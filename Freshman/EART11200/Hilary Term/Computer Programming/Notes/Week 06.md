# Week 6 — Pandas 与数据探索（Pandas and Data Discovery）：地理空间数据初步

> 课程：EART11200 The Natural Scientist's Toolkit — Computer Programming（Hilary Term）
> 本周材料：Lecture 6（`Lecture6_25.pdf` + 04-Mar 课堂录音转写）、Practical 6（`Practical_6.ipynb`）
> 数据集：Smithsonian Global Volcanism Program 全球火山喷发数据库（`GVP_Eruption_Results.csv`）

---

## 一、本周主题

本周是整门课的一个**分水岭**。前 5 周我们都在写「自己造数据」的代码：手工建 list、用 `np.random` 生成数组、写函数、用微分方程解算器跑数值模型（Conway's Game of Life、Predator-Prey 等）。从本周开始，课程转向**用别人已经采集好的真实数据**——把外部文件读进 Python，检查它、筛选它、可视化它。

老师在 transcript 里把这条主线说得很清楚：

> "What we're going to do this week is turn very much onto an area of work which I think will benefit most of you and we're going to look at working with data... previously collected, previously generated data. Loading into a Python environment and then doing stuff with that data."

### 本周三条主线

1. **pandas 模块**：Python 处理表格型数据的标准工具。老师给的最精炼定位是——
   > "pandas is the data equivalent module to numpy for arrays"
   （numpy 之于数组 = pandas 之于数据表）
   核心对象叫 **DataFrame（数据框）**，长得像 Excel 表格，但功能远比 Excel 强。
2. **条件筛选（subsetting）**：把前几周学的逻辑判断（`>`、`<`、`==`、`&`）搬进 DataFrame 的方括号里，一行代码就能取出「2019 年的喷发」「南北纬 40 度之间的喷发」这样的子集。
3. **地理空间可视化**：用 **Cartopy** 模块把从 DataFrame 里抽出来的经纬度画到世界地图上。

### 课程整体位置（老师给的课程地图）

| 周次 | 内容 | 阶段 |
|---|---|---|
| 1–2 | 'Vanilla' Python：data types, loops, basic operations, conditionals | 纯 Python |
| 3 | The Numpy module | 模块与函数 |
| 4 | Conway's Game of Life | 模块与函数 |
| 5 | Differential Equations（数值模型） | 模块与函数 |
| **6** | **Pandas and data discovery** ← **本周** | **数据科学** |
| 7 | Geospatial analysis（GeoPandas、GIS） | 数据科学 |
| 8 | Statistical Analysis | 数据科学 |
| 9 | Cluster Analysis（机器学习入门） | 数据科学 |
| 10–12 | Creating a notebook assessment（从 Week 4–9 里选一个题目做） | 评估 |

**关键提醒（考核相关）**：老师明确说 **Week 6–9 全部建立在 pandas 之上**（"all of the next four weeks are built on top of pandas"），而最终的 notebook assessment 要从 **Week 4–9** 里选一个主题。所以本周内容既是后面三周的地基，也直接是可选的考核题目之一。

### 为什么要学这个（老师的职业视角）

老师花了不少时间讲 **data science process**（引自 *Doing Data Science*, O'Reilly, 2013）：

```
Raw data collected → Data processing / cleaning → EDA（exploratory data analysis）
   → Models and algorithms → Communicate / visualise / make decisions → Data product
```

- 老师强调：所有人都盯着最后的 "models and algorithms"（深度学习、大模型），**但真正稀缺的岗位在前面那几步**——数据清洗、EDA、可视化沟通。"There are so many people doing that. Where's the niche? The niche tends to be in all these elements here."
- **EDA（exploratory data analysis，探索性数据分析）** 是本周正式引入的术语：在做任何事情之前先理解数据——数据里有没有错？可不可信？要不要再去采集？统计特征是什么？
- "Garbage in, garbage out"：把机器学习模型拟合到垃圾数据上，只会得到垃圾结果。
- 老师还提了数据的 **IP（知识产权）/ 法律**问题：现在很多官司源于「模型拟合在了本不该拿到的数据上」，大学正在为此紧张，因为这些成果可能进入政策后被法律挑战。

（另外老师顺带介绍了 **Gartner Hype Cycle（技术炒作周期）**：idea → peak of inflated expectations（期望膨胀顶峰）→ trough of disillusionment（幻灭低谷）→ slope of enlightenment → plateau of productivity。他说 generative AI 2023 年在顶峰，去年夏天的图上已经在往「幻灭低谷」走，而这其实是**好事**——意味着技术开始进入可信赖阶段；相比之下 Week 9 要用的 machine learning stacks 已经非常成熟，几十万篇论文用过。"AI augmented software engineering"（"帮我写代码"）目前还在期望顶峰。）

---

## 二、核心概念

### 2.1 为什么不用「原生 Python」读数据？

Python 本身当然能做 IO（input/output，输入输出）。但 pandas 官网的一句话说明了理由：

> "pandas...provides high-performance, easy-to-use data structures and data analysis tools."

两个关键词：
- **easy-to-use / human-readable**：读进来的数据能以人类可读的表格形式呈现，方便你**在做分析之前先看懂它**。
- **high-performance**：文件一旦很大（几十万、上百万行），性能就是决定性的。

### 2.2 文件格式：地球科学里的数据长什么样

老师用了相当篇幅讲文件格式，因为**不同学科各有偏好格式**，pandas 的价值就在于它是个「全能选手」（all-rounder）。

| 格式 | 典型使用场景 | 人类可读？ | 说明 |
|---|---|---|---|
| **CSV**（comma separated values，逗号分隔值） | 通用、Excel 导出 | ✅ | 本周用的就是它，最常见的入门格式 |
| **Excel (.xls/.xlsx)** | 办公、实验记录 | ✅（需软件） | `pd.read_excel` |
| **JSON** | IoT（Internet of Things，物联网）传感器网络 | ✅ | 老师说整栋楼、室外都布着传感器，数据以 JSON 回传服务器 |
| **NetCDF** | 气候模型、大气/海洋数据 | ✅（部分） | 有 dimensions、variables、attributes 三部分；常见于多维立方体数据 |
| **Parquet** | 大数据行业 | ❌（完全乱码） | 极高效、读写快、省存储和能耗，但必须用工具读 |
| **Shapefile / vector** | GIS | ❌ | 下周 GeoPandas 的主角 |

**为什么格式由不了你**：老师强调，很多时候格式不是你「喜欢」才选的，而是 **data standards / regulations（数据标准与法规）** 规定的。做环境政策相关的数据采集，会有一整套标准要遵守——IoT 领域就规定用 JSON。

**pandas 的应对**：对每种格式都有一个 reader 函数（`pd.read_csv`、`pd.read_excel`、`pd.read_parquet`、`pd.read_json`、`pd.read_html`…），也有对应的 writer（`.to_csv` 等）。所以 pandas 能当**格式转换的枢纽**。

### 2.3 Metadata（元数据）：data about the data

老师看 JSON 文件时提出的关键概念。一条 JSON 记录里，你可能只关心 `id` 和 `name` 两个字段，但文件里还塞了一大堆别的信息——那就是 **metadata（元数据）**，即「关于数据的数据」：

- 数据从哪来？谁采集的？谁拥有它？
- 什么时候采集的？用了什么仪器？当时的条件如何？

这些构成数据的 **provenance（溯源/来历）**。在 AI 时代这极其重要（回到上面的 IP 问题）。

**pandas 的价值**：如果 JSON 文件里有 200,000 条这样的记录，你不可能手动一条条翻出来。pandas 会替你解析。

### 2.4 NumPy array vs. pandas DataFrame

这是理解本周的关键对比：

| | NumPy array | pandas DataFrame |
|---|---|---|
| 结构 | 纯数值矩阵，1D/2D/3D/4D | 二维表格，行 + 列 |
| 数据类型 | **同质**（homogeneous，整表同一类型） | **异质**（heterogeneous，每列可以是不同类型：数字、文字、日期混装） |
| 索引方式 | 位置整数索引 `arr[0, 3]` | **带标签的轴**（labeled axes）：用列名 `data['Latitude']` |
| 大小 | 创建后形状固定 | **size-mutable**（可增删行列） |
| 内置能力 | 数学运算 | 统计、绘图、分组、条件筛选、缺失值处理… |

Practical 引用的正式定义：

> "[A] Pandas DataFrame is two-dimensional **size-mutable**, potentially **heterogeneous** tabular data structure with **labeled axes** (rows and columns)... Pandas DataFrame consists of three principal components: **the data, rows, and columns**."

**两者是可以互转的**，这是本周最重要的操作模式：

```
CSV 文件 --pd.read_csv--> DataFrame --条件筛选--> 子集 DataFrame
        --['列名'].values--> NumPy array --> 传给 Cartopy/matplotlib 画图
```

老师在 transcript 里说得非常直白：
> "This function here, name of a column dot values, **extracts a numpy array**. So this is why the two were interchangeable."

**为什么必须转成 NumPy array**？因为绘图模块（matplotlib / Cartopy）期望接收的是 NumPy array。

### 2.5 关于 index（索引）

老师提到：DataFrame 有 index（最左边那一列 0,1,2,3…）。

> "For this week and next week we won't be concerned about the index. But when we get to statistics, we can turn the index into a **timestamp** so that we can tell pandas 'just give me the values at 9 a.m.' from a million observations — that saves you hours and hours of development."

也就是说 **Week 8 统计那周会把 index 变成时间戳**，从而实现按时间切片。本周先不管。

### 2.6 典型工作流（老师概括的 "typical workflow"）

> "Load data into a data frame, maybe manipulate that, and then pass that data out into another workflow. That might include a numerical model."

举例：如果你有一个记录 predator-prey 各种参数的数据库（可能几百上千列），可以先用 pandas 读进来、清洗筛选，再把处理好的数据喂给上周学的数值模型。

### 2.7 本周的科学背景：全球火山喷发数据库

数据来自 **Smithsonian Global Volcanism Program**（https://volcano.si.edu），文件 `GVP_Eruption_Results.csv`。

- **规模**：9891 行 × 24 列（9891 次有记录的喷发事件）。
- **时间跨度**：最早 **-10450 年**（即公元前 10450 年），最晚 **2019 年**。
- **主要列**：
  - `Volcano Number`（火山编号，Smithsonian 内部 ID）、`Volcano Name`（火山名）
  - `Eruption Number`（喷发事件编号）、`Eruption Category`（如 "Confirmed Eruption" 确认喷发）
  - `Area of Activity`（活动区域）
  - **`VEI`**（Volcanic Explosivity Index，火山爆发指数，0–8 对数尺度，衡量喷发规模）、`VEI Modifier`
  - `Start Year` / `Start Year Modifier` / `Start Year Uncertainty`、`Start Month`、`Start Day` 等
  - **`Evidence Method (dating)`**（定年证据方法，例如 "Historical Observations" 历史观测记录；更古老的喷发要靠放射性碳测年、冰芯等）
  - `End Year` / `End Month` / `End Day` 及各自的 Modifier、Uncertainty
  - **`Latitude`**（纬度，−90 到 +90，正为北纬）、**`Longitude`**（经度，−180 到 +180，正为东经）
- **NaN 的含义**：表格里大量 `NaN`（Not a Number）表示**缺失值**。比如很多行 `VEI` 是 NaN——因为古老喷发无法估算爆发指数；`Start Year Uncertainty` 是 NaN 表示没标注不确定度。

