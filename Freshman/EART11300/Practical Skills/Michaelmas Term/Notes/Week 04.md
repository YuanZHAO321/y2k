# Week 4 — 空气质量测量与误差分析 (Measuring Air Quality and Meteorological Parameters)

> **本周材料清单**（`Michaelmas Term/Week 4/`，共 4 个 .md）
> 1. `Air Quality & Practical Intro_2024-25_GA_DK(1).md` — 实践导入幻灯片（22 张，含讲者备注 Notes）
> 2. `Measuring Air Quality_2024-25_GA_DK.md` — 主讲义 / 实践手册（docx 转写）
> 3. `Measuring Air Quality-ASSIGNMENT_INFORMATION_2023-24_GA(1).md` — 作业说明与指令（PDF 转写，共 9 题）
> 4. `Air_Quality_Practical_Assessment_Data_2024(4).md` — 评估用数据集（xlsx 转写，1359 行表格）
>
> 授课人：**Grant Allen (GA)** 与 **Doğuşhan Kılıç (DK)**（曼彻斯特大学大气科学组）。
> 实践地点：曼大 **G12** 教室（导入 + 数据检查）与 **Brunswick Park**（野外测量）。

---

## 一、本周主题

本周训练的是**大气/环境测量的野外数据采集与误差分析技能**：用手持气象仪 **Kestrel** 在 Brunswick Park 实地记录温度、气压、相对湿度、风速与风向，再与公园内一台**高精度参考气象站 (reference weather station)** 的同步数据对比，用 Excel 做**均值 (mean)、标准差 (standard deviation)、标准误 (standard error)** 与**校准偏移量 (calibration offset)** 的计算，从而分辨**系统误差 (systematic error)**、**随机误差 (random error)** 与**代表性误差 (representativity error)**。

在全课 10 周（Week 1、2、4、5、6、7、8、9、10、11）中，本周是**材料量最大的一周（约 3.1 万词，占全课 62%）**，也是第一次完整走通「野外采样 → 数据导出 → 统计分析 → 结果判读 → 在线测验」的整条科研流程。本周建立的误差概念（尤其"真实变率 vs 仪器噪声"的区分）是后续所有野外与实验课程的基础。

**关键背景说明**：本周的评估形式是 **Blackboard 在线测验 (online test)**，属于**形成性 (formative) 练习**——**不计入学位成绩**，无时间限制，可无限次重做，提交后立即给出反馈与正确答案。但**小组的 Kestrel 数据必须按时提交**给 `dogushan.kilic@manchester.ac.uk`（这一步是有截止日期的硬性要求）。

---

## 二、核心概念

### 2.1 空气污染的历史起点：1952 年伦敦大烟雾 (London's Great Smog of 1952)

这是本周导入幻灯片开篇的案例，也是现代空气质量立法的起点。

| 要素 | 内容 |
|---|---|
| **时间** | 1952 年 12 月 5 日 – 12 月 9 日 |
| **成因 (Cause)** | 低品质**煤炭 (coal)** 在家庭与电厂燃烧（domestic/industrial heating）+ **反气旋条件 (anticyclonic conditions)**：寒冷、无风、逆温封盖 |
| **化学过程** | 煤燃烧产生的**颗粒物 (particulate matter)**、**烟尘 (soot)** 与**二氧化硫 (sulphur dioxide, SO₂)** 与大气水汽混合，形成浓稠有毒的雾 |
| **健康影响** | 估计造成 **4,000 – 12,000 人死亡**，死因为**支气管炎 (bronchitis)**、**肺炎 (pneumonia)** 等呼吸道疾病 |
| **社会影响** | 能见度骤降、烟雾渗入室内；铁路、空中交通甚至救护车停摆；家畜与野生动物受害 |
| **政策后果** | 直接推动英国 **1956 年《清洁空气法》(Clean Air Act 1956)**，设立**烟控区 (smoke control areas)**，限制城市燃煤 |

> **为什么重要**：这是"环境与公共卫生政策的转折点"，证明空气污染可以致命，也是"监测 → 证据 → 立法"这一链条的典范。理解它，才能理解为什么本课要花整整一周训练"如何做出可信的测量"。

**⚠ 关键机理**：**反气旋 (anticyclone)** 下沉气流造成**逆温层 (temperature inversion)**，把污染物封在近地面薄层内无法垂直扩散；同时无风使水平输送几乎为零。**气象条件本身不产生污染物，但决定污染物的累积浓度**——这正是讲义 §2b 强调的"meteorology affects how long pollutants stay around and how they are dispersed"。

### 2.2 当代三大关注污染物：NOx、PM、O₃

幻灯片 Slide 4 给出的核心表格（原文为合并单元格，此处已拆分整理）：

| 污染物 | 来源 (Sources) | 健康影响 (Health Impacts) | 环境影响 (Environmental Impacts) |
|---|---|---|---|
| **氮氧化物 (Nitrogen Oxides, NOx)** | 化石燃料燃烧（交通、工业）；**闪电 (lightning)**；**土壤 (soils)** | 呼吸系统影响 (respiratory impacts)；心血管影响 (cardiovascular impacts) | **酸雨 (acid rain)** — 损害森林、湖泊等生态系统；在城镇上空形成**烟雾 (smog)** |
| **颗粒物 (Particulate Matter, PM)** | 化石燃料燃烧（交通、工业）；**农业 (agriculture)**；**海盐飞沫 (sea-spray)**、沙尘与火山灰 (dust & ash) | 呼吸系统影响 | 能见度下降（形成**霾 haze**）；可作为某些**病原体 (pathogens)** 与有害物质的**载体 (carriers)** |
| **臭氧 (Ozone, O₃)** | **二次污染物 (secondary pollutant)** — NOx 与**挥发性有机物 (volatile organic compounds, VOCs)** 在**阳光 (sunlight)** 下反应生成 | 呼吸系统影响；加重已有呼吸系统疾病 | **强氧化剂 (powerful oxidant)** — 损害植被与历史文化遗产、影响作物产量；形成烟雾 |

**讲者备注要点**：
- 这三者是当前城市公众最关心的污染物。
- **二次污染物 (secondary pollutants)** 是在大气中由**一次污染物 (primary pollutants)** 反应生成的，可以是**气态 (gas)** 也可以是**气溶胶 (aerosol)**。

> **概念区分（重点）**
> - **一次污染物 (primary pollutant)**：直接从源头排入大气（如 NO、SO₂、一次 PM、CO）。
> - **二次污染物 (secondary pollutant)**：在大气中经化学反应生成（如 **O₃**、**硝酸盐/硫酸盐气溶胶**、二次有机气溶胶）。
> - **NOx = NO + NO₂**。注意 NOx 有一部分是**天然来源**（闪电固氮、土壤微生物过程），不全是人为的——这是易被忽略的点。

### 2.3 空气污染的健康与经济负担（Slide 5 数据）

| 统计口径 | 数值 |
|---|---|
| **全球早逝人数 (premature deaths), 2012** | **700 万人 / 年**；其中 **400 万**归因于**室内空气污染 (indoor air pollution)**（讲者备注） |
| **WHO 2019 排名** | 空气污染列为 **2019 年全球健康十大威胁之一** |
| **英国** | 对英国人口而言是**最大的环境健康压力源 (largest environmental health stressor)** |
| **英国早逝人数** | **40,000 人 / 年** |
| **英国经济代价** | **£10–20 亿…实为 £10–20 billion / 年**（原文 "£10-£20 billion/year"，即每年 100 亿–200 亿英镑） |

**为什么必须精确测量与监测（Slide 5 的三条论证）**：
1. **深化对影响空气质量的过程与污染物的理解**——尤其在车辆与工业技术不断变化的背景下（如柴油车占比变化、电动化）。
2. **健康与环境影响重大**——测量结果直接关系到健康指南。
3. **评估空气质量干预政策的有效性 (assess the effectiveness of air quality intervention policies)**——没有可靠基线与持续监测，就无法判断政策（如低排放区 LEZ/ULEZ）是否有效。

### 2.4 误差理论：三类误差（本周理论核心）

讲义 §2a 与幻灯片 Slide 6–16 共同构成本周的理论骨架。核心命题：

