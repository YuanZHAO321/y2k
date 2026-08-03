# EART26201 Principles of Geochemistry — Week 05 学习笔记

## 一、本周主题

**本周主题：地球化学过程的速率——反应动力学与扩散（The pace of geochemical processes: kinetics and diffusion）。**

这个判定来自三份材料的直接互证，不是推测：

- 幻灯片 `EART26201_Lecture5_RT.md` 第 1 张的大标题就是 "The pace of geochemical processes: kinetics and diffusion"，并在 Slide 6 给出五部分提纲：Part 1 引论 / Part 2 反应速率与反应级数 / Part 3 温度与 Arrhenius 关系 / Part 4 扩散与 Fick 定律 / Part 5 估算岩浆过程时间尺度。
- 10 月 27 日课堂录音开头老师原话："Today we will be discussing about kinetics and how does kinetics apply to diffusion."
- Practical 5 反馈文档标题为 "Timescales of magmatic processes"，两道题分别是「扩散系数与 Arrhenius 关系」和「用橄榄石 Mg–Fe 环带估算岩浆混合时间尺度」。

因此，0a 预处理里「第 4–5 周可能讲热力学与相图」的推测**在本周不成立**——热力学与相图是**上一周（Week 04）**的内容，本周是它的「时间维度对偶」。0b 预处理由数据表推测的「Mg-Fe 互扩散实验」**成立**，而且正是 Practical 的主线。

**在全课骨架中的位置。** 本课四大块为：热力学与相图 / **反应动力学与扩散** / 酸碱溶解度与氧化还原 / 放射性与稳定同位素。本周是第二块的全部内容，也是**高温地球化学部分的收尾**。老师在课上明确交代了这个分界：他本人负责高温部分（Weeks 1–5），阅读周之后由 Greg Holland 接手低温地球化学（水溶液、酸碱、氧化还原、同位素）。

这一周的地位可以概括为一句话：**热力学告诉你「系统最终想去哪里」，动力学告诉你「它走得多快、走到哪儿被冻住了」。** 地质样品之所以能保存信息，恰恰是因为它们没走到终点。本周内容向前接 Week 04 的相图（橄榄石 Fo–Fa 固溶体相图在本周被反复使用），向后辐射到 EART22200 火成矿物与过程、EART24200 变质矿物与过程（Practical 反馈原文点名了这两门课），也为 Week 12 稳定同位素中的「封闭温度」概念打底。

> ⚠️ **周次编号说明**：课程大纲（spec）把 "kinetics and diffusion" 排在 Week 6，把 Week 5 写作 "Melting and crystallisation: phase diagram applications"。这是已知的**大纲编号与文件夹编号错位**（spec 含 reading week，从 Week 2 数到 Week 12）。幻灯片自身命名为 "Lecture 5"，与文件夹一致。本笔记库统一采用**文件夹编号**，故本周为 Week 05。

---

## 二、核心概念

### 2.1 热力学 vs 动力学：两个互补的问题

**热力学（thermodynamics）**描述系统在给定条件（T、P、成分 X）下的**平衡态**。相图告诉我们哪一个相或相组合具有**最低的 Gibbs 自由能 G**。前几周的应用包括：金属熔化（固→液）、岩浆结晶（液→固）、岩浆脱气（液→气）。这些**全部是平衡态描述**。

问题在于：**地质系统达到平衡需要时间，而很多系统根本没有达到平衡**。老师举的例子是上周的辉石相图（pyroxene phase diagram）——出溶（exsolution）现象有时发生、有时不发生，差别就在于**有没有足够的时间**。

**动力学（kinetics）**研究的正是：**你以多快的速度走向平衡，或者为什么走不到平衡**。

### 2.2 岩石记录中的动力学证据：为什么岩石学能存在

老师用一张俯冲带示意图讲了一个非常本质的观点。图上有俯冲板片插入大陆板块之下、上方有弧火山作用；标注了两种岩石：

- **橄榄岩（peridotite）**——来自地幔的岩石；
- **蓝片岩（blueschist）**——高压环境形成的岩石，其蓝色来自**蓝闪石（glaucophane）**。

如果这些岩石到达地表后有**足够长的时间在地表条件下重新平衡**，它们的热力学归宿是变成**黏土（clay）、石英（quartz）、蛇纹石（serpentine）**——因为地表富含水分。

**但我们确实能在野外采到含新鲜橄榄石的橄榄岩、含蓝闪石的蓝片岩。这纯粹是动力学的功劳：它们没有时间重新平衡。**

老师的结论掷地有声：**"without kinetics, there would be no igneous or metamorphic petrology"（没有动力学，就不存在火成岩与变质岩岩石学）**。这是本周最应该记住的一句话。

### 2.3 反应速率（reaction rate）

对通用反应

$$a\mathrm{A} + b\mathrm{B} \rightarrow c\mathrm{C} + d\mathrm{D}$$

**平均反应速率** $R$ 定义为单位时间内浓度的变化，并用化学计量系数归一化：

$$R = -\frac{1}{a}\frac{\Delta[\mathrm{A}]}{\Delta t} = -\frac{1}{b}\frac{\Delta[\mathrm{B}]}{\Delta t} = +\frac{1}{c}\frac{\Delta[\mathrm{C}]}{\Delta t} = +\frac{1}{d}\frac{\Delta[\mathrm{D}]}{\Delta t}$$

推广到任意组分 $i$ 的**瞬时速率（instantaneous rate）**：

$$R = \frac{1}{\nu_i}\frac{\mathrm{d}[i]}{\mathrm{d}t}$$

其中 $\nu_i$ 是化学计量系数，**对产物取正、对反应物取负**。老师特别解释了为什么要这样规定符号：**因为我们希望速率 $R$ 永远是正数**。反应物浓度随时间下降（$\Delta[\mathrm{A}]/\Delta t < 0$），配上负号才得到正的 $R$。

### 2.4 决定反应速率的两大因素：碰撞理论

幻灯片 Slide 9 和 Slide 14 把同一张图重复了两次（一次在 Part 2 开头，一次在 Part 3 开头），说明这是全周的组织框架：

> **反应物必须以足够的能量相互碰撞，反应才能发生。**
> 增加「成功碰撞」次数只有两条路：
> 1. **提高反应物的浓度** → 速率定律与反应级数（Part 2）
> 2. **提高反应物的能量** → 温度与 Arrhenius 关系（Part 3）

老师用一个简单示意图讲浓度那一条：一个 A 分子在运动，如果周围只有很少的 B 分子，碰上的概率很小；如果 B 分子很多，碰上的概率就高得多。

### 2.5 速率定律（rate law）与反应级数（reaction order）

对上面的反应，**速率定律**把速率与各组分浓度联系起来：

$$R = k\,[\mathrm{A}]^{n_A}[\mathrm{B}]^{n_B}\cdots$$

- $k$：**速率常数（rate constant）**。老师强调，**关于分子能量的全部信息都藏在 $k$ 里**；$k$ 越大，反应越快。$k$ 与温度的关系就是 Part 3 的 Arrhenius 关系。
- $n_A, n_B$：各组分的**反应级数**。
- **总反应级数（overall order）** = 各分级数之和（对简单反应而言）。

**关键警告（幻灯片 Slide 10 与老师口述都强调）**：只有**基元反应（elementary reaction）**才能直接从化学计量系数读出反应级数。**绝大多数地球化学反应是复杂反应，包含多个步骤、每步有各自的反应级数，必须通过实验测定。**

### 2.6 三种反应级数

| 级数 | 速率对浓度的依赖 | rate–concentration 图上的形状 |
|---|---|---|
| **零级（zeroth order）** | $R = k$，与浓度**无关** | 水平直线 |
| **一级（first order）** | $R = k[\mathrm{A}]$，正比于浓度 | 过原点的斜直线 |
| **二级（second order）** | $R = k[\mathrm{A}]^2$，正比于浓度平方 | 向上弯曲的抛物线 |

### 2.7 关键例子：CO₂ 水合反应与「准一级」近似

$$\mathrm{CO_2} + \mathrm{H_2O} \rightleftharpoons \mathrm{H_2CO_3}$$

老师指出这是**地球固定大气碳的重要途径之一**：CO₂ 与水反应生成碳酸，从而可以储存在海洋里。速率写作

$$R = -\frac{\Delta[\mathrm{CO_2}]}{\Delta t} = k\,[\mathrm{CO_2}][\mathrm{H_2O}]$$

**理论上这是二级反应**（对 CO₂ 一级、对 H₂O 一级）。**但在海洋里水是巨量过剩的、可视为无限储库，[H₂O] 实际上不变**，于是被吸收进速率常数，反应**表现为对 CO₂ 的一级反应**：

$$R = k'[\mathrm{CO_2}], \qquad k' = k[\mathrm{H_2O}]$$

结论：**CO₂ 越多，水合反应越快。**

📎 **背景补充**：这种「某反应物过量到浓度可视为常数，从而使表观级数低于真实级数」的近似，化学上称为**准一级反应（pseudo-first-order reaction）**。材料没有用这个术语，但这是标准叫法，值得记住。它也解释了 Week 09 碳酸盐化学里为什么可以把 $[\mathrm{H_2O}]$ 从平衡常数表达式中省略。

### 2.8 活化能（activation energy, $E_a$）与 Arrhenius 关系

