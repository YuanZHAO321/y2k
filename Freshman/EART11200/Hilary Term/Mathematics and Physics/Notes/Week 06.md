# Week 6 — 积分入门（Introduction to Integration）

> 课程：EART11200 The Natural Scientist's Toolkit — Hilary Term, **Mathematics and Physics**
> 对应手册章节：**Chapter 6. Introduction to Integration**（`main(1).md` 第 2059–2372 行）
> 本周材料：`Lecture/Week 6/Chapter6.md`、`Lecture/Week 6/lecture6.md`（24 页 slides）、`Lecture/Week 6/EART11200 - 03-Mar-transcript.md`（课堂录音转写）、`Practical/Week 6/Exercises6.md`、`Solutions6.md`、`practical6_soln(1).md`
> 课程日历：03/03/2025，学期第 25 周 = 本课程 **Week 6**

---

## 一、本周主题

本周是**整门课的分水岭**：前五周（Week 1–5）全部在做**微分 (differentiation)**，从这一周开始的四周全部在做**积分 (integration)**。

讲师在课堂开头把这件事说得非常直白：

> "So we spent five weeks looking at differentiation. ... For the next four weeks we're going to be talking about integration which is about kind of the opposite of differentiation. Instead of differentiating the final rate of change we're actually going to use the rate of change and integrate it to tell us something about the process of what has changed over time."

**方向的逆转**是本周唯一的核心思想：

$$
\underbrace{f(x)}_{\text{过程本身}}
\quad\xrightarrow[\text{Week 1--5}]{\ \text{differentiation}\ }\quad
\underbrace{\frac{df}{dx}}_{\text{变化率}}
\quad\xrightarrow[\text{Week 6--9}]{\ \text{integration}\ }\quad
\underbrace{f(x)}_{\text{过程本身}}
$$

- **前五周的题型**：「这是函数 $f(x)$，请求 $\dfrac{df}{dx}$。」
- **从本周起的题型**：「这是 $\dfrac{df}{dx}$（一个 **ODE**），请求 $f(x)$。」

讲师原话：*"I would have given you a function and I would have told you to derive these differential equations. The other way around we're going to do this now — I give you the differential equations, I'm going to ask you to solve them."*

### 本周在全课中的位置（Course Layout，slides p.6）

| 日期 | 学期周 | 课程周 | 主题 |
|---|---|---|---|
| 27/01/2025 | 20 | W1 | Calculating Gradients |
| 03/02/2025 | 21 | W2 | Introduction to Differentiation |
| 10/02/2025 | 22 | W3 | Differentiating Combinations of Functions |
| 17/02/2025 | 23 | W4 | Optimisation & Properties of Derivatives |
| 24/02/2025 | 24 | W5 | Second Order Derivatives & Root Finding |
| **03/03/2025** | **25** | **W6** | **Introduction to Integration ← 本周** |
| 10/03/2025 | 26 | W7 | Integration using Newton's Laws |
| 17/03/2025 | 27 | W8 | Integration by Substitution |
| 24/03/2025 | 28 | W9 | Integrating Second Order ODEs |
| 31/03/2025 | 29 | W10 | Vectors and Partial Differentiation |
| 07/04 – 21/04 | 30–32 | — | Non-teaching week + Easter break |
| 28/04/2025 | 33 | W11 | Revision: Differentiation |
| 05/05/2025 | 34 | W12 | Revision: Integration + **Exam Period** |

### 本周 Intended Learning Outcomes（slides p.7 与 practical p.3，两处一字不差）

1. **Describe the concept of integration** and explain its significance in calculus.（说清积分是什么、为什么微积分需要它）
2. **Identify and interpret common notation** used in integration.（认得并会读积分记号）
3. **Describe the role of Ordinary Differential Equations (ODEs)** in scientific modeling across various disciplines.（说清 ODE 在各学科建模中的角色）
4. **Apply common laws of integration** to solve theoretical and real-world problems.（会用积分表解代数题与真实世界问题）

### 一句话概括本周能力目标

**给你一条描述"变化率"的方程（ODE），你能把它积回去，得到"总量/绝对值"的函数；并且当给定上下限时，你能算出那段区间内的实际总量（= 曲线下面积）。**

---

## 二、核心概念

### 2.1 积分是微分的逆运算（Integration as the reverse of differentiation）

**手册 6.2 节的原始表述：**

> "Integration is the **reverse** of differentiation. Since the derivative function provides us with a gradient, integration therefore provides us with a function that can be used to calculate absolute values."

翻译并展开：

- **导函数 (derivative function) 给的是「梯度 / 斜率 / 变化率」**——它是一个**相对量**，只告诉你"每单位时间/距离变了多少"。
- **积分 (integral) 给的是「绝对值 (absolute values)」**——它还原出那个真正的量本身。

**手册与 slides 反复用的那个水箱例子：**

- 若 $\dfrac{dV}{dt}$ 告诉你**水箱里的水量每秒变化多少**（流量，flow rate），
- 那么对它积分，就告诉你**任一时刻水箱里有多少水**，或**某段时间内水量总共变化了多少**。

讲师课堂上把这个直觉讲到最朴素的程度：

> "If I'm telling you that this tank is filling up by one litre per second, then after 10 seconds, you should say, well, that's 10 litres. And that's what integration is telling you."

也就是说：**流量 × 时间 = 体积**。当流量不是常数时，这个"乘法"就要换成积分。

**为什么这件事"看上去不可能"？** 手册特别提醒：

> "To integrate a differential equation therefore requires us to reverse the steps taken to get to that point. At first glance, this seems like an impossible task since it is likely we did not generate the differential equation. However you will start to recognise forms of equations and what steps you therefore need to carry out."

即：微分是**机械的**（有链式法则、乘法法则一路推下去），积分本质上是**认模式 (pattern recognition)**——你要认出"这个式子长得像谁被微分之后的样子"。所以**积分表要背熟、要反复练**，这不是偷懒而是唯一的路。

---

### 2.2 定积分的几何意义：曲线下面积（Area under the curve）

这是本周的**第二根支柱**，也是把"逆运算"和"求和"两个直觉焊在一起的地方。

#### （1）简单情形：用三角形 + 矩形直接量（Figure 6.2）

Figure 6.2 上图是**流量 (flow rate, mL s⁻¹) vs 时间 (s)** 的曲线，形状是「梯形」：

- $t = 0 \to 30$ s：流量从 0 **线性上升**到 250 mL/s；
- $t = 30 \to 70$ s：流量**恒定** 250 mL/s（手册强调："Here the rate of change is constant. So, after 1 second, the water has increased by a fixed amount. In the next second, the water increases by the same amount."）；
- $t = 70 \to 100$ s：流量**线性下降**回 0。

Figure 6.2 下图则是**总体积 (total volume, mL) vs 时间**——它就是上图的**曲线下面积**。手册对下图形状的描述值得记住：

> "the volume increases at a non-constant rate at first, but between 30 and 70 seconds the volume increases according to a straight line. After 70 seconds the volume increases at a non-constant rate, before leveling off."

**这段描述本身就是「积分是微分的逆」的图像证据**：上图恒定 → 下图是直线（斜率恒定）；上图上升 → 下图是上凹曲线；上图回落到 0 → 下图变平（leveling off）。

**手算面积（讲师课堂现场算的三块）：**

$$
\begin{aligned}
\text{第一段（三角形）}&: \tfrac12 \times 30 \times 250 = 3750\ \text{mL}\\
\text{第二段（矩形）}&: 40 \times 250 = 10000\ \text{mL}\\
\text{第三段（三角形）}&: \tfrac12 \times 30 \times 250 = 3750\ \text{mL}\\
\hline
\text{总计}&: 17500\ \text{mL}
\end{aligned}
$$

与 Figure 6.2 下图纵轴（$\sim 1.75 \times 10^4$ mL 后趋平）完全吻合。

> 要点：**要求 $t=0$ 到任意 $t$ 的总量，就是求 $0$ 到 $t$ 的曲线下面积**。手册原句："if we want to describe how the volume of water in the system changes with time, $t$, then we can calculate it from the above graph by finding the area under the graph from $Time = 0$ to any time, $t$."

#### （2）一般情形：用矩形逼近（Figure 6.3，数值近似）

真实的流量曲线不会这么好心。Figure 6.3 上图给的是

$$
f(x) = -0.1x^2 + 10x
$$

（注意：这条抛物线在 $x = 50$ 处取最大值 $f(50) = -0.1(2500) + 500 = 250$，正好复刻了 Figure 6.2 的峰值流量 250 —— 是同一个物理场景的"光滑版"。）

**矩形逼近法 (numerical approximation)：**

- 把 $[0, x]$ 切成许多宽度为 $\Delta x$ 的小段；
- 每一小段上，用高度 $f(x)$ 的矩形近似那块面积；
- 单个矩形面积 $= f(x) \times \Delta x$；
- 总面积 $\approx$ 所有矩形面积之和：

$$
\text{Area} \approx \sum f(x)\,\Delta x
$$

手册明确点出这与前面微分内容的对应关系：

> "This is a **numerical approximation** method, similar to central differences method for differentiation, representing a manual integration of the function."

#### （3）取极限 → 解析积分（analytical integration）

