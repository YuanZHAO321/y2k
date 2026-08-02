# Week 3 — 地球的分层与元素分配 (Earth's Layers and Element Partitioning)

> 材料来源：
> - Lecture：`ChemEarth L3 - Earth's Layers and element partitioning.md`
> - Transcript：`EART11200 - 09-Oct-transcript.md`（2022/2026 版课堂录音转写）
> - Practical：`Practical 3 2022 - Element partitioning - feedback.md`

---

## 一、本周主题

本周讲 **地球如何分异出核 (core formation / differentiation)，以及在这个过程中各元素如何在金属熔体与硅酸盐熔体之间"选边站"**。核心工具是 **分配系数 (partition coefficient, D)**，核心分类是 **Goldschmidt 的四分类（亲铁 siderophile / 亲石 lithophile / 亲铜（亲硫）chalcophile / 亲气 atmophile）**，核心案例是 **铂族元素 (PGE) = 高度亲铁元素 (HSE)**，以及用 Ir 异常论证 K-Pg 界线陨石撞击假说。

在全课 11 周的位置：
- Week 1 讲了核合成 (nucleosynthesis) 与太阳系元素丰度（丰度随原子序数 Z 增大而下降）；
- Week 2 讲了"地球化学家的元素周期表"——电子构型 → 成键行为 → 离子电荷与地球化学行为；
- **Week 3（本周）** 把 Week 2 的"成键行为"直接应用到行星尺度：成键方式（金属键 vs 离子键）决定元素进核还是留幔，从而决定了地球每一层的化学成分。这一周引入的 **partitioning（分配）** 概念是全课的骨干概念，后面第 6 周的"熔融与稀土元素 (REE)"、水岩相互作用、同位素分馏全都建立在同一套逻辑上（老师原话：这个概念"pervades everything"，不是学完今天就丢掉的东西）。

**本讲四个明示目标 (Objectives)：**
1. 理解地球核形成的各种模型；
2. 知道为什么元素被分为 siderophile / chalcophile / lithophile / atmophile（Goldschmidt 分类）；
3. 引入元素分配 (element partitioning) 的概念；
4. 研究铂族元素 (PGEs) 如何被用来探究地质过程。

**阅读材料 (Reading)：**
- 基础（最低要求）：Grotzinger & Jordan，p. 603–604（core formation）；p. 247–249（mass extinctions）
- 推荐：Misra，Ch. 3.11（Goldschmidt 分类）、Ch. 12.2.3（core formation）
- 补充：Marshak Ch.1；Gill p.215–220（Goldschmidt、Ir、核形成）；McSween & Richardson Ch.2 p.23–24；White Ch.7.2.1（Goldschmidt）、Ch.7.2.2.7（PGEs）
- 视频：Collision that formed the Moon（月球形成撞击的模拟）https://www.youtube.com/watch?v=o2lRpiediP8 — 老师**特别推荐**，说讲得非常清楚。
- 电子书查找方式：Blackboard → EART11200 → Chemistry of the Earth → 左侧 "Reading Lists Online" → 往下滚到 Chemistry section，White / Gill / Albarède / Misra / McSween 全部有电子版。

---

## 二、核心概念

### 2.1 地球的分层结构 (Earth's layers)

从内到外：**内核 (inner core, 固态) → 外核 (outer core, 液态) → 地幔 (mantle) → 地壳 (crust)**。

本周要回答的两个问题（幻灯片原文）：
- **How and when did the core separate from the mantle?**（核何时、如何从幔中分离？）
- **What elements are concentrated in the core, and why?**（哪些元素富集在核里，为什么？）

我们能拿到的"实物样品"：
- **地幔**：地幔捕虏体 / 橄榄岩结核 (mantle nodule, peridotite)，由火山喷发带到地表；
- **核**：**铁陨石 (iron meteorite)** —— 它们来自已经发生过分异 (differentiation) 的小行星的核，是"别人家的核"的直接样品。

### 2.2 早期地球为什么这么热？(Heat sources)

要形成核，前提是至少铁能熔化。早期地球的热源有四个：
1. **吸积碰撞的动能 (energy from collisions of accretion)** —— 小石子 → 大块体不断碰撞并粘合，动能转化为热；
2. **放射性衰变 (radioactive decay)** —— 地球一形成就已经有放射性元素，衰变生热一直持续到今天；
3. **核形成本身释放的重力势能 (gravitational energy released during core formation)** —— 一个原本均匀的地球，把致密的金属搬到中心，会释放巨量重力能（这是一个**正反馈**：核形成放热 → 更热 → 更容易继续分异）；
4. **形成月球的巨大撞击 (giant moon-forming impact)** —— 发生在太阳系形成后约 **100 Myr**，能量极大。

**关键推论（转写中老师强调）**：这次巨撞击时，地球**已经有核了**；但撞击太剧烈，把地球几乎整个熔化——"几乎没有什么还是固态的，一切都是熔融的"。

**加热程度**：足以熔化金属铁，以及**部分（不一定是全部？）**硅酸盐——幻灯片原文用了 "some (not all?) silicate"，问号是刻意留的，说明这仍是开放问题。

### 2.3 不混溶液体 (Immiscible liquids)

**定义**：两种成键性质不同的液体不能混合成单一液体；两者中密度更大的会下沉。

日常类比（老师用的）：油和水、油和醋（沙拉酱）、熔岩灯 (lava lamp)。
**为什么不混溶？—— 因为成键方式不同**：
- 油：以**共价键 (covalent bonding)** 为主；
- 水：以**离子/极性键 (ionic bonding)** 为主。

对应到地球：
- **硅酸盐熔体 (silicate liquid)**：**离子键 (ionic bonding)** 为主；
- **金属铁熔体 (iron liquid)**：**金属键 (metallic bonding)**；
- 两者不混溶 → 铁熔体**密度更大** → **下沉** → 形成核。

（磁性/第三相：实际上还可能存在**第三种不混溶液体——硫化物熔体 (sulphide liquid)**。Goldschmidt 分类正是建立在"硅酸盐熔体、金属熔体、硫化物熔体三者可以共存且互不混溶"这个前提上。）

### 2.4 岩浆洋 (Magma ocean) 与核形成模型

**Magma ocean**：早期地球表层（或相当厚的一层）是熔融硅酸盐，其中悬浮着金属铁液滴。核形成模型都包含这样一个岩浆洋阶段。

幻灯片给出的两种"金属如何穿过固态下地幔到达核"的机制：
- **模型 A（岩浆洋较薄）**：金属液滴在岩浆洋中下沉 → 在岩浆洋底部**聚集成池 (pond)** → 以**diapir（底辟体、金属团块/pods）** 的形式**穿过固态地幔下沉**，加入到核。
- **模型 B（岩浆洋较厚）**：金属液滴下沉形成较厚的金属层 → 通过**渗滤 (percolation)**，沿固态地幔矿物晶粒之间的孔隙缝隙**滴渗**下去，最终到达核。

**Misra Fig. 12.11 的三个模型（幻灯片最后一页）：**

