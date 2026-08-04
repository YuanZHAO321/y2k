# EART22201 Igneous Minerals and Processes — Week 01 学习笔记

## 一、本周主题

**本周主题：对称性与七大晶系（Symmetry and the Seven Crystal Systems）。**

这是从讲义 `W1 notes.md` 的标题、五个编号小节，以及 `Practical 1 solutions.md` 的学习目标共同判定的，讲义自己把这一讲称作 **Lesson 1**。具体覆盖五个板块：

1. **1.1 晶体格子（crystal lattice）／1.2 晶胞（unit cell）**——矿物的定义、格点与基元、二维晶胞的五种类型、每个晶胞里有多少格点。
2. **2.1 三维格参数 ／2.2 七大晶系 ／2.3 三维晶胞的五种类型 ／2.4 布拉维格子（Bravais lattices）**。
3. **3.1 对称操作：反映、旋转、倒反 ／3.2 七大晶系的最小对称要求 ／3.3 对称操作的组合（32 点群、230 空间群）／3.4 晶形（form）与习性（habit）**。
4. **4.1 米勒指数（Miller indices）／4.2 矿物中的解理与双晶**。
5. **5.1 例题：角闪石中的双晶**——把格参数换算成"薄片里应该长什么样"。

配套的 **Practical 1** 则在此基础上加了一件全新的实操技能：**第一次上偏光显微镜（polarizing microscope）**，在单偏光（PPL）和正交偏光（XPL）下观察四个薄片里的解理与双晶。

### 它在全课骨架中的位置

本课（EART22201）是大二**两根"岩石材料学支柱"之一**（另一根是 EART27201 沉积岩与化石）。全课骨架是一条清晰的链条：

> **硅酸盐矿物的晶体化学 + 偏光显微镜光性** → **相图与地球化学数据** → **解释岩浆的生成、分异与构造背景**

Week 01 站在这条链条**最上游的第一个环节**，而且是"上游的上游"：它连矿物化学都还没讲，讲的是**任何一个晶体结构都必须服从的几何规则**。老师在课上把这个逻辑说得很直白（见第四段）：

> 对称 → 决定矿物的物理性质（解理方向、双晶方向、光性）→ 物理性质让我们在手标本和薄片里认出矿物 → 矿物组合告诉我们这块岩石是怎么形成的。

因此本周内容看起来最"抽象、最不像地质学"，但它是后面所有薄片鉴定的**几何底座**：Week 02 要讲的光性（多色性、消光角、干涉色）之所以存在，正是因为晶体在不同方向上不等价——而"不同方向上不等价"就是本周的晶系与对称在讲的事。

**这门课整体要解决什么问题**（课程简介原文与老师的口头版本）：

- 官方表述：*"The course investigates the variety of igneous rock types observed on Earth, and the processes that form them. It covers magma generation in the Earth, differentiation processes, and the links between magma compositions and tectonic setting… This unit provides the foundations for interpreting igneous rocks encountered elsewhere in the degree programme."*
- 老师的口头版本（transcript）：10 讲，**先理论、后应用**。开头是 symmetry → optics → mineralogy → rock-forming minerals，这些是"groundwork"；打好基础后进入**熔融与结晶（melting and crystallization）**这两个关键火成过程；最后把全部知识用到**不同板块构造背景下的岩浆作用与火山作用**——建设性板块边缘、板内、俯冲带，以及岩浆**侵入 vs 喷出**的差别。

📎 **背景补充：与其他课的接口**
- **上游**：EART26201 地球化学原理提供热力学与二元相图工具（该课 W03 讲相图原理、W04 讲 An–Di 共结、Ab–Or 溶线出溶、Di–En 辉石、Fo–Qz 包晶）。本课后半段直接消费这套工具——课程大纲里 "solid solution, phase transitions and exsolution will be explored using graphical methods including binary phase diagrams" 说的就是这个。
- **下游**：EART26001 能源与资源（层状侵入体中的铂族元素富集、金伯利岩与金刚石、造山型金矿热液体系）；EART25102 高级野外技术（苏格兰野外课，官方共修课，老师本人是领队之一）。
- **横向**：本周建立的偏光显微镜技能会在 EART27201（沉积岩薄片）和 EART23202 继续使用。
- 顺带一提，Practical 1 的 R1 薄片来自 **Rum 层状侵入体（Inner Hebrides, Scotland）**，这正是 EART26001 讲铬铁矿层与铂族元素富集时的经典对象；13415 来自 **Belhelvie igneous complex, Aberdeenshire**。这两个地点都在苏格兰，与野外课的区域背景相呼应。

---

## 二、核心概念

### 2.1 矿物的定义（Mineral）

> **Mineral:** A naturally occurring, inorganic solid, with a characteristic chemical composition and a regular internal atomic arrangement which results in a tendency to develop external crystal faces.

拆成五个必要条件：**天然产出**、**无机**、**固体**、**有特征化学成分**、**有规则的内部原子排列**。最后一条是本周的主角——正因为内部原子排列规则，晶体才**倾向于**发育外部晶面。注意讲义用的是 "a tendency to"（倾向），不是"一定会"：能不能长出晶面还取决于生长条件（见 2.11 自形程度）。

📎 **背景补充**："有特征化学成分"不等于"化学成分固定"。绝大多数造岩硅酸盐是**固溶体（solid solution）**，成分在两个（或多个）**端元（end-member）**之间连续变化，例如橄榄石在镁橄榄石 Fo（Mg₂SiO₄）与铁橄榄石 Fa（Fe₂SiO₄）之间。这种成分替换叫**类质同象／同晶置换（isomorphous substitution）**：只要替换离子的**半径相近、电价可配平**，就能进入同一个晶格位置而不改变结构。本周材料还没展开，但它是本课后半程（相图、分异）的核心，本周的"晶格 + 基元 = 结构"框架正是理解它的前提——固溶体保持同一个**格子（lattice）**，改变的是**基元（motif）**里坐在某个位置上的原子种类。

### 2.2 晶体格子、格点、基元、结构

- **晶体格子（crystal lattice）**：晶体内部原子的三维排列方式。更严格地说，格子是**空间中一组假想点的阵列，每一个点都具有完全相同的物理和化学环境**。
- **格点（lattice point）**：在空间中重复的那个原子、原子团或图案单元。
- **基元（motif）**：重复的那一组原子。
- 讲义给出的核心等式：

> **Lattice（格子） + Motif（基元） = Structure（结构）**

这个等式值得反复品味：**格子是"重复的规则"（纯几何），基元是"被重复的东西"（化学内容），两者相乘才是真实的晶体结构。** 同一个格子配不同的基元，就得到不同的矿物；同一个基元里换掉一个阳离子（类质同象），格子几乎不变，得到的是同一矿物的不同端元。

### 2.3 晶胞（Unit Cell）

> **Unit cell:** The smallest group of atoms whose geometric arrangement defines the characteristic symmetry of the crystal, and whose repetition in space produces a crystal lattice.

老师课上的口头版本更好记：**"晶胞是格子里最小的可重复对称单元（the smallest possible unit of repeatable symmetry within a lattice）"**。

关键点：**同一个格子可以画出无数个合法的晶胞**（讲义那张 a、b、γ 与 a′、b′、γ′ 并列的图就是在说这件事），但我们**约定选取能体现该格子特征对称性的、体积最小的那个**。Practical Part 1 第一题就是练这个：给你一张二维格子点阵，你要画出"合适的"晶胞。

### 2.4 Z 值：每个晶胞里的公式单位数

讲义在讲二维晶胞时插入了 **Z** 的定义：

> **Z is the total number of formula units contained within the unit cell.**

配图给的是一个基元含 1 个 A、2 个 B 的例子，**Formula = AB₂**；原始（P）格子 **Z = 1**，中心矩形（centred rectangular）格子 **Z = 2**。

📎 **背景补充**：注意区分两个容易混的量——**格点数**（每个晶胞里有几个格点）和 **Z**（每个晶胞里有几个"化学式单位"）。当每个格点上坐一个完整的化学式单位时，两者数值相同；但如果基元本身含有多个化学式单位，Z 会是格点数的整数倍。考试里若问"Z 是多少"，先数格点、再看基元里含几个化学式单位。

### 2.5 数格点的两种方法（二维）

讲义明确给了两条路，两条都对，用哪条看哪条方便：

- **方法一（分数法）**：把晶胞画成格点落在四个角上，然后把每个格点**落在晶胞内部的那一部分（分数）**加起来。角上的点被四个晶胞共享，各算 ¼。
- **方法二（平移法）**：把晶胞整体平移，使格点完全落在晶胞内部，然后直接数**完全被包含**的格点个数。

两种方法在讲义的例子里都给出 **Z = 1**。这是一个很好的自检工具：如果两种方法算出来不一样，说明晶胞画错了。

### 2.6 二维晶胞的五种类型

讲义给的五种（含格参数条件）：

| 二维晶胞 | 边长条件 | 角度条件 |
|---|---|---|
| 斜方形（oblique） | a ≠ b | γ ≠ 90° |
| 矩形（rectangular） | a ≠ b | γ = 90° |
| 中心矩形（centred rectangular） | a ≠ b | γ = 90°，且 \|cos γ\| = b/2a（见第三段） |
| 正方形（square） | a = b | γ = 90° |
| 讲义写作 "rhombohedral" | a = b | γ = 120° |

⚠️ 最后一行的命名有问题，见文末勘误表第 2 条：二维五种布拉维格子中，a = b、γ = 120° 的那一种标准名称是**六方（hexagonal）**，"rhombohedral（菱面体）"是三维术语。

### 2.7 三维格参数与命名约定

要完整描述一个三维格子，需要六个量：

- **三条棱长**：*a*、*b*、*c*
- **三个夹角**：α、β、γ

**命名约定（老师说"这个可能不好记，写到你的 practical reference handbook 里去"）**：

- *a* ∥ **x** 轴，*b* ∥ **y** 轴，*c* ∥ **z** 轴；
- **α = y^z**（y 与 z 轴之间的夹角）
- **β = x^z**（x 与 z 轴之间的夹角）
- **γ = x^y**（x 与 y 轴之间的夹角）

记忆窍门：**每个角"对着"同名的棱**——α 对 a（a 沿 x，而 α 是另外两轴 y、z 的夹角），β 对 b，γ 对 c。

老师特别强调：我们习惯了**笛卡尔坐标系（Cartesian system）**——"想想长方体、麦片盒、书本"——三轴互相垂直；但**晶体格子的轴不一定互相垂直**，这是后面米勒指数最容易出错的根源。

### 2.8 七大晶系（Seven Crystal Systems）

老师的关键论断：**三条棱长与三个夹角的组合方式，在三维空间里恰好只有七种**，这就是七大晶系；**每一种矿物都属于且仅属于其中一个晶系**，而晶系决定了它的对称性质和光学性质。

把讲义 2.2、2.4、3.2 三张表合并（并按后两张表订正三方晶系的角度，见勘误表第 1 条）：

| 晶系 | 棱长 | 夹角 | 必需对称（essential symmetry） | 可能的晶胞类型 |
|---|---|---|---|---|
| 立方 Cubic | a = b = c | α = β = γ = 90° | **4 个三次轴（4 triads）** | P, I, F |
| 三方 Trigonal（菱面体 rhombohedral） | a = b = c | α = β = γ ≠ 90° | 1 个三次轴 | R |
| 四方 Tetragonal | a = b ≠ c | α = β = γ = 90° | 1 个四次轴（tetrad） | P, I |
| 六方 Hexagonal | a = b ≠ c | α = β = 90°, γ = 120° | 1 个六次轴（hexad） | P |
| 斜方 Orthorhombic | a ≠ b ≠ c | α = β = γ = 90° | 3 个互相垂直的二次轴（diads） | P, C, I, F |
| 单斜 Monoclinic | a ≠ b ≠ c | α = γ = 90°, β > 90° | 1 个二次轴 | P, C |
| 三斜 Triclinic | a ≠ b ≠ c | α ≠ β ≠ γ ≠ 90° | 无 | P |

表的两端由讲义明确标注：**立方 = 对称性最高（most symmetry），三斜 = 对称性最低（least symmetry）**。

几个要点：

