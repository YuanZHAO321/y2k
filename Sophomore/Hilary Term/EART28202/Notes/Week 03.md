# EART28202 Structural Geology — Week 03 学习笔记

> **本周材料清单**
> - 讲义主干：`Lecture/Week 3/Class3_Strain.md`（Class 3: Strain，45 张幻灯片 + notes pane 注释，约 9,155 词）
> - 练习：`Practical/Week 3/2-CoverAns.md`（四道应变分析练习 + 答案，约 2,545 词）
> - 练习附件：`Logs.md`（对数复习）、`Fig1soln.md`（Exercise 1 图 1 的切面判定）、`4-Ex3sol2.md`（OCR 失败，无可用信息）
> - 背景：`(EART28202) Structural Geology.md`（课程大纲）

---

## 一、本周主题

### 1.1 本周讲什么

本周主题是**应变（strain）**——即**"岩石变形了多少"的定量描述**。讲义 Slide 2 给出了本课的出发点：

> "To develop our understanding of the origin and significance of geological structures, we need to quantify the deformation that they record. This is achieved with the concept of strain – strain is a measure of the change in size and shape that a body experiences during deformation."

即：**应变是物体在变形过程中所经历的"大小变化 + 形状变化"的度量**。这句话是本周所有内容的定义性起点，请一字不差地记住——它同时点出了应变的两个组成部分：**尺寸变化（线应变 linear strain）**与**形状变化（剪应变 shear strain）**。

配套 Practical 是**有限应变测量技术（Finite strain measurement techniques）**，四道练习分别覆盖：三维应变的图解表示（Flinn 图 + Hsü 图）、Mohr 圆应变分析、Fry 法、Rf/φ′ 法。

### 1.2 在全课骨架中的位置

课程大纲的 syllabus 顺序是：

| 周次 | Theory | Practical |
|---|---|---|
| 1 | 褶皱的基本几何特征及伴生小构造 | 用赤平投影分析褶皱几何 |
| 2 | 褶皱如何形成 | 基于地质图的褶皱几何巩固；构造史编制 |
| **3** | **应变（Strain）** | **有限应变测量技术** |
| 4 | 剪切带（Shear zones） | 用赤平投影分析断层几何 |
| 5 | 应力（Stress） | 用 Mohr 圆做应力分析 |
| 6 | 破裂与小型侵入体的就位 | 用 Mohr 图分析破裂 |
| 7 | 断层作用 | 绘制精确的褶皱剖面面切面 |
| 8 | 挤压构造背景 | 可复原剖面与平衡剖面 |
| 9–10 | 野外课程 | 野外课程 |
| 11 | 伸展构造背景 | 分析脆性与韧性剪切带组构 |
| 12 | 走滑构造背景 | 基于地质图的褶皱与断层巩固 |

可以清楚看出全课的三段式骨架：**几何学（W01–W03）→ 力学（W04–W06）→ 构造类型（W07–W12）**。

**本周正处在几何学段的收尾、力学段的门槛上**：

- **承前**：W01 与 W02 讲褶皱的几何与成因，用的是纯几何语言（枢纽、轴面、翼间角、剖面面）。本周把"变形"这件事从"看起来什么样"升级为"变了多少、以什么方式变"，给出可以填进方程的数字。EART24001 地质图课教的是"读出产状与形态"，本课从本周起把这些几何量转化为力学量。
- **启后**：讲义 Slide 1 的 notes pane 明说：

  > "The contents of this class and that describing stress (Class 5) are fundamental for taking a more quantitative approach to rock deformation/structural geology. **This is where mere description starts to turn into modelling** (conceptual, analytical or numerical) and hence into the development of a deeper understanding of how rocks deform."

  即：**应变（Class 3）+ 应力（Class 5）= 从"描述"跨到"建模"的两块基石**。本周讲"变形了多少"，W05 讲"为什么会变形"（施加了什么力）。W04 剪切带则是本周内容的直接应用——Slide 17 的 notes 明确预告："We shall return to the plane strain, simple shear case next week – it is an important starting point for considering strain in shear zones."

### 1.3 与考核的关系

大纲中，本周内容对应 **ILO 5**："quantify strains from deformed objects, evaluate normal and shear stresses acting on planes of different orientations using graphical techniques"。

大纲在 Feedback methods 一节特别写明：Theory 笔试（50%，2.5 小时）是"diagrammatic, short answer questions primarily on Theory session content **but with aspects that were developed in the practicals (e.g., stress and strain analysis)**"。也就是说，**本周的 Practical 技术（Flinn/Hsü 图、Mohr 应变圆、Fry 法、Rf/φ′ 法）会出现在理论卷上**，不是只在 Practical 卷考。这一点务必重视。

---

## 二、核心概念

### 2.1 量化变形的第一步：把"变形"拆成三个词

讲义 Slide 6 给出了本课最容易混淆、也最必须分清的三个词。量化变形的做法是：把地质体看成**连续的质点集合（a continuum of particles）**，比较每个质点在初始态与变形态的位置。

| 概念 | 英文 | 讲义定义 | 关键点 |
|---|---|---|---|
| **位移** | Displacement | 描述**某个给定质点位置的改变** | 单个质点的事 |
| **应变** | Strain | 描述质点**彼此之间**相对位置的改变，即质点间**距离**的变化 | 质点之间的事 |
| **变形** | Deformation | 泛指位移；**可能包含应变，也可能不包含** | 最宽泛的词 |

讲义给的判别语是：**"rigid displacement of a body is deformation, but it is not strain"**（刚性位移是变形，但不是应变）。

Slide 6 配的照片极具说明力：1999 年台湾一次逆断层滑动，断层正好从一栋房子底下通过；房子发生的"deformation"几乎全部是**刚体转动**，房子本身几乎没有 strain——讲义评论说这是那房子施工质量的明证。

应变按大小又分两档：

- **无限小应变（infinitesimal strain）**：质点间距离变化很小；
- **有限应变（finite strain）**：变化大到可测量。

📎 背景补充：构造地质学野外测到的几乎都是 **finite strain**（有限应变），因为地质变形量通常极大；而工程地质、地震波传播、井壁变形等问题里，**infinitesimal strain approximation**（无限小应变近似）成立，数学被大幅简化。讲义 Slide 9 的 notes 正是这么说的："Treating the displacements as small enough for this to be true is described as the infinitesimal strain approximation. It leads to a great simplification of the mathematics and is valid for many rock mechanics problems of interest (e.g., deformation around boreholes, deformation during the passage of a seismic wave)."

### 2.2 四种位移类型：哪些产生应变？

Slide 7 列出**四种基本位移类型**，这是本周最常考的分类之一：

1. **刚体平移（Rigid body translation）**——体内每个质点朝同一方向移动同样距离。位移矢量全部相同。
2. **刚体转动（Rigid body rotation）**——物体的整体物理转动。位移矢量**不**全相同（取决于质点相对转轴的位置），但**质点间距离不变**。
3. **畸变 / 形状变化（Distortion）**——质点相互之间发生位置改变，位移矢量不全相同。
4. **膨胀 / 体积变化（Dilation）**——体积改变而形状不变。

**结论（必背）**：

> 变形（deformation）涵盖全部四类位移，但**只有畸变（distortion）与膨胀（dilation）产生应变**——因为只有这两类改变了质点之间的距离。

📎 背景补充：这条结论就是后面所有数学处理的动机——**做应变分析的第一步永远是"把刚性平移和刚性转动剔除掉"**。剔除刚性平移靠"取梯度"（Slide 8），剔除刚性转动靠"取位移梯度矩阵的对称部分"（Slide 9）。

### 2.3 从变形梯度矩阵到应变张量（Slides 8–13）

这一段是讲义中数学味最重的部分。**讲义 Slide 8 的 notes pane 明确划定了考试要求的下限**，请照抄记忆：

> "Slides 8-13 provide a short introduction to the core concepts in the mathematical theory of strain. … As far as this course unit is concerned, **all I would like you to take away from these six slides is (a) that the state of strain at a point is not a single number but rather is a matrix of 9 terms (in 3d) of which 6 are independent, and (b) that the linear (longitudinal) strains are the terms on the leading diagonal of this matrix while the (tensor) shear strains are the off-diagonal terms.**"

也就是说，**必须掌握的只有两条**：

- **(a)** 一点处的应变状态**不是一个数**，而是三维下 **9 个分量的矩阵，其中 6 个独立**；
- **(b)** **主对角线上是线应变（longitudinal strain），非对角线上是（张量）剪应变**。

其余（矩阵代数、Lagrangian/Eulerian 描述、∇u 算符、StrainNote.pdf）都是"给感兴趣的人看的"。Slide 5 的 notes 也明说：随讲义附有 `StrainNote.pdf`，"**You do NOT need to know the contents of this document for this course unit**"，但将来从事岩石力学（工程地质、地球物理）者会用得上。

不过下面的概念链条仍值得理解一遍：

- **变形梯度矩阵（deformation gradient matrix）**（Slide 8）：二维下，质点原位置 (x, y)、变形后位置 (x\*, y\*)，则
  - x\* = D₁₁x + D₁₂y + A₁
  - y\* = D₂₁x + D₂₂y + A₂

  其中 A₁、A₂ 是平移项。**用"梯度"工作的好处**：刚性平移的影响被消掉了——讲义指出，一块岩石自形成以来到底平移了多远，一般根本无法确定。
  - **Lagrangian 描述**：用原位置给出变形后位置（如上式）；**Eulerian 描述**：反过来，用变形后位置给出原位置。

- **位移梯度矩阵（displacement gradient matrix）**（Slide 9）：变形梯度矩阵里仍含刚体转动。于是改用位移 u = x\* − x、v = y\* − y，考察位移在一点邻域内如何变化（即位移梯度）。然后把位移梯度矩阵**拆成对称部分与反对称部分**：
  - **对称部分 = 应变**（畸变 + 膨胀）
  - **反对称部分 = 转动**

  讲义 Slide 9 notes 的结论句：**"when we refer to strain, we are actually referring to the symmetric part of the displacement gradient matrix."**

- **线应变的物理意义**（Slide 11）：取 P(x, y)、Q(x+Δx, y)、R(x, y+Δy) 三点，若变形时角度不变，则 ∂u/∂x = [P\*Q\* − PQ] / PQ = (L − L₀)/L₀，即**长度变化 / 原长**——正是 x 方向的工程应变。

- **张量剪应变的物理意义**（Slide 12）：允许 PQ 与 PR 之间的夹角改变，则非对角项 = **两条原本正交的线之间夹角变化量的正切的一半**，即张量剪应变。由于应变矩阵是位移梯度矩阵的对称部分，故 **e_xy = e_yx**。

- **应变是二阶张量（2nd rank tensor）**（Slide 13）：坐标架旋转时，矩阵各分量按一个特定的变换方程改变——满足这类变换方程的物理量称为张量。张量按**阶（rank）n** 分类，三维下需要 **3ⁿ** 个分量：
  - 0 阶 = 标量（3⁰ = 1，如温度）
  - 1 阶 = 矢量（3¹ = 3，如力）
  - 2 阶 = 张量（3² = 9，如**应变**、**应力**）
  - 3 阶（3³ = 27，如压电效应）
  - 4 阶（3⁴ = 81，如弹性——联系应力与应变）

  且 e₁₂ = e₂₁、e₁₃ = e₃₁、e₂₃ = e₃₂（对称性），故 9 个分量中只有 6 个独立。**应力（stress）也是二阶张量，W05 会再见到它**（它联系力与"描述受力面大小与方向的矢量"）。

### 2.4 应变椭圆与应变椭球（Slides 14–15）

**这是本周最核心的可视化工具。**

**应变椭圆（strain ellipse，二维）**：
- 它是**初始为圆形的标志物变形后的形状**（讲义强调：虚线圆是未变形的圆，**半径为 1**）。
- 它同时展示了**线应变与角剪切如何随方向变化**。
- 椭圆上存在**两个相互垂直的方向**（即椭圆的长轴与短轴），在这两个方向上伸长量取到**最大值与最小值**，且**角剪切为零**。这两个极值称为**主应变（principal strains）e₁ 与 e₂**，按定义 **e₁ ≥ e₂**。

> ⚠️ 拼写陷阱：讲义 Slide 14 notes 专门写了一句 "Note the spelling of 'principal'."——是 **principal**（主要的），不是 principle（原理）。这属于会被扣分的低级错误。

📎 背景补充：Slide 14 notes 提到，若把 (x, y) 坐标架对齐主应变方向，则应变矩阵非对角项全为零，对角项就是 e₁ 和 e₂。用线性代数的语言说：**主应变是应变矩阵的特征值（eigenvalues），主应变方向是其特征向量（eigenvectors）**。

**应变椭球（strain ellipsoid，三维）**：
- 它是**初始为球形的物体变形后的形状**。
- 三个半轴即三个主应变方向，习称 **X、Y、Z 方向**，其量值为：
  - **X = (1 + e₁)，Y = (1 + e₂)，Z = (1 + e₃)**
  - 按定义 **X ≥ Y ≥ Z**（X = 最长轴 = 最大伸长方向；Z = 最短轴 = 最大缩短方向）
- 三个主应变方向**互相正交，且在变形前也互相正交**——即沿它们剪应变为零，**并且它们是唯一具有此性质的方向**。这句话是主应变方向定义的完整表述，考试常考。

### 2.5 均匀应变与非均匀应变（Slide 20）

| | 定义（讲义原文要点） | 判据 |
|---|---|---|
| **均匀应变**<br>homogeneous strain | 物体每一小部分的大小与形状变化，与整个物体的变化**成比例地相同** | **平面仍是平面，直线仍是直线，平行线仍平行** |
| **非均匀应变**<br>inhomogeneous strain | 大小与形状的变化**因地而异** | 上述三条不成立（如褶皱作用中直线变成曲线） |

