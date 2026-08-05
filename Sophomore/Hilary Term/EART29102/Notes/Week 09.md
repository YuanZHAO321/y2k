# EART29102 Geospatial Techniques — Week 09 学习笔记

> 授课日：21-Apr（Hilary Term, Week 09）
> 主讲：**Rufus Brunt**（客座，非课程负责人 Ray Burgess；他自称「my one and only appearance for Geospatial」）
> 材料：`Lecture - 3D geospatial techniques`（讲义，32 张 slide）＋ `EART29102 - 21-Apr-transcript`（课堂录音转写）＋ `Practical - 3D geospatial techniques`（ArcGIS Pro 实操教程，10 页）
> 本周主题：**三维地理空间技术（3D geospatial techniques）**

---

## 一、本周主题

### 1.1 本周在全课骨架中的位置

本课程的**实际**骨架（以讲义为准，**不是**官方大纲）：

**基础段** W01 GIS 导论 → W02 空间数据与数据管理 → W03 数据输入与操作
**分析段** W04 空间分析 → W05 空间统计
**专题段** W06 遥感 → W07 地形分析 → W08 空间可视化 → **W09 三维技术**
**收尾** W10 课程回顾

**本周是专题段的收尾，也是全课最后一次新内容。** W10 只做 revision，因此 W09 讲完，这门课的知识面就闭合了。老师本人在开场就点破了这一点：

> "I think this is the last week. Is this your last lecture in Geospatial? Have you got something next week as well? Who knows?"

### 1.2 与前面几周的衔接：从 2.5D 走向真 3D

本周的整条逻辑线是一次**回收与升级**——把前八周学的东西一件件搬进第三维：

| 前面学过的 | 本周怎么升级 |
|---|---|
| W02/W03 的 **datum / projection / CRS**（坐标参考系统） | 追问 **Z 从哪里量**：ellipsoid、geoid、vertical datum |
| W02 的 **raster / vector**、**continuous / discrete** 数据类型 | raster 的 pixel → **voxel（体元）**；两类数据都能建 3D 模型 |
| W04 的 **spatial interpolation（IDW / kriging）** | kriging 从 2D 推广到 **Empirical Bayesian Kriging 3D** |
| W05 的 **semi-variogram、descriptive statistics** | 3D 克里金的半变异函数；mean/median/mode 判读矿体品位分布 |
| **W07 地形分析** 的 DEM / DTM | 明确指出 **DEM 是「表面」不是「体」**——本周最核心的概念界线 |
| **W08 空间可视化** 的符号化、渲染 | 3D 场景导航、voxel 符号化、data filter、isosurface、slice |

老师自己给的衔接原话：

> "most of what you've been doing so far has been in 2D. You might have been thinking some of it's been in three dimensions, but actually you've mainly been working in the 2D realm."

> "We'll recap over things like continuous and discrete raster vector data and things like that. And then we'll go on and have a look at applications for 3D GIS."

**关键的接续点在 W07。** W07 做的是 DEM/DTM 上的坡度、坡向、山影、剖面——那些操作全都发生在「一张被揉皱的纸」上。本周第一件事就是告诉你：**那张纸再怎么揉，它仍然是 2D 的**。真三维的门槛只有一条——**volume（体积）**。

### 1.3 本周的 Intended Learning Outcomes（讲义 Slide 2 原文）

- Ability to **explain what '3D' is in the digital world**（说清数字世界里的「3D」到底指什么）
- **Recap geographical datums** and discuss implications for the **3rd dimension**（回顾大地基准面，讨论其对第三维的影响）
- Exploration of GIS data definitions: **continuous / discrete / raster / vector**
- Application of **2D geostatistical techniques within the 3rd dimension**（把 2D 地统计方法搬进第三维）

> 注意这四条的措辞：**没有一条要求你掌握 Lidar、点云、摄影测量、SfM、TIN、multipatch**。本周的「3D」是**体积数据（volumetric data）+ 3D 地统计插值**这条线，不是测量学那条线。
> 📎 背景补充：任务简报中预设的点云（point cloud / LAS / LAZ）、TIN、multipatch、SfM、InSAR、BIM、skyline analysis、3D buffer 等内容，**本周三份材料一律未涉及**。若考试出现，需另找来源。见 §2.9 的简表（已全部标注为补充内容）。

### 1.4 本周的落地场景：Coed-y-Brenin 铜矿

Lecture 后半段（Slide 18–32）和整个 Practical 共享同一个案例：**北威尔士 Snowdonia（Eryri）南缘、Harlech Dome 内的 Coed-y-Brenin 斑岩型铜矿**。

Lecture 用它讲**为什么要做**（关键金属需求、采矿的环境与人权代价），Practical 用它讲**怎么做**（把 1970 年代钻孔的铜品位数据放回地下正确位置，用 3D 克里金插值成体，再筛出经济品位的矿体几何）。

最后老师抛出的是一个**开放的价值判断题**（Slide 32 标题原文）：

> "**Would you dig up Eryri (Snowdonia) to access it?**"

这不是修辞——转写里他明确说 "I'd be interested to hear your opinion"。这类「技术 + 伦理」的收尾正好呼应课程 ILO 4「Choose an appropriate geospatial technique to solve a given scientific problem」。

---

## 二、核心概念

### 2.1 「3D」到底是什么：2D / 2.5D / 3D 的分界

这是本周**第一位**的概念，也是头号考点。

#### 2.1.1 问题的出发点

老师的切入极朴素：

> "most of the times we're interacting with GIS data ... we're doing it on a computer screen or we're doing it on a paper map. And both of these are 2D surfaces. So how can you have 3D in a GIS world?"

**显示介质永远是 2D 的**（纸、屏幕）。所以「3D」不可能由「看起来立体」来定义，必须由**数据本身的结构**来定义。

#### 2.1.2 判据：**volume（体积）**

讲义 Slide 6 给出唯一判据：

> "**Volume is integral in geospatial 3D.** To specify a location within these datasets we need to specify **x, y and z** coordinates."

转写里说得更直白：

> "What's important for defining something as 3D? And the most important thing is **it contains volume**."

**操作化的判别方法（务必记住这一条，可以直接用来做判断题）：**

> **给你一个 (x, y)，答案唯一吗？**
> - 唯一 → 这是一个 **surface（表面）**，本质是 **2D**（哪怕它在三维空间里起伏）。
> - 不唯一（同一 x,y 上下有多个值）→ 这才是 **volume（体）**，才是真 **3D**。

#### 2.1.3 三个层级（用讲义 Slide 4–6 的 Isle of Mull 三连图理解）

| 层级 | 讲义示例 | 定位需要 | 数学本质 |
|---|---|---|---|
| **2D** | Isle of Mull 的 **2D geological map**（BGS 纸质图的数字版） | x, y | 平面 |
| **2.5D** | 同一张地质图 **drape 在 DTM 上** | 仍然只要 x, y | **surface（表面）** —— 讲义 Slide 5 原文：「This is **not 3D**（mathematically speaking a 'surface' is always 2D）」 |
| **真 3D** | 荷兰土壤剖面体、地下构造模型 | x, y, **z** | **volume（体）** |

**⚠️ 2.5D 这一层是全周的重心。** 讲义 Slide 5 的原话值得逐字记：

> "The map is a surface existing in 3D space. But a point on this surface can still be described using only x and y coordinates."

翻译：**它是「存在于三维空间中的一个二维面」，不是三维体。** DTM/DEM 每个平面位置只存**一个**高程值，所以它无法表达：洞穴、悬崖倒悬（overhang）、多层结构、地下矿体、水体温度剖面——凡是「同一个 x,y 上下有不同东西」的情形，2.5D 一律表达不了。

#### 2.1.4 Wolfenstein 3D：教科书级的 2.5D 类比

讲义 Slide 3 与转写都花了不少篇幅在电子游戏史上，这不是闲聊，而是**给 2.5D 一个直觉锚点**：

- **Wolfenstein 3D**（讲义标 1991）号称是最早的商业「3D」游戏之一。
- 它用的技术叫 **raycasting（光线投射）**——讲义定义：「a **2D rendering technique** to give sprites / walls the appearance of 3D」（一种**二维渲染技巧**，让精灵图和墙面**看起来**立体）。
- 但游戏的运行逻辑仍在 **x, y 平面**：「the game plays in x, y space. **There is no access to the 3rd dimension**」——你不能跳、不能上下楼、不能站在墙头。
- 因此它被称为 **2.5D**。

老师顺手给了一个很有意思的类比：

> "You're interacting with topography. You're moving around a spatial world. So **a computer game is essentially a GIS program**."

他接着用 **Doom** 作为「拿到第三维」的分水岭：

> "as soon as games like Doom came along and you could start jumping up onto levels, running along the top of walls and stuff like that, then you've got access to the third dimension."

> 📎 背景补充（史实校正，见文末勘误表）：**Wolfenstein 3D 的实际发行年是 1992 年**（讲义写 1991）；1981 年的是前作 *Castle Wolfenstein*（这一点转写里老师说对了）。另外 **Doom（1993）在技术上同样属于 2.5D**——它的地图数据结构里同一 x,y 只能有一个地板/天花板高度（不支持 room-over-room），也不能真正垂直瞄准。业界公认的第一款真 3D 引擎是 **Quake（1996）**。老师用 Doom 作分界只是为了说明「能上下移动」的直觉，**不要把它当作严格的技术史结论**。

#### 2.1.5 真 3D 的代价：看得见外面，看不见里面

老师立刻指出了体数据的根本困难（讲义未写，仅口头）：

> "if you've got **volumetric data, you can only see the edges of it. You can't see what's going on inside it**. So in order to make it useful, we need to have ways of **interrogating** it, ways of **slicing it up** and looking at it in more detail."

这句话直接解释了 §2.7 全部可视化手段（slice、isosurface、data filter）的存在理由：**三维数据必须被「降维回 2D」才能被人看懂。** 这是本周一条贯穿始终的暗线。

---

### 2.2 Z 的麻烦：垂直基准（vertical datum）

本周第二大块，是把 W02/W03 的 datum 知识**只针对 Z** 重讲一遍。

#### 2.2.1 X、Y 好定义，Z 不好定义

讲义 Slide 7（lat–long 框架下）：

- **X** 由 **prime meridian（本初子午线）** 定义 —— 位于 **Greenwich**（伦敦附近）。
- **Y** 由 **equator（赤道）** 定义 —— 「the plane **equidistant** between the Earth's geographical poles」（与南北极等距的平面）。
- **Z** —— **how do we define height?**

老师点出问题的实质：

> "the prime meridian and the equator are both effectively **2D things, 2D phenomena**. So how do we define height away from that?"

即：X、Y 的基准是两个**几何上可以定死的面**；而高度的基准必须依附于「地球的形状」，而地球的形状本身就不规则。

#### 2.2.2 为什么「到地心的距离」不能当 Z

讲义 Slide 8：

- Earth is **not spherical**。
- 现代测量证明地球是 **oblate spheroid（扁椭球 / 扁球体）**。
- 讲义给的数字：**equatorial diameter 12,700 km**，**polar diameter 约短 40 km**。
- 结论：**distance from the centre of the Earth is not a valid Z**（到地心的距离不是有效的 Z）。

理由很直观：从赤道走到极点，**地表到地心的距离本身就在变**，所以同一个「到地心距离」在不同纬度对应完全不同的「海拔」。

> 📎 背景补充（数值校正，见勘误表）：**赤道直径的准确值是约 12,756 km**（赤道半径 6,378.137 km），**极直径约 12,714 km**（极半径 6,356.752 km），两者相差约 **43 km**——「相差约 40 km」是对的，但 **12,700 km 偏小约 56 km**，它更接近地球的**平均直径 12,742 km**。
> 扁率 **f = (a − b) / a ≈ 1/298.257**（见 §3.1）。

#### 2.2.3 Newton 的两口井：oblate spheroid 的由来（纯口头内容）

这段**只在转写里有，讲义完全没有**，是本周最好的一个故事，值得完整记住：

> "Isaac Newton ... used thought experiments to think about what shape the Earth would be. And his basic idea was that if we **drilled two wells, one down from the pole to the very centre of the Earth, and another down from the equator to the very centre of the Earth**, and then we **filled these two wells up with water so that they were a linked system**, he thought the **equator well would have to be longer in order for the system to be in equilibrium**."

牛顿把这个差异归因于**角动量（angular momentum）**：地球自转把赤道处的水「甩出去」，等效于降低了赤道井中的有效重力，因此赤道井需要更长的水柱才能与极井平衡。老师评价这是「**this sort of first ideas of angular momentum**」，而且牛顿把同样的推理用到了地球质量分布上，预言地球的赤道直径更大——**后来被证明是对的**。

**为什么这个故事重要：** 它说明「地球是扁的」不是观测巧合，而是**自转 + 流体静力平衡**的必然结果。这也是为什么用一个**旋转椭球（ellipsoid）**而不是球来近似地球。

#### 2.2.4 Geodesy、Ellipsoid、Geoid 三件套

讲义 Slide 9 标题给了定义：

> **Geodesy（大地测量学）**: the science of measuring **Earth's shape, orientation and gravity field**.（测量地球的形状、定向与重力场的科学）

**Ellipsoid（椭球体）** — 讲义：「an **idealised mathematical model** of the Earth」。老师补充：「It just **covers everything, averages everything out**」（把一切平均掉的理想模型）。

讲义 Slide 9 的关键一句（**全局 vs 局部**的取舍）：

> "**National map grids typically use an ellipsoid closely approximating the local geoid.** This works at 'local' scale, but is **too general for global maps**."

转写把这层意思讲反着说了一遍，两句合看才完整：

> "most of the sort of global scale things like your phone uses an online version of **WGS 84**, which is related to these **global ellipsoids**. **Local national grids tend to use a different ellipsoid**, one that a little bit better approximates the shape of the Earth's surface **in the area that you're at**. So these generally have **different functions**, the sort of national scale maps versus the global scale maps."

**要点：椭球没有「对与错」，只有「适不适合你的范围」。** 全球椭球（GRS80/WGS84）在全球范围内平均最优；国家椭球（如英国的 **Airy 1830**）在本国范围内贴合最好，但拿到全球就不行。

**Geoid（大地水准面）** — 转写给了精确定义（讲义 Slide 9 只画了图）：

> "A geoid is a **gravitational equipotential surface**. So it's the point where the gravitational measurements of the Earth's surface are sort of equal around the planet. And it's **broadly equivalent to sea level, but it changes. It's not a constant thing.** It changes as things that have mass move around the planet."

**geoid = 重力等位面 ≈ 平均海平面（延伸到陆地下方）**，但它是**动态的、起伏的**。

**影响 geoid 的因素**（讲义 Slide 9 列表 + 转写补充，合并后）：

| 因素 | 英文 | 出处 |
|---|---|---|
| 岩性密度 | lithological density | 讲义 + 转写 |
| 潮汐 | tides | 讲义 + 转写 |
| 板块构造 | plate tectonics | 讲义 + 转写 |
| 水深 | water depth | 讲义 + 转写 |
| 瞬时地壳加热 | transient crustal heating | 讲义 + 转写 |
| 侵蚀与沉积 | erosion / deposition | **仅转写** |
| 造山（山脉生长） | mountain growth | **仅转写** |
| 大陆漂移 | continental drift | **仅转写** |
| 地幔柱的活化与松弛 | activation and relaxation of mantle plumes | **仅转写**（转写作 "magnetic plumes"，系语音识别错误） |
| 构造动力载荷 | tectonic dynamic loads | **仅转写** |

#### 2.2.5 两个 geoid 异常实例（讲义 Slide 9 配图 + 转写详解）

| 位置 | 异常 | 成因 |
|---|---|---|
| **欧洲** | **red = gravity high**（重力高） | 「excess mass due to **dense crust and deep Moho**」；转写补充：欧洲是**稳定克拉通（stable craton）**，地壳非常厚，**多余质量 → 上方重力更高** |
| **印度洋（印度南端外海）** | **blue = gravity low**（重力低），即 **Indian Ocean Geoid Low** | 「Caused by **hot, low-density mantle plumes**」（热的、低密度的地幔柱物质）→ 引力不足 → **海面在此处凹陷 106 m** |

引文：**Pal & Ghosh, 2023**, https://doi.org/10.1029/2022GL102694

> ⚠️ 讲义原句「Sea level is **106 m below MSL** over the Indian Ocean Geoid low」和转写「sea level is 106 meters **below the sea level** there」都说不通（海平面不可能比海平面低）。**正确表述是：该处大地水准面比参考椭球面低约 106 m。** 见勘误表。

#### 2.2.6 三种「高」：ellipsoid height / geoid height / orthometric height

讲义 Slide 10 的示意图给了四个标签：**Topographic surface**、**Ellipsoid height**、**Geoid height**、**Orthometric height**、**Ocean**。这是本周**必须会画**的一张图（详见 §3.2）。

| 术语 | 英文 | 含义 |
|---|---|---|
| 椭球高 | **Ellipsoid height (h)** | 从**参考椭球面**沿法线量到地表的高度 —— **GNSS/GPS 直接测得的就是这个** |
| 大地水准面高 / 起伏 | **Geoid height (N)** | 大地水准面相对参考椭球面的高差（可正可负） |
| 正高 | **Orthometric height (H)** | 从**大地水准面**（≈平均海平面）量到地表的高度 —— **地图上标的「海拔」是这个** |

关系式见 §3.2。

#### 2.2.7 英国的三套 Z 系统（讲义 Slide 10）

| 系统 | 英文全称 | 基准 | 特点 |
|---|---|---|---|
| **OSGB36** | Ordnance Survey of Great Britain 1936 coordinate reference system | 系于 **Cornwall 的 Newlyn 平均海平面（tide gauge）** | **traditional datum** —— 由 **trig pillars（三角点石柱）** 组成的三角测量网，拟合到 **Airy 1830 ellipsoid** |
| **OS GPS permanent network** | 系于 **GB ETRS89**（European Terrestrial Reference System 1989） | 讲义称其为「a version of **WGS84**」 | 现代 GNSS 基准；**RTK 测量**接入的就是这张网 |
| **GPS（手机等）** | 全球 **WGS84**（World Geodetic System 1984） | 系于 **GRS80 ellipsoid**（Geodetic Reference System 1980） | 「the one that you'll most regularly find」 |

**讲义 Slide 10 的结论句（重点）：**

> "**All these systems will produce different z values – and maybe changes in xy.** A **mathematical transform** is needed to convert between coordinate frameworks."

老师用「爬山测山顶」把原因讲清楚了（讲义没有这段推理）：

> "if we were to climb this mountain and measure the top of this mountain, if we were to use different coordinate systems, we would end up with slightly different measurements. And the reason for that is that **our measurement position is defined effectively perpendicular to the reference system that we're using**. So if we're using the geoid height, which is more sort of ups and downs, more complexity associated with it, it can produce, when we measure sort of perpendicular to it ... a slightly different X, Y and Z coordinate than if we use a more global ellipsoid."

**核心机制：高度是沿着「垂直于参考面」的方向量的；参考面不同（geoid 起伏 vs 椭球光滑），法线方向不同，量出的 z 就不同，甚至 x、y 也会偏。**

他给的实战警告（**本周最实用的一句**）：

> "you need to use **translation systems** in order to convert from one coordinate system to another, which can generate all sorts of complexity if you've got data in different coordinate systems, or **data with an unknown coordinate system is your worst case scenario**."

**记住：坐标系未知的数据 = 最坏情况。** 因为已知的不同坐标系可以转换，未知的无法转换，只能猜。

> 📎 背景补充（严谨性提示，见勘误表）：讲义把 OSGB36 说成「tied to mean sea-level at Newlyn」略有混淆——**OSGB36 是水平大地基准（horizontal datum）**，英国的**垂直基准**正式名称是 **ODN（Ordnance Datum Newlyn）**，它才是系于 Newlyn 验潮站的。两者常被打包称作「OSGB36 / ODN」，但概念上应分开。
> 另外，**ETRS89 并不等于 WGS84**：ETRS89 在 1989.0 历元与 WGS84 重合，但此后**固连在欧亚板块稳定部分上随板块一起移动**，而 WGS84 是全球框架。到今天两者已相差**数十厘米**（欧亚板块约 2.5 cm/yr × 三十多年）。「a version of WGS84」是方便说法，不是严格等价。
> 还有，**WGS84 有自己的椭球**（WGS84 ellipsoid），它与 GRS80 几乎相同但扁率定义方式不同，差异在**亚毫米量级**，工程上可视为同一椭球。

---

### 2.3 数字空间：从 pixel 到 voxel

#### 2.3.1 复习：raster / vector（讲义 Slide 11 + 转写）

| 类型 | 英文 | 构成 | 例子 |
|---|---|---|---|
| 矢量 | **vector** | 点、线、面 | 道路（线）、井位（点） |
| 栅格 | **raster** | 规则排列的 **pixel（像元）** 阵列 | 航空影像、DEM |

讲义 Slide 11 对 **pixel** 的定义：

> "The **smallest unit of information in a 2D raster image**. In GIS a pixel is a **cell in a regular array of data values**. Each pixel has an **x, y location** and a **set of descriptors** such as **R, G, B, or height**."

**注意 pixel 的两要素：①一个 x,y 位置 ②一组描述符。** 描述符可以是颜色三通道（RGB，用于影像），也可以是高程（用于 DEM）。