- **单斜的 β > 90° 是"选取约定"而非物理必需**：真正的条件是 α = γ = 90°、β ≠ 90°；晶体学家习惯把晶胞选成 β 为钝角。
- **"必需对称"是判定晶系的唯一硬标准**。Practical Part 2 就是用这个：拿到一个三维晶体模型，先数出所有对称要素，再对照这张表反查晶系——**不是**靠"看起来像立方体"来猜。
- 讲义把立方系写成 "4 triads" 而不是"3 个四次轴"，是有深意的：**立方系真正不可缺的是沿四条体对角线的四个三次轴**（老师课上让大家用手指捏住立方体的一对相对顶角转一转，见第四段）。

### 2.9 三维晶胞的五种类型与格点数

| 符号 | 名称 | 格点位置 | 格点数计算 | 每晶胞格点数 |
|---|---|---|---|---|
| **P** | 原始（Primitive） | 仅在角上 | 8 × ⅛ | **1** |
| **R** | 菱面体（Rhombohedral） | 仅在角上 | 8 × ⅛ | **1** |
| **I** | 体心（Body-centred） | 角 + 体对角线交点 | 8 × ⅛ + 1 | **2** |
| **F** | 面心（Face-centred） | 角 + 每一个面的中心 | 8 × ⅛ + 6 × ½ | **4** |
| **C** | 底心（C face-centred） | 角 + 一对相对面的中心 | 8 × ⅛ + 2 × ½ | **2** |

计数规则（讲义原文）：

> **Lattice points on corners = ⅛；Lattice points on faces = ½；Lattice points fully enclosed = 1**

讲义把 C 底心留作练习（"See if you can work out the number of lattice points in a C face-centred unit cell"），答案是 **2**：8 个角各 ⅛ 得 1，加上一对相对面的两个面心各 ½ 得 1。

⚠️ 讲义"五种三维晶胞"那一页在 PDF 提取中把 **C 底心的小标题丢了**，只剩下描述句 "Lattice points at corners, and at the centre of one pair of opposite faces" 孤零零挂在 R 和 I 之间——读的时候不要以为那是 R 的补充说明。见勘误表第 3 条。

### 2.10 14 种布拉维格子（Bravais Lattices）

> **The seven crystal systems and five lattice types can be combined in 14 different ways. These are called Bravais lattices.**

把上面那张七晶系表最右列的"可能晶胞类型"数一遍：立方 3（P/I/F）+ 三方 1（R）+ 四方 2（P/I）+ 六方 1（P）+ 斜方 4（P/C/I/F）+ 单斜 2（P/C）+ 三斜 1（P）= **14**。

📎 **背景补充：为什么不是 7 × 5 = 35？** 因为很多组合要么**与已有的格子等价**（可以重新选一个更小的晶胞把它化归为已列出的类型），要么**破坏了该晶系的必需对称**。例如四方面心格子 tF 其实可以重新选出一个更小的四方体心晶胞 tI，所以不单独列；而立方底心格子会破坏四条三次轴，根本不属于立方系。这就是为什么 14 这个数字是"数出来"的而不是"乘出来"的。

### 2.11 对称操作（Symmetry Operators）

讲义列三大类**宏观对称操作（macroscopic symmetry）**：

**（1）反映（Reflection）**——通过一个**镜面（mirror plane）**。讲义给的例子：**一个立方体有 9 个镜面**（3 个平行于面对、6 个通过对棱的对角面）。

**（2）旋转（Rotation）**

| 旋转阶次 | 名称 | 旋转角 |
|---|---|---|
| 1 | 恒等（identity） | 360° |
| 2 | 二次轴（diad） | 180° |
| 3 | 三次轴（triad） | 120° |
| 4 | 四次轴（tetrad） | 90° |
| 6 | 六次轴（hexad） | 60° |

立方体中三种都有：**二次轴（通过对棱中点）、三次轴（通过体对角线）、四次轴（通过面心）**。

📎 **背景补充：为什么没有 5 次轴？** 因为晶体格子必须**平移周期性地填满空间而不留空隙**。正五边形无法密铺平面（内角 108°，不能整除 360°），所以 5 次、7 次及更高次的旋转轴与平移对称不相容。晶体中只可能有 1、2、3、4、6 五种旋转阶次——这条定律叫**晶体学限制定理（crystallographic restriction theorem）**。（准晶 quasicrystal 是 1984 年后发现的例外，但它们没有严格的平移周期性，因此按经典定义不算晶体。）

**（3）倒反（Inversion）**——**对称中心（centre of symmetry）**，也叫**倒反中心（centre of inversion）**：过某一点作直线，两端等距处必有等同的原子。

**（4）旋转倒反（Rotoinversion）**——把旋转与对称中心组合起来产生的新一类对称。讲义的例子：某物体具有 **4 次旋转倒反（4-fold rotoinversion）**——顶点和面之间的关系是"绕轴转 90°，再通过对称中心倒反"。

### 2.12 从 14 布拉维格子到 32 点群、230 空间群

讲义用两张流程图交代了整个晶体学分类体系的构建逻辑：

```
                    ┌─ 加 lattice type ────────→ 14 Bravais lattices
7 crystal systems ──┤
                    └─ 加 macroscopic symmetry ─→ 32 point groups
                        (reflection, rotation, inversion)

14 Bravais lattices ─┐
                     ├─ 加 microscopic symmetry ─→ 230 space groups
32 point groups ─────┘   (reflection + translation,
                          rotation + translation)
```

- **7 大晶系 + 5 种晶胞类型 → 14 布拉维格子**（纯平移几何）
- **7 大晶系 + 宏观对称（反映、旋转、倒反）→ 32 点群（point groups）**。点群描述的是**外形层次**的对称：所有操作都保持至少一个点不动。
- **14 布拉维格子 + 32 点群 + 微观对称（反映+平移、旋转+平移）→ 230 空间群（space groups）**。

📎 **背景补充**："反映 + 平移"叫**滑移面（glide plane）**，"旋转 + 平移"叫**螺旋轴（screw axis）**。它们只在原子尺度上存在（每次操作都伴随一个小于晶胞的平移），从外形上完全看不出来，所以叫"微观对称"。230 这个数字是 19 世纪末由 Fedorov、Schoenflies 和 Barlow 各自独立数出来的，是矿物学与固体物理共用的分类底座。老师并没有要求记住 230 个空间群，讲义的学习目标只写了"Explain the concept of a point group"。

### 2.13 晶形（Form）与习性（Habit）

**核心原则（讲义标题原文）：**

> **External form matches the underlying crystal symmetry.**（外部晶形必须与内部对称一致。）

讲义给的例子很有说服力：**两个看起来形状不同的晶形，可以拥有完全相同的对称要素**——都是"1 个四次轴 + 4 个二次轴 + 5 个镜面"；而另一个晶形只有"1 个四次轴 + 1 个镜面"，属于不同的对称类。所以**"形状"和"对称"不是一回事**。

讲义列的实例：
- **立方系**：石榴子石（garnet）、尖晶石（spinel）、石盐（halite）
- **斜方系**：重晶石（barite）
- **三斜系**：钠长石（albite）
- **单斜系**：正长石（orthoclase）

**晶体习性（crystal habit）**：

> Crystal habit describes the geometric appearance of the crystal, i.e. **the ratio of height, width and length**. The habit depends on **the crystallographic form** and on **the growth conditions**.

关键在最后半句：习性有**两个**控制因素——**晶体学形态（内因）** 和 **生长条件（外因）**。所以**同一种矿物可以有不同的习性**。讲义给的经典对照：

| | 辉长岩（gabbro）中的斜长石 | 玄武岩（basalt）中的斜长石 |
|---|---|---|
| 习性 | 大的**板状（tabular）**晶体 | 大的板状**斑晶（phenocryst）** + 基质中细小的**针状（acicular）**晶体 |
| 成因 | 深部缓慢冷却，晶体有时间长胖 | 斑晶在深部慢慢长大，基质在喷出后快速冷却→只能长成细针 |

Practical Part 2 的导言也重申了这条：*"the habit must conform to the underlying symmetry of the crystal. Recognising the habit can often help in identifying a mineral."*

📎 **背景补充：Reference Guide 中的习性词汇**（全课通用，可对照记忆）：equant（等轴，各方向差不多长）、tabular（板状）、prismatic（柱状）、acicular（针状）、fibrous（纤维状）、platy / micaceous（片状／云母状）。老师在课上口头解释：equant 是"所有面差不多大小、差不多形状、都发育得好"；fibrous 是"某一个方向特别拉长"；scaly / micaceous 是"扁平的、像一张纸的形状"。

### 2.14 自形程度（Quality of crystal form）

| 术语 | 含义 | 讲义／Reference Guide 的例子 |
|---|---|---|
| **自形 euhedral** | 晶面完美或接近完美 | 玄武岩中**等轴自形的橄榄石**；典型的早期结晶矿物 |
| **半自形 subhedral** | 部分晶面发育中等 | 13415 中形状不规则的斜长石 |
| **他形 anhedral** | 完全没有晶面，形状不规则或浑圆 | 辉长岩中**浑圆他形的橄榄石**；R1 中的橄榄石 |

老师课上补了一条很重要的推理提示：**自形晶体可以反推内部对称**（因为它是一个发育良好的三维几何体的切面）；**他形晶体不能**（不规则形状不携带对称信息）。这一条直接决定 Practical Part 2 能不能做——你必须挑发育好的模型来数对称。

📎 **背景补充：为什么自形 = 早结晶？** 见 Reference Guide："Early-formed crystals are generally euhedral. Later-forming minerals must grow around any pre-existing crystals so tend to have less well-formed crystal shapes."——先结晶的矿物周围全是熔体，可以自由长成理想形状；后结晶的必须挤在已有晶体的缝隙里。这条是薄片里判断**结晶顺序（order of crystallization）**的主要证据之一。Reference Guide 还特别警告：*"In most igneous systems, multiple minerals crystallize together simultaneously, so Bowen's Reaction Series is not usually good evidence for the order of crystallization."*——**不要用鲍文反应序列去推结晶顺序，要用结构证据。**

### 2.15 米勒指数（Miller Indices）

讲义定义原文：

> **Miller index:** *(hkl)* where *h*, *k* and *l* are obtained by taking **the reciprocal of the axis intercept**. The first lattice plane away from the origin intercepts the x, y, and z axes at distances of ***a/h***, ***b/k*** and ***c/l***.

用大白话拆解操作步骤（老师课上的版本）：

1. 定一个**原点（origin）**和一套**晶轴**；
2. 沿 **x** 方向走，问：**要走几个晶胞重复距离**才碰到离原点最近的那个平面？记为 *n*ₓ；**h = 1/n*ₓ***；
3. 沿 **y**、**z** 方向同理得 *k*、*l*；
4. 如果某个方向**永远碰不到**该平面（平面与该轴平行），则截距 = ∞，**倒数 = 0**。

讲义给的两个二维实例：
- 例 1：x 走 1 个晶胞、y 走 1 个晶胞，z 轴平行 → *h* = 1/1 = 1，*k* = 1/1 = 1，*l* = 1/∞ = 0 → **(110)**。
- 例 2：`a/2` 处截 x，`b/1` 处截 y，z 平行 → *h* = 1/½ = **2**，*k* = 1/1 = **1**，*l* = **0** → **(210)**。讲义原图标注：*"a/½ = 2; h = 2；b/1 = 1; k = 1；c/∞ = 0; l = 0"*。

**负指数与上划线（bar）**：当平面在某轴的**负方向**截取时，指数写成上划线，如 **(1̄10)**、**(2̄20)**、**(101̄)**。老师用一整段讲了为什么会冒出负号（见第四段"米勒指数的三个陷阱"）。

**圆括号 vs 花括号**：

- **(hkl)**：**单个**平面（准确说是一族互相平行、间距相同的平面中的代表）。
- **{hkl}**：**一整组**具有相同对称性质的平面。讲义写道 *"Sets of (hkl) planes are simplified to the lowest common factor: (2̄20) ⇒ (1̄10)"*，并给出 **{100} 集合**包含 (100)、(200) 等，**{010} 集合**包含 (010)、(030) 等。

**最小整数化**：描述**一组**平面时，永远化到最小整数比。老师原话："If I wrote down {200}, that would be the same, but it's much more straightforward to give it in the smallest integer proportions."但**描述单个平面时不能化简**——(200) 和 (100) 是两个不同位置的平面。

📎 **背景补充：晶向（zone axis）用方括号 [uvw]**。本周材料没有涉及，但这是同一套记号体系里的第三种括号，日后见到不要混淆：`(hkl)` 单个面 / `{hkl}` 面族 / `[uvw]` 单个方向 / `<uvw>` 方向族。