slides p.12 把这个类比写得最清楚：

$$
\underbrace{\frac{dy}{dx} = \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x}}_{\text{数值微分}\to\text{解析微分}}
\qquad\Longleftrightarrow\qquad
\underbrace{\int f(x)\,dx = \lim_{\Delta x \to 0} \sum f(x)\,\Delta x}_{\text{数值积分}\to\text{解析积分}}
$$

讲师原话：*"Well integration works in the same way! Making the increment smaller in the sum gives us analytical integration."* 以及 *"If we get that smaller and smaller, those rectangles will converge to the area under the curve. And that's where we get the integral from."*

**本课的对应解析结果：**

$$
\int_0^x \left(-0.1x^2 + 10x\right) dx = -\frac{0.1x^3}{3} + 5x^2
$$

即 Figure 6.3 下图那条曲线——它**是一个函数**，能直接给出 $0$ 到任意 $x$ 的面积，不用再拼矩形。

> **本课的实操立场**：讲师明说 *"we're not actually going to do numerical integration here because numerical integration is much more involved than numerical differentiation"*（数值积分要拼很多个矩形再求和，比数值微分麻烦得多）。所以**考试与作业一律走解析路线（查积分表）**，矩形逼近只作为"积分是什么"的直觉来源。

---

### 2.3 积分记号（Notation）

$$
\int_{a}^{b} f(x)\, dx
$$

| 记号部件 | 名称 | 含义（手册 / slides / transcript 的解释） |
|---|---|---|
| $\int$ | 积分号（S 形符号） | 代表 **"summing up"（求和）**。由 **Gottfried Wilhelm Leibniz** 于 **17 世纪** 引入，表示"无穷多个无穷小量的求和"（"summation of infinitely many infinitesimally small quantities"） |
| $f(x)$ | 被积函数 / **integrand** | 每个小矩形的**高** |
| $dx$ | 积分微元 | 每个小矩形的**底边长**，即 $\Delta x$ 取极限后的形式；同时声明**对哪个变量积分** |
| $a,\ b$ | **limits of integration**（积分限） | 下限、上限。$\int_0^x$ 读作"求 $0$ 到 $x$ 之间的曲线下面积" |

**读法（讲师逐字示范）：**

> "$dy/dx$ meant the rate of change in $y$ with respect to $x$. This reads as: we're going to integrate between zero and $x$ of this function with respect to $x$."

**为什么是 S 形？** 因为 S = Sum。手册："Because integration can be seen as a *summing up* of lots of smaller rectangles we write it formally with an S-shaped symbol."

---

### 2.4 不定积分 (Indefinite Integration) 与积分常数 $d$

#### 规则本身

对幂函数：

$$
\int x^n\, dx = \frac{x^{n+1}}{n+1} + d
$$

手册的口诀化表述（**加一次幂，除以新幂**）：

> "we can calculate the integral of them by **raising the power of $x$ by 1** and **dividing by the new power that $x$ is raised**."

对照 Week 2 的微分口诀（**幂次拿到前面，指数减一**），刚好完全相反：

| | 微分 | 积分 |
|---|---|---|
| 幂次 | $n$ **降** 1 | $n$ **升** 1 |
| 系数 | **乘以**原幂次 $n$ | **除以**新幂次 $n+1$ |
| 常数 | 微分掉，变 0 | 必须**补回** $+d$ |

#### 为什么必须加 $+d$？

手册的解释（这是**必考的概念题**）：

> "Why do we add the constant, $d$? Well, integration is the opposite of differentiation (remember differentiation of a constant is zero) and differentiation 'loses' any constant that might have been present in the original function so we add this in."

用式子讲清楚：

$$
\frac{d}{dx}\left(x^2\right) = 2x,\qquad
\frac{d}{dx}\left(x^2 + 7\right) = 2x,\qquad
\frac{d}{dx}\left(x^2 - 1000\right) = 2x
$$

三个**不同**的函数，导数**完全相同**。所以当你只拿到 $\dfrac{dy}{dx} = 2x$ 时，你**根本没有信息**能判断原函数尾巴上挂着什么常数。诚实的做法是写：

$$
\int 2x\,dx = x^2 + d
$$

讲师课堂原话：*"when you're just given $dy/dx$, you have no information ... So we're just going to add them on just in case they were. There may be a constant, it may be zero, it may not be. But what we're going to do is add it in to make sure that we're correct."*

#### 为什么叫「不定」？

> "For standard integration we cannot say what the constant is: it can take on any value so we just call it a **constant**. For this reason it is called **indefinite integration**."

讲师补充的两层理解：

1. **"不定"指常数不确定**：*"we cannot be definitive about what the full function is when integrating."*
2. **"不定"也指没有积分限**：*"because you're not doing it between any two limits ... there's no limits. So we're not going to integrate between any values. It's called indefinite integration."*

#### 怎样才能定出 $d$？

靠 **initial conditions（初始条件）** 或 **boundary conditions（边界条件）**。

> slides p.15: "You may have something called initial or boundary conditions, which helps figure out what this constant is!"

本周就有现成例子：解放射性衰变方程时，条件是 $t=0$ 时 $N = N_0$，代入即得 $c = \ln N_0$（见 2.7 节）。**Week 9 讲二阶 ODE 时会正式引入 initial value problems（讲师在 recap 中已经预告）。**

---

### 2.5 定积分 (Definite Integration)：求面积就得有上下限

手册：

> "To find the **area under a curve** we have to perform **definite integration** between limits. This means that we calculate the integral (as in the table above) then evaluate the integral for two values of $x$, and calculate the difference."

**操作三步：**

1. 先做不定积分，得到原函数（antiderivative）$F(x)$；
2. 分别代入上限 $b$ 与下限 $a$；
3. **上限值减下限值**：

$$
\int_a^b f(x)\,dx = \Big[F(x)\Big]_a^b = F(b) - F(a)
$$

> 这正是**微积分基本定理 (Fundamental Theorem of Calculus)** 在本课中的实用形态：本课不写它的名字、不证明它，但整套"先求原函数、再代上下限作差"的流程**就是**它。它的含义是：**"求面积"这个几何问题，与"求微分的逆"这个代数问题，是同一件事**——你不必真的去拼无穷多个矩形，只要能找到一个导数等于 $f$ 的函数 $F$，面积就等于 $F$ 在两端的差值。

#### 例题 Example 6.1（手册 / slides p.16 / 课堂逐步演算）

求 $y = x^2$ 在 $x = 1$ 到 $x = 2$ 之间的曲线下面积。

$$
\int_1^2 x^2\,dx
= \left[\frac{x^3}{3}\right]_1^2
= \frac{2^3}{3} - \frac{1^3}{3}
= \frac{8}{3} - \frac{1}{3}
= \frac{7}{3} \approx 2.333
$$

**物理读法（讲师给的）**：若 $x^2$ 描述"往水箱里加水的速率"，则在 $t = 1$ 到 $t = 2$ 这段时间里共加入了 $\tfrac73$ 升水。

#### 关键问题：常数 $d$ 去哪了？（slides p.16 特意留的思考题 "Where do you think the constant has gone?"）

**把 $d$ 老老实实带进去算一遍：**

$$
\int_1^2 x^2\,dx
= \left[\frac{x^3}{3} + d\right]_1^2
= \left(\frac{2^3}{3} + d\right) - \left(\frac{1^3}{3} + d\right)
= \frac{8}{3} + d - \frac{1}{3} - d
= \frac{7}{3}
$$

**$d$ 自动抵消**。手册的结论句：

> "Note that when calculating a difference the constant in the integration, $d$, disappears so we do not have to consider it."

因此实操规则：

- **不定积分 → 必须写 $+d$**（不写就是错，扣分）
- **定积分 → 不必写 $+d$**（写了也不算错，只是白写，因为一定抵消）

> ⚠️ **转写文字警告**：transcript 在这一段（约 1323–1345 行）讲师**口误**了，把 "definite" 说成了 "indefinite" 好几次（"When you do indefinite integration, you don't bother adding it in ... it all cancels out in the end"）。按语义，那几句里凡是"不用加常数、常数会抵消"的都指 **definite（定）积分**；凡是"必须加常数"的都指 **indefinite（不定）积分**。**不要被转写误导。**

---

### 2.6 和的积分 = 积分的和（Sum rule）

slides p.17：

> "What happens when we have a sum of functions? Well luckily, **the integral of the sum is the sum of the integral!** This means we can just integrate each term individually."

$$
\int \big[f(x) + g(x)\big] dx = \int f(x)\,dx + \int g(x)\,dx
$$

**slides 上的例子：**

$$
\frac{dy}{dx} = 2x + e^x
\quad\Longrightarrow\quad
y = \int 2x\,dx + \int e^x\,dx = x^2 + e^x + d
$$

（讲师在课堂上写这个例子时忘了写 $+d$，当场自我纠正：*"Oh, I missed out something here. I should have added a $d$ on there."* —— 这本身就是最好的易错点示范。）

> 注意：**只有和 / 差可以拆**。乘积、商、复合函数**不能**这样拆（微分有乘法法则、商法则、链式法则；积分对应的技巧是 Week 8 的**换元积分 (integration by substitution)**）。slides 原话："We'll see what happens when we have more complicated combinations of functions soon."