| 模型 | 英文 | 内容 | 对 HSE 问题的意义 |
|---|---|---|---|
| a | **Homogeneous accretion** 均匀吸积 | 先吸积未分异 (undifferentiated) 的物质形成整个地球，之后再整体熔融、发生核形成 | 最"标准"的模型 |
| b | **Heterogeneous accretion** 非均匀吸积 | 吸积物质的性质随时间改变；**核形成之后**才吸积上来的物质，其亲铁元素来不及进核，就留在了地幔 | 直接解释地幔 HSE 偏高 |
| c | **Magma ocean model** 岩浆洋模型 | 金属在熔融硅酸盐中分离 → 沉到岩浆洋底 → 再以 diapir 形式穿过固态地幔进入正在生长的核 | 本讲主要采用的图像 |

（转写中老师对 b 的描述略有不同：他说 heterogeneous accretion 是"先吸积金属较多的物质，随行星长大再加入越来越多的硅酸盐物质"。幻灯片强调的是"晚期吸积的物质不把亲铁元素交给核"。两种说法都是"吸积物成分随时间变化"这个大意，考试按幻灯片版本答更稳妥。）

### 2.5 核形成的时间：¹⁸²W 定年

**通过测量钨同位素 ¹⁸²W (tungsten)，可知地球核形成于太阳系形成之后约 50 Myr。**

原理背景（老师口头补充）：¹⁸²Hf → ¹⁸²W 这个同位素体系中的母体在太阳系初期**衰变得非常快**（半衰期短，约 9 Myr），因此只能记录太阳系最初几千万年内的事件——正好是核形成的时间窗口。Hf 是亲石的（留在幔），W 是亲铁的（进核），所以核幔分离会造成 Hf/W 分馏，进而在地幔中留下 ¹⁸²W 异常。

**尺度感（老师强调）**：50 Myr 对于"长成整个地球 + 加热 + 完成整个分异过程"这种**行星尺度过程**来说，其实是**相当快**的。

### 2.6 分异 (Differentiation) = 核形成

**Core formation = Differentiation**（differentiation 就是"分离/分异"的意思）。

关键：**核形成分离的不只是铁**。在金属熔体与硅酸盐熔体共存的地方，**每一个元素都要"做选择"**——进金属液还是留硅酸盐液。

甚至**铁本身也被劈成两份**：
- 在金属液中以**金属态 Fe⁰** 存在；
- 在硅酸盐液中以**离子态 Fe²⁺** 存在。

幻灯片给的两侧清单：

| | **SILICATE LIQUID（硅酸盐熔体）** | **IRON LIQUID（金属铁熔体）** |
|---|---|---|
| 主量元素 (major elements) | Si, O, Mg, Fe, Ca, Al | Fe, Ni, S, Si, O |
| 其他典型元素 | K, Rb, Cs, Ti, F, Cl, U, Th, REE 等 | Co, Ru, Pd, Ir, Pt, Au, W 等 |
| 名称 | **LITHOPHILE** (rock-seeking，亲石/嗜岩) | **SIDEROPHILE** (iron-seeking，亲铁/嗜铁) |

**注意 Fe、Si、O 三个元素在两边都出现**——老师明确点出：**不是非此即彼 (not just either-or)**，可能是 60% 进金属、40% 进硅酸盐，也可能 10:90。理解这个"程度"正是 partitioning 要量化的东西。

### 2.7 Goldschmidt 元素分类

**分类依据**：元素对**硅酸盐熔体 / 金属熔体 / 硫化物熔体**的偏好（注意——是对**液体 (liquid)** 的偏好，前提是这三种熔体可以作为不混溶液体共存）。

| 类别 | 词源 | 偏好的相 | 典型元素 |
|---|---|---|---|
| **Lithophile** 亲石 | litho = 岩石，-phile = 喜爱 | 硅酸盐熔体 | Si, O, Mg, Ca, Al, K, Rb, Cs, Ti, U, Th, REE, F, Cl |
| **Siderophile** 亲铁 | sidero = 铁 | 金属铁熔体 | Ni, Co, W, PGE (Ru, Rh, Pd, Os, Ir, Pt), Au, Re |
| **Chalcophile** 亲铜/亲硫 | chalco = 铜 | 硫化物熔体 | Cu, Pb, Zn, S 等 |
| **Atmophile** 亲气 | atmo = 大气 | 气相/大气 | 稀有气体、N 等挥发分 |

**要点：**
- 周期表上有些元素**标了两种颜色**——意思是它可以出现在两种液体中（如 Fe, Co, Ni）；
- 化学行为的根源是 **成键方式 (the way an element bonds)**：偏好**离子键** → 去硅酸盐；偏好**金属键** → 去金属铁液。
- **老师对幻灯片的公开吐槽（重要！）**："我不知道这个版本为什么把 Fe 标成 siderophile。如果周围氧很少它确实是 siderophile；但**大多数情况下 Fe 是一部分在硅酸盐里、一部分在金属里**，Co 和 Ni 也一样。我会把它们涂成**一半绿一半黄**（半亲石半亲铁）。"
- **Goldschmidt 分类不是绝对的**，它依赖于**条件**（尤其是氧含量）。

### 2.8 分配 (Partitioning) 与分配系数 D

**定义**：元素对某一相的偏好程度，称为该元素的 **partitioning behaviour（分配行为）**。

**影响 D 的条件（三个，必背）**：
1. **温度 (temperature)**
2. **压力 (pressure)**
3. **可获得的氧量 (amount of oxygen available)** —— 即氧逸度 $f_{O_2}$

**分配系数 (partition coefficient)，又名分布系数 (distribution coefficient)，符号 D，无量纲。**

写法约定（老师专门讲了记号）：符号写成 $^{X}D_{\text{met/sil}}$——
- **左上角**的元素符号 = 讨论的是哪个元素；
- **下标 met/sil** 中"**斜杠前的相放分子（上面）**，斜杠后的相放分母（下面）"。这个记号非常清晰，不要写反。

**这个概念的普适性（老师强调，不要以为学完今天就丢掉）**：
- 熔体 / 晶体：岩浆结晶时元素在晶体和熔体之间分配（→ 第 6 周 REE、部分熔融）；
- 流体 / 岩石：热液或水与岩石反应时元素在流体和岩石之间分配；
- 金属 / 硅酸盐：今天的核形成；
- 金属 / 硫化物：见 Practical A(g)。

### 2.9 亲铁 vs 亲石的判据

$$
\text{siderophile（亲铁）：} \quad D_{\text{met/sil}} > 1
$$
$$
\text{lithophile（亲石）：} \quad D_{\text{met/sil}} < 1
$$

即 $D>1$ → 元素**富集在核**；$D<1$ → 元素**富集在幔**。

**极重要的直觉（老师反复强调）**：D = 25 意味着金属中 Ni 是硅酸盐中的 25 倍，**但硅酸盐中仍然有 0.1 wt% 的 Ni**——**不是全部进了金属**。D 大只表示偏好强，永远不代表"清零"。

### 2.10 氧含量控制"能不能形成核"（本讲最深刻的一点）

老师在课上做了现场投票："**如果有非常多的氧，还能形成核吗？**"（正确答案：**不能**。）

逻辑链：
- 氧多 → 铁被氧化成 Fe²⁺ / Fe³⁺ → 铁以**离子**形式进入硅酸盐熔体 → 没有金属铁液 → **没有核**（或核很小）。
- 氧极少（还原条件）→ 铁保持金属态 Fe⁰ → 几乎所有铁都进核 → **形成巨大的核**。

**延伸到系外行星 (exoplanets)**：现在我们能测到系外行星的化学成分，发现它们成分差异极大。**一个 O/Fe 比很高的行星可能根本没有核，其行为会与地球完全不同。** 所以"氧含量"是决定一颗行星基本构造的**根本参数之一**。

