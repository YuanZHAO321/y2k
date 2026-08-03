# Week 2 — 微分入门 (Introduction to Differentiation)

> 课程：EART11200 The Natural Scientist's Toolkit — Mathematics and Physics
> 授课日期：03/02（学校周次 Week 21，课程第 2 周）
> 本周材料：`Lecture/Week 2/Chapter2.md`、`Lecture/Week 2/lecture2(4).md`、`Lecture/Week 2/EART11200 - 03-Feb-transcript.md`、`Practical/Week 2/Exercises2.md`、`Practical/Week 2/Solutions2.md`、`Practical/Week 2/practical2_soln(5).md`、主手册 `main(1).md` 第 680–1003 行（Chapter 2）

---

## 一、本周主题

本周把 Week 1 的**数值求梯度 (numerical gradients)** 正式升级为**解析微分 (analytical differentiation)**：先用极限定义 $\dfrac{dy}{dx}=\lim\limits_{\Delta x\to 0}\dfrac{\Delta y}{\Delta x}$ 从一阶原理 (first principles) 推出直线与二次函数的导数，从中归纳出**幂律 (power rule)**，然后给出一张**常见函数导数表 (table of common differentials)**，最后引入**和的导数等于导数的和 (sum rule)**。

在全课 12 周脉络中的位置：

| 周 | 主题 | 与本周关系 |
|---|---|---|
| Week 1 | Calculating Gradients（有限差分：向后/向前/中心差分） | 本周的**出发点**：本周就是把 Week 1 的 $\Delta x$ 取极限到 0 |
| **Week 2** | **Introduction to Differentiation** | **本周** |
| Week 3 | Differentiating Combinations of Functions（链式/乘积/商法则） | 本周只讲**和**，复合、乘积、商留到下周 |
| Week 4 | Optimisation & Properties of Derivatives | 讲师说 sin/cos 求导为何如此、为何 cos 求导带负号，将在 Week 4 解释 |
| Week 5 | Second Order Derivatives & Root Finding | |
| Week 6–10 | 积分与进阶 | 本周 Q2.4「反过来求原函数」正是**积分 (integration)** 的预告，包括积分常数 |

**Intended Learning Outcomes（幻灯片原文三条）**

1. Describe the concept of differentiation and explain its significance in calculus.（描述微分的概念并解释其在微积分中的意义）
2. Identify and interpret common notation used in differentiation.（识别并解读微分的常用记号）
3. Apply common laws of differentiation to solve theoretical and real-world problems.（把常见微分法则用于理论与真实世界问题）

---

## 二、核心概念

### 2.1 从 Week 1 回顾：三种有限差分法与记号约定

讲师本周开场花了很长时间澄清 Week 1 的下标记号（transcript 明确说上周讲得太快、幻灯片上的向后差分公式写错了、已更新）。统一约定如下：

- $y_x$ ＝ **y current**，在 $x$ 处求值的 $y$
- $y_{x-\Delta x}$ ＝ **y previous**，在 $x-\Delta x$ 处求值的 $y$
- $y_{x+\Delta x}$ ＝ **y future**，在 $x+\Delta x$ 处求值的 $y$

三种方法（幻灯片 3–5 页）：

