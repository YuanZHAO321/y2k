# EART29102 Geospatial Techniques — Week 01 学习笔记

> 本周材料：
> - `Lecture/Week 1/Lecture 1 Introduction to GIS.md`（讲义，Course Overview and Introduction）
> - `Practical/Week 1/Practical 1 - Introduction to ArcGISPro.md`（实操教程，ArcGIS Pro 入门）
> - 背景：`(EART29102) Geospatial Techniques.md`（官方课程大纲，仅用于了解学分、考核形式与总体目标）
>
> ⚠️ **重要说明**：本课的**官方大纲与实际授课内容严重不符**。大纲列的是大地测量（Geodesy）、GNSS、摄影测量（Photogrammetry）、卫星遥感、数据库与大数据、Lidar、声呐、无人机；而实际讲义序列是 GIS 导论 → 空间数据与数据管理 → 空间数据输入与操作 → 空间分析 → 空间统计 → 遥感 → 地形分析 → 空间可视化 → 三维地理空间技术 → 课程回顾，全部 practical 基于 ArcGIS Pro。**大纲只能用作课程总体背景，绝不可用来推断任何一周的内容。**

---

## 一、本周主题

### 1.1 这门课要解决什么问题

本周是全课**第一周**，讲义（Lecture 1）本身就是一次课程总览（Course Overview and Introduction）。这门课的核心问题是：

> **地球与环境科学中的观测数据几乎都带有"位置"这一维度。怎样系统地采集、存储、管理、分析、表达这些带位置的数据，并用它们回答科学问题与社会问题？**

讲义给出的课程目标（Course Overview – Aims，共 5 条）：

1. 介绍并发展对**地理空间技术（geospatial techniques）**原理与应用的理解；
2. 展示不同类型的地理空间数据如何被采集（含遥感技术）；
3. 通过真实案例，培养在地球与环境科学中有效处理地理空间数据的能力；
4. 能够用**地理信息系统（Geographical Information System, GIS）**添加、存储、分析、呈现地理空间数据；
5. 熟练使用 GIS 软件 **ArcGIS Pro**。

对应的**预期学习成果（Intended Learning Outcomes, ILOs）**（讲义版，共 5 条）：

| 编号 | 内容 |
|---|---|
| ILO 1 | 理解 GIS 是什么、它是如何构成的 |
| ILO 2 | 定义**空间参照系统（spatial reference systems）**、**基准面（datums）**、**投影（projections）**在记录位置时的作用 |
| ILO 3 | 说明不同尺度的地理空间数据如何帮助解决科学与社会问题 |
| ILO 4 | 为给定的科学问题选择合适的地理空间技术 |
| ILO 5 | 能够使用 ArcGIS Pro 完成地理空间分析与可视化 |

> 📎 背景补充：请注意 ILO 1 和 ILO 5 是**讲义独有**的，官方大纲只列了 4 条 ILO 且没有"ArcGIS Pro 能力"这一条。这再次印证实际授课已经整体改版为一门以 ArcGIS Pro 为主线的 GIS 课。复习时以讲义版 ILO 为准。

### 1.2 考核构成（以讲义为准）

**形成性评价（Formative，不计分但必须做）**
- 每周基于讲义内容的**简答与选择题小测（quizzes）**，对应 ILO 1–3；
- 每周对 ArcGIS Pro 练习与 workshop 的反馈，用于推进 case study，对应 ILO 4–5。

**总结性评价（Summative，计分）**
- **Canvas 测验，50 题**，考查 GIS 在地球与环境应用中的知识与理解，夏季考试期进行，对应 ILO 1、2、3 —— **占 70%**；
- **ArcGIS Pro 软件项目**（选定 case study），展示 ArcGIS Pro 操作能力与空间数据分析能力，**第 11 周末提交（2026 年 4 月 30 日）**，对应 ILO 4、5 —— **占 30%**。

> ⚠️ 官方大纲写的是"Set exercise 50% + Other 50%"，与讲义的 70/30 冲突，见文末勘误表。**以讲义为准。**

**教学方式**：每周 **1 小时 lecture + 2 小时 practical**；lecture 提供理论与背景，practical 做 ArcGIS Pro 实操；辅以在线视频（主要是 ESRI 官方培训视频）与核心教材。

**授课团队**：Ray Burgess（协调人）、Rufus Brunt、Peter Grinrod（Natural History Museum）、Ben Esse（practical 课）。

### 1.3 全课骨架

```
【基础】 W01 GIS 导论（本周）
        W02 空间数据与数据管理
        W03 空间数据输入与操作
【分析】 W04 空间分析
        W05 空间统计
【专题】 W06 遥感
        W07 地形分析
        W08 空间可视化
        W09 三维地理空间技术
【回顾】 W10 课程回顾
```

本周处在骨架最左端：**先建立"GIS 是什么、空间数据长什么样"的框架，并把 ArcGIS Pro 这个工具跑起来**。后面所有周都建立在这两件事之上。

### 1.4 这门课在学位中的定位

> 📎 背景补充（以下为学位层面的定位分析，非讲义原文）：
> - 本课**与大二其余 11 门课几乎不互为前置**，官方前置只有大一的 EART11200（The Natural Scientist's Toolkit）。它自成体系。
> - 它主要服务的是**大三独立项目（independent project）**：地图制作、空间数据处理、地形与遥感分析都是项目阶段的常用技能。
> - 在推荐的大二学习顺序中它排第 11 位（野外课之后）——既因为它独立、不打断依赖链，也因为它是 EART29200 项目课统计与制图技能的自然延伸。
> - 结论：**这门课的价值主要是"技能资产"而非"知识前置"**，学的时候应当以"能不能自己独立做出一张图/一次分析"为标准，而不是以"能不能答对概念题"为唯一标准。

### 1.5 本周两份材料的分工

- **Lecture 1**：课程管理信息 + GIS 概念框架（GIS 定义、功能、空间数据特征、分析功能、图层叠加、矢量/栅格数据模型、ArcGIS Pro 与 ArcGIS Online 简介）。
- **Practical 1**：ArcGIS Pro 完整上手流程（界面 → 新建工程 → 导航 → 加数据 → 看矢量属性表 → 看栅格属性 → 改地图名 → 保存 → Hillshade 地形晕渲 → Contour 等高线矢量化 → 设置地图范围）。**篇幅比讲义还大，是本周的重点。**

---

## 二、核心概念

### 2.1 GIS 的定义（讲义原文式定义，必背）

> **Geographic Information System (GIS)** is a computer-based system for **capture, management, storage, organization and analysis of spatially-referenced data**, and the **output of spatially-referenced information**.

中文：**地理信息系统（GIS）**是一个基于计算机的系统，用于对**具有空间参照（spatially-referenced）**的数据进行**采集、管理、存储、组织与分析**，并**输出具有空间参照的信息**。

关键在于：**GIS ≠ 画地图软件**。地图只是它的一种输出形式。它是"数据 → 信息"的完整链条。

### 2.2 数据 vs 信息（讲义明确区分，考点）

| 术语 | 讲义定义 | 理解 |
|---|---|---|
| **数据（Data）** | a collection of related facts; the basic elements of information（一组相关事实；信息的基本元素） | 原始的、未加工的 |
| **信息（Information）** | data that have been processed to be useful. It provides answers to questions, used in decision-making（经过处理而变得有用的数据；能回答问题、支持决策） | 加工后的、有语境的 |

例：一列井的经纬度是**数据**；"这片区域 80% 的井位于河流 100 m 缓冲区内，存在污染风险"是**信息**。

### 2.3 GIS 做什么（六大功能，讲义 "What does a GIS do?"）

| 功能 | 英文 | 讲义要点 |
|---|---|---|
| 采集数据 | **Capture data** | 从多种来源把数据加入 GIS，也可以从零创建数据 |
| 存储数据 | **Store data** | 以适合应用的方式存储、管理关于真实世界的信息 |
| 查询数据 | **Query data** | 基于**属性（attributes）**或**位置（location）**提出复杂问题并快速得到结果 |
| 分析数据 | **Analyse data** | 整合多个数据集，找出满足特定条件的要素，产出可用于解决问题的信息 |
| 显示数据 | **Display data** | 基于属性来显示要素——讲义称这是"任何 GIS 的强大功能" |
| 呈现数据 | **Present data** | 制作并分发高质量地图、图表、报告，把分析结果有说服力地传达给受众 |

> 记忆法：**Capture → Store → Query → Analyse → Display → Present**，前三步是"数据管理"，中间是"分析"，后两步是"表达"。这条链条正好对应全课骨架（W02–03 管理 → W04–05 分析 → W08 可视化）。

### 2.4 空间数据的特征（Features of spatial data）

讲义给出三点：

1. **空间数据通过坐标系统（coordinate system）建立联系**，坐标系定义**球面（spherical）坐标或平面（planimetric）坐标**、高程（elevation）、方位（orientation）等。
2. 观测与测量是针对**地理上分布的要素**做出的（植物、野生动物、河流等）。每一个这样的**空间对象（spatial object）都是一个实体（entity）**，可以用它的**属性（attribute）或性质（property）**来描述。
3. 属性可以是可观察的和/或可测量的特征。讲义原例：**"树"是观测对象，经纬度（latitude and longitude）定义它的位置，而高程（elevation）、坡向（aspect）、坡度（slope）、太阳辐射（solar radiation）、土壤类型（soil type）等是该位置特有的属性。**

> **核心结构：空间数据 = 几何（在哪里）+ 属性（是什么/多少）。** 这是理解属性表（attribute table）的前提。

讲义还有一页对比（该页无文字层，由 OCR 恢复）：
- **非空间数据（Non-spatial data）**：一张表格，列出澳大利亚 1900 年以来滑坡事件的日期、地点、滑坡类型（debris fall、debris flow、debris slide、rock fall、rock slide、earth flow、soil creep 等）、经度。
- **空间数据（Spatial data）**：同一批记录画在澳大利亚地图上，每个滑坡点位一个符号，附比例尺（0–600 km）与指北针。

> 这张对比图的教学意义：**同一批记录，做成表格只是"数据"，落到地图上就显现出空间格局（滑坡集中在东部沿海山区），变成了"信息"。**

### 2.5 GIS 功能组件（GIS functional components）

讲义此页只有一张编号 1–6 的示意图，**原文未给出各组件的文字说明**（PDF 中该页无可提取文字，OCR 也只恢复了编号）。

