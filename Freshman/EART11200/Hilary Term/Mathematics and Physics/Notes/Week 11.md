# Week 11 — 微分复习 (Revision: Differentiation)

> 课程：EART11200 The Natural Scientist's Toolkit — Mathematics and Physics（Hilary Term / Spring Semester）
> 本周材料：Lecture `Revision_Differentiation.pdf` + 课堂录音转写（02 May）、Practical = 2023–24 年度真题卷 `2324_Exam.pdf`、主手册 Chapter 12 Crib Sheet §12.1–12.2
> 本周性质：**复习课，不教新知识**。系统回顾 Week 1–5（微分）与 Week 10（向量与偏微分），并逐题讲评上一年度考卷中的**五道微分题**。

---

## 一、本周主题

本周是全课程微分部分的**总复习 (Revision Lecture — Differentiation)**。老师在开场明确了本周与下周的安排：

> "this week what I'm going to do in this lecture is I'm going to kind of recap slides of all the stuff... I've kind of picked up all the key items from the slides and brought them all together **week by week** so that you have an idea of **what might come up on the exam**... And then I'm going to cover the five questions that on the last year's exam cover the differentiation."
> "next week we'll do the same thing but with integration. So this week's differentiation and next week with the integration."

因此本周的内容分为两大块：

**(A) 逐周知识回顾**（对应 Revision 幻灯片 1–22 页）

| 幻灯片标注 | 实际对应本课程周次 | 主题 |
|---|---|---|
| WEEK 1 | Week 1 | 用数值方法求梯度：Euler backward / forward / central difference |
| WEEK 2 | Week 2 | 微分的定义与记号、基本微分表、和函数的微分 |
| WEEK 3 | Week 3 | 链式法则、乘积法则、商法则 |
| WEEK 4 | Week 4 | 导数的性质、驻点 (stationary values) 与优化 |
| WEEK 5 | Week 5 | 二阶导数、稳态 (steady state)、Newton–Raphson 求根 |
| "WEEK 11" | **本目录的 Week 10** | 标量场/向量场、向量运算、grad ∇f、偏微分 |

> ⚠️ **重要提示（别被带偏）**：幻灯片里的 "WEEK 11" 用的是**曼大学期的绝对周号**（本课程占学期第 20–34 周），它指的是**向量与偏微分**那一讲，也就是本目录中的 `Lecture/Week 10`。老师在录音里也自己纠正过："this is where we came back to in week 10, **I should say week 10**"。你现在做的这份笔记是**本课程的 Week 11**（复习周）。

