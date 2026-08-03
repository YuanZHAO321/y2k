# EART26201 Principles of Geochemistry — Week 09 学习笔记

> 本周材料：`Lecture/Week 9/lecture 9 redox 2025-1.md`（幻灯片）、`lecture 9 quiz answers 2024.md`（课堂 Kahoot 测验，2024 版）、`EART26201 - 01-Dec-transcript.md`（课堂录音转写，7,212 词，本周最主要的信息来源）、`Practical/Week 9/practical 2 post lab answers 2.md`（Experiment 2 课后问答参考答案）。
> 编号说明：课程大纲（spec）把 redox 排在 "Week 10"，是因为 spec 的周次从 Week 2 起算且含 reading week；本笔记库一律采用**文件夹周次**，故本周为 **Week 09**。

---

## 一、本周主题

**本周主题：氧化还原（reduction–oxidation, redox）反应，以及用 Eh / pE 这个「氧化还原的 pH」来定量描述天然水的氧化还原状态。**

### 1.1 在全课骨架中的位置

EART26201 全课有四大块：

| 块 | 内容 | 对应周次（文件夹编号） |
|---|---|---|
| ① 热力学与相图 | 平衡常数、ΔG、相图判读、熔融/结晶 | W03–W05 |
| ② 反应动力学与扩散 | 反应速率、扩散、地质过程的时间尺度 | W06 前半 / 相关 |
| ③ **水溶液化学：酸碱、溶解度、氧化还原** | 离子在溶液中的行为、络合与溶解度、缓冲与碱度、**氧化还原** | W06–**W09** |
| ④ 放射性与稳定同位素 | 定年、古气候、地幔不均一性 | W03、W10 |

**本周是第三块的收尾**。第三块的四周有一条非常清楚的主线：

- **W06 Ions in solution（离子在溶液中）**——建立"物种（species）"与活度的概念；
- **W07 Solubility and complexing（溶解度与络合）**——解决"某个元素能不能进入溶液、以什么形式进入"；
- **W08 Buffering, alkalinity and silica（缓冲、碱度与硅）**——建立第一个**主变量（master variable）pH**，以及矿物/溶液如何缓冲 pH；
- **W09 Redox（本周）**——建立**第二个主变量 Eh（或 pE）**。

老师原话（transcript）："we've talked quite a lot about pH … but there's another thing that quite often goes with pH in natural environments to essentially control what the fluids are really like, and that's something called EH or PE"；幻灯片总结页写成考点式的一句："Oxidation potential (as measured by Eh or pE) is the redox equivalent of pH. **Both Eh and pH are master variables in environmental systems.**"

所以 W08 与 W09 合起来才是完整的一对：**pH 决定质子（H⁺）的可得性，pE/Eh 决定电子（e⁻）的可得性**；两者共同决定元素的价态、物种、能否迁移、会否沉淀。这也正是 **Eh–pH 图（Pourbaix 图）** 存在的理由——把两个主变量放在两根坐标轴上。

### 1.2 为什么本周对 EART26001（Energy and Resources）支撑最直接

幻灯片和 transcript 里老师自己点名了 ERG（Energy and Resources Geoscience）学生：

> "If you're kind of like an ERG student, for example, redox reactions are also critical for understanding what happens in reservoir rocks."

材料里直接给出的 ERG 相关落点有：

1. **储层与盖层完整性（reservoir integrity / caprock preservation）**——Green River（美国）案例：还原性、微酸性的 CO₂-Na-Cl-SO₄ 流体沿断层上升，溶解赤铁矿（hematite）造成"漂白带（bleached zone）"，同时沉淀碳酸盐与黄铁矿。这直接关系到油气储层与 **CCS（碳捕集与封存）** 的盖层能否长期保存。
2. **有害金属迁移与固定（harmful metal transport / immobilization）**——同一反应锋面上钴、铜出现浓度尖峰，说明氧化还原锋面是天然的"金属捕集器"。
3. **放射性废物封存（radioactive waste containment）**——幻灯片首页列举的应用之一；老师在讲反应锋面固定金属时明确说这"feeds back into some of the ideas about radioactive waste disposal and stopping those radioactive metals moving"。
4. **酸性矿山排水（acid mine drainage）与 Mam Tor 案例**——Fe²⁺ 出露地表被氧化为 Fe³⁺ 并沉淀为 Fe(OH)₃，就是矿区溪流"橙色淤泥"的成因。
5. **水质、垃圾填埋场渗滤液、有机污染物**——幻灯片首页列举。

> 📎 背景补充：本课材料没有展开、但 EART26001 里最常考、且**机理完全就是本周内容**的几个资源实例，可以直接把本周的 Eh–pH 思路搬过去：
> - **铀矿（roll-front / sandstone-hosted uranium）**：U⁶⁺ 以 uranyl 络合物 UO₂(CO₃)₂²⁻、UO₂(CO₃)₃⁴⁻ 形式在氧化性地下水中高度可溶并随水流迁移；遇到含有机质或黄铁矿的还原带被还原为 U⁴⁺，以沥青铀矿（uraninite, UO₂）沉淀。矿体正好长在**氧化还原锋面**上，形态呈"卷状（roll-front）"——与本周 Green River 的反应锋面完全同构。
> - **条带状铁建造（Banded Iron Formation, BIF）**：太古宙—古元古代海洋 Fe²⁺ 可长距离迁移（还原性海水），大氧化事件（GOE）后 Fe²⁺ 被氧化为 Fe³⁺ 沉淀——这正是本周"Fe²⁺ 溶解度比 Fe³⁺ 高约 15 个数量级"的地球尺度版本。
> - **金的热液搬运**：Au 在还原性、含硫热液中以 Au(HS)₂⁻ 络合物搬运；氧化（或沸腾去除 H₂S）使硫化物络合物失稳，Au 沉淀成矿——把 W07 的络合与本周的 redox 串在一起。
> - **有机质保存与烃源岩**：缺氧（anoxic）+ 硫酸盐还原环境抑制有机质被氧化分解，是黑色页岩型烃源岩形成的先决条件——对应本周"有机质氧化反应序列"那一页。

---

## 二、核心概念

### 2.1 什么是氧化还原反应

**凡是涉及氧化态（oxidation state）改变的反应，就是氧化还原反应。**

- **氧化 = 失电子；还原 = 得电子**。助记词 **OIL RIG**（**O**xidation **I**s **L**oss, **R**eduction **I**s **G**ain）。老师在课上说这是"今天你只要记住一样东西"的那一样：
  > "there's that oil rig acronym at the top. Remember that? That's the only thing you remember from today that will be useful for you."
- **氧化剂（oxidizing agent）接受电子，自身被还原；还原剂（reducing agent）给出电子，自身被氧化。** 注意这个"自身相反"的关系是最常见的绕晕点。
- **重要澄清（老师专门讲的）**：地表环境下"氧化"确实常与氧气有关，但**氧化的定义与氧无关**，只与电子得失有关：
  > "I think naturally most of us think oxidation is something to do with the reaction of the oxygen. And that's kind of true at the Earth's surface, but it's not a definition of what redox or oxidation is. Oxidation, from a chemistry point of view, is just loss of electrons."

  向深部走，做氧化剂的就不再是 O₂，而依次是 N、Mn、Fe、S（见 §2.9）。

### 2.2 为什么地球化学家在乎它

幻灯片给的两个理由（老师逐条展开）：

1. **控制迁移性（mobility）**——因为价态直接控制溶解度。经典例子 Mam Tor：地下水中 Fe²⁺ 可溶、随水流走；接触空气被氧化成 Fe³⁺ 后立刻沉淀为 Fe(OH)₃。
2. **控制毒性（toxicity）**——幻灯片例子：**As³⁺（还原条件下稳定）比 As⁵⁺ 对人体毒性更大**。
3. 加上一句"天然水的氧化还原条件一直在变"，所以元素的化学物种（speciation）与迁移性也一直在变。

**具有 redox 行为的元素**（幻灯片原文）：

- **主量元素**：C、S、N、Fe（部分地下系统中还有 Mn）
- **微量元素**：As、Pb、Cu、Cd、Hg、Se、Cr —— 恰好几乎全是环境有害元素

### 2.3 氧化态（oxidation state / number / redox state）的定值规则

定义（幻灯片）：**如果把分子/物种拆散成离子，各原子将带有的电荷**，就是它的氧化态。它有一堆同义名：oxidation state / oxidation number / redox state / redox number。

规则（幻灯片 + 课堂）：

| 规则 | 例 |
|---|---|
| 单质中元素氧化态为 **0** | O₂、Cu°(s)、Zn°(s) 中均为 0（因为电子在同种原子间均分） |
| 与他元素成键时，**O 几乎总是 −2** | SO₄²⁻、CO₃²⁻、NO₃⁻、H₂O 中 O 皆为 −2 |
| **H 总是 +1** | H₂O、H₂S 中 H 为 +1 |
| 各原子氧化态之和 = 该物种的净电荷 | 见下 |

**典型算例（课堂与 quiz 都考）：**

- **SO₄²⁻**：4 个 O 共 −8，总电荷 −2 ⟹ S 为 **+6**。
- **CO₃²⁻**：3 个 O 共 −6，总电荷 −2 ⟹ C 为 **+4**。（Kahoot 第 4 题，老师原话："oxygen is two minus. We've got three of those, so the oxygen is six minus. But the overall charge is two minus, so the carbon must be plus four."）
- **MnO₂**：2 个 O 共 −4，中性分子 ⟹ Mn 为 **+4**。
- **Fe(OH)₃**：3 个 OH⁻ 共 −3，中性 ⟹ Fe 为 **+3**。（Kahoot 第 6 题）

