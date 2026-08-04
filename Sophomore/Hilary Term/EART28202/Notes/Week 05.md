# EART28202 Structural Geology — Week 05 学习笔记

> 本周材料：
> - Lecture：`Lecture/Week 5/Class5_Stress.md`（Class 5: Stress，共 40 张幻灯片，含大量 notes pane 补充说明）
> - Practical：`Practical/Week 5/` 下 `Handout(2).md`（符号约定说明）、`Ex1(6).md`（题面 + 1a 解答）、`Ex1bSoln(1).md`、`Ex1cSoln(1).md`、`Ex1dSoln(1).md`、`Ex2soln(1).md`、`Ex3soln(1).md`、`Ex4soln(1).md`
> - 本课全 10 周**没有 transcript**（课堂录音转写），所有内容均来自幻灯片正文、notes pane 与练习答案。

---

## 一、本周主题

本周的主题是**应力（stress）**，讲义标题 Class 5: Stress；配套 practical 是**二维莫尔圆（2D Mohr circle / Mohr diagram）**上的应力分析。

### 1.1 本周在全课骨架中的位置

EART28202 是春季学期（Semester 2）的第一门构造地质学课，是 EART24001 *Geological Maps* 的直接延续——把上学期"纯几何"的地质图判读，升级为**力学**。整门课的骨架（依据 syllabus 的 12 条 Theory/Practical 配对）大致是：

| 阶段 | 周次 | 内容 |
|---|---|---|
| **几何学** | W01–W03 | 褶皱几何、褶皱如何形成、应变（strain） |
| **力学** | W04–W06 | 剪切带、**应力（本周）**、破裂与小型侵入体的就位 |
| **构造类型** | W07–W10 | 断层作用、挤压构造域、伸展构造域、走滑构造域 |

**本周是"力学段"的理论核心。**W04 讲剪切带（变形的产物），W05（本周）建立应力这个"原因"的完整概念框架与图解工具，W06 立刻用它来讲**破裂准则（fracture criteria）**——Griffith 准则、Coulomb 准则、Byerlee 定律都要画在莫尔图上。讲义 Slide 16 自己就明说了："On a Mohr diagram, the effect of pore fluid pressure is to shift the Mohr circle to the left without changing its diameter. **The significance of this will be explored in the next two classes**"；Slide 23 也说古应力分析"forms the core material of the next two classes"。

也就是说：**本周不学会画莫尔圆，W06 与之后所有断层力学的内容都无从下手。**Syllabus 的 ILO 5 明确写着"evaluate normal and shear stresses acting on planes of different orientations using **graphical techniques**"——这就是本周 practical 要练的东西，而且 feedback 部分点名 Theory 笔试会考"aspects that were developed in the practicals (e.g., **stress and strain analysis**)"。

### 1.2 与 W03「应变」的对照：应变是结果、应力是原因

这是理解本周最重要的一条线索。W03 讲的**应变（strain）**是变形的**几何描述**——物体形状/大小变了多少，是可以在野外、在薄片下**直接测量**的东西；本周讲的**应力（stress）**是**力学状态**——是驱动变形的"原因"，本身**看不见、摸不着、只能间接推断**。

讲义 Slide 2 开门见山：

> "Deformation occurs when a force is applied to a body; the concept of stress is used to describe the physical state of a material body on which forces are applied. Hence, as structural geologists interested in deformation, we need to get to grips with stress."

两者的数学结构高度平行——**应变是张量，应力也是张量**（Slide 13 明说 "We noted previously (Class 3) that strain is a tensor quantity"）；应变有应变椭球，应力有应力椭球；应变有主应变轴，应力有主应力轴；两者都可以用莫尔圆表示（W03 讲过应变莫尔圆，本周是应力莫尔圆）。符号约定也刻意保持一致：**逆时针为正**（Slide 5 notes: "as it was when we considered shear strain, Class 3 Slide 4"）。

但讲义**最后一张内容页（Slide 39, "Stress or strain?"）专门提醒不要把这个因果关系当成绝对**：

> - 力学过程的"原因"由**边界条件**决定；
> - 若边界上施加并维持的是**应力**，则应力是原因、应变是响应；
> - 若边界被要求以规定的量或规定的速率**移动**，则**应变才是原因、应力是响应**（例如后面 Slide 29 的 uniaxial strain reference state，水平应力正是因为"水平方向不许应变"而产生的）；
> - "Many of our measurements in structural geology are actually of **strain** rather than stress"——我们在野外看到的是应变，把它反推成应力是一种**解释**，尤其当应变是有限应变（finite）而非无限小应变（infinitesimal）时要格外小心。

📎 背景补充：这一点在考试的简答题里是很好的"深度分"来源——被问到"从共轭断层推断古应力方向有什么局限"时，除了 Slide 32 notes 提到的 Andersonian 方案的局限（σ₂ 未必在断层面内），还可以答这条更根本的：我们观测的是应变而非应力。

### 1.3 讲义的宏观结构地图

讲义 40 张幻灯片可以切成四大块，复习时按块记忆效率最高：

| 幻灯片 | 板块 | 核心内容 |
|---|---|---|
| 2–17 | **应力的概念** | 力→traction→应力→主应力→莫尔圆→张量→平均/偏应力→有效应力→特殊应力状态 |
| 18–25 | **应力的测量** | 钻孔崩落、套芯解除、水力压裂、地震/断层反演、古应力（双晶、位错密度、动态重结晶粒径） |
| 26–38 | **岩石圈的应力状态** | 一个主应力铅直、σ_v=ρgz、孔压随深度、两种参考态、Anderson 分类、弯曲应力、残余应力、世界应力图、岩石圈强度剖面 |
| 39–40 | **反思与参考书** | 应力还是应变？；阅读书目 |

Slide 1 的 notes 里老师给了一句很关键的话：前十几张的应力概念推导是**提纲式的（outline form）**，严格版本在附带的 `StressNote.pdf` 里，"**You do NOT need to know the contents of this document for this course**"——即严格推导不考，但会用、会画必须过关。

---

## 二、核心概念

### 2.1 两类力：体力与面力

讲义 Slide 2 把力分成两类，这是全部推导的起点：

- **体力（body force）**：超距作用于岩石所有体元的力，例如重力、电磁力。**其大小正比于质量或体积。**
- **面力（surface force）**：一个物体通过它们之间的界面直接作用于另一个物体（例如用手推一块石头，力作用在手与石头的接触面积上）；或者**间接地**，物体的一部分通过某个**想象的内部界面**作用于另一部分——它描述的是想象界面一侧的物质对另一侧物质施加的**原子间力**。**其大小正比于力所作用的表面面积。**

**应力的概念完全来自对面力的考察**（"The concept of stress arises from a consideration of surface forces"）。想象的内部界面这一条尤其重要：正因为可以在岩石内部任意位置、任意方位切一个虚拟面出来谈受力，才有"一点处的应力状态"这种说法。

### 2.2 从力到 traction（面力强度）

Slide 3：

> "A large force obviously has a greater effect on an object than a small force. However, the **response of the object is governed by the intensity of the force, not by its magnitude**."

讲义用了一张恐龙站在不同支架上的图（引自 Twiss & Moores p.153）：恐龙体重不变（力不变），但支架的响应完全不同——因为接触面积不同。

**Traction（面力强度、面力向量）定义：**

$$T = \frac{F}{A}$$

- **单位**：力的 SI 单位是牛顿 N（使 1 kg 产生 1 m s⁻² 加速度的力）；故 traction 的单位是 N/m²，即**帕斯卡 Pa**（1 Pa = 1 N m⁻²）。
- Pa 太小，地质上常用 **MPa**，1 MPa = 10⁶ Pa。
- **1 kbar = 100 MPa**（notes 特别叮嘱："You will find it very convenient to remember this conversion"，因为在火成岩/变质岩岩石学里用的是 kbar）。
- 严格定义：traction 是 F/A 在 **A 收缩到零（收缩到一个点）时的极限**。

### 2.3 traction 向量的分解：为什么面积会变

Slide 4 是本周第一个真正需要动脑的地方。设力 F 作用在原始面积 A₁ 上，现在考察一个法线与 F 方向成 θ 角的斜面，其面积为 A₂ = A₁/cos θ。则该斜面上：

$$T_n = \frac{F_n}{A_2} = \frac{F\cos\theta}{A_1/\cos\theta} = \left(\frac{F}{A_1}\right)\cos^2\theta$$

$$T_s = \frac{F_s}{A_2} = \frac{F\sin\theta}{A_1/\cos\theta} = \left(\frac{F}{A_1}\right)\sin\theta\cos\theta = \left(\frac{F}{A_1}\right)\frac{\sin 2\theta}{2}$$

**θ 定义为施加力的方向与该面法线之间的夹角（逆时针为正）。**

Notes pane 特别点明了一个极易混淆之处：

> "Note the difference between **resolving the force vector** into normal and shear components (F_n = F cos θ; F_s = F sin θ), and **obtaining the traction vector** from its normal and shear components (T_n = T cos²θ; T_s = (T sin 2θ)/2)."

**区别的来源就是面积 A₂ 随 θ 变化。**分解"力"只出现一次三角函数，分解"traction"出现两次（一次来自力的投影，一次来自面积的变化）——这正是 cos²θ 与 sin 2θ/2 的由来，也是**莫尔圆公式里出现 2θ 的物理根源**。

另外 notes 提醒：**一般情况下，traction 向量与力向量并不平行**（"in general, the traction vector is not parallel to the force vector"），也与面的法线不平行。

### 2.4 符号约定：地质学 vs 工程学，Mohr 约定 vs 张量约定

这是本周**最容易失分**的一块，讲义 Slide 5、Slide 7、Slide 12 与 practical 的 `Handout(2).md` 反复强调。

**（1）正应力的正负：**
- **岩石力学 / 地质学约定：压应力（compressive）为正。**理由（Slide 5 notes）：地球内部的应力以压应力为主，这样定义可以少写一堆负号。
- **工程学约定：张应力（tensile）为正。**理由：工程师关心结构破坏，而材料的抗张强度通常远小于抗压强度，张应力对他们更重要。
- **本课永远用岩石力学约定**（`Handout(2).md` 用加粗强调："***We will always use the rock mechanics definitions***"）。

**（2）剪应力的正负——两套并存的约定：**

| 约定 | 规则 | 后果 |
|---|---|---|
| **Mohr 圆约定**（Mohr circle convention） | **逆时针剪切力偶为正**，顺时针为负 | 矩阵中 σ_xy 与 σ_yx **符号相反**（σ_xy = −σ_yx） |
| **张量约定**（tensor convention） | 看**切负坐标轴的那几个面**：若应力分量为正，它在该面上应指向**正坐标方向** | 矩阵中 σ_xy = σ_yx，**矩阵对称**，数学上方便 |

Slide 7：为使方块单元不自转（力学平衡），两个剪应力项必须**大小相等、方向相反**；在 Mohr 约定下这写成 σ_xy = −σ_yx；改用张量约定则可以写成 σ_xy = σ_yx，**矩阵关于主对角线对称**。

`Handout(2).md` 补充：在工程界（张为正）同样的规则改成看**切正坐标轴**的那几个面。

**（3）逆时针为正的方向依赖性**（Slide 5 notes 与 Handout 都讲了）：
一个旋转从一侧看是顺时针，从另一侧看就是逆时针。"逆时针为正"只有在 **x 轴向右、y 轴向上**（画图的常规摆法）时成立，因为按右手定则此时我们是沿 −z 方向观察。若 x 轴向左，则逆时针变成负。

`Handout(2).md` 给了**一致性判据**（3D 莫尔图上必须遵守，因为三个嵌套圆必须从同一方向看）：

> "Consistency is achieved if there is a **clockwise sense of rotation from the positive coordinate axis parallel to the greatest normal stress component to the positive coordinate axis parallel to the least normal stress component**. If this is not the case, flip the axes."

Handout 同时说明：**2D 练习里这件事其实不影响答案**（"This does not actually matter for 2D stress exercises"），只要自己内部一致即可。

