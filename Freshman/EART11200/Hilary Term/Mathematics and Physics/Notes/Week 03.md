# Week 3 — 复合函数的微分：链式法则、乘积法则、商法则 (Differentiating Combinations of Functions)

> 课程：EART11200 The Natural Scientist's Toolkit — Mathematics and Physics
> 讲次日期：2025-02-10（University Week 22 / 课程 Week 3）
> 对应主手册：Chapter 3 *Differentiating combinations of functions*（main(1).md 第 1004–1363 行）
> 本周材料：`Chapter3.md/.pdf`、`lecture3(2).md/.pdf`、`EART11200 - 10-Feb-transcript.md`、`Exercises3.md/.pdf`、`Solutions3(1).md/.pdf`、`practical3_soln(5).md/.pdf`
>
> **说明**：本周 md 转写文件里绝大多数公式是图片，转换后丢失。本笔记的所有公式均已从对应 PDF 中重新抽取核对，可直接当作原始材料使用。

---

## 一、本周主题

### 1.1 本周在整门课中的位置

Hilary Term 的 Mathematics and Physics 共 12 周，脉络是「微分 → 积分 → 复习」：

| 日期 | Univ. Week | 课程 Week | 主题 |
|---|---|---|---|
| 27/01/2025 | 20 | 1 | Calculating Gradients（数值求梯度：前向/后向/中心差分） |
| 03/02/2025 | 21 | 2 | Introduction to Differentiation（导数定义 + 基本求导表） |
| **10/02/2025** | **22** | **3** | **Differentiating Combinations of Functions（本周）** |
| 17/02/2025 | 23 | 4 | Optimisation & Properties of Derivatives |
| 24/02/2025 | 24 | 5 | Second Order Derivatives & Root Finding |
| 03/03/2025 | 25 | 6 | Introduction to Integration |
| 10/03/2025 | 26 | 7 | Integration using Newton's Laws |
| 17/03/2025 | 27 | 8 | Integration by Substitution |
| 24/03/2025 | 28 | 9 | Integrating Second Order ODEs |
| 31/03/2025 | 29 | 10 | Vectors and Partial Differentiation |
| 07/04–21/04 | 30–32 | — | Non-teaching week / Easter break |
| 28/04/2025 | 33 | 11 | Revision: Differentiation |
| 05/05/2025 | 34 | 12 | Revision: Integration（随后进入 Exam Period） |

**逻辑链条**：
- Week 1 用数值方法（差分）**近似**求梯度；
- Week 2 把它极限化为**解析导数** $\dfrac{dy}{dx}=\lim\limits_{\Delta x\to 0}\dfrac{\Delta y}{\Delta x}$，并建立**基本函数求导表**；同时得到「和的导数 = 导数的和」；
- **Week 3（本周）**：把可微分的函数类**大幅扩张**——从「表里能直接查到的单个函数」扩张到「函数的函数 / 函数的乘积 / 函数的商」；
- Week 4–5 转向「导数**能告诉我们什么**」（优化、极值、二阶导、求根）。

讲师在课上明确说明了本周的**范围界定（非常重要的考试信息）**：

> "These are all the types of functions you will see in this course. You will not see any more complicated types of functions. You'll not see more complicated rules of differentiation. These are the three extra types of differentiation rules that you need."

也就是说：**加减（Week 2）+ 链式 + 乘积 + 商（Week 3）= 本课程微分规则的全部**。以后题目只会让单个函数本身更复杂（嵌套更深、混用更多），但**不会再出现新的求导法则**。

### 1.2 Intended Learning Outcomes（讲义与 practical 均逐字重复三遍）

1. Apply the **chain rule** to differentiate composite functions in theoretical and real-world applications.
2. Apply the **product rule** to differentiate products of functions in theoretical and real-world applications.
3. Apply the **quotient rule** to differentiate quotients of functions in theoretical and real-world applications.
   （讲义原文第 (3) 条误写作 "products of functions"，是复制粘贴笔误，实际指 quotients。）

### 1.3 本周核心问题

Week 2 结束在这里：若 $y=u(x)+v(x)$，则

$$\frac{dy}{dx}=\frac{du}{dx}+\frac{dv}{dx}$$

**和的导数 = 导数的和**。那么很自然地要问：乘法、除法、嵌套是不是也这么「各管各」？

本周的教学主线就是：**先证明「想当然的推广」是错的，再给出正确的法则。** 三节的结构完全平行：

1. 提出一个「显然应该这样」的错误猜想；
2. 用一个可以直接验算的简单例子（$x^3\cdot x^6=x^9$，$x^3/x^6=x^{-3}$）把它打死；
3. 给出正确公式；
4. 用「一个能验算的例子」+「一个非用不可的例子」各做一遍。

### 1.4 贯穿全周的「三步法」(the mantra)

讲师反复强调，三条法则**操作流程完全一样**，只是最后套的公式不同：

> **Step 1 — Split（拆）**：把函数拆成两块（链式法则要做**代换 substitution**，乘积/商法则只需**直接拆**）。
> **Step 2 — Differentiate（各自求导）**：拆出来的每块都必须能在**基本求导表**里直接查到。
> **Step 3 — Recombine（用公式合回去并回代）**。

> "We split functions up, differentiate and bring them back together using a formula."

**Step 1 的目标就是让 Step 2 能查表**——这是选择怎么拆的判据。

---

## 二、核心概念

### 2.0 前置：Week 2 的基本求导表（本周每一页 slide 的右侧都挂着它）

| Function $y=f(x)$ | Derivative $\dfrac{dy}{dx}$ |
|---|---|
| constant | $0$ |
| $x$ | $1$ |
| $x^n$ | $nx^{n-1}$ |
| $e^{x}$ | $e^{x}$ |
| $e^{kx}$ | $ke^{kx}$ |
| $e^{f(x)}$ | $\dfrac{df}{dx}e^{f(x)}$ |
| $\ln(x)$ | $\dfrac{1}{x}$ |
| $\sin(x)$ | $\cos(x)$ |
| $\cos(x)$ | $-\sin(x)$ |

⚠️ 注意表里 $e^{kx}\to ke^{kx}$ 和 $e^{f(x)}\to \frac{df}{dx}e^{f(x)}$ **本身就是链式法则的特例**——Week 2 把结论直接发下来了，本周才知道它从哪来。讲师原话：

> "You can always find that the exponential is a derivative of itself multiplied by something else."

这张表在考试中会随卷提供（在 handbook 末尾的公式页 / "maths survival pack"），但讲师强调仍要练熟：

> "Even though they'll be presented to you, I still think you should get used to them over and over and over again... then you won't be flustered in the exam."

---

### 2.1 引子：静水压方程 (Hydrostatic Equation) — 上周留下的地球科学例子

空气密度通过理想气体定律与压强、温度相联系：$\rho=\dfrac{P}{R_\alpha T}$，于是大气压强随高度 $z$ 的变化满足**微分方程**

$$\frac{dP}{dz}=-\frac{g}{R_\alpha T}P$$

其中 $g$（重力加速度）与 $R_\alpha$（比气体常数）是常数。它的解是

$$P(z)=P_0\exp\left(-\frac{g}{R_\alpha T}z\right)$$

$P_0$ 是地表压强。**验证**（用表里 $e^{f(x)}$ 那一行，即链式法则的特例）：

$$\frac{dP}{dz}=P_0\cdot\left(-\frac{g}{R_\alpha T}\right)\exp\left(-\frac{g}{R_\alpha T}z\right)=-\frac{g}{R_\alpha T}\,P$$

回到了原方程 ✓。

**物理意义**：大气压随高度**指数衰减**；其变化率**正比于当前压强本身**——这是「指数衰减过程」的定义性特征（同样的数学结构出现在放射性衰变、水库排水、污染物一阶降解中）。

**为什么放在本周开头**：$\exp\!\left(-\frac{g}{R_\alpha T}z\right)$ 已经是一个**函数的函数**（指数函数套一个线性函数）。上周靠「表里有现成规则」蒙混过去，本周要正面解决。讲师：

> "There's a function within the exponential... but it's just lucky that last week I set you up a rule."

⚠️ **讲义 slide 7 的排版错误**：最后一行印成 `= −P/(R_αT) P`，是排版把两处压在一起了，正确应为 $-\dfrac{g}{R_\alpha T}P$。

---

### 2.2 链式法则 (Chain Rule) — 处理**函数的函数 / 复合函数 (composite functions)**

#### (1) 问题形式

$$y=u(v(x))\qquad\text{或}\qquad f(g(x))$$

典型：$y=\ln(2x)$、$f(x)=\sin(3x+1)$、$y=\sqrt{13x^2-6x+8}$、$y=\exp(x^2+5x+2)$。

#### (2) 为什么不能「照抄外层规则」

以 $y=\ln(2x)$ 为例。表里写着 $\dfrac{d}{dx}\ln(x)=\dfrac1x$，于是很容易**误**写成 $\dfrac{dy}{dx}=\dfrac{1}{2x}$。

但这个特例可以用对数律直接验算：

$$h(x)=\ln(2x)=\ln(2)+\ln(x)\;\Longrightarrow\;\frac{dh}{dx}=0+\frac1x=\frac1x\ne\frac{1}{2x}$$

**所以「把内层原样塞进外层导数公式」是错的**（这里恰好差了一个因子 2，正是内层导数 $\frac{d}{dx}(2x)=2$）。

