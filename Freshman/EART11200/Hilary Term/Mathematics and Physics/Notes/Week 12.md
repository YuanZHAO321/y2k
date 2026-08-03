# Week 12 — 积分复习 (Revision: Integration)

> 课程：EART11200 *The Natural Scientist's Toolkit* — Mathematics and Physics（Hilary Term / 春季学期）
> 本周性质：**全课最后一周**，Exam Period。不教新内容，全部用于**积分部分（Week 6–9）的系统复习 + 2023–24 年真题精讲 + 考试提示**。
> 讲课日期：09-May（Revision Lecture — Integration）
>
> ⚠️ **周号说明**：复习幻灯片里出现的 "WEEK 6 / WEEK 7 / WEEK 8 / WEEK 9" 指的是本课程**内部的教学周编号**（即微分/积分模块的第几周），而大学的绝对学期周号本课程占第 20–34 周。**一律以文件夹周号为准：本笔记是 Week 12。** 幻灯片提到的 WEEK 6/7/8/9 恰好对应本课程文件夹的 Week 6/7/8/9，可以直接对应回去。

---

## 一、本周主题

**Revision: Integration —— 积分板块总复习。**

上周（Week 11）复习了微分（Week 1–5），本周把 **Week 6–9 的积分内容**串成一条线，然后用 **2023–24 学年真题**逐题演示解法，最后开放提问、给考试提示。

老师原话（转写）：

> "So last week we looked at differentiation as the revision topic, so this week we're going to cover the rest of the weeks which is our integration. So what I'm going to do again like I did last week was just do a recap week by week, pause for questions and then we're going to do the questions that we had last year's past paper exam."

本周结构：

| 阶段 | 内容 |
|---|---|
| 1 | Week 6 回顾：积分是微分的逆运算、常见积分表、不定积分 vs 定积分、分离变量法、放射性衰变 |
| 2 | Week 7 回顾：牛顿第二定律的四种（实用上三种）ODE 形式、斜面/自由落体/摩擦力建模 |
| 3 | Week 8 回顾：换元积分法（integration by substitution）8 步流程、静力学方程 |
| 4 | Week 9 回顾：二阶齐次线性 ODE、辅助方程、初值问题 vs 边值问题、Fick / Fourier 定律 |
| 5 | 2023–24 真题精讲：Q2（选积分）、Q4（定积分）、Q8（斜面 + 反向力）、Q9（人口 ODE）、Q10（静力学方程，留到 Practical 讲） |
| 6 | 考试答疑与提示 |

**配套的三份材料**：
- Lecture：`Revision_Integration.pdf/.md`（37 页幻灯片）+ 课堂转写；
- Practical：`2324_Exam(1).pdf/.md` —— **2023–24 年完整真题卷**，本周 Practical 就是做/讲这张卷子；
- 主手册：Crib Sheet §12.3（积分速查）、第 13 章（常数与物理定律）、第 14 章（**考试会提供的公式清单**）。

---

## 二、核心概念

本节是**知识梳理与串联**：把积分板块四周的方法组织成体系，说清它们的关系；再讲第 13 章五条物理定律的含义与应用场景。

### 2.0 全景地图：积分板块的逻辑链条

```
                    积分 = 微分的逆运算  (Week 6)
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
   不定积分(+d)           定积分(带上下限)        常见积分表
        │                     │                     │
        └──────────┬──────────┘                     │
                   ▼                                │
          【分离变量法 Separation of Variables】     │
          把 dy/dx = f(x)g(y) 拆成 dy/g(y)=f(x)dx  │
                   │                                │
        ┌──────────┼─────────────┬──────────────────┘
        ▼          ▼             ▼
   放射性衰变   牛顿第二定律   静力学方程(等温)
   (Week 6)     (Week 7)        (Week 8)
                                 │
                                 │ 温度随高度变化 → 被积函数变复杂
                                 ▼
                    【换元积分法 Integration by Substitution】
                     = 微分中链式法则的逆过程        (Week 8)
                                 │
                                 ▼
                     【二阶 ODE：积分两次 / 辅助方程】 (Week 9)
                                 │
                    ┌────────────┴────────────┐
                    ▼                         ▼
            初值问题 (IVP)             边值问题 (BVP)
        同一点给 y 和 y′            两端点各给一个条件
        牛顿定律类问题              Fick / Fourier 稳态问题
```

**一句话串联**：先会"反着微分"（表 + 不定/定积分）→ 遇到微分方程就"分离变量"再积 → 被积函数是"函数的函数"就"换元" → 出现二阶导数就"辅助方程或积两次" → 最后用初始条件/边界条件把常数定下来。

---

### 2.1 Week 6：积分的基本概念

#### (a) 积分是微分的逆运算

- 微分给我们**梯度（gradient / rate）**；积分给我们**绝对值（absolute value）**。
- 举例：如果导函数告诉你"水量随时间变化多快"，那么对它积分就告诉你"某一时刻有多少水"或"某段时间内水总共变了多少"。
- 符号 $\int$ 由 **Gottfried Wilhelm Leibniz** 在 17 世纪引入，表示"把无穷多个无穷小量加起来"（summation of infinitely many infinitesimally small quantities）。是拉长的 S = Sum。
- 几何直观：积分是把无数个小矩形加起来。$dx$ 是每个矩形底边的长度（即 $\Delta x$），$\int$ 上下标叫**积分限 (limits of integration)**。

$$\int_a^b f(x)\,dx \;=\; \lim_{\Delta x \to 0}\sum f(x)\,\Delta x$$

#### (b) 不定积分 (Indefinite integration)

**没有积分限**。**必须加常数 $+d$（或 $+C$）**。

$$\int 3x^2\,dx = x^3 + d$$

为什么要加常数？因为微分会把常数变成 0，所以原函数里原本是否有常数、是多少，从导数里看不出来。

> 老师原话："Always make sure that when you do indefinite integration you always add that constant at the end because that's a really really important thing because you don't know with that constant existed before."

例（Crib Sheet）：$\displaystyle\int x^2\,dx = \frac{x^3}{3} + d$

#### (c) 定积分 (Definite integration)

**有积分限**。先求积分，再代入上限、下限，**上限值减下限值**。**不需要加常数**（常数会互相抵消）。

$$\int_0^1 3x^2\,dx = \Big[x^3\Big]_0^1 = 1^3 - 0^3 = 1$$

例（Crib Sheet）：$\displaystyle\int_1^2 x^2\,dx = \left[\frac{x^3}{3}\right]_1^2 = \frac{8}{3}-\frac{1}{3} = \frac{7}{3}$

**物理意义**：对一个 rate 在 $[0,1]$ 上做定积分 = 这段区间内的**总变化量**。老师的例子：水以 $3x^2$ 的速率流进水箱，问 1 分钟后水箱里有多少水，就把速率在 0 到 1 之间积分。

#### (d) 分离变量法 (Separation of Variables)

给你一个一阶 ODE，把含 $y$ 的项全部搬到一边、含 $x$（或 $t$）的项全部搬到另一边，然后两边各自积分。

$$\frac{dy}{dx} = f(x)g(y) \;\Longrightarrow\; \int\frac{dy}{g(y)} = \int f(x)\,dx$$

> 老师原话："When you're given an ordinary differential equation you just rearrange it… bring all of the N's on this side and all of the t's on this side. And then what you'll end up doing is integrating and then eventually getting some sort of answer at the end."

#### (e) 放射性衰变 (Radioactive decay) —— 分离变量的范例

衰变律：单位时间的衰变数正比于现存不稳定核数。

$$\frac{dN}{dt} = -\lambda N$$

- $N$：不稳定原子核数目（无量纲计数）
- $t$：时间（s）
- $\lambda$：衰变常数 / decay rate（单位 $\mathrm{s^{-1}}$），每种同位素固定

**解法（分离变量）**：

$$\frac{dN}{N} = -\lambda\,dt \;\Longrightarrow\; \int\frac{dN}{N} = -\lambda\int dt \;\Longrightarrow\; \ln N = -\lambda t + C$$

代入 $t=0$ 时 $N=N_0$，得 $C=\ln N_0$：

$$\ln\frac{N}{N_0} = -\lambda t \;\Longrightarrow\; \boxed{N = N_0 e^{-\lambda t}}$$

**半衰期 (half-life)**：$N=N_0/2$ 时的时间

$$t_{1/2} = \frac{\ln 2}{\lambda} \qquad\Longleftrightarrow\qquad \lambda = \frac{\ln 2}{t_{1/2}}$$

---

### 2.2 Week 7：用牛顿定律做积分

#### (a) 牛顿第二定律的四种写法

$$F = ma$$

- $F$：作用在物体上的**净力**（N = kg·m·s⁻²）
- $m$：质量（kg）
- $a$：加速度（m·s⁻²）

因为 $a = \dfrac{dv}{dt} = \dfrac{d^2x}{dt^2} = v\dfrac{dv}{dx}$（最后一个由链式法则：$\frac{dv}{dt}=\frac{dv}{dx}\frac{dx}{dt}=v\frac{dv}{dx}$），所以：

| 形式 | 表达式 | 什么时候用 |
|---|---|---|
| 代数形式 | $F = ma$ | 只问力/加速度 |
| **速度–时间** | $F = m\dfrac{dv}{dt}$ | 题目把 **velocity 和 time** 联系起来 |
| **位移–时间** | $F = m\dfrac{d^2x}{dt^2}$ | 题目把 **distance 和 time** 联系起来 |
| **速度–位移** | $F = mv\dfrac{dv}{dx}$ | 题目把 **velocity 和 distance** 联系起来 |

> ⚠️ **老师明确的考试要求**："I will expect you to remember these three formulations for the exam because who knows they may come up in the exam. So I would if I was you remember and revise all three of those formulations. Just remember particularly the only one that you really need to make sure you remember is the $v\,dv/dx$ right because that was a slightly different formula."

**解题第一步永远是**：读题，看它要你把哪两个量联系起来 → 选对应的形式。

#### (b) 建立 ODE 的方法：把力沿"运动方向"求和

- **真空中自由下落**：唯一的力是 $mg$ → $m\frac{dv}{dt}=mg$ → $\dfrac{dv}{dt}=g$
- **沿斜面下滑（角度 $\theta$，无摩擦）**：重力 $mg$ 竖直向下，但运动方向是沿斜面，用三角函数分解：沿斜面分量 $mg\sin\theta$，垂直斜面（法向）分量 $mg\cos\theta$。

$$m\frac{dv}{dt} = mg\sin\theta \;\Longrightarrow\; \frac{dv}{dt} = g\sin\theta$$

- **有摩擦力 / 空气阻力**：这些力**总是与运动方向相反**。

> 老师原话："You always sum up the forces in the direction of travel… If I asked you to look at the direction of travel at this you would say $F_G - F_F$… **Always look at the forces in the direction of travel.**"

- 法向不动的原因（第 13 章解释）：斜面给物体一个**大小相等、方向相反**的支持力（牛顿第三定律）。

#### (c) 动能与做功

功：

$$W = F\,s$$

- $W$：做的功（J，或 N·m）
- $F$：力（N）
- $s$：位移（m）

例：20 N 的力沿 3 m 路径作用 → 转移了 60 J 的功。

**从 $F = mv\frac{dv}{dx}$ 推动能定理**：沿路径 $dx$ 做的功是 $F\,dx$，总功 $=\int F\,dx$：

$$\int F\,dx = \int_u^v mv\,dv = \frac{1}{2}mv^2 - \frac{1}{2}mu^2$$

- $v$：末速度，$u$：初速度。这解释了为什么"同样的能量给 20 kg 球和 20 g 球，小球速度更大"。

---

### 2.3 Week 8：换元积分法 (Integration by Substitution)

#### (a) 为什么需要它

碰到**函数的函数 (function of functions)**，标准积分表直接用不了。例如 $\displaystyle\int (3x+2)^4\,dx$。

**换元积分 = 微分中链式法则的逆过程。**

> 老师原话："Integration by substitution is essentially the reverse process of the chain rule in differentiation."

#### (b) 怎么选 $u$ —— 老师给的黄金法则

