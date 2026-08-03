# Week 2 — 分数与因式分解 / 热与能量的等价性 / 净初级生产力（The Greens We Eat）

> 课程：EART11200 *The Natural Scientist's Toolkit* → Introductory Maths for Natural Scientists（Michaelmas Term，共 5 周）
> 本周材料：Lecture `EART11200_M&P_W2_1/2/3`；Practical `eart11200_week02_answers`（Problem 1.3 及其 related problems）
> 注：本周两个 `*-transcript.md`（Lecture 与 Practical 各一份，均为 `EART11200 - 04-Oct-transcript.md`）**内容为空**，仅含文件头与日期戳，无任何实际转写文字。因此「课堂补充」一节只能基于 slides 的口头提示语（"we will calculate it later…"、"Try to guess…"、"why?" 等）以及 practical 答案册中的讲解性文字来重建。

---

## 一、本周主题

本周是 5 周课程的**第 2 周**，主题是**"我们吃掉的绿色植物"（The Greens We Eat）**——一个典型的 Fermi 式（数量级估算式）自然科学问题：*人类一年吃掉了地球全部植物年生长量的百分之几？*

为了解这个问题，本周把三块内容串起来：

1. **数学工具**（W2_1）：分数（fractions）、括号展开（expanding brackets）、因式分解（factorising）。这是继 Week 1 之后的第二组"基本工具"，本周问题里大量出现分数（碳质量分数、饮食结构分数）。
2. **物理概念**（W2_2）：热与能量的等价性（heat–energy equivalence）、焦耳实验、卡路里与焦耳的换算、比热容公式 $E = mC\Delta T$。这是把"生物量"翻译成"能量"的桥梁。
3. **地球系统背景**（W2_3）：初级生产力（primary production）、光合作用与化能合成、GPP 与 NPP 的区别、NDVI 遥感估算方法。这提供了问题中 14.7 PgC/yr 这个数字的来源与意义。

在整门课的位置：Week 1 打下单位、量纲、有效数字、数量级的基础；Week 2 在此之上加入**分数运算 + 代数变形（因式分解）**，并首次把"化学（摩尔、化学计量）+ 物理（能量）+ 地球科学（NPP）"合成为一个真实的多步估算问题。本周课后作业还预告了 **transposing formulae（公式变形/移项）**，以及 related problem 4 里已经用到的**对数（logarithms）与指数方程（indicial equation）**——这两项是后续几周的内容，本周只是"提前露面"。

---

## 二、核心概念

### 2.1 分数 (Fractions)

**定义**：分数是"整体的一部分"的表达方式。例如三分之一（⅓）个苹果、八分之一（⅛）个蛋糕。

写作 $\dfrac{\text{numerator}}{\text{denominator}}$（分子/分母）：

- **denominator（分母）**：整体被平均分成的份数。例如整个蛋糕被切成 8 等份 → 分母是 8。
- **numerator（分子）**：我们取的份数。

**三类写法：**

| 类型 | 英文 | 条件 | 例子 |
|---|---|---|---|
| 真分数 | proper fraction | numerator < denominator | $\frac{2}{7}$ |
| 假分数 | improper fraction | numerator > denominator | $\frac{7}{3}$ |
| 带分数 | mixed fraction | 整数 + 真分数 | $2\tfrac{1}{3}$ |

假分数与带分数可以互相转换：$\frac{7}{3} = 2\tfrac{1}{3}$，因为 $7 \div 3 = 2$ 余 $1$。反向：$2\tfrac{1}{3} = \frac{2\times 3 + 1}{3} = \frac{7}{3}$。

**百分数 (percentage)**：1% 就是整体的百分之一，即 $\frac{1}{100}$。所以

$$10\% = \frac{10}{100} = \frac{1}{10}, \qquad 4\% = \frac{4}{100} = 0.04 .$$

> ⚠️ 本周主问题的最终答案 $f \approx 0.0425$ 就是"约 4%"——**分数、小数、百分数三种表达要能自由切换**，这正是把 fractions 放在本周开头的原因。

### 2.2 分数的合并 (Combining fractions)

slides 上这一页标题为 "Combining fractions"，正文在转成 md 时丢失。以下是标准规则（本周 practical 全部用到）：

**(a) 加减 —— 必须先通分（common denominator）**

$$\frac{a}{b} \pm \frac{c}{d} = \frac{ad \pm cb}{bd}$$

例：$\frac{1}{4} + \frac{1}{5} = \frac{5}{20} + \frac{4}{20} = \frac{9}{20}$。

> 这正是 related problem 2 中检验饮食比例是否加起来等于 1 的做法：
> $\frac{1}{4} + \frac{1}{5} + \frac{1}{5} + \frac{7}{20} = \frac{5}{20} + \frac{4}{20} + \frac{4}{20} + \frac{7}{20} = \frac{20}{20} = 1$ ✓

**(b) 乘法 —— 分子乘分子，分母乘分母**

$$\frac{a}{b} \times \frac{c}{d} = \frac{ac}{bd}$$

**(c) 除法 —— 乘以倒数（reciprocal）**

$$\frac{a}{b} \div \frac{c}{d} = \frac{a}{b} \times \frac{d}{c} = \frac{ad}{bc}$$

**(d) 约分（cancelling）**：分子分母同乘/同除一个非零数，分数值不变：$\frac{72}{180} = \frac{72 \div 36}{180 \div 36} = \frac{2}{5} = 0.4$。

### 2.3 括号展开 (Expanding brackets)

规则：括号外的每一项要乘进括号内的**每一项**（分配律 distributive law）。

slides 上的三个例子（完整过程见第三节）：

- $4(x + xy - 3) = 4x + 4xy - 12$
- $x\left(x^2 + xy + \frac{2}{x}\right) = x^3 + x^2 y + 2$ ← 注意 $x \cdot \frac{2}{x} = 2$，这是分数与代数结合的关键
- $(x - y)(x + z) = x^2 - yx + zx - yz = x^2 + x(z - y) - yz$

两个括号相乘时，第一个括号的每一项都要乘第二个括号的每一项（"FOIL"：First, Outer, Inner, Last）。

### 2.4 因式分解 (Factorising)

**定义**：括号展开的**逆过程**（the reverse process of expanding brackets）。核心动作是**找公因式（common factor）**。

**(a) 提公因式**