#### (3) 法则的来由（讲师称之为 "a nice mathematical trick"，很优雅，务必理解）

用「乘以 1」的技巧，其中把 1 写成 $\dfrac{dg}{dg}$：

$$\frac{df}{dx}=\frac{df}{dx}\times 1=\frac{df}{dx}\times\frac{dg}{dg}=\frac{df}{dg}\times\frac{dg}{dx}$$

关键在于：**Leibniz 记号 $\frac{df}{dx}$ 可以（在这个课程的层次上）当成分数来约分**——$dg$ 上下抵消，等式两端一致。讲师：

> "The chain rule allows us to treat derivatives in the same way we can multiply fractions. We **chain** together operations."
> "Can you see how the terms $dg$ cancel out?"

（严格数学上这不是真正的证明——$\frac{df}{dg}$ 不是分数——但作为记忆与理解的框架完全够用，也是本课程要求的水平。）

#### (4) 公式（handbook 式 3.1）

$$\boxed{\;\frac{d}{dx}\big(f(g(x))\big)=\frac{df}{dg}\times\frac{dg}{dx}\;}$$

在 handbook 的解答中一律写成 $u,v$ 的形式：

$$y=u(v(x))\quad\Longrightarrow\quad \frac{dy}{dx}=\frac{du}{dv}\times\frac{dv}{dx}$$

**读法**：先把**外层** $f$ 对**内层整体** $g$ 求导（把 $g$ 当成一个单独的变量），再乘上**内层对 $x$ 的导数**。

#### (5) 适用条件

- 函数能写成「一层套一层」的形式：外层是一个可查表的函数，内层是另一个可查表（或可继续拆）的函数；
- 内层可以是**任何**东西——多项式、三角、指数、根式，甚至又是一个复合函数（此时**重复使用链式法则**）；
- 讲师：$\cos(\sin(x))$、甚至 $\cos(\sin(\exp(x)))$ 都行，"the chain rule always kind of works out — you just take this little bit first and then differentiate as you go along"。

#### (6) 讲义示范：$f(x)=\sin(3x+1)$

- **Step 1（拆 + 代换）**：$f(g)=\sin(g)$，$g(x)=3x+1$
- **Step 2（求导）**：$\dfrac{df}{dg}=\cos(g)$，$\dfrac{dg}{dx}=3$
- **Step 3（合 + 回代）**：$\dfrac{df}{dx}=\cos(g)\times 3=\boxed{3\cos(3x+1)}$

（转写里讲师口头念成 "3 cos 3x" 漏了 +1，**以 slide 为准**：$3\cos(3x+1)$。）

---

### 2.3 乘积法则 (Product Rule) — 处理**函数的乘积**

#### (1) 问题形式

$$y=u(x)\cdot v(x)$$

典型：$f(x)=x\exp(3x)$、$y=(x^2+9)e^{-x}$、$V(t)=(4-t^2)(1+5t^2)$。

#### (2) 反证「导数相乘」的错误猜想（handbook 式 3.2）

错误猜想：$\dfrac{dy}{dx}\overset{?}{=}\dfrac{du}{dx}\times\dfrac{dv}{dx}$

**反例**：取 $u(x)=x^3$，$v(x)=x^6$，则 $y=x^3\cdot x^6=x^9$。

- 正确答案（直接查表）：$\dfrac{dy}{dx}=9x^8$
- 错误猜想给出：$\dfrac{du}{dx}\times\dfrac{dv}{dx}=(3x^2)(6x^5)=18x^7$

$18x^7\ne 9x^8$ ✗。**所以乘法不像加法那样「各管各」。**

（这个反例设计得很妙：$u,v$ 都是幂函数，乘起来还是幂函数，所以正确答案可以独立算出来当作裁判。）

#### (3) 公式（handbook 式 3.3/3.4）

$$\boxed{\;\frac{dy}{dx}=u\,\frac{dv}{dx}+v\,\frac{du}{dx}\;}$$

**记忆法（讲师推荐的 "cross multiplication" 视觉记忆）**：写成两行

```
u        v
du/dx    dv/dx
```

然后**交叉相乘再相加**：$u\times\frac{dv}{dx}\;+\;v\times\frac{du}{dx}$。

> "Take u, keep u as u, differentiate v; then keep v the same and differentiate u."
> "We just pass the derivative through the function, rather than doing the derivatives and multiplying them all together."

**顺序无关**：$u\frac{dv}{dx}+v\frac{du}{dx}=v\frac{du}{dx}+u\frac{dv}{dx}$，两项是加法，谁在前都行。**（这一点和商法则形成关键对比！）**

#### (4) 适用条件与提示

- 两个因子**各自只依赖 $x$**（handbook 强调 "u is a function that varies only with respect to variable x and v is also a function that varies only with respect to x"）；
- 可推广到三个及以上因子（逐次配对使用），但本课程只考两个；
- **拆分通常是显然的**（哪里是乘号就在哪里断开），比链式法则容易。

#### (5) 讲义示范：$f(x)=x\exp(3x)$

- **Step 1（拆）**：$u(x)=x$，$v(x)=\exp(3x)$
- **Step 2（求导）**：$\dfrac{du}{dx}=1$，$\dfrac{dv}{dx}=3\exp(3x)$（用表里 $e^{kx}\to ke^{kx}$）
- **Step 3（合）**：
$$\frac{df}{dx}=x\cdot 3\exp(3x)+\exp(3x)\cdot 1=3x\exp(3x)+\exp(3x)=\boxed{(3x+1)\exp(3x)}$$

**最后一步提取公因子 $\exp(3x)$ 是本课解答的惯用收尾**，务必养成习惯（考试整洁分 + 便于后续令导数为零求根）。

---

### 2.4 商法则 (Quotient Rule) — 处理**函数的商**

讲师明确说这是三条里**最难**的一条（"the most difficult of the three rules"），但仍然完全公式化。

#### (1) 问题形式

$$y=\frac{u(x)}{v(x)}$$

典型：$f(x)=\dfrac{3x+1}{6x-1}$、$y=\dfrac{e^{-x}}{x}$、$h(x)=\dfrac{x-x^2}{1+8x^2}$。

#### (2) 反证「导数相除」的错误猜想（handbook 式 3.5）

错误猜想：$\dfrac{dy}{dx}\overset{?}{=}\dfrac{du/dx}{dv/dx}$

**反例**：$u(x)=x^3$，$v(x)=x^6$，则 $y=\dfrac{x^3}{x^6}=x^{-3}$。

- 正确答案：$\dfrac{dy}{dx}=-3x^{-4}$
- 错误猜想给出：$\dfrac{3x^2}{6x^5}=\dfrac{1}{2x^3}=\dfrac12 x^{-3}$

$\frac12 x^{-3}\ne -3x^{-4}$ ✗（**连正负号都错了**）。

> "Oh god, this is a problem... multiplication and division work very very differently in differentiation. You can't just continue to use the arithmetic you've used before."

#### (3) 公式（handbook 式 3.6）

$$\boxed{\;\frac{dy}{dx}=\frac{v\,\dfrac{du}{dx}-u\,\dfrac{dv}{dx}}{v^{2}}\;}$$

#### (4) 与乘积法则的关系与记忆要点（考试最容易丢分的地方）

分子和乘积法则**长得几乎一样**，但有三处致命差别：

| | Product Rule | Quotient Rule |
|---|---|---|
| 结构 | $u\frac{dv}{dx}+v\frac{du}{dx}$ | $\dfrac{v\frac{du}{dx}-u\frac{dv}{dx}}{v^2}$ |
| 中间符号 | **加号**（顺序无所谓） | **减号**（顺序绝对不能换） |
| 谁在前 | 随意 | 必须 **$v\frac{du}{dx}$ 在前** |
| 分母 | 无 | $v^2$（**分母函数**的平方） |
| $u,v$ 定义 | 两个因子，对称 | $u$=**分子**，$v$=**分母**，不对称 |

讲师的口诀（转写中他说得有点绕，这里整理成正确版本）：

> **「$v\,du$ 减 $u\,dv$，全部除以 $v$ 平方」** —— **v du minus u dv, over v squared.**

英文助记（课外常见）：**"low d-high minus high d-low, over low-low"**（分母×分子的导 − 分子×分母的导，再除以分母平方）。

#### (5) 适用条件与替代方案

- $v(x)\ne 0$（否则原函数就没定义）；
- **不是必须用**：若分子可以逐项除下去（如 $\frac{3x+1}{x^2}=3x^{-1}+x^{-2}$），拆成和式再用幂法则往往更快 —— handbook Example 3.5 就是特意演示这一点；
- 若分母是**单项式**或整个式子能化简，优先化简；只有当「无法简化」时才必须上商法则。

#### (6) 讲义示范：$f(x)=\dfrac{3x+1}{6x-1}$

- **Step 1（拆）**：$u(x)=3x+1$（分子），$v(x)=6x-1$（分母）
- **Step 2（求导）**：$\dfrac{du}{dx}=3$，$\dfrac{dv}{dx}=6$
- **Step 3（合 + 化简）**：
$$\frac{df}{dx}=\frac{3(6x-1)-6(3x+1)}{(6x-1)^2}=\frac{18x-3-18x-6}{(6x-1)^2}=\boxed{\frac{-9}{(6x-1)^2}}$$

