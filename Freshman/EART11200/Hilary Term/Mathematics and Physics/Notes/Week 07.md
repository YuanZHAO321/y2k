# Week 7 — 用牛顿定律做积分 (Integration using Newton's Laws)

> 课程：EART11200 The Natural Scientist's Toolkit — Mathematics and Physics
> 本周主题（教学周 26，2025-03-10）：Integration using Newton's Laws
> 材料来源：`Lecture/Week 7/Chapter7.md`、`Lecture/Week 7/lecture7.md`、`Lecture/Week 7/EART11200 - 10-Mar-transcript.md`、`Practical/Week 7/Exercises7.md`、`Practical/Week 7/Solutions7.md`、`Practical/Week 7/practical7_soln(1).md`、主手册 `main(1).md` 第 7 章（第 2373–2574 行）

---

## 一、本周主题

### 1. 本周在全课中的位置

| 周次（教学周） | 主题 | 与本周关系 |
|---|---|---|
| Week 1 (20) | Calculating Gradients | 梯度 $\frac{y_1-y_0}{x_1-x_0}$ ——本周推导 $F=m\frac{dv}{dt}$ 的起点 |
| Week 2 (21) | Introduction to Differentiation | 取极限 $\Delta t \to 0$ 得导数 |
| Week 5 (24) | Second Order Derivatives | $x \to v \to a$ 的二阶导数链条 |
| Week 6 (25) | Introduction to Integration | 定积分/不定积分、**separation of variables**、ODE |
| **Week 7 (26)** | **Integration using Newton's Laws** | **本周：把物理定律写成 ODE，再积分解出运动** |
| Week 8 (27) | Integration by Substitution | 下周积分技巧变难 |
| Week 9 (28) | Integrating Second Order ODEs | 二阶 ODE |
| Week 10 (29) | Vectors and Partial Differentiation | 多变量 |

课程整体脉络：**Week 1–5 微分 → Week 6–10 积分与进阶 → Week 11–12 复习**。本周是积分的**第一个大型物理应用**，也是第一次让学生「自己造微分方程」而不是拿到现成的方程去解。

### 2. 本周的核心逻辑（讲师原话概括）

Transcript 里老师反复强调这是一个**固定流程 (a process)**，不是一堆零散题目：

> "you pick your differential equation, you work out the forces that are acting on an object, and then you build a differential equation which you'll use separation of variables for."

即三步走：

1. **选 ODE 形式** — 根据题目问的是「速度 vs 时间」还是「速度 vs 距离」，从三种牛顿第二定律写法中挑一个；
2. **算合力 (net force)** — 沿运动方向的力相加，减去反方向的力；
3. **分离变量 + 定积分** — 用初始条件 (initial condition) 定积分限，解出结果。

老师还特别说明本周**数学难度不增加**：

> "largely we're not going to do too much more difficult than this separation of variables technique this week, but this week we're going to learn some more physical, how to integrate through physical laws."

### 3. 官方 Intended Learning Outcomes（lecture7 与 practical 均列出）

1. 理解并描述 **Newton's Laws of Motion**，解释物理系统中力 (force)、质量 (mass)、加速度 (acceleration) 的关系；
2. 应用 **Newton's Second Law** 建立描述物体运动的**常微分方程 (ODE)**；
3. 用**积分 (integration)** 求解这些 ODE，预测真实世界问题中的物理行为。

### 4. 上周（Week 6）必须记牢的前置内容

Transcript 用了将近 1/4 篇幅复习 Week 6，说明这些是本周的工具箱：

**基本积分表（考试会考，lecture7 slide 3–4）：**

| 导数 $\frac{dy}{dx}$ | 积分 $y$ |
|---|---|
| $0$ | $d$ |
| constant | $\text{constant}\times x + d$ |
| $x$ | $\dfrac{x^2}{2}+d$ |
| $x^n$ | $\dfrac{x^{n+1}}{n+1}+d$ |
| $e^x$ | $e^x+d$ |
| $ke^{kx}$ | $e^{kx}+d$ |
| $\dfrac{1}{x}$ | $\ln(x)+d$ |
| $\cos(x)$ | $\sin(x)+d$ |
| $\sin(x)$ | $-\cos(x)+d$ |

（老师提示：积分 $x^n$ 时「**raise the power by one and divide by the new power**」；$\sin$ 积分带负号是最常错的一行。）

**不定积分 (indefinite integration)**：无积分限，**必须加常数 $d$**。老师的理由说得很清楚：

> "that constant when we differentiate it, it differentiates to zero, so if you're only given this left hand side, which is the differential equation, you do not know if there was a constant there in the first place."

$$\int 3x^2\,dx = x^3 + d$$

**定积分 (definite integration)**：有上下限，算的是**曲线下面积 (area under the curve)**，用「上限值减下限值」：

$$\int_0^1 3x^2\,dx = \left[x^3\right]_0^1 = 1^3-0^3 = 1$$

物理意义（老师的比喻）：若 $3x^2$ 是水注入水箱的**速率**，则该定积分给出 $t=0$ 到 $t=1$ 之间**注入的水量**。

**分离变量法 (separation of variables)** — 放射性衰变范例：

$$\frac{dN}{dt}=-\lambda N \;\Longrightarrow\; \frac{1}{N}dN = -\lambda\,dt \;\Longrightarrow\; \int\frac{1}{N}dN=\int-\lambda\,dt$$
$$\ln N = -\lambda t + c \;\Longrightarrow\; N = N_0 e^{-\lambda t}$$

本周所有题目都靠这一招。

---

## 二、核心概念

### 2.1 牛顿三定律 (Newton's three laws of motion)

**历史背景**（Chapter7 §7.2 / transcript）：
- 20 世纪以前，人类对物理世界的理解完全建立在**古典力学 (classical mechanics)**，更具体说是**牛顿物理 (Newtonian Physics)** 上。
- 这套框架源自「**科学革命 (Scientific Revolution)**」：1543 年 **Copernicus** 提出日心说 (heliocentric model)，接着 **Galileo**、**Kepler**、**Descartes** 共同推翻了亚里士多德世界观。
- 三定律首次发表于 1687 年的 **《Philosophiae Naturalis Principia Mathematica》**（简称 **Principia**）。
- 牛顿提出三定律的**原始动机**：解释**行星轨道为什么是椭圆 (ellipses) 而不是圆 (circles)**。
- 老师补充：牛顿物理**至今仍是理论与实验物理的活跃领域**（"still an active area of theoretical and experimental physics"）。

