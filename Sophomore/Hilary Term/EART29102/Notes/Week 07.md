# EART29102 Geospatial Techniques — Week 07 学习笔记

> 授课日：16-Mar（Hilary Term, Week 07）
> 材料：`Lecture 7 - Terrain Analysis`（讲义，含低质量 OCR 段）＋ `EART29102 - 16-Mar-transcript`（课堂录音转写，6,563 词）＋ `Practical 7 - Wind turbines`（ArcGIS Pro 实操教程）
> 本周主题：**地形分析（Terrain Analysis）**；实习：**风力发电机选址（Locating the optimal positions of wind turbines）**

---

## 一、本周主题

### 1.1 本周在全课骨架中的位置

本课程的实际骨架是：**基础段**（W01 GIS 导论 → W02 空间数据与数据管理 → W03 数据输入与操作）→ **分析段**（W04 空间分析 → W05 空间统计）→ **专题段**（W06 遥感 → **W07 地形分析** → W08 空间可视化 → W09 三维技术）→ W10 课程回顾。

**本周是专题段的第二类。** 这个位置很关键：

- **W06 遥感**解决的是「数据从哪来」——影像、波段、分辨率、传感器。
- **W07 地形分析**解决的是「拿到高程数据之后能算出什么」。老师在转写里把 W06 直接接了过来：

  > "often the kind of remote sensing data, hopefully most of these are familiar with you, you're familiar with now after last week's lecture ... so things like, you know, photogrammetry, radar altimetry, InSAR, Lidar and all of these data sets. Most of them are in the form already of a DEM."

  也就是说：**W06 的各种遥感手段，最后大多以 DEM 的形式落地；W07 就是把这个 DEM 榨干。**
- **W08 空间可视化**接着讲怎么把结果做成能给人看的图，而 W08 的 practical（Solar radiation mapping and map layout）正好接着本周讲义最后一节的太阳辐射制图——老师在课末明说了：

  > "the practical you're doing next week, we'll be looking at working out solar radiation ... the amount of solar energy that can be generated over an area of Manchester."

### 1.2 讲义列出的六条内容主线（原文）

讲义 "Lecture content" 页给了六条：

1. What is terrain analysis?（什么是地形分析）
2. Data sources, types and formats.（数据来源、类型与格式）
3. Slope, aspect, curvature and topographic profiles.（坡度、坡向、曲率与地形剖面）
4. Catchment and hydrology.（集水区与水文）
5. Line of sight and viewsheds.（视线与可视域）
6. Solar radiation mapping.（太阳辐射制图）

本笔记第二节按这六条展开。

### 1.3 与 W04 的衔接：从「叠加操作」到「真实选址问题」

这是本周最该想清楚的一条线索。

W04 教的是一堆**单独的空间操作**：buffer（缓冲区）、overlay（union / intersect / difference）、raster overlay / map algebra（地图代数）、reclassify（重分类）、merge、dissolve、spatial query（空间查询）。W04 的 practical 把它们分开练，但没有把它们串成一个**决策**。

W07 把这些工具第一次串成了一条**完整的多准则决策链**，而且是在真实业务场景里：

| W04 学的操作 | W07 practical 里承担的角色 |
|---|---|
| Select by Attributes（属性查询） | 从全英国县界里挑出 Cornwall；从全部道路里挑出 A、B 级路 |
| Select by Location（空间查询） | 用 Cornwall 县界把 6 个全英国图层「裁」到研究区 |
| Buffer（缓冲区） | 把「不能离道路 100 m 以内」这类**文字准则**变成**可叠加的几何图形** |
| Merge（合并） | 把 5 个缓冲区并成一个「禁建区」图层 `No_Build` |
| Difference / Erase（差集） | 用县界减去禁建区，得到「可建区」`Build` |
| Reclassify / Overlay 的思想 | 本周用的是**布尔排除**版本（见 §5.16 的重要说明） |

而 W07 自己新增的那一半是**地形**：DEM → hillshade 显示 → viewshed（可视域），用来回答「建了之后哪些村镇看得见」——这是纯 W04 工具做不到的，必须有高程数据。

**一句话概括本周：W04 给了你锤子，W07 第一次让你盖房子，而且房子的地基是 DEM。**

### 1.4 本周作业与资源（讲义 Homework 页原文）

- ➢ Read **Chapter 8** of course textbook: **Terrain Analysis**.
- ➢ Take the **quiz** to test your basic understanding（在 **Canvas** 上）。
- Further resources：
  - ESRI Training: *Terrain Analysis Using ArcGIS Pro*
  - Esri Storymap: *Terrain Analysis Case study: Rauriser Ache Catchment*

> 📎 背景补充：课程指定教科书是大纲里的 Liu & Mason, *Image Processing and GIS for Remote Sensing*。老师说的「Chapter 8: Terrain Analysis」即指该书对应章节。
>
> 📎 背景补充（同时也是勘误）：老师口头说这个 storymap 讲的是 "a particular catchment area **in Switzerland**"，但讲义写的是 **Rauriser Ache**——该河位于**奥地利** Salzburg 州的 Rauris 谷，不在瑞士。详见文末勘误表。

---

## 二、核心概念

### 2.1 什么是地形分析（Terrain analysis）

讲义用了一个**复杂度层级**开场：

> **Complexity: spheroid < geoid < land surface (terrain).**

老师把这三层的含义讲得比讲义清楚（转写）：

1. **Spheroid（椭球体）**——纯几何模型，是 W01–W02 讲坐标系统时用的那个数学面。
2. **Geoid（大地水准面）**——引入重力，是重力的**等位面（equipotential surface）**，通常取在平均海平面。
3. **Land surface / terrain（真实地表）**——最真实、最复杂的那一层。

> "we started off sort of talking about how the earth is essentially a spheroidal shape ... then the next sort of layer of realism was to consider it as a geoid which brings in gravity, the equipotential surface of gravity usually taken at sea level, and then having something that's much more realistic is the actual land surface."

**地形分析的定义（讲义原文）**：

> Using topographic data to derive terrain features:
> - the **morphology** of terrain surface.（地表形态）
> - the **influence of terrain on environmental processes**.（地形对环境过程的影响）

讲义在 Applications 页把这句话展开成一句更好背的话：

> Terrain analysis is about **how the shape of the land influences or reflects natural processes, hazards, ecosystems, and human influences.**

### 2.2 地形的四种表达方式

讲义列出四种，并强调它们是「_different ways of representing the same continuous surface at the same scale and extent_」（**同一个连续曲面、同一尺度同一范围的不同表达**）：

| 表达方式 | 英文 | 数据模型 | 特点 |
|---|---|---|---|
| 等高线 | **Contours** | 矢量（线） | 传统地图最熟悉的形式 |
| 高程点 | **Spot heights** | 矢量（点） | 离散控制点 |
| 数字高程模型 | **DEM** | **栅格（raster）** | 规则格网，每个 cell 一个高程值 |
| 不规则三角网 | **TIN** | **矢量（vector）** | 三角面拼接 |

老师在转写里还补了第五种：**point cloud（点云）**，典型来源是 LiDAR。

> "we could use a point cloud there of LIDAR data. On maps we were very familiar with the use of contours. But we can also use raster data ... or we can use TINs."

**本周重点是 raster（DEM）和 TIN 两种**，老师明说了：「we'll talk primarily about raster and TIN data in today's lecture」。

### 2.3 DEM / DTM / DSM 的区别

> 📎 背景补充：**讲义与转写全程只用 "DEM" 一个词，没有区分 DTM 与 DSM。** 但这三个词在实际工作与考试里必须分清，以下整段为补充内容。

| 术语 | 全称 | 含义 | 树冠 / 建筑 |
|---|---|---|---|
| **DSM** | Digital Surface Model（数字表面模型） | 记录**最先被传感器打到的那个面**的高程 | **包含**树冠、建筑、桥梁等地物 |
| **DTM** | Digital Terrain Model（数字地形模型） | 记录**裸地面（bare earth）**的高程 | **不包含**地物，已被滤除 |
| **DEM** | Digital Elevation Model（数字高程模型） | **泛称**，通常在实践中等同于 DTM，但严格说只表示「高程的数字模型」 | 取决于具体产品 |

**为什么必须分清：**

- 做**坡度**：用 DSM 会把树冠边缘、房屋墙面当成陡坡，坡度会被严重高估（详见 §6.1）。
- 做**水文（fill / flow direction）**：用 DSM 会让建筑物变成「山」、让屋顶变成「洼地」，河网彻底错乱。
- 做**可视域**：这时反而**可能需要 DSM**——因为树林和房子确实会挡住视线。本周 practical 用的是 **OS Terrain 5**（属 DTM 性质），所以算出来的 viewshed 是**保守偏大**的（没有把树和房子的遮挡算进去）。
- 讲义提到的 **hemispherical viewshed** 明确写了「(DTM)」，是全篇唯一一处出现 DTM 字样。

### 2.4 主要数据来源（讲义原文五条）

> **Main digital terrain data sources**
> - Ground surveys.（地面测量）
> - Photogrammetry.（摄影测量）
> - Radar altimetry.（雷达测高）
> - Interferometric synthetic aperture radar (**InSAR**).（干涉合成孔径雷达）
> - Airborne laser scanning (**LiDAR**).（机载激光扫描）
>
> Most of these are in the form of, or can be readily transformed to **DEM**.

**老师对 ground survey 的两个作用讲得比讲义细**（这是讲义上没有的）：

> "ground surveys are important for **both collecting data and also for verifying** the data that we have."

1. **验证（validate）**：遥感数据要经过解译，解译就有主观性，必须下野外核对。
2. **提高分辨率（higher spatial resolution）**：野外实测通常比遥感精细得多，可以做**多尺度（multi-scale）**应用——一小块高精度 + 大范围概略数据配合使用。

**关于空间分辨率，老师专门停下来强调了一段**（讲义无）：

> "if we are using digital elevation models, one of the factors we have to consider is the **spatial resolution** of that data ... nowadays we can go down to grid sizes or cell sizes within the grid that are down to **a metre** in terms of resolution ... it very much depends on what the application is and what the scale of the application is as to that level of resolution that we need, but **it's something we always need to consider**."

> 📎 背景补充：常见公开 DEM 数据集与其分辨率（材料未列，但选址题、独立项目里经常要选数据源）：
>
> | 数据集 | 覆盖 | 名义分辨率 | 性质 |
> |---|---|---|---|
> | **SRTM**（Shuttle Radar Topography Mission） | 全球 60°N–56°S | 30 m（SRTM1）／90 m（SRTM3） | 雷达干涉，近似 DSM |
> | **ASTER GDEM** | 全球 83°N–83°S | 30 m | 光学立体像对，噪声较大 |
> | **Copernicus DEM** | 全球 | 30 m / 10 m（EU-DEM 区域） | DSM |
> | **OS Terrain 5** | 英国 | **5 m 格网** | 本周 practical 用的就是它 |
> | **OS Terrain 50** | 英国 | 50 m 格网 | 免费开放数据 |
> | **LiDAR DTM/DSM（EA）** | 英格兰大部 | 0.25–2 m | 精度最高 |
>
> 本周 practical 说 OS Terrain 5「不是公开数据、ArcGIS Online 上没有」，需要从 **Digimap** 下载——Digimap 是英国高校的 OS 数据授权平台，曼大学生可用校内账号登录。

### 2.5 TIN 与断裂线（Breaklines）

**TIN 定义（讲义）**：

> ➢ TIN - using **contiguous, non-overlapping triangles** linking **3 adjacent elevation points**.（相邻、不重叠的三角形，每个三角形连接 3 个相邻高程点）
> ➢ **Independent of data scale** = flexible in level of detail.（与数据尺度无关 = 细节层次灵活）
> ➢ **Efficient in terms of data storage**.（存储高效）
> ➢ TIN **less useful than DEM when surface is flat**（平坦地表如高原、沙漠时不如 DEM 好用）

老师把「尺度无关」解释得很直观：

> "where you have a lot of complex surface changes, so surface roughness, on the land surface, you can represent that by using a lot of **small** triangles. On the other hand, where you have relatively flat areas you need only fewer triangles, a much **larger** size."

**TIN 的缺点（老师讲得比讲义狠）**：

> "once you get to a very flat surface like a desert or an upland plateau, you begin to **lose some of the subtle variation** using a TIN. Tends to **even out** things more than using a fixed cell size ... and the surface becomes a little bit more **unrealistic looking** as well where you have those large connected triangles."

**Breakline（断裂线）定义（讲义斜体原文）**：

> _A breakline is a line feature with elevation values that **forces the TIN surface to follow a specific shape**. They **prevent the interpolation from smoothing over important terrain edges**._

| 类型 | 英文 | 是否改变局部坡度 | 讲义给的作用 | 老师给的例子 |
|---|---|---|---|---|
| 硬断裂线 | **Hard breakline** | **是**——代表坡度的**不连续（discontinuity in slope）** | 「keep water inside channels」「preserve scarps（保住陡坎）」 | **湖岸线**——陆面与水面之间必须有一个突变，三角形不能跨过去把它抹平 |
| 软断裂线 | **Soft breakline** | **否**——不改变局部坡度 | 「guides the flow along the deepest parts of channels（沿深泓线导流）」「maintain natural curvature（保持自然曲率）」 | **道路**——路本身不一定造成坡度突变，但你仍然希望它在 TIN 里被表示出来 |

老师最后一句总结值得记：

> "breaklines are something that need to be incorporated into a TIN, **which you don't have to worry about with a digital elevation model**."

（DEM 是规则格网，没有三角剖分这一步，也就没有断裂线问题。）

### 2.6 一阶（primary）与二阶（secondary）地形属性

这是本周的**组织框架**，讲义与转写反复强调。

**Primary terrain attributes（一阶／基本地形属性）**——直接从高程数据算出来：

> ➢ **Elevation, slope, aspect, plan and profile curvature** are primary terrain attributes.

**Secondary / compound terrain attributes（二阶／复合属性）**——由两个或以上一阶属性组合算出：

> ➢ Secondary attributes are **computed from two or more primary attributes**.
> ➢ Quantify the role played by topography in **redistributing water** in the landscape and in modifying the amount of **solar radiation** received at the surface.
> ➢ These attributes affect **soil characteristics**, distribution and abundance of **soil water**, susceptibility of landscapes to **erosion by water**, and the distribution and abundance of **flora and fauna**.

讲义把水文量归入「derived (hydrological) characteristics」：

> ➢ **Flow direction, flow accumulation, flow length, flow order, drainage network and catchment area** are derived (hydrological) characteristics of a terrain surface.

**一个容易被忽略但会考的点（讲义原文）**：

> ➢ In GIS, they are mainly derived from **DEM or TIN** and represented in **raster layers**.

老师补了一句更明确的：

> "even though we may start off with a vector-based TIN, the secondary attributes that we get will usually be in the form of a **raster**."

**→ 无论输入是 DEM 还是 TIN，地形分析的输出基本都是栅格。**

老师还点明了「为什么要二阶属性」：

> "those secondary attributes are really what we're trying to get at. We're trying to get at information that's telling us something **important about the environment**."

### 2.7 坡度（Slope）

**定义（讲义 OCR 页 + 老师口述）**：坡度是**最大坡降方向上的角度**，由 **rise（高差）/ run（水平距离）** 决定。

> "The maximum angle is given by the change in height or **rise** divided by the change in distance or the **run**, and we can represent that either as a **percentage** or as an **angle in degrees**."

两种表达（公式见 §3.1）：

- **Percent slope（百分比坡度）**：θ = 100 × (h/d) %
- **Degree slope（度数坡度）**：θ = arctan(h/d)（度）

**Slope map 的判读（老师现场读图）**：讲义那张坡度图约 20 km 见方，按坡度角分色，**绿色 = 相对平坦，其他色 = 陡**。老师强调：「that's simply just based on the **elevation data** that's contained within the DEM」——只用高程就能算出来。

### 2.8 坡向（Aspect）

**定义**：坡面朝向，以**方位角（azimuth，罗盘方位）**表示。

> "the orientation of the slope, given as an **azimuth**, so a compass bearing."

老师读图时给了南北判读：

> "the ones in blue and green here generally **south facing** and the ones in red and purple colours are **north facing**."

> 📎 背景补充（材料未讲，但极重要）：**ArcGIS 的 Aspect 取值约定**
>
> - 取值范围 **0°–360°，正北为 0°，顺时针增加**：N = 0°/360°，E = 90°，S = 180°，W = 270°。
> - **平坦格网（flat cell）赋值 −1**，表示无坡向。
> - 通常按 8 个（或 9 个含 Flat）方位分类符号化。

> 📎 背景补充：**坡向是圆形数据（circular data）**——这是本周最容易出错的概念（详见 §6.1）。355° 与 5° 只差 10°，但算术平均是 180°（正南），完全错误。正确做法是**向量平均**：把每个角度拆成 sin 与 cos 分量分别求和，再用 atan2 还原。W05 讲的普通描述统计量（均值、标准差）**不能直接用在 aspect 上**。

### 2.9 地形剖面（Terrain profile）

**做法**：在 DEM/TIN 上画一条剖面线 A–B，输出一张「距离 vs 高程」的二维图。

老师点出这张图能同时读出三件事：

