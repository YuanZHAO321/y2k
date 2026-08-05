# EART29102 Geospatial Techniques — Week 04 学习笔记

> 授课日：23-Feb ｜ 主题：空间分析（Spatial Analysis）
> 材料：`Lecture 4 - Spatial Analysis`（讲义）、`EART29102 - 23-Feb-transcript`（课堂录音转写，本课第一份 transcript）、`Practical 4 - Spatial analysis`（ArcGIS Pro 实操教程）

---

## 一、本周主题

### 1.1 本周在全课骨架中的位置

本课的整体结构是：**基础段**（W01 GIS 导论 → W02 空间数据与管理 → W03 数据输入与操作）→ **分析段**（**W04 空间分析** → W05 空间统计）→ **专题段**（W06 遥感 → W07 地形分析 → W08 空间可视化 → W09 三维技术）→ W10 课程回顾。

**本周是分析段的第一周，也是整门课的技术分水岭。** 老师在开场时把这个转折说得很直白：

> "So we're in week four now, then. So we're moving on from talking about how we put data in, how we process it in coordinate systems, and so forth, and now getting into sort of **the meat of the subject**, where we're talking about spatial analysis itself. So once we've got all the data into our GIS, **what can we do with it to solve particular problems that we have?**"

也就是说：
- 前三周解决的是「**怎么把数据弄进来、整理好**」——数据模型（矢量/栅格）、地理数据库、坐标系与投影、数据输入与编辑；
- 从本周开始，问题变成「**怎么用这些数据回答一个科学问题**」——查询、叠加、量测、邻域、插值。

老师还明确交代了本周与前后周的边界：
- **空间统计（statistics）放到下周（W05）讲**；
- **3D 相关内容放到后面几周（W09）讲**；
- 本周只覆盖 **spatial query / spatial operations / spatial interpolation** 三大块，加上时间维度（temporal change）的一句带过。

### 1.2 讲义列出的四条内容主线

讲义首页 "Lecture content" 明确列了四条：

1. **Concepts of spatial analysis and modelling**（空间分析与建模的概念）
2. **Spatial query using attributes and locations**（用属性与位置做空间查询）
3. **Spatial operations**（空间操作）
4. **Spatial interpolation methods and errors**（空间插值方法及其误差）

老师自己把整堂课归纳为三分法：**spatial query（空间查询）、spatial operations（空间操作）、spatial interpolation（空间插值）**。这三个词是本周最重要的骨架，后面所有内容都挂在它们下面。

> ⚠️ **重要提示（关于本课的 Practical 与 Lecture 的对应关系）**
> 本周 Lecture 的覆盖面很宽（查询、叠加、地图代数、量测、缓冲区、成本距离、插值），但 **Practical 4 只落在最后一块——空间插值**：用 ArcGIS Pro 的 **Geostatistical Wizard** 对非洲与中东的气温点数据做 **IDW** 与 **Kriging** 插值，并用交叉验证比较精度。老师在课上也点了名：
> "You're gonna be doing a practical this week where you'll do some **ordinary Kriging**."
> 复习时要注意：讲义里的叠加分析、地图代数、成本路径**本周没有对应实操**（叠加与缓冲区的实操在 Practical 2 已经做过，见下）。

### 1.3 与前几周实操的衔接

老师在课上两次回指前面的 practical，说明本周的很多概念其实已经"手先动过"：

- **Buffer**：「we've already done buffers in one of your practical exercises, so that's all about proximity.」
- **Overlay**：「you did an example of this when you worked out in your **second practical** the number of properties that were at risk of flooding around the rivers in **Carlisle**, if you remember that.」

所以本周 lecture 的作用之一，是把前几周实操里"照着做"的工具，回填上概念框架和分类体系。

### 1.4 本周作业与评估提示

- 读课程教材 **第 5 章：Spatial Analysis**。
- 在 **Canvas** 上做本周的 **quiz**（自测基础理解）。
- 推荐 ESRI 培训课程 *Getting started with spatial analysis*（**只做 components 1–3**，约 1 小时 15 分钟）。
- 老师口头补充：「**I will, this week, I will put up the assessment for you** so you can have a look at that. It's not due in until **week 11** or something. So you've got plenty of time.」——即本周会发布计入成绩的 assessment，截止在第 11 周左右。

---

## 二、核心概念

### 2.1 空间分析的定义与用途

讲义给出的定义：

> **Spatial analysis** = *A set of methods used to query features based on their attributes or analyse how layers interact spatially.*
> （一组方法：既可以基于**属性**查询要素，也可以分析多个**图层在空间上如何相互作用**。）

用途：**identify patterns（识别模式）、associations（关联）、evidence of change through time and location（随时间与位置的变化证据）**。

讲义把空间分析拆成三个子类（这是本周最重要的三分法）：

| 子类 | 英文定义（讲义原文要点） | 中文理解 |
|---|---|---|
| **空间查询 Spatial query** | filtering and selecting data from a geodatabase based on **attributes and location** | 从地理数据库里"筛"出想要的记录，依据是属性值或空间位置 |
| **空间操作 Spatial operations** | a type of spatial query class that includes operations such as **intersection, containment, and distance calculations** for objects in a given region or point | 在查询之上做几何运算：相交、包含、距离计算等 |
| **空间插值 Spatial interpolation** | estimates **unknown values** at specific locations based on **known values** from surrounding points | 用已知点的值推测未知点的值，生成连续面 |

老师在课堂上还展示了一张"空间分析类型总览图"（见第三节图表描述），把常见空间分析分成六类：**network（网络）、overlay（叠加）、proximity（邻近）** 在上排，**statistics（统计）、3D、temporal change（时间变化）** 在下排。

### 2.2 空间查询（Spatial query）

讲义把空间查询分成两类：

**（1）Query by attribute（按属性查询）**
> *To retrieve all features with particular **attribute** values from one data layer or feature class in a spatial database and display their locations in a map.*

即：从一个图层/要素类里取出满足某属性条件的所有要素，并在地图上显示它们的位置。

**（2）Query by location（按位置查询）**
> *To find features from one or multiple data layers based on their **locations** relative to features from another layer in the same spatial database.*
> *To identify **attribute** values associated with features at particular locations.*

即：依据要素相对于**另一图层要素**的空间位置来筛选；也可以反过来，问"这个位置上的要素有哪些属性值"。

**关键限定（来自转写，讲义没写）**：老师明确说空间查询**基本上只适用于矢量数据**：
> "And really, this only really applies to **vector data**. Raster data has a way of doing spatial query, but that's based on something called **map algebra**."

**（3）Feature class 的复习定义（老师口头给的）**
> "feature class in a GIS ... is something which has a **common geometry**. So it's a sort of layer with either made up of lines, points, or polygons that share attribute features and also location. **They're all on the same coordinate system.**"

即：要素类 = 同一种几何类型 + 共享属性结构 + 同一坐标系的一组要素。

### 2.3 用 SQL 表达查询

多数 GIS 支持 **SQL（Structured Query Language，结构化查询语言）**，且 SQL 不是 GIS 专有的，普通数据库也用它。

**属性查询示例**（问题：*Retrieve all water mains installed before 2010 with a diameter less than 30 cm*，"取出所有 2010 年前安装、口径小于 30 cm 的自来水干管"）：

```sql
SELECT * FROM w_mains WHERE "year" < 2010 AND "diameter" < 30
```

讲义解释：**WHERE 子句**把结果过滤到同时满足两个条件的干管。

**位置查询示例**（问题：*Select all buildings that intersect with a given park*，"选出与某个公园相交的所有建筑"）：

```sql
SELECT * FROM buildings WHERE ST_Intersects(buildings.geometry,
(SELECT geometry FROM parks WHERE name='Whitworth'))
```

讲义解释：**`ST_Intersects` 函数**检查每栋建筑的几何是否与 Whitworth Park 的几何相交。讲义强调：*There are a large number of ST_geometry functions that can be used in a GIS.*

**`ST` 是什么？** 老师口头解释：
> "ST in that context ... **ST just means spatial type**. And there's lots of spatial type statements that you can use in SQL language."

**不会写 SQL 怎么办？** 老师特别安抚了这一点：
> "if you can't be bothered to learn SQL, most GISs now allow you to **build up clauses yourself** so you don't need to type them in in SQL."

讲义的截图示例（Page 7 OCR）展示的正是 ArcGIS Pro 的 **Select By Attributes** 对话框：
- **Input Rows**：`USA_Major_Cities`
- **Selection Type**：`New selection`
- 用 **+ Add Clause** 逐条加子句：`Where POPULATION is greater than 10000` **And** `FEMALES is greater than MALES`
- 界面上有 **Load / Save / Remove**、**Invert Where Clause** 选项
- 有一个开关可以把可视化子句**切换成 SQL 视图**，显示为：`POPULATION > 10000 And FEMALES > MALES`

老师用这个例子说明：选出"人口大于 10000 且女性多于男性"的美国城市，结果在地图上以蓝色点显示；处理的记录数从 3,305 条缩减到 5 条（截图中 "Records to be processed" 的变化）。

### 2.4 地理处理操作：Dissolve / Merge / Reclassify

这三个是讲义标题 "Geoprocessing operations (merge, reclassify and dissolve)" 下的一组操作。讲义正文只给了一句定义：

> *Assigning new values to raster dataset cells based on their pre-existing values is known as **reclassification** in GIS.*
> （在 GIS 中，根据栅格单元已有的值给它们赋新值，叫做重分类。）

**老师在课堂上的口头解释更完整、更好用**（讲义没有这些）：

| 操作 | 老师的解释 | 效果 |
|---|---|---|
| **Dissolve（融合）** | "dissolve just combines polygons together. So if they've all got the same attribute ... we don't need these different polygon shapes. We can just merge them all together to give us a much simpler output." | **同一图层内**，把属性相同的相邻多边形合并，**消除内部边界** |
| **Merge（合并）** | "Merge is where you're combining **different spatial data sets**. So here we've got data which are overlapping, but they're stored in **different data layers** and they can be merged together." | **跨图层**，把多个数据集合成一个图层 |
| **Reclassify（重分类）** | 见下面的森林/农业例子 | **重新编码属性值**，把多个类别归并成更粗的类别 |

**老师的 Reclassify + Dissolve 连用示例（很重要，考试与理解都容易用到）**：
一张土地覆盖图，原本有 **coniferous（针叶林）** 和 **deciduous（阔叶林）** 两类林地，以及 **corn（玉米）** 和 **soybean（大豆）** 两类农地。
1. 用 **Reclassify** 把针叶林+阔叶林 → **forest**，玉米+大豆 → **agriculture**。结果：属性简化了，**但多边形的形状边界还在**（老师特别指出右下角还能看到不同林型的多边形轮廓）。
2. 再用 **Dissolve** 去掉这些残留边界，得到真正简化的地图。

老师给的**应用场景**：
> "this is the kind of thing you might do, for example, **if you're changing the scale of your map**. So you've got to make it much simpler to look at if you're going to change the scale by a large amount."

> 📎 **背景补充**：讲义的定义句只提到"栅格单元"，但老师的演示是对**矢量多边形属性**做重分类。实际上 ArcGIS Pro 里 `Reclassify`（Spatial Analyst 工具）是栅格工具，矢量的等价做法通常是改字段值 + `Dissolve`。材料没有区分这两条路径，复习时注意讲义定义与课堂示例的对象不同。

### 2.5 叠加分析（Overlay analysis）

讲义定义：
> *A process of **stacking multiple data layers with a common georeferencing system** on top of each other so that the relationships between features at each location can be analysed.*
> *The most common GIS operation for comparing and analysing multiple data layers simultaneously. E.g. calculating the number of properties within a flood risk zone.*
> *Overlay analysis can be conducted using either **vector or raster** data.*

**前提条件（老师强调）**：所有图层必须在**同一投影、同一坐标系**下：
> "It's the process of stacking multiple data layers with a common georeferencing system. So they're all on the same projection, the same coordinate system."

