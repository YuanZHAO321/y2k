# Week 7 — GeoPandas 与地理空间数据（GIS）：矢量/栅格、坐标参考系、空间连接、裁剪与距离分析

> 材料来源
> - Lecture：`lecture7_25.pdf`（转 md）+ `EART11200 - 11-Mar-transcript.md`（课堂录音转写）
> - Practical：`Practical_7.md`（由 `Practical_7.ipynb` 转出，约 11,100 词，是全课最大的 Notebook 之一）
> - 课程进度：EART11200 Computer Programming 第 7 周（共 9 周）。课程结构为
>   Week 1–2「Vanilla Python」（数据类型 / 循环 / 基本运算 / 条件）→ Week 3–5「NumPy、Conway's Game of Life、微分方程、模块与函数」→ **Week 6 Pandas 与数据发现 → Week 7 地理空间分析 → Week 8 统计分析 → Week 9 聚类分析（机器学习）** → Week 10–12 完成一份 Notebook 形式的作业（**从 Week 4–9 中任选一个主题**）。
>   老师明确说：**本周的 Notebook 就是作业可选题目之一**——你要把本周做的事重做一遍，写成一份「迷你报告」形式的 Jupyter Notebook。

---

## 一、本周主题

本周把 Week 6 学的 **pandas** 扩展到**地理空间（geospatial）**领域，核心工具是 **GeoPandas**。

一句话概括本周做的事：

> 把来自不同来源、不同文件格式、不同坐标系的地理数据，全部读进 **GeoDataFrame**，统一到同一个 **CRS**，然后像叠图层一样把它们**画到同一张地图上**，再用**空间连接（sjoin）、裁剪（clip）、缓冲区（buffer）、距离（distance）**做真正的空间分析。

本周处理的真实科学数据（全部是英国公开数据）：

| 数据集 | 来源 | 文件格式 | 几何类型 | 规模 |
|---|---|---|---|---|
| 英国基岩地质图 Bedrock Geology | British Geological Survey (BGS)，DiGMapGB-625k | Shapefile `.shp` | Polygon（多边形） | 11244 行 × 56 列 |
| 历史煤矿 Collieries | National Library of Scotland，GB1900 gazetteer 项目 | Shapefile `.shp` | Point（点） | 3092 行 × 16 列 |
| 大曼彻斯特行政区边界 | 议会 / ONS | GeoJSON `.geojson` | MultiPolygon | 10 行 × 21 列 |
| 洪水风险区 Flood Zone 2 | Environment Agency（环境署） | Shapefile `.shp` | Polygon | 全英；GM 内 921 个多边形 |
| 电力变电站 Substations | UK National Grid | Shapefile `.shp` | Polygon → 取 `.centroid` 变成 Point | 547 行 × 8 列 |

最终成果：**一张「大曼彻斯特洪水风险 vs 电力变电站风险」地图**——洪泛区用蓝绿色多边形、变电站用点（红=1 km 内有洪水风险，aqua=安全）、每个变电站外围画一个 1 km 半径的红色半透明风险圈、再叠上蓝色的行政区边界线和 OpenStreetMap 底图。

老师强调的三个「为什么值得学」：
1. **GIS 是高度抢手的技能**（ArcGIS / QGIS 是行业标准软件，这里用 Python 实现同样的 workflow）；
2. **跨学科**——GIS 不只是地理学的东西。老师本人的研究是「空气质量如何影响敏感人群的疾病进展」，需要把空气质量数据推进 NHS，与带 GIS 标签的病历（记录人住在哪、在哪工作）结合；曼大目前正与 Esri 合作，做一个面向全英环境数据的新窗口；
3. **Python 生态可以不断叠加**——GeoPandas 能接机器学习模块、统计模块，比单独用 ArcGIS 更能「越搭越强」。

老师也坦承：**这只是 GIS 的皮毛**（"really just scratching the surface"），大学里有整门 GIS 课程、甚至有地理空间分析的硕士方向。

---

## 二、核心概念

### 2.1 GIS 是什么

**Geographic Information Systems（地理信息系统）**，逐词拆开：

- **Geographic**：地球表面上的物理位置；
- **Information**：能用来表征和理解某个特定地点的数据与细节；
- **Systems**：让多个组件协同工作以达成共同目标的工具。

GIS 的三个组成部分：

- **Data（数据）**：核心。包含**空间数据（geographical/spatial）**和**属性数据（attribute/descriptive）**两部分。GeoDataFrame 里，`geometry` 列 = 空间数据，其余所有列 = 属性数据。
- **Tools for Analysis（分析工具）**：揭示模式与关系。
- **Visualization（可视化）**：不止是地图，还有 3D 模型、专题地图（thematic map）。

GIS 与前几周做的事的**本质区别**在两点：

- **Layering Information（信息分层）**：把道路、河流、人口等不同类型的数据一层层叠起来，看它们之间的关系。老师反复用「图层」这个词，就像 Photoshop 把不同图层堆成一张图。
- **Spatial Analysis（空间分析）**：能回答「最短路线是什么？」「哪些区域洪水风险高？」这类**只有空间信息才能回答**的问题。

主流 GIS 软件：

- **ArcGIS**（Esri 公司开发，商业，含 ArcMap / ArcGIS Pro，校园内已安装）；
- **QGIS（Quantum GIS）**（开源替代品）；
- **Google Earth Engine**（云端，海量卫星影像，行星尺度环境数据分析）。

**Esri** 这家公司很关键：它在 1990 年代早期发明了 **Shapefile** 格式，这个格式后来成了全球事实标准。

市场规模（讲义引用 Data Bridge Market Research）：2021 年 GIS 市场 **91.6 亿美元**，预计 2029 年达 **225.18 亿美元**。

### 2.2 栅格数据（Raster）vs 矢量数据（Vector）

这是本周**最重要的概念区分**。

#### Raster 栅格数据

把地球表面表示成一个**单元格矩阵（matrix of cells）**，每个格子里存一个值代表某个属性（温度、高程、土壤湿度……）。

> 老师的比喻：像在地面上铺一张**棋盘**，每一格里写一个数。

- **关键特征**：网格格式（rows and columns）、cell values 存属性、**resolution dependent（分辨率依赖）**。
- **常见格式**：GeoTIFF (`.tif`)、ERDAS IMAGINE (`.img`)、DEM（Digital Elevation Model 数字高程模型）。
- **典型例子**：卫星影像、高程数据、土地覆盖图（land cover maps）。
- **来源**：气候模式 / 空气质量模式的输出天生就是栅格——把行星表示成一个网格，经纬度作为坐标轴。
- **痛点（老师在白板上画的）**：分辨率有限。如果网格是粗的，而你想提取「大曼彻斯特这个复杂形状边界内的数据」，你只能挑「大致落在里面」的格子，**必然丢失信息**。所以新一代气候模式在改写为 **adaptive mesh（自适应网格）**——某个国家上空高分辨率、全球其他地方低分辨率。

#### Vector 矢量数据

用**几何形状**表示空间特征：

- **Point（点）**：井位、气象站、火山、变电站、煤矿；
- **Line / LineString（线）**：河流、道路；
- **Polygon（多边形）**：湖泊、政治边界、地质单元、洪泛区。

> 老师的解释：怎么在**一行数据**里表示「Bollin 河」这样一条河？用 Week 6 的方法，你得把很多组经纬度分散写在很多行里。而 GeoPandas 可以把**整条河的 geometry 存进一个单元格**——它是一串点连起来的集合。

- **关键特征**：shape-based、**precise location（位置精确）**、**attribute richness（属性丰富）**。
- **常见格式**：Shapefile (`.shp`)、GeoJSON (`.geojson`) / TopoJSON、KML/KMZ（Google Earth）。
- **典型例子**：地质采样点位图、河网图、地层边界图。
- **优势**：矢量数据能**在一个网格单元内部捕捉形状**，比栅格精确。老师举例：一个工厂排放有害烟羽，工厂的占地轮廓（footprint）可能是个复杂形状，用矢量才能准确表达。

#### 对照表（Notebook 原表）

| Data Type | Key Characteristics | Common Formats | Examples |
|---|---|---|---|
| **Raster** | 网格格式（行列）<br>单元格值存属性<br>分辨率依赖 | GeoTIFF (.tif)<br>ERDAS IMAGINE (.img)<br>DEM | 卫星影像<br>高程数据 (DEMs)<br>土地覆盖图 |
| **Vector** | 形状为基础（点、线、面）<br>位置精确<br>属性丰富 | Shapefile (.shp)<br>GeoJSON (.geojson) / TopoJSON<br>KML/KMZ | 地质采样点位图<br>河网图<br>地质构造边界图 |

**如何选择？** 取决于：
- **Analysis type**：有些分析偏好栅格的「连续性」，有些需要矢量的「精确性」；
- **Data integration**：往往两者都要整合；
- **Visualization**：两者在制图与可视化上差别很大。

**Week 6 的火山数据属于哪一类？** → **point vector data（点矢量数据）**。因为它不是固定网格，而是每次喷发一组经纬度值。

> 老师课堂上口误又立刻纠正的一句：「So it's a raster data because it's a point on a map. Sorry, it's a **vector** data because it's a point on a map.」——点在地图上 = 矢量。

### 2.3 文件格式：人类可读 vs 不可读

