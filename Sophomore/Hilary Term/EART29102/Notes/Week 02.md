# EART29102 Geospatial Techniques — Week 02 学习笔记

> **本周材料**
> - 讲义：`Lecture/Week 2/Lecture 2 - Spatial Data and Data Management.md`（约 946 词，是本课最薄的一份讲义；含低质量 OCR 补充段）
> - 实操：`Practical/Week 2/Practical 2 - Carlisle_Flood_Map.md`（约 1,796 词，篇幅接近讲义两倍）
> - 背景：`(EART29102) Geospatial Techniques.md`（官方大纲）
>
> ⚠️ **关于官方大纲**：本课官方大纲列出的是大地测量、GNSS、摄影测量、Lidar、声呐、无人机等主题，且把 GIS 排在 Week 6–7、把 Week 2 排为「Photogrammetry + CloudCompare 实习」。**实际授课与之严重不符**：实际是一门以 ArcGIS Pro 为主线的 GIS 课程（W01 GIS 导论 → W02 空间数据与管理 → W03 数据输入与操作 → W04 空间分析 → W05 空间统计 → W06 遥感 → W07 地形分析 → W08 空间可视化 → W09 三维技术 → W10 课程回顾）。大纲只能当作课程总体背景，**不能用来推断任何一周的内容**。

---

## 一、本周主题

本周是本课「基础段」的第二周，位置是：

```
基础段：W01 GIS 导论  →  【W02 空间数据与数据管理】  →  W03 数据输入与操作
分析段：W04 空间分析  →  W05 空间统计
专题段：W06 遥感 → W07 地形分析 → W08 空间可视化 → W09 三维技术
收尾：  W10 课程回顾
```

**与 W01 的衔接。** W01 回答的是「GIS 是什么、能做什么」：GIS 被定义为一个用于**捕获（capture）、管理（management）、存储（storage）、组织（organization）与分析（analysis）**空间参考数据、并输出空间参考信息的计算机系统；W01 还给出了六大功能（Capture / Store / Query / Analyse / Display / Present），并**已经预告过本周实习**——W01 讲义在「Buffering and proximity measurement（缓冲与邻近度量）」一页里写的例子正是「在河流周围建立 100 m 缓冲区以评估洪水风险，红色建筑物位于河流 100 m 缓冲带内」。本周实习 Carlisle 洪水图就是把那一页 PPT 变成实际操作。

W01 也已经初步区分了矢量（vector，离散数据）与栅格（raster，连续数据）两种空间数据模型。**W02 的任务是把 W01 这些「点到为止」的说法系统化**：空间数据到底是什么性质的数据、人类用哪两种方式去概念化地理空间、这两种概念化如何分别落到矢量与栅格两种数据结构、地图比例尺与制图综合如何决定数据里能留下多少细节、地球的形状与基准面（datum）如何决定坐标数值、投影如何把球面压成平面。

**讲义自列的 6 条学习目标**（Lecture 2 content，原文）：

1. the characteristics of spatial data（空间数据的特征）
2. object and field views and surface models（对象视角、场视角与表面模型）
3. understand map scale and cartographic abstraction（地图比例尺与制图抽象）
4. map projections and projected coordinate systems（地图投影与投影坐标系）
5. how spatial data are represented, structured and organised using computers（空间数据在计算机中如何表示、构造与组织）
6. understand differences between vector and raster representations（矢量与栅格表示的差异）

**⚠️ 一个必须先说清楚的落差。** 本周讲义标题叫 *Spatial Data and **Data Management***，但通读全篇 946 词后可以确认：**讲义几乎没有讲「数据管理」**——没有讲 shapefile 与 geodatabase 的格式差异、没有讲元数据（metadata）、没有讲数据质量维度、没有讲文件命名与版本管理。讲义的第 5 条目标「how spatial data are represented, structured and organised using computers」只落实到「矢量存为 feature class、栅格存为像元网格」这个层面。真正的「数据管理」内容是**在实习里以操作形式出现的**（从 ArcGIS Online 加载数据、按范围裁出子集另存为图层、给图层重命名、给地图命名、清除选择集、导出与出图）。因此本笔记的「二、核心概念」会分成两块：**2.1–2.10 是讲义实有内容**，**2.11 是从实习反推 + 背景补足的数据管理知识，全部用 📎 标记**。

**本周实习的目标问题**：Carlisle（卡莱尔）位于 River Eden（伊登河）洪泛平原上，三条河在市区交汇，历史上多次洪灾（2005 年那次 3 人死亡、逾 1,800 处房产进水）。实习要用 Ordnance Survey（英国陆地测量局，OS）的开放地图数据，在 ArcGIS Pro 里回答一个具体问题：**Carlisle 有多少建筑物面临洪水风险？**

---

## 二、核心概念

### 2.1 空间数据的性质（Nature of spatial data）

讲义给出三条判断（原文三点）：

1. **空间数据通常是「观测性的（observational）」而非「实验性的（experimental）」。**
   📎 背景补充：这一条的含义讲义没有展开。它指的是——你无法像实验室那样设定自变量、控制其他变量再重复取样；地理现象是在真实世界中被**观察**到的，样本位置往往不是随机分布、观测之间彼此不独立（空间自相关，spatial autocorrelation，W05 空间统计会正式处理），也无法重做一次「同样的实验」。这直接导致后续所有分析必须承认数据是**给定的、有偏的、不可复现采集的**。

2. **空间数据通过一个特定的「概念化（conceptualisation）与表示（representation）」过程，把真实世界的复杂性以有限形式（finite form）捕捉下来。**
   这是本周最核心的一句话：**数据永远是真实世界的模型，不是真实世界本身**。「有限形式」意味着必然有取舍——取舍的规则就是 2.2 的两种视角与 2.5 的制图综合。

3. **空间数据按某个特定的地理参照系统（georeferencing system）记录位置。** 位置数值本身没有绝对意义，只在给定的基准面与坐标系下才有意义（见 2.6–2.8）。

### 2.2 两种概念化：对象视角与场视角（Object view vs Field view）

这是本周的**理论骨架**，后面矢量/栅格的分野完全由它决定。

| | **对象视角 Object view** | **场视角 Field view** |
|---|---|---|
| 空间被看作 | 由一个个**独立对象（individual objects）**填充的空白空间 | 被**连续表面（continuous surfaces）**完全覆盖 |
| 元素 | point（点）、line（线）、area/polygon（面）对象，也称 **features（要素）** | 属性值在**每一个位置**都有定义 |
| 讲义原文强调 | exactly located（位置精确）、well-defined boundaries（边界明确）、countable（可计数） | attribute values can be defined at every location |
| 对应数据模型 | **矢量 vector** | **栅格 raster** |
| 典型例子 | 建筑物、道路、行政区、气象站 | 高程、气温、坡度、卫星影像反射率 |

📎 背景补充：判断一个现象该用哪种视角，问两个问题即可——(a)「它有没有自然边界？」有 → 对象；(b)「问『这个点上它的值是多少』有没有意义？」有意义 → 场。**同一现象可以两种视角并存**：本周实习里，河流被当作**对象**（OS Open Rivers 的线要素），而底图地形是**场**；洪水淹没范围既可以是对象（Flood Alert Area 多边形）也可以是场（淹没水深栅格）。

### 2.3 表面模型：DEM 与 DTM（Surface Models）

| 术语 | 讲义定义（原文要点） |
|---|---|
| **DEM — Digital Elevation Model（数字高程模型）** | 地形表面的三维表示；是 **'bare-earth'（裸地）**高程模型，即**不含**植被、人工构筑物及其他非地形物体；DEM 通常是**栅格**（grid of squares）或**基于矢量的 TIN**（triangulated irregular network，不规则三角网） |
| **DTM — Digital Terrain Model（数字地形模型）** | 是「一个 DEM 再加上其他地表特征信息」，包括地形形态（**slope 坡度**、**curvature 曲率**）与**drainage structure（水系结构）** |
| 讲义附注 | *DTM and DEM are often used interchangeably because they are similar*（两者常被混用，因为它们很相似） |

⚠️ **术语警告（重要）**：讲义这套 DEM/DTM 定义**与业界更常见的约定不一致**，考试与阅读文献时都容易踩坑。更常见的约定是：

📎 背景补充（业界常见约定，讲义未讲）：
- **DSM（Digital Surface Model，数字表面模型）**＝包含植被冠层、建筑物顶面等一切地表反射面的高程；
- **DTM / DEM（裸地）**＝剥掉地物后的地面高程；
- 即通常是把 **DTM 当作裸地**、把 **DSM 当作含地物**，而讲义把「裸地」派给 DEM、把「DEM + 坡度曲率水系」派给 DTM。
- **应试策略**：以讲义定义作答（因为出题以讲义为准），但心里清楚 DSM 这个第三个概念的存在——W07 地形分析会真正用到 slope / curvature / 水系提取，届时讲义所谓「DTM 的附加信息」其实就是从 DEM **派生（derive）**出来的产品。

### 2.4 TIN（Triangulated Irregular Network，不规则三角网）

讲义要点（原文）：

- 是**基于矢量（vector-based）**的表面形态模型；
- 表面被建模为**连续（contiguous）的三角形层**；
- **每个三角形是一个平面，梯度（gradient）恒定**；
- TIN 中每个点作为顶点（vertices，讲义原文误拼为 "verticies"）具有 **3D 坐标 (x, y, z)**。
- 讲义引用：*OS Terrain 5m TIN — 使用三角形，比格网（grid）能更准确地贴合地物特征*，并给出 OS Terrain 5 用户指南链接。

📎 背景补充（TIN vs 栅格 DEM 的取舍，讲义未系统对比）：
- TIN 的优势是**采样密度可变**——地形破碎处三角形密、平坦处三角形疏，因此在相同精度下数据量小，且能沿山脊线、河道等**断裂线（breaklines）**精确保形；
- 栅格 DEM 的优势是结构规整、算法简单（坡度、坡向、水文分析工具几乎都以栅格为输入）、易与影像叠加；
- 实践中常见流程是：用 TIN 建模 → 转成栅格再做分析。

### 2.5 地图比例尺（Map scale）

讲义定义：**地图或影像上的距离与地面对应距离之比（The Ratio of distance on the map or image to the corresponding distance on the ground）。**

讲义的表述：

> Smaller the map scale: ➢ the larger the ratio ➢ less accurate ➢ more abstract
> The smaller the map scale, the fewer geographical features and less detail about these geographical features can be captured and represented.
> 1:3,000,000 / 1:800,000 — *Small scale = large area, Less detail*
> 1:40,000 — *Large scale = small area, More detail*

**读法**（这是最容易记反的一点）：
- **大比例尺（large scale）** = 分数值大（1/40,000 > 1/3,000,000）= **覆盖范围小、细节多**，例：1:1,250、1:10,000（本周实习出图用的就是 1:10,000）；
- **小比例尺（small scale）** = 分数值小 = **覆盖范围大、细节少、更抽象**，例：1:3,000,000。

⚠️ 讲义那句 "Smaller the map scale... the larger the ratio" 措辞含糊：它指的是**冒号后面那个分母数字更大**（3,000,000 > 40,000），而不是「比值（representative fraction）更大」——按分数看恰恰更小。见文末勘误表。另外讲义把小比例尺说成 "less accurate"（精度更低）也不够严谨，更准确的说法是 **less detailed / more generalised（细节更少、综合程度更高）**，因为小比例尺地图上的要素位置本身仍可以是正确的，只是被简化和移位了。

📎 背景补充：与比例尺配套但讲义未提的两个实务概念——
- **Scale-dependent rendering（随比例尺显示）**：ArcGIS Pro 中可为图层设置 Visibility Range（可见比例尺范围），避免小比例尺下绘制百万级要素而卡死。本周实习「先裁出 Carlisle 小范围让地图画得更快」解决的是同一类性能问题，只是用的是裁数据而非限显示。
- **数字地图没有固定比例尺**：可以无级缩放，但**数据本身的采集比例尺（source scale）是固定的**。把 1:250,000 的数据放大到 1:1,000 显示，屏幕上看似精细，实际精度并未提高——这是 GIS 里最常见的误用之一。

