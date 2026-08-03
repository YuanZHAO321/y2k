# Week 4 — 空气污染数据分析与野火排放估算 (Air Pollution & Wildfire Emissions) / 显微镜下的三大岩类 (Microscope Practical Class 2)

> 课程：EART11300 Practical and Professional Skills Development，Hilary Term (春季学期) Week 4
> 本周材料：`Week 4/Morning/`（4 个 md）+ `Week 4/Afternoon/`（2 个 md，问题+答案配套），共 6 个 md，是本学期材料量最大的一周。
> 本课无 lecture、无录音转写，全部内容来自 practical worksheet / dataset / answer sheet。
>
> **本周结构**：上午场与下午场是两场完全独立、主题无关的实践课。
> - **上午（Morning）**：环境科学 / 大气化学方向 —— 用一份模拟城市的空气污染数据集做数据分析；用网页版城市空气污染模拟器 (simcity) 做情景模拟；用 Sentinel-2 卫星影像追踪野火并做化学计量排放估算。
> - **下午（Afternoon）**：岩石学方向 —— 偏光显微镜下观察 9 张薄片 (thin sections)，练习描述矿物光学性质、画薄片素描 (sketch)、并用「三大岩类属性表」判断岩石类型。

---

## 一、本周主题

### 上午场：Air Pollution Analysis Practical（空气污染分析实践）

上午其实是**三个串联的小模块**，共用「排放 → 数据 → 定量」这条主线：

| 模块 | 文件 | 核心技能 |
| --- | --- | --- |
| A. 数据集分析 | `Air Pollution Analysis Practical Worksheet(2).md` + `Air_Pollution_Data(5).md` | Excel 数据探索：变量识别、散点图 + 趋势线 + R²、时间序列筛选、离群值识别 |
| B. 情景模拟 | `simcity(1).md` (City Air Pollution Simulator 网页) | 参数敏感性测试：改变车流/车型比例/电力需求/能源结构，观察排放响应 |
| C. 野火排放估算 | `wildfire_sheet_answers.md` | 遥感判读 (Sentinel-2 / Copernicus Browser)、面积量测、生物量估算、配平方程式、摩尔比换算 |

**目标句（worksheet 原文 Objective）**：
> "Analyse the provided dataset to determine the main factors influencing air pollution levels in this simulated city. Use data visualisation and statistical analysis to explore trends, correlations, and outliers."
> （分析所给数据集，判断影响这座模拟城市空气污染水平的**主要因素**；用**数据可视化**与**统计分析**探究趋势、相关性与离群值。）

**野火部分 Objective 原文**：
> "You will analyse a wildfire of your choice using Sentinel-2 satellite imagery from the Copernicus Browser. Your task is to track the fire's progress, measure the burn area, estimate the proportion of different vegetation types, balance the combustion equation, and calculate CO₂ emissions."

### 下午场：EART11300 Semester 2 Microscope Practical Class 2

标题原文：**Igneous, sedimentary and metamorphic rocks under the microscope**（显微镜下的火成岩、沉积岩与变质岩）

worksheet 明确列出三条 "In this practical you will..."：
1. **practise describing optical properties of minerals**，并开始能识别几种重要的造岩矿物 (rock-forming minerals)；
2. 看**薄片尺度的结构 (textures)** 如何用来把岩石归类为 igneous / sedimentary / metamorphic；
3. **练习画薄片素描 (sketches)**。

共 **9 张薄片**。三项任务：
1. 回答每个样品中特定矿物的光学性质问题；
2. 按提示画素描（**今天的素描必须加比例尺 scale bar**）；
3. 用第 5 页的「三大岩类属性表」判定岩石类型。

> worksheet 特别说明：**前 3 个样品（Peridotite、Blueschist、Sandstone）的任务 3 已经替你做好了**，"Make sure you agree with the answers for these 3 samples before moving on to the unknown samples."（先确认你同意这 3 个已给答案的推理，再去做未知样品。）这三个是**示范样本 (worked examples)**，后 6 个是**自己判定的未知样本**。

---

## 二、核心概念

### 上午场

#### 1. 数据集里的四种污染物及其成因过程

worksheet Section 1 明确要问：「污染物有哪些？主要来源是什么？**每个来源是通过什么过程产生这些污染物的？**」——最后这一问是化学，必须答出**过程**而不只是「汽车」「电厂」。

| 污染物 | 全称 / 中文 | 主要来源 | 生成过程 (process) |
| --- | --- | --- | --- |
| **NOx** (NO + NO₂) | 氮氧化物 | 机动车尾气、燃气/燃煤电厂 | **高温燃烧**时空气中的 N₂ 与 O₂ 直接化合：N₂ + O₂ → 2NO（**thermal NOx / Zeldovich 机制**，>1300 °C 才显著）；NO 在大气中被 O₃/过氧自由基氧化为 NO₂ |
| **CO** | 一氧化碳 | 机动车（尤其冷启动、低速）、燃烧设备 | **不完全燃烧 (incomplete combustion)**：氧气供应不足时碳只氧化到 CO 而非 CO₂，例如 2C + O₂ → 2CO |
| **CO₂** | 二氧化碳 | 发电（天然气/煤）、机动车 | **完全燃烧 (complete combustion)**：CₓHᵧ + O₂ → CO₂ + H₂O，含碳燃料中的碳全部氧化 |
| **PM2.5** | 细颗粒物（空气动力学直径 ≤ 2.5 µm） | 燃烧产生的**一次颗粒物**（soot / 碳烟）、刹车与轮胎磨损、扬尘；以及 NOx/SO₂/NH₃ 在大气中反应生成的**二次颗粒物 (secondary aerosol)** | 极端不完全燃烧 → 未燃碳与凝结的半挥发性有机物形成 soot；柴油车尤其严重 |

**记忆锚点**：CO₂ = 燃烧「做对了」的产物；CO 和 PM = 燃烧「做砸了」的产物；NOx = 燃烧「太热了」的产物（跟燃料含不含氮无关，空气本身就有 N₂）。

#### 2. 相关性分析：R² 与梯度 (gradient) 的分工

worksheet Section 2 给了一段关键说明（原文）：
> "The R² value tells you how well traffic (for example) explains the variation in CO₂ emissions. A higher R² (closer to 1) means a strong correlation, while a lower R² (closer to 0) means a weak correlation. The gradient (slope) of the line tells you how much the CO₂ concentration changes per unit increase in traffic."

拆开理解——这是本周最重要的统计概念：

- **R²（决定系数, coefficient of determination）** = 自变量能**解释**因变量变化的**比例**。0 ≤ R² ≤ 1。R² = 0.99 → 99% 的变化能被这个变量解释。它回答「**关系有多紧**」。
- **梯度 / 斜率 (gradient, slope)** = 自变量每增加 1 个单位，因变量变化多少（**带单位**）。它回答「**影响有多大**」。
- **两者不可互换**：斜率大不代表相关强；R² 高也不代表斜率大。
- **关键陷阱**：不同变量的斜率**单位不同**（kg CO₂ per MWh vs kg CO₂ per vehicle·h⁻¹），**不能直接比大小**。要判断「谁是主因」，应当看 **R²**，或者把斜率乘以该变量的实际变动范围换算成「贡献量」再比。

#### 3. 混杂 (confounding) 与虚假相关

本数据集的教学核心：车流量 (Traffic) 和电力需求 (Electricity Demand) **本身彼此相关**（实测 r = 0.523，R² = 0.273），因为两者都在早晚高峰同时上升。
于是「CO₂ vs 车流量」的单变量回归会得到一个**看起来很大的斜率（124.6 kg CO₂ 每 vehicle/hour）**，但那大部分是**电力需求借道车流量表现出来的**。做多元回归剥离后，车流的**真实**系数只有 3.81 kg CO₂ 每 vehicle/hour（详见第三节）。
**结论**：相关不等于因果；两个自变量共变时，单变量斜率会被夸大。

#### 4. 时间趋势：日变化 (diurnal) 与周变化 (weekly)

- **Rush hour（通勤高峰）**：早 07:00–09:00、晚 17:00–19:00，车流量出现双峰。
- **Non-peak / overnight**：23:00–05:00，车流量降至最低。
- **Weekday vs weekend**：工作日车流高、周末车流低；但**电力需求模式可以相反**（本数据集周末电力需求反而更高）——这正是本数据集设计的「反直觉」考点。

#### 5. 湿沉降 / 冲刷 (wet deposition / washout, rainout)

降水通过两种机制清除颗粒物：
- **Rainout（云内清除, in-cloud scavenging）**：气溶胶充当凝结核被并入云滴，随降水落下。
- **Washout（云下清除, below-cloud scavenging）**：下落的雨滴在空中碰撞捕获颗粒物。

因此 **PM2.5 与降水量呈负相关**，而气体污染物（CO₂、CO、NOx）受降水影响小得多（CO₂ 微溶、化学惰性；NOx 溶解度中等）。本数据集正是这样设计的：**只有 PM2.5 被雨「洗掉」，其余三种污染物完全不受降水影响**。

#### 6. 离群值 (outliers) 与异常 (anomalies)

- **Outlier** 的操作定义（本课可用的两种）：
  - **统计定义**：偏离均值 > 2 或 3 个标准差 (SD)，即 |x − x̄| > 2σ；
  - **IQR 定义**：< Q1 − 1.5×IQR 或 > Q3 + 1.5×IQR。
- **两类离群值必须区分**：
  1. **真实极端事件 (genuine extreme)**：确实发生了（如高峰叠加高电力需求）；
  2. **数据错误 (error / artefact)**：传感器故障、单位错误、录入错误。
- 追问「What could have caused these anomalies?」时应给出**物理/社会机制**：交通事故堵车、电厂启停或备用机组投运、逆温层 (temperature inversion) 导致的静稳天气累积、附近工地/焚烧/野火、大型活动、寒潮供暖负荷、传感器漂移或标定错误。

#### 7. 野火遥感与燃烧化学

**(a) Sentinel-2 与 SWIR 假彩色**
- **Sentinel-2** 是欧盟 Copernicus 计划的**光学多光谱卫星**（A/B/C 星组网），空间分辨率 10–60 m，重访周期约 5 天。
- **Copernicus Browser** 是免费在线影像浏览平台，左侧面板可切换渲染方式，右侧有**多边形量测工具 (polygon measuring tool)**。
- **True colour（真彩色）**：用红/绿/蓝波段合成，像肉眼所见。缺点是**烟雾会遮挡**火场。
- **SWIR（Short-Wave Infrared，短波红外，Sentinel-2 的 B12/B11/B4 合成）**：这是追踪野火的关键。
  - SWIR **能穿透烟雾**（长波长受气溶胶散射弱）；
  - **活跃火线**在 SWIR 中呈**亮红/橙色**（高温物体在 SWIR 强辐射）；
  - **火烧迹地 (burn scar)** 呈**深棕/褐色**（植被含水量与叶绿素被破坏，SWIR 反射率升高、NIR 下降）；
  - **健康植被**呈**绿色/亮绿**。
  - 由此可以逐日/逐次过境地**追踪火势推进方向与范围**，从初次探测到熄灭。

**(b) 纤维素 (cellulose) 与燃烧**
- 木材与植物材料的主要成分是**纤维素 C₆H₁₀O₅**（严格说是聚合物 (C₆H₁₀O₅)ₙ，162 g/mol 是**重复单元**的摩尔质量）。
- **氧气充足** → **完全燃烧** → 产物只有 CO₂ + H₂O；
- **氧气受限** → **不完全燃烧** → 额外产生 **CO（一氧化碳）与 soot（烟尘颗粒）**。
- ⚠️ **worksheet 原文这里写错了**："In an oxygen-rich environment, **incomplete** combustion occurs, releasing carbon dioxide and water." 富氧环境应当是 **complete combustion（完全燃烧）**。后面接的 "If the supply of oxygen is limited, we may also produce carbon monoxide and soot particles" 才是不完全燃烧。考试作答请用正确表述。

### 下午场

#### 1. 偏光显微镜的两种观察模式

| 模式 | 英文 | 光路 | 能看的性质 |
| --- | --- | --- | --- |
| 单偏光 | **PPL** (Plane-Polarised Light) / 下偏光镜单独工作 | 只插下偏光镜 (polariser) | 颜色 (colour)、**多色性 (pleochroism)**、**突起 (relief)**、**解理 (cleavage)**、裂纹 (fractures)、蚀变 (alteration)、晶形 (crystal shape)、包裹体 (inclusions)、不透明矿物 (opaques) |
| 正交偏光 | **XPL / crossed polars** | 下偏光镜 + 上分析镜 (analyser) 互相垂直 | **干涉色 (interference colour)**、**双晶 (twinning)**、**消光 (extinction)**、**各向同性/异性 (isotropic/anisotropic)** |

关键判据：**各向同性矿物 (isotropic)** 在 XPL 下**全方位漆黑**（转台一周不变亮）。garnet（石榴石）、spinel、以及薄片胶 (glue/resin)、玻璃都是各向同性的。

#### 2. 本周必须掌握的光学性质定义

- **Relief（突起）**：矿物折射率 (RI) 与周围树脂/胶 (n ≈ 1.54) 差异越大，晶体边界看起来越突出、轮廓越黑。
  - **High relief（高突起）**：olivine（橄榄石, RI ≈ 1.65–1.88）、garnet（石榴石, RI ≈ 1.7–1.9）；
  - **Low relief（低突起）**：quartz（石英, RI ≈ 1.54–1.55，几乎与胶相同，边界很淡）、feldspar（长石, RI ≈ 1.53–1.59）。
- **Cleavage（解理）**：沿晶体结构中弱键面的规则裂开，PPL 下表现为**一组或多组平行的直线**。
  - biotite（黑云母）：**一组极完全解理 (one perfect cleavage)**，平行直线极显著；
  - olivine：**无解理**，但有**发育良好的不规则裂纹 (irregular fractures)**——这是区分「解理 vs 裂纹」的经典例子：**解理平行且规则，裂纹不规则、不平行**。
- **Pleochroism（多色性）**：**只在 PPL 下**看得到。旋转载物台时，有色的**各向异性**矿物颜色/深浅发生变化，因为不同振动方向的光被吸收程度不同。
  - 观察方法：旋转 360°，记录**最深**与**最浅**两个颜色。
  - 物理原理：**当矿物最大吸收方向平行于下偏光镜振动方向时颜色最深**。多数英国教学显微镜的下偏光镜振动方向为 **E–W（东西向）**。
  - biotite 的最大吸收方向**平行于解理**，因此：**解理转到 E–W → 深绿棕色 (dark green-brown)；解理转到 N–S → 浅棕色 (pale brown)**。（务必以自己那台镜子的实际偏光方向为准，反过来也可能。）
- **Interference colour（干涉色）**：**只在 XPL 下**看得到。由**双折射率 (birefringence, δ = n_max − n_min)** 与**薄片厚度 (标准 30 µm)** 共同决定的**光程差 (retardation, Γ = δ × t，单位 nm)** 产生。
  - 本课简化为三档：**low（低）/ intermediate（中）/ high（高）**。
  - 判断要点：**必须找该矿物在薄片中出现的最高干涉色**（不同晶体切面方向不同，只有恰当方向才显示最大双折射），所以 worksheet 问的是 "**maximum** colour"。
- **Michel-Lévy colour chart（米歇尔-列维干涉色图表）**：把 Γ（横轴）、δ（斜线）、厚度（纵轴）三者联系起来的标准查算图。
- **Twinning（双晶）**：worksheet 给了完整定义（原文要点）：
  > 有些矿物倾向于长成由两个或多个部分组成的晶体，这些部分**化学成分相同但取向不同**。只有两部分的叫 **simple twinning（简单双晶）**；单个晶体内包含许多平行「双晶单元」的叫 **multiple twinning（聚片双晶 / 多重双晶）**。
  > **双晶在正交偏光 (crossed polars) 下最容易看到**，因为各单元显示**不同的干涉色和/或不同的消光位**，但从其他光学性质看它们显然属于同一个晶体。单元之间的界面通常是平面，在薄片中表现为**直线**（前提是界面大致垂直于薄片表面）。
  - **plagioclase feldspar（斜长石）的多重双晶（"斑马条纹"）是本周最好用的识别特征。**