**GeoJSON 是人类可读的**（用文本编辑器就能打开）。Notebook 给的单点样例：

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [-73.9617, 40.6629]
      },
      "properties": {
        "name": "Brooklyn",
        "borough": "Kings",
        "state": "NY"
      }
    }
  ]
}
```

结构解读：
- 最外层是一个 **FeatureCollection**（要素集合）；
- 里面是一个 **Feature 对象数组**；
- 每个 Feature 有 **`geometry`**（这里是一个 Point，`coordinates` 是 `[经度, 纬度]`——注意 GeoJSON 里**经度在前**）和 **`properties`**（该要素的附加属性）。
- GeoJSON 支持的几何类型：`Point`、`LineString`、`Polygon`、`MultiPoint`、`MultiLineString`、`MultiPolygon`、`GeometryCollection`。

**Shapefile 不是人类可读的**：
- 它其实是**一组协同工作的多个文件**（`.shp` / `.shx` / `.dbf` / `.prj` 等），内含**二进制数据**；
- 优点是**存储效率高得多**；
- 老师说：「I can't read a shape file... it's not human readable. But there are pros and cons for how these are stored.」
- 但**我们并不在乎它可不可读**，因为我们是用 GeoPandas 加载它，不是用记事本。

**"interchangeable formats"（可交换格式）**：老师提到的一个重要行业概念——一个社群会**约定**用什么格式存数据，这样它才能和别人的数据组合。GIS 领域过去几十年最大的成就之一就是这些格式的互通。

### 2.4 GeoPandas

> "GeoPandas is an open-source project that makes working with geospatial data in Python easier. It extends the datatypes used by pandas to allow spatial operations on geometric types."

**依赖栈（很重要，报错时要能认出来自哪一层）**：

| 依赖库 | 负责什么 |
|---|---|
| `pandas` | 表格数据结构的基础 |
| `shapely` | **所有几何运算**（面积、距离、buffer、相交判断） |
| `fiona` | **文件读写**（读 .shp / .geojson） |
| `pyproj` / PROJ | **坐标系转换**（`.to_crs`、CRS 查询） |
| `matplotlib` | 绘图 |

安装方式：用 `conda` 包管理器安装 GeoPandas 时会一并装上以上全部。

**GeoPandas 四大特性**：
- Geospatial Data Handling：简化 shapefile / GeoJSON 的处理；
- Integration with pandas：**pandas 的所有功能都还能用**（切片、条件筛选、`.value_counts()`、`.apply()`……）；
- Geometry Operations：直接在 GeoDataFrame 上做面积、距离、缓冲；
- Plotting：`.plot()` 直接出图，与 matplotlib 无缝集成。

**GeoDataFrame** 是核心数据结构。它与普通 DataFrame 的**唯一本质区别**：多了一个 **`geometry` 列**，能存形状。索引概念完全保留。

> 老师原话：「The key difference in GeoPandas is we have a column now that is called **geometry**. And that includes information like this like that or like this.」

### 2.5 Coordinate Reference System（CRS，坐标参考系）

**为什么 `geometry` 列里的数字不像经纬度？**

因为它用的是**投影坐标系**。基岩数据的 geometry 长这样：
```
POLYGON ((274375.248 555042.401, 274315.421 55...))
```
274375 和 555042 显然不是经纬度（经纬度范围是 ±180 / ±90）。

**CRS 定义了 GeoDataFrame 里那张二维投影地图，如何对应到地球上的真实位置。**

- **EPSG codes**：CRS 定义的**短标识符**，由 **EPSG（European Petroleum Survey Group，欧洲石油勘测组织）Geodetic Parameter Dataset** 标准化维护。老师说这是**历史遗留**——名字来自石油勘测行业。
- EPSG codes 涵盖两类：
  - **GCS（Geographic Coordinate System，地理坐标系）**：用**纬度和经度（度）**定位。
  - **PCS（Projected Coordinate System，投影坐标系）**：提供地球的**平面二维表示**，单位通常是**米**。

**常用 EPSG 码（Notebook 表）**：

| EPSG Code | CRS Name | 说明 |
|---|---|---|
| **EPSG:4326** | WGS 84 | 全球地理坐标系标准，**GPS 用它**，全球数据集通用。单位是**度**。 |
| **EPSG:3857** | WGS 84 / Pseudo-Mercator | 又叫 **Web Mercator**。Google Maps、OpenStreetMap 等网页地图服务通用。单位是**米**。**本周全部统一到这个。** |

**支持距离计算（单位为米）的投影 CRS 一览（Notebook 表）**：

| EPSG Code | Reference System Name | Distance Type |
|---|---|---|
| 4326 | WGS 84 | **Geographic**（度，不能直接当距离） |
| 3857 | WGS 84 / Pseudo-Mercator | Projected (Meters) |
| 32633 | WGS 84 / UTM zone 33N | Projected (Meters) |
| **27700** | **OSGB36 / British National Grid** | Projected (Meters) |
| 3395 | WGS 84 / World Mercator | Projected (Meters) |
| 3577 | GDA94 / Australian Albers | Projected (Meters) |
| 25832 | ETRS89 / UTM zone 32N | Projected (Meters) |
| 26713 | NAD27 / UTM zone 13N | Projected (Meters) |
| 54004 | World Sinusoidal | Projected (Meters) |
| 6933 | WGS 84 / NSIDC EASE-Grid 2.0 Global | Projected (Meters) |

**为什么必须统一 CRS？** 老师说得很直白：

> 「如果洪水风险图是一个 CRS，酒馆位置是另一个 CRS，你把它们画在一起，得到的地图就是不真实的。一旦都在同一个 CRS 上，你就知道这是准确的地图，这些就是真实位置。」
>
> 「Typically if you get the CRS system wrong, **it will look ridiculous**. 你会看到房子在海里，或者距离大到毫无意义。」

**为什么不同数据的 CRS 不一样？** 因为它们取决于所服务的系统或技术：GPS 用 EPSG:4326；英国官方测绘（Ordnance Survey / ONS）用 OSGB36；地质数据、大气数据各有自己的社群约定。

### 2.6 底图（basemap）与 contextily

**contextily**（惯例缩写 `cx`）：一个小型 Python 3 包，**从互联网上拉取 tile map（瓦片地图）**，把它们作为底图加到 matplotlib 图上。

- 默认使用 **OpenStreetMap** 瓦片（外观类似 Google Maps）；
- 可以换成其他样式（ONS street maps、Google Maps 风格等）；
- **这是一个网络服务**——没联网就用不了；
- 老师警告：**这一步会很慢**（几十秒到几分钟），尤其在 Colab 上，因为它在从服务器拉取瓦片、拼成画布；
- 也可以**本地存高分辨率地图**（Notebook 里有一行注释掉的 `cx.add_basemap(ax3, source="basemap_GM.tif")` 就是这个用法）。街道级 / 米级的超高分辨率地图通常**要付费**，但可以从 Google Earth 下载数据自己转成底图。

对比 Week 6 用的 **Cartopy**：老师说 Cartopy 是个好起点，但**只要做地理空间数据，通常都会跳到 GeoPandas**——它对地图类型的控制力和可做的计算都强得多。

### 2.7 三大空间操作的直觉理解

| 操作 | 直觉比喻 | 干什么 |
|---|---|---|
| **`sjoin`（spatial join，空间连接）** | 「pandas 的 join，但按位置关系而不是按 key」 | 把两个 GeoDataFrame 按**几何相交关系**合并 |
| **`clip`（裁剪）** | **饼干模具（cookie cutter）** | 用一组多边形把另一个 GeoDataFrame「切」出来，只保留落在里面的部分 |
| **`buffer`（缓冲区）** | 「围着点画一个圈」 | 在几何体外围生成指定距离的新几何体 |

老师对 clip 的关键洞察：

> 「Do you remember last week we did a subset according to conditional statements in the dataframe? 如果我们想要的子集是一个**地理边界内**的子集，我们**不需要那样做**——我们可以直接用那个地理边界 clip 掉数据框。**否则我们就得把这个边界的所有形状特征都手写出来，那是我们绝对不想做的事。**」

这就是本周最核心的「为什么用 GIS」的论证。

---

## 三、语法速查与函数表

### 3.1 模块导入与惯例缩写

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `geopandas` | 地理空间 DataFrame | `import geopandas as gpd` | 惯例缩写 **`gpd`** |
| `contextily` | 拉取网络底图瓦片 | `import contextily as cx` | 惯例缩写 **`cx`**；**需要联网** |
| `matplotlib.pyplot` | 绘图 | `import matplotlib.pyplot as plt` | 老朋友 |
| `%matplotlib inline` | Jupyter magic，图内嵌显示 | `%matplotlib inline` | 是 IPython magic，不是 Python 语句 |
| `os` / `os.getcwd()` | 取当前工作目录 | `path = os.getcwd()` | 用它拼相对路径，避免写死绝对路径 |

### 3.2 GeoPandas 读取与 CRS

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `gpd.read_file(path)` | **读任意地理空间文件**（.shp / .geojson / .gpkg…） | `gdf = gpd.read_file(file)` | 与 `pd.read_csv` 对应，但它靠后缀/内容**自动识别格式**，一个函数吃所有格式；返回 **GeoDataFrame** |
| `.crs` | **属性**（不是函数），查询当前 CRS | `gdf.crs` | 注意：**不加括号**。返回一个 `CRS` 对象，print 出来包含名称、轴信息、单位、基准面、椭球体 |
| `.to_crs(epsg=N)` | **转换**到目标 CRS | `gdf_wm = gdf.to_crs(epsg=3857)` | **返回新 GeoDataFrame，不原地修改**！必须赋值给新变量。也可写 `.to_crs("EPSG:3857")` |
| `geometry` 列 | 存几何体的特殊列 | `gdf['geometry']` | 值是 shapely 对象：`POINT`/`LINESTRING`/`POLYGON`/`MULTIPOLYGON` |
| `.geom_type` | 返回每行几何体的类型字符串 | `df[df.geom_type == 'Polygon']` | 空间连接后可能混有多种几何类型，用它过滤 |

### 3.3 绘图

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `.plot(...)` | GeoDataFrame 绘图，**返回一个 matplotlib Axes** | `ax1 = gdf_wm.plot(...)` | 默认画 `geometry` 列的形状；**返回值 ax 是叠图的关键** |
| `figsize=(16,16)` | 图幅尺寸（英寸） | | 地图要大才看得清 |
| `alpha=0.3` | 透明度 0–1 | | 设透明才能看到底图 |
| `column="RCS_D"` | **按哪一列的取值给多边形分类上色** | | 这是「专题地图」的核心参数 |
| `edgecolor="k"` | 多边形之间的边界线颜色（`"k"`=黑） | | |
| `cmap="gist_ncar"` | colormap（配色方案） | `cmap="winter"` | 完整列表见 matplotlib colormaps 文档 |
| `legend=True` | 是否画图例 | | 分类多时图例会很长 |
| `legend_kwds={...}` | 图例的样式与位置 | `{"loc":"center left","bbox_to_anchor":(1,0.5),"fontsize":7}` | **不用背**（Notebook 明说 "which you do not need to remember!"）。`bbox_to_anchor=(1,0.5)` = 把图例放到图**右侧外面**的垂直中点 |
| `ax=ax1` | **把这一层画到已有的坐标轴上** | `cdf_wm.plot(ax=ax1_new, ...)` | **叠图层的关键**。第一次 plot 创建 ax，之后每层都传 `ax=` |
| `marker='o'` | 点的形状 | | 只对点数据有意义 |
| `color='red'` | 单一颜色，或**一列颜色** | `color=ssdf_wm_GM['color']` | 传 Series 时逐点着色 |
| `markersize=5` | 点的大小 | 本周用过 5 / 8 / 12 / 18 | 放大到区域尺度时要调大 |
| `.boundary.plot(...)` | 只画多边形的**边界线**（不填充） | `GMdf_wm.boundary.plot(edgecolor='blue')` | `.boundary` 把 Polygon 转成 LineString |
| `cx.add_basemap(ax, crs=..., zoom=..., alpha=...)` | 在 ax 下面铺底图 | `cx.add_basemap(ax1, crs='EPSG:3857')` | **`crs=` 必须与数据一致**，否则底图对不上；`zoom=` 控制瓦片细节层级（本周用 10 / 12）；`source=` 可指定本地 .tif |
| `plt.show()` | 显示图 | | |

### 3.4 空间分析函数（本周新语法的核心）

| 名称 | 作用 | 用法示例 | 返回值 | 注意事项 |
|---|---|---|---|---|
| `gpd.sjoin(left, right)` | **空间连接**：按几何相交关系合并两个 GeoDataFrame | `joined_df = gpd.sjoin(gdf_wm, cdf_wm)` | GeoDataFrame | **只保留 left 的 geometry**！right 的几何列被丢弃，只有它的**属性列**被接到 left 的几何上。列数 = 56 + (16−1) + 1(`index_right`) = 72 |
| `.clip(mask)` | **裁剪**：只保留落在 mask 几何范围内的部分 | `cdf_wm.clip(joined_df)` / `gdf_wm.clip(GMdf_wm)` | 新 GeoDataFrame | mask 可以是 GeoDataFrame、GeoSeries，或它的一个子集（如 `GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)']`） |
| `.buffer(dist)` | **缓冲区**：围绕几何体生成指定距离的新几何体 | `risk_zone = ssdf_wm_GM.buffer(1000)` | **GeoSeries**（不是 GeoDataFrame） | **`dist` 的单位 = 当前 CRS 的单位**！3857 是米，所以 1000 = 1 km。**若 CRS 是 4326（度），1000 就是 1000 度——完全无意义** |
| `.distance(other)` | 计算每个几何体到 `other` 的**最短距离** | `frdf_wm_GM.geometry.distance(row.geometry)` | pandas Series（float64） | 单位同样是 CRS 单位（米）。**点落在多边形内部时距离 = 0** |
| `.centroid` | 取几何体的**质心** | `df['geometry'] = df['geometry'].centroid` | GeoSeries（Point） | 用来把复杂多边形简化成单点。**在投影 CRS 下才有意义**（地理 CRS 下会警告） |
| `.geometry` | 访问 GeoDataFrame 的活动几何列 | `df.geometry.distance(...)` | GeoSeries | 等价于 `df['geometry']`，但更通用（几何列可以改名） |

### 3.5 继承自 pandas 的用法（Week 6 复习）

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| 布尔索引 | 条件筛选行 | `data[data['Start Year'] == 2019]` | Week 6 学过 |
| `.str.contains('X')` | **字符串列中是否包含子串** | `gdf_wm[gdf_wm["RCS_D"].str.contains('SANDSTONE')]` | 本周新用法。返回布尔 Series。区分大小写；列里有 `NaN` 会报错（需 `na=False`） |
| `.value_counts()` | 统计某列各取值出现次数，**按降序排列** | `joined_df['RCS_D'].value_counts()` | 返回 Series，索引=取值，值=计数 |
| `.iterrows()` | 逐行迭代，返回 `(index, row)` 元组 | `for index, row in df.iterrows():` | `row` 是一个 Series，用 `row['列名']` 或 `row.geometry` 取值。**慢**，但对小表和教学很直观 |
| `.apply(func)` | 对列的每个元素施加函数 | `.apply(lambda x: 'aqua' if x > 1 else 'red')` | 见下 |
| `lambda` | 匿名函数 | `lambda x: 'aqua' if x > 1 else 'red'` | Notebook 说「Do not worry about the lambda function. 这是一种**非常高效但可读性不好**的按条件计算的写法」。等价于 `def f(x): return 'aqua' if x>1 else 'red'` |
| `.copy()` | 复制 DataFrame（**深拷贝**） | `ssdf_wm_copy = ssdf_wm.copy()` | **避免 `SettingWithCopyWarning` 的正确做法**（见第六节） |
| `.min()` | Series 最小值 | `distances.min()` | 本周用来找「最近的洪泛区有多远」 |
| `df['新列'] = list` | 新增一列 | `ssdf_wm_GM['min distance to flood'] = min_distances` | list 长度必须与行数一致 |

### 3.6 图表生成方式与判读要点

本周所有图都是「**图层堆叠**」模式，生成套路固定为四步：

```python
ax = 底层数据.plot(figsize=..., alpha=..., column=..., cmap=..., legend=True)  # 1. 建 ax
上层数据.plot(ax=ax, marker='o', color='red', markersize=5)                    # 2. 叠层（可重复）
边界数据.boundary.plot(ax=ax, edgecolor='blue')                               # 3. 叠边界线
cx.add_basemap(ax, crs='EPSG:3857', zoom=12)                                  # 4. 铺底图
plt.show()
```

**判读要点（怎么知道图是对的）**：

1. **底图和数据必须重合**——如果地质多边形飘在海里、或者点全挤在一个角落，几乎一定是 **CRS 没统一**。
2. **英国的轮廓要认得出来**——Web Mercator 下的英国是熟悉的形状。
3. **图例的类别数**要和 `column` 那一列的 unique 值个数对得上。
4. **煤矿点应当落在合适的基岩上**——老师说：「where those red points are represent the appropriate bedrock that people would have mined through to extract the coal」。这是一个**科学合理性检验**：红点应当密集出现在「泥岩、粉砂岩、砂岩、煤、铁石和铁质结壳」（即石炭纪煤系地层）之上。
5. **buffer 圈的大小要合理**——1 km 半径的圆在城市尺度地图上应该是个小圈；如果占满整张图，说明 CRS 单位不是米。

另外还有一张**非地图图表**——柱状图（Distribution of Bedrock Types），用纯 matplotlib 画：

```python
plt.figure(figsize=(10, 6))     # 新建一张 10×6 英寸的图
distribution.plot(kind='bar')   # 直接在 value_counts() 的结果 Series 上调用 .plot(kind='bar')
plt.title('Distribution of Bedrock Types')
plt.xlabel('Bedrock Type')
plt.ylabel('Frequency')
plt.xticks(rotation=90)         # 把 x 轴标签旋转 90° —— 岩性名称很长，不转会重叠成一团
plt.show()
```

判读要点：柱子按频次降序（因为 `value_counts()` 本身就降序），第一根柱子应该压倒性地高（2478 vs 第二名 200）。

---

## 四、课堂补充（transcript 独有）

以下内容**只在录音转写里有**，讲义 PDF 上没有。

### 4.1 老师开场：GIS 是抢手技能

- 「Has anyone heard of GIS before? Has anyone used ArcGIS?」——先问全场，说明这对大一学生是全新概念。
- 「If you go over to geography, they do lots of their work around ArcGIS.」ArcGIS 全校园都装了。
- 「It's actually a **pretty highly sought-after skill** in a whole range of companies.」
- 但学 ArcGIS 只是学「另一个软件平台」；**在 Python 里做，能接机器学习模块、统计模块，把生态一层层搭起来（"build and build and build our ecosystem"），比刚开课时强大得多。**

### 4.2 为什么值得花两周

「I think it's worthwhile spending **two weeks** on geospatial analysis... this is definitely one of those areas that's of relevance to pretty much **any pathway you pick in your degree**. 就算你做太阳系研究，你也可以把**其他行星的数据**包成 GIS 格式。」

### 4.3 老师自己的研究（GIS 的跨学科例子）

这是一个非常具体的、值得记住的应用故事：

> 「我关心的是**空气质量如何决定敏感人群的疾病进展**。我得把我的数据推送进 NHS，NHS 会把它和敏感数据结合起来。但一切都有地理空间要素。
>
> 我要载入 Python 的不只是空气质量数据——我还需要**土地利用（land use）**、**交通与出行（transport and mobility）**、**社会经济数据（socio-economic）**，这样才能看出污染在哪里影响最强。
>
> **通常你会发现，受污染影响最严重的是低收入社区**，而这一点你只要画出地图就能感觉到。但画那张图，需要把所有这些数据以**图层**的形式汇集在一起——而这些数据分散在不同的仓库、不同的地方。」

还提到：曼大目前有一个项目，与 Esri 合作，做一个通向全英环境数据的新窗口，然后推进 NHS。**病历会带 GIS 标签，记录人住在哪、在哪工作**，这样就能研究疾病进展的潜在决定因素。

> 「So GIS isn't just about geography. **It straddles the whole range of scientific disciplines that have a particular impact angle to them.**」

### 4.4 白板演示：栅格 vs 矢量的三张草图

老师在白板上画了三个东西来说明（转写里能还原）：

1. **点（火山）**——Week 6 的数据，一个坐标两个数（lat/lon），画成地图上的点。
2. **网格（气候模式）**——「跑空气质量模式或气候模式时，你把行星表示成一个网格，你想让这个网格分辨率尽可能高。经纬度是不同的轴，但信息存在这个格子里。」
3. **河流**——「现实世界里，某些自然系统并不容易符合这两者。想象我们有一条河，它有特定的形状。所以我们需要**另一种方式**来表示这类信息。」

然后他画了一个「粗糙的英国」和一个粗网格：

> 「如果这是在预测温度或降水，那这个格子并没有给我们多少关于**政治边界**的信息。我们想把它做得越来越小。」

再画了一个复杂形状的政治边界叠在网格上：

> 「Which grid cell do I pick? Well, I'll probably pick these ones. **But I'm going to miss some information.**」

**扩展知识点**：矢量可以在网格单元内部捕捉形状。新一代气候模式正在被改写为 **adaptive mesh（自适应网格）**——某个国家上空可以做到极高分辨率、全球其他地方保持粗分辨率。

老师还举了工厂的例子：「Imagine this is a factory chucking out lots of really harmful plumes, and this represents a neighborhood, and there's a certain wind direction. **The footprint of that factory might be much more complicated**, might be represented by a given shape.」

（然后自嘲：「Okay, I won't go near the whiteboard anymore.」）

### 4.5 老师对最终那张地图的完整讲解

老师提前展示了 Notebook 最后那张 GM 地图，并逐层拆解：

- **外边界内的不同 authorities** → 从**议会网站**下来的 GeoJSON 文件；
- **蓝色阴影区** → **Environment Agency 每年发布的洪水风险图**；老师说「如果你知道去年南曼彻斯特特别受洪水困扰，你在这里就能看到风险图，看到特定风险的空间范围」；
- **红点** → 变电站 / 发电站，从另一个网站拿的；
- **点周围的阴影区** → 「I've actually told GeoPandas **give me a radius of a kilometre** from around the substation」；
- **数据来源全部免费**：「The Environment Agency have their own data repositories that you can access **for free**. They're held in GIS formats.」

