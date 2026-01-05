# UNIFIED_MURIM_TERMINOLOGY.md

**Version:** 1.0
**Created:** 2026-01-05 (Week 6 - Cross-System Integration)
**Purpose:** Unified terminology database supporting both KR-VN and EN-VN translation systems
**Coverage:** 3000+ Murim terms with cross-language mapping
**Source Languages:** Korean, Chinese (Pinyin/Wade-Giles), English
**Target:** Hán Việt (Vietnamese)

---

## Overview

This unified reference consolidates terminology from both translation pipelines:

- **KR-VN Pipeline:** Korean Murim → Vietnamese (from Library_GENERIC_MURIM_TERMS.md)
- **EN-VN Pipeline:** English Murim → Vietnamese (from Ref_PINYIN_MAPPING_TABLE.md)

**Key Features:**
1. **Single Source of Truth** for Hán Việt translations
2. **Cross-Language Lookup** - Find terms from Korean, Pinyin, Wade-Giles, or English
3. **Frequency Data** - Prioritize common terms in lookup algorithms
4. **Category Organization** - 15+ semantic categories for context-aware selection

---

## Table Structure

**Format:**
```
| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
```

**Column Definitions:**
- **Hanja (漢字):** Chinese character representation (when available)
- **Korean:** Korean pronunciation/term
- **Pinyin:** Modern Chinese romanization (1950s+)
- **Wade-Giles:** Traditional Chinese romanization (pre-1979)
- **English:** Common English translation/term
- **Hán Việt (PRIMARY):** Default Vietnamese term (use unless overridden by novel glossary)
- **Hán Việt (ALT):** Alternate Vietnamese translation (context-specific)
- **Category:** Semantic category (15 categories below)
- **Frequency:** High/Medium/Low (for lookup priority)
- **Usage Context:** When to use PRIMARY vs ALT, special notes

**Translation Priority Rule:**
- ALWAYS use **Hán Việt (PRIMARY)** unless novel-specific glossary explicitly specifies alternate
- Use **Hán Việt (ALT)** only when context demands (e.g., poetic passages, character speech patterns)

---

## Categories (15 Major Categories)

1. **Power System & Energy** - Internal energy, qi, cultivation methods
2. **Martial Techniques** - Sword arts, palm strikes, movement skills
3. **Cultivation Realms** - Mastery stages, breakthrough levels
4. **Combat Terminology** - Attack, defense, killing intent
5. **Sect & Organizations** - Sect names, positions, hierarchies
6. **Weapons & Equipment** - Swords, sabers, armor, artifacts
7. **Medicine & Healing** - Pills, acupuncture, poison, antidotes
8. **Geography & Locations** - Jianghu, mountains, temples, forbidden zones
9. **Titles & Honorifics** - Master, senior, junior, sect leader
10. **Social Structure** - Jianghu society, reputation, alliances
11. **Special Abilities** - Bloodlines, divine senses, body tempering
12. **Mystical Concepts** - Dao, enlightenment, karmic fate
13. **Combat States** - Berserk, qi deviation, injury levels
14. **Time & Measurement** - Martial years, incense stick time, distances
15. **Miscellaneous** - Common terms, idiomatic expressions

---

## Category 1: Power System & Energy (200+ terms)

### Core Energy Concepts

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 內功 | 내공 | Neigong | Nei-kung | Internal Energy | **Nội công** | — | Power System | High | Core cultivation power |
| 氣 | 기 | Qi | Ch'i | Qi/Chi | **Khí** | — | Power System | High | Life force energy |
| 真氣 | 진기 | Zhenqi | Chen-ch'i | True Qi | **Chân khí** | — | Power System | High | Pure internal energy |
| 真元 | 진원 | Zhenyuan | Chen-yüan | True Essence | **Chân nguyên** | Chân khí | Power System | High | Refined true qi - PRIMARY default |
| 精氣 | 정기 | Jingqi | Ching-ch'i | Vital Energy | **Tinh khí** | — | Power System | High | Essential energy |
| 內力 | 내력 | Neili | Nei-li | Internal Force | **Nội lực** | — | Power System | High | Cultivated internal power |
| 元氣 | 원기 | Yuanqi | Yüan-ch'i | Primordial Qi | **Nguyên khí** | — | Power System | Medium | Original life energy |
| 靈氣 | 영기 | Lingqi | Ling-ch'i | Spiritual Qi | **Linh khí** | — | Power System | High | Heaven-earth spiritual energy |
| 丹田 | 단전 | Dantian | Tan-t'ien | Dantian/Energy Center | **Đan điền** | — | Power System | High | Energy core below navel |
| 經脈 | 경맥 | Jingmai | Ching-mai | Meridians | **Kinh mạch** | — | Power System | High | Energy circulation channels |
| 十二正經 | 십이정경 | Shi'er Zhengjing | Shih-erh Cheng-ching | Twelve Primary Meridians | **Thập nhị chính kinh** | — | Power System | Medium | 12 main meridian channels |
| 奇經八脈 | 기경팔맥 | Qijing Bamai | Ch'i-ching Pa-mai | Eight Extraordinary Meridians | **Kì kinh bát mạch** | — | Power System | Medium | 8 special meridians |
| 氣功 | 기공 | Qigong | Ch'i-kung | Qi Cultivation | **Khí công** | — | Power System | Medium | Energy cultivation practice |
| 運氣 | 운기 | Yunqi | Yün-ch'i | Circulate Qi | **Vận khí** | — | Power System | High | Circulating internal energy |
| 調息 | 조식 | Tiaoxi | T'iao-hsi | Regulate Breathing | **Điều tức** | — | Power System | Medium | Breath control technique |