> "Not only do we get elevation, we also get the **slope**, and not only do we get the slope, we also get **curvature**. So the landscape is not made up of this sort of zigzag pattern, it's **curved** on the surface ... you've got sort of **convex** shapes here and you've got **concave upward** facing shapes here."

**这句话是从 slope 过渡到 curvature 的桥梁**：剖面线不是折线，是曲线，曲线的弯曲程度就是曲率。

> 📎 背景补充：剖面图上的 **vertical exaggeration（垂直放大倍数）**（讲义 OCR 页显示为 "Vertical exaggeration 3.0 X"）是显示参数，不是地形属性。放大 3 倍会让坡看起来陡得多，**读剖面图必须先看这个数**，否则会严重误判坡度。

### 2.10 曲率（Curvature）

**定义（讲义）**：

> Amount by which a surface **deviates from being flat**.（曲面偏离平面的程度）

**两种曲率（这是必考的一对）**：

| 曲率 | 英文定义（讲义原文） | 通俗理解 | 控制什么 |
|---|---|---|---|
| 剖面曲率 | **Profile curvature** is the rate of change of slope **in the direction of the maximum slope** | 顺着水流方向、沿坡的纵剖面弯不弯 | **流速的加速/减速** → 侵蚀 vs 沉积 |
| 平面曲率 | **Plan curvature** is the curvature **perpendicular to the direction of the maximum slope** | 横切坡向的横剖面弯不弯 | **流线的辐合（convergence）/ 辐散（divergence）** |

老师承认 plan curvature 的定义难记，给了替代记法：

> "plan curvature ... is quite hard to remember. I think it's easier just to think of it in terms of **convergence or divergence of flow**."

**符号约定（老师口述，讲义只有图）**：

对 **profile curvature**：

> "negative values represent **convex up**, positive values **concave up**, and **zero is flat**."

- **负值 = 上凸（convex up）** —— 山脊、坡肩，水流在此**加速**、以**侵蚀**为主
- **正值 = 上凹（concave up）** —— 坡脚、谷底，水流在此**减速**、以**沉积**为主
- **零 = 平直坡**

对 **plan curvature**，老师只说「we give these positive and negative values depending on the shape」，**没有给具体符号**。

> 📎 背景补充：Esri 传统 **Curvature** 工具的完整符号约定：
> - **Profile curvature**：负 = upwardly convex（上凸），正 = upwardly concave（上凹）——与老师讲的一致。
> - **Plan (planform) curvature**：**正 = sidewardly convex（侧向外凸）= 辐散**，**负 = sidewardly concave（侧向内凹）= 辐合**。
> - ⚠️ ArcGIS Pro 3.x 新增的 **Surface Parameters** 工具采用**地貌学惯例**，其 profile（normal slope line）curvature 的**正负号与旧 Curvature 工具相反**。跨工具比较结果时务必先确认用的是哪个工具。

**剖面曲率图的判读（老师现场读图，很值得记）**：

图为灰度显示，**亮色 = 高正值，暗色 = 高负值**。因此：

- 亮色的线状条带 → 正值 → **上凹** → **谷底 / 河道**
- 暗色的线状条带 → 负值 → **上凸** → **山脊线**

> "you can already begin to think that you're picking out **ridges, valleys or stream valleys** on this map depending on the shape of the surface."

**四个属性的分工（讲义黑体总结句，必背）**：

> **Slope** influences the overall **rate of movement downslope**, **aspect** determines the **direction of flow**, **profile curvature** affects the **flow acceleration and erosion/deposition rate**, and **plan curvature** affects the **convergence and divergence of flow**.

老师加了一句点睛：「**all of that is derived from just simply the elevation data**」。

### 2.11 集水区分析（Watershed analysis）

**Watershed 的朴素定义（老师）**：

> "a watershed is just a place where **water collects and is drained from**."

一个 watershed 由三部分构成（老师读图）：

1. **Boundary（边界）**——由 **ridge lines（分水岭/山脊线）**定义
2. **Drainage network（水系网）**
3. **Outlet / pour point（出水口/倾泻点）**——可能流入另一个流域、溪流、湖泊、湿地或大海

**讲义给的 pour point 定义**：

> A **pour point** in GIS is the specific point where water flows out of a catchment. It is the **lowest point on a watershed boundary** and the location where all upstream flow **converges and "pours"** into the next downstream area.

**Watershed analysis 能做什么（讲义七条）**：

> - Models the movement of water over the land surface.
> - **Track pollution sources** to locate potentially affected streams（e.g. agrochemicals 农药、outlet pipes from factories 工厂排污口）
> - **Estimate stream flow for ungauged areas**（估算无监测站区域的流量）
> - **Predict water quality**
> - Analyse historic and future **climate predictions**
> - Understand **sedimentation processes**
> - **Characterise landforms**

老师对第三条做了很实用的注解：

> "we can estimate the amount of stream flow over the whole area, so **we don't have to go out and install gauges** to monitor stream levels, we can actually estimate those using the model."

以及一句总的态度：

> "this is based **solely on remote sensing data**. So we're not actually going out into the field and making any measurements, apart from just perhaps verifying some of the predictions."

**⚠️ 数据模型选择**：老师明确说：

> "we tend to use a **raster** based data set, so we use a digital elevation model based on a grid of cells. **Don't tend to use triangulated irregular networks** for this kind of application."

**→ 水文分析用 DEM，不用 TIN。这是一个明确的考点。**

### 2.12 水文分析四步链：Fill → Flow Direction → Flow Accumulation → Stream / Watershed

#### 第一步：填洼（Fill）／水文调整（Hydrological conditioning）

**Sink（洼地）定义（讲义）**：

> Areas which are **pits, surrounded by higher elevation values**.
> Whilst these can occur naturally, often they result from **errors in the input DEM**.
> **Bridges, roads, quarries, sinkholes or misrepresentation of narrow-sided channels** can all result in sinks.

**为什么必须先填（老师）**：

> "the problem with these sinks is that they **prevent water from flowing over the landscape** ... the water, if it's trying to flow downslope, suddenly it will hit a sink, go down into the sink, and then it will be difficult to get that water to flow any further."

**不填的后果（老师读那张对比图）**：含 sink 的 DEM 直接做水文建模，得到的河网「**doesn't look, or is not at all realistic**」——河道断裂、走向诡异。填洼后「**looks much more realistic**」。

**结论（老师原话）**：

> "It's an important step, might seem like a trivial one, but **it really does affect the output of your model**."

> 📎 背景补充：ArcGIS Pro 里的工具是 **Fill**（Spatial Analyst Tools → Hydrology → Fill）。关键可选参数是 **Z limit**——只填深度小于该值的洼地，用来保护真实存在的深洼（如石灰岩溶蚀漏斗 sinkhole、火山口、采石场）。不设 Z limit 则**全部**填平。材料未提到这个参数。

#### 第二步：流向（Flow Direction）

**原理（老师，讲义只有图）**：

> "water tends to flow **down the steepest slope**, doesn't it? So we look at the values surrounding that cell and determine which direction is the angle of **steepest slope**."

老师用一个 3×3 的小例子手算了一遍（完整算例见 §3.3）。核心是：**正交邻居的距离是 1 个 cell size，对角邻居的距离是 √2 个 cell size**，所以对角方向的坡度必须除以 √2，不能直接比高差。

> 📎 背景补充：**这个算法就是 D8（Deterministic 8-node / eight-direction）算法**。**讲义和转写全程都没有说出 "D8" 这个名字**，但描述的正是 D8：每个格网的水流只能流向 8 个邻居中的**唯一一个**（最陡的那个），不能分流。编码方式见 §3.3。
>
> 📎 D8 的已知缺陷：在平缓坡面上，水流被迫走 8 个固定方向之一，会产生**平行的锯齿状假河道（parallel flow artefacts）**。改进算法有 **D∞（D-infinity）**、**MFD（Multiple Flow Direction，多流向）**等，ArcGIS Pro 的 Flow Direction 工具的 `Flow direction type` 参数就提供 D8 / MFD / DINF 三个选项。材料未涉及。

#### 第三步：流量累积（Flow Accumulation）

**定义（讲义 + 老师）**：每个格网记录**有多少个上游格网的水最终流经它**。

> "essentially it shows the **number of upstream cells that flow into each cell**."

**判读规则（讲义黑体）**：

> _**High values = stream channels; zero values = ridgelines**_

老师读图：白色（高值）= 大量格网汇入 = **潜在河道**；暗色线（低值/零）= 没有上游汇入 = **山脊线**。

> "it's **reflecting the topography**, and you're already beginning to see how you could maybe get some stream channels from that."

累加算法的手工演示见 §3.4。

#### 第四步：阈值提取河网（Threshold）与集水区（Watershed）

**Threshold 定义（讲义）**：

> ➢ **Threshold values** are **numerical cut-offs** used to decide **where surface runoff becomes a stream**. Thresholds convert **continuous** flow accumulation into a **discrete** drainage network.

讲义给了两个对照：**1000 cells** 与 **7000 cells**。

**阈值的影响（老师）**：

> "if you **lower** your threshold you're going to **increase** your stream network, the complexity of your stream network, you can have a higher **stream order** value. Compared to if you **increase** your threshold, then you're only going to see the sort of **major channels**."

**⚠️ 老师明确指出这是需要野外验证的地方**：

> "this is one of the areas where you may need to go and do a **ground survey to verify** some of these decisions that you need to make."

**划分集水区**：在河网上选定若干 **pour point**，围绕每条（或每组）河道画出边界，就得到一个或多个 watershed。老师现场把两个 watershed（紫色、绿色）与前一张图上的两条河道一一对应上了。

> 📎 背景补充：ArcGIS Pro 的完整水文工具链（Spatial Analyst Tools → **Hydrology** 工具集）：
> `Fill` → `Flow Direction` → `Flow Accumulation` → `Con`（用阈值二值化，如 `Con("flowacc" > 1000, 1)`）→ `Stream Link` → `Stream Order`（Strahler / Shreve）→ `Stream to Feature`（转成矢量线）；
> 并行分支：`Snap Pour Point`（把人工点吸附到高流量累积格网上）→ `Watershed`（生成集水区）→ `Basin`（自动划分全图流域）。
> **`Snap Pour Point` 这一步材料没提但极关键**：手点的出水口若差一两个格网落到河道外，`Watershed` 会输出一个只有几个格网的荒谬结果。

### 2.13 地形湿度指数（TWI）与多准则建模案例

老师用了一个 2025 年的论文案例讲**多准则（multi-criteria）滑坡风险建模**：

- 研究区：**Utcubamba River Basin, Peru**（秘鲁 Utcubamba 河流域）
- 出处：**Rivera et al. (2025)**，https://doi.org/10.3390/app15179423
- 输出：**Landslide risk zoning and mapping（滑坡风险分区制图）**，分级 very low → very high

**用到的准则图层（老师逐个念的）**：slope（坡度）、geology（地质）、precipitation（降水）、drainage density（水系密度）、**profile curvature**（剖面曲率，就是本周学的）、**distance to roads**（到道路距离）、**distance to population**（到居民点距离）、**TWI**。

**多准则建模的方法论（老师，讲义无）**：

> "generally you start off with lots of different types of spatial information and you **assign some kind of weighting** to them. So **some of them are going to be more important than others**. And you can **play around with the weighting** to see what the effects are in the model."

**为什么要加 proximity 数据**：

> "that's going to help us in terms of mapping out the **risk** zone, because obviously **it doesn't matter if something is prone to landslides but it's a long way from anywhere**."

**→ 这是 hazard（危险性）与 risk（风险）的区别：risk = hazard × exposure。**离人越近，同样的滑坡危险性对应的风险越高。

**TWI（老师的定义）**：

> "TWI is **topographic wetness index**, which is again a terrain-derived **hydrological indicator of soil moisture content**. So it's based on the hydrological modelling that we've just described."

> 📎 背景补充：TWI 公式与用法见 §3.6。材料只给了名字和一句定义，没给公式。

**结论（老师）**：最高风险出现在「**steep slopes + high rainfall + proximity to population**」三者叠加处。以及那句很有说服力的效率论证：

> "you can do all of that **from your desktop**, and then you can go out in the field and evaluate the risk level yourself ... to try and do that by just going out in the field collecting data, evaluating risk, is going to take you an awful lot of **time and money**."

### 2.14 可视性分析（Visibility analysis）

老师先划了个界：

> "Visibility analysis, it's **not strictly speaking terrain analysis, but it's related to it**."

#### Line of sight（视线）

**定义（讲义黑斜体）**：

> **_Line of sight_** — Draws a **line between the observer point and the target point** to indicate the visibility (**visible or obstructed**) along the line between the given points.

**输出的判读（老师读图）**：

- 线被分成有色段：**绿色 = visible（可见）**，**红色 = invisible / obstructed（被遮挡）**
- 同时给一张**剖面图（profile）**，显示地形起伏与视线的关系
- 剖面上有一个关键点：**「the elevation at which you can no longer see your target」**（视线被切断的那个障碍点），图上用**黑星**标出

#### Viewshed（可视域）

**定义（讲义黑斜体）**：

> **_Viewshed_** — Shows the visibility (visible or obstructed) of an **area** from a specified viewpoint.

**判读（讲义 + 老师）**：**Green = visible from blue point.**（绿色区 = 从蓝色观察点可见）；未着色 = 不可见。**绿色的那一整片就叫 viewshed。**

**→ Line of sight 是「点到点、一条线」；Viewshed 是「点到面、一整片」。这是最基本的区分。**

#### Viewshed 2（多观察点）

> "sometimes it's called **Viewshed 2**, where you've got **two observers** ... each one of them has **its own viewshed** ... but it's also sometimes useful to know **which areas are visible to both observers**."

老师给的图里，一个观察者是绿点、一个是蓝三角，两片 viewshed 分别是绿色和蓝色，**重叠区**是「两人都能看到」的区域。

> 📎 背景补充（很重要的工具名澄清）：在 ArcGIS Pro 中，
> - 旧的 **Viewshed** 工具：只做简单的可视/不可视二值判断，不考虑地球曲率。
> - **Geodesic Viewshed**（本周 practical 用的名字）**已在 ArcGIS Pro 中更名为 `Viewshed 2`**——讲义链接的正是 `pro.arcgis.com/.../viewshed-2.htm`。两者是**同一个工具**，在 Geoprocessing 搜索框里搜任一名字都能找到。**不要以为讲义的 Viewshed 2 和 practical 的 Geodesic Viewshed 是两个不同工具。**
> - "Viewshed 2" 名字里的 "2" 指的是**工具的第二代**，不是「两个观察者」。老师课上把它讲成两个观察者的例子，容易造成误解（见勘误表）。
> - `Viewshed 2` 支持**地球曲率与大气折射改正（refractivity coefficient）**、多种 analysis type，以及地统计意义上的**垂直误差（vertical error）**。

**观察点参数（材料在 practical 里给，讲义未给）**——完整清单见 §5.13 与 §3.7。

### 2.15 山体阴影（Hillshade）

讲义只在「Hydrologically correct DEM」那页顺带出现（老师说 "this is our digital elevation model shown as the **hill shade**"），practical 第 6 节标题是 "Create a hill shade of the DEM"。

> 📎 背景补充（本小节基本全为补充，材料几乎没讲原理）：
>
> **Hillshade（山体阴影）**是用一个假想光源照射 DEM，按每个格网的坡度与坡向计算其接收的光照强度（0–255 的灰度值），生成一张**看起来有立体感的灰度图**。
>
> - 它是**可视化产品**，不是地形属性——**hillshade 的像元值没有物理意义**，不能拿去做统计。
> - **默认参数：Azimuth（方位角）= 315°（西北），Altitude（高度角）= 45°。**
> - 为什么默认从西北照？因为人眼习惯「光从左上来」；如果把光源放在东南（135°），人会产生**地形反转错觉（relief inversion）**——山谷看起来像山脊。
> - 公式见 §3.5。
> - ArcGIS Pro 里有两条路：
>   1. **Spatial Analyst Tools → Surface → Hillshade**，生成一个**新栅格**（可以再拿去做分析、叠加）。
>   2. **图层 Symbology → Primary symbology → Shaded Relief / Hillshade**，这是**纯显示效果，不产生新文件**。
>   **本周 practical 用的其实是第 2 条路**（Symbology → Shaded Relief），虽然章节标题写的是 "Create a hill shade"。见勘误表。

### 2.16 太阳辐射制图（Solar radiation mapping）

**目的（讲义）**：

> ➢ Estimate **spatial and temporal** distribution of solar radiation on the Earth's surface.

老师补充「temporal」的含义：「**geographically over an area and also over time, so throughout a year typically**」。

**三种辐射分量（讲义黑体，必背）**：

| 分量 | 英文 | 定义（讲义原文） |
|---|---|---|
| 直接辐射 | **Direct radiation** | propagates **unimpeded in a direct line** from the Sun to the receiving surface |
| 散射辐射 | **Diffuse radiation** | **scattered by clouds and dust** |
| 反射辐射 | **Reflected radiation** | the direct and diffuse radiation **reflected by nearby terrain** towards the location of interest |
| 总辐射／全球辐射 | **Global (total) solar radiation** | = **direct + diffuse + reflected** |

**计算方法：半球视域模型（Hemispherical viewshed）**