**课程内的实例**：Practical 2 里算"卡莱尔（Carlisle）河流周边有多少房产处于洪水风险中"。

#### 2.5.1 矢量叠加（Vector overlay）

讲义定义：*Two or more vector layers are combined to produce **new geometries**.*

老师按参与叠加的几何类型分了三种情形：

| 组合 | 老师的描述 | 输出 |
|---|---|---|
| **Point in polygon（点在多边形内）** | 一层是点数据，一层有两个多边形 | **统计每个多边形内点的个数** |
| **Line in polygon（线在多边形内）** | 一层是一条河流，一层是两个多边形 | 合并层里每个多边形各自带上落在其内部的**河段** |
| **Polygon on polygon（多边形叠多边形）** | 两个多边形叠合 | "more complex"——两个多边形合成 **4 个新多边形** |

#### 2.5.2 四种多边形叠加运算

讲义原句：*Typical overlay operations include **union**, **intersection**, and **difference** — named after the result of the combination of two layers.*

老师用**一个圆 + 一个正方形**演示了四种运算（绿色 = 输出图层）：

| 运算 | 老师的描述 | 输出几何 |
|---|---|---|
| **Intersection（相交）** | "here we're looking at the intersection area of those two shapes" | **只保留两者重叠的部分** |
| **Union（并集）** | "a way of just combining the two shapes together ... the output would just be a combination of the two shapes" | **保留两者的全部范围** |
| **Symmetrical difference（对称差）** | "excludes the overlap part. So the output wouldn't have this part within it" | 两者的全部范围**减去重叠部分**（"甜甜圈"式，重叠处挖空） |
| **Difference（差集）** | "just excluding **the whole of the overlap of the circle on the square**" | 从一个图形中**整块减去另一个图形**（保留方形中未被圆覆盖的部分） |

老师的总结句：
> "So you can look at these layers **visually**, but you can also **create new layers** based on how you combine them together. And there are tools in a GIS to allow you to do all of these things."

> 📎 **背景补充（ArcGIS Pro 对应工具名，材料未给出）**：讲义与转写只给了**概念名**，没有给 ArcGIS Pro 的工具名。对应关系大致是：Intersection → `Intersect`；Union → `Union`；Difference → `Erase`；Symmetrical difference → `Symmetrical Difference`；另有 `Identity`（以输入图层范围为准叠加）。**本周材料完全没有提到 `Erase`、`Identity`、`Clip` 这些工具名**，这一条属于外部补充，考试若按讲义出题，只需掌握概念名与几何效果。

#### 2.5.3 栅格叠加与地图代数（Raster overlay / Map algebra）

讲义定义：
> *Raster overlay superimposes at least two input raster layers to produce an output layer. **Each cell in the output layer is calculated from the corresponding cells in the input layers**.*

**关键前提（老师明确强调，是易错点）**：
> "To be able to combine rasters or use overlay, **the grids need to have the same number of cells and cover the same spatial area**. And there are tools within a GIS to allow you to **reprocess rasters** so that they meet those criteria. ... if your current rasters have different cell sizes, you can reprocess that data to get it into another cell size that allows you to do the map algebra."

**Map algebra 的运算类型**（讲义 Page 13 OCR 的表格）：

| Type（类型） | Operators/functions（运算符/函数） |
|---|---|
| **Arithmetic**（算术） | `+`, `−`, `×`, `÷`, square, square root, exponentials, logarithms |
| **Logical**（逻辑） | `AND`, `OR`, `NOT` |
| **Relational**（关系） | `=`, `>`, `<`, `≥`, `≤`（OCR 有损，原表为常见比较运算符） |
| **Conditional**（条件） | `IF…THEN…`, `IF…THEN…ELSE` |
| **Trigonometric**（三角） | (inverse) cosine, (inverse) sine, (inverse) tangent |
| **Statistical**（统计） | maximum, minimum, mean, range, standard deviation, sum, median, majority, minority, variety |

老师对这张表的态度：
> "**I don't expect you to remember these**, but just really an awareness that when you're combining raster layers using map algebra, you can use lots of different ways of doing that, different mathematical functions."

**老师逐格演算的例子**（很直观，务必掌握）：两个栅格层，各格有数值。
- **加法**：对应格相加（如 3+2=5，2+3=5，0+5=5）。
- **减法**：layer1 − layer2（如 3−2=1，2−3=−1）。
- **最大值 / 最小值 / 平均值**：逐格取 max / min / mean。
- **条件运算**：`IF (layer1 > 2) AND (layer2 > 1) THEN 1 ELSE 0`
  - 第一格：layer1=3 > 2 为真；layer2=2 > 1 为真 → **两个条件都满足 → 输出 1**
  - 第二格：layer1 不 > 2 为假；layer2 > 1 为真 → **必须同时满足 → 输出 0**

**为什么栅格更方便？** 老师的结论：
> "generally **raster data are much easier to combine in this way**. It's much more **efficient** to do that than it is to sort of do some of the overlay operations that we just described for vector data."

### 2.6 几何与距离量测（Geometric and distance measurement）

讲义要点：
> *Length, area, perimeter and shape. Useful for **landscape metrics** e.g. interaction between spatial pattern and ecological processes.*
> *Geometric properties and distances are **usually not encoded during spatial data input**. GIS offers measurement functions to calculate them.*

老师强调的一句（考点感很强）：
> "these geometric properties are **not encoded** into the spatial data input. **They're actually calculated for you. You have to ask it to calculate these numbers for you. They're not stored anywhere.**"

**矢量下怎么做**：在**属性表（attribute table）**里用 **Calculate Geometry** 选项。

**栅格下怎么量测**（讲义标题 "Measuring length, perimeter and area in raster"，细节由老师口头给出）：
- **长度（水平/垂直线）**：数格子数 × 单个格子边长。
- **长度（对角线）**：用格子的对角线长度来累加（略复杂）。
- **面积**：数多边形内部的格子数 × 单格面积。
- **周长**：直觉做法是数外围格子；但 **GIS 实际用的是"数内部边"的方法**——逐行数边、再逐列数边，把结果加起来（老师说这个例子得到 30），因为每条共享边由两个格子各贡献一次，所以要**乘 2**。
  > 老师的免责声明："Doesn't really matter, you don't need to, **you wouldn't be asked to do that kind of thing, so don't worry about learning it too much**, just trying to explain it."
  > 📎 **背景补充**：转写对这段的描述含糊（数出 30 后为何乘 2，与最终周长如何换算成长度单位，转写没交代清楚），且老师明说不会考。**不建议在这一点上深究。**

### 2.7 邻域之一：缓冲区（Buffers）

讲义定义：
> *Buffering is a **distance measurement tool for vector data** commonly available in GIS. It creates a **zone around a feature or a set of features with a specific width**.*

老师补充：
- 可以围绕**点、线、面**任意一种做缓冲，距离任意；
- **"Usually, we tend to dissolve the boundaries between the different buffers to make them continuous."**（通常会**融合**相邻缓冲区的边界，让它们连成一片）；
- 讲义示例：**沿道路的 500 m buffer**。

### 2.8 邻域之二：成本距离面与最小成本路径

**Cost distance surface（成本距离面）**，讲义定义：
> *Cost-distance analysis measures **how costly, or expensive, it is to travel over a surface**.*
> *Simulates how a mover will **experience** the landscape as they travel through it. This is different from **Euclidean distance**, which captures how far a mover is from known locations in a **straight line**.*
> *Cost can be measured in **topography, time, money, energy expended**, or other forms.*

老师的直觉解释（很好用）：
> "if I go from A to B, I can draw a straight line and I'll get there. And that's what we call the **Euclidean distance**. But obviously, that might involve a lot of cost. So if you imagine there's **a big mountain in the way**, then I have to go up and down the mountain. There's a huge cost there in time, energy, et cetera, risk, perhaps. So it might be easier if I **go around the mountain**."

**Least cost path（最小成本路径）**，讲义定义：
> *Calculates the lowest cost from a location to every other location and creates a **distance surface in raster form**.*
> *A least cost path represents the **most efficient route** through the landscape. e.g. wildlife corridors in fragmented habitat (foraging, range), pipeline or road planning, rescue operations, etc.*

**输出是什么**：一张按成本高低配色的**成本面（cost surface）**，上面叠加一条（或多条）**最小成本路径**。

**应用领域**（讲义 + 老师）：破碎生境中的**野生动物廊道**、**管线选线**、**道路规划**、**搜救行动**。

#### 刺猬案例（Balbi et al. 2019）

讲义引用：Balbi et al (2019), https://doi.org/10.1016/j.jenvman.2019.04.124
> *Different hedgehog movement patterns depend upon the degree of predicted connectivity in urban landscapes. In **highly connecting contexts (HCC)**, hedgehogs followed predicted **low cost path (LCP)** corridors, whereas in **unconnected contexts (UCC)** movements were **random**.*

老师口头补充的细节（讲义没有）：
- 研究区在**法国北部的 Rennes（雷恩）**；
- 他们先做出一张**阻力面（resistance surface）**——就是成本面的另一种叫法——用灰阶显示：**深灰 = 高成本/高阻力，浅灰 = 低成本**；
- 再算出一张由绿线构成的**最小成本路径网络**；
- 成本准则基于对刺猬的**吸引或阻隔**因素：道路、建筑、铁路、水道等（刺猬会尽量避开）；
- 然后**释放 30 只刺猬**，放在两类地点：**HCC（白点，路径连通性高）** 与 **UCC（黑点，不连通）**，用**无线电追踪**；
- 结果：**高连通区的刺猬走得更远、更快**；低连通区的刺猬移动是随机的；
- 现实意义（老师的话）："if you were a sort of **town planner** and you were worried about hedgehogs getting run over ... you might not want to **interrupt some of those pathways** which the hedgehogs were following."

### 2.9 空间插值（Spatial interpolation）

讲义定义：
> *Estimating values of an environmental variable at locations whose values are **unknown**, based on a **sample of locations with known values**.*
> *Apply an interpolation method to a set of points with known values to create a **continuous surface**.*
> *Environmental data are often collected as **discrete observations at points**.*
> *Two common methods: **Inverse Distance Weights (IDW) = deterministic** and **Kriging = geostatistical**.*

老师的场景化解释：
> "let's imagine each one of these dots is a **meteorological station** that's recording precipitation ... and let's say I want to go to this point here, which is a known location, but I don't have any precipitation data for that actual point. So what we're trying to do is **interpolate what the precipitation should be at that point** by looking at the precipitation values in the **neighbouring** meteorological stations."

并且强调：目标不是求某一个点，而是**求整个连续面**：
> "we're not interested necessarily in a single point, but we want to see **how the precipitation varies across that surface**."

**IDW 与 Kriging 的根本区别（老师反复强调，最重要的一句）**：
> "**IDW is what we call deterministic. So it just estimates a value** ... Whereas **kriging is something we call stochastic or geostatistical, which means it estimates a value AND an error**. So it's got some element of randomness built into the method that allows us to work out the error."

老师同时提醒：两者出的图**看起来可能很像**——
> "if you compare them, they look fairly similar. So sometimes, depending on your application, **it doesn't really matter which one you use**."

### 2.10 反距离权重（IDW, Inverse Distance Weights）