老师坦承这是个**假设情景（hypothetical scenario）**：洪水影响大曼彻斯特电力中断。

> 「Whether or not that will happen **doesn't matter**. The point being I've gone from loading data in with **not that much code** to produce that map.」

### 4.6 buffer 的另一种用法（老师口头扩展，Notebook 没做）

> 「你可以在洪水风险图外面做一个边界，**不一定非得是点数据**。我可以做一个离洪泛区 1 公里的边界。为什么你会关心这个？因为**洪水会在住房中造成很多问题——它产生霉菌（mould）、细菌滋生，影响人类健康，已知会在事件之后造成医疗问题**。
>
> 所以如果我想看离洪泛区一定距离的范围，我可以用 buffer 函数把这个距离建出来并可视化在地图上。**那个距离范围内是不是恰好包含了社会保障房（social housing）之类的东西？**」

这是一个很好的「GIS 如何转化为科学问题」的示范，值得在写作业时借鉴。

### 4.7 `.str.contains()` 是老师课上临时补充的

> 「**One thing I didn't say in the lecture actually** — look here, I've only plotted data on sandstone. 有几种在 GeoPandas 数据框里选子集的方法。记得上一个 notebook 里我们用条件语句调用数据框吗？我们也可以用**字符串包含某个词**这样的函数。」

也就是说 `.str.contains()` 是本周**唯一一个不在 PPT 上的新语法**，但它在练习里反复用到。

### 4.8 关于运行速度的警告

> 「You'll find that **some of the commands that you run will seem to take a while — maybe a couple of minutes or so**, because what's happening there is it's **pulling that basemap from servers** and creating that canvas for you. Particularly if you're running on Colab, it seems to take a bit of a while to run.」

**所以：跑 `cx.add_basemap()` 卡住不是死机，是在下载瓦片。**

### 4.9 关于 Notebook 篇幅

> 「You'll notice it's a **particularly large notebook** today... There is a lot there. **Don't worry if you don't go through it in the entire time that you've got in the practical tomorrow.** But do give us a shout.」

### 4.10 数据来源的指引

老师提到搜数据的技巧：

> 「如果你要找 shapefile 这类东西，你可以搜 **vector data**；如果你要网格化数据，就搜 **raster data / gridded data**。」

以及：Ordnance Survey / ONS（Office for National Statistics）的数据遵循英国标准（OSGB36），从美国系统拉数据就需要格式互换——「but we can check at every step: are we doing the right thing」。

### 4.11 老师顺带提到的软性内容

- 曼大有人文学院，很多人研究「**human interaction with data**」——「It's amazing the power a map can have in telling that story.」老师建议后续阶段可以探索地理空间分析 + 人文社科的硕士方向。
- 关于本地高分辨率地图：「如果你想画一个真正高分辨率的系统，比如**河湾几米的尺度**——有那么高分辨率的地图，但它们非常大。……一旦到街道/米级尺度，通常**你得付费**，因为有公司专门生产城市的高分辨率地图。你也可以从 **Google Earth** 下载数据转成底图。」

---

## 五、Practical 要点

### 5.0 环境设置代码块（第一个 cell）

Notebook 开头有一个「红色警告框」提示的环境准备块，**必须先跑**：

```python
# 判断当前是否运行在 Google Colab 上。get_ipython() 返回当前 IPython 内核对象，
# 在 Colab 上它的字符串表示里会包含 'google.colab'。
if 'google.colab' in str(get_ipython()):
    !pip install contextily     # Colab 默认没装 contextily，用 ! 前缀执行 shell 命令安装
else:
     print('Not running on CoLab')

if 'google.colab' in str(get_ipython()):
    from google.colab import drive
    mount='/content/gdrive'
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)          # 挂载 Google Drive，才能读到数据文件
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root             # %cd 是 IPython magic，切换工作目录
else:
    print('Not running on CoLab')

# 2025 年新增：曼大的 JupyterHub 实例固定在 Python 3.12。
# 如果 notebook 跑在这个特定的 JupyterHub 上，需要显式设置 PROJ 路径，
# 否则 CRS 查询（.crs / .to_crs）会失败。
import os

# 检查环境变量里有没有以 "JUPYTERHUB_" 开头的键 —— 这是判断是否在 JupyterHub 上的技巧
IN_JUPYTERHUB = any(k.startswith("JUPYTERHUB_") for k in os.environ)

if IN_JUPYTERHUB:
    print("Running on JupyterHub — PROJ paths set")
    os.environ["PROJ_DATA"] = "/opt/conda/envs/gis-practical/share/proj"
    os.environ["PROJ_LIB"]  = "/opt/conda/envs/gis-practical/share/proj"
```

**输出**：
```
Not running on CoLab
```
（老师在本地 anaconda 环境跑的，所以两次都打印 "Not running on CoLab"，且未进入 JupyterHub 分支。）

**这段代码值得学的地方**：
- `any(k.startswith("JUPYTERHUB_") for k in os.environ)`：一个**生成器表达式 + `any()`** 的组合，检查「是否存在任何一个满足条件的元素」。
- `os.environ` 是一个类字典对象，存放**环境变量**。改它就能影响底层 C 库（这里是 PROJ）的行为。
- **PROJ_DATA / PROJ_LIB 是 PROJ 库找坐标转换参数文件的路径**。这是本周最典型的「环境坑」：如果这两个变量指错，`.crs` 或 `.to_crs()` 会报 CRS 查找错误（常见形态是 `pyproj` 抛出 `CRSError` 或 `PROJ: proj_create_from_database: Cannot find proj.db`）。

---

### 5.1 Part 1：读取基岩数据、检查 CRS、画第一张图

#### 步骤 1 — 导入与读取

```python
# import the modules, using standard naming convention.
import geopandas as gpd            # GeoPandas，惯例缩写 gpd
import contextily as cx            # contextily，惯例缩写 cx，用来加底图
import matplotlib.pyplot as plt    # 绘图
%matplotlib inline                 # Jupyter magic：把图直接嵌在 notebook 里
import os
from os import path

path=os.getcwd()                   # 取当前工作目录，作为所有数据路径的前缀
# Our file has the following path and name - notice the extension .shp
file = path+"/data/digmap625_bedrock_arc/625k_V5_BEDROCK_Geology_Polygons.shp"
# Like Pandas, GeoPandas has a read_file function. Im creating a GeoDataframe called 'gdf'
gdf = gpd.read_file(file)          # 一行读完整个 shapefile

# Preview the GeoDataframe to the screen
gdf                                # 在 notebook 里裸写变量名 = 显示它
```

**输出（表格形式，关键信息）**：`11244 rows × 56 columns`

列名（部分）：`LEX, LEX_D, LEX_RCS, RCS, RCS_X, RCS_D, RANK, BED_EQ, BED_EQ_D, MB_EQ, ..., BGSREF_GP, BGSREF_RK, SHEET, VERSION, RELEASED, NOM_SCALE, NOM_OS_YR, NOM_BGS_YR, MSLINK, geometry`

第 0 行示例：
```
LEX = UISD
LEX_D = UNNAMED IGNEOUS INTRUSION, LATE SILURIAN TO EA...
RCS_D = MAFIC IGNEOUS-ROCK
RANK = INTRUSION
SHEET = 625k_V5_Bedrock,  VERSION = 5.17,  RELEASED = 11- 2-2008
NOM_SCALE = 625000          ← 名义比例尺 1:625,000
geometry = POLYGON ((274375.248 555042.401, 274315.421 55...))
```

第 11243 行（最后一行）示例：
```
LEX_D = WHITE CHALK SUBGROUP,  RCS_D = CHALK,  RANK = SUBGROUP
geometry = POLYGON ((600000.000 347101.531, 601624.750 34...))
```

**输出解读**：
- **11244 行 = 11244 个独立的地质多边形**。老师在讲义里指着一块黄色区域说：「that's a **single entry** of a shape, so it represents a geospatial extent of a certain bedrock type」——**一行 = 一片特定基岩类型的空间范围**。
- **56 列都是属性数据**，只有最后一列 `geometry` 是空间数据。
- 我们要用的关键列是 **`RCS_D`**——「describes the **dominant type of rock**（主导岩石类型）」。老师特意说明：「That's **not a column name that I've come up with**. It's just a column that's in the data frame.」（列名是数据自带的，不是他起的。）
- **地球科学背景**：BGS DiGMapGB-625k 是英国地质调查局的 1:625,000 比例尺数字地质图。`LEX` = Lexicon code（地层词典代码），`RCS` = Rock Classification Scheme（岩石分类方案）代码，`RCS_D` = 该代码的文字描述。`RANK` 表示地层等级（INTRUSION 侵入体 / SUBGROUP 亚群 / FORMATION 组 等）。
- **元数据的痛点**：Notebook 特别指出「you will often find it is difficult to obtain 'meta data' associated with records」——很多列名（BGSREF_GP、MSLINK）没有说明文档，这是真实数据工作的常态。

#### 步骤 2 — 检查 CRS

```python
gdf.crs
```

**输出**：
```
<Projected CRS: PROJCS["OSGB36 / British National Grid",GEOGCS["OS ...>
Name: OSGB36 / British National Grid
Axis Info [cartesian]:
- [east]: Easting (metre)
- [north]: Northing (metre)
Area of Use:
- undefined
Coordinate Operation:
- name: unnamed
- method: Transverse Mercator
Datum: Ordnance Survey of Great Britain 1936
- Ellipsoid: Airy 1830
- Prime Meridian: Greenwich
```

**逐行解读（这个输出要会读）**：

| 行 | 含义 |
|---|---|
| `<Projected CRS: ...>` | 这是一个**投影**坐标系（不是地理坐标系）——所以数字不是经纬度 |
| `Name: OSGB36 / British National Grid` | **英国国家格网**。EPSG:27700 |
| `Axis Info [cartesian]` | 笛卡尔坐标（平面直角），不是球面 |
| `- [east]: Easting (metre)` | X 轴叫 Easting，**单位是米** |
| `- [north]: Northing (metre)` | Y 轴叫 Northing，**单位是米** |
| `method: Transverse Mercator` | 投影方法：横轴墨卡托 |
| `Datum: Ordnance Survey of Great Britain 1936` | **基准面**：英国测绘局 1936 基准 |
| `Ellipsoid: Airy 1830` | 参考椭球：Airy 1830（专为英国拟合的椭球） |
| `Prime Meridian: Greenwich` | 本初子午线：格林尼治 |

所以 `274375.248, 555042.401` 的意思是：**距离 BNG 原点向东 274.4 km、向北 555.0 km**。

**为什么英国用 OSGB36？** Notebook：「OSGB36 was historically developed to provide a consistent and accurate mapping framework for the UK.」但要做全球定位（如 GPS），常需转换成 EPSG:4326 这类更通用的基准。

#### 步骤 3 — 转换 CRS

```python
gdf_wm = gdf.to_crs(epsg=3857)     # wm = Web Mercator。返回新的 GeoDataFrame
gdf_wm
```

**输出**：仍是 `11244 rows × 56 columns`，但 **geometry 列的数字全变了**：

| 行 | 转换前（OSGB36） | 转换后（Web Mercator 3857） |
|---|---|---|
| 0 | `POLYGON ((274375.248 555042.401, ...))` | `POLYGON ((-440750.842 7337513.465, ...))` |
| 1 | `POLYGON ((273618.809 553462.498, ...))` | `POLYGON ((-441985.281 7334731.896, ...))` |
| 11243 | `POLYGON ((600000.000 347101.531, ...))` | `POLYGON ((108859.856 6980028.266, ...))` |

**输出解读（怎么判断转对了）**：
- X 变成**负数**（-440750）→ 合理，因为 Web Mercator 的原点在**格林尼治本初子午线**上，苏格兰/威尔士在格林尼治**以西**，所以 X 为负；而伦敦东部（第 11243 行，Kent 的白垩）X 是正的（+108859）。
- Y 变成 **7,000,000 左右**的大数 → 合理，Web Mercator 的 Y 从赤道起算，英国在北纬 50–58°，对应 Web Mercator Y 约 6.5–8.0×10⁶ 米。
- 行数列数**完全不变** → 转换只改几何，不改属性。

**⚠️ 关键陷阱**：`.to_crs()` **不是原地修改**。必须 `gdf_wm = gdf.to_crs(...)`；写成 `gdf.to_crs(epsg=3857)` 而不赋值，`gdf` 一点没变。

**为什么统一到 3857 而不是 4326？** 因为：
1. contextily 的默认瓦片（OpenStreetMap）就是 Web Mercator；
2. **3857 单位是米**，`buffer(1000)` 和 `distance()` 才有直接意义。Notebook 后面自己点破了：「As if by magic, we have been using a CRS (EPSG:3857) that is based on metres.」

#### 步骤 4 — 第一张地图

```python
# Create an axis [ax1] that has the information held within the gdf_wm dataframe. Provide styling and colouring option
ax1 = gdf_wm.plot(
    figsize=(16, 16),       # 图幅 16×16 英寸，地图要够大
    alpha=0.3,              # 30% 不透明度 —— 老师说 "I would like to see some of the underlying map"
    column="RCS_D",         # 按主导岩性列给多边形分类着色
    edgecolor="k",          # 多边形之间用黑线分隔
    cmap="gist_ncar",       # 配色方案：gist_ncar 色彩跨度大，适合很多类别
    legend=True,            # 要图例
    legend_kwds={"loc": "center left",      # 图例锚点在其自身的「左中」
                 "bbox_to_anchor": (1, 0.5), # 把这个锚点放到图的右边界外、垂直中点
                 "fontsize": 7}              # 字号 7 —— 类别太多，字要小
)
# Use the Contextily module to add a basemap underneath axes (ax1), which will look like OpenStreetMap.
# We make sure Contextily uses the same 'CRS' system by supplying this as an argument
cx.add_basemap(ax1, crs='EPSG:3857')
plt.show()
```

**输出**：`output_11_0.png` —— 整个英国的基岩地质图，彩色多边形铺满不列颠岛，右侧一长条图例列出所有岩性类别，底下透出 OpenStreetMap 街道地图。

**逐参数说明（Notebook 蓝色信息框原文的翻译）**：
> - 创建一个新坐标轴 `ax1`，它是调用 `.plot` 时返回的。提供了多个绘图选项：
>   - `alpha` — 基岩图层的透明度。我想看到一些底下的地图。
>   - `column` — 指定我想用哪一列来给不同多边形**分类并加标签**。
>   - `edgecolor` — 分隔多边形的颜色。
>   - `cmap` — 不同类别使用的配色方案。matplotlib 里有很多种。
>   - `legend` — 要不要图例？要。
>   - `legend_kwds` — 定义图例样式和位置的特定关键字，**你不需要记住**！
> - 用 contextily 给上面的坐标轴加底图。contextily 通过给图形提供不同样式的瓦片来工作。默认用 OpenStreetMap，看起来像 Google Maps。调用 `.add_basemap` 时必须告诉 contextily **用哪个坐标轴**以及**映射到哪个 CRS**。**它替我们完成了所有对齐工作！** 注意这是网络服务，没联网可能不工作。

**最容易忽略的一点**：`ax1 = gdf_wm.plot(...)` 中的 **`ax1` 是这整套叠图流程的枢纽**。`.plot()` 返回的是一个 matplotlib `Axes` 对象，之后所有图层都通过 `ax=ax1` 画到它上面。

#### 步骤 5 — 选子集：`.str.contains()`

Week 6 的做法（数值条件）：
```python
data[data['Start Year'] == 2019]   # 上周：按数值筛选
```

本周的问题：**`RCS_D` 里没有数值条件可用**，只有一堆长长的岩性描述字符串，比如
`"MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTONE AND FERRICRETE"`。

解法：`.str.contains()`——检查 Series 里的每个字符串**是否包含**指定模式/子串。

