# Week 7 — 岩石的熔融与稀土元素 (Melting and the Rare Earth Elements, REE)

> 课程：EART11200 The Natural Scientist's Toolkit — Chemistry of the Earth
> 本周材料：Lecture 7 "Melting and REE"（讲师 **Mike Burton**，火山学家；前六周由 Marianne 讲授）+ 13-Nov 课堂录音转写 + Practical 7 及其 Feedback
> 建议阅读：Grotzinger & Jordan p.97–98（熔融）、p.133（全球火山作用）；Gill Ch.2 p.26–30；Misra Ch.12.3；White Ch.7（尤其 7.2.2.4、7.3、7.4.4）；McSween & Richardson Ch.12 p.237–255；Elements Magazine "Rare Earth Elements: Minerals, Mines, Magnets (and More)" e8_5 pp.15–22；Blackboard 上的 `Diopside-Anorthite.pdf`（完整结晶路径）

---

## 一、本周主题

本周把前六周建立的"元素—地球分层—元素分配"框架落到**岩石实际怎么熔化、熔体化学如何演化**这一具体过程上，并引入地球化学中最强大的示踪工具之一——**稀土元素 (Rare Earth Elements, REE)**。

内容分两大部分：

1. **Part 1: How rocks melt（岩石如何熔融）** — 用**二元相图 (binary phase diagram)**（钙长石 Anorthite–透辉石 Diopside 体系）定量描述**部分熔融 (partial melting)**：共结点 (eutectic)、固相线 (solidus)、液相线 (liquidus)、**杠杆规则 (lever rule)**，以及平衡结晶 (equilibrium crystallization) 是熔融的逆过程。
2. **Part 2: Melting the mantle and the REE（地幔熔融与稀土元素）** — 地幔（橄榄岩 peridotite）共结熔融产生玄武岩 (basalt)；REE 的电子构型、镧系收缩 (lanthanide contraction)、球粒陨石归一化 (chondrite normalization)；**分配系数 (partition coefficient, D)**、相容/不相容元素 (compatible / incompatible)；用 REE 配分曲线反演**熔融程度、地壳混染、熔融深度**。

**在 11 周主线中的位置**：Week 1 讲元素丰度与核合成（本周"奇偶丰度"直接回到 Lecture 1 的图）；Week 2 讲地球化学视角的周期表（本周 REE 在周期表中的位置、f 轨道电子构型直接引用 Lecture 2）；Week 3 讲元素在两种液体间的分配（本周把"分配"概念从液–液推广到**矿物–熔体**）；Week 4–6 讲碳循环/氧化还原/化学平衡（本周的熔融判据用到 Gibbs 自由能）。本周（Week 7）是**岩浆作用与微量元素地球化学**的核心，也是后续 Week 8（稳定同位素，同样由 Mike Burton 讲授）、Week 10（放射性同位素与年代学，Sm–Nd 体系正是 REE）的直接铺垫。

> **老师原话警告（transcript）**："These phase diagrams look simple, but they're actually incredibly powerful... These tricks are invaluable for a geochemist, and **they will be part of the exam at the end of this course**." 相图判读是必考内容。他还说："This is not easy... It will not be 2 plus 2 equals 4. There's multiple steps needed."

---

## 二、核心概念

### 2.1 岩石为什么会熔化？—— Gibbs 自由能判据

**Why（为什么熔）**：当体系中**液相 (liquid) 的 Gibbs 自由能低于组成该岩石的矿物 (minerals) 的 Gibbs 自由能**时，岩石开始熔融。

$$\Delta G_{\text{melting}} = G_{\text{liquid}} - G_{\text{solid}} < 0 \quad \Rightarrow \quad \text{熔融自发进行}$$

回忆 Gibbs 自由能定义：

$$G = H - TS$$

- $G$：Gibbs 自由能 (Gibbs free energy)，J 或 J/mol
- $H$：焓 (enthalpy)
- $T$：绝对温度 (K)
- $S$：熵 (entropy)

液体的熵 $S_{\text{liquid}}$ 远大于晶体的熵 $S_{\text{solid}}$（液体无长程有序结构）。因此 $-TS$ 项在高温下对液体更有利：温度升高到某一点后，$G_{\text{liquid}}$ 就会跌到 $G_{\text{solid}}$ 之下，熔融发生。

> 转写中老师强调的一句总纲：**"As always, nature tries to minimize the Gibbs free energy."**（自然界总是趋向最小化 Gibbs 自由能。）这与 Week 6 化学平衡部分完全一致。

**How（怎么熔）**：**岩石没有单一"熔点" (melting point)**。岩石是多种矿物的混合物，它在**一个温度区间内逐渐熔融**。在该区间内，熔体 (melt) 与固体 (solid) 共存 —— 这就叫**部分熔融 (partial melting)**。给定温度和压力下，平衡熔体的成分由热力学（相图）唯一确定。

对比记忆：
- **纯矿物**（如纯 Diopside）有确定熔点（Di：**1391 °C**；An：约 1553 °C）。
- **矿物混合物**（= 真实岩石）在**固相线 (solidus)** 与**液相线 (liquidus)** 之间部分熔融。

### 2.2 二元共结相图：Anorthite–Diopside 体系

本周的核心工具图。这是一个**二元共结体系 (binary eutectic system)**：

| 端元 | 矿物 | 化学式 | 在岩石中的角色 |
|---|---|---|---|
| An | Anorthite 钙长石 | CaAl₂Si₂O₈ | 斜长石 (plagioclase) 端元，浅色矿物 |
| Di | Diopside 透辉石 | CaMgSi₂O₆ | 单斜辉石 (clinopyroxene) 端元，暗色矿物 |

An + Di 的组合正是**辉长岩 (gabbro)** 的简化模型（斜长石 + 辉石）。

**图的坐标**：
- **纵轴**：温度 $T$（°C），本图范围约 1200–1600 °C
- **横轴**：成分，通常画成 $X_{\text{Di}}$（透辉石摩尔/重量分数）从 0（纯 An，左端）到 1（纯 Di，右端）。**同一根横轴同时被两件事使用**：(a) 体系的**总体成分 (bulk composition)**；(b) **熔体 (liquid) 的成分**。转写原话："This scale... **it has two jobs**."

**图上的关键线与点**：

1. **液相线 (liquidus)**：两条从两端熔点向下、在共结点相交的曲线。它给出**完全熔融的温度**，也给出**任一温度下平衡熔体的成分**。老师原话："For a mixture of An and Di, the temperature of complete melting and the equilibrium melt composition are given by this line, called the liquidus."
2. **固相线 (solidus)**：共结温度处的水平线（1274 °C）。**这条线以下，任何 An–Di 混合物都是全固态**。
3. **共结点 (eutectic point)**：$T_E = \mathbf{1274\ °C}$，成分 $\mathbf{An_{42}Di_{58}}$（即 $X_{\text{Di}} = 0.58$）。这是**整个体系熔融温度的最低点**。

**四个相区**：

| 相区 | 稳定的相 | 位置 |
|---|---|---|
| L | 只有液体（1 个相） | 两条液相线之上 |
| An + L | 钙长石 + 液体（2 个相） | 左侧液相线以下、固相线以上，$X_{\text{Di}} < 0.58$ |
| Di + L | 透辉石 + 液体（2 个相） | 右侧液相线以下、固相线以上，$X_{\text{Di}} > 0.58$ |
| An + Di | 两种固体矿物（2 个相） | 固相线 1274 °C 以下 |

**关键规则（务必背下）**：

> **对任意 An–Di 混合物，第一滴熔体都出现在 1274 °C，且其成分永远是共结成分 An₄₂Di₅₈ —— 与原岩中 An/Di 的比例无关。**

转写中老师反复强调："This is a **rule that is true regardless of where you begin** on the initial composition... unless you've got pure anorthite... you will always begin your journey over here [at the eutectic]."

**为什么？**（老师给的直观解释）在共结点，**An、Di、Liquid 三相同时共存**。共结温度以上，处于 An-rich 一侧（$X_{\text{Di}}<0.58$）的体系里，**Di 会优先被全部熔光**，之后只剩 An + L；处于 Di-rich 一侧则相反。**除了共结点这一个温度，An、Di、Melt 三者永远不会同时共存**（"we never have anorthite and diopside together with melt, apart from at the eutectic"）。

### 2.3 部分熔融的完整路径：以 An₈₀Di₂₀ 为例（讲义主线例题）

设原岩总成分 = **80% Anorthite + 20% Diopside**（$X_{\text{Di}} = 0.20$，落在共结点左侧的 An-rich 区）。

| 温度 | 体系状态 | 熔体成分 | 备注 |
|---|---|---|---|
| **1200 °C** | 全固态：An + Di 两种矿物 | 无熔体 | 位于固相线以下 |
| **1274 °C** | 首次出现熔体 | **An₄₂Di₅₈**（共结成分） | 所有 Di 在此温度熔光 |
| **1350 °C** | An + L（部分熔融） | 约 **An₅₆Di₄₄** | 熔体沿液相线向 An 端移动 |
| **1400 °C** | An + L（熔体更多） | 约 **An₆₃Di₃₇** | |
| **~1470 °C** | **完全熔融点** | **An₈₀Di₂₀** = 总成分 | 最后一粒 An 消失 |
| **1550 °C** | 全液态 | An₈₀Di₂₀ 不变 | 继续升温**只升温不变化学成分** |

**熔体成分为什么向 An 端移动？**老师自问自答："Why do you think the melt is becoming more rich in anorthite? **It's because we are melting anorthite.**" 越过共结点后 Di 已耗尽，继续加热就只能熔 An，残余熔体自然越来越富 An，直到与原岩总成分相同。

**质量守恒的直觉检查**：起始固体是 An₈₀Di₂₀，完全熔融后熔体也必须是 An₈₀Di₂₀ —— 但**这条路径不是直线**，它必须先绕道共结点（An₄₂Di₅₈），再沿液相线爬回来。