> **"Measurements must be as accurate as possible, but we can never avoid errors and uncertainties in what we measure! All measurements need to have error estimates so we know how confident we can be in our analysis and interpretation."**
> （测量要尽可能准确，但误差与不确定性永远无法避免；所有测量都必须带误差估计，才能知道我们对分析与解释有多少信心。）

#### (1) 系统误差 (Systematic error)

**定义**：**可重复的 (reproducible)** 误差，以**同样的方式影响你所有的测量**；对应仪器的**偏差 (bias)** 或实验设计上的缺陷。

**典型成因**：
- **观测误差 (observational error)**
- **仪器校准不完善 (imperfect instrument calibration)**
- **环境干扰 (environmental interference)** — 仪器对其他变量（如温度、湿度）的敏感性。例：温度变化影响某气体浓度测量的准确度。

**三种简单形态（Slide 9）**：

| 形态 | 描述 | 表现 |
|---|---|---|
| **1) 零点误差 (Zero error)** | 忘记**去皮/归零 (tare or zero)** 天平 | 所有测量都偏离同一固定量，即存在一个**偏移量 (offset)** |
| **2) 标度误差 (Scale error)** | 仪器未正确校准 | 通过**与标准 (standard) 对比**来修正 |
| **3) 仪器漂移 (Instrument drift)** | 连续读数随时间**持续变低或变高** | 可由气象条件（温度、湿度）变化引起；传感器随时间老化亦然，需**定期重新校准 (regular recalibration)** |

**处理方法（Slide 10）**：
1. 确保仪器已做**零点偏移修正 (corrected for zero off-sets)**；
2. **定期校准 (regular calibrations)**；
3. **与标准值比对 (comparing values against standards)**。

**⚠ 危险性**：系统误差会造成**数据的长期偏差 (long-term biases)**，导致对空气质量趋势得出错误结论——而且**取更多平均也消不掉**（因为它不是随机的）。

#### (2) 随机误差 (Random error / non-systematic error)

**定义**：使**一次测量与下一次测量略有不同**的、由实验过程中**不可预测的变化**引起的误差；通常称为**噪声 (noise)**。

**典型成因**：
- **仪器噪声 (instrumental noise)**
- **被测量对象本身的真实变化 (real variations in what is being measured)**
- 讲者备注补充：**环境噪声 (environmental noise)** — 温度突变、湿度尖峰；**电源波动 (power supply fluctuations)** — 电压波动影响传感器性能。

**统计性质（Slide 13，核心）**：
- 随机误差**向正负两个方向偏离均值的可能性相同**；
- 服从**正态/高斯分布 (normal Gaussian distribution)**，由**均值 (mean)** 与**标准差 (standard deviation)** 两个参数刻画；
  - **均值 = 中心值/平均值**；
  - **标准差 = 数据点围绕均值的离散程度 (spread)**；
- 正态分布中，**高于均值与低于均值的测量数量相等**。

**大数定律 (Law of large numbers)**（讲者备注）：样本数增加会**降低对总体均值（最可能结果）估计的不确定性**。

**处理方法（Slide 15）**：
- 随机误差**总是存在**；
- **无法预测，但可以被测量**；
- 测量方法：取**大量数据点（典型 >100 个）并求平均**；
- 这样既能**量化随机误差**（用标准差），又能帮助**估计真实均值**。

> **📌 讲义 §2a 的原文精确表述**："usually have a Gaussian distribution around some mean. This means it is possible to quantify the error as a standard deviation by examining the distribution of many separate measurements (usually >100 to ensure a meaningful statistical representation)."
> ——**">100 个测量"这个阈值是本周的考点数字**。

#### (3) 代表性误差 (Representativity error)

**定义**：由于**调查/实验设计的缺陷**，使得"我们以为自己在测什么"的**假设失效**。

**经典问句（讲义与幻灯片各给一例）**：
- 讲义：**"如果我们在半山腰测温度，山顶的温度和它一样吗？我们的测量对周边区域有多大代表性？"**
- 幻灯片 Slide 16：**"某一点测到的风，和 100 米外测到的风是同一个吗？"**

**做一次好测量时必须自问的两个问题（Slide 16）**：
1. **你自己是否在做任何可能影响测量的事？**（Are you doing anything which could be affecting the measurements?）
2. **周围环境是否存在任何外部因素在影响测量？**（buildings, trees, 遮挡, 热源, 人群…）

**这类误差在野外测量中"极其重要"**（原文 "very important for field measurements"）。

#### (4) 第四类：人为误差 (Human error)

讲义单独强调（幻灯片 Slide 6 备注则把它归入 Representativity 之下）：

- 必须**勤勉核查测量值**，在**笔记本记录**与**录入电脑**两个环节都要格外小心；
- **经典反面案例**：**如果你在仪器旁边呼吸，测到的是你呼出气体的湿度，而不是大气的湿度！**（This may invalidate the data because we would be measuring the humidity of our breath and not the atmosphere!）
- 人为误差**难以量化**，但解释结果时必须放在心上；
- 讲义给出的思辨题：如果想知道山顶温度但只能到半山腰，我们对数据解释的**置信度 (confidence)** 应如何表述？**这会是低估还是高估？为什么？**
  - （标准思路：对流层内温度随高度下降，**山顶实际更冷**，因此半山腰的读数是山顶温度的**高估 (over-estimate)**；反过来说，若把它当作山顶值，就"高估了温度"。回答时必须写出**递减率**这一物理依据。）

### 2.5 一个昂贵的错误：NASA 火星气候轨道器 (Mars Climate Orbiter, 1999)

Slide 7 的警示案例：

- 1999 年 NASA 的 **Mars Climate Orbiter** 因**单位换算错误 (unit conversion error)** 而损失；
- 一个团队用**公制 (metric)**，单位为**牛顿·秒 (newton-seconds)**；另一个团队用**英制 (imperial)**，单位为**磅·秒 (pound-seconds)**，来计算航天器轨道；
- 结果航天器进入火星大气层**过低**，被烧毁；
- 任务损失 **1.25 亿美元 ($125 million)**。

**讲者备注给出的类比**："即使是微小的数据处理或设备设置错误，也可能造成巨大后果。在空气质量监测中，**仪器校准错误或使用了错误的设置**，会导致污染读数不准，进而影响健康指南或政策决策。"

> **本周的方法论口号**：*Errors are part of the game but some of them can be costly.*（误差是游戏的一部分，但有些误差代价高昂。）

### 2.6 空气质量与气象的耦合（讲义 §2b）

> "Air quality in large urban areas like Manchester is not only affected by the emissions coming from things like vehicles and industry. The meteorology in these areas can affect **how long these air pollutants stay around for** in the air, and **how they are dispersed** in and around the surrounding area."

**必须理解的因果链**：

| 气象要素 | 对污染物的作用 |
|---|---|
| **风速 (wind speed)** | 决定**稀释/通风**速率；低风速 → 污染物累积 |
| **风向 (wind direction)** | 决定污染来自哪个源区；因此**风向按"风从哪里来"记录** |
| **温度 (temperature)** / 逆温 | 逆温层抑制垂直混合 → 污染物被困在近地面 |
| **相对湿度 (relative humidity)** | 影响气溶胶**吸湿增长 (hygroscopic growth)**、雾霾形成与能见度 |
| **气压 (pressure)** | 高压/反气旋 = 下沉、静稳、少雨 → 污染累积（1952 伦敦烟雾即此） |
| **太阳辐射 (sunlight)** | 驱动**光化学反应**生成 O₃ |

讲义要求：**"我们必须意识到这些效应，以及它们会如何影响我们所测数据的代表性 (representivity)。"**——即气象条件不仅是被测对象，也是解释测量结果代表性的依据。

---

## 三、公式与图表

### 3.1 本周必须掌握的三个统计量

设一组测量值 $x_1, x_2, \dots, x_n$：

**(1) 均值 / 平均值 (Mean, average)**

$$\bar{x} = \frac{1}{n}\sum_{i=1}^{n} x_i$$

- 含义：分布的**中心值**；对随机误差取平均可逼近**真值 (true value)**。
- **Excel**：`=AVERAGE(范围)`

**(2) 标准差 (Standard deviation, SD, σ / s)**

样本标准差（Excel 默认，n−1 分母，**Bessel 校正**）：
$$s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2}$$

