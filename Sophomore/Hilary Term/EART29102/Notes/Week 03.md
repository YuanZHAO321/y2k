# EART29102 Geospatial Techniques — Week 03 学习笔记

---

## 一、本周主题

本周主题为**空间数据输入与操作（Spatial Data Input and Manipulation）**，对应 Lecture 3 与 Practical 3。

### 1. 在全课骨架中的位置

本课的整体结构是「基础 → 分析 → 专题 → 回顾」四段：

| 阶段 | 周次 | 主题 |
|---|---|---|
| **基础** | W01 | Introduction to GIS（GIS 导论） |
| **基础** | W02 | Spatial Data and Data Management（空间数据与数据管理） |
| **基础** | **W03** | **Spatial Data Input and Manipulation（空间数据输入与操作）← 本周** |
| 分析 | W04 | Spatial Analysis（空间分析） |
| 分析 | W05 | Spatial Statistics（空间统计） |
| 专题 | W06 | Remote Sensing（遥感） |
| 专题 | W07 | Terrain Analysis（地形分析） |
| 专题 | W08 | Spatial Visualisation（空间可视化） |
| 专题 | W09 | 3D Geospatial Techniques（三维地理空间技术） |
| 回顾 | W10 | Course Review（课程回顾） |

**本周是「基础段」的收尾**。三周的逻辑链条很清楚：

- **W01** 回答「GIS 是什么、能做什么」；
- **W02** 回答「空间数据长什么样、怎么组织和管理」——矢量/栅格数据模型、坐标系与投影、地理数据库；
- **W03（本周）** 回答「**数据从哪里来、进到 GIS 里之后怎么把它弄对**」——即数据采集（capture）、传输（transfer）、变换与编辑（transformation & editing），以及随之而来的**误差与数据质量**问题。

换句话说：W02 讲的是「数据的静态结构」，W03 讲的是「数据的生产流程与可信度」。**只有先把数据弄进来、弄准了，W04 起的空间分析才有意义**——这就是本周作为基础段收尾的意义：它是「原料车间」，下一周开始进入「加工车间」。

### 2. 本周讲义列出的六条内容目标

Lecture 3 开篇给出的 content 清单（原文照录）：

1. Different spatial data capture techniques.（不同的空间数据采集技术）
2. The fundamentals of a GNSS.（GNSS 的基本原理）
3. Spatial data formats and transfer.（空间数据格式与传输）
4. Basics of spatial data editing.（空间数据编辑基础）
5. Assessing spatial data quality.（评估空间数据质量）
6. Some of the main errors in spatial data.（空间数据中的主要误差类型）

### 3. 本周 Practical 的学习目标

Practical 3 开篇的 learning objectives（原文照录）：

- Apply a coordinate system to a raster image（对栅格影像应用坐标系，如航片或扫描地图）
- Georeference an image using control points（用控制点把栅格影像与参考底图/basemap 上的真实空间位置对上）
- Digitise features on a raster image to make feature classes of point, polyline and polygon vector data（在栅格影像上数字化，生成点/线/面三类矢量 feature class）
- Add new fields and data to an Attribute Table of a Feature Class（向属性表新增字段并填数据）

**讲义与 practical 的对应关系**：讲义讲「有哪些采集方式、会出什么错」，practical 则把其中的 **on-screen digitising（屏幕数字化）** 和 **georeferencing（地理配准）** 这两条完整走一遍。所以本周 practical 是讲义的**一个子集的深挖**，不是全覆盖。

> ⚠️ **关于课程大纲**：本课官方大纲（Course unit overview / Syllabus）列的是大地测量、GNSS、摄影测量、卫星遥感、数据库与大数据、Lidar、声呐、无人机；而**实际授课内容是一门以 ArcGIS Pro 为主线的 GIS 实操课**。大纲与实际周次安排严重不符，**只能当作课程总体背景（例如它确实提到了 GNSS、摄影测量、Lidar，本周讲义里也确实出现了这几项），绝不可用来推断周次内容**。
>
> 大纲中与本周确有呼应的是 **ILO 2**：「Define how spatial reference systems, datums, and projections are used in recording locations」——本周 practical 的 Define Projection 与 georeferencing 正是这条 ILO 的直接落地。

---

## 二、核心概念

### 2.1 空间数据采集（Spatial Data Capture）

**定义（讲义原文）**：Spatial data capture is the process of generating new digital spatial data. It involves direct measurement or analogue-to-digital conversion.

即「**生成新的数字空间数据**的过程」，两条途径：
- **direct measurement**（直接测量，如野外测量、GNSS 打点）；
- **analogue-to-digital conversion**（模拟-数字转换，如把纸质地图扫描后数字化）。

**要点**：capture 是「无中生有」——生产出原来不存在的数字数据；这与后面的 **spatial data transfer**（把已有的数字数据搬进 GIS）是两件不同的事，考试与理解时不要混。

---

### 2.2 矢量数据采集（Vector Data Capture）的五种方式

讲义列出五种：

1. **keyboard entry**（键盘录入）
2. **digitising**（数字化）
3. **field surveying**（野外测量）
4. **photogrammetry**（摄影测量）
5. **LiDAR (light detection and ranging)**（激光雷达）

#### (1) Keyboard entry（键盘录入）

- 从地图、野外记录或其他源文件里读出点要素的坐标，**手工敲进 GIS**。
- 点要素在这种语境下也叫 **XY events**（XY 事件）。
- **适用条件**：点的数量很少时才用（Used when the number of point features is small）。

> 📎 **背景补充**：ArcGIS Pro 中把一张含 X、Y 两列的表转成点图层的工具叫 **XY Table To Point**（Data Management Tools → Features），这正是 keyboard entry 的现代化版本——先把坐标录进 Excel/CSV，再一次性转成点图层。**本周 practical 并未使用这个工具**，讲义也只提到 "XY events" 这个术语本身，没有给出工具名。

#### (2) Manual digitising（手工数字化）

- **定义**：沿着地图或影像上地理要素的边界**手工描摹**，同时记录所选点的坐标，用这些点去逼近每个要素的边界或形状。
- **硬件**：**digitizing table**（数字化板）+ **puck**（游标/鼠标器）。这是「把纸图钉在数字化板上，用带十字丝的 puck 沿边界点点点」的传统做法。

#### (3) On-screen digitising（屏幕数字化）

- **定义**：把纸质地图**扫描**成数字影像，然后**在计算机屏幕上描摹**要素。也常被称为 heads-up digitising。
- **局限**：受**扫描影像分辨率**限制（limited by the resolution of the scanned images），可能不如手工数字化那样精确地捕捉细节。
- 讲义配图旁的一句关键注解（斜体强调）：***Digitising involves accuracy not density of points***
  ——**数字化追求的是「准确」，不是「点多」**。盲目加密顶点不会提高精度，只会让数据臃肿；顶点应该加在**形状转折处**。

> 📌 这句话与 practical 里「To create smoother curves, add more vertices（要让曲线更平滑就多加顶点）」看似矛盾，实则不矛盾：practical 说的是「曲率大的地方需要更多顶点才能贴合形状」，讲义说的是「不要为了多而多」。两者共同的落点是：**顶点该密的地方密，该疏的地方疏**。

#### (4) Automatic digitising（自动数字化）

- **定义**：通过 **raster-to-vector conversion**（栅格转矢量）把栅格影像自动转成矢量数据。
- **优点**：处理大数据集时**效率极高**（highly efficient for handling large datasets）。
- **定位**：是更大范围的 **automated digital mapping**（自动化数字制图）浪潮的一部分。

#### (5) Field surveying（野外测量）

- 通过**野外直接测量**采集空间数据。
- 传统上用常规测量方法；**近年来则用 total stations（全站仪）和 GNSS**。
- **Total station（全站仪）**：讲义给了 Leica 与 Cleveland Brothers 两个厂商链接作为示意，未展开原理。

---

### 2.3 GNSS（Global Navigation Satellite System，全球导航卫星系统）

这是本周讲义唯一展开较深的「硬技术」板块。

**作用**：Provides accurate measurement of a position almost anywhere on the surface of the Earth——在地球表面几乎任何地方都能给出精确定位。手持 GNSS 接收机（hand-held GNSS receivers）让采集者可以**步行或驾车**在采样点采集 (x, y, z) 坐标。

**四大在轨系统**（讲义原文列出的）：

| 系统 | 归属 |
|---|---|
| **GPS** | USA（美国） |
| **GLONASS** | Russia（俄罗斯） |
| **Galileo** | Europe（欧洲） |
| **BeiDou / 北斗** | China（中国） |

> ⚠️ 讲义原文写的是 "…are **three** main GNSS systems that are currently operational"，但实际列了**四个**。见文末勘误表。

#### GNSS 的主要特征（Main features of a GNSS）

讲义给出四条：

1. **轨道**：GPS 卫星在地球上空 **20,200 km** 处运行，轨道周期 **12 小时**，分布在 **6 个轨道面**（six orbital planes）。
2. **可见性**：这种配置保证了地球上任何地方**任何时候至少有 4 颗卫星潜在可见**——而 **4 颗是精确定位所需的最少卫星数**。
   > 📎 **背景补充**：为什么是 4 而不是 3？三维定位（x, y, z）在数学上只需 3 个距离观测量，但接收机的**钟差（clock bias）**是第四个未知数——民用接收机装不起原子钟，其时间偏差必须一并解算。因此未知数为 4 个，需要 4 颗卫星。讲义只给了「4 颗」这个结论，**没有解释原因**。
3. **信号**：每颗卫星以**无线电波**形式发射 **2–3 个频段（frequency bands）**的信号。无线电波是**长波长电磁辐射**，因此**能穿透大气**。**至少有一个频段保留给军方使用**。
4. **信号强度**：功率很低，**到达地面的信号强度与背景噪声电平相差不大**（arriving signals are not much different from background noise level）——这是 GNSS 在遮挡环境下容易失锁的根本原因。

#### Smartphone GNSS（智能手机 GNSS）

讲义用 Android 的 **GPStest** app 截图讲解了几个界面参数，**这几个缩写要能读懂**：

| 参数 | 全称 / 含义 |
|---|---|
| **Alt** | Altitude above **WGS84 ellipsoid**（相对 WGS84 椭球体的高程） |
| **Alt (MSL)** | 基于**大地水准面（geoid）**的高程，采用 Earth Gravitational Model（如 **EGM96**，该模型定义了海平面） |
| **TTFF** | **Time To First Fix**（首次定位所需时间） |
| **E H/V Acc** | **Estimated Horizontal / Vertical Accuracy**（估计水平/垂直精度） |
| **L1 / L5** | 无线电频段；**L5 为民用高精度频段** |
| **C/N0** | 信号功率与噪声功率密度之比（ratio of signal power to noise power density），衡量接收信号质量的重要参数 |

**C/N0 的判读标准（讲义给出）**：**35–45 dB-Hz** 属于常见的良好条件（good conditions）。具体数值受**卫星高度角（satellite elevation）、遮挡（obstructions）、天线（antenna）、频段（band）**影响。

讲义配图为 **sky map**（天空图）：显示可见 GNSS 星座，**加粗轮廓的为已连接（connected）的卫星**。

> 📌 **理解要点**：`Alt` 与 `Alt (MSL)` 的差别就是 **ellipsoid height（椭球高）与 orthometric height（正高）**之差，即**大地水准面起伏（geoid undulation）**。这一区别在 W02 的 datum（基准面）内容里已经铺垫过，本周在手机界面上具体看到了它。

---

### 2.4 Photogrammetry（摄影测量）与 LiDAR（激光扫描）

#### Photogrammetry

- **定义**：用**从不同视角拍摄的、有重叠的航空像片对（overlapping pairs of aerial photographs，即 stereo-pair 立体像对）**测量物体的 (x, y, z) 坐标。
- 讲义引用的示意图讲的是无人机的 **overlap flight pattern**（重叠航线模式）。

