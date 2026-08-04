# EART26001 Energy and Resources — Week 04 学习笔记

> 本周主题：**铂族元素矿床（PGE — Platinum Group Elements）**
> 材料：`Lecture/Week 4/04-PGE.md`（讲义）、`Practical/Week 4/Practical 4 instructions.md`、`Practical/Week 4/Practical 4_calculation.md`（含答案）
> 讲授人：Dr Stefan Schroeder
> ⚠️ **本周无 transcript**（课堂录音转写缺失），第四段内容来源见该段说明。
> ⚠️ 课程大纲（syllabus）把 PGE 列在 Week 5、把 BIF 列在 Week 4，**与实际讲义顺序不符**。以讲义文件名为准：本周就是 PGE。大纲仅作全课背景使用。

---

## 一、本周主题

### 1.1 本周在全课中的位置

EART26001 是**秋季学期的应用汇总课**，全课的骨架是"先讲原理、再逐类矿床点名过一遍"：

```
W01 导论（商品类型、经济与社会背景、勘查评价）
W02 地下环境（温度、压力、流体运移）
W03 流体与作用（成矿流体、热液过程）
─────────────────────────────────────
W04 铂族 PGE       ← 本周，逐类矿床的第一类
W05 金刚石
W06 金
W07 铀
W08 石油
W09 蒸发岩
W10 铁锰
W11 全球趋势
```

**本周是"逐类矿床"部分的第一类**，而且刻意选了一条**岩浆成因（orthomagmatic / magmatic）**的路线。讲义原文明确：PGE 矿床 "essentially associated with igneous intrusions (layered igneous intrusions): **orthomagmatic**"，另加**砂矿（placers）**作次要类型。

这一点非常重要：**W03 讲的是流体与热液作用，本周则几乎完全不用热液**。PGE 的富集发生在**岩浆房内部、硅酸盐熔体仍处于熔融状态时**，靠的是熔体不混溶、结晶分异与重力沉降，而不是含矿热液的溶解—搬运—沉淀。讲义总结页里唯一提到水的一条是 "Later alteration by aqueous phases"（后期水相蚀变），并且它被放在四条机制的**最后一条**，属于修饰性、次要的过程。

所以本周的正确读法是：**把 W03 的热液思维暂时关掉，换上岩浆思维。** 后面几周会依次出现热液成因（如金的造山型矿床）与沉积成因（BIF、蒸发岩、铁锰结核），本周正好是三条主线里"岩浆成因"这一支的样板。

### 1.2 与上游课程的接口

- **EART22201 火成矿物与作用**：岩浆分异（fractional crystallization）、结晶顺序（Bowen 反应系列）、堆晶岩（cumulate）、层状侵入体（layered intrusion）——这是本周**直接的**基础。讲义里 "Crystallization + cumulates"、"Magma mixing"、"Magma chamber processes" 三页基本是把 22201 的内容拿来当工具用。
- **EART26201 地球化学原理**：元素在共存相之间的**分配系数（partition coefficient）**、相容/不相容行为——决定了 PGE 在什么时刻、进入哪一相。PGE 之所以能成矿，本质上就是因为它们对硫化物熔体的分配系数极高。

### 1.3 本周学习目标（讲义原文）

讲义 p.2 明确列出三条：

1. **Describe the uses, physical and chemical properties of platinum group elements (PGE).**（描述 PGE 的用途、物理与化学性质）
2. **Recognize the igneous geological processes forming PGE enrichment in magmatic resource deposits, as exemplified by the Bushveld Complex.**（识别形成 PGE 富集的火成地质作用，以 Bushveld 杂岩体为例）
3. **Recognize the exploration, production methods, and environmental impact of PGEs.**（认识 PGE 的勘查、生产方法与环境影响）

讲义本身分三大块讲：**(1) PGE 性质与应用 → (2) 层状侵入体与 PGE（Bushveld）→ (3) 勘查、生产与环境**。笔记的第二段按这个顺序展开。

---

## 二、核心概念

### 2.1 铂族元素是哪六个？

📎 **背景补充：** 讲义标题页只点了 Rhodium、Osmium、Iridium、Platinum 四个名字（配图的元素标签），并未在正文完整列出六元素。完整的铂族元素（PGE）共六个，按周期表位置分两行：

| 轻铂族（LPGE / IPGE 一支） | 重铂族（HPGE / PPGE 一支） |
|---|---|
| Ru 钌（Ruthenium） | Rh 铑（Rhodium） |
| Os 锇（Osmium） | Pd 钯（Palladium） |
| Ir 铱（Iridium） | Pt 铂（Platinum） |

📎 **背景补充：** 更常用的一种二分是 **IPGE（Ir-group：Os、Ir、Ru）** 与 **PPGE（Pd-group：Rh、Pt、Pd）**。IPGE 熔点更高、更早从熔体中析出（常以合金或 laurite RuS₂ 等形式进入铬铁矿），PPGE 更倾向于跟随硫化物熔体。这解释了为什么不同矿层（reef）的 PGE 配分（Pt/Pd 比值等）会系统性不同。讲义未展开这一点，但它是理解 UG-2 与 Merensky Reef 差异的关键。

### 2.2 物理与化学性质（讲义核心数据）

讲义 p.4 给出的关键性质：

**(a) 极高的熔点与凝聚温度（high melting and condensation temperatures）**
配图标注了三个熔点：**1555 °C、3033 °C、1768 °C**。
📎 **背景补充：** 这三个数分别对应 **Pd（1555 °C）、Os（3033 °C）、Pt（1768 °C）**——Os 是所有铂族中熔点最高的，也是密度最大的元素之一。讲义没有注明哪个数配哪个元素。

高熔点/高凝聚温度带来的**直接地质后果**（讲义原文）：
> **Early condensation from solar nebula and in mantle**
> （从太阳星云中**早期凝聚**，在地幔中也是早期相）

这句话的含义是：太阳系形成时，PGE 是**最早从星云气体中凝聚出来的一批难熔元素（refractory elements）**，因此在陨石（原始物质）中浓度相对高；而在地球分异过程中，它们又强烈跟随铁进入地核。

**(b) 丰度对比（讲义原文，考点）**

| 储库 | PGE 浓度 |
|---|---|
| 陨石（Meteorite） | **400–900 ppb** |
| 地壳（Crustal） | **0.4–0.5 ppb** |

即**地壳比陨石亏损约 1000 倍**。原因就是核幔分异时 PGE 强烈进入地核。

**(c) 亲铁 / 亲硫性（siderophile / chalcophile）**
讲义原文：**"Siderophile: bond with iron and sulfides"**——与铁及硫化物结合。
📎 **背景补充：** 严格说 PGE 同时是强**亲铁元素（siderophile）**和强**亲硫元素（chalcophile）**。讲义把两者合并表述了（"bond with iron **and sulfides**"）。在地壳/岩浆尺度上真正起作用的是**亲硫性**：只要熔体中出现独立的硫化物熔体相，PGE 就会几乎全部跑进去。这是全周成矿机制的物理化学基础。

**(d) 流体中的搬运形式**
讲义原文：**"Solute transport as S and Cl complexes"**——在溶液中以**硫（S）与氯（Cl）络合物**形式搬运。
📎 **背景补充：** 这条是为讲义总结页第四条机制 "Later alteration by aqueous phases" 埋的伏笔：晚期的岩浆水/变质水可以把已经就位的 PGE 局部再溶解、再迁移、再沉淀，从而**改造（upgrade 或稀释）**礁层的品位和 PGE 矿物形态。但它是**改造**过程，不是**主成矿**过程。

**(e) 贵金属属性**
讲义原文：**"Precious metal: resistant to corrosion and oxidation, and stable at high temperatures"**（抗腐蚀、抗氧化、高温稳定）。这三条性质直接决定了它的全部工业用途。

### 2.3 用途（uses）——为什么 PGE 是关键矿产

讲义花了三页讲应用，考试常出"为什么 PGE 是 critical resource"。

**(1) 催化剂（catalyst）——最重要的一类**
讲义用了一个漂亮的历史引子：
> **Davy's safe lamp (1817) included a platinum wire that limited combustion of flammable coal gases: first application of a catalytic reaction**
> （戴维安全灯（1817）中的铂丝抑制了可燃煤气燃烧，这是**催化反应的第一次应用**）

工业催化的三大方向（讲义原文）：
- **Automotive（汽车）**：尾气氧化（oxidation of exhaust gases）——即三元催化器。
- **Petrochemical（石化）**：提高燃料**辛烷值（octane rating）**——即重整催化。
- **Chemical（化工）**：生产**化肥、炸药、硝酸、氰化氢**等。

📎 **背景补充：** 汽车催化器是 PGE 需求的最大单一板块。这也是 PGE 与**能源转型**挂钩的地方——一方面纯电动车不需要三元催化器（利空 Pt/Pd/Rh 需求），另一方面质子交换膜燃料电池与绿氢电解槽大量用 Pt/Ir（利多）。这正对应大纲 ILO 4 "identify their importance in the energy transition"。讲义未展开，但这是本课程反复回到的主题。

**(2) 其他用途（讲义原文）**
- **Jewelry**（珠宝）
- **Electrical**（电接点、导线）
- **Electronics**（硬盘、LCD 显示器）
- **Medical and dental**（医疗与牙科）

**(3) 定性结论（讲义 summary 页）**
> "They are considered **critical resources**."（被视为关键矿产）

### 2.4 矿物学（mineralogy）

讲义 p.8 分两层：

**第一层：PGE 的宿主是普通硫化物（"Associated with sulfides"）**
- **磁黄铁矿 Pyrrhotite　Fe₁₋ₓS**
- **镍黄铁矿 Pentlandite　(Fe,Ni)₉S₈**
- **黄铜矿 Chalcopyrite　CuFeS₂**

📎 **背景补充：** 这三个矿物就是典型的**岩浆硫化物组合（magmatic sulphide assemblage）**——一个基性/超基性岩浆结晶出的不混溶硫化物液滴冷却后，就分解成这三相（Fe-S、Fe-Ni-S、Cu-Fe-S）。看到这三个共生，就要立刻想到"岩浆硫化物矿床"。大量 PGE 以**固溶体（solid solution）**形式藏在这些硫化物晶格里，而不是以独立矿物存在。

**第二层：独立的 PGE 副矿物（accessory PGE minerals, PGM）**

| 矿物 | 化学式 | 备注 |
|---|---|---|
| **Sperrylite** 砷铂矿 | PtAs₂ | 最常见的独立 Pt 矿物 |
| **Laurite** 硫钌矿 | RuS₂ | 常包裹在铬铁矿中 |
| **Erlichmanite** | OsS₂ | 与 laurite 成类质同象系列 |
| **Irarsite** | (Ir,Ru,Rh,Pt)AsS | 硫砷化物 |
| **Braggite** | (Pt,Pd,Ni)S | |
| **Cooperite** 硫铂矿 | PtS | |

**记忆要点**：`-ite` 前的名字记不住没关系，但要能说出**结构规律**——PGM 主要是**硫化物（S）、砷化物（As）、硫砷化物（AsS）**，几乎没有氧化物或硅酸盐。这再次印证 PGE 的**亲硫性**。

### 2.5 储量与产量（reserves & production）

讲义 p.9–10 的数据（**考试爱考南非的绝对主导地位**）：