📎 **背景补充：标准晶体学中 {hkl} 的严格含义**是"由点群对称操作互相联系起来的所有等价面"（称为**晶形／form**），例如立方系的 {100} 包含 (100)、(010)、(001)、(1̄00)、(01̄0)、(001̄) 共 6 个**互相垂直**的面，而不只是一叠平行面。本课在 Lesson 1 里用 {hkl} 表示"同一取向的整叠平行面"，是简化用法；transcript 里老师说 "you can then get the set by defining the set of mutually perpendicular plane" 其实正是标准含义的影子。**答题时按老师的用法走**，但知道这个区别有助于读教科书（Putnis、Klein & Philpotts）。

### 2.16 矿物中的平面构造：解理与双晶

讲义把这两者并列为**"planar features in minerals"**，因为它们在原子尺度上都是**沿特定 (hkl) 取向的平面**，因此都能用米勒指数描述。

**解理（cleavage）**：沿原子键合最弱的晶面族优先破裂。讲义例子：

| 解理型式 | 米勒指数 | 矿物例子 |
|---|---|---|
| 1 组完全底面解理（1 perfect basal cleavage） | {001} | **黑云母（biotite）、白云母（muscovite）** |
| 3 组互相垂直的解理 | {100}, {010}, {001} | **石盐（halite）、方铅矿（galena）** |

老师课上的形象比喻：黑云母"像一叠纸／一叠薄片"，**结晶学 z 轴垂直于这些片层**，所以解理是 {001}——解理迹线以固定间隔切过 z 轴。石盐则"像一块蛋糕，竖着切一刀、横着切一刀、再从中间平着切一刀"，三刀互相垂直，"有点像魔方"。

📎 **背景补充：解理的晶体化学成因**。云母的结构是 **T–O–T 层状硅酸盐**（四面体片–八面体片–四面体片），层与层之间只靠一层弱结合的 **K⁺** 离子维系；沿这个界面破裂只需断开弱的离子键，而不必断裂强的 Si–O 共价键，所以形成一组极完全的 {001} 解理。类似地，**辉石（单链）**的解理面绕开硅氧链，得到两组约 87°/93° 的 {110} 解理；**角闪石（双链）**的链更宽，解理面绕开双链得到约 56°/124° 的 {110} 解理。**这就是为什么解理角是鉴定矿物的可靠判据——它是结构决定的，不随切面变化（只随切面取向"表观"变化）。** 这条正是 Practical Part 3 反复用到的推理。

**双晶（twinning）**：两个（或多个）取向不同但按特定对称关系相关联的晶体域，共用一个**双晶面（twin plane）**。讲义例子是薄片中的**双晶斜长石**，以及手标本中的黄铁矿（pyrite）、辉石（augite）、黑云母（biotite）。

老师明确点出双晶的**两种型式**（Practical 中反复考）：
- **简单双晶（simple twinning）**：只有一个可见的双晶面（如角闪石）。
- **聚片双晶（lamellar twinning）**：同一颗晶体内有多条平行双晶面（如斜长石）。

📎 **背景补充：为什么双晶要在 XPL 下才看得清？** 双晶两侧的晶格取向不同，因此**光率体（indicatrix）取向不同**，在正交偏光下**消光位不同**——转动载物台时，一组条带变黑而另一组仍亮，交替出现，形成明暗相间的"斑马条纹"。在单偏光下，双晶两侧的化学成分和吸收特性完全相同，所以**看不出来**。这正好解释了 Practical 中 13415 的观察结果："Under PPL, plagioclase is almost feature-less. Under XPL you should observe multiple lamellar twins that go extinct (black) at different points as you rotate the stage."

📎 **背景补充：为什么解理反而在 PPL 下最清楚？** 解理是**物理裂隙**，裂隙中填充的树脂／空气与矿物折射率不同，产生**明显的黑色线状边界（Becke 效应／相对突起）**——这是折射率对比造成的，属于单偏光现象。到了 XPL，干涉色的明暗变化会部分掩盖这些细线。所以 Practical 的答案是 "Cleavage is usually best seen in PPL, but should also be visible in XPL"。

---

## 三、公式与图表

### 3.1 格点计数公式

**二维：**
- 角上格点计 **¼**（被 4 个晶胞共享）
- 边上格点计 **½**
- 内部格点计 **1**

**三维（讲义原文）：**

> Lattice points on **corners** = **⅛**
> Lattice points on **faces** = **½**
> Lattice points **fully enclosed** = **1**

由此得到五种三维晶胞的格点数：

$$
N_{\text{P}} = 8\times\tfrac18 = 1 \qquad
N_{\text{R}} = 8\times\tfrac18 = 1
$$
$$
N_{\text{I}} = 8\times\tfrac18 + 1 = 2 \qquad
N_{\text{F}} = 8\times\tfrac18 + 6\times\tfrac12 = 4 \qquad
N_{\text{C}} = 8\times\tfrac18 + 2\times\tfrac12 = 2
$$

**符号说明**：⅛ 表示立方体角上的格点被相邻的 8 个晶胞共享，因此只有 ⅛ 属于本晶胞；½ 表示面上的格点被 2 个晶胞共享。**单位**：无量纲（个数）。**适用条件**：把格点看作理想的点，且晶胞按标准方式选取（格点落在角上）。

### 3.2 中心矩形晶胞的判据

讲义在二维晶胞表里给出（原图文字提取略有破损）：

$$|\cos\gamma| = \frac{b}{2a}$$

**含义与用法**：如果你面对一个二维格子，用一个**斜方（oblique）**原始晶胞（棱长 *a*、*b*，夹角 γ）去描述它，而这三个量恰好满足上式，那么这个格子其实拥有**更高的对称性**——它可以被重新描述成一个**中心矩形（centred rectangular）**格子（含 2 个格点）。**适用条件**：二维格子；这是"该选原始斜方胞还是带心矩形胞"的定量判据。**典型数值**：若 *b* = *a*，则 |cos γ| = 0.5，γ = 120° 或 60°，即退化为六方格子。

📎 **背景补充**：这条式子体现了一个贯穿全周的原则——**优先选择能体现最高对称性的晶胞，即使它不是最小的**。中心矩形胞的面积是原始斜方胞的两倍，但因为它把两条互相垂直的镜面画了出来，所以是"正确"的选择。Practical Part 1 画晶胞时会用到这个判断。

### 3.3 米勒指数公式

$$
h = \frac{1}{n_x},\qquad k = \frac{1}{n_y},\qquad l = \frac{1}{n_z}
$$

其中 *n*ₓ、*n*_y、*n*_z 是**离原点最近的那个平面**在各轴上的截距，**以晶胞重复距离（a、b、c）为单位**。等价地，讲义写成：第一个平面在三轴上的截距分别为 **a/h、b/k、c/l**。

**符号与单位**：*h, k, l* 是整数（可为负，写成上划线），**无量纲**；截距以晶胞棱长为单位，也无量纲。
**适用条件**：只对**格子坐标系**成立，**不是笛卡尔坐标系**（老师课上的最大警告）。
**典型数值**：*l* = 0 表示平面平行于 z 轴；(001) 是底面；(100)、(010)、(001) 是三个"晶胞面"。

### 3.4 图解一：七大晶系表怎么用

这张表（见 2.8）实际上有**三种读法**，对应三种题型：

- **正读（给格参数 → 求晶系）**：题目给 a = b = c、α = β = γ = 90°，直接查表得立方。
- **反读（给晶系 → 求可用晶胞类型）**：题目问"四方系有哪几种布拉维格子"，查最右列得 P、I（**没有** F 和 C）。
- **对称读（给对称要素 → 求晶系）**：Practical Part 2 的做法。数出模型上的所有旋转轴、镜面、对称中心，找**必需对称**那一列里能匹配的行。注意"必需"是**下限**：立方系至少有 4 个三次轴，但通常还有更多对称要素；反过来，只要**缺**了必需对称，就一定不是这个晶系。

### 3.5 图解二：14 布拉维格子图

讲义那一页把 14 个格子按晶系分组排列：

- **立方（Cubic）**：Primitive、Body-centred、Face-centred —— 3 个
- **三方（Trigonal）**：Rhombohedral —— 1 个
- **四方（Tetragonal）**：Primitive、Body-centred —— 2 个
- **六方（Hexagonal）**：Primitive —— 1 个
- **斜方（Orthorhombic）**：Primitive、C face-centred、Body-centred、Face-centred —— 4 个
- **单斜（Monoclinic）**：Primitive、C face-centred —— 2 个
- **三斜（Triclinic）**：Primitive —— 1 个

合计 3+1+2+1+4+2+1 = **14**。**从图上读结论的方式**：看每个小立体图上画了几个球、球在什么位置（只有角？角+体心？角+全部面心？角+一对面心？），再看这个立体的棱长与角度是否相等（拉长了？倾斜了？），前者定晶胞类型、后者定晶系。

### 3.6 图解三：米勒指数在三维中的系列图（讲义 4.1 后半）

讲义用一整串三维小图逐步建立直觉，每一张图上都是一个立方体晶胞加上一组平面。**坐标轴约定**：z 轴竖直向上，y 轴向右，x 轴朝观察者斜下方（注意——**晶体学习惯把 x 轴画向页面下方**，老师专门提到这一点）。逐图读法：

| 图 | 平面截取情况 | 指数 |
|---|---|---|
| 1 | 在 x = 1 处截，永不截 y、z | **(100)** |
| 2 | 在 x = ½ 处截，永不截 y、z | **(200)**；化简后属于 **{100}** 集合 |
| 3 | 在 y = 1 处截，永不截 x、z | **(010)** |
| 4 | 在 y = ⅓ 处截 | **(030)**；属于 **{010}** 集合 |
| 5 | 在 z = 1 处截，永不截 x、y | **(001)** |
| 6 | x = 1 且 z = 1 处截，永不截 y | **(101)** |
| 7 | x = +1 且 z = **−1** 处截 | **(101̄)**；与 (101) **互成 90°**（前提是该晶胞的格角为 90°） |
| 8 | x = 1、z = ½ | **{102}** 集合 |
| 9 | x = 1、y = 1、z = 1（同时截三轴） | **(111)** |
| 10 | 同时截三轴，其中一轴走半格 | **{112}** 集合 |

老师看到第 9、10 张时说："Mind blown on the front row. I'm very happy about this. Don't worry about it."并承诺**绝不会要求学生凭空画出"glorious three dimensions"的立体图**，考试会把问题拆成二维投影。

### 3.7 图解四：角闪石双晶投影例题（讲义 5.1 完整走一遍）

**题目**：角闪石（hornblende）的格参数为 *a* = 10 Å，*b* = 18 Å，*c* = 5 Å，β = 105°；双晶面沿 **{100}**。"Draw a projection looking down the y axis, showing the unit cell dimensions and the orientation of the twin planes."（画一张沿 y 轴俯视的投影，标出晶胞尺寸与双晶面取向。）

**解题步骤（老师在投影仪上手绘的完整流程）：**

**Step 0 — 先判断晶系。** α = γ = 90°、β = 105° ≠ 90°，且 a ≠ b ≠ c → **单斜系**。（老师的口诀：**"If you've got no information in the question, then the lattice angle is 90 degrees."**——题目只给了 β，说明 α 和 γ 都是 90°。）

**Step 1 — 画轴。** 先画一套三维轴 x、y、z。确认哪个角是哪个：**γ = x^y = 90°，α = y^z = 90°，β = z^x = 105°**。所以只有 x 与 z 之间是斜的（105°），x–y 和 y–z 都是直角。

**Step 2 — 画晶胞。** 沿 x 量 *a* = 10 Å，沿 y 量 *b* = 18 Å（**最长**），沿 z 量 *c* = 5 Å（**最短**），连成一个"被压斜的火柴盒"。

**Step 3 — 加 {100} 双晶面。** {100} 意味着：**在 x = 1 个晶胞重复处截 x 轴，永不截 y 轴和 z 轴**。所以这些平面**平行于晶胞的 y–z 面**，沿 x 方向以一个晶胞的间隔重复出现。