讲义的关键说明：**"The remarks so far in this presentation refer to homogeneous strain. Real strains are inhomogeneous … However, inhomogeneously strained bodies can be analysed by subdividing them into a collection of small, approximately homogeneously deformed, domains."**

即：**本讲之前的一切讨论都建立在均匀应变假设上；真实应变都是非均匀的；处理办法是把物体切成许多小的、近似均匀变形的域**。这正是"为什么野外要在小范围内测应变、并注明测点位置"的理论根据。

### 2.6 几种重要的参考应变状态（Slides 16–17）

#### 二维（等面积的两个端元）

| | 简单剪切 Simple shear | 纯剪切 Pure shear |
|---|---|---|
| 定义 | 二维物体沿某给定方向受**均匀剪切**，无面积变化 | 无面积变化的**伸长或缩短** |
| 主应变轴 | **在变形过程中发生旋转** | **不旋转** |
| 术语 | **rotational（旋转的）、non-coaxial（非共轴的）** | **irrotational（非旋转的）、coaxial（共轴的）** |
| 形状变换 | 初始正方形/矩形 → **平行四边形** | 初始正方形/矩形 → **不同长宽比的矩形** |

讲义 Slide 16 notes 的两句要点：

1. **"One might think that pure shear and simple shear are too simplistic to be of much interest in real deformation, but field observations suggest that situations where these idealizations may be applied are actually very common."**（不要以为这两个端元太理想化——野外观察表明它们适用的情形其实非常普遍。）
2. **术语的严格区分**（易考的细节）：

   > "Strictly speaking, coaxial and irrotational are not synonymous: **rotational/irrotational refers to whether the finite principal strain axes change orientation with respect to some coordinate frame; a coaxial deformation is one in which the finite principal strain axes are parallel to those of the incremental strain ellipsoid.**"

   即：**旋转/非旋转**说的是**有限应变主轴相对某坐标架是否改变方向**；**共轴**说的是**有限应变主轴是否与增量应变椭球的主轴平行**。两者在纯剪/简单剪切这两个端元下恰好同时成立或同时不成立，但概念上不等同。

#### 三维

- **平面应变（plane strain）**：**在某一个主方向（Y 方向）上既无拉伸也无缩短**。此时应变可以当作二维问题处理。
  - 讲义给的实例：**平面应变型的简单剪切**——在大应变下，**X 平行于剪切方向，Z 垂直于剪切面，Y 位于剪切面内、与 X 成直角且沿它无拉伸或缩短**。这是 W04 剪切带的起点。
- **轴对称伸展 / 轴对称压缩（axially symmetric extension / compression）**：一种非旋转变形，其中**两个主方向上的长度变化相等**。
  - 轴对称**伸展**：Y 与 Z 相等（→ 长棒形 prolate）
  - 轴对称**压缩**：X 与 Y 相等（→ 扁圆形 oblate）

### 2.7 应变椭球的形状分类与图解（Slides 18–19）

**应变类型的三分：**

| 类型 | 英文 | 形状比喻 | 轴关系 | 主导变形 |
|---|---|---|---|---|
| 长棒型 | **prolate** | **雪茄（cigar）** | X > Y ≈ Z | 一个方向上的**伸长**主导（constriction 收缩型） |
| 平面应变 | **plane strain** | 无 | Y 不变 | 二维 |
| 扁圆型 | **oblate** | **薄饼（pancake）** | X ≈ Y > Z | 一个方向上的**压扁**主导（flattening 压扁型） |

**Flinn 图（Flinn diagram）**（Slide 18）：
- 作法：**画 R_XY 对 R_YZ（通常取这两个比值的对数来画）**。
- 作用：**把长棒型（雪茄形）与扁圆型（薄饼形）的应变椭球分开**，即把"由一个方向的伸长主导的变形"与"由一个方向的压扁主导的变形"分开。
- **重要限制**：**应变量值总体上随远离原点而增大，但在图的不同区域之间比较应变量值并不容易——这张图不是为此设计的。**（这句是 Flinn 图与 Hsü 图分工的关键，常考。）

**Hsü 图（Hsü diagram）**（Slide 19）：
- 一种**能够表示应变量值**的替代图（讲义诚实地说 "albeit in a way that takes some getting used to"，即需要适应）。
- 应变量值由参数 **ε_S** 给出（见第三节公式），形状由 **Lode 参数 ν** 给出。
- 两参数画在**径向图（radial plot）**上，**应变量值随远离原点而增大**。

> 📎 背景补充：许多教科书（如 Ramsay）把"取自然对数后再画 R_XY 对 R_YZ"的版本单独称为 **Ramsay 对数图（Ramsay logarithmic plot / log-Flinn plot）**，而把不取对数的原始版本称为 Flinn 图。**本课讲义与练习不做这个区分——Slide 18 直接说 "usually logarithms of these ratios are plotted. Such a diagram is called a Flinn diagram"，练习 Exercise 1 第 3 步也是要求取自然对数后再画在"Flinn diagram"上。**因此在本课语境里，"Flinn 图"默认就是对数版本。答题时按讲义口径即可，但要知道两种叫法指的是同一族图。

### 2.8 递进变形（Progressive deformation）（Slides 21–23）

**这是本周概念上最深的一节。**

**核心问题**：Slide 21 开宗明义——

> "**Strain relates the undeformed to the deformed state but says nothing about the deformation path between these two states.**"

即：**有限应变只联系"变形前"与"变形后"两个状态，对中间的变形路径一无所知。**

**解决办法**：把变形拆成**一系列小的应变增量（strain increments）**，每个增量的应变由**增量应变椭圆（incremental strain ellipse）**描述。

**有限应变椭圆 vs 增量应变椭圆**（讲义给的经典图示：九个相同应变增量叠加）：
- **有限应变椭圆（finite strain ellipse）**：**椭率与方位都在改变**；
- **增量应变椭圆（incremental strain ellipse）**：**保持不变**（因为任意两阶段之间的位移变化量是恒定的）。

**四象限 / 八扇区分析**（Slide 22）：
- 每个应变椭圆都可以被**两条"无有限纵向应变的线（lines of no finite longitudinal strain）"**分成**四个象限**：其中线段被**伸长（L）**或被**缩短（S）**。
- 把**有限**应变椭圆与**增量**应变椭圆叠合起来，若两者方位不同，则定义出**八个扇区**，对应四种变形情形组合：

| 代号 | 含义 |
|---|---|
| **SS** | 已缩短，且下一增量**继续缩短** |
| **LS** | 已伸长，但下一增量转为**缩短** |
| **LL** | 已伸长，且下一增量**继续伸长** |
| **SL** | 已缩短，但下一增量转为**伸长** |

**地质意义**（Slide 23）——这是把抽象概念变成野外可观察证据的一步：

> 若岩石中侵入了不同方位的岩脉（veins），原则上，有些会被**褶皱（folded）**，有些会被**布丁化（boudinaged）**，有些会成为**布丁化的褶皱（boudinaged folds）**，有些会成为**褶皱化的布丁（folded boudins）**。

对应关系：LL → 布丁；SS → 褶皱；**SL → 褶皱化的布丁（先褶皱后拉断）；LS → 布丁化的褶皱（先拉断后褶皱）**。哪个方位的岩脉落入哪种情形，取决于有限应变椭圆与增量应变椭圆的几何关系——**因此仔细检查岩脉就能反推出应变路径（strain path）**。

**对称性判据（极重要的野外识别标志）**：

> **"Note the different symmetry of the predicted structures (orthorhombic for pure shear; monoclinic for simple shear)."**

即：**纯剪切下产生的构造组合具有斜方对称（orthorhombic symmetry）；简单剪切下具有单斜对称（monoclinic symmetry）**。这是野外区分共轴与非共轴变形最可操作的判据之一。

### 2.9 应变标志物与测量原理（Slides 25–31）

**总原则**（Slide 25）：

- 原则上，测应变要求确定应变张量的**全部 6 个独立分量**。若能**沿三个主应变方向测量**，任务大为简化——因为此时**剪应变全为零**，只需三个主应变的量值。
- 这要求我们理解**主应变方向与劈理（cleavage）、拉伸线理（stretching lineation）等组构的关系**。
- **大多数应变分析是在穿过应变椭球的平面切面上以二维方式做的，再把不同方位切面的结果组合成三维图像。**
- **野外操作要点（讲义特别强调）**：

  > "when measuring strain in the field it is **super-important** to measure the orientation of cleavage (strike/dip) and any stretching lineation (plunge/plunge direction) if present. These establish a reference frame within which your strain measurement results can be interpreted."

  即：**测应变时必须同时测劈理产状（走向/倾角）与拉伸线理产状（倾伏角/倾伏向）**，否则测出的数字无法解释。

**四类应变标志物（strain markers）**（Slide 25）：

1. 初始为**圆形**（三维为球形）的物体
2. 初始为**椭圆形**（三维为椭球形）的物体
3. **原始尺寸（长度）已知**的物体
4. 初始具有**双侧对称（bilateral symmetry）**的物体

#### (1) 圆形标志物（Slide 26）

**"their deformed shape is the actual shape of the strain ellipse"**——变形后的形状**就是**应变椭圆本身，因此是理想标志物。

讲义列出的实例：
- **泥岩与板岩中的还原斑（reduction spots）**
- **灰岩中的鲕粒（ooids）**
- **熔岩中的气孔（vesicles）**
- **凝灰岩中的火山砾（lapilli）**
- **层面上 Skolithos 潜穴（burrows）的截面**
- 另可近似当作等轴的：**枕状熔岩（pillow lavas）、柱状玄武岩的横截面、一系列化石**

📎 值得注意的学术争议（讲义 notes 提到）：北威尔士寒武纪板岩中的还原斑被 Tullis & Wood (1975) 用作应变标志物，但 Nakamura & Borradaile (2001) 主张这些还原斑**其实不是应变标志物**。这提醒我们：标志物的适用性本身是可以被质疑的。

📎 Skolithos 潜穴的额外用途：**因为它们变形前与层面的夹角约为 90°，所以在垂直层面的切面上观察时，它们还能提供角剪切信息（以层面作为剪切面）**。

#### (2) Fry 法（Slide 27）

适用条件：**岩石中的碎屑/颗粒初始为等轴（equidimensional）**。

> "the Fry method provides a rapid and very effective way of estimating the strain."

**简单图解形式的限制**：要求颗粒**不成簇（not clustered）**且**大小相近（all of similar size）**；计算机版本可放宽这些限制。也可用**单矿物岩中原本等轴的颗粒中心**。

#### (3) 椭圆形标志物与 Rf/φ′ 法（Slides 28–29）

原理：若岩石含初始为椭球形的物体，**可以把"初始椭率"与"变形施加的椭率"分离开来**，从而估算应变。经典实例是**变形砾岩（deformed conglomerate）中砾石形状的分析**。

**Rf/φ′ 法的理想条件**：
- 所有椭圆标志物具有**相同的初始椭率 R_i**；
- 它们长轴的**初始方位有显著变化（随机）**。

**方法逻辑**：给定应变 R_s 后，最终（实测）椭率 **R_f** 可以理论预测为初始方位 φ 的函数，因而也是最终方位 **φ′** 的函数。做法是**把实测 R_f 对 φ′ 作图，再与不同 R_i、R_s 的理论曲线比较**。

**术语约定**：所有 R 都是**长轴/短轴之比**。

📎 讲义 notes 的野外提示：砾岩中的砾石常有优选方位（如叠瓦构造 imbrication 造成的），但**通常仍有足够多方位异常的砾石**使该技术可用。

#### (4) 已知长度的标志物（Slide 30）

与前几类不同：这类标志物**通过脆性碎裂（brittle fragmentation）变形，碎块内部长度不变**。做法是**把感兴趣方向上各碎块的长度加起来求得 L₀，再与岩石上量得的变形后长度 L 比较**。

实例：
- **比基体强得多的线状标志物**：箭石（belemnites）、强矿物相的针状晶体（如石英中的金红石针）
- **易解体的线状标志物**：海百合茎（crinoid stems）
- **具特征尺寸的化石**：如某些未变形笔石（graptolites）胞管（thecae）的间距

⚠️ **重要陷阱（讲义 notes 明说）**：Slide 30 图中上面那枚箭石的碎块发生了转动，那是**刚体转动**，**"should not be used to infer angular shear"**（不可用来推断角剪切）。

#### (5) 双侧对称标志物（Slide 31）

许多化石具有**初始互相垂直**的特征（**"it may require imagination to identify these"**——需要想象力才能识别出来）。它们可用于确定**角剪切**。

> **"In principle, measurement of angular shear in two different directions is enough to establish the ratio of the principal strains."**（原则上，在两个不同方向上测出角剪切，就足以确定主应变之比。）

讲义实例：
- 三叶虫 *Bathyuriscus*（角剪切为**顺时针，即负值**）
- **Delabole butterfly**：康沃尔 Delabole 板岩中的腕足类 *Cyrtospirifer verneuili*，因形似蝴蝶而得名，多数已变形（角剪切亦为顺时针 = 负）
- **关键判据**：在变形后的腕足壳 A 与 B 中，**铰合线（hinge line）与对称面（plane of symmetry）在变形后仍然正交**，因此**A、B 中的这两条线必定平行于主应变方向**（因为主方向是唯一在变形前后都保持正交、且剪应变为零的方向组）。

#### (6) Mohr 圆构造（Slide 32）

