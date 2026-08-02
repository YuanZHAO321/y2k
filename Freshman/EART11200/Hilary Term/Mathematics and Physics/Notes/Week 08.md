# Week 8 — 换元积分法 (Integration by Substitution)

> 课程：EART11200 *The Natural Scientist's Toolkit* — Mathematics and Physics
> 官方主题表：Week 27 (17/03/2025) — **Integration by Substitution**
> 材料来源：`Lecture/Week 8/Chapter8.md`、`Lecture/Week 8/lecture8.md`、`Lecture/Week 8/EART11200 - 17-Mar-transcript.md`、`Practical/Week 8/Exercises8.md`、`Practical/Week 8/Solutions8.md`、`Practical/Week 8/practical8_soln(1).md`、主手册第 8 章（含选读第 9 章）

---

## 一、本周主题

### 1.1 本周在全课中的位置

本课 Mathematics and Physics 的十周脉络：

| 周 | 主题 | 与本周的关系 |
|---|---|---|
| Week 1 | Calculating Gradients | 梯度 = 导数的直观来源 |
| Week 2 | Introduction to Differentiation | 基本导数表 |
| **Week 3** | **Differentiating Combinations of Functions** | **链式法则 (chain rule) 在此建立 —— 本周直接反推它** |
| Week 4 | Optimisation & Properties of Derivatives | — |
| Week 5 | Second Order Derivatives & Root Finding | — |
| Week 6 | Introduction to Integration | 基本积分表 + 分离变量 (separation of variables) |
| Week 7 | Integration using Newton's Laws | 用牛顿第二定律建 ODE 再积分 |
| **Week 8** | **Integration by Substitution ← 本周** | 让 Week 6 的积分表能处理 **复合函数 (composite function)** |
| Week 9 | Integrating Second Order ODEs | 由 David Topping 教授代课 |
| Week 10 | Vectors and Partial Differentiation | 收尾 + 考试说明 |
| Week 11–12 | Revision: Differentiation / Integration | 复习 |

**一句话定位**：Week 6 给了我们一张「基本积分表」，Week 7 教我们怎么从物理系统建出 ODE 并用分离变量去积分。但一旦被积函数 (integrand) 变成 **函数的函数 (function of a function)**，那张表就直接用不了了。**换元积分法就是把「表用不了的积分」改写成「表用得了的积分」的标准工序**。它在整门课里的地位相当于积分侧的链式法则。

### 1.2 官方 Intended Learning Outcomes（讲义与 practical 幻灯片均列出三条，逐字相同）

1. **Explain** the concept of integration by substitution and its relationship to the **chain rule** in differentiation.
   （能解释换元积分的概念，以及它与微分链式法则的关系。）
2. **Apply** integration by substitution on **indefinite integrals** to solve theoretical and real-world problems.
   （能对不定积分做换元，解决理论题与实际问题。）
3. **Apply** integration by substitution on **definite integrals** to solve theoretical and real-world problems.
   （能对定积分做换元，解决理论题与实际问题。）

注意 ILO 的措辞：**第 2、3 条被拆成两条，正是因为「定积分换元要额外换上下限」这一步是本周的独立考点。**

### 1.3 为什么需要它 —— 讲义给出的引子

我们已经会积分下面这些（Week 6 的表）：

$$\int x^n\,dx=\frac{x^{n+1}}{n+1}+c,\qquad \int e^x dx=e^x+c,\qquad \int \frac{1}{x}dx=\ln(x)+c,\qquad \int\cos x\,dx=\sin x+c$$

但如果题目给的是

$$y=\int (3x+2)^4\,dx$$

表里没有任何一行长这样。括号里 $3x+2$ 本身是一个函数，外面再套一个四次幂——这就是 **函数的函数 (function of a function / composite function)**。

课上老师明确提到了「土办法」以及为什么不用它：

> "yes of course you could just expand that quartic out and then do it in turn but why would you want to add in this unnecessary complication"
> （当然你可以把这个四次式展开再逐项积分，但何必给自己添这种不必要的麻烦。）

而且展开法只对 **整数次幂** 管用；碰到 $\int \sin(7x-3)dx$、$\int \frac{1}{7x+5}dx$、$\int\frac{1}{(3x+4)^2}dx$ 就完全无能为力。所以必须有一个通用的新工具 —— **integration by substitution**。

---

## 二、核心概念

### 2.1 由链式法则反推：换元法到底"从哪来"

这是 ILO 第 1 条要求会讲的东西，也是本节最重要的逻辑。

**回忆 Week 3 的链式法则 (chain rule)**（讲义 slide 9 原样复习了一遍）：
若 $f$ 是 $g$ 的函数，$g$ 又是 $x$ 的函数，则

$$\boxed{\ \frac{df}{dx}=\frac{df}{dg}\times\frac{dg}{dx}\ }$$

课上用的示范：微分 $f(x)=\sin(3x+1)$
- **Step 1** 拆分并代换：令 $g=3x+1$，则 $f=\sin(g)$
- **Step 2** 分别求导：$\dfrac{df}{dg}=\cos(g)$，$\dfrac{dg}{dx}=3$
- **Step 3** 相乘并把 $g$ 换回去：$\dfrac{df}{dx}=\cos(g)\times 3=3\cos(3x+1)$

**现在把这条式子反着读。** 链式法则说：

$$\frac{d}{dx}\Big[F\big(g(x)\big)\Big]=F'\big(g(x)\big)\cdot g'(x)$$

两边对 $x$ 积分，左边的微分与积分互相抵消：

$$\boxed{\ \int F'\big(g(x)\big)\,g'(x)\,dx=F\big(g(x)\big)+c\ }$$

如果记 $u=g(x)$，则 $\dfrac{du}{dx}=g'(x)$，形式上写作 $du=g'(x)\,dx$，上式就变成

$$\int F'(u)\,du=F(u)+c$$

**这就是换元积分法的全部理论内容**：一个"看起来复杂"的、以 $x$ 为变量的积分，可以被改写成一个"看起来简单"的、以 $u$ 为变量的积分。

老师在课上的原话把这层关系说得很直白：

> "essentially integration by substitution is the integration's version of the chain rule in differentiation"
> "we're going to follow a similar process here of coming up with a substitution, integrating, and then put the substitution back in"

**微分与积分的对照表**（自己整理，便于记忆）：

| | 微分 (differentiation) | 积分 (integration) |
|---|---|---|
| 处理复合函数的工具 | 链式法则 chain rule | **换元积分 integration by substitution** |
| 处理乘积的工具 | 乘积法则 product rule | 分部积分 integration by parts（见 §2.9 选读） |
| 操作方向 | 拆开 → 分别求导 → 相乘 → 代回 | 换元 → 积分 → 代回（或换限） |

老师也提醒：换元法比链式法则**步骤更多、更"手摇"**：

> "it's a little bit more involved than the chain rule in differentiation, but integration is always a little bit more hand and more involved than differentiation in general"

### 2.2 换元时到底换了几样东西 —— 本周最核心的认知

学生最容易犯的错，是**只换了函数，忘了换 $dx$**。课上老师专门停下来提问，学生答对了：

> "the problem is this integral is now we're asking you to integrate $u^4$ **with respect to $x$**"

也就是说，如果只写 $\int u^4\,dx$，这是一个**没有意义的混合式**：被积函数用的是新变量 $u$，微元用的却是老变量 $x$。

**因此不定积分换元必须换 2 样东西，定积分换元必须换 3 样东西：**

| | 要换的对象 | 不定积分 | 定积分 |
|---|---|---|---|
| ① | 被积函数中所有的 $x$ → 变成 $u$ | ✅ | ✅ |
| ② | 微元 $dx$ → 变成 $du$ | ✅ | ✅ |
| ③ | 积分上下限 $x=a,\,x=b$ → 变成 $u=g(a),\,u=g(b)$ | — | ✅ |

一句口诀：**换函数、换微元、换上下限（定积分才有第三条）。** 换完之后，整个积分式里**不能再出现任何一个 $x$**。