**科学解读**：把全部喷发点画到世界地图上，会立刻看到它们**沿板块边界（plate boundaries）呈带状分布**——环太平洋火山带（Ring of Fire）、中洋脊、地中海—喜马拉雅带。老师原话："It makes sense because they follow plate boundaries."

**数据质量的批判性思考**（老师反复强调）：越往古代走，记录的**采集方式与可靠性越差**。历史记录只覆盖有人类文明观测的地区，所以数据库天然存在 **sampling bias（采样偏差）**——欧洲、日本这类有长期文字记录的地区，喷发记录密度远高于实际差异。这正是 Week 8 统计那周要处理的 "is the data skewed? is there a bias? are we missing values?" 问题。

---

## 三、语法速查与函数表

### 3.1 导入与读取

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `import pandas as pd` | 导入 pandas 并起别名 `pd` | `import pandas as pd` | `pd` 是社区约定俗成的别名（就像 numpy 用 `np`）。别名可以随便起，但**强烈建议跟大家一致**，否则别人读不懂你的代码 |
| `import os` / `from os import path` | 导入操作系统路径工具 | `import os` | 用来拼文件路径，避免写死绝对路径 |
| `os.getcwd()` | get current working directory，返回当前工作目录的字符串 | `path = os.getcwd()` | 返回的是 notebook 所在目录。**注意**：这里把变量也叫 `path`，会**遮蔽（shadow）**前面 `from os import path` 导入的 `path` 模块——能跑但是坏习惯 |
| `pd.read_csv(filepath)` | 读 CSV 文件，返回一个 DataFrame | `data = pd.read_csv(path+"/data/GVP_Eruption_Results.csv")` | 常用可选参数：`sep=`（分隔符，默认 `,`）、`header=`（哪一行是列名）、`names=`（自定义列名）、`skiprows=`（跳过前几行）、`na_values=`（哪些字符串算缺失值）。**最常见的报错是路径写错** → `FileNotFoundError` |

### 3.2 DataFrame 的属性（properties，注意**不加括号**）

| 名称 | 作用 | 用法示例 | 返回值 / 注意事项 |
|---|---|---|---|
| `.size` | 元素总数 = 行数 × 列数 | `data.size` → `237384` | 返回 int。9891 × 24 = 237384 ✅ |
| `.shape` | 形状，(行数, 列数) | `data.shape` → `(9891, 24)` | 返回 **tuple**。单列 Series 返回 `(9891,)`（注意尾部逗号，一维元组的写法） |
| `.ndim` | number of dimensions，维数 | `data.ndim` → `2` | DataFrame 恒为 2；单列（Series）为 1 |

**⚠️ 属性 vs 方法**：`.size`、`.shape`、`.ndim` 是**属性**，写 `data.size`，**不加括号**。写成 `data.size()` 会报 `TypeError: 'int' object is not callable`。而 `.head()`、`.value_counts()`、`.hist()` 是**方法**，**必须加括号**。

### 3.3 DataFrame 的方法（methods，**必须加括号**）

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `.head(n)` | 预览前 n 行（默认 5 行） | `data.head()` / `data.head(10)` | **加载数据后的第一件事永远是 `.head()`**，确认你读进来的是对的文件 |
| `.tail(n)` | 预览后 n 行 | `data.tail()` | 同上 |
| `.value_counts()` | 统计某列各个不同取值出现的次数，**按次数降序排列** | `data['Volcano Name'].value_counts()` | 只能用于 **Series（单列）**，不能直接用在整个 DataFrame 上。对 categorical data（分类数据）特别有用。返回一个 Series，index 是取值、值是计数 |
| `.idxmax()` | index of maximum，返回**最大值所对应的索引标签** | `data['Volcano Name'].value_counts().idxmax()` → `'Etna'` | 注意它返回的是**标签**不是数值。对比 `.max()` 返回的是**数值**（这里会是 196） |
| `.hist(column=...)` | 对指定列画直方图 | `data.hist(column='Start Year')` | 这是 **DataFrame 自带的绘图能力**（底层调 matplotlib）。可选 `bins=` 控制柱子数量。返回一个 `numpy.ndarray` of `Axes` 对象 |
| `.values` | 把列的数据取出为 **NumPy array** | `data['Latitude'].values` | ⚠️ 是**属性不是方法**，不要写 `.values()`（Practical 文字里误写成 `.values()`，代码里是对的）。较新的 pandas 推荐用 `.to_numpy()`，但本课程用 `.values` |

### 3.4 选列与条件筛选（本周的核心语法）

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `df['列名']` | 选出一列，返回 **Series**（一维） | `data['Latitude']` | 列名是字符串，**必须加引号**，且**大小写、空格完全匹配**（`'Start Year'` 中间有空格！）。写错 → `KeyError` |
| `df[布尔条件]` | 按行筛选，返回**新的 DataFrame** | `data[data['Start Year'] == 2019]` | 方括号里放的是一个**布尔 Series**（每行 True/False），pandas 只保留 True 的行。这叫 **boolean masking（布尔掩码）** |
| `df[cond1 & cond2]` | 两个条件**同时**满足（AND） | `data[(data['Latitude'] > -40) & (data['Latitude'] < 40)]` | ⚠️ **每个条件必须用小括号包起来**！否则运算符优先级出错 → `TypeError`。用 `&` 不是 `and` |
| `df[cond1 \| cond2]` | 满足**任一**条件（OR） | `data[(data['VEI'] > 5) \| (data['Start Year'] > 2000)]` | 用 `\|` 不是 `or` |
| 链式操作 | 先筛行、再取列、再取值 | `data[data['Start Year'] == 2019]['Latitude'].values` | 从左往右逐步理解：先得到 2019 年的子 DataFrame → 再取它的 Latitude 列 → 再变成 NumPy array |

**⚠️ `&` vs `and` 是本周头号语法陷阱**，见第六节。

### 3.5 Python 比较运算符对照表（Practical 原表）

| 含义 | 数学符号 | Python 符号 |
|---|---|---|
| Less than 小于 | < | `<` |
| Greater than 大于 | > | `>` |
| Less than or equal 小于等于 | ≤ | `<=` |
| Greater than or equal 大于等于 | ≥ | `>=` |
| Equals 等于 | = | `==` |
| Not equal 不等于 | ≠ | `!=` |

**记牢**：判断相等是 **两个等号 `==`**；一个 `=` 是赋值。

### 3.6 NumPy 函数（本周复用）

| 名称 | 作用 | 用法示例 | 返回值 |
|---|---|---|---|
| `np.min(arr)` | 数组最小值 | `np.min(Years)` → `-10450` | 标量 |
| `np.max(arr)` | 数组最大值 | `np.max(Years)` → `2019` | 标量 |

也可以写成方法形式 `Years.min()` / `Years.max()`，等价。

### 3.7 Cartopy + matplotlib 绘图模板

> 老师和 Practical 都反复说：**这部分模板照抄即可，不需要背语法**。
> "As with all the other figures that we've done in the notebooks, don't worry about the syntax. We provide the template for plotting."

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `import cartopy.crs as ccrs` | 导入 Cartopy 的 coordinate reference system（坐标参考系统）子模块 | — | `crs` = coordinate reference system |
| `import matplotlib.pyplot as plt` | 导入绘图库 | — | 约定别名 `plt` |
| `plt.figure(figsize=(w, h))` | 创建画布，指定尺寸（英寸） | `plt.figure(figsize=(8,8))` | 改这两个数字就能放大缩小图。老师演示：8×8 → 16×16 直接翻倍 |
| `plt.axes(projection=ccrs.PlateCarree())` | 创建带地图投影的坐标轴 | `ax = plt.axes(projection=ccrs.PlateCarree())` | **PlateCarree（等距圆柱投影 / 平板投影）**：最简单的投影，经度直接当 x、纬度直接当 y。高纬度会严重变形 |
| `ax.stock_img()` | 铺一张自带的地球底图（蓝色大理石风格） | `ax.stock_img()` | 这是 Cartopy 内置的低分辨率地球图像，不联网也能用 |
| `plt.scatter(x, y, ...)` | 画散点 | 见下 | **注意参数顺序是 (Longitude, Latitude)**，即 (x, y)，不是 (纬度, 经度)！ |
| `transform=ccrs.PlateCarree()` | 告诉 Cartopy「我给的坐标是经纬度」 | scatter 的关键字参数 | **必须写**，否则 Cartopy 会把数字当成投影后的米数，点全画错位置 |
| `plt.show()` | 显示图像 | `plt.show()` | — |

**scatter 的常用外观参数**：

| 参数 | 含义 | 示例 |
|---|---|---|
| `color=` | 点的颜色 | `'red'`, `'green'`, `'blue'` |
| `s=` | size，点的**面积**（不是半径/直径） | `s=9` → `s=18` 就是「面积翻倍」 |
| `marker=` | 点的形状 | `'o'` 圆点 |
| `linewidth=` | 描边宽度 | `2` |

**marker 形状对照表**（Practical 给的子集，完整表见 matplotlib 官网）：

| character | description |
|---|---|
| `'.'` | point marker（小点） |
| `','` | pixel marker（像素点） |
| `'o'` | circle marker（圆圈） |
| `'v'` | triangle_down marker（下三角） |
| `'^'` | triangle_up marker（上三角） |
| `'<'` | triangle_left marker（左三角） |
| `'>'` | triangle_right marker（右三角） |

### 3.8 本周产出的图表及判读要点

| 图 | 生成方式 | 判读要点 |
|---|---|---|
| **全球空白底图** | `plt.axes(projection=...)` + `ax.stock_img()` | 确认底图出现、投影正确（世界地图铺满矩形） |
| **全部喷发位置散点图** | 上面 + `plt.scatter(Longitude, Latitude, transform=...)` | ✅ 正确的标志：点**沿板块边界成带状**（环太平洋、中洋脊、地中海带），而不是均匀撒满全球或全挤在一角。如果点全在一条直线上或全在 (0,0) 附近，说明经纬度传反了或者 `transform` 忘了写 |
| **2019 年喷发位置图** | 先 `data[data['Start Year']==2019]` 再取坐标 | 点数应该**大幅减少**（一年全球只有几十次确认喷发），且仍在板块边界上 |
| **南北纬 40° 之间的喷发图** | `data[(data['Latitude']>-40)&(data['Latitude']<40)]` | ✅ 正确的标志：**地图上下两条空白带**——高纬度（阿拉斯加、堪察加、冰岛、南极）的点全部消失。如果高纬度还有点，说明条件写错了 |
| **Etna 喷发年份直方图（全部）** | `data[data['Volcano Name']=='Etna'].hist(column='Start Year')` | x 轴跨度极大（从公元前几千年到 2019），导致近几百年的细节全挤在最右边一根柱子里——**分辨率不足** |
| **Etna 1200 年至今直方图** | 加上 `data['Start Year'] >= 1200` 条件 | x 轴压缩到 1200–2019，能看出**近几百年记录数明显上升**——这更多反映**观测记录的完善**而非火山活动真的变频繁（观测偏差！） |

---

## 四、课堂补充

这一节汇总只在 transcript 里出现、slides 上没有的老师口头内容。

### 4.1 pandas 的定位：「numpy 之于数组 = pandas 之于数据」

> "We're going to use something called pandas. pandas is the data equivalent module to numpy for arrays. So everything you do with data in Python typically will require us to have these pandas data frames."