**解读**：分子是常数 $-9<0$，分母是平方恒 $>0$（$x\ne 1/6$），所以这个函数在其定义域的每一段上**处处递减**——这就是 Week 4 要用的「用导数读函数行为」。

---

### 2.5 【本周最实用技能】如何判断该用哪条法则

先问：**这个函数是怎么「组装」出来的？** 找出**最外层的那一次运算**。

```
看整个表达式最外层的运算是什么？
│
├─ 加 / 减  →  逐项求导（Week 2），拆成若干独立小题
│
├─ 乘（两块相乘，且不能轻松展开） →  Product Rule
│      · 能展开就展开更快（如 (3x+1)² 直接展开）
│
├─ 除（一个式子除以另一个式子） →  Quotient Rule
│      · 分母是单项式/能逐项拆时，改写成和式更快
│
└─ 「套」（一个函数**整体**塞进另一个函数的括号里） → Chain Rule
       · 判据：括号里不是单独的 x，而是一整个表达式
       · sin(3x+1)、exp(x²+5x+2)、√(x²+25)、(sin x)² 都是
```

**快速自检问句**：

1. 「括号里是不是光秃秃的一个 $x$？」不是 → 需要链式法则。
2. 「有没有两坨东西中间是乘号（或并排写在一起）？」有 → 乘积法则。
3. 「有没有分数线，且上下都含 $x$？」有 → 商法则。（**分母不含 $x$ 就不用！** $\frac{x^2+1}{5}=\frac15(x^2+1)$ 直接求导。）

**常量因子永远不需要乘积法则**：$y=5x^3$ 不用 product rule，常数直接提出来。

### 2.6 【本周最实用技能】多重嵌套时的分解顺序

**原则：从最外层往里剥（outside-in），每剥一层就写下一个因子。**

**例：$Z=(\sin(x^2))^2$（Practical Q3.6a）**

结构：`平方( sin( 平方(x) ) )` —— 三层。

- 最外层：$(\cdot)^2$ → 导数 $2(\cdot)$
- 中间层：$\sin(\cdot)$ → 导数 $\cos(\cdot)$
- 最内层：$x^2$ → 导数 $2x$

$$\frac{dZ}{dx}=\underbrace{2\sin(x^2)}_{\text{外}}\times\underbrace{\cos(x^2)}_{\text{中}}\times\underbrace{2x}_{\text{内}}=4x\sin(x^2)\cos(x^2)$$

（可进一步化为 $2x\sin(2x^2)$，用倍角公式；handbook 答案停在 $4x\sin(x^2)\cos(x^2)$。）

**handbook 推荐的稳妥做法（"lets do it part by part"）**：不要一口气写三层，**先把内两层当成一个整体求导，把结果记下来，再当作「一个已知的 $\frac{dv}{dx}$」代进外层的链式法则**。官方解答就是这么做的：

1. 先算 $\dfrac{d}{dx}\sin(x^2)=2x\cos(x^2)$；
2. 再令 $u(v)=v^2$、$v(x)=\sin(x^2)$，$\dfrac{du}{dv}=2v$、$\dfrac{dv}{dx}=2x\cos(x^2)$；
3. $\dfrac{dZ}{dx}=2\sin(x^2)\times 2x\cos(x^2)$。

**法则混用时的顺序（Q3.4 系列示范）**：先用链式法则算出一个「零件」（如 $\frac{d}{dx}\sqrt{x^2+25}=\frac{x}{\sqrt{x^2+25}}$），**存起来**；后面 (b)(c)(d) 分别把这个零件塞进链式 / 乘积 / 商法则里当 $\frac{dv}{dx}$ 用。这是 handbook Q3.4 的整个设计意图（题干明写 "use the result of (a) in (b)-(e)"）。

---

## 三、公式与图表

### 3.1 三大法则速查

| 法则 | 何时用 | 公式 | 拆分方式 |
|---|---|---|---|
| **Chain rule 链式法则** | $y=u(v(x))$ 复合/嵌套 | $\dfrac{dy}{dx}=\dfrac{du}{dv}\times\dfrac{dv}{dx}$ | 代换：内层整体设为新变量 |
| **Product rule 乘积法则** | $y=u(x)v(x)$ | $\dfrac{dy}{dx}=u\dfrac{dv}{dx}+v\dfrac{du}{dx}$ | 在乘号处直接断开 |
| **Quotient rule 商法则** | $y=\dfrac{u(x)}{v(x)}$ | $\dfrac{dy}{dx}=\dfrac{v\frac{du}{dx}-u\frac{dv}{dx}}{v^2}$ | $u$=分子，$v$=分母 |
| （Week 2）Sum rule | $y=u(x)+v(x)$ | $\dfrac{dy}{dx}=\dfrac{du}{dx}+\dfrac{dv}{dx}$ | 逐项 |

> ✅ **考试信息**：讲师明确说明三条公式**会在考卷上提供**（"these three formulae will be given to you in the exam, so don't worry too much about remembering each of the individual formulas, but just remember how to apply them"）。基本求导表也在 handbook 末尾的公式页里。**要练的是「怎么拆、套哪条」，不是背公式。**

### 3.2 两个「错误猜想」的反例（务必记住，考概念题会考）

| 猜想 | 用 $u=x^3,\;v=x^6$ 检验 | 猜想给出 | 正确答案 | 结论 |
|---|---|---|---|---|
| $\frac{dy}{dx}=\frac{du}{dx}\cdot\frac{dv}{dx}$ | $y=x^9$ | $3x^2\cdot 6x^5=18x^7$ | $9x^8$ | ✗ |
| $\frac{dy}{dx}=\frac{du/dx}{dv/dx}$ | $y=x^{-3}$ | $\frac{3x^2}{6x^5}=\frac{1}{2}x^{-3}$ | $-3x^{-4}$ | ✗ |

### 3.3 导数符号与函数行为（Practical 收尾 + 下周预告）

$$\frac{dy}{dx}>0\;\Longrightarrow\;\text{函数递增 (increasing)}$$
$$\frac{dy}{dx}<0\;\Longrightarrow\;\text{函数递减 (decreasing)}$$
$$\frac{dy}{dx}=0\;\Longrightarrow\;\text{函数正在「改变方向」(changing direction)}$$

> "We will come across the important property a zero derivative has soon."（下周 Week 4 讲极值 / 优化。）

### 3.4 符号线（sign line）图表判读法 —— Figure 3.1 / Figure 3.2 的用法

Exercises Q3.5 与 Practical Exercise 3 用的都是同一套图，读法如下：

1. 求出 $\dfrac{dy}{dx}$，并**因式分解**；
2. 令导数 $=0$ 解出所有根（若是分式，**只需令分子为零**——分母平方恒正、不可能为零）；
3. 把这些根画成 **$x$ 轴上的虚线**，它们把实轴切成若干区间；
4. **在每个区间里取一个测试点**，代入导数看**正负号**；
   - 关键依据：*"Because the derivative is continuous we know that the only place it can change sign is where the derivative is zero."*（导数连续 ⇒ 只可能在零点处变号）
5. 正号区间 = 递增，负号区间 = 递减。

**Figure 3.2 具体形态（Practical slide 11 的图）**：函数 $h(x)=\dfrac{x-x^2}{1+8x^2}$，$x\in[-1,1]$，$y\in[-0.2,0.1]$。

```
            h'(x)<0        h'(x)>0          h'(x)<0
   ───────────────────┊───────────────┊─────────────────►  x
                  x=-1/2           x=1/4
                  h'=0             h'=0
                （局部极小）        （局部极大）
```

曲线在 $x=-1/2$ 处到达谷底（约 $y\approx-0.19$），在 $x=1/4$ 处到达峰顶（约 $y\approx0.083$）。

### 3.5 Week 3 的地球/环境科学应用场景清单

| 场景 | 数学形式 | 用到的法则 | 物理意义 |
|---|---|---|---|
| 大气静水压 (hydrostatic equation) | $P(z)=P_0e^{-gz/(R_\alpha T)}$ | chain rule | 压强随高度指数衰减，$dP/dz\propto -P$ |
| 生态水库排水 Q3.7(a) | $V(t)=V_0e^{-t^2/600}$ | chain rule | 高斯型排空：初期慢、中期快 |
| 生态水库排水 Q3.7(b) | $V(t)=\frac{V_0(t+10)}{10}e^{-t/5}$ | product rule | 先注入后指数排空（先升后降） |
| 生态水库排水 Q3.7(c) | $V(t)=\frac{V_0(t+10)}{t^2+10}$ | quotient rule | 幂律型衰减（长尾，比指数慢） |
| 体积随时间变化 Q3.5(a) | $V(t)=(4-t^2)(1+5t^2)$ | product rule | 判断体积何时增/何时减 |

**共同解读**：$\dfrac{dV}{dt}<0$ 表示水在**流出**（drainage），数值大小即**排水速率**，单位 $\mathrm{m^3\,hr^{-1}}$（题目中 $t$ 以小时计、$V$ 以 $\mathrm{m^3}$ 计）。

---

## 四、课堂补充（transcript 独有内容）

以下内容只出现在 `EART11200 - 10-Feb-transcript.md`，讲义/handbook 上没有：

### 4.1 课程叙事与串联