#### LiDAR（Laser scanning）

- **定义**：LiDAR 为大量离散点产生 (x, y, z) 坐标，这些点称为 **mass points** 或 **point clouds**（点云）。
- **精度（讲义给出的数字，两种方法共用）**：
  - **垂直精度 10–15 cm**
  - **水平精度 50–100 cm**

  > ⚠️ 注意这个数字有点反直觉：**垂直精度反而比水平精度高**。讲义把 photogrammetry 和 LiDAR 并列给出同一组数字，未区分二者、也未说明测量条件（飞行高度、点密度等）。**背这个数字时要连同「讲义未说明条件」一起记**，不要当作普适常数。

---

### 2.5 栅格数据采集（Raster Data Capture）

- 主要来源：**remotely sensed images**（遥感影像），包括**卫星影像（satellite images）**与**航空像片（aerial photographs）**。
- 讲义写「Four main types」：**visible（可见光）、infrared（红外）、multispectral（多光谱）、hyperspectral（高光谱）**。
- 讲义图注：
  - *Visible* → greyscale or colour bands（灰度或彩色波段）
  - *Visible and infrared* → colour bands or continuous（彩色波段或连续）

> 📌 这块是 **W06 Remote Sensing** 的预告，本周只是点到为止。

---

### 2.6 Crowdsourcing（众包）

- **定义**：通过向**社区或公众征集贡献**来采集空间数据。
- **手段**：使用**联网的、具备位置感知能力的移动设备（Internet-enabled and location-aware mobile devices）**收集特定位置的信息。
- **缺点（讲义明确列出三条）**：
  1. **possibly skewed data**（数据可能有偏——采集覆盖取决于谁在参与、在哪参与）
  2. **lack of ownership or confidentiality**（所有权与保密性缺失）
  3. **loss of expertise**（专业性丧失——贡献者未必受过训练）

> 📎 **背景补充**：最典型的众包地理数据是 **OpenStreetMap (OSM)**。讲义未点名任何具体平台。

---

### 2.7 空间数据传输（Spatial Data Transfer）与数据格式

**定义**：The process of **converting or translating existing digital spatial data** and importing them into a GIS.

与 capture 的区别再强调一次：**transfer 处理的是「已经存在的数字数据」**。要点：

- 从外部来源导入已有空间数据；
- 数据可能是**不同的格式**；
- 要么被 GIS **直接读取（read directly）**，要么被**翻译成合适的格式（translated into a suitable format）**。

#### FME（Feature Manipulation Engine）

- **ArcGIS Pro 内置了 FME 技术**用于空间数据传输。
- 支持 **超过 300 种**空间与非空间数据格式，例如各种 GIS 格式、栅格、数据库、3D、XML 以及点云（LiDAR）数据。

#### 数字空间数据格式一览（讲义表格，来自 OCR 页面）

> ⚠️ 下表由讲义 PDF 的图片 OCR 得到，个别名称有识别错误，已在勘误表中列出，此处**保留原样并加注**。

**矢量格式（Vector）**

| 格式 | 说明 |
|---|---|
| ESRI ArcInfo Coverage | ESRI 早期的拓扑矢量格式 |
| ESRI ArcInfo E00 | ArcInfo Interchange Format（交换格式） |
| **ESRI ArcView Shapefile** | 最常见的矢量交换格式 |
| MapInfo MIF | Map Interchange Format |
| USGS DLG | Digital Line Graphs |
| AutoCAD DXF | Data Exchange Format |
| AutoCAD DWG | Drawing |
| CGM | Computer Graphics Metafile (ISO) |
| Microstation DGN | Microstation drawing file format |
| SDTS | Spatial Data Transfer Standard（美国） |
| **NTF** | National Transfer Format（**英国**） |
| TIGER | Topologically Integrated Geographic Encoding and Referencing System（美国人口普查局） |
| DIME | Dual Independent Map Encoding（美国人口普查局） |
| VPF | Vector Product Format（美国 National Imagery and Mapping Agency） |
| ~~EML~~ **KML** | Keyhole Markup Language（Google）—— OCR 误识，应为 KML |
| WFS | Web Feature Service（Open Geospatial Consortium） |

**栅格格式（Raster）**

| 格式 | 说明 |
|---|---|
| ESRI GRID | ESRI 栅格格式 |
| DTED | Digital Terrain Elevation Data |
| ERDAS IMG | IMAGINE |
| BMP | Windows Bitmap |
| TIFF | Tagged Image File Format |
| **GeoTIFF** | 带地理参考信息的 TIFF（本周 practical 导出用的就是它） |
| GIF | Graphics Interchange Format |
| JPEG | Joint Photographic Experts Group |
| PNG | Portable Network Graphics |
| USGS DEM | 美国地质调查局数字高程模型 |
| ECW | Enhanced Compress(ed) Wavelet |
| NetCDF | Network Common Data Form（Unidata） |
| ~~8-457~~ **S-57** | International Hydrographic Organization（国际海道测量组织）电子海图格式—— OCR 误识 |

> 📌 **记忆抓手**：这张表不必逐条背，但要能答出「矢量交换用什么（Shapefile / DXF / KML / WFS）、栅格带坐标用什么（**GeoTIFF**）、英国的国家交换格式是什么（**NTF**）、科学多维栅格用什么（**NetCDF**）」。

---

### 2.8 空间数据变换与编辑（Spatial Data Transformation and Editing）

讲义列出四类：

1. **Data structure conversion**（数据结构转换，即 raster–vector conversion 矢栅互转）
2. **Geometric transformation — rubber sheeting**（几何变换——橡皮拉伸）
3. **Line simplification**（线简化）
4. **Edge matching**（边缘匹配）

#### (1) Data structure conversion（矢栅转换）

讲义给出两句关键判断：

- **Rasterisation（矢量 → 栅格）：and loss of information ——会丢失信息**。矢量的连续边界被离散成像元，边界被「阶梯化」，小于像元的要素直接消失。
- **Vectorisation（栅格 → 矢量）：and distortion ——会产生失真**。由像元边界追出来的矢量线会呈锯齿状，与原始地物的真实形状不符。

> 📌 **结论**：矢栅转换**不是无损、不可逆**的。转过去再转回来不会得到原数据。这是 GIS 中最容易被忽略的误差来源之一。

#### (2) Spatial transformations（空间变换）

讲义给出三种，**必须能区分**：

| 变换 | 讲义定义 | 保持不变的性质 | 最少控制点 |
|---|---|---|---|
| **Rubber sheeting**（橡皮拉伸） | correcting geometric distortions（校正几何畸变） | ——（局部非刚性变形） | 讲义未说明 |
| **Similarity transformation**（相似变换） | translate, rotate or scale（平移、旋转、缩放） | **preserves shape（保持形状），角度不变** | 讲义未说明 |
| **Affine transformation**（仿射变换） | scales, skews, rotates and translates（缩放、斜切、旋转、平移） | **preserve parallelism（保持平行性）**；长度和角度**可能改变** | **最少 3 个控制点** |

- **Edge matching**（边缘匹配）：**match features across data layers**——把跨图幅/跨图层的要素在接边处对齐（比如相邻两张图幅上的同一条道路要在边界处接上）。

> 📎 **背景补充（重要，因为 practical 会用到）**：ArcGIS Pro 的 Georeference 工具条里，**"1st Order Polynomial" 就是 Affine transformation（仿射变换）**，practical 原文明确写了 "the default 1st Order Polynomial (Affine) transformation method"。所需最少控制点数：
> - **1st Order Polynomial (Affine)：最少 3 个控制点**（讲义给出）
> - **2nd Order Polynomial：最少 6 个控制点**（📎 讲义与 practical 均未给出此数字，为补充）
> - **3rd Order Polynomial：最少 10 个控制点**（📎 补充）
>
> 这解释了 practical 的 Challenge 1 为什么要求「加到 **8** 个控制点」才切换 2nd Order——**少于 6 个点根本无法解算二阶多项式**。

#### (3) Line simplification（线简化，又称 weeding）

**定义（讲义原文）**：Removes insignificant bends and redundant points or vertices from a line or a polygon **while preserving its essential shape**.

即：**删除不重要的弯曲和冗余顶点，同时保留线/面的本质形状**。

> 📎 **背景补充**：经典算法是 **Douglas–Peucker 算法**，ArcGIS Pro 对应工具为 **Simplify Line / Simplify Polygon**（Cartography Tools → Generalization）。**讲义与 practical 均未提及算法名或工具名**。

---

### 2.9 Define Projection 与 Project 的区别（本周头号概念难点）

> ⚠️ 说明：**本周 practical 只用到 Define Projection**，讲义与 practical **都没有出现 Project 工具**。以下对比中，关于 **Project** 工具的部分为 📎 **背景补充**，但因为这是「投影」相关最经典的混淆点，且直接决定 practical 第 1.2 步做得对不对，必须讲清楚。

**Define Projection（定义投影）—— practical 实际用到的工具**

- **它做什么**：**只写元数据标签**，告诉 ArcGIS「这份数据里的坐标数值，是用哪个坐标系表达的」。
- **它不做什么**：**不改变数据里任何一个坐标数值**，不移动、不缩放、不重投影。
- **什么时候用**：数据的坐标系**未知（Unknown）或标错了**。本周 practical 的扫描地质图 `sk5505_sk5507.jpg` 就是这种情况——它是从门户网站下载的**未经地理配准（not georeferenced）**的 JPEG，ArcGIS 完全不知道它属于哪个坐标系，所以必须先用 Define Projection 贴上 **GDA 1994 MGA Zone 55** 这个标签。

> 📎 **背景补充：Project（投影变换）**
>
> - **它做什么**：**真正做坐标数值的换算**，把要素从一个坐标系变换到另一个坐标系（例如 GDA94 MGA Zone 55 → WGS 1984 Web Mercator）。输出是一份**新的数据集**。
> - **什么时候用**：数据的坐标系**已经正确定义**，但你需要它换到另一个坐标系里。
> - 栅格数据的对应工具是 **Project Raster**。
>
> **一句话记法**：**Define Projection 是「贴标签」，Project 是「搬家」。**
>
> **用错的后果**：
> - 该用 Project 却用了 Define Projection → 坐标数值没变但标签变了 → 图层**跑到地球另一端**或与其他图层严重错位；
> - 该用 Define Projection 却用了 Project → 因为原坐标系是错的，变换的起点就是错的 → 结果同样错位，而且更难查（因为坐标值真的被改过了）。

> 📎 **背景补充：Datum transformation（基准面变换）**
> 当源坐标系与目标坐标系基于**不同的 datum（基准面）**时（例如 GDA94 ↔ WGS84，或 OSGB36 ↔ WGS84），Project 工具会要求或建议选择一个 **Geographic Transformation**（地理变换）。不选或选错会带来**米级到上百米级**的系统性位移。**本周材料未涉及此内容**，但它是「为什么两个都标了坐标系的图层仍然对不齐」的常见原因，W04 之后做多源数据叠加时会遇到。

---

### 2.10 空间数据误差（Spatial Data Errors）

讲义列出 GIS 数据误差的**五个常见来源**：

1. **Data formatting errors（数据格式误差）** —— 具体包括 **scale（比例尺）、coordinate projection（坐标投影）、raster conversion（栅格转换）**等
2. **Cartographical generalisation errors（制图综合误差）**
3. **Location errors（位置误差）**
4. **Topological errors（拓扑误差）**
5. **Attribute errors（属性误差）**

#### Topological errors（拓扑误差）

**定义（讲义原文）**：Topology errors arise when spatial features **don't connect, intersect or align correctly**, according to the **spatial rules** in a GIS.

即：当空间要素**没有按照 GIS 中设定的空间规则正确连接、相交或对齐**时，就产生拓扑误差。