（这也与 Week 2 的复习内容衔接：Fe⁰ 在铁金属中；FeS₂ 黄铁矿中 Fe 处于共价/离子/金属之间的"中间态"；FeO 方铁矿 wüstite = Fe²⁺；Fe₃O₄ 磁铁矿 = Fe²⁺ + Fe³⁺ 混合；Fe₂O₃ 赤铁矿 = Fe³⁺。**Fe:O 比越高（氧越多），Fe 的电荷越高**——FeO 是 1:1，Fe₂O₃ 是 1:1.5。）

### 2.11 微量元素 (Trace elements)

**定义**：丰度很低的元素。

**但"低"是相对的**——老师强调必须先**定义你的体系**：同一个元素可能在核里是微量元素，在幔里却是主量元素。

**为什么地球化学上有用的微量元素通常是重元素？** 回到 Week 1 的核合成：太阳系元素丰度随原子序数 Z 增大而**下降**——因为核合成先是轻元素**聚变 (fusion)** 生成中等大小的核，之后必须靠**逐次中子俘获 (neutron addition)** 才能把原子序数一步步堆上去，效率低，所以重元素本来就稀少。

另一个 Week 1 的规律在本周复现：**奇偶效应 (Oddo–Harkins rule)** —— 老师指着 Ru (Z=44, 1.3 ppm) → **Rh (Z=45, 0.24 ppm)** → Pd (Z=46, 1.0 ppm) 说："**原子序数为奇数的那个，丰度更低。**"

### 2.12 铂族元素 (PGE) = 高度亲铁元素 (HSE)

**PGE 名单（幻灯片）**：Ru (ruthenium 钌)、Rh (rhodium 铑)、Pd (palladium 钯)、Os (osmium 锇)、Ir (iridium 铱)、Pt (platinum 铂)、Au (gold 金)。也叫 **noble metals（贵金属）**。
- 第 5 周期：Ru, Rh, Pd
- 第 6 周期：Os, Ir, Pt, Au
- （Re 铼严格说不属于 PGE，但它也是 HSE，行为完全一致；Practical feedback 中把 Re 也列进 PGE 名单了。）

**别名：Highly Siderophile Elements (HSEs)** —— 对金属的亲和力**极强**。

**为什么？** 课堂上老师又做了一次投票："这些元素**哪种轨道**在参与化学反应？s/p/d/f？"答案是 **d 轨道**。
- 周期表最左边填 s 轨道，最右边填 p 轨道，**中间过渡金属区填 d 轨道**，底部两行（镧系锕系）填 f 轨道。
- **d 轨道未填满 → 倾向参与金属键 (metallic bonding) → 必然强烈偏好金属铁液 → 高度亲铁。**

**地球整体丰度（Abundance in the Earth, ppm）**：

| 元素 | Ru | Rh | Pd | Os | Ir | Pt | Au |
|---|---|---|---|---|---|---|---|
| ppm | 1.3 | 0.24 | 1.0 | 0.9 | 0.9 | 1.9 | 0.16 |

全都在 ~1 ppm 量级——**它们在整个地球尺度上就是微量元素**。

**金 (Au) 的分配实例**：
- $^{Au}D_{\text{met/sil}} \approx 2000$
- 全地球 (bulk Earth) 含 Au 约 **160 ppb**
- 结果：**核 ~500 ppb，幔 ~0.25 ppb**
- **结论：地球上绝大部分黄金在核里。所有 PGE 都是如此。** 这就是为什么金在地表如此稀有、如此"贵"。

### 2.13 HSE 悖论：地幔中的 HSE 比预期高

**观察到的现象（Cottrell 2004 图）：**

图的读法：
- **x 轴**：元素按**亲铁性递增**排列（越往右越偏好金属）；
- **y 轴**：**地幔丰度 / 全地球 (bulk Earth) 丰度**（归一化比值）；
- **实心点**：实际测得的地幔丰度比；
- **叉号 (crosses)**：由实验测得的分配系数**计算出的预期**地幔丰度比。

图上从左到右的分区：
1. Mn, Cr, V —— 亲石，**富集在地幔**（比值 ≥ 1）；
2. Fe, Co, Ni —— **中度亲铁**，地幔中被"抽走了一部分"，比值 <1 但不算极低；
3. HSE / PGE —— 比值很低（强烈进核），**但仍显著高于叉号所在的位置**。

**两个"怪事" (two puzzling things)：**
1. **所有 HSE 在地幔中的丰度彼此相近**（不符合预期——它们的 D 值差别很大，本应"散落"在不同高度）；
2. **所有 HSE 在地幔中的丰度都比预期高**（比按 D 值算出来的高得多）。

**四种解释假说（Walker 2009, Chemie der Erde）：**
1. **核分离不完全 (incomplete core separation)**：一部分金属没能滴下去，被**困在地幔里**，把 HSE 也留下了；
2. **晚期吸积 (late accretion / late veneer)**：核形成完成**之后**，又有一批球粒陨石质 (chondritic) 物质加到地球上；此时已无岩浆洋，无法再进行金属-硅酸盐分离，因此这批 HSE **只能留在地幔**。→ 这也漂亮地解释了"为什么所有 HSE 丰度彼此相近"——因为它们保持了**球粒陨石的原始相对比例**！
3. **实验条件不对**：许多 D 值是在 **1 bar（1 个大气压）** 下测的，不适用于深部地幔的**高温高压**条件（近年已有改进，但那张图作图时确实如此）；
4. **以上多种过程叠加**（并且我们对 bulk Earth 成分的估计本身也可能不准）。

老师原话：这一段"如果跟不上就不用太担心"，但它**是地质学界至今仍在激辩的问题**——是很好的"开放性问题"素材。

---

## 三、公式与图表

### 3.1 分配系数的定义式

$$
D \;=\; \frac{\text{Abundance in liquid 1}}{\text{Abundance in liquid 2}}
$$

- **Abundance（丰度）**可用 wt%（weight percent，百分之几）、ppm（parts per million，百万分之一）、ppb（parts per billion，十亿分之一）表示；
- **分子分母必须用同一种单位** → 所以 **D 无量纲 (no units)**。

**单位换算**：
$$
1\ \text{wt\%} = 10^4\ \text{ppm} = 10^7\ \text{ppb}, \qquad 1\ \text{ppm} = 1000\ \text{ppb}
$$

**具体到金属/硅酸盐体系：**

$$
^{Ni}D_{\text{met/sil}} \;=\; \frac{\text{wt\% Ni in metal}}{\text{wt\% Ni in silicate}}
$$

符号说明：
- 左上标 $Ni$：所讨论的元素；
- 下标 $\text{met/sil}$：**met（金属）在分子，sil（硅酸盐）在分母**；
- 若写成 $^{Cr}D_{\text{sulphide/silicate}}$，则硫化物在分子、硅酸盐在分母。

### 3.2 判据式

$$
\boxed{D_{\text{met/sil}} > 1 \;\Rightarrow\; \textbf{siderophile}\ (\text{富集于核})}
$$
$$
\boxed{D_{\text{met/sil}} < 1 \;\Rightarrow\; \textbf{lithophile}\ (\text{富集于幔})}
$$

### 3.3 由 D 反推核的成分（本周最常考的计算套路）