📎 背景补充：这正是 Ex1 与 Ex2 的一个隐藏差异。Ex1 用 (x, y) 框，**y 轴向上**；Ex2 用 (x, z) 框，**z 是深度、向下**。同样是张量约定下 σ_xy = +40 的剪应力，在 Ex1 的框里换算成 Mohr 约定是**负**（顺时针），在 Ex2 的框里却是**正**（逆时针）。原因就是第二根轴的指向翻转了，页面上的旋转感随之翻转。做题时**一定要先看清楚第二根轴朝哪儿**。

### 2.5 二维的一点应力状态：应力椭圆与四个数

Slide 6：在 2D 中，若计算通过某点的**所有可能方位的面**上的 traction，把这些 traction 向量的尾端连起来，就画出一个**椭圆**——**应力椭圆（stress ellipse）**。

- 定义这个椭圆的形状与方位，只需要知道**两个相互垂直的面**上的 traction。
- 因此二维应力状态由**四个数**确定：
  - 两个正应力：σ_n = σ_xx, σ_yy
  - 两个剪应力：τ = σ_xy, σ_yx

**下标规则**（notes pane）：**第一个字母指面的法线方向，第二个字母指该应力分量作用的方向。**当只讨论某一个特定面时，习惯把该面上的正应力写作 **σ_n**、剪应力写作 **τ**。

Notes 还给出两条重要认识：
1. 2D 分析适用于**双轴压缩（或双轴拉伸）**，即所有 traction 同号，不能一正一负混着来。
2. 存在**两个互相垂直的面**，其 traction 向量恰好平行于面的法线（剪切分量为零）。这两个方位对应 traction 向量大小的**极大值与极小值**，也就是**应力椭圆的两个轴**。

**traction 与"面"的关系** —— notes 提醒：由于 traction 一般不垂直于它作用的面，**给定一个 traction 向量，它作用在哪个面上并不一目了然**。（Ragan p.226 给了一个由 traction 向量反推面方位的作图法。）

### 2.6 应力矩阵

Slide 7（2D）与 Slide 12（3D）：把这些数写成矩阵。

二维：

$$\boldsymbol{\sigma} = \begin{pmatrix} \sigma_{xx} & \sigma_{xy} \\ \sigma_{yx} & \sigma_{yy}\end{pmatrix}$$

三维（把 x, y, z 轴改标为 1, 2, 3）：

$$\boldsymbol{\sigma} = \begin{pmatrix} \sigma_{11} & \sigma_{12} & \sigma_{13} \\ \sigma_{21} & \sigma_{22} & \sigma_{23} \\ \sigma_{31} & \sigma_{32} & \sigma_{33}\end{pmatrix}$$

- **主对角线上是正应力，非对角线上是剪应力。**
- 同一**行**的项第一个下标相同，同一**列**的项第二个下标相同。
- 用张量约定（看立方体**背面/隐藏面**上的剪切分量是否指向正坐标方向）则 σ₁₂ = σ₂₁、σ₂₃ = σ₃₂、σ₁₃ = σ₃₁，矩阵**对称**。

### 2.7 三维的一点应力状态

Slide 11：三维中，一点的应力状态由**任意三个相互垂直的面**上的应力完全确定。用笛卡尔坐标系，外力 F 沿 x 轴的分量 F_x 产生：

- σ_xx = F_x / A_x（正应力）
- σ_yx = F_x / A_y（剪应力）
- σ_zx = F_x / A_z（剪应力）

同理 F_y → σ_yy, σ_xy, σ_zy；F_z → σ_zz, σ_xz, σ_yz。共 **9 个数**。

应力椭圆升级为**应力椭球（stress ellipsoid，又称 Lamé 应力椭球）**，定义**三个主应力 σ₁, σ₂, σ₃**：

- **σ₁ = 最大主应力**（椭球最长轴）
- **σ₂ = 中间主应力**（中间轴）
- **σ₃ = 最小主应力**（最短轴）
- 约定 **σ₁ ≥ σ₂ ≥ σ₃**（在压为正的地质约定下，σ₁ 是"压得最狠"的方向）

**以某个主应力为法线的面上，剪应力为零，traction 向量就等于该面上的正应力。**

### 2.8 主应力与主平面

Slide 8 是本周的公式枢纽：

> "It is always possible to choose an orientation of the coordinate axes such that the **shear stresses are zero** parallel to these axes."

- 在这个特殊取向下，平行于坐标轴的正应力称为**主应力（principal stresses）**。
- **主应力面（principal planes of stress）**：剪切分量为零的面，其上 traction 向量平行于面的法线。
- 2D 中 σ₁ 是应力椭圆的**半长轴**，σ₂ 是**半短轴**。

**两组核心公式**（notes 说明：第一组用于"已知 σ_xx, σ_yy, σ_xy 求主应力"，第二组用于"反过来"）：

$$\sigma_1, \sigma_2 \;=\; \tfrac{1}{2}(\sigma_{xx}+\sigma_{yy}) \;\pm\; \tfrac{1}{2}\left[(\sigma_{xx}-\sigma_{yy})^2 + 4\sigma_{xy}^2\right]^{1/2}$$

$$\tan 2\theta \;=\; \frac{2\sigma_{xy}}{\sigma_{xx}-\sigma_{yy}}$$

$$\sigma_n \;=\; \frac{\sigma_1+\sigma_2}{2} \;+\; \frac{\sigma_1-\sigma_2}{2}\cos 2\theta$$

$$\tau \;=\; \frac{\sigma_1-\sigma_2}{2}\sin 2\theta$$

其中 **θ 是从 σ₁ 量到该面法线的角度**（"where θ is the angle measured from σ₁ to the normal to the plane"）。

### 2.9 应力是张量

Slide 13：

> "Stress is an example of a **tensor** quantity. The individual components are defined in a coordinate frame that has a particular orientation; **if that frame is rotated the values of the components change**. However, they change in accordance with a specific transformation equation, and so **if the values are known in any one coordinate frame, they can be calculated in any other**."

- 总可以把坐标系转到使所有剪应力为零的取向——即平行于应力椭球的三根轴。
- 此时矩阵只剩三个非零的主对角项，就是三个主应力：σ₁ = σ₁₁, σ₂ = σ₂₂, σ₃ = σ₃₃。
- Notes 给出线性代数版本：**三个主应力的大小是应力矩阵的三个特征值（eigenvalues），主应力的方位是它的三个特征向量（eigenvectors）**——这正是 Practical Ex3(e) 要练的东西（notes 里明说了 "an illustration of this procedure for the 2D case is given in the solution set to one of the exercises in the Stress practical"）。
- 使用坐标变换方程需要熟悉**方向余弦（direction cosines）**。

**这就是"应力是张量"在实际操作上的意义**：应力不是一个数（标量），也不是一个箭头（向量）；它是一个"给我一个面的方位，我还你那个面上的 traction"的机器。莫尔圆就是这台机器的图形化。

### 2.10 平均应力与偏应力

Slide 15：任何应力张量都可以拆成两个矩阵之和——**平均应力（mean stress）**部分与**偏应力（deviatoric stress）**部分。

$$\sigma_m = \frac{\sigma_{11}+\sigma_{22}+\sigma_{33}}{3}$$

📎 背景补充（讲义 md 中矩阵图未被提取出来，此处补上标准写法）：

$$\begin{pmatrix} \sigma_{11} & \sigma_{12} & \sigma_{13} \\ \sigma_{21} & \sigma_{22} & \sigma_{23} \\ \sigma_{31} & \sigma_{32} & \sigma_{33}\end{pmatrix} = \begin{pmatrix} \sigma_m & 0 & 0 \\ 0 & \sigma_m & 0 \\ 0 & 0 & \sigma_m\end{pmatrix} + \begin{pmatrix} \sigma_{11}-\sigma_m & \sigma_{12} & \sigma_{13} \\ \sigma_{21} & \sigma_{22}-\sigma_m & \sigma_{23} \\ \sigma_{31} & \sigma_{32} & \sigma_{33}-\sigma_m\end{pmatrix}$$

讲义给出的物理含义（务必记牢）：

- **平均应力**造成/来源于**膨胀（dilation，体积变化）**；
- **偏应力**造成/来源于**畸变（distortion，形状变化）**；
- 在岩石圈中，平均应力的量级一般与**围压（confining pressure，由埋深与上覆岩柱密度控制）**相当，**通常远大于偏应力**；
- **但真正决定地质构造如何形成的是偏应力。**

Notes 里老师解释了他为什么写"causes/arises from"这种两可的措辞：既可以把应力看成应变的原因，也可以把应力看成应变的结果（呼应 Slide 39）。

📎 背景补充：**差异应力（differential stress）σ₁ − σ₃** 是偏应力在实际使用中最常见的标量度量，讲义在 Slide 25（古应力计标定 σ₁−σ₃）、Slide 37（岩石强度："at any depth, the one that gives the **smallest (σ₁ − σ₃)** applies"）、Slide 23（应力比 Φ 的分母）里都直接用它。**在莫尔图上，差异应力就是圆的直径，(σ₁−σ₃)/2 就是半径。** 讲义本身没有把"differential stress"这个词单独定义成一张幻灯片，但通篇默认你懂。

### 2.11 静水/等静应力与有效应力

Slide 16：

- 若**偏应力矩阵全为零**，则 σ₁ = σ₂ = σ₃，应力椭球退化成一个**球**。这种状态称为 **isostatic（等静）/ hydrostatic（静水）/ lithostatic（岩静）应力**。
- Notes 区分用法：**lithostatic 用于固体岩石中的应力，hydrostatic 用于流体中的应力。**
- **孔隙流体压力（pore fluid pressure）对抗正应力，而完全不影响剪应力。**因此定义**有效应力（effective stress）**。
- **在莫尔图上，孔隙流体压力的作用是把莫尔圆整体向左平移，而不改变其直径。**其意义将在接下来两节课（W06、W07）展开。

📎 背景补充：讲义 md 里"define effective stress as"后面的公式图未被提取出来。标准写法（**Terzaghi 有效应力原理**）为：

$$\sigma_n' = \sigma_n - P_f \qquad \text{(或写作 } \sigma' = \sigma - P_f\text{)}$$

$$\tau' = \tau$$

即**每一个正应力都减去孔隙流体压力，剪应力不变**。因此 σ₁' = σ₁ − P_f、σ₃' = σ₃ − P_f，两者同减一个数 ⇒ 圆心 (σ₁+σ₃)/2 左移 P_f，半径 (σ₁−σ₃)/2 不变。**这正是"圆整体左移、直径不变"这句话的公式来源，也是 W06 讲流体促发破裂（fluid-assisted fracturing / 水力压裂）的全部机理。**

### 2.12 特殊应力状态

Slide 17 列出六种（图引自 Fossen p.80）：

| 状态 | 名称 |
|---|---|
| σ₁ > σ₂ > σ₃ | 一般三轴应力（general triaxial） |
| σ₁ > σ₂ > σ₃ = 0 | 双轴压缩（biaxial compression） |
| σ₁ > σ₂ = σ₃ = 0 | 单轴压缩（uniaxial compression） |
| 0 = σ₁ = σ₂ > σ₃ | 单轴拉伸（uniaxial tension） |
| σ₁ > σ₂ = 0 > σ₃ | 一压一张的双轴状态 |
| σ₁ = σ₂ = σ₃ = p | 静水/等静应力 |

（表中"名称"一列为 📎 背景补充；讲义只给了不等式与图，未逐一命名。）

Notes 提醒一个记号问题：**谈主应力时双下标可以简写成单下标**（σ₁ = σ₁₁），不会有歧义。

### 2.13 应力的测量

Slide 19 先说明**为什么要测**：隧道/采石场/水坝的安全设计；提高钻孔稳定性与钻头导向控制；深部岩石的可控压裂以提高油气与地热产能；理解地震等自然灾害何时何地发生；从根本上理解板块构造如何运作。

📎 背景补充：这一段对 Energy and Resources 方向的学生格外相关——钻孔稳定性、水力压裂、地热储层增产全都是本专业后续（三年级 engineering geology / petrophysics）的直接内容。

**四类现今应力测量方法：**

