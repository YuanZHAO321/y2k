# Week 5 — 二阶导数与数值求根 (Second Order Derivatives & Root Finding)

> EART11200 The Natural Scientist's Toolkit — Mathematics and Physics
> 讲授日期：24/02/2025（校历 Week 24）｜本课程第 5 周
> 材料：`Lecture/Week 5/Chapter5.md`、`lecture5(1).md`、`EART11200 - 24-Feb-transcript.md`；`Practical/Week 5/Exercises5.md`、`Solutions5.md`、`practical5_soln(1).md`；主手册 `main(1).md` 第 5 章（1695–2058 行）

---

## 一、本周主题

### 1.1 本周在全课程中的位置

本周是**微分 (differentiation) 部分的收官周**。老师在课堂开场就说得很直白：

> "So what we're going to do today is we're going to finish up the topic of differentiation... And then from next week onwards, we're going to move on to integration."

整个微分板块的脉络：

| 周 | 主题 | 做了什么 |
|---|---|---|
| Week 1 | Calculating Gradients | 用手算割线/切线斜率，理解变化率 |
| Week 2 | Introduction to Differentiation | 把"手算梯度"形式化为微分法则 |
| Week 3 | Differentiating Combinations of Functions | 乘积法则、商法则、链式法则 |
| Week 4 | Optimisation & Properties of Derivatives | 驻点 (stationary values)、用 $f'$ 的正负判断增减、优化实例（金矿利润） |
| **Week 5** | **Second Order Derivatives & Root Finding** | **补齐 Week 4 遗留的两个缺口** |
| Week 6 起 | Introduction to Integration … | 转入积分 |

### 1.2 本周要补的两个"缺口"

Week 4 结束时留下了两个未解决的问题，本周正是为了填这两个坑：

**缺口 ①：如何"正式地"判断驻点是极大、极小还是鞍点？**
Week 4 用的是两种"非正式"手段：(a) 画出函数图像用眼睛看；(b) 在驻点两侧代入 $f'(x)$ 看符号变化。老师指出这两种方法在函数变复杂时不可靠：

> "We can't just rely on plotting a function or just evaluating it in each direction to figure out whether there is a maximum or minimum."

→ 本周引入**二阶导数判别法 (second derivative test)**。

**缺口 ②：如果 $f'(x)=0$ 这个方程解不出来怎么办？**
Week 4 的所有例子里，令导数为零后都能靠因式分解或求根公式解出 $x$。但这不是常态：

> "In all of our examples thus far, we've been able to solve a function for $x$ to get something equal to zero... But that might not always be possible."

→ 本周引入**牛顿-拉夫森法 (Newton-Raphson method / Newton's method)** 做数值求根。

### 1.3 Intended Learning Outcomes（讲义与 practical 均列出，考试考点导向）

1. Explain the concept and significance of **second-order derivatives** in the analysis of functions.
   （解释二阶导数的概念及其在函数分析中的意义）
2. **Compute second-order derivatives** of functions to **classify stationary values** as maxima, minima, or saddle points in optimisation problems.
   （计算二阶导数并用于分类驻点）
3. Describe **steady-state systems** in physical and mathematical modelling.
   （描述稳态系统）
4. Apply **Newton's Method** to find the **roots** of complex functions in numerical problem-solving.
   （应用牛顿法求根）

本周内容可归纳为**三块**：二阶导数（含驻点分类）→ 稳态 → 牛顿法求根。

---

## 二、核心概念

### 2.1 导数的"阶" (order of a derivative)

微分可以反复进行。对函数 $f(x)$：

$$
\text{一阶导数 (first-order derivative)}:\quad f'(x)=\frac{\mathrm{d}f}{\mathrm{d}x}=\frac{\mathrm{d}y}{\mathrm{d}x}
$$

$$
\text{二阶导数 (second-order derivative)}:\quad f''(x)=\frac{\mathrm{d}}{\mathrm{d}x}\!\left(\frac{\mathrm{d}f}{\mathrm{d}x}\right)=\frac{\mathrm{d}^{2}f}{\mathrm{d}x^{2}}=\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}
$$

**记号必须写对**（高频扣分点）：

- $\dfrac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}$ — 上面的 2 在 $\mathrm{d}$ 上，下面的 2 在 $x$ 上。这不是分数的平方。
- $\left(\dfrac{\mathrm{d}y}{\mathrm{d}x}\right)^{2}$ — 这是一阶导数的**平方**，完全不同的东西。
- $f''(x)$ 读作 "f double dash of x"（英式）/ "f double prime"（美式）。

**"阶"的实际用途**：老师提示这个概念在后面解微分方程时会正式用到。课程后期（Week 9 "Integrating Second Order ODEs"）会遇到形如

$$
a\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}+b\frac{\mathrm{d}y}{\mathrm{d}x}+cy=0
$$

的**二阶常微分方程 (second order ODE)**。老师特别指出：之前学过的**放射性衰变方程**就是它的退化情形——令 $a=0$，

$$
\frac{\mathrm{d}N}{\mathrm{d}t}=-\lambda N \;\Longrightarrow\; \frac{\mathrm{d}N}{\mathrm{d}t}+\lambda N=0
$$

正是上式在 $a=0,\;b=1,\;c=\lambda$ 时的样子。所以"阶"不是为了考试造出来的词，而是描述方程复杂度的标尺。

### 2.2 二阶导数的物理意义：变化率的变化率

一句话概括：

- $f'(x)$ 告诉我们**函数变化得多快**（rate of change of $f$）；
- $f''(x)$ 告诉我们**"变化得多快"这件事本身变化得多快**（rate of change of the rate of change）。

老师用**开车**这个例子讲（课上他一边在讲台上来回走一边讲）：

| 物理量 | 数学表达 | 含义 |
|---|---|---|
| 位移/距离 distance | $x = f(t)$ | 走了多远 |
| 速度 velocity | $v = \dfrac{\mathrm{d}x}{\mathrm{d}t}=f'(t)$ | 距离对时间的变化率 |
| 加速度 acceleration | $a = \dfrac{\mathrm{d}^{2}x}{\mathrm{d}t^{2}}=f''(t)$ | 速度对时间的变化率 |

> "So my rate of change of my distance is my velocity, but when you start changing the velocity, your rate of change in your velocity is your acceleration."

老师强调这不是为了考试而算：

> "This is a really, really important physical interpretation of what we'll see later in the term when we start looking at Newton's laws more specifically."

（Week 7 "Integration using Newton's Laws" 会反过来用积分从加速度还原速度、位移。）

**地球科学中的对应**：
- 地温梯度 $\mathrm{d}T/\mathrm{d}z$ 是一阶导；地温梯度沿深度是否变化 $\mathrm{d}^{2}T/\mathrm{d}z^{2}$ 是二阶导。若为零 ⇒ 线性地温剖面 ⇒ 稳态热传导。
- 污染物浓度随距离的衰减率 $\mathrm{d}C/\mathrm{d}x$；$\mathrm{d}^{2}C/\mathrm{d}x^{2}=0$ ⇒ 线性稀释 ⇒ 通量稳态。
- 沉积速率、地壳抬升速率的"加速/减速"都是二阶导数问题。

### 2.3 二阶导数判别法 (Second Derivative Test)

**规则**（设 $x=a$ 是驻点，即 $f'(a)=0$）：

$$
\boxed{
\begin{aligned}
f''(a) &< 0 \;\Longrightarrow\; x=a \text{ 是局部极大值 (local maximum)}\\
f''(a) &> 0 \;\Longrightarrow\; x=a \text{ 是局部极小值 (local minimum)}\\
f''(a) &= 0 \;\Longrightarrow\; \textbf{无法判定 (inconclusive)}
\end{aligned}}
$$

**为什么"负号 = 极大"？**（老师承认这"反直觉"：*"It seems slightly counterintuitive that negative equals maximum, positive equals minimum, but it does cross over."*）

理由：$f''$ 描述 $f'$ 的走向。
- 若 $f''(a)<0$，说明 $f'$ 在 $a$ 处**正在下降**，即 $f'$ 由正变负 ⇒ 函数先增后减 ⇒ 山顶 ⇒ 极大。曲线**上凸 (concave down)**，形状像 $\cap$。
- 若 $f''(a)>0$，说明 $f'$ 在 $a$ 处**正在上升**，即 $f'$ 由负变正 ⇒ 函数先减后增 ⇒ 谷底 ⇒ 极小。曲线**下凹 (concave up)**，形状像 $\cup$。

记忆法：$f''>0$ ⇒ $\cup$ ⇒ 像个"笑脸"/能盛水的碗 ⇒ 最低点是 minimum；$f''<0$ ⇒ $\cap$ ⇒ maximum。

**$f''(a)=0$ 时怎么办？**
判别法**失效**，不能得出任何结论。此时必须**退回 Week 4 的方法**：
1. 在 $a$ 左右两侧取点，检查 $f'(x)$ 的符号；
2. 或直接画图观察。

若 $f'$ 在两侧**同号**（都正或都负）⇒ 函数没有换向 ⇒ 是**鞍点 / 拐点 (saddle point / point of inflection)**；若变号则仍是极值。

> "If it's equal to zero, again, we're in the situation where we can't possibly conclude anything necessarily, so what we're going to have to do is revert back to the process you did last week."

**注意**：$f''(a)=0$ **不等于**"一定是鞍点"。例如 $f(x)=x^{4}$ 在 $x=0$：$f'(0)=0$，$f''(0)=0$，但 $x=0$ 是货真价实的极小值。这是判别法的一个"单向性"陷阱。

### 2.4 完整的驻点分析流程（考试标准答题步骤）

老师反复强调数学就是"churn the wheel"（照流程转轮子），本周的标准流程是：