### 2.4 氧化还原对（redox couple）与半反应（half-reaction）

**关键物理事实：溶液中不存在自由电子。**

> 幻灯片："Free electrons do not exist in solution. Any electron lost from one species in solution must be immediately gained by another."
> 课堂："You don't get electrons floating around in water. Otherwise, if you stuck your finger in, you'd get electrons."

因此氧化还原总是**成对**发生：

$$\mathrm{Ox_1 + Red_2 \rightleftharpoons Red_1 + Ox_2}$$

Ox₁–Red₁ 与 Ox₂–Red₂ 各自称为一个**氧化还原对（redox couple / redox pair）**。

幻灯片给的 Cu–Zn 例子：

$$\mathrm{Cu^0(s) + Zn^{2+}(aq) \rightleftharpoons Cu^{2+}(aq) + Zn^0(s)}$$

- 氧化半反应：Cu⁰(s) ⇌ Cu²⁺(aq) + 2e⁻ （Cu 由 0 → +2，失电子）
- 还原半反应：Zn²⁺(aq) + 2e⁻ ⇌ Zn⁰(s) （Zn 由 +2 → 0，得电子）

> ⚠️ 注意：这个方向只是用来演示"如何拆半反应"的形式写法。在标准态下自发方向其实是相反的（Zn + Cu²⁺ → Zn²⁺ + Cu，即后面 "Redox potential" 那页用的方向）。详见勘误表第 5 条与 §6.2。

### 2.5 半反应的配平——四步法（本周必考技能）

幻灯片给出的**固定顺序**（老师说"that's the order that you need to go through"）：

1. **配平除 O、H 以外的原子**（先把金属等主元素配平）；
2. **用 H₂O 配平氧**；
3. **用 H⁺ 配平氢**；
4. **用 e⁻ 配平电荷**。

顺序不能乱——先配电荷再配氢一定会推倒重来。

#### 完整算例：Fe²⁺ 被 MnO₂ 氧化（幻灯片 + 课堂逐步讲解）

**背景**：Fe²⁺ 被氧化为 Fe³⁺（以 Fe(OH)₃ 形式沉淀）；同时 MnO₂ 中的 Mn⁴⁺ 被还原为 Mn²⁺。

**第 1 步：只看金属，写骨架半反应并配平电子数**

- 氧化：Fe²⁺ ⇌ Fe³⁺ + e⁻ （放出 1 个电子）
- 还原：Mn⁴⁺ + 2e⁻ ⇌ Mn²⁺ （吸收 2 个电子）

电子数 1 ≠ 2，所以氧化半反应要 ×2：

$$\mathrm{2Fe^{2+} + Mn^{4+} \rightleftharpoons Mn^{2+} + 2Fe^{3+}}$$

（左 +4+4 = +8，右 +2+6 = +8，电荷已平。）

**第 2 步：把反应放回水里，配氧、配氢、配电荷**

*氧化半反应*：产物是 2Fe(OH)₃，含 2×3 = **6 个 O** ⟹ 左边加 **6H₂O**；6H₂O 带来 **12 个 H**，右边 2Fe(OH)₃ 已含 6 个 H，还差 6 个 ⟹ 右边加 **6H⁺**；此时左边电荷 2×(+2) = +4，右边 +6 ⟹ 右边再加 **2e⁻**：

$$\mathrm{2Fe^{2+} + 6H_2O \rightleftharpoons 2Fe(OH)_3 + 6H^+ + 2e^-}$$

*还原半反应*：MnO₂ 含 2 个 O ⟹ 右边加 **2H₂O**；2H₂O 含 4 个 H ⟹ 左边加 **4H⁺**；左边电荷 +4，右边 +2 ⟹ 左边加 **2e⁻**：

$$\mathrm{MnO_2 + 4H^+ + 2e^- \rightleftharpoons Mn^{2+} + 2H_2O}$$

**第 3 步：两式相加，消去两边重复项**

$$\mathrm{2Fe^{2+} + MnO_2 + 6H_2O + 4H^+ + 2e^- \rightleftharpoons 2Fe(OH)_3 + 6H^+ + 2e^- + Mn^{2+} + 2H_2O}$$

消去 2e⁻、2H₂O、4H⁺，得**最终方程**：

$$\boxed{\mathrm{2Fe^{2+} + MnO_2 + 4H_2O \rightleftharpoons 2Fe(OH)_3 + 2H^+ + Mn^{2+}}}$$

**验算电荷**：左 2×(+2) = **+4**；右 0 + 2×(+1) + (+2) = **+4**。✔ 老师特意强调："it's got plus four on the left, but it's got plus four on the right, so there's no charge change. And that's important when we're dealing with redox reactions."

> **老师强调的考点**：中学阶段"配平"只要求**原子数**守恒；地球化学里必须**同时**要求**电荷**守恒。否则"in the environment, you'd have situations where things will just naturally charge up, which isn't what happens."（Kahoot 第 7 题就是考这个：a chemical equation is balanced when **both mass/atoms and charge balance**。）

### 2.6 电化学电池与标准氢电极（SHE）

要把 redox 定量化，第一步是量出各元素的**电极电位**。装置：两个**电极**、导线、**伏特计**、**盐桥（salt bridge）**构成回路；**其中一极永远是标准氢电极（Standard Hydrogen Electrode, SHE）**——H₂ 气 + 强酸溶液、**H⁺ 活度 = 1**（课堂："something like HCl"）；另一极放待测金属，其离子活度也取 1。

**以 Zn 为例**：Zn(s) 放出电子变成 Zn²⁺ 进入溶液（**氧化**），电子沿导线跑到氢电极侧被 H⁺ 接受（**还原**）生成 H₂ 气——**实验上能看到氢电极那侧冒气泡**。伏特计读到的就是这一过程的电动势（emf）。

$$\mathrm{Zn(s) = Zn^{2+}(aq) + 2e^-} \qquad \mathrm{2H^+ + 2e^- = H_2(g)}$$

### 2.7 电动序（electromotive series）与标准电极电位 E⁰

幻灯片规定的读表规则：

- 表中每个半反应**左边写还原态、右边写氧化态**；
- 使 **H⁺ 被还原成 H₂** 的半反应取**负值**；
- 使 **H₂ 被氧化成 H⁺** 的半反应取**正值**；
- **强还原剂在表顶，强氧化剂在表底**。

老师的口语版判据："if it's got a negative number, it means it【指该金属】's oxidized and the hydrogen gas is reduced. If it's got a positive voltage, it means that actually the metal itself would be reduced and the hydrogen would be oxidized."

**材料中明确给出的 E⁰ 数值（务必记住这三个）：**

| 半反应 | E⁰ / V | 出处 |
|---|---|---|
| Zn / Zn²⁺ | **−0.76** | 幻灯片 "Redox potential" |
| Cu / Cu²⁺ | **+0.34** | 同上 |
| Cu⁺ ⇌ Cu²⁺ + e⁻ | **+0.16** | 幻灯片 "Using pE for predicting speciation" |

**由两个半反应算电池电位**（幻灯片原文）：对 Zn + Cu²⁺ ⇌ Zn²⁺ + Cu，把两个 E⁰ 相减，−0.76 − 0.34 = **−1.10 V**；幻灯片随后写道 "Any reaction with a negative potential will go to the right. Any reaction with a positive potential will go to the left."。课堂上老师只说 "the difference between those two is 1.1 volts"，没有说符号。

> ⚠️ **符号约定警告**：这套"负值向右"的表述与化学界通用的 IUPAC 约定**符号相反**。通用约定是 E°cell = E°(阴极) − E°(阳极) = +0.34 − (−0.76) = **+1.10 V**，且 **ΔG° = −nFE°**，即 **E° 为正 ⟹ 反应按写出方向自发**。两套说法数值大小一致（1.10 V），只是正负号约定不同。考试时若用通用约定作答请务必写清"E°cell = +1.10 V，正值 ⟹ 自发向右"，逻辑自洽即可。详见勘误表第 1 条。

### 2.8 Eh 与 pE：两个等价的"氧化还原主变量"

**野外怎么测？** 老师带了实物："a handheld redox monitor"——白色球泡里就装着一个氢电极（"it's actually the same thing as we've just seen on that schematic, just crammed into that little bulb on the end"），另一极直接接触水样。探头读数就是这份水相对 SHE 的电位。

**两种表达方式：**

| 量 | 定义 | 单位 | 直觉 |
|---|---|---|---|
| **Eh**（oxidation potential / redox potential） | 溶液相对 SHE 的电位 | 伏特 V（或 mV） | 直接测出来的电压 |
| **pE**（pe）| pE = −log[e⁻]（类比 pH = −log[H⁺]） | 无量纲 | 电子的"活度"标度 |

- **pE 是"电子活度"**——幻灯片承认这是方便的虚构："pE is defined as the 'activity' of the electron in water."；老师："It's a bit of a cheat … But for the level of chemistry that we are looking at, it's fine."
- **一份处于平衡的天然水只有一个 pE 值**——这是全部计算的前提。有了它，就能对**任何**氧化还原对算出氧化态/还原态的活度比，从而定物种（speciation）与优势域（predominance）。
- **方向记忆**：**pE 低 ⟹ 电子的 source ⟹ 还原性**；**pE 高 ⟹ 电子的 sink ⟹ 氧化性**；高 Eh 与高 pE 意思完全相同。

### 2.9 天然环境中的 pE–pH

**总体规律（幻灯片 + 课堂）：**

