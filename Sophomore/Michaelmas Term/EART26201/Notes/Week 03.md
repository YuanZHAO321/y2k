# EART26201 Principles of Geochemistry — Week 03 学习笔记

## 一、本周主题

**本周主题：地球化学体系中的反应——热力学与相图原理（Reactions in geochemical systems: thermodynamics and phase diagram principles）。**

这个判定来自三处互相印证的材料证据，而**不是**来自文件名或课程大纲：

1. 幻灯片 `EART26201_Lecture3-1_RT-1.md` 的 Slide 1 标题原文即为 "Reactions in geochemical systems: thermodynamics and phase diagram principles"，并标注 "EART26201 | Principles of Geochemistry | Lecture 3"。
2. 课堂录音转写（13-Oct）开场原话："Welcome to week three of this geochemistry course, and today, we're going to be talking about everybody's most favorite topic, **thermodynamics and phase diagrams**."
3. Practical 3 的 feedback 标题原文为 "**Introduction to phase diagrams** FEEDBACK"。

> ⚠️ **本周与放射性同位素定年无关。** 预处理阶段曾推测 Week 03 可能讲放射性同位素定年（等时线 isochron 之类），**材料证明这个推测是错的**。本周整节课没有出现任何核素、半衰期、衰变常数或等时线图；相应地，本笔记「三、公式与图表」中不包含等时线图解，「附：材料勘误表」中也无需核对母子体对应关系。

**周次错位说明。** 课程大纲（`(EART26201) Principles of Geochemistry.md`）把本内容列在 "Week 4: Reactions in geochemical systems: thermodynamics and phase diagram principles"，把 "Isochron dating (PC based)" 列在 Practical Week 3。但**实际文件夹 Week 3 的讲义、录音、practical 三份材料全部指向热力学与相图**，且授课者本人口头称之为 "week three"、幻灯片称之为 "Lecture 3"。大纲的周次是学期周（从 Week 2 开课），文件夹周次是授课周（从 Week 1 连续），二者相差 1：**文件夹 Week N ≈ 大纲 Week N+1**。本笔记库统一采用文件夹编号，故这是 Week 03。

**在全课四大块骨架中的位置。** EART26201 的四大块是：**（1）热力学与相图 →（2）反应动力学与扩散 →（3）酸碱溶解度与氧化还原 →（4）放射性与稳定同位素**。本周正是**第一块「热力学与相图」的开篇与理论地基**：它先把热力学的语言（体系、状态变量、四个基本量 U/H/S/G）搭起来，再落到相图这个「热力学的图形化表达」上，最后用二元固溶体相图（斜长石）把理论接回岩石学。

课程内部的前后关系（材料明确写出）：
- **回指 Lecture 1**（Slide 24 原文 "Think back to Lecture 1: element partitioning and Goldschmidt's Rules"；转写中"from the first week we discussed equilibrium and fractional processes"）——平衡/分离过程和元素分配的概念在第 1 周已铺垫。
- **前指 Lecture 4**（Slide 20 原文 "We'll look at this phase diagram again in Lecture 4"；转写 "we'll get back to this one next week as well"）——An–Di 共结相图下周细讲，即大纲的 "Melting and crystallisation: phase diagram applications"。
- **前指 Lecture 5**（Slide 30 原文 "We'll consider kinetics and disequilibrium in Lecture 5"；转写 "The final lecture I do with you will actually look into disequilibrium processes"）——本周全部建立在**平衡假设**上，失衡与动力学留到第二块。
- **辐射到其他课**：Practical feedback 原文 "You will revisit many of these themes in **EART22200 (Igneous Minerals and Processes)** and **EART24200 (Metamorphic Minerals and Processes)** later in the year."

📎 背景补充：授课人身份材料未在讲义中直接写明，但 Practical 3 feedback 的页眉署名为 **Dr David Neave**，而课程大纲的 unit coordinator 是 Greg Holland。结合转写中"The final lecture I do with you"（我给你们上的最后一节课）的说法，本课很可能由两位老师分段授课，Neave 负责前半段（高温地球化学、热力学与相图），Holland 负责后半段。这是推断，材料未明说。

---

## 二、核心概念

### 1. 平衡（equilibrium）与失衡（disequilibrium）

**定义（Slide 3 原文）**："Equilibrium is reached when constituents of a system do not change with time." 即**体系的各组成部分不随时间变化**时，体系达到平衡。

这个定义看似平凡，但它是整节课的前提：**热力学只描述平衡态**（转写原话 "Thermodynamics, it's only relating to equilibrium processes"）。热力学告诉你体系**最终会走向哪里**，但不告诉你**多快到达**——那是动力学（kinetics）的事，留到 Lecture 5。

地球体系里的典型例证（Slide 3–4 + 转写）：
- 玄武质岩浆（basaltic magma）在**地幔条件**（高温高压）下，平衡态是**液态**；
- 同样的成分在**地表条件**下，平衡态是**固态**；
- 因此，**结晶作用（crystallisation）本质上就是热岩浆与较冷环境的再平衡过程**（"Crystallisation reflects the re-equilibration of hot magmas with cooler surroundings"）。

**熔岩湖是失衡的活标本**：夏威夷 Halemaʻumaʻu 熔岩湖（2018 年喷发前）是"out of equilibrium"，因为岩浆在地表本该是固体。转写解释："If they're not replenished, they will slowly crystallize, they will cool down... because they want to reach equilibrium."（若无岩浆补给，它们会慢慢冷却结晶，因为它们"想要"达到平衡。）Makaopuhi 熔岩湖 1965 年的结晶过程（Wright & Okamura, 1977）则是"approaching equilibrium"（趋近平衡）的例子。

### 2. 体系（system）——由你自己定义

转写强调：**system 是人为任意界定的**，取决于你要回答什么问题。可以是一颗矿物颗粒（mineral grain）、一个岩浆房（magma reservoir）、同一花岗岩体中的若干岩石、一整颗行星，甚至整个太阳系。

📎 背景补充：热力学中通常还把体系分为**开放体系**（open，与外界既交换物质又交换能量）、**封闭体系**（closed，只交换能量）与**孤立体系**（isolated，两者都不交换）。本周材料没有引入这组分类，但它是理解"体系与环境（surroundings）"这对概念的标准框架。

### 3. 状态变量（state variables）：广度量 vs 强度量

这是本周最需要牢记的一组区分。

**广度量 / 广延变量（extensive variables）**：其数值**随体系大小改变**。
- 材料列举：质量 mass、体积 volume、焓 enthalpy (H)、熵 entropy (S)、自由能 free energy (G)。
- 直观检验：把体系一分为二，广度量也随之减半。

**强度量（intensive variables）**：其数值**与体系大小无关**。
- 材料列举：温度 temperature (T)、压力 pressure (P)、体相成分 bulk composition (X)。
- 直观检验：把一杯水倒掉一半，剩下的水温不变。

📎 背景补充：一个实用的记忆法是——**两个广度量相除得到强度量**（如 质量/体积 = 密度，Gibbs 自由能/摩尔数 = 摩尔自由能即化学势 μ）。这也是为什么 Gibbs 相律只统计**强度量**的自由度：相的数量和比例不影响强度量的自由度计数。

**重要提醒（转写反复强调）**：热力学中**温度必须用开尔文 K**，不能用摄氏度。"We're used to seeing temperature in Celsius or in centigrade, but don't forget to convert it to Kelvin."（注意：相图上的坐标轴常用 °C，这不矛盾——相图是读图，热力学公式代入才必须换算。）

**状态方程（equation of state）**把状态变量彼此联系起来。最著名的例子：**PV = nRT**（理想气体状态方程）。转写指出还有很多其他状态方程，这只是最有名的一个。

### 4. 热力学第一定律：能量守恒

**内能（internal energy, U）** = 体系的**动能**（来自原子振动 atomic vibration）+ **势能**（储存在原子间化学键中 stored in the bonds between atoms）。

第一定律：**能量既不能被创造也不能被消灭**。内能的变化 = 与环境交换的热 Q + 对体系做的功 W：