**三定律内容：**

**(1) 惯性定律 (Law of Inertia)**
> 静止的物体，或以恒定速率沿直线运动的物体，将保持该状态，除非受到外力作用。

老师的例子：太空中飞行的彗星会一直保持恒速；这把椅子静止不动，除非我推它。抛出的球之所以不沿直线飞下去，是因为有**重力**把它拉向地面，还有**风阻 (wind resistance)** 让它减速。

**(2) 力与动量定律 (Law of Force and Momentum)**
> 物体动量 (momentum) 的变化率与所施加的力成正比，且变化方向与力的方向相同。

这是本周唯一真正使用的定律。

**(3) 作用与反作用定律 (Law of Action and Reaction)**
> 两物体相互作用时，彼此施加的力大小相等、方向相反。

Chapter7 用它回答了一个关键疑问：**为什么放在斜面上的物体不会陷进斜面里？** 因为斜面对物体施加了等大反向的力（**normal force 法向力**）。手册诚实地说明，实际情况还涉及物体与表面的分子力，但这些定律已足以解释我们观测到的运动。老师还用第三定律解释行星轨道：太阳与地球互相施力，"largely holding each other in some sort of stationary way"。

### 2.2 牛顿第二定律的三种 ODE 形式（★本周最重要的一页）

基本形式：

$$\boxed{F = ma}$$

- $F$：作用在物体上的**净力 (net force)**，单位 N (牛顿) $=$ kg·m·s$^{-2}$
- $m$：**质量 (mass)**，单位 kg
- $a$：**加速度 (acceleration)**，单位 m·s$^{-2}$

回忆 Week 5 的微分链条（位移 → 速度 → 加速度）：

$$v = \frac{dx}{dt}, \qquad a = \frac{dv}{dt} = \frac{d^2x}{dt^2}$$

因此牛顿第二定律可以写成**三个等价的 ODE**（Exercises7 前言与 lecture7 slide 10）：

$$\boxed{\;\text{(i)}\;\; F = m\frac{dv}{dt} \qquad \text{(ii)}\;\; F = m\,v\frac{dv}{dx} \qquad \text{(iii)}\;\; F = m\frac{d^2x}{dt^2}\;}$$

> ⚠️ **编号约定**：`Solutions7.md` 中反复出现「use ODE (i)」「use ODE (ii)」，从题目内容反推可确定：**(i) = $m\,dv/dt$（速度对时间）**，**(ii) = $m\,v\,dv/dx$（速度对距离）**。写答案时最好写出方程本身而不是只写编号，避免歧义。

**第三种形式 $a = v\frac{dv}{dx}$ 的推导（用 chain rule）：**

$$a=\frac{dv}{dt} = \frac{dv}{dx}\cdot\frac{dx}{dt} = \frac{dv}{dx}\cdot v = v\frac{dv}{dx}$$

因为 $v=\frac{dx}{dt}$。手册 §7.3 里这句话被 PDF 转换搞乱了，正确读法就是上式。

**选哪一个？（老师明确当成考试提示给出）**

> "If I ask you to relate velocity with respect to distance, it's this equation. If I'm asking you to relate distance with respect to time, it's this equation, and if I'm asking you to relate velocity to time, use that equation."

| 题目问什么 | 已知/未知的配对 | 用哪个形式 |
|---|---|---|
| 「经过 $t$ 秒后速度多大？」 | $v \leftrightarrow t$ | (i) $F=m\dfrac{dv}{dt}$ |
| 「移动 $x$ 米后速度多大？」 | $v \leftrightarrow x$ | (ii) $F=m\,v\dfrac{dv}{dx}$ |
| 「经过 $t$ 秒走了多远？」 | $x \leftrightarrow t$ | (iii) $F=m\dfrac{d^2x}{dt^2}$，或先解 (i) 再积分一次 |

**看到「距离」就想 $v\,dv/dx$，看到「时间」就想 $dv/dt$** —— 这是本周最实用的一条判断规则。

### 2.3 为什么 $F = m\frac{dv}{dt}$ ？（飞机推导，从梯度到导数）

Chapter7 §7.3 与 lecture7 slide 11–12 给出的直觉推导：

设一架**质量恒定**为 $m$ 的飞机在大气中飞行，其动量 (momentum) $p = mv$ 只取决于速度。在两个时间点 $t_0, t_1$ 上速度分别为 $V_0, V_1$，则动量变化为 $m(V_1-V_0)$。

**力定义为动量对时间的变化率**：

$$F = \frac{m(V_1-V_0)}{t_1-t_0}$$

老师强调：**"This resembles the calculation of a gradient from Week 1!"** —— 这正是 Week 1 手算梯度、Week 2 前向/后向差分 (forward/backward method) 的同一个式子。

取极限 $t_1 - t_0 \to 0$（Week 2 的做法），差商变成导数：

$$F = m\frac{dv}{dt}, \qquad\text{即}\qquad a = \frac{dv}{dt}$$

> 老师的教学用意（原话）："I didn't just ask you to do it by hand to annoy you, I actually am showing you the maths and differential equations can actually be derived by looking at rates of change of a process."

### 2.4 合力的计算规则（★最容易失分的一步）

老师在两个例题里都用同一句话强调：

> "We add up all the forces in the direction of travel and minus the forces in the opposite direction."

$$\boxed{F_{\text{net}} = \sum F_{\text{沿运动方向}} - \sum F_{\text{逆运动方向}}}$$

操作顺序：
1. **先画图，标出运动方向 (direction of travel)**；
2. 把所有力按「与运动方向同向 / 反向 / 垂直」分类；
3. **垂直方向的分量（法向力）不进入运动方向的 ODE**（老师："the normal force is going to be a bit irrelevant to us here"）——但它可能通过摩擦力 $F_f = \mu F_1$ **间接**进入；
4. 把 $F_{\text{net}}$ 代入选好的 ODE 形式。

### 2.5 三个课本例题

#### Example 7.1：真空中自由下落 (Object Falling in a Vacuum)

**问题**：在真空中，能否证明砖块 (brick) 和羽毛 (feather) 在相同时间内下落相同距离？

**受力分析**：真空中无空气阻力 ⇒ $F_f = 0$；唯一的力是重力 $F_g = mg$，方向由物体中心指向地心（即运动方向）。$g = 9.8$ m·s$^{-2}$。

$$F = mg - 0 = mg$$

**第一步：建立并求解速度 ODE**（用形式 (i)）

