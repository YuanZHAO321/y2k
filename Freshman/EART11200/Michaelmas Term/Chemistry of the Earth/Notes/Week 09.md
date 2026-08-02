# Week 9 — 水：全球大气降水同位素与水化学 (Water: Global Meteoric Water & Water Chemistry)

> 材料来源：
> - Lecture: `ChemEarth L9 - Water.pdf`（含 Practical 9 的引言部分）
> - Transcript: `EART11200 - 27-Nov-transcript`（录音在结尾处被截断，最后一句停在 "In case you missed…"）
> - Practical: `ChemEarth Practical 9 - Water - Feedback.pdf`
>
> 推荐阅读（老师在 slides 上逐页标注了对应节，绿色标记）：
> - **水与气候**：Gurney/Grotzinger & Jordan Ch. 12, p. 350–354；Misra Ch. 11.4；Gill Ch. 4, p. 60–69；White Ch. 9.6；McSween Ch. 13, p. 271–273
> - **水化学**：Grotzinger & Jordan Ch. 16, p. 454–461；Misra Ch. 7（限定小节：7.1, 7.3, 7.4, 7.5, 7.6, 7.9, p. 53–54, p. 140–141）；Gill Ch. 10, p. 197–200；White Ch. 6；McSween Ch. 4, Ch. 7

---

## 一、本周主题

本周主题是 **水 (water)**，分成截然不同但内在相连的两大块：

1. **Part 1 — 全球大气降水 (global meteoric water)**：把 Week 8 学的稳定同位素 (stable isotopes) 工具**应用**到水循环上。海水蒸发 → 云中凝结 → 降雨，每一步都发生同位素分馏 (isotopic fractionation)，结果是全球降水的 $\delta^{18}\mathrm{O}$、$\delta\mathrm{D}$ 呈现出可预测的空间规律（**全球大气降水线 GMWL**），进而成为**古气候学 (palaeoclimatology)** 的核心代用指标——深海沉积岩芯、冰芯、米兰科维奇旋回 (Milankovitch cycles)。
2. **Part 2 — 水化学 (chemistry of water)**：从水分子的**极性 (polarity)** 出发，建立"盐/酸/碱—pH—平衡常数—溶解度积"这一整套水溶液化学语言，为 Practical 9 的**化学风化 (chemical weathering)** 反应打基础。

**在 11 周主线中的位置**：

| 周次 | 主题 | 与本周的关系 |
|---|---|---|
| W1–2 | 地球化学视角的元素周期表、离子与成键 | 本周讲水分子成键（O 的 2 个共价键）直接调用 |
| W3 | 地球分层与元素分配 | — |
| W4 | 碳循环与有机化学 | 本周的碳酸/碳酸盐体系是碳循环的**水相环节** |
| W5 | 化学反应式与氧化态 (redox) | 本周所有风化反应都要**配平**；氧化风化产物（赤铁矿等）属 redox |
| W6–7 | 化学平衡与热力学；熔融与稀土 | 本周的 $K$、$K_{sp}$ 就是**平衡常数**在水溶液中的具体化；开/闭系统概念直接沿用 |
| W8 | 稳定同位素 | **本周 Part 1 = W8 的旗舰应用**（$\delta$、$\alpha$、分馏、SMOW 全部复用） |
| **W9（本周）** | **水** | 承上（同位素 + 平衡）启下（水—岩相互作用） |
| W10 | 放射性同位素与地质年代学 | 与本周的稳定同位素形成对照 |
| W11 | 总复习 | — |

老师在开场明确说：本周是 **"把上周的稳定同位素术语用起来"** 的一周——"你很快就会发现稳定同位素被用来解决地球与环境科学中各种各样的问题"。

---

## 二、核心概念

# ══════ Part 1：全球大气降水 (Global Meteoric Water) ══════

### 2.1 "Meteoric" 的含义（老师专门澄清的易混词）

**Meteoric water（大气降水 / 天水）**：*relating to or denoting water derived from the atmosphere by precipitation or condensation* —— 指**由大气通过降水或凝结而来的水**（雨、雪、雹、霜、露）。

老师特别强调（transcript）：

> "people get confused about the word meteoric because it sounds like meteorites… but we don't mean anything to do with meteors or meteorites."

**Meteoric 与 meteorite（陨石）无关**！两者只是共享同一个希腊词根（"天上的东西"），meteorology（气象学）也是同根。**不要**把 meteoric water 理解成"陨石带来的水"。

### 2.2 水的同位素与同位素体 (isotopologues)

水 = H$_2$O。其组成元素的稳定同位素：

- 氢：$^1$H（轻氢 protium）、$^2$H（重氢 deuterium，写作 **D**）
- 氧：$^{16}$O、$^{17}$O、$^{18}$O

**同位素体 (isotopologue)**：同一种分子，但其中一个或多个原子被不同的同位素取代所形成的不同版本。

水的同位素体数目计算：
- 氢的位置组合：H–H、H–D、D–D → **3 种**
- 氧：$^{16}$O、$^{17}$O、$^{18}$O → **3 种**
- 总共 $3 \times 3 = \mathbf{9}$ 种同位素体

这 9 种分子的**地球化学行为略有差异**（质量不同 → 键能、扩散速度、蒸气压不同），正是同位素分馏的物理基础。

**为什么 H、O 的同位素效应特别显著？**（老师复述 W8 要点）
因为它们是**轻元素 (light elements)**，同位素之间的**质量差相对于总质量的比例很大**：
- 氢：D 的质量是 $^1$H 的**两倍**（2 vs 1）→ 质量差 100%！
- 氧：$^{18}$O vs $^{16}$O 差 2/16 = 12.5%，虽不如氢夸张，但仍然可观。

→ 结果：H 和 O 的同位素是**极其灵敏的温度与环境条件示踪剂 (sensitive tracers of temperature and other conditions)**。

### 2.3 海水：标准与开放系统

**海水的两个关键性质：**

1. **海洋混合良好 (well mixed)，同位素组成全球均一**。其平均值非常接近 **SMOW (Standard Mean Ocean Water)**，即按定义：
   $$\delta\mathrm{D}_{ow} = 0\ ‰ \qquad \delta^{18}\mathrm{O}_{ow} = 0\ ‰$$
   老师提醒：这个 0 是**定义出来的**——因为我们就是拿海水当参考标准。

2. **海洋对水蒸气而言是一个开放系统 (open system)**。

   > 回顾 W6 热力学：
   > - **闭系统 (closed system)**：可与外界交换**能量**，但**不交换物质 (mass)**。
   > - **开系统 (open system)**："盖子掀开了"，**物质和能量都可交换**。
   >
   > 老师的形象解释：水从海面蒸发后，**不会**在海面上薄薄一层里待着，而是上升进入大气并迅速扩散消失。所以海—气边界处刚形成的水汽**持续被移走**，这就是"开放"的含义。

   **这一点极其重要**：因为水汽一形成就被移走，蒸发过程无法达到真正的双向平衡，**动力学同位素效应 (kinetic isotope effect)** 得以发挥并被"放大"。

### 2.4 海水蒸发：平衡分馏

25 °C (298.15 K) 时的**平衡同位素分馏系数 (equilibrium isotopic fractionation factor)**：

$$\alpha_{ow\text{-}wv}^{\mathrm{O}} = \frac{(^{18}\mathrm{O}/^{16}\mathrm{O})_{ow}}{(^{18}\mathrm{O}/^{16}\mathrm{O})_{wv}} = 1.0092$$

$$\alpha_{ow\text{-}wv}^{\mathrm{H}} = \frac{(\mathrm{D/H})_{ow}}{(\mathrm{D/H})_{wv}} = 1.074$$

符号说明：
- $ow$ = ocean water（海水，液相）
- $wv$ = water vapour（水蒸气，气相）
- $\alpha > 1$ ⟹ **分子（液相）富集重同位素**

**推导出的水汽 $\delta$ 值：**
$$\delta^{18}\mathrm{O}_{wv} = -9.12\ ‰ \qquad \delta\mathrm{D}_{wv} = -68.90\ ‰$$

（完整推导见【三、公式与图表】3.1）

**核心结论（slide 加粗）：**
> **Ocean water is enriched in heavy isotopes relative to water vapour.**
> 海水相对于水蒸气富集重同位素（$^{18}$O、D 留在液相；$^{16}$O、$^1$H 进入气相）。

**再加上动力学效应：**
> "In addition, kinetic isotope effects contribute to making the water vapour even lighter."

老师解释：含 $^{16}$O 的水分子不仅在平衡态下更倾向进入气相，而且**运动更快、蒸发更快 (moves faster)**；因为系统是开放的（跑掉的水汽不再回来交换），这个速度差就**放大了同位素分馏**。

**数值对比（老师明确给出）：**

| 情形 | 初始水汽 $\delta^{18}$O |
|---|---|
| 仅平衡分馏 (equilibrium only) | $-9\ ‰$ |
| 平衡 + 动力学分馏（实际） | $-13\ ‰$ |

### 2.5 水汽凝结：瑞利式的逐步"变轻"

**凝结是平衡过程**，且是蒸发的逆过程（同一个 $\alpha$，方向相反）。

关键区别：
> "Water vapour in the atmosphere is **not a huge reservoir like the ocean**, so its isotopic composition **changes as water condenses**."

海洋是无限大的储库（取走一点点水汽不改变其组成）；而**云中的水汽是有限的小储库**，一旦下了雨，剩余水汽的组成就变了。

**逐步过程（这是本节的核心逻辑链）：**

1. 第一批雨滴的 $\delta^{18}$O **高于**（重于）水汽——因为液相富集重同位素。
2. 雨把重同位素"带走了" ⟹ **剩余水汽变轻**（$\delta$ 更负，即富集 $^{16}$O 和 $^1$H）。
3. 云继续内移，遇到下一座山，再下雨：这批雨仍比**当时的**水汽重 ~9‰，但因为水汽已经变轻了，**这批雨也比第一批雨轻**。
4. 如此循环 ⟹ **水汽和雨水都随内陆距离增加而单调变轻**。

老师的记忆口诀（transcript 原话）：

> "It's hard to get your brain around that sometimes, don't worry about it, the best thing to do is to just **look at the values** and see what the values are doing… **think of these negative values as very light and the water as being heavy**. 重的在水里，轻的在汽里 (heavy in the water, light in the vapour)。"

> ⚠️ 老师在讲台上一度说错又自己纠正："…the rain also gets lighter and lighter as it moves inland. **Sorry, no it doesn't. Yes, that's right, yes, I've got that the right way round.**" —— **正确答案是：雨和水汽都越往内陆越轻**，因为汽—液之间始终保持恒定的分馏差，而作为"母体"的水汽在不断变轻。

