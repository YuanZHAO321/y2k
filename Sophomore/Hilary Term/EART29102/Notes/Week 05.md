# EART29102 Geospatial Techniques — Week 05 学习笔记

> 授课日：02-Mar（Hilary Term, Week 05）
> 材料：`Lecture 5 - Spatial statistics`（讲义）＋ `EART29102 - 02-Mar-transcript`（课堂录音转写）＋ `Practical 5 - Spatial statistics`（ArcGIS Pro 实操教程）
> 本周主题：**空间统计（Spatial statistics）**

---

## 一、本周主题

### 1.1 本周在全课骨架中的位置

本课程的实际骨架是：**基础段**（W01 GIS 导论 → W02 空间数据与数据管理 → W03 数据输入与操作）→ **分析段**（W04 空间分析 → **W05 空间统计**）→ **专题段**（W06 遥感 → W07 地形分析 → W08 空间可视化 → W09 三维技术）→ W10 课程回顾。

**本周是分析段的收尾。** W04 教的是「确定性的空间操作」：overlay（union / intersection / difference）、raster overlay（map algebra）、buffer、以及 spatial interpolation（IDW 与 kriging）。这些操作**做完就是答案**——两个图层叠一下，交集就是交集，没有「这个结果有多大可能只是碰巧」的问题。

W05 把这条线往上推了一层：**从「看得见的空间操作」升级为「可检验的统计推断」**。同样是问「这些高值是不是聚在一起」，W04 的做法是画出来看，W05 的做法是算一个统计量、算一个 z-score、给一个 p-value，然后说「这个聚集有 99% 的把握不是随机造成的」。

老师在课上把这个动机讲得很直白（转写）：

> "we want to minimize any subjectivity or bias that we might have when we're looking at maps and spatial data... we want to question our data set and we want to have some idea of how confident we can be in the answers."

### 1.2 与 W04 的具体衔接点

两周之间有三处明确的接续，复习时应当成一条线看：

1. **Tobler 第一定律**。W04 讲义在 IDW 一节和 spatial autocorrelation 一节都写了这条定律（"Everything is related to everything else, but near things are more related than distant things"），并指出**空间自相关是空间插值的底层假设**。W05 把这条定律从「插值的前提」变成「被测量的对象」——Moran's I 就是在量化它。老师在转写里也说了这是「a variation of the slide I showed you last week」（上周那张图的变体）。
2. **Kriging 与 KDE**。老师讲 KDE 时说它「a little bit like an interpolation surface, like we were talking about last week when we were considering kriging」。
3. **Practical 的 Challenge Exercise 直接要求用上周的 IDW 和 kriging** 来做同一份臭氧数据的连续面——两周的 practical 共用一套数据逻辑。

### 1.3 本周的学习目标（Practical 明列）

By the end of this practical you will be able to:

- Create standard deviational ellipses.（生成标准差椭圆）
- Use the **Average Nearest Neighbor** tool.
- Use the **Spatial Autocorrelation** tool.
- Perform **hot spot analysis**.

### 1.4 ⚠️ 关于考核范围的重要提示

老师在讲 contents 页时**明确划了范围**（转写原话）：

> "Now I don't expect you to remember any statistical formulae or know how to perform any of the calculations for these. What I'm sort of aiming for is that you know how to use them and then you know what they tell you, what information they can give you, so that if you have a particular application, you know which of those statistics to apply."

讲义末尾的 Homework 页也重复了一次：读教科书第 6 章 *Spatial Data Exploration with Statistics*，「**you do not need to learn any statistical formulae**」。

**所以本周的复习重心不是公式，而是：给定一个科学问题，你能选对统计量，并能正确读懂它的输出。** 下面第三节仍然给出公式，但那是为了帮你理解统计量在算什么、为什么符号是那个方向——**不是要你背**。

---

## 二、核心概念

### 2.1 什么是空间统计，为什么要做

**Spatial statistics（空间统计）** = 把 space 与 spatial relationships（distance、area、length、orientation、centrality、coincidence、connectivity）**直接写进数学计算里**的统计工具与方法（Practical 定义）。

老师对「有什么特别的」的回答很朴素：

> "what's special about it? Well nothing really, it's just applying statistical methods to spatial data."

做它的三个理由（讲义与 Practical 用了完全相同的三条）：

1. **Minimize the subjectivity** inherent in human visual interpretation of maps and spatial data.（减少肉眼读图的主观性）
2. **Identify and quantify patterns and trends** in data that may not be revealed in visual analysis.（发现肉眼看不出的模式）
3. **Answer questions more confidently** and make important decisions using more than simple visual analysis.（给答案配上置信度）

讲义首页用的示例是 Neville et al. (2022) 对 central Appalachia 地区地表水中 mercury、lead、copper、zinc、nickel、fluoranthene 的 **hotspot analysis** 结果图。

### 2.2 空间抽样设计（Spatial sampling design）

一切统计的前提是**样本要能代表总体（representative of the population）**。老师强调：

> "if it's not representative and we're trying to infer something about the overall population... then our answer is going to be systematically wrong."

讲义列出的五种抽样布局：

| 方法 | 英文 | 做法 | 适用/说明 |
|---|---|---|---|
| 随机 | **Random** | 研究区内每个位置被选中的机会均等，各点彼此独立 | 最基本的基准 |
| 分层 | **Stratified** | 先按某个共有特征把区域切成 strata，再在各层内抽样 | 讲义例子按 topographic height 分层；老师另举 woodland / grassland 两种生境 |
| 系统 | **Systematic** | 按规则格网布点 | 覆盖均匀 |
| 成群 | **Clustered** | 先随机选若干小区，再在小区内密集布点 | 省成本 |
| 样带 | **Transect** | 沿一条线布点 | 追踪梯度变化 |

**分层抽样的关键细节（老师口头强调，讲义未展开）**：各层必须**按面积比例（proportionally）**抽样。若某层占总面积 40%，就要把 40% 的样点放在那一层，另外 60% 放在另一层。而且**任何一种抽样方式都可以套用在分层框架内**。

老师还提到 ArcGIS Pro 里有**专门生成采样点位的工具**（可随机取点、可做 transect）。
> 📎 背景补充：他没点名，ArcGIS Pro 中对应的是 **Create Random Points** 工具（Data Management Tools > Sampling），以及 **Generate Points Along Lines**。材料未给工具名，此处仅供定位。

### 2.3 描述统计（Descriptive statistics）——空间版

Descriptive statistics 就是**总结数据**，结果可以是定量的（summary statistic）也可以是可视的（graph 或 feature class）。GIS 里常测三样：

| 维度 | 英文 | 空间对应量 | 含义 |
|---|---|---|---|
| 集中趋势 | **Central tendency** | **Mean Center（平均中心）** | 所有要素 X 坐标的平均、Y 坐标的平均所定义的点，即空间分布的「重心」 |
| 离散程度 | **Dispersion** | **Standard Distance（标准距离）** | 各要素到 mean center 距离的离散度量，相当于空间版的标准差；画出来是一个**圆** |
| 方向 | **Direction** | **Standard Deviational Ellipse（标准差椭圆）** | 把 X、Y 两个方向的标准距离**分开计算**，画出来是一个**椭圆** |

**Direction 是空间数据独有的一个维度**（老师特别点出这一点：普通数据没有方向可查）。应用场景讲义列了：wind directions、animal migrations、pollution pathways、volcanic plumes。老师补充：可以用来追踪污染物在景观中的迁移轨迹。

椭圆怎么读：**Y 方向变异远大于 X 方向 → 椭圆在纵向被拉长**，反之亦然。椭圆的长轴方向就是数据的主导方向趋势。

### 2.4 推断统计与完全空间随机（Inferential statistics & CSR）

**Inferential statistics** = 基于样本中的值的分布，**推断整个总体**的性质。Practical 举的经典例子是「根据民调预测选举结果」。

**Statistical significance（统计显著性）** = 观测到的空间格局**不太可能仅仅由偶然（chance / random）产生**的概率。

**Complete Spatial Randomness（CSR，完全空间随机）** 是所有 pattern analysis 工具的**零假设内容**。Practical 说得很准确：

> "The **null hypothesis** for pattern analysis tools is **complete spatial randomness** in either the **location** of features or the **values** associated with those features."

注意这句话里的分叉：**有的工具检验「位置」的随机性（Average Nearest Neighbor），有的工具检验「值」的随机性（Moran's I、Gi\*）**。这是本周最重要的一条分类线。

**假设检验的框架**（讲义）：

- **Null hypothesis（H₀，零假设）**：**always** stated as being **no spatial pattern**, or no relationship between two observed spatial patterns.（永远是「没有格局、没有关系」）
- **Alternative hypothesis（Hₐ，备择假设）**：opposite to the null hypothesis.（有格局）
- **Significance test**：根据显著性水平决定是否拒绝 H₀。

老师用美国人口密度图和高程图做了一个非常直观的演示：左边是真实的 population density per km²（按县着色，颜色越深密度越高）/ 真实的 elevation map；右边是**把同样的值随机打乱**之后的图。右边那张就是「如果一切完全随机会长什么样」的样子——**这就是我们要拿来做对照的基线**。老师的原话：

> "we're setting up a baseline or a null hypothesis of randomness. This is what a random distribution would look like... How well does that match randomness? So it's not realistic, it's a concept that we tend to test against."

### 2.5 z-score 与 p-value

- **z-score**：表示某个值偏离分布均值的程度。老师解释了标准化的用意：**standardize 就是把分布的均值变成 0、标准差变成 1，从而去掉单位（remove units）**，这样任何量纲的变量都可以放到同一条标准正态曲线上比较。z-score 在图上就相当于「几个标准差」。
- **p-value**：讲义定义为——"The exact probability of getting a value of the test statistic of a given magnitude if the null hypothesis is true is called the p-value."（在 H₀ 为真的前提下，得到这么极端的检验统计量的确切概率。）
- 讲义给的换算：α = 0.05 对应「以 95% 置信度拒绝 H₀」。
- **两种用法可以互换**（老师强调）：你可以**先设定概率边界**（比如取 α=0.05，查出临界 z 值 ±1.96），也可以**先算出 z-score 再反推确切的 p 值**。

讲义 OCR 出来的**临界值表**（Average Nearest Neighbor 报告里的配色分级），这是本周最实用的一张查表：

| Critical Value (z-score) | 含义 |
|---|---|
| < −2.58 | 显著聚集，99% 置信 |
| −2.58 ~ −1.96 | 显著聚集，95% 置信 |
| −1.96 ~ −1.65 | 显著聚集，90% 置信 |
| −1.65 ~ 1.65 | 不显著（Random，不能拒绝 H₀） |
| 1.65 ~ 1.96 | 显著离散，90% 置信 |
| 1.96 ~ 2.58 | 显著离散，95% 置信 |
| > 2.58 | 显著离散，99% 置信 |

> ⚠️ **注意方向**：这张表是 **Average Nearest Neighbor** 的表——**负 z 值 = clustered，正 z 值 = dispersed**。到了 Moran's I 就**反过来**：正 z 值 = clustered。原因见 2.7、2.8。这是本周最容易记反的地方。

### 2.6 空间自相关（Spatial autocorrelation）与 Tobler 第一定律