**关键判断（讲义原文）**：**Most are common when manually digitising a scanned map (except knots)** —— 大多数拓扑误差**在手工数字化扫描地图时最常出现**（结（knots）除外）。

> ⚠️ 讲义只给了这一句和一张示意图，**没有在文字层中逐条列出拓扑错误的名称**。以下类型名称为 📎 **背景补充**，用于理解图示：
>
> | 拓扑错误 | 表现 |
> |---|---|
> | **Undershoot（悬挂/未及）** | 线没有画到该相交的地方就停了，留下**缝隙（gap）** |
> | **Overshoot（过头）** | 线画过了头，多出一段**悬挂线（dangle）** |
> | **Sliver polygon（狭长缝隙多边形）** | 两个本应共享边界的面之间出现细长的空隙 |
> | **Overlap（重叠）** | 两个本应相邻的面互相压叠 |
> | **Gap（空隙）** | 本应无缝拼接的面之间有空白 |
> | **Knot / loop（结）** | 线自身打结或自相交 |
>
> 讲义括号里的 "(except knots)" 意思正是：**knots 不是数字化操作失误造成的**（更多来自自动矢量化或数据本身的几何异常），其余几类则**基本都是数字化时手抖 / 没开捕捉造成的**。

> 📎 **背景补充：Snapping（捕捉）**。ArcGIS Pro 的 **Edit → Snapping** 开关，可设置捕捉到 **Point / Endpoint / Vertex / Edge / Intersection** 等目标，并可设定**捕捉容差（snapping tolerance，以屏幕像素计）**。开启捕捉能从源头消除 undershoot / overshoot / gap / overlap。**本周 practical 全程未提及 snapping**，但它是数字化的标准操作。

> 📎 **背景补充：拓扑检查**。ArcGIS Pro 在 geodatabase 中支持创建 **Topology**（右键 Feature Dataset → New → Topology），添加 **topology rules**（如 "Must Not Overlap"、"Must Not Have Gaps"、"Must Not Have Dangles"），再用 **Validate Topology** 与 **Error Inspector** 查找并修复错误。**本周材料未涉及**，讲义只在概念层面提到拓扑误差。

#### Attribute errors（属性误差）

- 属性数据可能包含**观测或测量误差（observational or measurement errors）、数据录入误差（data entry errors）**，或者干脆**过时（out of date）**。
- **Editing 包括**：对要素及其属性值执行 **adding, deleting, or updating**（增、删、改）。

---

### 2.11 空间数据质量（Spatial Data Quality）

**核心陈述**：
- 空间数据可能含有**固有误差（inherent errors）**；
- 其质量**必须与预期用途相匹配（compatible with their intended applications）**。

**定义（讲义原文）**：*Spatial data quality* — the level of **accuracy, precision, completeness, consistency and timeliness** of the data that makes them **appropriate for a particular use**.

即空间数据质量是**准确性、精密性、完整性、一致性、时效性**五个维度的水平，使数据**适合某一特定用途**。

> 📌 **注意这个定义的落点**：质量不是绝对的，而是**相对于用途**的。同一份数据对某个应用是「高质量」，对另一个应用可能完全不够用。

讲义后面又单独强调了其中三个：

| 维度 | 讲义定义 |
|---|---|
| **Precision（精密度）** | The **recorded level of detail**（记录的细节层次） |
| **Consistency（一致性）** | The **lack of apparent contradictions** between datasets or within a dataset（数据集之间或数据集内部**不存在明显矛盾**） |
| **Completeness（完整性）** | The extent and range of a dataset with regard to **completeness of coverage, classification and verification**（在**覆盖范围、分类、验证**三方面的完整程度） |

#### Metadata（元数据）

- **定义**：**the data about data**（关于数据的数据）。
- **作用**：描述数据集的 **content（内容）、quality（质量）、condition（状况）**及其他特征。
- **Lineage（谱系）**：**history of both the source data and the processing steps** used to produce the spatial dataset——源数据的来历 **加上** 生成该空间数据集所用的处理步骤的历史。
- 存在 **international metadata standards**（国际元数据标准），讲义未点名具体标准。

> 📌 **为什么 lineage 重要**：本周 practical 结束后你会得到一个 `lakes` 图层。它的 lineage 是「从 1:250,000 扫描地质图 → 用 4 个控制点做 1 阶多项式配准（RMS 约若干米）→ 屏幕数字化」。**没有这段 lineage，别人无法判断这份数据能不能用在他的场景里**——这正好把 2.11 的「质量相对于用途」和 practical 串了起来。

---

### 2.12 📎 背景补充：本周**未**涉及但常与本主题绑在一起的操作

> 以下内容 **Lecture 3 与 Practical 3 均完全没有出现**，写在这里只是为了让你知道「空间数据操作」这个大标题下还有什么、以及它们会在哪一周出现。**复习本周时不必展开，考本周内容时不要写进去**。

- **几何操作（geometry operations）**：**Clip**（按裁剪要素裁出范围内部分）、**Dissolve**（按属性值合并相邻要素、消除内部边界）、**Merge**（把多个图层/要素合成一个）、**Buffer**（按距离生成缓冲区）。这些属于 **W04 Spatial Analysis** 的 overlay/proximity 分析内容。
- **属性表连接**：**Join**（把另一张表的字段**追加到**当前属性表，要求**一对一或多对一**）与 **Relate**（只建立**关联关系**、不合并字段，支持**一对多、多对多**）；**Spatial Join**（按**空间关系**而非公共字段来连接两张表）。
- **Field Calculator（字段计算器）**：用表达式批量填充字段值。本周 practical 只用到了 **Add Field**（新增字段）+ **手工键入数值**，**没有用 Field Calculator**。
- **Geocoding（地理编码）**：把地址文本转成坐标点。本周未涉及。

---

## 三、公式与图表

本周定量内容不多，但有**两个必须掌握的定量工具**（误差矩阵、RMSE）和**一批必须能用文字复述的示意图**。

### 3.1 误差矩阵 / 交叉列表（Error matrix / Cross-tabulation）

**用途**：回答讲义提出的问题——*How many pixels have been assigned to the incorrect land use and land cover type?*（有多少像元被分到了错误的土地利用/覆盖类型？）

**表的读法**：**行 = Map data（地图/分类结果数据）**，**列 = Reference data（参考/真值数据）**。

| Map data ＼ Reference data | Grassland | Forest | Marsh | **Rows Total** |
|---|---|---|---|---|
| **Grassland** | **28** | 14 | 15 | 57 |
| **Forest** | 1 | **15** | 5 | 21 |
| **Marsh** | 1 | 1 | **20** | 22 |
| **Columns Total** | 30 | 30 | 40 | **100** |

**对角线元素（28, 15, 20）= 分类正确的像元数**；非对角线元素 = 各种混淆。

**讲义给出的计算**：

```
Grassland = (28 / 30) × 100 = 93%
Forest    = (15 / 30) × 100 = 50%
Marsh     = (20 / 40) × 100 = 50%

Overall Accuracy = (28 + 15 + 20) = 63%
```

**逐条解释**：

- 三个分类别精度都用 **该类的列总计（Columns Total，即参考数据中该类的真实总数）**做分母：
  - Grassland：参考数据中共 30 个 grassland 像元，其中 28 个被正确分为 grassland → **93%**
  - Forest：参考数据中共 30 个 forest 像元，只有 15 个被正确分类 → **50%**
  - Marsh：参考数据中共 40 个 marsh 像元，20 个正确 → **50%**
  > 📎 **背景补充**：以**列（参考数据）**为分母算出的这个指标标准名称叫 **Producer's Accuracy（生产者精度）**；若以**行（地图数据）**为分母则叫 **User's Accuracy（用户精度）**。**讲义没有使用这两个术语**，只写了类别名。

- **Overall Accuracy（总体精度）= 对角线之和 ÷ 总样本数 = (28 + 15 + 20) / 100 = 63/100 = 63%**
  > ⚠️ 讲义原文写作 "Overall Accuracy = (28 + 15 + 20) = 63%"，**省略了除以总数 100 这一步**。因为本例总数恰好是 100，数值上碰巧对得上，但**式子本身是不完整的**。见勘误表。**自己算题时务必写全分母**，否则总数不是 100 时会直接算错。

**这张表还能看出的信息**（讲义未展开，📎 属于我的补充解读）：Grassland 这一行总计 57，远大于参考数据中 grassland 的真实数量 30——说明**分类结果严重高估了草地**，把 14 个 forest 和 15 个 marsh 像元误判成了 grassland。

### 3.2 RMSE（Root Mean Square Error，均方根误差）

**用于衡量 Positional accuracy（位置精度）**。

**讲义给出的定义**：位置精度指**数据中要素的坐标描述与其真实位置的接近程度**（how closely the coordinate descriptions of features represented in the data compare with their true location），用 RMSE 度量。

**讲义给出的符号约定**：
- **x, y, z** = true location（真实位置）
- **x′, y′, z′** = encoded position（记录/编码的位置）
- **n** = number of data values（数据值个数）

> ⚠️ 讲义 PDF 的文字层中**只有符号说明，公式本体在图片里没有被提取出来**。以下写法为 📎 **背景补充**（标准 RMSE 定义，与讲义符号约定一致）：
>
> ```
> RMSE_x = sqrt( Σ (x_i − x′_i)² / n )
> RMSE_y = sqrt( Σ (y_i − y′_i)² / n )
>
> RMSE_total = sqrt( RMSE_x² + RMSE_y² )
>            = sqrt( Σ [ (x_i − x′_i)² + (y_i − y′_i)² ] / n )
> ```

**讲义明确给出的两条性质（必记）**：
1. **RMSE 与 x, y, z 的测量单位相同**（e.g. metres, deg-C 等）——所以配准时 RMS 的单位是**米**，不是无量纲数。
2. **RMSE = 0 表示精度上没有误差**。

**与 practical 的直接联系**：Georeferencing 的 Control Point 表里那一列 **Residual（残差）**就是每个控制点的误差，全部链接的平均差异即 **Residual (RMS)**。practical 给的验收标准：**RMS 越小越好，理想情况下 < 10 m**（Manchester 挑战题则要求 **< 5 m**）。

### 3.3 多项式变换阶数与控制点数

| 变换方法 | 等价名称 | 最少控制点 | 出处 |
|---|---|---|---|
| **1st Order Polynomial** | **Affine transformation** | **3** | 讲义（Affine 需 3 点）+ practical（默认方法即 1st Order Polynomial (Affine)） |
| 2nd Order Polynomial | —— | **6** | 📎 背景补充 |
| 3rd Order Polynomial | —— | **10** | 📎 背景补充 |

practical 的 Challenge 1 要求「加到 8 个控制点并改用 2nd Order Polynomial，RMS 应当下降」——8 > 6，满足解算条件。

> 📌 **重要提醒（📎 补充解读）**：更高阶多项式**不必然**给出更好的结果。阶数越高越容易发生**过拟合（overfitting）**：控制点处残差变小，但控制点之间的区域可能被扭曲得很厉害。practical 用了 "**hopefully** the RMS value should decrease"（「**但愿**」RMS 会下降）这个措辞，语气本身就是保守的。

### 3.4 关键示意图的文字描述

讲义中大量信息在图里，PDF 文字层未提取。以下按讲义标题逐一用文字描述其要表达的内容（**图示本身的含义为讲义内容；具体画面细节的补充说明已标注**）。

#### (1) "Digitising involves accuracy not density of points"

图示对比：同一条弯曲的地物边界，用**少量放在关键转折处的顶点**可以很好地逼近；而**大量密集但位置随意的顶点**反而既臃肿又不贴合。**结论：顶点位置的准确性 > 顶点数量。**

#### (2) Rasterisation and loss of information（栅格化与信息损失）

