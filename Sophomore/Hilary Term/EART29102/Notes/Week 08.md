# EART29102 Geospatial Techniques — Week 08 学习笔记

> 授课日：23-Mar（Hilary Term, Week 08）
> 材料：`Lecture 8 Spatial Visualisation`（讲义，1,354 词）＋ `EART29102 - 23-Mar-transcript`（课堂录音转写，5,242 词）＋ `Practical 8 - Solar radiation mapping and map layout`（ArcGIS Pro 实操教程，2,658 词）
> 本周主题：**空间可视化（Spatial Visualisation）** —— 老师原话：*"today's lecture then is on spatial visualization, which is rather grand way of saying maps. Really, we're going to be talking about maps."*

---

## 一、本周主题

### 1.1 本周在全课骨架中的位置

本课程实际骨架（**以讲义与 practical 实际内容为准，不是官方大纲**）：

**基础段** W01 GIS 导论 → W02 空间数据与数据管理 → W03 数据输入与操作
→ **分析段** W04 空间分析 → W05 空间统计
→ **专题段** W06 遥感 → W07 地形分析 → **W08 空间可视化** → W09 三维技术
→ **W10 课程回顾**

本周是**专题段的第三块**，也是全课在方法论上的一个转折点。

W01–W03 解决的是「数据怎么进 GIS、怎么管」；W04–W05 解决的是「怎么算出结论」；W06–W07 解决的是「怎么从遥感影像和 DEM 里挖出专题信息」。这些环节的产物都是**分析结果**——一张符号系统随手设的工作地图、一堆栅格、一列统计量。**W08 要回答的是最后一个问题：这些结果怎么变成一份别人看得懂、看得对、看得进去的地图产品。**

老师在开场就明确划出了这条界线（转写）：

> "GIS is very good at making maps for you, and **most of those maps are kind of working maps that you're using to interpret data**. Of course, there will be times when you need to produce a **presentation-style map**, for example, for your assessment."

这句话是理解本周定位的关键：

| | working map（工作地图） | presentation map（展示地图） |
|---|---|---|
| 目的 | 自己看，边做边判断 | 给别人看，传达一个明确信息 |
| 符号系统 | 软件默认即可 | 必须经过 selection / classification / symbolisation 三层设计 |
| 版面 | 无所谓 | 必须有完整的 cartographic elements 与视觉层次 |
| 前 7 周产出的多半是 | ✅ | |
| 本周要求你产出的是 | | ✅ |

### 1.2 本周与前面各周的接续点

- **与 W03（数据输入与操作）**：W03 讲的 geographic coordinate system 与 map projection，本周从「几何正确性」角度重讲一遍，变成「**选哪种投影取决于你的地图要传达什么**」（equal area / conformal / equidistant）。老师明确说 *"We did talk a little bit about this when we were talking about geographic coordinate systems and map projections a few lectures ago."*
- **与 W05（空间统计）**：W05 的 classification（把数据分箱）在本周变成 cartographic classification —— 同一份数据换一种分级方法，**地图会讲出完全不同的故事**。
- **与 W07（地形分析）**：本周讲义里的 hillshade、hypsometric map、isoline map、2.5D 表面，全部是 W07 地形分析工具的**可视化出口**；本周 practical 用的 slope / aspect / hillshade 也直接沿用 W07 的工具链。
- **与 W09（三维技术）**：本周结尾的 2.5D、voxel、animated mapping 是 W09 的引子。老师说下一次课由 **Rufus Brunt** 讲 3D visualization。

### 1.3 讲义列出的本周内容（Lecture content 原文）

1. The basic elements of a map.（地图的基本要素）
2. Map types and projections.（地图类型与投影）
3. How to design a map and effective layout.（地图设计与有效版面）
4. Visual hierarchy.（视觉层次）
5. Map lettering and placement.（地图注记与放置）
6. Multivariate maps.（多变量地图）
7. Animated maps.（动画地图）

### 1.4 Practical 的学习目标（原文）

By the end of this practical you will be able to:

- **Estimate solar energy production for an area of Greater Manchester.**（估算大曼彻斯特某区域的太阳能产量）
- **Apply surface parameters to exclude unfavourable aspect and roof slopes.**（用表面参数剔除不利的坡向与屋顶坡度）
- **Be able to produce an effective map layout.**（产出有效的地图版面）

### 1.5 ⚠️ 关于本周材料的结构，必须先知道

**讲义（PDF 转 md）大部分是「只有标题和图注、没有正文」的图片幻灯片。** 例如 `# Cartographic elements`、`# Visual hierarchy`（第二张）、`# Map layout`、`# Effective map layout design`、`# Multivariate mapping`、`# Bivariate choropleth map`、`# 3D perspective view`、`# Stepped statistical surface` 这些标题下**一个字都没有**——因为原页面是整页图。

因此：**本周的信息主体在 5,242 词的转写里，讲义只提供骨架和少量图注。** 复习时若只看讲义会漏掉一大半内容。

**关于低质量 OCR 段（重要）**：讲义 md 末尾有一节 `## OCR 补充（原文中无文字层的页面）`，明确标注「识别质量低——原件疑为手写或图件，文字大多不可靠」。涉及 **Page 2、Page 18、Page 26、Page 27、Page 29、Page 31** 六页。其中：

| 页 | 主题 | OCR 可用性 |
|---|---|---|
| Page 2 | Cartographic elements（地图要素标注图） | **基本可用**——要素名（Title / North arrow / Map body / Legend / inset / Scale bar / Credits / Neatline / Other text information）全部识别正确，可据此还原那张图 |
| Page 18 | Visual hierarchy | **完全不可用**——识别结果为 `S GUYS" ERRGT. / Be AW? / SEN / oN / < / so / MS`，纯乱码，无任何信息 |
| Page 26 | Map layout（墨尔本高收入家庭图） | **部分可用**——版面要素名可读，但**图例数值被严重误识**（详见文末勘误表） |
| Page 27 | Effective map layout design | **无内容**——只有标题 |
| Page 29 | Bivariate choropleth map | **仅标题 + 图题**（1997 World Rural Population Density and Arable Land） |
| Page 31 | Stepped statistical surface | **无内容**——只有标题 |

**下文凡引用自这六页的内容，我都会明确标注「（来自低质量 OCR 段）」。** Page 18 与 Page 27、31 的实质内容只能靠转写还原。

Practical 的 md 也有 OCR 后遗症：目录与部分正文出现 `ti` 连字丢失（`Introducton`、`generaton`、`tps`、`efect`、`htps://`），以及末页示例地图（Page 14）的 OCR 严重残缺。这些都不是内容错误，属于转换伪影。

---

## 二、核心概念

### 2.1 地图的构成要素（Cartographic elements）

这是本周最基础也最必须背下来的一张清单。来源：讲义 Page 2（低质量 OCR 段，但要素名识别可靠）＋ 转写中老师逐项讲解。

| 要素（英） | 中文 | 必要性 / 老师怎么说 |
|---|---|---|
| **Map body** | 图面主体 | *"the most important thing to display, and it sort of takes center of the page"*。**必备。** 显示地理区域＋符号化＋注记 |
| **Title** | 图名 | *"needs to be informative, needs to explain what the map is"*。**必备。** |
| **Legend** | 图例 | *"Any symbolization that we use on the map obviously needs to be defined in the legend"*。**只要用了符号就必备。** |
| **North arrow** | 指北针 | *"provides orientation, so that always needs to be present"*。**老师用了 always——必备。** |
| **Scale bar** | 比例尺 | **必备。** 有 graphic scale bar 与 ratio 两种表达（见 2.2） |
| **Inset** | 嵌图 | **可选。** 两种用途：(a) 把主图某一块**放大**显示；(b) 作 **location map**（位置图），显示研究区在国家/区域中的位置 |
| **Credits** | 出处 / 制图者 | 数据来源（data sources）。**展示地图必备**——否则读者无法追溯数据 |
| **Neatline** | 图廓线 | *"sometimes you enclose the map in a frame as shown here, which is referred to as a neat line. It kind of frames the whole thing. **You may or may not have that.**"* **可选。** |
| **Other text information** | 其他文字信息 | 投影/坐标系信息、制图日期、制图者姓名等 |
| **Grid / Graticule** | 格网 / 经纬网 | *"The other thing you might have is a grid or a graticule covering your map showing coordinates."* **可选。** |

> **术语区分（📎 背景补充）**：转写和讲义都同时提到 grid 与 graticule 却没有解释区别。**Graticule = 经纬线网（geographic coordinates，度）**；**Grid = 投影坐标格网（projected coordinates，米，如 UTM 方里网）**。ArcGIS Pro 的 `Insert > Grids` 库里两类都有。材料未作此区分。

### 2.2 比例尺的两种表达 —— 老师明确表态

这是转写里讲得最具体、讲义上完全没有的一段：

| 类型 | 形式 | 老师的评价 |
|---|---|---|
| **Graphic scale bar**（图形比例尺） | 一根带刻度的标尺 | *"when you're producing a presentation map, **this kind of graphic scale is much better**"* |
| **Ratio / representative fraction**（比例式） | 1:50,000 | 打印尺寸一变就失效 |

理由（原话）：

> "if you print your map out on a larger page or a smaller page, then that **naturally adjusts the size of that graphic**, whereas if you've got a one to 50,000 and you print it on a much smaller page, then obviously **that scaling doesn't work anymore**."

**逻辑要点**：图形比例尺是**画在图上的一个几何对象**，随图一起缩放，所以它与图面的比例关系永远正确；比例式是一个**数字**，缩放时数字不变而图变了，就撒谎了。这是本周最实用的一条经验规则，**做 assessment 的地图必须用 graphic scale bar**。

### 2.3 地图的两大类：General purpose vs Thematic

讲义原文：

- **General purpose maps** — provide geographical information **for reference purposes**
  - **Topographic map** — comprehensive reference information about a region
  - **Base map** — a foundation for superimposing additional layers of information
- **Thematic maps** — map the spatial distribution of **a single attribute or variable**, or the relationship among **several variables**

转写补充的细节：

| | Topographic map | Base map |
|---|---|---|
| 内容 | elevation（通常以 contours 表达）、hydrology（河湖海岸线）、settlements、road / transport networks、其他地理要素 | place names、rivers、road networks 等，**"not as much detail as you would find on a topographic map"** |
| 生产者 | 国家机构，UK 是 **Ordnance Survey (OS)** | 通常由 GIS 平台提供（Esri 底图服务等） |
| 角色 | 独立成图，供查阅 | **foundation layer**，供叠加专题图层 |
| 你在本课的接触 | — | *"The base map, then, is where we've been using in your practicals. You've been usually putting your layers of information onto a base map to provide context."* |

### 2.4 专题地图类型与适用数据

这是本周核心中的核心。下表整合讲义图注 + 转写实例。

| 类型（英） | 中文 | 讲义定义（原文） | 适用数据 | 转写举的例子 |
|---|---|---|---|---|
| **Dot map** | 点子图 / 点密度图 | *"Represent the spatial distribution of point features – dots are values (**not a surface map**)"* | 计数型、可离散化的量 | 河网＋人口密度，**100 persons per dot**；点密集处即人口稠密区 |
| **Proportional symbol map** | 比例符号图 | *"Scaled symbols to represent quantitative values... using ratios (values or classes)"* | **连续的单值**（未分级） | 村庄人口：10 人小点 → 100 人大点 → 500 人更大点 |
| **Graduated symbol map** | 分级符号图 | 同上 | **先分级（class / bin）再给符号** | *"we first divide our data up into class sizes or bins, and then we have a series of dots which increase in scale, but **they're not proportional to the size. They're stepped.**"* |
| **Choropleth map** | 分级设色图 | *"Data are classified into ranges or classes, then shading or colouring each unit area using graduated colours"* | **有行政/统计单元边界的面数据** | PM10 浓度图（µg/m³），深色高、浅色低，**白色 = no data** |
| **Isoline map** | 等值线图 | *"lines joining points of equal value of a **continuous variable**"* | **连续场** | 等高线（contour）最常见；isobars（等压线）、isotherms（等温线） |
| **Hypsometric map** | 分层设色图 | *"Shading the space between contour lines, which represents a terrain surface as a series of elevation zones"* | 高程等连续场 | 等高线之间填色，比纯等高线更直观 |
| **Hill-shaded map** | 晕渲图 | *"2D representation of 3D terrain surfaces produced by simulating the appearance of the effects of sunlight illuminating the surface of the land"* | DEM / DTM 栅格 | 见 2.4.1 |

#### 2.4.1 Proportional vs Graduated —— 本周最容易混的一对

| | Proportional | Graduated |
|---|---|---|
| 是否先分级 | **否**，每个值一个符号大小 | **是**，先分 bin |
| 符号大小变化 | 连续 | **阶梯式（stepped）** |
| 读图能力 | 能读出个体差异 | 只能读出类别归属 |
| 老师的评价 | *"they deal with single values"* | *"To make it more useful, I suppose... That's a more graduated approach"* |
| 图例形式 | 若干代表性尺寸（嵌套圆） | 与分级数一致的离散尺寸 |

#### 2.4.2 Hill-shade 的默认光照参数（转写，讲义未写）

> "Taking a digital elevation model and artificially lighting it, **usually from the northwest at some angle above the horizon, say 45 degrees**, so that northwest-facing slopes are brightly lit and southeast slopes are in shade."

即 **Azimuth ≈ 315°、Altitude ≈ 45°**。这与 W07 地形分析和本周 practical 第 3 步的 Hillshade 工具默认值一致。

> 📎 背景补充：ArcGIS Pro `Hillshade` 工具的默认值确实是 **Azimuth = 315、Altitude = 45**。选西北方向照明是制图惯例——因为人类视觉系统默认「光从左上方来」，若从东南照明会产生**地形反转错觉（relief inversion）**，山谷看起来像山脊。材料只说了「usually from the northwest」，没说为什么。

### 2.5 地图投影与「保留什么」

讲义原文（这段有正文，可靠）：

> Map projections by preserved property (**area, shape, direction, distance**).
>
> - **Equal area** projection (area) — preserve areas and are used for mapping distributions such as **population density, land cover, geology or climatic regions**.
> - **Conformal** map projections (shape and direction) — e.g. **geological structural data, isobars and isotherms, wind directions, ocean currents**.
> - **Equidistant** projections (distances) — e.g. **wildfire spreading from ignition point, volcanic ash dispersal from a volcano, pollution dispersal from a point source**.
>
> Projections are a compromise between **distortion, accuracy, and aesthetics**.

转写补充的两点：