### 2.6 影响降水同位素组成的三大效应

除了**距海距离 (distance from the ocean)** 这个"瑞利蒸馏"效应之外：

**核心物理原理（slide 加粗）：**
> **Isotopic fractionation gets larger with decreasing temperature.**
> 温度越低，同位素分馏越大（$\alpha$ 偏离 1 越远）。老师补充：**对氢尤其显著 (particularly for hydrogen)**。

由此产生两大地理效应：

| 效应 | 机制 | 结果 |
|---|---|---|
| **纬度效应 (latitude effect)** | 赤道热、两极冷 | 高纬降水更贫 $^{18}$O 和 D |
| **高程效应 (elevation / altitude effect)** | 海平面暖、山顶冷 | 高海拔降水更贫 $^{18}$O 和 D |

**极端实测值（南极）：**
$$\delta^{18}\mathrm{O} = -50\ ‰ \qquad \delta\mathrm{D} = -450\ ‰$$

老师评价："those are really really extreme differences."

### 2.7 全球大气降水线 GMWL (Global Meteoric Water Line)

$$\boxed{\ \delta\mathrm{D} = 8\,\delta^{18}\mathrm{O} + 10\ }$$

**全球各地的大气降水，其同位素组成都落在这条线上或非常接近它。**

判读要点：
- 海水位于 **原点 (0, 0)**（按定义）。
- **赤道附近**：分馏小 → 数据点靠近原点。
- **极地**：分馏大 → 数据点沿线延伸到左下角（$\delta^{18}$O 到 $-50$，$\delta$D 到 $-450$）。

> ⚠️ **课本勘误（slide 明确标注）**：**McSween 书 p. 272 上的 Meteoric Water Line 方程是错的 (incorrect)**。以本讲义的 $\delta\mathrm{D} = 8\delta^{18}\mathrm{O} + 10$ 为准。

**美国降水等值线图（McSween Fig. 3-6）判读**（老师说"数字太小看不清，我只要你看图案 pattern"）：
- 等值线**由南向北越来越负** → **纬度效应**
- 等值线在**落基山脉 (Rocky Mountains)** 区域**深深下凹**（更负），在**阿palachian 山脉 (Appalachians)** 也有较弱的下凹 → **高程效应**

### 2.8 古气候学应用：冰期—间冰期的海洋同位素信号

**核心机制：**

> During a glacial period, ice sheets **lock up a disproportionate amount of $^{16}$O**, leaving the oceans relatively enriched in $\delta^{18}$O.

逐步理解：

| 阶段 | 极地 | 海洋 |
|---|---|---|
| **间冰期 (interglacial，如今天)** | 冰盖小，降水最终大多回流海洋 | $\delta^{18}$O ≈ 0（正常） |
| **冰期 (glacial)** | 极地降雪（**极负 $\delta$ 值，富 $^{16}$O**）不断堆积、**不回流海洋** | 大量 $^{16}$O 被锁住 → 海水**相对富集 $^{18}$O** → $\delta^{18}$O 上升（示意图中升至 **+1.5‰**） |

老师的口诀：
> "think of it as the $^{18}$O is preferentially in the water, so we have lots of $^{18}$O, the heavier isotopes, stuck in the water; and then the $^{16}$O is precipitating at the poles with very negative delta values, so we get lots of $^{16}$O building up at the poles."

**图示背景**：末次冰盛期（**18,000 年前**）主要冰川的分布范围（White Fig. 9.22）。

### 2.9 米兰科维奇旋回 (Milankovitch Cycles)

> 老师课上问："Have you come across that in your other lectures?" —— "A lot of blank faces." 所以他**从头讲了一遍**（这部分 slides 上很简略，transcript 才有完整解释）。

**成因**：地球绕日轨道**不是固定的**，它会"摆动 (wobble)"。这些轨道参数的周期性变化改变了地球接收的**太阳辐射通量 (solar energy flux / insolation)**，从而驱动气候旋回。所有这些参数都源于**地日（及其他天体）之间的引力相互作用**，因而具有**非常明确的周期 (very well defined periodicities)**。

| 轨道参数 | 英文 | 含义 | 周期 |
|---|---|---|---|
| 偏心率 | **Eccentricity** | 椭圆轨道的"扁平程度"，即日地距离的变化幅度 | **123,000 yr**<br>**85,000 yr**<br>**58,000 yr** |
| 倾角（黄赤交角） | **Tilt / Obliquity** | 自转轴相对轨道面的倾斜角度振荡 | **41,000 yr** |
| 岁差 | **Precession** | 自转轴指向的进动 | **23,000 yr**<br>**18,000 yr** |

（共 **3 个偏心率周期 + 1 个倾角周期 + 2 个岁差周期**——老师明确点出这个"3+1+2"计数。）

**深海沉积岩芯记录（White Fig.）判读：**
- 图上有 **5 条独立岩芯曲线 + 1 条平滑后的平均曲线**。
- 纵轴 = $\delta^{18}$O，横轴 = 时间；**冰期在左，间冰期在右**（按老师描述的坐标方向）。
- 平均曲线中 $\delta^{18}$O 从**间冰期的 $-2.2‰$** 摆动到**冰期的约 $+2‰$**。
- 曲线**看似随机 (looks like a bit of a random pattern)**，但实际上是上述所有周期**叠加 (stacked on top of one another)** 的结果，可以通过**反卷积 (deconvolve)**（频谱分析）把这些规则周期分离出来。

### 2.10 冰芯记录 (Ice cores)

格陵兰和南极的冰芯保存了**极重要的气候变化记录**。

- **最长连续冰芯**：格陵兰 **123,000 年**；南极 **800,000 年**（老师："we can see back almost a million years and it's incredible"）。
- **冰芯图（NASA Earth Observatory）判读**：
  - 横轴 = **距今年数 (age, years before present)**，**今天在右侧**，向左回溯。
  - 曲线一 = **CO$_2$ 丰度 (ppm)**
  - 曲线二 = **$\delta$D (‰)**，被用作**温度代用指标 (temperature proxy)**
  - 关键观察：**温度曲线与 CO$_2$ 曲线形状高度吻合**；其锯齿形态由**米兰科维奇旋回**驱动；图右端是我们当前这个相对温暖的时期。

**科学传播意义**（老师专门强调）：
> "if somebody is a climate skeptic and says 'oh well it's been this warm in the past', how do we address that question? Then we look at this kind of record of ice cores — and what we're looking at is **the isotope composition of the hydrogen or oxygen**."

> 老师总括：稳定同位素"极其强大"，从**矿床形成温度**（W8 practical）一直到**古气候记录**，无所不在。

---

# ══════ Part 2：水化学 (Chemistry of Water) ══════

### 2.11 液态水为什么这么重要：极性溶剂 (polar solvent)

液态水是几乎所有地球化学系统的关键组分：
**大气 (atmosphere)、水圈 (hydrosphere)、生物圈 (biosphere)、风化 (weathering)、沉积岩/火成岩/变质岩的形成与蚀变**。

老师定义"水圈"：*everything where there is liquid water present — lakes, rivers, oceans*。

**根本原因只有一个：液态水是极性溶剂 (POLAR solvent)。**

> **极性 (polar) 的定义**：**电荷在分子上的分布不均匀 (the charge is not distributed evenly over the molecule)**。

**为什么水分子是极性的？**（老师从 W1 的电子构型讲起）

1. 氧原子：第一壳层 2 个电子，第二壳层 **6 个**电子 → 还需要 **2 个**才能达到惰性气体构型 (noble gas configuration) → **参与 2 个共价键 (covalent bonds)**。
2. 氢原子：只有 **1 个**电子（第一壳层）→ 成 1 个共价键后有 2 个电子，对前两号元素而言就是稳定构型。
3. 结果：H–O–H，且**两个 H 都靠在氧的同一侧、彼此靠得较近（弯曲形 bent）**。

**关键对比（老师明确点出）**：
> 回想 CH$_4$：碳的 **sp$^3$ 杂化 (sp$^3$ hybridization)** 使 4 个 H 彼此**完全等角**分布（正四面体）。
> 但 **氧不一样**——两个 H 倾向于**挤在一侧**，所以水分子**从来不画成 H–O–H 直线形**。

4. 因此：分子一端**电子多 → 高负电荷 (higher −ve charge)**（氧那端），另一端**质子多 → 高正电荷 (higher +ve charge)**（两个 H 那端）。**这就是偶极。**

老师的感慨：
> "that fundamental thing about a water molecule controls a lot of geochemical processes and it's just so basic that everybody, I think it's easy to overlook it, but it's **very, very important**."

### 2.12 盐的溶解与水合 (solvation)

**例：石盐 halite**
$$\ce{NaCl_{(s)} = Na^+_{(aq)} + Cl^-_{(aq)}}$$

**记号约定：**
- **(s)** = solid，固体
- **(l)** = liquid，液体
- **(g)** = gas，气体
- **(aq)** = aqueous，**离子处于溶液中**

**微观图像**（老师逐一描述）：
- 固态 NaCl 是**离子化合物**，晶格中 Cl$^-$ 与 Na$^+$ **交替排列**（W1–2 已学结构）。
- 溶解后，水分子**包围每一个离子**，并**按电性取向 (orientate themselves with the opposite charge)**：
  - 包围 **Cl$^-$（负）** 的水分子，把 **H 端（正）** 朝向氯离子；
  - 包围 **Na$^+$（正）** 的水分子，把 **O 端（负）** 朝向钠离子。
- 这层定向排列的水**把溶解的离子彼此隔开 (keeps the dissolved ions apart)**，阻止它们重新结合成晶体。

**三个必须记牢的术语：**

| 术语 | 英文 | 本例中 |
|---|---|---|
| 溶剂 | **SOLVENT** | 水 H$_2$O |
| 溶质 | **SOLUTE** | NaCl |
| 溶液 | **SOLUTION** | 溶剂 + 溶质的组合 |

### 2.13 电解质溶液 (electrolyte solutions)

因为溶解的离子是**带电粒子 (charged particles)**，水就能**导电 (conduct an electric current)**。因此含离子的水溶液统称 **ELECTROLYTE solutions（电解质溶液）**。

> 老师的生活化例子："I hope you all know that you shouldn't be using a **toaster in the bath** — because you don't want electricity going through the water. And that's **why**: because there are ions in water."（纯水其实导电性很差，是溶解的离子让它导电。）

### 2.14 盐、酸、碱的定义

**盐 (SALT)** 的定义（讲义给了两个互补版本）：
1. **一种溶于水的离子化合物 (an ionic compound that dissolves in water)**；
2. 更严格：**含有 H$^+$ 以外的阳离子、且含有 OH$^-$ 或 O$^{2-}$ 以外的阴离子的离子化合物**；
3. 第三个角度：**酸碱中和反应的离子产物**。