> ⚠️ **材料未说明**：六个组件分别是什么，讲义未写。
>
> 📎 背景补充（通用 GIS 教科书的标准划分，仅供理解，**不保证与讲义原图一致，答题时不要当作讲义内容引用**）：常见的 GIS 组件划分是 **Hardware（硬件）/ Software（软件）/ Data（数据）/ People（人）/ Methods 或 Procedures（方法与流程）/ Network（网络）**。另一种划分是按功能流程：**Data input（输入）/ Data storage & management（存储与管理）/ Data manipulation & analysis（操作与分析）/ Data output（输出）**。

### 2.6 空间数据分析组件（Spatial data analysis component）

讲义定义：**一套用于探索环境现象的格局（patterns）、关联（associations）与相互作用（interactions），以及它们随时间和空间变化证据的工具集合。**

讲义列出的分析工具类别（**这是一份"全课分析工具目录"，后面 W04–W07 会逐一展开**）：

- **空间查询（spatial query）**
- **几何量测（geometric measurement）**
- **缓冲区与邻近度量测（buffering and proximity measurement）**
- **叠加分析（overlay analysis）**
- **表面分析（surface analysis）**
- **网络分析（network analysis）**
- **影像分析（image analysis）**
- **空间统计（spatial statistics）**

讲义对其中三类给了详细页：

**（1）缓冲区与邻近度（Buffering and proximity measurement）**
- 定义：计算**围绕某要素的距离（buffer，缓冲区）**和**距某要素的距离（proximity，邻近度）**的函数。
- 讲义原例：在河流周围做 **100 m 缓冲区**，或计算建筑到河流的距离，用于评估**洪水风险（flood risk）**。图中"红色的建筑物位于河流的 100 m 缓冲区内"。

**（2）几何函数（Geometric functions）**
- 计算长度（length）、周长（perimeter）、面积（area）、形状（shape）、方位（orientation）、**质心（centroid）**、距离（distances）等属性。
- 用途：**景观指标（landscape metrics）**、分析**景观破碎化（landscape fragmentation）**、刻画景观结构。
- 图示：左侧"Distance of track（轨迹长度）"，右侧"Perimeter and area（周长与面积）"。

**（3）叠加分析（Overlay analysis functions）**
- 定义：**基于共同的地理位置，把不同主题（themes）的图层堆叠起来。**
- 用途：识别空间关联（如重叠 overlaps），用于**最优选址（optimal site selection）**或**适宜性建模（suitability modelling）**。
- 图示三层从上到下：**Land cover（土地覆被）→ Soil type（土壤类型）→ Base map（底图）**。

### 2.7 GIS 使用数据图层（Layers）

- GIS 常常把来自不同**图层（layers）**的信息组合起来。
- 图层形成一个**堆叠（stack）**，多个数据集共享同一个 x, y, z 位置。
- 讲义案例：**USGS National Map**——提供描述美国及其领地景观的基础地理空间信息，**由 8 个图层组成，比例尺 1:24,000**，有在线 National Map viewer（`https://apps.nationalmap.gov/viewer/`）。

**应用案例：矿产勘查（Mineral deposit exploration）**（Arvanitidis et al 2012）——把以下图层叠在一起找矿：
- 背景地图（Background map）
- 航空像片/卫星影像（Aerial photos / satellite images）
- 环境数据（Environmental data）
- 地质野外数据（Geological field data）
- 地球物理数据（Geophysical data）
- 地球化学数据（Geochemical data）

> 这个例子直接呼应地球科学专业：**GIS 在勘查地质中的价值就是"多源信息在同一空间框架下的叠合"。**

### 2.8 空间数据模型：矢量与栅格（核心考点）

讲义原句：

> 测量景观的空间数据最常见的两种表示方式是使用**离散数据（discrete data）——矢量模型（vector model）**，和**连续数据（continuous data）——栅格模型（raster models）**。

**数据采集方式（讲义明确给出，容易考）**

| 模型 | 采集方式（Data capture） |
|---|---|
| **矢量（Vector）** | 键盘录入（Keyboard entry）、数字化（Digitising）、野外测量（Field surveying）、摄影测量（Photogrammetry）、**LiDAR** |
| **栅格（Raster）** | 遥感（Remote sensing），包括卫星影像（satellite images）与航空像片（aerial photographs） |

**矢量数据模型（Vector data model）**
- 表示**有明确边界与身份（definite boundaries and identities）、具体形状**的要素；
- 三种几何基元：**点（points）、线（lines）、面/多边形（polygons）**；
- 适合存储**边界离散**的数据，讲义原例：**地下水井（groundwater wells，点）、溪流（streams，线）、湖泊（lakes，面）**。

**栅格数据模型（Raster model data）**
- 把地理要素**划分为离散的单元格（cells / pixels）网格**来表示；
- 适合存储**连续变化**的数据，讲义原例：**航空像片、卫星影像、湿度面（surface of humidity）、数字高程模型（Digital Elevation Model, DEM）**。

> 📎 背景补充（讲义只给了"适用场景"，未系统列优缺点；下表为通用 GIS 教科书的标准对比，用于理解与答题时的展开）：
>
> | 维度 | 矢量（Vector） | 栅格（Raster） |
> |---|---|---|
> | 存储结构 | 坐标序列 + 拓扑 + 属性表 | 规则格网，每个像元一个值 |
> | 精度 | 由坐标精度决定，可任意精细 | 由**像元大小（cell size）**决定，有"锯齿" |
> | 边界表达 | 边界清晰锐利 | 边界呈阶梯状 |
> | 文件体积 | 一般较小（要素少时） | 一般较大（随分辨率平方增长） |
> | 属性 | 每个要素可挂**多个字段** | 每个像元通常只有**一个值**（多波段除外） |
> | 擅长的分析 | 网络分析、精确面积/长度量测、拓扑叠加 | 表面分析、邻域分析、代数运算（map algebra） |
> | 典型用途 | 行政边界、道路、井位、地质界线 | DEM、遥感影像、温度/降水面 |

**Raster versus Vector 对比图**：讲义有一页并排展示同一区域的 raster 与 vector 表达（页面无文字层，只有 "Raster  Vector" 两个标签）。

**数字高程模型（DEM）**：讲义引用 ESRI ArcUser 的 mosaic dataset 文章配图，展示 DEM 是最典型的栅格数据产品。这是 W07 地形分析的伏笔，也是本周 practical 里 `elevlidar` 图层的类型。

**空间变换（Spatial transformation）**：讲义有一页标题为 "Spatial transformation"，引用 Yudono (2017)。
> ⚠️ **材料未说明**：该页除标题与文献引用外**无任何文字内容**（PDF 无文字层，OCR 仅识别出标题）。本周不清楚这一页具体讲了什么变换。**留待 W03「空间数据输入与操作」补齐。**

### 2.9 空间参照系统（Spatial reference systems）——本周只是点到

讲义在本周**只用了一句话**触及坐标系：

> "Spatial data are related using a **coordinate system** which defines **spherical or planimetric coordinates**, elevation, orientation etc."

以及 **ILO 2** 提到 spatial reference systems / datums / projections。Practical 中出现了一次实例：`elevlidar` 栅格的 **Spatial Reference** 是 **Customized Transverse Mercator（自定义横轴墨卡托）**，基准面是 **D custom**，并带有 **false easting（东偏移）**、**false northing（北偏移）**等投影参数。

> ⚠️ **材料未说明**：本周讲义**没有**系统讲解 GCS/PCS、datum、投影变形性质。**这部分应当是 W02「Spatial Data and Data Management」的内容。**
>
> 📎 背景补充（以下全部为补充，用于让本周的 practical 看得懂，**不是本周讲义内容**）：
>
> **地理坐标系（Geographic Coordinate System, GCS）**
> - 用**经度（longitude）/ 纬度（latitude）**在**椭球体（ellipsoid / spheroid）**表面定位，单位是**度（degrees）**，不是米。
> - 三要素：**椭球体（spheroid，如 WGS 1984、GRS 1980）+ 基准面（datum，如 WGS 1984、OSGB 1936）+ 本初子午线（prime meridian）**。
> - **基准面（datum）**：把椭球体"摆放"到地球实体上的方式。同一个经纬度在不同 datum 下可能相差**几十到几百米**（例：WGS84 与 OSGB36 在英国相差约 100 m 量级）。
>
> **投影坐标系（Projected Coordinate System, PCS）**
> - 把曲面"摊平"到平面，单位是**米/英尺**，坐标为 **Easting / Northing**。
> - 一定包含一个 GCS 作为基础，再加一组**投影参数**（投影方法、中央经线 central meridian、标准纬线 standard parallel、比例因子 scale factor、**false easting / false northing**）。
> - **false easting / false northing** 的作用：给坐标加一个大常数，保证研究区内坐标不出现负值。
>
> **投影变形性质（本课 ILO 2 直接相关）**
>
> | 性质 | 英文 | 保持什么 | 典型投影 | 适用 |
> |---|---|---|---|---|
> | 等角 | **conformal / orthomorphic** | 局部角度、形状 | Mercator、**Transverse Mercator**、Lambert Conformal Conic | 导航、大比例尺制图、地形图 |
> | 等积 | **equal-area / equivalent** | 面积 | Albers Equal Area Conic、Mollweide | 面积统计、密度制图、土地利用 |
> | 等距 | **equidistant** | 沿特定线的距离 | Azimuthal Equidistant、Equidistant Conic | 距离/缓冲区分析 |
>
> **关键结论：不可能同时保持角度、面积和距离——必须按分析目的选投影。** 做面积统计却用 Mercator，高纬度面积会被严重夸大。
>
> **为什么图层坐标系不一致会出错**
> - ArcGIS Pro 会做 **on-the-fly projection（即时投影）**，把图层临时变换到**地图（Map）的坐标系**下显示，所以*看起来*能对上；
> - 但如果图层缺少坐标系定义（Unknown / undefined coordinate system），或者 datum 不同却没有指定 **geographic transformation（地理变换）**，就会出现**图层错位几十米到几百米**，甚至完全不在一个地方；
> - 更严重的是：**几何计算（面积、长度、缓冲区）是在图层自身或地图的坐标系里做的**，坐标系选错会直接导致数值错误；
> - 因此规矩是：**先确定地图的坐标系 → 再加数据 → 发现 datum 不同就显式设置变换**。

### 2.10 数据的组织层级

讲义只在 ArcGIS Pro 一页给出"工程包含什么"：

> ArcGIS Pro **consists of maps, scenes, layouts, data, tables, and different tools that are structured in a project.**