```python
# 建一个新的 GeoDataFrame，只保留 RCS_D 中包含 'SANDSTONE' 的行
gdf_wm_new = gdf_wm[gdf_wm["RCS_D"].str.contains('SANDSTONE')]
ax2 = gdf_wm_new.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k",
                      cmap="gist_ncar", legend=True,
                      legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5), "fontsize": 7})
cx.add_basemap(ax2, crs='EPSG:3857')
plt.show()
```

**拆解 `gdf_wm[gdf_wm["RCS_D"].str.contains('SANDSTONE')]`（从内到外）**：
1. `gdf_wm["RCS_D"]` → 取出这一列，得到一个字符串 Series；
2. `.str` → **字符串访问器**，让你对 Series 的每个元素用字符串方法；
3. `.contains('SANDSTONE')` → 返回一个**布尔 Series**（True/False，长度 11244）；
4. `gdf_wm[布尔Series]` → **布尔索引**，只保留 True 的行。

**输出**：`output_13_0.png` —— 地图上只剩含砂岩的地质单元，覆盖范围明显减少，图例也短了很多。

**注意**：`'SANDSTONE'` 会匹配任何**包含**这个词的类别，包括 `"SILTSTONE AND SANDSTONE WITH SUBORDINATE MUDSTONE"`、`"SANDSTONE AND CONGLOMERATE, INTERBEDDED"` 等。这是**子串匹配，不是精确匹配**——既是优点（一次抓住所有含砂岩的组合岩性），也是要留心的地方。

---

### 5.2 Exercise 1：只画石灰岩基岩的位置

**题目要求**：重复上面的演示，但只选取有石灰岩（limestone）沉积的位置。已经给好了新数据框的名字 `gdf_wm_ex1`。

**解题思路**：把 `.str.contains('SANDSTONE')` 里的关键词换成 `'LIMESTONE'`，其余代码完全照抄。注意 `RCS_D` 里的值全是**大写**，所以必须写 `'LIMESTONE'` 而不是 `'limestone'`。

**完整代码**：
```python
# -------'INSERT CODE HERE'-------
# 1. 用 .str.contains 筛出 RCS_D 中含 'LIMESTONE' 的所有行
gdf_wm_ex1 = gdf_wm[gdf_wm["RCS_D"].str.contains('LIMESTONE')]
# 2. 画图 —— 参数与前面完全一致，只是数据框换成 gdf_wm_ex1，坐标轴变量换成 ax3
ax3 = gdf_wm_ex1.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k",
                      cmap="gist_ncar", legend=True,
                      legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5), "fontsize": 7})
# 3. 加底图，CRS 必须仍然是 3857
cx.add_basemap(ax3, crs='EPSG:3857')
plt.show()
# --------------------------------
```

**输出**：`output_15_0.png` —— 只显示石灰岩相关地质单元的英国地图。

**输出解读 / 科学背景**：英国的石灰岩主要出现在几个可预期的地带——奔宁山脉（Carboniferous Limestone，石炭纪石灰岩）、科茨沃尔德到约克郡的侏罗纪石灰岩带、以及南部/东部的白垩（Chalk，虽然 `CHALK` 本身不含 "LIMESTONE" 字样，所以**不会**被这个筛选抓到）。**这是一个值得注意的细节：`.str.contains('LIMESTONE')` 抓不到 `RCS_D == 'CHALK'` 的行，尽管白垩在化学上就是石灰岩。**（说明字符串匹配的局限：它匹配的是**词**，不是**概念**。）

---

### 5.3 Part 2：加入点矢量数据（煤矿）

#### 步骤 1 — 读取煤矿 shapefile

**数据背景**：来自 **National Library of Scotland** 的 [Mapping Quarries and Collieries] 项目，属于 **GB1900 gazetteer**（一个把 1900 年前后英国全境地形图上的**所有文字标注**数字化的众包项目）。

**Colliery 是什么？** Notebook 解释：「a colliery refers to a **coal mine and its associated buildings**（煤矿及其附属建筑），where coal is extracted from underground. 这个词不仅包括竖井本身，也包括煤炭开采和加工所用的基础设施与设施。」

**煤是怎么形成的？** Notebook 给的地球科学背景：「Coal is formed from the remains of ancient plants and animals that **accumulated in swampy environments millions of years ago**（数百万年前在沼泽环境中堆积的古代动植物遗骸）, eventually becoming **buried under layers of sediment**（最终被沉积层掩埋）. Over time, these organic deposits were subjected to **high pressure and heat**（高压高温）, transforming into coal.」所以**煤矿下面的基岩类型会因区域地质特征而显著不同**——这正是本节要探究的问题。

```python
# make referene to the location of the .shp file and then use GeoPandas to load in and then preview.
file_colliery = path+"/data/collieries/collieries.shp"
cdf = gpd.read_file(file_colliery)     # cdf = colliery dataframe
cdf
```

**输出**：`3092 rows × 16 columns`

列名：`pin_id, final_text, nation, local_auth, parish, osgb_east, osgb_north, latitude, longitude, notes, field_11, field_12, field_13, field_14, field_15, geometry`

前三行：
```
0  | 582454ab2c66dc2d42047bf8 | Witley Colliery    | England | Dudley   | Dudley (Un-parished)   | 395255.499 | 283988.833 | 52.453832 | -2.071245 | ... | POINT (-2.07124 52.45383)
1  | 57fe3a562c66dcab3d04f7db | Victoria Colliery  | England | Sandwell | Sandwell (Un-parished) | 400105.422 | 290519.532 | 52.512565 | -1.999876 | ... | POINT (-1.99988 52.51256)
2  | 57fe3a642c66dcab3d04f7e5 | Lyttleton Colliery | England | Sandwell | Sandwell (Un-parished) | 400022.413 | 290345.942 | 52.511004 | -2.001100 | ... | POINT (-2.00110 52.51100)
```

**输出解读**：
- **`geometry` 现在是 `POINT` 而不是 `POLYGON`**——Notebook 明确提示：「Once again we have a geometry column. However, now it is called a **POINT** rather than polygon.」
- **有意思的一点**：这份数据**同时**提供了 `osgb_east`/`osgb_north`（BNG 米）**和** `latitude`/`longitude`（度）**和** `geometry`（POINT，用的是经纬度）。也就是说同一份位置信息存了三遍。
- `final_text` 是煤矿名称（来自古地图上的文字标注），`nation` = England/Scotland/Wales，`local_auth` = 地方行政区，`parish` = 教区。
- `field_11` ~ `field_15` 全是 `None` —— **真实数据里的空列**，很常见。
- 3092 个煤矿，说明英国历史上煤矿密度极高。

#### 步骤 2 — 检查并转换 CRS

```python
cdf.crs
```

**输出**：
```
<Geographic 2D CRS: EPSG:4326>
Name: WGS 84
Axis Info [ellipsoidal]:
- Lat[north]: Geodetic latitude (degree)
- Lon[east]: Geodetic longitude (degree)
Area of Use:
- name: World.
- bounds: (-180.0, -90.0, 180.0, 90.0)
Datum: World Geodetic System 1984 ensemble
- Ellipsoid: WGS 84
- Prime Meridian: Greenwich
```

**输出解读（与基岩数据对比，这是本周最重要的对照）**：

| | 基岩 `gdf` | 煤矿 `cdf` |
|---|---|---|
| 类型 | **Projected** CRS | **Geographic 2D** CRS |
| EPSG | 27700（OSGB36 / BNG） | **4326（WGS 84）** |
| 轴信息 | `[cartesian]` Easting/Northing | `[ellipsoidal]` Lat/Lon |
| **单位** | **metre（米）** | **degree（度）** |
| 适用范围 | 英国 | `World.` bounds (-180, -90, 180, 90) |
| 椭球 | Airy 1830 | WGS 84 |

**两个数据集 CRS 完全不同！** 这就是老师反复强调的场景——两个不同来源的数据，一个是英国官方格网，一个是 GPS 标准。**如果直接叠加会得到荒谬的地图**（一层在数十万米量级，一层在个位数度量级，根本不在同一个坐标空间）。

```python
cdf_wm = cdf.to_crs(epsg=3857)   # 统一到 Web Mercator
cdf_wm
```

**输出**：`3092 rows × 16 columns`，geometry 从 `POINT (-2.07124 52.45383)` 变成了 Web Mercator 米制坐标。（注意：`osgb_east`、`latitude` 等**普通属性列不会跟着变**——`.to_crs` 只改 geometry 列。这是一个容易搞混的点。）

#### 步骤 3 — 把点叠到多边形地图上

```python
# Create a new axis for our bedrock map, using the same options as before.
ax1_new = gdf_wm.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k",
                      cmap="gist_ncar", legend=True,
                      legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5), "fontsize": 7})
# Now plot data from our new colliery dataframe, cdf_wm, specifying the axis to host the datapoints.
cdf_wm.plot(ax=ax1_new, marker='o', color='red', markersize=5)   # ← 关键：ax=ax1_new
# Use contextily to add a basemap.
cx.add_basemap(ax1_new, crs='EPSG:3857')
plt.show()
```

**输出**：`output_24_0.png` —— 基岩彩色底图 + 3092 个红色小点。

**输出解读（科学判读）**：红点应集中在几个熟悉的英国煤田——南威尔士、约克郡/诺丁汉郡、兰开夏郡、诺森伯兰/达勒姆、苏格兰中部地带（Midland Valley）。老师说：「what you'll see is where those red points are represent the **appropriate bedrock** that people would have mined through to extract the coal」——这些位置的基岩确实是石炭纪煤系地层。**这就是本周做的第一个「用地图验证科学假设」。**

**语法要点**：`ax=ax1_new` 是叠图层的**唯一机制**。第一次 `.plot()` 不带 `ax=`（它创建新的），之后每一层都要带。

---

### 5.4 空间连接 `sjoin` 与裁剪 `clip`

**问题**：现在想做一张图，**只显示煤矿实际落在其上的那些基岩多边形**。用手工条件筛选做不到——你没法写出「与这 3092 个点中任意一个相交」的条件表达式。

**`.sjoin()` 是什么？** Notebook：「The `.sjoin` (spatial join) function in GeoPandas is a tool for **combining two GeoDataFrames based on their spatial relationship**. It's akin to a standard join in Pandas, but instead of **joining on keys**, it joins based on **spatial relationships** between the geometries.」

```python
# Spatial join
joined_df = gpd.sjoin(gdf_wm, cdf_wm)   # left=基岩多边形, right=煤矿点
joined_df
```

**输出**：`3081 rows × 72 columns`

列名：`LEX, LEX_D, LEX_RCS, RCS, RCS_X, RCS_D, RANK, BED_EQ, BED_EQ_D, MB_EQ, ..., osgb_east, osgb_north, latitude, longitude, notes, field_11, ..., field_15`
索引：`368, 616, 967, 1224, 1298, ..., 11235, 11235, 11235, 11235, 11235`

**输出解读（这一步的四个关键观察）**：

1. **行数 3081**（不是 11244，也不是 3092）。原始煤矿 3092 个，结果 3081 行 → 有 **11 个煤矿没有落在任何基岩多边形内**（可能在海岸线外、或数据边界外、或坐标有误）。默认的 `how='inner'` 只保留**两边都匹配上**的记录。

2. **列数 72 = 56（左表全部） + 15（右表 16 列去掉 geometry） + 1（`index_right`）**。

3. **索引出现重复**（末尾连续 5 个 `11235`）→ 说明**同一个基岩多边形上有多个煤矿**，每个匹配产生一行，所以左表的行被复制了多次。这是 join 的标准行为（一对多）。

4. **`geometry` 列里是 POLYGON，不是 POINT**！Notebook 明确解释：
   > 「Our new dataframe however only contains **polygons**. This is because, **by default, in a spatial join the geometries from the 'left' data frame are retained in the output**. The 'right' data frame's geometries **do not appear** in the resulting data frame; instead, the **attributes (columns)** of the right data frame are joined to the geometries of the left data frame based on the specified spatial relationship.」

   **这是 sjoin 最重要、也最容易踩的一个坑**：sjoin 之后你只剩下 left 的几何。

#### 用 `.value_counts()` 分析基岩分布

```python
# Analyze distribution
distribution = joined_df['RCS_D'].value_counts()   # 统计各岩性出现次数，降序
# Print the distribution list
print(distribution)
```

**输出**：
```
RCS_D
MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTONE AND FERRICRETE          2478
SILTSTONE AND SANDSTONE WITH SUBORDINATE MUDSTONE                        200
SEDIMENTARY ROCK CYCLES, CLACKMANNAN GROUP TYPE                          123
MUDSTONE, SILTSTONE AND SANDSTONE                                         72
DOLOMITISED LIMESTONE AND DOLOMITE                                        61
SANDSTONE AND CONGLOMERATE, INTERBEDDED                                   49
LIMESTONE, ARGILLACEOUS ROCKS AND SUBORDINATE SANDSTONE, INTERBEDDED      34
LIMESTONE, SANDSTONE, SILTSTONE AND MUDSTONE                              23
LIMESTONE WITH SUBORDINATE SANDSTONE AND ARGILLACEOUS ROCKS               14
MAFIC IGNEOUS-ROCK                                                        12
DOLERITE AND THOLEIITIC BASALT                                             5
MUDSTONE, SILTSTONE, LIMESTONE AND SANDSTONE                               5
MAFIC LAVA AND MAFIC TUFF                                                  2
SANDSTONE, SILTSTONE AND MUDSTONE                                          1
SEDIMENTARY ROCK CYCLES, STRATHCLYDE GROUP TYPE                            1
SANDSTONE, LIMESTONE AND ARGILLACEOUS ROCKS                                1
Name: count, dtype: int64
```

**输出解读（这是本周最有科学价值的一个输出，务必看懂）**：

- **总数 = 2478+200+123+72+61+49+34+23+14+12+5+5+2+1+1+1 = 3081** ✓ 与行数吻合。
- **压倒性第一名（2478 / 3081 ≈ 80.4%）：`MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTONE AND FERRICRETE`**——这**字面上就写着 COAL**，正是**石炭纪煤系地层（Carboniferous Coal Measures）**的标准 BGS 描述。八成的英国历史煤矿坐落在这个地层单元上，**完全符合地质预期**。这就是「数据结果验证了科学常识」的漂亮案例。
- 第二、三名（`SILTSTONE AND SANDSTONE WITH SUBORDINATE MUDSTONE`、`SEDIMENTARY ROCK CYCLES, CLACKMANNAN GROUP TYPE`）也都是石炭纪的碎屑岩序列；**Clackmannan Group 是苏格兰中部地带的石炭纪含煤岩系**，对应苏格兰煤田。
- 末尾出现 `MAFIC IGNEOUS-ROCK`（12）、`DOLERITE AND THOLEIITIC BASALT`（5）、`MAFIC LAVA AND MAFIC TUFF`（2）——**火成岩上不可能有煤矿**。这些是**边界效应**：矿点恰好落在一个侵入岩床/岩墙的多边形范围内（石炭纪煤系常被辉绿岩床侵入），或者点的定位有几十米误差。**这提醒我们：GIS 结果永远要用地质常识回头检查。**
- `Name: count, dtype: int64` 是 `.value_counts()` 返回 Series 的标准尾注。

#### `.clip()` 把点也筛出来

**问题**：`joined_df` 里只有多边形，点没了。怎么办？

**解法**：用 `joined_df` 的多边形去 **clip** 原始的点数据框。

```python
cdf_wm_clipped = cdf_wm.clip(joined_df)   # 用 joined_df 的几何范围裁剪 cdf_wm
cdf_wm_clipped
```

**输出**：`3081 rows × 16 columns`

索引：`2206, 2273, 2205, 2208, 2207, ..., 870, 2133, 910, 3087, 146`（**顺序被打乱了**——clip 会按空间顺序重排）