> ΔU = Q + W　→　微分形式　dU = dQ + dW

在地质体系中，功主要表现为**压力—体积功**，于是：

> **dU = dQ − P dV**

（负号的含义：体系**膨胀**时 dV > 0，体系对外做功，内能减少。）

### 5. 热力学第二定律：熵增

**熵（entropy, S）** 是体系**能量分布**的度量，也就是**无序度**的度量（转写原话："Entropy is a measure of the energy distribution of the system. So, in other words, it's a measure of disorder"）。

第二定律：**反应倾向于朝熵增的方向进行**。

> 可逆过程：dS = dQ / T
> 不可逆过程：dS > dQ / T
> **合并：dS ≥ dQ / T**

### 6. 第一、第二定律合并：热力学基本方程

把 dU = dQ − PdV 与 dQ ≤ T dS 合起来：

> **dU ≤ T dS − P dV**

对地质地球化学中绝大多数问题（按平衡/可逆处理），简化为等号：

> **dU = T dS − P dV**

转写对两项的物理解读（对应 Slide 12 的三个小标题）：
- **dU** —— change in internal energy（内能变化）
- **T dS** —— heat exchanged with surroundings（与环境交换的热）
- **−P dV** —— physical movement in space（体系在空间上的"物理运动"，即体积膨胀/收缩所做的功）

### 7. 焓（enthalpy, H）

**定义**：**H = U + PV**。焓是物质**总热含量（total heat content）**的量度。

**关键限制（转写强调）**：**焓的绝对值无法测量，只能测量焓的变化 ΔH**。

**恒压条件下**：

> **dH = dQ**（当 dP = 0 时）

即：恒压下体系吸收的热量全部体现为焓变——这就是为什么化学反应热（反应焓）一般都在恒压下定义。

（⚠️ 转写此处有一句物理表述错误，见文末勘误表第 4 条。）

### 8. 吉布斯自由能（Gibbs free energy, G）——本周的核心量

**定义**：**G = H − T S**

**物理含义**：在**恒温恒压**条件下，体系**可用于做功的能量**（"the energy available to do work at a constant temperature and pressure"）。

**判据（这是最需要背下来的一句）**：在 T、P 固定时，

- **ΔG < 0** → 反应**自发进行**，朝 G 更低的方向走；
- **ΔG = 0** → 体系处于**平衡**，**没有净反应**；
- （📎 背景补充：ΔG > 0 → 正向反应不自发，逆向反应自发。这一句材料未明说，是上面两条的自然推论。）

转写原话："Gibbs free energy describes whether a reaction will occur or not."——**G 决定反应发不发生（方向），不决定反应有多快（速率）**。

老师提醒："Hopefully, you've all heard about that last year in Chemistry of the Earth."（Slide 13 亦写 "This should be familiar from Chemistry of the Earth"）——这是大一课程的复习点。

### 9. 相图 = 吉布斯自由能的图形化表达

**这是本周把「理论」与「图」缝合起来的那一句**（转写原话）：

> "At any given pressure, temperature and composition of a system, the equilibrium phase or phase assemblage is the phase with the **lowest G**. And the phase diagrams, that's what they show us graphically."

也就是说：**相图上每一个点标注的那个相（或相组合），就是在该 P–T–X 条件下 G 最低的那个**。相图不是经验涂鸦，它是自由能竞争的结果。

### 10. 吉布斯相律（Gibbs phase rule）

> **F = C − Φ + 2**

- **F（也写作 f）= 自由度 / 方差（degrees of freedom / variance）**：在**不改变体系状态**（不改变相的数量与种类）的前提下，可以**独立改变的强度量个数**。
- **C = 组分数（components）**：描述体系中所有相所**必需的最少化学物种数**（"the minimum number of chemical species that you need to describe the phases of your system"）。例如 H₂O、SiO₂、MgO、FeO。
- **Φ（phi）= 相数（phases）**：物理上可区分的相的数量——熔体 melt、冰 ice、蒸汽 vapour、橄榄石 olivine、液体 liquid 等。
- **"+2" 的来历**：反映**通常只有 P 和 T 两个强度量可以自由变化**。

**"+2" 何时变成 "+1"**（本周考点）：
- **等压体系（isobaric）**：压力固定 → **F = C − Φ + 1**
- **等温体系（isothermal）**：温度固定 → **F = C − Φ + 1**

⚠️ 转写在总结这一点时把话说反了（说 "that number refers to how many intensive variables are **fixed**"），正确说法是这个数字指**可以自由变化**的强度量个数。见勘误表第 8 条。

**三类几何要素（用 H₂O 相图讲解）**：
| 位置 | Φ | F | 名称 |
|---|---|---|---|
| 相区内部（如液态水场） | 1 | 2 | **双变区 divariant field** |
| 相界线（如水–冰边界） | 2 | 1 | **单变线 univariant curve** |
| 三相点 | 3 | 0 | **不变点 invariant point** |

### 11. 杠杆定律（lever rule）

用来**定量计算两相共存时各相的比例**。

设体系总成分点位于 I，两个共存相 A（左）与 B（右）在同一等温线（tie line，连结线）上，a、b 为线段长度：

> **X_A = a / (a + b)**　　**X_B = b / (a + b)**　　**X_A + X_B = 1**

比例可以用**重量百分比 wt.%** 或**摩尔百分比 mol.%** 表示（Slide 21 原文 "Expressed in wt.% or mol.%"）。

⚠️ **方向是最大陷阱**：某一相的比例，等于**从体系成分点量到「对面那个相」的线段长度**除以总长——线段离哪一相越远，那一相越多。用 Practical 的数字验证见「三、公式与图表」第 6 条。

（老师在课上把 X_A + X_B 等于多少留作提问 "And XA plus XB equals what? This will come in on Wednesday"——答案是 1，即 100%。）

### 12. 平衡过程 vs 分离过程（equilibrium vs fractional processes）

Slide 23 原文（三种情形）：
- **平衡熔融 / 平衡结晶（equilibrium melting and crystallisation）**：**固体与液体始终保持相互平衡**，不断彼此调整成分。
- **分离熔融（fractional melting）**：熔体一旦形成就被**移出体系**，不再与残余固体平衡。
- **分离结晶（fractional crystallisation）**：晶体一旦形成就被**移出体系**，不再与残余液体平衡。

**两者的关键区别在于"什么是体系"**（转写讲得很清楚）：
- 平衡情形下，**体系的总成分始终不变**（成分点在图上不动，只是分成两相）；
- 分离情形下，**被移走的相不再算体系的一部分**，因此**体系成分点会沿相界线漂移**。

### 13. 固溶体（solid solution）与斜长石

**斜长石（plagioclase）是 钠长石（albite, Ab; NaAlSi₃O₈）与 钙长石（anorthite, An; CaAl₂Si₂O₈）之间的完全固溶体**。X_An = 1 表示 100% An + 0% Ab；X_An = 0 表示 0% An + 100% Ab；X_An = 0.5 表示各占一半。

Slide 24 提示 "Think back to Lecture 1: element partitioning and Goldschmidt's Rules"——固溶体之所以存在，是因为 Na⁺ 与 Ca²⁺ 离子半径相近可以互换（配合 Si⁴⁺↔Al³⁺ 的耦合替代维持电价平衡）。

📎 背景补充：斜长石的替代是**耦合替代（coupled substitution）**：NaSi ⇌ CaAl，即 Na⁺+Si⁴⁺ 同时被 Ca²⁺+Al³⁺ 取代，总电荷守恒。材料只提示"回想 Goldschmidt 规则"，没有写出这个替代式。

**斜长石为什么重要（Slide 28 + 转写）**——它几乎无处不在：
- 洋中脊玄武岩 / 大洋玄武岩（如冰岛）
- 大陆弧安山岩（andesite），常含大颗粒斜长石斑晶
- 大陆地壳岩石：麻粒岩（granulite）、花岗岩
- **行星尺度意义**：月球高地（Lunar Highlands）表面所有浅灰到白色的物质都是斜长石——**月球原始月壳由钙长石构成**（斜长岩月壳）。

### 14. G–X 曲线（Gibbs free energy vs composition）