即 **工程（Project）**是最外层容器，里面有**地图（maps）、场景（scenes，三维）、布局（layouts，出图版面）、数据（data）、表（tables）与工具（tools）**。

Practical 补充了数据侧的两种形态：
- **地理数据库（geodatabase, `.gdb`）**：如 `Prac_1_data.gdb`；
- **Shapefile**：practical 称四个矢量图层是 shapefiles。

> 📎 背景补充（组织层级，讲义未系统讲）：
> ```
> Project (.aprx)                工程文件，记录地图、图层、符号、布局等"设置"
>  ├─ Map / Scene                地图（2D）/ 场景（3D），有自己的坐标系
>  │   └─ Layer                  图层 = 对某个数据源的"引用 + 显示方式"
>  ├─ Layout                     出图版面
>  └─ Toolboxes                  工具箱
>
> File Geodatabase (.gdb)        数据本体（一个文件夹形式的数据库）
>  ├─ Feature Dataset            要素数据集（共享同一坐标系的一组要素类）
>  │   └─ Feature Class          要素类（点/线/面），相当于 gdb 内的"图层数据"
>  ├─ Raster Dataset             栅格数据集
>  └─ Table                      独立属性表
>
> Shapefile (.shp)               旧格式，实际上是一组文件：
>                                .shp（几何）.shx（索引）.dbf（属性）.prj（坐标系）
> ```
> **要点 1：Layer ≠ Data。** 图层只是"指向数据 + 怎么画"的说明；数据本体在 `.gdb` 或 `.shp` 里。
> **要点 2：`.shp` 少了 `.prj` 就没有坐标系；少了 `.dbf` 就没有属性表。** 拷贝数据必须整组一起拷。

### 2.11 比例尺与分辨率

- **比例尺（scale）**：讲义案例 USGS National Map 为 **1:24,000**。Practical 中比例尺显示在地图视图下方的**组合框（combo box）**里，可以下拉选择或直接输入。
- **分辨率（resolution）/ 像元大小（cell size）**：Practical 中 `elevlidar` 的 cell size 是 **6.289 × 6.289 feet**——即一个像元代表地面约 1.92 m × 1.92 m 的方块。

> 📎 背景补充：比例尺分母越大 = 比例尺越小 = 覆盖范围越大、细节越少。栅格的"分辨率"通常指**像元的地面尺寸**，数值越小越精细。矢量数据没有固有分辨率，但有**采集比例尺**——用 1:250,000 采集的地质界线放到 1:5,000 去看，精度是假的。

### 2.12 ArcGIS Pro 与 ArcGIS Online（讲义原文要点）

- **ArcGIS Pro** 是 **Esri** 的高级 GIS 应用程序。
- 工程（project）中结构化地包含 maps、scenes、layouts、data、tables 与各类工具。
- **ArcGIS Online** 是基于云的系统，用于在组织与用户之间**共享 GIS 数据与其他资源**。
- **两者都需要 ESRI 账号**，账号提供更多数据与工具的访问权限。
- **ArcGIS Pro 也可离线运行。**
- ArcGIS Pro 具备 **ArcGIS Desktop（ArcMap、ArcCatalog、ArcToolbox）**的能力，并支持 **Python** 与 **ModelBuilder**。

---

## 三、公式与图表

本周是导论周，**定量内容很少**，讲义没有给出任何公式。下面把关键图表用文字复原，并把 practical 里出现的数值做成可算的定量练习。

### 3.1 矢量数据结构示意（讲义 "Vector data model" 页）

**图的内容**：同一片景观用三种几何基元表达——
- **点（point）**：一个 (x, y) 坐标对。例：地下水井、采样点。图上是一个个孤立符号。
- **线（line / polyline）**：一串有序的 (x, y) 顶点（vertices）连成的折线，有起点、终点，有长度但没有面积。例：溪流、道路。
- **面（polygon）**：一串有序顶点**首尾闭合**围成的区域，有周长和面积。例：湖泊、土地覆被斑块。

**结构上的关键**：每一个点/线/面对应属性表中**一行记录（record）**；几何存在几何字段（Shape）里，属性存在其他字段（fields）里。

### 3.2 栅格数据结构示意（讲义 "Raster model data" 页）

**图的内容**：一张规则的方形网格覆盖在景观上，每个格子（cell / pixel）被填上一个数值或一种颜色。数值代表该格子范围内的属性（高程、反射率、湿度……）。

**结构上的关键**：
- 栅格由**行（rows）× 列（columns）**定义；
- 需要三组信息才能定位：**左上角（或左下角）坐标原点、像元大小（cell size）、行列数**；
- 一个栅格可以有**多个波段（bands）**，遥感影像常见多波段；
- 表达连续面时，边界是"阶梯状"的——这是栅格的固有代价。

### 3.3 Raster versus Vector 对比图（讲义第 23 页）

**图的内容**（该页无文字层，只有 "Raster  Vector" 两个标题）：左右并排展示**同一个地物**（典型是一条河或一块地块）的两种表达。
- 左侧 Raster：河流被"画"成一连串同色的方格，边缘呈锯齿状；放大后能看见像元。
- 右侧 Vector：河流是一条光滑的折线/多边形，放大后边界仍然锐利。

**这张图要记住的一句话**：**同一个现实对象，用不同数据模型表示，得到的精度、体积和可做的分析都不同。选模型 = 选后续分析的可能性。**

### 3.4 分层叠加概念图（讲义 "Overlay analysis" 与 "GIS uses layers of data" 页）

**图的内容**：若干张半透明的平行四边形（代表地图图层）沿垂直方向堆叠，像切片一样错开摆放，每一层标注一个主题。讲义给的三层从上到下是：

```
        ┌──────────────────┐
        │  Land cover      │   土地覆被
        └──────────────────┘
        ┌──────────────────┐
        │  Soil type       │   土壤类型
        └──────────────────┘
        ┌──────────────────┐
        │  Base map        │   底图
        └──────────────────┘
                 ↓
        同一地理位置 (x, y) 在每一层都有一个取值
```

**概念要点**：叠加的前提是**共同的地理位置（common geography）**——也就是说，**所有图层必须能被放进同一个空间参照框架里**。这正是坐标系必须一致的根本原因。USGS National Map 就是这种设计：**8 个图层、1:24,000**。

### 3.5 缓冲区分析示意（讲义 "Buffering" 页）

**图的内容**：一条河流（线要素）两侧各生成一条 **100 m 宽的带状缓冲区**（半透明多边形）；建筑物（点或面）落在缓冲区内的**被显示为红色**，落在外面的保持原色。

**读图逻辑**：`buffer(河流, 100 m)` → 得到一个多边形图层 → 用它与建筑物图层做**空间查询/叠加** → 选出"在缓冲区内的建筑" → 这些就是洪水高风险对象。

### 3.6 投影变形示意

> 📎 背景补充（**讲义本周没有这张图**，此处补充是为了配合 ILO 2 与 practical 中 Transverse Mercator 的出现）：
>
> 想象把格陵兰岛（Greenland，实际面积约 216 万 km²）和非洲（约 3,000 万 km²，是格陵兰的约 14 倍）画在不同投影上：
> - **Mercator（墨卡托，等角圆柱投影）**：格陵兰看起来**和非洲差不多大**——因为面积变形随纬度余弦的平方增长，高纬被严重放大；但**局部形状和角度是正确的**，所以适合航海。
> - **Mollweide 或 Albers（等积投影）**：格陵兰缩回它应有的大小，面积比例正确；但形状被压扁、角度失真。
> - **同一个英国，在 WGS84 经纬度下画出来是"被横向拉长"的**（因为把度当成等长单位用），而在 **British National Grid（Transverse Mercator）**下形状才是正常的。
>
> **口诀：等角保形不保面积，等积保面积不保形状，等距只在特定线上保距离。**

### 3.7 Practical 中的定量信息与推算

Practical 第 7 节给出 `elevlidar` 栅格的参数：

| 参数 | 值 |
|---|---|
| 列数（columns） | 9,989 |
| 行数（rows） | 5,105 |
| 波段数（bands） | 1 |
| 像元大小（cell size / resolution） | 6.289 × 6.289 **feet** |
| 像素类型（pixel type） | **floating point（浮点）** |
| 位深（pixel depth） | **32 Bit** |
| 范围（Extent）单位 | feet |
| 空间参照（Spatial Reference） | Customized Transverse Mercator，datum = D custom |

> 📎 背景补充（以下推算材料未给出，是我据上表算的，用于理解"分辨率—范围—体积"的关系）：
>
> **（1）栅格覆盖的地面范围**
> ```
> 宽 = 列数 × 像元大小 = 9,989 × 6.289 ft ≈ 62,822 ft ≈ 19.1 km
> 高 = 行数 × 像元大小 = 5,105 × 6.289 ft ≈ 32,105 ft ≈  9.8 km
> ```
> 即约 **19 km × 10 km** 的范围（1 ft = 0.3048 m）。
>
> **（2）像元总数与文件体积**
> ```
> 像元总数 = 9,989 × 5,105 = 50,993,845 ≈ 5.1 × 10⁷ 个
> 未压缩体积 = 5.1×10⁷ × 32 bit / 8 = 5.1×10⁷ × 4 byte ≈ 204 MB
> ```
> 这解释了 practical 里那句"**it may take a while to load（加载可能要一会儿）**"。
>
> **（3）分辨率与像元数的平方关系（重要直觉）**
> ```
> 像元数 ∝ 1 / (cell size)²
> ```
> 把像元大小从 6.289 ft 减半到 3.14 ft，像元数变成 **4 倍**，文件体积也变成 4 倍。**"提高一倍分辨率"的代价是四倍存储和四倍计算量。**
>
> **（4）像元大小换算**
> ```
> 6.289 ft × 0.3048 m/ft ≈ 1.92 m
> ```
> 即约 2 m 分辨率的 LiDAR 高程数据——这是很精细的地形数据。
>
> **（5）"浮点型栅格没有属性表"的原因**
> Practical 明确说：pixel type 是 floating point，**意味着属性表打不开**。原因是浮点值是连续的，理论上每个像元的值都可能不同，无法像整型栅格那样按"唯一值 + 计数"建立 **Value Attribute Table (VAT)**。**整型栅格（如土地覆被分类结果）才有属性表。**

### 3.8 比例尺换算

> 📎 背景补充：讲义提到 USGS National Map 为 **1:24,000**。含义是**图上 1 单位 = 地面 24,000 单位**：
> ```
> 图上 1 cm  = 地面 24,000 cm = 240 m
> 图上 1 inch = 地面 24,000 inch = 2,000 ft ≈ 610 m
> ```
> 1:24,000 是美国地形图的经典比例尺（"7.5-minute quadrangle"）。

