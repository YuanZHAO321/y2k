# Week 9 — 二阶常微分方程 (Second-Order Ordinary Differential Equations)

> 课程：EART11200 The Natural Scientist's Toolkit — Mathematics and Physics
> 本周对应：**周版第 9 章 = 主手册第 10 章**（主手册第 9 章 Integration by Parts 未拆入周材料，故自本周起周版章号比主手册小 1）。
> 讲次日期：24/03/2025（课表中的 Week 28），标题 *Integrating Second-Order ODEs*。
> 材料：`Lecture/Week 9/Chapter9.md`、`lecture9.md`、`EART11200 - 24-Mar-transcript.md`；`Practical/Week 9/Exercises9(1).md`、`Solutions9.md`、`practical9_soln(1).md`；主手册 `main(1).md` 第 3086–3420 行。
> **题号一律以周版文件为准**（Question 9.1–9.8）。

---

## 一、本周主题

### 1.1 本周在全课中的位置

全课脉络：**Week 1–5 微分 → Week 6–8 积分 → Week 9 二阶 ODE → Week 10 向量与偏微分 → Week 11–12 复习**。

| 周 | 主题 | 与本周的关系 |
|---|---|---|
| Week 5 | Second Order Derivatives & Root Finding | 提供二阶导数 $f''(x)$ 的概念与判别极大/极小的用法 |
| Week 6 | Introduction to Integration | 不定积分 + 积分常数 $c$ |
| Week 7 | Integration using Newton's Laws | 用积分从 $F=ma$ 推 $v(t)$、$x(t)$（本周 Q9.5、Q9.8 的直接前身） |
| Week 8 | Integration by Substitution | 上周内容；讲课开头复习了整整 5 页 |
| **Week 9** | **Integrating Second-Order ODEs** | **把微分与积分合起来"解方程"** |
| Week 10 | Vectors and Partial Differentiation | 把一维推广到三维方向性 |

讲师原话（transcript）："You've actually come across these already in this course. It's just **how we framed them** — we can formalize the approach in terms of integration today."（Week 7 用 $F=ma$ 积两次求 $x(t)$，其实已经在解二阶 ODE 了，只是没有这个名字。）

### 1.2 本周的两条主线（务必分清）

本周表面上是一个主题，实际是**两套完全不同的求解流程**，考试时第一步就是判断走哪一条：

| | **主线 A：齐次线性二阶 ODE** | **主线 B：稳态物理定律 (steady-state)** |
|---|---|---|
| 方程长相 | $a\dfrac{d^2y}{dx^2}+b\dfrac{dy}{dx}+cy=0$ | $\dfrac{d^2T}{dx^2}=0$、$\dfrac{d^2C}{dx^2}=0$、$\dfrac{d^2x}{dt^2}=a$ |
| 方法 | **辅助方程 (auxiliary equation)** 猜指数解，解一元二次 | **直接积分两次** |
| 解的形状 | 指数函数组合 $Ae^{\lambda_1x}+Be^{\lambda_2x}$ | 线性/二次多项式 |
| 定常数用 | 多为**初始条件 (initial conditions)**：同一点的 $y$ 和 $y'$ | 多为**边界条件 (boundary conditions)**：两个不同点的函数值 |
| 对应章节 | 9.2 | 9.3 |
| 对应习题 | Q9.1–Q9.4（Algebraic problems） | Q9.5–Q9.8（Real-world problems） |

两条主线的**共同点**：二阶方程 ⇒ 通解里必然有**两个任意常数** $A,B$ ⇒ 必须有**两条独立信息**才能定出唯一解。这是本周的核心骨架。

### 1.3 Intended Learning Outcomes（讲义 + practical 原文，两处重复列出）

1. 描述二阶常微分方程的概念，并解释它们在数学与物理建模中的角色。
2. 用**辅助方程法 (auxiliary equation method)** 解二阶 ODE 得到**通解 (general solution)**。
3. 应用给定的**初始条件 (initial conditions)** 求得**全解 (full solution)**。
4. 用二阶 ODE 建模真实物理过程（牛顿定律、热传导 heat transfer、质量传输 mass transfer），并用**边界条件 (boundary conditions)** 求解。

---

## 二、核心概念

### 2.1 什么是二阶常微分方程

**常微分方程 (ordinary differential equation, ODE)**：含有未知函数的导数的方程，且只有**一个**自变量（"ordinary" 即区别于偏微分方程 partial differential equation）。

**阶 (order)**：方程中出现的**最高阶导数**的阶数。Transcript 明确说："if you hear n-order ODEs, it's **the number of times differentiation's been applied**."

**二阶 ODE** = 含二阶导数 $\dfrac{d^2y}{dx^2}$ 的 ODE。

最一般的（本课不解）形式：

$$a(x)\frac{d^2y}{dx^2}+b(x)\frac{dy}{dx}+c(x)\,y=d(x)$$

其中 $a(x),b(x),c(x),d(x)$ 叫**系数 (coefficients)**，是 $x$ 的一般函数。

本课只处理**常系数 (constant coefficients)** 的情况，即 $a,b,c$ 是常数：

$$a\frac{d^2y}{dx^2}+b\frac{dy}{dx}+cy=d(x)$$

### 2.2 三个分类术语（必背，考试可能直接问"classify this equation"）