1. **conformal 的实例**：*"Conformal map projections like UTM or Mercator transverse projections"*。
2. **地图覆盖面积是关键变量**（讲义完全没写）：
   > "Another important factor is just **how big an area does your map cover**? Because if you're showing a very large area, then these kind of distortions become more important because you're dealing with **more curvature of the Earth's surface**."

   —— 小区域（如本周 practical 的 Burnage，几平方公里）投影选择几乎无所谓；全球或洲际尺度则必须慎选。

3. **老师给的现实态度**：*"they may not necessarily, at the end of the day, be that important. You might have other priorities in using a map projection."*

**投影与「视觉印象」的关系（讲义那句 "compromise between distortion, accuracy, and aesthetics" 的含义）**：投影不只影响几何精度，还直接影响**读者对分布的直觉判断**。例如用 Mercator 画全球分布，高纬度地区面积被极度放大，读者会高估高纬现象的重要性。所以讲义把 equal area 明确指定给 population density / land cover / geology / climatic regions —— **凡是「面积即信息」的专题图，必须用等积投影**。

### 2.6 地图设计的四个步骤

讲义 `# Map design` 页（图注，可靠）：

| 步骤 | 讲义原文 | 中文 |
|---|---|---|
| **Selection** | selecting the geographical area, geographical features, map scale, projection, data variables, etc. | 选定范围、要素、比例尺、投影、变量 |
| **Classification** | grouping and categorising data | 数据分组与分类 |
| **Symbolisation** | selecting symbols and visual variables to represent data in a logical way | 选符号与视觉变量 |
| **Layout design** | organising disparate cartographic elements coherently on a page | 版面组织 |

**但老师在转写里在 Selection 之前插入了「第 0 步」，讲义上没有：**

> "obviously the first thing you've got to do is decide **what is the purpose of my map? Why am I producing this map? What do I want to show? What's the key message that I'm trying to communicate?** So that's **priority number one**."

**这是本周的方法论总纲。** 后面所有的分级、配色、版面决策，判据都是「是否服务于那个 key message」。

### 2.7 数据分级（Data classification）

讲义图注（可靠）：

> Classification involves grouping similar features into classes (**5-8 max**) to reduce complexity and organise data.
> (a) equal size ranges; (b) identifies natural patterns; (c) equal number of features in each class, irregular class sizes; (d) class breaks are standard deviations from the mean.

转写把「为什么必须分级」讲清楚了（讲义没写）：

> "for most maps you have to go through some process of classification in order to map them because **you can't generally show all your data because the map becomes too cluttered and loses its impact**."

**先分岔：数据类型决定分级形式**

> "if your attribute data are **qualitative**, then you tend to use **classes or categories**. Whereas **quantitative** data, you generally put these into some kind of **numerical range or a bin size**."

**四种定量分级方法**（讲义 (a)–(d) 对应转写四段讲解，同一份墨尔本高收入家庭数据、同样分 6 类）：

| 方法（英） | 中文 | 断点怎么定 | 优点 | 缺点（老师原话） |
|---|---|---|---|---|
| **Equal interval** | 等间隔 | 数据全距等分为 k 份 | *"the easiest one and the one we use most... Nice and easy"*；**类宽一致，可直接比较各区绝对值** | *"there's one class here, number five in this list, for which there's **no representative on the map**. So we can get **gaps in the data**."*（会出现空类） |
| **Natural breaks** | 自然断点 | 找数据中的**空隙或突变**（"if we suddenly go from say 50 to 200 or something as a gap there"），按这些位置断开；*"there are algorithms that you can use to compute where those natural breaks are"* | **最能显现数据内在模式**——转写里它揭示了中心城区外围的富裕郊区，而等间隔看不出来 | *"you end up with **irregular bin sizes**... it doesn't make it very easy to compare the districts in terms of their absolute values"* |
| **Quantile** | 分位数 | *"you **rank all your data from the lowest value to the highest value** and then you **chop it up into the number of quantiles**"*；6 分位则每类含 1/6 的要素 | 与自然断点类似，**能凸显排序上的差异**，每类要素数相同 | *"you can end up with quite a **distorted map** because you can see that the bin sizes here are very different from each other"* |
| **Standard deviation** | 标准差 | *"you just calculate where the **mean** of your data is and then you calculate **half a standard deviation, either side of that mean, one standard deviation, one and a half standard deviations**"*；中间那类是 **−0.5σ 到 +0.5σ** | 直接表达「相对平均水平的偏离」，语义清晰 | 需要数据近似对称分布才有意义（材料未说明这一限制） |

**老师的总结态度**（很关键，考试导向）：

> "**I'm not suggesting you use any of these**, but it's useful to know about these **if you are preparing a map or if you find a map online which uses this kind of classification.**"

—— 即：**不是要你死记哪种最好，而是要你看到一张图时能判断它用了哪种分级、因此在放大什么、掩盖什么。**

> 📎 背景补充：材料**没有**提到 **Manual（手动）** 与 **Geometric interval（几何间隔）** 两种分级方法，也**没有**提到 ArcGIS Pro 中 Symbology 面板的 Method 下拉列表默认是 **Natural Breaks (Jenks)**。这两点在实际操作时会遇到，此处补充说明，但**不属于本周材料内容**。

### 2.8 符号化（Symbolisation）与视觉变量

讲义原文（可靠）：

> **Symbolisation: use of shape** — Choosing symbols and using visual variables to represent the geographical features. **Simple, self-explanatory symbols are most appropriate. Symbol geometry is qualitative not quantitative.**

**最后一句是本周一个精准的考点**：*Symbol geometry is qualitative not quantitative*（**符号的形状表达定性信息，不表达定量信息**）。想表达数量要靠 size / colour value，不能靠形状。

转写举的例子：澳大利亚绿色能源图——蓝色的**太阳能板形状**代表 solar farms，**风机形状**代表 wind farms，biomass 与 geothermal 用行业标准符号。老师的话：*"just try and make your symbols obvious."*

**视觉变量（visual variables）× 几何类型的组合矩阵**（转写讲了一行，讲义只有图）：

| 视觉变量 | 点（point） | 线（polyline） | 面（area） |
|---|---|---|---|
| **Shape**（形状） | 不同符号形状 | 不同线型 | 不同**shading / texture pattern**（填充纹理） |
| **Size**（大小） | 符号大小 | 线宽 | —— |
| **Colour**（颜色） | ✅ | ✅ | ✅ |
| **Pattern**（图案） | ✅ | ✅ | ✅ |
| **Orientation**（方向） | ✅ | ✅ | ✅ |

老师原话：*"you can use size, you can use color, you can use pattern, and you can use orientation... this is basics of cartography essentially."*

### 2.9 视觉层次（Visual hierarchy）

讲义原文（可靠）：

> - The perceptual organisation of mapped features.
> - Uses a visual hierarchy:
>   - the **foreground** features are most visually prominent, which are the **primary** features;
>   - the **secondary and supporting** features have decreasing visual importance, placed in the lower levels.
> - Established by visual contrasts or differences in **colour intensity, colour hue, shading pattern, and size of map symbols**.

老师的说法：*"you need to place those in a sort of hierarchy from most prominent down to least prominent **so that the key message dominates your map**."*

**三种建立视觉层次的方法**（讲义各有一页，转写逐个解释）：

| 方法（英） | 中文 | 讲义定义 | 转写实例 |
|---|---|---|---|
| **Stereogrammic method** | 立体式 | *"Creates a stereogrammic hierarchy that makes the important features appear **above** the background base data layers"* | 一张点符号图：左图海、陆、圆符号不作区分，看不出层次；右图用不同颜色，**数据点像浮在底图之上**。真实案例：**The Rivers Trust** 制作的英格兰河流与地下水**有毒化学污染**分布图（讲义有此标题：*Toxic chemical pollution found in river and groundwater sites across England*），左图河湖塘、右图地下水，*"very impactful visually"* |
| **Extensional method** | 扩展式 | *"aims to show a hierarchy of importance among features"* | **交通网**是经典例子：dual carriageways（双车道干道）／principal road／secondary road／minor road／tracks，靠**不同颜色、更粗的线、更深的色**建立主次 |
| **Subdivisional method** | 细分式 | *"uses colour and pattern to distinguish between **classes and subclasses** of area features"* | 土地利用图：三大类 dryland agriculture / irrigated agriculture / conservation 各给一种**颜色**，各自的**子类**用不同的 **shading / pattern fill** 区分 |

> **记忆抓手**：Stereogrammic = 把重点「抬起来」；Extensional = 同类要素分主次；Subdivisional = 用「色相分大类、纹理分子类」的两级编码。

### 2.10 地图注记（Map lettering）

讲义列出的 7 条原则（原文，可靠）：

1. Easily recognisable.（易辨认）
2. Show hierarchy among geographical features.（体现要素等级）
3. Help distinguish between classes and subclasses.（帮助区分类与子类）
4. Clearly identify the feature to which it refers **without ambiguity**.（无歧义地指向所标注的要素）
5. **Does not obscure the adjacent important features.**（不遮挡邻近重要要素）
6. **Only used where necessary.**（只在必要处使用）
7. The density of annotation reflects the relative density of the distribution of the features.（注记密度应与要素分布密度相称）

老师对这页的处理：*"I'll let you read through most of this. I don't think there's anything there that you won't understand."* —— 但他重点讲了**放置规则**：

**点要素标注的优先位置（Preferred positions for labelling a point feature）**

讲义图注：*"The possible positions of annotation for a point feature ranked in order of **decreasing preference**."* 转写给出了具体顺序：

> "**This is where we would try and put our label if we could**（右上）. If there's something there that's blocking that position, then we move it over to the **top left**. If we can't use those two positions, it goes down to the **bottom right, bottom left**, and then **either side** and then and so on."

即优先级：**右上 → 左上 → 右下 → 左下 → 正右/正左 → …**

老师强调：*"**You can't just put them anywhere.** So there's a kind of hierarchy of where they should go that cartographers follow that sort of protocol."*

**线要素与面要素的标注规则**（纯转写，讲义无）：

- **道路与河流**：*"try and keep them **horizontal**. We **don't have any upside down text** on a map... Try and label them **along the sections** of the rivers and roads."*（尽量水平；绝不倒置；沿线要素走向排布）
- **面要素**：*"we try and put those **along the longest dimension**."*（沿最长轴方向排布）

老师的收束语：*"a lot of this is just, you know, it's basic common sense, but it's worth knowing some of the rules."*

### 2.11 版面布局（Map layout）

讲义两页（`# Map layout`、`# Effective map layout design`）**都是纯图片，无正文**，Page 26/27 的 OCR 也基本无效。**这部分的全部实质内容来自转写。**

**核心概念：视觉中心（visual centre）**

> "We talk about **visual center**, so our eyes are actually slightly better adjusted to look at things **just above the true center of a page**. Very often, the thing of most importance in our map is placed **slightly above the center point of the page**."

**好版面 vs 坏版面（转写讲了一组对比图）**

> "The one on the left is **not** a good way of laying out your map. The one on the right **is** a good way of doing it. It's not good because **your visual center is probably about where the scale bar is, whereas it should be the main body of the map**. So this kind of stuff dominates your map, whereas the important part is what you really want people to look at."

**→ 诊断法则：把版面缩略成灰度块，看哪块占据视觉中心。如果是 scale bar / legend / 大段文字占了中心，版面就是失败的。**

**要素放置的固定规则（转写）**

| 要素 | 位置 |
|---|---|
| **Title** | *"Title **always** goes at the top."* |
| **Legend** | *"Legend will **always** go either at the **side** or at the **bottom**."* |
| **Map body** | 视觉中心（略高于几何中心） |
| 其余 | *"you just have to try and work around to get the best use of space"*——取决于研究区形状（*"it depends upon the shape of your geographical area to some extent"*） |

**讲义 Page 26（低质量 OCR 段）能还原出的版面结构**：一张墨尔本高收入家庭图，标注了 Title / North arrow / Map body / Legend / Inset / Scale bar / Credits / Neatline / Other text information 的位置，图例分 6 级（`<= 300`、`301–600`、`601–900`、`901–1200`、`1201–1500`、`> 1500` 户），比例尺为 `0 12.5 25 50 Kilometers`，credits 为 `Data Source: Australian Bureau of Statistics`，`Date of production: 18/04/2014`。**注意：OCR 把若干数值识别错了（如 `201 - 600`、`001 - 1200`），详见勘误表。**

### 2.12 多变量制图（Multivariate mapping）

讲义定义（可靠）：

> Multivariate mapping involves showing **two or more attributes or variables** of geographical features **simultaneously**.

转写两个例子：

1. **图＋图表复合型**：Greater Sydney 的 **in-use copper stocks**（在用铜存量）。面状分区用**不同色调与纹理**表示各区铜存量，旁边配**直方图**显示这些存量在不同用途（dwellings 住宅、motor vehicles 机动车等）间的分配。
2. **Bivariate choropleth map（双变量分级设色图）**：讲义标题页给出图题 *1997 World Rural Population Density and Arable Land*（来自低质量 OCR 段，仅标题）。转写解释：用一个**二维色彩矩阵**同时编码「每平方公里人口」与「可耕地百分比」。
   > "if we look at a country over here like **India, which is dark red**, we can see that it has a **high population density, greater than 400**, and **more than 40 percent arable land**."

> 📎 背景补充：双变量分级设色图的图例是一个 **3×3 或 4×4 的方格矩阵**（不是一条色带）——横轴一个变量、纵轴另一个变量，格子颜色由两条色带混色而成。这是它最难读也最易被误用的地方。材料只展示了成图，未解释图例构造。

### 2.13 2.5D 与真三维

讲义定义（可靠）：

> A **2.5D** representation can be considered as a two-dimensional phenomenon with **the third dimension representing a single attribute value** e.g. elevation above sea level, air temperature, precipitation and population density.

转写讲得更透（讲义没有 voxel 这个词）：

> "You have a location **x, y**, and you have some value **z**, which represents your elevation or some attribute value. It could be temperature, for example. Then you **extrude that above the surface**. **Every x, y equals to one**, and that gives you a kind of 3D effect.
> For **true 3D** spatial mapping, we're talking about **volume**. You need to know the volume of a cube, essentially, or a **voxel**, sometimes it's called, a **volume pixel**. It's **not true 3D**, but it gives you that impression of being three-dimensional."

**判据：一个 (x, y) 只对应一个 z 值 → 2.5D；(x, y, z) 每一格都有独立取值（体元）→ 真 3D。**

材料给的三个 2.5D 例子：

| 例子 | 说明 |
|---|---|
| **Hill shade** | 最基本的 2.5D，z = elevation。转写还提到**多光源版本**：*"this is also a hill shade, but using **more than one light source** shows up a bit more detail of the relief"* |
| **Stepped statistical surface**（阶梯统计面） | 讲义有此标题（Page 31，低质量 OCR 段无内容）。转写：*"the surface has been **extruded upwards** to help highlight the differences between them. So these values have been used to lift the surface up"* |
| **3D virtual model** | 讲义图注：*"The **annual mean PM2.5** distribution is mapped in a 3D virtual model of **Clayton Campus, Monash University**. **Darker colours on the ground indicate higher levels of PM2.5**"*。转写：建筑按其**高程 extrude 上去**，*"it's not a volume. It's just lifting the building up according to its elevation"* |