**(1) 钻孔崩落 Borehole breakouts（Slide 20）**
- 钻孔壁上的破坏带，使钻孔变成不规则、通常呈**长条形**的截面。
- **碎片剥落（spalling）优先平行于最小水平应力 σ_h 发生，即垂直于最大水平应力 σ_H。**
- Notes 给出原因：假设铅直应力是最大主应力，则 σ_h 方向上的**偏应力最大**，崩落是钻孔壁的**压缩破坏**。若已知岩石抗压强度，**崩落带的宽度可用于定量估算 σ_H 的大小**。
- 用测斜仪（dipmeter）和井壁成像工具（有可向外撑住井壁的臂）测量。也可用于公路/隧道爆破孔，但可靠性较低。

**(2) 套芯解除 Overcoring（Slide 21）**
- 属于**应变松弛法（strain relaxation method）**。
- 步骤：先钻一个小孔 → 在孔壁贴**应变片（strain gauge）** → 再在小孔外围钻一个环，留下一个**中空岩石圆柱**，其上来自围岩的应力被释放 → 应力释放引起圆柱的弹性变形 → **若已知岩石的弹性性质，即可由这些变化算出应力**。也可取出岩芯、测它脱离围岩约束后的膨胀量。
- **限于几十米深度，常用于隧道中。**（应变片原理：金属丝电阻 = 电阻率 ×（长度÷截面积），变形改变电阻，由事先标定反推应变。）

**(3) 水力压裂 Hydraulic fracturing / hydrofracking（Slide 22）**
- 可同时确定主应力的**方位与大小**。
- 步骤：用两个可充气的橡胶封隔器（packers）封住一段钻孔 → 泵入流体提高两封隔器之间的流体压力 → 到某个**临界压力**时形成一条**张性裂缝（extension fracture）** → 此刻停泵 → 流体流入裂缝使压力下降，直到降至**刚好足以维持裂缝张开**的压力。
- **这个"刚好维持张开"的压力被取作 σ_h**；再结合岩石的**抗张强度**与裂缝形成时的**临界压力**，即可算出 σ_H。
- **裂缝平行于 σ_H 形成**，由此确定 σ_H 的方位。Notes 给出原因：环向应力（hoop stress，沿钻孔周向的应力）在该方向上压性最弱，所以最容易在那里张开裂缝。

**(4) 由地震与断层估算（Slide 23）**
- 可由 (a) **地震初动研究（earthquake first motion studies）**，或 (b) **断层面与滑动向量方位的测量**，估算主应力**方位**及其**相对大小**——后者用**应力比（stress ratio）**表示：

$$\Phi = \frac{\sigma_2-\sigma_3}{\sigma_1-\sigma_3}$$

- 两种方法都需要**多条不同方位的断层**的资料来约束分析。
- 若还能确定 (σ₁ − σ₃) 以及其中一个主应力（通常是铅直应力），则用 Φ 可得到全部三个主应力的大小。
- **应力柱（stylolites）、脉系（vein systems）、共轭裂隙（conjugate fractures）**的方位与空间分布，都可用于估算主应力方位——无论是现今活动的构造环境，还是地质记录中的。"The analysis of these features **forms the core material of the next two classes**."

**(5) 古应力技术 Palaeostress（Slide 24–25）**

*方位*：由**机械双晶（mechanical twins）**的方位、**变形纹（deformation lamellae）**的方位估算——具体讲义配了**石英变形纹**与**方解石双晶**两张显微照片。

*大小（"应力计" piezometers）*：随主应力增大，
- **方解石双晶出现频率增加**
- **位错密度（dislocation density）增加**
- **亚晶粒直径（subgrain diameter）减小**
- **动态重结晶粒径（dynamically recrystallized grain size）减小**

老师强调："Some of these piezometers have a **strong theoretical foundation** and are not merely empirical calibrations from laboratory deformation experiments."

Notes 的一条重要限制："The use of palaeostress techniques is **to some extent compromised by the need to establish when in the deformation history the microstructures formed**."（要知道这些显微构造是在变形史的哪个阶段形成的。）

### 2.14 岩石圈中的应力状态

**(1) 一个主应力是铅直的（Slide 27）**

> "Rocks at the Earth's surface are in contact with **air or water, neither of which can sustain a shear stress**. Hence there is **no shear stress at the Earth's surface** and so **one of the principal stresses at the Earth's surface must be vertical and the other two horizontal**."

- 现有资料表明这在整个**上地壳（深至 15–20 km）**都是很好的近似。
- 铅直应力通常取为上覆岩层重量：

$$\sigma_v = \rho_{rock}\, g\, z$$

- 大陆上 ρ_rock ≈ 2.7 g/cm³，给出**铅直应力梯度 26.5 MPa/km**，与现有资料吻合得很好。（复算：2700 × 9.81 × 1000 = 2.649×10⁷ Pa/km = **26.49 MPa/km** ✓）
- Notes 指出 σ_v = ρgz 本质上就是 F = ma 的另一种写法：σ_v = F/A，ρ = m/V，g = a，z = V/A ⇒ (F/A) = (m/V)·a·(V/A) ⇒ F = ma。
- 多孔沉积岩密度较小（ρ_rock = 2.1–2.5 g/cm³）。
- 南部非洲主应力的赤平投影图：数据**集中在网心、并沿网缘散布** ⇒ 一个主应力铅直、另两个水平。

**(2) 孔隙流体压力随深度的变化（Slide 28）**

若孔隙一直连通到地表：

$$p_{fluid} = \rho_{fluid}\, g\, z \;\approx\; g z \qquad (\rho_{fluid} \approx 1\ \mathrm{g/cm^3})$$

若孔隙不连通（例如夹在压实泥岩之间的多孔砂岩），孔隙流体可能**超压（over-pressured）**。此时孔压介于**静水**与**岩静**之间，但**不能比岩静压力大很多**。

**孔压参数：**

$$\lambda \equiv \frac{p_{fluid}}{\sigma_v}$$

对连通到地表的孔隙流体：λ = ρ_fluid/ρ_rock ≈ 1/2.7 ≈ **0.4**，因此 **λ > 0.4 是超压的度量**。

Notes 的两条要点：
- 单位陷阱：用 SI 单位（Pa, kg/m³, m/s², m）最保险；但若用 ρ 以 g/cm³、g 以 m/s²、z 以 km，算出的 p 直接就是 MPa。
- 孔压不能超过岩静压力（或超不了多少），因为那样有效压力就变成张性的，而**岩石抗张能力很弱——孔压一旦超过岩静压力，岩石就破裂**。
- 超压对钻井工程师很重要：超压岩石往往压实/胶结差，钻孔容易坍塌；若钻穿超压流体储层，流体会喷出地表（井喷）。

**(3) 水平应力：单轴应变参考态（Slide 29–30）**

考虑埋藏但**无侧向应变**的情形（两侧岩石不允许侧向膨胀，例如沉积盆地中的埋藏）。此时 σ_v = ρ_rock g z（= σ₁），而水平应力 σ_H = σ_h（= σ₂ 与 σ₃）为：

$$\sigma_H = \frac{\nu}{1-\nu}\,\sigma_v = \frac{\nu}{1-\nu}\,\rho_{rock}\, g\, z$$

其中 ν 是**泊松比（Poisson's ratio）**。对岩石 ν 约在 0.25–0.33 之间，故**水平应力约为铅直应力的 1/2 到 1/3**。

考虑温度变化后（E = 杨氏模量，α = 热膨胀系数，T = 温度变化）：

$$\sigma_H = \frac{\nu}{1-\nu}\,\sigma_v + \frac{E}{1-\nu}\,\alpha T$$

Notes 给了完整推导（值得看，因为它是纯弹性力学的三步）：H 方向的应变由三部分组成——该方向应力产生的应变 σ_H/E，减去另两个正交方向应力经泊松效应引起的膨胀 −νσ_V/E 与 −νσ_h/E：

ε_H = (1/E)[σ_H − ν(σ_V + σ_h)]

令 ε_H = 0 且 σ_h = σ_H，整理即得 σ_H = [ν/(1−ν)]σ_V。

**Slide 30 的推论非常漂亮**：相邻岩性因 ν、E、α 不同而有不同的应力史。若埋藏时 ν_砂 = 0.25、ν_泥 = 0.40，则 σ_H,砂 = 0.5 σ_H,泥（复算：0.25/0.75 = 0.333；0.40/0.60 = 0.667；比值恰为 0.5 ✓）。若在深部成岩后两种岩性的 ν 都变成约 0.3，则**当它们被带回地表时，砂岩会处于张应力状态、泥岩处于压应力状态**——这解释了野外常见的现象：**砂岩层中发育裂隙组，而其中的泥岩夹层里没有**（讲义配了 Amroth, Pembrokeshire 的照片）。

Notes 明确说这个模型只有**示意价值（illustrative value only）**：它假定无侧向应变、只粗略处理弹性性质随深度的变化、忽略孔压效应、并假定在最大埋深处瞬间成岩。

**(4) 恒定远场水平应力参考态（Slide 31）**

考虑厚度 z₁ 的均衡补偿岩石圈，其下地幔表现如流体（σ_H = σ_h = σ_v）。若因侵蚀而减薄或因沉积而加厚，均衡调整会抬升（侵蚀）或压低（沉积）岩石圈底面。**若远处的水平应力保持不变，则局部的水平应力在减薄段必然更大，因为同样的水平力作用在更小的面积上。**（📎 背景补充：具体公式图未在 md 中提取出来；讲义说明其中 z 为厚度变化量、减薄取负，ρ_c 为岩石圈密度，ρ_m 为地幔密度。）老师评价："This expression is **the most realistic available for a lithosphere unaffected by tectonic forces**."

**(5) 构造应力与 Anderson 分类（Slide 32）**

> "Deviations from the states of stress that we have discussed so far arise predominantly from **tectonic processes**. Tectonic stresses are classified into **three regimes depending upon which of the three principal stresses is vertical (Andersonian classification)**."

📎 背景补充（讲义此处只有图、无文字表格，下表为标准 Anderson 三分方案，与 Slide 32 notes 中"共轭断层以 ±30° 交于 σ₁、σ₂ 位于断层面内"的描述一致）：

| 铅直的主应力 | 构造体制 | 断层类型 | 典型断层倾角 |
|---|---|---|---|
| σ₁ 铅直 | 伸展（extensional） | **正断层 normal** | 约 60° |
| σ₂ 铅直 | 走滑（strike-slip） | **走滑断层 strike-slip** | 近直立 |
| σ₃ 铅直 | 挤压（contractional） | **逆断层 reverse / thrust** | 约 30° |

Notes 给出 Anderson 方案的推理与**局限**：
- 推理：假设一个主应力铅直（地表无平行于地面的剪应力），则主应力有三种可能排列；若共轭断层以 **±30° 交于 σ₁** 形成、且 **σ₂ 位于每条断层面内**（平行于它们的交线），就有三种断层几何。
- 局限："the assumption that **σ₂ lies in the fault plane is an oversimplification** and cannot be true in the case where three or more differently oriented faults that do not share a common line of intersection are simultaneously active."（Healy et al., 2015）
- 后人已把该分类扩展到**转张（transtension）与转压（transpression）**（Simpson, 1997）。

**这张幻灯片是 Practical Ex4 的直接依据，也是 W06–W07 的过渡。**

**(6) 其他应力来源（Slide 33–34）**

*弯曲应力（stresses due to bending）*：岩石圈弯曲在与**弯曲波长相当的距离**上产生应力。板块弯曲的场合：俯冲带进入海沟处；响应地表载荷（冰盖、火山岩堆积、盆地沉积载荷与侵蚀卸载、逆冲席 thrust sheets）；响应跨纬度运动（地球不是理想球体）。更局部则发生在断层、褶皱、底辟侵入体旁侧。（Notes 有趣的一笔：把图中的冰换成熔岩流，这张图就是**月海之下月壳变形**的卡通图。）

*残余应力（residual stress）*：微观尺度诱发、变形停止后仍储存在岩石中的应力，来源包括——**温度变化**（矿物热膨胀系数不同）、**压力变化**（矿物压缩性不同）、**变形本身**产生的晶格缺陷（位错）、**熔体结晶**、**有体积变化的变质反应**。这些应力可能在**抬升与剥蚀过程中通过破裂释放**。