### 3.9 等高线间隔

Practical Challenge 3 要求生成 **10 ft 间隔**的等高线。

> 📎 背景补充：等高线间隔（contour interval）的选择原则是"地形起伏越大、间隔越大"。10 ft ≈ 3 m，配合约 2 m 分辨率的 LiDAR DEM 是合理的——**间隔不应小于数据本身的高程精度**，否则会画出一堆噪声等高线。

---

## 四、课堂补充

> **本周无 transcript（本课的 lecture transcript 从第 4 周才开始，W04–W10 齐全，W01–W03 没有）。因此本段不包含任何口头讲解内容，全部来自讲义中强调的注意事项与实操教程透露出的规范与评分要点。**

### 4.1 讲义强调的课程管理事项

1. **账号是硬门槛**。Practical 第 1 节写得很清楚：要启动 ArcGIS Pro，**必须持有 name user 授权并拥有 ESRI 账号**。学生账号已经被创建好，每人有登录名和密码——**登录信息见 Lecture 1 讲义（handout）**。第一次启动时要先在浏览器打开 `www.arcgis.com` → **Sign In** → 用登录名密码登录组织 **University of Manchester（Uomanchester）**。
2. **登录组织不只是"能用软件"**。讲义说，登录组织后才能在工程中访问**你自己的内容、群组内容和组织内容**；还可以登录额外的 portal 使用其内容；**要发布（publish）和向组织共享（share），也必须登录。** —— 本周 practical 的数据就是从 **Portal > My Organisation** 拉的，不登录直接卡在第 5 节。
3. **每周都有小测**。形成性评价包含"weekly short answer and multiple-choice quizzes based on lecture content"，讲义末尾也写明**"Take the quiz to test your basic understanding (on BB)"**（Blackboard）。这意味着**讲义内容是逐周被检查的**，不能积压。
4. **30% 的分数来自一个持续积累的 ArcGIS Pro 项目**。讲义写"Weekly feedback on ArcGIS Pro examples and workshops **to support progress of case studies**"——即每周的 practical 不是孤立练习，而是在为**第 11 周（2026 年 4 月 30 日）提交的 case study 项目**积累素材和技能。**从第一周开始就应该有意识地保存好每次 practical 的工程。**
5. **70% 的分数是夏季考试期的 Canvas 50 题测验**，考 ILO 1、2、3——即**概念、坐标系、应用场景**，不考软件操作。所以讲义部分的概念不能只"看懂"，要能在选择题层面区分（例如 vector vs raster 各自适合什么）。

### 4.2 讲义指定的课后任务与资源

- **读教材第 1 章：Overview**（核心教材，practical 注明基于 Bajjali, W. (2023). *Introduction to ArcGIS Pro*. In: *ArcGIS Pro and ArcGIS Online*, Springer Textbooks in Earth Sciences, Geography and Environment）。
- **完成 Blackboard 上的 quiz。**
- **ESRI training "GIS Basics"（只做 components 1–3，约 55 分钟）**。
- 浏览 **Geo-Wiki**（`https://www.geo-wiki.org/`）与 **OpenStreetMap**（`https://www.openstreetmap.org/`）。
- Practical 末尾另指定一段 ESRI 视频：**"ArcGIS Online Basics"**（`https://www.esri.com/training/catalog/5d816c0255cf937306d2d3ef/arcgis-online-basics/`）。

### 4.3 实操教程透露的操作规范

1. **定期保存是被明文写进教程的规范**："It is a good practice to save your changes periodically while you work."（第 9 节）。教程还给了三种保存方式（Quick Access toolbar 的 Save 按钮、Project tab > Save、`Ctrl + S`）。
2. **右键是 ArcGIS Pro 的主要交互入口**。教程反复强调 **context menu（上下文菜单，也叫 contextual / shortcut / pop-up menu）**——移除图层、打开属性表、打开 Properties、Zoom to Layer、Add To Current Map 全都是右键出来的。**遇到"找不到某功能"时，先在图层名上右键。**
3. **图层的可见性与绘制顺序是两件事**。取消勾选 = 图层不可见但仍在工程里；**在 Contents pane 里上下拖动 = 改变绘制顺序（drawing order）**，上面的盖住下面的。
4. **教程刻意留了 4 个 Challenge 让你自己找菜单**——这是设计好的"学会自己探索软件"的训练：
   - Challenge 1：看 NewtonCreek 和 MurphyOil 的属性表，判断各自存的是什么几何类型；
   - Challenge 2：给采样点加**标注（labels）**；
   - Challenge 3：在工具箱里找到 **Contour** 工具，生成 10 ft 间隔等高线；
   - Challenge 4：给等高线标注高程值。
   > 📎 背景补充：这四题的做法见下一节 5.7 与 5.11（**这些具体步骤教程没有写，是我补充的**）。

---

## 五、Practical 要点

> **本段是本周笔记的重心。目标：不打开原教程，也能在 ArcGIS Pro 里从头到尾重做一遍。**
> 教程出处：Bajjali, W. (2023), *Introduction to ArcGIS Pro*, Springer。
> **凡是教程原文没有的步骤/参数，一律用 📎 标出。**

### 5.0 本次 practical 的学习目标（教程原文）

- 理解 ArcGIS Pro 基于 **ribbon** 的界面布局与基本工具；
- 添加数据、制作地图；
- 知道**矢量与栅格数据结构的区别**；
- 对数据应用一些**地理处理（geoprocessing）**工具，创建 **hillshade（山体阴影/晕渲）**与 **contour（等高线）**图层。

> ⚠️ 教程原文写的是"apply some geoprocessing tools to **vector data** to create hillshade and contour layers"——**这是错的**，hillshade 和 contour 都是作用在**栅格**（`elevlidar`）上的。见文末勘误表。

### 5.1 启动与登录（教程第 1 节）

1. 前提：拥有 **name user 授权**与 **ESRI 账号**（学生账号已创建，登录信息在 Lecture 1 讲义里）。
2. 首次使用：在浏览器打开 `www.arcgis.com` → 点 **Sign In** → 输入登录名与密码 → 登录组织 **University of Manchester (Uomanchester)**。
3. 登录后才能：访问个人内容 / 群组内容 / 组织内容；登录额外 portal；**发布并向组织共享**。

### 5.2 新建工程与界面结构（教程第 2 节）★重点

**操作**：启动 ArcGIS Pro，用账号登录 → 在 **New Project** 下点 **Map**。

> 📎 背景补充：`Map` 是一个工程模板（template），会自动创建一个二维地图并附带默认底图。其他常见模板有 `Catalog`（只管理数据）、`Global Scene` / `Local Scene`（三维场景）、`Map` 之外还有 `Start without a template`。**教程只让点 Map。**

**界面由三部分组成（教程原文编号）**：

| # | 名称 | 位置 | 说明（教程原文要点） |
|---|---|---|---|
| 1 | **Ribbon（功能区）** | 顶部 | 把功能组织成一系列**选项卡（tabs）**。**核心选项卡（core tabs）始终存在**；**上下文选项卡（contextual tabs）只在应用处于特定状态时出现**（例如选中某个图层时才出现 Feature Layer 相关的 tab）。 |
| 2 | **Views（视图）** | 中间 | **Map view** 是显示地图的窗口。每个 view 都有一个标签（tab），可用来关闭 view 或拖到别的位置。一个工程可以有多个 view，按需打开关闭。**当前活动 view 的标签是蓝色的。** |
| 3 | **Panes（窗格）** | 两侧 | 都是**可停靠窗口（dockable windows）**。教程列出三个：**Contents pane（左）、Map view（中）、Catalog pane（右）**。 |

> ⚠️ 教程这一段的术语有混乱：它把 **Map view** 说成"第二个 pane"，又把标题写成 "Catalog View"，还说 "Catalog View is in the middle of the program"。**Map view 是 view 不是 pane；中间的是 Map view 不是 Catalog View。** 见勘误表。

**实际记忆版（正确的界面地图）**：

```
┌─────────────────────────────────────────────────────────────┐
│  Ribbon:  Project | Map | Insert | Analysis | View | Edit |  │
│           Imagery | Share    (+ 上下文选项卡)                 │
├──────────────┬────────────────────────────┬─────────────────┤
│ Contents     │                            │ Catalog pane    │
│ pane（左）    │      Map view（中）         │ （右）           │
│              │                            │                 │
│ 图层列表      │  World Topographic Map     │ Project /       │
│ 勾选=可见     │  World Hillshade           │ Portal /        │
│ 拖动=改顺序   │                            │ Favorites       │
├──────────────┴────────────────────────────┴─────────────────┤
│  比例尺（Scale 组合框）      光标坐标（Coordinates）           │
└─────────────────────────────────────────────────────────────┘
```

**默认底图（教程明确点名）**：
- **World Topographic Map** —— 教程称之为 **basemap（底图）**，"作为你工作的背景使用的参考地图"。后面几周会用不同类型的底图。
- **World Hillshade** —— 来自 ESRI **Living Atlas** 的高程（晕渲）地图。

**Catalog pane 的标签页**（教程截图与正文提到）：**Project / Portal / Favorites**；Project 下包含 **Maps、Databases、Styles、Folders、Locators** 等节点。

> 教程原文提示：Catalog pane 也用来显示"与某一功能区域相关的命令和设置，例如 **Symbology** 和 **Geoprocessing** 窗格"——这两个窗格在后面几周会大量使用。

### 5.3 导航：Map tab 的 Navigate 组（教程第 3 节）

**路径**：`Map` tab（ribbon）→ **Navigate** 组。

教程列出的工具（英文原名必须记）：

| 工具 | 作用 |
|---|---|
| **Explore** | **地图与场景的默认工具**。用于移动（pan）、通过弹出窗口（pop-up）识别要素属性、缩放 |
| **Full Extent** | 缩放到全图范围 |
| **Fixed Zoom In** | 固定倍率放大 |
| **Fixed Zoom Out** | 固定倍率缩小 |
| **Previous Extent** | 回到上一个视图范围 |
| **Bookmarks** | 书签（保存视图位置） |
| **Go To XY** | 跳转到指定坐标 |