### 2.14 动画制图（Animated mapping）

讲义原文（可靠）：

> - Animated mapping uses animation to show changes over **time, space** or **attributes**.
> - Involves processing or playing back a sequence of individual maps, referred to as a **track**.
> - A map layer in a track is called a **frame**.
> - **Keyframing** technique is often used.
> - The most characteristic frames that form an outline of the most important movements are created first.
> - **The computer then interpolates the 'in-between' frames.**
> - A distinction is made between **temporal** and **non-temporal** cartographic animations.

| | Temporal animation | Non-temporal animation |
|---|---|---|
| 讲义定义 | *"Show changes in the locational or attribute components of spatial data through maps as a **time-lapse**. **Spatial data must have a time component.**"* | *"Show changes caused by **other variables other than time** — e.g. changes along a path, through the landscape, and with varying data presentation methods or view properties."* |
| 典型形式 | 时间序列播放 | **Fly-through animation** — *"provide the appearance of flying through a 3D landscape by showing a series of oblique views"* |
| 讲义给的实例链接 | 夏威夷 2018 年 5 月熔岩流与地震时间序列（3 小时窗口）；2019 全球地震图（深度夸大） | Oso, Washington 2014-03-22 泥石流动画；Lidar masspoint 数据做的公路隧道 fly-through；Jack and Laura Dangermond Preserve（加州）Lidar 景观漫游 |

转写的补充（关键的一句，解释了 keyframing 的**必要性**）：

> "it's **not a continuous set of maps. Usually there are gaps.** You might have collected it on one day, collected the data on another month and then maybe another three months. And you show each of those maps and you make it into an animation and **the animation software will fill the gaps** between the individual maps that you've collected."

另外：*"You can make these yourself, **not only in ArcGIS Pro, but in Google Earth** and other. There's lots of applications for doing that now."*

### 2.15 📎 背景补充：色彩使用的系统知识（材料只覆盖了其中一小块）

> **⚠️ 本小节整节都是背景补充。** 本周材料对配色的**全部**论述只有转写里的一句：
>
> > "For a choropleth map, you tend to use a **colour ramp**. **Don't produce a choropleth map that has a rainbow of colours, because that is too confusing.** Choropleth maps usually use a **single colour**, but use different shades, so they use a colour ramp."
>
> 以及讲义 visual hierarchy 页提到的 *colour intensity, colour hue*。**下面三类色带的分类、色觉障碍友好性、以及「必须用比率不用计数」这条规则，讲义与转写都没有讲过。** 之所以补充，是因为它们是理解上面那一句「不要彩虹色」的原理，而且做 assessment 会直接用到。

**三类色带（colour scheme）**

| 类型 | 结构 | 适用数据 | 例子 |
|---|---|---|---|
| **Sequential**（顺序色带） | 单一色相，明度/饱和度单调变化（浅→深） | **有序的、单向的量**：浓度、密度、高程、太阳辐射量 | 白→蓝渐变；本周 practical 的太阳辐射图（红色系高值） |
| **Diverging**（发散色带） | 两个色相从中间的中性色向两端加深 | **有明确「中间参照值」的量**：距平、正负变化率、标准差分级、Getis-Ord 的热点冷点 | 蓝—白—红 |
| **Qualitative**（定性色带） | 多个明度相近、色相不同的颜色 | **无序的类别数据**：土地利用类型、岩性、行政区 | 一组对比色 |

**老师说的「不要彩虹色」，本质是：彩虹色带（rainbow / jet）用色相变化去编码有序数据，而人眼对色相的排序没有天然共识**（红比绿"大"吗？），并且彩虹带里的黄色区域会形成虚假的视觉边界。顺序色带用明度编码，明度的排序是天然的。

**色觉障碍友好性（colour-vision-deficiency safe）**：约 8% 的男性有红绿色觉障碍。**红—绿发散色带是最糟的选择**，应改用**蓝—橙**或**蓝—红**。判断方法：把图转成灰度，若各级仍能区分，则基本安全（因为这说明差异编码在明度上，而非仅在色相上）。

**分级设色图必须用密度或比率，不能用绝对计数（本周材料未提，但这是制图学的头号规则）**：choropleth 用**整个多边形的面积**来承载颜色，所以大多边形天然占据更多视觉权重。若填的是绝对计数（如「总人口」「病例数」），地图实际上在显示「哪个区大」，而不是「哪个区强度高」。**必须换成密度（人/km²）或比率（%、每千人）。**

> ⚠️ 注意：**讲义 Page 26 的墨尔本示例图恰恰用的是绝对计数**（`No. of households`，`<=300` 至 `>1500` 户），而不是密度或比率。这在制图学上属于有争议的做法——若各 Local Government Area 面积差异大，该图会同时反映面积与富裕程度。**材料未对此作任何提示。** 这不算「材料错误」（该图是引自教材的示例，用于演示版面要素而非配色规范），但复习时应当意识到。

**地图伦理与误导性制图（📎，材料完全未涉及）**：同一份数据换分级方法、换配色、换投影、换分级数，可以合法地得出印象完全相反的地图。本周老师讲的「natural breaks 能看出等间隔看不出的富裕郊区」正是这个现象的正面版本；其负面版本就是选择性分级。**规范做法：在 credits 或 other text information 里注明分级方法与分级数**，让读者可以还原你的决策。

---

## 三、公式与图表

本周定量内容不多，但**分级算法必须能自己动手算**，practical 的能量换算链也要能复述。

### 3.1 四种分级方法的断点算法

设数据为 $x_1, \dots, x_n$，最小值 $\min$、最大值 $\max$、均值 $\bar{x}$、标准差 $\sigma$，分 $k$ 类（讲义：**5–8 类为宜**）。

**(a) Equal interval（等间隔）**

$$\text{类宽 } w = \frac{\max - \min}{k}, \qquad \text{断点 } b_i = \min + i\cdot w \;\; (i = 1,\dots,k-1)$$

- **每类宽度相同，每类要素数不定。**
- 转写的墨尔本例子：数据到 1800 户，分 6 类 → $w = 300$，断点 300 / 600 / 900 / 1200 / 1500。
- **必然后果**：若数据分布偏斜，会出现**空类（empty class）**——老师原话 *"class number five... for which there's no representative on the map"*。

**(b) Quantile（分位数）**

1. 把 $n$ 个值**从小到大排序**；
2. 第 $i$ 个断点取排序后第 $\lceil i\cdot n/k \rceil$ 个值。

- **每类要素数相同（$n/k$ 个），每类宽度不定。**
- 转写：*"this one at the top here represents the **upper sixth** of all the data in a ranked list, whereas the lighter color here at the lower end represents the **lower sixth**."*
- **必然后果**：类宽可能极不均衡（*"the bin sizes here are very different from each other"*），数值相近的两个区可能被分到不同类，造成 *"quite a distorted map"*。

**(c) Natural breaks（自然断点，Jenks）**

- **直觉版（转写就讲到这一层）**：找数据序列里的**间隙**（*"if we suddenly go from say 50 to 200 or something as a gap there"*），在间隙处断开。
- 📎 背景补充（材料只说 *"there are algorithms that you can use to compute where those natural breaks are"*，没给算法）：**Jenks natural breaks 的目标函数是——在所有可能的分割方案中，使「类内平方偏差之和（SDCM, sum of squared deviations from class means）」最小、等价地使「拟合优度 GVF = (SDAM − SDCM)/SDAM」最大**，其中 SDAM 是全体数据对总均值的平方偏差和。实现上用迭代或动态规划（Fisher–Jenks）求解。**这一层材料没讲，不必背，但要知道它是一个优化问题，不是随手找空隙。**
- **必然后果**：类宽不规则（*"irregular bin sizes"*），跨图比较困难；但**最能显现数据的内在结构**。

**(d) Standard deviation（标准差）**

$$\text{断点} = \bar{x} \pm 0.5\sigma, \;\; \bar{x} \pm 1.0\sigma, \;\; \bar{x} \pm 1.5\sigma, \dots$$

- 中间那一类是 $[\bar{x}-0.5\sigma,\; \bar{x}+0.5\sigma]$ —— 转写：*"this light colored one here I think is **plus 0.5 to minus 0.5**. So it kind of **represents the average** wealthy household number."*
- **语义最清晰**：颜色直接读作「比平均高多少个标准差」。
- 📎 背景补充：这要求数据**近似对称分布**；强偏斜数据用标准差分级会把绝大多数要素挤进中间一两类。材料未提这一前提。

### 3.2 关键图表的文字描述（读到能自己画出来）

#### 图 A —— 地图要素布局图（讲义 Page 2，低质量 OCR 段，但要素名可靠）

画一个竖长方形代表整页，最外一圈细线是 **Neatline**。

- **顶部居中**：两行标题 —— *Households with Very High Income in Melbourne* / *by Local Government Areas in 2006*，标注 **Title**。
- **中央偏上（视觉中心）**：一大块不规则多边形拼图，是墨尔本各 LGA 的分级设色图，标注 **Map body**。
- **右上角**：一个箭头符号，标注 **North arrow**。
- **左侧或下方**：一列色块＋数值区间，标注 **Legend**。
- **图内一角**：一个小方框，里面是同一区域的另一比例尺版本或位置图，标注 **Inset**。
- **底部左侧**：一条带刻度的横条（`0 — 12.5 — 25 — 50 Kilometers`），标注 **Scale bar**。
- **底部**：`Data Source: Australian Bureau of Statistics` 标注 **Credits**；`Date of production: 18/04/2014` 标注 **Other text information**。

**这张图就是本周的"标准答案版面"，practical 交的地图应当能一一对上这些要素。**

#### 图 B —— 同一数据、四种分级方法的对比（讲义 Data classification 页 + 转写详解）

画 **2×2 四张同样形状的墨尔本 LGA 拼图**，每张配一条 6 级单色渐变图例（浅→深）。

| 位置 | 方法 | 图上应该看到什么 |
|---|---|---|
| 左上 (a) | **Equal interval** | 图例数值整齐（≤300 / 301–600 / … / >1500），但**有一个色块在图上找不到对应区域**（空类）；整体多数区域集中在浅色端 |
| 右上 (b) | **Natural breaks** | 图例数值零碎不整齐；**中心城区最深**，且**中心外围出现一圈中深色的富裕郊区**，另有一处孤立的中深色区——这些在 (a) 里完全看不出来 |
| 左下 (c) | **Quantile** | 六种颜色**在图上占的区域面积大致相等**（因为每类要素数相同）；图例区间宽度差异极大（可能低端一类只跨 50，高端一类跨 800） |
| 右下 (d) | **Standard deviation** | 图例读作 `< −1.5σ`、`−1.5 to −0.5σ`、`−0.5 to +0.5σ`（最浅、代表"平均水平"）、`+0.5 to +1.5σ`、`> +1.5σ`；**最深色仍落在中心城区**，与 (b) 一致 |

**这张图要传达的唯一结论**：四张图数据完全相同，**读者得到的印象完全不同**。(a) 说「墨尔本大部分地方差不多」；(b)(c) 说「有清晰的富裕核心和富裕郊区带」；(d) 说「相对平均水平，中心城区异常突出」。

#### 图 C —— 好版面 vs 坏版面（讲义 Map layout / Effective map layout design 页；OCR 无内容，据转写还原）

并排画两个同样大小的页面框。

- **左（坏）**：地图主体被挤到页面上部一个较小的区域；页面**中间偏上的位置**被一根很长的 scale bar、一个大图例块和几行文字占据。→ 老师的诊断：*"your visual center is probably about where the scale bar is, whereas it should be the main body of the map."*
- **右（好）**：地图主体占据页面 60–70% 的面积，其**几何中心略高于页面中心**（视觉中心）；title 在顶部；legend 靠右侧或压在底部；scale bar 与 north arrow 缩小放在角落；credits 一行小字在最底。

**自检方法**：把版面眯眼看成灰度块，最"重"的那块必须是地图主体。

#### 图 D —— 点要素标注的优先位置（讲义 Preferred positions 页 + 转写）

画一个红点在中央，周围 8 个位置各画一个方框代表标签，按优先级编号：

```
      ⑥      ②      ①
        ↖    ↑    ↗
      ⑧  ←  ●  →  ⑦          ① 右上（首选）
        ↙    ↓    ↘          ② 左上
      ④      ⑤      ③        ③ 右下   ④ 左下
                              ⑤⑥⑦⑧ 正下/正上/正右/正左（依次递减）
```

> ⚠️ 转写只明确给出了**前四位的顺序**（右上 → 左上 → 右下 → 左下），之后只说 *"and then either side and then and so on"*。上图中 ⑤–⑧ 的具体次序属于 📎 背景补充的合理推断，**材料未明说**。

#### 图 E —— 三种视觉层次方法对照（讲义三页 + 转写）

| | 画法 | 效果 |
|---|---|---|
| **Stereogrammic** | 左图：海、陆、圆符号全用相近的浅灰，符号"陷"在底图里。右图：底图降为极浅灰、低对比，圆符号改用饱和的深色＋白边 | 符号**浮起来**，数据点与底图分离 |
| **Extensional** | 一张路网图：dual carriageway 用最粗的深色线，principal road 次粗，secondary road 更细，minor road 细浅线，tracks 用虚线 | 一眼看出**主干道骨架** |
| **Subdivisional** | 一张土地利用图：dryland agriculture = 黄色系、irrigated agriculture = 绿色系、conservation = 棕色系；每个色系内部的子类用**不同的斜线/点状/网格填充** | **色相分大类，纹理分子类**的两级编码 |

#### 图 F —— 📎 背景补充：三类色带适用场景对照

> **本图材料中没有，是补充。**

```
Sequential   浅□ □ ▨ ▩ ■深      单色相 · 明度递增     → 浓度、密度、高程、辐射量
Diverging    ■深◧ □白 ◨ ■深      双色相 · 中间为中性   → 距平、变化率、±标准差、热点/冷点
Qualitative  ■红 ■蓝 ■绿 ■橙      多色相 · 明度相近     → 土地利用、岩性、行政区
Rainbow ❌   ■紫■蓝■绿■黄■橙■红   色相编码有序量        → 老师明确反对
```

#### 图 G —— 本周 practical 的成果图（Practical 末页示例，来自低质量 OCR 段，仅部分可读）