**前**：一个边界光滑的矢量多边形（例如一个湖）。
**后**：叠上规则格网后，按「像元中心是否落在多边形内」赋值，得到的栅格是**阶梯状（锯齿状）**的边界。
**损失**：① 边界的平滑细节没了；② **小于一个像元的窄条、小岛会整体消失**；③ 结果强烈依赖**像元大小（cell size）**的选择。

#### (3) Vectorisation and distortion（矢量化与失真）

**前**：栅格图层，边界是像元阶梯。
**后**：raster-to-vector 追踪出来的多边形边界**保留了像元的直角锯齿**，与真实地物的平滑边界不符，即 **distortion（失真）**。通常还需要后续的 **line simplification / smoothing** 来缓解。

#### (4) Similarity vs Affine transformation

- **Similarity transformation**：把一个正方形做平移 + 旋转 + 等比缩放 → 结果仍是**正方形**（可能更大/更小/转了个角度）。**角度不变、形状不变**。
- **Affine transformation**：把一个正方形做缩放 + 斜切（skew）+ 旋转 + 平移 → 结果变成**平行四边形**。**边仍然两两平行（preserve parallelism），但角度和边长变了**。
- **记忆**：相似变换 = 「保形」；仿射变换 = 「保平行」。

#### (5) Rubber sheeting（橡皮拉伸）

想象把地图印在一张橡皮膜上，用图钉（控制点）把若干位置钉到真实坐标上，膜在钉子之间被**局部非均匀地拉伸**。用于**校正几何畸变**——这种畸变在全图上并不一致（如纸图受潮变形、老地图的不规则误差），因此需要局部变形而非全局的一次线性变换。

#### (6) Edge matching（边缘匹配）

两个相邻图幅在接边处，同一条道路/河流/地质界线的端点**没有对上**（错开或有缝）。Edge matching 把它们在跨图层的接边处强制对齐并接上。

#### (7) Line simplification / weeding（线简化）

**前**：一条由几十个顶点构成的曲折岸线。
**后**：删掉不显著的小弯和冗余顶点，只留下决定整体形状的关键顶点；**整体轮廓看上去与原线一致**，但数据量大幅减小。

#### (8) Topological errors（拓扑错误示意）

图中并列展示若干种错误几何：线**没画到位（undershoot，留缝）**、线**画过头（overshoot，留悬挂端）**、两个面之间的**细长缝隙（sliver）**、面**互相压叠（overlap）**、线**自身打结（knot）**。讲义强调：**除 knot 外，其余都是手工数字化扫描地图时的高频错误**。

#### (9) Smartphone GNSS sky map（天空图）

极坐标形式的半球投影图：圆心为天顶，外圈为地平线；每颗卫星按**方位角（azimuth）和高度角（elevation）**画在图上；**已连接（用于定位解算）的卫星以加粗轮廓显示**。旁边的条形图显示每颗星的 **C/N0**（35–45 dB-Hz 为良好）。

#### (10) 📎 背景补充：Georeferencing Control Point 表的结构

practical 让你打开这张表，但没有画出表头。其结构为（📎 补充）：每一行是一个 **link（链接）**，列包含 **Link ID、是否勾选启用、Source X / Source Y（源影像坐标）、Map X / Map Y（目标地图坐标）、Residual（该点残差，米）**；表底部显示 **Total RMS Error（总均方根误差）**与当前的 **Transformation（变换方法）**下拉框。

#### (11) 📎 背景补充：Clip / Dissolve / Merge / Buffer 示意

> **本周材料完全未涉及这四个工具**，此处仅作占位式说明，详见 W04：
> - **Clip**：用一个「饼干模子」多边形去切另一个图层，只留下模子内部的部分，属性不变。
> - **Dissolve**：把属性值相同的相邻多边形合并成一个，**消掉它们之间的内部边界**（例如把各区县合成省）。
> - **Merge**：把两个或多个图层的要素**堆进同一个图层**，不改变几何，只是并到一起。
> - **Buffer**：围绕点/线/面按指定距离生成一圈等距的多边形（点 → 圆；线 → 长条；面 → 外扩的面）。

---

## 四、课堂补充

> **本周无 transcript（本课 transcript 自第 4 周起才有）。以下内容全部来自讲义（Lecture 3 handout）与实操教程（Practical 3）本身，不是课堂录音的整理。**

### 4.1 讲义明确布置的作业与资源

Lecture 3 最后一页 "Homework and Resources"：

1. **阅读课程教材第 3 章：Spatial Data Input and Manipulation**。
   - 教材为 **Zhu X. (2016) *GIS for Environmental Applications***，可从 Blackboard 站点获取（practical 首页注明「Some of this Practical is based on the resources in Zhu X. (2016) GIS for Environmental Applications, Chapter 3. This is the course textbook and accessible from the Blackboard site.」）。
   - 📌 **注意**：**讲义与 practical 的第 3 章是同一章**——教材第 3 章同时是本周讲义的理论来源和 practical 的操作来源。这意味着**读教材第 3 章的性价比在本周特别高**。
2. **完成 Canvas 上的 quiz** 以自测基本理解（Take the quiz to test your basic understanding）。
3. **进一步资源**：ESRI 培训 *Getting Started with Imagery and Remote Sensing*（**只做 component 1，约 45 分钟**）。
4. Practical 末尾另给一条：ESRI 培训 *Georeferencing Raster Data Using ArcGIS*，建议**做完本周练习之后**再通读一遍。

> 📌 **评估相关**：课程大纲显示本课 **无期末笔试**，评估由 **Set exercise 50%** + **Other（on-line test）50%** 组成，且反馈表提到一次 **Week 6 的开卷作业（open book assessment，占 50%，ILO 1、2）**。ILO 2 明确涉及 **spatial reference systems, datums, projections**——本周的 **Define Projection / 坐标系选择 / 控制点配准** 正落在这条 ILO 上，**属于高概率考点**。（📎 此处对「考什么」的推断为我的补充判断，材料并未直接说明本周内容会被考。）

### 4.2 讲义强调的注意事项（从措辞看出的重点）

- **"Digitising involves accuracy not density of points"** 被单独抽出来做图注并用斜体重复了一遍——这是讲义里少数被重复强调的句子，几乎肯定是要点。
- **"at least **four** satellites"** 中的 four 在原文里被**加粗**——GNSS 部分唯一加粗的词。
- **Precision / Consistency / Completeness** 三个词在 "Data quality" 页被**逐个加粗**并给了定义——说明要求能**分别复述定义**，而不只是列举名词。
- Topological errors 那句 **"Most are common when manually digitising a scanned map"** 把讲义的理论部分和 practical 的实操部分直接扣在了一起：**你在 practical 里描 Lake St Clair 时犯的错，就是讲义里说的那些拓扑错误**。

### 4.3 Practical 透露的操作规范与验收标准

这些是「教程里写死的数字/要求」，做题和自查时可直接当标准用：

| 项目 | 标准（practical 原文） |
|---|---|
| 主练习控制点数 | **4 个**（地图四角） |
| 主练习目标 RMS | **ideally the RMS should be < 10 m** |
| Challenge 1 控制点数 | **总共 8 个**，并改用 **2nd Order Polynomial** |
| Challenge 1 期望 | RMS 值应当下降（"hopefully"） |
| Manchester 挑战题控制点数 | **约 6 个** |
| Manchester 挑战题目标 RMS | **< 5 m** |
| 默认变换方法 | **1st Order Polynomial (Affine)** |
| Strike_dip 采点数量 | 在地图的一小片区域内点**约 10 个** |

其他被教程点明的操作习惯：

- **"Be patient, it takes a little practice!"** ——教程原文对按住 `c` 键平移缩放的评价。**这是唯一一处教程主动提示「会不顺手」的地方**，说明该操作确实是新手卡点。
- **"The following step is not recommended."** ——教程明确**不建议**在本练习中执行 `Save as New` → `Export Raster as a new tiff layer`，理由是**可能耗时很长**。
- **"If you make a mistake you can uncheck or remove a control point or update its values in the table."** ——控制点表是可编辑的，**出错不必重来**。

---

## 五、Practical 要点

> **本段是本周笔记的重心。目标：不打开原教程，也能在 ArcGIS Pro 里完整重做一遍。**
> 凡是教程原文写了的步骤，直接照录（工具名/菜单名保留英文）；凡是教程没写、由我补充的操作细节或排错方法，一律用 📎 标出——照做时如果发现某一步在教程里找不到对应文字，看标记即可分辨。

### 5.0 总览：这次 practical 要做的三件事

```
【任务 A】给一张没有坐标的扫描地质图配上真实世界坐标
   下载 JPEG → Define Projection 贴标签 → 加 4 个控制点做 Georeferencing → 看 RMS 验收

【任务 B】在配准好的地图上做屏幕数字化，生成矢量数据
   Create Feature Class (polygon) → Edit → Create → 描 Lake St Clair → 存

【任务 C】给数字化出来的要素加属性
   Attribute Table → Add Field → 填 dip 值 → 存

【课后】Manchester.jpg 配准到 OS Open Background 底图（British National Grid）
```

**数据**：
- 主练习：`sk5505_sk5507.jpg` —— 澳大利亚西南塔斯马尼亚 **1:250,000 扫描地质图**，来自 Geoscience Australia Portal，**下载时不带地理参考**。
- 课后练习：`Manchester.jpg` —— Oxford Rd 上曼大建筑群的影像，从 **Week 3 Blackboard 站点的 Practical 文件夹**下载。教程给的辨认线索：**圆形的 University Place 大楼在图的上方中部，与之相邻的绿顶建筑是 Williamson Building**。

---

### 5.1 任务 A：Georeferencing an image（地理配准）

#### 步骤 A-1：下载扫描地质图（教程 §1.1）

1. 打开浏览器，访问 **Geoscience Australia Portal**：`https://portal.ga.gov.au`
   （⚠️ 教程原文里写作 "htps://…"，是 PDF 提取丢字符，实际是 `https://`。）
2. 在门户里依次点：**"Layers" → "Filters" → "Keywords" → "Australian Geological Survey Organisations Network (AGSON)"**
3. 在搜索栏搜索 **"Scanned 1:250,000 Geological Map"**，目标图层应是**第一条结果**。
4. 点开该结果的下拉，点 **"Add to Map"**。
5. 在地图上**选中塔斯马尼亚西南部的那个格网方块**（塔斯马尼亚在澳大利亚南方）。这会打开 **"Inspection Tool"** 窗口。
6. 在 Inspection Tool 里把地图**下载为 jpeg**（可选 **125 dpi 或 250 dpi** 两种分辨率），存为 **`sk5505_sk5507.jpg`**，位置自选。

> 📌 **教程强调**：*All the scanned geological maps available from the portal are **not georeferenced**.*（门户上所有扫描地质图都**没有地理参考**）——这正是接下来所有步骤存在的理由。且**免费下载**。

#### 步骤 A-2：把影像加进 ArcGIS Pro

7. 启动 **ArcGIS Pro**，新建一个 **Map**（new map）。
8. 点 **Add Data** 按钮，把 `sk5505_sk5507.jpg` 加到视图里。
9. 弹出提示时点 **Yes** 执行 **Calculate statistics**（计算统计值）。

**中间检查点 ①**：影像被加进来了，但**因为没有坐标，它极可能不会出现在世界地图上应有的位置**（教程原文：*There are no coordinates for the image so it is unlikely to appear on the world map*）。
- **如果在 Map View 里根本看不到影像**：在 **Contents Pane** 里**右键该图层 → Zoom to Layer**。

> 📎 **背景补充（排错）**：无坐标系的栅格被 ArcGIS Pro 加入时，通常会被临时按影像的**像素坐标**摆放（左上角在原点附近），所以它会出现在世界地图的西非外海附近或干脆在视野外。这属于**正常现象，不是加载失败**。

#### 步骤 A-3：Apply a projected coordinate system —— **Define Projection**（教程 §1.2）

**前提认知**：这张图的**地理参考系统印在地图图面上**（The georeferencing system of the map is printed on the map image）。读图可知：