$$mg = m\frac{dv}{dt} \;\xrightarrow{\text{约掉 } m}\; \frac{dv}{dt} = g$$

**质量 $m$ 被消掉了** —— 这是整个论证的关键。

分离变量：

$$dv = g\,dt$$

**不定积分版本**（transcript 的讲法）：

$$\int dv = \int g\,dt \;\Longrightarrow\; v = gt + c$$

**用初始条件定常数**：物体从静止开始，$t=0$ 时 $v=0$：

$$0 = g\cdot 0 + c \;\Longrightarrow\; c = 0$$

$$\boxed{v = gt}$$

**定积分版本**（等价，推荐考试用）：

$$\int_0^v dv' = \int_0^t g\,dt' \;\Longrightarrow\; \left[v'\right]_0^v = \left[gt'\right]_0^t \;\Longrightarrow\; v - 0 = gt - 0 \;\Longrightarrow\; v = gt$$

**结论 1**：真空中任何物体的速度**随时间线性增加**，与质量无关 ⇒ 砖块和羽毛速度相同。

**第二步：再积分一次得距离**（$v = \frac{dx}{dt}$）

$$\frac{dx}{dt} = gt \;\Longrightarrow\; dx = gt\,dt$$

用初始条件 $t=0$ 时 $x=0$：

$$\int_0^x dx' = \int_0^t g t'\,dt' \;\Longrightarrow\; x = \left[\frac{g t'^2}{2}\right]_0^t = \frac{1}{2}gt^2$$

$$\boxed{x = \tfrac{1}{2}gt^2}$$

**结论 2**：真空中所有物体在相同时间内下落**相同距离**，且距离随时间**二次 (quadratically)** 增长，与质量无关。

**自洽性检查**（老师的话）：距离是二次 → 微分得线性（速度）→ 再微分得常数（加速度 $g$）。因为加速度恒定，所以这三层关系必然是「常数—线性—二次」。

#### Example 7.2：斜面上的物体 (Object on an Incline)

**受力分解**：重力 $F_g = mg$ 竖直向下。斜面倾角 $\theta$。用三角学 (trigonometry) 把 $mg$ 分解为：

$$\boxed{F_1 = mg\cos\theta \;\;(\text{法向力 normal force，垂直于斜面})}$$
$$\boxed{F_2 = mg\sin\theta \;\;(\text{沿斜面向下，即运动方向})}$$

> 记忆法（老师课上讲的）：以 $mg$ 为**斜边 (hypotenuse)**，$\theta$ 为夹角，沿斜面方向是**对边 (opposite)** ⇒ 用 $\sin$；垂直斜面方向是**邻边 (adjacent)** ⇒ 用 $\cos$。

**无摩擦假设**下，运动方向合力：

$$F = mg\sin\theta - 0 = mg\sin\theta$$

**建立并求解 ODE**（形式 (i)）：

$$m g\sin\theta = m\frac{dv}{dt} \;\Longrightarrow\; \frac{dv}{dt} = g\sin\theta$$

分离变量、代入 $t=0$ 时 $v=0$：

$$\int_0^v dv' = \int_0^t g\sin\theta\,dt' \;\Longrightarrow\; v = g\sin\theta\; t$$

$$\boxed{v = g t \sin\theta}$$

**结论**：斜面上物体速度**随时间线性增加**；增长速率**取决于倾角 $\theta$**（角度越大越快），但**与质量无关**。

特例检验：$\theta = 90°$ 时 $\sin\theta=1$，退化为自由落体 $v=gt$ ✓；$\theta=0°$ 时 $v=0$，水平面上不动 ✓。

#### Example 7.3：液滴受到的阻力 (Drag forces on a droplet)

这是本周唯一的**非常数加速度**情形，也是最贴近地球科学的应用（大气中的雨滴、火山灰、气溶胶沉降）。

**物理背景**（Chapter7 §7.3）：
- 物体在流体中运动会排开流体，受到随速度变化的**阻力 (drag force)**；
- 这些力包含**剪切黏性 (shear viscosity)**、**涡流黏性 (eddy viscosity)**、**滞止压力 (stagnation pressure)** 的贡献；
- 物理学常用**无量纲量 (dimensionless variables)** 判断这些机制何时切换 —— 流体力学中就是 **Reynolds number ($Re$)**。**本课不涵盖 Reynolds number**，只需知道它的存在与意义；
- Figure 7.2 展示了球体在不同 $Re$ 下周围的**流线 (streamlines)**（图源 cfdflowengineering.com）。

**给定的阻力公式**（手册与习题中该式是图片，从 Q7.5 的数值答案 14.66 m 反推可唯一确定系数为 $\tfrac12$）：

$$\boxed{F_{\text{drag}} = \tfrac{1}{2}\,\pi r^2 \rho\, v_{rel}^{2}}$$

- $r$：球半径 (m)
- $v_{rel}$：物体相对空气的速度 (m·s$^{-1}$)
- $\rho = 1.2$ kg·m$^{-3}$：空气密度 (density of air)
- 量纲检查：$[\text{m}^2]\cdot[\text{kg m}^{-3}]\cdot[\text{m}^2\text{s}^{-2}] = \text{kg·m·s}^{-2} = \text{N}$ ✓

**手册留的思考题**：如何把这个力与重力平衡？

$$mg = \tfrac12 \pi r^2 \rho v_t^2 \;\Longrightarrow\; v_t = \sqrt{\frac{2mg}{\pi r^2 \rho}}$$

此即**终端速度 (terminal velocity)**：当阻力与重力相等时净力为零，加速度为零，速度不再增加。这正是雨滴不会以极高速度砸到地面的原因。

### 2.6 量纲与单位在每一步如何变化（★本课特别要求）

以自由落体链条为例，追踪单位：

| 步骤 | 表达式 | 单位 | 说明 |
|---|---|---|---|
| 力 | $F = mg$ | kg $\times$ m·s$^{-2}$ = **N** | 牛顿 |
| ODE | $m\dfrac{dv}{dt}$ | kg $\times$ (m·s$^{-1}$)/s = **N** | 两边单位一致 ✓ |
| 约掉 $m$ | $\dfrac{dv}{dt}=g$ | **m·s$^{-2}$** | 变成加速度方程 |
| 积分 $dt$ 一次 | $v = gt$ | m·s$^{-2}$ $\times$ s = **m·s$^{-1}$** | **每积一次 $dt$，单位乘一个 s** |
| 再积分一次 | $x=\tfrac12 gt^2$ | m·s$^{-2}$ $\times$ s$^2$ = **m** | 又乘一个 s |

