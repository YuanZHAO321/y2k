# EART29102 Geospatial Techniques — Week 10 学习笔记

> **本周材料**：
> - `Lecture/Week 10/Lecture 10 Course review_handout.md`（讲义，1,827 词）
> - `Lecture/Week 10/EART29102 - 27-Apr-transcript.md`（课堂录音转写，6,506 词）
> - 授课日：**27-Apr**（全课最后一次授课）
> - 本周**无 practical**
>
> 本周讲义短、转写长，**绝大部分信息（尤其是考试信息与答疑）只存在于录音转写中**，本笔记的第四段是全篇最重的一段。

---

## 一、本周主题

本周主题是 **课程回顾（Course review）**，也是 EART29102 的**最后一次正式授课**。老师在开场就把行政信息交代清楚：

- 「this is the last meeting that we have, so the last lecture」——**本次课之后本课程结束**，不再有任何正式课堂。
- 下周一是 **bank holiday（英国公共假日）**，本来也不上课。
- 「last Friday was the last practical session」——**上周五是最后一次 practical**，本周与下周**都没有实习课**。
- 提醒 assessment（课程作业）必须提交：老师口述为「**2 o'clock on the 30th, which is Thursday**」，通过 **Canvas** 提交。（老师本人对日期用了「I think」并向学生确认「is that right?」，属不完全确定的口头信息。）
- 课上会再放一次 **SEATS code**（供未签到的同学再补一次）。

本次课的**结构**由老师自己在开头宣布，共三块：

1. **回顾全课所有主题**，不深入任何单一主题，只「highlight one or two things」；
2. **讲解考试（exam）的形式**；
3. **留时间答疑（Q&A）**。

### 本周在全课中的位置

老师在回顾时把课程明确地分成**两条线**：**Theory（讲授）**与 **Practical（实操）**。

**Theory 主线**（讲义 "Theory" 一页给出的顺序，与老师口述一致）：

```
Intro to GIS → Data input and handling → Analysis and statistics
→ Remote sensing → Terrain analysis → Cartography → 3D visualisation
```

**Practical 主线**（讲义 "Practical" 一页 + 老师口述）：以 **ArcGIS Pro** 为核心，围绕
`Data input and analysis`、`maps`、`Air pollution`、`Wind turbines`、`Geology`、`Flood hazards`、`Mineral resources`、`Solar mapping` 等主题展开。

老师对 practical 目标的口头总结值得记下来：

> 「really getting you started with ArcGIS Pro. **If you know ArcGIS, then you can use other GIS systems, QGIS, for example. So it's kind of useful transferable skill.**」
> 「Talk to you a little bit about digital map creation and some cartographic principles, **particularly when you come to hand in your assessment**.」

### 讲义给出的课程总目标（Course Overview - Aims，5 条）

1. Introduce and develop understanding of the **principles and applications of geospatial techniques**.
2. Show how different types of geospatial data can be **collected**（including remote sensing techniques）.
3. Develop skills required to **deal effectively with geospatial data** through real world examples.
4. To be able to **add, store, analyse and present** geospatial data using a **Geographical Information System (GIS)**.
5. Develop **proficiency in using the GIS software ArcGIS Pro**.

老师的对应说明：**第 1、2 条与部分第 3 条对应 lectures；第 4、5 条对应 practical classes**。并说「you can decide for yourselves how well you think we met those」。

### 本周提到的其他授课人

- **Rufus** —— 上周（Week 9）的 3D visualization 讲座与 practical。
- **Pete Grinrod** —— remote sensing 讲座。
- 主讲/单元协调人为 **Raymond Burgess**（据课程大纲）。

> 📎 **背景补充**：官方课程大纲（`(EART29102) Geospatial Techniques.md`）列出的 syllabus 是 Geodesy、Photogrammetry、GNSS、Lidar、Sonar、Volcanic Plume Modelling、UAV 等，**与本次复习课实际回顾的内容差异很大**。本笔记对「前九周讲了什么」的判断**只依据本周复习课实际提到的内容**，不依据大纲。凡本周材料未提及的周次细节，本笔记一律不写。

---

## 二、核心概念

> 本段完全按照**复习课实际回顾的顺序与深度**整理。老师反复说「I'm not going to go into any kind of detail」，因此本段的价值在于**「老师认为哪些是必须掌握的」**，而非全课百科。凡老师明确说「you really need to know this / you should be aware of those」的地方，本笔记会标出。

### 1. 什么是 GIS（老师明确点名的必考基础）

> 「one of the key things really is **knowing what a GIS is. So you really need to know that.**」

- **GIS 定义（老师口述版）**：a **computerized system that processes and manages spatial data**——一个处理并管理空间数据的计算机化系统。
- 它处理的对象：**maps、images 及其他类型的 spatial data**。

**GIS functional components（功能组件，讲义有框图）**：

| 组件 | 中文 | 老师的说明 |
|---|---|---|
| Spatial Data **Input** | 空间数据输入 | 可以来自 **User Interface**（用户直接输入）、**外部数据库**、或 **Application Programming Interface**（外部程序） |
| Spatial Data **Manipulation** | 空间数据操作 | 从 geodatabase 中提取并加工数据 |
| Spatial Data **Analysis** | 空间数据分析 | 在 GIS 内做分析 |
| Spatial Data **Output** | 空间数据输出 | 以所需形式输出 |
| **Data management** | 数据管理 | 贯穿全流程，数据存储与管理在 **database / geodatabase** 中 |
| Tools | 工具集 | 讲义框图中列出 |

流程链条：**输入 → 存入 geodatabase 管理 → 提取/操作/分析 → 输出**。

### 2. 地理空间的两种概念视角（Concept views of geographical space）

老师说这两个概念「pretty easy things to understand, but **fairly fundamental** to the way that the GIS stores data, and also what you can do in the way of analysis」。

| 视角 | 英文 | 内涵 | 对应数据结构 | 讲义示例 |
|---|---|---|---|---|
| 对象视角 | **The object view** | 事物是**离散实体（discrete entities）**，有明确边界 | **Vector**（point / line / area(polygon) objects） | Trees as **discrete objects**（把树当成一个个点） |
| 场视角 | **The field view** | **连续表面（continuous surface）**，地图上**每一处**都有一个值 | **Raster** | Tree height as **continuous surface**（树高作为连续面） |

### 3. Vector 数据结构

**定义**：数据结构就是「a set of rules that the GIS has to follow in order to deal with this kind of data」——GIS 处理该类数据必须遵守的一套规则。

Vector：离散要素，有边界，表示为 **points / lines / polygons**。

| Advantages（优点） | Disadvantages（缺点） |
|---|---|
| Data can be represented in their **original resolution without generalization**（按原始分辨率表示，无需概化） | **More complex data structure**（数据结构更复杂） |
| Requires **less disk storage space**（占用磁盘空间小） | **Inefficient for remotely sensed data**（不适合遥感数据） |
| **Topological relationships** are readily maintained（易于维持拓扑关系） | Some spatial analysis procedures are **complex and process intensive**（部分空间分析复杂、耗算力） |
| Graphical output **resembles hand-drawn maps**（输出像手绘地图，视觉效果好） | **Overlaying multiple vector maps** is often time consuming（多层矢量叠加耗时） |

**老师专门解释的概念——Topology（拓扑）**：

> 「Topology is just the **spatial relationship between objects**. So maintaining their **relative position** in a spatial context. So that if you're **zooming in and out of a map**, they don't suddenly all move all over the place relative to each other. Their **size and their position are fixed** so that they maintain their position and scale size.」

**老师点名的「主要缺点」**：spatial analysis procedures **complex and process intensive**（相对 raster 而言），会拖慢分析；且对影像数据（remotely sensed data）表现不好。

### 4. Raster 数据结构

- 表示形式：**a grid of cells（栅格）**，每个 cell 的**值**代表所关注的要素（道路、房屋、土地利用等，用不同 cell pattern / value / colour 表达）。

| Advantages（优点） | Disadvantages（缺点） |
|---|---|
| **Simple data structure**（结构简单） | Requires **greater disk storage space**（占用空间大） |
| **Efficient for remotely sensed or scanned data**（continuous data）（适合遥感/扫描等连续数据） | Depending on **pixel size**, graphical output may be **less pleasing**（视觉效果可能较差） |
| **Simple spatial analysis procedures**（空间分析过程简单，处理快） | **Projection transformations are more difficult**（投影变换更困难） |
| | **Difficult to represent topological relationships**（难以表达拓扑关系） |

老师补充：能否维持拓扑关系「depends upon the number of cells that represent a particular area... so it depends on the **spatial resolution** to some extent」——一定程度上取决于空间分辨率。