> **地图坐标系 = GDA94 MGA Zone 55**

**操作**：

10. 在 **ribbon 顶部的 search box** 里，或在 **Tools** 里，输入 **`Define Projection`**，打开该工具。
11. **Input Dataset or Feature Class** → 选择 **`sk5505_sk5507.jpg`**。
12. **Coordinate System** → 点右侧的 **globe（地球仪）按钮**，切到 **Coordinate Systems** 标签页。
13. 展开路径：**Projected Coordinate Systems → National Grids → Australia**，选中 **`GDA 1994 MGA Zone 55`**。
14. 点 **OK**，再点 **Run**。

**中间检查点 ②（教程明确要求做的验证）**：
- 在 **Contents Pane** 里选中 `sk5505_sk5507.jpg` 图层 → **右键 Properties → Source → Spatial Reference**，确认坐标系显示为 **GDA 1994 MGA Zone 55**。

> ⚠️ **这一步做的是「贴标签」，不是「变换」**。Define Projection **不会移动影像**，它只是告诉 ArcGIS「这张图的坐标数值应当按 GDA94 MGA Zone 55 来理解」。真正把图搬到正确位置的是下一步的控制点配准。详见【六、易错点】。

> 📎 **背景补充**：`GDA 1994 MGA Zone 55` 的 **EPSG 代码是 28355**；MGA（Map Grid of Australia）本质上就是**基于 GDA94 基准面的 UTM 投影**，Zone 55 覆盖东经 144°–150°，塔斯马尼亚正在此带内。**教程未给出 EPSG 代码**，若在其他软件（QGIS 等）里复现，直接搜 `EPSG:28355` 更快。

#### 步骤 A-4：读取控制点坐标（教程 §1.3 前半）

**读图规则（教程原文说明）**：
- 塔斯马尼亚南部地质图的**图廓上按固定间隔标注了 MGA 的 x、y 坐标**：
  - **x 坐标（eastings，东坐标）标在图幅的上边和下边**；
  - **y 坐标（northings，北坐标）标在图幅的左边和右边**。
- **MGA 是一个格网参照系统（grid reference system）**；图面上的 **`+` 标记代表每 10,000 m 一条的格网参照线**，可用来帮助确定某个位置的 x、y 坐标。

**四角控制点坐标（教程给定，直接用）**：

| 角点 | X（Easting，m） | Y（Northing，m） |
|---|---|---|
| **lower left（左下）** | **270,000** | **5,140,000** |
| **lower right（右下）** | **460,000** | **5,140,000** |
| **upper right（右上）** | **460,000** | **5,380,000** |
| **upper left（左上）** | **270,000** | **5,380,000** |

> 📌 **自检**：左右差 460,000 − 270,000 = **190,000 m**，上下差 5,380,000 − 5,140,000 = **240,000 m**。输入时**不要打逗号**，直接输 `270000`、`5140000`。

#### 步骤 A-5：加控制点做配准（教程 §1.3 后半）

15. 在 **Contents Pane** 里**右键** `sk5505_sk5507.jpg` → **`1:1 Zoom To Source Resolution`**。
    - 教程说明：这会给出**定位控制点的最佳显示效果**（即让影像按其原始像素分辨率 1:1 显示，看得最清）。
16. 点主菜单栏的 **`Imagery`** 标签 → 点 **`Georeferencing`** 按钮，打开 **Georeferencing 工具条（新菜单）**。
17. 在 Georeferencing 工具条上点 **`Auto Apply`**。
    - 教程说明：这会**在你输入坐标后自动把影像显示移动到其真实世界位置**。
18. 点 **`Add Control Points`** 工具。鼠标移到地图显示区时，**指针变成十字丝（crosshair）**。

> ⚠️ **关键操作技巧（教程专门提醒）**：在 Georeferencing 模式下你仍需要平移和缩放地图，方法是**按住键盘上的 `c` 键**。教程原话：*Be patient, it takes a little practice!*（要有耐心，需要练一下）。

19. **第一个控制点（左下角）**：
    - 按住 `c` 平移地图，让**图幅左下角**可见；
    - 把十字丝对准该角点，**单击** —— 这就录入了一个控制点（source 端）；
    - **在视图任意处右键 → 选择 `Input X and Y...`**；
    - 在 **`Enter Coordinates`** 对话框里输入 **X (easting) = `270000`**，**Y (northing) = `5140000`**；
    - 点 **OK**。**影像显示随即被移到真实世界坐标空间。**

> 📌 **教程的一条重要注解**：`Enter Coordinates` 里 **Target Coordinates box** 中的 **DMS 指的是 Degrees, Minutes, Seconds（度分秒）**；而**本例用的是 UTM 坐标**（MGA 即 UTM 形式），所以**不要选 DMS**，直接输入米制的东/北坐标。

20. **回到全图**：在 **Contents Pane** 里右键 `sk5505_sk5507.jpg` → **`Zoom To Layer`**，重新显示整张扫描地图。
21. **第二个控制点（右下角）**：按住 `c` 平移缩放到图幅右下角，重复第 19 步，输入 **X = 460000, Y = 5140000**。
22. **重复**上述流程，加完**其余两个角点**：
    - 右上角：X = **460000**, Y = **5380000**
    - 左上角：X = **270000**, Y = **5380000**

**中间检查点 ③**：加完 4 个点后，影像应当已经落在澳大利亚塔斯马尼亚的位置上（若加了底图，可以直接看对不对得上）。

> 📎 **背景补充（排错）**：
> - 若点完控制点后影像**飞到很远的地方**，多半是坐标输反了（把 northing 输进了 X）或漏输/多输了一位数——回到控制点表逐行核对 Map X / Map Y。
> - 若影像**完全没有动**，检查 **`Auto Apply` 是否被打开**。
> - 十字丝**点错位置**时，可在控制点表中删除该行重来（见下一步）。

#### 步骤 A-6：Fitting method and errors（拟合方法与误差，教程 §1.4）

23. 在 Georeferencing 工具条上点 **`Control Point`** 按钮，打开控制点表。
    （📎 该按钮在 ArcGIS Pro 的 Georeference 标签页中标注为 **Control Point Table**；教程写作 "Control Point button"。）

**表的内容（教程说明）**：
- 显示 **links（源影像点与地理配准点之间的链接）**及 **errors** 的表格；
- **每一行包含一条链接的 from（source，源）→ to（map，地图）坐标**，以及 **residuals（残差，误差）**；
- **residual error 以米（metres）为单位**，通过**比较地图坐标的实际位置与其在源影像中的位置**计算得到；
- **所有链接的平均差异表示为 Residual (RMS, root mean square)**。

**变换方法与验收标准**：
- 扫描地图默认使用 **1st Order Polynomial (Affine) transformation** 进行变换；
- 教程提醒：**你的表中的数值很可能与教程截图不同**（The values in your link table will likely differ from those shown in the image below）——这是正常的；
- **残差越小结果越好**，**理想情况 RMS < 10 m**。

**纠错**：教程明确说明——如果点错了，可以在表中 **uncheck（取消勾选）**、**remove（删除）**某个控制点，或**直接修改它的数值**。

**Challenge 1（教程内挑战题）**：
> **总共加到 8 个控制点，并把 fitting 改为 2nd Order Polynomial，RMS 值应当会下降。**
>
> 📎 **补充**：额外的 4 个点建议加在**四条边的中点附近**的格网 `+` 交叉处（利用 10,000 m 格网线读坐标），而不是继续挤在角落——控制点**分布均匀**才能约束住整幅图。教程未说明额外控制点应加在哪里。

24. **保存与退出**：配准完成后，在 Georeferencing 菜单上点 **`Save`**，然后点 **`Exit Georeferencing`**。

> ⚠️ **教程明确不建议执行的一步**：
> *The following step is **not recommended**. Not recommended for this exercise (it may take a long time)*
> —— 即：点 **`Save as New`** 然后 **`Export Raster as a new tiff layer`**，把影像**永久变换**到真实世界位置。**本练习不要做，可能非常耗时。**
>
> 📎 **概念区分（补充）**：点 `Save` 只是把配准信息写成**辅助文件**（world file / .aux.xml），**原 JPEG 的像素没有被重采样**；只有 `Save as New` → 导出 TIFF 才会真正**重采样生成一份新的、几何已校正的栅格**。前者轻量可逆，后者重且不可逆。这一层区别教程没有解释，但它正好呼应了讲义里 "make the changes permanent" 这个说法。

---

### 5.2 任务 B：On-screen digitising（屏幕数字化，教程 §2）

**目标**：在刚配准好的塔斯马尼亚西南地质图上，用屏幕数字化的方法**提取湖泊（lake）要素**。

#### 步骤 B-1：Create a new Feature Class（教程 §2.1）

25. 在 **`Analysis`** 标签页打开 **`Tools`**，在 **Geoprocessing pane** 中搜索 **`Create Feature Class`**。
    - 用途（教程说明）：创建一个新的 feature class，用来**存放接下来数字化产生的要素**。
26. 在 **`Create Feature Class`** 对话框里：
    - **Feature Class Location**：浏览到**存放 Tasmania 项目的文件夹**，点 **`Add`**。
    - **Feature Class Name**：填 **`lakes`**。
    - **Geometry Type**：设为 **`POLYGON`**（教程注明这是**默认值**）。
    - **Coordinate System**：点 **`Spatial Reference Properties`**，在对话框中浏览到 **Projected Coordinate Systems → National Grids → Australia**，选 **`GDA 1994 MGA Zone 55`**，点 **`Add`**。
27. 点 **`Run`**。空的 feature class **`lakes`** 被创建并加入内容列表（table of contents）。

**中间检查点 ④**：Contents Pane 里出现一个名为 `lakes` 的**空图层**。
> ⚠️ **必须核对**：新建 feature class 的坐标系**必须与配准后地图的坐标系一致（GDA 1994 MGA Zone 55）**。这一步是整个 practical 里第二次手动指定坐标系，教程把路径完整重复了一遍，说明它重要。坐标系不一致会导致数字化出来的多边形与底图错位。

#### 步骤 B-2：Adding Features（描图，教程 §2.2）

28. 缩放到地图**右上部的 Lake St Clair（圣克莱尔湖）**。
29. 点 **`Edit`** 标签 → 点 **`Create`**。弹出 **`Create Features`** 窗口，矢量图层 **`lakes`** 会列在其中。
30. 在 **Create Features** 窗口**上半部**点击图层名 **`lakes`**；**下半部**随即出现若干 **construction tools（构造工具）**。点其中的 **`Polygon`** 工具。
31. **描边**：
    - 沿 Lake St Clair 的边界选择能**最好地逼近湖泊形状**的点；
    - **每点一下加一个顶点（vertex）**，沿着湖岸描；
    - 描的过程中同样**按住 `c` 键**来平移和缩放；
    - **每个绿色圆点代表一个 vertex**；
    - 教程提示：**要得到更平滑的曲线，就多加一些顶点**（To create smoother curves, add more vertices）；
    - **收尾**：加完最后一个顶点后，**在起点处双击**（或**右键 → `Finish`**）。一个代表该湖的多边形就被创建为 `lakes` 要素的符号。
32. 点 **`Finish`** 退出，并 **`Save`** 你的 Project。

> 📎 **背景补充（操作细节，教程未写）**：
> - 在 ArcGIS Pro 中，**双击可以在任意位置结束多边形草图**，系统会自动闭合到起点；不必精确双击在起点上。
> - 描错一个顶点时按 **`Ctrl + Z`** 撤销最近的顶点即可，不必整个重画。
> - **强烈建议先打开 Snapping**（`Edit` 标签 → `Snapping`）再描下一个多边形，否则相邻要素之间容易留下 sliver / gap（正是讲义 topological errors 那一页说的问题）。**教程全程未提 snapping。**
> - 描图前把 `lakes` 图层的**符号系统（Symbology）**改成**无填充 + 醒目轮廓线**（右键图层 → Symbology → Polygon → 选 "Black Outline"），这样多边形不会遮住底图，方便对边界。**教程未涉及符号系统设置。**