对形式 (ii)：$\int v\,dv$ 的单位是 (m·s$^{-1}$)$^2$ = m$^2$·s$^{-2}$，而 $\int a\,dx$ 的单位是 m·s$^{-2}$ $\times$ m = m$^2$·s$^{-2}$ ✓ —— 所以 $\frac{v^2}{2} = ax$ 两边同量纲，这是检查答案的好办法。

**积分常数的量纲**：$v = gt + c$ 中的 $c$ 必须是速度（m·s$^{-1}$）；$x = \frac12 gt^2 + c$ 中的 $c$ 必须是距离（m）。**积分常数永远与被解出的那个量同量纲**。

### 2.7 积分常数如何由初始条件确定（★本周核心技能）

有两种完全等价的写法，务必两种都会：

**写法 A：不定积分 + 代初始条件**

1. 分离变量后两边**不带限**积分，右边加一个常数 $c$；
2. 把**初始条件 (initial condition)**（例如 $t=0$ 时 $v=v_0$）代入求出 $c$；
3. 回代得到通解的具体形式。

例：$\dfrac{dv}{dt}=a \Rightarrow v = at + c$；代 $t=0, v=v_0$ 得 $c=v_0$；故 $v = v_0 + at$。

**写法 B：定积分 + 配对积分限（本课解答文件采用的写法）**

把初始条件直接写成积分下限、把目标状态写成上限，**左右两边的限必须成对配好**：

$$\int_{v_0}^{v_1} dv = \int_{0}^{t} a\,dt' \;\Longrightarrow\; v_1 - v_0 = at$$

老师在课上明确演示了「配对」这一动作：

> "at time equals zero, we traveled no distance... and at time equals t, we have traveled x distance."

即：**$t$ 的下限 0 ↔ $x$ 的下限 0；$t$ 的上限 $t$ ↔ $x$ 的上限 $x$**。左边变量的限与右边变量的限描述的是**同一个物理时刻**。

> 💡 考试建议：**写法 B 更安全**，因为它不会漏掉常数，也不会把常数代错；而且题目问「从 10 m/s 减到 0.01 m/s」这种情况时，直接把 10 和 0.01 当积分限即可（见 Q7.5）。

---

## 三、公式与图表

### 3.1 本周公式总表

| 名称 | 公式 | 适用条件 |
|---|---|---|
| 牛顿第二定律 | $F=ma$ | 质量恒定的经典力学（非相对论、非变质量） |
| ODE 形式 (i) | $F = m\dfrac{dv}{dt}$ | 求速度关于**时间**的关系 |
| ODE 形式 (ii) | $F = m\,v\dfrac{dv}{dx}$ | 求速度关于**距离**的关系 |
| ODE 形式 (iii) | $F = m\dfrac{d^2x}{dt^2}$ | 求位移关于**时间**的关系 |
| 链式法则关系 | $a = \dfrac{dv}{dt}=v\dfrac{dv}{dx}$ | 一维运动，$v\neq 0$ 时该换算有意义 |
| 合力 | $F_{\text{net}}=\sum F_{\text{同向}}-\sum F_{\text{反向}}$ | 一维（沿运动方向）分析 |
| 斜面分解 | $F_1 = mg\cos\theta$，$F_2 = mg\sin\theta$ | 刚性斜面，$\theta$ 为与水平面夹角 |
| 摩擦力 | $F_f = \mu F_1 = \mu mg\cos\theta$ | $\mu$ 为摩擦系数（题中 $\mu=0.1$）；方向**始终逆运动方向** |
| 球体阻力 | $F_{\text{drag}} = \tfrac12\pi r^2\rho v_{rel}^2$ | 空气中球体，本课给定的近似式 |
| 真空自由落体 | $v = gt$，$\;x=\tfrac12 gt^2$ | 从静止开始，无阻力 |
| 无摩擦斜面 | $v = gt\sin\theta$ | 从静止开始，无摩擦无阻力 |
| 终端速度 | $v_t=\sqrt{\dfrac{2mg}{\pi r^2\rho}}$ | 阻力与重力平衡时 |

### 3.2 恒定加速度三大公式（本周由 Q7.6–7.7 亲手推出）

**这三条务必背下来，但更要会现场推。**

$$\boxed{v_1 = v_0 + at} \qquad \boxed{v_1^2 = v_0^2 + 2ax} \qquad \boxed{x = v_0 t + \tfrac12 a t^2}$$

推导（第二式，来自 Q7.6）：

$$m\,v\frac{dv}{dx}=ma \;\Longrightarrow\; v\,dv = a\,dx$$
$$\int_{v_0}^{v_1} v\,dv = \int_0^x a\,dx' \;\Longrightarrow\; \left[\frac{v^2}{2}\right]_{v_0}^{v_1} = a x$$
$$\frac{v_1^2}{2}-\frac{v_0^2}{2}=ax \;\Longrightarrow\; v_1^2 = v_0^2 + 2ax$$

推导（第一式，来自 Q7.7）：

$$m\frac{dv}{dt}=ma \;\Longrightarrow\; \int_{v_0}^{v_1} dv = \int_0^t a\,dt' \;\Longrightarrow\; v_1 - v_0 = at$$

**⚠️ 适用条件：$a$ 必须是常数**（constant acceleration）。一旦有速度依赖的阻力（如 Q7.5），$a$ 不再恒定，**这三条公式立即失效**，必须回到 ODE 重新积分。

### 3.3 图表判读

**Figure 7.1（Chapter7）**：左右两幅受力示意图。
- **左**：物体竖直下落。只有一个向下的箭头 $F_g = mg$；反方向 $F_f = 0$（真空）。
- **右**：物体置于倾角 $\theta$ 的斜面上。竖直向下的 $mg$ 被分解成**垂直斜面**的 $F_1 = mg\cos\theta$ 与**沿斜面向下**的 $F_2 = mg\sin\theta$。读图要点：**$\theta$ 出现在重力矢量与法线之间**，所以沿坡分量配 $\sin$。

**Figure 7.2（Chapter7）**：球体在流体中运动时周围的**流线 (streamlines)**，随 Reynolds number 变化。读图要点：低 $Re$ 时流线平顺贴合球体（黏性主导）；高 $Re$ 时球体后方出现分离与涡旋（尾流），阻力机制从黏性主导转为压差主导。本课不要求定量处理，但要能说出「阻力形式随速度而变」这一结论。