老师对本节的要求：「**you should be aware of those and know some of their advantages and disadvantages**」——要能说出 vector 与 raster 各自的优缺点。

### 5. 数据采集与结构转换（Spatial data models）

| Vector data capture（矢量采集） | Raster data capture（栅格采集） |
|---|---|
| Keyboard entry（键盘录入） | Remote sensing including **satellite images** and **aerial photographs** |
| **Digitising**（数字化） | **Crowdsourcing**（众包） |
| **Field surveying**（野外测量） | |
| **Photogrammetry**（摄影测量） | |
| **LiDAR** | |
| **Crowdsourcing**（众包） | |

**结构互转（Conversion）**——老师特别强调这一点：

- **Rasterisation（栅格化）**：vector → raster
- **Vectorisation（矢量化）**：raster → vector

> 「it doesn't mean that if we collect the data in one kind of representation, we can't then transform that into the other and do other kinds of processing.」

### 6. 地图投影与坐标系统（Map projections and coordinate systems）

讲义 6 条要点 + 老师口头展开：

1. 数据通过 **georeferences（地理参照）** 定位到地球表面；「georeferencing」是通用术语。**老师把它和 practical 挂钩**：「one of the things you had to do with a digital image was you had to **georeference it** in order to allow the GIS to know exactly where on the earth surface the digital image came from.」
2. 地球形状被建模为**球体（sphere）**，更准确地说是**扁椭球（oblate spheroid）**——两极略扁。
3. **Spherical reference model**（球面参考模型）例如 **WGS84**；常再用**地球重力场在平均海平面处的等位面（equipotential surface of the Earth's gravitational field at mean sea level）**加以改进，即 **geoid（大地水准面）**。老师的说法：「WGS84 是地球形状的数学模型，然后根据重力场略作调整，因为地表反映了地球内部的组成」。
4. **Local datum（局部基准）**考虑区域差异，例如 **NAD27**（北美）、**OSGB36**（英国 Ordnance Survey）。老师说这类基准「there's a lot of these that you can use」，讲课时曾给过一张列表。
5. **Geographical coordinate system（地理坐标系）**：用**球面坐标**定义位置，如 **latitude / longitude**，单位是**度（degrees）**。
6. **Projected coordinate system（投影坐标系）**：把球面转换到**二维平面**（地图、电脑屏幕），坐标为格网上的 **(x, y)**，例如 **UTM**、**British National Grid**。老师的直观理由：「You don't wanna carry a big globe around with you... You wanna carry a nice flat map or look at it on a computer screen.」

### 7. GNSS（Global Navigation Satellite System）

| 要点 | 讲义 | 老师口述 |
|---|---|---|
| 构成 | a **constellation of satellites** orbiting the Earth | 同 |
| 全球覆盖所需卫星数 | 估计 **18 to 30** 颗 | 「somewhere between about **20 and 30**」（与讲义略有出入，见勘误表） |
| 主要系统 | **GPS**（USA）、**GLONASS**（Russia）、**Galileo**（Europe）、**BeiDou**（China），四大在运行系统 | 「most of them are **accessible to everyone**」——多数系统对所有人开放 |
| 位置三要素 | **latitude**（距赤道距离）、**longitude**（距格林尼治子午线距离）、**elevation**（相对平均海平面的高程） | 同 |
| 定位所需卫星数 | **Four "visible" satellites** required for positioning；可达 **mm-scale accuracy** | 「if you need your **X, Y, and Z** value, then you need **four visible satellites** in the sky」 |
| 接收机 | Hand-held GNSS receivers 可在采样点获取坐标 | 「such as your **mobile phone**」 |

### 8. 空间分析与建模（Spatial analysis and modelling）

老师说这部分「we covered a couple of lectures on spatial analysis, **at least two**」，并把它分成两大类：

| 类别 | 关注点 | 老师原话 |
|---|---|---|
| **Spatial operations** | **几何（geometry）**：size、position | 「you're interrogating your data using spatial operations based on **where things are, how large they are**」（老师现场自述漏了第三项：「and something else I've forgotten about」） |
| **Spatial statistics** | **空间格局（spatial patterns）** 的建模与分析 | 「how are the different objects **related** rather than on their geometry」 |

老师强调两者「there's a kind of **overlap** between them」，并特别点出：

> **spatial analysis not only involves location, but also things like changes over time.** 「the **time aspect** is quite an important thing to consider, particularly in our branch of science where we're looking for **changes over time**.」

**Methods of spatial analysis（讲义三条定义，需背）**：

- **Spatial query（空间查询）**：filtering and selecting data **from a geodatabase** based on **attributes and location**。
- **Spatial operations（空间操作）**：a type of spatial query class that includes operations such as **intersection、containment、distance calculations** for objects in a given region or point.
- **Spatial interpolation（空间插值）**：**estimates unknown values at specific locations based on known values from surrounding points.**

### 9. 空间插值：IDW 与 Kriging

老师说「I will say a little bit about spatial interpolation **given that we spent a bit of time on this**」——这是他唯一愿意展开的分析主题，重要性明显。

**目的**：根据**已知点位**的数据，推断**未知位置**上某属性的值，得到一张 **prediction surface（预测面）**。
**讲义示例**：地图上的点是**降水量观测站（rainfall / precipitation 测点）**，插值得到整片区域的降水变化面。

| 方法 | 类型 | 输出 | 特点 |
|---|---|---|---|
| **Inverse Distance Weighting (IDW)** 反距离加权 | **Deterministic（确定性）** | 只给 **interpolated value（插值结果）** | 「**quick and easy**」 |
| **Kriging** 克里金 | **Geostatistical（地统计）** | 给 **interpolated value + probability（概率）** | 能给出插值结果的**误差估计**；「more involved in terms of the processing and understanding that you need to have」 |

老师补充：在讲义那张图上，「the results of both of them look **quite similar**, which is what you would hope to see」——两法结果相近是正常且期望的。

**Tobler's first law of geography（托布勒地理学第一定律）**——老师明确说「it sounds very simple, but it's **very fundamental**」：

> **Everything is related to everything else, but near things are more related than distant things.**
> （万物彼此相关，但近处的事物比远处的事物更相关。）

老师指出：**IDW 与 Kriging 都建立在这条定律之上**，并用降水举例：一片高降水区与很远处的地方相关性差。

### 10. 空间自相关（Spatial autocorrelation）

- **定义**：a measure of the **similarity (correlation) between nearby observations**（邻近观测之间相似性的度量）。
- **空间格局三态**：**clustered（聚集，close proximity）**、**dispersed（离散，spread out）**、**random（随机）**。
- **讲义标度**：`Negative ----- spatial autocorrelation ----- Positive`
- **假设检验**：
  - **Null hypothesis（零假设）**：spatial distribution is **random**（空间分布是随机的）。
  - **Alternate hypotheses（备择假设）**：spatial **clustered** 或 **dispersed**。

> ⚠️ **注意**：老师在课上对正/负空间自相关与聚集/离散的对应关系**说反了**（把 negative 说成 clustered、positive 说成 dispersed）。这是**本周最需要注意的一处材料错误**，详见文末**材料勘误表**。复习时请以标准定义为准：**正自相关 = 聚集，负自相关 = 离散，0 = 随机**。老师对「随机时空间自相关值为 0」的说法是正确的。

### 11. 空间统计（Spatial statistics）四大方法

老师说「we looked, I think, **mainly at these four statistics**」——四个都要掌握。

| 方法 | 中文 | 用什么算 | 输出 | 用途 |
|---|---|---|---|---|
| **Nearest neighbour** | 最近邻分析 | 只用 **locations（位置）** | **一个 −1 到 +1 之间的数字**，**无图形输出** | 判断格局是 random / dispersed / clustered |
| **Moran's I**（local or global） | 莫兰指数 | **feature values（要素值）+ their locations** | **单一统计量（a single statistic）** | 比最近邻**更进一步**，可**识别 clusters 与 outliers**（尤其 **local Moran's**） |
| **Getis-Ord Gi\*** | 热点分析 | 要素值与位置 | 显著性聚集结果 | **Hot-spot analysis**：识别**统计显著的高值聚集（hot spots）与低值聚集（cold spots）** |
| **Kernel density estimation (KDE)** | 核密度估计 | 点位/要素值 | **heat map（热力图）**，一张 **smooth density surface** | 显示**位置或要素值的浓度**在区域内如何变化（讲义/课上示例：**ozone 臭氧**） |

### 12. 遥感（Remote sensing）

**定义（讲义）**：Techniques for collecting environmental data **from a distance without coming into direct contact** with the objects of interest；记录**从地表或大气中的物体反射或发射的电磁能通量（electromagnetic energy flux）的大小**，通常以**影像（imagery）**形式呈现。老师补充：既测 **wavelength** 也测 **magnitude**。