**三条例外（为什么要排除）：**

| 例外 | 例子 | 归类为 |
|---|---|---|
| 阳离子是 **H$^+$** | HCl | **酸 ACID** |
| 阴离子是 **OH$^-$** | NaOH | **碱 BASE / 碱液 ALKALI** |
| 阴离子是 **O$^{2-}$** | Na$_2$O | **碱 BASE** |

> ⚠️ slide 上写的是 "the cation is H$^+$… or OH$^-$… or O$^{2-}$"，老师在课上**口头更正**：后两个应该说 **anion（阴离子）**，不是 cation。

**酸 (ACID)**：溶于水时**产生氢离子 H$^+$** 的物质。

**碱 (BASE) vs 碱液 (ALKALI)** —— 这是本周一个明确的辨析点：

- **BASE（碱）**：能与酸反应并中和酸的物质。通常是**金属氧化物、金属氢氧化物、金属碳酸盐、金属碳酸氢盐**。**很多碱不溶于水 (insoluble)**。
- **ALKALI（碱液/可溶碱）**：**溶于水的那一部分碱**。溶于水时产生氢氧根离子 OH$^-$。

$$\ce{NaOH_{(aq)} -> Na^+_{(aq)} + OH^-_{(aq)}}$$

> 老师总结："we tend to refer to **acids and alkalis**, because alkalis are the bases that dissolve in water."（讨论水溶液时用"酸/碱液"这对词更贴切。）

### 2.15 中和反应 (neutralisation)

**离子净反应：**
$$\ce{H^+_{(aq)} + OH^-_{(aq)} -> H2O_{(l)}}$$

**完整例子（HCl + NaOH）：**
$$\ce{HCl_{(aq)} + NaOH_{(aq)} -> H^+_{(aq)} + Cl^-_{(aq)} + Na^+_{(aq)} + OH^-_{(aq)} -> NaCl + H2O}$$

即：H$^+$ 与 OH$^-$ 结合成水，剩下的 Na$^+$ 和 Cl$^-$ 组成盐 NaCl。

**三条 GCSE 级"万能公式"（老师说"useful little summaries"，值得背下来）：**

$$\text{酸 Acid} + \text{碱液 Alkali} \;=\; \text{盐 Salt} + \text{水 Water}$$
$$\text{酸 Acid} + \text{碳酸盐 Carbonate} \;=\; \text{盐 Salt} + \text{水 Water} + \text{二氧化碳 CO}_2$$
$$\text{酸 Acid} + \text{金属 Metal} \;=\; \text{盐 Salt} + \text{氢气 Hydrogen}$$

> 第二条在 Practical 9 的**碳酸盐溶解风化**中直接用到。

### 2.16 pH 标度

**酸度 (acidity)** 是溶液中 **H$^+$ 离子（质子）浓度**的量度。**pH 意为 "potential Hydrogen"（潜在氢）。**

$$\boxed{\ \mathrm{pH} = -\log_{10}[\mathrm{H}^+] = \log_{10}\!\left(\frac{1}{[\mathrm{H}^+]}\right)\ }$$

符号说明：
- **方括号 $[\ \cdot\ ]$ = "……的浓度"**。老师专门警告：这**不是**乘法括号，只是一个记号；在实际计算中，$[\mathrm{H}^+]$ 就是代数方程里的一个**变量**，可以照常移项、开方。
- 单位：**mol kg$^{-1}$**（= mol L$^{-1}$，对稀水溶液两者数值相同）。

**标度**：

| pH | 性质 |
|---|---|
| **0** | 强酸性 strongly acidic |
| **7** | 中性 neutral（25 °C 纯水） |
| **14** | 强碱性 strongly alkaline |

pH **越低越酸**，**越高越碱**。

**测量方法**（老师课堂互动）：
- **石蕊试纸 (litmus paper)** —— 只能粗判酸/碱；
- **通用指示剂 (universal indicator)** —— 液体，给出 0–14 的**更细分的标度 (more divided scale)**，通过颜色读数；
- **pH 计 (pH meter)** —— 学生们在 **Mam Tor 野外实习**中测水体 pH 用的就是"放进去直接吐出数字"的电子仪器。
- 家里也能做：醋 (vinegar) 是酸性的。

**例题（slide 上的算例）**：某溶液含 $5\times10^{-6}$ mol kg$^{-1}$ 的氢离子，求 pH。

$$\mathrm{pH} = \log_{10}\!\left(\frac{1}{5\times10^{-6}}\right) = -\log_{10}(5\times10^{-6})$$
$$= -(\log_{10} 5 + \log_{10} 10^{-6}) = -(0.699 - 6) = 5.301$$
$$\Rightarrow \mathrm{pH} = \mathbf{5.30}\quad\text{（弱酸性 mildly acidic）}$$

**补充事实**：H$^+$ 在水中**并不以孤立离子存在**，它会与水分子结合形成**水合氢离子 (hydronium ion) H$_3$O$^+_{(aq)}$**。（老师："Don't worry about that too much." —— 知道即可，计算仍写 H$^+$。）

### 2.17 平衡常数 (equilibrium constant) 与水的自解离

**通用写法（本周最重要的"语法规则"）：**

> $K$ = **右边 (RHS) 各物种浓度的乘积** ÷ **左边 (LHS) 各物种浓度的乘积**
> （Product of species on RHS, divided by product of species on LHS）

**水的解离反应 (dissociation reaction for water)：**
$$\ce{H2O = H^+ + OH^-}$$

$$K_w = \frac{[\mathrm{H}^+][\mathrm{OH}^-]}{[\mathrm{H_2O}]}$$

**在 1 bar、25 °C (298.15 K) 下，$K_w = 10^{-14}$。**

**关键简化**：在纯水（或很稀的溶液）中，水就是介质本身，取 $[\mathrm{H_2O}] = 1$。于是：

$$K_w = [\mathrm{H}^+][\mathrm{OH}^-] = 10^{-14}$$

在纯水中，H$^+$ 与 OH$^-$ 由同一个反应等量产生，故 $[\mathrm{H}^+] = [\mathrm{OH}^-]$：

$$[\mathrm{H}^+]^2 = 10^{-14} \;\Rightarrow\; [\mathrm{H}^+] = [\mathrm{OH}^-] = 10^{-7}$$
$$\Rightarrow \mathrm{pH} = -\log_{10}(10^{-7}) = \mathbf{7}\quad\text{（中性）}$$

> **这就回答了老师抛出的问题："whoever thought of a scale that went from 0 to 14?"**
> pH 标度的 0–14 范围和"7 = 中性"**不是人为规定的**，而是**由 $K_w = 10^{-14}$ 这个物理常数决定的**。这是本周一个漂亮的"为什么"。

### 2.18 酸度 / 碱度；强酸弱酸、强碱弱碱

- **酸度 (Acidity)**：溶液**给出质子 (donate protons)** 的能力。
- **碱度 (Alkalinity)**：溶液**接受质子 (accept protons)** 的能力。
- 在酸碱反应中：**酸 = 质子给体 (proton donor)，碱 = 质子受体 (proton acceptor)**（Brønsted–Lowry 定义）。

| 类别 | 定义 | 例子 |
|---|---|---|
| **强酸 strong acid** | 溶于水时**几乎完全解离 (dissociated almost completely)** | 盐酸 HCl、硝酸 HNO$_3$、硫酸 H$_2$SO$_4$ |
| **弱酸 weak acid** | 只有**小部分**解离，仅少量 H$^+$ 释放到溶液中 | 乙酸 CH$_3$COOH、**碳酸 H$_2$CO$_3$**、磷酸 H$_3$PO$_4$、**硅酸 H$_4$SiO$_4$** |
| **强碱 strong base** | 碱金属、碱土金属的氢氧化物 | 苛性钠 NaOH、熟石灰 Ca(OH)$_2$ |
| **弱碱 weak base** | — | NH$_4$OH（NH$_4^+$ = 铵离子）、Mg(OH)$_2$、Fe(OH)$_3$ |

> 老师的直觉解释：**你可以往水里加很多碳酸，但溶液中 H$^+$ 的浓度仍然不高**——因为它是弱酸，绝大部分以未解离的 H$_2$CO$_3$ 分子形式存在。这**直接预示了 Practical 中"大气平衡雨水 pH 只有 5.66 而不是 1 或 2"的结果**。
> 关于苛性钠：老师提醒 NaOH "really dangerous to your skin because it's very, very reactive"——大量 OH$^-$ 把 pH 推向 14。

### 2.19 解离常数 (dissociation constants)

对酸碱解离反应各自定义一个**解离常数**：

**(Reaction a)** $\ce{HCl = H^+ + Cl^-}$
$$K_a = \frac{[\mathrm{H}^+][\mathrm{Cl}^-]}{[\mathrm{HCl}]}$$

**(Reaction b)** $\ce{NaOH = Na^+ + OH^-}$
$$K_b = \frac{[\mathrm{Na}^+][\mathrm{OH}^-]}{[\mathrm{NaOH}]}$$

> **$K$ 值越大 ⟹ 酸或碱的解离程度越高 ⟹ 酸/碱越强。**

**广义形式（当酸/碱中阴阳离子比例不是 1:1 时）：**

$$\ce{H_{\mathit{m}}A_{\mathit{n}} = \mathit{m}H^+ + \mathit{n}A^-} \qquad \text{(Reaction a)}$$
$$\ce{B_{\mathit{p}}OH_{\mathit{q}} = \mathit{p}B^+ + \mathit{q}OH^-} \qquad \text{(Reaction b)}$$

$$K_a = \frac{[\mathrm{H}^+]^m\,[\mathrm{A}^-]^n}{[\mathrm{H}_m\mathrm{A}_n]} \qquad\qquad K_b = \frac{[\mathrm{B}^+]^p\,[\mathrm{OH}^-]^q}{[\mathrm{B}_p\mathrm{OH}_q]}$$

**核心规则**：**每个物种的浓度要取它在配平反应式中的化学计量系数为指数**（老师："we need to raise that to the power of the coefficient… where M is the subscript in the formula of that acid"）。

**具体例子：**
$$\ce{Mg(OH)2 = Mg^{2+} + 2OH^-} \qquad\Rightarrow\qquad K_b = \frac{[\mathrm{Mg}^{2+}][\mathrm{OH}^-]^2}{[\mathrm{Mg(OH)_2}]}$$

注意 $[\mathrm{OH}^-]$ 要**平方**，因为系数是 2。

### 2.20 溶解度 (solubility) 与溶解度积 (solubility product)