### 2.6 制图综合 / 抽象（Generalisation / Cartographic abstraction）

讲义定义：**制图综合是把现实转换为地图的过程（the process of transforming reality to a map）**。六种操作（讲义全部粗体列出）：

| 操作 | 讲义原文含义 | 📎 例子（补充） |
|---|---|---|
| **Selection（选取）** | 选择并保留最重要的地理要素 | 只画主干河流，去掉细支流 |
| **Simplification（简化）** | 去除复杂性 | 海岸线折点抽稀 |
| **Exaggeration（夸大）** | 保留或强调重要特征 | 把 3 m 宽的道路画成图上可见的宽度 |
| **Combination（合并）** | 合并相似要素 | 把一排小建筑合并成一个街区面 |
| **Displacement（位移）** | 移动对象以保持可区分 | 铁路与并行公路互相挪开以免叠压 |
| **Classification（分类）** | 按属性对要素分组 | 建筑物分为「一般建筑 / 重要建筑」——**这正是实习里 OS OpenMap Local Buildings 与 Important Buildings 两个图层的由来** |

**为什么这一节重要**：它解释了「为什么两份都号称正确的数据会对不上」。同一条河在 1:10,000 与 1:250,000 数据中位置会差几十米，不是谁错了，而是综合程度不同。本周实习用河流**中心线（centreline）**做 100 m 缓冲，本身就是一次极端的综合——把有宽度的河道抽象成一条无宽度的线。

### 2.7 地球的形状：geoid、spheroid 与 datum

讲义给出的三层递进（原文）：

- **geoid（大地水准面）** = 地球重力场的**等位面（an equipotential surface of the Earth's gravitational field）** = **平均海平面（mean sea level）**；
- **reference spheroid（参考椭球体）** = 地球大地水准面的**光滑表面模型（smooth surface model of Earth's geoid）**；
- 讲义标注 **a − b = 21.4 km**（赤道半径与极半径之差，即地球扁率造成的差值）；
- **主要的参考椭球体**：**WGS = World Geodetic System**（世界大地测量系统）、**GRS = Geodetic Reference System (1980)**（大地参考系统 1980）；
- **datum（基准面）accounts for local variations（用于顾及局部差异）**：讲义原文——**「地理坐标值取决于所选的参考椭球体与基准面（Geographical coordinate values depend upon the chosen reference spheroid and datum）」**。

**这句话是本周最实用的一条**：同一个地面点，在不同 datum 下经纬度数值不同，差异可达**上百米**。这就是后面「坐标系不匹配 → 图层错位」的根源。

📎 背景补充（讲义未给具体代号，但实习与后续周次必然用到）：
- **WGS 84**（EPSG:4326）：GPS/GNSS 使用的全球基准，也是 ArcGIS Online 底图与 Web 服务的通用基准；
- **GRS 1980** 椭球 + **ETRS89** 基准：欧洲现行标准；
- **OSGB 1936 / British National Grid（英国国家格网）**，EPSG:**27700**，基于 **Airy 1830** 椭球，投影为 **Transverse Mercator**：**所有 Ordnance Survey 数据（含本周实习用的 OS Open Rivers、OS OpenMap Local）的原生坐标系**。OSGB36 与 WGS84 在英国境内的差异可达 **100 m 量级**，绝不可忽略。
- **Web Mercator（EPSG:3857）**：ArcGIS Online 底图（World Topographic Map 等）的默认显示坐标系。

⚠️ **实习中的隐含陷阱**：Practical 2 全程**没有提到任何一次坐标系设置**。实际情形是——从 ArcGIS Online 加载的服务已带各自的坐标系，ArcGIS Pro 会**按第一个加载图层定义地图坐标系**并对其余图层做**即时投影（on-the-fly projection）**。这在显示上没问题，但**缓冲区距离计算发生在地图坐标系里**：若地图处于 Web Mercator，100 m 的实际地面距离会随纬度被放大（Carlisle 约北纬 54.9°，放大因子约 1/cos54.9° ≈ 1.74）。见第六节「易错点」。

### 2.8 地理坐标系与地图投影

**地理坐标系（Geographic coordinate system, GCS）** — 讲义只给了三个词：**Parallels（纬线/纬圈）**、**Meridians（经线/子午线）**、**Prime meridian（本初子午线）**。即用经度 λ、纬度 φ 这一对角度量在椭球面上定位。

**地图投影（Map projections）** — 讲义分类：

- **'Normal' map projections（正轴投影）** 三大族：**cylindrical（圆柱）**、**conic（圆锥）**、**azimuthal（方位）**；
- **Cylindrical map projections**：标注 **Standard parallels（标准纬线）**、**Secant lines cut the sphere（割线切入球体）**；
- **Secant Normal Mercator projection（正轴割圆柱墨卡托）**：讲义用一行文字描述变形分布——*Increasing distortion / No distortion / Increasing distortion / No distortion / Increasing distortion*，即在**两条标准纬线上无变形**，向两侧变形递增；
- **Mercator projection 的性质**（讲义粗体两点）：
  - ✅ **preserves shapes and directions（保持形状与方向）** —— 即等角（conformal），这是它成为航海投影的原因；
  - ❌ **distorts area and distances (apart from equator)（面积与距离变形，赤道除外）** —— 讲义配了一页 "Some countries are smaller than you think!"（有些国家没你想的那么大），说明高纬国家（格陵兰、俄罗斯）被严重放大。
- **UTM（Universal Transverse Mercator，通用横轴墨卡托）系统**：讲义仅有标题页，无文字。

📎 背景补充（UTM 关键参数，讲义未写但必须知道）：UTM 把地球按经度分成 **60 个 6° 带（zone）**，自 180°W 起编号 1–60；每带用一个**横轴墨卡托**投影，中央经线比例因子 **0.9996**（割投影）；南北向分 C–X 字母带；坐标单位为米，东偏移（false easting）500,000 m，南半球再加北偏移 10,000,000 m。**英国主要落在 UTM Zone 30N 与 31N**，但英国本土制图实际用的是 **British National Grid** 而非 UTM。

📎 背景补充（讲义未讲的投影性质分类，是理解「为什么有这么多投影」的钥匙）：任何投影都不可能同时保持全部性质，只能取舍——
- **Conformal（等角）**：保角度/局部形状，牺牲面积。例：Mercator、Transverse Mercator、UTM、British National Grid。
- **Equal-area / equivalent（等积）**：保面积，牺牲形状。例：Albers、Mollweide。**做面积统计必须用等积投影。**
- **Equidistant（等距）**：沿特定方向保距离。
- **Compromise（折中）**：都不保但都不太差。例：Robinson、Winkel Tripel。
- 记忆口诀：**要量面积用等积，要看形状用等角，要算距离先看投影**。

### 2.9 矢量数据模型（Vector data model）

讲义原文要点：

- **基于地理空间的对象视角（Based on the object view of geographical space）**；
- 矢量数据模型通常把空间数据存储为 **feature classes（要素类）**；
- **feature class 的定义（必背）**：*a collection of geographical features of the **same geometric type** (point, line and polygon) with the **same set of attributes***——具有**相同几何类型**且拥有**同一套属性字段**的地理要素的集合。
- 讲义给的三个例子：
  - **point feature class**：气象站，点上带各气象变量观测值；
  - **line feature class**：河流（streams），带一组河流属性（length 长度、elevation 高程、gradient 坡降）；
  - **polygon feature class**：地块（land parcels），带土地利用类型（land use types）。

**注意这三个例子与实习完全对应**：OS Open Rivers 是 line feature class，OS OpenMap Local Buildings 是 polygon feature class，Buffer 的输出也是 polygon feature class。

「Vector data model coordinates（矢量数据模型的坐标）」一页无文字。📎 背景补充其应有内容：点由单个 (x, y) 坐标对定义；线由有序坐标串（vertices 顶点 + 两端 nodes 节点）定义；面是首尾闭合的线。**拓扑（topology）**——邻接、连通、包含关系——可以显式存储（如 geodatabase 的 topology 规则）或隐式计算。

### 2.10 栅格数据模型（Raster data model）

讲义原文要点：

- **基于场视角（Raster data model is based on field view）**；
- 「Elements of a raster（栅格的组成要素）」一页给出**像元深度（Cell or pixel depth）**：
  - **greyscale（灰度）**：8-bit = 2⁸ − 1 = **0–255 shades**（黑到白）
  - **colour（彩色）**：8-bit RGB channels = **16.7 million colours**（1670 万色）
- 「Raster representations with different cell sizes」：**Increasing cell size = lower resolution and loss of detail（像元尺寸增大 = 分辨率降低、细节丢失）**。
- 该页还标了一个 **North（北）**方向，说明栅格网格通常按行列排列、行方向与坐标轴对齐。

⚠️ 讲义 "2⁸ − 1 = 0–255 shades" 的写法把**灰阶数量**与**最大值**混为一谈：8-bit 有 **2⁸ = 256** 个灰阶，取值范围是 **0 到 2⁸ − 1 = 255**。见勘误表。

📎 背景补充（栅格的完整要素，讲义只给了深度和像元尺寸）：一个栅格完整定义需要——**行列数（rows × columns）**、**像元尺寸（cell size / spatial resolution）**、**原点/范围（origin / extent）**、**坐标系**、**波段数（bands）**、**像元深度与数据类型**（8-bit unsigned integer、16-bit signed、32-bit float 等）、**NoData 值**。这七项在 ArcGIS Pro 里可通过图层右键 **Properties → Source** 查看。

### 2.11 📎 数据管理（Data Management）——讲义标题有、内容缺，此节全部为背景补充

> **⚠️ 本节全部内容不来自 Week 2 讲义**。讲义虽以 "Data Management" 命名，却未涉及以下任何一条。本节内容由两部分构成：(a) 从 `Practical 2 - Carlisle_Flood_Map.md` 的操作步骤反推出的、不懂就做不下去的知识；(b) 通用 GIS 数据管理常识。**复习时请把本节当作「理解本周实习所必需的背景」，而不是「讲义考点」**。

#### 📎 A. 空间数据的来源与类型

| 来源 | 说明 | 本周对应 |
|---|---|---|
| **实地实测（field survey / ground survey）** | 全站仪、GNSS 接收机、水准测量 | 无 |
| **遥感（remote sensing）** | 卫星影像、航空摄影、Lidar、声呐 | 底图 World Topographic Map / World Hillshade 的底层影像 |
| **既有数据集（existing / secondary datasets）** | 国家测绘机构、政府部门、科研机构发布 | **OS Open Rivers**、**OS OpenMap Local**、**Environment Agency Flood Alert Areas** |
| **众包（crowdsourced / VGI, volunteered geographic information）** | OpenStreetMap、Geo-Wiki 等 | W01 讲义的「Further resources」推荐过 Geo-Wiki 与 OpenStreetMap |

#### 📎 B. 常见数据格式与其结构、限制

| 格式 | 类型 | 结构 | 关键限制 |
|---|---|---|---|
| **Shapefile（.shp）** | 矢量 | **多文件集合**：`.shp`（几何）+ `.shx`（索引）+ `.dbf`（属性表）+ `.prj`（坐标系）+ 可选 `.cpg`/`.sbn` 等，**必须整组一起复制** | 字段名 ≤ **10 字符**；单文件 ≤ **2 GB**；不支持 NULL；日期无时间部分；不支持拓扑/子类型/域；一个 shapefile 只能存一种几何类型 |
| **File geodatabase（.gdb）** | 矢量 + 栅格 + 表 | 一个**文件夹**，内含多个二进制文件；Esri 原生格式 | 每个要素类 ≤ 1 TB；字段名可长；支持 NULL、域（domain）、子类型、拓扑、关系类 |
| **GeoTIFF（.tif）** | 栅格 | TIFF 影像 + 内嵌地理参考标签（坐标系、原点、像元尺寸）；也可用外挂 `.tfw` world file | 单文件默认 ≤ 4 GB（需 BigTIFF 突破）；无内建金字塔时显示慢（需 build pyramids） |
| **CSV / Excel 表** | 非空间表格 | 纯属性；若含 X/Y 列可用 **Display XY Data** 转为点要素 | 无坐标系信息，须手工指定；字段类型靠推断，易出错 |
| **Feature service / Map service（ArcGIS Online）** | 网络服务 | 数据存于云端，本地只是引用 | **断网即失效**；服务被下线或权限变更即断链；不适合长期存档 |