- **标题**：*Solar Radiation for Buildings in South Burnage, Manchester, UK*
- **主体**：南 Burnage 区域的建筑轮廓，每栋房屋的屋面按年太阳辐射量着色（红色系＝高值）；底图为浅灰街道图（GB Light Grey），可见 *Mauldeth Road*、*Burnage Cricket Ground* 等注记
- **Inset（location map）**：一张小图显示 Greater Manchester，标注 Salford、Manchester，说明研究区在都市区中的位置（底图为 World Topographic Map）
- **Scale bar**：`0 —— 1 Kilometers`
- **Legend 标题**：`Annual Solar Radiation (kW/hr/m2)`（⚠️ **单位写法有误，见勘误表**），5 级红色系分级：`600.2 – 828.1` / `828.2 – 855.6` / `855.7 – 866.9` / `867 – 884.7` / `884.8 – 1012.4`
- **说明文字**：*"Average annual solar energy potential values for rooftops in kilowatt-hours per square meter. Red colours indicate higher-yielding locations for installing solar panels. **North facing roofs were excluded from the analysis.**"*

> **值得注意**：这张示例图的分级明显是 **natural breaks 风格**（区间宽度极不规则：第一类跨 228，第三类只跨 11）。它把绝大多数变化压缩在 828–885 这个窄区间里做精细区分——因为屋顶辐射值高度集中，等间隔分级会让全图几乎同色。**这正是本周讲的「分级方法服务于 key message」的实例。**

### 3.3 Practical 的能量换算链（必须能复述）

这是本周唯一一串真正的计算，出自 Practical §6.1。

**(1) 单位换算**

$$1\ \text{kWh} = 1000\ \text{Wh} \quad\Rightarrow\quad \texttt{"Solar\_Rad" / 1000}$$

Area Solar Radiation 的输出单位是 **Wh/m²**，部分像元超过 1,000,000 Wh/m²，除以 1000 转成 **kWh/m²**。

**(2) 从入射辐射到发电量**

- 教程给出屋顶年入射辐射约 **500–1000 kWh/m²/yr**（原文写作 "500-1000 kWh/yr"，**漏了 /m²**，见勘误表）
- 家用光伏系统转换效率 **10–20%**，取 **17%**：

$$800\ \text{kWh/m}^2 \times 0.17 = \mathbf{136\ kWh/m^2}\ \text{(每年)}$$

**(3) 反向核对：从系统铭牌功率算**

- 典型家用系统最大输出 **3.5 kW**
- 英国全年日均日照 **5 小时**：

$$3.5\ \text{kW} \times 5\ \text{h} = \mathbf{17.5\ kWh/day}$$

- 典型系统需要约 **28 m²** 屋顶：

$$\frac{17.5\ \text{kWh}}{28\ \text{m}^2} = 0.625\ \text{kWh/m}^2/\text{day} = \mathbf{625\ Wh/m^2/day}$$

**(4) 现实折减**

教程明确指出上式是**理想条件下的最大值**：*"In reality systems produce more like **200 to 300 Wh/m² each day**."*

> ⚠️ 教程提醒 *"note the different scale units (kW versus W)"* —— 比较 (2) 的 kWh/m²/yr 与 (3) 的 Wh/m²/day 时**必须先统一到同一时间尺度**。粗算：136 kWh/m²/yr ÷ 365 ≈ **373 Wh/m²/day**，与 (3) 的理想值 625 同量级、且高于「现实」的 200–300，说明模型估计合理但偏乐观（因为 Area Solar Radiation **不考虑云量与天气**）。

**影响屋顶发电量的因素（教程列举）**：orientation（朝向）、weather（天气）、pitch（坡度）、efficiency（转换效率）、shading（遮挡）。本 practical 用 GIS 处理了其中的 **orientation** 与 **pitch** 两项。

---

## 四、课堂补充

> 本周转写 5,242 词，是本周信息量最大的材料。以下是**讲义上没有、只在课堂口头讲的内容**。

### 4.1 课程事务与考核信息（务必记下）

老师用了开头约 600 词交代日程，信息密度很高：

| 时间 | 安排 |
|---|---|
| **本周结束** | 进入 **Easter break**，持续到 **4 月 10 日** |
| **Week 9** | **Field course week，非教学周**——*"irrespective if you were on a field course"*（不管你去没去野外，这周都没课） |
| **Week 10** | 恢复讲座与 practical。**⚠️ 第一次回来的讲座改了日期、时间和地点**——*"Helpfully, we have a change of day, time, and location"*（老师这里是反讽）。地点：**Booth Street East Building**（老师自己都说 *"I have no idea where Booth Street East Building is"*）；时间 **16:00–17:00**；主讲人 **Rufus Brunt**；主题 **3D visualization**。**Practical 时间地点不变。** 完整安排已放在 **Canvas** 上 |
| **Week 11** | 一切恢复正常，**有讲座、无 practical**。讲座是 **revision-type lecture（复习课）**，*"I'll say something about the **exam format** as well"* |
| **Week 12** | 周一是 **bank holiday（五月银行假日）**，**无讲座、无 practical** |

**考核提示**：

- **assessment（个人报告）due 4 月 30 日** —— 老师在解释「为什么要学做展示地图」时点名：*"there will be times when you need to produce a presentation-style map, **for example, for your assessment, which is due in on the 30th of April**"*。**→ 本周内容直接对应 assessment 的地图部分，是投入产出比最高的一周。**
- Week 11 会讲 **exam format**。

**课后任务**：

1. **Read Chapter 5 of course textbook: Spatial Visualisation**（讲义与转写都点名）
2. **Take the quiz on Canvas** —— *"I put a quiz up on the Canvas site"*
3. 选读：**Esri ArcGIS tutorial "Introduction to Cartography"**（https://introduction-to-cartography-learngis.hub.arcgis.com/）—— 老师描述为 *"quite a long tutorial on ArcGIS online on cartography"*，讲义标注为 *"useful resource, more in-depth, worth looking at few topics for interest"*

### 4.2 老师对「制图学」在本课中定位的自我说明

> "Obviously, **we're not cartographers**, but it's useful if we know some of the background to cartography."

**→ 考核不会考制图学的深层理论，但会考「基本要素齐不齐、分级方法认不认得、版面合不合理」。**

### 4.3 视觉中心 —— 讲义完全没有的概念

见 2.11。这是转写里最实用的一条设计原理，**讲义上一个字也没有**（那两页是纯图片）。

### 4.4 图形比例尺优于比例式 —— 讲义完全没有的论证

见 2.2。这段论证（打印尺寸变化）**只在转写里有**，是可以直接写进 assessment 的理由。

### 4.5 choropleth 配色的唯一一条口头规范

> "**Don't produce a choropleth map that has a rainbow of colours, because that is too confusing.** Choropleth maps usually use a **single colour**, but use different shades."

**这是本周材料对配色的全部内容。** 2.15 节里三类色带、色觉障碍、比率 vs 计数等，都是我补充的背景知识，**不在材料范围内**。

### 4.6 no-data 的处理（讲 PM10 choropleth 时顺带提到）

> "You can also see there are **areas of the map where there are no data, which is shown in white here.**"

**→ 有缺失数据时应当在图例里显式给出「No data」一类，而不是留空让读者以为是零值。** 材料只是提了一句，没展开。

### 4.7 分级方法的口头评价（本周最有价值的一段口头内容）

见 2.7 表格。老师对四种方法**逐个给了优缺点和实际观察**，而讲义只有一行图注 `(a)(b)(c)(d)`。**这一段只能从转写学，讲义完全无法替代。** 特别注意他的结论句：*"I'm not suggesting you use any of these, but it's useful to know about these if you are preparing a map **or if you find a map online which uses this kind of classification**."* —— 考察点在**识别与批判**，不在**记忆哪个最好**。

### 4.8 「purpose first」——设计流程的第 0 步

见 2.6。讲义的 Map design 页只列了 Selection / Classification / Symbolisation / Layout design 四步，**老师在前面加了「先想清楚地图的目的和 key message」，并称之为 priority number one**。这是本周方法论的总纲。

### 4.9 老师对投影的现实态度

> "these projections are **always going to be some kind of compromise**. There's always going to be a distortion, there's going to be some loss of accuracy, and it **sometimes comes down to what's aesthetically pleasing**."

配合他关于「覆盖面积大小」的补充（见 2.5），本周的态度是：**小区域别纠结投影；大区域必须按「要保留什么」来选。**

### 4.10 注记规则的口头细则

见 2.10。**「道路河流保持水平、绝不倒置、沿线走向标注、面要素沿最长轴」这四条只在转写里**，讲义那七条原则里一条都没有。

### 4.11 Title / Legend 的固定位置

见 2.11。*"Title **always** goes at the top. Legend will **always** go either at the side or at the bottom."* —— 老师用了两个 always，**这是可以当规则背的**。

### 4.12 2.5D 与 voxel

见 2.13。**voxel（volume pixel，体元）这个词只在转写里出现**，讲义没有。这是 W09 三维技术的直接前置概念。

### 4.13 动画不止 ArcGIS Pro

> "You can make these yourself, **not only in ArcGIS Pro, but in Google Earth** and other."

### 4.14 老师对 practical 的口头预告

> "there will be a practical on Friday. So it'll be a nice way to finish off the semester, I'm sure. I think it's on **solar mapping, solar power generation mapping**."

（注意他说的是 "I think" —— 老师本人对 practical 内容并不完全确定，practical 由另外的教学团队准备。）

### 4.15 ⚠️ 转写中的自动语音识别（ASR）误写清单

这份转写是自动生成的，有若干专业术语被识别错，阅读时须自行还原：

| 转写写法 | 正确写法 | 出现位置 |
|---|---|---|
| **typography** | **topography**（地形） | 两处：*"contour map typography"*、*"what the typography or the relief is like"* |
| **stereogramic** | **stereogrammic**（讲义用的是双 m 拼写） | 视觉层次段，多处 |
| **divisional method** | **subdivisional method**（讲义为 subdivisional） | *"And then divisional method uses color shading and pattern"* |
| **statistical service surface** | **statistical surface**（阶梯统计面） | 2.5D 段 |
| **"Mercator transverse projections"** | **Transverse Mercator**（横轴墨卡托）；UTM 即基于此 | 投影段 |
| **"Rufus Brunt"** | 姓名拼写待核（曼大地球科学系教员，转写为自动识别结果） | 开场日程段 |

### 4.16 ⚠️ 讲义中来自低质量 OCR 段的内容（再次汇总）

讲义正文（`# Spatial visualization` 到 `# Homework and Resources`）**是从 PDF 文字层直接提取的，可靠**。

讲义末尾 `## OCR 补充（原文中无文字层的页面）` 一节**全部为图片 OCR 结果，质量低**，具体逐页可用性见 **1.5 节的表格**。其中：

- **Page 18（Visual hierarchy）识别结果为纯乱码，零信息量** —— 该页内容只能靠转写还原（见 2.9）。
- **Page 26（Map layout）的图例数值被误识**（`201 - 600` 应为 `301 - 600`；`001 - 1200` 应为 `901 - 1200`；`9 = 1,000 2,000` 是比例尺被误识）—— 详见勘误表。
- **Page 27（Effective map layout design）、Page 31（Stepped statistical surface）除标题外无任何内容** —— 完全依赖转写。

**结论：讲义 md 的最后一节请当作「线索」而非「内容」看待。**

---

## 五、Practical 要点

> **本段是本周笔记的重心。** 目标：不开原教程也能在 ArcGIS Pro 里从头重做一遍。
> **场景设定（教程原文）**：你所在的非营利组织在曼彻斯特 **Burnage**（一个以住宅为主的地区）启动了鼓励居民装光伏板的试点项目。你要用 ArcGIS Pro 算出每个屋顶全年接收多少太阳辐射，并产出一份可放进报告的地图成果。
> **教程来源**：改编自 Esri 官方教程 *Estimate Solar Power Potential*（https://learn.arcgis.com/en/projects/estimate-solar-power-potential/）。

### 5.0 数据与总体流程

**数据来源（教程列出）**

| 数据 | 来源 |
|---|---|
| Digital terrain model (1 m resolution) | https://environment.data.gov.uk/survey |
| **OS OpenMap Local Buildings** | 建筑轮廓 |
| **Manchester Ward Boundaries** | 用于取出 Burnage 边界，作为建筑与 DTM 栅格的 mask |

**工程包**：从 Blackboard 下载 ArcGIS Pro map package **`Burnage.mpkx`**，新建工程后打开。包含三个图层：

| 图层名 | 类型 | 内容 |
|---|---|---|
| **`Burnage_DTM_1m`** | GeoTIFF 栅格 | 数字地形模型，**1 m × 1 m 像元**，深灰＝低高程，浅灰/白＝高高程 |
| **`Burnage_Local_Buildings`** | 矢量（polygon） | 住宅建筑轮廓 |
| **`Burnage_outline`** | 矢量 | Burnage 区域外框 |

> ⚠️ **教程对 DTM 的定义有误**：教程写 *"A DTM shows the elevation of the ground **and the features on the ground, such as buildings and trees**"* —— 这实际上是 **DSM（Digital Surface Model，数字表面模型）** 的定义。DTM 是**裸地表**模型。但整个 practical 的逻辑（算屋顶辐射、算屋顶坡度坡向）**必须要求栅格包含建筑物**，也就是说这份数据实际上是 DSM。详见勘误表。**理解时请按「这是一个含地物的表面模型」来读。**

**总体流程（10 步）**

```
Burnage_DTM_1m
   ├─ Hillshade ──────────────────────────► HillShade_DTM_1m   （可视化）
   ├─ Area Solar Radiation (mask=Buildings)► Solar_Rad  [Wh/m²]
   │        └─ Raster Calculator ÷1000 ────► solar_rad  [kWh/m²]
   │                                             │
   ├─ Surface Parameters (Slope) ─────────► Slope_DTM  （检查有无 >45°）
   └─ Surface Parameters (Aspect) ────────► Aspect_DTM
                                                 │
                        Con(Aspect>22.5 AND Aspect<337.5, solar_rad)
                                                 ▼
                                          solar_rad_NN  （剔除朝北屋面）
                                                 ▼
                                          Layout view → 出图 → Export
```

---

### 5.1 Step 1 — 打开数据、熟悉图层

1. 新建 ArcGIS Pro 工程。
2. 从 Blackboard 下载并打开 map package **`Burnage.mpkx`**。
3. 在 **Contents Pane**（内容窗格）里逐个开关图层，看清各自内容。

> 📎 背景补充：`.mpkx` 是 ArcGIS Pro 的 **map package**，双击即可在 Pro 中打开并自动解包到工程中；它把地图、图层、符号系统和数据源打包在一起。教程未解释这个扩展名。

### 5.2 Step 2 — 生成 Hillshade（晕渲）

**目的**：DTM 的灰阶图能看出一些图案，但 hillshade 用**模拟光照**呈现表面，判读效果好得多。