**这是全部空间统计的出发点。**

**Tobler's First Law of Geography**（W04 讲义原文）：
> "Everything is related to everything else, but near things are more related than distant things."
> 「任何事物都与其他事物相关，但近处的事物比远处的事物更相关。」

**Spatial autocorrelation** 就是这条定律的**统计度量**（W04 讲义原话："a statistical measure of Tobler's first law"）。W05 讲义给的操作定义：

> "Distance methods using **both feature locations and feature values simultaneously**. Evaluates the spatial autocorrelation. Determines if pattern is clustered, dispersed, or random."

**三种型式与正负号的对应**：

| 空间格局 | 自相关 | 直观说法 |
|---|---|---|
| **Clustered（聚集）** | **Positive** spatial autocorrelation | 相似的值聚在一起 |
| **Random（随机）** | 无自相关 | 没有可辨认的规律 |
| **Dispersed（离散）** | **Negative** spatial autocorrelation | 不相似的值挨在一起 |

老师给了一个记忆口诀，还顺带自嘲了一句（转写）：

> "One way that people like to try and remember this, which **never works for me, I always get confused**, but you think of clustered, it's like **with like**... If you think of dispersed... it's like **with unlike**, things are located with things that are different from each other."

**「like with like → clustered → positive；like with unlike → dispersed → negative」。**

**📎 背景补充：为什么普通统计方法在空间数据上会失效。**
材料没有正面讲这一点，但它是空间统计存在的根本理由，值得补一句：经典统计（t 检验、OLS 回归等）都建立在**观测值相互独立（independent observations）**的假设上。而 Tobler 定律说的恰恰是**空间数据天然不独立**——相邻的观测互相「携带」对方的信息。后果是：**有效样本量（effective sample size）小于名义样本量 n**，标准误被系统性低估，于是 t 值、z 值被高估，**你会把本来不显著的关系判成显著的**（这叫 inflated Type I error，第一类错误膨胀）。所以空间数据需要一套显式把 spatial weights 写进公式的统计量——这正是 Moran's I、Gi\* 在做的事。**注意：这一整段是补充，讲义与转写均未涉及。**

### 2.7 四个统计量的功能分工（本周最该背下来的一张表）

材料把四个工具串成了一条**层层递进**的逻辑链，老师在课上是按这个顺序一步步「逼出」下一个工具的。请务必按这条链理解，不要孤立记忆：

| # | 统计量 | 回答的问题 | 用位置？ | 用属性值？ | 输出形式 | 给概率？ |
|---|---|---|---|---|---|---|
| 1 | **Average Nearest Neighbor (ANN)** | 这些**采样点位**是不是随机分布的？ | ✅ | ❌ **完全不用** | **报告（HTML），不是图层** | ✅ z-score, p-value |
| 2 | **Global Moran's I** | 在**整个研究区**范围内，相似的值是不是聚在一起？ | ✅ | ✅ | **报告，不是图** | ✅ z-score, p-value |
| 3 | **Local Moran's I（Cluster and Outlier Analysis）** | 聚集**发生在哪里**？有没有局部异常值？ | ✅ | ✅ | **地图**（HH/LL/HL/LH 四类着色） | ❌（老师说它用的是 arbitrary cutoff） |
| 4 | **Getis-Ord Gi\*（Hot Spot Analysis）** | 异常高/异常低的值**位于哪里**，且我有多大把握？ | ✅ | ✅ | **地图**（热点/冷点＋置信度分级） | ✅ 每点一个 z-score 与 p-value |
| — | **Kernel Density Estimation (KDE)** | 密度在空间上如何变化？ | ✅ | 可选 | **栅格（raster）密度面 / heat map** | ❌ |

老师推进这条链的逻辑（转写原话可作为答题主线）：

- ANN 之后：「what you might be interested in is knowing **where are the clusters**? Are there clusters of high ozone concentration?」→ 需要用到属性值 → Global Moran's I。
- Global Moran's I 之后：「our ozone concentrations are clustered together, but **we can't really see where** they are clustered」→ 需要可视化 → Local Moran's I。
- Local Moran's I 之后：「it's not giving us any kind of **probability**... and it's using some kind of **arbitrary cutoff** to define what is high and what is low」→ 需要置信度 → Getis-Ord Gi\*。

### 2.8 各统计量细节

**(1) Nearest Neighbour Analysis (NNA) / Average Nearest Neighbor**

- 做法：量测**每个要素到其最近邻的距离**（观测平均距离 r₀），与**完全随机格局下期望的平均距离**（rₑ）比较。
- **只用位置，完全不看属性值**（讲义加粗强调 "does **not** consider the feature values at all"）。
- **Ratio (R) = mean observed / mean random distances**
  - **R < 1 → 趋于 clustering（聚集）**
  - **R ≈ 1 → 趋于 random（随机）**
  - **R > 1 → 趋于 dispersed（离散）**
- 直觉：如果点挤在一起，每个点离最近邻**比随机情况更近**，所以观测距离偏小，比值小于 1。

**(2) Global Moran's I**

- 讲义定义：Detects **spatial clusters** of features with high or low values (**and spatial outliers**). **Works with attribute values.**
- 回答的问题（讲义原文）："Do similar values cluster together **across the whole study area**?"
- 「Global」的含义：**给整个研究区一个总结数字**，不告诉你位置。

**(3) Local Moran's I**

- 讲义：shows **where** clusters occur and identifies **local outliers**。
- 输出四类（老师逐一解释过）：

| 类别 | 英文 | 含义 |
|---|---|---|
| HH | **High-High cluster** | 高值周围也是高值 → 高值聚集 |
| LL | **Low-Low cluster** | 低值周围也是低值 → 低值聚集 |
| HL | **High-Low outlier** | **一个高值落在一堆低值中间** → 异常值 |
| LH | **Low-High outlier** | **一个低值落在一堆高值中间** → 异常值 |

- 老师课上放大了臭氧图的中央区域，把 ppm 数值标了出来：一片蓝色 LL 低值簇里嵌着一个 **0.062 的 HL 高低异常值**；另一侧一片红色高值区里嵌着若干 **LH 低高异常值**。他评论："there might be a reason why that concentration is very high. We would need further investigation."——**异常值是提出后续科学问题的抓手，不是要被删掉的噪声。**
- 另外提醒：并非所有点都会被分到四类中的某一类，**有相当一部分点不属于任何簇**（not statistically significant）。

**(4) Hot Spot Analysis（Getis-Ord Gi\*）**

- 回答的问题（讲义）："Where are the **unusually high** or **unusually low** values located?"
- 结果读法（讲义原文）：**hot spots（红）= 高值的统计显著聚集；cold spots（蓝）= 低值的聚集**。**Works with attribute values.**
- 输出带**置信度分级配色**（90% / 95% / 99%）。老师举例：深蓝点表示 **99% 置信度的 cold spot**——「你可以有 99% 的把握，这个小簇不是纯粹偶然造成的」。
- 讲义首页的 Appalachia 案例（Neville et al. 2022，DOI: 10.1080/02626667.2022.2052073）就是这类图。

**(5) Kernel Density Estimation (KDE)**

- 定义（讲义）：把**点对象转换成密度面（density surface）**，用来可视化点格局、探测局部密度高的热区。
- 计算方式：在估计位置 p 处放一个 **kernel（核）**——最简单就是以 p 为圆心的**圆**；更复杂的用一个**加权函数**对邻近事件加权。老师说最常用的是在每个点上**拟合一个 Gaussian 分布**。
- **每个点被替换成一个 kernel，密度面就是所有 kernel 的叠加和。**
- 输入是 vector 点数据，**输出是 raster（栅格）**。
- **Density is scale dependent（密度依赖于尺度）** —— 也就是下面的 bandwidth 问题。

**(6) Kernel radius / bandwidth（核半径 / 带宽）**

讲义与老师用同一份臭氧数据演示了三档半径：

| 半径 | 效果 | 老师的评价 |
|---|---|---|
| **1500 km** | 过度平滑（**Smoother / global average**） | 「produce a very smoothed out density surface... you can lose some of the detail」，看不出高值区 |
| **15 km** | **salt and pepper effect（椒盐效应）**，孤立在单个值上（Isolated on individual values） | 「You're not seeing much detail. It's not very realistic」 |
| **optimised 99.3 km** | 恰好显示出应有的细节层次 | GIS 的 **optimisation routine** 自动算出来的，能把几个热点都挑出来 |

> ⚠️ **KDE 与 Hot Spot Analysis 长得像，但根本不同**：KDE **不给概率**，它只是一张按密度着色的面；Gi\* 给的是**统计显著性**。Practical 第 7 节专门设计了一步来让你看清这个区别（见五、第 7 步）。

**📎 背景补充：材料未涉及但概念相邻的几项。**（讲义与 practical 均未提到以下内容，仅供你在写 assessment 或大三项目时知道有这些东西存在）
- **Geary's C**：另一个全局空间自相关指标，取值以 1 为「无自相关」中心，**C < 1 表示正自相关（聚集）、C > 1 表示负自相关（离散）**——注意它与 Moran's I **方向相反**。Geary's C 对**局部差异**更敏感，Moran's I 对**全局趋势**更敏感。
- **LISA（Local Indicators of Spatial Association，局部空间关联指标）**：Anselin (1995) 提出的一类局部指标的统称，Local Moran's I 是其中最常用的一个。ArcGIS Pro 里的 **Cluster and Outlier Analysis (Anselin Local Moran's I)** 工具就是它。
- **Ripley's K function**：点模式分析的一种，与 ANN 只看「最近邻」不同，它在**一系列不同距离尺度上**同时检验聚集程度，因此能回答「在多大尺度上聚集」。ArcGIS Pro 中的工具名是 **Multi-Distance Spatial Cluster Analysis (Ripley's K Function)**。
- **GWR（Geographically Weighted Regression，地理加权回归）**：让回归系数随位置变化的局部回归方法，用于处理空间非平稳性。**本周材料完全未涉及。**

---

## 三、公式与图表

> **再次提醒**：老师明确说了公式不考（"you do not need to learn any statistical formulae"）。以下公式**全部属于 📎 背景补充**——讲义只放了图、没放任何一条公式，转写里老师说 "we won't consider the actual formula for calculating that"。给出公式的目的是**帮你理解符号方向和 z-score 的判读逻辑**，不是让你背。

### 3.1 📎 背景补充：Global Moran's I 的公式

$$
I \;=\; \frac{n}{S_0}\cdot\frac{\displaystyle\sum_{i=1}^{n}\sum_{j=1}^{n} w_{ij}\,(x_i-\bar{x})(x_j-\bar{x})}{\displaystyle\sum_{i=1}^{n}(x_i-\bar{x})^2},
\qquad S_0=\sum_{i=1}^{n}\sum_{j=1}^{n} w_{ij}
$$

逐项含义：

| 符号 | 含义 |
|---|---|
| $n$ | 要素（观测点）总数 |
| $x_i$ | 第 i 个要素的属性值（本周即 OZONE 的 ppm 值） |
| $\bar{x}$ | 所有属性值的平均 |
| $w_{ij}$ | **空间权重（spatial weight）**——要素 i 与 j 在空间上「有多相邻」，由 **Conceptualization of Spatial Relationships** 决定 |
| $S_0$ | 所有权重之和，起归一化作用 |