讲义：
> *IDW estimates a value of each location by taking the **distance-weighted average** of the values of sample points in its neighbourhood.*
> *Explicitly assumes that things closer to one another are more alike than those further apart (**Tobler's first law of geography**).*
> *As value **p** increases, the weights for distant points decrease rapidly. If the p is very high, **only the immediate surrounding points** will influence the prediction.*

变量定义（讲义给出）：
- `z_p` = interpolated value（待求的插值结果）
- `z_i` = known value at points（已知点的值）
- `d_i` = distance of points from `z_p`（已知点到待求点的距离）
- `p` = power term（幂次项）

老师的直觉说明：待插值点周围有几个已知点（例如值为 10 和 12），距离不同；IDW **就是用距离给平均值加权**。

**IDW 的局限（老师口头总结，讲义没有，很可能是考点）**：
1. **p 值难定**："knowing what this value of P should be is kind of hard. So what value should I use for my power in the equation?"
2. **p = 2 时出现"牛眼"（bullseye）图案**，看起来不真实。
3. **不适合地形起伏大的区域**："It's **not a good method for landscape studies**. So if you're looking at topographic profiles and trying to interpolate elevation data, and you've got a very large amount of relief ... a lot of ridges, mountains, valleys, it doesn't work very well."
4. **空间自相关只是假设、没有被检验**："this idea of spatial autocorrelation is **assumed. It's not actually tested.** And that's an important underlying assumption."
5. 优点：**非常快、计算高效**，适合先看个大概。

### 2.11 空间自相关（Spatial autocorrelation）与 Tobler 第一定律

讲义：
> *Spatial autocorrelation is a **statistical measure of Tobler's first law of geography**: "Everything is related to everything else, but **near things are more related than distant things**".*
> ***Positive** spatial autocorrelation is when **similar** values cluster together.*
> ***Negative** spatial autocorrelation is when **dissimilar** values cluster together (i.e. nearby locations are more different than expected by chance).*
> *Spatial autocorrelation is an **underlying assumption of spatial interpolation**.*

老师的天气类比：
> "if me and you are standing **10 meters apart**, we experience very similar weather to each other ... If I'm **one kilometer away** from somebody else, we could have quite different meteorological conditions."

三种状态（对应课件上的三格示意图）：
- **正自相关（+）**：相似值聚在一起；
- **零（random）**：随机分布；
- **负自相关（−）**：不相似值聚在一起，"more different from each other than we expect by chance"，即**分散（dispersed）**，不是随机。

老师预告：**下周（W05）会大量讲空间自相关。**

### 2.12 克里金（Kriging）

讲义：
> *Kriging **interpolates values and their probability** at a specific location.*
> *Uses input data to build a mathematical function with a **semivariogram**, to create a **prediction surface**, and then validate the model with **cross-validation**.*
> *A geostatistical method that provides an **optimal prediction surface AND a measure of confidence** in how likely that prediction will be true.*

**命名来源**（老师口头）：以**南非采矿工程师 Krige** 命名。
> 📎 **背景补充**：转写把名字记作 "Danny Crigg"，正确拼写应为 **Danie G. Krige**（南非采矿工程师）。这是自动转写的拼写错误，已列入文末勘误表。

#### 半变异函数（Semivariogram）

讲义公式：
```
Semivariogram(distance) = 0.5 × average( (value_i − value_j)² )
```
> *The formula involves calculating the **difference squared** between the values of the paired locations.*
> *The image shows the **pairing of one point (the red point) with all other measured locations**. This process continues for each measured point.*

老师的构建过程（比讲义清楚得多）：
1. 有一个未知点（红点），周围是有测量值的点（黑点）；
2. **算距离**——待求点到各已知点的距离（这一步跟 IDW 一样）；
3. **算方差**——已知点两两之间数值的方差：`(value_i − value_j)² / n`；
4. **乘 0.5** → 得到该距离下的**半方差（semivariance）**；
5. 把所有点对的（距离，半方差）画成散点图 → **横轴 = distance/lag（距离或滞后），纵轴 = semivariance**；
6. 对散点**拟合一个数学模型**（曲线）。

**为什么曲线随距离上升？** 老师的解释直接呼应 Tobler 定律：
> "these points here are all quite close ... so we'd expect the variance to be **much lower** between them ... But as we increase that distance between points, they become **less similar** to each other. So the **variance increases**. And that's why we see this increasing semi-variance as the distance increases **until we reach a point where there's no change in the variance**."

#### 三个关键参数：Nugget / Sill / Range

讲义标题 "Range, sill and nugget"，正文只有一句：*The semivariogram defines the **spatial structure** that kriging uses to **weight data points**.* 具体含义全部来自转写：

| 参数 | 定义（老师原话要点） | 物理含义 |
|---|---|---|
| **Nugget（块金值）** | "this is where the curve comes down and **intersects the y-axis** ... at a distance of 0 separation" | 理论上距离为 0 时方差应为 0，但实际有一个**正的截距**。原因：**测量误差**（如温度测量 ±1 °C）或 **microscale variability（微尺度变异）**——极短距离上快速变化的现象。老师玩笑："Got some strange names. It's all to do with **mining**." |
| **Sill（基台值）** | "this is the **maximum variance** in our data. So the curve folds over here and goes flat." | 半方差达到的**平台值**，即数据的最大方差 |
| **Range（变程）** | "the **distance at which the sill appears** is known as the range" | 空间自相关**消失**的距离；超过 range 的点对之间不再相似 |

**Kriging 与 IDW 的加权差别**：
> "Kriging uses that **nugget, sill and range** to work out the weighting of the points. So it's **more sophisticated than inverse distance weights, which just depend upon the distance**. There's more taken into account during Kriging."

#### Kriging 的类型

讲义列出：**Ordinary kriging（普通克里金）**、**Simple kriging（简单克里金）**、**Universal kriging（泛克里金）**、**Co-kriging（协同克里金）**。

讲义只对 Ordinary kriging 给了定义：
> ***Ordinary kriging** uses a **linear combination of the observed data values, with weights**, to make predictions of values at unmeasured locations.*

老师的态度：
> "there's lots of different ways of Kriging. You're gonna be doing a practical this week where you'll do some **ordinary Kriging**. And **ordinary Kriging is usually pretty good for most things**, but there are other methods of Kriging **which we won't go into**."

#### Kriging 的误差评估

讲义 "Kriging error analysis" 给出的指标：

| 指标 | 讲义定义 | 判读标准 |
|---|---|---|
| **Count** | number of known values | 已知点个数 |
| **Mean** | average difference between known and predicted values | **应接近 0** |
| **RMSE**（Root-Mean-Square Error） | prediction accuracy | **应尽可能小** |
| **RMSS**（Root-Mean-Square Standardized） | — | **应接近 1** |
| **R²** | "Can use R² as estimate of model quality" | 越接近 1 越好 |

### 2.13 插值误差的来源

讲义 "Sources of error in interpolation" 列了四条：

1. **Errors inherent in interpolation method**（方法本身的误差）——用 **RMSE** 或 **r²** 度量。
2. **Sample data uncertainty**（样本数据的不确定性）——采样点**太少**、分布**受限或成簇（clustered）**、位置和/或数值本身不确定。
3. **Edge effects**（边缘效应）——研究区**边界附近**因为区域外没有样点，插值结果会**畸变**。
4. **Outliers**（离群值）——离群值会**显著影响 kriging 预测的准确性**。

---

## 三、公式与图表

### 3.1 反距离权重（IDW）公式

讲义只给了变量定义（`z_p`、`z_i`、`d_i`、`p`），公式本体在幻灯片图片里、md 中未提取出来。

> 📎 **背景补充（公式代数形式）**：IDW 的标准形式为
>
> ```
>           Σᵢ ( zᵢ / dᵢᵖ )
>   z_p =  ─────────────────
>           Σᵢ ( 1 / dᵢᵖ )
> ```
>
> 即：每个已知点的权重 `wᵢ = 1 / dᵢᵖ`，加权平均后即为待求点的估计值。**这个代数式是我补的，材料只给了变量含义和文字描述。**

**逐项解释（材料里的解释）**：
- `dᵢ`：已知点到待求点的距离。老师指出它"**在分子和分母中都以倒数形式出现**"（"it's got an inverse relationship, both in the numerator and in the denominator"）——分母上的 `Σ 1/dᵢᵖ` 是归一化项，保证所有权重之和为 1。
- `p`（power term，幂次）：**控制距离衰减的速度**。
  - `p = 0`：所有邻域点权重相等（这条来自 Practical：*"If Power is 0, all points in the neighborhood are weighted equally."*）；
  - `p` 越大，权重随距离**衰减越快**；
  - `p` 很大（如 5）时，"**only the immediate surrounding points will influence the prediction**"；
  - Practical 中优化得到的 `p = 3.1076`，被描述为"a surface that appears **more localized and less general**"。
- 老师提醒：**"you don't need to remember any of these equations"**。

### 3.2 半变异函数公式

```
Semivariogram(distance) = 0.5 × average( (valueᵢ − valueⱼ)² )
```

**逐项解释**：
- `valueᵢ − valueⱼ`：一对点（i, j）之间的数值差；
- **平方**：消除正负号，得到差异的量级；
- `average(...)`：对**同一距离段（lag）内的所有点对**取平均——老师的表述是 `(valueᵢ − valueⱼ)² / n`，即方差；
- **乘 0.5**：这就是"**semi**"（半）的来源——把方差折半得到半方差。

### 3.3 栅格量测公式

| 量 | 计算方式（讲义/转写） |
|---|---|
| **长度（水平或垂直）** | 格子数 × 格子边长 |
| **长度（对角）** | 用格子的对角线长度累加（老师："slightly more complicated"） |
| **面积** | 多边形内格子数 × 单格面积 |
| **周长** | GIS 的做法是"**数内部边**"：逐行数、逐列数，求和后 **× 2**（因为每条边由相邻两格各贡献一次）。老师明确说**不会考**。 |

### 3.4 交叉验证统计量（Practical 用到的判读规则）

| 统计量 | 判读方向 | 出处 |
|---|---|---|
| **Mean** | 越接近 **0** 越好；正/负偏说明模型**系统性高估或低估** | Practical §4.3 + 讲义 |
| **Root-Mean-Square (RMS/RMSE)** | 越接近 **0** 越好；单位与被插值变量相同（例：2.5 °C = 平均预测偏离实测约 2.5 °C） | Practical §4.3, §4.4 |
| **Root-Mean-Square Standardized (RMSS)** | 越接近 **1** 越好（**唯一的例外**！） | Practical §5 + 讲义 |
| **Average Standard Error (ASE)** | 应与 **RMS 接近**；差距大 → *"the prediction is **unstable**"* | Practical §5 |
| **R²（goodness of fit）** | 实测 vs 预测散点的拟合优度，越接近 1 越好 | Practical §5.1 + 讲义 |

### 3.5 关键图表的文字复原（读到能自己画出来）

**图 A｜空间分析类型总览（讲义 "Spatial analysis and modelling" 页）**
一张 2×3 的图标网格。**上排从左到右：Network（网络）、Overlay（叠加）、Proximity（邻近）**；**下排：Statistics（统计）、3D、Temporal change（时间变化）**。老师逐格点评：overlay 已讲过一点，本课细讲；proximity 就是 buffer（practical 已做）；network 是最小成本路径/面（找最短路线、管线选线、野生动物廊道）；statistics 下周讲；3D 后面几周讲；temporal 与空间维度并列关注。

**图 B｜Select By Attributes 对话框（讲义 Page 7）**
左半是美国地图，点数据为主要城市；执行查询后，满足条件的城市变为**蓝色点**。右半是三个叠放的 **Select By Attributes** 对话框，自上而下展示同一个查询的三个阶段：
1. **Input Rows** = `USA_Major_Cities`，**Selection Type** = `New selection`，下方 Expression 区用可视化子句拼出 `Where POPULATION is greater than 10000` + `And FEMALES is greater than MALES`，底部有 `+ Add Clause` 和 `Invert Where Clause` 复选框；
2. 同一对话框显示 "Records to be processed: **3,305**"（全量）；
3. 点击 SQL 切换按钮后，Expression 区变成纯文本：`POPULATION > 10000 And FEMALES > MALES`，处理记录数缩到 **5**。

**图 C｜Reclassify + Dissolve 的两步简化**
- 左上：原始土地覆盖图，四种颜色 = coniferous forest（针叶林）、deciduous forest（阔叶林）、corn（玉米）、soybean（大豆），多边形形状破碎。
- 中：**Reclassify 后**——只剩两种颜色（forest / agriculture），**但多边形轮廓线仍在**（右下角尤其明显，能看到原本两种林型之间的分界）。
- 右：**Dissolve 后**——内部边界全部消失，成为两大块连续色斑。

**图 D｜三种矢量叠加的几何组合**
三行示意，每行左边两个"输入图层"，右边一个"输出图层"：
1. **Point in polygon**：输入 = 一堆散点 / 两个多边形；输出 = 两个多边形，各自标注内部点数。
2. **Line in polygon**：输入 = 一条蜿蜒的河流线 / 两个多边形；输出 = 两个多边形，各自带着落在自己范围内的**那一段**河流。
3. **Polygon on polygon**：输入 = 两个部分重叠的多边形；输出 = **4 个新多边形**（A 独有、B 独有、A∩B、以及切分出的残块）。

**图 E｜四种叠加运算的圆与方对照（最重要的一张，务必能默画）**
四个并排小图，每个都是**一个正方形 + 一个与它部分重叠的圆**，**绿色阴影 = 输出**：
1. **Intersection**：只有正方形与圆的**重叠区域**是绿色。
2. **Union**：正方形与圆的**全部覆盖范围**都是绿色（外轮廓是两者的合并轮廓）。
3. **Symmetrical difference**：正方形与圆的全部范围是绿色，**唯独中间重叠部分被挖空（白色）**。
4. **Difference**：只有**正方形上未被圆覆盖的部分**是绿色（圆整块被减掉，包括圆超出正方形的部分也不保留）。

**图 F｜Map algebra 的逐格运算**
两张 3×3（或类似）小栅格并排，格内写着整数（如 Layer1 有 3、2、0…；Layer2 有 2、3、5…），中间一个运算符，右边是输出栅格。分别演示：
- **加法**：3+2=5、2+3=5、0+5=5 → 输出格全是 5（老师用这组数强调"对应格相加"）；
- **减法**：3−2=1、2−3=−1 …（**输出可为负值**）；
- **Maximum / Minimum / Mean**：逐格取最大/最小/平均；
- **条件**：`IF layer1 > 2 AND layer2 > 1 → 1 ELSE 0`，输出是一张**0/1 二值栅格**（第一格 1、第二格 0，如 2.5.3 演算）。

**图 G｜500 m 道路缓冲区**
底图是一片道路网（线要素）。每条道路两侧各生成 500 m 宽的带状面；由于道路密集，相邻缓冲带互相重叠——**融合（dissolve）后**成为一片连续的、无内部分割线的绿色（或半透明）多边形，形状像道路网被"加粗涂抹"了一遍。

**图 H｜成本面 + 最小成本路径**
一张色阶地图（例如红=高成本、绿/蓝=低成本），代表穿越该地表的困难程度。上面画着一条从起点蜿蜒到终点的线——它**不是直线**，而是绕开高成本区（如山体），沿低成本走廊延伸。对比：**Euclidean distance** 会是起点到终点的直线段。

**图 I｜刺猬案例图（Balbi et al. 2019）**
主图是 Rennes 市域的**灰阶阻力面**：深灰 = 高阻力（道路、建筑、铁路、水道），浅灰 = 低阻力（绿地、花园）。上面叠加一张**绿色线网**——最小成本路径（LCP）走廊。图上散布两类圆点：**白点 = HCC（高连通情境，LCP 交汇密集处）**，**黑点 = UCC（不连通情境）**。左上角一个小插图（inset map）标出 Rennes 在法国北部的位置。30 只刺猬从这些点释放并被无线电追踪；结果是白点释放的个体**移动距离更远、速度更快**并沿 LCP 走廊活动，黑点释放的个体**移动随机**。

**图 J｜IDW 的 p 值对比（两幅年降水图）**
左图 **p = 1**：色斑大而柔和，等值区域连成大片，整体**平滑**（老师："it smooths out the surface"，远处点影响被放大）。
右图 **p = 2**：每个观测点周围出现**同心圆状的"牛眼（bullseye）"**——近处值主导，围绕站点一圈圈套色，整体**看起来不真实**。

**图 K｜空间自相关三态**
三个并排小方格图，各含若干深/浅色单元：
- 左（标 **−**，negative）：深浅**交替排布**如棋盘——不相似值相邻，比随机更分散；
- 中（标 **Random**）：深浅**杂乱无规律**；
- 右（标 **+**，positive）：深色成一块、浅色成一块——**相似值成簇**。

**图 L｜半变异函数图（必须能画）**
- **横轴**：Distance（或 lag），单位 m / km；
- **纵轴**：Semivariance（半方差）；
- 散点自左下向右上分布，拟合出一条**先上升、后变平**的曲线；
- **Nugget**：曲线（外推）与纵轴的交点，**位于 0 以上**——用一小段竖直标注标出；
- **Sill**：曲线变平后的**水平渐近高度**——用一条水平虚线标注；
- **Range**：曲线**首次到达 sill 的横轴位置**——用一条竖直虚线从曲线拐平处落到横轴。

**图 M｜Practical 的非洲插值成果三联图**
1. **点数据图**：非洲与中东上密布的气象站点（共 **704** 个），按 8 月平均气温着色；注意撒哈拉/中非某些区域**站点稀疏**。
2. **Kriging 预测面**：连续色带，**暖色 = 高温**；用 **Oceans 图层做 mask** 后，海洋部分被遮住，只保留陆地。
3. **Standard Error 面**：整体偏红；**深红 = 标准误大 = 可信度低**，浅色 = 可信度高。误差最大的区域正好是**海洋**（没有采样点）和**站点稀疏的内陆区**——与图 1 的点密度呈镜像关系。
4. 另有 **measured（x）vs predicted（y）散点图**：理想情况下所有点落在 **1:1 线**上；以及**半变异函数图**（能看出 nugget、水平的 sill，range 在右侧较远处）。
5. 汇总统计示例（老师给的非洲数据）：**Count = 704，Mean = −0.06 °C，Root-Mean-Square = 2.2 °C**。

**图 N｜Geostatistical Wizard 的搜索邻域（search neighborhood）**
预览地图上叠着搜索邻域的示意圆：
- **Neighborhood Type = Standard** 时：**只有一个圆**；
- **Neighborhood Type = Smooth** 时：**三个同心圆**（内圈权重高、外圈权重渐减）。
圆内的样点会被着色区分权重：**红点 = 影响力大，绿点 = 影响力小**。

**图 O｜直方图（Practical §2）**
横轴为温度值，纵轴为频数，柱状分布上叠一条**黑色正态曲线**（勾选 **Show Normal distribution** 得到）。
- 用 **Jan Avg. Temp C** 时：分布**明显偏斜、不呈钟形**，取值范围 **−10.2 至 30.1 °C**；
- 换成 **Aug Avg. Temp C** 时：更接近**钟形**——这就是后续选用 8 月字段的理由。

---

## 四、课堂补充（transcript 提炼）

本周是本课**第一份完整课堂转写（6,374 词）**。以下都是**讲义上没有、或讲义只有标题而内容全靠口头**的部分。

### 4.1 关于本课的定位与节奏

- 老师开场就点明本周是"**the meat of the subject**"（这门课的正题、核心肉）。
- 时间紧："**there's a fair amount to cover, so I won't dwell on anything too long**"——这解释了为什么讲义很多页只有标题、内容全在口头。**这也意味着 transcript 对本周尤其关键，讲义单独看会有大量空洞页。**
- 明确划界：statistics → 下周；3D → 后面几周；**spatial join query 本课不讲**——"I'm not going to talk about spatial join query. **You can probably find that information about that in the book.**"

### 4.2 老师明说"不用记"的内容（省力清单）

这几处非常有价值，能帮你把复习精力放对地方：

| 内容 | 老师原话 |
|---|---|
| Map algebra 的完整函数表 | "**I don't expect you to remember these**, but just really an awareness that ... you can use lots of different ways" |
| IDW / 半变异函数的方程 | "**you don't need to remember any of these equations**" |
| 栅格周长的"数内部边"算法 | "**you wouldn't be asked to do that kind of thing**, so don't worry about learning it too much" |
| 其他 kriging 变体（simple/universal/co-kriging） | "there are other methods of Kriging **which we won't go into**" |

**反过来说，老师反复强调、语气加重的地方就是重点**：deterministic vs geostatistical 的区别、Tobler 第一定律与空间自相关是插值的**前提假设**、栅格叠加要求同 cell 数同范围、几何属性**不被存储**必须计算、nugget/sill/range 的含义。

### 4.3 讲义没有、只在口头出现的概念澄清

1. **空间查询主要是矢量的事**：栅格没有"按属性/位置查询"，它靠 **map algebra**。这是一条经常被忽略的分界。
2. **`ST` = spatial type**：SQL 里的 `ST_Intersects` 等一整族函数的前缀含义。
3. **不必学 SQL**：现代 GIS 提供子句构建器（clause builder），并且可以**一键在可视化子句与 SQL 文本之间切换**——老师演示了这一点，并说"So I didn't actually have to write anything"。
4. **Dissolve / Merge 的根本差别**：**Dissolve = 同一图层内合并属性相同的多边形**；**Merge = 跨图层把不同数据集合成一个**。讲义把这两个词和 reclassify 挤在一个标题下，很容易混。
5. **Reclassify 之后往往还需要 Dissolve**：重分类只改属性、**不会消除已有的多边形边界**。这一层"两步走"的关系是纯口头内容。
6. **换比例尺是重分类+融合的典型动机**："if you're going to change the scale by a large amount"。
7. **栅格更适合叠加**：矢量叠加要生成新几何、计算量大；栅格逐格运算**更高效**。
8. **几何属性不存储**：长度、面积、周长**不在数据里**，要用属性表的 **Calculate Geometry** 现算。
9. **Buffer 通常要 dissolve**：否则相邻缓冲区之间残留分割线。
10. **成本的多样性**：不只是地形，还可以是时间、金钱、能量消耗、风险——"**that's what makes it so useful**"。
11. **IDW 的 p 值选择是实践难题**，且 p=2 会出"牛眼"；**IDW 不适合高起伏地形的高程插值**。这两条都是讲义里没有的、很具体的经验之谈。
12. **空间自相关是"被假设"而非"被检验"**——这是 IDW 最根本的方法论弱点，也是转向 kriging 的动机。
13. **nugget ≠ 0 的两个原因**：测量误差、微尺度变异（microscale variability）。老师举例："say you're measuring temperatures and there's an error of plus or minus 1 degree."
14. **kriging 术语来自采矿业**："Got some strange names. **It's all to do with mining.**"（nugget = 金块，sill = 窗台/基台，都是矿业隐喻）。
15. **半变异函数曲线上升的物理解释**：距离近 → 相似 → 方差小；距离远 → 不相似 → 方差大；到某个距离后不再变化。

### 4.4 老师给的真实案例（三个，都可能出现在应用题里）

**（1）刺猬与城市连通性（Balbi et al. 2019, Rennes, France）**
详见 2.8。要点链条：**阻力面 → LCP 网络 → 按连通性分 HCC/UCC 释放 30 只刺猬 → 无线电追踪 → 高连通区移动更远更快 → 城市规划应避免切断这些路径**。这是把 GIS 分析结果**用实地实验验证**的完整闭环，是很好的"技术如何服务决策"的例子。

**（2）香港海洋塑料污染（Coleby and Grist 2019）**
讲义引用：https://doi.org/10.1016/j.ocecoaman.2018.12.021。用**半变异函数 + kriging**绘制香港及邻近海域的海洋塑料污染分布，并同时出**误差面（kriging variance）**。
老师强调的**解读方法**（这是本案例的真正价值）：
> "it allows you to focus on places where obviously most of the marine plastic pollution is occurring, **but also to look at areas where you might have fairly low** ... For example, here we've got relatively low error measurements but we don't have very much indication of a pollution in that area. So why is that? So basically allows us to **look for places where we have a higher uncertainty and then perhaps take more measurements in those areas**."
即：**误差面的用途不只是"打分"，更是"指导下一轮采样布点"**。

**（3）东非裂谷地壳厚度（Kebede et al. 2024）**
用 kriging 从离散的重力测点生成 **Main Ethiopian Rift（MER）的 Bouguer 异常图**。老师解读：**红色（亮色）= 地壳较薄，蓝/绿 = 地壳较厚**——由此可从点数据做出**地壳厚度图**。这是本课少见的、直接对口地球科学的例子。
> 📎 **背景补充**：讲义在这一页的图注里把参考链接错写成了塑料污染那篇的 DOI（见勘误表），Kebede et al. (2024) 的正确出处材料未给出。

### 4.5 老师对本周 Practical 的预告（与实操完全对应）

老师在课末直接放了 practical 的成果图：
- 数据 = 覆盖**非洲**的气象站，各站有**逐月**平均气温；
- 用 **kriging** 做出**温度插值图**（暖色 = 高温）；
- 同时得到**误差面**——"where you have higher errors, you get darker colors. And you can see that where you get higher errors is generally **where you have less data**"；
- 半变异函数图上可以指认 nugget、sill、range；
- 用插值面**反算每个站点的预测值**，做 **predicted vs measured** 散点，期望落在 **1:1 线**上；
- 汇总统计：**704 个站，Mean = −0.06 °C（越接近 0 越好），Root-Mean-Square = 2.2 °C（越小越好）**。老师顺带提了一句 "**Root mean square is something we did last week**"（RMSE 概念在 W03 已出现过）。

---

## 五、Practical 要点

**教程来源**：Esri Learn Team，官方维护版 https://learn.arcgis.com/en/projects/interpolate-temperatures-using-the-geostatistical-wizard/
**软件**：ArcGIS Pro（需 **Geostatistical Analyst** 扩展）
**数据**：从 ArcGIS Online 下载 **InterpolateTemperatures** 项目包（project package）

### 5.0 学习目标（教程原文）

完成后应能：
- 从**采样点数据集**生成非洲与中东的**连续温度图**；
- 用**直方图**分析样本数据的分布；
- 用 **IDW** 与 **kriging** 生成插值面；
- 用**交叉验证**比较不同插值面的精度；
- 为选定的插值面绘制**标准预测误差图**。

### 5.1 数据与背景

- 地图显示**非洲与中东**的温度点数据；**每个点存储各月的平均温度**（字段如 `Jan Avg. Temp C`、`Aug Avg. Temp C`）。
- 教程给出的**插值适用条件**（重要判据）：
  > *Spatial interpolation works best when the data points are **fairly evenly distributed**, are **densely populated**, and the amount of **variation looks similar across the area**.*
- 项目里还有一个 **Oceans** 图层，后面用作 **mask**。
- **先看分布再插值**的原则（教程 §1）：
  > *The first step before undertaking any geospatial interpolation is to **visualize the data** and check that it is not highly skewed, has any extreme outliers and generally follows a **normal distribution**.*

### 5.2 步骤一：做直方图，检查数据分布（§2）

1. **Contents pane** 中**右键** `Temperature` 图层 → **Create Chart** → **Histogram**。
   - 结果：**Chart Properties** 面板 + 一个空的图表视图（chart view）同时出现。
2. 在 **Chart Properties** 面板：
   - **Number** 设为 **`Jan Avg. Temp C`**（1 月平均温度，摄氏）；
   - **勾选 `Show Normal distribution`**（显示正态分布曲线）。
3. **读图（检查点 1）**：数值范围为 **−10.2 至 30.1 °C**。黑色曲线是正态分布参考线；1 月平均温度的分布**不是正态**的（教程原文说 "skewed to the right"，见勘误表）。
   - 教程提醒：坐标轴上显示的数值**会随面板宽度变化**。
4. 把 **Number** 改为 **`Aug Avg. Temp C`**。
   - **读图（检查点 2）**：8 月温度**更接近正态分布**。
   - 教程原则：*Interpolation methods are **most effective when the data is close to a normal (bell-shaped) distribution**, and **some geostatistical methods require** that the data be normally distributed.*
5. 检查**离群值（outliers）**，并记录 **skew（偏度）** 与 **kurtosis（峰度）**：

   | 统计量 | 教程定义 | 判读 |
   |---|---|---|
   | **Kurtosis（峰度）** | *a measure of how sharp or flat the peak is* | **0 = 正态**；负 = 比正态更扁平；正 = 比正态更尖峭 |
   | **Skew（偏度）** | *a measure of the symmetry of the distribution* | **0 = 对称**；正 = 向正值方向偏斜；负 = 向负值方向偏斜 |

   > 教程的经验阈值：***For both kurtosis and skew a value between −1 and +1 is usually taken to be a normal distribution.***
6. **替代检查法：Normal QQ Plot**（在 **Create Charts** 菜单里）。
   - 原理：*compares how your data lines up with normally distributed data. If all points have a perfectly normal distribution, all your points would fall on the **45° line**.*
   - 教程说本数据的点基本落成一条直线，并要求 "Try this for yourself"。
7. **关闭 chart view**。
8. **Contents pane** 右键 `Temperature` → **Symbology** → **Field** 改为 **`Aug Avg. Temp C`**。
   - **检查点 3**：地图更新为 8 月温度的符号化显示。

### 5.3 步骤二：确认 Geostatistical Analyst 扩展（§3）

- 路径：**Project** > **Licensing** > **Esri Extensions**，确认 **Geostatistical Analyst** 复选框**已勾选**。
- 若未勾选：点 **Configure your license options**，从列表中选择 Geostatistical Analyst。之后 **Geostatistical Analyst 工具条**会被加入。
- 教程说明：**Geostatistical Wizard** 提供多种插值方法，*Usually, you will **not know which one to use until you have tried several and compared their results**.*

### 5.4 步骤三：检查坐标系必须是投影坐标系（§4.1）— 关键前置

1. **Contents pane** 右键 `Temperature` → **Properties** → 打开 **Layer Properties: Temperature**。
2. 点 **Source** 选项卡 → 向下滚动 → 展开 **Spatial Reference**。
3. **检查点 4**：表格**第一个参数应为 `Projected Coordinate System`**。
4. **为什么必须是投影坐标系**（教程原文，是本周最重要的原理性提示之一）：
   > *Geostatistics relies on **distance measurements**. To **minimize the distortion** of these distances, your input data must use a **projected (rather than geographic) coordinate system**. You can assign one using the **Project** geoprocessing tool.*
5. **本数据用的投影**：**Equidistant Conic（等距圆锥投影）**，中心落在非洲。
   > *There is **no projection that can perfectly preserve all distances**, but **equidistant projections will do a better job** of this than others. The choice of projection is **more important when mapping a large area**, such as a continent.*
6. 点 **Cancel** 关闭 Layer Properties。

### 5.5 步骤四：IDW 第一次（IDW Smooth）（§4.2）

**方法说明（教程）**：*IDW is a **mathematical (deterministic, i.e. non-geostatistical)** method that assumes closer values are more related than further values ... It is one of the **simpler** methods to apply.*

| 步骤 | 操作（英文原名 + 路径） | 参数 |
|---|---|---|
| 1 | **ribbon → Analysis 选项卡 → Workflows 组 → Geostatistical Wizard** | — |
| 2 | 在 **Deterministic methods** 下选 **Inverse Distance Weighting**（可能需要向下滚动才能找到） | — |
| 3 | **Data Field** | **`Aug Avg. Temp C`** |
| 4 | 点 **Next** | — |
| 5 | 在预览地图上**点击不同位置**，在 **Identify Result** 区看该处的预测温度 | — |
| 6 | **General Properties → Neighborhood Type** | 改为 **`Smooth`** |
| 7 | **Smoothing Factor** | 确认为 **`0.2`** |
| 8 | 点 **Finish**，在 **Method Report** 窗口点 **OK** | — |

**检查点 5（搜索邻域的可视化）**：
> *When **Neighborhood Type is Standard**, there is **only one circle** on the preview map. When it is **Smooth**, there are **three concentric circles**. The circles represent the **search neighbourhood**. To predict a new value, **only the sample points that are nearby—within the search neighbourhood—are considered**.*

**重命名图层**：**Contents pane** 中选中 `Inverse Distance Weighting` → **properties** → 改名为 **`IDW Smooth`**。

**加海洋掩膜（mask）**：
- 目的：*use the **Oceans** layer as a **Mask** to restrict the temperature interpolation to the **continental areas***（把插值结果限制在陆地）。
- 操作：选择 **Geostatistical Layer** → **Masking** → 勾选标签为 **`oceans`** 的复选框。
- **常见问题（教程明确提示）**：*Note you **may need to click the layer off then on again** to see the masking.*（掩膜不生效时，把图层关掉再打开刷新。）
- **检查点 6**：地图现在显示了**原本没有温度数据的位置**的预测值。

### 5.6 步骤五：IDW 第二次——优化 Power（IDW Smooth Optimized）（§4.3）

1. **Analysis** 选项卡 → **Geostatistical Wizard**。
2. 确认方法仍是 **Inverse Distance Weighting**，**Data Field** 仍是 **`Aug Avg. Temp C`** → **Next**。
3. **Neighborhood Type** → **`Smooth`**。
4. 点 **Power** 参数旁的 **Optimize** 按钮。
   - **检查点 7**：**Power 值变为 `3.1076`**。
   - 教程解释：*Not all the points in the search neighborhood are considered equal. Those that are **nearer** to the location being predicted are given **more weight**. **If Power is 0, all points in the neighborhood are weighted equally.** The **higher the power, the more rapidly the weights decrease with distance**. A higher power of 3.1 results in a surface that appears **more localized and less general**.*
5. 展开 **Weights**，滚动列表查看**不同颜色的权重**。
   - 列表 = 搜索半径内的所有点及其权重；点击列表里的值，预览地图上会高亮对应点。
   - **配色含义：`Red points will exert more influence over the prediction than green ones.`（红点影响大，绿点影响小）**
6. 折叠 **Weights** → **Next** → 进入 **Cross validation** 页面。
   - **交叉验证的原理（教程原文）**：*It does this by **removing a single point** from the dataset and using **all remaining points** to predict the value of the removed point.*
     > 📎 **背景补充**：这个做法的通用名称叫 **leave-one-out cross-validation（留一交叉验证）**；教程只描述了过程，没有给这个名字。
   - **散点图判读**：*The scatter plot compares predicted values (on the x-axis) to measured values (on the y-axis) and is considered **best when the thin gray line coincides with the thick blue line**.*（细灰线 = 1:1 参考线，粗蓝线 = 回归线，两者重合最好。）
   - **Mean**：*tells you if the model is **skewed toward predicting values that are too high or too low**. It is **best when it is closest to 0**.*
   - **Root-Mean-Square**：教程记录**约 2.5**，含义是 *on average, the predicted temperature values differed from the measured values by about **2.5 °C***。
7. **Method Report** 窗口点 **OK** → 新图层加入地图。
8. 同样用 **oceans** 图层做 **Mask**。
9. 重命名为 **`IDW Smooth Optimized`**。
10. **Contents pane** 中**关闭 `Temperature` 点图层**。
11. 反复**取消勾选/勾选 `IDW Smooth Optimized`**，与 `IDW Smooth` 对比，记录差异。

### 5.7 步骤六：比较两个 IDW 的交叉验证结果（§4.4）

1. **Contents pane** 中**同时选中** `IDW Smooth` 与 `IDW Smooth Optimized`。
   - **技巧（教程注）**：*To select more than one layer, press the **Shift** key while selecting layers.*
2. **右键 → Cross Validation**。
   - 会弹出**两个** Cross validation 窗口（一个会挡住另一个），**把窗口挪开以便并排比较**。
3. 看 **Summary** 选项卡：*The closer the **Root-Mean-Square** value is to **0**, the more accurate the created surface is.*
   - **结果（教程给的确切数值，检查点 8）**：
     - **`IDW Smooth Optimized`：Root-Mean-Square = 2.4998`**
     - **`IDW Smooth`：Root-Mean-Square = 2.669`**
   - **结论**：Optimized 误差更小 → **更可靠**。
4. 关闭两个 Cross validation 窗口。
5. **Contents pane** 中只选 `IDW Smooth` → **右键 → Remove**（删除较差的那个面）。
6. 点 **Quick Access Toolbar** 上的 **Save** 按钮保存工程。

**教程对 IDW 的总评（结论性，值得背）**：
> *Inverse distance weighting is considered an **easy and fast** interpolation method. It is good for **getting an initial picture** of the phenomenon you are mapping, and sometimes you may need to use it because it will **follow measured values exactly**. But it can also produce a **ring effect around islands in your data**.*
> （"ring effect around islands" 就是老师课上说的 **bullseye/牛眼**现象。）

### 5.8 步骤七：Ordinary Kriging，默认参数（Kriging Default）（§5）

**教程的方法定位**：*Kriging is a **very flexible** geostatistical method. This means that you can **adapt it in many ways** to suit your data, but it also means that there are **many more choices** that must be made.*

1. 打开 **Geostatistical Wizard**。
2. 在 **Geostatistical methods** 下选 **Kriging / CoKriging** → **Next**。
3. 在 **Ordinary Kriging** 下选 **Prediction**（生成预测值面，与前面 IDW 的产出可比）。
4. **本次使用全部默认参数** → 点 **Finish** → 点 **OK**。
5. 新图层加入地图 → 重命名为 **`Kriging Default`**。
6. **检查点 9**：与 `IDW Smooth Optimized` 对比——*The new layer is **much more general in its pattern**.*（kriging 默认面的图案更概化、更平滑。）

### 5.9 步骤八：Ordinary Kriging，调参（Kriging Modified）（§5）

| 步骤 | 操作 | 参数 / 说明 |
|---|---|---|
| 1 | 打开 **Geostatistical Wizard** | — |
| 2 | 确认方法为 **Kriging/CoKriging** → **Next** | — |
| 3 | **Ordinary Kriging** 下选 **Prediction** → **Next** | — |
| 4 | 在 **Semivariogram/Covariance Modeling** 页，把 **Function Type** 改为 **`Semivariogram`** | 默认可能是 Covariance |
| 5 | 点 **Optimize model** 按钮 | *finds the parameters that result in the **smallest prediction errors***。**检查点 10**：半变异函数图（semivariogram map）与部分参数会变化——教程说*"In this case, the change is **minimal**"*（本例变化很小） |
| 6 | **Next** → 在 **Searching Neighborhood** 页，把 **Sector Type** 改为 **`8 Sectors`** | 理由：*Increasing the number of sectors ensures that **neighbors are searched for in all directions**, and a **large cluster of nearby points in only one direction will not have all of the influence** over the predicted value.*（防止单一方向的点簇垄断预测） |
| 7 | **Next** → 查看 **Cross validation** 页 | **检查点 11**：*kriging provides you with **many more values** than inverse distance weighting*（kriging 的验证统计量比 IDW 多得多） |
| 8 | **Finish** → **OK** → 重命名为 **`Kriging Modified`** | — |

**检查点 12**：`Kriging Modified` 与 `Kriging Default` 对比——*They are **very similar**.*

### 5.10 步骤九：两个 kriging 面的交叉验证对比（§5）

1. **Contents pane** 中同时选中 **`Kriging Default`** 与 **`Kriging Modified`** → **右键 → Cross Validation** → 排好窗口并排看 **Summary** 选项卡。
2. **判读规则（本节的核心，务必记牢）**：
   - *Numbers **closer to zero** indicate better accuracy.*
   - ***The exception is Root-Mean-Square Standardized. In this case, values closer to 1 are desired.***
   - *If any of these values are **too far off**, you should **eliminate that layer**.*
   - 当两者都合格时，*you can use **Root-Mean-Square as the tie breaker** value*（用 RMS 做决胜指标）。
   - ***It is also desirable that the Root-Mean-Square and Average Standard Error values be close to one another. If there is a large difference between these values, it may indicate that the prediction is unstable.***
3. **教程给出的本例结论**：*It is **not immediately obvious** from these values which surface is better. **Kriging Default has better values for every category except Root-Mean-Square.** However, this does not necessarily mean it is better.*
   - 换言之：**指标之间会打架，需要按上面的规则做取舍**，不能只看一个数。

### 5.11 步骤十：用地理处理工具算 R²（§5.1）

目标：得到**实测值与预测值之间的拟合优度 R²（goodness of fit）**。

1. **ribbon → Analysis → Tools**，搜索 **`Cross validation`**（这次用的是 **geoprocessing 工具**，不是图层右键菜单）。
2. **Input geostatistical layer** = **`Kriging Default`**。
3. **Output point feature class** = **`Kriging default points`**。
   > 教程原文写作 "Output point class feature"，参数名顺序有误，见勘误表。
4. 点 **Run** → 新图层加入地图（每个样点带上 predicted 值）。
5. **对 `Kriging Modified` 重复同样操作**。
6. 用输出的点要素类做**散点图**：**x = 实测 `Aug Avg. Temp C`，y = `Predicted`**，读取 **R²** 值。

**教程对 kriging 的总评**：
> *Kriging is a **more advanced** method than IDW and requires you to make **more decisions**. But this allows you to **experiment with the parameters** until you find those that are a good fit for your data and phenomenon. Kriging also gives you **more tools to assess the accuracy** of your results, such as a **map of the standard error estimates**.*

### 5.12 步骤十一：绘制标准误差图（§6）

**动机（教程原文，很值得引用）**：
> *You have now made **four different surfaces** of temperature ... Each was interpolated from the **same data**, but each showed a **different surface**. Clearly these predictions are useful, but **they cannot be taken as fact**. Some parts of the surface (where there are many data points) can be considered more accurate ... It is useful to **map these degrees of uncertainty to aid decision makers**.*

1. **Contents pane** 中选中 **`Kriging Modified`**。
2. **ribbon → Geostatistical Layer 选项卡** → 把 **Display Type** 改为 **`Standard Error`**。
3. **检查点 13**：*The map changes to become **mostly red**.*
4. **Contents pane** 中**打开 `Temperature` 点图层**，与误差图叠着看。
5. **判读**：
   > *Standard errors are measures of **uncertainty** for the predicted values. The **dark-red** areas have **larger standard error** values and therefore **lower certainty**. **Lighter** areas are those where you can place **more trust**. This map suggests that the results have the **greatest standard error in the ocean**. This makes sense, because there were **no sample measurement points in the ocean** (although there were some on small islands).*
6. 把 `Kriging Modified` 的 **Display Type 改回 `Prediction`**。
7. **Save** 保存工程。

**收尾结论（教程）**：
> *Geostatistics can help you map many phenomena as **continuous surfaces** even though you only have **discrete point data** ... You may not have a weather station in your study area, but a set of weather stations in a **wider region** can provide the data you need.*
> *If you are going to **make decisions** based on an interpolated surface, **finding the most accurate model is critical**.*

### 5.13 挑战题（§7）与延伸资源（§8）

**Challenge Exercise（值得读，因为它提出了一个方法论问题）**：
> *The four maps you made were all derived from the **same input data**, but they **looked different** from one another. Now that you know how maps with interpolated surfaces are made, **do you trust them more or less?** Geostatistical models can be tweaked to create more accurate results. On the other hand, **the map maker might have an agenda that they want to promote, and they may tweak the geostatistical parameters to emphasize a trend.***

- 项目里还有**另外五张地图，每张对应一个大洲**：**Catalog pane → Project 选项卡 → Maps 文件夹**。
- 任务：换一个大洲**把整个流程重做一遍**。教程提醒：*For Africa and the Middle East, you found that **`Aug Avg. Temp C` was the best field**, and **`Kriging Modified` was the best surface**. For **another continent, you may find that different parameters yield better results**.*（不能照搬非洲的结论。）

**延伸资源**：
- ESRI 培训 *Geostatistical Interpolation*：https://www.esri.com/training/catalog/5d8a8c9055cf937306dba777/geostatistical-interpolation-introduction/
- Co-Kriging Interpolation of annual average temperature（ArcGIS StoryMap）：https://storymaps.arcgis.com/stories/62e633c7685847c0a5474080a276dcec

### 5.14 操作流水线速查（一页纸版）

```
1. Create Chart → Histogram        [Jan → 偏斜；Aug → 近正态 → 选 Aug]
2. Symbology → Field = Aug Avg. Temp C
3. Project > Licensing > Esri Extensions → Geostatistical Analyst ✔
4. Layer Properties > Source > Spatial Reference → 确认 Projected（Equidistant Conic）
5. Analysis > Geostatistical Wizard > Deterministic > IDW
     Data Field = Aug Avg. Temp C；Neighborhood Type = Smooth；Smoothing Factor = 0.2
     → Finish → 重命名 IDW Smooth → Geostatistical Layer > Masking ✔ oceans
6. 再来一次 IDW：Power → Optimize (= 3.1076) → 看 Weights（红>绿）→ Cross validation (RMS ≈ 2.5)
     → 重命名 IDW Smooth Optimized → mask oceans
7. Shift 多选两层 → 右键 Cross Validation → RMS 2.4998 vs 2.669 → 删除 IDW Smooth → Save
8. Geostatistical Wizard > Geostatistical > Kriging/CoKriging > Ordinary Kriging > Prediction
     → 默认参数 Finish → 重命名 Kriging Default
9. 再来一次：Semivariogram/Covariance Modeling → Function Type = Semivariogram → Optimize model
     → Searching Neighborhood → Sector Type = 8 Sectors → Finish → 重命名 Kriging Modified
10. 两个 kriging 层 → Cross Validation 对比（0 最好；RMSS 例外，1 最好；RMS 做 tie breaker；RMS≈ASE）
11. Analysis > Tools > 搜 "Cross validation"（GP 工具）
      Input geostatistical layer = Kriging Default；Output point feature class = Kriging default points → Run
      → 对 Kriging Modified 重复 → 散点图 measured(x) vs Predicted(y) → 读 R²
12. 选 Kriging Modified → Geostatistical Layer > Display Type = Standard Error
      → 打开 Temperature 对照 → 改回 Prediction → Save
13. Challenge：Catalog pane > Project > Maps 文件夹里换一个大洲重做
```

---

## 六、易错点 / 重点难点

### 6.1 概念辨析类

**（1）Dissolve vs Merge vs Reclassify —— 本周最容易混的三兄弟**

| | 作用对象 | 做什么 | 是否改变几何 |
|---|---|---|---|
| **Dissolve** | **同一图层内部** | 把**属性相同**的相邻多边形合并，**消除内部边界** | 是（边界消失） |
| **Merge** | **多个不同图层/数据集** | 合并成一个图层 | 否（几何原样保留，只是并到一起） |
| **Reclassify** | 单个图层的**属性值** | 把细类归并成粗类（如针叶林+阔叶林→forest） | **否！边界仍在，需再 Dissolve** |

**记忆钩子**：Dissolve 是"**溶掉线**"，Merge 是"**并图层**"，Reclassify 是"**改编码**"。

**（2）Union vs Merge —— 名字像，行为完全不同**
- **Union（叠加运算）**：两个多边形层做**几何叠加**，会在重叠处**打断、生成新的多边形**，输出保留双方的属性。
- **Merge（数据管理）**：只是把两个数据集**堆到一个图层里**，**不做几何求交**，重叠部分仍然是两个重叠的要素。

**（3）四种叠加运算的输出范围（务必对着图 E 记）**
- **Intersection ⊂ Union**；
- **Symmetrical difference = Union − Intersection**；
- **Difference** 是**有方向的**（A−B ≠ B−A），Symmetrical difference 是**无方向的**。
- 老师描述 difference 时用的是"**excluding the whole of the overlap of the circle on the square**"——注意结果只保留**方形**的非重叠部分，圆超出方形的部分**不保留**。这一点最容易和 symmetrical difference 搞混。

> 📎 **背景补充（Clip vs Intersect，材料完全未涉及）**：实际使用 ArcGIS Pro 时最常见的混淆是 **`Clip`** 与 **`Intersect`**：两者输出的**几何范围相同**（都是重叠部分），但 **`Intersect` 保留双方图层的全部属性字段**，而 **`Clip` 只用第二个图层做"饼干模具"裁形状，属性只保留输入图层的**。**本周讲义与转写都没有提到 `Clip`**，若考试按讲义出题不会考这一对，但做项目时会遇到。

### 6.2 栅格分析类

**（4）栅格叠加的前提条件必须先满足**
老师明确说：*the grids need to have the **same number of cells** and **cover the same spatial area***。若两张栅格的 **cell size** 或 **extent** 不同，必须**先重采样/重投影**再做 map algebra，否则要么报错、要么结果范围/分辨率异常。
> 📎 **背景补充**：在 ArcGIS Pro 中这通常通过 **Environments（环境设置）** 里的 **Extent** 与 **Cell Size** 统一，或用 `Resample` / `Project Raster` 工具处理。**"Environment 设置"这一说法本周材料没有出现**，是我补的实践要点。

**（5）条件运算要逐格判断"全部条件"**
`IF layer1 > 2 AND layer2 > 1` 中，**AND 要求两个条件同时成立**才输出 1。老师演示的第二格就是"一个真一个假 → 输出 0"。考试给两张小栅格让你填输出格，最容易在这里丢分。

**（6）几何属性不会自动存在**
长度、面积、周长**不在数据里**，必须主动用属性表的 **Calculate Geometry** 计算。误以为"属性表里应该有面积字段"是常见误解。

### 6.3 坐标系与距离类

**（7）插值必须用投影坐标系（Projected CS），不能用地理坐标系（Geographic CS）**
这是 Practical §4.1 花整节强调的事：*Geostatistics relies on distance measurements. To minimize the distortion of these distances, your input data **must use a projected (rather than geographic) coordinate system**.*
- 地理坐标系的单位是**度**，度在不同纬度对应的实际距离不同 → 距离计算失真 → 插值权重全错。
- 本数据用 **Equidistant Conic** 正是因为它**较好地保持距离**；且**研究区越大（如整个大洲），投影选择越关键**。
- 同理，**Buffer 的距离单位也依赖坐标系**：在地理坐标系下输入"500 米"会出问题。
  > 📎 **背景补充**：Buffer 单位与坐标系不匹配这一点，本周材料**没有明说**，是从同一原理推出的实践提醒。

### 6.4 插值方法类

**（8）IDW 与 Kriging 的根本区别，一句话必须能答**
- **IDW = deterministic（确定性）→ 只给一个估计值**；
- **Kriging = stochastic / geostatistical（地统计）→ 给估计值 + 误差（不确定性）**。
- 因此**只有 kriging 能出 Standard Error 面**（Practical §6 就是用 `Kriging Modified` 做的），IDW 做不出误差面。

**（9）p 值（Power）的方向不能记反**
- **p 越大 → 远处点权重衰减越快 → 面越"局部化"、越尖锐**；
- **p 越小 → 远处点影响越大 → 面越平滑**；
- **p = 0 → 所有邻域点等权**；
- **p = 2 容易出"牛眼/ring effect"**。
- 老师给的判据："If the p is very high ... **only the immediate surrounding points** will influence the prediction."

**（10）交叉验证指标的判读方向有一个例外**
- **Mean、RMS、ASE、以及大多数量 → 越接近 0 越好**；
- **Root-Mean-Square Standardized (RMSS) → 越接近 1 越好**（唯一的例外，最容易记反）；
- **额外一条**：**RMS 与 ASE 应彼此接近**，差距过大意味着 *the prediction is unstable*。

**（11）指标之间会互相矛盾，要有取舍策略**
Practical §5 明确说 Kriging Default 在**除 RMS 外的每一项**都更好，但**这不代表它就更好**；策略是：先看有没有指标"离谱"（离谱就淘汰该层），都合格时用 **RMS 做 tie breaker**。**不要只报一个数字就下结论。**

**（12）空间自相关是插值的"前提假设"，不是结论**
讲义："**Spatial autocorrelation is an underlying assumption of spatial interpolation.**" 老师加了一句关键的批评：IDW 里这个假设"**is assumed. It's not actually tested.**" —— 这正是转向 kriging（用半变异函数**实际刻画**空间结构）的动机。

**（13）Semivariogram 三参数的含义不能混**
- **Nugget** 在**纵轴上**（距离 = 0 处的**截距**，且**通常不为 0**）——原因是测量误差或微尺度变异；
- **Sill** 在**纵轴上**（曲线变平后的**高度** = 最大方差）；
- **Range** 在**横轴上**（曲线**到达 sill 的距离**）。
- 常见错误：把 range 说成"纵轴的平台值"，或以为 nugget 应该是 0。

**（14）负空间自相关 ≠ 随机**
负自相关是"**比随机更分散**"（不相似值相邻），随机是自相关**为 0**。三态顺序：**负（分散）— 0（随机）— 正（聚集）**。

### 6.5 实操流程类

**（15）Mask 不生效**
Practical 明确提示：*you may need to **click the layer off then on again** to see the masking.* 遇到掩膜不显示先别怀疑参数，先刷新图层。

**（16）Geostatistical Wizard 里找不到 Kriging**
先检查 **Project > Licensing > Esri Extensions** 里 **Geostatistical Analyst** 是否勾选。扩展没启用时，相关方法不会出现。

**（17）多选图层做对比要按 Shift**
`Cross Validation` 的**并排对比**功能要求**同时选中两个 geostatistical layer**（Shift + 点击），单选只会开一个窗口。

**（18）两个 "Cross validation" 不是同一个东西**
- 图层**右键菜单**里的 `Cross Validation` → 打开**统计窗口**（看数字）；
- **Analysis > Tools** 里搜到的 `Cross Validation` → 是**地理处理工具**，产出**点要素类**，用来做散点图和算 **R²**。
Practical §5.1 用的是后者，别走错入口。

**（19）字段选择要有理由**
选 **`Aug Avg. Temp C`** 而不是 `Jan Avg. Temp C`，理由是**8 月数据更接近正态分布**——不是随便挑的。挑战题也提醒：换一个大洲，**最佳字段和最佳参数可能不同**。

**（20）插值结果不是事实**
Practical 的原话值得记住：*these predictions are useful, but **they cannot be taken as fact***；而且挑战题直接点出**制图者可以通过调参来"强调某个趋势"**。做解释题时，"报告插值结果时必须同时报告不确定性"是一个高分点。

---

## 七、本周术语表

### 7.1 空间分析概念

| 英文 | 中文 | 说明 |
|---|---|---|
| Spatial analysis | 空间分析 | 基于属性或空间关系查询要素、分析图层交互的一组方法 |
| Spatial modelling | 空间建模 | 与空间分析并列出现的概念（讲义标题） |
| Spatial query | 空间查询 | 基于属性与位置从地理数据库中筛选数据 |
| Query by attribute | 属性查询 | 按属性值取出要素 |
| Query by location | 位置查询 | 按相对于另一图层的空间位置取出要素 |
| Spatial operations | 空间操作 | 相交、包含、距离计算等几何运算 |
| Spatial interpolation | 空间插值 | 由已知点值估计未知位置的值，生成连续面 |
| Feature class | 要素类 | 同一几何类型、共享属性与坐标系的一组要素 |
| Attribute table | 属性表 | 存储要素属性的表格 |
| Georeferencing system | 地理参考系统 | 叠加分析要求各图层共用同一套参考系 |
| Continuous surface | 连续面 | 插值输出的连续栅格表面 |
| Discrete observations at points | 离散点观测 | 环境数据常见的采集形式 |

### 7.2 查询与 SQL

| 英文 | 中文 | 说明 |
|---|---|---|
| SQL (Structured Query Language) | 结构化查询语言 | GIS 与普通数据库通用的查询语言 |
| `SELECT … FROM … WHERE` | 选择/来源/条件 子句 | 基本查询语法；WHERE 负责过滤 |
| `ST_Intersects` | 空间相交函数 | 判断两个几何是否相交 |
| ST (spatial type) | 空间类型 | SQL 中空间函数的前缀（老师解释） |
| ST_geometry functions | 空间几何函数族 | GIS 中可用的大量空间判断函数 |
| Clause | 子句 | 查询条件的组成单元 |
| Spatial join query | 空间连接查询 | **本课未讲**，老师建议看教材 |

### 7.3 地理处理与叠加

| 英文 | 中文 | 说明 |
|---|---|---|
| Geoprocessing | 地理处理 | GIS 的数据处理运算总称 |
| Dissolve | 融合 | 合并属性相同的相邻多边形，消除内部边界 |
| Merge | 合并 | 把不同数据集/图层合成一个 |
| Reclassify / Reclassification | 重分类 | 依据原有值给单元/要素赋新值 |
| Overlay analysis | 叠加分析 | 多图层叠放以分析各位置上要素的关系 |
| Vector overlay | 矢量叠加 | 组合矢量层生成新几何 |
| Point in polygon | 点在面内 | 统计各多边形内的点数 |
| Line in polygon | 线在面内 | 提取落在各多边形内的线段 |
| Polygon on polygon | 面叠面 | 两多边形叠加生成多个新多边形 |
| Union | 并集 | 保留两图层的全部范围 |
| Intersection | 交集 | 只保留重叠部分 |
| Difference | 差集 | 从一个图形中整块减去另一个 |
| Symmetrical difference | 对称差 | 两者的全部范围减去重叠部分 |
| Raster overlay | 栅格叠加 | 逐单元由多个输入栅格计算输出栅格 |
| Map algebra | 地图代数 | 栅格上的算术/逻辑/关系/条件/三角/统计运算体系 |
| Cell | 单元格 | 栅格的基本单位 |
| Cell size | 单元大小 | 栅格分辨率；叠加前须统一 |

### 7.4 量测与邻域

| 英文 | 中文 | 说明 |
|---|---|---|
| Calculate Geometry | 计算几何 | 属性表中计算长度/面积/周长的选项 |
| Landscape metrics | 景观指标 | 用几何量描述空间格局与生态过程的交互 |
| Perimeter | 周长 | 栅格中用"数内部边 × 2"的方式算 |
| Buffer / Buffering | 缓冲区 / 缓冲分析 | 围绕点、线、面生成指定宽度的带状区 |
| Proximity | 邻近性 | buffer 所属的分析类别 |
| Euclidean distance | 欧氏距离 | 两点间直线距离 |
| Cost-distance analysis | 成本距离分析 | 量测穿越地表的"代价" |
| Cost surface | 成本面 | 按成本高低着色的栅格面 |
| Resistance (surface) | 阻力面 | 刺猬案例中对成本面的叫法 |
| Least cost path (LCP) | 最小成本路径 | 穿越景观的最有效路线 |
| Network (analysis) | 网络分析 | 求最短/最优路线的一类分析 |
| Wildlife corridor | 野生动物廊道 | LCP 的典型应用 |
| HCC (highly connecting context) | 高连通情境 | 刺猬案例中的高连通释放点 |
| UCC (unconnected context) | 不连通情境 | 刺猬案例中的低连通释放点 |

### 7.5 插值与地统计

| 英文 | 中文 | 说明 |
|---|---|---|
| Inverse Distance Weights / Weighting (IDW) | 反距离权重（法） | 确定性插值，用距离加权求平均 |
| Deterministic method | 确定性方法 | 只给估计值，不给误差 |
| Geostatistical / stochastic method | 地统计 / 随机方法 | 给估计值**和**误差 |
| Power term (p) | 幂次项 | 控制距离衰减速度 |
| Kriging | 克里金（法） | 以 Krige 命名的地统计插值方法 |
| Ordinary kriging | 普通克里金 | 用观测值的加权线性组合做预测；本周 practical 所用 |
| Simple kriging | 简单克里金 | 讲义列出，未展开 |
| Universal kriging | 泛克里金 | 讲义列出，未展开 |
| Co-kriging | 协同克里金 | 讲义列出，未展开 |
| Semivariogram | 半变异函数（图） | 半方差 vs 距离的图；定义空间结构 |
| Semivariance | 半方差 | 0.5 × 点对差值平方的平均 |
| Lag | 滞后（距离） | 半变异函数横轴 |
| Nugget | 块金值 | 距离为 0 时的正截距；来自测量误差或微尺度变异 |
| Sill | 基台值 | 半方差的最大值（平台） |
| Range | 变程 | 到达 sill 的距离；空间自相关的作用范围 |
| Microscale variability | 微尺度变异 | nugget 的成因之一 |
| Spatial autocorrelation | 空间自相关 | Tobler 第一定律的统计度量；插值的前提假设 |
| Tobler's first law of geography | 托布勒地理学第一定律 | 万物相关，近者更相关 |
| Prediction surface | 预测面 | 插值输出的预测值表面 |
| Cross-validation | 交叉验证 | 逐点剔除、用余下点预测该点以评估精度 |
| Standard error (of prediction) | （预测）标准误 | 预测不确定性的度量；只有 kriging 能出 |
| Edge effects | 边缘效应 | 研究区边界附近因缺少外部样点造成的畸变 |
| Outliers | 离群值 | 会显著影响 kriging 预测 |
| Skew | 偏度 | 分布对称性；−1~+1 视为近正态 |
| Kurtosis | 峰度 | 峰的尖/扁；0 = 正态；−1~+1 视为近正态 |
| Normal QQ Plot | 正态 QQ 图 | 检查正态性的替代方法，点应落在 45° 线上 |
| RMSE / Root-Mean-Square | 均方根误差 | 越接近 0 越好 |
| Root-Mean-Square Standardized (RMSS) | 标准化均方根 | **越接近 1 越好**（唯一例外） |
| Average Standard Error (ASE) | 平均标准误 | 应与 RMS 接近，否则预测不稳定 |
| Mean (error) | 平均误差 | 越接近 0 越好 |
| R² / goodness of fit | 决定系数 / 拟合优度 | 实测 vs 预测的拟合程度 |
| Bouguer anomaly | 布格异常 | 东非裂谷案例中由 kriging 生成的重力异常图 |

### 7.6 ArcGIS Pro 界面与工具（本周 Practical 出现的全部英文名）

| 英文原名 | 类型 | 位置 / 用途 |
|---|---|---|
| **Contents pane** | 面板 | 图层列表；右键菜单入口 |
| **Catalog pane** | 面板 | 浏览工程内容；Challenge 里找 Maps 文件夹 |
| **Create Chart → Histogram** | 右键菜单 | 生成直方图 |
| **Chart Properties** | 面板 | 设置 Number 字段、Show Normal distribution |
| **Show Normal distribution** | 复选项 | 在直方图上叠加正态曲线 |
| **Normal QQ Plot** | 图表类型 | Create Charts 菜单中的正态性检查图 |
| **Symbology** | 右键菜单/面板 | 设置显示字段（Field） |
| **Project > Licensing > Esri Extensions** | 菜单路径 | 检查/启用扩展 |
| **Geostatistical Analyst** | 扩展模块 | 提供 Geostatistical Wizard 等 |
| **Configure your license options** | 按钮 | 启用扩展 |
| **Layer Properties > Source > Spatial Reference** | 属性路径 | 查看坐标系 |
| **Projected Coordinate System** | 坐标系类型 | 插值必需 |
| **Equidistant Conic** | 投影 | 本数据所用，居中于非洲 |
| **Project** (geoprocessing tool) | 工具 | 为数据赋投影坐标系 |
| **Analysis 选项卡 > Workflows 组 > Geostatistical Wizard** | 菜单路径 | 插值主入口 |
| **Deterministic methods** | 向导分组 | 内含 IDW |
| **Inverse Distance Weighting** | 方法 | IDW |
| **Geostatistical methods** | 向导分组 | 内含 Kriging/CoKriging |
| **Kriging / CoKriging** | 方法 | 克里金 |
| **Data Field** | 参数 | 选择被插值的字段 |
| **Identify Result** | 向导区域 | 显示点击处的预测值 |
| **General Properties** | 向导分组 | 含 Neighborhood Type |
| **Neighborhood Type**（`Standard` / `Smooth`） | 参数 | Standard = 1 个圆；Smooth = 3 个同心圆 |
| **Smoothing Factor** | 参数 | 本例设为 **0.2** |
| **Power** + **Optimize** | 参数 + 按钮 | 优化后得 **3.1076** |
| **Weights** | 向导列表 | 显示各点权重；**红 > 绿** |
| **Search neighbourhood** | 概念 | 参与预测的邻域范围 |
| **Method Report** | 对话框 | Finish 后的方法报告 |
| **Geostatistical Layer 选项卡** | 上下文 ribbon | 含 Masking、Display Type |
| **Masking** | 功能 | 用 `oceans` 图层限制插值范围到陆地 |
| **Display Type**（`Prediction` / `Standard Error`） | 参数 | 切换预测面与标准误面 |
| **Semivariogram/Covariance Modeling** | 向导页 | 半变异/协方差建模 |
| **Function Type**（`Semivariogram`） | 参数 | 改为半变异函数 |
| **Optimize model** | 按钮 | 求使预测误差最小的参数 |
| **Searching Neighborhood** | 向导页 | 设置搜索邻域 |
| **Sector Type**（`8 Sectors`） | 参数 | 保证各方向都搜索到邻居 |
| **Cross Validation**（右键菜单） | 功能 | 打开交叉验证统计窗口（Summary 选项卡） |
| **Cross Validation**（Analysis > Tools 中的 GP 工具） | 工具 | 输出带预测值的点要素类，用于算 R² |
| **Input geostatistical layer** | 参数 | GP 工具的输入 |
| **Output point feature class** | 参数 | GP 工具的输出（教程写作 "Output point class feature"） |
| **Quick Access Toolbar > Save** | 按钮 | 保存工程 |
| **Remove**（右键） | 命令 | 删除图层 |
| **Shift + 点击** | 操作 | 多选图层 |
| **InterpolateTemperatures** | 项目包 | 本次实操数据（ArcGIS Online 下载） |
| **Temperature** / **Oceans** | 图层名 | 温度点图层 / 海洋掩膜图层 |
| **IDW Smooth / IDW Smooth Optimized / Kriging Default / Kriging Modified** | 图层名 | 本次生成的四个插值面 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Practical 4 - Spatial analysis.md` §4 标题及目录第 4 条 | "Interpolate an average **annual rainfall** surface using Inverse Distance Weighting (IDW)" | 本练习插值的是**气温**（`Aug Avg. Temp C`），不是年降水量 | 应为 "Interpolate an average **August temperature** surface using IDW"。疑为从 ESRI 其他降水教程沿用的标题 |
| `Practical 4` §2，第一次生成直方图后 | "The chart view updates to show a histogram representing the **maximum** temperature values from the point data." | 字段是 `Jan Avg. Temp C`（**平均**温度），不是最高温度 | 应为 "**average** temperature values" |
| `Practical 4` §4.2，IDW 完成后 | "A new layer is added to the map, representing a surface of **maximum** temperature for the Africa region." | 同上，插值的是 8 月**平均**气温 | 应为 "a surface of **average August** temperature" |
| `Practical 4` §4.3（Cross validation 说明）与 §5.1（散点图要求） | §4.3："The scatter plot compares **predicted values (on the x-axis)** to **measured values (on the y-axis)**"；§5.1："Make scatter plots of **measured** `Aug Avg. Temp C` (**x**) versus **Predicted** (**y**)" | **两处轴向定义互相矛盾** | 两处应统一。ArcGIS Pro 交叉验证图与 §5.1 的要求一致（**x = measured，y = predicted**），§4.3 的表述疑有误。判读结论（细灰线与粗蓝线重合最好、越靠近 1:1 线越好）不受影响 |
| `Practical 4` §5.1，Cross Validation 地理处理工具参数 | "**Output point class feature** as Kriging default points" | 参数名词序错误 | ArcGIS Pro 中该参数名为 "**Output point feature class**" |
| `Practical 4` §2 | "the distribution of average temperatures in January is not normal, but rather it is **skewed to the right**" | **存疑**：该字段取值范围为 −10.2 至 30.1 °C，非洲与中东 1 月气温的直方图更可能呈**长左尾（skewed to the left / 负偏）** | 材料未给出实际 skew 数值，无法定论。**建议照做时读取实际 skew 值再判断**：正值 = 右偏，负值 = 左偏（教程自己在同一节给了这条判据） |
| `Practical 4` §5.1 与 §5 各处图层名 | "Kriging **default**"、"**Krigging** modified"、"Kriging Default" 混用 | 图层名大小写与拼写不一致（`Krigging` 多一个 g） | 统一应为 **`Kriging Default`** 与 **`Kriging Modified`**（与前文重命名步骤一致） |
| `Practical 4` 目录表 | "Introducton"、"distributon"、"Geostatstcal"、"Weightng"、"Optmising"、"validaton"、"statstcs"、"cofcient"、"estmates" 等 | 大量 PDF 提取造成的字符丢失（"ti" 连字被吞） | 均为 OCR/提取问题，非作者拼写错误。正确形式为 Introduction、distribution、Geostatistical、Weighting、Optimising、validation、statistics、coefficient、estimates。同理链接中的 "htps://" 应为 "https://" |
| `EART29102 - 23-Feb-transcript.md`，克里金命名来源段 | "It's named after a South African mining engineer, **Danny Crigg**"；全文另有 "krigging"、"crigging" 等拼法 | 人名与方法名拼写错误（自动转写） | 方法名为 **Kriging**；命名者为 **Danie G. Krige**（南非采矿工程师） |
| `EART29102 - 23-Feb-transcript.md`，map algebra 加法演示 | "So **two plus two is five**, two plus three is five, zero plus five is five" | 2+2=4，与"和为 5"矛盾；后两式均为 5 | 自动转写听错，原话应为 "**three** plus two is five"。该段的正确理解是：两层对应格相加，示例中各格和均为 5 |
| `Lecture 4 - Spatial Analysis.md`，"Kriging examples – crustal thickness" 页图注 | 该页正文引用 Kebede et al. (2024)，但图注给出的链接是 `https://doi.org/10.1016/j.ocecoaman.2018.12.021` | 该 DOI 是上一页 Coleby and Grist (2019) 香港塑料污染论文的 DOI，被错误复制到本页 | Kebede et al. (2024) 的正确出处**材料未给出** |
| `Lecture 4 - Spatial Analysis.md`，Page 13 OCR 的 map algebra 表 | "Relational **=>,25,5**" | OCR 识别错误 | 应为关系运算符 **`=`, `>`, `<`, `≥`, `≤`**（原表为常见比较运算符） |
| `Lecture 4 - Spatial Analysis.md`，"Vector overlay - 2" | "➢ _union_ Typical overlay operations include , _intersection_ , and _difference_" | 斜体标记位置错乱，词序被打乱 | 原句应为 "Typical overlay operations include **union**, **intersection**, and **difference**" |
| `Lecture 4 - Spatial Analysis.md`，"Geoprocessing operations (merge, reclassify and dissolve)" 页 | 正文只定义了栅格重分类："Assigning new values to **raster dataset cells** based on their pre-existing values is known as reclassification" | 该页配图与老师的口头演示用的是**矢量多边形**（针叶林/阔叶林 → forest），与"栅格单元"的定义对象不符 | 两条路径都存在：栅格用 `Reclassify` 工具，矢量通过改字段值 + `Dissolve`。讲义定义偏窄，未涵盖演示的情形 |
| `(EART29102) Geospatial Techniques.md` 官方大纲 Syllabus 全节 | 大纲列出 Week 1 Geodesy、Week 2 Photogrammetry、Week 3/4 GNSS and satellite remote sensing 等 | **官方大纲与实际授课内容严重不符**：实际 Week 04 讲的是 Spatial Analysis，practical 全部基于 ArcGIS Pro | 大纲仅可作课程总体背景（ILO、评估方式、教材参考），**不可用于推断任何一周的具体内容**。以 Lecture/Practical 文件名与内容为准 |