**操作**

1. 在 **Geoprocessing pane** 中搜索 **`Hillshade`** 工具。
2. **使用默认设置**（教程原文：*"using the default setting"*）。
3. 输出命名为 **`HillShade_DTM_1m`**。

**叠加显示技巧（教程明确给出）**

4. 在 **Contents pane** 中把 **DTM 图层拖到 `Hillshade_DTM_1m` 图层之上**。
5. 把 DTM 图层的 **layer transparency 设为 40 percent**（40% 透明度）。

→ 这样两个图层同时可见：hillshade 提供立体感，DTM 的灰阶提供高程信息。

> 📎 背景补充：设置透明度的路径是 —— 选中图层 → **Feature Layer / Raster Layer 上下文选项卡 → Appearance 选项卡 → Transparency 框**输入 40。教程只说了「set to 40 percent layer transparency」，没给路径。
>
> 📎 背景补充：`Hillshade` 工具（Spatial Analyst Tools > Surface）的默认参数为 **Azimuth = 315**、**Altitude = 45**、**Model shadows = 不勾选**、**Z factor = 1**。这与讲座里老师说的「usually from the northwest at 45 degrees above the horizon」完全对应。**教程说「用默认值」但没列出默认值是什么。**

### 5.3 Step 3 — 查看建筑轮廓

**图层**：`Burnage_Local_Buildings` —— 与 DTM/hillshade（栅格）不同，这是**矢量 polygon 图层**。

**操作**：缩放平移浏览 Burnage 区域。

**要观察到的现象（教程原文）**：建筑类型多样，从独栋住宅到较大的商业与学校建筑；**部分区域有树木，会影响太阳能发电**。

### 5.4 Step 4 — Area Solar Radiation（本 practical 的核心工具）

**工具全称**：**`Area Solar Radiation`**
**所属**：**ArcGIS Spatial Analyst extension**（教程明确指出需要此扩展许可）
**输入**：DTM 栅格
**输出**：每个像元的太阳辐射量，单位 **watt-hours per square meter（Wh/m²）**

**工具原理（教程原文，理解性内容，要能复述）**

> "It calculates radiation based on a sophisticated model that takes into account **the position of the sun throughout the year and at different times of day**, **obstacles that may block sunlight such as nearby trees or buildings**, and **the slope and orientation of the surface**."

**→ 三个信息来源都来自 DTM 本身**：DTM 提供障碍物（obstacles）、朝向（orientation）、坡度（slope）；太阳位置由**纬度＋时间配置**决定。

> ⏱️ **教程明确警告**：*"The Area Solar Radiation tool is computationally intense and may take **about 10 minutes** to run."* —— 这也是下面几个参数都在「降低计算量」的原因。

**菜单路径（教程原文，逐字照抄）**

> On the ribbon, on the **Analysis** tab, in the **Geoprocessing** group, click **Tools**.
> The **Geoprocessing** pane appears.
> Search for and open the **Area Solar Radiation** tool.

即：**Analysis 选项卡 → Geoprocessing 组 → Tools → 在 Geoprocessing 窗格中搜索 "Area Solar Radiation"**。

**参数设置（教程给出的全部参数）**

| 参数（英文原名） | 设置值 | 教程给的理由 |
|---|---|---|
| **Input raster** | `Burnage_DTM_1m` | — |
| **Output global radiation raster** | `Solar_Rad` | — |
| **Latitude** | **自动填充** | *"When the input raster is chosen, the Latitude parameter is **automatically populated** with the latitude of the DTM. This parameter helps determine the sun's position."* **不要手动改。** |
| **Time configuration** | **`Whole year`** | 默认是「间隔若干天」，改成全年才能得到年总量 |
| **Year** | **`2024`** | *"If necessary"*——若上一步没自动填就填 2024 |
| **Hour interval** | **`1`** | 默认每半小时算一次；改成每小时**以减少计算时间** |
| **Topographic parameters > Calculation directions** | **`16`** | 默认检查每个像元周围 **32** 个方向找遮挡物；改成 16 **以减少计算时间** |
| **Environments > Raster Analysis > Mask** | `Burnage_Local_Buildings` | *"so that **only areas within the building footprints will be processed**, again saving calculation time"* |

**⚠️ Mask 的设置位置容易漏**：它**不在主参数页**，要点工具面板顶部的 **`Environments` 选项卡**，展开 **Raster Analysis** 分组，才能看到 **Mask**。

最后点 **Run**。

**📎 背景补充：Area Solar Radiation 的完整参数与默认值**

> ⚠️ **以下整块都是背景补充。教程只列了上表那 7 个参数，其余参数它一律使用默认值且未列出。** 下列默认值为 ArcGIS Pro Spatial Analyst 文档中的通行取值，**实际使用时请以你机器上工具面板显示的为准**。

| 参数 | 默认值 | 含义 |
|---|---|---|
| **Sky size / Resolution** | `200`（像元） | 生成的 **viewshed / sunmap / skymap** 栅格的边长。值越大越精细也越慢 |
| **Time configuration** | `Multiple days in a year`（默认起止为当年整年，Day interval = 14） | 时间积分范围。可选 Special days / Within a day / Multi days in a year / Whole year |
| **Day interval** | `14` | 多日模式下，每隔几天取一次样 |
| **Hour interval** | `0.5` | 每天内每隔几小时算一次 |
| **Each interval / Create outputs for each interval** | 不勾选 | 勾选后为每个时段单独输出栅格 |
| **Z factor** | `1` | 高程单位与平面单位的换算系数。**平面单位与高程单位都是米时保持 1**；若平面是度而高程是米则必须改 |
| **Slope and aspect input type** | `FROM_DEM` | 从输入 DEM 计算坡度坡向（另一选项是用平坦表面 FLAT_SURFACE） |
| **Calculation directions** | `32` | 计算 viewshed 时围绕像元检查的方位数，**必须是 8 的倍数** |
| **Zenith divisions** | `8` | 天空半球在**天顶方向**上被分成几层 |
| **Azimuth divisions** | `8` | 天空半球在**方位方向**上被分成几扇，**必须是 8 的倍数** |
| **Diffuse model type** | `UNIFORM_SKY` | 散射辐射模型。另一选项 `STANDARD_OVERCAST_SKY`（阴天，散射随天顶角变化） |
| **Diffuse proportion**（扩散比例） | `0.3` | 总辐射中散射所占比例。**0–1。晴朗天空取 0.2 左右，多云天空取 0.7 左右** |
| **Transmittivity**（透射率） | `0.5` | 大气对辐射的整体透过率。**0（全不透）–1（全透），0.5 为通用晴空值** |

**可选输出栅格**（教程只用了第一个）：

- **Output global radiation raster**（总辐射，必需）
- **Output direct radiation raster**（直接辐射）
- **Output diffuse radiation raster**（散射辐射）
- **Output direct duration raster**（直接日照时长）

> **`Zenith divisions` 与 `Azimuth divisions` 在做什么**（📎）：工具把整个天空半球离散成一张网格（**skymap**），天顶方向切 8 层、方位方向切 8 扇 = 64 个天空扇区（sky sector）。同时从每个像元向外做 viewshed，判断每个天空扇区对该像元是否可见。总辐射 = Σ（各可见扇区的直接辐射 + 散射辐射）。**方位分区数越多，对建筑与树木遮挡的刻画越精细，计算越慢** —— 这正是教程把 `Calculation directions` 从 32 降到 16 的代价所在。

**结果判读**

- 每个像元的值 = 该位置**全年**接收的总太阳辐射（Wh/m²）。
- 由于设了 mask，**只有建筑轮廓内的像元有值**，其余为 NoData。
- 部分像元超过 **1,000,000 Wh/m²** —— 数字太长不利于读图，所以下一步要换单位。

### 5.5 Step 5 — Raster Calculator 换算单位（Wh/m² → kWh/m²）

**为什么要换**（教程原文）：*"To reduce the size of these values and **make them easier to read**"* —— 这是一个**制图学理由**（图例数字太长会破坏可读性），呼应本周讲座主题。

**操作**

1. 先在 Contents pane 里**关掉 `Burnage_Local_Buildings` 图层**（后面不需要了）。
2. Geoprocessing pane 搜索并打开 **`Raster Calculator`**（教程写作 "Raster Calculator (Spatial Analysis Tool)"，正确名称为 **Spatial Analyst Tools**，见勘误表）。
3. 在 **Map Algebra expression** 框中输入（或用上方的图层/运算符按钮点选构建）：

   ```
   "Solar_Rad" / 1000
   ```

4. **Output raster** 命名为 **`solar_rad`**（**注意与输入 `Solar_Rad` 只差大小写**——见「易错点」）。
5. **Run**。
6. 结果与原图形态一致但数值小 1000 倍。**原始 `Solar_Rad` 图层可以移除。**

> 📎 背景补充：`Raster Calculator` 位于 **Spatial Analyst Tools > Map Algebra**。表达式里图层名要用**双引号**包住（也可以从对话框上方的 Rasters 列表双击插入）。若输入栅格是整型，除法会做整数除；本例是浮点型，无此问题。教程未说明这些。

### 5.6 Step 6 — 把结果放进现实语境（Practical §6.1）

这一步不涉及软件操作，是**结果解释**，但教程写得很实在，考核可能问到。完整算式见 **3.3 节**。

**关键结论**

1. 屋顶年入射辐射约 **500–1000 kWh/m²/yr**。
2. 家用光伏转换效率仅 **10–20%**，按 17% 算，800 kWh/m² → **136 kWh/m²**。
3. 反向估算：3.5 kW 系统 × 5 h/day = 17.5 kWh/day，÷ 28 m² = **625 Wh/m²/day**（理想条件）。
4. 实际约 **200–300 Wh/m²/day**。
5. 影响因素：**orientation、weather、pitch、efficiency、shading**。

**教程接下来要用 GIS 处理其中两条筛选准则**：

| 准则 | 阈值 | 教程给的理由 | 需要生成的图层 |
|---|---|---|---|
| **坡度（pitch）** | **≤ 45°** | *"steep slopes tend to receive less sunlight"*；**注意：平屋顶也适合装光伏板**（*"Note that flat roofs are suitable for solar panels."*） | **Slope** 栅格 |
| **朝向（aspect）** | **不朝北** | *"north-facing rooftops in the **northern hemisphere** receive less sunlight"* | **Aspect** 栅格 |

### 5.7 Step 7 — Surface Parameters 生成 Slope（坡度）

**工具**：**`Surface Parameters (Spatial Analyst Tools)`**

**操作**

1. Geoprocessing pane 搜索并打开 **`Surface Parameters`**。
2. **Input surface raster** → `Burnage_DTM_1m`
3. **Output raster** → `Slope_DTM`
4. **Parameter type** → 确认为 **`Slope`**
5. **Environments 选项卡 → Raster Analysis → Mask** → `Burnage_Local_Buildings`
6. **Run**

**结果判读（教程原文）**

> "Each cell in this layer contains a slope value ranging from **0 to 90 degrees**. The **lighter colours represent steeper slopes** while **darker colours represent milder slopes**."

> 📎 背景补充：`Surface Parameters` 是 ArcGIS Pro 2.8 之后引入的工具，**与老的 `Slope` / `Aspect` / `Curvature` 工具不同**——它用**局部二次曲面拟合（quadratic surface fit）** 而非 3×3 窗口的有限差分，并提供 **Neighborhood distance**（邻域距离，默认 = 一个像元大小）和 **Adaptive neighborhood** 选项，对噪声更稳健。`Parameter type` 下拉里除 Slope / Aspect 外还有 Mean curvature、Tangential (normal contour) curvature、Profile (normal slope line) curvature、Contour geodesic torsion 等。教程只说了"搜索 Surface Parameters"，未解释它与经典 Slope 工具的差异。
>
> 📎 背景补充：`Slope` 的输出单位可由 **Output slope measurement** 参数控制（Degree 或 Percent rise），默认 **Degree**。教程未提及。

### 5.8 Step 8 — Surface Parameters 生成 Aspect（坡向）

**同一个工具，改两个参数即可**（工具面板保持打开状态）。

1. **Input surface raster** → 保持 `Burnage_DTM_1m`
2. **Output raster** → `Aspect_DTM`
3. **Parameter type** → 改为 **`Aspect`**
4. **Environments > Raster Analysis > Mask** → `Burnage_Local_Buildings`
5. **Run**

**结果判读（教程原文）**

> "Each cell contains a value expressing **orientation in degrees**, with **0 representing absolute north** and **180 representing absolute south**."

即：**0° = 正北，90° = 正东，180° = 正南，270° = 正西，360° 回到正北。**

> 📎 背景补充：ArcGIS 的 aspect 栅格中，**完全水平（flat）的像元被赋值 −1**（不是 0）。这一点教程完全没提，但它在下一步的 Con 表达式里会产生实质后果 —— 见 5.9 的警告。

### 5.9 Step 9 — 用 Con 剔除朝北屋面

**先看坡度筛选（Step §6.4）**

教程原文：*"Looking at the legend for the `Slope_DTM` raster **there are no slopes steeper than 45 degrees** so we do not need remove any cells with values higher than this threshold."*

**→ 教程直接跳过了坡度筛选这一步。⚠️ 但这个结论依赖于你自己的输出结果，务必自己看一眼 `Slope_DTM` 的图例最大值再决定（见勘误表）。**

**朝北的定义**

教程原文：*"Based on the `Aspect_DTM` legend, slopes that face north have a value **less than 22.5 degrees or more than 337.5 degrees**."*

**→ 这是把整个圆周 360° 平分成 **16 个方位**（每个 22.5°），正北方位覆盖 **337.5°–360°** 与 **0°–22.5°**，合计 45°。**

**工具**：**`Con (Spatial Analyst)`**（Conditional，条件函数）

教程对工具的解释：*"The Con (conditional) tool allows you to **control the output value for each cell based on whether the cell value is evaluated as true or false** in a specified conditional statement."*

**操作**

1. Geoprocessing pane 搜索 **`Con (Spatial Analyst)`**。
2. **Input conditional raster** → `Aspect_DTM`
3. 构建表达式（两个子句）：
   - 第一句：**`Where VALUE is greater than 22.5`**
   - 点 **`Add Clause`**（添加子句）
   - 第二句：**`And VALUE is less than 337.5`**

   → 合起来即 `VALUE > 22.5 AND VALUE < 337.5`，**覆盖所有「不朝北」的表面**。
4. **Input true raster or constant value** → **`solar_rad`**
   （教程解释：*"Ultimately, you want to compute the solar radiation potential of the rooftops, so you'll have the output layer use solar radiation cell values."* —— **条件判断用 aspect，输出取值用 solar_rad**，这是 Con 工具最容易绕晕的地方。）
