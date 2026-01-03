# System Architecture

> **Architecture Pattern:** Hybrid Brain-Book Model (XML Logic + RAG Data)
> **Target Platform:** Google Gemini 1.5 Pro/Flash (1M+ context window)
> **Last Updated:** 2026-01-03

---

## 1. Architecture Overview

### 1.1 High-Level Design

```
┌────────────────────────────────────────────────────────────────┐
│                         USER INPUT                             │
│                  (Japanese Light Novel Text)                   │
└────────────────┬───────────────────────────────────────────────┘
                 │
                 ▼
┌────────────────────────────────────────────────────────────────┐
│                    GEMINI 1.5 PRO/FLASH                        │
│  ┌──────────────────────────────────────────────────────────┐ │
│  │ System Instruction (Brain - RAM)                         │ │
│  │ VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml (48KB)     │ │
│  │ ┌────────────────────────────────────────────────────┐   │ │
│  │ │ • RTAS Engine v2.0                                 │   │ │
│  │ │ • Boldness Module v1.0                             │   │ │
│  │ │ • Ruby Text Parsing v2.0                           │   │ │
│  │ │ • Romanization v2.0                                │   │ │
│  │ │ • Anti-Translationese Guardrails                   │   │ │
│  │ │ • Hybrid Honorific System                          │   │ │
│  │ │ • Conflict Resolution Rules                        │   │ │
│  │ └────────────────────────────────────────────────────┘   │ │
│  └──────────────────────────────────────────────────────────┘ │
│                                                                │
│  ┌──────────────────────────────────────────────────────────┐ │
│  │ Knowledge Base (Book - HDD)                              │ │
│  │ Reference/ directory (2.7MB)                             │ │
│  │ ┌────────────────────────────────────────────────────┐   │ │
│  │ │ Library Modules (External RAG)                     │   │ │
│  │ │ • Library_KANJI_KNOWLEDGE_BASE.md (2.4MB)          │   │ │
│  │ │ • Library_GOLDEN_SAMPLES.md (28KB)                 │   │ │
│  │ │ • Library_LOCALIZATION_PRIMER_VN.md (43KB)         │   │ │
│  │ └────────────────────────────────────────────────────┘   │ │
│  │ ┌────────────────────────────────────────────────────┐   │ │
│  │ │ Ref Modules (Integrated/Lookup)                    │   │ │
│  │ │ • Ref_VIETNAMESE_PRONOUN_SYSTEM.md (34KB)          │   │ │
│  │ │ • Ref_BOLDNESS_MODULE_v1.0.md (31KB)               │   │ │
│  │ │ • Ref_SENSORY_LEXICON.md (12KB)                    │   │ │
│  │ │ • Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (25KB)     │   │ │
│  │ │ • [13 more Ref modules...]                         │   │ │
│  │ └────────────────────────────────────────────────────┘   │ │
│  └──────────────────────────────────────────────────────────┘ │
└────────────────┬───────────────────────────────────────────────┘
                 │
                 ▼
┌────────────────────────────────────────────────────────────────┐
│                      DUAL-OUTPUT                               │
│  ┌────────────────────┐  ┌──────────────────────────────────┐ │
│  │ CHATBOX (Metadata) │  │ CANVAS (Clean Translation)       │ │
│  │ • RTAS Score       │  │ Tớ thích cậu.                    │ │
│  │ • Pronoun Pair     │  │ Từ lâu rồi... tớ đã thích cậu.   │ │
│  │ • Techniques Used  │  │                                  │ │
│  │ • Reasoning        │  │                                  │ │
│  └────────────────────┘  └──────────────────────────────────┘ │
└────────────────────────────────────────────────────────────────┘
```

### 1.2 Brain-Book Hybrid Model

**Brain (RAM):** In-memory logic
- **File:** `VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml` (48KB)
- **Loaded:** System Instruction (persistent across requests)
- **Contains:** Algorithms, decision trees, scoring tables, conflict resolution
- **Advantage:** Fast access, no RAG latency