**PGE 储量 2024（PGE Reserves 2024）**

| 国家 | 储量占比 |
|---|---|
| **South Africa 南非** | **89 %** |
| Russia 俄罗斯 | 8 % |
| Zimbabwe 津巴布韦 | 2 % |
| USA 美国 | 1 % |
| Canada 加拿大 | 0.5 % |

（合计 100.5 %，为各项四舍五入所致，见文末勘误表说明。）

**产量（Mine production 2007–2011，另标注 2023 年数值）**
讲义图上标了四个"2023:"的数字：**7 %、44 %、11 %、67 %**。📎 **背景补充：** 讲义没有说明这四个百分比分别属于哪个国家/哪个元素。从数量级判断，最可能是**Pt 与 Pd 两种元素的产量份额**分别对应南非与俄罗斯：南非约占全球 Pt 产量的 67–70 %、Pd 产量的 ~35–44 %；俄罗斯约占 Pd 产量的 40 %、Pt 产量的 ~10 %。**这属于推测，材料未说明**，考试不要作为确定事实引用。

**关键数字：品位与富集倍数（讲义原文，必背）**
> **Economic ore grade 2.5–10 g/t (ppm), i.e. enrichment < 25,000×**

拆开算给自己看：
- 经济品位下限 2.5 g/t，地壳丰度上限 0.5 ppb → 2.5 ppm / 0.0005 ppm = **5,000 倍**
- 经济品位上限 10 g/t，地壳丰度下限 0.4 ppb → 10 ppm / 0.0004 ppm = **25,000 倍**

所以"< 25,000×"这句是**准确的**（我已复核）。这个"**富集倍数**"概念是全课的通用工具：任何矿床都可以问"相对地壳丰度富集了多少倍"，PGE 属于**需要极高富集倍数**的一类（对比：Fe 只需要 ~5–8 倍，Al 只需要 ~4 倍）。

### 2.6 矿床类型（deposit types）

讲义 p.11 只给两类：

1. **层状火成侵入体（layered igneous intrusions）—— orthomagmatic 正岩浆型**：绝对主体。
2. **砂矿（Placers）**：次要类型。
   📎 **背景补充：** 砂铂矿（Pt placer）是原生 PGE 矿床风化剥蚀后，因为 Pt 密度极高（21.5 g/cm³）且化学惰性，在河流/滨海环境中被机械富集形成的。历史上乌拉尔（俄罗斯）与哥伦比亚 Chocó 的砂铂矿是最早的 Pt 来源（"platina" 一词即来自西班牙语"小银"）。讲义只写了 "Placers" 一个词，未展开。

📎 **背景补充（其他世界级类型，本周材料未讲）：** 除层状侵入体外，另有两类重要的岩浆 PGE 来源：
- **Ni-Cu-PGE 岩浆硫化物矿床（如俄罗斯 Norilsk-Talnakh）**：与大火成岩省（西伯利亚暗色岩）的岩浆通道（conduit）有关，PGE 是 Ni-Cu 的副产品。俄罗斯 8 % 的储量主要来自这里。
- **陨击构造相关（如加拿大 Sudbury）**：Ni-Cu-PGE。
本周讲义只以 Bushveld 为例，**若考试问"其他 PGE 矿床类型"，要能说出 Norilsk 与 Sudbury，但要注意这是补充知识，不是讲义内容**。

### 2.7 Bushveld Complex（布什维尔德杂岩体）

这是本周的**唯一实例**，讲义用了 13 页讲它，必须讲透。

**(1) 地质背景（Introduction）**
讲义原文：
> **Igneous intrusion into Archean–Paleoproterozoic sedimentary cover sequence on Kaapvaal Craton**
> （侵入到 Kaapvaal 克拉通之上的太古宙—古元古代沉积盖层序列中的火成侵入体）

配图给出年代序列：**2.06 / 2.40 / 2.50 / 2.65 / 2.70 / 3.00 Ga**。其中 **2.06 Ga 就是 Bushveld 的侵位年龄**，其余是下伏克拉通基底与沉积盖层的年龄。
📎 **背景补充：** Bushveld 侵入的沉积盖层是 **Transvaal Supergroup**（含 BIF、白云岩、页岩）。这一点在后面的成矿机制里有用——**白云岩与含硫页岩的同化混染**是触发硫饱和的候选机制之一。

**(2) 规模（讲义原文，惊人的数字）**
> **>70,000 km², several hundred km diameter**
> **1 million km³ of magma in 65,000 years**

即：面积 7 万多平方公里、直径数百公里、**100 万立方公里的岩浆在 6.5 万年内就位**。
这两个数字要一起记：**巨量 + 极快**。快速侵位意味着岩浆房长期保持高温、充分对流、可以反复补给（replenishment），这正是形成规则层理与礁层的前提。

**(3) 层序（Stratigraphy）——"Rustenburg Layered Suite（RLS）"**
讲义原文：**"Bushveld mafic and ultramafic rocks (Rustenburg Layered Suite)"**，**"Distinct layering of ultramafic and mafic rocks"**（超基性—基性岩的清晰层理）。

讲义配图（p.17）标出的岩带自下而上（图上文字碎片重组）：

| 位置 | 讲义图上的带名 | 主要岩性（讲义标注） |
|---|---|---|
| 最底 | **Marginal Zone**（边缘带） | — |
| ↑ | **Lower Zone**（下带） | **Harzburgite**（方辉橄榄岩）、**Pyroxenite**（辉石岩） |
| ↑ | **Critical Zone**（关键带 / 临界带） | **Norite**（苏长岩） |
| ↑ | **Middle Zone**（图上标注） | **Gabbro-norite**（辉长苏长岩） |
| 最顶 | **Upper Zone**（上带） | **Apatite diorite**（磷灰石闪长岩） |

讲义另一页（p.20）给出这套层序的**关键化学分界**：
> **Ultramafic cumulates**（下部超基性堆晶岩）
> **Gabbroic cumulates: First feldspar**（上部辉长质堆晶岩：**长石首次出现**）

**"First feldspar"（长石首次出现）是理解整个层序的钥匙**：岩浆冷却时按 Bowen 序列结晶，先出橄榄石、再出辉石（都是超基性堆晶岩），到某个温度斜长石开始结晶，岩石就从超基性变成基性（辉长质）。**Critical Zone 恰好横跨这个转折**，而三个主要 PGE 礁层都在 Critical Zone 的上部——这不是巧合，见 §2.9。

📎 **背景补充（标准 RLS 五分法）：** 教科书通用的 Rustenburg Layered Suite 分带是 **Marginal — Lower — Critical — Main — Upper** 五带，没有 "Middle Zone" 这一名称；讲义图上的 "Middle Zone + Gabbro-norite" 对应的应是标准命名中的 **Main Zone**。Critical Zone 又常再分为 **Lower Critical Zone**（以铬铁岩层 LG、MG 组为主）与 **Upper Critical Zone**（含 UG-1、UG-2 铬铁岩与 Merensky Reef）。考试写标准五分法更稳妥。

### 2.8 矿体层位（Ore body stratigraphy）——三大礁层

讲义 p.21，**本周最需要背的一页**：

> **Main PGE sources:**
> - **Merensky Reef (since 1926)**
> - **UG-2 (main today)**
> - **Platreef**
>
> **Reefs are 0.4–2.5 m thick**
> **Mineralogy: pyroxene, feldspar, chromite, sulfides, PGM (calc-silicates in Platreef)**
> **Grades:**
> - **Merensky: 3–20 g/t PGE**
> - **UG-2: 4–7 g/t PGE**

逐条解读：

- **Merensky Reef**：1926 年起开采（历史上最早的主力）。岩性是**伟晶质辉石岩（pegmatitic pyroxenite）**，上下常各夹一层薄铬铁岩条带（chromitite stringer）。品位范围最宽（3–20 g/t）。
- **UG-2**（Upper Group 2 chromitite，上组第 2 层铬铁岩）：**今天的主力矿层**。本身是一层**铬铁岩（chromitite）**，PGE 品位 4–7 g/t 且更稳定，还能同时回收 **Cr**。
- **Platreef**：只发育在**北翼（northern limb）**，比另两者厚得多、品位更不均匀，特征是含**钙硅酸盐（calc-silicates）**——因为它直接侵位到下伏白云岩/钙质围岩之上，发生了强烈的**围岩同化（assimilation）**并形成矽卡岩化矿物。**Practical 4 的实习区就在北翼**（见第五段）。

**"矿层极薄"这一点必须有直觉**：0.4–2.5 m 厚，却要在几百公里范围内横向连续——这既是它能被大规模开采的原因（层位可预测），也是它开采困难的原因（极窄的采场、深井、大量废石稀释）。

讲义 p.23 还给出 Merensky Reef 的**手标本级剖面**（配图文字）：
> **Chromitite band top（顶部铬铁岩条带）／ Sf（硫化物）／ Pyx（辉石）／ Fsp（长石）**
> 上覆 **Anorthosite**（斜长岩），矿层本身为 **Pegmatitic pyroxenite**（伟晶质辉石岩），比例尺 20 cm。

### 2.9 成矿机制（ore genesis and magmatic processes）——本周的理论核心

讲义按四个环节推进：**部分熔融 → 岩浆房过程 → 结晶与堆晶 → 硫化物饱和 / 岩浆混合**。

**环节 1：部分熔融（Partial melting）**
讲义只有标题页（引 Mungall 2008），无文字。
📎 **背景补充：** 这一步要回答的问题是"**母岩浆里的 PGE 从哪来**"。地幔部分熔融时，若熔融程度**足够高（>20–25 %）**，地幔源区中残留的硫化物相会被**完全熔尽**，其中的 PGE 才会全部释放进硅酸盐熔体。若熔融程度低，硫化物作为残留相留在地幔中，PGE 被扣留，产生的岩浆就是"贫 PGE"的。**这解释了为什么 PGE 矿床几乎总是与高程度部分熔融产生的科马提岩质/苦橄质/大火成岩省岩浆有关，而不与低程度熔融的碱性岩浆有关。** 讲义未写这段文字，但这是理解 "partial melting" 那两页图的必需背景。

**环节 2：岩浆房过程（Magma chamber processes）**
讲义配图（Emeleus 1996）文字碎片，还原出的要素：
> **Plume from magma replenishment**（岩浆补给形成的羽流）
> **Magma injection into crystal mush**（岩浆注入晶粥）
> **Solidifying cumulate**（正在固结的堆晶岩）
> **Slumped / deformed cumulate**（滑塌/变形的堆晶岩）
> **Feeder / conduit**（补给通道）

即一个**开放系统（open-system）岩浆房**：底部有通道持续补给新岩浆，新岩浆以羽流形式上升并注入尚未固结的晶粥层，同时堆晶层会因坡度而滑塌变形。

**环节 3：结晶与堆晶（Crystallization + cumulates）**
讲义给出 **Stokes 定律**（见第三段公式详解）。核心含义：**晶体或液滴在岩浆中的沉降速度**，取决于密度差、粒径平方与岩浆黏度。这解释了为什么密度大的铬铁矿、橄榄石、硫化物液滴会往下沉、堆积成层。

**环节 4：硫化物饱和与清扫（sulfide saturation & scavenging）**
讲义原文（p.30）：
> **Fractional crystallization → cumulate formation and sulfide saturation**
> **PGE adhere to sulfide droplets and clusters**
> （分离结晶 → 堆晶形成与硫饱和；**PGE 附着到硫化物液滴与团簇上**）

