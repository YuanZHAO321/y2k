# Week 6 — 底栖大型无脊椎动物鉴定与河流健康评估 (Identification of Benthic Macroinvertebrates & Assessing the Health of Rivers)

> 授课人：Dr Cecilia Medupin
> 本周材料：
> - `Practical Skills _Identification of organisms part 1(1).md`（生物鉴定 Part 1：分类学、采样、解剖显微镜）
> - `Practical Skills _Identification of organisms part 2(1).md`（生物鉴定 Part 2：各门/纲/目形态鉴定要点与污染分值）
> - `Practical Sheet _Assessing the health of rivers(2)(1).md`（河流健康评估实践表：BMWP / ASPT 计算与课堂练习）
> - 配套图表：`The freshwater name trail ID Chart pg 2(1).jpg`（Freshwater Name Trail 二歧检索表 ID 图卡，图片形式，未转文字）

---

## 一、本周主题

本周训练的是**环境科学野外—实验室联动的生物监测技能链**：从**河流采样 (kick sampling)** → **解剖显微镜下的标本鉴定 (identification)** → **用生物指示物打分评估河流生态健康 (BMWP / ASPT)**。这是 EART11300 十周实践课（Week 1、2、4、5、6、7、8、9、10、11）中第五次实践，属于**生物/环境科学取向**的一周：与前后周的岩矿、野外记录、测量类技能并列，本周补上"活体指标 (biological indicator)"这条独立于化学分析的环境评价路径，同时第一次系统教授**分类学 (taxonomy)** 与**二歧检索表 (dichotomous key)** 的使用方法。

本周的可迁移技能有三条：
1. 会用**双名法 (binomial nomenclature)** 与分类阶元准确称呼一个生物；
2. 会**看形态特征做类群判别**（这是所有地球与生命科学"标本鉴定"的通用套路，和矿物鉴定、化石鉴定同构）；
3. 会把**定性观察转成定量指标并解释**（BMWP/ASPT 打分 → 生态状态判读）。

---

## 二、核心概念

### 2.1 为什么关心河流健康：淡水的稀缺性

| 水体 | 占全球水量比例 |
| --- | --- |
| 海水 (seawater) | 97.75% |
| 冰川 (glaciers) | 2.24% |
| 湖泊 (lakes) | 0.009% |
| **河流 (rivers)** | **0.0001%** |

我们赖以饮用与生存的淡水占比极小（湖泊 0.009%，河流仅 0.0001%），因此保持淡水清洁"至关重要 (vitally important)"。**这组数字是本周材料的开场论据，考试中若问"为什么要监测河流"，先答稀缺性。**

### 2.2 河流污染的来源 (sources of pollution)

材料中列出的污染与破坏来源：

- **点源 (direct/point source)**：工业废水 (effluent from industries)——石油与有毒化学品 (oil and toxic chemicals)；
- **非点源 / 面源 (non-direct source)**：渗漏 (leakages)、污水 (sewage)、**合流制下水道溢流 (combined sewer overflows, CSO)**、道路径流 (runoff from roads)；
- **农业活动 (agricultural activities)**：化肥 (fertilisers) 与农药 (pesticides)；
- **物理/水文性破坏**：城市化加剧 (increased urbanisation)、**大坝与运河的修建 (construction of dams and canals)**——注意材料的表述是这些工程"increase water flow"（改变了水流条件）。

### 2.3 监管框架 (regulatory context)

- 河流的重要性在**国家与国际层面**均已被承认。
- **欧盟《水框架指令》(Water Framework Directive, WFD)**：要求所有水源达到"良好 (good)"生态状态 (good ecological condition)。
- **英格兰环境署 (Environment Agency)**：用**生活在水中的生物指示物 (biological indicators)** 加上**化学分析 (chemical analysis)** 两条腿监测河流质量。
- 本周活动的定位就是：体验如何用**无脊椎动物种群 (invertebrate populations)** 监测淡水质量、判定河流的**生态状态 (ecological status)**。

### 2.4 生物指示的原理：有机污染 → 溶解氧 → 物种筛选

这是本周**最核心的因果链**，必须能完整复述：

```
有机物输入（污水 sewage / 食物废弃物 food waste / 农场废液 farm effluent）
        ↓
细菌与其他微生物取食这些有机物 (bacteria and other microorganisms feed on it)
        ↓
微生物消耗掉水中可利用的氧 (use up the available oxygen)
        ↓
溶解氧 (dissolved oxygen, DO) 下降
        ↓
能够存活的无脊椎动物种类变少 (fewer invertebrate species survive)
        ↓
群落组成 = 水质的"记录仪"
```

要点：
- **大多数河流污染由有机物添加造成**（"Most river pollution is caused by the addition of organic material"），主要是污水。
- **未污染河流**：高溶解氧 + 水生无脊椎动物**多样性高 (wide diversity)**。
- 因此可按对**低氧的耐受能力 (ability to tolerate low levels of oxygen)** 给类群排序：
  - **石蝇 (stoneflies)、蜉蝣 (mayflies)** —— 只能生活在**高氧（未污染）**条件下；
  - **血虫 "blood worms"（实为昆虫幼虫，即摇蚊科 Chironomidae 幼虫）、颤蚓 tubifex worms** —— 能在**极低氧**、其他无脊椎动物全部缺席的环境中大量繁盛。

> **为什么用生物而不是只测化学？**（材料隐含、但必须理解的方法论）化学采样只反映"采样那一瞬间"的水质；而底栖动物**长期生活在底质中**，其群落组成是过去数周至数月环境条件的**积分记录**，能捕捉到间歇性排污事件。这就是环境署同时使用生物指示物与化学分析的原因。

### 2.5 什么是大型无脊椎动物 (macroinvertebrate)

**定义（按网目大小的操作性定义）**：能被 **500 µm 的网或筛 (net or sieve)** 捕获的无脊椎动物区系。
（Part 1 讲义给出的**底栖**版本定义稍宽：**被 200 µm–500 µm 网目截留、且生活史中至少有一部分时间栖息于底部底质 (bottom substrates) 的生物**。两个数字都要记，考试写 "200–500 µm" 更稳。）

包含的类群：
- **节肢动物 (arthropods)**：昆虫 (insects)、螨 (mites)、钩虾/侧游虾 (scuds)、螯虾 (crayfish)
- **软体动物 (molluscs)**：螺 (snails)、笠螺 (limpets)、贻贝 (mussels)、蛤 (clams)
- **环节动物 (annelids)**：分节蠕虫 (segmented worms)
- **线虫动物 (nematodes)**：圆虫 (roundworms)
- **扁形动物 (platyhelminthes)**：扁虫 (flatworms)

### 2.6 什么是"底栖 (benthic)"及其生态功能

**底栖大型无脊椎动物 (benthic macroinvertebrates)** = 栖息于**沉积物之上或之中 (on or in the sediments)** 以及**大型水生植物 (macrophytes)** 上的类群，是淡水群落的**关键组分 (key component)**，也是**连接有机质与营养资源的水生食物网关键环节 (key components of aquatic food webs that link organic matter and nutrient resources)**。

**摄食类型 (feeding modes)**：
- **草食 (herbivorous)**：多数——刮食附着于底质的**单细胞藻类 (unicellular algae)**，较少见地取食大型水生植物 (macrophytes)，或**滤食浮游植物 (filtering phytoplankton)**；
- **碎屑食性 (detritivorous)**：取食死亡有机质 (dead organic matter, detritus)；
- **肉食 (carnivorous)**：捕食其他无脊椎动物、甚至小鱼。