| 术语 | 定义 | 判据 |
|---|---|---|
| **线性 (linear)** | 未知函数 $y$ 及其各阶导数都只出现**一次方**，且不互相相乘、不套在函数里 | $\dfrac{d^2y}{dx^2}$ 的幂次为 1（手册原文："because the second derivative $\frac{d^2y}{dx^2}$ is raised to the power of 1"）。出现 $y^2$、$(y')^2$、$y\,y'$、$\sin y$ 即为非线性 |
| **齐次 (homogeneous)** | 右端项 $d(x)=0$ | 方程"整个等于零"（transcript: "It's homogeneous **because the whole thing is set to zero**"） |
| **非齐次 (non-homogeneous / inhomogeneous)** | $d(x)\neq 0$ | 右端有非零项；**本课不解**，需要另一套规则（求特解 particular integral） |

> ⚠️ **材料勘误**：主手册第 3099 行印成 "If the value of $d(x)=0$ we can also say the equation is homogeneous, whilst if $d(x)=0$ the equation is called non-homogeneous"——第二处应为 $d(x)\neq 0$。周版 `Chapter9.md` 第 19 行的符号 `→=` 正是 $\neq$，是对的。

本课的目标方程因此是：

$$\boxed{\,a\frac{d^2y}{dx^2}+b\frac{dy}{dx}+cy=0\,}\qquad\text{齐次、线性、常系数、二阶 ODE}$$

**等价记号 (alternative notation)**——手册与讲义都强调这两种写法完全相同，文献中两种都会见到：

$$ay''+by'+cy=0 \qquad\Longleftrightarrow\qquad a\frac{d^2y}{dx^2}+b\frac{dy}{dx}+cy=0$$

三阶就是 $y'''$ 或 $\dfrac{d^3y}{dx^3}$，以此类推。

### 2.3 辅助方程法的完整推导（务必会自己推一遍）

这一段是本周唯一的"理论推导"，讲课花了 3 页 slide + 大段口述，考试可能要求复述思路。

**第 1 步：作有根据的猜测 (educated guess / ansatz)。**
手册原话："Let's just jump to an **educated guess**"；transcript 说 "It's almost like a **leap of faith**"。假设解的形式是指数函数：

$$y=e^{\lambda x}$$

其中 $\lambda$ 是待定常数。
（**为什么猜指数？** 因为指数函数微分后**形状不变**，只是前面多个常数 $\lambda$。这样 $y''$、$y'$、$y$ 三项才可能相互抵消成 0。Transcript 还给了物理直觉：这类方程描述振动/阻尼系统——弹簧、地震后的地面振动——其位移随时间"指数衰减 (exponential damping)"，所以指数形式是物理上合理的。）

**第 2 步：微分两次。**

$$\frac{dy}{dx}=\lambda e^{\lambda x},\qquad \frac{d^2y}{dx^2}=\lambda^{2}e^{\lambda x}$$

（用的就是 Week 2–3 的规则：$\dfrac{d}{dx}e^{kx}=ke^{kx}$，把常数"拿下来"。）

**第 3 步：代回原方程。**

$$a\lambda^{2}e^{\lambda x}+b\lambda e^{\lambda x}+c\,e^{\lambda x}=0$$

$$e^{\lambda x}\left(a\lambda^{2}+b\lambda+c\right)=0$$

**第 4 步：除以 $e^{\lambda x}$。**
关键性质：**$e^{\lambda x}$ 永远不可能为零**（指数函数恒正），所以可以安全地除掉。讲课时讲师专门停下来确认："Do you see why $e$ to anything can't be zero?"

$$\boxed{\,a\lambda^{2}+b\lambda+c=0\,}$$

这就是**辅助方程 (auxiliary equation)**，又叫**特征方程 (characteristic equation)**。两个名字指同一个东西。

**第 5 步：这是一个一元二次方程 (quadratic equation)，用求根公式解。**

$$\lambda=\frac{-b\pm\sqrt{b^{2}-4ac}}{2a}$$

得两个根 $\lambda_1,\lambda_2$。

> 💡 **最重要的实用结论**：以后遇到齐次二阶 ODE，**不必重复上面 1–4 步**，直接从原方程"读出" $a,b,c$ 写辅助方程即可。手册："you can **jump straight to this point**"。Transcript："we don't have to go through all of those steps ever again."

### 2.4 通解的两种形式（按判别式分情况）

设判别式 $\Delta=b^{2}-4ac$。

**情形 1：两根实且不等 (real and distinct)，$\Delta>0$，$\lambda_1\neq\lambda_2$**

$$\boxed{\,y=Ae^{\lambda_1x}+Be^{\lambda_2x}\,}$$

**情形 2：两根实且相等 (real and equal / repeated root)，$\Delta=0$，$\lambda_1=\lambda_2$**

$$\boxed{\,y=(A+Bx)\,e^{\lambda_1x}\,}$$

**情形 3：两根非实 (complex roots)，$\Delta=b^2-4ac<0$ —— 本课不考虑。**
手册与讲义都明确写 "We don't consider what happens when the two roots are not real in this course."
Transcript 补充："That's the kind of problem that comes across in **optics**, where you work with imaginary numbers. It's not relevant to what we want to do here."
（背景知识，不考：复根对应**振荡解** $e^{\alpha x}(A\cos\beta x+B\sin\beta x)$，即欠阻尼 underdamped 振动。）

**为什么解要"组合两个函数"？** 手册："Since there are two roots to the auxiliary equation, the general solution will be **a combination of the two functions**." 因为方程是线性的，两个解的任意线性组合仍是解（叠加原理 superposition）。

**为什么必须引入 $A$ 和 $B$？** 手册原话："we have added two new constants $A$ and $B$ as **we are combining multiple solutions we need to know how much each will contribute** to the final solution."——$A,B$ 是两个基础解各自的"权重"。

**为什么重根时要乘一个 $x$？** （手册未证，理解用）若 $\lambda_1=\lambda_2$，则 $Ae^{\lambda_1x}+Be^{\lambda_1x}=(A+B)e^{\lambda_1x}$ 实际只剩**一个**独立常数，信息量不够定二阶方程的解。必须再找一个与 $e^{\lambda_1x}$ 线性无关的解，就是 $xe^{\lambda_1x}$。可直接验证：当 $\Delta=0$ 时 $\lambda_1=-\frac{b}{2a}$，把 $y=xe^{\lambda_1x}$ 代入方程确实成立。

### 2.5 两个任意常数如何由两个条件确定 —— **本周核心**

**为什么恰好是两个常数？**
每积分一次产生一个积分常数。二阶导数要"还原"成 $y$，本质上要积分两次 ⇒ 两个任意常数。辅助方程法虽然没有真的做积分，但结果同样带两个常数 $A,B$，这是**二阶**方程的固有性质。

**两个常数 ⇒ 需要两条独立信息 ⇒ 解二元一次联立方程组 (simultaneous equations)。**
Transcript："We have two unknowns, $A$ and $B$, so we need **at least two equations**, simultaneous equations, to actually extract the values."

**两类条件（务必分清，这是本周最常混淆的点）：**

| | **初始条件 (initial conditions)** | **边界条件 (boundary conditions)** |
|---|---|---|
| 定义 | 在**同一个点**（通常 $x=0$ 或 $t=0$）给出函数值**和**导数值 | 在**两个不同的点**（$x=x_0$ 与 $x=x_1$）各给一个函数值 |
| 典型写法 | $y(0)=y_0$ 且 $y'(0)=y_0'$ | $T(0)=T_0$ 且 $T(L)=T_L$ |
| 问题名称 | **初值问题 (initial value problem, IVP)** | **边值问题 (boundary value problem, BVP)** |
| 物理含义 | 从一个已知状态"向前推演"未来 | 解必须**同时穿过两端的已知值**（"we have to make the solution meet at both points"） |
| 本周例子 | Example 9.1/9.2、Q9.1–9.5、Q9.8、Practical Ex.1 | Q9.6（Fick）、Q9.7（Fourier） |

手册原文定义：
- IVP: "we specify some initial values (i.e. when $x=0$, $v=0$, $t=0$), and we solve the ODE to find something about our process **in the future** or a certain distance away."
- BVP: "**upper and lower boundary conditions** are specified. This gives us more information — this means that we have to make the solution meet at **both** points."

**为什么需要条件？**（transcript 的重点科学论述）
"The thing with integration is **you always need information on the system**. We can arrive at a general expression — indefinite integration — but to actually get constants from that so we can predict something ahead of time, we need some information. **This is why measurements are really important.** Someone might have created a theory that represents our broad observations, but you need to actually make those accurate measurements so we can take that theory and predict something ahead of time. So **global observations** in any part of your system are really important."
⇒ 数学上的"任意常数"就是物理上的"必须去实地测量的量"。

### 2.6 通解 vs 全解（术语要点）

- **通解 (general solution)**：含未定常数 $A,B$，代表一整族曲线，全都满足方程。
- **全解 / 特解 (full solution / particular solution)**：代入条件定出 $A,B$ 后的**唯一**解。

手册的措辞有点混乱，Solutions9 里对 Q9.2 每一小题都写 "Then the **full general solution** is given by" ——严格说定完常数后就不是 general 了，应叫 **full solution**（practical 幻灯片就用的是 "full solution"）。**答题时写 "full solution" 更稳妥。**

### 2.7 稳态 (steady state) —— 主线 B 的前提

**定义**（回顾 Week 5）：系统的关键变量**不随时间变化**，即 $f(x)=c$（常数）。

**手册的水箱图解（Figure 9.1）**：往一个侧壁开了出水口的容器里注水。
- (a) **暂态 (transient state)**：水位在出水口以下时，水位随时间上升；
- (b) **稳态 (steady state)**：水位升到出水口高度后，**流入量 = 流出量**，水位不再变化。

**数学操作**：若 $\dfrac{\partial T}{\partial t}=0$（温度不随时间变），则 Fourier 第二定律 $\dfrac{dT}{dt}=\alpha\dfrac{d^{2}T}{dx^{2}}$ 的左边为 0，因 $\alpha\neq0$，得

$$\frac{d^{2}T}{dx^{2}}=0$$

同理 Fick 第二定律给出 $\dfrac{d^{2}C}{dx^{2}}=0$。

**这类方程反而更简单**：手册说 "In some ways, they look **easier** because they offer us a starting point to begin the process of integration." 直接积分两次即可，**不需要辅助方程**。Transcript："I don't have to use the auxiliary equation here, because I can just integrate that twice."

### 2.8 地球科学中的四类应用（手册列表，必记）

| 应用 | 方程 | 含义 |
|---|---|---|
| **运动学 (Kinematics)** | $\dfrac{d^{2}x}{dt^{2}}=a$ | 加速度 = 位置对时间的二阶导 |
| **力与运动 (Forces and motion)** | $F=ma=m\dfrac{d^{2}x}{dt^{2}}$ | 牛顿第二定律本身就是二阶 ODE |
| **Fick 定律 (质量扩散)** | 稳态：$\dfrac{d^{2}C}{dx^{2}}=0$ | 污染物/气体扩散的稳态浓度剖面 |
| **Fourier 定律 (热传导)** | 稳态：$\dfrac{d^{2}T}{dx^{2}}=0$ | 地温剖面、材料内温度分布 |

> ⚠️ 手册在这个列表里把自变量误印成 $t$（写作 $\frac{d^2C}{dt^2}=0$），但在正文与习题中一律是**空间变量 $x$**：$\frac{d^2C}{dx^2}=0$、$\frac{d^2T}{dx^2}=0$。以习题为准。

---

## 三、公式与图表

### 3.1 主线 A 公式卡

$$\text{方程：}\quad a\frac{d^{2}y}{dx^{2}}+b\frac{dy}{dx}+cy=0$$

$$\text{辅助方程：}\quad a\lambda^{2}+b\lambda+c=0$$

$$\text{求根：}\quad \lambda=\frac{-b\pm\sqrt{b^{2}-4ac}}{2a}$$

$$\text{实根不等：}\quad y=Ae^{\lambda_1x}+Be^{\lambda_2x}$$

$$\text{实根相等：}\quad y=(A+Bx)e^{\lambda_1x}$$

**导数（定常数时要用）：**

$$\text{不等根：}\quad \frac{dy}{dx}=A\lambda_1e^{\lambda_1x}+B\lambda_2e^{\lambda_2x}$$

$$\text{重根：}\quad \frac{dy}{dx}=Be^{\lambda_1x}+\lambda_1(A+Bx)e^{\lambda_1x}=\big(B+\lambda_1A+\lambda_1Bx\big)e^{\lambda_1x}\quad(\text{乘积法则})$$

**在 $x=0$ 处的简化（本周所有初值题都在 $x=0$）：** $e^{0}=1$，于是

$$y(0)=A+B,\qquad y'(0)=\lambda_1A+\lambda_2B\quad(\text{不等根})$$
$$y(0)=A,\qquad\;\; y'(0)=B+\lambda_1A\quad(\text{重根})$$

记住这两组就能秒写联立方程。

### 3.2 主线 B 公式卡（稳态直接积分）

$$\frac{d^{2}T}{dx^{2}}=0\;\xrightarrow{\ \int dx\ }\;\frac{dT}{dx}=a\;\xrightarrow{\ \int dx\ }\;T(x)=ax+b$$

⇒ **稳态一维温度/浓度剖面一定是直线**（线性梯度），$a$ 是梯度，$b$ 是截距。

**用两点边界条件定 $a,b$：** 已知 $T(0)=T_0$、$T(L)=T_L$：

$$b=T_0,\qquad a=\frac{T_L-T_0}{L}$$

$$\boxed{\,T(x)=T_0+\frac{T_L-T_0}{L}\,x\,}\qquad\text{（浓度同形：}C(x)=C_0+\tfrac{C_L-C_0}{L}x\text{）}$$

这其实就是**过两点的直线方程**——稳态扩散/传导题可以一眼写出答案，但**考试仍要写出"积分两次 + 代边界条件"的完整过程**。

**常加速度运动（Q9.8 的通式）：**

$$\frac{d^{2}x}{dt^{2}}=a\;\Rightarrow\;v=\frac{dx}{dt}=at+v_0\;\Rightarrow\;x=\tfrac12at^{2}+v_0t+x_0$$

### 3.3 传输定律公式卡（第一定律 / 第二定律 / 稳态，三层要分清）

**Fourier 热传导：**

| 层次 | 公式 | 含义 |
|---|---|---|
| 第一定律 (flux) | $J\propto-\dfrac{dT}{dx}$（完整式 $J=-k\dfrac{dT}{dx}$） | 热流正比于**负的**温度梯度 ⇒ 热从热流向冷 |
| 第二定律 (讲义 slide 20) | $\dfrac{dT}{dt}=\alpha\dfrac{d^{2}T}{dx^{2}}$ | 某点温度随时间的变化率，由该点温度的**空间二阶导**驱动 |
| 稳态 | $\dfrac{d^{2}T}{dx^{2}}=0$ | 令 $\dfrac{dT}{dt}=0$ |

$\alpha$ = **热扩散率 (thermal diffusivity)**，"speed heat diffuses"，由材料的**热导率 (thermal conductivity)、密度 (density)、比热容 (specific heat capacity)** 三者组合而成（$\alpha=k/\rho c_p$）。

**Fick 质量扩散：**

| 层次 | 公式 | 含义 |
|---|---|---|
| 第一定律 (flux) | $J=-D\dfrac{dC}{dx}$ | 质量通量 $J$ 正比于负浓度梯度 ⇒ 质从高浓度流向低浓度 |
| 第二定律 (讲义 slide 21) | $\dfrac{dC}{dt}=D\dfrac{d^{2}C}{dx^{2}}$ | 考虑了**质量守恒 (conservation of mass)** 的时间依赖形式 |
| 稳态 | $\dfrac{d^{2}C}{dx^{2}}=0$ | 令 $\dfrac{dC}{dt}=0$ |

$D$ = **扩散系数 (diffusion coefficient / diffusivity)**，取决于扩散物质的性质。
机制：**布朗运动 (Brownian motion)**，即随机热运动。

**两条定律形式完全相同**——手册与讲师反复强调：一个描述热，一个描述质，数学是同一个。

### 3.4 图表判读

**Figure 9.1（手册）：暂态 vs 稳态水箱示意**
- (a) transient：水位—时间曲线**上升**（$\frac{dh}{dt}>0$）
- (b) steady state：水位—时间曲线**水平**（$\frac{dh}{dt}=0$，流入=流出）
判读要点：看纵轴变量对时间的曲线是否变平——**变平 = 稳态 = 时间导数项可置零 = 二阶 ODE 可直接积分**。

**讲义 slide 8 的二阶导数判据（Week 5 回顾，本周复习用）**
对驻点 (stationary value) $x$（即 $f'(x)=0$）：

| $f''(x)$ | 结论 |
|---|---|
| $f''(x)<0$ | 极大值 (maximum) |
| $f''(x)>0$ | 极小值 (minimum) |
| $f''(x)=0$ | **无法判断**，可能是拐点/鞍点 (saddle point)，需进一步研究 |

**Transcript 提到的函数图（$f(x)=4x^4-2x^3-12x^2$）**：红线为函数、另一线为一阶导、绿线为二阶导。判读：一阶导给"某点的变化率"（如速度），二阶导给"变化率的变化率"（如加速度）并判定极值性质。

**稳态温度/浓度剖面图**：$T$–$x$ 图上是一条**直线**，斜率 $=\frac{T_L-T_0}{L}$。若题目给的剖面是曲线，说明**不是稳态**（或存在源汇项）。

---

## 四、课堂补充（transcript 独有内容）

本次讲课由代课讲师（Matt 在哥伦比亚 WHO 会议）主讲，前 1/3 是上周（integration by substitution）的复习，后面才进入正题。以下是**只在录音里、讲义与手册没有的内容**。

### 4.1 解析解 vs 数值解（贯穿全场的主线）

- **解析解 (analytical solution)**：把微分方程"积出来"，得到一个**公式**。"That's the answer we want to get to... it's much quicker."
- **数值解 (numerical solution)**：用求解器 (solver) **迭代数值** (iterate around values)，直到答案落进设定的**容差 (tolerance)** 内。
- 讲师明确说：**二阶微分方程正是"常常找不到解析解"的典型**——"second order differentials are certainly one of those instances where it's hard to find that analytical solution"。所以本周只解一个非常特殊的子集。
- 与并行的 **programming 课**呼应：解不出来时，把积分号里的函数写进程序，调用 solver；之前编程课已经用 solver 从初始条件出发积分过微分方程。
- 全课的能力目标："recognizing **which tool to apply** to a particular problem"——微积分学到后面就是**工具箱识别题**。

### 4.2 为什么地球科学要学这个（讲师的动机论述）

"Most of our theoretical rules — whether they predict things that change in space or time — are written as **differential equations**：热量如何在全球分布、排放如何从地表逸出、地下温度剖面如何变化、海洋与大气中的压力变化。**气候模式 (climate models) 做的事就是把这些方程积分**，从而预测未来的时空变化。"

职业路径的两侧：
- **应用型研究者/顾问 (applied researcher or consultant)**：更像工程做法——你**知道用哪个工具解哪类问题**，但不一定自己造工具，你熟悉的是"工具生态 (ecosystem of tools)"。
- **基础型研究者**：可能提出或实现新理论，这时才真正需要这种层级的微积分。
- **两边都必须会的**："knowing what differential equations **mean** — what's the narrative behind them? What are they representing?" 读论文时人家用方程写理论，你要能读出**它的英文（口语）版本是什么**。

### 4.3 齐次二阶 ODE 的物理场景：振荡系统（讲义未写，重要）

讲师给这个抽象方程配了物理背景——**右端为零 = 没有外力 (no force)**：

- **弹簧振子 (spring)**：一块砝码挂在弹簧上，放手让它振，最终**阻尼 (damp)** 下来达到平衡。$y$ 是高度，$t$ 是时间。
- **地震 (earthquakes)**：理想化情形下能量一次性巨量释放，之后地面振动逐渐衰减。"You get huge displacement at the beginning, a vibrating system, and then it starts to calm down."
- 这解释了**为什么猜指数解**："imagine you're trying to predict that displacement as a function of time. There's an **exponential damping** — the first stages are quick, and then it starts to decrease exponentially. So the exponential form relates to these second order differentials."
- **现实的告诫**：真实情况右端通常**不为零**——"force is an instant. There isn't suddenly a release of energy and then it goes away. There will be something that varies with time." 所以真实问题多是**非齐次**的，本课的齐次假设是理想化。

### 4.4 火箭发射的例子（解释"加速度也在变"）

"you can visualize that in terms of a **rocket launch** — 如果是恒定加速度，你会看到速度线性增长；但它不是恒定加速度，因为**燃料在减少、大气越来越稀薄、引力在减小**，这些合起来使得加速度本身也在变化。"
⇒ 说明二阶导数的常见用途：**当"变化率本身在变"时**。

### 4.5 术语提醒：讲师口中的 "gamma" 就是 $\lambda$

Transcript 全程把辅助方程的根念作 **"gamma"**（如 "work out this constant, gamma"、"two values of gamma"），而讲义、手册、习题一律写 $\lambda$（lambda）。**是同一个东西**，看录音时别被绕晕。
另外讲师有一处口误把两个根说成 "$y_1$ and $y_2$"（应为 $\lambda_1,\lambda_2$）。

### 4.6 热传导的生活化解释（Fourier 第二定律的"英文版"）

"一杯热茶放在厨房里最后会凉下来，热量从它那里分布出去直到达到平衡。如果你在离杯子一定距离处测**温度的变化率**，驱动这个变化率的就是右端项——**空间中的温度差**。"

- 温差大（比如 1000°C 对着很冷的环境）⇒ 变化率**很快**；
- 温差小（30°C 对 25°C）⇒ 梯度很小 ⇒ 变化率**很慢**。
- "That's what that equation is describing. It's describing the **observed behavior in the real world**."

**烤箱例子（讲 $\alpha$ 的意义）**：你不想在用烤箱时被同等的热量烤到。决定这个的就是材料参数 $\alpha$。
- **铜 (copper)** 是极好的导热体 ⇒ 用铜做烤箱就完蛋了，热量直接传到你手上；
- **玻璃与陶瓷 (glass and ceramic)** 导热很差 ⇒ 所以保温瓶用玻璃/陶瓷做，热量传不出去，**温度变化率很慢，东西保温更久**。
- 补充：导热好的材料通常导电也好。
- **历史**："The whole **steam era** was built around knowing where heat can go, what can keep it trapped, how do you push the energy from that steam system into turning a set of wheels." 热与能量的迁移驱动了工业革命，Fourier 第二定律在其中非常关键。

> ⚠️ **讲师此处有一处口误**：他说 "you need to know what alpha is — and that's the **thermal conductivity**"。严格说 $\alpha$ 是**热扩散率 (thermal diffusivity)**，讲义 slide 20 写得很清楚：$\alpha$ 由热导率、密度、比热容三者组合而成。**以讲义为准。** 他还有一次把 $\alpha$ 说成 "gamma value"，同为口误。

### 4.7 质量扩散的生活化解释（Fick 第二定律的"英文版"）

"如果你在调饮料——一大桶水里倒进一点浓缩果汁 (cordial)，它最终会散布到整桶水里。这就是质量的迁移。"
"如果我在一个大水箱里某处放入高浓度物质，想测量它在空间每一点随时间怎么扩散——我测到的**左端那个量**，是由**浓度梯度**决定的。倒进去的量很大 ⇒ 扩散很快；倒一点点 ⇒ 要很久才能扩散到我所有的测点。"

**扩散系数 $D$ 的直觉（"猫与狗"类比，很好记）**：
"有些分子很大、结构很怪；有些很小，像水和臭氧，能很快地穿过东西。**这有点像一只猫——它能把自己缩小从别的分子之间钻过去；但如果是一只大狗，它就会一路撞到所有东西。** 这就是参数 $D$（diffusivity）所代表的。"

### 4.8 上周复习部分（transcript 前段，非本周考点但对全课有用）

- **积分换元 (integration by substitution)** 是**链式法则的逆过程**。核心原则："if we integrate something with respect to a variable, **that something has to be written using that variable — the two have to match**." 即 $\int(\cdot)\,du$ 里面必须全是 $u$。
- 若是定积分，**上下限也必须一起换成新变量的限**。
- **自检技巧（很实用）**："the good thing about integration is when you come to an answer, you can **check if that answer's true by differentiating it again**." ——积分结果求导应还原被积函数。这个技巧本周同样适用：**把求得的 $y$ 代回原 ODE 检验**。
- **静水压方程 (hydrostatic equation)**：描述任何流体（大气或水）中的压力变化。恒温情形 ⇒ **分离变量 (separation of variables)** 积分，得 $p$ 随高度**指数衰减**；温度随高度变化的更真实情形 ⇒ 必须**换元**（新变量含 $T_{\text{surface}}-0.01z$）。
- **压力与温度的物理耦合**：高压处分子多 ⇒ 撞击我们、传递动能多 ⇒ 感觉更热；低压处分子少 ⇒ 感觉更冷。二者通过**理想气体方程 (ideal gas equation)** 联系。
- **真实大气的复杂性（很好的地球科学插曲）**：对流层顶 (tropopause) 处温度会突然升高，导致压力剖面转折，**行星边界层 (planetary boundary layer) 被"盖住"**——像一个盖子，使空气无法向上通风。这是**夜间城市污染**的一大问题：大气被压缩，污染物散不出去。
- **真空中的自由落体**：无摩擦力时，下落速度**与质量完全无关**——真空中砖头和羽毛同速下落（Week 7 已证）。真实情况有摩擦阻力与尾流拖曳。

---

## 五、Practical 要点

### 5.1 Practical 的目的

Practical 幻灯片 (`practical9_soln(1).md`) 有 2 道课堂例题，Exercises9 有 8 道题。讲师说得很直白："**The whole point of the practicals today are playing around with that approach.** When you're given that functional form of a second order equation, there's a **workflow** to get to the answer."
⇒ Practical 的目的不是发明新方法，而是**把两条流程练成肌肉记忆**。

### 5.2 万能解题流程（背下来直接套）

**【流程 A】齐次线性二阶 ODE（Q9.1–9.4、Practical Ex.1）**

1. **写出方程并识别类型**：确认它是 $ay''+by'+cy=0$（右端为 0、线性、常系数）。读出 $a,b,c$（注意符号和缺项）。
2. **写辅助方程**：$a\lambda^{2}+b\lambda+c=0$。
3. **求根**：能因式分解就分解，否则用 $\lambda=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$。
4. **判断情形并写通解**：不等 ⇒ $y=Ae^{\lambda_1x}+Be^{\lambda_2x}$；相等 ⇒ $y=(A+Bx)e^{\lambda_1x}$。
   *（若只问 general solution，做到这里即止。）*
5. **写出 $y$ 与 $\dfrac{dy}{dx}$ 两个表达式**。
6. **代入两个条件**（通常 $x=0$，用 $e^0=1$ 化简），得两条方程。
7. **解联立方程**求 $A,B$。
8. **写出全解 (full solution)**，并**代回原方程或条件检验**。

**【流程 B】稳态 / 常加速度（Q9.5–9.8、Practical Ex.2）**

1. **写出方程**：$\frac{d^2C}{dx^2}=0$、$\frac{d^2T}{dx^2}=0$ 或 $\frac{d^2x}{dt^2}=\text{const}$。（物理题先做**受力分析**求出净力再除以 $m$。）
2. **第一次积分** ⇒ 得一阶导（梯度），带常数 1。
3. **第二次积分** ⇒ 得函数本身，带常数 2。
4. **代入两个条件**（初值：同一点的值和导数；边值：两点的值）。
5. **解出两个常数**，写出完整表达式。
6. **代入题目要求的具体数值**并**回答物理问题**（是否超标？温度多少？）——**别忘了写单位和结论句**。

### 5.3 Practical 课堂例题逐题解析

#### **Exercise 1**（`practical9_soln(1).md`）

方程：$\dfrac{d^{2}y}{dx^{2}}-\dfrac{dy}{dx}-6y=0$
（幻灯片 OCR 把 $6y$ 印成了 $6$，但从解答用的 $a=1,b=-1,c=-6$ 可确认原题是 $-6y$。）

**(a) 辅助方程：**

$$\lambda^{2}-\lambda-6=0$$

**(b) 求根：**

$$\lambda=\frac{-b\pm\sqrt{b^{2}-4ac}}{2a}=\frac{-(-1)\pm\sqrt{(-1)^{2}-4\cdot1\cdot(-6)}}{2\cdot1}=\frac{1\pm\sqrt{25}}{2}=\frac{1\pm5}{2}$$

$$\lambda_1=-2,\qquad \lambda_2=3$$

（也可直接分解：$(\lambda-3)(\lambda+2)=0$。）

**(c) 通解**（实根不等）：

$$y=Ae^{-2x}+Be^{3x}$$

**(d) 全解**，条件 $y(0)=3$、$y'(0)=4$：

$$y=Ae^{-2x}+Be^{3x},\qquad \frac{dy}{dx}=-2Ae^{-2x}+3Be^{3x}$$

代 $x=0$（$e^0=1$）：

$$\begin{cases}A+B=3 &\text{(1)}\\ -2A+3B=4 &\text{(2)}\end{cases}$$

由 (1)：$A=3-B$，代入 (2)：$-2(3-B)+3B=4\Rightarrow-6+5B=4\Rightarrow B=2$。
代回 (1)：$A=1$。

$$\boxed{y=e^{-2x}+2e^{3x}}$$

**检验**：$y(0)=1+2=3$ ✓；$y'=-2e^{-2x}+6e^{3x}$，$y'(0)=-2+6=4$ ✓。

#### **Exercise 2：Fick 定律（与 Q9.6 同题）**

见 5.4 的 Q9.6。幻灯片给出的解写成以 **km 为单位**：$C(x)=1-\frac{9}{10}x$，代 $x=0.5$ km 得 $0.55$ mg/m³ > 0.5 ⇒ **超标**。

### 5.4 Exercises 9 逐题解析

> **说明**：`Exercises9(1).md` 与 `Solutions9.md` 是 PDF 转出的，公式为图片，转换后只剩文字骨架；下面的方程与数字是依据"根的数值 + 条件 + 答案"反推重建的，**已逐题验算自洽**。反推处会标注。

---

#### **Question 9.1**：写辅助方程、求根、写通解

**(a)** $\dfrac{d^{2}y}{dt^{2}}+6\dfrac{dy}{dt}-16y=0$

辅助方程：$\lambda^{2}+6\lambda-16=0\Rightarrow(\lambda+8)(\lambda-2)=0$

$$\lambda_1=2,\qquad\lambda_2=-8\quad(\text{实、不等})$$

$$y=Ae^{2t}+Be^{-8t}$$

*（Solutions9 文件从 (b) 开始，(a) 的解答缺失——上式为自行补全，可由 Q9.2(a) 的答案反证一致。）*

**(b)** $8\dfrac{d^{2}y}{dt^{2}}-2\dfrac{dy}{dt}-y=0$

辅助方程：$8\lambda^{2}-2\lambda-1=0$

$$\lambda=\frac{2\pm\sqrt{4+32}}{16}=\frac{2\pm6}{16}\Rightarrow \lambda_1=\frac12,\quad\lambda_2=-\frac14$$

实、不等：

$$y(t)=Ae^{t/2}+Be^{-t/4}$$

**(c)** $4\dfrac{d^{2}y}{dt^{2}}-24\dfrac{dy}{dt}+27y=0$

辅助方程：$4\lambda^{2}-24\lambda+27=0$

$$\lambda=\frac{24\pm\sqrt{576-432}}{8}=\frac{24\pm12}{8}\Rightarrow\lambda_1=\frac92,\quad\lambda_2=\frac32$$

$$y(t)=Ae^{9t/2}+Be^{3t/2}$$

**(e)**（题号跳过 (d)，是原文印刷疏漏）$\dfrac{d^{2}y}{dt^{2}}-4y=0$

辅助方程：$\lambda^{2}-4=0$（注意 $b=0$）

$$\lambda_1=-2,\qquad\lambda_2=2$$

$$y(t)=Ae^{2t}+Be^{-2t}$$

> 💡 这个解等价于 $\cosh/\sinh$ 组合，但本课按指数形式写即可。

---

#### **Question 9.2**：用条件定 $A,B$，写全解

> ⚠️ Solutions9 里 (b)(c)(d) 都写 "From Question **9.1(a)**"，是复制粘贴错误，实际应分别对应 9.1(b)(c)(e)。

**(a)** 方程同 9.1(a)，条件 $y=2$、$\dfrac{dy}{dx}=-6$（当 $x=0$）

$$y=Ae^{2x}+Be^{-8x},\qquad \frac{dy}{dx}=2Ae^{2x}-8Be^{-8x}$$

代 $x=0$：

$$\begin{cases}A+B=2\\ 2A-8B=-6\end{cases}$$

由第一式 $A=2-B$ ⇒ $2(2-B)-8B=-6\Rightarrow 4-10B=-6\Rightarrow B=1$，$A=1$。

$$\boxed{y=e^{2x}+e^{-8x}}$$

**(b)** 方程同 9.1(b)，条件 $y=10$、$\dfrac{dy}{dx}=2$（当 $x=0$）

$$y=Ae^{x/2}+Be^{-x/4},\qquad\frac{dy}{dx}=\frac{A}{2}e^{x/2}-\frac{B}{4}e^{-x/4}$$

$$\begin{cases}A+B=10\\ \tfrac12A-\tfrac14B=2\;\Longrightarrow\;2A-B=8\end{cases}$$

两式相加：$3A=18\Rightarrow A=6$，$B=4$。

$$\boxed{y=6e^{x/2}+4e^{-x/4}}$$

**(c)** 方程同 9.1(c)，条件 $y=0$、$\dfrac{dy}{dx}=12$（当 $x=0$）

$$y=Ae^{9x/2}+Be^{3x/2},\qquad\frac{dy}{dx}=\frac92Ae^{9x/2}+\frac32Be^{3x/2}$$

$$\begin{cases}A+B=0\\ \tfrac92A+\tfrac32B=12\;\Longrightarrow\;9A+3B=24\end{cases}$$

由 $B=-A$：$9A-3A=24\Rightarrow6A=24\Rightarrow A=4$，$B=-4$。

$$\boxed{y=4e^{9x/2}-4e^{3x/2}=4\left(e^{9x/2}-e^{3x/2}\right)}$$

**(d)** 方程同 9.1(e)，条件 $y=-4$、$\dfrac{dy}{dx}=0$（当 $x=0$）

$$y=Ae^{2x}+Be^{-2x},\qquad\frac{dy}{dx}=2Ae^{2x}-2Be^{-2x}$$

$$\begin{cases}A+B=-4\\ 2A-2B=0\;\Rightarrow\;A=B\end{cases}$$

$$A=B=-2$$

$$\boxed{y=-2e^{2x}-2e^{-2x}=-2\left(e^{2x}+e^{-2x}\right)}$$

> **物理直觉**：$y'(0)=0$ 表示起点在极值处；解关于 $x$ 对称（偶函数），是双曲余弦形状 $-4\cosh 2x$。

---

#### **Question 9.3**：给定 $y$ 与梯度的初始条件求解

解答文件给出：根为 $\lambda_1=\dfrac43$、$\lambda_2=-2$；条件 $y=-6$、$\dfrac{dy}{dx}=-18$（当 $x=0$）。

*（反推）* 与这两根相容的方程是 $3\dfrac{d^{2}y}{dx^{2}}+2\dfrac{dy}{dx}-8y=0$：

$$3\lambda^{2}+2\lambda-8=0\Rightarrow\lambda=\frac{-2\pm\sqrt{4+96}}{6}=\frac{-2\pm10}{6}\Rightarrow\lambda_1=\frac43,\ \lambda_2=-2\ \checkmark$$

通解（实、**不等**）：

$$y=Ae^{4x/3}+Be^{-2x},\qquad\frac{dy}{dx}=\frac43Ae^{4x/3}-2Be^{-2x}$$

代 $x=0$：

$$\begin{cases}A+B=-6\\ \tfrac43A-2B=-18\;\Longrightarrow\;4A-6B=-54\end{cases}$$

由 $A=-6-B$：$4(-6-B)-6B=-54\Rightarrow-24-10B=-54\Rightarrow B=3$，$A=-9$。

$$\boxed{y=-9e^{4x/3}+3e^{-2x}}$$

**检验**：$y(0)=-9+3=-6$ ✓；$y'(0)=\frac43(-9)-2(3)=-12-6=-18$ ✓。

> ⚠️ **重要勘误**：`Solutions9.md` 在此写 "so the roots are $\frac43$ and $-2$. So as the roots are **real and equal**..." ——$\frac43\neq-2$，显然是**实且不等**，"equal" 是原文笔误（大概是从 Q9.4 复制过来的）。主手册第 3347 行同样有这个错误，且把 $\frac43$ 排版成了 "3/4"（若取 $3/4$ 则 $A,B$ 不是整数，可反证 $\frac43$ 才对）。**不要被这句话误导去套重根公式。**

---

#### **Question 9.4**：重根情形（本周唯一）

解答文件给出：$\lambda_1=\lambda_2=2$。
*（反推）* 相容的方程为 $\dfrac{d^{2}y}{dx^{2}}-4\dfrac{dy}{dx}+4y=0$：

$$\lambda^{2}-4\lambda+4=0\Rightarrow(\lambda-2)^{2}=0\Rightarrow\lambda_1=\lambda_2=2$$

判别式 $\Delta=16-16=0$ ⇒ **实且相等** ⇒ 用重根公式：

$$\boxed{y=(A+Bx)e^{2x}}$$

**这是本周唯一考重根的地方，务必记住这个形式和触发条件（$\Delta=0$）。**

---

#### **Question 9.5：牛顿运动定律作为二阶 ODE**

方程形式：

$$F=ma=m\frac{dv}{dt}=m\frac{d^{2}x}{dt^{2}}$$

三个表达式彼此等价。要求"距离 vs 时间"就必须**积分两次**：先得 $v(t)$，再由 $v=\frac{dx}{dt}$ 得 $x(t)$。

**(a) 30° 斜坡，无空气阻力、无摩擦，$v(0)=0$**

受力分析（回顾 Chapter 7 Example 2）：
- 沿斜面下滑的分力 $F_2=mg\sin\theta$
- 垂直斜面的法向力 $F_1=N=mg\cos\theta$

无摩擦 ⇒ 净力

$$F=mg\sin(30^{\circ})=m\frac{dv}{dt}\;\Longrightarrow\;\frac{dv}{dt}=g\sin(30^{\circ})$$

**注意 $m$ 被消掉了**——这正是"真空中所有物体同速下落"的原因（transcript 强调过）。

第一次积分（$v$ 从 0 到 $v$，$t$ 从 0 到 $t$）：

$$\int_{0}^{v}dv=\int_{0}^{t}g\sin(30^{\circ})\,dt\;\Longrightarrow\;v=g\sin(30^{\circ})\,t=\tfrac12gt\approx4.9\,t\ \text{m/s}$$

第二次积分（$x$ 从 0 到 $x$）：

$$\int_{0}^{x}dx=\int_{0}^{t}g\sin(30^{\circ})t\,dt\;\Longrightarrow\;x=\tfrac12g\sin(30^{\circ})t^{2}=\tfrac14gt^{2}\approx2.45\,t^{2}\ \text{m}$$

**结论句（解答文件明确要求写）**："**速度随时间线性增长，距离随时间二次增长 (velocity increases linearly and the distance quadratically)。**"

**(b) 同上但加摩擦力 $\mu N$，$\mu=0.1$**

摩擦力沿斜面向上，$N=mg\cos(30^{\circ})$：

$$F=mg\sin(30^{\circ})-\mu\,mg\cos(30^{\circ})$$

$$\frac{dv}{dt}=g\left[\sin(30^{\circ})-\mu\cos(30^{\circ})\right]=9.81\times(0.5-0.1\times0.8660)=9.81\times0.4134\approx4.06\ \text{m/s}^2$$

$$v\approx4.06\,t\ \text{m/s},\qquad x\approx2.03\,t^{2}\ \text{m}$$

同样是**速度线性、距离二次**，只是系数变小了。

> ⚠️ **解答文件此处有错**：`Solutions9.md` 与主手册都写 "$F=mg\sin(30°)-mg\cos(30°)$"，**漏掉了 $\mu$**。题干明确说摩擦力 $=\mu\times N$ 且 $\mu=0.1$，所以必须是 $-\mu mg\cos(30°)$。若照解答漏写 $\mu$，则 $\sin30°-\cos30°=0.5-0.866<0$，加速度为负——物块反而"往上加速"，物理上荒谬（正确解读是：此时静摩擦足以让物块不动）。**答题请写含 $\mu$ 的正确式子。**

---

#### **Question 9.6：Fick 扩散定律（边值问题）**

**题设**：工业焚烧炉烟囱处颗粒物浓度 $C_0=1.0$ mg m⁻³；距工厂 1 km 处 $C_{1km}=0.1$ mg m⁻³。房屋在 500 m 处。用稳态一维 Fick 定律 $\dfrac{d^{2}C}{dx^{2}}=0$，求房屋处浓度；限值为 0.5 mg m⁻³，是否超标？

**解**：

第一次积分：

$$\frac{dC}{dx}=a\quad(\text{常数，即浓度梯度})$$

第二次积分：

$$C(x)=ax+b$$

代入边界条件：
- $C(0)=C_0\Rightarrow b=C_0$
- $C(L)=C_{1km}$（$L=1$ km）$\Rightarrow aL+C_0=C_{1km}\Rightarrow a=\dfrac{C_{1km}-C_0}{L}$

$$\boxed{C(x)=C_0+\frac{C_{1km}-C_0}{L}\,x}$$

代数值（取 $L=1$ km，$x$ 以 km 计）：

$$C(x)=1+\frac{0.1-1}{1}x=1-0.9x=1-\frac{9}{10}x$$

**房屋处 $x=0.5$ km：**

$$C(0.5)=1-0.9\times0.5=1-0.45=0.55\ \text{mg m}^{-3}$$

**结论**：$0.55>0.5$ ⇒ **超过限值，是的，房屋处浓度超标。**

> 单位换算提醒：若用米作单位，则 $C(x)=1-9\times10^{-4}x$（$x$ 以 m 计），$C(500)=1-0.45=0.55$，结果相同。**只要前后单位一致即可**，但务必写清楚。
>
> ⚠️ 解答文件写 "**Differentiating** once gives us / Differentiating twice gives us"——应为 "**Integrating**"。这是原文笔误，别被带偏方向。

---

#### **Question 9.7：Fourier 热传导定律（边值问题）**

**题设**：地下 3 km 处有稳态温度 250 °C 的热花岗岩床；近地表温度稳定在 10 °C。用稳态一维 Fourier 定律 $\dfrac{d^{2}T}{dx^{2}}=0$，推导地表到花岗岩之间的温度剖面。

**解**（与 Q9.6 同构）：

$$\frac{d^{2}T}{dx^{2}}=0\;\Rightarrow\;\frac{dT}{dx}=a\;\Rightarrow\;T(x)=ax+b$$

边界条件 $T(0)=T_0=10$、$T(3000\ \text{m})=T_{3km}=250$：

$$b=T_0=10,\qquad a=\frac{T_{3km}-T_0}{L}=\frac{250-10}{3000}=\frac{240}{3000}=0.08\ ^{\circ}\text{C m}^{-1}$$

$$\boxed{T(x)=10+0.08x\quad(x\ \text{以 m 计})}$$

等价写法（$x$ 以 km 计）：$T(x)=10+80x$。

**通式**：

$$T(x)=T_0+\frac{T_{3km}-T_0}{L}\,x$$

**地球科学解读（务必会说）**：
- 斜率 $a=0.08\ ^{\circ}$C/m $=80\ ^{\circ}$C/km，就是**地温梯度 (geothermal gradient)**。
- 全球平均地温梯度约 25–30 °C/km，本题的 80 °C/km **明显偏高**，暗示这是热流异常区（如火山/岩浆活动区或地热田），有地热开发潜力。
- 稳态假设 ⇒ 剖面是**直线**；若实测剖面弯曲，说明系统未达稳态、或存在地下水对流/放射性生热等源汇项。
- 负号约定：Fourier 第一定律 $J=-k\frac{dT}{dx}$ 中，此处 $\frac{dT}{dx}>0$（越深越热）⇒ 热通量 $J<0$，即**热量向上（向地表）传导**，物理正确。

> ⚠️ 解答文件此处写 "Therefore the solution to **Fick's law** is..." ——应为 **Fourier's law**，复制粘贴笔误。

---

#### **Question 9.8：恒定加速度下的位移（通式推导）**

**题设**：物体以初速度运动并受恒定加速度，$\dfrac{d^{2}x}{dt^{2}}=a$（$a$ 为常数），起始位置 $x=0$，初速度 $v_0$。

**解**：

第一次积分：

$$\frac{dx}{dt}=v=at+B$$

当 $t=0$ 时 $v=v_0$ ⇒ $B=v_0$：

$$v=at+v_0$$

第二次积分：

$$x=\tfrac12at^{2}+v_0t+C$$

当 $t=0$ 时 $x=0$ ⇒ $C=0$：

$$\boxed{x(t)=v_0t+\tfrac12at^{2}}$$

**这就是中学的 SUVAT 公式 $s=ut+\frac12at^2$** ——本周的意义在于：它不是"背下来的公式"，而是**二阶 ODE 积分两次的结果**，两个常数分别对应"初速度"和"初位置"。这题是理解"两个常数 = 两条物理信息"的最佳范例。

### 5.5 解题技巧汇总

1. **先看右端是不是 0**：是 0 且含 $y$ 项 ⇒ 走辅助方程；是 0 但**不含 $y$ 项**（即 $\frac{d^2y}{dx^2}=0$）⇒ 直接积分两次（更快，别浪费时间写辅助方程）；右端是非零常数 ⇒ 直接积分两次。
2. **能因式分解就别用求根公式**（$\lambda^2+6\lambda-16=(\lambda+8)(\lambda-2)$ 秒解），省时且不易算错。
3. **缺项要补 0**：$y''-4y=0$ 的 $b=0$；$8y''-2y'-y=0$ 的 $c=-1$（不是 $1$）。
4. **在 $x=0$ 处代入时 $e^0=1$**，联立方程立刻变成简单的二元一次组。
5. **分数根不要慌**：$\lambda=\frac12$ 就写 $Ae^{x/2}$，求导得 $\frac{A}{2}e^{x/2}$；解联立时**先整体乘以分母**（如乘 4）化成整数系数。
6. **答案自检两步**：(i) 代 $x=0$ 验 $y$ 和 $y'$ 是否等于给定条件；(ii) 把 $y$ 代回原 ODE 看是否为 0。这是上周讲师强调的"积分完再微分回去检查"的同一思想。
7. **实际问题必须回答实际问题**：算出 0.55 mg/m³ 后要明确写"**高于 0.5 的限值**"；算出 $T(x)$ 后要说明它是线性剖面/地温梯度是多少。
8. **单位一致性**：Q9.6 的 km 与 m、Q9.7 的 °C/m 与 °C/km，选定后全程统一，并在答案中标注单位。

---

## 六、易错点 / 重点难点

### 6.1 概念类

1. **混淆"二阶导数"与"二次幂"**。$\frac{d^2y}{dx^2}$ 是"微分两次"，不是 $\left(\frac{dy}{dx}\right)^2$。方程仍是**线性**的，正因为导数的**幂次**是 1。
2. **齐次的判据是"右端 = 0"，不是"没有常数项"**。$c\,y$ 项存在不影响齐次性；关键看 $d(x)$。
3. **辅助方程的 $\lambda$ 不是解**。$\lambda$ 只是指数里的系数，解是 $y=Ae^{\lambda x}+\dots$。别把 $\lambda_1=2$ 直接当成 $y=2$。
4. **初始条件 vs 边界条件搞混**。一个点给"值 + 斜率" = 初值；两个点各给一个"值" = 边值。它们的**代入方式不同**：边值题不需要求导。
5. **忘记稳态假设是"人为施加"的**。Fourier/Fick 第二定律本身是**偏微分方程**（含 $\frac{\partial T}{\partial t}$ 和 $\frac{\partial^2T}{\partial x^2}$）；只有令时间导数为 0，才退化成本课能解的常微分方程。**答题时要写明 "assuming steady state"。**
6. **误以为真实系统都是齐次的**。Transcript 明确警告：真实中右端通常有随时间变化的项（力不是瞬时的），齐次只是理想化。
7. **$\alpha$ 是热扩散率不是热导率**（讲师口误处）。$\alpha=k/(\rho c_p)$，融合了热导率、密度、比热容三者。

### 6.2 计算类

8. **重根时忘了乘 $x$**。$\Delta=0$ 必须写 $(A+Bx)e^{\lambda x}$；写成 $Ae^{\lambda x}+Be^{\lambda x}$ 等于只有一个常数，无法满足两个条件。
9. **重根求导忘用乘积法则**。$\frac{d}{dx}\left[(A+Bx)e^{\lambda x}\right]=Be^{\lambda x}+\lambda(A+Bx)e^{\lambda x}$，两项都要有。
10. **首项系数 $a\neq1$ 时直接照抄系数进辅助方程**。$8y''-2y'-y=0\Rightarrow8\lambda^2-2\lambda-1=0$（不要先随手除以 8 又忘了除完）。
11. **求根公式的符号**：$-b$ 的负号、$c$ 为负时 $-4ac$ 变正号。Practical Ex.1 里 $-4\cdot1\cdot(-6)=+24$ 是典型陷阱。
12. **联立方程解完只求出一个常数就收工**。必须两个都求出并写回通解。
13. **积分两次只写一个常数**。$\frac{d^2C}{dx^2}=0$ 必须依次得到 $\frac{dC}{dx}=a$ 和 $C=ax+b$，**两个常数缺一不可**。
14. **单位不一致导致数值错**（Q9.6 最常见）：1 km = 1000 m，梯度写成 $-0.9$ /km 还是 $-0.0009$ /m 要与代入的 $x$ 匹配。
15. **Q9.5(b) 漏掉摩擦系数 $\mu$**（连官方解答都错了）。$F=mg\sin\theta-\mu mg\cos\theta$。

### 6.3 材料本身的勘误清单（复习时不要被误导）

| 位置 | 原文 | 应为 |
|---|---|---|
| 主手册 3099 行 | "if $d(x)=0$ the equation is called non-homogeneous" | $d(x)\neq0$ |
| 手册应用列表 | $\frac{d^2C}{dt^2}=0$、$\frac{d^2T}{dt^2}=0$ | $\frac{d^2C}{dx^2}=0$、$\frac{d^2T}{dx^2}=0$ |
| Exercises Q9.1 | 小题编号 (a)(b)(c)**(e)** | 应为 (a)(b)(c)(d) |
| Solutions Q9.2(b)(c)(d) | 都写 "From Question 9.1**(a)**" | 应分别对应 9.1(b)(c)(e) |
| Solutions Q9.3 | 根 $\frac43$ 与 $-2$，却说 "real and **equal**" | real and **distinct** |
| 主手册 3347 行 | 根排版成 "3/4" | 应为 $\frac43$ |
| Solutions Q9.5(b) | $F=mg\sin30°-mg\cos30°$ | $F=mg\sin30°-\mu\,mg\cos30°$ |
| Solutions Q9.6/9.7 | "**Differentiating** once/twice gives us" | "**Integrating** once/twice" |
| Solutions Q9.7 | "the solution to **Fick's** law" | **Fourier's** law |
| Solutions Q9.2 各题 | "the full **general** solution" | full solution（已定常数就不再是 general） |
| Practical Ex.1 题面 | $\frac{d^2y}{dx^2}-\frac{dy}{dx}-6=0$ | $-6y=0$ |
| Transcript | "gamma"、"$y_1$ and $y_2$"、$\alpha$ 是 "thermal conductivity" | $\lambda$、$\lambda_1,\lambda_2$、thermal **diffusivity** |

### 6.4 本周最该练熟的三件事

1. **辅助方程 → 判别式 → 选公式 → 代条件 → 解联立**，这条流水线要在 3 分钟内跑完一道题。
2. **重根公式 $(A+Bx)e^{\lambda x}$** 及其求导（本周唯一"特殊情形"，考点密度高）。
3. **稳态两点边值问题**：$\frac{d^2f}{dx^2}=0\Rightarrow f=ax+b\Rightarrow$ 过两点的直线，且能说清 Fick/Fourier 的**物理意义与地球科学解读**。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| ordinary differential equation (ODE) | 常微分方程 | 只含一个自变量的微分方程 |
| second-order ODE | 二阶常微分方程 | 最高含二阶导数 $\frac{d^2y}{dx^2}$ |
| order (of an ODE) | 阶 | 微分被施加的次数 |
| coefficients | 系数 | 方程中 $a,b,c,d$；本课限定为**常系数** |
| constant coefficients | 常系数 | $a,b,c$ 为常数而非 $x$ 的函数 |
| linear | 线性 | $y$ 及其导数都是一次幂 |
| homogeneous | 齐次 | 右端项 $d(x)=0$ |
| non-homogeneous / inhomogeneous | 非齐次 | $d(x)\neq0$；本课不解 |
| auxiliary equation | 辅助方程 | $a\lambda^2+b\lambda+c=0$ |
| characteristic equation | 特征方程 | 同上，另一个名字 |
| quadratic equation | 一元二次方程 | 辅助方程的形式 |
| quadratic formula | 求根公式 | $\lambda=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$ |
| roots | 根 | $\lambda_1,\lambda_2$ |
| real and distinct | 实且不等 | $\Delta>0$ ⇒ $y=Ae^{\lambda_1x}+Be^{\lambda_2x}$ |
| real and equal / repeated root | 实且相等 / 重根 | $\Delta=0$ ⇒ $y=(A+Bx)e^{\lambda_1x}$ |
| not real / complex roots | 非实根 / 复根 | $\Delta<0$；本课不考虑 |
| general solution | 通解 | 含任意常数 $A,B$ |
| full solution | 全解 | 代入条件后的唯一解 |
| particular solution | 特解 | 同上（另一常用叫法） |
| arbitrary constants | 任意常数 | $A,B$；二阶方程必有两个 |
| initial conditions | 初始条件 | 同一点的函数值与导数值 |
| boundary conditions | 边界条件 | 两个不同点的函数值 |
| initial value problem (IVP) | 初值问题 | 由初始条件确定 |
| boundary value problem (BVP) | 边值问题 | 由上下边界条件确定 |
| simultaneous equations | 联立方程组 | 用来解出 $A,B$ |
| steady state | 稳态 | 变量不随时间改变，$\frac{\partial}{\partial t}=0$ |
| transient state | 暂态 | 变量仍随时间变化 |
| analytical solution | 解析解 | 得到的是公式 |
| numerical solution | 数值解 | 靠 solver 迭代逼近，落入 tolerance |
| solver | 求解器 | 程序中调用的数值积分工具 |
| tolerance | 容差 | 数值解可接受的误差范围 |
| Newton's second law of motion | 牛顿第二运动定律 | $F=ma=m\frac{d^2x}{dt^2}$ |
| kinematics | 运动学 | 位置、速度、加速度的关系 |
| acceleration | 加速度 | $\frac{d^2x}{dt^2}$ |
| normal force / contact force | 法向力 / 接触力 | $N=mg\cos\theta$ |
| frictional force | 摩擦力 | $\mu N$，$\mu$ 为摩擦系数 |
| coefficient of friction | 摩擦系数 | $\mu$ |
| Fourier's law | 傅里叶定律 | 热传导；$J\propto-\frac{dT}{dx}$ |
| Fourier's second law | 傅里叶第二定律 | $\frac{dT}{dt}=\alpha\frac{d^2T}{dx^2}$ |
| Fick's law | 菲克定律 | 质量扩散；$J=-D\frac{dC}{dx}$ |
| Fick's second law | 菲克第二定律 | $\frac{dC}{dt}=D\frac{d^2C}{dx^2}$ |
| heat transfer | 热传输 / 传热 | — |
| mass transfer | 质量传输 | — |
| flux | 通量 | 单位时间单位面积通过的量 |
| gradient | 梯度 | 空间中的变化率 |
| thermal diffusivity | 热扩散率 | $\alpha$；热扩散的速度 |
| thermal conductivity | 热导率 | $k$；材料导热能力 |
| density | 密度 | $\rho$ |
| specific heat capacity | 比热容 | $c_p$ |
| diffusion coefficient / diffusivity | 扩散系数 / 扩散率 | $D$ |
| Brownian motion | 布朗运动 | 随机热运动 |
| conservation of mass | 质量守恒 | Fick 第二定律的基础 |
| concentration | 浓度 | $C$ |
| particulate matter | 颗粒物 | 大气污染物 |
| geothermal gradient | 地温梯度 | $\frac{dT}{dx}$，本题 80 °C/km |
| damping | 阻尼 | 振幅随时间衰减 |
| oscillation | 振荡 | 弹簧、地震振动 |
| equilibrium | 平衡 | 系统最终状态 |
| stationary value | 驻点 | $f'(x)=0$ 处 |
| saddle point | 鞍点 | $f''(x)=0$ 时的可能情形 |
| point of inflection | 拐点 | 凹凸性改变处 |
| integration by substitution | 换元积分法 | 上周内容；链式法则的逆 |
| separation of variables | 分离变量法 | 解静水压方程用 |
| hydrostatic equation | 静水压方程 | 流体中压力随高度变化 |
| ideal gas equation | 理想气体方程 | 联系压力与温度 |
| tropopause | 对流层顶 | 温度突增处 |
| planetary boundary layer | 行星边界层 | 被"盖住"时导致城市污染累积 |
| partial differentiation | 偏微分 | 下周 (Week 10) 内容 |
| vectors | 向量 | 下周内容，处理三维方向性 |
