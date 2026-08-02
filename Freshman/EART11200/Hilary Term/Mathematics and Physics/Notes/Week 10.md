# Week 10 — 向量与偏微分 (Vectors and Partial Differentiation)

> **章号对照说明**：本周文件名为 `Chapter10.md`，对应**主手册第 11 章 "Vectors and Partial Differentiation"**。主手册中有一章（第 9 章 Integration by Parts）从未拆入周材料，因此自 Week 9 起周版章号比主手册章号小 1。两者内容一致。**本笔记一律以周号 Week 10 为准**；题号（Question 10.1–10.9）以周版 `Exercises10.md` 为准（主手册中印的题号也是 10.x，与周版一致）。
>
> **材料清单（本周已全部读完）**
> - Lecture：`Chapter10.md`（手册正文段）、`lecture10(1).md`（讲义幻灯片 23 页）、`EART11200 - 04-Apr-transcript.md`（课堂录音转写，含大量考试信息）
> - Practical：`Exercises10.md`（Q10.1–10.9）、`Solutions10.md`（解答，公式多为图片，已据推导重建）、`practical10_soln(1).md`（practical 幻灯片 13 页，Exercise 1–2 及解答）
> - 主手册：`main(1).md` 第 3421–3709 行（第 11 章全文 + 习题 + 解答）
>
> ⚠️ 原始 PDF→MD 转换过程中**大量公式是图片，转换后只剩文字说明**。本笔记中所有公式均已由笔者据上下文与数值结果**完整重建并验算**，可直接使用。

---

## 一、本周主题

### 1.1 本周在全课中的定位

这是 EART11200 数学与物理部分**正课的最后一周**（Week 10 / 校历第 29 周，2025-03-31 那一周；讲座录音日期 04-Apr）。此后 Week 11、12 为复习周（Revision: Differentiation / Revision: Integration），不再讲新内容。

全课脉络：

| 阶段 | 周次 | 内容 |
|---|---|---|
| 微分 (Differentiation) | Week 1–5 | 求梯度、微分入门、组合函数求导、最优化与导数性质、二阶导与求根 |
| 积分 (Integration) | Week 6–9 | 积分入门、用牛顿定律做积分、换元积分、二阶 ODE 积分 |
| **进阶 / 收尾** | **Week 10** | **标量场、向量、偏微分** |
| 复习 | Week 11–12 | 微分复习、积分复习（+ 往年卷讲解） |

讲座原文课程表（幻灯片第 6 页给出的是校历周号 20–34）：

| 日期 | 校历周 | 主题 |
|---|---|---|
| 27/01/2025 | 20 | Calculating Gradients |
| 03/02/2025 | 21 | Introduction to Differentiation |
| 10/02/2025 | 22 | Differentiating Combinations of Functions |
| 17/02/2025 | 23 | Optimisation & Properties of Derivatives |
| 24/02/2025 | 24 | Second Order Derivatives & Root Finding |
| 03/03/2025 | 25 | Introduction to Integration |
| 10/03/2025 | 26 | Integration using Newton's Laws |
| 17/03/2025 | 27 | Integration by Substitution |
| 24/03/2025 | 28 | Integrating Second Order ODEs |
| **31/03/2025** | **29** | **Vectors and Partial Differentiation ← 本周** |
| 07/04/2025 | 30 | Non-teaching week（野外实习 / Wales field trip） |
| 14–21/04 | 31–32 | Easter break |
| 28/04/2025 | 33 | Revision: Differentiation |
| 05/05/2025 | 34 | Revision: Integration + Exam Period |

### 1.2 本周解决的核心问题

前九周所有的微分与积分，**全部围绕单变量函数** $y=f(x)$：

$$\frac{dy}{dx}\quad\text{（一个变量的变化率）},\qquad \int f(x)\,dx\quad\text{（一个变量下的曲线下面积）}$$

但自然科学中的量绝大多数**依赖多个变量**。讲座举的例子：明年学扩散方程 (diffusion equation) 时，你要关心物质**在空间中怎么移动**，那就至少有两个自变量；如果想成一张地图，就是「沿纬度 (latitude) 发生什么」和「沿经度 (longitude) 发生什么」。

于是本周引入三样东西：

1. **标量场 (scalar field)** — 多变量函数 $f(x,y)$，每点给一个数（有大小、无方向）。
2. **向量 (vector) 与向量场 (vector field)** — 每点给一个既有大小又有方向的量。
3. **偏微分 (partial differentiation)** — 把导数推广到多变量：对某一变量求导时，**其余变量当常数**；把各方向的偏导数打包成一个向量，就是**梯度 (gradient) $\nabla f$**。

### 1.3 官方 Intended Learning Outcomes（讲义与 practical 幻灯片均列出）

1. 描述**标量场与向量场**的性质及其在数学物理中的应用；
2. 在理论与实际问题中运用**基本向量运算**：加、减、数乘 (scalar multiplication)、模 (magnitude)；
3. 计算**偏导数**，以确定标量场的变化率（理论题与实际应用题）。

### 1.4 本周的考试地位（重要）

讲座明确说明：期末 100 分、10 题、每题 10 分，**5 题微分 + 5 题积分**，题目**由前 10 周的内容出**，难度从 Q1 递增到 Q10。所以本周内容（向量 + 偏微分）属于**靠后的较难题区间**，且它天然横跨"微分"一侧。详见「四、课堂补充」。

---

## 二、核心概念

### 2.1 标量场 (Scalar field)

**定义**：标量场是一个**两个或更多变量的函数** $f(x,y)$ 或 $f(x,y,z)$，它给空间中每一点**赋一个标量（一个数）**。

$$f:\ (x,y)\ \longmapsto\ f(x,y)\in\mathbb{R}$$

**关键性质**：

- **有大小 (magnitude)，无方向 (no direction)**。
- 本质上就是「更高维的普通函数」——以前是 $f(x)$，现在是 $f(x,y)$。
- 可以用**彩色图 / 等值线图 (colour plot / contour map)** 来可视化：颜色深浅代表数值大小。手册的图中约定 **白 = 高值，黑 = 低值**。

**讲座给的直观例子**：**风速 (wind speed)**。风速只告诉你「多快」，不告诉你「往哪吹」。类似的地球科学标量场还有：城市上空的温度分布、地表高程 (elevation)、气压场的数值、浓度场 $C(x,y,z)$。

**手册 Figure 11.1 的三个标量场（考点：看图辨函数）**

三张图分别是 $f(x,y)=x^2$、$f(x,y)=xy$、$f(x,y)=\tfrac12\left(x^2+y^2\right)$，绘图范围均为 $x,y\in[-10,10]$。判读方法：

| 函数 | 图像特征（怎么认） | 极值位置（在 $[-10,10]^2$ 内） |
|---|---|---|
| $f=x^2$ | **只依赖 $x$**，所以图像沿 $y$ 方向完全均匀 → **竖直条纹**；等值线是竖直直线。左右两边亮（$x=\pm10$ 时 $f=100$），中间一条竖直暗带 | 最小值 $f=0$ 出现在**整条直线 $x=0$ 上**（不是一个点！）；最大值在 $x=\pm10$ 的两条边 |
| $f=xy$ | **鞍形 (saddle)**：第一、三象限为正（亮），第二、四象限为负（暗）→ **四块交替明暗**，沿两坐标轴为 0 | 最大 $f=100$ 在角点 $(10,10)$ 与 $(-10,-10)$；最小 $f=-100$ 在 $(-10,10)$ 与 $(10,-10)$；原点是**鞍点** |
| $f=\tfrac12(x^2+y^2)$ | **旋转对称**：等值线是**同心圆**（因为 $x^2+y^2=$ const 是圆），中心暗、四周亮，像一个碗 (bowl) | 最小 $f=0$ 在原点**一点**；最大在四个角 $(\pm10,\pm10)$，$f=100$ |

> 讲座原话："$x^2+y^2$ 在数学里是个圆，所以你会看到这种圆形的样子……本质上是个球（碗）形，越往中心值越小。"

### 2.2 向量场 (Vector field)

**定义**：向量场是把**一个向量**赋给空间中每一点的函数。

$$\vec{F}:\ (x,y)\ \longmapsto\ \langle F_1(x,y),\,F_2(x,y)\rangle$$

**关键性质**：

- **既有大小又有方向 (magnitude and direction)**；
- 画成图就是**箭头场**（如天气预报上的风场）：箭头**方向**给方向 / 流向 (flow)，箭头**长度**给大小；
- 大小也可以通过「对照相应的标量场」读出。

**讲座给的直观对比（务必记住这一组）**：

| | 标量场 | 向量场 |
|---|---|---|
| 气象类比 | **风速** wind speed | **风向 / 风的速度矢量** wind direction / velocity |
| 给你什么 | 「它以 X m/s 在动」 | 「它正朝那个方向动」 |
| 有方向吗 | 否 | 是 |
| 画法 | 彩色图 / 等值线 | 箭头场 |

> ⚠️ **讲义勘误**：`lecture10(1).md` 第 10 页 "VECTOR FIELDS" 下写着 "For example, wind speed – but not direction."，这是从上一页 SCALAR FIELDS 直接复制粘贴留下的**错误**。按 transcript，向量场对应的应是**风向/风矢量**。记笔记时不要被这句误导。

**Figure 11.2 与 Figure 11.1 的对应关系（手册明确点出的考点）**：

手册说：「**左边和中间两个向量场都可以对应左边那个标量场（即 $f=x^2$）**。你看，这两个向量场给出**相反的流向 (opposite flow)，但作为距离的函数其大小相同**。」

**为什么？** 因为 $f=x^2$ 的梯度是 $\nabla f = \langle 2x,\,0\rangle$——它**只有 $x$ 分量**，且大小 $|2x|$ 随 $|x|$ 线性增长。$+\nabla f$ 的箭头从中间向外指，$-\nabla f$ 的箭头从外向中间指，两者**大小处处相同、方向恰好相反**。这正是"同一个标量场可以配出两个方向相反的向量场"的原因（一个是"上坡方向"，一个是"下坡方向"）。

