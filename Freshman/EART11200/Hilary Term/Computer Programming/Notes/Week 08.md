# Week 8 — Pandas 时间索引、数据框合并与统计可视化（Seaborn）

> 课程：EART11200 The Natural Scientist's Toolkit — Computer Programming（Hilary Term，第 8 周 / 共 9 周）
> 材料：`Lecture8_25.pdf`（讲义）、`EART11200 - 25-Mar-transcript`（课堂录音转写）、`Practical_8.ipynb`（实践 Notebook）
> 数据：Beijing 2017–2018 空气质量 + 气象观测（Harvard Dataverse, Wang Hongwei 2019, doi:10.7910/DVN/USXCAK）

---

## 一、本周主题

本周是「Pandas and data discovery」的第二部分，也是整个课程**最后一周的常规数据处理内容**（下周 Week 9 是 cluster analysis / 机器学习，之后进入 assessment notebook 阶段）。

课程整体版图（讲义 slide "course layout"）：

| 周次 | 主题 |
|---|---|
| 1–2 | 'Vanilla' Python：data types、loops、basic operations、conditionals |
| 3 | The NumPy module |
| 4 | Conway's Game of Life |
| 5 | Differential Equations（Modules and Functions） |
| 6 | Pandas and data discovery |
| 7 | Geospatial analysis |
| **8** | **Statistical Analysis（本周）** |
| 9 | Cluster Analysis |
| 10–12 | Creating a notebook assessment（从 week 4–9 中选一个题目） |

**本周要解决的核心问题**（讲义原话）：
> *"What if we have data we want to perform statistical analysis on the data?"*

拆成三个具体动作：

1. **Setting the index of a dataframe** —— 什么是 index？为什么要把「时间」设为 index？
2. **Merging two dataframes** —— 为什么要合并？如何在**共同时间戳**上安全地合并？
3. **Performing statistical analysis** —— correlation coefficients（相关系数）、pair plots（配对图）、box-plots（箱线图）。

老师在 transcript 开头把本周和上周做了明确对比：

> *"Merging different data frames, so it's very similar to what you've done on the previous notebook, but that was based on merging on **geographical** information. What we'll do today is merge on **time** information."*

即：**Week 7 按地理位置合并（GeoPandas / 空间叠置），Week 8 按时间戳合并（DatetimeIndex）**。

**为什么时间合并特别重要？** 老师的解释：

> *"a lot of the information we're able to access through instruments, we're measuring stuff as a function of time... whether it's manual or in the lab, then you'll have a time stamp... Often we collect things in different ways, so you might have one data frame on meteorological information and one data frame on air pollution. For various reasons they might not match, but we want to combine the two because we understand the impacts of weather on air quality."*

> *"really what we don't want to do is have to manually match the data sets because there's a lot of chance for error there."*

本周科学问题：**北京某一监测站，气象条件（温度、气压、湿度、风向、风速）如何影响空气污染物（PM2.5、PM10、NO2、CO、O3、SO2）的浓度？污染物有没有日变化（diurnal）规律？**

---

## 二、核心概念

### 2.1 什么是 index（索引）？

讲义原文：

> *Each column has a name associated with it, also known as a **label**. We can access entries in specific columns.*
> *When you ask for a preview, Pandas will assign an integer index system. The **index of a Dataframe is a set that consists of a label for each row**.*

要点：

- DataFrame 有两套"标签"：
  - **列标签（column labels / column names）**——我们一直在用，例如 `df['temperature']`；
  - **行标签（index）**——从 Week 6 到 Week 7 我们几乎没碰过它。
- 当你用 `pd.read_csv()` 载入数据时，**Pandas 会自动生成一个整数 index**：第 0 行 index=0，第 1 行 index=1……（老师："Everything starts at zero in pandas."）
- 这个默认整数 index **没有科学含义**，它只是"第几行"。
- **本周的关键跳跃**：把 index 换成**有意义的东西**——时间戳。一旦 index 是时间，Pandas 就"懂"这一行是哪一天哪一小时的数据，随后就能自动做时间对齐、时间切片、提取小时/星期/月份。

老师用一个很生动的例子说明这个跳跃的价值：

> *"if we tell Seaborn... I want you to give me all of the information at 9 a.m. on a weekday. Then how do we do that? Again, what we don't want to do is start getting ourselves in a twist by chaining together different conditional statements. We could if we wanted. But Python's all about redoing the minimum."*

> *"You can specify more complex criteria. Give me information on a Saturday in April between the hours of two and four."*

**一句话记忆**：index 不设时间 → 时间只是一列普通文本，你要自己写一堆 `if` 去拆；index 设成时间 → Pandas 自带一整套时间工具箱。

### 2.2 datetime 格式：为什么必须先转换

CSV 读进来时，`utc_time` 这一列的 dtype 是 `object`。

Notebook 原文解释：
> *"When we interrogate the original data type we are told the `utc_time` column has the type `object`. The details are not important here but essentially this is telling us that we have **variable string lengths in an array** here."*

老师在课上说得更直白：

> *"Pandas won't recognize this as time. It'll only recognize it as **text**. So we need to tell Pandas, convert that into information you will understand. I.e., when I ask you to give me the hour, minute, second, or month, it can do that."*

所以流程必须是：

```
CSV 里的 "30/01/2017 16:00"  (字符串 / object)
        ↓  pd.to_datetime()
   Timestamp('2017-01-30 16:00:00')   (dtype = datetime64[ns])
        ↓  df.set_index('utc_time')
   DatetimeIndex  → 解锁 .hour / .minute / .weekday / .month / 时间切片 / 时间对齐合并
```

**注意 dtype 名字**：转换成功后会看到 `datetime64[ns]`。`64` 指 64-bit 整数存储，`[ns]` 指精度到**纳秒（nanosecond）**。底层其实是"距离 1970-01-01T00:00:00 的纳秒数"，所以时间可以像数字一样比较、排序、相减。

### 2.3 为什么要 merge（合并）？

讲义：
> *"Quite often, we don't have all the data we need in one place. You can spend a long time trying to merge datasets into one place. Here we can use Pandas to merge to a common index."*

本周的具体情形：
- `beijing_17_18_meo.csv` —— 气象数据（meteorology），列名里站点叫 `station_id`，值形如 `shunyi_meo`；
- `beijing_17_18_aq.csv` —— 空气质量数据（air quality），列名里站点叫 `stationId`，值形如 `shunyi_aq`。

两个文件**起止时间不同**（气象从 2017-01-30 16:00 开始，空气质量从 2017-01-01 14:00 开始），行数也不同（顺义站：气象 8781 行，AQ 8886 行）。

老师强调**不对齐的后果**（这是本周最重要的"科学诚信"论点）：

> *"if I want to generate a correlation coefficient between one column and another, and they've come from two different data frames, **if they're not in sync, I'm going to get an erroneous statistic**. And that can then lead to many, many errors... So if I'm providing data to inform a decision and my data's wrong, then that decision could be wrong."*

> *"it doesn't matter what we do with the models and the algorithms. **If the data's not right, this can lead to massive problems.**"*
> *"you can create a garbage model from garbage data. It's useless."*

也就是经典的 **garbage in, garbage out**。老师还举了现实例子：NHS 正在建的基础模型 "Nightingale AI"，若底层数据错误，会直接影响临床决策，而这正是 AI 监管（regulation）要处理的问题——"谁的错？是科学家的错，还是建模型的人的错？"

### 2.4 merge 的机制（inner join）

`pd.merge(df1, df2)` 在**不指定任何参数**时的默认行为：

1. 自动找出两个 DataFrame 的**同名列**（common columns）作为合并键（join key）；
2. 默认 `how='inner'`，即**取交集**——只保留在两边都出现的键值。

本例中：

| meteo 的列 | aq 的列 |
|---|---|
| `station_id`, `longitude`, `latitude`, **`utc_time`**, `temperature`, `pressure`, `humidity`, `wind_direction`, `wind_speed`, `weather` | `stationId`, **`utc_time`**, `PM2.5`, `PM10`, `NO2`, `CO`, `O3`, `SO2` |

唯一同名列是 `utc_time` → 自动按时间戳做 inner join。

**结果验证**：met 8781 行、aq 8886 行 → merged **8220 行**。8220 < min(8781, 8886)，说明两边的时间戳并非完全覆盖，交集把两边都缺的时刻扔掉了。合并后的第一行时间是 `2017-01-30 16:00:00`——正好是气象数据的起点，因为 AQ 有 1 月初的数据但气象没有，那部分被 inner join 剔除了。

Notebook 原文提示：
> *"When this prints to the screen, you can see that our data now starts on the 30/1/2017, **even though we had meteorological data before that date**."*
（注：这句注释的方向说反了——实际是**空气质量**数据在此日期之前还有数据，气象数据才是从 1/30 开始的。看 `.head()` 输出即可确认：`Shunyi_aq_df` 起点为 2017-01-01 14:00，`Shunyi_met_df` 起点为 2017-01-30 16:00。这属于教材里的一处小口误，理解合并逻辑即可。）

老师补充的实操细节：

> *"that same workflow could be repeated. You could have three data frames, you could have 12. Yeah, you'd just merge them one by one, which is a bit of a pain in Pandas. **You can't give it the entire array and do that. It wants to check every merge operation.** So you just write multiple lines to do that."*

即 `pd.merge()` 一次只能合并两个 DataFrame，多个要链式或逐行写。

### 2.5 DatetimeIndex 的属性——本周最"性价比高"的语法

一旦 index 是 `DatetimeIndex`，就可以直接取出时间的各个分量：

```python
combined_df.index.hour      # 每一行的「小时」(0-23)
combined_df.index.minute    # 分钟
combined_df.index.second    # 秒
combined_df.index.weekday   # 星期几 (Monday=0 ... Sunday=6)
combined_df.index.month     # 月份 (1-12)
combined_df.index.year      # 年份
combined_df.index.day       # 日
```

返回的是一个**与行数等长的整数数组（Index 对象）**，可以直接当作绘图的 x 轴，也可以直接写成条件式。

老师：
> *"this data frame dot index basically is me accessing the index. And the hour dot minute dot second dot weekday dot month is a **property of a timestamped index**. So I could specify the weekday if I wanted to. **I could just switch this hour to weekday** and produce a plot to look at the variability over the week."*

这就是本周"一行代码画出日变化图"的秘密。

### 2.6 Diurnal profile（日变化廓线）的科学含义

**Diurnal profile** = 某变量在一天 24 小时内的平均/分布变化模式。

在大气污染研究中它极其重要，因为它把**污染浓度**和**人类活动节律**联系起来：

> *"imagine this axis was hour of the day, and we're going to look at air pollution — you can then see the range of values as a function of the hour of day. And why that's important? Because you can start to link that with **human activity**. If you see pollution spikes during rush hour, you can then start to infer there's probably a relationship there."*

老师给的英国实证：
- **PM（颗粒物）在英国的日变化不明显**——"you wouldn't expect that in the UK anyway because now we've moved away from heavy industries. You don't see these spikes as a function of human activity."
- **NO2 的日变化很明显**——"You do with nitrogen dioxide because a lot of that comes from cars. So you see the **rush hour peaks** going through."（早晚高峰双峰型）
- **季节性**：冷月 PM 高，因为 "everyone puts their wood burners on. They've become trendy, haven't they? And we see that now certainly in South Manchester. The spike in particulate pollution in **affluent areas**."（富裕地区烧柴壁炉导致颗粒物飙升——有政治意涵）

在北京，情况与英国不同（重工业 + 燃煤 + 供暖季），所以日变化和季节变化都更强，这也是 Exercise 3（对比全年 vs 八月）的意义所在。

### 2.7 本周涉及的污染物与气象变量（科学背景）

| 变量 | 全称 / 含义 | 单位（本数据集） | 主要来源 / 科学意义 |
|---|---|---|---|
| `PM2.5` | 空气动力学直径 ≤ 2.5 µm 的细颗粒物 | µg/m³ | 燃烧、二次生成（气态前体物转化）；可深入肺泡进入血液，健康危害最大 |
| `PM10` | 直径 ≤ 10 µm 的可吸入颗粒物 | µg/m³ | 扬尘、道路磨损、建筑、沙尘；含 PM2.5，故两者高度相关 |
| `NO2` | 二氧化氮 | µg/m³ | 主要来自机动车尾气与燃烧；早晚高峰型；O3 的前体物之一 |
| `CO` | 一氧化碳 | mg/m³ | 不完全燃烧（车辆、燃煤、生物质）；很好的"燃烧源示踪剂"（tracer） |
| `O3` | 臭氧（近地面） | µg/m³ | **二次污染物**，由 NOx + VOCs 在阳光下光化学生成；午后峰值、夏季高、夜间被 NO 滴定消耗 |
| `SO2` | 二氧化硫 | µg/m³ | 燃煤、含硫燃料；冬季供暖期升高；硫酸盐颗粒的前体物 |
| `temperature` | 气温 | °C | 影响光化学反应速率、边界层混合、供暖需求 |
| `pressure` | 气压 | hPa | 高压 → 静稳天气 → 逆温 → 污染累积 |
| `humidity` | 相对湿度 | % | 高湿促进二次气溶胶吸湿增长（PM2.5 上升）、也和霾（Haze）相关 |
| `wind_direction` | 风向 | 度（0–360） | 判断污染来源方位 |
| `wind_speed` | 风速 | m/s | 高风速 → 稀释扩散 → 污染下降 |
| `weather` | 天气现象文字描述 | 字符串 | `Sunny/clear`、`Haze`（霾）等 |

数据来源：**北京 2017–2018，共 18 个监测站点**。老师说他是从**使馆站点（embassy site）** 相关的公开渠道拿到的——"Embassies often have information on meteorological and air quality data."（美国驻华使馆的 PM2.5 监测数据是著名的公开数据源）。他也说 18 个站"Not a huge amount, but it's standard for air quality stations **because they're very expensive to run**."