**平台**：Airplanes、satellites、**UAVs**（装载传感器）。

**老师明确给出的二分法——被动 vs 主动传感器（讲义未直接列出，为课堂补充的重点）**：

| 类型 | 原理 | 例子 |
|---|---|---|
| **Passive sensors（被动）** | 测量**反射的太阳光（reflected sunlight）**在不同波长上的强度 | **Landsat**、**Sentinel-2** |
| **Active sensors（主动）** | **自己发射信号**射向目标，再测量**返回信号** | **Lidar、Radar、Sonar** |

**Spectral reflectance（光谱反射率）曲线判读**——老师现场读图（详见第三段）：横轴 wavelength，纵轴 reflectance(%)，三条典型曲线为 **water、vegetation、soils**。

**Digital multispectral images 的三种分辨率（考试高频，务必区分）**：

| 术语 | 中文 | 含义 |
|---|---|---|
| **Spectral resolution** | 光谱分辨率 | **spectral band width**——每个波段所覆盖的**波长宽度** |
| **Radiometric resolution**（= pixel depth） | 辐射分辨率 / 像元位深 | 每个 cell **能取多少个值**。讲义写 `8-bit = 2⁸ = 0–255` |
| **Spatial resolution** | 空间分辨率 | **pixel size**——每个 cell 在地表代表**多大面积**。面积小 = 高分辨率；面积大 = 低分辨率 |

老师补充的灰度约定：**高值 = 灰度的白端，低值 = 黑端**。

**Sentinel spectral bands（讲义表格的最后一列——用途）**：

| 波段用途（讲义原文） | 中文 |
|---|---|
| aerosols, bathymetry | 气溶胶、水深测量 |
| colour images | 彩色影像（老师说是 **band 2、3、4 = blue、green、red**） |
| vegetation health | 植被健康 |
| agriculture and forestry | 农业与林业 |
| vegetation, biomass, plant health | 植被、生物量、植物健康 |
| water vapour, cirrus clouds | 水汽、卷云 |
| burnt areas, moisture content | 火烧迹地、含水量 |

老师说该表还包含 **band number**、**波段名称（NIR = near-infrared，SWIR = short-wave infrared）**、**central wavelength**、**spatial resolution（以米计）** 等列，最后一列用途是他自己加的。他还提到可以「**separate rocks from snow**（区分岩石与雪）」。

### 13. 地形分析（Terrain analysis）

**同一连续表面的多种表示方式**（讲义原话：「different ways of representing the **same continuous surface at the same scale and extent**」）：

- **Contours（等高线）**
- **Spot heights（高程点）**
- **DEM（raster，栅格）**
- **TIN（Triangulated Irregular Network，不规则三角网，vector）**
- 老师口述中还加了 **Lidar points（激光点云）**

老师提到课上比较过 **rasters 与 TINs 各自的优缺点**。

**Primary vs secondary terrain attributes（地形属性）**：

| 类别 | 定义 | 例子 |
|---|---|---|
| **Primary attributes（一级属性）** | **直接由 DEM 计算得到** | **elevation（高程）、slope（坡度）、aspect（坡向）、plan curvature（平面曲率）、profile curvature（剖面曲率）** |
| **Secondary attributes（二级属性）** | **由两个或以上一级属性计算得到** | **solar radiation（太阳辐射）、moisture index（湿度指数）、sediment transport index（泥沙输移指数）** 等 |

**用途**：quantify the **movement and distribution of water in the landscape**（量化水在地表的运动与分布），以及 **the amount of solar radiation received at the surface**（地表接收的太阳辐射量）。

**Applications of terrain analysis（讲义列出 + 老师口述）**：

- **Catchment hydrology（流域水文）**——老师展开：「working out where **watersheds** are, **pour points** and **divides** and things like that」（分水岭、倾泻点、分水线）。
- **Line of sight and viewsheds（通视线与视域分析）**
- **Solar radiation mapping（太阳辐射制图）**——老师说「**you did a practical based on that as well**」。

### 14. 制图学（Cartography）

**(a) Map scale（比例尺）——老师亲自读图讲解的重点**

> 「The **smaller the scale, the larger the area** that's covered.」
> 「The **larger the scale, the smaller the area** that's covered and the **more detail** you get.」

讲义对应写作：`Large scale = small area` / `Small scale = large area`。
讲义底部四张递进的小图：每张图中央的小方框，就是下一级更大比例尺图所覆盖的范围。

老师把比例尺与**编辑/概化**直接挂钩：小比例尺图无法展示同样多的细节，所以必须 **generalise**，在**简化**的同时保持**有意义且准确的表达**。

**(b) Cartographic editing and generalisation（讲义表格）**

| **Editing（编辑）** | **Generalisation（概化 / cartographic abstraction）** |
|---|---|
| **Rubber sheeting** – remove geometric distortions（橡皮拉伸，消除几何变形） | **Selection** – retain important features（选取重要要素） |
| **Transformation** – rotate, scale, skew or translate features（旋转/缩放/斜切/平移） | **Simplification** – remove complexity（简化，去除复杂性） |
| **Edge matching** – feature matching across layers（接边匹配） | **Exaggeration** – emphasise important features（夸大重要要素） |
| **Line simplification** – simplify while retaining shape（线简化，保持形状） | **Combination** – merge similar features（合并同类要素） |
| **Error corrections** – overshoot, unclosed polygon, etc.（错误改正：过头线、未闭合多边形等） | **Displacement** – move to make distinguishable（位移以便区分） |
| **Reshaping individual features**（单要素重塑） | **Classification** – group similar features（分类归组） |

> ⭐ **老师的原话（重要的减负提示）**：「Now I **wouldn't expect you to know all of these**, okay? So **don't try and learn them all**, but try and remember **some of the ones that we actually did / covered in the lecture** in a little bit more detail.」——这张表比课上讲的更全，只需记住课上详讲过的那几个。

**(c) Map types（地图类型）**

| 大类 | 子类 | 说明 |
|---|---|---|
| **General purpose maps（通用地图）** | **Topographic maps（地形图）** | 提供某区域**综合性参考信息**；老师举例 Google Maps、纸质地图 |
| | **Base map（底图）** | 为叠加**附加信息图层**提供基础；老师说是地形图的「**stripped down version**」，只保留 roads、towns，视需要加 contours |
| **Thematic maps（专题地图）** | dot、isoline、choropleth、proportional、graduated 等 | 表达**单一属性/变量的空间分布**，或**若干变量之间的关系**；老师说其目的是「communicate a particular piece of information」 |

**(d) Map design（地图设计四步）**

1. **Selection**：选择 geographical area、geographical features、**map scale**、**projection**、data variables 等。
2. **Classification**：对数据分组与归类（老师：「to simplify things a little bit」）。
3. **Symbolisation**：选择符号与视觉变量，以**合乎逻辑的方式**表达数据（老师：要「visually appealing」且让人看得懂）。
4. **Layout design**：把各种制图要素**连贯地组织在一页上**。

**(e) Map elements（地图要素，讲义 OCR 出的示意图）**

以「Households with Very High Income in Melbourne by Local Government Areas in 2006」为例，一张完整地图应包含：

**Title（标题）、North arrow（指北针）、Map body（图面主体）、Legend（图例）、Inset（插图）、Scale bar（比例尺条）、Credits（数据来源/致谢）、Neatline（图廓线）、Other text information（其他文字信息）**。

> 老师说：「hopefully you should be familiar with this now having... going through your **assessment** process. You've got a nice map layout showing all of these elements and they're all arranged appropriately on the page.」——**这套要素是评作业的直接标准**。

**(f) Animated mapping（动态地图）**

- 用动画表现 **time（时间）、space（空间）或 attributes（属性）** 上的变化。
- 动画可以是 **temporal（含时间维）**，也可以是 **non-temporal（不含时间维）**。
- 讲义示例：**animation showing the positions of Antarctic icebergs through time**（南极冰山位置随时间变化）。
- 老师评价：「a **very effective way of communicating information**, particularly showing changes over time」。

（讲堂中老师在这一页发现讲义少了一页 / 版本不一致：「Missing a page... it looks like I've got an earlier version. Let's skip to this one.」）

### 15. 三维技术（3D）——Rufus 上周所讲，本周重申

**2.5D vs 3D 的区分（老师说这是「the first thing you probably did」）**：

| | **2.5D** | **True 3D** |
|---|---|---|
| 典型例子 | **Geological map draped over a DEM**（地质图铺在 DEM 上）——显示 elevation 与 relief | **Geological model（三维地质模型）**、**Digital twins（数字孪生城市）** |
| 坐标 | 点仍只需 **x, y** 描述（本质是二维表面存在于三维空间中） | 需要 **x, y, z** 三个坐标 |
| Z 的含义 | Z 只代表**一个属性值**（如海拔高度） | 代表**体积（volume）** |
| 关键判据 | **不含 volume** | **Volume is integral**；「Without z, it is **not possible to locate where inside the volume** something is.」 |