### 2.4 杠杆规则 (Lever Rule) —— 定量算出固/液比例

相图不仅告诉你**熔体成分**，还能算出**熔体与残余固体各占多少**。这就是杠杆规则。

**三个点的定义**（以 An + L 两相区为例，某一温度下画一条水平的连结线 tie line）：

- **A** = 该温度下**固相的成分**在横轴上的位置。在 An+L 区，固相是纯钙长石，所以 $A$ 在 $X_{\text{Di}} = 0$（An₁₀₀ 端）。
- **B** = **体系总成分**在横轴上的位置（$X_{\text{Di}}^{\text{bulk}}$）。
- **L** = 该温度下**液相的成分**（液相线上的点，读到横轴）。

$$\boxed{\ \text{熔体比例 } f_L = \frac{AB}{AL} \qquad\qquad \text{固体比例 } f_{An} = \frac{BL}{AL}\ }$$

**记忆口诀**：**某一相的比例 = 对面那一段 / 总长度**（"take the opposite arm"）。B 点（总成分）离 L 点近 → 液体多；离 A 点近 → 固体多。

**推导（为什么杠杆规则成立 —— 质量守恒）**：

设熔体质量分数 $f_L$，固体（纯 An）质量分数 $f_{An}$，且 $f_L + f_{An} = 1$。对组分 Di 做质量平衡：

$$X_{\text{Di}}^{\text{bulk}} = f_L \cdot X_{\text{Di}}^{L} + f_{An}\cdot X_{\text{Di}}^{An}$$

因为固相是纯 An，$X_{\text{Di}}^{An} = 0$，故：

$$X_{\text{Di}}^{\text{bulk}} = f_L \cdot X_{\text{Di}}^{L} \quad\Longrightarrow\quad f_L = \frac{X_{\text{Di}}^{\text{bulk}}}{X_{\text{Di}}^{L}} = \frac{AB}{AL}$$

$$f_{An} = 1 - f_L = \frac{X_{\text{Di}}^{L} - X_{\text{Di}}^{\text{bulk}}}{X_{\text{Di}}^{L}} = \frac{BL}{AL}$$

（老师上课时先只给"照做就对"的机械规则，说 "I'm just going to tell you... afterwards I'll give you the explanation about why it works"。上面这个质量平衡就是背后的原因。）

**逐点计算 An₈₀Di₂₀ 的固/液比例（讲义完整算例）**：

注意：**AB 永远固定 = 0.20**（因为 A 固定在 $X_{\text{Di}}=0$、B 固定在体系总成分 $X_{\text{Di}}=0.20$）。随温度改变的只有 **L 的位置**，从而 AL 和 BL 变。

**① 刚过共结点（1274.1 °C）**，$X_{\text{Di}}^{L} = 0.58$：

```
AB = 0.20 - 0    = 0.20
AL = 0.58 - 0    = 0.58
BL = 0.58 - 0.20 = 0.38

f_L  = AB/AL = 0.20 / 0.58 = 0.345 → 熔体 ≈ 35 %
f_An = BL/AL = 0.38 / 0.58 = 0.655 → 钙长石 ≈ 65 %
（校验：100 % − 35 % = 65 % ✓，闭合体系只有这两相）
```

**② 1350 °C**，$X_{\text{Di}}^{L} = 0.44$：

```
AB = 0.20 ; AL = 0.44 ; BL = 0.44 − 0.20 = 0.24

f_L  = 0.20 / 0.44 = 0.455 → 熔体 ≈ 46 %
f_An = 0.24 / 0.44 = 0.545 → 钙长石 ≈ 54 %
```

**③ 1400 °C**，$X_{\text{Di}}^{L} = 0.37$：

```
AB = 0.20 ; AL = 0.37 ; BL = 0.37 − 0.20 = 0.17

f_L  = 0.20 / 0.37 = 0.54 → 熔体 ≈ 54 %
f_An = 0.17 / 0.37 = 0.46 → 钙长石 ≈ 46 %
```

**④ ~1470 °C（完全熔融）**：L 点与 B 点重合，$BL = 0$，故 $f_{An} = 0$、$f_L = 100\%$。

**趋势总结**：温度升高 → L 点左移（向 An 端） → BL 缩短 → 固体比例单调下降、熔体比例单调上升 → 到 BL = 0 时全熔。老师提醒："you can immediately also project forward — when this line eventually reaches here, we've got no rock left, because **BL becomes zero**."

### 2.5 平衡结晶 (Equilibrium Crystallization) —— 熔融的完全逆过程

**平衡结晶严格沿熔融路径反向进行。**仍以 An₈₀Di₂₀ 为例，从高温冷却：

| 温度 | 事件 |
|---|---|
| **1600 °C** | 全熔体，成分 An₈₀Di₂₀ |
| **~1470 °C** | 液相线：**第一批固体（纯 Anorthite）出现**，此时固体量趋近于 0 |
| **1400 °C** | An + L；残余熔体 An₆₃Di₃₇；固体 46 %（用杠杆规则，同上表反读） |
| **1350 °C** | An + L；残余熔体 An₅₆Di₄₄；固体 54 % |
| **1274 °C** | **最后一滴熔体存在**，其成分为共结成分 An₄₂Di₅₈；此时残余熔体占 35 %。在这个**恒定温度**下，剩余熔体一次性同时结晶出 An + Di（共结连生体），直至熔体耗尽 |
| **1200 °C** | 全固态：An + Di 两种矿物，总比例回到 80 : 20 |

**要点**：
- 冷却过程中**液体成分沿液相线向共结点移动**（讲义中的"红线"）。
- **Di 在 1274 °C 之前完全不结晶**；所有 Di 都在共结温度那一瞬间（等温）结晶出来。老师："there'll be no diopside formed until this point, and then you would crystallize all of the diopside over a short temperature range."
- 共结结晶产生的 An+Di 连生结构在岩石薄片中可以识别，是判断共结结晶的证据。

### 2.6 布朗尼类比 (Brownie analogy) 及其局限

**类比**：80 g 巧克力 + 20 g 黄油（$X_{\text{choc}} = 0.8$，$X_{\text{butter}} = 0.2$）。

| 阶段 | 状态 | 对应相图 |
|---|---|---|
| 1 | 固体巧克力 + 固体黄油 | 全固态（solidus 以下） |
| 2 | 部分熔融（黄油先化） | 少量熔体 |
| 3 | 部分熔融（熔体更多） | 更多熔体 |
| 4 | 全部熔化，单一液体 | liquidus 以上 |

**类比在冷却时失效**（slides 明确强调）：巧克力–黄油液体冷却后**不会**回到状态 (1) 的两种分离固体（会变成布朗尼那种非平衡的混合物）。而**岩石的冷却严格是加热的逆过程**，在平衡条件下会重新结晶为两种固体矿物 An + Di。这是"平衡"这个前提的重要性所在。

### 2.7 从二元体系到真实岩石

真实岩石含**多于两种**矿物，但**同样的原理成立**：

- **第一滴熔体出现在共结温度**；
- **对给定的一套矿物组合，第一滴熔体的成分是固定的，与各矿物的相对比例无关**。

例子：
- **辉长岩 (Gabbro)**：斜长石 (plagioclase) + 辉石 (pyroxene) ← 就是 An–Di 二元体系的原型
- **花岗岩 (Granite)**：斜长石 + 碱性长石 (alkali feldspar) + 石英 (quartz) + 云母 (mica) ← 四组分体系，但共结原理不变

### 2.8 地幔熔融与玄武岩的产生

**极简图景**：地幔由**橄榄岩 (peridotite)**（主要是橄榄石 olivine + 辉石 pyroxene）组成。当地幔开始熔融，产生的**共结熔体的成分就是玄武岩 (basalt)**。

$$\text{Peridotite (mantle)} \xrightarrow{\ \text{partial melting}\ } \text{Basalt (melt)} + \text{residual peridotite}$$

熔体**密度小、有浮力 (buoyant)**，上升穿过地幔和地壳，最终喷出成为玄武岩。

**玄武岩形成的三种主要构造背景**（转写中老师展开讲的）：

1. **洋中脊 / 扩张脊 (spreading ridge)** —— **减压熔融 (decompression melting)**。地幔之上地壳极薄，地幔物质上涌时压力下降而发生熔融，产生新的洋壳。
2. **热点火山作用 (hotspot volcanism)** —— 地幔中的对流上升（地幔柱），热物质上升导致熔融；地壳板块在热点之上移动，形成**火山岛链**（如夏威夷）。
3. **岛弧火山作用 (arc volcanism)** —— **助熔剂熔融 / 流体致熔 (flux melting)**。俯冲板片 (subducting slab) 释放流体（主要是 H₂O），降低地幔楔的固相线温度，诱发熔融。

老师本人研究的火山（Canary Islands / La Palma、Hawaii、Etna）都属于上述体系。

**关键地球化学后果**：**部分熔融程度 (degree of partial melting, F) 不同 → 微量元素浓度差别巨大**。老师原话大意：如果某元素强烈偏好固体（相容元素），那么在部分熔融初期熔体中该元素**极度贫乏**，只有熔融了大部分岩石之后熔体中的浓度才会升上来；反之不相容元素在**小程度熔融**的熔体里被极度富集。这是 REE 能反演熔融过程的物理基础。

### 2.9 稀土元素 (REE) 的基本性质

**定义与范围**：
- REE 又称**镧系元素 (lanthanides)**，第一个元素是**镧 La (Z = 57)**，到**镥 Lu (Z = 71)**。
- 讲义/转写中老师给的更宽口径：原子序 **57–71**（4f 轨道填充）与 **89–92**（5f 轨道，即锕系的一部分）。
- **钷 Pm (Z = 61) 在自然界不存在**（无稳定同位素），因此 REE 图上永远缺这一格。
- 习惯划分：**LREE（轻稀土）** La–Sm/Eu；**HREE（重稀土）** Gd–Lu。