**溶解度 (SOLUBILITY) 的严格定义：**
> 某物质在水中的溶解度，是指**在给定温压条件下、与该物质处于平衡的水中该物质的浓度**。
> 这样的溶液叫**饱和溶液 (saturated solution)**，因为它**再也容纳不下更多的该盐**。

**过程图（Misra Fig. 7.5）判读**（老师逐帧描述）：
- 起始：烧瓶里有水 + 一堆未溶解的盐；
- 中间：盐逐步溶解，溶液中离子浓度**随时间缓慢上升**；
- 终态：浓度达到**饱和 (saturation)** 并不再变化，且**仍有剩余固体盐**。
- **关键概念对应**：
  - **饱和 = 平衡状态 (equilibrium state)**
  - **中间那个正在溶解的过程 = 非平衡 (disequilibrium)**

**溶解度积 $K_{sp}$**：就是把平衡常数写法用于"固体盐 ⇌ 离子"这个反应，且因为固体的"浓度"取 1，所以**分母消失，只剩右边离子浓度的乘积**。

**例 1 — 重晶石 barite (BaSO$_4$)：**
$$\ce{BaSO4_{(s)} = Ba^{2+} + SO4^{2-}} \qquad\Rightarrow\qquad K_{sp} = [\mathrm{Ba}^{2+}][\mathrm{SO_4}^{2-}]$$

**例 2 — 石盐 halite (NaCl)：**
$$\ce{NaCl_{(s)} = Na^+ + Cl^-} \qquad\Rightarrow\qquad K_{sp} = [\mathrm{Na}^+][\mathrm{Cl}^-]$$

**算例（slide + practical 共用）**：石盐的 $K_{sp} = 36$（25 °C）。含义是：与固体石盐平衡的水中，$[\mathrm{Na}^+]$（mol L$^{-1}$）乘以 $[\mathrm{Cl}^-]$（mol L$^{-1}$）等于 36。

因 NaCl 按 1:1 溶解，$[\mathrm{Na}^+] = [\mathrm{Cl}^-]$：
$$[\mathrm{Na}^+]^2 = 36 \;\Rightarrow\; [\mathrm{Na}^+] = [\mathrm{Cl}^-] = \sqrt{36} = 6\ \mathrm{mol\ L^{-1}}$$

⟹ **当 NaCl 浓度达到 6 mol L$^{-1}$ 时溶液饱和。**

### 2.21 地质应用：柴郡岩盐矿床 (Cheshire rock salt)

Wikipedia 引文（slide）：
> "Cheshire is a county in North West England. Rock salt was laid down in this region some **220 million years ago, during the Triassic period（三叠纪）**. Seawater moved inland from an open sea, creating a chain of **shallow salt marshes（浅盐沼）** across what is today the **Cheshire basin**. As the marshes evaporated, deep deposits of rock salt were formed."

**机制（slide 加粗）**：
> **The evaporating water reached saturation, resulting in precipitation of halite.**
> 蒸发使水量减少 → 离子浓度上升 → 达到 $K_{sp}$ 对应的饱和 → **石盐沉淀**。

老师补充（transcript）：这些盐矿**至今仍在开采**，可以参观；长期开采导致 **Northwich 一带地面大量沉陷 (subsidence)**。

---

## 三、公式与图表

### 3.1 从 $\alpha$ 反推 $\delta$：$-9.12‰$ 和 $-68.90‰$ 是怎么算出来的（完整推导）

这是本周最值得自己动手推一遍的计算。

**已知定义（W8）：**
$$\delta = \left(\frac{R_{\text{sample}}}{R_{\text{standard}}} - 1\right)\times 1000\ ‰ \qquad\qquad \alpha_{A\text{-}B} = \frac{R_A}{R_B}$$

其中 $R$ = 重同位素/轻同位素之比（如 $^{18}$O/$^{16}$O 或 D/H）。

**Step 1**：海水 = SMOW = 标准，所以 $R_{ow} = R_{\text{SMOW}}$，$\delta_{ow} = 0‰$。

**Step 2**：由分馏系数定义
$$\alpha_{ow\text{-}wv} = \frac{R_{ow}}{R_{wv}} \;\Rightarrow\; R_{wv} = \frac{R_{ow}}{\alpha_{ow\text{-}wv}} = \frac{R_{\text{SMOW}}}{\alpha_{ow\text{-}wv}}$$

**Step 3**：代入 $\delta$ 定义
$$\delta_{wv} = \left(\frac{R_{wv}}{R_{\text{SMOW}}} - 1\right)\times 1000 = \left(\frac{1}{\alpha_{ow\text{-}wv}} - 1\right)\times 1000$$

**Step 4 — 氧：**
$$\delta^{18}\mathrm{O}_{wv} = \left(\frac{1}{1.0092} - 1\right)\times 1000 = (0.990884 - 1)\times 1000 = \mathbf{-9.12\ ‰}\ ✓$$

**Step 5 — 氢：**
$$\delta\mathrm{D}_{wv} = \left(\frac{1}{1.074} - 1\right)\times 1000 = (0.931099 - 1)\times 1000 = \mathbf{-68.90\ ‰}\ ✓$$

> **速算近似**：当 $\alpha$ 接近 1 时，$\delta_{wv} \approx -(\alpha - 1)\times 1000$，即氧约 $-9.2‰$、氢约 $-74‰$。**近似对氧很准，对氢偏差较大**（因为 $\alpha_{\mathrm{H}} = 1.074$ 离 1 不够近），所以氢一定要用精确式。

### 3.2 反推第一批雨的 $\delta$（验证 Misra Fig. 11.4 的 "0" 点）

云中水汽 $\delta^{18}\mathrm{O}_{wv} = -9.12‰$；凝结是蒸发的逆过程，用同一个 $\alpha_{lw\text{-}wv}=1.0092$（液相在分子上）：

$$R_{\text{rain}} = 1.0092 \times R_{wv}$$
$$\frac{R_{\text{rain}}}{R_{\text{SMOW}}} = 1.0092 \times \frac{R_{wv}}{R_{\text{SMOW}}} = 1.0092 \times (1 + \tfrac{-9.12}{1000}) = 1.0092 \times 0.99088 = 1.0000$$
$$\Rightarrow \delta^{18}\mathrm{O}_{\text{rain}} = (1.0000 - 1)\times1000 \approx \mathbf{0\ ‰}\ ✓$$

**与图上第一对数值 $(-9,\ 0)$ 完全吻合。**

### 3.3 Misra Fig. 11.4 判读（"Equilibrium vaporization only"，25 °C）

**坐标**：横轴 = **剩余水汽的分数 (fraction of water vapour remaining)**，从 **1（左，全部水汽尚在云中）** 到 **0（右，云被降水耗尽）**；纵轴 = $\delta^{18}$O (‰)。

**两条曲线**：上面一条是**雨水 (rain)**，下面一条是**云中残余水汽 (vapour)**；两者始终相差约 **9–10‰**（= 平衡分馏量）。

| 阶段 | 水汽 $\delta^{18}$O | 该时刻降下的雨 $\delta^{18}$O |
|---|---|---|
| 起始（$f=1$，仅平衡分馏） | $-9$ | $0$ |
| 稍后 | $-11$ | $-2$ |
| … | … | … |
| 末尾（$f \to 0$） | $\approx -30$ | $\approx -20$ |

**对照：若把动力学分馏也算进去（实际大气）**，同样的两个阶段变成：

| 阶段 | 水汽 | 雨 |
|---|---|---|
| 起始 | $-13$ | $-3$ |
| 稍后 | $-15$ | $-5$ |

> **判读要诀**：① 雨永远比同时刻的水汽**重**（$\delta$ 大约 +9 到 +10）；② 两条线**都单调向下**；③ 只考虑平衡 vs 加入动力学 → 整体**平移约 $-4‰$**。

> **背景补充（超出讲义、帮助理解）**：这个过程在文献中叫 **瑞利蒸馏 (Rayleigh distillation)**，$R = R_0\,f^{(\alpha-1)}$，其中 $f$ 是剩余水汽分数。讲义没有要求这个公式，但它是图 11.4 曲线形状的来源——**知道有这么回事即可**。

### 3.4 全球大气降水线 GMWL

$$\delta\mathrm{D} = 8\,\delta^{18}\mathrm{O} + 10$$

- **斜率 8 的物理含义**：H 与 O 的平衡分馏程度之比。粗算 $\dfrac{74}{9.2} \approx 8$ —— 因为氢的分馏系数偏离 1 的程度约是氧的 8 倍。
- **截距 $+10$**：即所谓 **氘盈余 (deuterium excess)** $d = \delta\mathrm{D} - 8\delta^{18}\mathrm{O} = 10‰$，来源是海面蒸发时的**动力学（非平衡）分馏**。
- **数据点位置的意义**：越靠近原点 = 越接近海源、低纬、低海拔、高温；越向左下延伸 = 高纬、高海拔、低温、离海远。

### 3.5 pH 与平衡常数公式汇总

| 公式 | 表达式 | 符号含义 |
|---|---|---|
| pH 定义 | $\mathrm{pH} = -\log_{10}[\mathrm{H}^+]$ | $[\mathrm{H}^+]$ 单位 mol kg$^{-1}$ = mol L$^{-1}$ |
| 水的离子积 | $K_w = [\mathrm{H}^+][\mathrm{OH}^-] = 10^{-14}$ | 1 bar, 25 °C；已取 $[\mathrm{H_2O}]=1$ |
| 通用平衡常数 | $K = \dfrac{\prod(\text{RHS})^{\text{系数}}}{\prod(\text{LHS})^{\text{系数}}}$ | $K$ 是**比值，无量纲 (no units)** |
| 广义酸解离 | $K_a = \dfrac{[\mathrm{H}^+]^m[\mathrm{A}^-]^n}{[\mathrm{H}_m\mathrm{A}_n]}$ | $m,n$ = 分子式中的下标 |
| 广义碱解离 | $K_b = \dfrac{[\mathrm{B}^+]^p[\mathrm{OH}^-]^q}{[\mathrm{B}_p\mathrm{OH}_q]}$ | 同上 |
| 溶解度积 | $K_{sp} = [\text{阳离子}]^x[\text{阴离子}]^y$ | 固体不出现在式中 |

**代数操作要点（practical 明确提示）**：
> "Equations for equilibrium constants can be rearranged **just like any algebraic equation**."

即，若 $K = \dfrac{A}{B\cdot C}$，则 $A = K\cdot B\cdot C$。这是 Practical 里所有推导的机械基础。

**幂的运算律（practical 反复提醒"keep everything in powers of 10"）：**
$$10^X \times 10^Y = 10^{(X+Y)} \qquad\qquad \sqrt{10^X} = 10^{X/2}$$

### 3.6 CO$_2$–H$_2$O 体系的物种分布图（Bjerrum 图，Misra Fig. 7.6）