**Digital space：Pixel vs Voxel**

| | **PIXEL** | **VOXEL** |
|---|---|---|
| 定义 | **2D 栅格影像中最小的信息单元**，每个 pixel 有 **x, y** 位置 | **三维像素（volume element）**，用于显示 3D 影像 |
| 几何 | 平面单元格 | **一个由 x, y, z 范围界定的小立方体（a small cube）** |

---

## 三、公式与图表

本周是复习课，没有新推导，但重申了以下可量化/可判读的内容。

### 1. 辐射分辨率（Radiometric resolution / pixel depth）

讲义写法：

```
8-bit = 2^8 - 1 = 0 - 255
```

- **含义**：8 位存储 ⇒ 每个像元可取 **2⁸ = 256 个不同的值**，取值范围为 **0–255**。
- **灰度对应**：**高值 → 白（white end of the grey scale）；低值 → 黑（black end）**。
- 老师提到还有 **12-bit、24-bit** 等更高位深。
- 📎 **背景补充（供理解）**：位深 *n* 位对应的取值个数为 **2ⁿ**，取值范围为 **0 至 2ⁿ−1**。故 8-bit → 0–255（256 级）；12-bit → 0–4095（4096 级）；每通道 8-bit × 3 通道（RGB）= **24-bit，约 1,677 万（16.7 million）种颜色**。老师课上把「16.8 million 种颜色」归给 12-bit，这是**口误**，详见勘误表。

### 2. 空间分辨率（Spatial resolution）与像元大小的反比关系

- **每个 cell 覆盖面积小 ⇒ 空间分辨率高**
- **每个 cell 覆盖面积大 ⇒ 空间分辨率低**
- Sentinel 波段表以**米（m）**给出各波段的 spatial resolution。

### 3. 比例尺（Map scale）关系

```
Large scale（大比例尺） = small area（小范围） = 更多细节
Small scale（小比例尺） = large area（大范围） = 必须概化
```

判读讲义底部四联图的方法：**从右往左**，每张图**中心的小方框**对应下一张（更大比例尺）图的全幅范围，逐级放大、细节递增。

### 4. 空间自相关取值范围

- **Nearest neighbour**：返回一个 **+1 到 −1 之间的数字**（老师原话），据此判断 random / dispersed / clustered，**无图形输出**。
- **Moran's I**：返回**单一统计量**；有 **global** 与 **local** 两个版本，**local Moran's** 可识别 **clusters 与 outliers**。
- **假设检验框架**：H₀ = 空间分布随机；H₁ = 聚集或离散。**随机时空间自相关值为 0。**
- **标准对应关系（考试请以此为准）**：**Positive → clustered（聚集）；Negative → dispersed（离散）；0 → random（随机）**。

### 5. 光谱反射率曲线（Spectral reflectance）判读

老师现场读图的逻辑（**考试判读题的直接模板**）：

- **横轴**：wavelength（波长）；**纵轴**：reflectance（%）。
- **可见光区**：低波长端 **blue（蓝）** → 中间 **green（绿）** → 高波长端 **red（红）**；再往右超出可见光即 **infrared（红外）**。
- **三条曲线**：**water（水）、vegetation（植被）、soils（土壤）**。
- **Vegetation 的特征（老师详讲）**：
  - 在 **blue** 与 **red** 波段**吸收强**（反射低）；
  - 在 **green** 波段**反射较高** ⇒ **这就是植物看起来是绿色的原因**；
  - 在 **near-infrared（近红外）反射非常强**。
- **应用推论**：用不同波段组合可反演各类信息，**尤其是 vegetation health（植被健康）**。

### 6. 多光谱影像的三重分辨率（一图三问）

看到一幅多光谱影像，要能同时回答：

| 问题 | 对应术语 |
|---|---|
| 这个波段覆盖多宽的波长范围？ | **Spectral resolution**（band width） |
| 每个像元能有多少个取值？ | **Radiometric resolution / pixel depth**（如 8-bit → 0–255） |
| 每个像元代表地面多大面积？ | **Spatial resolution**（pixel size，单位 m） |

### 7. 考试计分「公式」（多选题 multiple-answer 计分规则）

这是本周唯一一条真正需要「算」的规则：

```
题目得分 = (选中的正确答案数) − (选中的错误答案数)
未选择的答案：不加分也不扣分
每题最低分 = 0（不会为负）
```

**讲义给出的评分示例表（以 2 分题为例）**：

| 情况 | No attempt（不作答） | Select both correct answers（两个都对） | Select one correct answer only（只选一个且对） | Select any two, one correct one incorrect（选两个，一对一错） | Select any two incorrect answers（选两个都错） |
|---|---|---|---|---|---|
| **得分** | **0** | **2** | **1** | **0** | **0** |

老师的口头推演补充：「if you selected **all five**, you'd still get **zero**」——五个全选，正负抵消后仍不低于 0，即得 0 分。

### 8. 讲义给出的例题（Example multiple answer question）

> **Which TWO of the following are forms of geometric corrections applied to satellite multispectral images?** *(2 marks)*
>
> A. Removal of geometric distortions caused by **sensor-Earth geometry variations**.
> B. **Georeferencing** an image to a particular **projected map coordinate system**.
> C. Correcting an image for **sensor response properties and viewing geometry**.
> D. Correcting an image for **atmospheric effects and scene illumination**.
> E. **Restoring an image to accurately represent the radiance** measured by the sensor.
>
> **Answer：A 与 B 是 geometric corrections（几何校正）。其余（C、D、E）是 radiometric corrections（辐射校正）。**
> **且：这些校正都在任何 image enhancement（如 band combinations）之前进行。**

**这条「校正先于增强」的顺序是讲义明确写出的知识点，值得单独记牢。**

---

## 四、课堂补充

> 本周转写 6,506 词、讲义仅 1,827 词，**考试信息、作业信息与答疑几乎全部只存在于录音中**。以下按老师讲述顺序忠实整理。

### A. 行政与课程收尾信息

| 事项 | 老师原话/要点 |
|---|---|
| 本次课的性质 | 「this is **the last meeting** that we have, so **the last lecture**」「**the course finishes today**」「there won't be any other formal classes」 |
| 下周一 | **Bank holiday**，本来就没课 |
| Practical | 「**last Friday was the last practical session**」；**本周与下周都没有 practical** |
| Assessment 截止 | 老师口述：「**2 o'clock on the 30th, which is Thursday**」；通过 **Canvas** 提交；老师说「I know many of you have already handed in your assessment」 |
| SEATS code | 课上会再放一次，供没签到的同学补（「if you haven't caught the SEATS code yet, you'll have another chance」） |
| 课后联系方式 | 「you can always **email me** if you have anything you want me to explain or if you didn't understand anything from any of the lectures... just feel free to email」 |
| 结语 | 「I hope you found the course interesting and it'll be useful for you in the years to come.」 |

> 📎 **背景补充**：SEAtS 是曼彻斯特大学用于课堂考勤登记的系统，上课时屏幕会显示一个签到码。此为通用背景，材料本身只提到「SEATS code」，未说明其用途。

### B. ⭐ 考试信息（Exam）——本周最核心的补充内容

**来源双重确认**：讲义 "EART29102 Exam" 一页 + 老师口述 + 讲义 OCR 出的**考卷封面（cover sheet）**。

#### B1. 考试形式与条件

| 项目 | 内容 | 出处 |
|---|---|---|
| 形式 | **Online exam（线上考试）**，在 **controlled conditions（受控条件）** 下进行，即 **invigilated（有监考）** | 讲义 + 转写 |
| 可携带材料 | **不可**参考 notes、books、web resources，**不可使用 AI**（「The use of AI software is **prohibited**」） | 讲义 + 封面 |
| 开卷/闭卷 | **Closed book（闭卷）** | 封面 + 转写 |
| **计算器** | **NOT permitted（不允许使用计算器）** | 封面「Additional permitted materials: The use of calculators is **NOT** permitted for this exam.」 |
| 时长 | **ONE HOUR THIRTY MINUTES（1 小时 30 分钟）**；老师说这是「a standard time」 | 封面 + 转写 |
| 日期与时间 | 封面写 **08 June 2026，14:00 – 15:30** | 讲义封面 OCR |
| 提交 | 「Answers to the online exam **MUST be submitted at the end of the exam**.」 | 封面 |
| 具体考场/时间以何为准 | 老师：「hopefully you should have an **exam timetable** now telling you **when and where** the exam is」 | 转写 |