**Book (HDD):** On-demand data
- **Files:** `Reference/*.md` (2.7MB)
- **Loaded:** Knowledge Base (RAG search on-demand)
- **Contains:** Kanji database, Golden Samples, Lexicons
- **Advantage:** Scalable, no token overhead unless queried

**Analogy:**
```
Brain (XML) = CPU instructions
Book (.md files) = Database tables
```

---

## 2. Core Modules

### 2.1 RTAS Engine v2.0

**Purpose:** Calculate Relationship Tension & Affection Score (1.0-5.0) to select appropriate pronoun pairs.

**Architecture:**

```
┌─────────────────────────────────────────────────────────────┐
│                   RTAS Calculation v2.0                     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ INPUT: Japanese Sentence                            │   │
│  │ Example: 「好きだ。ずっと前から、お前のことが好きだった」│  │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 1: Initialize Baseline                         │   │
│  │ RTAS = 3.0 (neutral relationship)                   │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 2: Apply Scoring Tables                        │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ PRONOUN_JP (俺/僕/お前/君...)                   │ │   │
│  │ │ Detected: お前 → +0.7                           │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ HONORIFIC_JP (-san/-kun/-chan...)               │ │   │
│  │ │ Detected: None → +0.4 (very close/disrespect)   │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ SENTENCE_ENDING (よ/ね/な/だ...)                │ │   │
│  │ │ Detected: だ → +0.2                             │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ CONTEXT_KEYWORDS (好き/殺す/告白...)            │ │   │
│  │ │ Detected: 好き (appears 2x) → +1.0             │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ PROXEMICS (耳元で/机を挟んで...)                │ │   │
│  │ │ Detected: None → 0                              │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │                                                     │   │
│  │ Subtotal: 3.0 + 0.7 + 0.4 + 0.2 + 1.0 = 5.3        │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 3: Conflict Resolution (Priority Overrides)    │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ YANDERE_PARADOX (殺す + 好き → 5.0)             │ │   │
│  │ │ Check: No 殺す detected → Skip                  │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ TSUNDERE_FLIP (嫌い + 赤面 → Visual Override)   │ │   │
│  │ │ Check: No 嫌い detected → Skip                  │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ KEIGO_WALL (です/ます + 怒り → 1.0)             │ │   │
│  │ │ Check: No です/ます detected → Skip             │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ VISUAL_OVERRIDE (Proxemics > Verbal)            │ │   │
│  │ │ Check: No proxemics → Skip                      │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │                                                     │   │
│  │ No conflicts → Keep subtotal: 5.3                  │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 4: Clamp to Range [1.0, 5.0]                   │   │
│  │ RTAS = min(max(5.3, 1.0), 5.0) = 5.0                │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ OUTPUT: RTAS = 5.0 (Maximum Affection)               │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘

                   │
                   ▼
┌─────────────────────────────────────────────────────────────┐
│               Pronoun Pair Selection                        │
├─────────────────────────────────────────────────────────────┤
│  RTAS = 5.0 → Em-Anh (romantic/intimate)                    │
│                                                             │
│  Mapping Table:                                             │
│  • 1.0-1.5: Tôi-Anh (hostile/distant)                       │
│  • 1.5-2.5: Tôi-Anh (defensive)                             │
│  • 2.0-3.5: Tớ-Cậu (friends)                                │
│  • 3.5-4.2: Tớ-Anh (friendly→romantic)                      │
│  • 4.2-5.0: Em-Anh (romantic/intimate)                      │
│                                                             │
│  OVERRIDE: Family context → Anh/Chị/Em/Ba/Mẹ               │
└─────────────────────────────────────────────────────────────┘
```

**Key Design Decisions:**

1. **Baseline = 3.0 (Neutral):**
   - Rationale: Most Light Novel relationships start neutral, then shift
   - Allows symmetric +/- modifiers