### 2.3 不定积分换元：官方八步法 (the 8-step recipe)

讲义 slide 12–13、Chapter8.md、practical 解答幻灯片，用的是**完全一致**的八步。以 $y=\int (3x+2)^4 dx$ 为例：

> **Step 1. Write out the integral in its simplest form**（把积分写成最简形式）
> $$y=\int (3x+2)^4\,dx$$
> （本例已是最简，无需化简。）

> **Step 2. Find a new variable $u$ as a function of the old variable $x$**（找一个代换）
> $$u=3x+2\quad\Longrightarrow\quad y=\int u^4\,dx$$
> 此时式子**还不合法**，因为还有 $dx$。

> **Step 3. Rearrange to get $x$ in terms of $u$**（反解出 $x$）
> $$3x=u-2\quad\Longrightarrow\quad x=\frac{1}{3}u-\frac{2}{3}$$

> **Step 4. Differentiate with respect to the new variable $u$**（对 $u$ 求导）
> $$\frac{dx}{du}=\frac{1}{3}$$
> 课上老师现场口误后自我纠正过一次（"$du/dx$ — sorry, wrong way around — $dx/du$"）：**本课的标准写法是 $\dfrac{dx}{du}$，不是 $\dfrac{du}{dx}$**，因为下一步要直接读出 $dx$。
> 求导细节：$-\frac{2}{3}$ 是常数，导数为 0；$\frac{1}{3}u$ 是线性项，导数为 $\frac13$。

> **Step 5. Get an expression for $dx$**（解出 $dx$）
> $$dx=\frac{1}{3}\,du$$

> **Step 6. Make the substitution in the original integral**（代回原积分）
> $$y=\int u^4\cdot\frac{1}{3}du=\frac{1}{3}\int u^4\,du$$
> 常数 $\frac13$ 提到积分号外面。**注意此时式中已无 $x$。**

> **Step 7. Integrate as usual**（照常积分，用 Week 6 的表）
> $$\frac{1}{3}\int u^4\,du=\frac{1}{3}\cdot\frac{u^5}{5}+c=\frac{1}{15}u^5+c$$
> 老师提醒："remember to add in a constant at the end like we always do when we do **indefinite** integration"。

> **Step 8. Substitute the original expression back in**（把 $u$ 换回 $x$）
> $$\boxed{\,y=\frac{1}{15}(3x+2)^5+d\,}$$

**验算方法**（手册反复强调，每道解答后面都写着这句）：
> "You can differentiate using the chain rule to verify that this works."

对答案求导：$\frac{d}{dx}\left[\frac{1}{15}(3x+2)^5\right]=\frac{1}{15}\cdot 5(3x+2)^4\cdot 3=(3x+2)^4$ ✓ 回到被积函数，正确。
**这是本周最好用的自查手段，考试时务必用。**

### 2.4 定积分换元：官方八步法（第 6 步换成"换上下限"）

讲义 slide 17–18 的定积分版本，与不定积分版**只有两处差别**：

- 第 6 步变成 **Find the new limits of the integral**（求新的上下限）；
- 第 8 步 **不需要把 $u$ 换回 $x$**，直接用新上下限算出数值即可，**也不需要加常数 $c$**。

以 $y=\displaystyle\int_{-1}^{1}(3x+2)^4dx$ 为例（讲义 slide 18 用的正是这题）：

1. $y=\displaystyle\int_{-1}^{1}(3x+2)^4dx$
2. $u=3x+2$
3. $x=\frac13 u-\frac23$
4. $\dfrac{dx}{du}=\dfrac13$
5. $dx=\dfrac13 du$
6. **换限**：
   - When $x=-1$: $u=3\times(-1)+2=-1$
   - When $x=1$: $u=3\times 1+2=5$
7. 代换：$y=\dfrac13\displaystyle\int_{-1}^{5}u^4\,du$
8. 积分求值：
   $$y=\frac13\left[\frac{u^5}{5}\right]_{-1}^{5}=\frac{1}{15}\Big[5^5-(-1)^5\Big]=\frac{1}{15}(3125+1)=\frac{3126}{15}=208.4$$

> ⚠️ **勘误**：课堂上老师口算成了 $\frac{3124}{15}$（转写稿原文 "you end up with 3124 divided by 15"）。正确值是 $5^5-(-1)^5=3125-(-1)=\mathbf{3126}$，故 $\frac{3126}{15}=208.4$。**这是转写稿中的一处算术错误，复习时以 3126/15 为准。**

**换限的本质**：新上下限就是「把老上下限的 $x$ 值代进代换式 $u=g(x)$ 算出的 $u$ 值」。老师的原话：

> "what that just involves is saying well, what is $u$ when $x$ is at a certain value"
> "when $x$ is between $-1$ and $1$, well $u$ is between $-1$ and $5$ under the new variable"

**为什么换了限就不用代回去？** 因为定积分的结果是一个**数**（面积），不是函数。把积分区间从「$x$ 轴上的 $[-1,1]$」翻译成「$u$ 轴上的 $[-1,5]$」以后，两个积分在数值上完全等价，直接算完就是答案。

**通用形式（值得背下来）**：

$$\boxed{\ \int_{x=a}^{x=b} f(x)\,dx=\int_{u=g(a)}^{u=g(b)} f\big(x(u)\big)\,\frac{dx}{du}\,du\ }$$

### 2.5 如何选取代换变量 —— 本周最实用的技能

这是"最难也最实用"的一步。把课程材料里出现的所有线索汇总成一套可操作的判断规则：

**规则 0（本课的黄金法则，老师明说是考试提示）：
看到函数里面套着 $ax+b$，就令 $u=ax+b$。**

> "generally as a rule, when you have something that says $ax+b$ inside a function, you will use that as the substitution. **So this may be a hint for the exam** ... don't overcomplicate it for yourself."
> "generally, in all the questions you will see, $ax+b$ will be your substitution."

这条规则覆盖了本周**全部 Practical 习题**和**全部课堂例题**。手册 §8.2 也写了同一句：
> "When the integral contains a factor like $ax+b$, substituting $u=ax+b$ often simplifies the problem."

**具体识别方法 —— "$u$ 取谁"检查清单：**

| 被积函数长相 | 取 $u$ = | 例子 |
|---|---|---|
| $(\,\square\,)^n$ 括号带幂次 | 括号里的 $\square$ | $\int(5x+6)^3dx\Rightarrow u=5x+6$ |
| $\sin(\square),\ \cos(\square)$ | 三角函数的**幅角** | $\int\sin(7x-3)dx\Rightarrow u=7x-3$ |
| $e^{\square}$ | **指数** | $\int e^{5x+2}dx\Rightarrow u=5x+2$ |
| $\dfrac{1}{\square}$ | **分母** | $\int\frac{1}{7x+5}dx\Rightarrow u=7x+5$ |
| $\dfrac{1}{(\square)^2}$ | **分母的底** | $\int\frac{1}{(3x+4)^2}dx\Rightarrow u=3x+4$ |
| 物理题里的复合表达式 | 整个"讨厌的"括号 | $\int\frac{dz}{T_s-0.01z}\Rightarrow u=T_s-0.01z$ |
| 分母是 $(v+w)^2$、分子有 $v$ | $z=v+w$（**平移代换**，让分母变单项） | Q8.9 |

**统一的判断口诀（背这一句就够）**：
> **找出"最里层的那个函数"（the function inside the function），令它等于 $u$。**

老师现场演示时就是这么念的：
> "the first function is cos, and the function inside cos is $3x+4$ ... just use whatever's inside that function"

**选对了的判据**：代换完成后，积分式中 **不再含有任何 $x$**，且剩下的 $\int(\cdots)du$ 能在 Week 6 的积分表里直接查到。**做不到这两点，说明 $u$ 选错了。**

### 2.6 线性代换的"快捷公式"（自己总结，做题提速用）

本周所有代换都是线性的 $u=ax+b$，此时 $\dfrac{dx}{du}=\dfrac1a$，即 $dx=\dfrac{du}{a}$。于是可以直接得到一条**万能捷径**：