- **与大气接触的环境 pE 高**：雨水、海洋、溪流；
- **与大气隔绝的环境 pE 低**：泥炭沼泽（peat bogs）、深部地下水；
- 原因很直观：大气 **P(O₂) = 0.21**，这个数离**水稳定域的上限**很近，离下限很远。所以地表水基本贴着 Eh–pH 图的上边界跑。
- **在多数天然水中，氧化还原条件由 O、S、Fe 控制**（Mn 在部分地下系统中也重要）。

**按含氧与否分类（幻灯片 "Eh and pH – natural waters"）：**

| 类型 | 定义 | pH 可以是？ |
|---|---|---|
| **含氧水（oxic waters）** | 含可测溶解氧 | 可低（硫氧化产酸）也可高（高碱度） |
| **还原性/缺氧水（reducing / anoxic waters）** | **同时含溶解铁和硫化物** | 可低（S → 硫酸）也可高（有机反应产 HCO₃⁻） |

老师特别澄清：**pE 的分区比 pH 清楚得多**——"The pH is not as well defined as pE in that sense. The surface environments are here, deeper environments are here, but both can have either alkaline or acidic conditions. It just depends what else is present." 也就是说：**深浅决定 pE，但不决定 pH**。

**有机质氧化的反应序列（redox ladder）——微生物介导**

幻灯片 "Redox reactions that oxidise organic matter"：地表酸性且氧化，向深部趋于还原。用 **CH₂O 代表最简单形式的有机碳**，随深度增加，充当氧化剂的元素按 **O > N > Mn > Fe > S > C** 的顺序更替：

| 序号 | 过程 | 氧化剂（被还原者） |
|---|---|---|
| 1 | 好氧呼吸 Aerobic respiration | O₂ |
| 2、3 | 反硝化 Denitrification | NO₃⁻（N） |
| 4 | 锰还原 Manganese reduction | MnO₂（Mn⁴⁺ → Mn²⁺） |
| 5 | 铁还原 Iron reduction | Fe(OH)₃ / Fe³⁺ → Fe²⁺ |
| 6 | 硫酸盐还原 Sulphate reduction | SO₄²⁻ |
| 7 | 甲烷发酵 / 产甲烷 Methane fermentation（methanogenesis） | 有机碳自身歧化 |

关键点（幻灯片 + 课堂）：

- **绝大多数这类反应由细菌介导（bacterially mediated）**，细菌从中获取生命活动所需能量；
- **越往深，单位反应产能越少 ⟹ 生存越困难**（"it gets harder and harder for things to live in the subsurface as you get deeper"），同时**氢浓度升高**，环境自然更还原；
- 天然沉积物中因此形成**层状的反应序列**。

### 2.10 Green River 储层案例（本周唯一的完整实例研究）

幻灯片 "Redox reactions in reservoir rocks" + 课堂详解：

**流体性质（实测）**：Na–Cl–SO₄–CO₂ 富集；**pH 5.0–5.3（酸性）**；**Eh 0 至 −50 mV（还原性，地表处）**。

**地质情景**：近水平层状碳酸盐岩；一条**断层作为流体通道**；断层两侧岩石由暗棕色（**赤铁矿 hematite**）变为浅色**漂白带（bleached zone）**；流体在地表溢出，冒 CO₂ 气泡并沉淀碳酸盐。

**用 Eh–pH 图解释**：把实测流体的 (pH, Eh) 点画到图上（幻灯片里的小黑方块），落在**碳酸盐 + 黄铁矿稳定域内，但不在赤铁矿稳定域内**。因此：

- **赤铁矿被溶解**（流体与之不相容）⟹ 岩石褪色成漂白带；
- **碳酸盐（ankerite/dolomite）与黄铁矿沉淀**；
- 在漂白/未漂白边界（**反应锋面 reaction front**）上，薄片分析显示 **Co、Cu 浓度出现明显尖峰** ⟹ **微量金属被固定（immobilized）**。

**意义（老师逐条点名）**：储层完整性、碳酸盐盖层能否被溶蚀、油气与 CO₂ 封存（CCS）、有害金属迁移的阻断、放射性废物处置。老师总结："It's not just water flowing through a rock. It's water flowing through a rock that's dissolving some minerals and precipitating other ones."

---

## 三、公式与图表

### 3.1 pE 的定义

$$\mathrm{pE} = -\log[e^-] \qquad (\text{类比 } \mathrm{pH} = -\log[\mathrm{H^+}])$$

- **[e⁻]**：电子的"活度"（无真实自由电子，是形式量）；
- **pE 无量纲**；数值范围在天然水中大致 −10 ~ +17（由水稳定域限定，见 §3.5）；
- **适用条件**：溶液处于（局部）氧化还原平衡。

### 3.2 pE 与 Eh 的换算 ★

材料原文（幻灯片，OCR 后为 "pE 169.Eh  Eh .0059 pE"，实为）：

$$\boxed{\mathrm{pE} = 16.9\,E_h \qquad\qquad E_h = 0.059\,\mathrm{pE}}$$

其一般式为：

$$\mathrm{pE} = \frac{F\,E_h}{2.303\,R\,T}$$

**逐项解释：**

| 符号 | 含义 | 材料给的数值 | 单位 |
|---|---|---|---|
| Eh | 相对 SHE 的氧化还原电位 | 实测量 | V（伏特） |
| F | **法拉第常数**（1 mol 电子的电量） | 幻灯片写 **96420** | J V⁻¹ eq⁻¹（= C mol⁻¹） |
| R | 气体常数 | **8.3144** | J K⁻¹ mol⁻¹ |
| T | 绝对温度 | **298 K（25 °C）** | K |
| 2.303 | ln → log₁₀ 的换算因子 | — | 无量纲 |

**核算（务必自己算一遍）：**

$$\frac{F}{2.303RT} = \frac{96485}{2.303 \times 8.3144 \times 298.15} = \frac{96485}{5708.5} = \mathbf{16.90}$$

✔ 与材料的 16.9 一致。反过来 1/16.9 = **0.0592**，与材料的 0.059 一致。

> ⚠️ **系数只在 25 °C 成立**。温度变了，16.9 和 0.059 都要重算（都正比/反比于 T）。热液系统绝不能直接套 25 °C 的数。
> ⚠️ 幻灯片把 F 写成 **96420**，标准值是 **96485 C mol⁻¹**（见勘误表第 3 条）；不过对 16.9 这个两位有效数字的结果没有影响。
> 老师原话："Don't learn this slide, this is just the conversion between the two."——**要记的是 16.9 这个数字和"两者含义相同"这句话**，不是推导。

### 3.3 能斯特方程（Nernst equation）★★★ 本周核心公式

**推导起点**：任一半反应

$$\mathrm{Ox} + n\,e^- \rightleftharpoons \mathrm{Red}$$

写平衡常数（产物比反应物，化学计量数变成幂次）：

$$K = \frac{[\mathrm{Red}]}{[\mathrm{Ox}]\,[e^-]^n}$$

解出 [e⁻]：

$$[e^-] = \left(\frac{[\mathrm{Red}]}{K\,[\mathrm{Ox}]}\right)^{1/n}$$

取负对数（用 log(xᵃ) = a·log x）：

$$\mathrm{pE} = -\log[e^-] = \frac{1}{n}\log K - \frac{1}{n}\log\frac{[\mathrm{Red}]}{[\mathrm{Ox}]}$$

定义 **pE⁰ = (1/n) log K**，即得

$$\boxed{\ \mathrm{pE} = \mathrm{pE}^{0} - \frac{1}{n}\log\frac{[\mathrm{Red}]}{[\mathrm{Ox}]}\ }\qquad\text{— the Nernst equation}$$

**逐项解释：**

| 符号 | 含义 | 怎么得到 | 单位 |
|---|---|---|---|
| **pE** | 该天然水的电子活度标度值 | **野外用 redox 探头实测**（若测得 Eh，先 ×16.9 换成 pE） | 无量纲 |
| **pE⁰** | 该**特定半反应**的标准值 = (1/n) log K | **查电动序表**得 E⁰，再 ×16.9 | 无量纲 |
| **n** | 该半反应**转移的电子数** | 由配平后的半反应读出 | 无量纲 |
| **[Red] / [Ox]** | 还原态与氧化态的**活度比** | 待求（或已知求 pE） | 无量纲比值 |

**适用条件**：25 °C（因为 16.9 是 25 °C 值）、体系达氧化还原平衡、用活度而非浓度（稀溶液可近似）。

> 📎 背景补充：以 **Eh 为变量**的等价形式（材料只给了 pE 形式）：
> $$E_h = E^0 - \frac{2.303RT}{nF}\log\frac{[\mathrm{Red}]}{[\mathrm{Ox}]} = E^0 - \frac{0.0592}{n}\log\frac{[\mathrm{Red}]}{[\mathrm{Ox}]}\ \ (25\,^\circ\mathrm{C},\ \text{单位 V})$$
> 记住 **0.0592 V / n** 这个"每十倍浓度比对应 59 mV"的经验数，做题很快。
>
> 📎 背景补充：与 **ΔG** 的关系（材料未直接给出，但是把本周接回 W03–W05 热力学的桥）：
> $$\Delta G = -nFE \qquad \Delta G^{0} = -nFE^{0} = -2.303\,RT\log K$$
> 由此可见 **E⁰ 与 log K 只差一个常数因子**，"电位表"本质就是"平衡常数表"。也正因为 ΔG⁰ = −nFE⁰，**E⁰ 为正 ⟺ ΔG⁰ 为负 ⟺ 反应自发向右**（这是 §2.7 里那条符号警告的根据）。