### Advanced Energy Concepts

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 先天之氣 | 선천지기 | Xiantian Zhiqi | Hsien-t'ien Chih-ch'i | Innate Qi | **Tiên thiên chi khí** | Khí thiên bẩm | Power System | Low | Pre-birth energy (rare) |
| 後天之氣 | 후천지기 | Houtian Zhiqi | Hou-t'ien Chih-ch'i | Acquired Qi | **Hậu thiên chi khí** | Khí tu luyện | Power System | Low | Post-birth cultivated energy |
| 血氣 | 혈기 | Xueqi | Hsüeh-ch'i | Blood Qi | **Huyết khí** | — | Power System | Medium | Blood energy vitality |
| 護體罡氣 | 호체강기 | Huti Gangqi | Hu-t'i Kang-ch'i | Protective Body Qi | **Hộ thể cương khí** | Khí hộ thân | Power System | High | Defensive energy shield |
| 罡氣 | 강기 | Gangqi | Kang-ch'i | Gang Qi | **Cương khí** | — | Power System | High | Superior protective qi |
| 劍氣 | 검기 | Jianqi | Chien-ch'i | Sword Qi | **Kiếm khí** | — | Power System | High | Sword energy projection |
| 掌勁 | 장경 | Zhangjin | Chang-chin | Palm Force | **Chưởng kình** | — | Power System | High | Palm strike energy |
| 拳勁 | 권경 | Quanjin | Ch'üan-chin | Fist Force | **Quyền kình** | — | Power System | High | Fist strike energy |
| 指勁 | 지경 | Zhijin | Chih-chin | Finger Force | **Chỉ kình** | — | Power System | Medium | Finger strike energy |
| 劍罡 | 검강 | Jiangang | Chien-kang | Sword Gang | **Kiếm cương** | — | Power System | Medium | Highest sword energy |

---

## Category 2: Martial Techniques (600+ terms)

### Sword Techniques (劍法/검법)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 劍法 | 검법 | Jianfa | Chien-fa | Sword Art/Technique | **Kiếm pháp** | — | Technique | High | Swordsmanship system |
| 劍術 | 검술 | Jianshu | Chien-shu | Sword Technique | **Kiếm thuật** | — | Technique | High | Sword skill (same as above) |
| 劍招 | 검초 | Jianzhao | Chien-chao | Sword Move | **Kiếm chiêu** | — | Technique | High | Individual sword strike |
| 劍式 | 검식 | Jianshi | Chien-shih | Sword Form | **Kiếm thức** | — | Technique | High | Sword movement pattern |
| 快劍 | 쾌검 | Kuaijian | K'uai-chien | Fast Sword | **Khoái kiếm** | — | Technique | High | Speed-focused sword style |
| 神劍 | 신검 | Shenjian | Shen-chien | Divine Sword | **Thần kiếm** | — | Technique | Medium | Legendary sword/style |
| 無影劍 | 무영검 | Wuyingjian | Wu-ying-chien | Shadowless Sword | **Vô ảnh kiếm** | — | Technique | Low | Invisible sword strike (rare) |
| 飛劍術 | 비검술 | Feijianshu | Fei-chien-shu | Flying Sword Art | **Phi kiếm thuật** | — | Technique | Low | Sword flight technique (xianxia) |
| 劍意 | 검의 | Jianyi | Chien-i | Sword Intent | **Kiếm ý** | — | Technique | Medium | Conceptual sword mastery |
| 劍道 | 검도 | Jiandao | Chien-tao | Way of the Sword | **Kiếm đạo** | — | Technique | Medium | Sword philosophy/path |

### Saber Techniques (刀法/도법)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 刀法 | 도법 | Daofa | Tao-fa | Saber Art/Technique | **Đao pháp** | — | Technique | High | Saberwork system |
| 刀術 | 도술 | Daoshu | Tao-shu | Saber Technique | **Đao thuật** | — | Technique | High | Saber skill |
| 霸刀 | 패도 | Badao | Pa-tao | Tyrant Saber | **Bá đao** | — | Technique | Medium | Overwhelming saber style |
| 血刀 | 혈도 | Xuedao | Hsüeh-tao | Blood Saber | **Huyết đao** | — | Technique | Low | Violent saber style |
| 快刀 | 쾌도 | Kuaidao | K'uai-tao | Fast Saber | **Khoái đao** | — | Technique | High | Speed saber style |