> 🌍 **地球科学意义**：自然界中的通量 (flux) 几乎总是**沿着 $-\nabla f$**（负梯度方向，即"下坡"）走：热从高温流向低温（Fourier 定律 $q=-k\nabla T$）、物质从高浓度扩散到低浓度（Fick 定律 $J=-D\nabla C$）、地下水从高水头流向低水头（Darcy 定律 $q=-K\nabla h$）。**那个负号就是"顺着斜坡往下"**。这与 Week 9 学的 Fick / Fourier 定律直接衔接。

### 2.3 向量记号 (Vector notation)

**向量 = 大小 + 方向**。手册 Figure 11.3 画了好几条起点不同的线段，它们**都是同一个向量**——因为无论从哪里出发，每条都是「向左 2 单位、向上 5 单位」。

$$\vec{v}=\langle -2,\,5\rangle$$

**记号规则（考试极易失分点）**：

$$\boxed{\ \langle -2,\,5\rangle \ \ne\ (-2,\,5)\ }$$

- **尖括号 (angle brackets) $\langle\ \rangle$** = **向量**，传达**大小与方向**信息；
- **圆括号 (curved/round brackets) $(\ )$** = **坐标点 (coordinate/point)**，表示空间中一个**位置**。

> 讲座反复强调："a vector means something that travels in a specific direction, a coordinate means any particular point"。写作业和考试时**一定要区分**。

**一般写法**：

$$\vec{v}=\langle a_1,\,a_2\rangle \quad(\text{2D}),\qquad \vec{v}=\langle a_1,\,a_2,\,a_3\rangle\quad(\text{3D})$$

其中 $a_1,a_2,a_3$ 是沿各坐标轴的**位移量 (shifts)**。

**从点 $A$ 到点 $B$ 的向量 $\overrightarrow{AB}$**：

若 $A=(x,y)$，$B=(x+a_1,\ y+a_2)$，则

$$\overrightarrow{AB}=\langle a_1,\,a_2\rangle$$

即向量 $\overrightarrow{AB}$ 描述从 $A$ 到 $B$ 的**位移 (displacement)**。三维同理：$A=(x,y,z)$，$B=(x+a_1,y+a_2,z+a_3)$，$\overrightarrow{AB}=\langle a_1,a_2,a_3\rangle$。

**一般公式（最重要的操作规则）**：设 $A=(a_1,a_2,a_3)$，$B=(b_1,b_2,b_3)$，则

$$\boxed{\ \overrightarrow{AB}=\vec{v}=\langle b_1-a_1,\ b_2-a_2,\ b_3-a_3\rangle\ }$$

$$\boxed{\ \overrightarrow{BA}=\langle a_1-b_1,\ a_2-b_2,\ a_3-b_3\rangle=-\overrightarrow{AB}\ }$$

**箭头上的方向很重要**：$\overrightarrow{AB}$ 与 $\overrightarrow{BA}$ 是**互为相反数**的两个向量（大小相同、方向相反）。

> ⚠️ **手册措辞勘误（大坑！）**：手册与讲座都说 "Using a **start minus end** approach"（起点减终点）。但**手册自己的解答（Q10.3）明确写的是 "we subtract coordinates of the starting point from the ending point"**，即 **终点减起点 (end − start)**，且数值答案也验证了这一点。
>
> **正确记法**：$\overrightarrow{AB} = B - A$（**头减尾 / 终点减起点**）。"start minus end" 那句话可以理解为"从 start 出发、把 start 减掉"的口语，但**照字面算会全错**。

### 2.4 单位向量 (Unit vectors) 与笛卡尔形式 (Cartesian form)

本课只用**笛卡尔形式 (Cartesian form)**，即把向量拆成沿 $x,y,z$ 的分量：

- 沿 $x$ 的分量记作 $\hat{i}$
- 沿 $y$ 的分量记作 $\hat{j}$
- 沿 $z$ 的分量记作 $\hat{k}$

$\hat{i},\hat{j},\hat{k}$ 称为**单位向量 (unit vectors)**，**长度恒为 1**（帽子 $\hat{\ }$ 就是"单位"的意思）。

$$\hat{i}=\langle1,0,0\rangle,\quad \hat{j}=\langle0,1,0\rangle,\quad \hat{k}=\langle0,0,1\rangle$$

**两种记号完全等价**：

$$4\hat{i}+3\hat{j}\ \equiv\ \langle 4,\,3\rangle$$

含义：**每沿 $x$ 移动 4 个单位，就沿 $y$ 移动 3 个单位**。

> 讲座补充：除笛卡尔坐标外还有**极坐标 (polar coordinates)**（用角度与半径描述），但**本课不涉及**，只用笛卡尔（"大致就像经度和纬度，看的是平的东西"）。

### 2.5 向量的模 (Magnitude)

**定义与公式（本质就是勾股定理 Pythagoras' theorem）**：若 $\bar{a}=a_1\hat{i}+a_2\hat{j}+a_3\hat{k}$，则

$$\boxed{\ |\bar{a}| = \sqrt{a_1^2+a_2^2+a_3^2}\ }$$

二维情形：$|\bar a|=\sqrt{a_1^2+a_2^2}$。也写作 $\|\bar a\|$。

**几何意义**：向量"走了多远"、位移的**长度**。向量越长，模越大。

**适用条件**：分量必须是**同一直角坐标系下相互正交的分量**（笛卡尔）。非正交坐标系下这个公式不成立（本课不涉及）。

### 2.6 求某向量方向上的单位向量（归一化 Normalisation）

**定义**：与 $\bar a$ **同方向、长度为 1** 的向量称为 $\bar a$ 的单位向量。

**方法**：把 $\bar a$ 的**每一个分量都除以它的模**：

$$\boxed{\ \hat{a}=\frac{\bar{a}}{|\bar{a}|}=\left\langle \frac{a_1}{|\bar a|},\ \frac{a_2}{|\bar a|},\ \frac{a_3}{|\bar a|}\right\rangle\ }\qquad\text{满足 } |\hat a| = 1$$

**用途（核心思想：方向与大小分离）**：
$$\text{任意向量} = \underbrace{|\bar a|}_{\text{大小 how much}}\times\underbrace{\hat a}_{\text{方向 which way}}$$
例如已知运动方向 $\hat u$ 与速率 (speed) $v$，则速度向量 (velocity) $= v\,\hat u$。这正是 Q10.5 的解题钥匙。

**适用条件 / 常见误用**：**零向量 $\vec 0$ 没有单位向量**（会除以 0）。另外，**先归一化再乘速率**，不能直接把速率乘在未归一化的方向向量上（否则模就不是速率了）——这是 Q10.5 最典型的错法。

### 2.7 向量算术 (Vector arithmetic)

所有运算都是 **逐分量 (component-wise)** 进行的。

**(1) 加法 (Addition)**：设 $\vec a=\langle a_1,a_2,a_3\rangle$，$\vec b=\langle b_1,b_2,b_3\rangle$，则

$$\boxed{\ \vec a+\vec b=\langle a_1+b_1,\ a_2+b_2,\ a_3+b_3\rangle\ }$$

**几何意义（首尾相接法 / 三角形法则）**：先沿 $\vec a$ 走，再从 $\vec a$ 的终点沿 $\vec b$ 走，**最终到达的位置**就是 $\vec a+\vec b$（手册 Figure 11.4）。讲座原话："你先沿 a 走到那里，再从那里沿 b 走过去。" 等价地也可以用**平行四边形法则**。加法**可交换**：$\vec a+\vec b=\vec b+\vec a$。

**(2) 减法 (Subtraction)**：

$$\boxed{\ \vec a-\vec b=\langle a_1-b_1,\ a_2-b_2,\ a_3-b_3\rangle\ }$$

**几何意义（Figure 11.5）**：把 $\vec a-\vec b$ 理解为 $\vec a+(-\vec b)$——先沿 $\vec a$ 走，再沿 $\vec b$ 的**反方向**走回来。讲座描述："你先往上走，然后再往下走，因为你在减方向上。" 另一个非常有用的几何解读：**$\vec b-\vec a$ 就是从 $\vec a$ 的终点指向 $\vec b$ 的终点的向量**——这正是 §2.3 的 $\overrightarrow{AB}=B-A$，也是"两点间距离 = $|\vec b - \vec a|$"的来源（Q10.5 用的就是它）。

**(3) 数乘 (Multiplication by a scalar)**：设 $c$ 为常数（标量），则

$$\boxed{\ c\,\vec a=\langle c\,a_1,\ c\,a_2,\ c\,a_3\rangle\ },\qquad |c\vec a| = |c|\,|\vec a|$$

**几何意义（Figure 11.6，以 $\vec a=\langle 2,4\rangle$ 为例）**：
- $c>1$：**沿原方向拉长**（如 $2\vec a=\langle4,8\rangle$，长度加倍，方向不变）；
- $0<c<1$：**缩短**（如 $\tfrac12\vec a=\langle1,2\rangle$）；
- $c<0$：**长度按 $|c|$ 缩放，方向完全反转**（如 $-\vec a=\langle-2,-4\rangle$）。手册强调："当我们把原向量乘以负数时，就是简单地把行进方向掉头。"
- $c=0$：得到零向量。

**物理意义（手册的引入方式）**：设某单位向量描述每秒的行进方向，若已知物体速率为 15 m/s，则**位置改变 = 速率 × 单位方向向量**；这个新向量就是**速度 (velocity)**。这就是"数乘"在物理里的典型用法。

**(4) 讲义例题（幻灯片第 17 页）**：设 $\bar a=\langle4,3\rangle=4\hat i+3\hat j$，$\bar b=\langle2,1\rangle=2\hat i+1\hat j$，$c=2$：

$$\vec a+\vec b=\langle 4+2,\ 3+1\rangle=\langle 6,4\rangle$$
$$\vec a-\vec b=\langle 4-2,\ 3-1\rangle=\langle 2,2\rangle$$
$$c\,\vec a=\langle 2\times4,\ 2\times3\rangle=\langle 8,6\rangle$$
$$|\bar a|=\sqrt{4^2+3^2}=\sqrt{16+9}=\sqrt{25}=5$$