**运动学曲线的定性形状（恒定加速度）**：
- $a$–$t$ 图：**水平直线**
- $v$–$t$ 图：**斜直线**，斜率 $=a$，截距 $=v_0$
- $x$–$t$ 图：**抛物线**（二次曲线）
- 三者关系：**微分向左（$x\to v\to a$），积分向右（$a\to v\to x$）**

---

## 四、课堂补充（transcript 独有内容）

以下内容只在录音转写中出现，讲义与手册里没有：

1. **本周定位的明确说明**：老师说"After this week, you've only got three weeks left, and then you've got three weeks for Easter"，并预告 **"Integration will get slightly harder as we go on from next week"** —— 本周是积分单元里数学最轻、物理最重的一周。

2. **「反向工程」的教学框架**：
   > "instead of going from the function to its derivative, we're going to give you something of a derivative and ask you to find out the original function by building differential equations."

3. **未来预告：初值与边值问题**。老师在讲不定积分常数时说：
   > "we'll come on to how do we figure out d later on... when we use initial value and boundary value problems, which we'll see in a couple of weeks."
   → 提示 Week 9（Integrating Second Order ODEs）会正式处理 **initial value problem / boundary value problem**。

4. **考试提示（原话）**：积分表 **"most of these will be in the exam"**，务必练熟到不用查表。

5. **选择 ODE 形式的考试暗示**：老师直接说 "this is probably going to be a little bit of a hint for some of the questions and some maybe exam questions"，随后给出「问速度对距离 → 用 $v\,dv/dx$」等对应表。这是本周**最像考点透题**的一段。

6. **汽车加速的直觉类比**：踩油门 = 施加的力；车越重加速越慢 —— 用来说明 $a = F/m$。

7. **真空中「没有反方向的力」的强调**：老师在黑板上反复画运动方向箭头，说明 $F = mg - 0$ 里那个 $-0$ 不是废话，而是提醒你**每次都要检查反方向有没有力**。

8. **对结果不含质量的反复强调**：
   > "the interesting thing here is that this equation does not contain mass, which means that any object falling in a vacuum fall at the same rate... If we had other external forces, then yes, perhaps mass would appear in this."
   → 关键洞察：**质量能被约掉，是因为所有的力都正比于 $m$**。一旦引入不正比于质量的力（如阻力 $\propto r^2 v^2$），质量就**不会**被约掉（对比 Q7.5，那里 $m$ 留在了答案里）。

9. **老师对后续变化的预告**（课末总结）：
   > "what happens if an object was already moving at time equals zero, what if it had travelled a certain distance at time equals zero... what happens if things are working in opposite directions"
   → 明确点出习题的三类变形：**非零初速度**、**非零初位置**、**反向力（摩擦/阻力）**。

10. **推导 $x=\frac12 gt^2$ 时老师用的是定积分**，边讲边配限：$t: 0\to t$ 配 $x: 0\to x$。这是理解「积分限配对」的最佳示范。

11. **一个口误提醒**：转写中出现 "force times mass equals force, force equals mass times acceleration" —— 前半句是口误，正确的是 $F = ma$。

---

## 五、Practical 要点

### 5.1 Practical 的目的

Practical 与 Lecture 共享同一组 ILO。它把课上「无摩擦」的理想斜面改成**有摩擦**的斜面，让学生亲手体会：**多一个反方向的力，ODE 只改一处，但解题流程完全不变**。两道题分别对应 ODE 形式 (i)（时间）与形式 (ii)（距离），正好把「选哪个 ODE」这一决策练一遍。

### 5.2 Practical 两道题（`practical7_soln(1).md`）

两题共同设定：$\theta = 30°$，初速度 $v_0 = 0$，$F = mg$，$F_1 = mg\cos\theta$，$F_2 = mg\sin\theta$，**摩擦力 $F_f = 0.1\,mg$（注意：是 $0.1mg$，不带 $\cos\theta$）**。

#### Practical Exercise 1：求 10 秒后的速度

**Step 1 合力**（沿运动方向为正）：

$$F = mg\sin\theta - 0.1mg = mg(\sin 30° - 0.1) = mg(0.5-0.1)=0.4mg$$

**Step 2 选 ODE**：问「10 秒后」⇒ 时间 ⇒ 形式 (i)

$$m\frac{dv}{dt} = mg(\sin\theta - 0.1) \;\xrightarrow{\text{约掉 }m}\; \frac{dv}{dt}=g(\sin\theta-0.1)$$

代入数值：$\frac{dv}{dt} = 9.8\times 0.4 = 3.92$ m·s$^{-2}$

**Step 3 分离变量 + 配限积分**（$t=0$ 时 $v=0$；$t=10$ 时 $v=v$）：

$$\int_0^v dv' = \int_0^{10} 3.92\,dt' \;\Longrightarrow\; v = 3.92\times 10 = 39.2$$

**答案：$v = 39.2$ m/s**（与解答一致）

#### Practical Exercise 2：求前进 10 米后的速度

**Step 1 合力**：同上，$F = 0.4mg$，加速度 $a = 3.92$ m·s$^{-2}$

**Step 2 选 ODE**：问「travels 10 metres」⇒ 距离 ⇒ 形式 (ii)（题目 HINT 也这么提示）

$$m v\frac{dv}{dx} = mg(\sin\theta-0.1) \;\Longrightarrow\; v\frac{dv}{dx}=3.92$$

**Step 3 分离变量 + 配限积分**（$x=0$ 时 $v=0$；$x=10$ 时 $v=v$）：

$$\int_0^v v'\,dv' = \int_0^{10} 3.92\,dx' \;\Longrightarrow\; \frac{v^2}{2}=39.2 \;\Longrightarrow\; v^2 = 78.4 \;\Longrightarrow\; v = 8.85\ \text{m/s}$$

> ⚠️ **原解答 slide 写的是 "8.5 m/s"，这与它自己给出的条件算不出来**。用 $F_f=0.1mg$ 得 $v=\sqrt{78.4}=8.85$ m/s；即使换成 $F_f=0.1mg\cos30°$ 也只得 $9.0$ m/s。**8.5 极可能是 8.9（四舍五入后的 8.85）的笔误**。考试时以自己的推导为准，并写出完整过程。

### 5.3 Exercises 7.1–7.9 完整解题梳理

题目来源 `Exercises7.md`，解答来源 `Solutions7.md`（题号以周版文件为准）。

**前置约定**（Exercises7 前言）：斜面上 $F_1 = mg\cos\theta$（法向力），$F_2 = mg\sin\theta$（沿坡）；三种 ODE 形式如 §2.2；$g=9.8$ m·s$^{-2}$。