**(7) 世界应力图与板块构造背景（Slide 35–36）**

- **World Stress Map** 项目汇编了全球应力测量结果（www.world-stress-map.org），图上采用 Andersonian 构造应力体制的分类。
- 其结果可与板块构造的主要驱动力良好对应：**板片拉力（slab pull）、洋脊推力（ridge push）、碰撞阻力（collisional resistance）、基底拖曳（basal drag）**。这些力定义了**全球应力型式**，再被重力控制的**二级应力源**（即 Slide 33 的各种弯曲过程）局部改造。

**(8) 岩石圈强度（Slide 37–38）**

- 任一深度的应力常被近似为该深度岩石的**强度**，由**本构方程（constitutive equations）**给出（把材料参数与温度、应力、应变速率结合）。四个最常用的本构方程中，**在任一深度，给出 (σ₁ − σ₃) 最小的那一个适用**。
- 两大类变形机制：浅部冷、压力小 → 脆性的**碎裂变形（cataclastic deformation）**；深部热、压力高 → 不形成裂缝地流动，通过**晶内塑性（intracrystalline plasticity）**与**扩散物质迁移（diffusive mass transfer）**实现。
- 碎裂变形的方程（同一方程分别按 σ₁ 铅直（伸展）与 σ₃ 铅直（挤压）改写）**基本与岩性无关**——这就是 **Byerlee 定律（Byerlee's law）**，"we will return to it in **Class 7**"。相关概念：岩石圈"**临界应力（critically stressed）**"，即其中应力等于岩石在当地条件下的强度。
- **强度–深度剖面**按给定应变速率、地温梯度、岩性分层计算。大陆岩石圈（上地壳=石英、下地壳=长石、上地幔=橄榄石）有三个流行模型：**"三明治"（jelly sandwich）**——弱下地壳夹在强上地壳与强上地幔之间，适用于**低**地温梯度与**水化**下地壳；**"焦糖布丁"（crème brûlée）**——强地壳、弱地幔，适用于**高**地温梯度与**脱水**下地壳；**"香蕉船"（banana split）**——适用于长期存在、延伸极深的大型断裂带。洋壳岩石圈的剖面则理解得更清楚。

---

## 三、公式与图表

**本段是本周的绝对核心。目标：读完能自己画、自己读一张 2D 莫尔图。**

### 3.1 两条核心方程

$$\boxed{\;\sigma_n \;=\; \frac{\sigma_1+\sigma_3}{2} \;+\; \frac{\sigma_1-\sigma_3}{2}\cos 2\theta\;}$$

$$\boxed{\;\tau \;=\; \frac{\sigma_1-\sigma_3}{2}\sin 2\theta\;}$$

> **符号说明**：讲义 Slide 8–9 因为在讲 **2D**，用的是 **σ₁ 与 σ₂**（二维只有两个主应力，σ₂ 就是二维中的最小主应力）。在三维的地质应用中（Practical Ex4、以及 W06 之后），惯例写成 **σ₁ 与 σ₃**。两者是同一个公式：**用你所在那个平面内的最大与最小主应力**。本笔记之后统一用 σ₁、σ₃，但做讲义原题时请照讲义的 σ₁、σ₂ 读。

### 3.2 逐项拆解

**（1）θ 到底是什么角？——头号考点**

> 讲义 Slide 8 原文：**"θ is the angle measured from σ₁ to the normal to the plane"**
> 讲义 Slide 9 notes：**"θ is the angle from σ₁ to the normal of the plane of interest and plots on the Mohr diagram as anticlockwise (+ve) up"**

**θ 是「σ₁ 方向」与「所考察那个面的法线（pole）」之间的夹角，不是 σ₁ 与面本身的夹角。**

Slide 10 专门为这件事开了一张幻灯片：很多人偏好用 **α**——σ₁ 与**面本身**的夹角（"arguably more intuitive"），莫尔图也可以照 α 画。但：

> **"Throughout this course we will use the mathematically more conventional version"**（即用 θ，法线角）。

**换算关系：α = 90° − θ**（α 也等于 σ₂/σ₃ 到面法线的角）。

**（2）为什么是 2θ 而不是 θ？**

三条理由，理解任何一条都够用：

1. **代数来源**：Slide 4 已经出现了 T_n ∝ cos²θ 与 T_s ∝ sinθcosθ；用倍角公式 cos²θ = (1+cos2θ)/2、sinθcosθ = (sin2θ)/2，2θ 自动出现。**根源是"面积随面的方位而变"，使三角函数出现两次。**
2. **周期性**：一个面转过 180° 就回到它自己（法线朝上和朝下是同一个面）。所以应力状态对面的方位是 **180° 周期**的。而莫尔圆上转一整圈是 360°。**180° 的实物周期 ↔ 360° 的图上周期，比例正是 2:1。**
3. **参数方程形式**（Slide 9 notes）：圆心在 x 轴上的圆的参数方程为 x = C ± r cos φ、y = ± r sin φ。把上面两条方程与之对照，**φ 就是 2θ**——即"莫尔圆上的圆心角"天然是实物角的两倍。

**实际操作口诀：图上转的角度 = 实物角度 × 2，转向相同（逆时针为正）。**

**（3）圆心与半径的物理含义**

| 量 | 表达式 | 物理含义 |
|---|---|---|
| **圆心** | $\left(\dfrac{\sigma_1+\sigma_3}{2},\;0\right)$ | **平面内的平均正应力**。它决定圆"坐在"横轴上的什么位置——即整体压得多狠。孔隙流体压力只改变它。 |
| **半径** | $\dfrac{\sigma_1-\sigma_3}{2}$ | **差异应力的一半**，也是**最大剪应力 τ_max**。它决定圆的大小——即偏应力有多强、岩石有多"想"破裂。 |
| **直径** | $\sigma_1-\sigma_3$ | **差异应力（differential stress）** |

📎 背景补充：这条对照直接呼应 Slide 15 的"平均应力 ↔ 体积变化 / 偏应力 ↔ 形状变化"：**圆心管体积、半径管形状**。也直接解释了 Slide 16：孔压只减正应力、不动剪应力 ⇒ **只动圆心、不动半径** ⇒ 圆整体左移、直径不变。

**（4）几个必须记住的验证关系**

- **θ = 0°（面法线平行 σ₁，即该面垂直于 σ₁）**：2θ = 0，σ_n = σ₁，τ = 0 —— 圆的最右点，是**主平面**。
- **θ = 90°（面法线平行 σ₃）**：2θ = 180°，σ_n = σ₃，τ = 0 —— 圆的最左点，也是**主平面**。
- **θ = 45°**：2θ = 90°，σ_n = (σ₁+σ₃)/2（= 平均应力），**τ = (σ₁−σ₃)/2 = τ_max** —— 圆的最高点。**最大剪应力出现在法线与 σ₁ 成 45° 的面上，也就是与 σ₁ 本身成 45° 的面上**（45° 时 θ = α，是唯一两者相等的角度）。
- **两个互相垂直的面**（θ 与 θ+90°）在莫尔圆上是**直径的两端**（2θ 相差 180°）。因此它们的 **σ_n 之和 = σ₁+σ₃ = σ_xx+σ_yy（迹不变量）**，**τ 大小相等、符号相反**。——这就是为什么画图时只要标出 (σ_xx, σ_xy) 和 (σ_yy, σ_yx) 两点，连线就是直径。

### 3.3 完整的莫尔图读法

**坐标轴**：横轴 = 正应力 σ_n（**向右为正 = 压**，地质约定）；纵轴 = 剪应力 τ（**向上为正 = 逆时针剪切力偶**）。

**一个点 = 一个面。**圆上每一点的坐标 (σ_n, τ) 就是某一方位的面上的正应力与剪应力。整个圆描述了 σ_n 与 τ 如何随面的方位**协同变化**（Slide 9 notes: "how σ_n and τ **co-vary** as the orientation of the plane is varied"）。

**两个方向的用法**（Slide 9 notes 明说）：
- **正向**：已知 σ₁ 与 σ₃ ⇒ 求任意面上的 σ_n 与 τ；
- **反向**：已知任意**两个**面上的 σ_n 与 τ ⇒ 求 σ₁ 与 σ₃。
- 老师的评语："This was very helpful in the days before calculators, and **remains very helpful now if you are not comfortable with matrix manipulation**."

**角度规则**：θ 从 σ₁ 点（圆的最右点）起算，**逆时针为正**，在图上量 **2θ**。

**孔隙流体压力**：把整个圆**向左平移 P_f**，半径不变。

**历史**：Christian Otto Mohr（1835–1918），德国土木工程师，1882 年提出该图解法。

### 3.4 三维莫尔图（Slide 14）

> "3D stress states may be shown on a Mohr diagram as **a set of nested circles**. This is helpful for **illustrating** particular stress states but when **calculating** the stress components on differently oriented planes it is **simpler to use the stress transformation equation**."

**三个圆的构成**（📎 背景补充：讲义只给了图与一个算例，未逐条列出三个圆的定义；下表为标准构造）：

| 圆 | 直径两端 | 代表的面族 |
|---|---|---|
| 大圆（外圈） | σ₃ 到 σ₁ | 包含 σ₂ 轴的面（σ₂ 平行于面） |
| 小圆之一 | σ₂ 到 σ₁ | 包含 σ₃ 轴的面 |
| 小圆之二 | σ₃ 到 σ₂ | 包含 σ₁ 轴的面 |

- **所有可能方位的面，其 (σ_n, τ) 都落在大圆之内、两个小圆之外的那片新月形阴影区内。**
- **τ_max = (σ₁ − σ₃)/2**，由**最大的那个圆**给出——所以在做破裂分析时只需要画 σ₁–σ₃ 那个大圆（这就是 W06 只画一个圆的原因）。
- 讲义给的算例：一个面 P，其**法线**与 σ₁、σ₂、σ₃ 轴分别成 **θ = 59.5°、φ = 55°、ψ = 50°**，在三维莫尔图上落在阴影区内的某一点。
- **警告**（notes）："Careful attention to the **signs of shear stresses / angles** is necessary"——三维图上三个嵌套圆必须**从同一方向观察**（见 `Handout(2).md` 的一致性判据）。
- **本课不要求掌握三维应力**：Slide 1 notes 明说 "you really don't need to worry about 3d stress at 2nd year level"。

### 3.5 本周其他需要记的公式汇总

| 公式 | 含义 | 出处 |
|---|---|---|
| $T = F/A$ | traction（面力强度） | Slide 3 |
| $T_n = (F/A_1)\cos^2\theta$，$T_s = (F/A_1)\sin\theta\cos\theta$ | traction 的法向/切向分量 | Slide 4 |
| $\sigma_{1,2} = \tfrac12(\sigma_{xx}+\sigma_{yy}) \pm \tfrac12[(\sigma_{xx}-\sigma_{yy})^2+4\sigma_{xy}^2]^{1/2}$ | 由任意坐标系分量求主应力 | Slide 8 |
| $\tan 2\theta = 2\sigma_{xy}/(\sigma_{xx}-\sigma_{yy})$ | 主应力方位 | Slide 8 |
| $\sigma_m = (\sigma_{11}+\sigma_{22}+\sigma_{33})/3$ | 平均应力 | Slide 15 |
| $\sigma' = \sigma - P_f$ | 有效应力（📎 补充自 Terzaghi） | Slide 16 |
| $\Phi = (\sigma_2-\sigma_3)/(\sigma_1-\sigma_3)$ | 应力比 | Slide 23 |
| $\sigma_v = \rho_{rock}\,g\,z$（≈ 26.5 MPa/km） | 铅直应力 | Slide 27 |
| $p_{fluid} = \rho_{fluid}\,g\,z$；$\lambda \equiv p_{fluid}/\sigma_v \approx 0.4$ | 孔压与孔压参数 | Slide 28 |
| $\sigma_H = [\nu/(1-\nu)]\,\sigma_v$ | 单轴应变参考态的水平应力 | Slide 29 |

---

## 四、课堂补充