```
Step 1  求一阶导数 f'(x)
Step 2  令 f'(x) = 0，解出所有驻点 x = a₁, a₂, …
Step 3  求二阶导数 f''(x)
Step 4  把每个 aᵢ 代入 f''(x)，按符号分类
          f''(aᵢ) < 0 → 极大   f''(aᵢ) > 0 → 极小   f''(aᵢ) = 0 → 转 Step 5
Step 5  （仅当 f''(aᵢ)=0）检查 aᵢ 两侧 f' 的符号 / 画图，判定是否为鞍点
Step 6  （若题目要求"驻点的值"）把 aᵢ 代回原函数 f(x) 求出 f(aᵢ)
```

Step 6 容易漏：题目问 "find the stationary **values**" 时，往往既要 $x$ 也要 $f(x)$；问 "stationary **points**" 通常指坐标 $(a, f(a))$。

### 2.5 稳态 (Steady State)

#### 概念

> "When a system is in steady-state, the key variables that describe the system's behaviour do not change over time."

稳态 = 描述系统的关键变量**不随时间改变**。注意这**不代表系统里什么都没发生**——恰恰相反，稳态**要求有持续的流动通过系统 (flow through the system)**，只是流入与流出相互抵消。

> "In a chemical system, this means that even though processes are happening that could cause change, the system's variables stay the same. For this to happen, there must be a continuous flow of materials through the system."

#### 水箱模型（Figure 5.1）

一个侧壁开有出水口的容器，从上方持续注水：

- **(a) 瞬态 (transient state)**：水位还没到出水口，进水 > 出水，水位**持续上升**，体积 $V$ 随时间变化。
- **(b) 稳态 (steady state)**：水位升到出水口后，出水速率与进水速率**相等**，水位**不再变化**，$V$ 恒定。

老师原话：

> "The volume at this point is not changing, because the water going into the system is matching the water coming out of the system."

这是地球科学里极常见的模型：地下水含水层（补给 vs 排泄）、湖泊水位、大气中某种气体的浓度（源 vs 汇）、地壳热流（生热 vs 散热）都用同一套逻辑。

#### 数学判据

设系统总量为 $w$（讲义用 $w$，slides 用 $V$），其变化率由若干源 (sources) 与汇 (sinks) 决定：

$$
\frac{\mathrm{d}w}{\mathrm{d}t}=f(t,\;x_{1},\;x_{2},\dots)
$$

**稳态的定义 ⇒ 这个变化率是常数（不随时间变化）**。既然是常数，再求一次导就得零：

$$
\boxed{\;\frac{\mathrm{d}^{2}w}{\mathrm{d}t^{2}}=0\;}
$$

**本课的稳态判据（答题口径）**：

$$
\frac{\mathrm{d}(\cdot)}{\mathrm{d}(\text{time or space})}=\text{constant}
\quad\Longleftrightarrow\quad
\frac{\mathrm{d}^{2}(\cdot)}{\mathrm{d}(\cdot)^{2}}=0
\quad\Longrightarrow\quad \text{steady state}
$$

标准答题两步：**(1) 求一阶导，指出它是常数；(2) 求二阶导，得 0，据此确认稳态。** Solutions 里每一题都是这个套路（"which is constant, so the system is in steady state. Verify this by taking the second derivative… As the second derivative is zero this verifies…"）。

> ⚠️ **口径提醒**：严格的物理稳态定义是 $\partial(\cdot)/\partial t=0$（量本身不随时间变）。本课把"一阶导恒定、二阶导为零"当作稳态判据，实际描述的是**通量恒定 / 剖面线性**的稳态（steady flux / linear profile），常见于 Q5.6、Q5.7 这类空间剖面题。**考试按课程口径答**，但心里要明白两者的差别。

#### 稳态例题

**Example 5.2（讲义）：匀加速运动**
"加速度恒定"数学上写作

$$
\frac{\mathrm{d}a}{\mathrm{d}t}=0
\qquad\text{等价于}\qquad
\frac{\mathrm{d}^{2}v}{\mathrm{d}t^{2}}=0
$$

设速度 $v(t)=\alpha t$（$t$ 单位 s，$\alpha$ 是常数，单位 $\mathrm{m\,s^{-2}}$），则

$$
\frac{\mathrm{d}v}{\mathrm{d}t}=\alpha \quad(\text{常数}),\qquad
\frac{\mathrm{d}^{2}v}{\mathrm{d}t^{2}}=\frac{\mathrm{d}\alpha}{\mathrm{d}t}=0
$$

⇒ 加速度不随时间变化，系统处于稳态。

**Slides 例题：匀速行驶的汽车**（transcript 里给出了函数：$x(t)=1+68t$，单位 miles）

$$
\frac{\mathrm{d}x}{\mathrm{d}t}=68\ \text{(mph, 常数 ⇒ 速度恒定)},\qquad
\frac{\mathrm{d}^{2}x}{\mathrm{d}t^{2}}=0\ \text{(加速度为零)}
$$

⇒ 汽车处于稳态：无加速度，速度恒定，距离随时间线性增长。

> "If we take the second order derivative, then we get zero, which means that the acceleration is zero… so the velocity is constant, and if the velocity is constant, then the amount of distance we're travelling is linear."

### 2.6 求根 (Root Finding)：为什么需要数值方法

**根 (root)** = 使 $f(x)=0$ 的 $x$ 值，图像上就是函数与 $x$ 轴的交点。

老师强调：**你其实已经在求根了**——找驻点就是在解 $f'(x)=0$，那也是一次求根。

到目前为止的题都能"硬解"：
- 一次方程：直接移项；
- 二次方程：因式分解或求根公式 $x=\dfrac{-b\pm\sqrt{b^{2}-4ac}}{2a}$；
- 特殊的三次方程：能凑因式。

但考虑本周的核心反例：

$$
f(x)=2x^{2}+5-e^{x}
$$

想解 $2x^{2}+5-e^{x}=0$，即 $2x^{2}+5=e^{x}$。老师逐条否掉了各种"硬解"思路：

1. **两边取对数**：$\ln(2x^{2}+5)=x$ —— 左边 $x$ 在 log 里，右边 $x$ 在外面，**无法把 $x$ 移到一侧**。
2. **作图求交点**：分别画 $y=2x^{2}+5$ 与 $y=e^{x}$，看交点横坐标。可行但"laborious"，而且读图精度有限，复杂函数根本画不出来。
3. **暴力试值**：依次代入 $x$，微调 $\pm 0.1,\pm 0.01,\dots$ 逼近。理论可行，但极其低效且没有终止保证。

> "It's time consuming and laborious and it's a bit boring to do that."

**关键洞察**：我们手里已经有一个强大的信息源——**导数（切线斜率）**。它告诉我们函数在当前点朝哪个方向、以多快的速度变化。为什么不用切线"指路"，直接沿切线滑到 $x$ 轴上去？

> "Why can't I use that information to tell me in that direction that we're about to cross the x-axis?"

这就是牛顿法。

### 2.7 牛顿-拉夫森法 (Newton-Raphson Method)

#### 几何直觉（配 Figure 5.2）

1. 在初始猜测 $x_{0}$ 处，函数值为 $f(x_{0})$，切线斜率为 $f'(x_{0})$；
2. 沿这条**切线**一直滑到它与 $x$ 轴的交点，把这个交点记作 $x_{1}$；
3. 因为切线是曲线在该点的最佳线性近似，$x_{1}$ 通常比 $x_{0}$ **更接近真实的根**；
4. 在 $x_{1}$ 处重复步骤 1–3，得到 $x_{2}$；如此反复，$x_{n}$ 越来越靠近根。

一句话：**用切线的"直线根"去近似曲线的"曲线根"，然后不断更新。**

#### 完整推导（必须会默写）

在点 $\big(x_{0},\,f(x_{0})\big)$ 处的**切线方程**（点斜式）：

$$
y = f(x_{0}) + f'(x_{0})\,(x - x_{0})
$$

我们要找切线与 $x$ 轴的交点，所以令 $y=0$，并把此时的 $x$ 记作 $x_{1}$：

$$
0 = f(x_{0}) + f'(x_{0})\,(x_{1} - x_{0})
$$

移项：

$$
f'(x_{0})\,(x_{1} - x_{0}) = -f(x_{0})
$$

两边同除以 $f'(x_{0})$（要求 $f'(x_{0})\neq 0$）：