这句话是理解本周最好的锚点。前几周对 numpy array 做的一切（索引、切片、逻辑判断、找最大最小），本周都要在 DataFrame 上重做一遍，只是语法更方便。

老师还补了一句关键的：
> "You'll find that pandas does a lot of the **grunt work** for us."
（grunt work = 又脏又累的杂活）

### 4.2 环境差异：Anaconda vs. 集群 vs. Colab

> "You've been playing with the distribution on the cluster so far, the Anaconda distribution... Typically when you download Anaconda on your own laptop, it will normally have pandas with it. It's considered one of the **fundamental modules**."

**踩坑点**：pandas 是 Anaconda 自带的，但 **Cartopy 不是**。所以 Practical 的第一个 code block 专门处理 Google Colab 上装 Cartopy 的问题（见 5.0）。

### 4.3 为什么一定要先 `.head()` 和看 shape

老师在这里给了一个非常实用的调试思路：

> "At this point on you really want to make sure that you're trusting the data you're working with moving forward. **If you don't preview the data and then you start getting a load of errors when you're doing numerical operations, it might be just you're loading the wrong thing.**"

Practical 的注释也说了同一件事：
> "This is also a good way of ensuring you have loaded in the data you expect. Sound silly? **If you work with lots of datafiles it can be easy to assume you are working on the correct one.**"

**这是本周最重要的调试习惯**：报错未必是你代码逻辑写错了，很可能是数据根本不是你以为的那个。

### 4.4 为什么要用 `.value_counts()` 而不是自己数

> "What I don't want to do is have to count manually all the individual names and then tally those up row after row after row... And this command alone will give us that list, so we can see that our database is **dominated by Mount Etna**."

老师用这个例子说明：EDA 的第一步往往就是「这一列有哪些不同的值，各出现多少次」，一行代码解决。

### 4.5 为什么要找最早/最晚年份

> "Imagine I wanted to find the minimum, so the earliest date in our record. **I can't guarantee that the entries in my data frame are done by order.** So someone has gone from the most recent down to the earliest."

**关键点**：DataFrame 的行顺序是文件里的原始顺序，**不保证有序**。所以要找最值必须用 `np.min` / `np.max`，不能想当然地看第一行或最后一行。

（顺便：观察本周的 `.head()` 输出——前 5 行都是 2019 年，说明这个文件确实是按时间**倒序**排的，但你**不该依赖**这一点。）

### 4.6 条件筛选「创建了一个新的 DataFrame」

> "So this now is basically creating a **new data frame**, this on the left-hand side before the dot."

理解 `data[data['Start Year'] == 2019].head()` 的方式：
1. `data['Start Year'] == 2019` 生成一个**布尔 Series**（9891 个 True/False）
2. `data[...]` 用它筛出行，**生成一个全新的 DataFrame**
3. `.head()` 作用在这个**新** DataFrame 上

老师说这个模式后面会反复用：
> "We'll use that over and over again over the next few weeks. Next week we'll cut out data from a certain **political boundary** on a map, and the week after we'll pull out data from a certain **monitoring station** in a different country."

### 4.7 条件链式组合的实战建议

> "I can chain things together. Now this starts to look a bit complicated quite quickly, but it's getting used to the syntax."

老师承认 `data[(data['Latitude'] > -40) & (data['Latitude'] < 40)]['Longitude'].values` 这种写法**一眼看上去很吓人**，建议的读法是：

> "Just focus on the right-hand side here... If we weren't interested in this specific subset, I'd just use `data['Latitude'].values`. But here in these brackets I'm also saying only when the information in the latitude column is greater than −40 **and** the information in that same column is less than 40."

即：**先看外层框架 `data[...]['列'].values`，再看方括号里塞了什么条件**。

老师还强调，条件可以无限接下去：
> "I could chain that together with an 'and' data start year is 2019 if I wanted to. **You can make it as long as you need it to be.**"

**为什么不该自己用 numpy 循环做这件事**：
> "That's saving a lot of effort on our part, because we're not extracting the data out into a numpy data frame, searching for latitude longitude values, creating another numpy frame. **It would get messy quite quickly. You'd probably create some errors.**"

### 4.8 关于「结果对不对」的判断

老师有一句很值得记的话（针对条件筛选）：

> "Typically if that wasn't working you'd get an **error**; it wouldn't give you the **wrong answer**."

意思是：条件筛选写错通常是直接报错（`KeyError`、`TypeError`），而不是静默给你错的结果。所以能跑通就基本可信。但——**这只针对语法层面**。如果你把 `>` 写成 `<`，代码照跑不误，答案是错的。所以还是要**看图判断合理性**（见 3.8 的判读要点）。

### 4.9 关于地理空间工具生态（超纲但有用）

- **Google Earth Engine**：老师问有没有人用过。基于 JavaScript，有 Google 账号就能用，能访问海量卫星遥感数据产品。Python 接口叫 **geemap**（老师口述转写成 "GEE maps"）。优势是**数据在云端**，不用下载到本地硬盘（否则根本没法处理）。老师说如果有人想在 practical 上看 demo，可以找他要代码。
- **Cartopy**（本周用）："quite old, still in use, still quite popular"。它本质是**给 matplotlib 提供一块认识地理坐标的画布**：
  > "Cartopy really is like a **map canvas that matplotlib recognizes**."
- **GeoPandas**（下周用）："a step up from that"，底层还是 pandas，但能处理**复杂的几何形状**（多边形、国界线等），而 Cartopy 主要是画点。
  > "It will look exactly the same, but GeoPandas can deal with much more complex shapes."
- 下周还会讲 **map projections（地图投影）** 的原理，以及把地图样式换成 OS maps（英国地形测量局地图）、Google Maps 风格。

### 4.10 未来几周的连接

| 周次 | 与本周的关系 |
|---|---|
| Week 7 | GeoPandas + vector/shape files；按**政治边界**裁数据；地图投影 |
| Week 8 | 统计分析；把 index 变成 **timestamp**；用另一个统计绘图模块看数据是否 **skewed（有偏）**、有无 bias、有无缺失值、有无不合理值 |
| Week 9 | 机器学习（"ML stacks"，多层代码堆叠），建立在前三周的 EDA 之上 |

老师原话：
> "That's why the next three weeks really build up that **EDA approach** to data before we fit a machine learning model."

### 4.11 老师留下的开放问题

看到最早喷发是 **−10450** 年时，Practical 直接问：

> "Does this make sense? Do we have an error in our database?"

**思考**：−10450 表示公元前 10450 年，处于**全新世（Holocene）初期**。Smithsonian 数据库正式名称就是 "Holocene Volcano List"，覆盖范围就是过去约 12000 年，所以 **−10450 是合理的，不是错误**。这种年代的记录来自地质证据（放射性碳测年、冰芯层、火山灰层），而非历史观测——这正是 `Evidence Method (dating)` 那一列存在的意义。

但反过来说，**负数年份在做数值运算时容易出问题**（比如画对数轴、算年份差），这是需要留意的。

---

## 五、Practical 要点

**Notebook**：`Practical_6.ipynb` — "Pandas data discovery - Geospatial analysis"

**总体目标**：用 pandas 加载真实火山喷发数据，做 EDA，并把结果画到地图上。

**Notebook 的提示约定**：
> "After reading the instructions and aims of any exercise, search the code snippets for a note that reads `-------'INSERT CODE HERE'-------` to identify where you need to write your code"

即：写代码的地方都用 `# <<-------------------- INSERT CODE HERE ----------------------->>` 标出来。

**练习清单**：
1. Exercise 1 — Plot eruption locations（改绘图外观）
2. Exercise 2 — Quantify the number of unique eruption locations（数唯一火山数）
3. Exercise 3 — Plot the location of eruptions in 2019（单条件筛选 + 绘图）
4. Exercise 4 — Plot eruptions between 40°N and 40°S（双条件筛选 + 绘图）
5. Exercise 5 — Histogram of eruptions at Mount Etna since 1200（双条件 + 直方图）

---

### 5.0 前置：Google Colab 环境准备（不是练习，但必须理解）

**题目要求**：运行第一个 code block。如果在 Colab 上，它会自动安装 Cartopy；如果不在，会打印提示信息。

**为什么需要**：Cartopy 不是 Colab 默认自带的模块，而且它依赖底层的 C 库（PROJ、GEOS），不能简单 `pip install` 了事。

```python
# 检查当前是否运行在 Google Colab 环境中
# get_ipython() 返回当前 IPython/Jupyter 内核对象；把它转成字符串后，
# 如果里面包含 'google.colab'，说明我们在 Colab 上
if 'google.colab' in str(get_ipython()):
    print('Running on CoLab')
    # ！开头的行是 shell 命令（不是 Python），Jupyter 允许这样直接调用系统命令
    !apt-get install libproj-dev proj-bin proj-data   # 安装 PROJ 库：负责地图投影的坐标换算
    !apt-get install libgeos-dev                      # 安装 GEOS 库：负责几何运算（点、线、面）
    # shapely 必须重装，让它和 cartopy 用同一份 geos 安装
    # （这是一个已知的兼容性 bug，见 cartopy issue #871）
    !pip uninstall -y shapely                         # -y 表示自动确认，不要交互式提问
    !pip install --no-binary shapely shapely          # --no-binary 强制从源码编译，而不是下载预编译包
    !pip install cartopy                              # 最后才装 cartopy
else:
     print('Not running on CoLab')                    # 不在 Colab 上，什么也不做

# 第二段：如果在 Colab 上，需要挂载 Google Drive 才能读到数据文件
if 'google.colab' in str(get_ipython()):
    from google.colab import drive          # 导入 Colab 专用的 drive 模块
    mount='/content/gdrive'                 # 指定挂载点（Drive 会出现在这个路径下）
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)                      # 执行挂载（会弹出授权流程）
    # 拼出课程仓库在 Drive 里的完整路径
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root                         # %cd 是 Jupyter 的 magic command，切换工作目录
                                            # $drive_root 表示引用上面那个 Python 变量
else:
    print('Not running on CoLab')
```

**输出**：
```
Not running on CoLab
```

**输出解读**：说明本次运行**不在 Colab 上**（在本地 Jupyter 或大学集群上），所以什么都没装、也没挂载 Drive。这是**正确的、预期的**结果。如果你在 Colab 上跑，会看到一大堆 `apt-get` / `pip` 的安装日志。

**新语法点**：
- `!command` — 在 Jupyter 里执行 shell 命令
- `%cd path` — Jupyter 的 **magic command**（魔术命令），`%` 开头是行魔术，`%%` 开头是单元格魔术
- `get_ipython()` — 获取当前 IPython 内核对象；**在纯 .py 脚本里调用会 `NameError`**，只能在 Jupyter 环境用

---

### 5.1 加载数据并预览

**题目要求**：把 CSV 读进 DataFrame 并预览。

**解题思路**：`import pandas as pd` → 用 `os.getcwd()` 拿到当前目录 → 拼出数据文件路径 → `pd.read_csv` → `.head()`。

```python
# 导入 pandas，起别名 pd（社区约定；注释里老师说"用 pd 只是因为好打"）
import pandas as pd
import os                  # 导入 os 模块，用来和操作系统打交道
from os import path        # 从 os 里单独导入 path 子模块

path = os.getcwd()         # 获取当前工作目录（current working directory），返回一个字符串
                           # 注意：这里的变量名 path 覆盖了上面导入的 path 模块（坏习惯，但能跑）

# 用字符串拼接组成完整路径，读入 CSV，结果赋给名为 data 的 DataFrame
data = pd.read_csv(path + "/data/GVP_Eruption_Results.csv")

data.head()                # 预览前 5 行；.head() 是 DataFrame 的方法，注意要加括号
```