### 2.8 相关系数（correlation coefficient）与相关矩阵

`.corr()` 默认计算 **Pearson 相关系数 r**，取值 [-1, 1]：

- `r = +1`：完全正线性相关；
- `r = 0`：无线性相关（注意：**不代表无关系**，可能是非线性关系）；
- `r = -1`：完全负线性相关。

**相关矩阵（correlation matrix）** 是一个 n×n 的方阵，第 (i, j) 个元素是第 i 列和第 j 列的相关系数。它必然：
- **对角线全是 1.0**（自己和自己完全相关）——这是检查结果是否正确的第一个 sanity check；
- **关于对角线对称**（r(A,B) = r(B,A)）——第二个 sanity check。

老师提醒的重要前提：**只有两列数据在时间上对齐了，相关系数才有意义**。这正是前面 merge 的全部理由。

### 2.9 Box plot（箱线图）——五数概括

老师课上专门问了学生 "Have you heard of box plots before?"，然后解释：

> *"box plots are a really nice way of visualising the statistics of the data in a **single figure**... A box plot allows us to see the distribution of our data, but highlight the mean, the interquartile range, and the outliers. So in a single figure, we can see **how skewed our data is, where the outliers are. Do we need to ignore them?** So we don't have to create line plot after line plot after line plot because quite quickly you wouldn't be able to see the information in your data."*

Notebook 给的定义（five number summary，五数概括）：

> *Boxplots are a standardized way of displaying the distribution of data based on a five number summary ("minimum", first quartile (Q1), median, third quartile (Q3), and "maximum").*

| 元素 | 英文 | 定义 |
|---|---|---|
| 中位数 | median (Q2 / 50th percentile) | 数据集的中间值 |
| 下四分位数 | first quartile (Q1 / 25th percentile) | 最小值与中位数之间的中间值 |
| 上四分位数 | third quartile (Q3 / 75th percentile) | 中位数与最大值之间的中间值 |
| 四分位距 | interquartile range (IQR) | Q3 − Q1，即中间 50% 数据的跨度 |
| 须 | whiskers | 从箱体延伸出的线段，到"最大/最小"为止 |
| "最大值" | "maximum" | **Q3 + 1.5 × IQR**（不是真正的最大值！） |
| "最小值" | "minimum" | **Q1 − 1.5 × IQR** |
| 离群点 | outliers | 超出上述"最大/最小"范围的点，单独画成散点 |

**判读要点**：
- 箱体（box）= 中间 50% 的数据，箱体越高说明数据越离散；
- 中位线**不在箱体正中** → 数据**偏态（skewed）**。中位线偏下 = 右偏（正偏），大量小值 + 少量极大值，这正是污染物浓度的典型分布；
- 上方一堆离群点 → 存在污染事件（pollution episode）。

---

## 三、语法速查与函数表

### 3.1 本周新语法 / 新函数

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `pd.read_csv(path)` | 读 CSV 成 DataFrame（Week 6 已学，本周复用） | `data_meteo = pd.read_csv(path+"/data/beijing_17_18_meo.csv")` | 路径用 `os.getcwd()` 拼接，避免硬编码绝对路径 |
| `df.head()` | 预览前 5 行 | `data_meteo.head()` | 在 Jupyter 里**只有 cell 最后一个表达式**会自动显示；写两遍没有意义 |
| `df.dtypes` | 返回每列的数据类型（**属性，无括号**） | `data_meteo.dtypes` | `object` 通常代表字符串；转换成功后应看到 `datetime64[ns]` |
| `df.size` | 元素总数 = 行 × 列（属性） | `data_meteo.size` → `1580470` | 158047 × 10 = 1580470，可用来自检 |
| `df.shape` | (行数, 列数) 元组（属性） | `data_meteo.shape` → `(158047, 10)` | 最常用的"数据有多大"检查 |
| `df.ndim` | 维数（属性） | `data_meteo.ndim` → `2` | DataFrame 恒为 2；Series 为 1 |
| `df['col'].value_counts()` | 统计某列各唯一值出现次数，返回 Series | `data_meteo['station_id'].value_counts()` | Week 6 用过（火山数据集）；**默认按次数降序**，且默认忽略 NaN |
| `.size` 接在 value_counts 后 | 唯一值的**个数** | `data_meteo['station_id'].value_counts().size` → `18` | 等价写法：`df['station_id'].nunique()`（更直接） |
| `df[df['col'] == value]` | 布尔筛选（boolean masking），选出满足条件的行 | `data_meteo[data_meteo['station_id'] == 'shunyi_meo']` | **必须用 `==`（比较）而不是 `=`（赋值）**；返回的是**视图/副本**，直接改它可能触发 `SettingWithCopyWarning` |
| `df.hist(column='name')` | 画某列的直方图（Pandas 内建，底层 matplotlib） | `data_meteo[...].hist(column='temperature')` | 返回 `array([[<Axes: ...>]], dtype=object)`——是**Axes 数组**不是图本身；老师吐槽这种图 "awful, they're just block diagrams" |
| `pd.to_datetime(series, format='mixed')` | 把字符串列转成 `datetime64[ns]` | `data_aq['utc_time'] = pd.to_datetime(data_aq['utc_time'], format='mixed')` | **必须把结果赋回去**，否则原列不变；`format='mixed'` 允许每行格式不一致（较慢但稳）；大数据集要跑几秒——Notebook 明确提示 "You may find this takes a few seconds" |
| `df.set_index('col')` | 把某列设为行索引 | `combined_df = combined_df.set_index('utc_time')` | **默认返回新 DataFrame，不原地修改！** 不赋值就等于白做（或用 `inplace=True`）。设为 index 后该列**从普通列中消失**（列数 10 → 9） |
| `df.index` | 访问行索引对象（属性） | `combined_df.index` → `DatetimeIndex([...], dtype='datetime64[ns]', name='utc_time', length=8220)` | 打印出来能确认三件事：是不是 DatetimeIndex、名字对不对、长度对不对 |
| `df.index.hour` / `.month` / `.weekday` / `.minute` / `.second` / `.year` / `.day` | 从 DatetimeIndex 取时间分量 | `combined_df.index.hour` | **只有 DatetimeIndex 才有**；普通整数 index 调用会 `AttributeError` |
| `pd.merge(df1, df2)` | 合并两个 DataFrame | `combined_df = pd.merge(Shunyi_met_df, Shunyi_aq_df)` | 默认按**所有同名列** inner join；一次只能合两个；显式写法更安全：`pd.merge(a, b, on='utc_time', how='inner')` |
| `df[['c1','c2',...]]` | 选取多列子集（**双层方括号**） | `combined_df[['temperature','pressure','PM2.5']]` | 单层 `df['c1']` 返回 Series；双层返回 DataFrame。选多列必须用 list |
| `df.corr()` | 计算相关系数矩阵 | `corr = combined_df[[...]].corr()` | 只对数值列有效；**必须先切出数值列**，否则字符串列（如 `weather`）会报错或被忽略；默认 Pearson，自动跳过 NaN（pairwise） |
| `df.dropna()` | 删除含 NaN 的行 | `combined_df[[...]].dropna()` | 默认 `how='any'`（一行里只要有一个 NaN 就删）；返回新对象 |
| `np.nanmax(arr)` / `np.nanmin(arr)` | 忽略 NaN 求最大/最小值 | `np.nanmax(combined_df_new["PM2.5"].values)` | **`np.max` 遇到 NaN 会返回 NaN**！这是本周 Notebook 专门警告的陷阱 |
| `.values` | 从 Series 取出底层 NumPy 数组 | `combined_df_new["PM2.5"].values` | 这就是老师反复说的"Pandas 与 NumPy 的连接点" |
| `df.boxplot(column=[...])` | Pandas 内建箱线图 | `combined_df_new[[...]].boxplot(column=['PM2.5','PM10',...], figsize=(12,12))` | 返回 Axes，可继续链式调用 `.set_yscale('log')` |
| `import seaborn as sns` | 引入 Seaborn 统计可视化库 | — | 约定俗成的别名是 `sns` |
| `sns.boxplot(data=, x=, y=, ax=)` | 画箱线图 | `sns.boxplot(data=combined_df, x=combined_df.index.hour, y=combined_df['PM2.5'], ax=axes[0])` | `x`/`y` 既可传列名字符串，也可直接传数组/Series；`ax=` 指定画到哪个子图 |
| `sns.heatmap(corr, xticklabels=, yticklabels=)` | 把矩阵画成热力图 | `sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns)` | 输入必须是二维矩阵（这里是相关矩阵 DataFrame）；`corr.columns` 保证标签顺序与矩阵一致 |
| `sns.pairplot(df)` | 所有数值列两两画散点 + 对角线画分布 | `sns.pairplot(combined_df[[...]].dropna())` | n 列 → n² 个子图，**列数多会非常慢**；必须先 `.dropna()` |
| `plt.subplots(nrows, ncols, figsize=)` | 创建 figure 和 axes 网格 | `fig, axes = plt.subplots(1, 2, figsize=(12,8))` | 单图时 `axes` 是单个对象；多图时是数组，用 `axes[0]`、`axes[1]` 索引 |
| `.set(xlabel=, ylabel=)` | 一次性设置坐标轴标签 | `sns.boxplot(...).set(xlabel='Hour of day', ylabel='Abundance')` | Seaborn 绘图函数返回 Axes，可以链式 `.set()` |
| `ax.set_ylim([min, max])` | 设 y 轴范围 | `axes[0].set_ylim([0,100])` | **对比两图时必须统一量程**，否则视觉误导 |
| `ax.set_title('...')` | 设子图标题 | `axes[0].set_title('All year')` | — |
| `ax.set_yscale('log')` | y 轴改对数刻度 | `....boxplot(...).set_yscale('log')` | 污染物浓度跨几个数量级时必备；**注意 log 轴无法显示 0 和负值** |
| `plt.show()` | 显示图像 | `plt.show()` | 在 Jupyter 里也能顺便抑制掉那行 `<Axes: >` 之类的返回值文本 |

### 3.2 本周产生的图表及判读要点

| 图 | 生成方式 | 怎么判读 / 判断对不对 |
|---|---|---|
| **温度直方图**（Exercise 2） | `data_meteo[data_meteo['station_id']=='shunyi_meo'].hist(column='temperature')` | 横轴温度、纵轴频次。北京大陆性季风气候 → 分布应该**很宽、接近双峰或平坦**，从约 −15 °C 到 +35 °C。老师："It can get very cold. It can get very, very warm." 如果只有一个窄峰，说明筛选条件写错了（可能没筛出单站） |
| **PM2.5 日变化箱线图**（全年 vs 八月，Exercise 3） | `sns.boxplot(data=..., x=df.index.hour, y=df['PM2.5'])`，两个子图 | 横轴 0–23 小时，纵轴浓度。看：(a) 有没有早晚高峰双峰；(b) 箱体高度反映离散程度；(c) 中位线偏下 → 右偏；(d) 上方大量离群点 = 重污染事件。**两图 y 轴必须都设 [0,100] 才可比**。八月是夏季（多雨、边界层高、无供暖），浓度整体应低于全年 |
| **PM2.5 vs PM10 日变化对比**（Exercise 4，pingchang 站） | 同上，y 分别取 `PM2.5` 和 `PM10` | y 轴分别设 [0,100] 和 [0,200]，因为 **PM10 ⊇ PM2.5，数值天然更大**。两者形态应高度相似（因为 r ≈ 0.84） |
| **相关系数热力图** | `corr = df[[...]].corr()` → `sns.heatmap(corr, ...)` | **对角线必须是最亮/最热的一条线（全为 1.0）**——这是最快的正确性检查。颜色越"热"= 相关越强。老师："the hotter the cell, the higher the correlation between meteorological factors and pollution factors" |
| **Pair plot（配对图）** | `sns.pairplot(df[[...]].dropna())` | n×n 网格：**对角线是每个变量自身的分布（直方图/KDE）**，非对角线是两两散点图。看散点是否呈条带状（线性关系）、扇形（异方差）、或团块（无关）。老师："This can become quite a complex figure to look at" |
| **多污染物箱线图（对数轴）** | `df[[...]].boxplot(column=[...], figsize=(12,12)).set_yscale('log')` | 横轴是不同污染物，纵轴是浓度。用对数轴是因为 CO（个位数 mg/m³）和 PM10（上千 µg/m³）差了 3 个数量级，线性轴上 CO 会被压成一条线 |

### 3.3 相关系数结果解读（Shunyi 站，实际输出）

```
             temperature  pressure  humidity   PM2.5    PM10     NO2      CO      O3     SO2
temperature     1.0000   -0.8629    0.2137   0.0411  0.1848 -0.1824 -0.2016  0.5784 -0.2544
pressure       -0.8629    1.0000   -0.2761  -0.0867 -0.2360  0.0396  0.0838 -0.4592  0.1893
humidity        0.2137   -0.2761    1.0000   0.2936  0.0937  0.2514  0.2644 -0.2666 -0.1442
PM2.5           0.0411   -0.0867    0.2936   1.0000  0.8445  0.5139  0.7617 -0.0666  0.4910
PM10            0.1848   -0.2360    0.0937   0.8445  1.0000  0.3594  0.5574  0.0266  0.2500
NO2            -0.1824    0.0396    0.2514   0.5139  0.3594  1.0000  0.5939 -0.5212  0.4433
CO             -0.2016    0.0838    0.2644   0.7617  0.5574  0.5939  1.0000 -0.2421  0.5729
O3              0.5784   -0.4592   -0.2666  -0.0666  0.0266 -0.5212 -0.2421  1.0000 -0.1278
SO2            -0.2544    0.1893   -0.1442   0.4910  0.2500  0.4433  0.5729 -0.1278  1.0000
```