**$E_a$ 是反应发生所必需的能量门槛。** 老师的描述非常直白：

- 能量**低于** $E_a$：A 与 B 碰撞了，但**不反应**，弹开；
- 能量**高于** $E_a$：A 与 B 碰撞并**生成产物 AB**。

**Boltzmann 分布**给出能量为 $\varepsilon_i$ 的分子数：

$$N_i = A\,\exp\!\left(-\frac{\varepsilon_i}{k_B T}\right)$$

其中 $A$ 是**频率因子（frequency factor）**，取决于体系中的分子总数；$k_B$ 是 **Boltzmann 常数**；$T$ 是**开尔文温度**。

进一步，**具备活化能的分子所占比例**为

$$\frac{N_{E_a}}{N} = \exp\!\left(-\frac{E_a}{k_B T}\right)$$

由于 $R \propto k$ 且 $k \propto N_{E_a}$，最终得到**Arrhenius 关系（Arrhenian relationship）**：

$$k = A\,\exp\!\left(-\frac{E_a}{RT}\right)$$

老师强调：**温度对反应速率的影响是极度非线性的**。温度越高，反应越快，而且是指数式地快。

📎 **背景补充**：$k_B$ 与 $R$ 只差一个 Avogadro 常数（$R = N_A k_B$）。写成 $k_B T$ 时 $E_a$ 用「每个分子」的能量（J 或 eV）；写成 $RT$ 时 $E_a$ 用「每摩尔」的能量（J/mol 或 kJ/mol）。**本课的 Practical 一律用 kJ/mol 配 $R = 8.314\times10^{-3}$ kJ mol⁻¹ K⁻¹，务必单位一致。** 材料把 $E_a$ 单位简写作 "kJ"，那是省略了 "/mol"。

### 2.9 Arrhenius 关系的地质意义：一个数量级对比

Slide 17 的两个例子（老师完整口述）：

| 反应 | 温度 | 时间尺度 |
|---|---|---|
| 熔体 → 橄榄石结晶（melt → olivine） | 800–1000 °C（高温） | **几秒到几分钟** |
| 橄榄石 → 蛇纹石（olivine → serpentine） | 地表低温 | **几年到几千年（millennia）** |

原因：**高温下有更大比例的分子具备所需的活化能**；低温下能翻过 $E_a$ 门槛的分子极少。

### 2.10 质量传输（mass transfer）：理论与现实的落差

到目前为止的速率理论**默认反应物随时可用**。现实中的地球化学系统不是这样：

1. **反应物常常彼此隔离**——地球化学系统往往是**稀释系统（dilute system）**。即使能量够、活化能翻得过去，A 和 B 碰不到一起也白搭。
2. **很多反应只能在相与相的界面（interface）上进行**。老师举的例子：基质（groundmass）中的橄榄石晶体，反应只发生在晶体边界一圈。
3. **相常常被锁在巨大的储库里**（海洋、地幔等）。

因此**质量传输是反应发生的前提**。有两种机制：

- **平流 / 对流搬运（advection）**：物质的**整体物理运动**。
- **扩散（diffusion）**：沿浓度梯度的**自发运动**。

### 2.11 平流 vs 扩散

| | 平流 advection | 扩散 diffusion |
|---|---|---|
| 驱动 | **需要外力**（搅拌、重力、洋流、板块运动） | **不需要外力**，只需**浓度梯度** |
| 生活类比 | 把牛奶**搅进**茶里 | 不搅，颜色自己慢慢均匀 |
| 有效距离 | **厘米到数千公里**——极其高效 | 固体中即使几百万年也只有**几厘米** |
| 地质实例 | 俯冲带把水带入地幔、大洋环流 | 晶体内的元素环带松弛 |

老师给的**扩散卡通图**：左边 $t_1$ 时刻，左半边挤满紫色分子、右半边一个都没有（强浓度梯度）；右边 $t_2$ 时刻，紫色分子在全空间**均匀分布**。

**一句很容易被忽略但很重要的话**：**扩散一直在发生（diffusion occurs all the time），但只有当它在抹平一个浓度梯度时你才「看得见」它。** 均匀体系中扩散照样在进行，只是净通量为零。

### 2.12 平流通量与平流方程

**平流通量（advective flux）**：溶质 $i$ 穿过一个平面的通量

$$J_i = v\,C_i$$

即**速度 × 浓度**。考虑一个体积元，进来的通量 $J_{i,\text{in}}$ 与出去的通量 $J_{i,\text{out}}$ 之差决定浓度随时间的变化：

$$\frac{\partial C_i}{\partial t} = -\frac{\partial J_i}{\partial x}$$

合并两式得到**一维平流方程**：

$$\frac{\partial C_i}{\partial t} = -v_x\frac{\partial C_i}{\partial x}$$

**地球上的平流实例（老师详述）：**
- **俯冲与板块构造**：洋底的水分子被俯冲板片带到地下**数百公里**深处；这对把水和其他挥发分输送进地幔至关重要，进而**促进地幔熔融、触发弧火山作用**。老师称之为「地质演化的基础过程」。
- **大洋环流**：驱动力是洋流，可以把物质搬运**数千公里**。

### 2.13 扩散通量与 Fick 第一定律（Fick's first law）

$$J_i = -D_i\frac{\partial C_i}{\partial x}$$

逐项解释：

- $J_i$：组分 $i$ 的**扩散通量**，单位时间单位面积通过的物质量。
- $D_i$：**扩散系数（diffusion coefficient / diffusivity）**，单位 **m² s⁻¹**（Practical 明确解释了为什么是 m²/s：因为它关联的是**通过一个平面的扩散通量**）。$D$ 是**每个组分在每种介质中各不相同的**。
- $\partial C_i/\partial x$：**浓度梯度**。
- **负号的含义**：**通量指向低浓度方向**。扩散从高浓度流向低浓度。

三条推论（老师逐条讲了）：
1. **梯度越大，通量越大**——"the more of a component I start with, the greater the flux"。
2. **平衡时没有浓度梯度，因此没有净通量**。
3. **通量的大小主要取决于 $D$ 的量级**。

> ⚠️ **老师专门停下来强调的符号陷阱**：**扩散系数 $D$ 不要与第 1 周学的分配系数（partition coefficient）$D$ 混淆**。两者用同一个字母纯属不幸。判断方法看语境：**讨论元素 $i$ 在橄榄石与熔体之间如何分配 → 分配系数；讨论扩散问题 → 扩散系数。**

### 2.14 扩散系数的温度依赖：Arrhenius 形式

$$D_i = D_0\exp\!\left(-\frac{E_a}{RT}\right)$$

- $D_0$：**指前因子（pre-exponential factor）**，单位与 $D$ 相同（m² s⁻¹），是每个元素—介质组合特有的常数。
- $E_a$：该扩散过程的**活化能**（kJ/mol）。
- $R = 8.314\times10^{-3}$ kJ mol⁻¹ K⁻¹。
- $T$：**开尔文温度**。$T(\mathrm{K}) = T(°\mathrm{C}) + 273.15$。

**"$D_0$ 与 $E_a$ 是溶质与介质的特征参数"**——镁在橄榄石中有一套 $(D_0, E_a)$，铁有另一套，同一元素在别的矿物里又是另一套。

**普遍规律**：$D_{\text{气体}} > D_{\text{液体}} > D_{\text{固体}}$。老师的原话：空气分子在大气中比在熔岩中动得快，在熔岩中比在固体中动得快。**在固体中，即使在中等温度下经过数百万年，反应物也只能移动几厘米**——所以扩散在长距离搬运上非常低效。

### 2.15 Fick 第二定律（Fick's second law）与封闭温度

**浓度梯度记录的是「不完全的扩散再平衡」。** 如果完全再平衡了，梯度就消失了、信息就没了。

**为什么不平衡态能被保存下来？——冷却，以及「封闭温度」概念。**

> **封闭温度（closure temperature）**：一个温度，**低于它以后基本上不再发生扩散**。高温下扩散顺畅、元素自由迁移；把系统冷下来，对某个元素在某个温度以下扩散就「停止」了，梯度被冻结保存。

Fick 第二定律描述浓度随**位置 $x$ 与时间 $t$** 的变化：

$$\frac{\partial C_i}{\partial t} = D_i\frac{\partial^2 C_i}{\partial x^2}$$

老师坦言：**"Solving Fick's second law is rarely straightforward"**，通常需要**计算机与电子表格建模**求解。

**求解的目的是反解出 $t$**，这就是**扩散年代学 / 扩散计时（diffusion chronometry）**——也就是本课的关键词 **geospeedometry（地质测速学）**。

📎 **背景补充**：材料没有给出 Fick 第二定律的解析解，但有两个「量级估算」工具非常值得记住：
- **扩散长度尺度（diffusion length scale）**：$x \approx \sqrt{D t}$，或更常用的 $x \approx 2\sqrt{Dt}$。这给了你一个快速判断：**知道 $D$ 和一段时间，扩散能走多远**。
- **半无限介质中初始为阶跃剖面的解析解**：$C(x,t) = C_\infty + (C_0-C_\infty)\,\mathrm{erfc}\!\left(\dfrac{x}{2\sqrt{Dt}}\right)$，其中 erfc 为**余误差函数**。注意所有解里 $x$ 与 $t$ 都只以 $x/\sqrt{Dt}$ 的组合出现——这就是「**时间翻 4 倍，剖面长度翻 2 倍**」的根源。