**(B) 2023–24 真题微分部分讲评**（幻灯片 23–43 页）：Q1 (True/False)、Q3 (Newton's method)、Q5 (优化)、Q6 (三个复杂函数求导)、Q7 (解析 vs 中心差分 + 百分比误差)。

**(C) Practical**：本周 Practical 文件夹里放的就是 **2023–24 年度完整考卷**（10 题、100 分）。课堂时间不够，老师把 Q6/Q7 的详细求解挪到 practical session 现场讲。

---

## 二、核心概念（微分部分的知识梳理与串联）

本节把 Week 1–5 + Week 10 的微分内容组织成一条完整逻辑链。**整条主线是：先"数值地"逼近梯度 → 再"解析地"求导 → 再把导数用起来（优化 / 求根 / 稳态）→ 最后推广到多维（偏微分与梯度向量）。**

### 2.1 主线地图

```
        「我想知道 y 随 x 变化得多快」
                    │
    ┌───────────────┴───────────────┐
    │                               │
[数值路线 Week 1]              [解析路线 Week 2]
Euler backward                  导数定义 dy/dx = lim(Δx→0) Δy/Δx
Euler forward                   基本微分表 (x^n, e^x, ln x, sin, cos)
central difference              和的导数 = 导数的和
    │                               │
    │                        [复合结构 Week 3]
    │                        chain / product / quotient rule
    │                               │
    └───────────────┬───────────────┘
                    │
        [导数拿来干什么 Week 4–5]
   ├── 判断函数增/减：f'>0 增，f'<0 减
   ├── 驻点 f'(x)=0 → 优化（最大/最小）
   ├── 二阶导数 f''(x) 判别极大/极小/无法判定
   ├── 稳态 steady state: d²V/dt² = 0
   └── f'(x)=0 解不出来时 → Newton–Raphson 迭代求根
                    │
            [推广到多维 Week 10]
   标量场 f(x,y,z) → 偏导数 ∂f/∂x → 梯度向量 ∇f（有大小和方向）
```

### 2.2 Week 1：数值求梯度（三种差分）

出发点：导数就是"$y$ 相对 $x$ 的变化率"。在**无法得到解析表达式**时（或者只有离散数据时），我们用有限的 $\Delta x$ 去逼近：

$$\frac{dy}{dx}=\lim_{\Delta x\to 0}\frac{\Delta y}{\Delta x}$$

三种取法（设当前点为 $x$，步长 $\Delta x$）：

- **Euler backward step（后向差分）**：只用当前点与**前一个**点
  $$\frac{dy}{dx}\approx\frac{y_x-y_{x-\Delta x}}{\Delta x}$$
- **Euler forward step（前向差分）**：只用当前点与**后一个**点
  $$\frac{dy}{dx}\approx\frac{y_{x+\Delta x}-y_x}{\Delta x}$$
- **Central difference（中心差分）**：同时用**两侧**的点（注意分母是 $2\Delta x$）
  $$\frac{dy}{dx}\approx\frac{y_{x+\Delta x}-y_{x-\Delta x}}{2\Delta x}$$

**关键结论（老师反复强调）：三种方法算的是同一个梯度，但用了曲线上不同的部分，所以给出略有不同的答案；对光滑函数而言 central difference 最准确**（Crib Sheet：*"The central difference approximation is more accurate for smooth functions, though this accuracy can vary depending on the shape of our curves."*）。

课上重现的 Week 1 例子（复习幻灯片第 3–5 页）：对一个含 $\sqrt{x}$ 的函数在 $x=16$ 处、以 $\Delta x=0.25$ 求梯度，结果为

| 方法 | 估计的梯度 |
|---|---|
| Euler backward | $-1.1071$ |
| Euler forward | $\approx -1.05$ |
| Central difference | $\approx -1.08$ |
| **解析导数（真值）** | $\mathbf{-1.08333}$ |

→ 中心差分与真值最接近。老师原话："what you can see is that... **the central difference is actually the most accurate of all three**."

> ⚠️ 材料缺陷说明：该例题的函数表达式在 PDF→MD 转换中被打散成 `2x − 10 / y = √x + ( 3 )`，已无法可靠还原；幻灯片写 "At $x=4$"、转写里老师说 "$x=16$，往前退到 14、往后到 18"，两处口径不一致（转写是口头随手举例，幻灯片的 $\Delta x=0.25$ 才是原题设定）。**需要原式时请查 `Revision_Differentiation.pdf` 第 3–5 页。** 但考试要考的是**方法与精度排序**，这一点已完整记录。

### 2.3 Week 2：解析微分的起点

- 记号：$f'(x)=\dfrac{dy}{dx}$。"$dy$ 表示 y 的变化，$dx$ 表示相对 x 而言"，合起来就是 y 相对 x 的变化率。
- **把中心差分的极限取到 $\Delta x\to 0$，就得到了微分本身**——这是从数值到解析的桥梁。
- **基本微分表**（见第三节完整表格）。
- **和的导数 = 导数的和**：
  $$y=5x+e^{x}\ \Longrightarrow\ \frac{dy}{dx}=5+e^{x}$$
  所以多项式/多项相加的函数可以**逐项求导**。

老师给的记忆窍门：
- 指数函数微分后**指数部分永远还在**，只是前面"掉出来 (pops out)"一个系数；你只需判断掉出来的是什么。
- $\sin$ 与 $\cos$ 互相循环：$\sin\to\cos\to-\sin\to-\cos\to\sin$，**微分四次回到自身**；微分 $\cos$ 时**千万别漏负号**。

### 2.4 Week 3：三大法则（考试必考）

三条法则老师教的是**同一套三步流程**，务必形成肌肉记忆：

> **Step 1** 拆分函数 → **Step 2** 分别求导 → **Step 3** 代入公式并回代化简。

- **Chain rule（链式法则）**：$f$ 是复合函数 $f(g(x))$
  $$\frac{df}{dx}=\frac{df}{dg}\times\frac{dg}{dx}$$
  做法：把**括号里面的东西**设为 $g$，对 $f$ 关于 $g$ 求导、对 $g$ 关于 $x$ 求导，相乘后把 $g$ 换回去。
- **Product rule（乘积法则）**：$f(x)=u(x)v(x)$
  $$\frac{df}{dx}=u\frac{dv}{dx}+v\frac{du}{dx}$$
- **Quotient rule（商法则）**：$f(x)=\dfrac{u(x)}{v(x)}$
  $$\frac{df}{dx}=\frac{v\dfrac{du}{dx}-u\dfrac{dv}{dx}}{v^{2}}$$
  老师认为**商法则是三者中最难的**（转写里被自动识别成 "Cauchy rule"，实为 quotient rule 的误听）："you'll need to remember the **v du minus u dv**"，且分子**顺序不能颠倒**、化简往往最麻烦。

### 2.5 Week 4：导数的性质与驻点（优化）

- $f'(x)>0$ → 函数**递增**；$f'(x)<0$ → 函数**递减**；$f'(x)=0$ → 可能在**转向**。
- 使 $f'(x)=0$ 的点称为 **stationary values / stationary points（驻点）**，它可能是 **maximum、minimum 或 saddle point（鞍点）**。
- **求驻点三步法**：
  1. 对 $f(x)$ 求导，得到梯度函数 $f'(x)=\dfrac{dy}{dx}$；
  2. 令 $\dfrac{dy}{dx}=0$，解出 $x$；
  3. 把 $x$ 代回 $f(x)$，求出驻点处的函数值。
- **非正式判别法**（Week 4 的方法）：在驻点两侧取点，看 $f'$ 的正负号变化 → 判断是极大、极小还是拐点。
- 若 $f'(x)=0$ 解不出来（函数太复杂），必须用 **Newton's method**（见 2.6）。

### 2.6 Week 5：二阶导数、稳态、Newton 求根

**(a) 二阶导数 (second-order derivative)**

$$f''(x)=\frac{d}{dx}\left(\frac{df}{dx}\right)=\frac{d^{2}f}{dx^{2}}$$

一阶导告诉你**函数变化得多快**；二阶导告诉你**"变化率本身"变化得多快**。

**驻点判别（formal method）**：在驻点 $x$ 处
- $f''(x)<0$ → **local maximum（极大）**
- $f''(x)>0$ → **local minimum（极小）**
- $f''(x)=0$ → **无法下结论**，可能是 saddle point，必须退回去用一阶导数的性质（两侧符号）或作图检查。

> 记忆法：二阶导为负 = 曲线向下弯（∩）= 山顶；二阶导为正 = 向上弯（∪）= 谷底。

**(b) Steady state（稳态）**

系统处于稳态时，描述系统的关键变量**不随时间改变**。设水/物质体积 $V$ 的变化率由源与汇决定：

$$\frac{dV}{dt}=f(t,x_1,x_2)\quad\Longrightarrow\quad \frac{d^{2}V}{dt^{2}}=0$$

含义：变化率本身不再变化——**流入 = 流出**，系统总量恒定。老师的类比：水箱进水与出水速率相等，整个系统"没有在变"；在力学语境下相当于**加速度为零**。这个概念在下周（积分 / ODE）会更有用。

**(c) Newton's method for root finding（Newton–Raphson 法）**

用途：**求函数的根**（$f(x)=0$ 的位置）。因为求驻点就是解 $f'(x)=0$，而很多时候（例如 $x$ 同时出现在 $2x^2$ 和 $e^x$ 里）根本解不出来，只能迭代。

$$\boxed{\,x_{n+1}=x_{n}-\frac{f(x_{n})}{f'(x_{n})}\,}$$

流程：选一个初始猜测 $x_0$ → 反复代入 → 直到达到规定的迭代次数，或达到收敛判据（例如**小数点后三位不再变化**）。

### 2.7 Week 10（幻灯片标为 "WEEK 11"）：多维推广

- **Scalar field（标量场）**：两个或更多变量的函数，如 $f(x,y)=x^2+y^2$。每点只给一个数值，**有大小无方向**，可用等值线图/彩色图表示（老师类比：等高线地图；只有风速没有风向）。
- **Vector field（向量场）**：给空间每一点分配一个**向量**，**既有大小又有方向**（类比：风速 + 风向）。
- **向量记号**：$\vec{v}=\langle -2,\,5\rangle$，用**尖括号**，与坐标点 $(-2,5)$ **本质不同**。同一向量可以从任意起点画出，含义都是"向 x 方向移动 −2，向 y 方向移动 +5"。
- **向量运算**：设 $\vec a=\langle a_1,a_2\rangle,\ \vec b=\langle b_1,b_2\rangle$
  - 加减（逐分量）：$\vec a\pm\vec b=\langle a_1\pm b_1,\ a_2\pm b_2\rangle$
  - 数乘：$c\vec a=\langle ca_1,\ ca_2\rangle$
  - **模长（Pythagoras）**：$|\vec a|=\sqrt{a_1^{2}+a_2^{2}}$，三维为 $\sqrt{a_1^2+a_2^2+a_3^2}$
- **Partial derivative（偏导数）**：从 $\dfrac{df}{dx}$ 换成 $\dfrac{\partial f}{\partial x}$（"curly d"）。含义：对 $x$ 求导时，**假设 $y$、$z$ 等其他变量为常数**，只关心分母中那个变量方向上的信息。
- **Grad（梯度）**：标量场的"梯度"记作 $\operatorname{grad}(f)$ 或 $\nabla f$（读作 grad-f），它**是一个向量**：
  $$\nabla f=\frac{\partial f}{\partial x}\hat{i}+\frac{\partial f}{\partial y}\hat{j}+\frac{\partial f}{\partial z}\hat{k}$$
  **对标量场求导 → 得到向量**，这个向量告诉你函数上升最快的**方向**以及**有多快**。
- **串联点（老师课上被学生问到的延伸）**：Newton 法在一维靠 $f'$ 告诉你"往哪边走能找到零点"；在多维，你需要 $\nabla f$ 的**方向 + 大小**才能知道往哪走、走多快 → 这正是**优化算法**（如梯度下降）的思想。再进一步，把多维函数微分两次会得到一个矩阵，叫 **Jacobian**（明年会学，用于求解常/偏微分方程）。
- **本课程的边界**：偏微分方程 (PDE) **只介绍概念，不要求积分求解**——"we don't do anything with partial differential equations, because... they're really, really difficult to integrate"。

---

## 三、公式与图表（Crib Sheet §12.2 微分部分完整重排）

> 来源：主手册 **Chapter 12 Crib Sheet**，§12.1 Overview + §12.2 Differentiation（涵盖 Chapters 1–5 与 11）。
> ⚠️ §12.1 明确说明：**Crib Sheet 本身不允许带进考场**；考场会提供的公式表见 **Chapter 14**。**凡是没出现在 Chapter 14 表格里的公式，都必须自己背下来。**
> ⚠️ 原手册中大量公式是图片，转 MD 后丢失；下面已按上下文补全为标准形式（表格部分是原生 MD，完整保留）。

### 3.1 Finding gradients（求梯度）

**解析 (analytical) vs 数值 (numerical)**：能用微分法则写出梯度函数的叫解析解，例如

$$f(x)=2x^{3}-20x^{2}+x+4000\ \Longrightarrow\ \frac{dy}{dx}=6x^{2}-40x+1$$

有些情况得不到解析式，只能用数值近似：

| 方法 | 公式 | 特点 |
|---|---|---|
| **Euler backward step** | $\dfrac{dy}{dx}\approx\dfrac{y_{x}-y_{x-\Delta x}}{\Delta x}$ | 用当前点与前一点 |
| **Euler forward step** | $\dfrac{dy}{dx}\approx\dfrac{y_{x+\Delta x}-y_{x}}{\Delta x}$ | 用当前点与后一点 |
| **Central difference** | $\dfrac{dy}{dx}\approx\dfrac{y_{x+\Delta x}-y_{x-\Delta x}}{2\Delta x}$ | 用两侧点，**对光滑函数最准确** |

**等价记号**（Crib Sheet 特别提醒，三种写法完全等价）：

$$\frac{dy}{dx}\ \equiv\ y'\ \equiv\ f'(x)$$

### 3.2 Common differentials（基本微分表 — 必背/考场提供）

> 这张表在 Crib Sheet 与 Revision 幻灯片中反复出现，是**全课程微分的核心表**。老师："**most of these will be on the exam paper in the list of formulae**. But please make sure you are familiar with these."

| Function $y=f(x)$ | Derivative $\dfrac{dy}{dx}$ |
|---|---|
| constant（常数） | $0$ |
| $x$ | $1$ |
| $x^{n}$ | $n\,x^{n-1}$ |
| $e^{x}$ | $e^{x}$ |
| $e^{kx}$ | $k\,e^{kx}$ |
| $e^{f(x)}$ | $\dfrac{df}{dx}\,e^{f(x)}$ |
| $\ln(x)$ | $\dfrac{1}{x}$ |
| $\sin(x)$ | $\cos(x)$ |
| $\cos(x)$ | $-\sin(x)$ |

（Crib Sheet 版本略去了 $x\to 1$ 一行，幻灯片版本含有；两者其余完全一致。）

**附加规则**：$\dfrac{d}{dx}\big[f(x)+g(x)\big]=\dfrac{df}{dx}+\dfrac{dg}{dx}$（和的导数 = 导数的和）。

### 3.3 三大法则（考场公式表会给）

| 法则 | 适用形式 | 公式 |
|---|---|---|
| **Chain rule** | $f\big(g(x)\big)$ | $\dfrac{df}{dx}=\dfrac{df}{dg}\times\dfrac{dg}{dx}$ |
| **Product rule** | $f=u(x)\,v(x)$ | $\dfrac{df}{dx}=u\dfrac{dv}{dx}+v\dfrac{du}{dx}$ |
| **Quotient rule** | $f=\dfrac{u(x)}{v(x)}$ | $\dfrac{df}{dx}=\dfrac{v\dfrac{du}{dx}-u\dfrac{dv}{dx}}{v^{2}}$ |

### 3.4 Properties of a derivative and Stationary values

| 情形 | 含义 |
|---|---|
| $f'(x)<0$ | 函数在该点**递减** |
| $f'(x)>0$ | 函数在该点**递增** |
| $f'(x)=0$ | **驻点**：maximum / minimum / saddle point |

**求驻点步骤（Crib Sheet 原文三步）**：
1. Differentiate the function → 得到梯度函数 $f'(x)$ 或 $\dfrac{dy}{dx}$；
2. Set the gradient function to zero，解出 $x$；
3. 把 $x$ 代回 $f(x)$，得到驻点的函数值。

复杂时无法解 $f'(x)=0$ → 用 Newton's method。判别极大/极小 → 用二阶导数。

### 3.5 Second-order derivatives

$$f''(x)=\frac{d}{dx}\left(\frac{df}{dx}\right)=\frac{d^{2}f}{dx^{2}}$$

| 条件（在驻点 $x$ 处） | 结论 |
|---|---|
| $f''(x)<0$ | $f(x)$ 在该驻点有 **local maximum** |
| $f''(x)>0$ | $f(x)$ 在该驻点有 **local minimum** |
| $f''(x)=0$ | **无法下结论**；可能是 saddle point，需目视检查或进一步分析 $f(x)$ |

### 3.6 Steady state

$$\frac{dV}{dt}=f(t,x_1,x_2)\qquad\Longrightarrow\qquad \frac{d^{2}V}{dt^{2}}=0$$

"变化率不随时间变化"→ 稳定流动，系统内总量保持恒定（流入 = 流出）。

### 3.7 Newton–Raphson method（求根）

$$x_{n+1}=x_{n}-\frac{f(x_{n})}{f'(x_{n})}$$

其中 $f'(x)$ 是 $f(x)$ 的导数。迭代直到达到指定次数，或**收敛判据**满足（例如小数点后三位不再变化）。

### 3.8 Ordinary Differential Equations（Crib Sheet 列出的一阶 ODE 清单）

> 这些是"导数函数"本身；要预测过去/未来的值，就要对 ODE 积分（不定积分或在给定上下限之间定积分）——这是 **Week 12 积分复习**的内容，但公式属于微分部分的语言。

| 名称 | 微分方程 | 符号说明 |
|---|---|---|
| **Radioactive decay equation** | $\dfrac{dN}{dt}=-\lambda N$ | $\lambda$ 为该同位素的衰变常数，$N$ 为不稳定核数目 |
| **Hydrostatic equation** | $\dfrac{dP}{dz}=-\rho g=-\dfrac{P g}{R_a T}$ | 由理想气体定律 $\rho=\dfrac{P}{R_aT}$，$R_a=287\ \mathrm{J\,kg^{-1}K^{-1}}$ |
| **Newton's Laws of Motion** | $F=ma=m\dfrac{dv}{dt}=m\dfrac{d^{2}x}{dt^{2}}$ | $a$ 加速度，$v$ 速度，$x$ 位移，$m$ 质量，$F$ 合力；各式等价 |
| **Fourier's Law** | $\propto -\dfrac{dT}{dx}$（热通量正比于温度的负梯度） | $T$ 温度，$x$ 距离；热从高温流向低温 |
| **Fick's Law** | $J=-D\dfrac{dC}{dx}$ | $J$ 质量通量，$C$ 浓度，$D$ 扩散系数；由 Brownian motion 驱动，由高浓度流向低浓度 |

**二阶 ODE**：homogeneous, linear, second-order ODE 的一般形式为

$$a\frac{d^{2}y}{dx^{2}}+b\frac{dy}{dx}+cy=0$$

例子：
- Newton's Laws of Motion：$F=m\dfrac{d^{2}x}{dt^{2}}$
- Fourier's / Fick's Laws 在**稳态**下（变化率在空间或时间上保持恒定）：$\dfrac{d^{2}T}{dx^{2}}=0$，$\dfrac{d^{2}C}{dx^{2}}=0$

**Initial value problem vs Boundary value problem**：
- *Initial value problem*：给定**初始条件**，求未来某时刻或某距离处的值；
- *Boundary value problem*：给定**上、下边界条件**。

### 3.9 Partial differentiation

$$\nabla f=\operatorname{grad}(f)=\frac{\partial f}{\partial x}\hat{i}+\frac{\partial f}{\partial y}\hat{j}+\frac{\partial f}{\partial z}\hat{k}$$

- $f=f(x,y,z)$ 是**标量场**，但 $\nabla f$ 是**向量**（有 magnitude 和 direction）。
- $\hat i$ 对应 $x$ 分量，$\hat j$ 对应 $y$ 分量，$\hat k$ 对应 $z$ 分量。
- 记号从 $\dfrac{df}{dx}$ 变成 $\dfrac{\partial f}{\partial x}$，这叫 **partial differential**：对 $x$ 求导时**假定 $y,z$ 为常数**。
- **向量模长**：$\vec a=a_1\hat i+a_2\hat j+a_3\hat k$
  $$|\vec a|=\sqrt{a_1^{2}+a_2^{2}+a_3^{2}}$$

---

## 四、课堂补充（transcript 中的考试提示、重点圈定、复习建议）

本节是本周最高价值的部分——复习课的口头讲解直接圈定了考试范围与评分方式。

### 4.1 考试形式与规则（来自真题首页 + 课堂问答）

- 试卷共 **100 分**，**Answer ALL questions**，题旁标注分值可作为时间分配参考。
- 答题写在**发放的答题册（"pink booklet"，空白纸，约 10–14 页）**里；不够可以再要一本，"人们要了第二本然后把它们订在一起"。
- **只有写在 pink booklet 里的内容才会被批改**。额外索取的草稿纸（scribble paper）**不批改** — "If you ask for spare paper to scribble on, I can't mark that."
- 字迹必须清晰：**Illegible documents cannot be marked**。
- **必须写出全部过程**："Please show all of your working to get to an answer. **This is used to mark correct methodologies.**"
- 允许使用计算器，但**不能存储文本、不能做代数运算、不能有绘图功能**。
- 可以画带标注的示意图辅助作答。
- 考场会在卷首**提供公式框**：chain rule、product rule、quotient rule、**common differentials 表**、**common integrals 表**（详见主手册 Chapter 14）。

### 4.2 老师明确圈定的考试重点

1. **"今年的题会和去年非常相似"** —— 原话："just as a warning **all of the questions you will see in the last year's paper will be very similar to what you will see this year**." → **去年真题是最高优先级的复习材料。**
2. **第 1 题大概率仍是 True/False**："probably the first question in the exam will probably be a **true or false question based on very basic rules of differentiation**." 5 小问 × 2 分 = 10 分。
3. **三大法则的公式会给，但必须练熟**："the quotient rule, the chain rule, and the product rule will be — the formula will be on the exam paper. It will be given in the box at the formula at the beginning. So **you won't have to remember them**, but... make sure you've applied them multiple times so you know at least what you're doing or have a process."
4. **基本微分表也会在卷上给**，但仍然要熟："most of these will be on the exam paper in the list of formulae. But please make sure you are familiar with these."
5. **Newton 法的公式考场会给**："I will give you this formula in my paper if I ask you to do this."
6. **偏微分/向量**：会考"给一个函数，求它的所有偏导数"，变量数量是 **x, y 或 x, y, z**，"more than three... that would be a bit mean"（不会超过三个变量）。PDE 的**求解/积分不考**。
7. 老师在每个主题结束后都问"有问题吗"，无人提问时说 "I'll assume you're all going to get **a hundred percent** of these"（对 basic differentiation、chain/product/quotient rule、stationary values、second-order derivatives、Newton's method、steady state 都说过）。

### 4.3 评分与答题策略（老师反复强调，价值极高）

**Follow-through marks（后续步骤分）—— 本节最重要的一条建议**：

> "If you feel like you've done something wrong, **continue with the solution**... if you did the differentiation wrong, you would just lose one mark. Because if you used that wrong differential in all of the subsequent solutions, **you would still get nine marks**. They get follow-through marks."
>
> "Where people go wrong is they feel like they make a mistake and they stop. **If you make a mistake and you stop, you will probably get zero on that question. But if you make a mistake and follow it through, you'll probably still salvage about five or six marks.**"
>
> "I will shout until the day I die that you need to put your working down. **Because I can't give you marks if you put nothing, but I might be able to give you marks if you put something.**"

**其他策略**：
- **只有题目说"prove"才需要证明是极大值**："only prove it's a maximum **if I say prove it's a maximum**. If I just say find the maximum, just assume that you know it's a maximum."
- **角度单位**：学生问"计算器用度还是弧度？"→ **"assume it's radians unless otherwise stated"**；只有当题目明确给出"an angle of 30 degrees"这类度数时才用度。
- 化简分数：Q6(b) 那种题，即使化简不到最简，"**if you left it there, it'll probably be okay**"——只要正确应用了商法则就能拿主要分数。

### 4.4 Newton 法一题的详细给分表（老师亲口给出）

对 2023–24 卷 Q3（10 分）：

| 步骤 | 分值 |
|---|---|
| 求出导数 $f'(x)$ | **1 分** |
| 第一次迭代 $x_1$ | **3 分** |
| 第二次迭代 $x_2$ | **3 分** |
| 第三次迭代 $x_3$（并说明已收敛） | **3 分** |

→ **启示：Newton 法题目一定要写满三次迭代并明确写出"到第三位小数不再变化，所以停止"。**

### 4.5 Q6 内部分值分配

- (a) $f=\cos(x)e^{-5x}$：**3 分**
- (b) $g=\dfrac{x}{\sqrt{x^{2}+4}}$：**4 分**（多给 1–2 分是**化简分**，因为这题化简最麻烦）
- (c) $y=\dfrac{e^{-x^{2}}}{x}$：**3 分**

老师："The second one I gave an extra simplification mark... given how complicated this one was."

在 Q6 的每个小题里，"each of these stages will probably get you one mark"——即**拆分 (Step 1)、求导 (Step 2)、代入公式并化简 (Step 3) 各自都有分**。

### 4.6 去年学生的实际表现（老师点出的易错处）

- Q1（True/False）："**the vast majority of people got 10 out of 10** for this question."
- 但其中 **(c) $\ln(2x)$ 那一小问最坑人**："I think this one was **the trickiest one that caught people up the most**. So just be a bit careful and make sure you simplify things a bit more."
- Q6(b)（商法则 + 链式法则 + 化简）："This one **caused a few issues when you were simplifying down** last year."

### 4.7 课堂行政信息

- 老师会把这份 Revision 幻灯片（含**比系里官方版本更详细的解答**）**上传到 Blackboard 作为这五题的标准答案**；幻灯片里有若干 typo（例如 Q6(a) 答案里漏掉的系数 5、漏掉的平方号、Q1(d) 里漏掉的 $n-1$ 指数），老师说会修正后再发布。
- 下周（Week 12）用同样的方式复习**积分**，讲评去年卷子里另外五题。
- 课堂时间不够，**Q6/Q7 的完整推导挪到 practical session 现场讲**。

---

## 五、Practical 要点

本周 Practical 文件夹里的材料就是 **2023–24 学年 EART11200 Toolkit – Maths and Physics 完整考卷**（The University of Manchester，June 2024，10 题 / 100 分，每题 10 分）。Practical 时段用于现场讲解课上没时间讲完的 Q6、Q7。

### 5.1 整卷结构（微分 vs 积分）

| 题号 | 内容 | 分值 | 归属 |
|---|---|---|---|
| 1 | True/False × 5，基本微分规则 | 10 | **微分（本周）** |
| 2 | 从选项中选出正确的 $\int f(x)\,dx$，需写过程 | 10 | 积分（Week 12） |
| 3 | Newton 法求根，精确到 3 位小数，$x_0=-0.6$ | 10 | **微分（本周）** |
| 4 | 定积分计算，答案精确到 3 位小数 | 10 | 积分 |
| 5 | 丁烷泄漏浓度 $G(t)$，求最大浓度出现的时间（优化） | 10 | **微分（本周）** |
| 6 | 求导三小问 (a)(b)(c)，尽量化简 | 10 | **微分（本周）** |
| 7 | 油箱泄漏：解析速率 vs 中心差分数值速率 + 百分比误差 | 10 | **微分（本周）** |
| 8 | 斜面 30° 上的物体：牛顿第二定律 → 积分求速度；反向力后求停止时间 | 10 | 力学 + 积分 |
| 9 | 人口方程 $\dfrac{dP}{dt}$：积分得 $P=P_0e^{t(\alpha-\beta)}$；换元积分 $(\psi-\beta P)$ | 10 | ODE + 积分 |
| 10 | 静力学方程：换元积分求 1400 m 处气压；$\alpha=0.01$ vs $0.02$ 的百分比差异 | 10 | ODE + 积分 |

→ **微分部分正好 5 题、50 分**，与老师说的"the five questions that on the last year's exam cover the differentiation"完全吻合。

### 5.2 五道微分真题 — 完整解答

#### Q1（10 分）True or False

**(a)** 若 $f(x)=\cos(2x)$，则 $\dfrac{df}{dx}=2\sin(2x)$？
> **FALSE.** 正确答案：$\dfrac{df}{dx}=-2\sin(2x)$。
> 理由：链式法则让 $2$ 掉出来，**但 $\cos$ 求导后是 $-\sin$，负号不能丢**。

**(b)** 若 $f(x)=e^{-2x}$，则 $\dfrac{df}{dx}=-\dfrac{e^{-2x}}{2}$？
> **FALSE.** 正确答案：$\dfrac{df}{dx}=-2e^{-2x}$。
> 老师原话："when you differentiate exponential, **it jumps out**, it doesn't become [a fraction]. That only happens when you **integrate**. If you integrated $e^{-2x}$, that's what [$-e^{-2x}/2$] would be."
> **→ 这是"微分 × 积分"的经典混淆陷阱：微分时系数乘出来，积分时系数除下去。**

**(c)** 若 $f(x)=\ln(2x)$，则 $\dfrac{df}{dx}=\dfrac{1}{2x}$？
> **FALSE.** 正确答案：$\dfrac{df}{dx}=\dfrac{1}{x}$。
> 老师给的最简证法（**用对数法则拆开**）：
> $$\ln(2x)=\ln 2+\ln x\ \Longrightarrow\ \frac{d}{dx}\big[\ln 2+\ln x\big]=0+\frac{1}{x}=\frac{1}{x}$$
> （$\ln 2$ 是常数，导数为 0。）
> 也可用链式法则验证：$\dfrac{1}{2x}\times 2=\dfrac{1}{x}$。
> **→ 老师说这题是全卷最坑人的一问。**

**(d)** 若 $f(x)=5x^{n}$，则 $\dfrac{df}{dx}=5nx^{n-1}$？
> **TRUE.**（原卷印刷时把指数 $n-1$ 漏掉了，老师课上说"imagine there's a mystical $n-1$ up there"，按 $n-1$ 理解则为真。）

**(e)** 若 $f(x)=\sin(x)$，则 $\dfrac{d^{2}f}{dx^{2}}=-\sin(x)$？
> **TRUE.** $\sin x\xrightarrow{\ d/dx\ }\cos x\xrightarrow{\ d/dx\ }-\sin x$。

#### Q3（10 分）Newton's method

**题目**：用 Newton 法求 $f(x)=e^{x}-x^{2}$ 的根，精确到 3 位小数，起始猜测 $x_0=-0.6$。公式：$x_{n+1}=x_n-\dfrac{f(x_n)}{f'(x_n)}$。

**Step 0 — 求导（1 分）**
$$f(x)=e^{x}-x^{2}\ \Longrightarrow\ f'(x)=e^{x}-2x$$

**Step 1 — 第一次迭代（3 分）**
$$f(x_0)=e^{-0.6}-(-0.6)^{2}=0.548812-0.36=0.188812$$
$$f'(x_0)=e^{-0.6}-2(-0.6)=0.548812+1.2=1.748812$$
$$x_1=x_0-\frac{f(x_0)}{f'(x_0)}=-0.6-\frac{0.188812}{1.748812}=-0.7079657$$

**Step 2 — 第二次迭代（3 分）**
$$f(x_1)=e^{-0.7079657}-(-0.7079657)^{2}=0.492614-0.501215=-0.008601$$
$$f'(x_1)=0.492614+1.415931=1.908545$$
$$x_2=-0.7079657-\frac{-0.008601}{1.908545}=-0.703458$$

**Step 3 — 第三次迭代（3 分）**
$$f(x_2)\approx 0.494881-0.494853=0.000028,\qquad f'(x_2)\approx 1.901797$$
$$x_3=-0.703458-\frac{0.000028}{1.901797}\approx-0.703473$$

**结论**：$x_2$ 与 $x_3$ 在**第三位小数上已经相同**（$-0.703$），达到收敛判据，停止迭代。
$$\boxed{x\approx-0.703}$$

> 老师："if you compare the second guess to the third guess, you can see that **to three decimal places they're exactly the same. And that's where you would stop.**"
> ⚠️ 转写中老师口述的中间数字（"−0.734"）是口误/自动转写错误，正确的收敛值是 **−0.703**（幻灯片明确写 "So the root of $f(x)$ correct to 3 decimal places is $x=-0.703$"）。

#### Q5（10 分）优化 — 气体泄漏

**题目**：丁烷以可变速率泄漏，浓度 $G$（单位 μg m⁻³），$t$ 以分钟计：
$$G(t)=3+14t-5t^{2}$$
求最大浓度出现的时间。

**解**：
$$\frac{dG}{dt}=14-10t$$
令导数为零：
$$14-10t=0\ \Longrightarrow\ \boxed{t=1.4\ \text{minutes}}$$

> 老师："a fairly simple question. You just differentiate the function, you set it to zero, and you solve for $t$."
> **注意**：题目只说 "find the maximum"，**没说 prove**，所以不需要再用二阶导数验证（若要验证：$\dfrac{d^2G}{dt^2}=-10<0$，确为极大值）。

#### Q6（10 分）求导并化简

**(a) $f=\cos(x)\,e^{-5x}$（3 分）— Product rule**

Step 1 拆分：$u=\cos x$，$v=e^{-5x}$
Step 2 求导：$\dfrac{du}{dx}=-\sin x$，$\dfrac{dv}{dx}=-5e^{-5x}$
Step 3 代入 $\dfrac{df}{dx}=u\dfrac{dv}{dx}+v\dfrac{du}{dx}$：
$$\frac{df}{dx}=-5\cos(x)\,e^{-5x}-\sin(x)\,e^{-5x}$$
提取公因子 $-e^{-5x}$：
$$\boxed{\frac{df}{dx}=-e^{-5x}\big(5\cos x+\sin x\big)}$$

> ⚠️ 幻灯片这一步有 typo（把 $5\cos x$ 写成了 $\cos x$）；课堂上有学生当场问 "Where did the coefficient of 5 on cos x go?"，老师答 "That's an error. That should say **5 cos x**." 老师会修正后再发布解答。

**(b) $g=\dfrac{x}{\sqrt{x^{2}+4}}$（4 分）— Quotient rule + Chain rule**

Step 1 拆分：$u=x$，$v=\sqrt{x^{2}+4}=(x^{2}+4)^{1/2}$
Step 2 求导：
$$\frac{du}{dx}=1$$
$$\frac{dv}{dx}=\tfrac12(x^{2}+4)^{-1/2}\cdot 2x=\frac{x}{\sqrt{x^{2}+4}}\quad(\text{链式法则})$$
Step 3 代入 $\dfrac{dg}{dx}=\dfrac{v\frac{du}{dx}-u\frac{dv}{dx}}{v^{2}}$：
$$\frac{dg}{dx}=\frac{\sqrt{x^{2}+4}\cdot 1-x\cdot\dfrac{x}{\sqrt{x^{2}+4}}}{\big(\sqrt{x^{2}+4}\big)^{2}}=\frac{\sqrt{x^{2}+4}-\dfrac{x^{2}}{\sqrt{x^{2}+4}}}{x^{2}+4}$$
分子分母同乘 $\sqrt{x^{2}+4}$（即"乘以 1"）：
$$=\frac{(x^{2}+4)-x^{2}}{(x^{2}+4)\sqrt{x^{2}+4}}=\boxed{\frac{4}{(x^{2}+4)^{3/2}}}$$

> 老师课堂上专门补讲了 $\dfrac{dv}{dx}$ 的链式法则细节："when you differentiate the square root, you get $1/(2\sqrt{\ })$... and then you differentiate what's inside so you get the $2x$. So the 2s would cancel, so you get $x$ divided by the square root."
> 这题是去年**化简翻车最多**的一题，额外给了化简分。

**(c) $y=\dfrac{e^{-x^{2}}}{x}$（3 分）— Quotient rule + Chain rule**

Step 1 拆分：$u(x)=e^{-x^{2}}$，$v(x)=x$
Step 2 求导：$\dfrac{du}{dx}=-2x\,e^{-x^{2}}$（链式法则：指数留下，$-2x$ 掉出来），$\dfrac{dv}{dx}=1$
Step 3 代入商法则：
$$\frac{dy}{dx}=\frac{x\cdot(-2x e^{-x^{2}})-e^{-x^{2}}\cdot 1}{x^{2}}=\frac{-2x^{2}e^{-x^{2}}-e^{-x^{2}}}{x^{2}}$$
$$=\boxed{-\frac{e^{-x^{2}}\big(2x^{2}+1\big)}{x^{2}}}$$

#### Q7（10 分）解析 vs 中心差分 + 百分比误差

**题目**：某油箱有缓慢泄漏，油量 $V$ 随时间 $t$ 变化，$V_0=10$（体积单位 m³），$0<t<24$（小时）。求 $t=2$ 小时时的泄漏速率：先用**解析法**求，再用**中心差分**（时间步长 $\Delta t=30$ 分钟 $=0.5$ h）数值求，并估计数值结果的百分比误差。

**解法框架**（幻灯片 39–43 页）：

1. **解析法**：对 $V(t)$ 用 **product rule** 求导（Step 1 拆分 → Step 2 分别求导 → Step 3 代入公式），得到 $\dfrac{dV}{dt}$，再代入 $t=2$：
   $$\left.\frac{dV}{dt}\right|_{t=2}=-1.10363$$
2. **数值法（central difference）**：$\Delta t=0.5$ h，所以要在 $t=1.5$ 和 $t=2.5$ 处计算 $V$：
   $$\left.\frac{dV}{dt}\right|_{t=2}\approx\frac{V(2.5)-V(1.5)}{2\times 0.5}=\frac{V(2.5)-V(1.5)}{1}=-1.13079$$
3. **百分比误差**：以解析值为基准
   $$100\times\frac{-1.13079-(-1.10363)}{-1.10363}=100\times\frac{-0.02716}{-1.10363}=\boxed{2.46\%}$$

> ⚠️ 材料缺陷：$V(t)$ 的具体表达式在 PDF→MD 转换中是图片，未能保留（只知道它需要用**乘积法则**求导，且含 $V_0=10$）。**需要原式请查 `Revision_Differentiation.pdf` 第 39–43 页或 `2324_Exam.pdf` 第 4 页。** 但解题**流程、三个关键数值、百分比误差的算法**已完整记录，这是本题的得分骨架。
>
> **百分比误差公式要记住**：$\text{\% error}=100\times\dfrac{\text{numerical}-\text{analytical}}{\text{analytical}}$（本题老师取的是相对解析值的相对误差）。
>
> **中心差分的陷阱**：$\Delta t=30$ 分钟 $=0.5$ 小时（**必须换算单位**），且分母是 $2\Delta t=1$，不是 $0.5$。

---

## 六、易错点 / 重点难点（重点为老师亲口指出的）

| # | 易错点 | 老师原话 / 说明 |
|---|---|---|
| 1 | **$\cos$ 求导忘记负号** | "when you differentiate cos, **make sure that you introduce a negative** because cos goes to minus sine." Q1(a) 就是考这个。 |
| 2 | **微分与积分中指数系数的方向搞反** | $\dfrac{d}{dx}e^{-2x}=-2e^{-2x}$（系数**乘出来**）；$\int e^{-2x}dx=-\tfrac12 e^{-2x}$（系数**除下去**）。"when you differentiate exponential, **it jumps out**... That only happens when you integrate." |
| 3 | **$\ln(kx)$ 的导数** | $\dfrac{d}{dx}\ln(2x)=\dfrac1x$ 而**不是** $\dfrac{1}{2x}$。拆成 $\ln 2+\ln x$ 最不容易错。**"the trickiest one that caught people up the most."** |
| 4 | **商法则分子顺序** | 是 $v\,du-u\,dv$，**不是** $u\,dv-v\,du$。老师："you'll need to remember the **v du minus u dv**"，并说这是三条法则里最容易在考场上犯迷糊的一条。 |
| 5 | **商法则后的化简** | Q6(b) 去年"caused a few issues"。技巧：把复合分式的分子分母同乘 $\sqrt{\cdot}$。安慰性提示：即使化简不完全，只要法则用对，"it'll probably be okay"。 |
| 6 | **$f''(x)=0$ 时不能下结论** | 不是"一定是鞍点"，而是**无法判断**，必须回到一阶导数在两侧的符号来判断。 |
| 7 | **中心差分的分母是 $2\Delta x$** | 前向/后向差分分母是 $\Delta x$，中心差分是 $2\Delta x$，写错直接结果错一倍。 |
| 8 | **Newton 法的收敛判据** | "三位小数"意思是**第三位小数不再变化**才停，必须做满并展示三次迭代（每次 3 分）。 |
| 9 | **向量记号 $\langle\ \rangle$ vs 坐标 $(\ )$** | "$\langle-2,5\rangle$ is **fundamentally different** from writing $(-2,5)$." 向量还要加箭头。 |
| 10 | **偏导数时其他变量当常数** | 求 $\partial f/\partial x$ 时 $y$ 视为常数；求 $\partial f/\partial y$ 时 $x$ 视为常数。"a really important distinction"。 |
| 11 | **梯度是向量不是标量** | 对标量场求导得到的 $\nabla f$ **是向量**，同时给出方向与大小。 |
| 12 | **不要多做证明** | 题目只说 "find the maximum" 时，**不必**再用二阶导数证明；只有写 "prove" 才要证。 |
| 13 | **单位：弧度优先** | "assume it's **radians** unless otherwise stated"；只有题目明确出现"30 degrees"这类才用度。 |
| 14 | **算错就停 = 0 分** | 最致命的考试习惯。**做错也要一路做到底**，可以拿 follow-through marks（可能挽回 5–6 分）。 |
| 15 | **草稿纸不批改** | 所有要给分的内容必须写进 pink booklet。 |
| 16 | **单位换算** | Q7 的 $\Delta t=30$ 分钟必须换成 $0.5$ 小时（因为方程用小时）。 |

---

## 七、本周术语表

| 英文术语 | 中文 | 说明 |
|---|---|---|
| **derivative** | 导数 | $f'(x)=\dfrac{dy}{dx}$，$y$ 相对 $x$ 的变化率 |
| **rate of change** | 变化率 | 导数的物理含义 |
| **analytical (solution)** | 解析解 | 能写出精确表达式的导数 |
| **numerical (approximation)** | 数值近似 | 用有限差分逼近导数 |
| **Euler backward step** | 后向（欧拉）差分 | $\dfrac{y_x-y_{x-\Delta x}}{\Delta x}$ |
| **Euler forward step** | 前向（欧拉）差分 | $\dfrac{y_{x+\Delta x}-y_x}{\Delta x}$ |
| **central difference** | 中心差分 | $\dfrac{y_{x+\Delta x}-y_{x-\Delta x}}{2\Delta x}$，对光滑函数最准确 |
| **step size** | 步长 | $\Delta x$ 或 $\Delta t$ |
| **chain rule** | 链式法则 | $\dfrac{df}{dx}=\dfrac{df}{dg}\dfrac{dg}{dx}$ |
| **product rule** | 乘积法则 | $u\dfrac{dv}{dx}+v\dfrac{du}{dx}$ |
| **quotient rule** | 商法则 | $\dfrac{v\,du/dx-u\,dv/dx}{v^{2}}$（转写误作 "Cauchy rule"） |
| **stationary value / stationary point** | 驻点 | 使 $f'(x)=0$ 的点 |
| **maximum / minimum** | 极大值 / 极小值 | 由 $f''$ 符号判定 |
| **saddle point** | 鞍点 | 既非极大也非极小 |
| **turning point** | 转折点 | 函数由增变减（或反之）的点 |
| **inflection point** | 拐点 | 凹凸性改变的点 |
| **optimisation** | 优化 | 用导数寻找最大/最小值 |
| **first-order derivative** | 一阶导数 | $f'(x)$ |
| **second-order derivative** | 二阶导数 | $f''(x)=\dfrac{d^{2}f}{dx^{2}}$ |
| **order (of a differential equation)** | （微分方程的）阶 | 微分次数 |
| **steady state** | 稳态 | 关键变量不随时间变化，$\dfrac{d^2V}{dt^2}=0$；流入 = 流出 |
| **root (of a function)** | 根 | 使 $f(x)=0$ 的 $x$ |
| **Newton's method / Newton–Raphson method** | 牛顿法 / 牛顿–拉夫森法 | $x_{n+1}=x_n-\dfrac{f(x_n)}{f'(x_n)}$ |
| **iterative / iteration** | 迭代（的） | 反复代入直到收敛 |
| **convergence / converge** | 收敛 | 相邻迭代值的差趋于零 |
| **starting guess / initial guess** | 初始猜测 | $x_0$ |
| **stopping criteria / threshold** | 停止判据 / 阈值 | 如"三位小数不变" |
| **Ordinary Differential Equation (ODE)** | 常微分方程 | 只含一个自变量的导数方程 |
| **homogeneous, linear, second-order ODE** | 齐次线性二阶常微分方程 | $a y''+b y'+c y=0$ |
| **initial value problem** | 初值问题 | 给定初始条件 |
| **boundary value problem** | 边值问题 | 给定上下边界条件 |
| **radioactive decay equation** | 放射性衰变方程 | $\dfrac{dN}{dt}=-\lambda N$ |
| **hydrostatic equation** | 静力学（气压）方程 | $\dfrac{dP}{dz}=-\rho g$ |
| **ideal gas law** | 理想气体定律 | $\rho=\dfrac{P}{R_aT}$，$R_a=287\ \mathrm{J\,kg^{-1}K^{-1}}$ |
| **Fourier's Law** | 傅里叶定律 | 热通量 $\propto-\dfrac{dT}{dx}$ |
| **Fick's Law** | 菲克定律 | $J=-D\dfrac{dC}{dx}$ |
| **Brownian motion** | 布朗运动 | 随机热运动，扩散的微观机制 |
| **diffusion coefficient** | 扩散系数 | $D$ |
| **flux** | 通量 | 单位时间单位面积通过的量 |
| **scalar field** | 标量场 | $f(x,y)$，有大小无方向 |
| **vector field** | 向量场 | 每点分配一个向量，有大小有方向 |
| **magnitude** | 大小 / 模长 | $|\vec a|=\sqrt{a_1^2+a_2^2+a_3^2}$ |
| **direction** | 方向 | 向量的第二属性 |
| **Cartesian (coordinates / form)** | 笛卡尔（坐标 / 形式） | 沿 $x,y,z$ 分解，单位向量 $\hat i,\hat j,\hat k$ |
| **component** | 分量 | 向量沿某轴的部分 |
| **partial derivative** | 偏导数 | $\dfrac{\partial f}{\partial x}$，"curly d" |
| **partial differential equation (PDE)** | 偏微分方程 | 本课只讲概念，不要求求解 |
| **grad / nabla / $\nabla f$** | 梯度 | $\nabla f=\dfrac{\partial f}{\partial x}\hat i+\dfrac{\partial f}{\partial y}\hat j+\dfrac{\partial f}{\partial z}\hat k$，是向量 |
| **Jacobian** | 雅可比（矩阵） | 多维函数二次求导得到的矩阵（明年内容，本课不考） |
| **crib sheet** | 速查表 / 小抄表 | 主手册 Ch.12，**不可带入考场** |
| **follow-through marks** | 后续步骤分 | 前面算错但方法正确，后续仍给分 |

---

## 附：本周复习行动清单

1. **把 2023–24 真题（Practical 文件夹）当作最重要的模拟卷**，因为"今年的题会非常相似"。
2. **反复练三大法则的"拆分 → 求导 → 代入化简"三步流程**，直到不看公式也知道流程。
3. **背熟基本微分表**（虽然考场会给，但熟练能省大量时间），特别注意 $\cos\to-\sin$ 和 $\ln$ 的形式。
4. **Newton 法**：练到能规范写出三次迭代 + 收敛说明。
5. **中心差分 + 百分比误差**：熟练单位换算与 $2\Delta t$ 分母。
6. **偏导数**：练习对 $f(x,y)$ 或 $f(x,y,z)$ 求全部偏导并写出 $\nabla f$。
7. **考场心态**：**永远不要留白，做错也要做完**。
8. 关注 Blackboard 上老师修正 typo 后发布的这五题标准答案。
9. 下周（Week 12）是**积分复习**，会讲评真题 Q2/Q4/Q8/Q9/Q10。