**老师对推导的态度（重要的考试情报）：**
> "Do not, please do not learn any of this. Don't even look at it, unless you really want to. … All I want you to know is that you can get from here to here."
> 也就是：**推导不考，会用能斯特方程才考**。

### 3.4 能斯特方程的完整算例：溪水中的铜（幻灯片 + 课堂逐步）

**题目**：某溪流实测 **Eh = +0.20 V**。铜可能是 Cu⁺ 或 Cu²⁺，求两者比例。已知半反应 Cu⁺ ⇌ Cu²⁺ + e⁻ 的 **E⁰ = +0.16 V**。

**第 0 步（定性预判，老师强调先做）**：+0.20 V > +0.16 V，说明**这份水比该铜反应本身更氧化**，所以铜应以 **Cu²⁺ 为主**。定量计算只是把这个直觉量化。

**第 1 步：Eh → pE（因为能斯特方程用 pE）**

- 溪水：pE = 16.9 × 0.20 = **3.38**
- 铜半反应：pE⁰ = 16.9 × 0.16 = **2.70**

**第 2 步：代入能斯特方程**，此处 Ox = Cu²⁺，Red = Cu⁺，**n = 1**：

$$3.38 = 2.70 - \frac{1}{1}\log\frac{[\mathrm{Cu^{+}}]}{[\mathrm{Cu^{2+}}]}$$

**第 3 步：移项**

$$0.68 = -\log\frac{[\mathrm{Cu^{+}}]}{[\mathrm{Cu^{2+}}]}$$

**第 4 步：解对数**

$$\frac{[\mathrm{Cu^{+}}]}{[\mathrm{Cu^{2+}}]} = \frac{1}{10^{0.68}} = 10^{-0.68} = \mathbf{0.21}$$

**结论**：Cu⁺ : Cu²⁺ ≈ 0.21，即约 **83 % 的铜是 Cu²⁺**，与定性预判一致。

老师的推广："if it was arsenic, for example, it would tell us **how many of those arsenic atoms are in the toxic state and how many are in the less toxic state**."——这正是能斯特方程在环境地球化学里的核心用途，也是 Kahoot 第 9 题的答案（**Nernst equation is used to quantify oxidation states**）。

### 3.5 Eh–pH 图（pE–pH 图 / Pourbaix 图）——务必彻底吃透

**别名**：pE–pH diagram = Eh–pH diagram = **Pourbaix diagram**（以 Marcel Pourbaix, 1904–1998 命名）。

#### (a) 坐标轴

- **横轴 x = pH**（通常 0–14）——质子活度；
- **纵轴 y = pE 或 Eh**（Eh 用 V，pE 无量纲；两轴可互换，只差 ×16.9）——电子活度；
- 图上每个**阴影区域 = 某个矿物或溶解物种的稳定域（stability field / predominance field）**。

#### (b) 水的稳定域：两条平行斜线怎么来的 ★

**这是全图的骨架，也是最常考的推导。**

**上限（氧化端）**——由 O₂/H₂O 半反应定义，代表**纯氧气氛**，"as oxidizing as you can get"：

$$\tfrac14\mathrm{O_2} + \mathrm{H^+} + e^- \rightleftharpoons \tfrac12\mathrm{H_2O}, \qquad \mathrm{pE}^0 = +20.75$$

**下限（还原端）**——由 H⁺/H₂ 半反应定义，代表**纯氢气氛**，"you can't get more reducing"：

$$\tfrac12\mathrm{H_2} \rightleftharpoons \mathrm{H^+} + e^-, \qquad \mathrm{pE}^0 = 0.00\ (\text{按定义，SHE 就是零点})$$

**下限的推导（幻灯片逐行 + 课堂逐字讲解）**：把 H⁺ + e⁻ ⇌ ½H₂ 代入能斯特方程，n = 1，Red = H₂^{1/2}，Ox = H⁺：

$$\mathrm{pE} = \mathrm{pE}^0 - \log\frac{P_{\mathrm{H_2}}^{1/2}}{[\mathrm{H^+}]} = 0 - \log P_{\mathrm{H_2}}^{1/2} + \log[\mathrm{H^+}]$$

取 **P(H₂) = 1 bar**（纯氢气氛）：1^{1/2} = 1，log 1 = 0，该项消失；而 log[H⁺] = −pH。故

$$\boxed{\mathrm{pE} = -\,\mathrm{pH}}$$

课堂验证："if pH is zero, all of these bits are zero and pE is zero … Where pH is 14, pE is minus 14."

**上限的推导**：同法代入 O₂ 半反应，n = 1：

$$\mathrm{pE} = 20.75 + \tfrac14\log P_{\mathrm{O_2}} - \mathrm{pH}$$

- 取 **P(O₂) = 1 bar**（纯氧）⟹ **pE = 20.75 − pH**；
- 取**地球大气 P(O₂) = 0.21** ⟹ ¼·log 0.21 = ¼×(−0.678) = −0.17 ⟹ **pE = 20.58 − pH**；**在 pH = 7 时 pE = 13.58**（幻灯片给的数）。

**两条线的关键性质：**

1. **斜率都是 −1**（在 pE–pH 图上；在 Eh–pH 图上是 **−0.0592 V per pH unit**）——因为两个半反应都是 **1 个 H⁺ 配 1 个 e⁻**；
2. **两条线平行**——老师原话："It's exactly parallel that line to this one, but it's just offset by that 20.75."（在 Eh 轴上相差 20.75/16.9 = **1.23 V**，正是水的分解电压）；
3. **地球表面环境点（P(O₂)=0.21）几乎贴着上限**——只比纯氧气氛低 0.17 个 pE 单位。所以"地表是氧化环境"在图上一目了然：地表水都在图的**上半部**。

#### (c) 各稳定域的边界线代表什么？斜率由什么决定？★★

幻灯片本身只推了水的两条线，但整套图的判读规则是同一个：**任一条边界线，就是"边界两侧的两个物种活度相等"这个条件代入能斯特方程后得到的 pE–pH 关系式。**

> 📎 背景补充（规则的一般化，材料只给了水线的特例）：设边界反应写成
> $$a\,\mathrm{Ox} + m\,\mathrm{H^+} + n\,e^- \rightleftharpoons b\,\mathrm{Red} + c\,\mathrm{H_2O}$$
> 令两侧活度相等，则边界方程为
> $$\mathrm{pE} = \mathrm{pE}^0 - \frac{m}{n}\,\mathrm{pH}\qquad\Longrightarrow\qquad \textbf{斜率} = -\frac{m}{n}$$
> 由此得到三条一眼判读法则：
>
> | 边界反应涉及 | 斜率 | 线的形状 | 例 |
> |---|---|---|---|
> | **有 e⁻，无 H⁺**（n ≠ 0, m = 0） | 0 | **水平线** | Fe³⁺ + e⁻ = Fe²⁺ |
> | **有 H⁺，无 e⁻**（n = 0, m ≠ 0） | ∞ | **垂直线**（纯酸碱/水解反应，与 redox 无关） | Fe³⁺ + 3H₂O = Fe(OH)₃ + 3H⁺ |
> | **H⁺ 与 e⁻ 数目相等**（m = n） | −1 | **与水稳定线平行的斜线** | 水的上下限本身 |
> | 一般 m ≠ n | −m/n | 其他斜率的斜线 | 视反应而定 |
>
> 另外两点判读常识：
> - **溶解物种之间**的边界，位置**不随假定浓度而变**（浓度在比值里约掉）；而**溶解物种与矿物**之间的边界，位置**依赖于所假定的溶解物种活度**，常规惯例是取 **10⁻⁶**（有时 10⁻⁴ 或 10⁻⁸）。所以**同一元素的 Eh–pH 图，换了假定浓度，矿物域会明显胀缩**——看图先看图注。
> - Eh–pH 图是**热力学平衡图**，只回答"什么能稳定存在"，不回答"多快达到"。

#### (d) 怎么用图判断某元素的赋存形式——Mam Tor 的图上轨迹

老师用 Mam Tor 演示了标准读图流程：

1. 出露前，水在岩石里，含 **Fe²⁺**，pH 偏酸（黄铁矿氧化产硫酸），pE 未测但偏低 ⟹ 落在图左下的 **Fe²⁺ 稳定域**；
2. 水流出岩壁、接触空气 ⟹ **pE 升高**；同时与酸性较弱的水混合 ⟹ **pH 升高**；
3. 在图上流体沿**右上方**演化，**跨过边界进入 Fe(OH)₃（铁氢氧化物）稳定域**；
4. 因此 Fe(OH)₃ 沉淀 ⟹ 就是山坡上那些**橙色淤泥**。

老师原话："the fluid would have evolved in this kind of direction as it mixed with less acidic water. And it would have entered into the iron hydroxide field and therefore precipitated iron hydroxide."

同一套流程用在 Green River 上：把实测 (pH 5.0–5.3, Eh 0 至 −50 mV) 点上图 ⟹ 落在碳酸盐 + 黄铁矿域、不在赤铁矿域 ⟹ 预测赤铁矿溶解、碳酸盐与黄铁矿沉淀 ⟹ 与野外漂白带完全吻合。

> ⚠️ **幻灯片的警告原文**：*"Caution: thermodynamically stable but may be limited by kinetics."* ——图只告诉你热力学上谁稳定，**不保证反应真的发生或以多快速度发生**。这是本周与 W06 动力学那一块的接口，也是易错点之一（见 §6.5）。

### 3.6 溶解度的数量级：Fe²⁺ vs Fe³⁺