> **说明：EART28202 全课 10 周均无 transcript（无课堂录音转写）。本段内容全部来自讲义幻灯片的 notes pane（老师写在备注栏里的补充说明与进一步阅读）以及 practical 答案中透露的作图规范与评分要点，不含任何课堂口头内容。**

### 4.1 老师在讲义里明确划定的"考不考"边界

这几条对复习的性价比极高：

1. **`StressNote.pdf` 的严格推导不考**（Slide 1 notes）："You do **NOT** need to know the contents of this document for this course."——但老师加了一句："anyone thinking of a career / further academic study in **rock mechanics or geophysics** will find that a sound understanding of stress is absolutely fundamental."
2. **三维应力不用担心**（Slide 1 notes）："you really don't need to worry about 3d stress at 2nd year level."（Slide 14 的三维莫尔图属于"理解性"内容。）
3. **碎裂变形/晶内塑性/扩散物质迁移这些术语不用担心**（Slide 37 notes）："You don't need to worry about these terms in this unit – they just refer to different ways in which the rock responds to stress."（详见 Optional PowerPoint。）
4. **Syllabus 的 teaching methods 部分说**：每周会在 Blackboard 上贴一份简短文件，**highlight 当周的关键材料以及可能的考法**。本周笔记无法替代那份文件，但下面 4.2/4.3 的内容基本就是它会点的东西。
5. **Feedback 部分明说**：Theory 笔试是"diagrammatic, short answer questions"，且会考"aspects that were developed in the practicals (e.g., **stress and strain analysis**)"。**换言之：莫尔圆是笔试会画的图。**

### 4.2 讲义 notes pane 里反复强调的注意事项

- **"逆时针为正"的方向依赖性**（Slide 5 notes 写了一整段，还教你用右手定则和转纸片自己验证）。结论：**"You'll not go wrong in this course unit if you simply remember anticlockwise = +ve."**
- **术语的严谨用法**（Slide 5 notes）："in **stress** we have **compression and tension**, while in **strain** shortening is **contraction** and lengthening is **extension**." 并且——**"extension can occur even when all stresses are compressive"**：只要某方向压得特别狠，与之高角度的方向就会伸长，前提是那些方向上的压应力相对较小。**这是构造地质学里最常被误解的一句话之一。**
- **Mohr 约定 ≠ 张量约定**（Slide 9 notes）："Note that the convention for assigning signs to the shear stresses outlined on Slide 5 must be used, **NOT the tensor convention**."——画莫尔圆时必须先把张量约定的矩阵**翻译成** Mohr 约定的两个点。
- **单位换算**（Slide 3 notes / Slide 28 notes）：1 kbar = 100 MPa 要背；p = ρgz 用 (g/cm³, m/s², km) 直接出 MPa。
- **图上量角与实物量角**（Slide 9 notes）：θ 在莫尔图上"plots as **anticlockwise (+ve) up**"。

### 4.3 从练习答案反推的作图规范与评分要点

`Ex1(6).md` 的 Method 部分把标准解题流程写成了 (a)(b)(c)(d) 四步，**这四步基本就是评分点**：

- **(a)** 画一个**方块单元（square element）**，按**张量符号约定**把应力箭头摆到正确方位。规则：**看切负坐标轴的那两个面**——分量为正就在该面上指向**正**坐标方向；为负就指向**负**坐标方向。
- **(b)** 判定各剪应力在 **Mohr 圆约定**下的正负（逆时针力偶 = +，顺时针力偶 = −）。
- **(c)** 画出 **(σ_xx, σ_xy)** 与 **(σ_yy, σ_yx)** 两个点，连线画圆，读出 σ₁ 与 σ₂；**并在方块单元图上用箭头画出 σ₁ 与 σ₂ 的正确方位**。
- **(d)** 找目标面：先把"面的方位"换算成"法线的方位"，再乘以 2 转到圆上，读出 σ_n 与 τ；**并在方块单元图上画出该面的正确方位，加一个"lazy arrow"（半箭头）表示剪切指向**。

**⇒ 两条隐含的评分要求：**
1. **答案不是两个数字，而是"两个数字 + 一张方块单元图"。**只算数不画方块，会丢一半分。
2. **必须显式写出你在两套符号约定之间的转换过程**（Ex3 的解答文字就是这么写的："The state of stress is presented in tensor sign convention, and so **first task is to determine the sign of the shear stresses using the Mohr circle convention**."）。

`Ex3soln(1).md` 还透露了两条：
- **每道图解题都要用公式复核**（题目本身设了 (b)(d) 两个 "Check your answers using the formulae" 小问）——**图解与代数必须互相印证**，这是老师期望的工作习惯。
- **tan 2θ 方程在 0–180° 内有两个解**（相差 90°，一个指向 σ₁、一个指向 σ₂），**选哪个有规则**："The rules for selecting the correct one are listed in the notes supporting the stress lecture (see also Jaeger et al., 2007, p.21)."——本题的判据是：σ_xx < σ_yy 且 σ_xy < 0（Mohr 约定）⇒ x 方向与 σ₁ 的夹角落在 **90°–135°** 之间。

`Ex4soln(1).md` 透露了一条**地质推理规范**：
- 判断滑动性质时，**两条独立证据要互相印证**："σ₁ is vertical and so from the **Andersonian** picture of faulting we expect the sense of slip on the fault to be **normal**. Note that this sense of slip **also follows from the sign of the shear stress** on the fault plane."

---

## 五、Practical 要点

**Practical 5: Stress analysis using Mohr's circle（syllabus 第 5 条）**。本周的 Lecture 与 Practical 主题完全吻合。

材料共 8 份：1 份符号约定 handout + 1 份题面（含 1a 详解）+ 6 份解答。**Ex2、Ex3、Ex4 的题面写在各自的解答文件开头。**

### 5.0 `Handout(2).md`：符号约定速查卡

这份 handout 不是题目，是一张**必须随身带的约定速查卡**。核心三块：

1. **示例矩阵**：(x, z) 坐标框下 $\begin{pmatrix}325 & 129.9\\129.9 & 175\end{pmatrix}$，配图展示 rock mechanics 与 engineering 两套画法（rock mechanics 全部 ij 为正、engineering 全部 ij 为正，但箭头方向不同）。
2. **两套正负约定**：
   - *rock mechanics*：压性正应力 σ_n 为 +；莫尔圆上**逆时针剪切力偶为 +**。
   - *engineering*：张性正应力 σ_n 为 +；莫尔圆上**顺时针剪切力偶为 +**。
   - **加粗声明："We will always use the rock mechanics definitions"**。
3. **两套剪应力符号约定的判定法**：
   - **张量约定**（矩阵中 σ_xz 与 σ_zx **同号**时隐含使用）：岩石力学中看**切负坐标轴的那些面**，"**+ve stresses point in a positive coordinate direction on those sides**"；工程界（张为正）则改看**切正坐标轴**的面。
   - **Mohr 圆约定**（矩阵中 σ_xz 与 σ_zx **异号**时隐含使用）：两个剪应力必然一正一负；岩石力学中逆时针为正。
   - **方向依赖与一致性判据**：见 §2.4。2D 练习不受影响，**3D 莫尔图受影响**。

### 5.1 Exercise 1（`Ex1(6).md` + 三份解答）

**题面**：给出四个应力状态（单位 MPa，**x 向右、y 向上**，即画图的常规摆法）。对每一个：
1. **用画莫尔图的方法**求主应力 σ₁ 与 σ₂；
2. 用莫尔图求**与 σ₁ 成 30° 逆时针夹角的那个面**上的正应力 σ_n 与剪应力 τ。

四个矩阵（张量约定）：

$$\text{(a)}\begin{pmatrix}50&20\\20&40\end{pmatrix}\quad \text{(b)}\begin{pmatrix}50&20\\20&-40\end{pmatrix}\quad \text{(c)}\begin{pmatrix}50&-20\\-20&40\end{pmatrix}\quad \text{(d)}\begin{pmatrix}0&-40\\-40&80\end{pmatrix}$$

**题面给的方法（四步，见 §4.3）**，其中第 (d) 步的角度换算写得极其清楚，值得逐字记住：

> "For the plane at **30° anticlockwise to σ₁** note that **the normal is 90° − 30° = 60° clockwise to σ₁**. Hence draw a line at **2 × 60° = 120° clockwise** to σ₁ to find the point on the Mohr circle."

以及一条提示：从张量矩阵读点时，
> x-direction: σ_n = σ_xx；τ = ± σ_xy　　y-direction: σ_n = σ_yy；τ = ± σ_yx
> **"sign of shear stress needs to be determined"**

**四题结果汇总（材料答案 / 我的独立复算）：**

| 题 | 材料给的 σ₁, σ₂ | 我复算的 σ₁, σ₂ | 材料给的角度 | 我复算（σ₁ 相对 x 轴，逆时针为正） | 材料给的 (σ_n, τ) | 我复算的 (σ_n, τ) |
|---|---|---|---|---|---|---|
| (a) | 65.6, 24.4 | **65.616, 24.384** ✓ | 2θ = −76°，θ = −38° | σ₁ 在 x 轴 **逆时针 +37.98°** ✓ | (34.7, −17.8) | **(34.692, −17.854)** ✓ |
| (b) | 54.2, −44.2 | **54.244, −44.244** ✓ | 2θ = −24°，θ = −12° | σ₁ 在 x 轴 **逆时针 +11.98°** ✓ | (−19.6, −42.6) | **(−19.622, −42.647)** ✓ |
| (c) | 65.6, 24.4 | **65.616, 24.384** ✓ | 2θ = +76°，θ = +38° | σ₁ 在 x 轴 **顺时针 37.98°** ✓ | (34.7, −17.8) | **(34.692, −17.854)** ✓ |
| (d) | 96.6, −16.6 | **96.569, −16.569** ✓ | 2θ = −45°，θ = −22.5°（**量到 y 方向**） | σ₁ 在 x 轴 **逆时针 112.5°**，即在 y 轴逆时针 **+22.5°** ✓ | (11.7, −49) | **(11.716, −48.990)** ✓ |

**全部吻合，未发现数值错误。**（复算方法：圆心 C = (σ_xx+σ_yy)/2，半径 R = ½√[(σ_xx−σ_yy)² + 4σ_xy²]；主应力方位用矩阵特征向量独立验证；(σ_n, τ) 用 2θ = −120° 代入 §3.1 两条方程。）

**逐题的符号判定过程（这才是本练习真正在练的东西）：**

**(a)** $\begin{pmatrix}50&20\\20&40\end{pmatrix}$
- 张量约定：σ_xy = +20 ⇒ 在**切负 x 轴的面（左面）**上箭头指向 **+y（向上）**；σ_yx = +20 ⇒ 在**切负 y 轴的面（下面）**上箭头指向 **+x（向右）**。
- 转成 Mohr 约定：作用在 x 面（左右两面）上的那对剪应力形成**顺时针**力偶 ⇒ **σ_xy = −20**；作用在 y 面（上下两面）上的那对形成**逆时针**力偶 ⇒ **σ_yx = +20**。
- 画点：**x 方向点 (50, −20)**，**y 方向点 (40, +20)**。连线得直径，圆心 (45, 0)，半径 20.62。
- **σ₁ = 65.6，σ₂ = 24.4**。x 方向点相对圆心的角度为 −76°，即 **2θ = −76°，θ = −38°**（从 σ₁ 顺时针 38° 到 x 方向；等价地 σ₁ 在 x 轴逆时针 38°）。
- 第 (d) 步：从 σ₁ 点**顺时针转 120°**（2θ = −120°），读出 **(34.7, −17.8)**。τ 为负 ⇒ **顺时针剪切**（解答图上明确标注 "−ve shear stress (clockwise shear sense)"）。

**(b)** $\begin{pmatrix}50&20\\20&-40\end{pmatrix}$
- 与 (a) 的符号判定完全相同（σ_xy 张量为 +）：**x 方向点 (50, −20)**，**y 方向点 (−40, +20)**。
- 注意 σ_yy = −40 是**张性**（负 = 拉），所以 y 方向点落在 σ_n 轴的**负半轴**上。圆心 (5, 0)，半径 49.24。
- **σ₁ = 54.2，σ₂ = −44.2**（σ₂ 为负 ⇒ 最小主应力是张性的）。**2θ = −24°，θ = −12°**。
- (d)：2θ = −120° ⇒ **(−19.6, −42.6)**。σ_n 为负 ⇒ 该面上是**张应力**；τ 为负 ⇒ 顺时针剪切。