**⚠️ 与本周实习直接相关**：Practical 2 的全部数据都来自 **ArcGIS Online 的在线服务**，本地并没有真正的数据文件。这就是为什么实习要反复做 **Make Layer From Selected Features**——把在线大数据集的一小块「固化」成本地可控的图层。Challenge Exercise 里也明确写了加载 EA Flood Alert Areas 后「**A new shape file has been added as a layer**（一个新的 shapefile 作为图层被加入）」。

#### 📎 C. Geodatabase 的组织层级

```
File Geodatabase  (MyProject.gdb  ← 实际是一个文件夹)
│
├── Feature Dataset（要素数据集）「Carlisle_Flood」   ← 容器；同一 dataset 内所有要素类共享同一坐标系
│   ├── Feature Class（要素类）「Rivers」        [line   线]
│   ├── Feature Class「Buildings」              [polygon 面]
│   ├── Feature Class「rivers_buffer100」       [polygon 面]
│   └── Topology / Network dataset（可选）      ← 只能建在 feature dataset 内
│
├── Feature Class（独立要素类，不在 dataset 内）「Sites」 [point 点]
│
├── Raster Dataset（栅格数据集）「carlisle_dem」
├── Raster Catalog / Mosaic Dataset（镶嵌数据集，管理大批影像）
│
├── Table（属性表，无几何）「flood_records」
└── Toolbox / Locator / Domain（域）/ Relationship Class（关系类）
```

**关键点**：
1. **Feature dataset 的唯一硬约束是「共享坐标系」**——把要素类放进同一个 feature dataset，就强制它们坐标系一致；这是防止图层错位最省事的手段。
2. **Topology 与 network dataset 只能建在 feature dataset 里**，独立要素类无法参与。
3. ArcGIS Pro 新建 Project 时会**自动创建一个同名 .gdb 作为 Default Geodatabase**，所有地理处理工具的输出**默认写进这里**——W01 Practical 里「New Project → Map」这一步就已经建好了。**这解释了本周实习为何从不指定输出路径：Buffer 的输出直接落进了默认 gdb。**

#### 📎 D. 元数据（Metadata）

**定义**：关于数据的数据——描述一份数据集「是什么、从哪来、什么时候、怎么做的、精度如何、能怎么用」。

应包含（ISO 19115 / INSPIRE 的核心项）：
- **标题、摘要、用途（purpose）**
- **空间范围（extent）与坐标系**
- **分辨率 / 采集比例尺**
- **生产者、联系方式**
- **时间信息**：采集日期、发布日期、更新周期（currency 时效性）
- **谱系（lineage）**：源数据是什么、经过哪些处理步骤
- **质量说明**：精度、完整性、一致性
- **使用限制与许可（use constraints / licence）**

在 ArcGIS Pro 中查看/编辑：**Catalog pane → 右键数据项 → View Metadata / Edit Metadata**。

#### 📎 E. 数据质量的维度

| 维度 | 含义 | 本周实例 |
|---|---|---|
| **Accuracy（准确度）** | 测量值与**真值**的接近程度——衡量**系统偏差** | 建筑物轮廓与实际墙线的偏差 |
| **Precision（精密度）** | 重复测量之间的**一致性**，也指记录数值的**位数** | 坐标记录到小数点后 6 位不代表准到 0.1 m |
| **Resolution（分辨率）** | 可分辨的最小单元 | OS Terrain 5 的 5 m 格网；OpenMap Local 的采集比例尺约 1:10,000 |
| **Completeness（完整性）** | 应有要素是否全部存在 | OS Open Rivers 是否包含所有细小水道（明显不含全部沟渠） |
| **Currency / timeliness（时效性）** | 数据反映的是哪个时点 | 2005 年洪水后新建的房屋是否已入库 |
| **Lineage（谱系）** | 数据的来源与处理历史 | `rivers_buffer100` 的谱系 = OS Open Rivers → 矩形选择 → Make Layer → Buffer 100 m |
| **Logical consistency（逻辑一致性）** | 拓扑与属性是否自洽 | 建筑物面是否自相交、河段是否断头 |

**Accuracy vs Precision 的经典四象限**（靶心比喻）：
```
          高 Accuracy              低 Accuracy
高       弹着点密集且都在靶心      弹着点密集但整体偏离靶心
Precision   ← 理想                  ← 有系统误差（如用错 datum！）
低       弹着点分散但平均在靶心    弹着点又散又偏
Precision   ← 有随机误差             ← 最差
```
**用错基准面（datum）正是「高精密度、低准确度」的典型**：所有点都整齐一致，但整体系统性平移了上百米。

#### 📎 F. 数据许可与来源引用

- **OS OpenData**（含 OS Open Rivers、OS OpenMap Local）按 **Open Government Licence (OGL)** 发布，**免费可商用，但必须署名**，标准署名文字形如：*Contains OS data © Crown copyright and database right [year]*。
- **Environment Agency** 数据同样多为 OGL。
- **地图上必须出现的署名**：数据来源、版权声明、坐标系、比例尺、制图日期、制图者。**这是出图评分里最常被扣分的一项。**

#### 📎 G. 存储、命名与版本管理的良好实践

1. **不要用中文、空格、特殊字符**做图层与文件名；shapefile 的字段名 ≤ 10 字符、不以数字开头。
2. **命名要自解释且含处理信息**：`rivers_buffer100` 就是好名字（对象 + 操作 + 参数）；`selection selection`（实习里 Make Layer From Selected Features 两次后产生的默认名）是坏名字——**这正是实习明确要求你把它改成 `Flood Risk local buildings` 的原因**。
3. **项目自包含**：ArcGIS Pro 的 `.aprx` 只存**图层对到数据源的引用路径**，不存数据。把项目文件夹整体移动、或数据被挪走，就会出现**断链（broken link，图层前出现红色感叹号）**。修复：右键图层 → **Properties → Source → Set Data Source**，或 **Repair Data Source**。
4. **归档打包**：**Share 选项卡 → Package Project / Project Package (.ppkx)**，会把数据一并打进包内，是提交作业与长期存档的正确做法。
5. **版本管理**：中间成果保留，不要就地覆盖；命名带日期或版本号（`carlisle_flood_v2_20260212`）。

---

## 三、公式与图表

本周定量内容确实很少，但有几处必须会算，另有几张只有图没有文字的关键页需要用文字复原。

### 3.1 比例尺换算

$$\text{Scale (RF)} = \frac{\text{图上距离}}{\text{地面距离}}$$

- **1:10,000**（本周实习出图比例尺）：图上 1 cm = 地面 10,000 cm = **100 m**；图上 1 mm = 地面 10 m。
- **1:40,000**（讲义的「large scale」例）：图上 1 cm = 地面 400 m。
- **1:3,000,000**（讲义的「small scale」例）：图上 1 cm = 地面 30 km。

📎 补充：**判断大小比例尺的机械方法**——把比例尺写成分数，分数值大的就是大比例尺。1/40,000 = 0.000025 > 1/3,000,000 = 0.00000033，所以 1:40,000 是大比例尺。

📎 补充：**成图幅面估算**。Carlisle 市区约 5 km × 4 km，按 1:10,000 出图，图面尺寸 = 5,000 m / 10,000 = 0.5 m = **50 cm × 40 cm**，即需要 **A2 幅面**。这决定了实习第 10 步「Select the preferred page size and orientation（选择页面尺寸与方向）」该怎么选。

### 3.2 像元深度与灰阶数

$$\text{灰阶数} = 2^{n}, \qquad \text{取值范围} = 0 \ \text{到}\ 2^{n}-1$$

- 8-bit：**256** 个灰阶，值域 **0–255**（0 = 黑，255 = 白）。
- 24-bit 真彩（3 个 8-bit RGB 通道）：$256^3 = 2^{24} = 16{,}777{,}216 \approx$ **1670 万色**（讲义的 "16.7 million colours"）。
- 📎 补充：1-bit = 2 值（二值掩膜）；16-bit = 65,536 阶（Landsat/Sentinel 常用）；32-bit float 用于连续量如高程、NDVI。

### 3.3 栅格分辨率与文件体积

$$\text{像元数} = \frac{\text{范围宽}}{\text{像元边长}} \times \frac{\text{范围高}}{\text{像元边长}}, \qquad
\text{体积} \approx \text{像元数} \times \frac{\text{位深}}{8} \times \text{波段数}$$

**关键结论（讲义只用图示、未给公式）**：**像元边长减半 → 像元数变为 4 倍 → 体积变为 4 倍**。这就是讲义 "Increasing cell size = lower resolution and loss of detail" 的另一面：分辨率与存储成本是平方关系。

📎 算例：Carlisle 研究区 10 km × 10 km，
- 5 m 像元：2,000 × 2,000 = 4,000,000 像元，8-bit 单波段 ≈ **4 MB**；
- 1 m 像元：10,000 × 10,000 = 100,000,000 像元，8-bit 单波段 ≈ **100 MB**（25 倍）；
- 1 m、3 波段、16-bit：≈ **600 MB**。

### 3.4 缓冲区几何

$$\text{缓冲带总宽度} = 2 \times \text{buffer distance}$$

本周实习对**河流中心线（centreline）**做 100 m 缓冲，得到的是一条**总宽约 200 m** 的走廊（河道两侧各 100 m）。⚠️ 由于用的是中心线而非河岸线，**河道本身的宽度被算进了这 200 m 里**——真实的「离岸 100 m」范围比这个缓冲带更宽。这是实习方法论上的第一个简化。

📎 补充：**Dissolve（融合）对面积统计的影响**。多条河流各自缓冲会产生**重叠区**，此时缓冲图层的总面积 = Σ 各段面积 > 实际覆盖面积。实习第 8 步提示可在重算 Buffer 时选 **Dissolve all output features into a single feature** 来消除重叠。注意：**是否 dissolve 不影响 Select By Location 的建筑物计数**（一栋建筑无论落在几个重叠缓冲里都只被选中一次），但**严重影响缓冲区面积统计**。

### 3.5 关键图表的文字复原

**(a) 对象视角 vs 场视角示意（讲义第 3、4 页，仅有图）**
- **对象视角图**：一片空白底面上散布着离散符号——几个圆点（点对象，如气象站）、几条折线（线对象，如河流道路）、几块带边界的多边形（面对象，如湖泊地块）。**关键视觉特征：对象之间存在「什么都没有」的空白**。
- **场视角图**：整幅画面被**连续渐变的色带**铺满，没有任何空白，颜色从一端平滑过渡到另一端（如高程从低到高、温度从冷到暖）。**关键视觉特征：任取一点都能读出一个值**。

**(b) DTM 显示（讲义第 6 页）**
灰度渲染的地形影像，讲义唯一的文字说明是 **"Light = high elevations, Dark = low elevations"（亮 = 高程高，暗 = 高程低）**。这是最基础的**连续型分级设色（stretched symbology）**。

**(c) Hillshade（山体阴影，讲义第 7 页）**
📎 复原说明（该页无文字层，仅有标题）：山体阴影是模拟一个虚拟光源照射 DEM 后计算出的明暗图，**ArcGIS Pro 默认光源方位角（azimuth）315°（西北）、高度角（altitude）45°**。西北方向打光是制图惯例，因为人眼在其他方位光下容易产生**地形反转错觉（relief inversion）**——把山谷看成山脊。W07 地形分析会正式讲。