> "Practical strain analysis using changes in line length and/or changes in angle is most conveniently carried out **graphically using the Mohr construction**."

原理：应变参数 **λ′ = 1/(1+e)²**（倒数二次伸长）与 **γ′ = γ/(1+e)²**（gamma prime）可以写成**圆的参数方程**形式。这个圆给出平面内与最大伸长方向 λ₁′ 成 φ′ 角的**任意线**的应变状态。

⚠️ **符号约定警告（讲义原文）**：**"Note that the clockwise up convention is relatively new – Ramsay and Huber use the opposite convention."**（顺时针向上的约定是较新的；Ramsay & Huber 用相反约定。）查阅老教材时务必注意。

W05 讨论应力时会以**更简单的形式**重访 Mohr 圆构造。

### 2.10 应变测量结果的解释（Slide 34）

讲义在这里给出了几条"批判性思维"要点，是简答题的好素材：

1. **测出的应变值反映的是"标志物"的应变状态**。若标志物与基质（host matrix）的**力学性质有差异**，解释结果时须小心。
2. 有些标志物与围岩力学性质**很接近**（如还原斑、火山砾）；有些则**差别很大**（如砾岩中的砾石）。后一种情形下，**分析劈理这类组构可以指示微观尺度上的应变变化**。
   - 讲义的两张对比照片：**多成分砾岩（polymict conglomerate）中劈理面不规则** → 指示局部应变变化；**火山砾凝灰岩（lapilli tuff）中无劈理折射** → 说明富火山砾层的应变与相邻凝灰岩相同。
   - 📎 火山砾小知识（讲义 notes）：lapilli 是凝灰质物质在同成分凝灰岩基质中形成的**原本球形**的团块，一般认为是雨滴穿过喷发火山灰云时围绕水滴形成的。**这正是它们能作为球形标志物的原因，也是 Practical Exercise 1 的材料。**
3. 在野外尺度上，**必须确定一次应变测量是具有区域意义，还是只与某个局部构造有关**。

### 2.11 组构与应变椭球形状：L/S/LS 构造岩（Slide 35）

在中—高级变质变形岩中，**组构（fabric）的性质提供了应变椭球几何形状最直观的印象**：

| 组构 | 名称 | 对应椭球 |
|---|---|---|
| **线状（linear）元素主导** | **L-tectonite（L 构造岩）** | **prolate 长棒形** |
| **面状（planar）元素主导** | **S-tectonite（S 构造岩）** | **oblate 扁圆形** |
| 既有强面理又有强线理 | **LS-tectonite** | 介于两者之间 |

讲义实例：美国新英格兰的变形砾岩（雪茄状砾石 = L 构造岩）；康沃尔 Tintagel 的压扁枕状熔岩（"S 构造岩"）。⚠️ 讲义自己加了限定：把压扁枕状熔岩叫 S 构造岩其实**有点勉强**——因为看不到第三维，而且组构尺度对于 "tectonite" 这个术语来说过大了。

### 2.12 劈理与应变椭球：劈理 = XY 面（Slide 36）

**核心命题**：**变形岩石中的劈理一般被认为代表应变椭球的 XY 面（主压扁面 principal flattening plane）**。

推论与限制：
- **Z 方向（XY 面的法线）上的缩短，可能被劈理面内的伸展补偿，也可能不被补偿——如果不被补偿，就意味着该方向存在体积损失（volume loss）**。
  - 📎 体积损失的机制：压溶（pressure solution）。
- 在剪切带内，**劈理跨越剪切带追踪 XY 面**（W04 内容）。
- ⚠️ **两个例外（易考）**：
  - 以**剪切带（shear bands）**形式形成的劈理**不直接对应应变椭球**；
  - **褶劈理（crenulation cleavage）**同样不对应——因为它形成于变形开始之后很久，**不代表岩石总应变的 XY 面**。

### 2.13 褶皱中的应变变化（Slides 37–39）

不同褶皱机制在**剖面面（profile plane）内**导致不同的应变变化型式。三种模型：

| 机制 | 英文 | 应变分布 |
|---|---|---|
| 切向纵向应变 | **Tangential Longitudinal Strain (TLS)** | **枢纽处应变最大，拐点处最小**；内弧收缩、外弧伸展，两者之间存在**零应变的中和面（neutral surface）** |
| 弯滑流 | **Flexural flow** | 与 TLS **相反**（枢纽最小，拐点最大） |
| 剪切褶皱 | **Shear folding** | 与 TLS **相反** |

📎 注意讲义的补充：TLS 与 flexural flow 是**平面应变模型**，其中 **Y 平行于褶皱枢纽，XZ 为剖面面**；但在**剪切褶皱中，Y 一般并不平行于枢纽，X 与 Z 一般也不在剖面面内**。

上述型式还会因下列因素变化：(a) 褶皱起始前的**层平行缩短（layer-parallel shortening）**量；(b) **后屈曲压扁（post-buckle flattening）**的性质。

**枢纽区的劈理型式**（Slide 38）：**中和点（neutral points，无劈理区）的出现，反映 XY 面局部方位的变化**。非能干层中位于中和点之下的层平行劈理，反映的是**下伏更能干层的外弧拉伸**（即 TLS 褶皱）。

**劈理折射与应变**（Slide 39）：劈理由能干层进入非能干层时会改变方位（**cleavage refraction，劈理折射**，W01 已提过）。这**反映了两层之间剪应变的差异，因而反映 XY 面局部方位的差异**。

> **关键结论**：**在两层的界面上，只要界面上没有滑动，两层共享同一个应变椭圆（"the strain ellipse is shared by the two layers"）。**

📎 这条"共享椭圆"性质可以在分析褶皱互层内部应变时发挥很大作用（讲义引 Hassani et al. 2004 对北威尔士 Anglesey 岛 Rhoscolyn 背斜的研究）。

### 2.14 区域应变的表达（Slides 40–44）

**应变椭圆图（strain ellipse maps）**是展示区域应变数据最直观的方式，尤其当应变椭球具有轴对称时效果好。讲义给的四类实例：

1. **岩基（plutons）**：津巴布韦 Chindamora 花岗岩基，由**捕虏体（xenoliths）形状**求得应变状态，用以推导岩体侵位时**气球式岩浆膨胀（balloon-like magmatic inflation）**模型。图上标注为 XZ = YZ 应变椭圆。
2. **褶皱（剖面上）**：瑞士 Valais 的 West Helvetic 推覆体叠置剖面面切面上的 XZ 应变椭圆。
3. **褶皱（区域剖面）**：澳大利亚中维多利亚剖面——注意 **Mount Useful 断层带内应变的强化**，以及**应变强度可由褶皱翼间角（interlimb angle）反映出来**。
4. **地表变形体**：
   - **冰川**：瑞士 Griesgletscher、斯瓦尔巴 Midre Lovénbreen（后者是数值模拟结果）
   - **蠕滑滑坡**：德比郡 Castleton 的 **Mam Tor 滑坡**（1996–2002 年地表应变；红线为应变椭圆轴，蓝线为**应变轨迹 strain trajectories**，即平行于主应变绘出的线）

📎 Mam Tor 是曼大 DEES（地球与环境科学系）长期监测项目（Ernie Rutter 主持）。讲义 notes 给出的数据：过去 200 年平均滑动速率 **26 cm/yr**；长期强降雨后（尤其冬季植被蒸腾排水能力弱时）有加速期；该滑坡相对不稳定的原因是**持续滑动阻止了树枝状水系的发育，因而无法排走地下水**。

📎 地表变形体的应变通常通过**测量一组标志点相对位置的变化**求得——如冰川上的测杆、蠕滑滑坡上的测站、跨板块区域的大地测量（GPS）站。

---

## 三、公式与图表

> **本节是本周笔记的重心。以下公式必须能默写，且必须分清彼此。**

### 3.1 线应变（Linear strain / longitudinal strain）的五种度量

尺寸变化可以描述为**沿一组参考方向测得的长度变化**；沿某给定方向的长度变化称为**线应变（linear strain，有时称 longitudinal strain）**。讲义 Slide 3 给出五个参数，"each of which has its own advantages in different applications"（各有各的适用场合）：

记 **L₀ = 起始长度，L = 变形后长度**。

| 参数 | 符号 | 公式 | 说明 |
|---|---|---|---|
| **工程应变 / 伸长率**<br>engineering strain (extension) | **e** | **e = ΔL / L₀ = (L − L₀) / L₀** | **可正可负**，取决于线段变长还是变短。未变形时 **e = 0** |
| **拉伸** | **s**（常写 **S**） | **s = L / L₀ = (1 + e)** | 未变形时 **s = 1**。**注意这与 e 差一个 1！** |
| **二次伸长**<br>quadratic elongation | **λ** | **λ = (L / L₀)² = (1 + e)²** | 未变形时 λ = 1 |
| **倒数二次伸长**<br>reciprocal quadratic elongation | **λ′** | **λ′ = 1 / λ = 1 / (1 + e)²** | Mohr 圆构造要用它 |
| **对数应变 / 自然应变**<br>logarithmic (natural) strain | **ε** | **ε = ln (L / L₀) = ln (1 + e)** | Hsü 图与对数 Flinn 图用它 |

**符号下标约定**：在坐标架中给出线应变时须加下标指明方向：**e_xx = 平行 x 轴的应变**，e_yy、e_zz 同理。**下标双写反映的是指定"一点处应变状态"所用的矩阵记号**。

**⚠️ 两套符号约定（极易考、极易错）**（Slide 3 notes）：

> - **工程学约定（engineering convention）**：**长度增加为正**。原因：工程中拉伸力的后果更相关（材料被拉时远比被压时弱）。
> - **岩石力学约定（rock mechanics convention）**：**长度减小为正**。原因：深部岩石因上覆岩石重量几乎总处于压缩状态，缩短更相关；这样定义只是为了让相关力学方程里不出现大量负号。
>
> **Slide 3 上的公式用的是工程学约定。**岩石力学约定下则是 e = (L₀ − L)/L₀，**"which is simply the negative of the engineering convention"**（就是工程学约定的相反数）。

**百分数表示**：常把应变乘以 100 写成百分数，例如**应变 0.001 = 0.1%**。

### 3.2 剪应变（Shear strain）

形状变化可以描述为**两条线之间夹角的变化**；夹角的变化称为**剪应变**。

| 参数 | 符号 | 公式 | 说明 |
|---|---|---|---|
| **角剪切**<br>angular shear | **ψ** | — | **两条原本互相垂直的线之间夹角的变化量** |
| **工程剪应变**<br>engineering shear strain | **γ** | **γ = tan ψ** | 由初等三角学直接得到：tan ψ = x/y = γ |
| **gamma prime** | **γ′** | **γ′ = γ / λ = γ / (1 + e)²** | Mohr 圆构造要用它 |
| **张量剪应变**<br>tensor shear strain | **e_ij** | **e_ij = γ_ij / 2（i ≠ j）** | **张量剪应变是工程剪应变的一半** |

**⚠️ 角剪切的符号约定（讲义说这是"现在的标准"）**：

> **逆时针旋转为正（+ve）；顺时针旋转为负（−ve）。**

判定方法：**考察剪切面的极（pole）如何旋转**。在二维图上，顺时针旋转为负。

📎 与右手定则的一致性（讲义 notes 的记忆法）：用右手，拇指沿 x 轴、食指沿 y 轴，则中指（z 轴）指向你；再让拇指沿 z 轴指向你，手指卷曲方向即逆时针——**逆时针为正**。

**剪应变的双下标**：需要两个下标分别指明 **(1) 剪切面的方位** 与 **(2) 该面内的剪切方向**。

### 3.3 应变椭球的三轴与体应变

| 量 | 公式 |
|---|---|
| 三个半轴量值 | **X = (1 + e₁)；Y = (1 + e₂)；Z = (1 + e₃)**，且 **X ≥ Y ≥ Z** |
| 主应变比 | **R_XY = (1 + e₁)/(1 + e₂)；R_XZ = (1 + e₁)/(1 + e₃)；R_YZ = (1 + e₂)/(1 + e₃)** |
| **体应变**<br>volumetric strain | **(V / V₀) = (1 + e_V) = (1 + e₁)(1 + e₂)(1 + e₃) = X · Y · Z** |

**体积不变（constant volume / isochoric）的判据**：**XYZ = 1**，即 (1+e₁)(1+e₂)(1+e₃) = 1，此时 e_V = 0。

**三个比值只有两个独立**（Practical Exercise 1 明确指出这一点）：

**R_XZ = R_XY × R_YZ**，因而 **R_YZ = R_XZ / R_XY**，其余同理。

> 验算：Exercise 1 中 R_XZ = 4.06，R_XY = 1.59，故 (R_YZ)_计算 = 4.06 / 1.59 = **2.55**——与练习答案给出的 2.55 完全一致 ✓

### 3.4 Hsü 图的两个参数

| 参数 | 公式 | 含义 |
|---|---|---|
| **应变量值** | **ε_S = 3^(−½) [ (ε₁ − ε₂)² + (ε₂ − ε₃)² + (ε₃ − ε₁)² ]^(½)** | ε₁、ε₂、ε₃ 为**对数主应变** |
| **Lode 参数** | **ν = (2ε₂ − ε₁ − ε₃) / (ε₁ − ε₃)** | 描述椭球形状 |

**用对数主应变差改写（Practical Exercise 1 第 4 步的思路，公式在 OCR 中丢失，以下为按讲义定义重建）**：

📎 背景补充（重建的推导链）：由 ε₁ = ln X、ε₂ = ln Y、ε₃ = ln Z 可得

- **ε₁ − ε₂ = ln R_XY**
- **ε₂ − ε₃ = ln R_YZ**
- **ε₁ − ε₃ = ln R_XZ**