$$
x_{1} - x_{0} = -\frac{f(x_{0})}{f'(x_{0})}
$$

$$
\boxed{\;x_{1} = x_{0} - \frac{f(x_{0})}{f'(x_{0})}\;}
$$

把 $x_{1}$ 当作新的起点重复，得 $x_{2}=x_{1}-\dfrac{f(x_{1})}{f'(x_{1})}$，一般地：

$$
\boxed{\;x_{n+1} = x_{n} - \frac{f(x_{n})}{f'(x_{n})}\;}
$$

这就是**牛顿法的迭代公式 (iterative formula)**。它是一个**迭代算法 (iterative algorithm)**：每一步的输出是下一步的输入。

#### 使用牛顿法的标准流程

```
Step 0  把方程整理成 f(x) = 0 的形式（所有项移到一边！）
Step 1  求导数 f'(x)
Step 2  选一个初始猜测 x₀（画图 / 题目给定 / 已知根所在区间的中点）
Step 3  代入 x_{n+1} = x_n − f(x_n)/f'(x_n)，算出下一个近似值
Step 4  检查停止准则；未满足则回到 Step 3
Step 5  报告结果，注意题目要求的小数位数
```

> ⚠️ Step 0 是最容易漏的一步。Exercises5 Q5.3 明确提醒："Newton's method is used for finding the root, so you need to **move all terms to one side**."

#### 停止准则 (stopping criteria / tolerance)

牛顿法**几乎永远不会**得到精确的 $f(x)=0$，所以必须人为定义"够近了"：

| 准则类型 | 表达式 | 说明 |
|---|---|---|
| 函数值容差 (residual) | $\lvert f(x_{n})\rvert < \varepsilon$，如 $\varepsilon=0.001$ | "y 已经足够接近 0" |
| 绝对步长 (absolute change) | $\lvert x_{n+1}-x_{n}\rvert < \varepsilon$，如 $0.01$ | "x 不再明显变化" |
| 相对变化 (percentage change) | $\left\lvert\dfrac{x_{n+1}-x_{n}}{x_{n}}\right\rvert < 0.01\%$ | 对量级不同的问题更稳健 |
| 小数位稳定 | 到第 $k$ 位小数不再变化 | 本课练习最常用 |

> "This depends on the nature of the problem you are trying to solve."
> 老师明确说：**"generally in an exam setting I would tell you at what point I would want you to stop, for example at like three or four decimal places."** —— 考试会告诉你精度要求。

**实操要点**：要报到 $k$ 位小数，必须**多算一位**并确认第 $k+1$ 位也稳定了才能停。practical Solution 3 的说法："at the fourth iteration… our value only changes at an accuracy greater than 4 decimal places so we can stop"（要 3 位小数，就看第 4 位是否还在变）。

#### 收敛性 (convergence)

**好消息**：在"良性"条件下（$x_{0}$ 足够靠近一个**单根**，且该处 $f'\neq 0$，$f$ 二阶可导），牛顿法是**二次收敛 (quadratic convergence)** 的——每迭代一次，正确的有效数字数目大致**翻倍**。误差满足

$$
\varepsilon_{n+1}\;\approx\;\left\lvert\frac{f''(x_{*})}{2f'(x_{*})}\right\rvert\,\varepsilon_{n}^{2}
$$

这就是为什么本周的题目通常 3–5 次迭代就能到 6 位小数（看 Q5.3 的误差列：$1.9\times10^{-1}\to3.4\times10^{-2}\to1.0\times10^{-3}\to8.6\times10^{-7}$，指数几乎是平方式下降）。

**坏消息（讲义原文警告）**：

> "There is **no guarantee** this method will converge to a root. Indeed there are cases where each iteration will get **worse and worse**."

#### 什么时候会失败？（重要考点）

| 失败模式 | 原因 | 表现 / 对策 |
|---|---|---|
| **导数为零** $f'(x_{n})=0$ | 切线水平，与 $x$ 轴平行，永不相交 | 迭代公式分母为 0，算法崩溃。换初值 |
| **接近驻点** $f'(x_{n})\approx 0$ | 切线几乎水平 | $x_{n+1}$ 被"甩"到极远处，可能跑到另一个根的吸引域甚至发散 |
| **发散 (divergence)** | 初值太差 / 函数形状不利 | $\lvert x_{n}\rvert$ 越来越大。Solutions5 Q5.5 原话："You may even find your value **grows**!" |
| **循环 (cycling / oscillation)** | 迭代在两点间来回跳 | 例如 $f(x)=x^{3}-2x+2$，$x_{0}=0$：$0\to1\to0\to1\to\cdots$ 永不收敛 |
| **收敛到"错误"的根** | 多根函数，初值落在别的**吸引域 (basin of attraction)** 里 | 得到的是根，但不是你想要的那个（见 Q5.5） |
| **重根 (repeated root)** | $f'(x_{*})=0$ 且 $f(x_{*})=0$ | 收敛退化为**线性**，慢很多 |
| **无实根** | 函数根本不与 $x$ 轴相交 | 永远不会满足停止准则；必须设最大迭代次数 |

#### 初值 $x_{0}$ 怎么选？

讲义特别强调："To arrive at the value for $x$ at the root, we need an initial guess. **This can be important.**"

选初值的实用办法：
1. **画图**（Q5.5 就直接给了 Figure 5.3），目测根在哪，取附近的整数或半整数；
2. **题目给出区间**（如"根在 $x=3$ 与 $x=4$ 之间"）⇒ 取中点 $3.5$；
3. **变号法 (sign change)**：找到 $f(a)$ 与 $f(b)$ 异号的一对点，根必在 $(a,b)$ 内（介值定理）；
4. **物理意义约束**：如天数、单位数不能为负（Week 4 金矿题里丢掉 $n=-11$ 就是这个道理）；
5. **多个根 ⇒ 每个根都要单独选一个初值**，并逐一验算。

---

## 三、公式与图表

### 3.1 本周公式总表

| # | 名称 | 公式 |
|---|---|---|
| 1 | 二阶导数定义 | $f''(x)=\dfrac{\mathrm{d}}{\mathrm{d}x}\!\left(\dfrac{\mathrm{d}f}{\mathrm{d}x}\right)=\dfrac{\mathrm{d}^{2}f}{\mathrm{d}x^{2}}$ |
| 2 | 位移-速度-加速度 | $x=f(t)$, $v=f'(t)$, $a=f''(t)$ |
| 3 | 二阶导数判别法 | $f'(a)=0$ 且 $f''(a)<0\Rightarrow$ max；$f''(a)>0\Rightarrow$ min；$f''(a)=0\Rightarrow$ 不定 |
| 4 | 稳态判据 | $\dfrac{\mathrm{d}w}{\mathrm{d}t}=\text{const}\;\Longleftrightarrow\;\dfrac{\mathrm{d}^{2}w}{\mathrm{d}t^{2}}=0$ |
| 5 | 切线方程 | $y=f(x_{0})+f'(x_{0})(x-x_{0})$ |
| 6 | **牛顿-拉夫森迭代式** | $x_{n+1}=x_{n}-\dfrac{f(x_{n})}{f'(x_{n})}$ |
| 7 | 二次收敛估计 | $\varepsilon_{n+1}\approx\left\lvert\dfrac{f''}{2f'}\right\rvert\varepsilon_{n}^{2}$ |
| 8 | 二次求根公式（校验用） | $x=\dfrac{-b\pm\sqrt{b^{2}-4ac}}{2a}$ |

### 3.2 求导法则速查表（practical slides 提供，本周必须信手拈来）

| 函数 $y=f(x)$ | 导数 $\dfrac{\mathrm{d}y}{\mathrm{d}x}$ |
|---|---|
| constant | $0$ |
| $x$ | $1$ |
| $x^{n}$ | $nx^{n-1}$ |
| $e^{x}$ | $e^{x}$ |
| $e^{kx}$ | $ke^{kx}$ |
| $e^{f(x)}$ | $\dfrac{\mathrm{d}f}{\mathrm{d}x}e^{f(x)}$ |
| $\ln(x)$ | $\dfrac{1}{x}$ |
| $\sin(x)$ | $\cos(x)$ |
| $\cos(x)$ | $-\sin(x)$ |

配套的组合法则（Week 3 学过，本周求二阶导时反复用到）：

- **乘积法则 (product rule)**：$(uv)'=u'v+uv'$
- **商法则 (quotient rule)**：$\left(\dfrac{u}{v}\right)'=\dfrac{u'v-uv'}{v^{2}}$
- **链式法则 (chain rule)**：$\dfrac{\mathrm{d}y}{\mathrm{d}x}=\dfrac{\mathrm{d}y}{\mathrm{d}u}\cdot\dfrac{\mathrm{d}u}{\mathrm{d}x}$

### 3.3 图表判读

**Figure 4.2（沿用自 Week 4）— 三次函数及其导数（双面板图）**
- 上图：$f(x)=\dfrac{x^{3}}{3}+2x^{2}-5x+1$，范围 $-10<x<5$；
- 下图：$f'(x)=x^{2}+4x-5$；
- 判读要点：$f'>0$ 的区间 ⟺ 上图上升；$f'<0$ ⟺ 上图下降；$f'$ **穿过 0 的位置**（$x=-5$、$x=1$）⟺ 上图的**转折点**（灰色竖线标出）。
- $f'$ 由正变负 ⇒ 极大（$x=-5$）；由负变正 ⇒ 极小（$x=1$）。
- 本周新增的一层：$f''(-5)=-6<0$、$f''(1)=6>0$，用代数**确认**了肉眼所见。

**Figure 5.1 — 稳态示意图**
- (a) **transient state（瞬态）**：进水口在上，出水口在侧壁；水位低于出水口，水位随时间上升。$\mathrm{d}V/\mathrm{d}t>0$。
- (b) **steady state（稳态）**：水位达到出水口高度，进水量 = 出水量，水位不再变化。$\mathrm{d}V/\mathrm{d}t=\text{const}$（这里是 0），$\mathrm{d}^{2}V/\mathrm{d}t^{2}=0$。
- 判读要点：**稳态 ≠ 静止**。水一直在流，只是"存量"不变。

**Figure 5.2 — 牛顿法几何示意（来源：Paul's Online Notes, lamar.edu）**
- 一条非线性上升曲线 $y=f(x)$，在 $x=0$ 附近 $y<0$，随 $x$ 增大穿过 $x$ 轴。
- 图上画出了 $x_{0}$、$x_{1}$、$x_{2}$ 三点处的**切线**。
- 判读要点：从 $x_{0}$ 垂直向上（或向下）到曲线，画切线，切线与 $x$ 轴交于 $x_{1}$；三角形的直角边分别是 $f(x_{0})$（竖直）和 $x_{0}-x_{1}$（水平），斜率 $f'(x_{0})=\dfrac{f(x_{0})}{x_{0}-x_{1}}$，直接给出 $x_{1}=x_{0}-\dfrac{f(x_{0})}{f'(x_{0})}$。
- 一眼看出：切线越陡（$\lvert f'\rvert$ 越大），步长 $\lvert x_{n+1}-x_{n}\rvert$ 越小、越稳；切线越平，跳得越远、越危险。

**Figure 5.3 — Q5.5 用的三次函数图**
- 图像显示曲线**三次穿过 $x$ 轴**：一个在 $x\approx-3.5$、一个在 $x\approx 0$、一个在 $x\approx 4.4$。
- 判读用途：**为每个根挑初值**。题干只给了 $x_{0}=-3.5$ 和 $x_{0}=4.5$（左右两根），中间那个根要自己看图补上 $x_{0}=0$。
- 这张图是"为什么要先画图再用牛顿法"的最佳教材：不看图就会漏根。

---

## 四、课堂补充（transcript 独有内容）

以下是录音转写里有、而讲义/幻灯片上没有或没说透的内容。

### 4.1 老师的"元方法论"：数学就是转轮子

反复出现的一句话：

> "Maths is always something about hand churning, trying to understand the processes that are involved."
> "Most of maths, a lot of maths is churning the wheel and trying to get something out at the end and just learning the process of this."

含义：本周的两个核心技能（二阶导数判别、牛顿迭代）都是**固定流程**，考试考的是能不能一步不漏地照着走完，而不是灵光一现。**把流程背成肌肉记忆**。

### 4.2 关于二阶导数用途的两次强调

老师两次澄清"我不是让你为了求导而求导"：

> "I'm not asking you to find the differentiated function for the sake of it, I'm actually asking you to do it because there's some interesting properties here."
> "Again, we're not just calculating the second order derivative for a test or anything, we actually have some meaningful physical interpretation."

### 4.3 关于二阶 ODE 的前瞻

老师把二阶导数与后续课程连了起来（讲义上只是一笔带过）：

> "What we're going to be doing later in the course is looking at to solve differential equations of this sort… where we look at something of a second order derivative plus the first order derivative plus an original function."

并明确指出**放射性衰变方程 $\mathrm{d}N/\mathrm{d}t=-\lambda N$ 就是这类方程在二阶项系数为零时的特例**（把 $-\lambda N$ 移到左边即得 $\frac{\mathrm{d}N}{\mathrm{d}t}+\lambda N=0$）。这条线索在 Week 9 会被正式接上。

### 4.4 老师亲口承认"反直觉"

> "Now it seems slightly counterintuitive that negative equals maximum, positive equals minimum, but it does cross over. It's slightly counterintuitive, but I'm hoping that you start to see that we now have a **formal test** for this."

并预告了 $f''=0$ 的情形："what you'll see is an example of where $x=0$, and you'll have to start encountering saddle points, and you have to start reverting back to what we learned last week." —— 指的就是 Exercises Q5.2(b) 的 $f(x)=x^{3}$。

### 4.5 稳态那一段老师讲混了（重要，避免被转写误导）

转写里这一段有明显混乱：老师先起了一个"高速公路旁污染物随距离衰减"的例子，讲到一半发现幻灯片上的函数 $x(t)=1+68t$ 其实是"汽车行驶距离"的例子，于是中途自己叫停：

> "I'm missing a bit of context here for some reason…"
> "and the, change this example, I'm getting very confused, right, let me start this again."
> "sorry, there was a bit confusion there, I got a bit confused, there was another example in here that didn't relate to some of the earlier slides."

**最终确认的版本是汽车例子**：$x(t)=1+68t$（距离，miles）⇒ $\mathrm{d}x/\mathrm{d}t=68$（常数速度）⇒ $\mathrm{d}^{2}x/\mathrm{d}t^{2}=0$（零加速度）⇒ 稳态。

**污染物那个例子并没有丢**——它其实就是 practical Exercise 2 / Exercises Q5.6 的焚烧炉浓度题，数学结构完全一样（线性函数 ⇒ 一阶导恒定 ⇒ 二阶导为零）。所以两个说法都对，只是幻灯片上放的是汽车版。

老师随后总结了稳态的实用价值：

> "You can start looking at systems and looking at where the second order derivative would be zero, and that will tell you at what points… that a process is in steady state."
> "This will become really useful later on… when we try to solve something called **initial value problems** or **boundary condition problems**."

### 4.6 老师详细解释了为什么 $2x^{2}+5=e^{x}$ 解不出来

这一段幻灯片上没有，只有口头讲解：

> "If you took $\ln(2x+5)$ is equal to $x$, it becomes a really really difficult thing to solve because **you can't get $x$ on one side and a number on the other**."

并列举了所有"笨办法"：作图找交点、迭代试值 $\pm0.1,\pm0.01$、用近似式——结论是 "sometimes it's actually not worth all of that time and attention"。

### 4.7 老师承认自己把牛顿法的推导讲砸了

> "So this is Newton's method and I completely messed that explanation up today but I'm really sorry, we'll see plenty of practical examples of this today."
> （中途还有："I'm getting confused now, my brain's not working" / "just my brain's not working, it's not completely failing me"）

**这意味着**：转写里牛顿法推导的那一大段（$y=f(x_0)+f'(x_0)(x_1-x_0)$ 的建立过程）读起来断断续续、符号混乱，**不要照抄转写**。以讲义 §5.3 和上面 §2.7 的干净推导为准。老师把补课交给了 practical（Exercise 3）。

### 4.8 考试相关的口头提示

> "Generally in an exam setting I would tell you at what point I would want you to stop, for example at like three or four decimal places."

⇒ 考试会明确给出精度要求，不必自己纠结容差取多少。

### 4.9 与 Week 4 金矿题的衔接（课堂复习部分）

老师用了不少时间回顾 Week 4 的优化实例：净利润

$$
P(n)=G(n)-C(n)=100-\frac{100}{n+1}-n
$$

$$
\frac{\mathrm{d}P}{\mathrm{d}n}=\frac{100}{(n+1)^{2}}-1=0
\;\Longrightarrow\;(n+1)^{2}=100\;\Longrightarrow\;n+1=\pm10\;\Longrightarrow\;n=9\ \text{或}\ n=-11
$$

丢弃 $n=-11$（不能有负天数），$n=9$ 天时净利润最大 ⇒ 第 9 天应停止开采。
老师当场点出：Week 4 只是"看图说话"确认它是极大值，"we could/should check this" —— 本周的二阶导数判别法正是这个"check"。（练习：$\dfrac{\mathrm{d}^{2}P}{\mathrm{d}n^{2}}=-\dfrac{200}{(n+1)^{3}}$，在 $n=9$ 处为 $-200/1000=-0.2<0$ ⇒ 确认极大。）

### 4.10 行政通知

> "Next week we move over to **Booth Street East**, we don't use this lecture hall anymore, so please for the next four weeks we move over to Booth Street East."

（Week 6–9 换教室。）

---

## 五、Practical 要点

### 5.0 Practical 的目的

本周 practical 分两层：

- **`practical5_soln(1).md`（课堂 practical 幻灯片，3 道题）**：老师带着做的入门题，尤其是 Exercise 3 用来**补上**课堂上没讲完的牛顿法完整迭代过程（老师说 "we'll see plenty of practical examples of this today"）。
- **`Exercises5.md` / `Solutions5.md`（周作业，Q5.1–Q5.8）**：正式练习。前 5 题是代数题 (algebraic problems)，后 3 题是真实世界应用 (real-world problems)。

> ⚠️ **题号一律以周版文件 `Exercises5.md` 为准**。主手册里的交叉引用（如 "from Chapter 3 Question 5.4(a)"）是转档后的编号错乱，不可信。

---

### 5.1 课堂 Practical Exercise 1：二阶导数分类驻点

**题目**：上次 practical 中我们对

$$
f(x)=\frac{x^{3}}{3}+x^{2}-15x+1
$$

求出了驻点 $x=-5$ 与 $x=3$。请用二阶导数确认它们是极大、极小还是鞍点。

**解**：

一阶导数：

$$
\frac{\mathrm{d}y}{\mathrm{d}x}=x^{2}+2x-15
$$

（验算驻点：$x^{2}+2x-15=(x+5)(x-3)=0\Rightarrow x=-5,\;x=3$ ✓）

二阶导数：

$$
\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}=2x+2
$$

代入驻点：

$$
\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}(3)=2\times 3+2=8>0
\quad\Longrightarrow\quad x=3 \text{ 是极小值 (minimum)}
$$

$$
\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}(-5)=2\times(-5)+2=-8<0
\quad\Longrightarrow\quad x=-5 \text{ 是极大值 (maximum)}
$$

---

### 5.2 课堂 Practical Exercise 2：稳态（焚烧炉污染物）

**题目**：某工业焚烧炉稳定排放颗粒物，烟囱处浓度 $C_{0}=1\ \mathrm{mg\,m^{-3}}$，1 km 外浓度 $C_{1}=0.11\ \mathrm{mg\,m^{-3}}$。浓度随距离的函数为

$$
C(x)=C_{0}+\frac{(C_{1}-C_{0})}{1000}x
$$

该系统是否处于稳态？

**解**：

求一阶导数（$C_{0}$、$C_{1}$ 都是常数）：

$$
\frac{\mathrm{d}C}{\mathrm{d}x}=\frac{C_{1}-C_{0}}{1000}=\frac{0.11-1}{1000}=-8.9\times10^{-4}\ \mathrm{mg\,m^{-3}\,m^{-1}}
$$

这是一个**常数**（不随 $x$ 变化），因此二阶导数为零：

$$
\frac{\mathrm{d}^{2}C}{\mathrm{d}x^{2}}=0
$$

**⇒ 系统处于稳态 (steady state)。**

**物理解读**：浓度随距离**线性**下降，稀释速率处处相同，说明污染物通量恒定——排放源稳定输出，大气稀释过程稳定，系统达到平衡。

---

### 5.3 课堂 Practical Exercise 3：牛顿法完整迭代（核心示范题）

**题目**：用牛顿法求

$$
f(x)=x^{2}+2x-10
$$

的一个根。初值 $x_{0}=4$，结果精确到 3 位小数（即第 4 位小数不再变化）。

**解**：

导数：

$$
f'(x)=2x+2
$$

迭代式：

$$
x_{n+1}=x_{n}-\frac{x_{n}^{2}+2x_{n}-10}{2x_{n}+2}
$$

**逐次迭代表**：

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}=x_{n}-\dfrac{f}{f'}$ | 步长 $\lvert\Delta x\rvert$ |
|---|---|---|---|---|---|
| 0 | 4.000000 | 14.000000 | 10.000000 | 2.600000 | $1.4\times10^{0}$ |
| 1 | 2.600000 | 1.960000 | 7.200000 | 2.327778 | $2.7\times10^{-1}$ |
| 2 | 2.327778 | 0.074105 | 6.655556 | 2.316643 | $1.1\times10^{-2}$ |
| 3 | 2.316643 | 0.000124 | 6.633287 | 2.316625 | $1.9\times10^{-5}$ |
| 4 | 2.316625 | $\approx 0$ | 6.633250 | 2.316625 | $5\times10^{-11}$ |

到第 4 次迭代（$x_{4}$）时，数值只在 4 位小数以外变化，**可以停止**。

$$
\text{根}\;\approx\;2.31662
$$

**验证（本题的精髓）**：这题其实是二次方程，可以用求根公式检验：

$$
x=\frac{-2\pm\sqrt{2^{2}-4(1)(-10)}}{2(1)}=\frac{-2\pm\sqrt{44}}{2}=-1\pm\sqrt{11}
$$

$$
\sqrt{11}=3.31662\ldots\;\Longrightarrow\; x=2.31662 \ \text{或}\ x=-4.31662
$$

**牛顿法找到的根完全正确！** 这道题的设计意图就是：**先在一个能解析验证的例子上建立对牛顿法的信任**，再拿去解那些解不出来的方程。

**另一个教学点**：本题有**两个根**，$x_{0}=4$ 只收敛到其中一个（正根）。若想找 $-4.31662$，必须从负的初值出发（如 $x_{0}=-4$）。这就是**吸引域**的直观演示。

---

### 5.4 周作业 Q5.1：求二阶导数

> 题干提示："we have seen two of these formulas when we practised using the product and quotient rule" —— (a) 和 (c) 是 Week 3 做过的。

#### (a) $y=\sqrt{x^{2}+25}=(x^{2}+25)^{1/2}$

**一阶导（链式法则）**：令 $u=x^{2}+25$，$y=u^{1/2}$。

$$
\frac{\mathrm{d}y}{\mathrm{d}u}=\frac{1}{2}u^{-1/2},\qquad \frac{\mathrm{d}u}{\mathrm{d}x}=2x
$$

$$
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{1}{2}(x^{2}+25)^{-1/2}\cdot 2x=\frac{x}{\sqrt{x^{2}+25}}
$$

**二阶导（商法则）**：设 $u=x$，$v=\sqrt{x^{2}+25}$，则 $u'=1$，$v'=\dfrac{x}{\sqrt{x^{2}+25}}$（就是上面的结果）。

$$
\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}
=\frac{u'v-uv'}{v^{2}}
=\frac{\sqrt{x^{2}+25}\cdot 1-x\cdot\dfrac{x}{\sqrt{x^{2}+25}}}{\left(\sqrt{x^{2}+25}\right)^{2}}
$$

分子通分：

$$
=\frac{\dfrac{(x^{2}+25)-x^{2}}{\sqrt{x^{2}+25}}}{x^{2}+25}
=\frac{25}{(x^{2}+25)^{3/2}}
$$

$$
\boxed{\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}=\frac{25}{(x^{2}+25)^{3/2}}}
$$

（顺带一提：这个结果恒为正，说明 $\sqrt{x^{2}+25}$ 处处下凹 $\cup$，其唯一驻点 $x=0$ 是极小值 $y=5$。）

#### (b) $y=\dfrac{x^{5}}{4}+x^{3}+12$

纯幂函数，逐项用 $x^{n}\to nx^{n-1}$：

$$
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{5x^{4}}{4}+3x^{2}
$$

$$
\boxed{\frac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}=\frac{20x^{3}}{4}+6x=5x^{3}+6x}
$$

#### (c) $f(x)=x\exp(x)$

**一阶导（乘积法则）**：$u=x$、$v=e^{x}$，$u'=1$、$v'=e^{x}$。

$$
f'(x)=u'v+uv'=e^{x}+x e^{x}
$$

**二阶导**：对 $f'(x)=e^{x}+xe^{x}$ 再求导。
- 第一项 $e^{x}$ 求导仍是 $e^{x}$（指数函数法则）；
- 第二项 $xe^{x}$ **就是原函数本身**，其导数已经算过，是 $e^{x}+xe^{x}$（Solutions 里说的 "this term is the same structure as the original function, allowing us to substitute it back"）。

$$
f''(x)=e^{x}+\left(e^{x}+xe^{x}\right)=2e^{x}+xe^{x}
$$

$$
\boxed{f''(x)=(x+2)e^{x}}
$$

（可推广：$f^{(n)}(x)=(x+n)e^{x}$。）

#### (d) $P(z)=P_{0}\exp\!\left(-\dfrac{g}{R_{a}T}z\right)$ —— 静水压方程 (hydrostatic equation)

$P_{0}$、$g$、$R_{a}$、$T$ 均为常数。用 $\dfrac{\mathrm{d}}{\mathrm{d}z}e^{kz}=ke^{kz}$，其中 $k=-\dfrac{g}{R_{a}T}$：

$$
\frac{\mathrm{d}P}{\mathrm{d}z}=-\frac{g}{R_{a}T}\,P_{0}\exp\!\left(-\frac{g}{R_{a}T}z\right)
$$

再求一次：

$$
\frac{\mathrm{d}^{2}P}{\mathrm{d}z^{2}}=\left(-\frac{g}{R_{a}T}\right)^{2}P_{0}\exp\!\left(-\frac{g}{R_{a}T}z\right)
=\boxed{\left(\frac{g}{R_{a}T}\right)^{2}P_{0}\exp\!\left(-\frac{g}{R_{a}T}z\right)}
$$

**Solutions 给的漂亮做法（务必掌握）**：注意到

$$
\frac{\mathrm{d}P}{\mathrm{d}z}=-\frac{g}{R_{a}T}\,P(z)
$$

即导数正比于函数本身，所以

$$
\frac{\mathrm{d}^{2}P}{\mathrm{d}z^{2}}=-\frac{g}{R_{a}T}\cdot\frac{\mathrm{d}P}{\mathrm{d}z}=\left(\frac{g}{R_{a}T}\right)^{2}P(z)
$$

**物理意义**：大气压随高度**指数**衰减。一阶导为负（越高压强越低），二阶导为正（衰减在减速——高空的压强下降没有低空那么陡）。这与 Q5.6/Q5.7 的**线性**剖面形成对照：指数剖面的二阶导 $\neq 0$，**不是**本课意义上的稳态。

---

### 5.5 周作业 Q5.2：找驻点并分类

#### (a) $f(x)=\dfrac{x^{3}}{3}+\dfrac{x^{2}}{2}-30x+5$

**一阶导**：

$$
f'(x)=x^{2}+x-30
$$

**令 $f'(x)=0$**：

$$
x^{2}+x-30=(x+6)(x-5)=0\;\Longrightarrow\; x=-6,\quad x=5
$$

**二阶导**：

$$
f''(x)=2x+1
$$

**分类**：

$$
f''(-6)=2(-6)+1=-11<0\;\Longrightarrow\; x=-6 \text{ 是极大值 (maximum)}
$$

$$
f''(5)=2(5)+1=11>0\;\Longrightarrow\; x=5 \text{ 是极小值 (minimum)}
$$

> ⚠️ `Solutions5.md` 此处有**笔误**："two stationary values at $x=-6$ and $x=-5$"，随后又写 "so $x=-6$ is a maximum and $x=5$ is a minimum"。正确的是 $x=-6$ 和 $x=+5$（因式分解 $(x+6)(x-5)$ 一眼可验）。

#### (b) $f(x)=x^{3}$

**一阶导**：$f'(x)=3x^{2}$。

**令 $f'(x)=0$**：$3x^{2}=0\Rightarrow x=0$（唯一驻点）。

**二阶导**：$f''(x)=6x$，故

$$
f''(0)=0
$$

**⇒ 二阶导数判别法失效，无法分类！**

**退回一阶导数法**（Week 4 的方法）：$f'(x)=3x^{2}$ 恒 $\geq 0$，
- 当 $x<0$：$f'(x)>0$ ⇒ $f$ **递增**；
- 当 $x>0$：$f'(x)>0$ ⇒ $f$ **仍在递增**。

函数在 $x=0$ 两侧都在增，**没有换向**。

$$
\boxed{x=0 \text{ 是鞍点 / 拐点 (saddle point / point of inflection)}}
$$

**这是本周最重要的一道概念题**——老师在课上专门预告过它。它演示了判别法的边界：$f''=0$ 时必须动用别的手段。

---

### 5.6 周作业 Q5.3（＝讲义 Example 5.3）：牛顿法求根到 6 位小数

**题目**：用牛顿法求

$$
f(x)=2x^{2}+5-e^{x}
$$

的根，精确到 6 位小数。已知根在 $x=3$ 与 $x=4$ 之间，初值 $x_{0}=3.5$。

> ⚠️ `Solutions5.md` / 主手册在这里写成 "assuming it is between $x=4$ and $x=6$"，与题干的 "between $x=3$ and $x=4$" 矛盾。以**题干**为准（初值 3.5 落在 $[3,4]$ 内，答案 3.275601 也在 $[3,4]$ 内）。

**Step 0**：方程已经是 $f(x)=0$ 的形式。若题目给的是 $2x^{2}+5=e^{x}$，**必须先把所有项移到一边**。

**Step 1 — 求导**：

$$
f'(x)=4x-e^{x}
$$

**Step 2 — 迭代式**：

$$
x_{n+1}=x_{n}-\frac{2x_{n}^{2}+5-e^{x_{n}}}{4x_{n}-e^{x_{n}}}
$$

**逐次迭代表**：

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}$ | 步长 $\lvert\Delta x\rvert$ |
|---|---|---|---|---|---|
| 0 | 3.500000 | $-3.615452$ | $-19.115452$ | 3.310862 | $1.9\times10^{-1}$ |
| 1 | 3.310862 | $-0.485132$ | $-14.165301$ | 3.276614 | $3.4\times10^{-2}$ |
| 2 | 3.276614 | $-0.013546$ | $-13.379493$ | 3.275602 | $1.0\times10^{-3}$ |
| 3 | 3.275602 | $-0.0000115$ | $-13.356740$ | 3.275601 | $8.6\times10^{-7}$ |
| 4 | 3.275601 | $\approx 0$ | $-13.356721$ | 3.275601 | $<10^{-12}$ |

$$
\boxed{\text{根} = 3.275601\ \text{(6 d.p.)}}
$$

**第一步的手算细节**（课上给的数）：

$$
f(3.5)=2(3.5)^{2}+5-e^{3.5}=24.5+5-33.11545=-3.61545
$$

$$
f'(3.5)=4(3.5)-e^{3.5}=14-33.11545=-19.11545
$$

$$
x_{1}=3.5-\frac{-3.61545}{-19.11545}=3.5-0.18914=3.31086
$$

> 📌 幻灯片上写的是 $x_{1}=3.5-\dfrac{3.6154}{19.1154}=3.3109$——**两个负号都被省略了**，但比值不变，结果正确。手算时**保留符号**更安全，尤其在多根问题里符号会决定往哪边走。

**收敛观察**：步长 $1.9\times10^{-1}\to3.4\times10^{-2}\to1.0\times10^{-3}\to8.6\times10^{-7}$，指数大致翻倍——教科书式的**二次收敛**。

---

### 5.7 周作业 Q5.4：求第二次迭代值 $x_{2}$

统一做法：求 $f'$ → 从 $x_{0}$ 迭代**两次** → 报告 $x_{2}$。

#### (a) $f(x)=x^{3}-7x^{2}+8x-3$，$x_{0}=5$

$$
f'(x)=3x^{2}-14x+8
$$

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}$ |
|---|---|---|---|---|
| 0 | 5 | $125-175+40-3=-13$ | $75-70+8=13$ | $5-\dfrac{-13}{13}=6$ |
| 1 | 6 | $216-252+48-3=9$ | $108-84+8=32$ | $6-\dfrac{9}{32}=5.71875$ |