**鼠标操作（教程原文）**：
- **平移（Pan）**：在地图上点击任意位置并拖动。平移时指针变成**手形**。
- **缩放（Zoom In/Out）**：**滚动鼠标滚轮**，围绕光标位置放大/缩小。
- **按住右键拖动**上下移动也可缩放；**点右键时指针变成放大镜**。
- **框选放大（Zoom In）**：按住键盘 **Shift** 并在地图上**拖出一个矩形**，缩放到该矩形。
- **回到上一范围**：在地图上**右键 → "Previous Extent"**。

### 5.4 比例尺与坐标显示（教程第 4 节）

- **比例尺（Scale）**：显示在**地图视图下方的组合框（combo box）**里。组合框允许从下拉列表中选择，**也可以直接输入一个比例尺**来控制显示。
- **坐标（Coordinates）**：**光标当前位置的坐标显示在窗口底部**，随鼠标移动实时更新。
- 讲义截图中底部显示的是形如 `109.4632905°E  80.5947417°N` 的经纬度，右侧还有 `Selected Features 0` 的计数。

> 📎 背景补充：底部显示的坐标使用的是**当前地图的坐标系**——如果地图是投影坐标系，这里会显示米/英尺形式的 Easting/Northing 而不是经纬度。这是判断"当前地图坐标系是什么"的一个快速办法。

### 5.5 加载与移除数据（教程第 5 节）★重点

教程给了**两种加载方式**：

**方式 A —— Add Data 按钮**
```
Map tab（toolbar）→ Add Data 按钮的下拉箭头 → Add Data to map
  → 导航到 Portal > My Organisation
  → 在搜索框搜 Prac_1_data.gdb
  → 点 OK
```

**方式 B —— 从 Catalog（教程称为 ArcCatalog）拖放**

教程描述：ArcCatalog 窗口以**目录树（catalogue tree）**的形式显示存放空间数据的文件夹与子文件夹内容。可以在目录树中导航到目标数据集，然后**把数据集拖放（drag and drop）到 table of contents 中列出的 data frame 里**。

本次具体操作：
```
Catalog pane → Portal 标签 → My Organization
  → 搜索框输入 elevlidar
  → 右键 → Add To Current Map
  （教程提示：it may take a while to load，加载需要一会儿）
```

> ⚠️ 教程这里用的是 ArcMap 时代的旧术语（**ArcCatalog**、**data frame**、**table of contents**）。ArcGIS Pro 里对应的是 **Catalog pane / Catalog view**、**Map**、**Contents pane**。见勘误表。

**加载后的行为（教程原文）**：
- 数据集被放在 **Contents pane 中图层列表的最顶端**；
- 它左边的**复选框默认是勾选的**；**取消勾选 → 该图层在地图视图中不可见**；
- **图层的绘制顺序（drawing order）可以通过在 Contents pane 中选中并上下拖动图层来改变**。

**移除图层**：
```
在 Contents pane 中右键图层名 → 弹出 context menu → 选择 Remove
```
图层随即从 Contents pane 和地图视图中移除。

> 📎 背景补充：**Remove 只是把图层从地图里拿掉，不会删除硬盘上的数据。** 真正删除数据要在 Catalog pane 里对数据源右键 **Delete**。这个区分很重要——见第六节易错点。

### 5.6 矢量数据探索（教程第 6 节）★重点

**场景**：把 `elevlidar` 图层**取消勾选**后，地图视图显示的是美国**威斯康星州 Superior 市的 Newton Creek** 一带，包含四个图层：

| 图层名（原文拼写） | 内容 |
|---|---|
| **SamplingSite** | 5 个水质采样点 |
| **NewtonCreek** | Newton Creek 河道 |
| **MurphyOil** | Murphy Oil Inc. 厂区 |
| **HogIsland** | Hog Island |

教程说明：这些图层是不同类型的**矢量（vector）**数据，形式为 **shapefiles**；它们可以被**分类（classified）与符号化（symbolized）**成不同的符号。地图显示 **Newton Creek 起自 Murphy Oil Inc.，排入 Hog Island；沿途设 5 个采样点监测水质。**

> ⚠️ 教程一方面说数据来自 `Prac_1_data.gdb`（**地理数据库**），另一方面说这些图层是 **shapefiles**——两者是不同的数据格式，不可能同时成立。见勘误表。

**打开属性表**：
```
在 Contents pane 中右键 SamplingSite 图层 → 选择 Attribute Table
```
一个新窗格在 **Map View 下方**打开，显示该图层的**属性（attributes）**表。

**属性表的结构（必背术语）**：

| 术语 | 中文 | 教程定义 |
|---|---|---|
| **Record** | 记录 | **表的行**。每条记录代表某个特定位置独有的信息 |
| **Field** | 字段 | **表的列**。字段定义属性表中的信息类型 |

`SamplingSite` 的字段包括：
- **FID**：该记录的**唯一标识符（unique identifier）**；
- **矢量数据类型**：point（点）；
- **站点名称**：1, 2, 3…；
- **位置**：纬度与经度（latitude and longitude）；
- **水样测量数据**：
  - **EC** = electrical conductivity（电导率）
  - **pH**
  - **T** = temperature（温度）
  - **DO** = 教程写作 "dissolved organic carbon"

> ⚠️ **DO 通常是 dissolved oxygen（溶解氧）**；dissolved organic carbon 的缩写是 **DOC**。教程此处术语有误，见勘误表。

**用 Explore 工具查属性（等价方法）**：教程指出，**直接用 Explore 工具点击地图上任意一个形状要素**，弹出的 pop-up 框会显示该要素在属性表中的信息（教程举例点击 site 2）。

**Challenge 1**：打开 `NewtonCreek` 和 `MurphyOil` 的属性表，判断各自存的是什么形状数据。
> 📎 背景补充（教程未给答案）：按地理常识，**NewtonCreek 是线（polyline）**，**MurphyOil（厂区）与 HogIsland 是面（polygon）**，**SamplingSite 是点（point）**。在属性表里看 **Shape 字段**的值，或在 Layer Properties > Source 中看 **Geometry Type / Feature Type** 即可确认。

**Challenge 2**：给沿 Newton Creek 的采样点添加**标注（labels）**。
> 📎 背景补充（教程未给步骤，以下是我补充的做法）：
> ```
> 方法一：在 Contents pane 中选中 SamplingSite 图层 →
>         ribbon 出现上下文选项卡 Feature Layer →
>         Labeling tab → 在 Label Class 组的 Field 下拉框选择要显示的字段（如站点名称）→
>         点 Labeling tab 最左侧的 Label 按钮打开标注
> 方法二：在 Contents pane 中右键图层 → 勾选 Label
> 字体、大小、颜色在 Labeling tab 的 Text Symbol 组中调整。
> ```

**符号系统（Symbology）**
> ⚠️ **教程只说这些图层"可以被分类和符号化"，没有给任何调整符号的步骤。**
>
> 📎 背景补充（以下步骤教程未写，是我补充的，供后面几周使用）：
> ```
> 在 Contents pane 中右键图层 → Symbology  （或：选中图层 → Feature Layer tab → Symbology）
>   → 右侧打开 Symbology pane
>   → Primary symbology 下拉框可选：
>        Single Symbol      单一符号（全部一个样式）
>        Unique Values      唯一值（按分类字段给不同颜色）
>        Graduated Colors   分级色彩（按数值字段分级填色，需选 Field + Method + Classes）
>        Graduated Symbols  分级符号（按数值改变符号大小）
>   → 点符号色块进入 Format Point/Line/Polygon Symbol，调 Color / Size / Outline
>   → 点 Apply
> 栅格图层的 Symbology pane 则提供 Stretch / Classify / Unique Values / Discrete 等方案，
> 并可选 Color scheme（色带）。
> ```

### 5.7 栅格数据探索（教程第 7 节）★重点

**操作**：把栅格文件 **`elevlidar`** 加入地图（重新勾选或按 5.5 方式 B 加载），会新增一个含高程数据的图层。

**查看栅格属性**：
```
Contents pane → 右键 "elevlidar" → Properties → Source 选项卡
```

**Source 选项卡包含六个小节（教程逐一说明）**：

| 小节 | 内容（教程原文） |
|---|---|
| **Data Source** | 显示 `elevlidar` 栅格的**存储位置** |
| **Raster Information** | **9989 列 × 5105 行**；**1 个波段（band）**；**cell size（分辨率）= 6.289 × 6.289 feet**；**pixel type = floating point（浮点）**，这意味着**属性表打不开**；**pixel depth = 32 Bit** |
| **Band Metadata** | 显示关于该栅格的（波段）信息 |
| **Statistics** | 显示栅格高程的**最小值、最大值、平均值、标准差** |
| **Extent** | 显示以 **feet** 为单位的坐标范围 |
| **Spatial Reference** | 坐标系为 **Customized Transverse Mercator**，基准面（datum）为 **D custom**；并给出投影参数，如 **false easting** 与 **false northing** |

探索完后点 **OK** 关闭。

> 📎 背景补充：这一步其实是全课**第一次接触坐标系实例**。要注意两件事：（1）这个栅格用的是**英尺**为单位的投影坐标系，而底图（World Topographic Map）用的是 Web Mercator——**两者单位、坐标系都不同，却能叠在一起显示，靠的就是 ArcGIS Pro 的 on-the-fly projection**；（2）`D custom` 说明数据作者自定义了基准面，这类数据与标准 datum 数据叠加时**尤其容易出现几十米级的偏移**。

### 5.8 修改地图名称（教程第 8 节）

```
Contents pane → 右键 "Map" → Properties → 把名称改为 Superior → OK
```
（教程原文把 Properties 误拼作 "Propertie s"，见勘误表。）

> 📎 背景补充：**Map Properties 对话框里除了 General 选项卡（改名）之外，还有 Coordinate Systems 选项卡——这就是设置地图坐标系的地方**（`Map Properties > Coordinate Systems`，可搜索坐标系名或 WKID/EPSG 代码，也可"从图层继承"）。教程本周没有让你改坐标系，但这是必须记住的路径。

### 5.9 保存工程（教程第 9 节）

教程原文规范："**It is a good practice to save your changes periodically while you work.**"

三种保存方式：
1. 点击应用顶部 **Quick Access toolbar（快速访问工具栏）**上的 **Save** 按钮；
2. 点 ribbon 上的 **Project** 选项卡 → **Save**；
3. 按 **Ctrl + S**。

### 5.10 生成山体阴影（Hillshade）（教程第 10 节）★核心操作

**问题**：栅格图层虽然含高程数据，但**很难看出地形起伏（hard to visualise the relief）**。解决办法是通过地理处理生成一个 **hillshade** 图层。