代入即得可直接用平均长短轴比计算的形式：

- **ε_S = (1/√3) · [ (ln R_XY)² + (ln R_YZ)² + (ln R_XZ)² ]^(½)**
- **ν = ( ln R_YZ − ln R_XY ) / ( ln R_XZ )**

**ν 的取值与含义**：

| ν | 应变类型 |
|---|---|
| **ν = −1** | 轴对称伸展 = 纯**长棒（prolate / constriction）** |
| **−1 < ν < 0** | 偏长棒 |
| **ν = 0** | **平面应变（plane strain）** |
| **0 < ν < +1** | 偏扁圆 |
| **ν = +1** | 轴对称压缩 = 纯**扁圆（oblate / flattening）** |

📎 验证（用 ν = +1 的极端情形）：轴对称压扁时 ε₁ = ε₂，且体积不变要求 ε₃ = −2ε₁，代入得 ν = (2ε₁ − ε₁ + 2ε₁)/(ε₁ + 2ε₁) = 3ε₁/3ε₁ = **+1** ✓

### 3.5 Flinn 参数 k

⚠️ **讲义与练习均未给出 k 的公式**，只给出"画 R_XY 对 R_YZ、上方为 prolate、下方为 oblate"。下面的 k 定义是标准教科书内容：

📎 背景补充：设 **a = R_XY = X/Y**，**b = R_YZ = Y/Z**，则 **Flinn 参数**

> **k = (a − 1) / (b − 1)**

| k | 区域 | 应变椭球形状 |
|---|---|---|
| **k = 0** | 横轴（a = 1，即 X = Y） | **纯扁圆（uniaxial oblate）**，轴对称压扁 |
| **0 < k < 1** | 横轴与 45° 线之间（下方） | **扁圆域 / 压扁域（oblate / flattening field）** |
| **k = 1** | 45° 对角线 | **平面应变（无体积变化时）** |
| **1 < k < ∞** | 45° 线与纵轴之间（上方） | **长棒域 / 收缩域（prolate / constriction field）** |
| **k = ∞** | 纵轴（b = 1，即 Y = Z） | **纯长棒（uniaxial prolate）**，轴对称伸展 |
| **原点 (1, 1)** | — | **未变形（球）** |

📎 在**对数版本**（本课练习实际使用的版本）中，坐标是 ln R_XY 与 ln R_YZ，对应的形状参数为

> **K = ln R_XY / ln R_YZ**

分区规则完全相同（K = 1 为 45° 线；K > 1 长棒；K < 1 扁圆；原点 (0, 0) 为未变形）。对数版本的好处是**等量值的应变增量在图上表现为等长的位移**，并且**平面应变（无体积变化）严格落在 45° 直线上**。

📎 为什么无体积变化的平面应变正好是 45° 线：平面应变意味着 Y = 1（Y 方向无长度变化），体积不变意味着 XYZ = 1 ⇒ XZ = 1 ⇒ X = 1/Z。于是 a = X/Y = X，b = Y/Z = 1/Z = X，故 **a = b**，落在 45° 线上。✓

### 3.6 Mohr 应变圆的关键关系

- **λ′ = 1 / (1 + e)²**
- **γ′ = γ / (1 + e)² = γ / λ**
- 由上两式相除：**γ′ / λ′ = γ = tan ψ**

📎 **最后这条关系是 Exercise 2 第 3 步 (a) 的全部理由**：从**原点**到 Mohr 圆上代表某条线的点 P 的连线，其**斜率角就等于该线的角剪切 ψ**。所以只知道 ψ，就能画出一条必然经过 P 的射线，而不必事先知道 λ′、γ′ 的绝对数值。

📎 由圆心与半径给出的标准参数式：设 **c = (λ₁′ + λ₃′)/2**（圆心横坐标），**r = (λ₃′ − λ₁′)/2**（半径），则与最大伸长方向成 φ′ 角的线满足

> **λ′ = c − r·cos 2φ′**，**γ′ = r·sin 2φ′**

（因为 φ′ = 0 时 λ′ 取**最小值** λ₁′——λ′ 是 (1+e)² 的倒数，伸长越大 λ′ 越小。）

- **应变椭圆椭率**：**R_s = (1 + e₁)/(1 + e₃) = √(λ₃′ / λ₁′)**
- **由 λ′ 反求伸长**：**(1 + e) = 1/√(λ′)**

### 3.7 Rf/φ′ 法的三条公式

来自 Practical Exercise 4（公式本身在 OCR 中丢失，但数值答案完整，可反推确认）：

| 量 | 公式 | 本题数值验算 |
|---|---|---|
| **应变椭圆椭率** | **R_s = [ R_f,max × R_f,min ]^(½)** | √(6.00 × 1.60) = √9.60 = **3.098 ≈ 3.10** ✓ |
| **砾石初始椭率** | **R_i = [ R_f,max / R_f,min ]^(½)** | √(6.00 / 1.60) = √3.75 = **1.937 ≈ 1.94** ✓ |
| 反过来 | R_f,max = R_s × R_i；R_f,min = R_s / R_i | 3.10 × 1.94 = 6.01 ✓；3.10 / 1.94 = 1.60 ✓ |

（上述两式在 **R_s > R_i** 时成立，此时 R_f/φ′ 曲线是**闭合的泪滴形**。）

**三种平均值**（Exercise 4 第 8 步，用于快速近似 R_s）：

- **算术平均（arithmetic mean）** = (ΣR_f)/n
- **几何平均（geometric mean）** = (ΠR_f)^(1/n)
- **调和平均（harmonic mean）** = n / Σ(1/R_f)

**适用性判据（讲义原句）**：三者在 **高 R_i 或小 R_s** 时都不会与真实 R_s 很好吻合，但**当 R_s > 2 且 R_i < 2 同时成立时，调和平均通常是很好的近似**。

---

### 3.8 图件详解（必须能自己画出来）

#### 图 A：应变椭球的三轴与三种应变类型

画法：画一个椭球，三条互相垂直的半轴，从长到短标为 **X ≥ Y ≥ Z**。三种典型形状：

| 类型 | 形状 | 轴关系 | 手绘要领 |
|---|---|---|---|
| **长棒 prolate（雪茄）** | 一长两短且两短相等 | X ≫ Y = Z | 画成橄榄球/雪茄：一条轴很长，横截面接近圆 |
| **平面应变 plane strain** | 一长一短，中间轴不变 | X > Y = 1 > Z | 画成"椭圆柱"：Y 方向长度与原球半径相同 |
| **扁圆 oblate（薄饼）** | 两长一短且两长相等 | X = Y ≫ Z | 画成飞碟/煎饼：XY 面是圆，Z 方向被压扁 |

⚠️ **未变形状态是半径为 1 的球**——所有类型都由这个球变来。

#### 图 B：Flinn 图（本课使用的对数版本）

画法（严格按 Practical Exercise 1 给出的图）：

1. **横轴 = ln R_YZ**，向右为正；**纵轴 = ln R_XY**，向上为正。练习图上两轴刻度均为 **0, 0.2, 0.4, 0.6, 0.8, 1.0**。
2. **原点 (0, 0) = 未变形的球**（R_XY = R_YZ = 1，取对数为 0）。
3. **从原点画一条 45° 的对角线**，标注 **"Plane strain"（平面应变）**——即 K = 1 线。
4. **对角线之上（左上三角区）标 "prolate"**（长棒/收缩域，K > 1）。
5. **对角线之下（右下三角区）标 "oblate"**（扁圆/压扁域，K < 1）。
6. **纵轴本身**（ln R_YZ = 0，即 Y = Z）= 纯长棒线 K = ∞；**横轴本身**（ln R_XY = 0，即 X = Y）= 纯扁圆线 K = 0。
7. **应变量值大体随远离原点而增大**，但注意讲义警告：**该图不适合用来在不同区域之间比较应变量值**。

**Exercise 1 数据点的落位**（自行验算）：R_XY = 1.59 → ln = 0.464；R_YZ = 2.18 → ln = 0.779。故点画在 **(0.779, 0.464)**，明显**位于 45° 线之下**，落在 **oblate（扁圆）域**。K = 0.464/0.779 = **0.60**。

#### 图 C：Hsü 图

画法：一个**扇形（径向图）**，**顶点在下方 = 原点 = 未变形**。

1. **角坐标 = Lode 参数 ν**，从**中央竖直线 ν = 0（标注 "Plane strain"）**向两侧展开；练习图上的刻度为 **0、±0.5、±1.0**。
2. **左侧（负 ν）标 "prolate"，右侧（正 ν）标 "oblate"**。（练习图上的标注顺序即 "prolate | oblate"。）
3. **径向坐标 = 应变量值 ε_S**，练习图上以同心弧标出 **0.25, 0.50, 0.75, 1.00, 1.25, 1.50**，**离原点越远应变越大**。
4. 与 Flinn 图的分工：**Flinn 图看形状好、看量值差；Hsü 图能同时看形状（ν）与量值（ε_S）**。

**Exercise 1 数据点的落位**（自行验算，📎 因为练习答案里的数字未被 OCR 提取出来）：
- 若用**自洽**的一组比值（R_XY = 1.59、R_YZ = 2.18、R_XZ = 1.59×2.18 = 3.47）：**ε_S = 0.888，ν = +0.254**
- 若用**实测**的 R_XZ = 4.06：**ε_S = 0.964，ν = +0.225**
- 两种算法都给出 **ν > 0 → oblate（扁圆）域**，与 Flinn 图结论一致 ✓——这正是练习第 4 步要求"confirm"的那件事。

#### 图 D：纯剪切与简单剪切下主轴的旋转行为（本周最核心的一张概念图）

**这是共轴/非共轴最本质的区别，务必能画。**

**画法（左右并排两栏，每栏画三个阶段：未变形 → 中期 → 晚期）**

**左栏：纯剪切（pure shear，共轴、非旋转）**
1. 第一格画一个**正方形**，内含一个**圆**，并在圆上标出水平与竖直两条直径。
2. 第二格：正方形变成**水平变长、竖直变短的矩形**（面积不变）；圆变成椭圆，**长轴仍水平、短轴仍竖直**。
3. 第三格：矩形更扁更长，椭圆更扁更长，**长短轴方位与第二格完全相同**。
4. **结论标注**：**有限应变椭圆的主轴方位始终不变** → **共轴（coaxial）、非旋转（irrotational）**。增量应变椭圆的主轴与有限应变椭圆的主轴**始终平行**。
5. **对称性**：产生的构造组合具有**斜方对称（orthorhombic）**——即存在两个互相垂直的对称面。

**右栏：简单剪切（simple shear，非共轴、旋转）**
1. 第一格画一个**正方形**，内含一个**圆**。
2. 第二格：正方形变成**平行四边形**（顶边相对底边侧向滑移，高度不变）；圆变成椭圆，其**长轴与剪切面成较大锐角**（初始瞬时为 45°）。
3. 第三格：平行四边形更倾斜；椭圆更扁，且**长轴向剪切面方向明显旋转靠拢**（角度变小，趋近但不到 0°）。
4. **结论标注**：**有限应变椭圆的主轴随递进变形不断向剪切方向旋转** → **非共轴（non-coaxial）、旋转（rotational）**。**增量应变椭圆保持不变**（永远保持 45° 那个方位），因而有限主轴与增量主轴**不平行**。
5. **大应变时的极限**（Slide 17）：**X 平行于剪切方向，Z 垂直于剪切面，Y 位于剪切面内且长度不变** → 这是**平面应变**。
6. **对称性**：产生的构造组合具有**单斜对称（monoclinic）**——只有一个对称面，因而**可以判断剪切指向（shear sense）**。

**一句话记忆**：**纯剪切——主轴钉死不动；简单剪切——主轴不停朝剪切方向倒。**

#### 图 E：递进变形的四象限 / 八扇区图

画法：
1. 画一个**有限应变椭圆**，在其上画出**两条"无有限纵向应变线"**（它们过椭圆中心，把椭圆分成四个象限）。**含长轴的一对象限内线段被伸长（L）**，**含短轴的一对象限内线段被缩短（S）**。
2. 在同一中心叠加**增量应变椭圆**，它的方位与有限应变椭圆**不同**（简单剪切时必然不同），同样带两条无增量纵向应变线。
3. 两组线共四条，把圆周分成**八个扇区**，逐扇区标注 **LL / LS / SL / SS** 四种组合（对角扇区标注相同）。
4. 地质解读标注：**LL → 布丁化（boudinage）；SS → 褶皱（folding）；SL → 褶皱化的布丁（folded boudins）；LS → 布丁化的褶皱（boudinaged folds）**。

#### 图 F：Mohr 应变圆的读法

画法：
1. **横轴 = λ′（倒数二次伸长）**，**纵轴 = γ′（gamma prime）**。
2. **符号约定：顺时针（−ve）角剪切向上，逆时针（+ve）角剪切向下**（讲义 Slide 32 的 "clockwise (−ve) up" 约定）。
3. 圆与 λ′ 轴的两个交点是 **λ₁′（左，较小）** 与 **λ₃′（右，较大）**。**注意方向感是"反的"**：λ₁′ 对应**最大伸长**方向，但因为 λ′ = 1/(1+e)²，所以它是**较小**的横坐标。
4. **点 P 代表平面内某条线**：从圆心出发、与 λ′ 轴成 **2φ′** 角（自 λ₁′ 一端量起）的半径与圆的交点即 P。φ′ 是该线与最大伸长方向的夹角。
5. **读数**：P 的横坐标 = 该线的 λ′（据此可算 1+e = 1/√λ′）；P 的纵坐标 = 该线的 γ′；**从原点到 P 的连线与 λ′ 轴的夹角 = 角剪切 ψ**。
6. 圆上还标出 **(1 + e₁) = (1/λ₁′)^½** 与 **(1 + e₃) = (1/λ₃′)^½**。