---

### 2.7 常微分方程 (ODEs) 与分离变量法 (Separation of Variables)

#### 什么是 ODE？

> slides p.9 / p.18: "A large part of science is built on solving **Ordinary Differential Equations (ODEs)**. ... **If we have a differential equation with respect to 1 variable, we have an ODE.**"

**判定标准就一条：只对 1 个自变量求导 → ODE**（"Ordinary" 就是这个意思；若涉及多个自变量的偏导数，那叫 PDE，Week 10 才碰）。

手册 6.3 节的叙事转向：

> "So far, we have been given $f(x)$ and asked to find $\frac{d}{dx}f$, but now we are starting with $\frac{d}{dx}f$ instead. We often refer to $\frac{d}{dx}f$ as **Ordinary Differential Equations (ODEs)**."

**课堂点名的"famous equations"（本课会遇到的三条）：**

| ODE | 形式 | 物理含义 |
|---|---|---|
| **放射性衰变 Radioactive decay** | $\dfrac{dN}{dt} = -\lambda N$ | 单位时间衰变数 ∝ 现存不稳定核数 |
| **牛顿冷却定律 Newton's law of cooling** | $\dfrac{dT}{dt} = -\alpha\,(T - T_s)$ | 降温速率 ∝ 物体与环境的温差（$\alpha$ = 冷却速率，$T_s$ = 表面/环境温度） |
| **牛顿第二定律 Newton's second law** | $F = ma$，可写成 $F = m\dfrac{dv}{dt} = m\dfrac{d^2x}{dt^2}$ | **Week 7 专门讲** |

**讲师强调的共同点**：*"effectively, this will be some sort of exponential relationship."*——这几条 ODE 的解都是指数型。

**不讲的部分（但要知道名字）**：教科书上会把 ODE 分"类型"，各类型有各自解法，例如 **Homogeneous（齐次）**、**Cauchy–Euler**、**Harmonic Oscillators（简谐振子）**。讲师明说本课**不深入**这些分类。

#### 手册的关键洞察：为什么放射性衰变与流体静力学方程"长得一样"？

> "The radioactive decay and hydrostatic equation have the same algebraic formulation. They are both equations that describe a **logarithmic change in one variable as a function of another**."

因为它们都是同一个模板：

$$
\boxed{\ \frac{dy}{dx} = k\,y \quad\Longrightarrow\quad y = y_0 e^{kx}\ }
$$

**只要"某量的变化率正比于该量自身"，解就一定是指数函数。** 衰变 ($k = -\lambda$)、气压随高度衰减 ($k = -g/(R_a T)$)、牛顿冷却、复利、种群增长……全是这一条。这是本周最值钱的一条**模式识别**。

#### 分离变量法（Separation of Variables）—— 本周唯一的解 ODE 技巧

**核心动作**：把方程"拆开"，让**所有 $y$（含 $dy$）挪到一边，所有 $x$（含 $dx$）挪到另一边**，然后两边同时积分。

讲师的口语版：*"you have to disassemble the differential equation, move all of the things on the numerator onto one side and move all the stuff on the denominator on the right hand side. Jiggle it about a little and you'll get an integral of your equation."*

**标准四步：**

$$
\begin{aligned}
&\text{① 出发：} && \frac{dy}{dx} = g(x)\,h(y)\\
&\text{② 除以 } h(y)：&& \frac{1}{h(y)}\frac{dy}{dx} = g(x)\\
&\text{③ 两边乘 } dx：&& \frac{1}{h(y)}\,dy = g(x)\,dx\\
&\text{④ 两边积分：}&& \int \frac{1}{h(y)}\,dy = \int g(x)\,dx
\end{aligned}
$$

> **注意本课的书写习惯**：这里把 $\dfrac{dy}{dx}$ 当分数拆开来乘 $dx$。严格数学上这需要论证，但**本课就是这么写的、也这么要求你写**，步骤名称固定为："We first divide both sides by $N$ / Then multiply both sides by $dt$ / Then integrate both sides"。**答题时把这三句话（或等价推导）写出来，是拿步骤分的关键。**

---

### 2.8 Example 6.2：放射性衰变方程（The radioactive decay equation）

#### 物理背景

> "For $\alpha$ and $\beta$ decay we can apply the radioactive decay equations. The law states that the number of decays per unit time is proportional to the number of unstable nuclei."

$$
\frac{dN}{dt} = -\lambda N
$$

- $N$ = 不稳定核的数目（number of unstable nuclei）
- $t$ = 时间
- $\lambda$ = **衰变常数 (decay constant)**，对特定同位素是常数，刻画衰变有多快
- 负号 = 数目在**减少**

**为什么这个定律"很自然"？** 手册：*"It is to be expected since if you have more unstable nuclei you would expect to observe more decays per second and vice versa."*（核多，每秒衰变自然就多。）

**衰变常数与半衰期的关系（Exercises 6.8 给出）：**

$$
\lambda = \frac{\ln 2}{t_{1/2}}
$$

#### 完整推导（Separation of variables，逐步）

$$
\begin{aligned}
\frac{dN}{dt} &= -\lambda N &&\text{出发的 ODE}\\[4pt]
\frac{1}{N}\frac{dN}{dt} &= -\lambda &&\text{两边除以 } N\\[4pt]
\frac{1}{N}\,dN &= -\lambda\,dt &&\text{两边乘 } dt\\[4pt]
\int \frac{1}{N}\,dN &= -\lambda \int dt &&\text{两边积分}\\[4pt]
\ln N &= -\lambda t + c &&\text{用 } \textstyle\int \frac1x dx = \ln x\\[4pt]
\end{aligned}
$$

**用初始条件定常数**：令 $t = 0$ 时 $N = N_0$（$N_0$ = 初始不稳定核数），代入：

$$
\ln N_0 = -\lambda \cdot 0 + c \quad\Longrightarrow\quad c = \ln N_0
$$

所以

$$
\ln N = -\lambda t + \ln N_0
$$

**两边取指数（讲师明确说 "take the exponential of each side"）：**

$$
N(t) = \exp\!\big(-\lambda t + \ln N_0\big) = e^{-\lambda t}\cdot e^{\ln N_0}
$$

**用对数律 $e^{\ln N_0} = N_0$：**

$$
\boxed{\,N(t) = N_0\, e^{-\lambda t}\,}
$$

> **注意这与前几周的呼应**：讲师说 *"I gave you a few weeks ago that this is a solution to that equation and I asked you to differentiate it to show that it is a solution. But actually now we're going to go from the top and actually use integration to get that."* —— 之前是给你答案让你**验证**（微分回去），现在是让你**从头解出来**（积分）。
>
> （手册这里有个笔误：把结果称作 "Newton's radioactive equations"，牛顿与放射性无关，忽略即可。）

---

### 2.9 Example 6.3：流体静力学方程（The hydrostatic equation）

#### 物理背景

空气密度由理想气体定律 (ideal gas law) 决定：

$$
\rho = \frac{P}{R_a T},\qquad R_a = 287\ \mathrm{J\,kg^{-1}\,K^{-1}}
$$

（$R_a$ = 干空气的比气体常数 specific gas constant；$P$ = 气压；$T$ = 气温）

流体静力平衡：气压随高度 $z$ 的变化率 = $-\rho g$。代入 $\rho$：

$$
\frac{dP}{dz} = -\rho g = -\frac{P g}{R_a T}
$$

**注意 $\dfrac{g}{R_a T}$ 整体是常数**（在"等温大气"假设下）。讲师反复强调："Remember, this is all constant."

#### 完整推导（Practical Exercise 3 就是让学生补完这一段）

$$
\begin{aligned}
\frac{dP}{dz} &= -\frac{g}{R_a T}\,P &&\text{出发}\\[4pt]
\frac{1}{P}\frac{dP}{dz} &= -\frac{g}{R_a T} &&\text{两边除以 } P\\[4pt]
\frac{1}{P}\,dP &= -\frac{g}{R_a T}\,dz &&\text{两边乘 } dz\\[4pt]
\int \frac{1}{P}\,dP &= -\frac{g}{R_a T}\int dz &&\text{两边积分}\\[4pt]
\ln P &= -\frac{g}{R_a T}z + c &&\\[4pt]
\end{aligned}
$$

**边界条件**：$z = 0$（地表）时 $P = P_0$ ⟹ $c = \ln P_0$。

$$
\ln P = -\frac{g}{R_a T}z + \ln P_0
\quad\Longrightarrow\quad
P = \exp\!\left(-\frac{g}{R_a T}z + \ln P_0\right)
$$

$$
\boxed{\,P(z) = P_0 \exp\!\left(-\frac{g z}{R_a T}\right)\,}
$$

**物理意义**：**气压随高度按指数衰减**。这就是"越高气压越低"的定量版本，也是气压高度计、大气标高 (scale height, $H = R_a T/g$) 的来源。

#### 更真实的版本（手册留的伏笔）

> "In actual fact the assumption that the temperature is constant is not true as it usually decreases with height in the atmosphere at about $10\ ^\circ\mathrm{C\ km^{-1}}$ (i.e. a drop of $10\ ^\circ$C for every km)."

（这就是**递减率 lapse rate**。）考虑温度随高度下降后，方程变成