**这就是整个成矿的关键一步。** 完整机制链：

1. 硅酸盐岩浆中溶解着少量 S。随着**分离结晶**进行，无水硅酸盐矿物（橄榄石、辉石、斜长石）不吸收 S，残余熔体中 S 浓度不断升高。
2. 当 S 浓度达到**硫化物饱和（sulphide saturation, SCSS — sulphur content at sulphide saturation）**时，熔体中析出一小滴一小滴的**不混溶硫化物熔体（immiscible sulphide melt）**。
3. 因为 PGE 的亲硫性极强，**PGE 从大体积的硅酸盐熔体中被这些小液滴"扫收"进去**（scavenging）。
4. 硫化物液滴密度约 4.5–5 g/cm³，远大于硅酸盐熔体（~2.7 g/cm³），按 Stokes 定律**下沉**并在堆晶层顶部聚集 —— 形成礁层。

**环节 5：岩浆混合（Magma mixing）—— 触发机制**
讲义原文（p.31）：
> **Magma injection forms layering. Magma injection promotes:**
> - **magma mixing and PGE scavenging by sulfide droplets**
> - **interruption of normal crystallization, formation of monomineralic chromite seams**

即：**新岩浆注入**同时做两件事——
(a) 与残余岩浆混合，**打破硫的平衡、触发硫化物饱和**，从而让液滴析出并清扫 PGE；
(b) **打断正常的结晶序列**，使体系落入铬铁矿单独稳定的区域，析出**单矿物铬铁岩层（monomineralic chromite seams）**。

**这一条同时解释了两件事：为什么 PGE 与铬铁岩层空间上共生（UG-2 既是铬铁岩层也是主力 PGE 矿层），以及为什么礁层是"层"而不是"体"——因为它记录的是一次瞬时的岩浆注入事件，在整个岩浆房内几乎同时发生，所以横向连续几百公里。**

📎 **背景补充：** 讲义描述的第二条机制（新注入的高温原始岩浆与残余分异岩浆混合后，落入铬铁矿唯一稳定场）就是经典的 **Irvine (1975) 岩浆混合模型**。另一类常被并列讨论的触发机制是 **围岩硅质同化（silica assimilation）**：同化长英质围岩会抬高熔体的 SiO₂ 活度，降低 S 的溶解度，同样把体系推入铬铁矿场并触发硫饱和。讲义总结页的第三条 "Assimilation of and reaction with (S-rich) country rock"（同化富 S 围岩）走的是另一条路——**直接外源加 S**，把体系一步推到硫饱和。Platreef 之所以含钙硅酸盐，就是这类同化最直观的证据。

**总结页（讲义 p.33，必背）：**
> The Bushveld Complex is the largest layered intrusion in the world, and currently the main source of PGEs.
> Magmatic processes of PGE ore genesis are strongly tied to processes of **partial melting and crystallization** in a magma chamber.
> PGEs bond with iron and sulfide minerals, and **the formation of sulfide melt droplets to scavenge PGEs from melt is a key factor in ore genesis.** This can be achieved by several mechanisms:
> - **Density segregation of sulfides**（硫化物的密度分离）
> - **Magma re-injection and mixing**（岩浆再注入与混合）
> - **Assimilation of and reaction with (S-rich) country rock**（同化并与富硫围岩反应）
> - **Later alteration by aqueous phases**（后期水相蚀变）
>
> Layered intrusions are also important sources of **Cr, Ni and V**.（层状侵入体也是 Cr、Ni、V 的重要来源）

**最后一句别漏**：层状侵入体是**多金属**的——Critical Zone 出 Cr 与 PGE，Upper Zone 的钒磁铁矿层出 **V**，Ni 则跟随镍黄铁矿。Practical 的题干也写着 "exploring for **PGEs and Cr**"。

### 2.10 勘查（Exploration）

讲义给出两种地球物理方法：

**(1) 重力（gravimetry）**
> **Density anomalies**（密度异常）
> 配图：**Modelling / Modelled thickness / Magnetics / Thickness / 3D map of top**

原理：超基性—基性堆晶岩（尤其铬铁岩，ρ ≈ 4.65）**密度远高于围岩沉积岩**，因此产生正重力异常；结合磁法（磁铁矿、铬铁矿有磁性）可以反演出侵入体**顶面的三维形态与厚度**。

**(2) 地震（seismic）**
> **Seismic survey allows recognition of features >25 m in size**
> **'Potholes' constitute significant ore loss (~15 %)**

- 分辨率：可识别 **>25 m** 的构造。
- **Potholes（"坑洞"构造）**：礁层局部向下塌陷/被切割的圆形构造，会造成 **约 15 % 的矿石损失**。
  📎 **背景补充：** pothole 是 Bushveld 礁层特有的构造——礁层在局部塌陷、下切到更低层位，形成碗状凹陷，直径从米级到数百米。对采矿而言这意味着采场层位突然消失、必须重新找矿层，是南非铂矿最主要的生产损失来源之一。讲义只给出 15 % 这个数字，未解释成因。

### 2.11 生产（Production：Mining and Beneficiation）

讲义原文：
> **Underground mining 500–2000 m, increase of open pit**（地下开采 500–2000 m，露天占比在上升）
> **Conditions in deepest mines similar to Witwatersrand**（最深矿井条件类似 Witwatersrand 金矿）
> **Processing via flotation and electric smelters**（浮选 + 电炉熔炼）
> **Concentrate 0.02–0.2 % PGE = 5×10⁵ – 10⁶ crustal values**（精矿品位 0.02–0.2 % PGE）

**选冶流程要点**：
1. **浮选（flotation）**——利用硫化物矿物的疏水性，把含 PGE 的硫化物富集成精矿。讲义单列一页讲 flotation。**注意：这就是为什么"PGE 藏在硫化物里"这件事有经济意义——只要能浮选硫化物，就等于回收了 PGE。**
2. **电炉熔炼（electric smelting）**——把浮选精矿熔炼成含 PGE 的锍（matte），再经转炉、精炼分离出各个 PGE。

**品位跃升的量级感**：原矿 2.5–10 g/t（即 2.5–10 ppm）→ 精矿 0.02–0.2 %（即 200–2000 ppm）。**选矿使品位提高约 100 倍**。（讲义给的"相对地壳富集 5×10⁵–10⁶ 倍"这句在数量级上有小问题，见文末勘误表。）

### 2.12 环境（Environmental aspects）

讲义原文：
> **Main emission sources: cars, smelters, medical facilities**（主要排放源：汽车、冶炼厂、医疗机构）
> **Nanoparticles**（以纳米颗粒形式）
> **Largely inert and low concentrations, but increasing evidence for bioavailability (toxic effects?)**
> （基本惰性、浓度低，但越来越多证据显示具有**生物可利用性**（毒性？））

总结页对应一句：**"Potential environmental impact of PGEs is little studied."**（PGE 的潜在环境影响研究还很不足。）

**答题角度**：三元催化器在使用中会磨损，把 Pt/Pd/Rh 纳米颗粒排到路面与路边土壤，因此城市道路灰尘中的 PGE 浓度可比自然背景高出几个数量级。传统上认为金属态 PGE 惰性无毒，但纳米尺度 + 可能的络合溶解（回忆 §2.2 的"S 和 Cl 络合物"）使得生物可利用性成为开放问题。

---

## 三、公式与图表

**本周有计算题，本段是重心。**

### 3.1 Stokes 定律（讲义唯一明确给出的公式）

讲义 p.29 原文（md 中排版被打乱）：
> **Stoke's Law:** (𝜌1 −𝜌) × 𝑔 × 𝑑² 　𝑉 = 　18 × 𝜇

还原后的正确形式：

$$V = \frac{(\rho_1 - \rho)\, g\, d^2}{18\,\mu}$$

| 符号 | 含义 | 单位 |
|---|---|---|
| $V$ | 颗粒/液滴的**沉降末速度**（settling velocity） | m/s |
| $\rho_1$ | **颗粒（或硫化物液滴）**的密度 | kg/m³ |
| $\rho$ | **周围岩浆（硅酸盐熔体）**的密度 | kg/m³ |
| $g$ | 重力加速度（9.81） | m/s² |
| $d$ | 颗粒**直径** | m |
| $\mu$ | 岩浆的**动力黏度**（dynamic viscosity） | Pa·s |

**四条必须能说出口的推论：**

1. **$\rho_1 > \rho$ → V > 0 → 下沉**；$\rho_1 < \rho$ → 上浮。硫化物液滴（≈4.5–5）和铬铁矿（4.65）都远重于硅酸盐熔体（≈2.7），所以**下沉并在底部聚集**——这就是讲义总结页的 "Density segregation of sulfides"。
2. **$V \propto d^2$**——**粒径的平方**！液滴/晶体只要长大一倍，沉降速度就快四倍。所以硫化物液滴的**聚并（coalescence，讲义说的 "droplets and clusters"）**对成矿至关重要：小液滴聚成团簇后才能有效沉降。
3. **$V \propto 1/\mu$**——岩浆越黏（越长英质、越冷），沉降越慢。基性/超基性岩浆黏度低（~10–100 Pa·s），这也是层状侵入体只出现在基性侵入体中的物理原因之一。
4. **温度的双重作用**：温度高 → 黏度低 → 沉降快；温度低 → 晶粥变稠 → 沉降停止、层理"冻结"。

📎 **背景补充：** Stokes 定律严格只对**层流、球形、稀疏悬浮**成立；实际岩浆房内晶体浓度高、存在对流，沉降会被显著减慢（hindered settling）。考试若问"堆晶层是否一定靠重力沉降形成"，标准答案是"重力沉降 + 原地结晶（in-situ crystallization）两种机制都有贡献"。

### 3.2 分配系数 D（partition coefficient）

📎 **背景补充：整段是补充内容，讲义未给出这个公式，但它是 §2.9 成矿机制的定量表达，且是 EART26201 地球化学原理的直接延伸。**

$$D_{i}^{\text{sul/sil}} = \frac{C_i^{\text{sulphide melt}}}{C_i^{\text{silicate melt}}}$$

即元素 $i$ 在**硫化物熔体**中的浓度与在**硅酸盐熔体**中浓度之比。

**关键量级**（这是理解 PGE 为什么能成矿的唯一原因）：

| 元素 | $D^{\text{sul/sil}}$ 量级 |
|---|---|
| **PGE（Pt、Pd、Ir、Os、Ru、Rh）** | **10⁴ – 10⁵**（部分实验值可达 10⁶） |
| Cu | ~10³ |
| Ni | ~10² – 10³ |
| 不相容元素（如 Zr、REE） | ≈ 0（几乎完全留在硅酸盐熔体） |

**含义**：只要出现哪怕**极少量**的硫化物熔体，PGE 就会几乎全部（>99 %）跑进硫化物相。这就是"**scavenging（清扫）**"这个词的定量含义。

**方向千万别记反**：分子是硫化物、分母是硅酸盐；**D 大 = 元素喜欢硫化物**。

### 3.3 R 因子（R factor）

📎 **背景补充：整段是补充内容，讲义未提 R 因子，但它是理解"为什么礁层能达到 g/t 级品位、而不是更低"的核心概念，也是 PGE 章节的标准考点。（Campbell & Naldrett 1979）**