**(d) Draping layers on a 3D surface（讲义第 10、11 页，标题重复两次，无文字）**
📎 复原说明：把二维图层（航片、地质图、土地利用图）**贴敷（drape）**到 DEM 表面上显示，得到「地形起伏 + 专题内容」的三维视图。ArcGIS Pro 中通过 **Scene（场景）视图**实现，把 DEM 设为 Ground/Elevation Surface，其余图层设为 draped。**W09 三维技术会展开。**

**(e) TIN 结构示意（讲义第 12、13 页）**
一片由**大小不一的三角形**无缝拼成的表面；平坦区三角形大而稀疏，陡峭破碎区三角形小而密集。每个三角形顶点是一个实测高程点 (x, y, z)，三角形内部按平面插值 → 因此**每个三角面梯度恒定**，整个表面是分片平面的、在三角形边界处一阶不连续。

**(f) 投影族示意（讲义第 21 页）**
三个并列图形：**cylindrical（圆柱）**——一张纸卷成筒套在地球外；**conic（圆锥）**——一个圆锥帽扣在地球上；**azimuthal（方位）**——一张平面纸贴在地球某一点上。三者的共同点：都是把球面投到一个**可展曲面（developable surface）**上再展平。

**(g) 割圆柱墨卡托的变形分布（讲义第 23 页）**
沿纬度方向从赤道向两极，变形呈 **递增 → 零 → 递增 → 零 → 递增** 的模式（讲义原文文字）：**两条标准纬线（standard parallels，即割线与球面相交处）上无变形**，其间与其外变形都递增。对比**切（tangent）**投影只有一条无变形线（正轴时为赤道）。

**(h) 不同像元尺寸的栅格对比（讲义第 30 页）**
同一景物用逐渐增大的像元表示，从清晰可辨的形状退化为粗糙的方块马赛克，细小地物完全消失。文字：**Increasing cell size = lower resolution and loss of detail**。

**(i) 📎 补充：矢量 vs 栅格格式对照表（讲义未给，但反复用到）**

| 对比项 | **Vector（矢量）** | **Raster（栅格）** |
|---|---|---|
| 概念基础 | Object view | Field view |
| 基本单元 | point / line / polygon（顶点坐标） | cell / pixel（行列 + 值） |
| 适合表达 | 离散、有明确边界的实体 | 连续变化的场 |
| 属性 | 每个要素可挂**任意多个字段** | 每个像元**一个值/波段**（可用属性表挂类别） |
| 精度 | 与坐标位数有关，可任意精细 | 受**像元尺寸**硬性限制 |
| 存储 | 复杂形状体积小；极复杂边界体积大 | 与范围/分辨率的平方成正比 |
| 常见分析 | 缓冲、叠加、网络、选择查询 | 代数运算、邻域统计、坡度坡向、重分类 |
| 缩放表现 | 无级放大不失真 | 放大出现方块 |
| 典型格式 | shapefile、geodatabase feature class | GeoTIFF、IMG、geodatabase raster dataset |
| 本周实例 | OS Open Rivers、OS OpenMap Local Buildings、rivers_buffer100 | World Topographic Map / World Hillshade 底图 |

---

## 四、课堂补充

> **⚠️ 本周没有 transcript（课堂录音转写）。本课的 transcript 从 Week 4（23-Feb）才开始，W01–W03 均无。** 因此本节内容全部来自**讲义**与**实操教程**本身透露的要求、规范与评分线索，不含任何课堂口头补充。

### 4.1 关于本周讲义的可靠性与 OCR 质量（重要）

本周讲义的 md 文件由 PDF 转换而来，**质量分为三档**，复习时需区别对待：

**① 有完整文字层、可靠**：第 1–5 页（学习目标、空间数据性质、object/field view、DEM/DTM 定义）、第 12 页（TIN）、第 14–16 页（map scale、generalisation）、第 17–19 页（geoid/spheroid/datum）、第 21–24 页（投影）、第 26 页（vector/feature class）、第 29–30 页（raster 要素与像元尺寸）、第 31 页（作业与资源）。**这些是本周的实质内容，可放心背。**

**② 只有标题、无正文（原页面基本是图片，没有可提取的文字）**：
- 第 6 页 Digital Terrain Model（仅有一行 "Light = high elevations, Dark = low elevations"）
- 第 7 页 Topography (hillshade) — **仅标题**
- 第 8 页 Relief and topography — **仅标题**
- 第 9 页 3D visualisation — **仅标题**
- 第 10、11 页 Draping layers on a 3D surface — **仅标题，且标题重复两次**
- 第 13 页 DEM using TIN — **仅标题**
- 第 20 页 Geographic coordinate system — 仅有 Parallels / Prime meridian / Meridians 三个标注词
- 第 25 页 Universal Transverse Mercator (UTM) system — **仅标题**
- 第 27 页 Vector data model coordinates — **仅标题**
- 第 28 页 Raster data model is based on field view — **仅标题**

→ **这些页的实质内容全部丢失**，本笔记第三节 3.5 已用 📎 标记的方式做了文字复原，但**复原基于通用 GIS 知识而非原 PPT 图像**，考试时若涉及这些页的具体图例，请务必对照原 PDF。**尤其 UTM 一页（第 25 页）完全空白，而 UTM 是学习目标里明确列出的「projected coordinate systems」的核心实例——这是本周材料最大的知识缺口。**

**③ 低质量 OCR 段（文件末尾「OCR 补充」区块）**：md 文件末尾有一段自动 OCR 的补充，其**开头已自我声明**：*「识别质量低——原件疑为手写或图件，文字大多不可靠，仅作线索，务必对照原件」*。该段实际只挽回了各页标题，唯一有实质数据的是 **Page 13（DEM using TIN）** 的一串坐标轴刻度，且明显有识别错误：

```
498.889 -
MB 433.333 -     ← "MB" 是噪声
MM 367.778 -     ← "MM" 是噪声
302.222 -
236.667 -
Me 7.111 -       ← 应为 171.111（与下方轴刻度序列对照可确认）
105.556 -
40 - 105.556
564.444 / 498.889 / 433,333 / 367.778 / 302.222 / 236.667 / 171.111
```

→ 判读：这是 TIN 高程渲染图的**图例刻度**，等差序列步长约 **65.556**，从 40 到 564.444（推测单位为米）。其中 `433,333` 的逗号应为小数点、`Me 7.111` 应为 `171.111`、`MB`/`MM` 为噪声。**这些数字对理解 TIN 概念毫无作用，可以完全忽略，不必记忆。** 已一并记入勘误表。

### 4.2 讲义明确布置的作业与资源（第 31 页，原文）

- **读课本第 2 章：Spatial Data and Management**（课本为 W01 指定的 Liu & Mason, *Image Processing and GIS for Remote Sensing*；⚠️ 但该书章节名与此不符，实际课本可能另有其书，见勘误表）；
- **在 Canvas 上做 quiz** 检验基本理解（⚠️ 注意 W01 讲义说 quiz 在 **BB**（Blackboard），W02 说在 **Canvas**，平台说法不一致）；
- **进阶资源**：ESRI Training 网络课程 *Introduction to Spatial Data*，并特别注明——**"Read the text, don't attempt the ArcGIS Pro exercises"（只读文字，不要做里面的 ArcGIS Pro 练习）**。

### 4.3 从 W01 讲义带过来的评分权重（本周实习的意义所在）

W01 讲义给出的正式评估（**与官方大纲的 50/50 不同，以讲义为准**）：
- **Canvas 测验 50 题**（暑期考试季）— **70%** — 覆盖 ILO 1、2、3（知识与理解）；
- **ArcGIS Pro 软件项目**（选定案例研究）— **30%** — 覆盖 ILO 4、5（操作能力）— **提交截止：Week 11 结束，2026 年 4 月 30 日**。
- 形成性评估：**每周基于讲义的简答/选择题 quiz** + **每周对 ArcGIS Pro 练习的反馈**。

**→ 推论：本周实习 Carlisle 洪水图的完整流程（在线取数 → 裁范围 → 缓冲 → 按位置选择 → 另存图层 → 符号化 → 布局出图）就是 30% 那个 project 的方法论模板。** 教程结尾的 Challenge Exercise 明确写着 **"to be completed for homework"**，且给出了核对答案（**1726 buildings**），说明这是要交的。

### 4.4 实操教程透露的规范与评分要点

1. **教程要求成图必须包含四类内容**（第 8 节原文）：River line（河流线）、River buffer（河流缓冲区）、The buildings within the buffer（缓冲区内的建筑物）、Background mapping for context（用于提供地理背景的底图）。
2. **Layout 必须包含的制图要素**（第 10 节原文）：**Legend（图例）、Grid Lines（格网线）、North Arrow（指北针）、Title（标题）、Scale Bar（比例尺条）**。教程说 "See if you can produce a similar version to this map"，即以示例图为标准。
3. **图层必须重命名为有意义的名字**：教程明确要求把两个默认名（`… selection selection`）改成 **Flood Risk local buildings** 与 **Flood risk important buildings**。
4. **教程自我承认方法学缺陷**（Challenge Exercise 原文）：*"The main drawback of our analysis is the assumption of the 100m (buffer) flood zone, which does not seem very reasonable for several reasons."*（本分析的主要缺陷是 100 m 缓冲洪泛区这一假设，从几个方面看都不太合理。）
   📎 背景补充：具体不合理在哪里，教程没有列举，但至少有五条——(a) 洪水淹没由**地形与水位**决定，与到河道的**平面距离**无必然关系，河边高地可能安全、远处洼地反而会淹；(b) 用**中心线**而非河岸线，宽河与窄河被同等对待；(c) 100 m 是任意选定的，未对应任何**重现期（return period）**，如 1 in 100 year flood；(d) 忽略了防洪工程（堤防、闸门）；(e) 忽略了城市排水与地表径流造成的**非河道洪水（pluvial flooding）**。**Environment Agency 的 Flood Alert Areas 之所以更合理，正是因为它是基于水文水力模型（含极端洪水轮廓 extreme flood outline）划定的。**
5. **教程的方法论出处**：基于 **Digimap Resource Centre** 的教学资源（`digimap.edina.ac.uk/webhelp/training/gis_exercises/flood_analysis.pdf`），另推荐参考 Esri 的 Carlisle 2015 洪水 **Story Map**（含地图、视频与报告，是「专业级 GIS 成果展示」的范例）。

---

## 五、Practical 要点

> **本节目标：不打开原教程，也能在 ArcGIS Pro 里从头做一遍。**
> 教程本身省略了不少细节（截图代替文字的地方尤其多），凡教程未明写、由本笔记补足的步骤一律用 **📎** 标出——照做时若发现界面与描述不符，优先以 📎 之外的原文步骤为准。

### 5.0 任务概览

| 项 | 内容 |
|---|---|
| **背景** | Carlisle 位于 River Eden 洪泛平原，三条河在市区交汇；2005 年大洪水造成 3 人死亡、逾 1,800 处房产受淹 |
| **要回答的问题** | **How many buildings in Carlisle are at risk of flooding?**（Carlisle 有多少建筑物面临洪水风险？） |
| **方法** | ① 定义一个 **AT RISK area**（风险区）＝ 河流中心线 **100 m 缓冲区**；② 查询有多少建筑物落在该区内 |
| **教程列出的 5 条学习目标** | download map data from ArcGIS On-line（从 ArcGIS Online 下载地图数据）／style map data（数据符号化）／create a buffer（创建缓冲区）／select features by location and save output（按位置选择要素并保存输出）／create an effective presentation map（制作有效的展示地图） |
| **数据需求（教程第 3 节）** | ① Detailed **vector** data showing **buildings**（建筑物矢量数据）② **Vector** data showing **rivers**（河流矢量数据）③ **Raster** map for **background mapping**（背景底图栅格） |
| **最终产出** | 一张带 Legend / Grid Lines / North Arrow / Title / Scale Bar 的 Layout 出图（可导出为 jpg / tiff / png / pdf）+ 两个成果图层 `Flood Risk local buildings`、`Flood risk important buildings` |

