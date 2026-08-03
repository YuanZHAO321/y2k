# Week 6 — 化学平衡与热力学 (Chemical Equilibrium & Thermodynamics)：从吉布斯自由能到相图

> **本周材料**
> - Lecture：`ChemEarth L6 - Chemical equilibrium.pdf/.md`（含 Practical 6 的引言幻灯片）
> - Transcript：`EART11200 - 06-Nov-transcript.md`
> - Practical：`ChemEarth Practical 6 - Chemical Equilibrium - Feedback.pdf/.md`

---

## 一、本周主题

本周（Week 6）进入 **化学平衡 (chemical equilibrium)** 与 **热力学 (thermodynamics)**：先建立"什么是平衡""能量如何决定反应方向"的基本框架（内能 U、熵 S、焓 H、吉布斯自由能 G），然后把这套框架**翻译成地质学家最常用的工具——相图 (phase diagram)**，用来预测在给定的温度 (T)、压力 (P)、成分 (X) 下，一个体系中哪些**相 (phase)** 是稳定的。

在 11 周主线中的位置：
- Week 1–5（元素周期表、地球分层与元素分配、碳循环/有机化学、氧化还原）回答的是"地球**由什么构成**、元素**去了哪里**"；
- **Week 6 是方法论上的转折点**：从"描述成分"转向"**预测反应方向与稳定状态**"。它给出后续几乎所有内容的底层逻辑；
- 直接下游：Week 7 的 **熔融 (melting) 与稀土元素**（本周的 Di–An 共熔相图正是下周部分熔融/结晶分异的基础）、以及后面水—岩反应、矿物溶解沉淀的平衡处理。
- 老师明确说："这周和下周的 practical 会花很多时间在相图上"——本周只是"very basic introduction"。

**老师的定调（transcript 反复强调）**：
> "I don't expect you at all to remember any of these equations… What we're going to do in the practical is I'll tell you the equation, tell you the variables. You can put those things into the equation and calculate the answer."

即：**不要求背公式、不要求会推导**，但**必须会把给定的公式和数据代进去算出答案，并会读/画相图**。

---

## 二、核心概念

### 2.1 平衡 (Equilibrium) —— 我们为什么在意它

**定义**：**Equilibrium 是一种不随时间变化的物质状态 (a state of matter that does not change with time)。**

老师在课堂上补了一个更直观的说法：平衡是**物质为了匹配周围的条件而做出的组织方式**（"the organization of matter to match the conditions that surround it"）。也就是说，给定 T、P、可用氧量、可用水量等条件，体系会"安顿"到某个特定状态。

**为什么地球科学家在意**：因为我们想**预测**。具体的四类预测：
1. **预测一块岩石在什么温度会熔融**（火成岩成因、地幔熔融）；
2. **预测熔体冷却时矿物结晶的顺序**（岩浆分异、Bowen 反应序列的热力学根据）；
3. **预测岩石变质时会生成什么新矿物**（变质岩：埋深 → P、T 升高 → 矿物组合改变）；
4. **预测风化过程中岩石如何溶解**、天然水的成分、以及水中会沉淀出哪些矿物（水—岩相互作用）。

### 2.2 热力学 (Thermodynamics) 的语义与能量类型

- **Thermo** = 热 (heat)；**Dynamics** = 运动 (movement)。
- 定义：**研究能量（热）及能量变化的学科**；热力学用来描述**体系如何响应其环境的变化**。
- 老师澄清：名字里是"热"，但**本质是"能量"**——"it's not really heat, it's energy"。

**能量 (energy) vs 热 (heat)**：
- **热是能量的一种形式**，即**热能 (thermal energy)**；
- 热来源于**物质内部分子和原子的随机运动 (random motions)**；
- 原子还把能量**储存在化学键里**，这叫**化学能 (chemical energy)**；
- 所以热力学里有两类基础能量：**化学能 + 热能**。

**能量单位：焦耳 (JOULE, J)**
- 定义：当 **1 牛顿 (newton)** 的力沿物体运动方向作用于物体、使其移动 **1 米** 时传递给该物体的能量。
- 牛顿的定义：使 1 kg 质量沿受力方向以 1 m s⁻² 加速所需的力。（老师说：**牛顿的定义不用背**，放在那里只是备查。）
- 量纲：$1\ \text{J} = 1\ \text{kg}\,\text{m}^2\,\text{s}^{-2} = 1\ \text{N}\,\text{m}$
- 冷知识（老师很喜欢讲）：**James Prescott Joule (1818–1889)**，物理学家兼**酿酒师 (brewer)**，出生于**Salford**（曼彻斯特隔壁）——"a very local man… he had a good pedigree"。

### 2.3 体系 (System) 与其边界

**SYSTEM 的定义**：**我们正在考虑的那一部分宇宙 (the part of the universe that we are considering)。**