样例行：
```
2206 | 57f20d772c66dca32201cbc2 | Breach Colliery (Disused)     | England | Mendip | Leigh-on-Mendip | 369557.075 | 148833.907 | 51.237867 | -2.437452 | ... | POINT (-271335.924 6663477.961)
2273 | 57f20d922c66dca32201cbc4 | Vobster Colliery (Disused)    | England | Mendip | Mells           | 370133.344 | 148879.812 | 51.238310 | -2.429202 | ... | POINT (-270417.485 6663556.786)
2205 | 5854451c2c66dc10b80071de | Mackintosh Colliery           | England | Mendip | Coleford        | 369118.210 | 149774.007 | 51.246296 | -2.443820 | ... | POINT (-272044.758 6664976.843)
```

**输出解读**：
- **3081 行**，与 `joined_df` 的行数一致 ✓ 说明这两种方法（sjoin / clip）挑出了同一批煤矿。
- **16 列**，保留了点数据框的全部原始列 ✓
- `geometry` 是 **POINT，且是 Web Mercator 坐标** ✓
- 索引不再从 0 开始且乱序 → clip 保留了**原始索引**但重排了行顺序。
- 数据本身也有意思：Mendip（萨默塞特的门迪普丘陵）的 "Breach Colliery (**Disused**)"、"Vobster Colliery (Disused)" ——名字里就带"废弃"，这是历史地图上的原始标注。老师说：「Obviously a lot of them are closed. Well, **all** of them are closed now.」

#### 画出「只有重叠部分」的地图

```python
ax4 = joined_df.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k",
                     cmap="gist_ncar", legend=True,
                     legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5), "fontsize": 7})
cdf_wm_clipped.plot(ax=ax4, marker='o', color='red', markersize=5)
cx.add_basemap(ax4, crs='EPSG:3857')
plt.show()
```

**输出**：`output_33_0.png` —— Notebook 说：「Notice how **only a subset of both polygons and points** are now displayed, but **both align**.」也就是说，基岩多边形只剩下有煤矿的那些（英国煤田的形状清晰浮现出来），点也只剩落在这些多边形内的。图例从几十类缩短到 16 类。

#### 柱状图

```python
# Create a histogram
plt.figure(figsize=(10, 6))       # 新建一张 10×6 英寸的空白图
distribution.plot(kind='bar')     # 直接在 value_counts() 结果 Series 上画柱状图
plt.title('Distribution of Bedrock Types')
plt.xlabel('Bedrock Type')
plt.ylabel('Frequency')
plt.xticks(rotation=90)           # x 轴标签旋转 90°，因为岩性名称非常长
plt.show()
```

**输出**：`output_35_0.png` —— 第一根柱子（2478）远远高过其余所有柱子，视觉上极其醒目。

**要点**：
- `distribution` 是 pandas Series，Series 也有 `.plot()`，`kind='bar'` 出柱状图。
- `plt.xticks(rotation=90)` 是必需的——不转的话 16 个超长岩性名会糊成一团。
- 这里用的是 **plt 的状态机接口**（`plt.figure()` → `plt.title()` → `plt.show()`），和前面的 `ax` 面向对象接口不同。两种风格都要认识。

---

### 5.5 Exercise 2：画泥岩基岩上的煤矿地图

**题目要求**（Notebook 标题写的是 "Create a map of collieries on mudstone bedrock"，但目录里写作 "Plot the distribution of bedrock under collieries across the UK"）：重复上面的演示，但**只用含泥岩（MUDSTONE）的基岩数据框**做空间连接。数据框名已给：`gdf_wm_ex2`。

**解题思路**（三步串联，是本周最能考察"组合能力"的一题）：
1. 先用 `.str.contains('MUDSTONE')` 从基岩数据里筛出泥岩子集 → `gdf_wm_ex2`；
2. 再把这个子集与煤矿点做 `sjoin` → `joined_df_ex2`（结果只含多边形）；
3. 用 `joined_df_ex2` 去 clip 煤矿点，然后两层一起画。

**完整代码**：
```python
# -------'INSERT CODE HERE'-------
# Create a subset dataframe with entries that only include 'MUDSTONE'
gdf_wm_ex2 = gdf_wm[gdf_wm["RCS_D"].str.contains('MUDSTONE')]

# Perform spatial join —— 把泥岩多边形和全部煤矿点做空间连接
joined_df_ex2 = gpd.sjoin(gdf_wm_ex2, cdf_wm)

# Create map
# ⚠️ 注意这里多了一个 .geom_type == 'Polygon' 的过滤
ax_ex2 = joined_df_ex2[joined_df_ex2.geom_type == 'Polygon'].plot(
    figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k", cmap="gist_ncar",
    legend=True, legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5), "fontsize": 7})
# 这里把 clip 和 plot 链在一起写，一行完成"裁剪 + 画点"
cdf_wm.clip(joined_df_ex2).plot(ax=ax_ex2, marker='o', color='red', markersize=5)
cx.add_basemap(ax_ex2, crs='EPSG:3857')
plt.show()
# --------------------------------
```

**输出**：`output_37_0.png` —— 只有泥岩相关基岩 + 落在其上的煤矿点。

**两个值得注意的写法**：

1. **`joined_df_ex2[joined_df_ex2.geom_type == 'Polygon']`** —— 为什么要加这一句？
   `.geom_type` 返回每行几何体的类型字符串。GeoDataFrame 的几何列**可以混合不同类型**（Polygon、MultiPolygon、GeometryCollection……）。sjoin 之后如果混进了非 Polygon 的几何体，`.plot()` 可能报错或画出奇怪的东西。这句话是一个**防御性过滤**，只保留纯 Polygon。（副作用：如果数据里有 `MultiPolygon`，它们会被**丢掉**——因为 `'MultiPolygon' != 'Polygon'`。这是个潜在的坑。）

2. **`cdf_wm.clip(joined_df_ex2).plot(ax=ax_ex2, ...)`** —— **方法链（method chaining）**。等价于：
   ```python
   temp = cdf_wm.clip(joined_df_ex2)
   temp.plot(ax=ax_ex2, marker='o', color='red', markersize=5)
   ```
   写成一行更简洁，但调试时不好检查中间结果。

**科学判读**：泥岩是煤系地层的主要组成之一（`MUDSTONE, SILTSTONE, SANDSTONE, COAL, IRONSTONE AND FERRICRETE` 里就有 MUDSTONE），所以这张图应该**非常接近**上面那张全岩性的图——因为 80% 的煤矿本来就在这个类别上。

---

### 5.6 Exercise 3：大曼彻斯特的煤矿位置与下伏基岩

**题目要求**：给定一个包含**大曼彻斯特各行政区形状**的 GeoJSON 文件，用它的几何去 clip 现有的基岩和煤矿数据框，做出一张大曼彻斯特地图。Notebook 提示：「Please remember that **each dataframe should use the same Coordinate Reference System (CRS)**.」

**解题思路（标准 GIS workflow，四步）**：
1. **Load** → `gpd.read_file()` 读 GeoJSON；
2. **Check / Convert CRS** → `.to_crs(epsg=3857)`；
3. **Clip** → 用 GM 的几何裁剪基岩和煤矿；
4. **Plot** → 叠三层 + 底图。

**完整代码**：
```python
# -------'INSERT CODE HERE'-------
# Location of the GM authority geometries
file_GM = path+"/data/gmauthorities.geojson"      # 注意扩展名是 .geojson，不是 .shp
# Read the .geojson file into a new dataframe
GMdf = gpd.read_file(file_GM)                     # gpd.read_file 同一个函数吃 GeoJSON
# Convert to EPSG:3857 —— 必须！否则 clip 会得到空结果或错误结果
GMdf_wm = GMdf.to_crs(epsg=3857)

# Clip the bedrock dataframe —— 用 GM 边界当"饼干模具"，把全国基岩切出 GM 那一块
gdf_wm_GM = gdf_wm.clip(GMdf_wm)
# Clip the colliery dataframe —— 同样切出 GM 范围内的煤矿点
cdf_wm_GM = cdf_wm.clip(GMdf_wm)

# Create a map
ax_ex3 = gdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="RCS_D", edgecolor="k",
                        cmap="gist_ncar", legend=True,
                        legend_kwds={"loc": "center left", "bbox_to_anchor": (1, 0.5), "fontsize": 7})
cdf_wm_GM.plot(ax=ax_ex3, marker='o', color='red', markersize=8)   # markersize 从 5 调到 8：区域尺度点要更大
#cx.add_basemap(ax3, source="basemap_GM.tif")     ← 注释掉的一行：用本地 tif 当底图的写法
cx.add_basemap(ax_ex3, crs='EPSG:3857')
plt.show()
# --------------------------------
```

**输出**：`output_39_0.png` —— 大曼彻斯特范围内的基岩地质 + 煤矿点。

**输出解读 / 科学与历史背景**：老师说他在 Salford 长大，认得其中一些煤矿。大曼彻斯特位于 **Lancashire Coalfield（兰开夏煤田）**的核心地带，Wigan、Bolton、Leigh、Salford 一带历史上煤矿极密集，这正是曼彻斯特成为工业革命中心的地质基础。图上煤矿点应该在 GM 的西部/西北部（Wigan、Bolton）密集，东南部（Stockport、Trafford）稀疏。

**`GMdf_wm` 数据框内容**（后面会再次用到，先看清楚）：`10 rows × 21 columns`

列名：`LGDNAME, AREA, LGDCode, OBJECTID, NAME, AREA_CODE, DESCRIPTIO, FILE_NAME, NUMBER, NUMBER0, ..., UNIT_ID, CODE, HECTARES, TYPE_CODE, DESCRIPT0, TYPE_COD0, DESCRIPT1, X, Y, geometry`

前三行：
```
0 | ... | NAME = 'Trafford District (B)'    | AREA_CODE='MTD' | DESCRIPTIO='Metropolitan District' | CODE='E08000009' | HECTARES=10604.476 | geometry = MULTIPOLYGON (((-270251.496 7055260.349, ...)))
1 | ... | NAME = 'Manchester District (B)'  | AREA_CODE='MTD' | DESCRIPTIO='Metropolitan District' | CODE='E08000003' | HECTARES=11564.826 | geometry = MULTIPOLYGON (((-254514.620 7052821.304, ...)))
2 | ... | NAME = 'Wigan District (B)'       | AREA_CODE='MTD' | DESCRIPTIO='Metropolitan District' | CODE='E08000010' | HECTARES=18817.091 | geometry = MULTIPOLYGON (((-290781.985 7072493.189, ...)))
```

**要点**：
- **10 行 = 大曼彻斯特的 10 个都市自治区（metropolitan districts）**：Manchester、Salford、Trafford、Stockport、Tameside、Oldham、Rochdale、Bury、Bolton、Wigan。
- **`NAME` 列**是后面 Exercise 5 用来挑 Stockport 的关键列。
- **`geometry` 是 `MULTIPOLYGON`**（不是 Polygon）——因为一个行政区可能包含多块不连通的区域（飞地、河中岛等）。
- `CODE` 是 ONS 的标准地理编码（E08000003 = Manchester）。
- `HECTARES` = 面积（公顷）。

---

### 5.7 Exercise 4：绘制大曼彻斯特的洪水风险区

**数据背景**（务必理解，这是本周科学含量最高的部分）：

来自 **Environment Agency（英国环境署）**的 [Flood Map for Planning (Rivers and Sea) Flood Zone 2]。

> **Flood Zone 2 的定义**：预计**每年有 0.1% 概率发生洪水**的区域。（0.1% 年概率 ≈ **千年一遇**洪水的淹没范围。）Notebook 说「The actual use of this data for planning is somewhat complex」——实际规划用途比较复杂，这里只做可视化。

**洪水类型**（Notebook 引用了一个 ArcGIS StoryMap）：

| 类型 | 中文 | 成因 |
|---|---|---|
| **Fluvial** | 河流洪水 | 河流漫溢 |
| **Pluvial** | 地表水洪水 | 降雨造成的地表径流积水 |
| **Tidal** | 海岸洪水 | 潮汐、风暴潮（storm surge） |

本数据集含 **Tidal 和 Fluvial** 两类（Flood Map for Planning 是 rivers and sea 的，不含 pluvial）。

**题目要求**：做**两张图**：
- 图 1：整个数据集的完整范围，按**预测的洪水成因**分类标注；
- 图 2：同样的信息，但只覆盖大曼彻斯特区域。

提示：「You will also need to **identify which column** to use that contains information on the predicted cause.」（要自己找出哪一列存了成因信息——答案是 `type` 列。）

**图 1 完整代码**：
```python
# Figure 1 - plot entire dataset
# -------'INSERT CODE HERE'-------
file_flood_risk = path+"/data/EA_floodrisk_level2/Environment_Agency_Flood_Zone_2.shp"
frdf = gpd.read_file(file_flood_risk)          # frdf = flood risk dataframe
frdf_wm = frdf.to_crs(epsg=3857)               # 照例统一 CRS
ax_ex4 = frdf_wm.plot(figsize=(16, 16), alpha=0.3,
                      column="type",           # ← 关键：按洪水成因分类着色
                      edgecolor="k",
                      cmap="winter",           # 换了配色：winter 是蓝-绿渐变，适合"水"的主题，且只有 2 类
                      legend=True)             # 只有 2 类，图例很短，不需要 legend_kwds
cx.add_basemap(ax_ex4, crs='EPSG:3857', zoom=10)   # ← 新参数：zoom=10
plt.show()
# --------------------------------
```

**输出**：`output_41_0.png` —— 全英范围的洪泛区，沿所有主要河流和海岸线呈树枝状/带状分布，两种颜色区分 Tidal 与 Fluvial（沿海是 Tidal，内陆沿河是 Fluvial）。老师说这个范围「produces a much bigger extent than the figure I showed in the lecture, but we'll narrow that down」。

**`zoom=10` 是什么？** contextily 的**瓦片缩放层级**。数字越大瓦片越精细、下载的瓦片越多、越慢。全国尺度用 10 就够；后面区域尺度用 12。**不指定的话 contextily 会自动推断**，但在大范围图上自动推断可能选得过高，导致下载几千张瓦片、卡住。

**图 2 完整代码**：
```python
# Figure 2 - plot the dataset covering only the Greater Manchester region
# -------'INSERT CODE HERE'-------
frdf_wm_GM = frdf_wm.clip(GMdf_wm)             # 用 Exercise 3 里已经建好的 GM 边界裁剪
ax_ex4b = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k",
                          cmap="winter", legend=True)
cx.add_basemap(ax_ex4b, crs='EPSG:3857', zoom=12)   # 区域尺度，zoom 提高到 12 看得更清
plt.show()
# --------------------------------
```

**输出**：`output_42_0.png` —— 大曼彻斯特范围内的洪泛区，沿 Irwell、Mersey、Medlock、Tame 等河流呈细长条带。GM 是内陆，所以基本全是 **Fluvial（河流洪水）**。

**要点**：这一题演示了**「代码复用」**——`GMdf_wm` 是 Exercise 3 里建的，直接拿来用；这就是为什么 Notebook 要求按顺序执行 cell。

---

### 5.8 Part 3：点与多边形之间的距离计算

#### 概念铺垫

Notebook 的解释（要点）：

> 在 GeoPandas 中，点与多边形之间的距离计算是通过 **`shapely`** 库完成的。这个过程测量的是**点几何体与多边形几何体最近部分之间的最短距离**。具体来说，对每个点，计算到多边形**最近的边界或顶点**的距离。**如果点落在多边形内部，到该多边形的距离视为 0。**

用途：「calculating distances to **environmental hazards**（环境危害）or inferring **accessibility to green space**（绿地可达性）」。

**方法签名**：在一个含点几何的 Series 上调用 `.distance()` 并传入一个多边形几何，返回一个新的 Series，装着每个点到该多边形的距离。反之亦然（多边形 GeoSeries 上调用、传入一个点，得到每个多边形到该点的距离）。