**这是本周理论闭环的最后一环**：相图**不是画出来的，是从 G–X 关系推出来的**。

做法：在若干个温度上分别画出「液相 L 的 G 随成分 X 的变化曲线」和「固相（斜长石）的 G 随 X 的变化曲线」，然后在每个成分上取 **G 最低的方案**。四个温度切片的结果（转写详述）：
- **T1（最高温）**：整条曲线上，液相的 G 都低于斜长石 → **全为液相**。
- **T2（中温）**：**富 Ab（左）**一侧液相 G 更低；**富 An（右）**一侧斜长石 G 更低；**中间成分区**，G 最低的方案既不是纯液也不是纯固，而是**液 + 斜长石的混合**——这就是相图上 L+plag 两相区的由来。
- **T3（较低中温）**：同 T2 结构，只是两相区的位置移向富 Ab 端。
- **T4（低温）**：整条曲线上斜长石的 G 都低于液相 → **全为斜长石**。

把四个温度上"哪种方案 G 最低"的结论纵向叠起来，就长出了 T–X 相图的液相线、固相线和三个相区。

📎 背景补充：材料只说"中间成分区是两者的混合物 G 最低"，没有给出这个混合方案的几何构造名称——它叫**公切线法（common tangent construction）**：在两条 G–X 曲线上作一条公切线，两个切点的横坐标就分别是该温度下平衡液相和平衡固相的成分，公切线覆盖的成分区间就是两相区。液相线与固相线，正是不同温度下这两个切点轨迹连成的线。

---

## 三、公式与图表

### 1. 公式清单（保留原文形式）

| 公式 | 符号与单位 | 适用条件 | 说明 / 典型数值 |
|---|---|---|---|
| **PV = nRT** | P 压力 (Pa 或 atm)；V 体积 (m³)；n 物质的量 (mol)；R 气体常数 (8.314 J·mol⁻¹·K⁻¹)；T 温度 (**K**) | 理想气体 | 状态方程（equation of state）的代表例；材料指出还有很多其他状态方程 |
| **ΔU = Q + W**　/　**dU = dQ + dW** | U 内能 (J)；Q 热 (J)；W 功 (J) | 通用（第一定律） | W 是**对体系做的功** |
| **dU = dQ − P dV** | dV 体积微变 (m³) | 地质体系，功只有 PV 功 | 负号：体系膨胀 → 对外做功 → 内能减少 |
| **dS ≥ dQ / T** | S 熵 (J·K⁻¹) | 可逆取等号，不可逆取大于号 | 第二定律 |
| **dU ≤ T dS − P dV** | 同上 | 通用 | **热力学基本方程**；地质问题中一般取等号 |
| **H = U + PV** | H 焓 (J) | 定义式 | 只能测 ΔH，测不到 H 绝对值 |
| **dH = dQ** | — | **恒压（dP = 0）** | 恒压吸热全部转为焓变 |
| **G = H − T S** | G 吉布斯自由能 (J)；T 必须用 **K** | 定义式 | 本周核心量 |
| **ΔG < 0 / = 0** | — | **恒 T、恒 P** | <0 反应自发朝 G 低处走；=0 平衡、无反应 |
| **F = C − Φ + 2** | F 自由度（无量纲计数）；C 组分数；Φ 相数 | P、T 均可变 | 吉布斯相律 |
| **f = c − Φ + 1** | 同上 | **等压**（或等温） | Practical feedback 原文即用此式 |
| **X_A = a/(a+b)，X_B = b/(a+b)** | a、b 为连结线上的线段长度（用尺子量）；X 为 wt.% 或 mol.% | 两相共存区 | 杠杆定律；X_A + X_B = 1 |

**关于符号记忆的考试提示**：Slide 9 原文 "We will use symbols to discuss and apply thermodynamics, but **I do not expect you to memorise them!**"；转写中老师又重复两次 "you're not expected to remember all these letters"、"Again, you're not expected to remember all of those. We're just going through those because they're important, but you don't have to remember them."（Slide 10 另注 "See the summary of key symbols"，说明幻灯片里有一张符号汇总表，但 md 转换后表格内容丢失。）

### 2. H₂O 相图（Slides 17–19）

- **纵轴**：压力 P（单位：atm，大气压）
- **横轴**：温度 T（单位：°C）
- **组分数 C = 1**（唯一组分就是 H₂O 分子）
- 三个相区：**水蒸气 vapour**（高温）、**液态水 water**（中温）、**水冰 ice**（低温）

三种位置的相律计算（本周最标准的例题）：

| 位置 | C | Φ | F = C − Φ + 2 | 含义 |
|---|---|---|---|---|
| 液态水场内部 | 1 | 1 | **1 − 1 + 2 = 2** | 可**独立**改变 T 和 P（上下左右移动）仍是液态水 → **双变区** |
| 水–冰边界线上 | 1 | 2 | **1 − 2 + 2 = 1** | 改 T 就**必须**相应改 P 才能留在线上 → **单变线** |
| 三相点（冰+水+汽共存） | 1 | 3 | **1 − 3 + 2 = 0** | T、P 都不能动，动一点就少一个相 → **不变点** |

转写用它讲预测能力："if the temperature in that picture increases by several degrees, most of that ice is going to melt away to form liquid water."（Jökulsárlón 冰湖照片的语境。）

📎 背景补充：H₂O 相图有一个著名特殊性——**水–冰边界线的斜率是负的**（加压使冰融化），因为冰的密度小于液态水。绝大多数物质的固–液线斜率为正。材料未提及这一点，但它常是考题素材。

### 3. SiO₂（硅石）相图（转写描述，幻灯片文字未保留）

- **纵轴**：压力 P；**横轴**：温度 T
- 图中各个场对应 **SiO₂ 的不同同质多象变体（polymorphs）**
- **柯石英 coesite**：高压多形，产于深部（转写作"deep in the mountains"，应为 mantle，见勘误表）
- **石英 quartz**：地表条件（T ≈ 0 °C，P ≈ 1 atm）——"like on a beach, the silica you find is quartz"
- **鳞石英 tridymite / 方石英 cristobalite**：高温结晶产物中出现的多形
- **L**：液相（熔融 SiO₂）——老师特别提醒 **"the L in that diagram refers to liquid, so it's not a mineral"**（L 是液体，不是某种矿物名）

📎 背景补充：SiO₂ 常见多形按「温度升高、常压」顺序为 α-石英 → β-石英 → 鳞石英 → 方石英 → 熔体；按「压力升高」顺序为 石英 → 柯石英 → 斯石英（stishovite）。柯石英与斯石英也是**陨石撞击变质**的标志矿物。材料只点了 coesite、quartz、tridymite、cristobalite 四个。

### 4. An–Di 等压二元共结相图（Slide 20，Lecture 4 会重讲）

- **端元**：**钙长石 anorthite（An，斜长石的富 Ca 端元）** 与 **透辉石 diopside（Di，Ca-Mg 辉石）**
- **纵轴**：温度 T；**横轴**：An–Di 之间的体系成分
- **等压（isobaric）**，P 固定在 **1 atm** → 相律用 **+1**
- **C = 2**（An 与 Di 两个组分）；图中共出现 **3 个相**：An 晶体、Di 晶体、熔体（melt / liquid，转写强调这两个词**可互换使用**）

三种位置的相律：

| 位置 | Φ | f = C − Φ + 1 | 名称 |
|---|---|---|---|
| 液相线以上的 L 场 | 1（只有液） | **2 − 1 + 1 = 2** | 双变 |
| 液相线上 | 2（液 + 一种晶体，左侧为 An） | **2 − 2 + 1 = 1** | 单变 |
| **共结点 eutectic** | 3（An + Di + 液） | **2 − 3 + 1 = 0** | **不变点** |

⚠️ 老师在讲"液相线上单变"时口误说成"改变温度就必须改变压力"——该图是**等压**的，压力被锁死，正确说法是**改变 T 就必须相应改变（液相）成分 X**。见勘误表第 5 条。