#### 图 G：Rf/φ′ 图的读法

画法：
1. **横轴 = φ′**（长轴相对参考方向的角度，练习中刻度自 +10° 向 −40°），**纵轴 = R_f**（长/短轴比，刻度 1 到 6）。
2. **每个砾石画一个点 (φ′, R_f)**。
3. 所有点落在一条**闭合的、泪滴形（tear-drop shaped）曲线**上，且**关于某个 φ′ 值对称**。
4. **该对称轴所在的 φ′ 值 = 最大伸长方向**（本题为 **φ′ = −15°**）。据此把横轴**重新标注为 φ′′**（自最大伸长方向量起的角度），本题重标后刻度为 +15、+5、−5、−15。
5. 在**重标后的 φ′′ = 0 这条竖线上**读出 **R_f,max（曲线顶点，本题 6.00）** 与 **R_f,min（曲线底点，本题 1.60）**。
6. 曲线的**最大宽度**称为**涨落（fluctuation, F）**，本题实测 **F = 36°**。
7. 用 R_s、R_i 代入理论公式画出理论曲线叠加对比。

#### 图 H：Fry 图的读法

画法（见 Practical Exercise 3 的操作步骤，见第五节）：最终成图是**一张布满点的图，中央出现一个椭圆形的"点空缺区（elliptical point vacancy）"**。

> **这个椭圆空缺区的长短轴比与方位，就是应变椭圆的长短轴比与方位。**

读法：目测确定空缺椭圆的长轴与短轴，计算 **R_s = (1 + e₁)/(1 + e₃)**，并量出**长轴与水平方向的夹角**。

---

## 四、课堂补充

> **⚠️ 说明：本课（EART28202 Structural Geology）全 10 周的教学材料中均无 transcript（课堂录音转录）。本段内容全部来自讲义 notes pane 的强调语句与练习答案透露的评分/作图要点，不是课堂口头补充。**

事实上，本课的教学方式使 transcript 的缺失影响较小——大纲 Teaching and learning methods 明确说：

> "The Theory content will be posted as PowerPoint presentations on Blackboard. These will be augmented with extra notes (comments/further reading) in the notes pane to each slide … **Students will be expected to learn the lecture material primarily by reading this material on Blackboard.**"

也就是说，**notes pane 就是"课堂讲解"本身**。以下把散落在 notes pane 与练习答案中的"教师强调"集中列出。

### 4.1 教师明确划定的考试范围（最重要）

1. **Slides 8–13（应变的数学理论）只需带走两条结论**（原文见 §2.3）：应变状态是 9 项矩阵、6 项独立；对角线是线应变，非对角线是张量剪应变。**矩阵代数不考。**
2. **`StrainNote.pdf` 明确不考**："You do NOT need to know the contents of this document for this course unit."
3. **大纲原话**："this is a road map of the subject – different students will focus on different aspects. **Assessment, however, focuses on key material (highlighted within each lecture)** that any Earth scientist with interests in geology should be familiar with."——讲义故意超载，考的是每讲中被高亮的核心。
4. **每周 Blackboard 上会另发一份短文档，指出该周 Theory 的关键材料以及可能的考法**（大纲 Teaching and learning methods）。本仓库材料中未见该文档。

### 4.2 教师反复强调的注意事项

1. **"principal" 的拼写**（Slide 14 notes 专门写了一句）。
2. **野外测应变必须同时测劈理产状与拉伸线理产状**（Slide 25 notes 用了 "super-important" 这个词）。
3. **两套符号约定必须说清楚用的是哪一套**：工程学（伸长为正）vs 岩石力学（缩短为正）（Slide 3 notes）。
4. **Mohr 圆的角剪切符号约定有新旧两套**："the clockwise up convention is relatively new – Ramsay and Huber use the opposite convention"（Slide 32）。**查旧书时会自相矛盾。**
5. **刚体转动不可用来推断角剪切**（Slide 30 notes 关于箭石碎块的警告）。
6. **褶劈理与剪切带型劈理不代表应变椭球 XY 面**（Slide 36）。
7. **应变结果是"标志物的应变"，不一定等于岩石整体的应变**（Slide 34）——标志物与基质流变性质差异是必须讨论的因素。
8. **教师本人的坦诚限定**：Slide 35 中把压扁枕状熔岩称为 S-tectonite "is actually pushing the point"（其实有点勉强）。这类自我限定往往是简答题里可以拿分的"批判性评论"。

### 4.3 练习答案透露的评分要点与作图规范

从 `2-CoverAns.md` 的答案措辞可以反推出评分偏好：

1. **不满足于给出数字，必须讨论数字的可靠性。** Exercise 1 第 5 步的标准答案是本周最典型的示范——它没有停在"2.18 vs 2.55 有差异"，而是给了**三层递进的讨论**：
   - **可能原因**：切面不完全平行于三个主应变面；和/或火山砾并非初始完美球形，而是方位各异的椭球；
   - **改进办法**：分析更多火山砾；更有效地使用统计量（例如**若有极端异常形状的火山砾把长短轴比的频率分布拉偏，则用众数 mode 可能优于均值 mean**）；
   - **检验办法**：**看长短轴比频率分布的形状**，或**对每组数据画长轴对短轴的散点图、看数据相对线性拟合的离散程度**；
   - **结论句**：**"In advance of doing this, the ellipticity of the strain ellipsoid is not reliably evaluated."**（在做这些之前，应变椭球的椭率无法可靠评估。）
   
   👉 **这个"数字 → 误差来源 → 改进方案 → 结论"的四段式，是本课简答题的标准答题模板。**

2. **测量要覆盖不同尺寸。** Exercise 1 第 1 步要求"**Select ellipses with a range of different sizes**"（选取一系列不同大小的椭圆），而不是只挑大的或好量的——这是防止系统偏差。

3. **数量要求明确**：每张照片量 **10 个椭圆**。

4. **量长度的具体规范**（Exercise 2 第 1 步的括号提示，是典型的"细节分"）：
   > "it is best to **measure the final length of the crinoid stem from the middle of the first ossicle to the middle of the last**, and in calculating the original length, to **use only the half lengths of the first and last ossicle together with the lengths of the five intervening ossicles**"
   
   即：**变形后长度从第一枚骨板中点量到最后一枚骨板中点；原始长度只算首尾骨板的一半长度加上中间五枚骨板的完整长度。**——首尾各取一半，保证 L 与 L₀ 量的是同一段材料。

5. **角度必须带符号并注明旋向**。答案里写的是 "**+ 53° (anticlockwise rotation)**" 和 "**+ 9° (anticlockwise rotation)**"——**不是只写 53°**。

6. **有效数字**：答案统一给到**三位小数或三位有效数字**（1.478、6.139、0.163、1.327、0.216、3.10、1.94、3.76、3.42、3.08）。

7. **作图的收尾步骤不可省**：Exercise 2 最后一步是 "**Draw a strain ellipse to scale and in the proper orientation on the diagram that shows the fossils**"——**按比例、按正确方位**把应变椭圆画回化石图上。这一步是把计算结果"落回岩石"的检查。

8. **理论曲线与数据不符时要给地质解释而非硬拟合**：Exercise 4 第 7 步的答案指出，实测涨落（F = 36°）比理论曲线**略宽**，这**"suggests that there is a small component of pebble rotation in addition to that produced by the pebble shape change"**——可能是**砾石之间相互接触**，或**基质与砾石的流变（flow）性质显著不同**所致。

---

## 五、Practical 要点

**本周 Practical 主题：Finite strain measurement techniques（有限应变测量技术）**，共四道练习，文件 `2-CoverAns.md` 是**题目 + 答案合一**的版本。

练习开篇的总说明：

> "The first focuses on **recovering the 3d state of strain from measurements of 2d strain on three differently oriented planes**; the other three explore **widely used techniques to determine 2d strain**."

即：**Exercise 1 = 由三个不同方位平面的二维应变恢复三维应变状态；Exercise 2–4 = 三种常用的二维应变测定技术。**

---

### 5.1 Exercise 1：三维应变状态的 Flinn 图与 Hsü 图表示

**题目**：图 1 是取自 Coniston 附近一套**变形奥陶纪凝灰岩**的**三个正交切面**上**变形火山砾（lapilli）**的照片。假定这三个切面对应应变的三个主平面，且火山砾**原本为球形**，请把应变状态 (a) 表示在 Flinn 图上，(b) 表示在 Hsü 图上。

**给出的关键概念**：三维表示所需的关键参数是**应变椭球三个主平面（XY、XZ、YZ 面）上应变椭圆的椭率**；且**知道其中任意两个，第三个即可推出**（R_XZ = R_XY × R_YZ）。

**解法步骤**：

1. **在每张照片上量 10 个椭圆的长轴与短轴**（**要选取大小不同的一系列椭圆**），算出每个椭圆的长短轴比（aspect ratio）。
2. **对每张照片求平均长短轴比**。判定三张照片分别是哪个主平面。
   - **标准答案**：**Top（上）= XZ 面，X 水平；Middle（中）= YZ 面，Y 水平；Bottom（下）= XY 面，X 水平。**
3. 取相关两个平面平均长短轴比的**自然对数**，画在 Flinn 图上；判断椭球落在长棒域还是扁圆域。
4. Hsü 图用**对数应变**画。用 §3.4 的换算关系把平均长短轴比转成 ε_S 与 ν，画在 Hsü 图上，**确认与 Flinn 图给出的（扁圆/长棒）判断一致**。
5. **把实测的 R_YZ 与由 R_XZ、R_XY 计算出的 R_YZ 相比较，讨论其含义。**

**数据与答案**：

| 量 | 值 |
|---|---|
| R_XZ（实测） | **4.06** |
| R_YZ（实测） | **2.18** |
| R_XY（实测） | **1.59** |
| R_YZ（由 4.06 / 1.59 计算） | **2.55** |

**第 5 步标准答案（全文要点）**：

> 两者的差异意味着：**要么切面并非完美平行于应变的三个主平面**，**和/或火山砾并非全都初始完美球形，而实际上是方位各异的椭球**。这个问题也许可以通过**分析更多火山砾**或**更有效地使用统计方法**来消除（例如，若有一些形状极端异常的火山砾把长短轴比的频率分布拉偏了，也许**用众数而非均值**会更好）。这一统计问题的性质可以通过**考察长短轴比频率分布的形状**、或**对每组数据画长轴对短轴的散点图并观察数据相对线性拟合的离散程度**来检验。**在做这些之前，应变椭球的椭率无法可靠评估。**

**自行验算（📎 以下数值为笔者据练习数据计算，练习答案文件中的对应数字未被 OCR 提取出来）**：

- ln R_XY = ln 1.59 = **0.464**；ln R_YZ = ln 2.18 = **0.779**；ln R_XZ = ln 4.06 = **1.401**
- Flinn 图上点位 **(0.779, 0.464)**，位于 45° 线**下方** → **oblate（扁圆）域**；K = 0.464/0.779 = **0.60**
- Hsü 参数（用自洽的 R_XZ = 3.47）：**ε_S = 0.888，ν = +0.254 → 扁圆侧** ✓ 与 Flinn 图一致
- Hsü 参数（用实测 R_XZ = 4.06）：**ε_S = 0.964，ν = +0.225 → 仍在扁圆侧** ✓

📎 **结论**：无论用哪套数字，都落在扁圆域，与"压扁型变形"的解读一致。这也说明**练习第 4 步要求的"confirm"在本题是成立的**——两张图给出同一个形状判断。

**配套文件 `Fig1soln.md`（图 1 的切面判定答案，77 词）**：

该文件给出三个照片 A、B、C 的判定逻辑（对应 `2-CoverAns.md` 中的 Top / Middle / Bottom）：

> - **A**：X 或 Y 水平；Y 或 Z 竖直
> - **B**：X 或 Y 水平；Y 或 Z 竖直 **⟹ 因此 Z 竖直，且 C 是 XY 面**
> - **C**：XY 面 **⟹ 因此 X 水平、Y 竖直，且 A 是 XZ 面、B 是 YZ 面**

即最终判定 **A = XZ 面，B = YZ 面，C = XY 面**，与 `2-CoverAns.md` 的 "Top: XZ; Middle: YZ; Bottom: XY" 一致（A/B/C 对应上/中/下）。

📎 背景补充：上述推理链在 OCR 后读起来略显循环，**更直接的判定法是按长短轴比排序**：由于 **X ≥ Y ≥ Z**，必然有 **R_XZ ≥ R_YZ ≥ R_XY**（本题 4.06 > 2.18 > 1.59）。所以：
- **长短轴比最大的切面 = XZ 面**（含最长与最短轴）
- **长短轴比最小的切面 = XY 面**（含最长与中间轴）
- **剩下的 = YZ 面**

再结合"三个正交切面必须共享公共轴向"的一致性检查（两张切面的竖直方向若相同，则该方向就是它们共有的那个主轴），即可完成判定。

---

### 5.2 Exercise 2：用 Mohr 圆做二维应变分析

**先说 Mohr 圆的四类可解情形**（练习列出，均给了 Ragan 书中的对应例题页码）。记 **e₁ 为该平面内最大伸长方向**：