**完整操作路径**：
```
Analysis（ribbon 选项卡）> Tools
   → 打开 Geoprocessing pane（地理处理窗格）
   → 在搜索框输入 hillshade
   → 选择 Hillshade (3D Analyst Tools)
   → Hillshade 对话框在 Geoprocessing pane 中打开
   → 把 Contents pane 中的 elevlidar 图层【拖放】到 Input raster 框
   → 其余参数全部接受默认值（包括默认的输出栅格名称 output raster name）
   → 点 Run
```

**Hillshade 的原理（教程原文）**：
> Hillshade 函数产生地形表面的**灰度三维表现（grayscale 3D representation）**，在为影像着色时考虑了**太阳的相对位置**。Hillshading 是一种通过**光源**以及高程表面的**坡度（slope）与坡向（aspect）**来可视化地形的技术。

> 📎 背景补充（**以下默认参数教程没有写出来**，但"接受默认值"时实际用的就是这些，知道它们才能理解结果）：
> | 参数 | 默认值 | 含义 |
> |---|---|---|
> | **Azimuth** | **315°** | 光源方位角。315° = 西北方向照射——这是制图学惯例，因为人眼默认"光从左上来"，用其他方向容易产生**地形反转错觉（relief inversion）**，山谷看起来像山脊 |
> | **Altitude** | **45°** | 光源高度角（地平线以上） |
> | **Model shadows** | 不勾选 | 勾选后计算真实投影阴影，速度慢很多 |
> | **Z factor** | **1** | 垂直方向的换算系数。**当高程单位与平面坐标单位一致时才用 1** |
>
> ⚠️ 关于 **Z factor** 的一个真实陷阱：本例中平面单位是 **feet**，高程单位大概率也是 feet，所以 Z factor = 1 正确。但**如果平面单位是度（经纬度），高程单位是米，Z factor 必须换算**（约 1/111,320，且随纬度变化），否则晕渲会夸张到完全失真。教程未提及此点。
>
> 另：**Hillshade 工具在 3D Analyst Tools 和 Spatial Analyst Tools 两个工具箱里都有**，功能相同；教程指定的是 **3D Analyst Tools** 版本。这两个工具箱都需要相应的 **extension license（扩展许可）**。

**结果**：一个灰度的地形晕渲图层，地形起伏立刻变得直观。

### 5.11 栅格转等高线（矢量化）（教程第 11 节）★核心操作

教程说明：**Contour 工具**是另一个有用的地理处理函数，用于**按指定间隔生成等高线（contour lines）**。

**Challenge 3**：在 Toolbox 中搜索 **contour** 函数，生成 **10 ft 间隔**的等高线图层。

> 📎 背景补充（**教程只给了 challenge，没给步骤和参数**，以下为我补充的完整做法）：
> ```
> Analysis > Tools → Geoprocessing pane 搜索框输入 contour
>   → 选择 Contour (3D Analyst Tools)   ← 与 Hillshade 同一工具箱
>   → 参数：
>       Input raster              : elevlidar        （注意：输入是原始 DEM，不是 hillshade！）
>       Output polyline features  : 接受默认或自定义名称
>       Contour interval          : 10               （单位跟随栅格的 Z 单位，本例为 feet）
>       Base contour              : 0（默认）         起算高程
>       Z factor                  : 1（默认）
>       Contour type              : CONTOUR（默认）
>   → Run
> ```
> ⚠️ **最容易犯的错：把 hillshade 图层当成 Input raster。** Hillshade 的像元值是 0–255 的灰度亮度，不是高程；对它做 Contour 会得到一堆毫无意义的"等亮度线"。**Contour 的输入必须是原始高程栅格 `elevlidar`。**

**Challenge 4**：给等高线标注高程值。
> 📎 背景补充（教程未给步骤）：与 5.6 的 Challenge 2 同理——选中等高线图层 → **Feature Layer > Labeling tab** → **Field** 选择等高线的高程字段（通常名为 **Contour**）→ 打开 **Label**。可在 Labeling tab 中把标注放置方式设为沿线放置。

**这一步的概念意义**：这是本课第一次**跨数据模型的转换**——**栅格（raster，连续面）→ 矢量（vector，线要素）**，教程称之为**矢量化（vectorisation）**。反方向的操作叫**栅格化（rasterisation）**。

### 5.12 设置地图范围（Set Map Extent）（教程第 12 节）

**概念（教程原文）**：地图范围（map extent）由一组坐标定义，勾勒出工程中地图或场景所覆盖的区域。**默认情况下，extent 是地图/场景中所有图层的所有要素所覆盖的空间范围——这是一个动态范围（dynamic extent），会随数据的增删自动更新。** GIS 用户可以设置**自定义地图范围（custom map extent）**。

**完整操作序列**：
```
① Map tab > Navigate 组 > 点 Full Extent 按钮
       → 地图缩放到整个世界（因为底图是全球范围的）

② 在 Contents pane 中选中 SamplingSite 图层 → 右键 → Zoom to Layer
       → 缩放到采样点所在区域

③ 手动缩放、平移，把地图调到教程截图所示的视图与比例尺

④ Contents pane → 右键 Superior 地图 → Properties
       → 打开 Map Properties 对话框
       → Extent 选项卡
       → 勾选 Use a custom extent
       → 在 Get extent from 下方选择 Current visible extent
         （由此生成范围坐标）
       → OK 关闭对话框

⑤ 再次点击 Full Extent 按钮
       → Superior 地图现在缩放到【自定义范围】，而不再是全世界

⑥ 保存工程（Ctrl + S）
```

> 📎 背景补充：设置自定义 extent 的实际用处是——**做完项目后，每次打开工程或点 Full Extent，都直接回到研究区，而不是被全球底图带到世界地图去。** 这在最后 30% 的 case study 项目里会很有用。

### 5.13 一页速查：本次 practical 的完整流水线

```
1.  浏览器登录 www.arcgis.com（Uomanchester）
2.  启动 ArcGIS Pro，登录
3.  New Project > Map
4.  认界面：Ribbon / Map view / Contents pane / Catalog pane
5.  Map tab > Add Data > Add Data to map > Portal > My Organisation
       > 搜 Prac_1_data.gdb > OK
6.  Catalog pane > Portal > My Organization > 搜 elevlidar
       > 右键 > Add To Current Map
7.  取消勾选 elevlidar，观察四个矢量图层
8.  右键 SamplingSite > Attribute Table，认 Record / Field / FID / EC / pH / T / DO
9.  Explore 工具点击要素，看 pop-up
10. [Challenge 1] 看 NewtonCreek / MurphyOil 的几何类型
11. [Challenge 2] Feature Layer > Labeling > Field > Label   📎
12. 勾选 elevlidar，右键 > Properties > Source，读六节信息
       （9989×5105，1 band，6.289 ft，float32，Transverse Mercator）
13. 右键 Map > Properties > 改名 Superior > OK
14. Ctrl + S 保存
15. Analysis > Tools > 搜 hillshade > Hillshade (3D Analyst Tools)
       > Input raster ← 拖入 elevlidar > 默认 > Run
16. [Challenge 3] Analysis > Tools > 搜 contour > Contour (3D Analyst Tools)
       > Input raster = elevlidar（不是 hillshade！）> Contour interval = 10 > Run   📎
17. [Challenge 4] 给等高线加高程标注   📎
18. Map tab > Navigate > Full Extent（看到全世界）
19. 右键 SamplingSite > Zoom to Layer，调整到目标视图
20. 右键 Superior > Properties > Extent > Use a custom extent
       > Get extent from: Current visible extent > OK
21. 再点 Full Extent 验证
22. Ctrl + S 保存
```

---

## 六、易错点 / 重点难点

### 6.1 概念层面

**（1）"GIS = 画地图"是最常见的误解**
讲义的定义强调 **capture / management / storage / organization / analysis** 全链条，地图只是 **output**。Canvas 测验很可能考"以下哪个**不是** GIS 的功能"这类题。**记住六动词：Capture, Store, Query, Analyse, Display, Present。**

**（2）Data 与 Information 混用**
讲义明确区分：Data 是"相关事实的集合、信息的基本元素"；Information 是"经过处理而变得有用的数据，能回答问题、支持决策"。**别把两个词当同义词写。**

**（3）矢量/栅格与离散/连续的对应关系记反**
```
矢量 Vector  ←→  离散 discrete   ←→  点/线/面   ←→  井、河、湖、边界
栅格 Raster  ←→  连续 continuous ←→  格网像元   ←→  DEM、影像、湿度面
```
另外**采集方式也是考点**：Photogrammetry 和 **LiDAR 被讲义归在 vector data capture 一侧**（因为直接产出点/线要素），而 **remote sensing（卫星影像、航空像片）归在 raster 一侧**。这一分类有一定的主观性，但**答题按讲义来**。

**（4）栅格"分辨率"不等于"精度"**
6.289 ft 的像元大小说明了**采样间隔**，不代表高程值本身准到这个量级。而且分辨率提高一倍，数据量变 4 倍（∝ 1/cell size²）。

**（5）浮点栅格没有属性表**
教程明确写了 "pixel type is a floating point, meaning that the attribute table cannot be opened"。**只有整型栅格才有 Value Attribute Table。** 这条容易被当成"软件坏了"。

### 6.2 坐标系相关（最容易出错，也是 ILO 2 的直接考点）

**（6）图层坐标系与地图坐标系不一致导致对不上**
- ArcGIS Pro 的 **on-the-fly projection** 会让不同坐标系的图层"看起来"能叠在一起，于是**问题被隐藏**；
- 但如果图层**缺少坐标系定义（Unknown coordinate system）**，软件无法即时投影，图层可能跑到世界另一端或干脆不显示；
- 如果两个图层用**不同的 datum**（例如本 practical 的 `D custom` vs WGS 1984），而没有指定 **geographic transformation**，会出现**系统性偏移**（几十到几百米）——地图看起来"差不多对"，但空间叠加分析的结果是错的；
- **诊断方法**：`Layer Properties > Source > Spatial Reference` 逐层核对；`Map Properties > Coordinate Systems` 看地图的坐标系；出现变换警告时点开 **Transformation** 对话框显式选择。

**（7）单位混淆**
本 practical 的栅格用 **feet**，Contour interval 填 `10` 意思是 **10 英尺**不是 10 米。**任何"距离/间隔/缓冲半径"参数都必须先确认坐标系的线性单位。**

**（8）Z factor 陷阱**
平面单位与高程单位不一致时（典型：地理坐标系 + 米制高程），Hillshade / Slope / Contour 的 **Z factor 必须换算**，否则结果荒谬。教程本周用默认值 1 是因为两者都是 feet。