**周期表位置与电子构型**（回顾 Lecture 2）：
- REE 填充的是 **f 轨道**。周期表中它们被"抽出来"单独排在下方，正是因为**f 电子是非成键电子 (non-bonding electrons)**，被外层电子屏蔽。
- 老师的比喻非常好记：REE 就像周期表上的**一条死胡同 / 小巷 (a side street, a closed cul-de-sac)** —— 你可以往里塞进越来越多的电子，而**化学性质几乎不变**。常规周期表描述的是外层电子如何填充、外层电子决定化学键性质；f 电子不参与成键，所以 REE 是这个规律的例外。
- 结果：**REE 之间化学性质高度一致，它们"成群结队"一起行动 (they all go on block, they all go together)**，这使它们成为审视大尺度地球化学过程的强大工具。

**电子构型算例（Sm，Z = 62）**：

```
Sm 原子:   [Xe] 4f⁶ 6s²
Sm³⁺ 离子: [Xe] 4f⁵          （先失去 2 个 6s 电子，再失去 1 个 4f 电子）
```

**两个重要例外**：

```
Eu 原子:   [Xe] 4f⁷ 6s²
Eu²⁺ 离子: [Xe] 4f⁷          ← 半满 f 亚层，特别稳定 → Eu 常以 2+ 存在
Eu³⁺ 离子: [Xe] 4f⁶
```

- **Eu (Z = 63)** 常以 **Eu²⁺** 出现（因为 Eu²⁺ 的 4f⁷ 是半满构型，额外稳定）。这是**铕异常 (Eu anomaly)** 的根源。
- **Ce (Z = 58)** 可以以 **Ce⁴⁺** 出现（Ce⁴⁺ 为 [Xe] 空 f 壳层，也较稳定）。这在氧化环境中重要（**铈异常 Ce anomaly**）。
- 除 Eu 和 Ce 外，**所有 REE 最稳定的离子都是 3+**。

**镧系收缩 (Lanthanide contraction)**：

> **3+ REE 离子的离子半径随原子序数 Z 增大而稳定减小。**
>
> 原因：**f 轨道电子不能完全屏蔽 (do not completely shield) 原子核的电荷**。随着 Z 增大、核内质子数增多，核电荷增强，电子云被拉得更近，离子半径因此收缩。

$$r(\text{La}^{3+}) > r(\text{Ce}^{3+}) > \cdots > r(\text{Yb}^{3+}) > r(\text{Lu}^{3+})$$

这条平滑的半径变化是 REE 一切"平滑配分曲线"的物理基础：**REE 的化学行为只受一个变量——离子半径——系统性地调控**（老师："The only control being the ionic radius, which has a small control, but that's a **systematic** thing."）。

**老师明确点出的"全课三大要点"**（transcript 原话："perhaps the three things to remember"）：
1. **REE 的离子半径随原子序数增大而减小**；且 f 电子非成键，**REE 之间化学性质高度相似**，只有 Eu（2+）和 Ce（4+）是例外，其余都是 3+。
2. **如何使用相图**（相图判读 + 杠杆规则）。
3. **分配系数 D** 是关键数字。

### 2.10 奇偶丰度与"归一化" (Normalization)

**问题**：REE 在地幔或球粒陨石中的**实际浓度**画出来是**锯齿形 (zigzag)** 的。

**原因（回到 Lecture 1）**：**Oddo–Harkins 规则** —— 偶数 Z 的核素比相邻奇数 Z 的核素**更稳定、丰度更高**（"the nucleus is more stable with an even number of nuclei compared with an odd number"）。这是**核合成 (nucleosynthesis)** 留下的印记，与地球上的化学过程无关。

**解决办法：球粒陨石归一化 (chondrite normalization)**

$$\left[\text{REE}\right]_N = \frac{[\text{REE}]_{\text{sample}}}{[\text{REE}]_{\text{CI chondrite}}}$$

- 分子：样品（如地幔、玄武岩）中该 REE 的浓度（ppm）
- 分母：**CI 碳质球粒陨石 (CI carbonaceous chondrite)** 中同一 REE 的浓度
- **CI 球粒陨石代表太阳系原始（未分异）物质的成分**，因此它也带有相同的奇偶锯齿

**效果**：相除后，来自核合成的锯齿被**完全抵消**，剩下的就是**纯粹由地球内部化学过程（熔融、结晶、分异）造成的信号** —— 曲线变得平滑，任何"折点"或"异常"都有地球化学意义。

**绘图约定**：
- **纵轴用对数坐标 (logarithmic scale)** —— 因为 REE 浓度跨越几个数量级，且分配过程是乘性的。
- **横轴按原子序数递增排列**（La → Lu，即 LREE 在左、HREE 在右）。
- **未分异地幔 / 球粒陨石本身归一化后是一条水平直线，值 = 1**。

### 2.11 矿物–熔体分配系数 (Mineral/Melt Partition Coefficient, D)

**定义**（Lecture 3 讲的是两种液体间的分配，本周推广到**矿物与熔体之间**）：

$$\boxed{\ D_i^{\text{mineral/melt}} = \frac{C_i^{\text{mineral}}}{C_i^{\text{melt}}}\ }$$

- $C_i^{\text{mineral}}$：元素 $i$ 在**矿物**中的浓度（wt% 或 ppm）
- $C_i^{\text{melt}}$：元素 $i$ 在**熔体**中的浓度（同一单位）
- **D 是两个浓度之比，因此无量纲 (no units)**。分子分母单位必须一致。
- 通常写作 $^{\text{olv}}D_{\text{Ni}}$ 或 $D_{\text{Ni}}^{\text{olv/melt}}$。老师说 D 大概取自 "**D**istribution"（分配/分布）。

**算例 1：镍在橄榄石/熔体之间**

```
橄榄石中 Ni = 1 wt%
熔体中  Ni = 0.1 wt%

D_Ni^(olv/melt) = 1 / 0.1 = 10
```

→ Ni 在橄榄石中的浓度是熔体中的 10 倍。

**算例 2：镥在橄榄石/熔体之间**

```
橄榄石中 Lu = 0.01 ppm
熔体中  Lu = 1 ppm

D_Lu^(olv/melt) = 0.01 / 1 = 0.01
```

**分配的物理机制**：分配之所以发生，是因为**矿物晶格 (mineral lattice) 对某种离子是"友好"还是"不友好"，取决于离子的大小与电荷、以及晶格中格位 (site) 的大小与电荷**。离子半径与格位半径匹配、电荷匹配 → 容易替代进去 → D 大。

**相容 vs 不相容**：

| | 判据 | 含义 | 老师的说法 |
|---|---|---|---|
| **相容元素 (compatible)** | $D > 1$ | 元素偏好待在**矿物**里 | "compatible means **it stays in the rock**" |
| **不相容元素 (incompatible)** | $D < 1$ | 元素偏好待在**熔体**里 | "incompatible means **it jumps into the melt**"（熔体一形成就立刻跳进去） |

注意措辞："Ni is **compatible in olivine**"（相容性总是**相对于某个矿物**而言）。

**D 的实用价值**：只要知道 D 和其中一相的浓度，就能算出另一相的浓度。老师："from **one** concentration together with the partition coefficient, you can infer and calculate what the concentration of nickel will be in the olivine."

$$C^{\text{mineral}} = D \times C^{\text{melt}} \qquad\qquad C^{\text{melt}} = \frac{C^{\text{mineral}}}{D}$$

### 2.12 REE 在各矿物中的分配系数模式

Slides（引自 White, *Geochemistry*）给出玄武质熔体中 olivine、pyroxene、plagioclase、garnet、spinel、amphibole 的 REE 分配系数曲线。**四条判读规则**：

1. **曲线沿 REE 序列平滑变化** —— 因为离子半径平滑变化（镧系收缩）。
2. **Eu 是例外** —— 因为它常以 2+ 而非 3+ 存在。**在斜长石中这个异常特别明显**（正异常）。
3. **在大多数矿物中，所有 REE 都是不相容的 (D < 1)** —— 即 REE 偏好液体。
4. **在大多数矿物中，La 比 Lu 更不相容** —— 因为 **La³⁺ 比 Lu³⁺ 大**，更难塞进晶格格位。老师总结："**the smaller the ionic radius, the more preference these elements have for staying in the rock phase**."（半径越小越倾向留在固相。）
5. **分配系数本身是比值，所以不需要归一化就已经是平滑曲线**（与浓度图不同 —— 浓度图必须先归一化才平滑）。

**对比记忆的两个极端矿物**（slides 上的示意）：

```
olivine  : La = 10⁻⁶ ppm ,  Lu = 0.01 ppm      → 对所有 REE 都极度不相容
garnet   : La = 0.001 ppm,  Lu = 10 ppm        → LREE 不相容，HREE 强烈相容
MELT     : La = 1 ppm    ,  Lu = 1 ppm
```

→ **石榴子石 (garnet) 是 REE 分配的关键矿物**：它把 HREE 牢牢锁在残余固体里，从而让熔体的 REE 曲线变得非常"陡"。

---

## 三、公式与图表

### 3.1 核心公式汇总

**(1) 熔融的热力学判据**

$$G_{\text{liquid}} < G_{\text{solid}} \quad\Longleftrightarrow\quad \Delta G_{\text{melting}} < 0$$

**(2) 杠杆规则 (Lever Rule)**

在两相区，沿等温连结线取三点：$A$ = 固相成分、$B$ = 体系总成分、$L$ = 液相成分。

$$f_{\text{liquid}} = \frac{AB}{AL},\qquad f_{\text{solid}} = \frac{BL}{AL},\qquad f_{\text{liquid}} + f_{\text{solid}} = 1$$

用横轴数值表示（以 $X_{\text{Di}}$ 为例，$A$ 为纯 An 即 $X_{\text{Di}}=0$）：