> ⚠️ 注意：**Exercises 里的摩擦力是 $0.1\times$ 接触力（contact force）$=0.1\,mg\cos\theta$**，与 Practical 的 $0.1mg$ **不同**！题目原文说得很明确："friction is equal to 0.1 times the contact force (i.e. the force of gravity perpendicular to the slope)"。这两处不一致是本周最容易混淆的地方。

---

#### Question 7.1（无摩擦，求 10 m 后速度）
> 质量 $m$ 的物体静止于 $30°$ 斜面，无摩擦，沿坡下滑 10 m 后速度多大？

**思路**：问距离 ⇒ 用 ODE (ii)。

$$m\,v\frac{dv}{dx} = mg\sin 30° \;\Longrightarrow\; v\frac{dv}{dx}= 9.8\times 0.5 = 4.9$$

配限：$x: 0\to 10$，$v: 0\to v$（从静止出发）

$$\int_0^v v'\,dv' = \int_0^{10} 4.9\,dx' \;\Longrightarrow\; \frac{v^2}{2}=49 \;\Longrightarrow\; v^2 = 98$$

$$\boxed{v = \sqrt{98} = 9.9\ \text{m/s}}$$

---

#### Question 7.2（有摩擦，求 10 m 后速度）
> 同上，但摩擦力 $=0.1\times$ 接触力。

**思路**：合力多减一项 $0.1 F_1$。

$$F = mg\sin 30° - 0.1\,mg\cos 30°= m\,g(0.5 - 0.1\times 0.8660) = m\times 9.8\times 0.41340 = 4.0513\,m$$

用 ODE (ii)：

$$v\frac{dv}{dx}=4.0513 \;\Longrightarrow\; \int_0^v v'dv' = \int_0^{10}4.0513\,dx' \;\Longrightarrow\; \frac{v^2}{2}=40.513$$

$$v^2 = 81.03 \;\Longrightarrow\; \boxed{v = 9.0\ \text{m/s}}$$

**对比 Q7.1**：加了摩擦，速度从 9.9 降到 9.0 ✓（合理）

---

#### Question 7.3（有摩擦，求 10 s 后速度）
> 同 Q7.2 的受力，但问「10 秒后」。

**思路**：问时间 ⇒ 改用 ODE (i)。**受力分析完全不变，只换 ODE 形式** —— 这是本题的教学重点。

$$m\frac{dv}{dt}=mg(\sin 30° - 0.1\cos 30°) \;\Longrightarrow\; \frac{dv}{dt}=4.0513$$

配限：$t: 0\to 10$，$v: 0\to v$

$$\int_0^v dv' = \int_0^{10} 4.0513\,dt' \;\Longrightarrow\; v = 40.513$$

$$\boxed{v = 40.51\ \text{m/s}}$$

> 对比 Q7.2 与 Q7.3：**同一个物理场景，问「10 米后」得 9.0 m/s，问「10 秒后」得 40.51 m/s** —— 数字差得极远。这提醒你：**看清楚问的是距离还是时间，选错 ODE 会得到完全离谱的答案**。

---

#### Question 7.4（无摩擦，初速度 2 m/s，求 10 m 后速度）
> 与 Q7.1 相同，但初速度 $v_0 = 2$ m/s。题目 HINT 特别提醒：思考如何设积分限，"You can pair the starting speed and distance with the end speed and distance."

**思路**：这题就是练**积分限配对**。受力与 Q7.1 相同，只是 $v$ 的下限从 0 改成 2。

$$v\frac{dv}{dx}=g\sin 30° = 4.9$$

配限：$x: 0\to 10$ ↔ $v: 2\to v$

$$\int_2^v v'\,dv' = \int_0^{10}4.9\,dx' \;\Longrightarrow\; \frac{v^2}{2}-\frac{2^2}{2} = 49$$
$$\frac{v^2}{2} = 49 + 2 = 51 \;\Longrightarrow\; v^2 = 102$$

$$\boxed{v = \sqrt{102}=10.1\ \text{m/s}}$$

**注意**：不是 $9.9 + 2 = 11.9$！速度**不能线性相加**，因为进入的是 $v^2$。这正好验证 $v_1^2 = v_0^2 + 2ax$：$4 + 98 = 102$ ✓

---

#### Question 7.5（阻力，求减速到 0.01 m/s 前走了多远）★本周最难
> 球半径 $r=0.5$ m，质量 $m=1$ kg，在水平面上以 $v_0=10$ m/s 推出，风速为零。阻力 $F_{\text{drag}}=\tfrac12\pi r^2\rho v_{rel}^2$，$\rho=1.2$ kg·m$^{-3}$。问减速到 $0.01$ m/s 前走了多远？

**Step 1 受力**：水平运动，**运动方向上没有驱动力**（重力与法向力垂直于运动方向，互相抵消）。风速为零 ⇒ $v_{rel}=v$。唯一的力是阻力，**方向与运动方向相反**：

$$F = 0 - \tfrac12\pi r^2\rho v^2 = -\tfrac12\pi r^2\rho v^2$$

**Step 2 选 ODE**：问「走了多远」⇒ 形式 (ii)

$$m\,v\frac{dv}{dx} = -\tfrac12 \pi r^2 \rho v^2$$

**Step 3 分离变量** —— 注意这里 $m$ **不能约掉**（因为阻力不含 $m$），且两边可约掉一个 $v$：

$$m\frac{dv}{v} = -\tfrac12\pi r^2\rho\,dx$$

**Step 4 配限积分**：$v: 10\to 0.01$ ↔ $x: 0\to x$

$$m\int_{10}^{0.01}\frac{dv}{v} = -\tfrac12\pi r^2\rho\int_0^x dx'$$
$$m\left[\ln v\right]_{10}^{0.01} = -\tfrac12\pi r^2\rho\,x$$
$$m\ln\!\left(\frac{0.01}{10}\right) = -\tfrac12\pi r^2\rho\,x$$

**Step 5 代数值**：$\tfrac12\pi r^2\rho = \tfrac12\times\pi\times 0.5^2\times 1.2 = 0.4712$ kg·m$^{-1}$

$$1\times\ln(0.001) = -0.4712\,x \;\Longrightarrow\; -6.9078 = -0.4712\,x$$

$$\boxed{x = 14.66\ \text{m}}$$