- 讲师用相当长的篇幅回顾 Week 1→Week 2 的因果关系：**中心差分/前向/后向差分不是凭空编出来的公式**，而是 $\frac{\Delta y}{\Delta x}$ 在 $\Delta x\to 0$ 时向导数收敛的过程。"We're not just... we didn't just come up with those formula randomly."
- 关于三角函数导数的循环性：$\sin\to\cos\to-\sin\to-\cos\to\sin$，"you differentiate sine three times and you end up back at something again"，并预告下周会说明 $\sin$ 与 $\cos$ 的导数为什么互相关联。
- 明确的「下一步路线图」：**Week 4–5 讲「为什么要求导」**——"They describe a rate of change, but can we use them to tell us something about a process?"——之后才进入积分。

### 4.2 考试相关的直接提示（transcript 独有，价值很高）

1. **三条法则 + 基本求导表都会在考卷上给出**，重点考「会不会用」。
2. handbook 末尾有完整公式页（"maths survival pack"），Blackboard 上有电子版。
3. **复活节后的两周复习课（Week 11–12）会专门带做「更复杂的组合函数」例题，难度即为夏季考试的实际难度。** 这是本周最有价值的一条备考情报。
4. "The individual functions might be more complicated, but the rules will remain the same." —— 考试不会有新法则，只会有更深的嵌套 / 更多法则混用。
5. 讲师建议：反复刷上周和本周 handbook 的练习题，"the more you do them the better you'll get at them and then you won't be flustered in the exam"。

### 4.3 讲师的实际操作建议

- **拆分的模板化**："You can use this as a kind of template if you're not very comfortable using it." 熟练后可以不再显式写代换，直接口算链式法则。
- **拆分的判据是「能不能查表」**："You try and split functions up or find substitutes that will allow you to use that table, and then just apply a formula at the end."
- **哪条法则的拆分最难**：讲师指出 **quotient rule 的拆分反而最容易**（分数线天然把式子切成两半），**chain rule 的代换最不显然**——"sometimes the chain rule and the product rule might not be the most obvious ones where you find the split or the substitution"。
- **乘积法则的视觉记忆**：讲师喜欢把它写成「**交叉相乘 cross multiplication**」的形式。
- **商法则的顺序警告**（转写里他说得有点乱，但意图明确）：分子里 **$v\frac{du}{dx}$ 必须写在前面**，因为有减号，顺序反了整个答案变号。

### 4.4 课堂花絮 / 现场信息

- 本次课换了教室，课后要**步行约 10–15 分钟到 Nancy Rothwell Building** 上下午的 practical；讲师提醒学生坐到长边房间的前排，因为「AV systems can't be linked」。
- 讲师两次点名问「有没有问题」都无人回应，于是自嘲："All of you guys just switched off and I'm boring you to tears... I'm just going to take that as I'm boring you to tears because I've had no response from you guys."（说明这堂课全程无学生提问，transcript 中没有额外的 Q&A 内容。）
- 讲师自嘲式的教学法："call me a fool, call me stupid, I'm going to try and continue to think about..." —— 他刻意用「明知会错的类比」引出商法则，这是他讲三条法则的统一叙事套路。

---

## 五、Practical 要点

本周 Practical 分两部分：**课堂现场三道题（`practical3_soln(5).pdf`）** + **Handbook 习题集 Q3.1–Q3.7（`Exercises3.md` / `Solutions3(1).md`）**。

> ⚠️ **题号说明**：以周版 `Exercises3.md` 为准，即 Q3.1–Q3.7。另注：`Exercises3.pdf` 的 Q3.6 有 (a)(b)(c) 三小问，而 md 转写只保留了 (a)；下面按 PDF 原文补全。Q3.4 题干写「(b)-(e)」但实际只有 (a)-(d)，是手册笔误。

### 5.0 Practical 的目的

三道现场题**一条法则一道**，都是「必须用该法则、无法绕开」的类型，用来把 lecture 的三步法当场跑通；最后一页把结果接回「导数符号 ⇒ 函数增减」，为 Week 4 铺路。

---

### 5.1 Practical 现场三题（完整解答）

#### Exercise 1（Chain rule）：$f(x)=-\ln(\cos(x))$

- **Step 1（拆+代换）**：$f(g)=-\ln(g)$，$g(x)=\cos(x)$
- **Step 2（求导）**：$\dfrac{df}{dg}=-\dfrac{1}{g}$，$\dfrac{dg}{dx}=-\sin(x)$
- **Step 3（合+回代）**：
$$\frac{df}{dx}=\left(-\frac{1}{\cos x}\right)\times(-\sin x)=\frac{\sin x}{\cos x}=\boxed{\tan(x)}$$

**要点**：两个负号相乘变正；结果恰好是 $\tan x$，是个漂亮的经典结果（$-\ln\cos x$ 是 $\tan x$ 的原函数，Week 8 积分会再见到）。注意**外层的负号要一路带着**，别在 Step 2 里丢掉。

#### Exercise 2（Product rule）：$g(x)=\sin(x)\exp(x)$

- **Step 1（拆）**：$u(x)=\sin(x)$，$v(x)=\exp(x)$
- **Step 2（求导）**：$\dfrac{du}{dx}=\cos(x)$，$\dfrac{dv}{dx}=\exp(x)$
- **Step 3（合）**：
$$\frac{dg}{dx}=\sin(x)\exp(x)+\exp(x)\cos(x)=\boxed{\exp(x)\big(\cos(x)+\sin(x)\big)}$$

**要点**：两项都含 $\exp(x)$，**提取公因子**是标准收尾。

#### Exercise 3（Quotient rule）：$h(x)=\dfrac{x-x^2}{1+8x^2}$

- **Step 1（拆）**：$u(x)=x-x^2$（分子），$v(x)=1+8x^2$（分母）
- **Step 2（求导）**：$\dfrac{du}{dx}=1-2x$，$\dfrac{dv}{dx}=16x$
- **Step 3（合+化简）**：
$$\frac{dh}{dx}=\frac{(1+8x^2)(1-2x)-16x(x-x^2)}{(1+8x^2)^2}$$
$$=\frac{1-2x+8x^2-16x^3-16x^2+16x^3}{(1+8x^2)^2}=\boxed{\frac{1-2x-8x^2}{(1+8x^2)^2}}$$

**要点**：$-16x^3$ 与 $+16x^3$ 相消是本题化简的关键；注意 $-16x\cdot(-x^2)=+16x^3$（负负得正）。
（官方 slide 上第二行把 $-16x^2$ 误打成 $-16x^3$，属排版笔误，最终结果正确。）

#### Practical 收尾：用 $h'(x)$ 读 $h(x)$ 的行为

令 $1-2x-8x^2=0$，即 $8x^2+2x-1=0$：

$$x=\frac{-2\pm\sqrt{4+32}}{16}=\frac{-2\pm 6}{16}\;\Longrightarrow\;x=\frac14\;\text{ 或 }\;x=-\frac12$$

分母 $(1+8x^2)^2$ 恒正，故导数符号完全由分子决定：

| 区间 | 测试点 | $1-2x-8x^2$ 符号 | 函数行为 |
|---|---|---|---|
| $x<-\tfrac12$ | $x=-1$ | $1+2-8=-5<0$ | 递减 |
| $-\tfrac12<x<\tfrac14$ | $x=0$ | $1>0$ | 递增 |
| $x>\tfrac14$ | $x=1$ | $1-2-8=-9<0$ | 递减 |

对应 slide 图上的标注：$h'(x)<0 \mid h'(x)>0 \mid h'(x)<0$，两条虚线在 $x=-1/2$ 和 $x=1/4$。

---

### 5.2 Handbook 习题 Q3.1–Q3.7（逐题完整解答）

#### **Question 3.1 —— 用链式法则**

**(a) $y=\exp(x^2+5x+2)$**
- 拆：$u(v)=\exp(v)\Rightarrow\frac{du}{dv}=\exp(v)$；$v(x)=x^2+5x+2\Rightarrow\frac{dv}{dx}=2x+5$
- 合：$\dfrac{dy}{dx}=\boxed{(2x+5)\exp(x^2+5x+2)}$
- *要点*：指数函数求导后**外形不变**，只是前面多乘一个内层导数——正是表里 $e^{f(x)}\to\frac{df}{dx}e^{f(x)}$ 的来源。

**(b) $y=\cos(3x+5)$**
- 拆：$u(v)=\cos(v)\Rightarrow\frac{du}{dv}=-\sin(v)$；$v(x)=3x+5\Rightarrow\frac{dv}{dx}=3$
- 合：$\dfrac{dy}{dx}=\boxed{-3\sin(3x+5)}$
- *要点*：内层是线性函数时，效果就是「照抄外层导数 + 前面乘上斜率」。**负号来自 $\cos$ 的导数，不要漏。**

**(c) $y=\sin(x)^2$**  ← 读作 $(\sin x)^2$，**不是** $\sin(x^2)$
- 拆：$u(v)=v^2\Rightarrow\frac{du}{dv}=2v$；$v(x)=\sin(x)\Rightarrow\frac{dv}{dx}=\cos(x)$
- 合：$\dfrac{dy}{dx}=\boxed{2\sin(x)\cos(x)}$（$=\sin(2x)$）
- *要点*：**「幂在外」的情况**——把整个 $\sin x$ 当成内层。这是最常见的链式法则考法。

---

#### **Question 3.2 —— 用乘积法则**