> ⚠️ 幻灯片原文把 $\bar b$ 也误写成 "$=4\hat i+3\hat j$"（复制粘贴错误），正确应为 $\bar b=\langle2,1\rangle=2\hat i+\hat j$；transcript 中讲师当场口头更正了（"that should say 2i plus 1j"）。

> 📌 **本课范围说明**：本周**没有讲点积 (dot product / scalar product) 与叉积 (cross product / vector product)**。Lecture、practical、习题与手册第 11 章**全部未出现**，因此**不在考纲内**。为知识完整性，笔记末尾 §6.7 附一小段「拓展（本课未考）」，复习时可跳过。

### 2.8 偏微分 (Partial differentiation) —— 本周最核心的概念转变

#### (a) 为什么需要它

一维曲线的梯度 $\dfrac{dy}{dx}$ 很直观：一条曲线上某点的斜率。但当函数是 $z=f(x,y)$（一个**曲面 / 标量场**）时，"斜率"这个说法**本身就不完整**了——站在山坡上，你朝北的坡度和朝东的坡度不一样。所以必须**指明沿哪个方向**求变化率。

#### (b) 核心定义（务必背下这句话）

$$\boxed{\ \text{求 }\frac{\partial f}{\partial x}\text{ 时，把 } y,z,\dots \text{ 全部当作常数 (constant)，然后按普通微分法则对 } x \text{ 求导。}\ }$$

手册原话："当函数用多于一个维度表达时，这意味着当你计算比如对 $x$ 的导数时，你**假定 $y$ 或 $z$ 这些其他变量保持不变**。我们只关心**沿分母中那个变量所给定的轴**的信息。"

讲座原话（更口语）："differentiate as normal but assume that other variables such as $y$ or $z$ remain constant"。

#### (c) 记号的改变（**这是本周最重要的符号转变**）

| 单变量（Week 1–9） | 多变量（Week 10 起） |
|---|---|
| $\dfrac{df}{dx}$、$\dfrac{dy}{dx}$ | $\dfrac{\partial f}{\partial x}$、$\dfrac{\partial f}{\partial y}$、$\dfrac{\partial f}{\partial z}$ |
| 直体的 **d**（"normal d"） | **卷曲的 ∂**（"curly d"，读作 "partial" / "del" / "der"） |
| **常微分 (ordinary derivative)** | **偏导数 (partial derivative)** |
| $f$ 只有一个自变量 | $f$ 有 ≥2 个自变量 |

> 讲座："the curly d basically means a partial differentiation and the normal d represents normal differentiation."
>
> **考试中若把 $\partial$ 写成 $d$（或反过来）会被视为概念错误**——因为它们表达的意思真的不同：$\frac{df}{dx}$ 表示"$f$ 的全部变化都来自 $x$"，$\frac{\partial f}{\partial x}$ 表示"只看 $x$ 引起的那部分变化，其余方向冻结"。

#### (d) 偏导 vs 常导：把这个区别彻底讲透

设 $f(x,y)=x^2+y^2$。

- **常微分的世界**：只有 $x$ 一个自变量，$\frac{d}{dx}$ 沿唯一的一条数轴度量变化。
- **偏微分的世界**：函数是一张**曲面**。$\frac{\partial f}{\partial x}$ 的几何含义是：**用平面 $y=\text{const}$ 去切这张曲面**，得到一条一维曲线，$\frac{\partial f}{\partial x}$ 就是**这条切出来的曲线的普通斜率**。同理 $\frac{\partial f}{\partial y}$ 是用 $x=\text{const}$ 去切。

$$\frac{\partial f}{\partial x}=2x\quad(\text{把 }y^2\text{ 视为常数，导数为 }0),\qquad \frac{\partial f}{\partial y}=2y\quad(\text{把 }x^2\text{ 视为常数，导数为 }0)$$

> 讲座现场问答：「对 $x$ 求导，你剩下 $y^2$，你假定其他变量保持常数。常数的导数是什么？」——「零。」这就是**为什么不含 $x$ 的整项直接消失**。

**一句话总结**：偏微分**没有任何新的求导技巧**——链式法则 (chain rule)、乘积法则 (product rule)、商法则 (quotient rule)、幂法则统统照旧；**唯一的新东西是"哪些字母现在是常数"**。

#### (e) 有限差分近似 (Finite difference)——与 Week 1 的衔接

手册指出：概念上，要在点 $(a,b)$ 求变化率，就是"固定 $y$、改变 $x$"。如果用**有限差分法 (method of finite difference)**（Week 1 "Calculating Gradients" 的数值方法），可写作：

$$\frac{\partial f}{\partial x}\bigg|_{(a,b)}\approx\frac{f(a+h,\,b)-f(a,\,b)}{h},\qquad \frac{\partial f}{\partial y}\bigg|_{(a,b)}\approx\frac{f(a,\,b+h)-f(a,\,b)}{h}$$

注意**第二个自变量在两个函数值中完全一致**——这正是"固定其他变量"的算术体现。手册接着说："当然本例我们不需要用有限差分，因为我们可以直接套用微分法则。"

> 🌍 **地球科学意义**：真实数据（DEM 高程栅格、卫星温度网格、模式输出）都是离散的，**没有解析表达式**，所以实际算坡度、算气压梯度力时用的正是上式这种有限差分。解析法与数值法互为验证——这也是往年考卷 Q6「比较数值速率与解析速率」的思路。

### 2.9 梯度 (Gradient, grad, $\nabla f$)

#### (a) 定义

一维用 $\frac{dy}{dx}$ 表示梯度；多维时需要一个新东西，标准记号叫 **'grad'**，写作 $\mathrm{grad}(f)$ 或 $\nabla f$（$\nabla$ 读作 **nabla** 或 **del**）。

$$\boxed{\ \nabla f=\mathrm{grad}(f)=\frac{\partial f}{\partial x}\hat{i}+\frac{\partial f}{\partial y}\hat{j}+\frac{\partial f}{\partial z}\hat{k}=\left\langle \frac{\partial f}{\partial x},\ \frac{\partial f}{\partial y},\ \frac{\partial f}{\partial z}\right\rangle\ }$$

二维情形：$\nabla f=\left\langle \dfrac{\partial f}{\partial x},\ \dfrac{\partial f}{\partial y}\right\rangle$。

#### (b) 最关键的一句话

$$\boxed{\ f \text{ 是标量场，但 } \nabla f \text{ 是一个\textbf{向量}。}\ }$$

手册与讲义都特别强调："We note that $\nabla f$ (where $f=f(x,y,z)$ is a scalar field) is **actually a vector**." 所以：

$$\text{标量场}\ \xrightarrow{\ \nabla\ }\ \text{向量场}$$

**这就是本周把「向量」和「偏微分」放在同一章的原因**——你必须先会向量，才能表达多变量的导数。讲座原话："largely this is where vectors come in, because you end up creating a 2D vector."

#### (c) 梯度的几何 / 物理意义

$$\nabla f\ \text{同时携带两条信息：}\quad\underbrace{\text{方向 direction}}_{\text{往哪边变化}}\ +\ \underbrace{\text{大小 magnitude}}_{\text{变得多快}}$$

- **方向**：指向函数**增长最快 (steepest ascent)** 的方向；$-\nabla f$ 指向**下降最快**的方向。
- **大小** $|\nabla f|$：那个最陡方向上的**陡峭程度**（坡度）。
- 梯度向量**垂直于等值线 / 等值面**（contour lines）——这解释了为什么 Figure 11.2 的箭头总是穿过 Figure 11.1 的等值线。

> 讲座："the gradient will tell you both the direction... 如果你想知道梯度朝哪个方向走、以及它有多陡，方向由向量本身告诉你，多快/多陡由**模**告诉你。"

#### (d) 梯度的模

$$\boxed{\ |\nabla f|=\sqrt{\left(\frac{\partial f}{\partial x}\right)^2+\left(\frac{\partial f}{\partial y}\right)^2+\left(\frac{\partial f}{\partial z}\right)^2}\ }$$

**用途**：任意点处**最陡坡度的数值**。Q10.7 就是标准考法。

#### (e) 多变量下的驻点 / 极值（讲座提到的延伸）

一维求极值是令 $\frac{dy}{dx}=0$（Week 4 Optimisation）。多维下的对应做法：**令梯度向量为零向量**，即

$$\nabla f=\vec{0}\quad\Longleftrightarrow\quad \frac{\partial f}{\partial x}=0\ \text{且}\ \frac{\partial f}{\partial y}=0$$

讲座的说法是"求出梯度向量、取模、令其等于零"（$|\nabla f|=0 \Leftrightarrow \nabla f=\vec 0$，因为各分量平方和为 0 要求每个分量都是 0，两种说法等价）。讲师说这"会是个更难的问题，但大致就是这么做"——属于**理解性延伸，非重点考点**。

> ⚠️ 注意：多维情形下 $\nabla f=\vec0$ 的点可能是**极大、极小或鞍点 (saddle point)**（如 $f=xy$ 在原点），判别需要二阶偏导矩阵，**本课不要求**。

### 2.10 二阶偏导与偏微分方程 (PDEs) —— 明确超纲

**二阶偏导**：可以对 $f$ 再次求偏导，得到

$$\frac{\partial^2 f}{\partial x^2},\quad \frac{\partial^2 f}{\partial y^2},\quad \frac{\partial^2 f}{\partial x\,\partial y},\quad \frac{\partial^2 f}{\partial y\,\partial x}$$

手册与讲义把这四个量排成的对象记作 $\nabla^2 f$，并说明：**因为要对所有变量组合各微分两次，$\nabla^2 f$ 变成一个矩阵 (matrix)**，它"在数学与物理中有奇妙的性质，但超出本课范围"。

> ⚠️ **记号提醒（重要，避免以后混淆）**：主流数学/物理文献中 $\nabla^2 f$ 通常指 **Laplacian（拉普拉斯算子）** $\nabla^2f=\frac{\partial^2f}{\partial x^2}+\frac{\partial^2f}{\partial y^2}+\frac{\partial^2f}{\partial z^2}$，那是一个**标量**；而二阶偏导排成的**矩阵**通常叫 **Hessian（黑塞矩阵）**。本课讲义把矩阵记成 $\nabla^2f$，属于**本课自用的简化说法**。考本课时照讲义答即可，但读别的书时要留心。