5. **Input false raster or constant value** → **留空**（→ 不满足条件的像元变成 **NoData**，即被剔除）
6. **Output raster** → **`solar_rad_NN`**（教程注：*"NN stands for **No North**"*）
7. **Run**

**结果判读（教程原文）**

> "You may **not notice very much visual difference** between the `solar_rad` and `solar_rad_NN` rasters but **by comparing the legends of these two layers** you can see that **some of the lower solar radiation surfaces have been excluded**. This is expected because north-facing roof surfaces will receive lower solar radiation levels."

**→ 判读要点：不要看图面，要看图例的最小值 —— `solar_rad_NN` 的下限应当比 `solar_rad` 高。** 这本身就是一个「结果自洽性检验」。

**教程的免责声明**：*"For actual solar panel installation, it would be necessary to look at each rooftop in more detail, but for the purpose of your analysis, this approximation is sufficient."*

**最后：`Save` 你的 Project。**

> ⚠️ **一个教程没有察觉的逻辑漏洞（务必注意）**：§6.1 明确写了 *"**flat roofs are suitable** for solar panels"*（平屋顶适合装板），但 aspect 栅格中平坦像元的值是 **−1**，而 Con 的条件是 `VALUE > 22.5 AND VALUE < 337.5` —— **−1 不满足第一个子句，因此所有平屋顶都被判为 false，连同朝北屋面一起被剔除了**。这与教程自己的准则矛盾。
>
> 📎 修正做法（材料未给）：把条件改为把 −1 也放行，例如三子句 `(VALUE = -1) Or (VALUE > 22.5 And VALUE < 337.5)`，或先用另一个 Con/Reclassify 把 −1 重编码为一个安全值（如 180）。**这一点若在报告里主动指出，是加分项。**

### 5.10 Step 10 — Map layout（地图排版）

> ⚠️ **教程在这一步没有给逐步操作**，只给了一个 Esri 官方文档链接和 6 条 hints：
> https://pro.arcgis.com/en/pro-app/latest/get-started/add-maps-to-a-layout.htm
> （教程说该页有视频演示如何添加与修改各要素）
> 教程的唯一硬性要求：*"**Make sure you include all the elements required to communicate the purpose and results of your map.**"* —— **即讲座 2.1 节那张要素清单。**
>
> **下面 5.10.1–5.10.5 的具体操作路径全部是 📎 背景补充**（教程未写），5.10.6 才是教程原文给的 hints。

#### 5.10.1 📎 Map view 与 Layout view 的区别

| | **Map view**（地图视图） | **Layout view**（布局视图） |
|---|---|---|
| 显示什么 | 只有地图内容，铺满整个窗口 | 一张**虚拟纸张**（page），上面放一个或多个 **map frame** 及各种 map surrounds |
| 有没有页面尺寸 | 无 | **有**（A4/A3/自定义，含方向与边距） |
| 能不能放图例/比例尺/指北针 | **不能** | **能** |
| 用途 | 分析、判读（前 9 步都在这里做） | **出图**（第 10 步） |
| 缩放的含义 | 只是看得近/远 | 有真实的 **map scale**，会写进比例尺 |

**关键概念：Map frame（地图框）** —— Layout 里承载地图的那个矩形容器。**图例、比例尺、指北针都是"绑定到某个 map frame"的**，所以插入它们之前必须先选中对应的 map frame，否则会绑错（多图幅时尤其容易出错）。

#### 5.10.2 📎 创建 Layout 并放入地图

1. **Insert 选项卡 → Project 组 → New Layout** → 选页面尺寸（如 **A4 Landscape**）。
2. **Insert 选项卡 → Map Frames 组 → Map Frame** 下拉 → 选择要放入的地图 → 在页面上拖出矩形。
3. 调整地图范围：用 **Layout 选项卡 → Map 组 → Activate**（激活 map frame，进入内部平移缩放）→ 调好后点 **Layout 选项卡 → Close Activation**。
4. 设定精确比例：选中 map frame → **Format Map Frame 窗格 → Map Frame → Constraint** 设为 **Fixed Scale**，并填入整数比例（如 1:5,000）。**→ 用整比例尺，图形比例尺的刻度才好看。**

#### 5.10.3 📎 插入各 map surrounds（图廓要素）

**全部在 Insert 选项卡 → Map Surrounds 组**。**每次插入前先在页面上选中目标 map frame。**

| 要素 | 路径 | 关键设置 |
|---|---|---|
| **Legend**（图例） | Insert > Map Surrounds > **Legend** → 在页面上拖框 | 选中后打开 **Format Legend** 窗格：<br>• **Legend > Show > Title / Layer names / Headings / Labels / Descriptions** 逐项开关<br>• **Legend Items**：右键单个条目可单独控制显示<br>• **⚠️ 图例条目 = Contents pane 里勾选的图层**，多余的图层要么在 Contents 里取消勾选，要么在 Legend Items 里移除 |
| **Scale Bar**（比例尺） | Insert > Map Surrounds > **Scale Bar** 库 → 选一种样式 | **选 graphic scale bar 样式**（讲座结论）。选中后 **Format Scale Bar > Divisions**：设 **Divisions（大格数）**、**Subdivisions（小格数）**、**Units**（Kilometers/Meters）、勾 **Show one division before zero** 等 |
| **North Arrow**（指北针） | Insert > Map Surrounds > **North Arrow** 库 | 样式选简洁的即可。**它随 map frame 的旋转自动调整**——不要手动旋转 |
| **Text**（文字） | Insert > **Graphics and Text** 组 → **Text**（矩形文本 / 直线文本等） | 用于标题、credits、姓名学号、日期、投影信息 |
| **Dynamic Text**（动态文本） | Insert > Graphics and Text 组 → **Dynamic Text** 库 | 自动引用工程属性（日期、比例尺、坐标系、服务图层版权等），内容随工程变化自动更新 |
| **Grid / Graticule**（格网） | 选中 map frame → Insert 选项卡 → **Map Frames 组 → Grid** 库 | 见 5.10.6 第 4 条 |
| **Chart Frame / Table Frame** | Insert > Map Surrounds | 用于做 2.12 那种「图＋图表」多变量地图 |

**标题的做法**：不要用 Legend 的 title 当图名。用 **Insert > Text**，字号明显大于其他文字，放在页面**顶部**（讲座：*"Title always goes at the top"*）。

#### 5.10.4 📎 位置图（location map / inset）的做法

教程 hint 2 提到要"add a location map"。完整做法：

1. **Insert > Project 组 > New Map**（建第二张地图）→ 设为更大范围（如整个 Greater Manchester）。
2. 回到 Layout，**Insert > Map Frames > Map Frame** 再插一个小框，选这张新地图。
3. 建立**范围指示器**（让小图上出现主图范围的红框）：选中小 map frame → **Insert 选项卡 → Map Frames 组 → Extent Indicator** → 选择主 map frame。

> 教程没提 **Extent Indicator**，但没有它，位置图就只是一张孤立的小图，读者不知道主图在哪。**这是 inset 的核心功能。**

#### 5.10.5 📎 导出（Export）

**路径**：**Share 选项卡 → Output 组 → Export Layout**（教程写作 "Share > Export"）。

**关键参数**

| 参数 | 说明 | 建议 |
|---|---|---|
| **File Type** | PDF / TIFF / JPEG / PNG / SVG / EPS / BMP / GIF / AIX | 教程用的是 **JPEG**（*"My map was exported as a jpeg image"*）。**要嵌进报告、需要保真 → 用 PDF 或 PNG；JPEG 会对文字与线条产生压缩伪影** |
| **Resolution (DPI)** | **默认 96 DPI**（屏幕分辨率） | **⚠️ 一定要改。屏幕看 → 150；报告/打印 → 300；出版 → 至少 300** |
| **Clip to Graphics Extent** | 裁到图形范围 | 通常不勾（保留页边距） |
| **Vector / Raster resampling** | 矢量输出的重采样质量 | PDF 导出时可保持默认 |
| **Embed fonts** | 嵌入字体（PDF） | **建议勾选**，避免在别人机器上字体替换 |
| **Compress vector graphics / Image compression** | 压缩 | PDF 交作业时可用默认 |

#### 5.10.6 教程给出的 6 条 Hints and tips（原文内容，可靠）

1. **移除 service layer credits（服务图层版权文字）**
   > "ArcGIS Pro adds service layer credits to your map, you will probably want to remove these as they tend to **make the map too cluttered**."
   >
   > 操作：*"On the **Map Frame** group, **Dynamic text** drop down scroll down the list until you see **Service Layer Credits**, select this and then **click on the credits on the map so they are selected (black box)**. **Uncheck** the appropriate text box in the contents pane (**trial and error may be necessary if you have several text boxes**), in the example below unchecking **Text 3** removed them."

   > 📎 说明：ArcGIS Pro 的 **Dynamic Text 在 Insert 选项卡的 Graphics and Text 组**，"Map Frame" 是这个下拉库里的**一个分类**（Service Layer Credits 列在该分类下），不是 ribbon 上的一个组。教程的表述容易让人在 ribbon 上找不到。见勘误表。

2. **加位置图可能需要新底图**
   > "Click on the **Map layer** and select **New Map** > **New Basemap**."
   > 教程作者用的底图：主图用 **GB Light Grey**，位置图用 **World Topographic Map**。

   > 📎 说明：正确路径是 **Insert 选项卡 → Project 组 → New Map 下拉 → New Basemap**。见勘误表。**主图用浅灰底图是很好的选择**——它把底图压到视觉层次的最低层，让太阳辐射数据"浮"起来（stereogrammic method 的实践）。

3. **分幅策略**
   > "My map shows the solar radiation for **south Burnage** – I could have made **two separate maps** covering south and north Burnage or a **multi-panel map** with south and north on the same page."

   → **区域太长条时，与其硬塞进一个框里比例尺被迫拉得很小，不如分幅。** 这呼应讲座那句 *"it depends upon the shape of your geographical area"*。

4. **加格网**
   > "I did not add a grid to my map but this can be done by clicking on the **Map Frame** in the **Contents pane** and the **Insert > Grids**."

5. **加个人信息**
   > "You can also add your **name, student number, date of creation**, and further text, etc to enhance your map."
   > **→ 这基本等于告诉你 assessment 的地图上要有这些。**

6. **导出**
   > "To print your map or export it you can **Share > Export** in a number of formats. My map was exported as a **jpeg** image."

### 5.11 常见报错与卡点处理

> 📎 **以下整节为背景补充**，教程未提供任何错误处理内容。

| 症状 | 原因 | 处理 |
|---|---|---|
| `Area Solar Radiation` 工具搜不到 / 灰掉 | **Spatial Analyst extension 未启用** | **Project 选项卡 → Licensing → Configure your licensing options**，勾选 **Spatial Analyst**，重启 Pro |
| Area Solar Radiation 跑了很久没结束 | 正常。教程说 ~10 分钟 | 已把 Hour interval 设为 1、Calculation directions 设为 16、并设了 Mask。若仍太慢，可再把 **Sky size** 从 200 降到 100 |
| Area Solar Radiation 报错说输入必须是投影坐标系 | 输入 DEM 在**地理坐标系（度）** | Area Solar Radiation 要求**投影坐标**（平面单位与高程单位一致）。本例 DTM 已是 British National Grid，不会遇到。若遇到，先 `Project Raster`，或设 **Z factor** |
| 输出全是 NoData | Mask 图层与输入栅格**范围不相交**，或坐标系不一致 | 检查 Environments 的 **Extent** 与 **Mask**；确认两者同一坐标系 |
| Raster Calculator 报「表达式无效」 | 图层名没加双引号，或名字里有空格/特殊字符 | 从对话框上方的 Rasters 列表**双击插入**图层名，不要手打 |
| Raster Calculator 输出名 `solar_rad` 与输入 `Solar_Rad` 冲突 | **File geodatabase 的要素名不区分大小写** | 若报「output already exists」，改一个明显不同的名字（如 `solar_rad_kwh`），并**在 Contents pane 里同步改图层显示名** |
| Con 工具的结果全是 NoData | **Input true raster** 选错（选成了 Aspect_DTM 而不是 solar_rad），或条件写反了 | 条件用 `Aspect_DTM`，true 值用 `solar_rad`，false 留空 |
| Con 之后平屋顶消失了 | aspect 平坦像元 = **−1**，被 `VALUE > 22.5` 排除 | 见 5.9 末尾的修正做法 |
| Layout 里图例列出了一堆不想要的图层 | 图例条目 = Contents 里勾选的所有图层 | 在 **Contents pane 取消勾选**中间过程图层，或在 **Format Legend > Legend Items** 里移除 |
| 导出的图模糊 / 文字发虚 | **DPI 仍是默认 96**，或用了 JPEG | 改 **Resolution = 300**，格式改 PDF/PNG |
| 导出后比例尺与实际不符 | map frame 的 **Constraint 没设为 Fixed Scale**，导出前又平移缩放过 | 设 **Fixed Scale**，或导出前重新检查 scale bar |
| 位置图上看不出主图在哪 | 没加 **Extent Indicator** | 见 5.10.4 |

---

## 六、易错点 / 重点难点

### 6.1 🥇 头号制图错误：分级设色图用绝对计数而非密度/比率

> 📎 **本条为背景补充**——**本周材料完全没有讲这条规则**，但它是制图学公认的头号错误，且讲义 Page 26 的示例图恰恰用的是绝对计数（`No. of households`）。

**机制**：choropleth 用整个多边形的面积承载颜色，**面积大的单元天然获得更多视觉权重**。填绝对计数时，一个大而稀疏的区可能和一个小而稠密的区同色，读者读到的是"哪里大"而不是"哪里强"。

**规则**：**choropleth 必须填密度（人/km²）、比率（%）或人均值（每千人）。** 要表达绝对量，请改用 **proportional / graduated symbol map** 或 **dot map** —— 这三种符号的大小与多边形面积无关。

### 6.2 分级方法随手用默认值

- **ArcGIS Pro 的 Symbology 默认是 Natural Breaks (Jenks)**（📎，材料未提）。它对**当前这份数据**优化，因此：
  - **跨图不可比** —— 两张用 Jenks 分级的图，颜色相同不代表数值相同。做时间序列或多区域对比时**必须手动固定断点**。
  - 类宽不规则，读者难以从图例反推数值（老师原话：*"doesn't make it very easy to compare the districts in terms of their absolute values"*）。
- **Equal interval 会产生空类**（老师明确指出第 5 类在图上无对应）。
- **Quantile 会造成 distorted map** —— 数值相近的两个单元可能被硬分到两类。
- **结论**：老师的态度是 *"I'm not suggesting you use any of these"* —— **没有"正确"的分级方法，只有"是否服务于你的 key message"，且必须在图上注明用了哪种。**

### 6.3 Proportional 与 Graduated 混用