📎 背景补充：**共结点（eutectic）** 是二元无固溶体系中液相线的最低点，也是最后一滴熔体固化的温度；在共结点上，两种晶体按固定比例同时结晶，温度不再下降，直到液体耗尽。材料本周只报出了它是 invariant point，其余留给 Lecture 4。

### 5. 斜长石 Ab–An 二元固溶体相图（Slides 25–27；Practical Figure 1）——**本周最重要的图**

**坐标轴**：
- **横轴 X_An，从 0 到 1**。**左端 X_An = 0 = 纯钠长石 Ab（NaAlSi₃O₈）**；**右端 X_An = 1 = 纯钙长石 An（CaAl₂Si₂O₈）**；中点 X_An = 0.5 表示 An 与 Ab 各半。
- **纵轴 T（°C）**，Practical 图上刻度为 1000 / 1200 / 1400 / 1600 °C。
- **等压，P = 1 atm**。

**三个相区、两条线**（自上而下）：
1. **L**（液相 / 熔体）——最上方
2. **液相线 liquidus**——液相区的下界；**读液相成分**用这条线
3. **L + plag**（液 + 斜长石两相区）——中间
4. **固相线 solidus**——两相区的下界；**读固相（斜长石）成分**用这条线
5. **plag**（斜长石固溶体单相区）——最下方

相律：C = 2（Ab 与 An），等压故用 +1。
- 在 **L + plag** 区内：Φ = 2 → **f = 2 − 2 + 1 = 1**
- 在 **plag** 区内或 **L** 区内：Φ = 1 → **f = 2 − 1 + 1 = 2**

**平衡结晶路径（Slide 25 + 转写，起始成分 X_An = 0.5，起始温度约 1600 °C）**：
1. 液体降温，垂直向下移动，在 **T1 ≈ 1460 °C** 与液相线相交 → 开始结晶。
2. 从 T1 处水平作连结线到固相线，读出**第一批斜长石成分 plag1 ≈ X_An 0.85**（比液体富钙得多）。
3. 继续降温到 **T2**：由于晶出的晶体富 An，**残余液体变得更富 Ab（向左移动）**，液体成分**沿液相线向左下滑动**至 L2；同时因为保持平衡，**已结晶的斜长石也整体重新平衡**，成分沿固相线左移至 **plag2 ≈ X_An 0.70**（转写数值）。
4. 任一温度上，用**杠杆定律**在液相成分点与固相成分点之间量距离，即可算出液/固比例。**注意：平衡结晶中体系成分点始终固定在 X_An = 0.5 这条垂线上不动。**
5. 降到 **T3**（固相线与 X_An = 0.5 的交点）：**最后一批斜长石的成分恰好等于体系初始成分 X_An = 0.5**；与之平衡的**最后一滴液体成分 ≈ X_An 0.13**（极富 Ab）。液体随即耗尽。

> **核心结论 1（平衡结晶）**：**最后结晶出的固体成分 = 体系初始成分**。这是"平衡"两个字的直接后果——物质守恒要求全部固化后固相平均成分必须等于起始成分，而平衡意味着固相是均一的。

**平衡熔融**：完全是平衡结晶的**逆过程**——从底部升温，沿同一路径反向走。

**分离结晶路径（Slide 26 + 转写，同样起始 X_An = 0.5）**：
1. 同样在 T1 ≈ 1460 °C 结晶出 plag1 ≈ X_An 0.85。
2. **但晶体一形成就被移走** → **体系 = 残余液体**。因此**体系成分点不再固定，而是跟着液体沿液相线向左（富 Ab）移动**。
3. 每一步都重复：结晶 → 移走 → 液体更富 Ab → 下一批晶体也更富 Ab。
4. **终点：液体一直演化到纯钠长石端元 X_An = 0，最后的晶体是纯 Ab。**

> **核心结论 2（分离结晶）**：**最终产物一定走到端元（本例为纯 Ab，X_An = 0）**，而不是停在体系初始成分。这是"分离"造成的成分极化。

**分离熔融路径（Slide 27 + 转写，起始固体 X_An = 0.5）**：
1. 升温，穿过**固相线**开始熔融（Practical 给出 T ≈ 1250 °C）。
2. 第一滴熔体的成分到**液相线**上读：**富 Ab**（低熔点端）。
3. 熔体立刻被抽走 → **残余固体（即体系）向富 An 方向演化**。
4. 继续升温，残余固体一路向右演化；**最后残留的斜长石在最高温度产生最富 An 的熔体**，终点是纯 An（X_An = 1）。

> **核心结论 3（转写原话，重点考点）**：**"Fractional melting is not the opposite of fractional crystallisation."** 平衡熔融与平衡结晶互为严格逆过程；**分离熔融与分离结晶则不是**。原因：两者移走的对象不同（一个移走熔体、一个移走晶体），残余体系的漂移方向因而不同——分离结晶把**液体**推向 Ab 端，分离熔融把**固体**推向 An 端。

### 6. 杠杆定律的几何与数值验证

**几何**：在两相区内，过体系成分点作**等温水平线（连结线 tie line）**，两端分别落在液相线和固相线上，读出两个平衡相的成分。设：
- X_sys = 体系成分，X_L = 液相成分，X_S = 固相成分

则（📎 背景补充：以下代数形式材料只给了 a/(a+b) 的几何形式，未写成成分表达式）：

> 固相比例 = (X_sys − X_L) / (X_S − X_L)　　液相比例 = (X_S − X_sys) / (X_S − X_L)

**用 Practical 的答案验证（1400 °C，X_sys = 0.5，X_plag = 0.75）**：
若 X_L ≈ 0.365，则 固相比例 = (0.50 − 0.365)/(0.75 − 0.365) = 0.135/0.385 ≈ **0.35**，即 **~35% plag、~65% L** —— 与 feedback 答案 h) 完全吻合。

**再用苯–甲苯题验证（365 K，X_sys = 0.40，X_V = 0.27，X_L = 0.51）**：
蒸汽比例 = (0.51 − 0.40)/(0.51 − 0.27) = 0.11/0.24 ≈ **0.46**，feedback 给 **~0.43**（读图误差范围内）。

> **由此确认方向：某一相的比例，正比于「体系点到对面那一相」的线段长度。离得越远，含量越多。**

### 7. G–X 图（Slide 31 / Practical Q2）

- **横轴**：成分 X（斜长石例：左 Ab、右 An；苯–甲苯例：X_Tol 从 0 到 1）
- **纵轴**：吉布斯自由能 G
- 每个温度画一张，图上有**两条曲线**：液相曲线（标 **L**）与另一相曲线（斜长石例为 plag，苯–甲苯例为蒸汽 **V**）
- **读法**：横轴上每个成分，取 G 最低者作为平衡相；两条曲线各自最低的区间之间存在一段"混合方案 G 更低"的区间，那就是两相区。
- **把多个温度的结果纵向堆叠 → 得到 T–X 相图。**（Practical Q2 就是让你从 5 个温度的 G–X 图**反向构建**出 T–X 相图。）

### 8. 本周没有的图

⚠️ 本周**没有等时线图（isochron diagram）、没有衰变曲线、没有任何同位素比值图**。放射性定年相关的图解（横轴子体/参考同位素比、纵轴放射成因子体比、斜率 = e^{λt} − 1、截距 = 初始比值）属于本课后段（大纲 Week 12 "Stable isotopes and carbon dating" 及相关内容），不在 Week 03。

---

## 四、课堂补充

本周的 5,214 词完整转写是最有价值的材料。以下是**幻灯片上没有、只有口头讲出来的内容**。

### （0）先说材料缺口 ⚠️

**`EART26201_Practical3_feedback_diagrams-1.md` 仅 59 词，是纯图件转换的残骸**。它的全部可提取内容只是一张被压扁的表格，里面散落着坐标轴刻度（1600 / 1400 / 1200 / 1000、0 / 0.2 / 0.4 / 0.6 / 0.8 / 1）、轴标签（*T* °C、*X*An）、端元化学式（Ab; NaAlSi₃O₈ / An; CaAl₂Si₂O₈）、相区标签（L、L+plag、plag），以及从 e) 到 m) 若干答案的标注文字。**图上的液相线、固相线的实际形状与曲率、答案标注所指的具体位置、以及第二题的 5 张 G–X 图和构建好的 T–X 相图，全部丢失，无法从 md 恢复**。