**⚠️ 关键提醒**：「the distance is calculated **in the coordinate system of the geometries**」——距离用的是几何体所在坐标系的单位。所以做距离测量**必须用投影坐标系**。Notebook 说：「**As if by magic**, we have been using a CRS (EPSG:3857) that is based on metres.」（其实不是魔法，是从一开始就规划好的。）

**Geographic vs Projected 在距离上的区别**：
- 地理坐标系（如 4326）：距离沿**椭球面**计算，数学复杂，尤其长距离；
- 投影坐标系：用**平面**计算，简单直接，但大范围下精度会下降。

#### 步骤 1 — 加载变电站数据 + `.centroid`

**数据背景**：来自 **UK National Grid** 官网的输电网路线图。**Substation（变电站）**：「Substations contain equipment that help ... network failures or power cuts.」——变电站是电网中变换电压、切换线路的关键节点，一旦被淹，会造成大面积停电。

```python
file_substation = path+"/data/Substations_10Dec23/Substations.shp"
ssdf = gpd.read_file(file_substation)      # ssdf = substation dataframe
ssdf_wm = ssdf.to_crs(epsg=3857)           # 统一 CRS

# copy GeoDataFrame —— 先复制一份，避免修改原数据框（也避免 SettingWithCopyWarning）
ssdf_wm_copy = ssdf_wm.copy()
# change geometry —— 把复杂的多边形几何替换成它们的质心（单点）
ssdf_wm_copy['geometry'] = ssdf_wm_copy['geometry'].centroid
ssdf_wm_copy
```

**输出**：`547 rows × 8 columns`

列名：`SUBSTATION, OPERATING_, ACTION_DTT, STATUS, Substation, OWNER_FLAG, GDO_GID, geometry`

前三行：
```
0 | SUBSTATION='DAMC4' | OPERATING_='400kV' | ACTION_DTT='2020-06-09' | STATUS='C' | Substation='DAMHEAD CREEK 400KV S/S' | OWNER_FLAG='Y' | GDO_GID=10051888.0 | POINT (66647.027 6696701.062)
1 | SUBSTATION='MONF2' | OPERATING_='275kV' | ... | Substation='MONK FRYSTON 275KV S/S' | ... | POINT (-140956.880 7124278.600)
2 | SUBSTATION='MONF2' | OPERATING_='275kV' | ... | Substation='MONK FRYSTON 275KV S/S' | ... | POINT (-141035.267 7124006.987)
```

**输出解读**：
- **`geometry` 现在是 `POINT`** ✓ `.centroid` 生效了。
- 注意有**两列名字很像**：`SUBSTATION`（全大写，是短代码 `DAMC4`、`MONF2`）和 `Substation`（首字母大写，是完整名称 `DAMHEAD CREEK 400KV S/S`）。**后面循环里用的是 `row['Substation']`——大小写敏感，写错会 KeyError！**
- `OPERATING_` 是电压等级（400kV / 275kV / 132kV / 25kV），列名被截断了（shapefile 的 DBF 属性表**列名最长 10 字符**，这是 shapefile 格式的经典限制，所以你会看到 `OPERATING_`、`ACTION_DTT`、`DESCRIPTIO`、`TYPE_COD0` 这类被砍掉尾巴的列名）。
- 索引 1 和 2 都是 `MONK FRYSTON 275KV S/S` 但坐标略有不同 → **同一个变电站站址有多个多边形要素**，取质心后就是多个近距离的点。

**`.centroid` 为什么要用？** Notebook 说：「This is **solely for the purpose of wanting to use single points to represent the substation location rather than complex geometries**.」——变电站原始数据是多边形（站区轮廓），但我们只关心「它在哪」，用单点更简洁，画在图上也更清楚，距离计算也更快。

**为什么先 `.copy()`？** 因为下一行要**修改 geometry 列**。如果直接改 `ssdf_wm`，原数据就被破坏了；如果 `ssdf_wm` 本身是另一个 DataFrame 的切片，还会触发 `SettingWithCopyWarning`。`.copy()` 是**正确且明确**的做法。

#### 步骤 2 — 裁剪到 GM 并画图

```python
ssdf_wm_GM = ssdf_wm_copy.clip(GMdf_wm)     # 变电站点裁剪到 GM
frdf_wm_GM = frdf_wm.clip(GMdf_wm)          # 洪泛区裁剪到 GM（重复了一次，无妨）
ax_ex4c = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k",
                          cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4c, marker='o', color='red', markersize=18)   # markersize 加大到 18
cx.add_basemap(ax_ex4c, crs='EPSG:3857', zoom=12)
plt.show()
```

**输出**：`output_46_0.png` —— GM 的洪泛区（蓝绿条带）+ 17 个红色变电站点。

（从后面 buffer 的输出可以数出 **GM 内有 17 个变电站**。）

#### 步骤 3 — `.buffer()` 建 1 km 风险圈

**`.buffer()` 是什么？** Notebook：

> `.buffer()` 方法用来**在 GeoSeries 或 GeoDataFrame 的几何体周围创建缓冲区**。它生成一个新的几何对象，表示**距原几何体给定距离内所覆盖的区域**。
> - 应用于**点** → 得到一个**圆**；
> - 应用于**线** → 得到一条指定宽度的**带状区域**；
> - 应用于**多边形** → 得到向外扩张的多边形。
>
> **距离使用 GeoDataFrame 的 CRS 单位**。如果 CRS 是经纬度（EPSG:4326），距离单位是**度**，对距离测量来说毫无直觉可言。

```python
# get circle with 1 km radius
risk_zone = ssdf_wm_GM.buffer(1000)   # 1000 米 = 1 km（因为 CRS 3857 单位是米）
risk_zone
```

**输出**：
```
389    POLYGON ((-235993.437 7060050.402, -235998.252...
174    POLYGON ((-236252.384 7060180.038, -236257.200...
393    POLYGON ((-252393.258 7061128.836, -252398.073...
407    POLYGON ((-252264.842 7061456.955, -252269.657...
16     POLYGON ((-226575.062 7074470.583, -226579.877...
492    POLYGON ((-226749.512 7074538.453, -226754.328...
387    POLYGON ((-263837.663 7062136.511, -263842.478...
209    POLYGON ((-266396.592 7063771.965, -266401.408...
60     POLYGON ((-267126.029 7064046.204, -267130.844...
59     POLYGON ((-266946.724 7064170.013, -266951.539...
137    POLYGON ((-226234.027 7074841.808, -226238.843...
320    POLYGON ((-240256.171 7081407.501, -240260.986...
31     POLYGON ((-261428.444 7083081.174, -261433.259...
62     POLYGON ((-245623.786 7098831.565, -245628.601...
219    POLYGON ((-245782.596 7098900.465, -245787.412...
223    POLYGON ((-261551.736 7083024.974, -261556.551...
225    POLYGON ((-261648.759 7083405.206, -261653.575...
dtype: geometry
```

**输出解读（四个关键观察）**：
1. **17 行** → GM 内有 17 个变电站（含同址多要素）。
2. **`POINT` 变成了 `POLYGON`** ✓ buffer 把点扩成了圆（用多边形逼近的圆）。
3. **`dtype: geometry`** 且没有列名 → 这是一个 **GeoSeries**（不是 GeoDataFrame）！它**只有几何，没有属性列**。所以后面画它的时候不能用 `column=` 参数。
4. **索引被保留**（389, 174, 393...）→ 与 `ssdf_wm_GM` 的索引一一对应，可以对照回去。

**验证 1 km 是否正确**：看第一行 `-235993.437` 和它的圆心。圆的采样点之间只差几米（`-235993.437` → `-235998.252`），说明这是一个用很多顶点逼近的圆，半径在 1000 米量级。在地图上看，圆的直径应该约等于 2 km，在 zoom=12 的城市尺度图上是一个明显但不夸张的小圈。

#### 步骤 4 — 画出带 buffer 的图

```python
ax_ex4d = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k",
                          cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4d, marker='o', color='red', markersize=18)
risk_zone.plot(ax=ax_ex4d, color="#ff000033")   # ← 8 位十六进制颜色！
cx.add_basemap(ax_ex4d, crs='EPSG:3857', zoom=12)
plt.show()
```

**输出**：`output_50_0.png` —— 洪泛区 + 红点 + 每个红点外围一个淡红色半透明圆。

**`color="#ff000033"` 这个"奇怪"的颜色码**：Notebook 说「In this example I specify a **strange looking** `color="#ff000033"` to create a **transparent circle** so we can better see the 1km distance zone.」

拆解 **8 位十六进制 RGBA**：
```
#  ff    00    00    33
   R     G     B     A(alpha)
   255   0     0     51
   纯红                20% 不透明度
```
- 前 6 位 `ff0000` = 纯红色（和普通 6 位 hex 一样）；
- **最后 2 位 `33` = alpha 通道**，十六进制 0x33 = 十进制 51，51/255 ≈ **20% 不透明度**。
- 这样圆是**半透明**的，能看到底下的洪泛区和底图。
- **这是 8 位 hex 颜色的标准写法**，值得记住：`#RRGGBBAA`。

#### 步骤 5 — 用 `for` 循环计算所有距离

**目标**：遍历每个变电站，算出它到所有洪泛区多边形的距离。

Notebook 的蓝色信息框逐句说明：
> - 创建一个 `for loop` 遍历 `ssdf_wm_GM` 中的每个变电站：
>   - `for index, row in ssdf_wm_GM.iterrows():` —— GeoPandas 数据框的 `.iterrows()` 方法返回**索引与行内容的唯一列表**。
>   - 我们通过打印 `row['Substation']` 来确认当前变电站的名字。
>   - `distances = frdf_wm_GM.geometry.distance(row.geometry)` —— **这是返回距离列表的关键命令**。
>     - `frdf_wm_GM.geometry.distance` —— `.geometry.distance(row.geometry)` 方法让我们计算 `frdf_wm_GM` 中所有多边形与 `(row.geometry)` 中信息之间的距离。
> - 每次循环我们把 distances 打印到屏幕上。

```python
for index, row in ssdf_wm_GM.iterrows():
    # Select one station in particular
    print(row['Substation'])              # 打印当前变电站全名（注意大小写！）
    # Measure distance from release to each station
    distances = frdf_wm_GM.geometry.distance(row.geometry)
    # ↑ frdf_wm_GM.geometry 是所有洪泛多边形的 GeoSeries
    #   row.geometry 是当前这一个变电站的 POINT
    #   结果 distances 是一个 Series：每个洪泛多边形到这个变电站的最短距离（米）
    print(distances)
```

**输出（节选，17 个变电站各一段）**：
```
BREDBURY 275KV S/S
995     15316.356074
1230    13617.006048
1891    20862.606691
1892    19995.599135
1917    20062.968048
            ...
7333    50787.963067
7392    49320.222082
7317    50234.510976
7318    50395.827465
7319    50398.403868
Length: 921, dtype: float64
BREDBURY 132KV S/S
995     15404.481203
...
Length: 921, dtype: float64
SOUTH MANCHESTER 275KV S/S
995     17739.808930
1230    14397.325286
1891     9706.535941
...
Length: 921, dtype: float64
...
（共 17 段）
```

17 个变电站依次是：
```
BREDBURY 275KV S/S       BREDBURY 132KV S/S
SOUTH MANCHESTER 275KV S/S   SOUTH MANCHESTER 132KV S/S
STALYBRIDGE 275KV S/S    STALYBRIDGE 25KV S/S    STALYBRIDGE 400KV S/S
DAINES 400KV S/S
CARRINGTON 275KV S/S     CARRINGTON 132KV S/S    CARRINGTON 400KV S/S
WHITEGATE 275KV S/S
KEARSLEY 275KV S/S       KEARSLEY 400KV S/S      KEARSLEY 132KV GSP S/S
ROCHDALE 132KV S/S       ROCHDALE 275KV SITE
```

**输出解读**：
- **`Length: 921`** → GM 内有 **921 个洪泛区多边形**。所以这个循环一共算了 17 × 921 = **15,657 次距离**。
- **`dtype: float64`** → 距离是浮点数，**单位是米**。
- 距离值在 9,000 ~ 51,000 米之间 → 也就是 9 km 到 51 km。**但这些都是"到某个特定多边形"的距离，不是"到最近洪泛区"的距离**——最近的那个还没显示出来（被 `...` 省略了）。
- **注意 Series 的索引（995, 1230, 1891...）不连续** → 因为 `frdf_wm_GM` 是从全国数据 clip 出来的，保留了原始索引。
- 变电站名带电压等级（275KV / 132KV / 400KV / 25KV），同一地点常有多个不同电压等级的变电站（BREDBURY 有 275 和 132 两个；STALYBRIDGE 有三个；CARRINGTON 有三个；KEARSLEY 有三个）。

**这个输出太长了、没法直接用**——这正是下一步要解决的问题。

#### 步骤 6 — 只保留最小距离

**思路**：我不想留下所有距离，**只想留最小的那个**。这样我就能判断：
- 距离 = 0 → 变电站**就在**洪泛区里；
- 距离 ≠ 0 → 记下它离最近洪泛区多远。

```python
min_distances=[]                                     # 初始化一个空列表来收集结果
for index, row in ssdf_wm_GM.iterrows():
    # Select one station in particular
    print(row['Substation'])
    # Measure distance from polygons to each station
    distances = frdf_wm_GM.geometry.distance(row.geometry)
    # Print the minimum distance
    print(distances.min())                           # .min() 取 Series 的最小值（单位：米）
    # Update min_distances list to account for the distance in km
    min_distances.append(distances.min()/1000.0)     # ← 除以 1000 转成 km 再存进列表

# Add this new list into our existing GeoPandas dataframe as a new column named 'min distance to flood'
ssdf_wm_GM['min distance to flood']=min_distances    # 列表长度 17 == 行数 17，直接赋值成新列
```

**输出**：
```
BREDBURY 275KV S/S
212.68743051913467
BREDBURY 132KV S/S
251.23069364215402
SOUTH MANCHESTER 275KV S/S
0.0
SOUTH MANCHESTER 132KV S/S
0.0
STALYBRIDGE 275KV S/S
0.0
STALYBRIDGE 25KV S/S
141.54007718982592
DAINES 400KV S/S
1588.087455581972
CARRINGTON 275KV S/S
201.78059738173124
CARRINGTON 132KV S/S
0.0
CARRINGTON 400KV S/S
0.0
STALYBRIDGE 400KV S/S
0.0
WHITEGATE 275KV S/S
1295.0350784971433
KEARSLEY 275KV S/S
136.3071588961682
ROCHDALE 132KV S/S
429.4027782829802
ROCHDALE 275KV SITE
269.9180509202209
KEARSLEY 400KV S/S
267.88594221561283
KEARSLEY 132KV GSP S/S
96.46211101706979
```
后面还跟着一段警告（见第六节详解）：
```
/Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/geopandas/geodataframe.py:1543: SettingWithCopyWarning:
A value is trying to be set on a copy of a slice from a DataFrame.
Try using .loc[row_indexer,col_indexer] = value instead
...
```

**输出解读（这是本周最有信息量的数值结果，逐条读）**：