> ➢ **Upward-looking hemispherical viewshed model (DTM).**（向上看的半球视域模型）
> ➢ **Maximum angle of sky obstruction in all directions.**（各方向的最大天空遮挡角）
> ➢ Used in combination with **sunmaps and skymaps**.
> ➢ Calculate solar radiation for each location.

老师解释得很形象：

> "you might be in a **valley** and you're looking up and you're seeing the **ridges either side**, and you're looking at the directions and the angles at which those occur ... then we come up with this upward-looking view of the sky. So it's like a **fish-eye view** of the sky looking upwards. The **light grey** area is where it is **visible** and the **darker** areas where it's **obstructed**."

**Sunmap 与 Skymap**：

| 图 | 用途（讲义） | 内容 |
|---|---|---|
| **Sunmap（太阳轨迹图）** | 算 **direct radiation** | 太阳在天空中的位置随**一年中的日期**和**一天中的时刻**的变化轨迹；**依赖纬度**（讲义示例为 **39°N**） |
| **Skymap（天空图）** | 算 **diffuse radiation** | 把天穹划分成若干扇区，给每个扇区一个散射贡献权重 |

**Sunmap 只画半年的原因（老师）**：

> "it goes from the **summer solstice** through to the **winter solstice**, so it only shows **six months**, but essentially once we reach the summer solstice the sky then moves back in the **opposite direction** towards December again ... it effectively covers the whole year."

**东西方向为什么是「反的」（这是个很好的口头澄清，讲义完全没有）**：

> "It's a bit weird because we know that the sun rises in the **east** and yet the earliest times of the day is shown in the **west**, but we've got to remember that **we're looking up** and it's a **mirror image**. So east is always on our right-hand side ... if you align yourself in the north-south direction looking upwards, east is over this side."

**→ Sunmap 是「仰视图」不是「俯视地图」，左右会镜像。**

**最终产物**：把 sunmap 与 skymap 叠到 hemispherical viewshed 上，逐位置累加即得**surface solar radiation map**；用在城市屋顶上就是 **rooftop solar power estimates（屋顶光伏发电潜力评估）**。

**老师明确划的考核范围（很重要）**：

> "Of course, that's all done within the GIS for you, **so you don't need to know how to do it**."
> "**You don't need to know the details**, but it's worth just pointing some of that out."（讲 sunmap 镜像时）

---

## 三、公式与图表

### 3.1 坡度公式

讲义 Page 9 是低质量 OCR 段，原始 OCR 文本为：

```
Slope
Rise (/)
<—— Run (¢) ——>
Percentslope: 6= 100 (h/d) (%)
Degree slope: @=arctan(h/d) (degree)
```

其中 `6` 与 `@` 是**希腊字母 θ 被 OCR 错认**的结果，`(/)`、`(¢)` 是 `(h)`、`(d)` 的误识。还原后的正确公式为：

$$\text{Percent slope: } \theta = 100 \times \frac{h}{d} \ (\%)$$

$$\text{Degree slope: } \theta = \arctan\left(\frac{h}{d}\right) \ (\text{degree})$$

其中：
- **h = rise（高差，vertical change）**
- **d = run（水平距离，horizontal distance）**

**两种单位的换算（📎 背景补充，材料未给换算表）**：

$$\text{percent} = 100 \times \tan(\text{degree}) \qquad \text{degree} = \arctan\!\left(\frac{\text{percent}}{100}\right)$$

| 度数 | 百分比 | 记忆点 |
|---|---|---|
| 0° | 0 % | 平地 |
| 5° | 8.7 % | |
| 10° | 17.6 % | 小角度时「百分比 ≈ 度数 × 1.75」 |
| 26.57° | **50 %** | |
| **45°** | **100 %** | **最关键的锚点：45° = 100%，不是 50%** |
| 60° | 173 % | |
| 90° | ∞ | 百分比无上界 |

**⚠️ 最常见的错：以为 100% 坡度等于 90°（垂直）。不是——100% = 45°。百分比坡度可以超过 100%，度数坡度不能超过 90°。**

> 📎 背景补充：**ArcGIS 实际怎么算坡度**——不是简单地用两个格网的高差，而是用 **Horn (1981) 的 3×3 移动窗口法**。对下面这个 3×3 窗口（e 为中心格网）：
>
> ```
> a  b  c
> d  e  f
> g  h  i
> ```
>
> $$\frac{dz}{dx}=\frac{(c+2f+i)-(a+2d+g)}{8\,\Delta x},\qquad \frac{dz}{dy}=\frac{(g+2h+i)-(a+2b+c)}{8\,\Delta y}$$
>
> $$\text{slope}_{\text{rise/run}}=\sqrt{\left(\frac{dz}{dx}\right)^{2}+\left(\frac{dz}{dy}\right)^{2}},\qquad \text{slope}_{\text{deg}}=\arctan\left(\text{slope}_{\text{rise/run}}\right)\times\frac{180}{\pi}$$
>
> **推论：格网越大（cell size 越大），分母越大，算出来的坡度越平缓。** 同一片山地，用 5 m DEM 和用 50 m DEM 算坡度，结果会差很多——这就是老师强调「分辨率永远要考虑」的定量原因。
>
> ⚠️ 还有一个坑：如果 DEM 用的是**地理坐标系（经纬度，单位为度）**，而高程单位是米，`dz/dx` 的量纲就完全错了。必须用**投影坐标系**，或在工具里设置 `Z factor`。

### 3.2 坡向的定义与取值

> 📎 背景补充（材料只给了「azimuth / compass bearing」一句，以下为补充）：
>
> $$\text{aspect} = \arctan2\left(\frac{dz}{dy},\ -\frac{dz}{dx}\right)$$
>
> 结果换算到 **0°–360°，正北 = 0，顺时针**。ArcGIS 对坡度为 0 的平坦格网赋 **−1**。
>
> **圆形数据的平均**（不能用算术平均）：
>
> $$\bar{\theta}=\arctan2\left(\frac{1}{n}\sum\sin\theta_i,\ \frac{1}{n}\sum\cos\theta_i\right)$$
>
> 同时可算**平均合成向量长度 R**（0 ≤ R ≤ 1）作为「方向集中度」：R 接近 1 表示坡向高度一致，R 接近 0 表示坡向杂乱无主导方向。

### 3.3 D8 流向编码与老师的手算例子

#### D8 编码（📎 背景补充——材料完全没给编码，但这是标准考点）

ArcGIS 的 Flow Direction 输出栅格里存的不是角度，而是 **2 的幂次编码**。中心格网周围 8 个方向的编码为：

```
        N
     32  64  128
      \   |   /
 W  16 — [C] — 1   E
      /   |   \
      8   4    2
        S
```

写成表格：

| 方向 | 英文 | 编码 |
|---|---|---|
| 东 | East | **1** |
| 东南 | Southeast | **2** |
| 南 | South | **4** |
| 西南 | Southwest | **8** |
| 西 | West | **16** |
| 西北 | Northwest | **32** |
| 北 | North | **64** |
| 东北 | Northeast | **128** |

**记忆法：从正东开始、顺时针，依次是 1, 2, 4, 8, 16, 32, 64, 128（每次翻倍）。**

用 2 的幂次是有原因的：这样任意几个方向的组合都对应唯一的和（位运算），便于处理平坦区的多值情况。

#### 老师的手算例子（转写还原）

老师用了一个 3×3 的 DEM 片段，中心格网高程 **67**，其中：
- 正下方（或某个正交邻居）高程 **53**
- 对角方向邻居高程 **44**

（转写里被自动语音识别写成了 "153"、"167"、"144"，应为 53、67、44。）

设**格网边长为 1**（可以是 1 m 或 1 km）：

**正交方向**：距离 = 1

$$\text{slope} = \frac{67-53}{1} = \mathbf{14}$$

**对角方向**：距离要用**勾股定理**

> "for the diagonal here going from 67 to 44, it's just a little bit more complex. You need to use **Pythagoras' theorem** ... the side length here is the **square root of 2**."

$$d = \sqrt{1^2+1^2} = \sqrt{2} \approx 1.414$$

$$\text{slope} = \frac{67-44}{\sqrt{2}} = \frac{23}{1.414} \approx \mathbf{16.3}$$

**16.3 > 14，所以水优先沿对角线流。**

> "so we know that water will preferentially flow along this **diagonal** from here to here."

**⚠️ 这个例子的教学价值在于：不能只比高差。** 如果只看高差，23 > 14 也是对角线赢；但**若把数字改成正交高差 20、对角高差 25**，则正交坡度 = 20，对角坡度 = 25/1.414 = 17.7，**正交方向反而更陡**。所以**必须除以 √2**。

> 📎 背景补充：这里的 14 与 16.3 是**无量纲的 rise/run 比值**（也就是 tan θ），不是角度。若真要换成度数，arctan(14) = 85.9°——显然不现实，说明这只是一个**便于口算的教学示例**，不是真实高程数据。

### 3.4 流量累积的手工累加（老师的完整演示）

老师把 flow accumulation 的算法拆成四步，是本周最值得完整复现的一段：

**第 1 步**：对每个格网算出流向，画成**箭头图**。

**第 2 步**：把箭头连成**流线（lines）**——多条流线在某个格网汇合，就形成一个 **node（节点）**。

**第 3 步**：**数每个格网有多少条上游流线汇入**。

> "this top left cell here doesn't have any arrows coming into it, so we could give that a value of **zero**. Whereas the next one down in the diagonal, it has **one, two, three** cells connected to it, so that gets a value of **three**."

**第 4 步**：把流线擦掉，只留数值 → 得到 **flow accumulation raster**。

**关键的累加逻辑（老师用一个值为 11 的格网演示，务必看懂）**：

> "this cell here has a value of **11**. So what that means is that it gains **three** from this point here plus another **one** from this cell. So that's **3 + 1 = 4**; **2 + 1**, that's **7**; **2 + 1** is **10**; and then gets **1** from here. So that gives it **eleven**."

拆开写：

| 累加步骤 | 说明 | 运行合计 |
|---|---|---|
| 上游支流带来 3 | 该支流自身的累积值 | 3 |
| 加上该支流所在格网本身 1 | **格网自己也算一个** | **4** |
| 再汇入一条累积值为 2 的支流 | +2 | 6 |
| 加上那个格网本身 1 | +1 | **7** |
| 再汇入一条累积值为 2 的支流 | +2 | 9 |
| 加上那个格网本身 1 | +1 | **10** |
| 最后再汇入 1 | +1 | **11** |

**→ 核心规则：某格网的 flow accumulation = 所有直接上游邻居的（accumulation + 1）之和。**

**→ 无上游汇入的格网（山脊、分水岭）值为 0。**（讲义：「zero values = ridgelines」）

> 📎 背景补充：ArcGIS 的 `Flow Accumulation` **默认不把格网自身计入**，所以山脊格网是 0 而不是 1。若加了权重栅格（如降水量栅格），则累积的是**权重之和**而不是格网个数——这是做产流量估算的常用技巧。

### 3.5 山体阴影公式与参数（📎 背景补充，材料未给）

$$\text{Hillshade} = 255 \times \Big[\cos(Z)\cos(S) + \sin(Z)\sin(S)\cos(A_{\text{sun}} - A_{\text{aspect}})\Big]$$

- **Z = Zenith angle（天顶角）= 90° − Altitude**
- **S = Slope（该格网坡度）**
- **A_sun = Azimuth（光源方位角）**
- **A_aspect = Aspect（该格网坡向）**
- 结果被拉伸到 **0–255** 的 8 位灰度；负值截断为 0（完全阴影）

**默认参数**：

| 参数 | 英文 | 默认值 | 含义 |
|---|---|---|---|
| 方位角 | **Azimuth** | **315°** | 光源的罗盘方位（315° = 西北） |
| 高度角 | **Altitude** | **45°** | 光源在地平线以上的仰角 |
| 模拟阴影 | **Model shadows** | 关 | 开启后会计算真实投影阴影（更慢） |
| 垂直放大 | **Z factor** | 1 | 高程单位与平面单位不一致时必须设 |

**注意 cos(A_sun − A_aspect) 这一项**：当坡向正对光源（差值为 0）时该项为 1，最亮；背对光源（差值 180°）时为 −1，最暗。**这正是 hillshade 能显出立体感的原因。**

### 3.6 地形湿度指数 TWI（📎 背景补充，材料只给了名字）

$$\mathrm{TWI} = \ln\!\left(\frac{a}{\tan \beta}\right)$$

- **a** = **specific catchment area（单位等高线长度的上游汇水面积）**，由 flow accumulation 除以格网边长得到
- **β** = **local slope angle（局部坡度角）**

**读法**：
- **a 大**（上游来水多）且 **β 小**（坡缓、水走不掉）→ **TWI 高 → 湿**，典型是**谷底、平缓洼地**
- **a 小**且 **β 大** → **TWI 低 → 干**，典型是**陡峭山脊**

**⚠️ 分母是 tan β，所以坡度为 0 时 TWI 发散。** 实践中会给 β 一个极小的下限值。

**这正好印证了老师说的「secondary attribute = 两个以上 primary attribute 的组合」**：TWI = flow accumulation（二阶水文量）+ slope（一阶量）的组合。

### 3.7 可视域分析的观察点参数（materials 在 practical 给出）

| 参数（practical 用名） | ArcGIS 字段名 | 含义 | Practical 用的值 |
|---|---|---|---|
| **Observer offset** | **OFFSETA** | 加在**观察点**上的高度（本例即风机高度） | **25** m |
| **Surface offset** | **OFFSETB** | 加在**每一个被观察的目标格网**上的高度（本例即人站着的眼高） | **1.6** m |
| **Observer elevation** | SPOT | 观察点的**绝对海拔**（不是相对地面高度） | **不用** |
| **Inner / Outer radius** | RADIUS1 / RADIUS2 | 限制分析的内外半径 | **不用** |
| **Refractivity coefficient** | — | 大气折射系数（用于非可见光，如手机基站选址） | **忽略** |
| **Analysis method** | — | `All sightlines`（默认，精确）／`Perimeter sightlines`（快但粗） | **All sightlines** |
| **Analysis type** | — | `Frequency`（统计每格网能被几个观察点看到）／`Observers`（记录具体是哪些观察点） | **Frequency** |
| **Vertical error** | — | DEM 高程的 RMSE，可纳入计算 | 不设 |

> 📎 背景补充：字段名还包括 **AZIMUTH1 / AZIMUTH2**（限制水平视角范围，例如只看正北到正东）与 **VERT1 / VERT2**（限制垂直视角）。**在观察点要素类的属性表里加上这些字段名的列并填值，工具会自动读取，逐点使用不同参数**——这比在工具面板里设一个全局值灵活得多。materials 没有提到这一点。

### 3.8 关键图表的文字复原（读到能自己画出来）

#### 图 A：复杂度层级（讲义首页）

从左到右三个球（或三个剖面）并排：

1. **Spheroid** —— 一个光滑的椭球，赤道略鼓、两极略扁，表面完全平滑。
2. **Geoid** —— 同样大小的球，但表面有平缓的凹凸起伏（**幅度被夸张放大了几千倍**，真实起伏只有 ±100 m 量级）。凸的地方是重力异常正区（地下密度大），凹的地方相反。
3. **Land surface / Terrain** —— 真实地形，有尖锐的山峰、深切的峡谷、平原，**起伏尺度远大于 geoid 的起伏**。

**画的时候要传达的信息**：从左到右**信息量与复杂度递增**，但同时**数学描述的难度也递增**。

#### 图 B：同一曲面的四种表达（讲义 "different ways of representing the same continuous surface"）

一个 2×2 排列，四个格子里是**同一座小山**：

- 左上：**Contours** —— 一圈套一圈的闭合等高线，越往里高程越大。
- 右上：**Spot heights** —— 散布的点，每个点旁标一个数字（如 ·142、·157）。
- 左下：**DEM (raster)** —— 规则方格网，每格填一个灰度/彩色，颜色深浅对应高程。**所有格子一样大。**
- 右下：**TIN (vector)** —— 三角网，山顶附近三角形**密而小**，山坡平缓处三角形**疏而大**。

**关键提示（讲义斜体）**：这四张图的**尺度与范围完全相同**，只是表达方式不同。

#### 图 C：TIN 的 breaklines（讲义 + 老师读图）

底图是一片三角网。上面叠了两个要素：

- **一条实心红线**穿过三角网 —— 这是一条**道路**，标为 **soft breakline**。三角形的边被强制沿这条线对齐，但线两侧的坡度是连续的。
- **一片蓝色填充多边形** —— 这是一个**湖**，其岸线标为 **hard breakline**。三角形**绝对不能跨越**这条岸线，因为陆面与水面之间有坡度的**突变**。

**画的时候要传达的信息**：断裂线的作用是**约束三角剖分**，防止三角形「跨过」重要地形边界把它抹平。

#### 图 D：Sink 的识别（讲义 + 老师读图）

分上下两部分：

**上半**：一个 DEM 栅格片段，比如 5×5 的格子，每格写一个高程数字（例如 78, 74, 69, 71, 66 …）。其中**中间某一格数字明显偏小**（比如周围都是 60–70，它是 **31**），四周都比它高。

**下半**：把上面某一行的数值画成**柱状图**（横轴 = 格网位置，纵轴 = 高程）。图上有两处异常：
- **一根异常矮的柱** → **sink（洼地/pit）**
- **一根异常高的柱** → **spike（尖峰）**