### 6.3 工程与数据的关系（本课最经常"翻车"的地方）

**（9）把 Project 文件当成数据文件**
- `.aprx` **只保存"设置"**：有哪些地图、哪些图层、图层指向哪个数据源、符号怎么配、范围是多少；
- **数据本体在 `.gdb` / `.shp` / 影像文件里，不在 `.aprx` 里**；
- 后果：把 `.aprx` 单独拷到 U 盘或换台机器打开，图层名旁边出现**红色感叹号（!）= broken link（断链）**；
- **修复**：在 Contents pane 中点红色感叹号，或 `Layer Properties > Source > Set Data Source`，重新指向数据；
- **预防**：把数据全部放进工程默认的 **File Geodatabase**（新建工程时自动创建的 `<项目名>.gdb`），或用 **Project tab > Share > Package > Project Package (.ppkx)** 打包分发。
- 📎 背景补充：以上断链诊断与修复路径教程未写，是我补充的；但这是提交 30% case study 项目时**几乎一定会遇到**的问题。

**（10）Remove 与 Delete 混淆**
- Contents pane 里右键 **Remove** = 把图层从地图移走，**数据还在**；
- Catalog pane 里右键数据源 **Delete** = **真的删掉硬盘上的数据**，且不可撤销。

**（11）图层不可见的两种原因分不清**
- **复选框没勾** → 图层隐藏；
- **绘制顺序（drawing order）被压在下面** → 图层被上面不透明的图层完全遮住（例如底图或 hillshade 盖住了矢量层）。
  解决：在 Contents pane 中**拖动图层调整顺序**（矢量要素通常应放在栅格之上），或调整图层透明度（`Appearance tab > Transparency`）📎。

**（12）Geoprocessing 输出去了哪里**
接受"默认输出名称"时，结果被写进**当前工程的默认地理数据库**里。如果不知道这一点，后面找不到 hillshade / contour 结果文件。**Run 之后在 Geoprocessing 的历史记录或 Catalog pane > Databases 下确认输出位置。** 📎

### 6.4 属性表相关

**（13）属性表编辑未保存**
- ArcGIS Pro 的属性编辑走 **Edit tab** 的编辑会话；改完必须点 **Edit tab > Manage Edits 组 > Save**（保存编辑），**这与 `Ctrl+S` 保存工程是两件不同的事**；
- 只按 `Ctrl+S` 保存了工程，编辑内容可能未提交；关闭时若提示 "Save edits?" 选了 No，改动全丢。
- 📎 背景补充：以上编辑保存机制教程本周未涉及（本周没有编辑操作），但记住"**保存工程 ≠ 保存编辑**"这条区分。

**（14）Contour 的输入搞错**
再强调一次：**Contour 的 Input raster 必须是 `elevlidar`（高程），不能是 hillshade（灰度亮度）。**

### 6.5 课程管理层面

**（15）不登录 ESRI 账号 = 整个 practical 做不了**
本周数据全部来自 **Portal > My Organisation**，没登录组织账号连第 5 节都过不去。

**（16）每周的 practical 工程要留好**
30% 的 case study 是**逐周积累**的。第一周就养成"每次 practical 存成独立工程 + 数据放进工程 gdb"的习惯。

---

## 七、本周术语表

### 7.1 GIS 概念术语

| 中文 | English | 说明 |
|---|---|---|
| 地理信息系统 | **Geographic Information System (GIS)** | 用于空间参照数据的采集、管理、存储、组织、分析并输出空间参照信息的计算机系统 |
| 地理空间技术 | **Geospatial techniques** | 本课总称 |
| 数据 | **Data** | 一组相关事实；信息的基本元素 |
| 信息 | **Information** | 经处理而变得有用的数据，可回答问题、支持决策 |
| 空间参照的 | **Spatially-referenced** | 带有位置信息的 |
| 空间数据 | **Spatial data** | 有几何位置的数据 |
| 非空间数据 | **Non-spatial data** | 仅有属性、无位置的数据（如纯表格） |
| 属性 / 性质 | **Attribute / Property** | 描述空间实体的可观测或可测量特征 |
| 实体 | **Entity** | 可被属性描述的空间对象 |
| 坐标系统 | **Coordinate system** | 定义球面或平面坐标、高程、方位 |
| 球面坐标 | **Spherical coordinates** | 经纬度形式 |
| 平面坐标 | **Planimetric coordinates** | 投影后的平面 x, y |
| 空间参照系统 | **Spatial reference system** | ILO 2 核心概念 |
| 基准面 | **Datum** | 椭球体相对地球的定位方式 |
| 投影 | **Projection** | 曲面到平面的映射 |
| 图层 | **Layer** | 对某数据源的引用 + 显示方式 |
| 图层堆叠 | **Layer stack** | 多个数据集共享同一 x, y, z 位置 |
| 底图 | **Basemap** | 作为背景的参考地图 |
| 比例尺 | **Scale** | 如 1:24,000 |
| 分辨率 / 像元大小 | **Resolution / Cell size** | 栅格一个像元代表的地面尺寸 |

### 7.2 空间分析术语

| 中文 | English | 说明 |
|---|---|---|
| 空间查询 | **Spatial query** | 按属性或位置提问 |
| 几何量测 | **Geometric measurement** | 长度、周长、面积、形状、方位、质心、距离 |
| 缓冲区 | **Buffer / Buffering** | 计算围绕某要素一定距离的区域 |
| 邻近度量测 | **Proximity measurement** | 计算到某要素的距离 |
| 叠加分析 | **Overlay analysis** | 基于共同地理位置堆叠不同主题图层 |
| 表面分析 | **Surface analysis** | 对连续面（如 DEM）的分析 |
| 网络分析 | **Network analysis** | 路径、可达性等 |
| 影像分析 | **Image analysis** | 遥感影像处理 |
| 空间统计 | **Spatial statistics** | W05 主题 |
| 适宜性建模 | **Suitability modelling** | 叠加分析的典型应用 |
| 最优选址 | **Optimal site selection** | 叠加分析的典型应用 |
| 景观指标 | **Landscape metrics** | 几何函数的应用 |
| 景观破碎化 | **Landscape fragmentation** | 几何函数的应用 |
| 质心 | **Centroid** | 要素的几何中心 |

### 7.3 数据模型术语

| 中文 | English | 说明 |
|---|---|---|
| 空间数据模型 | **Spatial data model** | 表示空间数据的方式 |
| 矢量模型 | **Vector model** | 表示离散数据 |
| 栅格模型 | **Raster model** | 表示连续数据 |
| 离散数据 | **Discrete data** | 有明确边界 |
| 连续数据 | **Continuous data** | 平滑变化 |
| 点 / 线 / 面 | **Point / Line / Polygon** | 矢量三种几何基元 |
| 像元 / 像素 | **Cell / Pixel** | 栅格基本单元 |
| 波段 | **Band** | 栅格的一个数据层 |
| 像素类型 | **Pixel type** | 如 floating point、integer |
| 位深 | **Pixel depth** | 如 32 Bit |
| 数字高程模型 | **Digital Elevation Model (DEM)** | 最典型的栅格产品 |
| 数字化 | **Digitising** | 矢量数据采集方式 |
| 野外测量 | **Field surveying** | 矢量数据采集方式 |
| 摄影测量 | **Photogrammetry** | 矢量数据采集方式 |
| 激光雷达 | **LiDAR** | 矢量数据采集方式（讲义分类） |
| 遥感 | **Remote sensing** | 栅格数据采集方式 |
| 航空像片 | **Aerial photograph** | 栅格数据 |
| 卫星影像 | **Satellite image** | 栅格数据 |
| 矢量化 | **Vectorisation** | 栅格 → 矢量（如 Contour） |
| 空间变换 | **Spatial transformation** | 讲义有此页但无文字内容 |
| Shapefile | **Shapefile (.shp)** | 旧式矢量数据格式 |
| 地理数据库 | **Geodatabase (.gdb)** | ESRI 的数据库式数据容器 |
| 要素类 | **Feature class** | geodatabase 内的矢量数据集 |

### 7.4 ArcGIS Pro 界面与工具（必须保留英文）

