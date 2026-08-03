# Week 5 — 对数与指数 (Logarithms & Exponentials)：里氏震级与大气科学应用

> 材料来源：
> - Lecture：`EART11200_M&P_W5_1.md`（对数与常数 e）、`EART11200_M&P_W5_2.md`（里氏震级）、`EART11200_M&P_W5_3.md`（大气科学 2）、`EART11200 - 25-Oct-transcript.md`（讲座录音转写）
> - Practical：`eart11200_week05_answers.md`（Chapter 3 答案与提示）、`EART11200 - 25-Oct-transcript.md`（practical 录音转写，主要是考试须知）
>
> ⚠️ 说明：本周三份 slides 的 PDF→md 转换把**公式图片全部丢失了**，只剩标题和文字。下文中的公式是根据 transcript 的口述、answers 文件的提示（如「subtract 1.4 and 0.16√D from both sides」「with D = 100 km this results in A ≈ 20,000 mm」）以及标准教科书形式**反推重建**的，并已用数值代回验算，与答案文件给出的数字完全吻合。凡是重建的地方都会标注。

---

## 一、本周主题

本周是 Introductory Maths for Natural Scientists 五周课程的**最后一周**，主题是**对数 (logarithms) 与指数函数 (exponentials)**，以及它们在地球与环境科学中的两大典型应用：**里氏震级 (Richter scale)** 和**大气科学**（云滴冻结的随机过程、静力方程、位温守恒与成云高度）。

在全课 5 周中的位置：
- Week 1 打下**幂与指数 (powers and exponents)**、科学计数法、单位的基础；
- Week 2 做了**净初级生产力 (net primary productivity, NPP)** 等实际问题，当时有几道题被标注「this uses logs — 先跳过」；
- Week 3–4 覆盖了代数变形、三角学 (trigonometry) 等；
- **Week 5 把 Week 1 的指数「反过来」**变成对数，于是 Week 2 那些当时做不了的题现在能补上了（讲座里老师就现场补做了「人类什么时候会吃光全部净初级生产力」这道题）。

课程节奏上，本周同时是**总结周**：下周三上午 11:00–13:00 有本课程第一次 summative maths test（详见第五节）。

---

## 二、核心概念

### 2.1 什么是对数 (logarithm)：它就是「指数」

老师在 transcript 里反复强调的一句话：**对数就是在问「我需要几次方？」(what exponent do I need?)**

举例：$3^? = 9$。答案是 2，因为 $3 \times 3 = 9$。写成对数就是

$$\log_3 9 = 2$$

读作「以 3 为底 9 的对数等于 2」。所以：

> **对数是指数 (the logarithm of something IS the exponent)。**

一般形式（slides 上标注为 "Key point"，老师说这是本节最重要的东西）：

$$y = a^x \quad \Longleftrightarrow \quad \log_a y = x$$

这两个式子是**完全等价的两种写法**（equivalent statements），一个是「指数形式 (exponential form)」，一个是「对数形式 (logarithmic form)」。学会在两者之间来回翻译，是本周所有题目的关键动作。

其中：
- $a$ 是**底数 (base)**，
- $x$ 是**指数 / 幂 (exponent / index / power)**，
- $y$ 是**真数 (argument)**。

**与 Week 1 的联系**：老师明确要求「go back and remind yourselves what we did in week one」。Week 1 讲的是「同底数相乘、指数相加」$a^m \cdot a^n = a^{m+n}$；本周的对数定律其实就是那些指数律的镜像。

### 2.2 常用的两个底：10 和 e

任何正数（≠1）都可以当底，但实际上只有两个常用：

**(1) 底 10 —— 常用对数 (common logarithm)**
记作 $\log_{10} x$，或在不引起歧义时直接写 $\log x$。

老师的理由：「Our counting system works in base 10. Our units work in base 10. **So unless you're told otherwise, the base is usually 10.**」——**没有特别说明时默认底是 10**。里氏震级、pH、分贝都是底 10。