### 2.16 晶体地层学（crystal stratigraphy）与 Mg–Fe 环带

**核心思想：晶体的成分环带就像树木的年轮。**

老师展示了一张斜长石（plagioclase）的**扫描电镜（SEM）**图像，可以看到许多**生长环带（growth zones）**。每一条环带记录了一组特定的**压力、温度或化学成分条件**，这些条件可以**用热力学与相图反推**（例如亮带对应低钙长石 anorthite 含量、暗带对应高 An 含量）。这套方法叫 **crystal stratigraphy（晶体地层学）**。

**最广泛使用的体系是橄榄石中的 Mg–Fe 环带**，原因有二（老师明确列出）：
1. **橄榄石在大量岩浆系统中都存在**，普适性强；
2. **Fe–Mg 环带的扩散「很有效率」**——扩散速率恰好落在能记录数天到数月尺度的窗口内。

**关键化学背景**：橄榄石 $(\mathrm{Mg,Fe})_2\mathrm{SiO_4}$ 是一个**固溶体（solid solution）**，两个端元是

- **镁橄榄石 forsterite (Fo)** = $\mathrm{Mg_2SiO_4}$，$X_{\mathrm{Fo}} = 1$
- **铁橄榄石 fayalite (Fa)** = $\mathrm{Fe_2SiO_4}$，$X_{\mathrm{Fo}} = 0$

因为 Mg 与 Fe 占据同一套晶格位置，**一个不进来另一个就出不去**——这叫**互扩散（interdiffusion）**，记作 $D_{\mathrm{Mg-Fe}}$。这与 H、Cr 这类**微量元素**不同，后者可以用简单的单组分扩散系数描述。

### 2.17 正环带与反环带（normal vs reverse zoning）

| | 定义 | 温度含义 | 岩浆过程 |
|---|---|---|---|
| **正环带 normal zoning** | 核部 Fo **高**、边部 Fo **低** | 记录**降温** | 与更冷的熔体混合、冷却 |
| **反环带 reverse zoning**（材料中也写作 inverse zoning） | 核部 Fo **低**、边部 Fo **高** | 记录**升温** | **岩浆补给（magma recharge）**：更热的熔体注入储库 |

**为什么？** 看 Fo–Fa 二元相图：高温端富 Fo，低温端富 Fa。降温时结晶出的橄榄石成分沿固相线向富 Fa 方向移动 → 边部 Fo 变低 = 正环带。反过来，要在已有的贫 Fo 核外面长出富 Fo 的边，**必须把温度升上去**，也就必须有**热的岩浆注入**。

**而岩浆补给正是触发火山喷发的机制之一。**

---

## 三、公式与图表

### 3.1 公式清单（保留原文形式 + 逐项解释）

| # | 公式（原文形式） | 符号说明 | 单位 | 适用条件 |
|---|---|---|---|---|
| 1 | $R = \dfrac{1}{\nu_i}\dfrac{\Delta[i]}{\Delta t}$ | $\nu_i$ 化学计量系数（产物正、反应物负） | mol L⁻¹ s⁻¹ | 任意反应；保证 $R>0$ |
| 2 | $R = k[\mathrm{A}]^{n_A}[\mathrm{B}]^{n_B}$ | $k$ 速率常数，$n$ 反应级数 | $k$ 单位随总级数变 | 级数只有基元反应可由计量数推得，**复杂反应必须实验测定** |
| 3 | $N_i = A\exp(-\varepsilon_i/k_BT)$ | $A$ 频率因子，$k_B$ Boltzmann 常数 | — | Boltzmann 能量分布 |
| 4 | $N_{E_a}/N = \exp(-E_a/k_BT)$ | 具备活化能的分子比例 | 无量纲 | — |
| 5 | $k = A\exp(-E_a/RT)$ | Arrhenius 方程 | — | $T$ 必须用 **K** |
| 6 | $J_i = vC_i$ | 平流通量 | mol m⁻² s⁻¹ | 需要外力驱动的整体运动 |
| 7 | $\dfrac{\partial C_i}{\partial t} = -v_x\dfrac{\partial C_i}{\partial x}$ | 一维平流方程 | — | 恒定速度、无源汇 |
| 8 | $J_i = -D_i\dfrac{\partial C_i}{\partial x}$ | **Fick 第一定律** | $J$: mol m⁻² s⁻¹；$D$: **m² s⁻¹** | 稳态；负号 = 顺梯度向下 |
| 9 | $D_i = D_0\exp(-E_a/RT)$ | **扩散系数的 Arrhenius 关系** | $D_0$: m² s⁻¹；$E_a$: kJ mol⁻¹；$R = 8.314\times10^{-3}$ kJ mol⁻¹ K⁻¹ | $T$ 用 **K**；$(D_0,E_a)$ 对每个「元素+矿物」组合特有 |
| 10 | $\dfrac{\partial C_i}{\partial t} = D_i\dfrac{\partial^2 C_i}{\partial x^2}$ | **Fick 第二定律** | — | 瞬态；$D$ 视为常数；一般需数值求解 |

**典型数值（来自 Practical 数据，1000–1300 °C 橄榄石中）：**

| 扩散物种 | $D_0$ (m²/s) | $E_a$ (kJ/mol) | $D$ 量级 @ ~1200 °C | 相对速率 |
|---|---|---|---|---|
| **H**（氢，微量元素） | $10^{-1.4} \approx 3.98\times10^{-2}$ | 258 | ~$10^{-11}$ m²/s | 最快 |
| **Mg–Fe**（互扩散） | 实验测定（Chakraborty 1997） | — | ~$10^{-16}$ m²/s | 中等 |
| **Cr**（铬，微量元素） | $10^{-5.31} \approx 4.90\times10^{-6}$ | 352 | ~$10^{-18}$ m²/s | 最慢 |

**跨越约 7 个数量级。** 这是本周最需要形成直觉的数字。

### 3.2 图表文字详解

#### 图 A：反应级数示意图（Slide 11）

- **横轴**：反应物浓度 $[\mathrm{A}]$；**纵轴**：反应速率 $R$。
- **零级**：一条**水平直线**——浓度怎么变，速率不动。
- **一级**：一条**过原点的直线**，斜率即 $k$。
- **二级**：一条**向上弯曲的曲线**（抛物线），浓度加倍速率变 4 倍。
- **读法**：拿到实验数据，先看 $R$–$C$ 图是平的、直的还是弯的，即可判断级数。

#### 图 B：活化能势垒图（Slide 16 / Part 3）

- **纵轴**：能量；**横轴**：反应进程。
- 曲线从反应物能级上升到一个**峰**，再下降到产物能级。**峰顶与反应物能级之差就是 $E_a$**。
- **读法**：能量低于 $E_a$ 的碰撞 → A 撞上 B 又弹开，无反应；能量高于 $E_a$ → 形成产物 AB。
- **关键结论**：$E_a$ 是一个**门槛（threshold）**，不是「反应放出/吸收的能量」——后者是反应物与产物能级之差 $\Delta H$。

#### 图 C：扩散均匀化卡通（Slide 20 / Part 4）

- 左框 $t_1$：一个盒子，**左半边密布紫色分子、右半边空白**——最大浓度梯度。
- 右框 $t_2$：**紫色分子在整个盒子里均匀分布**——梯度已被抹平。
- **读法**：这就是扩散的「终点」。终点之前的任何中间状态都携带**时间信息**，这正是扩散计时的原理。

#### 图 D：Fick 第二定律的理论解族（Slide 25 / Part 4，老师讲了两遍）

- **横轴**：距离 $x$（可理解为矿物颗粒内从核部到边部的位置）。
- **纵轴**：**归一化浓度 $C/C_0$**（当前浓度除以初始浓度）。
- **曲线族**（老师给的标注）：
  - $t = 0$：**一条陡峭的阶跃（step）**——从高浓度平台**垂直**跌到零，转折发生在极短距离内。
  - $t = 0.1$、$t = 1$（黄色曲线）：阶跃开始**变圆、变缓**，高浓度侧下凹、低浓度侧上凸。
  - $t = 10$（灰色曲线）：剖面**明显更长更平滑**，向两侧延伸的「尾巴」更远。
  - $t \to \infty$：**一条完全水平的直线**——完全均一化。
- **怎么读结论**：
  1. **剖面越长越平滑 → 扩散时间越长**（或温度越高）。
  2. 所有曲线**交于中点**且中点浓度不变（对称的阶跃初始条件）。
  3. 关键在于**长度尺度 $\propto \sqrt{Dt}$**——所以时间从 1 变到 10（10 倍），剖面只加长约 3 倍。**这是为什么扩散计时对「长时间」不敏感、对「短时间」很灵敏。**

#### 图 E：橄榄石 Fo–Fa 二元相图（Slide 29–31 / Practical Figure 3）

- **横轴**：$X_{\mathrm{Fo}}$，从 0（**铁橄榄石 fayalite**，纯 Fe 端元）到 1（**镁橄榄石 forsterite**，纯 Mg 端元）。
- **纵轴**：温度 $T$。
- **三个区域**（自上而下）：
  - 上方：**液相区（liquid）**；
  - 中间的透镜状两相区：**液相 + 橄榄石（liquid + olivine）**，上界是**液相线 liquidus**、下界是**固相线 solidus**；
  - 下方：**橄榄石固溶体区（olivine solid solution）**。