总体标准差：
$$\sigma = \sqrt{\frac{1}{n}\sum_{i=1}^{n}(x_i-\bar{x})^2}$$

- **含义（作业 Q4 原文）**："This gives an indication of the **combined instrumental noise error (random error) and the natural variability in the atmosphere** at the location where the data was collected."
  → **标准差 = 仪器随机噪声 + 大气真实变率，二者混在一起**。这是本周最重要的一句判读语。
- **Excel**：`=STDEV.S(范围)`（样本，推荐）或 `=STDEV(范围)`（旧版同义）；`=STDEV.P(范围)` 为总体。
- 当 n 很大（本周 n = 271 与 1353）时两者差异可忽略（差异因子 $\sqrt{(n-1)/n}$，n=271 时为 0.9982）。

**(3) 标准误 (Standard error of the mean, SE / SEM)**

$$SE = \frac{s}{\sqrt{n}}$$

- 含义：**均值本身的不确定度**——不是数据的离散度，而是"我把这批数据的均值当作真值时，能有多准"。
- 随 $n$ 增大按 $1/\sqrt{n}$ 收缩 → 这正是"取 >100 个点求平均"的数学依据（**大数定律**的定量版）。
- **Excel**：`=STDEV.S(范围)/SQRT(COUNT(范围))`
  也可写作 `=STDEV.S(A2:A272)/SQRT(COUNTA(A2:A272))`。

**(4) 校准偏移量 (Calibration offset)** — 本周的关键"新公式"

$$\text{Offset} = \bar{x}_{\text{Kestrel}} - \bar{x}_{\text{Reference}}\qquad\text{（作业 PDF Q3 的定义）}$$

$$\text{Offset} = \bar{x}_{\text{Reference}} - \bar{x}_{\text{Kestrel}}\qquad\text{（幻灯片 Slide 20 与讲义 §Experiment 2 的定义）}$$

**⚠ 三份材料的符号约定不一致，务必看清题目怎么问**（详见第六节易错点）。

**校准的应用**：
$$x_{\text{calibrated}} = x_{\text{measured}} - \text{Offset}_{(\text{Kestrel}-\text{Ref})}$$
讲义原文："Subtracting the difference of these two values from your measured data will **calibrate your measurements to those of the high-precision instrument**. This is a very common way to **remove bias error** from scientific measurements."
→ **减去偏移量 = 去除系统偏差**，这是科学测量中最常见的去偏方法。

**(5) 变率差 (Difference in variability)** — 作业 Q6

$$\Delta s = s_{\text{Kestrel}} - s_{\text{Reference}}$$

- 判读：由于**参考气象站预期比 Kestrel 手持仪更准确**，$\Delta s > 0$ 说明 Kestrel 的额外离散来自**更大的仪器噪声**（也可能来自采样位置的真实差异，见第六节）。

### 3.2 单位与换算

**气象量单位**

| 量 | 常用单位 | 换算 |
|---|---|---|
| **气压 (pressure)** | **hPa**（作业 PDF 用）/ **mbar**（数据集列头用）/ Pa / atm | **1 hPa = 1 mbar = 100 Pa**；1 atm = 1013.25 hPa；1 bar = 1000 hPa |
| **温度 (temperature)** | **°C**（本周统一用摄氏度）/ K / °F | $T[\text{K}] = T[°\text{C}] + 273.15$；$T[°\text{F}] = \frac{9}{5}T[°\text{C}] + 32$ |
| **相对湿度 (relative humidity, RH)** | **%**（无量纲百分数） | $RH = \dfrac{e}{e_s(T)}\times 100\%$，$e$ = 水汽压，$e_s$ = 该温度下的饱和水汽压 |
| **风速 (wind speed)** | m/s / km/h / knots / mph | 1 m/s = 3.6 km/h ≈ 1.944 knots ≈ 2.237 mph |
| **风向 (wind direction)** | 度 (°)，**风的来向** | 0°/360° = 北风(N)，90° = 东风(E)，180° = 南风(S)，270° = 西风(W) |

> **⚠ 数据集与作业说明的单位标注不一致但物理等价**：数据集列头写 `Pressure (mbar)`，作业 PDF 第 9 题写 "pressure (in units of **hPa**)"。**1 mbar ≡ 1 hPa，数值完全相同，无需换算**——但答题时要按题目要求的单位名报出。

**为什么 RH 与 T 反相关（本周数据必用的物理）**：
饱和水汽压 $e_s$ 随温度**指数增长**（Clausius–Clapeyron 关系，约 **每升温 1 °C，$e_s$ 增加约 7%**）。若空气中**绝对水汽量 $e$ 不变**而温度升高，则 $RH = e/e_s$ **下降**。
→ 因此本周 Kestrel 数据中"**温度上升、RH 同步下降**"完全符合物理，是**同一个原因（仪器被加热）**造成的两个表现。

**污染物浓度单位换算（背景补充，非本周材料要求但属课程通识）**

体积混合比（**ppb, parts per billion**；**ppm, parts per million**）与质量浓度（**µg/m³**）互换：

$$C\,[\mu g/m^3] = C\,[\text{ppb}] \times \frac{M}{V_m}$$

其中 $M$ 为**摩尔质量 (g/mol)**，$V_m$ 为**摩尔体积 (L/mol)**：25 °C、1 atm 时 $V_m = 24.45$ L/mol；20 °C、1 atm 时 $V_m = 24.055$ L/mol。

| 气体 | M (g/mol) | 1 ppb ≈ ? µg/m³ (25 °C) |
|---|---|---|
| **NO₂** | 46.01 | 1.88 |
| **NO** | 30.01 | 1.23 |
| **O₃** | 48.00 | 1.96 |
| **SO₂** | 64.06 | 2.62 |
| **CO** | 28.01 | 1.15 |

> **注意**：**PM（颗粒物）只用 µg/m³**，因为它是混合物、无单一分子量，不能用 ppb 表达。

**空气质量标准限值（背景补充，便于理解"为什么要精确测量"）**

| 污染物 | WHO 2021 空气质量指导值 (AQG) | 英国空气质量目标 (UK objective) |
|---|---|---|
| **PM2.5** | 年均 5 µg/m³；24 h 15 µg/m³ | 年均 20 µg/m³（英格兰目标 2040 年降至 10） |
| **PM10** | 年均 15 µg/m³；24 h 45 µg/m³ | 年均 40 µg/m³；24 h 50 µg/m³（每年不超 35 次） |
| **NO₂** | 年均 10 µg/m³；24 h 25 µg/m³ | 年均 40 µg/m³；1 h 200 µg/m³（每年不超 18 次） |
| **O₃** | 高峰季 8 h 60 µg/m³；日最大 8 h 100 µg/m³ | 日最大 8 h 100 µg/m³（每年不超 10 次） |
| **SO₂** | 24 h 40 µg/m³ | 1 h 350 µg/m³；24 h 125 µg/m³ |

> 这张表说明：**限值与实测值往往只差几个 µg/m³**，因此**仪器偏差（系统误差）足以让一个地点"合规"或"超标"**——这正是本周做校准的现实意义。

### 3.3 数据可视化方式

本周材料明确或隐含要求的图表：

| 图型 | 用途 | 要点 |
|---|---|---|
| **时间序列图 (time series)** | Kestrel 与参考站的 T / P / RH 随时间变化，**叠在同一张图上** | 横轴统一为 Date-Time；两条线之间的**恒定竖直间距**即为系统偏移，**发散/交叉**则说明存在漂移或代表性差异 |
| **直方图 (histogram)** | 展示测量值的分布，检验是否近似**高斯分布** | 幻灯片 Slide 13/14 展示的"钟形曲线"；正态分布应左右对称，均值处最高 |
| **散点图 (scatter plot) + 回归** | Kestrel 值 vs 参考站值 | 截距 = 零点偏移；斜率 ≠ 1 = 标度误差；R² = 一致性 |
| **误差棒 (error bars)** | 在均值柱状/点图上标注 ± SD 或 ± SE | **必须说明用的是 SD 还是 SE**——这是报告规范 |
| **风玫瑰图 (wind rose)** | 风向频率分布 | 与污染来源方位结合判读 |