| 变电站 | 最小距离 (m) | 判读 |
|---|---|---|
| BREDBURY 275KV | 212.7 | 距洪泛区约 213 m，**很近** |
| BREDBURY 132KV | 251.2 | 约 251 m |
| **SOUTH MANCHESTER 275KV** | **0.0** | **已在洪泛区内！** |
| **SOUTH MANCHESTER 132KV** | **0.0** | **已在洪泛区内！** |
| **STALYBRIDGE 275KV** | **0.0** | **已在洪泛区内！** |
| STALYBRIDGE 25KV | 141.5 | 约 142 m |
| DAINES 400KV | **1588.1** | **> 1 km，相对安全** |
| CARRINGTON 275KV | 201.8 | 约 202 m |
| **CARRINGTON 132KV** | **0.0** | **已在洪泛区内！** |
| **CARRINGTON 400KV** | **0.0** | **已在洪泛区内！** |
| **STALYBRIDGE 400KV** | **0.0** | **已在洪泛区内！** |
| WHITEGATE 275KV | **1295.0** | **> 1 km，相对安全** |
| KEARSLEY 275KV | 136.3 | 约 136 m |
| ROCHDALE 132KV | 429.4 | 约 429 m |
| ROCHDALE 275KV SITE | 269.9 | 约 270 m |
| KEARSLEY 400KV | 267.9 | 约 268 m |
| KEARSLEY 132KV GSP | 96.5 | **不到 100 m！最近的一个** |

**科学结论**：**17 个变电站中有 6 个（35%）距离为 0，即直接位于千年一遇洪泛区内**；另有 9 个在 1 km 内；只有 2 个（DAINES 400KV、WHITEGATE 275KV）超过 1 km。这是一个**触目惊心的基础设施风险画像**。Notebook 也指出这个议题已引发多项研究和政府项目（引用了 EEA Climate-ADAPT 的 "Flood defence framework for National Grid substations in United Kingdom" 案例），因为**极端天气事件的频率在上升**。

**⚠️ 一个容易混淆的单位问题**：
- **`print(distances.min())` 打印的是米**（212.68 m）；
- **`min_distances` 里存的是 `.min()/1000.0`，即千米**（0.21268 km）；
- **新列 `'min distance to flood'` 的单位是 km**。
这个不一致是刻意的（打印时看米更直观，存储用 km 便于后面和阈值 1 比较），但**读代码时必须留意**。

**语法要点**：
- `min_distances=[]` → **在循环外初始化空列表**，循环内 `.append()` 累积。这是 Python 最基础也最常用的模式。
- `ssdf_wm_GM['新列名'] = min_distances` → 用一个**长度与行数相同的 list** 直接创建新列。长度不匹配会 `ValueError: Length of values does not match length of index`。

#### 步骤 7 — 用 `lambda` + `.apply()` 按条件着色

```python
# Create a new column for colors
ssdf_wm_GM['color'] = ssdf_wm_GM['min distance to flood'].apply(lambda x: 'aqua' if x > 1 else 'red')
```

**输出**：又是一次 `SettingWithCopyWarning`（内容同上）。

**逐部分拆解**：
- `ssdf_wm_GM['min distance to flood']` → 取出 km 距离列（Series）；
- `.apply(func)` → **对 Series 的每个元素施加函数**，返回新 Series；
- `lambda x: 'aqua' if x > 1 else 'red'` → **匿名函数** + **条件表达式（三元运算符）**：
  - `lambda x:` 定义一个接收参数 x 的匿名函数；
  - `'aqua' if x > 1 else 'red'` 是 Python 的**条件表达式**，读作「如果 x > 1 就是 'aqua'，否则是 'red'」；
  - 等价于：
    ```python
    def pick_color(x):
        if x > 1:
            return 'aqua'
        else:
            return 'red'
    ssdf_wm_GM['color'] = ssdf_wm_GM['min distance to flood'].apply(pick_color)
    ```
- 阈值 `1` 的单位是 **km**（因为列的单位是 km），**恰好对应 1 km 的 buffer 半径**——设计上是一致的。

Notebook 的提醒：「**Do not worry about the `lambda` function.** This is a very efficient, but **not very readable**, way of performing a calculation dependent on conditions.」

**结果**：只有 DAINES 400KV（1.588 km）和 WHITEGATE 275KV（1.295 km）是 **aqua（安全）**，其余 15 个全是 **red（有风险）**。

#### 步骤 8 — 用颜色列画图

```python
ax_ex4e = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k",
                          cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4e, marker='o',
                color=ssdf_wm_GM['color'],     # ← 传一整列颜色，逐点着色
                markersize=18)
risk_zone.plot(ax=ax_ex4e, color="#ff000033")
cx.add_basemap(ax_ex4e, alpha=0.5, crs='EPSG:3857', zoom=12)   # ← 底图也加了 alpha=0.5
plt.show()
```

**输出**：`output_58_0.png` —— 「a **red** point represents an area at risk (under our definition) and an **aqua** point not at risk.」

**要点**：
- `color=` 参数既可以接受**单个颜色字符串**（`'red'`），也可以接受**一个与行数等长的颜色序列**（Series 或 list）。这是一个很实用的技巧。
- `cx.add_basemap(..., alpha=0.5, ...)` —— **给底图本身加透明度**，让底图变淡，数据层更突出。

#### 步骤 9 — 加行政区边界

```python
GMdf_wm      # 先预览一下 GM 数据框（10 rows × 21 columns，见 5.6 节）
```

```python
GMdf_wm.boundary.plot(edgecolor='blue')   # 单独画一下边界线看看效果
plt.show()
```

**输出**：
```
<Axes: >
```
以及 `output_62_1.png` —— 大曼彻斯特 10 个自治区的蓝色轮廓线（没有填充，没有底图）。

**注意那个 `<Axes: >` 输出**：这是因为 `.plot()` 返回了一个 Axes 对象，在 notebook 里最后一个表达式的值会被自动显示。`plt.show()` 之后仍然打印出来是 Jupyter 的行为。想抑制它可以写 `ax = GMdf_wm.boundary.plot(...)` 或在末尾加分号。

**`.boundary` 是什么？** 一个 GeoSeries 属性，把每个 **Polygon / MultiPolygon 转成它的边界 LineString / MultiLineString**。这样画出来就是**只有轮廓线、没有填充色**——正是我们想要的「行政区界」效果。（如果直接 `.plot()` 多边形，会把整个区域填满颜色，盖住下面的图层。）

```python
ax_ex4f = frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k",
                          cmap="winter", legend=True)
ssdf_wm_GM.plot(ax=ax_ex4f, marker='o', color=ssdf_wm_GM['color'], markersize=18)
risk_zone.plot(ax=ax_ex4f, color="#ff000033")
GMdf_wm.boundary.plot(ax=ax_ex4f, edgecolor='blue')   # ← 第四层：行政区边界
cx.add_basemap(ax_ex4f, alpha=0.5, crs='EPSG:3857', zoom=12)
plt.show()
```

**输出**：`output_64_0.png` —— **这就是老师在讲座里展示的那张最终地图**：
1. 底图（OpenStreetMap，alpha=0.5）
2. 洪泛区（蓝绿多边形，按 Tidal/Fluvial 分色，alpha=0.3）
3. 1 km 风险圈（半透明红圆）
4. 变电站点（红/aqua）
5. 大曼彻斯特各区边界（蓝线）

**这就是本周的「最终交付物」**——一张能讲故事的风险地图。老师说：「I've gone from loading data in with **not that much code** to produce that map.」

---

### 5.9 Exercise 5：Stockport 区的洪水与变电站风险地图

**题目要求**：用 `GMdf_wm` 中代表 **Stockport District** 的那个多边形去裁剪现有数据框，做一张只聚焦这个区的图。

**解题思路（本题的关键技巧）**：如何"取出 GM 数据框里的某一个区"？→ **组合使用「pandas 条件筛选」和「GeoPandas clip」**：
```python
GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)']
```
这个表达式返回一个**只有 1 行的 GeoDataFrame**，它的 geometry 就是 Stockport 的 MULTIPOLYGON。把它当 clip 的 mask 用即可。

**完整代码**：
```python
# -------'INSERT CODE HERE'-------
# Create new flood risk dataframe for Stockport
# 用 Stockport 那一行的几何去裁剪已经裁到 GM 的洪泛区数据（二次裁剪，进一步缩小）
Stock_frdf_wm_GM = frdf_wm_GM.clip(GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)'])

# Create new substation dataframe for Stockport
# 同理裁剪变电站点（注意 ssdf_wm_GM 此时已经带有 'min distance to flood' 和 'color' 两列）
Stock_ssdf_wm_GM = ssdf_wm_GM.clip(GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)'])

# Create new buffer zone
# ⚠️ 重新为 Stockport 的变电站生成 1 km 缓冲区。
#    这里复用了变量名 risk_zone —— 原来那个全 GM 的 risk_zone 被覆盖了！
risk_zone = Stock_ssdf_wm_GM.buffer(1000)

# Create new map —— 四层叠加，与上面完全同构
ax_ex5 = Stock_frdf_wm_GM.plot(figsize=(16, 16), alpha=0.3, column="type", edgecolor="k",
                               cmap="winter", legend=True)
Stock_ssdf_wm_GM.plot(ax=ax_ex5, marker='o', color='red', markersize=12)
risk_zone.plot(ax=ax_ex5, color="#ff000033")
# 用 GM 数据框自己 clip 自己的 Stockport 那一行，再取 boundary —— 得到 Stockport 的轮廓线
GMdf_wm.clip(GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)']).boundary.plot(ax=ax_ex5, edgecolor='blue')
cx.add_basemap(ax_ex5, alpha=0.5, crs='EPSG:3857', zoom=12)
plt.show()
# --------------------------------
```

**输出**：`output_66_0.png` —— 只有 Stockport 区的洪水/变电站风险地图。Stockport 内的变电站是 BREDBURY 275KV 和 BREDBURY 132KV（距离洪泛区 212.7 m 和 251.2 m），所以图上应该有两个红点，它们的 1 km 圈会明显与蓝绿色的洪泛条带（Mersey / Tame / Goyt 河谷）相交。

**四个值得注意的细节**：

1. **`'Stockport District (B)'` 里的 `(B)`** = **Borough（自治市镇）**。字符串必须**一字不差**，包括括号和空格。这是最容易出错的地方——写成 `'Stockport'` 会得到**空的结果**（clip 后 0 行），画出来是一张空白图，而且**不报错**！

2. **`.clip()` 可以链式二次裁剪**：`frdf_wm_GM` 已经是 GM 范围的了，再 clip 一次到 Stockport，完全合法。

3. **`GMdf_wm.clip(GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)'])`** 看起来很绕——「用自己的一个子集裁剪自己」。其实更直接的写法是：
   ```python
   GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)'].boundary.plot(ax=ax_ex5, edgecolor='blue')
   ```
   两者结果基本一样。参考答案用 clip 大概是为了保持代码风格一致。

4. **`risk_zone` 被重新赋值**：这在 notebook 里是常见但危险的做法——如果你之后又回头跑上面那个用 `risk_zone` 的 cell，画出来的就是 Stockport 的圈而不是全 GM 的圈了。**Notebook 的执行顺序依赖是真实存在的陷阱。**

---

### 5.10 Notebook 收尾总结（"What We Did"）

Notebook 自己的总结：

> 在这个 practical 中，我们：
> - 用 Python 介绍了 **GIS** 概念
> - 用 **GeoPandas** 处理空间（地图）数据
> - 学会了区分：
>   - **矢量数据**（点、线、面）
>   - **栅格数据**（网格化空间数据，概念性讨论）
> - 加载并使用了**地理空间文件格式**：Shapefile、GeoJSON
> - 在地图上可视化空间数据以展示真实世界位置
> - 组合多个空间数据集，探索不同要素如何关联
> - 聚焦真实案例：基岩地质、煤矿与采石场、洪水风险区
>
> 🧠 重点在于学习**空间数据如何被表示、组合和可视化**，以及**如何用 Python 探索 GIS 式的问题**。

五个练习的目标（Notebook 原文）：
- **Ex 1**：练习选择空间要素并在地图上可视化。
- **Ex 2**：探索工业遗址与下伏地质之间的关系。
- **Ex 3**：学习如何组合多个空间图层来回答基于位置的问题。
- **Ex 4**：理解 GIS 数据如何用来表示环境风险。
- **Ex 5**：看到空间筛选如何帮助我们把分析聚焦到一个具体的现实问题上。

---

## 六、易错点 / 重点难点

### 6.1 ⚠️ CRS 不统一（本周头号杀手）

**症状**：地图画出来「荒谬」——房子在海里、数据点全挤在图的一角、底图和数据完全错位、距离大到离谱、或者 clip 之后得到 **0 行**。

老师原话：「Typically if you get the CRS system wrong, **it will look ridiculous**. So you'll show houses in the sea, or your distances will be so large that doesn't make sense.」

**原因**：不同来源的数据用不同的 CRS。本周就遇到两种：
- 基岩（BGS）：EPSG:27700 OSGB36 / British National Grid（米）
- 煤矿（NLS）：EPSG:4326 WGS 84（度）

**修法**：
```python
# 1. 每次读完文件，先检查
print(gdf.crs)
# 2. 统一转换（注意必须赋值！）
gdf_wm = gdf.to_crs(epsg=3857)
# 3. 加底图时 crs 参数也要一致
cx.add_basemap(ax, crs='EPSG:3857')
```

**养成的 workflow**（老师原话）：**load the data in → preview it → make sure the CRS is right → 然后才做合并**。

### 6.2 ⚠️ `.to_crs()` 不是原地修改

```python
gdf.to_crs(epsg=3857)     # ❌ 结果被丢弃，gdf 一点没变
gdf = gdf.to_crs(epsg=3857)      # ✅
gdf_wm = gdf.to_crs(epsg=3857)   # ✅ 更好：保留原始数据框
```

同类的还有 `.clip()`、`.buffer()`、`.centroid`、`.to_crs()`——**GeoPandas 里绝大多数几何操作都返回新对象**。

### 6.3 ⚠️ `.buffer(1000)` 的单位取决于 CRS

- CRS = EPSG:3857（米）→ `buffer(1000)` = **1 km** ✅
- CRS = EPSG:4326（度）→ `buffer(1000)` = **1000 度**，完全没有意义（地球一圈才 360 度），画出来会覆盖整个宇宙，或者根本画不出来。

Notebook 原话：「if the CRS is in latitude and longitude (like EPSG:4326), the distance is **in degrees, which is not intuitive for distance measurements**.」

**同理适用于 `.distance()`**。

**记忆法**：**做距离/面积/缓冲之前，先确认 CRS 是 Projected（投影）而不是 Geographic（地理）**。看 `.crs` 输出的第一行：`<Projected CRS: ...>` 才安全。

### 6.4 ⚠️ `sjoin` 只保留左表的 geometry

**症状**：sjoin 之后想画点，结果画出来全是多边形。

**原因**：Notebook 明说「by default, in a spatial join **the geometries from the 'left' data frame are retained** in the output. The 'right' data frame's geometries **do not appear**」。

**修法（Notebook 用的方案）**：用 sjoin 的结果去 `clip` 原始的右表：
```python
joined_df = gpd.sjoin(gdf_wm, cdf_wm)       # 得到多边形 + 点的属性
cdf_wm_clipped = cdf_wm.clip(joined_df)     # 再用多边形把点切出来
# 然后两个一起画
```

### 6.5 ⚠️ `SettingWithCopyWarning`（本周唯一出现的实际警告）

**完整警告信息**：
```
/Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/geopandas/geodataframe.py:1543: SettingWithCopyWarning:
A value is trying to be set on a copy of a slice from a DataFrame.
Try using .loc[row_indexer,col_indexer] = value instead

See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
  super().__setitem__(key, value)
```

**它出现了两次**：
1. `ssdf_wm_GM['min distance to flood'] = min_distances`
2. `ssdf_wm_GM['color'] = ssdf_wm_GM['min distance to flood'].apply(...)`

**为什么会出现？**
`ssdf_wm_GM` 是通过 `ssdf_wm_copy.clip(GMdf_wm)` 得到的。pandas 无法确定这个结果是**原数据的视图（view）**还是**独立的副本（copy）**。当你往一个"可能是视图"的对象上写新列时，pandas 就警告你：**你的修改可能不会传播到原数据框，也可能意外修改了原数据框**。

**这是 Warning 不是 Error**——代码照常执行，结果也是对的。但它提示了一个潜在的隐患。