### 2.7 分类学 (Taxonomy)

**定义（Part 2 Summary 原文）**：*the study of naming, identifying & classifying groups of biological organisms based on shared characteristics* —— 基于**共有特征 (shared characteristics)** 对生物类群进行**命名、鉴定与分类**的学科。

**Karl von Linné（林奈，1707–1778）** —— 现代分类学之父 ("father" of modern taxonomy)。

**双名法 (Binomial Nomenclature)**：
- 学名由两个词组成：**第一个词是属 (genus)，第二个词是种 (species)**；
- 书写规范：**斜体**，属名首字母大写，种加词全小写；
- 材料给出的两个例子：*Baetis rhodani*（四节蜉属的一种，蜉蝣目）、*Gammarus pulex*（钩虾，淡水虾/端足目）。

**命名规则的国际法典 (Rules)**：
- **International Code of Botanical Nomenclature (ICBN)** —— 国际植物命名法规；
- **International Commission on Zoological Nomenclature (ICZN)** —— 国际动物命名法委员会。

**二歧检索表 (Dichotomous key)**：鉴定工具，每一步给出**两个互斥的选项**（"有 X / 无 X"），逐步二分直到锁定类群。本周使用的具体检索表是 **Freshwater Name Trail**（配套 ID 图卡 `The freshwater name trail ID Chart pg 2`）。

**本周涉及的分类阶元层级（从材料中出现的所有类群整理）**：

```
门 Phylum        Annelida / Platyhelminthes / Mollusca / Arthropoda
  纲 Class       (Annelida→) Hirudinea, Oligochaeta [亚纲 Subclass]
                 (Mollusca→) Gastropoda
                 (Arthropoda→) Insecta, Crustacea, Arachnida(Acari 螨)
    目 Order     (Insecta→) Plecoptera, Ephemeroptera, Trichoptera,
                            Odonata, Coleoptera, Diptera
                 (Crustacea→) Amphipoda, Isopoda, Decapoda
      科 Family  Baetidae, Heptageniidae, Gammaridae, Tipulidae,
                 Tabanidae, Simuliidae, Chironomidae, Planariidae,
                 Rhyacophilidae, Hydropsychidae
        属 Genus / 种 Species   Baetis rhodani, Gammarus pulex
```

### 2.8 BMWP 与 ASPT：两个指数的理论基础

**BMWP = Biological Monitoring Working Party score（生物监测工作组分值）**
- 欧洲常用，亚洲等地已提出其改编版本 (adaptations)；
- 基于类群对**有机污染 (organic pollution)** 的**敏感性 (sensitivity)**——这里"有机污染"具体指**营养富集 (nutrient enrichment)**，因为它会影响**溶解氧的可获得性**；
- 给每个水生生物**科 (family)** 一个 **1–10** 的分值：
  - **高分 (7–10)** = 对污染**敏感 (sensitive)**，出现即指示**良好条件**；
  - **低分 (1–3)** = 对污染**耐受 (tolerant)**，出现指示**高度污染条件**。
- **关键计分规则**：**不计个体数量 (do not take into account the number of individuals)**——同一"类型"无论抓到 1 只还是 8 只，都只计一次分。分值统计的是**类群丰富度加权的敏感性**，不是丰度。

**简化版 BMWP（本周课堂使用）**：
完整 BMWP 需鉴定到**科 (family)** 级别，"非常耗时、需要相当多的专业知识"，因此本课**只鉴定到大类群 (major groups only)**，并使用一张简化的分值表（见第三节 Table 2）。

**ASPT = Average Score Per Taxon（每分类单元平均分值）**
- 定义：所有找到的大型无脊椎动物**科的耐受分值的平均数**，取值范围 **0–10**；
- 计算：**ASPT = 总 BMWP 分 ÷ 分类单元 (taxa) 数**；
- 与 BMWP 的**根本区别**：**ASPT 不依赖于科的丰富度 (does not depend on the family richness)**；
- 因此 ASPT **与样本量无关 (independent of sample size，因为它是平均数)**，且**受季节变化影响更小 (less influenced by seasonal variations)**，提供了一个**额外的、更一致的指数 (a more consistent index)**。

> **理解要点**：BMWP 会因为"多采了 10 分钟、多翻了几块石头"而升高（找到更多科）；ASPT 不会。所以**两者要一起报告**：BMWP 反映"群落有多丰富且敏感"，ASPT 反映"群落的平均敏感度有多高"。若 BMWP 低但 ASPT 高 → 可能是样本量不足或生境单一，而非污染；若 BMWP 高但 ASPT 低 → 类群很多但都是耐污类群，典型的中度有机富集。

### 2.9 结果的方向性解释

材料原文：*"A higher score for the Type/Taxa means it is the more sensitive to pollution. So if your final score is high then it indicates that the river is less impacted by pollution."*

→ **分值越高 = 类群越敏感 = 最终总分越高 = 河流受污染影响越小 = 健康状况越好。**

---

## 三、公式与图表

### 3.1 计算公式

| 指标 | 公式 | 说明 |
| --- | --- | --- |
| 单类群得分 | `Score = (a) × (b)` | (a) = 该类群的每类型分值 (score per type/taxa)；(b) = 该类群下**不同类型的数目 (number of different types)** |
| **总 BMWP** | `BMWP = Σ [ (a)ᵢ × (b)ᵢ ]` | 对记录表中所有类群求和 |
| **ASPT** | `ASPT = 总 BMWP 分 ÷ taxa 数目` | 材料原文："total BMWP score divide by the number of taxa"，范围 0–10 |

**(b) 的含义务必分清**（这是本周最容易搞错的地方）：
- (b) **不是个体数 (number of individuals)**；
- (b) 是该类群中**不同"类型"的数目**。材料举例："如果我们找到三种不同类型的蜉蝣（每种各 10 分），它们得 3 × 10 = 30 分"。
- 反例（材料原文）："若你找到 1 只 A 型石蝇，得 10 分——和 8 只 A 型石蝇得分相同。"

**材料给出的完整示例**：
| 记录 | 分值 |
| --- | --- |
| 2 types of cased caddisflies（2 类有巢石蛾） | 7 |
| 1 type of freshwater shrimp（1 类淡水虾） | 6 |
| 3 types of leech（3 类水蛭） | 3 |

> ⚠ **注意这个示例的写法**：材料在示例中直接把"分值"写成了该类群的**单位分值**（7、6、3），而没有乘以类型数（否则应为 14、6、9）。这与它自己前面"3 种蜉蝣 = 3 × 10 = 30"的说法**存在表述不一致**。**做题时以"(a) × (b)"的规则为准**，同时留意本周课堂练习明确注明"不同类型未计入本题"，即所有 (b) 一律按 1 处理。

### 3.2 Table 2：河流记录表 — 底栖无脊椎动物（简化 BMWP 分值表）

> 数据来源（材料标注）：图片取自 IOWATER advanced benthic key（Iowa State University）；分值来源 https://oart.org.uk/our-work/projects/water-quality/biological-monitoring

**这是本周必须背下来的核心表格。**