已知地幔丰度 $C_{\text{mantle}}$ 与 $D_{\text{met/sil}}$，则：

$$
D_{\text{met/sil}} = \frac{C_{\text{core}}}{C_{\text{mantle}}} \;\Longrightarrow\; C_{\text{core}} = D_{\text{met/sil}} \times C_{\text{mantle}}
$$

**实验测 D 的做法（课堂补充）**：在 Williamson Building 地下室的 **experimental petrology lab（实验岩石学实验室）**，用 **multi-anvil press（多压砧压机）**——一台巨大的液压机，把只有**几毫米**大的样品管挤压到极高压力，并加热到高温，让金属熔体与硅酸盐熔体共存并达到平衡；淬火后在显微镜/电子探针下分别测两相中该元素的含量（幻灯片上的实验产物照片比例尺是 **200 μm**，即 5 个才 1 mm）。

### 3.4 完整例题 1：Ni 的分配系数与核中 Ni 含量

**(a) 求 D。** 实验测得金属中 Ni = 2.5 wt%，硅酸盐中 Ni = 0.1 wt%：

$$
^{Ni}D_{\text{met/sil}} = \frac{2.5}{0.1} = 25
$$

**含义**：金属中的 Ni 是硅酸盐中的 **25 倍**（25:1）。$D>1$ → Ni 是 **siderophile**。

**(b) 估算核中 Ni 含量。** 地幔 Ni = 0.20 wt%（来自 Practical 1 的表）：

$$
C_{\text{core}}^{Ni} = 0.20 \times 25 = 5\ \text{wt\%}
$$

**验证**：Practical 1 表中给的核实测（估计）值是 **5.2 wt%** —— 非常接近，说明这套方法是可靠的。

**方法论意义（老师强调）**：**我们没法钻到核里去取样**，所以核的成分**全部是这样估算出来的**——测地幔（可以拿到橄榄岩 peridotite 样品）+ 实验测 D → 推核。

### 3.5 完整例题 2：Mn（亲石元素）

已知 $^{Mn}D_{\text{met/sil}} = 0.3$，地幔中 Mn = 1045 ppm，求核中 Mn。

$$
\frac{\text{Amount of Mn in core}}{\text{Amount of Mn in mantle}} = 0.3
$$
$$
\text{Mn in core} = 0.3 \times 1045 = 313.5 \approx \mathbf{313\ ppm}
$$

$D<1$ → Mn 是 **lithophile**，核中 Mn 比幔中少。

### 3.6 完整例题 3：小行星 Eros 上有多少黄金？

已知：
- Eros 质量 $m = 7\times10^{15}$ kg，直径约 17 km；
- Eros 的物质类似**普通球粒陨石 (ordinary chondrite)**；
- 普通球粒陨石中 Au 丰度 ≈ **200 ppb**（对比：全地球 160 ppb）。

$$
m_{Au} = 7\times10^{15}\ \text{kg} \times 200\times10^{-9} = 7\times10^{15}\times2\times10^{-7} = 1.4\times10^{9}\ \text{kg}
$$

**答案：Eros 上有超过 10 亿公斤 (1 billion kg) 的黄金**——而且**每一种其他 PGE 也都在数十亿公斤量级**。

**背景（老师补充，Marshak 书上的表）**：按当时已知矿床储量，**全世界金资源只够约 30 年，美国约 20 年**。这就是"小行星采矿 (asteroid mining)"被认真讨论的原因。**但老师明确评价：目前经济上完全不可行，很多人认为这仍是"荒唐的科幻概念"。**

### 3.7 关键图表判读

**(1) 太阳系元素丰度图 (Composition of the Solar System)**（Lecture 1 复习）
- x 轴 = 原子序数 Z；y 轴 = 丰度（对数）。
- **要点**：丰度随 Z 增大而总体**下降**（"Decrease with increasing Z"）。
- **原因**：核合成先靠聚变造中等核，再靠中子俘获逐步加重，越重越难造。
- **叠加锯齿**：偶 Z 元素丰度高于相邻奇 Z 元素（Oddo–Harkins）。