**📎 前置准备（教程未写，但没有就开不了工）**：
- 必须有 **Esri 命名用户账号（named user licence）**并**登录 ArcGIS Online 组织门户**（曼大组织名 **Uomanchester**）——不登录就看不到 Portal 里的数据。这一条在 W01 Practical 第 1 节里讲过。
- 建议**新建一个 Project**：ArcGIS Pro 启动页 → **New Project → Map**，命名为如 `Carlisle_Flood`。这样会自动生成 `Carlisle_Flood.gdb` 作为 **Default Geodatabase**，本实习所有 Buffer 输出会自动落在这里。

---

### 5.1 步骤 1 — 从 ArcGIS Online 加载数据（教程第 4 节）

**① OS Open Rivers（英国开放河流数据）**
> OS Open Rivers 是 Ordnance Survey 发布的免费 GIS 数据集，覆盖英国 **超过 144,000 km** 的淡水河流、潮汐河口与运河。

操作路径：
```
Map 选项卡 → Add Data 按钮 → 左侧导航到 Portal → ArcGIS Online
→ 搜索框输入 "OS Open Rivers" → 选中结果 → OK
```

**② OS OpenMap Local Buildings（建筑物矢量数据）**
```
同上：Map → Add Data → Portal → ArcGIS Online
→ 搜索 "OS OpenMap Local Buildings" → 添加到地图
```

**📎 关键提示（教程未明说，但后面步骤依赖它）**：OS OpenMap Local Buildings 加进来后在 Contents pane 里是一个**组图层（group layer）**，内含**两个子图层**——**OS OpenMap Local Buildings**（一般建筑）与 **OS OpenMap Important Buildings**（重要建筑，如学校、医院、公共设施）。教程第 5 节说「do the same for the OS OpenMap LocalBuildings **group** to create **two** new layers（对该组做同样操作，创建两个新图层）」，第 7 节又直接引用了这两个名字——**如果不知道它是个组图层，后面会找不到「Important Buildings」在哪。**

**📎 底图**：ArcGIS Pro 新建 Map 时默认已加载 **World Topographic Map** 底图（W01 Practical 说明过），它就是数据需求里的第③项「Raster map for background mapping」，无需另行添加。

---

### 5.2 步骤 2 — 裁出研究区（教程第 5 节）

**问题**：河流与建筑物图层覆盖**整个英国**，绘制极慢。教程原话：*"Our map will draw faster with a smaller area."*

**① 定位到 Carlisle**
```
Map 选项卡 → Locate（定位）→ 搜索框输入 "Carlisle" → 回车
```
Map View 随即以 Carlisle 为中心。此时应能看到河流、建筑物与 World Topographic Map 三者叠加。

**② 用矩形框选**
```
Map 选项卡 → Select（选择）下拉 → Select by Rectangle（按矩形选择）
→ 在地图窗口中拖拽出一个覆盖 Carlisle 的矩形
```
框内所有要素高亮为**蓝色**。

**③ 查看各图层被选中的要素数**
```
Contents pane 顶部 → 切换到 List By Selection（按选择列出）
```
可看到 **OS Open Rivers** 与 **OS OpenMap Local Buildings** 各被选中多少要素。

**④ 把选择结果固化为新图层**
```
右键 OS Open Rivers → Selection → Make Layer From Selected Features
```
```
Contents pane → 切回 List By Drawing Order（按绘制顺序列出）
```
出现新图层 **OS Open Rivers selection**。此时可**取消勾选原始的 OS Open Rivers 图层**。

**⑤ 对建筑物组图层重复同样操作**，得到**两个**新图层（一般建筑 + 重要建筑的 selection 图层）。

**⑥ 清除选择集**
```
Map 选项卡 → Selection 组 → Clear（清除）
```

**📎 概念澄清（很重要）**：**Make Layer From Selected Features 创建的是一个「图层」而非一份新数据**——它只是对原数据源加了一个**定义查询（definition query）**式的过滤视图，数据仍在 ArcGIS Online 上。它解决了绘图速度问题，但**没有把数据落到本地**。若要真正导出为本地数据，应用：**右键图层 → Data → Export Features**（输出到默认 gdb 中的一个新 feature class）。教程用的是前者。

---

### 5.3 步骤 3 — 给地图命名（教程第 6 节）

```
Contents pane 中选中 Map（最顶层节点）→ 右键 Properties → General 页签
→ Name 框中输入 "Carlisle Flood Map" → OK
```

**📎 为什么这步不是可有可无的**：后面第 10 节插入 Map Frame 时要**按名字**选择地图（"Insert a New Map Frame selecting the Map of Carlisle you have created"）；如果所有地图都叫 "Map"，布局阶段就会插错。这也是数据管理里「命名要自解释」原则的直接体现。

---

### 5.4 步骤 4 — 建立 100 m 缓冲区（教程第 7 节，Buffer the river centreline）

**假设**：*"any property within 100m of the river will be considered 'AT RISK' from flooding"*（任何在河流 100 m 以内的房产被视为「有风险」）。用**河流中心线**建 100 m 缓冲。

**工具路径**：
```
Analysis 选项卡 → Tools 组 → Buffer
（教程注：也可在 Tool Pane / Geoprocessing 窗格里搜到）
```

**参数设置**：

| 参数（英文原名） | 设定值 | 说明 |
|---|---|---|
| **Input Features** | `OS Open Rivers selection` | 上一步固化的 Carlisle 河流图层 |
| **Output Feature Class** | `rivers_buffer100` | 教程原文 "Name it rivers_buffer100"；📎 输出会写入 Project 的默认 gdb |
| **Distance [value or field]** | **100** | 选 **Linear unit** 模式 |
| 单位 | **Meters** | ⚠️ 必须显式选 Meters，不要留在默认的 Unknown/Decimal Degrees |
| **Side Type**（📎 教程未提） | 默认 **Full**（两侧） | 线要素两侧都缓冲 |
| **End Type**（📎 教程未提） | 默认 **Round**（圆头） | |
| **Dissolve Type** | 首次运行留默认 **No Dissolve**；教程第 8 节提示可重算时改为 **"Dissolve all output features into a single feature"** | 用于消除多条河缓冲区之间的重叠边线 |

→ 点击 **Run**。新图层加入地图，可看到沿所有河流的缓冲带。

**教程的重要注记**：*"you may see a tool called **Pairwise Buffer**. This has the same functionality as Buffer, just utilises parallel processing to speed up the operation."*（**Pairwise Buffer** 与 Buffer 功能相同，只是用并行处理加速。）
📎 补充：两者有一处实质差异——**Pairwise Buffer 不提供 "Dissolve all output features into a single feature" 之外的全部 dissolve 选项组合**，且行为在重叠处理上与 Buffer 略有不同。做本实习用哪个都可以；若要用教程第 8 节的 dissolve 提示，用 **Buffer** 更稳妥。

---

### 5.5 步骤 5 — 统计缓冲区内的建筑物（教程第 7 节，Calculate the number of buildings in the buffer）

**工具路径**：
```
Map 选项卡 → Selection 组 → Select By Location
```

**参数设置**（教程原文 + 📎 修正）：

| 参数 | 教程给的值 | 说明 |
|---|---|---|
| **Input Features** | `OS OpenMap Local Buildings selection` **和** `OS OpenMap Important Buildings selection` | 可同时选两个输入图层 |
| **Relationship**（教程误写为 "Selection Features"） | **Intersect（相交）** | ⚠️ 见勘误表 |
| **Selecting Features** | `rivers_buffer100` | 教程原文：*"this is our outline feature - we want to see what is within it"*（这是我们的轮廓要素，我们想看什么在它里面） |
| **Selection Type** | 教程写 **"Select subset from the current selection"** | ⚠️ **此处教程有逻辑矛盾**——上一步刚执行过 **Clear**，当前没有任何选择集，"从当前选择集中选子集" 会选不到东西。**📎 应改用 "New selection（新建选择）"。** 见勘误表 |
| 执行 | 教程写 "Press **OK**" | 📎 ArcGIS Pro 的地理处理工具窗格里按钮是 **Run**；只有旧式对话框才是 OK |

**查看结果**：
```
Contents pane → 切到 List by Selection
```
教程给的参考答案：**1120 local buildings** 与 **18 important local buildings** 被选中。
> 教程明确提示：**"NOTE: you may have a slightly different number depending on the area you selection."**（你的数字可能略有不同，取决于你框选的范围。）——**这就是本方法「不可复现」的直接证据**，见第六节。

**把结果固化为成果图层**：
```
右键 OS OpenMap Local Buildings selection → Selection → Make Layer From Selected Features
右键 OS OpenMap Local Important Buildings（同样操作）
```
```
Contents pane → 切回 List by Drawing Order
→ 把两个默认名（"… selection selection"）分别重命名为：
   Flood Risk local buildings
   Flood risk important buildings
```
📎 重命名方法：在 Contents pane 中**慢双击**图层名，或右键 → **Properties → General → Name**。

最后再次 **Clear** 清除选择集。

---

### 5.6 步骤 6 — 制作展示级地图（教程第 8 节）

**地图必须显示的四类内容**（教程原文）：
1. River line（河流线）
2. River buffer（河流缓冲区）
3. The buildings within the buffer（缓冲区内的建筑物）
4. Background mapping for context（提供背景的底图）

**操作**：
- **调整绘制顺序**：教程注 —— *"you can change the order layers are drawn by dragging them up and down the Contents pane"*（在 Contents pane 里上下拖动图层即可改变绘制顺序）。
  📎 合理的从上到下顺序：`Flood risk important buildings` → `Flood Risk local buildings` → `OS Open Rivers selection` → `rivers_buffer100`（半透明）→ 底图。**点/小面在上、大面在下**，否则会被压住。
- **设定比例尺**：**Zoom to a scale of 1:10000**（📎 在 Map View 底部的 **Scale** 组合框中直接输入 `1:10,000`）。
- **只勾选需要的图层**：*"Uncheck everything else in the Table of Contents."*（其余全部取消勾选。）
- **去除缓冲区重叠**：*"to remove the overlapping regions in the river buffer you can recalculate it selecting **Dissolve all output features into a single feature**"*（重新跑一次 Buffer，Dissolve Type 选此项）。

**Styling（符号化，教程第 8 节）**：
```
选中 OS Open Rivers selection 图层
→ 功能区出现 Feature Layer 上下文选项卡组 → Labeling（标注）选项卡 → 点击 Label（标注）按钮
```
- 标注所用的字段由 **Field** 下拉框决定（📎 对 OS Open Rivers 通常选 `name1` 之类的河名字段）；
- 正确设置后应能在图上看到 **River Eden** 的标注；
- 教程原话：*"To change the size, play around with the options in the Labeling tab. Also play around with the colours to improve the appearance."*（在 Labeling 选项卡里调整字号，并调整颜色以改善观感。）

**📎 符号（Symbology）设置建议（教程完全没写具体配色，此处为补充）**：
```
右键图层 → Symbology（或 Feature Layer 选项卡 → Symbology）
```
- `rivers_buffer100`：面填充设为**半透明**（如 40–50% transparency，通过 **Appearance 选项卡 → Transparency** 设定），浅蓝或浅黄，配一条细边框；
- `OS Open Rivers selection`：蓝色线，线宽 1–1.5 pt；
- `Flood Risk local buildings`：**红色**填充（呼应 W01 讲义那句 "Buildings in red are in 100m buffer zone of rivers"）；
- `Flood risk important buildings`：更醒目的颜色（如深红/洋红）或加轮廓，以与一般建筑区分；
- 未受影响的建筑若显示，用灰色。

---

### 5.7 步骤 7 — 导出地图（教程第 9 节）

教程只有一句：*"You can export your map in various formats, including image formats (jpg/tiff/png) or a pdf."*

**📎 具体路径（教程未给）**：
```
Share 选项卡 → Export 组 → Map（在 Map view 下）或 Layout（在 Layout view 下）
→ 选择 File Type（PDF / PNG / JPEG / TIFF …）
→ 设定 Resolution（DPI，出图建议 ≥ 300）
→ 指定 Name（输出路径与文件名）→ Export
```
📎 PDF 导出可勾选 **Export Georeference Information**（导出地理参考信息），生成 **GeoPDF**。