**Excel 操作提示**：作业说明指出，Blackboard 的 "**Assignment Information and Help Sheets**" 文件夹中有一段 **YouTube 视频**，讲解如何用 Excel 计算**均值、标准差与标准误**。"Please watch that video if you get stuck."

---

## 四、课堂补充

本课**无 lecture 也无转写录音**，但导入幻灯片带有大量 **Notes（讲者备注）**，这些是口头补充的书面化，已在第二节中逐条并入。此处集中记录**未能归入其他章节的口吻提示与流程性说明**：

**当天流程（Slide 2 Outline）**
1. **实践课程介绍**（在 **G12** 教室）
2. **组建研究小组 (forming of the research teams)**（G12）
3. **设置手持监测仪 (setting up the hand-held monitors)**（G12）
4. **在 Brunswick Park 采集气象数据**
5. **数据检查 (data check)** — **回到 G12！**（原文特意加了感叹号，说明这一步不能跳过：当场确认数据导出成功）

**幻灯片 Slide 22 的地图**：Brunswick Park 地图上标注了 **6 个小组位置 A、B、C、D、E、F**，以及 **RS = Reference Station（参考气象站）** 的位置。位置分散是刻意设计的——**不同组测到不同结果，正是"代表性误差"的现场演示**。

**Slide 21**：Kestrel LiNK app 界面截图（原文件为图片，转写后无文字内容）。

**教师口吻的关键提醒**（散见各处）：
- "as scientists, **we can't always rely on our instruments working**. **Fieldwork is all about making notes** – recording our data manually is advisable, should our instruments not work properly."（做野外工作的本质就是记笔记；仪器随时可能出问题，手记是保险。）
- "This is important – it will mean that you have plenty of data points to use in your analysis, **if there are technical issues with the Kestrel**."（手记的目的：Kestrel 自动记录/导出出问题时的备份。）
- **"Make sure that your Kestrel and phone are kept in close proximity to each other (within 5 m). If not, Bluetooth connectivity may be lost and you may lose your data."**（手机与 Kestrel 保持 5 米内，否则蓝牙断开丢数据。）
- **"You should work individually when answering the questions in the online test – you should not work as a group."**（在线测验必须独立完成，不得组队。）

**作业说明结尾的学习目标陈述（极重要，是本周的"思想收尾"）**：

> "At the end of this assignment, you should be able to understand **the sources of random error in any scientific measurement dataset**, as well as **the sources of variability in the real atmosphere**, noting that **it can sometimes be difficult to distinguish between them**. In measurement science, the way to separate these two effects (one being a **real change** and the other being due to **instrumental uncertainty**) is to **calibrate instruments in controlled conditions** (e.g. in a laboratory where the temperature, pressure and humidity is kept constant). If they are held constant, then we can be sure that **any variability we measure in those controlled conditions represents the instrumental random error alone**. This would then allow us to separate the natural variability (in a real and changing atmosphere) from the instrumental uncertainty (random error) when we conduct measurements in the field."

**中文要义**：野外测到的标准差 = 仪器随机误差 + 大气真实变率，**两者在野外无法分离**。分离的唯一办法是**把仪器放进受控环境（实验室，T/P/RH 恒定）标定**——此时测到的全部变率就**只是仪器噪声**；有了这个"仪器噪声基准"，才能把野外测到的总变率减去它，得到大气的真实变率。**这是本周最高层次的方法论结论，极可能作为简答/讨论考点。**

---

## 五、Practical 要点

### 5.1 实践目的（讲义 §1 Aims）

> - To become familiar with the **different types and sources of error** associated with atmospheric measurement data.
> - To apply this knowledge to conduct a **simple statistical and error analysis** on measured atmospheric data.

即：**(a) 认识大气测量数据的误差类型与来源；(b) 把这些知识用到实测数据的统计与误差分析上。**

作业说明 PDF 补充目的："The aim of this assignment is to **collect meteorological data and examine it using statistical methods and error analyses**. You will **interpret and discuss** the data collected during the practical."

### 5.2 仪器

**(1) Kestrel 手持气象站 (Kestrel handheld weather station)**

| 项目 | 说明 |
|---|---|
| **测量参数** | 温度 (temperature)、气压 (barometric pressure)、相对湿度 (relative humidity)、**风速 (wind speed)**、**风向 (wind direction)** |
| **读数查看** | 用 Kestrel 上的 **UP/DOWN 箭头键**在各参数之间切换（App 收不到数据时用这个手动读数） |
| **风速测量部件** | 顶部的**小螺旋桨叫叶轮 (impeller)**；**必须取下塑料保护盖 (plastic cover)，让叶轮暴露在风中** |
| **数据记录** | 自动记录（讲义：**每 5 秒一次**；幻灯片：每 1 秒一次——见易错点 6.1） |
| **配套 App** | **Kestrel LiNK**（须在实践课**之前**装好在手机上），经**蓝牙 (Bluetooth)** 连接 |
| **连接距离要求** | **Kestrel 与手机保持 5 m 以内**，否则蓝牙断开、数据丢失 |
| **课后处理** | 用 App 导出数据 → **从手机把数据文件 email 给自己** → **关闭 Kestrel** → **归还给工作人员** |

**(2) 高精度参考气象站 (standard high-precision reference weather station)**

| 项目 | 说明 |
|---|---|
| **位置** | Brunswick Park 内，地图上标为 **RS**；实践开始时由老师指明位置 |
| **测量参数** | 温度、气压、相对湿度（**不含风**，因为对比只针对这三项） |
| **采样频率** | 数据集显示为**每 1 秒一次** |
| **角色** | 作为**标准/参考 (standard/reference)**，被认为**比 Kestrel 手持仪更准确**；用于求**校准偏移量** |
| **数据获取** | 实践结束后在 **Blackboard** 上发布 |

### 5.3 准备阶段 (Preparation)

**分组与领取**：
1. **自行分组，每组 6–8 人**（幻灯片 Slide 17）。
2. 向工作人员**领取一台 Kestrel 和一张地图**。
3. 每组分配一个字母 **A / B / C / D / E / F**，对应地图上的**测量位置**。
4. 与组员一起前往你们的测量地点，**分配角色**。

**必须分配的 4 个角色（Slide 17，考点）**：

| 角色 | 职责 |
|---|---|
| **仪器负责人** | 谁负责操作 Kestrel |
| **App 连接负责人** | 谁用自己的手机把 Kestrel 连到 **Kestrel LiNK** app |
| **手动记录员** | 谁负责手工抄录测量值 |
| **环境观察员** | 谁负责记录周围环境与条件（**建筑物、风、树木**等） |

**开始前的现场笔记清单（讲义 Experiment 1）**：
- Kestrel 是否已连上 Kestrel LiNK app？
- **附近有没有建筑物或树木？**（Are there any buildings or trees nearby?）
- **今天天气如何？**（What is the weather like today?）
- **能否判断风从哪里来？**（Can you establish where the wind is coming from?）

> **为什么要记这些**：这些是解释**代表性误差**的唯一依据。数据分析时若发现你的组与参考站差异异常大，只有靠这些现场笔记才能给出物理解释（例如"位于建筑物背风侧"、"在树荫下"）。

### 5.4 Experiment 1 — 代表性误差 (Representativity Error)

**目的**：让 6 个组在**不同地点**同时测量，暴露"同一公园内不同位置读数不同"这一现象，从而理解代表性误差。

**操作步骤（以讲义为准）**：
1. 各组前往自己的地点。
2. **每人在自己的位置测量 15 分钟**（幻灯片版本为 **25 分钟**，见 6.1）。
3. Kestrel **每 5 秒自动记录一次**气象数据。
4. **同时，每 2 分钟手工记录一次**：**气压、温度、相对湿度、风速、风向**（幻灯片版本为每分钟手记温压湿）。
5. 手记方法：用 Kestrel 的 **UP/DOWN 箭头**切换参数读数。

**风测量的操作要领（讲义原文，重点考点）**：