> ⚠️ 转写此处老师**口误**：「raster data is lines in space, things like roads」——**线状要素属于 vector，不是 raster**。同一段的后半句「Pixel data is what you find in raster information」才是对的。见勘误表。

#### 2.3.2 Voxel（体元）——本周的核心数据结构

讲义 Slide 11：

> **VOXELS**: A **3-dimensional pixel** used to display 3D images.
> "Each voxel has an **x, y, z position** and a **set of descriptors** used to describe **volume – or other data such as discrete class, time, density, porosity**, etc."

转写把「voxel = 3D raster」讲得更清楚：

> "We can take this idea and expand it into what's known as a voxel. And it's essentially a **three dimensional raster image**. So each voxel in this cube of voxels here has an X, Y and Z position."

**Voxel 的描述符可以是什么**（转写列举，比讲义更细）：

- **discrete class**（离散类别，如土壤类型、岩性）
- **time**（时间，「if we're looking at how things change」）
- **density**（密度）
- **rock type**（岩性）
- **reservoir properties, things like porosity**（储层性质，如孔隙度）

**pixel → voxel 的类比表（务必背下这张对照）：**

| | 2D | 3D |
|---|---|---|
| 基本单元 | **pixel** | **voxel** |
| 位置 | x, y | x, y, z |
| 集合体 | raster image（栅格影像） | **voxel layer（体元图层）** |
| 描述符 | R,G,B / height / … | class / time / density / porosity / grade… |
| 几何本质 | 面（area） | **体（volume）** |

> 📎 背景补充：**voxel 是 "volumetric pixel" 的缩写**（volume + element / volume + pixel），材料未给出词源。在 ArcGIS Pro 中 voxel layer 的物理载体是 **netCDF 文件（.nc）**（见 §5 第 12 步）。

---

### 2.4 离散数据与连续数据（3D 版复习）

讲义 Slide 12 的核心命题：

> "**Voxel layers can be created using discrete data or continuous data.**"

即：**你在 2D 里用什么数据建栅格，在 3D 里就能用什么数据建体元。** 这就是 Slide 2 里「Exploration of GIS data definitions」这条 ILO 的落点。

#### 2.4.1 Discrete data（离散数据）

讲义 Slide 13 定义：

- Information assigned to **defined values, usually integers**.（赋给确定值，通常是整数）
- Can have different functions, but **must have defined boundaries**.（可以有不同用途，但**必须有明确边界**）

两类用法：

| 用法 | 英文 | 讲义例子 |
|---|---|---|
| **计数变量** | **Counted variable** | Pets per household（每户宠物数）、Town population（城镇人口） |
| **分类编码** | used to **classify** | Land use（土地利用）、Geological map unit（地质图单元）、Road type（道路等级） |

讲义 Slide 13 给的 road type 编码表（典型的离散编码 + symbology 绑定）：

| class | Road type |
|---|---|
| 1 | Path（小径） |
| 2 | Track（土路） |
| 3 | B road（B 级路） |
| 4 | A road（A 级路） |

老师的解释（讲义没写这句，很好用）：

> "**discrete data is effectively a coding system**"（离散数据本质上就是一套编码系统）

他用地质图举例：

> "each of these different geological units is **encoded**. And if we look around it, we can see there's a **defined boundary** between our different geological units."

#### 2.4.2 Continuous data（连续数据）

讲义 Slide 14 定义：

- A **measured variable** that could have **any numeric value**.（可取任意数值的**测量**变量）
- **There are no boundaries**: values **vary continuously**.（**没有边界**，值连续变化）

讲义给的 2D GIS 例子：**Elevation（高程）、Rainfall（降雨）、Satellite photos（卫星影像）、Gravity（重力）**。转写补充了 **temperature（温度）**。

老师对「没有边界」的解释：

> "here we're looking at an elevation map and we can see that our elevation goes from low to high continuously. So **there's no boundaries between our different height values here**."

#### 2.4.3 两个 3D 实例（讲义 Slide 12，均来自 Esri ArcGIS Pro 文档）

| 实例 | 数据类型 | 说明 |
|---|---|---|
| **Dutch soil profiles**（荷兰土壤剖面） | **discrete** | 「Voxels are coded using **discrete data that represents soil categories**」——每个体元存一个土壤类别码 |
| **Gulf of Mexico temperature distribution**（墨西哥湾温度分布） | **continuous** | 「The plot is a **geostatistical interpolation of continuous data** recorded at many individual sample points」——由离散采样点插值成连续体 |

**⚠️ 这两个例子的对比正是 Practical 的方法论预告**：Coed-y-Brenin 的 Cu_percent 是**连续数据**，来自**有限的钻孔采样点**，因此必须走「墨西哥湾温度」那条路——**geostatistical interpolation**。

**记忆钩子：**
- discrete → 有边界 → 直接编码填体元
- continuous → 无边界 → **必须插值**才能填满体元之间的空白

---

### 2.5 地下数据的根本困境：稀疏采样

在讲插值之前，老师先解释了**为什么非插值不可**（这段**只在转写里**，讲义完全没有，但它是理解整个 Practical 的前提）：

> "quite often when you're dealing with the subsurface, when you're dealing with what's going on below ground level, **you don't really have access to it. You don't have access to that full 3D volume**."

**我们能拿到的地下数据只有三类**（转写列举）：

| 数据源 | 英文 | 老师的描述 | 覆盖特征 |
|---|---|---|---|
| **钻孔** | **boreholes** | 「people have drilled a hole and recovered a small amount of rock which you can identify. So it gives you a **very small window** into the subsurface」 | **一维线**（沿井轴），平面上是**点** |
| **探地雷达** | **ground penetrating radar (GPR)** | 「fire energy into the earth and then look at the **reflected patterns** that come back」 | 剖面 |
| **地震勘探** | **seismic surveys** | 同上 | 剖面 / 体（3D 地震） |

结论句：

> "But **it's not a complete picture**. So usually we need to **interpolate between that limited data** in order to get a picture of what's going on."

**这就是 3D 地统计存在的全部理由：** 用少量已知点，估计整个体内每一处的值。

---

### 2.6 3D 地统计插值：Empirical Bayesian Kriging 3D

#### 2.6.1 名字拆开看（讲义 Slide 15 + 转写）

讲义 Slide 15 的定义：

> "A **geostatistical interpolation tool** that uses **Empirical Bayesian Kriging methodology** to interpolate points in 3D."

**逐词拆解：**

| 词 | 讲义定义 | 转写补充 |
|---|---|---|
| **Kriging（克里金）** | "spatial interpolation between point data"（点数据之间的空间插值） | "a method of interpolating between point data" |
| **Bayesian（贝叶斯）** | "employment of **prior knowledge** into a calculation"（把先验知识纳入计算） | 同 |
| **Empirical（经验）** | 讲义未单独定义 | 由数据本身反复估计模型，而非人工指定 |

**先验知识在这里具体指什么？** 讲义 Slide 15 说得很准确：

> "Here, **prior knowledge is an estimation of the semi-variogram and associated uncertainty**. ArcGIS **iterates**, each time estimating a **new semi-variogram** to close in on the final model."

老师的口头版本：

> "it basically uses the information it's got to calculate **statistical relationships** between the variables that we've got and then **run that experiment repeatedly** until it comes up with a model of how the relationships work. And then it uses that to effectively **fill in the space between the points that we do know**."

#### 2.6.2 EBK3D 的迭代机制（Practical Figure 2 图注，最精确的一段）

Practical 的 Figure 2 图注给出了**具体算法流程**，这是三份材料里对 EBK3D 讲得最细的地方，务必逐条掌握：

> "The 3D Empirical Bayesian Kriging process is different. It **divides the data into subsets of points (default is 100 points)**, to **estimate a series of semi-variograms**. These semi-variograms are used to **simulate data at the input points**. This new data is used to **estimate a new semi-variogram** and the process **repeated a set number of times**. This generates a **large number of semi-variograms (blue lines)**. ArcGIS makes sense of it by **binning the data into pairs of points with common lag distance and direction**. These **empirical (experimental) semi-variances are plotted as blue crosses**."

**拆成五步（考试可直接写这五步）：**

1. **分子集**：把数据切成若干 subset，**默认每个 subset 100 个点**。
2. **估初始半变异函数**：对每个 subset 估一条 semi-variogram。
3. **模拟**：用这条 semi-variogram 在**原输入点位置上**模拟一批新数据。
4. **再估**：用模拟数据再估一条新的 semi-variogram；**重复固定次数**。
5. **汇总**：得到**大量**半变异函数（图上表现为**一簇蓝色曲线**）；ArcGIS 把点对按**相同 lag distance 与方向**分箱（binning），画成**蓝色十字**（实测半变异值）。

**⚠️ 这就是 EBK 与传统 kriging 的根本区别：** 传统 kriging 用**一条**人工选定/拟合的半变异函数；**EBK 用一大簇由数据自动生成的半变异函数，因而自带不确定性度量，且不需要用户手动调模型**——这正是 Practical 敢让你「Continue through the dialogue using **defaults for all options**」的原因。

#### 2.6.3 输出形态：先切片，后成体

讲义 Slide 15 结尾两句是**理解整个 Practical 后半段的钥匙**：

> "The tool generates a series of **2D horizontal slices** which can be **scrolled through**."
> "The **Geostatistical layers can be combined to create a 3D voxel layer**."

转写同义：

> "our empirical Bayesian Kriging produces a **set of horizontal slices** that move through the data and then we use ArcGIS again to **convert that into a volume** to basically **interpolate between those 2D slices** to come up with a three-dimensional volume."

**流程链（背下来）：**

> **点（钻孔样品）** → *EBK3D* → **一叠水平切片（geostatistical layer，用右侧竖直滑块浏览）** → *GA Layer 3D To NetCDF* → **voxel layer（真三维体）**

**⚠️ 易混点：EBK3D 的直接输出不是 voxel layer，而是一个可以按高度滑动浏览的「地统计图层」。必须再导出一步才拿到体。**（见 §5 第 11–12 步）

---

### 2.7 三维数据的可视化与「拆解」

#### 2.7.1 为什么需要专门的手段

回到 §2.1.5 的那句：体数据**只能看到外壳**。讲义 Slide 16–17 与转写给出三类破解手段。

老师的原话：

> "once you have that information, you often have to sort of **subsample it into 2D in order to be able to visualize it properly**."

#### 2.7.2 三种手段

| 手段 | 英文 | 定义 | 出处 |
|---|---|---|---|
| **垂直/水平切片** | **slice** | 从体中切出一张 2D 平面（讲义写「2D **vertical** slices」；EBK3D 原生产出的是**水平**切片） | 讲义 Slide 17 |
| **等值面** | **isosurface** | 讲义：「a surface created from **equal concentration values**」；Practical：「a **surface of equal value**. It can be used to **set and isolate the outer boundary of the ore body**」 | 讲义 Slide 17 + Practical |
| **数据过滤** | **data filter** | 按属性值域裁掉不需要的体元（Practical 用它滤掉 <0.2% Cu 的体元） | Practical |

老师对 isosurface 的口头解释（比讲义直白）：

> "an ISO surface is where this red area here is an ISO surface. It's where you **map out equal values that sort of wrap around your data** in order to **visualize the shape of the phenomena** that you're trying to image."

**理解要点：isosurface 就是三维里的「等值线」——2D 等值线 (contour) 连的是等值的点成线，3D 等值面连的是等值的点成面。** 它把「浓度 ≥ 某值的区域」的**外壳**画出来，于是矿体的**几何形状**就直接可见了。

#### 2.7.3 体数据可视化的应用领域

讲义 Slide 16 与转写列举（合并）：

| 领域 | 例子 |
|---|---|
| **地下 Subsurface** | porosity（孔隙度）、metal concentration（金属含量）；转写补充：**resource calculation（资源量计算）**、**aquifer calculation（含水层计算）** |
| **大气 Atmospheric** | 讲义 Slide 16 配 Esri 动画：**2003 年 daily relative humidity with altitude**（相对湿度随高度的日变化） |
| **海洋 Oceanic** | temperature（温度）、pollutant concentration（污染物浓度）；讲义 Slide 17 用 **oceanic nitrate concentration**（海洋硝酸盐浓度）演示 slice 与 isosurface |

讲义 Slide 16 的总评：

> "**Volumetric realisations provide a powerful method of visualising 3D data.**"

Slide 17 结尾还有一句预告：「**We will be slicing this afternoon**」（转写作 "we'll be slicing on Friday"）。

> ⚠️ 时间说法不一致：讲义写「this afternoon」，转写里老师三次说 practical 在 **Friday**。见勘误表（不影响知识点）。

---

### 2.8 地质背景：斑岩铜矿（porphyry copper deposit）

本节是 Practical 的**地质前提**，考试若考「为什么矿体是这个形状」必须用得上。讲义 Slide 24–30 与 Practical 的 Geological background 一节内容互补。

#### 2.8.1 成矿链条（讲义 Slide 24–25，引 Park et al. 2021 与 Richards & Mumin 2013）

**第一阶段——金属的来源（俯冲带）：**

1. **Associated with convergent plate tectonics**（与汇聚型板块边界相关）；老师说「particularly associated with **destructive** volcanism」（消亡带火山作用）。
2. **Downgoing slab sources O₂-rich waters and hydrous melts**（下插板片释放富氧的水和含水熔体）。转写：板片中的水被加热驱出，形成 **hydrous melts**，且含大量氧。
3. **Mantle wedge（地幔楔）**：「partial melting in **oxidising conditions deplete sulphides**」——在**氧化条件**下部分熔融，把硫化物耗尽。
4. **Cu 和 Au 对硫化物有亲和性（affinity for sulphides）**，因此被**优先带入上升的富硫化物熔体**中。

**第二阶段——岩浆的演化与上升：**

5. **Hydrous basaltic magmas** 上升到 **mantle–crust boundary（30–70 km）**，在那里通过 **fractionation / magmatic differentiation（分离结晶 / 岩浆分异）** 演化，**浓缩成矿流体**。
6. 演化后的岩浆继续上升，随**上覆压力下降**而变为 **fluid saturated（流体饱和）**。

**第三阶段——成矿（浅部，1–7 km）：**

7. 「Relative **low-density fluids** liberated from **shallow magmatic intrusions (1–7 km)** accumulate **at top of intrusion**」（低密度流体在侵入体顶部聚集）。
8. 「The **high pressure fluids hydraulic fracture (frack)** the top of intrusion and country rock」（高压流体**水力压裂**侵入体顶部与围岩）。
9. 「The fluids **condense and cool to a metal rich brine**」（冷凝成富金属卤水）。
10. 「**Metal sulphides precipitated from cooling brines** forming **halos** around the intrusions」（金属硫化物从冷却卤水中沉淀，在侵入体周围形成**晕圈**）。

老师补充了讲义没有的一点：除了裂隙充填，还有 **disseminated（浸染状）** 的 Cu、Au——「just basically sitting in the **pore spaces** of these sort of country rocks and also partly in the magmatic bodies as well」。

#### 2.8.2 蚀变与岩相分带（讲义 Slide 26）

| 单元 | 英文 | 特征 |
|---|---|---|
| **爆破角砾岩筒** | **Explosion breccia pipe** | 「Bleached / shattered **hydrous silica**. Sometimes '**pods**' of copper」（漂白/破碎的含水硅质，有时含铜「豆荚体」） |
| **绢云母化带** | **Sericitic zone** | 「hydrothermally decomposed microtonalite – here, **iron stained – pyrite rich**」（热液分解的微二长闪长岩，铁染、富黄铁矿） |
| **富铜蚀变带** | — | 「hydrothermally decomposed microtonalite – here, **enriched with copper**」 |
| **未蚀变原岩** | **Microtonalite: un-altered** | 新鲜微闪长岩 |

老师对角砾岩筒补了一句机制：

> "sometimes the **porosity in those shattered country rocks** can become very strongly mineralized by the fluids that were moving up through them."

#### 2.8.3 品位与表生富集（supergene enrichment）（讲义 Slide 27）

- **Porphyry halos are large, low grade bodies: a good one is 1% Cu.**（斑岩晕圈是**大而贫**的矿体，好的也就 1% Cu）
- **Supergene enrichment** 是发生在**近地表**的 **redox（氧化还原）过程**，可以把品位富集到 **>2%**。
- 机制：「**O₂ rich meteoric waters** weather and **leach metals** from the porphyry, and **re-deposit in deeper, reducing conditions**」（富氧大气降水在浅部淋滤金属，带到深部**还原**环境再沉淀）。

**实例：Reko Diq Mine, Pakistan**（引 Witherly, 2003 / DOI 年份 2023）——电磁勘探 + 解释的地壳剖面，穿过富集的表生带。
**储量数字：5.9 billion tonnes of ore @ 0.41% copper and 0.22 ppm gold（0.000022%）。**

> ⚠️ 转写里老师说「a good one might be sort of **2% copper**」，与讲义「a good one is **1% Cu**」矛盾；他随后又说「It could **double it from 1% to more than 2%**」，与讲义一致。**以讲义为准：原生斑岩好矿 ≈ 1% Cu，表生富集后 >2%。** 见勘误表。

#### 2.8.4 Coed-y-Brenin 的具体地质（Practical 的 Geological background，最详细）

Practical 给的解释与讲义的「经典弧后斑岩」略有不同，**以 Practical 为准**：

> "Mineralisation is interpreted to be part of a **copper-porphyry system (Mason, Liezers and Cotterell, 2018)**. In their scenario a **regional scale hydrothermal system** was driven by the **Rhobell volcanic system during the early Ordovician**. Circulating groundwaters carried metals derived from the volcanic bodies and **dissolved from local Cambrian shales of the Mawddach Group**. The metals accumulated in **altered, sheared and fractured intermediate volcanic rocks: microtonalite**."

**矿化形式（务必记住，直接决定 Practical 的插值结果长什么样）：**

- 「The **low grade copper mineralisation occurs as chalcopyrite associated with pyrite** and **disseminated through the rock volume** and **within small veinlets**.」（低品位铜以**黄铜矿**形式出现，伴生**黄铁矿**，**浸染状**分布于整个岩石体积中，并见于细脉）
- 「Later **quartz-carbonate filled veins** are larger and associated with **pods of both chalcopyrite and molybdenite**.」（后期石英-碳酸盐脉更大，含黄铜矿与**辉钼矿**豆荚体）
- 「The link to hydrothermal origins are particularly evident in **phreato-magmatic explosion breccia pipes** found in the **upper part of the porphyry**. Some of the breccia pipes are significantly **enriched in copper, arsenic, gold and tin – the Glasdir mine providing a prime example**.」

**斑岩系统的金属分带（Practical 的 extra task 一节，引 Sillitoe 2010）：**

> "As magmatic driven hydrothermal fluids pass upwards through the rock volume they develop a **central zone where copper becomes concentrated as copper sulphides**. **Outside this is a halo enriched in pyrite (iron sulphide)**. Separate hydrothermal phases may also deposit other metal rich phases."

配图（Figure 3）说明：**Blue: central core enriched to greater than 0.2% copper. Pink: pyrite rich (>1.5%) halo.**

**→ 这个「铜核 + 黄铁矿晕」的同心结构，就是 Practical 最后要你在 voxel 图里亲眼验证的东西。**

#### 2.8.5 采矿史（讲义 Slide 29–31 + Practical + 转写）

| 项目 | 讲义 / 转写 | Practical |
|---|---|---|
| 区域 | Harlech Dome 内的 Coed-y-Brenin | 同 |
| 区域总产金 | — | **130,000 oz gold**，另有 lead、silver、manganese、copper |
| 主矿山 | **Glasdir mine**（讲义误写 "Gasdir"） | Glasdir mine |
| 铜产量 | 「Shallow mines produced **13,077 t Cu ore**, 8275 oz Ag, 735 oz Au」 | 「produced about **1300 tonnes**」 |
| 开采时段 | 「Mining history **1850's to 1915**」 | 「until closure in **1914**」 |
| 关闭原因 | 「closed due to affects of **mine tailings polluting fisheries**」 | 「local campaigns organised to stop degradation of **salmon fisheries** by the dumping of mine waste into local rivers」 |
| 泥炭矿 | **Dolfrwnog Mine and 'turf' mine**：极局部表生富集；富氧地下水穿过斑岩后在**泥炭沼泽**出露，泥炭强还原条件下沉淀出**native copper and gold（自然铜与自然金）**；**1824–1865 年间把泥炭挖出来焙烧当矿石** | — |
| 生物指示 | **Sea Pinks（Armeria maritima）** 耐金属（含铜） | **Sea Pinks (Armeria maritima)** 与 **Sea-Campion (Silene uniflora)**，生长在矿渣堆与富金属水出露处 |
| 勘探数据 | 「Series of exploration wells drilled in the **1970s**」，数据录入 Excel，含 Cu 及其他金属 | 「extensively drilled in the **1960 and 1970s** to establish the extent of low grade copper mineralisation」 |

---

### 2.9 📎 本周**未**涉及的 3D 内容（防止复习时张冠李戴）