#### B2. 权重与题量

| 项目 | 内容 |
|---|---|
| **占最终成绩比例** | **70%**（讲义与老师口述一致：「Exam is 70% of the final mark for the course」） |
| **题目数** | **50 questions** |
| **总分** | **80 marks**（封面：「There are **80 marks** available on this exam」） |
| **推论** | 因为 50 题 80 分，所以「**some of the questions carry more than one mark**」；**每题会标明分值**，且「may be used as a guide to how much time you should spend on each」 |
| 题型 | **majority are multiple choice（单选为主）**，**some are multiple answer（部分为多选）** |
| 作答范围 | 「**Answer ALL questions** in the online exam」；老师：「attempt all the questions that you can」 |

> ⚠️ 关于 70% 与官方大纲（50% set exercise + 50% other，且写「There is **no exam** for this module」）的矛盾，见文末**勘误表**。**以本周讲义与老师口述的 70% 为准**（这是本学年的实际安排）。

#### B3. 老师给出的复习策略（原话）

1. **把所有 lecture quiz 做一遍——这是最重要的一条建议**：
   > 「Most of the multiple choice questions are **very similar in style to the lecture quiz questions**. So if I had any general advice, I would say **go through all the quizzes**, because you're probably going to encounter something quite similar in the exam. **If you feel confident in answering all the quiz questions from the lectures, that really will prepare you well for the exam.**」
   讲义同样写着：「Use the **weekly quizzes** as practice.」

2. **不要赶时间**：
   > 「You've got quite a lot of time... **take your time and read each question carefully**. You've got **plenty of time**. You don't need to race through it to the end.」
   讲义：「Take your time and **read each question carefully**.」

3. **练习题已发布**：
   > 「What I've done is, **for this week, I put up just a very few practice exam questions**, which cover... pretty much **all the main types of question**. **I don't think it's a true or false in there, but every other type is in there**, because there are a couple of other types in there as well. And I've put **a little bit of explanation about whether partial credit is applied or not** to those. So have a look at those. **So I think there's about four.** Includes this question here.」
   ⇒ **本周发布了约 4 道 practice exam questions**，涵盖除 true/false 外的所有主要题型，并附有是否给 partial credit 的说明。

4. **有疑问随时问**：
   > 「If you've got any questions about that, you can ask me **now or at any time before the exam**... Because the last thing I want to do is confuse everyone.」

#### B4. ⭐⭐ 多选题的负分机制与应试策略（老师花了最多篇幅解释的一点）

**封面原文（四条规则）**：

> - You **gain marks** for each **correct** answer selected.
> - You **lose marks** for each **incorrect** answer selected.
> - You **do not lose marks** for answers you do not select.
> - **The minimum score for each question is 0.**

**老师的口头解释与策略建议（几乎是逐字的应试指导）**：

> 「the way the marking works is that you **gain a mark for each of the correct answer that you select**, and you **lose a mark for each incorrect answer you select**. So you get **partial credit**, but it's also a kind of **negative marking**. You **don't lose any marks if you don't select** a question and answer... And **the minimum score for each question is zero**. So if, for example, you answer two incorrect answers, that would be minus two, but **you can't go below zero**. So if you selected **all five**, you'd still get **zero**.」

> 「**Think carefully about your strategy.** If you **definitely know one answer**, and you're **not sure about the other**, if it's asking you for two, then **go for the one that you really know**, and then consider whether you should choose the other one as well. **Because if you just choose one, you will get one mark. If you choose two and one is correct and one is incorrect, you'll get zero.**」

**⇒ 提炼成决策规则（考前必背）**：

| 情形 | 最优做法 |
|---|---|
| 两个答案都确定 | **两个都选**（得满分） |
| 只确定一个，另一个完全没把握 | **只选那个确定的**（稳拿 1 分）——**不要凑数** |
| 只确定一个，另一个把握 > 50% | 可以考虑再选一个（期望值判断） |
| 一个都不确定 | 乱选 = 期望 0 分，但也**不会倒扣到负分**；不过对该题而言与不答等价 |
| 全选 | **必然得 0 分**——绝不可全选 |

**核心直觉**：「一对一错 = 0 分」意味着**一个错误选项会完全抵消一个正确选项**，所以「多选一个赌一把」的代价是**丢掉已经到手的那 1 分**。

#### B5. 讲义例题的逐情形得分推演（老师口述）

以 "Which TWO... geometric corrections" 一题（2 分，正确答案 A 和 B，选项 A–E）为例：

| 你的选择 | 得分 | 老师原话 |
|---|---|---|
| 不作答 | **0** | 「if you don't make any selection, then obviously you'll get zero」 |
| A + B | **2** | 「that's great, you get two marks」 |
| 只选 A（或只选 B） | **1** | 「then you'll get one mark」 |
| A + C（一对一错） | **0** | 「they effectively **cancel themselves out**, you get zero」 |
| 任意两个错误选项 | **0** | 「you get zero」 |
| 全选 A–E | **0** | 「you'd still get zero」 |

**知识点本身**：A、B 为 **geometric corrections**；C、D、E 为 **radiometric corrections**；**所有 corrections 都在 image enhancement（如 band combinations）之前施加**。

### C. 老师明确说「你需要知道 / 不需要背」的清单

这是复习课上最有价值的信号，直接决定复习优先级：

**✅ 明确要求掌握：**
- 「one of the key things really is **knowing what a GIS is**. So **you really need to know that**.」
- 「object view and field view... **fairly fundamental** to the way that the GIS stores data」
- 「**you should be aware of those and know some of their advantages and disadvantages**」（指 vector 与 raster 的优缺点）
- 「**Tobler's law... it's very fundamental**」
- 「hopefully I've sort of highlighted some of the **key things that you need to know and understand in preparation for the exam itself**」（指整节复习课扫过的所有主题）

**❌ 明确说不必全背：**
- 「Now I **wouldn't expect you to know all of these**, okay? So **don't try and learn them all**」（指 editing/generalisation 那张长表）——「try and remember **some of the ones that we actually did** / covered in the lecture in a little bit more detail」。

**老师自己「不展开」的主题**（说明考法应偏定义与辨析，而非细节推导）：
- 「I'm **not going to go into any kind of detail** about any of them. I think we covered that quite well in the lectures」（指 spatial analysis 的各方法）
- 「Not really gonna talk about that much, but **I will say a little bit about spatial interpolation given that we spent a bit of time on this**」——**IDW 与 Kriging 是老师唯一主动展开的分析主题，权重明显更高**。

### D. Coursework / Assessment 的答疑（下课后学生逐个提问，全部关于作业）

课后有至少三位学生连续提问，全部围绕 **assessment（要交的 GIS 作业）**。老师的回答透露了**评分口径**，价值很高：

#### D1. 关于「做到什么程度」的总口径 ⭐

学生问：把建筑分成 high-risk / low-risk / medium-risk 三类做了 fly-through，「Is that **too over the top**?（是不是做过头了？）」

老师回答：
> 「**That's fine, yeah. I'm not being too prescriptive about what people do, so I'm very much gonna be led by how you've done it and then I'll judge you on the basis of that.**」

**⇒ 评分不预设固定模板，按你实际的做法来评。**

另一位学生反复确认深度：
> 学生：「And then I've not really developed it.」老师：「**No, that's fine, yeah.**」
> 学生：「Just basic kind of low-level.」老师：「**Yeah, low-level stuff is fine, yeah.**」
> 学生：「And then same for the maps.」老师：「**Same for the maps, yeah.**」

**⇒ 基础、低复杂度的做法是可以接受的，不要求做得多花哨。**

#### D2. 关于范围（extent）

学生问：已经做出了整个 borough 的轮廓，「Should I do the whole thing or just zoom into the effect of the area?」

老师：
> 「It might be that you want to **show just a small part of it**... **the bits that are most interesting**.」

**⇒ 建议聚焦到最有信息量的区域，而不是硬套整个行政区。**

#### D3. 关于底图（base map）与图面繁简

学生问：同一张图，一版有 base map 一版没有，「Which format would you prefer?」

老师：
> 「**It's entirely up to you. Which one you think is most useful, or you could put both in.**」

后面学生自己判断：「I thought with the base map, it was **too much**」，老师认同：
> 「Yeah, that's right, **you're too busy, isn't it? No, I think that's fine, yeah.**」

**⇒ 图面是否加底图看信息传达效果；底图使图面过于杂乱（too busy）时应去掉。**

#### D4. 关于文字说明的写法 ⭐（最容易踩坑的一条）

学生问：「are you expecting us to write kind of like a little...（要不要写一小段文字）」

老师：
> 「**It would be useful if you just summarised what you think the main message was of the map.**」（总结这张图的**主要信息**）