**输出**（前 5 行，24 列，中间列被 `...` 省略）：

| | Volcano Number | Volcano Name | Eruption Number | Eruption Category | Area of Activity | VEI | ... | Evidence Method (dating) | End Year | End Month | End Day | Latitude | Longitude |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 0 | 252120 | Ulawun | 22319 | Confirmed Eruption | NaN | NaN | ... | Historical Observations | 2019.0 | 6.0 | 27.0 | −5.050 | 151.330 |
| 1 | 354020 | Ubinas | 22324 | Confirmed Eruption | NaN | NaN | ... | Historical Observations | 2019.0 | 7.0 | 11.0 | −16.355 | −70.903 |
| 2 | 290250 | Raikoke | 22321 | Confirmed Eruption | NaN | NaN | ... | Historical Observations | 2019.0 | 7.0 | 1.0 | 48.292 | 153.250 |
| 3 | 233020 | Fournaise, Piton de la | 22318 | Confirmed Eruption | NaN | NaN | ... | Historical Observations | 2019.0 | 6.0 | 13.0 | −21.244 | 55.708 |
| 4 | 311120 | Great Sitkin | 22322 | Confirmed Eruption | NaN | NaN | ... | Historical Observations | 2019.0 | 6.0 | 7.0 | 52.076 | −176.130 |

`5 rows × 24 columns`

**输出解读**：
- ✅ **看到表格 = 文件路径正确、读取成功**。
- **最左边一列 0,1,2,3,4** 是 pandas 自动生成的 **index（索引）**，不是数据的一部分。
- **`NaN`** = 缺失值。`VEI`、`Area of Activity` 大量缺失是正常的（并非每次喷发都有爆发指数估算）。
- 前 5 行都是 2019 年、且 `Evidence Method` 都是 "Historical Observations"，说明文件按时间**倒序**排列（但不要依赖这一点）。
- 五座火山地理上分散得很开：Ulawun（巴布亚新几内亚）、Ubinas（秘鲁）、Raikoke（千岛群岛）、Piton de la Fournaise（留尼汪岛）、Great Sitkin（阿留申群岛）——都是典型的板块边界火山。
- **Longitude 有负数**（−70.903、−176.130）表示西经；**Latitude 有负数**（−5.050、−16.355）表示南纬。

**⚠️ 常见误用**：
- 路径分隔符：Windows 上手写 `"\data\..."` 里的 `\d` 会被当成转义字符。用 `/` 或 `os.path.join()` 更安全。
- 忘了 `.head()` 的括号 → 输出的是方法对象本身，看起来像 `<bound method NDFrame.head of ...>`。
- 文件不在 notebook 同级的 `data/` 目录下 → `FileNotFoundError: [Errno 2] No such file or directory`。

---

### 5.2 检查 DataFrame 的规模（size / shape / ndim）

**题目要求**：搞清楚数据框有多大。

**解题思路**：用三个属性分别看总元素数、形状、维数。

```python
# dataframe.size —— 元素总数，等于 行数 × 列数
size = data.size
print("Size of dataframe =", size)

# dataframe.shape —— 分开给出 (行数, 列数)
shape = data.shape
print("Shape of dataframe =", shape)

# dataframe.ndim —— 维数。是二维数组还是三维数组？
ndim = data.ndim
print("Number of dimensions =", ndim)
```

**输出**：
```
Size of dataframe = 237384
Shape of dataframe = (9891, 24)
Number of dimensions = 2
```

**输出解读**：
- **9891 行 = 9891 次喷发事件记录**；**24 列 = 每次喷发有 24 个字段**。
- **自检**：9891 × 24 = 237,384 ✅ 与 `.size` 完全对上，说明理解正确。
- `.shape` 返回的是 **tuple（元组）**，打印时带小括号。
- `ndim = 2` 是 DataFrame 的定义特征（"two-dimensional tabular data structure"）。

---

### 5.3 检查单列（Series）的规模

**题目要求**：把上面同样的操作用到某一列上。

**解题思路**：先用 `data["列名"]` 取出一列（得到 **Series**），再链上 `.ndim` / `.size` / `.shape`。老师称这是 "chain operations together"（把操作串起来）。

```python
# 注意：这里变量名叫 series 只是随便起的，关键是列名必须写对
series_ndim = data["Eruption Category"].ndim     # 单列的维数
print("Number of dimensions =", series_ndim)

series_size = data["Eruption Category"].size     # 单列的元素总数
print("Shape of dataframe =", series_size)       # ← 注意 notebook 里 print 的文字标签写反了

series_shape = data["Eruption Category"].shape   # 单列的形状
print("Size of dataframe =", series_shape)       # ← 这里的标签也写反了
```

**输出**：
```
Number of dimensions = 1
Shape of dataframe = 9891
Size of dataframe = (9891,)
```

**输出解读**：
- `ndim = 1` → 单列是**一维**的，这种一维带标签的对象在 pandas 里叫 **Series**。
- `size = 9891` → 元素个数，与 DataFrame 的**行数一致** ✅（每行在这列上都有一个值）。
- `shape = (9891,)` → 一维元组。**注意尾部那个逗号**：Python 里 `(9891)` 只是加了括号的整数，`(9891,)` 才是含一个元素的元组。

**⚠️ notebook 自身的小 bug**：上面 `print` 里 "Shape" 和 "Size" 两个标签**贴反了**（`.size` 的结果被标成 "Shape of dataframe"）。这是个很好的提醒——**输出的文字标签是人写的，不代表它正确**，要自己核对数值。

---

### 5.4 绘制空白世界地图（Cartopy 模板）

**题目要求**：熟悉绘图模板，学会调整图幅大小。

```python
import cartopy.crs as ccrs           # 导入 cartopy 的坐标参考系统模块，别名 ccrs
import matplotlib.pyplot as plt      # 导入绘图库，别名 plt

plt.figure(figsize=(8, 8))           # 创建一块 8×8 英寸的画布
ax = plt.axes(projection=ccrs.PlateCarree())   # 创建坐标轴，指定用 PlateCarree（等距圆柱）投影
                                     # 把返回的坐标轴对象存进变量 ax
ax.stock_img()                       # 在这个坐标轴上铺一张 cartopy 自带的地球底图
plt.show()                           # 把图显示出来
```

**输出**：一张矩形的世界地图（蓝色海洋 + 彩色陆地，类似 NASA Blue Marble 风格）。

**放大到两倍**（老师课上直接演示了这个改动）：

```python
import cartopy.crs as ccrs
import matplotlib.pyplot as plt

plt.figure(figsize=(16, 16))         # 只改这一行：8 → 16，图幅面积变成 4 倍、边长翻倍
ax = plt.axes(projection=ccrs.PlateCarree())
ax.stock_img()
plt.show()
```

**输出解读**：同一张地图，但显示得更大更清晰。老师的点是——**改一个参数就能快速调整给别人看的呈现效果**（"quite quickly you can start modifying what you're trying to produce for someone"）。

**关键理解**（Practical 原文）：
> "The great feature about this map is that **it isn't just an image**. It also acts as a **fully-functioning Matplotlib axes that accepts spherical coordinates** and allows us to easily plot data on it."

即：`ax` 不是一张图片，而是一块**能接受球面坐标的画布**，可以往上叠加数据。

---

### 5.5 从 DataFrame 提取经纬度到 NumPy 数组

**题目要求**：把 Latitude、Longitude 两列变成 NumPy 数组，好喂给绘图函数。

**解题思路**：`data['列名']` 取列 → `.values` 转成 NumPy array。两步链在一起。

```python
Latitude = data['Latitude'].values    # 取出 'Latitude' 列，再取它的 .values → 得到 NumPy array
Latitude                              # 在 Jupyter 里单独写变量名会打印它的预览
```

**输出**：
```
array([ -5.05 , -16.355,  48.292, ...,  38.654,  43.42 ,  -4.889])
```

```python
Longitude = data['Longitude'].values  # 对 Longitude 列做同样的事
Longitude
```

**输出**：
```
array([ 151.33 ,  -70.903,  153.25 , ...,   42.229, -113.5  ,   31.933])
```

**输出解读**：
- 开头的 `array([...])` 确认这是一个 **NumPy ndarray**，不再是 pandas Series ✅
- 中间的 `...` 是 NumPy 对长数组的**省略显示**（不是数据缺失）。
- 前 3 个值与 5.1 里 `.head()` 表格的前 3 行完全对得上（−5.05 / −16.355 / 48.292）✅ 这是很好的自检方式。
- 数值范围合理：纬度都在 −90 到 +90 之间，经度都在 −180 到 +180 之间 ✅

**⚠️ 关键误用**：`.values` 是**属性**，写 `.values()` 会报
```
TypeError: 'numpy.ndarray' object is not callable
```
（Practical 的说明文字里就误写成了 `.values()`，代码里是对的——**以代码为准**。）

---

### 5.6 把所有喷发点画到地图上（红色圆点）

**题目要求**：在世界地图上叠加全部 9891 个喷发位置的散点。

```python
import cartopy.crs as ccrs
import matplotlib.pyplot as plt

fig = plt.figure(figsize=(15,15))               # 创建 15×15 英寸画布，并把 figure 对象存进 fig

ax = plt.axes(projection=ccrs.PlateCarree())    # 建立带 PlateCarree 投影的坐标轴
ax.stock_img()                                  # 铺地球底图

Latitude = data['Latitude'].values              # 提取纬度 → NumPy array
Longitude = data['Longitude'].values            # 提取经度 → NumPy array

plt.scatter(Longitude, Latitude,                # 画散点：第一个参数是 x（经度），第二个是 y（纬度）
         color='red',                           # 点的颜色：红色
         linewidth=2,                           # 点的描边宽度
         s=9,                                   # 点的面积（size），单位是 points²
         marker='o',                            # 点的形状：圆圈
         transform=ccrs.PlateCarree(),          # 关键！告诉 cartopy "我给的是经纬度坐标"
                                                # 它据此把经纬度换算到当前投影的画布坐标
         )

plt.show()                                      # 显示
```

**输出**：世界地图上散布着近一万个红色小圆点。

**输出解读（怎么判断对不对）**：
- ✅ 点应该**明显沿板块边界成带状**：环太平洋火山带（Ring of Fire，从新西兰 → 印尼 → 日本 → 堪察加 → 阿留申 → 北美西岸 → 安第斯山）最密集；中大西洋洋脊、东非裂谷、地中海—土耳其—伊朗带也清晰可见。
- ✅ 大洋中部、大陆内部（西伯利亚中部、澳大利亚中部、撒哈拉大部、加拿大盾地）基本空白——这符合板块构造理论。
- ❌ 如果点均匀铺满全球 → 说明画的不是真实数据。
- ❌ 如果点全挤在地图左下角或一条对角线上 → 说明 `transform=` 忘了写，或者 Longitude/Latitude 顺序传反了。

老师的评价：
> "So there isn't that much code there. From loading that database into a data frame, extracting the coordinates, we can produce something that makes sense. **Producing maps is a really powerful way of communicating your data.**"

**⚠️ 最容易犯的错**：`plt.scatter(Latitude, Longitude, ...)` —— **参数顺序反了**。scatter 的签名是 `scatter(x, y)`，地图上 x 是经度、y 是纬度，所以必须是 `scatter(Longitude, Latitude)`。反了不会报错，但地图会完全变形（点被翻转 90°，且纬度值超出 ±90 会被裁掉）。