幻灯片 + 课堂反复强调的一个数：

> **在高 pE、pH = 7 的水中，Fe²⁺ 的溶解度比 Fe³⁺ 高约 15 个数量级（fifteen orders of magnitude）。**

老师怕学生看错，专门强调："It's not 15 times, **15 zeros**. So billions and billions of times more soluble than iron three plus." 这一个数就足以解释：为什么价态一变，铁就从"随水走"变成"就地沉淀"；为什么矿区溪流是橙色的；为什么任何缓流溪沟都能看到橙色淤泥。

---

## 四、课堂补充

（本节内容来自 7,212 词的课堂转写，只收录幻灯片上没有、或老师额外强调/澄清的部分。）

### 4.1 课程节奏与考试相关的口头信息

- 本周是**实验课写作周（write-up week）**："hopefully you managed to get to a lab practical last week. This week we'll do the write-up for that, like you did two weeks ago." 也就是**上周做 Experiment 2（缓冲与指示剂），本周写报告**——这正好解释了为什么 Week 9 文件夹里放的是 `practical 2 post lab answers`。
- **这是全课最后一次动手化学实验**："That was your last week doing lab chemistry … then next week we're just doing a class-based exercise on stab[le] iso[topes]." 下周（Week 10）转为纸面/PC 的稳定同位素练习。
- 老师对地球化学方向学生说："those of you who are geochemists will have seen some of this, but there's quite a lot more content than I covered in the other unit where I kind of touched on redox."——本周比其它单元里的 redox 讲得深。

### 4.2 老师明说"要记 / 不要记"的分界（最有价值的考试情报）

| 内容 | 老师原话 | 结论 |
|---|---|---|
| OIL RIG | "That's the only thing you remember from today that will be useful for you." | **必记** |
| pE ↔ Eh 换算推导 | "Don't learn this slide, this is just the conversion between the two." | 记住 **16.9** 这个数即可，不必背 F/R/T 推导 |
| 能斯特方程的完整推导（从 K 到 Nernst 的那一整页） | "**Do not, please do not learn any of this.** Don't even look at it, unless you really want to. … every year I have a slide with not all of this on it, and some people want to know how you get from one point to the other point. So I put it on, but please don't worry about it." | **推导不考**，但**会用能斯特方程必考** |
| 电动序表 | "So we have tables of different metals and how they oxidize or reduce. … That's all you really need to know." | 会**查表 + 读符号含义**即可，不必背数值 |
| 半反应配平 | 逐步演示了完整两页 | **必考技能** |

### 4.3 幻灯片上没有的推理细节

**(1) 为什么必须配平电荷——一句物理直觉**
> "Otherwise, in the environment, you'd have situations where things will just naturally charge up, which isn't what happens."
自然界不存在自发积累净电荷的水体，所以电荷守恒是硬约束，不是形式主义。

**(2) 为什么"没有自由电子"却还能定义电子活度**
老师承认这是个 cheat，但给了合理化的说法："it has activity essentially in the water **without having free electrons there**"。理解方式：pE 不是真的在数电子个数，而是描述**这份水把电子交出去/接过来的倾向**——本质上是所有共存氧化还原对共同确定的一个"电子化学势"。

**(3) 电动序表的物理读法**
老师把表的正负号翻译成实验现象："if it's got a negative number, it means it's oxidized and the hydrogen gas is reduced；if it's got a positive voltage, it means that actually **the metal itself would be reduced and the hydrogen would be oxidized**." 配合 Zn 实验中"氢电极那侧冒气泡"的现象记忆，比死记表格牢固得多。

**(4) 野外仪器与实验室装置是同一回事**
手持 redox 探头 = 把 SHE 塞进白色球泡里 + 另一极直接接触水样。这个类比消除了"教科书装置"与"野外读数"之间的距离感。

**(5) 对数运算的口头提示**
老师在 Cu 算例里两次停下来提醒：
- log(A/B) = log A − log B（用来把水稳定线里的除号拆开，让 −log[H⁺] 变成 pH）；
- 由 0.68 = −log(x) 得 x = 1/10^0.68 —— "it's one of those rules of logs you just have to accept."
这两条是本周计算题的全部数学工具。

**(6) 先定性、再定量的解题习惯**
Cu 算例里，老师**先**比较 0.20 V 与 0.16 V 得出"应以 Cu²⁺ 为主"，**再**用能斯特方程算出 0.21。考试时先写这一句定性判断，既能防止代错方向，又能拿到解释分。

### 4.4 老师口头澄清的四个误解

课堂上老师针对性地纠了四个直觉错误——**这四条正是 §6.5 表格的来源，此处只列老师的原话依据**：

1. **"氧化 = 与氧反应"** —— "Anything that can either give up or take electrons can do that job of oxidizing."（地表是 O₂，深部换成 N、Mn、Fe、S）
2. **"深部还原，所以深部一定酸/一定碱"** —— "The pH is not as well defined as pE in that sense … both can have either alkaline or acidic conditions. **It just depends what else is present.**"
3. **"反应序列到哪儿都一样"** —— 垃圾填埋场因无天然流场、含氧地下水下渗，序列**可能上下颠倒**："you kind of get methanogenesis near the surface and then flow of groundwater causes oxidation from oxygen at depth."
4. **"15 orders of magnitude = 15 倍"** —— "It's **not 15 times, 15 zeros**."

### 4.5 Green River 案例：幻灯片上没有、只在录音里的细节

§2.10 已给出案例主线，以下是**只有听录音才知道**的判读要点：

- 幻灯片右侧 Eh–pH 图上的**颜色是特意与左侧野外照片对应的**：棕色域 = 赤铁矿，浅色域 = ankerite/dolomite 碳酸盐；**图上那个小黑方块就是实测流体的 (pH, Eh)**——这是"把实测点画上图再读稳定域"这一标准流程的完整演示；
- 左图是**岩壁横剖面**，中间的裂缝是**断层，充当流体通道**；流体在地表溢出时**冒 CO₂ 气泡**并就地沉淀碳酸盐；
- 薄片横跨漂白/未漂白界面，可见**次生碳酸盐**与少量次生氧化物，**Co、Cu 浓度在界面处出现尖峰**；
- 老师的收束句："It's not just water flowing through a rock. It's water flowing through a rock that's **dissolving some minerals and precipitating other ones**." —— 强调这是**动态开放体系**，不是静态平衡。

### 4.6 课堂 Kahoot 测验（12 题）——答案与讲评

文件 `lecture 9 quiz answers 2024.md` 的 OCR 质量较差，以下答案由 OCR 中的 ✓/✗ 标记与课堂录音中老师的口头讲评**共同**确定。

| # | 题目 | 答案 | 依据 / 讲评 |
|---|---|---|---|
| 1 | Oxidation is …？ | **失去电子（loss of electrons）** | 老师："It's the acronym. Do you remember the acronym? … Oxidation is los[s] electrons." |
| 2 | 中性原子的氧化态？ | **0** | 全班答对 |
| 3 | CO₃²⁻ 中 O 的氧化态？ | **−2** | "oxygen is almost always two minus oxidation state" |
| 4 | CO₃²⁻ 中 C 的氧化态？ | **+4** | 老师现场推：3×(−2) = −6，总电荷 −2 ⟹ C = +4。**本题正确率明显下降** |
| 5 | Cu²⁺(aq) + 2e⁻ → Cu⁰(s) 中铜是？ | **被还原（reduced）** | 得电子 |
| 6 | Fe(OH)₃ 中 Fe 的氧化态？ | **+3** | 3 个 OH⁻ 各 −1 |
| 7 | 化学方程式配平的条件是？ | **原子（质量）与电荷都平衡** | 老师："Drive the point home, I think."——这题就是为了钉死 §2.5 那个考点 |
| 8 | Eh 相对哪种元素测量？ | **氢（hydrogen, SHE）** | "hydrogen, the standard hydrogen electrode" |
| 9 | 能斯特方程用来做什么？ | **量化氧化态（quantify oxidation states）** | 老师排除法：计算解离度和预测 pH 那两个是 **Henderson–Hasselbalch 方程**（W08 内容）干的活；"quantify the number of electrons" 也错 |
| 10 | 哪些元素控制地下的 Eh？ | **硫与铁（S、Fe）；地表则是 O** | 幻灯片："In most natural waters redox conditions are controlled by **oxygen, sulphur and iron**"；老师补充地下含氧少但仍有一些。**录音中该题选项的 OCR 与转写均不完整，具体选项材料未说明** |
| 11 | 地下水出露地表沉淀矿物，主因是？ | **被大气 O₂ 氧化（oxidation by atmospheric O₂）** | 老师："Most of you got that." |
| 12 | 泥炭沼泽（peat bogs）倾向于？ | **低 pE 且低 pH** | 幻灯片："environments isolated from the atmosphere (e.g. peat bogs)" 有较低 pE；录音中老师最终答"low"。📎 背景补充：泥炭沼泽同时酸性（腐殖酸、有机酸）且还原（隔绝大气 + 有机质耗氧），故**两者都低** |

---

## 五、Practical 要点

**本周 practical 时段 = Experiment 2 的写作课（write-up）。** Experiment 2 的标题是 **BUFFERS AND INDICATORS（缓冲液与指示剂）**，实验在上周做，本周提交/讲评。以下依据 `practical 2 post lab answers 2.md` 逐题重建。

### 5.0 实验背景（用于理解答案）