**(2) 底 e —— 自然对数 (natural logarithm)**
$e = 2.71828\ldots$，称为**欧拉数 (Euler's number)**。记作 $\log_e x$，但几乎总是简写成 $\ln x$（transcript 里老师提醒：计算器上可能显示成 "Ln"，也可能看起来像大写 I 加 n）。

老师对 e 的评价（slides 原文 + 口述）：
> "The constant $e = 2.71\ldots$ is a very important constant, which describes many natural processes. So much so it is given its own inverse on a calculator — the natural logarithm."

- e 描述了**大量自然过程**：「It's often a natural way that things decay or increase」——自然界的衰减 (decay) 和增长 (growth) 天然就是以 e 为底的指数形式。
- 在大气科学里到处都是（本周的云滴冻结、静力方程都是）。
- 因为太常用，计算器给了它**专门的按键**：`log`（底 10）、`ln`（底 e）、`e^x`。有些计算器还能自选底数。

**老师特别强调的易错点**：
> "Important point when using your calculators, **choose the right log**. Because if you choose the wrong one — if you use natural log when your problem requires log base 10, or vice versa — then you will get the wrong answer. **They are not the same, the base is different.**"

### 2.3 对数的三条定律 (laws of logarithms)

**前提条件（老师说了至少三遍）：所有项必须是同一个底！**
> "This holds provided that these are both the same base... **You've got to have the same base number.** ... The base has to be the same for all terms."

对照 Week 1 的指数律：$10^A \times 10^B = 10^{A+B}$ 成立，但 $10^A \times 5^B \ne 10^{A+B}$——底不同就不能合并。对数同理。

**第一定律（乘法 → 加法）**
$$\log_a A + \log_a B = \log_a (AB)$$

**第二定律（除法 → 减法）**
$$\log_a A - \log_a B = \log_a\!\left(\frac{A}{B}\right)$$

**第三定律（幂 → 乘法）**
$$n\log_a A = \log_a (A^n)$$

老师给的直观解释（transcript 原话）：
> "If we have lots of log A's — that's just $\log A + \log A + \log A + \log A + \log A$ — adding this up, we're just adding lots of A's. So it'd be $A \times A \times A \times A \times A$, which is just $A^n$."

即：由第一定律反复应用，$\underbrace{\log A + \log A + \cdots + \log A}_{n\ \text{个}} = \log(\underbrace{A \times A \times \cdots \times A}_{n\ \text{个}}) = \log A^n$。

**第三定律是本周最有用的一条**：它能把未知数从指数位置「拉下来」，这正是所有「增长/衰减要多久」类题目的解法核心。

关于证明：有同学问要不要看证明，老师说「It can be proved, but as far as you're concerned, **you just need to know these properties of logs**」，并建议**用你熟悉的简单数字自己代进去玩一玩**（"play about with moving around the logs and you'll soon become very familiar with it"），这样最快建立直觉。

### 2.4 常用推论

由定义可直接推出（slides W5_1 结尾部分）：

$$\ln(e^x) = x \qquad \text{以及} \qquad e^{\ln x} = x$$

slides 上的具体数值例子：
$$e^2 = 7.389\ldots \quad \Rightarrow \quad \ln(7.389\ldots) = \ln(e^2) = 2$$

老师说这是「a very important feature of the natural logarithm」，凡是处理以 e 为底的指数增长/衰减，都靠这条把指数上的东西剥下来。

同理对底 10：$\log_{10}(10^x) = x$，$10^{\log_{10} x} = x$。

其他有用的值：
$$\log_a 1 = 0 \quad(\text{因为 } a^0 = 1), \qquad \log_a a = 1 \quad(\text{因为 } a^1 = a)$$

**换底公式 (change of base)**（老师在讲座末尾提到的「另一种做法」）：
$$\log_b x = \frac{\log_a x}{\log_a b}$$

有同学建议用 $\log_{1.02}$ 直接解 $1.02^n = 22.8$，老师回答：「That's absolutely right, **so long as you can have a log to the base 1.02**, which you probably can on clever calculators. I should give you about the same answer.」——即，如果计算器支持任意底就能直接算；否则用换底公式或第三定律。

### 2.5 地震：里氏震级 (Richter scale) 与麦卡利烈度 (Mercalli scale)

**为什么地震要用对数**：地震释放的能量跨越许多个数量级 (orders of magnitude)，直接用线性刻度无法在一张表上表示，所以用底 10 的对数刻度压缩。

**里氏震级** 测量的是**振幅 (amplitude)**，是**定量的 (quantitative)**；它定义在**震中 (epicentre)**，因此**与观测者到震中的距离无关**——answers 文件原话：「The magnitude of an Earthquake is independent of distance from the Earthquake as it refers to the magnitude of the Earthquake at the epicentre.」这一点是本周 practical 第一题的全部立意：同一次地震，你在 100 km 和 1000 km 外测到的**振幅 A 天差地别**，但**震级 $m_l$ 必须一样**，办法就是用一个随距离变化的参考振幅 $A_0(D)$ 把距离效应扣掉。

**麦卡利烈度 (Mercalli scale)** 则测量**破坏性/影响 (destructiveness or effect)**，是**定性的 (qualitative)** ——它描述「房子塌了没有、人站不站得稳」，因此**同一次地震在不同地点的 Mercalli 值不同**。

**能量 (energy released / intensity)** 与震级的关系（slides W5_2 原文给出）：
$$\log_{10} E = 11.8 + 1.5M$$
其中 $M$ 是里氏震级。（该经典形式中 $E$ 的单位是尔格 erg；$1\ \text{erg} = 10^{-7}\ \text{J}$。）

含义：震级每增加 1 级，$\log_{10}E$ 增加 1.5，即能量变为 $10^{1.5} \approx 31.6$ 倍；震级增加 2 级，能量变为 $10^3 = 1000$ 倍。

参考阅读：*Portrait of a Planet* p.339（slides 上反复标注，讲的是地震波 seismic waves 和里氏震级的背景）。

### 2.6 大气科学 (Atmospheric Science)

**(a) 云滴冻结是随机过程 (stochastic process)**

answers 文件原话：「The freezing of cloud droplets in the atmosphere is **a stochastic process and obeys a law that is similar to radioactive decay**.」——单个云滴什么时候冻不可预测，但一大群云滴的**统计行为**服从指数衰减，形式与放射性衰变 (radioactive decay) 完全相同：

$$N = N_0\,e^{-Jt}$$

- $N$：$t$ 时刻**尚未冻结**的液滴数 (number of unfrozen droplets)
- $N_0$：初始未冻结液滴数
- $J$：成核速率 (nucleation rate)，单位 s$^{-1}$，题中取 $J = 0.1\ \text{s}^{-1}$（0 ℃ 以下）
- $t$：时间 (s)

**(b) 静力方程 (hydrostatic equation)：气压随高度指数衰减**

slides W5_3 原文：「The pressure reduces with altitude according to an exponential law, known as the hydrostatic equation」

$$P = P_0\, e^{-z/H}$$

- $P$：高度 $z$ 处的气压 (Pa)
- $P_0$：起始（参考）高度处的气压 (Pa)
- $z$：高度 (m)
- $H = 8000\ \text{m}$：大气的**标高 (scale height)** ——每上升 $H$，气压降到原来的 $1/e \approx 37\%$

**(c) 上升气块与守恒量：位温 (potential temperature) θ**

slides W5_3 原文：「But for rising parcels of air, temperature and pressure are related by **a conservation law**…」以及「By considering conservation laws, atmospheric scientists have shown that… **So if you calculate the initial value of θ it will stay the same even when pressure changes**」。

这就是**位温 (potential temperature)**，由 Poisson 方程给出（⚠️ slides 上的公式图片丢失，此处为标准形式重建）：

$$\theta = T\left(\frac{P_{\text{ref}}}{P}\right)^{R/c_p}, \qquad \frac{R}{c_p} = \kappa \approx 0.286,\quad P_{\text{ref}} = 10^5\ \text{Pa}\ (1000\ \text{hPa})$$

- $\theta$：位温 (K)，「把这块空气绝热地带到 1000 hPa 时它会有的温度」
- $T$：气块当前温度 (K)
- $P$：气块当前气压 (Pa)
- $R$：干空气气体常数 ($287\ \text{J kg}^{-1}\text{K}^{-1}$)
- $c_p$：定压比热容 ($1004\ \text{J kg}^{-1}\text{K}^{-1}$)

**物理图像**（slides 上的两个盒子动画 + 老师的两个引导问题）：

slides 画了两个装气体的盒子，都是高温（分子跑得很快），第二个盒子里分子被挤进更小的空间（**气压更高**）。然后让第二个盒子的气体膨胀：

> "Gas 'pushes' against air around it and gas molecules slow down."

slides 抛出两个思考题：
1. **用分子动理论 (Kinetic Theory)，分子的速度（动能）如何影响温度？** → 温度就是分子平均平动动能的量度，分子越快越热。
2. **你知道描述能量与功之间关系的定律吗？** → 热力学第一定律 (First Law of Thermodynamics)。气块膨胀时**对外做功 (does work on the surroundings)**；若过程是**绝热的 (adiabatic)**（无热量交换），做功的能量只能来自气块自身的内能，于是分子减速、**温度下降**。

这就是**绝热冷却 (adiabatic cooling)**：气块上升 → 环境气压下降 → 气块膨胀 → 对外做功 → 温度下降。而 $\theta$ 在这个过程中**守恒**（不变）。

**(d) 成云：暖空气能容纳更多水汽 + 云凝结核 (CCN)**

slides 标题：「**Warm air holds more water vapour than cold air**」。配图讲的是夜间降温：白天空气里的水汽量固定，夜里冷却后空气「装不下」了，一部分水必须以液态存在（露、雾）。

所以气块上升 → 绝热冷却 → 到某一高度水汽达到饱和 → **凝结 (condensation)** → 成云。

但**光冷却还不够**，还需要**云凝结核 (Cloud Condensation Nuclei, CCN)**：

> "As the air cools during the expansion, water vapour eventually condenses onto **Cloud Condensation Nuclei** (a type of small particle suspended in air) and forms a cloud. **Some small particles do not act as Cloud Condensation Nuclei.**"

即：空气中的小颗粒并非都能当 CCN（要看它的吸湿性 hygroscopicity、大小等）。

**(e) CCN 数量 → 云的反照率 (albedo)**

slides 原文：「The number of cloud condensation nuclei is important to **how much sun-light is reflected**」。配图是蓝底上的白点（水滴）：**同样多的水**，如果分成**更多更小**的液滴，总表面积更大，散射阳光更强，**云看起来更白**。这就是气溶胶间接效应 / Twomey 效应。

---

## 三、公式与图表

### 3.1 对数与指数公式总表

| 公式 | 符号含义 | 备注 |
|---|---|---|
| $y = a^x \iff \log_a y = x$ | $a$ 底数，$x$ 指数，$y$ 真数 | 定义；两种等价写法 |
| $\log_a A + \log_a B = \log_a(AB)$ | 同底 | 第一定律 |
| $\log_a A - \log_a B = \log_a(A/B)$ | 同底 | 第二定律 |
| $n\log_a A = \log_a(A^n)$ | 同底 | 第三定律；**把指数拉下来** |
| $\ln(e^x) = x$ | $e = 2.71828\ldots$ | 自然对数的核心性质 |
| $e^{\ln x} = x$ | $x > 0$ | 同上，反向 |
| $\log_a 1 = 0$，$\log_a a = 1$ | — | 特殊值 |
| $\log_b x = \dfrac{\log_a x}{\log_a b}$ | — | 换底公式 |

### 3.2 里氏震级公式（⚠️ 由 answers 提示反推重建，已验算）

**局地震级 (local magnitude)：**
$$m_l = \log_{10} A - \log_{10} A_0$$

- $m_l$：里氏局地震级（无量纲）
- $A$：**实测**地震波振幅 (mm)
- $A_0$：在距离 $D$ 处「刚好能被探测到」的参考波振幅 (mm)

**参考振幅随距离的经验关系：**
$$-\log_{10} A_0 = 1.4 + 0.16\sqrt{D}$$

- $D$：到震中的距离 (km)

代入后得到实用形式：
$$\boxed{m_l = \log_{10} A + 1.4 + 0.16\sqrt{D}}$$

> 验算：$D=100$，$m_l=7.3$ → $\log_{10}A = 7.3 - 1.4 - 1.6 = 4.3$ → $A = 10^{4.3} \approx 2.0\times10^4$ mm，与 answers 的「$A \approx 20{,}000$ mm」吻合 ✓
> $D=1000$ → $\log_{10}A = 7.3 - 1.4 - 5.06 = 0.84$ → $A = 6.9$ mm，与 answers 吻合 ✓

**能量公式（slides 原文）：**
$$\log_{10} E = 11.8 + 1.5M$$
$E$ 为释放能量（经典形式中单位为 erg），$M$ 为里氏震级。

### 3.3 大气科学公式

**云滴冻结（类放射性衰变）：**
$$N = N_0 e^{-Jt} \quad\Longrightarrow\quad t = -\frac{1}{J}\ln\!\left(\frac{N}{N_0}\right) = \frac{1}{J}\ln\!\left(\frac{N_0}{N}\right)$$

**静力方程：**
$$P = P_0 e^{-z/H} \quad\Longrightarrow\quad z = -H\ln\!\left(\frac{P}{P_0}\right) = H\ln\!\left(\frac{P_0}{P}\right), \qquad H = 8000\ \text{m}$$

**位温（守恒量）：**
$$\theta = T\left(\frac{P_{\text{ref}}}{P}\right)^{\kappa} \quad\Longrightarrow\quad P = P_{\text{ref}}\left(\frac{T}{\theta}\right)^{1/\kappa}, \qquad \kappa = R/c_p \approx 0.286$$

### 3.4 关键图表要点

**(1) 卫星云图上的「直线」(slides W5_3 最后一页，讲座末尾现场讨论)**

图：从太空俯视的海洋层云时间序列（海是蓝的，云是白的），云面上有几道**明显更亮的细直线**，随时间缓慢扩散、褪去。

- 亮度 = 云反射阳光的强度；**越亮通常意味着云越高或越冷**，也反映**液滴的数量和大小**（液滴越多越小 → 越白）。
- 那些直线是**飞机航迹云 (contrails / ship-track 类特征)**：飞机在云顶附近穿过，尾气注入大量**额外的凝结核**，使该处水汽凝结成**数量更多、尺寸更小**的液滴 → 那条线特别亮 → 随时间扩散消散。
- 同样的机制在晴空（干净大气）中就形成我们抬头看到的白色**凝结尾迹**。

**(2) 蓝底白点图（液滴数量 vs 反照率）**
同样的含水量，分成越多越小的液滴，白色越强 → 云反照率越高 → 反射更多太阳辐射。

**(3) 两个气体盒子（绝热膨胀冷却）**
两盒同温高温气体，第二盒被压缩（高压）；放开让其膨胀 → 气体对周围空气做功 → 分子减速 → 温度下降。

**(4) 夜间降温成露图**
空气中水汽量给定；温度高时水**全部以气态存在**；冷却后超过饱和，一部分**以液态出现**。

**(5) 查尔斯顿地震示意图 (slides W5_2)**
以震中为心的两个同心圆，半径分别标 **100 km** 和 **1000 km**（纽约市在 1000 km 圈上），用于 practical 第一题。

---

## 四、课堂补充

本节是 transcript 里有、slides 上没有的内容。

### 4.1 关于这节课本身

- 这节课**不是标准的过 slides**：老师说根据学生反馈，「rather than going through the lecture slides」，本次只挑对数的**要点 (salient things)** 讲，然后**现场做一道题**。所有 slides 上的例题「you can sit and look at those yourselves」——**需要自己课后补看**。
- 老师解释了教学场地的限制：以前在大平房 (flat room) 里可以叫更多 GTA 进来分组做不同的东西，今年在阶梯教室 (lecture theatre) 做不到。她鼓励：如果一群人想要不同的教学形式，**发邮件**给她，因为在大教室里当面举手很难 ("it's hard to put your hand up... in front of the big group")。
- 老师是**大气科学家 (atmospheric scientist)**，所以在里氏震级和大气科学两块内容里她选了讲大气。

### 4.2 讲座现场完整例题：人类何时吃光全球净初级生产力？

这是 **Week 2** 那道「uses logs — 先跳过」的题的后半部分，本周补做。老师说「it's just a case of... you would have known the NPP and how much one person eats in one year **because you'd already worked out all those things in the previous problem**」。

**已知**
- 全球净初级生产力 $\text{NPP} = 5.88\times10^{20}$ J/yr
- 一个人每天摄入 2500 kcal
- 2008 年世界人口 $P_0 = 6.7\times10^{9}$
- 人口年增长率 2%

**问**：多少年后人类将吃掉全部净初级生产力？

**Step 1：一个人一年吃多少焦耳**

老师在课上的引导：「I need to know how much a person eats in a year... **Change kilocalories to joules and multiply by 365.**」

$$2500\ \text{kcal/day} \times 4184\ \text{J/kcal} = 1.046\times10^{7}\ \text{J/day}$$
$$1.046\times10^{7} \times 365 = 3.8\times10^{9}\ \text{J per person per year}$$

（⚠️ 转写里老师口误说成 "joules per person per **day**"，但从上下文和数值可知是 **per year**——$3.8\times10^9$ J/day 是荒谬的。）

**Step 2：NPP 能养活多少人**

$$N = \frac{\text{NPP}}{\text{每人每年}} = \frac{5.88\times10^{20}}{3.8\times10^{9}} \approx 1.53\times10^{11}\ \text{人}$$

（约 1530 亿人。）

**Step 3：建立增长方程**（老师在黑板上一步步推）

每年人口乘以 1.02（增长 2%）：
- 2008：$P_0$
- 2009：$P_0 \times 1.02$
- 2010：$P_0 \times 1.02 \times 1.02 = P_0(1.02)^2$
- …
- $n$ 年后：$P = P_0 (1.02)^n$

老师的类比：「If I use two and just say you're going to multiply it by itself and multiply it by itself... we'd go squared, cubed, to the power four. **So in this case, we're multiplying by 1.02**, we're going to do it as many times as we need to, $n$ times.」

**Step 4：解方程（先做不用 log 的那一步）**

老师问：「There's an easy bit first that you can do without having to worry about logs. What's the first thing you do?」→ **两边同除以 $P_0$**：

$$(1.02)^n = \frac{1.53\times10^{11}}{6.7\times10^{9}} = 22.8\ldots$$

**Step 5：两边取对数**

老师问：「If you log one side, what have you got to do to the other side?」→ **另一边也要取 log**：

$$\log\left[(1.02)^n\right] = \log(22.8)$$

用**第三定律**把 $n$ 从指数上拉下来：

$$n\log(1.02) = \log(22.8)$$

$$n = \frac{\log(22.8)}{\log(1.02)} = \frac{1.3579}{0.008600} \approx 158$$

**答：约 158 年。**（用 ln 也一样：$\ln 22.8 / \ln 1.02 = 3.128/0.01980 \approx 158$。）

**Step 6：老师提到的两种等价写法**

(a) **长写法**（练习对数变形）：注意到 $n = \log(22.8) - \log(1.02)$ 是**错的**——正确的是**除**不是减。老师在课上说的是可以把右边那个大数写成商的形式再拆：如果写成 $\log\left(\frac{\text{目标人口}}{\text{初始人口}}\right) = \log(\text{目标}) - \log(\text{初始})$，用**第二定律**先把分数拆开算，这样练习「manipulating logs」。

(b) **换底写法**：直接 $n = \log_{1.02}(22.8)$，若计算器支持任意底可一步得出，「I should give you about the same answer」。

**Step 7：老师强调的两个「元技能」**

1. **先猜后算 (estimate first)**：老师在算出结果前先问全班猜多久，有人猜「a few hundred years」，老师说「Wasn't a bad guess... **You have to start getting used to the idea of making a bit of a guess to start with, and then seeing if it makes sense.**」——先估一个数量级，算完对照，是理科生必备习惯。
2. **不要过早四舍五入 (don't round too early)**：「Just be careful not to round them up too much because **it can make a difference to your answer**.」对数运算对中间值的舍入很敏感。

**Step 8：结果的现实意义**
老师的结语：如果人口继续以这个速度增长，且我们**找不到其他食物来源或更高效的养活方式** (any other source or more efficient way to feed ourselves)，约 158 年后人类将消耗掉地球全部净初级生产力。

### 4.3 关于对数定律的口头澄清

- 「$10^A \times 5^B$ **cannot** be written as $10^{A+B}$」——底不同不能合并，对数同理。这是老师举的反例。
- 关于要不要背证明：**不需要**，只要会用。建议用简单数字自己验证（「go through that and do it yourself with simple numbers that you understand」），因为一旦引入 log 就得查表/按计算器，「it's not so intuitive to show you」。
- 「it's really a case of **recognizing when to use a logarithm** and then **how you manipulate them**」——本周的能力目标就这两条：识别何时该用 log（凡是未知数在指数位置），以及会变形。

### 4.4 关于航迹云的现场讨论（讲座最后 5 分钟）

老师现场放了卫星云图的 time-lapse 动画（她一度以为技术故障打不开）。要点已整理在第三节 3.4(1)。补充口述细节：
- 「the brightness is the cloud reflecting sunlight. So the brighter the cloud, then it's usually either the higher or the colder it is.」
- 「as you got more and more smaller, smaller droplets, it looked whiter and whiter」——回指前面那张蓝底白点的 slides。
- 飞机尾气「put a lot more condensation particles in that line, you end up with lots more smaller droplets along that line」→ 那条线特别亮 → 「it slowly fades over time as it all dissipates」。
- 晴空中的凝结尾迹是同一个过程：「water vapour and hot gases, the water vapour condenses onto the [nuclei], creates this line, [given the] right conditions」。

---

## 五、Practical 要点

### 5.1 本周 practical 安排（slides W5_3 最后一页）

- **先做补充材料 (supplementary material)**：logarithms and exponentials
- **主问题做 1 和 2**（第 3 题不用做）
- **作业 (Homework)**：Blackboard 上的 "Exponentials and Logarithms"

answers 文件末尾的完整清单：
- **背景阅读**：Croft & Davison (2006) 中 'The exponential function'、'The logarithm function' 两章；**或** *Foundation Maths Support Pack* 的 §2.16, 2.17, 2.18, 3.4, 3.5, 3.6
- **Blackboard 上要交的两个 assessment**：
  - "The exponential and the logarithm functions"
  - "Logarithms in Earth and Environmental Science"

### 5.2 Problem 3.7 — 查尔斯顿地震 (Earthquake!)

**背景**：1886 年南卡罗来纳州查尔斯顿 (Charleston, South Carolina) 地震，估计里氏 **7.3** 级。本题的目的是「convert the amplitudes produced by an Earthquake at distance $D$ to an **equivalent magnitude for if the Earthquake occurred locally** ($D=0$)」——把远处测到的振幅换算成「假如这就是本地地震」的等效震级，从而直观感受**距离对振幅的巨大衰减**。

用到的两式：
$$m_l = \log_{10}A - \log_{10}A_0, \qquad -\log_{10}A_0 = 1.4 + 0.16\sqrt{D}$$

**第 1 问：$D = 100$ km 处测到的振幅 $A$**

方法（answers 的 Notes）：把 $-\log_{10}A_0$ 的表达式代入 $m_l$ 的式子；然后**两边减去 1.4 和 $0.16\sqrt D$** 来解出 $A$。

$$7.3 = \log_{10}A + 1.4 + 0.16\sqrt{100}$$
$$7.3 = \log_{10}A + 1.4 + 1.6$$
$$\log_{10}A = 7.3 - 3.0 = 4.3$$
$$A = 10^{4.3} = 1.995\times10^4 \approx \mathbf{20{,}000\ mm}\ (= 20\ \text{m})$$

**第 2 问：若这个振幅是在震中 ($D=0$) 测到的，震级是多少？**

$D=0$ 时 $-\log_{10}A_0 = 1.4 + 0 = 1.4$（即 $A_0 = 10^{-1.4} = 0.0398$ mm）：

$$m_l = \log_{10}(20{,}000) + 1.4 = 4.301 + 1.4 = \mathbf{5.70}$$

**第 3 问：$D = 1000$ km（纽约市）处的振幅**

$$\sqrt{1000} = 31.62,\qquad 0.16 \times 31.62 = 5.06$$
$$\log_{10}A = 7.3 - 1.4 - 5.06 = 0.84$$
$$A = 10^{0.84} \approx \mathbf{6.9\ mm}$$

**第 4 问：若纽约那个振幅出现在震中，震级是多少？**

$$m_l = \log_{10}(6.9) + 1.4 = 0.839 + 1.4 = \mathbf{2.24}$$

**结论与体会**：
- 同一次 7.3 级地震，100 km 外振幅约 **20 m**，1000 km 外只有 **6.9 mm** —— 相差约 3000 倍。
- 如果不做距离校正，直接把这两个振幅当本地地震读数，会得到 **5.70 级** 和 **2.24 级**——差 3.5 级，而真实震级是唯一的 7.3。**这就是为什么 $A_0(D)$ 这一项必不可少**。
- 数学技能点：把一个式子**代入**另一个式子；对含 log 的方程**先移项再取反对数** ($A = 10^{\text{something}}$)。

### 5.3 Atmospheric Science 1 — 云滴冻结

**题**：$J = 0.1\ \text{s}^{-1}$，未冻结液滴降到初始值的 **1%** 需要多久？

**解**（answers Notes：「Rearrange the nucleation equation for $t$ and put values in」）：

$$N = N_0 e^{-Jt} \;\Rightarrow\; \frac{N}{N_0} = e^{-Jt} = 0.01$$

两边取自然对数（因为底是 e，**必须用 ln 不能用 log10**）：

$$\ln(0.01) = \ln(e^{-Jt}) = -Jt$$
$$-4.605 = -0.1\,t$$
$$t = \frac{4.605}{0.1} = 46.05 \approx \mathbf{46\ s}$$

**要点**：$\ln(e^x)=x$ 是这里唯一的技巧。另外注意 $\ln(0.01) = \ln(10^{-2}) = -2\ln 10 = -4.605$。

### 5.4 Atmospheric Science 2 — 成云高度（本周最综合的一题）

**题**：一个气块 $T = 285$ K，$P = 9\times10^4$ Pa。
(a) 求 $\theta$；
(b) 若温度下降 5 K 即可成云，求相应的气压降；
(c) 气块必须上升多少米才能成云？（提示：用静力方程）

**Step (a)：算初始 θ**

$$\theta = T\left(\frac{P_{\text{ref}}}{P}\right)^{\kappa} = 285 \times \left(\frac{1\times10^{5}}{9\times10^{4}}\right)^{0.286}$$

$$= 285 \times (1.1111)^{0.286} = 285 \times 1.0306 = \mathbf{293.7\ K}$$

（计算细节：$\ln 1.1111 = 0.10536$；$\times 0.286 = 0.030133$；$e^{0.030133} = 1.03059$。）

**Step (b)：温度降 5 K 后的气压**

θ **守恒**（这是题目给的条件，也是 slides 强调的「conservation law」），新温度 $T' = 285 - 5 = 280$ K。把 θ 式变形解 P（answers Notes：「Now rearrange the θ equation for pressure」）：

$$\theta = T'\left(\frac{P_{\text{ref}}}{P'}\right)^{\kappa} \;\Rightarrow\; \left(\frac{P_{\text{ref}}}{P'}\right)^{\kappa} = \frac{\theta}{T'} \;\Rightarrow\; \frac{P_{\text{ref}}}{P'} = \left(\frac{\theta}{T'}\right)^{1/\kappa}$$