---

### 5.7 Exercise 1：Plot eruption locations（改成绿色、两倍大的圆点）

**题目要求**：
> "To get a feel for how we might change the appearance of a map based plot, repeat the above but with **green circles that are twice as big** as the previous version."

Practical 还建议：
> "I would recommend restarting all code snippets by clicking on `Kernel` in the toolbar and then `Restart and Run All`."
（**为什么建议重启内核**：notebook 里变量是跨 cell 共享的，反复改来改去容易留下上一次运行的残余变量，造成「明明改了代码结果没变」或「莫名其妙报错」。`Restart and Run All` 保证从干净状态从头跑一遍——这是 Jupyter 最重要的排错技巧之一。）

**解题思路**：只需要改 `plt.scatter` 的两个参数：
- `color='red'` → `color='green'`
- `s=9` → `s=18`（**"twice as big"**；`s` 参数控制的是**面积**，9 → 18 就是面积翻倍）

**完整代码**：

```python
import cartopy.crs as ccrs
import matplotlib.pyplot as plt

fig = plt.figure(figsize=(15,15))

ax = plt.axes(projection=ccrs.PlateCarree())
ax.stock_img()

Latitude = data['Latitude'].values      # 提取纬度（和上一格完全相同）
Longitude = data['Longitude'].values    # 提取经度

plt.scatter(Longitude, Latitude,
         color='green',                 # ← 改动 1：红色改绿色
         linewidth=2,
         s=18,                          # ← 改动 2：面积 9 → 18，翻倍
         marker='o',
         transform=ccrs.PlateCarree(),
         )

plt.show()
```

**输出**：与 5.6 完全相同的分布模式，但点是**绿色**且**更大更醒目**。

**输出解读**：分布模式**必须和上一张一模一样**——因为数据没变，只改了外观。如果模式变了，说明你不小心改到了数据提取的代码。

**知识点：`s` 参数到底是面积还是直径？**
matplotlib 官方文档说 `s` is "marker size in **points²**"，即**面积**。所以：
- 想让**面积**翻倍 → `s` 乘 2（9 → 18）✅ 本题答案
- 想让**直径**翻倍 → `s` 乘 4（9 → 36）

题目原文说 "twice as big"，标准答案用的是 `s=18`，即按面积理解。（这是个稍有歧义的题目，考试时按标准答案的 `s=18` 走。）

---

### 5.8 找出最早与最晚的喷发年份

**题目要求**：用 `np.min` / `np.max` 找出数据集的时间跨度。

**解题思路**：`data['Start Year'].values` 得到 NumPy array → 传给 `np.min` / `np.max`。这里体现了**pandas 与 numpy 的互通**。

```python
import numpy as np                      # 导入 numpy，别名 np（本 notebook 还没导过）

Years = data['Start Year'].values       # 选出 'Start Year' 列，取 .values 转成 NumPy array
                                        # ⚠️ 列名 'Start Year' 中间有一个空格，一个字都不能错

Earliest_eruption = np.min(Years)       # 用 numpy 的 min 函数找最小值 = 最早的年份
print("Earlist Eruption occured in ", Earliest_eruption)   # （原文拼写 Earlist / occured 有误，无伤大雅）

Latest_eruption = np.max(Years)         # 用 numpy 的 max 函数找最大值 = 最晚的年份
print("Latest Eruption occured in ", Latest_eruption)
```

**输出**：
```
Earlist Eruption occured in  -10450
Latest Eruption occured in  2019
```

**输出解读**：
- **−10450** = 公元前 10450 年（约 12,470 年前），落在**全新世（Holocene）**初期。Smithsonian 数据库正式覆盖的就是全新世火山活动，所以这个值是**合理的**，不是错误。
- **2019** = 数据库的下载/截止年份。合理。
- Practical 在这里故意问：**"Does this make sense? Do we have an error in our database?"** —— 这是一个训练**批判性数据审视**的问题。答案是「合理」，但你必须知道：这么古老的年份来自**地质证据定年**（放射性碳、冰芯、火山灰层），而不是历史观测，因此**不确定度巨大**（数据里的 `Start Year Uncertainty` 列就是干这个的）。

**为什么必须用 min/max 而不是看第一行/最后一行**：见 4.5——DataFrame 的行顺序**不保证有序**。

**替代写法**（等价）：
```python
Earliest_eruption = data['Start Year'].min()   # pandas Series 自带 .min()，不用先转 numpy
```

---

### 5.9 统计每座火山的喷发次数（`.value_counts()`）

**题目要求**：找出数据里有哪些不同的火山，各喷发了多少次。

**解题思路**：`.value_counts()` 一步到位。

```python
data['Volcano Name'].value_counts()   # 对 'Volcano Name' 这一列统计每个不同取值出现的次数
                                      # 返回一个 Series：index 是火山名，值是次数，按次数降序排列
```

**输出**：
```
Volcano Name
Etna                      196
Fournaise, Piton de la    187
Asosan                    171
Villarrica                152
Asamayama                 128
                         ...
Ubehebe Craters             1
Muria                       1
Cayutue-La Vigueria         1
Hudson Mountains            1
Igwisi Hills                1
Name: count, Length: 862, dtype: int64
```

**输出解读**：
- **降序排列**：`.value_counts()` 默认按计数从多到少排。
- **`Etna` 196 次排第一**——意大利西西里岛的埃特纳火山，是欧洲最活跃的火山，且**有 2700 年以上的连续文字记录**（罗马时代就有记载）。老师原话："our database is **dominated by Mount Etna**"。
- 其他高频：Piton de la Fournaise（留尼汪岛，187）、Asosan 阿苏山（日本，171）、Villarrica 比亚里卡（智利，152）、Asamayama 浅间山（日本，128）。
- **注意这个偏差**：排名前列的几乎都在**有长期观测传统的地区**（意大利、日本、法属留尼汪）。这不能说明它们客观上就是最活跃的火山，而是反映了**观测覆盖的不均衡**。这是 EDA 阶段必须意识到的 **sampling bias**。
- **末尾一大堆只出现 1 次的火山**（Ubehebe Craters、Muria、Igwisi Hills…）——这些通常是史前喷发，靠地质证据识别的单次事件。
- **最后一行的元信息**：`Name: count` 是这个 Series 的名字；**`Length: 862`** 表示有 862 个不同的火山名；`dtype: int64` 表示计数值是 64 位整数。

**⚠️ 常见误用**：
- `data.value_counts()` —— **不能直接对整个 DataFrame 用**（新版 pandas 会当成「统计完全相同的行」，语义完全不同）。必须先选出一列。
- 忘了括号写成 `.value_counts` → 打印出方法对象。

---

### 5.10 Exercise 2：Quantify the number of unique eruption locations

**题目要求**：
> "Extend the above procedure to calculate how many entries there are."
即：算出**有多少座不同的火山**。

**解题思路**：`.value_counts()` 返回的是一个 Series，它的 `.size` 就是不同取值的个数（因为每个不同取值占一行）。这是把 5.2/5.3 学的 `.size` 属性复用到新对象上。

**完整代码**：

```python
# <<-------------------- INSERT CODE HERE ----------------------->>
unique_eruptions = data['Volcano Name'].value_counts()   # 先得到「火山名 → 次数」的 Series
print("Number of unique locations = ", unique_eruptions.size)   # 这个 Series 有多少个元素
                                                                # = 有多少个不同的火山名
# <<------------------------------------------------------------->>
```

**输出**：
```
Number of unique locations =  862
```

**输出解读**：
- **862 座不同的火山**，共记录了 **9891 次**喷发 → 平均每座火山约 11.5 次记录。
- ✅ **自检**：862 与 5.9 输出末尾的 `Length: 862` 完全一致。
- ✅ 合理性检查：862 < 9891，必须如此（不同取值数不可能超过总行数）。

**替代写法**（更直接，也更常用）：
```python
data['Volcano Name'].nunique()          # number of unique，直接返回 862
len(data['Volcano Name'].unique())      # .unique() 返回所有不同取值的数组，再取长度
```
课程给的是 `value_counts().size` 的路子，因为它复用了刚学的两个概念。

---

### 5.11 单条件筛选：只看 2019 年的喷发

**题目要求**：预览只包含 2019 年喷发的子集。

```python
data[data['Start Year'] == 2019].head()
```

**逐层拆解**（老师强调的理解方式）：

```python
# 第 1 层：data['Start Year'] == 2019
#   → 对整列做逐元素比较，得到一个长度 9891 的布尔 Series：
#     [True, True, True, ..., False, False]
#
# 第 2 层：data[ <布尔 Series> ]
#   → 用这个布尔序列做「掩码」，只保留 True 对应的行
#   → 得到一个全新的、更小的 DataFrame
#
# 第 3 层：.head()
#   → 对这个新 DataFrame 预览前 5 行
```

**输出**：一张 5 行 × 24 列的表，与 5.1 的 `.head()` 输出**完全相同**（Ulawun / Ubinas / Raikoke / Piton de la Fournaise / Great Sitkin，index 仍是 0–4）。

**输出解读**：
- 输出看起来和原始 `.head()` 一样，**这不是巧合也不是 bug**——因为原始文件本来就是按年份倒序排的，前 5 行本来就都是 2019 年。
- **index 保持 0,1,2,3,4** 说明筛选**保留了原始索引**（pandas 筛选后不会重新编号）。这一点很重要：如果筛出来的是第 100、250、777 行，index 会显示 100、250、777 而不是 0、1、2。
- `5 rows × 24 columns` — 列数没变（筛的是行不是列）✅

**⚠️ 常见误用**：
- 写成 `data[data['Start Year'] = 2019]` —— 单等号是赋值 → `SyntaxError`。
- 写成 `data['Start Year' == 2019]` —— 方括号位置错了，把比较写在了列名字符串上 → `KeyError: False`。
- 列名写成 `'start year'`（小写）→ `KeyError: 'start year'`。

---

### 5.12 Exercise 3：Plot the location of eruptions in 2019

**题目要求**：
> "Extract the coordinates of eruptions that occurred in 2019 and plot them on a new map using **red circles**."
提示要串联两步：
> - Extract a subset of the dataframe 'data' where the Start Year variable is equal to 2019
> - From the above, extract the Latitude and Longitude values separately

**解题思路**：把 5.11 的筛选和 5.5 的取值链在一起：
```
data[条件]  →  ['Latitude']  →  .values
筛出行     取出列        变成数组
```

**完整代码**：

```python
# <<-------------------- INSERT CODE HERE ----------------------->>

# 三步链式：① data[data['Start Year'] == 2019] 筛出 2019 年的行
#          ② ['Latitude'] 从这个子 DataFrame 里取纬度列
#          ③ .values 转成 NumPy array
Latitude = data[data['Start Year'] == 2019]['Latitude'].values

# 同理取经度。注意筛选条件要**原样重复一遍**
Longitude = data[data['Start Year'] == 2019]['Longitude'].values

# <<------------------------------------------------------------->>

import cartopy.crs as ccrs
import matplotlib.pyplot as plt

fig = plt.figure(figsize=(15,15))          # 15×15 英寸画布

ax = plt.axes(projection=ccrs.PlateCarree())   # PlateCarree 投影坐标轴
ax.stock_img()                                 # 地球底图

plt.scatter(Longitude, Latitude,           # 散点：x = 经度，y = 纬度
         color='red',                      # 题目要求红色
         linewidth=2,
         s=9,                              # 恢复到原来的点大小
         marker='o',                       # 圆圈
         transform=ccrs.PlateCarree(),     # 声明输入坐标是经纬度
         )

plt.show()
```