老师同时提到了 pit 与 spike，但讲义定义只写了 pit（见 §6 与勘误表的说明）。

#### 图 E：填洼的效果对比（讲义 "Hydrologically correct DEM" 第二页）

上下两组，每组两张图：

**上组（未填洼）**：
- (a) DEM 的 **hillshade** 显示
- (b) 同一张图上用**黑色小方块**标出所有 sink 的位置（星星点点散布全图）
- (c) 由这个 DEM 直接算出的**河网** —— **看起来不真实**：河道**断续、中断、走向诡异**，很多短线段互不相连

**下组（已填洼）**：
- (d) **DEM without sinks**
- (e) **Drainage lines from the DEM without sinks** —— 河网**连续、树枝状（dendritic）、汇入主干**，符合真实水系形态

**这张对比图是「为什么必须 Fill」的最强证据，画一遍就永远记住了。**

#### 图 F：D8 流向的 3×3 邻域（复原 + 📎 编码补充）

画一个 3×3 方格，中心格写 **67**，八个邻居分别写上高程。以老师的例子为准：

```
 ┌──────┬──────┬──────┐
 │      │      │      │
 │      │      │      │
 ├──────┼──────┼──────┤
 │      │  67  │  53  │   ← 正交邻居，高差 14，距离 1，坡度 = 14
 ├──────┼──────┼──────┤
 │      │      │  44  │   ← 对角邻居，高差 23，距离 √2，坡度 = 16.3 ✔ 最陡
 └──────┴──────┴──────┘
```

然后在中心格画**一个箭头指向 44 那格**（对角方向）。旁边标注 **编码 = 2（Southeast）**。

**再画一张编码盘**（见 §3.3 的 ASCII 图）：中心格周围八个方向按顺时针从东开始标 1、2、4、8、16、32、64、128。

#### 图 G：Fill → Flow Direction → Flow Accumulation → Stream → Watershed 流程链

画成一条从左到右的流水线，每一格是一张小栅格图：

```
┌───────────┐   ┌───────────┐   ┌───────────┐   ┌───────────┐   ┌───────────┐
│  ① DEM    │→ │② Flow Dir │→ │③ Flow Acc │→ │④ Stream   │→ │⑤ Watershed│
│  含 sink  │   │  箭头图   │   │  白线网络 │   │  阈值切分 │   │  彩色分区 │
│  Fill 之后│   │  D8 编码  │   │  0=山脊   │   │ 1000/7000 │   │ + pour pt │
└───────────┘   └───────────┘   └───────────┘   └───────────┘   └───────────┘
      Fill        Flow Direction   Flow Accumulation   Con/阈值      Watershed
```

**每一格下面标上 ArcGIS 工具名**（📎 工具名为补充，materials 只描述了概念）：
`Fill` → `Flow Direction` → `Flow Accumulation` → `Con` + `Stream to Feature` → `Snap Pour Point` + `Watershed`

**每一格的判读要点**：
- ① 填洼前后差别肉眼几乎看不出，但结果差别巨大
- ② 每格一个箭头，只能指向 8 个方向之一
- ③ **白 = 高值 = 河道；黑 = 0 = 山脊**
- ④ 阈值 1000 → 支流密；阈值 7000 → 只剩主干
- ⑤ 相邻的彩色多边形，边界沿山脊，每个多边形有一个出水口（pour point）

#### 图 H：视线分析的原理（讲义 "Typical output of line-of-sight analysis" + 老师读图）

**上半（平面图）**：
- 一个**观察点**（图上标 observer）
- 一个**目标**（**蓝色三角形**）
- 两点之间一条直线，被分成若干段：**绿色段 = 可见，红色段 = 不可见**

**下半（剖面图）**：
- 横轴 = 沿视线的水平距离，纵轴 = 高程
- 一条起伏的**地形剖面曲线**
- 从观察点眼睛的位置画一条**直的视线**射向目标
- 地形剖面在某处**凸起并切断视线** —— 这个切点用**黑色星号**标出，老师称之为「the elevation at which you can no longer see your target」
- 切点之前的地面段是绿色（可见），切点之后被挡住的段是红色（不可见）

**画的时候要传达的核心**：**可见性的判据是「视线的仰角是否被中间某个地形点超过」**——只要中途有任何一点的仰角高于目标的仰角，目标就不可见。

#### 图 I：Viewshed（讲义 "Green = visible from blue point"）

一张地形底图（通常配 hillshade），上面：
- 一个**蓝色圆点** = viewpoint / observer
- 一大片**绿色半透明区域** = viewshed（可见）
- 未着色的区域 = 不可见

**绿色区的形态特征值得画出来**：不是一个圆，而是**放射状的、有很多楔形缺口**——那些缺口就是被山脊挡住的「视线阴影」。**山脊背后一定是缺口，山谷对面的坡面往往可见。**

#### 图 J：Viewshed 2（两个观察者）

同一张底图上：
- **绿点观察者** → 绿色 viewshed
- **蓝三角观察者** → 蓝色 viewshed
- **两者重叠的区域**用第三种颜色表示 → 「visible to **both** observers」

#### 图 K：半球视域 + Sunmap + Skymap（讲义太阳辐射部分）

三张图叠在一起看：

1. **Hemispherical viewshed（鱼眼图）**：一个圆，圆心是天顶，圆周是地平线。**浅灰 = 天空可见，深灰/黑 = 被地形遮挡**。若你在一条东西向的谷地里，南北两侧会是两条黑色的弧带。
2. **Sunmap（太阳轨迹图）**：同一个圆上叠一组**弧线**——每条弧是一天中太阳的轨迹，从夏至（最靠北/最高的那条）到冬至（最靠南/最低的那条），共约 6 个月的若干条；弧线上再画一组**垂直的时刻线**（早上、中午、下午）。**注意：东在右侧、西在左侧——因为是仰视镜像。**
3. **Skymap（天空图）**：同一个圆被分成**若干扇区**（像切披萨再加同心环），每个扇区一个散射权重值。

**叠加逻辑**：只有既在 sunmap 轨迹上、又落在 viewshed 浅灰（可见）区的那些时段，才贡献 direct radiation；skymap 中落在浅灰区的扇区才贡献 diffuse radiation。二者相加（再加 reflected）就是 **global radiation**。

#### 图 L：坡度图与坡向图的判读（OCR 低质量页，仅能部分复原）

- **Slope map（讲义 Page 10）**：约 20 km × 20 km 的彩色栅格。**绿色 = 平缓，暖色 = 陡峭**。平坦区通常呈**片状**（谷底、平原），陡坡呈**线状/带状**（沿河谷两侧、沿断层崖）。
- **Aspect map（讲义 Page 11）**：同一区域，按 8 个方位分色，图上方配一个**罗盘玫瑰图**作图例。OCR 只能辨出 "NW"、"W 270°"、"SW"、"SZ"（应为 SE 或 S）等零星字样，以及图例里几个被打乱的角度区间（"2025-2475"、"292 5.337 5"、"297 5-280" 等，均为 OCR 乱码）。
  **判读要点**：**坡向图看起来一定是「花的」**——一条山脊的两侧坡向相反（一侧向北、一侧向南），所以山脊线在坡向图上表现为**颜色的突变线**。这是识别山脊/山谷的一个技巧。
- **Terrain profile（讲义 Page 12）**：一张 TIN/DEM 底图 + 一条 A–B 剖面线 + 下方的剖面曲线，标注 **Vertical exaggeration 3.0 X**，高程图例分级为 200–500、500–800、800–1100、（1100–1400）、1400–1800、1800–2100、2100–2400、2400–2700、2700–3000 m。（其中 1100–1400 一档被 OCR 识别为 "BS 100 «200"，且 1400–1800 这一档的间距与其余各档的 300 m 不一致，疑为 OCR 数字误识——见勘误表。）

---

## 四、课堂补充（transcript 提炼）

本周有 6,563 词的完整转写，是本周最宝贵的材料。以下是**讲义上没有、只在口头出现**的内容。

### 4.1 关于讲义 OCR 低质量段的说明（必读）

`Lecture 7 - Terrain Analysis.md` 的**末尾单独有一节「OCR 补充（原文中无文字层的页面）」**，明确标注：

> _(以下内容由图片 OCR 识别得到，原文件该处无可提取文字。**识别质量低**——原件疑为手写或图件，文字大多不可靠，仅作线索，务必对照原件。)_

**受影响的具体页面共 4 页**：

| 页 | 内容 | 可信度评估 |
|---|---|---|
| **Page 9** | 坡度公式（Rise/Run、percent slope、degree slope） | **公式结构可信、符号不可信**。`6=` 与 `@=` 应为 `θ=`，`(/)`、`(¢)` 应为 `(h)`、`(d)`。还原后的公式在 §3.1 |
| **Page 10** | Slope map | 只剩标题，图内容全丢 |
| **Page 11** | Aspect map（罗盘图例） | **图例数值全部乱码**（"2025-2475"、"292 5.337 5"、"297 5-280"、"[sem GER Soctrrwees"），**完全不可用**；只有 "NW"、"W270°"、"SW" 几个方位缩写勉强可辨 |
| **Page 12** | Terrain profile（高程分级图例） | **部分可用**。"Vertical exaggeration 3.0 X" 可信；高程分级中 "BS 100 «200"、"PaO"、"TR"、"Orstance"（应为 Distance）为乱码；分级间距不一致疑为数字误识 |
| **Page 17** | Hydrologically correct DEM 的 (d)(e) 子图标题 | **可信**——"(d) DEM without sinks"、"(e) Drainage lines from the DEM without sinks" 语义完整 |

**结论：本周讲义中所有的定义性文字（正文黑体、斜体、项目符号）都是有文字层的可靠内容；只有上述 5 页的图内文字不可靠。核心公式（坡度）虽在 OCR 段，但结构清晰可还原，可以放心使用。**

### 4.2 老师明确说「不用记」的内容（省力清单）

三处：

1. **太阳辐射的具体算法**：
   > "Of course, that's all done within the GIS for you, so **you don't need to know how to do it**. What you end up with are surface solar radiation maps."
2. **Sunmap 的东西镜像细节**：
   > "**You don't need to know the details**, but it's worth just pointing some of that out."
3. **D8 的手算过程**（隐含）：老师算完那个 67/53/44 的例子后说：
   > "It's a bit laboured, but **it gives you the idea of generally how it's worked out**."
   → 重点是**理解「为什么对角要除以 √2」**，不是背算式。

**反过来，老师反复强调、务必掌握的是：**
- 一阶 vs 二阶属性的划分与各自包含哪些量
- slope / aspect / profile curvature / plan curvature **各自控制什么水文过程**（那句黑体总结）
- **Fill 是水文分析的第一步，不做会毁掉结果**
- **阈值选择会显著改变河网**，且需要野外验证
- line of sight 与 viewshed 的区别

### 4.3 讲义没有、只在口头出现的概念澄清

| 主题 | 老师的口头补充 |
|---|---|
| **Point cloud** | 讲义四种表达方式里没写点云，老师把 LiDAR 点云补进来作为第五种 |
| **Ground survey 的双重作用** | 「both collecting data and also for verifying」——讲义只列了一条 "Ground surveys" |
| **空间分辨率** | 讲义完全没提分辨率，老师专门停下来讲了一段：「现在能做到 1 m」「取决于应用与尺度」「**永远要考虑**」 |
| **TIN 的失效场景** | 讲义只写 "less useful when surface is flat"；老师展开成「沙漠、高原」「lose subtle variation」「even things out」「looks unrealistic」三条具体后果 |
| **水文分析必须用 raster** | 讲义没写；老师明说 "don't tend to use TINs for this kind of application" |
| **Sink 也可能是 spike** | 讲义定义只写 pit（"Areas which are pits"）；老师说 "sinks are pits **or sometimes they're spikes**"（这句在概念上有问题，见勘误表） |
| **多准则建模的权重可调** | 讲义只有一张案例图；老师讲了「assign weighting」「some are more important than others」「play around with the weighting」的完整方法论 |
| **Hazard vs Risk** | 讲义无；老师用「it doesn't matter if something is prone to landslides but it's a long way from anywhere」讲清了为什么要加 proximity to roads / population |
| **Sunmap 的仰视镜像** | 讲义无；老师专门解释了「为什么东在右边、早上的太阳画在左边」 |

### 4.4 老师给的真实案例（可能出现在应用题里）

**案例 1：火星冰下火山的形态参数（老师自己的科研）**

> "last year I had a project with a **fourth-year student** looking at **shape parameters of subglacial volcanoes on Mars** using remote sensing data and terrain analysis."

（讲义 Applications 页写的是 "Shape parameters of volcanic landforms (e.g. subglacial edifices on **Mars**)"。）

**→ 这条最重要的意义是：地形分析不限于地球，也不限于水；行星地质学用同一套方法。而且它是「大三独立项目」的典型题材——老师是在给你暗示项目方向。**

**案例 2：秘鲁 Utcubamba 河流域滑坡风险分区（Rivera et al. 2025）**

详见 §2.13。**这是本周讲义里唯一一个完整的多准则分析实例，也是本周 practical 的思路来源。**

**案例 3（讲义 Applications 页的完整清单，值得当作「地形分析能干嘛」的答题素材库）**：

- **Mapping drainage networks** —— 识别河道、流路、流域边界，用于河流管理
- **Flood modelling** —— 定位洪泛区、水流瓶颈、漫溢点
- **Erosion risk assessment** —— 预测土壤流失易发区
- **Wetland and groundwater recharge mapping** —— 识别洼地、低坡度区、辐合流区
- **Geomorphological mapping** —— 山脊、河谷、阶地、陡崖、沙丘
- **Shape parameters** of volcanic landforms
- **Detecting landslide-prone slopes**
- **Mapping glacial features** —— 鼓丘（drumlins）、冰碛（moraines）、融水通道（meltwater channels）

### 4.5 老师对本周 Practical 的预告

在讲 viewshed 的地方直接点名：

> "your practical this week, you'll be using a **viewshed** to look at the **environmental impact of a wind turbine location**."

**→ 这句话确认了 practical 的核心目的不是「找到风最大的地方」，而是「评估视觉影响」。** 见 §5.16 的重要说明。

### 4.6 老师对下周的预告

> "the practical you're doing next week, we'll be looking at working out **solar radiation**, the amount of solar energy that can be generated over an area of **Manchester**."

**→ 与 W08 practical《Solar radiation mapping and map layout》完全吻合。本周讲义最后 1/4（太阳辐射、半球视域、sunmap/skymap）实际上是在为下周的 practical 打理论底子——复习 W08 时要回头看本周 §2.16。**

### 4.7 自动转写（ASR）的误识清单

转写是机器生成的，有大量专有名词误识。阅读时须自行还原：

| 转写写法 | 正确写法 |
|---|---|
| "brake lines" | **breaklines** |
| "rasta" / "rasta layers" | **raster** |
| "tins" | **TINs** |
| "a DM or a tin" | **a DEM or a TIN** |
| "in saw" | **InSAR** |
| "give morphological mapping" | **geomorphological mapping** |
| "the okra Bamba River Basin" | **the Utcubamba River Basin** |
| "TW1" | **TWI**（Topographic Wetness Index） |
| "viewshed to" | **Viewshed 2** |
| "153" / "167" / "144"（D8 例子） | **53 / 67 / 44** |
| "sumap" | **sunmap** |
| "erosion ability" | **erodibility**（可蚀性） |
| "crigging"（W05 转写中） | kriging |

---

## 五、Practical 要点

> **本段是本课笔记的重心。目标：不开原教程，也能在 ArcGIS Pro 里从头重做一遍。**

### 5.0 学习目标（教程原文）

> By the end of this practical you will be able to:
> - Use **spatial analysis tools to merge and extract** data needed for a project.
> - Work with **DEM** and create **viewsheds**.
> - Know how to use GIS to **identify potential sites suitable for wind farms** and **assess their visibility from nearby locations**.

### 5.1 场景设定与背景知识（教程 §1）

**你的角色**：一家风电公司的经理，要在**英国 Cornwall（康沃尔郡）**选新的风电场址。

**教程给的风机背景数据（可能被问到）**：

| 项目 | 数值 |
|---|---|
| 寿命 | **20–25 年**（初装成本之后） |
| 高度 | **25–80 m** |
| 转子直径 | 最大 **65 m** |
| 可见距离 | "can be seen for **many miles**" |

**选址的两难（教程原文逻辑）**：

- **有利面**：风机应放在**多风处** —— "the top of valleys, **ridges** and **offshore**"（谷顶、山脊、海上）
- **反对面**：
  - 有人认为风机是景观上的 "**blots**"（污点）—— 吵、不好看
  - 在 **areas of outstanding natural beauty（AONB）**、**national parks（国家公园）**、**sites of special scientific interest（SSSI）** 不受欢迎
  - 体积巨大，对**低飞航空器**和**候鸟**有危害

**GIS 的定位（教程原话，值得记）**：

> "With so many objections to consider, **GIS is an ideal tool** for helping a company to locate an optimal site which **maximises the energy output whilst considering the wishes of local people and other organisations**."

**viewshed 在本 practical 中的用途（教程明确说明）**：

> "From this you can identify **which towns are able to see a new wind farm** and with this knowledge you can **tailor any advice given to these populations**."

**→ 即：viewshed 不是用来否决选址的，而是用来做「利益相关方沟通」的。**

### 5.2 数据清单（教程 §2）