> 📎 背景补充（装置与流程来自 Week 8 的 `EART26201 lab handbook 2025-1.md` 中 Experiment 2 章节；答案文件本身没有复述，但不知道流程就看不懂答案）：
> - **校准 pH 计**：pH 7 缓冲液校到 7.0 ± 0.2 → pH 4 缓冲液校到 4.0 ± 0.2 → 回 pH 7 复检；
> - **缓冲能力实验**：取 100 mL 的（pH 7 或 pH 4 缓冲液）与（去离子水或自来水）各一份，加 4 滴筛选甲基橙，用 **0.1 M HCl** 以约 0.5 mL 增量滴定、**共加 5 mL**，每次记录 pH、读数、pH 稳定所需时间与颜色变化；
> - **强碱–强酸滴定**：**100 mL 0.01 M NaOH** + 2 滴酚酞，用 **0.1 M HCl** 滴定；pH < 10.7 后改 0.1 mL 增量，酚酞褪色后加 4 滴甲基橙续滴至 pH < 3；作 pH–体积曲线与缓冲能力–pH 曲线。

### 5.1 第 1 问：自来水和去离子水，哪个是更好的缓冲液？

**答案：自来水（tap water）。**

**给出的数据与算法：**

| 溶液 | 加 5 mL 0.1 M HCl 后的 pH 变化速率 | 缓冲能力 |
|---|---|---|
| 自来水 | **0.7 pH 单位 / mL HCl** | 较高 |
| 去离子水 | **1.4 pH 单位 / mL HCl** | 较低 |

**结论**：两者加入的 HCl 量相同，但自来水 pH 变化只有一半 ⟹ **自来水的缓冲能力是去离子水的两倍**。

**机理解释（评分点）：**
- 去离子水中 HCl **几乎完全解离**为 H⁺ 和 Cl⁻，水里**没有任何能与 H⁺ 反应的物种**，所以 H⁺ 全部体现为 pH 下降；
- 自来水成分虽未知，但**很可能含有溶解物种（碳酸盐 / 碳酸氢盐 carbonate / bicarbonate）**，它们会消耗掉一部分 H⁺，从而减小 pH 变化。

> 📎 背景补充：**缓冲能力（buffer capacity）的严格定义**是 β = dC_b/dpH（加入单位量强碱/强酸所引起的 pH 变化的**倒数**，单位 mol L⁻¹ per pH unit）。答案里用的"每 mL 引起的 pH 变化"是它的**倒数型代用量**——数值越小缓冲越强。答题时说清方向（越小越强）就不会失分。
> 📎 背景补充：自来水的缓冲主要来自 **HCO₃⁻ + H⁺ → H₂CO₃（→ CO₂ + H₂O）**，正是 W08 碱度（alkalinity）那一课的内容——这也是为什么这个实验安排在 W08–W09 之间。

⚠️ **答案里一处表述不严谨**（也是常见扣分点）：原文写 "tap water and deionised water **absorbed the same amount of H+ and OH- ions**"。实际情况是**两者被加入了等量的 HCl**，但**被消耗/中和掉的 H⁺ 量并不相同**——恰恰是自来水消耗得更多，才导致 pH 变化更小。见勘误表第 14 条。

### 5.2 第 2 问：0.01 M NaOH 用 0.1 M HCl 滴定，终点（end-point）的意义？如何用滴定测未知 NaOH 浓度？

**终点的意义**：终点标志 **0.01 M NaOH 溶液不再能缓冲 pH**。实验现象是 pH **从碱性的 9.7 骤降到强酸性的 3.7**。**所有 OH⁻ 被消耗完、且无过量 H⁺ 时的 pH 是 7。**

**测未知 NaOH 浓度的做法（完整逻辑链）：**
1. 用**已知浓度**的 0.1 M HCl 逐渐滴入**已知体积**的未知浓度 NaOH；
2. 记录到达终点时消耗的 HCl 体积；
3. **n(HCl) = c(HCl) × V(HCl)**；
4. 本反应中 **HCl : NaOH = 1 : 1**，故 **n(NaOH) = n(HCl)**；
5. **c(NaOH) = n(NaOH) / V(NaOH 初始体积)**，单位 mol/L。

> 📎 背景补充：0.01 M NaOH 的**理论** pH = 14 − pOH = 14 − 2 = **12**，而实测起点只有 **9.7**。这个差值通常来自**溶液吸收了大气 CO₂**（生成碳酸/碳酸氢根中和了部分 OH⁻），以及配液与电极的误差。报告里若能主动指出这一点，是加分项——而且它直接呼应第 6 问"低缓冲能力样品的 pH 不可靠"。
> 📎 背景补充：**终点（end-point）** 与**等当点（equivalence point）** 是两个概念——等当点是化学计量恰好相等的那一点（此处 pH = 7），终点是**指示剂实际变色的那一点**。选对指示剂就是为了让两者尽量重合，这正是第 4 问要问的。

### 5.3 第 3 问：两种指示剂的变色 pH 范围（实测）

| 指示剂 | 实测变色范围 |
|---|---|
| **甲基橙 methyl orange** | **pH 2.9 – 4.6** |
| **酚酞 phenolphthalein** | **pH 8.3 – 10.0** |

> 📎 背景补充：实验手册给出的参考值是——筛选甲基橙 pH < 3.1 红色、pH > 4.4 黄色（即 **3.1–4.4**）；酚酞 0–8.3 无色、8.3–10 粉至品红、>10 又变无色（即 **8.3–10**）。可见**酚酞的实测与手册完全一致**，**甲基橙实测范围略宽（2.9–4.6 vs 3.1–4.4）**。这属于实测偏差（增量太粗、目视判色主观、指示剂浓度），不是错误，但报告里应当说明。另外注意酚酞在 **pH > 10 时会重新褪成无色**，是个经典陷阱。

### 5.4 第 4 问：为什么溴百里酚蓝（bromo-thymol blue）更适合定这个滴定的终点？

**已知**：溴百里酚蓝在 **pH 6.0–7.6** 由（酸性）黄变（碱性）蓝。

**答案**：因为**它的变色范围正好跨过本滴定的终点 pH**。理由链条：
- 本滴定是**强酸 + 强碱**：acid + base = salt + water；
- 生成的盐（NaCl）**不水解**，所以**等当点 pH = 7**；
- 7 落在 6.0–7.6 之内 ⟹ 指示剂变色与等当点重合 ⟹ 读数最准。

（相比之下：酚酞 8.3–10.0 会**提前**变色，甲基橙 2.9–4.6 会**滞后**变色，都会带来系统误差。）

### 5.5 第 5 问：100 mL 0.1 M NaOH + 100 mL 0.1 M HCl 的混合液是好缓冲液吗？

**答案：不是，是很差的缓冲液（poor buffer）。**

**理由**：acid + base = salt + water。两者**物质的量相等**（各 0.1 mol/L × 0.1 L = **0.01 mol**），**完全中和**，产物只剩 NaCl 和水，**没有任何剩余的缓冲潜力（no buffering potential left）**。

> 📎 背景补充：把这题讲透的说法是——**缓冲液必须同时含有一对共轭酸碱（弱酸 + 其盐，或弱碱 + 其盐）**，才能双向吸收 H⁺ 与 OH⁻。这里既没有弱酸也没有弱碱（HCl 和 NaOH 都是强的），中和产物 Na⁺ 和 Cl⁻ 都不水解，所以缓冲能力为零。这一点与实验手册前言里的 0.1 M 醋酸 / 0.1 M 醋酸钠缓冲液（pH = pKa = 4.74）形成直接对照。

### 5.6 第 6 问：低/高缓冲能力的地下水样，哪个测得的 pH 更能代表原位 pH？

**答案：缓冲能力高的样品。**

**理由**：它**更有韧性（more resilient）**，取样和运输过程中的扰动不容易改变其 pH。答案给的具体情景很好用：**如果实验人员对着水样呼气，引入 CO₂ 生成碳酸**，高缓冲能力的样品仍能维持采样时的 pH；低缓冲能力的样品因为"没有离子提供缓冲"，pH 会明显漂移。

> 📎 背景补充：这题是整份 post-lab 里**唯一直接的地球化学应用题**，也是最像考题的一题。可以再补两条现场理由：低缓冲水样还容易因**脱气（CO₂ 逸出会使 pH 升高）**、**温度变化**、**Fe²⁺ 氧化沉淀产酸** 而漂移。实践上的对策是**现场原位测 pH**，而不是带回实验室测。

### 5.7 从答案反推的评分标准

综观六道题的参考答案，评分明显看重四件事：

1. **必须给出数值证据**——第 1 问只说"自来水更好"不够，要给出 0.7 vs 1.4 和"两倍"这个比值；
2. **必须给出机理，不能只给现象**——"因为自来水含碳酸盐/碳酸氢盐能消耗 H⁺"才是得分句；
3. **必须写清完整的计算逻辑链**——第 2 问要把 n = cV、1:1 化学计量、c = n/V 三步都写出来；
4. **必须回到地球化学语境**——第 6 问的野外采样含义、第 1 问的天然水缓冲机制，都是把实验接回课程主线的地方。

常见错误（从答案的措辞可反推出）：把"加入的酸量"与"被中和的酸量"混为一谈（§5.1 ⚠️）；把终点与等当点混用；忘记指出强酸强碱滴定的等当点恰为 pH 7；把"缓冲能力"的大小方向说反。

---

## 六、易错点 / 重点难点

### 6.1 Eh 与 pE 混用而忘换算 ★最高频