$$
\boxed{x_{2}=5.71875}
$$

（这题数字全是整数，**适合手算，考试常考类型**。若继续迭代：$x_{3}=5.686202$，$x_{4}=5.685780$，真根 $\approx 5.685780$。注意第一步 $x_{0}=5\to x_{1}=6$ 是**跳过了**真根又跳回来——牛顿法不保证单调逼近。）

#### (b) $f(x)=\sin(x)-\ln(x)$，$x_{0}=2$

$$
f'(x)=\cos(x)-\frac{1}{x}
$$

（$x$ 必须用**弧度 (radians)**！）

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}$ |
|---|---|---|---|---|
| 0 | 2.000000 | $0.909297-0.693147=0.216150$ | $-0.416147-0.5=-0.916147$ | 2.235934 |
| 1 | 2.235934 | $-0.017827$ | $-1.064408$ | 2.219186 |

$$
\boxed{x_{2}=2.219185\ (\text{取到 6 d.p.})}
$$

（继续迭代得真根 $\approx 2.219107$。）

#### (c) $f(x)=x\cos(x)-x^{2}$，$x_{0}=1$

**先求导**，其中 $h(x)=x\cos(x)$ 用**乘积法则**：$u=x$、$v=\cos x$，$u'=1$、$v'=-\sin x$：