**Challenge 2（教程内挑战题）**：
> 重复上述步骤，**数字化 Lake King William**。

**Challenge 3（教程内挑战题）**：
> 再创建**两个 feature class**：
> - 一个叫 **`Strike_dip`**，**几何类型为 point（点）**，在图上看到 strike–dip（产状/走向-倾角）符号的地方打点——**在地图的一小片区域内点大约 10 个**；
> - 另一个叫 **`Faults`**，**几何类型为 polyline（折线）**，描出图上一些简单的断层线。
>
> ⚠️ 教程原文写的是 "trace some of the simple **points** on the map"，但该 feature class 名为 Faults 且几何类型是 polyline，此处**应为 faults（断层）**。见勘误表。
>
> 📎 **补充**：创建这两个 feature class 的方式与第 26 步完全相同，只是把 **Geometry Type** 分别改成 **`POINT`** 和 **`POLYLINE`**，坐标系同样选 **GDA 1994 MGA Zone 55**。教程没有重复这些步骤。

#### 步骤 B-3：Viewing and adding Feature class attributes（属性表，教程 §2.3）

33. **右键 `lakes` feature class → `Attribute Table`**。**Attributes window** 会在 **Map view 下方**打开。
34. 观察字段：数字化出来的湖有 **`ObjectID`、`Shape`、`Shape_Length`、`Shape_Area`** 这几个字段——它们是**系统为 lakes 图层自动创建的字段**（教程原文说 "Three attributes"，但实际列了四个，见勘误表）。

> 📎 **补充解读**：`Shape_Length`（周长）和 `Shape_Area`（面积）是 geodatabase feature class 自动维护的**几何字段**，**单位跟随坐标系**——因为坐标系是 MGA Zone 55（单位米），所以面积单位是**平方米**。这正是「坐标系必须选对」的一个直接后果。教程未说明单位。

35. 打开 **`Strike_dip`** feature class 的 **Attribute Table**，准备**把 dip（倾角）值加进属性表**。
36. 点 **`Add Field`** 按钮，弹出一个名为 **`Fields: Strike_dip`** 的新表（字段设计视图）。在其中**新增一个 Field 并设置其属性**。
    > ⚠️ 教程此处只写了 "Add a new Field and set it up as follows:" 后面接一张**截图**，**字段名、数据类型、别名等具体设置在文字层中不可见**。
    >
    > 📎 **补充（推荐设置，非教程原文）**：**Field Name = `Dip`**，**Data Type = `Short`（短整型，倾角为 0–90 的整数）**或 **`Float`**（若需小数）。若同时要记走向，可再加一个 `Strike`。**照做时请以原截图为准。**
37. **保存新字段**：在 **`Fields`** 标签页的 **`Changes`** 组里点 **`Save`**。
38. 新的空字段出现在 `Strike_dip` 的属性表里，可以**按地图上的倾角值逐行编辑填入**。
    - 教程给的定位技巧：**选中属性表中的某一行，可以 highlight 或 flash 对应的点**，从而确定它是地图上的哪一个。
39. 关闭属性表（提示保存时**保存更改**），然后 **`Save`** 整个 Project。

> 📎 **背景补充（教程未提）**：`Add Field` 只是**建了一个空字段**；要批量赋值需要用 **Field Calculator**（右键字段名 → Calculate Field）。本练习是**逐格手工输入**，所以用不到它。另外，编辑属性表内容前通常需要处于**编辑状态**，改完在 **`Edit` 标签 → `Save`** 提交编辑。

---

### 5.3 任务 C（课后作业）：Manchester.jpg 配准（教程 §3 Challenge Exercise）

**教程明确标注：to be completed for homework（课后完成）。**

**数据**：从 **Week 3 Blackboard 站点的 Practical 文件夹**下载 **`Manchester.jpg`**。
- 内容：Oxford Rd 上的曼大建筑影像；
- 辨认线索：**圆形的 University Place 大楼在图的上方中部**，**与之相邻的绿顶建筑是 Williamson Building**。

**步骤**：

40. 新建一个 ArcGIS Pro 项目。
41. **从 ArcGIS Online 添加数据**：加入 **`OS Open Background`** 图层（英国地形署开放底图）。
42. 把 **`Manchester.jpg`** 作为新图层加进来。
43. **把影像配准到底图上。**

**教程给的三条 Hint（直接照用）**：

| Hint | 内容 |
|---|---|
| **Hint 1** | 用 **Georeference 菜单上的 `Set SRS`（Spatial Reference System）按钮**，把影像的坐标系设成与 OS Open Background 图层一致，即 **British National Grid** |
| **Hint 2** | 用 **Georeference 菜单上的 `Locate` 按钮**搜索 **"University of Manchester"**，帮助在 OS Open Background 上定位到正确区域 |
| **Hint 3** | **反复开关图层可见性**来帮助找控制点——**这次不能用地图坐标，只能用地理特征在影像与底图之间互相匹配**。**建筑物的角点是很好的控制点位置**。大约需要 **6 个控制点**才能把 **RMS 降到 < 5 m** |

> 📌 **任务 C 与任务 A 的本质区别（务必理解）**：
> - **任务 A** 是 **image-to-map（影像到坐标）**配准：控制点的目标坐标是**从图廓上读出来的已知数值**，通过 `Input X and Y` **键入**。
> - **任务 C** 是 **image-to-map（影像到参考图层）**配准：**没有可读的坐标数值**，你必须**在底图上点击同名地物**来指定目标位置（先点影像上的建筑角点，再点底图上同一个角点）。
> - 这也是 practical 学习目标里写的 "**connect raster images to their spatial locations on a reference database such as a basemap**"（把栅格影像连接到参考数据库/底图上的空间位置）那一句的实际含义。

> 📎 **背景补充**：**British National Grid 的 EPSG 代码为 27700**（基准面 OSGB36）。`Set SRS` 与 `Locate` 都位于 ArcGIS Pro 的 **Georeference 标签页 → Prepare 组**。教程未给 EPSG 代码，也未给按钮所在的组名。

---

### 5.4 完整复现清单（自查用）

```
□ 1. 下载 sk5505_sk5507.jpg（GA Portal → AGSON → Scanned 1:250,000 Geological Map → SW Tasmania grid → Inspection Tool → jpeg）
□ 2. ArcGIS Pro 新建 Map → Add Data → Yes to Calculate statistics
□ 3. 看不到图？→ 右键图层 → Zoom to Layer
□ 4. Tools/search box → Define Projection
      Input = sk5505_sk5507.jpg
      CS = Projected CS → National Grids → Australia → GDA 1994 MGA Zone 55
□ 5. 验证：图层 Properties → Source → Spatial Reference = GDA 1994 MGA Zone 55
□ 6. 右键图层 → 1:1 Zoom To Source Resolution
□ 7. Imagery 标签 → Georeferencing → 打开 Auto Apply
□ 8. Add Control Points；按住 c 平移缩放
□ 9. 点左下角 → 右键 → Input X and Y → 270000 / 5140000 → OK
□ 10. Zoom To Layer → 右下角 460000 / 5140000
□ 11. 右上角 460000 / 5380000
□ 12. 左上角 270000 / 5380000
□ 13. Control Point（表）→ 检查 Residual 与 RMS，目标 < 10 m；错点可 uncheck / remove / 改值
□ 14. [Challenge 1] 加到 8 点 + 改 2nd Order Polynomial → RMS 应下降
□ 15. Save → Exit Georeferencing（不要做 Save as New / Export Raster）
□ 16. Analysis 标签 → Tools → Create Feature Class
      Location = 项目文件夹；Name = lakes；Geometry Type = POLYGON
      CS = GDA 1994 MGA Zone 55 → Run
□ 17. 缩放到 Lake St Clair → Edit 标签 → Create → 点 lakes → 选 Polygon 工具
□ 18. 逐点描边（按住 c 平移）→ 起点处双击 或 右键 Finish → Finish → Save Project
□ 19. [Challenge 2] 同法数字化 Lake King William
□ 20. [Challenge 3] 建 Strike_dip (POINT, 约10点) 与 Faults (POLYLINE)
□ 21. 右键 lakes → Attribute Table：确认 ObjectID / Shape / Shape_Length / Shape_Area
□ 22. Strike_dip 属性表 → Add Field → 设字段（建议 Dip, Short）→ Fields 标签 → Changes 组 → Save
□ 23. 逐行填 dip 值（选中行可 highlight/flash 定位点）→ 关表保存 → Save Project
□ 24. [Homework] Manchester.jpg：新项目 → 加 OS Open Background → 加影像
       → Set SRS = British National Grid → Locate 搜 "University of Manchester"
       → 用建筑角点做约 6 个控制点 → RMS < 5 m
```

---

## 六、易错点 / 重点难点

### ★ 头号易错点：Define Projection ≠ Project

| | **Define Projection** | **Project**（📎 本周材料未出现，补充对照） |
|---|---|---|
| 中文 | 定义投影 | 投影变换 |
| 干什么 | **只写元数据标签** | **真正换算坐标数值** |
| 坐标数值 | **完全不变** | **被重新计算** |
| 输出 | **原地修改**（无新数据集） | **生成新数据集** |
| 何时用 | 数据坐标系**未知/标错** | 数据坐标系**正确**，但要换到另一个坐标系 |
| 栅格版本 | Define Projection（通用） | **Project Raster** |

**为什么它是本周头号易错点**：
1. 两个工具的名字都含 "Projection/Project"，都在 **Data Management Tools → Projections and Transformations** 下面，视觉上极易点错；
2. **用错的症状是「图层跑到地球另一头」或「与其他图层严重错位」**，而不是报错——软件不会拦你；
3. 本周 practical 的第 1.2 步之所以用 Define Projection，是因为 `sk5505_sk5507.jpg` **根本没有坐标系（Unknown）**。**给一份 Unknown 坐标系的数据跑 Project 是无意义的**——变换的起点未知，结果必然错。

**一句话**：**Define Projection = 告诉软件「这份数据本来就是这个坐标系的」；Project = 让软件「把这份数据换个坐标系」。**

📎 **补充判据**：拿到一份图层不知道该用哪个，先看 **Properties → Source → Spatial Reference**：
- 显示 **Unknown / \<undefined\>** → 用 **Define Projection**（前提是你知道它真正的坐标系）；
- 显示的坐标系**正确但不是你想要的** → 用 **Project / Project Raster**；
- 显示的坐标系**是错的** → 先 **Define Projection** 改对，**再** Project。

---

### ★ Georeferencing 相关

1. **`Auto Apply` 忘了打开** → 输了坐标影像也不动，误以为操作失败。
2. **X 与 Y 输反**（把 5,140,000 输进 X）→ 影像瞬间飞出视野。**记法：X = easting（东，左右）= 六位数 27xxxx/46xxxx；Y = northing（北，上下）= 七位数 51xxxxx/53xxxxx**。本例中 **X 是 6 位、Y 是 7 位**，位数本身就是一个防呆检查。
3. **输坐标时打了逗号**（`270,000`）→ 输入被拒或解析错误。**只输纯数字 `270000`**。
4. **选了 DMS 输入模式** → 教程专门提醒：**Target Coordinates box 里的 DMS 是度分秒**，本练习用的是 **UTM（米制）**，不要用 DMS。
5. **控制点全挤在一小块区域** → RMS 看起来很小，但区域外的配准误差很大（外推）。**控制点必须在图幅上分散布置**。
6. **盲目升阶**：2nd/3rd Order Polynomial 需要更多控制点（6 / 10），且**高阶容易过拟合**，控制点之间的区域可能被扭曲。教程用 "hopefully" 而非 "will"，就是在留余地。
7. **RMS 单位是米，不是像素**——讲义已明确说明 RMSE 与测量量同单位。RMS = 8 意味着**平均差 8 米**。
8. **误做了 `Save as New` → `Export Raster`** → 教程明确**不推荐**，可能极其耗时。