- **Alteration（蚀变）**：矿物被后期流体/风化改造为细粒次生矿物，PPL 下呈浑浊、斑驳、发暗。
  - **quartz 永不蚀变 (never altered)**，永远干净透明 → 这是它极好用的鉴定属性；
  - **feldspar 常强烈蚀变**（变成 XPL 下灰色或亮干涉色的絮状斑点）；
  - **olivine 常沿裂纹蚀变**（变蛇纹石/伊丁石）。
- **Pleochroic haloes（多色晕）**：biotite 中常见的**深色小圆晕**，围绕微小的 **zircon（锆石）包裹体**。成因（worksheet 原文机制）：锆石含微量放射性**铀 (uranium)**，衰变放出的 **α 辐射**破坏周围黑云母晶格，形成暗色圆晕。这是**辐射损伤 (radiation damage)** 的直接可视证据。
- **Equant（等轴状）**：晶体三个方向尺寸大致相等，因此**任意方向的二维切面都近似等轴**（对应上周讲的 "2-D sections through 3-D crystals"）。garnet 是典型。

#### 3. 三大岩类的定义与判别属性（worksheet 第 5 页原文，逐条）

**Igneous Rocks（火成岩）**
> 定义："These rocks have **crystallised from partially molten material – magma** – either within the Earth or on Earth's surface."（由部分熔融物质——岩浆——在地球内部或地表结晶而成。）

在手标本或薄片中：
1. 倾向于有**互锁晶体 (interlocking crystals)**；
2. 部分晶体有**自形晶面 (own shape / bounded by flat crystal faces)**，说明是在液体中**无阻碍生长**；
3. 矿物种类**相对少**（通常 ≤ 5 种）；
4. 每种矿物的晶体**大小/形态较均一 (quite uniform)**；
5. 可能含**化石气泡 = 气孔 (vesicles)**；除此之外**不具孔隙**；
6. 晶体**通常无优选方位**（例外：**cumulate（堆晶岩）**、**flow-aligned crystals（流动定向）**）；
7. **不含有机质或化石**。

**Sedimentary rocks（沉积岩）**
> 定义："formed by the **accumulation, as layered deposits on the Earth's surface**, of material derived by **weathering of pre-existing rocks** or material of **biological origin**."（由先存岩石风化产物或生物来源物质，在地表以层状沉积堆积而成。）

1. 常由先存岩石的**碎屑 (clasts)** 组成，可能包含**多晶岩屑 (polycrystalline rock fragments)**；
2. 碎屑可能**磨圆 (rounded)**，指示搬运过程中的**磨蚀 (abrasion)**；
3. 可能含**化石 (fossils)**；
4. 可能含**有机质**；
5. **可能相当多孔 (porous)**；
6. 常呈**层理 (bedded/layered)**，常有显著成分反差（可能只有在大尺度上——如地质图或野外——才看得到）。

**Metamorphic rocks（变质岩）**
> 定义："formed by **alteration of pre-existing igneous or sedimentary rocks, in the solid state, through the action of heat and/or pressure**."（由先存火成岩或沉积岩在**固态**下经热和/或压力作用改造而成。）注意 "solid state" 是划重点的部分——没有熔融。

1. 可能保留**成分层理 (compositional layering, "fossil bedding")**，但可能已被**变形（褶皱等）**；
2. 矿物种类**相对少**（通常 ≤ 6 种），每种矿物晶体较均一；
3. 晶体常有**优选方位 (preferred orientation)**，即变形产生的**构造组构 (tectonic fabric)**；若为面状组构即**片理 (foliation)**，且可能与原有层理**斜交 (discordant)**；
4. 部分晶体有自形，其余为固态下**竞争生长 (competitive growth)** 的形态（类比：**泡沫中的气泡**）；
5. **无显著孔隙**；
6. **化石通常不能保存**。

> **三条最快的判别口诀**：
> - 看到**磨圆的碎屑 / 多晶岩屑 / 胶结物 (cement) / 化石 / 孔隙** → **沉积岩**
> - 看到**片理 / 晶体优选定向 / 成分条带** → **变质岩**
> - 看到**互锁晶体 + 随机取向 + 自形晶 + 气孔** → **火成岩**

#### 4. 本周涉及的造岩矿物光学速查

| 矿物 | PPL 颜色 | 突起 | 解理/裂纹 | 干涉色 | 双晶 | 蚀变 | 出现于 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Olivine（橄榄石）** | 无色 | **高** | **无解理（或很弱）**，有发育好的**不规则裂纹** | **中等 (intermediate，2 级)** | 无 | **常沿裂纹蚀变** | RP/R56, CP, RE114 |
| **Quartz（石英）** | 无色，**极干净** | **低** | **无** | **低（1 级灰白）** | **无**（也无环带 zoning） | **永不蚀变** | R25/SK, CG, S10 |
| **Feldspar（长石，此处指斜长石 plagioclase）** | 无色 | **低** | 有（不总明显） | **低** | **有，多重双晶** | **常强烈蚀变** | NH, CP, CG |
| **Calcite（方解石）** | 无色 | 变化剧烈（"闪突起"） | 菱面体解理 | **高**（"sandy"沙色，带绿粉色调） | — | — | R25/SK（作为**胶结物 cement**） |
| **Biotite（黑云母）** | **棕色 / 红棕 / 绿棕**，**强多色性** | 中—高（随方向变） | **一组极完全解理** | 高（但常被自身体色掩盖） | — | — | SB2, CG（及上周 15216） |
| **Garnet（石榴石）** | 无色或**极淡粉色** | **高** | 无 | **各向同性 (isotropic)——XPL 下全黑** | — | — | A/986 blueschist |
| **蓝色角闪石**（glaucophane 类；worksheet 明说**不要求识别**） | **淡蓝 / 紫红 (mauve) 多色性**，部分晶体近无色 | 中 | 角闪石式解理 | — | — | — | A/986 blueschist |

> **重要提示（答案文件原文）**："**Calcite (and its fellow carbonate mineral, dolomite) is the only common mineral you will see with high interference colour.**" —— 看到高干涉色（沙色/珠光色）基本可以直接锁定**碳酸盐矿物**。

---

## 三、公式与图表

### 3.1 数据集结构：`Air_Pollution_Data(5).xlsx` / `.md`

**基本规格**
- 单一工作表 `Sheet1`，**168 行数据 + 1 行表头**；
- 时间跨度：**2024-10-31 00:00 → 2024-11-06 23:00**，**逐小时 (hourly)**，共 **7 天 × 24 小时 = 168 条**；
- **12 列变量**；数值以完整浮点精度存储（未四舍五入）。

**变量清单（表头原文照抄，含单位）**

| # | 列名（原文） | 中文 | 类型 | 实测范围 (min – max) | 均值 |
| --- | --- | --- | --- | --- | --- |
| 1 | `Time of Day` | 时间戳（日期+小时） | 时间 | 2024-10-31 00:00 – 2024-11-06 23:00 | — |
| 2 | `Day` | 星期 | 类别 | Monday – Sunday，各 24 行 | — |
| 3 | `Traffic Volume (vehicles/hour)` | 车流量 | 自变量 | 50 – 2408 | 665.6 |
| 4 | `Electricity Demand (MWh)` | 电力需求 | 自变量 | 100.6 – 1192.9 | 474.7 |
| 5 | `Temperature (°C)` | 气温 | 气象 | 10 – 22 | 13.80 |
| 6 | `Wind Speed (m/s)` | 风速 | 气象 | 2.00 – 11.86 | 4.83 |
| 7 | `Humidity (%)` | 相对湿度 | 气象 | 20.1 – 77.2 | 48.9 |
| 8 | `Precipitation (mm)` | 降水量 | 气象 | 0 – 19.95（168 行中 48 行 > 0） | 2.30 |
| 9 | `NOx (kg/hour)` | 氮氧化物排放率 | 因变量 | 51.2 – 601.0 | 239.9 |
| 10 | `CO (kg/hour)` | 一氧化碳排放率 | 因变量 | 27.6 – 531.3 | 134.6 |
| 11 | `CO2 (kg/hour)` | 二氧化碳排放率 | 因变量 | 52 445 – 615 623 | 244 643 |
| 12 | `PM2.5 (kg/hour)` | 细颗粒物排放率 | 因变量 | 1.96 – 50.21 | 17.34 |

> **注意单位**：四种污染物给的是**排放率 (kg/hour)**，**不是浓度 (µg/m³)**。worksheet 里说 "CO₂ concentration" 是措辞不严谨；作答时应说 **emission rate（排放率）**。要转成浓度还需要城市体积/混合层高度与通风速率，本练习没有给。

**两个隐含的确定性结构（自行推导，非讲义给出，但对读懂数据极有帮助）**

- **气温是固定的日变化正弦曲线，每天完全相同、无噪声**（只有 7 个不同取值）：
  $$T(h)=\begin{cases}10+12\sin\!\left(\dfrac{2\pi (h-5)}{24}\right) & 5 \le h \le 17\\[4pt] 10\ ^\circ\mathrm{C} & \text{其他小时}\end{cases}$$
  | 小时 | 00–05 | 06 | 07 | 08 | 09 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17–23 |
  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
  | T (°C) | 10 | 13.11 | 16 | 18.49 | 20.39 | 21.59 | **22** | 21.59 | 20.39 | 18.49 | 16 | 13.11 | 10 |
- **风速有 2 m/s 的下限（floor）**（168 行中有 44 行恰好等于 2.00），且白天大、夜间小，与气温同相。

### 3.2 ⭐ 数据集的生成公式（逆向推导，精确到浮点误差 < 1e-10）

这是读懂整份数据的钥匙。四种污染物都是**两个源的线性叠加**：

$$\boxed{\;E_{\text{pollutant}} \;=\; a\cdot D_{\text{elec}}\;+\;b\cdot V_{\text{traffic}}\;}$$

其中 $D_{\text{elec}}$ 为电力需求 (MWh)，$V_{\text{traffic}}$ 为车流量 (vehicles/hour)。

| 污染物 | a（电力系数，per MWh） | b（交通系数，per vehicle·h⁻¹） | 均值下电力贡献占比 | 均值下交通贡献占比 |
| --- | --- | --- | --- | --- |
| **NOx (kg/h)** | **0.5** | **0.0024** | 99.3 % | 0.7 % |
| **CO (kg/h)** | **0.25** | **0.015** | 92.2 % | **7.8 %** |
| **CO₂ (kg/h)** | **510** | **3.81** | 99.0 % | 1.0 % |
| **PM2.5 (kg/h)** | **0.04** | **0.00015** | 99.5 % | 0.5 % |

**验算（第 1 行数据：Elec = 176.4050 MWh，Traffic = 129 veh/h）**
- NOx = 0.5 × 176.4050 + 0.0024 × 129 = 88.2025 + 0.3096 = **88.5121** ✓（表中 88.51209）
- CO = 0.25 × 176.4050 + 0.015 × 129 = 44.1012 + 1.9350 = **46.0362** ✓（表中 46.03625）
- CO₂ = 510 × 176.4050 + 3.81 × 129 = 89 966.54 + 491.49 = **90 458.03** ✓（表中 90 458.03）
- PM2.5 = 0.04 × 176.4050 + 0.00015 × 129 = 7.05620 + 0.01935 = **7.07555** ✓（表中 7.07555）

**PM2.5 的额外一项：降水冲刷因子 (washout factor)**
$$\text{PM2.5} = \left(0.04\,D_{\text{elec}} + 0.00015\,V_{\text{traffic}}\right)\times f_{\text{rain}}$$

| 降水情形 | 降水量范围 | 冲刷因子 $f_{\text{rain}}$（实测） |
| --- | --- | --- |
| 无雨 | 0 mm | **1.00** |
| 小雨（Wednesday） | 1.02 – 1.96 mm | **0.81 – 0.90**（均值 0.84） |
| 大雨（Friday） | 10.1 – 19.9 mm | **0.31 – 0.49**（均值 0.41） |

**其他三种污染物完全不受降水影响**（f = 1.00 恒成立）。这就是「只有 PM2.5 与降水相关」的数据来源。

### 3.3 相关性结果表（168 行全样本，Pearson）

**污染物 vs 各自变量的 R²**（这张表就是 Section 2 的标准答案）

| 自变量 | NOx | CO | CO₂ | PM2.5 |
| --- | --- | --- | --- | --- |
| **Electricity Demand** | **R² = 0.9982** | **R² = 0.8288** | **R² = 0.9998** | **R² = 0.8484** |
| **Traffic Volume** | R² = 0.2726 | R² = 0.2259 | R² = 0.2856 | R² = 0.1954 |
| Temperature | 0.0059 | 0.0021 | 0.0072 | 0.0054 |
| Wind Speed | 0.0000 | 0.0001 | 0.0001 | 0.0001 |
| Humidity | 0.0008 | 0.0000 | 0.0009 | 0.0000 |
| **Precipitation** | 0.0067 | 0.0085 | 0.0063 | **0.1422 (r = −0.377，唯一显著的负相关)** |

**单变量最佳拟合直线（含斜率与截距）**

| 关系 | 拟合方程 | R² |
| --- | --- | --- |
| CO₂ vs Electricity | CO₂ = **514.42 × Elec + 445.19** (kg/h) | **0.9998** |
| CO₂ vs Traffic | CO₂ = **124.63 × Traffic + 161 689** (kg/h) | 0.2856 |
| NOx vs Electricity | NOx = 0.5067 × Elec − 0.64 | 0.9982 |
| PM2.5 vs Electricity | PM2.5 = 0.0380 × Elec − 0.67 | 0.8484 |
| PM2.5 vs Precipitation | PM2.5 = **−0.825 × Precip + 19.24** | 0.1422 |

**混杂检验**：corr(Traffic, Electricity) = **0.523**（R² = 0.273）。因为两者共变，CO₂-vs-Traffic 的斜率被夸大到 124.63，而多元回归给出的真实交通系数只有 **3.79–3.81**（约夸大 33 倍）。

**多元回归（同时放入两个自变量）**

| 因变量 | 模型 | R² |
| --- | --- | --- |
| CO₂ | = 510.0 × Elec + 3.79 × Traffic − 4.0 | **1.0000** |
| NOx | = 0.5067 × Elec − 0.000014 × Traffic − 0.64 | 0.9982 |
| PM2.5 | = 0.0391 × Elec − 0.00101 × Traffic − 0.55 | 0.8506 |
| PM2.5（加入降水） | = 0.0377 × Elec − 0.00067 × Traffic − **0.665 × Precip** + 1.41 | **0.9419** |

（NOx/PM2.5 的交通项在单纯的两变量多元回归中被电力项吸收，是因为电力与污染物近乎完全共线；只有 CO₂ 与 CO 的交通份额足够大到被分离出来。）

### 3.4 时间趋势表

**逐小时均值（7 天平均）**

| 小时 | 车流量 | 电力 (MWh) | CO₂ (kg/h) | NOx (kg/h) | PM2.5 (kg/h) |
| --- | --- | --- | --- | --- | --- |
| 00 | 217 | 235 | 120 875 | 118.2 | 8.6 |
| 01 | 115 | 288 | 147 093 | 144.1 | 10.8 |
| 02 | 99 | 331 | 168 969 | 165.5 | 11.4 |
| 03 | 113 | 248 | 127 020 | 124.4 | 9.4 |
| 04 | 98 | 275 | 140 670 | 137.8 | 10.1 |
| 05 | 501 | 312 | 160 820 | 157.0 | 11.2 |
| 06 | 399 | 691 | 354 062 | 346.6 | 24.8 |
| **07** | **1441** | 715 | 370 043 | 360.9 | 25.5 |
| **08** | **1596** | **843** | **435 892** | **425.2** | **30.0** |
| 09 | 787 | 470 | 242 534 | 236.7 | 17.4 |
| 10 | 684 | 413 | 213 040 | 207.9 | 15.7 |
| 11 | 855 | 463 | 239 185 | 233.4 | 17.1 |
| 12 | 1025 | 561 | 290 222 | 283.2 | 20.6 |
| 13 | 1297 | 501 | 260 679 | 253.8 | 17.9 |
| 14 | 756 | 328 | 170 118 | 165.8 | 12.6 |
| 15 | 458 | 249 | 128 811 | 125.7 | 9.4 |
| 16 | 736 | 293 | 152 427 | 148.5 | 10.5 |
| **17** | **1404** | 371 | 194 372 | 188.7 | 13.2 |
| **18** | **1603** | **995** | **513 443** | **506.9** | **36.9** |
| 19 | 379 | 805 | 411 827 | 408.9 | 29.6 |
| 20 | 404 | 790 | 404 506 | 401.7 | 29.7 |
| 21 | 343 | 479 | 245 393 | 245.8 | 17.5 |
| 22 | 527 | 475 | 244 391 | 238.9 | 16.3 |
| 23 | 139 | 264 | 135 052 | 132.2 | 10.1 |