**Step 4 — 画沿 y 轴的投影。** 把眼睛放在 y 轴上往下看：
- **y 轴指向纸面外**，看不见；
- 纸面上剩下 **x 与 z 两条轴，夹角 105°**；
- 看到的晶胞是一个**平行四边形**：一边长 *a* = 10 Å，另一边长 *c* = 5 Å，锐角/钝角由 β = 105° 决定；
- 双晶面在这张投影上表现为**平行于 z 轴方向的一组直线**，把平行四边形沿 x 方向切开。

**Step 5 — 翻译成"薄片里该找什么"。** 这是整道题的**意义所在**，老师花了最长时间讲：如果角闪石的晶体习性遵循它的晶胞形状，那么在薄片中我们应该找

> **一个菱形（diamond-shaped）的切面，带一条双晶面；而且这条双晶面应该沿着晶胞的"胖轴"（长的 a 方向）而不是"瘦轴"（短的 c 方向）——所以是"短粗的（short and stubby）"双晶，而不是"细长的（long and thin）"双晶。**

老师总结这套方法的威力："This kind of framework is quite a powerful way of taking some data from a book and saying, *I don't know what this mineral is, but I can predict what it ought to look like.* … Or *I'm looking for this mineral. What should I be looking for?*"——**双向可用**：从格参数预测外观，或从外观反推取向。

### 3.8 📎 关于干涉色级序表（Michel-Lévy chart）

📎 **背景补充**：**本周材料完全没有涉及干涉色与 Michel-Lévy 图**——老师明确说光学性质"we're gonna be looking at those, the optical properties in particular, **next week**"。但 Practical 的 Reference Guide 里已经出现了双折射率数值（如橄榄石 0.035–0.052 → 三级色；普通辉石 0.018–0.033 → 二级色），所以这里先给一个最小说明，以免读 Reference Guide 时卡住：

**Michel-Lévy 干涉色级序表**是一张三坐标图：
- **横轴**：双折射率 δ = n_γ − n_α（无量纲，通常 0 到 0.05+）；
- **纵轴**：薄片厚度 *d*（μm，标准薄片 **30 μm**）；
- **图面**：彩色条带，从左下的灰、白（一级）经黄、橙、红到蓝、绿（二级）、再到更高级序的粉红/绿（三级及以上），高级序颜色逐渐变淡趋近"高级白"；
- **从图上读结论的方法**：知道厚度（30 μm）和观察到的最高干涉色，沿这两个坐标交会，读出从原点出发经过该点的那条**放射状斜线**所对应的 δ 值；或者反过来，已知 δ 和 *d*，预测该矿物在薄片中的最高干涉色。
- 支撑它的公式是**光程差 Γ = d × δ**（Γ 单位 nm），干涉色由 Γ 决定：Γ ≈ 550 nm 处是一级红／二级紫的分界。

Week 02 应会正式讲这张图，届时再详细展开。

---

## 四、课堂补充

本周有一份 6,635 词的完整课堂录音转写，前三分之一是课程组织信息（含大量考试情报），后三分之二是讲义内容的口头讲解与一道完整的板书例题。以下按主题归纳讲义上**没有**的内容。

### 4.1 授课教师与课程组织（讲义完全没有）

- **老师**：Margaret Hartley，**一个人讲完全部 10 讲**，同时是 Earth and Planetary Science 的**项目主任（Programme Director）**。
- **本周课的特殊情况**：老师上周被学校派去**智利圣地亚哥（Santiago, Chile）**出差，所以第一讲实际上在教学第二周才上（transcript 开头："First lecture in week two is a bit unusual"）。**后果是：reading week（阅读周）要补上一讲**。所有讲座都会**录播（podcast and recorded）**，不能到场可以事后补看；但**实习课无法重开**，老师会提供一些线上资源代替。
- **每周的教学流程**（三段式）：
  1. **课前**：Canvas 上放 1–3 段**约 10 分钟的异步视频**，是完整版讲解。老师强烈建议提前看："it'll be very, very advantageous if you watch that in advance"。
  2. **课堂 1 小时**：老师过一遍视频的 **"edited highlights"**，回答问题，并**做例题**（"worked examples that will help prepare you for the various assessments"）。本周的例题就是 3.7 那道角闪石题。
  3. **实习 2 小时**：紧接着到 **G12 / G14** 教室。
- **Canvas 使用方法**：用左侧 **Modules** 按钮找每周材料。每个 module 里有：课前视频、全部幻灯片和 PowerPoint、实习材料、线上资源、（课后放出的）**实习答案**、推荐阅读、本周学习目标小结、以及一个**不计分的小测（quiz）**。
- **讨论板（discussion board）**：可以**匿名提问**，鼓励大家**互相 upvote**；如果某个问题是全班共性的，老师会在讲座上统一回答。
- **答疑**：老师办公室在**本楼一楼（first floor）右侧走廊，茶水间（tea room）对面**；门通常关着挡走廊噪音，但**灯亮就在**，敲门即可。邮件承诺**两个工作日内**回复。

### 4.2 ⭐ 考试与评估情报（本周最重要的实用信息）

这几条讲义上一个字都没有，全部来自 transcript，务必记住：

**（1）Practical Reference Handout —— 可以带进考场的"外挂"**

> "In the practical classes, you are each gonna be given a handout, a practical reference handout. **Collect one in today's practical class and put your name on it, and bring it to every class.** This is gonna be one of your friends, because when we come to the assessment, there's a practical test at the end of semester, and **you can bring your own annotated copy of this handout.** So if there are things that you wanna write down that you wanna have to hand in the practical test, you can be making those notes as you go along throughout the 10 weeks of the course."

**这意味着 practical test 事实上是"半开卷"的，而且开卷的那本书是你自己写的。**这条信息的行动含义非常明确：**从 Week 01 开始，每一次实习课上学到的判据、数值、诀窍，都要立刻写进那本 Reference Guide 的空白处。**老师在讲格角约定（α = y^z、β = x^z、γ = x^y）时就直接说了一句："Write it down in your practical reference handbook so that you have it as a convenient reference when you need that information."

**（2）两项评估**

| 评估 | 权重 | 时间 | 时长 | 说明 |
|---|---|---|---|---|
| **Practical test**（实习考试） | **30%** | 学期最后一周（老师口头说"Monday the 13th of December"，并让大家自查课表；课程大纲写 Week 12） | 2 小时 | 线下、**可带注释版 Reference Handout**；有 support plan 的同学**自动获得加时，不需要申请** |
| **Written exam**（笔试） | **70%** | 一月 | 2 小时 | 老师会**提供往年练习卷**，大约学期过半时放上 Canvas，并会**用一次讲座专门讲考卷的形式、题型和拿分策略** |

（课程大纲补充：practical test 考 ILO 2、3、4、5、9；笔试考 ILO 3、6、7、8。所以**薄片鉴定与素描只在 practical test 里考，相图与地球化学计算只在笔试里考**。）

**（3）紫色标签 = 不考**

> "I also use this little **purple tag** in the corner of slides, where I want to tell you about something that's **extra to the course**. … The key difference here is that anything that's on one of these purple tag slides is **not assessable material**, so I won't be asking exam questions about anything that's on a purple slide."

复习时可以先跳过紫标幻灯片。（本周的 PDF 提取里看不出哪些页带紫标，需要对照原始 PowerPoint。）

**（4）每周 quiz 不计分**，纯自检用；老师建议课后做一遍、期末复习再做一遍（"can be attempted multiple times"）。

**（5）实习答案课后统一放出**（本笔记第五段依据的 `Practical 1 solutions.md` 就是）。

### 4.3 项目主任事项（与本专业学生直接相关）

- **Assessment calendar（评估日历）**：老师每年为 Earth and Planetary Science 的**每一条 pathway** 分别做一张，橙色是核心课的评估与截止日期，白色是该 pathway 的选修课。已放在 Canvas 的 **virtual common room**，另有纸质版张贴在**恐龙门厅（dinosaur foyer）的公告栏**和**一楼门厅**。⚠️ **注意**：非 EART 课号的单元**不在这张表上**，需要自己补进个人日历。（当天老师本以为已发邮件通知，全班摇头表示没收到，老师说会去查。）
- **Student Voice Committee（学生之声委员会）**：仍在招学生代表，老师说 Earth and Planetary Science **一贯代表不足**，鼓励报名。
- **EART25102 苏格兰野外课**：老师本人是领队之一，其他领队是 **Steve Covey-Crump、Russell Garwood**（古生物，本学期末会教你们）和 **Rufus Brunt**（平时教沉积学硕士项目，来协助沉积学部分）。老师明确说：**"This is core for geology and energy and resources pathways"**——对 Energy and Resources 方向是**核心课**。其他 pathway 的学生若喜欢野外也可以选，但要注意**选对配套的共修单元（co-requisite units）**，不确定就去问老师。
- 老师提到刚结束的 **Aliaga 野外实习**：听到不少正面反馈（大家很努力、很好带），也听到一些同学体验不佳并已通过正规渠道反映，老师感谢并表示会处理。

### 4.4 为什么地球科学家要学对称（老师的核心论证）

老师预判了学生的疑问——"这一节可能把你们带回小学：什么是镜面？什么是旋转对称？这跟地球与行星科学家有什么关系？"——然后给出了一条四步因果链：

> **对称是构建造岩矿物的关键 → 造岩矿物底层的原子对称从根本上支配这些矿物的物理性质 → 我们需要知道这些物理性质，才能在手标本或薄片中鉴定矿物 → 我们在一块岩石中观察到的矿物组合，告诉我们形成这块岩石的过程（特别是在火成体系中）。**

并且老师坦诚提醒：

> **"I want to give you a heads up that the first two lectures are probably the most mind-bending of the unit. Don't worry if you don't get it the first time round or the second time round, but it will get easier with repetition. It gets easier after these first two lectures, so please stick with it."**

（即 Lesson 1 对称 + Lesson 2 光学是全课最难的两讲，之后会变轻松。**这是重要的心理预期管理，也说明这两周值得多花时间反复看。**）

### 4.5 立方系"4 个三次轴"的手指实验

讲义只给了结论（cubic 的必需对称是 4 triads），老师给了一个可以自己做的验证方法：

> "If you think about **taking a cube and putting your fingers on all of the corners**, rotating it so that you've got **one set of corners facing your eye**, rotate it around, you'll find that it's got **three-fold rotational symmetry**. And there are **four pairs of opposite corners**. So in a cubic crystal system, the minimum symmetry is to have four triads. And we can do the same kind of thing with each of the other crystal systems. **Try it at home, try it in the practical.**"

要点：立方体有 8 个顶点 = **4 对相对顶点** = 4 条体对角线；沿每条体对角线看下去，立方体呈现三重对称（每转 120° 重合一次）。**Practical Part 2 就是把这套手上功夫用到全部七个晶系。**

### 4.6 米勒指数的三个陷阱（老师逐个演示，讲义完全没写）

这是 transcript 中信息密度最高的一段，老师在实物投影仪上手绘讲解。

**陷阱 1：把米勒指数当成笛卡尔坐标**

> "A common pitfall with this kind of notation is that **we are used to dealing with Cartesian coordinates. These are not Cartesian coordinates.** So a common mistake that people can make is, let's say they want to find the (110) plane. … The common mistake is to go: I'm going to have one point at my origin, and then I'm going to find the point that corresponds to (1,1), thinking about these as just Cartesian axes. Point (1,1) in a Cartesian world would be here. And then they join those points up and they get **that**, which is **not quite what we were asking for.**"

**正确做法**：*"You're always looking at the **interception of these planes with the unit cell**, rather than trying to treat it as a Cartesian system."* ——米勒指数描述的是**平面在各轴上的截距的倒数**，不是"从原点连到某个点的直线"。

**陷阱 2：负指数从哪来——必须盯住"同一个平面"**

老师用一组倾斜的平面演示：沿 +x 走半个晶胞碰到第一个平面（→ h = 2），然后沿 +y 走一个晶胞也碰到"一个"平面（→ k = 1），得到 (210)。但他随即指出这是错的：

> "I've just written down (210) planes, but **this set looks totally different**. So there's something missing here. In this example, when I followed my lattice towards my first plane, **I intersected the same plane when it crossed the unit cell in both directions.** In this case, when I went in positive x direction, I got to **this** plane. But when I went to the positive y direction, I got to **this** plane. So **I've described two different planes here, and that's not what we want.**"

**修正**：必须沿 **−y** 方向走一个晶胞重复距离，才碰到**同一个**平面，因此 *k* = −1，写成上划线 **(21̄0)**。