老师强调：**system 就是你自己决定要研究的东西，可大可小**。课上给的例子：
- 一个**熔岩湖 (lava lake)**——想知道它冷却凝固时会发生什么；
- 一个**花岗岩岩基 (granite pluton)**——像地下的熔岩湖；
- **单个矿物颗粒 (a single mineral grain)**，只有几毫克——想知道改变 P、T 时它怎么变；
- 一个**沉积层 (sedimentary deposit)**、**海洋 (the ocean)**、**地核 (the Earth's core)**、**大气 (the atmosphere)**、甚至**地球—月球体系 (Earth–Moon system)**。

**三类体系（按与环境交换能量/物质的能力划分）**：

| 体系类型 | 能量交换 | 物质（质量）交换 | 课堂比喻 |
|---|---|---|---|
| **孤立体系 (Isolated system)** | ✗ 不能 | ✗ 不能 | 被真空层包住并密封的盒子；想加热加不进去，想加压也加不了 |
| **封闭体系 (Closed system)** | ✓ 能 | ✗ 不能 | 密封但可导热的盒子：可以加热、可以挤压（改变能量），但物质进不去出不来 |
| **开放体系 (Open system)** | ✓ 能 | ✓ 能 | 盒子侧面/顶上有洞，或有**半透膜 (permeable membrane)**，原子可以进出，能量也可以进出 |

> 老师：**"It's really important to understand the system we're looking at and to know if it's open or closed."**

### 2.4 体系的变量：广延量 vs 强度量

**两类可变性质 (variable properties)**：

- **广延变量 (Extensive variables)：取决于体系的大小 (depend on the size of the system)**
  - **质量 (Mass)**、**体积 (Volume)**、**能量 (Energy)**
  - 直觉：大盒子和小盒子相比，质量不同、体积不同、能量也不同（因为能量与物质的量有关）。
- **强度变量 (Intensive variables)：不取决于体系的大小 (do not depend on the size of the system)**
  - **温度 (Temperature)**、**压力 (Pressure)**、**黏度 (Viscosity)**、**密度 (Density = Mass/Volume)**
  - 直觉：改变一个盒子的温度，并没有改变盒子里物质的量。

> 老师明确说 **"Don't worry too much about these terms"**——不必死记 extensive/intensive 这两个词，但读文献时会遇到。
> **但注意**：Gibbs 相律里的"自由度 f"定义中出现的正是 **intensive variables**，所以还是要理解这个概念。

### 2.5 理想气体定律与开尔文温标

**理想气体定律 (Ideal Gas Law)** 是"广延量与强度量之间关系"的一个范例：

$$PV = nRT$$

| 符号 | 含义 | 单位 |
|---|---|---|
| $P$ | 压力 (pressure) | Pa / bar |
| $V$ | 体积 (volume) | m³ |
| $n$ | 物质的量 / 摩尔数 (number of moles) | mol |
| $R$ | 气体常数 (Gas Constant) | **8.314 J mol⁻¹ K⁻¹** |
| $T$ | **绝对温度，必须用开尔文 (Kelvin)** | K |

> ⚠️ 讲义上写的是 "R = Gas Constant (8.314 J mol⁻¹)"，**这是打字遗漏**，完整单位应为 **J mol⁻¹ K⁻¹**。

**用法示例（老师课上给的）**：取**固定体积**的气体，改变温度 → 因为 $n$ 和 $R$ 不变、$V$ 固定，所以 $P$ 必须随之改变。
> ⚠️ **老师在这里口误了**：他说 "if the temperature goes up, the pressure goes down"，随即自己纠正 "I might have said that backwards, sorry"。
> **正确结论**：定容定量时 $P \propto T$，**温度升高 → 压力升高**（这正是火山、岩浆房超压、Mount St. Helens 1980/1982 喷发所用的幻灯片图示背后的物理）。

**开尔文温标 (Kelvin scale) 与绝对零度 (Absolute Zero)**：
- 依据来自理想气体定律：**理想气体在 $T = 0$ 时 $V = 0$**，所以 0 K 是可能达到的最低温度。
- **每一"度"的大小与摄氏度相同**（水的冰点到沸点之间同样划分 100 份）。
- 换算：$T(\text{K}) = T(°\text{C}) + 273.15$（老师说日常记 **273** 即可，"that number 273 is one that you have to sort of keep in your head"）。
- 对照：
  - 摄氏 (Celsius)：水冰点 0 °C，沸点 100 °C
  - 华氏 (Fahrenheit)：冰点 32 °F，沸点 212 °F
  - 开尔文 (Kelvin)：冰点 **273.15 K**，沸点 **373.15 K**
- 命名自 **William Thomson, Lord Kelvin (1824–1907)**。

### 2.6 热力学第一定律 (First Law)

**内容：能量守恒原理 (conservation of energy)**——在化学反应和物理变化中，能量既不被创造也不被消灭。

**内能 (Internal energy, U)**：对一个矿物而言，是**储存在化学键中的势能 + 原子振动的动能**之和。
（注：McSween 教材用 **E** 表示内能，本课用 **U**。）

体系内能的微小变化 $dU$ = 从环境流入体系的热 $dQ$ + 对体系做的机械功 $dW$：

$$dU = dQ + dW$$

在地质体系中，最重要的功来自**压力与体积的变化**：

$$dW = -PdV$$

代入得到**第一定律的常用形式**：

$$\boxed{dU = dQ - PdV}$$

> ⚠️ **讲义 PDF 转 md 时把负号 OCR 丢了**（显示成 "- dU = dQ PdV"），正确写法是 $dU = dQ - PdV$。

**关于符号 $d$（老师专门解释）**：
> "in this equation we've got this little d… d represents a very, very small amount. If you haven't come to calculus yet, you will do next semester. **What you need to think of it is you need to read it as a small change**… **That d just represents a small change. It's not part of the equation.**"

即：$dU$ 读作"内能的一个微小变化"，$d$ **不是**一个变量、**不能**约掉。

**$-PdV$ 的物理意义**：体积被压缩（$dV<0$）时 $-PdV>0$，即外界对体系做正功、内能增加；体系膨胀（$dV>0$）时体系对外做功、内能减少。

### 2.7 热力学第二定律 (Second Law) 与熵 (Entropy)

**引出问题（课堂"红蓝盒子"实验）**：
一个盒子中间有隔板 (partition)，左边是蓝色分子（气体 A），右边是红色分子（气体 B）——状态 **A**。抽掉隔板后，两种气体自发混合、均匀分布在整个空间——状态 **B**。

关键观察：
> **"But if we just sat and watched this system, it's never going to rearrange itself back to situation A. Once it's mixed, it's mixed."**

这叫**不可逆变化 (irreversible change)**。**第一定律完全无法解释这种"方向性"**——因为混合前后能量没变。所以我们需要一个**描述方向感 (sense of direction)** 的函数。

**熵 (ENTROPY, 符号 S)**：
- 描述**自发的、不可逆的变化的方向**；
- 是**能量在体系中如何分布 (how the energy is distributed in a system)** 的量度；
- 也可以理解为体系**随机性/无序度 (randomness or disorder)** 的量度；
- **单位：J mol⁻¹ K⁻¹**。

**第二定律的三条要点**：
1. 自然界偏好**自发变化 (spontaneous change)**；
2. 变化的方向是朝向**体系及其环境的总熵增大**；
3. 数学表述：

$$\boxed{dS \geq \frac{dQ}{T}}$$

（可逆过程取等号，不可逆过程取">"。老师："I'm not going to go into why that's the case. Let's just accept that it is."）

**熵的定量直觉：H₂O 三态的摩尔熵 (molar entropy)**

| 相 | 摩尔熵 S / J mol⁻¹ K⁻¹ |
|---|---|
| **水蒸气 (steam, gas)** | **188.8** |
| **液态水 (water, liquid)** | **70.0** |
| **冰 (ice, solid)** | **44.7** |

解读：熵与水分子在每种状态下的**运动量**直接相关。**固 → 液 → 气，无序度递增、熵递增**。老师顺带复习了：1 mol 水 = 18 g（H = 1，O = 16，2×1 + 16 = 18）。

> 课堂上老师把冰的值口述成 "45"，幻灯片精确值是 **44.7**，以幻灯片为准。

### 2.8 合并第一、第二定律 → 热力学基本方程

- 第一定律：$dU = dQ - PdV$
- 第二定律：$dS \geq dQ/T$，即 $dQ \leq TdS$

合并：

$$dU \leq TdS - PdV$$

**关键的地质学假设**：
> 因为**大多数地质过程发生得非常缓慢 (occur very slowly)**，微小的变化非常接近**可逆 (reversible)**，所以我们可以取等号：

$$\boxed{dU = TdS - PdV} \qquad \textbf{热力学基本方程 (Fundamental Equation of Thermodynamics)}$$

| 符号 | 含义 |
|---|---|
| $U$ | 内能 (internal energy) |
| $T$ | 温度（**开尔文**） |
| $S$ | 熵 (entropy) |
| $P$ | 压力 (pressure) |
| $V$ | 体积 (volume) |

> **这个"缓慢 ⇒ 近可逆 ⇒ 可用平衡热力学"的论证是整个地球化学热力学能成立的前提**，值得单独记住。

### 2.9 焓 (Enthalpy, H)

**定义**：一个物质的**总热含量 (total heat content)**。单位：**焦耳 (J)**。

$$\boxed{H = U + PV}$$

**关键性质**：**若变化在恒压下发生**，则焓变等于体系得失的热量：

$$dH = dQ \qquad (\text{constant } P)$$

> 这是为什么焓可以**用量热法 (calorimetry) 直接测量**——在恒压下测热量即得 $\Delta H$。地球化学数据表中的 $\Delta H^{o}_{f}$（生成焓）就是这么来的。

### 2.10 吉布斯自由能 (Gibbs Free Energy, G) —— 本周的核心

**定义**：在**恒温恒压 (constant T and P)** 条件下，体系**可用于做有用功的能量 (the amount of energy available for a system to do useful work)**。

$$\boxed{G = H - TS}$$

对于体系的一个变化：

$$\boxed{\Delta G = \Delta H - T\Delta S}$$

**吉布斯自由能定义了平衡与自发变化的判据，因此 $G$ 决定了自发变化朝哪个方向进行：**

| 条件 | 含义 |
|---|---|
| $\Delta G = 0$ | 体系处于**化学平衡 (chemical equilibrium)**；坐着看它也不会变 |
| $\Delta G < 0$（负） | 有能量可用于产生**自发变化 (spontaneous change)**；**反应会正向进行** |
| $\Delta G > 0$（正） | 反应**不会**按写出的方向进行（**逆反应**才是自发的） |

> **核心口诀：A chemical reaction will proceed in the direction of LOWER Gibbs free energy.**
> 化学反应总是朝**吉布斯自由能降低**的方向进行。

**命名自 Josiah Willard Gibbs (1839–1903)。**

**另一个重要关系式**（由 $G = H - TS = U + PV - TS$ 微分并代入 $dU = TdS - PdV$ 得到）：

$$\boxed{dG = VdP - SdT}$$

这个式子的地质意义极其重要：
- **等温时** ($dT = 0$)：$dG = VdP$ —— **摩尔体积 $V$ 小的相，其 $G$ 随压力上升得慢，因此高压下更稳定**。这就是"高压favours致密相"（石墨→金刚石、方解石→文石、石英→柯石英→斯石英）的热力学根源。
- **等压时** ($dP = 0$)：$dG = -SdT$ —— **熵 $S$ 大的相，其 $G$ 随温度上升下降得快，因此高温下更稳定**。这就是"高温favours高熵相"（固→液、低温石英→高温方石英）的根源。

### 2.11 相 (Phase) 与相图 (Phase Diagram)

**PHASE 的定义**：
> **相是一个物理上独立的物质体，(至少在原则上) 可以从体系的其余部分中物理分离出来。**
> (A phase is a physically distinct body of matter that is — at least in principle — physically separable from the rest of the system.)

老师用"水杯里有冰、水、水蒸气"来解释"physically separable"：
- 想去掉气体 → 用真空抽走；
- 想去掉液体 → 倒出来；
- 想去掉固体 → 把冰块捡出来。
所以气、液、固各自是一个**相**。

> ⚠️ **老师专门提醒的易错点**：
> **"Don't think that we're always going to talk about gas is a phase."**
> 相不等于"三态"。这里的相是**"水蒸气"这个相、"冰"这个相、"液态水"这个相**。在矿物体系中，**每一个不同的矿物（哪怕化学式完全相同）都是一个不同的相**（例如低温石英和高温石英是两个相）。

**PHASE DIAGRAM（相图）**：
- **表示一个或多个相的稳定区域 (regions of stability)**；
- **区域 (areas / fields)** = 每个相**热力学稳定**的范围 = 给定 P、T 下体系的**平衡状态**；
- **线 (lines)** = 发生反应和/或物理变化的地方 = **相界 (phase boundary)**，线上**两侧的相同时稳定共存**；
- **点 (junction / triple point)** = 三个相同时平衡共存。

### 2.12 H₂O 相图（入门范例）

- 纵轴：压力（讲义用 **kPa**）；横轴：温度（**°C**）；
- 单位换算：$1\ \text{Pa} = 10^{-5}\ \text{bar}$；$1\ \text{kPa} = 10^{-2}\ \text{bar}$；$100\ \text{kPa} = 1\ \text{bar}$；**1 atm ≈ 101 kPa**。
- **判读（老师逐点讲解）**：
  - 在 **101 kPa（1 atm）、0 °C**：固 → 液的转变点。低于 0 °C 全是冰；升温到 0 °C 开始出现水；继续升温只剩水。
  - 在 **101 kPa、100 °C**：水沸腾，液 → 气。**恰在这个点上，液态水和水蒸气两相共存并稳定**。
  - **三相点 (Triple point)**：**只有一个点** —— **0.6 kPa、0.01 °C** —— 冰、水、水蒸气三相同时平衡共存。
- 曲线的名称：**熔化/凝固曲线 (melting / freezing curve)**、**沸腾/凝结曲线 (boiling / condensation curve)**、升华曲线。

### 2.13 同质多象 (Polymorphs) 与 SiO₂ 体系

**Polymorph（同质多象/多形体）**：**化学式完全相同、但原子排列方式不同**的矿物。字面意思是"多种形状 (multiple shapes)"。

**SiO₂ 相图（T vs P，成分处处为 SiO₂）**：
- **一个组分 (one component)**：SiO₂；
- 图上共 **7 个相**（每个不同颜色的区域一个，**包含 liquid**）；
- **6 个 SiO₂ 同质多象**：
  - **低温石英 (low quartz)** —— 低 T、低 P（也叫 α-quartz）
  - **高温石英 (high quartz)** —— 升温后由低温石英转变而来（β-quartz）
  - **鳞石英 (tridymite)** —— 低 P、高 T
  - **方石英 (cristobalite)** —— 更高 T，熔融之前的最后一个固相
  - **柯石英 (coesite)** —— 高 P
  - **斯石英 (stishovite)** —— 极高 P
  - （**liquid 是一个相，但不是矿物同质多象**——practical 里专门考这一点）
- **升温路径（低 P）**：low quartz → high quartz → tridymite → cristobalite → **liquid**
- **升压路径（低 T）**：quartz → **coesite** → **stishovite**（原子越挤越紧，密度递增）
- **地表 (P = 0) 熔点**：约 **1700 °C（实际 1713 °C）**，在 cristobalite 与 liquid 的边界上。
- 幻灯片勘误：**y 轴上标的 "1900" 应为 "1800"**（老师和讲义都提了）。

**压力单位换算（必记）**：
- 1 kbar = 1000 bar = 1000 atm
- **1 kbar ≈ 地壳中 3–4 km 深度**
- 1 GPa = 10 kbar；也常用 MPa（1 kbar = 100 MPa）

**柯石英/斯石英的地质意义（老师的 aside）**：
- 二者**最早是在美国亚利桑那州 Barringer Meteorite Crater（Meteor Crater）周围的沉积物中被自然发现的**；
- 因为撞击瞬间产生**极高压力**；
- **发现柯石英 ⇒ 该岩石至少经历过约 20,000 atm（≈20 kbar）的压力** ⇒ 是**撞击构造 (impact structure)** 的诊断性证据；
- 讲义引例：德国 Ries 撞击构造的 suevite 中的柯石英（Fazio et al., 2017, *Meteoritics & Planetary Science*, 52, 1437–1448），电子显微镜下可见石英与柯石英共存。

### 2.14 碳的相图与"动力学 vs 热力学"

**碳 (C) 相图**：四个相 —— **金刚石 (Diamond)、石墨 (Graphite)、液体 (Liquid)、气体 (Gas/vapour)**。金刚石与石墨是**碳的同质多象**。

**结构差异（老师课上补充，slides 上没有）**：
- **石墨**：**六边形的片层 (sheets of hexagons)**，**层间是很弱的键** → 片层可以互相滑动 → **非常软**；
- **金刚石**：每个碳原子都以**很强的共价键 (covalent bond)** 连到相邻碳原子 → **极难打断** → **非常硬**。

**密度与压力的关系（重点）**：
- 石墨密度 **2.27 g cm⁻³**；金刚石密度 **3.51 g cm⁻³**；
- **石墨**是低压下稳定的固相；**高压下转变为金刚石**；
- **通则：更高的压力偏好更致密的相 (Higher pressures favour the denser phase)** —— 压缩矿物时形成的新相，原子排列更紧密。老师："It sort of makes sense if you think about squashing it… that's very typical behavior in geological systems."

**动力学 (Kinetics) —— 本周最重要的概念补丁**：
- **金刚石在地表条件下并不是热力学稳定相**——按相图，地表应该是石墨；
- 我们手上还戴着钻戒，是因为 **金刚石转变为石墨的速率 (rate) 太慢，慢到实际上不发生**；
- **反应速率**这件事叫 **kinetics（动力学）**，**必须与热力学并列考虑**：
  > **"We can look at a phase diagram and say, this is the phase that should be stable. But we don't necessarily see that phase because of kinetics, because it might be slow getting there."**
- 这类"本该转变却没转变"的相叫 **亚稳相 / 非平衡相 (metastable / disequilibrium phase)**。

### 2.15 组分 (Components) 与相图的维度

**COMPONENTS 的定义**：
> **体系的组分数是描述体系中所有相的成分所需要的 *最少* 化学物种数目。**
> (the minimum number of chemical species required to describe the composition of all the phases in the system)

| 例子 | 组分数 c | 图的两个轴 | 固定的量 |
|---|---|---|---|
| **H₂O 相图** | **1**（H₂O） | T vs P | 成分 X 全图恒定 |
| **SiO₂ 相图** | **1**（SiO₂） | T vs P | 成分 X 全图恒定 (X = SiO₂) |
| **C 相图** | **1**（C） | T vs P | 成分 X 全图恒定 |
| **Anorthite–Diopside 相图** | **2**（An 与 Di） | **T vs X（成分）** | **压力恒定 (P = 0.1 MPa = 1 bar)** |

**为什么两组分图必须固定压力？**（老师课堂解释）：
> "We have to show the difference in chemical composition on the x-axis, and we show temperature on the y-axis… **We can't show pressure because it's in the third dimension. We'd have to have a three-dimensional image of it.** So we define the pressure."

即：一张二维图只能放两个变量。一组分图选 (T, P)；两组分图选 (T, X)，代价是把 P 钉死。

### 2.16 熔融的热力学 (Thermodynamics of Melting)

**核心逻辑**：在**熔点 (melting point)**，**固相与液相处于平衡**，因此：

$$\Delta G_m = 0$$

由 $\Delta G_m = \Delta H_m - T_m \Delta S_m$ 且 $\Delta G_m = 0$：

$$\boxed{\Delta H_m = T_m \Delta S_m} \quad\Longrightarrow\quad \Delta S_m = \frac{\Delta H_m}{T_m}$$

| 符号 | 含义 |
|---|---|
| $T_m$ | 熔化温度（**Kelvin**） |
| $\Delta S_m$ | 熔化的熵变 |
| $\Delta H_m$ | 熔化焓 / 熔化热 (enthalpy of melting or fusion)，**可用量热法 (calorimetry) 测得** |

**降低熔点 (Depression of melting point)**：
> **两种物质混合物的最低熔点，总是低于任一单一物质的熔点。**
> (The lowest melting point of a mixture of two substances is always lower than the melting points of the individual substances.)

**生活类比（老师给的）**：汽车**防冻液 (antifreeze)** —— 把防冻液加到水里，混合物的凝固点比纯水低。**矿物混合物同理**。

控制方程（对 $i$ 和 $j$ 两相各写一条）：

$$\ln x_i = -\frac{\Delta H_{i,m}}{R}\left(\frac{1}{T} - \frac{1}{T_{i,m}}\right)$$
$$\ln x_j = -\frac{\Delta H_{j,m}}{R}\left(\frac{1}{T} - \frac{1}{T_{j,m}}\right)$$

| 符号 | 含义 |
|---|---|
| $x_i$, $x_j$ | 混合物中 $i$、$j$ 的**摩尔分数** |
| $\Delta H_{i,m}$, $\Delta H_{j,m}$ | $i$、$j$ 的熔化焓变 |
| $R$ | 气体常数 8.314 J mol⁻¹ K⁻¹ |
| $T$ | 温度（**Kelvin**） |
| $T_{i,m}$, $T_{j,m}$ | $i$、$j$ 的**纯矿物熔点**（Kelvin） |

### 2.17 共熔点 (Eutectic) 与 Di–An 相图

把上面的方程对 diopside 和 anorthite 各画一条曲线，就得到 **Diopside–Anorthite 二元相图**：

- **辉石熔融曲线 (melting curve of diopside)**：从纯 Di 端 (x_Di = 1, T = 1391 °C) 向左下方降；
- **钙长石熔融曲线 (melting curve of anorthite)**：从纯 An 端 (x_Di = 0, T = 1553 °C) 向右下方降；
- **两条曲线相交的点 = 共熔点 (EUTECTIC)** —— 体系**熔融的最低温度**；
- **共熔点以下的温度**：全部为**固体**；
- **两条熔融曲线以上**：全部为**液体**（这两条曲线合称 **liquidus 液相线**）；
- **中间两个区域**：
  - 左侧（富 An 一侧）：**anorthite + liquid**
  - 右侧（富 Di 一侧）：**diopside + liquid**
- 底部水平的共熔温度线称 **solidus（固相线）**。

**热力学计算给出的共熔点**：$X_{Di} = 0.7$，$T = 1334\ °\text{C}$（White, *Geochemistry*）

**判读示例（讲义原例）**：考虑 80% anorthite + 20% diopside 的混合物（$X_{Di} = 0.2$）：**在 1400 °C，体系由 anorthite + liquid 组成。**

---

## 三、公式与图表

### 3.1 "THERMODYNAMICS IN A NUTSHELL" —— 讲义的公式速查表

（这张幻灯片在 Lecture 和 Practical 里各出现一次，是老师给的"crib sheet"）

$$PV = nRT \qquad \text{理想气体定律 (Ideal Gas Law)}$$
$$dU = dQ - PdV \qquad \text{热力学第一定律 (First Law)}$$
$$dS \geq \frac{dQ}{T} \qquad \text{热力学第二定律 (Second Law)}$$
$$dU = TdS - PdV \qquad \text{基本方程 (Fundamental Equation)}$$
$$dG = VdP - SdT$$
$$\Delta G = \Delta H - T\Delta S$$
$$H = U + PV \qquad G = H - TS$$

**符号总表**

| 符号 | 含义 | 备注 |
|---|---|---|
| $P$ | 压力 pressure | bar / Pa / MPa / GPa |
| $V$ | 体积 volume | 也用摩尔体积 |
| $n$ | 摩尔数 number of moles | |
| $R$ | 气体常数 Gas Constant | **8.314 J mol⁻¹ K⁻¹** |
| $T$ | 温度 temperature | **必须是 Kelvin** |
| $U$ | 内能 internal energy | 有时写作 $E$（McSween） |
| $Q$ | 来自环境的热流 heat flow from surroundings | |
| $S$ | 熵 entropy | J mol⁻¹ K⁻¹ |
| $H$ | 焓 enthalpy | J |
| $G$ | 吉布斯自由能 Gibbs Free Energy | J |
| $d$ | **一个非常小的变化 (a very small change)** | 不是变量，不可约 |
| $\Delta$ | **一个（较大的）变化 (a change)** | 通常 = 产物 − 反应物 |

> 老师专门强调 $d$ 与 $\Delta$ 的区别：
> **"Previously I showed you the little d and I said that's a small change. Now we've got a capital delta and that means a big change… They're not a variable in themselves. They're representing a change in the system."**

### 3.2 吉布斯相律 (Gibbs Phase Rule) —— 本周必考公式

$$\boxed{f = c - \phi + 2}$$

| 符号 | 含义 |
|---|---|
| $c$ | **组分数 components** —— 描述体系中所有相的成分所需的最少化学物种数 |
| $\phi$ | **相数 phases** —— 在该 P、T 条件下**稳定共存**的相的数目 |
| $f$ | **自由度 degrees of freedom / 方差 variance** —— 在**不改变体系状态（即不改变相的数目）**的前提下，可以**独立改变**的**强度变量**的数目 |

**"+2" 的来源**：这个 2 对应 **T 和 P 两个可变的强度变量**，适用于 **成分 X 固定的一组分相图 (T vs P 图)**。

**若压力被固定**（例如 T vs X 图，P = 1 bar 恒定），则相律变为：

$$\boxed{f = c - \phi + 1}$$

**H₂O 体系的相律实例（一组分，三个相：ice / water / steam）**：$c = 1$

| 位置 | 相数 $\phi$ | 稳定相 | $f = 1 - \phi + 2$ | 物理含义 |
|---|---|---|---|---|
| **区域内 (area/field)** | 1 | 只有 ice 或 water 或 steam | **f = 2** | **可以任意小幅改变 P 或 T 而不改变体系状态**（仍在同一个区域内） |
| **线上 (phase boundary)** | 2 | 例如 ice + water | **f = 1** | **改变 P 就必须同时改变 T** 才能保持在这条线上（反之亦然）——只有一个自由度 |
| **三相点 (triple point)** | 3 | ice + water + steam | **f = 0** | **P 和 T 都不能改变**，否则体系状态立刻改变——一个固定的点 |

> **判读通则（practical 里反复用）**：
> **任何"面"→ f = 2；任何"线"→ f = 1；任何"线的交点/三相点"→ f = 0。**

### 3.3 熔化熵变的完整计算（讲义例题：透辉石 diopside）

**已知**：$T_m = 1391\ °\text{C}$，$\Delta H_m = 138{,}100\ \text{J mol}^{-1}$

**Step 1 — 温度换算为 Kelvin**：
$$T_m = 1391 + 273.15 = 1664.15\ \text{K}$$

**Step 2 — 代入 $\Delta S_m = \Delta H_m / T_m$**：
$$\Delta S_m = \frac{138{,}100\ \text{J mol}^{-1}}{1664.15\ \text{K}} = 82.99\ \text{J mol}^{-1}\text{K}^{-1}$$

**Step 3 — 结果解读**：
$\Delta S_m$ 是一个**高的正值**，符合预期，因为**熔融增大了体系的无序度 (degree of disorder)**。

### 3.4 混合物熔点的完整计算（讲义例题：80% Di + 20% An）

**目标**：求 $X_{Di} = 0.8$ 的岩石的熔化温度。

**Step 1 — 起点方程**：
$$\ln x_{Di} = -\frac{\Delta H_{Di,m}}{R}\left(\frac{1}{T} - \frac{1}{T_{Di,m}}\right)$$

**Step 2 — 重排解出 T**（讲义直接给出重排结果，考试会给这个式子）：
$$\boxed{T = \frac{\Delta H_{Di,m}}{\dfrac{\Delta H_{Di,m}}{T_{Di,m}} - R\ln x_{Di}}}$$

*（重排过程：$\dfrac{1}{T} = \dfrac{1}{T_{Di,m}} - \dfrac{R\ln x_{Di}}{\Delta H_{Di,m}}$ → 通分 → 取倒数。）*

**Step 3 — 代入数值**：
- $\Delta H_{Di,m} = 138{,}100\ \text{J mol}^{-1}$
- $T_{Di,m} = 1391\ °\text{C} = 1664.15\ \text{K}$
- $R = 8.314\ \text{J mol}^{-1}\text{K}^{-1}$
- $x_{Di} = 0.8$

分母第一项：$\dfrac{138100}{1664.15} = 82.985$

分母第二项：$R\ln x_{Di} = 8.314 \times \ln(0.8) = 8.314 \times (-0.22314) = -1.8552$
所以 $-R\ln x_{Di} = +1.8552$

分母 $= 82.985 + 1.855 = 84.840$

$$T = \frac{138100}{84.840} = 1627.8\ \text{K}$$

**Step 4 — 换回摄氏度**：
$$T = 1627.8 - 273.15 = 1354.6 \approx \boxed{1355\ °\text{C}}$$

**Step 5 — 解读**：
纯 Di 熔点 1391 °C，纯 An 熔点 1553 °C，而 80% Di + 20% An 的岩石在 **1355 °C 就完全熔融**——**比两者都低**。这正是"混合降低熔点"的体现，也是**岩石比单矿物更容易熔融**的原因。

### 3.5 关键图表判读速查

**① H₂O 相图（P–T）**
- 三个场：ice（左上）、water（中）、steam（右/下）；
- 熔化曲线**向左倾斜（负斜率）** —— 这是水的反常性质（冰的密度小于水；加压使冰熔化）；
- 三相点：0.6 kPa、0.01 °C；
- 1 atm = 101 kPa 这条水平线与曲线的交点即日常的 0 °C 和 100 °C。

**② SiO₂ 相图（P–T，一组分）**
- **横轴温度（0–2000 °C），纵轴压力（0–~100 kbar）**；
- **向右（升温）**：low quartz → high quartz →（低压时）tridymite → cristobalite → liquid；
- **向上（升压）**：quartz → coesite → stishovite；
- **判读方法**：给一个 (T, P) 坐标，落在哪个色块就是哪个相；落在线上就是两相共存（该反应 $\Delta G = 0$）；落在三线交点就是三相共存 (f = 0)。

**③ 碳相图（P–T，一组分）**
- 低 P → graphite（2.27 g cm⁻³）；高 P → diamond（3.51 g cm⁻³）；更高 T → liquid；极低 P 高 T → gas；
- **地表条件落在 graphite 场中** → 天然金刚石在地表是**亚稳的**。

**④ Diopside–Anorthite 相图（T–X，两组分，P 固定）**
- **纵轴 T（°C），横轴 $X_{Di}$（0 = 纯 An，1 = 纯 Di）**；
- 左端点 1553 °C（An 熔点），右端点 1391 °C（Di 熔点）；
- 两条下倾曲线在**共熔点**相交；
- **四个场**：上方 = **liquid**；左中 = **anorthite + liquid**；右中 = **diopside + liquid**；下方 = **anorthite + diopside（全固）**；
- **liquidus（液相线，红线）** = liquid 场的下边界；**solidus（固相线，绿线）** = 全固场的上边界（在共熔体系中就是过共熔点的水平线）。

**⑤ Al₂SiO₅ 相图（P–T，一组分，practical 用）**
- 三个同质多象：**蓝晶石 (kyanite)** —— 高 P；**红柱石 (andalusite)** —— 低 P 中 T；**夕线石 (sillimanite)** —— 高 T；
- 三条线交于**一个三相点**（kyanite + andalusite + sillimanite 共存，f = 0）；
- 是变质岩最经典的"压力—温度指示矿物"体系。

**⑥ 计算 vs 实验相图的对比（本周的方法论重点）**
- **热力学计算图**：由熔融方程算出；共熔点 $X_{Di} = 0.7$、$T = 1334\ °\text{C}$；
- **实验相图**：把不同比例的 Di+An 加热到已知温度、**快速冷却 (quenched)** 以保存高温组合，再观察产物；共熔点 $X_{Di} \approx 0.64$、$T \approx 1272\ °\text{C}$。

---

## 四、课堂补充

### 4.1 关于上周测验 (Week 5 test) 的反馈 —— 考试策略信息

老师用了将近 15 分钟讲测验，信息量很大：

- **成绩分布**：一个漂亮的**高斯分布 (Gaussian distribution)**，**均值 72 分**，这正是老师设定的目标。有人接近 100，也有人偏低。
- **20 道题**。**六道题算"容易"**（平均分 ≥ 4，标准差约 1）：
  - 配平化学反应式 (balancing chemical reactions)
  - 离子电荷 (charges on ions)
  - **地核形成 (core formation)**
  - 计算含多个同位素的元素的**原子量 (atomic mass)**
  - **核合成 (nuclear synthesis)**
  - **地球各层的成分 (composition of Earth's layers)**
- **有明显分化的一类题** 大多与 **practical 材料**相关 → **老师明确说："the material in the practicals is really important, that's what we will be seeing in the exam in January."**
- **有机化学 (organic chemistry)** 是失分点。老师安慰说：**"we won't be doing any more organic chemistry"** —— 本单元的有机化学到此为止，已学的就是全部要求。
- **踩坑提醒**：有学生在"填元素"的框里写了**元素名称**而不是**元素符号**。老师：**"pay attention to the instructions for what goes in a box."**
- **一月考试 (January exam) 的格式**：
  - 与测验**同样的题型**：**多选 (multiple choice)、匹配 (matching)、填空 (filling in blanks)**，需要动脑；
  - **两小时**，题更多、每题耗时更长；
  - **考察范围包括 Week 1–5 的全部内容**（"the stuff you've already done will come up again in January"）；
  - **十个主题，每个主题大约两道题** —— 这是分配复习精力的关键信息。
- **一道多选题平均分很低**，老师会去检查是不是题目表述有问题。

### 4.2 关于课程难度的回应（问卷反馈）

- 有人觉得**太简单**、有人觉得**太难** —— 因为大家先前的化学基础差异很大。
- **老师郑重重申**：
  > **"I do not expect you to have done A-level chemistry. This class is not starting from A-level chemistry… If you think it is, then please get that out of your head."**
- **给觉得难的人**：**专注基本原理 (basic principles)，不要太纠结应用 (applications)**；可以加入 **guided group（导学小组）**，practical 中逐题讲解；老师说必要时可以再开第二个导学组。
- **给觉得简单的人**：去读老师给的**延伸阅读**，追公式的推导——"it's really very logical and it's a really neat way of describing how reactions behave"。

### 4.3 上周 BIF（条带状铁建造）作图比赛的讲评

（这是 Week 5 practical 的遗留题，但讲评里有值得记的地球化学内容）

- 收到两份作品，**两份都得奖**。
- **第一份**：画出海洋、**Fe²⁺ 离子从火山喷口 (volcanic vent) 涌出**，与**蓝细菌 (cyanobacteria) 产生的氧气**反应，生成 **Fe³⁺** 并沉积下来，形成 **banded iron formation (BIF)**。老师的质疑：**沉积物画在了陆架 (shelf) 上，而不是海底**。
- **第二份**：色彩清晰、储库 (reservoirs) 分明。老师的质疑：**BIF 看起来像是在海底之下形成再向大陆侧"挤"进去**，应该改画成**海底上的沉积层 (a deposit at the bottom of the ocean)**。
- **方法论点评（值得记）**：
  > **"When you draw a sketch, it really illustrates your thinking… it's really good to have a go at something like this to try and represent what you're thinking on the page."**
  画示意图不是花活儿，是**检验自己是否真的理解过程**的手段。

### 4.4 老师对数学要求的定调（极其重要）

多次出现、请务必记住：

> - "**If you don't follow all the maths of this… don't worry about it. Anything that we ask you to do will give you an equation, and you'll just have to apply that equation.**"
> - "**I don't expect you at all to remember any of these equations.**"
> - "**Don't feel like you have to learn this. Don't feel like you have to understand all the derivations. It's just a sort of brief introduction.**"
> - "**What we're going to do in the practical is I'll tell you the equation, tell you the variables. You can put those things into the equation and calculate the answer, basically.**"

**结论：考试会给公式。你需要练的是"代入 + 单位换算 + 解读结果"，而不是背诵和推导。**

### 4.5 transcript 里 slides 上没有的补充

| 内容 | 只在课堂上讲的部分 |
|---|---|
| **平衡的定义** | slides 只说"不随时间变化"；老师补了"**the organization of matter to match the conditions that surround it**" |
| **石墨/金刚石的结构** | slides 只给密度；老师补了**石墨的六边形片层 + 弱层间键 → 软**、**金刚石的全共价键 → 硬**，并把结构差异与物理性质挂钩 |
| **柯石英的诊断意义** | 老师补了"发现柯石英意味着该岩石至少经历过 **20,000 atm**" |
| **相 ≠ 三态** | 老师专门警告 "Don't think that we're always going to talk about gas is a phase"；相是"水蒸气"、"冰"、"液态水"这些具体的东西 |
| **为什么两组分图要固定 P** | 老师解释"压力在第三个维度上，二维图放不下" |
| **$d$ 与 $\Delta$ 的区别** | 老师专门讲了 "$d$ = a very small change"、"$\Delta$ = a big change"、"they're not a variable in themselves"、"it's not part of the equation" |
| **可逆假设的地质理由** | 讲义写"地质过程很慢所以近可逆"，老师用它论证为什么可以把 ≤ 写成 = |
| **1 mol 水 = 18 g** | 顺带复习了摩尔质量的算法（H=1, O=16） |
| **理想气体定律的口误** | 老师说"T 升则 P 降"后自我更正 "I might have said that backwards"，**正确是 T 升则 P 升** |
| **防冻液类比** | 用汽车 antifreeze 解释"混合降低熔点"，slides 上只有一张 crankshift.com 的图 |
| **Kelvin/Celsius/Fahrenheit 三标对照** | 老师口头给了 32 °F / 212 °F 的对应 |

---

## 五、Practical 要点

**Practical 6 — Chemical Equilibrium: Thermodynamics and Phase Diagrams**

### 5.0 四个目标

1. 熟悉热力学变量（**焓、熵、吉布斯自由能**）与**平衡**的概念；
2. **从热力学数据构建相图**；
3. **从实验数据构建相图**；
4. **解读基本相图 + 应用吉布斯相律**。

---

### 5.A 热力学变量与平衡：方解石 vs 文石

**题目背景**：CaCO₃ 有两个同质多象 —— **方解石 (calcite)** 与 **文石 (aragonite)**。用热力学数据判断**地表条件（1 bar、298.15 K）下哪个稳定**。

**Table 1 数据**

| Mineral | $\Delta H^{o}_{f}$ / kJ mol⁻¹ | $S^{o}$ / J K⁻¹ mol⁻¹ |
|---|---|---|
| Calcite | **−1207.3** | **92.68** |
| Aragonite | **−1207.21** | **90.21** |

- $\Delta H^{o}_{f}$ = 由单质生成该矿物的**生成焓 (enthalpy of formation from the elements)**；
- 上标 "**o**" 表示**标准状态 (standard state)**：**1 bar (0.1 MPa) 与 298.15 K (25 °C)**；
- $S^{o}$ = 标准状态下该矿物的**熵**。

**反应式**：
$$\underbrace{\mathrm{CaCO_3}}_{Calcite} \;=\; \underbrace{\mathrm{CaCO_3}}_{Aragonite}$$

**计算法则（关键！）**：
$$\Delta H = \Delta H^{o}_{f}(\text{Aragonite}) - \Delta H^{o}_{f}(\text{Calcite})$$
$$\Delta S = S^{o}(\text{Aragonite}) - S^{o}(\text{Calcite})$$
> 即 **右边减左边 (right hand side minus left hand side)** —— **产物 − 反应物**。

#### (a) 求反应的吉布斯自由能 $\Delta G_r$

**Step 1 — 求 $\Delta H$**：
$$\Delta H = -1207.21 - (-1207.3) = +0.09\ \text{kJ mol}^{-1}$$

**Step 2 — 求 $\Delta S$ 并统一单位**：
$$\Delta S = 90.21 - 92.68 = -2.47\ \text{J K}^{-1}\text{mol}^{-1}$$
$$= -0.00247\ \text{kJ K}^{-1}\text{mol}^{-1}$$
> ⚠️ **必须换算！** $\Delta H$ 的单位含 **kJ**，$\Delta S$ 的单位含 **J**，两者不统一就会错 1000 倍。

**Step 3 — 温度必须用 Kelvin**：$T = 298.15\ \text{K}$

**Step 4 — 代入 $\Delta G = \Delta H - T\Delta S$**：
$$\Delta G_r = 0.09 - (298.15 \times -0.00247)$$
$$= 0.09 - (-0.7364)$$
$$= 0.09 + 0.7364$$
$$= \boxed{0.826\ \text{kJ mol}^{-1} = 826\ \text{J mol}^{-1}}$$

> ⚠️ **注意双重负号**：$-T\Delta S$ 中 $\Delta S$ 本身是负的，所以这一项最终是**加**。这是最常见的符号错误来源。
> **答案必须带单位。**

#### (b) 哪个多形体在地表稳定？

**推理**：
- 平衡时 $\Delta G_r = 0$；
- 反应朝**降低吉布斯自由能**的方向进行，即 $\Delta G_r < 0$ 时正向进行；
- 本题 $\Delta G_r = +826\ \text{J mol}^{-1} > 0$；

**结论**：**反应（calcite → aragonite）不会进行 → 地表条件下 CALCITE（方解石）是稳定的多形体。**

---

### 5.B 从热力学数据构建相图：calcite–aragonite 的 P–T 相界

**思路**：反应 $\text{Calcite} = \text{Aragonite}$ 的**化学平衡条件**由下式给出：

$$\boxed{P = 1 - \frac{\Delta G_r}{\Delta V_r}}$$

其中
$$\Delta V_r = V(\text{aragonite}) - V(\text{calcite})$$
$$\Delta G_r = G(\text{aragonite}) - G(\text{calcite})$$

**摩尔体积数据（假定不随 T、P 变化——因为方解石和文石的体积随 T、P 变化很小）**：
- $V(\text{calcite}) = 3.6934\ \text{J bar}^{-1}\text{mol}^{-1}$
- $V(\text{aragonite}) = 3.4150\ \text{J bar}^{-1}\text{mol}^{-1}$
- $\Delta V_r = 3.4150 - 3.6934 = \mathbf{-0.2784\ \text{J bar}^{-1}\text{mol}^{-1}}$（全表恒定）

**单位换算（讲义给的小技巧）**：
$$1\ \text{J} = 10\ \text{cm}^3\,\text{bar} \;\Longrightarrow\; 1\ \text{J bar}^{-1}\text{mol}^{-1} = 10\ \text{cm}^3\text{mol}^{-1}$$
所以 $V(\text{calcite}) = 36.934\ \text{cm}^3\text{mol}^{-1}$。

**Table 3 完整数据（G 随温度变化）**

| T / K | G(calcite) / kJ mol⁻¹ | G(aragonite) / kJ mol⁻¹ | ΔGr / J mol⁻¹ | ΔV / J bar⁻¹mol⁻¹ | P / bar | P / kbar | T / °C |
|---|---|---|---|---|---|---|---|
| 298.15 | −1128.842 | −1127.793 | **1049** | −0.2784 | **3769** | **3.8** | **25** |
| 400 | −1102.155 | −1100.691 | **1464** | −0.2784 | **5260** | **5.3** | **126.85** |
| 500 | −1076.292 | −1074.310 | 1982 | −0.2784 | 7120 | 7.1 | 226.85 |
| 600 | −1050.723 | −1048.132 | 2591 | −0.2784 | 9308 | 9.3 | 326.85 |
| 700 | −1025.427 | −1022.160 | 3267 | −0.2784 | 11736 | 11.7 | 426.85 |
| 800 | −1000.238 | −996.251 | 3987 | −0.2784 | 14322 | 14.3 | 526.85 |
| 900 | −975.195 | −970.468 | 4727 | −0.2784 | 16980 | 17.0 | 626.85 |
| 1000 | −950.299 | −944.833 | 5466 | −0.2784 | 19635 | 19.6 | 726.85 |

#### (a) 完整计算示范

**@ 298.15 K：**
$$\Delta G_r = -1127.793 - (-1128.842) = 1.049\ \text{kJ mol}^{-1} = 1049\ \text{J mol}^{-1}$$
$$P = 1 - \frac{\Delta G_r}{\Delta V_r} = 1 - \frac{1049}{-0.2784} = 1 + 3768.0 = \boxed{3769\ \text{bar} = 3.769\ \text{kbar}}$$
$$T = 298.15 - 273.15 = \boxed{25\ °\text{C}}$$

**@ 400 K：**
$$\Delta G_r = -1100.691 - (-1102.155) = 1.464\ \text{kJ mol}^{-1} = 1464\ \text{J mol}^{-1}$$
$$P = 1 - \frac{1464}{-0.2784} = 1 + 5258.6 = \boxed{5260\ \text{bar} = 5.26\ \text{kbar}}$$
$$T = 400 - 273.15 = \boxed{126.85\ °\text{C}}$$

> **注意**：$\Delta V_r$ 是负数，$\Delta G_r$ 是正数，所以 $-\Delta G_r/\Delta V_r$ 是**正的大数**；那个"+1"（即 1 bar 的参考压力）在数值上可以忽略但要写上。
> **单位链条**：$\dfrac{\text{J mol}^{-1}}{\text{J bar}^{-1}\text{mol}^{-1}} = \text{bar}$ ✓

#### (b) 作图

- **y 轴：P (kbar)；x 轴：T (°C)**；
- 把八个 (T, P) 点连成一条线 —— 这条线就是 **相界 (PHASE BOUNDARY)**；
- 线两侧的区域就是各矿物的 **稳定场 (STABILITY FIELDS)**；
- **用 A 题的结论定标签**：地表条件（25 °C, 1 bar）在这条线**下方**，而 A 题证明地表稳定的是方解石，因此：
  - **线以下 = CALCITE 稳定场**
  - **线以上 = ARAGONITE 稳定场**
  - **恰在线上 = 两者共存**
- 这条线是**正斜率的近直线**（T 升高，平衡压力升高）。

#### (c) 哪个在高压更稳定？为什么？

**答**：
- **文石 (aragonite) 是高压多形体**，方解石是低压多形体；
- **原因**：**文石的摩尔体积 (3.4150) 略小于方解石 (3.6934)**；
- **通则**：**摩尔体积更小的相在更高压力下更稳定**（"It is typical that a mineral phase with smaller volume will be more stable at higher pressure."）
- 与讲义中石墨/金刚石的例子完全一致 —— 也可以用 $dG = VdP - SdT$ 来理解：$V$ 小 ⇒ $G$ 随 $P$ 增长慢 ⇒ 高压下 $G$ 更低 ⇒ 更稳定。

---

### 5.C 从实验数据构建相图：Diopside–Anorthite

**实验方法（关键，要理解为什么这么做）**：
把 diopside 与 anorthite 按**不同比例**混合，加热到**不同温度**，然后 **快速冷却 (cooled quickly / quenched)**，以便**保存该温度下存在的相组合**。冷却后在显微镜下鉴定产物。

**Table 3 实验数据**

| $X_{Di}$ | T / °C | Phases present |
|---|---|---|
| 0 | 1250 | anorthite |
| 0 | 1400 | anorthite |
| 0 | 1552 | anorthite |
| 0 | 1554 | **liquid** |
| 0.2 | 1270 | anorthite + diopside |
| 0.2 | 1275 | anorthite + liquid |
| 0.2 | 1450 | anorthite + liquid |
| 0.2 | 1500 | liquid |
| 0.5 | 1250 | anorthite + diopside |
| 0.5 | 1325 | anorthite + liquid |
| 0.5 | 1350 | liquid |
| 0.5 | 1500 | liquid |
| 0.8 | 1250 | anorthite + diopside |
| 0.8 | 1300 | **diopside** + liquid |
| 0.8 | 1350 | diopside + liquid |
| 0.8 | 1400 | liquid |
| 1 | 1270 | diopside |
| 1 | 1275 | diopside |
| 1 | 1391 | diopside |
| 1 | 1400 | **liquid** |

**作图方法（Feedback 给的 Hint）**：
> **"for each point, plot the point and label it with the phases present (An, Di, L)"**
即：先把每个 (X, T) 点画上去并标注相组合，再在"相组合发生改变"的位置之间**画界线**。

**如何定位相界（解题思路）**：
1. **纯 An 端 (X = 0)**：1552 °C 还是 anorthite，1554 °C 已是 liquid → **An 熔点在 1552–1554 之间（≈1553 °C）**。
2. **纯 Di 端 (X = 1)**：1391 °C 还是 diopside，1400 °C 已是 liquid → **Di 熔点 ≈ 1391 °C**。
3. **共熔温度**：在 $X_{Di} = 0.2$ 处，1270 °C 是全固 (An + Di)，1275 °C 已有液体 (An + L) → **共熔温度在 1270–1275 °C 之间 ≈ 1272 °C**。
4. **共熔成分**：注意相组合从"An + L"翻转到"Di + L"的位置。$X_{Di} = 0.5$ 时是 **An + L**（1325 °C），$X_{Di} = 0.8$ 时是 **Di + L**（1300 °C）→ **共熔成分介于 0.5 与 0.8 之间**；结合各点的液相线约束，**$X_{Di} \approx 0.64$**。

**Feedback 给出的答案**：
$$\textbf{实验共熔点：} X_{Di} \approx 0.64,\quad T \approx 1272\ °\text{C （1270 与 1275 之间）}$$
$$\textbf{热力学计算共熔点：} X_{Di} = 0.7,\quad T = 1334\ °\text{C}$$

**图的结构**：
- **红线以上（liquidus，液相线）全部是 liquid**；
- **绿线以下（solidus，固相线）全部是 solid**；
- 两条红线之间的两个区域分别是 **anorthite + liquid** 和 **diopside + liquid**。

#### 为什么两张图不一样？哪个更准确？（本题的核心考点）

**答案（务必背下逻辑）**：
> **热力学计算假定 anorthite 与 diopside 的混合是"理想的 (ideal)"**，也就是说，液体的行为就好像它只是简单地含有互相独立的 An 组分和 Di 组分。
> **现实中，液体内部原子之间的成键与相互作用 (bonding and interactions between atoms in the liquid)** 使液体的行为与理想情形不同。这叫 **"非理想混合" (non-ideal mixing)**，而现实世界就是非理想的。
> **因此实验结果是对该体系真实行为更准确的记录 (The experiments are a more accurate record of the real behaviour of the system.)**

---

### 5.D 相图解读与吉布斯相律

#### D1. Al₂SiO₅ 体系（一组分，三个同质多象）

- **组分数 c = 1**（Al₂SiO₅），全图成分恒定；
- 三个多形体：**kyanite（蓝晶石）、andalusite（红柱石）、sillimanite（夕线石）**。

**Table 4 答案（$f = c - \phi + 2 = 1 - \phi + 2 = 3 - \phi$）**

| Point | T, P (°C, MPa) | Stable Phases | $\phi$ | **Degrees of Freedom $f$** |
|---|---|---|---|---|
| A | — | kyanite | 1 | **2** |
| B | — | ky + sillim | 2 | **1** |
| C | — | and + sillim | 2 | **1** |
| D | — | ky + and | 2 | **1** |
| E | — | ky + and + sillim | 3 | **0** |
| **F** | **300, 300** | **kyanite** | 1 | **2** |
| **G** | **500, 300** | **andalusite** | 1 | **2** |
| **H** | **800, 300** | **sillimanite** | 1 | **2** |

**解题要领**：
- **A、F、G、H 落在"面"上** → 只有 1 个相 → **f = 2**；
- **B、C、D 落在"线"上** → 2 个相共存 → **f = 1**；
- **E 是三条线的交点（三相点）** → 3 个相共存 → **f = 0**；
- F、G、H 需要**自己在图上标点**：都在 **P = 300 MPa** 的水平线上，沿温度从低到高 300 → 500 → 800 °C，依次穿过 **kyanite → andalusite → sillimanite** 三个场。
- 顺带学到的地质结论：**低 T 高 P → 蓝晶石；中 T 低 P → 红柱石；高 T → 夕线石**，这是变质带划分的基础。

#### D2. SiO₂ 体系相图（逐题解析）

**(a) 图中有几个组分？**
**一个 —— 二氧化硅 (SiO₂)。** 图上处处成分相同，都是 SiO₂。

**(b) 图中有几个相？**
**七个 —— 每一个不同颜色的区域就是一个相，包括 liquid。**

**(c) 列出图中 SiO₂ 的同质多象。**
**cristobalite（方石英）、tridymite（鳞石英）、high quartz（高温石英）、low quartz（低温石英）、coesite（柯石英）、stishovite（斯石英）。**
> ⚠️ **liquid 是一个相，但不是矿物同质多象** —— 所以多形体是 **6 个**，相是 **7 个**。这是本题最容易被扣分的地方。

**(d) 在图上各标出两个 f = 2、f = 1、f = 0 的点。**
- **图上任何一个"面"→ f = 2**；
- **任何一条"线"→ f = 1**；
- **任何"线与线的交点"→ f = 0**（例如 **low-quartz — high-quartz — coesite** 三相组合只在**一个点**上稳定，此处 f = 0）。

**(e) 在图上指出反应 $\text{high quartz} = \text{coesite}$ 的 $\Delta G = 0$ 之处。**
$\Delta G = 0$ 意味着**两相同时稳定** → **就是这两个场之间的那条线（相界）**。

**(f) 一个在 1200 °C 喷发的火山岩中的硅质矿物，会是哪个多形体？**
因为在**喷发**，可以假定**压力很低（P ≈ 0）**。在 **P = 0、1200 °C** 处，稳定的多形体是 **tridymite（鳞石英）**。

**(g) 一个在 10 kbar、200 °C 形成的沉积物中的硅质矿物，会是哪个多形体？**
**low quartz（低温石英）。**

**(h) 上题的石英颗粒被大型陨石撞击，在 70 kbar 下转变为另一个多形体，会是哪个？**
**coesite（柯石英）。**（柯石英与斯石英最早正是在**撞击坑物质**中被鉴定出来的。）

**(i) 在地球表面，SiO₂ 大约在什么温度熔化？**
**约 1700 °C（实际 1713 °C）。** 在图上 **y 轴 P = 0** 处、**cristobalite 场与 liquid 场的边界**上读出。

**(j) 如果你找到一粒方石英 (cristobalite)，它最可能来自什么岩石？**
**火山岩 (volcanic rock)** —— 因为方石英需要**非常高的温度**。

**(k) 那为什么能在地表（1 bar、20 °C）找到方石英颗粒？**
> **相图显示的是"热力学上稳定的相"。但许多亚稳相或非平衡相 (metastable or disequilibrium phases) 能够保存到地表条件，因为反应只有在有足够能量时才能进行。动力学效应 (Kinetic effects) 对于保存不平衡矿物非常重要。**

这与讲义里"金刚石在地表是亚稳的"是**同一个道理**——**热力学告诉你"应该"是什么，动力学决定你"实际"看到什么**。

---

## 六、易错点 / 重点难点

### 6.1 单位与换算类（最高频失分）

1. **温度必须用 Kelvin**。$\Delta G = \Delta H - T\Delta S$、$PV = nRT$、$\Delta S_m = \Delta H_m/T_m$ 里的 T 全部是 K。$T(\text{K}) = T(°\text{C}) + 273.15$。
2. **$\Delta H$ 用 kJ、$\Delta S$ 用 J** —— 数据表就是这么给的，**必须先统一**（把 J 除以 1000 变成 kJ，或反之）。Practical A 题就是专门考这个。
3. **压力单位链**：1 kbar = 1000 bar = 100 MPa；1 GPa = 10 kbar；1 kPa = 10⁻² bar；100 kPa = 1 bar；1 atm ≈ 101 kPa。
4. **体积单位小技巧**：1 J = 10 cm³ bar ⇒ 1 J bar⁻¹ mol⁻¹ = 10 cm³ mol⁻¹。
5. **$R = 8.314$ J mol⁻¹ K⁻¹** —— 讲义漏了 K⁻¹，别跟着漏。
6. **答案要写单位**（practical 明确要求 "Include units for G with your answer"）。

### 6.2 符号与正负号

7. **$-T\Delta S$ 里 $\Delta S$ 本身可能是负的**，两个负号相乘变正。Practical A 题：$0.09 - (298.15 \times -0.00247) = 0.09 + 0.736$。
8. **$\Delta$ = 右边 − 左边 = 产物 − 反应物**。搞反了整个结论就反了。
9. **$d$（小变化）与 $\Delta$（大变化）** —— 都**不是变量**，不能约分、不能当系数。
10. **第一定律的正确写法是 $dU = dQ - PdV$**（讲义 md 里负号被 OCR 吞了）。
11. **$\Delta G$ 判据方向**：$\Delta G < 0$ **才**自发正向进行；$\Delta G > 0$ 说明**逆反应**才自发；$\Delta G = 0$ 是平衡。

### 6.3 概念类

12. **相 (phase) ≠ 物态 (state of matter)**。老师专门警告过。SiO₂ 图里有 **6 个矿物相 + 1 个液相 = 7 个相**，但**只有 6 个 polymorph**。
13. **组分 (component) 是"最少"化学物种数**，不是"图上出现的物种数"。SiO₂、C、H₂O 图都是 **1 个组分**；Di–An 图是 **2 个组分**。
14. **相律的 "+2" 与 "+1"**：
    - **T vs P 图（X 固定）→ $f = c - \phi + 2$**
    - **T vs X 图（P 固定）→ $f = c - \phi + 1$**
    考试很容易在这里挖坑。
15. **自由度 f 的判读速记：面 = 2，线 = 1，交点 = 0**（对一组分 T–P 图而言）。
16. **热力学 vs 动力学**：相图说的是"**热力学上应该稳定**的相"；实际见到的可能是**亚稳相**，因为**反应速率太慢 (kinetics)**。金刚石、方石英、柯石英在地表存在都是这个道理。**任何"为什么地表能找到 X"的题，答案基本都是 kinetics。**
17. **理想混合 vs 非理想混合**：热力学计算的 Di–An 相图假设**理想混合**；实验图反映**非理想混合**（液体中原子的成键与相互作用）；**实验图更准确**。这是 practical C 的固定考点。
18. **高压偏好高密度/小摩尔体积的相**（graphite→diamond、calcite→aragonite、quartz→coesite→stishovite）；**高温偏好高熵的相**（固→液、低温相→高温相）。可用 $dG = VdP - SdT$ 统一理解。
19. **混合物的熔点低于任一纯组分的熔点**（antifreeze 效应）；**共熔点是体系熔融的最低温度**。
20. **老师的口误**：理想气体定律定容时 **T 升 → P 升**（他先说反了又自我更正）。
21. **幻灯片勘误**：SiO₂ 相图 y 轴的 "1900" 应为 "1800"。

### 6.4 考试策略（来自 transcript）

22. **一月考试涵盖 Week 1–11 全部内容**，包括已考过的 Week 1–5。
23. **十个主题，每个约两题**，两小时，题型为多选/匹配/填空。
24. **practical 材料是考试重点** —— 老师明说 "that's what we will be seeing in the exam in January"。
25. **公式会给**，不用背；练的是**代入与解读**。
26. **看清"框里要填什么"** —— 元素**符号**还是**名称**，别写错类型。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Equilibrium | 平衡 | 不随时间变化的物质状态；物质组织自身以匹配周围条件 |
| Thermodynamics | 热力学 | 研究能量（热）及其变化、描述体系如何响应环境变化的学科 |
| Kinetics | 动力学 | 研究反应**速率**的学科；决定热力学上应发生的变化是否**实际**发生 |
| Heat | 热 | 热能，来源于物质内部原子分子的随机运动 |
| Chemical energy | 化学能 | 储存在化学键中的能量 |
| Joule (J) | 焦耳 | 能量单位；1 J = 1 kg m² s⁻² = 1 N m |
| System | 体系 | 我们所要考虑的那一部分宇宙，可大可小，由研究者自行定义 |
| Isolated system | 孤立体系 | 既不能与环境交换能量、也不能交换物质 |
| Closed system | 封闭体系 | 可交换能量但不能交换物质 |
| Open system | 开放体系 | 既可交换能量又可交换物质 |
| Extensive variable | 广延变量 | 取决于体系大小的量：质量、体积、能量 |
| Intensive variable | 强度变量 | 不取决于体系大小的量：温度、压力、黏度、密度 |
| Ideal Gas Law | 理想气体定律 | $PV = nRT$，描述气体的 P、V、n、T 关系 |
| Gas constant (R) | 气体常数 | 8.314 J mol⁻¹ K⁻¹ |
| Kelvin scale | 开尔文温标 | 以绝对零度为 0 的绝对温标；度的大小同摄氏度；$T(K)=T(°C)+273.15$ |
| Absolute zero | 绝对零度 | 0 K；由理想气体定律外推（$T=0$ 时 $V=0$）得到的最低可能温度 |
| First Law of Thermodynamics | 热力学第一定律 | 能量守恒；$dU = dQ - PdV$ |
| Internal energy (U) | 内能 | 矿物中化学键势能与原子振动动能之和（McSween 写作 E） |
| Second Law of Thermodynamics | 热力学第二定律 | 自发变化朝总熵增大的方向进行；$dS \geq dQ/T$ |
| Entropy (S) | 熵 | 能量在体系中如何分布的量度；也可理解为无序度；单位 J mol⁻¹ K⁻¹ |
| Spontaneous / irreversible change | 自发变化 / 不可逆变化 | 会自动发生且不会自行逆转的变化（如两种气体混合） |
| Fundamental Equation | 热力学基本方程 | $dU = TdS - PdV$；因地质过程缓慢近可逆而可取等号 |
| Enthalpy (H) | 焓 | 物质的总热含量；$H = U + PV$；恒压时 $dH = dQ$ |
| Enthalpy of formation ($\Delta H^{o}_{f}$) | 生成焓 | 由单质生成该化合物时的焓变，标准态为 1 bar、298.15 K |
| Standard state (superscript °) | 标准状态 | 1 bar (0.1 MPa) 与 298.15 K (25 °C) |
| Gibbs Free Energy (G) | 吉布斯自由能 | 恒 T、恒 P 下可用于做有用功的能量；$G = H - TS$ |
| $\Delta G = \Delta H - T\Delta S$ | 吉布斯方程 | $\Delta G=0$ 平衡；$\Delta G<0$ 自发正向；反应朝 G 降低方向进行 |
| $dG = VdP - SdT$ | — | 说明小摩尔体积相偏好高压、高熵相偏好高温 |
| Calorimetry | 量热法 | 通过测量恒压下的热量来测定焓变 $\Delta H$ |
| Phase | 相 | 物理上独立、原则上可与体系其余部分物理分离的物质体 |
| Phase diagram | 相图 | 表示各相稳定区域的图；面 = 稳定场，线 = 相界，交点 = 多相共存点 |
| Phase boundary | 相界 | 相图上两相同时稳定共存的线，其上 $\Delta G = 0$ |
| Stability field | 稳定场 | 相图上某一相热力学稳定的区域 |
| Triple point | 三相点 | 三个相同时平衡共存的唯一一点（H₂O：0.6 kPa, 0.01 °C），f = 0 |
| Component | 组分 | 描述体系中所有相的成分所需的**最少**化学物种数 |
| Polymorph | 同质多象 / 多形体 | 化学式相同但原子排列不同的矿物（如金刚石与石墨） |
| Metastable / disequilibrium phase | 亚稳相 / 非平衡相 | 热力学上不该稳定、却因动力学缓慢而保存下来的相 |
| Gibbs Phase Rule | 吉布斯相律 | $f = c - \phi + 2$（P 固定时为 $f = c - \phi + 1$） |
| Degrees of freedom (f) | 自由度 / 方差 | 在不改变相数的前提下可独立改变的强度变量数目 |
| Melting point ($T_m$) | 熔点 | 固相与液相平衡的温度，此时 $\Delta G_m = 0$，$\Delta H_m = T_m \Delta S_m$ |
| Enthalpy of fusion ($\Delta H_m$) | 熔化焓 / 熔化热 | 熔化过程的焓变，可由量热法测得 |
| Depression of melting point | 熔点降低 | 混合物的最低熔点总低于任一纯组分的熔点（防冻液效应） |
| Eutectic | 共熔点 | 二元相图上两条液相线的交点，体系熔融的最低温度与对应成分 |
| Liquidus | 液相线 | 相图上液相场的下边界；其上全为液体 |
| Solidus | 固相线 | 相图上全固场的上边界；其下全为固体 |
| Ideal mixing | 理想混合 | 假定液体中各组分互不影响、行为如独立组分之和 |
| Non-ideal mixing | 非理想混合 | 液体中原子成键与相互作用使行为偏离理想；真实世界的情形 |
| Quenching (cooled quickly) | 淬火 / 急冷 | 实验中快速冷却以保存高温下的相组合 |
| Low / high quartz | 低温 / 高温石英 | SiO₂ 的两个低压多形体，随温度升高互相转变 |
| Tridymite | 鳞石英 | SiO₂ 的低压高温多形体（约 1200 °C, P≈0 时稳定） |
| Cristobalite | 方石英 | SiO₂ 熔融前的最高温多形体，多见于火山岩 |
| Coesite | 柯石英 | SiO₂ 高压多形体；发现它意味着岩石经历过 ≥ 约 20 kbar 压力，撞击构造的标志 |
| Stishovite | 斯石英 | SiO₂ 的极高压多形体，最早发现于陨石撞击坑 |
| Graphite | 石墨 | 碳的低压多形体；六边形片层 + 弱层间键 → 软；密度 2.27 g cm⁻³ |
| Diamond | 金刚石 | 碳的高压多形体；全共价键 → 硬；密度 3.51 g cm⁻³；地表为亚稳相 |
| Calcite | 方解石 | CaCO₃ 的低压多形体，地表稳定；摩尔体积 36.934 cm³ mol⁻¹ |
| Aragonite | 文石 / 霰石 | CaCO₃ 的高压多形体；摩尔体积较小 (34.150 cm³ mol⁻¹) |
| Diopside (Di) | 透辉石 | 单斜辉石；熔点 1391 °C，$\Delta H_m$ = 138,100 J mol⁻¹ |
| Anorthite (An) | 钙长石 | 斜长石端元；熔点 1553 °C |
| Kyanite | 蓝晶石 | Al₂SiO₅ 的高压多形体 |
| Andalusite | 红柱石 | Al₂SiO₅ 的低压中温多形体 |
| Sillimanite | 夕线石 / 矽线石 | Al₂SiO₅ 的高温多形体 |
| Suevite | 熔积角砾岩 | 撞击构造中的角砾状岩石（德国 Ries 撞击坑，含柯石英） |

---

## 附：本周一句话总纲

> **$\Delta G$ 告诉你反应往哪走（$\Delta G<0$ 就走，$\Delta G=0$ 就是平衡），把不同 T、P、X 下 $\Delta G=0$ 的位置连起来就是相图的线，线围出的面就是各相的稳定场；相律 $f=c-\phi+2$ 告诉你面上 f=2、线上 f=1、交点 f=0；而动力学 (kinetics) 提醒你——相图说"应该"是什么，不等于你"实际"看到什么。**