- **怎么读出环带**（老师讲的路径）：
  1. 橄榄石在深部岩浆房、较高温度下开始结晶，得到富 Fo 的核部成分 $C_0$。
  2. 熔体把晶体搬运到地壳浅部，**温度下降**。
  3. 降温时橄榄石成分**沿固相线向左（富 Fa 方向）移动**，新结晶的一代橄榄石成分为 $C_1 \ne C_0$，$X_{\mathrm{Fo}}$ 更低。
  4. 结果：**核高 Fo、边低 Fo 的正环带**。
  5. 要产生**反环带**，就必须在相图上**反向移动，即升温** → 需要**热岩浆补给**。

⚠️ **Practical 明确警告**：这张相图是**纯橄榄石二元系**的，而你分析的是**玄武岩**。所以**绝对温度是不对的**，只能做**定性/相对温度**的判断。

#### 图 F：橄榄石 Mg–Fe 环带剖面（Slide 29–31）

- **横轴**：从**核（core）到边（rim）**的距离（µm）。
- **纵轴**：$X_{\mathrm{Fo}}$（forsterite 含量）。
- **初始（生长刚结束时）**：一个**阶跃剖面**——高 Fo 的核，突然跌到低 Fo 的边。
- **经历高温停留后**：Mg 从高浓度的核向低浓度的边扩散（Fe 反向），阶跃**松弛（relax）成一条平滑的 S 形下降曲线**。
- **测量方法**：用**电子探针（electron microprobe，基于 X 射线光谱学）**沿核—边剖面逐点分析，算出 Fo 含量。
- **反解时间**：假定一个 $T$ 和 $P$（从而得到 $D$），用 Fick 第二定律的数值解拟合实测剖面，得到 $t$。

#### 图 G：Laki 1783–84 案例（Slide 32）

- SEM 背散射图上，橄榄石有**暗核 + 亮边**。老师解释：**暗 = 高 Fo（约 Fo 80）**，**亮 = 低 Fo（约 Fo 76）**。
- 拟合图：**菱形符号 = 实测 Fo 值**；曲线 = 模型剖面。**最佳拟合略低于 9 天**。
- **结论**：Laki 的橄榄石记录了**喷发前仅 6–10 天**与更冷熔体的混合。
- **社会意义（老师强调）**：过程这么快，**留给我们的预警时间极短**，这正是精确预测火山喷发依然极其困难的原因之一。

📎 **背景补充**：SEM 背散射（BSE）图像亮度正比于**平均原子序数**。Fe（Z=26）远重于 Mg（Z=12），所以**富 Fe（低 Fo）的部分更亮、富 Mg（高 Fo）的部分更暗**。这解释了老师说的「暗核=高 Fo、亮边=低 Fo」，材料本身没有解释成像原理。

#### 图 H：Etna 案例（Slide 33 + Slide 34）

- 一颗**直径略小于 1 mm** 的橄榄石。剖面显示**核 Fo ≈ 75，边 Fo ≈ 82** → **反环带**。
- ⚠️ 老师特别提醒：剖面**最外侧那个陡降的部分已经在橄榄石晶体之外了，不算数**——那是基质，不能纳入拟合。
- **建模结果：约 40 天**形成该剖面。
- **解释**：需要热的岩浆补给把温度提上去。**岩浆补给可能是喷发的触发机制。**
- **Slide 34「但岩浆通道系统可能更复杂」**：同一批样品的多颗橄榄石记录了不同故事——
  - 反环带（贫 Fo 核 + 富 Fo 边）→ 升温；
  - 正环带（富 Fo 核 + 贫 Fo 边）→ 降温；
  - **既有升又有降的复合环带**：中等 Fo 的核 → 向边略升（升温）→ 最外缘降到 Fo 75（冷却）。
- **老师的三点总结**：
  1. **每颗晶体记录的故事略有不同**；
  2. **有些晶体只记录了部分历史**；
  3. **晶体大小很重要——小晶体里扩散更容易穿透整颗晶体**（信息更容易被抹掉）。

---

## 四、课堂补充

以下内容基于 10 月 27 日约 5,700 词的完整课堂录音，提炼**幻灯片上没有、老师口头讲的部分**。

### 4.1 课程节奏与评估安排（考试相关，务必注意）

- **本周是高温地球化学部分的最后一周**。老师原话："Since last week you were having me for the high temperature part of geochemistry... After reading week you'll have Greg Holland for more low temperature applications to geochemistry."
- **周三上午有配套 practical**，是**计算机机房课**，主题就是动力学与扩散。
- ⭐ **周五发布占本模块 20% 的 coursework**，学生有**两周**时间完成并提交。（与课程大纲的 "Report handout week 5, hand in week 7, 20%" 一致。）**这意味着本周内容与 coursework 直接相关。**

### 4.2 老师亲口给出的「本周中心论点」

> **"Without kinetics, there would be no igneous or metamorphic petrology."**

紧接着补一句：**"Basically everything at the Earth's surface, given a very long period of time, a lot of minerals just transforms to clay because the surface contains a lot of moisture."**

——这句话把「动力学」从一个抽象的化学话题变成了**整个岩石学学科存在的前提**。如果考试问「为什么动力学对地质学重要」，这是标准答案的骨架。

### 4.3 「部分达到平衡」是计时的前提

老师反复强调：**"most of the time we partially attain equilibrium. So we're getting towards equilibrium, but we're not getting there entirely."**

这句话是**扩散计时的全部合法性来源**：
- 完全没反应 → 没有剖面，没有信息；
- 完全平衡 → 剖面被抹平，信息也没了；
- **只有「部分平衡」才携带时间信息。**

老师列出可以由此测定的问题：岩浆结晶要多久？岩浆储库补给要多久？

### 4.4 气候反馈：一个不平衡的收支表（Slide 5 的口头展开）

老师把动力学推广到气候：**动力学控制着地球各储库之间的碳通量**。

- 过去两个世纪、尤其最近几十年，人类**极快**地向大气释放 CO₂ —— **快过程**。
- 地表**硅酸盐风化（silicate weathering）**确实会消耗一部分 CO₂ —— **但慢得多的过程**。
- **结论：这个系统不平衡。"If it was balanced, it would be great, but it's not."**

老师明确说这不是本课的重点，但**"the principles we're going to discuss apply across a broad range of topics"**。

📎 **背景补充**：这里的对比正是「**碳酸盐—硅酸盐循环（Walker feedback）**」的核心。硅酸盐风化的特征时标是 10⁵–10⁶ 年量级，而化石燃料燃烧的时标是 10²年量级——**相差三到四个数量级**，所以这个负反馈根本来不及跟上人为排放。材料未给出具体数字，此为补充。

### 4.5 老师对「稀释系统」的口头强调

幻灯片只写了 "Reactants in geochemical systems are often isolated from each other"。老师的展开更有针对性：

> **"In real life, geochemical systems tend to be dilute systems... if they're very dilute in your system, the chances they'll collide with one another are low, even if you're above activation energy."**

**要点：能量够 ≠ 反应会发生。还得先把反应物送到一起。** 这就是为什么动力学讲完速率定律必须讲质量传输。

### 4.6 老师专门澄清的两个符号陷阱

1. **$D$ 的双重含义**（见 §2.13）——扩散系数 vs 分配系数。老师说 "That's a bit unfortunate that they've got the same letters for these two."
2. **反应速率符号必须为正**——所以对反应物要配负的化学计量系数。

### 4.7 老师对 Fo–Fa 相图的口头演绎

老师在讲台上现场走了一遍相图路径（比幻灯片详细）：

> "初始时你的橄榄石晶体在岩浆房深部结晶，比如说略低于 1500 °C。熔体把橄榄石晶体带到地壳更高的位置，温度下降。随着降温，橄榄石的成分沿固相线演化，第二代橄榄石会以一个不同于 $C_0$ 的浓度 $C_1$ 结晶出来。"

然后：**"Now you can do a profile using instruments in the lab. You can measure the concentration profile across your olivine grain from the core to the rim."**

再然后：**"If you stay at fairly high temperature in that state, you will have diffusion... magnesium will diffuse from the core to the rim, and it will start to homogenize the concentration gradient. So instead of a very sharp step change, you will have more of a smooth decrease from a magnesium-rich core to a magnesium-[poor rim]."**

📎 **背景补充（数值校核）**：老师口述的「略低于 1500 °C」在**纯 Fo–Fa 二元系**中偏低——纯镁橄榄石熔点约 **1890 °C**、纯铁橄榄石约 **1205 °C**，Fo80–90 的液相线在 1 atm 下约 1700–1800 °C。真实玄武岩中橄榄石的结晶温度反而是 **1100–1250 °C** 左右（Practical 的扩散模型正是用 **1100 °C**）。所以「1500 °C」既不是纯系的正确值也不是玄武岩的实际值，应理解为**板书示意的随口数字**。Practical 也明确警告：**这张相图的绝对温度对玄武岩不适用，只能做定性判断。**

### 4.8 老师对「晶体大小」这一变量的补充

幻灯片没有提，但老师在收尾时说：

> **"It will also depend on the size of the crystal. Smaller crystals, things will diffuse more efficiently across smaller crystals than across bigger crystals."**