这意味着：
- **无法从材料中重建液相线/固相线的精确形状**，只能依靠 feedback 给出的几个离散读数（1460、1400、1250/1270 °C 与对应成分）来锚定。
- **Practical Q2 的苯–甲苯 G–X 图与答案相图完全缺失**，只能靠 feedback 文字答案倒推。
- 同样地，讲义 `EART26201_Lecture3-1_RT-1.md` 中 Slide 6（Lecture 3 synopsis）、Slide 8（Thermodynamics）、Slide 9–14（状态变量表、三大定律公式）、Slide 16（相律）、Slide 31（G–X 图）等，**转换后只剩标题和页脚，正文公式/表格/图形全部丢失**。本笔记中这些公式的具体形式，**几乎全部是从转写的口述里还原出来的**——这也说明为什么本周必须精读 transcript。

### （1）老师对本节课的定位与"坦白"

开场就说："today's content at times probably will feel a bit dry, but there's not many ways to make that very interactive, but we'll just get through it and see how we go."（今天内容会有点枯燥，没什么办法讲得很互动，我们撑过去。）——**这是明确信号：本周是纯理论周，理论密度最高，练习全部压在周三的 practical**。

同时说明本课的节奏：**"today is a lecture, so it's the theory, and Wednesday, we'll do the practical"**——周一理论 / 周三实践。

以及："I believe you've all been introduced to phase diagrams last year, we'll go a little bit further this year"——**假定你大一已学过相图基础**，本周是拔高，不是从零开始。

### （2）三次明确的"不要求背"提示（考试相关）

老师在整节课里**三次**强调符号和公式不需要背：
- Slide 9 旁白："I do not expect you to memorise them!"
- 第一定律讲完后："Again, you're not expected to remember all of those. We're just going through those because they're important, but you don't have to remember them."
- 讲状态变量时："you're not expected to remember all these letters for all these different terms."

**如何理解**：不要求背符号≠不要求理解。考试更可能考的是**会用**（相律代入、杠杆定律计算、路径描述），而不是默写 dU = TdS − PdV。Slide 10 提到会提供 "summary of key symbols"，说明可能有符号表可查。

### （3）熵的"摔盘子"比喻（老师自创，幻灯片上没有）

> "One way I like to think of when I think about entropy is a pile of plates. If it falls down onto the ground, it will break in many small pieces. You rarely see the opposite... **From a physics point of view, there is no reason why it can't happen. It's just very unlikely.** All systems tend to go to their more disordered state."

这个比喻的精髓在最后一句被强调的部分：**熵增不是物理禁令，而是概率压倒性**。碎片自发拼回完整盘子在物理上并不被禁止，只是概率低到不可能观察到。这是对"第二定律是不是绝对的"这类常见困惑的正面澄清。

### （4）体系是任意定义的——反复强调

> "a system is something we define arbitrarily, depending on the questions we're interested in... it can be a mineral grain... a magma reservoir... different rocks from a single granite... a whole planet... the solar system. It can be anything."

这一点幻灯片只有一张图，全靠口头展开。**做题时第一步永远是"我把什么定义为体系"**——这直接决定了 C 和 Φ 怎么数。

### （5）结晶速率与玻璃（幻灯片只有图，没有文字）

> "when it crystallizes fairly slowly, it will form different crystals... you've got here a sequence from **1170 degrees to 1020 degrees**, and you can see different crystals forming in a basaltic magma. **If a lava crystallizes very, very quickly, it won't have time to form crystals, and you can get glass.**"

这段对应 Slide 4 的 Wright & Okamura (1977) Makaopuhi 熔岩湖图。要点：
- 玄武质岩浆在 **1170 → 1020 °C** 区间依次结晶出不同矿物（结晶序列）；
- **玻璃 = 动力学上来不及结晶的产物**，是平衡热力学的反例，预告 Lecture 5 的失衡/动力学主题。

### （6）热力学的两个"实用价值"论证（口头展开）

老师给出的"为什么地球科学要学热力学"，除了幻灯片上抽象的 "Predictive power" 与 "Applications"，口头给了两个具体案例：

**a) 找矿（prospecting for ore deposits）**：康沃尔（Cornwall）Cligga Head 花岗岩曾开采**锡（tin）与钨（tungsten）**。"because we know of the thermodynamics of that system that we can go and locate these potential deposits in some granitic [massifs]."

📎 背景补充：康沃尔的 Sn–W 矿化属于**花岗岩相关的岩浆热液（magmatic-hydrothermal）成矿系统**，本课后段的"Hydrothermal systems"（大纲 Week 11）会回到这类体系；对 Energy and Resources 方向的学生，这也是 EART26001 能源与资源的直接接口。

**b) 碳捕集（carbon capture）**：冰岛 **Carbfix** 项目。"Because we know the thermodynamics of the system, we can try and work out what's the best solution to put carbon back into the ground."

📎 背景补充：Carbfix 的原理是把 CO₂ 溶于水后注入玄武岩，利用玄武岩中的 Ca、Mg、Fe 使 CO₂ 矿化为碳酸盐固定下来——**这正是"矿物–流体反应"的工程化应用**，也预告本课后段的碳酸盐化学（大纲 Week 9）。材料只提了项目名称，未展开机理。

### （7）"melt" 与 "liquid" 完全同义

> "We use melt and liquid interchangeably, they mean the same thing."

小事，但读英文相图时不要以为两个词指不同东西。

### （8）"L 不是矿物"

讲 SiO₂ 相图时特意点明："the L in that diagram refers to liquid, so it's not a mineral, it would be liquid silica."——因为图上其他标签（quartz、coesite、tridymite…）都是矿物名，L 混在里面容易被误当成某个矿物。

### （9）等压/等温体系用 "+1" 是口头补充的重点

幻灯片相律那页文字全丢，这一段完全靠转写：

> "In some cases, you can only change one of them. So, you can have **isobaric** system where the pressure is fixed, you can have **isothermal** systems where the temperature is fixed. In some cases, you wouldn't have plus 2 here, you would have **plus 1**."

**这是本周最容易被考的机械操作点**，而且 Practical Q1(d) 直接给出了 f = c − Φ + 1 的等压式子。

### （10）关于 practical 的具体交代（实操信息）

- **"bring a ruler for Wednesday please because the practical Wednesday is mostly paper based"** —— 需要带**尺子**（因为杠杆定律要量线段长度），还要带铅笔。老师重复了两次。
- 课后有学生问 "Do we need a computer for Wednesday?"，答："**It's not going to be computer based this time. No, not this time. It's going to be paper based.**"

⚠️ 这与课程大纲的 Practical 列表构成又一处印证：大纲把 "Introduction to phase diagrams (**paper based**)" 列在 Week 4、把 "Isochron dating (**PC based**)" 列在 Week 3。**实际本周 practical 是 paper based 的相图入门**，再次确认周次错位、本周非同位素定年。

### （11）课堂留白的小问题

讲杠杆定律时老师抛出："And X_A plus X_B equals what? **This will come in on Wednesday** when you do some phase diagram calculation." —— 答案是 **1（或 100%）**，但老师故意没说，留到 practical。

### （12）平衡结晶最后一句的强调

> "**in equilibrium system your last few plagioclase to crystallize will have the same composition than your system as it started.** So, here about 50% anorthite, 50% albite."

这句是全课最容易在考试里被直接问的结论之一，老师用了完整一句话来点题。

### （13）月球斜长岩月壳

> "if you look at the moon, all the white, light gray to white material you see on the lunar surface is plagioclase. So, **the primordial crust of the moon is made of anorthite.**"

幻灯片只标了 "Lunar Highlands"，机理靠口述。

📎 背景补充：月球高地由**斜长岩（anorthosite）**组成，通常解释为月球岩浆洋（Lunar Magma Ocean）结晶时，密度较低的钙长石**上浮堆积**形成原始月壳，而橄榄石、辉石下沉——这其实就是**分离结晶 + 密度分异**的行星尺度实例，与本周的分离结晶概念直接相通。材料未给出这个机理解释。