**是否先分级是唯一判据。** Proportional = 连续、每值一大小；Graduated = 先分 bin、阶梯式。图例形式也不同（嵌套圆 vs 离散尺寸）。

> 📎 补充：真正的比例符号图应当让**符号面积**正比于数值（即半径 ∝ √value）。若让**直径**正比于数值，面积会按平方放大，严重夸大高值。转写里 *"the next size up is 10 times larger dot, which represents 100 people"* 是口语化的表述，不宜按字面理解。**材料未讨论这一点。**

### 6.4 📎 发散色带用在没有中心值的数据上

> 📎 **本条为背景补充，材料未涉及。**

**Diverging 色带的中间那个中性色是在宣告"这里有一个有意义的参照点"**（零、均值、目标值）。若数据只是单向递增（如太阳辐射量、人口密度），用发散色带会凭空制造一个不存在的分界，读者会以为中性色处有实质意义。**单向数据一律用 sequential。**

反过来：**标准差分级（2.7 (d)）天然有中心值（均值），是发散色带的正确用武之地。**

### 6.5 图例缺单位 / 单位写错

**本周材料里就有一个现成的反例**：practical 末页示例图的图例标题写作 **`Annual Solar Radiation (kW/hr/m2)`** —— **单位错了**。

- **kWh/m²** = 千瓦·时 / 平方米 = **能量密度**（正确）
- **kW/hr/m²** = 千瓦 / 小时 / 平方米 = 功率对时间的变化率 / 面积（**物理上完全不同的量**）

正文说明里写的是 *"in kilowatt-hours per square meter"*（正确），**图例却写错了**。→ **图例是读者唯一的解码器，单位必须写全写对。** 见勘误表。

### 6.6 比例尺在导出后与实际不符

- **用 ratio scale（1:5000）而不用 graphic scale bar**：一旦缩放打印或插入 Word 后被拉伸，比例式就是错的。**老师明确要求展示地图用 graphic scale bar。**
- **map frame 未设 Fixed Scale**：在 Layout 里不小心平移缩放会改变比例，而 scale bar 会跟着变，但如果你已经在别处写死了比例数字就对不上了。
- **📎 补充**：设 **Format Map Frame > Constraint = Fixed Scale**，并用整数比例。

### 6.7 版面的视觉中心被非主体要素占据

诊断：眯眼看灰度块，最重的必须是 map body。若 scale bar / legend / 大段文字落在页面中央偏上，版面就失败了。**Title 在上、Legend 在侧或底、其余压到角落。**

### 6.8 Area Solar Radiation 的参数陷阱

| 陷阱 | 后果 | 正解 |
|---|---|---|
| **手动改了 Latitude** | 太阳高度角全错，辐射量系统性偏差 | **选好输入栅格后 Latitude 自动填充，不要动**（教程明确说明） |
| **Time configuration 留默认** | 默认是"一年中若干天、每 14 天采样"，**不是全年积分** | 必须改成 **`Whole year`**，并确认 **Year** 正确（教程用 2024） |
| **忘了在 Environments 设 Mask** | 整个 DTM 全域参与计算，**运行时间暴涨且大量无用像元** | Environments > Raster Analysis > **Mask** = `Burnage_Local_Buildings` |
| **Hour interval / Calculation directions 保留默认** | 0.5 h × 32 方向，计算量约为教程设置的 **4 倍** | 教程改为 1 h、16 方向 |
| 📎 **Z factor 未按需设置** | 输入栅格是地理坐标（度）而高程是米时，坡度坡向全错 | 平面与高程单位一致时保持 1；不一致时必须换算 |
| 📎 **误以为结果考虑了天气** | 该工具**不含云量/天气模型**，结果是"晴空上限" | 教程 §6.1 的现实折减（200–300 vs 625 Wh/m²/day）正是在提醒这一点 |

### 6.9 Con 工具的三个坑

1. **条件栅格与取值栅格混淆** —— `Input conditional raster` = `Aspect_DTM`（判断依据），`Input true raster or constant value` = `solar_rad`（输出值）。**这两个填反是本步最常见的错误。**
2. **平屋顶（aspect = −1）被误剔除** —— 见 5.9 末尾。**教程本身有这个 bug。**
3. **false 值留空 = NoData** —— 这是有意的（剔除），但要清楚这意味着输出栅格里那些像元**不是 0，是没有值**。做后续统计时 0 与 NoData 结果完全不同。

### 6.10 导出忘了设 DPI

**默认 96 DPI**。插进报告放大看就是糊的。**报告用 300 DPI，且优先 PDF/PNG 而非 JPEG。**（📎 教程只说"exported as a jpeg"，未提 DPI。）

### 6.11 忘了必备要素

对照 2.1 的清单逐项自检：**Title / Map body / Legend / North arrow / Scale bar / Credits（数据来源）**，加上教程 hint 5 要求的**姓名、学号、制图日期**。Neatline、Inset、Grid 可选。

### 6.12 教程把 DTM 当成 DSM

见 5.0 的警告与勘误表。**概念上要清楚：DTM = 裸地表（bare earth），DSM = 含地物（建筑、树冠）。本 practical 用的数据必须含建筑，因此实为 DSM。** 若在报告里用错术语会被扣分。

---

## 七、本周术语表

### 7.1 制图学与可视化术语

| 英文 | 中文 | 说明 |
|---|---|---|
| Spatial visualisation | 空间可视化 | 本周主题；老师称之为 *"a rather grand way of saying maps"* |
| Cartography | 制图学 | |
| Cartographic elements | 地图（图廓）要素 | 见 2.1 清单 |
| Map body | 图面主体 | 应占据视觉中心 |
| Title | 图名 | 永远在顶部 |
| Legend | 图例 | 永远在侧边或底部 |
| North arrow | 指北针 | *"always needs to be present"* |
| Scale bar | 比例尺 | |
| Graphic scale bar | 图形比例尺 | 展示地图首选，随打印尺寸自动正确 |
| Ratio / representative fraction | 比例式 / 代表分数 | 如 1:50,000；打印缩放后失效 |
| Inset | 嵌图 | 局部放大图或 location map |
| Location map | 位置图 | 显示研究区在更大范围中的位置 |
| Credits | 制图信息 / 出处 | 数据来源、制图者 |
| Neatline | 图廓线 | 框住整幅图；可选 |
| Grid | （投影坐标）格网 | |
| Graticule | 经纬网 | 📎 材料未区分 grid 与 graticule |
| Visual centre | 视觉中心 | **略高于页面几何中心**（转写独有概念） |
| General purpose map | 普通地图 / 参考图 | |
| Topographic map | 地形图 | UK 由 Ordnance Survey 生产 |
| Base map | 底图 | 叠加专题图层的基础层 |
| Thematic map | 专题地图 | |
| Dot map | 点子图 / 点密度图 | 每点代表固定数量（如 100 persons per dot） |
| Proportional symbol map | 比例符号图 | 连续值，符号连续缩放 |
| Graduated symbol map | 分级符号图 | 先分级，符号阶梯式变化 |
| Choropleth map | 分级设色图 | 按行政/统计单元着色 |
| Bivariate choropleth map | 双变量分级设色图 | 二维色彩矩阵图例 |
| Isoline map | 等值线图 | contours / isobars / isotherms |
| Contour | 等高线 | |
| Isobar / Isotherm | 等压线 / 等温线 | |
| Hypsometric map | 分层设色图 | 等高线之间填色；hypsometry = 相对海平面的高程或深度测量 |
| Hill-shaded map / Hillshade | 晕渲图 | 默认光照方位角 315°、高度角 45° |
| Multivariate mapping | 多变量制图 | 同时显示 ≥2 个属性 |
| Map design | 地图设计 | Selection / Classification / Symbolisation / Layout design |
| Selection | 选取 | 范围、要素、比例尺、投影、变量 |
| Classification | 分级 / 分类 | 5–8 类为宜 |
| Symbolisation | 符号化 | *"Symbol geometry is qualitative not quantitative"* |
| Layout design | 版面设计 | |
| Equal interval | 等间隔分级 | 类宽相同；易出空类 |
| Natural breaks (Jenks) | 自然断点分级 | 找数据间隙；类宽不规则 |
| Quantile | 分位数分级 | 每类要素数相同；类宽差异大 |
| Standard deviation | 标准差分级 | 断点为 ±0.5σ、±1σ、±1.5σ… |
| Class / Bin | 类 / 分箱 | |
| Class break | 分级断点 | |
| Visual variables | 视觉变量 | shape / size / colour / pattern / orientation |
| Visual hierarchy | 视觉层次 | 由 colour intensity、colour hue、shading pattern、symbol size 建立 |
| Stereogrammic method | 立体式（视觉层次） | 让主要要素"浮"在底图之上 |
| Extensional method | 扩展式（视觉层次） | 同类要素分主次，如道路等级 |
| Subdivisional method | 细分式（视觉层次） | 色相分大类，纹理分子类 |
| Map lettering | 地图注记 | |
| Annotation | 注记 | |
| Colour ramp | 色带 | choropleth 用单色不同明度；**不要彩虹色** |
| Sequential / Diverging / Qualitative scheme | 顺序/发散/定性色带 | 📎 三类划分为背景补充，材料未讲 |
| 2.5D | 二维半 | 一个 (x,y) 对应一个 z 属性值，向上 extrude |
| Voxel (volume pixel) | 体元 / 体素 | 真三维的基本单元（转写独有） |
| Stepped statistical surface | 阶梯统计面 | 按属性值把面抬升 |
| Extrude | 拉伸 / 抬升 | |
| Animated mapping | 动画制图 | 展示 time / space / attribute 的变化 |
| Track | 轨道 | 一串单幅地图组成的序列 |
| Frame | 帧 | track 中的一个地图图层 |
| Keyframing | 关键帧技术 | 先做特征帧，计算机插值中间帧 |
| Temporal / Non-temporal animation | 时间/非时间动画 | 前者数据须有时间分量；后者如 fly-through |
| Fly-through animation | 飞越动画 | 一系列斜视图 |
| Equal area projection | 等积投影 | 人口密度、土地覆盖、地质、气候区 |
| Conformal projection | 等角投影 | 构造数据、等压线、等温线、风向、洋流；UTM / Transverse Mercator |
| Equidistant projection | 等距投影 | 野火蔓延、火山灰扩散、点源污染扩散 |
| Preserved property | 保留性质 | area / shape / direction / distance |

### 7.2 ArcGIS Pro 工具与界面（保留英文原名）