**含义**：小晶体的核—边距离短，扩散更容易贯穿整颗晶体、把环带完全抹平。所以**小晶体往往只保留最近一次事件的记录，甚至什么都不剩；大晶体才可能保存较长的历史。** 这是做样品选择时的实际考量。

### 4.9 老师用的生活类比（记忆锚点）

- **平流** = **把牛奶搅进茶里**（stirring milk into tea）——需要你出力。
- **树的年轮** = **晶体的生长环带**（"In a sense, it's very similar to the rings in a tree."）。

### 4.10 老师提到但未展开的技术细节

- **电子探针（electron microprobe）** 是测成分剖面的仪器，"based on X-ray spectroscopy"。
- 拟合剖面前**必须假定一个温度和压力**，因为 $D$ 依赖于它们。这是扩散计时的**最大不确定度来源**（老师未明说，见 §6）。
- 求解 Fick 第二定律 **"we mostly use computers and spreadsheets to solve it"** ——直接预告了周三 Practical 的形式。

### 4.11 进阶阅读（Slide 6 给出）

- **Misra, Chapter 9** —— "detailed and mathematical"（详细且偏数学）
- **White, Chapter 5** —— "comprehensive but readable"（全面且好读）

老师给出的这两句评语本身就是选书建议：**想补数学推导看 Misra，想先建立整体图像看 White。**

---

## 五、Practical 要点

**Practical 5：Timescales of magmatic processes（岩浆过程的时间尺度）**，Dr David Neave 主讲，配套文件 `EART26201_Practical5.xlsx`。两道题，各约 60 分钟。

### 5.0 关于大型数据表的读取策略（方法说明）

`EART26201_Practical5_feedback.xlsx.md` 共 **222 行、约 30,488 词**——它是把整个 Excel 工作簿倾印成 Markdown 的产物，其中绝大部分行是**每行数千字符的超宽数值行**（Question 2 model 表单的单行长度达 5,000+ 字符）。**信息密度极低而 token 消耗极高。**

本笔记采用了**限流读取策略**：
1. 完整读取文件**前 55 行**（Question 1 全部实验数据与计算结果，行较短）；
2. 用行长统计定位三个工作表的边界（第 7–52 行 = Question 1；第 54–109 行 = Question 2 model；第 111–165 行 = Question 2 data；第 167–222 行 = Question 2 answer）；
3. 对超宽行**只截取前 300–700 字符读取表头与首列**，另单独抽取答案表的**最右侧汇总列**；
4. **中间的纯数值网格一律不逐行读取**。

**因此本节描述的是数据表的结构、变量、单位、量级与结论，不搬运原始数据。** 我已对能校核的每一个数值做了独立复算（见 §5.2、§5.4），结果一致。

### 5.1 目标（原文的 6 条 Goals）

学完本 practical 应能：
1. 描述**温度与扩散率之间的 Arrhenius 性质**；
2. 解释**为什么同一颗晶体中不同元素会记录不同的事件**；
3. 描述**什么控制着晶体达到热力学平衡的速率**；
4. 解释**晶体的成分环带如何记录岩浆混合的时间尺度**；
5. 对环带晶体**应用简单扩散模型**估算混合时间尺度；
6. **由简单扩散模型重建火山的喷发前历史**。

反馈还指出：这些主题会在 **EART22200（火成矿物与过程）** 与 **EART24200（变质矿物与过程）** 中再次遇到；另有 **Blackboard 小测**覆盖相关内容。

### 5.2 Question 1：扩散系数与 Arrhenius 关系（60 分钟）

**方法**：用 Excel 处理三套橄榄石扩散数据。

**(a) 数据结构（Chakraborty 1997 的 Mg–Fe 互扩散实验）**
表头为：`Experiment | T (°C) | D (m²/s) | | T (K)`。共 **15 条实验记录**（编号形如 OLID-3、OLID-5、OLID-9…OLID-207），部分实验号重复出现（同一实验的多次测定）。
- **温度范围**：980–1300 °C；
- **$D_{\mathrm{Mg-Fe}}$ 范围**：约 $1.6\times10^{-18}$ 到 $4.1\times10^{-16}$ m² s⁻¹ ——**在 320 °C 的温度跨度内变化了约 2.4 个数量级**；
- **必做的第一步**：$T(\mathrm{K}) = T(°\mathrm{C}) + 273.15$。

**(a) 答案要点**：纵轴（$D$）**必须用对数坐标**，横轴 $T$ 用线性坐标。理由：$D$ 跨越两个多数量级，线性纵轴上除了最高温的一两个点，其余全部挤在零附近。

**(b) 趋势线类型**：**指数（exponential）** —— 因为 $D = D_0 e^{-E_a/RT}$。

**(c) 1350 K 时的 $D_{\mathrm{Mg-Fe}}$**：约 $\mathbf{10^{-17}}$ **m² s⁻¹**。
> ✅ 校核：1350 K = 1076.85 °C。数据表中 1050 °C 的两个值为 $1.2\times10^{-17}$ 和 $9.4\times10^{-18}$，1100 °C 的两个值为 $1.0\times10^{-17}$ 和 $7.1\times10^{-18}$ ——答案自洽。

**(d) H 在橄榄石中的扩散**（Demouchy & Mackwell 2006）
给定 $D_0 = 10^{-1.4}$ m² s⁻¹（$= 3.981\times10^{-2}$）、$E_a = 258$ kJ/mol、$R = 8.314\times10^{-3}$ kJ mol⁻¹ K⁻¹，在合适温区（**950–1300 °C，步长 50 °C，共 8 个点**）用 Arrhenius 式算 $D_{\mathrm{H}}$。
- 结果范围：$3.82\times10^{-13}$（950 °C）到 $1.08\times10^{-10}$（1300 °C）m² s⁻¹。
> ✅ 我独立复算了区间两端：950 °C → $3.817\times10^{-13}$；1300 °C → $1.079\times10^{-10}$，与表中一致。
- **注意**：H 在橄榄石中是**微量元素**，所以可以用**简单扩散系数**，不必考虑互扩散。

**(e) H vs Mg–Fe 的对比（重点答案）**
> **"H diffusion is about five orders of magnitude faster than Mg–Fe interdiffusion, so H will attain thermodynamic equilibrium much sooner."**

**原因（两条，都要答）**：
1. **H 是极小的离子（本质上就是一个质子）**，可以从橄榄石晶格的空隙中穿过，而更大的离子过不去；
2. **作为微量组分，H 不必与构成晶格的物种交换**；电荷平衡由**空位（vacancies）**实现——即晶格中偶尔缺失 Mg 或 Fe 离子。

**(f) Cr 在橄榄石中的扩散**（Ito & Ganguly 2006）
$D_0 = 10^{-5.31}$ m² s⁻¹（$= 4.898\times10^{-6}$）、$E_a = 352$ kJ/mol，同样 950–1300 °C。
- 结果范围：$4.54\times10^{-21}$（950 °C）到 $1.00\times10^{-17}$（1300 °C）m² s⁻¹。
> ✅ 复算 950 °C：$4.542\times10^{-21}$，一致。

**(g) Cr vs Mg–Fe**：
> **"Cr diffusion is about two orders of magnitude slower than Mg–Fe interdiffusion, meaning that Mg–Fe will attain thermodynamic equilibrium before Cr."**

**(h) 元素—过程匹配（这是全题的落脚点，考点）**

| 过程 | 时间尺度 | 记录它的元素 | 逻辑 |
|---|---|---|---|
| i. **浅部地壳的岩浆混合**，喷发前**数月** | 月 | **Mg–Fe** | 中等扩散速率 |
| ii. **岩浆的 H₂O 脱气**，喷发前**数小时** | 小时 | **H** | 最快 |
| iii. **深部地壳的岩浆结晶**，喷发前**数十年** | 年—十年 | **Cr** | 最慢 |

**核心思想（务必内化）**：**扩散速率越快的元素，其「记忆」被抹得越快，因此只能记录最晚近的事件；扩散速率越慢的元素，保存的记忆越古老。同一颗晶体因此是一台「多时钟」记录仪。**

配图 Figure 1 是**岩浆通道系统（magma plumbing system）的卡通图**，从深部地壳（iii）经浅部地壳岩浆房（i）到近地表脱气（ii），三个位置分别标注了对应的元素。

### 5.3 Question 2：由橄榄石估算岩浆混合时间尺度（60 分钟）

（致谢新加坡的 Fidel Costa 与海德堡的 Maren Kahl 提供材料。）

**物理背景**：岩浆混合把 Mg/Fe 含量不同的岩浆带到一起，其携带的橄榄石晶体的 Mg、Fe 含量因而通过扩散逐步均匀化。**如果扩散在达到平衡之前被打断（喷发冷却），且已知扩散系数，就能反推「从混合开始到被打断」的时间。**

#### 数据结构（限流读取所得）

工作簿有 **3 个相关表单**：

**① `Question 2 model`（第 54–109 行）** —— 一个求解 Fick 第二定律的**显式有限差分模型**。
- **可调参数区（原文标注颜色）**：
  - 绿色单元格 **E6 = Rim XFo**、**E7 = Core XFo** ——剖面两端的成分；
  - 淡黄色单元格 = 扩散时间与温度。