**偏微分方程 (Partial Differential Equations, PDEs)**：

- 解析积分 PDE **只有很简单的情形能做**，一般需要 **Fourier 方法 (Fourier methods)**，**超出本课范围**；
- **几乎所有现代天气预报模式都是用近似（数值）方法求解 PDE 的**。讲座点名："the Met Office when they do weather forecasting — that entire process they build is built on partial differential equations."
- 讲师明确表示：**"我不会要求你们做这个"**——本周只要求**会求偏导数、会组装梯度向量、会算模**。
- 讲师提到明年的 **mathematical modelling** 课会用计算方法进一步处理这些内容。

---

## 三、公式与图表

### 3.1 公式速查表

| 主题 | 公式 | 适用条件 / 备注 |
|---|---|---|
| 标量场 | $f(x,y)$ 或 $f(x,y,z)\to$ 一个数 | 有大小无方向 |
| 向量场 | $\vec F(x,y)=\langle F_1,F_2\rangle$ | 有大小有方向 |
| 向量 vs 坐标 | $\langle a_1,a_2\rangle$ ≠ $(a_1,a_2)$ | 尖括号=向量，圆括号=点 |
| 两点连线向量 | $\overrightarrow{AB}=\langle b_1-a_1,\ b_2-a_2,\ b_3-a_3\rangle$ | **终点减起点**；$\overrightarrow{BA}=-\overrightarrow{AB}$ |
| 笛卡尔单位向量 | $\hat i,\hat j,\hat k$，长度均为 1 | $a_1\hat i+a_2\hat j\equiv\langle a_1,a_2\rangle$ |
| 模 (magnitude) | $\vert\bar a\vert=\sqrt{a_1^2+a_2^2+a_3^2}$ | 勾股定理；仅正交笛卡尔分量适用 |
| 单位向量（归一化） | $\hat a=\dfrac{\bar a}{\vert\bar a\vert}$ | $\vert\hat a\vert=1$；$\bar a\ne\vec 0$ |
| 加法 | $\vec a+\vec b=\langle a_1+b_1,\ a_2+b_2,\ a_3+b_3\rangle$ | 逐分量；三角形/平行四边形法则 |
| 减法 | $\vec a-\vec b=\langle a_1-b_1,\ a_2-b_2,\ a_3-b_3\rangle$ | $=\vec a+(-\vec b)$ |
| 数乘 | $c\vec a=\langle ca_1,\ ca_2,\ ca_3\rangle$ | $c<0$ 反向；$\vert c\vec a\vert=\vert c\vert\vert\vec a\vert$ |
| 速度分解 | $\vec v=(\text{speed})\times\hat u$ | 必须先把方向向量**归一化** |
| 偏导数 | $\dfrac{\partial f}{\partial x}$：其余变量视为常数 | 求导法则全部照旧 |
| 有限差分 | $\dfrac{\partial f}{\partial x}\approx\dfrac{f(a+h,b)-f(a,b)}{h}$ | 数值近似；$h$ 要小 |
| 梯度 | $\nabla f=\left\langle \dfrac{\partial f}{\partial x},\dfrac{\partial f}{\partial y},\dfrac{\partial f}{\partial z}\right\rangle$ | 输入标量场，输出**向量** |
| 梯度的模 | $\vert\nabla f\vert=\sqrt{f_x^2+f_y^2+f_z^2}$ | 最陡坡度的数值 |
| 多维驻点 | $\nabla f=\vec 0$ | 延伸内容，非重点 |
| 二阶 | $\nabla^2 f$（本课语境=二阶偏导矩阵） | **超纲**，仅需知道存在 |

### 3.2 会用到的单变量求导法则（本周全部照旧使用）

| 法则 | 公式 |
|---|---|
| 幂法则 Power rule | $\dfrac{d}{dx}x^n=nx^{n-1}$ |
| 乘积法则 Product rule | $(uv)'=u'v+uv'$ |
| 商法则 Quotient rule | $\left(\dfrac{u}{v}\right)'=\dfrac{u'v-uv'}{v^2}$ |
| 链式法则 Chain rule | $\dfrac{dy}{dx}=\dfrac{dy}{du}\cdot\dfrac{du}{dx}$ |
| 指数 | $\dfrac{d}{dx}e^{g(x)}=g'(x)e^{g(x)}$ |
| 三角 | $\dfrac{d}{dx}\sin(kx)=k\cos(kx)$；$\dfrac{d}{dx}\cos(kx)=-k\sin(kx)$ |
| 根式 | $\dfrac{d}{dx}\sqrt{x}=\dfrac{1}{2\sqrt x}$ |

> 讲座提醒：考试会**提供一张微分与积分常用法则表** (table of common laws)，与手册最后几章那张表完全相同，含链式/乘积/商法则及常见微分、常见积分。**但仍需熟练到不用查**，表只当核对用。

### 3.3 图表判读要点

**Figure 11.1（三个标量场彩色图）**
- 判读顺序：① 看**对称性**（沿某轴均匀 → 该轴变量不出现）；② 看**等值线形状**（竖直线 = 只含 $x$；同心圆 = 含 $x^2+y^2$；双曲线/四象限交替 = 含 $xy$）；③ 看**明暗**（白=高，黑=低）定极值位置。
- **易错**：$f=x^2$ 的最小值不是"一个点"，而是**整条直线 $x=0$**；对应梯度 $\nabla f=\langle 2x,0\rangle$ 在整条 $y$ 轴上都为零向量。

**Figure 11.2（三个向量场箭头图）**
- 箭头**方向** = 流向；箭头**长度** = 大小。
- 左、中两图**大小相同、方向相反**，都可对应 $f=x^2$（一个是 $+\nabla f$、一个是 $-\nabla f$）。
- 记住"梯度箭头垂直穿过等值线"这条判读规则。

**Figure 11.3（同一向量、不同起点）**
- 四条线段起点不同（如从 $(-4,-3)$ 到 $(-6,2)$、从 $(3,-6)$ 到 $(1,-1)$ 等），但**都表示同一个向量 $\langle-2,5\rangle$**。
- 结论：**向量与位置无关，只由"位移量"定义**（这叫自由向量 free vector）。

**Figure 11.4 / 11.5（向量加减的可视化）**
- 11.4：$\vec a$ 首尾接 $\vec b$，合成 $\vec a+\vec b$。
- 11.5：$\vec a-\vec b=\vec a+(-\vec b)$，把 $\vec b$ 掉头再接上。

**Figure 11.6（数乘的可视化，以 $\vec a=\langle2,4\rangle$ 为例）**
- 由 $\vec a$ 派生的三个向量（放大、缩小、反向），全部与 $\vec a$ **共线**。

---

## 四、课堂补充（transcript 独有内容）

本周 transcript 的**前三分之一几乎全是考试信息**，是极高价值的独有内容，务必保留。

### 4.1 期末考试 (Exam) 全套信息

| 项目 | 内容 |
|---|---|
| 时长 | **2 小时**笔试 |
| 总分 | **100 分** |
| 题数 | **10 题，每题 10 分** |
| 出题范围 | **前 10 周内容**，与去年结构相同 |
| 配比 | **5 题微分 + 5 题积分** |
| 难度 | **Q1 最易，Q10 最难，逐题递增** |
| 答题 | 发**答题册 (booklet)**，全部写在册子里 |
| 计算器 | **允许**，但**不得存储文本、不得做代数运算、不得有图形功能** |
| 公式表 | **会提供**常用微分/积分法则表，与手册末章那张**完全相同** |
| 日期 | 讲师**明确表示不知道**（去年是学期最后一天；通常大模块排前面但不保证） |

### 4.2 讲师最强调的一件事：**必须写出过程 (show your working)**

讲师在这一点上反复强调了三遍以上，原话要点：

- 「**只给最终答案、答案又错 → 直接 0 分。**」
- 「给了最终答案是错的，但**给了方法**，我能看出你只是犯了个很小的错误 → 我可以给你 7、8 分。」
- 「小错误（比如把加号写成减号）我只扣 1–2 分，后面照样能拿 8–9 分，因为有**跟随分 (follow-through marks)**：前面某一步算错，只要后续方法正确、逻辑连贯，仍然给分。」
- 「**分数不只给答案，也给过程 (the marks are not just for the answer, they are for the working)。** 这就是为什么我上课总用很啰嗦的方式演示步骤。」
- 学生问「如果我答案完全正确但跳过了过程，能拿满分吗？」讲师答：**「大体上没问题，但你在冒险」**——答对拿 10 分，答错拿 0 分，是全有或全无；写了过程就有中间分兜底。
- 「去年**非常多人某些题拿 0 分，纯粹是因为只写了答案不写过程。**」

### 4.3 考试策略（讲师亲授）

- **不要按 1→10 的顺序做**。翻开卷子，**先做你最有把握的题**（play to your strengths）。
- 例如：如果你对链式法则很熟、对流体静力学方程 (hydrostatic equation) 没把握，就先做前者。
- 想先做完所有微分题再做积分题（或反之）**完全可以**。
- 先把"喜欢做的题"全部做完，再回头攻难题——**这样才能最大化分数**。

### 4.4 往年卷 (past paper) 的题型分布（讲师逐题过了一遍）

讲师展示了去年真题，题目走向如下（可作为复习靶子）：