> 📎 背景补充（以下全部为补充，三份材料**均未提及**，列出仅为界定边界，避免把别处看来的内容误记成本周内容）：
>
> | 主题 | 本周是否涉及 |
> |---|---|
> | 点云 point cloud、**LAS / LAZ** 格式、点云分类码（ground/vegetation/building） | **未涉及** |
> | **TIN**（Triangulated Irregular Network，不规则三角网）作为 GIS 表面模型 | **未涉及**（转写里的 "triangular irregular network" 指的是 **OS 三角测量网**，见 §6 易错点） |
> | **Multipatch**（多面体要素） | **未涉及** |
> | **Lidar**（机载/地面/移动）、**SfM**、**摄影测量**、**SAR/InSAR**、**BIM** | **未涉及**（这些出现在官方大纲里，但实际未授课） |
> | **Extrusion（拉伸）**、**Vertical exaggeration（垂直夸大）** | **未涉及**（ArcGIS Pro 中分别在图层 Appearance 选项卡的 Extrusion 组、以及 Scene Properties > Elevation Surface 的 Vertical Exaggeration） |
> | **3D viewshed / skyline analysis / 3D buffer** | **未涉及** |
> | **由点云生成 DSM / DTM** | **未涉及** |
>
> 本周的 3D 是**「体积 + 地统计插值 + 体元可视化」**这一条线，与「三维测量与建模」那条线不同。

---

## 三、公式与图表

> ⚠️ 说明：本周讲义与 Practical 的定量内容偏少，**除了品位换算，其余公式均为 📎 背景补充**（材料只给了文字定义或图示，未写公式）。补充公式的作用是帮你理解概念在算什么，**不是材料要求背诵的内容**。

### 3.1 椭球的扁率（flattening）

材料给的是数值（赤道直径、极直径），未给公式。

> 📎 背景补充：

$$f = \frac{a - b}{a}$$

- **a** = semi-major axis（赤道半径），**b** = semi-minor axis（极半径）
- 代入 GRS80/WGS84 的 a = 6,378,137 m、b ≈ 6,356,752 m：

$$f = \frac{6378137 - 6356752}{6378137} \approx \frac{21385}{6378137} \approx \frac{1}{298.257}$$

**解读：** 扁率约 1/298，即**极半径只比赤道半径短约 0.34%**。这个量极小——如果把地球画成直径 30 cm 的球，两者只差 1 mm。**但对测量学来说这 21 km 是决定性的**：忽略它会造成几公里的定位误差。讲义 Slide 8「polar diameter is about 40 km shorter」说的就是 2b 与 2a 之差（≈ 2 × 21.4 km ≈ 43 km）。

### 3.2 三种高度的关系（本周最该会的一条式子）

讲义 Slide 10 的示意图标了 **Topographic surface / Ellipsoid height / Geoid height / Orthometric height** 四个标签，但**没有给关系式**。

> 📎 背景补充：

$$H = h - N$$

| 符号 | 名称 | 参考面 | 谁测的 |
|---|---|---|---|
| **h** | **ellipsoid height（椭球高）** | reference ellipsoid | **GNSS / GPS 直接观测量** |
| **N** | **geoid height / geoid undulation（大地水准面高 / 起伏）** | ellipsoid → geoid 的高差 | 由**重力场模型**给出（如 OSGM15） |
| **H** | **orthometric height（正高）** | geoid（≈ MSL） | **地图上标注的「海拔」** |

**逐项解释：**

- **N 可正可负。** N > 0 表示大地水准面**高于**椭球面（该处质量偏多、重力偏强）；N < 0 表示**低于**椭球面。讲义提到的 **Indian Ocean Geoid Low 的 N ≈ −106 m**，是全球最负的地方；欧洲的红色区域则是 N > 0。
- **为什么 GPS 显示的高度和地图不一样？** 因为 GPS 原生给的是 **h**，地图给的是 **H**，两者相差 **N**。在英国 N 大约是 **+45 至 +57 m**（📎 补充数值，材料未给）。**如果不做 geoid 改正，你的高程会系统性地偏差数十米。**
- **这条式子正是讲义 Slide 10 结论句「All these systems will produce different z values」的数学表达。**

**在 Practical 里的对应：** 你把 vertical coordinate system 设为 **EVRF/EVRS2000（Gravity-related，即基于大地水准面的正高系统）**，而不是椭球高系统——这一步就是在选 H 而不是 h。

### 3.3 半变异函数（semi-variogram）

Practical 的 Figure 1 图注给了**完整的文字定义**，但**没给公式**。

**材料原文的六个定义（逐条务必掌握）：**

| 术语 | Practical 原文定义 | 中文解读 |
|---|---|---|
| **Sample variogram (Observed)** | "plot of **changing variance as lag distance increases**" | 实测数据算出的、方差随间距增大的变化曲线 |
| **Variogram model (Empirical)** | "**mathematical expression** used to describe the sample variogram" | 拟合实测曲线的数学函数（⚠️ 标签 "Empirical" 用错，见勘误表） |
| **Lag distance** | "the direction dependent **distance between data points**" | 点对之间的间隔距离 |
| **Semi-variance** | "**half the variance of the differences** between all possible points spaced a **constant distance** apart" | 相隔固定距离的所有点对，其差值方差的**一半** |
| **Range** | "The point where **increasing lag distance no longer has an effect on semi-variance**" | 变程：超过它，距离再远也不再影响相似性（= 空间自相关的作用半径） |
| **Nugget** | "semi-variance where separation distance between points is **zero**. In a perfect dataset the variogram model would **cross the y-axis at 0**. **Measurement error and Gaussian distribution of natural data** means it will have some variance." | 块金值：理论上距离为 0 时半变异应为 0；实际不为 0，源于**测量误差**与**自然数据本身的随机性** |

> 📎 背景补充（公式，材料未给）：

$$\gamma(h) = \frac{1}{2N(h)} \sum_{i=1}^{N(h)} \left[ z(x_i) - z(x_i + h) \right]^2$$

- **h** = lag distance（间距）
- **N(h)** = 相隔 h 的点对总数
- **z(xᵢ)** = 位置 xᵢ 处的观测值（本周即 Cu_percent）
- 分母里的 **2** 就是 "**semi**-variance" 里 "semi"（半）的来源。

**为什么曲线是上升的：** 距离越远，两点越不相似，差值越大，γ 越大——这正是 **Tobler 第一定律**（W04/W05 学过）的定量表达。曲线**升到平台（sill）后变平**，那个转折的横坐标就是 **range**。

> 📎 背景补充：材料**没提 sill（基台值）**这个术语，但它是读半变异图必备的第三个参数——**sill = 曲线达到的平台高度 ≈ 数据的总体方差**；**partial sill = sill − nugget**。

**3D 版的特别之处（Practical Figure 2）：** 在 EBK3D 里你看到的不是一条曲线，而是**一簇蓝色曲线（大量模拟出的半变异模型）+ 一片蓝色十字（分箱后的实测半变异值）**。**曲线簇的宽度本身就是不确定性的可视化**——簇越窄，模型越可信。

### 3.4 品位换算与经济截止品位（材料给出，唯一「必算」的一条）

Practical 原文：

> "The ore handling facilities are unable to process ore containing **less than 0.2% grade**. This is considered the **economical limit**, returning approximately **2 kg of copper per tonne of ore mined**."

**验算：**

$$1\ \text{tonne} = 1000\ \text{kg};\qquad 1000\ \text{kg} \times 0.2\% = 1000 \times 0.002 = \mathbf{2\ kg}$$

✓ 材料数值正确。

**通用换算（📎 背景补充，材料未列）：**

| 换算 | 关系 |
|---|---|
| 百分比 ↔ ppm | **1% = 10,000 ppm**；**1 ppm = 0.0001%** |
| ppm ↔ 克/吨 | **1 ppm = 1 g/t** |
| 品位 → 金属量 | 金属质量 = 矿石吨位 × 品位 |

**用它校验讲义 Slide 27 的 Reko Diq 数字：**
- 金品位 **0.22 ppm = 0.22 × 0.0001% = 0.000022%** ✓（讲义写的括号值正确）
- 铜金属量 = 5.9 × 10⁹ t × 0.41% ≈ **2.42 × 10⁷ t Cu**（约 2,420 万吨铜）📎
- 金金属量 = 5.9 × 10⁹ t × 0.22 g/t ≈ 1.30 × 10⁹ g ≈ **1,300 t Au** 📎

**本周 Practical 的经济截止品位一览：**

| 金属 | 单位 | 经济品位 | 出处 |
|---|---|---|---|
| **Cu**（Cu_percent） | % | **0.2%** | Practical 正文 |
| **Au** | **ppm** | **0.5 ppm** | Practical extra task |
| **Mo** | **%** | **约 0.05%** | Practical extra task |
| **Pyrite 晕圈**（Ss 字段） | % | **>1.5%**（不是经济指标，是分带指标） | Practical Figure 3 |

> ⚠️ **单位陷阱：Au 用 ppm，Mo 和 Cu 用 %。** 在 symbology 里设阈值时切不可混用。（见 §6）

### 3.5 📎 体积与吨位估算（材料只在 Final Analysis 里让你「用 measure 工具估」，未给公式）

> 📎 背景补充：一个 voxel layer 一旦筛出经济品位区域，标准的资源量估算是：

$$V = n_{\text{voxel}} \times (\Delta x \cdot \Delta y \cdot \Delta z)$$
$$T = V \times \rho_{\text{bulk}}$$
$$M_{\text{Cu}} = T \times \bar{g}$$

- **n_voxel** = 通过 data filter 后剩下的体元个数
- **Δx·Δy·Δz** = 单个体元的体积（m³）
- **ρ_bulk** = 矿石体积密度（tonnes/m³，微闪长岩约 2.7 t/m³）
- **ḡ** = 该区域的平均品位

**Practical 没有要求你算这个**，它只要求（Final Analysis）：

> "use the **measure tools** to estimate **how deep and wide the open cast pit would need to be**."

即用**量测工具**读出矿体的**深度范围与平面尺度**，从而定性判断露天坑规模。

### 3.6 📎 描述统计与偏态（Practical 要你填空并排序）

Practical 让你填 Cu_percent 的 **Mean / Median / Mode** 并排序，然后问「What do the relative values tell you about the resource?」

**材料没有给出具体数值**（需要你在 Data Engineering 里自己算），但**给出了答案的方向**——后文写道：

> "Note the shape of the histogram: **it is skewed to the right** which is what you probably predicted from calculation of mode, median and mean. Note: **Mode demonstrated that most of the dataset is below economic grade**."

**所以排序答案是：**

$$\textbf{Mean} > \textbf{Median} > \textbf{Mode}$$

**这是右偏（正偏，right-skewed / positively skewed）分布的标准特征。**

**地质含义（这才是这道题真正要的答案）：**

1. **绝大多数样品品位很低**（众数落在经济品位 0.2% 以下）；
2. **少数高品位样品把平均值拉高**（长长的右尾）；
3. → 这正是**低品位大吨位（low-grade, bulk-tonnage）**斑岩矿床的典型统计特征；
4. → **不能用平均品位来代表「典型矿石」**，因为平均值被极值绑架；
5. → 开采上意味着：**必须大规模采选 + 严格的截止品位筛选**，而不是追着高品位脉体挖。

---

### 3.7 关键图表的文字复原

> 以下几张图是本周必须**能自己默画出来**的。材料中的图像未被提取，下面依据文字与上下文复原。

#### 图 A：Isle of Mull 三连图 —— 2D → 2.5D → 3D（讲义 Slide 4–6）

**怎么画（画成左中右三格）：**

- **左格（2D）**：一个岛的轮廓，内部用不同颜色块填出地质单元（Mull 的火成杂岩、熔岩台地等），旁边画一套正交的 **x–y 坐标网格**。标注：「给我 (x, y)，我能找到唯一一点。」
- **中格（2.5D）**：同一个岛，但地质色块**贴合在起伏的地形上**（画成一张被山谷和山脊撑起来的「布」），视角是斜俯视。**关键**：在这块布上任选一点，向下投影到底面网格，仍然只对应一个 (x, y)。标注：「**surface existing in 3D space**，但仍是 2D。」
- **右格（真 3D）**：画一个**立方块**（地下岩体），侧面用不同颜色的层理/矿体表示，**块被切开一角**露出内部的分层。标注：「同一 (x, y)，沿 z 有多个不同的值 → **volume**。」

**三格底下写一行判据：** 「(x, y) → 唯一值 ? 2.5D : 3D」

#### 图 B：2.5D 表达不了什么（📎 本图为背景补充，材料未画，但它是理解 §2.1 的最好工具）

> 📎 背景补充：画一张**侧视剖面**（横轴 x，纵轴 z）：

- 画一条从左到右的地形线，中段做出一个**悬崖倒悬（overhang）**：崖壁向外突出，下方内凹。
- 在悬崖正下方的某个 x₀ 处画一条**竖直虚线**：这条线**穿过地形线三次**（崖顶、突出部下缘、内凹底部）。
- 在图旁写：「**DEM 只能存一个 z(x₀)** → 它必须在三个交点里挑一个，其余两个信息永久丢失。」
- 再在地形线下方画一个**洞穴（空腔）**：DEM 对它**完全无感**，因为洞穴不在表面上。
- 右侧画同一个剖面的 **voxel 版本**：网格化的小方块，空腔处的体元赋「air/void」类别，倒悬处三段实体分别有各自的体元。标注：「voxel 能表达，DEM 不能。」

#### 图 C：垂直基准剖面图（讲义 Slide 10，**本周最重要的一张图**）

**从下往上画四条线（横向都是波浪/曲线，纵向拉开距离）：**

1. **Reference ellipsoid（参考椭球面）**——画成一条**光滑平缓**的曲线（几乎是直线），标 "Reference ellipsoid"。
2. **Geoid（大地水准面）**——画在椭球面上方或下方**起伏波动**的一条曲线（波动幅度要比椭球明显，但比地形小得多）。在海洋段标 "**Ocean**"，说明 geoid ≈ 海面。
3. **Topographic surface（地形面）**——最上方一条**剧烈起伏**的线，画出一座山，山顶插一个 **trig pillar（三角点石柱）** 的小方尖（讲义配的是 **Mam Tor trig pillar** 照片）。

**再画三个箭头（这是本图的全部信息量）：**

- 从 **ellipsoid → topographic surface**，垂直于椭球面，标 **h = Ellipsoid height**（GPS 测的）。
- 从 **ellipsoid → geoid**，标 **N = Geoid height**（可正可负）。
- 从 **geoid → topographic surface**，标 **H = Orthometric height**（地图上的海拔）。

**在图上补一行式子：H = h − N。**

**还要标出老师口头强调的那点：** 在山顶处画两条**方向略有不同**的细虚线——一条垂直于椭球面，一条垂直于 geoid（因为 geoid 起伏，法线方向不同）。旁注：「measurement is defined **perpendicular to the reference system** → 不同基准给出不同的 z，甚至不同的 x, y。」

#### 图 D：Geoid 异常世界图（讲义 Slide 9）

画一个地球半球（面向欧洲—印度洋一侧），用**红—蓝发散配色**：

- **欧洲**区域涂**红**（gravity high），旁注「dense crust + deep Moho → excess mass」。
- **印度洋、印度南端外海**涂**深蓝**（gravity low），旁注「Indian Ocean Geoid Low，N ≈ −106 m，hot low-density mantle plumes (Pal & Ghosh, 2023)」。
- 图例：**red = gravity high / blue = gravity low**。

#### 图 E：Pixel → Voxel（讲义 Slide 11）

**左半边**：画一个 5×5 的正方形网格（raster），随手涂几格不同灰度；在其中一格上引出标注：「**pixel**：x, y + descriptors (R, G, B / height)」。

**右半边**：画一个由小立方体堆成的**大立方体**（例如 5×5×5），采用等轴测视角；把前表面和顶面的小方块画出来，右上角切掉一角显示**内部也是实心的小方块**；引出标注：「**voxel**：x, y, **z** + descriptors (class / time / density / porosity)」。

**中间画一个大箭头，写 "+ z"。** 底下一行：「voxel layer = 3D raster」。

#### 图 F：半变异函数图（Practical Figure 1 + Figure 2 合并）

**坐标轴：** 横轴 = **Lag distance（distance between data points）**；纵轴 = **Semi-variance**。

**曲线：** 从纵轴上一个**大于 0 的截距**出发，先陡后缓地上升，最后**变平**成一条水平渐近线。

**标注四个量：**

- **Nugget**：曲线与纵轴交点的高度（画一小段双箭头，从原点到截距）。
- **Sill**（📎 材料未标，自行补）：水平渐近线的高度。
- **Partial sill**（📎）：sill − nugget。
- **Range**：曲线开始变平处对应的横坐标（画一条竖直虚线下到横轴）。

**EBK3D 版（Figure 2）在此基础上加两样：**

- **一簇蓝色曲线**（不是一条）——「a large number of semi-variograms (blue lines)」，代表多轮模拟产生的众多模型；
- **一片蓝色十字**——「empirical (experimental) semi-variances plotted as blue crosses」，代表按 lag distance 与方向分箱后的实测值。

**旁注：** 「簇的宽度 = 不确定性。EBK 不需要你手动拟合模型。」

#### 图 G：斑岩铜系统剖面（讲义 Slide 24–27 + Practical Figure 3）

**画一张纵剖面（横轴几公里宽，纵轴 0 到 −7 km）：**

1. **底部（−7 至 −1 km）**：一个**上凸的岩株/岩浆房**（涂橙色），标 "shallow magmatic intrusion (1–7 km)"，标 "**microtonalite**"。
2. **岩浆房顶部**：画密集的**放射状/网格状裂隙**（hydraulic fracturing / frack），标 "high pressure fluids **frack** the top of intrusion and country rock"。
3. **紧邻岩体顶部与边缘**：涂**蓝色的中心带**，标 "**Cu core > 0.2% Cu**，chalcopyrite，**disseminated + veinlets**"（Practical Figure 3 的蓝色）。
4. **蓝色核外围**：涂**粉色环带**，标 "**pyrite halo > 1.5%**"（Practical Figure 3 的粉色）。
5. **上部贯穿到地表**：画一到两个**垂直的角砾岩筒**（breccia pipe），画成充填角砾的漏斗/柱体，标 "**phreato-magmatic explosion breccia pipe**，enriched in Cu, As, Au, Sn — **Glasdir mine**"。
6. **近地表（0 至 −100 m）**：画一条水平的**表生富集带（supergene blanket）**，用向下的箭头表示 "O₂-rich meteoric water **leaches** metals"，再用向下汇聚的箭头表示 "**re-deposit in deeper reducing conditions → >2% Cu**"。
7. **地表**：画泥炭沼泽（peat bog）与 **turf mine**，标 "native copper + gold, 1824–1865"；地表另标 **Sea Pinks / Sea-Campion** 作生物指示。

**这张图就是 Practical 里 voxel 模型应当呈现出的形状——画完再去看你的 3D 结果，能直接对照。**

#### 图 H：右偏直方图（Practical Results 一节）

横轴 **Cu_percent**，纵轴 **frequency**。画一个**峰紧靠左侧、右侧拖出长尾**的分布。

在横轴上从左到右依次标：**Mode**（峰顶）、**Median**、**Mean**（三者依次右移）。在 **0.2%** 处画一条**红色竖直虚线**，标 "**economic cut-off**"，并注明「**Mode 落在这条线左侧 → most of the dataset is below economic grade**」。

**这张图就是 Practical 里 voxel symbology 面板上显示的那个直方图，也是 data filter 滑块所依据的分布。**

---

## 四、课堂补充

> 本周 transcript 共 5,353 词，是三份材料里信息密度最高的一份。以下**只收录讲义 slide 上没有、或讲义写得远不如口头清楚的内容**。凡讲义已有的一律不重复。

### 4.1 课程结构层面的信息

**① 这是一次客座讲座。** 老师开场：

> "So this is my **one and only appearance for Geospatial** other than the practical that's associated with this **on Friday**. So I think **Ray Burgess has put in all the groundwork** and I'm just coming in."

**含义（对复习很实用）**：本周的讲课风格、术语习惯与前八周不同（Rufus Brunt 是石油/沉积构造背景，讲得偏资源地质）。**如果发现本周某些说法与前面几周略有出入，以课程负责人 Ray Burgess 的讲义为准**（例如 raster/vector 的口误，见 §6）。

**② 本周是最后一次新内容。** 老师现场不确定后面还有没有课（"Is this your last lecture in Geospatial?... Who knows?"）——结合仓库结构，W10 是 course review。

**③ Lecture 与 Practical 之间隔了几天。** 讲座在**周二（21-Apr）**，practical 在**周五**。老师因此特意在 lecture 末尾（Slide 18 起）花了近一半时间**给 practical 做背景铺垫**：

> "I don't get an option to introduce you to a linked practical, so I'll do that now."

**→ 复习提示：Slide 18–32 的全部内容（关键金属、斑岩、Coed-y-Brenin 采矿史）都是 practical 的前置知识，不是独立的知识点。**

### 4.2 概念讲解上比讲义更清楚的地方

**① 「电子游戏 = GIS 程序」这个类比**（讲义完全没有）：

> "You're interacting with topography. You're moving around a spatial world. **So a computer game is essentially a GIS program.**"

这个类比之所以有用：它把「什么算 3D」从抽象定义拉回到**你能不能在第三维上移动/取值**这个操作性判据。

**② 体数据「看不见内部」的困境**（讲义只字未提，但它解释了后面所有可视化手段）：

> "if you've got volumetric data, **you can only see the edges of it. You can't see what's going on inside it.** So in order to make it useful, we need to have ways of **interrogating** it, ways of **slicing it up**."