| 类群 (Name) | 拉丁/分类阶元 | 中文 | 每类型分值 (a) | 敏感性 |
| --- | --- | --- | --- | --- |
| Stonefly | Plecoptera | 石蝇（襀翅目） | **10** | 极敏感 |
| Mayfly（**Baetidae 除外 = 4**）& Damselflies | Ephemeroptera & Odonata | 蜉蝣（蜉蝣目）与豆娘（蜻蜓目） | **10** | 极敏感 |
| Cased Caddisfly | Trichoptera | 有巢石蛾（毛翅目） | **7** | 敏感 |
| Freshwater Shrimp | Amphipoda | 淡水虾/钩虾（端足目） | **6** | 中等偏敏感 |
| Caseless Caddisfly | Trichoptera | 无巢石蛾（毛翅目） | **5** | 中等 |
| Flat Worm | Planariidae | 扁虫（涡虫科） | **5** | 中等 |
| Water mite | Acari | 水螨（蜱螨） | **5** | 中等 |
| Beetle larva | Coleoptera | 甲虫幼虫（鞘翅目） | **5** | 中等 |
| Crane Fly & Horse Fly larva | Tipulidae & Tabanidae | 大蚊与虻幼虫 | **5** | 中等 |
| Black fly larva | Simuliidae | 蚋幼虫（蚋科） | **3** | 耐污 |
| Leech | Hirudinae | 水蛭（蛭亚纲） | **3** | 耐污 |
| Snail | Gastropoda | 螺（腹足纲） | **3** | 耐污 |
| — | — | **合计** | **Total BMWP / ASPT** | = 各行得分相加 |

记录表原始列结构（填表时按此填）：

| Name | Figures of organism | Score per type/Taxa (a) | Number of different types (b) | Score |
| --- | --- | --- | --- | --- |
| （类群名） | （图示，用于比对形态） | （查表得，固定值） | （你数出的不同类型数） | (a) × (b) |
| … | | | | |
| Total BMWP scores / ASPT | | | | = add up the scores |

**Table 2 之外、只在 Part 2 讲义中出现的分值**（记录表未列，但讲义明确给出）：

| 类群 | 分值 |
| --- | --- |
| Oligochaeta（寡毛纲蠕虫） | **1**（最耐污） |
| Diptera（双翅目，含 Chironomidae、Simuliidae） | **3** |
| Water louse / Isopoda（水虱，等足目） | **3** |

> ⚠ **材料内部冲突（必须知道）**：**无巢石蛾 (caseless caddisfly)** 在**实践表 Table 2 中为 5 分**，但在 **Part 2 讲义幻灯片中写"Pollution score = 7"**（与有巢石蛾同分）。做本周课堂练习时**以实践表 Table 2 的 5 分为准**（因为练习明确说 "refer to worksheet / table 1"）。若考试出现此项，可注明两版差异。

### 3.3 Table 1：BMWP 总分 → 河流健康等级

**⚠ 材料状态说明**：实践表中 "TABLE 1: Simplified BMWP score for activity" 在 .md 转换后**只保留了标题与出处链接，表格内容为图片未被转成文字**。因此**分级阈值不在本周文本材料中**。练习答案要求从 **very poor / poor / fair / good / very good** 五档中选择——这五个档名是材料明确给出的。

**参考（来自 BMWP 通行标准，非本周材料原文，复习时请以课堂发下的 Table 1 图片为准）**：

| 总 BMWP 分 | 等级 | 生物学含义 |
| --- | --- | --- |
| > 100 | Very good | 未污染、生境多样、敏感类群齐全 |
| 51 – 100 | Good | 轻度污染 |
| 31 – 50 | Fair / Moderate | 中度污染 |
| 16 – 30 | Poor | 污染较重 |
| 0 – 15 | Very poor | 严重污染，仅耐污类群存活 |

| ASPT | 大致解读 |
| --- | --- |
| > 6 | 清洁/未污染，群落以敏感类群为主 |
| 5 – 6 | 中等 |
| 4 – 5 | 差 |
| < 4 | 很差，群落被耐污类群主导 |

### 3.4 类群鉴定对照总表（本周核心查阅表）

**门级第一层分流：**

| 门 Phylum | 一眼判别的决定性特征 |
| --- | --- |
| **Annelida** 环节动物 | 身体**分节 (segmented)**，无附肢关节，蠕虫状 |
| **Platyhelminthes** 扁形动物 | **不分节 (un-segmented)**、扁平、软体、滑行运动 |
| **Mollusca** 软体动物 | 有**硬壳 (hard shell)** 覆盖身体 |
| **Arthropoda** 节肢动物 | **外骨骼 (exoskeleton, chitin)** + 分节身体 + **分节的附肢**；身体明确分为**头 head / 胸 thorax / 腹 abdomen** |

**逐类群鉴定要点表：**

| 类群 | 分类位置 | **关键鉴定特征 (ID features)** | 运动方式 | 分值 |
| --- | --- | --- | --- | --- |
| **水蛭 Leech** | Annelida → Subclass **Hirudinea** | 两端各有**吸盘 (suckers at each end)**；**前端较窄、后端较宽**，后端有小吸盘；**背侧 (dorsal) 前端有眼——可见为暗色斑点** | **伸缩身体 (stretching out the body)** 而移动 | **3** |
| **寡毛类蠕虫 Worms (Oligochaeta)** | Annelida → Subclass **Oligochaeta** | **分节清晰 (clear segmentation)**，多节；鉴定**主要依据刚毛 (chaetae)**——由**几丁质 (chitin)** 构成的硬鬃毛/毛发状纤维，单尖或多尖，出现在**大部分体节**上，**需高倍显微镜才能看到**；**前端 (anterior) 比后端 (posterior) 粗**；最前方有一个圆形（有时呈吻状 proboscis-like）的**口前叶 (prostomium)**；**环带 (clitellum)** 是性器官所在的膨大区，若存在则**总位于身体靠前部**；体节自前向后编号 | 蠕动 | **1** |
| **扁虫 Flatworm** | Platyhelminthes → **Tricladida**（Planariidae） | **不分节**；**无明显的头但有眼 (no obvious head but eyes present)**；常为**黑色或灰色**；**扁平——因为缺少充液的体腔 (lack a fluid-filled body cavity)**；**两侧对称 (bilaterally symmetrical)**；软体 | **独特的滑行运动 (distinct gliding movement)** | **5** |
| **螺与笠螺 Snails & limpets** | Mollusca → **Gastropoda** | **硬壳覆盖身体**；壳可为**尖锥形、扁平或螺旋形 (pointed, flat or coiled)**；**ID features: 壳形与壳口形状 (shell and aperture shape)** | 借助"腹足"移动（材料原文写 "moves with the aid of stomach"，即腹足纲 gastro-poda 字面义"胃-足"） | **3** |
| **石蝇 Stonefly** | Insecta → **Plecoptera**（希腊 *pleco* = 折叠, *ptera* = 翅） | **腹节上无鳃 (no gills on abdominal segments)**；有**翅芽 (wing pads)**；**两条尾丝**（与蜉蝣三条对比）；稚虫 (nymph) 形态多样 | **一般靠爬行 (crawling)** | **10** |
| **蜉蝣 Mayfly** | Insecta → **Ephemeroptera**（希腊 *ephemeros* = 短命） | **三条尾丝 (three filaments)**；腹部有**鳃 (anal gills / 腹部鳃)** | **短促的猛冲式游动 (swims in short darting movements)** | **10**（**Baetidae 科例外 = 4**） |
| **豆娘 Damselfly** | Insecta → **Odonata** | 与蜉蝣同列一行计分 | — | **10** |
| **有巢石蛾 Cased caddisfly** | Insecta → **Trichoptera**（拉丁 *tricho* = 多毛） | **身体藏在巢筒 (case) 内**，昆虫在巢中不受干扰；**巢由石子、沙粒或植物材料 (stones, sand grains, or plant material) 构成**；**找"会爬的小树枝" (look for sticks that crawl)** | 爬行 | **7** |
| **无巢石蛾 Caseless caddisfly** | Insecta → **Trichoptera**（如 Rhyacophilidae 自由生活石蛾、Hydropsychidae 结网石蛾/Sedgeflies） | **身体在巢外**；**外形像一条细毛虫 (thin caterpillar)**；**前部有 3 对足**；**身体末端有钩 (hooks at the end of body)** | **爬行而非游泳 (crawls rather than swim)** | **5**（Table 2）／讲义写 7 |
| **蚋幼虫 Blackfly larva** | Insecta → Diptera → **Simuliidae** | 双翅目共性：**固定的头壳 (fixed head capsule)**；有**伪足 (prolegs)** | — | **3** |
| **摇蚊幼虫（非咬人摇蚊）Non-biting midge larva** | Insecta → Diptera → **Chironomidae** | 即俗称的 **blood worm 血虫**（活体时可为红色）；极耐低氧 | 蠕动式扭动 | **3** |
| **双翅目通性 Diptera（true flies）** | Insecta → **Diptera**（*Di* = 2，*ptera* = 翅，按翅数命名） | **体节数远少于 Oligochaeta**；**头部无眼 (head has no eyes)**；可为**红、绿、褐或透明**，**活体时可能是红色**；**头与胸部分离 (head separated from the thorax)**；栖于水生、腐烂有机质底质中；口器**穿刺吸食 (pierces and sucks)** | **扭动式 (wriggling movement)** | **3** |
| **淡水虾/钩虾 Water shrimp** | Crustacea → **Amphipoda**（如 *Gammarus pulex*, Gammaridae） | **身体弯曲 (curved) 且侧扁 (flattened)**；可能略呈**半透明**；甲壳类共性：**2 对触角** | **侧躺着快速游动 (swims quickly on their sides)** | **6** |
| **水虱 Water louse** | Crustacea → **Isopoda** | **身体扁平 (flattened，背腹扁)**；**2 对触角** | **爬行 (crawling)** | **3** |
| **螯虾 Crayfish** | Crustacea → **Decapoda** | 甲壳类，十足 | — | （表中未列） |
| **水螨 Water mite** | Arachnida → **Acari** | 螨类 | — | **5** |
| **甲虫幼虫 Beetle larva** | Insecta → **Coleoptera** | 幼虫形态 | — | **5** |
| **大蚊 / 虻幼虫 Crane fly / Horse fly larva** | Diptera → **Tipulidae / Tabanidae** | — | — | **5** |