**输出**：世界地图上只有**几十个**稀疏的红点。

**输出解读**：
- ✅ 点数应该**急剧减少**（从 9891 → 几十个）。老师说："Plot the location of eruptions in 2019 — aren't that many, so obviously we start really reducing down the data we're working with."
- ✅ 剩下的点**依然分布在板块边界上**（环太平洋、印尼、中南美、意大利、冰岛等）。这是**科学合理性检查**：如果 2019 年的喷发出现在西伯利亚腹地，那就要怀疑数据或代码了。
- ❌ 如果地图上还是密密麻麻近万个点 → 筛选没生效，检查是不是漏了 `data[...]` 那层。
- ❌ 如果地图上一个点都没有 → 条件写错了（比如写成 `== '2019'` 字符串，或列名拼错）。

**⚠️ 关键陷阱：`== 2019` vs `== '2019'`**
`Start Year` 列是**整数**类型（能算 min/max 得到 −10450 就说明是数值型），所以必须用**整数 2019**。写成字符串 `'2019'` 不会报错，但会筛出**零行**，画出空地图——这是典型的「静默失败」。

**代码风格提醒**：上面把 `data[data['Start Year'] == 2019]` 写了两遍，重复且低效。更好的写法是：
```python
subset = data[data['Start Year'] == 2019]   # 先存下子集
Latitude  = subset['Latitude'].values
Longitude = subset['Longitude'].values
```
这样既少打字，也保证两次筛选**绝对一致**（避免手滑改了其中一个）。

---

### 5.13 Exercise 4：Plot the location of eruptions between 40°N and 40°S

**题目要求**：
> "We have just selected data from our dataframe using **one criterion**. What if we wanted to introduce a number of conditions?"

Practical 给出的通用模板：
```python
data[(data['Column A'] > X ) & (data['Column A'] < Y)]
```
> "if we wanted to only take data where Column A values were greater than X but less than Y. **When complete you should only see data points between these boundaries.**"

**解题思路**：南北纬 40° 之间 = 纬度 > −40 **且** 纬度 < 40。两个条件用 `&` 连接，**每个条件外面套小括号**。注意：**筛选条件只针对 Latitude**，但 Longitude 也要用**同一个**条件筛（否则两个数组长度不一致 → scatter 报错）。

**完整代码**：

```python
# <<-------------------- INSERT CODE HERE ----------------------->>

# 用两个条件同时筛行：纬度 > -40 且 纬度 < 40
# 注意：① 每个条件都用小括号包住  ② 用 & 而不是 and
Latitude = data[(data['Latitude'] > -40) & (data['Latitude'] < 40) ]['Latitude'].values

# 经度用**完全相同**的筛选条件（仍然是对 Latitude 列判断！），
# 这样才能保证两个数组长度一致、且一一对应同一批喷发事件
Longitude = data[(data['Latitude'] > -40) & (data['Latitude'] < 40)]['Longitude'].values

# <<------------------------------------------------------------->>

import cartopy.crs as ccrs
import matplotlib.pyplot as plt

fig = plt.figure(figsize=(15,15))

ax = plt.axes(projection=ccrs.PlateCarree())
ax.stock_img()

plt.scatter(Longitude, Latitude,
         color='red',
         linewidth=2,
         s=9,
         marker='o',
         transform=ccrs.PlateCarree(),
         )

plt.show()
```

**输出**：世界地图上，**上下两条明显的空白带**——所有 40°N 以北和 40°S 以南的点都消失了。

**输出解读（如何验证正确）**：
- ✅ **阿留申群岛、阿拉斯加、堪察加半岛、千岛群岛北部、冰岛、北欧、南极洲、南美最南端** 的点应该**全部消失**。
- ✅ **印尼、菲律宾、中南美洲、东非、地中海南部、太平洋岛链** 的点保留。
- ✅ 剩下的点依然沿板块边界分布。
- ❌ 如果高纬度还有点 → 条件写反了（比如写成 `<` 和 `>` 互换）。
- ❌ 如果地图空白 → 条件互相矛盾（比如写成 `> 40 & < -40`，永远无法同时成立）。
- ❌ 如果报错 `ValueError: x and y must be the same size` → 说明 Latitude 和 Longitude 用了**不同的**筛选条件。

**⚠️ 本周第一大陷阱：为什么必须写 `&` 而不是 `and`？**

| 写法 | 结果 |
|---|---|
| `(cond1) & (cond2)` | ✅ 正确。`&` 是**逐元素**的按位与，对 Series 的每一行分别判断 |
| `cond1 and cond2` | ❌ `ValueError: The truth value of a Series is ambiguous. Use a.empty, a.bool(), a.item(), a.any() or a.all().` |

**原因**：Python 的 `and` 要求两边能转成单个 True/False，但一个含 9891 个布尔值的 Series 无法归约成单个真假值，pandas 就抛出这个「歧义」错误。`&` 则是 NumPy/pandas 重载过的运算符，做逐元素运算。

**⚠️ 本周第二大陷阱：为什么每个条件都要加小括号？**

Python 里 `&` 的**运算符优先级高于**比较运算符 `>`、`<`。所以：
```python
data['Latitude'] > -40 & data['Latitude'] < 40
# Python 会先算 -40 & data['Latitude']  ← 完全不是你想要的！
# 报错：TypeError: unsupported operand type(s) / 或 ValueError
```
加上小括号后强制先算比较：
```python
(data['Latitude'] > -40) & (data['Latitude'] < 40)   # ✅
```

**扩展：其他逻辑运算符**

| 逻辑 | pandas 写法 | 普通 Python 写法（**不能用在 Series 上**） |
|---|---|---|
| 与 AND | `&` | `and` |
| 或 OR | `\|` | `or` |
| 非 NOT | `~` | `not` |

**老师提到的扩展**：条件可以无限接下去。比如「2019 年 **且** 南北纬 40° 之间」：
```python
subset = data[(data['Start Year'] == 2019) &
              (data['Latitude'] > -40) &
              (data['Latitude'] < 40)]
```

---

### 5.14 找出喷发最频繁的火山（`.idxmax()`）

**题目要求**：为画直方图做准备，先自动找出记录最多的那座火山。

**解题思路**：`.value_counts()` 已经按次数降序排好了，`.idxmax()` 直接返回**最大值对应的索引标签**（也就是火山名）。

```python
data['Volcano Name'].value_counts().idxmax()
# 拆解：
#   data['Volcano Name']        → Series（9891 个火山名）
#   .value_counts()             → Series（index=火山名，value=次数，862 项）
#   .idxmax()                   → 上面这个 Series 中最大值所在的 index 标签
```

**输出**：
```
'Etna'
```

**输出解读**：
- 返回的是**字符串 `'Etna'`**（带引号），不是数字。✅ 与 5.9 输出的第一行（Etna 196）一致。
- **为什么用 `.idxmax()` 而不是 `.max()`**：
  - `.max()` → 返回 `196`（最大的**次数**）
  - `.idxmax()` → 返回 `'Etna'`（次数最大的那一项的**名字**）
  这里我们要的是名字，所以用 `.idxmax()`。
- **为什么不直接手写 `'Etna'`**：因为如果数据更新了、或者换个数据集，`.idxmax()` 会自动适配，硬编码就失效了。这是好的编程习惯。

**⚠️ 注意**：如果有并列第一，`.idxmax()` 只返回**第一个**遇到的。

---

### 5.15 画直方图（DataFrame 的内置绘图能力）

**题目要求**：画出 Etna 所有喷发的年份分布直方图。

**解题思路**：先用条件筛出 Etna 的行，再用 DataFrame 自带的 `.hist()` 方法。

```python
data[data['Volcano Name'] == 'Etna']       # 筛出所有 Volcano Name 等于 'Etna' 的行（196 行）
                                            # ⚠️ 'Etna' 是字符串，必须加引号
```

```python
data[data['Volcano Name'] == 'Etna'].hist(column='Start Year')
# 对上面筛出的子 DataFrame 调用 .hist()
# column='Start Year' 指定对哪一列画直方图
```

**输出**：
```
array([[<Axes: title={'center': 'Start Year'}>]], dtype=object)
```
（下面跟着一张直方图。）

**输出解读**：
- 那行 `array([[<Axes: ...>]], dtype=object)` 是 `.hist()` 的**返回值**——一个装着 matplotlib `Axes` 对象的 NumPy 数组（因为一次可以画多个子图，所以返回的是数组）。它被 Jupyter 自动打印出来了，**不是错误信息**，可以忽略。想不打印它，可以在行尾加分号：`....hist(column='Start Year');`
- 图上的 **title 自动是 `Start Year`** ✅ 说明选对了列。
- **图形特征**：x 轴跨度从约 −4000（或更早）一直到 2019，**绝大多数柱子挤在最右边**，中间大片接近零。
- **科学解读**：Etna 的记录有一小撮很古老的（地质证据），然后是罗马时代以来的历史记录，近几百年密度剧增。
- **Practical 的评价**："Interesting but **lacking resolution** for us to infer behaviour in the last few centuries."（有意思，但分辨率不足，看不出近几百年的行为）→ 这直接引出 Exercise 5。

**新知识点：`.hist()` 是 DataFrame 自带的**
老师特别提到这一点：
> "The other thing I haven't talked about is **data frames have functions to actually produce histograms**. So as well as looking at unique entries in a column, we can actually look at statistical plots."

也就是说，你**不需要**先把数据抽成 NumPy array 再调 `plt.hist()`——DataFrame 直接就能画。这是 DataFrame「比 Excel 强」的体现之一。（Week 8 会用更专业的统计绘图模块，大概率是 seaborn。）

**可选参数**：`bins=` 控制柱子数量，如 `.hist(column='Start Year', bins=50)`。

---

### 5.16 Exercise 5：Plot a histogram of eruptions at Mount Etna between 1200 and the present day

**题目要求**：
> "Remember, we can select data that matches two criteria as, for example: `data[(data['Column A'] > X ) & (data['Column A'] < Y)]`... Can you now implement the required task?"

即：把上面的直方图**限制到 1200 年以后**，看清近代的细节。

**解题思路**：两个条件用 `&` 连接——
1. `data['Start Year'] >= 1200` （年份在 1200 及以后；用 `>=` 把 1200 年本身也包括进来）
2. `data['Volcano Name'] == 'Etna'` （只要 Etna）

然后照旧 `.hist(column='Start Year')`。

**完整代码**：

```python
# <<-------------------- INSERT CODE HERE ----------------------->>

data[(data['Start Year'] >= 1200) & (data['Volcano Name'] == 'Etna')].hist(column='Start Year')
#     └─ 条件1：年份 ≥ 1200 ─┘  └┬┘ └─ 条件2：火山名是 Etna ────┘
#                              用 & 连接，两个条件必须同时满足
#     两个条件各自都用小括号包住 ← 必须！
#     筛完之后对结果 DataFrame 调 .hist()，画 'Start Year' 列的分布

# <<------------------------------------------------------------->>
```

**输出**：
```
array([[<Axes: title={'center': 'Start Year'}>]], dtype=object)
```
（下面跟着一张 x 轴从 1200 到 2019 的直方图。）