> "you often have to **subsample it into 2D** in order to be able to visualize it properly."

**→ 一句话总结本周可视化哲学：三维数据的价值在于「存」，但要「看」就必须降回二维。**

**③ 为什么不同坐标系给出不同的 z**（讲义只给结论「All these systems will produce different z values」，机制全在口头）：

> "our measurement position is defined effectively **perpendicular to the reference system** that we're using."

**④ 「坐标系未知」是最坏情况**（讲义没有这句，但它是实战中最值钱的一条）：

> "data with an **unknown coordinate system is your worst case scenario**."

**⑤ 地下数据为什么必须插值**（§2.5 整节都只在转写里）。

### 4.3 讲义没有的历史与轶事（三则，都很可能成为记忆抓手）

**① 牛顿的两口井思想实验**（详见 §2.2.3）。这是全场唯一一段完整的科学史推理，**建议整段记住**——它把「地球为什么是扁的」从记忆变成了推理。

**② 英国殖民时期的三角测量精度。** 讲义只提 OSGB36 和 trig pillars，口头补了一段令人印象深刻的对比：

> "colonial UK did this all over the world. So the initial mapping of **India** and the area around that started in **Bombay**, as it was at the time, and then moved outwards. And you'll find that the accuracy that they were involved with at these times means that the measurements they took in **northern India were actually only 8, 10 metres out compared to modern satellite GIS measurements** that are conducted today. So just the accuracy involved with these measurements is quite impressive."

**要点：19 世纪纯光学三角测量，跨越整个印度次大陆后的累积误差只有 8–10 m。** 这解释了为什么 OSGB36 这类「传统基准」在今天仍然可用。

> ⚠️ 史实校正：**印度大三角测量（Great Trigonometrical Survey）始于 1802 年的 Madras（马德拉斯，今 Chennai）附近的 St. Thomas Mount，不是 Bombay。** 见勘误表。

**③ Ordnance Survey 的三角测量网。** 老师描述 OSGB36 的建网过程（讲义只有一行）：

> "we've got Newlyn and then we have a set of **triangulation pillars** which expand out from Newlyn. So it produces a **triangular irregular network grid**, which expands from Newlyn and covers the whole rest of the country. So in those early days, the sort of cartographers... would have gone to these individual trig pillars and **sighted to the next trig pillar**. So they would have worked out the **orientation, direction and height** of the trig pillars that they could see from the trig pillar that they were at."

**⚠️ 强烈注意用词陷阱：** 他这里说的 "triangular irregular network" 指的是**实地三角测量网**，**不是 GIS 里的 TIN（Triangulated Irregular Network，一种表面数据模型）**。两者名字几乎一样，含义完全不同。（见 §6 易错点）

**④ RTK 的精度。** 讲义只说 OS GPS network 系于 ETRS89，口头补了用途：

> "if you're doing live **RTK, real-time kinematic**, GPS measurements, which get you down to sort of **millimetre accuracy**, then they're tied into this GPS network."

**→ 记住这个层级：手机 GPS（WGS84）≈ 米级；RTK（接入 OS GPS network / ETRS89）≈ 毫米级。**

### 4.4 关键金属与采矿伦理（Slide 19–22 的口头展开）

这一整块是 lecture 的**价值判断骨架**，老师讲得比 slide 详细得多，而且**最后要求学生表态**，很可能出现在报告或讨论题中。

**① 为什么净零转型反而更依赖采矿：**

> "the general idea is that **making energy without burning oil and gas and coal requires other elements**. And these are other elements which essentially **require geologists to find and extract**."

**两个必须记住的数字（讲义 Slide 22 + 口头都强调）：**

| 对比 | 倍数 | 来源 |
|---|---|---|
| 电动车 vs 燃油车的**矿物投入** | **6×** | IEA, 2024 |
| 海上风电场 vs 燃气电站（**按 MW 计**）的**矿物资源需求** | **13×** | IEA, 2024 |

老师的强调：「**six times more mining has to take place in order for your car to work**」。

**② 三种关键金属的用途（口头比 slide 系统）：**

| 金属 | 用途 |
|---|---|
| **Copper (Cu)** | 「all things that use electricity」——电机的**铜绕组**、风机的**铜绕组**、所有发电机构、电网 |
| **Cobalt (Co)** | 锂离子电池的**稳定性** |
| **Nickel (Ni)** | 锂离子电池的**阴极（cathode）**；老师补充：「important for making a **stable battery**, one that **doesn't burst into flames if you overcharge it**」 |

讲义 Slide 19 另列了 IEA 的需求分项：**Electricity networks、Grid storage batteries、Electric vehicles、Wind、Solar PV、Other low-energy power generation、Other uses**。

**③ 人权与环境代价（讲义 Slide 20–21 + 口头）：**

**Cobalt / DRC：**
- 「'**Blood cobalt**' comes from **DRC**（刚果民主共和国）」
- 「**Apple, Tesla, Samsung and Microsoft** all implicated in cobalt supply chain that extracts minerals using **slavery and child labour**」
- 毒理：**heart, thyroid, liver, and kidney problems**（心脏、甲状腺、肝、肾）
- 老师补充：手工开采（相对于「modern mechanised systems」）**危害尤其严重**。

**Nickel / 印尼：**
- 「Rain forest destroyed in **Sulawesi and Maluku** to access nickel」
- 「Some large scale mining operations are **illegal**」，后果主要来自 **poor control of waste products and drainage**（废料与排水控制不力）
- 毒理：**cardiovascular and kidney diseases, lung fibrosis, lung and nasal cancer. May disturb the human genome.**
- 老师补充：「a lot of these operations in the **back end of beyond, where they're not really visible**, are essentially illegal」——**偏远 = 不可见 = 无监管**。

**④ 老师抛出的两个价值问题（讲义 Slide 21、22 各一个）：**

> "**Is it better for critical mineral extraction to take place in countries with robust environmental policy and government accountability?**"
> "**Should the UK aim for Cu self-sufficiency?**"

**→ 这两个问题 + Slide 32 的「Would you dig up Eryri (Snowdonia)?」构成一个完整的论证链：**
承认需求上升 → 承认现有供应链有严重伦理与环境问题 → 那么把开采搬到监管健全的国家（如英国）是否更负责任？→ 但那意味着要挖开自己的国家公园。**没有标准答案，但论证结构必须完整。**

### 4.5 Coed-y-Brenin 的口头细节

**① 学生认得这个地方——因为山地自行车：**

> "It's sort of famous for its **mountain biking**. Is that why you've been there? Yeah, it's good fun. So I think the **black trail** goes around here."

（Coed-y-Brenin 是英国最著名的山地车中心之一，就在拟议的矿区上方——这正是 Slide 32 那个问题的现实张力所在。📎 该背景为常识补充。）

**② 具体位置：** 「the **Afon Wen** up here and **Capel Hermon**, which is over in the background here」——目标区域在 **Capel Hermon**（转写作 "Cabell-Herman"/"Cappel Herman"，ASR 误写）。钻孔数据来自 Capel Hermon 之下。

**③ 1970 年代勘探的商业动机（讲义只写「Series of exploration wells drilled in the 1970s」）：**

> "they were investigating whether or not Coed-y-Brenin is a **potential copper mining site**. So they were kind of interested in **the geometry of it, the extent and the grade** of copper, **what would be the return on their investment** if they were to dig it up."

**→ 这三个词（geometry / extent / grade）正好就是 practical 三个阶段的目标。**

**④ 结论：1970 年代认定不值得开采。**

> "In the 1970s, they considered it **not worthy of an extraction**. But I'd be interested to hear your opinion."

（📎 补充：铜价、选矿技术与净零需求在 50 年间都变了，这正是重新评估的理由——老师暗示了这一点但没说满。）

**⑤ 1915 年关停的完整因果链（口头远比 slide 详细，是很好的「采矿外部性」案例）：**

> "after they'd removed the copper from the ore, **crushed the ore**, removed the copper, what was left, they just sort of **dumped it into the valleys** and the rivers **took it away**. And in the rivers, it sort of **ruined any fly fishing** or any sort of inland fishing... And **offshore**, all this sort of extra **sediment** and particularly the sort of **acidic, sulphide-bearing sediments** effectively caused a **collapse in the fisheries**. So **it affected other industries. So it was forced to shut down in 1915.**"

**要点：矿山不是因为矿采完了才关，而是因为对**其他产业**（渔业）造成的外部性引发了地方抗议。** Practical 的说法互补：「Closure was partly forced by **local campaigns organised to stop degradation of salmon fisheries**」。

> 📎 背景补充：这里的机制是 **AMD（Acid Mine Drainage，酸性矿山排水）**——硫化物（黄铁矿）暴露氧化产生硫酸并释放重金属。材料没有点这个名词，但这是标准术语，值得一并记住。

**⑥ Turf mine（泥炭矿）的机制（口头解释比 slide 完整）：**

> "there were sort of **redox conditions** within the turf mine, particularly sort of **rotting vegetation, which produces reducing conditions**, which led to a sort of **precipitation of copper, quite high concentrations of native copper**, where they just effectively **dug up the turf and burnt it** in order to extract the copper."

**→ 这是 supergene 过程的一个极端局部版本：氧化的富铜地下水 → 遇到泥炭的强还原环境 → 直接析出自然铜。**「把泥炭当矿石烧」是全场最反直觉的细节。

**⑦ Sea Pinks 作为找矿指示植物：**

> "these are pink flowers, known as **sea pinks**. You get them around the coast because they're **metal tolerant**... But they also **thrive above metal deposits** as well. So if you see lots of these when you're wandering around Wales, **it's probably because you're on top of some kind of sulphide deposit**."

**→ 这是「生物地球化学找矿（biogeochemical prospecting）」的教科书例子。** 📎 术语为补充。

### 4.6 地质讲解中口头补充的要点

**① 铜金为什么会被富集——一条完整的化学逻辑链**（讲义 Slide 24 是要点式，口头是连贯叙述）：

> "as those sediments, basically **water, which is held in the down-going slab**, are heated and driven off, we get these **water-rich or hydrous melts, also containing a lot of oxygen**. Now, as this material... go through the **mantle wedge and the lower part of the crust**, they **deplete sulfides**... **copper and gold have an affinity for these sulfides**. So as these sulfide-rich waters pass upwards and through, **they pick up copper and gold**."

> "as they ascend and start solidifying... these **sulfides are not compatible. They're incompatible with these magmas.** So they tend to either be **driven off in hydrothermal fluids** or form sort of **very late-stage mineralization**."

**→ 关键机制词：affinity（亲和性）+ incompatible（不相容）。** 硫化物对 Cu、Au 有亲和性 → 收集金属；硫化物对硅酸盐熔体不相容 → 被排出到热液中 → 于是金属跟着热液走到浅部沉淀。**这两步是斑岩成矿的核心。**

**② 老师对斑岩定义的一句话总结：**

> "that's essentially what a porphyry deposit is. It's these sort of **ore-bearing hydrothermal fluids which are driven off these systems**."

**③ 英国的斑岩很少：**

> "there's a lot of porphyries around the world, **not many in the UK**, but we do have a few."

（讲义 Slide 22 另举了 **Alderley Edge** 的 Engine vein 中的 **malachite（孔雀石）与 azurite（蓝铜矿）** 作为英国铜矿化的例子。）

**④ 矿化的两种赋存方式（口头强调）：** 除了裂隙充填，还有 **disseminated**——「just basically sitting in the **pore spaces** of these sort of country rocks and also partly in the magmatic bodies」。**这一点直接决定了 practical 的插值是有意义的**：如果铜只在极窄的脉里，钻孔点之间的插值就没有物理依据；正因为它是**浸染状、体积分布**的，克里金才成立。

### 4.7 关于评估与考试的信息

**本周 transcript 中老师没有给任何考试提示、作业要求或评分说明。** 唯一与「考核」相关的是：

- 讲义 Slide 2 的四条 **Intended Learning**（见 §1.3）——这是本周的官方范围。
- 课程整体考核（大纲）：**Set exercise 50% + Other（on-line test）50%**，**无期末笔试**。
- Practical 内嵌了**必须填写的题目**（mean/median/mode 填空与排序、"is this data display fit for purpose?"、"What type of intrusion is this?"、露天坑尺寸估算），**这些是 practical 的产出要求**。

> ⚠️ 材料未说明本周 practical 是否计入评分，也未给出提交要求。**不确定处不臆测。**

---

## 五、Practical 要点

**Practical 全称：** *Practical: 3D visualisation and analysis of critical mineral deposits beneath Coed-y-Brenin*（University of Manchester，Geostatistics: 3D visualisation）

> **本节写法说明：** 下面是一条**可照做的完整流水线**，工具与菜单一律保留 ArcGIS Pro 英文原名，括号内附中文。凡教程原文没有、由我补出的操作细节，一律以 **📎 背景补充** 明确标出。

### 5.0 任务目标与总览

**教程给出的 aims（原文）：**

> "Coed-y-Brenin was extensively drilled in the 1960 and 1970s to establish the extent of low grade copper mineralisation. Samples were taken from the wells and analysed for their metal content. This practical will use the **3D capabilities of ArcGIS** to **place the metal concentration values in their correct place below ground**. By completing **geostatistical analysis** of this extensive dataset you will be able to **visualise the extent of the copper deposit**."

**拆成三个阶段（这也是本 practical 的骨架）：**

| 阶段 | 做什么 | 核心工具 |
|---|---|---|
| **A. 建场景** | 建工程、设 XY/Z 坐标系、导入数据、转成 3D 场景、换用高分辨率地形 | `XY Table To Point`、`Convert > Local Scene`、Elevation Surfaces > Ground |
| **B. 把样品放到地下正确位置** | **这是全 practical 的关键难点**——井中深度 ≠ 海拔，必须通过表连接换算成绝对高程 | `Add Field`、`Add Join`、`Calculate Field`、`Display XY Data` |
| **C. 3D 地统计与可视化** | 描述统计 → 3D 克里金 → 转体元 → 按经济品位过滤 → 读矿体几何 | `Data Engineering`、`Geostatistical Wizard > Empirical Bayesian Kriging 3D`、`GA Layer 3D To NetCDF`、Voxel Layer symbology |

**前置假设（教程开篇原文）：**

> "I'm assuming that the class is familiar with **ArcGIS Pro and its operational environment**."

即：**不再教基础操作**（Contents pane、Catalog pane、Geoprocessing pane 的用法默认已会）。

---

### 5.1 阶段 A：建立工程与三维场景

#### 步骤 1 — 新建工程

1. 打开 **ArcGIS Pro**，**start a new map**（新建 Map 模板的工程）。
2. **保存位置必须满足两个条件**（教程明确提醒）：
   - **write permission**（有写入权限）
   - **enough disk space — about 250 MB**（约 250 MB 可用空间）
3. **工程名：`Coed-y-Brenin`**

> 📎 背景补充：在大学机房里，「有写权限」通常意味着**不要存到 C: 盘或网络只读盘**，应存到个人网络盘（如 P: 盘）或本地临时盘。教程强调这一点是因为后面 EBK3D + netCDF 输出会写入大量中间文件。

#### 步骤 2 — 设置坐标框架（**必须在导入数据之前做**）

**路径：** 在 **Contents Pane**（内容窗格）中 **右键点 `Map` → Map Properties**（地图属性）

**(a) General 选项卡：**
- **change map units to meters**（把地图单位改为米）

> 📎 背景补充：ArcGIS Pro 的 Map Properties > General 中，实际的选项名是 **Display Units**（显示单位）。「map units」严格说由坐标系决定（BNG 本身就是米），你能改的是显示单位。见勘误表。

**(b) Coordinate Systems 选项卡：**

**水平坐标系（Horizontal coordinate system）** — 点 **Current XY** 展开，逐层进入：

```
Projected Coordinate Systems  >  National Grids  >  United Kingdom  >  British National Grid
```

**垂直坐标系（Vertical coordinate system）** — 点 **Current Z** 展开，逐层进入：

```
Vertical Coordinate Systems  >  Gravity-related  >  Europe  >  EVRS2000
```

教程说明：「This is the **European Vertical Reference System**, which has many variants.」

点 **OK** 应用。

> ⚠️ **两处需要留神：**
> 1. **ArcGIS Pro 中该垂直坐标系的实际名称是 `EVRF2000`**（European Vertical Reference **Frame** 2000，WKID 5730），**不是 `EVRS2000`**。EVRS 是「系统」，EVRF 是其「实现/框架」。搜索框里输 `EVRF` 才找得到。见勘误表。
> 2. 📎 背景补充：**严格来说英国本土数据应使用 `ODN (Ordnance Datum Newlyn)`**（Newlyn 验潮站基准），EVRF2000 是欧陆基准，两者在英国有几十厘米的系统差。对本 practical（矿体尺度上百米）**没有实质影响**，但概念上应知道。
>
> 📎 若在 `National Grids > United Kingdom` 下找不到 British National Grid，可直接在 Coordinate Systems 选项卡顶部的**搜索框**里输入 `British National Grid`（EPSG/WKID **27700**）。不同 ArcGIS Pro 版本的文件夹层级略有差异（有的版本在 `National Grids > Europe` 下）。

**为什么这一步不能省：** 后面 `XY Table To Point` 要用 **Current Map (Map)** 作为坐标系来源；如果此时没设好，所有点会落到错误位置甚至跑到几内亚湾（0,0）。

#### 步骤 3 — 下载并解压数据

1. 从 **Canvas** 的 **3D Spatial Techniques** 模块下载 **`Practical_files.zip`**。
2. 解压，**Ensure that the folder structure is maintained**（**必须保持文件夹结构**）——教程解释原因：「so that **data files and spatial reference files remain linked together**」（数据文件与其空间参考文件必须保持在一起）。

**zip 包内容（四类）：**

| 文件 | 说明 |
|---|---|
| **`Coed-y-Brenin.img`** | **5 m 分辨率 DEM** |
| Aerial photographs | 覆盖 Coed-y-Brenin 的航空影像（多幅） |
| **`Well_positions.dbf`** | **井口位置**数据库表（在 `Well_Data` 文件夹内） |
| **`MetalGrade.dbf`** | **井下矿石品位**数据库表 |

> 📎 背景补充：`.img` 是 **ERDAS IMAGINE** 栅格格式；`.dbf` 是 **dBASE 表**格式（Shapefile 属性表用的就是它）。教程后文把 `MetalGrade.dbf` 称为 "the **geodatabase**"，这是**术语误用**——.dbf 是独立表（standalone table），不是地理数据库。见勘误表。
>
> 📎 「保持文件夹结构」具体指：栅格常带 `.aux.xml`、`.rrd`、`.ovr` 等伴随文件；shapefile 家族有 `.shp/.shx/.dbf/.prj`。**分开移动会丢投影信息（.prj）**。

#### 步骤 4 — 导入数据（三种不同做法，别混）

**路径：** 主功能区 **Map 选项卡 → Add Data**（逐个添加）

**(a) DEM：** 直接 `Add Data` 添加 `Coed-y-Brenin.img`。

**(b) 井位表：** 直接 `Add Data` 添加 `Well_Data` 文件夹内的 **`Well_positions.dbf`**。
→ 它会以 **data table（数据表）** 的形式出现在 Contents pane 中（**不是图层**，因为它还没有几何）。

**(c) 航空影像 — 走「组图层」流程**（教程专门给了不同做法）：

1. 在左侧 **Contents pane** 中 **右键 `Map` → New Group Layer**（新建组图层）
2. **右键该新图层 → Properties**，把名称改为 **`AerialPhotos`**
3. **右键 `AerialPhotos` 图层 → Add Data**
4. 定位到航空影像所在文件夹，**全选**（点列表最上一项，**按住 Shift**，点最下一项），点 **OK**

**教程给的理由（值得记住的实用技巧）：**

> "this is a simple way of putting the aerial photos in a separate folder. They can all be **switched on/off with a single click of the group layer visibility check box**."

**→ 组图层的价值：一个勾选框控制一批图层的显隐。** 在 3D 场景里这尤其重要——航空影像很占渲染资源，需要频繁整体开关。

#### 步骤 5 — 把井位表转成点要素（`XY Table To Point`）

**路径：** **Map 选项卡 → Layer 组 → `XY Table To Point`**
→ 屏幕右侧打开 **Geoprocessing**（地理处理）对话框。

**参数逐项：**

| 参数 | 值 |
|---|---|
| **Input Table** | 用输入框旁的箭头选 **`Well_positions`** |
| **Output Feature Class** | 自动填入默认名 **`Well_positions_XYTableToPoint`**（可保留） |
| **X Field** | **`BNG_X`** |
| **Y Field** | **`BNG_Y`** |
| **Z Field** | **`BNG_Z`** |
| **Coordinate System** | 选 **`Current Map (Map)`** ——「the simplest route」，直接沿用工程已设好的坐标框架 |

点 **Run**，然后 **Save your project**。

> ⚠️ **Z Field 是可选参数，但这里必须填。** 不填的话井口点会全部贴在 z=0，后面所有高程计算都失去基准。
>
> 📎 背景补充：ArcGIS Pro 中该工具在 **Map 选项卡 → Add Data 下拉 → XY Point Data**，或在 Geoprocessing 搜索框搜 `XY Table To Point`（属于 Data Management Tools > Features）。教程写的「Map 选项卡 Layer 组」在不同版本位置略有差异；**用搜索最稳**。
>
> 📎 `BNG_X / BNG_Y / BNG_Z` 中的 BNG = **British National Grid**，说明原始数据已经是英国国家格网坐标（米），与步骤 2 设的水平坐标系一致——**这就是为什么可以直接选 Current Map**。