$$f_{\text{liquid}} = \frac{X_{\text{Di}}^{\text{bulk}} - X_{\text{Di}}^{\text{solid}}}{X_{\text{Di}}^{L} - X_{\text{Di}}^{\text{solid}}} = \frac{X_{\text{Di}}^{\text{bulk}}}{X_{\text{Di}}^{L}}$$

**(3) 分配系数**

$$D_i = \frac{C_i^{\text{mineral}}}{C_i^{\text{melt}}} \qquad (\text{无量纲})$$

$$D > 1 \Rightarrow \text{compatible（进矿物）};\qquad D < 1 \Rightarrow \text{incompatible（进熔体）}$$

**(4) 总分配系数 / 体系分配系数 (Bulk partition coefficient)**

$$\boxed{\ D_{\text{bulk}} = x_1 D_1 + x_2 D_2 + x_3 D_3 + \cdots = \sum_j x_j D_j\ }$$

- $x_j$：矿物 $j$ 在岩石（源区）中的**质量/体积分数**，$\sum x_j = 1$
- $D_j$：该元素在矿物 $j$ 与熔体之间的分配系数

例（Ti，源区 50% olivine + 30% opx + 20% cpx）：

$$D^{\text{bulk}}_{\text{Ti}} = 0.5\,{}^{\text{olv}}D_{\text{Ti}} + 0.3\,{}^{\text{opx}}D_{\text{Ti}} + 0.2\,{}^{\text{cpx}}D_{\text{Ti}}$$

**(5) 由源区成分求熔体成分（Practical 采用的近似）**

$$D_{\text{bulk}} = \frac{C^{\text{mantle (solid)}}}{C^{\text{liquid}}} \quad\Longrightarrow\quad C^{\text{liquid}} = \frac{C^{\text{mantle}}}{D_{\text{bulk}}}$$

若把地幔的 REE 归一化丰度都取为 **1**（即地幔 = CI 球粒陨石），则：

$$\boxed{\ \left(\text{Liquid}/\text{CI}\right) = \frac{1}{D_{\text{bulk}}}\ }$$

> **重要提示**：这是一个**近似**（Practical 原文写 "As an approximation"）。它相当于假设熔体与残余固体平衡、且熔融程度 $F$ 很小。
> *（超纲补充，便于理解）* 完整的**批式熔融 (batch melting)** 方程为
> $$\frac{C^{L}}{C^{0}} = \frac{1}{D_{\text{bulk}} + F(1 - D_{\text{bulk}})}$$
> 其中 $F$ 是熔融的质量分数。当 $F \to 0$ 时即退化为 $C^L/C^0 = 1/D_{\text{bulk}}$，正是 Practical 用的式子。本周考试只要求会用 $1/D_{\text{bulk}}$。

### 3.2 关键图表判读方法

#### 图 A：Anorthite–Diopside 二元共结相图

**判读五步法**（考试标准流程）：

1. **确认坐标轴方向**。横轴到底是 $X_{\text{Di}}$ 还是 $X_{\text{An}}$、从左到右是增还是减 —— **Practical Feedback 明确警告"the x axis is reversed compared with the version on the previous page"**。先在轴上标出 0/20/40/60/80/100，转写中老师也说 "even though it's got no numbers, **you have to know what these numbers are**"。
2. **在横轴上标出体系总成分**（B 点），从该点画一条**垂直线**向上。
3. **在目标温度画一条水平线**，看交点落在哪个相区 → 写出**存在的相**。
4. **求熔体成分**：从水平线与**液相线**的交点**垂直下引到横轴**，读数。
5. **求相的比例**：用**杠杆规则**（只在两相区适用；单相区 100%）。

**特殊情形**：
- 总成分**恰好等于共结成分**（An₄₂Di₅₈）：整块岩石在 1274 °C 一次性全部熔化（像纯矿物一样有"单一熔点"）。
- 总成分为**纯端元**（纯 An 或纯 Di）：在其自身熔点熔化，无部分熔融区间。
- 位于共结点**右侧**（$X_{\text{Di}} > 0.58$）：两相区是 **Di + L**，此时 A 点应取 **纯 Di 端**（$X_{\text{Di}} = 1$）而不是 An 端。

**讲义中的判读示例**（Feedback 第 1 页图，bulk = An₈₀Di₂₀）：

- *1550 °C*：落在**单相区 (L)**。垂直下引读横轴 → 液体成分 **An₈₀Di₂₀**（不意外，就是体系成分本身）。
- *1350 °C*：落在**两相区 (An + L)**。**固相成分 = 100% 钙长石 (An₁₀₀)**；液相成分由液相线垂直下引 → **约 An₅₅Di₄₅**（$X_{\text{Di}} = 0.45$）。
- 比例（杠杆规则，图上量长度）：$AB = 20\ \text{mm}$、$BL = 30\ \text{mm}$、$AL = 50\ \text{mm}$
  $$f_{\text{liquid}} = \frac{AB}{AL} = \frac{20}{50} = 40\% \qquad f_{\text{An}} = \frac{BL}{AL} = \frac{30}{50} = 60\%$$
  → **体系 40% 是液体，60% 是固体钙长石**。

> ⚠️ **讲义标题排版陷阱**：slides 上这张图的小标题写作 "Example: Bulk composition An₂₀Di₈₀"，但从杠杆规则的实际数值（$AB$ 对应 $X_{\text{Di}}\approx 0.2$）和 Feedback 第 1 页（"Liquid only: Composition of liquid: **An₈₀Di₂₀**"）可知，**该图实际讨论的体系是 An₈₀Di₂₀**，标题里的 "An₂₀Di₈₀" 是坐标轴反转造成的写法差异。**做题时以你手上那张图的轴标为准，不要死记标题。**

#### 图 B：REE 离子半径 vs 原子序数

- 横轴：原子序数 $Z$（La 57 → Lu 71）
- 纵轴：3+ 离子半径
- **要点**：一条**单调下降**的平滑曲线（镧系收缩）。
- **判读**：Eu 和 Ce 因为常以 2+ / 4+ 存在，其"有效半径"偏离 3+ 系列的趋势线（Eu²⁺ 更大，Ce⁴⁺ 更小）。

#### 图 C：REE 丰度图 —— 归一化前 vs 归一化后

- **图 A（归一化前）**：纵轴为地幔或 CI 球粒陨石中 REE 的**实际浓度**（对数），横轴 La → Lu。曲线呈**锯齿状 (zigzag)**，偶数 Z 高、奇数 Z 低（核合成印记）。Pm (Z=61) 处缺一格。
- **图 B（归一化后）**：纵轴为 **地幔浓度 / CI 球粒陨石浓度**（对数）。锯齿消失，曲线平滑。
- **判读**：归一化后若仍有起伏（斜率、异常），**必然是地球内部过程造成的**，可以解释。

#### 图 D：REE 分配系数图（$D$ vs 原子序数）

- 纵轴：$D$（**对数坐标**），横轴：$Z$（La 57 → Lu 71）
- 一条水平参考线 $D = 1$：**线以上相容，线以下不相容**。
- 各矿物曲线的形态（本周必须能默画）：

| 矿物 | 曲线形态 | 物理原因 |
|---|---|---|
| **Olivine (橄榄石)** | 位置最低（$D \sim 10^{-3}$–$10^{-2}$），整体近水平略向 HREE 上升 | 孤立四面体结构，格位小且刚性，REE 几乎进不去 |
| **Orthopyroxene (斜方辉石)** | 比橄榄石高一个量级，向 HREE 上升 | 链状硅酸盐，格位稍大 |
| **Clinopyroxene (单斜辉石)** | 更高（$D \sim 0.05$–$0.6$），中重稀土处形成**平缓的驼峰** | 含 Ca²⁺（大离子），结构被"撑开" |
| **Plagioclase (斜长石)** | 整体很低且**向 HREE 下降**（La 比 Lu 相容！），Eu 处有**极显著的正尖峰**（$D_{\text{Eu}} > 1$） | Ca²⁺ 格位大，偏好大的 LREE；Eu²⁺ 与 Ca²⁺ 电荷半径都匹配 |
| **Garnet (石榴子石)** | **斜率极陡**，从 La 的 0.026 一路升到 Lu 的 11.9，跨越 $D=1$ 线 | 8 次配位的小格位，强烈偏好小半径的 HREE |

- **Eu 判读**：斜长石 → **正 Eu 异常 (positive Eu anomaly)**（尖峰向上）；辉石 → **轻微负 Eu 异常**。

#### 图 E：熔体的 REE 配分曲线（Practical 的最终产物）

因为 $(\text{Liquid}/\text{CI}) = 1/D_{\text{bulk}}$，**熔体的配分曲线是分配系数曲线的镜像（倒数）**：

- 分配系数曲线**上升** → 熔体曲线**下降**
- 分配系数曲线上的**正异常** → 熔体曲线上的**负异常**（反之亦然）

**这是本周最需要"想通"的一句话**（Feedback 原话："Have you noticed that the melt composition is the **inverse (mirror image)** of the partition coefficient?"）。

---

## 四、课堂补充（transcript 中有、slides 上没有的内容）

### 4.1 讲师与课程安排

- **Mike Burton** 接手 Lecture 7 与 Lecture 8（此前由 Marianne 讲授）。
- 他是**火山学家 (volcanologist)**，主要研究**岩浆气体 (magmatic gas)** —— 在喷发期间测量火山气体，反演火山系统内部正在发生什么，用于**火山活动预报**。这些脱气 (degassing) 现象是岩浆上升、岩浆形成、岩浆聚集等一系列过程的结果，与本节课直接相关。
- 他主要教四年级/硕士的科学传播课与四年级野外实习（**La Palma，加那利群岛的火山岛**）。
- Blackboard 上他重新上传了一版**文件名末尾带 "MB"** 的讲义（含更新的链接）。
- 有一个 **QR code 用于登记座位**，请务必使用。