$$
h'(x)=\cos(x)-x\sin(x)
$$

$$
f'(x)=\cos(x)-x\sin(x)-2x
$$

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}$ |
|---|---|---|---|---|
| 0 | 1.000000 | $0.540302-1=-0.459698$ | $0.540302-0.841471-2=-2.301169$ | 0.800233 |
| 1 | 0.800233 | $-0.082979$ | $-1.478108$ | 0.744094 |

$$
\boxed{x_{2}=0.744094}
$$

（继续迭代得真根 $\approx 0.739085$——恰好是著名的 **Dottie number**，即 $\cos x=x$ 的解，因为 $x\cos x-x^{2}=x(\cos x-x)$，非零根即 $\cos x = x$。）

---

### 5.8 周作业 Q5.5：找**全部**根（多根问题，最考验理解）

**题目**：用牛顿法求

$$
f(x)=x^{3}-x^{2}-15x+1
$$

的**所有**根，精确到 3 位小数。题目给了 $x_{0}=-3.5$（左根）与 $x_{0}=4.5$（右根），并提供 Figure 5.3。

> 📎 说明：原 md 中该函数是图片，此处的表达式由三个已知根 $-3.442,\,0.066,\,4.376$ **反推**并数值验证（韦达定理：和 $=1$、两两积之和 $=-15$、积 $=-1$，与 $x^{3}-x^{2}-15x+1$ 完全吻合；三个初值的迭代结果也精确复现了标准答案）。