**(a) $y=x\exp(x)$**
- 拆：$u=x\Rightarrow\frac{du}{dx}=1$；$v=\exp(x)\Rightarrow\frac{dv}{dx}=\exp(x)$
- 合：$\dfrac{dy}{dx}=x\exp(x)+\exp(x)=\boxed{(1+x)\exp(x)}$

**(b) $y=x^2\exp(4x)$**
- 拆：$u=x^2\Rightarrow\frac{du}{dx}=2x$；$v=\exp(4x)\Rightarrow\frac{dv}{dx}=4\exp(4x)$
- 合：$\dfrac{dy}{dx}=4x^2\exp(4x)+2x\exp(4x)=\boxed{(2x+4x^2)\exp(4x)}$（也可写 $2x(1+2x)e^{4x}$）
- *要点*：$\frac{dv}{dx}$ 本身用了链式法则（或表里 $e^{kx}$ 那一行）——**法则可以嵌套使用**。

**(c) $y=(x^2+9)\exp(-x)$**
- 拆：$u=x^2+9\Rightarrow\frac{du}{dx}=2x$；$v=\exp(-x)\Rightarrow\frac{dv}{dx}=-\exp(-x)$
- 合：$\dfrac{dy}{dx}=-(x^2+9)\exp(-x)+2x\exp(-x)=\boxed{-(x^2-2x+9)\exp(-x)}$
- *要点*：$\exp(-x)$ 求导带出 $-1$，**最容易漏的负号**。提公因子时把负号整体提出，注意括号内每项都要变号。

---

#### **Question 3.3 —— 用商法则**

**(a) $y=\dfrac{\exp(-x)}{x}$**
- 拆：$u=\exp(-x)\Rightarrow\frac{du}{dx}=-\exp(-x)$；$v=x\Rightarrow\frac{dv}{dx}=1$
- 合：$\dfrac{dy}{dx}=\dfrac{-x\exp(-x)-\exp(-x)}{x^2}=\boxed{\dfrac{-(1+x)\exp(-x)}{x^2}}$
- *要点*：注意 $v\frac{du}{dx}=x\cdot(-e^{-x})$ 已经是负的，再减去 $u\frac{dv}{dx}=e^{-x}$，两项都是负号。

**(b) $y=\dfrac{x}{x^2+25}$**
- 拆：$u=x\Rightarrow\frac{du}{dx}=1$；$v=x^2+25\Rightarrow\frac{dv}{dx}=2x$
- 合：$\dfrac{dy}{dx}=\dfrac{(x^2+25)-2x^2}{(x^2+25)^2}=\boxed{\dfrac{25-x^2}{(x^2+25)^2}}$
- *要点*：这个结果在 Week 4/5 会很有用——分子为零给出 $x=\pm5$，即函数的极大/极小点。

**(c) $y=\dfrac{x^2}{x^3+25x}$**
- 拆：$u=x^2\Rightarrow\frac{du}{dx}=2x$；$v=x^3+25x\Rightarrow\frac{dv}{dx}=3x^2+25$
- 合：
$$\frac{dy}{dx}=\frac{2x(x^3+25x)-x^2(3x^2+25)}{(x^3+25x)^2}=\frac{2x^4+50x^2-3x^4-25x^2}{(x^3+25x)^2}=\boxed{\frac{25x^2-x^4}{(x^3+25x)^2}}$$
- 💡 **值得注意的观察**（官方解答没写，但很有启发）：$\dfrac{x^2}{x^3+25x}=\dfrac{x}{x^2+25}$（上下约去一个 $x$，$x\ne0$），所以 (c) 和 (b) 其实是**同一个函数**！把 (c) 的答案化简：
$$\frac{x^2(25-x^2)}{x^2(x^2+25)^2}=\frac{25-x^2}{(x^2+25)^2}$$
与 (b) 完全一致 ✓。**教训：先化简再求导，往往省一半功夫。**

---

#### **Question 3.4 —— 链式/乘积/商法则的混用（本周最核心的综合题）**

题干设计：**(a) 先算出一个「零件」，(b)(c)(d) 各自把它塞进不同法则里复用。**

**(a) $y=\sqrt{x^2+25}$**
- 拆：$u(v)=\sqrt{v}=v^{1/2}\Rightarrow\frac{du}{dv}=\frac{1}{2\sqrt v}$；$v(x)=x^2+25\Rightarrow\frac{dv}{dx}=2x$
- 合：$\dfrac{dy}{dx}=\dfrac{2x}{2\sqrt{x^2+25}}=\boxed{\dfrac{x}{\sqrt{x^2+25}}}$ ← **记住这个零件，下面反复用**

**(b) $y=\sin\!\left(\sqrt{x^2+25}\right)$** —— 链式法则（**两层嵌套**）
- 拆：$u(v)=\sin(v)\Rightarrow\frac{du}{dv}=\cos(v)$；$v(x)=\sqrt{x^2+25}\Rightarrow\frac{dv}{dx}=\dfrac{x}{\sqrt{x^2+25}}$（直接用 (a) 的结果）
- 合：$\dfrac{dy}{dx}=\boxed{\dfrac{x}{\sqrt{x^2+25}}\cos\!\left(\sqrt{x^2+25}\right)}$
- *要点*：**内层导数本身就是链式法则的产物**——这正是「多重嵌套逐层剥」的实战。

**(c) $y=x\sqrt{x^2+25}$** —— 乘积法则
- 拆：$u=x\Rightarrow\frac{du}{dx}=1$；$v=\sqrt{x^2+25}\Rightarrow\frac{dv}{dx}=\dfrac{x}{\sqrt{x^2+25}}$
- 合：$\dfrac{dy}{dx}=x\cdot\dfrac{x}{\sqrt{x^2+25}}+\sqrt{x^2+25}\cdot 1=\boxed{\sqrt{x^2+25}+\dfrac{x^2}{\sqrt{x^2+25}}}$
- 可进一步通分：$=\dfrac{(x^2+25)+x^2}{\sqrt{x^2+25}}=\dfrac{2x^2+25}{\sqrt{x^2+25}}$（官方答案停在未通分形式）

**(d) $y=\dfrac{x}{\sqrt{x^2+25}}$** —— 商法则
- 拆：$u=x\Rightarrow\frac{du}{dx}=1$；$v=\sqrt{x^2+25}\Rightarrow\frac{dv}{dx}=\dfrac{x}{\sqrt{x^2+25}}$
- 合（注意 $v^2=x^2+25$，根号平方掉了，这是本题最妙的一步）：
$$\frac{dy}{dx}=\frac{\sqrt{x^2+25}-\dfrac{x^2}{\sqrt{x^2+25}}}{x^2+25}=\frac{1}{\sqrt{x^2+25}}-\frac{x^2}{(x^2+25)^{3/2}}$$
- 官方答案止于此；可再通分为最简形式：
$$\boxed{\dfrac{dy}{dx}=\dfrac{(x^2+25)-x^2}{(x^2+25)^{3/2}}=\dfrac{25}{(x^2+25)^{3/2}}}$$
- *要点*：$\dfrac{1}{\sqrt{A}}\cdot\dfrac{1}{A}=A^{-3/2}$，这类分数指数运算是本题的技术难点。**结果恒为正 ⇒ 该函数处处递增**（可作为答案合理性的直觉检验：$\frac{x}{\sqrt{x^2+25}}$ 从 $-1$ 单调升到 $+1$）。

---

#### **Question 3.5 —— 求函数的递增/递减区间（三步综合题）**

标准流程：**① 求导（选对法则）→ ② 因式分解 → ③ 令导数=0 求根 → ④ 分区间测符号 → ⑤ 写出递增/递减区间。**

**(a) $V(t)=(4-t^2)(1+5t^2)$** —— 乘积法则

- 拆：$u(t)=4-t^2\Rightarrow\frac{du}{dt}=-2t$；$v(t)=1+5t^2\Rightarrow\frac{dv}{dt}=10t$
- 合：
$$\frac{dV}{dt}=10t(4-t^2)-2t(1+5t^2)=40t-10t^3-2t-10t^3=38t-20t^3=\boxed{2t(19-10t^2)}$$
- 令 $\frac{dV}{dt}=0$：
$$t=0,\qquad t=\pm\sqrt{\frac{19}{10}}=\pm 1.3784$$
- 分区间测符号（$2t(19-10t^2)$）：

| 区间 | $2t$ | $(19-10t^2)$ | 乘积 | 行为 |
|---|---|---|---|---|
| $t<-1.3784$ | $-$ | $-$ | $+$ | 递增 |
| $-1.3784<t<0$ | $-$ | $+$ | $-$ | 递减 |
| $0<t<1.3784$ | $+$ | $+$ | $+$ | 递增 |
| $t>1.3784$ | $+$ | $-$ | $-$ | 递减 |

- **官方结论**：
$$\text{Increasing}:\;-\infty<t<-\sqrt{\tfrac{19}{10}},\quad 0<t<\sqrt{\tfrac{19}{10}}$$
$$\text{Decreasing}:\;-\sqrt{\tfrac{19}{10}}<t<0,\quad \sqrt{\tfrac{19}{10}}<t<\infty$$
- *要点*：本题也可以先展开 $V=4+20t^2-t^2-5t^4=4+19t^2-5t^4$，直接求导得 $38t-20t^3$ ✓（**用来验算乘积法则做对没有的绝佳方法**）。
- *物理注解*：若 $t$ 是时间，只有 $t\ge0$ 有意义 ⇒ 体积先增到 $t=1.3784$ hr 达到峰值，之后开始下降。