**定义**：

$$R = \frac{\text{与硫化物熔体发生平衡的硅酸盐熔体质量}}{\text{硫化物熔体质量}} = \frac{M_{\text{silicate}}}{M_{\text{sulphide}}}$$

即"一滴硫化物**扫过了多少倍于自身质量的硅酸盐岩浆**"。

**质量平衡推导**（考试可能要求写出）：设硅酸盐熔体初始浓度 $C_0$，平衡后硫化物中的浓度 $C_{\text{sul}}$，硅酸盐中的浓度 $C_{\text{sil}} = C_{\text{sul}}/D$。质量守恒：

$$C_0 \cdot M_{\text{sil}} = C_{\text{sul}} \cdot M_{\text{sul}} + \frac{C_{\text{sul}}}{D}\cdot M_{\text{sil}}$$

两边同除 $M_{\text{sul}}$，代入 $R = M_{\text{sil}}/M_{\text{sul}}$：

$$\boxed{\;C_{\text{sul}} = C_0 \cdot D \cdot \frac{R+1}{R+D}\;}$$

**三个极限行为（必须能定性说出）：**

| 情形 | 结果 | 物理意义 |
|---|---|---|
| **R ≫ D** | $C_{\text{sul}} \to C_0 \cdot R$ | 硫化物太少、岩浆太多：液滴"扫收"了海量岩浆中的金属，**品位随 R 线性上升**。 |
| **R ≪ D** | $C_{\text{sul}} \to C_0 \cdot D$ | 硫化物太多：金属被稀释到分配平衡上限，**品位封顶在 $C_0 D$**。 |
| **R 中等** | 介于两者之间 | |

**记忆口诀**：**R 越大 → 每一滴硫化物"扫"过的岩浆越多 → 液滴越"干净地"把 PGE 集中起来 → 最终品位越高。**

**为什么这解释了 Bushveld**：Bushveld 礁层的硫化物含量只有 **1–3 wt%**（Practical 题干给的正是 **2 wt% 硫化物**！），而礁层却含 4–7 g/t PGE。用 R 因子算：如果只有 2 % 的硫化物，R ≈ 50 就已经不够；礁层能达到这个品位，说明每滴硫化物实际与**成千上万倍**于自身质量的岩浆发生过平衡——这只有在**巨大的、对流强烈的、反复补给的岩浆房**中才可能实现。**Bushveld 的巨大规模（100 万 km³）与礁层的高品位，因果关系就在这里。**

**反过来看 Norilsk 型矿床**：那里硫化物含量高（可到块状矿石），R 小，所以 PGE 品位低（ppm 以下）但 Ni-Cu 品位高——PGE 只是副产品。**同一个公式解释了两类矿床的差异。**

### 3.4 资源量计算链（Practical 4 Part B 的方法论骨架）

**这条链是本课程反复使用的通用工具，后面石油、铀、蒸发岩各周还会再用。**

```
几何形态  →  体积 V  →  质量 M  →  金属量
(厚度×宽度×延伸)      (× 体密度 ρ)    (× 品位 g/t)
```

**第一步：体积**
$$V = t \times w \times L_{\text{dip}}$$
其中 $t$ = 矿层真厚度，$w$ = 走向宽度，$L_{\text{dip}}$ = **沿倾向的斜长**（不是水平距离！）。

**倾斜矿层的三角关系（本周最容易错的地方）：**

设倾角为 $\delta$，则对同一段矿层：

$$\text{水平距离 } x = L_{\text{dip}} \cos\delta \quad\Longrightarrow\quad \boxed{L_{\text{dip}} = \frac{x}{\cos\delta}}$$
$$\text{垂直深度 } z = L_{\text{dip}} \sin\delta \quad\Longrightarrow\quad \boxed{L_{\text{dip}} = \frac{z}{\sin\delta}}$$
$$z = x\tan\delta$$

**判断用 cos 还是 sin，只看题目给的是"水平距离"还是"垂直深度"：**
- 给**水平距离**（如"从露头往内陆 6790.7 m"）→ **除以 cos δ**
- 给**垂直深度**（如"到地下 1 km TVD"）→ **除以 sin δ**

**第二步：质量**
$$M = V \times \rho_{\text{bulk}}$$
**单位技巧**：**1 g/cm³ = 1 t/m³**。所以体密度直接写成 t/m³，乘 m³ 就得到吨。这是材料里 "3.3 g/cm³ = t/m³" 那个写法的意思。

**体密度由模态组成加权**（材料用的是算术加权）：
$$\rho_{\text{bulk}} = \sum_i \phi_i \rho_i \qquad (\phi_i = \text{体积分数})$$
⚠️ 若给的是**质量分数** $w_i$，正确公式是**调和平均**：
$$\frac{1}{\rho_{\text{bulk}}} = \sum_i \frac{w_i}{\rho_i}$$
（材料在这里有一处内部不一致，见文末勘误表。）

**第三步：金属量**
$$m_{\text{metal}} = M\ [\text{t}] \times G\ [\text{g/t}] = \dots\ \text{g}$$

**第四步：单位换算（考试常设陷阱）**

| 换算 | 关系 |
|---|---|
| **g/t = ppm** | 1 g / 1,000,000 g = 1 ppm ✔ 完全等价 |
| **ppm → ppb** | 1 ppm = 1000 ppb |
| **wt% → ppm** | 1 % = 10,000 ppm |
| **金衡盎司 troy ounce (ozt)** | **1 ozt = 31.1035 g**（贵金属报价用这个） |
| 常衡盎司 avoirdupois ounce | 1 oz = 28.3495 g（**贵金属不用这个**） |
| 吨 | 1 t = 10⁶ g |

**⚠️ 铂、金、钯的市场报价一律以金衡盎司（troy ounce）计**，1 ozt = 31.1035 g。材料的答案用了常衡盎司换算系数 0.035274 oz/g，偏高约 9.7 %（见勘误表）。

### 3.5 地温梯度（Practical Q3 用）

$$T(z) = T_{\text{surface}} + G \times z$$

- $T_{\text{surface}}$：地表年平均温度（°C）
- $G$：**地温梯度（geothermal gradient）**，°C/km
- $z$：垂直深度（TVD，True Vertical Depth，**真垂直深度**），km

**注意 TVD 的定义**：井/竖井的**垂直**深度，不是沿斜孔的钻杆长度（MD, measured depth）。本题问的是"竖井（mine shaft）在 1 km TVD 处的温度"，竖井本来就是垂直的，所以直接代入 z = 1 km。

📎 **背景补充：** 大陆平均地温梯度约 **25–30 °C/km**；但**太古宙克拉通（如 Kaapvaal 克拉通，Bushveld 就坐落其上）的岩石圈厚、热流低，梯度显著偏低，常见 9–20 °C/km**。这正是南非能把矿井打到 3–4 km 深还能作业的原因（对比讲义原文 "Conditions in deepest mines similar to Witwatersrand"）。材料给的 Figs. 4–5（Dhansay 2017 的地温梯度图）**在 md 中只剩图题、没有数值**，所以本题的具体答案无法从材料复原——见第五段。

### 3.6 图表的文字化描述（图在 md 中丢失，必须靠文字记住）

**图 A：层状侵入体（Bushveld RLS）柱状剖面 —— 自下而上**

```
┌─────────────────────────────────┐  顶
│ UPPER ZONE 上带                  │  辉长岩、闪长岩、磷灰石闪长岩
│  · 钒磁铁矿层（V 的来源）         │  最分异、最富 Fe-Ti-P
├─────────────────────────────────┤
│ MAIN ZONE 主带（讲义图作 Middle）│  辉长苏长岩 gabbro-norite
│  · 厚度最大、无 PGE 矿层          │  单调、缺乏明显层理
├─────────────────────────────────┤
│ CRITICAL ZONE 关键带 ★★★         │
│  ┌ Merensky Reef（伟晶辉石岩）    │  ← PGE 主力（1926 起）3–20 g/t
│  ├ UG-2 铬铁岩层                 │  ← 今日主力 4–7 g/t，兼产 Cr
│  ├ UG-1 铬铁岩层                 │
│  │  ── "First feldspar" 长石首现 ──  超基性→基性的转折
│  └ MG / LG 铬铁岩组              │  Cr 的主要来源
├─────────────────────────────────┤
│ LOWER ZONE 下带                  │  方辉橄榄岩 harzburgite、辉石岩 pyroxenite
│  · 纯超基性堆晶岩                 │  橄榄石 + 辉石，无斜长石
├─────────────────────────────────┤
│ MARGINAL ZONE 边缘带             │  细粒，代表母岩浆成分（chilled margin）
└─────────────────────────────────┘  底（与 Transvaal 沉积盖层接触）
      ※ Platreef 只见于北翼，位于侵入体底部与钙质围岩接触带
```

**"为什么礁层在 Critical Zone？"—— 这是本周最可能出的论述题，答案有三层：**

1. **化学时机**：Critical Zone 正好横跨"**长石首次结晶（first feldspar）**"这条界线。在此之前的分离结晶把残余熔体中的 S 不断浓缩；到 Critical Zone 上部，残余熔体恰好**逼近硫化物饱和**——即"上膛"状态。
2. **构造时机**：Critical Zone 期间岩浆房处于**频繁补给（replenishment）**阶段。每一次新岩浆注入都能通过**混合**把"上膛"的体系**扣动扳机**，触发硫饱和 + 铬铁矿单独结晶。所以礁层与铬铁岩层**成对出现**。
3. **物理条件**：此时晶粥层已足够厚且岩浆黏度低，密度大的硫化物液滴与铬铁矿能有效沉降并**在堆晶层顶面聚集成薄层**（Stokes 定律）。

**图 B：Merensky Reef 手标本级剖面（讲义 p.23，比例尺 20 cm）—— 自上而下**

```
──────────────  上覆 Anorthosite 斜长岩（浅色，几乎纯斜长石）
▓▓▓▓▓▓▓▓▓▓▓▓  上部 Chromitite stringer 铬铁岩细条带（数 mm–cm，黑色）
░░░░░░░░░░░░  Pegmatitic pyroxenite 伟晶质辉石岩  ← 矿层主体
              内含：Pyx 辉石 + Fsp 长石 + Sf 硫化物（星散粒状）+ PGM
▓▓▓▓▓▓▓▓▓▓▓▓  下部 Chromitite stringer（讲义图标 "Chromitite band top"）
──────────────  下伏堆晶岩
```

**记忆要点**：Merensky Reef 是"**两条黑色铬铁岩细线夹一层粗粒辉石岩**"，硫化物以**星散（disseminated）**方式分布——不是块状矿石。整个矿层只有 0.4–2.5 m 厚，最高品位常紧贴铬铁岩条带。

**图 C：Practical 剖面几何（Fig. 3 的三角关系）**

```
地表 ────────────────────────────────────────→ 露头
     ╲ 23°
      ╲  ← 斜长 L_dip = 7377.6 m
       ╲
        ╲                       ← 水平距离 x = 6790.7 m
         ╲                         垂直深度 z = 2882.5 m
          ╲  勘查区 SW 边界

另一处标注：447.2 m（垂直）/ 1053.5 m（水平）→ tan δ = 0.4245 → δ = 23°
```

---

## 四、课堂补充