**要点与洞察**：
- **本题是唯一 $m$ 不被约掉的题**。原因：阻力 $\propto r^2 v^2$，与质量无关；而斜面/自由落体的所有力都 $\propto m$。物理意义：**同样大小的球，越重越难被空气减速，滑得越远**。
- 解出的速度—距离关系其实是**指数衰减**：$v(x) = v_0 e^{-\frac{\pi r^2\rho}{2m}x}$。所以**球在数学上永远停不下来**（$v\to 0$ 需要 $x\to\infty$），题目才要求「减到 0.01 m/s」而不是「停止」。
- 量纲检查：$\tfrac12\pi r^2\rho$ 的单位是 kg·m$^{-1}$，$m/(\tfrac12\pi r^2\rho)$ 的单位是 m ✓，$\ln$ 内是无量纲比值 ✓
- 若改问「多长时间」，则用形式 (i)：$m\frac{dv}{dt}=-kv^2 \Rightarrow \frac{1}{v}=\frac{1}{v_0}+\frac{kt}{m}$。

---

#### Question 7.6（推导 $v^2 = v_0^2 + 2ax$）
> 推导初速 $v_0$、末速 $v_1$、起点 $x=0$、**恒定加速度**下的速度—距离关系。题目指定从 $F = m\,v\frac{dv}{dx}$ 出发。

$$m\,v\frac{dv}{dx}=ma \;\Longrightarrow\; v\,dv = a\,dx$$

配限：$v: v_0\to v_1$ ↔ $x: 0\to x$

$$\int_{v_0}^{v_1} v\,dv = \int_0^x a\,dx' \;\Longrightarrow\; \left[\frac{v^2}{2}\right]_{v_0}^{v_1}=a x$$
$$\frac{v_1^2 - v_0^2}{2}=ax$$

$$\boxed{v_1^2 = v_0^2 + 2ax}$$

---

#### Question 7.7（推导 $v_1 = v_0 + at$）
> 从 $F = m\frac{dv}{dt}$ 出发，恒定加速度。

$$m\frac{dv}{dt}=ma \;\Longrightarrow\; dv = a\,dt$$

配限：$v: v_0 \to v_1$ ↔ $t: 0\to t$

$$\int_{v_0}^{v_1}dv = \int_0^t a\,dt' \;\Longrightarrow\; v_1 - v_0 = at$$

$$\boxed{v_1 = v_0 + at}$$

---

#### Question 7.8（竖直上抛，最高多少米）
> 球以 $10$ m/s 竖直抛出，$a = -9.8$ m·s$^{-2}$（忽略空气阻力）。能升多高？

**关键物理洞察**：**最高点处速度为零**（$v_1 = 0$）。这是把「最高点」翻译成数学条件的唯一入口。

用 Q7.6 的结果，$v_0=10$，$v_1=0$，$a=-9.8$：

$$0^2 = 10^2 + 2(-9.8)x \;\Longrightarrow\; 0 = 100 - 19.6x \;\Longrightarrow\; x = \frac{100}{19.6}$$

$$\boxed{x = 5.1\ \text{m}}$$

**符号约定说明**：取**向上为正**，所以 $a=-9.8$（重力向下，与运动方向相反）。解出的 $x>0$，表示向上位移 5.1 m ✓

---

#### Question 7.9（竖直上抛，多久到最高点）
> 同上，问到达最高点所需时间。

用 Q7.7 的结果，$v_0=10$，$v_1=0$，$a=-9.8$：

$$0 = 10 + (-9.8)t \;\Longrightarrow\; t = \frac{10}{9.8}$$

$$\boxed{t = 1.02\ \text{s}}$$

> 注：`Solutions7.md` 此处写「use the general formula we developed in Question 7.8」，应为 **Question 7.7** 的笔误（7.8 本身也在引用 7.7）。

**交叉验证**：用 $x = v_0t+\frac12 at^2 = 10(1.0204)+\frac12(-9.8)(1.0204)^2 = 10.204 - 5.102 = 5.10$ m ✓ 与 Q7.8 一致。

### 5.4 解题技巧总结（考试用「五步法」）

1. **画受力图**，标出**运动方向**；
2. **写合力**：$F = \sum F_{\text{同向}} - \sum F_{\text{反向}}$；
3. **按题目问什么选 ODE 形式**：时间 → $m\frac{dv}{dt}$；距离 → $mv\frac{dv}{dx}$；
4. **约掉 $m$（若可以）** —— 先检查每一项力是否都含 $m$；
5. **分离变量，配对积分限，积分**，然后代数值并**写单位**。

**快速自检清单**：
- [ ] 答案的量纲对吗？（速度 m/s，距离 m，时间 s）
- [ ] 摩擦/阻力项的符号是负的吗？
- [ ] 有初速度时，$v$ 的积分下限改了吗？
- [ ] 加速度是常数吗？若否，不能用 $v^2=v_0^2+2ax$。
- [ ] 三角函数：沿坡是 $\sin$，法向是 $\cos$。
- [ ] 计算器是**度数模式 (degrees)** 吗？

---

## 六、易错点 / 重点难点

1. **选错 ODE 形式**（本周头号失分点）。同一场景问「10 米后」（9.0 m/s）与「10 秒后」（40.51 m/s）答案天差地别。**读题时先圈出「distance / metres」或「time / seconds」，再决定用哪个方程。**

2. **忘记 $a = v\frac{dv}{dx}$ 的来历**。它不是新公式，而是链式法则：$\frac{dv}{dt}=\frac{dv}{dx}\frac{dx}{dt}=v\frac{dv}{dx}$。理解了就不用死记。

3. **摩擦力用错法向力**。Exercises 用 $F_f = 0.1\,mg\cos\theta$（「0.1 倍接触力」），Practical 用 $F_f = 0.1\,mg$。**两份材料定义不同，考试务必读清题面文字**，不要凭记忆套。

4. **符号错误：忘了给反向力加负号**。摩擦力、阻力**永远与运动方向相反**，进合力时是**减**。写成加号会得到「摩擦让物体加速」的荒谬结果。

5. **盲目约掉质量 $m$**。只有当**所有力都正比于 $m$** 时才能约掉。Q7.5 的阻力 $\propto r^2v^2$ 与 $m$ 无关，$m$ 必须保留在答案里 —— 这正是「重的球滑得更远」的物理原因。

6. **积分限配对错误**。$v$ 的下限必须对应 $x$（或 $t$）的下限，描述**同一个物理时刻**。Q7.4 中，「$x=0$ 时 $v=2$」⇒ $\int_2^v v\,dv=\int_0^{10}a\,dx$。若误写成 $\int_0^v$，就丢掉了初速度。