新建一个 ArcGIS Pro 工程，从 **ArcGIS Online** 搜索并添加以下 shapefile：

| # | 图层全名（教程原文） | 内容 | 后续用途 |
|---|---|---|---|
| 1 | **Areas of Outstanding Natural Beauty (England) – shape file** | 杰出自然景观区 | 500 m 排除缓冲 |
| 2 | **Site of Special Scientific Interest (England) – shape file** | 特殊科学价值地点 | 500 m 排除缓冲 |
| 3 | **Built Up Areas (December 2022) Boundaries GB BGG – shape file** | 建成区 | 500 m 排除缓冲 |
| 4 | **Counties and Unitary Authorities (December 2021) Boundaries UK BFE** | 郡与单一管理区界 | 提取 Cornwall 边界 |
| 5 | **OS Open Rivers** | 河流 | 100 m 排除缓冲 |
| 6 | **OS Open Roads** | 道路 | 100 m 排除缓冲 |

另外后面还要加：

| # | 图层 | 来源 |
|---|---|---|
| 7 | **DEM_StCM** | **Add Data → ArcGIS Online → My Organisation**（也在 Canvas Week 7） |
| 8 | **Onshore_Windfarms** | ArcGIS Online |
| 9 | **Feasibility Map_WFL1**（homework challenge） | ArcGIS Online |

**操作提示**：用 **Contents Pane（内容窗格）**里的复选框逐个开关图层，先看清每个图层各是什么。

> 📎 背景补充：从 ArcGIS Online 添加数据的完整路径是 **Map 选项卡 → Add Data 下拉 → Data**，然后在弹出的浏览窗口左侧选 **Portal → ArcGIS Online**（或 **My Organisation**），在搜索框里输入图层名。教程只写了图层名，没写点击路径。

### 5.3 步骤 1：提取 Cornwall 县界（教程 §3）

**目的**：不需要全英国的数据，先把研究区裁出来。

1. **右键 `CTYUA_DEC_2021_UK_BFE` 图层 → Attribute Table（属性表）**，找到存郡名的字段：**`CTYUA21NM`**。
2. **Ribbon → Map → Select by Attributes**，输入表达式。

   > **材料未说明**：教程此处只给了截图，没有给出表达式文字。
   > 📎 按字段名推断，表达式应为：`CTYUA21NM` **is Equal to** `Cornwall`
   > （SQL 形式：`CTYUA21NM = 'Cornwall'`）

3. 点 **Run** → Cornwall 被选中。
4. **右键 `CTYUA_DEC_2021_UK_BFE` → Selection → Make Layer From Selected Features**。
5. 把新图层**重命名为 `County_Boundary`**。
6. **右键 Contents Pane 里的 `Map` → New Group Layer**，命名为 **`Cornwall`**，把 `County_Boundary` 拖进去。
7. **移除**原始的 `Counties and Unitary Authorities...` 图层。

**关键概念**：`County_Boundary` 从此成为**所有后续裁剪的「模板边界」**。

### 5.4 步骤 2：用 Select by Location 把 5 个图层裁到 Cornwall（教程 §3）

**先做道路，作为示范**：

**Map → Select by Location**，参数：

| 参数 | 值 |
|---|---|
| **Input Features** | **OS Open Roads（Road Link）** |
| **Relationship** | **Intersect** |
| **Selecting Features** | **County_Boundary** |

然后：**展开 `OS Open Roads` 组图层 → 右键 `Road Link` → Selection → Make Layer From Selected Features** → 重命名为 **`Roads`** → 拖入 `Cornwall` 组。

**⚠️ 教程此处有错**：原文写 "remove the **OS Open Rivers** from your project"，但这一步处理的是道路，应为 **OS Open Roads**。见勘误表。

**其余四个图层按下表重复**（教程原表）：

| Input Features | **Relationship** | New output layer name |
|---|---|---|
| OS Rivers | **Intersect** | **Rivers** |
| Areas of Outstanding Natural Beauty | **Have their center in** | **AONB** |
| Sites of Special Scientific Interest | **Within** | **SSSI** |
| Built Up Areas (December 2022) Boundaries GB BGG | **Within** | **Urban_Areas** |

**做完后**：移除所有 parent layer（父图层），把 5 个新图层都放进 `Cornwall` 组。

> 📎 背景补充（**三种 Relationship 为什么不一样，这是本步骤最值得理解的地方**）：
>
> | Relationship | 判定条件 | 为什么这里用它 |
> |---|---|---|
> | **Intersect** | 只要**有任何一点接触**就选中 | 道路和河流是**线**，很多会跨越县界。用 Intersect 能把「一半在 Cornwall 里」的路也选进来，不漏 |
> | **Within** | 要素**完全落在**目标多边形内部 | SSSI 和 Built Up Areas 是**多边形**，用 Within 只要完全在县内的。跨界的会被**丢掉** |
> | **Have their center in** | 要素的**质心**落在目标内 | AONB 面积大、经常跨郡界（如 Cornwall AONB 本身就是碎片化的）。用 Within 会把跨界的整块丢光；用 Intersect 又会把邻郡的一大块拉进来。**用质心是折中方案** |
>
> **考点：为什么不能统一用 Intersect？** 因为对多边形用 Intersect，只要边角碰到 Cornwall 一点，整块（可能横跨三个郡）的多边形都会进来，缓冲之后会在研究区外产生大片无意义的禁建区。

### 5.5 步骤 3：只保留 A 级与 B 级道路（教程 §3 末）

**理由（教程原文）**：

> "We have a **dense road network** so let's consider that only **A and B roads are important** for siting turbines (and note there are **no Motorways in Cornwall**)."

**操作**：**Map → Select by Attributes**，**Input Rows = `Roads`**，加**两条表达式**。

> **材料未说明**：教程给的是截图，没有表达式文字。
> 📎 OS Open Roads 的 RoadLink 要素类中，道路等级字段通常名为 **`class`**（取值 `'A Road'`、`'B Road'`、`'Motorway'`、`'Minor Road'`、`'Local Road'` 等），部分版本叫 `roadFunction`。
> 📎 **两条表达式必须用 `Or` 连接**，不能用 `And`：
> ```
> Where  class  is Equal to  'A Road'
> Or     class  is Equal to  'B Road'
> ```
> **用 `And` 会选中 0 条记录**（没有一条路同时既是 A Road 又是 B Road）——这是本练习最容易踩的坑。

点 **Apply** → **OK** → 从选择集新建图层，命名为 **`RoadsA_B`** → 移除父图层 `Roads`。

**⚠️ 教程给的重要排错提示（原文）**：

> "Note: If the blue text, if **records to be processed = 0 or 1**, then you need to **Clear** selected features first, i.e. **Map → Selection group → Clear**"

> 📎 背景补充（**为什么会出现这个现象**）：`Select by Attributes` 有一个 **Selection type（选择类型）**参数，默认是 **New selection（新建选择）**，但当图层上已有活动选择集时，工具面板顶部的蓝色提示会显示「x records will be processed」，表示它**只在当前选择集的范围内**查询。如果上一步的选择集只剩 1 条要素，新查询自然最多只能返回 1 条。**先 Clear 掉旧选择，再查询。**

**结果**：地图上只剩 **A 路（红色）**与 **B 路（绿色）**。

**➡️ Save your project.**（教程明确要求，此处存一次盘）

### 5.6 步骤 4：选址准则（教程 §4，本 practical 的核心）

> The final site selection must consider that a wind turbine **cannot be within**:
> - **100 m** of a **road** or **river**
> - **500 m** of a **built-up area**, or an **Area of Outstanding Natural Beauty (AONB)**, or a **Site of Special Scientific Interest (SSSI)**

整理成表：

| # | 准则（禁建条件） | 缓冲距离 | 对应图层 | 理由（📎 部分为补充） |
|---|---|---|---|---|
| 1 | 距**道路** | **100 m** | `RoadsA_B` | 📎 倒塌半径、施工通道、道路使用者安全 |
| 2 | 距**河流** | **100 m** | `Rivers` | 📎 水文与生态保护、基础施工限制 |
| 3 | 距**建成区** | **500 m** | `Urban_Areas` | 噪声、闪影（shadow flicker）、居民反对 |
| 4 | 距 **AONB** | **500 m** | `AONB` | 景观保护（教程 §1 明说 AONB 不欢迎风机） |
| 5 | 距 **SSSI** | **500 m** | `SSSI` | 生态/科学价值保护 |

**⚠️ 注意**：教程 §4 只列了这 5 条**排除性**准则，**没有**把「风速」「坡度」「离电网距离」作为准则计算。见 §5.16 的重要说明。

### 5.7 步骤 5：建缓冲区（教程 §4.1）

**工具**：**Pairwise Buffers**（教程用名）
**路径**：**Analysis → Tools**（Geoprocessing 窗格搜索）

> 📎 背景补充：ArcGIS Pro 中该工具的**正式名称是 `Pairwise Buffer`（单数）**，位于 **Analysis Tools → Pairwise Overlay** 工具集。同课程 `Practical 2`（Carlisle flood map）里写的就是单数的 "Pairwise Buffer"，并解释了它与普通 `Buffer` 的区别：「This has the **same functionality as Buffer**, just utilises **parallel processing** to speed up the operation.」——即功能相同、支持并行加速。见勘误表。

**逐个建 5 个缓冲区**：

| Input Features | Distance | 建议输出名（📎，教程未指定） |
|---|---|---|
| `RoadsA_B` | **100 Meters** | `Buf_Roads_100` |
| `Rivers` | **100 Meters** | `Buf_Rivers_100` |
| `Urban_Areas` | **500 Meters** | `Buf_Urban_500` |
| `SSSI` | **500 Meters** | `Buf_SSSI_500` |
| `AONB` | **500 Meters** | `Buf_AONB_500` |

**⚠️ 教程 §4.1 第一句写的是「create a 100 m buffer around the `Roads` layer」，但 `Roads` 在 §3 末已被移除（"you can now remove the parent layer Roads"）。实际应缓冲 `RoadsA_B`。见勘误表。**

**整理**：新建 **New Group Layer**，命名 **`Pairwise_Buffers`**，把 5 个缓冲图层都放进去。

**符号化提示（教程原话）**：「I have changed the colour scheme to be **the same for all layers**」——把 5 层设成同色，视觉上就是一整片「禁建区」。

> 📎 背景补充（**教程没写但会影响结果的参数**）：
> - **Distance Unit（距离单位）** 必须选 **Meters**。如果输入图层是地理坐标系，单位下拉会变成 Decimal Degrees，做出来的缓冲区完全错误。**OS 数据是 British National Grid（EPSG:27700，单位米），一般没问题，但要确认。**
> - **Dissolve Type（融合类型）**：`NONE`（默认，保留每条要素各自的缓冲多边形，会大量重叠）vs `ALL`（把所有缓冲融合成一个多部件多边形）。
>   道路有几万条线，用 `NONE` 会产生几万个重叠多边形，后续 `Erase` 会非常慢。**建议对道路和河流设 `Dissolve Type = ALL`。** 教程未提及。
> - `Practical 2` 里也提过同样的技巧：「to remove the overlapping regions in the river buffer you can recalculate it selecting **Dissolve all output features into a single feature**」。

**阶段性成果（教程原话）**：

> "The map shows **all the areas in Cornwall where planning laws prevent the construction of wind turbines**."

### 5.8 步骤 6：合并成单一禁建层（教程 §4.2）

**工具**：**Merge**（在 Geoprocessing 窗格搜索）

| 参数 | 值 |
|---|---|
| **Input Datasets** | 5 个缓冲图层全选 |
| **Output Dataset** | **`No_Build`** |

点 **Run**。

> 📎 背景补充：`Merge` 位于 **Data Management Tools → General → Merge**。它**只是把多个要素类的要素堆到一个要素类里，不做几何求并**——重叠的多边形仍然是重叠的多个多边形。若要真正合并成无重叠的单一面，应再跑一次 **`Dissolve`**（Data Management Tools → Generalization → Dissolve）。
>
> 对本练习而言，因为下一步 `Erase` 是「减掉所有覆盖到的地方」，重叠与否不影响**结果的正确性**，只影响**运算速度**。但如果你想统计「禁建区总面积」，**不 Dissolve 就会重复计算重叠部分，面积会被严重高估**——这是一个很典型的陷阱。

### 5.9 步骤 7：擦除得到可建区（教程 §4.2）

**逻辑（教程原话）**：

> "We are going to **subtract the No-Build areas from the County_Boundary**."

**工具**：**Erase**

| 参数 | 值 |
|---|---|
| **Input Features** | **`County_Boundary`**（被减数：整个 Cornwall） |
| **Erase Features** | **`No_Build`**（减数：禁建区） |
| **Output Feature Class** | **`Build`** |

关掉 `No_Build` 的可见性，地图上剩下的（教程作者版本里是**粉色**）就是**所有可以建风机的地方**。

> 📎 背景补充（**重要的许可证问题**）：`Erase` 位于 **Analysis Tools → Overlay → Erase**，**需要 ArcGIS Pro Advanced 级别许可**。如果你的许可是 Basic 或 Standard，工具会是灰的。替代方案：
> 1. 用 **`Symmetrical Difference`** 或 **`Update`**（同样可能需要 Advanced）。
> 2. **免费的等价做法**：`Select by Location`（Relationship = `Intersect`，Selecting = `No_Build`）选出与禁建区相交的部分，然后 **Switch Selection（反选）**——但这只在要素是离散多边形时有效，对本例的「一整块县界」不适用。
> 3. **最稳的替代**：把问题转成栅格 —— 把 5 个缓冲区 `Polygon to Raster`，再用 `Con` / 栅格代数做布尔运算。这也正是标准的 **suitability analysis（适宜性分析）**做法。

**➡️ 概念小结：`Buffer → Merge → Erase` 这条链，就是 W04 讲的 vector overlay 里的 `difference（差集）`运算在真实业务里的形态。**

### 5.10 步骤 8：换底图，改善可视化（教程 §4.3）

1. **Ribbon → Map → Basemap → Imagery**（换成航空影像底图）
2. 把 **`Build` 图层的 transparency（透明度）调到约 50%**
   > 📎 路径：选中 `Build` 图层 → **Feature Layer 上下文选项卡 → Appearance → Transparency**，或在 Symbology 窗格里设。
3. **Zoom / Pan** 浏览，人工检视候选地块。

**目的**：叠上真实影像后，你能看出每块「可建区」实际上是什么——农田？灌丛？采石场？这直接对应 Challenge Q1。

### 5.11 步骤 9：对照现有风电场（教程 §5）

**添加图层**：ArcGIS Online 上的 **`Onshore_Windfarms`**。

- **绿点 = 现有风电场**（展开图层可看图例）
- 放大点击绿点可以看**属性信息**
- 在影像底图上放到最大，**能看到真实的风机本体**

**四道 Challenge（教程原文）**：

| 题号 | 题目 | 📎 思路提示 |
|---|---|---|
| **Q1** | What type of **land use** covers most of the potential site areas you have identified? | 切到 Imagery 底图目视判读。Cornwall 内陆的可建区基本落在**农业用地/牧场**和**荒原（moorland）**上 |
| **Q2** | The highest wind speeds are likely to be **close to the coast**; how much of the **coastal area** is available for wind turbine developments? | 注意 Cornwall 海岸线几乎全被 **AONB** 覆盖，而 AONB 有 500 m 缓冲 → **沿海可建区极少**。这正是本练习设计出来要你发现的**根本矛盾：风最好的地方恰恰是最不能建的地方** |
| **Q3** | Apart from those considered already, what **other factors** may influence the siting? | 见下方清单 |
| **Q4** | How do the **locations of existing wind turbines** compare with your map? Are there any **anomalies**? | 你会发现有些现有风机**落在你的禁建区里**。可能原因：建成时间早于现行规划法规；缓冲距离是本练习的简化假定，不是真实法定值；数据精度/时相差异 |

**Q3 的答案清单（📎 大部分为补充，材料只给了问题）**：

- **风速与风况**（wind speed / wind resource）——最根本的一条，本练习**完全没有纳入**
- **坡度与地基条件**（slope、地质、承载力）
- **到电网接入点的距离**（grid connection / substation proximity）——常是决定成本的关键
- **施工道路的可达性**（大型部件运输需要转弯半径足够的道路，本练习反而把道路当成排除项）
- **国家公园与其他法定保护地**（教程 §1 提了 national parks，但数据里没加）
- **鸟类迁徙路线与蝙蝠栖息地**（教程 §1 提了 migratory birds）
- **低飞航空器与雷达干扰**（教程 §1 提了 low flying aircraft）
- **考古与文化遗产**（scheduled monuments、listed buildings）
- **噪声与阴影闪烁（shadow flicker）的具体建模**
- **土地所有权与地方规划意见**
- **累积视觉影响（cumulative visual impact）**——多个风电场一起看的效果
- 教程 §7 自己也提了一条：**风电场之间不能挨太近**（"it must not be near another wind farm"）

### 5.12 步骤 10：加载 DEM 并做山体阴影显示（教程 §6）

**数据**：

> "A DEM raster has been created for you. It is based on the **OS Terrain 5 m resolution DEM** for the UK ... it can be downloaded from **Digimap**."

**添加路径（教程原文）**：**Add Data → ArcGIS Online → My Organisation → `DEM_StCM`**（Canvas Week 7 也有）