| 情形 | 已知条件 | 可解出 | Ragan 页码 |
|---|---|---|---|
| **(a)** | 某方向的**角剪切 ψ** + **该方向与 e₁ 的夹角 φ′** | 比值 **(λ₁′/λ₃′)**；若再补充**某已知（与 e₁ 成已知角）方向上的长度变化**，则可求出 **λ₁′ 与 λ₃′ 的实际值**及平面上的完整应变 | p.316–317 |
| **(b)** | **两个不同方向上的 ψ** + 两方向间的夹角 | 比值 **(λ₁′/λ₃′)** 与 **e₁ 的方位**；补充一个长度变化后可求全部 | p.318–319 |
| **(c)** | **两个不同方向上的长度变化** + 各自与 e₁ 的夹角 | 平面上的**完整应变** | p.325–326 |
| **(d)** | **三个不同方向上的长度变化** | **e₁ 的方位**与平面上的完整应变 | p.327–328 |

📎 记忆要点：**"只知角剪切/长度变化的比例关系 → 只能定比值；补一个绝对的长度变化 → 才能定绝对值。"** 因为 Mohr 圆的位置可以整体缩放（练习中的"未知常数 c"就是这个缩放因子）。

**本题设定**：一块变形灰岩，含一枚**被拉伸的海百合茎（crinoid stem）**和一枚**变形的腕足类（brachiopod）**。海百合茎的骨板（ossicles）之间充填**方解石纤维**；腕足类原本具有**放射状对称的肋纹（rib pattern）**。

给出的量测值：
- **L₀ = 45 mm，L = 111.5 mm**（沿腕足类铰合线方向的海百合茎）
- **ψ = +53°**（原正交于铰合线的一条线的重新定向量，逆时针）
- **φ′ = +9°**（自最大伸长方向到腕足类铰合线的角度，逆时针）

**第 1 题：计算铰合线方向上的各应变参数**（答案表）

| 参数 | 计算 | 答案 |
|---|---|---|
| **e** | (111.5 − 45) / 45 | **1.478** |
| **λ** | (1 + e)² | **6.139** |
| **λ′** | 1 / λ | **0.163** |
| **ψ** | — | **+ 53°（逆时针旋转）** |
| **γ** | tan ψ | **1.327** |
| **γ′** | γ / λ | **0.216** |

**逐项复算验证** ✓：
- e = 66.5 / 45 = 1.4778 → **1.478** ✓
- λ = 2.4778² = 6.1394 → **6.139** ✓
- λ′ = 1/6.139 = 0.16289 → **0.163** ✓
- γ = tan 53° = 1.32704 → **1.327** ✓
- γ′ = 1.327/6.139 = 0.21616 → **0.216** ✓

**第 2 题**：海百合骨板之间的晶体纤维可能沿最大伸长方向排列。**要求用腕足类的肋纹型式来支持这个想法**（因为肋纹原本放射对称，变形后的对称轴指示主应变方向），画出最大伸长方向，并确定自最大伸长方向到铰合线的角度：

> **φ′ = + 9°（逆时针旋转）**

**第 3 题：Mohr 圆作图（五步 + 一步落图）**

| 步骤 | 操作 |
|---|---|
| **(a)** | 在一套 **λ′–γ′ 坐标**上，过**原点**画一条**斜率角为 ψ** 的直线。⚠️ **注意遵守"负角剪切向上斜 / 正角剪切向下斜"的约定**（本题 ψ = +53° 为正，故该线**向下斜**） |
| **(b)** | 在该线上任取一个方便的距离取点 **R**；过 R 作一条与该线成 **φ′** 角的直线（图中为虚线）。这条线与 **λ′ 轴的交点** 即为 **c·λ₁′**（λ₁′ 乘以一个未知常数 c） |
| **(c)** | 从 **R 与 cλ₁′ 的中点**出发，作一条**垂直于这条新线**的直线；它与 **λ′ 轴的交点即 Mohr 圆的圆心** |
| **(d)** | 计算比值 **R_s** |
| **(e)** | 自圆心作一条与 λ′ 轴成 **2φ′** 角的半径（**自 cλ₁′ 一侧量起**）；它与圆的交点即 **P**，**P 处的 λ′ 就是第 1 题算出的那个值（0.163）**。由此定出常数 c，从而得到**各应变的实际值** |
| **(f)** | **按比例、按正确方位**把应变椭圆画到显示化石的那张图上 |

**答案（图上标注）**：

| 量 | 值 |
|---|---|
| **λ₁′** | **0.130** |
| **λ₃′** | **1.537** |
| **(1 + e₁)** | **2.77** |
| **(1 + e₃)** | **0.81** |
| **R_s** | **3.42** |
| 圆上 P 点 | λ′ = 0.163，2φ′ = 18°（φ′ = +9°），ψ = +53° |

**逐项复算验证** ✓：
- (1 + e₁) = (1/λ₁′)^½ = (1/0.130)^½ = √7.692 = 2.7735 → **2.77** ✓
- (1 + e₃) = (1/λ₃′)^½ = (1/1.537)^½ = √0.6506 = 0.8066 → **0.81** ✓
- R_s = 2.77 / 0.81 = **3.42** ✓（亦等于 √(1.537/0.130) = √11.82 = 3.44，与 3.42 一致）
- **自洽性检查**：圆心 c = (0.130 + 1.537)/2 = 0.8335，半径 r = (1.537 − 0.130)/2 = 0.7035。
  - λ′(φ′ = 9°) = 0.8335 − 0.7035·cos 18° = 0.8335 − 0.6691 = **0.1644**，与第 1 题的 **0.163** 吻合 ✓
  - γ′(φ′ = 9°) = 0.7035·sin 18° = **0.2174**，与第 1 题的 **0.216** 吻合 ✓
  - **γ′/λ′ = 0.216/0.163 = 1.325 ≈ tan 53° = 1.327** ✓（即 §3.6 的关系成立）

📎 背景补充（材料未讨论的一点）：本题结果给出 **(1 + e₁)(1 + e₃) = 2.77 × 0.81 = 2.24 ≠ 1**，即**该切面上面积并不守恒（面积增大约 124%）**。材料对此未作说明。可能的解释包括：该切面并非应变椭球的主平面、存在体积变化、或这只是为练习设计的人造数据。**答题时若被问到"体积/面积是否守恒"，应当据 (1+e₁)(1+e₂)(1+e₃) = V/V₀ 直接计算并如实报告，而不要默认体积不变。**

**为什么 (d) 排在 (e) 之前？** 📎 因为 **R_s = √(λ₃′/λ₁′)** 是**比值**，与未知缩放常数 c 无关（c 在分子分母中约掉），所以在定标之前就能算；而 λ₁′、λ₃′ 的**绝对值**必须靠第 1 题算出的 λ′ = 0.163 来定标。

---

### 5.3 Exercise 3：Fry 法

**题目**：把 Fry 法应用到**图 2 的鲕状铁矿（oolitic ironstone）**上，估算**薄片平面上应变椭圆的椭率与方位**。

**方法（五步，可照做）**：

1. 在一张**描图纸**上标出**所有鲕粒的中心点**，并**编号**。
   - **提示**：**先给图像中央的鲕粒编号，再向外扩展**，这样做得更快。
2. 在**另一张描图纸**上标一个**中央参考点**。把这张纸放到**第 1 号鲕粒**上，把**其余所有鲕粒的中心**描到这张覆盖层上。
3. **不旋转地**移动覆盖层，使参考点落到**第 2 号鲕粒**上，再把其余所有鲕粒中心描上去。
4. **对所有其余鲕粒重复第 3 步。**
   - 做过几个鲕粒之后，**参考点周围就会出现一个椭圆形的点空缺区（elliptical point vacancy）**。
   - **一旦空缺区出现，若想加快速度，远离该空缺区的颗粒中心就不必再标了。**
5. **这个椭圆形空缺区的长短轴比与方位，就是应变椭圆的长短轴比与方位。**目测确定其长轴与短轴，计算 **R_s = (1 + e₁)/(1 + e₃)**，并**量出长轴与水平方向的夹角**。

**方法的限制与推广**：
- 本练习使用的 Fry 法要求所测物体**大小大致相同**且**充分分散（不成簇）**。
- 对**大小不一**的初始等轴物体，方法易于修改（Erslev, 1988, *JSG* 10: 201–209）。
- 拟合椭圆的**形式化策略**也已被开发（Erslev & Ge, 1990, *JSG* 12: 1047–1059）。

**⚠️ 本练习的答案文件 `4-Ex3sol2.md`（29 词）无可用信息。** 该文件在仓库中的全部正文是 OCR 从图片识别出的乱码（如 "o%s, °°"、"ese sts"、"© @sloJexy"），文件自身的说明已标注：**"识别质量低——原件疑为手写或图件，文字大多不可靠"**。原件应是 Fry 法的**图解答案**（点阵图），无法从 md 版本中读出任何数值或结论。**因此本练习没有可供核对的 R_s 与角度答案；复习时只能掌握操作步骤本身。**

---

### 5.4 Exercise 4：Rf/φ′ 法

**题目**：把 Rf/φ′ 法应用到一组**人造的变形椭圆砾石**上，以演示该技术。（该方法广泛用于分析**初始为椭圆形的标志物**，如砾岩中的砾石。）

**方法（八步，可照做）**：

1. 椭圆砾石图下方画有一条**水平线作为任意参考方向**，用于量测椭圆长轴的方位。**量出每个砾石长轴与参考方向的夹角 φ′**，**注意符号约定：顺时针为负，逆时针为正**。
2. **量每个砾石的长轴与短轴，求长短轴比 R_f（长轴 ÷ 短轴）**。
3. 把每一对 (φ′, R_f) 作为一个点画在图上。
4. 这些点落在一条**闭合的、泪滴形曲线**上，**关于某个 φ′ 值对称**。**该 φ′ 值就是最大伸长方向。**在参考方向旁边画出这个最大伸长方向的线。然后把图上的横轴**重新标注**，改为读**自最大伸长方向量到给定椭圆长轴的角度**（沿用同一符号约定）。
5. **R_f 的最大值与最小值落在重标后角度 = 0 的线上。**读出这两个值。
6. 用公式计算**应变椭圆椭率 R_s** 与**砾石初始椭率 R_i**。
7. 用第 6 步算得的 R_i、R_s 代入理论公式画出理论曲线。
8. 计算 R_f 数据的**算术平均、几何平均、调和平均**三种平均值，作为 R_s 的快速近似。

**数据（图中标注的 18 个砾石，格式为 R_f / φ′）**：

5.14、1.67、5.40 (−22°)、(−30°) 4.47 (−3°)、(−20°) 5.56 (−9°)、2.00 (+3°)、3.78 (−28°)、2.88、4.83 (−6°)、(−31°) 4.75 (−21°)、2.20、5.43 (−20°)、1.56 (−34°)、1.7 (−17°)、(0°) 5.90 (−12°)、2.75 (+1°)、4.27 (−26°)、3.33 (−1°)

（📎 注意：OCR 把数值与角度的配对关系打乱了，**R_f 数值本身可靠（共 18 个），但"哪个 R_f 配哪个 φ′"不可靠**。所幸第 8 步只需要 R_f 的集合，故三种平均值可以复算。）

**答案**：

| 量 | 值 |
|---|---|
| **R_f,max** | **6.00** |
| **R_f,min** | **1.60** |
| **R_s = [R_f,max × R_f,min]^½** | **3.10** |
| **R_i = [R_f,max / R_f,min]^½** | **1.94** |
| **涨落 F（曲线最大宽度）** | **36°** |
| **最大伸长方向** | **φ′ = −15°** |
| **算术平均** | **3.76** |
| **几何平均** | **3.42** |
| **调和平均** | **3.08** |

**逐项复算验证** ✓：
- R_s = √(6.00 × 1.60) = √9.60 = 3.098 → **3.10** ✓
- R_i = √(6.00 / 1.60) = √3.75 = 1.937 → **1.94** ✓
- 反算：R_s × R_i = 6.01 ≈ R_f,max ✓；R_s / R_i = 1.598 ≈ R_f,min ✓
- 用上列 18 个 R_f 值：**算术平均 = 3.757 → 3.76** ✓；**几何平均 = 3.425 → 3.42** ✓；**调和平均 = 3.078 → 3.08** ✓
- 适用性判据核对：**R_s = 3.10 > 2** 且 **R_i = 1.94 < 2**，两条件均满足，故**调和平均（3.08）应当是 R_s（3.10）的好近似**——实测差异仅 0.02，完全符合 ✓；而算术平均 3.76 明显偏高。

**第 7 步的讨论（重要的地质解释）**：

> 用第 6 步的 R_i、R_s 代入理论公式画出的泪滴形曲线**比数据略窄**。曲线的最大宽度称为**涨落（fluctuation, F）**。**数据的涨落略大于理论值这一事实，表明除了砾石形状改变所产生的转动之外，还存在一小部分砾石转动。**这可能是由于**砾石之间发生了接触**，或**基质与砾石具有显著不同的流变（flow）性质**所致。

📎 **笔者的数值验证**：以 R_i = 1.94、R_s = 3.10 做纯剪切正演（对初始椭率 1.94、初始方位遍历 0°–180° 的椭圆施加椭率为 3.10 的应变，计算最终长轴方位的极值），得到**理论 |φ′|_max ≈ 15.4°，即理论 F ≈ 31°**。这与实测 **F = 36°** 相比确实**偏窄约 5°**，**与练习答案"a little too narrow"的判断完全吻合** ✓。另可注意实测角度数据的范围是 +3° 到 −34°，关于 −15° 对称的话就是 −15° ± 18.5°，正对应 F ≈ 36–37° ✓。