**(2) 地球化学家的元素周期表 (Geochemist's Periodic Table)**（贯穿全课）
横向分区读法：
- 最左：**1+ ions**（碱金属）；次左：**2+ ions**（碱土）；
- 中间：**first series transition metals**（第一系列过渡金属，变价）；
- 右侧：**3+ ions**、**complex ions**（碳酸根、硝酸根、硅酸根、磷酸根等，兼有共价+离子键）、**2− ions**（O, S）、**1− ions**（卤素）、**noble gases**；
- 底部：**Rare Earth Elements (REE): 3+ ions**（稀土，第 6 周主题）；
- 标出的两个重要微量元素群：**High field-strength elements (HFSE，高场强元素)** 与 **Platinum group elements (PGE) / noble metals**。
- Week 2 已用到：Nb、Ta 是 **5+** 离子（因为它们左邻那列是 4+，往右一列变 5+）。

**(3) HSE 地幔亏损图 (Cottrell 2004)** —— 见 §2.13，判读方法已在上面写全。核心口诀：**"HSE 在地幔中既太平（都差不多高）又太高（高于预期）"**。

**(4) Practical 的 Mantle/Earth vs Atomic number 图** —— 见 §5.2。

**(5) Practical 的 Ir 剖面图** —— 见 §5.3。

---

## 四、课堂补充

以下内容 **transcript 有、slides 没有或没讲透**：

1. **Blackboard 与阅读材料的用法**：每周讲完课后立即开放当周 topic，同时开放下周的。老师用了一个比喻：**"你已经砌好了砖墙，但还没抹上灰浆 (you've got a brick wall, but you haven't quite put in the mortar)"**——做阅读就是在补那层灰浆，把知识黏合起来。他明显对"只有几个人在做阅读"感到不满。

2. **Week 2 的收尾问题（Mn 为什么有多种价态）在本周开头被回答了**：老师用 Fe 举例（Fe 和 Mn 都是过渡金属，道理一样）——
   - **iron metal（铁金属）** → Fe⁰，**金属键**，不是离子键也不是共价键；
   - **pyrite 黄铁矿 FeS₂** → 结构在电子行为上比较复杂，Fe 的成键**兼有共价、离子、金属性质**，是"中间状态"；
   - **wüstite FeO** → Fe²⁺；**magnetite Fe₃O₄** → Fe²⁺ 与 Fe³⁺ 混合；**hematite Fe₂O₃** → Fe³⁺。
   - **核心记忆法**："**氧越多，铁的电荷越高**"。看 Fe:O 比 —— FeO 是 1:1，Fe₂O₃ 是 1:1.5。
   - 氧化态 (oxidation states) 会在**后面的氧化还原那一讲**详细展开。

3. **"我们不知道答案"这句话反复出现**：核形成模型是**基于现有证据（很多是化学证据）建立的 model / picture**，不是确凿事实。这是本课的科学方法论基调。

4. **月球形成撞击的时间与顺序**：撞击发生在太阳系形成后约 **100 Myr**，而核形成在 **50 Myr** —— 所以**地球在巨撞击之前就已经有核了**，撞击只是把它重新熔化。这个先后关系幻灯片没有明说，容易搞混。

5. **"半亲铁半亲石"的修正**：老师亲口修正了幻灯片对 Fe/Co/Ni 的着色（见 §2.7）。

6. **氧含量与系外行星的联系**（见 §2.10）——这是本讲的"升华段"，也是课堂投票题，很可能出现在考试的概念题里。

7. **d 轨道 → 金属键 → 亲铁**这条推理链是老师用投票的方式带着全班推出来的，属于**必须会自己复述**的因果链。

8. **奇偶效应在 PGE 上的体现**：Ru(1.3) > **Rh(0.24)** < Pd(1.0)，Rh 是 Z=45 奇数所以最低。

9. **多压砧压机 (multi-anvil press)** 就在 Williamson Building 地下室——D 值是"我们系自己在做"的实验，不是抽象的书本数字。样品仅几毫米大。

10. **"partitioning 概念不止今天用"** —— 老师专门停下来强调它在晶体/熔体、流体/岩石体系中同样适用。这是提示：本周概念会在后续周次反复出现。

11. **"D 大 ≠ 全部进核"**：老师特意回到 Ni 的例子说"硅酸盐里还是有 0.1% 的 Ni，**这才是重点**"。

12. **关于 HSE 悖论的态度**："如果这一段跟不上，别太担心" —— 说明它在考核中权重较低，但作为"科研前沿"值得知道。

---

## 五、Practical 要点

**Practical 3: Core formation and Element Partitioning**

**三个目标：**
1. 理解 partition coefficient 的概念并练习计算；
2. 研究哪些元素被分配进地球核、为什么；
3. 用高度亲铁元素 (HSEs) 的信息，检验"K/Pg 界线发生大陨石撞击"的假说。

---

### 5.1 A 部分：分配系数计算（完整解题过程）

**(a) 求 Ni 的分配系数。** 金属中 Ni = 1 wt%，硅酸盐中 Ni = 0.04 wt%。

$$
^{Ni}D_{\text{met/sil}} = \frac{1}{0.04} = \mathbf{25}
$$

**(b) 由地幔 Ni = 0.20 wt% 求核中 Ni。**

$$
25 = \frac{X_{\text{core}}}{0.20} \;\Longrightarrow\; X_{\text{core}} = 25 \times 0.20 = \mathbf{5\ wt\%}
$$

**(c) 求 Mn 的分配系数。** 金属中 Mn = 100 ppm，硅酸盐中 Mn = 333 ppm。

$$
^{Mn}D_{\text{met/sil}} = \frac{100}{333} = \mathbf{0.30}
$$

→ $D<1$，Mn 是 lithophile。

**(d) Re（铼）：$^{Re}D_{\text{met/sil}} = 1.2\times10^4$，地幔 Re = 0.3 ppb，求核中 Re（用 ppm 表示）。**

$$
1.2\times10^4 = \frac{X_{\text{core}}}{0.3}
$$
$$
X_{\text{core}} = 1.2\times10^4 \times 0.3 = 3600\ \text{ppb} = \mathbf{3.6\ ppm}
$$

（单位换算：1 ppm = 1000 ppb，所以 3600 ÷ 1000 = 3.6 ppm。）

**(e) 用 (d) 的结果 + 质量比 68% 幔 / 32% 核，求全地球 (bulk Earth) 的 Re 丰度（ppm）。**

这是**质量平衡 (mass balance)** 计算：

$$
C_{\text{bulk}} = f_{\text{mantle}} \cdot C_{\text{mantle}} + f_{\text{core}} \cdot C_{\text{core}}
$$
$$
= (0.68 \times 0.3) + (0.32 \times 3600)
$$
$$
= 0.204 + 1152 = 1152.2 \approx 1152\ \text{ppb} = \mathbf{1.15\ ppm}
$$

**解题思路要点**：注意地幔那一项 (0.204 ppb) 相对于核那一项 (1152 ppb) **完全可以忽略**——因为 Re 极度亲铁，全地球的 Re 几乎全在核里。这个数量级感觉本身就是答案的一部分。

**(f) 地球核中到底有没有 Si？**
地幔含 Si ≈ 21 wt%；核中 Si 含量有 6 wt% 和 8 wt% 两种说法，求两种模型下的 $^{Si}D_{\text{met/sil}}$：

$$
\text{模型 1：}\ ^{Si}D_{\text{met/sil}} = \frac{6}{21} = \mathbf{0.286}
$$
$$
\text{模型 2：}\ ^{Si}D_{\text{met/sil}} = \frac{8}{21} = \mathbf{0.381}
$$

**如何检验"核里有 Si"这个假说？（论述题答案要点）**
- 可以在**高压实验**中测 $^{Si}D_{\text{met/sil}}$，看是否落在上述值附近；
- **但**：实验精度必须非常高，因为 **D 的微小差异会导致核中 Si 含量的巨大差异**（0.286 vs 0.381，D 只差 33%，但对应 6 → 8 wt%）；
- 其他途径：通过核的**物理性质**入手——**密度 (density)**、**地震波性质 (properties of seismic waves)** 等；
- **概念要点（重要）**：虽然我们通常把 Si 当作亲石元素，但在**还原条件 (reducing conditions，氧含量低)** 下 **Si 会变得亲铁**。事实上**某些陨石中的金属相就含 Si**，所以"核中有 Si"在化学上是可行的。（← 这直接呼应了 §2.10「氧含量控制一切」）

**(g) 三相分配（metal / sulphide / silicate）。**
已知 $^{Cr}D_{\text{metal/silicate}} = 3.4$，$^{Cr}D_{\text{sulphide/silicate}} = 0.5$，核（金属）中 Cr = 9000 ppm。求地幔中 Cr 与共存硫化物熔体中 Cr。

第一步，用 metal/silicate：
$$
3.4 = \frac{9000}{X_{\text{mantle}}} \;\Longrightarrow\; X_{\text{mantle}} = \frac{9000}{3.4} = \mathbf{2647\ ppm}
$$

第二步，用 sulphide/silicate（**注意：硅酸盐（地幔）是"桥梁相"**）：
$$
0.5 = \frac{X_{\text{sulphide}}}{X_{\text{silicate}}} \;\Longrightarrow\; X_{\text{sulphide}} = 0.5 \times 2647 = \mathbf{1323\ ppm}
$$

**解题思路（关键技巧）**：当题目给的两个 D 值**分母相同**（都是 silicate）时，先解出那个公共相的浓度，再往外推第三个相。若两个 D 的分母不同，则需要用 $D_{A/C} = D_{A/B}\times D_{B/C}$ 这类链式关系换算。

---

### 5.2 B 部分：哪些元素富集在核里？

**Table 1（完整，含补全的 Mantle/Earth 比值）**：

| 原子序数 Z | 元素 | 地幔丰度 (ppm) | 全地球丰度 (ppm) | Mantle / Earth |
|---|---|---|---|---|
| 15 | P | 90 | 715 | 0.13 |
| 23 | V | 82 | 105 | 0.78 |
| 24 | Cr | 2625 | 4700 | 0.56 |
| 25 | Mn | 1045 | 800 | 1.31 |
| 27 | Co | 105 | 800 | 0.12 |
| 28 | Ni | 1960 | 18200 | 0.11 |
| 29 | Cu | 30 | 60 | 0.50 |
| 30 | Zn | 55 | 40 | 1.38 |
| 44 | Ru | 0.005 | 1.3 | 0.004 |
| 45 | Rh | 0.001 | 0.24 | 0.004 |
| 46 | Pd | 0.004 | 1 | 0.004 |
| 56 | Ba | 6.6 | 4.5 | 1.47 |
| 57 | La | 0.65 | 0.44 | 1.48 |
| 75 | Re | 0.0003 | 0.075 | 0.004 |
| 76 | Os | 0.003 | 0.9 | 0.003 |
| 77 | Ir | 0.003 | 0.9 | 0.003 |
| 78 | Pt | 0.007 | 1.9 | 0.004 |
| 79 | Au | 0.001 | 0.16 | 0.006 |
| 82 | Pb | 0.15 | 0.23 | 0.65 |
| 92 | U | 0.02 | 0.015 | 1.33 |

**比值的物理含义（判读方法）：**
- **Mantle/Earth > 1** → 该元素在地幔中比全地球平均**更富集** → **亲石 (lithophile)**（如 Mn 1.31, Zn 1.38, Ba 1.47, La 1.48, U 1.33）；
- **Mantle/Earth ≈ 1** → 基本不分异；
- **Mantle/Earth << 1** → 强烈**亏损**于地幔 → 已进核 → **亲铁 (siderophile)**（PGE 全在 0.003–0.006）；
- 中间地带（0.1–0.8）→ **中度亲铁**（Co 0.12, Ni 0.11, P 0.13, Cu 0.50, Cr 0.56, Pb 0.65, V 0.78）。

**作图**：横轴 = 原子序数 Z，纵轴 = Mantle/Earth（建议**对数纵轴**，因为跨了三个数量级）。图形特征：曲线**不是**随 Z 单调下降；在 Z = 44–46 和 75–79 处有**两个深深的"低谷"**（正好是第 5、第 6 周期的 PGE），而 Ba/La（56/57）和 U（92）反而是**高峰**。

**四个"是不是真的？"论述题（这是 Practical 的精华，答案思路必须掌握）：**

**(a) "所有金属元素都强烈富集在地球核中" —— 对吗？**
> **不对。** 有些金属确实强烈富集在核中，如 **Pt 和 Au**。但 **Cu (0.50) 和 Pb (0.65) 只是轻微富集在核中，在地幔中丰度仍然很高**。**Co (0.12) 和 Ni (0.11) 虽然被分配进核，但并不十分强烈。**
>
> *答题技巧：题目明确要求"不要只答 yes/no，要举具体元素例子支持你的论证"。*

**(b) "所有重元素（高原子序数）都富集在地球核中" —— 对吗？**
> **不对。** **地幔丰度并没有随原子序数增大而单调下降的趋势。** 虽然 Os–Au（Z = 76–79）这些高 Z 的 PGE 确实富集在核中，但**最重的两个元素之一——Pb (Z=82) 和 U (Z=92)——却富集在地幔中**（U 的 Mantle/Earth = 1.33）。

**(c) "所有 d 轨道未填满的元素都富集在地球核中" —— 对吗？**
> **不对。** d 轨道未填满的元素位于周期表**中间的过渡金属区块**，所有 PGE 都在这里，它们的 d 轨道确实未填满。**但是第 4 周期的过渡元素 V、Cr、Mn、Cu、Zn 同样 d 轨道未填满，它们却主要是亲石元素，富集在地幔中。**
>
> *这是本 practical 最"反直觉"的一题：d 轨道未填满是 PGE 亲铁的**必要背景**，但**不是充分条件**。*

**(d) "所有铂族元素都富集在地球核中" —— 对吗？**
> **对。** PGE 包括 Ru, Rh, Pd, Os, Re, Ir, Pt, Au（feedback 原文把 Re 也算进来了）。**它们全部在地幔中极度亏损**（Mantle/Earth ≈ 0.003–0.006），因为都被分配进了核。PGE 是**高度亲铁元素 (HSEs)**。

**(e) 总结：什么性质导致元素富集在地球核中？**
> **最主要的性质是它必须具有 siderophile（亲铁）化学行为**——即在硅酸盐熔体与铁金属熔体共存的体系中，它强烈偏好金属熔体。PGE 就同时具备**高原子序数**与 **d 轨道未填满**这两个特征，因而表现出这种行为。

**(f) 为什么知道核中有多少 U 很重要？**
> **U 是天然放射性元素，放射性衰变会产热。** 如果核中有 U，它就会**贡献核的热量产出 (heat production)**。**理解地球的热收支 (Earth's heat budget) 是地球科学的一个根本目标**（它驱动地磁发电机、地幔对流、板块运动）。
>
> 但从图上可以看到，**U 实际上富集在地幔中——它是亲石元素**，这与它属于**锕系 (Actinide)** 相符（可与镧系/REE 的 La 作对比：La 的 Mantle/Earth = 1.48，U 是 1.33，行为一致）。
>
> 参考文献：Faure P. et al. (2020) "Uranium and thorium partitioning in the bulk silicate Earth and the oxygen content of Earth's core." *Geochimica et Cosmochimica Acta* **275**, 83–98.

---

### 5.3 C 部分：用 HSE 检验 K-Pg 撞击假说

**假说**：白垩纪末（约 **65 Ma**）包括恐龙在内的大规模物种灭绝，可归因于一次**大型陨石撞击**。

**地质证据 1：丹麦 Stevns Klint 的 K-Pg 界线**
- 剖面组成：上部为**苔藓虫灰岩 (bryozoan limestone)**，下部为**白垩 (chalk)**，两者都是石灰岩；
- 中间夹着一层**很薄的黏土层 (clayish material)**，形成于 65 Ma；
- **这层黏土 Ir（铱）含量极高**——Ir 在铁陨石中丰富，但在地球（地表）极其稀少；
- 深灰色斑点是**燧石结核 (chert nodules)**；
- 这一事件标志**中生代 (Mesozoic Era) 的结束**。

**地质证据 2：墨西哥 Chicxulub 撞击构造**
- 位于**尤卡坦半岛 (Yucatán Peninsula)**；
- 通过**重力异常图 (gravity anomaly map)** 识别出**一系列同心环状构造**；
- 图上白点是充水的**灰岩溶蚀塌陷天坑 (sinkholes)**，玛雅语称 **cenote**（复数 cenotes，源自玛雅词 *dzonot*）；**天坑环**与最大的外围重力梯度特征相关联，其成因尚不确定，但与地下埋藏的陨石坑的联系是清楚的；
- **撞击坑直径约 180 km；撞击体直径约 10–15 km。**

**Table 2：Stevns Klint K-Pg 界线沉积物的 Ir 含量（Alvarez et al. 1980）**

| 相对界线层的高度 (m) | Ir 丰度 (ppb) |
|---|---|
| +2.7 | <0.3 |
| +1.2 | <0.3 |
| +0.7 | 0.36 |
| **0**（界线层） | **28.6** |
| −0.5 | 0.73 |
| −2.2 | 0.25 |
| −5.4 | 0.3 |

**(a) 作图要求**：把数据画在图上（通常 y 轴 = 相对高度，x 轴 = Ir 含量），**点与点之间连线**以显示剖面形态。

**图形特征（判读）**：背景值稳定在 **0.25–0.36 ppb** 左右，在**恰好 0 m 处出现一个极窄、极高的尖峰 (sharp spike) 28.6 ppb**——约为背景值的 **~100 倍**；峰的上下都迅速回落（+0.7 m 处已回到 0.36，−0.5 m 处 0.73）。**"尖锐 (sharp)" 这个形态特征本身就是关键证据。**

**(b) 为什么大多数沉积物（代表地壳）中 Ir 丰度很低？**
> **两个原因叠加：**
> 1. **Ir 是微量元素**，在**全地球 (Bulk Earth)** 中的丰度本身就极低（0.9 ppm）；
> 2. **Ir 是高度亲铁元素 (HSE)**，因此在核形成时**被浓集到了地球核中**。
>
> 这两个因素结合，导致**地壳的 Ir 含量极低**。

**(c) 为什么 Ir 是支持撞击假说的好元素？**
> 1. **因为地壳中 Ir 的背景值很低，所以哪怕 Ir 只增加一点点，也非常容易被识别出来**（信噪比高）；
> 2. **因为 Ir 是亲铁元素，很难用其他地球过程来解释它的富集**——地球表面没有什么正常过程能把 Ir 浓集起来。

**(d) 撞击体可能是什么类型的陨石？球粒陨石？铁陨石？**
> **两者都有可能。**
> - **铁陨石 (iron meteorites)** 来自**已分异的小行星 (differentiated asteroids)**，它们本身就代表"核形成"的产物，因此含有**相对高的 PGE / HSE**。典型 Ir 丰度 **~1–10 ppm**。
> - **球粒陨石 (chondrite meteorites) 没有经历过核形成**，因此保留了**完整的太阳系元素丰度**，包括 PGE。典型 Ir 丰度 **~500 ppb**。
> - 这两类的 Ir 浓度**都远高于地球表面**（虽然对陨石自身而言 Ir 仍是微量元素），**足以在沉积记录中留下撞击的印记**。
> - **Chicxulub 的撞击体很可能是一颗彗星 (comet)，由球粒陨石质 (chondritic) 物质组成。**

**(e) 替代假说：印度德干暗色岩 (Deccan Traps) 的大规模玄武岩喷发（时间相近）。高 Ir 可能来自火山作用吗？**
> **很难。两条反驳：**
> 1. **成分论证**：玄武岩来自**地幔**，而**地幔的 PGE 含量很低**（正因为 PGE 都进核了），所以玄武岩不会有高 PGE 含量；
> 2. **形态论证**：火山假说描述的是**一段延续很长的喷发期**，这与在 K-Pg 界线观察到的 **Ir 的尖锐尖峰 (sharp spike)** 不符——延续性喷发应产生宽缓的、跨越多米地层的富集，而不是一层薄黏土里的骤升骤降。

**(f) 高 Ir 是否*证明*了大灭绝由撞击造成？若要深入研究，你会调查什么？**
> **不能证明。** 高 Ir 只**证明发生了一次撞击**，并**不能证明撞击与大灭绝之间存在因果关系**——**撞击有可能只是巧合 (coincidental)**。
> 要论证"撞击导致了大灭绝"，必须依靠**其他方向的研究**，例如：
> - 撞击造成的**气候变化模型 (models of the climate change effects)**；
> - 这种气候变化**对生物的影响 (the effect of such change on organisms)**。
>
> *这是典型的"相关 ≠ 因果"科学方法论考点。*

**参考文献：**
- Alvarez L. W., Alvarez A., Asaro F. and Michel H. (1980) *Extraterrestrial cause for the Cretaceous–Tertiary extinction.* **Science 208**, 1095–1108.
- Schulte P. and 40 co-authors (2010) *The Chicxulub asteroid impact and mass extinction at the Cretaceous–Paleogene boundary.* **Science 327**, 1214–1218.

---

## 六、易错点 / 重点难点

1. **D 的分子分母搞反。** 记号 $^{X}D_{\text{A/B}}$ 中，**斜杠前的 A 放分子，斜杠后的 B 放分母**。写 $^{Ni}D_{\text{met/sil}}$ 就必须是 (金属中 Ni)/(硅酸盐中 Ni)。反过来算出 0.04 而不是 25，整题就废了。

2. **"D 很大 = 全部进核"是错的。** D = 25 时硅酸盐里仍有 0.1 wt% Ni；D = 2000 时地幔里仍有 0.25 ppb Au。**分配永远是"程度问题"，不是"有/无"问题。**

3. **单位换算翻车。** 1 wt% = 10⁴ ppm = 10⁷ ppb；1 ppm = 1000 ppb。题目常常给 ppb 却要求答 ppm（如 A(d)：3600 ppb = 3.6 ppm）。**做完一定检查单位。**

4. **质量平衡题忘了乘质量分数。** Bulk Earth = 0.68×(幔) + 0.32×(核)，**不是**简单取平均，也**不是**幔+核直接相加。

5. **"重元素都进核"是典型错误结论。** U (Z=92) 和 Pb (Z=82) 都富集在**地幔**。原子序数与亲铁性**没有**单调关系。

6. **"d 轨道未填满 → 亲铁"不是充分条件。** 第 4 周期过渡金属 V, Cr, Mn, Cu, Zn 的 d 轨道也未填满，却主要是亲石的。

7. **"金属元素都进核"也是错的。** Cu、Pb 只是轻度进核，Co、Ni 进核但不强烈。

8. **Fe / Co / Ni 是"半亲铁半亲石"。** 老师亲自纠正了幻灯片把 Fe 单纯标为 siderophile 的做法。答题时务必写"Fe 部分进核（Fe⁰）、部分留幔（Fe²⁺）"。

9. **Goldschmidt 分类依赖条件，不是元素的固有属性。** 最典型的例子：**Si 通常亲石，但在还原（低氧）条件下会变亲铁**——这就是"核中可能有 6–8 wt% Si"的化学基础。

10. **氧含量决定"有没有核"。** 氧多 → Fe 被氧化成离子进硅酸盐 → 无核/小核；氧极少 → Fe 全部保持金属态 → 巨大的核。这是概念题高频考点，并连接到系外行星。

11. **时间顺序：核形成 (~50 Myr) 早于 月球形成巨撞击 (~100 Myr)。** 别写成"巨撞击导致了核形成"。

12. **¹⁸²W 是定核形成年龄的工具**，不要与后面第 10 周的 U-Pb 等长半衰期体系混淆——短半衰期的灭绝核素才能分辨太阳系最初几千万年。

13. **HSE 悖论的两个"怪"要分开说**：① 彼此丰度相近（不该相近）；② 都比预期高。只答一个会丢分。

14. **Ir 异常只证明"有撞击"，不证明"撞击导致灭绝"。** 相关不等于因果。

15. **反驳德干火山假说要给两条理由**：地幔源玄武岩 PGE 本来就低（成分）+ 长期喷发无法产生尖锐尖峰（形态）。只答一条不完整。

16. **不要把 Re 当成严格意义上的 PGE**（但它是 HSE，行为一致）；Practical feedback 把 Re 列进 PGE 名单，考试时按讲义答即可，但要知道其中的细微差别。

17. **"微量元素"是相对概念**，答题时应说明"相对于什么体系"——同一元素可以在核中是微量、在幔中是主量。

18. **immiscible 的根本原因是成键方式不同**，不是"密度不同"。密度不同只解释了**哪一个下沉**，不解释**为什么不混合**。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Core formation | 核形成 | 金属铁熔体从硅酸盐熔体中分离并下沉到地心的过程，与 differentiation 同义 |
| Differentiation | 分异（分化） | 行星内部按化学/密度分成不同层圈的过程；core formation 是其最主要的一次 |
| Accretion | 吸积 | 尘埃、小石块通过碰撞粘合逐渐长大成行星的过程；其碰撞动能是早期地球的重要热源 |
| Homogeneous accretion | 均匀吸积 | 先吸积成分不变的未分异物质形成整个地球，之后再整体熔融、发生核形成 |
| Heterogeneous accretion | 非均匀吸积 | 吸积物质成分随时间变化；核形成后才加入的物质不再把亲铁元素交给核 |
| Magma ocean | 岩浆洋 | 早期地球大规模熔融硅酸盐层，其中悬浮着金属铁液滴，是核形成的舞台 |
| Immiscible liquids | 不混溶液体 | 因成键性质不同而不能混成单一液体的两种液体（如油/水、金属铁熔体/硅酸盐熔体） |
| Silicate liquid | 硅酸盐熔体 | 以离子键为主的"岩石熔体"，即熔融的地幔/熔岩物质 |
| Iron (metal) liquid | 金属铁熔体 | 以金属键为主、密度更大的熔体，下沉形成地核 |
| Sulphide liquid | 硫化物熔体 | 岩浆洋中可能存在的第三种不混溶液体，是 chalcophile 元素的归宿 |
| Diapir | 底辟体（金属团块/pod） | 在岩浆洋底聚集的金属，以团块形式穿过固态地幔下沉进入核 |
| Percolation | 渗滤 | 液态金属沿固态地幔矿物晶粒间的孔隙下渗到核的机制 |
| Mantle nodule / peridotite | 地幔捕虏体 / 橄榄岩 | 火山带上来的地幔碎块，是我们能直接测量地幔成分的样品 |
| Iron meteorite | 铁陨石 | 来自已分异小行星的核，是"核物质"的直接样品，PGE 含量高（Ir ~1–10 ppm） |
| Chondrite | 球粒陨石 | 未经历核形成的原始陨石，保留完整太阳系元素丰度（Ir ~500 ppb） |
| Ordinary chondrite | 普通球粒陨石 | 最常见的球粒陨石类型；小行星 Eros 即由类似物质组成，Au ≈ 200 ppb |
| Goldschmidt's classification | 戈尔德施密特分类 | 按元素对硅酸盐/金属/硫化物/气相的偏好，把元素分为亲石、亲铁、亲铜、亲气四类 |
| Lithophile | 亲石（嗜岩）元素 | 偏好硅酸盐熔体、偏好离子键的元素；$D_{met/sil}<1$，富集于地幔 |
| Siderophile | 亲铁（嗜铁）元素 | 偏好金属铁熔体、偏好金属键的元素；$D_{met/sil}>1$，富集于地核 |
| Chalcophile | 亲铜（亲硫）元素 | 偏好硫化物熔体的元素，如 Cu、Pb、Zn |
| Atmophile | 亲气元素 | 偏好气相/大气的元素，如稀有气体、N |
| Highly siderophile element (HSE) | 高度亲铁元素 | 对金属亲和力极强、$D_{met/sil}$ 可达 10³–10⁴ 的元素，基本等同于 PGE + Re |
| Platinum group elements (PGE) | 铂族元素 | Ru, Rh, Pd, Os, Ir, Pt, Au（贵金属 noble metals），d 轨道未填满 → 强烈亲铁 |
| Noble metals | 贵金属 | PGE 的别称，化学性质稳定、地表稀有 |
| Element partitioning | 元素分配 | 元素在共存两相之间按各自偏好进行分布的行为，是全课的核心概念 |
| Partition coefficient (D) | 分配系数 | 元素在两相中丰度之比，无量纲；又名 distribution coefficient |
| Distribution coefficient | 分布系数 | partition coefficient 的旧称，符号 D 即由此而来 |
| Trace element | 微量元素 | 在所讨论体系中丰度很低的元素；"低"是相对概念，须先定义体系 |
| Major element | 主量元素 | 在所讨论体系中丰度高的元素（如地幔中的 O, Mg, Si, Fe, Ca, Al） |
| wt% / ppm / ppb | 重量百分比 / 百万分之一 / 十亿分之一 | 丰度单位；1 wt% = 10⁴ ppm = 10⁷ ppb，1 ppm = 1000 ppb |
| Bulk Earth | 全地球（整体地球） | 地幔+地核（+地壳）按质量加权的平均成分，常用 68% 幔 / 32% 核 |
| Mass balance | 质量平衡 | $C_{bulk}=f_{mantle}C_{mantle}+f_{core}C_{core}$，由各层成分反推整体成分 |
| Oxidation state | 氧化态（价态） | 元素在化合物中的形式电荷（Fe⁰ / Fe²⁺ / Fe³⁺），受可获得氧量控制 |
| Reducing conditions | 还原条件 | 氧含量低的条件；此时 Si 等通常亲石的元素也可能变得亲铁 |
| Multi-anvil press | 多压砧压机 | 实验岩石学装置，把毫米级样品加压加温以模拟深部条件、实测 D 值 |
| Experimental petrology | 实验岩石学 | 通过高温高压实验重现地球内部过程的学科分支 |
| ¹⁸²W (tungsten) | 钨-182 | 短寿命 ¹⁸²Hf–¹⁸²W 体系的子体，用来定出核形成发生在太阳系形成后约 50 Myr |
| Late accretion / late veneer | 晚期吸积 / 晚期薄层 | 核形成之后加入地球的球粒陨石质物质，用以解释地幔 HSE 偏高且比例相近 |
| K-Pg boundary | 白垩纪–古近纪界线 | 约 65 Ma 的地层界线（旧称 K-T boundary），伴随大灭绝与全球 Ir 异常 |
| Iridium anomaly | 铱异常 | K-Pg 界线黏土层中 Ir 含量骤增（Stevns Klint 达 28.6 ppb，约背景 100 倍） |
| Stevns Klint | 斯泰温斯崖（丹麦） | 世界著名 K-Pg 界线剖面，苔藓虫灰岩/白垩之间夹富 Ir 黏土层 |
| Chicxulub | 希克苏鲁伯（撞击构造） | 墨西哥尤卡坦半岛下的撞击坑，直径约 180 km，撞击体约 10–15 km |
| Cenote | 天坑（溶蚀塌陷坑） | 尤卡坦石灰岩中充水的塌陷坑，其环状排列勾勒出埋藏的撞击坑边缘 |
| Gravity anomaly map | 重力异常图 | 通过重力场差异识别地下密度结构的方法，用于揭示 Chicxulub 的同心环 |
| Deccan Traps | 德干暗色岩 | 印度的大规模玄武岩溢流省，是 K-Pg 大灭绝的替代（火山）假说 |
| Mass extinction | 大灭绝 | 短时间内大量物种消失的事件；K-Pg 事件终结了中生代与恐龙时代 |
| Exoplanet | 系外行星 | 环绕其他恒星的行星；其 O/Fe 比差异意味着有些行星可能根本没有核 |
| Nucleosynthesis | 核合成 | 恒星中生成元素的过程；解释了丰度随原子序数增大而下降的总体规律 |
| Oddo–Harkins rule | 奥多–哈金斯规则 | 偶原子序数元素丰度高于相邻奇数元素（如 Ru > Rh < Pd） |
| High field-strength elements (HFSE) | 高场强元素 | 电荷高、离子半径小的一组微量元素（如 Nb⁵⁺、Ta⁵⁺），周期表上单列标出 |
| Rare Earth Elements (REE) | 稀土元素 | 主要以 3+ 离子存在的镧系元素，亲石，将在第 6 周详细展开 |