- $42y + 7 = 7(6y + 1)$ ——公因式是 7
- $6p^2 - 3p = 3p(2p - 1)$ ——公因式是 $3p$（数字公因式 3 与字母公因式 $p$ 都要提）

**(b) 二次三项式分解**

- $r^2 + 3r + 2 = (r + 2)(r + 1)$
- $4v^2 + 12v - 40 = 4(v^2 + 3v - 10) = 4(v + 5)(v - 2)$ ← 先提数字公因式 4，剩下的括号再分解

**(c) 一般法则**

对于 $ar^2 + br + c = (dr + e)(fr + g)$，展开右边得 $dfr^2 + (dg + ef)r + eg$，对比系数：

$$d \times f = a, \qquad e \times g = c, \qquad d\times g + e \times f = b$$

即：找两个数使它们**乘积配 $a$ 和 $c$**、**交叉相乘之和配 $b$**。

> slides 结尾强调："Make sure you are comfortable with fractions and brackets/factorising, we will be using them in this week's problems. If you find this difficult, ask one of the members of staff during the practical session."

### 2.5 热与能量的等价性 (Heat and Energy equivalence)

**历史背景**：**James Prescott Joule**（1818–1888），出生于 Salford 的物理学家兼酿酒商。1845 年论文导出了**能量守恒定律 (law of conservation of energy)**。

- 焦耳做了大量实验，证明**电、化学、热三类现象在数量上是等价的**，且各种能量形式可以互相转换。
- 名言（slides 原文）：*"Believing that the power to destroy belongs to The Creator alone I affirm … that any theory which, when carried out, demands the annihilation of force, is necessarily erroneous."*（"相信毁灭的力量只属于造物主，我断言……任何要求'力'被消灭的理论必然是错的。"）——这句话是能量守恒的哲学表述：能量不能被创造也不能被消灭。
- 为纪念这项工作，**SI 能量单位命名为 joule (J)**。