7. **速度线性相加的错误**。Q7.4 的答案不是 $9.9+2=11.9$，而是 $\sqrt{2^2+98}=10.1$。因为进入方程的是 $v^2$ 不是 $v$。

8. **不定积分忘加常数 $d$**。老师专门强调：常数微分为零，所以从导数反推时你**不知道原来有没有常数**，必须加上再用初始条件确定。

9. **在非恒定加速度问题上套用 $v^2=v_0^2+2ax$**。Q7.5 里加速度随速度变化（$a\propto -v^2$），三大运动学公式**全部失效**，必须老实分离变量积分。

10. **忘记「最高点速度为零」这一物理翻译**。Q7.8/7.9 若不知道 $v_1=0$ 就无从下手。同类翻译还有：「静止出发」⇒ $v_0=0$；「终端速度」⇒ $a=0$。

11. **三角函数配错**（$\sin$ / $\cos$ 互换）。牢记：**沿坡下滑用 $\sin\theta$，压向斜面用 $\cos\theta$**。检验法：$\theta\to 90°$ 时应退化成自由落体（$\sin 90°=1$ ✓）。

12. **计算器弧度/角度模式**。题目给的是 $30°$，必须用度数模式，否则 $\sin(30)$ 会被算成 $-0.988$。

13. **积分 $\sin$ 时漏负号**：$\int\sin x\,dx = -\cos x + d$。

14. **物理上「停止」与数学上「$v\to 0$」的区别**。指数衰减意味着物体理论上永不停止，所以题目才设 0.01 m/s 的阈值。

15. **教材本身的两处笔误（已核对）**：
    - `practical7_soln(1).md` Exercise 2 的答案「8.5 m/s」与其自身条件不符，正确应为 **8.85 m/s**；
    - `Solutions7.md` Q7.9 说「use the general formula we developed in Question 7.8」，应为 **Question 7.7**。
    - 另外主手册题号与章节编号不自洽，**引用题号一律以周版 `Exercises7.md` / `Solutions7.md` 为准**。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| Newton's Laws of Motion | 牛顿运动定律 | 三条，出自 1687 年 *Principia* |
| Law of Inertia | 惯性定律 | 第一定律 |
| Law of Force and Momentum | 力与动量定律 | 第二定律，本周核心 |
| Law of Action and Reaction | 作用与反作用定律 | 第三定律 |
| classical mechanics | 古典力学 | 20 世纪前的物理框架 |
| Newtonian Physics | 牛顿物理 | 至今仍是活跃研究领域 |
| Scientific Revolution | 科学革命 | Copernicus、Galileo、Kepler、Descartes、Newton |
| *Principia* | 《自然哲学的数学原理》 | *Philosophiae Naturalis Principia Mathematica* (1687) |
| heliocentric model | 日心模型 | Copernicus, 1543 |
| force | 力 | $F$，单位 N |
| net force | 净力 / 合力 | 沿运动方向求和减去反向 |
| mass | 质量 | $m$，单位 kg |
| momentum | 动量 | $p = mv$，单位 kg·m·s$^{-1}$ |
| acceleration | 加速度 | $a$，单位 m·s$^{-2}$ |
| velocity | 速度 | $v = dx/dt$，单位 m·s$^{-1}$ |
| displacement / distance | 位移 / 距离 | $x$，单位 m |
| gravitational constant | 重力常数（此课语境） | $g = 9.8$ m·s$^{-2}$ |
| gravitational force | 重力 | $F_g = mg$ |
| normal force | 法向力 | $F_1 = mg\cos\theta$，垂直斜面 |
| contact force | 接触力 | 即法向力，习题中摩擦力以它为基准 |
| friction / frictional force | 摩擦力 | $F_f$，永远逆运动方向 |
| incline | 斜面 | 倾角 $\theta$ |
| direction of travel | 运动方向 | 定义合力正方向的基准 |
| drag force | 阻力 | $F_{\text{drag}}=\tfrac12\pi r^2\rho v_{rel}^2$ |
| terminal velocity | 终端速度 | 阻力与重力平衡时的恒定速度 |
| relative velocity | 相对速度 | $v_{rel}$，物体相对流体 |
| density of air | 空气密度 | $\rho = 1.2$ kg·m$^{-3}$ |
| shear viscosity | 剪切黏性 | 阻力的贡献之一 |
| eddy viscosity | 涡流黏性 | 阻力的贡献之一 |
| stagnation pressure | 滞止压力 | 阻力的贡献之一 |
| Reynolds number ($Re$) | 雷诺数 | 无量纲数，判别流动机制；**本课不考** |
| dimensionless variable | 无量纲变量 | 如 $Re$ |
| streamlines | 流线 | Figure 7.2 |
| ordinary differential equation (ODE) | 常微分方程 | 本周核心工具 |
| separation of variables | 分离变量法 | Week 6 学的解 ODE 方法 |
| definite integration | 定积分 | 带上下限，算曲线下面积 |
| indefinite integration | 不定积分 | 不带限，必须加常数 $d$ |
| constant of integration | 积分常数 | $c$ 或 $d$，由初始条件确定 |
| initial condition | 初始条件 | 如 $t=0$ 时 $v=0$ |
| initial value problem | 初值问题 | 老师预告 Week 9 会讲 |
| boundary value problem | 边值问题 | 老师预告 Week 9 会讲 |
| limits of integration | 积分限 | 必须左右配对 |
| constant acceleration | 恒定加速度 | 三大运动学公式的适用前提 |
| equations of motion | 运动学方程 | $v=v_0+at$ 等 |
| chain rule | 链式法则 | 用来导出 $a=v\,dv/dx$ |
| vacuum | 真空 | 无阻力理想情形 |
| air resistance / wind resistance | 空气阻力 / 风阻 | |
| trigonometry | 三角学 | 用于斜面力分解 |
| hypotenuse | 斜边 | 分解 $mg$ 时 $mg$ 本身 |
| opposite / adjacent | 对边 / 邻边 | 决定用 $\sin$ 还是 $\cos$ |
| gradient | 梯度 / 斜率 | Week 1 内容，本周用来推导导数 |
| rate of change | 变化率 | |
| second-order derivative | 二阶导数 | $d^2x/dt^2 = a$ |
| quadratic / linear | 二次 / 线性 | $x\propto t^2$，$v\propto t$ |
| exponential decay | 指数衰减 | Q7.5 中 $v(x)=v_0e^{-kx/m}$ |