**(b) $f(x)=\dfrac{x-x^2}{1+8x^2}$** —— 商法则（与 Practical Exercise 3 同一函数）

- 拆：$u=x-x^2\Rightarrow\frac{du}{dx}=1-2x$；$v=1+8x^2\Rightarrow\frac{dv}{dx}=16x$
- 合：
$$\frac{df}{dx}=\frac{(1-2x)(1+8x^2)-16x(x-x^2)}{(1+8x^2)^2}=\boxed{\frac{1-2x-8x^2}{(1+8x^2)^2}}$$
- **关键判断**：*"The denominator will never be zero for any real number and so the derivative will only be zero where the numerator is zero."* ⇒ 只解分子：
$$1-2x-8x^2=0\;\Longleftrightarrow\;8x^2+2x-1=0\;\Longrightarrow\;x=-\frac12,\;x=\frac14$$
- **官方结论**：
$$\text{Increasing}:\;-\tfrac12<x<\tfrac14$$
$$\text{Decreasing}:\;-\infty<x<-\tfrac12,\quad \tfrac14<x<\infty$$

---

#### **Question 3.6 —— 综合练习（自行判断用哪条法则）**

**(a) $Z=(\sin(x^2))^2$** —— **链式法则用两次**

官方做法「分步走」：
1. 先求内两层：$y=\sin(x^2)$，拆 $u(v)=\sin(v)$、$v(x)=x^2$ ⇒ $\dfrac{dy}{dx}=2x\cos(x^2)$
2. 再求整体：拆 $u(v)=v^2\Rightarrow\frac{du}{dv}=2v$；$v(x)=\sin(x^2)\Rightarrow\frac{dv}{dx}=2x\cos(x^2)$
3. 合：
$$\frac{dZ}{dx}=2\sin(x^2)\times 2x\cos(x^2)=\boxed{4x\sin(x^2)\cos(x^2)}$$
（$=2x\sin(2x^2)$）
- *要点*：官方原话 *"To make sure we don't make any mistakes, lets do it part by part."* —— **多层嵌套时不要一步到位，分步写、把中间结果标注出来。**
- ⚠️ 题干写 $Z(s)$ 但变量是 $x$，是手册笔误，按 $Z(x)$ 处理。

**(b) $S(x)=\left(1+\sqrt{x^3}\right)\left(x^{-3}-2\sqrt[3]{x}\right)$** —— **乘积法则 + 分数指数**
（此题在 md 转写中丢失，来自 `Exercises3.pdf` 第 2 页）

- **先改写成幂形式**（这是解本题的第一关键步骤）：
$$u(x)=1+x^{3/2},\qquad v(x)=x^{-3}-2x^{1/3}$$
- 求导：
$$\frac{du}{dx}=\frac32 x^{1/2},\qquad \frac{dv}{dx}=-3x^{-4}-\frac23 x^{-2/3}$$
- 合（乘积法则）：
$$\frac{dS}{dx}=\left(1+x^{3/2}\right)\left(-3x^{-4}-\tfrac23 x^{-2/3}\right)+\left(x^{-3}-2x^{1/3}\right)\left(\tfrac32 x^{1/2}\right)$$
- 展开（指数相加）：
  - $1\cdot(-3x^{-4})=-3x^{-4}$
  - $1\cdot(-\tfrac23 x^{-2/3})=-\tfrac23 x^{-2/3}$
  - $x^{3/2}\cdot(-3x^{-4})=-3x^{-5/2}$
  - $x^{3/2}\cdot(-\tfrac23 x^{-2/3})=-\tfrac23 x^{5/6}$
  - $\tfrac32 x^{1/2}\cdot x^{-3}=\tfrac32 x^{-5/2}$
  - $\tfrac32 x^{1/2}\cdot(-2x^{1/3})=-3x^{5/6}$
- 合并同类项：$(-3+\tfrac32)x^{-5/2}=-\tfrac32 x^{-5/2}$；$(-\tfrac23-3)x^{5/6}=-\tfrac{11}{3}x^{5/6}$
$$\boxed{\frac{dS}{dx}=-3x^{-4}-\frac32 x^{-5/2}-\frac23 x^{-2/3}-\frac{11}{3}x^{5/6}}$$
- *要点*：**根号一律先转成分数指数**（$\sqrt{x^3}=x^{3/2}$，$\sqrt[3]{x}=x^{1/3}$），否则无法用幂法则。合并同类项时靠**指数是否相同**判断。

**(c) $R(w)=\dfrac{3w+w^4}{2w^2+1}$** —— 商法则
（同样来自 `Exercises3.pdf` 第 2 页）

- 拆：$u(w)=3w+w^4\Rightarrow\frac{du}{dw}=3+4w^3$；$v(w)=2w^2+1\Rightarrow\frac{dv}{dw}=4w$
- 合：
$$\frac{dR}{dw}=\frac{(2w^2+1)(3+4w^3)-4w(3w+w^4)}{(2w^2+1)^2}$$
$$=\frac{6w^2+8w^5+3+4w^3-12w^2-4w^5}{(2w^2+1)^2}=\boxed{\frac{4w^5+4w^3-6w^2+3}{(2w^2+1)^2}}$$
- *要点*：自变量换成 $w$ 只是换个字母，不影响任何步骤——**看到陌生变量名不要慌**。

---

#### **Question 3.7 —— Real-world problems：生态水库的排水速率**

背景：研究一个生态水库 (ecosystem reservoir) 的水量随时间（**单位：小时**）的变化。$V_0$ 是 $t=0$ 时的水量，单位 $\mathrm{m^3}$。三小问用同一个物理情境分别练三条法则，最后都要算 $t=10\,\mathrm{hr}$、$V_0=10$ 时的**排水速率 (drainage rate)**。

**(a) 链式法则：$V(t)=V_0\exp\left(\dfrac{-t^2}{600}\right)$**

- 拆：$u(v)=V_0\exp(v)\Rightarrow\frac{du}{dv}=V_0\exp(v)$；$v(t)=\dfrac{-t^2}{600}\Rightarrow\dfrac{dv}{dt}=\dfrac{-t}{300}$
- 合：
$$\boxed{\frac{dV}{dt}=-\frac{V_0\,t}{300}\exp\left(\frac{-t^2}{600}\right)}$$
- 代入 $t=10$、$V_0=10$：
$$\frac{dV}{dt}(10)=-\frac{10\times 10}{300}\exp\left(\frac{-100}{600}\right)=-\frac13 e^{-1/6}$$
$$=-0.3333\times 0.8465=\mathbf{-0.282\ m^3\,hr^{-1}}$$
- ⚠️ **官方解答此处印的数值 $-0.1829$ 有算术错误**；$-\frac13 e^{-1/6}=-0.2822$（可自行验算：$e^{-1/6}=0.84648$）。**解析表达式是对的，只有最后的数值代入错了。**
- *物理意义*：负号 = 水在流出。这是**高斯型（钟形）衰减**，$t=0$ 时排水速率为零（水面静止），随后加速排出。

**(b) 乘积法则：$V(t)=\dfrac{V_0(t+10)}{10}\exp\left(\dfrac{-t}{5}\right)$**

- 拆：$u(t)=\dfrac{V_0(t+10)}{10}\Rightarrow\dfrac{du}{dt}=\dfrac{V_0}{10}$；$v(t)=\exp\!\left(\dfrac{-t}{5}\right)\Rightarrow\dfrac{dv}{dt}=-\dfrac15\exp\!\left(\dfrac{-t}{5}\right)$
- 合并与化简（官方展示了完整的提取公因子过程）：
$$\frac{dV}{dt}=\frac{V_0(t+10)}{10}\cdot\left(-\frac15\right)e^{-t/5}+e^{-t/5}\cdot\frac{V_0}{10}$$
$$=-\frac{V_0(t+10)}{50}e^{-t/5}+\frac{V_0}{10}e^{-t/5}=V_0e^{-t/5}\left[-\frac{t+10}{50}+\frac{1}{10}\right]$$
$$=V_0e^{-t/5}\left[\frac{-(t+10)+5}{50}\right]=V_0e^{-t/5}\cdot\frac{-t-5}{50}$$
$$\boxed{\frac{dV}{dt}=-\frac{V_0(t+5)}{50}\exp\left(\frac{-t}{5}\right)}$$
- 代入 $t=10$、$V_0=10$：
$$\frac{dV}{dt}(10)=-\frac{10\times(10+5)}{50}e^{-2}=-3e^{-2}=\mathbf{-0.406\ m^3\,hr^{-1}}$$
- *要点*：**通分技巧** $-\frac{t+10}{50}+\frac{1}{10}=\frac{-(t+10)+5}{50}$（把 $\frac1{10}$ 变成 $\frac5{50}$）。这一步是本题化简的核心。
- *物理意义*：$(t+10)$ 线性项代表持续注入，$e^{-t/5}$ 代表指数排空；两者竞争，但导数 $-\frac{V_0(t+5)}{50}e^{-t/5}$ 对 $t\ge0$ 恒为负，说明**从 $t=0$ 起水量就一直在减少**（排空压过注入）。