**高峰 vs 非高峰**

| 时段 | 车流量均值 | CO₂ 均值 (kg/h) | NOx 均值 (kg/h) |
| --- | --- | --- | --- |
| Rush hour（07–09, 17–19） | **1202** | **361 352** | **355** |
| Overnight（23–04） | 130 | 139 947 | 137 |
| **倍数** | **9.2 ×** | **2.6 ×** | **2.6 ×** |

> **关键判读**：车流量高峰是夜间的 **9.2 倍**，但 CO₂ 只有 **2.6 倍**——再次证明**污染主要由电力需求驱动，交通只是附带**。

**逐日均值**

| 星期 | 车流量 | 电力 (MWh) | CO₂ (kg/h) | PM2.5 (kg/h) | 降水均值 (mm) | PM2.5/电力比 |
| --- | --- | --- | --- | --- | --- | --- |
| Monday | 688 | 441 | 227 577 | 17.75 | 0 | 0.0403 |
| Tuesday | 604 | 440 | 226 954 | 17.71 | 0 | 0.0402 |
| **Wednesday** | 707 | 458 | 236 196 | **15.64** | **1.43（小雨）** | **0.0339 ↓** |
| Thursday | 744 | 445 | 229 830 | 17.92 | 0 | 0.0403 |
| **Friday** | 676 | 431 | 222 287 | **6.96** | **14.70（大雨）** | **0.0164 ↓↓** |
| **Saturday** | 637 | **549** | **282 654** | 23.00 | 0 | 0.0416 |
| **Sunday** | 603 | **558** | **287 007** | 22.42 | 0 | 0.0402 |

**工作日 vs 周末汇总**

| | 车流量 | 电力 (MWh) | CO₂ (kg/h) | PM2.5 (kg/h) |
| --- | --- | --- | --- | --- |
| Weekday (Mon–Fri) | **684** | 443 | 228 569 | 15.20 |
| Weekend (Sat–Sun) | 620 | **554 (+25 %)** | **284 831 (+25 %)** | **22.71** |

**周总排放量**：CO₂ ≈ **41 100 吨/周**；NOx ≈ **40 304 kg/周**；PM2.5 ≈ **2 914 kg/周**。

### 3.5 离群值清单

**电力需求 > 均值 + 2 SD（阈值 1029 MWh），共 5 个：**

| 时间戳 | 星期 | 电力 (MWh) | 车流量 | CO₂ (kg/h) | PM2.5 (kg/h) |
| --- | --- | --- | --- | --- | --- |
| 2024-10-31 08:00 | Monday | **1193（全周最高）** | 1906 | **615 623（全周最高）** | 48.0 |
| 2024-11-03 18:00 | Thursday | 1147 | 2180 | 593 374 | 46.2 |
| **2024-11-05 20:00** | **Saturday** | **1115** | **仅 178（极低）** | 569 384 | **50.21（全周最高）** |
| 2024-11-01 08:00 | Tuesday | 1063 | 2072 | 549 939 | 42.8 |
| 2024-11-02 18:00 | Wednesday | 1032 | **2408（全周最高）** | 535 573 | 37.3 |

> **诊断性最强的一条**：**2024-11-05 20:00（周六晚 8 点）**——车流量只有 178（全周极低区间），电力需求却高达 1115 MWh，产生了**全周最高的 PM2.5 (50.21 kg/h)**。这个「低车流 + 高污染」的组合，是证明「交通不是主因」的**决定性证据 (smoking gun)**。

### 3.6 野火排放计算的完整公式链

**Step 0：面积单位换算**
$$1\ \mathrm{km^2} = 247.1\ \mathrm{acres}\quad\Rightarrow\quad 100\ \mathrm{km^2} = 24{,}710\ \mathrm{acres}$$
（更精确值 1 km² = 247.105 acres；讲义用 247.1）

**Step 1：分植被类型算生物量与纤维素量**

| 参数 | Forest（森林） | Grassland（草地） |
| --- | --- | --- |
| 占火烧面积比例 | **60 %** | **40 %** |
| **生物量密度 (biomass)** | **75 tonnes/acre** | **10 tonnes/acre** |
| **纤维素含量 (cellulose content)** | **50 % of biomass** | **30 % of biomass** |

$$m_{\text{cellulose}} = A_{\text{total,acres}} \times f_{\text{veg}} \times \rho_{\text{biomass}} \times c_{\text{cellulose}}$$

- **Forest**：24 710 × 0.6 = **14 826 acres** → × 75 = **1 111 950 t 生物量** → × 0.5 = **555 975 t 纤维素**
- **Grassland**：24 710 × 0.4 = **9 884 acres** → × 10 = **98 840 t 生物量** → × 0.3 = **29 652 t 纤维素**
- **合计纤维素 = 555 975 + 29 652 = 585 627 tonnes**

**Step 2：配平燃烧方程式**

未配平：C₆H₁₀O₅ + O₂ → CO₂ + H₂O

$$\boxed{\ \mathrm{C_6H_{10}O_5} + 6\,\mathrm{O_2} \;\rightarrow\; 6\,\mathrm{CO_2} + 5\,\mathrm{H_2O}\ }$$

原子核对表（讲义原文给出）：

| 左侧 | 元素 | 右侧 |
| --- | --- | --- |
| 6 | **C** | 6 |
| 10 | **H** | 10 |
| **17**（5 来自纤维素 + 12 来自 6O₂） | **O** | **17**（12 来自 6CO₂ + 5 来自 5H₂O） |

配平方法（**先 C，再 H，最后 O**）：C 定 CO₂ 系数为 6；H 定 H₂O 系数为 5（10 H ÷ 2）；右侧总 O = 6×2 + 5×1 = 17，左侧纤维素自带 5 个 O，需再补 12 个 O = **6 个 O₂**。

**Step 3：摩尔质量与质量比**

| 物种 | 计算 | 摩尔质量 |
| --- | --- | --- |
| **纤维素 C₆H₁₀O₅** | 6×12 + 10×1 + 5×16 = 72 + 10 + 80 | **162 g/mol** |
| **CO₂** | 12 + 2×16 | **44 g/mol** |
| **6 CO₂** | 44 × 6 | **264 g** |
| **H₂O** | 2×1 + 16 | **18 g/mol** |
| **5 H₂O** | 18 × 5 | **90 g** |
| O₂ | 2×16 | 32 g/mol |

**质量转换因子**：
$$\frac{m_{\mathrm{CO_2}}}{m_{\text{cellulose}}} = \frac{6 \times 44}{162} = \frac{264}{162} = \mathbf{1.6296}\ (\text{讲义取 } 1.63)$$
$$\frac{m_{\mathrm{H_2O}}}{m_{\text{cellulose}}} = \frac{5 \times 18}{162} = \frac{90}{162} = \mathbf{0.5556}\ (\text{讲义写 } 0.56)$$

**Step 4：最终排放量**

$$m_{\mathrm{CO_2}} = 585{,}627 \times 1.63 = \mathbf{954{,}572\ tonnes\ CO_2}\quad(\text{讲义答案})$$
$$m_{\mathrm{H_2O}} = 585{,}627 \times \tfrac{90}{162} = \mathbf{325{,}348\ tonnes\ H_2O}\quad(\text{讲义答案})$$

> **精确值对照（供检查用）**：若 CO₂ 也用未取整的 264/162 = 1.62963，则 m = **954 355 t**，比讲义的 954 572 t 少 217 t。讲义在 CO₂ 上用了四舍五入的 1.63，在 H₂O 上却用了未取整的 0.5556（因为 585 627 × 0.56 = 327 951 ≠ 325 348）——**两处取舍标准不一致**，这是讲义的小瑕疵。
>
> **碳质量平衡独立验算**：585 627 t 纤维素中的碳 = 585 627 × 72/162 = **260 279 t C**；全部转为 CO₂：260 279 × 44/12 = **954 355 t CO₂** ✓ 与精确值一致。
>
> **单位面积排放强度**：954 355 ÷ 100 km² ≈ **9 544 t CO₂ per km²**。

### 3.7 浓度单位换算与空气质量标准限值（背景补充）

> ⚠️ 本节的换算公式与限值表**不是本周材料给出的**（本周数据用的是 kg/hour 排放率），但秋季学期同名课程 Week 4 做过实测空气质量、且这是本领域必须掌握的基本功，因此在此补齐。

**(a) 体积混合比 ↔ 质量浓度**

$$C\ (\mu\mathrm{g/m^3}) = C\ (\mathrm{ppb}) \times \frac{M\ (\mathrm{g/mol})}{V_m\ (\mathrm{L/mol})}\qquad\text{其中}\quad V_m = \frac{RT}{P}$$

- 0 °C, 1 atm（STP）：$V_m$ = **22.41 L/mol**
- 20 °C, 1013 hPa：$V_m$ = **24.06 L/mol**
- 25 °C, 1013 hPa（大气化学常用）：$V_m$ = **24.45 L/mol**

反向换算：$C\ (\mathrm{ppb}) = C\ (\mu\mathrm{g/m^3}) \times \dfrac{V_m}{M}$

**常用换算系数（25 °C, 1 atm）**

| 气体 | M (g/mol) | 1 ppb = ? µg/m³ | 1 µg/m³ = ? ppb |
| --- | --- | --- | --- |
| **NO₂** | 46 | **1.88** | 0.532 |
| **NO** | 30 | 1.23 | 0.815 |
| **O₃** | 48 | **1.96** | 0.510 |
| **SO₂** | 64 | **2.62** | 0.382 |
| **CO** | 28 | 1.145（注意 CO 通常用 **ppm ↔ mg/m³**） | 0.873 |
| CO₂ | 44 | 1.80 | 0.556 |

> **PM2.5 / PM10 没有 ppb 换算**——它们是颗粒物，本身就以质量浓度 (µg/m³) 计量。

**(b) 排放率 → 浓度（若给通风条件）**
$$C = \frac{E}{Q} = \frac{E\ (\mathrm{kg/h})}{u \times W \times H}$$
其中 $u$ 为风速 (m/s)、$W$ 为城市迎风宽度 (m)、$H$ 为混合层高度 (m)，$Q$ 为通风量 (m³/h)。这就是为什么**静风 + 低混合层（逆温）会让同样的排放产生高得多的浓度**。

**(c) 标准限值表（背景参考）**

| 污染物 | **UK / EU 法定限值**（Air Quality Standards Regulations 2010） | **WHO 2021 空气质量指南 (AQG)** |
| --- | --- | --- |
| **PM2.5** | 年均 **20 µg/m³**（英格兰 2040 年目标 10 µg/m³） | 年均 **5**；24 h 均 **15** |
| **PM10** | 年均 **40**；24 h 均 **50**（每年 ≤ 35 次超标） | 年均 **15**；24 h 均 **45** |
| **NO₂** | 年均 **40**；1 h 均 **200**（每年 ≤ 18 次超标） | 年均 **10**；24 h 均 **25** |
| **SO₂** | 15 min 均 **266**；1 h 均 **350**（≤ 24 次）；24 h 均 **125**（≤ 3 次） | 24 h 均 **40** |
| **O₃** | 日最大 8 h 滑动均 **120**（每年 ≤ 25 天，三年平均） | 8 h 均 **100**；高峰季 **60** |
| **CO** | 日最大 8 h 滑动均 **10 mg/m³** | 24 h 均 **4 mg/m³** |

（单位若未标注均为 µg/m³。）

### 3.8 Michel-Lévy 干涉色分级速查

$$\Gamma\ (\mathrm{nm}) = t\ (\mathrm{nm}) \times \delta \qquad \delta = n_{\max} - n_{\min},\quad t_{\text{标准薄片}} = 30\ \mu\mathrm{m} = 30{,}000\ \mathrm{nm}$$

| 级次 (order) | 光程差 Γ (nm) | 颜色 | 本课分档 | 典型矿物 |
| --- | --- | --- | --- | --- |
| **1 级** | 0 – 550 | 灰 → 白 → 黄 → 橙 → 红（1 级红为"敏感紫红" ~550 nm） | **Low（低）** | **quartz、feldspar** |
| **2 级** | 550 – 1100 | 蓝 → 绿 → 黄 → 橙 → 红（颜色鲜艳） | **Intermediate（中）** | **olivine、pyroxene** |
| **3 级** | 1100 – 1650 | 颜色渐淡、鲜艳度下降 | Intermediate–High | — |
| **4 级以上 (high order)** | > 1650 | **珠光白 / 沙色 (sandy)，带绿粉色调** | **High（高）** | **calcite、dolomite、white mica** |
| — | — | XPL 下**恒黑** | **Isotropic（各向同性）** | **garnet**、玻璃、薄片胶 |

> 答案文件对 CP 样品的判断口诀原文：**"if it is pink or higher, and very bright, then it is intermediate"**（如果是粉色或更高、而且非常鲜艳，那就是 intermediate）。

### 3.9 建议的可视化方式（Section 2–4 要交的图）

| 目的 | 图型 | 做法 |
| --- | --- | --- |
| 相关性 | **散点图 (scatter / XY chart) + 线性趋势线** | Excel：选两列 → Insert → Scatter → 右键数据点 → **Add Trendline** → 勾选 **Display Equation on chart** 和 **Display R-squared value on chart** |
| 时间趋势 | **折线图 (line chart)**，x 轴为 `Time of Day` | 讲义提示：表头旁的**下拉菜单 (drop-down menu / AutoFilter)** 可按日期或时间筛选数据 |
| 日变化对比 | **按小时分组的柱状图 / 多线叠加图** | 用 `AVERAGEIFS` 或数据透视表 (PivotTable) 按小时聚合 |
| 工作日 vs 周末 | **分组柱状图 / 箱线图 (box plot)** | 按 `Day` 列分组 |
| 离群值 | **箱线图**，或在时间序列上标注 ±2 SD 参考线 | 用 `AVERAGE` 与 `STDEV.S` 算阈值 |

---

## 四、课堂补充

### 4.1 City Air Pollution Simulator（`simcity(1).html`）—— 网页模拟器的设定

页面标题：**City Air Pollution Simulator**
说明文字：**"Adjust the parameters below to see how they affect air pollution emissions."**（调整下列参数，观察它们如何影响污染排放。）

**模拟器的排放因子来源（页面明确声明）**：
- **"Car emissions are based on Euro 6 petrol and diesel regulations and the CO₂ emissions are derived from a new Ford Focus."**（汽车排放基于 **Euro 6** 汽油/柴油法规；CO₂ 排放取自一辆新款 **Ford Focus**。）
- **"Electricity emissions are based on natural gas turbine power plants as reported by the UK Gov website."**（电力排放基于 **UK 政府网站**公布的**天然气涡轮发电厂**数据。）

**可调参数与默认值（页面默认状态）**

| 参数 | 英文原名 | 默认值 |
| --- | --- | --- |
| 车流量 | Traffic Volume (vehicles/hour) | **300** |
| 柴油车比例 | Diesel Vehicle Proportion | **30 %** |
| 汽油车比例 | Petrol Vehicle Proportion | **50 %** |
| 电动车比例 | Electric Vehicle Proportion | **20 %** |
| 电力需求 | Electricity Demand (MW) | **800** |
| 可再生能源占比 | Renewable Energy Share (%) | **20 %** |
| 电力来源（下拉选项） | Electricity Source | **Natural Gas** / Coal / Nuclear / Biofuel |
| 平均车速 | Average Car Speed (km/h) | **20** |

> **三条重要约束**：
> 1. 柴油 + 汽油 + 电动 = 30 + 50 + 20 = **100 %**，调整时必须保持总和为 100 %，否则模型无意义。
> 2. **单位不一致**：模拟器写 **MW（功率）**，数据集写 **MWh（电量）**。逐小时数据下 1 MW × 1 h = 1 MWh，数值等价，但严格来说标注是混用的。
> 3. **Average Car Speed 默认只有 20 km/h**——这是城市拥堵速度。**低速会显著抬高单位里程排放**（发动机效率低、怠速/走停工况多），所以「提高车速反而能减排」是这个模拟器会展示的反直觉结论之一（但只在低速段成立）。

**背景参考：Euro 6 排放限值（模拟器的数值依据，非页面直接给出）**