2. **Conflict Resolution Priority:**
   - Level 1 (CRITICAL): Yandere Paradox, Keigo Wall
   - Level 2 (HIGH): Tsundere Flip, Visual Override
   - Level 3 (NORMAL): Standard scoring tables

3. **Clamping [1.0, 5.0]:**
   - Prevents edge cases from breaking pronoun mapping
   - 1.0 = extreme hostility, 5.0 = extreme affection

---

### 2.2 Boldness Module v1.0

**Purpose:** Inject emotional intensity into translations when RTAS reaches extreme values (≤ 1.2 or ≥ 4.8).

**Architecture:**

```
┌─────────────────────────────────────────────────────────────┐
│              Boldness Module Activation                     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ INPUT: RTAS Score from RTAS Engine                  │   │
│  │ Example: RTAS = 4.9                                 │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ CHECK: RTAS ≥ 4.8 OR RTAS ≤ 1.2?                    │   │
│  │ → YES (4.9 ≥ 4.8) → ACTIVATE                        │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ TECHNIQUE 1: Sentence Shattering                    │   │
│  │ ───────────────────────────────────────────────     │   │
│  │ Before: "Tớ thích cậu từ lâu rồi"                   │   │
│  │ After:  "Tớ thích cậu.\n                            │   │
│  │          Từ lâu rồi... tớ đã thích cậu."            │   │
│  │                                                     │   │
│  │ Rules:                                              │   │
│  │ • Break at logical pauses (、。)                    │   │
│  │ • Add ellipsis (...) for emotion                    │   │
│  │ • Max 2 fragments per sentence                      │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ TECHNIQUE 2: Vivid Verb Replacement                 │   │
│  │ ───────────────────────────────────────────────     │   │
│  │ RAG Query: Ref_SENSORY_LEXICON.md                   │   │
│  │                                                     │   │
│  │ Before: "Nhiệt độ hiển thị 39.6"                    │   │
│  │ After:  "Màn hình hiện số. 39.6."                   │   │
│  │                                                     │   │
│  │ Replacement Table (200+ entries):                   │   │
│  │ • 表示された → "hiện số" (not "được hiển thị")     │   │
│  │ • 歩く → "lê bước" (not "đi bộ")                    │   │
│  │ • 見る → "nhìn chằm chằm" (not "nhìn")              │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ TECHNIQUE 3: Slang Injection (Level 1-5)            │   │
│  │ ───────────────────────────────────────────────     │   │
│  │ Level Selection:                                    │   │
│  │ IF RTAS ≥ 4.8: Level = min(floor((RTAS-4.8)*10), 5)│   │
│  │ IF RTAS ≤ 1.2: Level = min(floor((1.2-RTAS)*10), 5)│   │
│  │                                                     │   │
│  │ Example: RTAS = 4.9 → Level = floor(0.1*10) = 1    │   │
│  │                                                     │   │
│  │ Slang Levels:                                       │   │
│  │ • Level 1 (Safe): "nha", "nè", "ơi"                 │   │
│  │ • Level 2: "nha bạn ơi", "trời ơi"                  │   │
│  │ • Level 3: "toang", "die", "sốc nặng"               │   │
│  │ • Level 4: "cày", "flex", "xịn sò"                  │   │
│  │ • Level 5: "bựa", "nghiện", "phang"                 │   │
│  │                                                     │   │
│  │ Safety Rule: Level 1-2 for Publisher                │   │
│  │              Level 3-5 for Web Novel                │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ OUTPUT: Enhanced Translation                         │   │
│  │ "Tớ thích cậu.\n                                     │   │
│  │  Từ lâu rồi... tớ đã thích cậu."                     │   │
│  │ [No slang (Level 1 too mild for this example)]      │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

**Intensity Calibration:**

| RTAS Range | Boldness Level | Techniques Activated |
|-----------|---------------|---------------------|
| 4.8-4.9 | Low | Sentence Shattering only |
| 4.9-5.0 | Medium | + Vivid Verb (50%) |
| 5.0 | High | + Slang Level 1-2 |
| ≥ 5.0 (clamped) | MAX | All techniques, Slang Level 3-5 |

**Reverse Activation (Negative Emotion):**

| RTAS Range | Emotion Type | Techniques |
|-----------|-------------|-----------|
| 1.0-1.2 | Cold Anger | Short sentences, no particles |
| 0.5-1.0 | Hostility | Vivid Verb (aggressive), Slang Level 4-5 |

---

### 2.3 Ruby Text Parsing v2.0

**Purpose:** Handle furigana (振り仮名) with semantic awareness.

**Architecture:**

```
┌─────────────────────────────────────────────────────────────┐
│               Ruby Text Parsing v2.0                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ INPUT: Japanese Text with Furigana                  │   │
│  │ Example: 魔法<マホウ> (Kanji: 魔法, Ruby: マホウ)     │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 1: Detect Furigana Pattern                      │   │
│  │ Regex: ([一-龯]+)\u003c([ぁ-ん]+|[ァ-ヶー]+)\u003e            │   │
│  │ Capture Groups:                                      │   │
│  │ • Group 1 (Kanji): 魔法                              │   │
│  │ • Group 2 (Ruby): マホウ                             │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 2: Query Kanji Database                         │   │
│  │ RAG Search: Library_KANJI_KNOWLEDGE_BASE.md          │   │
│  │                                                      │   │
│  │ Query: "魔法"                                         │   │
│  │ Result:                                              │   │
│  │ • 魔 (ma) = magic                                    │   │
│  │ • 法 (pháp) = method/law                             │   │
│  │ → Semantic: "Ma pháp" (magic/sorcery)                │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 3: Strategy Selection                           │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ STRATEGY 1: Semantic Override                   │ │   │
│  │ │ Condition: Ruby matches standard ON-reading     │ │   │
│  │ │ Action: Use Kanji meaning                       │ │   │
│  │ │                                                 │ │   │
│  │ │ Check: マホウ = standard reading for 魔法       │ │   │
│  │ │ → YES → Use "Ma pháp"                           │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ STRATEGY 2: Sound Clash Detection               │ │   │
│  │ │ Condition: Ruby ≠ standard reading              │ │   │
│  │ │ Action: Romanize Ruby + add note                │ │   │
│  │ │                                                 │ │   │
│  │ │ Example: 愛\u003cラブ\u003e (Love pronounced "Love")   │ │   │
│  │ │ → "Tình yêu (Love)"                             │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ STRATEGY 3: Chuunibyou Names                    │ │   │
│  │ │ Condition: Ruby is foreign word                 │ │   │
│  │ │ Action: Translate Kanji + keep Ruby romanized   │ │   │
│  │ │                                                 │ │   │
│  │ │ Example: 聖剣\u003cエクスカリバー\u003e                   │ │   │
│  │ │ → "Thánh kiếm Excalibur"                        │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │                                                     │   │
│  │ Selected: STRATEGY 1 (Semantic Override)            │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ OUTPUT: "Ma pháp"                                    │   │
│  │ (Ruby text removed, semantic meaning preserved)     │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