| 英文原名 | 类别 | 中文说明 |
|---|---|---|
| **ArcGIS Pro** | 软件 | 本课全部 practical 的平台 |
| **Spatial Analyst extension** | 扩展许可 | Area Solar Radiation、Surface Parameters、Con、Raster Calculator 均需要 |
| **Contents pane** | 界面 | 内容窗格，管理图层顺序与勾选 |
| **Geoprocessing pane** | 界面 | 地理处理窗格，搜索与运行工具 |
| **Analysis tab > Geoprocessing group > Tools** | 菜单路径 | 打开 Geoprocessing pane |
| **Environments tab** | 工具面板选项卡 | 设置 Extent、Mask、Cell Size 等环境参数 |
| **Raster Analysis > Mask** | 环境参数 | 限定参与计算/保留的像元范围 |
| **Hillshade** | 工具 | 生成晕渲栅格；默认 Azimuth 315、Altitude 45 |
| **Area Solar Radiation** | 工具 | 面状太阳辐射，输出 Wh/m² |
| **Points Solar Radiation** | 工具 | 📎 同族工具，针对**点位置**而非整幅栅格计算辐射；输入为 DEM ＋ 点要素/坐标表。**本 practical 未使用**，材料也未提及 |
| **Input raster** | 参数 | Area Solar Radiation 的输入 DEM |
| **Output global radiation raster** | 参数 | 总辐射输出栅格（教程命名 `Solar_Rad`） |
| **Latitude** | 参数 | 由输入栅格自动填充，**不要手改** |
| **Time configuration** | 参数 | 设为 **Whole year** |
| **Year** | 参数 | 教程设 2024 |
| **Day interval** | 参数 | 📎 默认 14 天 |
| **Hour interval** | 参数 | 教程设 1（默认 0.5） |
| **Topographic parameters** | 参数分组 | 展开后可见 Calculation directions 等 |
| **Calculation directions** | 参数 | 教程设 16（默认 32，须为 8 的倍数） |
| **Sky size / Resolution** | 参数 | 📎 默认 200，viewshed/skymap 栅格边长 |
| **Zenith divisions** | 参数 | 📎 默认 8，天空半球天顶向分层数 |
| **Azimuth divisions** | 参数 | 📎 默认 8，天空半球方位向分扇数 |
| **Diffuse model type** | 参数 | 📎 默认 UNIFORM_SKY；另有 STANDARD_OVERCAST_SKY |
| **Diffuse proportion** | 参数 | 📎 默认 0.3，散射占总辐射比例（晴空 ~0.2，多云 ~0.7） |
| **Transmittivity** | 参数 | 📎 默认 0.5，大气透射率（0–1） |
| **Z factor** | 参数 | 📎 默认 1，高程单位/平面单位换算系数 |
| **Slope and aspect input type** | 参数 | 📎 默认 FROM_DEM |
| **Raster Calculator** | 工具（Spatial Analyst Tools > Map Algebra） | 教程用于 `"Solar_Rad" / 1000` |
| **Map Algebra expression** | 参数 | 表达式框；图层名需加双引号 |
| **Surface Parameters** | 工具（Spatial Analyst Tools） | 生成 Slope / Aspect 等表面参数 |
| **Input surface raster** | 参数 | Surface Parameters 的输入 |
| **Parameter type** | 参数 | 选 **Slope** 或 **Aspect** |
| **Neighborhood distance** | 参数 | 📎 二次曲面拟合的邻域半径，默认 = 一个像元 |
| **Con (Spatial Analyst)** | 工具 | 条件函数；按条件输出真值/假值栅格 |
| **Input conditional raster** | 参数 | 条件判断依据（本例 `Aspect_DTM`） |
| **Input true raster or constant value** | 参数 | 条件为真时的取值（本例 `solar_rad`） |
| **Input false raster or constant value** | 参数 | 留空 → NoData |
| **Add Clause** | 界面按钮 | Con 表达式中添加子句 |
| **Map view** | 视图 | 分析用视图 |
| **Layout view** | 视图 | 出图用视图，有页面尺寸 |
| **Map frame** | Layout 元素 | 承载地图的矩形容器；图例/比例尺/指北针绑定于此 |
| **Map surrounds** | Layout 元素类别 | Legend / Scale Bar / North Arrow / Chart Frame / Table Frame |
| **Insert tab** | 菜单 | New Layout、Map Frame、Map Surrounds、Grids、Dynamic Text 都在这里 |
| **New Layout** | 菜单项 | 📎 Insert > Project 组 |
| **New Map > New Basemap** | 菜单项 | 新建底图（教程 hint 2） |
| **Legend** | Layout 元素 | |
| **Scale Bar** | Layout 元素 | |
| **North Arrow** | Layout 元素 | |
| **Text** | Layout 元素 | Insert > Graphics and Text |
| **Dynamic text** | Layout 元素 | 自动更新的文本（日期、比例尺、坐标系、Service Layer Credits 等） |
| **Service Layer Credits** | Dynamic text 项 | 教程建议删除以免版面凌乱 |
| **Grids** | Layout 元素 | 选中 Map Frame 后 Insert > Grids |
| **Extent Indicator** | Layout 元素 | 📎 在位置图上标出主图范围；教程未提但 inset 必需 |
| **Activate / Close Activation** | Layout 操作 | 📎 进入/退出 map frame 内部编辑 |
| **Constraint > Fixed Scale** | Map frame 属性 | 📎 锁定比例尺 |
| **Layer transparency** | 图层属性 | 教程设 40%（DTM 叠 hillshade） |
| **Share > Export（Export Layout）** | 菜单 | 导出成图 |
| **Resolution (DPI)** | 导出参数 | 📎 默认 96；报告用 300 |
| **GB Light Grey** | 底图 | 教程主图所用底图 |
| **World Topographic Map** | 底图 | 教程位置图所用底图 |
| **.mpkx（map package）** | 文件格式 | 📎 打包地图与数据的 ArcGIS Pro 格式 |
| **DTM (Digital Terrain Model)** | 数据类型 | **裸地表**高程模型 |
| **DSM (Digital Surface Model)** | 数据类型 | **含地物**（建筑、树冠）的表面模型；本 practical 实际用的是这个 |
| **GeoTIFF** | 文件格式 | `Burnage_DTM_1m` 的格式 |
| **NoData** | 栅格值 | 无值像元；≠ 0 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Practical 8`，§2 Download the data，第 3 段 | "A **DTM** shows the elevation of the ground **and the features on the ground, such as buildings and trees**." | **概念错误。** 这是 **DSM（Digital Surface Model）** 的定义。**DTM（Digital Terrain Model）指裸地表（bare earth）模型，不含建筑与植被。** | 本 practical 的整个分析（屋顶辐射、屋顶坡度坡向）**必须要求栅格包含建筑物**，因此这份数据实为 **DSM**。原 Esri 教程 *Estimate Solar Power Potential* 用的正是 DSM，改编时把名称换成了 DTM 却保留了 DSM 的定义。**§3 中残留的一句 "you can combine hillshade and DSM layer symbolization" 正是这个改编痕迹的证据。** 复习与写报告时请按「含地物的表面模型」理解，术语上称 DSM 更准确。 |
| `Practical 8`，§3 Create a hillshade effect | "For optimum visual effect, you can combine hillshade and **DSM** layer symbolization." | **与上下文不一致。** 该工程中没有名为 DSM 的图层，唯一的高程图层是 `Burnage_DTM_1m`。 | 应为 **DTM**（或按上一条，两处统一为 DSM）。属改编未清理干净。 |
| `Practical 8`，§3 | 先要求命名为 "**HillShade**_DTM_1m"，下一段又写 "the **Hillshade**_DTM_1m layer" | **大小写不一致**（HillShade vs Hillshade） | 不影响功能（file geodatabase 名称不区分大小写），但按后者 `Hillshade_DTM_1m` 统一即可。 |
| `Practical 8`，§5 Map solar energy，Environments 段 | "for **Mask**, choose **Burnage_Local_Buldings**" | **图层名拼写错误**，缺一个 i。同一错误在 §5 出现两次（"You will also use the **Burnage_Local_Buldings** layer as a mask"）。 | 正确为 **`Burnage_Local_Buildings`**。§6.2、§6.3 中拼写正确，可对照。 |
| `Practical 8`，§6 Convert the units | "search for and open **Raster Calculator (Spatial Analysis Tool)**" | **工具箱名称错误。** ArcGIS Pro 中的工具箱名为 **Spatial Analyst Tools**，不是 "Spatial Analysis Tool"。 | 正确路径：**Spatial Analyst Tools > Map Algebra > Raster Calculator**。 |
| `Practical 8`，§6.1 第 1 段 | "The estimated solar power is between about **500-1000 kWh/yr**." | **单位缺失分母。** 该数值描述的是**单位面积**的年入射辐射量。 | 应为 **500–1000 kWh/m²/yr**。同段后文的 "800 kWh/m²" 与 "136 kWh/m²" 单位写法正确，可佐证。 |
| `Practical 8`，§6.1 第 2 段 | "assuming a conversion of 17%, then the estimated potential electricity generation for a rooftop with 800 kWh/m² reduces to 800 × 0.17 = **136 kWh/m²**" | 数值正确，但**省略了时间维**。 | 严格写法为 **136 kWh/m²/yr**（每年）。同段末尾的 625 Wh/m² 也应为 **625 Wh/m²/day**，教程在句中用 "each day" 补足了，但符号里没有。 |
| `Practical 8`，§6.1 准则 1 与 §6.5 Con 表达式 | 准则 1：*"**Note that flat roofs are suitable for solar panels.**"* / §6.5 条件：`VALUE > 22.5 And VALUE < 337.5` | **逻辑矛盾（教程未察觉的实质性缺陷）。** ArcGIS 的 aspect 栅格中，**完全水平的像元被赋值 −1**。−1 不满足 `VALUE > 22.5`，因此**所有平屋顶都被 Con 判为 false 而剔除**，与教程自己声明的准则相反。 | 修正方案（材料未给）：条件改为 `(VALUE = -1) Or (VALUE > 22.5 And VALUE < 337.5)`；或先用 Reclassify/Con 把 −1 重编码为 180（正南）再判断。在报告中主动指出此问题是加分点。 |
| `Practical 8`，§6.5 倒数第 3 段 | "If a cell has a value **less than 22.5 and more than 337.5** degrees then that cell is considered false." | **逻辑连词错误。** 没有任何数值能同时「小于 22.5」**且**「大于 337.5」，按字面读该条件恒为假。 | 应为 **"less than 22.5 **or** more than 337.5"**。教程前文（"slopes that face north have a value less than 22.5 degrees **or** more than 337.5 degrees"）用的正是 or，是本句写反了。 |
| `Practical 8`，§6.4 Remove roofs with high slopes | "Looking at the legend for the `Slope_DTM` raster **there are no slopes steeper than 45 degrees** so we do not need remove any cells..." | **结论存疑，不宜直接采信。** 在 1 m 分辨率的含建筑表面模型上，**建筑边缘（墙面）像元通常会产生远大于 45° 的坡度值**；实际最大值还取决于 `Surface Parameters` 的 Neighborhood distance 设置与 mask 的裁切方式。 | 不作为「材料硬错误」记录，但**务必自行查看 `Slope_DTM` 图例的最大值再决定是否跳过这一步**。若确有 >45° 的像元，应再用一次 `Con`（条件 `VALUE <= 45`）剔除。 |
| `Practical 8`，§7.1 Hints and tips，第 1 条 | "On the **Map Frame group**, **Dynamic text** drop down scroll down the list until you see Service Layer Credits" | **界面位置表述不准确。** ArcGIS Pro 的 **Dynamic Text 库位于 Insert 选项卡的 Graphics and Text 组**；"Map Frame" 是该下拉库**内部的一个分类标题**（Service Layer Credits 列在其下），**不是 ribbon 上的一个组**。 | 正确表述：**Insert 选项卡 → Graphics and Text 组 → Dynamic Text 下拉 → 滚动到 Map Frame 分类 → Service Layer Credits**。 |
| `Practical 8`，§7.1 Hints and tips，第 2 条 | "Click on the **Map layer** and select **New Map > New Basemap**." | **菜单路径不准确。** ArcGIS Pro 中没有叫 "Map layer" 的 ribbon 项。 | 正确路径：**Insert 选项卡 → Project 组 → New Map 下拉 → New Basemap**。 |
| `Practical 8`，末页示例地图（Page 14，OCR 段）图例标题 | "Annual Solar Radiation (**kW/hr/m2**)" | **单位写法错误。** kWh/m²（千瓦时每平方米，能量密度）≠ kW/hr/m²（千瓦每小时每平方米，功率变化率密度），后者是物理上完全不同的量。 | 应为 **kWh/m²**。同图说明文字写的 "in **kilowatt-hours per square meter**" 是正确的，说明是图例标注笔误。此错误来自原件而非 OCR（OCR 不会把 h 改成 /hr）。**本条同时是本周「图例单位」易错点的现成反例。** |
| `Practical 8`，§2 | "Turn the layers off and on in the Contents Pane to **real** their individual content." | 拼写错误。 | 应为 **reveal**。 |
| `Practical 8`，目录与正文多处 | "Introduc**ton**"、"genera**ton**"、"**tps**"（hints and tips）、"**efect**"（hillshade effect）、"**htps**://" | **PDF 文字提取时 "ti"/"tt" 连字（ligature）丢失**，非内容错误。 | 分别应为 Introduction、generation、tips、effect、https://。阅读时自行还原即可。 |
| `Lecture 8 Spatial Visualisation.md`，第 25–37 行 与 第 45–57 行 | `# Map types`（General purpose maps / Thematic maps）一整段**完全重复出现两次** | 原 PPT 中该幻灯片被重复放置（一次作为总览，一次作为分节过渡），转 md 后原样保留。 | 非错误，只是冗余。复习时按一次读即可。 |
| `Lecture 8 Spatial Visualisation.md`，`## OCR 补充` 之 **Page 18（Visual hierarchy）** | "S GUYS" ERRGT. / Be AW? / SEN / oN / < / so / MS" | **低质量 OCR 段：识别结果为纯乱码，零信息量。** 原页面为图片（很可能是一组对比示意图）。 | 该页实质内容**只能从转写还原**——即 2.9 节所述「同一区域三张图、视觉层次不同、强调对象不同」。**切勿把这段乱码当作内容。** |
| `Lecture 8 Spatial Visualisation.md`，`## OCR 补充` 之 **Page 26（Map layout）** 图例 | "[EE **201 - 600**"、"[I **001 - 1200**"、"9 = 1,000 2,000"、"o 12.5 25 50 **Kilomete**" | **低质量 OCR 段：数值与文字被误识。** 同页另一处图例给出的正确序列是 `<=300 / 301-600 / 601-900 / 901-1200 / 1201-1500 / >1500`，可据此校正。 | 应为 **301 - 600**、**901 - 1200**；"9 = 1,000 2,000" 是比例尺刻度的误识；"Kilomete" 应为 **Kilometers**。另外图例前的 `[1]`、`(B`、`HN`、`HE`、`tL]`、`HM`、`Vy` 等全部是**色块图形被误识成字符**，不是文字。 |
| `Lecture 8 Spatial Visualisation.md`，`## OCR 补充` 之 **Page 27 / Page 31** | 仅有标题 "Effective map layout design" / "Stepped statistical surface"，**正文空白** | **低质量 OCR 段：原页为纯图，无可提取内容。** | Page 27 内容见转写（好/坏版面对比，2.11 节）；Page 31 内容见转写（属性值抬升表面，2.13 节）。 |
| `Lecture 8 Spatial Visualisation.md`，讲义正文多处 | `# Cartographic elements`、`# Visual hierarchy`（第二处）、`# Map layout`、`# Effective map layout design`、`# Multivariate mapping`、`# Bivariate choropleth map`、`# 3D perspective view`、`# Stepped statistical surface`、`# Symbolisation: visual variables` 等标题下**无任何正文** | 原幻灯片为整页图片，PDF 文字层只含标题。 | 非错误。但意味着**本周讲义的信息完整度很低，必须以转写为主要学习材料**。 |
| `EART29102 - 23-Mar-transcript.md`，YAML frontmatter | `source: "Sophomore/Hilary Term/EART29102/Lecture/**Week 9**/EART29102 - 23-Mar-transcript.txt"` | **元数据路径错误。** 该文件实际位于 `Lecture/Week 8/`，内容也确为 Week 8 的 Spatial Visualisation 讲座。 | 应为 `Lecture/Week 8/`。属文件转换时的元数据填写错误，不影响内容。 |
| `EART29102 - 23-Mar-transcript.md`，等值线/分层设色段 | "contour map **typography**"、"more idea of what the **typography** or the relief is like" | **自动语音识别（ASR）误写。** | 两处均应为 **topography**（地形）。 |
| `EART29102 - 23-Mar-transcript.md`，视觉层次段 | "**divisional** method uses color shading and pattern to divide up between the classes" | ASR 漏词。讲义原文为 **subdivisional method**。 | 应为 **subdivisional method（细分式）**。同段的 "stereogramic" 亦为 ASR 拼写，讲义作 **stereogrammic**。 |
| `EART29102 - 23-Mar-transcript.md`，2.5D 段 | "we can use that same approach for a two point five D statistical **service** surface" | ASR 误写。 | 应为 **statistical surface（统计面）**，即讲义的 *Stepped statistical surface*。 |
| `EART29102 - 23-Mar-transcript.md`，投影段 | "Conformal map projections like **UTM or Mercator transverse projections**" | 表述不规范（口语）。UTM 本身就是基于 **Transverse Mercator（横轴墨卡托）** 的投影带系统，二者不是并列关系。 | 理解为「如 Transverse Mercator 及以其为基础的 UTM」即可。非实质错误。 |
| `EART29102 - 23-Mar-transcript.md`，比例符号段 | "we've got a value of 10 for a village population... Then the next size up is **10 times larger dot**, which represents 100 people. Then **five times larger dot** gives you 500" | 表述不精确（口语）。规范的比例符号图应使**符号面积**正比于数值（半径 ∝ √value）；若直径按 10 倍放大，面积会放大 100 倍，严重夸大高值。 | 老师此处是在描述图上的视觉印象，不是在给缩放规则。**材料全程未讨论比例符号的面积缩放问题**，此条仅提示不要按字面理解。 |
| `(EART29102) Geospatial Techniques.md`（课程大纲）全篇 | 大纲 Week 8 列为 "Lecture: **Laser Scanning/ Lidar**；Practical: Applied Lidar tomography" | **官方大纲与实际授课内容严重不符**（0a 预处理已核实）。实际 Week 8 为 **Spatial Visualisation ＋ Solar radiation mapping and map layout**。 | 大纲仅可作课程总体背景，**不可用来推断任何一周的内容**。另注意大纲写 "There is **no exam** for this module"，而老师在本次课明确说 Week 11 会讲 **exam format** —— 指的是暑期考试季的 on-line test（大纲评估表中确有此项，占 50%），并非纸笔考试，用词不一致而已。 |
