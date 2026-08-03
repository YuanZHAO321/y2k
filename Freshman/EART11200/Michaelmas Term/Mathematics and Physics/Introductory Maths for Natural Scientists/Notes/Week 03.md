# Week 3 — 勾股定理、三角学与地质几何（金矿脉 Seam of Gold 问题）

> 课程：EART11200 *The Natural Scientist's Toolkit* — Introductory Maths for Natural Scientists
> 材料：Lecture slides `W3_1 / W3_2 / W3_3` + 课堂录音转写 (11-Oct) + Practical 答案册 `eart11200_week03_answers`
> 本周日期：11 October（Michaelmas Term Week 3 / 共 5 周）

---

## 一、本周主题

本周的核心是 **平面三角学 (plane trigonometry)** 及其在真实科学问题中的应用：勾股定理 (Pythagorean theorem)、弧度与角度 (radians and degrees)、三角比 (trigonometric ratios)。这些工具被用来解决三个逐级递进的实际问题：

1. **主问题：金矿脉 (A seam of gold)** —— 用勾股定理与三角比，从"地表露头 + 一个钻孔 (borehole)"的有限信息，反推地下矿脉的几何形状、体积、矿石质量、含金量与经济价值。
2. **附加问题：布拉格定律 (Bragg's law)** —— 用三角学推导 X 射线衍射的相长干涉条件 $n\lambda = 2d\sin\theta$，从而测量晶体层间距。
3. **挑战问题（选做）：噪声级 (noise levels)** —— 用勾股定理算距离 + 分贝对数标度算声压级（因为 Week 3 尚未讲对数 logarithm，老师明确说**这题可以不做**）。

**在 5 周中的位置**：Week 1 讲了单位与量纲 (units and dimensions)，Week 2 讲了 Joule 的功热当量（实验数据、比例关系），Week 3 是**几何 / 三角学**这一块；后续 Week 4、Week 5 会进入对数、指数等内容（老师在本周多次预告"我们还没讲对数"）。本周材料本身数学门槛不高（多为 A-level 或 GCSE 内容），**真正的难点在于三维空间想象力**——老师原话：*"That's actually the difficult bit this week. Thinking through dimensions. That's this week's big challenge."*

---

## 二、核心概念

### 2.1 勾股定理 (Pythagorean theorem)

**适用条件：直角三角形 (right-angled triangle)**，即三个内角中有一个恰为 $90^\circ$。

**定理陈述（slides 原文）**：
> "The square of the hypotenuse (the side opposite the right angle) is equal to the sum of the squares of the other two sides."
> 斜边（直角所对的那条边）的平方，等于另外两条边的平方和。

$$c^2 = a^2 + b^2$$

其中 $c$ 为 **斜边 (hypotenuse)**，也是三角形中**最长的一条边**；$a,b$ 为两条直角边。

**几个必须记牢的附带事实（课堂强调）**：

- 一个三角形**最多只能有一个直角**。因为内角和为 $180^\circ$，一个角占了 $90^\circ$，剩下 $90^\circ$ 要分给另外两个角。
- 因此直角三角形中，**另外两个非直角内角之和恒为 $90^\circ$**（它们互为余角 complementary angles）。
- **三角形不一定要有直角**。勾股定理只**直接**适用于直角三角形；非直角三角形要用余弦定理等（本周不涉及）。
- **单位必须统一（呼应 Week 1）**：$a,b,c$ 三边必须用**同一个单位**测量，否则定理不成立。老师原话："If you use meters for one, and centimeters for another, and millimeters for another, Pythagoras theorem does not work... so long as it's the same unit — centimetres, or metres, or miles, **or cubits, or elbows, or fingers**."

**关于证明**：slides 上给的是**面积拼图式的图形证明 (pictorial proof)** —— $c^2$ 是以 $c$ 为边长的正方形面积，$a^2,b^2$ 同理；把这些正方形放进一个更大的正方形里，通过重排若干个全等三角形，可以直观看出面积相等。老师明确说：*"You can also go through a mathematical proof, which we're not going to do. What I need you to know is the theorem — **learn it, know it, use it**."* → **考试不要求证明，要求会用。**

---

### 2.2 角度单位：度 (degrees) 与弧度 (radians)

**弧度的定义 (definition of the radian)**：
> 圆心处由**长度等于半径的一段弧 (an arc length of one radius)** 所张开的角，为 1 弧度。

也就是说，若弧长 (arc length) $s$ 等于半径 $r$，则该弧对应的圆心角为 $1\ \text{rad}$。

**由定义推出 $2\pi$ 弧度 = 整圆**（课堂完整推导）：
- 圆的周长 (circumference) 为 $C = 2\pi r$。
- 一段长为 $r$ 的弧对应 1 弧度。
- 整个圆周包含 $\dfrac{2\pi r}{r} = 2\pi$ 段这样的弧。
- ⇒ 整圆的圆心角为 $2\pi$ 弧度。

同时整圆也是 $360^\circ$，故：

$$2\pi\ \text{rad} = 360^\circ$$

**必须背下来的换算锚点（老师说记住这几个，其余都能推）**：

| 弧度 | 度 |
|---|---|
| $2\pi$ | $360^\circ$（整圆） |
| $\pi$ | $180^\circ$（平角） |
| $\pi/2$ | $90^\circ$（直角 right angle） |
| $\pi/3$ | $60^\circ$ |
| $\pi/4$ | $45^\circ$ |
| $\pi/6$ | $30^\circ$ |

**换算公式**：

$$\theta_{\text{deg}} = \theta_{\text{rad}} \times \frac{180}{\pi}, \qquad \theta_{\text{rad}} = \theta_{\text{deg}} \times \frac{\pi}{180}$$

**由弧度定义直接得到的两个常用公式**（弧度制下才成立）：

$$s = r\theta \quad (\text{弧长 arc length}), \qquad A = \tfrac{1}{2} r^2 \theta \quad (\text{扇形面积 sector area})$$

**⚠️ 计算器警告（slides + 课堂双重强调，本周最实用的一条建议）**：
> "NB when doing calculations involving angles make sure your calculator is set to the unit that matches your input (radians or degrees)."

老师原话：*"If you're using calculators a lot, then that's usually the thing that goes most wrong when you're doing trigonometry. You've got it set to radians, and you put in degrees or vice versa."* —— 三角学出错最常见的原因就是 DEG/RAD 模式设错。

---

### 2.3 三角比 (Trigonometric ratios)

对一个直角三角形，选定一个非直角的角 $\theta$，三条边分别叫：

- **对边 (opposite, O)**：$\theta$ 所对的那条边；
- **邻边 (adjacent, A)**：紧挨着 $\theta$、且不是斜边的那条边；
- **斜边 (hypotenuse, H)**：直角所对的边，最长边。

> 注意：**"对边 / 邻边"是相对于所选的角 $\theta$ 而言的**，换一个角，对边和邻边就互换了。斜边永远不变。

三个基本三角比：

$$\sin\theta = \frac{O}{H}, \qquad \cos\theta = \frac{A}{H}, \qquad \tan\theta = \frac{O}{A}$$

（助记：**SOH-CAH-TOA**）

课堂用的具体标注：三角形顶点 $A,B,C$，直角在 $B$，角 $\theta$ 在顶点 $A$。则
- 对边 = $BC$，邻边 = $AB$，斜边 = $AC$；
- $\sin\theta = BC/AC$，$\cos\theta = AB/AC$，$\tan\theta = BC/AB$。

**两个基本恒等式 (identities)**：

$$\boxed{\tan\theta = \frac{\sin\theta}{\cos\theta}} \qquad\qquad \boxed{\sin^2\theta + \cos^2\theta = 1 \;\;\Longleftrightarrow\;\; 1 - \cos^2\theta = \sin^2\theta}$$

**恒等式的推导（都从勾股定理来，务必自己能推）**：

1. $\dfrac{\sin\theta}{\cos\theta} = \dfrac{O/H}{A/H} = \dfrac{O}{H}\cdot\dfrac{H}{A} = \dfrac{O}{A} = \tan\theta$ ✓

2. 由勾股定理 $O^2 + A^2 = H^2$，两边同除以 $H^2$：
$$\left(\frac{O}{H}\right)^2 + \left(\frac{A}{H}\right)^2 = 1 \;\Longrightarrow\; \sin^2\theta + \cos^2\theta = 1$$
（这个恒等式在本周的 **Bragg's law 推导**中是关键一步，务必熟练。）

**反三角函数 (inverse trigonometric functions)**：
知道边长比 → 求角度，用 $\sin^{-1}$、$\cos^{-1}$、$\tan^{-1}$（计算器上通常写作 `sin⁻¹` 或 `asin`，常需按 SHIFT/2nd）。例如已知 $\sin\theta = 1/\sqrt{2}$，则 $\theta = \sin^{-1}(1/\sqrt{2}) = 45^\circ$。

> ⚠️ 记号陷阱：$\sin^{-1}\theta$ 是**反函数**，**不是** $1/\sin\theta$（后者是 $\csc\theta$）。答案册里出现的 "1.8 sin⁻¹(14.8)" 是 PDF 转写错乱，正确写法见 §5。

**"解三角形" (solution of triangles) 的实际意义**：老师说，真实问题里你往往只知道**两条边**、或者**一条边加一个角**，被要求求出**其余的边与角**。勾股定理 + 三角比 + 内角和 $180^\circ$ 就是解决这类问题的全套工具。

---

### 2.4 特殊角的精确值 (special angles / surd form)

**（a）$45^\circ$：由等腰直角三角形推出**

取两条直角边都为 1 的直角三角形。因为两直角边相等 ⇒ 两个非直角内角相等 ⇒ 各为 $90^\circ/2 = 45^\circ$。
由勾股定理，斜边 $= \sqrt{1^2+1^2} = \sqrt{2}$。于是

$$\sin 45^\circ = \frac{1}{\sqrt2}, \qquad \cos 45^\circ = \frac{1}{\sqrt2}, \qquad \tan 45^\circ = \frac{1}{1} = 1$$

**（b）$30^\circ$ 与 $60^\circ$：由等边三角形对半切开推出**

取边长为 2 的等边三角形（三个角都是 $60^\circ$）。从一个顶点向对边作垂线，把它切成两个全等的直角三角形：
- 斜边 = 2；
- 底边 = 1（原边长的一半）；
- 高 $= \sqrt{2^2 - 1^2} = \sqrt{3}$（勾股定理）；
- 顶角被平分为 $30^\circ$，底角仍为 $60^\circ$。

对 $30^\circ$ 角：对边 = 1，邻边 = $\sqrt3$，斜边 = 2；
对 $60^\circ$ 角：对边 = $\sqrt3$，邻边 = 1，斜边 = 2。故

$$\sin 30^\circ = \tfrac12,\quad \cos 30^\circ = \tfrac{\sqrt3}{2},\quad \tan 30^\circ = \tfrac{1}{\sqrt3}$$
$$\sin 60^\circ = \tfrac{\sqrt3}{2},\quad \cos 60^\circ = \tfrac12,\quad \tan 60^\circ = \sqrt3$$

**根式形式 (surd form)**：老师建议在**大计算的中间步骤**保留 $\tfrac{1}{\sqrt2}$、$\tfrac{\sqrt3}{2}$ 这样的精确根式，而不是马上转成小数——可以避免累积舍入误差，而且往往能约分化简。
> 📌 转写里写成 "the third form of the fraction"，这是自动转写把 **"surd form"** 听错了，应读作 *surd form*（根式形式）。

**同时检查勾股定理**（slide 上写 "Check for Pythagorean Theorem too!"）：对这些特殊三角形，验证 $1^2 + (\sqrt3)^2 = 2^2$、$1^2+1^2 = (\sqrt2)^2$，可以确认边长没记错。

---

### 2.5 构造地质学与产状测量 (Structural geology: strike and dip)

**构造地质学 (structural geology)** 的定义（slides 原文）：
> "Structural geology is the study of the **three-dimensional distribution of rock units** with respect to their **deformational histories**."
> 研究岩石单元的三维空间分布，及其变形历史。

老师补充：比如砂岩 (sandstone) 层之上覆盖砾岩 (gritstone)，其上有含金层，再有花岗岩 (granite) 侵入体 (intrusion)。构造地质学不仅描述这种三维排布，还要**反推它是怎么形成的**——那一点上的地球历史发生了什么。

**平面 (plane) 的例子**（slides 列举）：
- **bedding**（层理面）、**cleavage**（劈理）、**joint surfaces**（节理面）、**fault planes**（断层面）、**fold axial planes**（褶皱轴面）、**quarry faces**（采石场面）。
- 本周研究的 **seam of gold（金矿脉）** 就是一个"富含 Au (gold) 的岩石平面"。

> ⚠️ 老师特别澄清：**矿脉不是埋在地里的一根黄金条**。*"It's not yellow shiny bar stuck into the ground. It's rock that contains gold. You have the rock and then extract the gold from it."* —— 是**含金的岩石 (ore, 矿石)**，需要开采出来再提炼。

**测量工具**：地质学家在野外用 **罗盘-倾斜仪 (COMPASS-CLINOMETER)** 测量这些产状要素（学生在实习中已经见过）。

#### 为什么需要"走向 + 倾角"这两个量？

老师用现场比划讲得非常清楚：你站在地表，看到一条金矿脉露头。要把它描述给"远方的银行家"（好让他给你投钱），你必须回答两个问题：

1. **它在地表沿哪个方向延伸？**（不然别人来了不知道往哪找）
2. **它往地下是怎么倾斜下去的？是垂直像一口井？还是往这边倒？往那边倒？倾斜多少度？**

老师强调这一点的经济意义：*"Obviously, if it's at the top here and it's tilted in that direction, it's pretty useless drilling over here."* —— 如果你不知道倾向，钻孔位置就是瞎猜，钱全打水漂。而且知道倾角后，你就能算出**要挖多深才能采到矿**：倾角很陡 ⇒ 很快就要挖极深的坑；倾角很缓 ⇒ 只需挖浅浅一层。

#### 约定一：走向与倾角 (strike and dip)

- **走向 (strike)**：*the line of intersection between the planar feature and a horizontal plane*，即**该平面与水平面的交线**，按**右手定则 (right-hand convention)** 取方向。直观上就是矿脉在地表露头延伸的那条线。
- **倾角 (dip)**：*the magnitude of the inclination, below horizontal, at right angles to strike*，即在**垂直于走向**的方向上，该平面**相对水平面向下倾斜**的角度大小。

**记法示例**：`N25E, 45SE` = 走向为北偏东 $25^\circ$（striking 25 degrees East of North），倾角 $45^\circ$，倾向东南。
（注意倾向要写个大致方位 SE，否则同一条走向线有两个可能的倾斜方向，会有歧义。）

#### 约定二：倾角与倾向 (dip and dip direction)

- **倾向 (dip direction)**：倾斜方向的方位角，用 $0^\circ \sim 360^\circ$ 表示，**一般自北起顺时针 (clockwise from North)** 度量。
- slides 说这种记法 **"is absolute"**（绝对、无歧义），因为它直接给出了下倾的朝向，不需要额外补 SE/NW 之类的字母。

**记法示例**：`45/115` = 倾角 $45^\circ$，倾向为自北顺时针 $115^\circ$。

#### 两种约定的换算关系

老师的比喻非常好记：*"If it had eyes here, which way would it be looking?"* —— 想象倾斜面上长了一双眼睛，它"望向"的方向就是倾向。因为倾向与走向垂直：

$$\text{dip direction} = \text{strike} + 90^\circ$$

验证：$25^\circ + 90^\circ = 115^\circ$ ⇒ `N25E, 45SE` 和 `45/115` 描述的是**同一个面**。✓

> 选哪种记法纯粹看个人习惯和场合。老师原话：*"It really just depends which you prefer, what works best in your mind."*

#### 真倾角 vs 视倾角（本周解题的关键前提）

Practical 题干写明：*"You can assume that the seam goes down at a **constant angle** and that you have followed it in **the direction in which it dips most steeply**."*

- "倾斜最陡的方向" = **真倾向 (true dip direction)**，即垂直于走向的方向；沿这个方向测到的才是**真倾角 (true dip)**。
- 沿任何其他方向测到的都是**视倾角 (apparent dip)**，且**视倾角恒小于真倾角**。
- "constant angle"（等倾角）意味着可以把矿脉理想化成**平直的平板 (idealised planar slab)**，才能用简单三角学。老师提醒现实中并非如此：*"But seams of rock are not always completely straight flat lines. They can change angle. But it's a good start — **start with what you know**."*

#### 实际勘探流程（老师讲的 Matilda 金矿案例，澳大利亚 2012）

1. 在地表观察露头，量出 strike 和 dip；
2. 据此**预测**矿脉在地下大致的位置；
3. 在预测位置打若干**钻孔 (boreholes)**，取出不同深度的岩芯样品；
4. 把岩石**压碎 (crushed up)**，提取黄金，测出含量 (ppm)；
5. 结合体积、密度、品位、金价，算出总价值；
6. 与开采成本比较：**"How costly is it to dig down and get the gold out? Would it pay for itself?"** —— 这才是"是否值得开采"的判据。

---

### 2.6 波的干涉 (Interference of waves)

理解 Bragg's law 的前提，是把光当成 **波 (wave)** —— 在 Bragg 的年代（20 世纪初）人们普遍认为光是"电磁场中的一种扰动 (a disturbance in the electromagnetic field)"。

**相长干涉 (constructive interference)**：两列波长、振幅相同的波**完全同相 (exactly in phase / synchronized)** 相遇 ⇒ 逐点相加 ⇒ 合成波振幅是单个波的**两倍**（"the net disturbance is the sum of the two individual disturbances"）。

**相消干涉 (destructive interference)**：两列波**恰好反相 (exactly opposite phases)** 相遇 —— 一个的波峰 (peak/crest) 对上另一个的波谷 (trough) ⇒ 一个把介质往上推、另一个往下拉，且幅度相等 ⇒ **净位移为零 (the net movement is nothing)**，互相抵消。

**通用做法**：*"We just add up their amplitude at every point"* —— 逐点把两列波的振幅相加（叠加原理 superposition），就能判断是相长还是相消。

**中间情形**：如果既不完全同相也不完全反相，得到的是介于两者之间的波形。**本周只处理两个极端**（完全相长 / 完全相消）。

**判据（用光程差 path difference 表述）**：
- 光程差 = $n\lambda$（整数倍波长，$n = 1,2,3,\dots$）⇒ **相长干涉**
- 光程差 = $(n+\tfrac12)\lambda$（半波长的奇数倍）⇒ **相消干涉**

老师的生活化类比：在海边看浪，后面一个大浪追上前面一个小浪、两者合并成更大的浪 = 相长；两列反向传播的波相遇几乎抵消 = 相消。

---

### 2.7 布拉格定律 (Bragg's law) 与 X 射线衍射

**人物背景（与曼彻斯特的联系，老师特别指出）**：
- **William Lawrence Bragg**，1919–1937 年任曼彻斯特大学 **Langworthy Professor of Physics**。
- 与其父 **William Henry Bragg** 共享 **1915 年诺贝尔物理学奖**，获奖理由：*"for their services in the analysis of crystal structure by means of X-rays"*（用 X 射线分析晶体结构）。
- 老师把它和 Week 2 的 Joule（曼彻斯特的酿酒师）并列，说明本课程有意选取"曼彻斯特本地的科学史"作为例子。

**实验装置**：把 X 射线射入晶体固体（实验者用大铅屏保护自己），晶体后方放一块**照相底片 (photographic plate)**。结果底片上除了正中一个"直射光斑"外，周围还出现**一圈有规律的斑点 (a distinctive pattern of diffracted X-rays)** —— 这就是**衍射 (diffraction)**。解释这个花样并用它反推晶体结构，就是他们获诺奖的工作。

**为什么需要衍射**：晶体层间距极小。老师举例：**氯化钠 (sodium chloride, NaCl)** 的层间距 $\approx 2.8\times10^{-8}\ \text{cm} = 2.8\times10^{-10}\ \text{m} = 2.8\ \text{Å}$。
> *"That's pretty small. You're not going to measure it with your ruler. We need to find another way to measure it."* —— 尺子量不了，只能用衍射间接测量。

**物理图像（老师逐步讲解）**：
1. 一列平面波 (wave plane / wavefront) 射向晶体，波长、振幅完全相同的两条射线同相入射。
2. 第一条在**顶层**的某个原子上被散射/反射出去。
3. 第二条从顶层的**空隙 (gap)** 穿过，打到**第二层**的原子上反射，再从顶层空隙穿出。
4. 出射后两列波再次形成两个波前，此时**它们走过的路程不同**。
5. 问题归结为：**多走的那段距离是整数倍波长（⇒ 相长）还是半波长的奇数倍（⇒ 相消）？**

老师强调的关键点：*"They're in phase here. They're exactly the same as they go into the crystal."* —— 入射时同相是前提；两条射线在到达图中 $A$ 点（下方射线开始"绕远路"的起点）之前走过的距离是完全相同的，所以只需要算**额外多走的部分**。

---

## 三、公式与图表

### 3.1 本周核心公式汇总

| 公式 | 名称 | 符号含义 |
|---|---|---|
| $c^2 = a^2 + b^2$ | 勾股定理 Pythagorean theorem | $c$ = 斜边 hypotenuse（最长边，直角所对）；$a,b$ = 两直角边。**三者单位必须相同** |
| $2\pi\ \text{rad} = 360^\circ$ | 弧度-角度换算 | $\pi\ \text{rad}=180^\circ$，$\pi/2\ \text{rad}=90^\circ$ |
| $s = r\theta$ | 弧长公式 | $s$ = 弧长；$r$ = 半径；$\theta$ = 圆心角（**必须用弧度**） |
| $\sin\theta = O/H$ | 正弦 sine | $O$ = 对边 opposite；$H$ = 斜边 hypotenuse |
| $\cos\theta = A/H$ | 余弦 cosine | $A$ = 邻边 adjacent |
| $\tan\theta = O/A$ | 正切 tangent | — |
| $\tan\theta = \dfrac{\sin\theta}{\cos\theta}$ | 三角恒等式 | — |
| $\sin^2\theta + \cos^2\theta = 1$ | 毕达哥拉斯恒等式 | 等价形式 $1-\cos^2\theta = \sin^2\theta$（Bragg 推导要用） |
| $n\lambda = 2d\sin\theta$ | **布拉格定律 Bragg's law** | $n$ = 衍射级次 (order, 正整数)；$\lambda$ = 波长 wavelength；$d$ = 晶面间距 interplanar spacing；$\theta$ = 掠射角（**自晶面量起**，不是自法线量起！） |
| $\rho = m/V$ | 密度 density | $m$ = 质量；$V$ = 体积 |
| $L = 10\log_{10}\!\left(\dfrac{p_{rel}^2}{p_{ref}^2}\right) = 20\log_{10}\!\dfrac{p_{rel}}{p_{ref}}$ | 分贝标度 decibel scale（选做） | $p_{ref} = 20\times10^{-6}$ Pa（人耳听阈参考声压） |
| $p(x) = p_{lev}\times \dfrac{x_1}{x}$ | 声压随距离衰减（选做） | 强度 $I \propto 1/x^2$（平方反比），而 $I\propto p^2$ ⇒ 声压 $p \propto 1/x$（反比于距离） |

### 3.2 布拉格定律的完整推导（必考推导，逐步写清）

**几何设定**（对应 slides 与答案册中的图）：
- 两层平行晶面，间距为 $d$。
- X 射线以掠射角 $\theta$（**相对晶面测量**，not 法线）入射。
- 上层射线在 $C'$ 处（顶层）反射；下层射线沿 $A \to B \to C$ 路径，其中 $B$ 在下层晶面上，$A$、$C$ 在上层晶面上。
- 图中 $B$ 处、$A$ 处各有一个直角（老师："This here is a right-angled triangle. Here's the right angle at B. There's a right angle at A here as well."）。

**光程差 (path difference)**：

$$\Delta = AB + BC - AC'$$

**第 1 步：求 $AB$ 与 $BC$**
$A$ 到 $B$ 的连线，与晶面成角 $\theta$，其垂直分量恰为层间距 $d$。所以在这个直角三角形里 $d$ 是对边、$AB$ 是斜边：

$$\sin\theta = \frac{d}{AB} \;\Longrightarrow\; AB = \frac{d}{\sin\theta}$$

由对称性（入射角 = 反射角）：

$$BC = AB = \frac{d}{\sin\theta} \;\Longrightarrow\; AB + BC = \frac{2d}{\sin\theta}$$

**第 2 步：求 $AC$**
$AC$ 是上层晶面上、入射点与出射点之间的距离。$B$ 位于 $AC$ 的正下方中点处，所以水平半距为 $\tfrac12 AC$，垂直距离为 $d$：

$$\tan\theta = \frac{d}{\tfrac{1}{2}AC} \;\Longrightarrow\; \tfrac12 AC = \frac{d}{\tan\theta} \;\Longrightarrow\; AC = \frac{2d}{\tan\theta}$$

**第 3 步：求 $AC'$**
$AC'$ 是 $AC$ 在波前方向上的投影（$C'$ 是自 $A$ 向上层反射线所作垂足）：

$$AC' = AC\cos\theta = \frac{2d\cos\theta}{\tan\theta} = \frac{2d\cos\theta \cdot \cos\theta}{\sin\theta} = \frac{2d\cos^2\theta}{\sin\theta}$$

（这里用了 $\tan\theta = \sin\theta/\cos\theta$，即 $1/\tan\theta = \cos\theta/\sin\theta$。）

**第 4 步：合并，并用毕达哥拉斯恒等式化简**

$$\Delta = AB + BC - AC' = \frac{2d}{\sin\theta} - \frac{2d\cos^2\theta}{\sin\theta} = \frac{2d}{\sin\theta}\left(1 - \cos^2\theta\right)$$

代入 $1 - \cos^2\theta = \sin^2\theta$：

$$\Delta = \frac{2d}{\sin\theta}\cdot \sin^2\theta = 2d\sin\theta$$

**第 5 步：相长干涉条件**
相长干涉要求光程差是波长的整数倍：

$$\boxed{n\lambda = 2d\sin\theta}, \qquad n = 1,2,3,\dots$$

这就是 **布拉格定律 (Bragg's law)**。

**两个常用变形**：

$$\sin\theta = \frac{n\lambda}{2d} \qquad\qquad d = \frac{n\lambda}{2\sin\theta}$$

> 注意 $\sin\theta \le 1$ ⇒ $n\lambda \le 2d$，所以只有有限个 $n$ 能给出衍射峰。这也解释了为什么必须用波长与原子间距同量级的 **X 射线**（而不是可见光）来做晶体衍射。

### 3.3 金矿脉几何图（文字描述关键要点）

slides 上的理想化剖面图（沿真倾向切开的**垂直剖面**）包含四个标注数字：

```
        地表(露头)                     钻孔 Drill hole
   ────┬──1.8 m──┬──────────── 30 m ────────────┬────  ← 水平地表
       │╲        ╲                              │
       │ ╲        ╲   (矿脉以恒定倾角 θ 下倾)      │ 8 m (垂直)
       │  ╲        ╲                            │
       │   ╲        ╲__________________________ ↓
       │              (钻孔在此深度 8 m 处再次遇到矿脉中心)

   另有：沿走向的宽度 (width perpendicular to dip) = 15 m —— 垂直于纸面的方向
```

- **1.8 m**：矿脉在**地表沿水平方向**量得的宽度（thickness of seam along ground）。**这不是真厚度！**
- **30 m**：矿脉地表露头中心到钻孔中心的**水平**距离。
- **8 m**：地面到钻孔中所遇矿脉中心的**垂直**距离（深度）。
- **15 m**：垂直于倾向的宽度（width perpendicular to dip），即**沿走向方向 (along strike)** 的延伸宽度 —— 这是第三个维度，垂直于上面那张剖面图。

> 💡 slides 上的提示：*"Those of you comfortable with Maths can solve this problem **without** the distance from centre of seam to bore hole (30 m)."* —— 这正是 §5.2 相关问题 1 的伏笔：30 m 其实会在代数中约掉。

---

## 四、课堂补充

以下内容**只出现在 lecture transcript 里，slides 上没有**：

### 4.1 关于本周难点的定位
- 老师直言：**本周真正难的不是三角公式，而是三维空间思维**。*"That's actually the difficult bit this week. Thinking through dimensions. That's this week's big challenge, OK?"*
- 因此他在课上刻意**跳过了所有课件里的换算练习题**（"We won't go through the little exercise bits, you can look at the exercise" / "They are on Blackboard, and you can look at them for yourself"），把时间全部用来讲**三维产状 (strike & dip)** 和 **Bragg 的几何**。→ 复习时要自己补做 slides 上的度/弧度换算练习。

### 4.2 关于本节课的行政说明
- 这一小时（11 点场）被临时改为**自愿参加 (officially optional)**，无需签到；下午 3 点在 **Engineering Building** 的那场（即 Practical）**需要签到**，届时会给考勤码。
- 课程内容顺序被学生的需求重排：先讲三角基础 → 直接跳到三维的 strike/dip → 有时间再回来讲 Bragg's crystals。

### 4.3 关于勾股定理的口头强调
- "learn it, know it, use it" —— 不要求会证，要求会用。
- **单位统一**是最容易被忽视的前提，老师用 "cubits, elbows, fingers" 的玩笑加深印象。
- 图形证明只是帮助直观理解面积关系，**不是考点**。

### 4.4 关于计算器（本周最实用的口头建议）
- 三角计算出错，**最常见的原因就是 DEG/RAD 模式与输入不匹配**。
- $\sin^{-1}$ 按键的用法：知道比值反推角度，"There's usually a little symbol. It'll say sine minus one on it. And that lets you go the other way."

### 4.5 关于特殊角
- $30^\circ$、$45^\circ$、$60^\circ$ 的值"很简单"，所以**在教材与试题中被大量使用**，值得直接记住。
- 中间步骤保留 **surd form**（根式）而非小数，尤其在"这只是一个更大计算的一部分"时 —— *"it's often very useful to do that if you're doing larger calculations."*

### 4.6 关于金矿脉问题的直觉铺垫（课堂比划、slides 上完全没有）
- **"想象倾斜面上有一双眼睛，它望向哪儿就是倾向"** —— 理解 dip direction 最好的记法。
- **走向线的直观定义**："基本上就是地面上、垂直于金矿露出方向的一条线"（注：老师此处口误，走向线本身就是露头延伸的那条线，倾向才与之垂直——以 slides 的严格定义为准）。
- 经济动机：知道倾角才能估算**要挖多深**；矿脉陡 ⇒ 很快就要挖很深的坑；矿脉缓 ⇒ 只需浅挖。
- 打钻孔的意义：*"If you're looking for gold, you don't want to just randomly start digging."* 钻孔取样是**低成本探测地下的手段**。
- 现实警告：真实矿脉**会变角度**，单一钻孔的推断只是起点（"but it's a good start — start with what you know"）。

### 4.7 关于光的本性（Bragg 部分的科学史铺垫）
老师串了一条光学史脉络（slides 只有一个 URL）：
- **古希腊哲学家**做了大量光学工作，奠定了现代光学的基础；
- **约一千年前的伊拉克**（指 Ibn al-Haytham 所在的时期），研究颜色与"光的小包"；
- 近代人们用**波长**解释光，但发现波动说无法解释全部现象；
- 最终 **Einstein** 把光归纳为一个个**能量包 (photons, 光子)**；
- 今天我们说光具有 **波粒二象性 (wave-particle duality)**。
- 老师的方法论提醒：*"We can use the idea of light as both waves or particles. **They're both correct.** In some explanations, one description works better, and in other cases, another one does."* —— Bragg 问题用**波动**图像最方便。

### 4.8 关于干涉的具体讲解
- 相长：两波"完全同步" ⇒ 净扰动是两者之和（振幅翻倍）。
- 相消：峰对谷，一个把介质往一个方向推、另一个往相反方向推等量 ⇒ 净位移为零。
- 操作方法：**逐点相加振幅**。
- 海浪类比（大浪追上小浪合并 / 反向波相消）。
- 明确说明本周**只讨论两个极端情形**，不处理中间相位差。

### 4.9 老师在课上标注的直角位置（做 Bragg 图时的关键）
"This here is a right-angled triangle. Here's the right angle at B. There's a right angle at A here as well." —— 画 Bragg 几何图时，务必标出这两个直角，否则无法建立三角关系。

### 4.10 Practical transcript 说明
Practical Week 3 的转写内容**全部是行政事务**，无任何数学内容，包括：
- 讲义纸质版发完了，请同学**共用**，并提醒**网上也有电子版**；
- 请所有人用 **QR code + PIN** 完成 Practical 的考勤签到（注意：那个 WhatsApp 的 QR 码**不是**签到码，两者不同）；
- 学生代表 (student reps) 建立了**一年级全体的 WhatsApp 群**，用于互相联系与收集反馈；
- 第一次 **Student Staff Liaison Committee (SSLC)** 会议下周举行，鼓励大家通过学生代表反馈课程问题。

---

## 五、Practical 要点

Practical 材料为 `eart11200_week03_answers`，属于 *Problem Solving 1: First Quarter Warm-ups* 的 **1.4 节 "A seam of gold"**。

### 5.0 本周任务清单（slides W3_3 明确列出）

| 优先级 | 任务 |
|---|---|
| 必做 | **主问题：Seam of Gold** |
| 必做 | **附加问题：Bragg's law** |
| 建议 | 三角与勾股的常规练习（参考 *Foundation Maths Support Pack* 4.1、4.2、4.5） |
| 选做 | 相关问题（related problems） |
| **不要求** | **噪声级 (sound pressure levels)** —— 需要对数 (logarithms)，本课程尚未讲到 |

Blackboard 上的两个在线测评：**"Angles, Triangles and Trigonometry"** 与 **"A seam of gold"**。
背景阅读：**Croft and Davison (2006)** 中 *Angles*、*Solution of triangles*、*Trig* 各章；**或** *Foundation Maths Support Pack* 的 4.1、4.2、4.5。
slides 明确写道：*"If you have not done A level maths, or are not familiar with the concept of logarithms, **stop here**."* —— 没学过对数的同学做完前两题即可，"well done"。

---

### 5.1 【主问题 Problem 1.4】金矿脉的价值估算 —— 完整解法

**题干**：一条矿化脉 (mineralised seam) 在地表可见，向围岩中下倾。你想知道开采是否**经济 (economic)**，因此要估算其中黄金的价值。为查明其去向，在一段距离外打了一个钻孔，记录了矿脉再次出现的深度。假设矿脉以**恒定角度**下倾，且你是沿**倾斜最陡的方向**追踪的。

**已知数据**：

| 量 | 数值 |
|---|---|
| 矿脉中心到钻孔中心的**水平**距离 | 30 m |
| 地面到矿脉中心的**垂直**距离（深度） | 8 m |
| 矿脉**沿地面**的厚度 | 1.8 m |
| 垂直于倾向的宽度（沿走向） | 15 m |
| 矿石密度 (density of ore) | 7.5 g cm⁻³ |
| 岩石中金的浓度 | 3 ppm（按重量 by weight） |
| 金价 | £330 / 金衡盎司 (troy ounce)；1 troy ounce = 31.1 g |

**答案册的 Notes 提示**：需要掌握 **mass percent（质量百分比）**、**用密度算体积和质量**、以及**勾股定理与三角比**。

---

#### 第 1 步：求沿矿脉的长度（down-dip length）—— 用勾股定理

从地表露头中心到钻孔处矿脉中心，水平位移 30 m、垂直位移 8 m，这两段与"沿矿脉的斜长 $h$"构成直角三角形：

$$h = \sqrt{30^2 + 8^2} = \sqrt{900 + 64} = \sqrt{964} = 31.048\ \text{m} \approx 31.05\ \text{m}$$

#### 第 2 步：求倾角 (angle of dip) —— 用三角比

对倾角 $\theta$，对边 = 8 m（垂直），邻边 = 30 m（水平）：

$$\tan\theta = \frac{8}{30} = 0.2667 \;\Longrightarrow\; \theta = \tan^{-1}(0.2667) = 14.93^\circ \approx 14.9^\circ$$

（计算器务必处于 **DEG** 模式。）

#### 第 3 步：求矿脉的**真厚度 (true thickness)** —— 本题最容易错的一步

给的 1.8 m 是**沿水平地面**量得的宽度，而**体积计算必须用垂直于矿脉两个界面的真厚度 $d$**。

设矿脉是两个平行平面夹成的板，两平面均以 $\theta$ 倾斜。沿地表的那条水平线段（长 1.8 m）连接了这两个平面，它与矿脉平面的夹角就是倾角 $\theta$。因此真厚度是它在垂直于平面方向上的投影：

$$d = 1.8 \times \sin\theta = 1.8 \times \sin(14.93^\circ) = 1.8 \times 0.2576 = 0.464\ \text{m} \approx 0.46\ \text{m}$$

> ⚠️ 答案册 PDF 在此处转写严重错乱（写成 "1.8 sin⁻¹(14.8)"）。正确写法是 $d = 1.8\sin\theta$。判断方法：倾角很缓（约 $15^\circ$）时，矿脉在地表被"斜切"，露头看起来会**比真厚度宽得多** ⇒ 真厚度必然**小于** 1.8 m ⇒ 必须**乘以** $\sin\theta$（$\sin 14.9^\circ \approx 0.26 < 1$）。✓ 得 0.46 m，合理。

#### 第 4 步：求矿脉体积 (volume)

把矿脉视为一个长方体板：**沿矿脉长度 × 真厚度 × 沿走向宽度**

$$V = h \times d \times z = 31.05 \times 0.46 \times 15 \approx 214\ \text{m}^3$$

（若不作中间舍入：$31.048 \times 0.4637 \times 15 = 216.0\ \text{m}^3$，与答案册的 214 m³ 差异纯属四舍五入。）

> ✅ **一致性检验（漂亮的技巧）**：注意 $h\cdot d = h\cdot(1.8\sin\theta) = h \cdot 1.8 \cdot \dfrac{8}{h} = 1.8 \times 8$，$h$ 直接约掉！所以
> $$V = 1.8 \times 8 \times 15 = 216\ \text{m}^3$$
> 完全不需要 30 m，也不需要算 $h$ 和 $\theta$。这正是 slides 上"数学好的同学可以不用 30 m 就解出来"的含义，也是 §5.2 相关问题 1 的正解。

#### 第 5 步：求矿石总质量 —— 用密度，注意**单位换算**

先把密度换成 SI 单位：

$$\rho = 7.5\ \text{g cm}^{-3} = 7.5 \times \frac{10^{-3}\ \text{kg}}{10^{-6}\ \text{m}^3} = 7.5 \times 10^{3}\ \text{kg m}^{-3} = 7500\ \text{kg m}^{-3}$$

（换算逻辑：$1\ \text{g} = 10^{-3}$ kg，$1\ \text{cm}^3 = 10^{-6}\ \text{m}^3$，所以 $1\ \text{g cm}^{-3} = 1000\ \text{kg m}^{-3}$。）

$$m_{\text{ore}} = \rho V = 7500 \times 214 = 1.605\times10^6\ \text{kg} \approx 1.6\times10^{6}\ \text{kg}$$

#### 第 6 步：求黄金质量 —— 用 ppm

**ppm (parts per million) by weight** = 每一百万份重量中所含的份数 = $10^{-6}$（无量纲的质量分数）。所以 3 ppm 意味着每 1 kg 矿石含 $3\times10^{-6}$ kg 黄金：

$$m_{\text{Au}} = m_{\text{ore}} \times 3\times10^{-6} = 1.6\times10^{6}\ \text{kg} \times 3\times10^{-6} = 4.8\ \text{kg}$$

#### 第 7 步：换算为金衡盎司 (troy ounces)

$$N = \frac{4.8\ \text{kg}}{31.1\ \text{g}} = \frac{4800\ \text{g}}{31.1\ \text{g/ounce}} = 154.3 \approx 154\ \text{troy ounces}$$

#### 第 8 步：求总价值

$$\text{Value} = 154 \times £330 = £50{,}820 \approx \boxed{£51{,}000}$$

**结论解读**：这条矿脉的黄金总值约 **5.1 万英镑**。要判断"是否经济 (economic)"，还需与开采、破碎、提炼的**成本**对比 —— 老师的问法：*"Would it pay for itself?"*（数量级上看，5 万英镑显然覆盖不了一个矿场的运营成本，所以答案多半是"不值得"。）

---

### 5.2 【相关问题 1】不给水平距离，如何求体积？（不用三角函数）

**题干变化**：
- **不给**地表矿脉中心到钻孔的水平距离；
- 矿脉与水平面之间的**垂直高度** $y = 7$ m；
- 沿走向宽度 $z = 15$ m；
- 沿倾向方向的厚度 $t = 2$ m。

**答案册解法（"Tricky bit of Maths here"）**：

**第 1 步：给未知量取个字母。** 设沿矿脉的长度为 $h$（未知，也不需要知道）。

**第 2 步：用相似三角形 (similar triangles) 建立比例关系。**
垂直深度 $y$ 与斜长 $h$ 的比，等于真厚度 $d$ 与倾向厚度 $t$ 的比：

$$\frac{y}{h} = \frac{d}{t}$$

> 这个关系的本质就是：两边都等于 $\sin\theta$。左边 $y/h = \text{对边}/\text{斜边} = \sin\theta$；右边 $d/t = \sin\theta$（就是 §5.1 第 3 步的关系）。用"相似三角形"表述可以**完全绕开三角函数**。

**第 3 步：解出真厚度。**

$$d = t \times \frac{y}{h}$$

**第 4 步：代入体积公式。**

$$V = h \times d \times z = h \times \left(t \times \frac{y}{h}\right) \times z$$

**第 5 步：$h$ 约掉。**

$$V = t \times y \times z$$

**第 6 步：代入数值。**

$$V = 2 \times 7 \times 15 = \boxed{210\ \text{m}^3}$$

> 💡 **答案册总结的方法论金句**："Sometimes, if you don't know the value of something, **try calling it a letter (like $x$) and you may be able to solve the problem**." —— 未知量不一定要求出来，它可能在代数中自行消去。这是本周最重要的**解题策略**收获。

---

### 5.3 【相关问题 2】多个钻孔样品，如何估算含金量？

**题干**：单个钻孔样品不足以确信能采到多少金。现有 5 个钻孔样品，测得不同位置的金浓度为 **3, 5, 1, 5.5, 4 ppm**。如何用这些数据估算可采金量？

**答案册答复**："Stats example. **Calculate the average! then repeat.**"

**做法**：

1. 求算术平均值 (mean)：
$$\bar{c} = \frac{3 + 5 + 1 + 5.5 + 4}{5} = \frac{18.5}{5} = 3.7\ \text{ppm}$$

2. 用 $\bar{c}$ 代替原来的 3 ppm，**重复 §5.1 的第 6~8 步**：
$$m_{\text{Au}} = 1.6\times10^6\ \text{kg} \times 3.7\times10^{-6} = 5.92\ \text{kg}$$
$$N = \frac{5920\ \text{g}}{31.1\ \text{g/oz}} = 190.4\ \text{troy oz} \;\Longrightarrow\; \text{Value} = 190 \times £330 \approx £62{,}800$$

**延伸思考（题目的真正用意）**：样品从 1 ppm 到 5.5 ppm 相差 5 倍多，说明矿脉品位 (grade) 空间变化很大。因此除了平均值，还应考察**离散程度**（极差 range、标准差 standard deviation），给出估值的**区间**而非单一数字 —— 用最低品位算最坏情形，用最高品位算最好情形。这是"单个钻孔永远无法确信"的量化表达。

---

### 5.4 【附加问题 Problem 1.5（例题）】已知 $d$ 与 $\lambda$，求相长干涉角

**题干**：晶体层间距 $d = 50$ Å，X 射线波长 $\lambda = 1$ nm。问从**晶面量起**的哪些角度会发生相长干涉？

**第 1 步：单位统一（关键！）**
- $1\ \text{Å (angstrom)} = 10^{-10}\ \text{m}$ ⇒ $d = 50\ \text{Å} = 50\times10^{-10}\ \text{m} = 5\times10^{-9}\ \text{m}$
- $1\ \text{nm} = 10^{-9}\ \text{m}$ ⇒ $\lambda = 1\times10^{-9}\ \text{m}$
- （亦即 $d = 5$ nm，$1\ \text{nm} = 10\ \text{Å}$）

**第 2 步：变形 Bragg's law 解出 $\sin\theta$**

$$n\lambda = 2d\sin\theta \;\Longrightarrow\; \sin\theta = \frac{n\lambda}{2d}$$

**第 3 步：代入数值**

$$\sin\theta = \frac{n \times 1\times10^{-9}}{2 \times 5\times10^{-9}} = \frac{n}{10} = 0.1n, \qquad n = 1,2,3,\dots$$

**第 4 步：取反正弦求角**

| $n$ | $\sin\theta$ | $\theta = \sin^{-1}(\sin\theta)$ |
|---|---|---|
| 1 | 0.1 | $5.74^\circ$ |
| 2 | 0.2 | $11.54^\circ$ |
| 3 | 0.3 | $17.46^\circ$ |
| ⋮ | ⋮ | ⋮ |
| 10 | 1.0 | $90^\circ$（上限） |

$$\boxed{\theta = 5.74^\circ,\ 11.54^\circ,\ 17.46^\circ,\ \dots}$$

> 注意：这些角**不是等间距的**（$5.74, 11.54, 17.46$ 的间隔逐渐变大），因为是 $\sin\theta$ 而非 $\theta$ 本身呈等差。这是判断答案对不对的一个快速检查。
> 又：由 $\sin\theta\le1$ 得 $n \le 2d/\lambda = 10$，所以最多只有 10 级衍射。

---

### 5.5 【附加问题 1.4.4.2】已知角度与 $\lambda$，反求层间距 $d$

**题干**：用波长 $\lambda = 2$ nm 的 X 射线研究一个晶体，发现相长干涉的强度极大出现在 $\theta = 10^\circ,\ 20.3^\circ,\ \dots$。估算晶体层间距。

**解法**：变形 Bragg's law 解出 $d$：

$$d = \frac{n\lambda}{2\sin\theta}$$

取第一级极大（$n=1$，对应最小角 $\theta = 10^\circ$），$\lambda = 2\times10^{-9}$ m：

$$d = \frac{1 \times 2\times10^{-9}}{2\sin 10^\circ} = \frac{2\times10^{-9}}{2 \times 0.17365} = \frac{2\times10^{-9}}{0.3473} = 5.76\times10^{-9}\ \text{m}$$

$$\boxed{d \approx 5.8\times10^{-9}\ \text{m} = 5.8\ \text{nm} = 58\ \text{Å}}$$

**用第二个峰交叉验证**（$n=2$，$\theta = 20.3^\circ$，$\sin 20.3^\circ = 0.3469$）：

$$d = \frac{2 \times 2\times10^{-9}}{2 \times 0.3469} = \frac{4\times10^{-9}}{0.6938} = 5.77\times10^{-9}\ \text{m}$$

两者一致 ✓ —— 这验证了这两个峰确实是同一组晶面的 $n=1$ 与 $n=2$ 级衍射。**养成用第二个数据点验算的习惯。**

---

### 5.6 【挑战问题 1.4.5，选做，需要对数】噪声级

> slides 明确说明："If time try the sound pressure levels — **not needed!** You have to be familiar with logs for this and we have not covered logs yet." 本周不作要求，此处整理供 Week 4/5 学完对数后回看。

#### 理论

- 一定频率的**压力波 (pressure wave)** 被听成声音；压力波的振幅称为**声压级 (sound pressure level)** $p$。
- 声强正比于声压的平方：$I \propto p^2$。
- **分贝标度 (decibel scale)**：

$$L = 10\log_{10}\left(\frac{p_{rel}^2}{p_{ref}^2}\right) = 20\log_{10}\left(\frac{p_{rel}}{p_{ref}}\right), \qquad p_{ref} = 20\times10^{-6}\ \text{Pa}$$

- **距离衰减**：声强遵从**平方反比定律 (inverse square law)**，$I \propto 1/x^2$；因为 $I\propto p^2$，所以**声压反比于距离**：

$$p(x) = p_{lev} \times \frac{x_1}{x}$$

其中 $p_{lev}$ 是在距声源 $x_1$ 处给出的声压级。

#### 例题 1.6：车在 10 m 处为 60 dB(A)，20 m 处是多少？

**第 1 步：由 dB 反求 10 m 处的声压。**

$$60 = 20\log_{10}\frac{p}{2\times10^{-5}} \;\Longrightarrow\; \log_{10}\frac{p}{2\times10^{-5}} = 3 \;\Longrightarrow\; \frac{p}{2\times10^{-5}} = 10^3$$
$$p_{car} = 2\times10^{-5}\times 1000 = 2\times10^{-2}\ \text{Pa}\quad ✓\text{（与答案册一致）}$$

**第 2 步：按反比距离缩放到 20 m。**

$$p(20) = 2\times10^{-2}\times\frac{10}{20} = 1\times10^{-2}\ \text{Pa}$$

**第 3 步：转回分贝。**

$$L = 20\log_{10}\frac{1\times10^{-2}}{2\times10^{-5}} = 20\log_{10}(500) = 20\times2.699 = \boxed{54.0\ \text{dB}}$$

> 记忆点：**距离加倍，声压级下降约 6 dB**（因为 $20\log_{10} 2 = 6.02$）。

#### 问题 1.4.5.2：房屋处的总噪声级

**布置**：房屋位于距直路起点 300 m、距路边 5 m 处。路上两辆车分别在 200 m 和 700 m 处，各为 60 dB(A) @ 10 m。另有一辆 HGV（重型货车）在 305 m 处，84 dB(A) @ 15 m。

**第 1 步：算各声源的参考声压级。**
- 车：$p_{car} = 2\times10^{-2}$ Pa（同上例）
- HGV：$84 = 20\log_{10}\dfrac{p}{2\times10^{-5}} \Rightarrow p = 2\times10^{-5}\times10^{4.2} = \boxed{0.317\ \text{Pa}}$ ✓（与答案册一致）

**第 2 步：用勾股定理算各车到房屋的距离**（沿路方向的差 + 垂直路边的 5 m）：
- Car 1：$\sqrt{(300-200)^2 + 5^2} = \sqrt{10000+25} = 100.12$ m ✓
- Car 2：$\sqrt{(300-700)^2 + 5^2} = \sqrt{160000+25} = 400.03$ m ✓
- HGV：$\sqrt{(300-305)^2 + 5^2} = \sqrt{25+25} = \sqrt{50} = 7.07$ m ✓

**第 3 步：按反比距离缩放各声压。**
- Car 1：$2\times10^{-2}\times\dfrac{10}{100.12} = 2.00\times10^{-3}$ Pa
- Car 2：$2\times10^{-2}\times\dfrac{10}{400.03} = 5.00\times10^{-4}$ Pa
- HGV：$0.317\times\dfrac{15}{7.07} = 0.673$ Pa

**第 4 步：合成总声压（非相干声源按声强/平方相加，不是直接加分贝！）。**

$$p_{tot}^2 = \sum p_i^2 = (2.00\times10^{-3})^2 + (5.00\times10^{-4})^2 + (0.673)^2$$
$$= 4.0\times10^{-6} + 2.5\times10^{-7} + 0.4529 = 0.4529$$
$$p_{tot} = 0.673\ \text{Pa}$$

**第 5 步：转回分贝。**

$$L = 20\log_{10}\frac{0.673}{2\times10^{-5}} = 20\log_{10}(3.36\times10^4) = 20\times4.527 = \boxed{\approx 90.5\ \text{dB(A)}}$$

**结论**：HGV 的贡献**完全压倒**两辆车（它的 $p^2$ 比两车之和大 5 个数量级）—— 因为它既更响，又离房子近得多（7.07 m vs 100 m / 400 m）。这是 dB 对数标度的直观教训：**几个声源中最大的那个往往就决定了总声级**。

---

## 六、易错点 / 重点难点

1. **计算器的 DEG / RAD 模式** —— 老师说这是三角学"最常出错"的地方。做题前先确认模式与题目单位一致。角度制题目里若得到诡异的小数答案，第一反应就是查模式。

2. **单位必须统一才能用勾股定理** —— 三条边不能一条用 m、一条用 cm。同理，Bragg 题里 Å 与 nm 必须先化到同一单位（$50\ \text{Å} = 5\ \text{nm}$，不是 50 nm！）。

3. **矿脉"沿地面的厚度" ≠ 真厚度** —— 这是主问题最大的坑。必须乘 $\sin\theta$：$d = 1.8\sin\theta = 0.46$ m。检验方法：缓倾角时露头会被"斜切"得很宽，所以真厚度**一定小于**地表量得的宽度。

4. **$\sin^{-1}$ 是反函数，不是倒数** —— $\sin^{-1}x \ne 1/\sin x$。答案册 PDF 的转写把 $1.8\sin\theta$ 写成了 "1.8 sin⁻¹(14.8)"，不要被误导。

5. **密度单位换算 g cm⁻³ → kg m⁻³ 要乘 1000**（$7.5 \to 7500$）。忘了这一步质量会差 1000 倍。这类"三次方单位"换算是 Week 1 内容的直接复用。

6. **ppm 是 $10^{-6}$，不是 $10^{-3}$ 也不是百分比** —— 3 ppm by weight = $3\times10^{-6}$ kg/kg。

7. **troy ounce = 31.1 g，不是常衡盎司 28.35 g** —— 贵金属专用单位。题目会明确给出，但要记得**除**（求盎司数）而不是乘。

8. **Bragg 定律中的 $\theta$ 是"掠射角"（自晶面量起）**，不是物理光学里常用的"自法线量起"的入射角。答案册反复强调 "measured from the face of the crystal / lattice"。二者互为余角，混淆会导致把 $\sin$ 写成 $\cos$。

9. **Bragg 推导中不要漏掉 $-AC'$ 这一项** —— 光程差是 $AB + BC - AC'$，不是 $AB+BC$。少了这项就得不到那个漂亮的 $1-\cos^2\theta = \sin^2\theta$ 化简。

10. **相长干涉的角度不是等间距的** —— 等差的是 $\sin\theta$（$0.1n$），不是 $\theta$。

11. **strike 与 dip direction 相差 $90^\circ$** —— `N25E,45SE` 与 `45/115` 是同一件事。写 strike-and-dip 记法时**必须**附上倾斜的大致方位（SE 等），否则有 180° 歧义；dip-and-dip-direction 记法则天然无歧义（slides 说它 "is absolute"）。

12. **真倾角 vs 视倾角** —— 只有沿垂直于走向（"倾斜最陡"）的方向测量才是真倾角。本周题目**默认已沿真倾向**，这是能用简单二维三角学的前提。

13. **三维想象是本周真正的门槛** —— 金矿脉问题有三个方向：沿倾向（剖面内）、垂直矿脉（真厚度）、沿走向（15 m，垂直于剖面）。搞清楚哪个长度属于哪个方向，比公式本身更重要。**画图！先画剖面图，再标出第三维。**

14. **"未知量取字母，可能自动约掉"** —— 相关问题 1 的核心技巧（$V = t\,y\,z$，与 $h$ 无关）。遇到"信息不足"的题，先别放弃，设个未知数试试。

15. **多声源合成不能直接把 dB 相加** —— 必须先转回声压/声强，平方相加，再转回 dB（选做题的坑）。

16. **勾股定理的证明不是考点**，但定理的适用条件（直角三角形 + 单位统一）是。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Pythagorean theorem | 勾股定理 / 毕达哥拉斯定理 | 直角三角形中 $c^2=a^2+b^2$，$c$ 为斜边；三边须同单位。 |
| right-angled triangle | 直角三角形 | 含一个 $90^\circ$ 角的三角形，最多只能有一个直角。 |
| hypotenuse | 斜边 | 直角所对的边，也是直角三角形中最长的边。 |
| opposite / adjacent | 对边 / 邻边 | 相对于所选角 $\theta$ 而言的两条非斜边（对边与 $\theta$ 相对，邻边紧挨 $\theta$）。 |
| radian | 弧度 | 圆心处由长度等于半径的弧所张的角；整圆为 $2\pi$ 弧度。 |
| degree | 度 | 角度单位，整圆为 $360^\circ$；$2\pi\ \text{rad}=360^\circ$。 |
| arc length | 弧长 | 圆周上一段的长度，$s = r\theta$（$\theta$ 用弧度）。 |
| circumference | 周长 | 圆的一周长度，$C = 2\pi r$。 |
| subtend | 张（角） | 一段弧/线段在某点处"张开"出一个角。 |
| trigonometric ratios | 三角比 | $\sin=O/H$、$\cos=A/H$、$\tan=O/A$（SOH-CAH-TOA）。 |
| sine / cosine / tangent | 正弦 / 余弦 / 正切 | 三个基本三角函数。 |
| inverse sine ($\sin^{-1}$) | 反正弦 | 由比值反求角度；注意不是 $1/\sin$。 |
| surd form | 根式形式 | 保留 $\tfrac{1}{\sqrt2}$、$\tfrac{\sqrt3}{2}$ 等精确根式而非小数，便于后续化简。 |
| identity | 恒等式 | 对所有取值都成立的等式，如 $\sin^2\theta+\cos^2\theta=1$。 |
| solution of triangles | 解三角形 | 已知部分边角，求出其余边角。 |
| structural geology | 构造地质学 | 研究岩石单元的三维分布及其变形历史。 |
| seam | 矿脉 / 矿层 | 一层特定成分的岩石（本周指富含金的岩层，**不是**纯金）。 |
| ore | 矿石 | 含有可提取金属的岩石。 |
| mineralised seam | 矿化脉 | 因成矿作用而富集了矿物的岩层。 |
| strike | 走向 | 平面构造与水平面的交线（按右手定则定向）。 |
| dip | 倾角 | 在垂直于走向的方向上，平面相对水平面向下倾斜的角度。 |
| dip direction | 倾向 | 下倾方向的方位角，自北顺时针 $0^\circ\sim360^\circ$；= strike + $90^\circ$。 |
| true dip / apparent dip | 真倾角 / 视倾角 | 沿最陡方向测得的是真倾角；沿其他方向测得的视倾角总是偏小。 |
| bedding | 层理（面） | 沉积岩中的成层界面，是常见的地质平面。 |
| cleavage | 劈理 | 岩石中易于劈开的定向面。 |
| joint surface | 节理面 | 岩石中无明显位移的裂开面。 |
| fault plane | 断层面 | 岩块沿其发生相对位移的破裂面。 |
| fold axial plane | 褶皱轴面 | 通过褶皱各层枢纽点的平面。 |
| quarry face | 采石场面 | 采石作业形成的岩壁露面。 |
| outcrop | 露头 | 岩层暴露于地表的部分。 |
| borehole / drill hole | 钻孔 | 为取样探测地下岩石而钻的孔。 |
| compass-clinometer | 罗盘-倾斜仪 | 野外测量走向与倾角的地质专用仪器。 |
| intrusion | 侵入体 | 一种岩石侵入到另一种岩石中形成的体。 |
| sandstone / gritstone / granite | 砂岩 / 粗砂岩 / 花岗岩 | 课堂示意图中用到的三种岩石类型。 |
| grade / concentration (ppm) | 品位 / 浓度（百万分之一） | 矿石中目标金属的含量，3 ppm by weight = $3\times10^{-6}$ kg/kg。 |
| density | 密度 | $\rho = m/V$；本题 7.5 g cm⁻³ = 7500 kg m⁻³。 |
| troy ounce | 金衡盎司 | 贵金属计量单位，1 troy ounce = 31.1 g（≠ 常衡盎司 28.35 g）。 |
| economic (deposit) | （矿床）经济性 | 开采收益能否覆盖成本，即"值不值得挖"。 |
| Bragg's law | 布拉格定律 | $n\lambda = 2d\sin\theta$，X 射线晶体衍射的相长干涉条件。 |
| diffraction | 衍射 | 波遇到与其波长相当的结构时发生的偏折与干涉现象。 |
| interplanar spacing ($d$) | 晶面间距 | 晶体中相邻原子层之间的距离。 |
| constructive interference | 相长干涉 | 两波同相叠加，振幅增强；光程差 = $n\lambda$。 |
| destructive interference | 相消干涉 | 两波反相叠加，互相抵消；光程差 = $(n+\tfrac12)\lambda$。 |
| path difference | 光程差 | 两条射线走过的距离之差，决定干涉类型。 |
| in phase / out of phase | 同相 / 反相 | 两波峰谷对齐 / 波峰对波谷。 |
| wavelength ($\lambda$) | 波长 | 相邻两个波峰之间的距离。 |
| amplitude | 振幅 | 波偏离平衡位置的最大位移。 |
| wavefront / wave plane | 波前 / 波面 | 同相位点构成的面。 |
| order ($n$) | 衍射级次 | Bragg 定律中的正整数，对应光程差为几个波长。 |
| angstrom (Å) | 埃 | 长度单位，$1\ \text{Å}=10^{-10}$ m $=0.1$ nm。 |
| wave-particle duality | 波粒二象性 | 光既可作波也可作粒子（光子）描述，两者都正确。 |
| photon | 光子 | 光的能量量子（Einstein 提出的"能量小包"）。 |
| Langworthy Professor of Physics | 兰沃西物理学讲席教授 | 曼彻斯特大学物理学讲席；W. L. Bragg 于 1919–1937 年任此职。 |
| decibel (dB) scale | 分贝标度 | $L = 20\log_{10}(p/p_{ref})$，$p_{ref}=20\ \mu$Pa（选做内容）。 |
| sound pressure level | 声压级 | 声波的压力振幅 $p$；$I\propto p^2$（选做内容）。 |
| inverse square law | 平方反比定律 | 声强随距离平方反比衰减，故声压随距离一次反比衰减（选做内容）。 |
| HGV (heavy goods vehicle) | 重型货车 | 选做噪声题中的声源之一，84 dB(A) @ 15 m。 |
| similar triangles | 相似三角形 | 对应角相等、对应边成比例；用于绕开三角函数建立比例关系。 |