> **老师的口诀（务必记住）："The trick is *how many unit cell repeats from the origin*, but also to be **looking at the same plane** from the origin."**

**陷阱 3：() 与 {} 分不清**

> "What we've done here with this notation is to describe **this plane, this singular plane**, the (21̄0) plane. But we can see that we've got **a set of planes** here that all have the same orientation. **They're all mutually parallel. They're never going to intersect one another. They all have the same symmetry.** If we're trying to describe a mineral, it would be really annoying to have to describe each one of those planes separately. We want a notation that will describe the set of the planes. And we do that using these curly brackets. So **normal brackets refer to one plane in isolation. Curly brackets refer to all of the planes that have exactly the same symmetry.**"

老师还给了一个验证方法：*"The way that we would know that is that we could **define a different unit cell**, work out our (21̄0) plane, and we'd still come up with something that has the same orientation. So they belong to the same set."*

### 4.7 x 轴画向页面下方的约定

> "In crystallography, **the x axis is conventionally drawn down the page. I don't know why that convention exists, but it does, so I'm going to follow it.**"

老师自己都说不清缘由，但**画图时必须遵守**——这直接影响 Practical Part 1 里"哪条是 a、哪条是 b"的判断，Practical 的提示 *"Remember to look at which crystallographic axes are shown on the diagram!"* 讲的正是这件事。

### 4.8 老师的口误与自纠（听录音时注意）

- 报角闪石格参数时说成 "A equals 10, B equals 18, **C equals 105**, and beta"，随即自纠 "sorry, **C equals five**, and **B**[eta] **equals 105**"。**正确值：a = 10 Å, b = 18 Å, c = 5 Å, β = 105°。**
- 讲立方系必需对称时说 "the minimum symmetry is to have **three, sorry, four** triads"。**正确：4 个三次轴。**
- 讲米勒指数定义时一度记不清，翻回幻灯片："let me just make sure I've got this right… **Sorry, it helps if I actually read the definition.**"（说明这个定义连老师都要照着念，学生记不住是正常的。）

### 4.9 老师对难度的承诺与安抚

- **"I will never ask you to try and sketch something in glorious three dimensions. I'll always try and break down questions for you."** ——考试不会考徒手立体作图，会拆成二维投影。这大幅降低了 3.6 那一串三维图的备考压力：**要求是能"读懂"，不是能"画出"**。
- 讲到复杂解理型式那一页时：**"You do not need to know all of these words on this slide"**——那页只是给你一个"解理可以有多复杂"的感性认识，不用背。
- 反复邀请提问：*"I'm absolutely fine with people coming to say, I didn't understand that, can you go through it again? That is what we're here for, so please do not be afraid to ask questions."*

### 4.10 课堂节奏的现实

最后一句很有意思：**"I think we're going to get chucked out of the room in like two seconds. So what I suggest we do is stop there."** ——角闪石例题讲完刚好下课，讲义 5.1 之后的内容（如果有）没有在课堂上展开。所以**讲义比课堂多的部分（二维晶胞五种类型的细节、Bravais 格子的完整列举、32 点群/230 空间群流程图）需要自己看课前视频补齐**——老师课上明确跳过了："There are various ways that you can configure the unit cell. **I won't go into that now.** … But if you haven't watched the video, do have a look at those."

---

## 五、Practical 要点

### 5.0 实习总览

**Practical 1: Symmetry and the seven crystal systems**，共三部分，**顺序不限**，总计约 2 小时。

**完成后应能（学习目标原文翻译）：**
1. 为二维格子指定一个晶胞；
2. 用米勒指数描述格子中平面构造的取向；
3. 识别三维物体中的对称操作；
4. 从宏观对称推断三维矿物所属的晶系；
5. **使用偏光显微镜在单偏光与正交偏光下观察薄片**；
6. **在显微镜下识别硅酸盐矿物中的解理与双晶**。

注意第 5、6 条是**全新技能**，讲义里没有任何对应内容——这就是本课"lecture 讲晶体学、practical 教显微镜"的分工方式。

### 5.1 Part 1（30 分钟）：晶胞与米勒指数

**任务**：给出一系列**二维格子**，对每个格子：
- 画出一个**合适的晶胞**；
- **测量**图上可见的格参数（纸质版可以直接量，屏幕上则估计）；
- 画出题目指定米勒指数的**平面组**。

**三个小题：**

| 小题 | 要求画的平面 | 说明 |
|---|---|---|
| i) | **{110}** | 最基础：x 走 1 个晶胞、y 走 1 个晶胞 |
| ii) | **{11̄0}** | 练负指数：y 方向要往**负**方向走 1 个晶胞 |
| iii) | **{101}** 和 **{101̄}** | 引入 z 轴；**{101} 用虚线，{101̄} 用实线** |

**⭐ 官方提示（Hint）**：*"Remember to look at **which crystallographic axes are shown on the diagram**!"* ——不同小题画的可能是 x–y 面、也可能是 x–z 面。小题 iii 出现 *l* = 1，说明那张图上画的一定是含 **z 轴**的截面（x–z），此时"y 方向"的指数为 0。**这是本部分最容易丢分的地方：不看清坐标轴就套模板。**

**推理链模板（做每一题都走这四步）：**
1. **看轴** → 确认图上是哪两条晶轴，第三条轴垂直纸面（其指数由是否与该平面平行决定）。
2. **选晶胞** → 找出最小的、能体现该格子对称性的重复单元（必要时用 3.2 的 |cos γ| = b/2a 判据决定用原始胞还是带心胞）；定原点。
3. **反推截距** → 由 *h* = 1/n 反过来求 n：*h* = 1 → 在 1 个晶胞重复处截；*h* = 2 → 在 ½ 处截；*h* = 0 → 与该轴平行，永不相交。带上划线 → 往负方向走。
4. **画整组平行线** → 因为是花括号 {hkl}，要画出整组等间距平行线，而不是孤零零一条。

### 5.2 Part 2（30 分钟）：三维物体中的对称

**导言（值得整段记住）**：

> "When minerals grow under ideal conditions, they develop external crystal faces. The characteristic external shape of a mineral is referred to as the **habit**. The habit describes **both the general shape and the crystallographic form, and also how well developed that form is**. Importantly, **the habit must conform to the underlying symmetry of the crystal.** Recognising the habit can often help in identifying a mineral."

**操作步骤**：
1. 从模型盘里挑 **2–3 个三维晶体模型**带回座位；
2. **i)** 找出所有的**旋转、反映、倒反**对称要素，逐一写下来（答案示例格式：**"3 diads, 3 mirror planes, centre of inversion"**）；
3. **ii)** 考察这些对称要素**彼此之间的关系**（示例：**"the mirror planes are perpendicular to the diads"**）；
4. **iii)** 用你的对称分类，**把模型指派到七大晶系之一**；
5. 用完把模型还回讲台的托盘，然后**浏览其余模型，确认你能为七大晶系各找到至少一个代表物体**。

**判据（对照 2.8 的必需对称列）：**

| 你数出来的 | 晶系 |
|---|---|
| 4 个三次轴（沿体对角线） | **立方** |
| 1 个六次轴 | **六方** |
| 1 个四次轴 | **四方** |
| 1 个三次轴（且无四/六次轴） | **三方** |
| 3 个互相垂直的二次轴（且无三次以上轴） | **斜方** |
| 只有 1 个二次轴 | **单斜** |
| 什么都没有（可能只有对称中心） | **三斜** |

📎 **背景补充：数对称的实操顺序**（材料未给，但很有用）——**先找最高阶的旋转轴**（拿模型转一转，看有没有转 60°/90°/120° 就重合的方向），因为最高阶轴唯一地锁定了大半个答案；**再数二次轴**；**最后找镜面和对称中心**。判断有没有对称中心的快捷方法：**每一个面是否都有一个平行的、大小相同的相对面？**——如果是，就有对称中心。

### 5.3 Part 3（60 分钟）：硅酸盐矿物中的解理与双晶

**三个目标**：
1. 熟悉使用**岩石薄片显微镜（petrological microscope）**观察薄片；
2. 复习常见造岩硅酸盐矿物（大一学过）；
3. 观察硅酸盐矿物中解理与双晶的实例。

**四个薄片，顺序不限。要求：至少对其中两个做细致观察，但下课前四个都要看过一遍。**建议边看边画**带标注的素描（labelled sketches）**。

---

#### 薄片 RFM7 —— 角闪石正长岩（hornblende syenite）

主角：**角闪石（hornblende）**，是薄片中**颜色最深（strongly coloured）**的矿物。

**问题与答案（含推理链）：**

**Q：描述并素描角闪石的特征形状；你应该能找到至少两种代表不同切面角度的特征形状。**
> **A**：应能识别出——
> - **细长切面，带 1 条解理迹线**；
> - **规则的近八边形切面，带 2 条解理迹线**。
>
> 晶体是**自形（euhedral）**的，即接近理想晶体习性。**角闪石的三维习性是柱状（prismatic）或针状（acicular）。**

> **推理链**：柱状晶体是"长条形的棱柱"。**纵切**（沿柱体长轴切）→ 看到细长矩形，两组 {110} 解理中只有平行于长轴的那一组能显现 → **1 条解理迹线**；**横切**（垂直柱体长轴切，即"基面切面 basal section"）→ 看到近八边形（柱面 + 截角），两组解理都在切面内 → **2 条解理迹线，夹角约 60°**。
> **⭐ 关键认识：同一种矿物在薄片中呈现几种"特征形状"，取决于切面方向，不是它有几种习性。**

**Q：找一颗有双晶的角闪石。双晶在 PPL 还是 XPL 下看得更清楚？角闪石是简单双晶还是聚片双晶？**
> **A（材料只答了后半问）**：**角闪石通常是简单双晶（simple twinning）**，但偶尔能找到有两条双晶面的晶体。
>
> ⚠️ 前半问（PPL 还是 XPL）**材料未直接作答**。
> 📎 **背景补充**：应为 **XPL**。理由见 2.16 的补充——双晶两侧化学成分相同，PPL 下没有对比；只有在正交偏光下，两侧因光率体取向不同而**在不同的载物台角度消光**，才显现为明暗相间的域。

**Q：找一颗显示 2 条解理迹线的角闪石。解理在 PPL 还是 XPL 下更清楚？两条解理的夹角是多少？**
> **A**：**解理通常在 PPL 下最清楚（Cleavage is usually best seen in PPL），但在 XPL 下也应该可见。角闪石有两组解理，夹角约 60°。**
>
> 📎 **背景补充**：更精确的标准值是 **56° 和 124°**（互补角）。这个角度是**角闪石最重要的鉴定判据**，用来与辉石（约 87°/93°，实用上"约 90°"）区分。成因见 2.16 的补充：双链硅酸盐的链宽决定了解理面必须绕行的角度。

**Q：双晶面与解理面之间是什么关系？它们互相切割吗？如果是，夹角多少？**
> **A**：
> - **在两组解理的切面（横切面）中，双晶面平分（bisects）解理夹角**；
> - **在一组解理的切面（纵切面）中，双晶面平行于解理。**
>
> 📎 **背景补充**：这与 3.7 那道例题呼应——角闪石的双晶面是 **{100}**，解理是 **{110}**。在基面切面上，{100} 恰好位于两组 {110} 的中间，因此平分解理角；在纵切面上，{100} 与 {110} 都平行于柱体长轴，所以看起来平行。**讲义的例题和实习的观察是同一件事的两个方向。**

**Q：这个薄片里还能认出哪些造岩矿物？**
> **A**：**碱性长石（alkali feldspar）**、**斜长石（plagioclase）**，以及**磷灰石（apatite）**（后面的实习会再讲）。
>
> 📎 **背景补充**：正长岩（syenite）按 QAPF 分类是**碱性长石占优、石英 <20%** 的深成岩，所以这里碱性长石多、石英少是意料之中的（见 Reference Guide 的 QAPF 部分：trachyte 的粗粒等价物就是 syenite，其常见斑晶矿物为 alkali feldspar）。

---

#### 薄片 13415 —— 斜方辉石粗玄岩（orthopyroxene dolerite），Belhelvie igneous complex, Aberdeenshire

主角：**斜长石（plagioclase）**，是本样品中**最丰富**的矿物。

**Q：描述并素描斜长石的特征形状。**
> **A**：有些斜长石呈**规则矩形——自形（euhedral）**；也会看到一些形状**相当不规则的——可描述为半自形（subhedral）**。**在这块岩石中，斜长石的三维习性是板状（tabular）。**