1. **暴露叶轮**：取下顶部塑料保护盖，让 **impeller** 暴露在风中。
2. **测风向**：
   - **把 Kestrel 正对着风的来向**（hold the Kestrel pointing straight into the wind）。
   - 风向不稳定时，需要找到"**最佳估计 (best guess)**"，方法有三：
     - **摘一片草叶或树叶，松手看它往哪飘**；
     - **举起围巾或一段绳子**；
     - **观察附近的植物或树木**作为指示。
   - 确定大致方向后，**与周围建筑物比对并记下**。例："**the wind was at 45 degrees to Road X or Path Y**"（风与 X 路成 45 度）。
   - **事后再看地图，把它换算成罗盘方位 (compass direction)**。
3. **⚠ 风向的定义约定（必考）**：
   > "the wind direction is generally noted as **where the wind is coming from**. This is because when you are looking at weather and air pollution, you tend to be **more interested in where the pollution or air mass is coming from**."
   → **风向 = 风的来向**，因为研究污染时关心的是**气团/污染物从哪来**。所以"西风"指风**从西边吹来**。

### 5.5 Experiment 2 — 系统误差 (Systematic Error)

**目的**：用高精度参考站给手持仪做**现场比对校准 (co-location calibration)**，量化并消除系统偏差。

**原理**：参考站与各组**同一时段、不同地点**同步测量。将两者均值相减得到**偏移量 (offset)**，即系统误差；再从实测数据中减去该偏移量，就把你的测量"校准到高精度仪器的标尺上"。

**讲义原文步骤**：
> "You will calculate the offset (i.e. the systematic error) by **subtracting your measured mean temperature, pressure and relative humidity from the corresponding means calculated from the reference weather station data**. Subtracting the difference of these two values from your measured data will **calibrate your measurements** to those of the high-precision instrument. This is a very common way to **remove bias error** from scientific measurements."

**幻灯片 Slide 20 的 5 步版本**：
| 步骤 | 内容 |
|---|---|
| **Step 1** | 每组**一名成员**在实践后**尽快**把本组 Kestrel 数据（**Excel 电子表格**）email 给 **dogushan.kilic@manchester.ac.uk** |
| **Step 2** | **一个组的 Kestrel 数据 + 参考气象站数据**会发布到 **Blackboard**，供**个人**分析 |
| **Step 3** | 计算 Kestrel 与参考站各自的**气压、温度、相对湿度**的**均值与标准差** |
| **Step 4** | 计算两者之差（= **calibration offset**）：**用参考站的均值减去 Kestrel 的均值** |
| **Step 5** | 拿到这些值后，去 Blackboard 完成**在线测验**；**即时反馈**；**形成性 (formative)，不计入学位成绩** |

### 5.6 实践结束时的收尾清单（讲义 "At the end of the practical"）

1. **用手机上的 Kestrel LiNK app 导出记录的数据**（具体方法见 Blackboard 上的 "Connecting and configuring the Kestrel LiNK app" 资源）；**可以从手机把 Kestrel 数据文件 email 给自己**。
2. **务必关闭 Kestrel**（turn your Kestrel off）。
3. **把 Kestrel 归还给工作人员**。
4. （Slide 2）**回到 G12 做数据检查**。

### 5.7 数据准备 (Preparing your data for analysis)

导出的 Excel 表里有 Kestrel 记录的**全部气象字段**，但**只需要以下 4 列**：

> **Date-Time, Temperature, Relative Humidity & Barometric Pressure**

（即：**日期时间、温度、相对湿度、大气压**；**风速与风向不参与在线测验的统计分析**——它们只用于现场笔记与代表性讨论。）

**提交要求（硬性）**：
- 把本组的**已校准数据 (calibrated data)**，**连同你所应用的校准偏移量 (including the calibration offsets that you applied)**，录入 Blackboard 上的 **measurement entry spreadsheet（测量录入表）**；
- 在 **Blackboard 公布的截止日期前**发送到 **dogushan.kilic@manchester.ac.uk**；
- Doğuşhan 会把所有数据**合并成一个表格**，再放回 Blackboard 供大家分析、答在线测验。

### 5.8 评估作业：在线测验的 9 道题（作业说明 PDF 全文要点）

**性质与规则**：
- **个人独立完成**（work individually）；
- **无时间限制 (not time-limited)**；
- **可无限次重做 (repeat as many times as you like)**；
- **提交后立即获得自动反馈 (instant automatic feedback)**，并给出正确答案与算法；
- **不计入学位成绩 (NOT assessed / does not count towards your degree mark)** — **形成性练习**；
- 测验还包含**关于如何解释所算结果的多选题 (multiple choice questions about how to interpret the results)**；
- 位置：air quality practical 文件夹下的 "**Assessment and Feedback – online test**" 子文件夹。

**数据来源**：
> "In the '**Calibrated Data**' folder within the air quality practical folder you will find a data file (an Excel Spreadsheet) containing **calibrated kestrel data** and data from the **high-quality weather station** placed in Brunswick Park. **This may not be the same data as the data collected by your group.** Please use this data for the analysis."
→ **⚠ 必须用官方发布的这份数据做分析，它可能不是你们组自己测的数据。**

**九道题逐条**：

| 题号 | 要求 | Excel 做法 |
|---|---|---|
| **Q1** | 计算 **Kestrel 温度**（°C）的**均值** | `=AVERAGE(Kestrel温度列)` |
| **Q2** | 计算 **参考气象站温度**（°C）的**均值** | `=AVERAGE(参考站温度列)` |
| **Q3** | **偏移量 = Q1 − Q2**（用 Q1 减 Q2）。**并思考：什么样的物理环境原因与仪器原因可能造成这个差异？** | `=Q1-Q2` |
| **Q4** | 计算 **Kestrel 温度**的**标准差**。题干说明：这反映了**仪器噪声（随机误差）与采样地点大气自然变率的合成** | `=STDEV.S(...)` |
| **Q5** | 计算 **参考站温度**的**标准差** | `=STDEV.S(...)` |
| **Q6** | **变率差 = Q4 − Q5**。**并思考：考虑到参考气象站预期比 Kestrel 手持仪更准确，什么仪器原因会造成这个差异？** | `=Q4-Q5` |
| **Q7** | 计算 **Kestrel 温度**的**标准误** | `=STDEV.S(...)/SQRT(COUNT(...))` |
| **Q8** | 计算 **参考站温度**的**标准误** | 同上 |
| **Q9** | **对气压（hPa）与相对湿度（%）重复 Q1–Q8 的全部步骤**，并记录答案 | 共 3 参数 × 8 题 = **24 个数值** |

**⚠ Q9 意味着实际要算的是 24 个数**：温度、气压、湿度各 8 个（2 个均值、1 个偏移、2 个标准差、1 个变率差、2 个标准误）。

**帮助资源**：
- Blackboard "**Assignment Information and Help Sheets**" 文件夹里有一段 **YouTube 视频**，讲 Excel 计算 mean / SD / SE；
- 讲义 §4 末尾："Further guidance on how to answer the questions is provided in the Assignment Information and help sheets tab on Blackboard."

### 5.9 数据集结构说明（`Air_Quality_Practical_Assessment_Data_2024(4).md`）

**文件形态**：原为 xlsx，仅 **Sheet1** 一个工作表，转写后是一张 **1359 行的 Markdown 表格**（含 3 行表头 + 数据行 + 末尾 3 行空的汇总标签行）。

**列结构（10 列，中间用两个空列隔开两组数据）**：

| 列号 | 分组 | 列名 | 说明 |
|---|---|---|---|
| 1 | **Reference Station（参考气象站）** | `Date-time` | 格式："**Thu 17 October 2024 10:46:27**"（英文星期 + 日 月 年 + 时:分:秒） |
| 2 | Reference Station | `Pressure (mbar)` | 气压，毫巴（= hPa） |
| 3 | Reference Station | `RH (%)` | 相对湿度，百分数（整数分辨率） |
| 4 | Reference Station | `Temperature (°C)` | 温度，摄氏度（0.1 °C 分辨率） |
| 5–6 | — | （空列） | 用作两组数据的视觉分隔 |
| 7 | **KESTREL Hand-held Monitor（Kestrel 手持仪）** | `Date-time` | 格式："**2024-10-17 10:46:03**"（ISO 风格，与左侧格式**不同**！） |
| 8 | KESTREL | `Pressure (mbar)` | 气压 |
| 9 | KESTREL | `RH (%)` | 相对湿度（**0.1% 分辨率**，比参考站更细） |
| 10 | KESTREL | `Temperature (°C)` | 温度 |