**输出解读**：
- ✅ **x 轴范围压缩到 1200–2019**，这是最直接的正确性检查。如果 x 轴还是从 −4000 开始，说明年份条件没生效。
- ✅ **柱子明显变多、变清晰**，能看出时间上的分布结构。
- **科学解读**：柱子高度**随时间递增**，近一两个世纪最高。这里必须区分两种解释：
  1. Etna 真的变得更活跃了？
  2. **观测记录变得更完整了？**

  绝大部分应归因于 (2)——**观测偏差 / 记录完备性偏差**。18 世纪以后科学观测系统化、20 世纪有了仪器监测和卫星遥感，短小的喷发也能被记录下来；而中世纪只有特别剧烈的喷发才会被写进编年史。这正是老师说的 "How accurate are some of these observations?"

- 那行 `array([[<Axes: ...>]])` 依然是返回值，不是报错。

**⚠️ 陷阱**：这里两个条件的**数据类型不同**——`>= 1200` 比的是**整数**，`== 'Etna'` 比的是**字符串**。这完全合法（DataFrame 是 heterogeneous 的，每列类型可以不同），但要保证类型对得上：`>= '1200'` 或 `== Etna`（没引号）都会出错。

**变体练习**（自己可以试）：如果题目要求「1200 到 1800 之间」，就是三个条件：
```python
data[(data['Start Year'] >= 1200) &
     (data['Start Year'] <= 1800) &
     (data['Volcano Name'] == 'Etna')].hist(column='Start Year')
```

---

### 5.17 Practical 官方小结（What We Did）

Notebook 结尾自带的总结：

> 在这次 practical 里我们：
> - 引入 **Pandas** 作为处理结构化真实数据的工具
> - 把真实数据集载入 **Pandas DataFrame**
> - 探索数据集，理解：行和列各代表什么、数据的规模与结构
> - 用 DataFrame 的方法：查看列名与数据类型、选取特定行列、应用简单的筛选条件
> - 处理**地理空间数据**，聚焦于纬度和经度
> - 绘图可视化数据中的空间模式
> - 开始把数值数据与真实世界的地理联系起来
>
> 🧠 *重点是学会探索陌生数据集，并用 Pandas 从中提取意义。*

各练习的学习目标（Notebook 自述）：

| 练习 | 目标（原文意译） |
|---|---|
| Ex 1 | 学会加载陌生数据并做出第一张可视化概览 |
| Ex 2 | 练习从真实数据里提取**数值洞察**，而不只是画图 |
| Ex 3 | 理解**筛选如何改变数据讲述的故事** |
| Ex 4 | 把**数值条件**与**真实地理区域**联系起来 |
| Ex 5 | 从空间可视化转向对真实现象的**统计概括** |

---

## 六、易错点 / 重点难点

### 6.1 语法陷阱清单

#### ① 属性 vs 方法：括号加不加

| 不加括号（属性 property） | 加括号（方法 method） |
|---|---|
| `.size` `.shape` `.ndim` `.values` `.columns` `.dtypes` | `.head()` `.tail()` `.value_counts()` `.idxmax()` `.hist()` `.min()` `.max()` `.nunique()` |

**错误示范与报错**：
```python
data.size()            # TypeError: 'int' object is not callable
data['Lat'].values()   # TypeError: 'numpy.ndarray' object is not callable
data.head              # 不报错，但打印出 <bound method NDFrame.head of ...>，看不到数据
```
**记忆法**：属性是「数据本身的一个性质」（形状、大小），不需要「做」什么；方法是「让数据做一件事」（预览、统计、画图），要用括号「启动」。

#### ② `&` vs `and`（本周头号大坑）

```python
data[(data['Latitude'] > -40) and (data['Latitude'] < 40)]
# ValueError: The truth value of a Series is ambiguous.
#             Use a.empty, a.bool(), a.item(), a.any() or a.all().
```
**原因**：`and` 需要把两边化成单个 True/False，但含 9891 个布尔值的 Series 做不到。
**修法**：改用 `&`（AND）、`|`（OR）、`~`（NOT）。

#### ③ 忘记给每个条件加小括号

```python
data[data['Latitude'] > -40 & data['Latitude'] < 40]
# 因为 & 的优先级高于 >，Python 先算 -40 & data['Latitude']
# → TypeError 或 ValueError（具体取决于 pandas 版本）
```
**修法**：`data[(data['Latitude'] > -40) & (data['Latitude'] < 40)]`

#### ④ 列名写错（大小写 / 空格 / 拼写）

```python
data['start year']    # KeyError: 'start year'
data['StartYear']     # KeyError: 'StartYear'
data['Start  Year']   # KeyError（两个空格）
```
**正确**：`data['Start Year']`
**排错技巧**：先跑 `print(data.columns)` 或 `data.columns.tolist()` 看看真实列名长什么样。**永远不要凭记忆写列名**。

#### ⑤ 用 `=` 而不是 `==` 做比较

```python
data[data['Start Year'] = 2019]   # SyntaxError: invalid syntax
```
**修法**：判断相等用 `==`，赋值才用 `=`。

#### ⑥ 数据类型不匹配（静默失败，最危险）

```python
data[data['Start Year'] == '2019']   # 不报错！但返回 0 行 → 画出空地图
```
**原因**：`Start Year` 列是整数，跟字符串 `'2019'` 永远不相等。
**排错技巧**：
```python
print(data.dtypes)                              # 看每列的数据类型
print(len(data[data['Start Year'] == 2019]))    # 筛完先看看有几行，不要直接画图
```
**这是本周最危险的一类错误**——因为它**不报错**。老师说「写错通常会报错而不是给你错答案」，那句话只覆盖语法层面；类型不匹配和条件写反都属于「静默给错答案」。

#### ⑦ scatter 参数顺序反了

```python
plt.scatter(Latitude, Longitude, ...)   # 错！点全乱套
plt.scatter(Longitude, Latitude, ...)   # 对：x=经度, y=纬度
```
**记忆法**：`scatter(x, y)`，地图上横轴是**经度 Longitude**（东西方向），纵轴是**纬度 Latitude**（南北方向）。

#### ⑧ 忘写 `transform=ccrs.PlateCarree()`

不写的话 Cartopy 会把你的经纬度数字当成**投影后的坐标**（通常是米），点会全部挤到地图正中间的一个极小区域里，或者跑到画面外。**不会报错**。
**记法**：`transform=` 的意思是「我提供的数据是在**哪个**坐标系里的」，Cartopy 负责把它转到 `projection=` 指定的显示坐标系。

#### ⑨ 两个数组长度不一致

```python
Latitude  = data[data['Latitude'] > -40]['Latitude'].values      # 条件 A
Longitude = data[data['Longitude'] > 0]['Longitude'].values      # 条件 B ← 不一样！
plt.scatter(Longitude, Latitude, ...)
# ValueError: x and y must be the same size
```
**修法**：两次筛选必须用**完全相同**的条件；更好的做法是先存下子集再分别取列。

#### ⑩ `.value_counts()` 用在整个 DataFrame 上

```python
data.value_counts()          # 语义完全不同（统计完全相同的整行），几乎没用
data['Volcano Name'].value_counts()   # ✅
```

---

### 6.2 可能遇到的运行时报错速查

| 报错 | 典型原因 | 修法 |
|---|---|---|
| `FileNotFoundError: [Errno 2] No such file or directory: '.../data/GVP_Eruption_Results.csv'` | CSV 路径不对；notebook 的工作目录不是你以为的那个 | `print(os.getcwd())` 看当前目录；`os.listdir()` 看有哪些文件；确认 `data/` 文件夹存在 |
| `KeyError: 'Start year'` | 列名拼写/大小写/空格错 | `print(data.columns)` 核对 |
| `ValueError: The truth value of a Series is ambiguous...` | 用了 `and` / `or` / `not` | 改用 `&` / `\|` / `~` |
| `TypeError: 'int' object is not callable` | 对属性 `.size` 加了括号 | 去掉括号 |
| `TypeError: 'numpy.ndarray' object is not callable` | 写了 `.values()` | 改成 `.values` |
| `ValueError: x and y must be the same size` | Latitude 与 Longitude 的筛选条件不一致 | 用同一个子集 |
| `NameError: name 'np' is not defined` | 忘了 `import numpy as np` | 补上 import |
| `NameError: name 'data' is not defined` | 前面读数据的 cell 没运行（或重启过内核） | **`Kernel → Restart and Run All`** |
| `ModuleNotFoundError: No module named 'cartopy'` | 环境里没装 Cartopy | 在 Colab 上先跑第一个 code block；本地用 `conda install -c conda-forge cartopy` |
| 图是空的 / 没有点 | 条件筛出 0 行（类型不匹配或条件矛盾） | 先 `print(len(subset))` 检查行数 |
| 点全挤在中心一小块 | 忘写 `transform=` | 补上 `transform=ccrs.PlateCarree()` |

---

### 6.3 重点难点：链式操作的阅读方法

本周最难读的一行代码是：

```python
Longitude = data[(data['Latitude'] > -40) & (data['Latitude'] < 40)]['Longitude'].values
```

**老师给的读法**：先看骨架、再看填充。

```
第 0 步（骨架）：   data[ ??? ][ ??? ].???
第 1 步（最外层）： data[ 筛选条件 ]         → 一个更小的 DataFrame
第 2 步（选列）：   [...]['Longitude']       → 从这个小 DataFrame 里取经度列，得到 Series
第 3 步（转数组）： ....values               → 变成 NumPy array
```

**筛选条件本身再拆**：
```
(data['Latitude'] > -40)  →  布尔 Series A：纬度大于 -40 吗？
(data['Latitude'] < 40)   →  布尔 Series B：纬度小于 40 吗？
A & B                     →  布尔 Series C：两个都成立吗？（逐行做 AND）
```

**新手最佳实践：拆成多行**
不要一行写完，分步骤写、每步 print 一下：
```python
mask = (data['Latitude'] > -40) & (data['Latitude'] < 40)   # 布尔掩码
print(mask.sum())            # 有多少行满足条件？（True 算 1，False 算 0）
subset = data[mask]          # 筛出子集
print(subset.shape)          # 确认行数
Latitude  = subset['Latitude'].values
Longitude = subset['Longitude'].values
print(len(Latitude), len(Longitude))   # 确认两个数组等长
```
这样任何一步出问题都能立刻定位。**熟练之后再写成一行。**

---

### 6.4 重点难点：先检查、再相信

本周最重要的**工作方法**（不是语法）：

1. **加载后立刻 `.head()`** —— 确认读进来的是对的文件、列名长什么样。
2. **看 `.shape`** —— 确认行列数符合预期。
3. **筛选后先看行数** —— `len(subset)` 或 `subset.shape`，不要直接画图。
4. **画完图看合理性** —— 火山是否沿板块边界？高纬度是否真的空了？点数是否减少了？
5. **交叉验证** —— 5.10 的 862 与 5.9 的 `Length: 862` 对得上；5.2 的 9891×24 与 237384 对得上。这些「对得上」就是最好的自检。

老师的原话值得抄下来：
> "If you don't preview the data and then you start getting a load of errors when you're doing numerical operations, **it might be just you're loading the wrong thing**."

---

### 6.5 数据科学层面的难点：偏差意识

本周的数据看似「客观」，但处处是偏差，考试/作业里如果要写讨论，这是加分点：