**图的内容**：CO$_2$–H$_2$O 溶液中各溶解物种的**活度 (activity)** 随 **pH** 的变化。**总溶解碳酸盐 $m_{\text{carb}} = 0.01$ mol kg$^{-1}$。**

**坐标**：横轴 = pH（0→14）；纵轴 = log(活度)。

**"活度 (activity)" 的含义（slide 专门解释）：**
> **Activity ≈ Concentration（活度 ≈ 浓度）**，但活度考虑了"离子的化学活性并不完全等于其浓度"这一事实——溶液中的化学相互作用会改变该离子参与反应的可及性。**活度是离子的"有效浓度 (effective concentration)"。**

**五条曲线及其判读：**

| 曲线 | 行为 |
|---|---|
| **H$^+$** | 一条**斜率 $-1$ 的直线**，从左上到右下（因为纵轴本质上就是 $\log[\mathrm{H}^+] = -\mathrm{pH}$） |
| **OH$^-$** | 一条**斜率 $+1$ 的直线**，随 pH 升高而升高 |
| **H$_2$CO$_3$ (aq)** | 在**低 pH（< ~6.35）占主导**，然后急剧下降 |
| **HCO$_3^-$（碳酸氢根 bicarbonate）** | 在**中等 pH（~6.35–10.3）占主导** |
| **CO$_3^{2-}$（碳酸根 carbonate）** | 在**高 pH（> ~10.3，碱性）占主导** |

**三个必须能在图上指出的位置：**
1. **pH = 7**：H$^+$ 与 OH$^-$ 两条线**相交**，$\log[\mathrm{H}^+] = \log[\mathrm{OH}^-] = -7$ ⟹ **中性**。
2. **pH = 5.66**：与大气 CO$_2$ 平衡的雨水 ⟹ 主导物种是 **H$_2$CO$_3$ (aq)**。
3. **pH ≈ 8**：海洋 ⟹ 主导物种是 **HCO$_3^-$**（海洋为**弱碱性 mildly basic**）。

---

## 四、课堂补充

以下内容 **transcript 里有、slides 上没有或极简略**：

### 4.1 概念澄清与记忆技巧

1. **"Meteoric ≠ meteorite"**：老师特意花时间破除这个误解（他本人研究陨石，所以特别在意）。
2. **"重的在水里，轻的在汽里"**：老师承认这个方向感很容易搞混，建议**不要硬记逻辑，直接看图上的数值走向**。他自己在课上都口误了一次并当场纠正。
3. **海洋 $\delta = 0$ 是"定义出来的"**，不是测量巧合——因为标准就是 SMOW。
4. **方括号 $[\ ]$ 只是"浓度"的记号**，不是要你把括号里的东西相乘；在代数运算中它就是一个普通变量。
5. **pH 为什么是 0–14、7 中性**：老师专门抛出这个问题（"whoever thought of a scale that went from 0 to 14?"），然后用 $K_w = 10^{-14}$ 给出了答案——**这是本周最漂亮的一个"因果闭环"，很可能是考点**。

### 4.2 老师补充的实例与轶事

- **新墨西哥州的降水同位素研究**：老师曾长期在新墨西哥工作，那里有位博士生**收集雨水、测量 O 和 H 同位素，用来判断这场雨的水汽是来自墨西哥湾 (Gulf of Mexico) 还是太平洋 (Pacific Ocean)**——因为新墨西哥正好夹在两个天气系统之间，同位素组成随天气型态变化。**这是"同位素追踪水汽源区"的经典应用。**
- **美国等值线图上的落基山区**："where I lived in New Mexico… we're at the southern end of the Rockies，如果北极冷空气南下导致温度下降，我们就会看到更大的分馏"——把**温度效应**与**天气系统**联系起来。
- **英国的雨**：开场提到"过去一周英国下了很多雨，很多地方下得太多了"，作为引入水主题的引子。
- **柴郡盐矿**：还在开采、可以参观、导致 Northwich 地面沉陷。
- **浴缸里不能用烤面包机**：解释电解质导电。
- **Mam Tor 野外实习**：老师做课堂调查，确认大家用的是**电子 pH 计**而非石蕊试纸或通用指示剂。
- **醋 (vinegar)**：家里就能做的酸碱指示实验。
- **苛性钠 NaOH 腐蚀皮肤**：强碱的直观例子。

### 4.3 老师特别展开的知识点（slides 上只有一张表）

**米兰科维奇旋回**：老师在课上问"你们在别的课上学过吗？"，看到"一片茫然的脸 (a lot of blank faces)"后，**从零讲起**：地球轨道会"摆动"，偏心率、倾角、岁差各自振荡，都源于**引力相互作用**，因而有**明确周期**。深海岩芯的 $\delta^{18}$O 曲线**看起来随机**，实际上是这些周期的**叠加**，可以**反卷积**分离出来。**这段解释在 slides 上完全没有，必须靠 transcript。**

### 4.4 与前几周的显式连接（老师主动做的"回顾"）

| 老师回顾的旧知识 | 用在哪里 |
|---|---|
| W8：同位素体 isotopologue、$\delta$、$\alpha$ | 水的 9 种同位素体、蒸发分馏 |
| W8：轻元素的质量差比例大 → 分馏显著 | 为什么 H、O 是好的温度示踪剂 |
| W6：开系统 vs 闭系统 | 海洋对水汽是开系统 → 动力学分馏被放大 |
| W1：电子壳层与共价键、惰性气体构型 | 水分子为什么形成 2 个 O–H 键 |
| W4：CH$_4$ 的 **sp$^3$ 杂化**、等角四面体 | **对比**：水分子为什么是弯的、有偶极 |
| W1–2：NaCl 的离子晶体结构 | 盐溶解时离子如何被水合 |
| W8 practical：矿床形成温度 | 稳定同位素应用的另一个例子 |

### 4.5 课程节奏提示

老师在讲到**解离常数广义式**和**溶解度积**时都说："there's an example of this **in the practical**, so I'm not going to walk through it now in the lecture."
⟹ **这两块的计算训练全部集中在 Practical 9**，讲义只给了框架。

老师对整个 Part 2 的总结：
> "it's basically all **the same principle** — 我们取一个在水中发生的反应，写出 $K$ 值，无论它叫**解离常数 (dissociation constant)**、**溶解度积 (solubility product)** 还是**反应常数 (reaction constant)**，**定义方式永远相同**。"

---

## 五、Practical 要点

### 5.0 目的 (Objectives)

1. 熟悉**水溶液（电解质溶液）中化学反应式的写法**；
2. 理解**为什么天然水会是酸性的**；
3. 考察**化学风化反应**，理解地表岩石如何通过化学机制分解。

### 5.A 碳酸 (Carbonic Acid)

#### 5.A.0 三个反应

CO$_2$ 溶于水形成碳酸：
$$\ce{CO2_{(g)} + H2O_{(l)} = H2CO3_{(aq)}} \qquad \textbf{(Reaction 1)}$$

碳酸是**弱酸**，**分两步解离**：
$$\ce{H2CO3_{(aq)} = H^+ + HCO3^-} \qquad \textbf{(Reaction 2)}\quad \text{碳酸氢根 bicarbonate}$$
$$\ce{HCO3^- = H^+ + CO3^{2-}} \qquad\ \ \textbf{(Reaction 3)}\quad \text{碳酸根 carbonate}$$

**两个关键结论（slide）：**
- **与大气 CO$_2$ 平衡的雨水本身就是酸性的。**
- **大气 CO$_2$ 越高，雨水越酸。**

**其他"酸雨 (acid rain)"来源：**
$$\ce{SO2}\ \text{气体} \longrightarrow \ce{H2SO4}\ \text{（硫酸 sulphuric acid）}$$
$$\ce{NO_x}\ \text{气体} \longrightarrow \ce{HNO3}\ \text{（硝酸 nitric acid）}$$

#### 5.A.1 Q1 — 写出三个平衡常数

$$K_1 = \frac{[\mathrm{H_2CO_3}]_{(aq)}}{[\mathrm{CO_2}]_{(g)}\,[\mathrm{H_2O}]_{(l)}}$$
$$K_2 = \frac{[\mathrm{H}^+]\,[\mathrm{HCO_3}^-]}{[\mathrm{H_2CO_3}]}$$
$$K_3 = \frac{[\mathrm{H}^+]\,[\mathrm{CO_3}^{2-}]}{[\mathrm{HCO_3}^-]}$$

（Reaction 2、3 中所有物种都是 aq。）

#### 5.A.2 Q2 — 稀溶液简化

对**极稀溶液**，$[\mathrm{H_2O}] = 1$，所以：
$$K_1 = \frac{[\mathrm{H_2CO_3}]_{(aq)}}{[\mathrm{CO_2}]_{(g)}} = \frac{[\mathrm{H_2CO_3}]_{(aq)}}{P_{\mathrm{CO_2}}}$$

**记号约定**：因为 CO$_2$ 是气体，用它的**分压 (partial pressure) $P_{\mathrm{CO_2}}$** 代替 $[\mathrm{CO_2}]_{(g)}$。

#### 5.A.3 计算 $K_1$ 的值（完整步骤，Misra Example 4-1, p. 53）

**(a) 单位换算：g/100 g → mol kg$^{-1}$**

已知：1 bar、298.15 K 下，CO$_2$ 在水中的溶解度 = **0.148 g CO$_2$ / 100 g 水**。

Step 1 — 换成 g kg$^{-1}$（乘 10）：
$$0.148\ \mathrm{g/100\ g} \times 10 = \mathbf{1.48\ g\ kg^{-1}}$$

Step 2 — 换成 mol kg$^{-1}$（原子量 C = 12，O = 16）：
$$M(\mathrm{CO_2}) = 12 + (16\times2) = \mathbf{44}$$
$$n = \frac{1.48}{44} = \mathbf{0.0336\ mol}$$
$$\Rightarrow \text{溶解度} = 0.0336\ \mathrm{mol\ kg^{-1}}$$

**(b) 化学计量假设**

假设**每溶解 1 mol CO$_2$ 就生成 1 mol H$_2$CO$_3$ (aq)**（Reaction 1 是 1:1）。
$$\Rightarrow n(\mathrm{H_2CO_3}) \text{ in 1 kg solution} = n(\mathrm{CO_2}) = 0.0336\ \mathrm{mol}$$
$$\Rightarrow [\mathrm{H_2CO_3}] = 0.0336\ \mathrm{mol\ kg^{-1}}$$

**(c) 求 $K_1$**

假设 $P_{\mathrm{CO_2}} = 1$ bar（这正是溶解度数据对应的条件）：
$$K_1 = \frac{[\mathrm{H_2CO_3}]}{P_{\mathrm{CO_2}}} = \frac{0.0336}{1} = 0.0336$$