### （14）反复重申"热力学只管平衡"

> "Thermodynamics, it's only relating to equilibrium processes. The final lecture I do with you will actually look into disequilibrium processes, but that's not for this week."

配合 Slide 30 的 "We'll consider kinetics and disequilibrium in Lecture 5"。**本周所有结论都带一个隐含前提：体系有足够时间达到平衡。** 现实岩石（成分环带的斜长石、玻璃质基质）常常不满足这个前提。

---

## 五、Practical 要点

**Practical 3 | Introduction to phase diagrams**（Dr David Neave）
**形式**：纸笔（paper based），2 小时，两道题各约 60 分钟。需自备**尺子**。

### 组织方式与"评分"性质

- feedback 原文："I strongly encourage you to **discuss your work with each other** as you go."（鼓励讨论）
- "Demonstrators will be available throughout the practical class, and I will provide a **short round-up at the end**."（全程有助教，结束时统一小结）
- "I suggest **typing your answers into this document** as well as **annotating the associated blank phase diagrams**."（答案打进文档 + 在空白相图上标注）
- 另有 **Blackboard quiz** 覆盖本周其他主题（"Other themes relevant to this week's content are reviewed in a Blackboard quiz."）
- 📎 背景补充：本 practical 属于**形成性（formative）**练习，材料未标注分值。课程大纲显示本课的 20% report 是 Week 5 发、Week 7 交的那一份；Week 2 发、Week 4 交的 formative report 才是当前时段的书面作业。因此本 practical 的"评分要点"实际是**能力目标（Goals）达成度**，见下。

### 五条能力目标（feedback 原文 Goals，即自测清单）

1. 在二元相图上**标出固相线（solidus）、液相线（liquidus）与各相区**；
2. **解读带固溶体的简单二元相图**；
3. 用相图**解释平衡/分离的结晶与熔融**；
4. 用**杠杆定律**在不同相图上求各相比例；
5. **从 G–X 图构建简单二元相图**。

### Question 1：解读斜长石二元固溶体相图（60 min）

给定：1 atm 的 Ab–An 斜长石相图（单独一张纸）。

| 小题 | 问题 | 答案 | 解题要点 |
|---|---|---|---|
| a) | 标出 liquidus 与 solidus | — | 上面那条是液相线，下面那条是固相线 |
| b) | 标出 L、L+plag、plag 三个相区 | 见 a) | 自上而下三层 |
| c) | 体系有几个组分？是什么？ | **2 个：albite (Ab) 与 anorthite (An)** | 组分 = 描述所有相所需的最少化学物种 |
| d) | X_An = 0.5 时，1000 °C 和 1300 °C 各有几个自由度？（提示用等压相律 **f = c − Φ + 1**） | **1000 °C：c=2, Φ=1, f=2**；**1300 °C：c=2, Φ=2, f=1** | 1000 °C 在固相线以下（只有 plag 一相）；1300 °C 在两相区 |
| e) | X_An = 0.5 的液体在什么温度开始结晶？ | **T ≈ 1460 °C** | 垂线与**液相线**的交点 |
| f) | 第一批斜长石的成分？ | **X_An ≈ 0.85** | 从 1460 °C 水平拉到**固相线** |
| g) | 1400 °C 时与液体平衡的斜长石成分？ | **X_An ≈ 0.75** | 1400 °C 连结线右端 |
| h) | 计算 1400 °C 时液与斜长石的平衡比例 | **≈35% plag，≈65% L**（"This requires the lever rule and a ruler"） | 杠杆定律，量线段 |
| i) | X_An = 0.5 液体**平衡结晶**时，最后一批斜长石的成分？ | **X_An = 0.5** | **= 体系初始成分** |
| j) | 形成这批斜长石的液体成分？ | **X_An ≈ 0.13** | 同一连结线的左端，极富 Ab |
| k) | 若改为**分离结晶**，最后的斜长石与液体成分有何不同？ | **两者都是 X_An = 0，即纯 Ab** | 体系跟着液体沿液相线跑到端元 |
| l) | X_An = 0.5 的固体在什么温度开始熔融？ | **T ≈ 1250 °C**（⚠️ 图件文件写 1270 °C，见勘误表） | 垂线与**固相线**的交点 |
| m) | 平衡熔融与分离熔融中，最后熔掉的斜长石成分各是多少？ | **平衡：X_An ≈ 0.85；分离：X_An = 1（纯 An）** | 平衡熔融是平衡结晶的逆过程（回到 0.85）；分离熔融把残余固体推到端元 |

**Q1 的内在逻辑**：i)/k) 与 m) 两对答案，就是「平衡 vs 分离」差别的**数值化表达**——平衡回到起点或对称点，分离一律冲到端元。

### Question 2：从 G–X 图构建相图（60 min）——**苯–甲苯体系**

**为什么用有机溶剂？** feedback 原文解释得很清楚："Although we are primarily concerned with high-T geochemical processes in my part of the course, remember that the thermodynamic principles we have been discussing are **widely applicable**. Benzene (Ben) and toluene (Tol) are organic solvents that **mix when liquid but vaporise at different temperatures**; this behaviour is **not unlike that exhibited by olivine and plagioclase solid solutions**."

即：**液–气二元体系的数学结构与固–液固溶体体系完全相同**，只是把「固相/液相」换成「液相 L / 气相 V」、把「固相线/液相线」换成「液相线 liquidus / 露点线 vaporus」。

给定：1 atm、**5 个不同温度（K）** 的 G–X 图，液相曲线标 **L**、气相曲线标 **V**。

| 小题 | 问题 | 答案 |
|---|---|---|
| a) | 用 G–X 图在空白坐标上构建 1 atm 的 T–X 二元相图 | （图件缺失，无法重建）方法：每个温度找 G 最低的方案，标出两相区边界，再把 5 个温度的边界连成两条曲线 |
| b) | X_Tol = 0.4、365 K 的平衡相组合？各相成分与比例？ | **V + L**；**V: X_Tol ≈ 0.27**，**L: X_Tol ≈ 0.51**；比例 **V ≈ 0.43，L ≈ 0.57** |
| c) | 定量描述 X_Tol = 0.4 蒸汽的**平衡冷凝**与**分离冷凝** | **平衡**：首滴液在 **≈369 K** 冷凝出来，成分 **X_Tol = 0.63**；到 **≈362 K** 时蒸汽全部冷凝完，液相成分回到 **X_Tol = 0.4**，最后一点蒸汽成分 **X_Tol ≈ 0.2**。**分离**：首滴液同样在 ≈369 K、X_Tol = 0.63 出现，但液体被**持续移走**，V 与 L 的成分分别沿 vaporus 与 liquidus 演化，直到体系变成**纯苯（X_Tol = 0）于 353 K**。 |
| d) | 如何从 X_Tol = 0.2 的液体制得**纯甲苯**？ | 用**分离汽化（fractional vaporisation）**：加热并不断移走蒸汽，最后剩下的那一小部分液体就是纯甲苯——**这就是分馏 / 精馏（fractional distillation）**。 |

**b) 的结构与 Q1(g)+(h) 完全同构**（读两端成分 + 杠杆定律）；**c) 的结构与 Q1(i)(k) 完全同构**（平衡回到初始成分 0.4，分离冲到端元 0）。

📎 背景补充：苯的常压沸点约 **353 K（80.1 °C）**、甲苯约 **384 K（110.6 °C）**——甲苯更难挥发。这解释了 c) 和 d) 的方向：冷却蒸汽时**先冷凝出的液体富甲苯**（X_Tol 0.63 > 0.4）；加热液体时**先蒸发出的是苯**，所以残液富集甲苯。答案中"分离冷凝终点是纯苯、353 K"正好是苯的沸点，自洽。材料给出了 353 K 这个数字但未点明它是苯的沸点。

### 常见错误与得分要点（依据 feedback 的设问方式归纳）