**怎么理解这个式子**：分子是「**每一对要素的离均差乘积，按空间邻近程度加权求和**」。如果高值旁边也是高值（两个正的离均差相乘为正）、低值旁边也是低值（两个负的相乘也为正）→ 分子为正 → **I > 0 → 正自相关 → 聚集**。如果高值旁边总是低值（一正一负相乘为负）→ **I < 0 → 负自相关 → 离散**。分母是总方差，作用是把 I 归一化到大致 −1 到 +1 的区间。

**期望值（这是最关键、也最容易记错的一条）**：

$$
E(I) \;=\; -\frac{1}{n-1}
$$

- **注意：随机情况下 Moran's I 的期望值不是 0，而是一个略小于 0 的负数。**
- $n$ 越大，$E(I)$ 越接近 0。以本周 practical 的 167 个监测站为例：$E(I) = -1/166 \approx -0.0060$。
- 所以严格地说，**判断聚集/离散的基准线是 $E(I)$ 而不是 0**——虽然样本量大时两者几乎没差别。

**z-score 的构成**：

$$
z_I \;=\; \frac{I - E(I)}{\sqrt{V(I)}}
$$

即「**观测值减期望值，再除以标准差**」——这就是 2.5 节说的「标准化、去单位」。判读方向：

- **$z_I$ 显著为正（如 > +1.96）→ clustered（相似值聚集）**
- **$z_I$ 显著为负（如 < −1.96）→ dispersed（棋盘格式的离散）**
- **$|z_I| < 1.65$ → 不能拒绝 H₀，视为 random**

> ⚠️ **和 ANN 的方向正好相反**（ANN 是负 z = 聚集）。原因很简单：ANN 量的是**距离**，聚集意味着距离**变小**；Moran's I 量的是**相似性**，聚集意味着相似性**变大**。**理解这一句，就永远不会记反。**

### 3.2 📎 背景补充：Getis-Ord Gi\* 的公式与含义

$$
G_i^* \;=\; \frac{\displaystyle\sum_{j=1}^{n} w_{ij}x_j - \bar{X}\sum_{j=1}^{n} w_{ij}}{S\sqrt{\dfrac{n\sum_{j} w_{ij}^2-\left(\sum_{j} w_{ij}\right)^2}{n-1}}}
$$

**Gi\* 本身就已经是一个 z-score**（这是它和 Moran's I 在使用上的一个重要差别：Moran's I 要再标准化一次，Gi\* 直接输出 z）。

其含义可以完全用文字说清：**分子 = 「要素 i 及其邻域内所有要素的属性值之和」减去「如果这块邻域是平均水平应该有的和」**。

- 邻域实测总和 **远高于**全局平均预期 → **Gi\* 大正值 → hot spot（热点）**
- 邻域实测总和 **远低于**全局平均预期 → **Gi\* 大负值 → cold spot（冷点）**
- 差不多 → Gi\* 接近 0 → 不显著

**星号 `*` 的含义**：Gi\* 的邻域**包含要素 i 自身**；不带星号的 Gi 只算邻居、不算自己。ArcGIS Pro 的 Hot Spot Analysis 工具用的是 **Gi\***。

**Gi\* 与 Local Moran's I 的本质差别**（考试极易混淆，见第六节）：
- **Gi\***：问「这一片的值**整体上是高还是低**」→ 输出热点/冷点。**它找不出异常值**——一个孤立高值周围全是低值时，邻域总和被拉平，Gi\* 反而不显著。
- **Local Moran's I**：问「这个点**和它的邻居像不像**」→ 输出 HH/LL（像）与 HL/LH（不像）。**它专门能揪出异常值。**

### 3.3 📎 背景补充：Average Nearest Neighbor 的比值公式

$$
R \;=\; \frac{\bar{D}_O}{\bar{D}_E}, \qquad
\bar{D}_O=\frac{\sum_{i=1}^{n} d_i}{n}, \qquad
\bar{D}_E \;=\; \frac{1}{2\sqrt{n/A}} \;=\; \frac{0.5}{\sqrt{n/A}}
$$

| 符号 | 含义 |
|---|---|
| $\bar{D}_O$ | **观测**平均最近邻距离（每个点到其最近邻距离 $d_i$ 的平均） |
| $\bar{D}_E$ | **期望**平均最近邻距离（在同样面积、同样点数的完全随机分布下的理论值） |
| $n$ | 点数 |
| $A$ | **研究区面积** |

**注意 $A$ 出现在期望值公式的分母里**——这解释了为什么 Practical 第 4 步要你手动从 `ca_outline` 的属性表里把 **Shape_Area** 抄进 **Area** 参数：**面积取值直接决定 $\bar{D}_E$，从而直接决定 R 是大于 1 还是小于 1。面积填错，结论就会反过来。**（材料只说了要抄，没说为什么，这里补上原因。）

**判读方向（讲义原文，务必记牢）**：

| R 值 | 结论 |
|---|---|
| **R < 1** | tendency toward **clustering**（聚集） |
| **R = 1** | tendency to be **random**（随机） |
| **R > 1** | tendency to be **dispersed**（离散） |

### 3.4 关键图表的文字描述

材料里的图无法直接复制，以下是逐张的文字还原，复习时按这些描述在脑子里重建图像即可。

**图 A —— 空间自相关的三种型式（讲义 "Spatial Autocorrelation" 页，OCR 提示为 "negative / random / positive" 三联图）**

三个并排的方格，各代表一种格局：

- **左（negative，离散 / dispersed）**：点或格子呈**棋盘格状交替**——深色格子的四邻全是浅色，浅色的四邻全是深色。相邻的东西**互相排斥**。「like with unlike」。
- **中（random，随机）**：深浅格子毫无规律地散布，看不出任何成片或交替的结构。这是 H₀ 的样子。
- **右（positive，聚集 / clustered）**：深色格子连成一大片，浅色格子连成另一大片，**颜色成块出现**。「like with like」。

**图 B —— Complete spatial randomness（讲义第 8 页，两组对照图）**

左边一列是**真实数据**：美国按 county 着色的 population density（东部沿海和大城市区深色成片）和 elevation map（西部落基山系高值成片、中部平原低值成片）。右边一列是**把同样的值随机重排**后的图：颜色像雪花点一样均匀撒开，任何成片结构消失。

**读图要点**：肉眼一看就知道左右两边完全不同——**这种「一眼看出的不同」正是统计量要去量化的东西**。老师说右边这种图 "it's not realistic, it's a concept that we tend to test against"。

**图 C —— Nearest Neighbour Analysis 的输出报告（讲义第 13 页，本周最该会读的一张图）**

图分左右两块：

- **左侧**是加州地图（可辨认出 San Francisco、Los Angeles、Sierra Nevada 山脉走向、Mojave Desert），上面撒着一批红色采样点，明显在几个区域挤在一起。
- **右侧**是 **Average Nearest Neighbor Summary** 报告，内容为：

  | 项 | 值 |
  |---|---|
  | Nearest Neighbor Ratio | **0.866323** |
  | z-score | **−3.304793** |
  | p-value | **0.000950** |

  下方是一条**标准正态钟形曲线**，横轴按临界 z 值分成七段并配色（就是 2.5 节那张表）：左尾标 **Clustered**、中段标 **Random**、右尾标 **Dispersed**。
  
  报告底部一行结论：**"Given the z-score of −3.304793, there is a less than 1% likelihood that this clustered pattern could be the result of random chance."**

**读图链条（把这条链背下来就等于会读所有类似报告）**：
R = 0.866 **< 1** → 观测距离比随机预期近 → **聚集** → z = −3.30 落在**左尾深蓝区（< −2.58）** → p = 0.00095 **< 0.01** → **拒绝 H₀，99% 置信度下判定为 clustered**。

**图 D —— Moran 散点图的四象限（📎 背景补充：本周材料中没有这张图，但它是理解 HH/LL/HL/LH 的最好工具）**

> 📎 背景补充：讲义只给了 Local Moran's I 的**地图输出**，没有给散点图。以下为补充说明。

Moran scatterplot 的横轴是**标准化后的自身属性值 $z_i$**，纵轴是**该点邻域的加权平均值（spatial lag）$Wz_i$**。原点即全局平均。散点图被分成四个象限，**恰好与 Local Moran's I 的四类一一对应**：

| 象限 | 位置 | 自身 | 邻居 | 类别 |
|---|---|---|---|---|
| 第一象限 | 右上 | 高 | 高 | **HH cluster** |
| 第二象限 | 左上 | 低 | 高 | **LH outlier** |
| 第三象限 | 左下 | 低 | 低 | **LL cluster** |
| 第四象限 | 右下 | 高 | 低 | **HL outlier** |

**并且：拟合这堆散点的回归直线，其斜率就等于 Global Moran's I。** 这一条把 global 与 local 两个尺度串成了一件事——**Global Moran's I 是全局斜率，Local Moran's I 是每个点落在哪个象限**。

**图 E —— Local Moran's I 的地图输出（讲义引 Mashhoodi 2024）＋ 老师的放大讲解**

加州底图上的采样点按四类着色：HH cluster、HL outlier、LH outlier、LL cluster（再加一类「不显著」）。老师放大了中央一个方框区域，把每点的 ppm 数值标了出来：

- 一片全是低值的**蓝色 LL 簇**中间，坐着一个 **0.062 的高值点，被标为 HL outlier**。
- 另一侧一片高值的**红色区域**里，嵌着几个明显偏低的点，被标为 **LH outlier（深蓝）**。
- 周围还有一批点**不属于任何簇**。

**读图要点**：颜色回答「在哪里」，但**这张图不带置信度**。

**图 F —— Hot Spot Analysis (Gi\*) 的地图输出**

同样是加州采样点，但配色是**红—白—蓝的发散色带**，且每一档都标着置信水平：

- **深红 = hot spot, 99% confidence**；中红 95%；浅红 90%
- **白/灰 = not significant**
- 浅蓝 90%；中蓝 95%；**深蓝 = cold spot, 99% confidence**

Practical 里对应的实际结果是：**north-central California 有统计显著的高臭氧热点**（点开这些红点，OZONE 值都在 0.08–0.10 附近）；**加州南部有冷点**（点开蓝点，值多在 0.05 或更低）。

**读图要点**：**颜色的深浅 = 置信度，不是数值大小。** 一个非常高的孤立值可能是白色（不显著），因为它周围没有别的高值陪着它。

**图 G —— 不同 kernel radius（bandwidth）导致结果差异的示意**

同一份加州臭氧点数据，三张 KDE 结果并排：

- **1500 km**：整张图变成一大团柔和的渐变，几乎看不出局部结构——**Smoother（趋近全局平均）**。老师指着某个区域说「这里完全看不出有高值」。
- **15 km**：每个采样点变成一个孤零零的小亮斑，图上一片零碎的斑点——**salt and pepper effect（椒盐效应），Isolated on individual values**。
- **optimised 99.3 km**：出现了三到四个清晰的热区，既没糊成一片也没碎成点。