$$P' = P_{\text{ref}}\left(\frac{T'}{\theta}\right)^{1/\kappa} = 1\times10^{5} \times \left(\frac{280}{293.7}\right)^{1/0.286}$$

$$= 10^{5} \times (0.95335)^{3.4965} = 10^{5} \times 0.8461 = \mathbf{8.46\times10^{4}\ Pa}$$

**气压降** $\Delta P = 9\times10^4 - 8.46\times10^4 \approx \mathbf{5.4\times10^{3}\ Pa}$（约 5.4 kPa / 54 hPa）。

**Step (c)：上升高度**

用静力方程，$P_0 = 9\times10^4$ Pa（气块出发处的气压），$P = 8.46\times10^4$ Pa，$H = 8000$ m：

$$P = P_0 e^{-z/H} \;\Rightarrow\; \frac{P}{P_0} = e^{-z/H} \;\Rightarrow\; \ln\!\left(\frac{P}{P_0}\right) = -\frac{z}{H}$$

$$z = -H\ln\!\left(\frac{P}{P_0}\right) = -8000 \times \ln\!\left(\frac{8.46\times10^4}{9\times10^4}\right)$$

$$= -8000 \times \ln(0.9401) = -8000 \times (-0.06174) \approx \mathbf{4.9\times10^{2}\ m}$$