| 英文原名 | 类型 | 位置 / 路径 | 说明 |
|---|---|---|---|
| **ArcGIS Pro** | 软件 | — | Esri 的高级 GIS 桌面应用 |
| **ArcGIS Online** | 平台 | `www.arcgis.com` | 云端 GIS 数据共享系统 |
| **ArcGIS Desktop (ArcMap, ArcCatalog, ArcToolbox)** | 旧版软件 | — | ArcGIS Pro 的前身，具备同等能力 |
| **ModelBuilder** | 工具 | ArcGIS Pro 内 | 可视化建模工作流 |
| **Python** | 语言 | ArcGIS Pro 内 | 脚本自动化（arcpy） |
| **Ribbon** | 界面 | 顶部 | 功能选项卡区 |
| **Core tabs** | 界面 | Ribbon | 始终存在的选项卡 |
| **Contextual tabs** | 界面 | Ribbon | 特定状态下才出现的选项卡 |
| **View** | 界面 | 中部 | 可关闭/拖动，活动 view 标签为蓝色 |
| **Map view** | 界面 | 中部 | 显示地图的窗口 |
| **Pane** | 界面 | 两侧 | 可停靠窗口 |
| **Contents pane** | 界面 | 左侧 | 显示 view 的内容（图层列表） |
| **Catalog pane** | 界面 | 右侧 | 显示 Project / Portal / Favorites |
| **Catalog View** | 界面 | — | 目录视图（教程此处术语有误） |
| **Symbology pane** | 界面 | 右侧 | 符号系统设置 |
| **Geoprocessing pane** | 界面 | 右侧 | 地理处理工具面板 |
| **Quick Access toolbar** | 界面 | 左上角 | 含 Save 按钮 |
| **Project** | 概念/文件 | `.aprx` | 包含 maps, scenes, layouts, data, tables, tools |
| **Map / Scene / Layout** | 概念 | 工程内 | 二维地图 / 三维场景 / 出图版面 |
| **New Project > Map** | 菜单 | 启动界面 | 本周新建工程的方式 |
| **Portal > My Organisation** | 数据源 | Add Data / Catalog | 本周数据来源 |
| **Add Data** | 工具 | `Map` tab | 下拉 > **Add Data to map** |
| **Add To Current Map** | 命令 | Catalog 右键 | 把数据加入当前地图 |
| **Remove** | 命令 | Contents pane 右键 | 移除图层（不删数据） |
| **Attribute Table** | 命令 | Contents pane 右键 | 打开属性表 |
| **Record** | 概念 | 属性表 | 行 |
| **Field** | 概念 | 属性表 | 列 |
| **FID** | 字段 | 属性表 | 唯一标识符 |
| **Properties** | 命令 | 右键 | 图层/地图属性对话框 |
| **Source（tab）** | 界面 | Layer Properties | 含 Data Source / Raster Information / Band Metadata / Statistics / Extent / Spatial Reference |
| **Extent（tab）** | 界面 | Map Properties | 设置自定义地图范围 |
| **Use a custom extent** | 选项 | Map Properties > Extent | 启用自定义范围 |
| **Current visible extent** | 选项 | Get extent from | 用当前可见范围生成坐标 |
| **Navigate（group）** | 界面 | `Map` tab | 导航工具组 |
| **Explore** | 工具 | Map > Navigate | 默认工具：平移、识别、缩放 |
| **Full Extent** | 工具 | Map > Navigate | 缩放到全图范围 |
| **Fixed Zoom In / Fixed Zoom Out** | 工具 | Map > Navigate | 固定倍率缩放 |
| **Previous Extent** | 工具 | Map > Navigate / 右键 | 回到上一视图 |
| **Bookmarks** | 工具 | Map > Navigate | 视图书签 |
| **Go To XY** | 工具 | Map > Navigate | 跳转到坐标 |
| **Zoom to Layer** | 命令 | Contents pane 右键 | 缩放到图层范围 |
| **Analysis > Tools** | 菜单路径 | Ribbon | 打开 Geoprocessing pane |
| **Hillshade (3D Analyst Tools)** | 工具 | Geoprocessing | 生成山体阴影 |
| **Input raster** | 参数 | Hillshade / Contour | 输入栅格 |
| **Run** | 按钮 | Geoprocessing | 执行工具 |
| **Contour** | 工具 | Geoprocessing | 生成等高线（Challenge 3） |
| **Contour interval** | 参数 | Contour | 等高线间隔（本周 10 ft） |
| **World Topographic Map** | 数据 | 默认底图 | 参考底图 |
| **World Hillshade** | 数据 | 默认图层 | 来自 Living Atlas 的高程图 |
| **Living Atlas** | 平台 | ESRI | 官方数据集合 |
| **Drawing order** | 概念 | Contents pane | 图层绘制顺序 |
| **Context menu** | 界面 | 右键 | 也叫 contextual / shortcut / pop-up menu |
| **Combo box** | 界面 | 地图下方 | 比例尺下拉框 |
| **Basemap** | 概念 | — | 背景参考地图 |
| **Geoprocessing** | 概念 | — | 地理处理 |
| **Hillshade** | 概念 | — | 灰度三维地形表现，由光源 + slope + aspect 决定 |
| **Slope / Aspect** | 概念 | — | 坡度 / 坡向 |
| **Azimuth / Altitude** | 参数 | Hillshade | 光源方位角 / 高度角 📎 |
| **Z factor** | 参数 | Hillshade / Contour | 垂直换算系数 📎 |
| **Customized Transverse Mercator** | 坐标系 | elevlidar | 自定义横轴墨卡托投影 |
| **False easting / False northing** | 投影参数 | Spatial Reference | 东/北偏移常数 |

### 7.5 本周数据集与地名

| 名称 | 说明 |
|---|---|
| **Prac_1_data.gdb** | 本周数据（来自 Portal > My Organisation） |
| **elevlidar** | LiDAR 高程栅格，9989×5105，6.289 ft，float 32 bit |
| **SamplingSite** | 5 个水质采样点（点图层） |
| **NewtonCreek** | Newton Creek 河道 |
| **MurphyOil** | Murphy Oil Inc. |
| **HogIsland** | Hog Island |
| **Newton Creek, Superior, Wisconsin** | 本周案例区（美国威斯康星州） |
| **EC / pH / T / DO** | 水样测量字段：电导率 / 酸碱度 / 温度 / 溶解氧（教程写作 dissolved organic carbon，疑误） |
| **USGS National Map** | 讲义案例：8 图层，1:24,000 |
| **Geo-Wiki / OpenStreetMap** | 讲义推荐浏览的在线地理数据平台 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `(EART29102) Geospatial Techniques.md` — Course unit overview / Syllabus 全节 | 大纲列出 Geodesy、GNSS、Photogrammetry、Satellite remote sensing、Databases and Big Data、Lidar、Sonar、UAV，并给出逐周安排（Week 1 Geodesy、Week 2 Photogrammetry……Week 10 Volcanic Plume Modelling 等） | **与实际授课内容严重不符**。实际讲义序列为 W01 GIS 导论 → W02 空间数据与数据管理 → W03 空间数据输入与操作 → W04 空间分析 → W05 空间统计 → W06 遥感 → W07 地形分析 → W08 空间可视化 → W09 三维地理空间技术 → W10 课程回顾，practical 全部基于 ArcGIS Pro | 大纲已过时（大纲本身注明 "subject to change depending on staff availability"）。**只可用作学分/考核形式等总体背景，不可用于推断周次内容。** |
| `(EART29102) Geospatial Techniques.md` — Assessment methods 表 | Set exercise 50% / Other 50% | 与 Lecture 1 讲义"Canvas test 70% + ArcGIS Pro project 30%"冲突 | **以讲义为准：Canvas 50 题测验 70%（夏季考试期），ArcGIS Pro 项目 30%（第 11 周末，2026-04-30 提交）** |
| `(EART29102) Geospatial Techniques.md` — Learning outcomes | 列出 4 条 ILO | 讲义列出 **5 条 ILO**，多出 "ILO 1: 理解 GIS 是什么与如何构成" 与 "ILO 5: 熟练使用 ArcGIS Pro" | 以讲义 5 条为准 |
| `Practical 1 - Introduction to ArcGISPro.md` — Learning objectives 第 4 条 | "apply some geoprocessing tools to **vector data** to create hillshade and contour layers" | **数据类型写反**。Hillshade 与 Contour 都以**栅格（raster）**为输入，本次输入是 `elevlidar` 栅格 | 应为 "apply some geoprocessing tools to **raster data** to create hillshade and contour layers" |
| `Practical 1` — 第 2 节 "Catalog View" 段 | "**Catalog View** is in the middle of the program and consists of map view." | 术语与位置均有误。中间的是 **Map view（视图）**；**Catalog View** 是另一种独立视图，与位于右侧的 **Catalog pane** 也不是一回事 | 应为："**Views** 位于程序中部，其中 **Map view** 是显示地图的窗口。" |
| `Practical 1` — 第 2 节 "Panes" 段 | "There are three panes… The second pane is called the **Map view** (middle)" | **Map view 是 view，不是 pane。** 教程把 view 与 pane 两个概念混为一谈 | 三个界面区域应为：**Contents pane（左）+ Map view（中，属于 Views）+ Catalog pane（右）** |
| `Practical 1` — 第 5 节 | "Another way to add spatial datasets is from **ArcCatalog**. The **ArcCatalog window**…" | **ArcCatalog 是 ArcMap（ArcGIS Desktop）时代的独立应用程序，ArcGIS Pro 中并不存在。** 后文实际操作用的是 Catalog pane | 应为 **Catalog pane / Catalog view** |
| `Practical 1` — 第 5 节 | "drag the dataset and drop it into the **data frame** listed in the **table of contents**" | **data frame** 与 **table of contents** 都是 ArcMap 旧术语 | ArcGIS Pro 中对应 **Map** 与 **Contents pane** |
| `Practical 1` — 第 5 节 vs 第 6 节 | 第 5 节从 **`Prac_1_data.gdb`**（地理数据库）加载数据；第 6 节称四个矢量图层 "comprising **shapefiles**" | **格式自相矛盾**：`.gdb` 内的矢量数据是 **feature class（要素类）**，不是 shapefile；两者是不同的存储格式 | 若数据确实来自 `Prac_1_data.gdb`，应称 **feature classes**。也可能是原书（Bajjali 2023）用 shapefile、本课改用 gdb 后未同步修改文字 |
| `Practical 1` — 第 6 节属性表字段说明 | "**DO** = dissolved organic carbon" | **缩写与全称不匹配**。水质监测中 **DO = dissolved oxygen（溶解氧）**；dissolved organic carbon 的缩写是 **DOC** | 应为 **DO = dissolved oxygen（溶解氧）**（除非该数据集确实记录 DOC，则缩写应改为 DOC） |
| `Practical 1` — 第 6 节 | "Right-click the **Sampling Site** layer" | 图层实际名称在同节上文写作 **`SamplingSite`**（无空格） | 统一为 **SamplingSite** |
| `Practical 1` — 第 8 节 | "right-click the "Map", select **Propertie s**" | 拼写/断词错误 | 应为 **Properties** |
| `Practical 1` — 第 13 节 Further help 链接 | "**htps**://www.esri.com/training/catalog/5d816c0255cf937306d2d3ef/arcgis-online-basics/" | 协议名拼写错误，少一个 `t` | 应为 **https://** |
| `Lecture 1 Introduction to GIS.md` — 第 1 页教学团队 | "Peter **Grinrod** (Natural History Museum)" | 姓氏疑似拼写错误 | 疑应为 **Peter Grindrod**（自然历史博物馆行星科学家）。**存疑，请以官方名单为准** |
| `Lecture 1 Introduction to GIS.md` — "GIS functional components" 页（第 12 页） | 仅有一张编号 1–6 的示意图，PDF 无文字层，OCR 也未恢复出组件名称 | **内容缺失**，无法从 md 得知六个组件分别是什么 | 需查阅原 PDF/PPT 或课件截图补齐。本笔记 2.5 节已标注"材料未说明" |
| `Lecture 1 Introduction to GIS.md` — "Spatial transformation" 页（第 25–26 页） | 仅有标题与文献引用 Yudono (2017)，无正文 | **内容缺失**，无法得知该页讲了什么变换 | 需查阅原件；预计在 W03「空间数据输入与操作」展开 |
| `Lecture 1 Introduction to GIS.md` — Further resources 链接 | "https://www.esri.com/training/catalog/5d9cd7de5edc347a71611cc - <u>c/gis basics/</u>" | URL 在 PDF 转换时被断行、插入空格与连字符，**无法直接点击使用** | 正确形式应为 `https://www.esri.com/training/catalog/.../gis-basics/`（需在 ESRI Academy 搜索 "GIS Basics" 获取准确链接） |