1. **液相线/固相线读反**——液相成分永远读**液相线**，固相成分永远读**固相线**。e) 用液相线（开始结晶），l) 用固相线（开始熔融）。
2. **杠杆定律方向反**（把 35% 和 65% 写颠倒）——记住「离得越远，含量越多」。
3. **分离结晶的体系成分点忘了移动**——分离情形下体系 ≠ 原始成分，体系就是残余相。
4. **相律里 +2 / +1 用错**——本 practical 全部是等压图，一律 **+1**。feedback 特意把公式印在 d) 题干里，说明这是易错点。
5. **d) 中 Φ 数错**——1000 °C（固相区）只有 1 个相，很多人会误以为固溶体是"两个组分所以两个相"；**固溶体是单一相**。
6. **不带尺子**——h) 明写 "requires the lever rule and **a ruler**"，没有尺子这题做不了。
7. **不标注图**——feedback 明确要求 "annotating the associated blank phase diagrams"，图上标注本身就是答案的一部分。

---

## 六、易错点 / 重点难点

### 1. ⭐ 杠杆定律的方向（最高频错误）
某相的比例 = **体系点到「对面那一相」的距离 / 总距离**。检验方法：体系成分**越靠近**哪一相，那一相就**越多**。用 Practical h) 自检：X_sys = 0.5 离液相（≈0.365）比离固相（0.75）近，所以液相多（65%），固相少（35%）。✓

### 2. ⭐ 分离熔融 ≠ 分离结晶的逆过程
- **平衡熔融 ↔ 平衡结晶**：严格互逆，路径完全相同、方向相反。
- **分离熔融 vs 分离结晶**：**不互逆**。分离结晶把**液体**推向低熔点端元（Ab，X_An = 0）；分离熔融把**残余固体**推向高熔点端元（An，X_An = 1）。两者终点在相图的**两个相反端**。

### 3. ⭐ 相律的 +2 / +1
默认 **F = C − Φ + 2**（P、T 都自由）。只要题目/图上写了 isobaric（等压，如 "1 atm"）或 isothermal（等温），就改用 **+1**。本周所有二元相图（An–Di、Ab–An、苯–甲苯）**全部是等压图**。

### 4. ⭐ 固溶体是"一个相"，不是"两个相"
X_An = 0.5 的斜长石在固相区里 **Φ = 1**（一个均一的固溶体相），不是"Ab 相 + An 相"。Ab 和 An 是**组分（C = 2）**，不是相。**组分数和相数是两套完全独立的计数**，这是相律最常见的混淆源。

### 5. f = 1 到底意味着什么（细节陷阱）
Practical d) 的答案写："f = 1, which means that T and X_An **cannot** be changed without altering the system because although Φ will remain 2, the proportions of L and plag will change."

**这个表述需要小心理解**：严格地说，f = 1 意味着**只有一个强度量可以自由指定**——一旦定了 T，两个平衡相的成分（X_L 和 X_plag）就被完全锁死了。feedback 想强调的是"随便动 T 或 X 会改变体系的状态（相比例变了）"。

📎 背景补充：更严格的区分是——相律中的"成分变量"指的是**各个相自身的成分**（intensive），而**体相成分 X_sys 并不是相律计数的强度量**。在两相区内，你其实可以在保持 Φ = 2 的前提下平移 X_sys（相比例会变，但相的种类和成分不变）。feedback 的说法是教学上的简化。考试按 feedback 口径答即可，但要知道其中的分寸。

### 6. 温度单位
相图轴上是 **°C 或 K，看图说话**；但一旦代入热力学公式（G = H − TS、PV = nRT、dS = dQ/T），**必须用 K**。老师专门提醒过这一点。

### 7. ΔG 只管方向、不管速率
ΔG < 0 只说明反应"可以发生"，不说明"多久发生"。地质中大量矿物（如地表的橄榄石、玻璃）处于 ΔG < 0 的亚稳态却能保存百万年，因为动力学障碍。**这是 Lecture 5（动力学与失衡）的伏笔，也是本周与全课第二大块的接缝。**

### 8. 恒压下 dH = dQ 的正确条件
成立条件是 **dP = 0**，**不是** dV = 0（恒压下体积照样可以变，−PdV 的功照样存在）。正确推导：dH = dU + PdV + VdP = (dQ − PdV) + PdV + VdP = dQ + VdP，dP = 0 → dH = dQ。转写此处说法有误（勘误表第 4 条）。

### 9. 平衡结晶"最后一批固体 = 初始成分"的条件
这条结论**只在平衡结晶**下成立，且要求**固相始终保持成分均一**（即固相内部扩散足够快）。现实的斜长石常保留**成分环带（zoning）**，说明固相内扩散跟不上——这正是分离结晶的物理成因。

📎 背景补充："成分环带"这个词材料本周未出现，但它是理解为什么天然斜长石既不完全平衡也不完全分离的关键，Lecture 5 与 EART22200 会展开。

### 10. 液相线以上 / 固相线以下都是单相区，自由度相同
在 Ab–An 图上，**L 场**和 **plag 场**的相律计算结果完全一样（f = 2 − 1 + 1 = 2），因为都只有一个相。别因为一个是液体一个是固体就以为自由度不同。

### 11. 材料内部数值不一致：1250 vs 1270 °C
Q1(l) 在文字 feedback 中为 **T ≈ 1250 °C**，在图件文件中标注为 **T ≈ 1270 °C**。这是读图精度差异，考试中给出 ±20 °C 范围内的读数都应可接受，但要知道两个文件对不上（勘误表第 10 条）。

---

## 七、本周术语表