**答：约 490 m。** 这个量级很合理——典型的云底高度就在几百米到一两公里。

**这题的价值**：它把本周所有工具串起来了——**指数方程 → 取对数 → 变形解未知数**，同时用到一个**守恒量 (θ)** 作为桥梁把「温度变化」翻译成「气压变化」，再把「气压变化」翻译成「高度变化」。

### 5.5 Population growth — 人口翻倍

**题**：2019 年世界人口年增长率 1.08%（即每年乘以 1.0108）。多少年翻一番？

**解**（answers 明确说「For this one you will have to **write down your own equation**」——要自己建模）：

$$P = P_0 (1.0108)^n$$

翻倍即 $P = 2P_0$：

$$2\cancel{P_0} = \cancel{P_0} \times (1.0108)^n \;\Rightarrow\; 2 = (1.0108)^n$$

两边取 ln：
$$\ln 2 = \ln\left[(1.0108)^n\right]$$

**用第三定律 (the 3rd law of logarithms)**：
$$\ln 2 = n\ln(1.0108)$$

$$n = \frac{\ln 2}{\ln 1.0108} = \frac{0.6931}{0.010742} \approx \mathbf{64.5\ 年}$$

**答：约 65 年。**

**延伸（心算捷径）**：「70 法则 (rule of 70)」——翻倍时间 $\approx 70 / (\text{年增长百分数})$。这里 $70/1.08 = 64.8$，与精确值 64.5 几乎一致。原理就是 $\ln 2 \approx 0.693$ 且当 $r$ 很小时 $\ln(1+r)\approx r$：