> **⚠️ 本周无 transcript，本段内容来自讲义与实习材料。**
> 本课程 W03、W04、W05 三周缺课堂录音转写。以下不是课堂原话的转写，而是**从讲义的强调方式（重复出现、被列入 learning goals 与 summary 页）以及实习材料透露的评分要点与解题规范**中反推出来的"老师在意什么"。

### 4.1 讲义自己强调了什么（从结构反推）

**(1) 三条 learning goals 与 summary 页高度对应，等于给出了考纲。** 讲义开头的三条学习目标、结尾的 summary 页五条、中间成矿部分的 summary 页五条，重复度极高。**凡是在这三个地方都出现的内容，就是必考内容**：

- PGE 在地壳中**极其稀少**、需要**高富集倍数**才成矿（learning goal 1 + summary 第 1 条）
- PGE 是**贵金属**，用于**催化、电子/电气、医疗、珠宝**，是**关键矿产**（goal 1 + summary 第 2 条）
- **层状火成侵入体 + orthomagmatic 过程**是主要矿床类型（goal 2 + summary 第 3 条 + 成矿 summary 第 1 条）
- **与铁和硫化物相结合 + 硫化物熔滴从母熔体中分离**是富集到矿石品位的关键（summary 第 4 条 + 成矿 summary 第 3 条，**这句话在两个 summary 页里都出现，是全周分量最重的一句**）
- **环境影响研究不足**（goal 3 + summary 第 5 条）

**(2) "四条机制"被单独列成 bullet，几乎肯定是简答题的答案模板。** 成矿 summary 页把实现"硫化物熔滴清扫 PGE"的途径列成四条：密度分离、岩浆再注入与混合、同化富 S 围岩、后期水相蚀变。**答"PGE 如何富集"时，先给主线（硫饱和 → 不混溶硫化物熔滴 → 清扫 PGE → 密度沉降成层），再把这四条作为触发/实现机制展开**，是最稳的结构。

**(3) 讲义反复提醒"层状侵入体不只出 PGE"。** 成矿 summary 最后一句单列 "Layered intrusions are also important sources of **Cr, Ni and V**"，Practical 题干也写 "exploring for PGEs **and Cr**"。这类"顺带一句"往往就是判断题/选择题的来源。

**(4) 数字被加粗单列的，都要背。** 讲义里以下数字是单独成行、加粗的：**陨石 400–900 ppb / 地壳 0.4–0.5 ppb**、**经济品位 2.5–10 g/t，富集 <25,000×**、**礁层厚 0.4–2.5 m**、**Merensky 3–20 g/t、UG-2 4–7 g/t**、**南非储量 89 %**、**>70,000 km²、100 万 km³/6.5 万年**、**地下开采 500–2000 m**、**地震分辨率 >25 m、pothole 损失 ~15 %**、**精矿 0.02–0.2 % PGE**。

### 4.2 实习材料透露的评分要点与解题规范

**(1) 老师明确说了"数学很简单，难的是设定"。** Practical Part B 开篇原文：
> "This calculation illustrates the **basic simplicity of maths** used in reserve/resource calculations."

**这句话是提示：考试不会考复杂数学，会考你能不能把地质图/剖面图翻译成正确的几何量。** 失分点几乎全在"用了水平距离而不是斜长"、"倾角三角函数用反"、"单位没换"这些地方，而不在算术。

**(2) 老师明确说了"这个算法忽略了什么"。** 原文：
> "Note that a number of uncertainties such as **ore losses** are not considered here. Full evaluations would also take a **statistical approach**."

**这句话本身就是简答题**：问"这个资源量估算有哪些局限"，答案至少包括——
- **未考虑矿石损失（ore losses）**：如讲义提到的 pothole 造成约 15 % 损失，还有采矿回收率、贫化（dilution）。
- **未做统计处理**：真实评估要用地质统计（克里金）从有限钻孔外推品位，并给出置信区间；本题只是取一个钻孔品位（4 g/t）就外推到 32 million m³ 的整个矿体，**这是极强的假设**。
- **几何过度简化**：题干自己承认 "Although in reality the rocks are **folded**, for this exercise consider the TBM as a **simple sheet**"（实际岩层是褶皱的，本题当作简单板状体）。
- **未区分 Resource 与 Reserve**：📎 背景补充——算出来的是**资源量（resource）**，只有在证明技术与经济上可采之后才能称**储量（reserve）**（JORC / NI 43-101 标准）。Q2 问经济性，正是走这一步。

**(3) 老师要求"自己去查数据"。** 材料里两处明确让学生外部查数：
> "Need to determine bulk density of reef (**find information via mindat.org**)"
> "**check current market prices** for Pt to see if mining is economically viable"

**这说明评分看重"知道去哪里找参数"这项能力**，而不是记住密度数值。答题时应写明数据来源。

**(4) 老师给出了开放题的落点。** Q2 后半问 "What parameters can change around economic viability?"——这是**没有唯一答案的讨论题**，需要系统地列出影响经济性的变量（见第五段 5.4）。

**(5) Part A 的岩相学要求非常具体。** 材料把三个矿物的镜下特征逐条列出（长石、橄榄石、辉石），并明确要求识别 "**fabrics** of the rocks, including **layering and cumulates**"——**不只认矿物，还要认结构（堆晶结构、层理、伟晶结构）**。而且特别提醒 "remember your **first year classes**!"，说明这部分是复习性的、默认你已经会。

---

## 五、Practical 要点

**Practical 4: PGE petrography and volumetrics calculation for a PGE deposit**
分 **Part A（岩相学观察）** 与 **Part B（体积法资源量计算）** 两部分。**Part B 是本周核心，`Practical 4_calculation.md` 带答案。**

### 5.1 Part A：PGE 岩石的岩相学

**任务**：用手标本（HS）与薄片（TS）识别层状侵入体中典型的**含 PGE 超基性—基性岩**的**主要造岩矿物**与**结构（fabrics）**，包括**层理（layering）**与**堆晶结构（cumulates）**。

**三个手标本展示的结构（材料原文）：**
1. **pegmatite fabric**（伟晶结构；材料给出定义："pegmatite = very coarse-grained igneous rock"，即**极粗粒**火成岩）——对应 Merensky Reef 的 pegmatitic pyroxenite。
2. **layered fabric**（层状结构）——对应侵入体的岩浆层理。
3. **massive chromitite**（块状铬铁岩）——对应 UG-2 一类的铬铁岩层。
（材料温馨提示："careful, samples are **heavy**"——正好呼应本周主题：这些岩石密度大，是重力法勘查有效的原因。）

**薄片**展示**矿物学与铬铁矿堆晶（chromite cumulates）**。

**三个矿物的镜下鉴定特征（材料原文，直接可背）：**

| 矿物 | 材料给出的镜下特征 |
|---|---|
| **长石 Feldspar** | 透明矿物；**低级序灰色干涉色**（low order grey interference colors）；**双晶发育**（well developed twinning） |
| **橄榄石 Olivine** | **等粒状**（equigranular）；**高突起**（high relief）；**高级序干涉色**（high order interference colors）；解理发育 |
| **辉石 Pyroxene** | **高突起**；**近 90° 的清晰解理**（distinct near 90° cleavage） |

⚠️ 注意：材料写橄榄石 "well developed **cleavage**"。**橄榄石实际上没有发育的解理，只有贝壳状断口与不规则裂纹**——这一条与标准光性矿物学不符，已列入勘误表。**辉石的近 90° 解理**才是区分辉石与角闪石（约 56°/124°）的经典判据。

**推荐的在线虚拟显微镜（材料给出）：**
- `virtualmicroscope.org/content/troctolite-chromite-layer`（橄长岩—铬铁矿层）
- `virtualmicroscope.org/content/o3 magnetite gabbro`（磁铁矿辉长岩）
- `virtualmicroscope.org/content/merensky-reef-bushveld-complex-elements`（**Merensky Reef 本尊**）

📎 **背景补充（堆晶结构怎么认）：** 堆晶岩（cumulate）的镜下判据是——存在一群**自形—半自形、粒度相近、常有沉积式排列**的早期结晶矿物（**堆晶相 cumulus phase**，如铬铁矿、橄榄石、辉石），它们之间的空隙被**他形、包裹式生长的晶间矿物**（**填隙相 intercumulus phase**，常为斜长石或单斜辉石）充填。当填隙相把多个堆晶颗粒**光性连续地**包起来时，称**嵌晶结构（poikilitic texture）**，是层状侵入体的标志性结构。材料未给出这些术语，但实习要求"识别 cumulates"，必须知道这些判据。

### 5.2 Part B：题目条件（逐条列出）

**地质背景**：Bushveld 杂岩体**北翼（northern limb）**的一个勘查靶区，找 **PGE 与 Cr**。目标层位是 **Tennis Ball Marker（TBM）**（图上用蓝色标出）。数据改编自 **Grobler (2019)**。

**给定条件汇总：**

| 参数 | 数值 | 来源 |
|---|---|---|
| 矿层真厚度 $t$ | **0.8 m** | 题干（"consider the TBM as a simple sheet of rock"） |
| 走向宽度 $w$ | **5488.4 m** | 在图上量取（"measured straight between prospect boundaries"） |
| 倾角 $\delta$ | **23°** | 由剖面 tan δ = 447.2 / 1053.5 得出 |
| 至 SW 边界的水平距离 $x$ | **6790.7 m** | 剖面量取 |
| 品位 $G$ | **3–5 g/t，取 4 g/t** | Fig. 3 钻孔品位范围 |
| 模态组成 | 辉石(透辉石 CaMgSi₂O₆) **70 %**<br>斜长石(钙长石 CaAl₂Si₂O₈) **25 %**<br>硫化物(磁黄铁矿 Fe₁₋ₓS) **2 %**<br>铬铁矿 FeCr₂O₄ **3 %** | 题干（标为 wt%） |
| 各矿物密度（查 mindat.org） | 辉石 3.3 / 斜长石 2.75 / 硫化物 4.62 / 铬铁矿 4.65 g/cm³ | 答案页 |
| Pt 占总 PGE 比例 | **1/3（按重量）** | Q2 题干假设 |
| Pt 提取成本 | **1000 $/oz** | Q2 题干 |

**留意题干的岩性描述**：矿层是 **pegmatitic pyroxenite**（伟晶质辉石岩）+ 含 2 % 硫化物 + 3 % 铬铁矿——**这就是 Merensky Reef 型矿层的标准配方**（对照 §2.8 讲义 p.21 的 "Mineralogy: pyroxene, feldspar, chromite, sulfides, PGM"）。题目和讲义是严丝合缝对上的。

### 5.3 Q1 逐步重建 + 独立复算

**问题：What is the total resource of platinum in this prospect?**（这个勘查靶区的铂总资源量是多少？）

---

**Step 1a — 厚度**：已知 $t = 0.8$ m。

**Step 1b — 走向宽度**：在图上直接量取。材料原文提示可以"分段量取以提高精度，或在勘查区边界之间量直线距离"，取
$$w = 5488.4\ \text{m}$$

**Step 1c — 倾角**：由剖面几何求
$$\tan\delta = \frac{447.2}{1053.5} = 0.42449 \quad\Rightarrow\quad \delta = 23.0^\circ$$
✅ **我的复算**：$\arctan(0.42449) = 23.0007°$ —— **与材料完全吻合**。