- **模型参数（读到的实例值）**：
  | 参数 | 值 | 单位 |
  |---|---|---|
  | $T$ | 1100 | °C |
  | $f\mathrm{O_2}$（氧逸度） | $3\times10^{-7}$ | bar |
  | Minimum $X_{\mathrm{Fo}}$ | 0.7 | — |
  | $D_0$ | $6.166\times10^{-10}$ | m² s⁻¹ |
  | $E_a$ | 201 | kJ mol⁻¹ |
  | $D$（算出的） | $4.5297\times10^{-4}$ | **µm² s⁻¹** |
  | $\Delta x$（空间步长） | 5 | µm |
  | $\Delta t$（时间步长） | 7200 | s（= 2 小时） |
  | **稳定性条件** | **0.1305（要求恒 < 0.5）** | 无量纲 |
- **网格规模**：空间上 $x$ 从 **5 µm（rim）到 255 µm（core）**，步长 5 µm，共 **51 个节点**；时间上从 **0 到 849,600 s（= 236 小时 ≈ 9.83 天）**，步长 7200 s，共 **119 个时间列**。每个时间列同时输出 `DFeMg` 与 `C` 两个字段（$D$ 随成分变化，所以逐格重算）。
- 表右端还有**时间单位换算列**：秒 / 小时 / 天 / 月 / 年。

> ✅ **稳定性条件的校核**：$D\Delta t/\Delta x^2 = (4.5297\times10^{-4}\times7200)/5^2 = 3.2614/25 = 0.1305$ ✓ 与表中数值精确吻合。这确认了模型使用的是**显式 FTCS 格式**，其 von Neumann 稳定判据正是 $D\Delta t/\Delta x^2 < 0.5$。
> 📎 **背景补充**：这条判据材料只写了 "stability condition needs to be always < 0.5" 而没说原因。原因是：显式差分格式中，如果单个时间步内「扩散走的距离」超过半个网格，数值解会振荡发散。**实际含义是：你把温度调高（$D$ 变大）后，必须同时缩小 $\Delta t$，否则模型会「炸掉」**——这正是反馈里那句 "if you change the values too much you may break the model!" 的技术原因。
> 另外，模型中 $D$ 逐格不同（读到的两个值：$X_{\mathrm{Fo}}=0.7$ 处为 $4.53\times10^{-4}$ µm²/s，$X_{\mathrm{Fo}}=0.55$ 处为 $1.277\times10^{-3}$ µm²/s，比值 2.82）。这正是 $10^{3(X_{\mathrm{Fe}}-0.1)}$ 成分校正项的效果（$10^{3(0.45-0.1)}/10^{3(0.30-0.1)} = 10^{0.45} = 2.82$ ✓）——即 **Mg–Fe 互扩散在富 Fe 的橄榄石中显著更快**，且依赖 $f\mathrm{O_2}$。材料的正文未展开这套 Dohmen & Chakraborty 型参数化，但表单里的 $f\mathrm{O_2}$ 列和逐格变化的 $D$ 值说明模型确实内建了它。

**② `Question 2 data`（第 111–165 行）** —— **12 颗橄榄石的实测（教学合成）成分剖面**。
- 表头：`Zone | x (um) | Olivine 1 … Olivine 12`；
- 首列 Zone 只在首行标 `Rim`、末行标 `Core`；
- $x$ 从 **5 到 255 µm，步长 5 µm，共 51 行**；
- 数据是 $X_{\mathrm{Fo}}$，**全部 12 颗的 rim 值均为 0.70**（代表混合后共同的寄主岩浆），**core 值只有三种：0.90、0.80、0.55**。

**③ `Question 2 answer`（第 167–222 行）** —— 参考答案：12 个时间尺度 + 右侧一张按核部成分分组的汇总表。

#### 操作流程（原文步骤）

1. 从 `Question 2 data` 一次复制一颗橄榄石的剖面；
2. **粘贴「值」（paste values，右键 → 粘贴选项 → 123 图标）** 到 `Question 2 model` 的 A3 起的淡绿色单元格 `Measured distribution of XFo`；
3. 调 E6（Rim XFo）与 E7（Core XFo），让模型曲线族**叠合到**实测剖面上；
4. **目视比较实测剖面落在哪条彩色（不同时间）曲线附近**，粗估时间尺度；
5. 记录**环带类型（正/反）**与**时间估计**。

#### 关键结论

**(c) 环带统计**：**8 颗正环带，4 颗反环带。**

**(d) 三个橄榄石种群（populations）** —— 把每颗橄榄石的**核部 $X_{\mathrm{Fo}}$ 对估算时间作图**，会清晰分成三簇：

| 种群 | 核部 $X_{\mathrm{Fo}}$ | 颗数 | 时间尺度（各颗，小时） | **平均** | 环带类型 |
|---|---|---|---|---|---|
| A | **0.90** | 5 | 228, 226, 224, 180, 172 | **≈ 206 h（≈ 8.6 天）** | normal 正环带 |
| B | **0.80** | 3 | 22, 18, 16 | **≈ 19 h** | normal 正环带 |
| C | **0.55** | 4 | 44, 42, 38, 36 | **= 40 h** | reverse 反环带 |

> ✅ 校核：5 + 3 + 4 = 12 ✓；正环带 5 + 3 = **8** ✓，反环带 **4** ✓ ——与 (c) 的答案完全自洽。反馈正文写的「~19、~40、~206 小时」与表单里的均值 18.67、40、206 一致。

**(e) 重建喷发前历史（本 practical 的最终产出）**

按**时间倒序（最早的事件时间最长）**排列：

1. **≈ 206 小时（约 8.6 天）前**：核部 $X_{\mathrm{Fo}} = 0.90$ 的**正环带**橄榄石被混入与 $X_{\mathrm{Fo}} = 0.70$ 平衡的岩浆中。→ 这批晶体来自**最热的环境**（相图上 Fo 越高 = 温度越高）。
2. **≈ 40 小时前**：核部 $X_{\mathrm{Fo}} = 0.55$ 的**反环带**橄榄石被混入。→ 这批晶体来自**比晶体边部形成环境更冷**的环境。
3. **≈ 19 小时前**：核部 $X_{\mathrm{Fo}} = 0.80$ 的**正环带**橄榄石被混入。→ 来自**比边部形成环境略热**的环境。

**判读规则（一定要记住）**：**核部 $X_{\mathrm{Fo}}$ > 边部 0.70 → 正环带 → 晶体来自更热的储库；核部 $X_{\mathrm{Fo}}$ < 0.70 → 反环带 → 晶体来自更冷的储库。**

反馈强调：虽然这个练习**大大简化了**天然岩浆系统的复杂性与扩散建模的过程，**但原理与火山学家真实使用的方法完全类同**。配图 Figure 4 来自 **Kahl et al. (2017)**，展示了 **Etna 1669 年大喷发**前的岩浆相互作用与上升路径。

**(f) 敏感性测试（两条重要结论）**

1. **改变扩散时间**：时间增量越长，**剖面越长、越平滑**；数月到数年的长时间尺度对应**数百 µm 量级**的剖面；最终剖面会变平。
2. **改变温度的效果是"dramatic"**：**温度线性上升，算出的扩散时间急剧下降，因为扩散是 Arrhenius 过程。**
   > ⚠️ 这是本 practical 最重要的方法学警示：**温度假设的一点误差，会被指数放大成时间估计的巨大误差。**

### 5.4 评分与常见错误（由反馈的措辞与答案结构推断）

- **必须写出「为什么」而不只是「多少」**：(e) 和 (g) 的参考答案都由「快多少 / 慢多少」+「离子半径与晶格机制」两部分组成，**只答数量级不给机制会失分**。
- **单位与温标**：忘记 °C→K 转换是最常见的硬错误（直接把答案带偏几十个数量级）；$E_a$（kJ/mol）与 $R$（kJ mol⁻¹ K⁻¹）必须配套。
- **Arrhenius 式中的负号**：反馈原文特意提醒 **"remember the minus sign"** ——漏了负号会得到荒谬的巨大 $D$。
- **对数坐标**：(a) 用线性纵轴是典型错误。
- **粘贴方式**：必须**只粘贴值**，直接粘贴会带过来公式并破坏模型。
- **剖面边界的判读**：老师在课上强调，Etna 那个剖面**最外侧的陡降在晶体之外**，不能纳入。

---

## 六、易错点 / 重点难点

### 6.1 概念层面

1. **热力学 ≠ 动力学。** 热力学预测「终点」，动力学决定「速度」和「是否到得了」。**一个相图上「不该存在」的矿物组合（如地表的橄榄岩、蓝片岩）不是热力学错了，而是动力学没让它反应完。**

2. **活化能 $E_a$ 不是反应热 $\Delta H$。** $E_a$ 是能垒的**高度**（决定速率），$\Delta H$ 是反应物与产物的**能级差**（决定热效应）。催化剂降低 $E_a$ 但不改变 $\Delta H$。

3. **反应级数不能从化学方程式「读」出来** —— 除非它是基元反应。地球化学反应几乎都是多步复杂反应，**级数必须实验测定**。

4. **CO₂ 水合是「二级还是一级」取决于语境**：严格是二级；在水过量的天然体系中表现为**对 CO₂ 的一级（准一级）**。考试时要能说清「为什么可以降级」。