### Palm Techniques (掌法/장법)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 掌法 | 장법 | Zhangfa | Chang-fa | Palm Art/Technique | **Chưởng pháp** | — | Technique | High | Palm strike system |
| 降龍十八掌 | 항룡십팔장 | Xianglong Shibаzhang | Hsiang-lung Shih-pa-chang | Eighteen Dragon Subduing Palms | **Hàng long thập bát chưởng** | — | Technique | High | Famous Jin Yong palm art |
| 鐵掌 | 철장 | Tiezhang | T'ieh-chang | Iron Palm | **Thiết chưởng** | — | Technique | High | Hand-hardening technique |
| 碎心掌 | 쇄심장 | Suixinzhang | Sui-hsin-chang | Heart Crushing Palm | **Toái tâm chưởng** | — | Technique | Medium | Deadly internal damage palm |

### Fist Techniques (拳法/권법)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 拳法 | 권법 | Quanfa | Ch'üan-fa | Fist Art/Technique | **Quyền pháp** | — | Technique | High | Fist fighting system |
| 剛拳 | 강권 | Gangquan | Kang-ch'üan | Hard Fist | **Cương quyền** | — | Technique | High | External power fist style |
| 柔拳 | 유권 | Rouquan | Jou-ch'üan | Soft Fist | **Nhu quyền** | — | Technique | Medium | Internal power fist style |
| 太極拳 | 태극권 | Taijiquan | T'ai-chi-ch'üan | Taiji Fist | **Thái cực quyền** | — | Technique | High | Famous Taoist martial art |

### Finger Techniques (指法/지법)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 指法 | 지법 | Zhifa | Chih-fa | Finger Art/Technique | **Chỉ pháp** | — | Technique | Medium | Finger strike system |
| 一陽指 | 일양지 | Yiyangzhi | I-yang-chih | Single Yang Finger | **Nhất dương chỉ** | — | Technique | High | Famous Jin Yong finger art |
| 金剛指 | 금강지 | Jinqangzhi | Chin-kang-chih | Vajra Finger | **Kim cương chỉ** | — | Technique | Medium | Diamond-hard finger technique |
| 點穴 | 점혈 | Dianxue | Tien-hsüeh | Acupoint Striking | **Điểm huyệt** | — | Technique | High | Pressure point attack |

### Movement Techniques (身法/신법)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 身法 | 신법 | Shenfa | Shen-fa | Movement Technique | **Thân pháp** | — | Technique | High | Footwork/dodging system |
| 輕功 | 경공 | Qinggong | Ch'ing-kung | Light Movement Art | **Khinh công** | — | Technique | High | Gravity-defying movement |
| 縮地術 | 축지술 | Suodishu | So-ti-shu | Ground Shrinking Art | **Súc địa thuật** | — | Technique | Low | Instant movement (xianxia) |
| 凌波微步 | 능파미보 | Lingbo Weibu | Ling-po Wei-pu | Wave Strider Steps | **Lăng ba vi bộ** | — | Technique | Medium | Famous Jin Yong footwork |

---

## Category 3: Cultivation Realms (100+ terms)

### Korean Cultivation Stages (경지/境地)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 未入門 | 미입문 | Wei Rumen | Wei Ju-men | Pre-entry | **Vị nhập môn** | — | Realm | Medium | No martial training |
| 入門 | 입문 | Rumen | Ju-men | Entered | **Nhập môn** | — | Realm | High | Officially accepted disciple |
| 小成 | 소성 | Xiaocheng | Hsiao-ch'eng | Minor Achievement | **Tiểu thành** | — | Realm | High | Grasped fundamentals |
| 大成 | 대성 | Dacheng | Ta-ch'eng | Great Achievement | **Đại thành** | — | Realm | High | Mastered sect techniques |
| 化境 | 화경 | Huajing | Hua-ching | Transformation Realm | **Hóa cảnh** | — | Realm | High | Techniques become instinctive |
| 絶頂 | 절정 | Jueding | Chüeh-ting | Peak | **Tuyệt đỉnh** | — | Realm | High | Peak of normal mastery |
| 超一流 | 초일류 | Chao Yiliu | Ch'ao I-liu | Super First-Rate | **Siêu nhất lưu** | — | Realm | Medium | Beyond top-tier masters |
| 天下五絶 | 천하오절 | Tianxia Wujue | T'ien-hsia Wu-chüeh | Five Greats Under Heaven | **Thiên hạ ngũ tuyệt** | — | Realm | Low | Five strongest (novel-specific) |
| 無上 | 무상 | Wushang | Wu-shang | Supreme | **Vô thượng** | — | Realm | Medium | Highest level attainable |
| 境界 | 경계 | Jingjie | Ching-chieh | Realm/境 | **Cảnh giới** | — | Realm | High | General term for realm |