$$\boxed{\ \int f(ax+b)\,dx=\frac{1}{a}F(ax+b)+c\quad\text{其中 }F'=f\ }$$

**"$a$ 是几，前面就乘 $\frac1a$"**。由此立刻得到：

$$\int (ax+b)^n dx=\frac{(ax+b)^{n+1}}{a(n+1)}+c\quad(n\neq -1)$$
$$\int \sin(ax+b)dx=-\frac{1}{a}\cos(ax+b)+c\qquad \int \cos(ax+b)dx=\frac{1}{a}\sin(ax+b)+c$$
$$\int e^{ax+b}dx=\frac{1}{a}e^{ax+b}+c\qquad \int \frac{1}{ax+b}dx=\frac{1}{a}\ln|ax+b|+c$$

> ⚠️ **考试仍应写完整八步**（题干明确要求 "Using integration by substitution"）。这条捷径用于**检查答案**和**节省时间**，不能直接当作解答过程写上去。
> 其中第一条正是 **Question 8.6** 要求证明的结论（见 §5.3）。

### 2.7 为什么这门课需要它 —— 地球科学中的物理意义

老师在课末专门解释了"why does this matter"，这一段是本课"面向自然科学家"定位的核心：

> "if the physics of the system requires another formulation, a substitution might be needed."
> "when you start looking at ODEs and you start **relaxing certain assumptions**, you're going to start coming up with much harder functions that you need to integrate."

**关键洞见：放宽一个物理假设 = 让积分变难一级。**

以 **静力学方程 (hydrostatic equation)** 为例：

- **Week 6 的版本（假设温度恒定）**：
  $$\frac{dP}{dz}=-\frac{g}{R_a T}P \quad\Longrightarrow\quad \int\frac{1}{P}dP=-\frac{g}{R_aT}\int dz$$
  右边是常数积分，**用基本积分表就能做**，得到指数衰减解
  $$P(z)=P_0\exp\!\left(-\frac{g}{R_aT}z\right)$$

- **Week 8 的版本（放宽假设：温度随高度线性下降）**：
  实际大气温度以约 $10\,^\circ\mathrm{C\,km^{-1}}$ 的速率随高度递减，即 $T(z)=T_{surface}-0.01z$（单位 K，$z$ 单位 m）。于是
  $$\frac{dP}{dz}=-\frac{g}{R_a\big(T_{surface}-0.01z\big)}P$$
  分离变量后
  $$\int\frac{1}{P}\,dP=-\frac{g}{R_a}\int\frac{1}{T_{surface}-0.01z}\,dz$$
  **右边这个积分基本表里没有 —— 必须换元。** 这正是 Question 8.7 / 8.8。

老师还顺带把这个思路推向了后续课程：

> "they may become so complicated that you need to do some **numerical approximations**, which is probably what you will have seen with David Topping in your computer programming class"

即：解析积分（本课）→ 换元等技巧（本周）→ 数值方法（编程课）是一条连续的能力链条。

### 2.8 适用条件与不适用的场合

**换元法适用于：**
- 被积函数是**复合函数** $f(g(x))$，且 $g$ 是简单函数（本课几乎总是 $ax+b$）；
- 被积函数中同时出现 $g(x)$ 与 $g'(x)$（相差一个常数因子也行）；
- 分离变量后出现「1/(线性表达式)」型的物理积分。

**换元法（本周形式）帮不上忙的场合：**
- 被积函数是**两个函数的乘积**且互不相关，如 $\int x e^x dx$ —— 需要 **分部积分 (integration by parts)**，见下面的选读小节；
- 代换后仍留有 $x$ 且无法消掉 —— 说明代换选错，或此题需要别的技巧；
- 被积函数根本没有初等原函数（如 $\int e^{-x^2}dx$）—— 只能数值积分。

---

### 📎 选读：Integration by Parts（非考纲，课程未讲授）

> **说明**：主手册第 9 章 *Integration by Parts* **在本课程中从未被讲授**。官方十周主题表不含此项，全部 12 份课堂逐字稿与两份复习幻灯片中**零次提及** "integration by parts"，该章在手册中的习题与解答本身也是空的。它是手册里的遗留章节，此处仅因内容承接第 8 章而附带介绍，**篇幅从简，不属于考试范围**。

**它解决什么问题**：换元法对付**函数的函数**；分部积分对付**函数的乘积 (products of functions)**，例如 $\int x\,e^{x}\,dx$ —— 这里 $x$ 和 $e^x$ 是两个毫不相关的函数相乘，无论怎么代换都消不掉。

**公式怎么来的 —— 由乘积法则 (product rule) 反推**（手册 §9.2 的推导）：
乘积法则说

$$\frac{d}{dx}\big[u(x)v(x)\big]=u\frac{dv}{dx}+v\frac{du}{dx}$$

两边对 $x$ 积分：

$$u v=\int u\frac{dv}{dx}dx+\int v\frac{du}{dx}dx$$

移项即得 **分部积分公式**：

$$\boxed{\ \int u\,\frac{dv}{dx}\,dx=uv-\int v\,\frac{du}{dx}\,dx\ }$$

（定积分版：$\displaystyle\int_a^b u\frac{dv}{dx}dx=\Big[uv\Big]_a^b-\int_a^b v\frac{du}{dx}dx$）

手册对这个公式的评语：
> "It may look counterintuitive, as this would involve splitting the function, integrating one part and differentiating another, but it does indeed work!"

**典型用法（手册六步）**：
1. 把积分写成最简形式；
2. 指定 $u$ 并求 $\dfrac{du}{dx}$ —— **选那个"求导后会变简单"的因子**（"select the term that simplifies upon differentiation"）；
3. 剩下的部分记作 $\dfrac{dv}{dx}$，积分得到 $v$；
4. 代入公式；
5. 把剩下的 $\int v\frac{du}{dx}dx$ 积出来；
6. 化简。

**示范** $\int x e^x dx$：取 $u=x$（求导变成 1，简化了），$\frac{dv}{dx}=e^x\Rightarrow v=e^x$。于是

$$\int x e^x dx = x e^x-\int e^x\cdot 1\,dx = x e^x-e^x+c=e^x(x-1)+c$$

**与本周正课的关系**：两者是"微分两大法则的镜像"——链式法则↔换元积分，乘积法则↔分部积分。理解这层对称性即可，本课考试不会考。

---

## 三、公式与图表

### 3.1 基本积分表（Week 6 建立，本周反复使用；**考试会提供**）

讲义 slide 2 与 slide 7 都完整给出这张表；老师明确说过这张表在考卷上会给：

> "most of these laws will be on your exam paper, they will be given to you ... The equation table in the exam is also in the handbook that I gave you, it's right at the end."
> （即主手册第 14 章 *Provided Equations in the Exam*。）

| 导数 $\dfrac{dy}{dx}$ | 积分 $y$ |
|---|---|
| $0$ | $d$ |
| constant | $\text{constant}\times x+d$ |
| $x$ | $\dfrac{x^2}{2}+d$ |
| $x^n$ | $\dfrac{x^{n+1}}{n+1}+d$ |
| $ax^n$ | $\dfrac{ax^{n+1}}{n+1}+d$ |
| $e^x$ | $e^x+d$ |
| $ke^{kx}$ | $e^{kx}+d$ |
| $\dfrac{1}{x}$ | $\ln(x)+d$ |
| $\cos(x)$ | $\sin(x)+d$ |
| $\sin(x)$ | $-\cos(x)+d$ |

**配套的两条基本性质**（讲义 slide 7）：
- **和的积分 = 积分的和**：$\dfrac{dy}{dx}=u(x)+v(x)\ \Longrightarrow\ y=\displaystyle\int u(x)dx+\int v(x)dx$
- 常数因子可提到积分号外。

### 3.2 微分导数表（供第 8 步验算用，讲义 slide 9 复习）

| 函数 $y=f(x)$ | 导数 $\dfrac{dy}{dx}$ |
|---|---|
| constant | $0$ |
| $x$ | $1$ |
| $x^n$ | $nx^{n-1}$ |
| $e^x$ | $e^x$ |
| $e^{kx}$ | $ke^{kx}$ |
| $e^{f(x)}$ | $\dfrac{df}{dx}e^{f(x)}$ |
| $\ln(x)$ | $\dfrac{1}{x}$ |
| $\sin(x)$ | $\cos(x)$ |
| $\cos(x)$ | $-\sin(x)$ |

### 3.3 本周必须记牢的三个式子

$$\text{链式法则：}\quad \frac{df}{dx}=\frac{df}{dg}\times\frac{dg}{dx}$$

$$\text{换元（不定）：}\quad \int f(x)\,dx=\int f\big(x(u)\big)\frac{dx}{du}\,du,\qquad \text{末尾必须代回 }u=g(x)\text{ 且加 }+c$$

$$\text{换元（定）：}\quad \int_{x=a}^{x=b} f(x)\,dx=\int_{u=g(a)}^{u=g(b)} f\big(x(u)\big)\frac{dx}{du}\,du,\qquad \text{不代回、不加 }c$$

### 3.4 两个流程图（文字版，考试可默画）

```
【不定积分 · 八步】
① 化简          y = ∫ f(x) dx
② 定代换        u = g(x)   ← 取"函数里面的那个函数"，通常是 ax+b
③ 反解 x        x = h(u)
④ 求 dx/du      dx/du = h'(u)
⑤ 解出 dx       dx = h'(u) du
⑥ 整体代入      y = ∫ f(h(u)) h'(u) du     ← 检查：式中还有 x 吗？有就错了
⑦ 查表积分      = F(u) + c
⑧ 代回          = F(g(x)) + c              ← 用链式法则求导验算
```

```
【定积分 · 八步】
①②③④⑤ 同上
⑥ 换上下限      x = a → u = g(a)
                x = b → u = g(b)
⑦ 整体代入      y = ∫_{g(a)}^{g(b)} f(h(u)) h'(u) du
⑧ 求值          = [F(u)]_{g(a)}^{g(b)} = F(g(b)) − F(g(a))
                 ← 不代回 x，不加常数 c
```

### 3.5 关于图表判读

本周材料**没有出现需要判读的图像**（无函数图像、无散点图、无地质剖面图）。讲义中的"图片"全部是被 PDF 转换工具截断的公式与表格，其内容已在上文以 LaTeX 完整还原。若需核对原始排版，可回看 `lecture8.pdf` 与 `Solutions8.pdf`。

---

## 四、课堂补充

本节记录 **只在 17-Mar 课堂转写稿里出现、讲义与手册中没有** 的内容。

### 4.1 课程行政安排（老师用了整整开头五分钟讲，考试相关，务必留意）

- **本周 (17/03)**：Integration by Substitution（本节课）。
- **下周 (24/03)**：老师本人不在，由 **Professor David Topping** 代课，讲 **integrating second-order differential equations**。老师连说三次"make sure you come next week"，强调有"really interesting techniques"。
- **再下周（31 号那一周）**：**上课时间从周一改为周五 12:00**，地点改到 **Samuel Alexander Building**。老师反复提醒不要走错时间地点。这节课内容是 **vectors and partial differentiation**（模块收尾），**并且会讲考试要求**：
  - 会说明 "what the expectations of the exam will be"；
  - 会有 **Q&A 环节**，可以当场问考试相关问题；
  - 老师说 "I may give a few hints about the exam. I will make sure the microphone is off so that those hints aren't recorded." —— **即：考试提示不会进录音，只有到场才能听到。**
- **往年真题**：该节课之后会**发布去年的 past paper**，这样复活节假期有三周时间做。老师说今年的卷子已经定稿签字（"I signed off your exam this morning, it's set in stone now"），且 **"very similar in principle to the one I set last year"** —— 去年真题的参考价值极高。
- **复活节后**：两周复习课（Revision: Differentiation / Revision: Integration），随后即考试周。考试**具体日期当时未知**。

### 4.2 对 Week 6–7 的口头回顾（把整条积分线索串了起来）

- **为什么要积分**：老师举了一个讲义上没有的例子 —— 如果给你 $\frac{dy}{dx}$ 表示"水箱里水的变化率"，那么积分它就告诉你"这段时间水箱总体积变了多少"。**积分 = 求曲线下面积 = 由变化率还原总量。**
- **牛顿第二定律的四种 ODE 形式**（Week 7 内容，老师完整复述了一遍，说明它们会一直用下去）：

| 形式 | 联系的两个量 | 何时用 |
|---|---|---|
| $F=ma$ | 力 ↔ 加速度 | 只关心力与加速度 |
| $F=m\dfrac{dv}{dt}$ | 速度 ↔ 时间 | 想知道速度怎么随时间变 |
| $F=m\dfrac{d^2x}{dt^2}$ | 位移 ↔ 时间 | 想知道位置怎么随时间变 |
| $F=mv\dfrac{dv}{dx}$ | 速度 ↔ 位移 | **想知道"跑多远速度降到多少"（Q8.9 用的就是这个）** |

  老师的总结："we're able to build up many different types of differential equations and then use integration to solve them."
- **微分与积分互为逆运算**："we're just looking at differentiation and integration as opposites of each other."

### 4.3 课堂互动与口头强调（讲义上没有的措辞）

- **师生问答**：老师写出 $\int u^4\,dx$ 后问 "is there a problem with this integral?"，有学生答出问题所在（还剩 $dx$ 没换）。这说明**这个点是本周的核心考点**。
- **"hand cranking"（手摇曲柄）**：老师三次用这个比喻形容换元法 —— 它是**极其公式化、机械化**的流程，不需要灵感，照步骤摇就行：
  > "it's a very formulaic, methodological thing, you just kind of hand crank it"
- **熟练度靠练**："hopefully you start doing this over and over and over again"；"the more you practice these procedures, the easier it will become to apply them without looking them up"（讲义 slide 2 同义）。
- **Maths survival pack**：老师提到 "Use your math's survival pack when needed!"（讲义 slide 2），指手册末尾的公式速查资料。
- **考试提示（明说的那句）**：$ax+b$ 就是代换 —— "**this may be a hint for the exam**"。

### 4.4 课堂完整演算的三个例子（讲义只有骨架，转写稿有全过程）

**课堂例 A（不定，多项式）** $y=\int (3x+2)^4dx$
$u=3x+2\Rightarrow x=\frac13u-\frac23\Rightarrow \frac{dx}{du}=\frac13\Rightarrow dx=\frac13du$
$$y=\frac13\int u^4du=\frac13\cdot\frac{u^5}{5}+d=\frac{1}{15}(3x+2)^5+d$$

**课堂例 B（不定，三角）** $y=\int\cos(3x+4)dx$
$u=3x+4\Rightarrow x=\frac13u-\frac43\Rightarrow\frac{dx}{du}=\frac13\Rightarrow dx=\frac13du$
$$y=\frac13\int\cos u\,du=\frac13\sin u+c=\boxed{\frac13\sin(3x+4)+c}$$
> ⚠️ 转写稿此处老师口误："cos integrates to minus cos, integrates to sine" —— 前半句是口误，立刻自我更正。**正确：$\int\cos u\,du=\sin u+c$；$\int\sin u\,du=-\cos u+c$。**

**课堂例 C（定，对数型）** $y=\displaystyle\int_{-9}^{1}\frac{1}{x+10}dx$
$u=x+10\Rightarrow x=u-10\Rightarrow\frac{dx}{du}=1\Rightarrow dx=du$（老师特别说这题"makes our life easier because we don't have to have any fractions in there"）
换限：$x=-9\Rightarrow u=1$；$x=1\Rightarrow u=11$
$$y=\int_{1}^{11}\frac{1}{u}du=\Big[\ln u\Big]_1^{11}=\ln 11-\ln 1=\ln 11=2.398$$
（$\ln 1=0$，所以第二项直接消掉。）

### 4.5 课堂现场推的静力学方程（本周物理主线，讲义 slide 21 只给了一个截图）

老师板书的完整过程：

$$\frac{dP}{dz}=-\frac{g}{R_a\big(T_{surface}-0.01z\big)}\,P$$

分离变量 (separation of variables)：

$$\frac{1}{P}\,dP=-\frac{g}{R_a}\cdot\frac{1}{T_{surface}-0.01z}\,dz$$

两边加积分号：

$$\int\frac{1}{P}\,dP=-\frac{g}{R_a}\int\frac{1}{T_{surface}-0.01z}\,dz$$

老师的点评（本周最重要的一句物理洞见）：
> "automatically, by relaxing one assumption — which is to say that temperature isn't constant in this hydrostatic equation — it becomes a much more complicated thing to integrate."

**右边这个积分就必须用换元法**（令 $u=T_{surface}-0.01z$），这正是 Practical 的 Q8.7 与 Q8.8。

---

## 五、Practical 要点

### 5.1 Practical 的目的与结构

本周 Practical（`practical8_soln(1).md`，10 页幻灯片）与 Lecture 共用同一套 ILO，**目的是把八步法练成肌肉记忆**：只安排了 **2 道课堂练习**，一道不定、一道定积分，**逐步骤对照八步模板**，刻意不追求题量。课后另有手册的 Q8.1–Q8.9 共 9 组题（`Exercises8.md`）。

老师在课末说："we're going to head over to Nancy Rothwell now for the practical ... loads of different exercises that we have"（practical 在 Nancy Rothwell Building 进行）。

### 5.2 Practical 课堂两题（完整解答）

#### **Exercise 1（不定）**：$\displaystyle\int\frac{1}{(3x+4)^2}dx$

这题是**幂函数伪装成分数**的经典陷阱题。

1. 化简：先改写成幂的形式 —— $\displaystyle\int (3x+4)^{-2}dx$
2. 代换：$u=3x+4$
3. 反解：$x=\dfrac{u-4}{3}=\dfrac13 u-\dfrac43$
4. 求导：$\dfrac{dx}{du}=\dfrac13$
5. 解 $dx$：$dx=\dfrac13 du$
6. 代入：$\displaystyle\int u^{-2}\cdot\frac13 du=\frac13\int u^{-2}du$
7. 积分：$\dfrac13\cdot\dfrac{u^{-1}}{-1}+c=-\dfrac{1}{3u}+c$
8. 代回：
$$\boxed{\ -\frac{1}{3(3x+4)}+c\ }$$

**验算**：$\dfrac{d}{dx}\left[-\dfrac13(3x+4)^{-1}\right]=-\dfrac13\cdot(-1)(3x+4)^{-2}\cdot 3=(3x+4)^{-2}$ ✓

> ⚠️ **本题最大的坑**：看到分数就往 $\ln$ 上想，写成 $\frac13\ln(3x+4)^2$ —— **大错**。只有 $\int\frac{1}{u}du$（分母**一次方**）才给 $\ln$；$\int\frac{1}{u^2}du=\int u^{-2}du=-\frac1u$ 走的是幂法则。

#### **Exercise 2（定）**：$\displaystyle\int_{0}^{\pi/2}\sin(2x+1)\,dx$

1. 化简：已是最简
2. 代换：$u=2x+1$
3. 反解：$x=\dfrac{u-1}{2}=\dfrac12 u-\dfrac12$
4. 求导：$\dfrac{dx}{du}=\dfrac12$
5. 解 $dx$：$dx=\dfrac12 du$
6. **换限**：$x=0\Rightarrow u=2(0)+1=1$；$x=\dfrac{\pi}{2}\Rightarrow u=2\cdot\dfrac{\pi}{2}+1=\pi+1\approx 4.1416$
7. 代入：$\displaystyle\frac12\int_{1}^{\pi+1}\sin u\,du$
8. 求值：
$$\frac12\Big[-\cos u\Big]_1^{\pi+1}=-\frac12\Big[\cos(\pi+1)-\cos(1)\Big]$$
利用 $\cos(\pi+\theta)=-\cos\theta$，得 $\cos(\pi+1)=-\cos(1)$：
$$=-\frac12\big[-\cos 1-\cos 1\big]=-\frac12\big(-2\cos 1\big)=\boxed{\cos(1)\approx 0.5403}$$

（注意 $\cos(1)$ 中的 1 是**弧度**，不是度数。计算器务必在 RAD 模式。）

> 这题就是手册的 **Question 8.5**（解答里写明 "Let's use $u=2x+1$"）。

### 5.3 手册习题 Q8.1–Q8.6（代数题）完整解答梳理

> 说明：Practical 的 `Solutions8.md` 中，公式部分在 PDF→md 转换时全部丢失，只剩"用哪个代换"的文字。下列解答按材料指定的代换逐步补全并核算，可直接用于复习。**题号以周版 `Exercises8.md` 为准。**

#### **Question 8.1（不定积分）**

**(a) $\displaystyle\int 4(5x+6)^3dx$** — 代换 $u=5x+6$
$x=\frac{u-6}{5}\Rightarrow \frac{dx}{du}=\frac15\Rightarrow dx=\frac15du$
$$=\frac45\int u^3du=\frac45\cdot\frac{u^4}{4}+d=\frac{u^4}{5}+d=\boxed{\frac{(5x+6)^4}{5}+d}$$

**(b) $\displaystyle\int (x-2)^3dx$** — 代换 $u=x-2$
$x=u+2\Rightarrow\frac{dx}{du}=1\Rightarrow dx=du$（系数为 1，最省事）
$$=\int u^3du=\frac{u^4}{4}+d=\boxed{\frac{(x-2)^4}{4}+d}$$

**(c) $\displaystyle\int (x+5)^4dx$** — 代换 $u=x+5$，$dx=du$
$$=\int u^4du=\frac{u^5}{5}+d=\boxed{\frac{(x+5)^5}{5}+d}$$

**(d) $\displaystyle\int (1-2x)^7dx$** — 代换 $u=1-2x$
$x=\dfrac{1-u}{2}\Rightarrow\dfrac{dx}{du}=-\dfrac12\Rightarrow dx=-\dfrac12du$ ← **负号！本题唯一的难点**
$$=-\frac12\int u^7du=-\frac12\cdot\frac{u^8}{8}+d=-\frac{u^8}{16}+d=\boxed{-\frac{(1-2x)^8}{16}+d}$$
验算：$\frac{d}{dx}\left[-\frac{1}{16}(1-2x)^8\right]=-\frac{1}{16}\cdot 8(1-2x)^7\cdot(-2)=(1-2x)^7$ ✓

#### **Question 8.2（定积分，续用 8.1 的代换 —— 只需加"换限"一步）**

**(a) $\displaystyle\int_0^1 4(5x+6)^3dx$**，$u=5x+6$：$x=0\Rightarrow u=6$；$x=1\Rightarrow u=11$
$$=\left[\frac{u^4}{5}\right]_6^{11}=\frac{11^4-6^4}{5}=\frac{14641-1296}{5}=\frac{13345}{5}=\boxed{2669}$$

**(b) $\displaystyle\int_0^1 (x-2)^3dx$**，$u=x-2$：$x=0\Rightarrow u=-2$；$x=1\Rightarrow u=-1$
$$=\left[\frac{u^4}{4}\right]_{-2}^{-1}=\frac{(-1)^4-(-2)^4}{4}=\frac{1-16}{4}=\boxed{-\frac{15}{4}=-3.75}$$
（结果为负很正常：在 $0\le x\le 1$ 上 $(x-2)^3<0$，曲线在 $x$ 轴下方。）

**(c) $\displaystyle\int_0^1 (x+5)^4dx$**，$u=x+5$：$x=0\Rightarrow u=5$；$x=1\Rightarrow u=6$
$$=\left[\frac{u^5}{5}\right]_5^{6}=\frac{7776-3125}{5}=\frac{4651}{5}=\boxed{930.2}$$

**(d) $\displaystyle\int_{-1}^{1}(1-2x)^7dx$**，$u=1-2x$：$x=-1\Rightarrow u=3$；$x=1\Rightarrow u=-1$
$$=-\frac12\int_{3}^{-1}u^7du=-\frac{1}{16}\Big[u^8\Big]_3^{-1}=-\frac{1}{16}\big(1-6561\big)=\frac{6560}{16}=\boxed{410}$$
> ⚠️ **注意这里新的"下限" $u=3$ 比"上限" $u=-1$ 大**。这是因为 $u=1-2x$ 是**递减**的代换。**不要私自把上下限对调**（对调必须同时变号），照抄顺序、连同 $dx=-\frac12du$ 的负号一起算，结果自然正确。

#### **Question 8.3（不定积分：三角/指数/对数型）**

**(a) $\displaystyle\int\sin(7x-3)dx$** — $u=7x-3$，$x=\frac{u+3}{7}$，$\frac{dx}{du}=\frac17$，$dx=\frac17du$
$$=\frac17\int\sin u\,du=-\frac17\cos u+d=\boxed{-\frac17\cos(7x-3)+d}$$

**(b) $\displaystyle\int e^{5x+2}dx$** — $u=5x+2$，$dx=\frac15du$
$$=\frac15\int e^u du=\frac15 e^u+d=\boxed{\frac15 e^{5x+2}+d}$$

**(c) $\displaystyle\int\cos(1-x)dx$** — $u=1-x$，$x=1-u$，$\frac{dx}{du}=-1$，$dx=-du$
$$=-\int\cos u\,du=-\sin u+d=\boxed{-\sin(1-x)+d}$$
验算：$\frac{d}{dx}\big[-\sin(1-x)\big]=-\cos(1-x)\cdot(-1)=\cos(1-x)$ ✓

**(d) $\displaystyle\int\frac{1}{7x+5}dx$** — $u=7x+5$，$dx=\frac17du$
$$=\frac17\int\frac{1}{u}du=\frac17\ln|u|+d=\boxed{\frac17\ln|7x+5|+d}$$

#### **Question 8.4（定积分，续用 8.3 的代换）**
> 全部为弧度制。

**(a) $\displaystyle\int_0^{\pi/2}\sin(7x-3)dx$**，$u=7x-3$：$x=0\Rightarrow u=-3$；$x=\frac\pi2\Rightarrow u=\frac{7\pi}{2}-3\approx 7.9956$
$$=\frac17\Big[-\cos u\Big]_{-3}^{7.9956}=-\frac17\big[\cos(7.9956)-\cos(-3)\big]$$
$\cos(7.9956)=\cos(7.9956-2\pi)=\cos(1.7124)=-0.1411$；$\cos(-3)=\cos 3=-0.9900$
$$=-\frac17\big[-0.1411+0.9900\big]=-\frac{0.8489}{7}\approx\boxed{-0.121}$$

**(b) $\displaystyle\int_0^{1}e^{5x+2}dx$**，$u=5x+2$：$x=0\Rightarrow u=2$；$x=1\Rightarrow u=7$
$$=\frac15\Big[e^u\Big]_2^{7}=\frac{e^7-e^2}{5}=\frac{1096.63-7.39}{5}\approx\boxed{217.85}$$

**(c) $\displaystyle\int_{-\pi/4}^{\pi/4}\cos(1-x)dx$**，$u=1-x$：$x=-\frac\pi4\Rightarrow u=1+\frac\pi4\approx1.7854$；$x=\frac\pi4\Rightarrow u=1-\frac\pi4\approx0.2146$
$$=\Big[-\sin(1-x)\Big]_{-\pi/4}^{\pi/4}=-\sin(0.2146)+\sin(1.7854)=-0.2130+0.9771\approx\boxed{0.764}$$

**(d) $\displaystyle\int_0^{1}\frac{1}{7x+5}dx$**，$u=7x+5$：$x=0\Rightarrow u=5$；$x=1\Rightarrow u=12$
$$=\frac17\Big[\ln u\Big]_5^{12}=\frac17\big(\ln 12-\ln 5\big)=\frac17\ln\!\frac{12}{5}=\frac{0.8755}{7}\approx\boxed{0.125}$$
（用到对数律 $\ln a-\ln b=\ln\frac ab$。）

#### **Question 8.5（定积分）**
即 Practical Exercise 2：$\displaystyle\int_0^{\pi/2}\sin(2x+1)dx=\cos(1)\approx 0.5403$（解答见 §5.2，材料指定代换 $u=2x+1$）。

#### **Question 8.6（一般化：证明幂函数的线性换元公式）**

> 题干：由基本积分表我们知道 $\int x^n dx=\frac{x^{n+1}}{n+1}+d$。用换元积分求出下式的一般表达式：
> $$\frac{dy}{dx}=(ax+b)^n,\qquad a,b,n\ \text{为常数}$$

代换 $u=ax+b\Rightarrow x=\dfrac{u-b}{a}\Rightarrow \dfrac{dx}{du}=\dfrac1a\Rightarrow dx=\dfrac{1}{a}du$

$$y=\int (ax+b)^n dx=\frac{1}{a}\int u^n du=\frac{1}{a}\cdot\frac{u^{n+1}}{n+1}+d$$

代回：

$$\boxed{\ y=\frac{(ax+b)^{n+1}}{a(n+1)}+d\ ,\qquad n\neq -1\ }$$

**这道题是整章的"总纲"**：它证明了 §2.6 的快捷公式，Q8.1、Q8.2、Exercise 1 全都是它的特例。
**限制条件**：$n\neq-1$（否则分母为 0）；$n=-1$ 时结果是 $\frac1a\ln|ax+b|+d$，即 Q8.3(d) 的情形。$a\neq 0$（否则不是复合函数）。

### 5.4 手册习题 Q8.7–Q8.9（Real-world problems）完整解答

#### **Question 8.7 — 特内里费岛上空的云底气压与温度**

**背景与建模**：空气密度由理想气体定律 (ideal gas law) 给出

$$\rho=\frac{P}{R_a T},\qquad R_a=287\ \mathrm{J\,kg^{-1}K^{-1}}\ (\text{干空气气体常数}),\quad g=9.8\ \mathrm{m\,s^{-2}}$$

静力学方程 $\dfrac{dP}{dz}=-\rho g$ 代入后：

$$\frac{dP}{dz}=-\frac{gP}{R_a T}$$

Week 6 中假设 $T$ 恒定，解为 $P(z)=P_0\exp\left(-\frac{g}{R_aT}z\right)$。**本题放宽这个假设**：$T(z)=T_{surface}-0.01z$（对应 $10\,^\circ\mathrm{C\,km^{-1}}$ 的递减率 lapse rate）。于是

$$\frac{dP}{dz}=-\frac{g}{R_a\big(T_{surface}-0.01z\big)}P$$

**已知**：$T_{surface}=290$ K，$P(0)=100000$ Pa，求 $z=1000$ m 处的 $P$ 与 $T$。

**Step 1｜分离变量并加限**（老师提示 "Rearrange this ODE and use integration by substitution"）：

$$\int_{100000}^{P}\frac{1}{P}dP=-\frac{g}{R_a}\int_{0}^{1000}\frac{1}{290-0.01z}\,dz$$

**Step 2｜对右边换元**：$u=290-0.01z$

$$z=\frac{290-u}{0.01}=100(290-u)\quad\Longrightarrow\quad \frac{dz}{du}=-100\quad\Longrightarrow\quad dz=-100\,du$$

**Step 3｜换限**：$z=0\Rightarrow u=290$；$z=1000\Rightarrow u=290-10=280$

**Step 4｜代入并积分**：

$$\Big[\ln P\Big]_{100000}^{P}=-\frac{g}{R_a}\int_{290}^{280}\frac{-100}{u}\,du=\frac{100g}{R_a}\Big[\ln u\Big]_{290}^{280}$$

$$\ln\!\left(\frac{P}{100000}\right)=\frac{100g}{R_a}\ln\!\left(\frac{280}{290}\right)$$

**Step 5｜代数字**：$\dfrac{100\times 9.8}{287}=3.4146$，$\ln\!\frac{280}{290}=\ln(0.96552)=-0.03509$

$$\ln\!\left(\frac{P}{100000}\right)=3.4146\times(-0.03509)=-0.11982$$

$$P=100000\,e^{-0.11982}=100000\times 0.88708$$

$$\boxed{P(1000\ \mathrm m)\approx 88708\ \mathrm{Pa}\ (\approx 887\ \mathrm{hPa}),\qquad T(1000\ \mathrm m)=290-0.01\times1000=280\ \mathrm K}$$

**物理解读**：上升 1 km，气压降约 11.3%，温度降 10 K。这正是云底 (cloud base) 的环境条件 —— 气块上升膨胀降温至露点即凝结成云。

#### **Question 8.8 — 推导带温度递减率的静力学方程通解**

要求证明：解具有 $P=P_0\times(\cdots)$ 的形式，其中 $P_0$ 是 $z=0$ 处的气压。

把 8.7 换成一般上下限：

$$\int_{P_0}^{P}\frac{1}{P}dP=-\frac{g}{R_a}\int_{0}^{z}\frac{1}{T_{surface}-0.01z'}\,dz'$$

代换 $u=T_{surface}-0.01z'$，$dz'=-100\,du$；换限：$z'=0\Rightarrow u=T_{surface}$，$z'=z\Rightarrow u=T_{surface}-0.01z$

$$\ln\!\left(\frac{P}{P_0}\right)=\frac{100g}{R_a}\Big[\ln u\Big]_{T_{surface}}^{T_{surface}-0.01z}=\frac{100g}{R_a}\ln\!\left(\frac{T_{surface}-0.01z}{T_{surface}}\right)$$

两边取指数：

$$\boxed{\ P(z)=P_0\left(\frac{T_{surface}-0.01z}{T_{surface}}\right)^{\frac{100g}{R_a}}=P_0\left(1-\frac{0.01z}{T_{surface}}\right)^{g/(0.01R_a)}\ }$$

其中指数 $\dfrac{100g}{R_a}=\dfrac{100\times 9.8}{287}\approx 3.4146$。

**关键物理对比（值得反复体会）**：

| 假设 | 方程右边 | 需要的积分技巧 | 解的形式 |
|---|---|---|---|
| $T$ 恒定 | $-\frac{g}{R_aT}\int dz$ | 基本积分表 | **指数衰减** $P=P_0e^{-gz/(R_aT)}$ |
| $T$ 线性递减 | $-\frac{g}{R_a}\int\frac{dz}{T_s-0.01z}$ | **换元积分** | **幂律 (power law)** $P=P_0\left(1-\frac{0.01z}{T_s}\right)^{3.41}$ |

**放宽一个假设，解的函数形式就从指数变成幂律** —— 这是本周最深刻的一课。这个幂律形式就是气象学中的 **标准大气压高公式 (barometric formula with constant lapse rate)**。

#### **Question 8.9 — 逆风中球的滑行距离**

**背景**：Week 7 已求过无风时的情形。球在空气中运动的阻力 (drag force) 近似为

$$F_{drag}=\frac{1}{2}\rho\,\pi r^2 v^2$$

（$r$ = 球半径，$v$ = 相对空气的速度，$\rho=1.2\ \mathrm{kg\,m^{-3}}$ 为空气密度，$\pi r^2$ 是球的迎风截面积 cross-sectional area）

**本题新增条件**：风速 $w=10\ \mathrm{m\,s^{-1}}$，**方向与球运动方向相反**。此时球相对空气的速度不是 $v$ 而是 $v+w$，所以

$$F_{drag}=\frac12\rho\pi r^2 (v+w)^2$$

**参数**：$m=1$ kg，$r=0.5$ m，$v_0=10\ \mathrm{m\,s^{-1}}$，求速度降到 $v_1=0.01\ \mathrm{m\,s^{-1}}$ 时走过的距离。

**Step 1｜选牛顿第二定律的正确形式**。题目问的是"**多远**"，联系的是**速度与位移**，所以用第四种形式（见 §4.2 表）：

$$m v\frac{dv}{dx}=-\frac12\rho\pi r^2(v+w)^2$$

（负号：阻力与运动方向相反。）

**Step 2｜分离变量并加限**（$x$ 从 0 到 $x$；$v$ 从 10 到 0.01）：

$$\int_0^x dx=-\frac{2m}{\rho\pi r^2}\int_{10}^{0.01}\frac{v}{(v+10)^2}\,dv$$

**Step 3｜换元**（材料指定用 $z=v+10$，即 $u=v+w$ 的**平移代换**）：

$$z=v+10\ \Longrightarrow\ v=z-10\ \Longrightarrow\ \frac{dv}{dz}=1\ \Longrightarrow\ dv=dz$$

**Step 4｜换限**：$v=10\Rightarrow z=20$；$v=0.01\Rightarrow z=10.01$

**Step 5｜代入并拆项**（这一步是本题技巧核心 —— 平移后分子能拆开）：

$$\int\frac{v}{(v+10)^2}dv=\int\frac{z-10}{z^2}dz=\int\left(\frac{1}{z}-\frac{10}{z^2}\right)dz=\ln z+\frac{10}{z}$$

**Step 6｜求值**：

$$x=-\frac{2m}{\rho\pi r^2}\left[\ln z+\frac{10}{z}\right]_{20}^{10.01}$$

$\left[\ln(10.01)+\frac{10}{10.01}\right]=2.30359+0.99900=3.30259$
$\left[\ln 20+\frac{10}{20}\right]=2.99573+0.50000=3.49573$
差值 $=-0.19315$

$$\frac{2m}{\rho\pi r^2}=\frac{2\times 1}{1.2\times\pi\times 0.25}=\frac{2}{0.94248}=2.1221$$

$$x=-2.1221\times(-0.19315)=\boxed{0.41\ \mathrm m}$$

**结论与物理解读**（手册原话）：
> "the total distance travelled has reduced from **14.66** to **0.41 m** by adding in wind speed, so the wind causes the sphere to slow down much quicker."

对比无风情形：$mv\frac{dv}{dx}=-\frac12\rho\pi r^2v^2\Rightarrow x=\frac{2m}{\rho\pi r^2}\ln\frac{v_0}{v_1}=2.1221\times\ln 1000=14.66$ m。
**加了 10 m/s 逆风，滑行距离缩短约 36 倍** —— 因为阻力正比于**相对速度的平方**，即使球本身几乎停下，$（v+w)^2\approx w^2=100$ 的阻力依然存在。

### 5.5 Practical 解题技巧总结

1. **先看是不是定积分**。有上下限 → 记得第 6 步换限、末尾不代回不加 $c$；没有上下限 → 记得第 8 步代回、加 $+c$。
2. **代换一律取"函数里面的那个函数"**，本课几乎全是 $ax+b$ 型。
3. **系数为 1 的代换最省事**（如 $u=x-2$、$u=x+10$），$dx=du$，不产生分数。
4. **系数为负要小心**（$u=1-2x$、$u=1-x$、$u=T_s-0.01z$），$dx$ 会带负号，且定积分换限后上下限顺序会颠倒 —— 照抄顺序即可。
5. **物理题先分离变量再换元**：几乎所有 real-world 题的套路都是「建 ODE → 分离变量 → 右边那个积分表里没有 → 换元」。
6. **物理题的上下限来自初始条件与目标条件**，两边各自带自己的限（如 $P$ 从 $P_0$ 到 $P$，同时 $z$ 从 0 到 $z$）—— 这样就不必求积分常数 $c$。
7. **每道不定积分做完都用链式法则回验**，代价小、收益大。
8. **三角函数一律弧度制**。

---

## 六、易错点 / 重点难点

### 6.1 概念类

1. **❌ 只换函数不换 $dx$** —— 写出 $\int u^4\,dx$ 这种"半吊子"式子。这是老师课上专门设问的错误。**记住：换完必须一个 $x$ 都不剩。**
2. **❌ 分不清 $\dfrac{du}{dx}$ 与 $\dfrac{dx}{du}$** —— 本课标准流程是先反解 $x=h(u)$，再求 $\dfrac{dx}{du}$，直接得到 $dx=h'(u)du$。老师自己在课上也说反过一次。
3. **❌ 把换元法当"猜"** —— 它是完全机械的八步流程（老师的 "hand cranking"）。慌了就照步骤走。
4. **❌ 以为换元法能对付一切复杂积分** —— 乘积型（$\int xe^xdx$）要用分部积分；有些积分根本没有初等原函数。

### 6.2 不定积分类

5. **❌ 忘记第 8 步代回 $x$** —— 答案里出现 $u$ 是不完整的，必然扣分。
6. **❌ 忘记 $+c$（或 $+d$）** —— 老师每道例题都在强调。
7. **❌ 常数因子处理错** —— $dx=\frac13du$ 中的 $\frac13$ 要提到积分号外，别漏乘。

### 6.3 定积分类

8. **❌ 换了限还把 $u$ 代回 $x$** —— **重复转换**，结果错。换限与代回**二选一**：定积分选换限，不定积分选代回。
9. **❌ 忘记换限，直接把老的 $x$ 上下限套在 $u$ 上** —— 最常见的致命错误。$\int_{-1}^{1}(3x+2)^4dx$ 换元后是 $\frac13\int_{-1}^{5}u^4du$，**不是** $\frac13\int_{-1}^{1}u^4du$。
10. **❌ 定积分末尾还加 $+c$** —— 定积分结果是一个数，不需要常数。
11. **⚠️ 递减代换导致"下限大于上限"** —— 如 Q8.2(d) 的 $u:3\to-1$。这是**正确的**，不要擅自对调；对调必须同时给整个积分变号。

### 6.4 计算类

12. **❌ 把 $\int\frac{1}{u^2}du$ 当成 $\ln$** —— 只有分母是**一次方**时才出 $\ln$。$\int u^{-2}du=-u^{-1}+c$。（Practical Exercise 1 的核心陷阱。）
13. **❌ 三角函数积分符号搞反** —— $\int\sin u\,du=-\cos u+c$（**有负号**），$\int\cos u\,du=\sin u+c$（无负号）。老师课上口误过一次。
14. **❌ 计算器用了角度制** —— 本周全部为弧度，$\cos(1)=0.5403$ 而不是 $0.9998$。
15. **❌ 反解 $x$ 时算错** —— $u=3x+2\Rightarrow x=\frac{u-2}{3}=\frac13u-\frac23$（不是 $\frac{u}{3}-2$）。
16. **⚠️ 转写稿勘误**：$\int_{-1}^{1}(3x+2)^4dx$ 的正确答案是 $\dfrac{3126}{15}=208.4$，课堂口算的 $\dfrac{3124}{15}$ 有误。

### 6.5 物理题类

17. **❌ 牛顿第二定律选错形式** —— 问"多远"（$v$ 与 $x$）就必须用 $F=mv\dfrac{dv}{dx}$，用 $F=m\frac{dv}{dt}$ 会绕远路。
18. **❌ 忽略相对速度** —— Q8.9 里阻力取决于 $v+w$ 而不是 $v$。
19. **❌ 两边积分的限配错** —— 左边是 $P$ 的限，右边是 $z$ 的限，各自独立，不要混。
20. **⚠️ 单位与数量级自查** —— 气压应在 $10^5$ Pa 量级、温度在 $10^2$ K 量级；算出 88708 Pa（合理）而不是 0.887 Pa。

### 6.6 本周的三个"必须会"

- ✅ 能口头说清**换元法与链式法则的关系**（ILO 1，可能是简答题）。
- ✅ 能对任意 $\int f(ax+b)dx$ 走完八步（ILO 2）。
- ✅ 能对定积分正确**换上下限**（ILO 3，独立考点）。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| integration by substitution | 换元积分法 | 本周主题；微分链式法则的逆过程 |
| substitution | 代换 / 换元 | 引入新变量 $u=g(x)$ 的操作 |
| chain rule | 链式法则 | $\frac{df}{dx}=\frac{df}{dg}\cdot\frac{dg}{dx}$（Week 3） |
| product rule | 乘积法则 | 分部积分的来源（Week 3） |
| integrand | 被积函数 | 积分号内的函数 |
| indefinite integral | 不定积分 | 无上下限，结果是函数，需 $+c$ 并代回 $x$ |
| definite integral | 定积分 | 有上下限，结果是数，需换限、不加 $c$ |
| limits (of integration) | 积分上下限 | 定积分换元时必须同步转换 |
| new limits | 新上下限 | 由 $u=g(a)$、$u=g(b)$ 算出 |
| constant of integration | 积分常数 | 记作 $c$ 或 $d$ |
| area under the curve | 曲线下面积 | 定积分的几何意义 |
| function of a function / composite function | 复合函数 / 函数的函数 | 需要换元法的根本原因 |
| products of functions | 函数的乘积 | 需要分部积分（选读） |
| integration by parts | 分部积分法 | 选读，非考纲 |
| separation of variables | 分离变量法 | 把 ODE 两边变量分开再积分（Week 6） |
| ordinary differential equation (ODE) | 常微分方程 | 只含一个自变量的微分方程 |
| initial condition | 初始条件 | 用来定出积分常数 |
| Newton's second law | 牛顿第二定律 | $F=ma$ 及其四种 ODE 形式 |
| drag force | 阻力 | $F_{drag}=\frac12\rho\pi r^2v^2$ |
| hydrostatic equation | 静力学方程 / 流体静力学方程 | $\frac{dP}{dz}=-\rho g$ |
| ideal gas law | 理想气体定律 | 本课用作 $\rho=\frac{P}{R_aT}$ |
| gas constant for air ($R_a$) | 空气气体常数 | $287\ \mathrm{J\,kg^{-1}K^{-1}}$ |
| surface temperature ($T_{surface}$) | 地表温度 | 温度廓线的基准值 |
| lapse rate | 温度递减率 | 本课取 $0.01\ \mathrm{K\,m^{-1}}$（$10\,^\circ$C/km） |
| altitude | 高度 / 海拔 | 变量 $z$ |
| power law | 幂律 | 带递减率的静力学方程解的形式 |
| exponential decay | 指数衰减 | 等温假设下静力学方程解的形式 |
| relaxing an assumption | 放宽假设 | 让模型更真实、积分更难的过程 |
| numerical approximation | 数值近似 | 解析解做不出来时的替代路线 |
| cross-sectional area | 迎风截面积 | 球体为 $\pi r^2$ |
| relative velocity | 相对速度 | Q8.9 中为 $v+w$ |

---

## 附：本周一页速查 (one-page cheat sheet)

**核心恒等式**
$$\int F'\big(g(x)\big)g'(x)\,dx=F\big(g(x)\big)+c\qquad\Longleftrightarrow\qquad u=g(x)$$

**八步法**：①化简 ②定 $u$ ③反解 $x$ ④求 $\frac{dx}{du}$ ⑤解 $dx$ ⑥代入／换限 ⑦积分 ⑧代回／求值

**选 $u$**：取"函数里面的那个函数"，本课几乎总是 $ax+b$（老师明说的考试提示）

**快捷公式**（验算用）：$\displaystyle\int f(ax+b)dx=\frac1a F(ax+b)+c$

**四类标准结果**
$$\int(ax+b)^ndx=\frac{(ax+b)^{n+1}}{a(n+1)}+c\ (n\neq-1)\qquad \int\frac{dx}{ax+b}=\frac1a\ln|ax+b|+c$$
$$\int e^{ax+b}dx=\frac1a e^{ax+b}+c\qquad \int\sin(ax+b)dx=-\frac1a\cos(ax+b)+c$$

**定积分 vs 不定积分**
| | 换限 | 代回 $x$ | 加 $+c$ |
|---|---|---|---|
| 不定 | ✗ | ✅ | ✅ |
| 定 | ✅ | ✗ | ✗ |

**物理主线**：$T$ 恒定 → 指数衰减（查表即可）；$T=T_s-0.01z$ → **换元** → 幂律 $P=P_0\left(1-\frac{0.01z}{T_s}\right)^{100g/R_a}$