#### 步骤 6 — 转换为三维场景（**Local Scene**）

**为什么要转：** 教程原文——

> "So far all data has been displayed in a **2D map framework**. To increase the usefulness of data interrogation and **allow exploration of the subsurface** the map needs to be **converted to 3D**."

**ArcGIS 提供两种场景：**

| 场景类型 | 教程给的适用条件 | 选哪个 |
|---|---|---|
| **Global Scene** | "national / very large scale datasets" | ✗ |
| **Local Scene** | "small scale projects" | ✓ **For our purposes Local scene will work best** |

> ⚠️ **教程这里的「scale」用反了。** 制图学中 **large scale = 小范围、细节多**（如 1:1,000）；**small scale = 大范围、概括**（如 1:1,000,000）。所以「national 数据集」应是 **small scale**，「local 项目」应是 **large scale**。教程写反了。**但结论（本练习用 Local Scene）是对的。** 见勘误表。
>
> 📎 背景补充 —— **两种 Scene 真正的技术差别**（教程没说，这是本周极易考的点）：
>
> | | **Global Scene** | **Local Scene** |
> |---|---|---|
> | 坐标系 | 必须是**地理坐标系**（WGS84 等），地球画成**球面** | 可用**投影坐标系**（如 British National Grid），地面视作**平面** |
> | 适用范围 | 全球 / 洲际 / 国家尺度 | 城市 / 矿区 / 单体尺度 |
> | 地下导航 | 支持有限 | **完整支持在地表以下自由导航** |
> | Voxel layer | 受限 | **voxel layer 需在 Local Scene 中使用** |
>
> **→ 本练习必须用 Local Scene 的真正理由有三条：①数据是 BNG 投影坐标；②研究区只有几平方公里；③要看地表以下的矿体。**

**转换的两步操作：**

1. **View 选项卡 → Windows 组 → `Reset Panes` → `Reset Panes for Mapping`**
   目的（教程原文）：「This will **close unused panes** and ensure that the **Contents and Catalog panes are open**」——关闭无关窗格，确保 Contents 与 Catalog 窗格打开。
2. **View 选项卡 → View 组 → `Convert` → `To Local Scene`**

结果：**ArcGIS 会用已加载的数据生成一个 `Map_3D` 窗口。**

> 📎 背景补充：`Convert` 是**转换**而非新建——原来的 2D `Map` 会被替换/转为 3D。若想同时保留 2D 与 3D 两个视图，应先复制地图（Catalog pane 中右键 Map > Copy，再 Paste）。教程未说明这点。

#### 步骤 7 — 三维场景中的导航（务必记熟，否则寸步难行）

| 操作 | 鼠标 |
|---|---|
| **Zoom（缩放）** | 滚动**滚轮**，或**按住右键**移动鼠标 |
| **Drag / Pan（平移）** | **按住左键**移动鼠标 |
| **Rotate（旋转）** | **按住中键（滚轮键）**移动鼠标 |

> 📎 背景补充：**Rotate 是 3D 场景里最重要的操作**——把视角压到接近水平（低倾角）才能看清地下体的深度关系。若中键不可用，可用键盘 **方向键 / A、D 键** 或场景左下角的 **navigator 控件** 旋转。教程未给替代方案。

#### 步骤 8 — 提高垂直分辨率（换掉默认全球地形）

**问题所在（教程原文）：**

> "ArcGIS uses a **default elevation model: `WorldElevation3D/Terrain3D`**. This model is based on **SRTM data (Shuttle Radar Topography Mission)**. It is the same **30 meter resolution** global database that Google Earth uses."

而你手上的 `Coed-y-Brenin` DEM 是 **5 m 分辨率**，精细 6 倍。但——

> "It is **currently displayed as a georeferenced raster image where pixel colour corresponds to height**."

**⚠️ 这是本步骤的核心概念：栅格被当成「一张彩色图片」贴在地上，它的高程数值并没有被场景用作地形。要让它真正抬起地表，必须把它放进 Ground（地面高程面）。**

**操作：**

1. 在 **Contents pane** 中找到 **`Elevation Surfaces`** → 其下的 **`Ground`** 分组。
2. **把 `Coed-y-Brenin DEM` 拖进 `Ground`** 里。
3. **取消勾选 `WorldElevation3D/Terrain3D`**，「to ensure you are using the **higher resolution DTM**」。

> 📎 背景补充（教程说法不够准确，见勘误表）：`WorldElevation3D/Terrain3D` **不是纯 SRTM**，而是 Esri 汇集多来源的**融合产品**（全球约 24–30 m，局部可达 1–3 m 甚至更细）；Google Earth 同样使用多来源数据，不能说「同一个数据库」。**但结论仍成立：默认全球地形远粗于本地 5 m DEM，必须替换。**
>
> 📎 一个图层可以**同时**出现在 Contents 的图层列表（作为可见的彩色栅格）和 Elevation Surfaces > Ground（作为高程源）中——两者用途不同，不冲突。

---

### 5.2 阶段 B：把样品放到地下的正确位置（**本 practical 的核心难点**）

#### 步骤 9 — 先犯一次「错」：直接用 Depth_m 当 Z

**操作：**
1. 添加 **`MetalGrade.dbf`**（教程称其为 "the geodatabase"，实为独立表）。
2. 用与步骤 5 相同的方式显示其 x, y, z 样品位置。
3. **Z 字段只能用 `Depth_m`**——因为「The data only contains the **depth below surface recorded by the driller (`Depth_m`)**」。
4. **"Don't forget to define the correct coordinate system."**（教程加粗强调）

**然后教程提问：**

> **QUESTION: is this data display fit for purpose?**
> "Turn off layers that mask your view of the xyz data and think about the **position of sample points in relation to the ground surface – are they correct?**"

**答案（务必自己想清楚，这是全练习的教学眼）：**

**不合格。** 因为 `Depth_m` 是**「井下深度」——相对于钻机台面（drill floor）量的相对深度**，而 ArcGIS 把它当成了**绝对高程**（相对于垂直基准面）。结果就是：**所有钻孔的样品都被挂在了同一个高度带上，完全无视各井口本身的海拔差异。**

教程随后点破了为什么这特别糟糕：

> "All data was recorded from the **same very local datum – the drill floor**. However **the drill floor moved from hill top to valley floor within the study area** so **this measurement is meaningless**."

**→ 在山顶打的井，其「深 100 m」处的绝对海拔，可能比山谷里打的井「深 20 m」处还要高得多。** 不换算就画，矿体的几何形状完全是错的。

**这一步与 §2.2 的 lecture 内容严丝合缝：垂直基准（vertical datum）选错，z 就没有意义。** Lecture 讲的是国家尺度的 datum 问题，practical 让你在一个矿区尺度上亲手踩一次同样的坑。

#### 步骤 10 — 新建 `Height_m` 字段

**路径：**

1. Contents pane 中 **右键 `MetalGrade` standalone table → Open**（打开属性表）
   教程提示：「The associated data table shows how data is arranged in **columns (Data fields)**。」
2. 点表格上方的 **`Field: Add`**（字段：添加）→ 进入 **Fields view**（字段视图），新建一行。
3. **逐项设置（教程强调「clicking enter to set each one」——每设一项要回车确认）：**

| 参数 | 值 | 教程说明 |
|---|---|---|
| **Field Name** | **`Height_m`** | 存放样品的绝对高程 |
| **Data Type** | **`Float`** | 教程写「values stored in the column will be numbers of up to **6 decimal places**」；并说「**Double** precision would be more precise, but also use **unnecessary memory**」 |
| **Number Format** | **`Numeric`** | 「define that the values are numeric」 |

4. **Save** 新字段——教程：「this option should be present in the **context sensitive menu in the main `Fields` menu**」（在 Fields 选项卡里点 Save）。然后**关闭 Fields view**。

> ⚠️ **`Float` 的描述不准确。** ArcGIS 的 **Float 是单精度浮点（4 字节）**，约 **7 位有效数字**——不是「6 位小数」。对于本例的高程值（如 `-123.456`，量级几百米），单精度足够；但**「6 decimal places」这个说法会误导**。见勘误表。
>
> 📎 背景补充：**加字段前必须确认表没有被 Join 占用、也没有正在编辑**，否则 Add 按钮可能灰掉。若 `.dbf` 是只读（文件属性或所在文件夹权限），也加不了字段——这也是步骤 1 要求「write permission」的原因之一。

#### 步骤 11 — 连接两张表（`Add Join`）

**为什么要 join（教程原文）：**

> "join the `Well_positions` and `Metal_Grade` tables to give access to **both the xyz position of each drill position and the down well depths**"

**→ 井口高程在 `Well_positions` 表里（`BNG_Z`），井下深度在 `MetalGrade` 表里（`Depth_m`），两者必须先拼到一起才能相加。**

**路径：** Contents pane 中 **右键 `MetalGrade` 表 → `Joins and Relates` → `Add Join`**

**参数：**

| 参数 | 值 | 说明 |
|---|---|---|
| **Input Table** | **`Metal_Grade`**（first database） | 被连接的目标表 |
| **Input Join Field** | **`Borehole`** | 「this field is **common to both databases** and will be used to 'join' the tables」——**两表共有的钻孔编号，是连接键** |
| **Join Table** | **`Well_Positions`**（related database） | 提供井口坐标的来源表 |
| **Join Table Field** | **`Borehole`** | 同名连接键 |
| **Join Operation** | **`Join one to first`** | 一对一（只取第一条匹配记录） |

**点 `Validate Join`（验证连接）：**

> 教程原文：「(there is an **error as one of the databases has no index**, but **this is not a problem**), click **OK**」

> 📎 背景补充：这条提示实际上是 **warning（警告）而非 error**，含义是**连接字段上没有属性索引**，会导致连接速度变慢（对本数据量无感）。若想消除，可用 **`Add Attribute Index`** 工具在 `Borehole` 字段上建索引。教程称之为 "error"，措辞不准确。

**连接成功的标志（教程原文）：**

> "Joining the databases has **populated the BNG x, y and z fields for the drill position for each of the borehole positions**."

即：`MetalGrade` 表现在多出了 `Well_positions.BNG_X / BNG_Y / BNG_Z` 这几列。

> ⚠️ **注意 join 之后字段名会带前缀**：`MetalGrade.Depth_m`、`Well_positions.BNG_Z`。下一步的表达式必须用带前缀的全名。

#### 步骤 12 — 计算绝对高程（`Calculate Field`）

**路径：**

1. **右键 `Height_m` 字段的表头 → `Calculate Field`**
2. 在对话框底部找到 **`MetalGrade.Height_m =`**（教程：「We will fill this with values selected from this window.」）
3. 在左侧 **Fields** 列表中找到 **`Well_positions.BNG_Z`**，**双击**把它加入表达式
4. 加上 **`+`**，再双击加入 **`MetalGrade.Depth_m`**

**最终表达式（教程原文，加粗）：**

```
Metal_Grade.Height_m = !Well_Positions.BNG_Z! + !Metal_Grade.Depth_m!
```

5. 点 **OK**，并 **save the table**。

**验算方法（教程给的自检，务必执行）：**

> "A visual inspection of the new content of the field should show **decreasing height corresponding with increasing well depth**."

**→ 井越深，`Height_m` 应该越小。**

> ⚠️ **符号陷阱（本步骤最容易出错的地方，也是最值得考的地方）：**
> 表达式用的是 **加号（+）**。这意味着数据中的 **`Depth_m` 必须是负值**（例如 −50 表示井下 50 m）。
> **如果你打开表发现 `Depth_m` 是正数**，那么这个加法会把样品放到井口**上方**的空中，必须改成：
> ```
> !Well_Positions.BNG_Z! - !Metal_Grade.Depth_m!
> ```
> **判据就是教程给的那句自检：先算几行，看 `Height_m` 是不是随深度递减。递增就说明符号反了。**
> 📎 教程没有明说 `Depth_m` 的符号约定 —— 这属于教程留白，动手前必须自己查表确认。

> 📎 背景补充：`Calculate Field` 的表达式语言默认是 **Python 3 (Arcade / Python 可选)**，字段名两侧的 **`!` 感叹号** 是 Python 解析器的字段引用语法。若切换成 Arcade，语法变成 `$feature.BNG_Z`——**教程用的是 Python 语法**，不要混用。

#### 步骤 13 — 移除连接（**不做这一步就画不出点**）

**教程原文：**

> "right click on the `Metal-Grade` table and select **`Joins and Relates` > `Remove All Joins`**. This is a **necessary step because joined tables cannot be plotted**."

**→ 带 join 的表不能被 `Display XY Data` 绘制。必须先断开。**

**⚠️ 断开 join 会不会丢掉刚算的值？** 不会——`Height_m` 是**你自己在 `MetalGrade` 表里新建的实体字段**，值已经物理写入；被移除的只是那些**虚拟拼接过来的** `Well_positions.*` 列。

**教程给的保险做法（万一出问题）：**

> "In case of error, **export your new table** with the additional `Height_m` column:
> Right click on `Metal_Grade` in the Contents pane. Select **`Data` > `Export Table`**. Provide a logical name for your output table and select OK. Arc should add this new table to your project – **if not manually add it using `Map` > `Add data`**."

> 📎 背景补充：**建议无条件执行这一步导出**，不要等出错。原因：`.dbf` 表在 join 状态下计算字段有时会把值写进「连接后的视图」而非源表；导出成 **file geodatabase table** 可以彻底固化结果，也避开 `.dbf` 的诸多限制（字段名 ≤10 字符、无 NULL 支持等）。

#### 步骤 14 — 用正确的高程重新绘点

**教程原文：**

> "Select your modified table and select **`Display XY Data`**. Use your calculated **`Height_m`** field for **Z values** and **the correct coordinate system**. **Disable / delete the old copper x,y values to avoid confusion.**
> (Note – it is possible the `Height_m` field became **linked to the original `Metal_Grade` table** – check here if it is missing)."

**参数回顾：**

| 参数 | 值 |
|---|---|
| X Field | `BNG_X`（📎 教程未重复列出，但显然仍需 BNG 平面坐标） |
| Y Field | `BNG_Y` |
| **Z Field** | **`Height_m`** ← 关键改动 |
| Coordinate System | **`Current Map (Map)`** |

**⚠️ 一定要把步骤 9 生成的旧点图层关掉或删掉**，否则场景里会有两套位置矛盾的点，判读时必然混乱。

#### 步骤 15 — 按铜品位符号化

**路径：** Contents pane 中 **右键 `MetalGrade` 点图层 → Symbology**

**设置：**
- 启用 **`Graduated Colors`**（分级色彩）
- **Field: `Cu_percent`**

**判读（教程原文）：**

> "In the resultant colouring of feature points, the **warm colours represent higher copper grade**. This is a **basic view of the ore body**. To get a better view, **geostatistical methods can be employed to predict a 3D volume (filling in the space between point measurements)**."

**→ 到这一步你已经有了「地下正确位置上的彩色点云」，但点与点之间还是空的。下一阶段就是把这些空隙填起来。**

> 📎 背景补充：Graduated Colors 的默认分级方法是 **Natural Breaks (Jenks)**，默认 5 级。对右偏严重的品位数据，可考虑改用 **Quantile** 或 **Manual Interval**（把 0.2% 设为一个断点），能更直观地看出经济矿体的位置。教程未提。

---

### 5.3 阶段 C：三维地统计分析与可视化

#### 步骤 16 — 描述统计（`Data Engineering`）

**路径：**
1. 在 Contents pane 中**选中 metal grades standalone table**
2. **`Analysis` 选项卡 → `Workflows` 组 → `Data Engineering`**
3. 把 **`Cu_Percent`** 字段**拖进分析窗口**，点 **`Calculate`**

**要填的三个统计量（教程留空，需自己读数）：**

| 统计量 | 教程给的定义 | 你的值 |
|---|---|---|
| **Mean** | "the **arithmetic mean** of Cu_percent values" | ______ |
| **Median** | "the value that lies **centrally in an ordered list** of Cu values" | ______ |
| **Mode** | "the value that occurs **most frequently**" | ______ |

**排序题：** `________ > ________ > ________`

**答案：`Mean > Median > Mode`**（依据后文「the histogram... is **skewed to the right**」，见 §3.6）

**教程的思考题：**

> "**What do the relative values of mean, mode and median tell you about the resource?**"

**答案要点（§3.6 已展开）：** 右偏分布 → 绝大多数样品品位低（**mode 落在 0.2% 经济品位之下**）→ 少数高品位样本抬高均值 → 典型的**低品位大吨位斑岩矿床** → 不能用均值代表典型矿石 → 必须大规模采选并严格套用截止品位。

> ⚠️ 材料**未给出具体数值**，需自己在 Data Engineering 里读。笔记中不臆造数字。

#### 步骤 17 — 3D 克里金插值（`Empirical Bayesian Kriging 3D`）

**教程的衔接句：**

> "You have previously used **2D geostatistical methods**（W04/W05）to investigate relationships between data points. **The same methods can be expanded into 3D.**"

**路径：** **`Analysis` 选项卡 → `Geostatistical Wizard`** → 选择 **`Empirical Bayesian Kriging 3D`** 工具

**⚠️ 授权提醒（教程原文）：**

> "(**Licensing errors** will be caused if **3D Analyst** and **Spatial Analyst** are not enabled)."

> ⚠️ 这条说法不对。**`Empirical Bayesian Kriging 3D` 属于 `Geostatistical Analyst` 扩展模块**，后续的 `GA Layer 3D To NetCDF` 同样属于 Geostatistical Analyst。**真正必须启用的是 Geostatistical Analyst**；3D Analyst 与 Spatial Analyst 是三维显示与栅格分析的常见搭配，但不是 EBK3D 的授权来源。见勘误表。
> 📎 启用路径：**`Project` 选项卡 → `Licensing` → `Configure your licensing options` → 勾选 `Geostatistical Analyst`（及 `3D Analyst`、`Spatial Analyst`）→ 重启 ArcGIS Pro**。教程未给路径。

**输入参数（教程原文）：**

| 参数 | 值 |
|---|---|
| **Source Dataset** | 你新建的 **`Metal_Grades XYTableToPoint` 点要素**（**必须是含高程的那一份**，即步骤 14 生成的） |
| **Elevation Field** | **`Height_m`** |
| **Data Field** | **`Cu_percent`** |

点 **Next**，然后：

> "**Continue through the dialogue using defaults for all options.**"（后续所有页面一律用默认值）

**要看的东西：**

> "Take note of the **semi-variogram**, which displays the **results of data correlation**."

**→ 半变异图的读法见 §3.3 与图 F。** 重点看：**nugget 有多高**（测量误差与天然随机性有多大）、**range 有多远**（铜品位的空间自相关能延伸多少米——这直接决定钻孔间距是否足够）、**蓝色曲线簇有多宽**（不确定性）。

> ⚠️ **别跳过这一页。** 教程虽然让你全用默认，但半变异图是**唯一一处能判断插值是否可信**的地方。若曲线几乎水平（没有明显 range），说明数据间没有空间自相关，**克里金结果就没有意义**。

> 📎 背景补充：EBK3D 的关键默认参数（教程只提了 subset size）：
> - **Subset size = 100**（Figure 2 明写）
> - **Overlap factor**、**Number of simulations**（默认 100）、**Order of trend removal**、**Semivariogram model type（默认 Power）**、**Elevation inflation factor**（3D 专有，用于校正垂直方向与水平方向尺度不同的问题）
> 这些教程都没有列。**`Elevation inflation factor` 尤其重要**：钻孔在垂直方向采样密（每几米一个样），在水平方向稀（井距几十上百米），若不做各向异性校正，插值会在垂直方向过度平滑。ArcGIS 默认会自动估计该因子。

#### 步骤 18 — 浏览结果（水平切片）

**教程原文：**

> "3D kriging generates **horizontal slices** from the data. The results can be browsed using the **vertical slider to the right of the main screen**."

**→ 结果暂时还是「一叠可以上下滑动浏览的水平面」，不是体。** 用右侧竖直滑块上下移动，观察铜的高值区在不同深度上的位置与形状变化。

#### 步骤 19 — 导出为体元图层（`GA Layer 3D To NetCDF`）

**教程原文：**

> "To view in 3D we need to **convert the Krig results to a Voxel Layer**."
> "**Right click** on the **Empirical Bayesian Kriging 3D results** in the contents pane. Select **`Export to NetCDF/Voxel`** tool. Navigate to your file location and **name it `Cu_voxels`**."

**⚠️ 教程特意给的坑：**

> "**Note: Output of the GA Layer to NetCDF tool is not always automatically added to the local scene.** You may need to use **`Add Data`** to add it to your local scene as a **Multidimensional Voxel Layer**."

**→ 导完后如果场景里什么都没变，不要以为失败了。手动 `Add Data` 把 `Cu_voxels.nc` 添加进来，类型选 `Multidimensional Voxel Layer`。**