**方法的前提条件与现实困难**：
- **要求所有被测物体具有相同的初始椭率**，且**这些椭圆物体长轴的初始方位是随机的**。
- **现实中这两个条件通常有一个或两个都不满足**，使方法的应用复杂化。
- 尽管如此，已发展出使该方法非常强大的分析策略（Lisle, 1985, *Geological Strain Analysis: A Manual for the Rf/φ Technique*, Pergamon Press）。

---

### 5.5 `Logs.md`：对数复习（340 词）

这是一份**数学预备材料**，因为 Flinn 图与 Hsü 图都要用自然对数。要点：

- **定义**：x 在以 b 为底的对数，是使 **x = bⁿ** 成立的那个数 n。例：log₃(81) = 4，因为 3⁴ = 81；log₁₀(100) = 2，因为 10² = 100。
- **最常用的底**：**10、2、以及 e ≈ 2.71828…**。e 之所以被这样定义，是因为 **d log_e(x)/dx = 1/x**；**log_e 通常写作 ln**。
- **换底公式**：**log_b(x) = log_k(x) / log_k(b)**。注记：**ln(10) = 2.302585…**
- **三条运算律**（对数的全部威力所在）：
  - **log(mn) = log(m) + log(n)**（乘法降为加法）
  - **log(m/n) = log(m) − log(n)**（除法降为减法）
  - **log(mⁿ) = n·log(m)**（乘方降为乘法）
- **历史评论**：17 世纪对数的发现所带来的冲击，类似于计算机的发明——它简化了计算，使得从前不切实际的复杂分析成为可能。曾有专门的对数表小册子供查表用，**"just 35 years ago these tables used to be a commonplace part of the schoolboy's kit"**。
- **在岩石力学中的典型应用**（材料给的例子，公式在 OCR 中有符号缺失）：若
  - **ε̇ = A σⁿ exp(−H / RT)**（幂律蠕变方程）
  
  则取对数得
  - **ln ε̇ = ln A + n ln σ − H / RT**
  
  从而
  - **n = ( ln ε̇ − ln A + H / RT ) / ln σ**

  📎 这就是**幂律蠕变的应力指数 n** 的求法——把非线性关系线性化，从而可以用直线拟合求参数。虽然本周不考，但这正是 `Logs.md` 被放进应变练习包的深层原因：**构造地质学里大量参数是靠"取对数后做线性拟合"求出来的。**

---

## 六、易错点 / 重点难点

### 6.1 概念混淆类

| # | 易错点 | 正确理解 |
|---|---|---|
| 1 | **把应力（stress）与应变（strain）混用** | **本周只讲应变**——变形了多少，是几何/运动学量。**应力在 W05（Class 5）**——是什么力造成的，是力学量。两者都是**二阶张量**，都用 **Mohr 圆**表示，因此极易混淆。**答题时看清题目问的是 σ 还是 ε/e。** 讲义明说应力的 Mohr 圆是"更简单的形式"。 |
| 2 | **把"变形（deformation）"与"应变（strain）"当同义词** | 变形包含**四类位移**；**只有畸变与膨胀产生应变**。刚体平移与刚体转动是变形但**不是**应变。讲义的判别句："rigid displacement of a body is deformation, but it is not strain"。 |
| 3 | **有限应变（finite）与增量应变（incremental）混淆** | **有限应变**只联系"变形前"与"变形后"两个端点状态，**对变形路径一无所知**；**增量应变**描述路径上的每一小步。在**简单剪切**中，有限应变椭圆**不断改变椭率与方位**，而增量应变椭圆**保持不变**。 |
| 4 | **纯剪与单剪的旋转行为记反** | **纯剪切（pure shear）= 共轴 = 非旋转 = 主轴不动**；**简单剪切（simple shear）= 非共轴 = 旋转 = 主轴不断向剪切方向旋转**。记忆法：**"simple" 的 S 想成 "Spin（转）"**；或记住简单剪切把正方形变成**平行四边形**（歪掉了 → 转），纯剪切把正方形变成**矩形**（没歪 → 不转）。 |
| 5 | **把"共轴（coaxial）"与"非旋转（irrotational）"当作严格同义** | 讲义 Slide 16 notes 专门指出两者**严格说不同义**：**rotational/irrotational** 讲的是**有限主应变轴相对某坐标架是否改变方位**；**coaxial** 讲的是**有限主应变轴是否平行于增量应变椭球的主轴**。 |
| 6 | **把"劈理 = XY 面"当成无条件成立** | 三个例外必须记住：**剪切带型劈理（shear bands）不代表应变椭球**；**褶劈理（crenulation cleavage）不代表总应变的 XY 面**（因为它形成于变形开始之后很久）；此外，**Z 方向的缩短若未被 XY 面内的伸展补偿，则意味着体积损失**。 |
| 7 | **把标志物的应变当作岩石的应变** | 若标志物与基质**流变性质不同**（如砾岩中的砾石），测出的只是标志物的应变。还原斑、火山砾与围岩性质接近，结果更可信。 |

### 6.2 公式定义类（最高频失分区）

| # | 易错点 | 辨析 |
|---|---|---|
| 8 | **伸长率 e 与拉伸 s 搞混** | **e = (L − L₀)/L₀**，未变形时 **e = 0**；**s = L/L₀ = 1 + e**，未变形时 **s = 1**。**两者差一个 1！**若把 e = 1.478 当成 s 用，λ 会算成 2.18 而不是 6.14。 |
| 9 | **λ 与 λ′ 搞反** | **λ = (1 + e)²**（二次伸长，伸长越大 λ 越大）；**λ′ = 1/λ**（倒数二次伸长，伸长越大 λ′ **越小**）。Mohr 圆上 **λ₁′ 在左边（数值小）却对应最大伸长**——这是最反直觉的一点。 |
| 10 | **γ 与 γ′ 搞混** | **γ = tan ψ**（工程剪应变）；**γ′ = γ/λ = γ/(1+e)²**。Mohr 圆的纵轴是 **γ′ 不是 γ**。 |
| 11 | **张量剪应变忘了除以 2** | **e_ij = γ_ij / 2（i ≠ j）**。工程剪应变是张量剪应变的**两倍**。 |
| 12 | **角剪切 ψ 与剪应变 γ 混用** | **ψ 是角度（度或弧度）**，**γ 是无量纲的正切值**。ψ = 53° 时 γ = 1.327，**不是 53**。用计算器时**务必确认在度（DEG）模式**——若误用弧度，tan(53 rad) 会给出完全离谱的数。 |
| 13 | **符号约定张冠李戴** | **工程学约定：伸长为正**（讲义 Slide 3 的公式用的是这套）；**岩石力学约定：缩短为正**。**角剪切：逆时针为正、顺时针为负**。**Mohr 圆：顺时针（负）向上**——但 **Ramsay & Huber 用相反约定**。答题时**写明自己用的是哪一套**。 |
| 14 | **体应变公式记成加法** | **(1 + e_V) = (1 + e₁)(1 + e₂)(1 + e₃)** 是**乘积**，不是 e₁ + e₂ + e₃。（📎 只有在无限小应变下才近似有 e_V ≈ e₁ + e₂ + e₃。） |
| 15 | **R_XZ = R_XY × R_YZ 记成加法或搞错顺序** | 展开看就清楚：(X/Y)·(Y/Z) = X/Z ✓。**取对数后才变成加法**：ln R_XZ = ln R_XY + ln R_YZ。 |

### 6.3 图解与判读类

| # | 易错点 | 辨析 |
|---|---|---|
| 16 | **Flinn 图的 k 值分区判错** | **k > 1（45° 线之上）= prolate 长棒/收缩**；**k < 1（45° 线之下）= oblate 扁圆/压扁**；**k = 1 = 平面应变（无体积变化时）**；**k = 0 = 横轴 = 纯扁圆**；**k = ∞ = 纵轴 = 纯长棒**。记忆法：**纵轴（"竖着"）方向是"雪茄立起来"= prolate；横轴（"躺着"）方向是"饼摊平"= oblate。** |
| 17 | **Flinn 图的横纵轴装反** | 本课练习明确：**纵轴 = ln R_XY，横轴 = ln R_YZ**。装反会把 oblate 判成 prolate。 |
| 18 | **忘了取对数** | 本课的 Flinn 图是**对数版本**——练习第 3 步写得很清楚："take **natural logarithm** of the mean aspect ratio"。直接把 1.59 和 2.18 画上去会得到错误的点位（虽然本例中 oblate/prolate 的判断恰好不变，但量值全错）。 |
| 19 | **Lode 参数 ν 的正负与形状对应记反** | **ν = +1 → oblate（扁圆）**；**ν = −1 → prolate（长棒）**；**ν = 0 → 平面应变**。验证法：轴对称压扁时 ε₁ = ε₂，代入 ν = (2ε₂ − ε₁ − ε₃)/(ε₁ − ε₃) 得 +1。 |
| 20 | **Mohr 应变圆上把 2φ′ 写成 φ′** | 与应力 Mohr 圆一样，**圆上的圆心角是实空间角度的两倍**。本题 φ′ = 9° → 圆上量 **18°**。 |
| 21 | **Rf/φ′ 中 R_s 与 R_i 的公式记反** | **R_s = √(R_f,max × R_f,min)**（乘积开方，"应变"是两个极值的**几何平均**）；**R_i = √(R_f,max / R_f,min)**（商开方）。记忆法：**R_f,max = R_s × R_i，R_f,min = R_s / R_i**，反解即得。数值检查：R_s 应当落在 R_f,max 与 R_f,min **之间**（本题 1.60 < 3.10 < 6.00 ✓），而 R_i 应当**接近 1**（本题 1.94，是"砾石本来就有点扁"的程度）。 |
| 22 | **用算术平均近似 R_s** | 三种平均中**只有调和平均**在 **R_s > 2 且 R_i < 2** 时是好近似（本题 3.08 vs 真值 3.10）。**算术平均系统性偏高**（本题 3.76，偏高 21%）。 |
| 23 | **Fry 法作图时旋转了覆盖层** | 练习明确要求 "**Move the overlay (without rotating it)**"。一旦旋转，中央空缺椭圆的方位信息就毁了。 |
| 24 | **用刚体转动的碎块推断角剪切** | 讲义 Slide 30 notes 的明确警告——被拉断的箭石碎块的转动是**刚体转动**，不是角剪切。 |

### 6.4 答题规范类

| # | 易错点 | 规范 |
|---|---|---|
| 25 | **"principal" 拼成 "principle"** | 讲义专门提醒。**principal strain / principal axis / principal plane**。 |
| 26 | **角度只写数值不写旋向与符号** | 标准答案写的是 **"+ 53° (anticlockwise rotation)"**。 |
| 27 | **算完就停，不讨论可靠性** | Exercise 1 第 5 步的四段式（数字 → 误差来源 → 改进方案 → 结论）是本课的答题模板。 |
| 28 | **野外只测应变不测参考架** | 讲义原话 "super-important"：**必须同时测劈理走向/倾角与拉伸线理倾伏角/倾伏向**，否则应变结果无从解释。 |

---

## 七、本周术语表