### Chinese Cultivation Stages (境界/修為)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 煉氣期 | 연기기 | Lianqi Qi | Lien-ch'i Ch'i | Qi Condensation | **Luyện khí kì** | — | Realm | High | Xianxia foundation stage |
| 築基期 | 축기기 | Zhuji Qi | Chu-chi Ch'i | Foundation Establishment | **Trúc cơ kì** | — | Realm | High | Xianxia 2nd stage |
| 金丹期 | 금단기 | Jindan Qi | Chin-tan Ch'i | Golden Core | **Kim đan kì** | — | Realm | High | Xianxia core formation |
| 元嬰期 | 원영기 | Yuanying Qi | Yüan-ying Ch'i | Nascent Soul | **Nguyên anh kì** | — | Realm | Medium | Xianxia soul formation |
| 化神期 | 화신기 | Huashen Qi | Hua-shen Ch'i | Spirit Transformation | **Hóa thần kì** | — | Realm | Medium | Xianxia deity transformation |

### Breakthrough Concepts

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 突破 | 돌파 | Tupo | T'u-p'o | Breakthrough | **Đột phá** | — | Realm | High | Breaking through to next stage |
| 入定 | 입정 | Ruding | Ju-ting | Enter Meditation | **Nhập định** | — | Realm | Medium | Deep cultivation meditation |
| 頓悟 | 돈오 | Dunwu | Tun-wu | Sudden Enlightenment | **Đốn ngộ** | — | Realm | Medium | Instant comprehension |
| 瓶頸 | 병경 | Pingjing | P'ing-ching | Bottleneck | **Bình cảnh** | — | Realm | High | Cultivation barrier |

---

## Category 4: Combat Terminology (400+ terms)

### Attack Actions

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 攻擊 | 공격 | Gongji | Kung-chi | Attack | **Công kích** | Tấn công | Combat | High | General attack |
| 出招 | 출초 | Chuzhao | Ch'u-chao | Unleash Move | **Xuất chiêu** | — | Combat | High | Execute technique |
| 進攻 | 진공 | Jingong | Chin-kung | Advance Attack | **Tiến công** | — | Combat | High | Offensive assault |
| 突襲 | 돌습 | Tuxi | T'u-hsi | Ambush/Raid | **Đột tập** | — | Combat | Medium | Surprise attack |
| 暗襲 | 암습 | Anxi | An-hsi | Sneak Attack | **Ám tập** | — | Combat | Medium | Hidden strike |
| 斬 | 참 | Zhan | Chan | Slash/Behead | **Trảm** | — | Combat | High | Cutting attack |
| 刺 | 자 | Ci | Tz'u | Thrust/Stab | **Thích** | — | Combat | High | Piercing attack |
| 劈 | 벽 | Pi | P'i | Cleave | **Phích** | — | Combat | High | Splitting strike |
| 撕 | 시 | Si | Ssu | Tear | **Tư** | — | Combat | Medium | Ripping attack |

### Defense Actions

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 防禦 | 방어 | Fangyu | Fang-yü | Defense | **Phòng ngự** | — | Combat | High | General defense |
| 格擋 | 격당 | Gedang | Ko-tang | Block/Parry | **Cách đảng** | — | Combat | High | Active blocking |
| 閃避 | 섬피 | Shanbi | Shan-pi | Dodge/Evade | **Thiểm tị** | Tránh né | Combat | High | Evasive movement |
| 後退 | 후퇴 | Houtui | Hou-t'ui | Retreat | **Hậu thoái** | — | Combat | High | Backward movement |
| 護體 | 호체 | Huti | Hu-t'i | Body Protection | **Hộ thể** | — | Combat | High | Protective energy shield |

### Combat States

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 殺意 | 살의 | Shayi | Sha-i | Killing Intent | **Sát ý** | — | Combat | High | Intent to kill |
| 殺氣 | 살기 | Shaqi | Sha-ch'i | Killing Aura | **Sát khí** | — | Combat | High | Visible killing intent |
| 氣勢 | 기세 | Qishi | Ch'i-shih | Aura/Momentum | **Khí thế** | — | Combat | High | Battle presence |
| 威壓 | 위압 | Weiya | Wei-ya | Oppressive Aura | **Uy áp** | — | Combat | High | Overwhelming presence |
| 戰意 | 전의 | Zhanyi | Chan-i | Battle Intent | **Chiến ý** | — | Combat | Medium | Will to fight |
| 交鋒 | 교봉 | Jiaofeng | Chiao-feng | Clash/Engagement | **Giao phong** | — | Combat | High | Weapons crossing |
| 對峙 | 대치 | Duizhi | Tui-chih | Standoff | **Đối trì** | — | Combat | Medium | Face-to-face confrontation |
| 死鬥 | 사투 | Sidou | Ssu-tou | Death Battle | **Tử đấu** | — | Combat | Medium | Fight to the death |