> 📎 背景补充：
> - 工具的完整名称是 **`GA Layer 3D To NetCDF`**（Geostatistical Analyst Tools → Working with Geostatistical Layers）。右键菜单里显示为 `Export` 下的子项。
> - 输出格式 **netCDF（`.nc`）** 是多维科学数据的通用格式（气象、海洋领域标准格式）。**voxel layer 在 ArcGIS Pro 中的物理载体就是 netCDF。**
> - 该工具有 **`Output cell size`（输出体元大小）** 之类的参数会影响体元数量与文件大小——**体元越小越精细，但渲染越卡**（见步骤 22 的性能问题）。教程未提这些参数，全用默认。

#### 步骤 20 — 按经济品位过滤（`Data Filter`）

**背景（教程原文）：**

> "The **ore handling facilities are unable to process ore containing less than 0.2% grade**. This is considered the **economical limit**, returning approximately **2 kg of copper per tonne of ore mined**."

**操作路径：**

1. 在 Contents pane（file tree）中**选中 voxel 图层** → 顶部出现**对象专用工具条（object specific toolbar）**
2. 点 **`Voxel Layer`** 选项卡
3. 在 **`Drawing` 组**中点 **`Symbology`**，打开体元图层的符号系统面板

**面板内容（教程原文）：**

> "Display is based around the **data histogram for copper grade**. Note the shape of the histogram: **it is skewed to the right** which is what you probably predicted from calculation of mode, median and mean. Note: **Mode demonstrated that most of the dataset is below economic grade.**"

4. **在直方图上方选择 `Data Filter`**（数据过滤器）
5. **用滑块（或输入框）把低于 0.2% 的体元剔除**

> "use the slider (or input box) to **remove voxels that represent uneconomical copper**."

**→ 剩下的体，就是「经济上可采的铜矿体」的三维几何形状。**

> 📎 背景补充：优先用 **输入框手打 `0.2`** 而不是拖滑块——滑块难以精确停在 0.2，而这个阈值有明确的经济含义，差一点结论就变。教程把两种方式并列，但精度上输入框更可靠。

#### 步骤 21 — 最终分析（教程的三道题）

**题 1：侵入体的形态**

> "Geology: The copper mineralisation mostly occurs in **microtonalite intrusives**. **What type of intrusion is this?** Assess intrusion shape by **isolating copper display to the highest concentrations which occur around the intrusion edges**. **Is this geometry helpful for extracting minerals?**"

**做法：** 把 data filter 的下限继续调高（只显示最高品位的体元），此时显示出来的就是**沿侵入体边缘分布的高品位壳层**——因为矿化集中在侵入体顶部与接触带（见 §2.8）。**这个「壳」的形状勾勒出侵入体本身的轮廓。**

> ⚠️ 材料**没有给出这道题的答案**（不写明是岩株 stock、岩盖 laccolith 还是岩墙 dyke）。**推断需要看实际模型，笔记不臆断。** 但可用 §2.8 的知识准备判据：斑岩型矿床通常与 **1–7 km 深处的浅成侵入体（stock / 岩株）** 相关，其顶部呈上凸的钟形。
>
> **「Is this geometry helpful for extracting minerals?」的思考方向（📎 分析框架，非材料原文）：** 高品位若呈**薄壳/环带**而非**实心块体**，对露天开采是**不利**的——为了采到那层壳，必须把中间的低品位核心一起剥掉（高剥采比 strip ratio）。反之若高品位集中成实心团块，则可选择性开采。

**题 2：露天坑规模**

> "The model displays the distribution of **exploitable copper** in the subsurface below Coed-y-Brenin. **If the copper body was to be mined, how destructive would it be to Snowdonia?** i.e. **use the measure tools to estimate how deep and wide the open cast pit would need to be.**"

**做法：** 用 ArcGIS Pro 的 **`Measure`**（量测）工具，在过滤后的体上量：
- **矿体的水平延展（宽度）** → 决定露天坑的**开口直径**
- **矿体的最深经济品位位置** → 决定坑的**深度**

> 📎 背景补充（教程未讲，但估算露天坑必须知道）：**露天坑的实际开口远大于矿体本身**，因为边坡必须放坡（典型总体边坡角 **45°–55°**）。粗略估算：
> $$\text{坑口半径} \approx \text{矿体半径} + \frac{\text{坑深}}{\tan(\text{边坡角})}$$
> 即深 300 m、边坡 45° 的坑，每一侧要多剥出约 **300 m**。**这会把「破坏范围」放大好几倍**——这正是老师那个问题（Would you dig up Eryri?）的分量所在。
> **量测工具路径：`Map` 选项卡 → `Inquiry` 组 → `Measure` → `Measure Distance` / `Measure Features`。** 教程只说 "measure tools"，未给路径。

**题 3（Lecture Slide 32，收尾讨论）：**

> **"Would you dig up Eryri (Snowdonia) to access it?"**

结合 §4.4 的伦理链条作答。

#### 步骤 22 — 三维渲染性能问题（Troubleshooting）

**教程原文：**

> "If the computer has issues **displaying and manipulating in 3D space**, try **reducing the CPU load**."

**路径：** 主窗口 **`PROJECT` 选项卡 → 左侧菜单的 `OPTIONS` → 找到 `DISPLAY` 选项**

**三个可调项：**

| 选项 | 调整 |
|---|---|
| **Antialiasing mode**（抗锯齿） | switch to **Normal** or **None** |
| **Rendering quality**（渲染质量） | slide to **Low** |
| **Rendering engine**（渲染引擎） | "Maybe switch to the **OpenGL** rendering engine" |

> 📎 背景补充：ArcGIS Pro 的三维渲染主要吃 **GPU** 而非 CPU（教程写 "reducing the CPU load" 略有偏差）。除上述三项外，实用的减负手段还有：
> - **关掉 `AerialPhotos` 组图层**（步骤 4 建组图层的实际收益就在这里——一键关掉一整批高分辨率影像）
> - 关掉不看的点图层
> - 提高 data filter 的下限（渲染的体元少了自然就快）
> - Voxel 导出时用更大的 cell size
>
> **另有一个 ArcGIS Pro 的已知点：默认渲染引擎是 DirectX；机房显卡驱动老旧时切到 OpenGL 常能解决闪烁/黑屏。** 切换后需**重启 ArcGIS Pro** 才生效——教程没说这一点。

---

### 5.4 拓展任务（If you have time at the end）

#### 拓展 A — 其他关键金属

**背景（教程原文，引 Sillitoe 2010）：**

> "Distinct **zones** develop within copper porphyry systems. As magmatic driven hydrothermal fluids pass upwards through the rock volume they develop a **central zone where copper becomes concentrated as copper sulphides**. **Outside this is a halo enriched in pyrite (iron sulphide).** Separate hydrothermal phases may also deposit other metal rich phases."

**操作：** metal grades 数据库里还有三个字段，用同样的流程（符号化 / 加入 EBK3D / data filter）把它们画进 3D 模型，看它们与主铜矿体的空间关系：

| 元素 | 字段 | 单位 | 经济品位 |
|---|---|---|---|
| **Pyrite（黄铁矿）** | **`Ss`** | %（推断） | **>1.5%** 定义为晕圈（非经济指标） |
| **Molybdenum（钼）** | Mo | **%** | **约 0.05%** |
| **Gold（金）** | Au | **ppm** | **0.5 ppm** |

**Figure 3 的预期结果：**

> "**Blue**: central core enriched to **greater than 0.2% copper**. **Pink**: **pyrite rich (>1.5%) halo**."

**→ 你应当看到一个「蓝色铜核 + 粉色黄铁矿晕」的同心结构。这直接验证了 §2.8 的斑岩分带模型。**

> ⚠️ **单位不统一是这里最大的坑：Cu 和 Mo 用百分比，Au 用 ppm。** 设 data filter 时若把 Au 的 0.5 ppm 误当成 0.5%（= 5000 ppm），会把所有金全部滤掉，得到一个空模型。
> ⚠️ 字段名 **`Ss`** 代表 pyrite 的依据不明（教程只写 "pyrite (Ss)"），实际字段名以数据表为准。

#### 拓展 B — 其他体数据可视化方法

**教程原文：**

> "There are other ways of interacting with voxel layers. By **expanding the Voxel layer in the content panel**, it is possible to use various **slicing and isosurface** techniques. Experiment with the options by **right clicking and selecting `Create New`**."
> "Note: an **isosurface is a surface of equal value**. It can be used to **set and isolate the outer boundary of the ore body**."

**操作：** 在 Contents pane 中**展开 voxel 图层**（点左侧三角），会看到 **`Slices`** 与 **`Isosurfaces`** 两个子项，**右键 → `Create New`**。

**两者的分工：**

| 手段 | 看什么 | 何时用 |
|---|---|---|
| **Slice（切片）** | 沿任意方向切一刀，看**断面内部**的品位分布 | 想知道矿体**内部**怎么变化 |
| **Isosurface（等值面）** | 画出某一品位值的**外壳** | 想知道矿体的**边界几何形状**（如 0.2% 的经济边界） |

**→ 这正是 §2.7 与 lecture Slide 17 内容的动手落实（老师说的 "We will be slicing this afternoon"）。**

> 📎 背景补充：**等值面阈值取 0.2%（经济截止品位）时，得到的等值面就是「经济矿体的外表面」**——比 data filter 的方块状体元边界更平滑，更适合用于报告插图与体积估算。这一点教程没有点破，但它是 isosurface 在资源评估里最标准的用法。

### 5.5 引用文献（Practical 列出）

- **Mason, J.S., Liezers, M., Cotterell, T.F. 2018.** *Andradite-bearing skarn-like mineralisation and a suspected palaeogene dyke from Coed y Brenin, North Wales.* Journal of the Russell Society, v.21, p.106–123.
- **Sillitoe, R.H. 2010.** *Porphyry Copper Systems.* Economic Geology, v.105, p.3–41.

（Lecture 另引：Park et al. 2021, https://doi.org/10.1038/s43017-021-00182-8；Richards & Mumin 2013, https://doi.org/10.1130/G34275.1；Pal & Ghosh 2023, https://doi.org/10.1029/2022GL102694；Witherly, https://doi.org/10.1080/14432471.2023.2287269；IEA critical minerals: https://www.iea.org/topics/critical-minerals）

---

## 六、易错点 / 重点难点

### ★★★ 头号考点：把 DEM / DTM 当成真 3D

**错误说法：** 「我做了一个 DEM 的三维显示，所以我在做 3D GIS。」

**为什么错：** 讲义 Slide 5 的原话——

> "The map is a **surface** existing in 3D space. But a point on this surface can **still be described using only x and y coordinates**. **This is not 3D**（mathematically speaking a 'surface' is always 2D）."

**判据（一句话）：给定 (x, y)，答案唯一 → 2.5D；答案不唯一 → 3D。**

**DEM 表达不了的四类东西（务必能举例）：**

| 情形 | 为什么 2.5D 失效 |
|---|---|
| **洞穴 / 地下巷道** | 它根本不在地表上，DEM 只存表面 |
| **悬崖倒悬（overhang）** | 同一 (x,y) 上下有多段实体，DEM 只能存一个 z |
| **多层建筑 / 立交桥** | 同上 |
| **本周的矿体、水体温度剖面、大气湿度剖面** | 值随深度/高度变化，是**体**属性 |

**答题模板：** 「DEM 是 2.5D，因为它对每个平面位置只存储**一个**高程值；真 3D 要求数据具有 **volume**，即同一 (x, y) 沿 z 方向可以有多个不同的值。」

---

### ★★ 陷阱：把 Wolfenstein / Doom 的技术史当作严格结论

- 讲义写 Wolfenstein 3D 是 **1991** → 实际是 **1992**（1981 的是 *Castle Wolfenstein*）。
- 老师说 **Doom** 拿到了第三维 → **Doom（1993）在技术上仍是 2.5D**（不支持 room-over-room、不能真正垂直瞄准）；真 3D 从 **Quake（1996）** 开始。

**→ 这个例子的教学价值在于「raycasting = 2D 渲染技巧」这个类比，不在于游戏史细节。答题时用类比，不要引用年份。**

---

### ★★★ 混淆：`triangular irregular network`（三角测量网）vs `TIN`（不规则三角网）

老师在讲 OSGB36 时说：trig pillars「produces a **triangular irregular network grid**, which expands from Newlyn」。

**⚠️ 这里指的是 19 世纪的实地三角测量控制网（triangulation network），不是 GIS 数据模型 TIN。**

| | 老师说的 | GIS 里的 TIN |
|---|---|---|
| 全称 | triangulation network（三角测量网） | **Triangulated Irregular Network** |
| 是什么 | 一批实体三角点石柱 + 互相通视的观测边 | 一种由不规则三角面片构成的**表面数据模型** |
| 用途 | 建立**大地控制基准** | 存储和显示**地形表面**（2.5D！） |
| 本周是否讲 | 讲了（历史背景） | **没讲** |

**→ 顺带记住：即便是 GIS 的 TIN，它也是 2.5D，不是 3D。**

---

### ★★★ Local Scene vs Global Scene 选错

**教程给的判据本身用词有误（scale 反了），但结论是对的：本练习用 Local Scene。**

**正确的选择依据（记这三条）：**

| 判据 | 用 Local Scene | 用 Global Scene |
|---|---|---|
| 坐标系 | **投影坐标系**（如 British National Grid） | **地理坐标系**（WGS84 等） |
| 空间范围 | 局部（矿区、城市、单体） | 国家 / 洲际 / 全球 |
| 是否需要看**地下** | **是** → 必须 Local | 否 |

**选错的后果：**
- 在 Global Scene 里加载 BNG 投影数据，ArcGIS 会**动态投影**到球面，性能大幅下降，垂直方向可能异常。
- **Voxel layer 需要 Local Scene。** 在 Global Scene 里可能根本加载不出来。
- 地下导航体验极差 —— 而本周整个练习的全部意义就在地表以下。

---

### ★★★ 垂直基准：把 `Depth_m` 直接当成高程

**这是 Practical 专门设计的一个「先犯错、再纠正」的环节（步骤 9）。**

**错在哪：** `Depth_m` 是相对于**钻机台面（drill floor）**的相对深度；而钻机台面「moved from **hill top to valley floor**」——每口井的基准都不一样。教程原话：「**this measurement is meaningless**」。

**正确做法：** 通过 `Borehole` 字段 join 井口坐标表，取 `BNG_Z`（井口绝对高程），换算：

$$\text{Height\_m} = \text{BNG\_Z} + \text{Depth\_m}\quad (\text{Depth\_m} < 0)$$

**自检：`Height_m` 必须随井深单调递减。**

**→ 这一条与 lecture 的 §2.2 是同一个道理的两个尺度版本：国家尺度上是 OSGB36 / ETRS89 / WGS84 之争，矿区尺度上是 drill floor vs sea level 之争。本质都是「Z 的基准是什么」。**

---

### ★★ 符号约定：`+ Depth_m` 还是 `- Depth_m`

教程给的公式是**加号**，隐含 `Depth_m` 存的是**负值**。

**⚠️ 动手前先打开属性表看一眼 `Depth_m` 的正负。** 如果是正数，公式必须改成减号，否则样品会被放到井口上方的空中——而且**图上看起来「有模有样」，不会报错**，这是最危险的一类错误。

**唯一可靠的检查方式：教程给的那句自检——「decreasing height corresponding with increasing well depth」。**

---

### ★★ Join 相关的三个坑

1. **Join 之后字段名带前缀。** 表达式必须写 `!Well_Positions.BNG_Z!` 而不是 `!BNG_Z!`。
2. **算完必须 `Remove All Joins`。** 「joined tables **cannot be plotted**」——不断开就无法 `Display XY Data`。
3. **Validate Join 报的「没有索引」不是错误**，是性能警告，可以忽略（教程也这么说，只是把 warning 说成了 error）。

**保险起见：算完 `Height_m` 后立刻 `Data > Export Table` 导出一份固化的表。**

---

### ★★ 数据类型与格式的三处术语坑

| 材料写法 | 问题 | 正确理解 |
|---|---|---|
| "Add the **geodatabase**: MetalGrade.dbf" | `.dbf` 是 **dBASE 独立表**，不是 geodatabase | 应称 **standalone table** |
| "Data Type: **Float** (numbers of up to **6 decimal places**)" | Float 是**单精度浮点**，约 7 位**有效数字**，不是 6 位小数 | 高程值用 Float 够用；若需更高精度用 **Double** |
| "Coed-y-Brenin.**img**: 5m resolution **DEM**" / 后文称 "**DTM**" | DEM 与 DTM 在文中混用 | 📎 严格来说 **DTM = 地面高程（去除地物）**，**DSM = 含地物表面**，**DEM 是二者的统称**。本练习用的是地面模型，称 DTM 更准确 |

---

### ★★ 单位与坐标系不匹配

1. **拉伸/高程值的单位必须与坐标系单位一致。** BNG 的单位是**米**，所以 `BNG_Z`、`Depth_m`、`Height_m` 都必须是米。若混入英尺（1970 年代的钻孔记录很可能用英尺！），矿体的垂直尺度会错 3.28 倍。
   > ⚠️ 教程没有提示单位核查，**但字段名 `Depth_m` / `Height_m` 的后缀 `_m` 就是米的证据**。若换用其他数据集必须自查。
2. **拓展任务里 Au 用 ppm，Cu 与 Mo 用 %。** 混用会导致 data filter 结果完全错误（详见 §5.4）。
3. **垂直坐标系是 gravity-related（正高）而不是椭球高。** 概念上对应 §3.2 的 **H** 而不是 **h**。

---

### ★★ 垂直夸大（vertical exaggeration）未标注

> 📎 背景补充：**本周材料完全没有提到 vertical exaggeration**，但它是所有三维地学可视化的通病，值得一并记住：
>
> - ArcGIS Pro 中路径：**Scene Properties（右键场景 → Properties）→ Elevation Surface → Vertical Exaggeration**。
> - **只要 ≠ 1，就必须在图注里写明**。否则读者会把被拉高的地形误读成陡坡，把被压扁的矿体误读成薄层。
> - 在本练习中：研究区水平范围可能有数公里，而矿体垂直范围只有几百米——**默认 1:1 显示时矿体会显得很扁**，容易忍不住去调夸大系数。**调了就要标。**

---

### ★★ 三维渲染性能 vs 数据量的权衡

**症状：** 旋转卡顿、黑屏、闪烁、ArcGIS Pro 无响应。

**教程给的三招：** Antialiasing → Normal/None；Rendering quality → Low；切到 OpenGL 引擎。

**📎 补充的四招：** 关掉 `AerialPhotos` 组图层（这就是当初建组图层的收益）；关掉不看的点图层；提高 data filter 下限；voxel 导出时用更大 cell size。

**核心权衡：体元越小 → 矿体边界越平滑、体积估算越准 → 但体元数量按 **立方** 增长（cell size 减半 → 体元数 ×8）→ 渲染与内存开销急剧上升。**

---

### ★ 概念上必须分清的三对

| A | B | 区别 |
|---|---|---|
| **Ellipsoid** | **Geoid** | ellipsoid 是**光滑的数学面**；geoid 是**起伏的重力等位面**（≈ 海平面） |
| **Ellipsoid height (h)** | **Orthometric height (H)** | h 是 GPS 直接测的；H 是地图上的「海拔」；**H = h − N** |
| **Discrete data** | **Continuous data** | discrete 有**明确边界**、是编码；continuous **无边界**、可取任意值、**必须插值** |

---

### ★ 别把「EBK3D 的输出」当成体元图层

**流程链必须记全：**

> **点 → EBK3D → 一叠可滑动浏览的水平切片（geostatistical layer）→ `GA Layer 3D To NetCDF` → voxel layer（.nc）**

**中间那一步不做，你手上就只有切片，没有体。** 而且导出后**不一定自动加载到场景**，要手动 `Add Data`。

---

### ★ 别跳过半变异图

教程让你「use defaults for all options」，很容易一路 Next 到底。**但半变异图是唯一能判断插值可不可信的地方。** 如果曲线几乎水平（没有清晰的 range），说明数据没有空间自相关，克里金结果就是数学上的胡编。

---

### ★ 授权模块搞错

**`Empirical Bayesian Kriging 3D` 与 `GA Layer 3D To NetCDF` 都属于 `Geostatistical Analyst` 扩展**，不是教程说的 3D Analyst / Spatial Analyst。**报授权错误时先去 `Project > Licensing` 检查 Geostatistical Analyst 是否勾选。**

---

### ★ 统计判读：不要用平均品位代表矿体

Cu_percent 是**强右偏**分布。**mean > median > mode**，且 **mode 落在经济品位 0.2% 之下**。这意味着：

- **平均品位被少数高值样品拉高**，不代表典型矿石；
- 真正决定项目可行性的是**「高于截止品位的那部分矿石的吨位与平均品位」**，而不是全体样品的均值。

**这是资源地质里最常见的统计误用，也是本 practical 那道思考题的答案核心。**

---

## 七、本周术语表

### 7.1 三维与维度概念

| 英文 | 中文 | 说明 |
|---|---|---|
| **2D** | 二维 | x, y 定位；纸质地图、屏幕 |
| **2.5D** | 二维半 | 「存在于三维空间中的二维**表面**」；给定 (x,y) 值唯一；DEM/DTM、drape 的地质图、Wolfenstein 3D |
| **3D (true 3D)** | 真三维 | 具有 **volume**；定位需 x, y, **z**；同一 (x,y) 沿 z 可有多值 |
| **Volume** | 体积 | 讲义判据：「**Volume is integral in geospatial 3D**」 |
| **Surface** | 表面 | 「mathematically speaking a 'surface' is **always 2D**」 |
| **Raycasting** | 光线投射 | 「a **2D rendering technique** to give sprites/walls the appearance of 3D」 |
| **Volumetric data** | 体数据 | 只能看到外壳，必须切片/等值面才能看内部 |
| **Volumetric realisation** | 体渲染实现 | 讲义：「a powerful method of visualising 3D data」 |