---

### 5.8 步骤 8 — 创建 Layout 排版（教程第 10 节）

**① 复位面板**
```
View 选项卡 → Windows 组 → Reset Panes → Reset Panes for Mapping (Default)
```
教程说明：这样能确保 **Contents pane 与 Catalog pane 打开、其他面板关闭**。

**② 理解两种视图**
教程原文：ArcGIS Pro 有 **Map** 与 **Layout** 两种视图；**要生成可打印的地图，必须切换到 Layout 视图**。
📎 区别：**Map view** 是数据工作区（用于分析），**Layout view** 是版面工作区（用于出图，以纸张为单位，可放置多个 map frame 及图廓要素）。

**③ 新建布局**
```
Insert 选项卡 → New Layout → 选择页面尺寸与方向（page size and orientation）
```
📎 按 3.1 节的估算，Carlisle 市区在 1:10,000 下约需 **A2**；若只做市中心，A3 横向（Landscape）通常够用。

**④ 插入地图框**
```
Insert 选项卡 → Map Frame → 从下拉列表中选择你创建的 "Carlisle Flood Map"
→ 在页面上拖出一个大小合适的矩形
```

**⑤ 在 Layout 里导航**
教程原话：*"To pan and zoom your map you need to use the **Activate** button"*（要平移缩放地图内容，必须先用 **Activate**（激活）按钮进入 map frame 内部）。
📎 具体：选中 map frame → **Layout 选项卡 → Map 组 → Activate**；调整完毕后点击 Layout 视图左上角的 **返回箭头 / Close Activation** 退出激活状态。**不激活直接拖动，移动的是整个框而不是框内地图。**

**⑥ 添加制图要素**
教程原文：*"In Layout view a **Legend, Grid Lines, North Arrow, Title** and **Scale Bar** can all be added to your map."*

📎 各自的路径（教程只列了名字，未给路径）：
```
Insert 选项卡 → Map Surrounds 组 → Legend（图例）
Insert 选项卡 → Map Surrounds 组 → North Arrow（指北针）
Insert 选项卡 → Map Surrounds 组 → Scale Bar（比例尺条）
Insert 选项卡 → Graphics and Text 组 → Text（标题，通常用 Rectangle Text 或 Straight Text）
Grid Lines（格网/经纬网）：选中 Map Frame → Insert 选项卡 → Map Frames 组 → Grid
   → 选择 Graticule（经纬网，度分秒）或 Measured Grid（投影坐标格网，米）
```
📎 **Legend 的内容取决于 Contents pane 中勾选的图层与图层名**——这就是前面必须把图层重命名为 `Flood Risk local buildings` 的实际原因：**图层名会原样出现在图例里**。

📎 **不要忘了署名**（第 2.11 F 节）：用 Text 元素加上 *Contains OS data © Crown copyright and database right 2026*、数据来源、坐标系、制图者与日期。

**⑦ 目标**：教程给了一张示例成图，要求 *"See if you can produce a similar version to this map"*。

**参考资源**：Esri 培训课程 *Creating a Map Layout*（教程第 11 节给出链接）。

---

### 5.9 步骤 9 — Challenge Exercise（作业，教程第 12 节）

**背景**：Environment Agency（英国环境署）对 **Flood Alert Areas（洪水预警区）**的定义（教程引原文）：
> *"a large expanse of floodplain (up to and including the extreme flood outline which defines the Flood Warning Service Limit), within a catchment, sub-catchment or group of catchments, that is/are at risk from low impact flooding (from main rivers, ordinary watercourses and the sea)."*
> （一片广阔的洪泛平原——上至并包括界定洪水预警服务界限的**极端洪水轮廓**——位于某个流域、子流域或流域群内，面临低影响洪水风险（来自主河道、普通水道及海洋）。）

**任务**：用真实的 Flood Alert Areas 数据替代那个人为假定的 100 m 缓冲区，重做统计。

**操作步骤**：
```
① Add Data 按钮旁的小下拉箭头 → Add Data from ArcGIS Online
② 搜索 "UK flood alert" → 选择 Environment Agency: Flood Alert Areas → OK
   → Flood Alert 区域出现在 Carlisle 一带；教程注明「A new shape file has been added as a layer」
③ 该图层覆盖全英国 → 用 5.2 节同样的方法（Select by Rectangle → Make Layer From
   Selected Features）裁到 Carlisle 范围
④ 重复 5.5 节的 Select By Location 流程，
   **hint（教程原文）：把 EA_Flood_Alert_Areas 当作你的 buffer（即 Selecting Features）**
⑤ Make Layer From Selected Features，得到新的成果图层
```
**教程给出的核对答案：1726 buildings**（对比 100 m 缓冲法的 1120 栋——**真实洪泛区内的建筑物比简易缓冲法多出约 54%**，说明 100 m 缓冲严重低估了风险）。

---

### 5.10 完整流程速查（一页流水线）

```
[登录 ArcGIS Online (Uomanchester)] → [New Project → Map]
   ↓
① Map → Add Data → Portal → ArcGIS Online → "OS Open Rivers"        → 加载
② Map → Add Data → Portal → ArcGIS Online → "OS OpenMap Local Buildings" → 加载（组图层，含 2 子层）
   ↓
③ Map → Locate → "Carlisle"
④ Map → Select → Select by Rectangle → 框出 Carlisle
⑤ Contents → List By Selection → 查看各层选中数
⑥ 右键各层 → Selection → Make Layer From Selected Features   （得到 3 个 …selection 图层）
⑦ Map → Selection → Clear
   ↓
⑧ 右键 Map → Properties → General → Name = "Carlisle Flood Map"
   ↓
⑨ Analysis → Buffer
      Input Features       = OS Open Rivers selection
      Output               = rivers_buffer100
      Distance             = 100  Meters
      Dissolve Type        = No Dissolve（出图时可改 Dissolve all…）
   → Run
   ↓
⑩ Map → Select By Location
      Input Features    = 两个 buildings selection 图层
      Relationship      = Intersect
      Selecting Features= rivers_buffer100
      Selection Type    = New selection  ← 📎（教程写的 "Select subset…" 有误）
   → Run          【参考值：1120 local + 18 important】
   ↓
⑪ 右键 → Make Layer From Selected Features ×2
   → 重命名为 "Flood Risk local buildings" / "Flood risk important buildings"
   → Clear
   ↓
⑫ 设 Scale = 1:10,000；勾选需要的 4 类图层；符号化（Symbology / Transparency）
⑬ Feature Layer → Labeling → Label（标注河名，Field 选河名字段）
   ↓
⑭ View → Reset Panes → Reset Panes for Mapping (Default)
⑮ Insert → New Layout → 选页面尺寸方向
⑯ Insert → Map Frame → "Carlisle Flood Map" → 拖出矩形
⑰ Layout → Activate → 调整框内视图 → 退出激活
⑱ Insert → Legend / North Arrow / Scale Bar / Text(Title) / Grid
   ↓
⑲ Share → Export → Layout → PDF/PNG，DPI ≥ 300
   ↓
⑳【作业】加载 Environment Agency: Flood Alert Areas，重复 ③–⑪  【参考值：1726 buildings】
```

---

## 六、易错点 / 重点难点

### 概念类

1. **大比例尺 / 小比例尺记反。** 记住分数：1/40,000 > 1/3,000,000，所以 **1:40,000 是大比例尺（细节多、范围小）**。讲义 "Smaller the map scale, the larger the ratio" 那句话说的是**冒号后的数字**，别按字面理解成「比值更大」。

2. **DEM / DTM / DSM 三者定义在不同教材中不一致。** 讲义的说法（DEM = 裸地；DTM = DEM + 坡度曲率水系）与业界主流（DTM = 裸地；DSM = 含地物）**相反**。答本课的题以讲义为准，读文献时看作者怎么定义。

3. **Object view ≠ vector 格式，Field view ≠ raster 格式。** 视角是**概念层面**的选择，数据模型是**表示层面**的选择。连续的高程场可以存成栅格 DEM，也可以存成矢量的 TIN 或等高线——**TIN 是「场视角 + 矢量结构」的反例**，最容易被忽略。

4. **像元深度：2ⁿ 是灰阶数，2ⁿ−1 是最大值。** 8-bit = 256 阶、0–255。讲义把两者混写了。

5. **geoid ≠ spheroid ≠ datum。** geoid 是重力等位面（起伏不规则，≈ 平均海平面）；spheroid/ellipsoid 是拟合 geoid 的光滑数学面；datum 是把某个 spheroid **固定到地球上**（定义原点与定向）的完整定义。**坐标数值由 datum 决定，改 datum 就改数值。**

6. **投影不可能同时保角、保积、保距。** 做面积统计（如"洪泛区面积"）必须用**等积投影**，用 Mercator/Web Mercator 算面积在高纬会显著偏大。

### 数据管理类

7. **Shapefile 的字段名 ≤ 10 字符。** 把 geodatabase feature class 导出为 shapefile 时，`Building_Height_m` 会被截断成 `Building_H`；若有多个同前缀字段还会被自动改名为 `Buildin_1`、`Buildin_2`——**属性含义就此丢失**。同时 shapefile **不支持 NULL**（数值 NULL 变 0，会污染统计），也不保存字段别名。**结论：分析中间过程一律用 geodatabase，只在必须交换数据时才导出 shapefile。**

8. **Shapefile 是「一组文件」不是一个文件。** 只复制 `.shp` 而漏掉 `.dbf`/`.shx`/`.prj` 会导致数据不可用或**丢失坐标系定义**（丢 `.prj` 后 ArcGIS 会当作 Unknown Coordinate System 处理，图层跑到地球另一侧）。

9. **坐标系不匹配 → 图层错位。** 两种情形要分清：
   - **Define Projection（定义投影）**：数据的坐标系**标错或缺失**，需要用正确的坐标系去「贴标签」——**不改坐标数值**；
   - **Project（投影/转换）**：数据坐标系是对的，但要**转换到另一个坐标系**——**改坐标数值**。
   **用错这两个工具是新手最常见的灾难**：对一份 OSGB36 数据错误地 Define Projection 为 WGS84，坐标数值不变但被解释错，图层会偏到几百公里外。

10. **⚠️ 本周实习的隐藏坑：缓冲距离与地图坐标系。** 教程全程未设置坐标系。若地图处于 **Web Mercator（EPSG:3857）**，其比例因子随纬度按 1/cos φ 增大；Carlisle 约 **54.9°N**，1/cos(54.9°) ≈ **1.74**。此时"100 Meters"的缓冲若在地图投影坐标系下按平面计算，实际地面宽度会被系统性放大。
    **📎 防范做法**：在 Buffer 前把 Map 的坐标系显式设为 **British National Grid（EPSG:27700）**——右键 **Map → Properties → Coordinate Systems → 搜索 "British National Grid"**。（现代版本的 ArcGIS Pro Buffer 工具在很多情况下会自动做测地线/大地测量计算 **Method = Geodesic**，但**不要依赖默认行为**，显式设定坐标系才安全。）

11. **Select By Location 的 Selection Type 用错。** 教程写 "Select subset from the current selection"，但上一步刚 **Clear** 过选择集——**没有当前选择就没有子集可选**。应用 **New selection**。**这是本周实习最容易卡住的一步：按教程做会得到 0 个结果，然后不知道错在哪。**

12. **栅格与矢量混用时的分辨率与 extent 不匹配。** 做栅格叠加/代数运算前必须统一三件事：**坐标系、像元尺寸（cell size）、范围（extent）与对齐（snap raster）**。在 ArcGIS Pro 中通过 **Environments（环境设置）** 统一指定：`Output Coordinate System`、`Cell Size`、`Extent`、`Snap Raster`、`Mask`。不设的话，工具会按各自默认取值，输出常常「差半个像元」，逐像元比较全错位。