**Step 1d — 沿倾向斜长**：已知从露头到勘查区 SW 边界的**水平距离** 6790.7 m，求斜长：
$$L_{\text{dip}} = \frac{x}{\cos\delta} = \frac{6790.7}{\cos 23°} = \frac{6790.7}{0.92050} = 7377.1\ \text{m}$$
材料给出 **7377.6 m**。
✅ **我的复算**：7377.1 m，与材料的 7377.6 m 相差 0.5 m（0.007 %），来自倾角取整（材料实际用的倾角约 23.006°）。**数值吻合。**

⚠️ **但材料的算式写错了**：原文写
> "cos 23 = 6790.7 / x → x = 6790.7 / **sin** 23 = 7377.6 m"

前半句用 cos、后半句却写成 sin。若真用 sin 23°，结果是 **6790.7 / 0.39073 = 17379.5 m**，与它自己给出的 7377.6 m 差了 2.4 倍。**所以 "sin 23" 是笔误，正确的是 cos 23**（已列入勘误表）。

**交叉验证**：图上另标注 **2882.5 m**。用 $z = x\tan\delta = 6790.7 \times 0.42447 = 2882.5$ m ✅，或 $z = L_{\text{dip}}\sin\delta = 7377.6\times 0.39073 = 2882.6$ m ✅ —— **两条路径都给出 2882.5 m，证实 2882.5 m 是勘查区 SW 边界处的垂直深度，也反证了 Step 1d 必须用 cos。**

**Step 1e — 体积**：
$$V = 7377.6 \times 5488.4 \times 0.8 = 3.239\times10^7\ \text{m}^3$$
材料给出 **32,392,846.2 m³ = 32.4 × 10⁶ m³**。
✅ **我的复算**：用 7377.6 得 32,392,976 m³；用未取整的 7377.576 得 32,392,870 m³。材料的 32,392,846.2 落在这个区间内（对应 $L_{\text{dip}} = 7377.576$ m），**吻合，差异纯属显示取整。**

---

**Step 2 — 换算为质量**

体密度按模态加权：
$$\rho = \frac{70\times3.3 + 25\times2.75 + 2\times4.62 + 3\times4.65}{100} = \frac{231 + 68.75 + 9.24 + 13.95}{100} = \frac{322.94}{100} = 3.2294 \approx \mathbf{3.23\ g/cm^3 = 3.23\ t/m^3}$$
✅ **我的复算**：3.2294 → 3.23 ✔ **完全吻合**。
（材料原式写作 "70×3.3 + 25×2.75 + … = 3.23"，**省略了除以 100**，是记法上的简写，不是计算错误。）

⚠️ **方法学问题**：题干把模态组成标为 **wt%（质量分数）**，但答案用的是**算术加权**——算术加权只对**体积分数**成立。若严格按 wt% 处理，应用调和平均：
$$\frac{1}{\rho} = \frac{0.70}{3.3}+\frac{0.25}{2.75}+\frac{0.02}{4.62}+\frac{0.03}{4.65} = 0.31381 \Rightarrow \rho = 3.187\ \text{g/cm}^3$$
差异 1.3 %，对最终答案影响不大，但**逻辑上材料把 wt% 当 vol% 用了**（岩相学里 "modal composition" 通常本来就指体积%，所以真正的错误在于把它标注成 wt%）。已列入勘误表。

矿层质量：
$$M = 32{,}392{,}846.2\ \text{m}^3 \times 3.23\ \text{t/m}^3 = 104{,}628{,}893.2\ \text{t} \approx \mathbf{104.6 \times 10^6\ t}$$
✅ **我的复算**：104,628,893.226 t —— **与材料逐位吻合**。

---

**Step 3 — 资源量**

取 Fig. 3 钻孔品位范围 3–5 g/t 中的 **4 g/t**：
$$m_{\text{PGE}} = 104{,}628{,}893.2\ \text{t} \times 4\ \text{g/t} = 418{,}515{,}572.8\ \text{g} = \mathbf{418.5\ t\ PGE}$$
✅ **我的复算**：418,515,572.9 g = 418.5 t —— **吻合**。

Pt 按 1/3 计：
$$m_{\text{Pt}} = \frac{418{,}515{,}572.8}{3} = \mathbf{139{,}505{,}190.9\ g = 139.5\ t\ Pt}$$

⚠️ **材料这里写的是 "13950519.1 g Pt"，即 13.95 t —— 少了一个数量级（差 10 倍）。**
✅ **我的复算**：418,515,572.8 ÷ 3 = **139,505,190.9 g**。材料印的 13,950,519.1 g 正好是它的 1/10，是**笔误/漏位**。已列入勘误表。

**反证**：材料紧接着写 "= **4.9 million oz**"。
- 用 139,505,190.9 g × 0.035274 oz/g = **4,920,906 oz ≈ 4.9 M oz** ✅ 与材料的最终答案一致；
- 用材料印的 13,950,519.1 g × 0.035274 = 492,091 oz = 0.49 M oz ✗ 与它自己的 4.9 M oz 差 10 倍。

**所以材料的最终答案 4.9 M oz 是对的（在它自己的换算系数下），中间那个克数印错了。**

⚠️ **第二个问题：换算系数用错了盎司。** 材料用 **1 g = 0.035274 oz**，这是**常衡盎司（avoirdupois ounce, 28.3495 g）**。**贵金属市场（包括 Pt）一律使用金衡盎司（troy ounce, 31.1035 g）**，且 Q2 引用的 "1000 $/oz" 显然是金衡盎司报价。用金衡盎司重算：
$$\frac{139{,}505{,}191\ \text{g}}{31.1035\ \text{g/ozt}} = \mathbf{4{,}485{,}196\ ozt \approx 4.49\ \text{M ozt}}$$
**正确答案应为约 4.5 百万金衡盎司，而不是 4.9 百万盎司**（差 9.7 %）。已列入勘误表。

---

**Q1 最终答案（我的推荐写法）**

| 量 | 数值 |
|---|---|
| 矿层体积 | 3.24 × 10⁷ m³ |
| 体密度 | 3.23 t/m³ |
| 矿石量 | **1.046 × 10⁸ t（104.6 Mt）** |
| 品位（取值） | 4 g/t PGE（范围 3–5 g/t） |
| **总 PGE 资源量** | **418.5 t**（范围 314–523 t） |
| **Pt 资源量（1/3）** | **139.5 t ≈ 4.49 M ozt**（材料值 4.9 M oz，用了常衡盎司） |

**敏感性提示**：品位从 3 到 5 g/t，资源量从 313.9 t 到 523.1 t 变化，即**±25 %** —— 这就是为什么材料强调真实评估要用统计方法。

### 5.4 Q2 逐步重建：经济性判断

**问题**：资源量算的是总 PGE；假设按重量 1/3 是 Pt，提取 1 盎司 Pt 的成本是 **1000 $**，查当前 Pt 市场价，判断是否有经济性？哪些参数会改变经济可行性？

**材料未给出答案**（`Practical 4_calculation.md` 的 Solution 部分只算到 Q1 结束），Q2、Q3 与 Homework 都没有解答。以下是解题框架。

**判断逻辑**：
$$\text{单位利润} = P_{\text{market}} - C_{\text{extraction}} = P - 1000\ \$/\text{ozt}$$
$$\text{毛利总额} = (P - 1000)\times 4.49\times10^6\ \text{ozt}$$

- 若 $P > 1000\ \$/ozt$ → 每盎司有正毛利，**潜在可行**；
- 若 $P < 1000\ \$/ozt$ → **不可行**（除非成本下降或有副产品收入）。

📎 **背景补充（价格量级，须自行核实当日价）：** 铂价波动很大——2020 年代前半段大致在 **900–1,100 \$/ozt** 区间震荡，2025 年出现明显上行。**请务必按答题当天的实际报价（LPPM/NYMEX）计算，不要引用笔记里的数字。** 关键的定性结论是：**1000 \$/ozt 的成本线正好落在铂价的历史震荡区间中央，所以这个项目处于"经济性边缘（marginal）"** —— 这本身就是出题人想让你看到的结论：**PGE 项目对价格极度敏感。**

**"哪些参数会改变经济可行性"——系统性答案（按类别组织）：**

| 类别 | 具体参数 | 影响方向 |
|---|---|---|
| **收入侧** | **金属价格**（Pt、Pd、Rh 各不相同，Rh 价格可达 Pt 的数倍） | 直接线性 |
| | **副产品信用**：本矿层含 **3 % 铬铁矿**，还有 Ni、Cu、Co；Cr 与贱金属的销售收入可抵扣成本 | ↑ 大幅改善 |
| | **PGE 配分**：题目假设 Pt 占 1/3，实际 Pt : Pd : Rh 比例决定"篮子价（basket price）" | 可正可负 |
| | **汇率**（南非兰特 ZAR / 美元）——成本以兰特计、收入以美元计 | 兰特贬值 → 成本降低 |
| **资源侧** | **品位**（3 vs 5 g/t，±25 %） | 直接线性 |
| | **矿层厚度**与横向连续性 | 直接线性 |
| | **深度**：本靶区延伸到 **2882 m 垂深**，越深成本越高（见 Q3 的温度问题） | ↑ 深度 → ↑ 成本 |
| **技术侧** | **回收率（recovery）**：浮选与冶炼的实际回收率（PGE 通常 80–90 %） | ↓ 直接扣减 |
| | **矿石损失与贫化**：pothole 损失 ~15 %（讲义数据） | ↓ |
| | **采矿方法**：地下 vs 露天（讲义提到露天占比在上升，成本更低） | 露天 → 成本大降 |
| **外部** | 能源与劳动力成本、资本支出（CAPEX）、折现率、税费与权利金、环境与社区许可、基础设施 | — |
| **资源分类** | 从 **Resource → Reserve** 需要通过可行性研究；只有一小部分资源量能转为可采储量 | ↓ |

### 5.5 Q3 逐步重建：矿井温度

**问题**：计算 1 km TVD 处矿井竖井的预期温度，给出了地温梯度图（Figs. 4, 5，Dhansay 2017）。

$$T(z) = T_{\text{surface}} + G\times z$$

**⚠️ 材料无法给出确定答案**：`Practical 4_calculation.md` 与 instructions 中，Figs. 4–5 在 md 转换后**只剩图题、没有任何数值**，且 Solution 未解答 Q3。**因此本题的具体数字无法从材料复原——材料未说明。**

📎 **背景补充（解题方法与合理量级）：**
1. 在 Fig. 4 上定位 "Prospect"（Bushveld 北翼）的位置。
2. 在 Fig. 5 的地温梯度图上读出该位置对应的 $G$（单位 °C/km）。
3. 取南非内陆年均地表温度 $T_{\text{surface}} \approx 18$–$20$ °C。
4. 代入。

以两个合理的梯度值示范：
- 若 $G = 20$ °C/km：$T = 20 + 20\times1 = \mathbf{40\ °C}$
- 若 $G = 30$ °C/km：$T = 20 + 30\times1 = \mathbf{50\ °C}$

Kaapvaal 克拉通热流低、梯度偏低（常见 9–20 °C/km），但 Bushveld 侵入体本身富含放射性元素的岩体与局部构造会抬高局部梯度，Dhansay (2017) 图中 Bushveld 一带的梯度确实高于克拉通平均。**答题时必须写出读图得到的 G 值、假设的地表温度，以及公式本身**——评分看的是过程，不是巧合对上的数字。