**表尾三行**：`Mean (Average):`、`Standard Deviation:`、`Standard Error:` —— **数值单元格是空的，需要你自己填**（这就是作业要算的东西）。

**数据规模与时间范围（实测统计）**：

| | 参考气象站 (Reference) | Kestrel 手持仪 |
|---|---|---|
| **有效数据行数 n** | **1353** | **271** |
| **采样间隔** | **1 秒** | **5 秒**（与讲义一致） |
| **起始时间** | 2024-10-17 **10:46:27** | 2024-10-17 **10:46:03** |
| **结束时间** | 2024-10-17 **11:08:59** | 2024-10-17 **11:08:33** |
| **总时长** | 约 **22.5 分钟** | 约 **22.5 分钟** |

> **⚠ 两列长度不等**：参考站 1353 行、Kestrel 只有 271 行。因此**Kestrel 那半张表在第 272 行之后全是空单元格**。在 Excel 里选整列做 `AVERAGE` 时会自动忽略空格，但**做 `COUNT` 求标准误时必须确认计数是 271 而不是 1353**（否则标准误会被算小约 2.2 倍）。**这是本周最容易踩的坑。**

**统计结果（依据数据集实算，样本标准差 STDEV.S）**

| 参数 | 仪器 | n | **均值 Mean** | **标准差 SD** | **标准误 SE** | 最小值 | 最大值 |
|---|---|---|---|---|---|---|---|
| **气压 Pressure (hPa/mbar)** | Reference | 1353 | **1002.414** | **0.068** | **0.0018** | 1002.3 | 1002.6 |
| | Kestrel | 271 | **1010.258** | **0.116** | **0.0070** | 1010.0 | 1010.7 |
| **相对湿度 RH (%)** | Reference | 1353 | **71.803** | **2.337** | **0.0635** | 66.0 | 75.0 |
| | Kestrel | 271 | **72.269** | **3.873** | **0.2353** | 60.2 | 78.7 |
| **温度 Temperature (°C)** | Reference | 1353 | **15.305** | **0.544** | **0.0148** | 14.8 | 16.8 |
| | Kestrel | 271 | **16.672** | **1.506** | **0.0915** | 14.7 | 21.3 |

**偏移量与变率差**

| 参数 | **Offset = Kestrel − Reference**（PDF Q3 约定） | **Offset = Reference − Kestrel**（幻灯片/讲义约定） | **ΔSD = SD_Kestrel − SD_Ref**（Q6） |
|---|---|---|---|
| **气压 (hPa)** | **+7.845** | −7.845 | **+0.048** |
| **相对湿度 (%)** | **+0.465** | −0.465 | **+1.536** |
| **温度 (°C)** | **+1.367** | −1.367 | **+0.962** |

### 5.10 结果判读（Q3 与 Q6 的"讨论"部分——这是拿分/学懂的关键）

**(A) 气压偏移 +7.8 hPa —— 典型的系统误差 / 零点或标度偏差**

- 7.8 hPa 远超真实天气造成的空间差异（同一公园内几百米范围的真实气压差 **< 0.1 hPa**）。
- **可能原因**：
  1. **Kestrel 的气压传感器未做零点校准**（zero error / offset）；
  2. **仪器设置错误** —— Kestrel 可显示**站点气压 (station pressure)** 或**海平面订正气压 (sea-level pressure / QNH)**，若两台仪器设置不同（例如一台设了参考高度、一台没设），就会产生固定量级的差；曼彻斯特市中心海拔约 40–70 m，对应约 5–8 hPa 的高度订正——**与观测到的 7.8 hPa 高度吻合**；
  3. 传感器老化/漂移。
- **判读结论**：这是**纯系统误差**（恒定偏差），**可以且必须通过减去 offset 完全校正**。校正后 Kestrel 气压与参考站几乎完全一致（两者标准差都极小：0.116 vs 0.068 hPa）。

**(B) 温度偏移 +1.37 °C 且 SD 大近 3 倍（1.51 vs 0.54 °C）—— 系统误差 + 代表性/人为误差混杂**

从数据的时间演变可以看出**决定性证据**：

| | 前 1/4 时段均值 | 后 1/4 时段均值 | 趋势 |
|---|---|---|---|
| **参考站温度** | 16.14 °C | 14.82 °C | **下降约 1.3 °C** |
| **Kestrel 温度** | 15.55 °C | 18.53 °C | **上升约 3.0 °C** |
| **参考站 RH** | 68.3 % | 74.0 % | **上升**（与降温一致 ✓） |
| **Kestrel RH** | ~76 % | ~68 % | **下降**（与升温一致 ✓） |

- **两台仪器的温度趋势完全相反**！参考站在降温（伴随 RH 上升，物理自洽），Kestrel 在升温（伴随 RH 下降，同样物理自洽）。
- **这不可能是真实的大气变化**——不可能同一公园内一处降温 1.3 °C 而另一处同时升温 3 °C。
- **最合理的解释（标准答案思路）**：
  1. **仪器被人手握持而受体温加热**，或**被放进/靠近口袋、身体**；
  2. **仪器被阳光直射**（**太阳辐射加热 (solar radiative heating)**），而参考站有**辐射防护罩 (radiation shield / Stevenson screen)**；
  3. **测量地点位于建筑物或硬质地面附近**（沥青、砖墙的**热岛/储热效应**），或处于背风的静风区，通风不足；
  4. **人为呼吸干扰** —— 讲义明确警告过：靠近仪器呼吸会测到呼出气体的湿度（而呼气也是暖湿的，同时抬高 T、扰动 RH）。
  - Kestrel 温度最高达 **21.3 °C**（11:04:53），同一时刻 RH 骤降到 61.4%——**这是一次典型的"被加热/被呼吸"事件**：温度尖峰与湿度低谷同步出现。
- **判读结论**：温度上的 +1.37 °C **不是纯粹的可校正系统偏差**，其中混入了**随时间增长的代表性/人为误差**。因此**简单减去一个常数 offset 并不能真正校正它**——这正是本周想让学生发现的深层教训。

**(C) 相对湿度偏移仅 +0.47 % 但 SD 大 1.66 倍（3.87 vs 2.34 %）**

- **均值几乎一致**（偏移 <0.5%），说明 RH 传感器本身**没有明显系统偏差**；
- 但 Kestrel 的**离散度显著更大**：既有**传感器噪声更大**（消费级 vs 研究级），也有**RH 随 T 的强耦合**（温度被扰动 → RH 跟着被扰动），还有**呼吸干扰**这一典型野外污染源；
- **注意分辨率差异**：参考站 RH 只到**整数**（66–75），Kestrel 到 **0.1%**（60.2–78.7）。**分辨率更高不等于准确度更高**——这是常见的误解。

**(D) Q6 判读的标准逻辑（"变率差为什么为正"）**

$\Delta s = s_{\text{Kestrel}} - s_{\text{Ref}} > 0$ 对三个参数都成立。给出原因时应包含：
1. **仪器等级不同**：Kestrel 是**消费级手持仪 (handheld)**，参考站是**研究级 (research-grade)**，后者**传感器噪声更低、时间常数更长（内部平滑）**；
2. **参考站有专业安装**：**辐射防护罩、标准安装高度、强制通风**，减少了外界扰动；
3. **手持仪暴露于人为扰动**（握持、移动、呼吸、遮挡）；
4. **采样位置不同**：两者在公园不同位置 → 部分差异是**真实的空间变率（代表性误差）**，不是仪器噪声；
5. **两者采样频率不同**（1 s vs 5 s），会影响所捕捉到的高频变率量；
6. **⚠ 但关键限制**：野外条件下，**仪器噪声与大气真实变率无法分离**——必须在**受控实验室条件**下标定才能分离（见第四节末尾的学习目标陈述）。

### 5.11 完整分析流程（可复用的"操作清单"）

1. 打开官方 "Calibrated Data" 文件夹里的 Excel 数据。
2. 只保留 **Date-Time、Temperature、Relative Humidity、Barometric Pressure** 四类列（两台仪器各一份）。
3. **检查数据长度**：确认 Kestrel 列的实际行数（本例 271）和参考站行数（本例 1353），**不要把空行算进去**。
4. 对 6 组数列（2 仪器 × 3 参数）分别计算：
   `=AVERAGE(rng)`、`=STDEV.S(rng)`、`=STDEV.S(rng)/SQRT(COUNT(rng))`
