# Week 1 — 科学记数法、单位换算与「测量分子」（Scientific Notation, Units & Measuring Molecules）

> 课程：EART11200 The Natural Scientist's Toolkit — Introductory Maths for Natural Scientists
> 讲师：Professor Ann Webb
> 本周材料：`EART11200_M&P_W1_1/2/3`（Lecture slides）+ Practical Week 1（讲座录音转写文件为空，见第四节说明）

---

## 一、本周主题

本周是这门 5 周「数学与物理工具箱」课程的**第 1 周**，任务是把整门课的**地基**打好：先讲清楚"为什么自然科学家必须会算数"（Why maths matters），再补齐三样最基础的工具——**科学记数法 (scientific notation)**、**指数律 (law of indices) 与 SI 词头 (SI prefixes)**、**单位换算 (unit conversion)**；最后用一个贯穿全周的实际问题——**"测量分子" (measuring molecules)**——把这些工具串起来：从原子 (atom)、原子质量 (atomic mass)、分子质量 (molecular mass)、阿伏伽德罗常数 (Avogadro's number)，一路推到**数密度 (number density)**、**原子间平均距离 (average interatomic spacing)**，再到本周主问题**"一层油有多厚？" (How thick is a layer of oil?)** 和 **石墨烯 (graphene) 键长问题**。

在 5 周的整体位置：
- **Week 1（本周）**：数量级、记数法、单位、指数律；用摩尔 (mole)/密度 (density)/体积 (volume) 做"尺度估算"。这是后面所有内容的**语言基础**。
- 后续几周将在此基础上展开代数、函数、图像、微分、积分等工具。**本周的东西是"每次算题都要用"的底层技能，不是可以跳过的开场白。**

一句话概括本周的核心能力目标：**给你一个真实世界的物理量，你能把它写成正确的数量级、正确的单位，并判断这个数字合不合理。**

---

## 二、核心概念

### 2.1 为什么自然科学需要数学（Why maths matters）

slides 用三句引言开场，直接给出这门课的哲学立场：

> "To not know math is a severe limitation to understanding the world." — Richard P. Feynman
> "There is nothing that living things do that cannot be understood from the point of view that they are made of atoms acting according to the laws of physics." — Richard P. Feynman
> "Mathematics is the queen of science, and arithmetic the queen of mathematics." — Carl Friedrich Gauss

**核心论点：**

1. **地质学与环境科学不是"只描述"的定性科学 (qualitative science)。**
   描述化石长什么样、污染怎样影响生物，这只是入口。像所有**真正的科学 (true science)** 一样，它们本质上是**定量的 (quantitative)**。
2. **科学的目的是预测未来 / 解释过去。**
   我们通常想预测未来会发生什么，或解释过去发生了什么——而解释过去，往往正是为了更好地预测未来。这两件事都必须靠数字。
3. **就业理由（slides 引用了本系 Industrial Liaison Panel 的雇主问卷）：**
   - Robert Finney（BP）：雇主看重"标准的学位级技能，例如**数值能力 (numeracy)**、团队合作、演示表达"。
   - Shaun Robinson（Environment Agency）：明确回答"**是**，需要相当水平的数学 / 定量技能"——因为要用它来证明基本数值能力，并且实际用于**排放量与排放物的计算、单位换算 (conversion into appropriate units)、以及影响建模 (impact modelling)**。
   - Paul Field（Met Office）："我们要找的是那些能**用数字把事情做出来 (can 'do stuff', numerically)** 的人。"

> 记忆点：这门课不是"数学系的数学"，而是**为了算排放、算通量、算年代、算浓度而存在的数学**。

### 2.2 起点：批判性判断力（Critical faculty）—— 最重要的思维习惯

slides 把这一条放在所有技术内容之前，说明它的地位。

**含义：算完一个数，先问"这个数合不合理？"**

slides 给的反例：
> 计算一个**直径 100 m 的湖**的质量，如果你算出来是 **50–80 kg**，你要立刻意识到不对劲。

**为什么不对——自己做量级估算（order-of-magnitude estimate）：**
设湖为圆柱形，直径 $D=100$ m（半径 $r=50$ m），保守取平均水深 $h=10$ m：

$$V=\pi r^{2}h=\pi\times(50\ \mathrm{m})^{2}\times 10\ \mathrm{m}\approx 7.85\times10^{4}\ \mathrm{m^{3}}$$

水的密度 $\rho\approx 1000\ \mathrm{kg\,m^{-3}}$：

$$m=\rho V\approx 1000\times7.85\times10^{4}=7.85\times10^{7}\ \mathrm{kg}$$

即 **$\sim 10^{7}\text{–}10^{8}$ kg（几万吨到十万吨量级）**，而不是 50 kg（50 kg 只相当于一个人的体重、约 50 L 水）。差了 **6 个数量级**。

**方法论提炼：**
- 算完之后，把结果和你**已经知道的东西**比一比（Does it fit in with what you know already?）。
- 大多数计算错误的表现形式是**数量级错误**（点错小数点、单位没换、指数加减符号弄反），而数量级错误恰恰是最容易被常识抓出来的。

### 2.3 单位换算（Converting units）

slides 明确说："这是相当基础的事，但也是**常见问题 (a common problem)**，所以我们会花些时间讲。"

**基本原理：乘以"等于 1 的换算因子"（conversion factor）**

任何换算关系（如 $1\ \mathrm{km}=1000\ \mathrm{m}$）都可以写成一个值为 1 的分数：

$$\frac{1000\ \mathrm{m}}{1\ \mathrm{km}}=1\qquad\text{或}\qquad\frac{1\ \mathrm{km}}{1000\ \mathrm{m}}=1$$

乘以 1 不改变物理量的大小，只改变它的表达形式。**方向的选法：让你想消掉的单位出现在分母上。**

**例 1（速度）：把 $72\ \mathrm{km\,h^{-1}}$ 换成 $\mathrm{m\,s^{-1}}$**

$$72\ \frac{\mathrm{km}}{\mathrm{h}}\times\frac{1000\ \mathrm{m}}{1\ \mathrm{km}}\times\frac{1\ \mathrm{h}}{3600\ \mathrm{s}}=\frac{72\times1000}{3600}\ \mathrm{m\,s^{-1}}=20\ \mathrm{m\,s^{-1}}$$

km 与 h 都被约掉，只剩 m 和 s——这就是**量纲分析 (dimensional analysis)** 的自检机制。

**例 2（密度，地球科学里极常见）：把 $2.7\ \mathrm{g\,cm^{-3}}$（花岗岩）换成 $\mathrm{kg\,m^{-3}}$**

$$2.7\ \frac{\mathrm{g}}{\mathrm{cm^{3}}}\times\frac{1\ \mathrm{kg}}{1000\ \mathrm{g}}\times\left(\frac{100\ \mathrm{cm}}{1\ \mathrm{m}}\right)^{3}=2.7\times\frac{10^{6}}{10^{3}}=2.7\times10^{3}\ \mathrm{kg\,m^{-3}}$$

> **关键易错点：单位带幂次时，换算因子也必须整体取同样的幂次。**
> $1\ \mathrm{m^{3}}=(100\ \mathrm{cm})^{3}=10^{6}\ \mathrm{cm^{3}}$，**不是** $100\ \mathrm{cm^3}$。
> 同理 $1\ \mathrm{m^{2}}=10^{4}\ \mathrm{cm^{2}}$，$1\ \mathrm{km^{2}}=10^{6}\ \mathrm{m^{2}}$。

**例 3（体积记忆点）：** $1\ \mathrm{L}=1000\ \mathrm{cm^{3}}=10^{-3}\ \mathrm{m^{3}}$，所以 $1\ \mathrm{m^{3}}=1000\ \mathrm{L}$；水的密度 $1\ \mathrm{g\,cm^{-3}}=1\ \mathrm{kg\,L^{-1}}=1000\ \mathrm{kg\,m^{-3}}$。

### 2.4 建模与不确定性（Simple models & uncertainty）

slides 强调：**你们每个人都能建立真实世界情境的简单数学模型 (simple mathematical models)，并用它预测未来或反推过去。**

但同时给出警告——**要清楚你的预测有多大不确定性 (degree of uncertainty)**，其来源有两类：
1. **输入数据本身不确定 (uncertain input data)**——测量误差、参数取值范围；
2. **模型过度简化 (oversimplified models)**——把湖当成圆柱、忽略温压对密度的影响等。

> 这一点会贯穿整个学位：一个没有误差讨论的数字，在科学上是不完整的。

### 2.5 解题方法论（Problem-solving toolkit）

slides 明确说："我们提供给你构成你的**工具箱 (toolkit)** 的基本技能。一旦你拥有这些工具，你会在整个学位课程的许多不同情境中学会应用它们。"

**做题的固定流程（原文列点）：**
1. **Look for hints in the question** — 题目里的提示词往往直接指向该用哪个公式（例如出现"per gram"就想到摩尔）。
2. **Re-read the problem** — 重读题目。
3. **Look for the actual question (highlight it)** — 找出真正要问的那句话，把它**高亮**出来。（长题干里常常只有一句是问题。）
4. **Circle important data / information** — 把重要数据/信息**圈出来**。
5. **Double-check that you copied everything correctly** — 检查你有没有**抄错数字**。
6. **Try drawing a picture** — **试着画个图**，slides 特别说这"是一项非常值得培养的技能 (a great skill to develop)"。

> 第 6 条在本周的石墨烯问题里是决定性的：不画出蜂窝晶格并框出重复单元，根本无从下手。

### 2.6 科学记数法（Scientific notation）

**定义：** 把很大或很小的数写成 $a\times10^{n}$ 的简便方式（$a$ 为系数，$n$ 为整数指数）。

slides 的例子：

$$10{,}000{,}000{,}000{,}000=10^{13}=\texttt{1E13}$$
$$0.000000000001=10^{-12}=\texttt{1E-12}$$

**"E 记号" (E-notation)：** `1E13` 是计算器 / 计算机上的写法，`E` 后面的数字就是 10 的指数（slides 原话："superscript numbers, # after E"）。**这门课的 slides 与题目会大量混用 $10^{n}$ 与 `En` 两种写法，必须都认识。**

**运算规则（这就是指数律在 $b=10$ 时的特例）：**

- **相乘 → 指数相加：**
  $$(3\times10^{13})\times(2\times10^{-12})=(3\times2)\times10^{13+(-12)}=6\times10^{1}=60$$
  注意：**系数相乘，指数相加**，两件事分开做。
- **相除 → 指数相减：**
  $$\texttt{1E13}/\texttt{1E-12}=10^{13-(-12)}=10^{25}=\texttt{1E25}$$
  slides 特别把括号写出来：$13-(-12)=25$——**减去负数等于加**，这是本周最高频的符号错误。
- **零次幂：** $10^{0}=1$（slides 用 "NB" 标注，即 nota bene，请注意）。

### 2.7 指数律（Law of indices）

**术语：** 在 $b^{3}$ 中，$b$ 是**底数 (base number)**，上标 3 是**指数 (index / power)**，复数为 indices。

**核心条件（slides 反复强调）：只有在底数 $b$ 相同时，指数才能相加减。** 对科学记数法和 SI 词头来说，底数恒为 10，所以永远可以合并。

**底数不同就不能合并：**
- $a^{2}b^{4}$ **不能**化简（两个不同底数）。
- 但 $a^{2}b^{4}\times a^{5}b^{6}c=a^{7}b^{10}c$ ——**对每一个底数分别合并**：$a$ 的指数 $2+5=7$，$b$ 的指数 $4+6=10$，$c$ 只出现一次即 $c^{1}$。

**幂的幂（power of a power）：**
$$(a^{3})^{3}=a^{3}\times a^{3}\times a^{3}=a^{9}$$
slides 注明是 "(multiply)"——**指数相乘**，即 $(a^{m})^{n}=a^{mn}$。注意这与"相乘时指数相加"是两条不同的规则，极易混淆。

**分数指数（fractional indices）= 根号：**
- 平方根 (square root) 写作 $a^{1/2}$，即 $\sqrt{a}$；
- 立方根 (cube root) 写作 $a^{1/3}$，即 $\sqrt[3]{a}$；
- slides 强调："这些分数指数的**用法与整数指数完全一样**"——即 $\left(a^{1/2}\right)^{2}=a^{1}=a$，$a^{1/2}\times a^{1/2}=a$，$a^{2/3}=\sqrt[3]{a^{2}}=\left(\sqrt[3]{a}\right)^{2}$。

> slides 补充说明：如果你对 indices 不熟悉，请阅读 Blackboard 上的支持材料 **`all_maths`**，或在 practical 课上直接问。

**完整规则表见第三节 3.1。**

### 2.8 SI 词头（SI prefixes）

**本质：SI 词头就是 10 的整数次幂的代号。** 所有词头换算最终都归结为"指数相减"。

slides 给的三行"心算示范"：
- $\texttt{E-7}/\texttt{E-9}=\texttt{E2}=10^{2}=100$，配算式 $(-7)-(-9)=2$
- $\texttt{E24}\times1000=\texttt{E27}$
- $\texttt{E27}/\texttt{E18}=\texttt{E9}$

**换算的通用思路：**
$$\text{以词头 P 为单位的数值}=\frac{\text{以基本单位表示的数值}}{\text{P 所代表的 }10\text{ 的幂}}$$
例如换成 nm（$10^{-9}$ m），就把用 m 表示的数除以 $10^{-9}$，即**指数减去 $-9$、也就是加 9**。

**完整词头表与本周 6 道例题的完整解答见第三节 3.2 / 3.3。**

### 2.9 原子与元素周期表（Atoms & the Periodic Table）

**本周讲什么、不讲什么：**
- 讲：周期表、原子、原子质量、分子质量、摩尔、阿伏伽德罗常数。
- **不讲**：离子键与共价键 (ionic, covalent bonding)。slides 明确说这部分放在本模块的 **Chemistry of the Earth** 部分讲；有兴趣可看 Blackboard 上 `eart11200_appendices` 的 **附录 C2**。

**中性原子的基本事实：**
$$\text{质子数 (number of protons)}=\text{电子数 (number of electrons)}$$
这保证原子整体电中性。

**氢 (hydrogen)：最简单的原子**
- 组成：1 个质子 + 1 个电子。
- 尺寸：$\sim1\times10^{-10}\ \mathrm{m}=1\ \text{Å}$（**埃 (Ångström)**，$1\ \text{Å}=10^{-10}$ m）。
- slides 的关键提问与回答："我们**不能只是再加一个质子**——因为**正电荷互相排斥 (positive charges repel)**，我们必须**加一些'胶水' (add some glue)**。"
  这个"胶水"就是**中子 (neutrons)**：中子不带电，通过**强核力**帮助把原子核**束缚在一起 (help to bind the nucleus together)**，抵消质子间的静电排斥。这是"为什么重元素中子数比质子数多"的直观解释。

**壳层模型 (shell model of the atom)：**
- 原子核 (nucleus) 在中心，含质子 (protons) 与中子 (neutrons)；电子分布在外面一层层的**壳层 (shells)** 上。
- **质量事实（本周最重要的数字之一）：**
  - 质子与中子的质量都约为 $1.66\times10^{-27}\ \mathrm{kg}$（$=1.66\times10^{-24}\ \mathrm{g}$）；
  - 电子质量 $9.1\times10^{-31}\ \mathrm{kg}$。
  - slides 原话："电子与质子、中子相比**几乎没有质量 (hardly have any mass)**"。
  - 定量核对：$\dfrac{1.66\times10^{-27}}{9.1\times10^{-31}}\approx1.8\times10^{3}$，即**质子约为电子的 1800 倍重**。所以**计算原子质量时电子可以忽略**——这是后面"原子质量 ≈ 质量数 × $1.66\times10^{-24}$ g"这一近似成立的原因。

**slides 上的两个课堂提问（Socratic questions）：**

1. **"如果我们打掉一个中子（比如用高能中子把它撞出来），会发生什么？它现在是什么元素？"**
   **答：仍然是同一种元素。** 元素身份**只由质子数（原子序数 atomic number, $Z$）决定**；改变中子数只改变**质量数 (mass number, $A$)**，得到的是同一元素的**另一种同位素 (isotope)**。
   例：$^{7}\mathrm{Li}$（3 质子 + 4 中子）打掉一个中子 → $^{6}\mathrm{Li}$（3 质子 + 3 中子），**还是锂**，只是质量数从 7 变成 6。
   > 这个概念在地球科学里极其重要：同位素地球化学（放射性定年、稳定同位素示踪）整个建立在"同元素、不同中子数"之上。

2. **"这个原子是什么元素？"（配图标注 Size ~ $1.52\times10^{-10}$ m = 1.52 Å）**
   **答：锂 (lithium, Li, $Z=3$)。** 锂的原子半径正是 152 pm = 1.52 Å，且壳层图上画的是 2 个电子壳层、3 个质子。对照氢的 1 Å——原子尺寸都在**几个 Å（即 $10^{-10}$ m 量级）**，这是要记住的"原子尺度"。

### 2.10 阿伏伽德罗常数（Avogadro's number）—— 本周的推导核心

**问题的出发点（slides 原文逻辑）：**
一个质子的质量（$1.66\times10^{-24}$ g）**小到我们没法直接用**。我们需要另一种表达原子数量的方式：**定义一个"我们能用克为单位称量出来"的原子数目**。

**推导（完整过程）：**

取氢——最简单、最小的原子，只有 1 个质子和 1 个电子（电子质量可忽略），所以

$$m_{\mathrm{H}}\approx1.66\times10^{-24}\ \mathrm{g}$$

问：**多少个氢原子重 1 克？** 设这个数为 $N$，则

$$(\text{1 克中的 H 原子数})\times(\text{1 个 H 原子的质量})=1\ \mathrm{gram}$$

$$N\times m_{\mathrm{H}}=1\ \mathrm{g}$$

$$N=\frac{1\ \mathrm{g}}{m_{\mathrm{H}}}=\frac{1}{1.66\times10^{-24}}=6.02\times10^{23}$$

这个数就是**阿伏伽德罗常数 (Avogadro's number)**：

$$\boxed{N_{A}=6.02\times10^{23}}$$

（现代 SI 定义值：$N_{A}=6.02214076\times10^{23}\ \mathrm{mol^{-1}}$，2019 年起为**精确定义值**；本课用 $6.02\times10^{23}$ 即可。）

**推广到任意元素——"按质量数 A 缩放"（This scales with mass number, A）：**

对质量数为 $A$ 的元素，一个原子含 $A$ 个核子（质子+中子），每个核子质量约 $1.66\times10^{-24}$ g，所以

$$m_{\text{atom}}\approx A\times1.66\times10^{-24}\ \mathrm{g}$$

那么 $N_A$ 个这样的原子总质量为

$$N_{A}\times\left(1.66\times10^{-24}\ \mathrm{g}\right)\times A=6.02\times10^{23}\times1.66\times10^{-24}\times A\ \mathrm{g}=1.0\times A\ \mathrm{g}=A\ \text{gram}$$

（核心巧合：$6.02\times10^{23}\times1.66\times10^{-24}\approx1$，因为 $1.66\times10^{-24}=1/N_A$ 按定义就是这么来的。）

**结论（slides 原文）：**
> **"'A' grams of every element contains Avogadro's number of atoms."**
> 每一种元素，取 **A 克**（A = 质量数），其中就恰好含有**阿伏伽德罗常数个原子**。

这直接导出**原子质量 (atomic mass)** 的概念：

> **'Atomic mass' = mass of 1 mole of an element**（1 摩尔某元素的质量，单位 $\mathrm{g\,mol^{-1}}$，数值等于质量数 $A$）

**摩尔 (mole) 的定义：** 含有 $N_A=6.02\times10^{23}$ 个基本单元（原子/分子/离子）的物质量。

### 2.11 分子质量（Molecular mass）

**原子质量的概念可以直接推广到分子。**

计算方法：**把分子里所有原子的原子质量加起来**（slides："Sum of mass nos, means add up the atomic masses of all atoms in molecule"）。

$$N_{A}\times\left(1.66\times10^{-24}\ \mathrm{g}\right)\times(\text{sum of mass numbers})=\text{molecular mass}\ [\mathrm{g\,mol^{-1}}]$$

> **'Molecular mass' = mass of 1 mole of a substance**

**结论（slides 原文）：**
> **"So 'sum of mass no' grams of every molecule contains Avogadro's number of molecules."**

**例（自补，标准算例）：水 $\mathrm{H_2O}$**
$$M(\mathrm{H_2O})=2\times1+16=18\ \mathrm{g\,mol^{-1}}$$
即 18 g 水中含有 $6.02\times10^{23}$ 个水分子。

**例：二氧化碳 $\mathrm{CO_2}$**
$$M(\mathrm{CO_2})=12+2\times16=44\ \mathrm{g\,mol^{-1}}$$

**例：石英 $\mathrm{SiO_2}$**
$$M(\mathrm{SiO_2})=28+2\times16=60\ \mathrm{g\,mol^{-1}}$$

**由此得到的关键推论（slides 明确指出，用于 'related problems 2'）：**
> 你现在知道**每单位质量物质中有多少原子/分子**，即
> $$\frac{\text{分子数}}{\text{质量}}=\frac{N_A}{M}\qquad\left(\text{每克含 }\frac{1}{\text{molecular mass}}\text{ 摩尔}\right)$$

### 2.12 从"每克多少个"到"每立方米多少个"：密度与数密度

slides 提出的承接问题：
> **"How can we work out the number of atoms / molecules per unit volume?"**（怎么求单位体积里的原子/分子数？）

**桥梁就是密度 (density)：**

$$\rho\ [\mathrm{kg\,m^{-3}}]=\frac{m\ [\mathrm{kg}]}{V\ [\mathrm{m^{3}}]}\qquad\Longleftrightarrow\qquad m=\rho V$$

**推导数密度 (number density) $n$：**

取体积 $V$ 的物质：
1. 质量 $m=\rho V$
2. 摩尔数 $n_{\mathrm{mol}}=\dfrac{m}{M}=\dfrac{\rho V}{M}$
3. 分子数 $N=n_{\mathrm{mol}}\times N_{A}=\dfrac{\rho V N_{A}}{M}$
4. 数密度（单位体积分子数）

$$\boxed{n=\frac{N}{V}=\frac{\rho N_{A}}{M}}\qquad[\mathrm{m^{-3}}]$$

> **单位陷阱：** $\rho$ 用 $\mathrm{g\,m^{-3}}$、$M$ 用 $\mathrm{g\,mol^{-1}}$ 时，$n$ 的单位才是 $\mathrm{m^{-3}}$。若 $\rho$ 用 $\mathrm{kg\,m^{-3}}$，要先乘 1000 换成 $\mathrm{g\,m^{-3}}$。

### 2.13 从数密度到原子间平均距离

slides 的最后一问：
> **"If you know how many atoms (or molecules) there are per unit volume [# m$^{-3}$], how can you calculate the *average* distance between atoms (or molecules) [m]?"**

**推导思路：** 每个原子"独占"的体积是数密度的倒数：

$$v_{\text{per atom}}=\frac{1}{n}\ [\mathrm{m^{3}}]$$

把这块体积近似看成一个边长为 $d$ 的小立方体（即想象原子排成简单立方点阵），则 $d^{3}=1/n$，于是

$$\boxed{d=\left(\frac{1}{n}\right)^{1/3}=n^{-1/3}}$$

这就是**原子（分子）间的平均距离**。

> 注意这里用到了 **2.7 节的分数指数**：开立方 = 取 $1/3$ 次幂。这正是 slides 把指数律放在前面讲的原因。

**完整算例见第三节 3.5。**

### 2.14 体积与密度的旁注（Aside on Volume/Density）

slides 单独用一页强调三件事：

1. **必须会算简单形状的面积、体积和表面积**：
   正方形 / 圆 / 三角形；立方体 / 长方体 (cuboid)、球 (sphere)、圆柱 (cylinder)、圆锥 (cone)。
   公式可在 Blackboard 文件 `eart11200_appendices` 的**附录 B** 中找到。（常用公式见 3.4 节。）
2. **物质的密度可以查表**，但要注意——
3. **⚠️ 查到的密度通常是 STP（标准温压 standard temperature and pressure）下的值。密度会随温度和压力变化！**
   这在地球科学里尤为致命：气体密度对温压极敏感（理想气体 $\rho\propto P/T$）；岩石/水在深部高压下也会被压缩。**做题时要留意题目给的是哪种条件下的密度。**

### 2.15 本周主问题与作业安排（Today / in week）

slides 给出的**本周任务顺序**（务必按顺序做）：

1. **先做补充材料 (supplementary material)**：
   - `eart11200_additional_1`
   - `eart11200_additional_2`
2. **然后尝试主问题 (main problem)**：`eart11200_week01` —— **"How thick is a layer of oil?"（一层油有多厚？）**
3. **然后做相关问题 (related questions)**（在同一个文件里）
4. **本周内完成 Blackboard 上的测评 (Blackboard assessments)**，具体在主问题文件末尾有说明。
5. **Practical 课：周五 11:00**

**必须带的东西（slides 用加粗强调 "Remember to have everything you need available"）：**
- **Laptop（笔记本电脑）**
- **Pencil and paper（纸笔）**
- **Calculator（计算器）**

> 手算/纸笔仍然是必需品——画图、列量纲、写中间步骤都要靠它。

---

## 三、公式与图表

### 3.1 指数律完整表（Law of indices）

| 规则 | 公式 | 说明 / 陷阱 |
|---|---|---|
| 同底相乘，指数相加 | $b^{m}\times b^{n}=b^{m+n}$ | **底数必须相同** |
| 同底相除，指数相减 | $\dfrac{b^{m}}{b^{n}}=b^{m-n}$ | 减负数 = 加正数 |
| 幂的幂，指数相乘 | $(b^{m})^{n}=b^{mn}$ | slides 例：$(a^{3})^{3}=a^{9}$ |
| 零次幂 | $b^{0}=1$（$b\neq0$） | slides 用 "NB" 标出 |
| 负指数 = 倒数 | $b^{-n}=\dfrac{1}{b^{n}}$ | $10^{-3}=0.001$ |
| 分数指数 = 根号 | $b^{1/n}=\sqrt[n]{b}$ | $a^{1/2}=\sqrt a$，$a^{1/3}=\sqrt[3]{a}$ |
| 一般分数指数 | $b^{m/n}=\sqrt[n]{b^{m}}=\left(\sqrt[n]{b}\right)^{m}$ | |
| 积的幂 | $(ab)^{n}=a^{n}b^{n}$ | |
| 商的幂 | $\left(\dfrac{a}{b}\right)^{n}=\dfrac{a^{n}}{b^{n}}$ | |
| **不同底数不能合并** | $a^{2}b^{4}$ 无法化简 | 但 $a^{2}b^{4}\times a^{5}b^{6}c=a^{7}b^{10}c$（逐底数合并） |
| **加法没有指数律** | $b^{m}+b^{n}\neq b^{m+n}$ | 高频错误 |

### 3.2 SI 词头完整表（SI prefixes）

| 词头 | 符号 | 因子 | E 记号 | 中文 |
|---|---|---|---|---|
| tera | T | $10^{12}$ | E12 | 太（兆兆） |
| giga | G | $10^{9}$ | E9 | 吉 |
| mega | M | $10^{6}$ | E6 | 兆 |
| kilo | k | $10^{3}$ | E3 | 千 |
| — | — | $10^{0}$ | E0 | 基本单位 |
| centi | c | $10^{-2}$ | E-2 | 厘 |
| milli | m | $10^{-3}$ | E-3 | 毫 |
| micro | μ | $10^{-6}$ | E-6 | 微 |
| nano | n | $10^{-9}$ | E-9 | 纳 |
| pico | p | $10^{-12}$ | E-12 | 皮 |
| femto | f | $10^{-15}$ | E-15 | 飞 |
| atto | a | $10^{-18}$ | E-18 | 阿 |

**本周题目额外用到的大词头（"tricky" 那两题就是考这个）：**

| 词头 | 符号 | 因子 |
|---|---|---|
| peta | P | $10^{15}$ |
| exa | E | $10^{18}$ |
| zetta | Z | $10^{21}$ |
| yotta | Y | $10^{24}$ |

> ⚠️ **注意符号冲突**：作为词头的 **E = exa = $10^{18}$**，与作为记数法的 **E（`1E13`）** 是两码事，靠上下文区分。

### 3.3 slides 例题：词头换算 6 题（完整解答）

slides 上只给了其中两题的答案（500 和 1.66E-6），其余为课堂口头/自练。以下为全部 6 题的完整过程。

**(1) 绿光波长 (wavelength of green light) $5\times10^{-7}$ m，等于多少纳米 (nm)？**
$$1\ \mathrm{nm}=10^{-9}\ \mathrm{m}\quad\Rightarrow\quad \frac{5\times10^{-7}}{10^{-9}}=5\times10^{-7-(-9)}=5\times10^{2}=\boxed{500\ \mathrm{nm}}$$
✔ 与 slides 答案 "500" 一致。这也正是 slides 上那行 $\texttt{E-7}/\texttt{E-9}=\texttt{E2}=100$ 的来源。
（记忆点：可见光波长 400–700 nm，绿光约 500–550 nm——合理。）

**(2) 太阳常数 (solar constant) $\approx1300\ \mathrm{W\,m^{-2}}$，等于多少 $\mathrm{kW\,m^{-2}}$？**
$$1\ \mathrm{kW}=10^{3}\ \mathrm{W}\quad\Rightarrow\quad\frac{1300}{10^{3}}=\boxed{1.3\ \mathrm{kW\,m^{-2}}}$$
✔ 与 slides 答案 "1.3" 一致。

**(3) 云滴尺寸 (size of a cloud drop) $1\times10^{-5}$ m，等于多少微米 (μm)？**
$$1\ \mathrm{\mu m}=10^{-6}\ \mathrm{m}\quad\Rightarrow\quad\frac{10^{-5}}{10^{-6}}=10^{-5-(-6)}=10^{1}=\boxed{10\ \mathrm{\mu m}}$$
（典型云滴直径确实是 10–20 μm——合理。）

**(4) 英国能源消耗 (UK energy consumption) $6\times10^{11}$ W，等于多少太瓦 (TW)？**
$$1\ \mathrm{TW}=10^{12}\ \mathrm{W}\quad\Rightarrow\quad\frac{6\times10^{11}}{10^{12}}=6\times10^{11-12}=6\times10^{-1}=\boxed{0.6\ \mathrm{TW}}$$
（对照：全球一次能源消耗约 18–20 TW，英国占约 3%——合理。）

**(5) 地球质量 (mass of Earth) $6\times10^{24}$ kg，等于多少艾克 (exagram, Eg)？（slides 标 "tricky"）**

两步走，**先统一到克，再套词头**：
$$6\times10^{24}\ \mathrm{kg}=6\times10^{24}\times10^{3}\ \mathrm{g}=6\times10^{27}\ \mathrm{g}$$
（这就是 slides 那行 $\texttt{E24}\times1000=\texttt{E27}$。）
$$1\ \mathrm{Eg}=10^{18}\ \mathrm{g}\quad\Rightarrow\quad\frac{6\times10^{27}}{10^{18}}=6\times10^{27-18}=\boxed{6\times10^{9}\ \mathrm{Eg}}$$
（这就是 slides 那行 $\texttt{E27}/\texttt{E18}=\texttt{E9}$。）

> **"tricky" 在哪里**：题目给的是 **kg** 而词头要加在 **g** 上——**必须先把 kilo 消掉**。这是本周最典型的陷阱：*词头不能叠加*，没有 "kilo-exa-gram" 这种东西。

**(6) 氢原子质量 $1.66\times10^{-27}$ kg，等于多少阿克 (attogram, ag)？（slides 标 "tricky"）**
$$1.66\times10^{-27}\ \mathrm{kg}=1.66\times10^{-27}\times10^{3}\ \mathrm{g}=1.66\times10^{-24}\ \mathrm{g}$$
$$1\ \mathrm{ag}=10^{-18}\ \mathrm{g}\quad\Rightarrow\quad\frac{1.66\times10^{-24}}{10^{-18}}=1.66\times10^{-24-(-18)}=1.66\times10^{-6}\ \mathrm{ag}$$
$$\boxed{1.66\times10^{-6}\ \mathrm{ag}=\texttt{1.66E-6}\ \mathrm{ag}}$$
✔ 与 slides 答案 "1.66E-6" 一致。

> 顺带记住：$1.66\times10^{-24}\ \mathrm{g}$ 这个数就是**原子质量单位 (atomic mass unit, u / dalton)**，也正好等于 $1/N_A$ 克。

### 3.4 核心公式汇总

| 名称 | 公式 | 符号含义 |
|---|---|---|
| 科学记数法 | $x=a\times10^{n}$ | $a$ 系数（通常 $1\le|a|<10$），$n$ 整数指数 |
| 阿伏伽德罗常数 | $N_{A}=\dfrac{1\ \mathrm{g}}{m_{\mathrm{H}}}=\dfrac{1}{1.66\times10^{-24}}=6.02\times10^{23}$ | $m_\mathrm{H}$：一个氢原子的质量（g） |
| 原子质量标度 | $N_{A}\times\left(1.66\times10^{-24}\ \mathrm{g}\right)\times A=A\ \mathrm{g}$ | $A$：质量数 (mass number) = 质子数+中子数 |
| 单原子质量 | $m_{\text{atom}}=\dfrac{M}{N_{A}}$ | $M$：原子质量 $[\mathrm{g\,mol^{-1}}]$，数值 $=A$ |
| 分子质量 | $M=\sum_i A_i$ | 对分子中所有原子的质量数求和，单位 $\mathrm{g\,mol^{-1}}$ |
| 单分子质量 | $m_{\text{mol}}=\dfrac{M}{N_{A}}$ | |
| 摩尔数 | $n_{\mathrm{mol}}=\dfrac{m}{M}$ | $m$ 质量 (g)，$M$ 摩尔质量 $[\mathrm{g\,mol^{-1}}]$ |
| 粒子总数 | $N=\dfrac{m}{M}N_{A}$ | |
| 密度 | $\rho=\dfrac{m}{V}$，$[\mathrm{kg\,m^{-3}}]$ | $m$ 质量 [kg]，$V$ 体积 [m³] |
| 数密度 | $n=\dfrac{\rho N_{A}}{M}$，$[\mathrm{m^{-3}}]$ | $\rho$ 用 $\mathrm{g\,m^{-3}}$，$M$ 用 $\mathrm{g\,mol^{-1}}$ |
| 平均粒间距 | $d=n^{-1/3}$，$[\mathrm{m}]$ | 由 "每个粒子独占体积 $1/n$" 近似为立方体 |
| 薄层厚度 | $t=\dfrac{V}{A}$ | $V$ 液体体积，$A$ 铺开面积（油膜问题核心） |
| 比表面积 | $\mathrm{SSA}=\dfrac{A}{m}$，$[\mathrm{m^{2}\,g^{-1}}]$ 或 $[\mathrm{m^{2}\,mg^{-1}}]$ | 单位质量所具有的表面积（石墨烯问题核心） |

**附录 B 常用几何公式（Aside on Volume/Density 要求掌握）：**

| 形状 | 面积 / 表面积 | 体积 |
|---|---|---|
| 正方形 (square)，边长 $a$ | $A=a^{2}$ | — |
| 长方形，$a\times b$ | $A=ab$ | — |
| 三角形 (triangle)，底 $b$ 高 $h$ | $A=\tfrac12 bh$ | — |
| 圆 (circle)，半径 $r$ | $A=\pi r^{2}$，周长 $C=2\pi r$ | — |
| 立方体 (cube)，边长 $a$ | $S=6a^{2}$ | $V=a^{3}$ |
| 长方体 (cuboid) $a\times b\times c$ | $S=2(ab+bc+ca)$ | $V=abc$ |
| 球 (sphere)，半径 $r$ | $S=4\pi r^{2}$ | $V=\tfrac43\pi r^{3}$ |
| 圆柱 (cylinder)，半径 $r$ 高 $h$ | 侧面 $2\pi rh$；总 $2\pi r(r+h)$ | $V=\pi r^{2}h$ |
| 圆锥 (cone)，半径 $r$ 高 $h$，斜高 $l=\sqrt{r^2+h^2}$ | 侧面 $\pi rl$；总 $\pi r(r+l)$ | $V=\tfrac13\pi r^{2}h$ |

### 3.5 关键图表的文字描述

**图 A：氢原子示意（W1_3）**
中心 1 个质子，外围 1 个电子。标注 "Size ~ 1E-10 m = 1 Å"。旁注文字："Hydrogen is the simplest atom. We can't just add another proton as positive charges repel — we have to add some **glue**." → "胶水" = 中子。

**图 B：壳层模型示意（W1_3）**
原子核（质子 + 中子）+ 分层的电子壳层。标注："(neutrons help to bind the nucleus together)"；质子/中子质量 $1.66\times10^{-27}$ kg，电子质量 $9.1\times10^{-31}$ kg；尺寸 1.52 Å（→ 锂）。配两个提问（见 2.9）。

**图 C：石墨烯蜂窝晶格（W1_3 最后两页）**
- 二维 (2-D) 碳原子六边形蜂窝网格，键长记为 $t$（distance between carbon atoms）。
- 图上用红色框出一块"方形"区域 (red-outlined area / red 'square')，并标注两个几何量：**$0.5t$** 和 **$(\sqrt{3}/2)\,t$**，以及未知的 **Height = ?** 与 **Length = ?**。
- 这两个标注的来源：一条与水平方向成 $30^\circ$ 的 C–C 键，其**水平投影** $=t\cos30^\circ=\dfrac{\sqrt3}{2}t$，**竖直投影** $=t\sin30^\circ=0.5t$。这就是矩形单元的边长要用这两个量拼出来的原因。
- 解题步骤（slides 列的 4 步）：
  1. 一个碳原子的质量是多少？（提示：用阿伏伽德罗常数）
  2. **数出红框内的原子数**（Count the atoms within the red-outlined area）；
  3. **用键长 $t$ 表示红框面积**（Calculate the area of the red 'square' in terms of the bond length $t$）；
  4. **取比值，令其等于测得的比表面积**（Take a ratio and set equal to the measured specific surface area）→ 解出 $t$。
- 完整解答见第五节 5.3。

**图 D：油层问题（W1_3）**
标题页 "Problem: How thick is a layer of oil?"，即本周主问题 `eart11200_week01`。核心几何关系：**体积 = 面积 × 厚度**，故 $t=V/A$。见 5.2。

---

## 四、课堂补充

**⚠️ 本周的两个转写文件均为空文件。**

- `Lecture/Week 1/EART11200 - 27-Sep-transcript.md`
- `Practical/Week 1/EART11200 - 27-Sep-transcript.md`

两个文件都只有 YAML 文件头和一行 `'EART11200 - 27-Sep', automated transcript / 01/08/2026 / ---`，**正文部分为空**（自动转写未生成内容或录音缺失）。因此本周**没有可提取的课堂口头补充内容**。

作为替代，以下整理 **slides 本身以"口头提问 / 强调语气"形式给出、但答案没写在幻灯片上**的内容——这些正是老师课上会讲解的部分，务必自己补上答案：

1. **"打掉一个中子会怎样？现在是什么元素？"**
   → 幻灯片只有问题没有答案。**答案：元素不变**（元素由质子数决定），变成同一元素的另一种**同位素**，质量数 $A$ 减 1。

2. **"这个原子是什么元素？"（1.52 Å）**
   → **答案：锂 (Li)**，原子半径 152 pm。

3. **"为什么不能直接再加一个质子？"**
   → 幻灯片给了答案的一半（正电荷排斥），另一半要自己补：**中子提供强核力做"胶水"**，把核子束缚住。这解释了为什么原子核里必须有中子、以及为什么重元素中子数 > 质子数。

4. **"如何求单位体积的原子/分子数？"与"如何由此求平均原子间距？"**
   → 幻灯片只抛出问题并画了个大大的 "**?**"。**答案见 2.12–2.13 的推导**（$n=\rho N_A/M$，$d=n^{-1/3}$）。这两问是本周从"化学计量"跨到"尺度估算"的关键桥梁，几乎必考。

5. **老师用加粗/高亮强调的点（slides 上的 `<mark>` 与加粗）：**
   - 高亮标题：**Atoms, hydrogen and Periodic Table**、**Molecular mass** —— 这两块是本周重点。
   - 加粗强调：**"Electrons hardly have any mass compared to protons and neutrons"** —— 为忽略电子质量提供依据。
   - 加粗强调：**Laptop / Pencil and paper / Calculator** —— practical 课必带三件套。

6. **明确的"划界"提醒：**
   本周**不讲成键 (bonding)**，那是 Chemistry of the Earth 部分的内容；想提前看可以读 `eart11200_appendices` 附录 C2。**不要在本周的题里纠结键的类型，本周只关心"数原子、算质量、算尺度"。**

7. **明确的"补课"提醒：**
   对 indices 不熟的同学，先读 Blackboard 上的 **`all_maths`**，或者**在 practical 课上直接问**（老师明确邀请提问）。

---

## 五、Practical 要点

**材料状况说明：** `Practical/Week 1` 文件夹中**只有一个空的转写文件**，**没有 practical 题目文件，也没有答案文件（week01_answers）**。（对比：Week 2–5 都有 `eart11200_weekXX_answers`。）因此以下要点根据 lecture slides 中对 practical 的安排说明，以及 slides 给出的问题本身重建。

### 5.1 Practical 的目的、安排与方法

- **时间**：周五 11:00。
- **必带**：Laptop、纸笔 (pencil and paper)、计算器 (calculator)。
- **本周任务顺序（严格按此顺序）**：
  1. `eart11200_additional_1`（补充材料 1）
  2. `eart11200_additional_2`（补充材料 2）
  3. `eart11200_week01`——**主问题：How thick is a layer of oil?**
  4. 同一文件里的 **related questions**（其中 "related problems 2" 明确对应"每单位质量的原子/分子数"这一考点）
  5. 本周内完成 **Blackboard assessments**（具体说明在主问题文件末尾）
- **方法**：practical 是**答疑 + 动手算**的形式；slides 两次明确邀请"不会就在 practical 课上问"（indices 不熟的、supporting material 看不懂的）。

### 5.2 主问题：一层油有多厚？（How thick is a layer of oil?）

**这是经典的"油膜法估算分子尺寸"实验（oil-film / monolayer method）。** 逻辑链如下：

**第 1 步：几何关系——薄层厚度**

一滴已知体积 $V$ 的油滴在水面铺开，形成面积 $A$ 的薄膜。若薄膜厚度均匀为 $t$：

$$V=A\times t\qquad\Longrightarrow\qquad \boxed{t=\frac{V}{A}}$$

**示范算例（自补，典型数量级）**：设 $V=1\ \mathrm{mm^{3}}=1\times10^{-9}\ \mathrm{m^{3}}$，铺开后面积 $A=1\ \mathrm{m^{2}}$，则

$$t=\frac{1\times10^{-9}\ \mathrm{m^{3}}}{1\ \mathrm{m^{2}}}=1\times10^{-9}\ \mathrm{m}=1\ \mathrm{nm}$$

**第 2 步：物理解释——为什么这个厚度有意义**

油在水面上铺开，最薄只能铺到**一个分子那么厚**——即形成**单分子层 (monolayer)**。所以

$$t\approx\text{一个油分子的长度}$$

得到的 $\sim1\ \mathrm{nm}=10^{-9}\ \mathrm{m}=10\ \text{Å}$，与"原子尺寸约 1 Å、长链有机分子由十几个原子串成"完全吻合。**这就是不用任何显微镜就"测量了分子"的方法**——呼应本周标题 *Measuring Molecules*。

**第 3 步：用摩尔的方法交叉验证（related questions 的典型思路）**

已知油的密度 $\rho$ 和摩尔质量 $M$，体积 $V$ 的油中分子数为

$$N=\frac{\rho V}{M}N_{A}$$

若铺成单分子层占面积 $A$，则**每个分子占的面积**为

$$a=\frac{A}{N}=\frac{A M}{\rho V N_{A}}$$

**分子的横向尺寸** $\approx\sqrt{a}$，**纵向尺寸** $\approx t=V/A$。两个方向的尺寸都应落在 $10^{-10}\text{–}10^{-9}$ m，互相印证。

**第 4 步：批判性检查（呼应 2.2）**
- 结果如果算出 $10^{-3}$ m（毫米级）或 $10^{-15}$ m（原子核级），一定是单位换算错了。
- 分子尺寸的"合理区间"就是 **几 Å 到几 nm**，记死这个尺度作为 sanity check。

**易错点**：$V$ 常以 $\mathrm{mm^{3}}$ 或 $\mathrm{cm^{3}}$ 给出、$A$ 常以 $\mathrm{cm^{2}}$ 给出，**必须先统一到 SI**：$1\ \mathrm{mm^{3}}=10^{-9}\ \mathrm{m^{3}}$，$1\ \mathrm{cm^{3}}=10^{-6}\ \mathrm{m^{3}}$，$1\ \mathrm{cm^{2}}=10^{-4}\ \mathrm{m^{2}}$（**注意幂次要整体取幂！**）。

### 5.3 石墨烯问题（The 'Graphene' question）——完整解答

**题目条件（slides）：**
- 石墨烯是**二维 (2-D)** 的，**比表面积 (specific surface area) $=1.299\ \mathrm{m^{2}\,mg^{-1}}$**；
- 碳的原子质量 $M_{\mathrm{C}}=12\ \mathrm{g\,mol^{-1}}$；
- 求：碳原子之间的距离（键长）$t$。

---

**Step 1：一个碳原子的质量是多少？（提示：阿伏伽德罗常数）**

$$m_{\mathrm{C}}=\frac{M_{\mathrm{C}}}{N_{A}}=\frac{12\ \mathrm{g\,mol^{-1}}}{6.02\times10^{23}\ \mathrm{mol^{-1}}}=1.993\times10^{-23}\ \mathrm{g}$$

比表面积是以 **mg** 为单位给的，所以换算（$1\ \mathrm{g}=10^{3}\ \mathrm{mg}$）：

$$m_{\mathrm{C}}=1.993\times10^{-23}\times10^{3}\ \mathrm{mg}=1.993\times10^{-20}\ \mathrm{mg}$$

---

**Step 2：数出重复单元里的原子数 + 用 $t$ 表示它的面积**

**方法 A（用六边形，最简洁）：**
石墨烯是**蜂窝晶格 (honeycomb lattice)**：每个碳与 3 个近邻成键，键长 $t$，形成正六边形。
- 正六边形的**边长就是 $t$**，其面积为
  $$A_{\text{hex}}=\frac{3\sqrt{3}}{2}t^{2}$$
- **每个顶点上的碳原子被 3 个相邻六边形共享**，一个六边形有 6 个顶点，所以
  $$\text{每六边形独占的原子数}=6\times\frac{1}{3}=2$$
- 因此**每个碳原子占的面积**：
  $$a_{\text{per C}}=\frac{A_{\text{hex}}}{2}=\frac{3\sqrt{3}}{4}t^{2}=1.299\,t^{2}$$

**方法 B（用 slides 图上的矩形红框，对应 $0.5t$ 与 $(\sqrt3/2)t$ 的标注）：**
取一个矩形重复单元（rectangular unit cell）：
- **Length（宽）** $=2\times\dfrac{\sqrt3}{2}t=\sqrt{3}\,t$ （两个 $30^\circ$ 键的水平投影拼起来）
- **Height（高）** $=t+0.5t+t+0.5t=3t$ （沿竖直方向：一段竖直键 $t$、一段斜键投影 $0.5t$，循环两次）
- **框内原子数 = 4**
- 面积：
  $$A_{\text{rect}}=\sqrt3\,t\times3t=3\sqrt{3}\,t^{2}$$
- 每原子面积：
  $$a_{\text{per C}}=\frac{3\sqrt3\,t^{2}}{4}=1.299\,t^{2}\qquad\text{（与方法 A 完全一致 ✔）}$$

> **数值巧合（也是本题设计的妙处）：** $\dfrac{3\sqrt3}{4}=1.29904\approx1.299$ —— 正好等于题目给的比表面积数值。

---

**Step 3：取比值，令其等于测得的比表面积**

比表面积的定义：**单位质量的表面积**。对石墨烯（一层原子），单位质量的面积 = 每原子面积 ÷ 每原子质量：

$$\mathrm{SSA}=\frac{a_{\text{per C}}}{m_{\mathrm{C}}}=\frac{1.299\,t^{2}}{m_{\mathrm{C}}}$$

代入 $\mathrm{SSA}=1.299\ \mathrm{m^{2}\,mg^{-1}}$、$m_{\mathrm{C}}=1.993\times10^{-20}\ \mathrm{mg}$：

$$1.299=\frac{1.299\,t^{2}}{1.993\times10^{-20}}$$

**Step 4：解出 $t$**

$$t^{2}=\frac{1.299\times1.993\times10^{-20}}{1.299}=1.993\times10^{-20}\ \mathrm{m^{2}}$$

$$t=\sqrt{1.993\times10^{-20}}=\left(1.993\times10^{-20}\right)^{1/2}=1.412\times10^{-10}\ \mathrm{m}$$

$$\boxed{t\approx1.41\times10^{-10}\ \mathrm{m}=0.141\ \mathrm{nm}=1.41\ \text{Å}}$$

**开方的手算技巧（用到 2.7 的分数指数）：** 要开方的指数必须是偶数，所以先改写
$$1.993\times10^{-20}=19.93\times10^{-21}\ ?\ \text{（指数为奇数，不好开）}$$
直接用 $10^{-20}$ 更方便：$\sqrt{1.993}\approx1.412$，$\sqrt{10^{-20}}=10^{-10}$，相乘即得。

**Sanity check（批判性判断力）：** 石墨烯 C–C 键长的公认值是 **0.142 nm**，我们算出 0.141 nm，误差 <1%。✔ 而且这个值落在"原子尺度 ~1 Å"的预期区间内。

---

### 5.4 数密度与平均间距的完整算例（related questions 的典型题型）

**题：水的密度 $\rho=1000\ \mathrm{kg\,m^{-3}}$，$M(\mathrm{H_2O})=18\ \mathrm{g\,mol^{-1}}$。求 (a) 每立方米水中的分子数；(b) 水分子间的平均距离。**

**(a) 数密度**

先统一单位：$\rho=1000\ \mathrm{kg\,m^{-3}}=1000\times10^{3}\ \mathrm{g\,m^{-3}}=1\times10^{6}\ \mathrm{g\,m^{-3}}$

$$n=\frac{\rho N_{A}}{M}=\frac{1\times10^{6}\ \mathrm{g\,m^{-3}}\times6.02\times10^{23}\ \mathrm{mol^{-1}}}{18\ \mathrm{g\,mol^{-1}}}$$

$$=\frac{6.02\times10^{29}}{18}=3.34\times10^{28}\ \mathrm{m^{-3}}$$

**(b) 平均间距**

$$d=n^{-1/3}=\left(3.34\times10^{28}\right)^{-1/3}$$

手算技巧：**把指数凑成 3 的倍数**——
$$3.34\times10^{28}=33.4\times10^{27}$$
$$\left(33.4\times10^{27}\right)^{1/3}=\sqrt[3]{33.4}\times10^{9}=3.22\times10^{9}\ \mathrm{m^{-1}}$$
$$d=\frac{1}{3.22\times10^{9}}=3.1\times10^{-10}\ \mathrm{m}=3.1\ \text{Å}$$

**Sanity check：** 水分子直径约 2.8 Å，液态水中分子几乎"贴在一起"，所以平均间距 ~3 Å 完全合理。✔

---

## 六、易错点 / 重点难点

1. **减去负指数忘记变号。** $10^{13}/10^{-12}=10^{13-(-12)}=10^{25}$，**不是** $10^{1}$。slides 特意把 $13-(-12)=25$ 写出来就是为了防这个错。
2. **系数与指数混着算。** $(3\times10^{13})\times(2\times10^{-12})$：**系数相乘 $3\times2=6$，指数相加 $13+(-12)=1$**，得 $6\times10^{1}$。不要把 3 和 13 搅在一起。
3. **"相乘指数相加" vs "幂的幂指数相乘" 搞混。** $a^{3}\times a^{3}=a^{6}$，但 $(a^{3})^{3}=a^{9}$。
4. **不同底数硬合并。** $a^{2}b^{4}$ 不能化简；只能对**同一底数**分别合并指数。
5. **加法当成指数律。** $10^{3}+10^{4}\neq10^{7}$（正确：$=1000+10000=11000=1.1\times10^{4}$）。
6. **带幂次单位换算时忘记整体取幂。** $1\ \mathrm{m^{3}}=10^{6}\ \mathrm{cm^{3}}$（不是 $10^{2}$）；$1\ \mathrm{m^{2}}=10^{4}\ \mathrm{cm^{2}}$。
7. **词头叠加。** 从 kg 转 exagram 必须**先把 kilo 化掉变成 g**，再套 exa。没有 "kilo-exa-gram"。slides 把这两题标为 "tricky" 正是因为这个。
8. **忘了做数量级检查。** 直径 100 m 的湖不可能重 50 kg。**每算完一题，都要问一句"这个数在现实里是什么感觉？"**
9. **搞混"元素由什么决定"。** 元素 = **质子数 $Z$**；中子数变 → **同位素**，元素不变。质量数 $A=Z+N$。
10. **算原子质量时把电子算进去。** 电子只有质子的 $1/1800$，本课一律**忽略**。
11. **"原子质量" 与 "一个原子的质量" 混为一谈。** $M=12\ \mathrm{g\,mol^{-1}}$ 是**一摩尔**碳的质量；**一个**碳原子是 $M/N_A=2\times10^{-23}\ \mathrm{g}$。差了 $N_A$ 倍。
12. **数密度公式里的单位不一致。** $n=\rho N_A/M$ 中，$\rho$ 必须是 $\mathrm{g\,m^{-3}}$（若给的是 $\mathrm{kg\,m^{-3}}$ 要 $\times10^{3}$），否则结果差 1000 倍。
13. **求平均间距时忘了开立方根。** $d=n^{-1/3}$，不是 $1/n$。（$1/n$ 是体积，量纲是 m³。**用量纲检查：$[\mathrm{m^{-3}}]^{-1/3}=[\mathrm{m}]$ ✔**）
14. **手算开立方时指数不是 3 的倍数。** 先把 $3.34\times10^{28}$ 改写成 $33.4\times10^{27}$ 再开。同理开平方要先凑成偶数指数。
15. **查密度不看条件。** 密度随**温度和压力**变化，查表值通常是 **STP** 下的。气体尤其敏感。
16. **石墨烯问题里数错原子数。** 六边形顶点上的原子是被 **3 个**六边形共享的，每个六边形只"拥有" $6\times\frac13=2$ 个原子，不是 6 个。矩形单元同理要小心边界原子的归属。
17. **忽略比表面积的质量单位。** 题目给的是 $\mathrm{m^{2}\,mg^{-1}}$，而摩尔质量是 $\mathrm{g\,mol^{-1}}$，必须先把原子质量换成 **mg**。
18. **不画图就动手算。** slides 明确说 "Try drawing a picture – it is a great skill to develop"。石墨烯题、油膜题不画图基本做不出来。
19. **不确定性意识缺失。** 给出预测时要说明不确定性来源：输入数据不准，还是模型过度简化。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| quantitative science | 定量科学 | 用数字和公式而非仅用文字描述自然现象的科学。 |
| critical faculty | 批判性判断力 | 算完结果后判断其数量级是否符合常识的习惯。 |
| order of magnitude | 数量级 | 一个量最接近的 10 的整数次幂，用于粗略估算与检查。 |
| unit conversion | 单位换算 | 乘以值为 1 的换算因子，把量表达成另一套单位。 |
| dimensional analysis | 量纲分析 | 通过检查单位是否约掉得到正确量纲，来验证公式/计算。 |
| conversion factor | 换算因子 | 形如 $\frac{1000\ \mathrm{m}}{1\ \mathrm{km}}$ 的等于 1 的分数。 |
| mathematical model | 数学模型 | 用方程近似描述真实系统，以预测未来或反推过去。 |
| uncertainty | 不确定性 | 预测结果的误差范围，来自输入数据误差或模型简化。 |
| scientific notation | 科学记数法 | 把数写成 $a\times10^{n}$ 的形式，便于表示极大/极小的数。 |
| E-notation | E 记号 | 计算器/计算机写法，`1E13` 即 $1\times10^{13}$。 |
| index / power (pl. indices) | 指数 / 幂 | $b^{n}$ 中的上标 $n$。 |
| base (number) | 底数 | $b^{n}$ 中的 $b$；只有底数相同的幂才能合并指数。 |
| law of indices | 指数律 | $b^mb^n=b^{m+n}$、$b^m/b^n=b^{m-n}$、$(b^m)^n=b^{mn}$ 等规则。 |
| square root | 平方根 | $\sqrt a=a^{1/2}$。 |
| cube root | 立方根 | $\sqrt[3]a=a^{1/3}$。 |
| fractional index | 分数指数 | 用 $a^{m/n}$ 表示根式，运算规则与整数指数完全相同。 |
| SI prefix | SI 词头 | kilo、nano 等代表 10 的整数次幂的前缀。 |
| tera (T) | 太 | $10^{12}$。 |
| exa (E) | 艾 | $10^{18}$；注意与 E 记号的 E 区分。 |
| atto (a) | 阿 | $10^{-18}$。 |
| micro (μ) | 微 | $10^{-6}$。 |
| nano (n) | 纳 | $10^{-9}$。 |
| Ångström (Å) | 埃 | $10^{-10}$ m，原子尺度的常用长度单位。 |
| atom | 原子 | 由原子核（质子+中子）与核外电子组成的物质基本单元。 |
| proton | 质子 | 带正电的核子，质量 $1.66\times10^{-27}$ kg；其数目决定元素种类。 |
| neutron | 中子 | 不带电的核子，质量同质子；作为"胶水"帮助束缚原子核。 |
| electron | 电子 | 带负电，质量 $9.1\times10^{-31}$ kg，约为质子的 1/1800，算质量时可忽略。 |
| nucleus | 原子核 | 原子中心，由质子与中子构成，集中了几乎全部质量。 |
| shell model | 壳层模型 | 把电子看作分布在一层层壳层上的原子简化模型。 |
| periodic table | 元素周期表 | 按原子序数排列元素、体现周期性性质的表。 |
| atomic number ($Z$) | 原子序数 | 质子数；唯一决定元素身份。 |
| mass number ($A$) | 质量数 | 质子数 + 中子数，即核子总数。 |
| isotope | 同位素 | 质子数相同、中子数不同的同一元素的不同核素。 |
| atomic mass unit (u / dalton) | 原子质量单位 | $1.66\times10^{-24}$ g，等于 $1/N_A$ 克。 |
| Avogadro's number ($N_A$) | 阿伏伽德罗常数 | $6.02\times10^{23}$，1 克氢中的氢原子数，也是 1 摩尔的粒子数。 |
| mole | 摩尔 | 含 $6.02\times10^{23}$ 个基本单元的物质量单位。 |
| atomic mass | 原子质量（摩尔质量） | 1 摩尔某元素的质量 $[\mathrm{g\,mol^{-1}}]$，数值等于质量数 $A$。 |
| molecular mass | 分子质量 | 1 摩尔某物质的质量，等于分子内各原子质量数之和。 |
| density ($\rho$) | 密度 | $\rho=m/V$，随温度与压力变化，查表值通常为 STP 值。 |
| STP (standard temperature and pressure) | 标准温压 | 密度等物性表所依据的参考状态。 |
| number density ($n$) | 数密度 | 单位体积内的原子/分子数，$n=\rho N_A/M$ $[\mathrm{m^{-3}}]$。 |
| average interatomic spacing | 原子间平均距离 | $d=n^{-1/3}$，由每个原子独占体积开立方得到。 |
| specific surface area (SSA) | 比表面积 | 单位质量物质所具有的表面积 $[\mathrm{m^2\,g^{-1}}]$。 |
| graphene | 石墨烯 | 单原子层厚的二维碳材料，碳原子构成蜂窝状六边形晶格。 |
| honeycomb lattice | 蜂窝晶格 | 石墨烯的六边形网格结构，每个碳与 3 个近邻成键。 |
| bond length ($t$) | 键长 | 相邻两原子核间距离；石墨烯中约 0.142 nm。 |
| unit cell | 晶胞 / 重复单元 | 晶格中可平移铺满整个结构的最小重复区域。 |
| monolayer | 单分子层 | 只有一个分子厚的薄膜，是油膜法测分子尺寸的关键假设。 |
| ionic bonding | 离子键 | （本周不讲，见 Chemistry of the Earth 及附录 C2）靠正负离子静电吸引成键。 |
| covalent bonding | 共价键 | （本周不讲）靠共用电子对成键。 |
| numeracy | 数值能力 | 雇主最看重的基础技能之一：能正确地用数字做事。 |