| 英文 | 中文 | 本周定义 / 关键点 |
|---|---|---|
| Strain | 应变 | 物体在变形中所经历的大小与形状变化的度量 |
| Deformation | 变形 | 泛指位移；涵盖四类位移，可含或不含应变 |
| Displacement | 位移 | 某个给定质点位置的改变 |
| Displacement field | 位移场 | 物体内许多质点的位移矢量的集合 |
| Infinitesimal strain | 无限小应变 | 质点间距离变化很小时的应变 |
| Finite strain | 有限应变 | 质点间距离变化大到可测量时的应变 |
| Rigid body translation | 刚体平移 | 全部质点同向同距移动；不产生应变 |
| Rigid body rotation | 刚体转动 | 物体整体转动；质点间距离不变；不产生应变 |
| Distortion | 畸变 / 形状变化 | 质点相对位置改变；**产生应变** |
| Dilation | 膨胀 / 体积变化 | 体积改变而形状不变；**产生应变** |
| Linear (longitudinal) strain | 线应变 / 纵向应变 | 沿某方向的长度变化 |
| Engineering strain / extension | 工程应变 / 伸长率 | **e = (L − L₀)/L₀** |
| Stretch | 拉伸 | **s = L/L₀ = 1 + e** |
| Quadratic elongation | 二次伸长 | **λ = (1 + e)²** |
| Reciprocal quadratic elongation | 倒数二次伸长 | **λ′ = 1/λ** |
| Logarithmic (natural) strain | 对数应变 / 自然应变 | **ε = ln(1 + e)** |
| Shear strain | 剪应变 | 两条线之间夹角的变化 |
| Angular shear | 角剪切 | **ψ**：两条原本正交的线之间夹角的变化；**逆时针为正** |
| Engineering shear strain | 工程剪应变 | **γ = tan ψ** |
| Gamma prime | γ′ | **γ′ = γ/λ** |
| Tensor shear strain | 张量剪应变 | **e_ij = γ_ij/2（i ≠ j）** |
| Deformation gradient matrix | 变形梯度矩阵 | 用原位置给出变形后位置（Lagrangian）或反之（Eulerian）；已消去刚性平移 |
| Displacement gradient matrix | 位移梯度矩阵 | 其**对称部分 = 应变**，**反对称部分 = 转动** |
| Lagrangian / Eulerian specification | 拉格朗日 / 欧拉描述 | 以原位置 / 以变形后位置为参照 |
| 2nd rank tensor | 二阶张量 | 三维下需 3² = 9 个分量；应变与应力均是 |
| Strain ellipse | 应变椭圆 | 初始为**半径 1 的圆**的标志物变形后的形状（二维） |
| Strain ellipsoid | 应变椭球 | 初始为球的物体变形后的形状（三维） |
| Principal strain | 主应变 | 伸长取极值、角剪切为零的方向上的应变；**e₁ ≥ e₂ ≥ e₃** |
| X, Y, Z directions | X、Y、Z 方向 | 应变椭球三个半轴；**X = 1+e₁ ≥ Y = 1+e₂ ≥ Z = 1+e₃** |
| Volumetric strain | 体应变 | **(1 + e_V) = (1+e₁)(1+e₂)(1+e₃)** |
| Simple shear | 简单剪切 | 无面积变化的均匀剪切；**主轴旋转；rotational、non-coaxial**；正方形→平行四边形 |
| Pure shear | 纯剪切 | 无面积变化的伸长/缩短；**主轴不旋转；irrotational、coaxial**；正方形→矩形 |
| Coaxial / non-coaxial | 共轴 / 非共轴 | 有限主应变轴是否平行于增量应变椭球的主轴 |
| Rotational / irrotational | 旋转的 / 非旋转的 | 有限主应变轴相对坐标架是否改变方位 |
| Plane strain | 平面应变 | 某一主方向（Y）上无伸长或缩短；应变可当二维处理 |
| Axially symmetric extension / compression | 轴对称伸展 / 压缩 | 两个主方向长度变化相等（前者 Y=Z→长棒；后者 X=Y→扁圆） |
| Prolate | 长棒型 | **雪茄形（cigar）**；由一个方向的伸长主导 |
| Oblate | 扁圆型 | **薄饼形（pancake）**；由一个方向的压扁主导 |
| Constriction / flattening | 收缩型 / 压扁型 | prolate / oblate 域的另一种叫法 |
| Flinn diagram | Flinn 图 | 画 R_XY 对 R_YZ（本课取自然对数）；分开长棒域与扁圆域 |
| Flinn parameter k | Flinn 参数 k | 📎 **k = (a−1)/(b−1)**，a = R_XY，b = R_YZ（讲义未给，标准教科书定义） |
| Hsü diagram | Hsü 图 | 径向图；以 **ε_S**（量值）与 **Lode 参数 ν**（形状）作图 |
| Lode parameter | Lode 参数 | **ν = (2ε₂ − ε₁ − ε₃)/(ε₁ − ε₃)**；+1 扁圆，0 平面应变，−1 长棒 |
| Homogeneous strain | 均匀应变 | 平面仍是平面、直线仍是直线、平行线仍平行 |
| Inhomogeneous strain | 非均匀应变 | 大小与形状变化因地而异；真实应变均如此 |
| Progressive deformation | 递进变形 | 把变形拆成一系列应变增量来考察变形路径 |
| Incremental strain ellipse | 增量应变椭圆 | 每个应变增量对应的椭圆；恒定增量下**保持不变** |
| Strain path | 应变路径 | 由未变形态到变形态的中间过程 |
| Lines of no finite longitudinal strain | 无有限纵向应变线 | 把应变椭圆分成 L/S 四象限的两条线 |
| Boudinage | 布丁构造 / 石香肠构造 | 能干层被拉断成串；对应 LL 扇区 |
| Folded boudins / boudinaged folds | 褶皱化的布丁 / 布丁化的褶皱 | 分别对应 SL 与 LS 扇区，是判读应变路径的证据 |
| Orthorhombic / monoclinic symmetry | 斜方 / 单斜对称 | 分别为纯剪切 / 简单剪切所产生构造组合的对称性 |
| Strain marker | 应变标志物 | 已知初始大小或形状的物体 |
| Reduction spot | 还原斑 | 泥岩与板岩中的球形还原斑点 |
| Ooid / oolite | 鲕粒 | 灰岩中初始球形的颗粒 |
| Lapilli | 火山砾 | 凝灰岩中初始球形的凝灰质团块（雨滴周围形成） |
| Vesicle | 气孔 | 熔岩中的球形空腔 |
| Skolithos burrow | Skolithos 潜穴 | 层面截面近圆；与层面初始夹角约 90°，可测角剪切 |
| Belemnite | 箭石 | 脆性碎裂型标志物；碎块转动是刚体转动 |
| Crinoid stem / ossicle | 海百合茎 / 骨板 | 易解体的线状标志物；碎块间充填纤维 |
| Graptolite / thecae | 笔石 / 胞管 | 具特征尺寸（胞管间距）的化石标志物 |
| Fry method | Fry 法 | 用初始等轴颗粒中心点作图，中央出现椭圆形点空缺区 |
| Point vacancy | 点空缺区 | Fry 图中央的椭圆空白，其形状即应变椭圆 |
| Rf/φ′ method | Rf/φ′ 法 | 用初始椭圆标志物；画 R_f 对 φ′ 得泪滴形曲线 |
| R_f | 最终椭率 | 标志物变形后的长短轴比 |
| R_i | 初始椭率 | 标志物变形前的长短轴比 |
| R_s | 应变椭圆椭率 | **R_s = (1+e₁)/(1+e₃)** |
| Fluctuation, F | 涨落 | Rf/φ′ 泪滴形曲线的最大宽度 |
| Mohr construction (for strain) | 应变 Mohr 圆构造 | 横轴 λ′、纵轴 γ′；顺时针（负）向上 |
| L-tectonite / S-tectonite / LS-tectonite | L / S / LS 构造岩 | 线状元素主导（prolate）/ 面状元素主导（oblate）/ 两者兼有 |
| Cleavage | 劈理 | 一般假定代表应变椭球的 **XY 面（主压扁面）** |
| Cleavage refraction | 劈理折射 | 劈理跨越能干性不同的层时改变方位；反映剪应变差异 |
| Crenulation cleavage | 褶劈理 | 形成于变形开始之后很久，**不代表总应变的 XY 面** |
| Shear band | 剪切带（面理） | 此类劈理不直接对应应变椭球 |
| Tangential Longitudinal Strain (TLS) | 切向纵向应变 | 枢纽应变最大；内弧收缩、外弧伸展；存在中和面 |
| Neutral surface | 中和面 | TLS 褶皱中零应变的面 |
| Neutral point | 中和点 | 枢纽区无劈理的区域，反映 XY 面局部方位变化 |
| Flexural flow | 弯滑流 | 一种褶皱机制；应变分布与 TLS 相反 |
| Shear folding | 剪切褶皱 | Y 一般不平行枢纽，X、Z 一般不在剖面面内 |
| Layer-parallel shortening | 层平行缩短 | 褶皱起始前的缩短量，影响应变型式 |
| Post-buckle flattening | 后屈曲压扁 | 屈曲之后的进一步压扁 |
| Strain trajectory | 应变轨迹 | 平行于主应变绘出的线 |
| Strain ellipse map | 应变椭圆图 | 展示区域应变数据的最直观方式 |
| Xenolith | 捕虏体 | 岩基中可用作应变标志物的外来岩块 |
| Pressure solution | 压溶 | Z 方向体积损失的机制 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Class3_Strain.md` Slide 3 的 notes pane | "in the rock mechanics convention we have instead **e = L / L0 = (L0 - L) / L0** which is simply the negative of the engineering convention" | 中间那一项 **L / L₀ 写错了**。L/L₀ 是**拉伸 s**，不是应变 e；且 L/L₀ 与 (L₀−L)/L₀ 在数值上并不相等（例如 L = 2L₀ 时前者 = 2，后者 = −1） | 应为 **e = ΔL / L₀ = (L₀ − L) / L₀**。同一张幻灯片正文中工程学约定写的是 "e = ΔL/L₀ = (L − L₀)/L₀"，形式正确，可见 notes 中的 "L/L₀" 是笔误（很可能是想写 ΔL/L₀）。**这是本周唯一一处实质性公式错误。** |
| `Class3_Strain.md` Slide 19 正文 | "ε S = 3-½ [ (ε 1 - ε 2) 2 + … ] ½ **in which e1, e2 and e3 are the logarithmic principal strains**" | 公式中用的是希腊字母 **ε**，说明文字却写成拉丁字母 **e1, e2, e3**；而在同一份讲义中 e₁/e₂/e₃ 一直表示**工程主应变（伸长率）**，ε 才表示**对数应变** | 说明文字应为 "in which **ε₁, ε₂ and ε₃** are the logarithmic principal strains"。符号不一致，代入时若误用工程应变会得到完全错误的 ε_S 与 ν。 |
| `Class3_Strain.md` Slide 13 正文与 notes | "Tensors are distinguished as being of rank n where **3n** is the number of terms…"；notes 中 "30 = 1"、"31 = 3"、"32 = 9"、"33 = 27"、"34 = 81" | **上标在 pptx→md 转换中全部丢失**，读起来像 "3n"、"30"、"31" 等 | 应为 **3ⁿ**，以及 3⁰ = 1、3¹ = 3、3² = 9、3³ = 27、3⁴ = 81。属**格式转换损失**，非作者错误，但不知情者会读不懂（"30 = 1" 显然荒谬）。同类损失亦见于 Slide 3 的 "λ = ( L / L0 ) 2"（应为平方）与 Slide 4 的 "eij = γij/2"。 |
| `Class3_Strain.md` Slide 15 正文 | "( V / V0 ) = ( 1 + eV ) = ( 1 + e1 ) ( 1 + e2 ) ( 1 + e3 )" 中的 "eV" | 下标 V 未标为下标 | 应为 **e_V**（体应变）。格式问题，不影响理解，一并记录。 |
| `2-CoverAns.md` Exercise 2 引言 | "Remember this utilizes the **reciprocal quadratic extension** parameter, λ′ = 1/(1+e)²" | 术语与讲义不一致：讲义 Slide 3 与 Slide 32 用的是 **reciprocal quadratic elongation** | 应为 **reciprocal quadratic elongation（倒数二次伸长）**。属术语用词不统一，公式本身正确。 |
| `2-CoverAns.md` Exercise 2 第 1 题答案表 | 表中第一行标签被 OCR 成 "\|_e_\|=<br>_L_/_L_0\|= (111.5 - 45) / 45 = **1.478**" | 标签写成 **L/L₀**，但实际计算的是 **(L − L₀)/L₀** | 标签应为 **ΔL/L₀**。这多半是 PDF 中 "ΔL/L₀" 的 Δ 未被 OCR 识别所致（属**转换损失**而非原件错误）；**计算与答案 1.478 本身正确**。 |
| `2-CoverAns.md` Exercise 1 第 3、4 步；Exercise 2 引言；Exercise 4 第 6、7、8 步 | 多处 "These ellipticities are given by" / "for example," / "Hence it is trivial to show that" / "R_s is given by" 之后**紧接空白** | **关键公式在 PDF→md 转换中整段丢失**（原件中是排版公式或图片公式） | 丢失的公式已在本笔记 §3.3、§3.4、§3.7 中按讲义定义重建，并用练习给出的数值逐一复算验证通过（R_YZ = 4.06/1.59 = 2.55 ✓；R_s = √(6.00×1.60) = 3.10 ✓；R_i = √(6.00/1.60) = 1.94 ✓；三种平均值 3.76 / 3.42 / 3.08 ✓）。**复习时须以本笔记的公式为准，不能只看 md 版练习。** |
| `2-CoverAns.md` Exercise 4 数据区 | "5.14 1.67<br>5.40 -22° -30° 4.47 -3°<br>…" | OCR 把图中砾石的 **R_f 数值与 φ′ 角度的配对关系完全打乱**，且部分数值（如 "1.7"）有效位数与其余不一致 | **R_f 的数值集合（18 个）可用**——据此复算的三种平均值与答案完全吻合，说明数值本身抄录无误；但**"哪个 R_f 对应哪个 φ′"不可用**，因此无法据 md 版重画 Rf/φ′ 散点图。需查阅 PDF 原件。 |
| `4-Ex3sol2.md` 全文（29 词） | "o%s, °° / e e / ese sts / we? / ° fe % / aaa Sa ; / ou / © @sloJexy" | 该文件是 **Exercise 3（Fry 法）的答案**，但整份内容是图片 OCR 失败后的乱码，文件头已自标 "识别质量低——原件疑为手写或图件，文字大多不可靠" | **该文件不含任何可用信息**，无法从中读出 Fry 法练习的 R_s 值或长轴方位角。**不作任何推测。**Exercise 3 的操作步骤在 `2-CoverAns.md` 中完整可用，仅数值答案缺失；如需核对答案须查阅 `4-Ex3sol2.pdf` 原件。 |
| `Logs.md` 末段 | "= _A n_ exp (- _H_ / _RT_ )"、"ln = ln _A_ + _n_ ln - _H_ / _RT_" | **应变速率 ε̇ 与应力 σ 两个符号在 OCR 中整体丢失**，导致方程读不通 | 据形式可确定为**幂律蠕变方程**：**ε̇ = A σⁿ exp(−H/RT)**，取对数得 **ln ε̇ = ln A + n ln σ − H/RT**，故 **n = (ln ε̇ − ln A + H/RT) / ln σ**。已在 §5.5 中标注为重建内容。 |

**另外记录两点"非错误但值得注意"的事项**（不计入勘误）：

1. **`2-CoverAns.md` Exercise 2 的答案在该切面上不满足面积守恒**：(1+e₁)(1+e₃) = 2.77 × 0.81 = 2.24。材料对此未作说明。这**不一定是错误**（切面可能不是主平面，或数据本为教学而人造），但答题时若被问及体积变化，应据 (1+e₁)(1+e₂)(1+e₃) = V/V₀ 如实计算，不可默认体积不变。
2. **讲义 Slide 18 与练习均把"取对数后的 R_XY–R_YZ 图"称为 Flinn diagram**，而许多教科书把该对数版本单独称为 **Ramsay 对数图**。这是**术语惯例差异，不是错误**；本课答题一律按讲义口径称 Flinn diagram 即可。