5. 计算 3 个**偏移量**与 3 个**变率差**，**注意题目要求的相减顺序**。
6. **画时间序列图**把两台仪器叠在一起看趋势——这是发现"温度趋势相反"这类问题的唯一途径。
7. 结合**现场笔记**（建筑、树木、天气、风向、谁在什么时候握着仪器）解释异常。
8. 到 Blackboard 完成在线测验，看即时反馈，重做直到全对。

---

## 六、易错点 / 重点难点

### 6.1 ⚠ 三份材料的实验参数互相矛盾（务必以讲义为准，但两者都要知道）

| 项目 | **主讲义 docx (2024-25)** | **导入幻灯片 pptx (2024-25)** | **实际数据集** |
|---|---|---|---|
| **测量时长** | **15 分钟** | **25 分钟** | 约 **22.5 分钟** |
| **Kestrel 自动记录间隔** | **每 5 秒** | **每 1 秒** | **每 5 秒** ✓ |
| **手动记录间隔** | **每 2 分钟** | **每 1 分钟** | — |
| **手动记录的参数** | 气压、温度、RH、**风速、风向** | 气压、温度、RH（不含风） | — |
| **参考站数据频率** | 未说明 | 未说明 | **每 1 秒** |

**应对**：数据集证实**Kestrel 记录间隔是 5 秒**（讲义正确）；时长以现场老师宣布为准。**答题时若被问到"Kestrel 多久记录一次"，答 5 秒。**

### 6.2 ⚠ 偏移量的符号约定不统一（本周最大的陷阱）

| 材料 | 表述 | 公式 | 温度结果 |
|---|---|---|---|
| **作业说明 PDF, Q3** | "subtracting your answer to **question 2** from the answer to **question 1**" | **Kestrel − Reference** | **+1.367 °C** |
| **幻灯片 Slide 20, Step 4** | "subtracting the mean value ... measured by the **Kestrel** from the corresponding mean value of the **weather station**" | **Reference − Kestrel** | **−1.367 °C** |
| **讲义 Experiment 2** | "subtracting **your measured mean** ... from the corresponding means calculated from the **reference weather station** data" | **Reference − Kestrel** | **−1.367 °C** |

**⚠ 在线测验以作业说明 PDF 的定义为准（Q1 − Q2 = Kestrel − Reference）**，因为测验题目就是照 PDF 的九题写的。**做题时逐字读"从哪个减哪个"，不要凭印象。数值相同，符号相反——填错符号直接判错。**

**记忆法**：英文 "subtract **A** from **B**" = **B − A**（把 A 从 B 里减掉）。**中文语序与英文相反，这是最常见的翻译错误来源。**

### 6.3 ⚠ 标准差 vs 标准误：概念与用途混淆

| | **标准差 (SD)** | **标准误 (SE)** |
|---|---|---|
| **衡量对象** | **单次测量**的离散程度 / 数据的散布 | **均值估计**的不确定度 |
| **随 n 增大** | **趋于一个常数**（收敛到真实的总体 σ） | **持续减小**（∝ 1/√n） |
| **本周含义** | 仪器随机噪声 + 大气真实变率 | "这个平均值我有多确定" |
| **公式** | $s$ | $s/\sqrt{n}$ |

**易错**：以为"SD 变小说明测得更准"——SD 反映的是**真实的+噪声的变率**，样本再多它也不会变小。**只有 SE 会随样本数变小。**

**另一个易错**：本周两台仪器 n 不同（271 vs 1353），所以**即使 SD 差不多，SE 也会差很多**。比较两仪器的"精度"应看 **SD**，比较"均值的可信度"才看 **SE**。

### 6.4 ⚠ Excel 操作坑

| 坑 | 后果 | 正确做法 |
|---|---|---|
| **选取整列（含空白行）算 COUNT** | Kestrel 的 n 被误算为 1353，SE 偏小 2.2 倍 | 用 `COUNT()` 确认实际数值个数；或先把数据区域框准 |
| **`COUNT` vs `COUNTA`** | `COUNTA` 会把文本/空字符串也计入 | 数值列用 `COUNT` |
| **`STDEV.P` 与 `STDEV.S` 混用** | n 小时结果不同 | 测量数据是**样本**，用 `STDEV.S`（本周 n 大，差异可忽略，但概念要对） |
| **把两台仪器的 Date-Time 直接横向对齐** | 二者**起始时刻不同（10:46:03 vs 10:46:27）、频率不同（5 s vs 1 s）、行数不同**，逐行相减完全错误 | **只比较统计量（均值/SD），不要逐行配对**；若要逐行比对必须先做**时间重采样/插值** |
| **忘了 Q9 要对 P 和 RH 全部重做** | 只交了温度的 8 个答案 | 记住总共 **24 个数值** |
| **单位标错** | 数据集写 mbar，题目要 hPa | **1 mbar = 1 hPa，数值不变**，但报答案时按题目单位写 |
| **四舍五入过早** | 偏移量精度损失 | 中间计算保留全精度，只在最终报告时按合理有效数字取舍（温度/RH 取 2 位小数，气压取 2–3 位） |

### 6.5 ⚠ 野外操作的坑

| 坑 | 后果 | 预防 |
|---|---|---|
| **忘了取下叶轮塑料保护盖** | 风速读数恒为 0 或严重偏低 | 出发前检查 impeller 已暴露 |
| **手机离 Kestrel 超过 5 m** | **蓝牙断开，数据丢失** | 全程随身，App 保持前台 |
| **只依赖自动记录，不做手记** | 仪器/导出出问题时**整组数据归零** | **每 2 分钟手记一次**——讲义把这条列为"as scientists we can't always rely on our instruments working" |
| **对着仪器呼吸/用手包住仪器** | RH 与 T 被严重污染（见 5.10 的 21.3 °C 尖峰） | 手臂伸直、迎风举起、避免呼气方向 |
| **仪器被阳光直射或贴近墙面/地面** | 温度**系统性偏高**（辐射加热） | 遮阴、离热表面足够远、保持通风 |
| **忘了关机 / 忘了归还** | 电池耗尽、器材丢失 | 收尾清单三步走：导出 → 关机 → 归还 |
| **忘了记录周围环境** | **事后无法解释代表性误差**，讨论题写不出内容 | 现场就写下建筑、树木、天气、风向与人员行为 |

### 6.6 ⚠ 概念判读上的陷阱

1. **"标准差大 = 仪器差"** ✗ —— 标准差里同时含**大气真实变率**。Kestrel 的位置若在开阔风口，真实变率本就更大。**野外无法分离二者**，必须写明这一点。
2. **"减去 offset 就完全校正了"** ✗ —— 只有当偏差**恒定**时才成立。本周的温度偏差是**随时间增长的**（前 1/4 时段 Kestrel 比参考站还低 0.6 °C，后 1/4 时段高出 3.7 °C），减常数无法修正。
3. **"分辨率高 = 准确度高"** ✗ —— Kestrel 的 RH 显示到 0.1%，参考站只到 1%，但参考站更准。**分辨率 (resolution) ≠ 精密度 (precision) ≠ 准确度 (accuracy)**。
4. **"风向 = 风吹向哪里"** ✗ —— **风向记录的是"风从哪里来"**。
5. **混淆一次与二次污染物** —— **O₃ 是二次污染物**，没有直接排放源；NOx 与 PM 主要是一次的（但也有二次 PM）。
6. **忽视系统误差的不可平均性** —— 随机误差可以靠平均消除，**系统误差不能**，只能靠校准。
7. **把"形成性 (formative)"理解成"可以不做"** —— 在线测验不计分，但**小组数据提交是有截止日期的硬性任务**，且测验内容是后续野外课程的必备技能。
8. **在线测验必须独立完成**，讲义明确 "you should not work as a group"。

### 6.7 本周最可能的简答/讨论考点