- 能斯特方程 **pE = pE⁰ − (1/n)·log([Red]/[Ox])** 中**所有量都是 pE，不是 Eh**。
- 表里查到的是 **E⁰（伏特）**，实测探头给的也常是 **Eh（伏特/毫伏）**，**必须先各自 ×16.9 换成 pE⁰ 和 pE**。Cu 算例里 0.16 → 2.70、0.20 → 3.38 就是这一步。
- 反向常见错误：把 16.9 记成 1/16.9 = 0.059，或者只换算了一个量而忘了另一个（这会让答案偏差整整一个 16.9 倍）。
- **单位陷阱**：储层案例给的 Eh 是 **0 到 −50 mV**，是**毫伏**！先化成 −0.05 V 再乘 16.9，否则差 1000 倍。
- **温度陷阱**：16.9 与 0.0592 只在 **25 °C** 成立。

### 6.2 电位符号约定的坑

- 幻灯片的规则是"负电位向右自发"，通用（IUPAC）规则是"**E°cell 为正才向右自发**"，两者**符号相反、数值相同**。
- 稳妥做法：**用 ΔG = −nFE 定锚**。E 正 ⟹ ΔG 负 ⟹ 自发。写答案时把用的约定说清楚。
- 另一个坑：**把半反应反写时 E⁰ 要变号**，但**乘以化学计量系数时 E⁰ 不变**（E⁰ 是强度量，不是广延量）。这一点材料未提，但很容易被考。
- 幻灯片两页对 Cu–Zn 反应写了**相反的方向**（Cu⁰ + Zn²⁺ vs Zn + Cu²⁺），只是演示需要，不代表两个方向都自发。

### 6.3 能斯特方程里 n 取错、比值方向写反

- **n 是该半反应转移的电子数**，必须从**配平后的半反应**读出，不是元素价态的绝对值。
  - Cu⁺ ⇌ Cu²⁺ + e⁻ ⟹ **n = 1**；
  - Mn⁴⁺ + 2e⁻ ⇌ Mn²⁺ ⟹ **n = 2**；
  - Fe²⁺ ⇌ Fe³⁺ + e⁻ ⟹ **n = 1**（不要因为"从 +2 到 +3"就写 3）。
- **log 里是 [Red]/[Ox]（还原态在上）**，前面是**减号**。老师原话："it has a log term and **a ratio of reduced to oxidised**"。写反了会得到互为倒数的答案（0.21 变成 4.8）。
- 快速自检：**pE 越高（越氧化）⟹ [Red]/[Ox] 越小**。若算出"水更氧化却还原态更多"，一定写反了。

### 6.4 Eh–pH 图判读的三类错误

1. **斜率判错**：记住 **斜率 = −m/n**（m 为 H⁺ 数，n 为 e⁻ 数）。
   - **只有 e⁻ 没有 H⁺ ⟹ 水平线**；
   - **只有 H⁺ 没有 e⁻ ⟹ 垂直线**（这类边界压根不是氧化还原反应，只是水解/酸碱平衡，pE 高低对它没影响）；
   - **m = n ⟹ 斜率 −1，与水稳定线平行**。
2. **忘了水稳定域**：任何落在上限之上或下限之下的点在天然水中**不存在**（水会自己被氧化放 O₂ 或被还原放 H₂）。地表水几乎贴着上限（因为 P(O₂) = 0.21 只比纯氧低 0.17 个 pE 单位）。
3. **忘了图的浓度前提**：矿物–溶液边界的位置依赖于假定的溶解物种活度（常取 10⁻⁶）。看图先看图注，否则会把"某矿物稳定域很大"当成绝对结论。

### 6.5 概念性混淆

| 错误说法 | 正确理解 |
|---|---|
| "还原环境 = 缺氧" | 缺氧只是"没有 O₂ 这个氧化剂"。还原程度是连续的：反硝化带、锰还原带、铁还原带、硫酸盐还原带、产甲烷带的 pE 依次降低，都叫"缺氧"，但氧化还原状态差很远。幻灯片对 anoxic water 的定义更严格：**同时含溶解 Fe 和硫化物**。 |
| "氧化 = 和氧反应" | 氧化 = 失电子。深部由 N、Mn、Fe、S 充当氧化剂。 |
| "深部一定酸性 / 一定碱性" | pE 随深度系统降低，但 **pH 不随深度系统变化**——地表和深部都能酸也能碱，取决于有黄铁矿（产酸）还是碳酸盐（产碱度）。 |
| "Eh–pH 图预测会沉淀就一定会沉淀" | 幻灯片明写 "**thermodynamically stable but may be limited by kinetics**"。动力学障碍导致的**非平衡态**在天然水中非常普遍（典型如常温下有机质与 O₂ 共存、SO₄²⁻ 还原需要微生物催化才有可观速率）。这也解释了为什么很多天然水根本**没有单一的、各氧化还原对彼此一致的 pE**——探头测的往往是混合电位。 |
| "反应序列一定是从上到下 O→N→Mn→Fe→S→CH₄" | 天然沉积物是这样；**垃圾填埋场可能上下颠倒**，因为含氧地下水循环把氧带到深部。 |
| "15 orders of magnitude = 15 倍" | 是 **10¹⁵ 倍**。 |

### 6.6 配平的顺序错误

必须按 **①非 O/H 原子 → ②加 H₂O 配 O → ③加 H⁺ 配 H → ④加 e⁻ 配电荷** 的顺序。先加电子会导致后面加 H⁺ 时电荷又乱掉。做完**一定要两边点一次总电荷**（Fe–Mn 例子里两边都是 +4）。

### 6.7 氧化态计算的边界情况

- O 是 **"almost always" −2**，不是绝对——过氧化物（H₂O₂ 中 O 为 −1）和 OF₂ 是例外。材料用了 "almost always" 这个措辞，说明老师知道有例外但不打算展开。
- 计算多原子离子时，**总和等于该离子的净电荷，不是 0**（CO₃²⁻ 要等于 −2，不是 0）——Kahoot 第 4 题正确率下降就是栽在这里。

---

## 七、本周术语表