> "Generally what I would say is **the substitution should just be whatever is inside the function**. So for example if it was $1/(x+1)$ then I would say the substitution would be $x+1$. If it was $\sin(3x+2)$ I would say use $3x+2$. Just use whatever substitution is inside the function, it just makes your life so much easier."

**即：令 $u$ = 括号里/函数内部的那一坨。** 目标是换完之后能直接查标准积分表。

#### (c) 完整 8 步流程（幻灯片版，含新积分限）

以 $\displaystyle y = \int_{-1}^{1}(3x+2)^4\,dx$ 为例：

1. **写出最简形式的积分**：$\displaystyle\int_{-1}^{1}(3x+2)^4\,dx$
2. **令新变量**：$u = 3x+2$
3. **反解旧变量**：$x = \dfrac{u-2}{3} = \dfrac{1}{3}u - \dfrac{2}{3}$
4. **对新变量求导**：$\dfrac{dx}{du} = \dfrac{1}{3}$
5. **得到 $dx$ 的表达式**：$dx = \dfrac{1}{3}\,du = \dfrac{du}{3}$
6. **（定积分才需要）换积分限**：
   - $x=-1 \Rightarrow u = 3(-1)+2 = -1$
   - $x=1 \Rightarrow u = 3(1)+2 = 5$
7. **代入原积分**：$\displaystyle\int_{-1}^{5} u^4\,\frac{du}{3} = \frac{1}{3}\int_{-1}^{5}u^4\,du$
8. **正常积分并求值**：$\dfrac{1}{3}\left[\dfrac{u^5}{5}\right]_{-1}^{5} = \dfrac{1}{15}\big(5^5 - (-1)^5\big) = \dfrac{3125+1}{15} = \dfrac{3126}{15} = 208.4$

> **不定积分**版本：跳过第 6 步，第 8 步积完后**加常数 $+d$**，并**把 $u$ 换回 $x$**。

**Crib Sheet 的不定积分例子** $\displaystyle\int (x+4)^2\,dx$：
令 $u=x+4$ → $x=u-4$ → $\frac{dx}{du}=1$ → $dx=du$ →
$\displaystyle\int u^2\,du = \frac{u^3}{3}+d = \frac{(x+4)^3}{3}+d$

其定积分版本（$x=0$ 到 $x=1$）：限变为 $u=4$ 到 $u=5$ →
$\left[\dfrac{u^3}{3}\right]_4^5 = \dfrac{125-64}{3} = \dfrac{61}{3} \approx 20.333$

#### (d) 一个常被问到的细节（课堂问答）

学生问：第 7 步到第 8 步，那个 $\frac13$ 是被提出来了吗？

老师答：**是的，因为 3 不依赖于 $u$，可以提到积分号外面，最后再乘回去**。你也可以留在里面，那样分母就会变成 15。两种都对，选你顺手的。老师本人习惯提出来，"这样不容易在最后犯低级错误"。

> **考试提示**："In the exam, I won't necessarily expect you to write down all eight steps. I'm just saying I'm doing it step by step so you can understand the steps."

#### (e) 静力学方程 —— 换元积分的典型应用

- **温度恒定**的静力学方程 → 只需**分离变量**；
- **温度随高度变化**（有 lapse rate）→ **必须用换元积分**。

> 老师原话："just one very, very small change and it becomes a much more difficult challenge."

（详细推导见 §2.6(e) 与 §4 的 Q10。）

---

### 2.4 Week 9：二阶常微分方程 (Second-order ODEs)

#### (a) 什么是二阶 ODE

含**二阶导数**的微分方程。本课只处理**齐次、线性、二阶 ODE (homogeneous, linear, second-order ODE)**：

$$a\frac{d^2y}{dx^2} + b\frac{dy}{dx} + cy = 0$$

等价记号：$ay'' + by' + cy = 0$，其中 $a,b,c$ 是常数。

> 老师说这个式子本身"if it becomes the only form I'll probably give it to you"（大概率会给你）。

#### (b) 三步解法

**第 1 步：写辅助方程 (auxiliary equation) 并求根**

$$a\lambda^2 + b\lambda + c = 0 \qquad\Longrightarrow\qquad \lambda = \frac{-b \pm \sqrt{b^2-4ac}}{2a}$$

> ⚠️ 老师："Use this again, **I won't give you this**, I'll expect you to know this if that came up."（求根公式**不提供**，必须背。）

**第 2 步：根据根的类型选通解**

| 情况 | 条件 | 通解 |
|---|---|---|
| 两根**实且不等** | $b^2-4ac>0$，$\lambda_1 \neq \lambda_2$ | $y = Ae^{\lambda_1 x} + Be^{\lambda_2 x}$ |
| 两根**实且相等** | $b^2-4ac=0$，$\lambda_1 = \lambda_2$ | $y = (A + Bx)e^{\lambda_1 x}$ |
| 两根**复数** | $b^2-4ac<0$ | **本课不考虑** |

> ⚠️ 老师："**I won't give you these general solutions**, so you just know which general solution is applicable in what setting."（通解公式**不提供**，必须背，并且要会判断用哪个。）

**课堂问答**：学生问 $\lambda_1$ 是不是永远对应 "+"、$\lambda_2$ 对应 "−"？
老师答：**两个都是加号（$Ae^{\lambda_1 x} + Be^{\lambda_2 x}$），谁是 $\lambda_1$ 谁是 $\lambda_2$ 无所谓**。比如根是 2 和 3，放哪边都行。只要注意根本身的正负号别搞错。

**第 3 步：用初始条件定 $A$ 和 $B$**

因为合并了两个解，需要知道各自贡献多少，所以有两个新常数 $A, B$，需要**两个条件**，比如：

$$y = 0 \text{ 且 } y' = 1 \quad \text{当 } x = 0$$

代入后得到**联立方程组 (simultaneous equations)**，解出 $A, B$。

#### (c) 初值问题 vs 边值问题（重要区分）

| | **Initial Value Problem (IVP)** | **Boundary Value Problem (BVP)** |
|---|---|---|
| 中文 | 初值问题 | 边值问题 |
| 条件给在哪 | **同一点**给 $y$ 和 $y'$（通常 $x=0$） | **两个不同点**各给一个条件（$x=x_0$ 和 $x=x_1$） |
| 直觉 | "从这里出发，速度是多少" | "解必须同时穿过这两点" |
| 典型例子 | 牛顿运动定律问题 | Fick 定律、Fourier 定律的稳态问题 |

> 老师原话（关于 BVP）："you use **both** the conditions because you can't just use the fact that everything happens on the initial conditions. You need a condition here and a condition here and you can just use that function to interpolate between the two."

#### (d) Fick / Fourier 稳态 → 最简单的二阶 ODE

稳态假设下，Fick 第二定律和 Fourier 第二定律都退化为：

$$\frac{d^2\Theta}{dx^2} = 0 \qquad\text{或}\qquad \frac{d^2T}{dx^2} = 0$$

**直接积分两次**：

$$\frac{d\Theta}{dx} = A \;\Longrightarrow\; \Theta = Ax + B$$

结果是**线性的**（浓度/温度随距离线性变化），再用两个边界条件解出 $A, B$。

> 老师原话："these are Fick and Fourier laws which essentially you would just integrate — the simplest form I would give it to you is something like this which has steady state conditions and ultimately that would be linear at the end and you would just solve and find A, B."

---

### 2.5 第 13 章：常数与物理定律（概览）

> 主手册明说："**You are not expected to memorise the contents of this Chapter**, as it is designed to supplement the course."（本章内容不要求背诵，是补充材料。）
> 但**理解这五条定律的物理含义、符号与单位是必须的**，因为它们是积分题的应用背景。

五条定律的共同点：**它们都是（或都能化成）微分方程，而这门课就是教你怎么把它们积出来。**

| 定律 | 微分方程形式 | 积分方法 | 出现在 |
|---|---|---|---|
| 放射性衰变 | $\frac{dN}{dt}=-\lambda N$ | 分离变量 | Week 6 |
| 牛顿第二定律 | $m\frac{dv}{dt}=\sum F$ | 分离变量 | Week 7 |
| 静力学方程（等温） | $\frac{dP}{dz}=-\frac{Pg}{R_aT}$ | 分离变量 | Week 8 |
| 静力学方程（变温） | $\frac{dP}{dz}=-\frac{Pg}{R_a(T_s-\alpha z)}$ | **换元积分** | Week 8 |
| Fourier / Fick（稳态） | $\frac{d^2T}{dx^2}=0$ | 积分两次 + 边界条件 | Week 9 |

---

### 2.6 第 13 章五节详解

#### (a) §13.4 放射性衰变 (Radioactive decay)

**为什么会衰变**：某些同位素不稳定，因为中子（"胶水"）不够，无法把质子束缚住；于是自发衰变成子核 (daughter nuclei)。三种衰变按放出的高能粒子/辐射命名：$\alpha$、$\beta$、$\gamma$。

**Alpha (α) 衰变**：放出一个 α 粒子（= 氦核 $^4_2\mathrm{He}$），子核**质量数 −4，原子序数 −2**。

$$^{238}_{\;92}\mathrm{U} \;\longrightarrow\; ^{234}_{\;90}\mathrm{Th} + ^{4}_{2}\mathrm{He}$$

- **注意：这不是化学反应**，因为不涉及电子转移。
- 为什么会发生？衰变前 $^{238}$U 有 92 质子、146 中子，中子/质子比 $=146/92=1.587$；衰变后 $=144/90=1.60$。**比值升高一点点就足以让子核更稳定。**（手册原文把 1.587 误写成 "1.587%"，是排版错误。）

**Beta (β) 衰变**：放出 β 粒子（电子或正电子）。

- $\beta^-$（电子发射）：中子 → 质子 + 电子 + 反中微子
  $$n \longrightarrow p + e^- + \bar{\nu}_e$$
  发生原因：中子太多。$\beta^-$ 衰变后子核常处于**激发态**，随后放出 γ 射线。
- $\beta^+$（正电子发射）：质子 → 中子 + 正电子 + 中微子
  $$p \longrightarrow n + e^+ + \nu_e$$
  发生原因：中子太少。**只有当子核的结合能高于母核时才能发生。**
- 同样**不是化学反应**（电子不参与成键）。

**Gamma (γ) 衰变**：处于激发态的核跃迁到较低能态，放出**穿透力极强的高能电磁辐射**。原子序数、质量数都不变。

**衰变方程**（α 和 β 衰变适用）：

$$\frac{dN}{dt} = -\lambda N \qquad\Longrightarrow\qquad N = N_0 e^{-\lambda t} \qquad\Longrightarrow\qquad \lambda = \frac{\ln 2}{t_{1/2}}$$

- $N_0$：$t=0$ 时的不稳定核数
- $t_{1/2}$：半衰期，初始核数衰减到一半所需时间

**为什么这个定律"合理"**：不稳定核越多，单位时间观察到的衰变自然越多——正比关系在物理里很常见。

#### (b) §13.5 牛顿定律 (Newton's laws)

**历史背景**：20 世纪以前，物理世界的理解完全建立在**经典力学 (classical mechanics)**、更具体地说是**牛顿物理 (Newtonian Physics)** 上。这个框架源自"科学革命"，参与者包括哥白尼 (Copernicus)、伽利略 (Galileo)、牛顿 (Newton)。1543 年哥白尼提出**日心说**，为伽利略、开普勒 (Kepler)、笛卡尔 (Descartes) 铺路，共同推翻亚里士多德世界观。牛顿三定律首次发表于 1687 年的《自然哲学的数学原理》(*Philosophiae Naturalis Principia Mathematica*，简称 *Principia*)，本意是解释**为什么行星轨道是椭圆而不是圆**，但适用范围远超行星运动。

**三定律**：

1. **惯性定律 (Law of Inertia)**：静止或匀速直线运动的物体，在不受外力作用时保持原状态。
2. **力与动量定律 (Law of Force and Momentum)**：物体动量的变化率正比于所受的力，变化方向与力同向。
3. **作用与反作用定律 (Law of Action and Reaction)**：两物体相互作用时，彼此施加大小相等、方向相反的力。