**逐条科学解读**（考试/报告里能直接用）：

| 变量对 | r | 科学解释 |
|---|---|---|
| temperature ↔ pressure | **−0.863** | 最强的一对。温压反相是基本气象规律：暖 → 空气膨胀密度下降 → 地面气压低；冷 → 高压。也对应季节（冬季冷高压）。 |
| PM2.5 ↔ PM10 | **+0.845** | 极强正相关。**PM2.5 是 PM10 的子集**（PM10 按定义包含所有 ≤10 µm 的颗粒），必然高度相关。这条可以当作"数据合并是否正确"的物理自检——如果这里不接近 1，说明对齐出了问题。 |
| PM2.5 ↔ CO | **+0.762** | 二者都主要来自**燃烧过程**（燃煤、机动车、生物质）。CO 化学寿命长，是很好的一次燃烧源示踪剂，与一次颗粒物同源同步。 |
| CO ↔ NO2 | +0.594 | 同为燃烧/交通源。 |
| temperature ↔ O3 | **+0.578** | 臭氧是**二次光化学污染物**：气温高 → 通常伴随强太阳辐射 → 光化学反应快 → O3 生成多。夏季午后 O3 峰值。 |
| CO ↔ SO2 | +0.573 | 都与燃煤相关（尤其冬季供暖）。 |
| NO2 ↔ O3 | **−0.521** | 显著负相关。夜间/高 NO 条件下 **NO + O3 → NO2 + O2**（"titration effect"，滴定效应）会消耗臭氧；同时市区高 NO2 的时段往往是低辐射时段。这是大气化学的经典关系。 |
| pressure ↔ O3 | −0.459 | 高压常见于冬季冷高压（低温低辐射 → O3 低）。 |
| humidity ↔ PM2.5 | +0.294 | 弱正相关。高湿促进气溶胶**吸湿增长（hygroscopic growth）** 和二次转化，也对应霾（Haze）天气。 |
| temperature ↔ PM2.5 | +0.041 | **几乎为零**。注意：这**不代表温度和 PM2.5 无关**，而是「线性」关系弱——冬季（低温）供暖排放高、夏季（高温）二次生成也可能高，两个相反机制互相抵消，导致线性相关系数接近 0。**这是"相关系数不等于因果、也不能捕捉非线性"的绝佳教学案例。** |

---

## 四、课堂补充（transcript 独有）

### 4.1 老师对"用可视化讲故事"的强调

这是本节课最重头的口头内容，讲义 slide 上只有一句 "statistical visualisations can tell a story"。

> *"I always like to use these diagrams because I think we assume that when we're doing statistics, we want to look at numbers. So we want to understand means, medians and interpret them scientifically. **But you can bypass that and generate really meaningful visualisations**."*

**例子 1：麻疹（measles）疫苗**
> *"being through the Covid period, a lot of hesitancy around vaccinations, lots of misuse of information in the media, and this is where visualisations can be really powerful... this is just showing as a function of time the yearly incidences of measles outbreaks before and after vaccines were introduced. **That in itself tells the story you need to tell. You don't need to look at medians into quartile ranges.**"*

**例子 2：他自己的科研成果——新冠封锁期的交通与空气质量**（这段是纯 transcript 内容，讲义上没有）
> *"this is when we were researching the impact of the lockdown on traffic flow and air quality. So the information in this graph we provided to the council... we found that the **ratio of HGVs to normal traffic increased significantly during lockdown** because pollution wasn't dropping as quickly as we thought it should. We were all online ordering on Amazon. So the number of HGVs went up... **I think DPD increased threefold its business operations.** ... we were monitoring increases in carbon, nitrogen dioxide and particulate matter that just didn't reflect the state that the country was in. But this made sense. So we gave this to **Transport for Greater Manchester** and said, look, this is a really unfortunate experiment, but this shows the impact of HGVs."*

（HGV = Heavy Goods Vehicle，重型货车。这个故事说明：**看似矛盾的数据（封城了污染却没降）恰恰通过分组可视化找到了解释**——用 Seaborn 按"是否封城"上色，一眼看出 HGV 占比变了。）

> *"someone who's working in a public sector organisation just wants to see something like this, they need to tell their bosses that we need to keep funding this."*

**给我们的启示**：做数据分析最终要输出**决策者能看懂的图**，不是一堆数字。

### 4.2 老师反复推荐：去读文档

> *"I'm going to recommend actually that there's many different modules we've worked with. **Start looking at the documentation of these packages** because you can go much further beyond than what I'm introducing you to. And Seaborn is another example of that."*

> *"You don't have to be limited by the data from a particular notebook."*
> *"you can apply [this workflow] to any data that you can load in, whether it's time series, you could then combine it with the GeoPandas data frames as well."*

Seaborn 官方文档：https://seaborn.pydata.org

课上展示的箱线图示例就是直接从 Seaborn 文档里拿的——一个**天文学数据集**（radial velocity vs distance，行星径向速度随距离的变化）。

### 4.3 关于"社区构建的函数"

> *"a lot of these functions have been built by the community. They've been **tested, validated**. We just use them in a very applied sense, which is really what we want to do more broadly."*

即：不必重新造轮子，你的价值在于**正确地组合已有工具去回答科学问题**。

### 4.4 数据清洗在求职中的价值（老师的职业建议）

> *"If you do want to actually take your coding journey forward after this course... when you get to applying to the next stage, so you might have a **GitHub repository**, which can help you set that up if you like, so really showcase your **digital CV**. The more that you can show that you can do the **cleaning steps prior to models and algorithms**, the more competitive it is, because **not many people want to spend time on that element, but everything rests on that**."*

### 4.5 下周预告：Cluster analysis

> *"Next week we will look at models and algorithms... Specifically what we'll do is we'll **detect distinct groups within our data, so that's called clustering**. So we merge similar observations together, and that's useful in many different areas, whether it's finance, socioeconomic work, or environmental science, because often what we're measuring we don't have a label for. If you're observing lots of different species in an environment, you might have images of lots of different birds or sound files of different birds. You might not necessarily know which one each is, but clustering at least bunches those into very similar groups."*

同时老师说下周会用 Seaborn 把直方图画得更漂亮：
> *"the Seaborn documentation does have much more prettier versions of histograms. We'll use that next week before we do some machine learning... because these are awful. They're just block diagrams, aren't they? We can produce really nice plots and **overlay distributions according to different criteria**."*

### 4.6 课上对 Notebook 的逐段口头导览（关键提示）

老师在课上把 Notebook 从头到尾过了一遍，这些是他额外强调的：

1. **顶部的 Colab box** —— "The standard box at the top, whether you're working in Google Colab or not."（每周都一样，判断是否在 Colab 里，是则挂载 Google Drive 并 cd 到课程目录）
2. **两个 CSV 是分开的** —— "The underscore MEO files and meteorological data, there's an underscore AQ file as well. **They're kept separately. So that's the whole point of this exercise.**"
3. **站点列名不一致是个坑** —— "there's a station ID. But notice **the station ID is named a little bit differently**. So that can be confusing. It's just the way the data was collected."（`station_id` vs `stationId`）
4. **Exercise 2 是"链式操作"的示范** —— "what I'm doing here is I'm **chaining together conditional operations with a histogram**... I'm saying work with this data frame but only when this is true. So when the station ID is given by this entry, then produce the histogram of that data... **So in a single line, loaded data in, get a feel for the temperature variation.**"
5. **顺序很重要** —— "I'm going to actually **extract single sites first**. So if I'm not on the entire network. Then we set the index."（先按站点筛，再设索引，再合并。若先在 15 万行全网数据上设时间索引，index 会有大量重复值，合并会灾难性膨胀）
6. **Seaborn 需要你告诉它三件事** —— "as with any function, there is an expected set of inputs... **What's the name of the data frame you're working with? What x variables and y variables do you want me to work with?**"
7. **可以自由替换维度** —— "I could change that to weekday. Look, if you see here, I change it to month. And I'm actually specifying only look at data in August. **So I can chain together multiple things here, depending on what questions you're trying to answer.**"
8. **Notebook 看着长其实操作不多** —— "it looks like this notebook's quite big, but actually there aren't many operations. A lot of it's what you've done already."

### 4.7 Assessment notebook（本周课上花了很长时间讲，务必记）

这是 transcript 里独有的、对成绩最直接的信息：

**基本安排**
- Blackboard 上已开放 **assessment folder**。
- 共 **6 个选项**，分别对应 **Week 4 到 Week 9** 的主题：
  1. Conway's Game of Life（Week 4）
  2. Differential Equations（Week 5）
  3. + 4. 两个 Geospatial 的（Week 6/7）
  5. **本周内容：Pandas + 统计分析（Week 8）**
  6. Cluster analysis（Week 9）
- **只需做一个**。"They all have the same feeling."
- 每年约 **60–70% 的人选 Conway's Game of Life**，但完全自由。
- 老师个人推荐：*"next week [cluster analysis] I think is probably the one that's most directly useful based on the current investment areas of focus... in terms of AI and data science."*

**截止日期：5 月 12 日**（在考试季之前）。

**提交格式**（务必注意）
> *"you can download the Jupyter Notebook file and that's what you'll upload for me to run. So **no PDFs, no Word documents, the actual notebook file** (.ipynb). You would download that and upload it to **Turnitin**."*

**Notebook 结构**（像写一份 mini report）
- **Abstract**：向完全不了解的人总结这份报告在展示什么。"treat this as if you were coming at this completely cold."
- **Introduction**：介绍这个领域、为什么相关。"you might have to do a little bit of digging around the area, not too long, but **set the scene**."（不要求写成大论文——"we're not expecting a big essay on that"）
- **Methodology**（**关键 section**）：*"explaining to a user **modules and functions** that are used, the **workflow** that's apparent in the code."* 老师强调：光有代码注释不够，**读者还想要一段叙述（narrative）**。
- **Code**：可以是一整个大代码块，也可以拆成多个 cell（"in notebooks, you can create new code blocks"，在 notebook 顶部工具栏的选项里）。**必须加注释**——"you're expected to put comments on different parts of the code."
- **Results**：讨论发生了什么，和任何 dissertation 写法类似，但带有代码/数值模拟的成分。

**可以直接用 practical 的代码**
> *"In each example, you can use the **exact same code in the practical** to drop into your notebook, but you might need to change the options or change the flow a little bit, change any for loop, produce an extra set of plots."*
> *"**You don't need to reference where the code came from**, you can use the code from the notebook, that's absolutely fine."*

**关于生成式 AI**
> *"If you want to do the same task using generative AI code, absolutely fine. **But put that code in and describe it**... What I'd recommend, though, is at least doing this one first and then getting a feel for what generative AI tools can give you."*
> *"there is ChatGPT guidance as well. You can use that **if you reference it**. ... In some examples, **it doesn't necessarily give you the right answer either. So make sure you test it when you're running it.**"*

**其他**
- 无字数上下限（"no minimum or maximum length"）。
- 引用格式不限，**但要一致**（"I'm not interested in what referencing style you use. Just be consistent."）。
- Blackboard 上有 **rubric（评分标准）**、**guide sheets for the report and the code**、以及 **FAQs**。
- 复活节假期后还有 **2 次 practical 专门用来答疑**（"we can't do the work for you, obviously, but we can give you guidance, refer you to the solutions from the weekly practicals"）。
- 老师的工作顺序建议：**先把代码跑通、生成输出，再围绕输出写文字**。"I'd normally always recommend getting the code working first, generate some outputs, and then start writing around that."

---

## 五、Practical 要点

Notebook：`Practical_8.ipynb` — *Pandas and statistics*

**总目标**（Notebook 原文）：
> *"We are going to load two datasets: One with meteorological data, and the other with air quality data. It is important to understand the concentrations and variability of key pollutants **as a function of time and meteorological conditions**."*

结构：
- Part 1：用 Pandas 建 DataFrame（Exercise 1、2）
- Part 2：用共同时间索引合并两个 DataFrame（Exercise 3、4）
- Part 3：对 DataFrame 做统计分析（Exercise 5）

---

### Step 0 — Colab 环境检测（每周固定模板）

```python
if 'google.colab' in str(get_ipython()):
    # get_ipython() 返回当前 IPython/Jupyter 内核对象；转成字符串后
    # 如果里面含 'google.colab' 说明我们跑在 Google Colab 上
    from google.colab import drive          # 只有在 Colab 上才 import，避免本地报 ModuleNotFoundError
    mount='/content/gdrive'                 # Colab 里挂载 Google Drive 的固定路径
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)                      # 弹出授权流程，把 Drive 挂到 /content/gdrive
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    # 切换工作目录，这样后面的相对路径 "/data/xxx.csv" 才能找到文件
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root                         # %cd 是 Jupyter 的 magic command（不是 Python 语法）
else:
    print('Not running on CoLab')           # 在学校集群 / 本地 Anaconda 上跑就走这一支
```

**输出**：`Not running on CoLab`（若在本地）

**为什么需要它**：同一份 Notebook 要能在 Colab 和本地两种环境跑。`%cd` 前面的 `%` 表示这是 IPython 的 **magic command**，不是标准 Python。

---

### Step 1 — 载入气象数据并预览

```python
import pandas as pd          # 惯例别名 pd
import os                    # 操作系统接口模块
from os import path          # 单独引入 path 子模块（本 Notebook 其实没直接用到）

path=os.getcwd()             # get current working directory，取当前工作目录
                             # 注意：这里把变量名取成 path，覆盖了刚才 from os import path 导入的 path 模块！
                             # 能跑通是因为后面只把它当字符串用，但这是坏习惯（见第六节）

# 用字符串拼接得到完整文件路径，然后读 CSV
data_meteo = pd.read_csv(path+"/data/beijing_17_18_meo.csv")
data_meteo.head()            # 这一行的输出会被下一行覆盖，其实是多余的

# Preview the first 5 lines of the loaded data
data_meteo.head()            # 只有 cell 里最后一个表达式会自动渲染
```