学生试探：「so like closer to the cities and...」老师：
> 「Yeah, that's right, **but don't try and interpret what it all means.** You know, **don't say, well, this area has got higher whatever it is, because...**」

**⇒ 关键区分：要写「这张图在讲什么（描述性 main message）」，不要写「为什么会这样（因果性解释/成因推断）」。**

#### D5. 关于统计结果的呈现

学生（做 hot spot 分析）说：「I'm just putting the probability number, the **p-value**.」
老师：「**Yeah, that's fine, yeah.**」

**⇒ 统计部分给出 p-value 即可，不必展开。**

#### D6. 关于比例尺（scale）与排版 ⭐

学生（做 air quality 那个题目）问：「do I need to **scale everything for all of the maps**...？」并说有很多张同一区域的图但没法叠加。

老师：
> 「**Yeah, it's fine to have separate maps, no problem with that, but yeah, try and include a scale.**」

关于提交格式，老师给出的明确说明：
> 「you'll probably want to **submit a PDF with some map images, and some statistical data**.」

学生问「You want each map on a different page?」，老师：
> 「**It's up to you.** If you think it's useful to have **side-by-side comparisons**, then that's fine. If you want to put them on a separate page（也行）.」

**⇒ 作业提交要点：PDF；含 map images + statistical data；每张图都要有 scale（比例尺）；分页或并排比较由自己决定；可以用多张独立的图而不必强行叠加。**

（录音末尾因下一堂课要进教室而中断：「We've got a class in here now. Can we plug it in outside?」）

---

## 五、Practical 要点

**本周无 practical，本课实习课至第 9 周结束。**

老师在课上明确说明：「a reminder that **last Friday was the last practical session**, so there **won't be a practical either this week or next week**」，且「**the course finishes today**」。

不过本次复习课**确实包含了与实操相关的内容**，按任务要求归入本段如实整理如下：

### 1. 老师对整个 Practical 系列的总结（讲义 "Practical" 页 + 口述）

- **核心软件**：**ArcGIS Pro**（全部 practical 的主线）。
- **技能可迁移性**：「**If you know ArcGIS, then you can use other GIS systems, QGIS, for example. So it's kind of useful transferable skill.**」
- **涵盖内容**（讲义列出的关键词）：`Data input and analysis`、`maps`、`Air pollution`、`Wind turbines`、`Geology`、`Flood hazards`、`Mineral resources`、`Solar mapping`。
- **老师口述的补充**：digital map creation 与 **cartographic principles**（并指出这些原则**在写 assessment 时要用上**）；satellite imagery 的 practical；以及 air pollution、wind turbines、flood hazards、solar mapping 等案例，还有 geological maps 与 renewable resources。
- 老师总评：「a fairly **wide range of topics** that we tried to **integrate into the practicals**」。

### 2. 复习课中回指到具体 practical 操作的几处

| 主题 | 老师的回指 |
|---|---|
| **Georeferencing** | 「if you remember back to one of your practicals, one of the things you had to do with a **digital image** was you had to **georeference it** in order to allow the GIS to know exactly where on the earth surface the digital image came from」 |
| **Solar radiation mapping** | 「We did something on solar radiation mapping, and **you did a practical based on that as well**」 |
| **3D 地质模型** | 「You can make **three-dimensional geological models**, which is a bit like **you did in the practical last week**（Week 9，Rufus）」 |
| **Map elements / 图面布局** | 「hopefully you should be familiar with this now having going through your **assessment** process. You've got a nice **map layout showing all of these elements** and they're all **arranged appropriately on the page**」 |
| **Fly-through（三维飞行浏览）** | 学生课后提到自己「I've done the **fly-through**」，并按 high/medium/low-risk 对建筑分类；老师认可这种做法 |

### 3. 作业操作层面的要求（源自课后答疑，详见第四段 D）

- 提交物：**PDF**，包含 **map images + statistical data**，通过 **Canvas** 提交。
- **每张地图都要有 scale（比例尺）**。
- 允许**多张独立地图**，不必强行叠加到一张图上。
- **base map** 加不加由信息传达效果决定；太杂乱（too busy）就去掉。
- 每张图配一小段**「main message」**的概括，**不要做成因解释**。
- 统计部分给出 **p-value** 即可。
- 深度上，**basic / low-level 的做法可接受**；老师不预设模板，按你实际做法评分。

---

## 六、易错点 / 重点难点

### ⭐ A. 考试作答类（老师亲自强调，风险最高）

| # | 易错点 | 正确做法 |
|---|---|---|
| A1 | **多选题「凑数多选」** | 一对一错 = **0 分**，会把已到手的 1 分抵消掉。**只确定一个就只选一个。** |
| A2 | **以为全选可以保底拿分** | 全选 = **0 分**（老师明说「if you selected all five, you'd still get zero」）。 |
| A3 | 以为不作答会倒扣 | **不选不扣分**，每题**最低 0 分**，不会为负。但不选也拿不到分——**能作答的都要作答**（"Answer ALL questions"）。 |
| A4 | 以为 50 题 = 50 分 | **50 题 / 80 分**，部分题目多于 1 分；**每题会标注分值**，可据此分配时间。 |
| A5 | 匆忙抢答 | 90 分钟对 50 题**时间充裕**，老师两次强调 **read each question carefully**。 |
| A6 | 带计算器 / 想着查资料 | **计算器不允许**；**闭卷**；**禁止使用 AI**；有**监考**。 |
| A7 | 不做 quiz 就去考 | 老师最强的一条建议：**把所有 lecture quiz 过一遍**，考题风格与之高度相似；本周另发布了约 **4 道 practice exam questions**（含除 true/false 外的各类题型及 partial credit 说明）。 |

### ⭐ B. 概念混淆类

| # | 易混对 | 辨析 |
|---|---|---|
| B1 | **Positive vs Negative spatial autocorrelation** | **正 = clustered（聚集）；负 = dispersed（离散）；0 = random**。⚠️ 老师课上说反了（见勘误表），**不要跟着记错**。 |
| B2 | **Large scale vs Small scale** | **Large scale = small area = 更多细节**；**Small scale = large area = 需概化**。直觉容易反过来。 |
| B3 | **Spectral / Radiometric / Spatial resolution** | 波段**宽度** / 像元**取值个数（位深）** / 像元**地面面积**。三者是多光谱影像的三个独立维度。 |
| B4 | **2.5D vs True 3D** | 判据是**有没有 volume（体积）**。地质图 drape 到 DEM 上仍是 **2.5D**（z 只是一个属性值）；有体积、需要 x,y,z 定位「体内某处」才是 **true 3D**。 |
| B5 | **Pixel vs Voxel** | Pixel = 2D 栅格最小单元（x, y）；Voxel = **volume element**，由 x, y, z 范围界定的**小立方体**。 |
| B6 | **Object view vs Field view** | 离散实体、有边界（→ vector） vs 连续表面、处处有值（→ raster）。 |
| B7 | **IDW vs Kriging** | IDW = **deterministic**，只给插值**值**，快而简单；Kriging = **geostatistical**，给**值 + 概率（误差估计）**，更复杂。 |
| B8 | **Nearest neighbour vs Moran's I** | 最近邻**只用位置**、给一个 −1~+1 的数、**无图形输出**；Moran's I **用要素值 + 位置**，可识别 **clusters 与 outliers**（尤其 local 版）。 |
| B9 | **Getis-Ord Gi\* vs KDE** | Gi\* = **hot spot analysis**，找**统计显著**的高值/低值聚集；KDE = **heat map / 平滑密度面**，展示浓度变化（并非显著性检验）。 |
| B10 | **Geographical vs Projected coordinate system** | 前者是**球面坐标**（lat/long，单位度）；后者是**投影到二维平面**的 (x, y) 格网（UTM、British National Grid）。 |
| B11 | **Spheroid / Geoid / Datum** | **WGS84** 是地球形状的**数学模型（oblate spheroid）**；**geoid** 是重力场在平均海平面处的**等位面**；**local datum**（NAD27、OSGB36）针对**区域**做修正。 |
| B12 | **Geometric vs Radiometric corrections** | **几何校正**：sensor-Earth geometry 变形的消除、**georeferencing 到投影坐标系**；**辐射校正**：sensor response、viewing geometry、atmospheric effects、scene illumination、radiance 还原。**两类校正都在 image enhancement 之前做。** |
| B13 | **Passive vs Active sensors** | 被动：测**反射的太阳光**（Landsat、Sentinel-2）；主动：**自己发信号再测回波**（Lidar、Radar、Sonar）。 |
| B14 | **Primary vs Secondary terrain attributes** | 一级**直接从 DEM 算**（elevation、slope、aspect、plan/profile curvature）；二级由**两个及以上一级属性组合**而来（solar radiation、moisture index、sediment transport index）。 |
| B15 | **General purpose vs Thematic maps** | 通用图（topographic / base map）用于**参考与承载图层**；专题图表达**单一属性的分布或多变量关系**（dot、isoline、choropleth、proportional、graduated）。 |
| B16 | **Editing vs Generalisation** | Editing 是**几何纠错与变换**（rubber sheeting、transformation、edge matching、line simplification、error corrections、reshaping）；Generalisation 是**制图抽象**（selection、simplification、exaggeration、combination、displacement、classification）。 |