**为什么这题重要（联系讲义）**：讲义写 "Underground mining 500–2000 m" 与 "Conditions in deepest mines similar to Witwatersrand"。**岩温是深部开采的硬约束**：法定的作业湿球温度上限约 27–28 °C，岩温超过 50 °C 就必须大规模制冷通风，这是深井最大的运营成本之一。这一条直接回到 Q2 的"哪些参数影响经济性"。

### 5.6 Homework 逐步重建：只算到 1 km 垂深的资源量

**问题**：What is the total resource down to 1 km vertical depth (typical Bushveld mine depth)?

**材料未给答案。以下是我的完整解答。**

**关键**：这次给的是**垂直深度**，所以用 **sin**（对照 §3.4 的判据）：

$$L_{\text{dip}} = \frac{z}{\sin\delta} = \frac{1000}{\sin 23°} = \frac{1000}{0.39073} = \mathbf{2559.3\ m}$$

$$V = 2559.3 \times 5488.4 \times 0.8 = \mathbf{1.124\times10^7\ m^3}\ (11{,}237{,}190\ \text{m}^3)$$

$$M = 1.124\times10^7 \times 3.23 = \mathbf{3.63\times10^7\ t}\ (36{,}296{,}124\ \text{t})$$

$$m_{\text{PGE}} = 3.63\times10^7\ \text{t}\times 4\ \text{g/t} = 1.452\times10^8\ \text{g} = \mathbf{145.2\ t\ PGE}$$

$$m_{\text{Pt}} = 145.2/3 = \mathbf{48.4\ t\ Pt} = \frac{48{,}394{,}832\ \text{g}}{31.1035} = \mathbf{1.56\ M\ ozt}$$

**结果解读（这才是这道 homework 真正想让你看到的东西）：**

$$\frac{L_{\text{dip}}(1\ \text{km TVD})}{L_{\text{dip}}(\text{全靶区})} = \frac{2559.3}{7377.6} = \mathbf{34.7\ \%}$$

**只有约 35 % 的"资源量"落在 1 km 垂深以内、即典型可开采深度以内。** 另外 65 % 延伸到 1–2.88 km 深，虽然地质上存在，但在当前技术与成本下**未必可采**。

**这正是 Resource（资源量）与 Reserve（储量）区别的教学点**：Q1 算出的 418.5 t PGE 是**地质资源量**；真正能进入现金流模型的，在扣除深度限制后只剩约 145 t，再扣除回收率（~85 %）、pothole 损失（~15 %）、贫化等，还要更少。**答 Q2"哪些参数影响经济性"时，把这个 35 % 的数字拿出来用，是最有力的论证。**

---

## 六、易错点 / 重点难点

### 6.1 概念方向类（最常丢分）

**① 分配系数 D 的方向搞反**
$D^{\text{sul/sil}} = C_{\text{硫化物}} / C_{\text{硅酸盐}}$，**分子是硫化物**。
- PGE 的 D ≈ 10⁴–10⁵，是**极大**的数，意思是"**极其偏爱硫化物相**"。
- 千万不要说成"PGE 的 D 很小所以进硫化物"——那是把 D 写反了。
- 记忆锚点：**D 大 = 分子大 = 硫化物里浓度高 = 元素喜欢硫化物**。

**② R 因子与品位的关系记反**
$$C_{\text{sul}} = C_0 D \frac{R+1}{R+D}$$
**R 越大 → 品位越高。** 直观理解：R = 硅酸盐/硫化物质量比，**R 大意味着"一小滴硫化物扫过了一大片岩浆"**，把广域分散的 PGE 集中到一点。
- ❌ 错误直觉："硫化物多，PGE 就多" —— 硫化物**总量**是多了，但**每单位硫化物的 PGE 浓度（=品位）被稀释了**。
- 这就是为什么 Bushveld 礁层只含 **1–3 % 硫化物却品位很高**，而 Norilsk 的块状硫化物矿石 PGE 品位反而低。
- 一句话：**"少而勤劳的硫化物"比"多而懒惰的硫化物"品位高。**

**③ 把 PGE 矿床当成热液成因**
这是本周最大的概念陷阱，尤其在刚学完 W03 流体与作用之后。
- **PGE 主成矿是岩浆成因（orthomagmatic）**：硫化物熔体不混溶 → 清扫 → 重力沉降。**全程在 1000 °C 以上的熔体中完成，没有水的参与。**
- 水相只在 "**Later** alteration by aqueous phases"（讲义总结第四条）中作为**后期改造**出现，而且是四条里的**最后一条**。
- ⚠️ 但也不要走到另一个极端：**Merensky Reef 中确实有晚期流体改造的证据**（伟晶结构、PGE 矿物的再分布），学术界对"岩浆 vs 流体"的相对贡献仍有争论。**标准答案是"以岩浆过程为主，晚期流体作局部改造"。**

**④ "堆晶层一定是沉降形成的"**
Stokes 定律解释了密度分选，但现代观点认为堆晶层也可以由**原地结晶（in-situ crystallization）**在岩浆房底部形成。别把 Stokes 定律当成唯一机制。

### 6.2 数值与单位类

**⑤ g/t、ppm、ppb、wt% 换算**

| 表述 | 等价 |
|---|---|
| 1 **g/t** | = 1 **ppm** = 1000 **ppb** = 10⁻⁴ % |
| 1 **%** | = 10,000 ppm = 10 g/kg |
| 地壳 PGE **0.4–0.5 ppb** | = 0.0004–0.0005 g/t |
| 矿石 **2.5–10 g/t** | = 2.5–10 ppm |
| 精矿 **0.02–0.2 %** | = 200–2000 ppm |

**练习**：从矿石 (5 g/t) 到精矿 (0.1 % = 1000 ppm) 富集了多少倍？→ 1000/5 = **200 倍**。

**⑥ 金衡盎司 vs 常衡盎司（本周材料就踩了这个坑）**
- **贵金属（Au、Ag、Pt、Pd）报价一律用金衡盎司 troy ounce：1 ozt = 31.1035 g**
- 常衡盎司（食品、普通商品）：1 oz = 28.3495 g
- **两者差 9.7 %** —— 在一个 1.4 亿美元量级的项目上就是上千万美元的差别。
- 换算记忆：**1 kg ≈ 32.15 ozt**；**1 t ≈ 32,151 ozt**。

**⑦ 倾角三角函数用错（Practical 最大失分点）**

| 题目给的是 | 求斜长用 | 为什么 |
|---|---|---|
| **水平距离** x | $L = x / \cos\delta$ | 水平距离是斜长的**邻边** |
| **垂直深度** z | $L = z / \sin\delta$ | 垂直深度是斜长的**对边** |

**画个小三角形永远比背公式可靠。** 而且做完要**用另一个量反算检验**（比如本题用 $z = x\tan\delta$ 反算出 2882.5 m，与图上标注一致，就确认没用错）。

**⑧ 忘记"真厚度"vs"视厚度"**
资源量计算必须用**真厚度（true thickness，垂直于层面量）**。若题目给的是钻孔截穿长度（intersection length），要乘以角度校正。本题直接给了 0.8 m 真厚度，但考试可能不给。

**⑨ 体密度由 wt% 还是 vol% 加权**
- **vol%** → 算术加权 $\rho = \sum \phi_i\rho_i$
- **wt%** → 调和平均 $1/\rho = \sum w_i/\rho_i$
- 岩相学的 "modal composition（模态组成）" **默认是体积 %**。

**⑩ 1 g/cm³ = 1 t/m³**
这个恒等式让"体积(m³) × 密度(t/m³) = 质量(t)"一步到位。不要绕道去换算 kg。

### 6.3 事实记忆类

**⑪ 三大礁层别混**

| | 层位 | 岩性 | 品位 | 地位 |
|---|---|---|---|---|
| **Merensky Reef** | Upper Critical Zone | 伟晶质辉石岩（上下夹铬铁岩条带） | 3–20 g/t | **1926 年起**的历史主力 |
| **UG-2** | Upper Critical Zone（在 Merensky 之下） | **铬铁岩层** | 4–7 g/t | **当今主力**，兼产 Cr |
| **Platreef** | **仅北翼**，侵入体底部 | 含**钙硅酸盐**，厚、不均匀 | 变化大 | 露天开采为主 |

**⑫ 陨石 vs 地壳丰度别记反**：**陨石 400–900 ppb（高）**，**地壳 0.4–0.5 ppb（低）**，相差约 **1000 倍**，原因是核幔分异把亲铁的 PGE 拉进了地核。

**⑬ 富集倍数别算错**：矿石 2.5–10 g/t ÷ 地壳 0.4–0.5 ppb = **5,000 至 25,000 倍**。讲义写 "< 25,000×"。

**⑭ Bushveld 的两个"巨"要一起记**：**面积 >70,000 km²、体积 100 万 km³**，而侵位只用了 **65,000 年**——巨量 + 极快。

**⑮ 别忘了副产品**：层状侵入体还是 **Cr、Ni、V** 的重要来源（V 在 Upper Zone 的钒磁铁矿层）。

**⑯ pothole ≈ 15 % 矿石损失、地震分辨率 > 25 m** —— 这两个数字常出现在"勘查/开采挑战"类题目里。

---

## 七、本周术语表