**第二定律**：$F = ma$，及其 ODE 变形（见 §2.2(a)）。

**动能与做功**：$W = Fs$；$\int F\,dx = \frac12 mv^2 - \frac12 mu^2$（见 §2.2(c)）。

#### (c) §13.6 热传导与 Fourier 定律 (Heat transfer and Fourier's laws)

**背景**：1822 年法国物理学家/数学家 **Joseph Fourier** 提出：**热传导产生的热通量正比于温度梯度的大小，方向与之相反**（heat flux is proportional to the magnitude of the temperature gradient and opposite to it in sign）。即热从热处流向冷处。

**什么是热传导 (thermal conduction)**：热从物体较热部分传到较冷部分、使温度趋于均衡的过程。
- 与**对流 (convection)** 的区别：热传导**不涉及宏观位移**，是粒子（分子、原子、电子）之间高能→低能的**直接能量传递**。
- 与**辐射 (radiation)** 的区别：**真空中没有热传导**。

**Fourier 第一定律**：

热流率形式（通过厚度 $L$、面积 $A$ 的板）：

$$Q = -kA\frac{\Delta T}{L}$$

- $Q$：传递的热量/热流率（W）
- $k$：**热导率 thermal conductivity**（W·m⁻¹·K⁻¹）
- $A$：垂直于传热方向的截面积（m²）
- $L$：厚度（m）
- $\Delta T$：温度差（K）

一维热通量形式（热通量 = 单位面积、单位时间的能量流，注意 1 W = 1 J/s）：

$$q = -k\frac{dT}{dx}$$

- $q$：热通量（W·m⁻²）

向量形式（$\nabla$ 是第 11 章的 Grad 算子）：

$$\mathbf{q} = -k\nabla T$$

- $\mathbf{q}$：热通量矢量（W·m⁻²），$T$：温度（K）

**Fourier 第二定律**：考虑 1 m³ 的盒子、厚度 $\delta x$，热进入盒子的速率 $R$（W·m⁻³）等于一侧进入与另一侧流出之差——即**梯度的梯度 (a gradient of a gradient)**：

$$R = k\frac{d^2T}{dx^2}$$

若盒子温度处于**稳态 (steady state)**，$R = 0$：

$$\frac{d^2T}{dx^2} = 0 \qquad\text{向量形式：}\qquad \nabla^2 T = 0$$

**这就是 Week 9 里"积分两次"的那个二阶 ODE。**

#### (d) §13.7 物质输运与 Fick 定律 (Mass transfer and Fick's laws)

**背景**：继 Fourier 之后，生理学家 **Adolf Fick** 发现，由**布朗运动 (Brownian motion，即随机热运动)** 驱动的**质量输运**遵循非常相似的定律：**质量从高浓度流向低浓度**。

**微观图像**：气体分子按其温度对应的热能运动，彼此碰撞改变方向；密闭盒子里这些碰撞就形成对壁面的压强（理想气体方程）。若在盒子中央注入一团分子，热运动会让它们**扩散 (diffuse)** 开来；打开一侧，气体最终扩散出去。粒子随机扩散后，最终从高浓度区均匀分布到低浓度区（扩散仍在继续，但**净通量为零**）。

**Fick 第一定律（一维）**：

$$J = -D\frac{d\Theta}{dx}$$

| 符号 | 含义 | 单位（示例） |
|---|---|---|
| $J$ | 扩散通量 diffusive flux（单位面积单位时间的物质量） | g·cm⁻²·s⁻¹ |
| $\Theta$ | 浓度 concentration（单位体积的量） | molecules·cm⁻³ |
| $d\Theta/dx$ | 浓度梯度 | molecules·cm⁻⁴ |
| $D$ | 扩散系数 diffusion coefficient | cm²·s⁻¹ |

**关于 $D$**：$D$ 正比于扩散粒子速度的平方，因此取决于**温度、流体黏度、碰撞分子的大小**。

**向量形式**：$\mathbf{J} = -D\nabla\Theta$

**Fick 第二定律**：预测扩散如何使浓度随时间变化。第一定律给的是通量，把通量再写成微分方程：

$$\frac{\partial \Theta}{\partial t} = D\frac{\partial^2 \Theta}{\partial x^2}$$

> ⚠️ 这是**偏微分方程 (partial differential equation, PDE)**。**本课不解 PDE**（"they are very difficult to solve"）。

**稳态情形**（$\partial\Theta/\partial t = 0$）：

$$D\nabla^2\Theta = 0 \qquad\text{一维：}\qquad \frac{d^2\Theta}{dx^2} = 0$$

对它积分两次即可得到浓度沿某一维度的变化表达式（线性）。

**注意 Fourier 与 Fick 的高度对称性**：都是"通量 = −(系数) × 梯度"，都在稳态下退化为"二阶导数 = 0"。**记住一个就等于记住两个。**

#### (e) §13.8 大气压强与静力学方程 (Atmospheric pressure and the hydrostatic equation)

**物理起点**：地表以上某点的压强来自**其上方空气的重量**（深水中同理，只是换成水的重量）。

重量：

$$W = mg$$

- $m$：质量（kg），$g$：地球重力加速度（9.8 m·s⁻²）。**重量就是我们在牛顿第二定律里用的重力。**

**推导**：一个 1 m³、密度 $\rho$（kg·m⁻³）的空气立方体，其重量 $= \rho \times 1 \times g$（质量 $=V\rho$，$V=1$ m³）。压强 = 单位面积的力，除以 1 m² 得：

$$P = \rho g$$

在 1 m² 截面的气柱中，向上移动 $\Delta z = 1$ m，压强变化 $\Delta P = -\rho g \Delta z$。因此：

$$\boxed{\frac{dP}{dz} = -\rho g}$$

**含义：压强随高度的梯度 = −（空气密度 × 重力）。** 负号表示越高压强越低。

**代入理想气体定律** $\rho = \dfrac{P}{R_a T}$，其中 $R_a = 287\ \mathrm{J\,kg^{-1}\,K^{-1}}$（干空气比气体常数）：

$$\frac{dP}{dz} = -\frac{Pg}{R_a T}$$

**等温假设下的解（分离变量）**：

$$\frac{dP}{P} = -\frac{g}{R_aT}dz \;\Longrightarrow\; \ln\frac{P}{P_0} = -\frac{gz}{R_aT} \;\Longrightarrow\; P = P_0\,e^{-\frac{gz}{R_aT}}$$

**实际情况**：温度不是常数，大气中温度**随高度约每 km 下降 10 °C**（lapse rate）。设

$$T = T_s - \alpha z$$

- $T_s$：地表温度（K），$\alpha$：递减率 lapse rate（K·m⁻¹）

静力学方程变为：

$$\frac{dP}{dz} = -\frac{Pg}{R_a(T_s - \alpha z)}$$

**这个必须用换元积分**，解析解为：

$$\boxed{P = P_0\left(\frac{T_s - \alpha z}{T_s}\right)^{\frac{g}{\alpha R_a}}}$$

（完整推导见 §四 Q10。）

---

## 三、公式与图表

> 本节是本周**最有价值的产出**：把 Crib Sheet §12.3 的积分公式表、第 13 章的常数与物理定律表、第 14 章的考试提供公式清单**全部完整重排**。

### 3.1 常见积分表 (Common Integrals) —— Crib Sheet §12.3 + 复习幻灯片

这是**本课需要用到的全部常见积分**。左列是导函数 $\frac{dy}{dx}$，右列是积分结果 $y$（$d$ 为积分常数）。

| 导函数 $\dfrac{dy}{dx}$ | 积分 $y = \int \frac{dy}{dx}\,dx$ | 备注 |
|---|---|---|
| $0$ | $d$ | 常数的导数是 0，反过来 0 积分成常数 |
| $\text{constant } c$ | $cx + d$ | |
| $x$ | $\dfrac{x^2}{2} + d$ | 是下一行 $n=1$ 的特例 |
| $x^n$ | $\dfrac{x^{n+1}}{n+1} + d$ | **幂次 +1，再除以新幂次**（$n \neq -1$） |
| $e^x$ | $e^x + d$ | 自己积分成自己 |
| $ke^{kx}$ | $e^{kx} + d$ | 等价地 $\displaystyle\int e^{kx}dx = \frac{1}{k}e^{kx}+d$ |
| $\dfrac{1}{x}$ | $\ln(x) + d$ | 补上了 $x^n$ 规则中 $n=-1$ 的缺口 |
| $\cos(x)$ | $\sin(x) + d$ | |
| $\sin(x)$ | $-\cos(x) + d$ | **负号在这里！** |

> 老师提醒："The more you practice these procedures, the easier it will become to apply them without looking them up. Use your maths survival pack when needed!"
> 又说："**Most of these will be on the formula table that you will get in the exam** so if you do forget them — particularly the one I always forget is where the sine and the minus goes… **double check things**."

**微分 ↔ 积分对照记忆（三角部分最容易错）**：

| | 微分 | 积分 |
|---|---|---|
| $\sin$ | $\dfrac{d}{dx}\sin x = \cos x$ | $\displaystyle\int \sin x\,dx = -\cos x + d$ |
| $\cos$ | $\dfrac{d}{dx}\cos x = -\sin x$ | $\displaystyle\int \cos x\,dx = \sin x + d$ |

**口诀**：微分时**负号跟着 cos**（cos 求导出负），积分时**负号跟着 sin**（sin 积分出负）。

### 3.2 不定积分 vs 定积分 vs 分离变量 —— 三种基本操作对照

| | 不定积分 Indefinite | 定积分 Definite | 分离变量 Separation of Variables |
|---|---|---|---|
| 有无积分限 | 无 | 有 | 视情况（两种都可以） |
| 要不要 $+C$ | **必须加** | 不需要（会抵消） | 不定积分版本要加 |
| 典型写法 | $\int 3x^2dx = x^3+d$ | $\int_0^1 3x^2dx=[x^3]_0^1=1$ | $\int\frac{dN}{N}=-\lambda\int dt$ |
| 意义 | 还原原函数（差一个常数） | 区间内的总变化量 / 曲线下面积 | 解一阶 ODE |
| 常数怎么定 | 需要初始条件 | 不需要 | 初始条件 或 直接用带限积分 |

### 3.3 换元积分法速查

| 步骤 | 操作 | 不定积分 | 定积分 |
|---|---|---|---|
| 1 | 化简积分式 | ✓ | ✓ |
| 2 | 令 $u = $ 函数内部那一坨 | ✓ | ✓ |
| 3 | 反解 $x = x(u)$ | ✓ | ✓ |
| 4 | 求 $\dfrac{dx}{du}$ | ✓ | ✓ |
| 5 | 得 $dx = (\cdots)du$ | ✓ | ✓ |
| 6 | **换积分限** $x_{lo},x_{hi} \to u_{lo},u_{hi}$ | ✗ 跳过 | ✓ **必做** |
| 7 | 代入，用标准积分表积分 | ✓ | ✓ |
| 8 | 收尾 | **加 $+d$，把 $u$ 换回 $x$** | 直接代 $u$ 的新限求值 |

### 3.4 二阶齐次线性 ODE 速查

$$a\frac{d^2y}{dx^2} + b\frac{dy}{dx} + cy = 0$$

| 步骤 | 内容 | 考试是否提供 |
|---|---|---|
| ① 辅助方程 | $a\lambda^2+b\lambda+c=0$ | 方程本身老师说"probably give it to you" |
| ② 求根 | $\lambda = \dfrac{-b\pm\sqrt{b^2-4ac}}{2a}$ | ❌ **不提供，必须背** |
| ③ 通解（$\lambda_1\neq\lambda_2$，实） | $y = Ae^{\lambda_1x}+Be^{\lambda_2x}$ | ❌ **不提供，必须背** |
| ③′ 通解（$\lambda_1=\lambda_2$） | $y = (A+Bx)e^{\lambda_1x}$ | ❌ **不提供，必须背** |
| ③″ 复根 | $b^2-4ac<0$ | 本课**不涉及** |
| ④ 定常数 | 用初始条件解联立方程求 $A,B$ | — |