1. **列举并解释三类误差**，各给一个空气质量测量中的例子。
2. **为什么随机误差需要 >100 个测量点才能可靠量化？**（高斯分布 + 大数定律 + SE ∝ 1/√n）
3. **如何把仪器随机误差与大气真实变率分离？**（受控实验室标定 —— 见第四节末尾原文）
4. **Kestrel 与参考站的温度偏移可能由哪些物理环境与仪器原因造成？**（辐射加热、握持体温、遮挡通风、传感器校准、代表性差异）
5. **为什么风向按"来向"记录？**（关心污染/气团的来源）
6. **1952 伦敦烟雾的成因、影响与政策后果。**
7. **Mars Climate Orbiter 的教训对空气质量监测的启示。**（单位/设置错误 → 读数错误 → 健康指南与政策错误）

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| **Air quality** | 空气质量 | 大气中污染物浓度水平及其对健康与环境的影响程度 |
| **Great Smog of 1952 / London Smog** | 1952 年伦敦大烟雾 | 燃煤 + 反气旋静稳天气造成的致命烟雾事件，死亡 4,000–12,000 人 |
| **Clean Air Act (1956)** | 《清洁空气法》(1956) | 伦敦烟雾后英国出台的反污染立法，设立"烟控区"限制城市燃煤 |
| **Smoke control area** | 烟控区 | 《清洁空气法》划定的禁止/限制燃烧产烟燃料的城市区域 |
| **Anticyclonic conditions** | 反气旋条件 | 高压系统下沉气流、静风、逆温，使污染物在近地面累积 |
| **Nitrogen oxides (NOx)** | 氮氧化物 | NO + NO₂ 的统称；来自化石燃料燃烧、闪电与土壤；致酸雨与烟雾 |
| **Particulate matter (PM)** | 颗粒物 | 悬浮固/液微粒；来自燃烧、农业、海盐与沙尘；降低能见度、可携带病原体 |
| **Ozone (O₃)** | 臭氧 | 二次污染物，NOx 与 VOCs 在阳光下反应生成；强氧化剂，损害植被与文物 |
| **Volatile organic compounds (VOCs)** | 挥发性有机物 | 易挥发的含碳气体，是生成 O₃ 的前体物之一 |
| **Sulphur dioxide (SO₂)** | 二氧化硫 | 燃煤主要污染物，1952 伦敦烟雾的关键成分，致酸雨 |
| **Primary pollutant** | 一次污染物 | 直接从排放源进入大气的污染物 |
| **Secondary pollutant** | 二次污染物 | 在大气中由一次污染物反应生成的污染物，可为气态或气溶胶 |
| **Aerosol** | 气溶胶 | 悬浮在气体中的固体或液体微粒系统 |
| **Acid rain** | 酸雨 | NOx/SO₂ 转化为硝酸/硫酸随降水沉降，损害森林与湖泊 |
| **Smog** | 烟雾 | smoke + fog；城镇上空的污染性雾霾 |
| **Haze** | 霾 | 气溶胶造成的能见度下降现象 |
| **Premature death** | 早逝 | 因污染暴露而早于预期寿命的死亡；全球每年约 700 万 |
| **Systematic error** | 系统误差 | 可重复的、以同样方式影响全部测量的偏差；靠校准消除，平均无效 |
| **Random error / non-systematic error** | 随机误差 / 非系统误差 | 不可预测的逐次波动（"噪声"），高斯分布，靠多次测量量化与平均削弱 |
| **Representativity error** | 代表性误差 | 因采样设计/位置使"测到的"不能代表"想知道的"而产生的误差 |
| **Human error** | 人为误差 | 记录、录入或操作不当造成的误差（如对着仪器呼吸） |
| **Bias** | 偏差 | 测量值系统性偏离真值的方向与大小 |
| **Zero error** | 零点误差 | 未归零/去皮导致所有读数偏移同一常数 |
| **Scale error** | 标度误差 | 仪器未正确校准导致读数按比例失真 |
| **Instrument drift** | 仪器漂移 | 读数随时间单调偏移，常由温湿度变化或传感器老化引起 |
| **Sensor drift** | 传感器漂移 | 传感器随使用时间性能变化，需定期重新校准 |
| **Calibration** | 校准 | 用已知标准修正仪器读数的过程 |
| **Recalibration** | 重新校准 | 因漂移而定期重复的校准 |
| **Calibration offset** | 校准偏移量 | 待校仪器与参考仪器均值之差，从数据中减去即去除系统偏差 |
| **Reference / standard weather station** | 参考（标准）气象站 | 高精度基准仪器，用于比对校准手持仪 |
| **Research-grade** | 研究级 | 精度与稳定性达到科研要求的仪器等级 |
| **Mean (average)** | 均值（平均值） | 分布的中心值；Excel `AVERAGE` |
| **Standard deviation (SD)** | 标准差 | 数据围绕均值的离散程度；本周=仪器噪声+大气真实变率；Excel `STDEV.S` |
| **Standard error (SE / SEM)** | 标准误 | 均值的不确定度，= SD/√n；Excel `STDEV.S(...)/SQRT(COUNT(...))` |
| **Gaussian / normal distribution** | 高斯分布 / 正态分布 | 钟形对称分布，由均值与标准差刻画；随机误差的典型分布 |
| **Law of large numbers** | 大数定律 | 样本量增加会降低对总体均值估计的不确定性 |
| **Noise** | 噪声 | 随机误差的俗称 |
| **Accuracy** | 准确度 | 测量值接近真值的程度（受系统误差影响） |
| **Precision** | 精密度 | 重复测量彼此接近的程度（受随机误差影响） |
| **Resolution** | 分辨率 | 仪器能显示的最小刻度；分辨率高 ≠ 准确度高 |
| **Uncertainty** | 不确定度 | 对测量值可信范围的定量表述 |
| **Kestrel (handheld weather station)** | Kestrel 手持气象站 | 本周使用的手持仪，测 T/P/RH/风速/风向 |
| **Kestrel LiNK (app)** | Kestrel LiNK 应用 | 经蓝牙连接 Kestrel、记录与导出数据的手机 App |
| **Impeller** | 叶轮 | Kestrel 顶部测风速的小螺旋桨，使用前须取下保护盖 |
| **Bluetooth connectivity** | 蓝牙连接 | Kestrel 与手机的通信方式，需保持 5 m 内 |
| **Temperature (T)** | 温度 | 本周记为 °C |
| **Barometric pressure** | 大气压 / 气压 | 本周记为 mbar（= hPa） |
| **Relative humidity (RH)** | 相对湿度 | 实际水汽压占该温度饱和水汽压的百分比 |
| **Wind speed** | 风速 | 空气水平运动速率，m/s |
| **Wind direction** | 风向 | **风的来向**（因为关心污染/气团来源） |
| **Compass direction** | 罗盘方位 | 用 N/E/S/W 或角度表示的方向 |
| **Meteorology** | 气象（学） | 决定污染物停留时间与扩散方式的大气物理条件 |
| **Dispersion** | 扩散 / 弥散 | 污染物在大气中被输送与稀释的过程 |
| **Temperature inversion** | 逆温 | 温度随高度升高的层结，抑制垂直混合、加剧污染累积 |
| **Radiation shield** | 辐射防护罩 | 遮挡太阳辐射以保证气温测量准确的装置 |
| **Co-location** | 同址比对 | 把待校仪器与参考仪器放在一起同步测量以求偏移量 |
| **Formative assessment** | 形成性评估 | 以学习与反馈为目的、不计入最终成绩的评估 |
| **Blackboard** | Blackboard | 曼大的在线教学平台，发布数据、作业与在线测验 |
| **Brunswick Park** | 布伦瑞克公园 | 曼大校园内的野外测量地点，设 A–F 六个组位与参考站 RS |
| **Mars Climate Orbiter** | 火星气候轨道器 | 1999 年因公制/英制单位换算错误而损失的 NASA 探测器（$125 M） |
| **ppb / ppm** | 十亿分率 / 百万分率 | 气体体积混合比单位；与 µg/m³ 通过摩尔质量与摩尔体积换算 |
| **µg/m³** | 微克每立方米 | 质量浓度单位；PM 只能用它表示 |
| **hPa / mbar** | 百帕 / 毫巴 | 气压单位，**1 hPa = 1 mbar = 100 Pa** |
| **WHO Air Quality Guidelines (AQG)** | 世卫组织空气质量指导值 | WHO 发布的健康导向浓度限值（2021 版最新） |