### 4.2 老师对"难度"的直白提醒（重要）

> "These tricks are invaluable for a geochemist, and **they will be part of the exam at the end of this course**. So it's imperative that you understand how these phase diagrams work."
>
> "This is one of those times where **it will not be simple. It will not be 2 plus 2 equals 4.** There's multiple steps needed. You need to pay attention... and think very carefully **over and over again** in order to get this straight."
>
> "It's also **completely feasible**. Once you've got your head around it, it's incredibly powerful and very useful. But you do need to **overcome a certain bump** before you get there."

他还说："What I've just told you is basically all the information in one go and **you will not have understood it all**. So I'm going to go over this **again and again and again** during the course of this lecture about three or four times, and then we'll go over it in the practical." → **讲义里那一大串重复的 "PARTIAL MELTING" 页不是排版错误，是刻意的重复教学**。

**"有问题就在 practical 上问"** —— 他明确说 practical 是提问的最佳时机。

### 4.3 老师给的"机械化规则"教学策略

他先给"照做就对"的操作步骤，之后才解释原理：

> "I'm going to just give you a rule that **if you follow this rule, you will get the right answer**. Afterwards, I'll give you the explanation about why it works, but I think the easiest thing to do to start with is just to give you a process to follow."

所以考试策略：**先把 $f_L = AB/AL$、$f_S = BL/AL$ 背成肌肉记忆**，理解（质量守恒）作为验证手段。

### 4.4 关于"哪些量固定、哪些量变"的关键洞察

> "**A and B, once we set AB, that's it. AB is always going to be 20%**（或任何初始成分）**. Now the BL length changes. And so therefore the AL length changes. Therefore all the numbers change as we go up the melting point.**"

这是解题时最容易混乱的地方：升温过程中 **A 点（纯固相端元）和 B 点（体系总成分）都不动**，只有 **L 点沿液相线移动**。

### 4.5 一个真实实验的例子（老师亲身经历）

他上周刚在**牛津郡的 Diamond Light Source（英国同步辐射光源）** 做实验：用**高压红外透明容器 (high-pressure infrared-transparent vessel)** 熔化一种成分与钙长石非常相似的材料（转写中记作 "cyanite"，很可能是 **kyanite 蓝晶石** Al₂SiO₅ 的转写误差），同时用 **X 射线成像做层析重建 (tomographic reconstruction)**，从而**实时看到相图在眼前展开**。

→ 说明相图不是抽象概念，是可以实验直接观测的。

### 4.6 老师对共结点的直觉解释

> "This is slightly counterintuitive, but this is just what we find by experiment. And in a way, it makes sense that what happens is that **one phase becomes unstable and melts together**."

即：共结现象是**实验事实**，理论上可以理解为在共结成分处两个固相同时与熔体达到平衡。老师承认"有点反直觉"，不要求硬推。

### 4.7 关于"熔体成分"符号的澄清（易混淆点）

老师专门澄清：**"L" 在相图上表示 liquid melt，"L" 和 "melt" 完全可以互换，是同一个东西。**

以及：当我们说熔体成分是 "An₅₆Di₄₄" 时，**这不是岩石成分，也不意味着熔体里有钙长石晶体**。它只是说**熔体的化学成分，等价于把 56% An + 44% Di 的晶体混合物熔化后得到的成分**。他反复强调："**This is all molten. This is not the rock composition. This is just the relative chemical contributions.**"

**硅酸盐熔体的性质**（slides + 转写）：
- 硅酸盐熔体**没有晶体的有序结构 (not ordered into crystalline structures)**；
- 熔体**可以有任意成分，只要满足电荷平衡 (charge balance)**，**不受特定矿物化学式的限制**；
- 因此熔体成分可以**连续演化**。

### 4.8 关于 REE 的额外解释

- **"死胡同"比喻**：4f/5f 是非成键电子，被外层壳层屏蔽，"they are kind of almost like a side street, **a closed cul-de-sac on the periodic table**, where you can fill up a bunch of electrons without actually changing the chemistry."
- **Sm 的成键电子澄清**：老师特别指出，samarium 参与化学成键的**不是** 4f 上的 5 个电子，**而是 6s 上的电子**。
- **为什么 REE 是强大工具**："they all go on block, they all go together, giving them a very powerful way to **interrogate large-scale geochemical processes in the solar system and on the Earth**."
- **半径—相容性的核心因果链**（老师明确说出）：**原子序数↑ → 质子数↑ → 核电荷↑ → 电子被拉近 → 离子半径↓ → 更容易挤进矿物晶格 → D↑（更相容）**。

### 4.9 部分熔融程度与微量元素（老师额外展开）

> "That **different degrees of partial melting** is really, really important when we consider the relative proportions of compatible and incompatible elements... if you have an element that is very favourable to the rock, as melting occurs, then **the melt will be very impoverished in those elements at the beginning of partial melting** because they'll all stay in the rock. It's only when you've melted the majority of the rock will you start to see higher proportions in the melt itself."

反过来：**不相容元素在小程度部分熔融的熔体中被极度富集** —— 这正是 Practical 中 "REE contents of the melts are **high** compared with the (unmelted) mantle"（熔体的 REE 含量远高于未熔融的地幔）的原因，也是稀土矿床形成的地球化学基础。

### 4.10 地幔的长期亏损（讲到最后一张图）

老师讲了 Elements Magazine 那篇 PDF 里的一张图（REE 在上地壳、下地壳、平均地壳、**亏损上地幔 (depleted upper mantle)** 中的相对丰度）：

> "Over Earth's history, when Earth was first formed, there was a **pristine mantle**. But over Earth's history, obviously there's been a lot of processing and a lot of production of new volcanoes, new basalt. **That's depleted the upper mantle.**"

即：地幔持续熔融、把不相容元素（含 LREE）不断抽走送进地壳 → **上地幔逐渐变得"亏损 (depleted)"**，地壳则相对富集不相容元素。这是"地球化学分异"的长期后果，为后续讲同位素演化埋下伏笔。

---

## 五、Practical 要点

### 5.1 Practical 目标

1. 学会**用相图解读岩石的部分熔融**；
2. 理解 **REE 为何是强大的微量元素示踪剂**：
   - 研究 REE 在不同矿物中的行为；
   - 用 REE 反演**地幔中的熔融过程**。

### 5.2 Part A：相图判读（体系 = 70% Anorthite + 30% Diopside）

**先做的事**：在相图上**标出四个相区** —— Liquid（单相区）；Diopside + Anorthite；Diopside + Liquid；Anorthite + Liquid（三个两相区）。

**Table 1 完整答案与计算过程**（$X_{\text{Di}}^{\text{bulk}} = 0.30$，落在共结点 $X_{\text{Di}}=0.58$ 左侧 → An-rich 一侧，两相区为 An + L，故 A 点取 An₁₀₀ 即 $X_{\text{Di}}=0$）：

| 温度 | 存在的相 | 各相比例 | 液相成分 |
|---|---|---|---|
| **1250 °C** | Anorthite + Diopside | 70% An, 30% Di | n/a（无液体） |
| **1300 °C** | Anorthite + Liquid | **55% Liq, 45% An** | **An₄₅Di₅₅** |
| **1400 °C** | Anorthite + Liquid | **79% Liq, 21% An** | **An₆₂Di₃₈** |
| **1500 °C** | Liquid | 100% Liq | **An₇₀Di₃₀** |

**计算过程（务必自己能复现）**：

*1300 °C*，液相线上读得 $X_{\text{Di}}^{L} = 0.55$：
```
AB = 0.30 − 0    = 0.30
AL = 0.55 − 0    = 0.55
BL = 0.55 − 0.30 = 0.25

%Liquid    = AB/AL = 0.30 / 0.55 = 0.545 → 55 %
%Anorthite = BL/AL = 0.25 / 0.55 = 0.455 → 45 %
```

*1400 °C*，$X_{\text{Di}}^{L} = 0.38$：
```
AB = 0.30 ; AL = 0.38 ; BL = 0.38 − 0.30 = 0.08

%Liquid    = 0.30 / 0.38 = 0.789 → 79 %
%Anorthite = 0.08 / 0.38 = 0.211 → 21 %
```

*1500 °C*：在液相线之上，单相区 → 100% 液体，成分 = 体系成分 An₇₀Di₃₀。

*1250 °C*：在固相线之下 → 全固态，两种矿物比例就是体系比例 70:30，没有液体所以"液相成分"填 n/a。

**每一格还要画草图**：1250 °C 画两种晶体；1300 °C 画大量 An 晶体浮在少量熔体中（其实是 55% 熔体 + 45% An）；1400 °C 画少量 An 晶体在大量熔体中；1500 °C 画纯液体。

**问答题标准答案**：

**(a) 首次出现熔体的温度（共结温度）？**
→ **1274 °C**。对**任何** An + Di 的混合物，这都是第一滴熔体出现的温度。

**(b) 第一滴熔体的成分？**
→ **An₄₂Di₅₈**（共结成分）。对**任何** An + Di 的混合物都一样。

**(c) 完全熔融的温度？**
→ **1450 °C**。这是体系总成分的垂直线**穿过 Liquid 区与 Liquid+Anorthite 区之间的相界（液相线）**的那一点。
⚠️ **注意对比**：共结温度对所有成分都相同，但**完全熔融温度取决于体系总成分**（讲义主线例子 An₈₀Di₂₀ 是 ~1470 °C，本题 An₇₀Di₃₀ 是 1450 °C）。

**(d) 随温度升高，液体成分如何变化？为什么？**
→ 第一滴液体是共结成分 **An₄₂**。在共结点，**所有 Diopside 加上一部分 Anorthite** 熔化。继续升温，**更多 Anorthite 熔化**，液体成分**逐渐趋近于体系总成分**：
$$\text{An}_{42}\ (1274\,°\text{C}) \to \text{An}_{45}\ (1300\,°\text{C}) \to \text{An}_{62}\ (1400\,°\text{C}) \to \text{An}_{70}\ (1450\,°\text{C})$$