化成 10 的幂（取对数）：
$$\log_{10}(0.0336) = \log_{10}(3.36\times10^{-2}) = 0.526 - 2 = -1.474$$
$$\boxed{K_1 = 10^{-1.47}}$$

> **$K$ 是一个比值，没有单位 (K is a ratio and has no units)。**

#### 5.A.4 计算与大气平衡的雨水 pH（Misra Ch. 7.5.1）—— 本周最重要的算题

**(a) 求实际大气条件下的 $[\mathrm{H_2CO_3}]$**

大气 CO$_2$ 分压 $P_{\mathrm{CO_2}} = 10^{-3.5}$ bar（≈ 316 ppm）。由 $K_1$ 表达式移项：
$$[\mathrm{H_2CO_3}]_{(aq)} = K_1 \times P_{\mathrm{CO_2}} = 10^{-1.47} \times 10^{-3.5}$$
$$= 10^{(-1.47-3.5)} = \boxed{10^{-4.97}\ \mathrm{mol\ kg^{-1}}}$$

**(b) 由 $K_2$ 反解 $[\mathrm{H}^+]$**

$$K_2 = \frac{[\mathrm{H}^+][\mathrm{HCO_3}^-]}{[\mathrm{H_2CO_3}]} \qquad\Rightarrow\qquad [\mathrm{H}^+] = \frac{K_2 \times [\mathrm{H_2CO_3}]_{(aq)}}{[\mathrm{HCO_3}^-]}$$

**(c) 电中性近似**

假设 $[\mathrm{HCO_3}^-] = [\mathrm{H}^+]$（因为在这个 pH 区间，Reaction 2 是 H$^+$ 的唯一重要来源，H$^+$ 与 HCO$_3^-$ 成对产生；详见 Misra）：
$$[\mathrm{H}^+] = \frac{K_2 \times [\mathrm{H_2CO_3}]}{[\mathrm{H}^+]} \qquad\Rightarrow\qquad \boxed{[\mathrm{H}^+]^2 = K_2 \times [\mathrm{H_2CO_3}]_{(aq)}}$$

**(d) 代数值**

已知 $K_2 = 10^{-6.35}$：
$$[\mathrm{H}^+]^2 = 10^{-6.35} \times 10^{-4.97} = 10^{(-6.35-4.97)} = 10^{-11.32}$$
$$[\mathrm{H}^+] = \sqrt{10^{-11.32}} = 10^{-11.32/2} = \boxed{10^{-5.66}\ \mathrm{mol\ kg^{-1}}}$$

**(e) 转成 pH**
$$\mathrm{pH} = -\log_{10}[\mathrm{H}^+] = -\log_{10}(10^{-5.66}) = \boxed{\mathbf{5.66}}$$

**如何描述这个溶液？** → **弱酸性 (mildly acidic)**

> **物理意义（务必理解）**：这就是**"天然雨水本来就是酸性的"** 的定量证明——**即使完全没有工业污染**，雨水与大气 CO$_2$ 平衡后 pH 也只有 5.66，而非 7。这是**化学风化的天然驱动力**。（真正的"酸雨"指 SO$_2$/NO$_x$ 造成的 pH 明显更低的情况。）

#### 5.A.5 (f) Bjerrum 图判读题（5 小问，全部答案）

**i) H$^+$ 和 OH$^-$ 的浓度随 pH 变化是否符合预期？**
> 符合。**H$^+$ 随 pH 降低而升高；OH$^-$ 随 pH 升高而升高。** 这正是 $\mathrm{pH} = -\log[\mathrm{H}^+]$ 所要求的。**H$^+$ 那条线是斜率为 $-1$ 的直线**，因为**纵轴本质上就是 $\log[\mathrm{H}^+]$**。

**ii) 图上如何体现 pH = 7 时溶液"中性"？**
> 在 pH 7 处，**H$^+$ 与 OH$^-$ 的量相等（两条线相交）**，所以溶液**既不酸也不碱**。此时 $\log[\mathrm{H}^+] = \log[\mathrm{OH}^-] = -7$。

**iii) 把 (e) 算出的 pH 标在图上，该 pH 下的主导物种是什么？**
> pH = **5.66**；主导（浓度最高）物种是 **H$_2$CO$_3$ (aq)**。

**iv) 海洋 pH 约为 8，主导物种是什么？如何描述海洋？**
> 主导物种是 **HCO$_3^-$（碳酸氢根 / 重碳酸根）**。海洋是 **mildly basic（弱碱性）**。

**v) 什么样的溶液中碳酸根 CO$_3^{2-}$ 浓度高？**
> **碱性溶液 (basic solution)**，例如 **pH > 11**。

### 5.B 风化反应 (Weathering Reactions)

#### 5.B.0 化学风化总论（lecture 与 practical 共有的定义，必须能背）

> **化学风化 (chemical weathering)** 是指**地表矿物与水（尤其是酸性水）以及大气中的气体（CO$_2$ 和 O$_2$）相互作用，形成在环境温压 (ambient P-T) 条件下热力学上更稳定的矿物组合 (mineral assemblages) 的过程。**

**酸的来源**：
- **生物成因 (biogenic activity)**：植物活动、细菌代谢
- **酸性雨水**

**化学风化可以包含（反应类型）：**

| 类型 | 英文 | 例子 |
|---|---|---|
| 溶解 | **dissolution** | 石盐溶解、碳酸盐溶解 |
| 水合 | **hydration** | 石膏的形成 |
| 水解 | **hydrolysis** | 长石 → 高岭石 |
| 氧化 | **oxidation** | 铁矿物 → 赤铁矿/针铁矿 |
| 碳酸化 | **carbonation** | 与溶解并列，由碳酸驱动 |

**常见的风化产物 (products)：**
- **黏土矿物 (clay minerals)**：**高岭石 kaolinite、蒙脱石 smectite** —— 由**水解 hydrolysis** 形成
- **氧化物、氢氧化物**：**赤铁矿 hematite、针铁矿 goethite、三水铝石 gibbsite** —— 由**氧化 oxidation** 形成

**slides 上的野外实例照片：**

| 照片 | 风化类型 |
|---|---|
| 石灰岩，Malham Cove（英国约克郡） | **溶解 + 碳酸化 dissolution & carbonation** |
| 石膏，White Sands, New Mexico | **水合 hydration** |
| Ghost Ranch, New Mexico（红层） | **氧化 oxidation** |
| 高岭土矿，保加利亚 | **水解 hydrolysis** |

#### 5.B.1 溶解反应 (Dissolution Reactions)

> 在溶解反应中，矿物**直接溶解进入水中**。反应通常由**酸性水驱动**。**碳酸盐岩极易受这类化学风化影响**，**碳酸 H$_2$CO$_3$ 是关键驱动酸**。

**方解石 calcite 溶解（题目给出的已配平范例）：**
$$\ce{CaCO3_{(s)} + H2CO3_{(aq)} = Ca^{2+} + 2HCO3^-}$$

> ⚠️ **核心提醒（feedback 加粗）**：**电荷 (CHARGES) 必须配平，元素也必须配平。**
> 检验：左边净电荷 = 0（两个都是中性分子）；右边 = $(+2) + 2\times(-1) = 0$ ✓
> 元素：Ca 1=1；C 1+1=2 ✓；O 3+3=6 = 2×3 ✓；H 2 = 2×1 ✓

**白云石 dolomite 溶解（题目要求自己配平）：**

未配平骨架：$\ce{CaMg(CO3)2_{(s)} + H2CO3_{(aq)} = Ca^{2+} + Mg^{2+} + HCO3^-}$

**答案：**
$$\ce{CaMg(CO3)2_{(s)} + \mathbf{2}H2CO3_{(aq)} = Ca^{2+} + Mg^{2+} + \mathbf{4}HCO3^-}$$

**配平检验：**
| 元素/电荷 | 左 | 右 |
|---|---|---|
| Ca | 1 | 1 ✓ |
| Mg | 1 | 1 ✓ |
| C | 2 + 2 = 4 | 4 ✓ |
| O | 6 + (2×3) = 12 | 4×3 = 12 ✓ |
| H | 2×2 = 4 | 4×1 = 4 ✓ |
| **电荷** | 0 | $(+2)+(+2)+4(-1) = 0$ ✓ |

> **解题思路**：白云石含 **2 个 CO$_3$**（比方解石多一个）和 **2 个阳离子**，所以碳酸系数从 1 加倍到 2、碳酸氢根从 2 加倍到 4。**"方解石反应 × 2 再合并"** 是最快的心算路径。

**问答题：为什么河水和地下水含大量 Ca$^{2+}$ 和 HCO$_3^-$？若大气 CO$_2$ 更高会怎样？**

**标准答案（feedback 原文思路）：**
1. 大气中的 CO$_2$ **溶于水，形成碳酸 H$_2$CO$_3$**（Reaction 1）。
2. 碳酸**解离**，生成 **HCO$_3^-$ 和 H$^+$**（Reaction 2）。
3. H$^+$ 意味着**溶液呈酸性**，这**增强了碳酸盐矿物的溶解**。
4. 碳酸盐矿物溶解后，水中就富含 **Ca$^{2+}$ 和 HCO$_3^-$**。
5. **若大气 CO$_2$ 更高** ⟹ 水更酸 ⟹ **碳酸盐矿物溶解速率提高** ⟹ **水中这些溶解离子的量增加**。

> 这道题把 **Part A（碳酸体系）** 与 **Part B（风化）** 串成了一条完整因果链，是本 practical 的**主旨题**。

#### 5.B.2 水解反应 (Hydrolysis Reactions)

> **大多数硅酸盐矿物**的风化反应，除了溶解物种之外，**还有一个或多个固体反应产物**。典型例子是**钾长石 (K-feldspar) 风化成黏土矿物高岭石 (kaolinite)**。此反应**发生在酸性溶液中**。产物包括溶液中的 **K$^+$ 离子**和**硅酸 H$_4$SiO$_4$**。
> （硅酸是弱酸，行为与碳酸类似。）

**配平后的反应（本题要求自己配平）：**
$$\ce{\mathbf{2}KAlSi3O8_{(s)} + \mathbf{9}H2O_{(l)} + \mathbf{2}H^+ = Al2Si2O5(OH)4_{(s)} + \mathbf{2}K^+ + \mathbf{4}H4SiO4_{(aq)}}$$

$$\underbrace{\text{钾长石}}_{\text{K-feldspar}} + \underbrace{\text{水}}_{\text{water}} + \underbrace{\text{酸}}_{\text{acid}} = \underbrace{\text{高岭石}}_{\text{kaolinite}} + \underbrace{\text{钾离子}}_{\text{K}^+} + \underbrace{\text{硅酸}}_{\text{silicic acid}}$$