| 污染物 | Euro 6 汽油车 (petrol) | Euro 6 柴油车 (diesel) |
| --- | --- | --- |
| **NOx** | **60 mg/km** | **80 mg/km** |
| **CO** | **1000 mg/km** | **500 mg/km** |
| **PM（质量）** | 4.5 mg/km（仅缸内直喷 GDI） | **4.5 mg/km** |
| THC | 100 mg/km | — |
| HC + NOx | — | 170 mg/km |

**要点对比**：柴油车 **NOx 限值更宽松（80 > 60）、CO 限值更严（500 < 1000）**；柴油发动机 CO₂ 效率更高但 NOx 和 PM 更差——这就是「柴油门」和城市 NO₂ 超标的根源。新款 Ford Focus 的 CO₂ 约 **120–130 g/km (WLTP)**。

**背景参考：发电碳强度**

| 电源 | 典型 CO₂ 排放因子 |
| --- | --- |
| **Coal（煤）** | ~0.9 – 1.0 kg CO₂/kWh |
| **Natural Gas / CCGT（天然气联合循环）** | ~0.35 – 0.40 kg CO₂/kWh |
| **Biofuel（生物燃料）** | 燃烧时排放高，但按「生物成因碳循环」常计为接近碳中性 |
| **Nuclear（核能）** | 运行阶段 ≈ **0**（仅全生命周期有少量） |
| 本数据集隐含值 | **510 kg CO₂/MWh = 0.51 kg/kWh**（介于天然气与煤之间，偏向老式/开式循环燃气机组） |

### 4.2 Copernicus Browser 操作提示（wildfire 部分讲义原文要点）

1. **Access the Copernicus Browser**：打开浏览器，用提供的链接定位野火位置。
2. **左侧面板 (panel on the left)**：在 **true SWIR (infrared wavelengths)** 与 **true colour** 之间切换渲染方式。
3. **Identify the Fire's Progression**：用 Sentinel-2 影像**从首次探测追踪到火灾扑灭**（拖动时间轴逐次过境对比）。
4. **Measure the Burn Area**：用**页面右侧的多边形量测工具 (polygon measuring tool)** 沿火烧迹地边界勾画，读取面积。
5. **Estimate Vegetation Composition**：估算火烧区中森林/草地各占多大比例——讲义给了两条可行做法：**(a) 用卫星影像中植被的颜色判断**；**(b) 上网搜索该区域的图片/植被资料**。

### 4.3 显微镜实践的器材与操作补充

- **薄片 (thin section)**：标准厚度 **30 µm**（这是干涉色判读的前提，厚度变了颜色级次就会变）。
- **9 张薄片编号**：RP 或 R56、A/986、R25 或 SK、SB2、NH、CP、CG、S10、RE114。
- ⭐ **比例尺 (scale bar) 的做法**——worksheet 加了星号特别说明：
  > "When you draw sketches today, you should add a scale bar. To do this, you will need to **measure the width of the field of view**. We will do this together at the start of the practical."
  > （今天画素描必须加比例尺。为此需要**测量视场宽度 (field of view, FOV)**，课程开始时会一起做。）

  **具体做法**：
  1. 把**载物台测微尺 (stage micrometer)** 放上载物台（典型规格：1 mm 分成 100 格，每格 0.01 mm = 10 µm）；
  2. 在**目标物镜倍数下**，数出视场直径横跨多少格；
  3. **FOV 宽度 (mm) = 格数 × 0.01 mm**；
  4. 换物镜要**重新测量**（FOV 与物镜倍数成反比）；
  5. 也可用公式估算：**FOV = 目镜视场数 (Field Number, FN) ÷ 物镜倍数**。例：FN 20 的目镜 + ×10 物镜 → FOV = 20/10 = **2 mm**；+ ×4 物镜 → 5 mm；+ ×40 物镜 → 0.5 mm。
  6. **画比例尺**：若素描圆圈直径画成 100 mm、代表 2 mm 的实际视场，放大倍数 = 50×，则纸上 25 mm 长的线段 = **0.5 mm** 实际长度。
- **答案文件中出现的比例尺标注**（说明该画多大）：
  - Peridotite (RP/R56) 素描图标注 **"1 mm"**；
  - Blueschist (A/986) 的 garnet 标注 **"Variable size ~0.1–0.5 mm"**。
- **答案文件对 peridotite 素描的批注**：**"Note these crystals are not as parallel sided as they could be!"**（这些晶体的两侧并没有你以为的那么平行）——提醒画自形晶时不要理想化，要照实画。

### 4.4 上下文衔接

- 下午的 practical 多处提到 **"you looked at ... last week"**：R56（上周看过）、NH 中的绿色矿物（上周看过）、15216 中的 biotite（上周看过）、以及「上周讲义第 6 页的 2-D sections through 3-D crystals」。本周是 **Microscope Practical Class 2**，是 Class 1（显微镜基础与光学性质入门）的续篇。
- 三大岩类的属性表 worksheet 明说 **"essentially the same as you used for hand specimens last semester"**（与上学期手标本用的那套基本一致），对应 Michaelmas Term Week 9 的 "Rocks in hand specimen"。**技能迁移点：同一套判据，从手标本尺度搬到薄片尺度。**
- 上午的空气污染主题承接 Michaelmas Term Week 4 的 "Measuring Air Quality"（实测 + 带评估的作业）；本学期从**实测**转向**数据分析与建模**。

---

## 五、Practical 要点

### 【上午场 A】数据集分析 — `Air Pollution Analysis Practical Worksheet(2)` 逐题

> **目的**：判断影响这座模拟城市空气污染水平的主要因素。
> **方法**：Excel 数据可视化 + 统计分析（散点图 + 趋势线 + R²、时间序列筛选、离群值识别）。
> **产出**：四个 Section 的书面回答 + 相应图表。

#### 操作步骤（通用流程）

1. 打开 `Air_Pollution_Data(5).xlsx`，确认 **168 行 × 12 列**、检查有无缺失值/异常单位。
2. 给数据区加 **AutoFilter（表头旁的下拉菜单）**——讲义明确提到用它按日期或时间筛选。
3. 建议**新增两个辅助列**：`=HOUR(A2)` 提取小时、`=WEEKDAY(A2)` 或直接用 `Day` 列，便于按小时/按星期聚合。
4. 用 **PivotTable（数据透视表）** 或 `AVERAGEIFS` 做逐小时、逐日均值。
5. 作散点图 → 加趋势线 → 勾选显示方程与 R²。
6. 用 `AVERAGE` + `STDEV.S` 算 ±2 SD 阈值，用条件格式高亮离群值。

#### Section 1：Understanding the Dataset（理解数据集）

**Q1. What are the variables in the data set?（数据集里有哪些变量？）**
共 12 个，应分三类作答：
- **时间标识 (identifiers)**：`Time of Day`（逐小时时间戳）、`Day`（星期）；
- **人类活动 / 排放驱动变量 (activity / driver variables，即自变量)**：`Traffic Volume (vehicles/hour)`、`Electricity Demand (MWh)`；
- **气象变量 (meteorological variables)**：`Temperature (°C)`、`Wind Speed (m/s)`、`Humidity (%)`、`Precipitation (mm)`；
- **排放变量 (emissions，即因变量)**：`NOx`、`CO`、`CO₂`、`PM2.5`，**均为 kg/hour**。

**Q2. Which pollutants are included in the dataset?（包含哪些污染物？）**
四种：**NOx（氮氧化物）、CO（一氧化碳）、CO₂（二氧化碳）、PM2.5（细颗粒物）**。
- 注意 **CO₂ 严格说是温室气体 (greenhouse gas)，不是「空气污染物」**（不直接危害呼吸健康），但常与污染物一起监测。NOx、CO、PM2.5 才是直接的健康相关污染物。
- 数据集**没有** SO₂、O₃、PM10、VOCs——回答时可以指出这个局限。

**Q3. What are the main sources of pollution levels?（污染的主要来源？）**
只有两个：**(1) 发电 / 电力需求 (Electricity Demand)**、**(2) 道路交通 / 车流量 (Traffic Volume)**。
**定量答案**：电力需求解释了 CO₂ 变化的 **99.98 %**（R² = 0.9998），车流量只解释 28.6 %（且大部分是共变假象）。**电力是压倒性的主导来源。**

**Q4. What process is responsible for creating the pollutants from each source?（每个来源通过什么过程产生污染物？）**
- **发电（天然气/煤燃烧）**：化石燃料的**完全燃烧**产生大量 **CO₂ + H₂O**；燃烧室**高温**使空气中 N₂ + O₂ → **NO（thermal NOx）**，NO 再氧化成 NO₂；燃烧不完全或燃料含杂质时产生 **CO** 与**一次颗粒物 (PM2.5)**。
- **道路交通（内燃机）**：汽油/柴油**燃烧**产生 CO₂；缸内高温高压产生 **NOx**；氧气不足（富油工况、冷启动、怠速拥堵）产生 **CO**；柴油机的扩散燃烧产生大量 **soot（碳烟）→ PM2.5**；此外还有**非尾气来源 (non-exhaust)**：刹车片、轮胎、路面磨损与扬尘。

#### Section 2：Correlation Analysis（相关性分析）

**Q1. Electricity consumption 与 CO₂ emissions 的关系？**
- **极强的正线性相关**：**R² = 0.9998**（r = 0.9999）——几乎是完美直线。
- 最佳拟合：**CO₂ (kg/h) = 514.4 × Electricity Demand (MWh) + 445**
- **物理解释斜率**：每多用 1 MWh 电，就多排放约 **514 kg CO₂**（≈ **0.51 kg CO₂/kWh**），这就是这座城市电网的**碳强度 (carbon intensity)**，与燃气发电厂的量级一致。
- 数据集真实生成系数为 **510 kg/MWh**，回归得 514.4 是因为交通项被吸收了一小部分。

**Q2. Precipitation 与 PM2.5 的关系？**
- **中等强度的负相关**：**r = −0.377，R² = 0.142**，拟合线 **PM2.5 = −0.825 × Precip + 19.24**（每多 1 mm 降水，PM2.5 排放率降低约 **0.83 kg/h**）。
- **但直接做全样本回归会低估这个效应**，因为 PM2.5 的绝对值主要由电力需求决定，降水只是一个乘性折减因子。**更好的分析方法**（这是本题的高分答法）：
  - **方法 A：分组比较**。有雨小时 vs 无雨小时的 PM2.5 均值——Friday（大雨，日均 14.7 mm）PM2.5 均值 **6.96 kg/h**，其余无雨日均值 **19.76 kg/h**，**降低 65 %**。
  - **方法 B：归一化**。计算 **PM2.5 ÷ Electricity Demand** 的比值以消除排放源强度的影响：无雨日恒为 **0.0403**，小雨日 **0.0339（↓16 %）**，大雨日 **0.0164（↓59 %）**。这条证据最干净。
- **机制**：**wet deposition（湿沉降）**——包括 **rainout（云内清除）** 与 **washout（云下清除）**，雨滴碰撞捕获并带走气溶胶颗粒。
- **对照组证据**：同样在下雨的时段，**CO₂、CO、NOx 完全没有下降**（R² 均 < 0.01）。这符合物理预期：**气体不像颗粒物那样容易被雨水清除**。

**Q3. CO₂ 与「电力需求」还是「车流量」相关性更强？请用 R² 与最佳拟合线的梯度解释。**

**这是 Section 2 的核心题，标准答法如下：**

| 对比项 | CO₂ vs **Electricity Demand** | CO₂ vs **Traffic Volume** |
| --- | --- | --- |
| **R²** | **0.9998** | **0.2856** |
| 拟合线斜率 | **514.4 kg CO₂ per MWh** | 124.6 kg CO₂ per (vehicle/hour) |
| 数据点分布 | 几乎完全落在直线上 | 散布极宽的点云 |

**结论**：**CO₂ 与电力需求的相关性远强于与车流量的相关性。**

**论证要分两层写：**
1. **用 R²（决定性证据）**：R² = 0.9998 意味着电力需求解释了 **99.98 %** 的 CO₂ 变化，几乎没有残差；而车流量只解释 **28.6 %**，超过七成的变化无法用车流量说明。因此电力需求是**主导驱动因子 (dominant driver)**。
2. **用梯度（要非常小心）**：两条线的斜率**单位不同**（per MWh vs per vehicle·h⁻¹），**不能直接比数字大小**。正确用法是把斜率乘以各变量的实际变动幅度：
   - 电力需求变动范围 100.6 → 1192.9 MWh，跨度 1092 MWh × 514.4 = **约 562 000 kg/h 的 CO₂ 变化**；
   - 车流量变动范围 50 → 2408 veh/h，跨度 2358 × 124.6 = 约 294 000 kg/h ——但这个数字本身就是**被夸大的**。

**加分要点（真正理解数据的标志）**：
- 车流量的 124.6 这个斜率**是虚高的**。因为 **corr(Traffic, Electricity) = 0.523**，两者在早晚高峰同时升高，车流量在回归中「借用」了电力需求的效应。做**多元回归**同时放入两个变量，得到 **CO₂ = 510.0 × Elec + 3.79 × Traffic**，**R² = 1.0000**——车流量的真实边际效应只有 **3.79 kg CO₂ per vehicle·h⁻¹**，比单变量回归给出的 124.6 小了约 **33 倍**。
- 用平均值算贡献占比：电力贡献 510 × 474.7 = **242 100 kg/h（99 %）**，车流贡献 3.81 × 665.6 = **2 536 kg/h（1 %）**。
- **最直观的反证**：2024-11-05 20:00（周六晚），车流量仅 **178**（全周极低），电力需求 **1115 MWh**，CO₂ 高达 **569 384 kg/h**、PM2.5 达到**全周最高的 50.21 kg/h**。低车流依然高污染 → 交通不是主因。

#### Section 3：Temporal Trends（时间趋势）

> 讲义提示：**"There is a drop-down menu next the header for the time that allows you to filter the data based on date or time."**（表头旁的下拉菜单可按日期或时间筛选数据。）

**(a) Rush hours vs. non-peak hours（高峰 vs 非高峰）**

观察到的现象：
- **车流量呈清晰双峰 (bimodal / twin-peak)**：早高峰 **07:00–09:00**（08:00 均值 1596 veh/h 为最高）、晚高峰 **17:00–19:00**（18:00 均值 1603 veh/h 为最高）；夜间 **23:00–04:00** 降至 100–220 veh/h。**峰谷比约 9 : 1**。
- **电力需求的峰值也在 06:00–08:00 与 18:00–20:00**，但**衰减更慢**：晚高峰后 19:00 (805)、20:00 (790) 仍然很高，而车流量在 19:00 已经掉到 379。
- **污染物完全跟随电力需求，而不是车流量**：
  - CO₂ 峰值出现在 **18:00 (513 443 kg/h)** 和 **08:00 (435 892)**，与电力需求的峰完全同相；
  - 19:00–20:00 车流量已经回落到 ~400，但 CO₂ 仍维持在 40 万以上；
  - **17:00 是最关键的反例**：车流量 1404（第三高），但电力需求只有 371，CO₂ 只有 194 372——**比 19:00（车流量仅 379）的 411 827 还低一半以上**。
- 定量：高峰时段 (07–09, 17–19) 车流量是夜间的 **9.2 倍**，但 CO₂ 只有 **2.6 倍**。

**结论**：**高峰时段污染确实更高，但升高的原因是电力需求同步上升，而不是车流量本身。**

**(b) Weekdays vs. weekends（工作日 vs 周末）**

| | 车流量 | 电力需求 | CO₂ | PM2.5 |
| --- | --- | --- | --- | --- |
| 工作日 (Mon–Fri) | **684** | 443 MWh | 228 569 kg/h | 15.20 kg/h |
| 周末 (Sat–Sun) | **620（↓ 9 %）** | **554 MWh（↑ 25 %）** | **284 831 kg/h（↑ 25 %）** | **22.71 kg/h（↑ 49 %）** |

**这是本数据集最反直觉、也最出题的发现**：
- 周末**车流量更低**（通勤消失），但**电力需求反而高出 25 %**（住宅用电增加：人在家、供暖/空调/娱乐设备），
- 结果**周末的 CO₂ 与 PM2.5 排放反而高于工作日**。
- 这**再次独立地证明**污染由电力驱动：如果交通是主因，周末污染应当下降。
- （附带说明：PM2.5 周末涨幅 49 % 大于 CO₂ 的 25 %，是因为工作日均值被 Wednesday 与 Friday 两个下雨日的冲刷效应拉低了。剔除雨天后，工作日 PM2.5 ≈ 17.8，周末 22.7，涨幅约 28 %，与电力涨幅一致。）