| 题号 | 题型 |
|---|---|
| Q1 | **判断题 (true or false)**，考微分基本法则 |
| Q2 | 积分基本法则 |
| Q3–Q4 | **求根 (root finding)**、**定积分 (definite integration)** |
| Q5 | **最优化 (optimisation)**，函数较复杂，需用乘积/商/链式法则 |
| Q6 | **速率 (rates)**：比较**数值速率与解析速率** |
| Q7 | 更复杂函数，需**乘积法则** |
| Q8 | **牛顿定律 (Newton's laws)** 相关 |
| Q9 | 没见过的 **ODE**，需要求解，会用到**换元积分 (integration by substitution)** |
| Q10 | **流体静力学方程 (hydrostatic equation)**——"你会见到的最难的 ODE"，要求积分 |

**往年卷的发放安排**：
- 往年卷已上传 Blackboard，在新建的 **"Easter break" 文件夹**里；
- **复活节期间不发解答/评分标准 (mark scheme)**——讲师说"这是让你练习考试题型的复习工具"；
- 解答将在复活节后的**两次复习课上现场讲解**：5 月 2 日讲微分（含卷中 5 道微分题），5 月 9 日讲积分（含 5 道积分题），**讲完之后才发布解答**；
- 手册与 practical 中的**所有题目本来就都有解答，且已在线可得**。

### 4.5 复活节后的安排

- Week 11（05/02，即 2 May）：**Revision: Differentiation** — 先做方法总复习 (recap lecture)，再讲往年卷的 5 道微分题，然后 **Q&A**，最后转入 practical 时段自由复习。
- Week 12（09 May）：**Revision: Integration** — 同样结构。
- 复习课的 practical 时段是**开放式 workshop**：讲师与 GTA 在场，可以问**整门课任何一周**的问题。

### 4.6 上周（Week 9）回顾——讲师开场复述的内容

（本周开头讲师快速复述了 Week 9，可作为纵向复习索引）

- **二阶 ODE**：形如 $a\dfrac{d^2y}{dx^2}+b\dfrac{dy}{dx}+cy=0$（**齐次、线性、二阶 ODE**）。
- 解法：先写**辅助方程 (auxiliary equation)** $a\lambda^2+b\lambda+c=0$，用求根公式解出 $\lambda_{1,2}$：
  - $\lambda_1\ne\lambda_2$ 且为实数（即 $b^2-4ac>0$）：$y=Ae^{\lambda_1x}+Be^{\lambda_2x}$；
  - $\lambda_1=\lambda_2$（$b^2-4ac=0$）：$y=(A+Bx)e^{\lambda x}$；
  - $b^2-4ac<0$（复根）：**有解，但本课不涉及**。
- 用**初始条件 (initial conditions)** 定 $A,B$ → 解**联立方程 (simultaneous equations)**。
- **特例 $b=c=0$**：直接**积分两次**即可（因为线性函数微分两次得 0），此时用**边界条件 (boundary conditions)**。
- **初值问题 vs 边值问题**：初值问题在**同一点**（通常 $x=0$）给出函数值及其导数值；边值问题在**两个端点** $x=x_0$ 与 $x=x_1$ 各给一个条件，解必须**同时满足两端**。
- **Fick 定律与 Fourier 定律**描述质量与热量的传输；**稳态 (steady state)** 假设下得到二阶 ODE，积分两次 + 边界条件即可求解。

### 4.7 讲师口头强调的其它要点

- 关于"为什么现在讲向量"："largely this is where vectors come in"——因为多变量求导的结果**天然是一个向量**，不先学向量就没法表达它。
- 关于难度："it's much easier than it seems"（偏微分本身不难，难的是记号）。
- 关于 $\nabla^2 f$："如果你像我一样是个数学 nerd，它有非常可爱的性质，但我不会拿这个烦你们"——**明确不考**。
- 关于 PDE 积分："**really really difficult，我不会要求你们做**"，实际都靠数值方法。
- 明年的 **mathematical modelling** 课会用计算机做这些事（"像你跟 Dave 做的那样"），而不是手算。
- 结课语："that's everything I have to teach... well done for making it through 10 weeks of mathematics."

---

## 五、Practical 要点

本周 practical 分两块：**幻灯片上的 2 道课堂练习**（`practical10_soln(1).md`），以及**手册习题 Q10.1–Q10.9**（`Exercises10.md` / `Solutions10.md`）。目标就是三条 ILO：辨识标量场/向量场、做向量运算、求偏导并组装梯度向量。

> ⚠️ 说明：`Solutions10.md` 的解答**公式几乎全是图片**，转 md 后只剩文字提示。以下所有推导为笔者据题目与文字提示**完整重建并验算**，数值与原解答给出的数字（如 Q10.5 的 145.1、Q10.2 的 $\sqrt{50}$）一致。

---

### 5.1 Practical 幻灯片 Exercise 1：向量计算

**题目**：设 $\vec a=\langle5,3\rangle$，$\vec b=\langle-2,5\rangle$，$\vec c=\langle-1,3,5\rangle$。求 (a) $3\vec c$；(b) $\vec a-\vec b$；(c) $10\vec b-3\vec a$；(d) $|\vec c|$；(e) $|\vec b-\vec a|$。

**(a) $3\vec c$** — 数乘，逐分量乘 3：
$$3\vec c=\langle 3\times(-1),\ 3\times3,\ 3\times5\rangle=\langle -3,\ 9,\ 15\rangle$$

**(b) $\vec a-\vec b$** — 逐分量相减：
$$\vec a-\vec b=\langle 5-(-2),\ 3-5\rangle=\langle 7,\ -2\rangle$$
（注意 $5-(-2)=7$，**负负得正**，这是最常见的失分点。）

**(c) $10\vec b-3\vec a$** — 先各自数乘，再相减（幻灯片给的完整步骤）：
$$10\vec b=\langle 10\times(-2),\ 10\times5\rangle=\langle -20,\ 50\rangle$$
$$3\vec a=\langle 3\times5,\ 3\times3\rangle=\langle 15,\ 9\rangle$$
$$10\vec b-3\vec a=\langle -20,50\rangle-\langle 15,9\rangle=\langle -20-15,\ 50-9\rangle=\langle -35,\ 41\rangle$$

**(d) $|\vec c|$** — 三维模：
$$|\vec c|=\sqrt{(-1)^2+3^2+5^2}=\sqrt{1+9+25}=\sqrt{35}\approx 5.92$$

**(e) $|\vec b-\vec a|$** — 先减后取模：
$$\vec b-\vec a=\langle -2-5,\ 5-3\rangle=\langle -7,\ 2\rangle$$
$$|\vec b-\vec a|=\sqrt{(-7)^2+2^2}=\sqrt{49+4}=\sqrt{53}\approx 7.28$$

> **解题技巧**：$|\vec b-\vec a|=|\vec a-\vec b|$——**两点间距离与方向无关**，取模会把负号平方掉。但**向量本身** $\vec b-\vec a\ne\vec a-\vec b$。
>
> **注意维数**：$\vec a,\vec b$ 是二维，$\vec c$ 是三维——**不同维数的向量不能相加减**。本题刻意把 $\vec c$ 单列，就是要你注意这一点。

---

### 5.2 Practical 幻灯片 Exercise 2：偏微分（三变量）

**题目**：设标量场 $f(x,y,z)=xyz+yz+xz^2$，求所有偏导数并写出梯度向量 $\nabla f$。

**解法（幻灯片逐项拆解，是最好的示范）**：

**对 $x$ 求偏导**（把 $y,z$ 当常数，逐项处理）：

| 项 | 对 $x$ 的偏导 | 理由 |
|---|---|---|
| $xyz$ | $yz$ | $yz$ 是常数系数，$\frac{\partial}{\partial x}(x)=1$ |
| $yz$ | $0$ | **不含 $x$** → 整项是常数 |
| $xz^2$ | $z^2$ | $z^2$ 是常数系数 |

$$\boxed{\frac{\partial f}{\partial x}=yz+z^2}$$

**对 $y$ 求偏导**（把 $x,z$ 当常数）：

| 项 | 对 $y$ 的偏导 |
|---|---|
| $xyz$ | $xz$ |
| $yz$ | $z$ |
| $xz^2$ | $0$（不含 $y$） |

$$\boxed{\frac{\partial f}{\partial y}=xz+z}$$

**对 $z$ 求偏导**（把 $x,y$ 当常数）：

| 项 | 对 $z$ 的偏导 |
|---|---|
| $xyz$ | $xy$ |
| $yz$ | $y$ |
| $xz^2$ | $2xz$（幂法则：$z^2\to2z$，系数 $x$ 保留） |

$$\boxed{\frac{\partial f}{\partial z}=xy+y+2xz}$$

**组装梯度向量**：

$$\nabla f=\left\langle yz+z^2,\ \ xz+z,\ \ xy+y+2xz\right\rangle=(yz+z^2)\hat i+(xz+z)\hat j+(xy+y+2xz)\hat k$$

> **解题技巧（本周最实用的一条）**：**逐项列表法**。把函数拆成若干项，画一张"项 × 变量"的表，一格一格填。这样既不会漏项，也不会把"不含该变量的项"错误保留。考试中这张表本身就是**过程分**。

---

### 5.3 手册习题 Q10.1 — 求模

**题目**：(a) $\bar a=4\hat i+3\hat j$；(b) $\bar b=4\hat i-3\hat j$；(c) $\bar c=3\hat i+4\hat j+5\hat k$。

$$\text{(a)}\quad |\bar a|=\sqrt{4^2+3^2}=\sqrt{16+9}=\sqrt{25}=5$$
$$\text{(b)}\quad |\bar b|=\sqrt{4^2+(-3)^2}=\sqrt{16+9}=\sqrt{25}=5$$
$$\text{(c)}\quad |\bar c|=\sqrt{3^2+4^2+5^2}=\sqrt{9+16+25}=\sqrt{50}=5\sqrt2\approx 7.07$$

> **本题的教学点**：(a) 与 (b) **模完全相同**，因为**平方消掉了符号**。$\bar a$ 与 $\bar b$ 方向不同（一个指向右上、一个指向右下），但**长度一样**。这说明**模只描述大小，完全丢失方向信息**。

---

### 5.4 手册习题 Q10.2 — 求单位向量

**题目**：与 $3\hat i+4\hat j+5\hat k$ 同方向的单位向量是什么？

**解法（题目自带提示：先求模，再除）**：

1. 求模：$\|\bar v\|=\sqrt{3^2+4^2+5^2}=\sqrt{50}$
2. 归一化（每个分量除以 $\sqrt{50}$）：

$$\hat v=\frac{\bar v}{\|\bar v\|}=\frac{3}{\sqrt{50}}\hat i+\frac{4}{\sqrt{50}}\hat j+\frac{5}{\sqrt{50}}\hat k$$

有理化后（$\sqrt{50}=5\sqrt2$）：

$$\hat v=\frac{3}{5\sqrt2}\hat i+\frac{4}{5\sqrt2}\hat j+\frac{5}{5\sqrt2}\hat k=\frac{3\sqrt2}{10}\hat i+\frac{4\sqrt2}{10}\hat j+\frac{\sqrt2}{2}\hat k\approx 0.424\hat i+0.566\hat j+0.707\hat k$$

**验算（好习惯）**：$\left(\tfrac{3}{\sqrt{50}}\right)^2+\left(\tfrac{4}{\sqrt{50}}\right)^2+\left(\tfrac{5}{\sqrt{50}}\right)^2=\dfrac{9+16+25}{50}=\dfrac{50}{50}=1$ ✓

---

### 5.5 手册习题 Q10.3 — 由两点求向量

**题目**：(a) 从 $a=(2,-7,0)$ 到 $b=(1,-3,-5)$ 的向量；(b) 从 $a=(1,-3,-5)$ 到 $b=(2,-7,0)$ 的向量。

**解法（官方解答原话：把起点坐标从终点坐标中减去 = 终点 − 起点）**：

$$\text{(a)}\quad \vec v=b-a=\langle 1-2,\ \ -3-(-7),\ \ -5-0\rangle=\langle -1,\ 4,\ -5\rangle$$

$$\text{(b)}\quad \vec v=b-a=\langle 2-1,\ \ -7-(-3),\ \ 0-(-5)\rangle=\langle 1,\ -4,\ 5\rangle$$

> **本题的教学点**：(a) 与 (b) 恰好互为相反数 $\langle-1,4,-5\rangle=-\langle1,-4,5\rangle$——因为两题**起点终点对调**了。这直接验证了 $\overrightarrow{BA}=-\overrightarrow{AB}$。
>
> **常见误用**：被手册那句 "start minus end" 误导而算成 $a-b$。**认准解答里的原则：终点 − 起点**。另外**负数相减务必打括号**：$-3-(-7)=-3+7=4$。

---

### 5.6 手册习题 Q10.4 — 求模（含分数分量）

$$\text{(a)}\quad \vec a=\langle 3,-5,10\rangle:\qquad |\vec a|=\sqrt{3^2+(-5)^2+10^2}=\sqrt{9+25+100}=\sqrt{134}\approx 11.58$$

$$\text{(b)}\quad \vec p=\left\langle \frac{1}{\sqrt5},\ -\frac{2}{\sqrt5}\right\rangle:\qquad |\vec p|=\sqrt{\left(\frac{1}{\sqrt5}\right)^2+\left(-\frac{2}{\sqrt5}\right)^2}=\sqrt{\frac{1}{5}+\frac{4}{5}}=\sqrt{1}=1$$

> **本题的教学点**：(b) 的模恰为 1——它**本身就是一个单位向量**。出题人在暗示：$\langle 1,-2\rangle$ 除以自己的模 $\sqrt5$ 就得到 $\vec p$。看到分母带 $\sqrt{\ }$ 的分量组合，先猜它是归一化过的。

---

### 5.7 手册习题 Q10.5 — 两车距离（应用题，本周最典型的综合题）

**题目**：$t=0$ 时两车都在原点 $(0,0)$。A 车沿 $x$ 轴以 **30 mph** 行驶；B 车沿 **$3\hat i+4\hat j$ 方向**以 **60 mph** 行驶。3 小时后两车相距多少英里？

**解题思路（四步，官方解答的骨架）**：

**第 1 步：A 车位置。**
$$30\ \text{mph}\times3\ \text{h}=90\ \text{miles，沿 }x\text{ 轴}\quad\Rightarrow\quad \vec r_A=90\hat i=\langle 90,\ 0\rangle$$

**第 2 步：B 车走的总距离。**
$$60\ \text{mph}\times3\ \text{h}=180\ \text{miles}$$

**第 3 步：把 180 miles 分配到 $3\hat i+4\hat j$ 方向上（关键步！）。**

方向向量 $3\hat i+4\hat j$ **的模是 5**（$\sqrt{3^2+4^2}=5$），**不是 1**，所以必须先归一化：

$$\hat u=\frac{3\hat i+4\hat j}{5}=\left\langle \frac35,\ \frac45\right\rangle$$

$$\vec r_B=180\,\hat u=180\times\frac35\,\hat i+180\times\frac45\,\hat j=108\hat i+144\hat j=\langle 108,\ 144\rangle$$

**验算**：$|\vec r_B|=\sqrt{108^2+144^2}=\sqrt{11664+20736}=\sqrt{32400}=180$ ✓

**第 4 步：求两车间的向量并取模。**

$$\vec r_A-\vec r_B=\langle 90-108,\ 0-144\rangle=\langle -18,\ -144\rangle=-18\hat i-144\hat j$$

$$\text{distance}=\sqrt{(-18)^2+(-144)^2}=\sqrt{324+20736}=\sqrt{21060}\approx \boxed{145.1\ \text{miles}}$$

> **解题技巧**：
> 1. 题目提示"画个图会有帮助"——**先画图**：原点出发的两条射线，一条沿 $x$ 轴，一条斜向上，3 小时后连接两个端点。
> 2. **归一化是本题的命门**。若直接写 $\vec r_B=180\times\langle3,4\rangle=\langle540,720\rangle$，那 B 车实际跑了 900 英里，全错。
> 3. **两点距离 = 位置向量之差的模**，减的顺序无所谓（平方抵消符号）。
> 4. **$3$-$4$-$5$ 是最经典的勾股数**，看到 $3\hat i+4\hat j$ 就应该立刻反应出模 = 5。

---

### 5.8 手册习题 Q10.6 — 求梯度 grad

**通用步骤**：① 逐个变量求偏导（其余当常数）；② 把偏导数按顺序装进尖括号（或写成 $\hat i,\hat j,\hat k$ 形式）。

**(a) $f(x,y)=x^2\sin(5y)$**

- 对 $x$：把 $\sin(5y)$ **整体视为常数系数**，只对 $x^2$ 用幂法则：
$$\frac{\partial f}{\partial x}=2x\sin(5y)$$
- 对 $y$：把 $x^2$ 视为常数系数，对 $\sin(5y)$ 用链式法则（内函数 $5y$ 的导数是 5）：
$$\frac{\partial f}{\partial y}=x^2\cdot 5\cos(5y)=5x^2\cos(5y)$$
- 梯度：
$$\nabla f=\left\langle 2x\sin(5y),\ \ 5x^2\cos(5y)\right\rangle = 2x\sin(5y)\,\hat i+5x^2\cos(5y)\,\hat j$$

**(b) $f(x,y,z)=z\,e^{-xy}$**（三变量）

- 对 $x$：$z$ 为常数；指数的内函数 $-xy$ 对 $x$ 的导数是 $-y$：
$$\frac{\partial f}{\partial x}=z\cdot(-y)e^{-xy}=-yz\,e^{-xy}$$
- 对 $y$：同理，内函数对 $y$ 的导数是 $-x$：
$$\frac{\partial f}{\partial y}=z\cdot(-x)e^{-xy}=-xz\,e^{-xy}$$
- 对 $z$：$e^{-xy}$ 中**不含 $z$**，整体是常数系数，$\frac{\partial}{\partial z}(z)=1$：
$$\frac{\partial f}{\partial z}=e^{-xy}$$
- 梯度：
$$\nabla f=\left\langle -yz\,e^{-xy},\ \ -xz\,e^{-xy},\ \ e^{-xy}\right\rangle=e^{-xy}\left\langle -yz,\ -xz,\ 1\right\rangle$$

**(c) $f(x,y)=1\times10^{-3}(x-400)^2+1\times10^{-3}y^2$**

- 对 $x$：第二项不含 $x$ → 0；第一项用链式法则（内函数 $x-400$ 的导数为 1）：
$$\frac{\partial f}{\partial x}=1\times10^{-3}\cdot 2(x-400)\cdot 1=2\times10^{-3}(x-400)$$
- 对 $y$：第一项不含 $y$ → 0：
$$\frac{\partial f}{\partial y}=1\times10^{-3}\cdot 2y=2\times10^{-3}y$$
- 梯度：
$$\nabla f=\left\langle 2\times10^{-3}(x-400),\ \ 2\times10^{-3}y\right\rangle$$

> 🌍 **物理解读**：这个 $f$ 是一个**开口向上的抛物面（碗）**，最低点在 $(400,0)$（$\nabla f=\vec0$ 之处）。若把 $f$ 视为地形高程，梯度就是**坡度矢量**，处处指向"上坡"、即背离碗底的方向。

---

### 5.9 手册习题 Q10.7 — 梯度的模（沿用 Q10.6(c) 的场）

**题目**：对 $f(x,y)=1\times10^{-3}(x-400)^2+1\times10^{-3}y^2$，求对所有 $x,y$ 的梯度向量的模；并求 $(x,y)=(800,400)$ 处的值。

**第 1 步：偏导（同上）**
$$\frac{\partial f}{\partial x}=2\times10^{-3}(x-400),\qquad \frac{\partial f}{\partial y}=2\times10^{-3}y$$

**第 2 步：梯度向量**
$$\nabla f=\left\langle 2\times10^{-3}(x-400),\ 2\times10^{-3}y\right\rangle$$

**第 3 步：一般表达式（对所有 $x,y$）**
$$|\nabla f|=\sqrt{\left[2\times10^{-3}(x-400)\right]^2+\left[2\times10^{-3}y\right]^2}=2\times10^{-3}\sqrt{(x-400)^2+y^2}$$

（**技巧**：把公因子 $2\times10^{-3}$ **提到根号外**，式子立刻干净很多。注意提出时要取绝对值，此处系数为正无妨。）

**第 4 步：代入 $(800,400)$**
$$\frac{\partial f}{\partial x}\bigg|_{(800,400)}=2\times10^{-3}\times(800-400)=2\times10^{-3}\times400=0.8$$
$$\frac{\partial f}{\partial y}\bigg|_{(800,400)}=2\times10^{-3}\times400=0.8$$
$$\nabla f\big|_{(800,400)}=\langle 0.8,\ 0.8\rangle$$
$$|\nabla f|=\sqrt{0.8^2+0.8^2}=\sqrt{0.64+0.64}=\sqrt{1.28}\approx \boxed{1.13}$$

（用一般式验算：$2\times10^{-3}\sqrt{400^2+400^2}=2\times10^{-3}\times400\sqrt2=0.8\sqrt2\approx1.131$ ✓）

> **解读**：两个分量都是 0.8，说明该点最陡上坡方向是 $\langle1,1\rangle$ 方向，即**与 $x$ 轴成 45°**；最陡坡度约 1.13。

---

### 5.10 手册习题 Q10.8 — 求所有一阶偏导

**(a) $f(x,y)=x^4+6\sqrt{y}-10$**

- 对 $x$：**第二、三项都不含 $x$，恒为 0**（解答原话："The second and third term in the expression always differentiate to 0 for $x$"）：
$$\frac{\partial f}{\partial x}=4x^3$$
- 对 $y$：$x^4$ 与 $-10$ 都是常数 → 0；$6\sqrt y=6y^{1/2}$：
$$\frac{\partial f}{\partial y}=6\cdot\frac12 y^{-1/2}=3y^{-1/2}=\frac{3}{\sqrt y}$$

**(b) $f(x,y)=\cos\!\left(\dfrac{4}{x}\right)e^{\,x^2y-5y^3}$**

**对 $x$——需要乘积法则 (product rule)**，因为**两个因子都含 $x$**（解答明确指出这一点）。

拆分：$u=\cos\!\left(\dfrac4x\right)$，$v=e^{\,x^2y-5y^3}$

$$\frac{\partial u}{\partial x}:\quad \frac{4}{x}=4x^{-1}\ \Rightarrow\ \frac{d}{dx}(4x^{-1})=-4x^{-2}=-\frac{4}{x^2}$$
$$\Rightarrow\ \frac{\partial u}{\partial x}=-\sin\!\left(\frac4x\right)\cdot\left(-\frac{4}{x^2}\right)=\frac{4}{x^2}\sin\!\left(\frac4x\right)$$

$$\frac{\partial v}{\partial x}:\quad \text{指数 } x^2y-5y^3 \text{ 对 }x\text{ 求导（}y\text{ 当常数）}=2xy \ \Rightarrow\ \frac{\partial v}{\partial x}=2xy\,e^{\,x^2y-5y^3}$$

**应用乘积法则** $\frac{\partial f}{\partial x}=\frac{\partial u}{\partial x}v+u\frac{\partial v}{\partial x}$：

$$\boxed{\frac{\partial f}{\partial x}=\frac{4}{x^2}\sin\!\left(\frac4x\right)e^{\,x^2y-5y^3}+2xy\cos\!\left(\frac4x\right)e^{\,x^2y-5y^3}}$$

提取公因子：
$$\frac{\partial f}{\partial x}=e^{\,x^2y-5y^3}\left[\frac{4}{x^2}\sin\!\left(\frac4x\right)+2xy\cos\!\left(\frac4x\right)\right]$$

**对 $y$——不需要乘积法则**（解答明确说明：因为 $y$ **只出现在指数里**，$\cos(4/x)$ 对 $y$ 而言是常数系数）：

指数对 $y$ 求导（$x$ 当常数）：$\dfrac{\partial}{\partial y}(x^2y-5y^3)=x^2-15y^2$

$$\boxed{\frac{\partial f}{\partial y}=\cos\!\left(\frac4x\right)\left(x^2-15y^2\right)e^{\,x^2y-5y^3}}$$

> **这一题是本周最重要的方法示范**：**"要不要用乘积法则"取决于你正在对哪个变量求导**。同一个函数，对 $x$ 求导需要乘积法则，对 $y$ 求导就不需要——因为对 $y$ 来说 $\cos(4/x)$ 只是个常数。这是偏微分与常微分最直观的差别。

**(c) $z(u,v)=\dfrac{9u}{u^2+5v}$**

**对 $u$——需要商法则 (quotient rule)**，因为 **$u$ 同时出现在分子与分母**（解答明确指出）。

拆分：分子 $N=9u\Rightarrow \dfrac{\partial N}{\partial u}=9$；分母 $D=u^2+5v\Rightarrow \dfrac{\partial D}{\partial u}=2u$（$5v$ 当常数 → 0）

$$\frac{\partial z}{\partial u}=\frac{N_u D-N D_u}{D^2}=\frac{9(u^2+5v)-9u\cdot 2u}{(u^2+5v)^2}=\frac{9u^2+45v-18u^2}{(u^2+5v)^2}=\boxed{\frac{45v-9u^2}{(u^2+5v)^2}}$$

**对 $v$——不需要商法则**（$v$ 只出现在分母）。改写为幂函数用链式法则：

$$z=9u\,(u^2+5v)^{-1}$$
$$\frac{\partial z}{\partial v}=9u\cdot(-1)(u^2+5v)^{-2}\cdot\frac{\partial}{\partial v}(u^2+5v)=9u\cdot(-1)(u^2+5v)^{-2}\cdot 5=\boxed{-\frac{45u}{(u^2+5v)^2}}$$

> ⚠️ **官方解答的笔误**：Solutions 中写 "For the partial derivative with respect to $v$, we do not need the quotient rule since variable $v$ only appears in the **exponential**." ——这里的 "exponential" 是从 (b) 复制粘贴留下的错误，正确应为 "**只出现在分母 (denominator) 中**"。
>
> 另注：本题也可以对 $v$ 硬套商法则（$N_v=0$），结果相同 $\dfrac{0\cdot D-9u\cdot5}{D^2}=-\dfrac{45u}{D^2}$——不过多一步而已。

---

### 5.11 手册习题 Q10.9 — 碗形山丘（应用题）

**题目**：一座碗形山丘由 $f(x,y)=100\exp\!\left[-1\times10^{-5}\left(x^2+y^2\right)\right]$ 描述。你决定沿直线 $y=0$ 行走，此时梯度 $\dfrac{\partial f(x,y)}{\partial x}$ 是多少？

**第 1 步：对 $x$ 求偏导（把 $y$ 当常数），用链式法则。**

外函数 $100e^{g}$，内函数 $g=-1\times10^{-5}(x^2+y^2)$。

$$\frac{\partial g}{\partial x}=-1\times10^{-5}\cdot 2x=-2\times10^{-5}x\qquad(y^2\text{ 是常数，导数为 }0)$$

$$\frac{\partial f}{\partial x}=100\cdot e^{\,-1\times10^{-5}(x^2+y^2)}\cdot\left(-2\times10^{-5}x\right)=-2\times10^{-3}\,x\,\exp\!\left[-1\times10^{-5}\left(x^2+y^2\right)\right]$$

（系数：$100\times2\times10^{-5}=2\times10^{-3}$。）

**第 2 步：代入 $y=0$。**

$$\boxed{\ \frac{\partial f}{\partial x}\bigg|_{y=0}=-2\times10^{-3}\,x\,\exp\!\left(-1\times10^{-5}x^2\right)\ }$$

> **物理解读（这题的意义所在）**：
> - **山顶在原点**：$x=0$ 时 $f=100$（最高），且 $\frac{\partial f}{\partial x}=0$——**山顶处坡度为零**，符合直觉。
> - **$x>0$ 时梯度为负**：说明沿 $+x$ 方向走是**下坡**（远离山顶）。
> - **$x\to\pm\infty$ 时梯度 $\to 0$**：因为指数衰减压过线性增长，远处地形又变平了。
> - 所以坡度在某个中间的 $x$ 处**最陡**——这正是"碗形/钟形山"的典型特征。
> - "沿 $y=0$ 走"这个设定就是**把二维问题降成一维切片**——正好把 §2.8(d) 讲的"用平面去切曲面"具象化了。

---

### 5.12 Practical 解题技巧总结

1. **先判断"谁是变量、谁是常数"再动笔**——在草稿上把当前的常数圈起来。
2. **逐项列表**（见 §5.2）——多项式型函数最稳妥，不漏项不多项。
3. **"要不要用乘积/商法则"因变量而异**——对某个变量而言只有一个因子含它时，另一个因子只是常数系数，不用法则。
4. **组装梯度时保持分量顺序** $\langle f_x,f_y,f_z\rangle$，不要错位。
5. **提公因子**（如 $e^{-xy}$、$2\times10^{-3}$）能极大简化后续求模。
6. **算完模要验算**：代回勾股定理或用一般式与具体点两条路互验。
7. **应用题先画图**（Q10.5 题目自己就这么建议）。
8. **写全过程**——见 §4.2，这是分数的来源。

---

## 六、易错点 / 重点难点

### 6.1 概念层面

1. **偏导 vs 常导的符号必须严格区分**：$\partial$（卷曲 d）用于多变量，$d$（直 d）用于单变量。写错 = 概念错。
2. **"其余变量当常数"要贯彻到底**：不含目标变量的**整项**直接归零；含目标变量的项里，其余字母是**常数系数**，要**保留**（如 $\frac{\partial}{\partial x}(xyz)=yz$，$yz$ 不能丢）。
3. **不要把"常数系数"也当成 0**。$\frac{\partial}{\partial x}(2xy)=2y$，**不是 0，也不是 2**。这是最高频的错误。
4. **标量场 $f$ 的梯度 $\nabla f$ 是向量，不是标量**。$\nabla$ 把标量场变成向量场。答案写成一个数就错了。
5. **标量场 vs 向量场别混**：风速（标量）vs 风向/风矢量（向量）。讲义第 10 页那句 "wind speed" 是印刷错误。
6. **$f=x^2$ 的最小值是一整条直线，不是一个点**（图判读题）。
7. **一个标量场可以对应两个方向相反的向量场**（$\pm\nabla f$），大小相同。地学里的通量取**负梯度**方向。

### 6.2 记号层面

8. **$\langle\ \rangle$（向量）与 $(\ )$（坐标点）绝不能混用**。讲座与手册都反复强调。
9. **$\overrightarrow{AB}$ 与 $\overrightarrow{BA}$ 方向相反**，箭头方向有实际含义。
10. **⚠️ 手册措辞陷阱**："start minus end" 这句话**字面是错的**。正确规则是 **$\overrightarrow{AB}=B-A$（终点减起点）**，与手册解答的文字描述和数值答案一致。
11. **单位向量的帽子 $\hat{\ }$ 表示长度为 1**；$\hat i,\hat j,\hat k$ 是固定的坐标轴单位向量，不要与"某向量的单位向量 $\hat a$"混淆。
12. **本课讲义把二阶偏导矩阵记作 $\nabla^2 f$**；外部文献中 $\nabla^2$ 通常是 Laplacian（标量）。答本课的题按讲义，读别的书要留心。

### 6.3 计算层面

13. **负数相减务必打括号**：$-3-(-7)=+4$；$5-(-2)=7$。Q10.3、Q10.4 全是陷阱。
14. **方向向量必须先归一化再乘速率**。$3\hat i+4\hat j$ 的模是 **5 不是 1**（Q10.5 的命门）。
15. **不同维数的向量不能相加减**（Practical Ex.1 中 $\vec c$ 是三维）。
16. **取模前先完成加减**：$|\vec b-\vec a|$ 要先算 $\vec b-\vec a$，不能写成 $|\vec b|-|\vec a|$（这是完全不同的数：$\sqrt{53}\approx7.28$ vs $\sqrt{29}-\sqrt{34}<0$）。
17. **模永远非负**，平方会消掉符号——所以 $|\bar a|=|\bar b|$ 时方向未必相同（Q10.1(a)(b)）。
18. **链式法则的内层导数别漏**：$\frac{\partial}{\partial y}\sin(5y)=5\cos(5y)$ 的那个 5；$\frac{\partial}{\partial x}e^{-xy}$ 的那个 $-y$；Q10.9 里 $-1\times10^{-5}\times2x$ 的那个 2。
19. **对不同变量求导，需要的法则可能不同**（Q10.8(b)(c) 的核心教学点）。
20. **科学记数法的系数运算要仔细**：$100\times2\times10^{-5}=2\times10^{-3}$（Q10.9）；$1\times10^{-3}\times2=2\times10^{-3}$（Q10.6c/10.7）。
21. **求模时把公因子提到根号外**，能大幅减少算错的机会（Q10.7）。

### 6.4 考试策略层面

22. **必须写出过程**——只写答案且错误 = 0 分；写了过程即使小错也能拿 7–9 分（follow-through marks）。讲师强调了三次以上。
23. **不按顺序做题**，先做最有把握的。
24. **公式表会提供**，但要提前熟悉；不要考场上现学。
25. **计算器规格**：不能存文本、不能做代数、不能有图形功能。

### 6.5 官方材料勘误汇总（复习时以本笔记为准）

| 位置 | 原文 | 应为 |
|---|---|---|
| 手册 §11.3 / 讲义 p.13 | "start minus end approach" | **end minus start**（终点 − 起点），与其自身解答一致 |
| 讲义 p.10 (VECTOR FIELDS) | "For example, wind speed – but not direction." | 应为**风向 / 风矢量**（复制粘贴错误，transcript 已澄清） |
| 讲义 p.17 | "$\bar b=\langle2,1\rangle=4\hat i+3\hat j$" | $\bar b=\langle2,1\rangle=2\hat i+\hat j$（讲师口头更正） |
| Solutions Q10.8(c) | "$v$ only appears in the **exponential**" | 应为 "only appears in the **denominator**" |
| 手册 §11.4 / 讲义 p.19 | 称 $\frac{\partial f}{\partial x}$ 为 "partial differential equation" | 严格说这是 **partial derivative（偏导数）**；讲义 p.19 后半已改口为 "partial derivative"。**PDE 是含偏导数的方程**，二者不同 |
| Chapter10.md §10.2 | 标题缺失、"a scalar is a function..." | 应为 "**Scalar fields**"，"a **scalar field** is a function..." |

### 6.6 本周与其它周的连接（复习索引）

| 本周内容 | 依赖 / 呼应的周 |
|---|---|
| 有限差分求偏导 | Week 1 Calculating Gradients（数值梯度） |
| 幂/乘积/商/链式法则 | Week 2–3 Differentiating Combinations of Functions |
| $\nabla f=\vec0$ 找极值 | Week 4 Optimisation |
| 二阶偏导 / $\nabla^2f$ | Week 5 Second Order Derivatives |
| Fick / Fourier 定律的梯度形式 | Week 9 Integrating Second Order ODEs |
| PDE 与数值天气预报 | 明年 Mathematical Modelling |

### 6.7 拓展（**本课未涉及、不考**）

为知识完整性简记，复习时可跳过。本周材料**完全没有**出现点积与叉积。

- **点积 (dot product / scalar product)**：$\vec a\cdot\vec b=a_1b_1+a_2b_2+a_3b_3=|\vec a||\vec b|\cos\theta$，结果是**标量**，用于求两向量夹角、判断垂直（$\vec a\cdot\vec b=0$）、求投影与做功。
- **叉积 (cross product / vector product)**：$\vec a\times\vec b$，结果是**垂直于 $\vec a,\vec b$ 所张平面的向量**，模等于 $|\vec a||\vec b|\sin\theta$（= 平行四边形面积），用于力矩、角动量、地质中的面/线构造。
- 本课的梯度只用到偏导数与向量的组装、模，**不需要这两种乘法**。

---

## 七、本周术语表

| 英文 | 中文 | 说明 / 关键点 |
|---|---|---|
| Scalar | 标量 | 只有大小、没有方向的量（一个数） |
| Scalar field | 标量场 | 两个或更多变量的函数，给每点赋一个数；有大小无方向；例：风速、温度、高程 |
| Vector | 向量 / 矢量 | 有**大小 (magnitude)** 与**方向 (direction)**；与位置无关 |
| Vector field | 向量场 | 给空间每点赋一个向量；例：风矢量场；画成箭头场 |
| Magnitude | 模 / 大小 | $\lvert\bar a\rvert=\sqrt{a_1^2+a_2^2+a_3^2}$；勾股定理 |
| Direction | 方向 | 向量除大小外的另一半信息 |
| Unit vector | 单位向量 | 模为 1 的向量；$\hat i,\hat j,\hat k$；$\hat a=\bar a/\lvert\bar a\rvert$ |
| Normalise | 归一化 | 把向量除以自身的模，得到同方向的单位向量 |
| Cartesian form | 笛卡尔形式 | 用 $x,y,z$ 正交分量表示（对比 polar coordinates 极坐标，本课不用） |
| Polar coordinates | 极坐标 | 用角度与半径描述；讲座提及但本课不涉及 |
| Angle brackets $\langle\ \rangle$ | 尖括号 | 表示**向量** |
| Curved/round brackets $(\ )$ | 圆括号 | 表示**坐标点** |
| Displacement | 位移 | 从 $A$ 到 $B$ 的向量 $\overrightarrow{AB}=B-A$ |
| Component-wise | 逐分量 | 向量加减、数乘都逐分量进行 |
| Scalar multiplication | 数乘 | 向量乘常数：缩放长度；负数则反向 |
| Vector arithmetic | 向量算术 | 加、减、数乘 |
| Velocity | 速度（矢量） | = 速率 × 单位方向向量；有方向 |
| Speed | 速率（标量） | 只有大小；标量场的典型例子 |
| Contour map / colour plot | 等值线图 / 彩色图 | 标量场的可视化；白=高，黑=低 |
| Saddle (point) | 鞍点 | 如 $f=xy$ 在原点；沿一方向是极大、另一方向是极小 |
| Partial derivative | 偏导数 | $\partial f/\partial x$；求导时其余变量视为常数 |
| Partial differentiation | 偏微分 | 求偏导数的过程 |
| Ordinary derivative | 常导数 / 普通导数 | $df/dx$；单变量情形 |
| "Curly d" $\partial$ | 卷曲 d | 偏导数符号，读作 partial / del |
| Gradient / grad | 梯度 | $\nabla f=\langle f_x,f_y,f_z\rangle$；**标量场求梯度得到向量** |
| Nabla / del $\nabla$ | 纳布拉算子 | 梯度算符 |
| Steepest ascent | 最陡上升方向 | $\nabla f$ 所指的方向；$-\nabla f$ 是最陡下降 |
| Finite difference | 有限差分 | 偏导数的数值近似：$[f(a+h,b)-f(a,b)]/h$ |
| Second-order partial derivative | 二阶偏导数 | 本课讲义记作 $\nabla^2f$（矩阵形式）；**超纲** |
| Hessian | 黑塞矩阵 | 二阶偏导排成的矩阵的标准名称（课外） |
| Laplacian | 拉普拉斯算子 | 标准文献中 $\nabla^2f$ 的通常含义（课外，注意与讲义记号差异） |
| Partial Differential Equation (PDE) | 偏微分方程 | 含偏导数的方程；解析求解需 Fourier 方法，**超纲**；天气预报模式的基础 |
| Fourier methods | 傅里叶方法 | 解析求解 PDE 的工具；**超纲** |
| Numerical / approximate methods | 数值 / 近似方法 | 实际求解 PDE 的手段（如 Met Office 天气预报） |
| Pythagoras' theorem | 勾股定理 | 求模的依据 |
| Product rule | 乘积法则 | $(uv)'=u'v+uv'$；Q10.8(b) 用到 |
| Quotient rule | 商法则 | $(u/v)'=(u'v-uv')/v^2$；Q10.8(c) 用到 |
| Chain rule | 链式法则 | 复合函数求导；Q10.6、Q10.9 用到 |
| Fick's Law | 菲克定律 | 质量扩散：$J=-D\nabla C$（Week 9 衔接） |
| Fourier's Law | 傅里叶定律 | 热传导：$q=-k\nabla T$（Week 9 衔接） |
| Steady state | 稳态 | 不随时间变化；Week 9 用于化简为 ODE |
| Initial conditions | 初始条件 | 在同一点（通常 $x=0$）给出函数与导数值 |
| Boundary conditions | 边界条件 | 在两个端点各给条件；解必须两端都吻合 |
| Follow-through marks | 跟随分 | 前面算错但方法正确，后续仍给分（考试关键） |
| Past paper | 往年真题 | 在 Blackboard 的 "Easter break" 文件夹 |
| Mark scheme | 评分标准 | 复活节期间不发放，复习课后才给 |