$$
\frac{dP}{dz} = -\frac{P g}{R_a (T_0 - \Gamma z)}
$$

手册说它**有解析解**，但

> "we need some fancier integration techniques, which we will see later, to be able to show this!"

—— 指的就是 **Week 8 的换元积分 (integration by substitution)**。

> ⚠️ 主手册与 slides 在这里有 OCR 混乱，把 $R_a$ 写成 $R\alpha$、$\rho$ 写成 $\exists/\forall$ 等；正确形式以本节为准（$\rho = P/(R_a T)$，$R_a = 287\ \mathrm{J\,kg^{-1}K^{-1}}$）。

---

## 三、公式与图表

### 3.1 ★ 常用积分表（Common Laws of Integration）

**这张表 slides 里重复出现了 6 次**，讲师明说：*"these are in your handbook, they're in the survival packs. One of these will actually be on the exam. You'll have a table of equations at the beginning."*

| 导数 $\dfrac{dy}{dx}$（被积函数） | 积分 $y$ |
|---|---|
| $0$ | $d$ |
| $\text{constant}$（常数 $a$） | $\text{constant} \times x + d$ |
| $x$ | $\dfrac{x^2}{2} + d$ |
| $x^n$ | $\dfrac{x^{n+1}}{n+1} + d$ |
| $a x^n$ | $\dfrac{a x^{n+1}}{n+1} + d$ |
| $e^x$ | $e^x + d$ |
| $k e^{kx}$ | $e^{kx} + d$ |
| $\dfrac{1}{x}$ | $\ln(x) + d$ |
| $\cos(x)$ | $\sin(x) + d$ |
| $\sin(x)$ | $-\cos(x) + d$ |

**手册 6.2 节还额外列的具体示例行（帮助理解"升幂除以新幂"）：**

| 被积函数 | 积分 |
|---|---|
| $3x^2$ | $x^3 + d$ |
| $x^3$ | $\dfrac{x^4}{4} + d$ |
| $2x^4$ | $\dfrac{2x^5}{5} + d$ |

**★ 讲师课堂补充的一行（表上没有，但极常用）：**

> "sometimes you may not have the $k$ in front of it. So that means that you may want to say, OK, the integral of $e^{kx}\,dx$ is equal to $\frac{1}{k}e^{kx} + d$."

$$
\int e^{kx}\,dx = \frac{1}{k}e^{kx} + d
$$

这正是 Exercises 6.1(f) $\int e^{2x}dx = \frac{e^{2x}}{2}+d$ 和 6.2(f) $\int_0^1 e^{3x}dx$ 用到的形式。**务必单独记住。**

### 3.2 ★ 与 Week 2 导数表的镜像对照

这是本周最该做的一件事：把两张表并排放，确认"每一行都是反着读"。

| 函数 $y$ | 微分 $\dfrac{dy}{dx}$（Week 2 学的） | ← 逆向 → | 被积函数 | 积分（Week 6 学的） |
|---|---|---|---|---|
| $c$（常数） | $0$ | ⇄ | $0$ | $d$ |
| $ax$ | $a$ | ⇄ | $a$ | $ax + d$ |
| $x^n$ | $n x^{n-1}$ | ⇄ | $x^n$ | $\dfrac{x^{n+1}}{n+1} + d$ |
| $e^x$ | $e^x$ | ⇄ | $e^x$ | $e^x + d$ |
| $e^{kx}$ | $k e^{kx}$ | ⇄ | $k e^{kx}$ | $e^{kx} + d$ |
| $\ln x$ | $\dfrac{1}{x}$ | ⇄ | $\dfrac{1}{x}$ | $\ln x + d$ |
| $\sin x$ | $\cos x$ | ⇄ | $\cos x$ | $\sin x + d$ |
| $\cos x$ | $-\sin x$ | ⇄ | $\sin x$ | $\boxed{-\cos x} + d$ |

**讲师亲口点出唯一的坑：**

> "The only [thing] you need to be a bit careful of is where to place the plus or minuses on the sine [and cosine]. But largely all of these rules you've seen before, it's just that we swap the columns now."

**记忆法**：微分 $\cos \to -\sin$（微分时"cos 变负"），所以积分 $\sin \to -\cos$（积分时"sin 变负"）。**负号永远挂在 cos 那一侧。**

### 3.3 运算法则

| 法则 | 公式 | 适用条件 |
|---|---|---|
| 常数倍法则 | $\displaystyle\int a f(x)\,dx = a\int f(x)\,dx$ | $a$ 与 $x$ 无关 |
| **和 / 差法则** | $\displaystyle\int \big[f \pm g\big] dx = \int f\,dx \pm \int g\,dx$ | 永远成立 |
| 定积分（FTC） | $\displaystyle\int_a^b f(x)\,dx = F(b) - F(a)$ | $F' = f$ |
| **不适用** | 乘积、商、复合函数**不能**逐项拆 | 需 Week 8 换元法 |

### 3.4 图表判读要点

**Figure 6.1 — Differentiation ↔ Integration 的互动图**

$$
f(x)\ \ \xrightleftharpoons[\ \text{integrate}\ ]{\ \text{differentiate}\ }\ \ \frac{df}{dx}
$$

看到这张图只需记一件事：**左边是"量"，右边是"率"；向右微分，向左积分。**

**Figure 6.2 — 流量 vs 时间（上）/ 总体积 vs 时间（下）**

判读口诀（**上图的高度 = 下图的斜率**）：

| 上图（$dV/dt$，流量） | 下图（$V$，总量） |
|---|---|
| 线性上升（0→30 s） | 上凹加速增长 |
| **恒定**（30→70 s，250 mL/s） | **直线**（斜率恒定） |
| 线性下降（70→100 s） | 增长变缓，上凸 |
| 归零（>100 s） | **变平 leveling off** |

**反向判读也要会**：给你 $V$–$t$ 曲线，其斜率就是流量曲线。这是把 Week 1（gradients）和 Week 6 焊在一起的关键练习。

**Figure 6.3 — 矩形逼近示意图**

- 上图：$f(x) = -0.1x^2 + 10x$，叠了一排宽 $\Delta x$、高 $f(x)$ 的矩形；
- 下图：$-\dfrac{0.1x^3}{3} + 5x^2$，即精确的"$0$ 到 $x$ 的累计面积"函数。
- 判读要点：**矩形是近似（有锯齿误差），下图曲线是精确解**；$\Delta x \to 0$ 时前者收敛到后者。

---

## 四、课堂补充（transcript 独有）

以下内容**只在录音转写里有**，slides 与手册上找不到。

### 4.1 Week 5 完整回顾（讲师用了近 1/6 的课时）

1. **微分方程的"阶 (order)"**：阶数 = 微分了几次。
   $$f'(x) = \frac{df}{dx}\ (\text{一阶}),\qquad f''(x) = \frac{d}{dx}\!\left(\frac{df}{dx}\right) = \frac{d^2f}{dx^2}\ (\text{二阶})$$
2. **二阶导数判别驻点 (stationary values)**：
   - $f''(x) < 0$ → **极大 maximum**
   - $f''(x) > 0$ → **极小 minimum**
   - $f''(x) = 0$ → **无法下结论**，可能是**鞍点 (saddle point)**，需回头查一阶导数的行为
   - 讲师对鞍点的口语定义：*"where a function comes to rest and starts going off in the same direction again"*（函数"停一下"然后**沿原方向继续**走）
3. **稳态 (steady-state)**：系统的关键变量不随时间改变 →
   $$\frac{dV}{dt} = \text{constant} \quad\Longleftrightarrow\quad \frac{d^2V}{dt^2} = 0$$
   讲师的水箱例子：暂态 (transient state) 时进水 > 出水；到达临界后进水 = 出水，变化率恒定，二阶导数为 0。
   **★ 预告**：*"that second order derivative equals zero is going to come up really really important later on in the term when we start talking about integrating differential equations and using something called **initial value problems**."*（Week 9）