5. **扩散一直在发生**，只是在均匀体系里净通量为零、你「看不见」；**Fick 第一定律里的负号不是装饰**，它编码了「通量沿浓度下降方向」；**$D$（扩散系数）与 $D$（分配系数）同字母**，看语境判断（三点老师均专门强调过，见 §2.11、§2.13）。

6. **封闭温度（closure temperature）不是矿物的固有常数**：它取决于**元素、矿物、冷却速率、晶体尺寸**。材料只说了「低于它扩散极少」，没有展开。
   📎 **背景补充**：更精确的表述是 Dodson (1973) 的封闭温度公式，它显式包含冷却速率——冷却越快，封闭温度越高。这一点在 Week 12 的同位素定年里会再遇到。

### 6.2 计算层面

7. **温度必须用开尔文**（$T(\mathrm{K}) = T(°\mathrm{C}) + 273.15$，不是 273）；**单位必须配套**（$E_a$ 用 kJ/mol 配 $R = 8.314\times10^{-3}$，用 J/mol 配 $R = 8.314$）；**指数上的负号别漏**（Practical 原文就在提醒）。这三条是最常见的硬错误。

8. **对数坐标不是可选项。** $D$ 跨越 7 个数量级，任何 $D$ 对 $T$ 的图都必须用对数纵轴。
   📎 **背景补充**：更标准的做法是画 **Arrhenius 图（Arrhenius plot）**：横轴 $1/T$（或 $10^4/T$），纵轴 $\ln D$，此时数据落在**一条直线**上，**斜率 $= -E_a/R$、截距 $= \ln D_0$**，可直接回归出 $E_a$ 和 $D_0$。本课 Practical 用的是「$T$ 线性 + $D$ 对数 + 指数趋势线」的简化版，效果类似但读不出 $E_a$。这是考试可能考的延伸。

9. **$\sqrt{Dt}$ 的非线性直觉。** 剖面长度正比于 $\sqrt{Dt}$：**时间要变 4 倍，剖面才长 2 倍。** 所以短时间尺度的估算比长时间尺度精确得多。

10. **温度不确定度会被指数放大。** 这是扩散计时最大的系统误差来源，Practical (f) 的答案专门点了这一条。

### 6.3 判读层面

11. **正环带 / 反环带的方向千万别记反。**
    - **正环带 normal**：核 Fo **高** → 边 Fo **低** = **降温 / 冷却**；
    - **反环带 reverse（= inverse）**：核 Fo **低** → 边 Fo **高** = **升温 / 岩浆补给**。
    记忆法：**「正常」的岩浆房是在冷却的，所以「正环带 = 冷却」。**

12. **SEM 图像的亮暗要和 Fo 含量正确对应**：暗 = 高 Fo（富 Mg），亮 = 低 Fo（富 Fe）。（📎 原因见 §3.2 图 G 的背景补充。）**剖面端点还必须落在晶体内**，超出晶体边界的数据点必须剔除。

13. **不同元素记录不同事件，不是矛盾而是特性。** 同一颗晶体的 H、Mg–Fe、Cr 给出的时间不一样，是因为它们的「记忆时长」不同（小时 / 月 / 十年）。

14. **单颗晶体的记录可能不完整。** 小晶体扩散更容易贯穿、抹掉早期信息；因此**必须统计一批晶体**（本 practical 用 12 颗）才能得到种群结构。

15. **Fo–Fa 二元相图不能给玄武岩的绝对温度**，只能做相对/定性判断；**Practical 的时间尺度（19/40/206 小时）与讲课案例（Laki 6–10 天、Etna ~40 天）也是不同的数据集**，不要混记——Practical 的 12 颗橄榄石是教学数据集，Etna 的 Figure 4 只是示范真实研究的样子。

---

## 七、本周术语表