**输出（前 5 行）**：

| | station_id | longitude | latitude | utc_time | temperature | pressure | humidity | wind_direction | wind_speed | weather |
|---|---|---|---|---|---|---|---|---|---|---|
| 0 | shunyi_meo | 116.615278 | 40.126667 | 30/01/2017 16:00 | -1.7 | 1028.7 | 15 | 215.0 | 1.6 | Sunny/clear |
| 1 | shunyi_meo | 116.615278 | 40.126667 | 30/01/2017 17:00 | -3.5 | 1028.4 | 24 | 16.0 | 1.0 | Haze |
| 2 | shunyi_meo | 116.615278 | 40.126667 | 30/01/2017 18:00 | -3.7 | 1028.1 | 27 | 32.0 | 1.1 | Haze |
| 3 | shunyi_meo | 116.615278 | 40.126667 | 30/01/2017 19:00 | -3.9 | 1027.6 | 27 | 21.0 | 0.9 | Haze |
| 4 | shunyi_meo | 116.615278 | 40.126667 | 30/01/2017 20:00 | -4.1 | 1026.7 | 26 | 17.0 | 1.1 | Haze |

**输出解读**：
- **最左边那一列 0,1,2,3,4 就是 Pandas 自动生成的整数 index** —— 本周的主角就是要把它换掉。
- 数据是**每小时一条**（16:00 → 17:00 → 18:00 …）。
- 经纬度 (116.615, 40.127) 确实在北京东北方向（顺义区），量级合理。
- 气压 ~1028 hPa 偏高 + 气温 −2 °C → 典型冬季冷高压，静稳天气 → 果然 `weather` 列显示 `Haze`（霾）。**这已经能看出气象与污染的耦合了。**
- `utc_time` 目前还是形如 `"30/01/2017 16:00"` 的**字符串**，是 **DD/MM/YYYY**（英式日期）格式。

---

### Step 2 — 检查数据类型

```python
data_meteo.dtypes    # 属性，不是函数，所以没有括号
```

**输出**：
```
station_id         object
longitude         float64
latitude          float64
utc_time           object      ← 注意！时间还是 object（字符串）
temperature       float64
pressure          float64
humidity            int64      ← 湿度是整数
wind_direction    float64
wind_speed        float64
weather            object
dtype: object
```

**为什么要看 dtypes**（Notebook 原文）：
> *"This is useful for a number of reasons that might include whether we need to convert between, for example, `string` to `float` to perform some numerical analysis."*

**判读**：
- `object` = Pandas 对"混杂类型/字符串"的统称。三个 object 列：站名、时间、天气描述。
- `utc_time` 是 object → **现在还不能用 `.hour`**，必须先转 datetime。这就是接下来 Step 6 要做的事。

---

### Step 3 — 检查数据规模

```python
# Lets also check the data frame size
size = data_meteo.size          # .size = 元素总数（行 × 列）
print("Size of dataframe =", size)

# dataframe.shape - gives the seperated number of rows, columns, etc
shape = data_meteo.shape        # .shape = (行数, 列数) 元组
print("Shape of dataframe =", shape)

# dataframe.ndim  - Number of dimensions. Do we have a 2D array, 3D array?? etc
ndim = data_meteo.ndim          # .ndim = 维数，DataFrame 恒为 2
print("Number of dimensions =", ndim)
```

**输出**：
```
Size of dataframe = 1580470
Shape of dataframe = (158047, 10)
Number of dimensions = 2
```

**输出解读与自检**：
- 158047 × 10 = 1,580,470 ✓ —— `size` 和 `shape` 自洽，说明读取无误。
- 158,047 行 = 18 个站 × 约 8,780 小时。一年 = 8760 小时，数据跨 2017-01 到 2018-01（约 1 年）→ **完全对得上**。
- 老师："That is quite a large number of observations!" / "It's quite a lot. But again, I don't want to manually deal with that. And this is where I want Pandas to do a lot of the heavy lifting for me."

---

### Exercise 1 — 数一数北京有多少个气象站

**题目**：
> *Count how many meteorological stations there are in Beijing. If you recall, in Practical 6, we were able to count how many unique values we had from a particular column in our data frame. In this case, you should find there are **18** different stations.*

**解题思路**：
1. 站点名存在 `station_id` 列里；
2. 用 `.value_counts()` 得到"每个唯一站名出现了多少次"的 Series；
3. 这个 Series 有多长，就有多少个唯一站点 → `.size`。

**代码**：
```python
#------'INSERT CODE HERE'------
data_meteo['station_id'].value_counts().size
#   data_meteo['station_id']   → 取出站名这一列，得到一个 Series
#   .value_counts()            → 统计每个唯一值出现次数，返回 Series（索引=站名，值=次数）
#   .size                      → 该 Series 的元素个数 = 唯一站名的数量
#------------------------------
```

**输出**：
```
18
```

**输出解读**：北京这套网络有 18 个气象监测站。老师补充：*"Not a huge amount, but it's standard for air quality stations because they're very expensive to run."*

**等价的更简洁写法**：
```python
data_meteo['station_id'].nunique()      # number of unique，一步到位
len(data_meteo['station_id'].unique())  # 先取唯一值数组再算长度
```

**顺带看看是哪 18 个站**（自己复习时可以跑）：
```python
data_meteo['station_id'].value_counts()   # 会列出每个站名及其行数
```

---

### Exercise 2 — 画顺义站的温度直方图

**题目**：
> *Plot a histogram of temperature from the station with the ID `shunyi_meo`.*

**解题思路**：
1. 先用**布尔筛选**从 15 万行中挑出 `station_id == 'shunyi_meo'` 的那 8781 行；
2. 对筛出的子 DataFrame 直接调用 `.hist(column='temperature')`。

老师课上称这叫 **chaining together conditional operations with a histogram**——把"条件筛选"和"画图"串成一行。

**代码**：
```python
# Plot the histogram with one line
#------'INSERT CODE HERE'------
data_meteo[data_meteo['station_id'] == 'shunyi_meo'].hist(column='temperature')
#   内层 data_meteo['station_id'] == 'shunyi_meo'
#        → 得到一个长度 158047 的布尔 Series（True/False mask）
#   外层 data_meteo[ ...布尔Series... ]
#        → 只保留 True 的行，得到顺义站的 8781 行子表
#   .hist(column='temperature')
#        → 对 'temperature' 这一列画直方图
#------------------------------
```

**输出**：
```
array([[<Axes: title={'center': 'temperature'}>]], dtype=object)
```
再加上一张直方图。

**输出解读**：
- 那行文字**不是报错**，而是 `.hist()` 的**返回值**——一个 NumPy object 数组，里面装着 matplotlib 的 `Axes` 对象。`.hist()` 设计成可以一次画多列，所以返回的是二维 Axes 数组。想抑制这行文字可以在末尾加分号 `;` 或加 `plt.show()`。
- 直方图本身：横轴温度（约 −15 到 +35 °C），纵轴频次。分布很宽，反映北京**温带大陆性季风气候**的巨大年温差。老师："It can get very cold. It can get very, very warm."
- **判断对不对**：如果直方图只有几百个样本或范围极窄，说明筛选条件写错了（比如把 `shunyi_meo` 写成 `shunyi_aq`，那样会筛出 0 行）。

---

### Step 4 — 载入空气质量数据

```python
# Lets load the second spreadsheet
# Read data from file 'beijing_17_18_aq.csv'
data_aq = pd.read_csv(path+"/data/beijing_17_18_aq.csv")
data_aq.head()
# Preview the first 5 lines of the loaded data
data_aq.head()
```

**输出（前 5 行）**：

| | stationId | utc_time | PM2.5 | PM10 | NO2 | CO | O3 | SO2 |
|---|---|---|---|---|---|---|---|---|
| 0 | aotizhongxin_aq | 01/01/2017 14:00 | 453.0 | 467.0 | 156.0 | 7.2 | 3.0 | 9.0 |
| 1 | aotizhongxin_aq | 01/01/2017 15:00 | 417.0 | 443.0 | 143.0 | 6.8 | 2.0 | 8.0 |
| 2 | aotizhongxin_aq | 01/01/2017 16:00 | 395.0 | 467.0 | 141.0 | 6.9 | 3.0 | 8.0 |
| 3 | aotizhongxin_aq | 01/01/2017 17:00 | 420.0 | 484.0 | 139.0 | 7.4 | 3.0 | 9.0 |
| 4 | aotizhongxin_aq | 01/01/2017 18:00 | 453.0 | 520.0 | 157.0 | 7.6 | 4.0 | 9.0 |

**输出解读（重要的科学观察）**：
- **列名是 `stationId` 不是 `station_id`！** 老师专门提醒过。这个"不一致"其实是**幸运的**——正因为不同名，`pd.merge()` 才不会误把它当作合并键（详见第六节）。
- **站名后缀是 `_aq` 不是 `_meo`**，所以 Shunyi 站在两个表里分别叫 `shunyi_meo` 和 `shunyi_aq`。
- **时间起点是 2017-01-01 14:00**，比气象数据（2017-01-30 16:00）早了近一个月 → 这就是需要 inner join 对齐的原因。
- **数值本身触目惊心**：PM2.5 = 453 µg/m³。WHO 24 小时指导值是 **15 µg/m³**，中国国标二级日均是 75 µg/m³。453 是严重霾污染（这正是 2017 年元旦华北那场著名的重污染过程）。同时 PM10 = 467，二者接近说明**颗粒物以细粒子为主**（PM2.5/PM10 比值 ≈ 0.97），典型的二次生成/燃烧来源而非扬尘。
- O3 只有 3 µg/m³ —— 极低。因为冬季+高 NO2（156）→ **NO 滴定把臭氧消耗光了**，且冬季光化学弱。这与后面 corr 矩阵里 NO2–O3 = −0.52 完全一致。

---

### Step 5 — 转换为 datetime 格式

Notebook 原文：
> *"once we convert strings to the datetime format, we can ask Pandas to extract powerful information like hourly averages or diurnal profiles **without having to get our hands dirty with NumPy or similar**."*

```python
data_aq['utc_time']=pd.to_datetime(data_aq['utc_time'],format='mixed')
#   pd.to_datetime(...)  → 把字符串 Series 解析成 datetime64[ns]
#   format='mixed'       → 允许每一行的日期格式不完全一致，逐行推断
#                          （比固定 format 慢，但对脏数据更稳）
#   最关键：结果必须重新赋值回 data_aq['utc_time']，否则原表纹丝不动
data_aq.dtypes
```

**输出**：
```
stationId            object
utc_time     datetime64[ns]     ← 转换成功！
PM2.5               float64
PM10                float64
NO2                 float64
CO                  float64
O3                  float64
SO2                 float64
dtype: object
```

```python
data_meteo['utc_time']=pd.to_datetime(data_meteo['utc_time'],format='mixed')
data_meteo.dtypes
```

**输出**：
```
station_id                object
longitude                float64
latitude                 float64
utc_time          datetime64[ns]     ← 同样成功
temperature              float64
pressure                 float64
humidity                   int64
wind_direction           float64
wind_speed               float64
weather                   object
dtype: object
```

**如何判断是否成功**：Notebook 直接问了 *"Can you see the `datetime64[ns]` result?"* —— 看到 `datetime64[ns]` 就对了。若还是 `object`，说明解析失败或忘了赋值。

**耗时提示**：Notebook 写 *"You may find this takes a few seconds."* —— 15 万行 × `format='mixed'` 逐行推断确实慢。若知道格式固定，用 `format='%d/%m/%Y %H:%M'` 会快几十倍。

---

### Step 6 — 按站点拆出两个子 DataFrame

Notebook 强调的语法模板：
```python
new_dataframe = old_dataframe[old_dataframe[column] == some value]
```

以及一个反复出现的提醒：
> *"When we are checking a value is true, we use **two equal signs `==`** rather than one `=` when assigning a value to a variable."*

```python
# Lets create a seperate Meteorology based data frame
Shunyi_met_df = data_meteo[data_meteo["station_id"] == "shunyi_meo"]
# 从 15 万行全网气象数据中，只挑出站名等于 "shunyi_meo" 的行

# And now lets create a seperate Air Quality based data frame
Shunyi_aq_df = data_aq[data_aq["stationId"] == "shunyi_aq"]
# 注意这里列名是 stationId（无下划线），值的后缀是 _aq

#Lets just check we have the right data by printing the head information:
Shunyi_met_df.head()
```

**输出**：气象前 5 行，`utc_time` 现在显示为 `2017-01-30 16:00:00`（**注意格式变了**——从 `30/01/2017 16:00` 变成了 ISO 标准的 `2017-01-30 16:00:00`，这是 datetime 转换成功的又一个视觉证据）。左侧 index 仍是 0,1,2,3,4。

```python
#Same for the air quality data
Shunyi_aq_df.head()
```

**输出**：AQ 前 5 行，index 是 **195492, 195493, 195494, 195495, 195496**。

**这个输出非常值得注意**：index 不是从 0 开始，而是 19 万多！因为**布尔筛选保留了原始行号**——顺义站的数据在原始 AQ 大表里位于第 195492 行之后。这直观证明了：**默认整数 index 只是"原始行号"，筛选后就变得毫无规律，根本不能用来对齐两个表**。这正是必须换成时间索引的直接动机。