$$n = \frac{\ln 2}{\ln(1+r)} \approx \frac{0.693}{r} = \frac{69.3}{100r}$$

### 5.6 Practical 时段的考试须知（transcript 全文要点）

Practical 的 transcript 内容**全部是下周 summative test 的说明**，重要程度极高：

**时间地点**
- **周三上午 11:00–13:00**（以个人 timetable 为准）
- 绝大多数人在 **Simon Building Room 604**（顶楼，一个大机房 computer cluster）
- 有 **DAS (Disability Advisory Service) 需求**的同学在 **Williamson Building Room 245**，由 **Catherine Harrison** 负责安排额外时间

**时长**
- 名义时长 **1 小时**，但实际给 **90 分钟**——理由：这是第一次 summative test，也是第一次在机房考，机器有时需要现场调试
- 有额外时间资格的同学在 90 分钟基础上再加

**试卷结构（关键）**
- **一份试卷，两部分**，可以前后自由跳转
- **第一部分：纯数学，占 60%** —— 分数 (fractions)、10 的幂 (powers of 10)、三角学 (trigonometry) 等，「just here's the maths, do it」
- 老师明确安慰：「**You can all pass the test without having to go anywhere near the problem**」——只做第一部分就能及格
- **第二部分：一道 problem**，但**被拆成许多小问引导你走 (broken down into parts so you're guided through it)**，就像老师在讲座里带着大家一步步做那道人口题一样，「like having me sort of standing on your shoulder and guiding you through it」

**复习提示**
- 「don't forget to have a quick read through **all** of your lecture notes」
- 「Remember that while we've mainly concentrated on the maths, **we have done a bit of physics as well** and some of your problems have been using some of the physics. **So just have a quick read through the physics.**」——⚠️ 物理部分也会考

**考场规定**
- **可以带计算器**，但**不能存文本、不能作图 (cannot store text or do graphics)**；太高级的会被**没收**
- 手机、笔记本电脑、iPad、外套、包**全部放在教室前面**，手机**必须关机**
- 桌上只能有计算器；**强烈建议自带几支笔和一张空白纸**（开考时必须是空白的，考试中可以在上面写）
- 提前做完可以**保存后安静离场**，但**一旦离场不得返回**
- 考试中可以上厕所，但**必须由监考人员陪同**

**老师的结语**：「we want you to pass and I'm sure that you all will... Don't worry too much about it. Just go in there, keep calm and do the exam. **Don't forget to save your work.**」

---

## 六、易错点 / 重点难点

1. **底必须一致 (same base)** ——三条对数定律全都以此为前提。$\log_{10}A + \ln B$ 不能合并；$10^A \times 5^B \ne 10^{A+B}$。老师在讲座里反复强调了至少三次。

2. **计算器上选错 log** ——老师点名的头号易错点。`log` 是底 10，`ln` 是底 e，**两者结果完全不同**。判断依据：
   - 方程里出现 $e^{\ldots}$（如 $N=N_0e^{-Jt}$、$P=P_0e^{-z/H}$）→ **必须用 ln**
   - 里氏震级、pH、分贝 → **用 log10**
   - 像 $1.02^n$ 这种既不是 10 也不是 e 的底 → **两个都行**，只要上下一致（$n=\log(x)/\log(1.02) = \ln(x)/\ln(1.02)$）

3. **$\dfrac{\log A}{\log B} \ne \log A - \log B$** ——第二定律是 $\log A - \log B = \log(A/B)$，注意是「**真数**相除对应**对数**相减」，不是「对数相除」。解 $n\log(1.02)=\log(22.8)$ 时是**除**以 $\log 1.02$，不是减。

4. **$\log(A+B) \ne \log A + \log B$** ——没有「加法定律」。$\log A + \log B = \log(AB)$。

5. **忘记两边同时取对数** ——解 $a^n = b$ 的标准动作是**两边都取 log**。老师现场提问：「If you log one side, what have you got to do to the other side?」

6. **过早四舍五入 (rounding too early)** ——「it can make a difference to your answer」。像 $\log(1.02) = 0.0086$ 这种很小的数，多留几位有效数字，最后再舍入。

7. **建立增长模型时用 $1.02$ 而不是 $0.02$** ——2% 的年增长意味着**每年乘 1.02**（原来的 100% 加新增的 2%），不是乘 0.02。同理 1.08% → 乘 1.0108。

8. **单位换算别漏** ——kcal → J 要乘 4184；每天 → 每年要乘 365；km 与 m；Pa 与 hPa。里氏题里 $D$ 用 km、$A$ 用 mm。

9. **里氏题里忘了 $A_0$ 随距离变化** ——$-\log_{10}A_0 = 1.4+0.16\sqrt D$ 是距离修正项。震级与距离无关，但**振幅与距离强烈相关**；$D=0$ 时该项退化为 1.4。

10. **$\sqrt{D}$ 别算错** ——$\sqrt{100}=10$（→ 1.6），$\sqrt{1000}=31.62$（→ 5.06），不是 $\sqrt{1000}=100$。

11. **位温变形时指数的倒数** ——从 $\theta = T(P_{\text{ref}}/P)^{\kappa}$ 解 $P$ 时，要开 $1/\kappa = 1/0.286 \approx 3.50$ 次方，别把 $\kappa$ 和 $1/\kappa$ 弄反。

12. **静力方程里 $P_0$ 是「起点气压」不一定是海平面气压** ——成云高度那题里 $P_0 = 9\times10^4$ Pa 是气块出发处的气压，算出的 $z$ 是**相对上升高度**，不是海拔。

13. **概念区分：Richter vs Mercalli** ——Richter 定量、测振幅、与距离无关（定义在震中）；Mercalli 定性、测破坏程度、随地点变化。

14. **Week 1 的指数律是 Week 5 的前提** ——老师明确要求回头复习。$a^m a^n = a^{m+n}$、$(a^m)^n = a^{mn}$、$a^{-n}=1/a^n$ 都要熟。

15. **考试策略**：第一部分纯数学占 60%，先把它做完再攻第二部分的引导型 problem；物理内容也要复习。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| logarithm | 对数 | 回答「底数要几次方才等于这个数」的运算，是指数的逆运算 |
| exponent / index / power | 指数 / 幂 | 底数自乘的次数；对数的值就是指数 |
| base | 底数 | 被反复相乘的那个数；对数定律要求所有项同底 |
| argument | 真数 | 对数运算的输入，必须为正 |
| common logarithm, $\log_{10}$ | 常用对数 | 以 10 为底；无特别说明时的默认底 |
| natural logarithm, $\ln$ | 自然对数 | 以 e 为底；描述自然界的增长与衰减 |
| Euler's number, $e$ | 欧拉数 | $e = 2.71828\ldots$，自然对数的底，出现在几乎所有自然增长/衰减律中 |
| exponential growth | 指数增长 | 量按固定百分比逐期增长，$P = P_0 a^n$ 形式 |
| exponential decay | 指数衰减 | 量按固定比例逐期减少，$N = N_0e^{-\lambda t}$ 形式 |
| laws of logarithms | 对数定律 | 三条：$\log A+\log B=\log AB$；$\log A-\log B=\log(A/B)$；$n\log A=\log A^n$ |
| change of base | 换底公式 | $\log_b x = \log_a x / \log_a b$，把任意底转成计算器有的底 |
| doubling time | 倍增时间 | 量翻一番所需时间，$n=\ln 2/\ln(1+r)$；小 $r$ 时约等于 $70/(100r)$ |
| Richter scale | 里氏震级 | 底 10 对数刻度，定量描述地震在震中的振幅大小 |
| local magnitude, $m_l$ | 局地震级 | $m_l = \log_{10}A - \log_{10}A_0$，做过距离校正的震级 |
| amplitude | 振幅 | 地震波位移的最大值 (mm)，随距震中距离急剧衰减 |
| epicentre | 震中 | 震源在地表的正上方投影点，$D=0$ 处 |
| Mercalli scale | 麦卡利烈度表 | 定性描述地震破坏程度/影响，随观测地点而变 |
| seismic wave | 地震波 | 地震释放的能量在地球中传播的波动 |
| order of magnitude | 数量级 | 10 的整数次幂；对数刻度就是用来压缩多个数量级的 |
| net primary productivity (NPP) | 净初级生产力 | 生态系统扣除自身呼吸后固定的能量总量，全球约 $5.88\times10^{20}$ J/yr |
| stochastic process | 随机过程 | 个体行为不可预测但群体统计规律确定的过程，如云滴冻结 |
| nucleation rate, $J$ | 成核速率 | 单位时间内单位液滴冻结的概率，单位 s$^{-1}$ |
| radioactive decay | 放射性衰变 | 经典的指数衰减过程，与云滴冻结数学形式相同 |
| hydrostatic equation | 静力方程 | $P = P_0e^{-z/H}$，气压随高度指数衰减 |
| scale height, $H$ | 标高 | 气压降到 $1/e$ 所需的高度，大气中约 8000 m |
| air parcel | 气块 | 假想的一小团空气，热力学分析的基本对象 |
| potential temperature, $\theta$ | 位温 | 气块绝热移到参考气压 (1000 hPa) 时的温度；绝热过程中守恒 |
| conservation law | 守恒律 | 某个量在过程中保持不变，这里指 θ 不随气压改变 |
| adiabatic | 绝热的 | 与外界无热量交换的过程 |
| adiabatic cooling | 绝热冷却 | 气块上升膨胀对外做功、内能减少而降温 |
| kinetic theory | 分子动理论 | 用分子运动解释宏观热学量；温度 ∝ 分子平均动能 |
| First Law of Thermodynamics | 热力学第一定律 | 能量守恒：内能变化 = 吸热 − 对外做功 |
| water vapour | 水汽 | 气态的水；暖空气能容纳的水汽比冷空气多 |
| condensation | 凝结 | 水由气态变液态；成云的直接过程 |
| Cloud Condensation Nuclei (CCN) | 云凝结核 | 悬浮在空气中、水汽可以凝结其上的小颗粒；并非所有小颗粒都能当 CCN |
| albedo | 反照率 | 反射太阳辐射的比例；液滴越多越小，云越白、反照率越高 |
| contrail | 凝结尾迹 | 飞机尾气提供额外凝结核形成的线状云，卫星云图上表现为亮直线 |
| summative test | 总结性测验 | 计入最终成绩的考试（对应 formative 形成性练习） |