**Euler 向后法 (Euler's Backward Method)** — 往回看一步：

$$\frac{dy}{dx}=\lim_{\Delta x\to 0}\frac{\Delta y}{\Delta x}\equiv\lim_{\Delta x\to 0}\frac{y_x-y_{x-\Delta x}}{\Delta x}$$

**Euler 向前法 (Euler's Forward Method)** — 往前看一步：

$$\frac{dy}{dx}=\lim_{\Delta x\to 0}\frac{\Delta y}{\Delta x}\equiv\lim_{\Delta x\to 0}\frac{y_{x+\Delta x}-y_x}{\Delta x}$$

**中心差分法 (Central Differences Method)** — 两边都看，所以分母是 $2\Delta x$：

$$\frac{dy}{dx}=\lim_{\Delta x\to 0}\frac{\Delta y}{\Delta x}\equiv\lim_{\Delta x\to 0}\frac{y_{x+\Delta x}-y_{x-\Delta x}}{2\Delta x}$$

Week 1 用的例函数（transcript 口述）是 $y=\left(\dfrac{\sqrt{x}+x-10}{3}\right)^2$，在 $x=16$ 处求导；步长取 $\Delta x=2$，即用 14、16、18 三个点。中心差分时 $16\to14$ 与 $18\to16$ 各跨 2，合计 $2\Delta x=4$。

**Week 1 的两个关键结论（本周的逻辑起点）**：

1. 不同方法、不同步长给出**不同**的梯度估计，各有各的误差。选哪个"非常 case dependent"（取决于函数、场景等等）。
2. 步长越小，数值近似越接近解析导数；但步长越小计算量越大 —— **精度与计算量之间有权衡 (a balance between computation and accuracy)**。

### 2.2 为什么需要微分：从"每点手算"到"一个梯度函数"

主手册 §2.1 用 $f(x)=2x^3-20x^2+x+4000$ 说明：这条曲线的梯度**随 $x$ 变化**，不是常数：

- 在 $x=-5$：梯度陡且为正
- 在 $x=0$：梯度几乎为零
- 在 $x=5$：梯度较缓且为负

如果只会 Week 1 的方法，你就得在每个感兴趣的点画切线／算有限差分。讲师在课上反复强调这一点的荒谬之处："如果我叫你在 $x=2.5$、$2.15$、$2.156$ 再各算一遍，那会 really really irritating。"

**微分的作用**：直接给出一个**描述梯度的函数** $\dfrac{dy}{dx}$（也写作 $f'(x)$），叫作**梯度函数 (gradient function)** 或**导函数**。有了它，代入任何 $x$ 都能立刻得到该点梯度。对上面这个三次函数：

$$f'(x)=6x^2-40x+1$$

讲师还补了一个更深层的理由：低维函数还能画图看；一旦进入**高维函数 (high dimensional functions)** 或很复杂的函数，根本画不出来，那时只能靠解析导数，不能靠"画图＋量切线"。

### 2.3 导数的定义（极限定义）

$$\boxed{\;\frac{dy}{dx}=f'(x)=\lim_{\Delta x\to 0}\frac{\Delta y}{\Delta x}\;}$$

符号含义：

- $\Delta x$：$x$ 的**有限增量 (finite increment)**，一个可以量出来的间隔
- $\Delta y$：由 $\Delta x$ 引起的 $y$ 的变化
- $\dfrac{\Delta y}{\Delta x}$：**平均变化率**，即割线斜率（Week 1 算的就是它）
- $\lim\limits_{\Delta x\to 0}$：让增量**无穷小 (infinitesimally small)**
- $\dfrac{dy}{dx}$：**导数 (derivative)**，$y$ 对 $x$ 的**瞬时变化率 (instantaneous rate of change)**，即该点**切线 (tangent)** 的斜率

**主手册 Figure 2.2 的意思**：在曲线上取 $P=(x,y)$ 与 $Q=(x+\Delta x_1,\;y+\Delta y_1)$。若换一个更小的增量组合 $(\Delta x_2,\Delta y_2)$，算出的 $\dfrac{\Delta y}{\Delta x}$ 会**不同**。即（幻灯片 11 页）：

$$\frac{\Delta y_1}{\Delta x_1}\neq\frac{\Delta y_2}{\Delta x_2},\qquad\text{但}\qquad\frac{dy}{dx}=\lim_{\Delta x\to 0}\frac{\Delta y}{\Delta x}\ \text{是唯一的}$$

增量越小，越逼近真值。取极限就把"近似"变成了"精确"。

### 2.4 "瞬时"两个字为什么重要（讲师反复强调）

transcript 里讲师专门停下来问："Why is it important that I keep saying instantaneous?"

- 有限差分给的是**某个区间上的平均变化率**（discrete，离散的），依赖于你选的步长和方法；
- 导数给的是**恰好在那一点的变化率**（not discrete, instantaneous），不依赖任何步长，是精确值。

这就是从 Week 1 到 Week 2 的本质飞跃：**numerical → analytical**。

### 2.5 一阶原理推导 I：直线 (derivative of a straight line)

设 $y=ax$，$a$ 为常数。几何上梯度处处相同，所以我们**预期** $\dfrac{dy}{dx}=a$。用向前法推导：

**Step 1** 从 $(x,y)$ 沿 $x$ 轴平移 $\Delta x$，到达 $(x+\Delta x,\;y+\Delta y)$，代入直线方程：

$$y+\Delta y=a(x+\Delta x)=ax+a\Delta x$$

**Step 2** 两边减去原式 $y=ax$：

$$y+\Delta y-y=ax+a\Delta x-ax$$
$$\Delta y=a\,\Delta x$$

**Step 3** 两边除以 $\Delta x$：

$$\frac{\Delta y}{\Delta x}=a$$

**Step 4** 取极限 $\Delta x\to 0$。右边**根本不含 $\Delta x$**（讲师当堂提问"会发生什么？"答案是"Nothing!"），所以：

$$\frac{dy}{dx}=\lim_{\Delta x\to 0}\frac{\Delta y}{\Delta x}=a$$

**结论**：$y=ax\;\Longrightarrow\;\dfrac{dy}{dx}=a$。导数是常数 $a$，与预期一致。

### 2.6 一阶原理推导 II：二次函数 (derivative of a quadratic)

设 $y=ax^2$。同样从 $(x,y)$ 前移 $\Delta x$：

**Step 1** 代入并展开（注意 $(x+\Delta x)^2=x^2+2x\Delta x+(\Delta x)^2$）：

$$y+\Delta y=a(x+\Delta x)^2=a\big(x^2+2x\Delta x+(\Delta x)^2\big)=ax^2+2ax(\Delta x)+a(\Delta x)^2$$

**Step 2** 两边减去 $y=ax^2$：

$$y+\Delta y-y=ax^2+2ax(\Delta x)+a(\Delta x)^2-ax^2$$
$$\Delta y=2ax(\Delta x)+a(\Delta x)^2$$

**Step 3** 两边除以 $\Delta x$：

$$\frac{\Delta y}{\Delta x}=2ax+a\,\Delta x$$

**Step 4** 取极限 $\Delta x\to 0$：第一项 $2ax$ **不含** $\Delta x$，保持不变；第二项 $a\Delta x\to 0$，消失。

$$\frac{dy}{dx}=2ax$$

**结论**：$y=ax^2\;\Longrightarrow\;\dfrac{dy}{dx}=2ax$。

> ⚠️ transcript 的自动转写在这里有两处口误／漏字：一处把 $\Delta y$ 写成 "2ax delta x + delta x squared"（漏了系数 $a$），一处结尾说 "dy by dx is equal to two a"（漏了 $x$）。**以幻灯片第 16 页与手册为准：$\dfrac{dy}{dx}=2ax$。**

### 2.7 归纳出幂律 (power rule)

把上面的过程对更高次多项式重复，模式就出来了（主手册黑体原话）：**multiplying the original function of $x$ by its power** 并 **reducing the power that $x$ is raised to by 1** ——「把幂次拿到前面来乘，再把幂次减 1」。

$$\boxed{\;y=x^n\;\Longrightarrow\;\frac{dy}{dx}=nx^{n-1}\;}\qquad\qquad\boxed{\;y=ax^n\;\Longrightarrow\;\frac{dy}{dx}=anx^{n-1}\;}$$

讲师明确说：**不要求你证明这个规则**，直接当既成事实 (take it as read) 用；但要练到熟。

**适用条件**：$n$ 可以是任意实数 —— 正整数、负数（$1/x^n=x^{-n}$）、分数（$\sqrt{x}=x^{1/2}$）都适用。练习题 Q2.5(d) 与 practical Exercise 1(b) 就是专门考这一点的。

### 2.8 指数函数的导数（讲师认为最"有意思"的一条）

- $y=e^x\;\Longrightarrow\;\dfrac{dy}{dx}=e^x$ —— **求导后完全不变**。讲师说这在数学里是"really interesting, really powerful"，因为它跟前面所有函数的行为都不一样。
- $y=e^{kx}\;\Longrightarrow\;\dfrac{dy}{dx}=ke^{kx}$ —— 指数里 $x$ 前面的常数 $k$ **掉下来乘在前面**，其余不变。
- $y=e^{f(x)}\;\Longrightarrow\;\dfrac{dy}{dx}=\dfrac{df}{dx}\,e^{f(x)}$ —— 指数里若是任意函数 $f(x)$（二次、三次、sin、cos、log 都行），就**把这个函数拿出来但必须先求导**，指数部分原样保留。

讲师点明第三条其实就是**链式法则 (chain rule)** 的特例，Week 3 会正式讲。

记忆口诀：**指数求导，指数永远还在；只是可能要额外乘一个东西**（$k$ 或 $\frac{df}{dx}$）。

### 2.9 对数与三角函数

- $y=\ln(x)\;\Longrightarrow\;\dfrac{dy}{dx}=\dfrac{1}{x}$。讲师说这条"a little bit weird because it changes form completely" —— 不像指数保形，对数求导后**彻底变形**成了一个幂函数。
- $y=\sin(x)\;\Longrightarrow\;\dfrac{dy}{dx}=\cos(x)$
- $y=\cos(x)\;\Longrightarrow\;\dfrac{dy}{dx}=-\sin(x)$

**sin/cos 的循环 (cyclical loop)**（讲师板书强调）：

$$\sin x\;\xrightarrow{\;d/dx\;}\;\cos x\;\xrightarrow{\;d/dx\;}\;-\sin x\;\xrightarrow{\;d/dx\;}\;-\cos x\;\xrightarrow{\;d/dx\;}\;\sin x\;\to\cdots$$

求导 4 次回到原点。讲师坦言："I still to this day forget which differential gives me minus in front of cos and sine" —— 所以别死记，记住这个环。为什么是这样、为什么带负号，**Week 4 会解释**（可以用无穷级数／微分方程证明，本课不要求）。

### 2.10 和的法则 (sum rule)

$$\boxed{\;\frac{d}{dx}\big[f(x)+g(x)\big]=\frac{df}{dx}+\frac{dg}{dx}\;}$$

主手册原话：**the derivative of the sum is equal to the sum of the derivatives**（和的导数等于导数的和）；也说微分对求和是"invariant"的。实践上：**逐项求导即可**。

幻灯片例子：

$$y=5x+e^x\;\Longrightarrow\;\frac{dy}{dx}=5+e^x$$

主手册例子：

$$y=2x^2+3x\;\Longrightarrow\;\frac{dy}{dx}=4x+3$$

**适用条件与边界**：和／差都成立（差就是加负数），常数因子可以提出来。但**乘积、商、复合函数不能这样逐项做** —— 这正是 Week 3 的内容（chain rule / product rule / quotient rule）。这条法则也自动推广到 $\sum$ 求和号（见 Q2.6(a)）。

### 2.11 什么是微积分（幻灯片 "WHAT IS CALCULUS?"）

- 微积分不只是一套算法，它是**一种语言和一种推理方式 (a language and a way of reasoning)**。
- 本课会用特定记号来构建这种推理，并用它求解若干物理定律。
- 幻灯片上那句 **"Differentiation goes from right to left!"** 指的是课上画的那个"微积分循环"图：从函数 $f(x)$ 出发，**向右**用大 S 符号 $\int$ 积分 → 得到曲线下面积／绝对量；**向左**微分 → 得到变化率。两者互为逆过程。积分从 Week 6 开始讲。

### 2.12 应用：放射性衰变 (radioactive decay) —— 本周的招牌应用

**微分方程 (differential equation)**：

$$\frac{dN}{dt}=-\lambda N \tag{2.1}$$

- $N$：不稳定核的数目 (number of unstable nuclei)
- $t$：时间
- $\lambda$：**衰变常数 (decay constant)**，控制衰变快慢
- 物理含义（讲师原话）：**任一时刻核数目的变化率，正比于当时还剩多少核**。负号表示在减少。

**它的解 (solution)**：

$$N(t)=N_0e^{-\lambda t}=N_0\exp(-\lambda t) \tag{2.2}$$

其中 $N_0$ 是 $t=0$ 时的初始核数（常数）。

**记号说明**（讲师专门讲的一段）：$e^{-\lambda t}$ 与 $\exp(-\lambda t)$ **完全等价**，可互换使用。当指数里东西很多（比如一串求和）时，写 $\exp(\cdot)$ 更清爽好读。计算器上按 $e^x$ 就是它。

**本周的高潮：证明 (2.2) 确实是 (2.1) 的解**

对 (2.2) 关于 $t$ 求导。$N_0$ 是常数不动，指数部分用 $\dfrac{d}{dt}e^{kt}=ke^{kt}$，这里 $k=-\lambda$：

$$\frac{dN}{dt}=N_0\cdot(-\lambda)e^{-\lambda t}=-\lambda\,N_0e^{-\lambda t}$$

注意到括号里那一坨 $N_0e^{-\lambda t}$ **就是 $N$ 本身**，所以：

$$\frac{dN}{dt}=-\lambda N \qquad\checkmark$$

讲师评语："Notice how we have used the rule for obtaining derivatives of exponential functions and then simplified to show the **instantaneous decay is proportional to the existing abundance**."（瞬时衰变率正比于现存丰度）—— 这是物理与化学中极重要的结果。

**半衰期形式**：

$$\lambda=\frac{\ln 2}{t_{1/2}},\qquad N=N_0\left(\frac{1}{2}\right)^n \tag{2.3}$$

$t_{1/2}$ 是**半衰期 (half-life)**，$n$ 是已经过去的半衰期个数。每过一个半衰期，剩下 $N_0/2$；再过一个，剩 $N_0/4$，依此类推。

---

## 三、公式与图表

### 3.1 记号对照

| 记号 | 读法 | 含义 |
|---|---|---|
| $\dfrac{dy}{dx}$ | "dy by dx" | $y$ 对 $x$ 的导数（Leibniz 记号） |
| $f'(x)$ | "f dash x" / "f prime" | 同上（Lagrange 记号），讲师说两者**完全等价、可互换** |
| $\dfrac{df}{dx}$、$\dfrac{dg}{dx}$、$\dfrac{dh}{dx}$ | | 对应函数 $f,g,h$ 的导数，practical 解答中常用 |
| $\dfrac{dN}{dt}$、$\dfrac{dV}{dt}$、$\dfrac{dP}{dz}$ | | 对**时间／高度**求导，物理量场景 |
| $\Delta x,\Delta y$ | "delta x" | **有限**增量，用于数值近似（Week 1） |
| $\lim\limits_{\Delta x\to 0}$ | | 极限，把有限增量压缩到无穷小 |
| $\exp(x)$ | | 与 $e^x$ 完全等价 |
| $\sum$ | "sigma" | 求和算子，例：$\sum_{x=1}^{4}3x=3+6+9+12=30$ |

### 3.2 幂律的具体展开（幻灯片第 17 页表）

| 函数 $y=f(x)$ | 导数 $\dfrac{dy}{dx}$ |
|---|---|
| $a$（常数） | $0$ |
| $ax$ | $a$ |
| $ax^2$ | $2ax$ |
| $ax^3$ | $3ax^2$ |
| $ax^4$ | $4ax^3$ |
| $x^n$ | $nx^{n-1}$ |
| $ax^n$ | $anx^{n-1}$ |

### 3.3 ★ 常见函数导数表 (Table 2.1: List of common differentials)

这是本周**最重要的一张表**，手册、幻灯片、practical 每一页都在重复它。讲师说：表中**大部分条目会出现在考试公式册 (exam formula book) 里，不需要背**，但练得多自然就记住了。

| 函数 $y=f(x)$ | 导数 $\dfrac{dy}{dx}$ | 备注 |
|---|---|---|
| constant（常数） | $0$ | 常数没有变化率 |
| $x$ | $1$ | 即 $n=1$ 的幂律 |
| $x^n$ | $nx^{n-1}$ | **幂律**，$n$ 可为负数／分数 |
| $ax^n$ | $anx^{n-1}$ | 常数因子直接带着走 |
| $e^x$ | $e^x$ | 求导不变，唯一具此性质 |
| $e^{kx}$ | $ke^{kx}$ | $k$ 为常数，掉到前面 |
| $e^{f(x)}$ | $\dfrac{df}{dx}\,e^{f(x)}$ | 链式法则特例（Week 3 详讲） |
| $\ln(x)$ | $\dfrac{1}{x}$ | 完全变形 |
| $\sin(x)$ | $\cos(x)$ | |
| $\cos(x)$ | $-\sin(x)$ | 注意负号 |

**由基本表推出的常用衍生结果**（本周习题里反复用到，建议一并记住）：

| 函数 | 改写为 | 导数 |
|---|---|---|
| $\sqrt{x}$ | $x^{1/2}$ | $\tfrac12x^{-1/2}=\dfrac{1}{2\sqrt{x}}$ |
| $\dfrac{1}{x}$ | $x^{-1}$ | $-x^{-2}=-\dfrac{1}{x^2}$ |
| $\dfrac{1}{x^n}$ | $x^{-n}$ | $-nx^{-n-1}$ |
| $2\ln(x)$ | | $\dfrac{2}{x}$ |
| $\ln(2x)$ | $\ln 2+\ln x$ | $\dfrac{1}{x}$（**不是** $\tfrac{1}{2x}$） |
| $e^{5x+4}$ | $f(x)=5x+4,\ f'=5$ | $5e^{5x+4}$ |
| $\sqrt{\pi}$、$\ln 2$ 等 | 常数 | $0$ |

### 3.4 Figure 2.1（主手册／幻灯片第 12 页）文字描述

**上图**：$f(x)=2x^3-20x^2+x+4000$ 在 $x\in[-10,10]$ 上的曲线，纵轴 0–5000。图上在三个位置画出了直角三角形（$\Delta x$ 与 $\Delta y$）表示切线斜率：

| 位置 | 标注梯度 | 用 $f'(x)=6x^2-40x+1$ 验算 |
|---|---|---|
| $x=-5$ | $m_1=\Delta Y/\Delta X=351.0$ | $6(25)-40(-5)+1=150+200+1=351$ ✓ |
| $x=0$ | $m_2=1.0$ | $0-0+1=1$ ✓ |
| $x=5$ | $m_3=-49.0$ | $6(25)-200+1=150-200+1=-49$ ✓ |

**下图**：梯度函数 $f'(x)=6x^2-40x+1$，纵轴 $-500$ 到 1500。它是一条开口向上的抛物线：在 $x\approx0$ 之前为正，$x\approx0$ 到 $x\approx6$ 之间为负，之后又变正。（精确零点：$x=\frac{40\pm\sqrt{1576}}{12}$，即 $x\approx0.025$ 与 $x\approx6.64$。）

**要读懂的关键对应关系**：上图曲线**上升**处 ↔ 下图 $f'>0$；上图**峰／谷**处 ↔ 下图 $f'=0$；上图**下降**处 ↔ 下图 $f'<0$。这是 Week 4「优化」的伏笔。

> 手册图注有个笔误：写成 $f(x)=2x^3-20x^2+x*4000$，应为 $+4000$。

### 3.5 Figure 2.2 / 2.3 / 2.4 文字描述

- **Figure 2.2**：一条 $y$ 随 $x$ **非线性**增长的曲线，标出 $P=(x,y)$ 与 $Q=(x+\Delta x_1,y+\Delta y_1)$。$P$、$Q$ 两点的梯度不同 → 说明割线斜率依赖增量选择。
- **Figure 2.3**：一条**线性**增长的直线，$P$ 与 $Q$ 的梯度**相同** → 所以我们预期导数是常数。对应 §2.5 的推导。
- **Figure 2.4**：一条**二次**增长的曲线，$P$ 与 $Q$ 梯度不同。对应 §2.6 的推导。

### 3.6 本周出现的物理／地球科学方程汇总

| 方程 | 形式 | 解 | 领域 |
|---|---|---|---|
| 放射性衰变 | $\dfrac{dN}{dt}=-\lambda N$ | $N=N_0e^{-\lambda t}$ | 核物理、地质年代学 |
| 半衰期形式 | $\lambda=\dfrac{\ln 2}{t_{1/2}}$ | $N=N_0(1/2)^n$ | 同上 |
| 流体静力学方程 (hydrostatic equation) | $\dfrac{dP}{dz}=-\dfrac{g}{R_aT}P$ | $P(z)=P_0\exp\!\left(-\dfrac{gz}{R_aT}\right)$ | 大气科学、流体力学 |
| 线性排水 | $V(t)=V_0-\dfrac{t}{c}$ | — | 水文／生态系统水库 |
| 指数排水／泄漏 | $V(t)=V_0\exp(-t/c)$ | — | 水文、气体泄漏 |

**流体静力学方程的符号**：$P$ 压强，$z$ 高度，$g$ 重力加速度，$R_a$ 干空气气体常数，$T$ 温度（本题中 $g$、$R_a$、$T$ 均假设为常数）。手册明确说它与放射性衰变方程"formulation 相似"，Week 后期会大量使用。

---

## 四、课堂补充

以下内容只在 transcript 里出现，幻灯片和手册上没有：

### 4.1 课程管理／评估信息

- **Blackboard 结构**：每周一个独立版块，含 lecture、practical、weekly exercises、quiz。
- **每周小测 (quiz)** 是 **formative（形成性，不计分）**，约 **10 题**，考的是"我认为你考试需要的关键材料"，包含**我期望你在考试里会算的那类计算**。本周的 quiz 当周发布，**解答下一周才放出来**。
- 讲师应学生要求，为 Week 1 那几道"算梯度"的练习题做了一个 **Excel 电子表格**放上 Blackboard，可以交互地看向后／向前／中心差分是怎么算的（因为把每一步手算都印出来会有好几页）。他也据反馈**扩写了部分解答**。
- 欢迎邮件反馈，他会持续更新材料。
- **考试**：大部分导数表条目会印在**考试公式册**里，不必背；讲师明确说**不会要求你在考试里重做一阶原理的推导**（"You don't have to recreate this for the exam"）。但"who knows we may have a mini question on the exam on how to calculate a gradient" —— Week 1 的有限差分仍可能考。
- 每周的 **weekly assessment** 会有大量关于这些基本法则的题。

### 4.2 学习方法建议（讲师反复说）

- "You don't have to really understand the maths necessarily. If you keep plugging away the process you'll start to learn something." —— 先把流程练熟，理解会随之而来。
- "Keep trying things over and over and over again... things will start to sink into your brain."
- 把这些法则当工具用：手册原话是"treat these rules as an engineer might treat a **screwdriver or hammer**"，随身带着 **crib sheet / maths survival pack**（数学生存包）。
- 幻灯片最后一页 "YOUR GROWING SKILLS LIBRARY" —— 呼应课名 "Natural Scientist's **Toolkit**"，每周往工具带里加工具。

### 4.3 数学内容上的课堂补充

- 讲师承认 Week 1 幻灯片上的 **Euler 向后法公式写错了**，本周已修正（"That's the wrong formula. We'll have to fix that."）。
- 关于精度与成本：真实科研中解微分方程往往"**一行代码**"就够（他提到本学期稍后 David Topping 的部分会涉及），但我们这里手算是为了理解机制。
- 关于为什么 $e^x$ 求导不变：讲师说"in the practicals if you're really interested I can show you how it works"，可以用**无穷级数 (infinite sums)** 或微分方程证明，本课不作要求。
- 关于 sin/cos：为什么 cos 求导带负号，"if you plot cos and sine over each other, you can kind of see how this works" —— 把两条曲线叠画就能看出来；**Week 4 会正式讲**。
- $e^{f(x)}$ 的规则被讲师明确标记为**下周 chain rule 的预告**。
- 下周（Week 3）预告的三类"更复杂的组合"：**composite functions（复合函数）**、**product of two functions（乘积）**、**quotient of two functions（商）**。

---

## 五、Practical 要点

### 5.1 Practical 的目的

本周 practical（`practical2_soln(5).md`，共 11 页）目标与讲座 ILO 完全一致，重点是**动手把导数表用起来**：先做纯代数的"重写表达式再求导"，再做一个真实的**氦气罐泄漏 (gas leak)** 场景，并把**解析导数**与 Week 1 的**中心差分数值导数**做定量对比。核心信息是：**解析法给精确瞬时值，数值法在步长足够小时非常接近它**。

每一页幻灯片右侧都常驻那张导数表 —— 讲师有意让你养成"查表 → 套用"的习惯。

---

### 5.2 Practical Exercise 1：Rearranging Expressions（重写表达式）

> 对 $x$ 求导：

**(a) $y=4x^3+2x^2+5x+6$**

用和的法则逐项求导，每项用 $ax^n\to anx^{n-1}$：

$$\frac{d}{dx}(4x^3)=12x^2,\quad \frac{d}{dx}(2x^2)=4x,\quad \frac{d}{dx}(5x)=5,\quad \frac{d}{dx}(6)=0$$
$$\boxed{\frac{dy}{dx}=12x^2+4x+5}$$

**(b) $f(x)=\sqrt{x}$**

**关键技巧：先把根号改写成分数幂**（这正是"rearranging expressions"的意思）。

$$f(x)=x^{1/2}\;\Longrightarrow\;\frac{df}{dx}=\frac12x^{1/2-1}=\frac12x^{-1/2}=\boxed{\frac{1}{2\sqrt{x}}}$$

**(c) $g(x)=4x^4+e^x-\cos(x)$**

逐项：$4x^4\to16x^3$；$e^x\to e^x$；$-\cos x\to-(-\sin x)=+\sin x$（**两个负号相消**）。

$$\boxed{\frac{dg}{dx}=16x^3+e^x+\sin(x)}$$

**(d) $h(x)=e^{5x+4}$**

用 $e^{f(x)}\to\frac{df}{dx}e^{f(x)}$，这里 $f(x)=5x+4$，$\frac{df}{dx}=5$：

$$\boxed{\frac{dh}{dx}=5e^{5x+4}}$$

（也可看作 $e^{5x+4}=e^4\cdot e^{5x}$，常数 $e^4$ 提出，$e^{5x}\to5e^{5x}$，结果相同。）

---

### 5.3 Practical Exercise 2：Gas Leak（氦气罐泄漏）

#### 第一部分：线性泄漏

> 一个氦气罐在漏气，气体体积随时间 $t$（分钟）为
> $$V(t)=V_0-\frac{t}{60},\qquad V_0=1\ \text{m}^3,\quad 0<t<60$$
> 泄漏速率是多少？这个速率合理吗？

**解**：对 $t$ 求导。$V_0$ 是常数 → 0；$-\frac{t}{60}=-\frac{1}{60}t$ 是 $t$ 的一次项 → $-\frac{1}{60}$。

$$\boxed{\frac{dV}{dt}=-\frac{1}{60}\ \text{m}^3\,\text{min}^{-1}}\quad\text{（常数）}$$

**物理讨论（这是本题真正的考点）**：速率恒定意味着不管罐里还剩多少气，都以同样速度漏 —— **"It is unlikely that the rate of the gas leak is constant."** 真实情况下罐内压强随气体流失而下降，驱动泄漏的压差变小，速率会**逐渐减慢**。所以线性模型只是粗糙的一阶近似。

（另外注意：负号表示体积在**减少**；定义域 $0<t<60$ 正好保证 $V$ 不会变成负数，$t=60$ 时刚好漏完。）

#### 第二部分：指数泄漏

> 更真实的模型：
> $$V(t)=V_0\exp\left(-\frac{t}{6}\right),\qquad V_0=1\ \text{m}^3,\quad 0<t<60$$
> (i) 6 分钟时的泄漏速率是多少？(ii) 与中心差分法（$t=6$ 两侧各 0.1 分钟）比较。

**(i) 解析解**：用 $e^{kt}\to ke^{kt}$，这里 $k=-\frac16$：

$$\frac{dV}{dt}=V_0\cdot\left(-\frac16\right)\exp\left(-\frac{t}{6}\right)=-\frac16\exp\left(-\frac{t}{6}\right)$$

代入 $t=6$：

$$\frac{dV}{dt}(6)=-\frac16\exp(-1)=-\frac{0.367879}{6}=\boxed{-0.061313\ \text{m}^3\,\text{min}^{-1}}$$

**(ii) 数值解（中心差分）**：取 $\Delta t=0.2$，即用 $t=5.9$ 与 $t=6.1$：

$$\frac{\Delta V}{\Delta t}(6)=\frac{V(6.1)-V(5.9)}{6.1-5.9}=\frac{\exp(-6.1/6)-\exp(-5.9/6)}{0.2}$$

$$=\frac{0.361799-0.374063}{0.2}=\frac{-0.012263}{0.2}=\boxed{-0.061316\ \text{m}^3\,\text{min}^{-1}}$$

**误差计算**：

$$\text{Error}=100\times\left|\frac{-0.061313+0.061316}{-0.061313}\right|\approx0.005\%$$

（幻灯片印为 $0.004\%$，同一量级；核心结论是"**It is fairly accurate with a small step-size**"。）

**这道题的教学意义**：把 Week 1（数值）与 Week 2（解析）**焊在一起** —— 数值法在步长小时非常准，但它需要两次函数求值且只给出一个点的近似；解析法一次性给出**任意点**的精确速率。

---

### 5.4 Weekly Exercises（`Exercises2.md` / `Solutions2.md`）完整梳理

> 手册在开头说明了题目的两大分类：
> 1. **Algebraic problems（代数题）** —— "纯"数学题，不绑定具体应用，目的就是练熟求导方法。
> 2. **Real-world problems（真实世界题）** —— 给你一个情境，需要你**建立问题框架 (framing)**；未必要做冗长推导，而是理解导数扮演的角色。
>
> 建议：先不看 crib sheet 试做，卡住了再翻。
> 两个补充说明：(1) $\sum$ 是求和算子，例如 $\sum_{x=1}^{4}3x$ 表示 $x$ 从 1 到 4 步长为 1 求和；(2) $\sqrt{x}$ 可改写为 $x^{1/2}$。

#### 【代数题】

**Question 2.1** 对 $x$ 求导：

| 题 | 函数 | 解法 | 答案 |
|---|---|---|---|
| (a) | $f(x)=5x^2$ | $anx^{n-1}$，$a=5,n=2$ | $\dfrac{df}{dx}=10x$ |
| (b) | $g(x)=10x^3$ | $a=10,n=3$ | $\dfrac{dg}{dx}=30x^2$ |
| (c) | $h(x)=11x^1$ | $a=11,n=1$ → $11\cdot1\cdot x^0=11$ | $\dfrac{dh}{dx}=11$ |

> (c) 是个陷阱：$x^1$ 求导得 $x^0=1$，不是 0。

**Question 2.2** 多项式求导（和的法则 + 幂律逐项）：

- (a) $f(x)=5x^3+2x^2+3x+5\;\Longrightarrow\;\dfrac{df}{dx}=15x^2+4x+3$（常数 5 → 0）
- (b) $g(x)=10x^3+x+5\;\Longrightarrow\;\dfrac{dg}{dx}=30x^2+1$
- (c) $h(x)=11x^5+2x^4+2x^3+x^2+3x+2\;\Longrightarrow\;\dfrac{dh}{dx}=55x^4+8x^3+6x^2+2x+3$

**Question 2.3** 在指定 $x$ 处求梯度（**两步：先求导函数，再代入数值**）。
> ⚠️ 官方 `Solutions2.md` 这一题的答案在 PDF→md 转换中丢失（只剩题号）。以下为完整推算：

- (a) $f(x)=x^2-3x$ → $f'(x)=2x-3$ → $f'(10)=20-3=\mathbf{17}$
- (b) $f(x)=5x^5-2x$ → $f'(x)=25x^4-2$ → $f'(0)=0-2=\mathbf{-2}$
  （注意：函数在 $x=0$ 处值为 0，但梯度不是 0！）
- (c) $f(x)=10x-3x^7$ → $f'(x)=10-21x^6$ → $f'(-2)=10-21\cdot64=10-1344=\mathbf{-1334}$
  （注意：$(-2)^6=+64$，**偶次幂结果为正**，这是最常见的失分点。）

**Question 2.4** 反向操作：什么函数求导后得到下式？（提示：把微分过程倒过来做）

这题是**积分 (integration) 的预演**。反向规则：把幂次 **+1**，再**除以**新的幂次。

| 题 | $\dfrac{dy}{dx}$ | 反推过程 | $y$ |
|---|---|---|---|
| (a) | $2x$ | 幂次 $1\to2$，系数 $2/2=1$ | $y=x^2\;(+c)$ |
| (b) | $-3x^3$ | 幂次 $3\to4$，系数 $-3/4$ | $y=-\dfrac34x^4\;(+c)$ |
| (c) | $7$ | $7=7x^0$，幂次 $0\to1$ | $y=7x+d$ |

> 官方解答在 (c) 后特意加了一句：**"$d$ is a constant. Why do you think we need this? Ask in class if this is unclear."**
>
> **答案**：因为**任何常数求导都得 0**，所以 $7x$、$7x+1$、$7x-100$ 求导后**都**等于 7。仅凭导数无法确定那个常数，因此原函数是一整族平行曲线，必须带上任意常数 $d$。这就是后面积分里的**积分常数 (constant of integration)**。严格来说 (a)、(b) 也应该加 $+c$。

**Question 2.5** 求导：

| 题 | 函数 | 解法要点 | 答案 |
|---|---|---|---|
| (a) | $y=10x(5x+3x)$ | **先化简再求导**：$5x+3x=8x$，$y=10x\cdot8x=80x^2$ | $\dfrac{dy}{dx}=160x$ |
| (b) | $y=50x^2+30x^2$ | 先合并同类项：$=80x^2$ | $\dfrac{dy}{dx}=160x$ |
| (c) | $y=3ce^{ix}$ | $3c$ 是常数因子；$e^{kx}\to ke^{kx}$，$k=i$ | $\dfrac{dy}{dx}=3cie^{ix}$ |
| (d) | $y=\sqrt{x}=x^{1/2}$ | 分数幂 | $\dfrac{dy}{dx}=\dfrac12x^{-1/2}=\dfrac{1}{2\sqrt{x}}$ |
| (e) | $y=\cos(x)$ | 查表 | $\dfrac{dy}{dx}=-\sin(x)$ |
| (f) | $y=e^{5x}$ | $k=5$ | $\dfrac{dy}{dx}=5e^{5x}$ |
| (g) | $y=3x+5y$ | **必须先重排**：$y-5y=3x\Rightarrow-4y=3x\Rightarrow y=-\tfrac34x$ | $\dfrac{dy}{dx}=-\dfrac34$ |
| (h) | $y=2\ln(x)$ | 常数因子 2 提出，$\ln x\to1/x$ | $\dfrac{dy}{dx}=\dfrac{2}{x}$ |

> (a)(b) 的教学点：官方解答特意把两题设成**同一个函数的两种伪装**（都等于 $80x^2$），提醒你**动笔前先化简**。
> (g) 的教学点：等号两边都有 $y$，直接求导会出错；必须先解出 $y$ 的显式表达式。（若题目原意是 $y=3x+5$，则答案为 3；但按字面 $5y$ 应作重排处理，与 practical 的 "Rearranging Expressions" 主题一致。）

**Question 2.6** 稍难的求导：

| 题 | 函数 | 解法要点 | 答案 |
|---|---|---|---|
| (a) | $y=\sum_i 3ce^{ix}$ | **和的导数 = 导数的和**，逐项用 $e^{kx}\to ke^{kx}$（$k=i$）；官方解答明确注明"See Section 2.4" | $\dfrac{dy}{dx}=\sum_i3cie^{ix}$ |
| (b) | $y=\dfrac{4x}{\pi}$ | $\dfrac{4}{\pi}$ 只是个数字常数 | $\dfrac{dy}{dx}=\dfrac{4}{\pi}$ |
| (c) | $y=\cos(x)+\sin(x)$ | 逐项 | $\dfrac{dy}{dx}=-\sin(x)+\cos(x)$ |
| (d) | $y=e^{5x+4}$ | $f(x)=5x+4,\ f'=5$ | $\dfrac{dy}{dx}=5e^{5x+4}$ |
| (e) | $y=\ln(2x)$ | 用对数律拆开：$\ln(2x)=\ln2+\ln x$，$\ln 2$ 是常数→0 | $\dfrac{dy}{dx}=\dfrac{1}{x}$ |
| (f) | $y=4x^4+e^x+\sin(x)$ | 三项分别用幂律／指数／三角 | $\dfrac{dy}{dx}=16x^3+e^x+\cos(x)$ |

> (b) 在 md 转换中排版损坏（$4x$ 被吸到上一行、分数线丢失）。若原题实为 $y=\sqrt{\pi}$，那它是纯常数，答案为 $0$ —— 两种读法都在考"**认出常数**"。
> (e) 是最经典的陷阱：答案是 $\frac1x$ 而**不是** $\frac{1}{2x}$。
> 官方 `Solutions2.md` 中 (b)–(f) 的答案同样在转换中丢失，上表为完整推算。

#### 【真实世界题】

**Question 2.7 — 放射性衰变**

给定：$\dfrac{dN}{dt}=-\lambda N$ (2.1)；$N(t)=N_0e^{-\lambda t}$ (2.2)；$N=N_0(1/2)^n$ (2.3)；$\lambda=\dfrac{\ln2}{t_{1/2}}$。

**(a) 对 (2.2) 求导并代回，证明它满足 (2.1)。**

$$\frac{dN}{dt}=\frac{d}{dt}\left(N_0e^{-\lambda t}\right)=N_0\cdot(-\lambda)e^{-\lambda t}=-\lambda N_0e^{-\lambda t}$$

代回 (2.1) 的右边，或者反过来识别 $N_0e^{-\lambda t}=N$：

$$\frac{dN}{dt}=-\lambda\underbrace{\left(N_0e^{-\lambda t}\right)}_{=N}=-\lambda N\qquad\checkmark$$

官方解答的措辞："Therefore Equation 2.2 is indeed the solution to the radioactive decay equation!"

**(b) $t_{1/2}=30$ 年，初始 10,000 个核，用 (2.3) 求 90 年后剩多少。**

90 年 = 3 个半衰期，故 $n=3$：

$$N=10000\times\left(\frac12\right)^3=10000\times\frac18=\boxed{1250}$$

**(c) 用 (2.2) 重算。**

先求衰变常数：

$$\lambda=\frac{\ln2}{t_{1/2}}=\frac{0.6931}{30}=0.023105\ \text{yr}^{-1}$$

代入：

$$N(90)=10000\times e^{-0.023105\times90}=10000\times e^{-2.0794}=10000\times0.125=\boxed{1250}$$

**结论**：两种方法结果**完全一致**（官方解答："i.e. the same"）。这不是巧合 —— (2.3) 就是 (2.2) 在 $t=nt_{1/2}$ 时的重写：$e^{-\lambda t}=e^{-\frac{\ln2}{t_{1/2}}\cdot nt_{1/2}}=e^{-n\ln2}=2^{-n}=(1/2)^n$。

**Question 2.8 — 流体静力学方程 (hydrostatic equation)**

> 大气／流体力学的基本原理，描述压强如何随高度变化。设 $g$、$R_a$、$T$ 均为常数：
> $$\frac{dP}{dz}=-\frac{g}{R_aT}P$$
> 证明 $P(z)=P_0\exp\!\left(-\dfrac{gz}{R_aT}\right)$ 是它的解。

**解**（与 Q2.7(a) 完全同构 —— 手册就是这么设计的）：对 $z$ 求导，用 $e^{kz}\to ke^{kz}$，其中 $k=-\dfrac{g}{R_aT}$（因为 $g,R_a,T$ 都是常数）：

$$\frac{dP}{dz}=P_0\cdot\left(-\frac{g}{R_aT}\right)\exp\left(-\frac{gz}{R_aT}\right)=-\frac{g}{R_aT}\underbrace{P_0\exp\left(-\frac{gz}{R_aT}\right)}_{=P(z)}=-\frac{g}{R_aT}P\qquad\checkmark$$

官方解答："Therefore $P(z)$ is indeed the solution to the hydrostatic equation!"

**物理意义**：大气压强随高度**指数衰减**；$H=\dfrac{R_aT}{g}$ 称为**标高 (scale height)**，是压强下降到 $1/e$ 所需的高度。手册预告后面会大量用到它。

**Question 2.9 — 生态系统水库的排水速率**

> ⚠️ **材料说明**：本题 (a)–(d) 四个小问的体积函数在主手册中**全部是图片**，md 转换后丢失；`Solutions2.md` 里对应的公式与数值也同样丢失，只剩下解题步骤的说明文字。以下按现存文字＋practical 的同构题重建方法框架。

**已知**：$V_0=1\times10^{-2}\ \text{m}^3$ 为 $t=0$ 时的水量；(b)(c)(d) 均要求在 $t=600\ \text{s}$ 处求排水速率，**并**用**有限差分法**（$\Delta t=20$ s，即 $t=590$ s 与 $t=610$ s，各偏离 10 s）做数值对比。

**统一解题流程（四小问通用，务必掌握）**：

1. **解析部分**：对 $t$ 求导得到 $\dfrac{dV}{dt}$ 的表达式（查导数表：多项式用幂律，$\exp$ 用 $e^{kt}\to ke^{kt}$）。
2. 代入 $t=600$，得到该时刻的**瞬时排水速率**，单位 $\text{m}^3\,\text{s}^{-1}$。
3. **数值部分**：用**中心差分**
   $$\frac{\Delta V}{\Delta t}(600)=\frac{V(610)-V(590)}{610-590}=\frac{V(610)-V(590)}{20}$$
4. **对比**：两者应当非常接近；可算相对误差 $100\times\left|\dfrac{\text{数值}-\text{解析}}{\text{解析}}\right|\%$。
5. **物理解读**：负号 = 水在流失；数值大小 = 流失有多快。

**各小问的已知信息**：

- **(a)** 线性模型（形如 $V(t)=V_0-ct$）。官方解答原话：**"We can see that the drainage rate is constant here."** —— 求导后 $\dfrac{dV}{dt}=-c$，与时间无关。这一问不要求数值对比。
- **(b)(c)(d)** 分别是三种"非常数排水速率"的模型（practical 的同构题用的是 $V(t)=V_0\exp(-t/c)$ 型），每一问都要**解析 + 中心差分**双算并比较。

> 与 practical Exercise 2 的对照可以直接迁移：那里 $V(t)=V_0\exp(-t/6)$，$\dfrac{dV}{dt}=-\dfrac16\exp(-t/6)$，在 $t=6$ 得 $-0.061313$，中心差分（$h=0.1$）得 $-0.061316$，误差 $\approx0.005\%$。Q2.9 就是同一套流程换数字。
>
> **精确公式请回看 `Exercises2.pdf` / `Solutions2.pdf` 原件。**

### 5.5 本周关键解题技巧总结

1. **先化简，再求导**（Q2.5(a)(b)、Q2.6(e)、Q2.5(g)）—— 合并同类项、展开括号、用对数律拆开、把方程解出显式 $y$。
2. **把根号／分式改写成幂**（Q2.5(d)、Exercise 1(b)）：$\sqrt{x}=x^{1/2}$，$\dfrac{1}{x^n}=x^{-n}$。
3. **认出常数**：$\pi$、$e^4$、$\ln2$、$N_0$、$V_0$、$P_0$、$c$、$g/R_aT$ 都是常数，求导为 0 或作为因子带走。
4. **"求梯度"= 两步走**：先求导函数，再代入数值（Q2.3）。
5. **验证微分方程的解 = 求导 + 代回识别原函数**（Q2.7(a)、Q2.8）：求导后，把结果里出现的那一坨**认回原函数**，就是全部技巧。
6. **解析 vs 数值对比**（Q2.9、Exercise 2）：解析给精确瞬时值，中心差分在小步长下误差可低至千分之几个百分点。

---

## 六、易错点 / 重点难点

**记号与概念**

1. **$\Delta y/\Delta x$ 与 $dy/dx$ 不是一回事**。前者是有限区间上的**平均**变化率（依赖步长与方法），后者是**瞬时**变化率（唯一、精确）。只有取极限 $\Delta x\to0$ 才把前者变成后者。
2. $f'(x)$ 与 $\dfrac{dy}{dx}$ **完全等价**，考卷上两种都会出现。
3. 对**谁**求导要看清：$\dfrac{dN}{dt}$ 是对 $t$，$\dfrac{dP}{dz}$ 是对 $z$。别惯性地都当成对 $x$。
4. 中心差分的分母是 **$2\Delta x$**，不是 $\Delta x$ —— 因为跨了两个区间。

**幂律**

5. $x^1$ 求导得 **1**，不是 0（Q2.1(c)）。只有**常数**才求导得 0。
6. 系数不能丢：$\dfrac{d}{dx}(5x^2)=10x$，不是 $2x$。
7. 负数代入偶次幂：$(-2)^6=+64$（Q2.3(c)），别丢正负号。
8. 分数幂求导后仍是分数幂：$\dfrac12x^{-1/2}$ 要会写回 $\dfrac{1}{2\sqrt{x}}$。
9. 幂律**不能**用在指数函数上：$e^{kx}$ 的导数是 $ke^{kx}$，**不是** $kxe^{kx-1}$，也不是 $e^{kx}$ 本身。搞清"底数是常数、指数是变量"（指数函数）还是"底数是变量、指数是常数"（幂函数）。

**指数与对数**

10. $e^x\to e^x$（不变）；$e^{kx}\to ke^{kx}$（$k$ 掉下来）；$e^{f(x)}\to f'(x)e^{f(x)}$（拿出来还要求导）。三条别混。
11. $\ln(2x)$ 的导数是 $\dfrac{1}{x}$，**不是** $\dfrac{1}{2x}$。安全做法：先拆成 $\ln2+\ln x$。
12. $e^{5x+4}$：$+4$ 不影响导数中的因子，因子仍是 5（因为 $\frac{d}{dx}(5x+4)=5$）。

**三角函数**

13. $\cos$ 求导带**负号**，$\sin$ 不带。记住循环 $\sin\to\cos\to-\sin\to-\cos\to\sin$。
14. 遇到 $-\cos(x)$ 求导，两个负号相消得 $+\sin(x)$（Exercise 1(c)）。

**法则的适用范围**

15. **和／差**可以逐项求导；**乘积、商、复合函数不行**！$\dfrac{d}{dx}[f\cdot g]\neq f'\cdot g'$。这三种要等 Week 3 的 product / quotient / chain rule。本周题目里凡是出现乘积（如 Q2.5(a) $10x(5x+3x)$），都是**先展开化简**再用和的法则绕过去的。
16. **常数因子**可以提到导数外面：$\dfrac{d}{dx}[af(x)]=a\dfrac{df}{dx}$。

**反向求导（Q2.4）**

17. 反推原函数时**必须加任意常数** $+c$，因为常数求导为 0，信息丢失了。这是积分常数的雏形。
18. 反向规则是"幂次 +1 再除以新幂次"，别写成"幂次 −1"。

**应用题**

19. 导数的**符号有物理意义**：负号 = 减少（衰变、排水、泄漏、压强随高度下降）。
20. 导数有**单位**：$\dfrac{dV}{dt}$ 的单位是 $\text{m}^3\,\text{s}^{-1}$ 或 $\text{m}^3\,\text{min}^{-1}$，考试要写。
21. 验证"某函数是某微分方程的解"时，最后一步是**把求导结果里的那一坨认回原函数**（$N_0e^{-\lambda t}=N$），不是继续硬算。
22. 建模的合理性判断也是考点：常数速率的泄漏／排水模型往往**不现实**（practical Exercise 2 明确问 "Do you think the rate is sensible?"）。

**本周材料本身的错误（考前注意）**

23. 主手册 Figure 2.1 图注把 $+4000$ 印成了 $*4000$。
24. transcript 中二次函数推导有两处口误（漏 $a$、漏 $x$），正确结果是 $\dfrac{dy}{dx}=2ax$。
25. Week 1 幻灯片的向后差分公式讲师承认写错了，Week 2 已更正。
26. **主手册题号与章号不自洽**，引用题号请以周版 `Exercises2.md` / `Solutions2.md` 为准。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Differentiation | 微分（求导） | 由函数求出其变化率函数的运算 |
| Derivative | 导数 | $\dfrac{dy}{dx}$ 或 $f'(x)$，$y$ 对 $x$ 的瞬时变化率 |
| Gradient function | 梯度函数／导函数 | 描述原函数在每一点梯度的那个新函数 |
| First principles | 一阶原理 | 直接用极限定义 $\lim_{\Delta x\to0}\frac{\Delta y}{\Delta x}$ 推导导数的方法 |
| Limit | 极限 | 让某量（这里是 $\Delta x$）无限趋近某值（这里是 0）的过程 |
| Instantaneous rate of change | 瞬时变化率 | 恰在某一点的变化率，与"区间平均变化率"相对 |
| Rate of change | 变化率 | 一个量随另一个量变化的快慢 |
| Increment | 增量 | $\Delta x$、$\Delta y$，有限大小的改变量 |
| Infinitesimally small | 无穷小 | 小到可以忽略、但尚未真正为零 |
| Tangent | 切线 | 与曲线在一点相切的直线，其斜率即该点导数 |
| Finite difference | 有限差分 | 用有限增量近似导数的数值方法（Week 1） |
| Euler's Backward Method | 欧拉向后法 | $\frac{y_x-y_{x-\Delta x}}{\Delta x}$，用当前点与前一点 |
| Euler's Forward Method | 欧拉向前法 | $\frac{y_{x+\Delta x}-y_x}{\Delta x}$，用当前点与后一点 |
| Central Differences Method | 中心差分法 | $\frac{y_{x+\Delta x}-y_{x-\Delta x}}{2\Delta x}$，两侧都用，通常最准 |
| Step size | 步长 | 有限差分中所取的 $\Delta x$ 大小 |
| Analytical (derivative) | 解析（导数） | 用公式精确求得的导数，与"数值近似"相对 |
| Numerical (approximation) | 数值（近似） | 靠代入数字计算得到的近似结果 |
| Power rule | 幂律 | $x^n\to nx^{n-1}$：幂次提到前面，再减 1 |
| Sum rule | 和的法则 | 和的导数等于导数的和，可逐项求导 |
| Common differentials | 常见导数（表） | Table 2.1，本课要反复查用的基本导数清单 |
| Exponential function | 指数函数 | $e^x$ 或 $\exp(x)$，求导后形式不变 |
| Natural logarithm | 自然对数 | $\ln(x)$，导数为 $1/x$ |
| Polynomial | 多项式 | 若干 $x$ 的幂次项之和 |
| Quadratic | 二次函数 | 形如 $ax^2$ 的函数 |
| Linear | 线性（一次） | 形如 $ax$ 的函数，梯度恒定 |
| Constant | 常数 | 不随变量变化的量，导数为 0 |
| Constant of integration | 积分常数 | 反向求导时必须补上的任意常数（Q2.4 的 $d$） |
| Differential equation | 微分方程 | 含有导数的方程，如 $\frac{dN}{dt}=-\lambda N$ |
| Solution (of an ODE) | （微分方程的）解 | 代回后使方程恒成立的函数 |
| Radioactive decay | 放射性衰变 | 不稳定原子核释放能量趋于稳定的过程 |
| Decay constant $\lambda$ | 衰变常数 | 控制衰变快慢的常数，$\lambda=\ln2/t_{1/2}$ |
| Half-life $t_{1/2}$ | 半衰期 | 样品中不稳定核减半所需的时间 |
| Unstable nuclei | 不稳定核 | 会发生放射性衰变的原子核 |
| Hydrostatic equation | 流体静力学方程 | $\frac{dP}{dz}=-\frac{g}{R_aT}P$，描述压强随高度的变化 |
| Scale height | 标高 | $H=R_aT/g$，大气压强降至 $1/e$ 所需的高度 |
| Drainage rate | 排水速率 | 水库水量对时间的导数 $\frac{dV}{dt}$ |
| Chain rule | 链式法则 | 复合函数求导法则，Week 3 讲；本周 $e^{f(x)}$ 是其特例 |
| Optimisation | 优化 | 用导数找极值，Week 4 讲 |
| Crib sheet / Maths survival pack | 速查表／数学生存包 | 课程提供的公式小抄，鼓励随身携带查用 |
| Formative quiz | 形成性小测 | 不计入成绩、仅供自测复习的每周测验 |