**顺序为什么重要**：老师说 "I'm going to actually extract single sites first... Then we set the index."
先筛站点、再设时间索引 → 每个时间戳在单站表里唯一。
若反过来先在全网表上设时间索引 → 同一时刻有 18 行，index 大量重复，merge 会产生笛卡尔积式爆炸。

---

### Step 7 — 设置索引（set_index）

Notebook 明确列出两步：
> *1. Set the **index** of both dataframes to be the same*
> *2. Merge both dataframes into one using this new index.*

```python
# Set the index of the meteorological dataframe to be UTC time
Shunyi_met_df.set_index('utc_time')
# What do you see below?
```

**输出**（表头结构变了）：
```
                     station_id  longitude  latitude  temperature  pressure  humidity  wind_direction  wind_speed  weather
utc_time
2017-01-30 16:00:00  shunyi_meo  116.615278 40.126667    -1.7        1028.7      15         215.0          1.6      Sunny/clear
2017-01-30 17:00:00  shunyi_meo  116.615278 40.126667    -3.5        1028.4      24          16.0          1.0      Haze
...
2018-01-31 15:00:00  shunyi_meo  116.615278 40.126667    -6.0        1024.4      42         324.0          0.3      Sunny/clear

8781 rows × 9 columns
```

**输出解读（三个关键变化）**：
1. **最左列变成了时间戳**，且左上角标出了索引名 `utc_time`；
2. **列数从 10 变成 9** —— `utc_time` 不再是普通列，它"升格"成了索引；
3. **8781 行** —— 顺义站一年的小时数据（8760 + 21，跨了 2017-01-30 到 2018-01-31）。

**⚠️ 但这行代码有个大问题**：`set_index()` **默认返回新对象，不原地修改**。这里没有赋值给任何变量，所以 `Shunyi_met_df` **实际上没有被改变**！只是在屏幕上"演示"了一下效果。详见第六节。

```python
# Now do the same for the other dataframe
Shunyi_aq_df.set_index('utc_time')
```

**输出**：
```
                     stationId  PM2.5  PM10   NO2   CO    O3   SO2
utc_time
2017-01-01 14:00:00  shunyi_aq  386.0 477.0 116.0  6.3   4.0   8.0
2017-01-01 15:00:00  shunyi_aq  410.0 476.0 121.0  6.3   4.0  10.0
...
2018-01-31 15:00:00  shunyi_aq   44.0 100.0  90.0  1.3   5.0  19.0

8886 rows × 7 columns
```

**关键对比**：

| | 起始时间 | 结束时间 | 行数 |
|---|---|---|---|
| `Shunyi_met_df` | 2017-01-30 16:00 | 2018-01-31 15:00 | **8781** |
| `Shunyi_aq_df` | 2017-01-01 14:00 | 2018-01-31 15:00 | **8886** |

→ **起点不同、行数不同**，这就是必须 inner join 的证据。

另外注意 AQ 最后几行的数值：PM2.5 = 30~45，比 2017 年元旦的 400+ 低了一个数量级 —— 2018 年 1 月底那几天空气好得多。

---

### Step 8 — 合并（merge）

```python
# Now we can combine these into a new dataframe
combined_df=pd.merge(Shunyi_met_df,Shunyi_aq_df) #, how='inner',left_index=True, right_index=True)
#   pd.merge(左表, 右表)
#   没写 on= 和 how= → 使用默认：
#     · on   = 两表所有同名列 → 这里只有 'utc_time'
#     · how  = 'inner'       → 取时间戳的交集
#   注释掉的那段是"按索引合并"的写法（因为上一步 set_index 没生效，用不了）

combined_df.head()                          # 这行输出会被后面覆盖，无实际作用
combined_df=combined_df.set_index('utc_time')  # 这次赋值了，索引真的换成了时间
combined_df.index                           # 查看索引对象
```

**输出**：
```
DatetimeIndex(['2017-01-30 16:00:00', '2017-01-30 17:00:00',
               '2017-01-30 18:00:00', '2017-01-30 19:00:00',
               '2017-01-30 20:00:00', '2017-01-30 21:00:00',
               '2017-01-30 22:00:00', '2017-01-30 23:00:00',
               '2017-01-31 00:00:00', '2017-01-31 01:00:00',
               ...
               '2018-01-31 06:00:00', '2018-01-31 07:00:00',
               '2018-01-31 08:00:00', '2018-01-31 09:00:00',
               '2018-01-31 10:00:00', '2018-01-31 11:00:00',
               '2018-01-31 12:00:00', '2018-01-31 13:00:00',
               '2018-01-31 14:00:00', '2018-01-31 15:00:00'],
              dtype='datetime64[ns]', name='utc_time', length=8220, freq=None)
```

**输出逐项解读（这是本周最重要的一段输出，务必看懂）**：

| 输出片段 | 含义 |
|---|---|
| `DatetimeIndex([...])` | **索引类型是 DatetimeIndex** ✓ —— 这才解锁 `.hour`/`.month` |
| 起点 `2017-01-30 16:00:00` | 交集起点 = 两表起点中较晚的那个（气象的起点）✓ |
| 终点 `2018-01-31 15:00:00` | 两表终点相同 ✓ |
| `dtype='datetime64[ns]'` | 底层类型正确 ✓ |
| `name='utc_time'` | 索引继承了原列名 ✓ |
| `length=8220` | **只剩 8220 行**（原本 8781 / 8886）→ inner join 丢掉了单边独有的时刻 |
| `freq=None` | Pandas **没有**推断出固定频率 → 说明时间序列**有缺口（gaps）**，不是完美的连续小时序列。若数据完美，这里会显示 `freq='h'` |

`freq=None` 是一个容易被忽略但很有价值的信号：它告诉你数据有缺测。8781 − 8220 = 561 个气象时刻没有对应的 AQ 数据。

```python
combined_df.head()
```

**输出（前 5 行，16 列）**：

| utc_time | station_id | longitude | latitude | temperature | pressure | humidity | wind_direction | wind_speed | weather | stationId | PM2.5 | PM10 | NO2 | CO | O3 | SO2 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 2017-01-30 16:00:00 | shunyi_meo | 116.615278 | 40.126667 | -1.7 | 1028.7 | 15 | 215.0 | 1.6 | Sunny/clear | shunyi_aq | 94.0 | 104.0 | 42.0 | 0.2 | 44.0 | 27.0 |
| 2017-01-30 17:00:00 | shunyi_meo | 116.615278 | 40.126667 | -3.5 | 1028.4 | 24 | 16.0 | 1.0 | Haze | shunyi_aq | 136.0 | NaN | 52.0 | 3.1 | 28.0 | 37.0 |
| 2017-01-30 18:00:00 | shunyi_meo | 116.615278 | 40.126667 | -3.7 | 1028.1 | 27 | 32.0 | 1.1 | Haze | shunyi_aq | 112.0 | NaN | 43.0 | 2.5 | 31.0 | 26.0 |
| 2017-01-30 19:00:00 | shunyi_meo | 116.615278 | 40.126667 | -3.9 | 1027.6 | 27 | 21.0 | 0.9 | Haze | shunyi_aq | 110.0 | NaN | 42.0 | 2.7 | 26.0 | 26.0 |
| 2017-01-30 20:00:00 | shunyi_meo | 116.615278 | 40.126667 | -4.1 | 1026.7 | 26 | 17.0 | 1.1 | Haze | shunyi_aq | 112.0 | NaN | 43.0 | 2.9 | NaN | 27.0 |

**输出解读**：
- **16 列 = 9（气象，去掉 utc_time）+ 7（AQ，去掉 utc_time）** ✓ 合并成功。
- 索引是时间戳，`station_id`（`shunyi_meo`）和 `stationId`（`shunyi_aq`）都保留了 —— 可以当作"这行确实来自顺义站"的确认。
- **出现了 NaN！** `PM10` 有 4 个 NaN，`O3` 有 1 个 NaN。这是真实数据的常态（仪器标定、断电、质控剔除）。**这直接引出 Exercise 4 里必须用 `np.nanmax` 而不是 `np.max` 的原因。**
- **科学解读**：16:00 时 `Sunny/clear`，PM2.5=94；17:00 起转为 `Haze`，PM2.5 跳到 136，CO 从 0.2 跳到 3.1（15 倍！）—— **傍晚边界层塌陷 + 燃烧排放累积**，霾生成的典型过程。同时 O3 从 44 降到 28 再到 26，与 NO2 上升同步 —— NO 滴定消耗臭氧。**几行数据就讲了一个完整的大气化学故事。**

---

### Exercise 3 — 画 PM2.5 的日变化箱线图（全年 vs 八月）

**题目**：
> *Now that you have a new dataframe with a datetime index, we can plot diurnal profiles of entire columns with only one line of code! ... Your challenge is to populate the right-hand plot, which is currently empty, with data on PM2.5 for **August**.*
>
> 提示：*"if I wanted to specify the month of March in a conditional statement I would write: `combined_df.index.month == 3`"*

**给定的模板**：
```python
import seaborn as sns
import matplotlib.pyplot as plt
fig, axes = plt.subplots(figsize=(8,8))
sns.boxplot(data=combined_df, x=combined_df.index.hour, y=combined_df['PM2.5'], ax=axes)
```

Notebook 对模板的解释：
> *"Remember that we can access properties of our dataframe using the `.` operator? Now that we have specified the index to be in the datetime format, we can access the `.index` of our dataframe and then the `.hour` of that index. Behind the scenes, Pandas can pass the data for our `y` variable of interest, `combined_df['PM2.5']`, to the Seaborn box-plotting function."*

**解题思路**：
1. 用 `plt.subplots(1, 2, ...)` 建两个并排子图；
2. 左图：全年数据；
3. 右图：用布尔条件 `combined_df.index.month == 8` 筛出八月的数据 —— **注意 `data=`、`x=`、`y=` 三处都要筛，否则长度不一致会报错**；
4. 统一两图 y 轴范围以便公平比较；
5. 加标题和轴标签。

**完整代码**：
```python
import seaborn as sns
import matplotlib.pyplot as plt

#------'INSERT CODE HERE'------
fig, axes = plt.subplots(1,2,figsize=(12,8))
#   1 行 2 列的子图网格；figsize 单位是英寸 (宽 12, 高 8)
#   axes 现在是一个长度为 2 的数组：axes[0] 左图, axes[1] 右图

sns.boxplot(data=combined_df,
            x=combined_df.index.hour,      # x 轴 = 每行的「小时」(0-23)，DatetimeIndex 属性
            y=combined_df['PM2.5'],        # y 轴 = PM2.5 浓度列
            ax=axes[0]                     # 画到左边那个子图
           ).set(xlabel='Hour of day', ylabel='Abundance')
#   sns.boxplot 会自动按 x 的每个取值（0~23）分组，各画一个箱子
#   .set(...) 链式设置轴标签（boxplot 返回的是 Axes 对象）

sns.boxplot(data=combined_df[combined_df.index.month == 8],
            #   ↑ 只保留 index 月份 == 8 的行（八月）
            x=combined_df[combined_df.index.month == 8].index.hour,
            #   ↑ x 也必须用「筛过之后」的数据取 .hour，长度才能对上
            y=combined_df[combined_df.index.month == 8]['PM2.5'],
            #   ↑ y 同理
            ax=axes[1]
           ).set(xlabel='Hour of day', ylabel='Abundance')

axes[0].set_ylim([0,100])       # 统一 y 轴范围，否则两图无法直接目视比较
axes[1].set_ylim([0,100])       # 同时也把极端离群点裁掉，让箱体看得清
axes[0].set_title('All year')
axes[1].set_title('August')
#------------------------------
```

**输出**：
```
Text(0.5, 1.0, 'August')
```
加上一张 1×2 的箱线图。

**输出解读**：
- `Text(0.5, 1.0, 'August')` 是 `set_title()` 的返回值（一个 matplotlib Text 对象，坐标 (0.5, 1.0) 表示位于子图顶部居中）—— **不是报错**。
- 图的判读：
  - 每个箱子代表一个整点小时（0–23）在全年/八月所有天数上的 PM2.5 分布；
  - **中位线普遍偏箱体下方** → PM2.5 分布强烈右偏（多数时候中等，偶尔极高）；
  - 箱体上方大量离群点 → 重污染事件；
  - 全年图整体浓度水平高于八月图 → **夏季空气好**（降水冲刷、边界层高、无供暖燃煤）；
  - 日变化幅度不算剧烈——PM2.5 有较长的大气寿命且区域输送为主，不像 NO2 那样紧跟交通高峰。

**为什么这个练习重要**：它同时练了三件事——**DatetimeIndex 属性取值**、**布尔条件筛选**、**多子图对比绘图**。老师说 "So I can chain together multiple things here, depending on what questions you're trying to answer."

**可以自己延伸的变体**（老师明确鼓励）：
```python
x=combined_df.index.weekday     # 改成看周内变化（周末 vs 工作日）
x=combined_df.index.month       # 改成看季节变化
combined_df.index.month == 12   # 换成十二月（供暖季），对比会更震撼
y=combined_df['NO2']            # 换成 NO2，应该能看出早晚高峰双峰
```

**代码可以更简洁**（避免重复写三遍筛选表达式）：
```python
aug = combined_df[combined_df.index.month == 8]      # 先存成变量
sns.boxplot(data=aug, x=aug.index.hour, y=aug['PM2.5'], ax=axes[1])
```

---

### Exercise 4 — 为 pingchang 站建新 DataFrame，求各污染物最大值，并画 PM2.5/PM10 日变化