### ★ 数字化（Digitising）相关

9. **未开 Snapping 就描相邻要素** → 直接制造讲义列举的拓扑错误：**undershoot（缝隙）、overshoot（悬挂）、sliver polygon、overlap、gap**。📎 教程全程没提 snapping，是这份教程的一个空白。
10. **误以为顶点越多越好** → 讲义原话 *Digitising involves **accuracy** not **density** of points*。顶点应加在**形状转折处**，不是均匀撒点。
11. **新建 feature class 时坐标系选错或留空** → 数字化出来的多边形与底图错位，且 `Shape_Area` 单位不可信。教程把 `Projected Coordinate Systems → National Grids → Australia → GDA 1994 MGA Zone 55` 这条路径**重复写了两遍**（Define Projection 一次、Create Feature Class 一次），就是在防这个错。
12. **Geometry Type 选错**：Strike_dip 必须是 **POINT**，Faults 必须是 **POLYLINE**，lakes 是 **POLYGON**。**feature class 建好后几何类型不能改**，只能删了重建。
13. **描图时误用普通鼠标滚轮/拖拽平移** → 会中断草图。教程给的正确做法是**按住 `c` 键**。
14. **忘记 Finish**：草图没有结束就切换工具，要素不会被保存。

### ★ 属性表相关

15. **`Add Field` 后忘了在 `Fields` 标签 → `Changes` 组点 `Save`** → 字段根本没被创建，回到属性表找不到它。这是教程专门用一整段强调的一步。
16. **字段 Data Type 选错**：把倾角这种数值字段建成 **Text** → 之后无法做数值计算、排序也会按字符串排（"9" 排在 "10" 后面）。📎 教程用截图给出设置，文字层不可见，**建议 Short 或 Float**。
17. **📎 Field Calculator 的表达式语法**（教程未涉及，但作为通用易错点）：ArcGIS Pro 的 Calculate Field 默认用 **Python 3**，字段名在表达式中要写成 **`!FieldName!`**（前后各一个感叹号），字符串用引号；SQL 语法（`[FieldName]`）是旧版 VBScript 的写法，**在 Python 解析器下会报错**。
18. **📎 Join 与 Relate 的基数（cardinality）搞错**（教程未涉及，属 W04 内容，提前预警）：**Join 只支持 one-to-one 或 many-to-one**；若目标表与源表实际是 **one-to-many**，Join 只会**保留匹配到的第一条记录**并**静默丢弃其余**——不会报错，结果却是错的。这种情况必须用 **Relate** 或 **Spatial Join**（后者可设 **Join Operation = JOIN_ONE_TO_MANY**）。
19. **📎 Buffer 的单位与坐标系不匹配**（教程未涉及，属 W04 内容，提前预警）：在**地理坐标系（GCS，单位为度）**的图层上做 Buffer 并填 "500 Meters"，工具会用近似换算，在高纬度产生显著变形。**做距离类分析前必须先投影到投影坐标系（PCS，单位为米）**。本周的 MGA Zone 55 就是一个合适的 PCS。

### ★ 概念层面的重点难点

20. **Capture vs Transfer**：capture 是**生成新数据**（直接测量或模拟转数字）；transfer 是**转换/翻译已有数字数据并导入**。
21. **Rasterisation vs Vectorisation 的后果不同**：前者是 **loss of information（信息损失）**，后者是 **distortion（失真）**。两个词不能互换。
22. **Similarity vs Affine**：相似变换**保形（角度不变）**；仿射变换**保平行（角度、长度可变）**，**最少 3 个控制点**。
23. **Accuracy vs Precision**：讲义定义 **Precision = the recorded level of detail（记录的细节层次）**——注意这是「记录了多少位/多细」，**不等于「准」**。数据可以很 precise（记到小数点后 6 位）却完全不 accurate（差了 500 m）。
24. **Overall Accuracy 的分母**：讲义式子省略了 ÷ 总数。**自己计算时必须写全**：对角线之和 ÷ 全部样本数。
25. **数据质量是相对于用途的**：讲义定义里的落点是 "appropriate for a **particular use**"。不存在脱离用途的「高质量数据」。

---

## 七、本周术语表

### A. 数据采集与输入（Data Capture & Input）

| 英文 | 中文 | 说明 |
|---|---|---|
| Spatial data capture | 空间数据采集 | 生成新数字空间数据的过程；含直接测量与模拟-数字转换 |
| Spatial data transfer | 空间数据传输 | 转换/翻译**已有**数字空间数据并导入 GIS |
| Keyboard entry | 键盘录入 | 手工键入点坐标；仅适用于点数很少时 |
| XY events | XY 事件 | 键盘录入语境下点要素的别称 |
| Digitising / Digitizing | 数字化 | 描摹地图或影像上的要素并记录坐标 |
| Manual digitising | 手工数字化 | 用 digitizing table + puck 在纸图上描摹 |
| Digitizing table | 数字化板 | 手工数字化的硬件 |
| Puck | 游标 / 鼠标器 | 数字化板配套的带十字丝定点设备 |
| On-screen digitising | 屏幕数字化 | 在扫描影像上于屏幕描摹；受扫描分辨率限制 |
| Automatic digitising | 自动数字化 | 用 raster-to-vector conversion 自动生成矢量 |
| Raster-to-vector conversion | 栅格转矢量 | 自动数字化的核心技术 |
| Automated digital mapping | 自动化数字制图 | 自动数字化所属的更大趋势 |
| Vertex (pl. vertices) | 顶点 | 构成线/面的坐标点；ArcGIS Pro 中显示为绿点 |
| Field surveying | 野外测量 | 通过野外直接测量采集空间数据 |
| Total station | 全站仪 | 现代野外测量仪器 |
| Photogrammetry | 摄影测量 | 用重叠航片立体像对测 (x,y,z) 坐标 |
| Stereo-pair | 立体像对 | 从不同视角拍摄的重叠像片对 |
| Overlap flight pattern | 重叠航线模式 | 无人机摄影测量的飞行方案 |
| LiDAR (Light Detection and Ranging) | 激光雷达 / 激光扫描 | 产生大量离散点的 (x,y,z) 坐标 |
| Mass points | 密集点 | LiDAR 产生的离散点 |
| Point cloud | 点云 | 同上 |
| Crowdsourcing | 众包 | 向公众征集空间数据；缺点：数据有偏、无所有权/保密性、丧失专业性 |
| Location-aware mobile devices | 位置感知移动设备 | 众包采集的载体 |

### B. GNSS

| 英文 | 中文 | 说明 |
|---|---|---|
| GNSS (Global Navigation Satellite System) | 全球导航卫星系统 | 总称 |
| GPS | 全球定位系统（美国） | 卫星轨道高度 20,200 km，周期 12 h，6 个轨道面 |
| GLONASS | 格洛纳斯（俄罗斯） | |
| Galileo | 伽利略（欧洲） | |
| BeiDou | 北斗（中国） | |
| Orbital plane | 轨道面 | GPS 有 6 个 |
| Frequency band | 频段 | 每颗卫星发 2–3 个频段，**至少 1 个为军用** |
| L1 / L5 | L1 / L5 频段 | **L5 为民用高精度频段** |
| C/N0 | 载噪比 | 信号功率与噪声功率密度之比；**35–45 dB-Hz 为良好** |
| TTFF (Time To First Fix) | 首次定位时间 | |
| E H/V Acc | 估计水平/垂直精度 | Estimated Horizontal / Vertical Accuracy |
| Alt | 椭球高 | 相对 **WGS84 ellipsoid** 的高程 |
| Alt (MSL) | 海平面高程 / 正高 | 基于 **geoid**，用 EGM96 等地球重力场模型 |
| WGS84 | 世界大地测量系统 1984 | GPS 采用的椭球/基准面 |
| EGM96 | 地球重力场模型 1996 | 定义海平面（geoid） |
| Geoid | 大地水准面 | |
| Sky map | 天空图 | 显示可见星座；**加粗轮廓 = 已连接卫星** |

### C. 数据格式与传输（Formats & Transfer）

| 英文 | 中文 | 说明 |
|---|---|---|
| FME (Feature Manipulation Engine) | 要素操作引擎 | ArcGIS Pro 内置，支持 **>300 种**格式 |
| Shapefile | ESRI ArcView Shapefile | 最常见矢量交换格式 |
| Coverage | ESRI ArcInfo Coverage | ESRI 早期拓扑矢量格式 |
| E00 | ArcInfo Interchange Format | |
| MIF | Map Interchange Format (MapInfo) | |
| DLG | Digital Line Graphs (USGS) | |
| DXF / DWG | AutoCAD 数据交换格式 / 图形文件 | |
| DGN | Microstation drawing file format | |
| SDTS | Spatial Data Transfer Standard（美国） | |
| NTF | National Transfer Format（**英国**） | |
| TIGER | 拓扑集成地理编码与参照系统（美国人口普查局） | |
| DIME | Dual Independent Map Encoding（美国人口普查局） | |
| VPF | Vector Product Format | |
| KML | Keyhole Markup Language (Google) | 讲义 OCR 误作 "EML" |
| WFS | Web Feature Service (OGC) | |
| GRID | ESRI GRID | 栅格格式 |
| DTED | Digital Terrain Elevation Data | |
| IMG | ERDAS IMAGINE | |
| TIFF / GeoTIFF | 标签图像文件格式 / 带地理参考的 TIFF | 配准后导出用 GeoTIFF |
| ECW | Enhanced Compress(ed) Wavelet | 小波压缩栅格 |
| USGS DEM | 美国地质调查局数字高程模型 | |
| NetCDF | Network Common Data Form (Unidata) | 多维科学数据 |
| S-57 | 国际海道测量组织电子海图格式 | 讲义 OCR 误作 "8-457" |

### D. 变换与编辑（Transformation & Editing）

| 英文 | 中文 | 说明 |
|---|---|---|
| Data structure conversion | 数据结构转换 | 即矢栅互转 |
| Rasterisation | 栅格化（矢→栅） | **loss of information（信息损失）** |
| Vectorisation | 矢量化（栅→矢） | **distortion（失真）** |
| Geometric transformation | 几何变换 | |
| Rubber sheeting | 橡皮拉伸 | 校正几何畸变（局部非刚性） |
| Similarity transformation | 相似变换 | 平移/旋转/缩放；**保持形状，角度不变** |
| Affine transformation | 仿射变换 | 缩放/斜切/旋转/平移；**保持平行性**；**最少 3 控制点**；= 1st Order Polynomial |
| Edge matching | 边缘匹配 | 跨图层/图幅对齐要素 |
| Line simplification / Weeding | 线简化 | 删除不显著弯曲与冗余顶点，保留本质形状 |
| Control point | 控制点 | 配准时连接源影像与目标坐标的点 |
| Link | 链接 | 控制点表中的一行（source → map） |
| Residual | 残差 | 单个控制点的误差，**单位为米** |
| 1st / 2nd Order Polynomial | 一阶/二阶多项式（变换） | 一阶 = Affine；二阶最少 6 点（📎 补充） |

### E. 误差与质量（Errors & Quality）