**Edge Cases:**

1. **Multiple Readings:**
   ```
   生徒<せいと> vs 生徒<がくせい>
   → Both valid → Prefer frequency (せいと more common)
   ```

2. **Ateji (当て字):**
   ```
   珈琲<コーヒー> (Coffee)
   → Kanji is decorative → Use romanization "Cà phê"
   ```

3. **Nested Ruby:**
   ```
   超電磁砲<レールガン><S>
   → Flatten: "Railgun S" (Súng điện từ Railgun S)
   ```

---

### 2.4 Romanization v2.0

**Purpose:** Convert Japanese names to Vietnamese-friendly romanization with long vowel preservation.

**Architecture:**

```
┌─────────────────────────────────────────────────────────────┐
│              Romanization v2.0 Engine                       │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────────────────────────────────────────────┐   │
│  │ INPUT: Japanese Name (Hiragana/Katakana)            │   │
│  │ Example: 紅葉 → こうよう (Kōyō)                      │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 1: Convert to Romaji (Modified Hepburn)        │   │
│  │ こうよう → kouyou                                    │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 2: Apply Long Vowel Rules (15 patterns)        │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ Rule Table:                                     │ │   │
│  │ │ • おう → ō  (kouyou → kōyou)                    │ │   │
│  │ │ • えい → ē  (sensei → sensē)                    │ │   │
│  │ │ • おお → ō  (ooki → ōki)                        │ │   │
│  │ │ • ああ → ā  (okaasan → okāsan)                  │ │   │
│  │ │ • いい → ī  (oishii → oishī)                    │ │   │
│  │ │ • うう → ū  (yuuki → yūki)                      │ │   │
│  │ │ • [15 total patterns]                           │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │                                                     │   │
│  │ Apply: ou → ō                                       │   │
│  │ Result: kōyou                                       │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ STEP 3: Second Pass (remaining long vowels)         │   │
│  │ Apply: ou → ō (again for remaining)                 │   │
│  │ Result: kōyō                                        │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ OUTPUT: "Kōyō"                                       │   │
│  │ (Capitalize first letter for names)                 │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

**Rationale:**
- Vietnamese readers unfamiliar with "Kouyou" (looks awkward)
- "Kōyō" preserves phonetic accuracy
- Macrons (ō, ū, ā) standard in Japanese romanization systems

---

### 2.5 Anti-Translationese Guardrails

**Purpose:** Remove machine translation artifacts.

**Architecture:**

```
┌─────────────────────────────────────────────────────────────┐
│           Anti-Translationese Filter                        │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────────────────────────────────────────────┐   │
│  │ INPUT: Draft Translation (potentially translationese)│   │
│  │ Example: "Một cách nhanh chóng, anh ta đi vào phòng" │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ SCAN: 20+ Banned Patterns                            │   │
│  │ RAG Query: Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md     │   │
│  │                                                      │   │
│  │ Pattern Database:                                    │   │
│  │ • "Một cách [adv]" → [Vivid verb]                    │   │
│  │ • "Có vẻ như..." → Direct statement                  │   │
│  │ • "[Noun] của [pronoun]" → Rephrase                  │   │
│  │ • "Cảm xúc..." → Avoid noun abstraction              │   │
│  │ • [20+ patterns total]                               │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ MATCH DETECTED: "Một cách nhanh chóng"               │   │
│  │ Replacement Rule: Use vivid verb instead             │   │
│  │ → "Vội vã" or "Lao vào"                              │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ OUTPUT: "Anh vội vã bước vào phòng."                 │   │
│  │ (Natural Vietnamese, no translationese)              │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