| 英文 | 中文 | 说明 / 本周关键点 |
|---|---|---|
| Redox (reduction–oxidation) reaction | 氧化还原反应 | 涉及氧化态改变的反应 |
| Oxidation | 氧化 | **失电子**（OIL） |
| Reduction | 还原 | **得电子**（RIG） |
| OIL RIG | 助记词 | Oxidation Is Loss, Reduction Is Gain |
| Oxidizing agent | 氧化剂 | **接受**电子，自身被还原 |
| Reducing agent | 还原剂 | **给出**电子，自身被氧化 |
| Oxidation state / number；redox state / number | 氧化态 / 氧化数 / 氧化还原态 | 拆散分子后各原子应带的电荷；单质为 0，O 通常 −2，H 为 +1 |
| Redox couple / redox pair | 氧化还原对 | Ox₁–Red₁ 与 Ox₂–Red₂ 成对出现 |
| Half-reaction | 半反应 | 分开写的氧化半反应与还原半反应 |
| Oxidation half-reaction | 氧化半反应 | 电子写在**产物**侧 |
| Reduction half-reaction | 还原半反应 | 电子写在**反应物**侧 |
| Electrochemical cell | 电化学电池 | 两电极 + 导线 + 伏特计 + 盐桥 |
| Salt bridge | 盐桥 | 连通两半电池、维持电荷平衡 |
| Electromotive force (emf) | 电动势 | 电池两极的电位差，以伏特计量 |
| Standard Hydrogen Electrode (SHE) | 标准氢电极 | 一切电位的**零点基准**；a(H⁺) = 1 |
| Electromotive series | 电动序 | 各半反应 E⁰ 的排序表；强还原剂在顶，强氧化剂在底 |
| Standard electrode potential, E⁰ | 标准电极电位 | 材料给值：Zn/Zn²⁺ −0.76 V；Cu/Cu²⁺ +0.34 V；Cu⁺/Cu²⁺ +0.16 V |
| Eh (oxidation potential / redox potential) | 氧化还原电位 | 溶液相对 SHE 的电位，单位 V/mV；**pH 的氧化还原对应物** |
| pE (pe) | 电子活度指数 | pE = −log[e⁻]；**pE = 16.9 Eh**（25 °C） |
| Electron activity | 电子活度 | 形式量——溶液中无自由电子 |
| Faraday constant, F | 法拉第常数 | 1 mol 电子的电量；96485 C mol⁻¹（幻灯片写 96420） |
| Nernst equation | 能斯特方程 | pE = pE⁰ − (1/n) log([Red]/[Ox])；用于**量化氧化态比例** |
| Equilibrium constant, K | 平衡常数 | pE⁰ = (1/n) log K |
| Speciation | 化学物种形态 / 物种分布 | 元素在溶液中以哪些形式、各占多少 |
| Predominance (field) | 优势（域） | 某物种占主导的 pE–pH 区域 |
| pE–pH / Eh–pH diagram | pE–pH 图 / Eh–pH 图 | 以 pH 为横轴、pE(Eh) 为纵轴的稳定域图 |
| Pourbaix diagram | 布拜图 | Eh–pH 图的别名（Marcel Pourbaix, 1904–1998） |
| Stability field | 稳定域 | 某矿物/物种在图上稳定存在的区域 |
| Stability limits of water | 水的稳定域上下限 | 上限 pE = 20.75 − pH（纯 O₂）；下限 pE = −pH（纯 H₂）；斜率均为 −1 |
| Oxic water | 含氧水 | 含可测溶解氧；雨水、海洋、溪流 |
| Anoxic / reducing water | 缺氧水 / 还原性水 | 幻灯片定义：**同时含溶解铁与硫化物** |
| Peat bog | 泥炭沼泽 | 与大气隔绝 ⟹ 低 pE（且通常低 pH） |
| Ferrous / Ferric | 亚铁（Fe²⁺）/ 高铁（Fe³⁺） | Fe²⁺ 溶解度比 Fe³⁺ 高约 **15 个数量级** |
| Iron hydroxide, Fe(OH)₃ | 氢氧化铁 | 矿区溪流"橙色淤泥"的成分 |
| Aerobic respiration | 好氧呼吸 | 序列第 1 步，O₂ 作氧化剂 |
| Denitrification | 反硝化作用 | 序列第 2、3 步，N（NO₃⁻）作氧化剂 |
| Manganese reduction | 锰还原 | 序列第 4 步，MnO₂（Mn⁴⁺）→ Mn²⁺ |
| Iron reduction | 铁还原 | 序列第 5 步，Fe(OH)₃/Fe³⁺ → Fe²⁺ |
| Sulphate reduction | 硫酸盐还原 | 序列第 6 步，SO₄²⁻ 作氧化剂 |
| Methane fermentation / methanogenesis | 甲烷发酵 / 产甲烷作用 | 序列第 7 步，直接由有机质产气 |
| CH₂O | 有机质的简写式 | 幻灯片与课堂中代表"最简单形式的有机碳" |
| Bacterially mediated | 细菌介导的 | 上述反应序列多由细菌催化并从中取能 |
| Bleached zone | 漂白带 | Green River 案例中赤铁矿被溶解后的浅色带 |
| Hematite | 赤铁矿 | Fe₂O₃；在还原性酸性流体中不稳定，被溶解 |
| Ankerite / dolomite | 铁白云石 / 白云石 | 在反应锋面沉淀的碳酸盐 |
| Reaction front | 反应锋面 | 漂白/未漂白界面；Co、Cu 浓度尖峰所在 |
| Immobilization (of trace metals) | （微量金属的）固定 / 不活化 | 反应锋面把金属从流体中取出并沉淀 |
| Caprock preservation | 盖层保存 | 储层完整性；CCS 与油气封存的关键 |
| Acid mine drainage | 酸性矿山排水 | 硫化物氧化产酸；本周应用之一 |
| Landfill leachate | 填埋场渗滤液 | 本周应用之一；反应序列可能上下颠倒 |
| Buffer capacity | 缓冲能力 | Practical 核心量；自来水约为去离子水的 2 倍 |
| End-point / equivalence point | 滴定终点 / 等当点 | 强酸强碱滴定的等当点 pH = 7 |
| Methyl orange | 甲基橙 | 实测变色 pH 2.9–4.6 |
| Phenolphthalein | 酚酞 | 实测变色 pH 8.3–10.0 |
| Bromo-thymol blue | 溴百里酚蓝 | pH 6.0–7.6 变色，最适合本滴定 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| 1. `lecture 9 redox 2025-1.md`，"Redox potential" 页 | "Zn = Zn²⁺ + 2e = −0.76 volt；Cu = Cu²⁺ + 2e = +0.34 volt；Subtract: −0.76−0.34 = −1.10 volt。Any reaction with a **negative** potential will go to the right." | ①半反应写成**氧化**方向却用了**还原**电位数值（若真按氧化方向写，Zn 的值应为 +0.76 V）；②"负电位向右自发"与 IUPAC/热力学通用约定**符号相反** | 通用约定：E°cell = E°(阴极) − E°(阳极) = +0.34 − (−0.76) = **+1.10 V**；ΔG° = −nFE°，**E° 为正 ⟹ 自发向右**。数值大小 1.10 V 无误，仅符号约定不同。答题时明确声明所用约定即可 |
| 2. 同上，"pE/pH diagrams: Fe–H₂O system" 页 | "pE = 20.75 − log(0.21)^¼ − pH = 13.58 @ pH = 7" | 按字面计算：log(0.21^¼) = −0.17，"20.75 − (−0.17) − 7" = **13.92**，与所给答案 13.58 不符 | **13.58 是正确结果**；正确写法应为 **pE = 20.75 + ¼·log P(O₂) − pH = 20.75 − 0.17 − 7 = 13.58**。即该行的减号位置有误，结论无误 |
| 3. 同上，"Oxidation potential, Eh" 页 | "F = **96420** J volt⁻¹ eq⁻¹" | 法拉第常数数值有误 | 应为 **96485 C mol⁻¹（≈ 96485 J V⁻¹ eq⁻¹）**。对两位有效数字的换算系数 16.9 无影响（用 96420 算得 16.90，用 96485 算得 16.90） |
| 4. 同上，"Nernst Equation" 页 | 该页图片文字中比值方向出现两种写法：一处为 "log(Red/Ox)"，另一处为 "log(Ox/Red)" | 同一页内比值方向自相矛盾（很可能是 PDF 转文字时的排版错乱） | **正确形式为 pE = pE⁰ − (1/n)·log([Red]/[Ox])**。依据：课堂原话 "a ratio of reduced to oxidised"，且 Cu 算例用的正是 log([Cu⁺]/[Cu²⁺]) |
| 5. 同上，"Redox systems" 页 vs "Redox potential" 页 | 前页写 "Cu⁰(s) + Zn²⁺(aq) ⇌ Cu²⁺(aq) + Zn⁰(s)"；后页写 "Zn + Cu²⁺ ⇌ Zn²⁺ + Cu" | 两页对同一体系写了**相反的反应方向** | 标准态下自发方向是**后者**（Zn + Cu²⁺ → Zn²⁺ + Cu，E°cell = +1.10 V）。前页只是用来演示"如何拆半反应"的形式写法，不表示该方向自发 |
| 6. 同上，"Redox reactions" 页 | "Reduction MnO + 2e⁻ ⇋ Mn²⁺ + 2H O 2 + 4H⁺ 2" | 化学式与配平项被排版打乱（下标丢失、项序错位） | 应为 **MnO₂ + 4H⁺ + 2e⁻ ⇌ Mn²⁺ + 2H₂O**。后续合并结果 2Fe²⁺ + MnO₂ + 4H₂O ⇌ 2Fe(OH)₃ + 2H⁺ + Mn²⁺ 正确（两边电荷均为 +4，已核算） |
| 7. 同上，"Redox or oxidation state" 页 | "SO42-, CO32-, **NO3** (electron acceptors = oxidising agents)" | 硝酸根缺少电荷 | 应为 **NO₃⁻** |
| 8. 同上，"Eh and pE" 页 | "pE 169.Eh  Eh .0059 pE" | OCR/排版致小数点错位 | 应为 **pE = 16.9 Eh**、**Eh = 0.059 pE**。数值本身正确（F/2.303RT = 16.90；1/16.9 = 0.0592） |
| 9. `EART26201 - 01-Dec-transcript.md`，pE/Eh 换算段 | "pH and PE are related … such that **PE is 16.9 times pH** … so **high pH is the same as high PE**" | 语音转写把 **Eh** 听成 **pH**（连错两处） | 应为 "**pE is 16.9 times Eh**"、"**high Eh is the same as high pE**"。以幻灯片为准 |
| 10. 同上，Kahoot 第 10 题 | "Which of these elements controls **pH** in subsurface" | 同样是 Eh/pH 转写混淆 | 应为 "**controls Eh in the subsurface**"（`lecture 9 quiz answers 2024.md` 的 OCR 版本作 "control Eh in the subsurface"，以此为准） |
| 11. 同上，Pourbaix 图介绍段 | "called Pourbaix diagrams after a **French** guy called Marcel Pourbaix" | 国籍有误 | Marcel Pourbaix（1904–1998）是**比利时**化学家（生于俄国 Myshega）。幻灯片只给了生卒年、未给国籍，无误 |
| 12. 同上，全文 | "MANTOR / Mantoor"、"anchorite"、"SHG"、"Henson-Hasselbal"、"string"（多处）、"iron"（在应为 ion 处） | 自动语音转写的固有拼写错误 | 分别应为 **Mam Tor**（英国峰区著名滑坡与黄铁矿风化点）、**ankerite**（铁白云石）、**SHE**（standard hydrogen electrode）、**Henderson–Hasselbalch**（W08 的方程）、**stream**（溪流）、**ion**（离子） |
| 13. `lecture 9 quiz answers 2024.md`，文件名 vs 幻灯片首页 | 文件名标 "**2024**"，Slide 1 的 OCR 文字为 "Lecture 9 **2023**" | 年份标注不一致 | 属版本沿用，不影响题目内容。另本文件整体 OCR 质量低（Slide 2 明确标注"识别质量低"），题目选项多不可读，本笔记 §4.6 的答案是结合课堂录音讲评还原的，个别选项文本**材料未说明** |
| 14. `practical 2 post lab answers 2.md`，第 1 问第 1 段 | "So, tap water and deionised water **absorbed the same amount of H⁺ and OH⁻ ions**, but tap water saw less of a pH change." | 表述与自己的结论矛盾——若吸收量相同，pH 变化就该相同 | 应为"**两者被加入了等量的 HCl（5 mL 0.1 M）**，但自来水中的碳酸盐/碳酸氢盐**消耗掉了更多 H⁺**，故 pH 变化较小"。结论（自来水缓冲能力约为 2 倍）正确 |
| 15. 同上，第 3 问 | "Methyl orange changes from 2.9 pH – 4.6 pH" | 与 Week 8 实验手册给出的筛选甲基橙参考范围（< 3.1 红、> 4.4 黄，即 3.1–4.4）不一致 | 这是**实测值**而非笔误，不算错误；但报告中应说明偏差来源（滴定增量偏粗、目视判色主观）。酚酞的 8.3–10.0 与手册完全一致 |