**(c) 其他可写的趋势**
- **温度**：严格的日循环，夜间 10 °C、11:00 达 22 °C 峰值；与污染物**几乎零相关 (R² < 0.008)** —— 说明这个模型里**没有考虑供暖需求随气温变化**，是模型的简化。
- **风速**：白天大（最高 11.9 m/s）、夜间小（下限 2 m/s）；与所有污染物**零相关 (R² ≈ 0)**。**这是模型的重要局限**：真实世界中风速通过稀释与输送强烈影响**浓度**；但本数据集给的是**排放率**，排放率本来就不该受风影响。**如果给的是浓度，就必须看到强烈的负相关。**
- **湿度**：与所有污染物零相关。

#### Section 4：Identifying Outliers（识别离群值）

**Q1. Identify any extreme values in pollutant emissions.（找出污染物排放中的极端值）**

方法：算均值 + 标准差，标出 |x − x̄| > 2 SD 的点（或用箱线图）。

- **CO₂ 最高**：2024-10-31 08:00（Monday），**615 623 kg/h**（均值 244 643，SD 142 578 → 高出 **2.6 SD**）
- **PM2.5 最高**：2024-11-05 20:00（Saturday），**50.21 kg/h**（均值 17.34，SD 11.42 → 高出 **2.9 SD**）
- **NOx 最高**：601.0 kg/h（2024-10-31 08:00）
- **车流量最高**：2 408 veh/h（2024-11-02 18:00）
- **最低值**：CO₂ 最低 52 445 kg/h；PM2.5 最低 1.96 kg/h（出现在大雨的 Friday）

**电力需求 > 均值+2SD（1029 MWh）的 5 个时刻**（即第 3.5 节的表）：Mon 08:00、Thu 18:00、**Sat 20:00**、Tue 08:00、Wed 18:00。

**Q2. Are there times when emissions spike unexpectedly?（有没有排放意外飙升的时刻？）**

**有，而且最值得写的就是这一条**：
- **2024-11-05 20:00（Saturday）**：**车流量仅 178 veh/h（全周最低区间之一）**，但电力需求高达 **1115 MWh**，导致 **CO₂ 569 384 kg/h**、**PM2.5 达到全周最高值 50.21 kg/h**。这是「**在最不该出现污染峰的时间出现了污染峰**」的典型异常。
- **对称的反例**：**2024-10-31 17:00（Monday）**，车流量 2 398（全周第三高），电力需求只有 276 MWh，CO₂ 仅 149 804 kg/h ——**极高车流量下污染反而处于低位**。
- **PM2.5 的「反向异常」**：整个 **Friday**，电力需求与其他日子相当（431 MWh vs 均值 475），但 PM2.5 只有 **6.96 kg/h**，比正常水平低 **65 %**——这是一个**低值离群 (low outlier)**。

**Q3. What could have caused these anomalies?（可能的成因？）**

必须分成「**数据集内可解释的**」和「**现实世界的可能机制**」两层作答：

**A. 在本数据集内可解释的（先做这一步，才是严谨的分析）**
1. **Sat 20:00 的 PM2.5 峰值** → 由**异常高的电力需求**完全解释（周末晚间居民用电高峰）。既然 PM2.5 = 0.04 × Elec × f_rain，1115 MWh 必然产生约 44.6 kg/h，加上无雨 f = 1.0 → 观测值 50.2 与之一致。**不是数据错误，是真实的机制性极值。**
2. **Friday 的 PM2.5 低值** → 由**大雨的湿沉降**完全解释（f_rain ≈ 0.41）。
3. **Mon 17:00 的低污染** → 电力需求恰好处在低谷；说明**交通对总排放的边际贡献太小**，无法把污染顶起来。

**B. 现实世界中可能造成此类异常的原因（拓展作答）**
- **发电侧**：电厂计划外停机后启用**效率较低的备用/尖峰机组 (peaking plant)**；可再生出力骤降（无风/夜间无光）导致燃气机组顶峰；寒潮/热浪推高供暖或制冷负荷。
- **交通侧**：**交通事故或道路封闭造成拥堵 (congestion)**——车流量计数不高但怠速排放极高；大型赛事/活动散场。
- **气象**：**逆温层 (temperature inversion)** + 静风 → 混合层高度骤降，同样的排放造成浓度飙升（注意：这影响**浓度**而非**排放率**）。
- **外部源**：邻近区域的**野火烟羽 (wildfire smoke plume)**、农业焚烧、烟花（如 11 月 5 日恰好是英国的 **Bonfire Night / Guy Fawkes Night**，全国燃放篝火与烟花 —— **2024-11-05 20:00 这个 PM2.5 峰值时间点非常巧合，值得在报告里点名**）、沙尘输送、工业事故。
- **仪器/数据问题**：传感器漂移、标定错误 (miscalibration)、单位录入错误、数据传输丢包造成的尖峰。

> **Bonfire Night 彩蛋**：数据集里 PM2.5 全周最高值落在 **11 月 5 日晚 20:00**，正是英国 Bonfire Night 燃放烟花的时刻，而 PM2.5 恰恰是烟花的标志性污染物。虽然数据集的生成公式里并没有真的加入「烟花项」（该峰值由电力需求驱动），但在报告里指出这个时间巧合能体现对情境的敏感度。

#### 数据处理与结果判读的完整逻辑链（本节总结）

```
观察 → 相关性 → 剥离混杂 → 定量归因 → 反证检验 → 结论
 ↓        ↓          ↓            ↓          ↓         ↓
时间序列  R²比较   多元回归   贡献占比%   离群时刻   电力主导
双峰     0.9998    510 vs 3.79   99%:1%   Sat 20:00  (99%)
        vs 0.286                          低车流高污染
```

**最终结论（要写进报告的一句话）**：
> 在这座模拟城市中，**电力需求 (Electricity Demand) 是空气污染排放的压倒性主导因素**，单独解释了 CO₂ 变化的 99.98 %、NOx 的 99.8 %；**车流量只有次要影响**（对 CO₂ 约 1 %，对 CO 约 8 %，因为 CO 是不完全燃烧产物、交通占比相对较高）。**降水是唯一有效的清除机制，且只作用于 PM2.5**（大雨可使 PM2.5 降低约 60 %），对气体污染物无效。因此，**减排的最有效政策杠杆是电源脱碳（提高可再生占比 / 从煤或天然气转向低碳电源），而不是限制交通**。

---

### 【上午场 B】City Air Pollution Simulator 情景模拟

> **目的**：把 Section 2 得到的「谁是主因」结论**在可控的参数空间里验证一遍**，并测试各种减排政策的效果。
> **方法**：单变量敏感性分析 (one-at-a-time sensitivity analysis) —— **每次只改一个滑块，其余保持默认**，记录排放变化。

#### 操作步骤

1. **记录基线 (baseline)**：先在默认设置（Traffic 300、Diesel 30 %、Petrol 50 %、EV 20 %、Electricity 800 MW、Renewable 20 %、Source = Natural Gas、Speed 20 km/h）下记下四种污染物的排放值。
2. **单变量扫描**：每次只动一个参数，取 3–5 个档位（如 Traffic = 100 / 300 / 600 / 1200 / 2400），记录每种污染物的响应。
3. **回到基线**再改下一个参数（**关键：不要多个参数一起改，否则无法归因**）。
4. **把每组数据画成折线图**（x = 参数值，y = 排放量），比较各条线的**斜率陡峭程度** = 敏感度。
5. **做政策情景 (policy scenarios)** 组合测试（见下表）。

#### 需要设计并记录的情景

| 情景 | 参数设置 | 预期结论 |
| --- | --- | --- |
| **基线 (Baseline)** | 全部默认 | 参照点 |
| **交通翻倍** | Traffic 300 → 600（其余不变） | 各污染物涨幅有限（交通份额小） |
| **电力翻倍** | Electricity 800 → 1600 MW | **各污染物近乎翻倍**——敏感度最高 |
| **全面电动化 (Full EV)** | Diesel 0 %, Petrol 0 %, **EV 100 %** | 尾气 NOx/CO/PM 归零，**但若电力仍来自天然气/煤，CO₂ 只是转移到发电侧（"排放转移" emission shifting）** |
| **柴油转汽油** | Diesel 30 → 0 %, Petrol 50 → 80 % | **NOx 与 PM 下降**（柴油 NOx 限值 80 > 汽油 60，柴油 PM 更高），但 **CO 上升**（汽油 CO 限值 1000 > 柴油 500） |
| **电源脱碳 (Coal → Nuclear)** | Source: Coal → Natural Gas → Nuclear | **CO₂ 阶梯式大幅下降**；Nuclear 运行阶段近乎零碳 |
| **提高可再生占比** | Renewable 20 % → 50 % → 80 % | 排放**按比例线性下降**（可再生的那部分不排放） |
| **提速缓堵** | Speed 20 → 50 km/h | 单位里程排放下降（脱离低速高排放区间），总排放下降 |
| **最优组合** | EV 100 % + Renewable 80 % + Nuclear | 排放接近最低 |

#### 结果判读要点

- **最敏感的参数是 `Electricity Demand` 与 `Electricity Source`**，与数据集分析结论一致（互相印证）。
- **「排放转移 (emission shifting)」是必须写出来的洞察**：把车全换成 EV，尾气污染确实归零，**但用电量上升**；如果电还是燃煤/燃气发的，**总 CO₂ 未必下降**。因此 **EV 的减排效果取决于电网的碳强度**。这是本模拟器最重要的教学意图。
- **污染物之间存在权衡 (trade-off)**：柴油 vs 汽油在 NOx/PM 与 CO/CO₂ 之间是此消彼长的；没有单一「最干净」的选项。
- **比例约束**：柴油 + 汽油 + 电动必须 = 100 %，否则结果无意义。
- **注意单位**：模拟器写 MW（功率），数据集写 MWh（电量）；逐小时下数值等价。

---

### 【上午场 C】Wildfire Tracking & Emissions Calculation — 逐题梳理

> **目的**：结合遥感判读与化学计量，估算一场野火的 CO₂ 与 H₂O 排放量。
> **文件**：`wildfire_sheet_answers.md`（这是**答案版**，含全部计算过程）

#### Part 1：用 Sentinel-2 影像追踪野火

**四个操作步骤（逐条）**

| 步骤 | 原文任务 | 做法 / 判读要点 |
| --- | --- | --- |
| 1 | **Access the Copernicus Browser** | 打开 Copernicus Browser，用提供的链接定位火场。**左侧面板**在 **true SWIR（红外波段）** 与 **true colour（真彩色）** 之间切换 |
| 2 | **Identify the Fire's Progression** | 拖时间轴逐次过境对比，**从首次探测追踪到熄灭**。SWIR 下活跃火线呈亮红/橙、火烧迹地呈深棕、健康植被呈绿；真彩色下烟雾会遮挡 |
| 3 | **Measure the Burn Area** | 用**右侧的多边形量测工具 (polygon measuring tool)** 沿火烧迹地边界勾画，读取面积（km²） |
| 4 | **Estimate Vegetation Composition** | 估算森林 / 草地比例。两条途径：**(a) 看影像中植被的颜色**（森林深绿、草地黄绿/浅色）；**(b) 上网搜该地区的图片或植被资料** |

**答案文件给出的示例测量结果（后续计算全部基于这三个数）**：
- **Total Burned Area = 100 km²**
- **Percentage of Forest = 60 %**
- **Percentage of Grassland = 40 %**

#### Part 2：配平燃烧方程式

**题面（原文要点）**：木材与植物材料的主要成分是**纤维素 (cellulose) C₆H₁₀O₅**。氧气充足时发生燃烧，释放 **CO₂ 与 H₂O**；氧气受限时还会产生 **CO 与烟尘 (soot)**。
（⚠️ 原文误写为 "incomplete combustion occurs" —— 富氧应为 **complete combustion**，见第二节。）

**未配平**：C₆H₁₀O₅ + O₂ → CO₂ + H₂O

**答案（配平方程式）**：
$$\mathrm{C_6H_{10}O_5} + \mathbf{6}\,\mathrm{O_2} \rightarrow \mathbf{6}\,\mathrm{CO_2} + \mathbf{5}\,\mathrm{H_2O}$$

**答案文件给出的原子核对表**：

| 左侧原子数 | 元素 | 右侧原子数 |
| --- | --- | --- |
| **6** | C | **6** |
| **10** | H | **10** |
| **17** | O | **17** |

**解题思路（要写出来的推理顺序）**：
1. **先配 C**：左侧 6 个 C → 右侧 CO₂ 系数 = **6**；
2. **再配 H**：左侧 10 个 H → 右侧 H₂O 系数 = 10 ÷ 2 = **5**；
3. **最后配 O**：右侧总 O = 6×2 + 5×1 = **17**；左侧纤维素自带 **5** 个 O，还差 **12** 个 O → O₂ 系数 = 12 ÷ 2 = **6**；
4. **回查**：左侧 O = 5 + 6×2 = **17** ✓。

**为什么最后配 O**：O 同时出现在两个反应物和两个产物中，先配只出现一次的元素（C、H），最后用 O 收尾，是配平的通用策略。

#### Part 3：计算 CO₂ 排放量

**Step 1：确定火烧区内的生物量与纤维素量**

给定参数（答案文件原文）：
- **Forest biomass = 75 tonnes per acre**
- **Grassland biomass = 10 tonnes per acre**
- **Forest cellulose content = 50 % of biomass**
- **Grassland cellulose content = 30 % of biomass**

单位换算：**1 km² = 247.1 acres → 100 km² = 24,710 acres**

**森林 (Forest)**（逐步照抄答案）：
1. 24,710 acres × 0.6 = **14,826 acres of forest**
2. 14,826 acres × 75 tonnes/acre = **1,111,950 tonnes of biomass**
3. 1,111,950 tonnes × 0.5 = **555,975 tonnes of cellulose**

**草地 (Grassland)**：
1. 24,710 × 0.4 = **9,884 acres**（答案文件此处笔误写成 "acres of forest"，应为 grassland）
2. 9,884 acres × 10 tonnes/acre = **98,840 tonnes of biomass**（答案文件排版误写为 "98,8840"）
3. 98,840 tonnes × 0.3 = **29,652 tonnes of cellulose**

**合计**：555,975 + 29,652 = **585,627 tonnes of cellulose burned**

**Step 2：最终排放计算**

**CO₂**（答案文件原文逻辑，逐句）：
- "balanced equation has a **mole ratio between cellulose and CO₂ of 1 : 6**"（配平方程式中纤维素与 CO₂ 的摩尔比为 1 : 6）
- **Molar mass of cellulose = 162 g**
- **Molar mass of 6CO₂ = 44 g × 6 = 264 g**
- 因此 **162 g 纤维素产生 264 g CO₂**
- **质量转换因子 = 264 ÷ 162 = 1.63**
- **585,627 tonnes × 1.63 = 954,572 tonnes of CO₂** ✅

**H₂O**：
- "mole ratio between cellulose and H₂O of **1 : 5**"
- **Molar mass of cellulose = 162 g**；**Molar mass of 5H₂O = 18 g × 5 = 90 g**
- 因此 **162 g 纤维素产生 90 g H₂O**
- **转换因子 = 90 ÷ 162 = 0.56**（实际计算用的是未取整的 0.5556）
- **585,627 tonnes × 0.5556 = 325,348 tonnes of H₂O** ✅

**核对与拓展**：
- 若 CO₂ 也用精确的 264/162 = 1.62963，得 **954,355 t**（讲义的 954,572 t 因四舍五入到 1.63 而高出 217 t，误差 0.02 %，可接受但要意识到）。
- **碳质量平衡独立验算**：纤维素中碳的质量分数 = 72/162 = 44.4 % → 585,627 × 0.4444 = **260,279 t C**；全部氧化为 CO₂：260,279 × 44/12 = **954,355 t** ✓。
- **单位面积排放强度**：约 **9,544 t CO₂ / km²**。
- **量级感**：954,572 t CO₂ ≈ 一座百万人口城市数天的 CO₂ 排放；也约等于 20 万辆汽车行驶一整年的排放。

#### 这套方法的关键假设（写报告时必须列出的 limitations）