**(c) 商法则：$V(t)=\dfrac{V_0(t+10)}{t^2+10}$**
（原题打印成 $x$，但上下文与官方解答均按 $t$ 处理，是手册笔误。）

- 把常数 $V_0$ 提到外面，只对 $\dfrac{t+10}{t^2+10}$ 用商法则：
- 拆：$u(t)=t+10\Rightarrow\frac{du}{dt}=1$；$v(t)=t^2+10\Rightarrow\frac{dv}{dt}=2t$
- 合：
$$\frac{dV}{dt}=V_0\cdot\frac{(t^2+10)\cdot 1-2t(t+10)}{(t^2+10)^2}=V_0\cdot\frac{t^2+10-2t^2-20t}{(t^2+10)^2}$$
$$\boxed{\frac{dV}{dt}=V_0\cdot\frac{-t^2-20t+10}{(t^2+10)^2}}$$
- 代入 $t=10$、$V_0=10$：
$$\frac{dV}{dt}(10)=10\times\frac{-100-200+10}{(100+10)^2}=10\times\frac{-290}{12100}=-\frac{2900}{12100}=\mathbf{-0.2397\ m^3\,hr^{-1}}$$
- ⚠️ 官方解答中间那一行把分母误写成 $(2w^2+1)^2$，是从上一题 Q3.6(c) 复制粘贴留下的，正确分母是 $(t^2+10)^2$。
- *要点*：**常数 $V_0$ 不必参与商法则**，先提出来能大幅减少出错概率。
- *物理意义*：幂律型衰减，尾部比指数衰减**慢得多**（长尾）。三种模型在 $t=10$ hr 的排水速率对比：(a) $-0.282$、(b) $-0.406$、(c) $-0.240$ $\mathrm{m^3\,hr^{-1}}$ —— **同一个「水库排空」现象，选不同的函数模型会给出量级相近但明显不同的速率**，这正是本课程强调「模型选择很重要」的地方。

---

### 5.3 Handbook 正文例题（Chapter 3 中的 Example 3.1–3.6）

这六个例题按「**能验算的 / 非用不可的**」配对设计：每条法则各配一个「其实可以硬算、用来验证法则正确性」的例子，和一个「不用法则就做不出来」的例子。

| 例题 | 函数 | 法则 | 类型 |
|---|---|---|---|
| 3.1 | $y=(3x+1)^2$ | chain | 可验算 |
| 3.2 | $y=\sqrt{13x^2-6x+8}$ | chain | 非用不可 |
| 3.3 | $y=(3x+1)^2$ | product | 可验算 |
| 3.4 | $y=x\exp(-3x)$ | product | 非用不可 |
| 3.5 | $y=\dfrac{3x+1}{x^2}$ | quotient | 可验算 |
| 3.6 | $y=\dfrac{3x+1}{x^2+1}$ | quotient | 非用不可 |

**Example 3.1**（chain）：$y=(3x+1)^2$
- 硬算：$y=9x^2+6x+1\Rightarrow\frac{dy}{dx}=18x+6$
- 链式：$u(v)=v^2$、$v(x)=3x+1$；$\frac{du}{dv}=2v$、$\frac{dv}{dx}=3$
$$\frac{dy}{dx}=2(3x+1)\times 3=6(3x+1)=18x+6\;✓$$

**Example 3.2**（chain）：$y=\sqrt{13x^2-6x+8}$
- $u(v)=\sqrt v=v^{0.5}$、$v(x)=13x^2-6x+8$
- $\frac{du}{dv}=0.5v^{-0.5}=\dfrac{1}{2\sqrt v}$、$\frac{dv}{dx}=26x-6$
$$\frac{dy}{dx}=\frac{1}{2\sqrt{13x^2-6x+8}}\times(26x-6)=\boxed{\frac{13x-3}{\sqrt{13x^2-6x+8}}}$$
- ⚠️ handbook 中间一步印成 $\sqrt{13x^2-5x+8}$（$-5x$），是笔误，应为 $-6x$；最终答案正确。
- *要点*：$\frac{26x-6}{2}=13x-3$，**约分要做完**。

**Example 3.3**（product，注意是同一个函数换法则做）：$y=(3x+1)^2=(3x+1)(3x+1)$
- $u=v=3x+1$，$\frac{du}{dx}=\frac{dv}{dx}=3$
$$\frac{dy}{dx}=(3x+1)\cdot 3+(3x+1)\cdot 3=18x+6\;✓$$
- 💡 **教学意图**：同一个函数 $(3x+1)^2$ **既能用链式也能用乘积法则**，两条路殊途同归。说明「选哪条法则」有时不唯一，选顺手的即可。

**Example 3.4**（product）：$y=x\exp(-3x)$
- $u=x$、$v=\exp(-3x)$；$\frac{du}{dx}=1$、$\frac{dv}{dx}=-3\exp(-3x)$
$$\frac{dy}{dx}=x\cdot(-3e^{-3x})+e^{-3x}\cdot 1=\boxed{(1-3x)\exp(-3x)}$$

**Example 3.5**（quotient）：$y=\dfrac{3x+1}{x^2}$
- 硬算（拆成两个分数）：$y=\dfrac{3}{x}+\dfrac{1}{x^2}=3x^{-1}+x^{-2}\Rightarrow\frac{dy}{dx}=-3x^{-2}-2x^{-3}=\dfrac{-3x-2}{x^3}$
- 商法则：$u=3x+1$、$v=x^2$；$\frac{du}{dx}=3$、$\frac{dv}{dx}=2x$
$$\frac{dy}{dx}=\frac{x^2\cdot 3-(3x+1)\cdot 2x}{x^4}=\frac{3x^2-6x^2-2x}{x^4}=\frac{-3x^2-2x}{x^4}=\frac{-3x-2}{x^3}\;✓$$
- 💡 **教学意图**：分母是单项式时，**拆成幂函数之和往往更快**——不要机械地一见分数就上商法则。

**Example 3.6**（quotient）：$y=\dfrac{3x+1}{x^2+1}$
- $u=3x+1$、$v=x^2+1$；$\frac{du}{dx}=3$、$\frac{dv}{dx}=2x$
$$\frac{dy}{dx}=\frac{(x^2+1)\cdot 3-(3x+1)\cdot 2x}{(x^2+1)^2}=\frac{3x^2+3-6x^2-2x}{(x^2+1)^2}=\boxed{\frac{-3x^2-2x+3}{(x^2+1)^2}}$$
- ⚠️ **handbook 印出的答案是 $\dfrac{-3x^2+2x-3}{(x^2+1)^2}$，中间项和常数项的符号有误**。按上面逐步展开，正确结果是 $\dfrac{-3x^2-2x+3}{(x^2+1)^2}$。（自查：$3x^2+3-(6x^2+2x)=-3x^2-2x+3$。）
- *注*：handbook 在 Example 3.5、3.6 的行文里都误写成 "using the product rule formula"，实际用的是 quotient rule——slide 上也有同样的复制粘贴笔误。

---

### 5.4 Practical 解题技巧总结

1. **永远写出 Step 1/2/3 的框架**，哪怕心算得出来——考试按步骤给分，且能防止漏项。
2. **拆分后先检查**：每个 $u$、$v$ 是否都能在求导表里直接查到？不能的话继续拆。
3. **常数先提出来**（如 Q3.7c 的 $V_0$），不要让它参与法则。
4. **能化简就先化简**（如 Q3.3c 的约分、Example 3.5 的拆分数）。
5. **收尾一定要提公因子**：$e^{kx}$、$\sqrt{\cdot}$ 等公共项提出来，答案更整洁，也便于下一步令导数为零。
6. **分式导数令零时只看分子**（分母是平方，恒不为零）。
7. **验算手段**：若原函数能展开（如 Q3.5a），展开后直接求导对答案，是最可靠的自查方式。
8. **注意负号来源**：$\cos\to-\sin$、$e^{-x}\to -e^{-x}$、商法则的减号 —— 本周失分的绝大多数原因。

---

## 六、易错点 / 重点难点

### 6.1 概念性错误（最致命）

1. ❌ **「乘积的导数 = 导数的乘积」** —— 用 $x^3\cdot x^6$ 反例记牢：$18x^7\ne 9x^8$。
2. ❌ **「商的导数 = 导数的商」** —— 反例：$\frac12 x^{-3}\ne-3x^{-4}$，**连符号都错**。
3. ❌ **链式法则漏掉内层导数** —— 最经典的错法：$\frac{d}{dx}\ln(2x)\overset{?}{=}\frac{1}{2x}$（正确是 $\frac1x$）；$\frac{d}{dx}\sin(3x+1)\overset{?}{=}\cos(3x+1)$（漏了因子 3）。
4. ❌ **只把「加减法可以逐项处理」的直觉往乘除上套** —— 只有加减法有这个性质。

### 6.2 商法则专项（讲师点名的「最难」）

5. ⚠️ **分子的顺序不能颠倒**：必须是 $v\frac{du}{dx}-u\frac{dv}{dx}$，写反了整个答案变号。乘积法则可以随便换序，商法则不行——**这是两条法则最容易串味的地方**。
6. ⚠️ **分母是 $v^2$，不是 $v$，也不是 $u^2$** —— $v$ 是**原式的分母**。
7. ⚠️ **$u$ 是分子、$v$ 是分母**，代反了答案全错。建议每次都在草稿上明确标注「$u$ = 分子」。
8. ⚠️ 展开分子时**减号后面的整个括号都要变号**：$-16x(x-x^2)=-16x^2+16x^3$（不是 $-16x^2-16x^3$）。