### 7.2 大地测量与垂直基准

| 英文 | 中文 | 说明 |
|---|---|---|
| **Geodesy** | 大地测量学 | 「the science of measuring Earth's **shape, orientation and gravity field**」 |
| **Oblate spheroid** | 扁椭球 / 扁球体 | 地球形状；赤道直径大于极直径约 40 km |
| **Ellipsoid** | （参考）椭球体 | 「an **idealised mathematical model** of the Earth」 |
| **Reference ellipsoid** | 参考椭球 | 讲义 Slide 9 用语 |
| **Geoid** | 大地水准面 | 「a **gravitational equipotential surface**」，≈ 海平面，但**动态起伏** |
| **Equipotential surface** | 等位面 | 重力位相等的曲面 |
| **Prime meridian** | 本初子午线 | 定义 X；位于 **Greenwich** |
| **Equator** | 赤道 | 定义 Y；「the plane **equidistant** between the Earth's geographical poles」 |
| **Ellipsoid height (h)** | 椭球高 | GNSS/GPS 直接测得 |
| **Geoid height (N)** | 大地水准面高 / 起伏 | 椭球面到 geoid 的高差，可正可负 |
| **Orthometric height (H)** | 正高 | geoid 到地表；地图上的「海拔」；**H = h − N**（📎 公式为补充） |
| **Topographic surface** | 地形面 | 讲义 Slide 10 标签 |
| **Vertical datum** | 垂直基准 | 高程的起算面 |
| **Horizontal coordinate system** | 水平坐标系 | ArcGIS Pro Map Properties 中的 Current XY |
| **Vertical coordinate system** | 垂直坐标系 | ArcGIS Pro 中的 Current Z |
| **Gravity-related** | 基于重力的（垂直坐标系类别） | 对应正高系统 |
| **OSGB36** | 英国国家测量局 1936 坐标参考系统 | Ordnance Survey of Great Britain 1936；tied to **Newlyn, Cornwall** 的平均海平面；拟合 **Airy 1830** 椭球 |
| **Airy 1830** | 艾里 1830 椭球 | 英国国家椭球 |
| **ODN (Ordnance Datum Newlyn)** | 纽林基准 | 📎 补充：英国**垂直**基准的正式名称 |
| **ETRS89** | 欧洲地面参考系统 1989 | European Terrestrial Reference System 1989；OS GPS 网所系 |
| **WGS84** | 世界大地测量系统 1984 | World Geodetic System 1984；手机 GPS 用 |
| **GRS80** | 大地参考系统 1980 | Geodetic Reference System 1980；全球椭球 |
| **EVRS / EVRF2000** | 欧洲垂直参考系统 / 参考框架 2000 | Practical 中用作 Z 坐标系（⚠️ 教程写作 `EVRS2000`，ArcGIS 中实为 **EVRF2000**） |
| **British National Grid (BNG)** | 英国国家格网 | EPSG/WKID **27700**；单位米 |
| **Trig pillar / triangulation pillar** | 三角点石柱 | 讲义配图为 **Mam Tor trig pillar** |
| **Triangulation network** | 三角测量网 | ⚠️ 转写作 "triangular irregular network"，**不是 GIS 的 TIN** |
| **RTK (Real-Time Kinematic)** | 实时动态（定位） | 毫米级精度；接入 OS GPS 网（转写作 "real-time chemetics"，ASR 误） |
| **Transform / translation** | 坐标转换 | 不同坐标框架之间必需的数学变换 |
| **Indian Ocean Geoid Low** | 印度洋大地水准面低 | N ≈ **−106 m**；成因为热的低密度地幔柱（Pal & Ghosh, 2023） |
| **Moho** | 莫霍面 | 欧洲重力高的成因之一：dense crust + deep Moho |
| **Craton** | 克拉通 | 转写补充：欧洲是稳定克拉通，地壳厚 |

### 7.3 GIS 数据模型与数据类型

| 英文 | 中文 | 说明 |
|---|---|---|
| **Raster** | 栅格 | 由 pixel 组成的规则数值阵列 |
| **Vector** | 矢量 | 点、线、面（⚠️ 转写此处老师口误，把线说成 raster） |
| **Pixel** | 像元 | 「the **smallest unit of information** in a 2D raster image」；有 x,y + descriptors (R,G,B / height) |
| **Cell** | 像元格 | 「a **cell in a regular array of data values**」 |
| **Voxel** | 体元 | 「a **3-dimensional pixel**」；有 x,y,**z** + descriptors（volume / discrete class / time / density / porosity） |
| **Voxel layer** | 体元图层 | ArcGIS Pro 中的三维体图层，物理载体为 **netCDF** |
| **Multidimensional Voxel Layer** | 多维体元图层 | `Add Data` 时的图层类型名 |
| **Descriptor** | 描述符 | pixel/voxel 携带的属性值 |
| **Discrete data** | 离散数据 | 「assigned to **defined values, usually integers**」；「must have **defined boundaries**」；老师：「effectively a **coding system**」 |
| **Continuous data** | 连续数据 | 「a **measured variable** that could have **any numeric value**」；「**no boundaries**」 |
| **Counted variable** | 计数变量 | 离散数据的一类（如 pets per household、town population） |
| **Classification** | 分类 | 离散数据的另一类用法（land use、geological map unit、road type） |
| **Symbology** | 符号系统 | 图层的显示样式设置 |
| **DEM (Digital Elevation Model)** | 数字高程模型 | 本练习的 `Coed-y-Brenin.img`，5 m 分辨率 |
| **DTM (Digital Terrain Model)** | 数字地形模型 | 讲义 Slide 5 用 Isle of Mull DTM 举例 |
| **netCDF (.nc)** | 网络通用数据格式 | 多维科学数据标准格式；voxel layer 的载体 |
| **.img** | ERDAS IMAGINE 栅格格式 | 📎 格式说明为补充 |
| **.dbf** | dBASE 表格式 | ⚠️ 教程误称其为 "geodatabase" |
| **Standalone table** | 独立表 | 没有几何的属性表；在 Contents pane 中单列 |

### 7.4 地统计与插值

| 英文 | 中文 | 说明 |
|---|---|---|
| **Geostatistical interpolation** | 地统计插值 | 由有限采样点估计整个空间的值 |
| **Kriging** | 克里金（法） | 「spatial **interpolation between point data**」 |
| **Bayesian** | 贝叶斯 | 「employment of **prior knowledge** into a calculation」 |
| **Empirical Bayesian Kriging 3D (EBK3D)** | 三维经验贝叶斯克里金 | 本周核心工具；迭代估计大量半变异函数 |
| **Semi-variogram** | 半变异函数（图） | 半变异随间距的变化曲线 |
| **Sample variogram (Observed)** | 样本变异函数（实测） | 由数据算出的曲线 |
| **Variogram model** | 变异函数模型 | 「**mathematical expression** used to describe the sample variogram」（⚠️ 材料给它贴了 "Empirical" 标签，用词有误） |
| **Semi-variance** | 半变异（值） | 「**half the variance** of the differences between all possible points spaced a **constant distance** apart」 |
| **Lag distance** | 间距 / 滞后距离 | 点对之间的分隔距离 |
| **Range** | 变程 | 「the point where increasing lag distance **no longer has an effect** on semi-variance」 |
| **Nugget** | 块金（值） | 间距为 0 时的半变异；源于 **measurement error** 与自然数据的随机性 |
| **Sill** | 基台值 | 📎 材料未提；曲线的平台高度 ≈ 总方差 |
| **Subset** | 子集 | EBK3D 把数据切成子集，**默认 100 点** |
| **Binning** | 分箱 | 「binning the data into pairs of points with **common lag distance and direction**」 |
| **Spatial autocorrelation** | 空间自相关 | W05 学过；半变异函数是它的定量表达 |
| **Interpolate** | 插值 | 「**fill in the space between the points that we do know**」 |
| **Isosurface** | 等值面 | 「a **surface of equal value**」；可圈出矿体外边界 |
| **Slice** | 切片 | 从体中切出的 2D 面；EBK3D 原生输出为**水平**切片 |
| **Data filter** | 数据过滤器 | Voxel Layer symbology 中按值域剔除体元 |
| **Mean / Median / Mode** | 均值 / 中位数 / 众数 | Practical 要求计算并排序；右偏 → **mean > median > mode** |
| **Skewed to the right** | 右偏（正偏） | 本数据集的分布形态 |
| **Histogram** | 直方图 | Voxel symbology 面板的判读依据 |

### 7.5 ArcGIS Pro 界面、菜单与工具（**全部保留英文原名**）

| 英文原名 | 位置 / 路径 | 用途 |
|---|---|---|
| **Contents pane** | 左侧 | 图层列表、右键各类操作的入口 |
| **Catalog pane** | 右侧 | 浏览工程文件 |
| **Geoprocessing pane** | 右侧（运行工具时弹出） | 工具参数对话框 |
| **Map Properties** | 右键 `Map` → Map Properties | 设坐标系、显示单位 |
| **General tab** | Map Properties 内 | 「change **map units** to meters」（📎 实为 **Display Units**） |
| **Coordinate Systems tab** | Map Properties 内 | 设 Current XY / Current Z |
| **Current XY** | Coordinate Systems tab | 水平坐标系 |
| **Current Z** | Coordinate Systems tab | 垂直坐标系 |
| **Projected Coordinate Systems > National Grids > United Kingdom > British National Grid** | 坐标系树 | 本练习的水平坐标系 |
| **Vertical Coordinate Systems > Gravity-related > Europe > EVRS2000** | 坐标系树 | 本练习的垂直坐标系（⚠️ 实名 **EVRF2000**） |
| **Map tab → Add Data** | 主功能区 | 添加数据 |
| **New Group Layer** | 右键 `Map` → New Group Layer | 建组图层（本练习用于 `AerialPhotos`） |
| **XY Table To Point** | Map tab → Layer 组（📎 或 Geoprocessing 搜索） | 把含 X/Y/Z 字段的表转成点要素 |
| **Display XY Data** | 右键表 → Display XY Data | 同上（教程后半段用的名称） |
| **Input Table / Output Feature Class** | XY Table To Point 参数 | |
| **X Field / Y Field / Z Field** | XY Table To Point 参数 | 本练习分别为 `BNG_X` / `BNG_Y` / `BNG_Z`（后改为 `Height_m`） |
| **Coordinate System: Current Map (Map)** | XY Table To Point 参数 | 沿用工程坐标框架 |
| **View tab → Windows 组 → Reset Panes → Reset Panes for Mapping** | 主功能区 | 关闭无关窗格，确保 Contents 与 Catalog 打开 |
| **View tab → View 组 → Convert → Local Scene** | 主功能区 | **2D Map 转 3D 场景**；生成 `Map_3D` 窗口 |
| **Local Scene** | 场景类型 | 投影坐标系 + 局部范围 + 支持地下导航；**本练习必用** |
| **Global Scene** | 场景类型 | 地理坐标系 + 全球/国家尺度 |
| **Map_3D** | 转换后生成的三维视图窗口名 | |
| **Elevation Surfaces → Ground** | Contents pane 中 | 把 DEM 拖进来才会真正抬起地表 |
| **WorldElevation3D/Terrain3D** | 默认全球高程服务 | 约 30 m 分辨率；本练习需**取消勾选** |
| **SRTM (Shuttle Radar Topography Mission)** | 航天飞机雷达地形测绘任务 | Terrain3D 的主要来源之一 |
| **Field: Add** | 属性表上方 | 新建字段 |
| **Fields view** | 字段视图 | 编辑字段定义 |
| **Field Name / Data Type / Number Format** | Fields view 参数 | 本练习：`Height_m` / `Float` / `Numeric` |
| **Float / Double** | 单精度 / 双精度浮点 | 教程选 Float（Double「use unnecessary memory」） |
| **Joins and Relates → Add Join** | 右键表 | 按公共字段拼接两张表 |
| **Input Table / Input Field / Join Table / Join Table Field** | Add Join 参数 | 本练习均以 **`Borehole`** 为连接键 |
| **Join Operation: Join one to first** | Add Join 参数 | 一对一连接 |
| **Validate Join** | Add Join 对话框按钮 | 检查连接可行性（无索引的提示可忽略） |
| **Joins and Relates → Remove All Joins** | 右键表 | **绘点前必须执行** |
| **Calculate Field** | 右键字段表头 → Calculate Field | 用表达式批量赋值 |
| **`!Well_Positions.BNG_Z! + !Metal_Grade.Depth_m!`** | Calculate Field 表达式（Python） | 井口高程 + 井下深度 = 绝对高程 |
| **Data → Export Table** | 右键表 → Data → Export Table | 固化计算结果（保险步骤） |
| **Graduated Colors** | Symbology 中的显示方式 | 按 `Cu_percent` 分级着色，暖色 = 高品位 |
| **Analysis tab → Workflows 组 → Data Engineering** | 主功能区 | 计算 mean / median / mode 等描述统计 |
| **Analysis tab → Geostatistical Wizard** | 主功能区 | 地统计向导 |
| **Empirical Bayesian Kriging 3D** | Geostatistical Wizard 中的工具 | 三维克里金插值 |
| **Source Dataset / Elevation Field / Data Field** | EBK3D 参数 | 点图层 / `Height_m` / `Cu_percent` |
| **Geostatistical Analyst** | 扩展模块 | ⚠️ EBK3D 与 GA Layer 3D To NetCDF 的真正授权来源 |
| **3D Analyst / Spatial Analyst** | 扩展模块 | 教程称需启用（表述有误，见勘误表） |
| **Vertical slider** | 主屏右侧 | 浏览 EBK3D 输出的水平切片 |
| **GA Layer 3D To NetCDF** | 右键 EBK3D 结果 → Export to NetCDF/Voxel | **把克里金结果转成 voxel layer**；本练习输出名 `Cu_voxels` |
| **Voxel Layer tab → Drawing 组 → Symbology** | 选中体元图层后出现的专用工具条 | 打开体元符号系统 |
| **Data Filter** | Voxel symbology 面板中，直方图上方 | 按品位阈值剔除体元（本练习 **0.2%**） |
| **Slices / Isosurfaces → Create New** | Contents pane 中展开 voxel 图层后右键 | 创建切片与等值面 |
| **Measure tools** | 📎 Map tab → Inquiry 组 → Measure | 估算露天坑深度与宽度 |
| **PROJECT tab → OPTIONS → DISPLAY** | 主窗口 | 渲染性能设置 |
| **Antialiasing mode** | DISPLAY 选项 | 设为 **Normal** 或 **None** |
| **Rendering quality** | DISPLAY 选项 | 滑到 **Low** |
| **OpenGL rendering engine** | DISPLAY 选项 | 备选渲染引擎 |
| **Vertical Exaggeration** | 📎 Scene Properties → Elevation Surface | 垂直夸大系数（**材料未涉及**） |
| **Extrusion** | 📎 图层 Appearance tab → Extrusion 组 | 要素拉伸（**材料未涉及**） |

### 7.6 资源地质与关键金属

| 英文 | 中文 | 说明 |
|---|---|---|
| **Critical minerals / metals** | 关键矿产 / 关键金属 | 净零转型所需；IEA 分类 |
| **Porphyry (copper) deposit** | 斑岩（铜）矿床 | 与汇聚板块边缘岩浆-热液系统相关的大吨位低品位矿床 |
| **Convergent plate tectonics** | 汇聚型板块构造 | 斑岩矿床的构造背景 |
| **Downgoing slab** | 下插板片 | 提供富氧水与含水熔体 |
| **Hydrous melt** | 含水熔体 | |
| **Mantle wedge** | 地幔楔 | 氧化条件下部分熔融，耗尽硫化物 |
| **Affinity for sulphides** | 对硫化物的亲和性 | Cu、Au 被优先带入硫化物 |
| **Incompatible** | 不相容（元素/相） | 硫化物与硅酸盐岩浆不相容 → 被排入热液 |
| **Fractionation / magmatic differentiation** | 分离结晶 / 岩浆分异 | 发生在 30–70 km 的壳幔边界 |
| **Fluid saturated** | 流体饱和 | 上升致上覆压力下降的结果 |
| **Hydraulic fracture (frack)** | 水力压裂 | 高压岩浆流体压裂侵入体顶部与围岩 |
| **Brine** | 卤水 | 冷凝后的富金属流体 |
| **Halo** | 晕（圈） | 金属硫化物在侵入体周围形成的环带 |
| **Disseminated** | 浸染状 | 金属散布在岩石孔隙中（**这是克里金插值成立的物理前提**） |
| **Veinlet** | 细脉 | |
| **Supergene enrichment** | 表生富集 | 近地表 **redox** 过程，可把品位从 1% 富集到 >2% |
| **Meteoric water** | 大气降水（地下水） | 富氧，淋滤金属 |
| **Redox** | 氧化还原 | 表生富集与 turf mine 的核心机制 |
| **Leach** | 淋滤 | |
| **Reducing conditions** | 还原条件 | 金属再沉淀的环境 |
| **Explosion breccia pipe** | 爆破角砾岩筒 | 「Bleached / shattered hydrous silica. Sometimes 'pods' of copper」 |
| **Phreato-magmatic** | 潜水-岩浆（爆发） | Practical 用语 |
| **Sericitic zone** | 绢云母化带 | 「hydrothermally decomposed microtonalite – iron stained – pyrite rich」 |
| **Microtonalite** | 微（粒）英云闪长岩 | 矿化主岩（⚠️ 材料在"volcanic"与"intrusive"之间用词不一致） |
| **Chalcopyrite** | 黄铜矿 | CuFeS₂；主要铜矿物 |
| **Pyrite** | 黄铁矿 | FeS₂；构成晕圈（>1.5%） |
| **Molybdenite** | 辉钼矿 | MoS₂；与后期石英-碳酸盐脉共生 |
| **Native copper / gold** | 自然铜 / 自然金 | Turf mine 中的产出形式 |
| **Malachite / Azurite** | 孔雀石 / 蓝铜矿 | Alderley Edge 的铜次生矿物 |
| **Andradite** | 钙铁榴石 | Mason et al. 2018 标题中的矽卡岩矿物 |
| **Ore grade / cut-off grade** | 矿石品位 / 截止品位 | 本练习 Cu 截止品位 **0.2%** |
| **Economic limit** | 经济界限 | 「ore handling facilities are unable to process ore containing less than 0.2%」 |
| **Open cast pit** | 露天采坑 | Final Analysis 要估算其深度与宽度 |
| **Mine tailings / mine spoil** | 尾矿 / 矿渣 | 1915 年关停的直接原因 |
| **Acid Mine Drainage (AMD)** | 酸性矿山排水 | 📎 补充术语；材料描述了机制但未点名 |
| **Borehole / exploration well** | 钻孔 / 勘探井 | 1960s–1970s 钻探；本练习的数据来源 |
| **Drill floor** | 钻机台面 | **`Depth_m` 的原始基准**；「moved from hill top to valley floor」→ 无意义 |
| **Ground penetrating radar (GPR)** | 探地雷达 | 地下数据来源之一 |
| **Seismic survey** | 地震勘探 | 地下数据来源之一 |
| **Bulk-tonnage / low-grade deposit** | 大吨位低品位矿床 | 📎 补充术语；由 mean>median>mode 的右偏分布指示 |
| **Biogeochemical prospecting** | 生物地球化学找矿 | 📎 补充术语；Sea Pinks 指示硫化物矿体 |
| **Sea Pinks (Armeria maritima)** | 海石竹 | 耐金属，生长于矿渣与富金属水出露处 |
| **Sea-Campion (Silene uniflora)** | 白玉草 | 同上（仅 Practical 提及） |
| **Harlech Dome** | 哈莱赫穹隆 | Coed-y-Brenin 所在的构造单元 |
| **Glasdir mine** | 格拉斯迪尔矿 | 主矿山（⚠️ 讲义误作 "Gasdir"） |
| **Dolfrwnog Mine / 'turf' mine** | 泥炭矿 | 1824–1865 挖泥炭焙烧提铜 |
| **Rhobell volcanic system** | Rhobell 火山系统 | 早奥陶世，驱动区域热液系统 |
| **Mawddach Group** | Mawddach 群 | 寒武纪页岩，金属来源之一 |
| **Eryri / Snowdonia** | 埃里里 / 斯诺登尼亚 | 威尔士国家公园；Slide 32 的伦理问题所在 |
| **Reko Diq** | 雷科迪克矿（巴基斯坦） | 5.9 Bt @ 0.41% Cu、0.22 ppm Au |
| **IEA (International Energy Agency)** | 国际能源署 | 关键矿产需求数据来源（讲义误写为 "Association"） |

---

## 附：材料勘误表