**题目**：
> *Combine the operations above and merge the meteorology and air quality existing datasets into a new one for the station **Pingchang**. Once you have done that, access a preview, and also **calculate the maximum and minimum of each air quality variable using the relevant NumPy functions**. Your results should confirm:*
> - PM2.5 = 522.0, PM10 = 1010.0, NO2 = 154.0, CO = 6.4, O3 = 378.0, SO2 = 300.0
>
> *Following this, produce a diurnal plot for PM2.5 and PM10 side-by-side. You may find you need to change the scales of each graph to make for easier comparison.*
>
> **警告框**：*"If the results from your maximum calculation all produce a 'NaN' (Not-a-Number), this means your columns have NaN values. In this case, let us assume you do not want to investigate those but simply ignore them. In this case you can use `numpy.nanmax`."*

**解题思路**：把 Step 6 → 7 → 8 的整套流程对 `pingchang` 站重做一遍，然后用 `np.nanmax` 求最大值，最后画两张日变化箱线图。

**完整代码**：
```python
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

#------'INSERT CODE HERE'------
# ① 按站点拆分（注意后缀：气象 _meo，空气质量 _aq）
pingchang_met_df = data_meteo[data_meteo["station_id"] == "pingchang_meo"]
pingchang_aq_df  = data_aq[data_aq["stationId"] == "pingchang_aq"]

# ② 设索引（⚠️ 这两行同样没有赋值，实际不生效，只是"演示"——见第六节）
pingchang_met_df.set_index('utc_time')
pingchang_aq_df.set_index('utc_time')

# ③ 合并：默认按同名列 'utc_time' 做 inner join
#combined_df_new=pd.merge(pingchang_met_df,pingchang_aq_df,on='utc_time')   # 显式写法（更好）
combined_df_new=pd.merge(pingchang_met_df,pingchang_aq_df)
combined_df_new.head()

# ④ 这一步才是真正把索引换成时间（有赋值）
combined_df_new=combined_df_new.set_index('utc_time')
combined_df_new.head()

# ⑤ 求各污染物最大值
#    .values 把 Series 转成 NumPy 数组；np.nanmax 忽略 NaN 求最大
PM25 = np.nanmax(combined_df_new["PM2.5"].values)
PM10 = np.nanmax(combined_df_new["PM10"].values)
NO2  = np.nanmax(combined_df_new["NO2"].values)
CO   = np.nanmax(combined_df_new["CO"].values)
O3   = np.nanmax(combined_df_new["O3"].values)
SO2  = np.nanmax(combined_df_new["SO2"].values)

print("Max value for PM2.5 = ",PM25)
print("Max value for PM10 = ",PM10)
print("Max value for NO2 = ",NO2)
print("Max value for CO = ",CO)
print("Max value for O3 = ",O3)
print("Max value for SO2 = ",SO2)

# ⑥ 并排画 PM2.5 与 PM10 的日变化箱线图
fig, axes = plt.subplots(1,2,figsize=(12,8))
sns.boxplot(data=combined_df,                       # ⚠️ 这里传的是旧的 combined_df（Shunyi），是笔误
            x=combined_df_new.index.hour,           # 但 x 和 y 都显式给了 pingchang 的数据
            y=combined_df_new['PM2.5'],             # 所以画出来的其实是 pingchang 的图 —— 见第六节
            ax=axes[0]).set(xlabel='Hour of day',ylabel='Abundance')
sns.boxplot(data=combined_df,
            x=combined_df_new.index.hour,
            y=combined_df_new['PM10'],
            ax=axes[1]).set(xlabel='Hour of day',ylabel='Abundance')
axes[0].set_ylim([0,100])       # PM2.5 量程小
axes[1].set_ylim([0,200])       # PM10 量程大（因为 PM10 ⊇ PM2.5）
axes[0].set_title('PM2.5')
axes[1].set_title('PM10')
#------------------------------
```

**输出**：
```
Max value for PM2.5 =  522.0
Max value for PM10 =  1010.0
Max value for NO2 =  154.0
Max value for CO =  6.4
Max value for O3 =  378.0
Max value for SO2 =  300.0

Text(0.5, 1.0, 'PM10')
```
加上一张 1×2 箱线图。

**如何判断结果正确**：题目已经给了标准答案，六个数字**逐一对上**即为正确。如果全是 `nan`，说明你用了 `np.max` 而非 `np.nanmax`；如果数字对不上，说明站点名写错或者合并出了问题。

**输出的科学解读（这些数字都很有故事）**：

| 变量 | 最大值 | 科学含义 |
|---|---|---|
| PM2.5 | **522 µg/m³** | WHO 24h 指导值 15 µg/m³ 的 **35 倍**；中国 AQI 严重污染（>250）。极端霾事件。 |
| PM10 | **1010 µg/m³** | 破千！PM10 ≫ PM2.5 说明这次是**粗颗粒主导**——很可能是**沙尘暴（dust storm）**，北京春季（3–5 月）受蒙古/内蒙沙源影响的典型现象。这与 PM2.5 峰值大概率不是同一天。 |
| NO2 | 154 µg/m³ | 交通/燃烧源峰值。 |
| CO | 6.4 mg/m³ | 重污染时的燃烧源累积。 |
| O3 | **378 µg/m³** | 极高！夏季午后光化学臭氧污染事件（中国一级标准 1 小时值 160 µg/m³）。与 PM 峰值出现在**完全不同的季节**。 |
| SO2 | 300 µg/m³ | 冬季燃煤高值。中国这些年 SO2 治理成效显著，2017 年仍有这样的峰值。 |

**关键洞察**：`nanmax` 只给出"最坏时刻"，不同污染物的最坏时刻在**不同季节、不同成因**。这也说明为什么要看**分布（箱线图）** 而不只看极值。

**箱线图判读**：PM2.5 和 PM10 的日变化形态高度相似（因为二者 r ≈ 0.84），但 PM10 数值约为 PM2.5 的 2 倍，所以 y 轴分别设成 [0,100] 和 [0,200] 才能让两图的"箱子"占据相似的视觉高度，便于比较**形状**而非绝对值。

---

### Step 9 — 相关系数矩阵（Part 3 示范）

Notebook 给的两步模板：
```python
dataframe[['column 1','column 2','column 3'...etc]]   # ① 选出感兴趣的数值列（双层方括号）
.corr()                                                # ② 求相关矩阵
```

```python
corr = combined_df[['temperature','pressure','humidity','PM2.5','PM10','NO2','CO','O3','SO2']].corr()
#   双层方括号 [[...]] → 选取 9 列，返回一个 DataFrame（不是 Series）
#   .corr()            → 返回 9×9 的 Pearson 相关矩阵，本身也是一个 DataFrame
#   注意：故意没有选 'weather'（字符串）和 'station_id'（字符串），也没选经纬度（常数，无变化）
print("Correlation coefficient matrix = ", corr)
```

**输出**（已在第三节 3.3 完整给出并逐条解读）。

**如何自检**：
1. **对角线全为 1.000000** ✓
2. **矩阵关于对角线对称**（如 r(temperature, PM2.5) = r(PM2.5, temperature) = 0.041147）✓
3. 所有值在 [−1, 1] 内 ✓
4. 物理常识检查：temperature–pressure 应强负相关（−0.86 ✓），PM2.5–PM10 应强正相关（0.84 ✓）。

**输出格式的小坑**：因为有 9 列，Pandas 打印时会**换行折断**——先打印前 6 列，再打印剩下 3 列（`CO`, `O3`, `SO2`）。看输出时不要以为是两个矩阵。

---

### Step 10 — 相关系数热力图（heatmap）

Notebook 引用 Seaborn 官方定义：
> *"Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics."*

```python
import matplotlib.pyplot as plt
import seaborn as sns
# calculate the correlation matrix
corr = combined_df[['temperature','pressure','humidity','wind_direction','wind_speed',
                    'PM2.5','PM10','NO2','CO','O3','SO2']].corr()
#   注意：这次比上一步多加了 wind_direction 和 wind_speed，共 11 列 → 11×11 矩阵

# Now use an internal function within Seaborn called '.heatmap'
sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns)
#   第一个参数：要画的二维矩阵（这里是相关矩阵 DataFrame）
#   xticklabels / yticklabels：指定坐标轴刻度标签
#       用 corr.columns 保证标签顺序和矩阵行列顺序完全一致（不会错位）
#       其实 Seaborn 对 DataFrame 会自动用列名，这里是显式写出来更保险/更教学

# And we now need to show the plot.
plt.show()
#   在脚本里必须调用才会弹图；在 Jupyter 里可省略，但写上能抑制多余的对象输出
```

**输出**：一张 11×11 的彩色方阵图。

**判读要点**：
- **对角线是一条完整的最亮/最热的线（全 1）** ← 第一眼就该看这个，它证明图画对了；
- 图关于对角线对称；
- 右侧色条（colorbar）给出颜色↔数值的对应；
- 找"热点"：temperature–pressure 那个格子应该是最"冷"（最负），PM2.5–PM10 应该很"热"。

老师原话：*"the hotter the cell, the higher the correlation between meteorological factors and pollution factors. So we can start to understand the relationships inherent in the data."*

**注意 `wind_direction` 这一列的相关系数意义有限**：风向是**角度型（circular）数据**，0° 和 359° 其实几乎相同，但 Pearson 相关系数会把它们当成天差地别的两个数。而且数据里还有 `999017.0` 这种明显的缺测标记（见第六节）。所以这一行/列的数值**不要过度解读**。

---

### Exercise 5 — 为 pingchang 站画相关系数热力图

**题目**：
> *Replicate the procedures given above for your new merged dataframe created in Exercise 4.*

**解题思路**：把 Step 10 的代码里的 `combined_df` 换成 `combined_df_new` 即可。

**代码**：
```python
import matplotlib.pyplot as plt
import seaborn as sns
# calculate the correlation matrix

#------'INSERT CODE HERE'------
corr_new = combined_df_new[['temperature','pressure','humidity','wind_direction','wind_speed',
                            'PM2.5','PM10','NO2','CO','O3','SO2']].corr()
#   唯一改动：数据源换成 Exercise 4 建的 pingchang 合并表
#   变量也改名成 corr_new，避免覆盖前面 Shunyi 的 corr（好习惯）

# Now use an internal function within Seaborn called '.heatmap'
sns.heatmap(corr_new, xticklabels=corr_new.columns, yticklabels=corr_new.columns)
#------------------------------

# And we now need to show the plot.
plt.show()
```

**输出**：pingchang 站的 11×11 热力图。

**输出解读**：形态应与 Shunyi 站高度相似（同一个城市、同样的气象-污染耦合机制）。**如果两站的热力图差别巨大，那多半是代码出错而非科学发现**——这是一个很好的"用领域知识验证代码"的例子。

---

### Step 11 — Pair plot（配对图）

```python
# Create the default pairplot
sns.pairplot(combined_df[['temperature','pressure','humidity','PM2.5','PM10','NO2','CO','O3','SO2']].dropna())
#   选 9 列 → 会生成 9×9 = 81 个子图
#   .dropna() 必须加：只要一行里任一列是 NaN，整行删掉
#             因为散点图需要成对的 (x, y) 值，缺一个就画不了
```

Notebook 解释：
> *"To make this easier to visualise let's focus on 9 variables and also apply the `.dropna()` extension to our dataframe to remove `NaN` entries. An entry of `NaN` can often arise through errors in processing and literally means '**Not-a-Number**'."*

**输出（含警告）**：
```
/Users/user/opt/anaconda3/envs/DEES_python/lib/python3.12/site-packages/seaborn/_oldcore.py:1119:
FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version.
Convert inf values to NaN before operating instead.
  with pd.option_context('mode.use_inf_as_na', True):
（这段重复出现 9 次）

<seaborn.axisgrid.PairGrid at 0x1693c3170>
```
加上一张 9×9 的散点矩阵图。

**输出解读（三部分都要看懂）**：

1. **`FutureWarning` 不是错误！** 这是 Seaborn 内部调用了 Pandas 一个**即将废弃（deprecated）** 的选项 `use_inf_as_na` 而触发的警告。它来自**库自己的代码**（路径里是 `seaborn/_oldcore.py`），**不是我们写错了**，也不影响结果。重复 9 次是因为 pairplot 对 9 个变量各调用了一次。
   - **处理方式**：升级 Seaborn 版本，或用 `import warnings; warnings.filterwarnings('ignore', category=FutureWarning)` 屏蔽。但在学习阶段，**看懂警告说了什么比屏蔽它更重要**。
   - **Warning vs Error 的区别**：Warning → 代码继续跑，只是提醒；Error（Exception）→ 代码中断。

2. **`<seaborn.axisgrid.PairGrid at 0x1693c3170>`** 是 pairplot 的返回值（PairGrid 对象及其内存地址），同样不是报错。

3. **图本身**：
   - **对角线**：每个变量自身的**单变量分布**（默认是直方图/KDE）；
   - **非对角线 (i, j)**：变量 i 对变量 j 的**散点图**；
   - 图关于对角线镜像对称（只是 x/y 互换）；
   - 看点：PM2.5 vs PM10 应呈明显的正斜率条带；temperature vs pressure 应呈负斜率条带；temperature vs PM2.5 应是一团散乱的云（对应 r=0.04）。

老师评价：*"look at the relationship between each column and its other partners... This can become quite a complex figure to look at, but it's another option."*

**实用提醒**：pairplot 计算量是 O(n²)，9 列已经要跑一会儿；**别对 20 列的表直接跑 pairplot**，会卡死。

---

### Step 12 — 多污染物箱线图（Pandas 内建）

```python
combined_df_new[['PM2.5','PM10','NO2','CO','O3','SO2']].boxplot(column=['PM2.5','PM10','NO2','CO','O3','SO2'])
#   先选 6 个污染物列，再对这些列各画一个箱子
#   注意这次 x 轴是「不同污染物」，不是「小时」——和前面 Seaborn 的日变化图用途完全不同
```

**输出**：
```
<Axes: >
```
加一张图。