**(c)** $\begin{pmatrix}50&-20\\-20&40\end{pmatrix}$
- 张量 σ_xy = −20 ⇒ 在切负轴的面上箭头指向**负**坐标方向（解答图上写 "shear sense on −ve axis side in **−ve** direction"）。
- 转 Mohr：**符号与 (a) 完全相反**——**x 方向点 (50, +20)**，**y 方向点 (40, −20)**。
- 圆与 (a) 完全相同（σ₁ = 65.6，σ₂ = 24.4），但**方位镜像**：**2θ = +76°，θ = +38°**，σ₁ 位于 x 轴**顺时针** 38° 处。
- (d)：仍从 σ₁ 点顺时针转 120°，读出**同样的 (34.7, −17.8)**。
- **(a) 与 (c) 的对照是本题组的精髓**：剪应力变号，主应力**大小不变**、**方位镜像翻转**。

**(d)** $\begin{pmatrix}0&-40\\-40&80\end{pmatrix}$
- σ_xx = 0（x 方向完全没有正应力），σ_yy = 80。张量 σ_xy = −40 ⇒ Mohr：**x 方向点 (0, +40)**，**y 方向点 (80, −40)**。
- 圆心 (40, 0)，半径 56.57。**σ₁ = 96.6，σ₂ = −16.6**。
- 因为 σ_yy ≫ σ_xx，σ₁ 靠近 **y** 方向，所以解答里的角度是从 σ₁ **量到 y 方向**的：**2θ = −45°，θ = −22.5°**（σ₁ 在 y 轴逆时针 22.5° 处；相对 x 轴则是逆时针 112.5°）。
- (d)：2θ = −120° ⇒ **(11.7, −49)**。**注意 τ 的绝对值（49）比 σ_n（11.7）大得多**——这是一个高剪切、低正应力的面。

### 5.2 Exercise 2（`Ex2soln(1).md`）

**题面**：笛卡尔坐标框 (x, z)（**z 是深度方向**）中给定应力状态（MPa）：

$$\begin{pmatrix}100&40\\40&30\end{pmatrix}$$

**(a)** 在给出的若干个方块上（每个方块所配的坐标框方位不同），画出 σ_n 与 τ 的方向箭头；并在每种情形下用 **Mohr 符号约定**判定 σ_xz 的正负。

- **这一小问的全部意义就是让你亲手验证 §2.4 的那句话：Mohr 约定的正负依赖于坐标框在纸面上的摆法。**解答图里，随着坐标框翻转，同一个 σ_xz 在 "**+ve (anticlockwise)**" 与 "**−ve (clockwise)**" 之间交替；而张量约定下的箭头画法始终按同一条规则（看切负轴的面）得出。

**(b)** 为下面两个应力状态画莫尔圆，并在方块单元上标出 σ₁ 的方向：

$$\begin{pmatrix}100&40\\40&30\end{pmatrix} \qquad \text{与} \qquad \begin{pmatrix}100&-40\\-40&30\end{pmatrix}$$

**第一个**（σ_xz 张量为 +40）：解答判定 **σ_xz 在 Mohr 约定下为 +（逆时针）**，画点 **x 方向 (100, +40)**、**z 方向 (30, −40)**。图上标注 **2θ = 49°**、实物角 **24.5°**。

> ⚠️ **注意这里与 Ex1 的差别**：同样是张量 σ_xy = 正，Ex1（y 轴向上）得到的 x 方向点在**下方**（Mohr 为负），Ex2（z 轴向下）得到的 x 方向点在**上方**（Mohr 为正）。**原因就是第二根轴翻转了。**（见 §2.4 的 📎 背景补充。）

**第二个**（σ_xz 张量为 −40）：符号镜像，**x 方向 (100, −40)**、**z 方向 (30, +40)**，角度变成 **−49° / −24.5°**。

**📎 我的复算（材料的解答图中没有印出主应力的数值，只标了角度）：**
- 圆心 C = (100+30)/2 = **65**；半径 R = ½√[(100−30)² + 4×40²] = ½√11300 = **53.15**
- **σ₁ = 118.2 MPa，σ₂ = 11.8 MPa**（第一、第二个状态相同）
- 角度：tan 2θ = 2×40/(100−30) = 1.143 ⇒ **2θ = 48.81°，θ = 24.41°**——与材料标注的 49° / 24.5° 吻合（材料是图上量出来的，取整合理）✓
- 特征向量独立验证：σ₁ 的方向向量在 (x, z) 分量下 ∝ (1, 0.454)，即偏离 x 轴 **24.4° 朝 +z（向下）** ✓，与解答图上把 σ₁ 箭头画成从 x 轴向下偏 24.5° 一致。

### 5.3 Exercise 3（`Ex3soln(1).md`）——本周最完整的一题

**题面**：笛卡尔坐标框 (x, y) 中给定应力状态（MPa）：

$$\begin{pmatrix}7&19\\19&36\end{pmatrix}$$

**(a) 用莫尔图求 σ₁、σ₂ 以及 σ₁ 与 x 方向之间的夹角 θ。**

解答的文字步骤（值得逐字模仿，因为这就是标准答题格式）：

> "The state of stress is presented in **tensor sign convention**, and so first task is to determine the sign of the shear stresses using the **Mohr circle convention**. We draw a square element and orient the stresses in an (x, y) coordinate frame, noting that since the shear stresses are positive, for any given shear couple, **on the side that cuts the negative axis the shear stress should be going in a positive direction**. We then determine the sign of the shear stresses in Mohr circle convention (for given shear couple, **clockwise is negative and anticlockwise is positive**)."

- 转换结果：**σ_yy = 36, σ_yx = +19（逆时针）**；**σ_xx = 7, σ_xy = −19（顺时针）**。
- 画点：**x 方向 (7, −19)**、**y 方向 (36, +19)**。
- **材料答案：σ₁ = 45.4 MPa，σ₂ = −2.4 MPa，2θ = 232.65°，θ = 116.3°。**
- **我的复算**：C = 21.5，R = ½√[(7−36)² + 4×19²] = ½√2285 = **23.901** ⇒ **σ₁ = 45.401，σ₂ = −2.401** ✓；x 方向点 (7, −19) 相对圆心的方位角 = atan2(−19, −14.5) = **232.65°** ✓，θ = **116.33°** ✓。**完全吻合。**
- 注意 **σ₂ = −2.4 为负** ⇒ 最小主应力是**张性**的，圆略微越过 σ_n = 0 进入张性区。

**(b) 用公式核对 (a)。**

（解答文件里"With ... then ..."之间的数值图未被提取出来，但公式就是 Slide 8 的那两条。）
- $\sigma_{1,2} = \tfrac12(7+36) \pm \tfrac12[(7-36)^2 + 4(19)^2]^{1/2} = 21.5 \pm 23.90$ ⇒ **45.4 / −2.4** ✓
- $\tan 2\theta = \dfrac{2\sigma_{xy}}{\sigma_{xx}-\sigma_{yy}} = \dfrac{2(-19)}{7-36} = \dfrac{-38}{-29} = 1.3103$ ⇒ 2θ = 52.65° 或 232.65° ⇒ **θ = 26.3° 或 116.3°**

**⭐ 选根规则（这是本题最有价值的一句话）：**

> "note that in the range 0–180° there are **two values of θ** that satisfy the tan 2θ equation (one finds the angle to σ₁ and the other to σ₂). These differ by 90° (26.3 + 90 = 116.3°). The rules for selecting the correct one are listed in the notes supporting the stress lecture (see also **Jaeger et al., 2007, p.21**). In this case **σ_xx < σ_yy and σ_xy < 0 (Mohr circle sign convention) and so the angle between the x-direction and σ₁ lies between 90° and 135°**. Hence **116.3°** is the correct solution."

📎 背景补充：不背 Jaeger 的判据表也没关系——**画一张草图就能自己判断**。σ_yy = 36 ≫ σ_xx = 7，所以 σ₁ **必然靠近 y 方向**（离 x 方向远），θ 必须大于 45°，于是只能是 116.3° 而不是 26.3°。**"哪个正应力大，σ₁ 就更靠近哪个轴"** 是万能的定性检验。

**(c) 用莫尔图求「与 x 方向成 30° 逆时针」的那个面上的 σ_n 与 τ。**

注意题目这次给的是**面相对 x 方向**的角度（不是相对 σ₁）。解答图上的角度链条是：

- 面在实物上位于 x 方向逆时针 **30°** ⇒ 该面的**法线**在 x 方向 **−60°**（图上标 "α = −60°"）
- 换到莫尔图上：**从 x 方向点起，转 2α = −120°**（图上标 "2α = 120°"）
- x 方向点本身在 σ₁ 点起算的 **232.65°** 处 ⇒ 目标点在 **232.65° − 120° = 112.65°** 处（图上标 "2θ = 112.65°"，即 **θ = 56.33°**）
- **材料答案：σ_n = 12.3 MPa，τ = +22.1 MPa**（τ 为正 ⇒ **逆时针剪切**）
- **我的复算**：σ_n = 21.5 + 23.901·cos(112.65°) = 21.5 − 9.20 = **12.296** ✓；τ = 23.901·sin(112.65°) = **22.057** ✓。**吻合。**

**验证角度链条的自洽性**：σ₁ 在 x 方向逆时针 −116.3°（等价 +63.7°）；面法线在 x 方向 −60°；所以从 σ₁ 到面法线 = 116.3° + (−60°) = **56.3° = θ** ✓，2θ = 112.65° ✓。

**(d) 用公式核对 (c)。**代入 §3.1 两条方程，2θ = 112.65°，同上。

**(e) 用特征值/特征向量求 σ₁、σ₂ 与 θ。**

这一小问把 Slide 13 的"应力是张量、主应力是特征值"落到实处：

- 求解 **Av = λv**，改写为 **(A − λI)v = 0**；非零特征向量要求 **|A − λI| = 0**。
- 展开行列式得二次方程，用求根公式解出两个 λ ⇒ **λ = 45.4 与 −2.4**（即 σ₁ 与 σ₂）。
- 求 λ = 45.4 对应的特征向量：解答给出 **v = (1, 2.02)**，并做了验算：
  $\begin{pmatrix}7&19\\19&36\end{pmatrix}\begin{pmatrix}1\\2.02\end{pmatrix} = \begin{pmatrix}45.4\\91.7\end{pmatrix} = 45.4\begin{pmatrix}1\\2.02\end{pmatrix}$ ✓
  （我的复算：(7 − 45.401)·1 + 19·v₂ = 0 ⇒ v₂ = 38.401/19 = **2.0211** ✓；19·1 + 36·2.0211 = 91.76 ✓）
- 转成角度：**tan θ = 2.02/1 ⇒ θ = 63.7°**；解答再写 **"or from σ₁ clockwise to x-direction, θ = 180 − 63.7 = 116.3°"**。
- **λ = −2.4 对应的特征向量与之成 90°。**

📎 背景补充：63.7° 与 116.3° 之和恰为 180°，这不是巧合——主应力**轴**是一条线（双向），从它量到 x 方向，顺时针量得 63.7°、逆时针量得 116.3°，是同一个几何关系的两种读法。**莫尔图给出的 116.3° 与特征向量给出的 63.7° 完全等价**，只是量角的方向相反。答题时**务必写清楚"从哪儿量到哪儿、顺时针还是逆时针"**。

### 5.4 Exercise 4（`Ex4soln(1).md`）——把莫尔圆用到真实断层上

**题面**（逐字）：

> "If the state of stress at a point is **σ_xx = 75 MPa, σ_zz = 125 MPa, and σ_zx = 0**, where **z is depth, and the x axis points eastwards**, what are the **normal and shear stresses on a fault plane oriented 000/55W** that passes through the same point? **What sense of slip** might be expected? Given that the orientation of the x and z axes have been defined as they are, **why is the strike of the fault important** in this question?"