1. **假设 100 % 的生物量被完全燃烧**——实际野火只烧掉部分地上生物量（地下根系、粗大树干、湿润植被常残留），**实际燃烧效率 (combustion completeness) 通常只有 20–90 %**，所以此估算是**上限值 (upper bound)**。
2. **假设生物质全部是纤维素**——实际木材还含**半纤维素 (hemicellulose, ~20–30 %)** 和**木质素 (lignin, ~20–30 %)**，两者的 C:H:O 比不同，CO₂ 产率略有差异。
3. **假设完全燃烧**——真实野火有大量**闷烧 (smouldering)**，产生 CO、CH₄、黑碳，因此 CO₂ 产率被高估，而这些其他产物没被计入。
4. **生物量密度是粗略的类型平均值**（75 / 10 t per acre），实际随林龄、树种、气候差异巨大。
5. **面积与植被比例靠目视估算**，多边形勾画与颜色判读带主观误差。
6. **忽略了净碳平衡**：若火后植被再生，这部分碳会被重新吸收，**净排放小于总排放**（不同于化石燃料的净新增排放）。

---

### 【下午场】Microscope Practical Class 2 — 9 张薄片逐个梳理

> **目的**：(1) 描述矿物光学性质；(2) 用薄片结构判定三大岩类；(3) 练习带比例尺的素描。
> **方法**：偏光显微镜，PPL 与 XPL 交替观察，旋转载物台。
> **判据**：worksheet 第 5 页的三大岩类属性表（见第二节）。

#### 通用观察流程（每张薄片都按这个顺序走一遍）

1. **肉眼看整张薄片 (naked eye)** —— worksheet 明确要求：blueschist 的**成分层理 (compositional layering)** "Look at the slide with the naked eye to see this"。**大尺度构造在低倍或肉眼下才看得到，不要一上来就用高倍。**
2. **低倍 PPL 通览**：数一数有几种矿物？有没有孔隙？晶体是互锁还是碎屑？有没有优选定向？
3. **逐矿物 PPL 观察**：颜色 → 多色性（旋转 360°）→ 突起 → 解理/裂纹 → 晶形 → 蚀变 → 包裹体。
4. **切到 XPL**：干涉色（**找该矿物的最高干涉色**）→ 是否各向同性 → 双晶 → 消光。
5. **回到属性表逐条打勾**，最后下结论并写理由。
6. **画素描**：加**比例尺**、加**标注 (annotations)**、注明**是 PPL 还是 XPL**。

---

#### 【示范样品 1/9】**Peridotite（橄榄岩）— 编号 RP 或 R56 — 火成岩 (Igneous)**

**背景（worksheet 原文）**："Most of the Earth's mantle is made of peridotite, but these samples actually come from a large intrusion (from the island of **Rum, Inner Hebrides, Scotland**)."（地幔主要由橄榄岩组成，但这些样品实际来自苏格兰**内赫布里底群岛 Rum 岛**的一个大型侵入体。）R56 上周看过，RP 与之类似。

**主要矿物：olivine（橄榄石）**

| 问题 | **答案** |
| --- | --- |
| 画几个晶形较好的晶体（会有**平行的边 parallel sides**） | 素描；答案文件比例尺标注 **1 mm**；批注 **"Note these crystals are not as parallel sided as they could be!"** |
| 突起是高还是低？(Is its relief high, or low?) | **High（高突起）** |
| 能看到解理吗？(Can you see any cleavage in it?) | **No（没有；最多很弱 "maybe weak"）**——但有**发育良好的不规则裂纹 (well-developed irregular fractures)** |
| 各晶体取向下的干涉色范围？**最高**干涉色（Michel-Lévy 图表上）是什么？ | **"It will be a colour in the intermediate range."（中等范围的颜色，即 2 级干涉色）** |

**判定为火成岩的证据（逐条，答案文件原文）**：

| 属性问题 | 答案 | 备注 |
| --- | --- | --- |
| Does it have interlocking crystals? | **No.** | ⚠️ 反直觉！属性表说火成岩「倾向于」互锁，但这块**不互锁**——因为它是**堆晶岩 (cumulate)**：晶体先从岩浆中结晶沉降堆积，晶间由后期结晶物填充 |
| Do some crystals have their own shape? | **Yes**（在 R56 中不太明显） | 自形晶 = 在液体中自由生长 |
| Does it contain relatively few minerals? | **Yes** —— 大部分是 olivine 加另外两种矿物（另有少量不透明颗粒 opaque grains 和一些蚀变） | ≤ 5 种 |
| Are crystals of each mineral quite uniform? | **Yes.** | |
| Does it contain fossil gas bubbles (= vesicles)? | **No, it has no porosity.** | 深部侵入体压力大，气体溶解不出溶 |
| Do the crystals have a preferred orientation? | **No.** | 随机取向 → 排除变质岩 |

**教学要点**：**属性表是「可能的属性 (possible attributes)」清单，不是必须全部满足的检查表**。这块岩石在第 1 条上就是 "No"，但其余 5 条都指向火成岩。**判定靠证据的权重与组合，不靠逐条全中。**

---

#### 【示范样品 2/9】**Blueschist（蓝片岩）— 编号 A/986 — 变质岩 (Metamorphic)**

**背景（worksheet 原文）**："Before metamorphism it was an igneous rock (probably volcanic), and it has been metamorphosed at **high pressure**, producing several new minerals."（变质前是火成岩（很可能是火山岩），经**高压变质**产生了若干新矿物。）

> **地质意义（背景补充）**：蓝片岩相 (blueschist facies) 是**高压 / 低温 (HP/LT)** 变质条件的标志，形成于**俯冲带 (subduction zone)** ——冷的洋壳被快速带到深处，压力上去了但温度还没跟上。蓝色矿物是**钠质角闪石 glaucophane（蓝闪石）**。

**矿物 1：蓝色矿物（worksheet 明说 "you do NOT need to be able to identify"，不要求识别）**

| 问题 | **答案** |
| --- | --- |
| 它的**多色性 (pleochroism)** 是什么颜色？ | **"Mostly pale blue and mauve, but some crystals may go almost colourless."**（多数为**淡蓝色与紫红色 (mauve)**，部分晶体可能几乎变为无色） |

**矿物 2：garnet（石榴石）** —— worksheet 提示："There is a mineral in this thin section that is **equant** (见上周讲义第 6 页 2-D sections through 3-D crystals) **and isotropic**."

| 问题 | **答案** |
| --- | --- |
| 找到它并画一个晶体的素描 | 素描；答案文件比例尺标注 **"Variable size ~0.1–0.5 mm"** |
| 突起？(What is its relief?) | **High（高）** |
| 颜色？(What is its colour?) | **Colourless or very pale pink（无色或极淡的粉色）** |
| 该矿物是什么？ | **Garnet（石榴石）** |

**garnet 的三条鉴定组合**：**等轴 (equant) + 各向同性 (isotropic，XPL 下恒黑) + 高突起 + 无色/淡粉**。

**判定为变质岩的证据（逐条）**：

| 属性问题 | 答案 |
| --- | --- |
| Does it have **compositional layering**? | **Yes.** —— **"Look at the slide with the naked eye to see this."**（用肉眼看整张薄片才看得出来） |
| Does it contain relatively few minerals? | **Yes, 5 or 6.** |
| Are crystals of each mineral quite uniform? | **Yes.** |
| Do some crystals have their own shape? | **Yes.** |
| Does it contain any porosity? | **No.** |
| Do the crystals have a **preferred orientation**? | **Yes, it has foliation（有片理）** —— ⭐ **worksheet 版明确写：This is the key evidence that this is a metamorphic rock（这是判定为变质岩的关键证据）** |

---

#### 【示范样品 3/9】**Sandstone（砂岩）— 编号 R25 或 SK — 沉积岩 (Sedimentary)**

**含两种矿物：一种低干涉色，一种高干涉色。**

**矿物 1：低干涉色的 → quartz（石英）**

| 问题 | **答案** |
| --- | --- |
| 有解理吗？(Does it contain any cleavage?) | **No.** |
| 该矿物是？ | **Quartz** |

**quartz 的完整鉴定属性组合（worksheet 原文列举，务必背下来）**：
- **晶体非常清澈 (very clear) —— 没有蚀变 (no alteration)**，这是"a useful property of quartz"；
- **低突起 (low relief)**；
- **无双晶、无环带 (no twinning or zoning)**（这一点用来与长石区分——其他低干涉色矿物会有双晶或环带）；
- **无解理**；
- **低干涉色**（1 级灰白）。

**矿物 2：高干涉色的 → calcite（方解石）**
- 干涉色："**The sandy interference colour, with green and pink tinges**"（沙色，带绿色与粉色调）—— 这是典型的**高级干涉色**。
- ⭐ **worksheet 原文关键句**："**Calcite (and its fellow carbonate mineral, dolomite) is the only common mineral you will see with high interference colour.**"
- **产状**："Notice how the calcite is **filling in the gaps around the quartz crystals, forming a cement**."（方解石填充在石英颗粒之间的空隙中，形成**胶结物 cement**。）

**素描任务**：画几个 quartz 颗粒，并**标注 (annotate) 出 calcite cement**。答案文件的素描注释："**Calcite cement in between quartz grains**"。

**判定为沉积岩的证据（逐条）**：

| 属性问题 | 答案 |
| --- | --- |
| Does it consist of **particles (clasts)** of pre-existing rocks? | **Yes** —— 许多石英颗粒**形状很不规则 (very irregular shape)**，说明它们**不是新鲜结晶的晶体**，而是**从先存岩石上磨蚀 (abraded) 下来的** |
| Are the clasts rounded? | **Some of them.（部分是）** |
| Does it contain fossils? | **No.** |
| Does it contain organic matter? | **No.** |
| Does it contain any porosity? | **No** —— 因为**方解石胶结物已经把早期孔隙填满了** |
| Is it layered? | **Not that you can see on the thin section scale.**（在薄片尺度上看不到层理） |

**关键判读逻辑**：**「颗粒形状不规则/磨圆」+「有胶结物填充粒间」= 碎屑沉积岩**。这两条是最强的沉积岩薄片证据。

---

> **以下 6 个是需要自己判定的未知样品 (Rocks for you to identify)**

---

#### 【未知样品 4/9】**SB2 — 变质岩 (Metamorphic)**

**先看绿棕色矿物：biotite（黑云母）**

| 问题 | **答案** |
| --- | --- |
| 解理如何？ | **very good cleavage（极好的解理，一组完全解理）** —— worksheet 强调 "make sure you can see this" |
| 画一个显示良好解理的晶体 | 素描：画出一组平行的细直线 |
| 把解理转到 **N–S** 方向，看到 pale brown 还是 dark green-brown？ | **多数教学显微镜（下偏光镜 E–W）下应为 pale brown（浅棕色）**——⚠️ **答案文件此处未给出答案，需自己观察记录**。原理：**吸收最强的方向平行于偏光镜振动方向时颜色最深**；biotite 的最大吸收方向**平行于解理**。 |
| 把解理转到 **E–W** 方向，看到哪个？ | **dark green-brown（深绿棕色）**（同上，以自己那台镜子为准） |
| 该矿物是？ | **Biotite（黑云母）**——worksheet 补充："usually more of an orange-brown than a green-brown"（通常更偏橙棕而非绿棕） |
| 里面的小包裹体是什么？为什么周围有暗晕？ | **zircon（锆石）包裹体**；锆石含微量**放射性铀 (uranium)**，衰变放出的 **α 辐射 (alpha radiation)** 损伤周围的黑云母晶格，形成 **pleochroic haloes（多色晕）**。"These are quite common in biotite." |

**岩石类型判定**

> **答案（原文）**：**"Metamorphic. The crystals are aligned in a foliation."**（变质岩。晶体沿片理定向排列。）

**理由展开**：晶体呈**优选方位 (preferred orientation)**，构成**片理 (foliation)** —— 这是构造变形产生的组构，只有变质岩才有（火成岩的流动定向是例外情况，且不会形成贯穿性片理）。含大量云母且强片理化 → 很可能是**片岩 (schist)**。

---

#### 【未知样品 5/9】**NH — 变质岩 (Metamorphic)**

**先看绿色晶体之间的无色矿物：feldspar（长石）**

| 问题 | **答案** |
| --- | --- |
| 干涉色是 low / intermediate / high？ | **Low（低）** |
| 有什么特征结构？ | **Twinned（有双晶）** —— 见 worksheet 的 TWINNING 说明框 |
| 该矿物是？ | **Feldspar** —— 精确说是 **plagioclase feldspar（斜长石）**，"but we are just going to call it feldspar today"（今天统称长石即可） |

（绿色晶体是上周看过的矿物，很可能是角闪石/绿泥石类。）

**岩石类型判定**

> **答案（原文）**：**"Metamorphic. The crystals are aligned in a foliation."**（变质岩。晶体沿片理定向排列。）

**素描任务**：画几个晶体来说明这一点（**素描要画出定向排列的组构，而不只是单个晶体**）。

**教学要点**：这个样品的关键在于 —— **长石既出现在火成岩里也出现在变质岩里，所以矿物成分本身不能定类型；定类型的是「结构 texture」**，即晶体是否定向。

---

#### 【未知样品 6/9】**CP — 火成岩 (Igneous)**

含 **3 种主要矿物** + 一个**不透明相 (opaque phase)** + 一些**蚀变矿物 (alteration minerals)**。

**矿物 1：淡棕色矿物（pale brown mineral）** —— 从性质看是**辉石 pyroxene**（worksheet 未点名）

| 问题 | **答案** |
| --- | --- |
| 有多色性吗？(Is this mineral pleochroic?) | **Not obviously.（不明显）** |
| 有解理吗？(Does it have cleavage?) | **Yes**（但 "this is not obvious in all thin sections"，不是每张薄片都明显） |
| 干涉色 low / intermediate / high？ | **Intermediate** —— 判断口诀（原文）：**"if it is pink or higher, and very bright, then it is intermediate"** |

**矿物 2：无色、高突起的矿物 → olivine（橄榄石）**

| 问题 | **答案** |
| --- | --- |
| 有解理吗？ | **No.** |
| 有裂纹吗？(Fractures?) | **Yes** |
| 干涉色？ | **Intermediate** |
| 特征？ | **裂纹中有蚀变 (alteration in the fractures)** —— "this is common for this mineral"，是 olivine 的典型特征 |

> **注意与 RP/R56 的一致性**：橄榄石在两处都是 **高突起 + 无解理 + 有不规则裂纹 + 中等干涉色 + 沿裂纹蚀变**。这五条是 olivine 的固定组合。

**矿物 3：无色、低突起的矿物 → feldspar（长石）**

| 问题 | **答案** |
| --- | --- |
| 干涉色？ | **Low** |
| 特征？ | **Twinned（有双晶）** |
| 该矿物是？ | **Feldspar（plagioclase）** |

**岩石类型判定**

> **答案（原文）**：**"Igneous. Some of the crystals are interlocking and they are all in random orientation."**（火成岩。部分晶体互锁，且全部为随机取向。）

**理由展开**：
- **互锁晶体 (interlocking crystals)** → 从熔体中同时结晶、彼此挤占空间；
- **随机取向 (random orientation)** → **排除变质岩**（没有片理）；
- 无碎屑、无胶结物、无孔隙 → **排除沉积岩**；
- 矿物组合 olivine + pyroxene + plagioclase → **基性 (mafic) 火成岩**，如**辉长岩 (gabbro)** 或**玄武岩 (basalt)**。

**素描任务**：画几个晶体展示互锁与随机取向。

---

#### 【未知样品 7/9】**CG — 火成岩 (Igneous)**

主要矿物三种：

| # | 矿物 | 参照描述 | 本样品的特殊之处 |
| --- | --- | --- | --- |
| 1 | **Quartz（石英）** | 见 R25/SK 描述 | 无色、低突起、低干涉色、**永不蚀变**、无双晶 |
| 2 | **Feldspar（长石）** | 见 NH 与 CP 描述 | ⭐ **在这块岩石里长石强烈蚀变 (heavily altered)**，变成"XPL 下呈灰色或有明亮干涉色的絮状斑点 (flecks)"。worksheet 强调：**"This is common in feldspar, whereas quartz is never altered."**（长石常蚀变，而石英从不蚀变）——**这是区分石英与长石的最实用判据** |
| 3 | **Mica（云母）**，大部分是 **Biotite（黑云母）** | 已在 SB2 见过 | 这里的 biotite 是**更典型的红棕色 (red-brown)**；同样要画出显示良好解理的晶体，并描述解理 N–S 与 E–W 时的多色性颜色（同 SB2：N–S 浅、E–W 深）。上周在 15216 中也看过 biotite |