**覆盖范围**：**St Columb Major** 村周边（Cornwall 的一个约 **4,500 人**的镇）。

**符号化步骤**：

1. **右键 Contents Pane 里的 `DEM_StCM` → Symbology**
2. 展开 **Primary Symbology**，选 **Shaded Relief**
3. 设置 **Colour scheme（色带）**——教程推荐了一个特别适合表达高程的色带（截图，未给名称）

**基本判读规则（教程原文）**：

> "Remember **light areas are high elevation, dark areas are low elevation**."

> 📎 背景补充（**这里教程的说法需要澄清**）：
> - 上面那句「亮 = 高、暗 = 低」描述的是 DEM 的**默认灰度拉伸（Stretch）显示**，**不是 hillshade**。
> - **Hillshade 的亮暗取决于坡向与光照方向，不是高程** —— 一个低洼处的西北向坡面可以比高处的东南向坡面更亮。
> - `Shaded Relief` 这种 Primary Symbology 实际上是**把彩色高程带与山体阴影效果合成显示**，所以两种规则同时在起作用：**整体色调反映高程，明暗浮雕反映坡向。**
> - **教程 §6 的标题是 "Create a hill shade of the DEM"，但实际操作只是改了 Symbology，并没有用 Spatial Analyst 的 `Hillshade` 工具生成新栅格。** 如果后续要把山体阴影当数据用（比如叠加透明度、参与运算），必须走 **Spatial Analyst Tools → Surface → Hillshade**。见勘误表。

### 5.13 步骤 11：新建点图层并数字化风机位置（教程 §7）

**规则（教程原文）**：

> "Each point you identify represents a **single wind farm** ... Each wind farm you identify **must be in an area you have identified in the "Build" layer** and it **must not be near another wind farm**."

**建要素类**：

1. 在 **Geoprocessing Pane** 搜索 **Create Feature Class**
2. **Feature Class Name** → 例如 **`turbines`**
3. **Coordinate System** → **设为与 `DEM_StCM` 图层相同**，应为 **British National Grid**
4. **Geometry Type** → **Point**
5. **Run**

> 📎 背景补充：
> - `Create Feature Class` 位于 **Data Management Tools → Feature Class → Create Feature Class**。它有一个**必填参数教程没提**：**Feature Class Location（要素类位置）**——必须指向一个**文件地理数据库（.gdb）**，通常就是工程默认的 `<ProjectName>.gdb`。
> - 「British National Grid」的完整名称是 **OSGB 1936 / British National Grid**，**EPSG:27700**。这是英国 OS 数据的标准投影坐标系，单位为**米**。
> - **为什么必须和 DEM 一致**：`Geodesic Viewshed` 要求观察点与输入栅格在同一坐标系下配准；坐标系不一致轻则报错，重则算出完全错位的可视域。

**数字化点**：

1. **Ribbon → Edit → Create**（打开 Create Features 窗格）
2. 选中 `turbines` 模板里的 **point 工具**，在屏幕上点击即添加点
3. **教程要求**：先**数字化 St Columb Major 以北的两个现有风机**（`Onshore_Windfarms` 图层上的两个绿点）
4. **Ribbon 上点 Save** 保存编辑

**⚠️ 教程强调的排错点（原文）**：

> "You may find that the **last point you digitised is still selected**, so to clear the selection, right-click the `turbines` layer in Contents Pane → **Selection → Clear Selection**. (**if you do not clear the selection, then if you run any tools subsequently, only the selected point will be used for analysis**)"

**→ 这是本 practical 第二个「选择集陷阱」（第一个在 §5.5）。ArcGIS Pro 的所有地理处理工具默认只处理「当前选择集」，不是整个图层。这条规则值得单独记住。**

### 5.14 步骤 12：可视域分析（教程 §8）

**目标（教程原话）**：

> "Now we need to calculate the **area from which the new turbines will be visible**."

**工具**：在 **Geoprocessing Pane** 搜索 **Geodesic Viewshed**

> 📎 该工具在 ArcGIS Pro 中现名 **`Viewshed 2`**，位于 **Spatial Analyst Tools → Visibility → Viewshed 2**，**需要 Spatial Analyst 扩展**。讲义链接的 `viewshed-2.htm` 就是它。

**必填参数**：

| 参数 | 值 |
|---|---|
| **Input raster** | **`DEM_StCM`** |
| **Input point or polyline observer features** | **`turbines`** |
| **Output raster** | 例如 **`viewshed_DEM1`** |

**Viewshed Parameters（教程逐条解释，需要理解每一条）**：

| 参数 | 教程说明 | 本练习设置 |
|---|---|---|
| **Refractivity coefficient** | "used in specialist applications involving **non-visible parts of the spectrum**, such as **siting mobile phone masts**" | **忽略**（用默认） |
| **Analysis method** | 两个选项：**`All sightlines`**（默认，逐格网算，精确）／**`Perimeter sightlines`**（"a **much quicker but less accurate** calculation that works out which pixels along the **study area perimeter** are visible, radiating these back to observer features"） | **`All sightlines`** |
| **Analysis type** | **`Frequency`** — "the **number of visible observer points** will be calculated" | **`Frequency`** |
| **Vertical error** | "If we knew the **Root Mean Square Error (RMSE)** of the elevation values in our DEM, it could be incorporated into viewshed calculations via this setting" | **不设** |

**Observer Parameters（本 practical 最容易搞混的地方，教程也承认了）**：

| 参数 | 教程原文解释 | 值 |
|---|---|---|
| **Surface offset** | "will '**raise' the surface of the DEM** by a given amount. Enter **1.6** for this as an approximate **height in metres of somebody standing in the landscape**" | **1.6** |
| **Observer offset** | "raises the surface **where the wind turbines are present**. Since our turbines are **25 metres tall**, enter **25** here (**yes – it is a bit confusing that the software terms our turbines 'observer points'**)" | **25** |
| **Observer elevation** | "enables us to set the height of our turbines as an **absolute elevation value above sea level – not what we want to do here**" | **不用** |
| **Radii（Inner / Outer radius）** | "can be used to **limit the viewshed calculations** to just part of a study area, but **we will not use them here**" | **不用** |

**⚠️ 这里的角色反转必须想清楚：**

- **风机 = observer（观察者）** —— 所以 **Observer offset = 25 m（风机高度）**
- **地面上的人 = target（被看到的位置）** —— 所以 **Surface offset = 1.6 m（人的眼高）**
- **可见性是对称的**：「从风机能看到某格网」 ⟺ 「站在那个格网上的人能看到风机」。所以尽管软件把风机称为「观察者」，实际回答的问题是「**站在哪些地方的人能看见风机**」。
- 教程自己都加了一句 "yes – it is a bit confusing"，说明这确实是最容易绕晕的一点。

点 **Run**。教程警告：

> "**be patient this may take some time**, as the calculations are fairly computer-intensive."

**结果判读（教程原文）**：

> "The resultant raster grid indicates **how many of the input features (wind turbines) are visible from each grid cell**. A value of '**no data**' (blank areas) means that the grid cell **cannot be seen by any** of the turbines, a value of **one (yellow)** means visible from **one** turbine, **two (brown)** means visible from **two** turbines, and so on."

**最终结论（教程）**：

> "It shows that **one of the two existing wind farms (pins) is visible in parts of the village of St Columb Major**."

用 **Map ribbon → Explore 工具**点击栅格查看各处的具体值。

> 📎 背景补充（**对上面「no data」说法的存疑**）：在 ArcGIS Pro 的 `Viewshed 2`（Geodesic Viewshed）中，`Analysis type = FREQUENCY` 时，**不可见的格网通常被赋值为 `0`，而不是 NoData**；NoData 一般只出现在输入 DEM 本身是 NoData 的地方。屏幕上之所以看起来是「空白」，可能是因为默认符号化把 0 值渲染成了透明或与底图同色。**判读时最好用 Explore 点一下确认到底是 0 还是 NoData** —— 这在写报告统计「不可见面积」时会造成显著差异。见勘误表。

### 5.15 Challenge Q5 / Q6 与 Homework Challenge

| 题 | 题目（原文） | 📎 思路 |
|---|---|---|
| **Q5** | "The viewshed shows that **one** of the wind farms is visible in St Columb Major. **Work out a method of determining which one** of the wind farms this is." | 三种做法：① **把两个点分开跑两次 viewshed**，各得一张图，看哪张覆盖了村子；② 把 **Analysis type 改成 `Observers`** —— 这个模式的输出会用**位编码**记录「具体是哪几个观察点看得见」，直接给出答案；③ 用 **Construct Sight Lines + Line of Sight** 从村子分别向两个风机拉视线，看哪条通 |
| **Q6** | "Modify your `turbines` point layer to include a **proposed new wind farm site south of St Columb Major**. Use your **`Build`** layer to help identify this site. Run a viewshed analysis to determine if your proposed wind farm **will be visible from the village**." | 回到 **Edit → Create**，在 `Build` 图层覆盖到的、村子以南的地块上点一个新点 → **Save 编辑** → **清除选择集**（否则只会算这一个点）→ 重跑 `Geodesic Viewshed`。⚠️ 记得新点也要保证「不靠近现有风电场」 |
| **Homework** | 加载 ArcGIS Online 的 **`Feasibility Map_WFL1`** 图层，"a more comprehensive assessment of renewable energy locations in Cornwall ... **also includes locations of solar photovoltaic farm locations**" | 把它和你自己的 `Build` 图层叠起来对比。**你的版本只用了 5 条排除准则，专业版会纳入风速、电网、坡度、雷达等** —— 差异本身就是最好的学习材料 |

### 5.16 ⚠️ 重要说明：本 practical 用的是「布尔排除」，不是「加权叠加」

这是复习时必须想明白的一件事，否则会把本周和 W04 的知识混起来。

**教程实际做的（Boolean / binary exclusion，布尔排除法）**：

```
县界  −  (道路100m ∪ 河流100m ∪ 建成区500m ∪ SSSI 500m ∪ AONB 500m)  =  可建区
```

- 每条准则的结果只有**两个值**：能建 / 不能建
- 五条准则**同等重要**，没有权重
- 用的是**矢量**运算（Buffer → Merge → Erase）
- 输出是一个**二值的多边形图层**

**标准的多准则适宜性分析（Weighted Overlay / MCDA，加权叠加）会怎么做**（📎 以下整段为背景补充，教程完全没有做，但老师在讲 Utcubamba 案例时描述的正是这套方法）：

1. **准备各准则的连续栅格**：风速栅格、坡度栅格、到电网的欧氏距离栅格、到居民区的距离栅格……
   工具：`Slope`、`Euclidean Distance`、`Aspect` 等
2. **Reclassify（重分类）**：把每个栅格**统一重分类到同一个尺度**（例如 1–9 分，9 = 最适宜）
   工具：**Spatial Analyst Tools → Reclass → Reclassify**
   **⚠️ 这一步是最容易出错的地方**——如果一个准则分 1–9、另一个分 0–100，加权结果毫无意义
3. **赋权重**：给每条准则一个百分比权重（合计 100%），可用 **AHP（层次分析法）**等方法定权
4. **Weighted Overlay / Weighted Sum**：
   工具：**Spatial Analyst Tools → Overlay → Weighted Overlay**（要求输入为整型、同一评价尺度）或 **Weighted Sum**（允许浮点）
5. **叠加「硬约束」掩膜**：把绝对禁建区（保护区、水体）以 **Restricted** 或乘以 0 的方式排除
6. 输出一张**连续的适宜性得分栅格**，再取高分区作为候选点

**两者的对比**：

| | 布尔排除（本 practical） | 加权叠加（Utcubamba 案例 / 标准 MCDA） |
|---|---|---|
| 数据模型 | 矢量 | 栅格 |
| 输出 | 能建 / 不能建（二值） | 适宜性得分（连续） |
| 准则重要性 | 全部相同 | 可加权 |
| 优点 | 直观、快、法规约束天然是二值的 | 能表达「较好/更好」的程度差异 |
| 缺点 | **无法区分「刚好合规」与「非常理想」** | 权重主观，结果对权重敏感 |
| 老师的话 | — | "you can **play around with the weighting** to see what the effects are in the model" |

**→ 复习时的正确表述：本 practical 完成的是「约束筛选（constraint mapping）」这一半，加权评分那一半交给了 Challenge Q3 让你自己想。** 如果考题问「你会怎么改进这个选址分析」，把上面那 6 步答出来就是满分答案。

### 5.17 操作流水线速查（一页纸版）

```
【阶段一：裁研究区】
 ①  Attribute Table 找字段 CTYUA21NM
 ②  Map ▸ Select by Attributes ▸ CTYUA21NM = 'Cornwall' ▸ Run
 ③  右键图层 ▸ Selection ▸ Make Layer From Selected Features ▸ 改名 County_Boundary
 ④  右键 Map ▸ New Group Layer ▸ 命名 Cornwall ▸ 放入
 ⑤  移除父图层

【阶段二：裁 5 个专题图层】
 ⑥  Map ▸ Select by Location
       Roads      : OS Open Roads (Road Link)  | Intersect            → Roads
       Rivers     : OS Open Rivers             | Intersect            → Rivers
       AONB       : AONB                       | Have their center in → AONB
       SSSI       : SSSI                       | Within               → SSSI
       Urban      : Built Up Areas             | Within               → Urban_Areas
 ⑦  每个都 Make Layer From Selected Features ▸ 改名 ▸ 移除父层 ▸ 放入 Cornwall 组

【阶段三：筛 A/B 级路】
 ⑧  Map ▸ Selection ▸ Clear（先清空旧选择！）
 ⑨  Map ▸ Select by Attributes ▸ Input Rows = Roads
       class = 'A Road'  Or  class = 'B Road'      ← 必须用 Or
 ⑩  Apply ▸ OK ▸ 新建图层 RoadsA_B ▸ 移除 Roads
 💾 Save project

【阶段四：建禁建区】
 ⑪  Pairwise Buffer × 5
       RoadsA_B    100 m
       Rivers      100 m
       Urban_Areas 500 m
       SSSI        500 m
       AONB        500 m
     （📎 建议 Dissolve Type = ALL，Distance Unit = Meters）
 ⑫  New Group Layer「Pairwise_Buffers」▸ 全部放入 ▸ 统一配色
 ⑬  Merge ▸ Input = 5 个缓冲层 ▸ Output = No_Build ▸ Run

【阶段五：得可建区】
 ⑭  Erase ▸ Input Features = County_Boundary
              Erase Features = No_Build
              Output = Build              （📎 需 Advanced 许可）
 ⑮  关掉 No_Build 可见性
 ⑯  Map ▸ Basemap ▸ Imagery ；Build 图层 Transparency ≈ 50%

【阶段六：对照与地形】
 ⑰  Add Data ▸ ArcGIS Online ▸ Onshore_Windfarms（绿点 = 现有风电场）
 ⑱  Add Data ▸ ArcGIS Online ▸ My Organisation ▸ DEM_StCM
 ⑲  右键 DEM_StCM ▸ Symbology ▸ Primary Symbology = Shaded Relief ▸ 选色带

【阶段七：数字化 + 可视域】
 ⑳  Create Feature Class ▸ Name = turbines
                          ▸ Coordinate System = DEM_StCM（British National Grid）
                          ▸ Geometry Type = Point ▸ Run
 ㉑  Edit ▸ Create ▸ 点工具 ▸ 数字化 St Columb Major 以北的 2 个现有风机
 ㉒  Ribbon ▸ Save（保存编辑）
 ㉓  右键 turbines ▸ Selection ▸ Clear Selection  ← 不清会只算 1 个点！
 ㉔  Geodesic Viewshed（= Viewshed 2）
       Input raster                = DEM_StCM
       Observer features           = turbines
       Output raster               = viewshed_DEM1
       Analysis method             = All sightlines
       Analysis type               = Frequency
       Observer offset  (OFFSETA)  = 25    ← 风机高度
       Surface  offset  (OFFSETB)  = 1.6   ← 人的眼高
       Observer elevation / Radii  = 不用
 ㉕  Run（耐心等）▸ Explore 工具点击查看栅格值
       值 = 1 → 能看见 1 台；值 = 2 → 能看见 2 台
```

---

## 六、易错点 / 重点难点

### 6.1 数据模型与数据源类

| # | 易错点 | 正确理解 |
|---|---|---|
| 1 | **DSM 与 DTM 混用导致坡度虚高** | 用 DSM 算坡度，**树冠边缘和建筑立面会被当成近乎垂直的悬崖**，森林区和城区的坡度被系统性高估。做坡度、做水文，**必须用 DTM/裸地面 DEM**；做可视域和太阳辐射（要考虑遮挡）时才可能需要 DSM。**materials 全篇只说 "DEM"，不代表这个区分不重要。** |
| 2 | 以为「DEM 就是一种数据」 | DEM 是**表达方式**不是数据源。同一片地形可以由 LiDAR、摄影测量、InSAR、雷达测高、地面测量做出 DEM，**精度、误差结构、含不含地物完全不同**。 |
| 3 | 忽略**分辨率对结果的影响** | 格网越大坡度越平（见 §3.1 的 Horn 公式，cell size 在分母）。**同一片山地用 5 m 和 50 m DEM 算出的坡度分布完全不同**，直接影响滑坡风险、适宜性评分。老师专门强调「it's something we **always** need to consider」。 |
| 4 | 认为 TIN 一定比 DEM 好（"矢量更精确"） | **平坦地形上 TIN 反而更差**——大三角形会把细微起伏抹平（"tends to even out things"），且外观不真实。**水文分析根本不用 TIN。** |
| 5 | 混淆 hard 与 soft breakline | **Hard = 坡度不连续（湖岸、陡坎）；Soft = 坡度连续但需要被表示（道路、深泓线）**。老师给的例子（红线的路 = soft，蓝色的湖 = hard）是最好的记忆锚点。 |