**解答链条：**

1. **σ_zx = 0 ⇒ σ_zz 与 σ_xx 本身就是主应力**（剪应力为零的面即主平面）。
2. **σ_zz (125) > σ_xx (75) ⇒ σ_zz = σ₁（铅直），σ_xx = σ₃（东西向水平）。**
3. 莫尔圆：**圆心 (100, 0)，半径 25**（差异应力 = 50 MPa）。
4. 断层产状 **000/55W**：走向正南北，向西倾 55°。**断层面的法线与铅直方向（σ₁）成 55°** ⇒ **θ = 55°，2θ = 110°**。
5. **读出 (σ_n, τ) = (91.45, 23.49) MPa。**
6. **我的复算**：σ_n = 100 + 25·cos(110°) = 100 − 8.551 = **91.449** ✓；τ = 25·sin(110°) = **23.492** ✓。**完全吻合。**
7. **滑动性质**："σ₁ is vertical and so from the **Andersonian** picture of faulting we expect the sense of slip on the fault to be **normal**（正断层）. Note that this sense of slip **also follows from the sign of the shear stress** on the fault plane."（τ 为正 = 逆时针，与该几何下的正断滑动一致。）
8. **为什么走向重要**："The strike of the fault is important because it means that **the fault plane contains the intermediate principal stress, σ₂**, and so we can treat this **three dimensional stress problem as a two dimensional one**."

**⇒ 这一问是全周最重要的"思想"题**：三维问题之所以能降维成二维莫尔圆，前提是**所考察的面包含 σ₂**（即 σ₂ 平行于断层走向）。断层走向 000（南北），而 x 轴指东、z 轴向下，所以 x–z 平面就是 E–W 铅直剖面，断层面与之垂直相交、其法线正好落在 x–z 平面内。**若断层走向不是南北，就必须用三维应力变换，不能只画一个圆。**

📎 背景补充：顺带做一个对照——在这个应力状态下，**最大剪应力 τ_max = 25 MPa，出现在倾角 45° 的面上**（θ = 45°，2θ = 90°）。而题中 55° 倾角的断层只有 τ = 23.49 MPa，略小。**但 Anderson 预测的正断层倾角恰恰就是约 60°，而不是"最大剪应力面"的 45°**——原因是真正的破裂面由**内摩擦角**（Coulomb 准则）控制，需要在 τ 与 σ_n 之间权衡（σ_n 越小越容易滑动）。这是 **W06 的核心内容**，本周只需知道"最大剪应力面 ≠ 破裂面"。

### 5.5 通用操作步骤：给定 σ₁、σ₃ 与面的方位 → 求该面上的 σ_n 与 τ

把上面所有题归纳成一套可以照做的流程：

**情形 A：题目直接给主应力**（如 Ex4）

1. 确认 σ₁ 与 σ₃ 的**大小与方位**（若给的是"σ_zx = 0"这类信息，说明坐标轴就是主轴）。
2. 计算圆心 C = (σ₁+σ₃)/2 与半径 R = (σ₁−σ₃)/2；在 σ_n–τ 坐标上画圆。
3. 找出**目标面的法线**（不是面本身！），量出它与 **σ₁** 的夹角 **θ**（逆时针为正）。
   - 若题目给的是"面与 σ₁ 成 α"，则 **θ = 90° − α**（或 α − 90°，取决于转向）。
   - 若题目给的是产状（走向/倾角），先确认**面包含 σ₂**，再在剖面上量法线与 σ₁ 的夹角。
4. 在图上从 **σ₁ 点（圆最右点）** 起，按 **2θ**、同向（逆时针为正）转到圆上一点。
5. 读出该点坐标 = **(σ_n, τ)**。
6. **代数复核**：σ_n = C + R cos2θ，τ = R sin2θ。
7. **回到方块/剖面图**上画出该面、标出 σ_n 与 τ 的箭头，τ 的正负决定"lazy arrow"的指向（正 = 逆时针）。

**情形 B：题目给任意坐标系下的应力矩阵**（如 Ex1、Ex2、Ex3）

1. **先辨认约定**：矩阵中 σ_xy 与 σ_yx **同号** ⇒ 张量约定；**异号** ⇒ 已是 Mohr 约定。
2. **画方块单元**，按张量约定摆箭头（看切**负**坐标轴的两个面，正分量指向**正**坐标方向）。
3. **判定 Mohr 符号**：每一对剪应力力偶，**逆时针 = +，顺时针 = −**。（务必看清第二根轴朝上还是朝下！）
4. **画两个点**：(σ_xx, σ_xy) 与 (σ_yy, σ_yx)——它们是**直径的两端**。连线交 σ_n 轴于圆心，画圆。
5. **σ₁ = C + R，σ₃(或 σ₂) = C − R**。
6. 量 **2θ**：从 σ₁ 点逆时针量到 **x 方向点**，除以 2 得实物角 θ。**定性检验**：σ_xx 与 σ_yy 哪个大，σ₁ 就更靠近哪根轴。
7. 之后接情形 A 的第 3–7 步。

---

## 六、易错点 / 重点难点

### ⭐ 头号易错点：θ 的定义

**θ 是「σ₁ 方向」与「该面的法线（pole）」的夹角，不是 σ₁ 与「面本身」的夹角。**

- 讲义 Slide 10 专门为此开了一页，指出很多老一辈的岩石力学教科书用的是 **α**（σ₁ 与面本身的夹角，"arguably more intuitive"），并明确宣布："**Throughout this course we will use the mathematically more conventional version**"（即 θ）。
- **两者相差 90°：α = 90° − θ。**记混了，σ_n 与 τ 会整个对调（cos 变 sin）：θ = 0 时 τ = 0、σ_n = σ₁；若误当成 α = 0，那实际上是 θ = 90°，会得到 σ_n = σ₃。**这是把最大值算成最小值的量级错误。**
- **自检办法**：算完后代 θ = 0 检查——**σ_n 必须等于 σ₁ 且 τ 必须等于 0**。
- Ex1 的题面把这个换算写死了："For the plane at 30° anticlockwise to σ₁ note that **the normal is 90° − 30° = 60° clockwise** to σ₁"——**做题时先把"面"翻译成"法线"，再动手。**

### ⭐ 第二易错点：图上角度 = 实物角度 × 2，且**同向**

- 图上量 **2θ**，实物量 **θ**。**倍数关系记反（在图上量 θ）是最常见的低级错误。**
- **转向相同**：图上逆时针为正、实物也逆时针为正（在 x 右、y 上的常规摆法下）。
- **90° 的实物角 ↔ 180° 的图上角**：两个互相垂直的面在圆上是**直径两端**。
- **180° 的实物角 ↔ 360° 的图上角**：转一整圈回到原面。

### ⭐ 第三易错点：最大剪应力面 ≠ 破裂面

- 莫尔圆的最高点（**2θ = 90°，即 θ = 45°**，法线与 σ₁ 成 45°，面本身也与 σ₁ 成 45°）给出 **τ_max = (σ₁−σ₃)/2**。
- **但真实岩石不在 45° 面上破裂。**Anderson 分类里共轭断层是以 **±30°** 交于 σ₁ 的（Slide 32 notes），正断层倾角约 60°、逆断层约 30°。
- **原因**：破裂不只看 τ 大不大，还要看 σ_n（正应力压得越紧越难滑动）。真正的判据是 **Coulomb 破裂准则**，由**内摩擦角（angle of internal friction）**控制，**W06 讲**。
- **Ex4 就是活教材**：τ_max = 25 MPa 在 45° 面上，而题中 55° 倾角断层上 τ = 23.49 MPa——略小，但那才是自然界发生的。

### ⭐ 第四易错点：压应力符号约定

- **地质学 / 岩石力学：压为正**（因为地球内部以压应力为主）。
- **工程力学：张为正**（因为工程师关心抗张破坏）。
- **本课永远用岩石力学约定**（`Handout(2).md` 加粗声明）。
- **后果**：σ₁ ≥ σ₂ ≥ σ₃ 中，**σ₁ 是"压得最狠"的方向**，σ₃ 是"压得最轻"（甚至张性）的方向。Ex1(b)、Ex1(d)、Ex3 中出现的**负的 σ₂ 就意味着张应力**。
- **不要在同一份卷子里混用两套约定。**读外文文献（尤其工程/土木文献）时要先确认对方用哪套。

### ⭐ 第五易错点：两套剪应力约定（Mohr vs 张量）

- **张量约定**：矩阵对称（σ_xy = σ_yx），数学方便，题目给的矩阵**通常是这一套**。
- **Mohr 圆约定**：一正一负（σ_xy = −σ_yx），**画莫尔圆必须用这一套**。
- Slide 9 notes 加粗警告："the convention for assigning signs to the shear stresses outlined on Slide 5 must be used, **NOT the tensor convention**."
- **⇒ 拿到矩阵的第一件事：把张量约定翻译成 Mohr 约定，并在卷面上写出翻译过程**（Ex3 的解答开头就是这么写的，见 §5.3）。

### ⭐ 第六易错点：第二根坐标轴朝哪儿

- **Ex1 用 (x, y)、y 轴向上；Ex2 用 (x, z)、z 是深度、向下。**
- **同样是张量 σ_xy = +40，在 Ex1 里换算成 Mohr 是负，在 Ex2 里是正。**
- 因为"逆时针"是相对纸面观察方向定义的，翻转一根轴就翻转旋转感（Slide 5 notes 教你转一张纸自己验证）。
- **地质题几乎都用 z 向下（深度），务必留神。**
- `Handout(2).md` 的一致性判据：**从"平行于最大正应力分量的正坐标轴"顺时针转到"平行于最小正应力分量的正坐标轴"**——若不是这样，就翻转坐标轴。（2D 不影响答案，3D 必须遵守。）

### ⭐ 第七易错点：有效应力的方向

- **σ' = σ − P_f：孔隙流体压力是「减」的，圆向「左」移。**
- 直观理解：孔隙流体**把岩石撑开**，抵消了一部分把岩石压紧的正应力 ⇒ 有效正应力**变小** ⇒ 圆心左移 ⇒ 圆更靠近破裂包络线 ⇒ **更容易破裂**（这就是水力压裂能奏效的原因）。
- **剪应力完全不受影响** ⇒ **半径不变**。记成"圆整体平移、不缩不胀"。
- 若记成右移，W06 的整套结论（超压促进断层活动、注水诱发地震）会全部反过来。
- 相关：Slide 28 说孔压**不能超过岩静压力**，否则有效压力变成张性，而岩石抗张很弱，会直接破裂。

### 其他值得注意的点