**(e) 两相组合 anorthite + melt 存在的总温度区间？**
→ 从刚过共结点（**1275 °C**）到刚低于完全熔融温度（**1450 °C**），即 **约 175 °C** 的区间。

**(f) 改变 An/Di 比例，这个温度区间怎么变？**

| 体系成分 | 两相区温度跨度 | 两相组合 |
|---|---|---|
| 90% Anorthite | 约 **250 °C** | An + Liquid |
| 70% Anorthite | 约 **175 °C** | An + Liquid |
| 50% Anorthite | 约 **50 °C** | An + Liquid（很接近共结成分 An₄₂，所以区间短） |
| 10% Anorthite | 约 **100 °C** | **Di + Liquid**（越过共结点到了 Di-rich 一侧！） |

**结论**：**部分熔融发生的温度范围随体系成分变化很大**。越接近共结成分，部分熔融区间越窄（成分恰为共结成分时区间 = 0）；越靠近端元成分，区间越宽。

> ⚠️ **10% An 这一栏是最容易做错的**：$X_{\text{An}}=0.10$ 意味着 $X_{\text{Di}}=0.90 > 0.58$，已经跨到共结点右侧，两相组合变成 **Diopside + Liquid**，杠杆规则的 A 点必须改取**纯 Di 端**。

### 5.3 Part B：REE 在不同矿物中的行为

**Table 2：玄武质熔体的 REE 矿物/熔体分配系数**（数据来自 Rollinson, *Using Geochemical Data*）

| REE | Z | Olivine | Orthopyroxene | Clinopyroxene | Plagioclase | Garnet |
|---|---|---|---|---|---|---|
| La | 57 | — | — | 0.056 | 0.148 | 0.026 |
| Ce | 58 | 0.007 | 0.020 | 0.092 | 0.082 | 0.051 |
| Nd | 60 | 0.007 | 0.030 | 0.230 | 0.055 | — |
| Sm | 62 | 0.007 | 0.050 | 0.445 | 0.039 | 0.600 |
| **Eu** | **63** | 0.007 | 0.050 | 0.474 | **1.126** | **1.000** |
| Gd | 64 | 0.008 | 0.090 | 0.556 | 0.031 | 2.100 |
| Tb | 65 | 0.010 | — | 0.570 | — | — |
| Dy | 66 | 0.011 | 0.150 | 0.582 | 0.023 | 4.100 |
| Ho | 67 | — | — | — | — | — |
| Er | 68 | 0.026 | 0.230 | 0.583 | 0.020 | 6.560 |
| Yb | 70 | 0.049 | 0.340 | 0.542 | 0.023 | 11.500 |
| Lu | 71 | 0.045 | 0.420 | 0.506 | 0.019 | 11.900 |

三种矿物的化学式（题目给出，用来解释结构差异）：
```
Olivine        (Mg,Fe)₂SiO₄        —— 岛状硅酸盐 (nesosilicate)，孤立 SiO₄ 四面体
Orthopyroxene  (Mg,Fe)₂Si₂O₆       —— 链状硅酸盐 (inosilicate)，单链
Clinopyroxene  (Mg,Fe)CaSi₂O₆      —— 链状硅酸盐，M2 位被 Ca 占据
```

**问答题标准答案与解题思路**：

**(a) REE 在橄榄石和辉石中是相容还是不相容？为什么？**
→ **不相容 (incompatible)**。因为**所有分配系数都小于 1**（olivine 0.007–0.049；opx 0.020–0.420；cpx 0.056–0.583）。
*解题思路：只看 D 与 1 的大小关系，一句话说清即可。*

**(b) 橄榄石和斜方辉石化学式很相似，为什么 D 差别这么大？**
→ 二者**原子排列方式 (arrangement of atoms) 不同**：
- **橄榄石中 SiO₄ 四面体是孤立的 (isolated)**；
- **辉石中 SiO₄ 四面体连成链 (chains)**。

不同的硅酸盐结构意味着**阳离子格位的大小不同**；**辉石结构能比橄榄石多容纳一点 REE**，因此 opx 的 D 系统性地高于 olivine（约高一个量级）。

*解题思路：化学式相似 ≠ 结构相似。回答必须落到**晶体结构 / 格位大小**上，不能只说"成分差不多"。*

**(c) 斜方辉石与单斜辉石最显著的化学差异是什么？为什么会影响 D？**
→ 差异是**单斜辉石含有大量 Ca**（对比化学式：opx (Mg,Fe)₂Si₂O₆ vs cpx (Mg,Fe)**Ca**Si₂O₆）。**Ca²⁺ 是一个大离子 (large ion)**，它的存在**把结构"撑开" (opens up the structure)**，从而允许更多**大半径的 REE 离子**被容纳进去。所以 cpx 的 D 明显高于 opx。

*解题思路：找化学式差异 → 指出关键离子的大小 → 联系到晶格格位 → 联系到 D。*

**(d)** 把 plagioclase 和 garnet 的数据加到图上（画图题）。

**(e) REE 在石榴子石中是相容还是不相容？**
→ **混合情形 (a mixture)**：**轻稀土 LREE 不相容 ($D<1$，如 La 0.026、Ce 0.051)**；**重稀土 HREE 相容 ($D>1$，如 Gd 2.10、Dy 4.10、Er 6.56、Yb 11.5、Lu 11.9)**。分界大致在 Eu/Gd 附近（Eu 的 $D = 1.000$ 恰好等于 1）。

**(f) REE 在斜长石中是相容还是不相容？**
→ **基本上全部不相容 ($D<1$)**，唯有 **Eu 略微相容（$D = 1.126$，刚刚超过 1）**。

**(g) 为什么 Eu 不符合斜长石的主趋势？**
→ **Eu 倾向以 Eu²⁺ 存在**，而其他所有 REE 都是 3+ 阳离子，所以它的行为不同。**Eu²⁺ 在大小和电荷上都与 Ca²⁺ 相似，因此可以轻易替代进斜长石的 Ca²⁺ 格位**，导致它的分配系数比其他 REE 高得多。

（补充记忆：斜长石 CaAl₂Si₂O₈ 里的 Ca²⁺ 格位 —— Eu²⁺ 电荷相同、半径相近 → 完美替代。这是"**离子半径 + 电荷双匹配**"原则的教科书例子。）

**(h) 什么是 Eu 异常？哪些矿物显示负 Eu 异常？**
→ Eu 行为的偏离称为 **Eu 异常 (Eu anomaly)**。斜长石表现为**正 Eu 异常 (positive Eu anomaly)**。**斜方辉石和单斜辉石显示负 Eu 异常 (negative Eu anomaly)**，不过它们的异常**远不如斜长石的正异常显著**。

**(i) 哪些矿物中 La 比 Lu 更相容？哪些相反？**
→ **La 比 Lu 更相容的：斜长石 (plagioclase)**（$D_{\text{La}} = 0.148 > D_{\text{Lu}} = 0.019$）。
→ **Lu 比 La 更相容的：橄榄石、斜方辉石、单斜辉石、石榴子石**（曲线向 HREE 上升）。

*记忆法*：斜长石的 Ca²⁺ 格位**大**，所以偏好**大**的 LREE；石榴子石的格位**小**，所以偏好**小**的 HREE。**格位大小决定偏好谁**。

### 5.4 Part C：用 REE 理解地幔熔融过程

**背景逻辑链**：
熔体携带其源区矿物组合的"指纹" → 而**地幔橄榄岩的矿物组合随深度（压力）变化** → 因此**测量喷发熔体的 REE 丰度可以反演熔融发生的深度**。

**关键的深度—矿物对应关系**：

| 深度 / 压力 | 地幔橄榄岩相 | 铝相矿物 |
|---|---|---|
| **浅部 / 低压**（slides 标注 **< 1 GPa**） | **斜长石橄榄岩 (plagioclase peridotite)** | **斜长石 plagioclase** |
| （中等压力，约 1–2.5 GPa，标准补充） | 尖晶石橄榄岩 (spinel peridotite) | 尖晶石 spinel |
| **深部 / 高压** | **石榴橄榄岩 (garnet peridotite)** | **石榴子石 garnet**（斜长石不稳定） |

> Practical 原文："mantle peridotite contains **plagioclase at shallow depths (low pressures)** but at greater depths (high pressures), **plagioclase is not stable and garnet is preferred**."

**(a) 计算高压情形的总分配系数**

**源区矿物比例（题目给定）**：60% olivine + 25% opx + 10% cpx + 5%（低压：plagioclase / 高压：garnet）

**通式**：
$$D^{\text{bulk}}_{i} = 0.60\,{}^{\text{olv}}D_i + 0.25\,{}^{\text{opx}}D_i + 0.10\,{}^{\text{cpx}}D_i + 0.05\,{}^{\text{plag or gnt}}D_i$$

**Ce 的高压完整计算（题目给出的示范式）**：
```
Bulk D_Ce(高压) = (0.60 × 0.007) + (0.25 × 0.020) + (0.10 × 0.092) + (0.05 × 0.051)
                = 0.00420 + 0.00500 + 0.00920 + 0.00255
                = 0.02095  ≈ 0.021
```

**Sm 的高压计算**：
```
= (0.60 × 0.007) + (0.25 × 0.050) + (0.10 × 0.445) + (0.05 × 0.600)
= 0.00420 + 0.01250 + 0.04450 + 0.03000
= 0.09120  ≈ 0.091
```

**Eu 的高压计算**：
```
= (0.60 × 0.007) + (0.25 × 0.050) + (0.10 × 0.474) + (0.05 × 1.000)
= 0.00420 + 0.01250 + 0.04740 + 0.05000
= 0.11410  ≈ 0.114
```