**甲壳纲 (Crustacea) 的通用鉴定要点（讲义重复强调两次，即考点）**：
- 以**2 对触角 (2 pairs of antennae)** 为特征——**这是与昆虫 (1 对触角) 的决定性区别**；
- 有些触角是**退化的 (vestigial)**，即被**外部的背甲 (carapace)** 遮住；
- 有些触角**特化为取食器官甚至运动器官**，因而**难以辨认成触角**；
- 触角是**大多数节肢动物都有的感觉器官 (sensory organ)**，**成对着生于头部最前端的体节 (anterior body segment in the head)**；
- 触角通常**再细分为一系列更小的单元（节, segments）**。

**节肢动物身体分区（讲义图注）**：`Head 头 — Thorax 胸 — Abdomen 腹 — Tails (filaments) 尾丝`；另有 **Wing pads 翅芽**、**Anal gills 尾鳃/腹鳃** 两个关键结构名。

### 3.5 解剖显微镜 (Dissecting microscope) 部件对照表

讲义给出编号 1–13 的部件，练习题要求"识别显微镜的编号部位"，**必须背**：

| 编号 | 英文 | 中文 | 功能 |
| --- | --- | --- | --- |
| 1 | Eyepiece in eyepiece tube (eyepiece 10×/23) | 目镜（在目镜筒内，10×/23） | 观察端镜片，放大 10 倍，视场数 23 |
| 2 | Microscope body with installed vertical illuminator | 显微镜镜体（内置垂直照明器） | 主体结构，含垂直光源 |
| 3 | Interface for cameras with connector | 相机接口（带连接器） | 接摄像/拍照设备 |
| 4 | Zoom button to adjust the magnification | 变倍旋钮 | 调节放大倍率 |
| 5 | Handle | 手柄 | 搬运握持 |
| 6 | Stand | 支架/镜座 | 支撑整机 |
| 7 | Focusing drive (knob) | 调焦手轮 | 对标本对焦 |
| 8 | Push-button for switching ON/OFF the illuminators or the additional reflected-light illumination and for adjusting intensity | 照明器/附加**反射光**照明开关与亮度调节按钮 | 开关并调节反射光亮度 |
| 9 | Push-button for switching ON/OFF the transmitted-light illumination and adjusting intensity | **透射光**照明开关与亮度调节按钮 | 开关并调节透射光亮度 |
| 10 | Reflected-light illumination | 反射光照明（落射照明） | 从上方打光，看不透明标本的表面结构 |
| 11 | Lever for adjusting the transmitted-light illuminator – bright field or dark field on the stand | 透射光照明器调节杆——**明场 (bright field) / 暗场 (dark field)** 切换 | 切换背景照明方式 |
| 12 | Insert plate for placing the specimen on the stage | 载物台插板 | 放置标本 |
| 13 | Lens | 物镜 | 成像镜头 |

> **为什么用解剖（体视）显微镜而不是复式显微镜**：底栖无脊椎动物是**有厚度的完整立体标本**，需要**低倍、大工作距离、立体成像**，并且要能从上方打**反射光**看体表结构（刚毛、尾丝、鳃、巢筒材质）。复式显微镜只适合薄片透射观察。**唯一需要高倍的场合**是看寡毛类的**刚毛 (chaetae)**——讲义明确写 "require high magnification microscope to see them"。

---

## 四、课堂补充

本课**无 lecture 与 transcript**（本周材料为两份讲义 PDF 转 md 与一份实践表 docx 转 md，无教学视频转写）。

以下为材料中出现、但不属于主线内容的补充信息，一并记录：

- **示例河流地点**：两份讲义封面均为 **River Aire at Gordale Beck, Yorkshire Dales**（约克郡谷地的艾尔河/Gordale 溪）——典型的英国上游清洁溪流生境。
- **课堂练习的两条河**：London（伦敦）与 Leeds（利兹）的本地英国河流。
- **Part 1 的既定学习产出 (Intended learning outcomes)**（五条，是本周的考纲提要）：
  1. 什么是分类学 (taxonomy)？
  2. 什么是底栖大型无脊椎动物，它们如何被采集？
  3. 识别解剖显微镜的各部件；
  4. 鉴定关键底栖大型无脊椎动物及其特征；
  5. 如何用底栖大型无脊椎动物评估河流？
- **Part 2 的总结 (Summary)**（五条，与上面一一呼应，见第二节各处已展开）。
- **材料中的文献与资源出处**：
  - Li, Zheng & Liu (2010) *Biomonitoring and Bioindicators Used for River Ecosystems: Definitions, Approaches and Trends*, https://doi.org/10.1016/j.proenv.2010.10.164
  - 显微镜图示：http://www.visio-tek.net/public/files/16-VISIO-S.pdf
  - BMWP 分值：https://oart.org.uk/our-work/projects/water-quality/biological-monitoring
  - 底栖检索图：IOWATER advanced benthic key, https://www.nrem.iastate.edu/class/assets/aecl518/Data%20and%20Tools/IOWATER_advanced_benthic_key.pdf
  - 鉴定图卡：**Freshwater Name Trail**（本周附 `The freshwater name trail ID Chart pg 2` 图片）
  - 讲义中出现的示例科：**Heptageniidae**（扁蜉科，蜉蝣目）、**Gammaridae**（钩虾科，端足目）
  - 讲义图注中另外出现的类群（未进入计分表）：**Water bug（水生蝽）**、**Dragonfly（蜻蜓）**——与豆娘同属 Odonata。