**正确的修法（两种）**：
```python
# 方法 1：显式复制（最简单、最常用）
ssdf_wm_GM = ssdf_wm_copy.clip(GMdf_wm).copy()

# 方法 2：用 .loc 显式赋值
ssdf_wm_GM.loc[:, 'min distance to flood'] = min_distances
```

**注意 Notebook 里自己就用过正确做法**：`ssdf_wm_copy = ssdf_wm.copy()` —— 在改 geometry 列之前先 `.copy()`，所以那一步**没有**触发警告。这是一个很好的对照。

**如何读这类 traceback**：
- 第一行是**文件路径 + 行号 + 警告类型**（`geodataframe.py:1543: SettingWithCopyWarning`）；
- 中间是**问题描述**和**建议修法**（`Try using .loc[...] instead`）；
- 最后是**触发警告的那行代码**（`super().__setitem__(key, value)`）。
- **看到路径在 site-packages 里，说明警告来自库内部，但根因在你的代码**。

### 6.6 ⚠️ `.str.contains()` 的三个坑

1. **大小写敏感**：`RCS_D` 全是大写，写 `'sandstone'` 会一个都匹配不到（返回空 DataFrame，画出空白图，**不报错**）。
   - 修法：`.str.contains('sandstone', case=False)`
2. **列里有 NaN 会报错**：`ValueError: Cannot mask with non-boolean array containing NA / NaN values`
   - 修法：`.str.contains('X', na=False)`
3. **它是子串匹配，会顺带匹配到你没预期的类别**：`'LIMESTONE'` 会匹配 `'DOLOMITISED LIMESTONE AND DOLOMITE'`；但**匹配不到** `'CHALK'`（虽然白垩就是石灰岩）。
   - 另外 `.str.contains()` 默认把参数当**正则表达式**，所以 `.`、`*`、`(` 等字符有特殊含义。字面匹配用 `regex=False`。

### 6.7 ⚠️ 列名大小写与截断

- Substations 数据里同时有 **`SUBSTATION`**（代码）和 **`Substation`**（全名）两列。`row['substation']`（全小写）会 **`KeyError: 'substation'`**。
- **Shapefile 的 DBF 属性表列名最多 10 个字符**——所以你会看到 `OPERATING_`、`ACTION_DTT`、`DESCRIPTIO`、`TYPE_COD0`、`DESCRIPT1` 这些被截断的列名。**这是格式限制，不是数据错误**。GeoJSON 就没有这个限制。

### 6.8 ⚠️ 忘记传 `ax=`

```python
ax1 = gdf_wm.plot(...)          # 建 ax
cdf_wm.plot(marker='o', ...)    # ❌ 没传 ax= —— 会画在一张全新的图上！
cdf_wm.plot(ax=ax1, marker='o', ...)   # ✅
```
**症状**：本该叠在一起的两层，出来是两张独立的图。

### 6.9 ⚠️ `clip` 的 mask 写错 → 静默返回空

```python
GMdf_wm[GMdf_wm['NAME']=='Stockport']        # ❌ 少了 ' District (B)' → 0 行
frdf_wm_GM.clip(<0 行的 GeoDataFrame>)        # → 得到 0 行，画出空白图，不报错
```
**修法**：clip 之前先检查 mask：
```python
mask = GMdf_wm[GMdf_wm['NAME']=='Stockport District (B)']
print(len(mask))          # 应该是 1
print(GMdf_wm['NAME'].unique())   # 不确定时先看看有哪些取值
```

### 6.10 ⚠️ `.geom_type` 过滤会丢掉 MultiPolygon

Exercise 2 用了 `joined_df_ex2[joined_df_ex2.geom_type == 'Polygon']`。这**只保留 `Polygon`，会丢掉 `MultiPolygon`**。想都保留应该写：
```python
df[df.geom_type.isin(['Polygon', 'MultiPolygon'])]
```

### 6.11 ⚠️ `cx.add_basemap()` 很慢 / 失败

- **慢**：老师明确警告「maybe a couple of minutes or so」，因为它在**从服务器下载瓦片**。Colab 上更慢。**不要以为是死机。**
- **失败**：没联网就用不了（Notebook：「Note this is a **web service** so if not connected to the internet this may not work.」）。
- **`zoom=` 太大会灾难性变慢**：zoom 每 +1 瓦片数量 ×4。全国尺度用 10，城市尺度用 12，别乱调大。
- **`crs=` 写错**：底图会与数据完全错位（数据在英国，底图在非洲海面上）。

### 6.12 ⚠️ 环境问题：PROJ 路径

如果 `.crs` 或 `.to_crs()` 报错（如 `CRSError` / `Cannot find proj.db`），检查环境变量：
```python
import os
os.environ["PROJ_DATA"] = "/opt/conda/envs/gis-practical/share/proj"
os.environ["PROJ_LIB"]  = "/opt/conda/envs/gis-practical/share/proj"
```
这是曼大 JupyterHub（固定 Python 3.12）上的已知问题，Notebook 第一个 cell 就处理了。

### 6.13 ⚠️ 单位混淆（米 vs 千米）

本周的距离代码里：
- `distances` 和 `distances.min()` → **米**
- `min_distances` 列表和 `'min distance to flood'` 列 → **千米**（因为 `/1000.0`）
- `lambda x: 'aqua' if x > 1 else 'red'` 里的 `1` → **1 千米**
- `buffer(1000)` 里的 `1000` → **1000 米**

**同一段代码里两种单位并存**。写作业时建议在列名里写明单位，如 `'min_distance_to_flood_km'`。

### 6.14 ⚠️ Notebook 的执行顺序依赖

本周 Notebook 里大量后面的 cell 依赖前面创建的变量（`GMdf_wm`、`frdf_wm_GM`、`ssdf_wm_GM`、`risk_zone`），而且 **Exercise 5 还覆盖了 `risk_zone`**。
**必须从上到下顺序执行**；跳着跑或反复跑会得到不一致的结果。作业里如果遇到「明明代码一样结果不同」，先 **Restart Kernel & Run All**。

### 6.15 GeoSeries vs GeoDataFrame

`risk_zone = ssdf_wm_GM.buffer(1000)` 返回的是 **GeoSeries**（只有几何，`dtype: geometry`，没有列名）。所以：
- `risk_zone.plot(color=...)` ✅
- `risk_zone.plot(column='xxx')` ❌ 没有列可用
- `risk_zone['某列']` ❌

想变回 GeoDataFrame：`gpd.GeoDataFrame(geometry=risk_zone)`。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| **GIS (Geographic Information System)** | 地理信息系统 | 用于捕获、存储、检查和显示与地球表面位置相关的数据的系统 |
| **Geospatial data** | 地理空间数据 | 带有地球表面位置信息的数据 |
| **Raster data** | 栅格数据 | 把地表表示成单元格矩阵，每格存一个属性值（如温度、高程） |
| **Vector data** | 矢量数据 | 用点、线、面等几何形状表示空间要素，位置精确、属性丰富 |
| **Point / LineString / Polygon** | 点 / 线串 / 多边形 | 三种基本矢量几何类型 |
| **MultiPolygon** | 多重多边形 | 由多个不相连多边形组成的单个要素（如含飞地的行政区） |
| **Resolution** | 分辨率 | 栅格数据每个单元格代表的地面尺寸；越小越精细 |
| **Adaptive mesh** | 自适应网格 | 在关注区域用高分辨率、其他区域用低分辨率的网格方案 |
| **Layer / Layering** | 图层 / 分层 | GIS 把不同类型数据叠成多层来揭示关系的核心思想 |
| **Shapefile (.shp)** | Shapefile 格式 | Esri 1990 年代发明的矢量格式，二进制、不可读但高效，实为一组文件 |
| **GeoJSON (.geojson)** | GeoJSON 格式 | 基于 JSON 的矢量格式，人类可读，结构为 FeatureCollection → Feature → geometry + properties |
| **GeoTIFF (.tif)** | GeoTIFF 格式 | 带地理坐标信息的栅格图像格式 |
| **DEM (Digital Elevation Model)** | 数字高程模型 | 存储地表高程的栅格数据集 |
| **KML / KMZ** | KML/KMZ 格式 | Google Earth 使用的矢量格式 |
| **Interchangeable format** | 可交换格式 | 社群约定的、便于不同来源数据组合的标准数据格式 |
| **Metadata** | 元数据 | 描述数据本身的数据（何时采集、如何采集、单位等）；真实数据中常缺失 |
| **Attribute data** | 属性数据 | GeoDataFrame 中除 geometry 外的所有描述性列 |
| **GeoPandas** | GeoPandas | pandas 的地理空间扩展，核心结构是 GeoDataFrame |
| **GeoDataFrame** | 地理数据框 | 带 `geometry` 列的 DataFrame，能存形状并做空间运算 |
| **GeoSeries** | 地理序列 | 只含几何体的 Series（如 `.buffer()` 的返回值） |
| **geometry column** | 几何列 | GeoDataFrame 中存放形状的特殊列 |
| **shapely** | shapely | GeoPandas 底层负责所有几何运算的库 |
| **fiona** | fiona | GeoPandas 底层负责地理文件读写的库 |
| **pyproj / PROJ** | pyproj / PROJ | 负责坐标系定义与转换的底层库 |
| **contextily (cx)** | contextily | 从网络拉取瓦片地图、给 matplotlib 图加底图的库 |
| **Basemap** | 底图 | 铺在数据图层下面的背景地图（如 OpenStreetMap） |
| **Tile map** | 瓦片地图 | 把地图切成小方块按需下载的网络地图机制 |
| **Zoom level** | 缩放层级 | 瓦片地图的细节等级；数字越大越精细、下载越慢 |
| **CRS (Coordinate Reference System)** | 坐标参考系 | 定义投影地图上的二维坐标如何对应地球上的真实位置 |
| **EPSG code** | EPSG 代码 | CRS 定义的标准化短标识符，由欧洲石油勘测组织维护 |
| **GCS (Geographic Coordinate System)** | 地理坐标系 | 用经纬度（度）定位，如 EPSG:4326 |
| **PCS (Projected Coordinate System)** | 投影坐标系 | 用平面直角坐标（通常是米）定位，如 EPSG:3857、27700 |
| **EPSG:4326 / WGS 84** | WGS 84 | 全球地理坐标系标准，GPS 使用，单位是度 |
| **EPSG:3857 / Web Mercator** | 伪墨卡托 | 网页地图（Google Maps、OSM）通用投影，单位是米；本周统一用它 |
| **EPSG:27700 / OSGB36 / British National Grid** | 英国国家格网 | 英国官方投影坐标系，单位米，基于 Airy 1830 椭球 |
| **Datum** | 大地基准面 | 定义椭球体相对于地球的位置与方向的参考框架 |
| **Ellipsoid** | 参考椭球 | 用来近似地球形状的数学曲面（如 Airy 1830、WGS 84） |
| **Easting / Northing** | 东距 / 北距 | 投影坐标系中的 X / Y 坐标，单位通常是米 |
| **Transverse Mercator** | 横轴墨卡托投影 | OSGB36 使用的投影方法 |
| **Prime Meridian** | 本初子午线 | 经度起算线，通常是格林尼治 |
| **`.crs`** | CRS 属性 | 查询 GeoDataFrame 当前坐标参考系（属性，无括号） |
| **`.to_crs()`** | 坐标系转换 | 把 GeoDataFrame 转到目标 CRS，**返回新对象** |
| **Spatial join (`sjoin`)** | 空间连接 | 按几何相交关系合并两个 GeoDataFrame，只保留左表几何 |
| **Clip (`.clip()`)** | 裁剪 | 用一组几何体当"饼干模具"，只保留落在其中的数据 |
| **Buffer (`.buffer()`)** | 缓冲区 | 在几何体周围生成指定距离的新几何体；单位随 CRS |
| **Centroid (`.centroid`)** | 质心 | 几何体的中心点；常用来把多边形简化成点 |
| **`.distance()`** | 距离 | 计算几何体之间的最短距离；点在多边形内时为 0 |
| **`.boundary`** | 边界 | 把多边形转成它的轮廓线，用于只画边界不填色 |
| **`.geom_type`** | 几何类型 | 返回每行几何体类型的字符串（'Polygon'、'Point'…） |
| **`.str.contains()`** | 字符串包含 | 检查字符串列的每个元素是否包含指定子串，返回布尔 Series |
| **`.value_counts()`** | 值计数 | 统计某列各取值出现次数，降序排列 |
| **`.iterrows()`** | 逐行迭代 | 返回 (index, row) 元组的迭代器 |
| **`.apply()`** | 逐元素应用 | 对 Series 每个元素施加一个函数 |
| **`lambda`** | 匿名函数 | 一行定义的无名函数，高效但可读性差 |
| **`SettingWithCopyWarning`** | 副本赋值警告 | pandas 警告你可能在给一个视图/副本写值，修改可能不生效 |
| **Bedrock** | 基岩 | 覆盖层之下的固结岩石；本周主数据集 |
| **Colliery** | 煤矿（含地面设施） | 煤矿及其附属建筑与加工设施 |
| **Coal Measures** | 煤系地层 | 石炭纪含煤的泥岩-粉砂岩-砂岩-煤旋回沉积序列 |
| **Mudstone / Siltstone / Sandstone** | 泥岩 / 粉砂岩 / 砂岩 | 三种粒度递增的碎屑沉积岩 |
| **Ironstone / Ferricrete** | 铁石 / 铁质结壳 | 富铁的沉积岩 / 铁质胶结的表生硬壳 |
| **Chalk** | 白垩 | 白色细粒的生物成因石灰岩（英国南部/东部） |
| **Dolomite / Dolomitised Limestone** | 白云岩 / 白云岩化石灰岩 | 富含镁的碳酸盐岩 |
| **Mafic igneous rock / Dolerite / Tholeiitic basalt** | 镁铁质火成岩 / 辉绿岩 / 拉斑玄武岩 | 富镁铁的深色火成岩 |
| **Argillaceous rocks** | 泥质岩 | 以黏土矿物为主的细粒沉积岩 |
| **Intrusion** | 侵入体 | 侵入到围岩中的岩浆体 |
| **Subgroup / Group / Formation** | 亚群 / 群 / 组 | 岩石地层单位的等级（`RANK` 列的取值） |
| **Flood Zone 2** | 二级洪泛区 | 环境署定义的、年发生概率 0.1%（千年一遇）的洪水淹没范围 |
| **Fluvial flooding** | 河流洪水 | 河流漫溢造成的洪水 |
| **Pluvial flooding** | 地表水洪水 | 降雨造成地表径流积水的洪水 |
| **Tidal flooding** | 潮汐/海岸洪水 | 潮汐与风暴潮造成的沿海洪水 |
| **Storm surge** | 风暴潮 | 风暴引起的海平面异常升高 |
| **Substation** | 变电站 | 电网中变换电压、切换线路的节点设施，被淹会造成大面积停电 |
| **Environment Agency (EA)** | 英国环境署 | 发布洪水风险图等环境数据的政府机构 |
| **British Geological Survey (BGS)** | 英国地质调查局 | 发布本周基岩地质数据的机构 |
| **ONS (Office for National Statistics)** | 英国国家统计局 | 发布行政边界等官方地理数据的机构 |
| **Esri** | Esri 公司 | ArcGIS 与 Shapefile 格式的创造者 |
| **ArcGIS / QGIS** | ArcGIS / QGIS | 商业 / 开源的主流 GIS 软件平台 |
| **Google Earth Engine** | 谷歌地球引擎 | 云端行星尺度环境数据分析平台 |
| **Metropolitan District (B)** | 都市自治市镇 | 英格兰的一级地方行政区类型；(B) = Borough |
| **Greater Manchester Combined Authority** | 大曼彻斯特联合政府 | 由 10 个都市自治区组成的城市区域 |