- **tan 2θ 方程有两个解**（相差 90°，一个指向 σ₁、一个指向 σ₂）。**定性检验：σ_xx 与 σ_yy 哪个大，σ₁ 就更靠近哪根轴。**（Ex3 中 σ_yy = 36 ≫ σ_xx = 7，所以 θ = 116.3° 而不是 26.3°。）
- **"分解力"与"分解 traction"不是一回事**（Slide 4 notes）：F_n = F cos θ 但 T_n = T cos²θ。**因为面积 A₂ = A₁/cos θ 也随方位变。**
- **一般情况下 traction 向量既不平行于力向量，也不垂直于它所作用的面。**
- **应力状态的完整信息在 2D 是四个数、3D 是九个数（对称后为六个独立数）**，不是"一个应力值"。
- **"全部为压应力时仍然可以发生伸长"**（Slide 5 notes）——压/张说的是应力，缩短/伸长说的是应变，两者不能混谈。
- **平均应力通常远大于偏应力，但决定构造形态的是偏应力**（Slide 15）。
- **答题必须画方块单元图**（Ex1 method 的 (c)(d) 两步都要求在方块上标 σ₁/σ₂ 方位、面的方位与剪切指向），只写数字要丢分。
- **图解答案要用公式复核**（Ex3 专门设了 (b)(d) 两小问做这件事）。
- **θ 的答案要写清"从哪儿量到哪儿、顺时针还是逆时针"**（Ex3(e) 的 63.7° 与 116.3° 是同一答案的两种量法）。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| body force | 体力 | 超距作用于所有体元的力（重力、电磁力）；大小正比于质量/体积 |
| surface force | 面力 | 通过界面由一物体（或一部分）作用于另一物体（或另一部分）的力；大小正比于面积。**应力概念的来源** |
| traction (T) | 面力强度 / 牵引力 | T = F/A，力的**强度**；单位 Pa（= N m⁻²）；严格定义为 A→0 的极限 |
| Pascal (Pa) | 帕斯卡 | 1 Pa = 1 N m⁻²；1 MPa = 10⁶ Pa；**1 kbar = 100 MPa** |
| stress | 应力 | 描述通过一点的**所有方位**的面上的力强度的量（张量） |
| normal stress (σ_n) | 正应力 | traction 垂直于面的分量；**地质约定压为正** |
| shear stress (τ) | 剪应力 | traction 平行于面的分量；**Mohr 约定逆时针力偶为正** |
| stress ellipse | 应力椭圆 | 2D 中所有方位的面上 traction 向量尾端连成的椭圆 |
| stress ellipsoid | 应力椭球 | 3D 版本，又称 **Lamé 应力椭球**；三根轴 = 三个主应力 |
| principal stress | 主应力 | 剪应力为零的方向上的正应力；σ₁ ≥ σ₂ ≥ σ₃ |
| σ₁ / σ₂ / σ₃ | 最大 / 中间 / 最小主应力 | 分别是椭球的最长 / 中间 / 最短轴 |
| principal plane of stress | 主应力面 | **其上剪应力为零**的面；traction 平行于面法线 |
| pole / normal to plane | 面的极点 / 法线 | **θ 就是从 σ₁ 量到它的角度** |
| stress tensor / matrix | 应力张量 / 应力矩阵 | 2D 为 2×2（4 个数），3D 为 3×3（9 个数）；主对角线为正应力 |
| eigenvalue / eigenvector | 特征值 / 特征向量 | **主应力的大小 = 特征值；主应力的方位 = 特征向量** |
| tensor sign convention | 张量符号约定 | 看切**负**坐标轴的面；使矩阵**对称**（σ_xy = σ_yx） |
| Mohr circle convention | 莫尔圆符号约定 | 逆时针剪切力偶为正；使 σ_xy = −σ_yx；**画莫尔圆必须用它** |
| Mohr diagram / Mohr circle | 莫尔图 / 莫尔圆 | 横轴 σ_n、纵轴 τ；圆上一点 = 一个面；**图上 2θ = 实物 θ** |
| mean stress (σ_m) | 平均应力 | (σ₁₁+σ₂₂+σ₃₃)/3；对应**体积变化（dilation）**；= 莫尔圆圆心 |
| deviatoric stress | 偏应力 | 应力张量减去平均应力部分；对应**形状变化（distortion）**；**决定构造形成** |
| differential stress (σ₁−σ₃) | 差异应力 | = 莫尔圆**直径**；(σ₁−σ₃)/2 = **半径 = τ_max** |
| hydrostatic / lithostatic / isostatic stress | 静水 / 岩静 / 等静应力 | σ₁ = σ₂ = σ₃，椭球退化为球；lithostatic 用于岩石、hydrostatic 用于流体 |
| confining pressure | 围压 | 由埋深与上覆岩柱密度控制；量级与平均应力相当 |
| pore fluid pressure (P_f) | 孔隙流体压力 | **对抗正应力、不影响剪应力** |
| effective stress (σ′) | 有效应力 | σ′ = σ − P_f；**莫尔圆整体左移、直径不变** |
| over-pressure | 超压 | p_fluid > ρ_fluid g z；用 **λ = p_fluid/σ_v > 0.4** 度量；不能超过岩静压力 |
| pore pressure parameter (λ) | 孔压参数 | λ ≡ p_fluid/σ_v；连通到地表时 ≈ ρ_fluid/ρ_rock ≈ 0.4 |
| stress ratio (Φ) | 应力比 | Φ = (σ₂−σ₃)/(σ₁−σ₃) |
| borehole breakout | 钻孔崩落 | 井壁压缩破坏；**平行于 σ_h（垂直于 σ_H）** |
| overcoring | 套芯解除 | 应变松弛法；用应变片测卸载变形；限于几十米深 |
| strain gauge | 应变片 | 金属丝，由电阻变化反推应变 |
| hydraulic fracturing / hydrofracking | 水力压裂 | 封隔器 + 泵压；裂缝**平行于 σ_H**；维持张开的压力 = **σ_h** |
| packer | 封隔器 | 密封一段井筒的可充气橡胶塞 |
| earthquake first motion | 地震初动 | 由初动方向反演主应力方位与 Φ |
| palaeostress | 古应力 | 由变形显微构造反推的古代应力 |
| mechanical twin / deformation lamellae | 机械双晶 / 变形纹 | 方解石双晶、石英变形纹——主应力**方位**的指示物 |
| piezometer | 应力计 | 由位错密度（**增**）、亚晶粒直径（**减**）、动态重结晶粒径（**减**）标定应力**大小** |
| dislocation | 位错 | 晶格中多余半原子面的边缘 |
| σ_H / σ_h | 最大 / 最小水平应力 | |
| σ_v | 铅直应力 | σ_v = ρ_rock g z；大陆约 **26.5 MPa/km** |
| Poisson's ratio (ν) | 泊松比 | 岩石约 0.25–0.33 |
| Young's modulus (E) | 杨氏模量 | |
| uniaxial strain reference state | 单轴应变参考态 | 无侧向应变；σ_H = [ν/(1−ν)]σ_v ≈ (1/2 ~ 1/3)σ_v |
| reference state | 参考态 | 无构造应力时应力随深度的分布，是加构造应力的起点 |
| tectonic stress | 构造应力 | 偏离参考态的部分，主要来自构造过程 |
| Andersonian classification | Anderson 分类 | 按**哪个主应力铅直**分为伸展 / 走滑 / 挤压三种体制 |
| conjugate fractures | 共轭裂隙 | 以 **±30° 交于 σ₁** 形成，σ₂ 在断层面内 |
| transtension / transpression | 转张 / 转压 | Anderson 方案的后续扩展 |
| stylolite | 应力柱 / 缝合线 | 可指示主应力方位 |
| residual stress | 残余应力 | 热失配、压缩性差异、位错、结晶、变质反应体积变化引起，变形后仍残留 |
| World Stress Map | 世界应力图 | 全球应力测量数据库；对应板片拉力 / 洋脊推力 / 碰撞阻力 / 基底拖曳四大板块力 |
| constitutive equation | 本构方程 | 把材料参数与温度、应力、应变速率联系起来；取 (σ₁−σ₃) 最小者适用 |
| cataclastic deformation | 碎裂变形 | 浅部脆性破裂机制；**基本与岩性无关 → Byerlee 定律（Class 7）** |
| intracrystalline plasticity / diffusive mass transfer | 晶内塑性 / 扩散物质迁移 | 深部塑性流动的两类机制 |
| jelly sandwich / crème brûlée / banana split | 三明治 / 焦糖布丁 / 香蕉船（模型） | 大陆岩石圈强度–深度剖面的三种流行模型 |
| critically stressed | 临界应力状态 | 岩石圈中应力 = 岩石强度 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Class5_Stress.md`，Slide 29「Horizontal stresses: uniaxial strain reference state」正文 | "For rocks **0.25 > ν > 0.33** and so the horizontal stress is expected to be about one half to one third of the vertical stress" | **不等号方向写反了**。0.25 > ν > 0.33 是不可能成立的（要求 ν 同时小于 0.25 且大于 0.33） | 应为 **0.25 < ν < 0.33**（或写成 0.33 > ν > 0.25）。后半句的结论是对的：ν/(1−ν) 在 ν = 0.25 时为 1/3、在 ν = 0.33 时约为 1/2，故 σ_H 约为 σ_v 的 1/3 至 1/2 |
| `Class5_Stress.md`，Slide 8 第二组公式的说明 | "tan 2θ = 2σ_xy/(σ_xx − σ_yy) **where θ is the angle measured from σ₁ to the normal to the plane**" | **表述不够精确**。这一句里的 θ 特指 σ₁ 与 **x 方向**（即法线平行于 x 轴的那个面的法线）之间的夹角，而不是"任意一个面"的法线。若照字面理解成任意面，公式无解释力 | 应表述为"θ 是从 σ₁ 量到 **x 坐标方向**的角度"。同页下方 σ_n / τ 两式中的 θ 才是"从 σ₁ 量到目标面法线"的角度——**同一张幻灯片上的两个 θ 含义不同**，是本页最容易造成混乱之处。Practical Ex3(a)(b) 的用法证实了这一读法（那里的 θ = 116.3° 正是 σ₁ 与 x 方向的夹角） |
| `Class5_Stress.md`，Slide 9 notes | "The parametric equations for a circle centred on the x-axis are: x = C **±** r cos ϕ and y = **±** r sin ϕ" | **多余的 ± 号**。参数方程本身用 φ 遍历 0–360° 即可覆盖整圆，不需要 ± | 应为 x = C + r cos φ，y = r sin φ。不影响结论，属书写冗余 |
| `Ex3soln(1).md`，Part (e) 末尾特征向量转角度的插图文字 | "tan θ = 2.02/1，θ = 63.7°；**or from σ₁ clockwise to x-direction, θ = 180 − 63.7 = 116.3°**" | **旋转方向的措辞存疑**。按本课"逆时针为正"的约定，以及 (a)(b) 两问由莫尔图/公式得到的 θ = 116.3°（该值对应莫尔图上 2θ = 232.65°，即**逆时针**），此处的 116.3° 应当是**逆时针**量得的；而 63.7° 才是顺时针量得的 | 数值 116.3° 本身正确（我已用特征向量与莫尔圆两条独立路径复算确认），有疑问的只是 "clockwise" 一词。**说明：该文字来自 PDF 转出的图内文本，原图中箭头的实际指向无法从 md 还原，故此条标为"存疑"而非确定错误。**答题时务必自己画箭头、写清量角方向 |
| `Class5_Stress.md`，Slide 16 | "it becomes convenient to define effective stress as"（其后为空） | **公式图未随 pptx→md 转换保留**（内容缺失，非内容错误） | 缺失的应为 **σ′ = σ_n − P_f**（Terzaghi 有效应力原理），剪应力不变。本笔记 §2.11 已用 📎 补出 |
| `Class5_Stress.md`，Slide 15 / Slide 31 / Slide 37；`Ex3soln(1).md` Part (b)(d) | 分别为"split into two matrices"后的矩阵图、"One may show that"后的公式图、"four most widely used constitutive equations"、"With … then …" | **同上：公式/矩阵图在转换中丢失**（转换缺陷，非内容错误） | Slide 15 的分解式已在 §2.10 用 📎 补出；Ex3(b)(d) 的数值已在 §5.3 用 Slide 8 的公式复算补出；Slide 31、37 的具体公式本笔记未擅自补写，**材料未说明** |

**除上述以外，本周材料（讲义与全部 8 份练习文件）的所有数值算例、莫尔圆的圆心与半径表达式、2θ 关系、正负号约定，我均已逐一复算核对，结果全部与材料一致，未发现错误。**具体复算见 §5.1（Ex1 a–d 四题的 σ₁/σ₂、主应力方位、(σ_n, τ)，另用矩阵特征向量独立验证方位）、§5.2（Ex2 的圆心/半径/角度，并补出材料未印出的 σ₁ = 118.2、σ₂ = 11.8）、§5.3（Ex3 的 σ₁ = 45.401/σ₂ = −2.401、2θ = 232.65°、(σ_n, τ) = (12.296, 22.057)、特征向量 (1, 2.0211)）、§5.4（Ex4 的 (σ_n, τ) = (91.449, 23.492)）；另核对了 Slide 27 的铅直应力梯度（2700 × 9.81 = 26.49 MPa/km，材料写 26.5 ✓）、Slide 28 的 λ ≈ 1/2.7 = 0.37 ≈ 0.4 ✓、Slide 30 的 0.25/0.75 ÷ 0.40/0.60 = 0.5 ✓、Slide 4 的 T_n = (F/A₁)cos²θ 与 T_s = (F/A₁)(sin 2θ)/2 ✓。