**Gd 的高压计算**：
```
= (0.60 × 0.008) + (0.25 × 0.090) + (0.10 × 0.556) + (0.05 × 2.100)
= 0.00480 + 0.02250 + 0.05560 + 0.10500
= 0.18790  ≈ 0.188
```

**Lu 的高压计算**：
```
= (0.60 × 0.045) + (0.25 × 0.420) + (0.10 × 0.506) + (0.05 × 11.900)
= 0.02700 + 0.10500 + 0.05060 + 0.59500
= 0.77760  ≈ 0.778
```

**（低压情形校验，用 plagioclase 的 D 代入第四项）**：
```
Ce: 0.00420 + 0.00500 + 0.00920 + (0.05 × 0.082 = 0.00410) = 0.02250 ≈ 0.022 ✓
Sm: 0.00420 + 0.01250 + 0.04450 + (0.05 × 0.039 = 0.00195) = 0.06315 ≈ 0.063 ✓
Eu: 0.00420 + 0.01250 + 0.04740 + (0.05 × 1.126 = 0.05630) = 0.12040 ≈ 0.120 ✓
Gd: 0.00480 + 0.02250 + 0.05560 + (0.05 × 0.031 = 0.00155) = 0.08445 ≈ 0.084 ✓
Lu: 0.02700 + 0.10500 + 0.05060 + (0.05 × 0.019 = 0.00095) = 0.18355 ≈ 0.184 ✓
```

**Table 3 完整答案**：

| REE | 低压（含 Plagioclase）$D_{\text{bulk}}$ | 高压（含 Garnet）$D_{\text{bulk}}$ |
|---|---|---|
| Ce | 0.022 | 0.021 |
| Sm | 0.063 | **0.091** |
| Eu | 0.120 | **0.114** |
| Gd | 0.084 | **0.188** |
| Lu | 0.184 | **0.778** |

**"REE 在地幔中总体是相容还是不相容？"**
→ **不相容元素**，因为**所有总分配系数都远小于 1**，说明它们**偏好待在熔体里**。因此：**地幔中产生的少量熔体会有很高的 REE 浓度**。

⚠️ 注意：**即使源区含有对 HREE 强烈相容的石榴子石（$D_{\text{Lu}}^{\text{gnt}} = 11.9$），因为石榴子石只占 5%，加权后的 $D^{\text{bulk}}_{\text{Lu}}$ 仍只有 0.778 < 1**。这说明**矿物比例的权重非常重要** —— 少量的"关键矿物"能显著改变斜率，但通常不足以把总体从不相容翻转成相容。

**(b) 计算熔体的 REE 配分曲线**

**假设**：地幔的 REE 浓度与 CI 球粒陨石相同 → 归一化后**地幔的所有 REE 值都是 1**。

**公式**：
$$D_{\text{bulk}} = \frac{\text{地幔中元素丰度}}{\text{熔体中元素丰度}} \quad\Longrightarrow\quad \text{熔体丰度} = \frac{1}{D_{\text{bulk}}}$$

**Table 4 完整答案（相对 CI 球粒陨石）**：

| REE | 地幔 / CI | 低压熔体 / CI | 高压熔体 / CI |
|---|---|---|---|
| Ce | 1 | **44.61** | **47.87** |
| Sm | 1 | **15.89** | **10.99** |
| Eu | 1 | **8.32** | **8.77** |
| Gd | 1 | **11.87** | **5.33** |
| Lu | 1 | **5.44** | **1.29** |

**计算示范**（用未四舍五入的 $D_{\text{bulk}}$ 更精确；用表 3 的四舍五入值会有 ±0.5% 的小差异）：
```
低压 Lu:  1 / 0.18355 = 5.45  ≈ 5.44
高压 Lu:  1 / 0.77760 = 1.286 ≈ 1.29
高压 Gd:  1 / 0.18790 = 5.32  ≈ 5.33
低压 Gd:  1 / 0.08445 = 11.84 ≈ 11.87
高压 Sm:  1 / 0.09120 = 10.96 ≈ 10.99
```

**结果的图形解读（两条配分曲线的形态）**：

**低压熔体（源区含斜长石）**：
```
Ce 44.6 ──▶ Sm 15.9 ──▶ Eu 8.3 ──▶ Gd 11.9 ──▶ Lu 5.4
                          ↑ 明显的凹陷
```
- **斜率较缓 (shallower slope)**：从 Ce (44.6) 到 Lu (5.4) 只降了约 8 倍。
- **显著的负 Eu 异常 (significant negative Eu anomaly)**：Eu = 8.32 明显**低于** Sm (15.89) 与 Gd (11.87) 之间的内插值（约 13.7）。
- **原因**：斜长石的 $D_{\text{Eu}} = 1.126 > 1$，把 Eu **扣留在残余固体中**，熔体因此贫 Eu。

**高压熔体（源区含石榴子石）**：
```
Ce 47.9 ──▶ Sm 11.0 ──▶ Eu 8.8 ──▶ Gd 5.3 ──▶ Lu 1.3
                          ↑ 轻微凸起
```
- **斜率很陡 (steep slope)**：从 Ce (47.9) 到 Lu (1.3) 下降约 37 倍 —— **HREE 强烈亏损**。
- **原因**：石榴子石对 HREE 强烈相容（$D_{\text{Lu}}^{\text{gnt}} = 11.9$），把 HREE **锁在残余的石榴橄榄岩中**，熔体因此严重贫 HREE。
- **小的正 Eu 异常 (small positive Eu anomaly)**：Eu = 8.77 略**高于** Sm (10.99) 与 Gd (5.33) 的内插值（约 8.16）。

**核心问答：在玄武岩中该找什么特征来论证是高压还是低压熔融？**

| | **高压熔融（源区有 garnet，深部）** | **低压熔融（源区有 plagioclase，浅部）** |
|---|---|---|
| 配分曲线斜率 | **陡 (steep slope)** —— HREE 强烈亏损 | **缓 (shallower slope)** |
| Eu 异常 | **小的正异常 (small positive)** | **显著的负异常 (significant negative)** |
| 判别关键 | (Ce/Yb)ₙ 或 (La/Lu)ₙ 比值大 | Eu 明显下凹 |

**两条必须记住的"顿悟"结论**（Feedback 结尾特别点出）：

1. **熔体的成分是分配系数的倒数（镜像）** —— $C^L/C^0 = 1/D_{\text{bulk}}$。所以看到分配系数图上石榴子石往上翘（HREE 相容），就要立刻反应过来熔体曲线在 HREE 端会往下掉。
2. **熔体的 REE 含量远高于（未熔融的）地幔** —— 因为 $D_{\text{bulk}} \ll 1$，$1/D_{\text{bulk}} \gg 1$（低压 Ce 达 44.6 倍球粒陨石）。这就是"不相容元素在熔体中被富集"的定量表达。

### 5.5 REE 分配系数的三大用途（slides 明确列出）

在讨论**玄武岩的成因 (origin of basalts)** 时，可以用 REE：

1. **判断熔融程度 (extent of melting)** —— 我们是否已经离开了共结点？（熔融程度越低，不相容元素越富集）
2. **判断是否发生地壳混染 (crustal assimilation)** —— 玄武岩从地幔上升穿过地壳时是否混入了地壳物质？能否**仅用地幔熔融**来解释观测到的 REE 丰度？
3. **判断熔融深度 (depth of melting)** —— 地幔源区中存在哪些矿物？（斜长石 → 浅；石榴子石 → 深）

---

## 六、易错点 / 重点难点

### 相图部分

1. **⚠️ 坐标轴方向必须先确认**。Feedback 明确提醒 practical 上那张图的 x 轴与讲义上那张**是反过来的**。slides 上还有一处标题写 "Bulk composition An₂₀Di₈₀" 但实际讨论的是 An₈₀Di₂₀。**每次做题第一件事：在轴上写下 0/20/40/60/80/100，确认哪端是 An 哪端是 Di。**
2. **共结温度 (1274 °C) 对所有成分都相同；完全熔融温度对每个成分都不同。**（An₈₀ → ~1470 °C；An₇₀ → 1450 °C）这两个概念极易混淆。
3. **第一滴熔体的成分永远是共结成分 An₄₂Di₅₈**，与原岩比例无关。学生常错误地以为"An 多的岩石第一滴熔体就富 An"。
4. **杠杆规则要用"对面那一段"**。$f_{\text{liquid}} = AB/AL$（B 到 A 那段，A 是固相端），$f_{\text{solid}} = BL/AL$。用错方向会得到互补的错误答案 —— **快速检查法：B 离 L 越近，液体应该越多**。
5. **两相区在共结点两侧固相端元不同**。$X_{\text{Di}} < 0.58$ → 固相是纯 An，A 点取 $X_{\text{Di}}=0$；$X_{\text{Di}} > 0.58$ → 固相是纯 Di，A 点取 $X_{\text{Di}}=1$。Practical (f) 中 "10% anorthite" 那一栏正是这个陷阱。
6. **升温时 A、B 两点不动，只有 L 点动**。$AB$ 恒等于体系成分值，这是最省时的解题捷径。
7. **熔体成分 "An₅₆Di₄₄" 不代表熔体里有 An 晶体**。它只是化学成分的等价表述。硅酸盐熔体没有晶体结构，只需满足电荷平衡。
8. **完全熔融后继续升温，成分不再变化**（只是变热）。
9. **平衡结晶中，Di 直到 1274 °C 才开始结晶，且在恒温下一次性全部结晶完**。学生常画成 Di 随温度逐渐析出。
10. **布朗尼类比只对熔融有效，对冷却无效**。

### REE 部分