---

### 3.5 第 13 章 表 13.1：导出单位 (Derived Units)

| 物理量 Entity | 缩写 Abbreviation | 名称 Name |
|---|---|---|
| 力 Force | $\mathrm{N = kg\cdot m/s^2}$ | newton 牛顿 |
| 能量 Energy | $\mathrm{J = kg\cdot m^2/s^2}$ | joule 焦耳 |
| 功率 Power | $\mathrm{W = J/s}$ | watt 瓦特 |
| 压强 Pressure | $\mathrm{Pa = N/m^2}$ | pascal 帕斯卡 |
| 频率 Frequency | $\mathrm{Hz = 1/s}$ | hertz 赫兹 |
| 电势 Electric potential | $\mathrm{V = J/C}$ | volt 伏特 |
| 电容 Capacitance | $\mathrm{F = C/V}$ | farad 法拉 |
| 电荷 Charge | $\mathrm{C = s\cdot A}$ | coulomb 库仑 |
| 电阻 Resistance | $\mathrm{\Omega = V/A}$ | ohm 欧姆 |
| 磁场 Magnetic field | $\mathrm{T = N/(A\cdot m)}$ | tesla 特斯拉 |
| 核衰变率 Nuclear decay rate | $\mathrm{Bq = 1/s}$ | becquerel 贝可勒尔 |

### 3.6 第 13 章 表 13.2：基本单位 (Fundamental Units)

| 物理量 Entity | 缩写 | 名称 |
|---|---|---|
| 质量 Mass | $\mathrm{kg}$ | kilogram 千克 |
| 时间 Time | $\mathrm{s}$ | second 秒 |
| 电流 Current | $\mathrm{A}$ | ampere 安培 |

> 注：手册只列了这三个（长度 m、温度 K、物质的量 mol、光强 cd 未列出，但全课都在用）。

### 3.7 第 13 章 表 13.3：物理常数 (Physical constants)

| 常数 | 定义 | 数值与单位 |
|---|---|---|
| $g$ | 地球重力加速度 earth's gravitational constant | $9.80\ \mathrm{m\,s^{-2}}$ |
| $c$ | 真空光速 speed of light in vacuum | $3.00\times10^{8}\ \mathrm{m\,s^{-1}}$ |
| $e$ | 电子电荷 charge of electron | $1.60\times10^{-19}\ \mathrm{C}$ |
| $m_e$ | 电子质量 mass of electron | $9.11\times10^{-31}\ \mathrm{kg}$ |
| $m_n$ | 中子或质子质量 mass of neutron or proton | $1.67\times10^{-27}\ \mathrm{kg}$ |
| $N_A$ | 阿伏伽德罗常数 Avogadro's number | $6.022\times10^{23}\ \mathrm{molecules/mol}$ |
| $k_B$ | 玻尔兹曼常数 Boltzmann's constant | $1.38\times10^{-23}\ \mathrm{J/K}$ |
| $R$ | 普适气体常数 universal gas constant | $8.31\ \mathrm{\dfrac{J}{mol\,K}} = 0.0821\ \mathrm{\dfrac{l\,atm}{mol\,K}}$ |
| $c_w$ | 水的比热 specific heat of water | $1\ \mathrm{cal/(g\,K)}$ |
| $1\ \mathrm{cal}$ | 卡路里 calorie | $4.186\ \mathrm{J}$ |
| $\sigma$ | 斯特藩–玻尔兹曼常数 Stefan-Boltzmann constant | $5.67\times10^{-8}\ \mathrm{\dfrac{W}{m^2\,K^4}}$ |

**课程另外常用但不在此表**：干空气比气体常数 $R_a = 287\ \mathrm{J\,kg^{-1}\,K^{-1}}$（静力学方程用）。

### 3.8 第 13 章 表 13.4：十的幂次与词头 (Powers of Ten / Metric Prefixes)

| 词头 Prefix | 符号 Symbol | 数值 Value |
|---|---|---|
| tera | T | $10^{12}$ |
| giga | G | $10^{9}$ |
| mega | M | $10^{6}$ |
| kilo | k | $10^{3}$ |
| hecto | h | $10^{2}$ |
| deka | da | $10^{1}$ |
| deci | d | $10^{-1}$ |
| centi | c | $10^{-2}$ |
| milli | m | $10^{-3}$ |
| nano | n | $10^{-9}$ |
| pico | p | $10^{-12}$ |
| femto | f | $10^{-15}$ |

> ⚠️ **手册漏了 micro (μ, $10^{-6}$)**——从 milli ($10^{-3}$) 直接跳到 nano ($10^{-9}$)。自己补上：**micro, μ, $10^{-6}$**（真题 Q5 里的"micrograms per cubic metre"就用到）。

### 3.9 第 13 章 表 13.5：常用几何公式 (Useful Formulae)

| 定义 | 公式 |
|---|---|
| 圆的周长（半径 $r$，直径 $d$） | $C = 2\pi r = \pi d$ |
| 圆的面积（半径 $r$，直径 $d$） | $A = \pi r^2 = \pi d^2/4$ |
| 球的表面积（半径 $r$） | $A = 4\pi r^2$ |
| 球的体积（半径 $r$） | $V = \dfrac{4}{3}\pi r^3$ |

### 3.10 第 13 章 表 13.6：典型不稳定同位素

| 母核 Parent atom | 放射粒子 | 能量 Energy | 半衰期 Half-life |
|---|---|---|---|
| $^{235}$U | $\alpha$ | 4.52 MeV | $7.1\times10^{8}$ 年 |
| $^{238}$U | $\alpha$ | 4.18 MeV | $4.5\times10^{9}$ 年 |
| $^{232}$Th | $\alpha$ | 3.98 MeV | $1.4\times10^{10}$ 年 |
| $^{222}$Rn | $\alpha$ | 5.49 MeV | 3.825 天 |
| $^{14}$C | $\beta$ | 0.56 MeV | 5670 年 |

### 3.11 第 13 章 表 13.7：常见材料的热导率

| 材料 Material | 热导率 $k$（$\mathrm{W\,m^{-1}\,K^{-1}}$） |
|---|---|
| 0 °C 的空气 Air at 0 °C | 0.024 |
| 铝 Aluminium | 205.0 |
| 黄铜 Brass | 109.0 |
| 混凝土 Concrete | 0.8 |
| 铜 Copper | 385.0 |
| 玻璃 Glass | 0.8 |
| 泡沫塑料 Styrofoam | 0.01 |
| 木材 Wood | 0.12–0.04 |

> **规律**：金属（铜、铝、黄铜）热导率极高（10²量级）；建材（混凝土、玻璃）约 1；保温材料（空气、泡沫塑料、木材）低于 0.1。这就是保温层为什么用"困住空气"的材料。

### 3.12 五条物理定律汇总表（符号 · 单位 · 用途）

| 定律 | 方程 | 符号含义与单位 |
|---|---|---|
| **放射性衰变** | $\dfrac{dN}{dt}=-\lambda N$；$N=N_0e^{-\lambda t}$；$\lambda=\dfrac{\ln 2}{t_{1/2}}$ | $N$ 不稳定核数；$\lambda$ 衰变常数 (s⁻¹)；$t_{1/2}$ 半衰期 (s) |
| **牛顿第二定律** | $F=ma=m\dfrac{dv}{dt}=m\dfrac{d^2x}{dt^2}=mv\dfrac{dv}{dx}$ | $F$ 净力 (N)；$m$ 质量 (kg)；$a$ 加速度 (m·s⁻²)；$v$ 速度 (m·s⁻¹)；$x$ 位移 (m) |
| **功与动能** | $W=Fs$；$\displaystyle\int F\,dx=\tfrac12mv^2-\tfrac12mu^2$ | $W$ 功 (J = N·m)；$s$ 位移 (m)；$u$ 初速，$v$ 末速 (m·s⁻¹) |
| **Fourier 第一定律** | $Q=-kA\dfrac{\Delta T}{L}$；$q=-k\dfrac{dT}{dx}$；$\mathbf{q}=-k\nabla T$ | $Q$ 热流率 (W)；$q$ 热通量 (W·m⁻²)；$k$ 热导率 (W·m⁻¹·K⁻¹)；$A$ 面积 (m²)；$L$ 厚度 (m)；$T$ 温度 (K) |
| **Fourier 第二定律** | $R=k\dfrac{d^2T}{dx^2}$；稳态 $\dfrac{d^2T}{dx^2}=0$，$\nabla^2T=0$ | $R$ 单位体积产热率 (W·m⁻³) |
| **Fick 第一定律** | $J=-D\dfrac{d\Theta}{dx}$；$\mathbf{J}=-D\nabla\Theta$ | $J$ 扩散通量 (g·cm⁻²·s⁻¹)；$\Theta$ 浓度 (molecules·cm⁻³)；$D$ 扩散系数 (cm²·s⁻¹) |
| **Fick 第二定律** | $\dfrac{\partial\Theta}{\partial t}=D\dfrac{\partial^2\Theta}{\partial x^2}$；稳态 $\dfrac{d^2\Theta}{dx^2}=0$ | PDE，本课**不解**，只用稳态形式 |
| **重量** | $W = mg$ | $W$ 重量 (N)；$g=9.8\ \mathrm{m\,s^{-2}}$ |
| **静力学方程** | $\dfrac{dP}{dz}=-\rho g=-\dfrac{Pg}{R_aT}$ | $P$ 压强 (Pa)；$z$ 高度 (m)；$\rho$ 空气密度 (kg·m⁻³)；$R_a=287\ \mathrm{J\,kg^{-1}K^{-1}}$ |
| **静力学（等温解）** | $P=P_0e^{-gz/(R_aT)}$ | $P_0$ 地面压强 (Pa) |
| **静力学（变温）** | $\dfrac{dP}{dz}=-\dfrac{Pg}{R_a(T_s-\alpha z)}$；解 $P=P_0\left(\dfrac{T_s-\alpha z}{T_s}\right)^{g/(\alpha R_a)}$ | $T_s$ 地表温度 (K)；$\alpha$ 温度递减率 (K·m⁻¹，实际约 10 °C/km = 0.01 K/m) |

---

### 3.13 ⭐ 第 14 章：考试中会提供的公式 (Provided Equations in the Exam)

> **手册原文（关键）**："This Chapter contains equations that will be presented to you in the exam. **If an equation does not appear in this Chapter, then you are expected to learn it for the exam.**"
> **即：本章有的 = 不用背；本章没有的 = 必须背。**
> 这份清单已由 2023–24 真题卷第 2 页交叉验证——真题卷开头确实印着 chain rule / product rule / quotient rule / common differentials / common integrals。

#### 【会提供 ✅】