**输出解读**：`<Axes: >` 是返回的 matplotlib Axes 对象，不是报错。
图的问题：**PM10 的量级（可达 1010）把其他所有变量压扁成贴地的一条线** —— CO 的值只有个位数，在同一个线性 y 轴上根本看不见。这就引出下一步。

```python
combined_df_new[['PM2.5','PM10','NO2','CO','O3','SO2']].boxplot(
    column=['PM2.5','PM10','NO2','CO','O3','SO2'],figsize=(12,12)).set_yscale('log')
#   figsize=(12,12)      → 图变大，标签不挤
#   .set_yscale('log')   → y 轴改成对数刻度
#      .boxplot() 返回 Axes → 直接链式调用 Axes 的 set_yscale 方法
```

**输出**：一张对数 y 轴的箱线图（没有额外文本输出，因为 `set_yscale` 返回 None）。

**为什么用对数轴**：六种污染物跨越约 **3 个数量级**（CO ~ 0.1–6.4 mg/m³ vs PM10 ~ 1–1010 µg/m³，且单位还不同）。对数轴让每个变量的**相对变化幅度**都能看清。

**对数轴的陷阱**：`log(0)` 和 `log(负数)` 无定义 → 值为 0 或负的数据点会被**静默丢弃**（图上直接不显示）。用对数轴前应确认数据是否有 0 值。

---

### Notebook 结尾的总结（What We Did）

> - Used **Pandas** to load time-series data from a spreadsheet
> - Worked with **dates and time** as part of a dataset
> - Explored the structure of the data to understand: what each column represents; how values change over time
> - Used Pandas tools to calculate **basic statistical quantities**: Mean, Minimum and maximum values, Standard deviation
> - Applied these statistics to real data to summarise trends and variability
> - Created plots to visualise how values evolve through time
> - Began **interpreting numerical summaries alongside graphical output**

> *The focus was on using statistics to describe real datasets, and understanding how numerical summaries and plots complement each other.*

（注：这段自动生成的总结里提到的"Mean / Standard deviation"在 Notebook 正文中并没有单独练习，但 `df.describe()`、`df.mean()`、`df.std()` 是很自然的延伸，值得自己补练。）

---

## 六、易错点 / 重点难点

### ⚠️ 陷阱 1：`set_index()` 默认不原地修改 —— 本 Notebook 里真实存在的"无效代码"

**问题代码**（Notebook 里出现了 4 次）：
```python
Shunyi_met_df.set_index('utc_time')      # ← 没有赋值！
Shunyi_aq_df.set_index('utc_time')       # ← 没有赋值！
pingchang_met_df.set_index('utc_time')   # ← 没有赋值！
pingchang_aq_df.set_index('utc_time')    # ← 没有赋值！
```

**发生了什么**：`set_index()` 返回一个**新的 DataFrame**，原变量**完全不变**。这几行只是在 Jupyter 里"显示"了一下设完索引长什么样，然后那个新对象就被丢弃了。

**为什么代码还能跑通**：因为紧接着的 `pd.merge(Shunyi_met_df, Shunyi_aq_df)` **不是按索引合并的，而是按同名列 `utc_time` 合并的**。`utc_time` 作为普通列还在两个表里，所以 merge 照常工作。真正让索引变成时间的，是后面**有赋值**的那一行：
```python
combined_df = combined_df.set_index('utc_time')    # ← 这行才真正生效
```

**正确写法（两种）**：
```python
Shunyi_met_df = Shunyi_met_df.set_index('utc_time')     # 赋值回去（推荐）
Shunyi_met_df.set_index('utc_time', inplace=True)       # 或用 inplace=True
```

**这个坑的通用规律**：Pandas **绝大多数方法都返回新对象、不修改原对象**。同样的坑适用于 `.dropna()`、`.rename()`、`.sort_values()`、`.reset_index()`、`.fillna()`、`.drop()`……**看到方法调用结果没被接住，就要警觉。**

**记忆口诀**：*Pandas 方法是"生孩子"不是"整容"——不接住就白生了。*

---

### ⚠️ 陷阱 2：`pd.merge()` 默认按**所有同名列**合并 —— 这次是运气好

**本例为什么安全**：气象表用 `station_id`、AQ 表用 `stationId`，**列名不同** → 唯一同名列只有 `utc_time` → 正好按时间合并。

**如果两个表的站点列都叫 `station_id` 会怎样**：merge 会同时按 `station_id` **和** `utc_time` 合并。而 `shunyi_meo ≠ shunyi_aq`（值不同），结果就是**合并出 0 行的空 DataFrame**！这时你会莫名其妙地得到一个空表，且不会有任何报错。

**防御性写法（强烈推荐）**：
```python
combined_df = pd.merge(Shunyi_met_df, Shunyi_aq_df, on='utc_time', how='inner')
#   on='utc_time'  → 明确指定合并键，杜绝意外
#   how='inner'    → 明确指定连接方式
print(combined_df.shape)    # 合并后立刻检查行数，0 行说明键对不上
```

**`how` 参数的四种取值**：

| how | 含义 | 结果行数 |
|---|---|---|
| `'inner'`（默认） | 只保留**两边都有**的键 | 交集，可能变少 |
| `'outer'` | 保留**任一边有**的键，缺的填 NaN | 并集，可能变多 |
| `'left'` | 以左表键为准 | = 左表行数 |
| `'right'` | 以右表键为准 | = 右表行数 |

本周科学上应该用 `inner`：**只有两边都有观测的时刻，相关分析才有意义。**

**合并后必查的三件事**：
```python
print(combined_df.shape)        # 行数是否合理？0 行 = 键对不上；行数暴增 = 键有重复值（笛卡尔积）
print(combined_df.index)        # 索引类型对不对？
print(combined_df.columns)      # 有没有出现 _x / _y 后缀？有的话说明有同名非键列被自动改名了
```

---

### ⚠️ 陷阱 3：`np.max` 遇到 NaN 返回 NaN —— Notebook 专门警告的坑

Notebook 原文警告框：
> *"If the results from your maximum calculation all produce a 'NaN' (Not-a-Number), this means your columns have NaN values. In this case, let us assume you do not want to investigate those but simply ignore them. In this case you can use `numpy.nanmax`."*

**演示**：
```python
import numpy as np
a = np.array([1.0, 2.0, np.nan, 4.0])
np.max(a)       # → nan       ← NaN 有"传染性"，任何和它的比较都是 False
np.nanmax(a)    # → 4.0       ← 正确
```

**为什么会这样**：NaN 的定义是"与任何数（包括自己）比较都返回 False"，所以逐元素求最大时它会"污染"整个结果。

**NaN 家族的完整对照表**：

| 会被 NaN 污染 | 忽略 NaN 的版本 | Pandas 的行为 |
|---|---|---|
| `np.max()` | `np.nanmax()` | `Series.max()` **默认就忽略 NaN** |
| `np.min()` | `np.nanmin()` | `Series.min()` 默认忽略 |
| `np.mean()` | `np.nanmean()` | `Series.mean()` 默认忽略 |
| `np.std()` | `np.nanstd()` | `Series.std()` 默认忽略 |
| `np.sum()` | `np.nansum()` | `Series.sum()` 默认忽略 |

**关键区别**：**NumPy 默认被 NaN 污染，Pandas 默认忽略 NaN。** 所以下面两行结果不同：
```python
np.max(combined_df_new["PM2.5"].values)   # → 可能是 nan（先 .values 转成裸 NumPy 数组了）
combined_df_new["PM2.5"].max()            # → 522.0（Pandas 方法，自动跳过 NaN）
```
Notebook 用的是前一种写法 + `nanmax`，是为了强调 Pandas↔NumPy 的衔接。日常用 Pandas 自己的 `.max()` 更省心。

---

### ⚠️ 陷阱 4：忘记把 `pd.to_datetime()` 的结果赋值回去

```python
pd.to_datetime(data_aq['utc_time'], format='mixed')   # ✗ 结果丢弃，原列还是 object
data_aq['utc_time'] = pd.to_datetime(...)             # ✓ 正确
```

**症状**：后面调用 `df.index.hour` 时报
```
AttributeError: 'Index' object has no attribute 'hour'
```
或 `'RangeIndex' object has no attribute 'hour'`。

**诊断三步**：
```python
df.dtypes           # utc_time 是不是 datetime64[ns]？
df.index            # 是不是 DatetimeIndex？（不是就说明 set_index 没生效或没转类型）
type(df.index)      # 明确看类型
```

---

### ⚠️ 陷阱 5：DD/MM/YYYY vs MM/DD/YYYY —— 日期解析的经典灾难

原始数据是 `"30/01/2017 16:00"`，这是**英式的 DD/MM/YYYY**。

- `30` 不可能是月份 → Pandas 能正确推断为 2017 年 1 月 30 日 ✓
- 但如果某一行是 `"05/01/2017"`，**歧义！** 可能是 1 月 5 日（英式）也可能是 5 月 1 日（美式）。

`format='mixed'` 会**逐行推断**，可能导致**同一列里不同行用了不同的解析规则**——这是隐蔽而致命的数据错误。

**安全做法（推荐）**：
```python
# 已知格式固定时，显式指定，既快又零歧义
data_aq['utc_time'] = pd.to_datetime(data_aq['utc_time'], format='%d/%m/%Y %H:%M')

# 或者至少告诉 Pandas 日在前
data_aq['utc_time'] = pd.to_datetime(data_aq['utc_time'], dayfirst=True)
```

**常见 format 指令**：`%d` 日、`%m` 月、`%Y` 四位年、`%y` 两位年、`%H` 24 小时制时、`%M` 分、`%S` 秒。

**验证方法**：转换后 `df['utc_time'].min()` 和 `.max()` 看起止时间是否合理；再看 `df['utc_time'].dt.month.value_counts()`，如果月份分布怪异（比如只有 1–12 号出现在某些月），说明解析错了。

---

### ⚠️ 陷阱 6：`=` 与 `==` 混淆

Notebook 专门强调：
> *"Just to re-iterate an important point on use of the equals sign. When we are checking a value is true, we use two equal signs `==` rather than one `=` when assigning a value to a variable."*

```python
data_meteo[data_meteo["station_id"] == "shunyi_meo"]   # ✓ 比较
data_meteo[data_meteo["station_id"] = "shunyi_meo"]    # ✗ SyntaxError: invalid syntax
```

**报错**：`SyntaxError: invalid syntax`（因为函数/索引调用里不能做赋值）。

---

### ⚠️ 陷阱 7：Exercise 4 里 `data=combined_df` 与 `x/y=combined_df_new` 不一致

```python
sns.boxplot(data=combined_df,                 # ← 旧的 Shunyi 表
            x=combined_df_new.index.hour,     # ← 新的 pingchang 数据
            y=combined_df_new['PM2.5'],       # ← 新的 pingchang 数据
            ax=axes[0])
```

**为什么不报错**：当 `x` 和 `y` 直接传入**实际的数组/Series** 而非列名字符串时，Seaborn 就用传进来的数据，`data=` 参数被**完全忽略**。所以画出来的确实是 pingchang 的图 —— 结果碰巧是对的。

**但这是坏代码**，因为：
- 读代码的人会以为画的是 `combined_df`（Shunyi）；
- 如果哪天改成 `x='hour'`（字符串），Seaborn 就会去 `data=combined_df` 里找列，画出完全错误的图，而且不会报错。

**正确写法**：
```python
sns.boxplot(data=combined_df_new, x=combined_df_new.index.hour,
            y=combined_df_new['PM2.5'], ax=axes[0])
```

**教训**：**`data=` 和 `x=`/`y=` 必须来自同一个 DataFrame。** 这类"能跑但语义错"的 bug 比报错更危险，因为没有任何提示。

---

### ⚠️ 陷阱 8：变量名 `path` 覆盖了模块 `path`

```python
from os import path      # 导入 os.path 模块，绑定到名字 path
path = os.getcwd()       # ← 立刻把 path 覆盖成一个字符串！
```

后面 `path+"/data/..."` 能工作是因为它现在是字符串。但如果你想用 `path.join(...)`，就会报
```
AttributeError: 'str' object has no attribute 'join'
```
（实际上字符串有 `join`，会得到诡异的结果，更难 debug）

**正确做法**：
```python
import os
data_dir = os.getcwd()                                  # 用不冲突的变量名
csv_file = os.path.join(data_dir, "data", "beijing_17_18_meo.csv")   # 跨平台安全的路径拼接
data_meteo = pd.read_csv(csv_file)
```
`os.path.join()` 会自动用正确的分隔符（Windows 用 `\`，Linux/Mac 用 `/`），比字符串 `+` 更健壮。

---

### ⚠️ 陷阱 9：布尔筛选后可能触发 `SettingWithCopyWarning`

```python
Shunyi_met_df = data_meteo[data_meteo["station_id"] == "shunyi_meo"]
Shunyi_met_df['new_col'] = 1        # ← 可能触发 SettingWithCopyWarning
```

**报警内容**：
```
SettingWithCopyWarning: A value is trying to be set on a copy of a slice from a DataFrame.
Try using .loc[row_indexer,col_indexer] = value instead
```

**原因**：布尔筛选返回的对象可能是原表的**视图（view）** 也可能是**副本（copy）**，Pandas 自己也不确定，所以修改它时会警告"你的修改可能没有落到你以为的地方"。

**解决**：筛选时显式复制
```python
Shunyi_met_df = data_meteo[data_meteo["station_id"] == "shunyi_meo"].copy()
```

本 Notebook 里没有对筛选结果赋新列，所以没触发；但一旦你自己做数据清洗就会遇到。

---

### ⚠️ 陷阱 10：`FutureWarning` / `DeprecationWarning` 不是你的错

```
FutureWarning: use_inf_as_na option is deprecated and will be removed in a future version.
Convert inf values to NaN before operating instead.
  with pd.option_context('mode.use_inf_as_na', True):