11. **Pm (Z = 61) 自然界不存在**，REE 图上永远缺这一格 —— 不要以为是数据缺失。
12. **Eu 和 Ce 是唯二例外**：Eu 常为 **2+**（[Xe]4f⁷ 半满，稳定），Ce 可为 **4+**。其余 REE 全部是 3+。
13. **Eu 异常的方向要分清**：**斜长石中是正异常**（Eu 被扣留在斜长石里，$D>1$）；**由此产生的熔体中是负异常**。"矿物里正异常 ⇒ 熔体里负异常"，因为熔体是矿物的镜像。
14. **不要把"相容/不相容"当成元素的固有属性** —— 它永远是相对于**某个特定矿物 + 某个特定熔体**的。同一个 Lu 在橄榄石中极不相容 ($D=0.045$)，在石榴子石中极相容 ($D=11.9$)。
15. **归一化的目的是消除核合成留下的奇偶锯齿**（Oddo–Harkins 效应），不是为了"美观"。归一化后的起伏才是地球化学信号。
16. **分配系数图不需要归一化**就已经是平滑的 —— 因为 D 本身就是比值，奇偶效应在分子分母中自动抵消。这一点和浓度图正好相反，考试爱考。
17. **总分配系数是加权和，不是简单平均、更不是乘积**：$D_{\text{bulk}} = \sum x_j D_j$。计算时**别忘了乘以矿物比例**，也别忘了检查 $\sum x_j = 1$（本题 0.60+0.25+0.10+0.05 = 1.00 ✓）。
18. **少量关键矿物可以主导斜率**。5% 的石榴子石就把 $D_{\text{bulk}}^{\text{Lu}}$ 从 0.184 抬到 0.778（4 倍以上），使熔体的 HREE 从 5.44 掉到 1.29。
19. **$C^{L} = C^{0}/D_{\text{bulk}}$ 是近似式**（对应 $F \to 0$ 的小程度熔融）。答题时如果题目说 "as an approximation"，直接用即可。
20. **离子半径的因果方向**：$Z↑ \Rightarrow$ 质子数↑ $\Rightarrow$ 核电荷↑ $\Rightarrow$ f 电子屏蔽不完全 $\Rightarrow$ 电子被拉近 $\Rightarrow$ **半径↓** $\Rightarrow$ 在多数矿物中**更相容**。别把因果链倒过来说。
21. **矿物结构解释题的答题套路**：不要停在"化学式差不多/不一样"，必须落到**硅酸盐结构类型（孤立四面体 vs 链）→ 阳离子格位大小 → 与 REE 离子半径的匹配程度 → D 值**。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Gibbs free energy | 吉布斯自由能 | $G = H - TS$；当液体的 $G$ 低于固体时岩石开始熔融，自然界总是趋向最小化 $G$。 |
| Melting point | 熔点 | 纯物质有单一熔点（Di 为 1391 °C）；矿物混合物没有单一熔点。 |
| Partial melting | 部分熔融 | 岩石在一个温度区间内逐渐熔化，熔体与残余固体共存的状态。 |
| Solidus | 固相线 | 固相线以下体系完全为固态；在 An–Di 体系中即 1274 °C 的水平线。 |
| Liquidus | 液相线 | 液相线以上体系完全为液态；同时给出任一温度下平衡熔体的成分。 |
| Eutectic (point / temperature / composition) | 共结点 / 共结温度 / 共结成分 | 体系熔融温度的最低点；An–Di 体系为 1274 °C、An₄₂Di₅₈；任何 An–Di 混合物的第一滴熔体都在此产生。 |
| Eutectic melting | 共结熔融 | 第一滴熔体总是共结成分、与原岩矿物比例无关的熔融方式。 |
| Binary (two-component) phase diagram | 二元（双组分）相图 | 以温度为纵轴、二元成分为横轴，标出各相稳定区的图。 |
| Tie line | 连结线 | 两相区内的等温水平线，两端给出共存两相的成分。 |
| Lever rule | 杠杆规则 | $f_{\text{liquid}} = AB/AL$、$f_{\text{solid}} = BL/AL$；由质量守恒推出，用来算两相区各相的比例。 |
| Bulk composition | 体系总成分 | 整块岩石（固+液合计）的化学成分，在相图上是一条固定的垂直线。 |
| Equilibrium crystallization | 平衡结晶 | 熔融的严格逆过程：冷却时液体沿液相线移向共结点，最后在共结温度等温结晶完毕。 |
| Anorthite (An) | 钙长石 | CaAl₂Si₂O₈，斜长石的钙端元，An–Di 相图的左端元。 |
| Diopside (Di) | 透辉石 | CaMgSi₂O₆，单斜辉石端元，熔点 1391 °C，An–Di 相图的右端元。 |
| Gabbro | 辉长岩 | 由斜长石 + 辉石组成的粗粒基性侵入岩，就是 An–Di 体系的真实对应物。 |
| Granite | 花岗岩 | 由斜长石 + 碱性长石 + 石英 + 云母组成的酸性岩，多组分共结体系的例子。 |
| Peridotite | 橄榄岩 | 主要由橄榄石 + 辉石组成的超基性岩，是地幔的主要岩石类型。 |
| Basalt | 玄武岩 | 地幔橄榄岩部分熔融产生的共结熔体，是最常见的火山岩。 |
| Silicate melt | 硅酸盐熔体 | 无长程有序结构的液体，成分只受电荷平衡限制，不受矿物化学式限制。 |
| Decompression melting | 减压熔融 | 地幔物质上涌、压力下降导致的熔融，洋中脊和地幔柱的主要熔融机制。 |
| Hotspot volcanism | 热点火山作用 | 地幔柱上升产生熔体，板块移动形成火山岛链（如夏威夷）。 |
| Arc volcanism / flux melting | 岛弧火山作用 / 助熔剂熔融 | 俯冲板片释放流体降低地幔楔固相线，诱发熔融。 |
| Rare Earth Elements (REE) | 稀土元素 | 镧系元素 La (Z=57) 至 Lu (Z=71)（广义也含 Z=89–92），填充 f 轨道、化学性质高度一致的一组元素。 |
| Lanthanides | 镧系元素 | REE 的另一名称，以镧 La 为首。 |
| LREE / HREE | 轻稀土 / 重稀土 | LREE 约 La–Sm/Eu（半径大），HREE 约 Gd–Lu（半径小）。 |
| f orbitals | f 轨道 | REE 填充的轨道；f 电子**非成键**且被外层屏蔽，故 REE 化学性质彼此相似。 |
| Lanthanide contraction | 镧系收缩 | 3+ REE 的离子半径随 Z 增大而系统性减小，因为 f 电子对核电荷屏蔽不完全。 |
| Eu²⁺ | 二价铕 | Eu 的常见价态（[Xe]4f⁷ 半满特别稳定），大小电荷都像 Ca²⁺，是 Eu 异常的根源。 |
| Ce⁴⁺ | 四价铈 | Ce 的另一常见价态，是 REE 中除 Eu 外的第二个例外。 |
| Eu anomaly | 铕异常 | REE 配分曲线在 Eu 处偏离平滑趋势；斜长石中为正异常，其熔体中为负异常。 |
| Oddo–Harkins rule / odd–even effect | 奇偶效应 | 偶数 Z 的核素比相邻奇数 Z 更稳定、丰度更高，造成 REE 浓度图的锯齿形。 |
| Promethium (Pm) | 钷 | Z = 61，自然界不存在，REE 图上永远空缺。 |
| CI chondrite | CI 碳质球粒陨石 | 代表太阳系原始未分异物质的成分标准，用作归一化的分母。 |
| Normalization | 归一化 | 样品浓度除以 CI 球粒陨石浓度，消除核合成的奇偶锯齿，只保留地球化学信号。 |
| Partition coefficient (D) | 分配系数 | $D = C^{\text{mineral}}/C^{\text{melt}}$，无量纲；D 取自 "distribution"。 |
| Compatible element | 相容元素 | $D > 1$，偏好留在矿物（岩石）中，如 Ni 在橄榄石中 ($D = 10$)。 |
| Incompatible element | 不相容元素 | $D < 1$，熔体一形成就"跳"进熔体，如大多数 REE。 |
| Bulk partition coefficient | 总分配系数 | $D_{\text{bulk}} = \sum x_j D_j$，按源区各矿物的比例加权求和。 |
| Trace element | 微量元素 | 含量很低、不构成主要矿物的元素；REE 是最有用的一类微量元素示踪剂。 |
| Degree of partial melting (F) | 部分熔融程度 | 熔体占源岩的质量分数；F 越小，不相容元素在熔体中越富集。 |
| Plagioclase peridotite | 斜长石橄榄岩 | 浅部（< 1 GPa）稳定的地幔橄榄岩相，含斜长石。 |
| Spinel peridotite | 尖晶石橄榄岩 | 中等压力稳定的地幔橄榄岩相（补充知识）。 |
| Garnet peridotite | 石榴橄榄岩 | 深部（高压）稳定的地幔橄榄岩相，斜长石不稳定而由石榴子石取代。 |
| Garnet | 石榴子石 | 8 次配位小格位，强烈相容 HREE（$D_{\text{Lu}} = 11.9$），是"深部熔融"的关键指示矿物。 |
| Crustal assimilation | 地壳混染 | 岩浆上升穿过地壳时混入地壳物质，会改变其 REE 特征。 |
| Depleted upper mantle | 亏损上地幔 | 地球历史上反复熔融、把不相容元素抽走后残留的上地幔。 |
| Nesosilicate (isolated tetrahedra) | 岛状硅酸盐（孤立四面体） | 橄榄石的结构类型，SiO₄ 四面体互不相连，格位小，REE 极难进入。 |
| Inosilicate (chain silicate) | 链状硅酸盐 | 辉石的结构类型，SiO₄ 四面体连成链，格位较大，能容纳更多 REE。 |
| Batch melting | 批式熔融 | $C^L/C^0 = 1/[D + F(1-D)]$（超纲补充）；$F \to 0$ 时退化为本周用的 $1/D_{\text{bulk}}$。 |