**Q：斜长石中能识别出什么平面构造？在 PPL 还是 XPL 下可见？是解理还是双晶？**
> **A**：**在 PPL 下，斜长石几乎没有任何特征（almost feature-less）。在 XPL 下，你应该能观察到多条聚片双晶（multiple lamellar twins），在转动载物台时它们在不同角度消光（变黑）。**
>
> **⭐ 推理链（这是本次实习最重要的一条判据）：**
> **观察**：PPL 无特征 → **排除解理**（解理是物理裂隙，PPL 下应有明显黑线）。
> **观察**：XPL 下出现平行条带，且**转台时不同条带在不同角度变黑** → **判定为双晶**。因为解理迹线是固定的黑线，不会随转台交替消光；只有取向不同的双晶域才会交替消光。
> **观察**：条带**多条平行** → **聚片双晶（lamellar / polysynthetic twinning）**，不是简单双晶。
> **结论**：**多条平行、只在 XPL 下可见、交替消光的条带 = 斜长石的聚片双晶。这是薄片中鉴定斜长石的头号判据。**

**Q：还能认出哪些造岩矿物？它们有解理或双晶吗？**
> **A**：
> - **两种在 PPL 下略带颜色（slightly coloured）的矿物：单斜辉石（clinopyroxene）和斜方辉石（orthopyroxene）**。答案原文说："Well done if you managed to tell them apart!"（能区分开就很棒了，后面会有更多练习。）
> - **两者都有两组夹角 90° 的解理迹线**，但**取决于切面方向，可能只看得到一组**。
> - 还有一种**不透明氧化物矿物（opaque oxide）**，**很可能是磁铁矿（magnetite）**。

> 📎 **背景补充：怎么区分 cpx 与 opx**（Reference Guide 给了完整方法，可提前写进 handout）：
> - **消光角（extinction angle）是最常用的判据**：opx 属斜方系→**平行消光**；cpx 属单斜系→**斜消光**。用法：**挑一颗只显示单组解理迹线（不是两组）、且干涉色最高的晶体**来量。
> - **颜色与多色性**：cpx 可能呈粉红到褐色，有些有多色性；opx 通常无色、无多色性。**唯一例外是顽火辉石（enstatite, Mg₂Si₂O₆）**，有时呈**弱但很特别的浅粉—浅绿多色性**。
> - **干涉色**：opx 是低的一级干涉色；多数 cpx 更高，典型为二级。
> - **双晶**：**斜方辉石从不出现双晶（never exhibit twinning）**，而单斜辉石可能有。

---

#### 薄片 SW —— 黑云母白云母花岗岩（biotite muscovite granite）

主角：**黑云母（biotite）**，是薄片中颜色最深的矿物。

**Q：描述并素描黑云母的特征形状（习性）。**
> **A**：黑云母晶体**典型地又薄又长（thin and elongate）**；**平面构造沿晶体长边延伸，短边参差不齐（ragged）**。也可能看到**近六边形的切面**（在本样品中很罕见）。**黑云母通常描述为片状习性（platy habit）。**
>
> 📎 **背景补充**：为什么大多数切面是细长条、六边形却罕见？因为片状晶体像一叠纸，**随机切面绝大多数会斜着或垂直切过纸叠**，得到细长的矩形；只有恰好**平行于片层**切，才看到片的完整轮廓（云母的理想外形接近假六方）。这与角闪石的道理相同：**"特征形状"是三维习性与切面方向共同的产物。**

**Q：能识别出什么平面构造？在 PPL 还是 XPL 下最清楚？是双晶还是解理？**
> **A**：**这个平面构造是解理（cleavage），在 PPL 下最清楚。**

**Q：这些平面构造的取向是 {001}。用这个信息在素描上标出结晶学 z 轴的方向。**
> **A**：**{001} 平面切过 z 轴，因此 z 轴的方向必然垂直于解理迹线。**
>
> **推理链**：{001} 意味着 *h* = 0（平行 x 轴）、*k* = 0（平行 y 轴）、*l* = 1（在 1 个晶胞重复处截 z 轴）。一个同时平行于 x 和 y 的平面，就是 x–y 面本身，其法线正是 **z 轴**。所以在素描上，**z 轴画成一条垂直于解理迹线的箭头**。

**Q：在单偏光下，转动薄片直到平面构造沿十字丝呈东西向（E–W）。此时黑云母是什么颜色？转到南北向（N–S）时又有什么变化？**
> **A**：**解理呈 E–W 时，颜色是深棕色（dark brown）；解理呈 N–S 时，颜色是麦秆黄（straw yellow）。这种颜色变化叫多色性（pleochroism），我们会在 Lesson 2 更仔细地讨论这个现象。**
>
> 📎 **背景补充：多色性的物理成因**（材料明确把解释推给了 Lesson 2，这里先给出机制）：
> 1. 单偏光下，下偏光片让光只在**一个固定方向**振动（英国常见的显微镜设定为 **E–W 方向**）。
> 2. 各向异性晶体对光的**吸收（absorption）是随方向变化的**——不同振动方向的光被不同程度地吸收，被吸收掉的波长不同，因此**透过来的颜色不同**。
> 3. 黑云母的深色来自八面体片中的 **Fe²⁺**（以及 Ti），其**晶体场跃迁（crystal field transition）**对**平行于片层方向**振动的光吸收最强。
> 4. 所以：**解理（= 片层）转到 E–W** → 片层平行于偏光振动方向 → **最强吸收 → 深棕色**；**解理转到 N–S** → 偏光振动方向垂直于片层 → **弱吸收 → 麦秆黄**。
> 5. 转动载物台一整圈，颜色在深棕与麦秆黄之间变化两次——**这就是多色性**，只在 PPL 下出现（XPL 下被干涉色掩盖）。**立方晶系矿物（各向同性）永远没有多色性**——这条把光性直接接回了本周的晶系。

**Q：还能认出哪些造岩矿物？**
> **A**：**斜长石、碱性长石、石英（quartz）和白云母（muscovite）——这些在 PPL 下都是无色的。**
>
> 📎 **背景补充**：岩石名 "biotite muscovite granite" 本身就在传递信息。按 Reference Guide 的命名规则：**根名（granite）暗示了必要矿物（essential minerals）——石英 + 斜长石 + 碱性长石**；根名前面的修饰词列的是**特征矿物（type minerals）**，且**丰度最低的写在最前面**。所以 "biotite muscovite granite" = 石英+斜长石+碱性长石（必要）+ 白云母 + 黑云母（特征，且黑云母比白云母多）。

---

#### 薄片 R1 —— 橄榄粗玄岩（olivine dolerite），Rum layered intrusion, Inner Hebrides, Scotland

主角：**橄榄石（olivine）**，是最丰富的矿物。

**Q：描述并素描橄榄石的特征形状（习性）。**
> **A**：本薄片中**大多数橄榄石没有明显的晶面**——它们看起来相当**浑圆（rounded）**，应描述为**他形（anhedral）**。**注意这不是橄榄石的理想晶体习性！**
>
> 📎 **背景补充**：橄榄石的理想习性是**等轴到短柱状的自形晶**（斜方系）。R1 中的浑圆外形是**堆晶（cumulate）过程**的结果——层状侵入体中，先结晶的橄榄石沉降堆积，随后被粒间熔体部分**溶蚀（resorption）**并被后结晶的矿物包裹改造。Reference Guide 的 cumulate 词条正是描述这类岩石："The rock will have a framework of larger, closely packed **cumulus** crystals … The interstitial spaces between the cumulus crystals are filled by **intercumulus** minerals."

**Q：注意橄榄石中有弯曲的裂纹切过晶体。它们在 PPL 还是 XPL 下可见？这是解理，还是别的什么？你怎么知道？**
> **A（这是整份实习答案里推理最完整的一题）**：
> **弯曲裂隙（curving fractures）在橄榄石中很常见。它们在 PPL 下很显著，在 XPL 下也可见。它们不可能是解理，因为解理按定义是平面构造（planar feature）——所以在薄片中，解理应当总是表现为直线（或非常接近直线）的特征。**
> 材料补充：*"Olivine does actually have three cleavage traces at 90° to each other, but they are usually very faint or invisible in thin section."*（⚠️ "三组"存疑，见勘误表第 4 条。）
>
> **⭐ 推理链模板：弯的 = 不是解理。**因为薄片是一个**平面切片**，一个**真正的平面**与切片平面相交，几何上**只能是一条直线**。任何弯曲的线状特征都必然是**不规则破裂（fracture）**，而不是晶体学控制的解理。**这是一条纯几何论证，非常适合写进 Reference Handout。**
>
> 📎 **背景补充**：这些贝壳状／弯曲裂隙叫 **conchoidal fracture（贝壳状断口）**，是橄榄石的经典特征，源于其孤立四面体（**岛状硅酸盐 nesosilicate**）结构——SiO₄ 四面体之间靠 Mg/Fe 八面体连接，各方向键强差别不大，所以**没有明显优势的破裂面**，只能不规则地碎裂。这与云母（层状，一组极完全解理）、辉石/角闪石（链状，两组解理）形成鲜明对比。**结构类型 → 解理型式**这条链条，就是本课"晶体化学 → 光性/物性"骨架的最好例子。

**Q：还能认出哪些造岩矿物？**
> **A**：**围绕橄榄石的单斜辉石（clinopyroxene）和斜长石**；还应注意到一种**不透明氧化物矿物——这是尖晶石（spinel）**。
>
> 📎 **背景补充**：Rum 层状侵入体中的不透明尖晶石族矿物通常是**铬铁矿（chromite, FeCr₂O₄）**——这是一种**尖晶石族（spinel group）**矿物，在薄片中不透明。而狭义的尖晶石端元 **MgAl₂O₄** 在薄片中通常是**透明**的（绿色至褐色）。所以答案里的 "spinel" 应理解为"尖晶石族矿物"。**这也正是 EART26001 能源与资源课讨论层状侵入体铬-铂族元素矿化的对象。**

---

### 5.4 通用描述建议与评分要点（材料原文，极重要）

> **General advice for describing minerals in thin section**
> - 有没有**解理迹线**？如果有不止一组，**它们之间的夹角是多少**？
> - 矿物有没有**双晶**？如果有，是**简单双晶**（只有一条可见双晶面）还是**聚片双晶**（同一晶体内有多组双晶面）？
> - **如果没有识别出任何平面构造，也要把这个观察记录下来。**
>
> **⭐ 评分要点原文**：*"These kinds of observations would be required if you needed to identify an unknown mineral in a thin section. **(And in an exam-style question you will pick up marks for recording these observations, even if you are not able to identify the mineral.)**"*
>
> **翻译成备考策略：在 practical test 里，即使认不出矿物，把系统的观察写全也能拿分。永远不要因为"不知道是什么"就交白卷。**

📎 **背景补充：Reference Guide 里的完整薄片描述框架**（本周虽未正式讲，但从第一次实习就该按这个格式记笔记）：
1. **肉眼特征**：粒度、有无斑晶、有无层理／条带、有无接触关系或包体。
2. **上镜前先通览整个薄片**，确保看到了所有矿物和整体结构，再动笔。
3. **素描要求**：大（至少半页，约 10 cm）；**必须有比例尺**（用透明尺垫在镜下估视域直径；**不要写 "×10"／"×20"**，那只说明物镜倍数，不等于图的比例）；用线条粗细、明暗和颜色表现细节。
4. **描述顺序**：原生大晶体（斑晶、堆晶）→ 原生小晶体（基质、粒间）→ 副矿物（尖晶石、不透明氧化物、磷灰石、榍石、锆石）→ 次生矿物（蛇纹石、绿泥石）。每种矿物记：粒度/习性/形状、颜色与多色性、成分（若薄片能定）、双晶/环带/出溶、蚀变。
5. **描述结构（texture）** → 用结构证据**推结晶顺序**（不要用鲍文序列）。
6. **分类岩石** → **解释成因序列**。

### 5.5 附加题（Bonus question）

> 一个**四方（tetragonal）**矿物，格参数 *a* = 12 Å、*c* = 6 Å，具有**体心（body-centred）**格子；有一个米勒指数为 **(001)** 的**镜面**；以及 **{100}** 和 **{010}** 两组完全解理。画出该矿物的 **(100)** 与 **(001)** 截面投影（即分别沿 **x** 轴和 **z** 轴俯视），标出晶胞形状、镜面与解理面、以及格点的位置。