**读图要点**：**这三张图来自同一份数据，结论却完全不同。** 这就是「Density is scale dependent」的具体含义，也是第六节要讲的头号陷阱在 KDE 上的体现。

**图 H —— 不同空间权重设定导致结果差异的示意（📎 背景补充）**

> 📎 背景补充：材料**没有**这张图，但 Practical 第 5 步的那段警告文字（关于 154,019 m 与 800 m 的对比）实际上描述的就是这个现象。以下为补充的可视化想象。

设想同一份点数据跑三次 Gi\*，只改 **Distance Band**：

- **带宽极小**（只有最近的一两个点算邻居）：几乎所有点都不显著，因为每个邻域样本太少，方差太大，图上一片白。
- **带宽适中**：清晰浮现出若干红色热点与蓝色冷点。
- **带宽极大**（几乎所有点互为邻居）：每个点的邻域平均都趋近全局平均，Gi\* 全部趋近 0，图上又是一片白——**或者，如果研究区本身有大尺度梯度，会出现一整个半边红、一整个半边蓝的假象。**

**读图要点**：**同一份数据 + 同一个工具 + 不同权重设定 = 三种彼此矛盾的图。** 权重不是可以随手默认的技术细节，它是分析的一部分假设。

**图 I —— Standard Deviational Ellipse（讲义 "Measures of central tendency and dispersion" 与 Washington 野火案例）**

- **基础示意图**：一堆散点；中间一个**黄色圆圈中间带黑点** = **Mean Center**；外面一个**大圆** = **Standard Distance**；再套一个**椭圆** = **Standard Deviational Ellipse**，椭圆的长短轴方向反映数据在 X、Y 上变异的不对称。
- **Washington 野火案例**（讲义引 https://link.springer.com/article/10.1007/s13753-022-00396-4）：左图是美国本土图，Washington 州被涂黑；中图是该州的放大图，上面是 **1970–2020 年间所有 >100 acre 的野火火烧点**；右图是**每个十年一个椭圆**，从 1970s 到 2020s 用**逐渐加深的颜色**表示。

**读图要点（老师亲自演示的一条结论）**：随着年代推进，**椭圆逐渐变小、并向该州东北部移动**——「the areas of burns are becoming more intense in the north east part of Washington state」。**一组椭圆叠在一起就是一部时间序列的空间演化史**，这是标准差椭圆最有说服力的用法。

---

## 四、课堂补充

本周有 5,850 词的完整 transcript，以下是**讲义 slide 上没有、只在口头讲出来**的内容。

### 4.1 课程事务与考核提示（务必留意）

1. **Podcast（录播）问题**：前几周的 podcast 有访问故障，老师起初以为只影响自己，后来发现是普遍问题。他说如果本周还解决不了，就**重新录一遍**并把链接放到 Canvas 上。
2. **⚠️ Assessment exercise 已发布**（这是本周最重要的实务信息）：
   - 已经上传到 Canvas，如果打不开要告诉他。
   - 形式是**从四个 case studies 里选一个**（"choosing one of four case studies, depending on your preference"）。
   - 可以现在就开始动手，但——**"don't submit anything too soon. Certainly not before the Easter break."**
   - 理由：**后续的 practical exercises 会提供对完成 assessment 有帮助的信息**（"there will be more information as you go through the practical exercises that will help you"）。
   - **这条提示的实际含义**：assessment 的能力要求是**跨周累积的**，本周的空间统计工具很可能就是某个 case study 的核心方法。做 assessment 前应该先把后面几周的 practical 走完。
3. **下周（W06）换人上课**：由 **Pete Grinrod**（Natural History Museum，同时在曼大有 honorary position）讲 **remote sensing**，那是他的专长领域。老师说他会在开头露个面确认设备没问题。
4. **公式不考**（已在 1.4 详述）。老师原话再录一次以强调："I don't expect you to remember any statistical formulae... you know how to use them and then you know what they tell you... **if you have a particular application, you know which of those statistics to apply**." ——**考核方式高度可能是「给场景选方法 + 读结果」，而不是计算。**
5. **课后资源**：教科书第 6 章 *Spatial Data Exploration with Statistics*（"probably got more information than you need"）；Canvas 上的 quiz；ESRI 官方培训 **Mapping Clusters: Introduction to Statistical Cluster Analysis**（约 50 分钟）。Practical 末尾另推荐了一个约 1 小时的视频 **Spatial Data Mining I: Essentials of Cluster Analysis**（"quite good at explaining the concepts with everyday examples"）。
6. 老师说这门课的空间统计只是冰山一角：**"Obviously there's a lot more spatial statistics than the ones listed there, but some of the common ones that you'll come across."**

### 4.2 抽样部分的口头补充

- **代表性是一切的前提**，而且**不代表性造成的是系统性错误（systematically wrong），不是随机误差**——多采几个样也补不回来。
- **Random sampling 的准确定义**：每个位置被选中的机会均等，各点**彼此独立**。老师特别澄清：「It doesn't matter what the measurement is, **it's the actual location where we do the measurement that's important**.」——抽样设计管的是位置，不是测什么。
- **Stratified 的两个例子**：讲义图上是按 topographic height 分层（高海拔 / 低海拔）；老师另举一个更直观的——**橙色区是 woodland、白色区是 grassland，两种生境要分别采样但保持比例**。
- **按比例的具体算法**：「if one of those areas represented 40% of the total area, then we'd need to collect **40% of our samples** within that strata. And the other 60% in the other strata.」
- **分层与其他方法可以叠加**：「we can apply **any of these types of sampling** to that stratified situation」——比如在每个 stratum 内部再做 systematic 或 transect。
- **"Depending on what we want to find out, what our question is really matters."** ——**抽样方法由科学问题决定**，没有普遍最优的方法。

### 4.3 描述统计部分的口头补充

- **Mean center 的算法**被明确说成「simply the average of our X and Y coordinate values」。
- **Standard distance ≈ 空间版标准差**：「a measure of the variance between the average distance of the features to the mean centre」，在图上就是那个大圆的半径尺度。
- **Standard deviational ellipse 与 standard distance 的关系（关键区别，讲义没写）**：
  > "here we're calculating **separate standard distances for each of the X and Y values**. In the **standard distance itself these two are combined**, but here **they're kept separate**."
  
  ——**Standard distance 把 X、Y 合并成一个数（所以是圆）；ellipse 把 X、Y 分开算（所以是椭圆）。** 这是判断题的常见考点。
- 椭圆形状的解读：「if we've got a lot more variation in our Y value compared to X, then it's going to **elongate the ellipse in a vertical sense**」。
- **Washington 野火案例的完整解读**（见图 I）：1970–2020，>100 acre 的野火，逐十年画椭圆，颜色渐深。结论是**火烧区随时间变小、并集中到该州东北部**。老师评价：「you can see how useful that is in... showing how things are changing over time.」

### 4.4 推断统计部分的口头补充

- 老师明确说这是**大一统计课的复习**：「I'm sure you've done this in your first year on your statistics course, so hopefully this is something of a refresher.」——**如果这里发懵，应该回去翻 EART11200 的统计部分。**
- **为什么需要统计**：「we can't go out and measure everything, so we collect a sample, we hope that it's representative of the population, and then based on the characteristics of that sample we try and infer something about the overall population.」
- **z-score 的意义被讲得很实用**：标准化「is to **remove units**」，把分布变成均值 0、标准差 1，「that means you can apply **any scaled variable** onto your standard curve」。
- **两种等价用法**：「you can either **set boundaries for your probability**, or you can **determine the actual probability** based on the z-score that you calculate.」
- **一个必须留意的措辞简化**：老师说「Once you exceed that 90% level it means that **you can be 90% confident that your sample distribution is not part of this parent random distribution**」。这是教学上的通俗说法，严格的统计学表述见第六节的讨论——**p 值不是「H₀ 为假的概率」**。
- **统计学不给确定性**：「you can't always be certain of course in statistics but you can apply a certain level of probability to your data.」

### 4.5 各统计量的口头补充与实例

**Appalachia hotspot 案例**（讲义首页那张图，老师花了一段讲）：
- 数据是 **2008–2018** 年（他先说 2000 后自我更正为 2008）的**地表水污染**（surface water contamination）数据，涵盖多种金属和有机污染物。
- 图上的分级表示「高值与其他高值聚在一起，且有一定置信度不是偶然」——**90% 或 95% 的置信水平**。
- 「in one of those areas you've got **high values associated with other high values** and you have a level of confidence that it's not just happening by chance.」——**这句话是 hot spot 的最佳一句话定义。**

**Average Nearest Neighbor 的实例（加州臭氧）**：
- 数据背景：加州各监测站的**臭氧浓度**测量，目的是**空气质量监测（air quality）**。地理参照物：San Francisco、Los Angeles、Sierra Nevada 山脉。
- 老师先让大家肉眼判断：「you could probably say, well, they're probably not random. They're in some way, they're clustered.」**然后再用统计量去确认**——这个「先看图猜、再算统计量验证」的顺序是他反复示范的工作方式。
- **⚠️ 关键提醒（讲义没有）**：「If you run this analysis on ArcGIS Pro... **You get a summary statistic. You don't get a map. You don't get a visual output.**」
- 结论：「we looked at it, we said, yeah, they're clustered. We carried out the statistic, and now we've got a **kind of confidence that we can associate with that**.」——**统计量的价值不是告诉你新结论，而是给你的结论配上可辩护的置信度。**

**ANN 的应用领域清单**（讲义只给了四个标题词，老师全部展开了，这段对写 assessment 选题很有用）：

| 领域 | 具体用法 |
|---|---|
| **Woodland management（林业管理）** | 分析野生动物或野火造成的破坏范围、林木**再生格局（regrowth patterns）** |
| **Tree surveys（树木调查）** | 老师直接点名「**you did a tree survey back in the first year**」——量树间距离，用 ANN 判断是随机、聚集还是离散。**人工种植的林子不会是随机格局** |
| **Palaeoecology（古生态）** | 判断古生物群落是否**群居（gregarious behavior）**。**若呈离散格局，可能指示资源短缺、个体间竞争，彼此尽量拉开距离** |
| **Petrology / Mineral textures（岩石学 / 矿物结构）** | 分析矿物颗粒之间的空间关系，反推**结晶过程的化学与物理条件** |
| **Earthquakes（地震）** | 主震后会出现余震丛集，可用聚集分析**定位主震位置**，或**验证某批地震确实与该主震相关** |

**Local Moran's I 的口头补充**：
- 老师承认这个分类「that's quite complicated」，然后逐类拆解（见 2.8）。
- 放大图中 **0.062 ppm 的 HL 异常值**：「there might be a reason why that concentration is very high. We would need... further investigation.」
- 明确指出它的两个短板，这是引出 Gi\* 的理由：**（a）不给概率；（b）用的是 arbitrary cutoff（任意界限）来定义什么算「高」什么算「低」。**

**Gi\* 的口头补充**：
- 「the dark blue points that you can see indicates a **cold spot with a 99 percent level of confidence**. So you can be 99 percent confident that that little cluster was not caused by just a random chance alone.」