| 中文 | English | 简要含义 |
|---|---|---|
| 动力学 | kinetics | 研究反应速率及趋近平衡的速度 |
| 热力学 | thermodynamics | 研究给定条件下的平衡态 |
| Gibbs 自由能 | Gibbs free energy ($G$) | 平衡相组合具有最低 $G$ |
| 反应速率 | reaction rate ($R$) | 单位时间的浓度变化，按计量数归一 |
| 瞬时变化 | instantaneous change | 微分形式的速率 |
| 速率定律 | rate law | $R = k[\mathrm{A}]^{n_A}[\mathrm{B}]^{n_B}$ |
| 速率常数 | rate constant ($k$) | 速率定律中的比例常数，含能量信息 |
| 反应级数 | reaction order | 速率定律中浓度的指数 |
| 总反应级数 | overall reaction order | 各分级数之和 |
| 基元反应 | elementary reaction | 单步反应，级数可由计量数推得 |
| 零级 / 一级 / 二级反应 | zeroth / first / second order | 速率与浓度无关 / 成正比 / 与平方成正比 |
| 准一级反应 | pseudo-first-order reaction | 📎 某反应物过量、浓度视为常数导致的表观降级 |
| 碳酸 | carbonic acid ($\mathrm{H_2CO_3}$) | CO₂ 水合产物 |
| 活化能 | activation energy ($E_a$) | 反应发生所需的能量门槛，kJ/mol |
| 频率因子 | frequency factor ($A$) | Boltzmann/Arrhenius 式中的前因子 |
| Boltzmann 常数 | Boltzmann constant ($k_B$) | 单分子尺度的气体常数 |
| 气体常数 | gas constant ($R$) | $8.314\times10^{-3}$ kJ mol⁻¹ K⁻¹ |
| Arrhenius 关系 | Arrhenian relationship | $k$ 或 $D$ 随 $T$ 的指数依赖 |
| Arrhenius 图 | Arrhenius plot | 📎 $\ln D$ 对 $1/T$ 作图，斜率 $=-E_a/R$ |
| 质量传输 | mass transfer | 把反应物送到一起的物理过程 |
| 平流 / 对流搬运 | advection | 物质的整体运动，需外力 |
| 扩散 | diffusion | 沿浓度梯度的自发运动 |
| 通量 | flux ($J$) | 单位时间单位面积通过的物质量 |
| 浓度梯度 | concentration gradient | $\partial C/\partial x$ |
| Fick 第一定律 | Fick's first law | $J = -D\,\partial C/\partial x$ |
| Fick 第二定律 | Fick's second law | $\partial C/\partial t = D\,\partial^2C/\partial x^2$ |
| 扩散系数 / 扩散率 | diffusion coefficient / diffusivity ($D$) | m² s⁻¹；越大扩散越快 |
| 指前因子 | pre-exponential factor ($D_0$) | Arrhenius 式中的常数，元素—介质特有 |
| 分配系数 | partition coefficient ($D$) | ⚠️ 与扩散系数同字母，勿混 |
| 互扩散 | interdiffusion | 两种元素占同一位置、必须互换地扩散（Mg–Fe） |
| 空位 | vacancy | 晶格中缺失的离子位置，为微量元素提供电荷平衡 |
| 封闭温度 | closure temperature | 低于此温度扩散基本停止，梯度被冻结 |
| 扩散年代学 / 扩散计时 | diffusion chronometry | 由扩散剖面反解时间 |
| 地质测速学 | geospeedometry | 由动力学记录测定地质过程速率的统称 |
| 晶体地层学 | crystal stratigraphy | 把晶体环带当作「地层」逐层解读 |
| 成分环带 | compositional zoning | 晶体内成分随位置的变化 |
| 生长环带 | growth zone | 记录特定 $P$-$T$-$X$ 条件的一圈晶体 |
| 正环带 | normal zoning | 核高 Fo、边低 Fo → 降温 |
| 反环带 | reverse / inverse zoning | 核低 Fo、边高 Fo → 升温 |
| 橄榄石 | olivine | $(\mathrm{Mg,Fe})_2\mathrm{SiO_4}$ |
| 镁橄榄石（镁端元） | forsterite (Fo) | $\mathrm{Mg_2SiO_4}$，$X_{\mathrm{Fo}}=1$ |
| 铁橄榄石（铁端元） | fayalite (Fa) | $\mathrm{Fe_2SiO_4}$，$X_{\mathrm{Fo}}=0$ |
| 固溶体 | solid solution | 端元之间成分连续可变的矿物系列 |
| 斜长石 | plagioclase | 本周用作环带示例的矿物 |
| 钙长石组分 | anorthite content | 斜长石环带的成分指标 |
| 出溶 | exsolution | 固溶体冷却时分离成两相 |
| 液相线 / 固相线 | liquidus / solidus | 二元相图中两相区的上、下界 |
| 橄榄岩 | peridotite | 地幔岩石 |
| 蓝片岩 | blueschist | 高压变质岩 |
| 蓝闪石 | glaucophane | 蓝片岩中的蓝色角闪石 |
| 蛇纹石 | serpentine | 橄榄石低温水化产物 |
| 岩浆补给 | magma recharge | 热熔体注入储库，可触发喷发 |
| 岩浆混合 | magma mixing | 成分不同的岩浆相遇 |
| 岩浆通道系统 | magma plumbing system | 从深部到地表的岩浆储存/输送网络 |
| 电子探针 | electron microprobe | 基于 X 射线光谱的微区成分分析仪 |
| 扫描电子显微镜 | scanning electron microscope (SEM) | 成像观察环带 |
| 氧逸度 | oxygen fugacity ($f\mathrm{O_2}$) | 影响 Mg–Fe 互扩散速率的参数 |
| 硅酸盐风化 | silicate weathering | 缓慢消耗大气 CO₂ 的过程 |
| 稀释系统 | dilute system | 反应物浓度低、相互隔离的体系 |
| 界面 | interface | 相与相的接触面，很多反应只在此发生 |
| 显式有限差分 | explicit finite difference | Practical 模型求解 Fick 第二定律的数值方法 |
| 稳定性条件 | stability condition | 📎 $D\Delta t/\Delta x^2 < 0.5$，显式格式不发散的判据 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `EART26201_Practical5_feedback.md`，**Task** 段（p.1） | "This practical contains two questions about **using radiogenic isotopes to date meteorite formation and track crustal contamination recorded by lavas erupted from an Andean volcano**." | **段落内容与本 practical 完全无关**——这是从 Practical 3（等时线定年 / isochron dating）复制粘贴后忘记修改的残留。本 practical 标题为 "Timescales of magmatic processes"，两题分别是扩散系数/Arrhenius 关系与橄榄石 Mg–Fe 环带计时。 | 应为「本 practical 包含两道关于**用扩散系数与橄榄石成分环带估算岩浆过程时间尺度**的题目」。**阅读时请直接忽略这句话。** |
| `EART26201_Practical5_feedback.md`，Question 1 第一个 bullet（p.2） | "…because they relate to the magnitude of the diffusive flux of an element through a plane (**Lecture 2 \| Part 4**)." | **交叉引用的讲次编号错误。** 扩散通量与 Fick 定律出现在 **Lecture 5 Part 4**（Slide 18–25），Lecture 2 是「地球化学家的元素周期表 / 元素分配」。同一文档后续两处引用都正确写作 "Lecture 5 \| Part 4"、"Lecture 5 \| Part 5"。 | 应为 **Lecture 5 \| Part 4**。 |
| `EART26201_Practical5_feedback.md` 第 d) 小题；及 `EART26201_Practical5_feedback.xlsx.md` 第 27 行 | "**Demouchy and Maxwell (2006)** performed high-$T$ experiments to determine the diffusivity of H in olivine." / "d) H diffusion (**Demouchy and Maxwell, 2006**)" | **作者姓名拼写错误。** 该文献的第二作者是 **Stephen Mackwell**（Demouchy & Mackwell 2006, *Physics and Chemistry of Minerals*，关于含铁橄榄石中氢的扩散），不是 "Maxwell"。**两个文件里都错**，说明是从同一处复制。 | 应为 **Demouchy and Mackwell (2006)**。查文献时用错的拼写会搜不到。 |
| `EART26201_Practical5_feedback.md` 第 d)、f) 小题；`…xlsx.md` 第 29、42 行 | "an $E_a$ value **258 kJ**" / "an $E_a$ value **352 kJ**" / 表头 "**Ea (kJ) =**" | **单位不完整。** 活化能是**摩尔量**，且同一段落里 $R$ 已写作 $8.314\times10^{-3}$ **kJ/mol/K** —— 若 $E_a$ 真是 kJ（每分子/每反应），$E_a/RT$ 就不是无量纲数。 | 应为 **kJ/mol**（即 258 kJ mol⁻¹、352 kJ mol⁻¹）。计算结果与 kJ/mol 的解释一致（我已复算验证），所以只是标注遗漏。 |
| `EART26201_Practical5_feedback.md` 第 f) 小题（p.3） | "…and the equation given in **b)**, determine values of $D_\mathrm{Cr}$…" | **交叉引用指向错误的小题。** b) 小题只问「需要什么类型的趋势线方程（答：指数）」，并没有给出方程。Arrhenius 方程 $D_i = D_0e^{-E_a/RT}$ 是在 a) 之前的引言 bullet 中给出的。 | 应为「上文给出的方程」或「d) 中使用的方程」。 |
| `EART26201_Practical5_feedback.md` 第 2 题 f) 的参考答案（p.8） | "Eventually the profiles will become flat, **but the simple excel model we're using here.**" | **句子不完整**，"but" 之后的内容缺失，无法判断作者原意（很可能是想说「但本 Excel 简单模型在时间步过大时会失稳/不再可靠」）。 | 阅读时按残缺句处理；若需要完整含义，应参照 §5.3 中的稳定性条件说明（$D\Delta t/\Delta x^2 < 0.5$）。 |
| `EART26201 - 27-Oct-transcript.md`，Arrhenius/Boltzmann 段（约 439–447 行） | "Ni is given by that relationship here, where you've got **A exponential epsilon i divided by KT**." | **指数上的负号缺失。** Boltzmann 分布必须写作 $N_i = A\exp(-\varepsilon_i/k_BT)$；没有负号则「能量越高分子越多」，与紧接着那句 $N_{E_a}/N = \exp(-E_a/k_BT)$（老师自己念出了 "exponential **minus** Ea over KT"）以及整节的物理含义矛盾。**这是自动语音转写漏字，不是老师讲错。** | 应为 $N_i = A\exp(\mathbf{-}\varepsilon_i/k_BT)$。 |
| `EART26201 - 27-Oct-transcript.md`，橄榄石扩散段（约 997–999 行） | "…you will have more of a smooth decrease from a magnesium-rich core to a **magnesium core**." | **语句残缺**，与上下文（Mg 由核向边扩散、边部贫 Mg）矛盾。 | 应为 "…to a magnesium-**poor rim**"（贫镁的边部）。同为转写脱字。 |
| `EART26201 - 27-Oct-transcript.md`，全篇 | 多处专业名词被语音识别错拼：**"perinotite"**、**"bluishists"**、**"glycophane"**、**"olefin"**、**"4-steroid" / "four sterite"**、**"phthalite" / "firelight"**、**"Iranian relationship"**、**"rate lows"**、**"second law of thick"**、**"diffusion chromatometry"**、**"mathematical processes"**、**"magnetic systems"** | **自动转写的同音误识**，不是内容错误，但会严重妨碍检索与理解。 | 依次应为：**peridotite（橄榄岩）**、**blueschists（蓝片岩）**、**glaucophane（蓝闪石）**、**olivine（橄榄石）**、**forsterite（镁橄榄石）**、**fayalite（铁橄榄石）**、**Arrhenian relationship（Arrhenius 关系）**、**rate laws（速率定律）**、**second law of Fick（Fick 第二定律）**、**diffusion chronometry（扩散计时）**、**magmatic processes（岩浆过程）**、**magmatic systems（岩浆系统）**。 |
| `EART26201 - 27-Oct-transcript.md`，Fo–Fa 相图口述段（约 955–959 行） | "…your olivine crystal will crystallize, say, at **just under 1500 degrees C**, down deep in a magma chamber." | **数值与所用相图不自洽（存疑，非确定错误）。** 在纯 Fo–Fa 二元系中，Fo80–90 的液相线在 1 atm 下约 1700–1800 °C（纯 forsterite 熔点 ≈ 1890 °C，纯 fayalite ≈ 1205 °C）；而玄武岩中橄榄石的实际结晶温度约 1100–1250 °C（Practical 的扩散模型即取 **1100 °C**）。1500 °C 两头都不贴。 | 应理解为**课堂口头示意的随口数字**，不要当作可引用的数值。Practical 已明确警告该相图对玄武岩「绝对温度不正确，只能定性使用」。 |
| 课程大纲 `(EART26201) Principles of Geochemistry.md`，Syllabus 的 Lectures 列表 | "Week 5: Melting and crystallisation in geochemical systems: phase diagram applications" / "Week 6: The pace of geochemical processes: kinetics and diffusion" | **大纲周次与文件夹周次错位。** 本文件夹 Week 5 的幻灯片自称 "Lecture 5"，标题为 "The pace of geochemical processes: kinetics and diffusion" —— 即大纲所列的 **Week 6** 内容。大纲的编号包含了 Week 7 阅读周并从 Week 2 起算。 | **这是已知的系统性编号错位，非内容错误。** 本笔记库统一采用**文件夹编号**，本周记为 **Week 05**。查阅大纲时请自行 −1 换算。 |

**其他核对结果（无误）：**
- Question 1 中 $D_0 = 10^{-1.4} = 3.981\times10^{-2}$、$10^{-5.31} = 4.898\times10^{-6}$ 与表内数值一致；
- H（950 °C → $3.817\times10^{-13}$；1300 °C → $1.079\times10^{-10}$ m²/s）与 Cr（950 °C → $4.542\times10^{-21}$ m²/s）的 Arrhenius 计算结果，经独立复算全部正确；
- 稳定性条件 $D\Delta t/\Delta x^2 = 4.5297\times10^{-4}\times7200/25 = 0.1305 < 0.5$ 与表内数值精确吻合；
- 三个橄榄石种群的均值 206 h / 18.67 h（正文写 ~19 h）/ 40 h 与 12 个单颗时间值一致；正环带 8 颗、反环带 4 颗与核部成分分组自洽；
- (c) 小题「1350 K 时 $D_{\mathrm{Mg-Fe}} \approx 10^{-17}$ m²/s」与 Chakraborty (1997) 数据表内插一致；
- $R = 8.314\times10^{-3}$ kJ mol⁻¹ K⁻¹、$T(\mathrm{K}) = T(°\mathrm{C})+273.15$ 均正确。