材料注明：**"Solutions available on request! Please email me if you attempted this question and would like feedback on your work."**（答案需向老师索取。）

📎 **背景补充：解题思路**（材料未给答案，以下为本笔记的推导，仅供参考，建议照老师的邀请把自己的作图发去要反馈）：

**先整理条件**：四方系 → *a* = *b* = 12 Å ≠ *c* = 6 Å，α = β = γ = 90°。体心 → 除 8 个角上的格点外，晶胞正中心（½, ½, ½）还有 1 个格点，**每晶胞共 2 个格点**。

**（1）沿 z 轴俯视（(001) 截面，即 x–y 面）：**
- 看到一个**正方形**，边长 *a* = *b* = 12 Å（因为 a = b 且 γ = 90°）；
- **格点**：四个角各一个；体心格点在 z = ½ 处，投影到中心 → 画在正方形正中（可标注"位于 c/2 深度"）；
- **{100} 解理**：平行于 y–z 面，在这张投影上表现为**平行于 y 轴的一组竖直线**，间距 12 Å；
- **{010} 解理**：平行于 x–z 面，表现为**平行于 x 轴的一组水平线**，间距 12 Å；
- 两组解理在这张投影上**互相垂直**——这正是四方系"a = b"的直接后果，也是薄片里该矿物基面切面会显示 **90° 两组解理**的原因；
- **(001) 镜面**：垂直于 z 轴，因此**平行于纸面**，在这张俯视图上**看不到**（只能标注"镜面 ∥ 纸面"）。

**（2）沿 x 轴俯视（(100) 截面，即 y–z 面）：**
- 看到一个**矩形**，宽 *b* = 12 Å（水平），高 *c* = 6 Å（竖直）——**宽是高的两倍**；
- **格点**：四个角各一个；体心格点在 x = ½ 处，投影到矩形中心；
- **{010} 解理**：平行于 x–z 面 → 在这张图上是**平行于 z 轴的竖直线**，间距 12 Å；
- **{100} 解理**：平行于 y–z 面 → **平行于纸面**，在这张投影上看不到（标注即可）；
- **(001) 镜面**：垂直于 z 轴 → 在这张图上是一条**水平线**，把矩形从中间（c/2 高度）横切开。

**（3）自检**：镜面 (001) 必须与体心格点的位置相容——体心格点在 z = ½，镜面在 z = ½ 处，格点正好落在镜面上，自洽。

---

## 六、易错点 / 重点难点

**【晶体学几何】**

1. **⭐ 米勒指数不是笛卡尔坐标**（老师亲自点名的头号陷阱）。(110) **不是**"从原点连到点 (1,1) 的线"，而是"在 x 轴 1 个晶胞重复处、y 轴 1 个晶胞重复处截取、与 z 轴平行的**平面**"。做题时永远问"平面在哪儿截轴"，不要问"点在哪儿"。

2. **⭐ 必须盯住同一个平面**。求指数时若沿 +x 和 +y 分别碰到的是**两个不同**的平面，说明其中一个方向要走**负向**，指数带上划线。老师口诀："how many unit cell repeats from the origin, **but also to be looking at the same plane**"。

3. **截距与指数是倒数关系，方向相反**。截距**越小**（越靠近原点），指数**越大**。h = 2 意味着在 ½ 处截取，不是在 2 处。

4. **括号必须区分**：`(hkl)` = 单个平面；`{hkl}` = 一整组；`[uvw]` = 方向（本周未涉及但迟早遇到）。**描述一组平面时化到最小整数，描述单个平面时不能化简**——(200) 和 (100) 是不同位置的平面，但它们属于同一个 {100} 集合。

5. **指数 0 表示"平行于该轴、永不相交"**，来自 1/∞ = 0。不要写成"截距为 0"。

6. **x 轴习惯画向页面下方**。看图和画图都要先确认坐标轴取向，Practical Part 1 的官方提示就是在防这个。

7. **三方晶系的格角**：正确条件是 α = β = γ **≠ 90°**（不是 = 120°）。讲义前后不一致，以后面的表（2.4 与 3.2 节）为准。**六方系才有 γ = 120°，且六方是 a = b ≠ c、α = β = 90°。**

8. **面心 F 别漏了 6 个面**：8×⅛ + **6×½** = 4，不是 2。C 底心才是 8×⅛ + 2×½ = 2。**I 和 C 的格点数都是 2 但位置完全不同**，别混。

9. **"最小对称要求"是下限不是等式**。立方系"至少"有 4 个三次轴，实际上还有更多；判定晶系时，**只要缺了必需对称就一定不是该晶系**，但有更多对称不影响归属。

10. **Z 值 ≠ 格点数**。Z 数的是"化学式单位"，格点数数的是"重复位置"。

11. **单斜系的 β > 90° 是选胞约定**，物理条件是 β ≠ 90°。

12. **14 不是 7 × 5**。很多组合会退化为已有类型或破坏必需对称，所以数出来是 14。

**【晶形、习性、自形程度：三个独立的维度】**

13. **不要混淆晶形（form）、习性（habit）、自形程度（euhedral/subhedral/anhedral）**：
 - **晶形**：由内部对称决定的一组等价晶面（几乎不可变）；
 - **习性**：三维上的长宽高比例（受晶形 + **生长条件**共同控制，**同一矿物可有多种习性**，如辉长岩中板状 vs 玄武岩中针状的斜长石）；
 - **自形程度**：晶面发育得好不好（几乎完全由结晶时的空间和时间条件控制）。

14. **只有自形晶体能反推内部对称**。他形晶体的浑圆轮廓不携带对称信息——Practical Part 2 一定要挑发育良好的模型。

15. **"特征形状"是三维习性 × 切面方向的产物**。角闪石在薄片里的"细长带一条解理"和"八边形带两条解理"是**同一种晶体的两种切面**，不是两种习性。同理，黑云母的近六边形切面之所以罕见，是因为随机切面很少恰好平行于片层。

**【薄片观察】**

16. **⭐ 弯的 = 不是解理**。解理按定义是**平面**，平面与薄片切面相交只能是**直线**。橄榄石的弯曲裂隙是断口（fracture），不是解理。

17. **⭐ 解理与双晶的鉴别流程**：
 - PPL 下就有清晰黑线 → 多半是**解理**（折射率对比）；
 - PPL 下几乎看不见、XPL 下才出现平行条带 → **双晶**；
 - **转动载物台，条带交替消光** → 决定性证据，是**双晶**；解理迹线不会交替消光。

18. **单条 vs 多条双晶**：**简单双晶**（1 条，如角闪石）vs **聚片双晶**（多条平行，如斜长石）。这是描述里必须写明的。

19. **解理夹角是核心判据，但只在正确的切面上量**：
 - **角闪石约 56°/124°**（实习答案说"约 60°"）；
 - **辉石约 87°/93°**（实习答案说"90°"）；
 - **必须在垂直于柱轴的基面切面上量**；斜切面会把角度"投影"得偏大或偏小。**只看到一组解理，不代表这个矿物只有一组解理**——很可能是切面方向的问题。

20. **cpx / opx 的区分**（Reference Guide）：opx **平行消光**且**从不双晶**；cpx **斜消光**、可能有双晶、干涉色更高、可能带粉褐色和多色性。量消光角要**挑只有单组解理迹线、且干涉色最高的晶体**。

21. **多色性只在 PPL 下观察**，XPL 下会被干涉色淹没。观察方法是**转动载物台一整圈**，看颜色如何随解理相对于偏光振动方向的取向而变。

22. **不透明矿物的鉴定要谨慎**：实习答案本身也用了 "probably magnetite"、"this is spinel" 这样的措辞。薄片透射光下只能定到"不透明氧化物"这个层级，精确定名需要反射光显微镜或电子探针。

**【课程与考试】**

23. **Reference Handout 是唯一能带进 practical test 的资料，而且要靠自己写满。**从第一周开始就往上面记判据、数值、诀窍——这是本周最高性价比的行动项。老师课上讲格角约定时就直接说了"写到你的 handout 里"。

24. **紫色标签的幻灯片不考**，复习时可以降优先级。

25. **老师承诺不考徒手三维作图**，问题会拆成二维投影。所以对 3.6 那一串三维图，目标是**能读懂并能画出对应的二维投影**（如 3.7 的角闪石题），而不是能徒手画立体图。

26. **听录音时注意老师的口误**：角闪石那题一度说成 "C equals 105"（应为 c = 5 Å, β = 105°）；立方系最小对称说成 "three, sorry, four triads"（应为 4 个三次轴）。

27. **讲义比课堂内容多**。老师课上明确跳过了二维晶胞配置的细节（"I won't go into that now"），并让大家去看课前视频。**二维五种格子、五种三维晶胞、14 布拉维格子的完整列举、32 点群/230 空间群流程图，都要靠自己补。**

---

## 七、本周术语表

### 晶体学基础

| 中文 | English | 说明 |
|---|---|---|
| 矿物 | mineral | 天然、无机、固体、有特征成分、有规则内部原子排列 |
| 晶体格子 | crystal lattice | 空间中一组假想点，每点物理化学环境完全相同 |
| 格点 | lattice point | 在空间中重复的原子／原子团／图案单元 |
| 基元 | motif | 重复的那一组原子；格子 + 基元 = 结构 |
| 结构 | structure | Lattice + Motif = Structure |
| 晶胞 | unit cell | 最小的、能定义晶体特征对称性的重复单元 |
| 格参数 | lattice parameters | 晶胞的物理尺寸：a、b、c、α、β、γ |
| 埃 | ångström (Å) | 10⁻¹⁰ m；格参数的常用单位 |
| Z 值 | Z | 每个晶胞内所含的化学式单位数 |
| 晶系 | crystal system | 七种：立方、三方、四方、六方、斜方、单斜、三斜 |
| 布拉维格子 | Bravais lattice | 7 晶系 × 5 晶胞类型的 14 种合法组合 |
| 原始（晶胞） | primitive (P) | 格点仅在角上；1 个格点／晶胞 |
| 体心（晶胞） | body-centred (I) | 角 + 体对角线交点；2 个格点／晶胞 |
| 面心（晶胞） | face-centred (F) | 角 + 每个面的中心；4 个格点／晶胞 |
| 底心（晶胞） | C face-centred (C) | 角 + 一对相对面的中心；2 个格点／晶胞 |
| 菱面体（晶胞） | rhombohedral (R) | 格点仅在角上；三方晶系专用 |
| 立方晶系 | cubic | a = b = c，α = β = γ = 90°；4 triads；对称性最高 |
| 三方晶系 | trigonal | a = b = c，α = β = γ ≠ 90°；1 triad |
| 四方晶系 | tetragonal | a = b ≠ c，全 90°；1 tetrad |
| 六方晶系 | hexagonal | a = b ≠ c，α = β = 90°、γ = 120°；1 hexad |
| 斜方晶系 | orthorhombic | a ≠ b ≠ c，全 90°；3 个互相垂直的 diad |
| 单斜晶系 | monoclinic | a ≠ b ≠ c，α = γ = 90°、β > 90°；1 diad |
| 三斜晶系 | triclinic | a ≠ b ≠ c，角均 ≠ 90°；无必需对称；对称性最低 |

### 对称

| 中文 | English | 说明 |
|---|---|---|
| 对称操作 | symmetry operator | 反映、旋转、倒反及其组合 |
| 镜面／反映 | mirror plane / reflection | 立方体有 9 个镜面 |
| 旋转 | rotation | 阶次只能为 1、2、3、4、6 |
| 二次轴 | diad | 180° 旋转对称 |
| 三次轴 | triad | 120° 旋转对称 |
| 四次轴 | tetrad | 90° 旋转对称 |
| 六次轴 | hexad | 60° 旋转对称 |
| 恒等 | identity | 1 次；360° |
| 对称中心／倒反中心 | centre of symmetry / centre of inversion | 过一点两端等距处有等同原子 |
| 旋转倒反 | rotoinversion | 旋转与倒反的组合 |
| 必需对称 | essential symmetry | 判定晶系的最低对称要求 |
| 点群 | point group | 7 晶系 + 宏观对称 → 32 个 |
| 空间群 | space group | 14 布拉维格子 + 32 点群 + 微观对称 → 230 个 |
| 滑移面 | glide plane | 反映 + 平移（📎 补充术语） |
| 螺旋轴 | screw axis | 旋转 + 平移（📎 补充术语） |
| 晶体学限制定理 | crystallographic restriction theorem | 解释为何无 5 次轴（📎 补充术语） |