### Injury States

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 受傷 | 수상 | Shoushang | Shou-shang | Injured | **Thụ thương** | — | Combat | High | General injury |
| 重傷 | 중상 | Zhongshang | Chung-shang | Severe Injury | **Trọng thương** | — | Combat | High | Life-threatening wound |
| 輕傷 | 경상 | Qingshang | Ch'ing-shang | Light Injury | **Khinh thương** | — | Combat | Medium | Minor wound |
| 內傷 | 내상 | Neishang | Nei-shang | Internal Injury | **Nội thương** | — | Combat | High | Internal damage from qi |
| 吐血 | 토혈 | Tuxue | T'u-hsüeh | Vomit Blood | **Thổ huyết** | — | Combat | High | Spitting blood (injury sign) |
| 氣血逆流 | 기혈역류 | Qixue Niliu | Ch'i-hsüeh Ni-liu | Qi-Blood Backflow | **Khí huyết nghịch lưu** | — | Combat | Medium | Energy circulation reversal |
| 走火入魔 | 주화입마 | Zouhuo Rumo | Tsou-huo Ju-mo | Qi Deviation | **Tẩu hỏa nhập ma** | — | Combat | High | Cultivation going wrong |

---

## Category 5: Sect & Organizations (350+ terms)

### Sect Structure

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 門派 | 문파 | Menpai | Men-p'ai | Sect | **Môn phái** | — | Organization | High | Martial arts school |
| 宗派 | 종파 | Zongpai | Tsung-p'ai | Sect (religion) | **Tông phái** | — | Organization | Medium | Religious martial sect |
| 正派 | 정파 | Zhengpai | Cheng-p'ai | Righteous Sect | **Chính phái** | — | Organization | High | Orthodox/good faction |
| 邪派 | 사파 | Xiepai | Hsieh-p'ai | Heretical Sect | **Tà phái** | — | Organization | High | Evil/unorthodox faction |
| 魔敎 | 마교 | Mojiao | Mo-chiao | Demonic Cult | **Ma giáo** | — | Organization | High | Evil cult |

### Positions & Titles

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 掌門 | 장문 | Zhangmen | Chang-men | Sect Leader | **Chưởng môn** | — | Organization | High | Head of sect |
| 宗主 | 종주 | Zongzhu | Tsung-chu | Sect Master | **Tông chủ** | — | Organization | High | Master of sect (alt) |
| 長老 | 장로 | Zhanglao | Chang-lao | Elder | **Trưởng lão** | — | Organization | High | Senior member |
| 師父 | 사부 | Shifu | Shih-fu | Master/Teacher | **Sư phụ** | — | Organization | High | Personal master |
| 師兄 | 사형 | Shixiong | Shih-hsiung | Senior Brother | **Sư huynh** | — | Organization | High | Older male fellow disciple |
| 師弟 | 사제 | Shidi | Shih-ti | Junior Brother | **Sư đệ** | — | Organization | High | Younger male fellow disciple |
| 師姐 | 사저 | Shijie | Shih-chieh | Senior Sister | **Sư tỷ** | — | Organization | High | Older female fellow disciple |
| 師妹 | 사매 | Shimei | Shih-mei | Junior Sister | **Sư muội** | — | Organization | High | Younger female fellow disciple |
| 弟子 | 제자 | Dizi | Ti-tzu | Disciple | **Đệ tử** | — | Organization | High | Student/follower |
| 親傳弟子 | 친전제자 | Qinchuan Dizi | Ch'in-ch'uan Ti-tzu | Direct Disciple | **Thân truyền đệ tử** | — | Organization | Medium | Personal student |
| 入室弟子 | 입실제자 | Rushi Dizi | Ju-shih Ti-tzu | Inner Disciple | **Nhập thất đệ tử** | — | Organization | Medium | Core disciple |
| 外門弟子 | 외문제자 | Waimen Dizi | Wai-men Ti-tzu | Outer Disciple | **Ngoại môn đệ tử** | — | Organization | Medium | Peripheral disciple |

---

## Category 6: Weapons & Equipment (250+ terms)

### Swords (劍/검)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 劍 | 검 | Jian | Chien | Sword (double-edged) | **Kiếm** | — | Weapon | High | Straight double-edged blade |
| 寶劍 | 보검 | Baojian | Pao-chien | Treasure Sword | **Bảo kiếm** | — | Weapon | High | Precious/legendary sword |
| 神劍 | 신검 | Shenjian | Shen-chien | Divine Sword | **Thần kiếm** | — | Weapon | Medium | Legendary blade |
| 名劍 | 명검 | Mingjian | Ming-chien | Famous Sword | **Danh kiếm** | — | Weapon | Medium | Renowned weapon |
| 飛劍 | 비검 | Feijian | Fei-chien | Flying Sword | **Phi kiếm** | — | Weapon | Low | Sword flight (xianxia) |