### C. 复习策略类

- **不要背 generalisation 全表**——老师明说不要求全部记住，只需记住课上详讲过的几个。
- **IDW / Kriging 与 Tobler 定律权重更高**——这是老师在「不展开」的整体基调下唯一主动展开的分析主题。
- **GIS 定义、object/field view、vector/raster 优缺点**是老师点名「必须知道」的三块基础。
- **各周 quiz 是最好的模拟题**，其重要性被老师放在所有复习建议之首。

### D. 作业（assessment）易错点

- 写文字时**越界做因果解释**——只写 **main message**，不要解释成因。
- **忘记加 scale bar** —— 老师特别叮嘱「try and include a scale」。
- **图面过于 busy** —— 底图不是必需品，杂乱就去掉。
- **过度堆砌** —— 「low-level stuff is fine」，深度不是评分的唯一维度；地图要素齐全、布局得当更重要。
- **范围选错** —— 展示最有信息量的局部，而不是硬铺整个区域。

---

## 七、本周术语表

> **说明**：下表中标 **【本周】** 的是本次复习课上直接出现并解释的术语（全部来自 Week 10 讲义或转写）；标 **【全课汇总 📎】** 的条目为本周复习课**仅提及名称而未在本周展开定义**、或由本笔记补充定义的术语，其定义部分属于背景补充。本表**没有**加入本周材料完全未出现的术语。

### 1. GIS 基础与数据结构【本周】

| 英文 | 中文 | 要点 |
|---|---|---|
| Geographical Information System (GIS) | 地理信息系统 | 处理并管理空间数据的计算机化系统 |
| Geodatabase | 地理数据库 | GIS 中存储与管理空间数据的数据库 |
| Spatial data input / manipulation / analysis / output | 空间数据输入 / 操作 / 分析 / 输出 | GIS 的四大功能组件 |
| Object view | 对象视角 | 事物为离散实体、有边界；对应 vector |
| Field view | 场视角 | 连续表面、处处有值；对应 raster |
| Vector data | 矢量数据 | point / line / polygon |
| Raster data | 栅格数据 | grid of cells，每格一个值 |
| Topology | 拓扑（关系） | 对象之间的空间关系；缩放时相对位置与尺度保持不变 |
| Data structure | 数据结构 | GIS 处理某类数据必须遵守的一套规则 |
| Digitising | 数字化 | 矢量数据采集方式之一 |
| Field surveying | 野外测量 | 矢量数据采集方式之一 |
| Photogrammetry | 摄影测量 | 矢量数据采集方式之一 |
| Crowdsourcing | 众包 | 矢量与栅格均可用的采集方式 |
| Rasterisation | 栅格化 | vector → raster |
| Vectorisation | 矢量化 | raster → vector |

### 2. 坐标、基准与定位【本周】

| 英文 | 中文 | 要点 |
|---|---|---|
| Georeference / Georeferencing | 地理参照 / 地理配准 | 把数据定位到地球表面 |
| Oblate spheroid | 扁椭球 | 两极略扁的地球形状模型 |
| WGS84 | 世界大地坐标系 1984 | 目前最常用的球面参考模型 |
| Geoid | 大地水准面 | 地球重力场在平均海平面处的等位面 |
| Local datum | 局部基准 | 顾及区域差异，如 NAD27、OSGB36 |
| NAD27 | 北美基准 1927 | 北美所用局部基准 |
| OSGB36 | 英国大地基准 1936 | 英国 Ordnance Survey 所用 |
| Geographical coordinate system | 地理坐标系 | 球面坐标（latitude / longitude，单位度） |
| Projected coordinate system | 投影坐标系 | 球面→二维平面，(x, y) 格网 |
| UTM | 通用横轴墨卡托 | 投影坐标系示例 |
| British National Grid | 英国国家格网 | 投影坐标系示例 |
| GNSS | 全球导航卫星系统 | 卫星星座；全球覆盖需 18–30 颗 |
| GPS / GLONASS / Galileo / BeiDou | 美/俄/欧/中四大 GNSS | 四大在运行系统 |
| Latitude / Longitude / Elevation | 纬度 / 经度 / 高程 | 位置三要素 |

### 3. 空间分析与空间统计【本周】

| 英文 | 中文 | 要点 |
|---|---|---|
| Spatial query | 空间查询 | 基于属性与位置从 geodatabase 中筛选数据 |
| Spatial operations | 空间操作 | intersection、containment、distance calculations 等 |
| Spatial interpolation | 空间插值 | 由已知点值估计未知位置的值 |
| Inverse Distance Weighting (IDW) | 反距离加权 | 确定性方法，只给插值值 |
| Kriging | 克里金 | 地统计方法，给插值值 + 概率 |
| Prediction surface | 预测面 | 插值得到的连续面 |
| Tobler's first law of geography | 托布勒地理学第一定律 | 万物相关，近者更相关 |
| Spatial autocorrelation | 空间自相关 | 邻近观测之间相似性的度量 |
| Clustered / Dispersed / Random | 聚集 / 离散 / 随机 | 三种空间格局 |
| Nearest neighbour | 最近邻分析 | 仅用位置，输出 −1~+1 的数值 |
| Moran's I (local / global) | 莫兰指数 | 用要素值 + 位置，识别 clusters 与 outliers |
| Getis-Ord Gi\* | 热点分析统计量 | 识别显著的 hot spots 与 cold spots |
| Kernel density estimation (KDE) | 核密度估计 | 生成平滑密度面（heat map） |
| Hot spot / Cold spot | 热点 / 冷点 | 高值 / 低值的显著聚集 |
| Null hypothesis / Alternate hypothesis | 零假设 / 备择假设 | H₀：随机；H₁：聚集或离散 |

### 4. 遥感【本周】

| 英文 | 中文 | 要点 |
|---|---|---|
| Remote sensing | 遥感 | 非接触式的远距离环境数据采集 |
| Electromagnetic energy flux | 电磁能通量 | 遥感所记录的物理量 |
| Passive sensor | 被动传感器 | 测反射的太阳光（Landsat、Sentinel-2） |
| Active sensor | 主动传感器 | 自发信号测回波（Lidar、Radar、Sonar） |
| Spectral reflectance | 光谱反射率 | 反射率随波长变化的曲线 |
| Multispectral image | 多光谱影像 | 多个波长波段同时成像 |
| Spectral resolution | 光谱分辨率 | 波段的波长宽度 |
| Radiometric resolution / Pixel depth | 辐射分辨率 / 像元位深 | 每像元取值个数（8-bit → 0–255） |
| Spatial resolution | 空间分辨率 | 像元代表的地面面积 |
| Digital number | 数字量测值 | 栅格单元中存储的数值 |
| NIR (near-infrared) | 近红外 | 植被强反射波段 |
| SWIR (short-wave infrared) | 短波红外 | Sentinel 波段之一 |
| Landsat / Sentinel-2 | 陆地卫星 / 哨兵二号 | 两类常用多光谱卫星 |
| Geometric correction | 几何校正 | 消除几何变形、georeferencing 到投影坐标系 |
| Radiometric correction | 辐射校正 | 传感器响应、观测几何、大气效应、场景光照、radiance 还原 |
| Image enhancement / Band combination | 影像增强 / 波段组合 | 在各类校正**之后**进行 |

### 5. 地形分析【本周】

| 英文 | 中文 | 要点 |
|---|---|---|
| DEM (Digital Elevation Model) | 数字高程模型 | 栅格形式的连续高程面 |
| TIN (Triangulated Irregular Network) | 不规则三角网 | 矢量形式的连续高程面 |
| Contours / Spot heights | 等高线 / 高程点 | 高程的其他表示方式 |
| Primary terrain attributes | 一级地形属性 | elevation、slope、aspect、plan / profile curvature |
| Secondary terrain attributes | 二级地形属性 | solar radiation、moisture index、sediment transport index |
| Slope / Aspect | 坡度 / 坡向 | 一级属性 |
| Plan curvature / Profile curvature | 平面曲率 / 剖面曲率 | 一级属性 |
| Catchment hydrology | 流域水文 | 地形分析的应用 |
| Watershed / Pour point / Divide | 流域（集水区）/ 倾泻点 / 分水线 | 流域分析中的关键对象 |
| Line of sight / Viewshed | 通视线 / 视域 | 地形分析的应用 |
| Solar radiation mapping | 太阳辐射制图 | 地形分析的应用（有对应 practical） |