### 6.2 一阶属性类

| # | 易错点 | 正确理解 |
|---|---|---|
| 6 | **坡度百分比与度数混淆**；以为 100% = 90° | **45° = 100%**。百分比 = 100·tan(度)。百分比**无上界**，度数上界 90°。工具输出默认单位要确认（ArcGIS `Slope` 工具的 `Output measurement` 参数有 `DEGREE` 和 `PERCENT_RISE` 两个选项）。 |
| 7 | **坡向是圆形数据，不能取算术平均** | 355° 和 5° 的算术平均是 180°（正南），**完全反了**。必须用向量平均（见 §3.2）。同理，**坡向不能做普通标准差、不能直接做 IDW 插值、不能直接进加权叠加**——若要用，通常先转成「北向度 = cos(aspect)」「东向度 = sin(aspect)」这样的连续量，或按 8 方位重分类成类别。 |
| 8 | 忘记平坦格网的坡向是 **−1** | 直接把 aspect 栅格拿去算平均或重分类，−1 会被当成一个真实方位混进去。**重分类时要单独处理 −1（Flat）这一类。** |
| 9 | **profile 与 plan curvature 记反** | **Profile = 沿最大坡降方向（顺水流）→ 管加速/减速 → 侵蚀 vs 沉积**；**Plan = 垂直于最大坡降方向（横切）→ 管辐合/辐散**。老师的记法：plan 就想成 **convergence / divergence** 就行。 |
| 10 | 曲率符号记反 | Esri 传统 `Curvature` 工具：**profile 负 = 上凸（山脊，加速侵蚀）、正 = 上凹（坡脚，减速沉积）**。⚠️ ArcGIS Pro 3.x 的 `Surface Parameters` 工具符号相反，跨工具比较前先确认。 |
| 11 | 把「profile curvature = 最大坡度」当定义 | **讲义那句 "Profile curvature = maximum slope of this surface" 与老师的口头复述都是不严谨的表述。** 正确定义是讲义黑体那句：「the **rate of change of slope** in the direction of the maximum slope」——是**坡度的变化率**（二阶导），不是坡度本身。见勘误表。 |

### 6.3 水文分析类

| # | 易错点 | 正确理解 |
|---|---|---|
| 12 | **不填洼直接做流向 → 河网断裂** | 这是本周最强调的一条。Sink 会让水「掉进去出不来」，得到的河网短碎、不连通、走向诡异。**Fill 永远是第一步。** |
| 13 | 无脑全填 | Fill 会把**真实存在的**深洼（sinkhole、火山口、采石场、冰蚀湖盆）一并填掉。**用 `Z limit` 参数只填浅的假洼地**（📎，materials 未提）。 |
| 14 | 以为 **spike 也能被 Fill 处理** | **Fill 只处理 pit（洼地），不处理 spike（尖峰）。** 尖峰要靠平滑滤波或人工编辑去除。老师顺口说的 "sinks are pits or sometimes they're spikes" 在概念上不准确——**spike 不是 sink**。见勘误表。 |
| 15 | **D8 算坡度时忘记对角要除以 √2** | 只比高差会系统性偏向对角方向。**正交距离 = 1 × cell size，对角距离 = √2 × cell size。** 老师的 67/53/44 例子就是为这个设计的。 |
| 16 | **D8 编码记成 1–8** | 是 **1, 2, 4, 8, 16, 32, 64, 128**（2 的幂次），**从正东开始顺时针**。用 2 的幂次是为了支持位运算。 |
| 17 | **流量累积阈值随意取** | 阈值低 → 河网过密（把坡面细沟也画成河）；阈值高 → 河网过疏（只剩主干，支流全丢）。**阈值必须结合实际地形、气候与野外验证来定**，老师明说这是「need to go and do a ground survey to verify」的环节。**报告里必须写明用了什么阈值以及为什么。** |
| 18 | 忘记 `Snap Pour Point` | 手点的出水口若偏离高流量累积格网哪怕 1 格，`Watershed` 会输出一个只有几个格网的荒谬流域。（📎 materials 未提及此工具） |
| 19 | 混淆 flow accumulation 的「0」含义 | **0 不是「没数据」，而是「没有任何上游格网汇入」= 分水岭/山脊。** 讲义原文：「zero values = ridgelines」。 |

### 6.4 可视域分析类

| # | 易错点 | 正确理解 |
|---|---|---|
| 20 | **忘设观察者高度（offset）** | 不设 offset 相当于观察者的眼睛贴在地面上，viewshed 会**严重偏小**且形态怪异。本 practical 里若忘了填 25，风机就成了一根贴地的杆子。 |
| 21 | **Observer offset 与 Surface offset 搞反** | **Observer offset (OFFSETA) 加在观察点上**（本例 = 风机 25 m）；**Surface offset (OFFSETB) 加在每一个被观察的地面格网上**（本例 = 人眼高 1.6 m）。填反了结果会显著不同。 |
| 22 | 把 **Observer elevation** 当成 offset 用 | Observer elevation 是**绝对海拔**（如「海拔 180 m」），不是「地面以上 25 m」。教程明确说了 "**not what we want to do here**"。 |
| 23 | 混淆 **line of sight** 与 **viewshed** | **Line of sight = 点到点、输出一条分段着色的线 + 一张剖面图**；**Viewshed = 点到面、输出一张栅格**。 |
| 24 | 把 **Viewshed 2** 理解成「两个观察者」 | "2" 指的是**工具第二代**（支持地球曲率、折射、多种分析类型），不是观察者数量。**Viewshed 2 一次就能处理任意多个观察点。** |
| 25 | 用 DTM 做 viewshed 却当成真实可见性 | 本 practical 用 OS Terrain 5（裸地面），**没有把树林和建筑的遮挡算进去 → 算出的可视域是保守偏大的**。真实的视觉影响评估应该用 DSM 或至少加上林地遮挡图层。 |
| 26 | 误读 Frequency 输出的 0 与 NoData | **值 1 = 能看到 1 台，值 2 = 能看到 2 台。** 「看不见」通常是 **0** 而非 NoData（见 §5.14 的存疑说明）。统计「不可见面积」时必须先确认。 |

### 6.5 栅格环境与叠加类

| # | 易错点 | 正确理解 |
|---|---|---|
| 27 | **Environment 里的 extent 与 cell size 未统一** | 📎 多个栅格参与运算时，若 **Processing Extent（处理范围）**和 **Cell Size（像元大小）**不一致，ArcGIS 会自动重采样并取交集范围，导致**结果范围莫名变小、精度莫名下降**。正确做法：在 **Geoprocessing 窗格 → Environments 选项卡**里显式设置 `Extent`、`Cell Size`、`Snap Raster`、`Mask`、`Output Coordinate System` 五项。 |
| 28 | **加权叠加前各准则未统一重分类尺度** | 📎 一个图层是 1–9 分、另一个是 0–100，加权求和的结果完全被后者主导。**必须先 `Reclassify` 到同一评价尺度**（Weighted Overlay 工具本身就要求输入是同一 evaluation scale 的整型栅格）。 |
| 29 | **`Merge` 之后不 `Dissolve` 就统计面积** | `Merge` 不做几何求并，重叠部分会被**重复计算**，禁建区总面积严重高估。 |
| 30 | **Select by Location 三种 Relationship 乱用** | 线用 `Intersect`（否则跨界的线全丢）；大面用 `Have their center in`（否则要么全丢要么带进邻郡）；小面可用 `Within`。选错会静默地改变研究区范围，**且不会报错**。 |
| 31 | **两条属性表达式用 `And` 连接** | `class = 'A Road' And class = 'B Road'` 返回 0 条。**必须用 `Or`。** |
| 32 | **忘记清除选择集就跑工具** | ArcGIS Pro 的地理处理工具**默认只处理当前选择集**。教程在两个地方都专门警告过（§3 的 "records to be processed = 0 or 1" 和 §7 的 "only the selected point will be used"）。**跑任何工具前先看图层有没有高亮的选中要素。** |
| 33 | **坐标系不统一** | 缓冲距离单位、栅格叠加、viewshed 都要求投影坐标系。英国 OS 数据统一用 **British National Grid（EPSG:27700，单位米）**。若图层是 WGS84 经纬度，Buffer 的距离单位会变成度，结果完全错误。 |

---

## 七、本周术语表

### 7.1 地形与表达方式

| 中文 | 英文 | 说明 |
|---|---|---|
| 地形分析 | **Terrain analysis** | 用地形数据推导地表形态及其对环境过程的影响 |
| 椭球体 | **Spheroid** | 纯几何的地球模型 |
| 大地水准面 | **Geoid** | 重力等位面（equipotential surface），通常取平均海平面 |
| 地表／地形 | **Land surface / Terrain** | 真实地表，复杂度最高 |
| 等高线 | **Contours** | 矢量线表达 |
| 高程点 | **Spot heights** | 矢量点表达 |
| 数字高程模型 | **DEM** — Digital Elevation Model | 栅格；本周的核心数据形式（泛称） |
| 数字地形模型 | **DTM** — Digital Terrain Model | 📎 裸地面高程，不含地物 |
| 数字表面模型 | **DSM** — Digital Surface Model | 📎 含树冠、建筑等地物 |
| 不规则三角网 | **TIN** — Triangulated Irregular Network | 矢量；相邻不重叠三角形连接 3 个高程点 |
| 点云 | **Point cloud** | LiDAR 的原始形式（老师口头补充） |
| 断裂线 | **Breakline** | 强制 TIN 表面遵循特定形状的线要素 |
| 硬断裂线 | **Hard breakline** | 坡度不连续（湖岸、陡坎） |
| 软断裂线 | **Soft breakline** | 不改变局部坡度（道路、深泓线） |
| 垂直放大 | **Vertical exaggeration** | 剖面图的显示参数（讲义示例 3.0 ×） |
| 空间分辨率／像元大小 | **Spatial resolution / Cell size / Grid size** | 老师强调「always need to consider」 |

### 7.2 数据来源

| 中文 | 英文 |
|---|---|
| 地面测量 | **Ground surveys** |
| 摄影测量 | **Photogrammetry** |
| 雷达测高 | **Radar altimetry** |
| 干涉合成孔径雷达 | **InSAR** — Interferometric Synthetic Aperture Radar |
| 机载激光扫描 | **Airborne laser scanning (LiDAR)** |
| 英国地形数据集 | **OS Terrain 5**（5 m）／📎 **OS Terrain 50**（50 m） |
| 英国校园数据平台 | **Digimap** |
| 📎 全球高程数据集 | **SRTM**、**ASTER GDEM**、**Copernicus DEM** |

### 7.3 地形属性

| 中文 | 英文 | 备注 |
|---|---|---|
| 一阶／基本地形属性 | **Primary terrain attributes** | elevation, slope, aspect, plan & profile curvature |
| 二阶／复合地形属性 | **Secondary / Compound terrain attributes** | 由两个以上一阶属性计算 |
| 高程 | **Elevation** | |
| 坡度 | **Slope** | 度（degree）或百分比（percent） |
| 高差／水平距离 | **Rise / Run** | 坡度公式的分子与分母 |
| 坡向 | **Aspect** | 方位角（azimuth），0–360°，平坦为 −1 |
| 曲率 | **Curvature** | 曲面偏离平面的程度 |
| 剖面曲率 | **Profile curvature** | 沿最大坡降方向的坡度变化率 → 控制加速/侵蚀沉积 |
| 平面曲率 | **Plan / Planform curvature** | 垂直于最大坡降方向 → 控制辐合/辐散 |
| 上凸 / 上凹 | **Convex up / Concave up** | profile curvature 的负值/正值 |
| 辐合 / 辐散 | **Convergence / Divergence** | plan curvature 的含义 |
| 地形剖面 | **Terrain profile / Topographic profile** | |
| 地表粗糙度 | **Surface roughness** | 老师讲 TIN 时用到 |

### 7.4 水文分析

| 中文 | 英文 | 备注 |
|---|---|---|
| 集水区／流域 | **Watershed / Catchment** | |
| 集水区分析 | **Watershed analysis** | |
| 水文调整 | **Hydrological conditioning** | 即检查并处理 sink |
| 水文正确的 DEM | **Hydrologically correct DEM** | |
| 洼地／坑 | **Sink / Pit** | 被更高高程包围的低值区 |
| 尖峰 | **Spike** | 📎 异常高值，**不是 sink**，Fill 不处理 |
| 填洼 | **Fill** | 水文分析第一步 |
| 流向 | **Flow direction** | |
| 📎 D8 算法 | **D8 (Deterministic 8-node) algorithm** | 材料未点名，编码 1/2/4/8/16/32/64/128 |
| 📎 多流向 | **MFD / D-infinity (DINF)** | D8 的改进 |
| 流量累积 | **Flow accumulation** | 高值 = 河道；0 = 山脊线 |
| 流程长度 | **Flow length** | |
| 河流分级 | **Flow order / Stream order** | 📎 Strahler、Shreve |
| 水系／排水网络 | **Drainage network** | |
| 阈值 | **Threshold value** | 讲义示例 1000 / 7000 cells |
| 倾泻点／出水口 | **Pour point / Outlet** | 流域边界上的最低点 |
| 分水岭／山脊线 | **Ridge line** | 流域边界 |
| 水系密度 | **Drainage density** | Utcubamba 案例的准则之一 |
| 地形湿度指数 | **TWI** — Topographic Wetness Index | 📎 公式 ln(a/tanβ) |
| 树枝状水系 | 📎 **Dendritic drainage pattern** | 正常填洼后的河网形态 |

### 7.5 可视性与太阳辐射

| 中文 | 英文 | 备注 |
|---|---|---|
| 可视性分析 | **Visibility analysis** | |
| 视线 | **Line of sight** | 点到点 |
| 可视域 | **Viewshed** | 点到面 |
| 观察点 / 目标点 | **Observer point / Target point** | |
| 可见 / 被遮挡 | **Visible / Obstructed** | 绿 / 红 |
| 半球视域 | **Hemispherical viewshed** | 向上看的鱼眼视图，用于太阳辐射 |
| 天空遮挡角 | **Angle of sky obstruction** | |
| 地平线角 | **Horizon angle** | |
| 太阳轨迹图 | **Sunmap** | 算 direct radiation，依赖纬度 |
| 天空图 | **Skymap** | 算 diffuse radiation |
| 直接辐射 | **Direct radiation** | |
| 散射辐射 | **Diffuse radiation** | 被云和尘埃散射 |
| 反射辐射 | **Reflected radiation** | 被邻近地形反射 |
| 总辐射／全球辐射 | **Global / Total solar radiation** | = 直接 + 散射 + 反射 |
| 夏至 / 冬至 | **Summer / Winter solstice** | |
| 山体阴影 | **Hillshade** | 📎 默认 Azimuth 315°、Altitude 45° |
| 晕渲显示 | **Shaded Relief** | practical 用的 Symbology 选项 |

### 7.6 应用与建模

| 中文 | 英文 |
|---|---|
| 多准则建模 | **Multi-criteria modelling** |
| 权重 | **Weighting** |
| 风险分区制图 | **Risk zoning and mapping** |
| 危险性 / 风险 | 📎 **Hazard / Risk** |
| 邻近性数据 | **Proximity data**（distance to roads / population） |
| 滑坡易发坡 | **Landslide-prone slopes** |
| 洪水建模 | **Flood modelling** |
| 侵蚀风险评估 | **Erosion risk assessment** |
| 地下水补给 | **Groundwater recharge** |
| 地貌制图 | **Geomorphological mapping** |
| 阶地 / 陡崖 / 沙丘 | **Terraces / Scarps / Dunes** |
| 鼓丘 / 冰碛 / 融水通道 | **Drumlins / Moraines / Meltwater channels** |
| 冰下火山锥 | **Subglacial edifices**（火星案例） |
| 形态参数 | **Shape parameters** |
| 可蚀性 | **Erodibility** |

### 7.7 ArcGIS Pro 界面与工具（本周 Practical 出现的全部英文名）