**岩石类型判定**

> **答案（原文）**：**"Igneous. Some of the crystals are interlocking and they are all in random orientation."**（火成岩。部分晶体互锁，全部随机取向。）

**⭐ 与 SB2 的关键对比（本次实践的核心考点）**：
**SB2 和 CG 都含大量 biotite**，但结论完全相反：
- **SB2 → 变质岩**：biotite **定向排列 (aligned in a foliation)**；
- **CG → 火成岩**：矿物**随机取向 + 互锁**。
- **同样的矿物，不同的结构 → 不同的岩石类型。矿物组合不能定类型，结构 (texture) 才能。**

矿物组合 quartz + feldspar + biotite → **长英质 (felsic) 侵入岩，即花岗岩 (granite) 类**。

---

#### 【未知样品 8/9】**S10 — 沉积岩 (Sedimentary)**

**题面（原文）**："The most abundant mineral in this rock occurs in a **wide range of grain sizes**. It is the same mineral as in at least one of the samples above. Can you identify it from its optical properties?"（本岩石中最丰富的矿物粒度变化范围很大，与上面至少一个样品中的矿物相同。能用光学性质识别它吗？）

| 问题 | **答案（原文）** |
| --- | --- |
| 最丰富的矿物是什么？ | **Quartz（石英）：colourless, low relief, low interference colour, no twinning or alteration.**（无色、低突起、低干涉色、无双晶、无蚀变） |

**岩石类型判定**

> **答案（原文）**：**"Sedimentary. Consists of clasts of pre-existing rocks, including polycrystalline rock fragments. These clasts are rounded."**（沉积岩。由先存岩石的碎屑组成，包括**多晶岩屑 (polycrystalline rock fragments)**。这些碎屑是**磨圆的 (rounded)**。）

**理由展开（三条独立证据）**：
1. **粒度范围宽 (wide range of grain sizes)** —— **分选差 (poorly sorted)**，是碎屑沉积物的特征；**火成岩与变质岩的每种矿物粒度都「相当均一 (quite uniform)」**（属性表第 4 条 / 第 2 条），这一条本身就排除了那两类。
2. **多晶岩屑 (polycrystalline rock fragments)** —— ⭐ **这是最强的沉积岩证据**：一整块由多个小晶体组成的颗粒，说明它是**从一块先存岩石上整块剥落下来的**，不可能是原地结晶的产物。
3. **碎屑磨圆 (rounded clasts)** —— 指示**搬运过程中的磨蚀 (abrasion during sediment transport)**。

**素描任务**：画出磨圆的碎屑与多晶岩屑，说明判定依据。

**岩石命名（拓展）**：石英为主 + 磨圆碎屑 + 分选差 → **砂岩 (sandstone)**，若含大量岩屑则为**杂砂岩/岩屑砂岩 (litharenite)** 或**砾岩 (conglomerate)**（取决于粒径）。

---

#### 【未知样品 9/9】**RE114 — 火成岩 (Igneous)**

**题面（原文）**："This sample contains crystals of one mineral that are **up to ~5 mm long**. The rest of the rock is **very fine-grained**. The large crystals are the same mineral as in at least one of the samples above."（本样品含有一种矿物的晶体，长达约 5 mm；岩石的其余部分非常细粒。大晶体与上面至少一个样品中的矿物相同。）

| 问题 | **答案** |
| --- | --- |
| 大晶体是什么矿物？ | **Olivine（橄榄石）** —— 依据其光学性质：**无色、高突起、无解理但有不规则裂纹、中等干涉色、裂纹中常见蚀变**（与 RP/R56 及 CP 中的完全一致） |

**岩石类型判定**

> **答案（原文）**：**"Igneous. Contains large olivine crystals. These have their own shape and are in random orientation. The rock also contains some vesicles (these are now filled with the glue that holds the thin section together; this glue is amorphous and is therefore isotropic)."**
> （火成岩。含大的橄榄石晶体，这些晶体**具有自形晶面**且**随机取向**。岩石还含有一些**气孔 (vesicles)**——这些气孔现在被固定薄片的**胶 (glue)** 填充，这种胶是**非晶质 (amorphous)**，因此**各向同性 (isotropic)**。）

**理由展开（三条证据）**：
1. **大晶体有自形晶面 (own shape)** → 在液体中无阻碍生长；
2. **随机取向** → 排除变质岩；
3. ⭐ **含气孔 (vesicles)** → **火成岩独有的决定性证据**（属性表第 5 条："May contain fossil gas bubbles (= vesicles)"）。气孔说明岩浆**喷出到地表或近地表**，压力骤降使溶解气体出溶形成气泡。

**⚠️ 关键陷阱与判读技巧**：气孔在薄片中被**环氧树脂胶**填充。**胶是非晶质的，所以在 XPL 下恒黑（isotropic）**，很容易被误认成 garnet 或不透明矿物。**区分方法**：
- **胶：低突起、形状不规则或圆形、常成群出现、边缘与围岩不吻合、无晶形**；
- **garnet：高突起、等轴、有晶形（常见六边形/八边形切面）**；
- **不透明矿物 (opaques)：在 PPL 下也是黑的**，而胶在 PPL 下是**透明无色的**——⭐ **PPL 下透明、XPL 下全黑 = 各向同性（胶或 garnet）；PPL 与 XPL 下都黑 = 不透明矿物。**

**结构命名（拓展）**：**大晶体 (phenocrysts) 嵌在细粒基质 (groundmass) 中 = 斑状结构 (porphyritic texture)**，指示**两阶段冷却**：先在岩浆房中缓慢结晶出大晶体，随后喷出地表快速冷却形成细粒基质。含橄榄石斑晶 + 气孔 → **玄武岩 (basalt)** 或**苦橄岩 (picrite)**。

---

#### 下午场 9 张薄片总表（速查）

| # | 编号 | **岩石类型** | 岩石名 | 关键矿物 | **判定的决定性证据** |
| --- | --- | --- | --- | --- | --- |
| 1 | **RP / R56** | **火成岩** | Peridotite（橄榄岩，堆晶） | **olivine** | 自形晶 + 随机取向 + 矿物种类少 + 无孔隙（**注意：不互锁**） |
| 2 | **A/986** | **变质岩** | Blueschist（蓝片岩，高压） | 蓝色角闪石 + **garnet** | **片理 (foliation) + 成分层理**（肉眼可见） |
| 3 | **R25 / SK** | **沉积岩** | Sandstone（砂岩） | **quartz + calcite 胶结物** | 形状不规则/磨圆的碎屑 + **方解石胶结物填充粒间** |
| 4 | **SB2** | **变质岩** | 片岩类 (schist) | **biotite**（含 zircon 多色晕） | **晶体沿片理定向排列** |
| 5 | **NH** | **变质岩** | — | **feldspar** + 绿色矿物 | **晶体沿片理定向排列** |
| 6 | **CP** | **火成岩** | 基性岩（gabbro / basalt） | pyroxene + **olivine** + **feldspar** | **互锁晶体 + 随机取向** |
| 7 | **CG** | **火成岩** | 花岗岩类 (granite) | **quartz + feldspar（强蚀变）+ biotite** | **互锁晶体 + 随机取向** |
| 8 | **S10** | **沉积岩** | 砂岩 / 岩屑砂岩 | **quartz** | **磨圆碎屑 + 多晶岩屑 + 粒度范围宽（分选差）** |
| 9 | **RE114** | **火成岩** | 玄武岩 / 苦橄岩（斑状） | 大 **olivine** 斑晶 + 细粒基质 | **自形斑晶 + 随机取向 + 气孔 (vesicles)** |

**统计**：**火成岩 4 个（RP/R56、CP、CG、RE114）、变质岩 3 个（A/986、SB2、NH）、沉积岩 2 个（R25/SK、S10）**。

---

## 六、易错点 / 重点难点

### 上午场

1. **⭐ 把「梯度大」当成「相关性强」**。CO₂-vs-Traffic 的斜率是 124.6，CO₂-vs-Electricity 的斜率是 514.4，看起来是同一量级；但**单位不同（per vehicle·h⁻¹ vs per MWh），完全不能直接比**。判断主导因子**必须看 R²**（0.286 vs 0.9998）。

2. **⭐ 忽略混杂 (confounding)**。车流量和电力需求本身相关 (r = 0.523)，所以单变量回归会把电力的效应算到交通头上，把交通的真实系数从 3.79 夸大到 124.6（**33 倍**）。**只要两个自变量共变，就必须做多元回归或分组控制。**

3. **把 kg/hour 当成浓度**。数据集给的是**排放率 (emission rate)**，不是**浓度 (concentration)**。worksheet 里写 "CO₂ concentration" 是措辞错误。**风速、混合层高度影响的是浓度而不是排放率**——这也解释了为什么本数据里风速与污染物零相关（不是错误，是因为给的是排放率）。若给的是浓度，风速必须呈显著负相关。

4. **直接用全样本回归判断降水效应**。PM2.5-vs-Precipitation 的 R² 只有 0.142，看起来「相关很弱」，很容易得出错误结论。正确做法是**归一化**（PM2.5 ÷ Electricity Demand：无雨 0.0403 → 大雨 0.0164，降 59 %）或**分组比较**（Friday 6.96 vs 无雨日 19.76，降 65 %）。**先控制住主导变量，才能看清次要变量的效应。**

5. **想当然认为「周末污染更低」**。本数据集里**周末车流量下降 9 %，但电力需求上升 25 %，导致污染反而上升 25 %**。作答一定要看数据，不要凭常识。

6. **只报告离群值而不解释机制**。Section 4 明确问 "What could have caused these anomalies?"。**先在数据集内部解释（Sat 20:00 的 PM2.5 峰完全由异常高的电力需求解释），再拓展到现实机制**（电厂尖峰机组、逆温、事故拥堵、Bonfire Night 烟花……）。

7. **混淆 CO 与 CO₂**。CO 是**不完全燃烧**的产物、有毒；CO₂ 是**完全燃烧**的产物、温室气体。数据里 **CO 的交通份额 (7.8 %) 明显高于其他污染物 (0.5–1 %)**，正因为交通工况（怠速、冷启动、拥堵）更容易产生不完全燃烧。

8. **认为 NOx 来自燃料中的氮**。**Thermal NOx 来自空气中的 N₂**，只要燃烧温度足够高（> 1300 °C）就会产生，**与燃料含不含氮无关**。

9. **⭐ 讲义原文的错误（必须知道正确版本）**：wildfire 讲义写 "In an **oxygen-rich** environment, **incomplete** combustion occurs, releasing CO₂ and H₂O" —— **富氧应为 complete combustion（完全燃烧）**。缺氧才是不完全燃烧（产生 CO 和 soot）。

10. **配平方程式先配 O**。正确顺序是 **C → H → O**：O 同时出现在两个反应物和两个产物中，最后配才不会来回调整。核对时务必写出 **17 = 17** 的两侧 O 总数。

11. **纤维素摩尔质量算错**。C₆H₁₀O₅ = 6×12 + 10×1 + 5×16 = 72 + 10 + 80 = **162 g/mol**。常见错误是把 O 算成 6 个（80 ≠ 96）。另外要知道纤维素实际是聚合物 **(C₆H₁₀O₅)ₙ**，162 只是**重复单元**。

12. **摩尔比与质量比混淆**。摩尔比是 **1 : 6**（纤维素 : CO₂），但**质量比是 162 : 264 = 1 : 1.63**。**不能直接用 6 去乘质量**（那会得到 6 × 585,627 = 3,513,762 t，错得离谱）。

13. **面积单位换算漏做**。生物量密度以 **tonnes per acre** 给出，但面积以 **km²** 量测。必须先换算 **1 km² = 247.1 acres**。忘了这一步会差 **247 倍**。

14. **⭐ 讲义答案的两处小瑕疵（自己算时要一致）**：
    - CO₂ 用了四舍五入的 **1.63**（→ 954,572 t），而 H₂O 用了未取整的 **0.5556**（→ 325,348 t）。**同一份计算里取舍精度要一致**。精确 CO₂ 应为 **954,355 t**。
    - 讲义中 grassland 一步误写为 "9,884 acres of **forest**"（应为 grassland），生物量误排为 "98,8840"（应为 **98,840**）。

15. **忘记声明假设与局限**。这套野火估算假设 **100 % 完全燃烧、生物质全是纤维素、生物量密度取类型平均**——结果是**上限估计**。报告里不写 limitations 会失分。

16. **在模拟器里一次改多个参数**。必须**一次只改一个 (one-at-a-time)**，否则无法归因。同时车型三个比例之和必须保持 **100 %**。

17. **认为电动车 = 零排放**。**排放转移 (emission shifting)**：EV 消除了尾气排放，但增加了用电需求；若电网碳强度高（燃煤/燃气），总 CO₂ 未必下降。**EV 的减排效果取决于电源结构。** 另外 EV 仍有**非尾气 PM**（刹车、轮胎、路面磨损，且 EV 更重）。

### 下午场

18. **⭐ 用矿物组合而非结构定岩石类型**。**SB2 与 CG 都以 biotite 为主，但一个是变质岩、一个是火成岩**——区别只在**晶体是否定向排列**。同理长石既在 NH（变质）也在 CP/CG（火成）中出现。**Texture（结构）决定类型，mineralogy（矿物学）不决定。**

19. **把属性表当成必须全中的检查表**。Peridotite (RP/R56) 的第一条 "interlocking crystals" 答案是 **No**（因为它是堆晶岩），但仍然是火成岩。**属性表是「possible attributes」，看证据的权重与组合。**

20. **⭐ 混淆解理 (cleavage) 与裂纹 (fractures)**。
    - **解理：平行、规则、成组、沿晶体学弱面**（biotite 的一组完全解理）；
    - **裂纹：不规则、不平行、无晶体学控制**（olivine 的 well-developed irregular fractures）。
    - **olivine 无解理但裂纹发育**，是最经典的对比例子。

21. **不去找最高干涉色就下结论**。同一种矿物在不同切面方向显示的干涉色差别极大（垂直光轴的切面甚至接近全黑）。worksheet 问的是 "**maximum** colour" ——**必须扫视整张薄片，找该矿物出现的最高干涉色**才能定级。

22. **在错误的偏光条件下观察性质**。
    - **多色性 (pleochroism)、突起 (relief)、解理、颜色 → 只能在 PPL 下看**；
    - **干涉色、双晶、消光、各向同性 → 只能在 XPL 下看**。
    - 忘了推/拉分析镜是最常见的操作失误。

23. **⭐ 把薄片胶 (glue) 当成矿物**。RE114 的气孔被胶填充，**胶是非晶质 → 各向同性 → XPL 下全黑**，容易被误认为 garnet。**鉴别法：PPL 下透明无色 + 低突起 + 无晶形 + 形状与围岩空腔吻合 = 胶；PPL 下也是黑的 = 不透明矿物 (opaque)；高突起 + 等轴 + 有晶形 = garnet。**

24. **不用肉眼看整张薄片**。Blueschist 的**成分层理必须用肉眼看整张玻片**才能发现（worksheet 明确指示）。**大尺度构造（层理、片理、条带）在高倍镜下反而看不见**。养成「肉眼 → 低倍 → 高倍」的顺序。

25. **忘记加比例尺**。worksheet 用星号特别强调今天的素描**必须加 scale bar**，需要先测视场宽度 (FOV)。**换物镜必须重测 FOV。** 素描还应注明是 PPL 还是 XPL。

26. **把自形晶画得过于理想化**。答案文件对 peridotite 素描的批注：**"Note these crystals are not as parallel sided as they could be!"** ——**素描是记录观察，不是画教科书示意图**，要照实画。

27. **用「有没有蚀变」以外的方法区分石英与长石**。两者都无色、低突起、低干涉色，最可靠的三条区分：
    - **石英：从不蚀变，永远清澈；无双晶；无环带**；
    - **长石：常强烈蚀变（浑浊斑点）；有多重双晶（"斑马纹"）；可能有环带 (zoning)**。

28. **看到高干涉色不往碳酸盐想**。worksheet 明确说 **calcite（和 dolomite）是你会见到的唯一常见高干涉色矿物**。看到沙色/珠光色带绿粉色调 → 直接考虑碳酸盐。

29. **多色性方向记反**。**最深的颜色出现在矿物最大吸收方向平行于下偏光镜振动方向时**。biotite 的最大吸收方向平行解理，所以解理平行偏光方向时最深。**务必先确认自己那台显微镜的下偏光镜振动方向（多数为 E–W）**，答案文件对 SB2 这一问**并未给出答案**，属于自行观察记录题。