| 偏差类型 | 在本数据集里的表现 |
|---|---|
| **Sampling bias（采样偏差）** | Etna 记录最多，不是因为它客观上最活跃，而是因为西西里有 2700 年文字记录 |
| **Temporal bias（时间偏差）** | 越近代记录越密集（Exercise 5 的直方图），反映的是观测能力提升而非活动增强 |
| **Missing data（缺失值）** | 大量 `NaN`（VEI、Area of Activity、各种 Uncertainty 列） |
| **Dating uncertainty（定年不确定度）** | 古老喷发的 `Start Year` 来自地质定年，误差可能几十到几百年 |
| **Geographic bias（地理偏差）** | 海底火山、无人区火山严重欠采样 |

老师说这些正是 **Week 8 统计** 要处理的：
> "We can produce statistical plots of the data in our columns, really have a feel for where data is skewed. Is there a bias in the data? Are we missing values? Are there values that just don't make sense? We need to cut those out."

---

## 七、本周术语表

### 编程 / pandas 术语

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| pandas | （不译，读 "潘达斯"） | Python 处理表格型数据的标准模块，约定别名 `pd` |
| DataFrame | 数据框 | pandas 的核心对象：二维、可变大小、可容纳异质数据、带标签行列的表格 |
| Series | 序列 | DataFrame 的一列（或一行），一维带标签的数据 |
| index | 索引 | DataFrame 最左边那一列行标签；筛选后仍保留原编号；Week 8 会改成时间戳 |
| column | 列 | DataFrame 的纵向字段，用 `data['列名']` 访问 |
| labeled axes | 带标签的轴 | 行和列都有名字，不必靠数字位置定位 |
| size-mutable | 大小可变 | DataFrame 创建后还能加/删行列 |
| heterogeneous | 异质的 | 不同列可以是不同数据类型（数字/文字/日期混装） |
| `pd.read_csv()` | 读 CSV 函数 | 把 CSV 文件读成 DataFrame |
| `.head()` | 预览头部 | 显示前 n 行（默认 5），加载数据后的第一件事 |
| `.tail()` | 预览尾部 | 显示后 n 行 |
| `.size` | 元素总数 | 行数 × 列数（属性，不加括号） |
| `.shape` | 形状 | 返回 (行数, 列数) 的元组（属性） |
| `.ndim` | 维数 | number of dimensions；DataFrame 恒为 2，Series 为 1（属性） |
| `.values` | 取值 | 把列转成 NumPy array（属性，不加括号） |
| `.value_counts()` | 值计数 | 统计某列各不同取值出现的次数，按次数降序 |
| `.idxmax()` | 最大值的索引 | 返回最大值对应的**索引标签**（不是数值） |
| `.hist()` | 直方图 | DataFrame 自带的绘图方法，`column=` 指定列 |
| `.nunique()` | 唯一值个数 | 返回某列有多少个不同取值 |
| boolean masking | 布尔掩码 | 用一串 True/False 筛选行的机制：`data[条件]` |
| subset | 子集 | 按条件筛出来的一部分数据 |
| chaining | 链式操作 | 把多个操作用 `.` 或 `[]` 串起来一次写完 |
| NaN | 非数 / 缺失值 | Not a Number，表示该位置没有数据 |
| property / attribute | 属性 | 对象自带的性质，访问时**不加括号** |
| method | 方法 | 对象能执行的操作，调用时**必须加括号** |
| shadowing | 变量遮蔽 | 自定义变量名撞上已导入的模块名，把它盖掉（如本周的 `path`） |

### 文件与数据术语

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| CSV | 逗号分隔值文件 | Comma Separated Values，最通用的文本表格格式 |
| JSON | JSON 格式 | JavaScript Object Notation，物联网/网络传输常用，人类可读 |
| NetCDF | 网络通用数据格式 | Network Common Data Form，气候/大气数据标准；含 dimensions、variables、attributes |
| Parquet | Parquet 格式 | 大数据行业的高效列式二进制格式，读写快省空间但不可读 |
| shapefile / vector file | 矢量文件 | GIS 里存储点线面几何的格式，下周 GeoPandas 处理 |
| IO | 输入输出 | Input/Output，读写文件 |
| metadata | 元数据 | 「关于数据的数据」：谁采的、何时、用什么仪器、什么条件 |
| provenance | 溯源 / 来历 | 数据的来源与流转记录 |
| data standard | 数据标准 | 法规或行业规定的数据格式与规范 |
| IP (intellectual property) | 知识产权 | 数据的所有权；AI 时代的重大法律议题 |
| delimiter | 分隔符 | CSV 里分隔字段的字符（默认逗号） |

### 数据科学术语

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| EDA (exploratory data analysis) | 探索性数据分析 | 建模之前先理解数据：有无错误、是否可信、统计特征如何 |
| data science process | 数据科学流程 | 原始数据 → 处理清洗 → EDA → 模型算法 → 沟通决策 → 数据产品 |
| data cleaning | 数据清洗 | 处理缺失、异常、重复、格式不一致的数据 |
| "garbage in, garbage out" | 垃圾进垃圾出 | 用垃圾数据训练出来的模型只会给出垃圾结果 |
| bias | 偏差 | 数据系统性地偏离真实情况 |
| sampling bias | 采样偏差 | 因采样方式导致某些情况被过度/不足代表 |
| skewed | 有偏的 / 偏斜的 | 分布不对称，向一侧拖尾 |
| categorical data | 分类数据 | 取值为类别而非数值的数据（如火山名） |
| data product | 数据产品 | 分析成果转化成可供他人使用的东西（报告、地图、API…） |
| Hype Cycle | 炒作周期 | Gartner 提出的技术成熟度曲线：期望膨胀顶峰 → 幻灭低谷 → 启蒙爬升 → 生产力平台 |
| peak of inflated expectations | 期望膨胀顶峰 | 人们以为新技术无所不能的阶段 |
| trough of disillusionment | 幻灭低谷 | 发现技术不万能、期望回落的阶段（老师说这是好事） |

### 地理空间与绘图术语

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| geospatial data | 地理空间数据 | 带有地理坐标（经纬度）的数据 |
| Cartopy | （不译） | 给 matplotlib 提供地图画布的 Python 模块，本周用它画世界地图 |
| GeoPandas | （不译） | 建立在 pandas 之上的地理空间模块，能处理复杂几何形状，下周用 |
| GIS | 地理信息系统 | Geographical Information Systems，处理与分析空间数据的整套学科与工具 |
| CRS (coordinate reference system) | 坐标参考系统 | 定义坐标数值如何对应地球上真实位置的规则，`cartopy.crs` 就是它 |
| map projection | 地图投影 | 把球面的地球展开到平面的数学方法，必然带来变形 |
| PlateCarree | 等距圆柱投影 / 平板投影 | 最简单的投影：经度直接当 x、纬度直接当 y；高纬度严重变形 |
| Latitude | 纬度 | −90 到 +90，正为北纬（南北方向，地图上的 y） |
| Longitude | 经度 | −180 到 +180，正为东经（东西方向，地图上的 x） |
| `stock_img()` | 内置底图 | Cartopy 自带的低分辨率地球图像 |
| `transform=` | 变换参数 | 告诉 Cartopy 你提供的坐标属于哪个坐标系 |
| marker | 标记 | 散点图上点的形状（`'o'` 圆、`'^'` 上三角…） |
| `figsize` | 图幅尺寸 | matplotlib 画布大小，单位英寸，`(宽, 高)` |
| scatter plot | 散点图 | 用点表示每个观测的位置 |
| histogram | 直方图 | 把数值分成区间（bins），统计每个区间的频数 |
| bins | 分箱 / 区间 | 直方图把数据切分的区间数或边界 |
| Google Earth Engine | 谷歌地球引擎 | 云端海量卫星遥感数据平台，基于 JavaScript；Python 接口为 geemap |

### 地球科学 / 数据集术语

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Smithsonian Global Volcanism Program | 史密森学会全球火山活动计划 | 本周数据来源，维护全新世以来的全球火山喷发数据库 |
| Holocene | 全新世 | 约 1.17 万年前至今的地质时期；数据库最早记录 −10450 年正落在此期 |
| VEI (Volcanic Explosivity Index) | 火山爆发指数 | 0–8 的对数尺度，衡量喷发规模（喷出物体积、喷发柱高度） |
| Confirmed Eruption | 确认喷发 | 有可靠证据确认发生过的喷发事件 |
| Evidence Method (dating) | 定年证据方法 | 如何确定喷发年代：Historical Observations（历史观测）、放射性碳、冰芯等 |
| plate boundary | 板块边界 | 构造板块交界处；全球绝大多数火山沿此分布 |
| Ring of Fire | 环太平洋火山带 | 环绕太平洋的高地震与火山活动带 |
| Etna | 埃特纳火山 | 意大利西西里岛，欧洲最活跃火山，本数据库记录最多（196 次） |
| Piton de la Fournaise | 富尔奈斯火山 | 法属留尼汪岛的盾状火山，记录第二多（187 次） |
| Asosan | 阿苏山 | 日本九州的大型破火山口火山（171 次） |
| Villarrica | 比亚里卡火山 | 智利安第斯山脉的活火山（152 次） |

---

## 附：本周一页纸速记

```python
# ---------- 1. 加载 ----------
import pandas as pd
import numpy as np
import os
path = os.getcwd()
data = pd.read_csv(path + "/data/GVP_Eruption_Results.csv")

# ---------- 2. 检查（永远先做！） ----------
data.head()          # 预览前 5 行
data.shape           # (9891, 24)
data.size            # 237384
data.ndim            # 2
data.columns         # 看真实列名，防 KeyError

# ---------- 3. 选列 / 转数组 ----------
data['Latitude']              # → Series（一维）
data['Latitude'].values       # → NumPy array（喂给绘图函数）

# ---------- 4. 统计 ----------
np.min(data['Start Year'].values)              # -10450
np.max(data['Start Year'].values)              # 2019
data['Volcano Name'].value_counts()            # 各火山次数，降序
data['Volcano Name'].value_counts().size       # 862 座不同的火山
data['Volcano Name'].value_counts().idxmax()   # 'Etna'

# ---------- 5. 条件筛选（核心！） ----------
data[data['Start Year'] == 2019]                             # 单条件
data[(data['Latitude'] > -40) & (data['Latitude'] < 40)]     # 双条件：& + 每个条件加括号
data[data['Start Year'] == 2019]['Latitude'].values          # 筛行 → 选列 → 转数组

# ---------- 6. 画地图（模板，照抄） ----------
import cartopy.crs as ccrs
import matplotlib.pyplot as plt
fig = plt.figure(figsize=(15,15))
ax = plt.axes(projection=ccrs.PlateCarree())
ax.stock_img()
Latitude  = data['Latitude'].values
Longitude = data['Longitude'].values
plt.scatter(Longitude, Latitude,              # 注意顺序：x=经度, y=纬度
            color='red', linewidth=2, s=9, marker='o',
            transform=ccrs.PlateCarree())     # 必须写！
plt.show()

# ---------- 7. 画直方图 ----------
data[(data['Start Year'] >= 1200) & (data['Volcano Name'] == 'Etna')].hist(column='Start Year')
```

**三条铁律**：
1. 用 `&` `|` `~`，不用 `and` `or` `not`；每个条件外面**加小括号**。
2. `.size` `.shape` `.ndim` `.values` **不加括号**；`.head()` `.value_counts()` `.hist()` **加括号**。
3. 加载后立刻 `.head()`，筛选后立刻查行数，画完图先看**科学上合不合理**。