**KDE 的口头补充（这段讲得最细，讲义几乎全是标题）**：
- **输入输出的转换过程**被讲得很完整：「you start off with some **vector data, which are points**... it converts that into a **grid of cells** and then associates each cell with some ozone concentration of a certain probability... **you produce a raster as an output**.」
- **kernel 是什么**：「a kernel is just a **circle that's centered on the location**. And then it applies some kind of function to that kernel. So most commonly it fits a **Gaussian distribution** at that point, but there are **other types of functions** that you can use depending on what kind of data you have.」
- **叠加的直觉**：「lots of Gaussian distribution functions, each one of these at a location where you've made a measurement x, **all overlapping with each other**, and then you're **adding these together** to give you an overall shape to your surface.」
- **Bandwidth 的定义**：「some what we call **bandwidth** is the **size of the circle** around each point」。
- **KDE 与 Gi\* 的关系与差别（重要）**：「in some ways it's quite similar to the Getis-Ord, **however, this time you're not given a probability, it's just a surface that you're creating**.」
- **KDE 可以对两种东西做**：（a）**只对采样点位置**做 → 得到 sample points/km² 的热图；（b）**对某个属性值**做 → 得到 ppm/km² 的热图。**两者含义完全不同**（这正是 practical 第 7 步要对比的）。
- **KDE 有插值的味道**：「in areas where you haven't got any data, you can kind of perhaps come up with some estimate of what the ozone concentration would be. So it's a little bit like an **interpolation surface**, like we were talking about last week when we were considering kriging.」
- **优化例程**：「most GIS systems have what's called an **optimised routine** or an optimisation routine that try and produce the **best kernel radius** for you.」

---

## 五、Practical 要点

> **本节目标：不打开原教程也能在 ArcGIS Pro 里从头重做一遍。**
> 教程来源：originally developed by **ESRI training — Spatial Analysis with ArcGIS Pro**。

### 5.0 任务总览

用**加州大气臭氧监测数据**，依次跑完五类空间统计工具，并对比它们的结论：

Directional Distribution（方向趋势）→ Average Nearest Neighbor（点位是否随机）→ Spatial Autocorrelation / Global Moran's I（值是否聚集）→ Hot Spot Analysis / Gi\*（聚集在哪、多可信）→ Kernel Density（密度面）→ Challenge：IDW 与 kriging 插值面。

### 5.1 Step 1 — 数据准备与环境设置

**背景**：美国 EPA 负责监测加州大气臭氧浓度，各监测站上报浓度。数据集 **`O3_Sep06_3pm`** 由 **California Air Resources Board** 提供，记录 **2007 年 9 月 6 日 15:00–16:00** 的臭氧浓度，单位 **ppm（parts per million）**。

**操作**：

1. 启动 **ArcGIS Pro**，**新建一个 project**（例如命名为 `ozone`）。
2. **Add Data** → 数据源选 **ArcGIS Online** → 搜索 **`California_Ozone_Map`** → 添加该 **feature layer**。
3. 打开 `O3_Sep06_3pm` 图层的 **Attribute Table** 检查数据。
   - 应看到 **167 个 monitoring stations**，字段包含站名、**elevations**、以及 **ozone measurements (ppm)**。
   - 该图层默认按 **OZONE** 字段符号化（symbolized using the OZONE field）——地图上已经能肉眼看出高低臭氧的视觉簇。
4. **设置分析环境，把分析范围限制在加州边界内**（这一步不做，后面所有面状输出都会溢出州界）：
   - **Analysis** 选项卡 → 点 **Environments**。
   - **Extent**：`Same As Layer` → **`ca_outline`**
   - **Mask**：**`ca_outline`**
   - 点 **OK**。
5. **Save** 工程。

> 📎 背景补充：**Extent** 控制处理范围的矩形边界，**Mask** 控制栅格输出中哪些像元参与计算/被保留——两者都设成 `ca_outline`，才能既限定范围又裁出加州的真实轮廓。**Mask 属于 Spatial Analyst 的环境设置，主要对栅格结果（如 Kernel Density）生效。** 材料只写了要设，没说各自作用。

### 5.2 Step 2 — Directional Distribution（标准差椭圆）

**目的**：识别臭氧数据的**方向趋势（directional trends）**。

**工具**：**Directional Distribution (Standard Deviational Ellipse)**

**菜单路径**：**Analysis** 选项卡 → **Tools** → 打开 **Geoprocessing** 窗格 → 搜索框输入 **`direction`** → 打开该工具。

**参数（第一次运行）**：

| 参数 | 值 |
|---|---|
| **Input Feature Class** | `O3_Sep06_3pm` |
| **Output Feature Class** | `Ellipses` |
| **Ellipse Size** | **1 Standard Deviation** |
| **Weight Field** | **`OZONE`** |

点 **Run**。

**结果判读（教程给的原理说明，考点）**：
> "When the underlying spatial pattern of features is concentrated toward the centre with fewer features toward the periphery, **one standard deviational ellipse polygon will cover approximately 63 percent of the features**. The ellipse indicates a **directional trend** that is based on the orientation of the sample points."

**参数（第二次运行，做对比）**：

1. 在 **Contents** 窗格里把 **`Ellipses`** 图层**关掉（turn off）**。
2. 回到 **Geoprocessing** 窗格，修改：

| 参数 | 值 |
|---|---|
| **Output Feature Class** | `Ellipses2` |
| **Ellipse Size** | **2 Standard Deviations** |

点 **Run**。

**结果判读**：选 2 个标准差会**纳入更多样点，得到一个更大的椭圆，但方向趋势与 1 个标准差的椭圆相似**（similar directional trend）。**——这正是「椭圆大小 = 覆盖比例，椭圆方向 = 数据趋势，两者独立」的实证。**

最后把 **`Ellipses2`** 也 **turn off**。

> 📎 背景补充：**Weight Field 设成 OZONE 意味着椭圆是按臭氧浓度加权的**——高浓度的站点对椭圆的位置和形状贡献更大。如果 Weight Field 留空，得到的就是纯粹的**站点位置分布椭圆**。教程未解释这一点，但这决定了椭圆到底在描述「站点在哪」还是「臭氧在哪」。

### 5.3 Step 3 — Average Nearest Neighbor（平均最近邻）

**目的**：判定**要素位置（feature locations）**的聚集或离散程度。

**前置操作（不能跳过）**：ANN 工具需要**面积**参数，要先去取加州的面积值。

1. 在 **Contents** 窗格中打开 **`ca_outline`** 图层的 **Attribute Table**。
2. **记下 `Shape_Area` 的值**（后面要手输进去）。

**工具**：**Average Nearest Neighbor**

**菜单路径**：**Geoprocessing** 窗格 → 点 **Back** 按钮返回 → 搜索框输入 **`average`** → 打开工具。

**参数**：

| 参数 | 值 |
|---|---|
| **Input Feature Class** | `O3_Sep06_3pm` |
| **Generate Report** | **勾选 ✅**（不勾就看不到那张钟形曲线图） |
| **Area** | **手工输入刚才记下的 `Shape_Area` 值** |

点 **Run**。

**⚠️ 输出形式**：**"The output from the Average Nearest Neighbor tool is a report, not a feature class."**（是报告，不是图层——地图上不会多出任何东西，别以为工具没跑成功。）

**查看结果**：把光标悬停在 **View Details** 上 → 打开 **Report File（一个 HTML 文件）**。

**结果判读（教程原文）**：
- **H₀**：the locations of the features are randomly distributed.（各站点位置随机分布）
- 返回的 **z-score = −3.30**，在 **99% 置信水平下统计显著**，意味着**这批臭氧监测点的空间格局由随机造成的可能性小于 1%**。
- 看那条正态曲线：**z-score 落在左侧尾部（蓝色区）→ 数据是 clustered。**

**关掉报告，回到 ArcGIS Pro。**

> ⚠️ 教程此处写的是 "i.e. **p < 0.1**"，这是笔误，正确应为 **p < 0.01**（见文末勘误表）。

### 5.4 Step 4 — Spatial Autocorrelation（Global Moran's I）

**为什么要跑这一步**（教程原话，是本周最重要的逻辑衔接句）：
> "The Average Nearest Neighbor tool **only looks at feature locations**. If you want to determine if there is clustering in the **attribute values** (i.e. ozone concentrations) at those locations, you must run the **Spatial Autocorrelation (Moran's I)** tool."