**关键洞察（Solutions 明确指出）**：图上有**三个**交点，但题目只给了两个初值。**必须自己补上第三个初值** $x_{0}=0$ 去抓中间那个根。

> "Since we have 3 roots (according to what we can see), it makes sense to select values near these points. We have been given $x_0=-3.5$ and $x_0=4.5$ as starting values but **there is also a root near zero so let's also use $x_0=0$**."

**导数**：

$$
f'(x)=3x^{2}-2x-15
$$

**迭代式**：

$$
x_{n+1}=x_{n}-\frac{x_{n}^{3}-x_{n}^{2}-15x_{n}+1}{3x_{n}^{2}-2x_{n}-15}
$$

**根 ①：$x_{0}=-3.5$**

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}$ |
|---|---|---|---|---|
| 0 | $-3.500000$ | $-1.625000$ | 28.750000 | $-3.443478$ |
| 1 | $-3.443478$ | $-0.036559$ | 27.459584 | $-3.442147$ |
| 2 | $-3.442147$ | $-0.0000201$ | 27.429420 | $-3.442146$ |

$$
\Rightarrow\ x\approx -3.442
$$

**根 ②：$x_{0}=0$（自己补的初值）**

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}$ |
|---|---|---|---|---|
| 0 | 0.000000 | 1.000000 | $-15.000000$ | 0.066667 |
| 1 | 0.066667 | $-0.004148$ | $-15.120000$ | 0.066392 |
| 2 | 0.066392 | $\approx 0$ | $-15.119561$ | 0.066392 |

$$
\Rightarrow\ x\approx 0.066
$$

**根 ③：$x_{0}=4.5$**

| $n$ | $x_{n}$ | $f(x_{n})$ | $f'(x_{n})$ | $x_{n+1}$ |
|---|---|---|---|---|
| 0 | 4.500000 | 4.375000 | 36.750000 | 4.380952 |
| 1 | 4.380952 | 0.175467 | 33.816327 | 4.375764 |
| 2 | 4.375764 | 0.000327 | 33.690393 | 4.375754 |

$$
\Rightarrow\ x\approx 4.376
$$

$$
\boxed{\text{三个根：}-3.442,\quad 0.066,\quad 4.376}
$$

**Solutions 的重要警告（必背）**：

> "Please note that the following solution is **dependent on the starting guess** so your results may change. **You may even find your value grows!** So **care is needed when there are multiple roots**."

这句话包含三层意思：
1. 不同初值可能收敛到**不同的根**（吸引域问题）；
2. 有些初值会让数值**发散**（"grows"）——本题中若初值落在 $f'(x)=0$ 附近（$3x^{2}-2x-15=0\Rightarrow x\approx -1.907,\;2.573$），切线近乎水平，$x_{1}$ 会被甩得极远；
3. **多根问题必须先画图**，逐根设初值，逐根验证。

---

### 5.9 周作业 Q5.6：焚烧炉排放的稳态（真实世界题）

**题目**：焚烧炉稳定排放颗粒物，烟囱处 $C_{0}=1.0\ \mathrm{mg\,m^{-3}}$，1 km 外 $C_{1\mathrm{km}}=0.1\ \mathrm{mg\,m^{-3}}$。有些住宅距工厂 500 m。浓度随距离的表达式为

$$
C(x)=C_{0}+\frac{(C_{1\mathrm{km}}-C_{0})}{1000}\,x
$$

证明通量处于稳态。

**解**：

**Step 1 — 一阶导数**：

$$
\frac{\mathrm{d}C}{\mathrm{d}x}=\frac{C_{1\mathrm{km}}-C_{0}}{1000}=\frac{0.1-1.0}{1000}=-9\times10^{-4}\ \mathrm{mg\,m^{-3}\,m^{-1}}
$$

这是**常数**（不含 $x$）⇒ 浓度以恒定速率随距离下降 ⇒ 通量恒定 ⇒ 稳态。

**Step 2 — 二阶导数验证**：

$$
\frac{\mathrm{d}^{2}C}{\mathrm{d}x^{2}}=0
$$

**⇒ 二阶导为零，确认通量处于稳态。** ∎

**附带信息的用途**（题干提到 500 m 处的住宅）：

$$
C(500)=1.0+(-9\times10^{-4})(500)=1.0-0.45=0.55\ \mathrm{mg\,m^{-3}}
$$