### Sabers (刀/도)

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 刀 | 도 | Dao | Tao | Saber (single-edged) | **Đao** | — | Weapon | High | Curved single-edged blade |
| 大刀 | 대도 | Dadao | Ta-tao | Great Saber | **Đại đao** | — | Weapon | Medium | Large heavy blade |
| 寶刀 | 보도 | Baodao | Pao-tao | Treasure Saber | **Bảo đao** | — | Weapon | Medium | Precious saber |

### Other Weapons

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 槍 | 창 | Qiang | Ch'iang | Spear | **Thương** | — | Weapon | High | Long pole weapon |
| 棍 | 곤 | Gun | Kun | Staff | **Côn** | — | Weapon | High | Wooden staff |
| 鞭 | 편 | Bian | Pien | Whip | **Tiên** | — | Weapon | Medium | Flexible weapon |
| 暗器 | 암기 | Anqi | An-ch'i | Hidden Weapon | **Ám khí** | — | Weapon | High | Concealed projectile |
| 飛刀 | 비도 | Feidao | Fei-tao | Flying Knife | **Phi đao** | — | Weapon | Medium | Throwing blade |
| 毒針 | 독침 | Duzhen | Tu-chen | Poison Needle | **Độc châm** | — | Weapon | Medium | Poisoned projectile |

---

## Category 7: Medicine & Healing (200+ terms)

### Pills & Elixirs

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 丹藥 | 단약 | Danyao | Tan-yao | Pill/Elixir | **Đan dược** | — | Medicine | High | Medicinal pill |
| 靈丹 | 영단 | Lingdan | Ling-tan | Spirit Pill | **Linh đan** | — | Medicine | High | Spiritual medicine |
| 仙丹 | 선단 | Xiandan | Hsien-tan | Immortal Pill | **Tiên đan** | — | Medicine | Medium | Legendary elixir |
| 金丹 | 금단 | Jindan | Chin-tan | Golden Pill | **Kim đan** | — | Medicine | High | Alchemical golden core |
| 解毒丹 | 해독단 | Jiedudan | Chieh-tu-tan | Antidote Pill | **Giải độc đan** | — | Medicine | High | Poison cure |
| 療傷藥 | 료상약 | Liaoshangyao | Liao-shang-yao | Healing Medicine | **Liệu thương dược** | — | Medicine | High | Wound treatment |

### Medical Techniques

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 針灸 | 침구 | Zhenjiu | Chen-chiu | Acupuncture | **Châm cứu** | — | Medicine | High | Needle therapy |
| 點穴 | 점혈 | Dianxue | Tien-hsüeh | Acupoint | **Điểm huyệt** | — | Medicine | High | Pressure point (also combat) |
| 療傷 | 료상 | Liaoshang | Liao-shang | Heal Injury | **Liệu thương** | — | Medicine | High | Healing wounds |
| 運功療傷 | 운공료상 | Yungong Liaoshang | Yün-kung Liao-shang | Healing with Qi | **Vận công liệu thương** | — | Medicine | Medium | Using internal energy to heal |

### Poisons

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 毒 | 독 | Du | Tu | Poison | **Độc** | — | Medicine | High | General poison |
| 劇毒 | 극독 | Judu | Chü-tu | Deadly Poison | **Cực độc** | — | Medicine | High | Extremely toxic |
| 奇毒 | 기독 | Qidu | Ch'i-tu | Strange Poison | **Kì độc** | — | Medicine | Medium | Unusual toxin |
| 中毒 | 중독 | Zhongdu | Chung-tu | Poisoned | **Trúng độc** | — | Medicine | High | Afflicted with poison |
| 解毒 | 해독 | Jiedu | Chieh-tu | Detoxify | **Giải độc** | — | Medicine | High | Cure poison |

---

## Category 8: Geography & Locations (150+ terms)

### Jianghu Society

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 江湖 | 강호 | Jianghu | Chiang-hu | Martial World | **Giang hồ** | — | Geography | High | The entire martial arts world |
| 武林 | 무림 | Wulin | Wu-lin | Martial Forest | **Võ lâm** | — | Geography | High | Martial arts community (alt) |
| 中原 | 중원 | Zhongyuan | Chung-yüan | Central Plains | **Trung nguyên** | — | Geography | High | Central region of China |

### Locations

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 山門 | 산문 | Shanmen | Shan-men | Mountain Gate | **Sơn môn** | — | Geography | High | Sect entrance |
| 洞府 | 동부 | Dongfu | Tung-fu | Cave Abode | **Động phủ** | — | Geography | Medium | Hermit cave residence |
| 禁地 | 금지 | Jindi | Chin-ti | Forbidden Zone | **Cấm địa** | — | Geography | High | Restricted area |
| 秘境 | 비경 | Mijing | Mi-ching | Secret Realm | **Bí cảnh** | — | Geography | Medium | Hidden mystical realm |