| 类别 | 英文原名 | 中文/说明 |
|---|---|---|
| 界面 | **Ribbon** | 顶部功能区 |
| 界面 | **Contents Pane** | 内容窗格（左侧图层列表） |
| 界面 | **Geoprocessing Pane** | 地理处理窗格（工具搜索与运行） |
| 界面 | **Attribute Table** | 属性表 |
| 界面 | **Group Layer / New Group Layer** | 组图层 |
| 界面 | **Basemap → Imagery** | 底图 → 影像 |
| 界面 | **Transparency** | 透明度 |
| 界面 | **Symbology → Primary Symbology → Shaded Relief** | 符号系统 → 主符号系统 → 晕渲 |
| 界面 | **Colour scheme** | 色带 |
| 界面 | **Explore（Map ribbon）** | 浏览/查询工具 |
| 界面 | **Add Data → ArcGIS Online → My Organisation** | 添加数据 |
| 选择 | **Select by Attributes** | 按属性选择 |
| 选择 | **Select by Location** | 按位置选择 |
| 选择 | **Relationship: Intersect / Within / Have their center in** | 空间关系 |
| 选择 | **Selection → Make Layer From Selected Features** | 由选中要素创建图层 |
| 选择 | **Map → Selection group → Clear / Clear Selection** | 清除选择集 |
| 选择 | **Expression / Input Rows / Input Features / Selecting Features** | 表达式与输入参数 |
| 分析 | **Pairwise Buffers**（正名 **Pairwise Buffer**） | 成对缓冲 |
| 分析 | **Buffer** | 缓冲区 |
| 分析 | **Merge** | 合并（不做几何求并） |
| 分析 | 📎 **Dissolve** | 融合（真正消除重叠） |
| 分析 | **Erase** | 擦除（需 Advanced 许可） |
| 数据 | **Create Feature Class** | 创建要素类 |
| 数据 | **Feature Class Name / Geometry Type / Coordinate System** | 要素类参数 |
| 编辑 | **Edit → Create** | 编辑 → 创建要素 |
| 编辑 | **Digitise / Digitising** | 数字化 |
| 表面 | **Geodesic Viewshed**（＝ **Viewshed 2**） | 测地线可视域 |
| 表面 | 📎 **Hillshade**（Spatial Analyst → Surface） | 山体阴影（生成新栅格） |
| 表面 | 📎 **Slope / Aspect / Curvature / Surface Parameters** | 一阶二阶属性工具 |
| 水文 | 📎 **Fill / Flow Direction / Flow Accumulation / Con / Stream Link / Stream Order / Stream to Feature / Snap Pour Point / Watershed / Basin** | Spatial Analyst → Hydrology 工具集 |
| 叠加 | 📎 **Reclassify / Weighted Overlay / Weighted Sum / Euclidean Distance** | 适宜性分析常用工具 |
| Viewshed 参数 | **Input raster** | 输入栅格 |
| Viewshed 参数 | **Input point or polyline observer features** | 观察点/线要素 |
| Viewshed 参数 | **Output Raster** | 输出栅格 |
| Viewshed 参数 | **Refractivity coefficient** | 折射系数 |
| Viewshed 参数 | **Analysis method: All sightlines / Perimeter sightlines** | 分析方法 |
| Viewshed 参数 | **Analysis type: Frequency / Observers** | 分析类型 |
| Viewshed 参数 | **Vertical error（RMSE）** | 垂直误差 |
| Viewshed 参数 | **Surface offset（📎 OFFSETB）** | 目标面抬升（本例 1.6 m） |
| Viewshed 参数 | **Observer offset（📎 OFFSETA）** | 观察点抬升（本例 25 m） |
| Viewshed 参数 | **Observer elevation（📎 SPOT）** | 观察点绝对海拔 |
| Viewshed 参数 | **Radii（📎 RADIUS1 / RADIUS2）** | 内外半径 |
| Viewshed 参数 | 📎 **AZIMUTH1 / AZIMUTH2 / VERT1 / VERT2** | 水平与垂直视角限制字段 |
| 坐标系 | **British National Grid**（📎 OSGB 1936, EPSG:27700） | 英国国家格网 |
| 图层名 | **County_Boundary / Roads / RoadsA_B / Rivers / AONB / SSSI / Urban_Areas / Cornwall / Pairwise_Buffers / No_Build / Build / turbines / DEM_StCM / Onshore_Windfarms / viewshed_DEM1 / Feasibility Map_WFL1** | 本练习产生的全部图层名 |
| 数据字段 | **CTYUA21NM** | 郡名字段 |

### 7.8 选址背景术语

| 中文 | 英文 |
|---|---|
| 杰出自然景观区 | **AONB** — Area of Outstanding Natural Beauty |
| 特殊科学价值地点 | **SSSI** — Site of Special Scientific Interest |
| 国家公园 | **National park** |
| 建成区 | **Built-up area** |
| 陆上风电场 | **Onshore wind farm** |
| 海上风电 | **Offshore** |
| 转子直径 | **Rotor diameter** |
| 📎 阴影闪烁 | **Shadow flicker** |
| 📎 电网接入 | **Grid connection** |
| 📎 累积视觉影响 | **Cumulative visual impact** |
| 光伏电场 | **Solar photovoltaic farm** |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Practical 7 - Wind turbines.md` §3，提取道路之后 | "Rename the new output layer to **Roads**, move it to the group layer **Cornwall** and remove the **OS Open Rivers** from your project." | **图层名写错**。这一步处理的是道路，此时河流（OS Open Rivers）还没有被提取，若照做会把还要用的源数据删掉。 | 应为 "remove the **OS Open Roads** from your project"。河流的父图层应在下一步（表格中 OS Rivers → Rivers）完成后再移除。 |
| `Practical 7 - Wind turbines.md` §4.1 第一句 | "Our first criteria is that wind turbines cannot be within 100m of a road. We can, therefore, start by creating a 100m buffer around the **Roads** layer." | **与 §3 末尾自相矛盾**。§3 明确要求 "you can now remove the parent layer **Roads** from your project"，此时 `Roads` 已不存在。 | 应缓冲 **`RoadsA_B`**（只含 A、B 级路）。若真去缓冲全部 `Roads`，Cornwall 密集的乡村路网会把几乎整个郡都变成禁建区，练习无法继续。 |
| `Practical 7 - Wind turbines.md` §4.1 | "Use the **Pairwise Buffers** geoprocessing tool" | **工具名多了复数 s**。 | ArcGIS Pro 中正式名称为 **`Pairwise Buffer`（单数）**，位于 Analysis Tools → Pairwise Overlay。同课程 `Practical 2 - Carlisle_Flood_Map` 里写的就是正确的单数形式。搜索时输入复数一般仍能模糊匹配到，但正式引用应用单数。 |
| `Practical 7 - Wind turbines.md` §4.1 与 §3 表格 | §3 输出层名为 **`Urban_Areas`**（复数）／§4.1 写 "**Urban_Area** (500 m buffer)"；§3 输出层名为 **`Rivers`**／§4.1 写 "**River** (100 m buffer)" | **图层名单复数不一致。** | 以 §3 表格创建时的名称为准：**`Urban_Areas`**、**`Rivers`**。属于笔误，不影响操作，但按 §4.1 的名字搜图层会找不到。 |
| `Practical 7 - Wind turbines.md` §3 表格第一行 | Input Features 写作 "**OS Rivers**" | 与 §2 数据清单里的名称 "**OS Open Rivers**" 不一致。 | 以 §2 的 **OS Open Rivers** 为准（这是 Ordnance Survey 开放数据的正式产品名）。 |
| `Practical 7 - Wind turbines.md` §6 章节标题与正文 | 标题 "**Create a hill shade of the DEM**"，但正文只要求 "Expand **Primary Symbology** and select **Shaded Relief**" | **标题与操作不符**。改 Symbology 只是**显示效果**，不会生成任何新数据；真正「create a hillshade」需要跑 Spatial Analyst 的 `Hillshade` 工具产出新栅格。 | 若只需看图，教程的做法足够；若要把山体阴影当数据用（叠加、参与运算、导出），必须用 **Spatial Analyst Tools → Surface → Hillshade**（默认 Azimuth 315°、Altitude 45°）。 |
| `Practical 7 - Wind turbines.md` §6 | "It is based on the **OS Terain 5m reolution** DEM for the UK." | **拼写错误**：Terain → **Terrain**；reolution → **resolution**。 | 正式产品名为 **OS Terrain 5**（5 m 格网 DEM）。 |
| `Practical 7 - Wind turbines.md` §7 | "Set the **Coordinate System** to **DEM_StCM** layer this should be **British national Grid**." | **专有名词大小写不规范。** | 正式名称为 **British National Grid**（完整写法 **OSGB 1936 / British National Grid**，**EPSG:27700**）。 |
| `Practical 7 - Wind turbines.md` §8 结果说明 | "A value of '**no data**' (blank areas on the map below) means that the grid cell **cannot be seen by any** of the turbines" | **存疑（可能不准确）**。在 ArcGIS Pro 的 `Viewshed 2` / `Geodesic Viewshed` 中，`Analysis type = FREQUENCY` 时，**不可见格网通常赋值 `0`**，NoData 一般保留给输入 DEM 本身为 NoData 的位置。屏幕上「空白」很可能是 0 值被渲染为透明所致。 | 判读前用 **Explore** 工具点击空白区确认实际值。这在报告里统计「不可见面积占比」时会造成显著差异——把 0 当 NoData 会让面积统计直接失败。 |
| `Practical 7 - Wind turbines.md` §1 与 §8 | §1 "Modern turbines are typically between **25 – 80 metres** high"；§8 "Since our turbines are **25 metres** tall, enter 25" | **非错误，但是一个重要的简化假定。** | 25 m 是现代风机高度区间的**下限**。若按更常见的 80 m 或轮毂高度更高的机型设定 Observer offset，**可视域会显著扩大**，得出的「哪些村镇看得见」的结论也会改变。写报告时应说明这个假定并做敏感性分析。 |
| `Practical 7 - Wind turbines.md` §3、§4.1 等 | Select by Attributes 的两处**表达式只有截图，正文没有文字** | **信息缺失（非错误）**：md 转写丢失了图片内容，读者无法从笔记还原表达式。 | 见本笔记 §5.3 与 §5.5 的 📎 推断（`CTYUA21NM = 'Cornwall'`；`class = 'A Road' Or class = 'B Road'`）。**这两处是全篇最需要对照原 PDF 截图确认的地方。** |
| `Practical 7 - Wind turbines.md` 目录页 | "Introducton"、"Criteria for site selecton"、"Adding Bufers"、"visualisaton"、"Locaton of existng wind turbines"、"Locatng"、"Relatonship"、"Scientfc" 等 | **PDF 文字提取时丢失了 "ti"/"fi" 连字（ligature）**，属系统性提取缺陷，不是原文错误。 | 阅读时自行补回：Introduction、selection、Buffers、visualisation、Location、existing、Locating、Relationship、Scientific。 |
| `Lecture 7 - Terrain Analysis.md`，Surface curvature 页图注 | "**Profile curvature = maximum slope of this surface**" | **定义不严谨**。同一页上方的黑体正文写的才是正确定义：「Profile curvature is the **rate of change of slope** in the direction of the maximum slope」。图注把「坡度的变化率」说成了「最大坡度」本身。 | Profile curvature 是**沿最大坡降方向的坡度变化率（二阶导）**，与坡度（一阶导）是两个不同的量。老师在转写中也复述了这句不严谨的话（"You can think of profile curvature as simply being the maximum slope of a surface"）——**以黑体正文的定义为准。** |
| `EART29102 - 16-Mar-transcript.md`，讲 sink 一段 | "**sinks are pits or sometimes they're spikes**, which are surrounded by higher elevation values" | **概念不准确**。讲义定义写的是 "Areas which are **pits**, surrounded by higher elevation values"，**只有 pit**。**Spike（异常高值尖峰）不是 sink**，且 **`Fill` 工具不处理 spike**。 | Sink = 被更高值包围的**低值**格网。Spike 是另一类 DEM 误差（被更低值包围的**高值**格网），会造成假的分水岭，需要用平滑滤波或人工编辑处理，`Fill` 对它无效。老师后面读图时说的 "this one here is an artificially high value ... on the right hand side we have a sink" 也把两者并列了。 |
| `EART29102 - 16-Mar-transcript.md`，课末介绍延伸资源 | "there's also a story map about terrain analysis for a particular catchment area **in Switzerland**" | **地理位置说错。** 讲义写的是 **Rauriser Ache Catchment**。 | **Rauriser Ache 是奥地利（Austria）Salzburg 州 Rauris 谷的一条河**，属 Hohe Tauern 地区，不在瑞士。以讲义的名称为准。 |
| `EART29102 - 16-Mar-transcript.md`，太阳辐射结果一段 | "very often displayed in **watts per hour per square meter**" | **单位表述错误。** 「瓦特每小时每平方米」不是一个有意义的辐射量单位（瓦特本身已经是「每秒的能量」）。 | 正确说法有两种：**辐照度（irradiance）= W/m²**（瞬时功率密度）；**累积太阳辐射量（insolation）= Wh/m²（watt-hours per square metre）**。ArcGIS 的 `Area Solar Radiation` 工具输出单位就是 **WH/m²**。老师想说的应是后者。 |
| `EART29102 - 16-Mar-transcript.md`，D8 手算一段 | "for water that may go from this cell 67 to this **153** and this **167** to this **144**" | **自动语音识别（ASR）数字误识。** 与上下文（"67 minus 53"、"67 minus 44"）矛盾。 | 应为 **53**、**67**、**44**。这不是老师讲错，是转写工具的问题。 |
| `EART29102 - 16-Mar-transcript.md`，全篇 | "brake lines"、"rasta"、"a DM"、"in saw"、"the **okra Bamba** River Basin"、"**TW1**"、"viewshed **to**"、"give morphological mapping"、"crigging"、"sumap"、"erosion ability" | **ASR 对专有名词的系统性误识**，非授课内容错误。 | 依次应为：**breaklines、raster、a DEM、InSAR、Utcubamba River Basin、TWI、Viewshed 2、geomorphological mapping、kriging、sunmap、erodibility**。 |
| `Lecture 7 - Terrain Analysis.md`，Page 9（低质量 OCR 段） | "Percentslope: **6**= 100 (h/d) (%)" / "Degree slope: **@**=arctan(h/d) (degree)" / "Rise **(/)**" / "Run **(¢)**" | **OCR 字符误识**：希腊字母 **θ** 被识别为 `6` 和 `@`；`(h)`、`(d)` 被识别为 `(/)`、`(¢)`；"Percent slope" 被连成一个词。 | **公式本身正确**，还原后为：percent slope **θ = 100 × (h/d) %**；degree slope **θ = arctan(h/d)**。h = rise（高差），d = run（水平距离）。 |
| `Lecture 7 - Terrain Analysis.md`，Page 11（低质量 OCR 段） | "SZ"、"[sem"、"GER Soctrrwees (2025-2475"、"BEE Wren rar sone 5)"、"= treat (292 5.337 5"、"BEE erm (297 5-280)" | **OCR 完全失败**。这是 Aspect map 的罗盘图例，原件为图形，识别出的全部是乱码。 | **该页文字内容不可用，请务必对照原 PDF。** 可确认的只有方位缩写 "NW"、"W270°"、"SW" 与标题 "Aspect map"。若要回答坡向分级问题，请以标准的 8 方位分级（N 337.5–22.5°、NE 22.5–67.5° …）为准（📎 补充）。 |
| `Lecture 7 - Terrain Analysis.md`，Page 12（低质量 OCR 段） | 高程分级 "2700-3000 / 2400-2700 / 2100-2400 / 1800-2100 / **1400 - 1800** / **BS 100 «200** / 800-1100 / 500-800 / 200-500"；另有 "PaO"、"TR"、"Orstance"、"1000 7400 1800" | **数字与文字误识**。其余各档间距均为 **300 m**，唯独 "1400–1800" 是 400 m，且 1100–1400 一档被识别成 "BS 100 «200"。"Orstance" 应为 **Distance**（横轴标签）。 | 分级序列应为 200–500、500–800、800–1100、**1100–1400**、**1400–1700**、1700–2000…或原图另有安排；**具体数值须对照原件**。可信的信息只有：这是一张彩色分级高程图 + 一条 A–B 剖面，**Vertical exaggeration 3.0 ×**。 |
| `Lecture 7 - Terrain Analysis.md`，"Flow direction" 页 | 标题为 "**Flow direction**"，但页内两条斜体图注写的是 "_DEM – starting raster_" 与 "_**flow accumulation** – derived raster_" | **标题与图注所指内容不一致**（该页图注描述的是 flow accumulation，下一页才是 "Flow accumulation map"）。 | 疑为幻灯片图注沿用了后一页的文字，或该页同时展示了 DEM → flow accumulation 的整体流程。**不影响概念，但阅读时不要以为 flow direction 的输出叫 "flow accumulation"。** 正确的链条是：DEM →（Fill）→ **Flow Direction** → **Flow Accumulation**。 |
| `Lecture 7 - Terrain Analysis.md`，"Interferometric synthetic aperture radar (InSAR)" 一行前后 | 项目符号排版混乱（"- • Airborne laser scanning (LiDAR)."、多处 "➢" 与 "-" 混用、部分条目被合并到同一行如 "➢ Slope, aspect, curvature and topographic profiles. ➢ Catchment and hydrology."） | **PDF 转 Markdown 时的排版丢失**，非内容错误。 | 阅读时按 "➢" 拆分条目即可。 |
| 课程大纲 `(EART29102) Geospatial Techniques.md` | Syllabus 列的是 Geodesy / Photogrammetry / GNSS / Lidar / Sonar / Volcanic Plume Modelling / UAV，Week 7 写的是 "Geographic Information Systems - Part 2" | **官方大纲与实际授课内容严重不符**（全课范围的问题，非本周独有）。 | 实际 Week 7 讲的是 **Terrain Analysis**，practical 是 **Wind turbines siting（ArcGIS Pro）**。**大纲只能作课程总体背景，绝不可用来推断任何一周的内容。** |