**工具**：**Spatial Autocorrelation (Global Moran's I)**

**菜单路径**：**Geoprocessing** 窗格 → 返回搜索结果 → 搜索 **`spatial`** → 打开该工具。

**参数（本周最需要背下来的一组）**：

| 参数 | 值 | 说明 |
|---|---|---|
| **Input Feature Class** | `O3_Sep06_3pm` | |
| **Input Field** | **`OZONE`** | 这就是「用属性值」的体现 |
| **Generate Report** | **勾选 ✅** | |
| **Conceptualization Of Spatial Relationships** | **Fixed Distance Band** | **空间关系概念化——即空间权重矩阵的定义方式** |
| **Standardization** | **Row** | **行标准化** |

点 **Run**。

**⚠️ 会弹出一个 warning，这是正常的，教程专门解释了它**：

> "The warning is due to **not providing a distance band or threshold distance**. The software calculates a **default value of 154,019 meters, or roughly 95 miles**, to ensure that **every feature has at least one neighbor**."

**这段解释里藏着本周最核心的方法论提醒**，教程用了一个绝妙的反例：
> "If you were investigating **crime clusters**, a distance of **800 meters** might work because that is the average size of a **city block**. When choosing the appropriate distance threshold, it is often based on **common sense, theory, and the field that you are working in**."

——**距离阈值不是软件替你决定的技术参数，而是由你的研究对象的空间过程尺度决定的科学判断。** 加州臭氧的合理尺度是百公里级（大气传输），城市犯罪的合理尺度是百米级（街区）。**默认值只保证「每个要素至少有一个邻居」，它不保证这个尺度对你的问题有意义。**

**查看结果**：悬停 **View Details** → 打开 **`MoransI_Result`** HTML 文件。

**结果判读（教程原文）**：
> "The **high z-score and low p-value** indicates that you can **reject the null hypothesis** and conclude that the spatial distribution of high values and low values in the data is **more spatially clustered than would be expected if the underlying spatial processes were random**."

（老师课上给的对应数值是 **z ≈ 15**，p 极小，远在右尾之外。）

**关掉报告，返回 ArcGIS Pro。**

> 📎 背景补充：**Standardization: Row（行标准化）的作用**——把每个要素的权重按其邻居数量归一化，使每行权重之和为 1。这样**邻居多的要素不会仅仅因为「朋友多」就在统计量里占更大分量**。ESRI 官方建议：当要素分布本身不均匀（比如加州监测站南密北疏）或采用固定距离带时，**几乎总应该用 Row standardization**。教程只让你选 Row，没说为什么。

> 📎 背景补充：**Conceptualization of Spatial Relationships 的其他选项**（教程只用了 Fixed Distance Band 一个，但这是本周头号考点，需要知道有哪些替代方案）：
> | 选项 | 中文 | 定义邻居的方式 |
> |---|---|---|
> | **Fixed Distance Band** | 固定距离带 | 阈值内的都是邻居，权重相等；阈值外权重为 0（教程所用） |
> | **Inverse Distance** | 反距离 | 所有要素都是邻居，但权重随距离衰减（越远影响越小） |
> | **Inverse Distance Squared** | 反距离平方 | 同上，但衰减更快 |
> | **Zone of Indifference** | 无差异区 | 阈值内权重相等，阈值外按反距离衰减——是前两者的折中 |
> | **K Nearest Neighbors** | K 最近邻 | 固定取最近的 k 个作为邻居，**保证每个要素邻居数相同**，适合点分布极不均匀的情况 |
> | **Contiguity Edges Only / Edges Corners** | 邻接（共边 / 共边或共角） | **仅适用于面要素（polygon）**，按是否共享边界判定 |
> | **Get Spatial Weights From File** | 从文件读取 | 使用自定义的权重矩阵文件 |

### 5.5 Step 5 — Hot Spot Analysis（Getis-Ord Gi\*）

**目的**：确定**聚集发生在哪里**（"to determine **where** the clusters are located"）。

**工具**：**Hot Spot Analysis (Getis-Ord Gi\*)**

**菜单路径**：**Geoprocessing** 窗格 → 搜索 **`hot`** → 打开工具。

**参数**：

| 参数 | 值 |
|---|---|
| **Input Feature Class** | `O3_Sep06_3pm` |
| **Input Field** | **`OZONE`** |
| **Output Feature Class** | `HotSpots` |
| **Distance Band Or Threshold Distance** | **`150000`**（单位：米） |
| 其余参数 | **Accept all remaining default settings**（全部接受默认） |

点 **Run**。

教程对这个数值的说明是：「150000 is the value that the Spatial Autocorrelation tool used as the threshold distance.」
> ⚠️ 但上一步教程自己写的默认值是 **154,019 m**，两者对不上。见文末勘误表。**实际操作时按 150000 输入即可**，这是一个取整后的近似值，不影响本练习的结论——但你应当意识到**这两个数不相等**这件事本身。

**结果判读**：

1. 在 **Contents** 窗格里把 **`O3_Sep06_3pm`** 图层 **turn off**（否则原始点会盖住结果）。
2. 观察：**统计显著的高臭氧热点位于 north-central California（加州中北部）**。含义是「higher ozone values **surrounded by** other higher ozone values」——**注意这个 "surrounded by"，热点从来不是关于单个点，而是关于点及其邻域。**
3. **放大到中部区域，点选几个红点**：OZONE 值都彼此接近且相对较高，**约 0.08 到 0.10**。
4. **放大到加州南部的冷点（蓝点）区域，点选几个点**：大多数冷点的臭氧值在 **0.05 或更低**。
5. 在 **Contents** 窗格中**右键 `HotSpots` → Attribute Table**，查看每个点的统计量。

**属性表的读法（教程原文，直接就是考点）**：
> "Each point is assigned a value for **z-score and p-value**... When you have a **high z-score and a low p-value**, it indicates **spatial clustering of high values**. The **lower or negative z-scores** in combination with a **lower p-value** indicate **spatial clustering of low values**."

**——即：z 大正 + p 小 = hot spot；z 大负 + p 小 = cold spot；p 大 = 不显著（无论 z 是正是负）。**

**关闭属性表。**

> 📎 背景补充：Gi\* 结果的属性表中，ESRI 生成的字段通常命名为 **`GiZScore`**、**`GiPValue`**、**`Gi_Bin`**（后者就是 −3 到 +3 的置信度分档，±3 = 99%、±2 = 95%、±1 = 90%、0 = 不显著）。教程只说了「z-score 和 p-value 被加到属性表里」，未给字段名。

### 5.6 Step 6 — Kernel Density（密度面 / 热图）

**目的**：把 **hot spot analysis 的结果**与**密度面（density surface / heat map）**做对比——**这一步的设计意图就是让你亲眼看到两者不是一回事。**

**准备**：在 **Contents** 窗格里把 **`HotSpots`** 图层 **turn off**。

**工具**：**Kernel Density**

**菜单路径**：**Geoprocessing** 窗格 → 搜索 **`kernel`** → 打开工具。

**⚠️ 先设环境，再设参数**：

1. 打开工具后，**在窗格顶部点 `Environments` 选项卡**。
2. 把 **Cell Size** 设为 **Maximum Of Inputs**。
3. 回到窗格顶部点 **`Parameters`** 选项卡，设置：

**参数（第一次运行 —— 只看采样点密度）**：

| 参数 | 值 |
|---|---|
| **Input Point Or Polyline Features** | `O3_Sep06_3pm` |
| **Population Field** | **`NONE`** |
| **Output Raster** | `Density` |
| 其余 | 接受默认 |

点 **Run**。

**结果判读（第一次）**：
> "The density surface **aligns well with the sample points, as it should**, because you **did not use a population field and only used the point location** to create the surface. However, the **symbology of the heat map makes it difficult to interpret patterns**."

**——Population Field 设为 NONE 时，KDE 画的是「监测站有多密集」，和臭氧浓度毫无关系。**

**对比实验（这是本步骤的重点，务必做）**：

1. 在 **Contents** 窗格中**打开 `HotSpots` 图层**，**关掉 `O3_Sep06_3pm` 图层**。
2. 在地图上**放大到加州最北端**——那里采样点密度很高。
3. 观察并记住这个结论（教程原文）：
   > "The hot spots at a **99% confidence interval are NOT all located in the high-density area of the points**. The density surface is symbolized based on **density of features, not ozone values**. Comparing a density surface to a statistical result demonstrates **how spatial statistics quantify spatial patterns and how heat maps do not**."

**——这是整个 practical 最重要的一句话：热图漂亮，但它不做统计推断。点密的地方不等于值高的地方。**

**参数（第二次运行 —— 看臭氧浓度密度）**：

重跑 Kernel Density，只改一个参数：

| 参数 | 值 |
|---|---|
| **Population Field** | **`OZONE`** |

**结果**：得到一张**臭氧浓度密度面**，单位是 **ppm/km²**。把它与刚才的采样点密度图（单位 **number/km²**）对比。

**Save** 工程。

> **对应讲义的两张图**：讲义里的 "Heat map using kernel density: **sample point**"（图例 `Sample Points (number/km²)`）就是第一次运行的结果；"Heat map using kernel density: **ozone**"（图例 `Ozone (ppm/km²)`）就是第二次的结果。

> 📎 背景补充：**Population Field 这个参数名容易误导**——它跟「人口」无关，指的是「**每个点代表多少量**」的权重字段。设为 NONE 就是每个点计 1（纯点位密度），设为 OZONE 就是每个点按其臭氧值加权。教程未解释这个命名。

> 📎 背景补充：**Cell Size 设为 Maximum Of Inputs 的用意**是让输出栅格的像元大小与输入数据中最粗的那个保持一致，避免生成一张分辨率虚高、体积巨大却没有额外信息的栅格。教程只给了设置，未说理由。

### 5.7 Step 7 — Challenge Exercise（衔接 W04）

**任务**：用**上周 practical 学的空间插值方法（IDW 和 kriging）**，从监测站点位生成**连续的臭氧浓度面**。

**要点清单**：

1. **裁到加州边界**：用 **Clip** 把分析限制在州界内。
2. **IDW**：
   - **要优化 power（幂指数）**（"remember to **optimise your power**"）。
   - **记录 mean 和 RMSE**（均值误差与均方根误差）——这是评价插值质量的指标。
3. **Kriging**：
   - **前提检查**：kriging **假定数据服从正态分布（normally distributed）**。
   - **做一张 ozone 值的 histogram（直方图）检查是否正态**。
   - 若不正态，**试哪种 transformation（变换）能把它变正态**。
   - **变换要在 kriging 的选项里做**，而且**变换之后可能需要换模型（model）**。
   - **老师自己试过的两组配置**（教程原文，直接可用）：
     - **transformation = "none" + "stable" model**
     - **"log" transform + "exponential" model**（作为 semivariogram 的最佳拟合）
     - **"Results were similar."**（两组结果相近）
   - **必须额外生成一张 standard errors 的面**（"Remember to make a surface of **standard errors** as part of your kriging analysis."）——**误差面和预测面同等重要。**

> ⚠️ 教程正文把 kriging 一律拼作 "krigging"（多了一个 g），正确拼法是 **kriging**（W04 讲义拼写正确）。见勘误表。

### 5.8 常见报错与卡点处理

> 📎 背景补充：以下为**教程未写**的常见问题应对，供实操时参照。

| 现象 | 原因 | 处理 |
|---|---|---|
| 跑完 ANN / Moran's I 后地图上什么都没变 | **这两个工具输出的是 HTML 报告，不是 feature class** | 悬停 **View Details** 打开报告；确认运行前已勾选 **Generate Report** |
| Spatial Autocorrelation 弹 warning 提示距离带 | **未填 Distance Band**，软件自动取默认值 | 这是**预期行为**，教程明确说了。想消除就手动填一个有依据的阈值 |
| 报「某些要素没有邻居」类的警告 | 距离阈值设得太小 | 增大 **Distance Band**，或改用 **K Nearest Neighbors** |
| Kernel Density 结果溢出加州边界 | **Environments 的 Extent / Mask 没设** | 回 Step 1 重设 `ca_outline` |
| Kernel Density 灰掉不能用 | **Spatial Analyst extension 未启用** | 检查 license / extension |
| Average Nearest Neighbor 结果与预期相反 | **Area 参数填错或单位不匹配** | 确认 `Shape_Area` 的值抄完整，且其单位（通常为平方米）与图层坐标系一致 |
| 距离参数单位不确定 | 距离带单位取决于图层的**投影坐标系** | 本练习用米；若图层是地理坐标系（度），**必须先投影**，否则距离毫无意义 |

---

## 六、易错点 / 重点难点

### 6.1 🥇 头号陷阱：空间权重矩阵的设定会得出相反的结论，却常被当作「默认值直接用」

这是本周**最重要、也最容易被忽略**的一点。

**问题在哪**：Moran's I 和 Gi\* 的公式里都有 $w_{ij}$。**$w_{ij}$ 变了，统计量就变了，结论就可能反过来。** 而在 ArcGIS Pro 里，你只要不管它，软件就会替你**默认**一个值——本练习里就是那个 **154,019 m**。

**教程自己给出了最好的警醒**：加州臭氧用 154 km 合理，**城市犯罪要用 800 m（一个街区的平均尺寸）**。同一份数据、同一个工具，换个距离阈值就是完全不同的分析。

**必须记住的三句话**：
1. **默认值只保证「每个要素至少有一个邻居」，它不保证这个尺度对你的科学问题有意义。**
2. 选阈值的依据是 **"common sense, theory, and the field that you are working in"**——即**你研究的空间过程本身的特征尺度**。
3. **报告结果时必须同时报告你用的 Conceptualization of Spatial Relationships、Distance Band 和 Standardization。** 不写这三项的空间统计结果是不可复现的。

**同一个陷阱的另一副面孔：KDE 的 bandwidth。** 1500 km 和 15 km 用的是同一份数据，画出来一张糊成一片、一张碎成椒盐。**bandwidth 与 distance band 在本质上是同一类参数——它们都在定义「多远算近」。**

### 6.2 z-score 正负方向：ANN 与 Moran's I **正好相反**

| 工具 | 量的是什么 | 负 z | 正 z |
|---|---|---|---|
| **Average Nearest Neighbor** | **距离** | **Clustered（聚集）** | Dispersed（离散） |
| **Global Moran's I** | **相似性** | Dispersed（离散） | **Clustered（聚集）** |
| **Getis-Ord Gi\*** | **邻域值高低** | **Cold spot（低值簇）** | **Hot spot（高值簇）** |

**记忆锚点（理解了就不用背）**：
- ANN 量距离，**聚集 = 距离变近 = 观测距离小于期望 = R < 1 = z 为负**。
- Moran's I 量相似性，**聚集 = 相似性变高 = I 大于期望 = z 为正**。

**别把 R 的方向记反**：**R < 1 是聚集**，不是离散。（直觉：挤在一起 → 邻居更近 → 距离更小 → 比值更小。）

### 6.3 Getis-Ord Gi\* 与 Local Moran's I 的结果含义混淆

**这两个都产生地图、都用属性值、都告诉你「在哪里」，但回答的是不同的问题。**

| | **Local Moran's I**（Cluster and Outlier Analysis） | **Getis-Ord Gi\***（Hot Spot Analysis） |
|---|---|---|
| 问的问题 | 这个点**和它的邻居像不像**？ | 这一片的值**整体上是高还是低**？ |
| 输出类别 | **HH / LL / HL / LH**（四类） | **Hot spot / Cold spot / Not significant** |
| **能不能找异常值** | **能**——HL 和 LH 就是异常值 | **不能** |
| 老师指出的短板 | **不给概率**，用 **arbitrary cutoff** 定义高低 | —— |
| 带置信度分级 | 否 | **是**（90 / 95 / 99%） |

**最容易错的一条**：一个孤立的极高值点，在 **Local Moran's I 里是显眼的 HL outlier**，但在 **Gi\* 里可能完全不显著**（因为它周围全是低值，把邻域和拉平了）。**所以「Gi\* 没标出来」不等于「那里没有异常」。**

### 6.4 统计显著 ≠ 因果，也 ≠ 重要

- **显著性只说明「不太可能是随机造成的」，不说明「是什么造成的」。** 老师在 Local Moran's I 那个 0.062 的异常点上的态度是标准示范：「there **might be a reason** why that concentration is very high. **We would need further investigation.**」——统计量提出问题，不回答问题。
- **p 值的严格含义**是：**在 H₀ 为真的前提下，观察到当前或更极端结果的概率。** 它**不是**「H₀ 为假的概率」，也**不是**「结论正确的概率」。老师课上说的「you can be 90% confident that your sample distribution is not part of this parent random distribution」是教学上的通俗化表述，写正式报告时不要照抄这个措辞。
- **样本量足够大时，任何微小的偏离都会变显著。** 显著的效应可能小到毫无实际意义。
- 严格的统计学表述是 **"reject" 或 "fail to reject"（拒绝 / 不能拒绝）H₀**，**不是 "accept H₀"（接受零假设）**。讲义写的是 "accept or reject the null hypothesis"，这是措辞上的不严谨；**Practical 的写法 "rejecting or not rejecting" 才是标准的**。**你永远无法证明 H₀ 为真，只能说「证据不足以推翻它」。**

### 6.5 样本量与代表性的问题

- **抽样不具代表性 → 结论系统性错误**，这不是靠增大样本量能修正的（老师原话："our answer is going to be **systematically wrong**"）。
- **点数太少时，检验没有效力（power）**：$E(I) = -1/(n-1)$ 在 n 很小时会明显偏离 0，方差也很大，几乎什么都检不出显著。
- **Gi\* 的邻域内点太少时结果不可靠**（📎 背景补充：ESRI 一般建议每个要素**至少有 8 个邻居**，工具本身在邻居过少时会给警告。教程未提及此建议）。
- 抽样设计与统计方法必须匹配：如果你的样点本身就是**成群（clustered）抽样**得来的，那么用 ANN 去检验「点位是否随机」几乎必然得到「聚集」——**你检验出来的是自己的抽样设计，不是自然界的格局。**

### 6.6 边界效应（Edge effect）

W04 讲义在「Sources of error in interpolation」里已经给了定义：
> "**Edge effects**: distortions of the interpolated values near the boundary of the study area due to the **lack of sample data outside the area**."

**在空间统计里同样成立且更隐蔽**：位于研究区边缘的要素，**其邻域有一部分落在研究区外，那里没有数据**，于是它的邻居数天然比内部要素少。后果：
- **ANN 的观测平均距离被系统性高估**（边缘点找不到本该更近的域外邻居）→ R 偏大 → **聚集程度被低估**。
- **Gi\* 在边缘处的估计不稳定**，边界附近的热点/冷点判定应当谨慎解读。
- 本周 practical 用 Mask 把分析限制在 `ca_outline` 内，**这本身就制造了一条人为边界**——加州州界之外当然也有臭氧，只是不在数据里。

📎 背景补充：常见的缓解手段是 **guard area / buffer zone**（在研究区外围保留一圈数据只作邻居用、不参与统计）或使用带 edge correction 的估计量。**材料未涉及此类方法。**

### 6.7 KDE 的三个常见误解

1. **KDE 不做统计推断**——它**不给 p 值、不给置信度**。老师说得很明确：「this time you're not given a probability, **it's just a surface**」。**不要把好看的红色热图当成「统计显著的热点」。**
2. **Population Field = NONE 与 = OZONE 是两个完全不同的分析。** 前者画的是「站点有多密」，后者画的是「臭氧有多浓」。Practical 第 6 步专门用「加州最北端点很密、但 99% 的热点并不都在那里」来演示这个区别。
3. **密度面依赖尺度（Density is scale dependent）**——见 6.1。

### 6.8 操作层面的细节坑

| 坑 | 说明 |
|---|---|
| 忘记勾 **Generate Report** | ANN 和 Moran's I 就只剩几个数字，看不到那张关键的钟形曲线判读图 |
| 忘设 **Environments（Extent + Mask）** | Kernel Density 的栅格会溢出加州边界 |
| **Area 参数抄错** | ANN 的期望距离与面积直接相关，面积错则 R 的方向可能翻转（见 3.3） |
| 以为 ANN 会出图 | **它只出报告**，教程和老师都特别强调过 |
| 混淆 **Standard Distance（圆）** 与 **Standard Deviational Ellipse（椭圆）** | 前者把 X、Y 合并算，后者分开算 |
| 混淆 **Ellipse Size** 的含义 | 1 SD 覆盖约 63% 的要素，2 SD 覆盖更多——**它改的是覆盖比例，不是方向趋势** |
| **Distance Band 的单位** | 取决于图层坐标系；地理坐标系（度）下的距离阈值毫无意义，必须先投影 |
| kriging 前不检查正态性 | kriging **假定正态分布**，不检查直接跑等于跳过了方法的前提 |
| kriging 只出预测面、不出误差面 | Challenge Exercise 明确要求 **standard errors surface** |

---

## 七、本周术语表

### 7.1 统计与概念术语

| 英文 | 中文 | 说明 |
|---|---|---|
| **Spatial statistics** | 空间统计 | 把空间与空间关系直接写入数学计算的统计方法 |
| **Descriptive statistics** | 描述统计 | 总结数据，输出可以是统计量或图形 |
| **Inferential statistics** | 推断统计 | 基于样本推断总体性质 |
| **Population / Sample** | 总体 / 样本 | |
| **Representative sample** | 代表性样本 | 一切统计推断的前提 |
| **Spatial sampling design** | 空间抽样设计 | |
| **Random sampling** | 随机抽样 | 每个位置被选中机会均等且相互独立 |
| **Stratified sampling** | 分层抽样 | 按共有特征分层，**各层按面积比例抽样** |
| **Systematic sampling** | 系统抽样 | 规则格网布点 |
| **Clustered sampling** | 成群抽样 | 先随机选小区，再在小区内密集布点 |
| **Transect** | 样带 | 沿线布点 |
| **Central tendency** | 集中趋势 | |
| **Mean Center** | 平均中心 | X、Y 坐标的平均 |
| **Dispersion** | 离散程度 | |
| **Standard Distance** | 标准距离 | 空间版标准差，**X、Y 合并计算 → 圆** |
| **Standard Deviational Ellipse** | 标准差椭圆 | **X、Y 分开计算 → 椭圆**；1 SD 覆盖约 63% 的要素 |
| **Direction / Directional trend** | 方向 / 方向趋势 | 空间数据独有的第三个描述维度 |
| **Complete Spatial Randomness (CSR)** | 完全空间随机 | pattern analysis 工具的零假设内容 |
| **Null hypothesis (H₀)** | 零假设 | **永远陈述为「无空间格局 / 无关系」** |
| **Alternative hypothesis (Hₐ)** | 备择假设 | H₀ 的对立面 |
| **Significance / Hypothesis testing** | 显著性检验 / 假设检验 | |
| **Statistical significance** | 统计显著性 | 观测格局不太可能仅由偶然产生的概率 |
| **z-score** | z 分数 / 标准分 | 偏离均值多少个标准差；标准化的作用是**去除单位** |
| **p-value** | p 值 | H₀ 为真时得到当前或更极端统计量的确切概率 |
| **Critical value** | 临界值 | ±1.65 (90%)、±1.96 (95%)、±2.58 (99%) |
| **Confidence level** | 置信水平 | 90% / 95% / 99% |
| **Spatial autocorrelation** | 空间自相关 | Tobler 第一定律的统计度量 |
| **Tobler's First Law of Geography** | 托布勒地理学第一定律 | 「Everything is related to everything else, but near things are more related than distant things」 |
| **Positive spatial autocorrelation** | 正空间自相关 | 相似值聚集（clustered，like with like） |
| **Negative spatial autocorrelation** | 负空间自相关 | 不相似值相邻（dispersed，like with unlike） |
| **Clustered / Random / Dispersed** | 聚集 / 随机 / 离散 | 三种空间格局 |
| **Nearest Neighbour Analysis (NNA)** | 最近邻分析 | **只用位置，不用属性值** |
| **Nearest Neighbor Ratio (R)** | 最近邻比值 | 观测平均距离 ÷ 随机期望平均距离；**R<1 聚集、R≈1 随机、R>1 离散** |
| **Global Moran's I** | 全局莫兰指数 | 全研究区一个数，用属性值，**无地图输出** |
| **Local Moran's I** | 局部莫兰指数 | 显示聚集位置与局部异常值，**有地图输出** |
| **High-High (HH) cluster** | 高—高聚集 | 高值被高值包围 |
| **Low-Low (LL) cluster** | 低—低聚集 | 低值被低值包围 |
| **High-Low (HL) outlier** | 高—低异常值 | 高值落在低值群中 |
| **Low-High (LH) outlier** | 低—高异常值 | 低值落在高值群中 |
| **Getis-Ord Gi\*** | 盖蒂斯—奥德 Gi\* 统计量 | 热点分析；**Gi\* 本身即 z-score**；星号表示邻域含自身 |
| **Hot spot / Cold spot** | 热点 / 冷点 | 高值的显著聚集 / 低值的显著聚集 |
| **Kernel Density Estimation (KDE)** | 核密度估计 | 点 → 密度面（栅格）；**不给概率** |
| **Kernel** | 核 | 以估计位置为中心的圆或加权函数 |
| **Bandwidth / Kernel radius** | 带宽 / 核半径 | 核的作用范围；过大→过度平滑，过小→椒盐效应 |
| **Salt and pepper effect** | 椒盐效应 | 带宽过小导致的碎斑状结果 |
| **Heat map** | 热图 | KDE 的可视化产物 |
| **Density surface** | 密度面 | |
| **Spatial weights / $w_{ij}$** | 空间权重 | 决定「谁是谁的邻居、权重多大」 |
| **Edge effect** | 边界效应 | 研究区边缘因缺少域外数据造成的畸变 |
| **Spatial interpolation** | 空间插值 | W04 内容；IDW（确定性）与 kriging（地统计） |
| **IDW (Inverse Distance Weights)** | 反距离权重 | |
| **Kriging** | 克里金法 | **假定数据正态分布** |
| **Semivariogram** | 半变异函数图 | kriging 用来定义空间结构的工具 |
| **RMSE (Root Mean Square Error)** | 均方根误差 | 插值精度指标 |
| **📎 Geary's C** | 吉尔里 C 指数 | **材料未涉及**；C<1 正自相关、C>1 负自相关，与 Moran's I 方向相反 |
| **📎 LISA (Local Indicators of Spatial Association)** | 局部空间关联指标 | **材料未涉及**；Local Moran's I 属于此类 |
| **📎 Ripley's K function** | 里普利 K 函数 | **材料未涉及**；在多个距离尺度上检验聚集 |
| **📎 GWR (Geographically Weighted Regression)** | 地理加权回归 | **材料未涉及** |

### 7.2 ArcGIS Pro 工具与界面术语（保留英文原名）

| 工具 / 界面项 | 中文说明 | 出处 |
|---|---|---|
| **Geoprocessing** pane | 地理处理窗格（Analysis 选项卡 > Tools） | 全流程入口 |
| **Analysis** tab | 分析选项卡 | |
| **Environments** | 环境设置 | 设 Extent、Mask、Cell Size |
| **Extent: Same As Layer** | 处理范围与某图层一致 | 设为 `ca_outline` |
| **Mask** | 掩膜 | 设为 `ca_outline`，限定栅格输出轮廓 |
| **Cell Size: Maximum Of Inputs** | 像元大小取输入中最粗者 | Kernel Density 的环境设置 |
| **Contents** pane | 内容窗格（图层列表） | 开关图层、右键属性表 |
| **Attribute Table** | 属性表 | |
| **Add Data → ArcGIS Online** | 从 ArcGIS Online 添加数据 | 搜 `California_Ozone_Map` |
| **Feature layer / Feature class** | 要素图层 / 要素类 | |
| **Directional Distribution (Standard Deviational Ellipse)** | 方向分布（标准差椭圆）工具 | 搜索关键词 `direction` |
| **Ellipse Size** | 椭圆大小 | `1 Standard Deviation` / `2 Standard Deviations` |
| **Weight Field** | 权重字段 | 设为 `OZONE` |
| **Average Nearest Neighbor** | 平均最近邻工具 | 搜索关键词 `average`；**输出是 report 不是图层** |
| **Generate Report** | 生成报告（复选框） | 不勾就看不到判读图 |
| **Area** | 面积参数 | 手输 `ca_outline` 的 **Shape_Area** |
| **Shape_Area** | 图形面积字段 | |
| **View Details** | 查看详细信息 | 悬停后可打开 HTML 报告 |
| **Report File (HTML)** | 报告文件 | |
| **Spatial Autocorrelation (Global Moran's I)** | 空间自相关（全局莫兰指数）工具 | 搜索关键词 `spatial` |
| **Input Field** | 输入字段 | 设为 `OZONE` |
| **Conceptualization Of Spatial Relationships** | 空间关系概念化 | **本周头号参数**；本练习用 `Fixed Distance Band` |
| **Fixed Distance Band** | 固定距离带 | 阈值内为邻居、权重相等 |
| **Standardization: Row** | 行标准化 | 每行权重和归一为 1 |
| **Distance Band Or Threshold Distance** | 距离带 / 阈值距离 | Gi\* 里填 `150000`（米） |
| **MoransI_Result** | Moran's I 结果报告文件名 | HTML |
| **Hot Spot Analysis (Getis-Ord Gi\*)** | 热点分析工具 | 搜索关键词 `hot`；输出 `HotSpots` 要素类 |
| **Kernel Density** | 核密度工具 | 搜索关键词 `kernel` |
| **Input Point Or Polyline Features** | 输入点或折线要素 | |
| **Population Field** | 「总量」字段（权重字段） | `NONE` = 只算点位密度；`OZONE` = 按臭氧值加权 |
| **Output Raster** | 输出栅格 | 命名 `Density` |
| **Clip** | 裁剪工具 | Challenge Exercise 中用来裁到州界 |
| **Parameters / Environments** tabs | 工具窗格内的「参数 / 环境」两个页签 | |
| `O3_Sep06_3pm` | 臭氧数据图层（167 站，ppm） | |
| `ca_outline` | 加州边界图层 | |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Practical 5 - Spatial statistics.md`，§4 Run the Average Nearest Neighbor tool，结果判读段 | "the z-score (-3.30) ... is statistically significant at a confidence level of 99 percent (**i.e. p < 0.1**)" | **显著性水平写错**。99% 置信水平对应的是 α = 0.01；p < 0.1 只对应 90% 置信水平，与同句中的「99 percent」和「less than a 1 percent likelihood」自相矛盾。 | 应为 **p < 0.01**。（讲义 OCR 出的报告也给出实际 p-value = 0.000950，确实小于 0.01。） |
| `Practical 5 - Spatial statistics.md`，§5 结尾 与 §6 开头 | §5：软件默认距离带 "**154,019 meters**"；§6：距离带填 "**150000**"，并说明「150000 is the value that the Spatial Autocorrelation tool used as the threshold distance」 | **两个数值不一致**。§6 声称 150,000 就是 §5 里 Spatial Autocorrelation 用的阈值，但 §5 明写的是 154,019 m，两者相差约 4 km。 | 150,000 应理解为 154,019 的**取整近似值**，教程的措辞不准确。严格复现时若要与 Moran's I 保持完全一致，应填 **154019**；填 150000 对本练习结论无影响，但表述应改为「approximately the value used by the Spatial Autocorrelation tool」。 |
| `Practical 5 - Spatial statistics.md`，§6 Run the Hot Spot Analysis tool，放大查看红点一段 | "The OZONE values are all close to one another and are relatively high, around **0.08 to +1.0**." | **数值明显错误**（很可能是 PDF 转换/OCR 造成）。臭氧浓度单位为 ppm，全数据集量级在 0.05–0.10 之间；1.0 ppm 比冷点值高 20 倍，与「values are all close to one another」自相矛盾。 | 应为 **0.08 到 0.10**（即 "0.08 to 0.10"，原文的 "+1.0" 应是 "0.10" 的误识）。 |
| `Practical 5 - Spatial statistics.md`，§8 Challenge Exercise（多处） | "IDW and **krigging**"、"remember that **krigging** assumes..."、"as an option for **krigging**"、"part of your **krigging** analysis" | **拼写错误**，全节一律多写一个 g。W04 讲义 `Lecture 4 - Spatial Analysis.md` 中拼写正确。 | 正确拼写为 **kriging**（源自南非采矿工程师 D. G. Krige 的姓氏）。 |
| `Lecture 5 - Spatial statistics.md`，"z-scores and p-values" 页 | "A **p-value (confidence level)** dictates the critical z-score for rejecting or not rejecting the null hypothesis (H0)." | **术语误用**。p-value 不等于 confidence level。p 值是在 H₀ 为真时得到当前或更极端结果的概率；confidence level = 1 − α（如 α=0.05 对应 95% 置信水平）。同一张 slide 后文写的 "α = 0.05 means a probability of rejecting H0 with 95% confidence" 是正确的，前后不一致。 | 应为「**显著性水平 α（significance level）**决定临界 z 值」，或写成「p-value **与之比较的阈值 α**」。**置信水平 = 1 − α，不是 p 值本身。** |
| `Lecture 5 - Spatial statistics.md`，"Null and alternative hypotheses" 页 | "Significance test – **accept or reject** the null hypothesis." | **统计学措辞不严谨**。在 Neyman–Pearson 框架下，检验的结论只有「reject H₀」和「fail to reject H₀」两种；**「accept H₀」在逻辑上不成立**——缺乏拒绝的证据不等于证明 H₀ 为真。 | 应为 **"reject or fail to reject（不能拒绝）the null hypothesis"**。同课程的 `Practical 5` §1.2 写的是 "rejecting or **not rejecting** the null hypothesis"，措辞正确，可见是讲义 slide 的疏漏。 |
| `EART29102 - 02-Mar-transcript.md`（全篇，自动转写） | "Moran's **eye**"、"**Gettyshawd** / **Gettys Ord** / **Gettys Award** / **GetisOrgGI star**"、"**crigging**"、"Sierra and the **Avada** Mountains"、"Pete **Grinrod**" | **自动语音识别（ASR）造成的专有名词误写**，非授课内容错误。 | 正确写法依次为：**Moran's I**、**Getis-Ord Gi\***、**kriging**、**Sierra Nevada Mountains**、**Pete Grindrod**（Natural History Museum 行星科学家，姓氏标准拼写为 Grindrod）。阅读转写时须自行还原。 |
| `EART29102 - 02-Mar-transcript.md`，Appalachia 案例段 | "this is a compilation of data, I think from **2000 to 2018**. So this is **2008 to 2018**" | 老师口误后已当场自我更正，**转写忠实记录了两个数值**。 | 以后一个 **2008–2018** 为准。此条非材料错误，仅提示阅读时注意。 |
| `EART29102 - 02-Mar-transcript.md`，讲 Appalachia 图配色段 | "these are shown by these different sort of **colors of green** on the map here" | 与 `Lecture 5` 讲义中 Getis-Ord 页的说明「hot spots (**red**) ... Cold spots (**blue**)」不一致。 | 老师此处描述的是首页 Neville et al. (2022) 论文原图（该图配色由论文作者决定，未必是 ArcGIS 默认的红蓝发散配色），并非 ArcGIS Pro 的标准 Gi\* 输出。**ArcGIS Pro 的 Hot Spot Analysis 标准配色是红（hot）—白（不显著）—蓝（cold）。** 此条非错误，仅为避免混淆而记录。 |
| `Practical 5 - Spatial statistics.md`，§4 第二段 | "The Average Nearest Neighbor tool **uses area as a parameter**, so you will copy the area from the ca_outline." | 表述可能造成误解：**Area 在 ArcGIS Pro 中是可选参数（optional）**，不填时工具会自动使用输入要素的**最小外接矩形（minimum enclosing rectangle）**面积。 | 教程的做法（手动填入州界真实面积）是**更严谨的做法**，因为加州形状狭长，其最小外接矩形面积远大于真实面积，会导致期望距离被高估、R 被低估。**但「uses area as a parameter」不应被理解为「必填」。** 此条为表述不精确，非硬错误。 |