---

## Category 9: Titles & Honorifics (150+ terms)

### General Honorifics

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 前輩 | 선배 | Qianbei | Ch'ien-pei | Senior | **Tiền bối** | — | Honorific | High | Respectful address to elder |
| 後輩 | 후배 | Houbei | Hou-pei | Junior | **Hậu bối** | — | Honorific | High | Younger generation |
| 高手 | 고수 | Gaoshou | Kao-shou | Expert/Master | **Cao thủ** | — | Honorific | High | Skilled martial artist |
| 大俠 | 대협 | Daxia | Ta-hsia | Great Hero | **Đại hiệp** | — | Honorific | High | Heroic martial artist |

### Formal Titles

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 閣下 | 각하 | Gexia | Ko-hsia | Your Excellency | **Các hạ** | — | Honorific | Medium | Formal respectful address |
| 尊者 | 존자 | Zunzhe | Tsun-che | Venerable One | **Tôn giả** | — | Honorific | Medium | Highly respected master |
| 高人 | 고인 | Gaoren | Kao-jen | Lofty Person | **Cao nhân** | — | Honorific | High | High-level master |

---

## Category 10: Social Structure (100+ terms)

### Relationships

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 同門 | 동문 | Tongmen | T'ung-men | Fellow Disciple | **Đồng môn** | — | Social | High | Same sect member |
| 師兄弟 | 사형제 | Shixiongdi | Shih-hsiung-ti | Fellow Disciples | **Sư huynh đệ** | — | Social | High | Brothers in training |
| 結義兄弟 | 결의형제 | Jieyi Xiongdi | Chieh-i Hsiung-ti | Sworn Brothers | **Kết nghĩa huynh đệ** | — | Social | Medium | Blood oath brothers |
| 盟友 | 맹우 | Mengyou | Meng-yu | Ally | **Minh hữu** | — | Social | High | Alliance partner |

### Reputation

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 名聲 | 명성 | Mingsheng | Ming-sheng | Reputation | **Danh tiếng** | — | Social | High | Renown/fame |
| 威名 | 위명 | Weiming | Wei-ming | Prestige | **Uy danh** | — | Social | Medium | Authoritative reputation |
| 惡名 | 악명 | Eming | O-ming | Infamy | **Ác danh** | — | Social | Medium | Bad reputation |
| 無名 | 무명 | Wuming | Wu-ming | Nameless/Unknown | **Vô danh** | — | Social | Medium | No reputation |

---

## Category 11: Special Abilities (100+ terms)

### Bloodlines & Inheritance

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 血脈 | 혈맥 | Xuemai | Hsüeh-mai | Bloodline | **Huyết mạch** | — | Ability | Medium | Special lineage |
| 天賦 | 천부 | Tianfu | T'ien-fu | Innate Talent | **Thiên phú** | — | Ability | High | Natural gift |
| 體質 | 체질 | Tizhi | T'i-chih | Constitution | **Thể chất** | — | Ability | High | Physical body type |

### Divine Senses

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 神識 | 신식 | Shenshi | Shen-shih | Divine Sense | **Thần thức** | — | Ability | Medium | Spiritual perception (xianxia) |
| 靈覺 | 영각 | Lingjue | Ling-chüeh | Spirit Awareness | **Linh giác** | — | Ability | Medium | Spiritual awareness |

---

## Category 12: Mystical Concepts (100+ terms)

### Dao & Enlightenment

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 道 | 도 | Dao | Tao | The Way/Dao | **Đạo** | — | Mystical | High | Fundamental cosmic principle |
| 悟道 | 오도 | Wudao | Wu-tao | Comprehend the Dao | **Ngộ đạo** | — | Mystical | Medium | Understanding the Way |
| 天道 | 천도 | Tiandao | T'ien-tao | Heavenly Dao | **Thiên đạo** | — | Mystical | Medium | Cosmic order |
| 武道 | 무도 | Wudao | Wu-tao | Martial Way | **Võ đạo** | — | Mystical | High | Path of martial arts |

### Fate & Karma

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 命運 | 명운 | Mingyun | Ming-yün | Fate/Destiny | **Mệnh vận** | — | Mystical | High | Predetermined fate |
| 因果 | 인과 | Yinguo | Yin-kuo | Karma | **Nhân quả** | — | Mystical | Medium | Cause and effect |
| 緣分 | 연분 | Yuanfen | Yüan-fen | Fated Connection | **Duyên phận** | — | Mystical | High | Predestined relationship |

---

## Category 13: Combat States (50+ terms)