**焦耳实验装置 (Joule's apparatus)** 的原理：一个下落的重物把**重力势能 (potential energy)** $= mgh$ 转换为水的**粘性加热 (viscous heating)** $= mC\,\mathrm{d}T$。

$$mgh \;\longrightarrow\; m C \Delta T$$

这是本周最重要的一个"翻译"：**机械能 ↔ 热能**。

### 2.6 卡路里 vs 卡路里 (calorie vs Calorie)

这是本周极易混淆的一对，**大小写决定了 1000 倍差别**：

- **calorie (cal)**，小写 c：把 **1 gram** 水升温 **1 °C** 所需的热量。
- **Calorie (kcal)**，大写 C：把 **1 kilogram** 水升温 **1 °C** 所需的热量 = 1000 cal。**食物标签上的"卡路里"就是这个**。
- 换算：**1 calorie = 4.18 J**（practical 中用 4.2 J，估算够用）。

这个**热含量 (heat content)** 可以用来驱动我们的活动、保暖，或转换成另一种能量形式（例如电）。

> 所以"一个人一天吃 2500 kcal"= 2500 大卡 = $2500 \times 10^3$ cal = $2.5\times10^6$ cal。

### 2.7 比热容与升温所需能量

**每种物质有自己的热容 (each substance has its own heat capacity)**。

$$\boxed{E = m\,C\,\Delta T}$$

- $E$：能量 / 热量（J）
- $m$：质量（kg）
- $C$：**比热容 (specific heat capacity)**，单位 $\mathrm{J\,kg^{-1}\,K^{-1}}$；水的 $C = 4180\ \mathrm{J\,kg^{-1}\,K^{-1}}$
- $\Delta T$（slides 写作 $\delta T$ 或 $\mathrm{d}T$）：**温度变化量**

> ⚠️ **$\Delta T$ 是温度的"变化"，不是温度本身**。因为是差值，用 °C 或 K 数值相同（1 °C 的温差 = 1 K 的温差），所以 $C$ 用 K⁻¹ 而 $\Delta T$ 用 °C 也不会出错。

### 2.8 初级生产 (Primary production)

**定义**：**Primary production 是生物体在有机化合物中产生化学能的过程**。主要能量来源是阳光，但极小一部分由**岩石营养生物 (lithotrophic organisms)** 利用无机分子的化学能驱动。

无论能量来源如何，这些能量都被用来**从简单无机化合物（如 CO₂ 和 H₂O）合成复杂有机分子**。

**两条简化方程：**

$$\text{光合作用 (photosynthesis)：}\quad \mathrm{CO_2 + H_2O + light \longrightarrow CH_2O + O_2}$$

$$\text{化能合成 (chemosynthesis，一种形式)：}\quad \mathrm{CO_2 + O_2 + 4H_2S \longrightarrow CH_2O + 4S + 3H_2O}$$

两种情况的终点都是**还原态碳水化合物 $\mathrm{CH_2O}$**，典型分子是 **葡萄糖 glucose ($\mathrm{C_6H_{12}O_6}$)** 或其他糖类。这些相对简单的分子随后可以进一步合成更复杂的分子——蛋白质、复杂碳水化合物、脂类 (lipids)、核酸 (nucleic acids)——或者被**呼吸 (respired)** 掉以做**功（能量）**。

**其它要点：**

- Primary production = 从大气或水体的 CO₂ 生产有机化合物。
- 可通过**光合作用**（以光为能源）或**化能合成**（以化合物的氧化还原为能源）进行。
- **地球上几乎所有生命都直接或间接依赖初级生产**。负责初级生产的生物叫 **primary producers（初级生产者）** 或 **autotrophs（自养生物）**，构成**食物链的底端 (base of the food chain)**。
- **陆地生态区**的初级生产者是**植物 (plants)**；**水生生态区**是**藻类 (algae)**。

### 2.9 GPP ≠ NPP（本周被 slides 单独列为 "Important point"）

- **GPP (Gross Primary Productivity，总初级生产力)**：**不扣除**任何损失的总固碳/总能量固定量。
- **NPP (Net Primary Productivity，净初级生产力)**：**扣除了细胞呼吸 (cellular respiration) 等过程损失后**的净值。

$$\mathrm{NPP = GPP - R_{autotroph}}$$

slides 原文："Primary production is either as net or gross, the former accounting for losses to processes such as cellular respiration, the latter not."

**NPP 的直观理解**：*"Think of it as the amount of Carbon that goes into plant growth / biomass each year."*——每年**进入植物生长/生物量的碳量**，单位 $\mathrm{g(C)\,yr^{-1}}$。

**slides 提出的思考题**："It does not equal the mass of the plants growing per year… why?"

> **答案**：NPP 的单位是**碳的质量**（gC），而植物本身除了碳还含有大量的**氢、氧**（以及氮、磷、硫等）。以葡萄糖 $\mathrm{C_6H_{12}O_6}$ 为例，碳只占质量的 **40%**。所以每年生成的**生物量总质量**要比 NPP 大得多（约 $1/0.4 = 2.5$ 倍）。**这正是本周主问题第 3 步必须做的换算。**
> 另外 NPP 通常指**干重 (dry biomass)** 相关的碳，而活植物含大量水分，也是"不等于植物增重"的一个原因。

### 2.10 如何全球估算初级生产力？——NDVI

**思路链条**：完全被植物覆盖的表面会**吸收 (absorb)** 不同波长的可见光辐射 → 吸收量可以与**光合速率 (photosynthesis rate)** 建立关系 → 光合速率可用于估算 NPP。

**NDVI (Normalized Difference Vegetation Index，归一化植被指数)**：

$$\boxed{\mathrm{NDVI} = \frac{\mathrm{NIR} - \mathrm{red}}{\mathrm{NIR} + \mathrm{red}}}$$

- $\mathrm{NIR}$：近红外波段 (near-infrared) 的反射率
- $\mathrm{red}$：红光波段的反射率

**物理原理**：植物**吸收红光**用于光合作用（叶绿素的吸收峰在红光和蓝光），但**不吸收近红外**（叶片内部结构强烈反射 NIR）。所以对植被覆盖区，$\mathrm{NIR} > \mathrm{red}$，**NDVI 为正**；植被越茂密 NDVI 越大。裸土、水面、云的 NDVI 接近 0 或为负。

- slides 提到 2011 年 8 月的全球 NPP 图，以及 MODIS 卫星 14 年的视频（见 Wikipedia "Primary production" 条目）。
- **思考题**："It is more difficult to estimate sub-surface primary production, why?" → 因为海洋中的浮游植物 (phytoplankton) 分布在水面以下一定深度（真光层 euphotic zone），卫星只能"看到"表层几个光学深度内的信号；水体本身吸收和散射光；还要考虑混合层深度、垂直叶绿素剖面等，无法直接由表面反射率读出。

### 2.11 生物量 = 能量

**核心链条（本周问题的骨架）：**

$$\text{阳光} \xrightarrow{\text{光合}} \text{碳被固定 (NPP)} \to \text{生物量 (biomass)} \xrightarrow{\text{燃烧/呼吸}} \text{能量}$$

- 燃烧时释放储存的碳/能量。**燃料的热含量 (heat content of the fuel)** 单位是 **Joules per gram (J g⁻¹)**。
- 本周采用 **干生物量的能量含量 = $1.6\times10^4\ \mathrm{J\,g^{-1}}$**（即 16 kJ/g ≈ 3.8 kcal/g，与食物标签上碳水化合物约 4 kcal/g 一致 ✓）。
- slides 抛出的两个大问题：
  - **Grown Biomass = Energy for power generation?**（生物量能不能当发电燃料？）
  - **Grown Biomass = Energy for food?**（生物量作为食物够不够？）
  - "What fraction of Earth's plants need to be burned each year to meet energy demands? Try to guess, and we will calculate it later…"（→ related problem 3，答案约 85%）
  - "Can we feed the world?" / "Energy – do we need fossil fuels?"
- slides 给出 BBC 新闻链接（2014, science-environment-28409704）：牛肉的资源需求约是猪肉/禽肉/蛋/奶的 **28 倍**——这直接对应 related problem 2 中"1 J 牛肉需要 8 J 谷物"的设定。

---

## 三、公式与图表

### 3.1 代数工具汇总

| 公式 | 说明 |
|---|---|
| $\frac{a}{b} \pm \frac{c}{d} = \frac{ad \pm cb}{bd}$ | 分数加减，先通分 |
| $\frac{a}{b}\times\frac{c}{d} = \frac{ac}{bd}$ | 分数乘法 |
| $\frac{a}{b}\div\frac{c}{d} = \frac{ad}{bc}$ | 分数除法 = 乘倒数 |
| $a(b+c) = ab + ac$ | 分配律，括号展开 |
| $(x-y)(x+z) = x^2 - yx + zx - yz$ | 双括号展开 |
| $ar^2+br+c=(dr+e)(fr+g)$，其中 $df=a$、$eg=c$、$dg+ef=b$ | 二次因式分解通法 |

**slides 上展开的完整过程：**

1. $4(x + xy - 3)$
 $= 4\cdot x + 4\cdot xy + 4\cdot(-3)$
 $= 4x + 4xy - 12$

2. $x\left(x^2 + xy + \dfrac{2}{x}\right)$
 $= x\cdot x^2 + x\cdot xy + x\cdot \dfrac{2}{x}$
 $= x^3 + x^2y + 2$
 （最后一项：$x \times \frac{2}{x} = \frac{2x}{x} = 2$，$x$ 约掉）

3. $(x-y)(x+z)$
 $= x\cdot x + x\cdot z - y\cdot x - y\cdot z$
 $= x^2 + xz - yx - yz$
 $= x^2 + x(z-y) - yz$（把含 $x$ 的两项提出公因式 $x$）

**slides 上因式分解的完整过程：**

1. $42y + 7$：$42 = 7\times 6$，公因式 7 → $7(6y+1)$
2. $6p^2 - 3p$：$6p^2 = 3p\cdot 2p$，$3p = 3p\cdot 1$，公因式 $3p$ → $3p(2p-1)$
3. $r^2+3r+2$：需要两数乘积 = 2、和 = 3 → 2 与 1 → $(r+2)(r+1)$
4. $4v^2+12v-40$：
 先提公因式 4：$= 4(v^2+3v-10)$
 再分解括号：两数乘积 = $-10$、和 = $+3$ → $+5$ 与 $-2$
 $= 4(v+5)(v-2)$

### 3.2 能量公式

$$\boxed{E_p = mgh}\qquad \text{重力势能 (gravitational potential energy)}$$

- $m$：质量（kg）；$g$：重力加速度 $\approx 9.81\ \mathrm{m\,s^{-2}}$；$h$：高度（m）
- 单位检验：$\mathrm{kg\cdot m\,s^{-2}\cdot m = kg\,m^2\,s^{-2} = J}$ ✓

$$\boxed{E = m\,C\,\Delta T}\qquad \text{加热所需能量}$$

- 单位检验：$\mathrm{kg \cdot J\,kg^{-1}K^{-1} \cdot K = J}$ ✓
- 变形（transposing formulae，本周作业主题）：$\Delta T = \dfrac{E}{mC}$，$\;C = \dfrac{E}{m\Delta T}$，$\;m = \dfrac{E}{C\Delta T}$

$$\boxed{\mathrm{NDVI} = \frac{\mathrm{NIR}-\mathrm{red}}{\mathrm{NIR}+\mathrm{red}}}$$

- 取值范围 $[-1, 1]$；植被为正值。

### 3.3 常数与单位换算表（slides 明确给出）

| 项目 | 数值 |
|---|---|
| 1 calorie（小写） | 4.18 J（practical 中取 4.2 J） |
| 1 Calorie = 1 kcal | 1000 calorie ≈ 4180 J ≈ 4.18 kJ |
| 水的比热容 $C$ | $4180\ \mathrm{J\,kg^{-1}\,K^{-1}}$ |
| 水的密度 $\rho$ | $\approx 1000\ \mathrm{kg\,m^{-3}}$ |
| 1 kWh | $1000 \times 60 \times 60 = 3.6\times10^6\ \mathrm{J} = 3.6\ \mathrm{MJ}$ |
| 1 m³ 水 | 1000 L ≈ 220（英）加仑 |
| 干生物量能量含量 | $1.6\times10^4\ \mathrm{J\,g^{-1}}$ |
| 全球 NPP（2008 前后） | $14.7\ \mathrm{PgC\,yr^{-1}} = 14.7\times10^{15}\ \mathrm{gC\,yr^{-1}}$ |
| 2008 年世界人口 | $6.7\times10^9$ |
| 人均日食物摄入 | ≈ 2500 kcal |
| 化石燃料年供能（2008） | $\approx 5\times10^{20}\ \mathrm{J}$ |

> **P（Peta）= $10^{15}$**。Pg = petagram = $10^{15}$ g = $10^{12}$ kg = $10^9$ t = 1 Gt（十亿吨）。所以 14.7 PgC/yr = 每年 147 亿吨碳。

### 3.4 分子量计算图（slides Figure 1.2）

**葡萄糖 $\mathrm{C_6H_{12}O_6}$ 的分子量 (molecular mass)** 由各元素原子质量加总：

$$M(\mathrm{C_6H_{12}O_6}) = \underbrace{6\times 12}_{\text{C}} + \underbrace{12\times 1}_{\text{H}} + \underbrace{6\times 16}_{\text{O}} = 72 + 12 + 96 = 180\ \mathrm{g\,mol^{-1}}$$

原子量取整数近似：C = 12，H = 1，O = 16，N = 14，P = 31，S = 32。

### 3.5 例题一：焦耳实验（slides W2_2）

> **题目**：绳上有 1 kg 的质量块，离地 1.0 m 高。
> (a) 有多少重力势能（用焦耳表示）？
> (b) 若质量块落地并驱动水中的桨叶（水的质量为 0.5 kg），水温会升高多少？（水的热容为 4180 J 每 kg 每 °C）

**(a) 势能**

$$E_p = mgh = 1.0\ \mathrm{kg} \times 9.81\ \mathrm{m\,s^{-2}} \times 1.0\ \mathrm{m} = 9.81\ \mathrm{J}$$

（若取 $g \approx 10$，则约 10 J。）

**(b) 温升**

假设所有势能都转化为水的热能（能量守恒）：

$$E_p = m_{\text{water}} C \Delta T \;\Longrightarrow\; \Delta T = \frac{E_p}{m_{\text{water}}\,C}$$

$$\Delta T = \frac{9.81\ \mathrm{J}}{0.5\ \mathrm{kg} \times 4180\ \mathrm{J\,kg^{-1}\,K^{-1}}} = \frac{9.81}{2090} = 4.69\times10^{-3}\ \mathrm{K}$$

即约 **0.005 °C**——**极其微小**。

> **这就是焦耳实验为什么困难**：把 1 kg 的重物从 1 m 高落下，只能把半公斤水加热不到千分之五度。焦耳必须使用极其灵敏的温度计、重复多次下落、并小心排除环境热交换，才能测出这个效应。**这也说明"热"是一种"廉价而大量"的能量形式，机械能转成热很容易，反过来很难。**

### 3.6 例题二：一缸洗澡水的能量与成本（slides W2_2）

> **题目设定**：洗澡水温 $T \approx 40$–$45\ ^\circ\mathrm{C}$，即从室温加热的 $\delta T = 25\ ^\circ\mathrm{C}$；体积 $V \approx 140$ 升 ≈ 30 英制加仑。

**第 1 步：由体积求质量**

$$m = \rho V = 1000\ \mathrm{kg\,m^{-3}} \times 0.140\ \mathrm{m^3} = 140\ \mathrm{kg}$$

（140 L = 0.140 m³，因为 1 m³ = 1000 L）

**第 2 步：算能量**

$$E = m C \Delta T = \rho V C \Delta T = 1000 \times 0.140 \times 4180 \times 25$$
$$= 140 \times 4180 \times 25 = 140 \times 104500 = 1.463\times10^{7}\ \mathrm{J} \approx 14.6\ \mathrm{MJ}$$

**第 3 步：换算成 kWh**

$$\frac{1.463\times10^7\ \mathrm{J}}{3.6\times10^6\ \mathrm{J\,(kWh)^{-1}}} = 4.06\ \mathrm{kWh} \approx 4\ \mathrm{kWh}$$

**第 4 步：成本（slides 给出）**

| 项目 | 成本 | 隐含单价 |
|---|---|---|
| 水费 (Water cost) | 28 p | — |
| 用电加热 Heat (electricity) | 50 p | ≈ 12.3 p/kWh |
| 用燃气加热 Heat (gas) | 16 p | ≈ 3.9 p/kWh |

> **结论**：燃气加热比电加热便宜约 3 倍；而水本身的钱（28p）比燃气加热的钱（16p）还贵。这是一个"把物理量转成日常经济量"的典型练习。

---

## 四、课堂补充

**本周两份 transcript 文件（Lecture 与 Practical 目录下的 `EART11200 - 04-Oct-transcript.md`）均为空文件**——只含 YAML 头（title / source / type）与一行 `'EART11200 - 04-Oct', automated transcript / 01/08/2026`，**没有任何转写内容**。因此无法提取"老师口头说了什么"。

以下是从 slides 与 practical 答案册中可辨认出的**课堂互动/口头提示痕迹**，作为替代记录：

1. **"Try to guess, and we will calculate it later…"**（W2_3）——老师在讲到"每年要烧掉地球植物的百分之几才能满足人类能源需求"时，先让学生**猜**，再在 practical 里算。这是典型的 Fermi 估算教学法：**先建立直觉，再验证**。（答案：约 **85%**，远超大多数人的直觉。）

2. **"It does not equal the mass of the plants growing per year… why?"**（W2_3，GPP ≠ NPP 那一页）——这是一个课堂提问点。答案见 §2.9：NPP 只算**碳**的质量，而生物量还含 H、O 等；碳只占葡萄糖质量的 40%。

3. **"It is more difficult to estimate sub-surface primary production, why?" / "How do you think we estimate NPP globally?"**（W2_3）——引导学生自己想到遥感/NDVI。

4. **"Discuss this with and how you will use it with your group."**（practical 1.3）——**人均每天吃多少能量这个数字是要学生自己估计并小组讨论的**，答案册给出 2500 kcal 作为参考值。这说明本周的教学重点之一是：**在缺数据时敢于做合理假设，并说明假设是什么**。

5. **"Make sure you are comfortable with fractions and brackets/factorising… If you find this difficult, ask one of the members of staff during the practical session."**（W2_1 结尾）——老师明确说本周问题会大量用到分数与因式分解，遇到困难要在 practical 上问。

6. **Practical 的推荐顺序**（W2_3 最后一页）：
 - **先做 supplementary material（补充材料）**
 - **再尝试 main problem（主问题）**
 - **然后做 related questions（相关题）**
 - **课后一周内在 Blackboard 上做 practice assessments**
 - 老师强调："**you do need to try these assessments to show engagement, but marks are not counted.**"（必须做以体现参与度，但**不计入成绩**。）

7. **对数是"提前露面"的内容**：practical related problem 4 的答案里明确写着 *"You will need to have done logarithms to do this part. **Leave if you are uncomfortable: we will come back to it later.**"*——说明第 4 题是**选做/超前**内容，后续周会正式讲对数。

8. **关于"我们稍后会更详细讲能量"**：practical 1.3.1 Notes 写 *"You will also need to at least have some idea what energy is and that it is measured in joules or calories. **We will cover it in more detail later though.**"*——本周对能量只要求"够用"的理解。

---

## 五、Practical 要点

### 5.1 目的

Practical Problem **1.3 "The greens we eat"**（属于 *Problem Solving 1: First Quarter Warm-Ups*）。

答案册 §1.3.1 Notes 明确指出这道题的训练目标：

> *"This is a good problem containing elements of **moles, stoichiometry, fractions and unit conversions**."*

即：**摩尔、化学计量、分数、单位换算**四项能力的综合演练，外加对"能量"的初步认识。

### 5.2 主问题（Problem 1.3）完整解法

> **题目**：净初级生产力是每年从 CO₂ 转化为含碳分子的元素碳的量，为 **14.7 PgC/yr**（Peta gram carbon per year）。若干生物量的能量含量为 $1.6\times10^4\ \mathrm{J\,g^{-1}}$，那么 **2008 年人类吃掉了地球全年植物生长量的百分之几？**（2008 年世界人口 $6.7\times10^9$）

**解题策略**：分别算出「分子」= 人类年食物能量消耗，「分母」= NPP 对应的年生物量能量，然后相除。

---

**Step 1 — 人均每天的能量摄入（单位换算）**

假设：一个人平均每天吃约 **2500 kcal**（这是需要学生自己估计的量）。

$$2500\ \mathrm{kcal} = 2500\times10^3\ \mathrm{cal}$$

$$2500\times10^3\ \mathrm{cal} \times 4.2\ \mathrm{J\,cal^{-1}} = 1.05\times10^7\ \mathrm{J\,day^{-1}\,person^{-1}}$$

> 关键点：**先把大写 Calorie(kcal) 换成小写 calorie，再乘 4.2 J/cal**。少走一步就会差 1000 倍。

---

**Step 2 — 全球人类年食物能量消耗**

$$E_{\text{human}} = 1.05\times10^7\ \frac{\mathrm{J}}{\cancel{\mathrm{day}}\cdot\cancel{\mathrm{person}}} \times 6.7\times10^9\ \cancel{\mathrm{people}} \times 365\ \frac{\cancel{\mathrm{days}}}{\mathrm{year}}$$

$$= 1.05\times 6.7 \times 365 \times 10^{16} = 2.568\times10^{19} \approx \boxed{2.6\times10^{19}\ \mathrm{J\,yr^{-1}}}$$

> 注意答案册用**单位约分（斜杠划掉）**的写法明确显示 day 和 person 被消掉，只剩 J yr⁻¹。**这是本课强调的做法：让单位自己告诉你算对没有。**

---

**Step 3 — 由 NPP（碳）求生物量总质量（关键的分数步骤）**

NPP $= 14.7\times10^{15}\ \mathrm{gC\,yr^{-1}}$。

答案册的原话：*"If we assume glucose is the biomass being made (a good approximation) then $14.7\times10^{15}$ gC of carbon in glucose is being made, **but glucose contains oxygen and hydrogen as well**. So now the question turns to calculating what the mass of glucose would be if there were $14.7\times10^{15}$ gC in the glucose."*

**碳的质量分数**：

$$f_C = \frac{\text{Total mass of carbon in one mole}}{\text{Total mass of carbon} + \text{oxygen} + \text{hydrogen in one mole}}$$

$$f_C = \frac{6\times12\ \mathrm{g\,mol^{-1}}}{6\times12 + 6\times16 + 12\times1\ \mathrm{g\,mol^{-1}}} = \frac{72}{180} = 0.4\ \mathrm{g(carbon)\,g^{-1}(biomass)}$$

**生物量总质量 = NPP ÷ 碳质量分数**：

$$m_{\text{biomass}} = \frac{14.7\times10^{15}\ \mathrm{g(carbon)}}{0.4\ \mathrm{g(carbon)\,g^{-1}(biomass)}} = 3.675\times10^{16} \approx \boxed{3.67\times10^{16}\ \mathrm{g\ biomass}}$$

> **为什么是除不是乘**：碳只占生物量的 40%，所以生物量比碳质量**大** 2.5 倍。单位约分也证实：$\frac{\mathrm{g(C)}}{\mathrm{g(C)/g(bio)}} = \mathrm{g(bio)}$ ✓。**这是本题最容易出错的一步。**

---

**Step 4 — 生物量对应的能量**

$$E_{\text{NPP}} = 1.6\times10^4\ \mathrm{J\,g^{-1}} \times 3.67\times10^{16}\ \mathrm{g} = 5.88\times10^{20}\ \mathrm{J\,yr^{-1}}$$

---

**Step 5 — 求分数 $f$**

$$f = \frac{E_{\text{human}}}{E_{\text{NPP}}} = \frac{2.6\times10^{19}}{5.88\times10^{20}} \approx 0.0425$$

$$\boxed{f \approx 0.043 \;\approx\; 4\%}$$

**结论**：2008 年人类**直接**吃掉了地球全年净初级生产量的**约 4%**。

---

### 5.3 Related Problem 1 — 用更精确的生物量化学式

> **题目**：典型新鲜光合合成的干生物量的近似化学组成为 $\mathrm{H_{2960}O_{1480}C_{1480}N_{160}P_{18}S_{10}}$（下标表示各元素原子的相对个数）。若用这个更精确的表示代替 $\mathrm{C_6H_{12}O_6}$，重算分数 $f$。

**答案册注**：*"This is done in exactly the same way as the first problem except that the fraction of biomass that is carbon by mass is different."*——**方法完全一样，只是碳的质量分数变了**。

**碳质量分数**：

分子（碳）：$1480 \times 12 = 17760$

分母（全部）：
- H：$2960 \times 1 = 2960$
- O：$1480 \times 16 = 23680$
- C：$1480 \times 12 = 17760$
- N：$160 \times 14 = 2240$
- P：$18 \times 31 = 558$
- S：$10 \times 32 = 320$
- **合计** $= 2960 + 23680 + 17760 + 2240 + 558 + 320 = 47518\ \mathrm{g\,mol^{-1}}$

$$f_C = \frac{17760}{47518} = 0.374 \approx 0.37\ \mathrm{g\,g^{-1}}$$

**生物量总质量**：

$$m_{\text{biomass}} = \frac{14.7\times10^{15}}{0.374} = 3.93\times10^{16}\ \mathrm{g\ (biomass)}$$

**能量**：

$$E_{\text{NPP}} = 1.6\times10^4\ \mathrm{J\,g^{-1}} \times 3.93\times10^{16}\ \mathrm{g} = 6.29\times10^{20}\ \mathrm{J}$$

**分数**：

$$f = \frac{2.6\times10^{19}}{6.29\times10^{20}} \approx 0.0413 \approx \boxed{4\%}$$

> **重要教训**：从 0.40 换到 0.37 只让答案从 4.25% 变成 4.13%——**结论的数量级和"约 4%"的判断完全不变**。这说明在这类估算中，**用葡萄糖近似生物量是完全合理的**，而真正的不确定性来自"人均 2500 kcal"这类假设。

---

### 5.4 Related Problem 2 — 考虑动物性食品的能量放大

> **题目**：生产动物性食品（牛肉、蛋、鱼、奶）需要生产植物作为饲料。生产 1 J 的牛肉需要约 **8 J** 的谷物能量；禽肉约 **3 J**。这是两个极端。生产 1 J 其他动物性食品大致需要 **5 J** 的植物物质。假设人们平均的饮食构成是 **1/4 禽肉、1/5 牛肉、1/5 其他、7/20 蔬菜**，那么分数 $f$ 是多少？
> （提示：先考虑全是禽肉的饮食需要多少能量，用上面算出的人类总能耗。）

**先检查比例是否合理**（分数通分练习）：

$$\frac14 + \frac15 + \frac15 + \frac{7}{20} = \frac{5}{20} + \frac{4}{20} + \frac{4}{20} + \frac{7}{20} = \frac{20}{20} = 1 \;✓$$

**建立表达式**：人类需要的食物能量仍是 $2.6\times10^{19}$ J/yr，但要**生产**这些食物所需的**植物能量**是：

$$E_{\text{plant}} = 3\times\frac14\times 2.6\times10^{19} + 8\times\frac15\times2.6\times10^{19} + 5\times\frac15\times2.6\times10^{19} + 1\times\frac{7}{20}\times2.6\times10^{19}$$

提取公因子 $2.6\times10^{19}$（**因式分解在实战中的应用**）：

$$E_{\text{plant}} = 2.6\times10^{19}\left(\frac{3}{4} + \frac{8}{5} + \frac{5}{5} + \frac{7}{20}\right)$$

通分到 20：

$$\frac{3}{4} + \frac{8}{5} + 1 + \frac{7}{20} = \frac{15}{20} + \frac{32}{20} + \frac{20}{20} + \frac{7}{20} = \frac{74}{20} = 3.7$$

$$E_{\text{plant}} = 2.6\times10^{19} \times 3.7 = \boxed{9.62\times10^{19}\ \mathrm{J\,yr^{-1}}}$$

**分数**（分母用主问题的 $5.88\times10^{20}$ J/yr）：

$$f = \frac{9.62\times10^{19}}{5.88\times10^{20}} \approx \boxed{0.16 \;=\; 16\%}$$

> **结论极其重要**：一旦考虑食物链的能量损失（营养级效率），人类的"植物足迹"从 4% 跳到 **16%——放大了近 4 倍**。这就是 slides 引用的 BBC 报道（牛肉资源需求是禽肉/猪肉/蛋/奶的 28 倍）的量化版本。**少吃牛肉对地球的影响是可以用一行分数算出来的。**

---

### 5.5 Related Problem 3 — 用生物量替代全部化石燃料？

> **题目**：如果我们把现在（2008）从化石燃料获得的全部能量（约 $5\times10^{20}$ J）改由生物量提供，大约需要消耗地球当前 NPP 的多大比例？这个答案告诉你"用生物量全面替代化石燃料"是否明智？会带来什么生态问题？

**计算**（答案册："Just take the fraction of energy consumed globally to npp"）：

$$f = \frac{5\times10^{20}\ \mathrm{J}}{5.88\times10^{20}\ \mathrm{J}} \approx \boxed{0.85 \;=\; 85\%}$$

**讨论（本题的重点是定性结论）：**

- 需要烧掉地球**全部**净初级生产量的 **85%** 才能替代化石燃料——**这在物理上几乎不可能，在生态上是灾难性的**。
- 再加上人类吃掉的 4%（或考虑食物链后的 16%），总需求已经**超过或逼近 100%**——地球的全部植物生产量都不够用。
- **预期的生态问题**：
 - 所有其他异养生物（动物、真菌、分解者）将无食物可用 → **食物网崩溃、大规模物种灭绝**
 - 土壤有机质无法补充 → **土壤退化、侵蚀加剧**
 - 为增产而大规模砍伐/开垦 → **栖息地丧失、生物多样性丧失**
 - 燃烧生物量释放 CO₂，若采伐速度超过再生长速度则**并非碳中和**
 - 大量占用土地和淡水，与粮食生产竞争
- **这正是 slides 开头让学生"猜"的那个问题的答案**。大多数人会猜远低于 85%。

---

### 5.6 Related Problem 4 — 人口增长到吃光 NPP 需要多久（对数/指数方程）

> **题目**：如果人口继续以约 **2%/yr** 增长，人类将在哪一年吃掉相当于地球当前 NPP 的量？
> 答案册注：*"You will need to have done logarithms to do this part. Leave if you are uncomfortable: we will come back to it later."*

**Step 1 — 一个人一年消耗多少能量**

$$1.05\times10^7\ \frac{\mathrm{J}}{\cancel{\mathrm{day}}} \times 365\ \frac{\cancel{\mathrm{days}}}{\mathrm{year}} = 3.83\times10^{9}\ \mathrm{J\,yr^{-1}\,person^{-1}}$$

（答案册写 $\approx 3.8\times10^9$）

**Step 2 — 需要多少人才能吃光 NPP**

$$N = \frac{5.88\times10^{20}\ \mathrm{J\,yr^{-1}}}{3.8\times10^{9}\ \mathrm{J\,yr^{-1}\,person^{-1}}} = 1.53\times10^{11}\ \mathrm{people}$$

（即 **1530 亿人**）

**Step 3 — 建立指数增长模型**

答案册的逐步说明：*"If the population grows at 2% per year then after the first year it will be 1.02 times greater. After the second year it will be $1.02\times1.02$ or $1.02^2$ times greater than the initial value. After $x$ years it will be $1.02^x$ times greater than the initial value."*

$$P(x) = P_0 \times 1.02^{\,x}$$

**Step 4 — 写出 indicial equation（指数方程）并解**

$$(6.7\times10^9)\times 1.02^{\,x} = 1.53\times10^{11}$$

$$1.02^{\,x} = \frac{1.53\times10^{11}}{6.7\times10^{9}} = 22.84$$

两边取自然对数（把指数"拿下来"）：

$$\ln\left(1.02^{\,x}\right) = \ln(22.84)$$

用对数法则 $\ln(a^x) = x\ln a$：

$$x \ln 1.02 = \ln 22.84$$

$$x = \frac{\ln 22.84}{\ln 1.02} = \frac{3.128}{0.019803} \approx \boxed{158\ \text{years}}$$

**结论**：从 2008 年起约 158 年，即**约公元 2166 年**，人口将增长到能吃光地球全部 NPP 的规模。

> **这道题引入了两个后续内容**：
> - **indicial equation（指数方程）**：未知数在指数位置的方程，必须用对数解。
> - **对数法则** $\ln(a^x) = x\ln a$。
> 参考资料：*Foundation Maths* support booklet 的 Logarithms 章节。

---

### 5.7 作业与阅读（Homework and reading，答案册 §1.3.4）

**背景阅读：**
- 复习 booklet **Appendix C**
- 阅读 booklet **Appendix D**（关于能量单位 joule）
- **Croft and Davison (2006)**, "Transposing formulae" 一章；**或** *Foundation Maths Support Pack* 的 §2.7, 2.8, 2.9, 2.10, 2.11, 2.12

**Blackboard 上本周的 assessment：**
- **'Transposing formulae'**（公式变形/移项）
- **'The greens we eat'**

**老师提示**：如果觉得吃力，就把 supplementary material 做完，**带着答案来下节课和老师讨论**。

---

## 六、易错点 / 重点难点

1. **calorie vs Calorie（小写 vs 大写）差 1000 倍。**
 食物标签上的 "2500 Calories" = 2500 **kcal** = $2.5\times10^6$ cal。必须先换成小写 cal 再乘 4.2 J/cal。忘了这一步答案会小 1000 倍。

2. **NPP 是"碳"的质量，不是"生物量"的质量。**
 必须**除以**碳的质量分数（0.4）才能得到生物量。常见错误是**乘** 0.4（方向反了，答案差 6.25 倍），或者干脆跳过这一步（答案差 2.5 倍）。判断方向的小技巧：碳只是生物量的一部分，所以生物量一定**更大** → 用除。

3. **GPP ≠ NPP。**
 NPP 已扣除自养呼吸损失。题目里给的 14.7 PgC/yr 是 **N**PP。

4. **$\Delta T$ 是温度差，不是温度值。**
 洗澡水题里 $T = 40\text{–}45\ ^\circ$C 但 $\delta T = 25\ ^\circ$C（因为自来水本来约 15–20 °C）。直接把 40 代进公式是常见错误。

5. **比热容公式中质量必须用 kg。**
 $C = 4180\ \mathrm{J\,kg^{-1}\,K^{-1}}$ 的单位里是 kg。若体积以升给出，要先乘密度换算：$140\ \mathrm{L} = 0.140\ \mathrm{m^3} \to 140\ \mathrm{kg}$。

6. **能量含量的单位是 J g⁻¹（每克），不是每千克。**
 $1.6\times10^4$ J g⁻¹ 要配 g 为单位的生物量质量。NPP 给的是 gC，正好匹配——但如果中途换成 kg 就会差 1000 倍。

7. **单位约分（unit cancellation）是最好的检错工具。**
 答案册特意把 day、person、days 划掉演示。养成习惯：写出每个数字的完整单位，看最后剩下的单位是不是你要的。

8. **食物链的能量放大效应容易被忽略。**
 主问题算的 4% 是**直接摄入**；考虑到牛肉需要 8 倍谷物、禽肉 3 倍后，实际植物需求是 **16%**。两个数字回答的是不同的问题，别混。

9. **提公因式后括号内还能再分解。**
 $4v^2+12v-40 = 4(v^2+3v-10)$ **不是最终答案**，还要 $= 4(v+5)(v-2)$。

10. **$x \cdot \frac{2}{x} = 2$**，展开括号时含分数项要记得约分，不要写成 $\frac{2x}{x}$ 就停下。

11. **指数方程必须两边同时取对数**，且要记得 $\ln(a^x) = x\ln a$。直接"除以 1.02"是错的。

12. **有效数字与近似**：本周所有计算都是**数量级估算**，答案写 "about 4%"、"about 85%" 就够。答案册里 4.25% 与 4.13% 的差别不必纠结——但**过程中不要提前四舍五入**。

13. **NDVI 为什么是正的**：因为植物**吸收红光、反射近红外**，所以 NIR > red，分子为正。要能说出物理原因，不要死记公式。

14. **Blackboard assessment 不计分但必须做**（体现 engagement）。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| fraction | 分数 | 表示整体的一部分，写作 numerator/denominator |
| numerator | 分子 | 分数线上方的数，表示取了多少份 |
| denominator | 分母 | 分数线下方的数，表示整体被分成多少份 |
| proper fraction | 真分数 | 分子小于分母，如 2/7 |
| improper fraction | 假分数 | 分子大于分母，如 7/3 |
| mixed fraction | 带分数 | 整数加真分数，如 2⅓ |
| percentage (%) | 百分数 | 以 1/100 为单位表示的分数 |
| expanding brackets | 展开括号 | 用分配律把括号外的项乘进括号内每一项 |
| factorising | 因式分解 | 展开括号的逆过程，核心是找公因式 |
| common factor | 公因式 | 各项都含有的因子，可提到括号外 |
| transposing formulae | 公式变形/移项 | 把公式改写成求解另一个变量的形式，本周作业主题 |
| indicial equation | 指数方程 | 未知数出现在指数位置的方程，需用对数求解 |
| logarithm | 对数 | 指数运算的逆运算，满足 ln(aˣ) = x ln a |
| Joule (J) | 焦耳 | SI 能量单位，纪念 J. P. Joule |
| law of conservation of energy | 能量守恒定律 | 能量不能被创造或消灭，只能在形式间转换 |
| potential energy | 势能 | 由位置决定的能量，重力势能 = mgh |
| viscous heating | 粘性加热 | 流体内摩擦把机械能转化为热的过程（焦耳实验的机制） |
| calorie (cal) | 卡（小卡） | 使 1 g 水升温 1 °C 所需热量，= 4.18 J |
| Calorie (kcal) | 千卡（大卡） | 使 1 kg 水升温 1 °C 所需热量，= 1000 cal，食物标签用的单位 |
| heat content | 热含量 | 单位质量燃料/食物释放的能量，单位 J g⁻¹ |
| specific heat capacity (C) | 比热容 | 使单位质量物质升温 1 K 所需能量，水为 4180 J kg⁻¹ K⁻¹ |
| kWh (kilowatt-hour) | 千瓦时（度） | 能量单位，1 kWh = 3.6 MJ |
| primary production | 初级生产 | 生物体把无机碳合成有机化合物、储存化学能的过程 |
| primary producer / autotroph | 初级生产者 / 自养生物 | 进行初级生产的生物，食物链的基础；陆地是植物，水体是藻类 |
| photosynthesis | 光合作用 | 以光为能源：CO₂ + H₂O + light → CH₂O + O₂ |
| chemosynthesis | 化能合成 | 以化合物氧化还原为能源：CO₂ + O₂ + 4H₂S → CH₂O + 4S + 3H₂O |
| lithotrophic organism | 岩石营养生物 | 利用无机分子化学能的生物，驱动极小部分初级生产 |
| cellular respiration | 细胞呼吸 | 氧化有机物释放能量的过程，是 GPP 转 NPP 时被扣除的损失 |
| GPP (Gross Primary Productivity) | 总初级生产力 | 未扣除呼吸损失的固碳/固能总量 |
| NPP (Net Primary Productivity) | 净初级生产力 | GPP 减去自养呼吸后的净值，可理解为每年进入植物生长/生物量的碳量 |
| biomass | 生物量 | 生物体的质量，本周指干生物量，能量含量 1.6×10⁴ J g⁻¹ |
| glucose (C₆H₁₂O₆) | 葡萄糖 | 典型的光合产物，分子量 180，碳质量分数 0.4 |
| carbohydrate (CH₂O) | 碳水化合物 | 光合/化能合成的还原态碳产物通式 |
| lipid | 脂类 | 由简单糖类进一步合成的复杂有机分子之一 |
| nucleic acid | 核酸 | 由简单糖类进一步合成的复杂有机分子之一 |
| molecular mass | 分子量 | 各原子相对原子质量之和，如 C₆H₁₂O₆ = 6×12+12×1+6×16 = 180 |
| mole | 摩尔 | 物质的量单位，1 mol 葡萄糖质量为 180 g |
| stoichiometry | 化学计量 | 由化学式/方程式推算各元素质量比例的方法 |
| NDVI (Normalized Difference Vegetation Index) | 归一化植被指数 | (NIR − red)/(NIR + red)，用卫星遥感估算植被与 NPP |
| NIR (near-infrared) | 近红外 | 植物强烈反射的波段，NDVI 的分子正项 |
| MODIS | 中分辨率成像光谱仪 | NASA 卫星传感器，用于全球 NPP 遥感监测 |
| Peta (P) | 拍（10¹⁵） | SI 词头，1 PgC = 10¹⁵ g 碳 = 10 亿吨碳 |
| food chain | 食物链 | 能量在营养级间传递的路径，每级都有大量损失 |
| dry biomass | 干生物量 | 去除水分后的生物量，能量含量以此计 |
| fodder | 饲料 | 为生产动物性食品而种植的植物 |