13. **数据路径变动导致断链（broken link）。** `.aprx` 只存引用不存数据。移动文件夹、重命名磁盘、别人的电脑打开——图层前就出现**红色感叹号**。修复：右键图层 → **Properties → Source → Set Data Source**。**根治**：用 **Share → Package Project (.ppkx)** 打包提交。
    **📎 本周实习的特殊风险**：全部数据来自 **ArcGIS Online 在线服务**，不仅路径会断，**服务本身被下线或组织权限变更，项目就永久失效**。若成果要长期保存，务必用 **Export Features** 把关键图层落成本地 feature class。

14. **元数据缺失导致成果无法复现。** 本周实习就是活教材——教程自己承认 *"you may have a slightly different number depending on the area you selection"*（数字会因你框选范围不同而不同）。**因为「用鼠标随手拖的矩形」这个关键参数既没被记录也无法复现**，1120 这个数字就是不可验证的。
    **📎 正确做法**：用一个**明确定义的研究区边界**（如 Carlisle 的行政区划多边形，或写明四至坐标的矩形），并把研究区边界与所有处理参数（缓冲距离、空间关系、数据版本与下载日期）写进元数据。**这条对 30% 的期末 project 直接影响评分。**

15. **Dissolve 与面积统计。** 未 dissolve 的缓冲图层，各段缓冲区在河流交汇处重叠；此时**属性表行数 ≠ 独立区域数**，直接对 Shape_Area 求和会**重复计算重叠部分**。计数建筑物不受影响，但报告"风险区面积"时必须先 dissolve。

16. **方法学本身的局限要能说出来。** 教程明确点名 100 m 缓冲假设不合理。考试或报告中若被问「这个分析的缺陷是什么」，至少答出：**平面距离 ≠ 洪水淹没范围（洪水由地形与水位决定）**、**用中心线忽略河宽**、**100 m 是任意值、不对应任何重现期**、**未考虑防洪工程**、**未考虑非河道洪水**。Challenge Exercise 用 Flood Alert Areas 得到 1726 栋（vs 1120 栋）就是这个缺陷的量化证据。

### 材料使用类

17. **不要用官方大纲复习本课。** 大纲与实际授课严重不符（见文首警告）。

18. **本周讲义有大量「只有标题没有正文」的页**（hillshade、3D visualisation、draping、UTM、vector coordinates、raster data model 等，见 4.1 节清单）。**UTM 一页完全空白但属于明确列出的学习目标**——必须自行补足（本笔记 2.8 已补）。

---

## 七、本周术语表

### A. 空间数据与概念化

| 英文 | 中文 | 要点 |
|---|---|---|
| Spatial data | 空间数据 | 观测性（observational）而非实验性；按 georeferencing system 记录位置 |
| Observational / Experimental | 观测性 / 实验性 | 空间数据无法设定与控制变量、无法重复采集 |
| Conceptualisation | 概念化 | 把真实世界抽象为有限形式的第一步 |
| Representation | 表示 | 概念化结果在计算机中的具体存储方式 |
| Georeferencing system | 地理参照系统 | 坐标数值的意义依赖于它 |
| Object view | 对象视角 | 空间由离散、边界明确、可计数的对象填充 |
| Field view | 场视角 | 空间被连续表面覆盖，每个位置都有属性值 |
| Feature | 要素 | 对象视角下的 point / line / area 实体 |
| Attribute | 属性 | 要素的可观测/可测量特征 |

### B. 表面模型

| 英文 | 中文 | 要点 |
|---|---|---|
| Digital Elevation Model (DEM) | 数字高程模型 | 讲义定义：裸地（bare-earth）高程，不含植被与建筑 |
| Digital Terrain Model (DTM) | 数字地形模型 | 讲义定义：DEM + 坡度/曲率/水系信息；与 DEM 常混用 |
| Digital Surface Model (DSM) | 数字表面模型 | 📎 讲义未提；含植被冠层与建筑顶面 |
| Triangulated Irregular Network (TIN) | 不规则三角网 | 矢量表面模型；连续三角形；每三角形梯度恒定；顶点带 (x,y,z) |
| Vertex / Vertices | 顶点 | TIN 三角形的角点（讲义误拼 "verticies"） |
| Hillshade | 山体阴影 | 模拟光照的地形晕渲；📎 默认 azimuth 315°、altitude 45° |
| Drape | 贴敷 / 叠覆 | 把二维图层贴到三维表面上显示 |
| Breakline | 断裂线 | 📎 TIN 中强制保形的地形结构线（山脊、河道） |

### C. 比例尺与制图综合

| 英文 | 中文 | 要点 |
|---|---|---|
| Map scale | 地图比例尺 | 图上距离 : 地面距离 |
| Large scale | 大比例尺 | 分数值大，范围小，细节多（如 1:10,000） |
| Small scale | 小比例尺 | 分数值小，范围大，细节少（如 1:3,000,000） |
| Representative fraction (RF) | 代表分数 | 📎 比例尺的分数写法 |
| Generalisation / Cartographic abstraction | 制图综合 / 制图抽象 | 把现实转换为地图的过程 |
| Selection | 选取 | 保留最重要的地理要素 |
| Simplification | 简化 | 去除复杂性 |
| Exaggeration | 夸大 | 保留或强调重要特征 |
| Combination | 合并 | 合并相似要素 |
| Displacement | 位移 | 移动对象以保持可区分 |
| Classification | 分类 | 按属性对要素分组 |

### D. 地球形状、基准与投影

| 英文 | 中文 | 要点 |
|---|---|---|
| Geoid | 大地水准面 | 地球重力场等位面 ≈ 平均海平面 |
| Equipotential surface | 等位面 | geoid 的定义性质 |
| Reference spheroid / Ellipsoid | 参考椭球体 | geoid 的光滑数学模型；a − b ≈ 21.4 km |
| Datum | 大地基准面 | 顾及局部差异；**坐标数值取决于所选椭球与 datum** |
| WGS (World Geodetic System) | 世界大地测量系统 | 全球基准；📎 WGS 84 = EPSG:4326 |
| GRS 1980 (Geodetic Reference System) | 大地参考系统 1980 | 📎 ETRS89 所用椭球 |
| OSGB 1936 / British National Grid | 英国 1936 基准 / 英国国家格网 | 📎 EPSG:27700；OS 数据原生坐标系 |
| Web Mercator | 网络墨卡托 | 📎 EPSG:3857；ArcGIS Online 底图默认 |
| Geographic coordinate system (GCS) | 地理坐标系 | 用经纬度在椭球面上定位 |
| Projected coordinate system (PCS) | 投影坐标系 | 📎 平面直角坐标，单位为米/英尺 |
| Parallel | 纬线 / 纬圈 | |
| Meridian | 经线 / 子午线 | |
| Prime meridian | 本初子午线 | |
| Map projection | 地图投影 | 球面 → 平面的数学变换 |
| Cylindrical / Conic / Azimuthal | 圆柱 / 圆锥 / 方位投影 | 三大可展曲面族 |
| Tangent / Secant | 切 / 割 | 切：1 条标准线；割：2 条标准线 |
| Standard parallel | 标准纬线 | 无变形线 |
| Mercator projection | 墨卡托投影 | 保形状与方向；变形面积与距离（赤道除外） |
| Universal Transverse Mercator (UTM) | 通用横轴墨卡托 | 📎 60 个 6° 带；中央经线比例因子 0.9996 |
| Conformal / Equal-area / Equidistant | 等角 / 等积 / 等距 | 📎 投影的三类性质，不可兼得 |
| Distortion | 变形 | 面积、形状、距离、方向的失真 |

### E. 数据模型与格式

| 英文 | 中文 | 要点 |
|---|---|---|
| Vector data model | 矢量数据模型 | 基于 object view |
| Raster data model | 栅格数据模型 | 基于 field view |
| Feature class | 要素类 | 相同几何类型 + 相同属性字段集 的要素集合 |
| Point / Line / Polygon | 点 / 线 / 面 | 三种矢量几何类型 |
| Cell / Pixel | 像元 / 像素 | 栅格基本单元 |
| Cell size | 像元尺寸 | 决定空间分辨率；增大 = 分辨率降低、细节丢失 |
| Cell / pixel depth (bit depth) | 像元深度 / 位深 | 8-bit 灰度 = 256 阶（0–255）；8-bit×RGB ≈ 1670 万色 |
| Band | 波段 | 📎 栅格的通道数 |
| NoData | 无数据值 | 📎 表示该像元无有效值 |
| Extent | 范围 | 📎 数据的四至边界 |
| Shapefile | Shapefile | 📎 多文件格式；字段名 ≤ 10 字符；≤ 2 GB；不支持 NULL |
| File geodatabase (.gdb) | 文件地理数据库 | 📎 Esri 原生；支持长字段名、NULL、域、拓扑 |
| Feature dataset | 要素数据集 | 📎 gdb 内的容器，强制共享同一坐标系 |
| Raster dataset | 栅格数据集 | 📎 gdb 内存储的栅格 |
| Table | 表 | 📎 无几何的属性表 |
| GeoTIFF | GeoTIFF | 📎 带地理参考标签的 TIFF；可配 .tfw world file |
| Feature service | 要素服务 | 📎 ArcGIS Online 上的在线数据；本周全部数据来源 |

### F. 数据管理与质量（📎 本节术语讲义均未涉及）

| 英文 | 中文 | 要点 |
|---|---|---|
| Metadata | 元数据 | 描述数据的数据；来源、时间、精度、谱系、许可 |
| Lineage | 谱系 | 数据的来源与全部处理历史 |
| Accuracy | 准确度 | 与真值的接近程度（系统偏差） |
| Precision | 精密度 | 重复测量的一致性 / 记录位数 |
| Resolution | 分辨率 | 可分辨的最小单元 |
| Completeness | 完整性 | 应有要素是否齐全 |
| Currency / Timeliness | 时效性 | 数据反映的时点 |
| Logical consistency | 逻辑一致性 | 拓扑与属性是否自洽 |
| Broken link | 断链 | 数据源路径失效，图层出现红色感叹号 |
| Open Government Licence (OGL) | 开放政府许可 | OS OpenData 与 EA 数据的许可；**必须署名** |
| Project package (.ppkx) | 项目包 | 把项目与数据一并打包，用于提交与存档 |
| Definition query | 定义查询 | 只显示满足条件的要素，不改动源数据 |

### G. ArcGIS Pro 界面与工具（全部保留英文原名）