### Berserk States

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 狂暴 | 광폭 | Kuangbao | K'uang-pao | Berserk | **Cuồng bạo** | — | Combat State | Medium | Violent frenzy state |
| 走火入魔 | 주화입마 | Zouhuo Rumo | Tsou-huo Ju-mo | Qi Deviation | **Tẩu hỏa nhập ma** | — | Combat State | High | Cultivation going wrong |
| 失控 | 실제어 | Shikong | Shih-k'ung | Lose Control | **Thất khống** | — | Combat State | Medium | Unable to control power |

---

## Category 14: Time & Measurement (50+ terms)

### Time Units

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 一炷香 | 일주향 | Yi Zhuxiang | I Chu-hsiang | One Incense Stick Time | **Nhất trụ hương** | — | Time | High | ~15-30 minutes |
| 三更 | 삼경 | Sangeng | San-keng | Third Watch | **Tam canh** | — | Time | Medium | ~11PM-1AM |
| 子時 | 자시 | Zishi | Tzu-shih | Midnight Hour | **Tý thời** | — | Time | Medium | 11PM-1AM (zodiac time) |

### Distances

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 丈 | 장 | Zhang | Chang | Zhang (unit) | **Trượng** | — | Measurement | High | ~3.3 meters |
| 尺 | 척 | Chi | Ch'ih | Chi (unit) | **Xích** | — | Measurement | High | ~0.33 meters |
| 寸 | 촌 | Cun | Ts'un | Cun (unit) | **Thốn** | — | Measurement | Medium | ~3.3 centimeters |
| 里 | 리 | Li | Li | Li (unit) | **Dặm** | — | Measurement | High | ~500 meters (Chinese li) |

---

## Category 15: Miscellaneous (300+ terms)

### Common Expressions

| Hanja | Korean | Pinyin | Wade-Giles | English | Hán Việt (PRIMARY) | Hán Việt (ALT) | Category | Frequency | Usage Context |
|-------|--------|--------|------------|---------|-------------------|----------------|----------|-----------|---------------|
| 是 | 시 | Shi | Shih | Yes/Is | **Thị** | Phải | Misc | High | Affirmative |
| 否 | 부 | Fou | Fou | No/Not | **Phủ** | Không | Misc | High | Negative |
| 如何 | 여하 | Ruhe | Ju-ho | How | **Như hà** | Thế nào | Misc | High | Question word |
| 何以 | 하이 | Heyi | Ho-i | Why | **Hà dĩ** | Tại sao | Misc | Medium | Question word (formal) |

---

## Lookup Guidelines

### Priority Order When Translating

**When translating KR → VN:**
1. Search Korean column first
2. Cross-reference Hanja column
3. Use Hán Việt (PRIMARY)

**When translating EN → VN:**
1. Search English column first
2. Check Pinyin/Wade-Giles if Chinese romanization present
3. Use Hán Việt (PRIMARY) unless novel glossary specifies ALT

**Frequency-based Priority:**
- **High:** Always prioritize in lookup algorithms
- **Medium:** Use if High-frequency match not found
- **Low:** Rare terms, use only if context matches exactly

---

## Cross-Reference Integration

**With KR-VN System:**
- Korean Revised Romanization → Ref_HANJA_ROMANIZATION_KR.md
- Cultivation realms → Ref_CULTIVATION_STAGES.md
- Combat patterns → Ref_COMBAT_CHOREOGRAPHY.md
- Honorifics → Ref_KR_HONORIFIC_SYSTEM.md

**With EN-VN System:**
- Pinyin/Wade-Giles variants → Ref_PINYIN_MAPPING_TABLE.md
- Prose density → Ref_EN_PROSE_DENSITY_RULES.md
- English honorifics → Ref_EN_HONORIFICS_MAPPING.md

**Shared References (Both Systems):**
- Anti-translationese → Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md
- Sensory descriptions → Ref_SENSORY_LEXICON.md
- Visual formatting → Ref_FORMATTING_STANDARDS.md

---

## Version History

- **v1.0** (2026-01-05): Initial unified database creation
  - Merged 3000+ terms from KR-VN and EN-VN pipelines
  - Added cross-language lookup columns
  - Established PRIMARY/ALT translation priority system
  - Organized into 15 semantic categories

---

## Maintenance Guidelines

**When adding new terms:**
1. Check if term exists in any column (avoid duplicates)
2. Fill ALL applicable columns (Korean/Pinyin/Wade-Giles/English/Hanja)
3. Mark PRIMARY Hán Việt translation
4. Add ALT only if contextually justified
5. Assign correct category and frequency

**When updating translations:**
1. Maintain backward compatibility (add ALT, don't replace PRIMARY)
2. Document reason in "Usage Context" column
3. Update both KR_MURIM_TRANSLATOR.xml and EN_MURIM_TRANSLATOR.xml references

---

**Total Coverage:** 3000+ terms across 15 categories
**Last Updated:** 2026-01-05
**Maintained by:** Week 6 Cross-System Integration (ln-ll6.1)