| 英文 | 中文 | 简要说明 |
|---|---|---|
| Thermodynamics | 热力学 | 研究能量及能量变化的学科；本周只处理**平衡态** |
| Equilibrium | 平衡 | 体系各组成不随时间变化的状态 |
| Disequilibrium | 失衡 / 非平衡 | 如熔岩湖、玻璃质熔岩；留待 Lecture 5 |
| System | 体系 | 人为界定的研究对象，可从矿物颗粒到太阳系 |
| Surroundings | 环境 | 体系以外的部分 |
| State variable | 状态变量 | 描述体系状态的量 |
| Extensive variable | 广度量 / 广延变量 | 随体系大小改变：质量、体积、H、S、G |
| Intensive variable | 强度量 | 与体系大小无关：T、P、成分 |
| Equation of state | 状态方程 | 联系状态变量的方程，如 PV = nRT |
| Internal energy (U) | 内能 | 原子振动动能 + 化学键势能 |
| Heat (Q) | 热 | 与环境交换的能量 |
| Work (W) | 功 | 地质体系中主要是 −P dV（压力—体积功） |
| First law of thermodynamics | 热力学第一定律 | 能量守恒，dU = dQ − P dV |
| Entropy (S) | 熵 | 能量分布 / 无序度的量度；单位 J·K⁻¹ |
| Second law of thermodynamics | 热力学第二定律 | dS ≥ dQ/T，反应朝熵增方向进行 |
| Reversible / Irreversible | 可逆 / 不可逆 | 可逆时 dS = dQ/T，不可逆时 dS > dQ/T |
| Enthalpy (H) | 焓 | H = U + PV，总热含量；只能测 ΔH |
| Gibbs free energy (G) | 吉布斯自由能 | G = H − TS；恒 T、P 下判断反应方向 |
| Phase diagram | 相图 | 以图形表示何种相/相组合具有最低 G |
| Gibbs phase rule | 吉布斯相律 | F = C − Φ + 2（等压/等温时 +1） |
| Degrees of freedom / Variance (F, f) | 自由度 / 方差 | 可独立改变的强度量个数 |
| Component (C) | 组分 | 描述体系所有相所需的**最少**化学物种数 |
| Phase (Φ) | 相 | 物理上可区分的均一部分 |
| Divariant field | 双变区 | F = 2，相图上的面 |
| Univariant curve | 单变线 | F = 1，相图上的线（相界） |
| Invariant point | 不变点 | F = 0，如三相点、共结点 |
| Triple point | 三相点 | H₂O 图上冰–水–汽共存的不变点 |
| Polymorph | 同质多象变体 / 多形 | 同成分不同结构，如 SiO₂ 的 quartz/coesite |
| Coesite | 柯石英 | SiO₂ 的高压多形 |
| Quartz | 石英 | 地表条件下稳定的 SiO₂ 多形 |
| Tridymite | 鳞石英 | SiO₂ 的高温低压多形 |
| Cristobalite | 方石英 | SiO₂ 的更高温多形 |
| Liquidus | 液相线 | 液相区下界；读**液相成分** |
| Solidus | 固相线 | 固相区上界；读**固相成分** |
| Vaporus | 露点线 | 液–气体系中与液相线对应的气相成分线（苯–甲苯题） |
| Eutectic | 共结点 / 低共熔点 | 二元体系中三相共存的不变点（An–Di 图） |
| Tie line | 连结线 / 等温线 | 两相区内的水平线，两端为平衡相成分 |
| Lever rule | 杠杆定律 | X_A = a/(a+b)；求两相比例 |
| Melt / Liquid | 熔体 / 液体 | 本课中**完全同义** |
| Solid solution | 固溶体 | 端元之间连续互溶的**单一相** |
| Binary phase diagram | 二元相图 | 两组分体系的 T–X 图 |
| G–X diagram | G–X 图（自由能–成分图） | 相图的构造依据 |
| Equilibrium crystallisation | 平衡结晶 | 固液始终保持平衡；末批固体 = 初始成分 |
| Fractional crystallisation | 分离结晶 | 晶体即时移出；液体演化到端元 |
| Equilibrium melting | 平衡熔融 | 平衡结晶的严格逆过程 |
| Fractional melting | 分离熔融 | 熔体即时抽出；**不是**分离结晶的逆过程 |
| Fractional distillation | 分馏 / 精馏 | 分离汽化的工业形式（Practical Q2d） |
| Plagioclase (plag) | 斜长石 | Ab–An 固溶体 |
| Albite (Ab) | 钠长石 | NaAlSi₃O₈，X_An = 0 端元 |
| Anorthite (An) | 钙长石 | CaAl₂Si₂O₈，X_An = 1 端元 |
| Diopside (Di) | 透辉石 | Ca-Mg 辉石，An–Di 图端元 |
| Andesite | 安山岩 | 弧环境火山岩，常含大斜长石斑晶 |
| Granulite | 麻粒岩 | 大陆地壳深部变质岩，含斜长石 |
| Lunar Highlands | 月球高地 | 由斜长石（钙长石）构成的原始月壳 |
| Isobaric | 等压 | P 固定 → 相律用 +1 |
| Isothermal | 等温 | T 固定 → 相律用 +1 |
| Carbon capture | 碳捕集 | Carbfix 项目为热力学的工程应用例 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| 1. `EART26201 - 13-Oct-transcript.md`，Gibbs 相律引入段 | "it's given as follows, **F equals C minus 5 plus 2**" | 相数符号 Φ（phi）被自动转写误听成数字 "5"，公式被写坏 | 应为 **F = C − Φ + 2**。紧随其后的三个算例（1−1+2=2、1−2+2=1、1−3+2=0）都用的是 Φ，可反证 |
| 2. 同上，水相图段 | "the only component in that diagram is H2O, the water molecule. **D equals 1.**" | 字母误转写 | 应为 **C = 1**（组分数为 1），"D" 是 "C" 的转写错误 |
| 3. 同上，第二定律段 | "for a reversible process, **the entropy, which is S, equals dQ over T**" | 漏掉微分符号，把 S 写成等于 dQ/T | 应为 **dS = dQ/T**（可逆过程）。后文合并式 "dS ≥ dQ/T" 是对的 |
| 4. 同上，焓段 | "at constant pressure, **meaning no work is done on the system, dP and dV is equal to zero**. Then we've got dH... equals dQ" | 物理表述错误：恒压只要求 dP = 0，**dV 不为零**，体积功 −P dV 依然存在 | 正确推导：dH = dU + P dV + V dP = (dQ − P dV) + P dV + V dP = dQ + V dP；令 dP = 0 得 **dH = dQ**。结论对，理由错 |
| 5. 同上，An–Di 等压图液相线段 | "you become univariant when you're on the liquidus. **If you change the temperature, you have to change the pressure to remain on that line. If you change the pressure, you have to change the temperature.**" | 该图**是等压的（P 固定在 1 atm）**，压力根本不能变；这句话是把前面 H₂O 图（P–T 图）的说法照搬过来了 | 在等压二元图上，f = 1 意味着**改变 T 就必须相应改变（液相）成分 X** 才能留在液相线上 |
| 6. 同上，相律 "+2/+1" 总结句 | "**So, that number refers to how many intensive variables are fixed.**" | 说反了。同一段前文的表述是对的（"+2 reflects the fact that pressure and temperature are the only intensive variables you can change"） | 该数字指**可以自由变化**的强度量个数：P、T 都可变 → +2；等压或等温 → +1 |
| 7. 同上，SiO₂ 相图段 | "In most lavas, most lavas would crystallize at something like 800, 900 degrees C, **and a few GPAs**" | 压力数量级错误。几 GPa 相当于百公里级地幔深度，熔岩不可能在此结晶 | 熔岩（lava）按定义在地表附近结晶，压力约 **1 atm ~ 数百 MPa**。疑为口误或 "a few hundred MPa / a few kbar" 的转写错误 |
| 8. 同上，SiO₂ 相图段 | "coesite is a high-pressure polymorph of silica. So, **deep in the mountains**, at high pressure, you can find some coesite" | 疑为 "deep in the **mantle**" 的转写错误 | 柯石英是高压多形，主要产于地幔深度、**超高压变质（UHP）俯冲陆壳**及**陨石撞击构造**中。若原话确为 "mountains"，则指 UHP 造山带（如大别–苏鲁），亦可通，但语境更像 "mantle" |
| 9. 同上，SiO₂ 相图段 | "such as tridymites or **crystallites**" | 矿物名转写错误 | 应为 **cristobalite（方石英）**，不是 "crystallite（微晶）" |
| 10. `EART26201_Practical3_feedback-1.md` 第 l) 题 **vs** `EART26201_Practical3_feedback_diagrams-1.md` | 文字版："l) _T_ ~ **1250** °C"；图件版："l) T ~ **1270** C" | **两份 feedback 文件对同一小题给出不同数值**，相差 20 °C | 属读图精度差异。X_An = 0.5 的固相线温度应在 **1250–1270 °C** 之间；答题时给出该区间内的读数均合理 |
| 11. 同上（转写全篇）拼写/听写类 | "a **mathematics** system"（应为 magmatic）；"**anortite** / **diopsite**"（应为 anorthite / diopside）；"the **level** rule"（应为 lever rule）；"**J-X** curves"（应为 G–X curves）；"**mid-ocean rich** basalts"（应为 mid-ocean ridge basalts）；"prospecting for **all** deposits"（应为 ore deposits）；"more **albatic**"（应为 albitic）；"plage / plagi"（应为 plag）；"There's many **moles**"（应为 there are many more） | 自动转写的同音/近音误识别，属系统性噪声 | 按括号内更正阅读。这类错误在本转写中密度较高，引用原文时需自行还原 |
| 12. `(EART26201) Principles of Geochemistry.md` Syllabus 周次 **vs** 文件夹周次 | 大纲把本内容列为 "Week 4"，把 "Isochron dating (PC based)" 列为 Practical Week 3 | **大纲周次（学期周，从 Week 2 开课，含 Week 7 reading week）与文件夹周次（授课周，Week 1–10 连续）系统性错位 1 周** | 文件夹 Week N ≈ 大纲 Week N+1。授课者本人称本次为 "week three"、幻灯片标 "Lecture 3"、practical 确为 paper based 相图入门（大纲 Week 3 列的是 PC based 等时线定年，与实际不符）。**本笔记库统一采用文件夹编号** |

**关于放射性核素的核对**：本周材料**完全不涉及任何放射性核素、半衰期、衰变常数或母子体关系**，因此无此类数据可核对，也不存在类似「²³⁹Pu 半衰期被安给 ²³⁹U」的风险点。