**配平方法（feedback 明确给出的窍门）：按 Al → Si → O → H → K 的顺序配平。**

**逐步演示：**

1. **Al**：高岭石 Al$_2$Si$_2$O$_5$(OH)$_4$ 有 **2 个 Al**，而长石每个只有 1 个 Al ⟹ **长石系数 = 2**。
2. **Si**：左边 $2\times3 = 6$ 个 Si；高岭石用掉 2 个 ⟹ 剩 4 个 Si 必须进入硅酸 ⟹ **H$_4$SiO$_4$ 系数 = 4**。
3. **O**：右边 O 总数 = 高岭石 $(5 + 4) = 9$ + 硅酸 $4\times4 = 16$ ⟹ **共 25**。
   左边长石贡献 $2\times8 = 16$ ⟹ 还差 $25 - 16 = 9$ ⟹ **H$_2$O 系数 = 9**。
4. **H**：右边 H 总数 = 高岭石 (OH)$_4$ 的 4 + 硅酸 $4\times4 = 16$ ⟹ **共 20**。
   左边水贡献 $9\times2 = 18$ ⟹ 还差 2 ⟹ **H$^+$ 系数 = 2**。
5. **K**：左边 $2\times1 = 2$ ⟹ **K$^+$ 系数 = 2** ✓
6. **电荷校验**：左边 $= 2\times(+1) = +2$；右边 $= 2\times(+1) = +2$ ✓

**完整核对表：**
| | 左 | 右 |
|---|---|---|
| K | 2 | 2 ✓ |
| Al | 2 | 2 ✓ |
| Si | 6 | 2 + 4 = 6 ✓ |
| O | 16 + 9 = 25 | 9 + 16 = 25 ✓ |
| H | 18 + 2 = 20 | 4 + 16 = 20 ✓ |
| 电荷 | +2 | +2 ✓ |

> **为什么先配 Al？** 因为 Al 只出现在**两个物种**里（长石与高岭石），自由度最小，最先被"锁死"。**先配出现次数最少的元素、最后配 H 和 O（以及可自由调整的离子）**，是配平的通用策略——W5 学过，这里是它在硅酸盐风化上的直接应用。

#### 5.B.3 水合反应与溶解度 (Hydration Reactions and Solubility)

> **水合反应**把**无水 (anhydrous) 矿物**转变成**含水 (hydrated) 矿物**。典型例子是硫酸钙矿物：**硬石膏 anhydrite (CaSO$_4$) → 石膏 gypsum (CaSO$_4\cdot$2H$_2$O)**。硬石膏形成于**蒸发岩 (evaporite) 沉积**中，与**石盐 halite (NaCl)** 共生。

**(a) 蒸发岩形成与水合反应**

**蒸发岩成因**：湖水蒸发 ⟹ **水中盐类离子达到饱和 ⟹ 盐类沉淀**。

石盐沉淀（题目给出的范例）：
$$\ce{Na^+_{(aq)} + Cl^-_{(aq)} = NaCl_{(s)}}$$

**写出硬石膏的形成反应（答案）：**
$$\ce{Ca^{2+} + SO4^{2-} = CaSO4}$$

**写出硬石膏水合成石膏的反应（答案）：**
$$\ce{CaSO4 + 2H2O = CaSO4.2H2O}$$

> **补充（feedback 括注）**：**这个转变是可逆的 (reversible)** —— 在**常压条件下加热到约 200 °C**，石膏会脱水变回硬石膏。

**(b) 溶解度积计算**

**写出硬石膏的溶解度积（答案）：**
$$K_{sp} = [\mathrm{Ca}^{2+}] \times [\mathrm{SO_4}^{2-}]$$

> **重要概念点（feedback 特别解释）**：**石膏的溶解度积表达式与硬石膏完全相同**，因为**石膏中的结晶水在溶解时直接并入溶剂 (the water in gypsum just becomes part of the solvent)**，不出现在 $K_{sp}$ 中。

---

**例题 1：石盐能在 1 升水中溶解多少克？**

已知 25 °C 时 $K_{sp}(\mathrm{NaCl}) = 36$；原子量 Na = 23，Cl = 35.5。

$$K_{sp} = [\mathrm{Na}^+][\mathrm{Cl}^-] = 36$$

因 NaCl 按 1:1 溶解，$[\mathrm{Na}^+] = [\mathrm{Cl}^-]$：
$$[\mathrm{Na}^+]^2 = 36 \;\Rightarrow\; [\mathrm{Na}^+] = [\mathrm{Cl}^-] = \sqrt{36} = 6\ \mathrm{mol\ L^{-1}}$$

即：饱和 NaCl 溶液含 6 mol L$^{-1}$ Na$^+$ 和 6 mol L$^{-1}$ Cl$^-$，**等价于 6 mol 的 NaCl**。

$$M(\mathrm{NaCl}) = 23 + 35.5 = 58.5$$
$$m = n \times M = 6 \times 58.5 = \boxed{351\ \mathrm{g\ per\ litre}}$$

> feedback 上还追问了一句 **"(units?)"** —— 提醒同学**答案必须带单位**：**351 g L$^{-1}$**（或"351 g 溶于 1 L 水"）。

---

**例题 2：石膏能在 1 升水中溶解多少克？**

已知 25 °C 时 $K_{sp}(\text{gypsum}) = 2.4\times10^{-5}$；原子量 Ca = 40，S = 32，O = 16，（H = 1）。

$$K_{sp} = [\mathrm{Ca}^{2+}][\mathrm{SO_4}^{2-}] = 2.4\times10^{-5}$$
$$[\mathrm{Ca}^{2+}] = [\mathrm{SO_4}^{2-}] = \sqrt{2.4\times10^{-5}} = 4.9\times10^{-3} \approx 0.005\ \mathrm{mol\ L^{-1}}$$

⟹ **溶解的石膏为 0.005 mol**（1:1 化学计量）。

**石膏分子量**（CaSO$_4\cdot$2H$_2$O）：
$$M = \underbrace{40}_{\mathrm{Ca}} + \underbrace{32}_{\mathrm{S}} + \underbrace{4\times16 = 64}_{\mathrm{O_4}} + \underbrace{2\times18 = 36}_{\mathrm{2H_2O}} = \mathbf{172}$$

$$m = 0.005 \times 172 = \boxed{0.86\ \mathrm{g\ per\ litre}}$$

> **对比结论（很重要的地球化学意义）**：石盐 **351 g L$^{-1}$** vs 石膏 **0.86 g L$^{-1}$**，**相差约 400 倍**。这解释了**蒸发岩的沉淀顺序**：蒸发时**溶解度小的先沉淀**（碳酸盐 → 石膏/硬石膏 → 石盐 → 钾盐），所以**石膏总是出现在石盐之下**。这也是为什么石盐矿床（如柴郡）需要**极度**蒸发才能形成。

---

## 六、易错点 / 重点难点

### 6.1 概念性易错

1. **Meteoric ≠ meteorite**。Meteoric water = 大气降水，和陨石毫无关系。
2. **"轻/重"与 $\delta$ 正负的方向**。$\delta$ 越负 = 越"轻"（越富集轻同位素）。口诀：**重的留在液相（水），轻的进入气相（汽）**。老师自己在课上都说反过一次。
3. **$\alpha > 1$ 时谁富集重同位素？** 看 $\alpha_{A\text{-}B} = R_A/R_B$ 的**分子**——分子那一相富集重同位素。$\alpha_{ow\text{-}wv} = 1.0092 > 1$ ⟹ **海水**富集 $^{18}$O。
4. **海洋 $\delta^{18}$O = 0 是定义，不是巧合**。
5. **冰期时海洋 $\delta^{18}$O 变正（更高）**。很多人会直觉搞反——记住：**冰盖锁住 $^{16}$O**（因为极地降雪极负），所以留在海里的相对更富 $^{18}$O。
6. **McSween p. 272 的 GMWL 方程是错的**（slide 明确警告）。用 $\delta\mathrm{D} = 8\delta^{18}\mathrm{O} + 10$。
7. **Base 与 alkali 的区别**：alkali = **溶于水的** base。很多 base 不溶于水。
8. **盐的定义有三个"排除项"**：阳离子不能是 H$^+$，阴离子不能是 OH$^-$ 或 O$^{2-}$。
9. **方括号 $[\ ]$ 是"浓度"记号，不是乘法括号。**
10. **CH$_4$ 是等角四面体（sp$^3$），H$_2$O 是弯的**。这正是水有极性、甲烷没有的原因。**不要**把水画成直线形。

### 6.2 计算性易错

11. **由 $\alpha$ 求 $\delta$ 必须用精确式** $\delta_{wv} = (1/\alpha - 1)\times1000$。对氢用近似式 $-(\alpha-1)\times1000$ 会得到 $-74$ 而不是 $-68.9$，误差 5‰，**不可接受**。
12. **平衡常数的书写方向**：**永远是右边(产物) ÷ 左边(反应物)**。写反了 $K$ 就变成倒数。
13. **化学计量系数要写成指数**，例如 Mg(OH)$_2$ 的 $K_b$ 里 $[\mathrm{OH}^-]$ 必须**平方**。
14. **纯水 / 固体的"浓度"取 1**，不出现在 $K$ 的表达式中（$[\mathrm{H_2O}]=1$；$K_{sp}$ 里没有固体项）。
15. **气体用分压 $P$ 代替浓度**。
16. **全程用 10 的幂运算**（practical 反复叮嘱）：$10^X\cdot10^Y = 10^{X+Y}$；$\sqrt{10^X} = 10^{X/2}$。这能避免小数舍入误差。
17. **$K$ 无量纲**（它是比值）。
18. **配平反应式时电荷也必须配平**，不只是元素。这在离子反应中极易漏掉。
19. **硅酸盐水解的配平顺序**：Al → Si → O → H → K。乱序配会陷入死循环。
20. **单位换算别漏**：g/100 g → g/kg 要 **×10**；g → mol 要 **÷ 分子量**。
21. **石膏分子量要算上结晶水**：CaSO$_4\cdot$2H$_2$O = 172，不是 136。
22. **$K_{sp}$ 求浓度要开方**（1:1 盐类），不是直接等于 $K_{sp}$。
23. **答案要写单位**（feedback 专门用 "(units?)" 提醒过）。

### 6.3 需要重点理解（而非死记）的三条因果链

**链 A — pH 标度的由来：**
$$K_w = 10^{-14} \;\Rightarrow\; [\mathrm{H}^+]=[\mathrm{OH}^-]=10^{-7} \;\Rightarrow\; \mathrm{pH}_{\text{中性}} = 7 \;\Rightarrow\; \text{标度 }0\text{–}14$$