```

**读懂警告的方法**：看**文件路径**。这里是 `site-packages/seaborn/_oldcore.py` —— 在**第三方库内部**，不是你的 Notebook。说明是 Seaborn 版本与 Pandas 版本不匹配，Seaborn 用了 Pandas 即将删掉的功能。

**Warning 的三种常见类型**：

| 类型 | 含义 | 要不要管 |
|---|---|---|
| `FutureWarning` | 这个用法未来会改 | 若在你的代码里，应尽早改；在库里，等库升级 |
| `DeprecationWarning` | 这个功能已废弃 | 同上 |
| `SettingWithCopyWarning` | 你的赋值可能没生效 | **必须管**，这通常是真 bug |
| `RuntimeWarning` | 数值计算异常（除零、log 负数等） | **必须管** |

**关键区分：Warning ≠ Error**
- **Warning**：程序继续运行，只是打印一条提示；
- **Error / Exception**（如 `KeyError`、`AttributeError`、`ValueError`）：程序**中断**，后面代码不执行。

---

### ⚠️ 陷阱 11：数据里的伪装缺测值 —— `wind_direction = 999017.0`

在 Step 7 的输出里，2018-01-31 13:00 那一行：
```
2018-01-31 13:00:00  shunyi_meo  ...  39   999017.0   0.2   Sunny/clear
```

风向是 **999017 度**！物理上不可能（风向只能是 0–360°）。

**这是什么**：很多观测仪器用一个**极端数值（如 999、9999、-9999、999017）当作"缺测/无效"的标记**，而不是留空。Pandas 读进来时会把它当成一个正常的浮点数，**不会变成 NaN，也不会有任何警告**。

**危害**：一个 999017 混在一堆 0–360 的数里，会把这一列的 `mean`、`std`、`corr` 全部毁掉。这就是老师说的 *"garbage in, garbage out"* 的具体形态。

**如何发现**：
```python
combined_df['wind_direction'].describe()          # 看 max/min 是否离谱
combined_df['wind_direction'].max()               # 999017.0 → 立刻警觉
combined_df[combined_df['wind_direction'] > 360]  # 找出所有异常行
```

**如何处理**：
```python
import numpy as np
combined_df.loc[combined_df['wind_direction'] > 360, 'wind_direction'] = np.nan
# 把不合物理的值替换成 NaN，后续统计会自动跳过
```

**这是本周材料里最有价值但最容易被略过的一个细节** —— 数据清洗（data cleaning）不只是处理 NaN，还包括**识别伪装成正常数值的缺测标记**。老师课上反复强调的"数据清洗比模型更重要"，说的就是这类事。

---

### ⚠️ 陷阱 12：Jupyter 只显示 cell 里最后一个表达式

Notebook 里多处出现：
```python
data_meteo.head()     # 这行的结果看不到
data_meteo.head()     # 只有这行会显示
```
以及
```python
combined_df.head()                              # 看不到
combined_df=combined_df.set_index('utc_time')   # 赋值语句本身无输出
combined_df.index                               # 只有这行显示
```

**规则**：Jupyter 只会自动渲染 **cell 中最后一个"表达式语句"** 的值。赋值语句（`a = b`）不是表达式，不产生输出。

**想显示多个**：用 `print()` 或 `display()`
```python
from IPython.display import display
display(df1.head())
display(df2.head())
```

---

### 难点总结：本周流程的正确顺序（背下来）

```python
# ① 读入两个 CSV
df_a = pd.read_csv('a.csv')
df_b = pd.read_csv('b.csv')

# ② 把时间列转成 datetime（记得赋值回去！）
df_a['utc_time'] = pd.to_datetime(df_a['utc_time'], format='mixed')
df_b['utc_time'] = pd.to_datetime(df_b['utc_time'], format='mixed')

# ③ 先筛出单个站点（顺序很重要！否则索引会重复）
a1 = df_a[df_a['station_id'] == 'xxx_meo'].copy()
b1 = df_b[df_b['stationId']  == 'xxx_aq'].copy()

# ④ 合并（显式指定 on 和 how）
merged = pd.merge(a1, b1, on='utc_time', how='inner')

# ⑤ 设时间索引（记得赋值回去！）
merged = merged.set_index('utc_time')

# ⑥ 检查：类型、长度、起止
print(merged.index)          # 应看到 DatetimeIndex + datetime64[ns]
print(merged.shape)

# ⑦ 分析与绘图
sns.boxplot(data=merged, x=merged.index.hour, y=merged['PM2.5'])
corr = merged[[数值列...]].corr()
sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns)
```

**四个"必须赋值"的位置**：`to_datetime`（×2）、`set_index`、`merge`。
**三个"必须检查"的位置**：`dtypes`（转换后）、`index`（设索引后）、`shape`（合并后）。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| index | 索引 / 行标签 | DataFrame 中每一行的标签；默认是 0,1,2… 的整数，本周把它换成时间戳 |
| label | 标签 | 列名或行索引值的统称 |
| `DatetimeIndex` | 日期时间索引 | 元素为 Timestamp 的索引对象，支持 `.hour`/`.month`/`.weekday` 等时间属性 |
| `datetime64[ns]` | 纳秒精度日期时间类型 | Pandas/NumPy 存储时间的底层 dtype，本质是距 1970-01-01 的纳秒数 |
| `Timestamp` | 时间戳 | Pandas 表示"某一具体时刻"的对象 |
| `object` (dtype) | 对象类型 | Pandas 对字符串/混杂类型列的统称；时间列未转换前就是这个类型 |
| `pd.to_datetime()` | 转日期时间 | 把字符串列解析成 `datetime64[ns]` |
| `set_index()` | 设置索引 | 把某一列提升为行索引；**默认返回新对象** |
| `reset_index()` | 重置索引 | 把索引降回普通列，恢复整数索引（本周未用但常配套） |
| merge | 合并 / 连接 | 按共同的键把两个表横向拼在一起 |
| join key / `on` | 连接键 | 用来匹配两表行的列（本周是 `utc_time`） |
| inner join | 内连接 | 只保留两表**都有**的键值（取交集）——本周默认行为 |
| outer join | 外连接 | 保留两表**任一有**的键值（取并集），缺失补 NaN |
| left / right join | 左 / 右连接 | 以左表 / 右表的键为准 |
| concatenate | 拼接 | 简单堆叠（`pd.concat`），与 merge 的按键匹配不同 |
| boolean masking | 布尔掩码筛选 | 用 True/False 数组筛选行，如 `df[df['a']==1]` |
| conditional statement | 条件语句 | 用 `==`、`>`、`<` 等构成的判断表达式 |
| chaining | 链式调用 | 把多个操作串起来写成一行，如 `df[cond].hist(...)` |
| time series | 时间序列 | 带时间戳的观测数据序列 |
| diurnal profile | 日变化廓线 | 变量在 24 小时内的变化模式 |
| seasonality | 季节性 | 变量随季节的周期性变化 |
| UTC (Coordinated Universal Time) | 协调世界时 | 全球统一的标准时间基准，避免时区混乱 |
| Seaborn (`sns`) | Seaborn 统计可视化库 | 基于 matplotlib 的高级统计绘图库 |
| box plot | 箱线图 / 盒须图 | 用五数概括展示分布的标准图形 |
| five number summary | 五数概括 | 最小值、Q1、中位数、Q3、最大值 |
| median (Q2) | 中位数 | 排序后位于正中间的值（50 百分位） |
| first quartile (Q1) | 第一四分位数 | 25 百分位 |
| third quartile (Q3) | 第三四分位数 | 75 百分位 |
| interquartile range (IQR) | 四分位距 | Q3 − Q1，中间 50% 数据的跨度 |
| whiskers | 须 | 箱体延伸出的线，端点为 Q1−1.5·IQR 和 Q3+1.5·IQR |
| outlier | 离群点 / 异常值 | 超出须端点的数据点，单独画成散点 |
| skewed | 偏态的 | 分布不对称；中位线偏离箱体中心即为偏态 |
| percentile | 百分位数 | 数据中低于该值的比例所对应的分位点 |
| heatmap | 热力图 | 用颜色深浅表示矩阵数值大小的图 |
| pair plot | 配对图 / 散点矩阵 | 所有变量两两画散点、对角线画分布 |
| histogram | 直方图 | 展示单个变量取值频次分布的柱状图 |
| correlation coefficient | 相关系数 | 衡量两变量线性关系强度的量，范围 [−1, 1] |
| Pearson correlation | 皮尔逊相关 | `.corr()` 的默认方法，衡量线性相关 |
| correlation matrix | 相关矩阵 | n×n 方阵，第 (i,j) 元为第 i、j 列的相关系数；对角线全为 1 |
| `.corr()` | 求相关矩阵 | DataFrame 内建方法 |
| NaN (Not-a-Number) | 非数 / 缺失值 | 表示缺失或无效数值；会"传染"普通的 NumPy 统计函数 |
| `dropna()` | 删除缺失值 | 删掉含 NaN 的行（或列） |
| `np.nanmax` / `np.nanmin` | 忽略 NaN 求最值 | NumPy 的"NaN-safe"版本 |
| log scale | 对数刻度 | y 轴按对数展开，适合跨数量级的数据；不能显示 0 和负值 |
| `figsize` | 图幅尺寸 | matplotlib 图的宽高（英寸） |
| `Axes` | 坐标轴对象 | matplotlib 中一个子图的绘图区域 |
| `subplots` | 子图 | 一个 figure 里的多个绘图区域 |
| `set_ylim` | 设置 y 轴范围 | 对比多图时统一量程的关键 |
| Warning | 警告 | 程序继续执行，只是提示；区别于 Error |
| `FutureWarning` | 未来变更警告 | 某用法将在未来版本改变或移除 |
| `DeprecationWarning` | 弃用警告 | 某功能已被废弃 |
| `SettingWithCopyWarning` | 副本赋值警告 | 你在修改一个可能是副本的对象，修改可能不生效 |
| `AttributeError` | 属性错误 | 对象没有你调用的那个属性/方法（如非 DatetimeIndex 调 `.hour`） |
| `SyntaxError` | 语法错误 | 代码不符合 Python 语法（如条件里写成单个 `=`） |
| PM2.5 | 细颗粒物 | 空气动力学直径 ≤ 2.5 µm 的颗粒物，健康危害最大 |
| PM10 | 可吸入颗粒物 | 直径 ≤ 10 µm 的颗粒物；按定义包含 PM2.5 |
| NO2 | 二氧化氮 | 主要来自机动车和燃烧；臭氧的前体物 |
| CO | 一氧化碳 | 不完全燃烧产物，燃烧源的良好示踪剂 |
| O3 (ground-level ozone) | 近地面臭氧 | 二次污染物，由 NOx + VOCs 光化学生成 |
| SO2 | 二氧化硫 | 燃煤等含硫燃料排放，硫酸盐气溶胶前体物 |
| Haze | 霾 | 大量悬浮细颗粒物导致能见度下降的天气现象 |
| titration effect | 滴定效应 | NO + O3 → NO2 + O2，高 NO 环境下臭氧被消耗 |
| photochemical | 光化学的 | 由太阳辐射驱动的化学反应（生成 O3 的机制） |
| boundary layer | 边界层 | 近地面受地表影响的大气层，其高度决定污染物稀释体积 |
| HGV (Heavy Goods Vehicle) | 重型货车 | 老师封锁期研究中的关键污染来源 |
| clustering | 聚类 | 无监督地把相似观测分组（Week 9 内容） |
| data science process | 数据科学流程 | 从数据获取→清洗→分析→建模→呈现的完整链条 |
| garbage in, garbage out | 垃圾进垃圾出 | 数据质量决定一切下游结果的质量 |
| provenance | 数据溯源 | 数据的来源与处理历史 |
| Harvard Dataverse | 哈佛数据存储库 | 本周数据的来源开放数据平台 |

---

## 附：本周一页速记卡

```python
# ===== Week 8 万能模板 =====
import pandas as pd, numpy as np, seaborn as sns, matplotlib.pyplot as plt

# 1. 读数据
df_met = pd.read_csv('meteo.csv');  df_aq = pd.read_csv('aq.csv')

# 2. 时间列转 datetime  ← 必须赋值
df_met['utc_time'] = pd.to_datetime(df_met['utc_time'], format='mixed')
df_aq ['utc_time'] = pd.to_datetime(df_aq ['utc_time'], format='mixed')

# 3. 先筛站点  ← 用 == 不是 =
a = df_met[df_met['station_id'] == 'shunyi_meo'].copy()
b = df_aq [df_aq ['stationId']  == 'shunyi_aq' ].copy()

# 4. 合并  ← 显式 on / how
m = pd.merge(a, b, on='utc_time', how='inner')

# 5. 设时间索引  ← 必须赋值
m = m.set_index('utc_time')
print(m.index)              # 应看到 DatetimeIndex, datetime64[ns], length=?

# 6. 日变化箱线图（一行搞定）
sns.boxplot(data=m, x=m.index.hour, y=m['PM2.5'])

# 7. 相关矩阵 + 热力图
corr = m[['temperature','pressure','humidity','PM2.5','PM10','NO2','CO','O3','SO2']].corr()
sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns); plt.show()

# 8. 忽略 NaN 求极值
np.nanmax(m['PM2.5'].values)     # 或直接 m['PM2.5'].max()（Pandas 自动忽略 NaN）
```

**三句话记住本周**：
1. **把时间设成 index**，Pandas 就送你一整套时间工具（`.hour` / `.month` / `.weekday`）。
2. **merge 之前必须让两表的时间对齐**，否则相关系数是假的 —— 这是科学诚信问题，不是技术细节。
3. **Pandas 方法默认返回新对象**，`set_index` / `to_datetime` / `dropna` 不赋值就等于没做。