4. **牛顿求根法 (Newton's Method for Root Finding)**：当 $f(x)=0$ 解不出来时用的迭代算法。
   - 要挑一个**受过教育的初始猜测 $x_0$**：*"you wouldn't choose an $x$ value that gives you a function evaluated at say a thousand. You would try and find something fairly small."*
   - 迭代到**收敛判据**为止，例如**第三位小数不再变化**就认为收敛。

### 4.2 考试与课程安排的硬信息（**极重要**）

- 剩下 **5 周**教学，**复活节前所有教学材料全部发完**。
- **Week 10（学期第 29 周，31/03/2025）那次课结束时，讲师会发去年的考卷 (last year's exam paper)**，让学生整个复活节假期都能做。
- 复活节后有 **2 次复习课 + 2 次 practical**：Week 11 复习微分，Week 12 复习积分。
- 讲师在复习课上会：**讲解全部习题答案**、**回顾他认为会考的内容**、给 tips and tricks、警告常见错误。
- **讲师本人出的考卷**：*"I have written your exam, I might give you some hints so please do come to those lectures."* → **复习课必须去。**
- **考卷首页会附一张公式表 (table of equations)**，就是本周这张积分表；同一张表也在 handbook 和 **maths survival pack** 里。
- 本周的积分表 *"one of these will actually be on the exam"*；本周内容还会出现在 **weekly assessment / quiz** 上。

### 4.3 讲师对"怎样学积分"的方法论

- *"The more you practice these procedures, the easier it will become to apply them without looking them up."*
- *"what I want you to do over the next few weeks is to try and get used to them and apply these over and over and over again in the lab questions and the quizzes."*
- **Practical 解答 slide 上的验算技巧（Exercise 1）**：
  > "You can verify your answer by **differentiating** and making sure that the result is the same as the integrand!"
  —— **积分做完，微分回去检查**。这是本课唯一免费的自检方法，考试时若有时间必用。

### 4.4 课堂上现场演板的两段（slides 上是图片，转写里有文字）

**（a）矩形逼近的现场推导**：讲师在白板上画了一条曲线，切成小块，说"这一小块的面积 $=f(x)\times 1$"（宽取 1），再把所有块加起来；然后强调"让宽度越来越薄 → 越来越准 → 收敛到曲线下面积 → 这就是积分"。他反复用 *"infinitesimal sum"* 这个词。

**（b）积分表的逐行"反向推导"**：讲师不是直接甩表，而是每一行都先写微分再倒过来：

| 讲师先写（微分方向） | 再倒过来（积分方向） |
|---|---|
| $y = c \Rightarrow \frac{dy}{dx} = 0$ | $\int 0\,dx = d$ |
| $y = ax \Rightarrow \frac{dy}{dx} = a$ | $\int a\,dx = ax + d$ |
| $y = x^n \Rightarrow \frac{dy}{dx} = nx^{n-1}$ | $\int n x^{n-1}dx = x^n + d$；改写为 $\int x^n dx = \frac{x^{n+1}}{n+1}+d$ |
| $y = e^x \Rightarrow \frac{dy}{dx} = e^x$ | $\int e^x dx = e^x + d$ |
| $y = e^{kx} \Rightarrow \frac{dy}{dx} = ke^{kx}$ | $\int ke^{kx}dx = e^{kx}+d$，故 $\int e^{kx}dx = \frac1k e^{kx}+d$ |
| $y = \ln x \Rightarrow \frac{dy}{dx} = \frac1x$ | $\int \frac1x dx = \ln x + d$ |
| $y = \sin x \Rightarrow \frac{dy}{dx} = \cos x$ | $\int \cos x\,dx = \sin x + d$ |
| $y = \cos x \Rightarrow \frac{dy}{dx} = -\sin x$ | $\int \sin x\,dx = -\cos x + d$ |

**这张"先微分、再倒读"的表就是背积分表的正确方法**：不要单独背积分表，背 Week 2 的导数表然后**从右往左读**。

### 4.5 讲师提到但本课不深入的东西

- ODE 的分类：**Homogeneous、Cauchy–Euler、Harmonic Oscillators** —— 知道名字即可。
- **数值积分 (numerical integration)** —— 只讲原理不做题，理由是比数值微分麻烦得多。
- **Week 7 预告**：*"I'll see you guys next week to carry on integrating Newton's laws."*（用积分处理 $F = ma$，把加速度→速度→位移串起来。）
- **Week 10 预告**：higher dimensions、**partial differentiation**、**nabla ($\nabla$)**。

---

## 五、Practical 要点

### 5.0 Practical 的目的

Practical 与 lecture 共用同一套 ILOs（1–4）。本周 practical 只有 **3 个 exercise**，分工非常清楚：

1. **Exercise 1** → 练不定积分 + 多项式逐项积分 + **别忘常数**；
2. **Exercise 2** → 练定积分 + **分数次幂** + 真实应用（气体泄漏）；
3. **Exercise 3** → 把 lecture 最后没做完的**流体静力学方程**补完（分离变量 + 边界条件）。

讲师课堂结语：*"we're going to do many, many different examples now in the practical."*

---

### 5.1 Practical Exercise 1：Common Laws of Integration

**题**：计算下列不定积分。

**(1)** $\displaystyle\int 6x^5 - 18x^2 + 7\ dx$

逐项应用 $\int ax^n dx = \frac{a x^{n+1}}{n+1}+d$：

$$
\int 6x^5 - 18x^2 + 7\ dx
= \frac{6}{6}x^6 - \frac{18}{3}x^3 + \frac{7}{1}x + d
= \boxed{x^6 - 6x^3 + 7x + d}
$$

> 解题思路：$6x^5 \to$ 幂升到 6，系数 $6/6 = 1$；$-18x^2 \to$ 幂升到 3，系数 $-18/3 = -6$；常数项 $7 \to 7x$。
> **自检**：微分回去 $6x^5 - 18x^2 + 7$ ✓

**(2)** $\displaystyle\int 10w^4 + 9w^3 + 7w\ dw$

注意：**积分变量是 $w$ 不是 $x$** —— 换个字母而已，规则一模一样。

$$
\int 10w^4 + 9w^3 + 7w\ dw
= \frac{10}{5}w^5 + \frac{9}{4}w^4 + \frac{7}{2}w^2 + d
= \boxed{2w^5 + \frac{9}{4}w^4 + \frac{7}{2}w^2 + d}
$$

> ⚠️ **原始 PDF 的印刷/OCR 不一致**：`practical6_soln(1).md` 上答案里第二项写成 $-\frac94 w^4$（负号），而题面写的是 $+9w^3$。二者矛盾，最可能是原题为 $10w^4 - 9w^3 + 7w$，或答案排版出错。**方法不受影响**：符号照抄被积函数即可。若题面为 $-9w^3$，答案则是 $2w^5 - \frac94 w^4 + \frac72 w^2 + d$。

**slide 上的红字提醒**：**"Don't forget the constants in indefinite integrals!"**

---

### 5.2 Practical Exercise 2：Definite Integration（气体泄漏）

**题**：某容器按下列 ODE 泄漏气体：

$$
\frac{dG}{dt} = 390\,t^{0.4}
$$

$t$ 单位为分钟，$G$ 单位为升/分钟。求 **1 到 3 分钟之间**释放的气体体积。

**解题思路**：题目问"某段时间内的总量" → **定积分**，上下限就是 1 和 3。

$$
\begin{aligned}
G &= \int_1^3 390\,t^{0.4}\,dt\\[4pt]
&= 390\left[\frac{t^{1.4}}{1.4}\right]_1^3 &&\text{幂 }0.4+1 = 1.4\text{，除以 }1.4\\[4pt]
&= 390\left(\frac{3^{1.4}}{1.4} - \frac{1^{1.4}}{1.4}\right)\\[4pt]
&= 390\,(3.325 - 0.714)\\[4pt]
&= 390 \times 2.611\\[4pt]
&= \boxed{1018.328\ \text{litres}}
\end{aligned}
$$

（$3^{1.4} = 4.6555$，$4.6555/1.4 = 3.3254$；$1/1.4 = 0.7143$。）

**答**：约 **1018.3 升**气体在第 1 到第 3 分钟之间泄漏。

> 技巧：**分数指数照常用"升幂除新幂"**，$0.4 \to 1.4$，不要被小数吓到。
> 技巧：常数系数 390 可以提到积分号外面（常数倍法则），最后再乘回去，算起来干净。
> **未写 $+d$ 是对的**——定积分不需要。

---

### 5.3 Practical Exercise 3：Hydrostatic Equation

**题**：lecture 已做到分离变量这一步：

$$
\int \frac{1}{P}\,dP = -\frac{g}{R_a T}\int dz
$$

请补完积分，证明 $P = P_0 \exp\!\left(-\dfrac{g z}{R_a T}\right)$ 是流体静力学方程的解（$P_0$ = 地表气压）。

**完整解答**（见 §2.9，此处给 practical 解答 slide 的原始步骤）：

$$
\ln P = -\frac{g}{R_a T} z + c
$$

代入边界条件 $z = 0,\ P = P_0$：

$$
\ln P_0 = c
$$

$$
\ln P = -\frac{g}{R_a T}z + \ln P_0
$$

两边取指数：

$$
P = \exp\!\left(-\frac{g}{R_a T}z + \ln P_0\right) = P_0 \exp\!\left(-\frac{g z}{R_a T}\right)
$$

$$
\boxed{P(z) = P_0\,\exp\!\left(-\frac{g z}{R_a T}\right)}
$$

> ⚠️ practical 解答 slide 上写 "if we say at $t = 0$" —— 这是**从放射性衰变那页复制过来的笔误**，此处应为 **$z = 0$**。

---

### 5.4 Handbook Exercises 6.1 – 6.10（周版 `Exercises6.md` 题号为准）

> **说明**：`Exercises6.md` / `Solutions6.md` 中不少公式在原 PDF 里是图片，转 md 后丢失。下面凡是原文可复原的，都给出完整解法；无法复原的题面已明确标注。

#### 【Algebraic problems】

**Question 6.1**：求下列**不定积分**。

| # | 题 | 解 | 思路 |
|---|---|---|---|
| (a) | $\displaystyle\int x^2\,dx$ | $\dfrac{x^3}{3} + d$ | 升幂除新幂 |
| (b) | $\displaystyle\int 12x^4\,dx$ | $\dfrac{12x^5}{5} + d$ | 系数提出，$12/5$ |
| (c) | $\displaystyle\int \sin(x)\,dx$ | $-\cos(x) + d$ | **注意负号** |
| (d) | $\displaystyle\int \cos(x)\,dx$ | $\sin(x) + d$ | 无负号 |
| (e) | $\displaystyle\int e^{x}\,dx$ | $e^{x} + d$ | 指数不变 |
| (f) | $\displaystyle\int e^{2x}\,dx$ | $\dfrac{e^{2x}}{2} + d$ | 用 $\int e^{kx}dx = \frac1k e^{kx}+d$，$k=2$ |
| (g) | $\displaystyle\int x^2+2x+3\,dx$ | $\dfrac{x^3}{3} + x^2 + 3x + d$ | 和法则，逐项 |
| (h) | $\displaystyle\int \sin(x)+\cos(x)\,dx$ | $-\cos(x) + \sin(x) + d$ | 和法则；负号只跟 cos 走 |
| (i) | $\displaystyle\int e^{2x}+2x\,dx$ | $\dfrac{e^{2x}}{2} + x^2 + d$ | 和法则；$2x \to \frac{2x^2}{2}=x^2$ |
| (j) | $\displaystyle\int e^{x}+\cos(x)\,dx$ | $e^{x} + \sin(x) + d$ | 和法则 |

> **十题只写一个 $+d$**：即使有多项，最后**只加一个**积分常数（多个常数可以合并成一个）。

---

**Question 6.2**：求下列**定积分**。

**(a)** $\displaystyle\int_0^{10} x^2\,dx = \left[\frac{x^3}{3}\right]_0^{10} = \frac{1000}{3} - 0 = \frac{1000}{3} \approx 333.33$

**(b)** $\displaystyle\int_{-10}^{10} x^2\,dx = \left[\frac{x^3}{3}\right]_{-10}^{10} = \frac{1000}{3} - \left(\frac{-1000}{3}\right) = \frac{2000}{3} \approx 666.67$

> 思路：$x^2$ 是**偶函数**，关于 $y$ 轴对称，所以恰好是 (a) 的两倍。可用对称性快速验算。

**(c)** $\displaystyle\int_{-1}^{1} x^3\,dx = \left[\frac{x^4}{4}\right]_{-1}^{1} = \frac{1}{4} - \frac{1}{4} = \boxed{0}$

> **重要概念题**：$x^3$ 是**奇函数**，$[-1,0]$ 上曲线在 $x$ 轴**下方**（面积记为负），$[0,1]$ 上在**上方**（正），恰好抵消。
> ⚠️ **这说明"定积分 = 面积"要加限定**：定积分给的是**带符号面积 (signed area)**。若真要"几何面积"，必须分段处理正负号。

**(d)** $\displaystyle\int_0^{80} \left(-0.1x^2 + 10x\right) dx = \left[-\frac{0.1x^3}{3} + 5x^2\right]_0^{80}$

$$
= -\frac{0.1 \times 512000}{3} + 5 \times 6400 = -17066.67 + 32000 = \boxed{14933.33}
$$

**(e)** $\displaystyle\int_0^{50} \left(-0.1x^2 + 10x\right) dx = -\frac{0.1 \times 125000}{3} + 5 \times 2500 = -4166.67 + 12500 = \boxed{8333.33}$

> **(d)(e) 的意义**：这就是 Figure 6.3 那条流量曲线。$x=50$ 是峰值流量点，$x=100$ 是流量归零点。(e) 是"到峰值为止的累计量"，(d) 是"到 $x=80$ 的累计量"。可以互相检查：(d) > (e) 因为区间更长，且 $50\to80$ 段流量仍为正。

**(f)** $\displaystyle\int_0^{1} \exp(3x)\,dx = \left[\frac{e^{3x}}{3}\right]_0^{1} = \frac{e^3}{3} - \frac{e^0}{3} = \frac{e^3 - 1}{3} = \frac{20.0855 - 1}{3} \approx \boxed{6.362}$

> ⚠️ 最容易错的地方：$\dfrac{e^{3\cdot 0}}{3} = \dfrac{1}{3}$，**不是 0**。

---

**Question 6.3**：求下列定积分（几何/物理含义题）。

**(a)** $\displaystyle\int_0^{b} \frac{h}{b}x\,dx$（即底 $b$ 高 $h$ 的三角形面积）

$$
= \frac{h}{b}\left[\frac{x^2}{2}\right]_0^{b} = \frac{h}{b}\cdot\frac{b^2}{2} = \boxed{\frac{bh}{2}}
$$

> **这题的意义**：直线 $y = \frac{h}{b}x$ 从 $(0,0)$ 连到 $(b,h)$，其下方就是三角形。积分给出 $\frac12 bh$ —— **与小学的三角形面积公式完全一致**，证明"积分就是求面积"不是空话。

**(b)** $\displaystyle\int_0^{b} h\,dx = \big[hx\big]_0^{b} = \boxed{hb}$

> 同理：常数函数 $y = h$ 下方是矩形，面积 = 底 × 高。**(a)+(b) 两题合起来正好复现 Figure 6.2 那种"三角形 + 矩形"手算法。**

**(c)** $\displaystyle\int_0^{T} \exp(-\lambda t)\,dt$

$$
= \left[-\frac{1}{\lambda}e^{-\lambda t}\right]_0^{T}
= -\frac{1}{\lambda}e^{-\lambda T} - \left(-\frac{1}{\lambda}e^{0}\right)
= \boxed{\frac{1}{\lambda}\left(1 - e^{-\lambda T}\right)}
$$

> **这题是 Q6.9 的核心工具**——放射性衰变曲线下的面积。
> 检查：$T \to \infty$ 时结果 $\to \frac1\lambda$（有限！），这就是**平均寿命 (mean lifetime)** 的来源。

---

**Question 6.4**：利用 $\displaystyle\int ax^n\,dx = \frac{a x^{n+1}}{n+1} + d$ 积分下列函数。

**关键技巧：先把根号和分母改写成幂 $x^n$（$n$ 可以是分数或负数）。**

**(a)** $f(x) = \sqrt{x} = x^{1/2}$

$$
\int x^{1/2}dx = \frac{x^{3/2}}{3/2} + d = \boxed{\frac{2}{3}x^{3/2} + d} = \frac23 x\sqrt{x} + d
$$

**(b)** $f(x) = \dfrac{1}{x^2} = x^{-2}$

$$
\int x^{-2}dx = \frac{x^{-1}}{-1} + d = \boxed{-\frac{1}{x} + d}
$$

**(c)** $f(x) = \dfrac{1}{\sqrt{x}} = x^{-1/2}$

$$
\int x^{-1/2}dx = \frac{x^{1/2}}{1/2} + d = \boxed{2\sqrt{x} + d}
$$

> ⚠️ **公式的适用条件**：$\int x^n dx = \frac{x^{n+1}}{n+1}+d$ 对**所有 $n \neq -1$** 成立（包括负数、分数）。
> **$n = -1$ 是唯一例外**，因为会除以 0——这时要用 $\displaystyle\int x^{-1}dx = \int\frac1x dx = \ln x + d$。**这是积分表里 $1/x$ 单独占一行的原因。**

---

**Question 6.5**：用分离变量法积分给定的 ODE。

> 📌 **题面在原 PDF 中是图片，md 版丢失。** 但从 `Solutions6.md` 保留的步骤文字可以**逆推**出结构：解答说 *"We first **multiply** both sides by $N$"*（不是"除以"）、*"Then multiply both sides by $dt$"*、*"The integral $\int x\,dx$ is equal to $\frac{x^2}{2}$"*、*"Rearranging this equation gives us..."*。
>
> 因此原 ODE 形如 $\dfrac{dN}{dt} = \dfrac{t}{N}$（或同型），推导为：

$$
\begin{aligned}
\frac{dN}{dt} &= \frac{t}{N}\\[4pt]
N\frac{dN}{dt} &= t &&\text{两边乘 } N\\[4pt]
N\,dN &= t\,dt &&\text{两边乘 } dt\\[4pt]
\int N\,dN &= \int t\,dt &&\text{两边积分}\\[4pt]
\frac{N^2}{2} &= \frac{t^2}{2} + c &&\text{用 }\textstyle\int x\,dx = \frac{x^2}{2}\\[4pt]
N^2 &= t^2 + 2c\\[4pt]
N &= \sqrt{t^2 + C},\qquad C = 2c
\end{aligned}
$$

> **不管具体是哪个 ODE，本题考的是"分离变量三句话"：divide/multiply by [变量] → multiply by $d$[另一变量] → integrate both sides。答题时把这三步写全。**
> **复习时若需精确题面，请回看 `Practical/Week 6/Exercises6.pdf` 第 101 页。**

---

#### 【Real-world problems】

**Question 6.6（河流流量）**：河水流量 $\dfrac{dW}{dt}$（m³ s⁻¹）由某函数描述，求 $t = 100$ 到 $t = 700$ s 之间流过的水量（m³）。

> 📌 **具体函数在 PDF 中是图片，md 版丢失。** `Solutions6.md` 提示："Perform definite integration of the function to get (**and using Question 6.4(b)**)"。
> **Q6.4(b) 是 $\int x^{-2}dx = -\frac1x$**，所以 $\dfrac{dW}{dt}$ 里含有 $\dfrac{k}{t^2}$ 型的项。

**通用解法**：

$$
W = \int_{100}^{700} \frac{dW}{dt}\,dt
$$

若 $\dfrac{dW}{dt} = \dfrac{k}{t^2}$，则

$$
W = k\left[-\frac1t\right]_{100}^{700} = k\left(\frac{1}{100} - \frac{1}{700}\right) = k\times\frac{6}{700} \approx 0.008571\,k\ \mathrm{m^3}
$$

> **解题思路要点（这才是考点）**：
> 1. "求某段时间流过多少水" = 对**流量**做**定积分**，上下限 = 给定的两个时刻；
> 2. 出现 $1/t^2$ 时改写为 $t^{-2}$ 再套幂法则；
> 3. **单位检查**：$\mathrm{m^3\,s^{-1}} \times \mathrm{s} = \mathrm{m^3}$ ✓ 答案单位必须是 m³。

**Question 6.7（降雨量）**：$t = 3.5$ 到 $t = 6.5$ 小时之间，云的降雨率（mm/hr）可近似为 $-3t^2 + 30t - 65$。求这段时间的**总降水量**（mm）。

**完整解答**：

$$
\begin{aligned}
\text{Total} &= \int_{3.5}^{6.5}\left(-3t^2 + 30t - 65\right)dt\\[4pt]
&= \left[-\frac{3t^3}{3} + \frac{30t^2}{2} - 65t\right]_{3.5}^{6.5}\\[4pt]
&= \left[-t^3 + 15t^2 - 65t\right]_{3.5}^{6.5}
\end{aligned}
$$

代入上限 $t = 6.5$：

$$
-(6.5)^3 + 15(6.5)^2 - 65(6.5) = -274.625 + 633.75 - 422.5 = -63.375
$$

代入下限 $t = 3.5$：

$$
-(3.5)^3 + 15(3.5)^2 - 65(3.5) = -42.875 + 183.75 - 227.5 = -86.625
$$

作差：

$$
-63.375 - (-86.625) = \boxed{23.25\ \text{mm}}
$$

> **解题思路要点**：
> 1. "rate (mm/**hr**)" 对时间（hr）积分 → 得到 mm。**单位自洽是判断"要不要积分"的最快信号。**
> 2. 两个端点的函数值**都是负数**，但**差是正的** —— 千万别看到负数就慌，也别忘了减号前的括号。
> 3. 这是 **upper − lower** 的典型考法，把括号写全能避免符号错误。

---

**Question 6.8：放射性衰变方程**

用分离变量法求解

$$
\frac{dN}{dt} = -\lambda N,\qquad \lambda = \frac{\ln 2}{t_{1/2}}
$$

**完整解答见 §2.8**，结果：

$$
N(t) = N_0 e^{-\lambda t}
$$

> **这题与 lecture 的 Example 6.2 完全相同**，是本周必须能默写的推导。

---

**Question 6.9：切尔诺贝利羊（Chernobyl sheep，$^{137}$Cs）** ★ 本周旗舰应用题

**题目背景**：一只羊在被切尔诺贝利释放的 $^{137}$Cs 污染的田里吃草。约 1 kg $^{137}$Cs 被释放，其中一小部分雾化并扩散到很大范围。羊吃的草上有一定**表面数密度 (surface density)** 的放射性核，该密度随时间因衰变而降低。

**给定**：
- 初始表面数密度 $N_0 = 2.16 \times 10^{9}\ \mathrm{m^{-2}}$
- 吃草面积 $A = 7.47\ \mathrm{m^2}$
- $^{137}$Cs 是 **β 发射体**，半衰期 $t_{1/2} = 30$ 年（衰变为 $^{137}$Ba）
- $N(t) = N_0 e^{-\lambda t}$（放射性衰变方程）

**求**：1 年内摄入的原子总数。

**完整解答**：

**Step 1 — 算衰变常数：**

$$
\lambda = \frac{\ln 2}{t_{1/2}} = \frac{\ln 2}{30} = \frac{0.6931}{30} = 0.0231\ \mathrm{yr^{-1}}
$$

**Step 2 — 建立积分：** 摄入速率 = 面积 × 当时的表面密度：

$$
n = \int_0^{1} A\,N(t)\,dt = \int_0^{1} A\,N_0\,e^{-\lambda t}\,dt
$$

**Step 3 — 积分（用 Q6.3(c) 的结果）：**

$$
n = A N_0 \left[-\frac{1}{\lambda}e^{-\lambda t}\right]_0^{1}
= \frac{A N_0}{\lambda}\left(1 - e^{-\lambda}\right)
$$

**Step 4 — 代数值：**

$$
A N_0 = 7.47 \times 2.16\times10^{9} = 1.6135\times10^{10}
$$

$$
1 - e^{-0.0231} = 1 - 0.97716 = 0.022835
$$

$$
n = 1.6135\times10^{10} \times \frac{0.022835}{0.0231} = 1.6135\times10^{10} \times 0.98853
$$

$$
\boxed{n \approx 1.595 \times 10^{10}\ \text{atoms}}
$$

**答**：一年内羊摄入约 $1.595 \times 10^{10}$ 个 $^{137}$Cs 原子（与解答文件的 $1.595\times10^{10}$ 一致）。

> **解题思路与洞察**：
> 1. **为什么要积分而不是直接乘？** 因为密度 $N(t)$ **随时间衰减**，不是常数。若错误地用 $A N_0 \times 1$ 年 $= 1.614\times10^{10}$，会**高估**。
> 2. **误差有多大？** $1.614$ vs $1.595$，差约 1.2%。因为 30 年半衰期相比 1 年很长，一年内衰变很少 —— 这个"合理性检查"（$\lambda T \ll 1$ 时积分 ≈ 直接相乘）值得记住。
> 3. **单位链**：$\mathrm{m^{-2}} \times \mathrm{m^2} = $ 无量纲个数；再对时间积分并除以 $\lambda$（单位 $\mathrm{yr^{-1}}$）→ 时间单位抵消 → 得到纯数（原子个数）✓
> 4. **地球科学背景**：这是切尔诺贝利后英国（尤其威尔士/坎布里亚高地）对羊肉设限的真实科学依据。$^{137}$Cs 化学性质类似钾，被植物吸收后进入食物链。

---

**Question 6.10：流体静力学方程**

用分离变量法求解

$$
\frac{dP}{dz} = -\frac{Pg}{R_a T},\qquad \rho = \frac{P}{R_a T},\quad R_a = 287\ \mathrm{J\,kg^{-1}K^{-1}}
$$

**完整解答见 §2.9 与 §5.3**，结果：

$$
P(z) = P_0 \exp\!\left(-\frac{gz}{R_a T}\right)
$$

> **这题与 Q6.8 是"同一道题换皮"**：
> | | Q6.8 衰变 | Q6.10 气压 |
> |---|---|---|
> | 变量 | $N$ vs $t$ | $P$ vs $z$ |
> | ODE | $\frac{dN}{dt} = -\lambda N$ | $\frac{dP}{dz} = -\frac{g}{R_aT}P$ |
> | 常数 | $\lambda$ | $\frac{g}{R_a T}$ |
> | 初值 | $N(0) = N_0$ | $P(0) = P_0$ |
> | 解 | $N_0 e^{-\lambda t}$ | $P_0 e^{-gz/(R_aT)}$ |
>
> **识别出这个同构，就等于一次性会做两道题**（也是手册 6.3 节反复强调 "have the same algebraic formulation" 的原因）。

---

### 5.5 Practical 通用解题技巧总结

1. **看到"求某段时间/距离内的总量" → 定积分**，上下限就是题目给的两个端点值。
2. **看到"给了变化率，求量本身" → 积分**；**看到"给了量，求变化多快" → 微分**。
3. **单位是最好的路标**：`m³ s⁻¹ × s = m³`、`mm hr⁻¹ × hr = mm` —— 单位对上了，做法就对了。
4. **先化简为幂形式**：$\sqrt{x} \to x^{1/2}$，$\frac{1}{x^2}\to x^{-2}$，$\frac{1}{\sqrt x}\to x^{-1/2}$。
5. **常数系数先提出积分号**，最后再乘回去。
6. **定积分严格写 $\big[F(x)\big]_a^b = F(b) - F(a)$，括号写全**，尤其 $F(a)$ 为负时。
7. **做完微分回去验算**（practical slide 明确推荐）。
8. **分离变量的三句话固定模板**：divide by [var] → multiply by d[other var] → integrate both sides。
9. **有初值/边界条件就一定要用它定常数**，别把 $c$ 留在答案里。
10. **对数律收尾**：$e^{A + \ln B} = B\,e^{A}$ —— 这是所有指数解最后一步的固定动作。

---

## 六、易错点 / 重点难点

### ★★★ 最高频错误

1. **不定积分漏写 $+d$（或 $+c$）**
   - practical 解答 slide 上专门用红字写着 **"Don't forget the constants in indefinite integrals!"**
   - 讲师本人在课堂上都漏写过一次并当场纠正。
   - **判定规则**：题目**没有**上下限 → 必须写常数；题目**有**上下限 → 不必写。

2. **$\sin$ / $\cos$ 的负号放错**
   - $\displaystyle\int \sin x\,dx = \boxed{-}\cos x + d$（**有负号**）
   - $\displaystyle\int \cos x\,dx = \sin x + d$（**无负号**）
   - 讲师亲口点名这是"唯一需要小心的地方"。
   - **记忆**：负号永远在 **cos** 那边（微分 $\cos\to-\sin$，积分 $\sin\to-\cos$）。

3. **$n = -1$ 时误用幂法则**
   - $\displaystyle\int x^{-1}dx \neq \frac{x^{0}}{0}$（分母为 0，无意义！）
   - 正确：$\displaystyle\int \frac1x dx = \ln x + d$
   - **幂法则的适用条件：$n \neq -1$。**

4. **定积分代入下限时符号出错**
   - 必须写成 $F(b) - F(a)$，并且 **$F(a)$ 整体加括号**。
   - Q6.7 就是典型：$-63.375 - (-86.625) = +23.25$，不加括号就会算成 $-150$。

5. **$e^{k\cdot 0} = 1$ 不是 0**
   - Q6.2(f)：$\left[\frac{e^{3x}}{3}\right]_0^1$ 的下限项是 $\frac13$，**不是 0**。

### ★★ 概念性难点

6. **"定积分 = 面积"必须加"带符号"三个字**
   - Q6.2(c) $\int_{-1}^1 x^3 dx = 0$，但曲线下并非没有面积——$x$ 轴**下方**的部分计为**负**。
   - 若题目真要"几何面积"，需按零点分段、取绝对值再相加。

7. **积分是"认模式"，不是"套算法"**
   - 微分有固定流程；积分要靠**认出被积函数是谁的导数**。
   - 因此**积分表必须熟到不用查**（讲师原话："The more you practice these procedures, the easier it will become to apply them without looking them up."）。

8. **只有和/差能逐项拆开**
   - $\displaystyle\int fg\,dx \neq \left(\int f\,dx\right)\left(\int g\,dx\right)$ —— **绝对不成立**。
   - $\displaystyle\int \frac{f}{g}dx \neq \frac{\int f}{\int g}$ —— **绝对不成立**。
   - 复合函数要等 Week 8 的换元积分。

9. **分离变量时忘记"两边都要有 $d$"**
   - $\frac{1}{N}dN = -\lambda\,dt$ 左边有 $dN$，右边**必须有 $dt$**；不能只在一边写微分。
   - 右边的 $\int dt$ 就是 $\int 1\,dt = t$，别漏掉。

10. **有初值条件却不用**
    - 拿到 $\ln N = -\lambda t + c$ 就停手是**没做完**。题目给了 $t=0, N=N_0$ 就必须代进去解出 $c = \ln N_0$，最后化到 $N = N_0 e^{-\lambda t}$。

11. **积分变量写错 / 漏写 $dx$**
    - Exercise 1(2) 的变量是 $w$，答案里要出现 $w$ 不是 $x$。
    - 写积分时 $dx$ 是**记号的一部分**，不能省。

### ★ 材料本身的坑（复习时注意）

12. **转写里 "definite / indefinite" 口误**（transcript 约 1323–1345 行）：讲师把 definite 说成 indefinite。以 slides 与手册为准。
13. **practical 解答 slide 上流体静力学写 "at $t = 0$"**，应为 **$z = 0$**。
14. **手册把衰变方程称为 "Newton's radioactive equations"** —— 与牛顿无关，是笔误。
15. **Exercise 1(2) 的 $\pm 9w^3$ 符号在题面与答案间不一致**（见 §5.1）。
16. **主手册题号与章号不自洽**：本笔记的题号一律以周版 `Exercises6.md` / `Solutions6.md` 为准。
17. **Q6.5、Q6.6 的题面在 md 版中丢失**（原为图片），需要精确题面时回看对应 PDF。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| **Integration** | 积分 | 微分的逆运算；由变化率还原出量本身 |
| **Integral** | 积分（结果） | 积分运算的结果 |
| **Integrand** | 被积函数 | $\int$ 与 $dx$ 之间的那个函数 |
| **Indefinite integration** | 不定积分 | 无上下限；结果**必须** $+$ 积分常数 |
| **Definite integration** | 定积分 | 有上下限；结果是数值 = $F(b)-F(a)$ |
| **Constant of integration** ($d$ / $c$) | 积分常数 | 因微分会"丢常数"而必须补回；本课手册用 $d$，ODE 推导中常用 $c$ |
| **Limits of integration** | 积分限 | $\int_a^b$ 的下限 $a$ 与上限 $b$ |
| **Area under the curve** | 曲线下面积 | 定积分的几何意义（带符号） |
| **Antiderivative** | 原函数 | 导数等于被积函数的那个函数 $F$ |
| **Fundamental Theorem of Calculus** | 微积分基本定理 | 「求面积」与「求微分的逆」是同一件事（本课不点名但全程在用） |
| **Numerical approximation / integration** | 数值近似 / 数值积分 | 用矩形求和逼近面积；本课只讲原理不做题 |
| **Analytical integration** | 解析积分 | 查表得到精确的原函数；本课主用方法 |
| **Infinitesimal** | 无穷小 | $\Delta x \to 0$ 的极限；$\int$ 是"无穷多个无穷小量的和" |
| **Ordinary Differential Equation (ODE)** | 常微分方程 | 只对**一个**自变量求导的微分方程 |
| **Partial Differential Equation (PDE)** | 偏微分方程 | 涉及多个自变量（Week 10 才碰） |
| **Separation of variables** | 分离变量法 | 把两个变量分到等号两侧再各自积分 |
| **Initial condition** | 初始条件 | 如 $t=0$ 时 $N = N_0$，用来定出积分常数 |
| **Boundary condition** | 边界条件 | 如 $z=0$ 时 $P = P_0$ |
| **Initial value problem** | 初值问题 | 给定初值求 ODE 特解（Week 9 正式讲） |
| **Order (of an ODE)** | （微分方程的）阶 | 微分了几次 |
| **Radioactive decay equation** | 放射性衰变方程 | $\frac{dN}{dt} = -\lambda N$ |
| **Decay constant** ($\lambda$) | 衰变常数 | $\lambda = \ln 2 / t_{1/2}$ |
| **Half-life** ($t_{1/2}$) | 半衰期 | 数目减半所需时间；$^{137}$Cs 为 30 年 |
| **Unstable nuclei** | 不稳定核 | 会发生衰变的原子核 |
| **$\alpha$ / $\beta$ decay** | α / β 衰变 | $^{137}$Cs 是 β 发射体，衰变为 $^{137}$Ba |
| **Surface density** | 表面（数）密度 | 单位面积上的原子数，单位 m⁻² |
| **Hydrostatic equation** | 流体静力学方程 | $\frac{dP}{dz} = -\rho g = -\frac{Pg}{R_aT}$ |
| **Ideal gas law** | 理想气体定律 | 本课用形式 $\rho = P/(R_a T)$ |
| **Specific gas constant** ($R_a$) | 比气体常数 | 干空气 $R_a = 287\ \mathrm{J\,kg^{-1}K^{-1}}$ |
| **Lapse rate** | 温度递减率 | 大气中约 $10\ ^\circ\mathrm{C\,km^{-1}}$ |
| **Newton's law of cooling** | 牛顿冷却定律 | $\frac{dT}{dt} = -\alpha(T - T_s)$ |
| **Flow rate** | 流量 | 单位时间通过的体积，如 mL s⁻¹ |
| **Steady-state** | 稳态 | 一阶导数恒定 ⇔ 二阶导数为 0 |
| **Stationary value / point** | 驻点 | $f'(x)=0$ 的点（Week 4–5） |
| **Saddle point** | 鞍点 | $f''=0$ 且不是极值的驻点 |
| **Newton's Method for Root Finding** | 牛顿求根法 | 求 $f(x)=0$ 的迭代算法（Week 5） |
| **Central differences method** | 中心差分法 | 数值微分方法（Week 1–2），本周作为类比反复引用 |
| **Integration by substitution** | 换元积分法 | Week 8 内容 |
| **Gottfried Wilhelm Leibniz** | 莱布尼茨 | 17 世纪引入 $\int$ 符号 |
| **Maths survival pack** | 数学生存包 | 本课发的公式速查资料，考卷首页也会附同一张公式表 |

---

## 附：本周一页速记（考前 5 分钟版）

**一句话**：积分 = 微分的逆 = 曲线下（带符号）面积。

**核心公式**
$$\int x^n dx = \frac{x^{n+1}}{n+1}+d\ (n\neq-1),\quad \int\frac1x dx=\ln x+d,\quad \int e^{kx}dx=\frac1k e^{kx}+d$$
$$\int\cos x\,dx=\sin x+d,\quad \int\sin x\,dx=-\cos x+d$$
$$\int_a^b f(x)dx=\big[F(x)\big]_a^b=F(b)-F(a)$$

**万能模板**
$$\frac{dy}{dx}=ky \ \Longrightarrow\ y=y_0e^{kx}$$
（衰变 $k=-\lambda$；气压 $k=-g/(R_aT)$）

**三条纪律**：不定积分写 $+d$ ｜ 定积分不写 $+d$ ｜ 做完微分回去验算。
