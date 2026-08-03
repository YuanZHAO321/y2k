# Week 2 — 水硬度微量重量滴定 (Microscale Gravimetric Titration) / 地质图判读一 (Geological Maps 1)

> 本周材料清单（共 6 个 md，全部已通读）
>
> **Morning/**
> - `P02 ANSWERS water hardness gravimetric titration.md` — 化学实践 2：微量重量滴定测水硬度（含全部答案）
>
> **Afternoon/**
> - `Geological maps 1(3).md` — 地质图判读一：产状 (dip & strike)、地形与露头、三点问题 (three-point problem)
> - `EART11300 Practical Class 2 or 3(1)(1).md` — 配套讲义：地质图的组成、等高线、地形剖面、Digimap
> - `Brighton Map Answers.md` — Brighton & Worthing 图幅 (Sheet 318/333) 问题答案
> - `Q3soln(4)(1).md` — 练习 3 解答（已知露头 + 产状补全界线）
> - `Q4soln(4)(1).md` — 练习 4 解答（已知三处接触点补全煤层露头）

---

## 一、本周主题

本周是 **EART11300 (Practical and Professional Skills Development)** Hilary Term（春季学期）第 2 周。本课程每周分**上午场**与**下午场**两场主题完全不同的实践课，本周为：

| 场次 | 主题 | 学科归属 | 核心技能 |
|---|---|---|---|
| **上午场** | **Microscale gravimetric titration to determine water hardness**（微量重量滴定法测定水硬度） | Chemistry 2（化学模块第 2 讲） | 定量化学分析、EDTA 络合滴定、摩尔比换算、误差与不确定度评估 |
| **下午场** | **Geological Maps 1**（地质图判读一） | 地质图学 (Geological map interpretation) | 产状 (strike/dip) 的定义与记录、露头形态与地形的关系、V 字法则、三点问题与地层等高线 (stratum contours)、地形剖面绘制、Digimap 与英国国家格网 |

两场课的共同定位：
- **上午场**承接上学期 (Semester 1) 在 **Mam Tor** 的野外工作 (fieldwork)，主题是「**当地地质如何影响水化学**」；同时为二年级 **EART26201 Principles of Geochemistry** 与 **EART27001 Environmental Chemistry 1** 的实验任务打下安全操作与定量分析基础。
- **下午场**是地球科学的**核心技能之一**：把二维地图上的露头图案 (outcrop pattern) 还原成三维地下几何。本周只处理**最简单的情形：均匀倾斜的平面地层 (uniformly dipping planar beds)**，为后续褶皱、断层、不整合的判读打底。

> **注意**：本周下午场材料的正式内容仅覆盖**产状 + 露头与地形关系 + 三点问题**。褶皱 (folds)、断层 (faults)、不整合 (unconformities) 的系统判读**并未在本周材料中出现**（材料明确说「we will start with the simple cases first」）。本笔记第三节给出的判读流程，仅在本周材料明确支持的范围内展开，不额外扩写。

---

## 二、核心概念

### 上午场：水硬度与 EDTA 络合滴定

#### 1. 什么是水硬度 (water hardness)？

- 水硬度由水中 **Ca²⁺ 与 Mg²⁺ 离子**（二价金属阳离子, divalent metal cations）的存在造成。
- 成因链条：**降水 (precipitation) → 下渗 (percolate) 通过富含钙/镁矿物的沉积层 → 二价阳离子溶解进入水中**。
- 因此 **当地地质 (local geology) 直接决定水硬度**——这正是本实验与 Mam Tor 野外工作的连接点。
- 硬度的**表述单位**不统一，各国框架不同，但常用两种：
  - **mg CaCO₃ / l**（以碳酸钙计）
  - **mg Ca²⁺ / l**（以钙离子计）
  - 两者数值上大致成 ~2.5 倍关系（CaCO₃ 的 M ≈ 100.09，Ca 的 Aᵣ ≈ 40.078）。

#### 2. 英国的硬度分级框架 (United Utilities / Drinking Water Inspectorate)

| mg CaCO₃/l | mg Ca²⁺/l | 分类 (Classification) | 中文 |
|---|---|---|---|
| 0–50 | 0–20 | Soft | 软水 |
| 51–100 | 21–40 | Moderately soft | 中度软水 |
| 101–150 | 41–60 | Slightly hard | 微硬水 |
| 151–200 | 61–80 | Moderately hard | 中度硬水 |
| 201–300 | 81–120 | Hard | 硬水 |
| >300 | >120 | Very Hard | 极硬水 |

> **本实验最终答案报的是 mg Ca²⁺/l**，所以对照的是**第二列**。这是最容易出错的地方之一。

#### 3. 硬度的实际影响

- **硬水加热** → 碳酸氢盐 (bicarbonates) **热分解 (thermal decomposition)** → 沉积出固体钙镁化合物 = **水垢 (scale)** → 堵塞管道、影响热水器性能。
- **软水**反而**腐蚀金属管道 (corrodes metal pipework) 的速率更快**（比硬水快）。
- **健康**：饮用硬水可能对人体健康有益（WHO 2009 报告：钙镁摄入与降低心血管疾病死亡率、骨质疏松相关）。但 **WHO 目前不为饮用水硬度设定指导值 (no guideline values)**；饮用水中的硬度水平**不被视为健康问题**。
- **口感**：[Ca²⁺] > 100 mg/l 时水会有**强烈的味道 (strong taste)**，可能影响可接受性 (acceptability)。

#### 4. 「重量法 (gravimetric method)」——为什么用称重代替读体积？

- 常规滴定用**滴定管 (burette)** 读体积；本实验为**微量化 (microscale)**，出于**可持续性 (sustainability)、节约试剂**的考虑。
- 微量条件下体积太小无法用滴定管准确读数，因此改用**天平称量质量变化**来间接得到体积。
- **关键假设**：EDTA 溶液很稀 (0.01 M)，可假设其**密度与纯水相同 = 1 g cm⁻³**。
- 于是：**加入的 EDTA 溶液质量 (g) 在数值上等于转移的体积 (cm³)**。
  $$\text{质量}(\mathrm{g}) \xrightarrow{\ \rho = 1\ \mathrm{g\,cm^{-3}}\ } \text{体积}(\mathrm{cm^3})$$
- **代价**：微量技术会带来**更大的相对误差 (larger error in our measurements)**——这是本实验后半段误差分析的由来。

#### 5. 滴定的络合反应 (complexation reaction)

- **EDTA** = **e**thylene **d**iamine **t**etraacetic **a**cid（乙二胺四乙酸），浓度 **0.01 M**。
- 在 **pH = 10** 时，EDTA 分子处于**完全去质子化 (fully deprotonated)** 形式——即已把全部酸性氢离子给了水溶液。这就是为什么必须加 **pH 10 缓冲液 (buffer)**。
- 完全去质子化的 EDTA 可与金属阳离子结合形成**水溶性络合物 (water-soluble complexes)**。
- EDTA 是 **六齿配体 (hexadentate ligand)**：拥有 **6 对孤对电子 (lone pairs)** 可供给金属阳离子。
- 金属阳离子 **M**（此处为 Ca²⁺ 或 Mg²⁺）被**包裹 (enclosed)** 在 EDTA 络合物内部，络合过程把原先配位的 **6 个单齿配体 (monodentate ligands，即 6 个水分子)** 释放回溶液。
- **驱动力 = 熵增 (large increase in entropy)**：反应物侧 2 个粒子 → 产物侧 7 个粒子，体系粒子数增加。这一现象称为 **螯合效应 (chelate effect)**（源自希腊语 *chelos* = 「蟹」，形容多齿配体像蟹钳一样「抱住」金属阳离子）。
- **★ 反应计量比 (reaction ratio) EDTA : M(Ca²⁺ 或 Mg²⁺) = 1 : 1**（全部计算的基石）。

#### 6. 指示剂反应 (indicator reaction)

- 指示剂 **Eriochrome Black T**（铬黑 T），配方为 **0.2 g 固体 + 20 ml 乙醇 (ethanol)**。
- **颜色判据**：
  - 有游离 **Mg²⁺** 存在时 → **红紫色 (red-purple)**
  - 当标准溶液中的 EDTA 已与样品中**全部**的 Ca²⁺ 与 Mg²⁺ 形成络合离子后 → **变蓝 (blue)**
- **终点 (end point)** = 指示剂由 **红紫 → 蓝** 的那一刻。

---

### 下午场：地质图判读的基础概念

#### 1. 两类地图与两个机构

| | 定义 | 英国出版机构 |
|---|---|---|
| **Topographic map**（地形图） | 显示地表物理特征，包括这些特征相对某一**基准面 (datum level)** 的**高度** | **Ordnance Survey (OS)** |
| **Geological map**（地质图） | 显示**若无表层覆盖物 (superficial coverings，如土壤 soil、柏油 tarmac、建筑)** 时会出露在地表的**岩石地层单位 (lithostratigraphic formations)** | **British Geological Survey (BGS)** |

- 地质图是把**地质信息叠加在地形图上**——所以既有等高线又有地层界线，二者的**相互关系**正是判读的关键。
- **Contour line（等高线）**：连接**等高程 (equal elevation)** 各点的线，**永远是水平线 (always horizontal)**。这一点非常重要——它是「地层等高线」概念的类比基础。

#### 2. 地层学的基本单位与定律

- **Bed（层）**：我们使用的**最小地层学单位 (smallest stratigraphical division)**，指由**单次流动事件 (a flow event)** 沉积、通常历时很短的单个层。层面 (bedding surface) 在过去某时刻往往就是**沉积物表面**。
- **Bedding plane（层面 / 层理面）**：层与层之间的**界面**。我们用**层面的产状 (orientation of the planes)** 来推断一个区域的**地质构造与地质历史**。
- **Formation（组）**：一组具有某些共性的层的集合（如岩石类型相同、或沉积构造显示同一沉积环境）。要求：
  - **足够厚 / 大**，在图上**可见 (visible on the map)**
  - 与其他 formation **可区分 (distinct)**
  - 但**接触界线本身不必是截然的 (the contact does not have to be sharp or distinct)**——例如可以定义为「砾岩层 (conglomerate) 比例超过 50% 时即为另一 formation」
- **地图上多数岩石是沉积岩 (sedimentary)**，因此可以使用：
  - **Law of Superposition（地层叠覆律）**：未受扰动时，上覆者新、下伏者老
  - **Law of Original Horizontality（原始水平律）**：地层最初近似水平沉积，之后的倾斜是构造事件造成的

#### 3. Contact（接触界线）与置信度符号

地质图上两个不同 formation 之间画的线叫 **contact（接触界线）**。用线型表达**我们对界线位置的把握程度**：

| 线型 | 含义 |
|---|---|
| **实线 (solid line)** | **绝对确信 (absolutely confident)** 界线位置 |
| **虚线 (dashed line)** | 位置存在**一定不确定性 (some uncertainty)** |
| **带问号的虚线 (dashed line with question marks)** | **非常不确定 (really unsure)** |

#### 4. Outcrop vs. Exposure（露头 vs. 出露）—— 极易混淆

| 术语 | 定义 |
|---|---|
| **Exposure（出露 / 露头点）** | 岩石**实际裸露在地表**、你**可以站上去并测量层面产状**的地方 |
| **Outcrop（露头 / 露头分布）** | **地质图上看到的东西**；表示某 formation **若出露于地表则会出现的范围**（不管实际上有没有被土壤/建筑盖住） |

> 记忆法：**Exposure 是野外的现实，Outcrop 是地图上的投影范围。** 一张可靠的地质图往往是在**只有百分之几的地表有基岩出露**的区域做出来的。

#### 5. Strike 与 Dip（走向与倾角）—— 平面产状的两个要素

地层 (beds/strata) 最初近似水平，之后在构造事件 (tectonic events) 中被褶皱、形成山带。**层被几何上视为平面 (planes)**，地质学家用**两条信息**记录平面的产状：

- **(1) Strike（走向）**：平面上**一条水平线 (horizontal line) 的方向**。
  - 更精确的表述：走向是该水平线的**方位角 / 罗盘方位 (azimuth / compass bearing)**。
  - 这条线也**垂直于最陡倾斜的方向**。
  - **永远写成 3 位数字**，例如南北走向的层写作 **180**。
- **(2) Dip（倾角）**：平面**最大的坡角 (maximum angle of slope)**，**永远垂直于走向 (always perpendicular to strike)**。
  - **永远写成 2 位数字**：垂直层 = **90°**，水平层 = **00°**。
  - **必须同时给出倾向 (dip direction)**，用罗盘方向表示，如 East。

**本课程使用的记录格式**：
$$\boxed{\textbf{strike} / \textbf{dip} \ \text{and} \ \textbf{dip direction}}$$
例：**180/60 E**（走向 180°，倾角 60°，向东倾）；**180/24 E**。

另有一种在解答文件中出现的**等价写法**：**dip / dip-direction(方位角)**，例如 **6/209**（倾角 6°，倾向方位角 209°）。同一产状的两种写法可互换：
$$\text{dip direction azimuth} = \text{strike} \pm 90^\circ \quad(\text{取指向下倾一侧的那个})$$

**测量工具**：**罗盘倾角仪 (compass clinometer)**。现在也有各种手机 app，**但必须先学会用罗盘倾角仪**。

#### 6. 露头图案 (outcrop pattern) 与地形的关系 —— 判读的核心

> **露头图案 = 岩体三维形态与地表面 (land surface) 的交线。**

因为地层出露的**高程**取决于接触面的倾斜方式，所以地形起伏 (topographic relief) 控制了图上的露头形状。四种基本情形（对应讲义 Fig. 2 的四个块状图，图中含一条河谷、等高线向上游呈 V 形）：

| 情形 | 露头与等高线的关系 | 图上表现 |
|---|---|---|
| **(a) 水平地层 (horizontal stratum)** | 露头**完美地跟随等高线 (perfectly follows the topographic contours)**，与等高线平行 | 界线与等高线重合/平行 |
| **(b) 直立地层 (vertical stratum)** | 与地形**毫无呼应 (shows no sympathy with topography)**，**横切山坡** | 一条**直线**穿过所有等高线（断层 fault、火成岩墙 dyke 亦如此） |
| **(c) 向山内倾斜 (dipping into the hill)** | 露头在河谷处**向上游 V (V's upstream)**，切过等高线 | V 形尖端指向上游 |
| **(d) 向下游倾斜且比河床坡度更陡 (dipping downstream more steeply than the stream slope)** | 露头在河谷处**向下游 V (V downstream)**，切过等高线 | V 形尖端指向下游 |

**★ V 字法则 (the "V" rule)**（讲义原文强调的斜体结论）：
> *当一个倾斜的接触面穿过河谷时，会形成一个 "V"，**V 的尖端指向接触面的倾向 (the apex pointing in the direction of dip of the contact)**。主要例外是接触面**水平**（情形 a）或**垂直**（情形 b）。*

**推论（判读速查）**：
- 界线**紧贴等高线** → 倾角**很缓 / 接近水平**
- 界线**笔直切过等高线、完全不理会地形** → 倾角**很陡 / 接近直立**
- 界线**波状起伏地切过等高线** → **中等倾角**，且可由 V 形定倾向

#### 7. 由地层新老关系判定倾向 (dip direction from outcrop patterns)

- 所有地质图都附有**地层柱状图 (stratigraphic column / strat column)**，按顺序列出图上出现的各 formation：**最老在底部，最新在顶部**。
- **规则**：若地层倾斜，则**倾向由老指向新 (the dip direction goes from older to younger)**。
- **前提条件**：这条规则**对倒转地层 (upside down / overturned beds) 不成立**。本周只处理简单情形。
- 图上还会用 **younging symbols（指向变新方向的符号）** 标出变新方向。

#### 8. Stratum contours（地层等高线）—— 三点问题的工具

- **定义（讲义 Geological maps 1 的说法）**：地层等高线是**地质平面与地形等高线的交点 (points of intersection of a geological plane and topographic contours)**。
- **定义（讲义 Practical Class 的说法，更一般）**：可以画在**任何地质面**上的等高线——通常是层面 (bedding surface)，也可以是**断层面 (fault plane)** 或**煤层面 (surface of a coal seam)**。和地形等高线一样，它们画在**相对基准面的特定高度上**。
- **作用**：用二维图表示**地下（甚至剥蚀掉的地上部分）岩层面的三维形态**。
- **几何性质（★ 必背）**：

| 地质面性质 | 地层等高线表现 |
|---|---|
| **平面 (planar) 且均匀倾斜** | 地层等高线是**直的、平行的、等间距的 (straight, parallel and equidistant)** |
| 面的走向 | **等于地层等高线的走向**（地层等高线本身就是走向线） |
| 地层等高线**弯曲** | 该地质面的**走向随位置变化**，沿曲线变化 |
| 地层等高线**间距变化** | 该地质面的**倾角随位置变化**（间距密 = 倾角陡） |

---

## 三、公式与图表

### A. 上午场：滴定定量计算的公式链

#### 基本关系式

**Equation 1（浓度定义）**
$$\text{Concentration}\ (M) = \frac{\text{moles}\ (\mathrm{mol})}{\text{Volume}\ (\mathrm{l})}$$

变形（本实验最常用的形式）：
$$\text{moles} = \text{Concentration} \times \text{Volume}\ (\mathrm{l})$$

**Equation 2（质量—物质的量关系）**
$$\text{Mass}\ (\mathrm{g}) = A_r\ (\mathrm{g\,mol^{-1}}) \times \text{moles}\ (\mathrm{mol})$$

**由密度假设得到的换算（重量法的核心）**
$$\rho_{\text{稀溶液}} \approx \rho_{\text{纯水}} = 1\ \mathrm{g\,cm^{-3}} \ \Longrightarrow\ V/\mathrm{cm^3} = m/\mathrm{g}$$

#### 单位换算（★ 讲义特别提醒 "check units!"）

$$1\ \mathrm{cm^3} = 1\ \mathrm{ml} = 10^{-3}\ \mathrm{l} = 10^{-3}\ \mathrm{dm^3}$$
$$1\ \mathrm{g} = 10^{3}\ \mathrm{mg}$$
$$1\ \mathrm{mg\,l^{-1}} = 1\ \mathrm{ppm}$$

即：**cm³ → l 除以 1000**；**g/l → mg/l 乘以 1000**。

#### 完整的五步计算链（合并成一条总式）

$$
[\mathrm{Ca^{2+}}]\ /\ \mathrm{mg\,l^{-1}}
= \frac{c_{\mathrm{EDTA}} \times \left(\dfrac{m_{\mathrm{EDTA}}}{1000}\right)}{\dfrac{m_{\mathrm{water}}}{1000}} \times A_r(\mathrm{Ca}) \times 1000
$$

化简后（因为两个 1/1000 相消）：

$$\boxed{\ [\mathrm{Ca^{2+}}]\ /\ \mathrm{mg\,l^{-1}} = \frac{c_{\mathrm{EDTA}} \times m_{\mathrm{EDTA}}}{m_{\mathrm{water}}} \times A_r(\mathrm{Ca}) \times 1000\ }$$

其中 $c_{\mathrm{EDTA}} = 0.01\ \mathrm{mol\,l^{-1}}$，$A_r(\mathrm{Ca}) = 40.078$，$m$ 单位为 g。

> **考试建议仍按五步分开写**（讲义要求分步作答），但用这条简化式**验算**极快。

#### 相对原子质量（本实验用到）

| 元素 | $A_r$ |
|---|---|
| Ca | **40.078** u |
| Mg | **24.305** u |

#### 不确定度公式

$$\text{天平绝对不确定度（2 dp）} = \pm 0.005\ \mathrm{g}$$
$$\text{质量差（两次读数）的不确定度} = 2 \times (\pm 0.005) = \pm 0.01\ \mathrm{g}$$
$$\text{细口 Pasteur 移液管单滴体积} = 0.02\ \mathrm{ml} \Rightarrow 0.02\ \mathrm{g}\ (\text{最多多加一整滴}) $$
$$\boxed{\text{总不确定度（非对称）} = -0.01\ \mathrm{g}\ \text{到}\ +0.03\ \mathrm{g}}$$

$$\%\ \text{error}_{\text{lower}} = \frac{-0.01}{m_{\mathrm{EDTA}}}\times 100\%, \qquad \%\ \text{error}_{\text{upper}} = \frac{+0.03}{m_{\mathrm{EDTA}}}\times 100\%$$

---

### B. 下午场：地质图判读流程与要点对照表

#### B-1. 由「露头图案 × 等高线」快速判定产状 —— 判读流程

```
第 1 步：看接触界线与地形等高线的关系
   ├─ 界线与等高线平行/重合 ────────────→ 地层【水平】(dip ≈ 00)
   ├─ 界线是直线，无视等高线横切 ────────→ 地层/构造面【直立】(dip = 90)
   │                                        （或为断层 fault / 岩墙 dyke）
   └─ 界线波状切过等高线 ────────────────→ 地层【倾斜】，进入第 2 步

第 2 步：找河谷（等高线向上游 V 的地方），看地质界线的 V 字
   └─ V 的尖端所指方向 = 倾向 (dip direction)
       ├─ V 指向上游 → 向山内倾（情形 c）
       └─ V 指向下游且比河床更陡 → 向下游倾（情形 d）

第 3 步：用地层柱状图交叉验证
   └─ 倾向应由【老地层】指向【新地层】
       （倒转地层例外，本周不涉及）

第 4 步：定量求走向与倾角 → 做三点问题 / 地层等高线作图（见 B-2）
```

#### B-2. 三点问题 (three-point problem) 的标准作图流程

**适用前提**：地层是**平面 (planar) 且均匀倾斜 (uniformly dipping)**；已知**同一接触面**在**三个位置**出露。

| 步骤 | 操作 |
|---|---|
| **1. 定高程点** | 在图上找出**地质界线与地形等高线的交点**。每个交点的**高程 = 该地形等高线的高程**。这些点即为该地质面上的已知高程点。 |
| **2. 连等高点** | 把**高程相同**的两个（或以上）交点用**直线**连起来 → 这条线就是该高程的**地层等高线 (stratum contour)**，也就是一条**走向线 (strike line)**。 |
| **3. 检验平面性** | 若地层是平面且均匀倾斜，则各条地层等高线必须**互相平行、且等间距**。用这一点检查作图是否正确。 |
| **4. 补齐其余高程** | 按等间距、平行地外推/内插出其余高程的地层等高线（可延伸到图外的负高程，如 −100、−200 m，代表地下）。 |
| **5. 补全露头界线** | 地层等高线与**同高程**的地形等高线的**交点**，就是地质界线在图上应通过的点；把这些交点顺次连成光滑曲线 = 完整的露头界线。 |
| **6. 读走向** | 用量角器量**地层等高线的方位角** = **strike**（写 3 位数）。 |
| **7. 算倾角** | 见下方公式。 |
| **8. 定倾向** | 倾向指向**地层等高线高程降低**的一侧；再用地层新老（老→新）交叉验证。 |
| **9. 判新老 / 阴影** | 用 younging symbol 或叠覆律判断哪层老；题目要求时，把**位于该面之上 (above the seam)** 的区域涂阴影。 |

#### B-3. 倾角计算公式

设相邻两条地层等高线的**高程差**为 $\Delta h$（垂直间距 / vertical interval），它们在图上的**垂直距离**（沿倾向方向、即垂直于走向量得）换算到**地面真实水平距离**为 $d$（horizontal distance），则

$$\boxed{\ \tan(\text{dip}) = \frac{\Delta h}{d}\ } \qquad \text{dip} = \arctan\!\left(\frac{\Delta h}{d}\right)$$

**比例尺换算**（讲义 Exercise 3 给的比例尺是 **1:4,000**）：
$$d_{\text{地面}} = d_{\text{图上}} \times \text{比例尺分母}$$
- 1:4,000 → 图上 **1 cm = 40 m**
- 1:50,000 → 图上 **1 cm = 50,000 cm = 500 m**，故 **2 cm = 1,000 m = 1 km**（Brighton 图幅答案）

> **★ 必须沿垂直于走向（即沿最大坡度）方向量距离**，否则算出的是**视倾角 (apparent dip)**，比真倾角小。

**反向使用（已知倾角画等高线间距）**：
$$d = \frac{\Delta h}{\tan(\text{dip})}$$
- 例（Q3）：dip = 45°，$\Delta h$ = 100 m → $d = 100/\tan 45° = 100$ m
- 例（Q4）：dip = 6°，$\Delta h$ = 5 m → $d = 5/\tan 6° \approx 47.6$ m（故地层等高线间距很宽，符合缓倾）

#### B-4. 要点对照速查表

| 观察到的现象 | 推断 |
|---|---|
| 地质界线 ∥ 地形等高线 | 水平地层，dip ≈ 00 |
| 地质界线为**直线**、横切一切等高线 | 直立面（垂直地层 / 断层 / 岩墙） |
| 地质界线在谷中 **V 向上游** | 向山内倾斜 |
| 地质界线在谷中 **V 向下游**（比河床陡） | 向下游倾斜 |
| **V 尖端指向** | **= 倾向** |
| 地层等高线**直、平行、等间距** | 平面、均匀倾斜 |
| 地层等高线**弯曲** | 走向沿曲线变化（非平面） |
| 地层等高线**间距变化** | 倾角变化（间距窄 = 陡） |
| 地层等高线间距**很宽** | 缓倾 |
| 图上**由北向南出现越来越新的地层** | 地层**向南倾** |
| 黏土层形成**平坦谷地 (clay "vale")** | 软弱易蚀岩性的地貌表现 |

---

## 四、课堂补充

### 上午场：健康与安全 (Health and Safety) —— 完整风险表

| Hazard（危害物） | Risk（风险） | Control Measures（控制措施） |
|---|---|---|
| **0.01 M EDTA** | 造成**严重眼刺激 (serious eye irritation)** | 全程佩戴**护目镜 (eye protection)、实验服 (lab coat)、手套 (gloves)** |
| **pH 10 标准缓冲液 (standard buffer solution)** | **无危害 (not hazardous)** | — |
| **Eriochrome Black T 指示剂**（0.2 g 固体 + 20 ml 乙醇） | Eriochrome Black T 造成**严重眼刺激**；**乙醇 (ethanol) 高度易燃 (highly flammable)** 且造成严重眼刺激 | 全程佩戴护目镜、实验服、手套；**指示剂远离热源/火源 (heat/ignition sources)** |
| **玻璃器皿 (glassware)** | 破损造成**割伤 (cuts)** 风险 | 使用前**检查器皿有无缺陷**；**收拾时、器皿潮湿时尤其小心**；破损物按**正确处置程序 (correct disposal procedure)** 处理 |

### 上午场：ILOs（预期学习成果）

完成本次实践后应能：
1. 执行**微量重量滴定 (microscale gravimetric titration)** 以测定溶液中某化学物种（Ca²⁺ 与 Mg²⁺）的浓度
2. 使用**摩尔比 (molar ratios)** 与**定量摩尔关系**计算物质的质量与浓度
3. 将结果与**英国国家框架 (UK national framework)** 对比，评估并分类水样硬度
4. **评估测量中的不确定度 (evaluate the uncertainties)**

### 上午场：参考文献（讲义列出）

1. **United Utilities** — Water for the North West: Water hardness（有 PDF 概况表可下载）
2. **The Drinking Water Inspectorate (DWI)** — www.dwi.gov.uk，可查英格兰与威尔士各地供水的硬度
3. **Cotruvo J. & Bartram J. (eds.), 2009, WHO** — *Calcium and magnesium in drinking-water: Public health significance*（综述饮用水对每日钙镁总摄入的贡献，及可能的健康益处，含降低心血管疾病死亡率与骨质疏松）
4. **WHO, 2022** — *Guidelines for drinking-water quality*, 4th ed. incl. 1st & 2nd addenda

### 下午场：Practical Class 讲义的 ILOs

完成本次课后应能：
- **描述已出版地质图的各个组成部分 (parts of a published geological map)**
- **描述什么是等高线**，并用地形（等高线）在图上找出不同地貌特征
- **绘制地形剖面 (construct a topographic profile)**〔讲义高亮项〕
- **打开 Digimap 并用它查询格网参考 (Grid References)**〔讲义高亮项〕

### 下午场：图件与资源

- **BGS 在线地图浏览器**（英国多地区高清地质图）——讲义给出 Isle of Wight 图的链接：
  `https://largeimages.bgs.ac.uk/iip/mapsportal.html?id=1004974`
- 讲义中大量图件来自：**Borradaile G. (2014) _Understanding Geology Through Maps_, First Edition, Elsevier, 183 pp.** —— 这是本单元地质图判读的推荐参考书。
- **Digimap**：使用说明在 **BB (Blackboard) 页面**上。

### 下午场：图幅信息（Fig. 4 说明）

Isle of Wight 地质图的两个局部：**格网方格为 1 km**；**北向上**，与**东向格网线 (easting grid lines) 平行**。

---

## 五、Practical 要点

### ══════ 上午场：微量重量滴定测水硬度 ══════

#### 1. 目的 (Aim)

> **测量并评估来自不同产地的水样中的总水硬度 (total water hardness, Ca²⁺ + Mg²⁺)。**

#### 2. 器材与试剂

| 类别 | 明细 |
|---|---|
| **器材** | **10.5 ml 玻璃样品瓶 (glass sample vial)**；**电子天平 (mass balance，读数到 2 位小数)**；**小烧杯 (small beaker)**；**滴管 (dropping pipette)**；**细口 Pasteur 移液管 (fine-tip Pasteur pipette)**（单滴 0.02 ml）；**一张白纸**（垫在瓶下便于观察终点变色） |
| **试剂** | **0.01 M EDTA 标准溶液**；**pH 10 标准缓冲液**；**Eriochrome Black T 指示剂**（滴瓶装）；**若干产地的水样 (stock samples)** |
| **PPE** | 护目镜、实验服、手套（全程） |

#### 3. 操作步骤（逐步，★ 所有质量记录到 2 位小数）

| # | 操作 | 记录到 |
|---|---|---|
| 1 | 把 **10.5 ml 玻璃样品瓶放到天平上**，记录**空瓶质量** | **第 1 列** |
| 2 | 从库存水样中选一种，倒 **2–5 ml** 到小烧杯；**样品瓶仍在天平上**，用滴管往瓶里加 **约 2.5 g** 待测水，记录质量；再算出加入的水样质量 | **第 2 列**（第 6 列 = 列2 − 列1） |
| 3 | 用滴管加入 **约 0.2 g pH 10 标准缓冲液** | — |
| 4 | 从滴瓶加 **2 滴 Eriochrome Black T 指示剂**，**小心旋摇 (swirl carefully)** 混匀 | — |
| 5 | 记录**混合液总质量**（瓶 + 水样 + 缓冲液 + 指示剂） | **第 3 列** |
| 6 | 把样品瓶**从天平取下**，放在**一张白纸上**（便于识别终点变色） | — |
| 7 | 用**细口 Pasteur 移液管**吸取 **0.01 M EDTA 溶液** | — |
| 8 | **加 1 滴 EDTA**，小心旋摇混匀，观察指示剂颜色 | — |
| 9 | **逐滴继续加 EDTA 并旋摇**，直到指示剂由 **红紫 (red-purple) → 蓝 (blue)**，即达终点 | — |
| 10 | 终点时记录**新的混合液总质量**；由此算出加入的 EDTA 质量 | **第 4 列**（第 5 列 = 列4 − 列3） |
| 11 | **重复实验**（新一行），检查是否得到**一致结果 (concordant amounts)**。**理想应取得 3 个一致结果并求平均**。时间不够时可**与同学共享结果**以确认可重复性 | — |
| 12 | 换其他水样，重复整个流程 | — |

> **注意**：**加水样、加缓冲、加指示剂、终点称重都在天平上（或回到天平上）完成**；只有**滴加 EDTA 的过程**在天平外（白纸上）进行，因为需要观察颜色并旋摇。

#### 4. 数据记录表（含讲义给出的示范数据）

| Water sample | **1** 空瓶 | **2** 水样+瓶 | **3** 指示剂+缓冲+水样+瓶 | **4** 终点总质量 | **5 EDTA 加入量**（列4−列3） | **6 水样质量**（列2−列1） |
|---|---|---|---|---|---|---|
| 1 | 8.68 | 11.19 | 11.46 | 12.32 | **0.86** | **2.51** (=11.19−8.68) |
| 1 (repeat) | 8.62 | 11.14 | 11.39 | 12.26 | **0.87** | **2.52** |
| 2 | 8.75 | 11.26 | 11.58 | 11.73 | **0.15** | **2.51** |

（单位均为 g，2 dp）

#### 5. 数据处理 —— 讲义答案逐题吃透

以下按讲义 Data Analysis 的 7 问逐题写全（数据取样品 1）。

---

**Q1. 用一致的质量读数，计算达到终点所加 EDTA 的平均体积。**

答案示范（讲义假设有三个一致读数 0.86、0.87、0.84）：
$$\bar{m}_{\mathrm{EDTA}} = \frac{0.86 + 0.87 + 0.84}{3} = 0.85666\ldots = \mathbf{0.86\ g}$$

由于溶液很稀，可假设密度为 1 g cm⁻³（同纯水），故：
$$\bar{V}_{\mathrm{EDTA}} = \mathbf{0.86\ cm^3} = 0.86 \times 10^{-3}\ \mathrm{l} = \mathbf{0.00086\ l}$$

> 注：结果表里只列了 0.86 与 0.87 两次，第三个 0.84 是讲义为示范平均而补的假设值。

---

**Q2. 计算达到终点所加 0.01 M EDTA 的物质的量。**

已知 $V_{\mathrm{EDTA}} = 0.00086$ l，$c_{\mathrm{EDTA}} = 0.01$ M。把 Equation 1 变形使 moles 成为主语：
$$\textbf{Moles EDTA} = \textbf{concentration EDTA} \times \textbf{volume EDTA}$$
$$n_{\mathrm{EDTA}} = 0.01 \times 0.00086 = \mathbf{8.6 \times 10^{-6}\ mol}$$

---

**Q3. 用理论部分的反应比，求水样中 Ca²⁺ + Mg²⁺ 的物质的量。**

由络合反应方程，**EDTA : 金属离子 = 1 : 1**，所以
$$n(\mathrm{Ca^{2+}} + \mathrm{Mg^{2+}}) = n_{\mathrm{EDTA}} = \mathbf{8.6 \times 10^{-6}\ mol}$$

---

**Q4. 计算 Ca²⁺ + Mg²⁺ 的浓度（mol/l）。**

第 6 列算得水样质量 = **2.51 g**；样品很稀，故体积可视为
$$V_{\text{water}} = 2.51\ \mathrm{cm^3} = \mathbf{0.00251\ l}$$

这部分水中含有 $8.6\times10^{-6}$ mol 的 Ca²⁺ + Mg²⁺（来自 Q3）。用 Equation 1：
$$c(\mathrm{Ca^{2+}}+\mathrm{Mg^{2+}}) = \frac{n(\mathrm{Ca^{2+}}+\mathrm{Mg^{2+}})}{V_{\text{water}}} = \frac{8.6\times10^{-6}}{0.00251} = 3.426\ldots\times10^{-3}\ \mathrm{mol\,l^{-1}}$$

---

**Q5. 把 mol/l 换算成 mg/l。**

> **★ 重要假设**：**假设全部硬度都来自钙离子 (!)**，因此使用**钙的相对原子质量**，而**不是** Ca 与 Mg 原子质量的某种加权平均——因为我们**不知道样品中二者的相对比例**。$A_r(\mathrm{Ca}) = 40.078$ u。

Equation 2 说明质量与摩尔数由 $A_r$ 相联系，因此**摩尔浓度乘以 $A_r$ 即得质量浓度**：
$$\text{Mass concentration} = 3.426\ldots\times10^{-3} \times 40.078 = 0.13731885\ \mathrm{g\,l^{-1}}$$

单位换算到毫克（× 1000）：
$$\boxed{\text{Mass concentration} = \mathbf{137\ mg\,l^{-1}}}$$

（讲义提示：可与**水样瓶上的矿物质含量标签 (sample mineral content label)** 对比）

---

**Q6. 用背景部分 United Utilities / DWI 的框架，评估并分类你的水样硬度。**

$137\ \mathrm{mg\,l^{-1}} > 120\ \mathrm{mg\,l^{-1}}$（mg Ca²⁺/l 列的 "Very Hard" 阈值）
→ 该样品分类为 **"very hard"（极硬水）**。

---

**Q7. 能否对水样源区的地质做出推断？**

答：**有可能，源区的当地地质由富含钙/镁的矿物 (calcium/magnesium-rich minerals) 组成。**

---

**【衍生练习：样品 2 的完整计算】**（讲义未给出，按同一流程自行推演，可作为自测答案）

- $m_{\mathrm{EDTA}} = 0.15$ g → $V = 0.15$ cm³ $= 1.5\times10^{-4}$ l
- $n_{\mathrm{EDTA}} = 0.01 \times 1.5\times10^{-4} = 1.5\times10^{-6}$ mol $= n(\mathrm{Ca^{2+}}+\mathrm{Mg^{2+}})$
- $m_{\text{water}} = 2.51$ g → $V = 2.51\times10^{-3}$ l
- $c = 1.5\times10^{-6} / 2.51\times10^{-3} = 5.976\times10^{-4}$ mol/l
- 质量浓度 $= 5.976\times10^{-4} \times 40.078 = 0.02395$ g/l $= \mathbf{23.9\ mg\,l^{-1}}$
- 分类：落在 **21–40 mg Ca²⁺/l** → **Moderately soft（中度软水）**
- 误差：下界 $-0.01/0.15 \times 100 = -6.7\%$；上界 $+0.03/0.15 \times 100 = +20\%$
  → 范围约 **22.3 – 28.7 mg/l**。相对误差比样品 1 大得多（因为所需 EDTA 量少），且下界已很接近 21 mg/l 的分类边界——**这正是讲义 Q2 所说「硬度越低、百分误差越大、可能跨越分类边界」的具体体现**。

---

#### 6. 不确定度分析 —— 讲义答案逐题吃透

**不确定度的来源与量化（讲义给出的推理链）**

1. **天平**读数到 2 位小数 → **仪器绝对不确定度 = ±0.005 g**。
2. EDTA 质量是**两个质量之差**（列4 − 列3），所以该不确定度要**算两次**：$2 \times (\pm 0.005) = \pm 0.01$ g。
3. **细口 Pasteur 移液管**每滴体积 **0.02 ml (= 0.02 cm³)**；溶液极稀，故对应 **0.02 g**。**最后一滴中所含的 EDTA 可能超过与剩余金属离子络合所需的量**，即加入的 EDTA 比实际需要的**偏多**，最多可多出**几乎整整一滴** → 由「滴」引入的不确定度**最大为 +0.02 g**（**只有正方向**）。
4. 二者合并 → **不确定度是非对称的 (asymmetric)**：
$$\boxed{-0.01\ \mathrm{g} \ \text{到} \ +0.03\ \mathrm{g}}$$
（下界只有天平的 −0.01；上界是天平 +0.01 加上多加一滴 +0.02）

---

**U1. 用每个水样的一个结果，计算上下界的百分误差。**

以结果表中样品 1 的第一个结果 EDTA = 0.86 g 为例：
$$\text{lower bound \% error} = \frac{-0.01}{0.86} \times 100 = \mathbf{-1.2\%}$$
假设终点是在加入**一滴** EDTA 时判定的（+0.02 g），加上两次称量之差引入的 ±0.01 g：
$$\text{upper bound \% error} = +\frac{0.03}{0.86}\times 100 = \mathbf{+3.5\%}$$

---

**U2. 用上述百分误差确定 (Ca²⁺+Mg²⁺) 浓度的最大与最小值（mg/l）。评论这个范围——它会影响硬度分类吗？**

$$-1.2\%\ \text{of}\ 137 = \mathbf{135.4\ mg\,l^{-1}}$$
$$+3.5\%\ \text{of}\ 137 = \mathbf{141.8\ mg\,l^{-1}}$$

**范围 = 6.4 mg/l。**

评论（讲义原答案）：
- 上下界**都 > 120 mg/l**（"very hard" 的阈值），因此**不会改变本样品的分类**。
- **但是**：对**硬度更低的水样**，百分误差会**更大**（因为滴定所需 EDTA 更少，分母更小），此时范围可能大到**跨越两个硬度等级**；或者样品数值本身**离等级分界很近**，误差棒会**跨过分界线**。

---

**U3. 计算总硬度时用了 Ca 的 $A_r$ 而不是 Ca 与 Mg 的加权平均。这个假设对结果准确度有何影响——结果会偏大还是偏小？解释。**

- 我们用 Equation 2（mass = $A_r$ × moles）把摩尔浓度换算成质量浓度。
- $A_r(\mathrm{Mg}) = 24.305$，**远小于** $A_r(\mathrm{Ca}) = 40.078$。若把镁计入，用于换算的原子质量数**应当变小**。
- **结论：质量浓度会比真值偏大 (greater than the true value)。**

---

**U4. 自来水可能经由含铅管道 (lead piping) 输送，会溶入二价铅离子 Pb²⁺。Pb²⁺ 会与 Eriochrome Black T 指示剂分子结合。若样品中存在铅离子，对总硬度结果有何影响？解释。**

- 计算得到的**总水硬度（Ca²⁺ + Mg²⁺ 的质量浓度）会大于真值 (greater than the true value)**。
- 原因：需要**更大体积的 EDTA** 才能与 Ca²⁺、Mg²⁺ **和 Pb²⁺** 都形成络合物（相比无 Pb²⁺ 污染时）。
- 这意味着按 1:1 比推出的 $n(\mathrm{Ca^{2+}}+\mathrm{Mg^{2+}})$ **大于真值**，误差会**沿着整条计算链传播 (propagate)** 到最终的质量浓度。

---

### ══════ 下午场：地质图判读一 ══════

#### 1. 目的

- 认识已出版地质图的各组成部分，读懂图例、比例尺、地层柱状图与剖面
- 掌握 **strike / dip** 的定义、测量与记录格式
- 用**露头图案与地形等高线的关系**推断产状
- 掌握 **三点问题 (three-point problem)** 与 **地层等高线 (stratum contours)** 的作图法，从而在露头稀少的区域**补全地质界线**
- 学会**绘制地形剖面 (topographic profile)** 与使用 **Digimap** 查询英国国家格网坐标

#### 2. 器材

- **模型：一个倾斜平面的实体模型** (model of a dipping plane)
- **水平仪 (spirit level)**——讲义建议用**手机 app**
- **地形图**、**地质图 Sheet 318/333 Brighton & Worthing (1:50 000)**、**Isle of Wight 地质图局部 (Fig. 4)**
- **方格纸 (graph paper)**（画地形剖面）
- **实验记录本 (lab book)**
- **罗盘倾角仪 (compass clinometer)**
- **笔记本电脑 / 手机 / 借用的 iPad**（用 Digimap）；**教室 PC 上打开的 Excel 文件**（汇总全班数据）

#### 3. 讲义 Activities（Practical Class 讲义的 5 项课堂活动）

| # | 活动 | 要点 |
|---|---|---|
| **1** | 看地形图，识别出**河谷 (valley)、陡坡 (steep slope)、缓坡 (gentle slope)、山脊 (ridge)、山丘 (hill)**，并在 lab book 里**画出各自的示例** | 靠等高线密度与形态识别：**密 = 陡**、**疏 = 缓**；**V 形指向上游 = 谷**；**闭合圈 = 丘** |
| **2** | 在图上选一处显示 **谷 / 脊 / 丘** 的位置，在**方格纸**上作**地形剖面**。剖面长度 **15–20 cm**；**必须记录两端的格网参考 (grid references)**；**剖面的垂直比例尺必须与地图的水平比例尺相同**（即**无垂直夸大 vertical exaggeration = 1**） | 作法：沿剖面线放纸条 → 标出每条等高线与剖面线的交点及高程 → 转到方格纸上按高程点绘 → 光滑连线 |
| **3** | 在 lab book 中画出**罗盘方位图**，标出 N、S、E、W 的**度数** | N = 000/360°，E = 090°，S = 180°，W = 270° |
| **4** | 看地质图 **Sheet 318/333 Brighton & Worthing**，回答单独问题纸上的问题 | 答案见下方逐题梳理 |
| **5** | 打开 **Digimap**（照 BB 页面上的说明），查出**你家所在位置的英国国家格网 (British National Grid) 东坐标 (Easting) 与北坐标 (Northing)**，例如 `385708, 378225`；到教室 PC 上把数值填进已打开的 Excel 文件。全班的数值会用 Digimap 绘制成一张全英国的分布图。**非英国学生**可填 **Alderley Edge** 或 **Mam Tor** 的坐标 | 英国国家格网为 6 位 Easting + 6 位 Northing（1 m 精度） |

#### 4. 讲义 Exercises 逐题梳理（Geological maps 1）

---

**Exercise 1：观察倾斜平面的模型，找出走向线与最大倾角。用水平仪（手机 app）检查走向线确实是水平的。**

- **要点**：**走向线的判据就是「水平」**。在倾斜平面上有无数条方向不同的线，只有一族方向的线是水平的——那就是走向线。
- **最大倾角**必须沿**垂直于走向**的方向量；任何其他方向量到的都是**视倾角 (apparent dip)**，数值**偏小**。
- 讲义 Fig. 1 的示例产状记为 **180/60 E**。

---

**Exercise 2：Isle of Wight 地质图两个局部（Fig. 4a、4b，格网 1 km，北向上）**

> **说明：本周材料中未提供 Exercise 2 的书面答案文件**，以下是依据讲义原理应作的推理（判读逻辑必须掌握）。

**(1) Fig. 4(a) 中，观察地质接触界线与地形等高线的相互关系，你能推断该区地层的倾角如何？**
- 判读逻辑：看界线**在多大程度上「跟随」等高线**。
- 若界线**大体平行/贴合等高线**并随地形起伏而弯曲 → 地层**倾角很缓、接近水平**（对应 Fig. 2a 的极端情形）。
- 关键的量化标准：界线跟随地形的程度越高 → 倾角越小。

**(2) 与 Fig. 4(b) 比较，你推断它的倾角相对 (a) 如何？**
- 判读逻辑：若 (b) 中界线**更笔直、更少理会等高线、更明显地横切等高线** → 相对 (a) **倾角更陡**（趋近 Fig. 2b 的直立情形）。
- 反之若 (b) 的界线比 (a) 更贴合等高线 → 相对 (a) 更缓。**答案取决于图上实际形态，方法是恒定的：横切程度 ∝ 倾角。**

**(3) 看 (b) 中标为 'X' 的特征，基于你的观察，该区地层的倾向是哪个方向？**
- 判读逻辑：**X 处应是一个 V 形（河谷处的界线弯折）**。
- 应用 **V 字法则**：**V 的尖端 (apex) 指向接触面的倾向**。
- 因此读出 V 尖端所指的罗盘方向，即为倾向。再可用地层柱状图（老→新）交叉验证。

---

**Exercise 3：完成平面倾斜地层的地图（三点问题）**

题设：图上画有一条**薄煤层 (thin coal seam) 的露头**（**实心黑线**），**上方是较年轻的砂岩 (younger sandstone)**，**下方是较老的页岩 (older shale)**（图上用 **younging symbols** 标出变新方向）。**虚线是地形等高线（单位 m）**。等高线呈**特征性的向高程方向 V 形**，指示**煤层正在穿过一个河谷**。

**3.1 完成平面倾斜地层的地图（三点问题）。**
→ 按第三节 B-2 的九步流程作图：找地质界线 × 地形等高线的交点 → 连等高点成地层等高线 → 检验其平行等间距 → 外推补齐 → 由地层等高线与同高程地形等高线的交点连出完整露头界线。

**3.2 露头图案与地形等高线的相互关系可以用来判断煤层的倾向。推断的倾向是什么？**
→ 用 **V 字法则**：河谷处煤层露头形成的 **V 的尖端所指方向 = 倾向**。
→ 交叉验证：煤层**之上是较年轻的砂岩**，故**倾向应指向砂岩出露的一侧**（老 → 新）。

**3.3 除了外推地质界线，结构等高线还可用来计算地层的走向与倾角。假设地图比例尺为 1:4,000，计算倾角并量出走向。用 strike/dip 与倾向的格式记录答案。**
→ 步骤：
1. 量出**相邻两条地层等高线之间、垂直于走向方向的图上距离** $d_{\text{map}}$（cm）
2. 换算到地面：$d = d_{\text{map}} \times 4000$ cm $= d_{\text{map}} \times 40$ m（**1:4,000 ⇒ 1 cm = 40 m**）
3. 取相邻地层等高线的**高程差** $\Delta h$（等于地形等高线间隔）
4. $\text{dip} = \arctan(\Delta h / d)$
5. 用量角器量地层等高线的方位角 = **strike**（3 位数）
6. 倾向 = 地层等高线**高程降低**的一侧（并与 3.2 的 V 字法则结果一致）
7. 写成 **strike/dip 倾向**，例如 `076/45 NW`

> 本周材料中未附 Exercise 3 的数值答案；掌握流程与单位换算即可。

---

**Exercise 4：完成地图（三点问题）。标出地层的走向与倾角，并指出哪一层更老。**

→ 同样按 B-2 流程；额外两点：
- **走向与倾角要用标准的 strike/dip 符号**（长线 = 走向，短垂线 = 倾向，数字 = 倾角）标在图上
- **判断新老**：用 **younging symbol**；或用**叠覆律**——沿倾向方向出露的地层更新，反倾向方向的更老

---

#### 5. 答案文件逐题梳理

---

##### 【Q3soln】「已知露头与倾角信息，补全地图」

**题目原文**：*"Completing a map given exposure and dip information. The map below shows some exposures of sandstones and mudstones (shaded), together with some information about the dip of the beds. Assuming a **uniform strike and dip**, complete the boundary between the two units for the whole map."*

**题设**：图上给出若干**砂岩 (sandstone)** 与**泥岩 (mudstone，阴影)** 的**出露点 (exposures)**，以及**关于地层倾角的一些信息**。假设**走向与倾角均匀**，为整张图补全两个单位之间的界线。

**解答图中出现的关键信息**（从 PDF 转出的文字碎片重建）：
- 图中有 **N 箭头**（北向标注）
- 一系列**地层等高线的高程标注**：`-300 -200 -100 0 100 200 300 400 450 500 600 700 800 900 1000 1100`
  → 即**地层等高线以 100 m 为间隔**（450 m 是插入的一条），且**外推到负高程 (−100、−200、−300 m)**，代表该地质面**延伸到海平面基准以下**
- 重复标注的 **`45`** 与 **`45 0`** / **`450 m`** —— 前者是**倾角 45°**，后者是 **450 m 的地层等高线**
- **`200 m`**、**`450 m`** 等具体高程标签

**★ 最终答案（解答文件明确给出）：**
$$\boxed{\textbf{076/45 NW}}$$
即：**走向 076°，倾角 45°，向西北 (NW) 倾。**

**思路复盘**：
1. 由若干出露点确定同一接触面上的若干**已知高程点**
2. 连接**等高点** → 得到**直的、平行的、等间距的地层等高线**（因为题设「uniform strike and dip」）
3. 量地层等高线方位角 → **走向 = 076°**
4. 用 $\tan(\text{dip}) = \Delta h / d$：相邻地层等高线 $\Delta h = 100$ m，**倾角 45°** ⇒ 图上水平间距对应地面 $d = 100/\tan 45° = 100$ m（即地层等高线间距在地面上恰好等于高差，这是 45° 倾角的特征）
5. 地层等高线高程**向 NW 方向递减** ⇒ **倾向 NW**（与走向 076° 垂直的两个方向是 NNW≈346° 与 SSE≈166°，取高程降低的那侧）
6. 把地层等高线与**同高程的地形等高线**求交，把交点连成光滑曲线 → 补全整张图的砂岩/泥岩界线

**可迁移的要点**：
- 地层等高线可以**外推到图外与负值**——这不是错误，负高程代表该面在**海平面之下 / 地下**的延伸
- **45° 倾角是一个便利的自检点**：$\tan 45° = 1$，地层等高线的地面间距 = 等高线高差

---

##### 【Q4soln】「已知接触点位置，补全地图」

**章节标题**：**THE ORIENTATION OF SURFACES (1)**（面的产状 一）

**题目原文**：*"Completing a map given the position of contacts. The map below shows a hillside **contoured at 5 m intervals** and **three locations where a seam of coal is exposed**. Complete the location of the remainder of the seam outcrop **assuming that it dips uniformly** across the area covered by the map. **Shade the area which lies above the seam.** State the strike/dip and dip/dip direction of the coal seam."*

**题设拆解**：
- 一片山坡，**地形等高线间隔 5 m**（图中出现的高程标注：5, 10, 15, 20, 25, 30, 35, 40, 45, 50 m）
- **三处煤层出露点**（这就是「三点问题」的三个点）
- 假设**均匀倾斜**
- 要求：(a) 补全煤层露头的其余部分；(b) **把位于煤层之上的区域涂阴影**；(c) 给出 **strike/dip** 与 **dip/dip direction** 两种格式的产状
- 图中另有 **N 箭头** 和 **比例尺 `0 50 100 m`**

**★ 最终答案（解答文件明确给出）：**
$$\boxed{\textbf{Orientation of coal seam : 119/6 SW} \;=\; \textbf{6/209}}$$

**两种记法的对应关系**：
- **119/6 SW** = 本课程标准格式：**走向 119°，倾角 6°，向西南倾**
- **6/209** = 另一种常用格式：**倾角 6°，倾向方位角 209°**
- 验算：$119° + 90° = 209°$ ✓，且 209° 落在 SW 象限（180°–270°）✓

**思路复盘**：
1. 三个煤层出露点分别落在（或可内插到）不同高程的地形等高线上 → 得到煤层面上三个**已知高程点**
2. 若两点同高程，直接连线得地层等高线；若三点高程各不相同，用**经典三点法**：在最高点与最低点的连线上，按**线性内插**找出与中间点等高的位置，连接该位置与中间点 → 得到一条**走向线**；再按等间距平行外推其余地层等高线
3. 量走向线方位角 → **strike = 119°**
4. 倾角：$\Delta h = 5$ m（等高线间隔），$\tan(6°) = 0.1051$ ⇒ 地层等高线的地面间距 $d = 5/0.1051 \approx \mathbf{47.6\ m}$。这与比例尺条 `0–50–100 m` 相符：地层等高线间距接近「50 m」刻度长度，属**很缓的倾斜**
5. 倾向：地层等高线高程向 **SW** 降低 ⇒ 倾向 SW (209°)
6. 补全露头：地层等高线 × 同高程地形等高线 → 交点连线
7. **阴影区（above the seam）**：煤层面之上的部分 = 地面高程**高于**该处煤层面高程的区域，也就是在**上倾方向 (up-dip side)** 一侧、即**东北 (NE) 一侧**、地形较高处；实操上，在图上任一点比较「地形等高线高程」与「地层等高线高程」，地形更高 ⇒ 该点地表位于煤层之上 ⇒ 涂阴影

**★ 关键概念**：这道题让你区分**倾角 6°（极缓）与倾角 45°（陡）** 在图上的表现——**倾角越缓，地层等高线间距越宽，露头图案越贴合地形等高线**。6° 时露头会大幅度地随地形起伏蜿蜒；45° 时露头几乎笔直地切过地形。

---

##### 【Brighton Map Answers】Sheet 318/333 Brighton and Worthing 1:50 000 Scale Geology Series —— 逐题答案

**Q1. 最新版本的出版日期？**
→ **2006 年**

**Q2. 最初的地质测量 (original geological survey) 何时出版？**
→ **1864 年**
（即这张图的测绘工作跨越了 140 多年，体现地质图的长期积累性）

**Q3. 最初的测量人之一是 W B Dawkins——查一查他，他与曼彻斯特有什么联系？**
→ **William Boyd Dawkins** 后来成为 **Manchester Museum 的馆长 (Curator)**，并且是 **Owens College（后发展为 University of Manchester）的第一位地质学教授 (first Professor of Geology)**。系里的 Study（自习室）藏有他原始藏书的一部分，开放时欢迎学生查阅这些历史书籍。

**Q4. 这张图的比例尺是多少？**
→ **1:50,000**

**Q5. 图上 2 cm 代表地面上多长距离？**
→ 1 cm = 50,000 cm = **500 m**，所以 2 cm = 500 × 2 = **1000 m = 1 km**
$$\text{地面距离} = \text{图上距离} \times 50{,}000$$

**Q6. 什么是 Bedrock（基岩）与 Superficial Deposits（表层沉积）？**
→
- **Bedrock（基岩）**：已**固结成岩的 (lithified)** 岩石，按 **Formation（组）** 分组。它们在图例的 **Generalized Vertical Sections（概化垂直剖面）** 中**按地层顺序 (stratigraphic order)** 展示，**最老的在剖面底部**。
- **Superficial Deposits（表层沉积）**：**未固结的 (unconsolidated / loose)** 沉积物，按**类型**分组（例如 beach and tidal flat deposits 海滩与潮坪沉积）。它们在图例中**不按叠覆顺序（年代顺序）排列**。

> **★ 这是读图例时最容易混淆的一点**：基岩图例是**有年代顺序的**，表层沉积图例**没有**。

**Q7. 最老的岩石组出露在图幅的哪个象限 (N/S/E/W)？**
→ 最老的组是 **Wadhurst Clay Formation**，出现在图幅的 **NE（东北）部分**，位于 **Section 2 的北端 (GR 3271 2220)**。
→ Wadhurst Clay Formation 属于 **Wealden Group**，时代为 **Lower Cretaceous（下白垩统）**。

**Q8. 你认为各组中的地层是水平层还是倾斜的（即偏离原始水平姿态）？解释你的答案并说明用了什么证据。**
→ **地层是缓倾的（小于 8 度），向南 (towards the South) 倾。**
→ **证据（三条，互相印证）**：
1. **图上的倾向箭头 (dip arrows)**
2. **看垂直剖面 (vertical cross sections)**
3. **地图显示越往南出露的组越年轻 (younger formations outcropping towards the South)**，与倾向一致——这正是「**倾向由老指向新**」规则的实际应用

**Q9. 找到 Gault Formation。Gault 出露处地表的高程范围是多少？**
→ **Gault Formation 形成一片黏土「谷地」(clay "vale") 或平坦低地 (flat lying area)**。**高程为 53 m 与 34 m。**
→ **地貌与岩性的联系**：黏土软弱易蚀，因此形成低平的谷地；而抗蚀的砂岩/灰岩形成山脊 (ridge) 与陡崖 (escarpment)。这是「**地形反映岩性**」的典型例证。

---

## 六、易错点 / 重点难点

### 上午场（化学）

| # | 易错点 | 正确做法 / 提醒 |
|---|---|---|
| 1 | **单位换算漏掉** cm³ → l | 讲义原文加粗提醒 **"check units!"**。必须 **÷1000**；最终答案 **g/l → mg/l 要 ×1000** |
| 2 | **对照错列** | 最终答案是 **mg Ca²⁺/l**，要对照分级表的**第二列**（20/40/60/80/120 阈值），**不是** mg CaCO₃/l 那列（50/100/150/200/300） |
| 3 | 忘记 **1:1 反应比**的来源 | 来自 EDTA 是**六齿配体**、一个 EDTA 分子包裹**一个**金属阳离子。$n(\mathrm{M}) = n(\mathrm{EDTA})$ |
| 4 | **列 5 与列 6 算反** | **列 5（EDTA 加入量）= 列 4 − 列 3**；**列 6（水样质量）= 列 2 − 列 1**。讲义在表头都加了感叹号强调 |
| 5 | 用 Ca、Mg 的**平均原子质量** | **不能**——我们**不知道 Ca 与 Mg 的相对比例**，所以按惯例**只用 $A_r(\mathrm{Ca}) = 40.078$**，并明确这是一个**会使结果偏大**的假设 |
| 6 | 认为不确定度是**对称的** | **不对称**：**−0.01 g / +0.03 g**。下界只有天平的两次读数误差；上界还要加上「最后一滴可能整滴过量」的 **+0.02 g** |
| 7 | 忘记天平误差要**算两次** | 因为 EDTA 质量是**两个称量值之差**：$2 \times \pm0.005 = \pm0.01$ g |
| 8 | 认为误差范围**永远不影响分类** | 只有本例（137 mg/l，远高于 120）不受影响。**硬度越低 → 所需 EDTA 越少 → 百分误差越大**，误差棒可能**跨越分类边界** |
| 9 | 混淆 **hard/soft 的管道效应** | **硬水 → 结垢 (scale)、堵管**；**软水 → 腐蚀金属管道更快**。别记反 |
| 10 | 认为硬水有健康风险 | WHO **不设指导值**，饮用水中的硬度**不被视为健康问题**；只有 [Ca²⁺] > 100 mg/l 时会有**口感 (taste)** 问题 |
| 11 | **忘记加 pH 10 缓冲液**或不理解其作用 | EDTA 必须在 **pH 10** 下才处于**完全去质子化**形式，才能有效络合金属离子。缓冲液不是可选步骤 |
| 12 | **旋摇过猛 / 一次加太多 EDTA** | 终点判断靠**逐滴**加入 + **小心旋摇 (swirl carefully)**；一次多加会直接冲过终点，放大 +0.02 g 那部分误差 |
| 13 | 忘记**垫白纸** | 红紫 → 蓝的变色在白底上才容易辨认 |
| 14 | 只做一次就下结论 | 必须做到 **concordant results**，理想是 **3 个一致结果取平均**；时间不够则**与同学共享数据** |
| 15 | Pb²⁺ 污染影响判断错方向 | Pb²⁺ 也会消耗 EDTA → **需要更多 EDTA** → 推出的 $n(\mathrm{Ca^{2+}}+\mathrm{Mg^{2+}})$ **偏大** → 最终硬度**偏大** |

### 下午场（地质图）

| # | 易错点 | 正确做法 / 提醒 |
|---|---|---|
| 1 | **Outcrop 与 Exposure 混用** | **Exposure** = 野外岩石真正裸露、可站可测的地点；**Outcrop** = 地图上表示该组「若出露于地表则会分布」的范围 |
| 2 | 沿**任意方向**量倾角 | 倾角**必须沿垂直于走向的方向**量（最大坡角）。斜着量得到的是**视倾角 (apparent dip)**，**永远小于真倾角** |
| 3 | **V 字法则记反** | **V 的尖端指向倾向 (apex points in the dip direction)**。注意区分「地形等高线的 V 指向上游」与「地质界线的 V 指向倾向」——这是**两件不同的事** |
| 4 | 忘了 V 字法则的**两个例外** | **水平地层**（界线与等高线重合，不形成独立的 V）与**直立地层**（界线笔直穿过，不弯折） |
| 5 | 忽略**倾向由老到新**的前提 | 该规则**对倒转 (overturned) 地层不成立**。本周只处理简单情形，但要知道有此限制 |
| 6 | 写产状**位数不对** | **strike 永远 3 位数**（如 076、119、180）；**dip 永远 2 位数**（如 06、45、90）；**必须给出倾向**（如 SW、E） |
| 7 | 两种产状格式**换算出错** | `strike/dip 倾向` ↔ `dip/倾向方位角`。倾向方位角 = 走向 ± 90°，取**指向下倾一侧**的那个。核对 Q4：119 + 90 = 209 (SW) ✓ |
| 8 | 地层等高线**不平行/不等间距**却不检查 | 若题设是「uniformly dipping planar bed」，则地层等高线**必须**是**直的、平行的、等间距的**。作图出来若不满足，说明找点或连线错了 |
| 9 | 混淆**地形等高线**与**地层等高线** | 地形等高线 = 地表面的等高线（图上通常虚线或棕线）；地层等高线 = **某个地质面**（层面/断层面/煤层面）的等高线，是**我们自己画上去的构造线** |
| 10 | 忘记**地层等高线可以是负值** | Q3 解答中出现 −100、−200、−300 m，代表该地质面延伸到**基准面以下**。这是正常的、必要的外推 |
| 11 | **比例尺换算算错** | 1:4,000 ⇒ 1 cm = 40 m；1:50,000 ⇒ 1 cm = 500 m。计算倾角时**必须换成地面真实距离**，不能直接用图上厘米数 |
| 12 | 地形剖面加了**垂直夸大** | 讲义明确要求：**剖面的垂直比例尺必须与地图的水平比例尺相同**。否则读出的坡度与倾角会失真 |
| 13 | 剖面**没记两端格网参考** | 讲义硬性要求记录剖面两端的 **grid references**，且剖面长度 **15–20 cm** |
| 14 | 忘记 **Superficial Deposits 图例不按年代排序** | 只有 **Bedrock** 的 Generalized Vertical Sections 是**按地层顺序、最老在底**；表层沉积按**类型**分组 |
| 15 | 判断倾向只用**一条**证据 | Brighton 答案示范了**三重证据交叉验证**：dip arrows + cross sections + 越南越新的地层出露 |
| 16 | 忽视**岩性—地貌的对应** | Gault Formation（黏土）形成**平坦谷地 (clay vale)**，高程仅 34–53 m。地形本身就是判读岩性的线索 |
| 17 | 忘记**接触界线线型**的含义 | 实线 = 完全确信；虚线 = 有不确定性；虚线加问号 = 非常不确定 |
| 18 | 认为「三点问题」需要三个**同高程**的点 | 不需要。若三点高程各异，用**线性内插**：在最高点—最低点连线上找出与中间点等高的位置，连线即得走向线 |

---

## 七、本周术语表

### 上午场：化学 / 水化学

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Water hardness | 水硬度 | 水中 Ca²⁺ 与 Mg²⁺ 离子含量的量度，由当地地质决定 |
| Titration | 滴定 | 用已知浓度的标准溶液逐滴反应，由消耗量求未知物浓度的定量方法 |
| Gravimetric (titration) | 重量（滴定）法 | 用**称质量**代替读体积来测定加入的标准溶液量 |
| Microscale | 微量化 | 大幅缩小试剂用量的实验方式，省资源但相对误差更大 |
| EDTA (ethylenediaminetetraacetic acid) | 乙二胺四乙酸 | 本实验的标准溶液（0.01 M），与二价金属离子按 1:1 络合 |
| Ligand | 配体 | 能向金属离子提供孤对电子形成配位键的分子/离子 |
| Hexadentate ligand | 六齿配体 | 有 6 对孤对电子、可从 6 个位点结合同一金属离子的配体（EDTA 即是） |
| Monodentate ligand | 单齿配体 | 只从 1 个位点结合金属离子的配体（如水分子） |
| Polydentate ligand | 多齿配体 | 可从多个位点结合的配体的统称 |
| Chelate effect | 螯合效应 | 多齿配体取代多个单齿配体时因**粒子数增多、熵增**而使络合特别稳定的现象 |
| Complexation reaction | 络合反应 | 金属离子与配体结合形成络合物的反应 |
| Deprotonated | 去质子化的 | 已把酸性氢离子给出的形态；EDTA 在 pH 10 时完全去质子化 |
| Divalent metal cation | 二价金属阳离子 | 带 2+ 电荷的金属离子，如 Ca²⁺、Mg²⁺、Pb²⁺ |
| Eriochrome Black T | 铬黑 T | 络合滴定指示剂；有游离 Mg²⁺ 时红紫，全部络合后变蓝 |
| End point | 终点 | 指示剂发生规定颜色变化的时刻（本实验：红紫 → 蓝） |
| Buffer solution | 缓冲溶液 | 维持恒定 pH 的溶液；本实验用 pH 10 标准缓冲液 |
| Concordant results | 一致结果 | 多次重复测得的、彼此接近可取平均的结果 |
| Pasteur pipette (fine-tip) | （细口）巴斯德吸管 | 逐滴加液用的玻璃/塑料吸管；本实验单滴约 0.02 ml |
| Scale | 水垢 | 硬水加热时碳酸氢盐热分解沉积出的固体钙镁化合物 |
| Thermal decomposition | 热分解 | 受热而分解的反应，此处指碳酸氢盐受热生成碳酸盐沉淀 |
| Bicarbonate | 碳酸氢盐 | HCO₃⁻，硬水中溶解态钙镁的主要伴生阴离子 |
| Relative atomic mass ($A_r$) | 相对原子质量 | 元素原子的相对质量；Ca = 40.078，Mg = 24.305 |
| ppm (parts per million) | 百万分之一 | 稀水溶液中数值上等于 mg/l |
| Absolute uncertainty | 绝对不确定度 | 仪器读数本身的不确定量，如 2 dp 天平为 ±0.005 g |
| Percentage error | 百分误差 | 绝对不确定度除以测量值再乘 100% |
| Asymmetric uncertainty | 非对称不确定度 | 正负方向大小不等的不确定度（本实验为 −0.01 / +0.03 g） |
| Propagate (error) | （误差）传播 | 早期步骤的误差经计算链传递到最终结果 |
| DWI (Drinking Water Inspectorate) | 饮用水监察局 | 英国饮用水质量监管机构，发布硬度分级 |
| WHO | 世界卫生组织 | 发布饮用水质量准则；目前不为硬度设指导值 |

### 下午场：地质图学

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Topographic map | 地形图 | 显示地表物理特征及其相对基准面高度的地图 |
| Geological map | 地质图 | 显示若无表层覆盖时会出露地表的岩石地层单位的地图，叠加在地形图上 |
| Contour (line) | 等高线 | 连接等高程各点的线，**永远水平** |
| Datum level | 基准面 | 高程测量的零点参考面（英国通常为平均海平面） |
| Relief | 地形起伏 | 地表高程的变化幅度 |
| Superficial deposits | 表层沉积 | 未固结的松散沉积物，按类型而非年代分组 |
| Bedrock | 基岩 | 已固结成岩的岩石，按 Formation 分组、按地层顺序排列 |
| Bed | 层 | 最小的地层学单位，单次流动事件沉积的单层 |
| Bedding plane | 层面 / 层理面 | 层与层之间的界面，其产状用于推断构造 |
| Formation | 组 | 共享岩性或沉积构造特征、图上可辨的一组层 |
| Lithostratigraphic | 岩石地层的 | 按岩性划分地层单位的 |
| Stratigraphic column | 地层柱状图 | 按老在下、新在上排列图上各 formation 的柱状图 |
| Law of Superposition | 地层叠覆律 | 未扰动时下伏者老、上覆者新 |
| Law of Original Horizontality | 原始水平律 | 地层最初近似水平沉积 |
| Younging symbol | 变新方向符号 | 图上指示地层由老变新方向的符号 |
| Contact | 接触界线 | 图上两个不同 formation 之间画的线 |
| Exposure | 出露（点） | 野外岩石真正裸露、可站上去测量的地点 |
| Outcrop | 露头（分布） | 地图上某 formation 若出露于地表所占的范围 |
| Outcrop pattern | 露头图案 | 岩体三维形态与地表面相交所形成的平面图形 |
| Strike | 走向 | 平面上一条水平线的方位角，写 3 位数 |
| Dip | 倾角 | 平面的最大坡角，垂直于走向，写 2 位数 |
| Dip direction | 倾向 | 最大坡度向下的罗盘方向 |
| Apparent dip | 视倾角 | 沿非垂直走向方向量得的倾角，总是小于真倾角 |
| Compass clinometer | 罗盘倾角仪 | 野外测量走向与倾角的仪器 |
| Azimuth | 方位角 | 以正北为 0° 顺时针度量的罗盘方位 |
| Stratum contour / Structure contour | 地层等高线 / 构造等高线 | 画在某地质面（层面、断层面、煤层面）上的等高线 |
| Three-point problem | 三点问题 | 由同一接触面上三个已知点求其走向、倾角并补全界线的作图法 |
| Planar / plane-dipping layer | 平面（均匀倾斜）层 | 可视为几何平面、倾角处处相同的地层 |
| Uniform strike and dip | 均匀走向与倾角 | 全区产状不变的假设条件 |
| Topographic profile | 地形剖面 | 沿一条测线绘制的地表高程剖面图 |
| Vertical exaggeration | 垂直夸大 | 剖面垂直比例尺相对水平比例尺放大的倍数；本课要求为 1（不夸大） |
| Grid reference | 格网参考 | 英国国家格网上的位置编码（Easting, Northing） |
| Easting / Northing | 东坐标 / 北坐标 | 英国国家格网中向东/向北的坐标值 |
| British National Grid | 英国国家格网 | 英国统一的平面坐标参考系统 |
| Digimap | Digimap | 英国高校用的在线地图与空间数据服务平台 |
| BGS (British Geological Survey) | 英国地质调查局 | 英国地质图的编制与出版机构 |
| Ordnance Survey (OS) | 英国陆地测量局 | 英国地形图的编制与出版机构 |
| Fault | 断层 | 岩石沿其发生位移的破裂面；近直立时在图上呈直线切过等高线 |
| Dyke | 岩墙 | 切割围岩的板状侵入体；近直立时图上表现同断层 |
| Coal seam | 煤层 | 薄层状煤，常作为地质图练习中的标志层 |
| Vale | 谷地 / 平坦低地 | 软弱岩性（如黏土）差异侵蚀形成的低平地形 |
| Wealden Group | Wealden 群 | 英格兰东南部的下白垩统地层群 |
| Wadhurst Clay Formation | Wadhurst 黏土组 | Brighton 图幅上最老的组，属 Wealden Group，下白垩统 |
| Gault Formation | Gault 组 | Brighton 图幅上形成黏土谷地的组，出露高程 34–53 m |
| Generalized Vertical Section | 概化垂直剖面 | 地质图图例中按地层顺序展示基岩各组的柱状图 |