住宅处浓度为 $0.55\ \mathrm{mg\,m^{-3}}$（这是这类环境评估题的典型后续问法）。

> 注意：课堂 practical 版本用的是 $C_{1}=0.11\ \mathrm{mg\,m^{-3}}$，斜率 $-8.9\times10^{-4}$；周作业版本用 $0.1$，斜率 $-9\times10^{-4}$。**数字不同但方法完全一样**，不要被搞混。

---

### 5.10 周作业 Q5.7：地热剖面的稳态（真实世界题）

**题目**：地下 3 km 处有一个热花岗岩床，温度 $250^{\circ}\mathrm{C}$；近地表温度基本恒定在 $10^{\circ}\mathrm{C}$。用一维**傅里叶定律 (Fourier's law)** 构建了温度随深度的表达式。该系统是否处于稳态？

**解**：

线性温度剖面（与 Q5.6 结构相同）：

$$
T(z)=T_{0}+\frac{(T_{3\mathrm{km}}-T_{0})}{3000}\,z
=10+\frac{250-10}{3000}\,z
=10+0.08\,z\qquad(z \text{ 单位 m})
$$

**Step 1 — 一阶导数（地温梯度 geothermal gradient）**：

$$
\frac{\mathrm{d}T}{\mathrm{d}z}=\frac{240}{3000}=0.08\ ^{\circ}\mathrm{C\,m^{-1}}=80\ ^{\circ}\mathrm{C\,km^{-1}}
$$

常数 ⇒ 系统处于稳态。

**Step 2 — 二阶导数验证**：

$$
\frac{\mathrm{d}^{2}T}{\mathrm{d}z^{2}}=0
$$

**⇒ 确认稳态。** ∎

**物理意义**：一维傅里叶定律 $q=-k\dfrac{\mathrm{d}T}{\mathrm{d}z}$ 告诉我们**热流 (heat flux) 正比于温度梯度**。梯度恒定 ⇒ 热流处处相同 ⇒ 任一薄层"进多少热就出多少热"，不积累也不亏空 ⇒ 稳态热传导 (steady-state conduction)。若 $\dfrac{\mathrm{d}^{2}T}{\mathrm{d}z^{2}}\neq 0$，说明某处有净的产热或吸热（如放射性生热、岩浆侵入、地下水对流），系统就不是稳态。

> 补充：$80\ ^{\circ}\mathrm{C\,km^{-1}}$ 是相当高的地温梯度（全球大陆平均约 $25\text{--}30\ ^{\circ}\mathrm{C\,km^{-1}}$），符合"热花岗岩床"的地质设定——正是地热发电 (EGS, enhanced geothermal systems) 的目标靶区。

---

### 5.11 周作业 Q5.8：利润最小化（牛顿法 + 二阶导数判别的综合题）

**题目**：你是某公司的业务分析师。公司想用毛利函数 $P(x)$ 建模，其中 $x$ 是售出**千**件数。

- (a) 求毛利最小时的销量。**提示：可能需要用牛顿法求导数的根来定位驻点。用初值 $x_{0}=3$，求到 3 位小数。**
- (b) 确认在该点毛利确实取到最小。

> 📎 说明：原 md 中利润函数是图片。根据 Solutions 的最终答案（$x=2.833$，$P''>0$）与迭代路径反推，函数为
> $$P(x)=e^{x}-3x^{2}$$
> （或其正数倍）。数值完全吻合：从 $x_{0}=3$ 出发四步收敛到 $2.833148$，且 $P''(2.833)>0$。**做题时以试卷上给的函数为准，但解法步骤完全一致。**

#### (a) 求驻点

**关键概念（Solutions 特别强调）**：

> "It's important to note that we are solving for the root of $\dfrac{\mathrm{d}P}{\mathrm{d}x}$, **not** $P(x)$."

要找**驻点**，就要解 $\dfrac{\mathrm{d}P}{\mathrm{d}x}=0$。所以把**导函数**当作牛顿法要求根的那个 $f$：

$$
f(x)\equiv\frac{\mathrm{d}P}{\mathrm{d}x}=e^{x}-6x
$$

牛顿法还需要 $f'(x)$，而 $f'=\dfrac{\mathrm{d}^{2}P}{\mathrm{d}x^{2}}$：

$$
f'(x)=\frac{\mathrm{d}^{2}P}{\mathrm{d}x^{2}}=e^{x}-6
$$

（**注意这个巧合**：牛顿法所需的分母，恰好就是 (b) 问要用的二阶导数。所以 (a) 做完，(b) 几乎白送——Solutions 原话："We already calculated the second derivative in the last part through Newton's method."）

$e^{x}-6x=0$ 即 $e^{x}=6x$，**无法用代数解出**，因此用牛顿法：

$$
x_{n+1}=x_{n}-\frac{e^{x_{n}}-6x_{n}}{e^{x_{n}}-6}
$$

**逐次迭代表**（$x_{0}=3$）：

| $n$ | $x_{n}$ | $f(x_{n})=P'(x_{n})$ | $f'(x_{n})=P''(x_{n})$ | $x_{n+1}$ | 步长 |
|---|---|---|---|---|---|
| 0 | 3.000000 | 2.085537 | 14.085537 | 2.851938 | $1.5\times10^{-1}$ |
| 1 | 2.851938 | 0.209687 | 11.321313 | 2.833416 | $1.9\times10^{-2}$ |
| 2 | 2.833416 | 0.002953 | 11.003450 | 2.833148 | $2.7\times10^{-4}$ |
| 3 | 2.833148 | 0.0000010 | 10.998888 | 2.833148 | $<10^{-7}$ |

到 3 位小数已稳定：

$$
\boxed{x=2.833}
$$

**回答题目问的问题**：$x$ 以**千件**为单位，所以

$$
\text{毛利最小时的销量}\approx 2.833\times1000=\textbf{2833 件}
$$

#### (b) 确认是极小值

用二阶导数判别法，二阶导数在 (a) 中已经算过：

$$
\frac{\mathrm{d}^{2}P}{\mathrm{d}x^{2}}=e^{x}-6
$$

代入 $x=2.833$：

$$
\frac{\mathrm{d}^{2}P}{\mathrm{d}x^{2}}(2.833)=e^{2.833}-6\approx 16.996-6=10.996>0
$$

**二阶导数为正 ⇒ 该驻点确为极小值 (minimum)。** ∎

（另注：$e^{x}=6x$ 还有一个根 $x\approx 0.204$，从 $x_{0}=0$ 出发会收敛到它，那里 $P''=e^{0.204}-6\approx-4.77<0$，是极大值。又是一个"初值决定收敛到哪个根"的例子。）

---

### 5.12 Practical 解题技巧汇总

1. **列表迭代**。牛顿法一律画表：$n$ / $x_{n}$ / $f(x_{n})$ / $f'(x_{n})$ / $x_{n+1}$。这样既不会算错，也方便阅卷人给步骤分，还能一眼看出是否收敛。
2. **多保留 2 位小数**。要 3 位小数就算到 5–6 位，最后再四舍五入。中途过早取整会导致最后一位错。
3. **计算器用弧度**。凡出现 $\sin$、$\cos$ 的题（Q5.4b, Q5.4c），必须切到 RAD 模式。这是最常见的"整题全错"来源。
4. **先移项再开工**。$g(x)=h(x)$ ⇒ 写成 $f(x)=g(x)-h(x)=0$ 再用牛顿法。
5. **能验算就验算**。二次方程用求根公式对答案（practical Ex 3 的教学意图）；其他情况把最终 $x$ 代回 $f(x)$ 看是否 $\approx 0$。
6. **"求驻点 + 无法解析求解" = 对导数用牛顿法**。这是 Q5.8 的题型信号，也是本周两大主题唯一的交汇点。
7. **稳态题只有两步**：一阶导（说明是常数）、二阶导（说明是 0）。两句话都要写，不要只写一句。
8. **线性函数 ⇒ 必稳态；指数函数 ⇒ 必不稳态**（本课口径下）。看到 $C(x)=a+bx$ 型立刻知道答案是 yes。
9. **多根题先看图**，图上有几个交点就要找几个根，题目给的初值可能不全（Q5.5 的坑）。
10. **单位与语境要还原**。Q5.8 答案不能停在 "2.833"，要写成 "约 2833 件"；Q5.6 要写单位 $\mathrm{mg\,m^{-3}\,m^{-1}}$。

---

## 六、易错点 / 重点难点

### 记号与概念

1. **$\dfrac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}$ 不是 $\left(\dfrac{\mathrm{d}y}{\mathrm{d}x}\right)^{2}$**。位置不同，含义完全不同。写错直接扣分。
2. **"二阶"指求导两次，不是"平方"**。$f''(x)$ 是把 $f'(x)$ 再求一次导。
3. **符号方向反直觉**：$f''<0\Rightarrow$ **极大**，$f''>0\Rightarrow$ **极小**。老师自己也说 "it does cross over"。用 $\cup$/$\cap$ 图形记忆。
4. **$f''(a)=0$ 不等于鞍点**。它只说明"判别法用不了"，必须回到一阶导符号法。$f(x)=x^{4}$ 在 $x=0$ 就是反例（是极小值）。
5. **判别法只能用在驻点上**。必须先确认 $f'(a)=0$，再看 $f''(a)$。随便取一点算 $f''$ 并说"这是极小值"是错的。
6. **稳态 ≠ 静止 / 平衡**。稳态要求有持续的流入流出，只是净变化为零。老师的水箱例子里水一直在流。
7. **稳态的空间与时间两种版本**。本课既用 $\mathrm{d}/\mathrm{d}t$（汽车、水箱）也用 $\mathrm{d}/\mathrm{d}x$、$\mathrm{d}/\mathrm{d}z$（浓度剖面、温度剖面）。两者形式一样，注意自变量是什么。