### 晶形与习性

| 中文 | English | 说明 |
|---|---|---|
| 晶形 | crystal form | 由内部对称决定的一组等价晶面 |
| 晶体习性 | crystal habit | 高、宽、长的比例；受晶形与生长条件共同控制 |
| 自形 | euhedral | 晶面完美；典型的早结晶矿物 |
| 半自形 | subhedral | 部分晶面发育中等 |
| 他形 | anhedral | 无晶面，形状不规则或浑圆 |
| 等轴状 | equant | 各方向尺寸相近 |
| 板状 | tabular | 如辉长岩中的斜长石 |
| 柱状 | prismatic | 如角闪石 |
| 针状 | acicular | 如玄武岩基质中的斜长石 |
| 纤维状 | fibrous | 某一方向极度拉长 |
| 片状／云母状 | platy / micaceous | 如黑云母 |
| 骨架状 | skeletal | 分枝树状、内有空腔；极快速生长（Ref. Guide） |
| 港湾状／熔蚀 | embayed | 晶面凹陷，由部分熔蚀造成（Ref. Guide） |
| 筛状 | sieve | 内含大量互连玻璃包体（Ref. Guide） |

### 平面构造与米勒指数

| 中文 | English | 说明 |
|---|---|---|
| 米勒指数 | Miller index (hkl) | 轴截距的倒数 |
| 平面组／晶形 | set of planes {hkl} | 具有相同对称性质的一整组平面 |
| 上划线（负指数） | bar (e.g. 1̄) | 在该轴负方向截取 |
| 解理 | cleavage | 沿键合最弱晶面族的规则破裂；PPL 下最清楚 |
| 底面解理 | basal cleavage | {001}；如黑云母、白云母 |
| 柱面解理 | prismatic cleavage | 如辉石 {110}、角闪石 {110} |
| 双晶 | twinning | 取向不同但按对称关系相关的晶体域 |
| 双晶面 | twin plane | 如角闪石的 {100} |
| 简单双晶 | simple twinning | 只有一条可见双晶面（角闪石） |
| 聚片双晶 | lamellar / polysynthetic twinning | 多条平行双晶面（斜长石） |
| 断口／裂隙 | fracture | 不规则破裂；弯曲即非解理 |
| 贝壳状断口 | conchoidal fracture | 橄榄石的典型特征（📎 补充术语） |

### 显微镜与光性（本周初步接触）

| 中文 | English | 说明 |
|---|---|---|
| 偏光显微镜／岩石薄片显微镜 | polarizing / petrological microscope | 本周第一次使用 |
| 薄片 | thin section | 标准厚度 30 μm |
| 单偏光 | plane-polarized light (PPL) | 观察颜色、多色性、解理、突起 |
| 正交偏光 | cross-polarized light (XPL) | 观察双晶、消光、干涉色 |
| 多色性 | pleochroism | 吸收随振动方向变化造成的颜色变化 |
| 消光 | extinction | XPL 下晶体变黑的位置 |
| 消光角 | extinction angle | 区分 opx（平行消光）与 cpx（斜消光）的关键 |
| 平行消光 | straight / parallel extinction | 斜方系矿物 |
| 斜消光 | inclined extinction | 单斜系矿物 |
| 双折射率 | birefringence (δ) | 橄榄石 0.035–0.052；普通辉石 0.018–0.033 |
| 干涉色 | interference colour | 由光程差 Γ = d·δ 决定 |
| 突起 | relief | 折射率对比造成 |
| 贝克线 | Becke line | 比较折射率的方法（Ref. Guide） |
| 不透明矿物 | opaque mineral | 透射光下全黑，如磁铁矿、铬铁矿 |

### 本周出现的矿物与岩石

| 中文 | English | 出处 |
|---|---|---|
| 角闪石 | hornblende | 讲义例题；RFM7 |
| 斜长石 | plagioclase | 讲义；13415 主矿物 |
| 碱性长石 | alkali feldspar | RFM7、SW |
| 正长石 | orthoclase | 讲义（单斜系例子） |
| 钠长石 | albite | 讲义（三斜系例子） |
| 黑云母 | biotite | 讲义；SW 主矿物 |
| 白云母 | muscovite | 讲义；SW |
| 石英 | quartz | SW |
| 橄榄石 | olivine | 讲义；R1 主矿物 |
| 单斜辉石／普通辉石 | clinopyroxene / augite | 13415、R1 |
| 斜方辉石 | orthopyroxene | 13415 |
| 顽火辉石 | enstatite (Mg₂Si₂O₆) | Ref. Guide |
| 磁铁矿 | magnetite | 13415 |
| 尖晶石（族） | spinel (group) | 讲义（立方系例子）；R1 |
| 磷灰石 | apatite | RFM7 |
| 石榴子石 | garnet | 讲义（立方系例子） |
| 石盐 | halite | 讲义（立方系、三组解理） |
| 方铅矿 | galena | 讲义（三组解理） |
| 重晶石 | barite | 讲义（斜方系例子） |
| 黄铁矿 | pyrite | 讲义（平面构造例子） |
| 正长岩 | syenite | RFM7 |
| 粗玄岩 | dolerite | 13415、R1 |
| 花岗岩 | granite | SW |
| 辉长岩 | gabbro | 讲义（斜长石习性对比） |
| 玄武岩 | basalt | 讲义（斜长石习性对比） |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `W1 notes.md`，2.2 节"七大晶系"表（该表在 PDF 中重复出现 6 次） | Trigonal (rhombohedral)：*a = b = c*，**α = β = γ = 120°** | **格角标错**，且与同一份讲义后文自相矛盾：2.4 节（布拉维格子表）与 3.2 节（必需对称表）都写作 **α = β = γ ≠ 90°** | 应为 **α = β = γ ≠ 90°**。菱面体格子的三个格角相等但不等于 90°（且必须小于 120°，否则退化）。**γ = 120° 是六方晶系的特征**（配合 a = b ≠ c、α = β = 90°），把它安到三方系上会与六方系混淆。复习时以 2.4／3.2 两张表为准。 |
| `W1 notes.md`，1.2 节"Types of 2D unit cell"图 | 五种二维晶胞列为：oblique / rectangular / centred rectangular / square / **rhombohedral**（a = b, γ = 120°） | **术语误用**。二维五种布拉维格子中，a = b、γ = 120° 的那一种标准名称是**六方（hexagonal）**（有时也叫 rhombic）；**rhombohedral（菱面体）是三维术语**，专指三方晶系的 R 格子 | 该二维格子应称 **hexagonal（六方）**。同一份讲义在 2.3 节又用 "Rhombohedral (R)" 指三维菱面体晶胞，两处同名不同义，极易混淆。 |
| `W1 notes.md`，2.3 节"The five types of 3D unit cell" | 依次列出 **Primitive (P)** / **Face-centred (F)** / **Rhombohedral (R)** / *(无标题)* "Lattice points at corners, and at the centre of one pair of opposite faces" / **Body-centred (I)** | **第四项缺少标题**，描述句孤立地夹在 R 与 I 之间，读起来像是 R 的补充说明 | 该无标题项应为 **C face-centred (C)（底心）**。依据：2.4 节的布拉维格子表里，斜方与单斜系的可用晶胞类型都含 **C**；且讲义下一页的练习题 "See if you can work out the number of lattice points in a C face-centred unit cell" 正是针对它。（推测为 PDF → md 转换时丢失了加粗小标题。） |
| `Practical 1 solutions.md`，薄片 R1 橄榄石"弯曲裂隙"一题的答案 | "Olivine does actually have **three cleavage traces at 90°** to each other, but they are usually very faint or invisible in thin section." | **解理组数存疑**。标准矿物学描述（Deer, Howie & Zussman；Ref. Guide 的橄榄石／普通辉石对照表也只说 "Cleavage rarely visible"）给出橄榄石的解理为 **{010} 中等** 与 **{100} 不完全**，即**两组互相垂直的不完全解理**，另有贝壳状断口 | 应为**两组互相垂直的不完全解理（{010} 与 {100}）**。"三组"可能是与石盐／方铅矿的三组 90° 解理串了行。不过该答案的**核心论证（弯曲 ⇒ 不是解理，因为解理是平面，在薄片中必为直线）完全正确**，不受此影响。 |
| `EART22201 - 06-Oct-transcript.md`，角闪石例题开头 | "A equals 10, B equals 18, **C equals 105**, and beta, that's the lattice angle, sorry, **C equals five**, and **B equals 105**." | **老师口误**，已当场自纠；转写把 "beta" 写成了 "B" | 正确格参数：***a* = 10 Å，*b* = 18 Å，*c* = 5 Å，β = 105°**（与 `W1 notes.md` 5.1 节一致）。 |
| `EART22201 - 06-Oct-transcript.md`，讲立方系必需对称处 | "the minimum symmetry is to have **three, sorry, four** triads" | **老师口误**，已当场自纠 | 正确：**立方系的必需对称是 4 个三次轴（4 triads）**，对应 4 条体对角线。 |
| `EART22201 - 06-Oct-transcript.md`，讲花括号 {hkl} 处 | "once you've worked out one, you can then get the set by defining the set of **mutually perpendicular** plane" | **前后矛盾**：同一段前文老师明确说 "They're all **mutually parallel**. They're never going to intersect one another." | 按本课的用法应为 **mutually parallel（互相平行）**——多半是自动转写把 parallel 听成 perpendicular。（📎 需要注意：在**标准晶体学**中 {hkl} 确实指由对称操作联系的**等价面族**，在立方系里它们恰恰是互相垂直的，所以老师这句话未必是口误，也可能是在暗示更严格的定义。**答题时按本课"整叠平行面"的用法。**） |
| `EART22201 - 06-Oct-transcript.md`，课程概览处 | "we're gonna apply all of that knowledge to look at **magnetism** and volcanism in different plate tectonic settings" | **自动转写错误** | 应为 **magmatism（岩浆作用）**，不是 magnetism（磁性）。同类转写错误还有 **"uhedral"** 应为 **euhedral**（自形），全文出现 3 次。 |
| `EART22201 Reference Guide 2025.md`，"Chemical classification" 节的 SiO₂ 分类表 | \<45 ultramafic；**45–52 mafic**；**53–62 intermediate**；**>63 felsic** | **区间不连续**：52–53 wt.% 与 62–63 wt.% 落在任何一类之外 | 边界应连续，通行划分为：<45 超镁铁质；**45–52** 镁铁质；**52–63** 中性；**>63** 长英质。表中的 53 与 63 应理解为"≥53"式的取整表述，使用时按连续边界处理即可。 |
| `EART22201 Reference Guide 2025.md`，若干处 | "serpentite (alteration of olivine)"；"chorite (alteration of biotite)"；"the phenocryst **plase**"；"Quartz-Alkali feldspar-Plagioclase-**Feldsathoid** (QAPF)"；"Use the texture determine the order of crystallization" | **拼写／漏字**（多为 PDF 提取或原文录入错误） | 应分别为 **serpentine（蛇纹石）**、**chlorite（绿泥石）**、**phase**、**Feldspathoid（似长石）**、"Use the texture **to** determine…"。 |
| `Practical 1 solutions.md`，薄片 R1 最后一问 | "You should also notice an opaque oxide mineral – **this is spinel**." | **命名过于笼统**（非硬性错误，记录以免误记） | Rum 层状侵入体中的不透明尖晶石族氧化物通常是**铬铁矿（chromite, FeCr₂O₄）**。狭义端元尖晶石 **MgAl₂O₄** 在薄片中一般是**透明**的（绿至褐色），不会呈不透明。此处 "spinel" 应理解为"**尖晶石族矿物**"。 |
| `Practical 1 solutions.md`，薄片 RFM7 双晶一题 | 问题："**Is the twinning best seen in plane-polarized or cross-polarized light?** Does hornblende show simple twinning or lamellar twinning?" 答案只回答了后半问 | **答案不完整**：前半问未作答 | 相邻的解理一题明确答了 "Cleavage is usually best seen in PPL"，双晶一题却漏掉了对应答案。按光学原理，**双晶应在 XPL 下观察**（双晶域取向不同 → 消光位不同；PPL 下两侧成分相同、无对比）。此为本笔记的补充，材料未说明。 |