**Top 5 Patterns (by frequency):**

1. `"Một cách [ADV]"` → **79% of cases** → Eliminate
2. `"Có vẻ như..."` → **45%** → Remove hedge
3. `"[N] của [PRO]"` → **38%** → Rephrase to "[PRO]... [N] [V]"
4. `"Cảm xúc..."` → **22%** → Use concrete verbs
5. `"Thực sự/thật sự"` → **18%** → Omit (implied)

---

## 3. Integration Architecture

### 3.1 Knowledge Base RAG Flow

```
┌─────────────────────────────────────────────────────────────┐
│                    Gemini RAG System                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ Translation Request:                                 │   │
│  │ "Translate: 魔法少女は強い"                          │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ XML Logic Layer (System Instruction)                 │   │
│  │ • Detect: 魔法 (need Kanji lookup)                   │   │
│  │ • Detect: 少女 (need Kanji lookup)                   │   │
│  │ • Trigger: RAG search request                        │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ Gemini RAG Engine                                    │   │
│  │ Query: "魔法" in Knowledge Base                      │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ Search: Library_KANJI_KNOWLEDGE_BASE.md         │ │   │
│  │ │ Result: 魔 (ma) + 法 (pháp) = "Ma pháp"         │ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  │ Query: "少女" in Knowledge Base                      │   │
│  │ ┌─────────────────────────────────────────────────┐ │   │
│  │ │ Search: Library_KANJI_KNOWLEDGE_BASE.md         │ │   │
│  │ │ Result: 少 (thiếu) + 女 (nữ) = "Thiếu nữ"      │ │   │
│  │ │ BUT: Collocation "魔法少女" = "Cô gái phép thuật"│ │   │
│  │ └─────────────────────────────────────────────────┘ │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ Context Injection (Back to XML Logic)                │   │
│  │ • 魔法 → "Ma pháp" (phép thuật)                      │   │
│  │ • 少女 → "Thiếu nữ" (but use "Cô gái" collocation)  │   │
│  │ • 強い → "Mạnh mẽ"                                   │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│                   ▼                                         │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ Final Translation:                                   │   │
│  │ "Cô gái phép thuật thật mạnh mẽ."                    │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

**RAG Latency:** ~200-500ms per query (Gemini internal)
**Cache:** Gemini caches frequent queries (e.g., common Kanji)

---

### 3.2 Dual-Output Protocol

```
┌─────────────────────────────────────────────────────────────┐
│                  Output Generation Flow                     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ Translation Complete                                 │   │
│  │ • RTAS: 4.9                                          │   │
│  │ • Pronoun Pair: Tớ-Cậu                               │   │
│  │ • Techniques: Sentence Shattering, Vivid Verb        │   │
│  │ • Translation: "Tớ thích cậu.\n..."                  │   │
│  └────────────────┬────────────────────────────────────┘   │
│                   │                                         │
│        ┌──────────┴──────────┐                              │
│        │                     │                              │
│        ▼                     ▼                              │
│  ┌──────────┐         ┌───────────────┐                    │
│  │ CHATBOX  │         │ CANVAS        │                    │
│  │ (Metadata)│         │ (Clean Output)│                    │
│  └────┬─────┘         └───────┬───────┘                    │
│       │                       │                              │
│       ▼                       ▼                              │
│  ┌──────────────────────────────────────────────────┐      │
│  │ Chatbox Content (Inside <thinking> tag):         │      │
│  │ ───────────────────────────────────────────       │      │
│  │ [ANALYSIS]                                        │      │
│  │ • Input: 「好きだ。ずっと前から、お前のことが好きだった」 │
│  │                                                   │      │
│  │ [RTAS CALCULATION]                                │      │
│  │ • Baseline: 3.0                                   │      │
│  │ • Pronoun お前: +0.7                              │      │
│  │ • Keyword 好き (x2): +1.0                         │      │
│  │ • Ending だ: +0.2                                 │      │
│  │ • TOTAL: 4.9                                      │      │
│  │                                                   │      │
│  │ [PRONOUN SELECTION]                               │      │
│  │ • RTAS 4.9 → Cặp Tớ-Cậu (intimate/affectionate)   │      │
│  │                                                   │      │
│  │ [TECHNIQUES APPLIED]                              │      │
│  │ • Sentence Shattering: Break at 。                │      │
│  │ • Vivid Verb: N/A (no verbs to enhance)           │      │
│  │ • Slang Injection: None (Level 1 too mild)        │      │
│  └──────────────────────────────────────────────────┘      │
│                                                             │
│  ┌──────────────────────────────────────────────────┐      │
│  │ Canvas Content (Clean Translation):              │      │
│  │ ───────────────────────────────────────────       │      │
│  │ Tớ thích cậu.                                     │      │
│  │ Từ lâu rồi... tớ đã thích cậu.                    │      │
│  └──────────────────────────────────────────────────┘      │
└─────────────────────────────────────────────────────────────┘
```

**User Interaction:**
1. User sees **Chatbox** = understand reasoning
2. User copies from **Canvas** = publish-ready text

---

## 4. Performance Optimization

### 4.1 Token Budget Management

**Current Allocation:**

| Component | Tokens | % | Strategy |
|-----------|--------|---|----------|
| XML Core | 14,225 | 1.3% | Minified, keep essential |
| Kanji DB | 983,174 | 88.3% | RAG on-demand |
| Golden Samples | ~7,000 | 0.6% | Cache frequent queries |
| Sensory Lexicon | ~3,000 | 0.3% | RAG on-demand |
| Other Ref | ~105,636 | 9.5% | Minify redundant content |
| **TOTAL** | **1,113,035** | **100%** | **Target: ≤ 1.5M** |

**Optimization Techniques:**

1. **XML Minification:**
   - Remove verbose examples → Move to Ref_ files
   - Abbreviate attributes: `modification` → `mod`
   - Inline short comments

2. **RAG Lazy Loading:**
   - Only query Kanji DB when unknown Kanji detected
   - Cache frequent queries (Gemini internal)

3. **Golden Samples Compression:**
   - Keep only 19 best examples (currently)
   - Remove redundant metadata

---

### 4.2 Latency Breakdown

**Average Translation Request (50-100 chars):**

| Stage | Latency | Notes |
|-------|---------|-------|
| Input parsing | 50ms | Detect furigana, pronouns |
| RTAS calculation | 100ms | Scoring tables + conflict resolution |
| RAG queries (Kanji) | 200-500ms | 2-5 queries per request |
| Boldness techniques | 150ms | If RTAS ≥ 4.8 |
| Anti-translationese | 100ms | Pattern matching |
| Output generation | 50ms | Dual-output formatting |
| **TOTAL** | **650-1000ms** | **P95: 1.2 seconds** |

**Bottleneck:** RAG queries (Kanji DB)
**Solution:** Cache common Kanji (top 1000) → Reduce latency to ~100ms

---

## 5. Failure Modes & Mitigation

### 5.1 Edge Cases

**Case 1: RTAS Overflow**
- **Scenario:** Multiple affection keywords → RTAS > 5.0
- **Mitigation:** Clamp to [1.0, 5.0] range
- **Fallback:** If clamped, log warning in Chatbox

**Case 2: Kanji Not in Database**
- **Scenario:** Rare Kanji (e.g., 鬻 - "sell")
- **Mitigation:** Romanize Kanji + add note "(Unknown: [Kanji])"
- **Fallback:** Use context clues for meaning

**Case 3: Conflicting RTAS Signals**
- **Scenario:** Yandere says "殺す" (kill) but uses -chan (affectionate)
- **Mitigation:** Conflict Resolution rules (Yandere Paradox)
- **Fallback:** Prioritize visual cues over verbal

**Case 4: No Pronoun Detected**
- **Scenario:** Japanese omits pronouns (zero pronoun)
- **Mitigation:** Inherit RTAS from previous sentence
- **Fallback:** Default to Tớ-Cậu (neutral)

**Case 5: Token Limit Exceeded**
- **Scenario:** User pastes entire chapter (>1M tokens)
- **Mitigation:** Chunk into 5-10 paragraph segments
- **Fallback:** Warn user, suggest batching

---

## 6. Future Architecture Enhancements

### 6.1 Planned Features (Phase 2-4)

**Multi-Speaker Dialogue Tagging:**
```
Current: "「好きだ」と彼は言った。"
         → "Tớ thích cậu," anh nói.

Future:  [Speaker: Haruto | RTAS: 4.9]
         "Tớ thích cậu," Haruto nói.
         (Auto-tag speakers, maintain RTAS per character)
```

**Genre-Specific Presets:**
```
Isekai Mode:
  - Prioritize fantasy terms (魔法 → "Ma pháp" not "Phép thuật")
  - Chuunibyou names → Romanize aggressively

Romance Mode:
  - Lower Boldness threshold (4.5 instead of 4.8)
  - More Sensory Lexicon usage
```

**A/B Testing Framework:**
```
Generate 2 versions:
  A: RTAS-based pronoun
  B: Fixed pronoun (user override)

User selects → Train preference model
```

---

**Document Version:** 1.0
**Last Updated:** 2026-01-03
**Maintainer:** Thang (thangdam7790@gmail.com)