### 牛顿法

8. **忘记先把方程写成 $f(x)=0$**。题目给 $2x^{2}+5=e^{x}$ 时，要先移成 $2x^{2}+5-e^{x}=0$。Exercises5 专门提醒了这一点。
9. **迭代式的符号**：是 $x_{n}\;\boldsymbol{-}\;\dfrac{f(x_{n})}{f'(x_{n})}$，**减号**。写成加号会朝反方向跑。
10. **$f$ 与 $f'$ 都是负数时不要漏掉负负得正**。Q5.3 第一步 $\dfrac{-3.615}{-19.115}=+0.189$，是**减去**一个正数。幻灯片省略了负号，容易误导。
11. **不要把牛顿法用在 $P(x)$ 上而应该用在 $P'(x)$ 上**（Q5.8）。题目要"最小利润点"，那是 $P'=0$ 的根，不是 $P=0$ 的根。Solutions 用粗体强调过。
12. **计算器角度模式**。三角函数题必须用弧度。
13. **过早四舍五入**导致最后一位错。中途一律多留几位。
14. **停止准则要看"下一位"**。要 3 位小数，就得确认第 4 位不再变。
15. **一个初值只能找一个根**。多根问题必须为每个根单独设初值（Q5.5 要补 $x_{0}=0$）。
16. **切线水平就完蛋**：$f'(x_{n})=0$ ⇒ 除以零；$f'(x_{n})\approx 0$ ⇒ 被甩到很远，可能发散或跳到别的根。选初值时避开驻点。
17. **牛顿法不保证收敛**。讲义原文警告 "there is no guarantee this method will converge… each iteration will get worse and worse"。答题时若被问到局限性，要能说出：发散、循环、除零、收敛到非目标根、重根收敛慢。
18. **牛顿法不保证单调逼近**。Q5.4(a) 里 $5\to 6\to 5.719$，先跳过了根又跳回来。中途"变远了"不代表算错。

### 题源与编号

19. **主手册题号混乱**：Solutions 里写的 "from Chapter 3 Question 5.4(a)"、"Chapter 2 Question 5.8" 是转档产生的错误交叉引用，**不要按这个去 Week 2/3 的文件里找**。**一律以周版 `Exercises5.md` 的 Q5.1–Q5.8 为准。**
20. **Q5.3 的区间描述前后矛盾**：题干说 $[3,4]$，Solutions 说 $[4,6]$。以题干为准。
21. **Q5.2(a) Solutions 有笔误**：写成 "$x=-6$ and $x=-5$"，正确是 $x=-6$ 和 $x=+5$。
22. **Q5.6 两个版本数字不同**：practical 用 $C_{1}=0.11$，周作业用 $C_{1km}=0.1$。方法一样，代数不同。
23. **课堂 practical 的 Exercise 编号（1–3）与周作业的 Question 编号（5.1–5.8）是两套**，不要混引。

### 转写陷阱

24. **稳态那一节老师讲串了**（污染物 vs 汽车），中途自我纠正。以 $x(t)=1+68t$ 的汽车版为准。
25. **牛顿法推导那一段转写不可读**（老师自认 "I completely messed that explanation up"）。用讲义 §5.3 的干净推导。

---

## 七、本周术语表

| 中文 | English | 记号 / 说明 |
|---|---|---|
| 一阶导数 | first-order derivative | $f'(x)=\dfrac{\mathrm{d}y}{\mathrm{d}x}$；函数的变化率 |
| 二阶导数 | second-order derivative | $f''(x)=\dfrac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}$；变化率的变化率 |
| （微分方程的）阶 | order (of a differential equation) | 方程中出现的最高阶导数 |
| 二阶常微分方程 | second order ODE | $a\dfrac{\mathrm{d}^{2}y}{\mathrm{d}x^{2}}+b\dfrac{\mathrm{d}y}{\mathrm{d}x}+cy=0$，Week 9 内容 |
| 驻点 / 稳定值 | stationary point / stationary value | $f'(x)=0$ 处 |
| 二阶导数判别法 | second derivative test | $f''<0$ 极大，$f''>0$ 极小，$f''=0$ 不定 |
| 局部极大值 | local maximum | $f'(a)=0,\;f''(a)<0$ |
| 局部极小值 | local minimum | $f'(a)=0,\;f''(a)>0$ |
| 鞍点 | saddle point | 驻点但非极值，函数不换向 |
| 拐点 | point of inflection | 凹凸性改变的点 |
| 上凸 / 下凹 | concave down / concave up | $f''<0$ 为 $\cap$；$f''>0$ 为 $\cup$ |
| 优化 | optimisation | 求函数的最大/最小值 |
| 位移 / 速度 / 加速度 | distance / velocity / acceleration | $x=f(t)$，$v=f'(t)$，$a=f''(t)$ |
| 稳态 | steady state | 系统变量不随时间改变；$\dfrac{\mathrm{d}^{2}w}{\mathrm{d}t^{2}}=0$ |
| 瞬态 | transient state | 变量仍在随时间变化的阶段 |
| 源 / 汇 | source / sink | 使系统量增加 / 减少的过程 |
| 通量 | flux | 单位时间通过单位面积的量 |
| 傅里叶定律 | Fourier's law | $q=-k\dfrac{\mathrm{d}T}{\mathrm{d}z}$，热流正比于温度梯度 |
| 地温梯度 | geothermal gradient | $\dfrac{\mathrm{d}T}{\mathrm{d}z}$，本周题中为 $80\ ^{\circ}\mathrm{C\,km^{-1}}$ |
| 静水压方程 | hydrostatic equation | $P(z)=P_{0}\exp\!\left(-\dfrac{g}{R_{a}T}z\right)$ |
| 根 | root | 使 $f(x)=0$ 的 $x$ |
| 求根 | root finding | 求 $f(x)=0$ 的解 |
| 牛顿-拉夫森法 / 牛顿法 | Newton-Raphson method / Newton's method | $x_{n+1}=x_{n}-\dfrac{f(x_{n})}{f'(x_{n})}$ |
| 迭代 | iteration | 重复应用同一公式，前次输出为后次输入 |
| 迭代算法 | iterative algorithm | 牛顿法即是 |
| 初始猜测 / 初值 | initial guess | $x_{0}$；选取影响收敛与收敛到哪个根 |
| 切线 | tangent (line) | $y=f(x_{0})+f'(x_{0})(x-x_{0})$ |
| 收敛 | convergence | 迭代值趋近某个定值 |
| 发散 | divergence | 迭代值越跑越远 |
| 二次收敛 | quadratic convergence | 每次迭代正确位数约翻倍 |
| 容差 / 阈值 | tolerance / threshold | 判定"够接近 0"的标准 |
| 停止准则 | stopping criterion | 何时终止迭代 |
| 吸引域 | basin of attraction | 收敛到某一特定根的初值集合 |
| 解析解 | analytical solution | 用代数写出的精确解 |
| 数值解 | numerical solution | 用迭代算法逼近的近似解 |
| 小数位 | decimal places (d.p.) | 精度表述，如 "3 d.p." |
| 二次求根公式 | quadratic formula | $x=\dfrac{-b\pm\sqrt{b^{2}-4ac}}{2a}$ |
| 乘积法则 | product rule | $(uv)'=u'v+uv'$ |
| 商法则 | quotient rule | $\left(\dfrac{u}{v}\right)'=\dfrac{u'v-uv'}{v^{2}}$ |
| 链式法则 | chain rule | $\dfrac{\mathrm{d}y}{\mathrm{d}x}=\dfrac{\mathrm{d}y}{\mathrm{d}u}\dfrac{\mathrm{d}u}{\mathrm{d}x}$ |
| 初值问题 | initial value problem | 老师预告的后续内容 |
| 边界条件问题 | boundary condition problem | 老师预告的后续内容 |

---

## 附：本周一页速记

```
【二阶导数】f''(x) = d²f/dx²  —— 变化率的变化率
  物理: 位移 x=f(t) → 速度 v=f'(t) → 加速度 a=f''(t)

【驻点分类】先 f'(a)=0，再看 f''(a)：
   f''(a) < 0  →  极大 (∩)
   f''(a) > 0  →  极小 (∪)
   f''(a) = 0  →  不定！回退查 f' 在两侧的符号
                  同号 → 鞍点；变号 → 仍是极值

【稳态】一阶导 = 常数  ⟺  二阶导 = 0  ⇒  steady state
   答题两句：① 求一阶导，说它是常数 ② 求二阶导，说它是 0
   线性剖面 ⇒ 稳态；指数剖面 ⇒ 非稳态

【牛顿法】x_{n+1} = x_n − f(x_n)/f'(x_n)
   来源：切线 y = f(x₀) + f'(x₀)(x−x₀)，令 y=0 解 x₁
   流程：移项成 f(x)=0 → 求 f' → 选 x₀ → 迭代 → 查停止准则
   失败：f'=0（除零）/ 初值差（发散）/ 循环 / 收敛到别的根 / 重根变慢
   求驻点解不出来时 ⇒ 对 f = P'(x) 用牛顿法，此时 f' = P''(x)

【关键数字】
   Ex 5.3 / Q5.3  2x²+5−eˣ, x₀=3.5  → 3.275601 (6 d.p.)
   Prac Ex 3      x²+2x−10, x₀=4    → 2.31662  (= −1+√11 ✓)
   Q5.4  (a) 5.71875  (b) 2.219185  (c) 0.744094   (均为 x₂)
   Q5.5  x³−x²−15x+1 三根: −3.442, 0.066, 4.376
   Q5.7  地温梯度 0.08 °C/m = 80 °C/km
   Q5.8  x = 2.833 → 约 2833 件，P''(2.833) > 0 ⇒ 极小
```