### 6.3 链式法则专项

9. ⚠️ **区分 $\sin(x)^2=(\sin x)^2$ 与 $\sin(x^2)$** —— 两者的拆法完全不同：
   - $(\sin x)^2$：外层是平方，内层是 $\sin x$ ⇒ $2\sin x\cos x$
   - $\sin(x^2)$：外层是 $\sin$，内层是 $x^2$ ⇒ $2x\cos(x^2)$
10. ⚠️ **回代不彻底**：Step 2 算出的是 $\frac{du}{dv}$（含 $v$），Step 3 必须把 $v=v(x)$ 代回去，**答案里不能残留 $v$ 或 $g$**。
11. ⚠️ **多重嵌套漏层**：$(\sin(x^2))^2$ 要乘三个因子，少乘一个 $2x$ 是常见错误。**从外往里剥，每剥一层写一个因子，剥到只剩 $x$ 为止。**
12. ⚠️ **外层的负号/系数要一路带着**：$-\ln(\cos x)$ 的负号，$\frac{df}{dg}=-\frac1g$ 而非 $\frac1g$。

### 6.4 代数与化简

13. ⚠️ **根号必须先化成分数指数**才能用幂法则：$\sqrt{v}=v^{1/2}$，$\sqrt[3]{x}=x^{1/3}$，$\frac{1}{\sqrt{v}}=v^{-1/2}$。
14. ⚠️ **$\frac{1}{\sqrt A}\cdot\frac{1}{A}=A^{-3/2}$**（Q3.4d）—— 分数指数相加的运算容易出错。
15. ⚠️ 商法则里若 $v=\sqrt{A}$，则 $v^2=A$，**根号会消掉**——这往往是化简的突破口。
16. ⚠️ **通分技巧**（Q3.7b）：$-\frac{t+10}{50}+\frac{1}{10}=\frac{-(t+10)+5}{50}$，注意把 $\frac1{10}$ 换成 $\frac5{50}$。

### 6.5 策略性错误（会做但做慢/做错）

17. 💡 **一见括号就上链式法则** —— 若括号能轻松展开（$(3x+1)^2$、$(4-t^2)(1+5t^2)$），**展开更快且不易错**，还能当验算。
18. 💡 **一见分数线就上商法则** —— 分母是单项式或常数时，拆成幂函数之和更快（Example 3.5）。分母不含 $x$ 时**根本不需要**商法则。
19. 💡 **先化简再求导** —— Q3.3(c) 的 $\frac{x^2}{x^3+25x}$ 本可先约成 $\frac{x}{x^2+25}$，工作量减半。
20. 💡 **常数因子不要卷进法则**（Q3.7c 的 $V_0$）。

### 6.6 应用题专项

21. ⚠️ **单位与符号解读**：$\frac{dV}{dt}<0$ 表示水量在**减少**（排水）；"drainage rate" 通常报绝对值或带负号说明方向，单位 $\mathrm{m^3\,hr^{-1}}$。
22. ⚠️ **先求出解析导数，再代入数值**（题目明确要求 "determine the gradient analytically"），不要一上来就代数字。
23. ⚠️ 代入后**保留足够小数位**（官方答案给 3–4 位）。

### 6.7 官方材料勘误汇总（复习时以本笔记为准）

| 位置 | 印刷内容 | 应为 |
|---|---|---|
| `lecture3(2).pdf` slide 7 | $\;=-\frac{P}{R_\alpha T}P$ | $=-\frac{g}{R_\alpha T}P$ |
| `lecture3(2).pdf` slide 10, 13 | $v(x)=x^6\Rightarrow \frac{du}{dx}=6x^5$ | $\frac{dv}{dx}=6x^5$ |
| 所有 slide 的 Step 3 | "Apply the **product** rule" | 应随该页法则而定（chain / quotient） |
| ILO 第 (3) 条 | "products of functions" | "quotients of functions" |
| `Chapter3.pdf` Example 3.2 中间步 | $\sqrt{13x^2-5x+8}$ | $\sqrt{13x^2-6x+8}$ |
| `Chapter3.pdf` Example 3.6 答案 | $\frac{-3x^2+2x-3}{(x^2+1)^2}$ | $\frac{-3x^2-2x+3}{(x^2+1)^2}$ |
| `Solutions3(1).pdf` Q3.4(b) | $\frac{du}{dx}=\cos(v)$ | $\frac{du}{dv}=\cos(v)$ |
| `Solutions3(1).pdf` Q3.5(b) | "We have been given 3 points where the derivative is zero" | 只有 2 个根（$-\frac12$, $\frac14$） |
| `Solutions3(1).pdf` Q3.7(a) | $-\frac13 e^{-1/6}=-0.1829$ | $=-0.2822$ |
| `Solutions3(1).pdf` Q3.7(c) | 分母 $(2w^2+1)^2$ | $(t^2+10)^2$ |
| `Exercises3.pdf` Q3.4 题干 | "(b)-(e)" | 实际只有 (a)-(d) |
| `Exercises3.pdf` Q3.6(a) | $Z(s)=\ldots$ | 变量应为 $x$ |
| `Exercises3.pdf` Q3.7(c) | $V(t)=\frac{V_0(x+10)}{x^2+10}$ | 变量应为 $t$ |
| `practical3_soln(5).pdf` Ex.3 展开 | $\ldots+8x^2-16x^3-16x^3+16x^3$ | 第二项应为 $-16x^2$ |

---

## 七、本周术语表

| 英文 | 中文 | 说明 / 公式 |
|---|---|---|
| chain rule | 链式法则 | $\frac{dy}{dx}=\frac{du}{dv}\times\frac{dv}{dx}$，处理复合函数 |
| product rule | 乘积法则 | $\frac{dy}{dx}=u\frac{dv}{dx}+v\frac{du}{dx}$ |
| quotient rule | 商法则 | $\frac{dy}{dx}=\frac{v\frac{du}{dx}-u\frac{dv}{dx}}{v^2}$ |
| sum rule | 和法则 | 和的导数 = 导数的和（Week 2） |
| composite function | 复合函数 | $f(g(x))$，「函数的函数」 |
| function of a function | 函数的函数 | handbook 对 composite function 的口语说法 |
| product of functions | 函数的乘积 | $y=u(x)v(x)$ |
| quotient of functions | 函数的商 | $y=u(x)/v(x)$ |
| combinations of functions | 函数的组合 | 本章标题，泛指复合/乘积/商 |
| substitution | 代换 | 链式法则 Step 1 的核心操作，把内层设为新变量 |
| split the function | 拆分函数 | 三步法的第一步 |
| numerator | 分子 | 商法则中的 $u$ |
| denominator | 分母 | 商法则中的 $v$ |
| derivative | 导数 / 导函数 | $\frac{dy}{dx}$ 或 $f'(x)$ |
| analytical derivative | 解析导数 | 用公式精确求出的导数（对比数值方法） |
| numerical approach | 数值方法 | Week 1 的差分法，函数无法解析求导时使用 |
| rate of change | 变化率 | 导数的物理解读 |
| gradient | 梯度 / 斜率 | 本课程中常与 derivative 混用 |
| increasing / decreasing | 递增 / 递减 | $\frac{dy}{dx}>0$ / $<0$ |
| changing direction | 改变方向 | $\frac{dy}{dx}=0$ 处 |
| root | 根 | 令导数为零解出的 $x$ 值 |
| continuous | 连续的 | 导数连续 ⇒ 只能在零点处变号 |
| factored form | 因式分解形式 | 便于读出零点与符号 |
| hydrostatic equation | 静水压方程 | $\frac{dP}{dz}=-\frac{g}{R_\alpha T}P$ |
| ideal gas law | 理想气体定律 | $\rho=\frac{P}{R_\alpha T}$ |
| differential equation | 微分方程 | 含未知函数导数的方程 |
| exponential decay | 指数衰减 | $P(z)=P_0e^{-kz}$ |
| drainage rate | 排水速率 | $\frac{dV}{dt}$，单位 $\mathrm{m^3\,hr^{-1}}$ |
| reservoir | 水库 / 蓄水体 | Q3.7 的应用背景 |
| natural logarithm | 自然对数 | $\ln(x)$，导数 $\frac1x$ |
| maths survival pack | 数学求生包 | 讲师对 handbook 末尾公式页的称呼，考试随卷提供 |
| Intended Learning Outcomes (ILOs) | 预期学习成果 | 每讲开头/结尾列出的学习目标 |

---

## 附：一页速记卡

```
三步法：SPLIT → DIFFERENTIATE → RECOMBINE

    最外层运算是……
      +/-  →  逐项求导
      套   →  chain:     dy/dx = du/dv · dv/dx
      ×    →  product:   dy/dx = u·v' + v·u'
      ÷    →  quotient:  dy/dx = (v·u' − u·v') / v²
                          ↑ v du 在前！分母 v²！

多层嵌套：从外往里剥，每剥一层乘一个因子，剥到只剩 x。
拆分判据：拆到每一块都能在基本求导表里直接查到为止。
收尾动作：提公因子 / 通分 / 约分，令导数=0 时只看分子。
自查手段：能展开的先展开硬算一遍对答案。
```