| 英文 | 中文 | 简要说明 |
|---|---|---|
| Platinum Group Elements (PGE) | 铂族元素 | Ru、Rh、Pd、Os、Ir、Pt 共六个 |
| Platinum Group Minerals (PGM) | 铂族矿物 | PGE 的独立矿物，多为硫化物/砷化物 |
| Siderophile | 亲铁（元素） | 倾向于与金属铁结合，进入地核 |
| Chalcophile | 亲硫（元素） | 倾向于进入硫化物相 |
| Refractory element | 难熔元素 | 高凝聚温度，从星云中早期凝聚 |
| Orthomagmatic | 正岩浆（成因） | 成矿完全在岩浆结晶过程中完成 |
| Layered igneous intrusion | 层状火成侵入体 | 具有规则岩浆层理的基性—超基性侵入体 |
| Bushveld Complex | 布什维尔德杂岩体 | 南非，2.06 Ga，世界最大层状侵入体 |
| Rustenburg Layered Suite (RLS) | 拉斯滕堡层状岩套 | Bushveld 的镁铁质—超镁铁质层状部分 |
| Kaapvaal Craton | 卡普瓦尔克拉通 | Bushveld 所在的太古宙克拉通 |
| Marginal / Lower / Critical / Main / Upper Zone | 边缘带/下带/关键带/主带/上带 | RLS 自下而上的五个岩带 |
| Critical Zone | 关键带（临界带） | 含全部主要 PGE 礁层与铬铁岩层 |
| Reef | 矿层（礁层） | 层状侵入体中薄而横向连续的含 PGE 层，0.4–2.5 m |
| Merensky Reef | 梅伦斯基礁层 | 伟晶质辉石岩，3–20 g/t，1926 年起开采 |
| UG-2 (Upper Group 2 chromitite) | UG-2 铬铁岩层 | 当今主力，4–7 g/t，兼产 Cr |
| Platreef | 普拉特礁层 | 仅见于北翼，含钙硅酸盐，厚而不均 |
| Tennis Ball Marker (TBM) | 网球标志层 | 北翼的一个勘查目标层位（Practical 4） |
| Pothole | 坑洞构造 | 礁层局部塌陷下切，造成约 15 % 矿石损失 |
| Cumulate | 堆晶岩 | 早期结晶矿物聚集形成的火成岩 |
| Cumulus / Intercumulus phase | 堆晶相 / 填隙相 | 早期堆积矿物 / 充填其间的晚期矿物 |
| Poikilitic texture | 嵌晶结构 | 大晶体光性连续地包裹多个小晶体 |
| Pegmatite / pegmatitic | 伟晶岩 / 伟晶（质）的 | 极粗粒的火成岩 |
| Chromitite | 铬铁岩 | 以铬铁矿为主的单矿物岩层 |
| Harzburgite | 方辉橄榄岩 | 橄榄石 + 斜方辉石，超基性 |
| Pyroxenite | 辉石岩 | 以辉石为主的超基性岩 |
| Norite | 苏长岩 | 斜长石 + 斜方辉石 |
| Gabbro-norite | 辉长苏长岩 | 含单斜与斜方辉石的辉长岩 |
| Anorthosite | 斜长岩 | 几乎全部由斜长石组成 |
| Diopside | 透辉石 | CaMgSi₂O₆，密度 3.3 g/cm³ |
| Anorthite | 钙长石 | CaAl₂Si₂O₈，密度 2.75 g/cm³ |
| Chromite | 铬铁矿 | FeCr₂O₄，密度 4.65 g/cm³ |
| Pyrrhotite | 磁黄铁矿 | Fe₁₋ₓS，密度 4.62 g/cm³ |
| Pentlandite | 镍黄铁矿 | (Fe,Ni)₉S₈ |
| Chalcopyrite | 黄铜矿 | CuFeS₂ |
| Sperrylite | 砷铂矿 | PtAs₂，最常见的独立 Pt 矿物 |
| Laurite | 硫钌矿 | RuS₂ |
| Erlichmanite | 硫锇矿 | OsS₂ |
| Irarsite | 硫砷铱矿 | (Ir,Ru,Rh,Pt)AsS |
| Braggite | 硫铂钯镍矿 | (Pt,Pd,Ni)S |
| Cooperite | 硫铂矿 | PtS |
| Partial melting | 部分熔融 | 高熔融程度才能释放地幔硫化物中的 PGE |
| Fractional crystallization | 分离结晶 | 结晶相与熔体分离，驱动残余熔体演化 |
| Sulphide saturation | 硫化物饱和 | 熔体 S 达到溶解度上限，析出硫化物熔体 |
| Immiscible sulphide melt | 不混溶硫化物熔体 | 与硅酸盐熔体不互溶的独立液相 |
| Scavenging | 清扫（捕获） | 硫化物液滴从硅酸盐熔体中收集 PGE |
| Partition coefficient (D) | 分配系数 | D = C_硫化物 / C_硅酸盐；PGE 达 10⁴–10⁵ |
| R factor | R 因子 | 硅酸盐/硫化物质量比；R 越大品位越高 |
| Magma replenishment / re-injection | 岩浆补给 / 再注入 | 新岩浆注入，触发混合与硫饱和 |
| Magma mixing | 岩浆混合 | 触发硫饱和与单矿物铬铁岩层形成 |
| Assimilation | 同化（混染） | 熔化吸收围岩，可外源加 S 或提高 SiO₂ |
| Density segregation | 密度分离 | 重相下沉、轻相上浮的重力分选 |
| Stokes' Law | 斯托克斯定律 | V = (ρ₁−ρ)gd²/(18μ)，沉降速度 |
| Dynamic viscosity (μ) | 动力黏度 | 单位 Pa·s |
| Gravimetry | 重力测量 | 利用密度异常探测侵入体 |
| Flotation | 浮选 | 利用硫化物疏水性富集精矿 |
| Electric smelter | 电炉熔炼 | 精矿熔炼成含 PGE 的锍 |
| Concentrate | 精矿 | 选矿产物，0.02–0.2 % PGE |
| Beneficiation | 选矿（选冶） | 提高品位的物理/化学处理 |
| Ore grade | 矿石品位 | PGE 经济品位 2.5–10 g/t |
| Enrichment factor | 富集倍数 | 品位 / 地壳丰度；PGE 可达 25,000× |
| Resource / Reserve | 资源量 / 储量 | 储量须证明技术与经济可采 |
| Ore loss / Dilution | 矿石损失 / 贫化 | 降低实际可采金属量 |
| TVD (True Vertical Depth) | 真垂直深度 | 与沿孔测量深度 MD 相对 |
| Geothermal gradient | 地温梯度 | °C/km；克拉通区常偏低 |
| Troy ounce (ozt) | 金衡盎司 | 31.1035 g，贵金属报价单位 |
| Placer | 砂矿 | 高密度矿物的机械富集矿床 |
| Critical raw material | 关键原材料 | 供应风险高且经济重要的资源 |
| Bioavailability | 生物可利用性 | PGE 纳米颗粒潜在毒性的关注点 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Practical 4_calculation.md`，Solution 第 1.d 步（沿倾向斜长） | "dip length at this point: **cos 23 = 6790.7 / x → x = 6790.7 / sin 23 = 7377.6 m**" | 同一步内前后不一致：前半句写 cos、后半句改用 sin。若真按 sin 23° 计算，结果是 **17,379.5 m**，与它自己给出的 7377.6 m 相差 2.4 倍。 | 应为 **x = 6790.7 / cos 23° = 7377.1 m**。复算得 7377.1 m，与材料结果 7377.6 m 一致（差 0.007 %，源自倾角取整），**证明公式该用 cos，"sin 23" 是笔误**。交叉验证：图上标注的 2882.5 m = 6790.7 × tan 23° = 7377.6 × sin 23°，恰为该点的垂直深度，进一步确认。 |
| `Practical 4_calculation.md`，Solution 第 3 步（resources） | "418515572.8 g PGE = 418.5 t PGE　1/3 is Pt: **13950519.1 g Pt** = 4.9 million oz" | **少了一个数量级。** 418,515,572.8 ÷ 3 = **139,505,190.9 g**，不是 13,950,519.1 g（后者恰为前者的 1/10）。 | 应为 **139,505,190.9 g Pt = 139.5 t Pt**。反证：材料自己给出的最终答案 "4.9 million oz" 只有用 139,505,190.9 g 才能得到（×0.035274 = 4.92 M oz）；用它印出的 13,950,519.1 g 只得 0.49 M oz。**最终答案 4.9 M oz 无误，中间的克数印错。** |
| `Practical 4_calculation.md`，Solution 第 3 步（单位换算） | "**1 g = 0.035274 oz**" | 用的是**常衡盎司（avoirdupois ounce, 28.3495 g）**。**铂等贵金属的市场报价一律以金衡盎司（troy ounce, 31.1035 g）计**，而 Q2 引用的 "1000 \$/oz" 显然是金衡盎司报价，两者混用会使资源量被高估约 **9.7 %**。 | 应用 **1 ozt = 31.1035 g（1 g = 0.0321507 ozt）**。正确结果：139,505,191 g ÷ 31.1035 = **4,485,196 ozt ≈ 4.49 M ozt**，而非 4.9 M oz。 |
| `Practical 4 instructions.md` / `Practical 4_calculation.md`，Data 段 + Solution 第 2 步 | 题干："70 **wt%** pyroxene / 25 **wt%** plagioclase / 2 **wt%** sulfide / 3 **wt%** chromite"；答案："70×3.3 + 25×2.75 + 2×4.62 + 3×4.65 = 3.23" | **单位与算法不匹配。** 对质量分数求体密度必须用调和平均 1/ρ = Σ(wᵢ/ρᵢ)，算术加权只对**体积分数**成立。按 wt% 严格计算得 **ρ = 3.187 g/cm³**，而非 3.229。 | 岩相学中 "modal composition（模态组成）" 通常本就指**体积 %**，因此更可能是**题干把 vol% 误标为 wt%**，而答案的算术加权本身是对的。两种算法差 1.3 %，对最终资源量影响约 1 %。另外算式省略了"÷100"，属记法简写而非错误。 |
| `04-PGE.md`，"Production — Mining and Beneficiation" 页 | "Concentrate 0.02-0.2% PGE = **5 × 10⁵ - 10⁶** crustal values" | 上限数量级偏低。以讲义自己给出的地壳丰度 0.4 ppb 计：0.02 % = 200 ppm → 200/0.0004 = **5×10⁵**（下限正确）；0.2 % = 2000 ppm → 2000/0.0004 = **5×10⁶**（不是 10⁶）。用 0.5 ppb 计则为 4×10⁵ – 4×10⁶。 | 区间应为约 **5×10⁵ – 5×10⁶ 倍地壳丰度**。（讲义同页的另一处 "ore grade 2.5–10 g/t, enrichment < 25,000×" 经复核**完全正确**。） |
| `Practical 4 instructions.md`，"Typical crystal morphologies" 页，Olivine 条目 | "Olivine: equigranular minerals, high relief, high order interference colors, **well developed cleavage**" | **与标准光性矿物学不符。橄榄石没有发育的解理**，其特征是**贝壳状断口（conchoidal fracture）**与不规则裂纹（常沿裂纹发生蛇纹石化）。"发育良好的解理"是**辉石**（近 90°）与**角闪石**（约 56°/124°）的特征。 | 橄榄石正确描述：高突起、高级序（二级—三级）干涉色、**无解理、贝壳状断口**、常见不规则裂纹与蛇纹石化边。同页对长石与辉石的描述均正确。 |
| `04-PGE.md`，"PGE Reserves 2024" 页 | South Africa 89 % + Russia 8 % + Zimbabwe 2 % + USA 1 % + Canada 0.5 % | 合计 **100.5 %**。 | 系各项独立四舍五入所致，**非实质错误**，与 USGS 的量级一致（南非约占全球 PGE 储量九成）。此处仅作提示，答题时不必纠正。 |

**其他核对结果（均无误，记录以备查）：**
- `tan δ = 447.2 / 1053.5 → δ = 23.0007°` ✅
- 体积 32,392,846.2 m³（对应未取整斜长 7377.576 m）✅
- 体密度 3.2294 → 3.23 t/m³ ✅（算术加权前提下）
- 质量 32,392,846.2 × 3.23 = 104,628,893.2 t ✅ 逐位吻合
- 总 PGE 104,628,893.2 t × 4 g/t = 418,515,572.8 g = 418.5 t ✅
- 讲义中所有 PGM 化学式（PtAs₂、RuS₂、OsS₂、(Ir,Ru,Rh,Pt)AsS、(Pt,Pd,Ni)S、PtS）与硫化物化学式（Fe₁₋ₓS、(Fe,Ni)₉S₈、CuFeS₂）✅ 全部正确
- 题干矿物化学式（CaMgSi₂O₆、CaAl₂Si₂O₈、FeCr₂O₄、Fe₁₋ₓS）✅ 正确
- 各矿物密度（3.3 / 2.75 / 4.62 / 4.65 g/cm³）✅ 与 mindat 数据一致
- 讲义配图熔点 1555 / 3033 / 1768 °C ✅ 分别对应 Pd / Os / Pt
- Bushveld 侵位年龄 2.06 Ga、面积 >70,000 km²、礁层厚 0.4–2.5 m、Merensky 3–20 g/t、UG-2 4–7 g/t ✅ 均与文献量级一致