| 英文 | 中文 | 说明 |
|---|---|---|
| Data formatting errors | 数据格式误差 | 含 scale、coordinate projection、raster conversion |
| Cartographical generalisation errors | 制图综合误差 | |
| Location errors | 位置误差 | |
| Topological errors | 拓扑误差 | 要素未按空间规则正确连接/相交/对齐 |
| Spatial rules | 空间规则 | GIS 中定义的拓扑规则 |
| Undershoot | 未及 / 欠头 | 📎 线未画到位，留缝 |
| Overshoot | 过头 | 📎 线画过界，留悬挂 |
| Dangle | 悬挂线 | 📎 |
| Sliver polygon | 狭长缝隙多边形 | 📎 |
| Knot | 结 | 讲义提及，**是唯一「非手工数字化高发」的类型** |
| Attribute errors | 属性误差 | 观测/测量误差、录入误差、数据过时 |
| Spatial data quality | 空间数据质量 | accuracy / precision / completeness / consistency / timeliness，**相对特定用途而言** |
| Accuracy | 准确度 | |
| Precision | 精密度 | **the recorded level of detail（记录的细节层次）** |
| Completeness | 完整性 | 覆盖、分类、验证三方面的完整程度 |
| Consistency | 一致性 | 数据集间/内**无明显矛盾** |
| Timeliness | 时效性 | |
| Positional accuracy | 位置精度 | 坐标描述与真实位置的接近程度 |
| RMSE (Root Mean Square Error) | 均方根误差 | **与 x,y,z 同单位**；**RMSE = 0 表示无误差** |
| RMS | 均方根 | 配准中所有 link 的平均差异 |
| Error matrix / Cross-tabulation | 误差矩阵 / 交叉列表 | 行 = map data，列 = reference data |
| Overall accuracy | 总体精度 | **对角线之和 ÷ 总样本数** |
| Producer's accuracy | 生产者精度 | 📎 讲义未用此术语，即按**列**计算的类别精度 |
| User's accuracy | 用户精度 | 📎 讲义未用此术语，即按**行**计算的类别精度 |
| Metadata | 元数据 | data about data；描述 content / quality / condition |
| Lineage | 谱系 | 源数据来历 + 处理步骤的历史 |

### F. ArcGIS Pro 工具与界面（Practical 用到的，全部保留英文）

| 英文 | 中文 | 位置 / 说明 |
|---|---|---|
| **Add Data** | 添加数据 | Map 标签页 |
| **Calculate statistics** | 计算统计值 | 加载栅格时的提示，选 Yes |
| **Contents Pane** | 内容窗格 | 图层列表 |
| **Map View** | 地图视图 | |
| **Zoom to Layer** | 缩放至图层 | 右键图层 |
| **1:1 Zoom To Source Resolution** | 按源分辨率 1:1 缩放 | 右键栅格图层；找控制点的最佳显示 |
| **Define Projection** | 定义投影 | **只贴坐标系标签，不改坐标数值** |
| **Input Dataset or Feature Class** | 输入数据集或要素类 | Define Projection 的参数 |
| **Coordinate System** | 坐标系 | 点 globe 按钮选择 |
| **Projected Coordinate Systems** | 投影坐标系 | 选择路径的第一级 |
| **National Grids → Australia** | 国家格网 → 澳大利亚 | 选择路径 |
| **GDA 1994 MGA Zone 55** | 澳大利亚地理基准 1994 / MGA 55 带 | 本练习的坐标系（📎 EPSG:28355） |
| **Properties → Source → Spatial Reference** | 属性 → 源 → 空间参考 | 验证坐标系的位置 |
| **Imagery（tab）** | 影像（标签页） | Georeferencing 入口 |
| **Georeferencing / Georeference** | 地理配准 | 工具条 |
| **Auto Apply** | 自动应用 | 输入坐标后自动移动影像显示 |
| **Add Control Points** | 添加控制点 | 指针变十字丝 |
| **Input X and Y…** | 输入 X 和 Y | 在视图内右键调出 |
| **Enter Coordinates** | 输入坐标（对话框） | |
| **Target Coordinates box** | 目标坐标框 | 其中 **DMS = Degrees, Minutes, Seconds** |
| **Control Point (Table)** | 控制点表 | 显示 links 与 residuals |
| **Set SRS** | 设置空间参考系统 | Georeference 菜单；Manchester 练习 Hint 1 |
| **Locate** | 定位 | Georeference 菜单；Manchester 练习 Hint 2 |
| **Save / Exit Georeferencing** | 保存 / 退出地理配准 | |
| **Save as New / Export Raster** | 另存为新的 / 导出栅格 | **教程明确不推荐在本练习执行** |
| **Analysis（tab）→ Tools** | 分析标签页 → 工具 | Geoprocessing pane 入口 |
| **Geoprocessing pane** | 地理处理窗格 | 搜索工具的地方 |
| **Create Feature Class** | 创建要素类 | |
| **Feature Class Location** | 要素类位置 | |
| **Geometry Type** | 几何类型 | POINT / POLYLINE / **POLYGON（默认）** |
| **Spatial Reference Properties** | 空间参考属性 | Create Feature Class 中指定坐标系 |
| **Edit（tab）→ Create** | 编辑标签页 → 创建 | 打开 Create Features 窗口 |
| **Create Features** | 创建要素（窗口） | 上半选图层，下半选构造工具 |
| **Construction tools** | 构造工具 | Polygon / Line / Point 等 |
| **Polygon（tool）** | 面（构造工具） | |
| **Finish** | 完成 | 结束草图；也可双击 |
| **Attribute Table** | 属性表 | 右键图层调出 |
| **Attributes window** | 属性窗口 | 出现在 Map view 下方 |
| **ObjectID / Shape / Shape_Length / Shape_Area** | 对象 ID / 形状 / 周长 / 面积 | 系统自动创建的字段；**长度面积单位随坐标系** |
| **Add Field** | 添加字段 | 打开 Fields: \<名称\> 设计表 |
| **Fields（tab）→ Changes → Save** | 字段标签页 → 更改 → 保存 | **不点这里字段不会被创建** |
| **`c` key（按住）** | 按住 c 键 | 在配准/编辑状态下平移缩放 |
| **OS Open Background** | OS 开放底图 | ArcGIS Online 的英国底图（📎 British National Grid = EPSG:27700） |
| **British National Grid** | 英国国家格网 | Manchester 练习的坐标系 |
| 📎 **Snapping** | 捕捉 | Edit 标签页；**教程未提，但强烈建议开启** |
| 📎 **Field Calculator / Calculate Field** | 字段计算器 | **本练习未用**；表达式用 Python 3，字段写作 `!Field!` |
| 📎 **Project / Project Raster** | 投影 / 投影栅格 | **本周材料未出现**；真正做坐标变换的工具 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| Lecture 3 handout，"Global Navigation Satellite System (GNSS)" 页第 3 条 | "GPS (USA), GLONASS Russia), Galileo (Europe) and BeiDou (China) are **three** main GNSS systems that are currently operational." | **数量与列举不符**：句中列了 **4** 个系统却说 "three"。另 "GLONASS Russia)" 缺左括号 | 应为 "**four** main GNSS systems"；并写作 "GLONASS **(**Russia)"。GPS、GLONASS、Galileo、BeiDou 目前**均已完成全球组网**，确为四大系统 |
| Lecture 3 handout，"Cross-tabulation or error matrix" 页 | "Overall Accuracy = (28 + 15 + 20) = 63%" | **公式不完整**：只写了对角线求和，**漏掉了除以总样本数**这一步。本例总数恰为 100，数值上碰巧对得上，掩盖了错误 | 应为 **Overall Accuracy = (28 + 15 + 20) / 100 × 100% = 63%**。总数不等于 100 时，照原式计算会直接得出错误结果 |
| Lecture 3 handout，"Raster data capture" 页 | "Four main types **visible, infrared, multispectral, and hyperspectral**." | 列举无误（确为四项），但**句中缺少冒号/系动词**，且 "Visible and infrared" 在下方图注中被当作一类，与正文的四分法略有出入 | 建议读作 "Four main types**:** visible, infrared, multispectral and hyperspectral"。图注的 "Visible and infrared" 指的是**影像的显示波段组合**，不是第五个类别 |
| Lecture 3 handout，OCR 补充 Page 21 矢量格式表 | "**EML** (Keyhole Markup Language, Google)" | **格式名错误**（PDF 图片 OCR 误识） | 应为 **KML**（Keyhole Markup Language）。压缩版为 KMZ |
| Lecture 3 handout，OCR 补充 Page 21 栅格格式表 | "**8-457** (Intemational Hydrographic Organization)" | **格式名与单词均为 OCR 误识** | 应为 **S-57**（IHO 电子海图数据交换标准）；"Intemational" 应为 "**International**" |
| Lecture 3 handout，OCR 补充 Page 21 栅格格式表 | "ECW (Enhanced **Compressed** Wavelet)" | 全称用词略有出入 | 通行全称为 **Enhanced Compression Wavelet**（ERDAS/Hexagon 的小波压缩栅格格式）。属细微用词问题，不影响理解 |
| Practical 3，§1.1 第 1 段 | "download … from the Geoscience Australia Portal at **htps://portal.ga.gov.au**" | **URL 拼写错误**（PDF 文字提取丢字符） | 应为 **`https://portal.ga.gov.au`**。同一份 PDF 中 §4 的 ESRI 链接同样写作 "htps://"，问题相同 |
| Practical 3，目录及正文多处 | "Fit**ng** method"、"On-screen digit**s**ing"、"Feature class **atributes**"、"**Adding** … digit**s**ing" | **系统性的字符丢失**（PDF 连字 ti/tt 提取失败） | 应分别为 **Fitting**、**digitising**、**attributes**。属提取瑕疵而非作者笔误，阅读时按正确拼写理解即可 |
| Practical 3，§1.4 第 1 句 | "Click the **Control Point** button on the Georeferencing toolbar." | **按钮名称不完整**：ArcGIS Pro 的 Georeference 标签页中该按钮标注为 **Control Point Table** | 应为 **Control Point Table**（位于 Review 组）。按 "Control Point" 找容易与旁边的 **Add Control Points** 混淆 |
| Practical 3，§2.1 | "Name the Feature Class as **lakes**" ／ §2.3 "Right click **Lakes** feature class" | **大小写前后不一致** | 统一为 **`lakes`**（按 §2.1 创建时的名称）。ArcGIS 中要素类名通常不区分大小写显示，但引用时应保持一致 |
| Practical 3，§2.3 第 2 段 | "**Three** attributes are listed in the window for the digitised lake: ObjectID, Shape, Shape_length and Shape_Area. They are **three** fields in the attribute table created by the system" | **数量与列举不符**：说 "three" 却列了 **4** 个字段。另 `Shape_length` 大小写与 ArcGIS Pro 实际显示的 `Shape_Length` 不一致 | 应为 "**Four** attributes … **four** fields"；字段名应为 **`Shape_Length`**（首字母大写 L） |
| Practical 3，§2.2 Challenge 3 | "another feature class called 'Faults', create polylines and trace some of the simple **points** on the map" | **用词错误**：该要素类名为 Faults、几何类型为 polyline，却说描 "points"，语义不通 | 应为 "trace some of the simple **faults** on the map"（描出图上一些简单的**断层**） |
| Practical 3，§1.2 第 2 段 | "The map coordinate system is **GDA94 MGA Zone 55**" ／ 下文选择 "**GDA 1994 MGA Zone 55**" | 同一坐标系在两处写法不同（有无空格、简写与全称） | 二者指同一坐标系（**EPSG:28355**）。ArcGIS Pro 中的正式名称为 **GDA 1994 MGA Zone 55**，选择时按此名查找 |
| Practical 3，§2.2 收尾操作 | "After the final vertex is added, **double-click at the start point** (or right click Finish)." | **操作描述过严**：ArcGIS Pro 中双击可在**任意位置**结束多边形草图，系统会自动闭合到起点，不必精确双击起点 | 应为 "double-click **to finish the sketch**"。按原文操作虽可行，但会让人误以为必须精确对准起点 |

---

> **备注**：本周为本课**基础段最后一周**。下周（W04 Spatial Analysis）起进入分析段，并且**从第 4 周开始才有课堂 transcript**，笔记的「四、课堂补充」一段将改由录音整理，信息量会显著增加。