**链 B — 天然雨水为什么是酸的（并进而驱动风化）：**
$$\mathrm{CO_2\ (大气)} \to \mathrm{H_2CO_3} \to \mathrm{H^+ + HCO_3^-} \;\Rightarrow\; \mathrm{pH}=5.66 \;\Rightarrow\; \text{酸性水溶解碳酸盐/水解硅酸盐}$$
$$\Rightarrow\ \text{河水富含 Ca}^{2+}\text{、HCO}_3^- \;\Rightarrow\; \text{CO}_2\text{ 越高 → 越酸 → 风化越快}$$

**链 C — 水的同位素为什么能读出古气候：**
$$\text{温度}\downarrow \Rightarrow \text{分馏}\uparrow \Rightarrow \text{极地降雪 }\delta\text{ 极负（富 }^{16}\mathrm{O}) \Rightarrow \text{冰期冰盖锁住 }^{16}\mathrm{O} \Rightarrow \text{海水 }\delta^{18}\mathrm{O}\uparrow$$
$$\Rightarrow \text{深海有孔虫/沉积岩芯记录冰量} \;;\; \text{冰芯 }\delta\mathrm{D}\text{ 记录温度} \;;\; \text{周期} = \text{Milankovitch}$$

---

## 七、本周术语表

### 7.1 同位素与古气候部分

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| **Meteoric water** | 大气降水 / 天水 | 由大气通过降水或凝结形成的水（雨、雪等）；与陨石无关 |
| **Isotopologue** | 同位素体 | 同一种分子的不同同位素取代版本；水有 9 种 |
| **SMOW** | 标准平均海水 | Standard Mean Ocean Water，$\delta^{18}$O 与 $\delta$D 的参考标准，定义为 0‰ |
| **Fractionation factor $\alpha$** | 分馏系数 | 两相同位素比值之比，$\alpha_{A\text{-}B}=R_A/R_B$；$>1$ 表示 A 相富集重同位素 |
| **Equilibrium fractionation** | 平衡分馏 | 双向交换达到平衡时的同位素分配差异 |
| **Kinetic isotope effect** | 动力学同位素效应 | 轻同位素分子运动/反应更快造成的额外分馏；在开系统中被放大 |
| **Open system** | 开放系统 | 可与外界交换物质和能量；海面蒸发即是 |
| **Closed system** | 封闭系统 | 只交换能量、不交换物质 |
| **Latitude effect** | 纬度效应 | 高纬温度低 → 分馏大 → 降水 $\delta$ 更负 |
| **Elevation / altitude effect** | 高程效应 | 高海拔温度低 → 降水 $\delta$ 更负 |
| **GMWL** | 全球大气降水线 | $\delta\mathrm{D}=8\delta^{18}\mathrm{O}+10$；全球降水都落在这条线上或附近 |
| **Palaeoclimatology** | 古气候学 | 通过代用指标重建地质历史时期气候的学科 |
| **Glacial / Interglacial** | 冰期 / 间冰期 | 冰盖扩张期 / 收缩期；海水 $\delta^{18}$O 分别偏正 / 偏负 |
| **Milankovitch cycles** | 米兰科维奇旋回 | 地球轨道参数变化引起的日射量周期性变化，驱动冰期旋回 |
| **Eccentricity** | 偏心率 | 轨道椭圆度；周期 123 / 85 / 58 ka |
| **Obliquity / Tilt** | 黄赤交角 / 倾角 | 自转轴倾角振荡；周期 41 ka |
| **Precession** | 岁差 | 自转轴指向的进动；周期 23 / 18 ka |
| **Insolation** | 日射量 | 地表接收的太阳能通量 |
| **Ice core** | 冰芯 | 极地冰盖钻取的柱状样；南极最长 800 ka，格陵兰 123 ka |
| **Temperature proxy** | 温度代用指标 | 用 $\delta$D 或 $\delta^{18}$O 间接反演古温度 |
| **Deconvolve** | 反卷积 / 解卷积 | 从叠加信号中分离出各个周期成分 |

### 7.2 水化学部分

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| **Polar solvent** | 极性溶剂 | 分子内电荷分布不均、具有偶极的溶剂；水是典型 |
| **Solvent** | 溶剂 | 溶解别的物质的介质（水） |
| **Solute** | 溶质 | 被溶解的物质（NaCl） |
| **Solution** | 溶液 | 溶剂 + 溶质的组合 |
| **(aq) / (s) / (l) / (g)** | 水溶液 / 固 / 液 / 气 | 反应式中标注物种的相态 |
| **Electrolyte solution** | 电解质溶液 | 含自由离子、能导电的溶液 |
| **Salt** | 盐 | 溶于水的离子化合物（阳离子非 H$^+$、阴离子非 OH$^-$/O$^{2-}$）；也是酸碱中和的产物 |
| **Acid** | 酸 | 溶于水产生 H$^+$ 的物质；质子给体 (proton donor) |
| **Base** | 碱 | 能中和酸的物质；许多不溶于水 |
| **Alkali** | 碱液 / 可溶碱 | 溶于水的碱，溶解时产生 OH$^-$ |
| **Neutralisation** | 中和反应 | H$^+$ + OH$^-$ → H$_2$O；酸 + 碱液 = 盐 + 水 |
| **pH** | 酸碱度 | "potential Hydrogen"；$\mathrm{pH}=-\log_{10}[\mathrm{H}^+]$ |
| **Universal indicator** | 通用指示剂 | 用颜色给出 0–14 连续 pH 读数的指示剂 |
| **Litmus paper** | 石蕊试纸 | 只能粗判酸碱的试纸 |
| **Hydronium ion** | 水合氢离子 | H$_3$O$^+$；水中 H$^+$ 的真实存在形式 |
| **Equilibrium constant $K$** | 平衡常数 | 右边物种浓度乘积 ÷ 左边物种浓度乘积；无量纲 |
| **$K_w$** | 水的离子积 | $[\mathrm{H}^+][\mathrm{OH}^-]=10^{-14}$（1 bar, 25 °C） |
| **Dissociation constant $K_a$/$K_b$** | 解离常数 | 酸/碱解离反应的平衡常数；越大解离越完全 |
| **Strong / weak acid** | 强酸 / 弱酸 | 在水中几乎完全解离 / 只有小部分解离 |
| **Acidity** | 酸度 | 溶液给出质子的能力 |
| **Alkalinity** | 碱度 | 溶液接受质子的能力 |
| **Proton donor / acceptor** | 质子给体 / 受体 | 酸 / 碱的 Brønsted–Lowry 定义 |
| **Solubility** | 溶解度 | 给定 P-T 下与固相平衡的溶液中该物质的浓度 |
| **Saturated solution** | 饱和溶液 | 再也溶不进更多溶质的溶液；对应平衡态 |
| **Solubility product $K_{sp}$** | 溶解度积 | 饱和溶液中各离子浓度（按系数取幂）的乘积 |
| **Disequilibrium** | 非平衡 | 尚未达到饱和/平衡的中间状态 |
| **Activity** | 活度 | 离子的"有效浓度"，考虑了溶液内相互作用；活度 ≈ 浓度 |
| **Partial pressure $P_{\mathrm{CO_2}}$** | 分压 | 气体在 $K$ 表达式中代替浓度使用的量 |

### 7.3 风化与矿物部分

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| **Chemical weathering** | 化学风化 | 地表矿物与水和大气气体反应，生成在环境 P-T 下更稳定的矿物组合 |
| **Dissolution** | 溶解（作用） | 矿物直接溶入水中，如石盐、碳酸盐 |
| **Carbonation** | 碳酸化 | 由碳酸驱动的溶解风化 |
| **Hydration** | 水合（作用） | 无水矿物转变为含水矿物，如硬石膏 → 石膏 |
| **Hydrolysis** | 水解（作用） | 硅酸盐在酸性水中分解，生成黏土矿物 + 溶解物种 |
| **Oxidation** | 氧化（作用） | 生成氧化物/氢氧化物的风化，如赤铁矿、针铁矿 |
| **Mineral assemblage** | 矿物组合 | 共生的一组矿物 |
| **Ambient P-T** | 环境温压条件 | 地表的常温常压 |
| **Biogenic activity** | 生物成因活动 | 植物活动、细菌代谢等产酸过程 |
| **Acid rain** | 酸雨 | SO$_2$→H$_2$SO$_4$、NO$_x$→HNO$_3$ 造成的额外酸化 |
| **Carbonic acid H$_2$CO$_3$** | 碳酸 | CO$_2$ 溶于水形成的弱酸；风化的主要天然驱动酸 |
| **Bicarbonate HCO$_3^-$** | 碳酸氢根 / 重碳酸根 | 碳酸第一步解离产物；pH 6.35–10.3 的主导物种，海水中主导 |
| **Carbonate CO$_3^{2-}$** | 碳酸根 | 第二步解离产物；仅在强碱性（pH > 11）占主导 |
| **Silicic acid H$_4$SiO$_4$** | 硅酸 | 硅酸盐水解释放的弱酸 |
| **Calcite CaCO$_3$** | 方解石 | 最常见的碳酸盐矿物 |
| **Dolomite CaMg(CO$_3$)$_2$** | 白云石 | 含 Ca 和 Mg 的碳酸盐矿物 |
| **K-feldspar KAlSi$_3$O$_8$** | 钾长石 | 常见硅酸盐；水解产物为高岭石 |
| **Kaolinite Al$_2$Si$_2$O$_5$(OH)$_4$** | 高岭石 | 水解生成的黏土矿物 |
| **Smectite** | 蒙脱石 | 另一类水解生成的黏土矿物 |
| **Hematite / Goethite / Gibbsite** | 赤铁矿 / 针铁矿 / 三水铝石 | 氧化风化生成的氧化物与氢氧化物 |
| **Halite NaCl** | 石盐 | 蒸发岩矿物；$K_{sp}=36$，溶解度 351 g L$^{-1}$ |
| **Anhydrite CaSO$_4$** | 硬石膏 | 无水硫酸钙，蒸发岩矿物 |
| **Gypsum CaSO$_4\cdot$2H$_2$O** | 石膏 | 含水硫酸钙；$K_{sp}=2.4\times10^{-5}$，溶解度 0.86 g L$^{-1}$ |
| **Evaporite** | 蒸发岩 | 水体蒸发至饱和后盐类沉淀形成的岩石 |
| **Barite BaSO$_4$** | 重晶石 | 硫酸钡矿物，$K_{sp}=[\mathrm{Ba}^{2+}][\mathrm{SO_4}^{2-}]$ |
| **Subsidence** | 地面沉陷 | 盐矿开采造成的地表下沉（柴郡 Northwich） |