30. **忽略「粒度均一性」这条判据**。属性表里火成岩「crystals of each mineral tend to be quite uniform」、变质岩「crystals of each mineral tend to be quite uniform」，而**沉积岩没有这条**。S10 的 "wide range of grain sizes（分选差）" 本身就是强有力的沉积岩证据。

31. **忘记「多晶岩屑」是沉积岩的铁证**。**polycrystalline rock fragment（一颗碎屑内部由多个小晶体组成）** 只可能来自先存岩石的整块剥落，火成岩与变质岩不可能原地长出这种结构。

32. **不知道气孔 (vesicles) 是火成岩独有**。属性表中只有火成岩列了 "may contain fossil gas bubbles (= vesicles)"。看到气孔基本可以直接定火成岩（且是**喷出/浅成**的）。

---

## 七、本周术语表

### 上午场：空气污染与遥感

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| NOx (NO + NO₂) | 氮氧化物 | 高温燃烧时空气中 N₂ 与 O₂ 化合生成，与燃料是否含氮无关 |
| Thermal NOx / Zeldovich mechanism | 热力型氮氧化物 / 泽尔多维奇机制 | 燃烧温度 > 1300 °C 时空气中 N₂ 被氧化的主要途径 |
| CO (Carbon monoxide) | 一氧化碳 | 氧气不足导致的**不完全燃烧**产物，有毒 |
| CO₂ (Carbon dioxide) | 二氧化碳 | **完全燃烧**产物，主要温室气体（严格说不是「空气污染物」） |
| PM2.5 | 细颗粒物 | 空气动力学直径 ≤ 2.5 µm 的颗粒物，能深入肺泡 |
| PM10 | 可吸入颗粒物 | 直径 ≤ 10 µm 的颗粒物 |
| Complete combustion | 完全燃烧 | 氧气充足，碳全部氧化为 CO₂ |
| Incomplete combustion | 不完全燃烧 | 氧气不足，产生 CO 与 soot（烟尘） |
| Soot | 碳烟 / 烟尘 | 燃烧生成的未燃碳质颗粒，是一次 PM2.5 的主要成分 |
| Primary pollutant | 一次污染物 | 直接从源排放出来的污染物 |
| Secondary pollutant / aerosol | 二次污染物 / 二次气溶胶 | 一次污染物在大气中经化学反应生成，如由 NOx 生成的硝酸盐颗粒 |
| Non-exhaust emissions | 非尾气排放 | 刹车、轮胎、路面磨损与扬尘产生的颗粒物，与燃料无关 |
| Emission rate | 排放率 | 单位时间排放的质量（本数据集用 kg/hour） |
| Concentration | 浓度 | 单位体积空气中污染物的质量（µg/m³），受排放率与稀释共同决定 |
| Carbon intensity | 碳强度 | 每发一度电排放的 CO₂（kg CO₂/kWh），本数据集隐含 0.51 |
| Correlation | 相关性 | 两个变量共同变化的统计关系，不等于因果 |
| R² / Coefficient of determination | 决定系数 | 自变量能解释因变量变化的比例，0–1，越接近 1 关系越紧 |
| Pearson's r | 皮尔逊相关系数 | 线性相关强度与方向，−1 至 +1；r² = R² |
| Gradient / Slope | 梯度 / 斜率 | 自变量每增加 1 单位，因变量变化多少（**带单位，不同变量间不可直接比较**） |
| Line of best fit / Trendline | 最佳拟合线 / 趋势线 | 最小化残差平方和的直线，Excel 中可显示方程与 R² |
| Confounding variable | 混杂变量 | 与自变量和因变量都相关的第三变量，会造成虚假或夸大的相关 |
| Multiple regression | 多元回归 | 同时纳入多个自变量，从而分离各自的独立贡献 |
| Outlier | 离群值 | 显著偏离整体分布的数据点（如 > 均值 ± 2 SD 或超出 1.5×IQR） |
| Standard deviation (SD, σ) | 标准差 | 数据离散程度的度量 |
| IQR (Interquartile range) | 四分位距 | Q3 − Q1，箱线图判断离群值的基础 |
| Diurnal cycle | 日变化 / 昼夜循环 | 以 24 小时为周期的变化模式 |
| Rush hour | 通勤高峰 | 本数据集为 07:00–09:00 与 17:00–19:00 |
| Wet deposition | 湿沉降 | 降水把大气中的污染物带到地面的总过程 |
| Rainout (in-cloud scavenging) | 云内清除 | 气溶胶作为凝结核被并入云滴而随雨落下 |
| Washout (below-cloud scavenging) | 云下清除 | 下落雨滴在空中碰撞捕获颗粒物 |
| Temperature inversion | 逆温 | 上暖下冷的稳定层结，抑制垂直混合，使污染物在近地面累积 |
| Mixing layer height | 混合层高度 | 污染物可垂直混合的大气层厚度，越低浓度越高 |
| Sensitivity analysis | 敏感性分析 | 每次只改一个参数，观察输出如何响应 |
| Emission shifting | 排放转移 | 把排放从一个环节挪到另一个环节（如 EV 把尾气排放转到发电侧） |
| Euro 6 | 欧六排放标准 | 欧盟机动车排放法规（汽油 NOx 60 mg/km、柴油 NOx 80 mg/km 等） |
| CCGT (Combined Cycle Gas Turbine) | 联合循环燃气轮机 | 高效燃气发电技术，约 0.35–0.40 kg CO₂/kWh |
| Renewable energy share | 可再生能源占比 | 电力中来自风、光、水等零碳源的比例 |
| Sentinel-2 | 哨兵 2 号卫星 | 欧盟 Copernicus 计划的光学多光谱卫星，10–60 m 分辨率，约 5 天重访 |
| Copernicus Browser | 哥白尼浏览器 | 免费在线卫星影像浏览与量测平台 |
| True colour | 真彩色 | 红/绿/蓝波段合成，接近肉眼所见；烟雾会遮挡火场 |
| SWIR (Short-Wave Infrared) | 短波红外 | 能穿透烟雾，活跃火线呈亮红橙、火烧迹地呈深棕 |
| Burn scar / Burned area | 火烧迹地 / 过火面积 | 被野火烧过的区域，SWIR 下呈深棕色 |
| Polygon measuring tool | 多边形量测工具 | Copernicus Browser 右侧用于勾画并计算面积的工具 |
| Cellulose (C₆H₁₀O₅) | 纤维素 | 木材与植物的主要成分，重复单元摩尔质量 162 g/mol |
| Hemicellulose / Lignin | 半纤维素 / 木质素 | 木材的另外两种主要成分，本练习中被忽略 |
| Biomass | 生物量 | 单位面积的植物物质质量（本练习：森林 75 t/acre、草地 10 t/acre） |
| Mole ratio | 摩尔比 | 配平方程式中各物质的系数比（纤维素 : CO₂ = 1 : 6） |
| Molar mass | 摩尔质量 | 1 mol 物质的质量（纤维素 162、CO₂ 44、H₂O 18、O₂ 32 g/mol） |
| Stoichiometry | 化学计量 | 用配平方程式的系数进行物质量换算 |
| Combustion completeness | 燃烧完全度 | 实际被烧掉的生物量占总生物量的比例，真实野火通常 20–90 % |
| Acre | 英亩 | 面积单位，1 km² = 247.1 acres |

### 下午场：显微镜与岩石学

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| Thin section | 薄片 | 磨到标准厚度 **30 µm** 的岩石片，可透光观察 |
| Petrographic / polarising microscope | 偏光显微镜 | 带下偏光镜与上分析镜的岩石学显微镜 |
| PPL (Plane-Polarised Light) | 单偏光 | 只用下偏光镜，看颜色、多色性、突起、解理、蚀变 |
| XPL / Crossed polars | 正交偏光 | 上下偏光镜垂直，看干涉色、双晶、消光、各向同性 |
| Polariser / Analyser | 下偏光镜 / 上分析镜 | 前者产生平面偏振光（多数为 E–W 振动），后者与之垂直 |
| Relief | 突起 | 矿物折射率与树脂 (n ≈ 1.54) 的差异，差异越大边界越显著 |
| Refractive index (RI) | 折射率 | 光在矿物中传播速度的度量，决定突起高低 |
| Cleavage | 解理 | 沿晶体结构弱面的规则裂开，PPL 下呈成组平行直线 |
| Fracture | 裂纹 | 不规则、不平行、无晶体学控制的破裂（olivine 的典型特征） |
| Pleochroism | 多色性 | PPL 下旋转载物台时有色各向异性矿物颜色/深浅变化 |
| Pleochroic halo | 多色晕 | biotite 中围绕含铀 zircon 包裹体的暗色圆晕，由 α 辐射损伤造成 |
| Interference colour | 干涉色 | XPL 下由光程差产生的颜色，本课分 low / intermediate / high |
| Birefringence (δ) | 双折射率 | δ = n_max − n_min，决定干涉色级次的高低 |
| Retardation (Γ) | 光程差 | Γ = δ × 薄片厚度，单位 nm，直接对应 Michel-Lévy 图表颜色 |
| Michel-Lévy colour chart | 米歇尔-列维干涉色图表 | 把光程差、双折射率、厚度三者联系起来的标准查算图 |
| Order (1st / 2nd / 3rd) | 干涉色级次 | 1 级灰白黄橙红（0–550 nm）、2 级蓝绿黄橙红（550–1100 nm）…… |
| Isotropic | 各向同性 | 光学性质各方向相同，XPL 下**恒黑**（garnet、玻璃、薄片胶） |
| Anisotropic | 各向异性 | 光学性质随方向变化，XPL 下有干涉色并每 90° 消光一次 |
| Extinction | 消光 | XPL 下旋转载物台时晶体变黑的位置，每转 90° 出现一次 |
| Twinning | 双晶 | 同一晶体内成分相同但取向不同的部分，XPL 下最易见 |
| Simple twinning | 简单双晶 | 只由两部分组成的双晶 |
| Multiple / polysynthetic twinning | 多重双晶 / 聚片双晶 | 单个晶体内含多个平行双晶单元，斜长石的"斑马纹"特征 |
| Zoning | 环带 | 晶体从核部到边缘成分渐变形成的同心带（石英从不出现） |
| Alteration | 蚀变 | 矿物被后期流体改造为细粒次生矿物，PPL 下呈浑浊斑驳 |
| Opaque | 不透明矿物 | 不透光的矿物（多为氧化物/硫化物），PPL 与 XPL 下都是黑的 |
| Equant | 等轴状 | 三个方向尺寸相近，任意切面都近似等轴（garnet 的特征） |
| Field of view (FOV) | 视场 | 目镜中看到的圆形范围直径；FOV = 视场数 ÷ 物镜倍数 |
| Stage micrometer | 载物台测微尺 | 刻有标准刻度（通常 1 mm/100 格）的玻片，用于测量 FOV |
| Scale bar | 比例尺 | 素描上必须标注的长度参照 |
| Olivine | 橄榄石 | 无色、高突起、无解理、有不规则裂纹、中等干涉色、沿裂纹蚀变 |
| Quartz | 石英 | 无色、低突起、无解理、低干涉色、**从不蚀变**、无双晶无环带 |
| Feldspar / Plagioclase | 长石 / 斜长石 | 无色、低突起、低干涉色、**有多重双晶**、常强烈蚀变 |
| Calcite | 方解石 | **高干涉色**（沙色带绿粉调），常见碳酸盐矿物中唯一的高干涉色者 |
| Dolomite | 白云石 | 与方解石同为碳酸盐，同样具高干涉色 |
| Biotite | 黑云母 | 棕/红棕/绿棕色，强多色性，**一组完全解理**，常含 zircon 多色晕 |
| Mica | 云母 | 层状硅酸盐矿物族，含 biotite（黑云母）与 muscovite（白云母） |
| Garnet | 石榴石 | **各向同性**、高突起、等轴、无色或极淡粉色 |
| Zircon | 锆石 | 含铀的副矿物，常作为 biotite 中的微小包裹体产生多色晕 |
| Glaucophane | 蓝闪石 | 蓝片岩中的钠质角闪石，淡蓝-紫红多色性（本课不要求识别） |
| Igneous rock | 火成岩 | 由岩浆（部分熔融物质）结晶而成 |
| Sedimentary rock | 沉积岩 | 由风化产物或生物来源物质在地表层状堆积而成 |
| Metamorphic rock | 变质岩 | 先存岩石在**固态**下经热和/或压力改造而成 |
| Texture | 结构 | 岩石中晶体/颗粒的大小、形状与相互关系——**判定岩石类型的关键** |
| Interlocking crystals | 互锁晶体 | 晶体彼此嵌合无空隙，火成岩与变质岩的典型结构 |
| Preferred orientation | 优选方位 | 晶体统一朝某方向排列，变质岩的标志 |
| Foliation | 片理 | 面状的构造组构，由变形产生，变质岩的关键证据 |
| Tectonic fabric | 构造组构 | 由构造变形产生的定向排列 |
| Compositional layering | 成分层理 | 成分不同的条带，可能是被改造的原始层理（"fossil bedding"） |
| Clast | 碎屑 | 来自先存岩石的颗粒，沉积岩的基本组成 |
| Polycrystalline rock fragment | 多晶岩屑 | 由多个小晶体组成的碎屑，**沉积岩的铁证** |
| Rounding | 磨圆度 | 碎屑棱角被磨蚀的程度，指示搬运距离 |
| Sorting | 分选 | 颗粒粒度的均一程度；粒度范围宽 = 分选差 |
| Cement | 胶结物 | 沉积后从孔隙水中沉淀、把颗粒粘结起来的矿物（本例为方解石） |
| Porosity | 孔隙度 | 岩石中孔隙所占体积比例；沉积岩可能多孔，火成/变质岩通常无 |
| Vesicle | 气孔 | 岩浆中溶解气体出溶形成的"化石气泡"，**火成岩独有** |
| Phenocryst | 斑晶 | 细粒基质中的大晶体，指示两阶段冷却 |
| Groundmass | 基质 | 斑晶之间的细粒部分 |
| Porphyritic texture | 斑状结构 | 斑晶 + 细粒基质的组合结构 |
| Cumulate | 堆晶岩 | 晶体从岩浆中沉降堆积形成的火成岩（如本周的 peridotite） |
| Peridotite | 橄榄岩 | 以橄榄石为主的超基性火成岩，构成地幔主体 |
| Blueschist | 蓝片岩 | 高压低温 (HP/LT) 变质岩，形成于俯冲带，含蓝闪石 |
| Sandstone | 砂岩 | 以砂级碎屑（常为石英）组成的沉积岩 |
| Schist | 片岩 | 具强片理、富云母的中级变质岩 |
| Granite | 花岗岩 | 石英 + 长石 + 云母组成的长英质侵入岩 |
| Gabbro / Basalt | 辉长岩 / 玄武岩 | 由橄榄石、辉石、斜长石组成的基性岩（前者侵入、后者喷出） |
| Rum, Inner Hebrides | 苏格兰内赫布里底群岛 Rum 岛 | 本周 peridotite 样品 (RP / R56) 的产地，一个大型层状侵入体 |

---

## 附：本周文件清单与角色

| 文件 | 场次 | 角色 |
| --- | --- | --- |
| `Air Pollution Analysis Practical Worksheet(2).md` | Morning | 主任务书，4 个 Section 的问题（**无答案，需自行作答**） |
| `Air_Pollution_Data(5).md` (.xlsx) | Morning | 数据集，168 行 × 12 列逐小时模拟数据 |
| `simcity(1).md` (.html) | Morning | 网页版 City Air Pollution Simulator 的参数界面 |
| `wildfire_sheet_answers.md` | Morning | 野火追踪与排放计算工作表的**答案版**（含全部计算） |
| `EART11300 Semester 2 Practical Class 2_2023_questions.md` | Afternoon | 显微镜实践的问题版 + 第 5 页三大岩类属性表 |
| `EART11300 Semester 2 Practical Class 2_2023_answers.md` | Afternoon | 对应的**答案版**（含素描比例尺标注与批注） |

> **注意**：数据集的 `Day` 列（Monday–Sunday）与真实日历不符（2024-10-31 实际是星期四），但列内部自洽（Mon→Sun 连续 7 天各 24 小时）。分析时**以 `Day` 列为准**即可，不必按真实日历重新对齐。