> 说明：本周三份材料的勘误集中在三类——**（A）软件工具名/参数/授权模块**、**（B）地质与地理数值/名称**、**（C）自动语音识别（ASR）造成的转写误写**。C 类不属于授课内容错误，但会严重影响阅读，故一并列出。

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Practical - 3D geospatial techniques.md`，Set up coordinate framework system，Vertical coordinate systems | "Vertical coordinate systems > Gravity-related > Europe and select **EVRS2000**：This is the European Vertical Reference System" | **垂直坐标系名称错误。** ArcGIS Pro 坐标系库中该项的实际名称是 **`EVRF2000`**（European Vertical Reference **Frame** 2000，WKID 5730）。EVRS 是「系统」，EVRF 是其具体「实现/框架」，坐标系库里只有后者。按 `EVRS2000` 搜索**找不到**。 | 应为 **EVRF2000**。另需注意：**英国本土数据的标准垂直基准是 `ODN (Ordnance Datum Newlyn)`**，EVRF2000 是欧陆基准，两者在英国存在数十厘米系统差；对本练习（矿体尺度百米级）无实质影响，但概念上应区分。 |
| `Practical`，Interpolate Borehole Data 一节 | "(**Licensing errors** will be caused if **3D Analyst** and **spatial Analyst** are not enabled)." | **授权模块指认错误。** `Empirical Bayesian Kriging 3D` 与后文的 `GA Layer 3D To NetCDF` 均属于 **Geostatistical Analyst** 扩展，不属于 3D Analyst 或 Spatial Analyst。仅启用后两者仍会报授权错误。 | 应为「**Geostatistical Analyst** 未启用会导致授权错误」（3D Analyst 用于三维显示与分析、Spatial Analyst 用于栅格分析，是常见搭配但不是本工具的授权来源）。启用路径：`Project > Licensing > Configure your licensing options`，勾选后需重启 ArcGIS Pro。 |
| `Practical`，Convert to 3D view 一节 | "ArcGIS offers two options: **Global Scene (national / very large scale datasets); Local scene (small scale projects)**." | **制图学「scale」用反。** large scale（大比例尺）= 小范围、高细节；small scale（小比例尺）= 大范围、概括。因此「national 数据集」应是 **small scale**，「local 项目」应是 **large scale**——原文恰好写反。 | 应为「**Global Scene（national / very small scale datasets）；Local Scene（large scale, local projects）**」。**结论（本练习用 Local Scene）正确**，但依据应改为技术判据：Local Scene 支持**投影坐标系**（本练习为 BNG）、**局部范围**、**地表以下导航**，且 **voxel layer 需在 Local Scene 中使用**。 |
| `Practical`，Investigate critical metals 一节开头 | "Add the **geodatabase**: MetalGrade.dbf" | **数据格式术语误用。** `.dbf` 是 **dBASE 表文件**（Shapefile 的属性表格式），在 ArcGIS 中作为 **standalone table（独立表）** 加载，与 **geodatabase（地理数据库，`.gdb` / `.sde`）** 是完全不同的概念。 | 应为「Add the **standalone table**（或 **dBASE table**）: MetalGrade.dbf」。同一份教程后文正确地称其为 "the MetalGrade **standalone table**"，前后不一致。 |
| `Practical`，Add consistent vertical datum 第 2 步，Data Type 说明 | "Data Type: **Float** (this defines that the values stored in the column will be **numbers of up to 6 decimal places**)" | **数据类型描述错误。** ArcGIS 的 **Float 是单精度浮点（4 字节）**，精度约为 **7 位有效数字**，**不是「6 位小数」**。有效数字与小数位数是两回事：单精度存 `1234567.8` 已到极限，而不是能存 6 位小数。 | 应为「Float 为**单精度浮点，约 7 位有效数字**；Double 为双精度，约 15 位有效数字但占用双倍存储」。对本例的高程值（数百米、小数点后 1–2 位）Float 完全够用，**教程的选择是对的，只是理由写错了**。 |
| `Practical`，Add Join 第 7 步 | "**Validate Join** (there is an **error** as one of the databases has no index, but this is not a problem)" | **将 warning 说成 error。** 连接字段缺少属性索引在 ArcGIS Pro 的 Validate Join 中返回的是**警告**，含义是连接性能会下降，不是错误。 | 应为 "there is a **warning**"。若要消除，可对 `Borehole` 字段运行 **`Add Attribute Index`** 工具。 |
| `Practical`，Improve vertical resolution 一节 | "ArcGIS uses a default elevation model: WorldElevation3D/Terrain3D. **This model is based on SRTM data**... It is the **same 30 meter resolution global database that Google Earth uses**." | **数据源描述不准确（两处）。** ①`Terrain3D` 是 Esri 的**多源融合**高程服务，SRTM 只是其全球背景层之一，许多地区已用更高分辨率数据（局部可达 1–3 m）替换；②Google Earth 的地形同样来自多来源拼接，**并非与 Terrain3D 同一个数据库**。 | 应为「默认高程服务为 Esri **多源全球高程数据**，全球背景约 24–30 m（部分源自 SRTM），局部更精细」。**结论仍然成立**：它远粗于本练习的 5 m 本地 DEM，必须替换。 |
| `Practical`，Set up coordinate framework system，General tab | "General tab: change **map units** to meters" | **界面项名称不精确。** ArcGIS Pro 的 Map Properties > General 中可设置的是 **Display Units**（显示单位）；真正的「map units」由所选投影坐标系决定（British National Grid 本身就是米），用户无法在此单独更改。 | 应为「General tab: set **Display Units** to Meters」。 |
| `Practical`，Data import 一节 | "Bring each of these into ArcGIS: Enter the **Map** menu (main toolbars) and click on **Add Data**"；以及后文 "Under the **Map tab, in the layer group** select **XY Table to Point**" | **菜单路径与版本相关，且工具归属不精确。** `XY Table To Point` 是 **Data Management Tools > Features** 下的地理处理工具；在 Map 选项卡中的入口实为 **`Add Data` 下拉 → `XY Point Data`**。不同 ArcGIS Pro 版本 ribbon 布局略有差异。 | 最稳妥的做法是**在 Geoprocessing 窗格的搜索框中搜索 `XY Table To Point`**。同理，`Projected Coordinate Systems > National Grids > United Kingdom` 的文件夹层级也随版本变化（部分版本在 `National Grids > Europe` 下），可直接在坐标系搜索框输入 `British National Grid`（WKID **27700**）。 |
| `Practical`，Add consistent vertical datum 第 8 步 | "**Metal_Grade.Height_m = !Well_Positions.BNG_Z! + !Metal_Grade.Depth_m!**" | **符号约定未说明。** 该表达式用**加号**，只有在 `Depth_m` 存储为**负值**时才正确。教程通篇未说明 `Depth_m` 的正负约定，仅在下一句给了自检标准（"decreasing height corresponding with increasing well depth"）。若数据中 `Depth_m` 为正，此式会把样品放到井口**上方**，且**不会报任何错误**。 | 应补充说明：**若 `Depth_m` 为正值，公式须改为 `!Well_Positions.BNG_Z! - !Metal_Grade.Depth_m!`。** 动手前必须打开属性表核对符号，事后必须执行教程给的递减性自检。 |
| `Practical`，表名（全篇） | 同一张表先后被写成 **`MetalGrade.dbf`**、**`MetalGrade`**、**`Metal_Grade`**、**`Metal_Grades`**、**`Metal-Grade`**（含连字符） | **表名前后不一致（五种写法）。** 在 `Calculate Field` 表达式与 `Add Join` 参数中，字段/表名必须与实际名称**逐字符一致**，否则报错。 | 以**实际数据包中的文件名为准**（应为 `MetalGrade.dbf`）。教程中出现的下划线/连字符变体均为笔误。 |
| `Practical`，Figure 1 图注 | "Sample variogram (**Observed**) ... **Variogram model (Empirical)**: mathematical expression used to describe the sample variogram" | **术语标签互换。** 地统计学标准用法中，**empirical / experimental variogram 指由数据直接计算出的实测变异函数**（即这里的 "Sample variogram"），而拟合它的数学函数称 **variogram model / theoretical variogram**。把 model 标为 "Empirical" 是明确的术语误用。 | 应为「Sample / **Empirical (experimental)** variogram：实测曲线；Variogram **model (theoretical)**：拟合用的数学函数」。**同一份教程的 Figure 2 图注中写的 "These empirical (experimental) semi-variances are plotted as blue crosses" 是正确用法**，前后自相矛盾。 |
| `Practical`，Figure 1 图注 | "**Lag distance**: the **direction dependent** distance between data points." | **定义不准确。** lag distance 就是**点对之间的分隔距离**，本身与方向无关；方向是变异函数分析中的**另一个独立维度**（用于检测各向异性 anisotropy，即不同方向上 range 不同）。 | 应为「**Lag distance：点对之间的分隔距离**；在各向异性分析中，半变异会按**距离与方向**两个维度同时分箱（Figure 2 后文的 "common lag distance **and** direction" 才是正确表述）」。 |
| `Practical`，Figure 1 图注（缺项） | 定义了 nugget 与 range，**未定义 sill** | **要素缺失。** 读半变异图必需的三个参数是 nugget、sill、range，教程只给了两个，导致「range 是曲线变平之处」这句话缺少参照物。 | 应补：**sill（基台值）= 曲线达到的平台高度，近似等于数据的总体方差**；**partial sill = sill − nugget**。 |
| `Practical`，Additional critical minerals | "The metal grades database contains values for **pyrite (Ss)**, molybdenum (Mo) and gold (Au)." | **字段名与元素符号的对应不明。** `Ss` 既不是黄铁矿的化学式（FeS₂），也不是任何元素符号；教程未说明该字段的含义（是硫化物总量？还是黄铁矿体积百分比？），也未说明其单位。 | 需以**实际数据表的字段说明为准**。从 Figure 3 图注「pyrite rich (**>1.5%**) halo」推断单位为百分比。教程应给出字段词典。 |
| `Practical`，Additional critical minerals（单位） | "**Gold: values are in ppm.** Economic grade is 0.5 ppm. **Molybdenum: values listed as percentages.** Economic grade is about 0.05%." | 非错误，但**同一练习中三种金属使用两种单位制**（Cu、Mo 用 %，Au 用 ppm），教程未加警示。 | 保留原文，但**设 data filter 阈值时必须逐一确认单位**。换算：**1% = 10,000 ppm**。误把 0.5 ppm 当 0.5% 会滤掉全部金数据。 |
| `Practical`，Additional critical minerals 引用 | "Distinct zones develop within copper porphyry systems (**Silitoe 2010**)" | **人名拼写错误**（少一个 l）。文末参考文献表中写的是正确的 "**Sillitoe, R.H.**"。 | 正确拼写 **Sillitoe**（Richard H. Sillitoe，斑岩铜矿系统研究的权威）。 |
| `Practical`，References | "Journal of the **the** Russell Society" | 重复冠词（排印错误）。 | 应为 "Journal of the Russell Society"。 |
| `Practical`，Geological background vs. Final Analysis | Geological background：「metals accumulated in altered, sheared and fractured **intermediate volcanic rocks: microtonalite**」；Final Analysis：「copper mineralisation mostly occurs in **microtonalite intrusives**」 | **岩石成因类型前后矛盾。** 同一岩性先被称为 volcanic（火山岩），后被称为 intrusive（侵入岩）。转写中老师亦说「microtonalite, so intermediate to volcanic rock」（表述含混）。 | **微英云闪长岩（microtonalite）是浅成/次火山侵入岩（hypabyssal intrusive）**——「micro-」前缀正表示其为细粒的浅成相，成分为中性至中酸性。Final Analysis 的 "intrusives" 是正确表述。 |
| `Practical` vs `Lecture`（铜产量与关闭年份） | Practical：「Glasdir mine ... produced about **1300 tonnes** until closure in **1914**」；Lecture Slide 29：「Shallow mines produced **13,077 t Cu ore** ... 」，Slide 标题「Mining history 1850's to **1915**」；转写：「forced to shut down in **1915**」 | **两处数字不一致：** ①产量 1,300 t vs 13,077 t，相差近 10 倍；②关闭年份 1914 vs 1915。产量差异**可能**是「金属铜吨数」与「铜矿石吨数」之别，但两份材料都没有注明是哪一种，无法判定。 | **材料未说明，不宜断言。** 记忆时应记为：「Glasdir 矿约在 **1850s–1914/15** 间开采，产铜量的两份材料记载分别为 ~1,300 t 与 13,077 t（**单位口径不明**）」。关闭年份以 Practical 的 **1914** 与讲义/转写的 **1915** 并存记录。 |
| `Lecture - 3D geospatial techniques.md`，Slide 29 | "**Gasdir** mine" | **矿名拼写错误。** | 应为 **Glasdir mine**（Practical 与文献中均作 Glasdir）。 |
| `Lecture`，Slide 8 | "The **equatorial diameter is 12,700 km**. The polar diameter is about 40 km shorter." | **数值不准确。** 地球赤道直径实为约 **12,756 km**（赤道半径 6,378.137 km），极直径约 **12,714 km**，两者相差约 **43 km**。**12,700 km 更接近地球的平均直径（12,742 km）**，作为赤道直径偏小约 56 km。 | 应为「equatorial diameter ≈ **12,756 km**；polar diameter ≈ 12,714 km，短约 **43 km**」。**「约短 40 km」这部分是对的**，错的是赤道直径本身。 |
| `Lecture`，Slide 9 配图说明；及转写对应段 | 讲义："**Sea level is 106 m below MSL** over the Indian Ocean Geoid low"；转写："sea level is **106 meters below the sea level** there" | **表述自相矛盾**：海平面不可能比「平均海平面（MSL）」低 106 m。此处混淆了「相对于参考椭球」与「相对于平均海平面」两个基准。 | 应为「**该处大地水准面（≈海面）比参考椭球面低约 106 m**」，即 **geoid height N ≈ −106 m**，这是全球最负的大地水准面异常。 |
| `Lecture`，Slide 10 | "Uses the **OSGB36 coordinate reference system: tied to mean sea-level at Newlyn, Cornwall**." | **水平基准与垂直基准混为一谈。** **OSGB36 是水平大地基准/坐标参考系统**（拟合 Airy 1830 椭球）；系于 Newlyn 验潮站的是英国的**垂直基准 ODN（Ordnance Datum Newlyn）**。两者常打包使用，但不是同一个东西。 | 应为「OSGB36（水平基准，Airy 1830 椭球）+ **ODN（垂直基准，系于 Newlyn 验潮站平均海平面）**」。 |
| `Lecture`，Slide 10 | "GB **ETRS89** ... **– a version of WGS84** (World Geodetic System 1984)." | **等价关系表述过强。** ETRS89 在 **1989.0 历元**与 WGS84 重合，但此后**固连于欧亚板块稳定部分随板块移动**，而 WGS84 是全球框架。三十余年、约 2.5 cm/yr 的板块运动使两者今日已相差**数十厘米**。 | 应为「ETRS89 是**在 1989.0 历元与 WGS84 一致、此后固连于欧亚板块的欧洲区域参考框架**」，不是 WGS84 的一个版本。 |
| `Lecture`，Slide 10 | "GPS uses the global WGS84 ... **This is tied to the global GRS80 ellipsoid**." | **椭球指认不严格。** WGS84 有**自己的椭球（WGS84 ellipsoid）**，其长半轴与 GRS80 相同（6,378,137 m），扁率定义方式略有不同，导致短半轴相差约 **0.1 mm**。 | 应为「WGS84 使用 **WGS84 椭球，与 GRS80 几乎完全相同（差异在亚毫米级），工程上可视为同一椭球**」。**教程的说法在实用层面无害**，仅术语不严格。 |
| `Lecture`，Slide 3 | "Wolfenstein 3D (**1991**)" | **发行年份错误。** *Wolfenstein 3D* 由 id Software 于 **1992 年 5 月**发行；**1981 年**的是前作 *Castle Wolfenstein*（转写中老师提到的 "started back in 1981" 是对的）。 | 应为 **Wolfenstein 3D (1992)**。 |
| `Lecture`，Slide 3 | "**I.D. games**" | **公司名拼写错误。** | 应为 **id Software**（全小写 "id"，取自弗洛伊德的「本我」）。 |
| `EART29102 - 21-Apr-transcript.md`，Wolfenstein / Doom 段 | "as soon as games like **Doom** came along and you could start jumping up onto levels ... then **you've got access to the third dimension**" | **技术史判断不准确。** *Doom*（1993）的地图数据结构同样限制每个平面位置只能有**一组地板/天花板高度**（不支持 room-over-room），且不能真正垂直瞄准，业界通常仍将其归为 **2.5D**。第一款真正三维的主流引擎是 **Quake（1996）**。 | 该例子的教学价值在于「raycasting 是 2D 渲染技巧」的类比，**不宜引用为严格的技术史结论**。 |
| `transcript`，Ordnance Survey 段 | "it produces a **triangular irregular network grid**, which expands from Newlyn" | **用词与 GIS 标准术语撞车，极易误解。** 此处指的是 19 世纪实地建立的**三角测量控制网（triangulation network）**，与 GIS 中的 **TIN（Triangulated Irregular Network，一种表面数据模型）** 是两个完全不同的概念。 | 应为 "**triangulation network**"。复习时务必区分：**GIS 的 TIN 是一种 2.5D 表面模型，本周并未讲授。** |
| `transcript`，印度测量段 | "the initial mapping of India ... started in **Bombay**, as it was at the time, and then moved outwards" | **史实错误。** 印度大三角测量（**Great Trigonometrical Survey**）由 William Lambton 于 **1802 年**在 **Madras（马德拉斯，今 Chennai）附近的 St. Thomas Mount** 起算基线，此后沿「大弧」（Great Arc）向北推进，不是从 Bombay 开始。 | 应为 **Madras / Chennai**。（转写中「northern India 误差仅 8–10 m」这一精度评价本身是站得住的。） |
| `transcript`，Digital space 段 | "**raster data is lines in space, things like roads.** Pixel data is what you find in raster information." | **数据模型说反。** **线状要素（道路）属于 vector（矢量）数据**，不是 raster。同一段后半句「Pixel data is what you find in raster information」才是正确的。 | 应为「**vector** data is lines in space, things like roads；**raster** data 由 pixel 组成」。讲义 Slide 11 的定义正确，**以讲义为准**。 |
| `transcript`，斑岩品位段 | "So they're relatively low grade. So **a good one might be sort of 2% copper**." | **与讲义矛盾。** 讲义 Slide 27 明写「Porphyry halos are large, low grade bodies: **a good one is 1% Cu**」，且「Supergene enrichment ... can enrich deposits to **>2%**」。老师在同一段后文也说「It could **double it from 1% to more than 2%**」，与讲义一致。 | **以讲义为准：原生斑岩优质矿体约 1% Cu，经表生富集后可达 >2%。** 口误处应读作 1%。 |
| `Lecture`，Slide 19 与 Slide 27 | Slide 19："IEA (**International Energy Association**)"；Slide 27："Witherly, **2003**: https://doi.org/10.1080/1443247**1.2023**.2287269" | **两处引用错误：** ①IEA 的正确全称是 **International Energy Agency（国际能源署）**，不是 Association；②DOI 中的年份为 **2023**，正文标注为 2003，相差 20 年。 | 分别更正为 **International Energy Agency** 与 **Witherly, 2023**（以 DOI 为准）。 |
| `Lecture`，Slide 24 | 正文出现占位符文本 "**sdsd**" | **PPT 未清理的占位字符**，无实际内容。 | 忽略。该 slide 的实际内容是 Park et al. (2021) 的两幅图与右侧四条要点。 |
| `Lecture`，Slide 21、Slide 22 | "**Nickle**"（两处）；"a car running on **hydroarbons**" | 拼写错误。 | 应为 **Nickel**、**hydrocarbons**。 |
| `Lecture`，Slide 17 vs `transcript` | 讲义："We will be slicing **this afternoon**"；转写：老师三次说 practical 在 **Friday** | 时间表述不一致（讲义为往年版本遗留，实际本年 lecture 在周二、practical 在周五）。 | 以转写为准：**practical 在周五**。不影响知识点。 |
| `EART29102 - 21-Apr-transcript.md`，YAML front-matter | `source: "Sophomore/Hilary Term/EART29102/Lecture/**Week 8**/EART29102 - 21-Apr-transcript.txt"` | **元数据路径错误**：该转写文件实际位于 `Lecture/Week 9/`，front-matter 中却写 Week 8。 | 应为 `Lecture/Week 9/`。（不影响内容，但按周检索时可能误导。） |
| `EART29102 - 21-Apr-transcript.md`（全篇，自动语音识别） | "**Creeging** / **Bayesian Creeging**"；"**Newland** in Cornwall"；"a **tied gauge**"；"real-time **chemetics**"；"**magnetic** plumes"；"**peak** distribution in the Netherlands"；"**Coda Brennan**"；"**Cabell-Herman** / **Cappel Herman**"；"**Athen Wen**"；"**Nickle**"；"**plectectonics**"；"World Geodetic **Reference** System of 1984"；"**battle lift**"（多次） | **ASR（自动语音识别）造成的专有名词误写**，非授课内容错误，但会严重妨碍阅读。 | 依次还原为：**kriging / Empirical Bayesian Kriging**；**Newlyn**；**tide gauge**；**real-time kinematic (RTK)**；**mantle plumes**；**peat distribution**；**Coed-y-Brenin**；**Capel Hermon**；**Afon Wen**；**nickel**；**plate tectonics**；**World Geodetic System 1984**；**batholith**（「battle lift」应为 batholith / 岩基，指下方的侵入体）。阅读转写时须自行还原。 |