---

## 五、Practical 要点

### 5.1 野外采样流程（"你的样品是怎么采到的"）

讲义 Part 1 "How your samples were collected" 一节的完整步骤，**这是本周必须能复述的操作规程**：

**① 选择采样生境 (Sampling habitats)**
在河道中选取三类生境：**riffle（浅滩/急流段）**、**pool（深潭/缓流段）**、**weeds（水草丛）**。
> **为什么要分生境采**：不同类群偏好不同水流与底质——石蝇/蜉蝣多在浅滩的石块间（高流速、高溶氧），水虱/摇蚊多在缓流细颗粒沉积中，端足类多在水草中。只采一种生境会系统性漏掉整类群，把 BMWP 压低，造成"假污染"的结论。

**② 踢网采样 (Kick sampling)**
- 使用 **1 mm 网目的踢网 (1 mm mesh kick-net)**；
- **踢网/扫网 3 分钟 (3-minutes' kicknet/sweep)**——站在网的上游，用脚扰动底质，被冲起的生物随水流进入下游的网中；
- 采样时间必须标准化（3 分钟），否则不同样点不可比。

**③ 转移 (Transfer)**
- 把网中内容物**倒入装了半桶水的桶中 (empty into buckets half-filled with water)**；
- 半桶水的作用：保持生物存活（活体便于按运动方式鉴定，如"滑行""侧游""扭动"），并稀释泥沙便于分拣。

**④ 手工搜寻大石块 (Hand search)**
- **1 分钟手工搜寻大石块 (1-minute hand search of large stones)**；
- **把石块轻轻在桶中刷/搓下来 (rub the stones gently into the bucket)**；
- **为什么需要这一步**：踢网踢不动大石块，而**有巢石蛾、扁蜉 (Heptageniidae)、扁虫、笠螺**等紧贴石面的类群主要就在石块表面，漏掉它们会显著低估高分类群。"轻轻"是关键——用力刷会把软体动物碾碎导致无法鉴定。

**⑤ 分拣与鉴定 (Sort / identification)**
- 从**白色托盘 (white trays)** 中分拣鉴定；
- **为什么用白盘**：白色高对比背景使深色的小型无脊椎动物一目了然，同时便于看清运动方式（滑行 vs 扭动 vs 猛冲）。

**⑥ 记录 (Record)**
- **记录无脊椎动物样品 (record samples of invertebrates)** —— 填入 Table 2 记录表。

### 5.2 实验室鉴定操作流程

1. **上镜前先看整体与运动**：许多类群靠**运动方式**就能定下来（扁虫滑行、双翅目扭动、端足类侧游、水蛭伸缩、蜉蝣猛冲、石蛾/石蝇爬行）。趁生物还活着在白盘里时先记录这一条。
2. **用二歧检索表 (Freshwater Name Trail)**：从最上层的互斥问题开始（有壳 / 无壳；分节 / 不分节；有关节附肢 / 无附肢），逐级二分。**每一步都要在标本上真的看到那个特征再往下走**，不要跳步。
3. **上解剖显微镜看细节**：
   - 打**反射光**（按钮 8/10）看体表结构：尾丝数目、鳃的位置、翅芽、巢筒材料、壳口形状；
   - 需要看轮廓/透明结构时切**透射光**（按钮 9），必要时用杆 11 切**暗场**提高低对比结构的可见度；
   - 用旋钮 4 变倍，旋钮 7 对焦；
   - **看寡毛类的刚毛 (chaetae) 需要更高倍的显微镜**——体视镜可能不够。
4. **按"关键判别对"确认**（详见 5.3 与第六节）。
5. **填表**：把鉴定结果按类群归入 Table 2 的行。

### 5.3 记录表 (Table 2) 的填法 —— 逐列操作

| 列 | 怎么填 | 注意 |
| --- | --- | --- |
| **Name** | 已印好的 12 个类群行 | 找到的生物必须归入这 12 行之一；不在表内的类群（如螯虾）本次简化评分不计 |
| **Figures of organism** | 已印好的图示 | 用于形态比对，是"图形检索"的辅助 |
| **(a) Score per type/Taxa** | 已印好的固定分值 | **不要改**，这是 BMWP 规定值 |
| **(b) Number of different types** | 填你在该类群中辨出的**不同类型数** | **绝不是个体数**！找到 8 只同一型石蝇 → 填 1 |
| **Score** | 填 (a) × (b) | 该类群未出现 → 该行留空 / 填 0，**不计入 taxa 数** |
| **Total BMWP / ASPT** | Total = 各行 Score 之和；ASPT = Total ÷ 有记录的 taxa 数 | 分母只数**实际找到的**类群数 |

### 5.4 课堂练习 (Workshop exercise) 及完整解答

**题目数据**（两条英国本地河流）：

- **London**：10 leeches（水蛭）、15 snails（螺）、2 stoneflies（石蝇）、35 freshwater shrimps（淡水虾）、3 flatworms（扁虫）、25 caseless caddisflies（无巢石蛾）、2 damselflies（豆娘）
- **Leeds**：22 cased caddisfly larvae（有巢石蛾幼虫）、35 mayflies（蜉蝣）、10 leeches（水蛭）、4 snails（螺）、7 stoneflies（石蝇）、17 freshwater shrimps（淡水虾）、3 black fly larvae（蚋幼虫）

**关键提示（题目原文注明）**：*"the different types of organisms for individual taxa have not been included in this question"* —— **各类群的"不同类型数"未给出，因此所有 (b) 一律按 1 计**，题中的数字（10、15、2…）是**个体数，按规则一律不参与计分**。这正是对"不计个体数"规则的直接考查。

**解答 ① London**

| 类群 | 分值 (a) | (b) | Score |
| --- | --- | --- | --- |
| Leech（水蛭） | 3 | 1 | 3 |
| Snail（螺） | 3 | 1 | 3 |
| Stonefly（石蝇） | 10 | 1 | 10 |
| Freshwater shrimp（淡水虾） | 6 | 1 | 6 |
| Flatworm（扁虫） | 5 | 1 | 5 |
| Caseless caddisfly（无巢石蛾） | 5 | 1 | 5 |
| Damselfly（豆娘） | 10 | 1 | 10 |
| **合计** | | **7 taxa** | **BMWP = 42** |

**ASPT = 42 ÷ 7 = 6.0**

**解答 ② Leeds**

| 类群 | 分值 (a) | (b) | Score |
| --- | --- | --- | --- |
| Cased caddisfly（有巢石蛾） | 7 | 1 | 7 |
| Mayfly（蜉蝣） | 10 | 1 | 10 |
| Leech（水蛭） | 3 | 1 | 3 |
| Snail（螺） | 3 | 1 | 3 |
| Stonefly（石蝇） | 10 | 1 | 10 |
| Freshwater shrimp（淡水虾） | 6 | 1 | 6 |
| Black fly larva（蚋幼虫） | 3 | 1 | 3 |
| **合计** | | **7 taxa** | **BMWP = 42** |

**ASPT = 42 ÷ 7 = 6.0**

> （若采用 Part 2 讲义中"无巢石蛾 = 7"的版本，London 变为 **BMWP = 44，ASPT ≈ 6.29**，Leeds 不变。答题时说明所用分值来源即可。）

**问题 2：两地答案有差异吗？**

**没有差异——两地的 BMWP 与 ASPT 完全相同（42 与 6.0），taxa 数也都是 7。** 这正是这道题精心设计的教学点：

- **两地的个体数分布截然不同**（London 有 35 只虾、25 只无巢石蛾占绝对优势；Leeds 有 35 只蜉蝣、22 只有巢石蛾），但因为 **BMWP 不计个体数**，这些差异完全不进入指数。
- **两地的类群组成也不同**：London 有扁虫 (5)、豆娘 (10)、无巢石蛾 (5)；Leeds 有蜉蝣 (10)、有巢石蛾 (7)、蚋幼虫 (3)。但**替换后的分值之和恰好抵消**（London 的 5+10+5 = 20；Leeds 的 10+7+3 = 20）。
- **结论/讨论要点**：BMWP 与 ASPT 都是**粗粒度指数**，会掩盖群落结构上的真实差异。指数相同 **≠** 两条河生态状况完全相同。要区分它们，需要：(i) 鉴定到**科级**做完整 BMWP（如把 Baetidae 从蜉蝣中分出来只得 4 分）；(ii) 记录**不同类型数 (b)**，让丰富度进入计分；(iii) 补充**多样性指数**与**丰度数据**；(iv) 配合**化学分析**。

**问题 3：河流健康等级？**

从五档（very poor / poor / fair / good / very good）中判读。两地 BMWP 均为 **42**，落在通行 BMWP 分级的 **31–50 → Fair / Moderate（中等）** 一档；而 **ASPT = 6.0** 位于"中等偏好"的临界。
→ **两条河都判为 "fair"（中等）**，即受到一定程度的有机污染影响，但仍保留了石蝇、蜉蝣/豆娘等敏感类群，说明并非严重污染。
> **务必以课堂 Table 1 的实际阈值为最终依据**（见 3.3 的材料状态说明）。

### 5.5 结果如何判读（写讨论时的思路）

1. **先看 BMWP 绝对值** → 定大致等级；
2. **再看 ASPT** → 判断这个总分是"靠很多耐污类群堆出来的"还是"靠少数敏感类群撑起来的"：
   - BMWP 高 + ASPT 高 → 健康、生境多样；
   - BMWP 高 + ASPT 低 → 类群多但全是耐污种，典型**中度有机富集**；
   - BMWP 低 + ASPT 高 → 敏感类群在但总类群少，可能是**采样不足/生境单一**，而非污染（这正是 ASPT 独立于 richness 的价值）；
   - BMWP 低 + ASPT 低 → **严重污染**，只剩 Oligochaeta(1)、Chironomidae(3) 之类。
3. **看指示类群的在与不在**：石蝇 + 蜉蝣**同时缺席**是有机污染的强信号；**颤蚓 (tubifex) + 血虫 (blood worms) 大量出现**且其他类群缺席，指示极低氧。
4. **回到污染源假设**：结合 2.2 的来源清单（排污口、CSO、道路径流、农业面源、坝与运河）解释空间格局。
5. **对照监管标准**：WFD 要求"good ecological condition"，把结果放回这一政策框架里表述。

### 5.6 练习题 (Practice Questions) 及答案

**Part 1 练习**：识别显微镜的编号部位 → 见 3.5 表。

**Part 2 练习 1**：识别以下生物的关键部位
- **a. 水虱 (water louse)**：2 对触角、扁平身体、分节的体节与步足；
- **b. 螺 (snail)**：**壳 (shell)**（尖/扁/螺旋）、**壳口 (aperture)**、腹足；
- **c. 水蛭 (leech)**：**前吸盘与后吸盘 (suckers at each end)**、**背侧前端的眼（暗色斑点）**、窄前端 / 宽后端；
- **d. 昆虫 (insect)**：**头 head / 胸 thorax / 腹 abdomen** 三分、**1 对触角**、3 对胸足、**翅芽 (wing pads)**、**尾丝 (filaments/tails)**、**鳃 (gills)**。

**Part 2 练习 2a：水虱 (water louse) 与淡水虾 (freshwater shrimp) 的主要形态差异？**

| 特征 | 水虱 Water louse (Isopoda) | 淡水虾 Freshwater shrimp (Amphipoda) |
| --- | --- | --- |
| 身体形状 | **背腹扁平 (dorso-ventrally flattened)**，像水生的鼠妇 | **左右侧扁 (laterally flattened) 且身体弯曲 (curved)**，呈"C"形 |
| 透明度 | 不透明，灰褐色 | **可能略呈半透明** |
| 运动 | **爬行 (crawling)** | **侧躺着快速游动 (swims quickly on their sides)** |
| 污染分值 | **3**（耐污） | **6**（中等偏敏感） |

**Part 2 练习 2b：蠕虫 (worm, Oligochaeta) 与水蛭 (leech, Hirudinea) 的主要形态差异？**

| 特征 | 寡毛类蠕虫 Worm (Oligochaeta) | 水蛭 Leech (Hirudinea) |
| --- | --- | --- |
| **吸盘 (suckers)** | **无** | **两端各有吸盘**（后端吸盘更大） |
| **刚毛 (chaetae)** | **有**（几丁质硬鬃毛，遍布多数体节；需高倍镜） | **无** |
| 体形 | 前端粗、后端细，粗细渐变不剧烈 | **前端窄、后端宽** |
| 头部结构 | 前端有**口前叶 (prostomium)**，圆形或吻状 | 前端**背侧有眼——可见暗色斑点** |
| **环带 (clitellum)** | 若有则位于身体前部的膨大区，内含性器官 | 无（此语境下不作为鉴定特征） |
| 分节 | **分节清晰**，体节自前向后编号 | 分节，但外部环纹多于真实体节 |
| 运动 | 蠕动 | **伸缩身体前进 (stretching out the body)**，尺蠖式 |
| 污染分值 | **1**（极耐污） | **3**（耐污） |

---

## 六、易错点 / 重点难点

### 6.1 计分规则上的错误（最常丢分处）

1. **把个体数当作 (b) 填进表里** —— 本周最大的坑。练习中"35 freshwater shrimps"只得 **6 分**，不是 35×6=210。规则原文："we do not take into account the number of individuals of the same type — whatever the number, they only score once."
2. **(b) 与 (a) 搞混**：(a) 是查表固定的，(b) 是你数出的**不同类型数**。
3. **ASPT 的分母数错**：分母是**实际找到的 taxa 数**，不是记录表上的 12 行，也不是个体总数。
4. **把 ASPT 当成 BMWP 的替代品**：两者要**同时报告**——BMWP 反映丰富度+敏感性，ASPT 只反映平均敏感性。
5. **误以为 ASPT 受样本量影响**：恰恰相反，ASPT 的全部价值就在于它**独立于样本量与家族丰富度、受季节影响更小**。
6. **忘记 Baetidae 例外**：蜉蝣目一般 10 分，但 **Baetidae 科只有 4 分**（该科对污染的耐受性明显高于其他蜉蝣）。简化评分只到大类群时容易忽略这一条。
7. **忘记简化 BMWP 的局限**：本课只鉴定到**大类群 (major groups)**，完整 BMWP 需鉴定到**科 (family)**。写讨论时要主动承认这一方法学限制。
8. **无巢石蛾分值的材料内部冲突**：Table 2 = 5，Part 2 讲义 = 7。答题时**注明所用来源**。
9. **只报总分不作解释**：分数本身不是结论，必须回到"哪些敏感类群在/不在""可能的污染源是什么""是否满足 WFD 的 good status"。

### 6.2 鉴定时易混淆的类群（重点难点）

| 混淆对 | **决定性区别特征** |
| --- | --- |
| **石蝇 (Plecoptera) vs 蜉蝣 (Ephemeroptera)** | ① **尾丝数**：石蝇 **2 条**，蜉蝣 **3 条 (three filaments)**；② **腹部鳃**：石蝇 **腹节上无鳃 (no gills on abdominal segments)**，蜉蝣**有腹部/尾鳃 (anal gills)**；③ 运动：石蝇**爬行**，蜉蝣**短促猛冲式游动**。（两者分值都是 10，认错不影响总分，但认错会影响"你到底会不会鉴定"的评分。） |
| **蠕虫 (Oligochaeta) vs 水蛭 (Hirudinea)** | 水蛭**两端有吸盘**、前端背侧有**眼点**、**伸缩式**移动；寡毛类**有刚毛 (chaetae)**、有**口前叶 (prostomium)**、可能有**环带 (clitellum)**。分值差别大（1 vs 3），必须分清。 |
| **蠕虫 (Oligochaeta) vs 双翅目幼虫 (Diptera larva)** | 双翅目有**固定的头壳 (fixed head capsule)**、**头与胸分离**、**体节数远少于寡毛类**、**头部无眼**；寡毛类**体节多**、有刚毛。**分值 1 vs 3**，且两者常同处于富有机质的淤泥中，是野外最常见的误判之一。 |
| **扁虫 (Platyhelminthes) vs 水蛭 (Hirudinea)** | 扁虫**不分节、无吸盘、有眼但无明显头部、滑行运动**；水蛭**分节且有吸盘、伸缩式运动**。分值 5 vs 3。 |
| **水虱 (Isopoda) vs 淡水虾 (Amphipoda)** | 水虱**背腹扁平、爬行**；淡水虾**侧扁且弯曲、侧躺游动、半透明**。**分值 3 vs 6，认错会大幅改变结论**，是本周最需要小心的一对。 |
| **甲壳类 (Crustacea) vs 昆虫 (Insecta)** | **触角对数**：甲壳类 **2 对**，昆虫 **1 对**。注意甲壳类的触角可能**退化 (vestigial)、被背甲遮住、或特化为取食/运动器官**而难以识别——必须仔细看头部前端体节。 |
| **有巢石蛾 vs 无巢石蛾 (Trichoptera)** | 有巢者**身体在由石子/沙粒/植物材料构成的巢筒内**，"找会爬的小树枝"；无巢者**身体裸露、像细毛虫、前部 3 对足、体末有钩**。分值 7 vs 5（或 7）。**风险：巢在采样与倾倒过程中可能脱落**，导致把有巢石蛾误判为无巢石蛾——要在托盘中找散落的空巢作为旁证。 |
| **蚋幼虫 (Simuliidae) vs 摇蚊幼虫 (Chironomidae)** | 同属 Diptera，均 3 分。蚋幼虫有**伪足 (prolegs)**、体后端膨大、常固着于石面；摇蚊幼虫细长、**活体常呈红色（"血虫"）**、扭动式运动。分值相同不影响 BMWP，但生态含义不同——血虫大量出现是**极低氧**的强指示。 |
| **豆娘 (Damselfly) vs 蜻蜓 (Dragonfly)**（同属 Odonata） | 讲义图中两者都出现；计分表中只把 **damselflies** 与蜉蝣同列为 10 分。豆娘稚虫尾端有三片**叶状尾鳃**，蜻蜓稚虫尾端无叶状鳃、腹部粗壮。 |

### 6.3 采样与操作上的常见错误

1. **只在一种生境采样**（只踢浅滩或只扫水草）→ 系统性漏掉整类群 → BMWP 被人为压低，得出"假污染"结论。必须覆盖 **riffle / pool / weeds**。
2. **采样时间不标准化**：必须是 **3 分钟踢网 + 1 分钟手搜**。时长不同的样点之间 BMWP 不可比（**这正是 ASPT 更稳健的原因**）。
3. **跳过大石块手搜**：紧贴石面的有巢石蛾、扁蜉、扁虫、笠螺全部漏掉——而这些多是**高分类群**，漏掉后果最严重。
4. **刷石块太用力**：压碎软体动物与柔软虫体，标本无法鉴定。原文强调 "**gently**"。
5. **桶里不放水或水太少**：生物死亡 → 失去"运动方式"这条关键鉴定线索，且软体标本变形。
6. **用深色托盘分拣**：小型深色生物看不见，直接漏检。必须用**白盘**。
7. **网目选错**：踢网用 **1 mm mesh**；大型无脊椎动物的定义网目是 **200–500 µm**。网目过大会漏掉小个体，过小会堵塞并混入大量藻类与碎屑。
8. **鉴定时跳步用检索表**：没在标本上真正看到某个特征就往下走，会一路错到底。二歧检索表的每一步都必须**实证**。
9. **显微镜照明方式选错**：看体表结构（刚毛、鳃、巢筒）要用**反射光**（按钮 8/10）；只开透射光会把标本拍成剪影。
10. **想用体视镜看刚毛**：刚毛 (chaetae) **需要高倍显微镜**，体视镜倍率通常不够——这是寡毛类鉴定的实际瓶颈。
11. **忽略"活体颜色"信息**：摇蚊幼虫**活着时是红色的**，死后/固定后褪色。要在现场记录。
12. **假设指数相同 = 河流相同**：见 5.4 问题 2 的讨论。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| Taxonomy | 分类学 | 基于共有特征对生物进行命名、鉴定与分类的学科 |
| Binomial nomenclature | 双名法 | 学名 = 属名 (genus) + 种加词 (species)，如 *Gammarus pulex* |
| ICBN | 国际植物命名法规 | International Code of Botanical Nomenclature，管植物命名 |
| ICZN | 国际动物命名法委员会 | International Commission on Zoological Nomenclature，管动物命名 |
| Dichotomous key | 二歧检索表 | 每步给两个互斥选项、逐级二分以锁定类群的鉴定工具 |
| Freshwater Name Trail | 淡水物种识别路径图 | 本周使用的具体淡水无脊椎动物二歧检索图卡 |
| Macroinvertebrate | 大型无脊椎动物 | 能被 500 µm 网/筛捕获的无脊椎动物 |
| Benthic macroinvertebrate | 底栖大型无脊椎动物 | 生活史中至少部分时间栖于底部底质、被 200–500 µm 网目截留的类群 |
| Benthic | 底栖的 | 栖息于沉积物之上或之中 |
| Macrophyte | 大型水生植物 | 肉眼可见的水生植物，是底栖动物的栖息基质之一 |
| Detritus | 碎屑（死有机质） | 部分底栖动物以此为食（detritivore 碎屑食性） |
| Phytoplankton | 浮游植物 | 滤食性底栖动物从水中滤取的食物 |
| Bioindicator | 生物指示物 | 其在与不在可指示环境状态的生物 |
| Biomonitoring | 生物监测 | 用生物群落评估环境质量的方法 |
| Dissolved oxygen (DO) | 溶解氧 | 有机污染下降的关键变量，决定哪些类群能存活 |
| Organic pollution | 有机污染 | 主要来自污水、食物废弃物、农场废液，导致耗氧 |
| Nutrient enrichment | 营养富集 | BMWP 所针对的具体污染类型，影响溶解氧的可获得性 |
| Effluent | 废水/排出液 | 工业或农场排出的液体废物 |
| Combined sewer overflow (CSO) | 合流制下水道溢流 | 暴雨时污水与雨水混合溢流入河的非点源污染 |
| Water Framework Directive (WFD) | 水框架指令 | 欧盟法规，要求所有水源达到"良好"生态状态 |
| Environment Agency | 环境署 | 英格兰的河流质量监管机构，用生物指示物 + 化学分析 |
| Ecological status | 生态状态 | 水体生态健康的分级评价结果 |
| BMWP | 生物监测工作组分值 | Biological Monitoring Working Party score，各科按耐污性给 1–10 分再求和 |
| ASPT | 每分类单元平均分值 | Average Score Per Taxon = 总 BMWP ÷ taxa 数，范围 0–10，与样本量无关 |
| Taxon (pl. taxa) | 分类单元 | 计分时的一个"类群"，本课为大类群，完整 BMWP 为科 |
| Family richness | 科丰富度 | 找到的科的数目；BMWP 依赖它，ASPT 不依赖 |
| Kick sampling / kick-net | 踢网采样 / 踢网 | 用脚扰动底质、生物随水流入网的标准采样法（1 mm 网目，3 分钟） |
| Riffle | 浅滩/急流段 | 水浅流急、底质为砾石的河段，高溶氧敏感类群的栖息地 |
| Pool | 深潭/缓流段 | 水深流缓、底质细的河段 |
| Dissecting microscope | 解剖（体视）显微镜 | 低倍立体成像、大工作距离，适合完整立体标本 |
| Bright field / Dark field | 明场 / 暗场 | 透射照明的两种模式，由载物台上的调节杆切换 |
| Reflected-light illumination | 反射光（落射）照明 | 从上方打光，用于观察不透明标本的表面结构 |
| Transmitted-light illumination | 透射光照明 | 从下方打光，用于观察轮廓与半透明结构 |
| Annelida | 环节动物门 | 分节蠕虫，含 Hirudinea 与 Oligochaeta |
| Hirudinea | 蛭亚纲 | 水蛭，两端有吸盘，分值 3 |
| Oligochaeta | 寡毛亚纲 | 有刚毛的分节蠕虫（含 tubifex），分值 1，最耐污 |
| Chaetae | 刚毛 | 几丁质硬鬃毛，寡毛类的关键鉴定特征，需高倍镜观察 |
| Prostomium | 口前叶 | 寡毛类最前端的圆形或吻状叶片 |
| Clitellum | 环带 | 寡毛类身体前部的膨大区，内含性器官 |
| Platyhelminthes | 扁形动物门 | 扁虫，不分节、无体腔 |
| Tricladida / Planariidae | 三肠目 / 涡虫科 | 扁虫的分类位置，分值 5 |
| Mollusca / Gastropoda | 软体动物门 / 腹足纲 | 有硬壳的螺与笠螺，分值 3；鉴定看壳与壳口形状 |
| Aperture | 壳口 | 螺壳的开口，是腹足类鉴定的关键形态 |
| Arthropoda | 节肢动物门 | 有几丁质外骨骼、身体分节、附肢分节；河流中类群最多 |
| Exoskeleton (chitin) | 外骨骼（几丁质） | 节肢动物的体表硬壳 |
| Insecta | 昆虫纲 | 头/胸/腹三分，**1 对触角** |
| Plecoptera | 襀翅目（石蝇） | *pleco*=折叠, *ptera*=翅；2 尾丝、腹节无鳃、爬行；分值 10 |
| Ephemeroptera | 蜉蝣目（蜉蝣） | *ephemeros*=短命；3 尾丝、有腹鳃、猛冲式游动；分值 10（Baetidae=4） |
| Baetidae | 四节蜉科 | 蜉蝣目中的耐污科，分值仅 4（如 *Baetis rhodani*） |
| Heptageniidae | 扁蜉科 | 蜉蝣目的一科，身体扁平、贴附石面 |
| Trichoptera | 毛翅目（石蛾） | 拉丁 *tricho*=多毛；分有巢 (7) 与无巢 (5/7) |
| Rhyacophilidae | 原石蛾科 | 自由生活（无巢）石蛾 |
| Hydropsychidae | 纹石蛾科 | 结网型（Common Netspinner）无巢石蛾，亦称 sedgeflies |
| Odonata | 蜻蜓目 | 含豆娘 (damselfly) 与蜻蜓 (dragonfly)；豆娘计 10 分 |
| Coleoptera | 鞘翅目 | 甲虫；其幼虫计 5 分 |
| Diptera | 双翅目 | *Di*=2 + *ptera*=翅；固定头壳、头胸分离、头无眼、扭动式运动；分值 3 |
| Simuliidae | 蚋科 | 蚋幼虫，有伪足 (prolegs)，分值 3 |
| Chironomidae | 摇蚊科 | 非咬人摇蚊幼虫，即"血虫"，活体呈红色，极耐低氧 |
| Blood worm | 血虫 | Chironomidae 幼虫的俗称（实为昆虫幼虫，非蠕虫），低氧指示种 |
| Tubifex worm | 颤蚓 | 寡毛类，可在极低氧环境繁盛，重污染指示种 |
| Tipulidae | 大蚊科 | Crane fly 幼虫，分值 5 |
| Tabanidae | 虻科 | Horse fly 幼虫，分值 5 |
| Prolegs | 伪足 | 幼虫腹部的非真足附肢，蚋幼虫具此特征 |
| Crustacea | 甲壳纲 | **2 对触角**（与昆虫 1 对区分）；含 Amphipoda、Isopoda、Decapoda |
| Amphipoda | 端足目（淡水虾/钩虾） | 身体弯曲侧扁、半透明、侧躺快速游动；分值 6 |
| Gammaridae / *Gammarus pulex* | 钩虾科 / 淡水钩虾 | 端足目的代表类群与代表种 |
| Isopoda | 等足目（水虱） | 身体背腹扁平、爬行；分值 3 |
| Decapoda | 十足目（螯虾） | Crayfish，甲壳类，本次简化评分表未列 |
| Acari | 蜱螨（水螨） | Water mite，分值 5 |
| Antennae | 触角 | 成对着生于头部前端体节的感觉器官，再分为若干小节 |
| Vestigial | 退化的 | 结构存在但已缩小/被遮蔽（如被 carapace 遮住的触角） |
| Carapace | 背甲 | 覆盖甲壳类头胸部的外壳 |
| Wing pads | 翅芽 | 未成熟昆虫稚虫背部的翅原基 |
| Anal gills | 尾鳃/腹鳃 | 蜉蝣等腹部末端的呼吸结构；石蝇腹节无鳃 |
| Filaments (tails) | 尾丝 | 腹部末端的丝状突起；数目（2 vs 3）是石蝇/蜉蝣的关键区分 |
| Nymph | 稚虫 | 不完全变态昆虫的幼期，石蝇有多种稚虫形态 |
| Bilateral symmetry | 两侧对称 | 扁虫的体制特征 |
| Body cavity (fluid-filled) | 体腔（充液） | 扁虫因缺此结构而呈扁平 |
| Anterior / Posterior | 前端 / 后端 | 寡毛类前端比后端粗，是判别方向的依据 |
| Dorsal | 背侧 | 水蛭的眼位于前端背侧 |
| Mesh (200–500 µm / 1 mm) | 网目 | 定义大型无脊椎动物的操作性标准 / 踢网所用规格 |