### 6. 制图学与三维【本周】

| 英文 | 中文 | 要点 |
|---|---|---|
| Map scale | 地图比例尺 | 大比例尺 = 小范围 + 更多细节 |
| Cartographic editing | 制图编辑 | rubber sheeting、transformation、edge matching 等 |
| Rubber sheeting | 橡皮拉伸 | 消除几何变形 |
| Edge matching | 接边匹配 | 跨图层的要素匹配 |
| Generalisation / Cartographic abstraction | 概化 / 制图抽象 | selection、simplification、exaggeration、combination、displacement、classification |
| General purpose map | 通用地图 | topographic map、base map |
| Topographic map | 地形图 | 综合参考信息 |
| Base map | 底图 | 供叠加其他图层的基础 |
| Thematic map | 专题地图 | dot、isoline、choropleth、proportional、graduated |
| Choropleth map | 分级统计图 | 专题图类型之一 |
| Isoline map | 等值线图 | 专题图类型之一 |
| Map design: Selection / Classification / Symbolisation / Layout design | 地图设计四步 | 选择 / 分类 / 符号化 / 版面设计 |
| Map elements | 地图要素 | Title、North arrow、Map body、Legend、Inset、Scale bar、Credits、Neatline、Other text |
| Neatline | 图廓线 | 地图要素之一 |
| Inset | 插图 | 地图要素之一 |
| Animated mapping | 动态制图 | 表现 time / space / attributes 的变化 |
| 2.5D | 二点五维 | z 仅代表一个属性值，无体积 |
| True 3D | 真三维 | 含体积，需 x, y, z |
| Digital twin | 数字孪生 | 真三维应用示例（城市建模） |
| Pixel | 像元 / 像素 | 2D 栅格最小单元 |
| Voxel | 体元 / 体素 | 三维像素，由 x, y, z 范围界定的小立方体 |

### 7. 软件与课程管理【本周】

| 英文 | 中文 | 要点 |
|---|---|---|
| **ArcGIS Pro** | （软件名，保留英文） | 本课全部 practical 的主线软件 |
| **QGIS** | （软件名，保留英文） | 老师提到的可迁移替代 GIS 软件 |
| **Canvas** | （平台名，保留英文） | 作业提交平台 |
| **SEATS code** | （考勤码，保留英文） | 课堂签到码 |
| Fly-through | 三维飞行浏览 | 学生在作业中使用的三维展示方式 |
| Multiple choice / Multiple answer question | 单选题 / 多选题 | 考试两大题型 |
| Partial credit | 部分给分 | 多选题按选中的正确答案逐个给分 |
| Negative marking | 负分制 | 每选中一个错误答案扣一分（每题最低 0 分） |
| Closed book | 闭卷 | 本次考试形式 |
| Invigilated | 有监考的 | 本次考试形式 |

### 8. 【全课汇总 📎】——本周仅提及名称、定义为背景补充

| 英文 | 中文 | 说明 |
|---|---|---|
| Lidar | 激光雷达 | 📎 本周仅作为 active sensor 与 vector 采集手段被点名，未在本周展开定义 |
| Radar | 雷达 | 📎 同上 |
| Sonar | 声呐 | 📎 同上 |
| UAV | 无人机 | 📎 本周仅在遥感平台清单中被点名 |
| Bathymetry | 水深测量 | 📎 本周仅出现在 Sentinel 波段用途表中 |
| Aerosols | 气溶胶 | 📎 同上 |
| Cirrus clouds | 卷云 | 📎 同上 |
| Moisture index | 湿度指数 | 📎 本周仅作为二级地形属性举例出现 |
| Sediment transport index | 泥沙输移指数 | 📎 同上 |
| p-value | 概率值 / 显著性水平 | 📎 本周仅在课后答疑中被学生提到（用于 hot spot 分析结果的呈现） |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `EART29102 - 27-Apr-transcript.md`，空间自相关一段 | 「if you've got **negative** spatial autocorrelation, it means things are either very similar or they're **clustered** together. If you've got things which are as far apart from each other as possible, then they are completely **dispersed** and that's **positive** spatial autocorrelation.」 | **正/负空间自相关与聚集/离散的对应关系说反了**。这与同一份讲义中 `Negative ----- spatial autocorrelation ----- Positive` 的标度含义、以及空间统计的标准定义相冲突。 | 标准定义：**正空间自相关（positive）= clustered（相似值聚集在一起）；负空间自相关（negative）= dispersed（相似值彼此远离/棋盘格式分布）；0 = random**。老师同一段中「随机时空间自相关为 0」的说法正确。**考试请按标准定义作答。** |
| `EART29102 - 27-Apr-transcript.md`，辐射分辨率一段 | 「**12-bit** resolution allows you to have something like about **16.8 million shades of colour**」 | **位深与颜色数对应错误**。12-bit 每通道只有 2¹² = 4,096 级；约 1,670 万（16.7 million）种颜色对应的是 **24-bit（每通道 8-bit × RGB 三通道）**。 | 应为：**24-bit ≈ 16.7 million colours**。12-bit 指每通道 4,096 级灰度。（老师随后也把 8/12/24-bit 并列，可见此处为口误。） |
| `Lecture 10 Course review_handout.md`，Digital multispectral images 一页 | 「8-bit = 2 8 -1 = 0 -255.」（即 `2⁸ − 1 = 0–255`） | **写法歧义**：`2⁸ − 1 = 255` 是**最大值**，而不是「取值个数」。8 位的取值**个数**为 2⁸ = 256 个。 | 严谨写法：**8-bit ⇒ 2⁸ = 256 个取值，范围 0 至 2⁸ − 1 = 255**。 |
| 讲义 GNSS 一页 vs 转写 GNSS 一段 | 讲义：「a constellation requires **18 to 30** satellites」；转写：「somewhere between about **20 and 30** satellites」 | **数值前后不一致**（讲义 18–30，口述 20–30）。 | 以**讲义为准：18 to 30 satellites**。口述的「about 20」应为临场近似表述。 |
| `(EART29102) Geospatial Techniques.md`（官方大纲）「Teaching and learning methods」与「Assessment methods」 | 「**There is no exam for this module**, with assessment taking the form of on-line tests and an individual report.」；Assessment methods 表：Set exercise 50% / Other 50% | 与本周讲义及老师口述**严重矛盾**：本周明确说明**有一场受监考的线上考试，占最终成绩 70%**（讲义 "EART29102 Exam" 页 + 转写；封面标注 08 June 2026, 14:00–15:30, 80 marks）。此外大纲 Syllabus 所列周次内容（Geodesy、Photogrammetry、Lidar、Sonar、Volcanic Plume Modelling、UAV 等）与实际授课内容也不符。 | **以本周讲义与课堂口述为准：exam 占 70%，1 小时 30 分钟，50 题 / 80 分，closed book、invigilated、禁 AI、禁计算器。** 官方大纲仅可作课程总体背景参考，不可用于推断周次内容或评分权重。 |
| `EART29102 - 27-Apr-transcript.md`（自动转写全篇） | 「crigging」、「Moran's **eye**」、「**Gettysord** Gi star」、「inverse **distant** weight」、「Pete **Grinrod**」 | **自动语音识别（ASR）转写造成的拼写错误**，非知识性错误。 | 正确写法：**Kriging**、**Moran's I**、**Getis-Ord Gi\***、**Inverse Distance Weighting (IDW)**；人名以讲义/官方名单为准。 |
| `Lecture 10 Course review_handout.md`，Animated mapping 之后 | （讲义在此处缺页 / 版本不一致） | 老师课上当场发现：「**Missing a page. Are you missing a page on yours?** ... **it looks like I've got an earlier version. Let's skip to this one.**」 | **本次课所用讲义为较早版本，Animated mapping 与 2.5D/3D 之间缺失一页内容，材料本身未说明缺失内容是什么。** 复习时如发现该处衔接突兀，属材料本身问题。 |
| `EART29102 - 27-Apr-transcript.md`，开场行政信息 | 「I think it's **2 o'clock on the 30th, which is Thursday**, is that right?」 | 老师本人对**作业截止日期不确定**（用了「I think」并当场向学生求证），材料未给出确认结果。 | **截止时间请以 Canvas 上的正式公告为准**，不要依赖此处口述。本笔记不作推断。 |

---

**未在本笔记中出现的信息一律为材料未说明**。特别是：考试的具体题目分布（各主题占多少题）、practice exam questions 的具体题目内容与发布位置、exam timetable 的具体考场，**材料均未说明**。