**1. 牛顿法 (Newton's method)** —— 求根

$$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$$

其中 $f'(x)$ 是 $f(x)$ 的导数。

**2. 链式法则 (Chain rule)** —— 复合函数 $f(g(x))$ 的导数：先对 $g$ 求导，再乘以 $g$ 对 $x$ 的导数

$$\frac{df}{dx} = \frac{df}{dg}\cdot\frac{dg}{dx}$$

**3. 乘积法则 (Product rule)** —— $f(x) = u(x)v(x)$

$$\frac{df}{dx} = u\frac{dv}{dx} + v\frac{du}{dx}$$

**4. 商法则 (Quotient rule)** —— $f(x) = \dfrac{u(x)}{v(x)}$

$$\frac{df}{dx} = \frac{v\dfrac{du}{dx} - u\dfrac{dv}{dx}}{v^2}$$

**5. 常见导数表 (Common differentials)**

| 函数 $y$ | 导数 $\dfrac{dy}{dx}$ |
|---|---|
| $y = x^n$ | $nx^{n-1}$ |
| $y = e^{f(x)}$ | $\dfrac{df}{dx}\,e^{f(x)}$ |
| $y = \ln(x)$ | $\dfrac{1}{x}$ |
| $y = \sin(x)$ | $\cos(x)$ |
| $y = \cos(x)$ | $-\sin(x)$ |

**6. 常见积分表 (Common integrals)** —— 即 §3.1 的那张表（手册中此处为图片，内容与 §3.1 一致）

| $\dfrac{dy}{dx}$ | $y$ |
|---|---|
| $0$ | $d$ |
| constant $c$ | $cx+d$ |
| $x$ | $\dfrac{x^2}{2}+d$ |
| $x^n$ | $\dfrac{x^{n+1}}{n+1}+d$ |
| $e^x$ | $e^x+d$ |
| $ke^{kx}$ | $e^{kx}+d$ |
| $\dfrac{1}{x}$ | $\ln(x)+d$ |
| $\cos(x)$ | $\sin(x)+d$ |
| $\sin(x)$ | $-\cos(x)+d$ |

#### 【不提供 ❌ —— 必须背】

反过来推：凡不在第 14 章的，都要背。结合老师课堂原话，重点如下：

| 必背内容 | 公式 | 依据 |
|---|---|---|
| **牛顿第二定律的三种 ODE 形式** | $m\dfrac{dv}{dt}$、$m\dfrac{d^2x}{dt^2}$、$mv\dfrac{dv}{dx}$ | 老师："I will expect you to remember these three formulations for the exam" |
| **二次求根公式** | $\lambda=\dfrac{-b\pm\sqrt{b^2-4ac}}{2a}$ | 老师："I won't give you this, I'll expect you to know this" |
| **二阶 ODE 的两个通解** | $Ae^{\lambda_1x}+Be^{\lambda_2x}$；$(A+Bx)e^{\lambda_1x}$ | 老师："I won't give you these general solutions" |
| **分离变量法的操作流程** | — | 属"方法"，不是"公式" |
| **换元积分的 8 步流程** | — | 属"方法"；老师说不必写全 8 步 |
| **放射性衰变律与半衰期** | $\frac{dN}{dt}=-\lambda N$，$N=N_0e^{-\lambda t}$，$t_{1/2}=\ln2/\lambda$ | 不在第 14 章 |
| **重力分解 / 斜面受力** | $mg\sin\theta$（沿斜面）、$mg\cos\theta$（法向） | 不在第 14 章 |
| **功与动能** | $W=Fs$，$\int F dx = \frac12mv^2-\frac12mu^2$ | 不在第 14 章 |
| **数值微分（中心差分等）** | $f'(x)\approx\dfrac{f(x+h)-f(x-h)}{2h}$ | 真题 Q7 用到，第 14 章未列 |
| **百分比误差 / 百分比差** | $100\times\dfrac{\text{新}-\text{旧}}{\text{旧}}$ | 真题 Q7、Q10 用到 |
| **Fourier / Fick / 静力学方程本身** | — | 老师说这类方程"the simplest form I would give it to you"，题干通常会给，但**推导与积分方法要会** |
| **对数/指数运算律** | $\ln a - \ln b = \ln\frac ab$；$e^{\ln x}=x$；$e^{a+b}=e^ae^b$ | 每道题最后一步都要用 |
| **三角函数值** | $\sin30°=0.5$ 等 | 计算器可算，但要注意角度/弧度模式 |

---

## 四、课堂补充

> 本节是本周**信息密度最高**的部分：全部来自 09-May 复习课录音转写，包含老师亲口给出的考试提示、重点圈定、易错点、评分方式。

### 4.1 ⭐ 考试信息（老师明说的）

| 项目 | 内容 |
|---|---|
| **考试日期** | 老师说 "**it's the 20th** … I think it's the afternoon anyway"（下午场，具体时间以官方为准） |
| **卷面结构** | 与去年**基本相同**："the exam in theory is pretty similar to the one last year. **So the first few questions are probably going to be very very similar to last year's questions.**" |
| **第 1 题** | 微分部分的第一题**大概率是 True / False**（老师上周复习课已说过） |
| **积分第一题** | "your first integration question is probably just going to be a **select the correct** [integral]" |
| **总分** | 100 分（2023–24 卷：10 题 × 10 分） |
| **积分占比** | 去年卷上**积分共 5 题**（Q2、Q4、Q8、Q9、Q10）= **50 分** |
| **答题范围** | Answer **ALL** questions（全做，无选做） |
| **计算器** | **允许使用**，但**不能存文本、不能做代数运算、不能有绘图功能** |
| **书写要求** | 字迹必须**清晰可辨 (LEGIBLE)**，"Illegible documents cannot be marked" |
| **答题册** | Answer in the booklets provided；**清楚标注每个答案对应哪一题** |
| **图示** | "You may wish to use labelled sketches to illustrate your answers where appropriate"——**画带标注的示意图可以得分** |

### 4.2 ⭐⭐⭐ 最重要的一条：**必须写过程 (Show your working)**

老师在课上反复强调，篇幅最长、语气最重：

> "This is a ten mark question, okay. **If you just select the wrong answer you get zero.** But if you put some working down **I may be able to give you 5, 6, 7 marks. Even if your answer is wrong.** Because not every mark for that question is down to selecting the right answer."
>
> "So if I say please show your working, **please show your working**… This is where the value of putting your working in is. Because even if you don't feel like you're strong at maths, then putting some working down gives me an opportunity to give you marks."
>
> "One tiny error and you don't want one tiny error to give you zero marks out of ten."
>
> "I will say it till I'm blue in the face, **please put your working in**."

**要点提炼**：
1. 选择题也是 **10 分**，不是 1 分；
2. **只写答案而答案错了 = 0 分**；
3. **写了过程即使答案错，也可能拿 5–7 分**；
4. 卷面上写着 "Please show all of your working to get to an answer. This is used to mark **correct methodologies**"——**方法论本身就是评分点**。

### 4.3 ⭐ 各周的考试提示逐条汇总

**Week 6（积分基础）**
- 常见积分表"most of which will be on the paper anyway"（大部分会给），但**老师自己也常记不清 sin/cos 的负号位置**，建议做题时**反过来微分验算**。
- 不定积分**永远记得 $+C$**。
- 定积分：**上限值 − 下限值**，不需要常数。

**Week 7（牛顿定律）**
- **三种 ODE 形式必须背**，尤其是 $v\dfrac{dv}{dx}$——"It looks slightly different to the other two"。
- 读题判断"哪两个量要联系起来"：
  - velocity ↔ time → $\dfrac{dv}{dt}$
  - distance ↔ time → $\dfrac{d^2x}{dt^2}$
  - velocity ↔ distance → $v\dfrac{dv}{dx}$
- **摩擦力/空气阻力方向**：永远与**运动方向 (direction of travel)** 相反；沿运动方向对力求代数和。

**Week 8（换元积分）**
- 选 $u$ 的法则：**取函数内部那一坨**。
- **定积分必须换限**；不定积分必须把 $u$ 换回 $x$ 并加常数。
- 常数因子（如 $\frac13$）可以提出积分号外，最后再乘——**推荐这样做，不容易出错**。
- **考试不要求写全 8 步**。

**Week 9（二阶 ODE）**
- 三步：辅助方程求根 → 选通解 → 用初始条件解联立方程定 $A,B$。
- **求根公式和两个通解都不提供**。
- $\lambda_1$ 与 $\lambda_2$ **谁在前无所谓，两项都是加号**。
- 复根情形**不考**。
- **Fick / Fourier 稳态题**：老师会给最简形式，你只要**积两次**得线性解，然后用**两端的边界条件**求两个常数。

### 4.4 ⭐ 计算器与角度单位

> 老师原话："there was a question last week about calculators and angles. **Assume that, if I give you anything, assume it's in radians unless it's stated in degrees.** So for example in this question it's in degrees, so make sure you set your calculators to degrees, otherwise set it to radians. **So be careful when you're doing these type of questions.**"

**规则**：
- 题目**明写 degrees** → 计算器切到 **DEG**；
- **没说** → 默认 **radians**，计算器切到 **RAD**。

### 4.5 "Show that" 类题目的策略

> 老师原话："these are the nicer questions when you get given something to show, because you can obviously work — you can realize very quickly if you're doing something wrong. So **make sure you keep an eye on what the 'show that' question is and the answer is at the end.**"

**策略**：题目给了终点表达式，就**一路盯着终点做**，中途形式对不上立刻发现错误。

### 4.6 真题精讲（2023–24 Past Paper 的 5 道积分题）

> 老师注明：这些题**不是他出的**（"I didn't write these questions"，Q8 是 Dave Topping 出的），但他给了自认为最清晰的解法。他也说 **"you don't have to have done it exactly the same way as I do, this is the one that I think is simplest, but it's completely up to you"**。

---

#### 【Q2】选出正确的积分（10 分）

**题目**：从下列选项中选出 $f(x) = 4x^3 - 2x + 5$ 的积分 $\int f(x)dx$，**请写出过程**。

- (a) $x^4 - x^2 + 5x + C$
- (b) $x^4 - 2x^2 + 5x + C$
- (c) $x^4 - x^2 + 5 + C$
- (d) $3x^4 - x^2 + 5x$

**完整解法（不定积分，逐项处理）**：

$$\int (4x^3 - 2x + 5)\,dx$$

- $\displaystyle\int 4x^3dx = 4\cdot\frac{x^{3+1}}{4} = \frac{4x^4}{4} = x^4$ （4 约掉）
- $\displaystyle\int -2x\,dx = -2\cdot\frac{x^2}{2} = -x^2$ （2 约掉）
- $\displaystyle\int 5\,dx = 5x$
- **加常数** $+C$

$$\boxed{\int(4x^3-2x+5)dx = x^4 - x^2 + 5x + C}$$

**答案：(a)**

**排除法看错在哪**：
- (b) $-2x^2$：忘了除以新幂次 2；
- (c) $+5$：忘了常数积分成 $5x$，且漏了 $x$；
- (d) $3x^4$ 且**没有 $+C$**：幂次处理错，且漏常数。

> 老师："that would probably mean I would give you a few marks for doing the integration even if you pick the wrong answer at the end."

---

#### 【Q4】定积分，答案给到 3 位小数（10 分）

**题目**（据转写还原）：$\displaystyle\int_{-3}^{4}\left(f^2 - e^{3f}\right)df$

**完整解法**：

**第 1 步：分项积分**

$$\int_{-3}^{4} f^2\,df = \left[\frac{f^3}{3}\right]_{-3}^{4}, \qquad \int_{-3}^{4} e^{3f}\,df = \left[\frac{1}{3}e^{3f}\right]_{-3}^{4}$$

（用 $\int e^{kx}dx = \frac1k e^{kx}$，这里 $k=3$）

**第 2 步：合并**

$$\left[\frac{f^3}{3} - \frac{1}{3}e^{3f}\right]_{-3}^{4}$$

**第 3 步：代入上限 − 下限（⚠️ 负数一定加括号）**

$$= \left(\frac{4^3}{3} - \frac{1}{3}e^{12}\right) - \left(\frac{(-3)^3}{3} - \frac{1}{3}e^{-9}\right)$$

$$= \left(\frac{64}{3} - \frac{e^{12}}{3}\right) - \left(\frac{-27}{3} - \frac{e^{-9}}{3}\right)$$

$$= \frac{64}{3} + 9 - \frac{e^{12}}{3} + \frac{e^{-9}}{3}$$

**第 4 步：数值计算**
- $\frac{64}{3} = 21.3333$，$+9$ → $30.3333$
- $e^{12} = 162754.7914$，$\frac{e^{12}}{3} = 54251.5971$
- $e^{-9} = 1.2341\times10^{-4}$，$\frac{e^{-9}}{3} = 4.11\times10^{-5}$（可忽略但保留）

$$= 30.3333 - 54251.5971 + 0.0000411 = \boxed{-54221.264}$$

> 老师的**易错提醒**："make sure, like I do, just to be careful that you **put brackets around minuses**, because when minuses cancel out it may get a bit tricky and you may get a bit lost."（$(-3)^3 = -27$，前面还有个减号，两个负号连用最容易错。）

---

#### 【Q8】斜面上的物体 —— 牛顿第二定律（10 分）

**题设**：质量 $m$ kg 的物体静止在**倾角 30°** 的斜面上。

##### (a) 求 10 秒后的速度（4 分）

初速度 $= 0\ \mathrm{m/s}$，$g = 9.8\ \mathrm{m\,s^{-2}}$，无摩擦。

**第 1 步：判断用哪个牛顿第二定律形式**
题目联系 **velocity 和 time** → 用 $F = m\dfrac{dv}{dt}$。

**第 2 步：分析沿运动方向的力**
重力 $mg$ 竖直向下，但运动方向沿斜面向下。用三角函数分解：

$$F = mg\sin(30°)$$

（法向分量 $mg\cos(30°)$ 被斜面的支持力抵消，不产生运动。）

**第 3 步：写出完整 ODE 并约去质量**

$$m\frac{dv}{dt} = mg\sin(30°) \;\Longrightarrow\; \frac{dv}{dt} = g\sin(30°)$$

> 注意：**质量约掉了** —— 与题目没给具体 $m$ 值一致。

**第 4 步：分离变量并加积分限**
- $t = 0$ 时 $v = 0$（下限）
- $t = 10$ 时 $v = v$（上限）

$$\int_0^v dv = \int_0^{10} g\sin(30°)\,dt$$

**第 5 步：积分求值**

$$\Big[v\Big]_0^v = g\sin(30°)\Big[t\Big]_0^{10}$$

$$v = 10\,g\sin(30°) = 10 \times 9.8 \times 0.5 = \boxed{49\ \mathrm{m\,s^{-1}}}$$

> ⚠️ 转写里出现 "which is 29 meters per second"，是**语音转写错误**，正确答案是 **49 m/s**（后文老师自己反复说 49 m/s）。

##### (b) 突加反向力后何时停下（2 + 4 分）

**题设**：$t=10$ 时突然施加一个**与运动方向相反**的力，大小正比于质量：$F = \alpha m$，$\alpha = 8.5$。

**(b-i) 画受力示意图（2 分）**

> 老师："this is the kind of schematic that I'm looking for… I want you to show me that the object is resting on an incline. You have the force acting towards the centre, which would just be $mg$. We want to know that the angle is [30] degrees… and then you have the forces in the $\sin\theta$ [direction] — in the opposite direction of travel is $\alpha m$, and then in the normal direction is $mg\cos\theta$."

图上必须标出：

```
                    ╱│
                  ╱  │
                ╱ ▓▓ │           ▓▓ = 物体
              ╱  ↗ ↘ │
            ╱  αm   mg sin30°  ← 沿斜面：下滑分量 mg sin30°，
          ╱                       反向阻力 αm（指向斜上方）
        ╱  ↓ mg cos30°         ← 垂直斜面（法向）分量
      ╱_θ=30°_______________
              ↓ mg             ← 总重力，竖直向下
```

必须标注的四项：
1. 物体位于**斜面**上；
2. **总重力 $mg$**，竖直指向地心；
3. **倾角 $\theta = 30°$**；
4. 沿斜面向下的 $mg\sin\theta$、法向的 $mg\cos\theta$、以及**与运动方向相反的 $\alpha m$**。

> ⭐ **老师的送分提示**："**You don't necessarily need to have done the maths to get to those two marks.** You just write a schematic and you've got two marks."（不用做任何计算，画对图就是 2 分。）

**(b-ii) 求停止所需时间（4 分，2 位小数）**

**第 1 步：沿运动方向求合力**

$$F = mg\sin(30°) - \alpha m$$

**第 2 步：写新 ODE 并约去质量**

$$m\frac{dv}{dt} = mg\sin(30°) - \alpha m \;\Longrightarrow\; \frac{dv}{dt} = g\sin(30°) - \alpha$$

**第 3 步：⭐ 关键——正确设定积分限（去年最多人错的地方）**

> 老师："**The trick with this question is what limits do you use.** Where people got slightly wrong was using the wrong limits last year when I was marking this."

**把时间归零重新计时**：
- **下限**：$t = 0$ 时 $v = 49\ \mathrm{m/s}$（阻力刚施加的瞬间）
- **上限**：$t = t$ 时 $v = 0$（完全停止）

> 老师："even though this object has travelled for 10 seconds, we're going to **assume that we're going to start time again at the point of this**… assume that it's starting again but at 49 metres per second."

**第 4 步：积分**

$$\int_{49}^{0} dv = \int_0^{t}\big(g\sin(30°) - \alpha\big)dt$$

$$\Big[v\Big]_{49}^{0} = \big(9.8\times0.5 - 8.5\big)\Big[t\Big]_0^{t}$$

$$0 - 49 = (4.9 - 8.5)\,t = -3.6\,t$$

$$t = \frac{-49}{-3.6} = \boxed{13.61\ \mathrm{s}}$$

**第 5 步：解释含义**
物体在**阻力施加后 13.61 秒**停下。

> ⚠️ **常见错误（老师亲口说的）**："if you had assumed that $t=10$, like some people did… you would integrate between 10 and $t$ here and you would end up with **23.61**"——即从整个运动的起点算，总时间是 $10 + 13.61 = 23.61$ s。这个数**本身不算错**，但你**必须写清楚"从阻力施加算起是 13.61 秒"**。题目问的是 "how long it takes for the vehicle to stop"，即施加阻力后到停止的时长 → **13.61 s**。
>
> 老师："In this question you just shift time by 10."

**课堂问答（积分限方向）**：学生问为什么是从 49 积到 0 而不是从 0 积到 49？
老师答：**初始条件是 49（下限），终止条件是 0（上限）**，所以是 $\int_{49}^{0}$。如果你反过来写成 $\int_0^{49}$，会得到 $-13.61$，"you would just have to take away the minus"——但**正确写法是 49 → 0**。

---

#### 【Q9】人口变化 ODE（10 分）

##### (a) 基础版：出生率、死亡率都与人口成正比（4 分）

**题设**：

$$\frac{dP}{dt} = (\alpha - \beta)P$$

- $P$：人口
- $\alpha$：出生贡献系数（births）
- $\beta$：自然死亡贡献系数（natural deaths）
- $P_0$：$t=0$ 时的人口

**要求"show that"**：$P = P_0 e^{(\alpha-\beta)t}$

**完整解法（分离变量 + 不定积分）**：

**第 1 步：分离变量**

$$\frac{dP}{P} = (\alpha - \beta)\,dt$$

**第 2 步：两边积分**

$$\int\frac{1}{P}dP = (\alpha-\beta)\int dt$$

$$\ln P = (\alpha - \beta)t + C$$

**第 3 步：用初始条件定 $C$**
$t = 0$ 时 $P = P_0$，此时 $(\alpha-\beta)t = 0$：

$$\ln P_0 = C$$

**第 4 步：代回**

$$\ln P = (\alpha-\beta)t + \ln P_0$$

**第 5 步：两边取指数，用对数/指数律**

$$P = e^{(\alpha-\beta)t + \ln P_0} = e^{(\alpha-\beta)t}\cdot e^{\ln P_0}$$

$$\boxed{P = P_0\,e^{(\alpha-\beta)t}}$$

> **课堂问答**：学生问能不能直接用带限积分（下限 $P_0$、上限 $P$）？
> 老师："**You could do, yeah, yeah, yeah.** I like to do it a little bit like this, but there's no reason why you couldn't. **You just need to make sure that both integrals then have limits.** You would do it between $P_0$ and $P$ and then 0 and $T$, and then you would get that answer, **that's completely valid, that's fine.**"

**带限积分的等价写法**：

$$\int_{P_0}^{P}\frac{dP}{P} = \int_0^t(\alpha-\beta)dt \;\Longrightarrow\; \ln\frac{P}{P_0} = (\alpha-\beta)t \;\Longrightarrow\; P = P_0e^{(\alpha-\beta)t}$$

##### (b) 进阶版：出生率恒定 → 必须换元（6 分）

**题设**：出生率现在是常数 $\psi$：

$$\frac{dP}{dt} = \psi - \beta P$$

**要求**：用换元 $u = \psi - \beta P$ 积分。

**完整解法**：

**第 1 步：分离变量**

$$\frac{dP}{\psi - \beta P} = dt \;\Longrightarrow\; \int\frac{1}{\psi-\beta P}dP = \int dt$$

**第 2 步：令 $u = \psi - \beta P$**

**第 3 步：反解 $P$**

$$P = \frac{\psi - u}{\beta}$$

**第 4 步：对 $u$ 求导**

$$\frac{dP}{du} = -\frac{1}{\beta}$$

**第 5 步：得 $dP$**

$$dP = -\frac{1}{\beta}du$$

**第 6 步：代入原积分**

$$\int\frac{1}{u}\left(-\frac{1}{\beta}du\right) = \int dt \;\Longrightarrow\; -\frac{1}{\beta}\int\frac{du}{u} = \int dt$$

等价写成（老师板书的形式）：

$$\frac{1}{\beta}\int\frac{du}{u} = -\int dt$$

**第 7 步：积分**

$$\frac{1}{\beta}\ln u = -t + C$$

**第 8 步：用初始条件定 $C$**
$t = 0$ 时 $P = P_0$，因此 $u = u_0 = \psi - \beta P_0$：

$$\frac{1}{\beta}\ln u_0 = 0 + C \;\Longrightarrow\; C = \frac{1}{\beta}\ln u_0$$

**第 9 步：代回并整理**

$$\frac{1}{\beta}\ln u = -t + \frac{1}{\beta}\ln u_0$$

两边乘 $\beta$：

$$\ln u = -\beta t + \ln u_0 \;\Longrightarrow\; \ln\frac{u}{u_0} = -\beta t$$

**第 10 步：取指数**

$$\frac{u}{u_0} = e^{-\beta t}$$

**第 11 步：换回 $P$**

$$\frac{\psi - \beta P}{\psi - \beta P_0} = e^{-\beta t}$$

**第 12 步：解出 $P$**

$$\psi - \beta P = (\psi - \beta P_0)e^{-\beta t}$$

$$\beta P = \psi - (\psi - \beta P_0)e^{-\beta t}$$

$$\boxed{P = \frac{\psi}{\beta} - \left(\frac{\psi}{\beta} - P_0\right)e^{-\beta t}}$$

**物理意义**：$t\to\infty$ 时 $P \to \psi/\beta$，即**恒定出生率与正比死亡率之间的平衡人口**。

> 老师："**you don't have to have done it exactly the same way as I do, this is the one that I think is simplest, but it's completely up to you how you do it.** And again, you could have just done your step for example, which is just to add in limits into these integrals."

---

#### 【Q10】静力学方程（10 分）—— **老师说是整张卷子最难的一题**

> 老师："In the next session, if you come over to the practical, I'll cover the last question, **which was by far the hardest question on the exam**."（这题留到 Practical 讲。）

**题设**：静力学方程给出压强 $P$ 随高度 $z$ 的变化：

$$\frac{dP}{dz} = -\frac{Pg}{R_a(T_s - \alpha z)}$$

其中 $R_a = 287\ \mathrm{J\,kg^{-1}\,K^{-1}}$，$T_s = 290$ K（地表温度），$g = 9.8\ \mathrm{m\,s^{-2}}$，$P_0 = 100000$ Pa（$z=0$）。$\alpha$ 可能是 0.01 或 0.02，问 $z = 1400$ m 处压强差别多大。

##### (a) 用换元法积分，求 $\alpha = 0.01$ 时 1400 m 处的压强（6 分）

**第 1 步：分离变量**

$$\frac{dP}{P} = -\frac{g}{R_a(T_s - \alpha z)}\,dz$$

加上积分限（$z=0$ 时 $P = 100000$；$z=1400$ 时 $P=P$）：

$$\int_{100000}^{P}\frac{dP}{P} = -\frac{g}{R_a}\int_0^{1400}\frac{dz}{T_s - \alpha z}$$

**第 2 步：令 $u = T_s - \alpha z$**

**第 3 步：反解 $z$**

$$z = \frac{T_s - u}{\alpha}$$

**第 4 步：对 $u$ 求导**

$$\frac{dz}{du} = -\frac{1}{\alpha}$$

**第 5 步：得 $dz$**

$$dz = -\frac{1}{\alpha}du$$

**第 6 步：⭐ 换积分限**
- $z = 0 \Rightarrow u = T_s = 290$
- $z = 1400 \Rightarrow u = T_s - 1400\alpha$

**第 7 步：代入**

$$\left[\ln P\right]_{100000}^{P} = -\frac{g}{R_a}\int_{T_s}^{T_s-1400\alpha}\frac{1}{u}\left(-\frac{du}{\alpha}\right) = \frac{g}{\alpha R_a}\int_{T_s}^{T_s-1400\alpha}\frac{du}{u}$$

**第 8 步：积分求值**

$$\ln\frac{P}{P_0} = \frac{g}{\alpha R_a}\left[\ln u\right]_{T_s}^{T_s-1400\alpha} = \frac{g}{\alpha R_a}\ln\left(\frac{T_s - 1400\alpha}{T_s}\right)$$

**第 9 步：整理出最终表达式**

$$\boxed{P = P_0\left(\frac{T_s - \alpha z}{T_s}\right)^{\frac{g}{\alpha R_a}}}$$

**第 10 步：代数值（$\alpha = 0.01$，$T_s = 290$，$R_a = 287$，$g = 9.8$，$z = 1400$，$P_0 = 100000$）**

- 指数：$\dfrac{g}{\alpha R_a} = \dfrac{9.8}{0.01\times287} = \dfrac{9.8}{2.87} = 3.41463$
- 底数：$\dfrac{290 - 0.01\times1400}{290} = \dfrac{290-14}{290} = \dfrac{276}{290} = 0.951724$
- $0.951724^{3.41463} = e^{3.41463\times\ln0.951724} = e^{3.41463\times(-0.049485)} = e^{-0.168973} = 0.84453$

$$P(1400) = 100000 \times 0.84453 = \boxed{84454\ \mathrm{Pa}}\quad(\text{5 位有效数字})$$

##### (b) $\alpha$ 从 0.01 改为 0.02 时的百分比差（4 分，1 位小数）

**$\alpha = 0.02$**：
- 指数：$\dfrac{9.8}{0.02\times287} = \dfrac{9.8}{5.74} = 1.70732$
- 底数：$\dfrac{290 - 0.02\times1400}{290} = \dfrac{290-28}{290} = \dfrac{262}{290} = 0.903448$
- $0.903448^{1.70732} = e^{1.70732\times(-0.101557)} = e^{-0.173390} = 0.84083$

$$P(1400)\big|_{\alpha=0.02} = \boxed{84083\ \mathrm{Pa}}$$

**百分比差**：

$$100\times\frac{84083 - 84454}{84454} = 100\times\frac{-371}{84454} = -0.439\% \approx \boxed{-0.4\%}$$

**物理解释**：递减率 $\alpha$ 加倍（每 km 降温 10 °C → 20 °C），大气整体更冷、密度更大，1400 m 处压强略低，但影响很小（约 −0.4%）。

> **精度要求**：题目明确要求 $P$ 用 **5 位有效数字**、百分比差用 **1 位小数**——**照做，不要中途四舍五入**。

---

### 4.7 老师的收尾话与其他

- 老师会把**解答幻灯片上传**（"I'll put these solutions up"），并会**修正幻灯片里两个表格的排版错误**（"I'll fix the two tables that I found"）。
- 老师承诺**考前继续回复邮件**："I'm answering emails if you have any questions."
- 老师在课上多次停下来问"有没有问题"，本周只有 4 个学生提问（都记录在 §4.6 相应位置），说明**主动提问的机会很多**。
- 老师在讲 Week 6 结束时开玩笑："Fantastic, I shall expect **10 out of 10** on all of these questions."——暗示**基础积分题是必须拿满的送分题**。

---

## 五、Practical 要点

**本周 Practical 材料 = `2324_Exam(1).pdf` —— 2023–24 年完整真题卷（10 题，100 分）。**

Practical 环节老师安排：**继续讲复习课里没讲完的 Q10（静力学方程）**。

> 老师："I'm probably going to have to do this next question and the last question in the practical session, like I did last week… If you come over to the lab, the practical, I'll cover the last question, which was by far the hardest question on the exam. I'll go through [the hydrostatic] equation in that one."

### 5.1 真题卷封面信息（考试规则原文要点）

- **THE UNIVERSITY OF MANCHESTER — EART11200 Toolkit – Maths and Physics**
- June 2024
- **Answer ALL questions in the booklets provided.**
- **Clearly label which question each of your answers corresponds to. All writing must be LEGIBLE. Illegible documents cannot be marked.**
- **There are 100 marks available on this paper. The number of marks for each question is shown and may be used as a guide to how much time you should spend on each.**（分值 = 时间分配指南）
- **You may wish to use labelled sketches to illustrate your answers where appropriate.**
- **Please show all of your working to get to an answer. This is used to mark correct methodologies.**
- **The use of calculators is permitted, as long as they cannot store text, perform algebra and have no graphing capability.**

### 5.2 试卷第 2 页：提供的公式（考前必看）

真题卷**第 2 页**就是"送给你的公式页"，内容与主手册第 14 章完全对应：

1. **The chain rule**
2. **The product rule**
3. **The quotient rule**
4. **Common differentials**（表）
5. **Common integrals**（表）

> ⭐ 这一页**证实了第 14 章的清单是真实的考试提供公式**。凡不在这一页上的公式（牛顿第二定律三种 ODE 形式、二次求根公式、二阶 ODE 通解、衰变律等）**都要自己背**。
> 另外注意：**Newton's method 的公式虽然在第 14 章，但真题里是写在 Q3 题干中的**（"Please note that we can write Newton's formula, generally, as: …"），说明有些"提供的公式"是随题给出的。

### 5.3 2023–24 真题全卷题目结构（10 题 × 10 分）

| 题号 | 内容 | 所属板块 | 分值细分 |
|---|---|---|---|
| **Q1** | 微分 **TRUE / FALSE** 五小题：(a) $f=\cos(2x)$ 的导数；(b) $f=e^{kx}$ 型；(c) $f=\ln(2x)$；(d) $f=5x^n$；(e) $f=\sin(x)$ 的**二阶**导数 | 微分 | 10 |
| **Q2** | **选出正确的积分** $\int(4x^3-2x+5)dx$，须写过程 | **积分** | 10 |
| **Q3** | **牛顿法求根**，3 位小数，起始猜测 $x_0 = -0.6$ | 数值方法 | 10 |
| **Q4** | **定积分**，答案 3 位小数 | **积分** | 10 |
| **Q5** | 气体泄漏：丁烷浓度 $G$（μg·m⁻³）随时间（分钟）变化，求**最大浓度出现的时刻** | 微分（求极值） | 10 |
| **Q6** | 对 $x$ **求导并化简**：(a) $f=\cos(x)e^{kx}$（乘积法则）；(b) $g$ 含 $x\sqrt{x}$ 与常数；(c) $y = e^{kx^2}/x$（商法则 + 链式法则） | 微分 | 10 |
| **Q7** | 燃油箱缓慢漏油，$V_0=10\ \mathrm{m^3}$，$0<t<24$ h。求 $t=2$ h 时的**泄漏速率**：**解析法** vs **中心差分数值法**（$\Delta t = 30$ min），并估计**百分比误差** | 微分 + 数值 | 10 |
| **Q8** | **斜面上的物体**（30°）：(a) 10 s 后速度 [4 分]；(b) 突加反向力 $F=\alpha m$（$\alpha=8.5$）：画受力图 [2 分] + 求停止时间到 2 位小数 [4 分] | **积分/牛顿定律** | 10 |
| **Q9** | **人口 ODE**：(a) 积分得 $P=P_0e^{(\alpha-\beta)t}$ [4 分]；(b) 出生率恒定 $\psi$，用 $u=\psi-\beta P$ 换元 [6 分] | **积分** | 10 |
| **Q10** | **静力学方程**：(a) 用换元积分求 $\alpha=0.01$ 时 1400 m 处压强 [6 分]；(b) $\alpha$ 改为 0.02 的百分比差 [4 分] | **积分** | 10 |

**板块占比**：
- **微分侧**：Q1、Q3、Q5、Q6、Q7 = **50 分**
- **积分侧**：Q2、Q4、Q8、Q9、Q10 = **50 分**（与老师"there were 5 questions on integration"一致）

### 5.4 Practical 复习清单（根据真题卷倒推）

做完这张卷子你应该能做到：

- [ ] 判断五个常见导数的对错（Q1）
- [ ] 多项式的不定积分并选对答案（Q2）
- [ ] 牛顿法迭代到 3 位小数（Q3）
- [ ] 含 $x^n$ 与 $e^{kx}$ 的定积分并保留 3 位小数（Q4）
- [ ] 求函数极值（令一阶导数 = 0）（Q5）
- [ ] 熟练使用乘积法则、商法则、链式法则并化简（Q6）
- [ ] 中心差分数值微分 + 与解析解比较 + 百分比误差（Q7）
- [ ] 斜面受力分解、写 ODE、画受力图、正确设定积分限（Q8）
- [ ] 分离变量 + 对数/指数律整理成 "show that" 的目标形式（Q9a）
- [ ] 换元积分处理 $\frac{1}{a-bx}$ 型（Q9b、Q10）
- [ ] 换元时正确更换积分限、正确取有效数字（Q10）

---

## 六、易错点 / 重点难点

> 本节以**老师亲口指出的**为主，标 ⭐ 的是课堂上明确警示过的。

### 6.1 ⭐⭐⭐ 只写答案不写过程 = 丢掉全部分数

**最严重的失分方式。** 详见 §4.2。
- 10 分的选择题，选错且无过程 → **0 分**；
- 选错但有过程 → **可能 5–7 分**。
- **策略：任何题目都把过程完整写出来，哪怕最后算错。**

### 6.2 ⭐ 不定积分忘记加常数 $+C$

老师专门用一整段强调。判据很简单：**没有积分限 → 必须有 $+C$**。
- 真题 Q2 的错误选项 (d) 就是**没有 $+C$**。

### 6.3 ⭐ Q8(b) 的积分限设定（去年最多人错）

> 老师原话："Where people got slightly wrong was **using the wrong limits** last year when I was marking this."

- 阻力施加后**把时间归零重新计时**：$t: 0 \to t$，$v: 49 \to 0$；
- 得 **13.61 s**（阻力施加后的时长）；
- 若从整个运动起点算是 **23.61 s**，那你**必须显式说明"从阻力施加算起是 13.61 s"**；
- 积分限方向要对：**从初始条件 (49) 积到终止条件 (0)**，写反会得到负号。

### 6.4 ⭐ 定积分代限时的负号与括号

> 老师："make sure… that you **put brackets around minuses** because when minuses cancel out it may get a bit tricky and you may get a bit lost."

Q4 里 $-\left(\frac{(-3)^3}{3}\right) = -(-9) = +9$，两处负号相消，不加括号极易漏掉。

### 6.5 ⭐ sin / cos 积分的负号位置

> 老师："particularly the one I always forget is where the sine and the minus goes and the sine and the cos. **So double check things when you're doing that.**"

| 别背混了 | |
|---|---|
| $\int \sin x\,dx = \textbf{−}\cos x + d$ | **积分：负号在 sin 这一行** |
| $\int \cos x\,dx = \sin x + d$ | |
| $\frac{d}{dx}\sin x = \cos x$ | |
| $\frac{d}{dx}\cos x = \textbf{−}\sin x$ | **微分：负号在 cos 这一行** |

**自检法**：积完之后**反过来微分一次**，看能不能回到原函数。

### 6.6 ⭐ 计算器的角度 / 弧度模式

**题目写 degrees → DEG 模式；没写 → RAD 模式。**（详见 §4.4）
Q8 是 30 **degrees**，若用 RAD 算 $\sin(30)$ 会得 $-0.988$，答案全错。

### 6.7 ⭐ 换元积分：定积分**必须**换限

第 6 步不能省。**只有不定积分才跳过换限，但不定积分要把 $u$ 换回 $x$ 并加 $+C$。**
两种收尾方式**不要混用**：
- 定积分：换限 → 用 $u$ 的新限直接求值 → **不换回 $x$**；
- 不定积分：不换限 → 积完 → **换回 $x$** → **加 $+C$**。

### 6.8 ⭐ 换元时必须把 $dx$ 也换掉

> 老师："When we do integration by substitution we need to **get rid of all references of $x$**. So we can't just use a substitution of $3x+2$, we also need to substitute $dx$."

只换被积函数、不换 $dx$ 是初学者最常见的错误。

### 6.9 ⭐ 牛顿定律：选错 ODE 形式

**读题时先问：题目要联系哪两个量？**

| 题目提到 | 用 |
|---|---|
| 速度 + 时间 | $m\dfrac{dv}{dt}$ |
| 位移 + 时间 | $m\dfrac{d^2x}{dt^2}$ |
| 速度 + 位移 | $mv\dfrac{dv}{dx}$ ← **最容易忘，长得最不一样** |

### 6.10 ⭐ 力的方向：永远沿运动方向求和

> 老师："**Always look at the forces in the direction of travel.**"

- 沿斜面下滑：驱动力 $mg\sin\theta$，摩擦力**沿斜面向上**；
- 空气中下落：重力向下，空气阻力**向上**；
- 合力 = 驱动力 − 阻力。

### 6.11 二阶 ODE 的三个坑

1. **求根公式和通解都不提供**——必须背；
2. **选错通解形式**：判别式 $b^2-4ac$ 决定用哪个（$>0$ 用 $Ae^{\lambda_1x}+Be^{\lambda_2x}$，$=0$ 用 $(A+Bx)e^{\lambda_1x}$）；
3. **$A, B$ 需要两个条件**，解联立方程，不能只用一个。
   - 但 $\lambda_1$ / $\lambda_2$ 的顺序**无所谓**，两项都是加号（老师明确回答过）。

### 6.12 IVP vs BVP 用错条件

- **IVP**：两个条件都给在**同一点**（通常 $x=0$）；
- **BVP**（Fick / Fourier 稳态）：条件给在**两个不同的位置**，必须**两个都用**。

> 老师："you can't just use the fact that everything happens on the initial conditions. **You need a condition here and a condition here.**"

### 6.13 "Show that" 题目要盯住终点

给了答案就用它自查。中途形式对不上说明前面错了，及早发现。

### 6.14 有效数字与精度

- Q4：**3 位小数**；
- Q8(b)：**2 位小数**；
- Q10(a)：**5 位有效数字**；(b)：**1 位小数**。
- **中途不要四舍五入**，只在最后一步按要求取位。

### 6.15 别忘了"画图也给分"

Q8(b) 的受力示意图值 **2 分**，不需要任何计算。卷面也明说 "You may wish to use labelled sketches to illustrate your answers"。**不会算也要把图画了。**

### 6.16 手册本身的两处小错（不要被误导）

1. §13.4 写 "$146/92 = 1.587\%$"——**不是百分比**，就是比值 1.587；
2. §13.6 写热传导面积 "$A$, in $m^{-2}$"——**面积单位应是 m²**，是排版/转换错误。
3. 表 13.4 的公制词头**漏了 micro (μ, $10^{-6}$)**。

---

## 七、本周术语表

### 积分核心术语

| 英文 | 中文 | 说明 |
|---|---|---|
| Integration | 积分 | 微分的逆运算；从 rate 得到 absolute value |
| Integrand | 被积函数 | $\int f(x)dx$ 中的 $f(x)$ |
| Limits of integration | 积分限 | $\int$ 的上下标 |
| **Indefinite integration** | **不定积分** | 无积分限，**必须加常数 $+C$/$+d$** |
| **Definite integration** | **定积分** | 有积分限，上限值减下限值，不需常数 |
| Constant of integration | 积分常数 | $C$ 或 $d$ |
| **Separation of variables** | **分离变量法** | 把 $y$ 项与 $x$ 项分到等号两侧再各自积分 |
| **Integration by substitution** | **换元积分法** | 令 $u=$ 内层函数；是**链式法则的逆过程** |
| Area under a curve | 曲线下面积 | 定积分的几何意义 |

### 微分方程术语

| 英文 | 中文 | 说明 |
|---|---|---|
| Differential equation | 微分方程 | 含导数的方程 |
| **ODE (Ordinary Differential Equation)** | **常微分方程** | 只含一个自变量 |
| **PDE (Partial Differential Equation)** | **偏微分方程** | 含多个自变量；**本课不解** |
| First-order ODE | 一阶常微分方程 | 最高含一阶导数 |
| **Second-order ODE** | **二阶常微分方程** | 含二阶导数 |
| **Homogeneous, linear, second-order ODE** | **齐次线性二阶 ODE** | $a y'' + by' + cy = 0$ |
| **Auxiliary equation** | **辅助方程 / 特征方程** | $a\lambda^2+b\lambda+c=0$ |
| Roots | 根 | 辅助方程的解 $\lambda_1,\lambda_2$ |
| General solution | 通解 | 含待定常数 $A, B$ |
| **Initial conditions** | **初始条件** | 在同一点给出 $y$ 与 $y'$ |
| **Boundary conditions** | **边界条件** | 在两个不同点各给一个条件 |
| **Initial Value Problem (IVP)** | **初值问题** | 用初始条件 |
| **Boundary Value Problem (BVP)** | **边值问题** | 用边界条件；Fick/Fourier 稳态属此类 |
| Simultaneous equations | 联立方程组 | 求 $A, B$ 时得到 |
| Steady state | 稳态 | 量不随时间变化（$\partial/\partial t = 0$） |

### 物理定律与常数术语

| 英文 | 中文 | 说明 |
|---|---|---|
| Radioactive decay | 放射性衰变 | $dN/dt=-\lambda N$ |
| Alpha ($\alpha$) decay | α 衰变 | 放出氦核，质量数 −4，原子序数 −2 |
| Beta ($\beta$) decay | β 衰变 | $\beta^-$ 放电子，$\beta^+$ 放正电子 |
| Gamma ($\gamma$) decay | γ 衰变 | 激发态核跃迁，放高能电磁辐射 |
| Daughter nuclei | 子核 | 衰变产物 |
| Decay rate / decay constant | 衰变常数 $\lambda$ | 单位 s⁻¹ |
| **Half-life** | **半衰期** $t_{1/2}$ | $t_{1/2}=\ln2/\lambda$ |
| Antineutrino / neutrino | 反中微子 / 中微子 | β 衰变伴随粒子 |
| Binding energy | 结合能 | $\beta^+$ 衰变的能量条件 |
| Classical mechanics | 经典力学 | 20 世纪前的物理框架 |
| Newtonian physics | 牛顿物理 | *Principia* (1687) |
| Law of Inertia | 惯性定律 | 牛顿第一定律 |
| Law of Force and Momentum | 力与动量定律 | 牛顿第二定律 |
| Law of Action and Reaction | 作用与反作用定律 | 牛顿第三定律 |
| Net force | 净力 | 合力 |
| Angle of inclination | 倾角 | 斜面与水平面夹角 |
| Normal (direction) | 法向 | 垂直于表面的方向 |
| Direction of travel | 运动方向 | 求合力时的参考方向 |
| Frictional force | 摩擦力 | 与运动方向相反 |
| Air resistance | 空气阻力 | 与运动方向相反 |
| Work done | 功 | $W = Fs$，单位 J 或 N·m |
| Kinetic energy | 动能 | $\frac12mv^2$ |
| **Thermal conduction** | **热传导** | 粒子间直接能量传递；真空中不存在 |
| Convection | 对流 | 涉及宏观位移 |
| Radiation | 辐射 | 可在真空中传播 |
| **Thermal conductivity** ($k$) | **热导率** | W·m⁻¹·K⁻¹ |
| **Heat flux** ($q$) | **热通量** | 单位面积单位时间的能量流，W·m⁻² |
| **Fourier's first law** | **傅里叶第一定律** | $\mathbf{q}=-k\nabla T$ |
| **Fourier's second law** | **傅里叶第二定律** | 稳态 $\nabla^2T=0$ |
| Temperature gradient | 温度梯度 | $dT/dx$ |
| Gradient of a gradient | 梯度的梯度 | 二阶导数的直观说法 |
| **Brownian motion** | **布朗运动** | 随机热运动 |
| Diffusion | 扩散 | 物质从高浓度向低浓度输运 |
| **Diffusive flux** ($J$) | **扩散通量** | 单位面积单位时间的物质量 |
| **Diffusion coefficient** ($D$) | **扩散系数** | cm²·s⁻¹；取决于温度、黏度、分子大小 |
| Concentration ($\Theta$) | 浓度 | 单位体积的量 |
| **Fick's first law** | **菲克第一定律** | $\mathbf{J}=-D\nabla\Theta$ |
| **Fick's second law** | **菲克第二定律** | $\partial\Theta/\partial t = D\,\partial^2\Theta/\partial x^2$（PDE） |
| Grad operator ($\nabla$) | 梯度算子 | 第 11 章内容 |
| Ideal gas law | 理想气体定律 | $\rho = P/(R_aT)$ |
| **Hydrostatic equation** | **静力学方程** | $dP/dz = -\rho g$ |
| Lapse rate ($\alpha$) | 温度递减率 | 约 10 °C/km |
| Weight | 重量 | $W = mg$（力，单位 N） |
| Density ($\rho$) | 密度 | kg·m⁻³ |

### 考试相关术语

| 英文 | 中文 | 说明 |
|---|---|---|
| Crib sheet | 速查表 / 小抄页 | 主手册第 12 章 |
| **Provided equations** | **考试提供的公式** | 主手册第 14 章 = 不用背 |
| Maths survival pack | 数学生存包 | 课程提供的公式速查资料 |
| Show your working | 写出解题过程 | **最重要的得分策略** |
| Labelled sketch | 带标注的示意图 | 可直接得分（Q8b 值 2 分） |
| Newton's method | 牛顿法（求根） | $x_{n+1}=x_n-f(x_n)/f'(x_n)$ |
| Central differences | 中心差分 | 数值微分方法（真题 Q7） |
| Percentage error / difference | 百分比误差 / 百分比差 | $100\times\frac{\text{新}-\text{旧}}{\text{旧}}$ |
| Significant digits | 有效数字 | Q10 要求 5 位 |
| Decimal places | 小数位 | Q4 要求 3 位，Q8b 要求 2 位 |

---

## 附：考前 24 小时速查清单

**必背（考试不提供）**
1. $F = m\frac{dv}{dt}$ / $m\frac{d^2x}{dt^2}$ / $mv\frac{dv}{dx}$ ← 三种都要
2. $\lambda = \frac{-b\pm\sqrt{b^2-4ac}}{2a}$
3. $y = Ae^{\lambda_1x}+Be^{\lambda_2x}$（$\lambda_1\neq\lambda_2$）；$y=(A+Bx)e^{\lambda_1x}$（$\lambda_1=\lambda_2$）
4. $\frac{dN}{dt}=-\lambda N \Rightarrow N=N_0e^{-\lambda t}$；$t_{1/2}=\ln2/\lambda$
5. 斜面：沿面 $mg\sin\theta$，法向 $mg\cos\theta$
6. $W=Fs$；$\frac12mv^2-\frac12mu^2$
7. 中心差分 $f'(x)\approx\frac{f(x+h)-f(x-h)}{2h}$
8. $\ln a-\ln b=\ln\frac ab$；$e^{\ln x}=x$；$e^{a+b}=e^ae^b$
9. $\frac{dP}{dz}=-\rho g=-\frac{Pg}{R_aT}$，$R_a=287$

**会给（不用背，但要会用）**
链式法则、乘积法则、商法则、常见导数表、常见积分表、牛顿法公式

**考场三条铁律**
1. **写过程**（选择题也写）
2. **不定积分加 $+C$**
3. **确认计算器 DEG / RAD 模式**

**流程自检**
- 定积分换元 → 换限了吗？
- 不定积分换元 → 换回 $x$ 了吗？加 $C$ 了吗？
- 代限 → 负数加括号了吗？
- 最终答案 → 有效数字/小数位符合要求吗？单位写了吗？