| 英文原名 | 中文 | 路径 / 说明 |
|---|---|---|
| Ribbon | 功能区 | 顶部选项卡区；分 core tabs 与 contextual tabs |
| Contents pane | 内容窗格 | 左侧；管理图层。教程有时沿用旧称 "Table of Contents" |
| Catalog pane | 目录窗格 | 右侧；浏览项目与 Portal 内容 |
| Map view / Layout view | 地图视图 / 布局视图 | 前者做分析，后者做出图 |
| Scene | 场景 | 📎 三维视图（W09 用） |
| Add Data | 添加数据 | **Map → Add Data**；下拉可选 Add Data from ArcGIS Online / Add Data to map |
| Portal | 门户 | Catalog 中通往 ArcGIS Online / My Organization 的入口 |
| Locate | 定位 | **Map → Locate**；按地名搜索定位 |
| Select by Rectangle | 按矩形选择 | **Map → Select → Select by Rectangle** |
| List By Selection | 按选择列出 | Contents pane 顶部切换按钮；显示各层选中要素数 |
| List by Drawing Order | 按绘制顺序列出 | Contents pane 顶部切换按钮 |
| Make Layer From Selected Features | 由所选要素创建图层 | 右键图层 → **Selection →** …；创建过滤视图，**不复制数据** |
| Export Features | 导出要素 | 📎 右键图层 → **Data → Export Features**；真正落成新 feature class |
| Clear | 清除（选择集） | **Map → Selection 组 → Clear** |
| Buffer | 缓冲区 | **Analysis → Buffer**；参数 Input Features / Distance / Dissolve Type |
| Pairwise Buffer | 成对缓冲区 | 功能同 Buffer，使用并行处理加速 |
| Dissolve Type | 融合类型 | 选 "Dissolve all output features into a single feature" 可消除重叠 |
| Select By Location | 按位置选择 | **Map → Selection 组 → Select By Location**；参数 Input Features / **Relationship** / Selecting Features / Selection Type |
| Intersect | 相交 | Select By Location 的空间关系（Relationship）之一 |
| New selection / Add to / Remove from / Select subset from the current selection | 新建选择 / 添加到 / 从中移除 / 从当前选择中选子集 | Selection Type 的四个选项 |
| Symbology | 符号系统 | 右键图层 → Symbology；设置颜色、填充、分级 |
| Transparency | 透明度 | 📎 **Appearance 选项卡 → Transparency** |
| Labeling / Label / Field | 标注 / 标注开关 / 标注字段 | **Feature Layer → Labeling 选项卡 → Label**；Field 决定标注内容 |
| Feature Layer (contextual tab) | 要素图层上下文选项卡 | 选中图层后自动出现 |
| Properties → General → Name | 属性 → 常规 → 名称 | 用于重命名 Map 与 Layer |
| Reset Panes for Mapping (Default) | 重置为制图默认面板 | **View → Windows → Reset Panes** |
| New Layout | 新建布局 | **Insert → New Layout**；选页面尺寸与方向 |
| Map Frame | 地图框 | **Insert → Map Frame**；选择要放入的 Map |
| Activate | 激活 | Layout 中进入 map frame 内部平移缩放 |
| Legend / North Arrow / Scale Bar / Title / Grid Lines | 图例 / 指北针 / 比例尺条 / 标题 / 格网线 | **Insert → Map Surrounds / Graphics and Text / Grid** |
| Graticule / Measured Grid | 经纬网 / 投影格网 | 📎 Grid 的两种类型 |
| Export Map / Export Layout | 导出地图 / 导出布局 | 📎 **Share → Export**；jpg / tiff / png / pdf |
| Set Data Source / Repair Data Source | 设置数据源 / 修复数据源 | 📎 修复断链 |
| Environments | 环境设置 | 📎 地理处理工具窗格顶部；统一 Cell Size / Extent / Snap Raster / Output Coordinate System |
| Define Projection | 定义投影 | 📎 修正坐标系标签，**不改坐标值** |
| Project (tool) | 投影（工具） | 📎 转换到另一坐标系，**改坐标值** |

### H. 本周数据集与机构

| 英文 | 中文 | 说明 |
|---|---|---|
| Ordnance Survey (OS) | 英国陆地测量局 | 英国国家测绘机构 |
| OS Open Rivers | OS 开放河流数据 | 免费；覆盖英国 >144,000 km 河流、潮汐河口与运河；线要素 |
| OS OpenMap Local | OS 本地开放地图 | 含 Buildings 与 Important Buildings 两类建筑面要素 |
| Environment Agency (EA) | 英国环境署 | 洪水风险主管机构 |
| Flood Alert Area | 洪水预警区 | 基于流域与极端洪水轮廓划定的洪泛区 |
| Extreme flood outline | 极端洪水轮廓 | 界定 Flood Warning Service Limit 的边界 |
| Flood Warning Service Limit | 洪水预警服务界限 | |
| Digimap / EDINA | Digimap 数据服务 | 本实习教学资源出处 |
| ArcGIS Online | ArcGIS 在线平台 | 云端数据与服务共享平台 |
| Story Map | 故事地图 | Esri 的图文并茂成果展示形式；Carlisle 2015 洪水有专业范例 |
| River Eden | 伊登河 | Carlisle 所在的主河 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| Lecture 2，"Elements of a raster"（第 29 页） | `greyscale: 8-bit = 2^8 - 1 = 0-255 shades` | **把灰阶数量与最大值混为一谈**。2⁸ − 1 = 255 是**最大灰度值**，不是灰阶**数量** | 应为：8-bit 有 **2⁸ = 256** 个灰阶，取值范围 **0–255**。写成 "256 shades (values 0–255)" 才正确 |
| Lecture 2，"Map scale"（第 14 页） | `Smaller the map scale: ➢ the larger the ratio ➢ less accurate` | ① "larger the ratio" 措辞含糊——按**代表分数（RF）**看，小比例尺的比值恰恰**更小**（1/3,000,000 < 1/40,000）；原意应指冒号后的**分母数字更大**。② "less accurate"（精度更低）用词不当 | ① 建议表述为 "the larger the **denominator** / the smaller the representative fraction"。② 应为 **"less detailed / more generalised"**（细节更少、综合程度更高）——小比例尺地图上要素位置仍可正确，只是被简化与位移 |
| Lecture 2，"Surface Models: DEM and DTM"（第 5 页） | DEM = 'bare-earth'；DTM = DEM 加上 slope / curvature / drainage structure | **与业界主流约定相反**。通行做法是 **DTM/DEM = 裸地**、**DSM（Digital Surface Model）= 含植被与建筑**；讲义完全未提 DSM | 非硬性错误（讲义自己注明两者常混用），但属**术语分歧**，需知晓。作答本课以讲义为准；读文献须看作者定义 |
| Lecture 2，"Triangulated irregular network (TIN)"（第 12 页） | `Each point in TIN has 3D coordinates (x,y,z) as verticies (nodes).` | 拼写错误 | `verticies` → **`vertices`** |
| Lecture 2，"Triangulated irregular network (TIN)"（第 12 页） | `OS Terrain 5m TIN – triangulated irregular networks uses triangles which relate to features more accurately than a grid.` | **存疑**：Ordnance Survey 的 **OS Terrain 5** 产品实际以 **5 m 格网 DTM + 等高线 + 高程点**形式发布，通常并非以 TIN 交付 | 该页作为"TIN 优于 grid"的示例说法可能不准确；建议以讲义给出的 OS Terrain 5 用户指南链接核对产品形式。概念本身（TIN 可变密度、更贴合地形特征）无误 |
| Lecture 2，"Homework and Resources"（第 31 页） | `Read Chapter 2 of course textbook: Spatial Data and Management` | 官方大纲列出的推荐读物是 Liu & Mason《Image Processing and GIS for Remote Sensing》，**其章节结构与"Chapter 2: Spatial Data and Management"不符** | 实际"course textbook"很可能另有其书（W01 讲义同样只写"course textbook"未给书名）。**需向任课教师确认课本书目**——这直接影响能否找到指定阅读 |
| Lecture 2 第 31 页 vs Lecture 1 第 32 页 | W02 写 `Take the quiz ... (on **Canvas**)`；W01 写 `Take the quiz ... (on **BB**)` | **平台名称前后不一致**（Canvas vs Blackboard） | 两周材料互相矛盾，需确认实际使用哪个学习管理系统 |
| Lecture 2，末尾"OCR 补充" Page 13 | `MB 433.333` / `MM 367.778` / `Me 7.111` / `433,333` | **低质量 OCR 识别错误**：`MB`、`MM`、`Me` 是噪声字符；`Me 7.111` 依等差序列（步长约 65.556）应为 **171.111**；`433,333` 的逗号应为**小数点** | 该段仅为 TIN 高程图例刻度（约 40–564 m），**对理解概念无用，可忽略**。md 文件该段已自我声明"识别质量低……务必对照原件" |
| Lecture 2，多页 | 第 7、8、9、10、11、13、20、25、27、28 页仅有标题，无正文 | **原 PDF 该处无文字层**（页面为图片），转换后实质内容全部丢失 | 影响最大的是 **第 25 页 "Universal Transverse Mercator (UTM) system" 完全空白**，而 UTM 属讲义明列的学习目标。本笔记 2.8 节已用 📎 补足，但需对照原 PDF 核实 |
| Practical 2，第 4 节 OS Open Rivers | `Navigate to Portal the ArcGIS Online.` | 句子残缺/语法错误（PDF 提取或原文笔误） | 应为 `Navigate to **Portal > ArcGIS Online**` |
| Practical 2，第 5 节 | 同一份数据在文中出现三种写法：`OS OpenMap Local Buildings`（第 4 节）、`OS LocalMap Buildings`（第 5 节）、`OS OpenMap LocalBuildings`（第 5 节） | **图层名称前后不一致**，其中 `OS LocalMap Buildings` 明显是把 OpenMap 写反 | 正确名称应统一为 **`OS OpenMap Local Buildings`** |
| Practical 2，第 7 节 Select By Location | `Set **Selection Features** > **Intersect**.` | **参数名错误**。Intersect 是**空间关系**选项，而 ArcGIS Pro 中该参数名为 **Relationship**；"Selecting Features" 是另一个参数（指定用作选择依据的图层，下一行已单独设为 rivers_buffer100） | 应为 **Set `Relationship` > `Intersect`** |
| Practical 2，第 7 节 Select By Location | `Set **Selection Type** > **Select subset from the current selection**.` | **逻辑矛盾**：上一节（第 5 节末）刚执行过 **Clear** 清除全部选择集，此时不存在"current selection"，选此项会得到 **0 个结果** | 应改为 **`New selection`（新建选择）** |
| Practical 2，第 7 节 Select By Location | `Press **OK**.` | ArcGIS Pro 的**地理处理工具窗格**中执行按钮是 **Run**，不是 OK（OK 是旧版 ArcMap 对话框的按钮） | 应为 **Click `Run`** |
| Practical 2，第 7 节 | 输入要素写作 `OS OpenMap Important Buildings selection`，随后又写 `Do the same for **OS OpenMap Local Important Buildings**` | **同一图层两种名称**，且此前第 5 节从未介绍过"Important Buildings"这个子图层从何而来 | 教程遗漏了"OS OpenMap Local Buildings 是一个 **group layer**，内含 Buildings 与 Important Buildings 两个子图层"这一关键说明；名称应统一 |
| Practical 2，第 5 节、第 7 节 | 多处使用 `Table of Contents`（如 "click List By Selection in the Table of Contents"） | **术语过时**：`Table of Contents` 是 **ArcMap** 的叫法；**ArcGIS Pro** 中该面板名为 **Contents pane** | 教程自身也混用（同段又出现 "Contents Pane"）。以 **Contents pane** 为准 |
| Practical 2，第 12 节标题 | `Challenge Exercise (to be completed for **howework**)` | 拼写错误 | `howework` → **`homework`** |
| Practical 2，第 9 节 "Export your map" | 整节仅一句"You can export your map in various formats…"，**未给任何菜单路径** | 步骤缺失，读者无法照做 | 应补 **Share 选项卡 → Export 组 → Map / Layout**。本笔记 5.7 节已用 📎 补足 |
| Practical 2，全篇 | 从第 1 步加载数据到第 9 步 Buffer，**全程未提及任何坐标系设置** | 关键步骤缺失。Buffer 的距离计算依赖地图坐标系；若地图为 Web Mercator，Carlisle（约 54.9°N）处比例因子约 1.74，"100 m" 的实际地面含义会被系统性放大 | 应在 Buffer 前显式设定 Map 坐标系为 **British National Grid（EPSG:27700）**：右键 Map → Properties → Coordinate Systems。本笔记 5.10 / 第六节第 10 条已提示 |
| Practical 2，封面区 | 标题写 `Background information on Carlisle flooding in **2015**`，但正文第 1 节描述的是 **2005** 年洪水（3 人死亡、逾 1800 处房产受淹） | **年份看似矛盾**，但实为两次不同洪灾 | **非错误**：Carlisle 在 2005 年与 2015 年（Storm Desmond 风暴德斯蒙德）各有一次重大洪灾；Story Map 讲的是 2015 年那次，正文举的是 2005 年那次。仅记录以免混淆 |

---

> **本笔记的 📎 标记说明**：凡以 `📎` 开头的段落、表格行或括注，均为**原始材料中没有、由笔记补充**的背景知识（包括 ArcGIS Pro 的具体菜单路径、坐标系代号、参数默认值、格式限制、投影性质分类等）。**未标 📎 的内容均可在讲义或实操教程原文中找到出处。** 由于本周讲义仅 946 词且多页无文字层，补充比例较高，尤其是「2.11 数据管理」整节与「三、公式与图表」的多数算例——复习时请注意区分「考点」与「理解支撑」。
