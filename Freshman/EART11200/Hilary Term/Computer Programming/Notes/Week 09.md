# Week 9 — 机器学习入门：聚类分析（无监督）与随机森林（有监督）

> 本周材料：
> - Lecture：`Lecture-9b_25.pdf`（幻灯片，md 提取版）+ `EART11200 - 01-Apr-transcript.md`（课堂录音转写，全课**最后一次 Lecture**）
> - Practical：`Practical_9.ipynb` / `Practical_9.md` — *Practical 9: Pandas to Machine learning*
> - 数据集：`data/forestfires.csv`（葡萄牙森林火灾气象数据）、`data/Frogs_MFCCs.csv`（南美蛙鸣声学特征，带 Family / Genus / Species 三级标签）

---

## 一、本周主题

### 1. 本周学什么

本周把前几周积累的 **pandas 数据处理 + matplotlib/seaborn 可视化 + numpy 数组**串起来，第一次真正走进**机器学习（Machine Learning, ML）**。主线是两条：

| 分支 | 英文 | 本周用到的算法 | 本周数据 |
|---|---|---|---|
| 无监督学习（聚类分析） | Unsupervised learning / Cluster Analysis | `KMeans` | 森林火灾数据、蛙鸣数据 |
| 有监督学习（分类） | Supervised learning / Classification | `RandomForestClassifier` | 蛙鸣数据 |

配套的两个"数据准备"技术也是本周的核心，重要性甚至高于算法本身：

- **标准化 / 缩放（Standardisation / Scaling）**：`StandardScaler`、`MinMaxScaler`、`RobustScaler`、`MaxAbsScaler`
- **降维（Dimensionality reduction）**：`PCA`（主成分分析）

以及**评估**：`accuracy_score`（准确率）与 `confusion_matrix`（混淆矩阵）。

新库是 **scikit-learn**（导入名 `sklearn`），这是 Python 里最主流的"浅层机器学习"（shallow learning）工具箱。

### 2. 它在全课中的位置（收官定位）

幻灯片给出的课程地图（course layout）：

```
Weeks 1–2   'Vanilla' Python      —— Data types / Loops / Basic operations / Conditionals
Weeks 3–5   Numpy 模块 / Conway's Game of Life / Differential Equations
Weeks 6–9   Pandas and data discovery —— Geospatial analysis / Statistical analysis / Cluster Analysis
Weeks 10–12 Creating a notebook assessment（从 Week 4–9 中任选一个主题）；Modules and Functions
```

老师在转写中的原话（Week 9 定位）：

> "Welcome to the final class before Easter. This is actually **the final lecture on our course**, but the practicals will remain, because this is where we lock in the content. So the final topic of today is probably my favorite, which is machine learning and cluster analysis. … we're at the end of the pandas and data discovery arm. And **this also has an option for the assessment as well**."

也就是说：

- 这是**最后一次讲课**（lecture），但 practical 还有——Week 10–12 的 practical 用来做**评估作业（notebook assessment）**，老师和助教在实验室里现场答疑。
- Week 9 是 "pandas and data discovery" 这条支线的终点：Week 6 pandas 基础 → Week 7 统计分析（相关系数、boxplot）→ Week 8 地理空间（GeoPandas）→ Week 9 机器学习。
- 本周的 notebook **本身也可以选作评估作业的题目**（六个选项之一，覆盖 Week 4–9）。

### 3. 与 Week 8（上周）的接续

老师明确回顾：

> "One thing we did last week was use pandas in a statistical package to look at statistical distributions in our data, potential relationships. So we looked at correlation coefficients … You might have heard the phrase **correlation doesn't infer causation** … But what we'll do today is to start looking at tools that can enable that, so to develop predictive techniques."

幻灯片 `recap`：

- Pandas 可以把信息存进 dataframe
- Pandas 能处理各种 data types
- 我们可以对**整列或子集**做统计分析
- Dataframe 有很多**内部函数**（internal functions）可以利用
- **新问题**：如果我们想把相似的观测**分组（group similar observations together）**呢？→ 开始用机器学习库

---

## 二、核心概念

### 2.1 什么是机器学习

Notebook 定义：

> Machine learning (ML) is a branch of artificial intelligence (AI) that enables computers to **learn from data and make predictions or decisions without being explicitly programmed**.

与传统编程的对比（notebook 里给出的例子非常贴合本课）：

> "The best example from this course would be referring back to using Python to **integrate differential equations**. In that notebook you **explicitly wrote down the equations** to be solved. What if we didn't know what the underlying theory was but we had data on the system we are interested in? This is one example where machine learning could be used."

**这句话是理解 ML 的钥匙**：
- Week 5 解微分方程：我们**知道物理规律**（方程），让计算机数值求解。
- Week 9 机器学习：我们**不知道规律**，但有数据，让算法从数据里"学"出模式。

老师在课上的表述：

> "I'll talk a lot about models, but what I mean really is we're going to be using **tools that someone else has written**, and we're going to **fit that to the data** that we have. … You're fitting a framework to the data you have access to and telling that framework what you want from it."

以及**本课的定位声明**（很重要，直接决定考核标准）：

> "You don't have to get your hands dirty with the algorithms. That's not what we're here to do. … it's like working in a car garage. **What tool do I need for the problem I've got?** So that's about learning the **workflow** today in the notebook."

→ 本周考的是**工作流（workflow）**，不是算法数学推导。

### 2.2 AI / ML / DL 的历史与层级

老师的时间线：

| 时期 | 事件 |
|---|---|
| ~1840s | **Ada Lovelace** —— 第一个想到"计算机能生成新东西"的人，常被称为世界上第一位程序员 |
| 1950s | **Turing** —— "机器能思考吗" |
| 1980s 起 | 人们开始玩 machine learning：用计算机学习模式并重复模式 |
| 2000 起 | **GPU（显卡）爆发**，机器学习加速 |
| 近年 | Nvidia 新一代 GPU；DeepSeek 发布证明"不需要海量显卡也能训练 AI 模型" |

**CPU vs GPU（老师现场解释，考点式的常识）**：

- CPU 是主板上的大处理器，普通电脑典型 **4–8 个 core**，每个 core 可以独立做事。
- GPU（graphics card）内部有**数千个小处理器**，"you might have 3,000 of those cores"。
- 技术不同，但结果是**可以大规模并行（do things in parallel at scale）**，而 ML 正是要从**海量数据**中学特征。

**Deep learning（深度学习）**：

> "a neural network which is replicating our thought pathways has collections of **neurons** in different stages, and a **deep** network has **multiple layers** rather than a shallow that just has one. The more neurons you have, the more things you can learn."

本课**不讲神经网络**（"we won't cover neural networks in this course"），但给了延伸资源（见第四节）。

**Shallow learning vs Deep learning**（notebook）：

- **Shallow learning**：linear regression、decision trees、support vector machines。变换相对简单，**需要人做更多 feature engineering**。
- **Deep learning**：多层神经网络，**自动学习层级化表示**，能处理图像、音频、文本等非结构化数据。
- 关键差别在于**模型深度与抽象层级**。本周用的全是 shallow models。

**Gartner Hype Cycle（炒作周期曲线）**：左下角一个想法被开发 → 到达"期望膨胀顶峰"（我们以为它能解决一切）→ 跌入"幻灭低谷" → 趋于稳定。

- **Computer vision** 已经处于**稳定期**，可以放心用于科研。地球环境科学的例子：**飓风路径追踪**（从卫星图预测飓风走向）；医学：**扫描图像中检测癌变**。
- **Generative AI** 目前正要进入"幻灭低谷"——老师说这是好事，"it means that we'll finally realize what it can and can't do"。
- 已在科研生态中使用 GenAI 的实例：环境署（Environment Agency）判定垃圾填埋场/堆肥场的风险区，原本需要**人工分拣 11,000 篇论文 → 精读 600 篇**；现在 LLM 可以自动处理**上百万篇**并抽取信息。系里正在用它做主题式文献研究（thematic research）。

### 2.3 三类机器学习（按"数据依赖"划分）

| 类型 | 英文 | 你给算法什么 | 典型任务 | 本周是否实践 |
|---|---|---|---|---|
| 无监督学习 | Unsupervised learning | 只给数据，不给答案 | Clustering（聚类）、Dimensionality reduction（降维）、Anomaly detection（异常检测）、Customer segmentation | ✅ K-means、PCA |
| 有监督学习 | Supervised learning | 数据 + 已知标签 | Classification（分类）、Regression（回归） | ✅ Random Forest |
| 强化学习 | Reinforcement learning | 一个环境 + 奖励信号 | 下棋、玩游戏、控制系统 | ❌ 只讲概念 |

**无监督学习**——老师原话：

> "unsupervised learning literally means **you're not supervising the algorithm**. You give it some data and say, **tell me the distinct groups in that data**."

地球/环境科学的应用场景（老师举例）：
- 你在实验室里测不到的东西，但想知道有哪些**不同的分组**：物种图像、森林里鸟叫的录音片段。
- **质谱仪 / 复杂显微镜**：测水或土壤，可能得到**数千个 mass spectral peaks 随时间变化**。怎么可视化变化？无监督学习可以**把它压缩下来**（降维），让你能看见数据的显著特征。
- 超市消费者行为聚类 → 优化食品配送，慈善机构据此重新分配食物。

**有监督学习**——老师原话：

> "Supervised learning is actually when we **give the algorithm a helping hand**. … Imagine I have five different bird species, and I have the sound bites matched to those labels. So we can tell the algorithm, do your cluster analysis. **However, I know these are the answers that you should be finding.**"

- **Classification（分类）**：输出是类别。交通路口摄像头识别卡车/公交——有人用监督方式训练过"卡车长什么样"。
- **Regression（回归）**：输出是连续值。老师自己的领域：给 10 年空气污染 + 气象数据，已知 6 小时后的气象，**预测 6 小时后的污染值**。

**强化学习**：

> "what a reinforcement learning algorithm does is it **learns from its environment**. It keeps going until it gets to the **optimal point**."

- 例子：Atari 游戏、下棋、AlphaGo。
- 环境科学应用：**室内空气污染**。做饭时污染会很严重，工程师做的系统会**根据实测污染值动态调整通风率**，强化学习算出最优通风条件。
- 但"much harder to code and much less stable"。

### 2.4 数据量依赖（非常重要的"反炒作"论点）

老师的核心提醒：

> "these neural networks have many, many parameters. They need **huge amounts of data** to fit those parameters. … It doesn't mean a deep neural network is the best though **if you don't have enough data**. Because often in the lab, you can't collect enough data to fit a neural network. **People jump straight into these because they sound really fancy.** … There are **older machine learning libraries which are much, much easier to understand that perform much better when you don't have much data.**"

参数量的量级对比（老师给的直觉）：
- 拟合一条直线：**3 个参数**（大致的说法）
- GPT 类模型：**几千亿（a couple of hundred billion）参数**

**碳足迹**：老师引用同事的数据——某个国家（"Ireland"，转写为 "islands"）**20% 的用电需求来自数据中心**。所以"减少 AI 碳足迹"是真实议题。

**可解释性**：本课选用的算法是"we can interpret … we can understand the decisions they've made and why"（可解释的浅层模型），这是选 K-means / Random Forest 而不是神经网络的另一个理由。

### 2.5 相似性 = 数字之间的距离

这是本周**最核心的概念**。

> "Typically, what machine learning does across the board, it defines **similarity as the distance between numbers**."

**LLM 也是这样工作的**（老师的类比，很好用）：

> "imagine I have a text … What the model first does is **convert this into a set of numbers**. It **encodes text as a string of numbers**. And that might be 1.2, 3, 5.6, whatever. And it might have 4,000 elements. When you ask it a question … it extracts from its knowledge base **what looks the same in terms of numbers**. … So that's called an **encoding model**."

**图像也是数字**：

> "an image is just basically a **matrix of numbers**. … you've got three layers. You've got a **red** layer of numbers, and each pixel represents the **intensity** of red. You've got a **blue** layer, and you've got a **green** layer. … the higher resolution the image, the more pixels you've got."

**Euclidean distance（欧氏距离）**——老师口头定义：

> "A Euclidean distance is literally the **sum of the difference between the values squared, square root**."

即对两个观测 $p, q$（各有 $n$ 个特征）：

$$ d(p,q) = \sqrt{\sum_{i=1}^{n}(p_i - q_i)^2} $$

**聚类的目标**（notebook）：

> "The goal is to **minimize the distance between points within the same cluster** while **maximizing the distance between points in different clusters**."

老师的图示解释："we want the points to be in the blue circle with small distances, but the distance between the blue and green to be large."

**坏的聚类结果**：不同类之间靠得很近，出现"这个点到底属于蓝还是黄"的**歧义（ambiguity）**。

**在 dataframe 里是什么意思**（老师现场在白板/幻灯上画的）：

```
           height  width   age
obs 1        6.4    6.5    3.2
obs 2        6.6    3.1    8
obs 3        ...
```

> "What cluster analysis is going to do is look at the **numerical distance** and actually put them into **distinct groups**. So we're doing the exact same thing as the complex algorithm does, but we're **asking the algorithm to do that for us**. We're not gonna calculate the distance."

### 2.6 K-means 是什么

- K-means 是 **13 种以上** sklearn 聚类算法中的一个（HDBSCAN 文档里提到 "The standard sklearn clustering suite has **thirteen** different clustering classes alone"）。
- 老师的评价（诚实且重要）：

> "K-means has been around for a very long time. It's **very quick**. It's very simple under the hood, but it's **quite bad**. But it's very quick, so we can run it in our environment."

**为什么"快"重要**：

> "sometimes you might have 100,000 observations, sometimes you might have a million. … K-means will still give you an answer within a matter of **seconds**. If you ran a more accurate method … that might take **days**. It could even take **weeks**, or you could **run out of memory**. Because … if you're calculating the distance between a million observations, you need more and more memory. **The more accurate the method, typically the higher the computational resource required.**"

**K-means 的关键限制**：**它不会告诉你有几个簇**，你必须自己指定 `n_clusters`。

> "the slight problem with things like k-means is it **won't tell you how many distinct groups there are** at first. … so we need to tell it how many distinct groups we want."

**"fit" 到底在做什么**（notebook 的正式解释）：

> "'Fitting' in this context means **adjusting the model parameters — specifically, the positions of the cluster centroids** — to best represent the natural groupings within the data. The algorithm **iteratively optimizes these centroids by minimizing the distance between each data point and its assigned cluster center**. The goal is … **reducing the within-cluster variance**."

**簇数的选择**（老师现场提醒）：

> "You'll realize with cluster analysis, **the more clusters you specify, you'll start to lose any difference**. So there is an **optimal number of clusters**. There are techniques to work out the optimal number of clusters. What we can do is just **eyeball it** for now. If you have a known answer, then you already know what the optimal number is."

**算法与数据的依赖性**：sklearn 文档里那张著名的对比图（每列一个聚类算法，每行一种数据分布）——

> "you can recognize from the top row, there are two distinct groups there … **Some of these algorithms can't even get this simple data set right.** … the whole point of this diagram is, **there is data and algorithm dependency**."

### 2.7 为什么必须标准化（Standardisation / Scaling）

**这是本周最容易出考点的概念。**

问题：距离计算会被**量纲/量级最大的那个特征**主导。

老师的具体数值例子：

> "imagine that you have … **feature one has a range between 10,000 and minus 30,000** … **Feature two might have values between 0.6 and 0.2**. **Feature three might have values between 50 and 90**. … Our distance is gonna be **dominated by this value because it's so large**. It's gonna **completely warp** the observations. What we want is we want to give **each feature equal weight** in the first instance."

Notebook 用森林火灾数据说得更具体：

> "variable `area` varies from less than 10 to **1000**. On the other hand, variable `temp` and `RH` vary from **5 to 30** and **20 to 100** respectively. How do we know if `area` is dominating the distance and thus clustering calculation?"

**五种常见缩放技术**（notebook 原文列表）：

| # | 方法 | 英文 | 做什么 |
|---|---|---|---|
| 1 | 最小-最大缩放 | **Min-Max Scaling** | 缩放到固定区间，通常 [0, 1] |
| 2 | 标准化 / Z 分数 | **Standardization (Z-Score Scaling)** | 使均值为 0、标准差为 1 |
| 3 | 稳健缩放 | **Robust Scaling** | 用中位数和四分位距（IQR），**对离群值不敏感** |
| 4 | 最大绝对值缩放 | **Max Abs Scaling** | 按每列最大绝对值缩放到 [-1, 1] |
| 5 | 对数缩放 | **Log Scaling** | 取对数，压缩大范围数据的偏度（skewness） |

Notebook 提醒术语互换：**scaling ≈ standardisation ≈ normalisation**，文献里混用。

**离群值（outliers）的危害**（老师）：

> "If we have an outlier that's 100,000, but it's literally **one observation**, that's gonna affect where **one [centroid]** is."

### 2.8 降维（Dimensionality Reduction）与 PCA

Notebook 定义：

> "dimensionality reduction is a process used in machine learning to **simplify high-dimensional datasets by transforming them into a lower-dimensional space while retaining as much of the original data's meaningful information as possible**. High-dimensional data can be difficult to interpret, **prone to overfitting**, and **computationally expensive**."

**为什么新特征叫 "latent"（潜在的）**：

> "The new features … are often referred to as **latent features** because they are **not directly observed** in the original dataset. Instead, they are abstract, **derived** representations … In PCA, the new features (**principal components**) are **linear combinations of the original features**. These latent features are not tied to any specific real-world measurement but are **mathematical constructs that explain the variance in the data**. This makes them valuable for uncovering hidden relationships, but it also means they may be **harder to interpret**."

老师的直觉解释：

> "Typically, what you need to do with any unsupervised learning algorithm is **give it as simple data as possible**. So you're **helping it**. Even though I said it's unsupervised, **you're manipulating the data to give it its best chance**. In the same way that we struggle with huge amounts of data … if that can be **distilled down**, we can deal with it better."

另一个动机：

> "if you've got **100,000 columns** and you've only got **50 observations**, that's also a problem."

### 2.9 有监督学习：train / validation / test

Notebook：

- **Training set（训练集）**：用来拟合模型参数，让它学到数据里的模式。
- **Validation set（验证集）**：用来调**超参数（hyperparameters）**，在开发过程中提供无偏评估，**防止过拟合（overfitting）**。
- **Test set（测试集）**：独立评估模型性能，确保它能**泛化（generalise）**到新的、没见过的数据。

**Parameters vs Hyperparameters**（务必分清）：

> - **Parameters are learned from the data.**（例如神经网络的权重）
> - **Hyperparameters are set by you before training.**（例如神经网络的层数、随机森林的树数）

老师口头版：

> "When we're training an algorithm, what we do is we give it the answer we expect, but we **also give it test data**. So we can **train it on a subset and then hold a bit of data back** to evaluate it in a robust way. 'You've not seen this data before, but can you get it right?'"

### 2.10 Random Forest（随机森林）

Notebook 解释：

> "in a **Random Forest**, the number of estimators refers to the number of **decision trees** that the algorithm builds before making predictions. It is controlled by the parameter `n_estimators` … Each tree is trained on a **random subset of the data and features**, and the final prediction is made by **aggregating the outputs of all the trees**（分类用**多数投票 majority voting**，回归用**平均 averaging**）"

**`n_estimators` 的权衡**：

- **树太多** → 计算成本和训练时间上升，但过了某个点性能几乎不再提升。
- **树太少** → 欠拟合（underfit），错过重要模式。
- **实践建议**：**100–500 棵树**对大多数问题够用。
- 训练时每棵树用不同随机子集 = **bagging**。

### 2.11 评估：Accuracy 与 Confusion Matrix

**Confusion matrix（混淆矩阵）**：

> "A confusion matrix is a table that allows us to visualize the performance of a classification algorithm. **Each row represents the instances of the actual class, while each column represents the instances of the predicted class.**"

组成部分：

- **True Positives (TP)**：正确预测为正类
- **True Negatives (TN)**：正确预测为负类
- **False Positives (FP)**：错误预测为正类（**Type I error，第一类错误**）
- **False Negatives (FN)**：错误预测为负类（**Type II error，第二类错误**）

$$ \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} $$

老师的判读口诀：

> "you want to see **dark blue along the diagonal**. Where you don't, you see a **misclassification** or a **misgrouping**. … It might be related to the data. You could have **not standardised** it. You might have **missed an outlier**. You might have **missed some features** that you haven't measured yet."

**"多高的准确率才算够"是伦理问题，不是技术问题**（老师专门强调）：

> "An appropriate level of accuracy is **completely up to the user**. So typically, if you're using something in healthcare sector … every one image missed where there's a tumor, that's bad. So how do you define an appropriate level of accuracy when you're applying machine learning? That's all about **ethical and sustainable use of AI**. … whether or not that's [more] accurate than a human doing the same thing … because we know that we change our outputs, we change our response according to the time of day, day of the week and so on."

### 2.12 完整工作流（本周要背下来的东西）

幻灯片给的两个版本：

**无监督（无已知答案）**
```
load data → clean data → standardise data → [reduce dimensions?] → fit cluster algorithm
```

**有已知答案时（可评估）**
```
load data → clean data → standardise data → [reduce dimensions?] → fit cluster algorithm → evaluate accuracy
```

**Notebook 中 §1.4/1.5 给出的六步（针对带标签数据）**：

1. Prepare the features and target variables（分离特征与目标）
2. Standardise the dataset（标准化）
3. Apply dimension reduction（降维）
4. Apply K-means clustering（聚类）
5. Map clusters to true labels（把簇 ID 映射到真实标签）
6. Evaluate accuracy（评估准确率）

**"90% 的时间在准备数据"**（幻灯片 + 老师反复强调）：

> "There is a common, often 'painful', process of data preparation before we use machine learning. **Data preparation takes up >90% of the machine learning pipeline.**"
> "the algorithm fitting, you'll see, is a couple of lines of code. But really **understanding the data that impacts your model performance is the key thing**."

以及 **garbage in, garbage out**：

> "with any machine learning application, you can have **garbage in, garbage out**. If we just throw the data from our data frame, there might be errors, there might be outliers, you can really affect the results."

### 2.13 EDA（探索性数据分析）

Notebook 术语：

> "a significant amount of time is typically spent exploring and understanding the data. This process, which we refer to as **exploratory data analysis, or EDA**, is crucial because **clustering algorithms are highly sensitive to the scale, distribution, and structure of the data**. Tasks such as handling missing values, removing outliers, normalizing features, and selecting relevant variables can greatly influence the quality of the clusters formed. … **the success of a clustering task depends less on the algorithm itself and more on how well we prepare and understand the data beforehand.**"

### 2.14 数据的科学背景

**（A）forestfires.csv —— 葡萄牙森林火灾数据**

来源：UC Irvine Machine Learning Repository，Cortez & Morais (2007), *A Data Mining Approach to Predict Forest Fires using Meteorological Data*。共 **517 行**。

列的含义（结合加拿大 FWI 火险指数系统）：

| 列名 | 含义 | 说明 |
|---|---|---|
| `X`, `Y` | 公园内的空间坐标 | Montesinho 公园网格 |
| `month` | 月份 | 字符串 `'mar'`, `'oct'` … |
| `day` | 星期 | 字符串 `'fri'`, `'tue'` … |
| `FFMC` | Fine Fuel Moisture Code | 细燃料湿度码，反映地表细小可燃物含水量（易燃程度） |
| `DMC` | Duff Moisture Code | 腐殖质层湿度码 |
| `DC` | Drought Code | 干旱码，反映深层有机质的长期干燥程度 |
| `ISI` | Initial Spread Index | 初始蔓延指数（火势扩散速率） |
| `temp` | 温度 (°C) | |
| `RH` | Relative Humidity (%) | 相对湿度 |
| `wind` | 风速 (km/h) | |
| `rain` | 降雨量 (mm/m²) | |
| `area` | 过火面积 (ha) | **大量为 0**（很多火被及时扑灭），分布极度偏斜 |

科学含义：**高温 + 低湿 + 大风 + 无雨 → 火险高、过火面积大**。本周聚类的科学问题就是：*森林火灾能不能按气象条件分成若干"类型"？*

**（B）Frogs_MFCCs.csv —— 南美无尾目（anuran）蛙鸣声学特征**

来源：Colonna, Nakamura, Cristo & Gordo (2015), *Anuran Calls (MFCCs)*, UCI ML Repository, DOI 10.24432/C5CC9H。共 **7,195 行**（68+542+2165+4420 = 7195）。

- **MFCCs_1 … MFCCs_22**：**Mel-Frequency Cepstral Coefficients（梅尔频率倒谱系数）**，22 个数值特征。这是把一段音频"音节（syllable）"压成 22 个数字的标准声学表征方法（语音识别里也用同一套）。注意 `MFCCs_ 1` 的**列名里有空格**（`'MFCCs_ 1'` 到 `'MFCCs_ 9'` 中间有空格，`'MFCCs_10'` 起没有）——这是个真实的坑。
- **`MFCCs_ 1` 全是 1.0**（从 `head()` 可见）——归一化后的常数列，对聚类没有信息量。
- **Family / Genus / Species**：三级生物分类标签（**多标签 multilabel**）。
  - **Family（科）**：更宽的类别，包含多个属。
  - **Genus（属）**：科内更具体的一组，含亲缘很近的种。
  - **Species（种）**：最具体，能相互繁殖的个体。
- **RecordID**：录音编号。

生态学背景：被动声学监测（passive acoustic monitoring）是热带雨林生物多样性调查的重要手段——布放录音机连续几个月采集，再用算法自动识别物种。老师在课上就是用"森林里的鸟叫"作类比。

**类别极度不平衡（class imbalance）**：Bufonidae 只有 68 条，Leptodactylidae 有 4420 条 —— 这直接导致后面 K-means 的 76% 准确率被"吃掉"。

---

## 三、语法速查与函数表

### 3.1 导入语句一览

```python
import pandas as pd                                   # 数据框
import numpy as np                                    # 数值数组
import matplotlib.pyplot as plt                       # 绘图
import seaborn as sns                                 # 统计绘图（热图、带 hue 的直方图、散点）
import os
from os import path

from sklearn.cluster import KMeans                    # K-means 聚类
from sklearn.preprocessing import MinMaxScaler, StandardScaler, RobustScaler, MaxAbsScaler
from sklearn.preprocessing import LabelEncoder        # 字符串标签 → 整数
from sklearn.decomposition import PCA                 # 主成分分析（降维）
from sklearn.metrics import accuracy_score, confusion_matrix
from sklearn.model_selection import train_test_split  # 训练/测试拆分
from sklearn.ensemble import RandomForestClassifier   # 随机森林分类器
from scipy.stats import mode                          # 众数（本 notebook 实际未用到，用了 np.bincount）
```

> **注意**：`sklearn` 是**安装名 scikit-learn、导入名 sklearn**——这是新手最常见的困惑之一。

### 3.2 核心函数速查表

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `pd.read_csv(path)` | 从 CSV 读入 DataFrame | `data = pd.read_csv(path+"/data/forestfires.csv")` | 可控制 delimiter、行、列名；文件需在 notebook 能访问到的目录 |
| `df.head()` | 预览前 5 行 | `data.head()` | 只是预览，不改变数据 |
| `df.columns.values` | 拿到所有列名（numpy 数组） | `data.columns.values` | 复制列名列表时最省事的办法，**避免手打错列名** |
| `df.hist(column=..., ax=...)` | 对某列画直方图，画到指定子图 | `data.hist(column='temp', ax=axs[0,0])` | `column` 必须是**精确列名（大小写敏感）**；`ax` 必须是已存在的 Axes |
| `plt.subplots(r, c, figsize=, sharey=)` | 创建 r×c 网格子图 | `fig, axs = plt.subplots(2, 3, figsize=(12,8), sharey=False)` | 返回 `(fig, axs)`；`axs` 是二维数组，用 `axs[行,列]` 索引；`sharey=False` 让每个子图独立 y 轴 |
| `df[[c1,c2]].corr()` | 计算列间相关系数矩阵 | `corr = data[['temp','RH','wind','rain','area']].corr()` | 只对**数值列**有效；默认 Pearson |
| `sns.heatmap(corr, xticklabels=, yticklabels=)` | 画热图 | `sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns)` | 加 `annot=True` 可显示数值；`fmt='d'` 表示整数格式 |
| `df.boxplot(column=[...], by=[...], ax=)` | 分组箱线图 | `data.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])` | `by` 是**分组列**，会按该列的每个唯一值画一个箱；返回 Axes，可链式 `.set_yscale('log')` |
| `df['Col'].value_counts()` | 统计某列各唯一值出现次数 | `data_frogs['Family'].value_counts()` | 返回 Series，**按频次降序**；`.size` 给唯一值个数 |
| `df[df["area"] > 0]` | 布尔索引筛选行 | `data_new = data[data["area"] > 0]` | 返回的是**切片视图**，之后赋值会触发 `SettingWithCopyWarning`（见第六节） |
| `df[[cols]].values` | DataFrame → numpy 矩阵 | `numpy_matrix = data[['temp','RH','area']].values` | sklearn 大多接受 DataFrame，但 `.values` 更明确；注意**双层方括号** |
| `KMeans(n_clusters=k, random_state=n)` | 构造 K-means 对象 | `clusterer = KMeans(n_clusters=4)` | **必须指定 `n_clusters`**；`random_state` 固定随机种子保证**可复现** |
| `.fit(X)` | 用数据拟合模型 | `clusterer.fit(numpy_matrix)` | 只训练，不返回预测 |
| `.labels_` | 拟合后每个样本的簇编号 | `labels = clusterer.labels_` | **注意末尾下划线**——sklearn 约定：**训练后才存在的属性**都以 `_` 结尾；值为 0..k-1 |
| `.fit_predict(X)` | 拟合并直接返回标签 | `clusters = kmeans.fit_predict(pca_components)` | 等价于 `.fit(X)` 后取 `.labels_`，更简洁 |
| `StandardScaler()` | Z 分数标准化器 | `scaler = StandardScaler()` | 结果：均值 0、标准差 1 |
| `.fit_transform(X)` | 学习缩放参数并变换 | `features_scaled = scaler.fit_transform(features)` | 返回 **numpy 数组**，不是 DataFrame（列名丢失！） |
| `MinMaxScaler()` | 缩放到 [0,1] | `MinMaxScaler().fit_transform(data)` | 对离群值敏感 |
| `RobustScaler()` | 用中位数/IQR 缩放 | `RobustScaler().fit_transform(data)` | **对离群值稳健** |
| `MaxAbsScaler()` | 按最大绝对值缩放到 [-1,1] | `MaxAbsScaler().fit_transform(data)` | 不改变稀疏性 |
| `PCA(n_components=2)` | 主成分分析降维 | `pca = PCA(n_components=2)` | `n_components` 是降到几维；**应先标准化再 PCA** |
| `LabelEncoder()` | 字符串标签 ↔ 整数 | `le = LabelEncoder(); y = le.fit_transform(target)` | 编号按**字母序**；`le.inverse_transform(nums)` 转回字符串 |
| `np.bincount(arr)` | 统计非负整数出现次数 | `np.bincount(true[mask]).argmax()` | 配 `.argmax()` 求**众数（最常见值）** |
| `np.zeros_like(a)` | 生成与 a 同形同 dtype 的全 0 数组 | `labels = np.zeros_like(predicted)` | 保持 dtype 很关键（整数） |
| `np.unique(a)` | 返回排序后的唯一值 | `for i in np.unique(predicted):` | 用来遍历所有簇 ID |
| `accuracy_score(y_true, y_pred)` | 计算准确率 | `accuracy_score(target, predicted_labels)` | 返回 0–1 的浮点数 |
| `confusion_matrix(y_true, y_pred)` | 生成混淆矩阵 | `confusion_matrix(target, predicted_labels)` | **行 = 真实类，列 = 预测类**；标签按**字母序/数值序**排列 |
| `train_test_split(X, y, test_size=, random_state=)` | 拆分训练/测试集 | `X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)` | 返回顺序**固定为 4 个**，别搞反；`test_size=0.2` 表示 20% 做测试 |
| `RandomForestClassifier(n_estimators=, random_state=)` | 随机森林分类器 | `rf_model = RandomForestClassifier(n_estimators=100, random_state=42)` | `n_estimators` = 树的棵数（超参数） |
| `.predict(X_test)` | 对新数据预测标签 | `predictions = rf_model.predict(X_test)` | 返回与 `X_test` 行数相同的标签数组 |
| `sns.histplot(data=, x=, hue=, kde=, element=)` | 带分组着色的直方图 | `sns.histplot(data=data_frogs, x=feature, hue='Family', kde=True, element="step")` | `hue` = 按哪列着色；`kde=True` 叠加核密度曲线；`element="step"` 阶梯样式便于重叠比较 |
| `sns.scatterplot(data=, x=, y=, hue=, palette=)` | 散点图 | `sns.scatterplot(data=pca_df, x='PC1', y='PC2', hue='Genus', palette='Set2')` | `palette='Set2'` 是配色方案 |
| `f'...{var}...'` | f-string 格式化 | `print(f'K-means Accuracy: {accuracy:.2f}')` | `:.2f` = 保留 2 位小数 |

### 3.3 本周产生的图表及判读要点

| 图 | 生成方式 | 怎么判读 |
|---|---|---|
| **气象变量直方图网格**（Exercise 1） | `plt.subplots(2,3)` + `data.hist(column=..., ax=axs[i,j])` | `temp`/`RH`/`wind` 呈可辨认的分布（近似正态或偏斜）；`rain` 和 `area` **绝大多数值挤在 0 附近**，尾巴拖得很长 → 说明这两列量级/分布与其他列差异巨大，**必须警惕它们主导距离计算** |
| **相关系数热图**（Exercise 2） | `data[[...]].corr()` + `sns.heatmap` | 颜色越亮/越暗表示相关性越强；对角线恒为 1。目的是**发现潜在关系（latent relationships）**，例如 temp 与 RH 呈负相关 |
| **按簇分组的箱线图**（K-means 之后） | `data.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])` | 若不同簇的箱体**明显错开**（中位数、四分位数不同）→ 聚类"做了点事"；若各簇箱体几乎重叠 → 聚类没抓到结构。`area` 那张加了 `.set_yscale('log')`，因为面积跨几个数量级 |
| **按 Family 着色的特征分布图**（Exercise 4b） | 循环 22 次 `sns.histplot(..., hue='Family', kde=True, element="step")` | 若某个 MFCC 特征上不同 Family 的曲线**分离得开** → 该特征对聚类有用；若完全重叠 → 该特征没有区分力 |
| **PCA 二维散点图**（PCA + Exercise 5） | `PCA(n_components=2)` → `sns.scatterplot(x='PC1', y='PC2', hue=target)` | 把 22 维压到 2 维后看不同标签是否分开。Notebook 结论："**some level of separation between different targets, but still some overlap**"（有一定分离但仍有重叠） |
| **混淆矩阵热图** | `confusion_matrix` + `sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues')` | **对角线深蓝 = 好**；非对角线的大数字 = 误分类。整列全 0 说明**该类从未被预测到** |

---

## 四、课堂补充（transcript 独有）

### 4.1 老师的现场演示与口头解释

**（1）关于"我们只是用别人写好的工具"**

老师反复回到这个主题，因为它直接对应考核期望：

> "These algorithms that are available in Python are pretty **mature**, i.e. we can **trust they do something**. It **doesn't mean it's the best algorithm for the job**. So it's like working in a car garage: **What tool do I need for the problem I've got?**"

> "We'll use functions that other people have created. **We won't generate anything ourselves**, but we'll pull it in from a function from pandas and scikit-learn."

**（2）逐行讲解 K-means 代码（老师在幻灯片上的现场解说）**

- `numpy_matrix = data[['temp','RH','area']].values`
  > "recognize that syntax here. I'm **specifying the columns in my data frame**. I'm **extracting the values into a numpy matrix**."
- `clusterer = KMeans(n_clusters=4)`
  > "I'm **preparing** the algorithm and telling it, I want you to give me four distinct clusters. **This variable name is one that I haven't defined. That's the requirement from the function.** So if you check the documentation, you'll see the entries that you can put in there. **The minimum is specifying the number of clusters.**"

  → 老师在讲**关键字参数（keyword argument）**：`n_clusters` 不是你随便起的变量名，而是函数**规定的参数名**，必须查文档。
- `clusterer.fit(numpy_matrix)`
  > "this fitting process is doing everything I just mentioned. It's **calculating the distances** between everything, and then it's **grouping similar observations** together, and it **stops when we've reached the desired number of clusters**."
- `labels = clusterer.labels_`
  > "remember a **dot operator**? You can access **functions and properties** of things. This **`labels_` (labels underscore)** is literally a number that the algorithm has given to the members of each group. … you belong to group zero, one, two, three."
- `data['K-means label'] = labels`
  > "we `data` **square brackets** 'K-means label' is literally us **adding another column into our data frame**, but now with a cluster member number."

**（3）森林火灾结果的科学判读（老师现场读图）**

> "You'll see here that clearly the **temperature** in those forest fires **vary according to the group**. So it's **done something right**. So in K-means label **1**, we see the **highest median temperature**. So there's a certain type of fire that's occurred here. The **humidity is the lowest**. So highest temperature, lowest humidity. And we might **expect the fire area to be biggest, which it is**. So it **starts to make some sense** if we try and understand the data."

→ **这是判断聚类结果是否合理的正确方法**：不是看数学指标，而是看**分出来的组在科学上讲不讲得通**。高温 + 低湿 → 大面积火灾，符合物理直觉。

> "really that's just demonstrating **how little code it takes** to get from your data you've loaded in to then determine the distinct groups in your data."

**（4）关于 18,000 行"其实很小"**

> "with the files that we've given you in the example, there aren't that many observations. **Even with 18,000 rows, that's quite a low amount when it comes to cluster analysis.**"

**（5）标准化的口头解释**

> "What standardization does or normalization is it **puts everything on a similar scale**. Typically what that means is … **the scale for each column might go from one to minus one**. So then everything has **equal weight** in the distance calculation. So it's **normalizing to itself**, i.e. what's the maximum and minimum."

**（6）转写里的技术故障与小插曲**

- 老师在讲 dataframe 时白板/翻页出了问题：*"So our data, oh God, wrecked the joint."* —— 之后手画了一个行=观测、列=height/width/age 的表。
- 幻灯片提到 min-max scaling 时老师说 "between minus one and one"（口误，min-max 标准范围是 [0,1]，[-1,1] 是 MaxAbsScaler）——**以 notebook 的书面定义为准**。
- 课末学生指出 notebook 末尾说有 resources 但往下翻是空的：老师回答 *"So what I'll do, I'll **email those around**. They're basically how to carry on the learning through **Keras, [Py]Torch**, and other things."* 另有一处 "extra 2022" 老师说 *"ignore that"*。

### 4.2 后续学习建议（老师明确推荐）

| 资源 | 说明（老师原话要点） |
|---|---|
| **Keras** | "the Python framework that I mostly use … for building these deep learning, machine learning algorithms." 可以**上传自己的图片做 object detection**；**支持视频流**——买个 webcam 就能用文档里的代码做**实时图像检测**。老师的 open day 演示：用摄像头**数房间里的人数**。**入口友好**，可视化工具好。 |
| **PyTorch** | 另一个深度学习框架，**更底层（lower level）**，但**性能更好**。可在 Colab 或 Anaconda 发行版上运行。 |
| **Nvidia Deep Learning Institute (DLI)** | **有免费自学课程**；经常有为期一天的课程（可以是 instructor-led 也可以自定进度）；**完成后可拿证书**。系里正在**与 Nvidia 建立正式合作**。老师本人上过。 |

两个框架的示例通常都可以**直接在 Google Colab 里跑**。

### 4.3 全课回顾与"这门课到底教了什么"

老师对这门课定位的总结：

> "It's all about **learning the workflow**, and this is why this course is **really applied**."

> "if you were working in a particular sector — pollution data, health data, financial data — you would learn what the **industry standard approaches** are for your problem, but **the workflow will be the same**. So it's like anyone who becomes a practitioner in a certain field: you have that grounding in their workflow like this, but then you'll learn relevant tools for your field. **And that's why this is really the groundwork** and you can go on from this."

以及为什么"数字工具"是现代科学家的必需品：

> "as a scientist, someone who works with digital tools **by default now** … when I did my degree, I spent way more time in a lab … And now you'll see there's a **balance between the two**, because technology is rapidly evolving in this space."

### 4.4 ⭐ 评估作业（Notebook Assessment）——完整说明

**这是全课最重要的实务信息，老师用了课尾一大段专门讲。**

**基本框架**

- **可以现在开始做**（"you can start working on your assessments now"）。
- **六个选项（six options）任选一个**，覆盖 **Week 4–9** 的主题（对应幻灯片 course layout 的 "select topic from weeks 4–9"）。
- **所有选项的结构完全相同**。
- 每个 notebook 里都有"a stream of activities"——从**载入数据 / 运行模型**一路做到终点。

**结构与各部分要求**

| 部分 | 要求（老师原话要点） |
|---|---|
| **Abstract（摘要）** | "a standard abstract. **Summarize the results, the area and the results** to someone to give them a **lay summary**."（写给外行看的通俗总结） |
| **Introduction（引言）** | **不是**写数据科学，而是**介绍这个科学领域为什么重要**。"So **why earthquakes**, the history of earthquakes, why they're important, **flood risks**. Depending on the notebook, **Conway's Game of Life, where that came from, what's the background**." <br>**"This is not about the data science element. It's about why the example's important."**<br>**没有字数上下限**（"There's no maximum or minimum length. Can't really do that in a notebook anyway."）。<br>参考文献数量：**"Enough to introduce the area."** 判断标准是 **"can I read it and understand why you're doing it"**。<br>⚠️ **不要照抄 notebook 里老师写的文字**——"rather than **copying the text from the notebook** that I put in there, **can you expand on that and do a little bit of reading**? Shouldn't take you long." |
| **Methodology（方法）** | **必须使用 class template（课堂模板）**——这是硬性要求。<br>这一段文字要**向读者解释 workflow**："**What Python modules are being used and in what order? How is the code being put together and why?**" "How are you solving it? How are you applying those functions?" 例如 Conway's Game of Life："**What are you implementing?**" |
| **Methodology (GenAI option)（可选）** | **可选的额外部分**。"If you want to use a **generative AI example, you can. It won't hinder you at all if you don't want to.** That's just if you want some feedback on it, but **it won't affect the results because we're not teaching you how to use generative AI**."<br>⚠️ **使用 GenAI 的注意事项**（老师专门解释）："what large language models do … is done using **probabilities** … large language models behind the scenes will write text and write code in order but **that will change if you ask it over and over again because it's done by chance**. So when you're using ChatGPT, there's a parameter called **temperature** which basically dictates its **randomness**. **The higher the temperature, the more diverse and random it is. The lower the temperature, the more consistent it is.** … So just be wary. **If you run it once, the code can vary as well.**"<br>老师建议顺序：**"Perhaps work on the class template first, get that nailed, and then if you want to look at the GenAI option."** |
| **Code（代码）** | **不必写成一个代码块**。"You don't have to use one code block. You can use multiple. It doesn't matter. … **It all boils down to personal preference.**" 有人喜欢整块跑，有人喜欢在 notebook 上下穿插。不会用就问老师（"If you're not sure how to do that, I can show you in the practical."） |
| **Results（结果）** | "just standard results. **What's happening? How have you solved the problem that's been set? What could you do better? What are the limitations? What have other people done?**"<br>"it's pretty much **the same approach you would take with a dissertation**, but you're embedding within that, **telling the user how code has been used, what modules and functions have been used, and then referring back to the output from the code**." |

**代码量与"要改多少"**

> "The **weekly examples give you a feel for the amount of code you'll need**. You'll **change some of the inputs**. You'll **change some of the settings**. You'll **create figures** and then work the text around that."

> "We can help you with the code. **You can use the code from the weekly examples. You can drop that in. Absolutely fine.** So the templates are there for you to use. **You'll have to change them though**, whether it's **numbers in the code**, whether it's **adding a bit of other code at the bottom** or **repeating it**."

**时间安排与策略建议**

- 帮助时间：**明天（Week 9 的 practical）+ 复活节后的两次 practical**。"That's the whole point of tomorrow and the two practicals after Easter. So you've got enough time to nail the code section and then start wrapping the text around it."
- **老师推荐的工作顺序**：**"work on the code a little bit first while we're helping you in the labs, and then you can wrap the text around it."**（先在有人帮的时候把代码搞定，再补文字）

**⚠️ 本周 notebook（Week 9, 机器学习/聚类）也是六个可选题目之一。**

---

## 五、Practical 要点

> Notebook 标题：**Practical 9: Pandas to Machine learning**
>
> 目标（Objectives 原文要点）：继续练习 pandas，同时开始应用常见机器学习技术。具体是用 **Cluster Analysis（无监督）**研究两个非常不同的数据集里的明显分组，并用**有监督方法根据一堆特征预测标签**。
>
> Notebook 提醒：**"you should not feel pressured to complete every exercise in class"**——课后可以继续做；**Solutions 文件夹里有全部参考答案**。

### 5.0 前置代码块：Google Colab 挂载

```python
if 'google.colab' in str(get_ipython()):          # 判断当前是否运行在 Google Colab 环境
    from google.colab import drive                # 只有 Colab 才有这个模块
    mount='/content/gdrive'                       # 挂载点路径
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)                            # 弹出授权，把 Google Drive 挂到 /content/gdrive
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    # Change to the directories to get data files
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root                               # IPython magic：切换工作目录到课程文件夹
else:
    print('Not running on CoLab')                 # 本地 Anaconda 就走这一支
```

**要点**：
- `get_ipython()` 返回当前 IPython/Jupyter 内核对象；`str(...)` 把它转成字符串再查是否含 `'google.colab'` —— 这是判断运行环境的常用技巧。
- `%cd` 前面的 `%` 表示这是 **IPython magic command**，不是 Python 语法，只能在 notebook 里用。
- **在本地跑时预期输出就是 `Not running on CoLab`**，这是正确的。

---

### 5.1 载入森林火灾数据

```python
import pandas as pd     # Im using pd here as its easier to keep writing!
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
import seaborn as sns
import os
from os import path

path = os.getcwd()       # getcwd = get current working directory，返回当前工作目录的绝对路径字符串

# 用 pandas 的 read_csv 读入 CSV
data = pd.read_csv(path + "/data/forestfires.csv")   # 字符串拼接出完整路径
data.head()

# 预览已载入数据的前 5 行
data.head()
#data.columns.values      # 取消注释可打印所有列名
```

**输出**（前 5 行）：

| | X | Y | month | day | FFMC | DMC | DC | ISI | temp | RH | wind | rain | area |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 0 | 7 | 5 | mar | fri | 86.2 | 26.2 | 94.3 | 5.1 | 8.2 | 51 | 6.7 | 0.0 | 0.0 |
| 1 | 7 | 4 | oct | tue | 90.6 | 35.4 | 669.1 | 6.7 | 18.0 | 33 | 0.9 | 0.0 | 0.0 |
| 2 | 7 | 4 | oct | sat | 90.6 | 43.7 | 686.9 | 6.7 | 14.6 | 33 | 1.3 | 0.0 | 0.0 |
| 3 | 8 | 6 | mar | fri | 91.7 | 33.3 | 77.5 | 9.0 | 8.3 | 97 | 4.0 | 0.2 | 0.0 |
| 4 | 8 | 6 | mar | sun | 89.3 | 51.3 | 102.2 | 9.6 | 11.4 | 99 | 1.8 | 0.0 | 0.0 |

**输出解读**：
- 13 列，`month`/`day` 是**字符串**（不能直接参与距离计算），其余是数值。
- 前 5 行 `area` **全是 0.0** —— 提前暗示了这一列的严重偏斜。
- 第 3 行 `RH=97`、`rain=0.2` —— 一个潮湿有雨的三月天，`area=0`，符合直觉。
- **如何判断读对了**：列数与列名符合数据说明；行数应为 517（可用 `len(data)` 或 `data.shape` 确认）。

**注意**：`path` 这个名字被用了两次——`from os import path` 导入了 `os.path` 模块，紧接着 `path = os.getcwd()` **把它覆盖成了字符串**。虽然这里能跑通（因为后面只把 `path` 当字符串用），但这是**变量名遮蔽（shadowing）**的典型坏习惯，考试/作业里应避免。

---

### 5.2 Exercise 1：绘制气象变量与火灾范围的直方图

**题目要求**：为下列变量各画一张直方图，排成一个 subplot 网格：
- `'temp'`（温度）、`'RH'`（相对湿度）、`'wind'`（风速）、`'Rain'`（降雨）
- （另外加上 `'area'`）

**给的模板**：

```python
import matplotlib.pyplot as plt
# 这条命令为整张图和分布在图上的各个坐标轴分配变量，行列数由括号里的数字决定
# figsize 指定图大小，sharey=False 表示各子图不共用 y 轴刻度
fig, axs = plt.subplots(2, 3, figsize=(12, 8), sharey=False)
# 给 'temp' 画直方图。ax=axs[0,0] 告诉 Matplotlib 用之前分配好的第 [0,0] 个坐标轴
data.hist(column='temp', ax=axs[0,0])
```

⚠️ Notebook 的黄色提示框：**"For each histogram you will need to change the values within the command `ax=axs[0,0]`, where the first value indicates the row, and the second the column value."**

**解题思路**：`axs` 是 2×3 的 Axes 数组，索引 `axs[行, 列]`，行∈{0,1}，列∈{0,1,2}。把 5 个变量依次放到 `[0,0] [0,1] [0,2] [1,0] [1,1]` 即可（第 6 格 `[1,2]` 留空）。

**完整代码**：

```python
# Make a boxplot for each column. We could group them into one figure but this is beyond the scope of this practical.
import matplotlib.pyplot as plt

fig, axs = plt.subplots(2, 3, figsize=(12, 8), sharey=False)  # 2 行 3 列共 6 个子图
# Temperature —— 放在第 0 行第 0 列
data.hist(column='temp', ax=axs[0,0])
#------'INSERT CODE HERE'------
# RH —— 相对湿度，第 0 行第 1 列
data.hist(column='RH', ax=axs[0,1])
# Wind —— 风速，第 0 行第 2 列
data.hist(column='wind', ax=axs[0,2])
# Rain —— 降雨，第 1 行第 0 列
data.hist(column='rain', ax=axs[1,0])
# Fire area —— 过火面积，第 1 行第 1 列
data.hist(column='area', ax=axs[1,1])
#------------------------------
```

**输出**：

```
array([<matplotlib.axes._subplots.AxesSubplot object at 0x1a16d80390>],
      dtype=object)
```
+ 一张 2×3 的直方图网格。

**输出解读**：
- 那行 `array([...AxesSubplot...])` 是**最后一句 `data.hist(...)` 的返回值被 Jupyter 自动打印出来了**，不是错误。想去掉可以在末尾加 `plt.show()` 或给最后一行加分号 `;`。
- ⚠️ **陷阱**：题目文字写的是 `'Rain'`（大写 R），但 dataframe 里的实际列名是 `'rain'`（小写）。**写成 `'Rain'` 会报 `KeyError`。列名大小写敏感！**

**科学与统计上的结论**（notebook 原文）：

> "For the first three variables, we can easily infer a distribution of values. For the final two variables, however, **the distribution is much harder to interpret due to a very high number of small values**. Given that we are interested in forest fires, we need to consider whether this might influence our clustering. Why is that? **If we are using the values of each variable to calculate a 'distance' between each observation, a variable that has a very large range relative to others might dominate the clustering.**"

→ 这一步不是画着玩，**它是后面"必须标准化"这个决定的证据来源**。

---

### 5.3 Exercise 2：相关系数矩阵热图

**题目要求**：画一张气象变量与火灾范围之间的相关系数热图。提示：可回顾 Practical 7 的例子。

**解题思路**：两步 —— ① `df[[列名列表]].corr()` 算相关矩阵；② `sns.heatmap()` 画出来。

**完整代码**：

```python
import seaborn as sns
# calculate the correlation matrix
#------'INSERT CODE HERE'------
corr = data[['temp','RH','wind','rain','area']].corr()
# ↑ 双层方括号：外层是"取列"操作，内层是列名的 list；.corr() 返回 5×5 的 Pearson 相关系数 DataFrame

# Now use an internal function within Seaborn called '.heatmap'
sns.heatmap(corr, xticklabels=corr.columns, yticklabels=corr.columns)
# ↑ corr 是要画的矩阵；x/yticklabels 用列名当刻度标签，否则会显示 0,1,2,3,4
#------------------------------
# And we now need to show the plot.
plt.show()   # 显式渲染图形（在脚本里必须；在 notebook 里是好习惯）
```

**输出解读**：
- 5×5 热图，**对角线恒等于 1**（自己和自己完全相关）——如果对角线不是最亮/最暗的那一档，说明代码写错了。
- 矩阵**关于对角线对称**。
- 预期的科学模式：`temp` 与 `RH` 应呈**负相关**（越热越干）；`rain` 与几乎所有变量相关性都很弱（因为大部分是 0）。
- 想看具体数值可以加 `annot=True`。

---

### 5.4 K-means 聚类分析（§1.2.1）

**四个步骤**（notebook 蓝色框原文）：

1. **Extract** our variables of interest from the dataframe into a new **Numpy matrix**
2. **Specify how many clusters** we want the Kmeans algorithm to find（有些算法能自动给，但这里必须指定）
3. **Fit** the clustering algorithm to our Numpy matrix
4. **Extract the labels** to which each row in our matrix has been assigned

**完整代码**：

```python
from sklearn.cluster import KMeans

# 1) 把感兴趣的变量从 dataframe 抽成新的 numpy 矩阵
numpy_matrix = data[['temp','RH','area']].values
# ↑ 只用 温度/相对湿度/过火面积 这三列做聚类；.values 把 DataFrame 转成 numpy 二维数组 (517, 3)

# 2) 指定我们希望 K-means 找出多少个簇
clusterer = KMeans(n_clusters=4)
# ↑ 这只是"准备"算法对象，还没有碰数据。n_clusters 是函数规定的关键字参数名

# 3) 把聚类算法拟合到我们的 numpy 矩阵上
clusterer.fit(numpy_matrix)
# ↑ 这一步内部：随机初始化 4 个质心 → 把每个点分配给最近质心 → 重算质心 → 迭代直到收敛

# 4) 取出每一行被分到的簇标签
labels = clusterer.labels_
# ↑ 末尾下划线 = sklearn 约定的"训练后属性"。返回长度 517 的整数数组，取值 0~3

# 在 dataframe 'data' 里存下 K-means 的标签：
data['K-means label'] = labels
# ↑ 给 DataFrame 新增一列。左边的列名之前不存在 → pandas 自动创建新列

# 打印这个新列
data['K-means label']
```

**输出**：

```
0      0
1      1
2      1
3      0
4      0
      ..
512    1
513    0
514    0
515    1
516    1
Name: K-means label, Length: 517, dtype: int32
```

**输出解读**：
- `Length: 517` —— 与原数据行数一致 ✅ 说明**每一行都被分配了一个簇**（K-means 不会漏掉任何点）。
- `dtype: int32` —— 标签是整数。
- 值只出现 0 和 1（在展示的这几行里）——正常，因为只截取了首尾各 5 行。
- ⚠️ **簇编号本身没有意义**：0/1/2/3 只是任意 ID，重跑一次编号可能全变（除非设 `random_state`）。**不能把"簇 1"当成固定的类别名**。

**用箱线图看各簇的性质**：

Notebook 先复习了 Practical 7 的用法：
```python
<<name of dataframe>>.boxplot(column=[<<names of columns>>])
```
然后扩展出 `by=` 参数：
```python
data.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])
```
> "we are asking Python to produce a boxplot of values in the column `temp` but **also produce a number of separate boxplots according to the number of unique values given by the column `K-means label`**."

**完整代码**：

```python
fig, ax = plt.subplots(1, 3, figsize=(10, 5))         # 1 行 3 列（注意这里 ax 是一维数组，用 ax[0]）
data.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])   # 温度按簇分组
data.boxplot(column=['RH'],   by=['K-means label'], ax=ax[1])   # 相对湿度按簇分组
data.boxplot(column=['area'], by=['K-means label'], ax=ax[2]).set_yscale('log')
# ↑ .boxplot() 返回 Axes 对象，直接链式调用 .set_yscale('log') 把 y 轴设为对数刻度
#   为什么用 log？因为 area 从 0 跨到 1000+，线性刻度下所有小值都会挤在底部看不见
```

**输出解读**（结合老师课上的讲解）：
- 判断标准：**各簇的箱体是否明显错开**。
- 老师读出的结论：某个簇具有**最高的中位温度 + 最低的湿度 + 最大的过火面积** → **物理上自洽**，说明聚类确实抓到了"某一类火灾"。
- 若各簇箱体高度重叠 → 聚类没抓到有意义的结构，需要回头改数据。

---

### 5.5 Exercise 3：只用正的过火面积重做聚类

**题目要求**：复制上面的代码，但要在**新的 dataframe**（只含 `area` 为正的行）上操作。提示给了筛选写法：

```python
new_dataframe = data[data["area"] > 10.0]
```

**为什么要这么做（科学动机）**：原数据里大量 `area == 0` 的行代表"火被立即扑灭 / 没有可测量的过火面积"。这些零值会在 `area` 这一维上形成一个巨大的尖峰，把 K-means 的质心往 0 拽。**只保留真正烧起来的火灾**，才能研究"火灾类型"的差异。

**解题思路**：把筛选条件从 `> 10.0` 改成 `> 0`，其余四步照搬。

**完整代码**：

```python
#-------'INSERT CODE HERE'-------
data_new = data[data["area"] > 0]
# ↑ 布尔索引：data["area"] > 0 生成一个 True/False 的 Series，用它去索引 data 只留 True 的行
#   结果 270 行（原 517 行中约一半 area>0）

numpy_matrix_new = data_new[['temp','RH','area']].values   # 同样抽三列成矩阵
clusterer = KMeans(n_clusters=4)                           # 重新构造一个 KMeans 对象（4 个簇）
clusterer.fit(numpy_matrix_new)                            # 拟合到新矩阵
labels = clusterer.labels_                                 # 取标签
data_new['K-means label'] = labels                         # 写回新 dataframe ← 这里会触发警告
#--------------------------------

data_new['K-means label']
#data['Operator'].value_counts().plot(kind='bar')          # 注释掉的另一种可视化写法

fig, ax = plt.subplots(1, 3, figsize=(10, 5))
data_new.boxplot(column=['temp'], by=['K-means label'], ax=ax[0])
data_new.boxplot(column=['RH'],   by=['K-means label'], ax=ax[1])
data_new.boxplot(column=['area'], by=['K-means label'], ax=ax[2]).set_yscale('log')
```

**输出（一个警告）**：

```
/Users/user/anaconda3/lib/python3.7/site-packages/ipykernel_launcher.py:6: SettingWithCopyWarning:
A value is trying to be set on a copy of a slice from a DataFrame.
Try using .loc[row_indexer,col_indexer] = value instead

See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
```

**这个警告的完整解释（本周最重要的报错知识点之一）**：

- **是什么**：`SettingWithCopyWarning`。**它是 Warning 不是 Error**——代码照常跑完，图也画出来了。
- **为什么会出现**：`data_new = data[data["area"] > 0]` 返回的可能是 `data` 的一个**视图（view）**而不是**独立副本（copy）**。pandas 无法在编译期确定到底是哪一种。当你接着写 `data_new['K-means label'] = labels` 时，pandas 不确定你是想改 `data_new` 还是想通过它改到原始 `data`，于是发出警告。
- **风险**：在某些 pandas 版本/情形下，赋值**可能悄悄不生效**，或者**意外污染原始 DataFrame**。
- **正确修法（三选一）**：

```python
# 方法 1（最推荐）：显式复制一份，斩断与原 df 的联系
data_new = data[data["area"] > 0].copy()
data_new['K-means label'] = labels          # 现在完全安全

# 方法 2：用 .loc 一步到位
data.loc[data["area"] > 0, 'K-means label'] = labels

# 方法 3：用 .assign() 返回新对象
data_new = data[data["area"] > 0].assign(**{'K-means label': labels})
```

**Notebook 的提醒**：**"Please note the ordering may be different, but this is normal."**
→ 因为 `KMeans` 没有设 `random_state`，**每次运行簇的编号顺序都可能不同**。图形的形状（哪个簇高温、哪个簇低湿）应该稳定，但**编号 0/1/2/3 与具体簇的对应关系会变**。这不是 bug。

**输出解读**：去掉 `area == 0` 之后，`area` 的箱线图不再被零值压扁，各簇之间的面积差异应该更清晰。

---

### 5.6 §1.2.2 标准化：四种 Scaler 演示

**演示代码（用一个玩具数据集说明四种缩放器的效果）**：

```python
import numpy as np
import pandas as pd
from sklearn.preprocessing import MinMaxScaler, StandardScaler, RobustScaler, MaxAbsScaler

# Sample Data —— 故意做出两个量纲完全不同的列（cm 和 kg）
data = pd.DataFrame({
    'Height (cm)': [150, 160, 170, 180, 190],
    'Weight (kg)': [50, 65, 70, 80, 90]
})

# 1. Min-Max Scaling —— 线性映射到 [0, 1]
min_max_scaler = MinMaxScaler()                          # 构造缩放器对象
data_min_max_scaled = min_max_scaler.fit_transform(data) # fit: 学每列的 min/max；transform: 应用变换
print("Min-Max Scaled Data:")
print(data_min_max_scaled)

# 2. Standardization (Z-Score Scaling) —— 变成均值 0、标准差 1
standard_scaler = StandardScaler()
data_standard_scaled = standard_scaler.fit_transform(data)
print("\nStandardized Data:")
print(data_standard_scaled)

# 3. Robust Scaling —— 用中位数和 IQR，对离群值稳健
robust_scaler = RobustScaler()
data_robust_scaled = robust_scaler.fit_transform(data)
print("\nRobust Scaled Data:")
print(data_robust_scaled)

# 4. Max Abs Scaling —— 按每列最大绝对值缩放到 [-1, 1]
max_abs_scaler = MaxAbsScaler()
data_max_abs_scaled = max_abs_scaler.fit_transform(data)
print("\nMax Abs Scaled Data:")
print(data_max_abs_scaled)
```

**要点**：
- 四个 scaler 的 API 完全一样：`Scaler()` → `.fit_transform(X)`。**这就是 sklearn 的统一接口设计**，学会一个就会全部。
- `fit_transform` 返回的是 **numpy 数组**（列名丢失）。如果需要保留列名要自己重新包成 DataFrame。
- ⚠️ **一个重要的方法论细节（notebook 未强调但要知道）**：真正做有监督学习时，`fit` 应该只在**训练集**上做，测试集用 `.transform()`（不是 `fit_transform`），否则测试集的信息会泄漏进模型（**data leakage**）。

⚠️ **注意这段代码有个副作用**：`data = pd.DataFrame({...})` **把之前的森林火灾 DataFrame `data` 覆盖掉了！** 所以下一个代码块里 `data[data["area"] > 0]` 若在同一次运行中会 `KeyError: 'area'`。实际运行时之所以能跑，是因为下面那块单元格是在**重新运行过读取 CSV 的单元格之后**执行的。这是 **Jupyter notebook 的经典陷阱：单元格执行顺序 ≠ 从上到下**（详见第六节）。

---

### 5.7 用标准化后的数据重做 K-means

```python
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

# Extract data for which we only have positive values of 'area'
data_new_scaled = data[data["area"] > 0]                       # 同样只保留正的过火面积

# Extract our variables of interest from the dataframe into a new Numpy matrix
numpy_matrix = data_new_scaled[['temp', 'RH', 'area']].values  # 三列 → numpy 矩阵

# Apply Standard Scaling to ensure all features contribute equally to the clustering
scaler = StandardScaler()                                      # Z-score 标准化器
scaled_matrix = scaler.fit_transform(numpy_matrix)             # ★ 关键新增步骤：每列变成 均值0/标准差1

# Specify how many clusters we want the KMeans algorithm to find
clusterer = KMeans(n_clusters=4)

# Fit the clustering algorithm to the scaled matrix
clusterer.fit(scaled_matrix)                                   # ★ 注意：拟合的是 scaled_matrix，不是原矩阵

# Extract the labels
labels = clusterer.labels_

# Store the KMeans labels back into the dataframe
data_new_scaled['K-means label (scaled)'] = labels             # 新列名带 (scaled) 便于与未缩放版对比

print(data_new_scaled['K-means label (scaled)'])

# Create a new plot —— 注意：箱线图画的仍然是【原始未缩放】的数值，只是分组依据换成了缩放后的簇标签
fig, ax = plt.subplots(1, 3, figsize=(10, 5))
data_new_scaled.boxplot(column=['temp'], by=['K-means label (scaled)'], ax=ax[0])
data_new_scaled.boxplot(column=['RH'],   by=['K-means label (scaled)'], ax=ax[1])
data_new_scaled.boxplot(column=['area'], by=['K-means label (scaled)'], ax=ax[2]).set_yscale('log')
```

**输出**：

```
C:\Users\mccikdt3\anaconda3\envs\DEES_programming\lib\site-packages\pandas\core\frame.py:3607: SettingWithCopyWarning:
A value is trying to be set on a copy of a slice from a DataFrame.
Try using .loc[row_indexer,col_indexer] = value instead
  self._set_item(key, value)

138    1
139    1
140    1
141    3
142    1
      ..
509    0
510    0
512    3
513    0
514    0
Name: K-means label (scaled), Length: 270, dtype: int32
```

**输出解读**（这是本周最值得细看的输出之一）：
- **`Length: 270`** —— 从 517 行筛到 270 行，说明**有 247 场火灾的 `area` 为 0**（几乎一半！）。这是对数据本身的重要认识。
- **索引从 138 开始，且中间跳号（… 510, **512**, 513 …，缺 511）** —— 这是布尔筛选的正常表现：**pandas 保留原始索引**，不会重新编号。想重编号用 `.reset_index(drop=True)`。索引跳跃**证明筛选确实生效了**。
- 又一次 `SettingWithCopyWarning`（原因同 5.5）。
- 同样是 `int32` 的 0–3。

**Notebook 的结论（诚实且重要）**：

> "Can you detect much of a difference in the outputs? **It is difficult to assign any difference in a qualitative way.**"

老师的呼应：

> "we'll look at how the cluster membership changes, and **it does change**. … **Is it more accurate? We don't know yet, because this is a data set without labels.** But nonetheless, it shows you the **sensitivity**."

→ **这是本周的一个方法论要点**：没有真实标签时，你**无法证明**标准化让结果变好，只能说结果**变了**（对数据处理敏感）。这正是下一节要转向"有标签数据"的理由。

**修订后的五步工作流**（notebook 蓝色框）：

1. Extract our variables of interest from the dataframe into a new Numpy matrix
2. **Scale the features (variables) prior to clustering** ← 新增
3. Specify how many clusters we want the Kmeans algorithm to find
4. Fit the clustering algorithm to our Numpy matrix
5. Extract the labels to which each row in our matrix has been assigned

**Notebook 留的自选练习**：*"why not try to modify the example above and use a different scaler function."*（换成 `MinMaxScaler` / `RobustScaler` 试试）

---

### 5.8 §1.3 载入带标签的蛙鸣数据

```python
# Load the Air BnB data     ← 注释是从旧 notebook 复制粘贴留下的，实际载入的是青蛙数据（无害的复制遗留）
if 'google.colab' in str(get_ipython()):
    # 在 Colab 上：直接从 GitHub raw 链接读取（不依赖本地文件）
    data_frogs = pd.read_csv('https://raw.githubusercontent.com/loftytopping/DEES_programming_course/master/data/Frogs_MFCCs.csv')
    data_frogs.head()
else:
    # 在本地：从相对路径 data/ 读取
    data_frogs = pd.read_csv("data/Frogs_MFCCs.csv")
    data_frogs.head()

# Preview the first 5 lines of the loaded data
data_frogs.head()
```

**要点**：`pd.read_csv()` **可以直接吃 URL**，不必先下载。这是很实用的技巧。

**输出**：5 行 × **26 列**。前 22 列是 `MFCCs_ 1` … `MFCCs_22`，然后是 `Family`、`Genus`、`Species`、`RecordID`。

前 5 行全是 `Leptodactylidae / Adenomera / AdenomeraAndre / RecordID=1`（同一段录音的连续音节）。

**输出解读**：
- `MFCCs_ 1` 全部等于 `1.0` → **这是一个常数列，对区分类别毫无贡献**（但后面代码仍然把它包含进特征里了）。
- 其余 MFCC 值大致在 −0.3 到 +0.4 之间 → **数据已经归一化过**，所以本例中 `StandardScaler` 的作用不如森林火灾数据那么戏剧化。
- `5 rows × 26 columns` —— 确认列数对。

**三级标签的生物学含义**（notebook 原文）：

- **Family** is a broader category that includes multiple related genera.
- **Genus** is a more specific group within a family that contains closely related species.
- **Species** is the most specific rank and refers to individual organisms that can reproduce together.

---

### 5.9 Exercise 4a：统计三个标签列的唯一值

**题目要求**：用 Practical 6 学过的 `.value_counts()` 列出 `Family`、`Genus`、`Species` 的唯一取值。

**完整代码**：

```python
#-------'INSERT CODE HERE'-------
print("\n List of unique Family entries : \n", data_frogs['Family'].value_counts())
# ↑ .value_counts() 返回一个 Series：索引=唯一值，值=出现次数，按次数降序
print("Number of of unique Family entries : \n", data_frogs['Family'].value_counts().size)
# ↑ .size 给出这个 Series 的长度，也就是【唯一值的个数】

print("\n List of unique Genus entries : \n", data_frogs['Genus'].value_counts())
print("Number of of unique Genus entries : \n", data_frogs['Genus'].value_counts().size)

print("\n List of unique Species entries : \n", data_frogs['Species'].value_counts())
print("Number of of unique Species entries : \n", data_frogs['Species'].value_counts().size)
#------------------------------
```

**输出**：

```
 List of unique Family entries :
 Leptodactylidae    4420
Hylidae            2165
Dendrobatidae       542
Bufonidae            68
Name: Family, dtype: int64
Number of of unique Family entries :
 4

 List of unique Genus entries :
 Adenomera        4150
Hypsiboas        1593
Ameerega          542
Dendropsophus     310
Leptodactylus     270
Scinax            148
Osteocephalus     114
Rhinella           68
Name: Genus, dtype: int64
Number of of unique Genus entries :
 8

 List of unique Species entries :
 AdenomeraHylaedactylus    3478
HypsiboasCordobae         1121
AdenomeraAndre             672
Ameeregatrivittata         542
HypsiboasCinerascens       472
HylaMinuta                 310
LeptodactylusFuscus        270
ScinaxRuber                148
OsteocephalusOophagus      114
Rhinellagranulosa           68
Number of of unique Species entries :
 10
```

**输出解读（极其重要，直接决定后面每一步）**：

1. **唯一值个数 = 后面 `KMeans(n_clusters=?)` 该填的数字**：Family → **4**、Genus → **8**、Species → **10**。
2. **总行数验证**：68 + 542 + 2165 + 4420 = **7195**；三个层级加起来都应等于 7195 ✅ 说明**没有缺失值**。
3. **严重的类别不平衡（class imbalance）**：
   - Leptodactylidae 4420 条 vs Bufonidae 只有 **68** 条 —— 相差 **65 倍**！
   - 这就是后面 K-means 只有 76% 准确率的**根本原因**：K-means 倾向于把簇分得大小相近，而真实类别大小相差悬殊，小类必然被大类"吞掉"。
   - Notebook 明说："**much of this dominated by the imbalanced 'Bufonidae' class**"。
4. **层级一致性**：Ameerega(542) = Ameeregatrivittata(542)、Rhinella(68) = Rhinellagranulosa(68)、Leptodactylus(270) = LeptodactylusFuscus(270) —— 这些属下只有一个种；而 Adenomera(4150) = 672 + 3478（两个种）。**这是检查数据自洽性的好方法**。

---

### 5.10 Exercise 4b：按 Family 着色看每个特征的分布

**题目要求**：补全特征名列表，用循环为每个特征画一张按 `Family` 着色的分布图。

给的单特征示例（**注意这段示例里故意/意外写错了列名**）：

```python
sns.histplot(data=data_frogs, x='MCCs_17', hue='Family', kde=True, element="step")
#                                ↑ 'MCCs_17' 少了一个 F！正确是 'MFCCs_17' → 会报 KeyError / ValueError
plt.title(f'Distribution of {feature} by Family')
plt.show()
```

**完整代码（正确版）**：

```python
#-------'INSERT CODE HERE'-------
# 建立一个包含所有特征列名的 list —— 务必和 dataframe 里的列名【逐字符一致】
column_list = ['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']
# ⚠️ 注意 'MFCCs_ 1' 到 'MFCCs_ 9' 中间【有一个空格】（为了对齐两位数），
#    'MFCCs_10' 起【没有空格】。手打极易出错 —— 用 data_frogs.columns.values 复制粘贴最稳。

for feature in column_list:                 # 遍历 22 个特征，每个画一张图
    # 画直方图，用 Family 标签控制颜色（hue）
    sns.histplot(data=data_frogs, x=feature, hue='Family', kde=True, element="step")
    # data=  传整个 DataFrame；x= 指定画哪一列；hue= 按哪列分组着色
    # kde=True 叠加核密度估计曲线（平滑的分布轮廓）
    # element="step" 用阶梯线而非实心柱，多组重叠时看得清
    plt.title(f'Distribution of {feature} by Family')   # f-string 把当前特征名插进标题
    plt.show()                              # 每轮显式显示一张图，否则 22 张会画在同一张上重叠成一团
#------------------------------
```

**输出**：22 张图（notebook 里只保留了前 2 张 `output_26_0.png`、`output_26_1.png`）。

**输出解读**：
- 每张图里有 **4 条颜色不同的分布曲线**，对应 4 个 Family。
- **判读规则**：若某特征上 4 条曲线**峰位明显错开** → 这个特征**对区分 Family 有用**；若 4 条曲线几乎重合 → 这个特征**没有区分力**。
- Notebook 的结论：**"We can see that some features are clearly different for a given family label. This means these features are going to be useful in applying cluster analysis."**
- 注意 `MFCCs_ 1` 那张图会是一条竖线（全是 1.0），直观地暴露出它是无用的常数列。
- ⚠️ `plt.show()` **必须在循环体内**。放在循环外的话，22 个直方图会全部叠在一张图上。

**为什么要看 22 张图**：这就是 **EDA（探索性数据分析）**的实践 —— 在做任何建模之前，先用眼睛把数据看一遍。

---

### 5.11 §1.4 降维：PCA

**完整代码**：

```python
# Import the relevant libraries
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

# Extract the features and target 'Family'
features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
# ↑ features 是 22 列的 DataFrame，形状 (7195, 22)
target = data_frogs['Family']
# ↑ target 是单列 Series，形状 (7195,)，内容是字符串标签

# Step 1: Standardize the features —— 让每一列均值 0、标准差 1
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)
# ↑ 返回 numpy 数组 (7195, 22)。★ PCA 之前必须标准化，否则方差大的列会主导主成分

# Step 2: Apply PCA to reduce to 2 components
pca = PCA(n_components=2)                       # 指定降到 2 维
pca_components = pca.fit_transform(features_scaled)
# ↑ 返回 (7195, 2) 的数组：每行是原来 22 维的点在新的 2 维"主成分空间"里的坐标

# Step 3: Create a new dataframe with the PCA components and target label
pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
# ↑ 把 numpy 数组重新包成 DataFrame，方便交给 seaborn
pca_df['target'] = target
# ↑ 把真实标签加回来当作着色依据

# Step 4: Plot the PCA results using Seaborn
plt.figure(figsize=(10, 6))                     # 新建一张 10×6 英寸的图
sns.scatterplot(data=pca_df, x='PC1', y='PC2', hue='target', palette='Set2')
# ↑ x/y 是两个主成分，hue='target' 按真实 Family 着色
plt.title('PCA: First Two Principal Components')
plt.show()
```

**输出解读**：
- 一张二维散点图，4 种颜色对应 4 个 Family。
- **PC1、PC2 没有物理单位**——它们是 22 个原始 MFCC 的**线性组合**，是 latent features（潜在特征）。
- Notebook 的判读：**"We can see some level of separation between different targets, but still some overlap."**（能看到一定程度的分离，但仍有重叠）
- **重叠意味着什么**：这 2 个主成分没有保留全部信息（22 → 2 必然丢信息）。重叠区域正是后面 K-means 会分错的地方。
- ⚠️ **注意 `pca_df['target'] = target` 的隐患**：`pca_components` 生成的 DataFrame 索引是 0,1,2,…；`target` 的索引来自 `data_frogs`。这里恰好一致（因为原 df 没有被筛选过），所以能对齐。但如果 features 来自筛选过的 df，**索引不匹配会导致大量 NaN**。安全写法是 `pca_df['target'] = target.values`。

---

### 5.12 Exercise 5：对 'Genus' 标签做 PCA

**题目要求**：用上面的代码，但换成 `'Genus'` 标签。

**解题思路**：**只需改两处**：`target = data_frogs['Genus']`，以及着色列名。特征、标准化、PCA 全部不变（**PCA 是无监督的，根本不看标签**——标签只用于着色）。

**完整代码**：

```python
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', ..., 'MFCCs_22']]   # 与上面完全相同（此处省略中间列名）
target = data_frogs['Genus']          # ★ 改动 1：目标标签换成 Genus（8 个属）

# Step 1: Standardize
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)

# Step 2: PCA 降到 2 维
pca = PCA(n_components=2)
pca_components = pca.fit_transform(features_scaled)

# Step 3: 新建 DataFrame
pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
pca_df['Genus'] = target              # ★ 改动 2：列名叫 'Genus'

# Step 4: 画图
plt.figure(figsize=(10, 6))
sns.scatterplot(data=pca_df, x='PC1', y='PC2', hue='Genus', palette='Set2')  # ★ 改动 3：hue='Genus'
plt.title('PCA: First Two Principal Components')
plt.show()
```

**输出解读**：
- 现在是 **8 种颜色**（8 个属）。
- **点的位置和 Exercise 5 之前那张图完全一样**——因为 PCA 不看标签，投影坐标不变，**只有着色变了**。
- 预期结果：颜色更多、重叠更严重。**类别越细，在 2 维投影里越难分开**——这也预示着 Genus（8 类）比 Family（4 类）更难聚类。

---

### 5.13 §1.5 用带标签数据评估聚类准确率（Family，4 类）

**六个步骤**（notebook 明确给出，务必背下来）：

1. Prepare the features and target variables
2. Standardise the dataset
3. Apply dimension reduction
4. Apply K-means clustering
5. **Map clusters to true labels**
6. Evaluate accuracy

**第 5 步为什么必要（关键概念）**：

> "**K-means assigns arbitrary cluster IDs**, so we map the clusters to the most common true labels using **the mode**."
> "Note that clustering labels retrieved from K-means are **arbitrary**, so mapping the predicted labels to the closest matching true labels is **necessary for accuracy measurement**."

→ K-means 输出的是 0/1/2/3，而真实标签是 'Bufonidae'/'Hylidae'/…。**这两套编号之间没有任何对应关系**。必须先建立映射：**看每个簇里"真实标签的众数是什么"，就把这个簇整体判定为那个标签**。

**完整代码**：

```python
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
from sklearn.cluster import KMeans
from scipy.stats import mode                       # 导入了但本代码块实际未使用（用了 np.bincount 代替）
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns
from sklearn.preprocessing import LabelEncoder
import numpy as np

# 1) Separate features and target
features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Family']                      # 真实标签（字符串）

# Convert string labels to numeric labels
le = LabelEncoder()                                # 标签编码器：字符串 ↔ 整数
true_labels_encoded = le.fit_transform(target)
# ↑ 'Bufonidae'→0, 'Dendrobatidae'→1, 'Hylidae'→2, 'Leptodactylidae'→3（按【字母序】编号）
#   为什么要转成整数？因为下面 np.bincount 只能吃非负整数

# Step 2: Standardize the Features
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)   # (7195, 22)，每列均值0标准差1

# Step 3: Apply dimension reduction
pca = PCA(n_components=2)
pca_components = pca.fit_transform(features_scaled)  # (7195, 2)

# Create a new dataframe with the PCA components and target label
pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
pca_df['Family'] = target                          # 这个 pca_df 后面其实没用到，只是为了留个记录

# Step 4: Apply K-means Clustering
kmeans = KMeans(n_clusters=4, random_state=42)     # ★ 4 个簇，因为我们知道 Family 有 4 个唯一值
                                                   # ★ random_state=42 固定随机种子 → 结果可复现
clusters = kmeans.fit_predict(pca_components)      # ★ 在【PCA 后的 2 维数据】上聚类；直接返回标签数组

# Step 5: Map Clusters to True Labels
def map_clusters_to_labels(predicted, true):
    """把任意的簇 ID 映射到该簇中最常见的真实标签。
       predicted: K-means 给的簇编号数组，如 [2,0,3,1,...]
       true:      LabelEncoder 编码后的真实标签数组，如 [3,3,2,0,...]
       返回:      与 predicted 等长的数组，元素已换成"该簇代表的真实标签编号"
    """
    labels = np.zeros_like(predicted)              # 建一个同形状同 dtype 的全 0 数组存结果
    for i in np.unique(predicted):                 # 遍历每一个出现过的簇 ID（0,1,2,3）
        mask = predicted == i                      # 布尔掩码：属于簇 i 的位置为 True
        labels[mask] = np.bincount(true[mask]).argmax()
        # ↑ true[mask]      取出簇 i 内所有样本的【真实标签编号】
        #   np.bincount(...) 统计 0,1,2,3 各出现几次 → 例如 array([0, 0, 1200, 3400])
        #   .argmax()        取出现次数最多的那个编号（这里是 3）→ 即【众数 mode】
        #   labels[mask] = 3 把整个簇 i 都判定为标签 3
    return labels

predicted_labels = map_clusters_to_labels(clusters, true_labels_encoded)

# Convert mapped numeric labels back to original string labels
predicted_labels = le.inverse_transform(predicted_labels)
# ↑ 3 → 'Leptodactylidae' 等，转回字符串，才能和 target（字符串）比较

# Step 6: Evaluate Accuracy
accuracy = accuracy_score(target, predicted_labels)   # 逐元素比对，算正确比例
print(f'K-means Accuracy: {accuracy:.2f}')            # :.2f = 保留两位小数

conf_matrix = confusion_matrix(target, predicted_labels)   # 行=真实类，列=预测类
print("Confusion Matrix:")
print(conf_matrix)

# Plot the confusion matrix as a heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues',
            xticklabels=set(target), yticklabels=set(target))
# annot=True 在每格显示数字；fmt='d' 用整数格式；cmap='Blues' 蓝色系配色
plt.yticks(rotation=0)          # 把 y 轴标签转成水平，方便阅读
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()
```

**输出**：

```
K-means Accuracy: 0.76
Confusion Matrix:
[[   0    0   68    0]
 [   0    0  542    0]
 [   0    0 2029  136]
 [   0    0  954 3466]]
```

**输出的完整解读（本周最值得吃透的一段）**：

标签按**字母序**排列：`[0]=Bufonidae, [1]=Dendrobatidae, [2]=Hylidae, [3]=Leptodactylidae`

| 真实 \ 预测 | Bufonidae | Dendrobatidae | Hylidae | Leptodactylidae | 行合计 |
|---|---|---|---|---|---|
| **Bufonidae** | 0 | 0 | **68** | 0 | 68 |
| **Dendrobatidae** | 0 | 0 | **542** | 0 | 542 |
| **Hylidae** | 0 | 0 | **2029 ✅** | 136 | 2165 |
| **Leptodactylidae** | 0 | 0 | 954 | **3466 ✅** | 4420 |

1. **验算准确率**：对角线正确数 = 0 + 0 + 2029 + 3466 = **5495**；总数 = 7195。
   $5495 / 7195 = 0.7637 → \mathbf{0.76}$ ✅ 与输出一致。
2. **行合计与 `value_counts()` 完全吻合**（68 / 542 / 2165 / 4420）→ 说明矩阵构造正确。
3. **⚠️ 最关键的观察：前两列全是 0！** 意思是**没有任何一个样本被预测为 Bufonidae 或 Dendrobatidae**。
   - 原因：K-means 分出了 4 个簇，但在 Step 5 映射时，**4 个簇的众数只落到了 2 个真实标签上**（Hylidae 和 Leptodactylidae）。因为这两类样本太多（2165 + 4420 = 6585，占 91.5%），任何一个簇里它们都是多数。
   - **68 个 Bufonidae 全军覆没**，542 个 Dendrobatidae 也全被判成 Hylidae。
4. **这暴露了 K-means + 众数映射方法的根本缺陷**：**类别不平衡（class imbalance）**下，小类会被完全吞掉。Notebook 原话：**"much of this dominated by the imbalanced 'Bufonidae' class"**。
5. **76% 的准确率具有欺骗性**：如果什么都不做，把所有样本都猜成 Leptodactylidae，准确率就有 4420/7195 = **61.4%**。76% 相对于这个"平凡基线（baseline）"其实只提升了 15 个百分点。**永远要和基线比。**
6. **老师的呼应**："where you don't [see dark blue on the diagonal], you see a **misclassification** … It might be related to the data. You could have **not standardised** it. You might have **missed an outlier**. You might have **missed some features**."

⚠️ **`xticklabels=set(target)` 是个真实的 bug**：`set()` 是**无序集合**，它的迭代顺序**不保证**是字母序，而 `confusion_matrix` 的行列**一定**是字母序。所以热图上的刻度标签**很可能是错位的**。正确写法：

```python
labels_sorted = sorted(target.unique())        # 或者直接用 le.classes_
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues',
            xticklabels=labels_sorted, yticklabels=labels_sorted)
```
或者更稳妥地显式指定：
```python
conf_matrix = confusion_matrix(target, predicted_labels, labels=le.classes_)
sns.heatmap(conf_matrix, ..., xticklabels=le.classes_, yticklabels=le.classes_)
```

---

### 5.14 Exercise 6：对 'Genus' 做 K-means，且不降维

**题目要求**：重复上面的工作流，做两处改动：
- 目标标签换成 `'Genus'`
- **不使用 PCA 降维**

题目问："**Do you obtain an accuracy of 80%?**"

**解题思路（正确做法）**：
1. `target = data_frogs['Genus']`
2. `n_clusters=8`（Genus 有 8 个唯一值）
3. 跳过 PCA，**直接在 `features_scaled`（22 维）上聚类**

**Notebook 给出的"解答"代码**：

```python
#-------'INSERT CODE HERE'-------
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
from sklearn.cluster import KMeans
from scipy.stats import mode
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns
from sklearn.preprocessing import LabelEncoder
import numpy as np

# 1) Separate features and target
features = data_frogs[['MFCCs_ 1', ..., 'MFCCs_22']]     # 同前
target = data_frogs['Genus']                             # ★ 改动 1：目标换成 Genus

le = LabelEncoder()
true_labels_encoded = le.fit_transform(target)           # 8 个属 → 0..7（字母序）

# Step 2: Standardize the Features
scaler = StandardScaler()
features_scaled = scaler.fit_transform(features)

# Step 3: Apply dimension reduction  ← ★ 改动 2：把 PCA 全部注释掉
# pca = PCA(n_components=2)
# pca_components = pca.fit_transform(features_scaled)
# pca_df = pd.DataFrame(data=pca_components, columns=['PC1', 'PC2'])
# pca_df['Genus'] = target

# Step 4: Apply K-means Clustering
kmeans = KMeans(n_clusters=8, random_state=42)           # ★ 改动 3：8 个簇
clusters = kmeans.fit_predict(pca_components)            # ⚠️ 这里仍然传的是 pca_components！
                                                         #    应该是 features_scaled

# Step 5: Map Clusters to True Labels（函数与前面完全相同）
def map_clusters_to_labels(predicted, true):
    labels = np.zeros_like(predicted)
    for i in np.unique(predicted):
        mask = predicted == i
        labels[mask] = np.bincount(true[mask]).argmax()
    return labels

predicted_labels = map_clusters_to_labels(clusters, true_labels_encoded)
predicted_labels = le.inverse_transform(predicted_labels)

# Step 6: Evaluate Accuracy
accuracy = accuracy_score(target, predicted_labels)
print(f'K-means Accuracy: {accuracy:.2f}')

conf_matrix = confusion_matrix(target, predicted_labels)
print("Confusion Matrix:")
print(conf_matrix)

plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues',
            xticklabels=set(target), yticklabels=set(target))
plt.yticks(rotation=0)
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()
#------------------------------
```

> ### 🚨 这份参考答案里藏着一个真正的 bug —— 务必看懂
>
> 题目要求"**不做降维**"，代码也确实把 `pca = PCA(...)` 那两行注释掉了。**但是 Step 4 依然写着 `kmeans.fit_predict(pca_components)`。**
>
> 为什么不报 `NameError`？因为 **`pca_components` 这个变量在前面的单元格里已经被创建了**（§5.13 的 Family 分析里），它**还留在 Jupyter 的内存里**。所以代码"顺利"跑完了 —— **但它实际上仍然用的是 PCA 降维后的 2 维数据，完全没有达到题目的要求**。
>
> **正确写法**：
> ```python
> clusters = kmeans.fit_predict(features_scaled)   # 用 22 维标准化后的完整特征
> ```
>
> **这是 Jupyter Notebook 最经典的陷阱**：变量在内核里持久存在，注释掉某段代码**并不会**让依赖它的变量消失。老师在整个课程里反复强调的"从上到下重新跑一遍（Restart & Run All）"就是为了防这个。
>
> **怎么发现这个 bug**：`Kernel → Restart & Run All`，如果代码依赖了被注释掉的变量，就会立刻抛出 `NameError: name 'pca_components' is not defined`。

**输出**：

```
K-means Accuracy: 0.80
Confusion Matrix:
[[3965  120    0   65    0    0    0    0]
 [ 227  260    0   55    0    0    0    0]
 [  87  122    0  101    0    0    0    0]
 [  42    3    0 1548    0    0    0    0]
 [ 176   18    0   76    0    0    0    0]
 [  69    0    0   45    0    0    0    0]
 [   9    0    0   59    0    0    0    0]
 [   8   19    0  121    0    0    0    0]]
```

**输出解读**：

标签按字母序：`[0]=Adenomera, [1]=Ameerega, [2]=Dendropsophus, [3]=Hypsiboas, [4]=Leptodactylus, [5]=Osteocephalus, [6]=Rhinella, [7]=Scinax`

| 真实 \ 预测 | Adeno | Ameer | Dendro | Hypsi | Lepto | Osteo | Rhin | Scinax | 行合计 |
|---|---|---|---|---|---|---|---|---|---|
| **Adenomera** | **3965 ✅** | 120 | 0 | 65 | 0 | 0 | 0 | 0 | 4150 |
| **Ameerega** | 227 | **260 ✅** | 0 | 55 | 0 | 0 | 0 | 0 | 542 |
| **Dendropsophus** | 87 | 122 | **0 ❌** | 101 | 0 | 0 | 0 | 0 | 310 |
| **Hypsiboas** | 42 | 3 | 0 | **1548 ✅** | 0 | 0 | 0 | 0 | 1593 |
| **Leptodactylus** | 176 | 18 | 0 | 76 | **0 ❌** | 0 | 0 | 0 | 270 |
| **Osteocephalus** | 69 | 0 | 0 | 45 | **0 ❌** | 0 | 0 | 0 | 114 |
| **Rhinella** | 9 | 0 | 0 | 59 | 0 | 0 | **0 ❌** | 0 | 68 |
| **Scinax** | 8 | 19 | 0 | 121 | 0 | 0 | 0 | **0 ❌** | 148 |

1. **验算**：对角线 = 3965 + 260 + 0 + 1548 + 0 + 0 + 0 + 0 = **5773**；5773 / 7195 = **0.8024 → 0.80** ✅ 与题目预期的 80% 一致。
2. **行合计全部与 `value_counts()` 吻合** ✅
3. **⚠️ 8 个簇，但只映射出 3 个不同的预测标签**（第 0、1、3 列有值，其余 5 列全 0）。也就是说**5 个属从未被预测到**，其中 5 个属的召回率（recall）是 **0**。
4. **为什么 8 类的准确率（80%）反而比 4 类（76%）高？** 这看起来反直觉，但原因很简单：**Genus 层级的最大类 Adenomera 占 4150/7195 = 57.7%，而算法把绝大部分样本都判给了它，正好蒙对了大量样本。** 再次说明**准确率单独看是不可靠的**，必须结合混淆矩阵。
5. **平凡基线**：全猜 Adenomera 就有 57.7%。80% 相对基线提升 22 个百分点，比 Family 那次略好，但代价是 5 个属完全丢失。

---

### 5.15 §2 有监督学习：Random Forest 预测 'Family'

**四个步骤**（notebook）：

1. Split the data into training and testing sets
2. Train a Random Forest classification model
3. Predict labels for new data points
4. Evaluate the model using accuracy and a confusion matrix

**完整代码**：

```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns

features = data_frogs[['MFCCs_ 1', 'MFCCs_ 2', 'MFCCs_ 3', 'MFCCs_ 4', 'MFCCs_ 5', 'MFCCs_ 6',
       'MFCCs_ 7', 'MFCCs_ 8', 'MFCCs_ 9', 'MFCCs_10', 'MFCCs_11', 'MFCCs_12',
       'MFCCs_13', 'MFCCs_14', 'MFCCs_15', 'MFCCs_16', 'MFCCs_17', 'MFCCs_18',
       'MFCCs_19', 'MFCCs_20', 'MFCCs_21', 'MFCCs_22']]
target = data_frogs['Family']

# 1) Split the data into training and testing sets.
X = features        # 惯例：X 表示特征矩阵（大写，因为是二维）
y = target          # 惯例：y 表示目标向量（小写，因为是一维）

# Split the data (80% train, 20% test)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
# ↑ 返回顺序固定：训练特征, 测试特征, 训练标签, 测试标签 —— 顺序写错会静默产生灾难性错误
#   test_size=0.2 → 20% 留作测试；random_state=42 → 固定拆分方式，保证可复现

print(f"Training samples: {len(X_train)}")
print(f"Testing samples: {len(X_test)}")

# Step 2: Train a Random Forest classification model.
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
# ↑ n_estimators=100 表示建 100 棵决策树（这是【超参数】，由人指定，不是学出来的）
rf_model.fit(X_train, y_train)      # ★ 只在【训练集】上训练 —— 绝不能碰测试集
print("Random Forest model trained successfully!")

# Step 3: Predict labels for new data points.
predictions = rf_model.predict(X_test)   # 对模型【没见过】的测试集做预测
# ↑ 注意这里是 .predict()（返回预测值），不是 .fit_predict()

print("Predicted labels:", predictions[:5])   # 看前 5 个预测
print("True labels:", y_test[:5])             # 看对应的前 5 个真实标签

# Step 4: 评估
accuracy = accuracy_score(y_test, predictions)   # ★ 用【测试集】的真实标签比对
print(f"Accuracy: {accuracy:.2f}")

conf_matrix = confusion_matrix(y_test, predictions)
print("Confusion Matrix:")
print(conf_matrix)

plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues',
            xticklabels=set(target), yticklabels=set(target))
plt.yticks(rotation=0)
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()
```

**输出**：

```
Training samples: 5756
Testing samples: 1439
Random Forest model trained successfully!
Predicted labels: ['Leptodactylidae' 'Hylidae' 'Hylidae' 'Leptodactylidae' 'Leptodactylidae']
True labels: 3340    Leptodactylidae
5108            Hylidae
6524            Hylidae
3649    Leptodactylidae
1617    Leptodactylidae
Name: Family, dtype: object
Accuracy: 0.99
Confusion Matrix:
[[ 12   0   3   2]
 [  0 105   1   0]
 [  0   0 413   9]
 [  0   1   5 888]]
```

**输出的逐项解读**：

1. **`Training samples: 5756` / `Testing samples: 1439`**
   - 验算：5756 + 1439 = **7195** ✅ 全部数据都被用上，没有丢失。
   - 1439 / 7195 = **0.20** ✅ 正好 20%，`test_size=0.2` 生效。
2. **前 5 个预测 vs 真实标签：5/5 全对** ✅ 这是快速的"眼球检查（sanity check）"。
   - 注意 `y_test[:5]` 打印出来带着**原始索引**（3340, 5108, 6524, 3649, 1617）——说明 `train_test_split` 是**随机打乱后拆分**的，不是按顺序切前 80%。**这很重要**：如果数据是按物种排序的（本数据确实是），顺序切分会导致训练集和测试集包含完全不同的物种，模型必然崩溃。
3. **`Accuracy: 0.99`** —— 相比 K-means 的 0.76，**提升巨大**。
4. **混淆矩阵（测试集 1439 行）**：

| 真实 \ 预测 | Bufonidae | Dendrobatidae | Hylidae | Leptodactylidae | 行合计 |
|---|---|---|---|---|---|
| **Bufonidae** | **12 ✅** | 0 | 3 | 2 | 17 |
| **Dendrobatidae** | 0 | **105 ✅** | 1 | 0 | 106 |
| **Hylidae** | 0 | 0 | **413 ✅** | 9 | 422 |
| **Leptodactylidae** | 0 | 1 | 5 | **888 ✅** | 894 |

   - 验算：对角线 = 12 + 105 + 413 + 888 = **1418**；1418 / 1439 = **0.9854 → 0.99** ✅
   - 行合计 17 + 106 + 422 + 894 = 1439 ✅
   - **对角线以外只有 21 个错误**，而且**分散在各处**，没有系统性的整类丢失。
   - **⭐ 与 K-means 的关键对比**：K-means 把 68 个 Bufonidae **全部**判错；Random Forest 在测试集的 17 个 Bufonidae 里**答对了 12 个**。**这就是"给算法答案"（有监督）的威力。**

**Notebook 对 `n_estimators` 的补充解释**（见第二节 2.10）：

- 每棵树用**数据和特征的随机子集**训练（**bagging**）。
- 预测时**每棵树投票**，票数最多的类胜出。
- **更多树** → 更稳健、更不易过拟合单个样本；**太少树** → 欠拟合；**太多树** → 计算成本上升但收益递减。
- **实践区间：100–500 棵**。

**⚠️ 一个方法论疑问（值得思考）**：这里的 Random Forest **没有做标准化**（直接用了原始 `features`），准确率却高达 99%。为什么？
→ 因为**树模型不基于距离**！决策树是按"某特征 > 某阈值"来分裂的，**对特征的单调变换（缩放）完全不敏感**。而 K-means 是距离算法，必须标准化。
**这是一个非常好的考点**：**标准化对距离类算法（K-means、KNN、SVM、PCA）是必需的，对树类算法（决策树、随机森林）是不必要的。**

---

### 5.16 Exercise 7：用随机森林预测 'Species'

**题目要求**：重复上面的有监督工作流，**只改一处**：目标标签换成 `'Species'`（10 类）。

**解题思路**：Random Forest 的 `.fit()` 会**自动**从 `y_train` 里推断出有多少个类，**不需要像 K-means 那样手动指定数量**。所以真的只改一行。

**完整代码**：

```python
#-------'INSERT CODE HERE'-------
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix
import seaborn as sns

features = data_frogs[['MFCCs_ 1', ..., 'MFCCs_22']]     # 特征完全不变
target = data_frogs['Species']                           # ★ 唯一的改动：Species（10 个种）

X = features
y = target
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

print(f"Training samples: {len(X_train)}")
print(f"Testing samples: {len(X_test)}")

rf_model = RandomForestClassifier(n_estimators=100, random_state=42)   # 超参数不变
rf_model.fit(X_train, y_train)                                        # 自动识别有 10 个类
print("Random Forest model trained successfully!")

predictions = rf_model.predict(X_test)
print("Predicted labels:", predictions[:5])
print("True labels:", y_test[:5])

accuracy = accuracy_score(y_test, predictions)
print(f"Accuracy: {accuracy:.2f}")

conf_matrix = confusion_matrix(y_test, predictions)
print("Confusion Matrix:")
print(conf_matrix)

plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues',
            xticklabels=set(target), yticklabels=set(target))
plt.yticks(rotation=0)
plt.title('Confusion Matrix')
plt.xlabel('Predicted Label')
plt.ylabel('True Label')
plt.show()
#------------------------------
```

**输出**：

```
Training samples: 5756
Testing samples: 1439
Random Forest model trained successfully!
Predicted labels: ['AdenomeraHylaedactylus' 'HypsiboasCinerascens' 'HypsiboasCordobae'
 'AdenomeraHylaedactylus' 'AdenomeraHylaedactylus']
True labels: 3340    AdenomeraHylaedactylus
5108      HypsiboasCinerascens
6524         HypsiboasCordobae
3649    AdenomeraHylaedactylus
1617    AdenomeraHylaedactylus
Name: Species, dtype: object
Accuracy: 0.98
Confusion Matrix:
[[143   0   1   1   1   0   0   0   0   0]
 [  0 693   0   0   0   1   0   0   0   0]
 [  0   0 105   0   0   1   0   0   0   0]
 [  1   4   0  51   0   0   0   0   0   1]
 [  1   0   0   0  89   0   0   0   0   0]
 [  0   0   0   0   0 229   2   0   0   0]
 [  1   0   0   0   0   0  53   0   0   0]
 [  0   0   0   0   3   2   1  14   0   0]
 [  0   0   0   0   0   0   2   0  15   0]
 [  0   0   0   0   0   0   0   0   0  24]]
```

**输出解读**：

1. **训练/测试样本数与上一题完全相同（5756 / 1439）** —— 因为 `random_state=42` 且拆分只依赖 `X` 的行数，**测试集的行完全一样**。这让两次实验可以直接对比 ✅
2. **前 5 个预测全对**，而且注意到：索引 3340 在 Family 那次是 'Leptodactylidae'，这次是 'AdenomeraHylaedactylus' —— **完全一致的层级关系**（Adenomera 属于 Leptodactylidae 科）✅
3. **`Accuracy: 0.98`** —— 从 4 类升到 **10 类**，准确率只掉了 1 个百分点。**这非常令人印象深刻**：说明 MFCC 特征对物种的区分力极强。
4. **验算对角线**：143 + 693 + 105 + 51 + 89 + 229 + 53 + 14 + 15 + 24 = **1416**；1416 / 1439 = **0.984 → 0.98** ✅
5. **10×10 矩阵，非对角线只有 23 个错误**，全部是**个位数**，没有整行归零。
6. **最难的类**：第 8 行（`OsteocephalusOophagus`，测试集 20 个）只对了 14 个，错的 3 个跑到 `HypsiboasCinerascens`、2 个到 `HypsiboasCordobae`、1 个到 `LeptodactylusFuscus`。第 9 行（`Rhinellagranulosa`，17 个）对了 15 个，2 个错判。**这些都是训练样本最少的类**（Osteocephalus 全库仅 114 条，Rhinella 仅 68 条）→ **再次印证：小类难学。**
7. **与 K-means 的终极对比**：

| 方法 | 类型 | 目标 | 准确率 | 小类表现 |
|---|---|---|---|---|
| K-means (PCA 2D) | 无监督 | Family (4类) | 0.76 | Bufonidae **全错**，2 个类从未被预测 |
| K-means (8簇) | 无监督 | Genus (8类) | 0.80 | **5 个属从未被预测** |
| Random Forest | 有监督 | Family (4类) | **0.99** | Bufonidae 12/17 正确 |
| Random Forest | 有监督 | Species (10类) | **0.98** | 全部 10 个种都有正确预测 |

→ **结论：当你有标签时，用有监督方法。无监督聚类的价值在于"你根本没有标签"的场景。**

---

### 5.17 Notebook 结尾：What We Did（总结框）

> 🟦 **In this practical, we:**
> - Introduced the core idea of **machine learning** as a way for computers to learn patterns from data
> - Distinguished between: **Features** (inputs) / **Targets / labels** (outputs we want to predict)
> - Used a real dataset to explore how machine learning models are trained
> - Split data into **training** and **testing** sets
> - Introduced **supervised learning**, where the correct answers are known
> - Trained a simple machine learning model using **scikit-learn**
> - Used the trained model to make **predictions** on unseen data
> - Compared predictions to true values to assess performance
>
> 🧠 *The focus was on understanding the machine learning workflow:* **data → model → training → prediction → evaluation**

⚠️ **注意**：notebook 最末尾还有一段"📝 Exercises 1–5"的复述框（讲"探索数据集 / 拆分训练测试集 / 训练模型 / 做预测 / 评估性能"），**这段与上文实际的 Exercise 1–7 编号对不上**——它是一个自动生成的通用总结，**不是真正的题目清单**。复习时以上文 Exercise 1–7 为准。

**Notebook 提到但未展示的额外资源**：*"A number of resources are provided at the bottom of this notebook … This includes learning how to work with images, detect objects, work with large language models (LLMs) and so on."* —— 课上学生指出这一节实际是空的，**老师承诺会邮件发送**（Keras / PyTorch 等）。

---

## 六、易错点 / 重点难点

### 6.1 报错与警告全清单

| 报错/警告 | 触发场景 | 原因 | 修法 |
|---|---|---|---|
| **`SettingWithCopyWarning`** | `data_new = data[data["area"] > 0]` 后接 `data_new['新列'] = labels` | 布尔筛选返回的可能是**视图（view）**而非独立副本，pandas 不确定你想改哪个 | `data_new = data[...].copy()`；或 `data.loc[mask, 'col'] = val` |
| **`KeyError: 'Rain'`** | Exercise 1 按题目文字写 `column='Rain'` | **列名大小写敏感**，真实列名是 `'rain'` | 用 `data.columns.values` 查看真实列名并复制 |
| **`KeyError: 'MCCs_17'`** | Exercise 4b 的示例代码里 `x='MCCs_17'` | **少打一个 F**，正确是 `'MFCCs_17'` | 从 `data_frogs.columns.values` 复制列名 |
| **`KeyError: 'MFCCs_1'`** | 手打特征列表时漏掉空格 | 真实列名是 `'MFCCs_ 1'`（下划线后**有空格**），1–9 有空格、10–22 没有 | 永远用 `df.columns.values` 复制粘贴，不要手打 |
| **`NameError: name 'pca_components' is not defined`** | Exercise 6 注释掉 PCA 后 **Restart & Run All** | 变量来自上一个单元格的残留内存 | 改成 `kmeans.fit_predict(features_scaled)` |
| **`KeyError: 'area'`**（潜在） | §1.2.2 演示 scaler 时 `data = pd.DataFrame({'Height...'})` 把森林火灾的 `data` 覆盖了 | **变量名被覆盖（overwriting）** | 给玩具数据换个名字，如 `demo_data` |
| **`ModuleNotFoundError: No module named 'sklearn'`** | 环境里没装 scikit-learn | 安装名与导入名不同 | `pip install scikit-learn` / `conda install scikit-learn`，但 `import sklearn` |
| **`ValueError: could not convert string to float`**（潜在） | 把 `month`/`day` 这样的字符串列丢进 `KMeans` 或 `StandardScaler` | 距离算法只能吃数值 | 只选数值列；或用 `LabelEncoder` / `pd.get_dummies()` 编码 |
| **`AttributeError: 'KMeans' object has no attribute 'labels_'`**（潜在） | 在 `.fit()` 之前访问 `.labels_` | sklearn 里带下划线后缀的属性**只有训练后才存在** | 先 `.fit(X)` 再取 `.labels_` |
| **`ValueError: Found input variables with inconsistent numbers of samples`**（潜在） | `accuracy_score(y_true, y_pred)` 两者长度不一致 | 常见于把 `target`（全量）和 `predictions`（测试集）比对 | 用 `accuracy_score(y_test, predictions)` |
| **`IndexError: too many indices`**（潜在） | `plt.subplots(1, 3)` 后写 `ax[0,0]` | 只有 1 行时 `ax` 是**一维**数组 | 1 行用 `ax[0]`；多行用 `axs[i,j]` |

### 6.2 概念性陷阱

**（1）簇标签是任意的（arbitrary cluster IDs）**

- K-means 输出的 0/1/2/3 **没有内在含义**，重跑一次可能全部换位。
- Notebook 提醒：*"Please note the ordering may be different, but this is normal."*
- **想让结果可复现就必须设 `random_state=42`**（或任何固定整数）。前几个例子没设，后面评估准确率的例子都设了 —— **这不是巧合，是必要**。
- 要和真实标签比准确率，**必须先做映射（Step 5）**。

**（2）"准确率高"不等于"模型好"**

- Family 的 76% 里，**两个类完全没被预测到**。
- Genus 的 80% 里，**五个属完全没被预测到**。
- 永远要**同时看混淆矩阵**，并且**和平凡基线比**（把所有样本猜成最大类的准确率）。
- 类别不平衡（class imbalance）是本周数据的核心问题。

**（3）标准化 —— 什么时候需要，什么时候不需要**

| 算法 | 是否需要标准化 | 原因 |
|---|---|---|
| K-means、KNN、SVM、PCA | ✅ **必须** | 基于**距离/方差** |
| 决策树、随机森林、梯度提升树 | ❌ 不需要 | 基于**阈值分裂**，对单调变换不敏感 |
| 线性回归（无正则化） | 一般不需要 | 系数会自动吸收尺度 |
| 岭回归 / Lasso | ✅ 需要 | 正则化项对尺度敏感 |

这正好解释了 notebook 里的现象：K-means 前做了 `StandardScaler`，而 Random Forest 直接用原始特征照样 99%。

**（4）PCA 之前必须先标准化**

PCA 找的是**方差最大的方向**。如果一列量级是 10000、另一列是 0.1，第一主成分几乎必然沿着大尺度那一列。所以顺序永远是：**Scale → PCA → Cluster**。

**（5）`.fit()` vs `.fit_transform()` vs `.fit_predict()` vs `.predict()`**

| 方法 | 用于 | 返回 |
|---|---|---|
| `.fit(X)` | 所有 estimator | `self`（训练好的对象本身） |
| `.fit_transform(X)` | **transformer**（Scaler, PCA） | 变换后的数据 |
| `.transform(X)` | transformer | 用**已学好的**参数变换新数据 |
| `.fit_predict(X)` | **clusterer**（KMeans） | 簇标签 |
| `.predict(X)` | **predictor**（RandomForest） | 预测标签 |

⚠️ **对测试集要用 `.transform()` 而不是 `.fit_transform()`**，否则会造成 **data leakage（数据泄漏）**。

**（6）`train_test_split` 的返回顺序**

```python
X_train, X_test, y_train, y_test = train_test_split(X, y, ...)
#   ①       ②       ③        ④
```
顺序是 **X_train, X_test, y_train, y_test**，**不是** X_train, y_train, X_test, y_test。写反了不会报错，但训练出的模型完全是垃圾——**这是最阴险的 bug 之一**。

**（7）Jupyter 单元格执行顺序陷阱**

- 变量在**内核内存**里持久存在，注释掉代码**不会**清除它（见 Exercise 6 的 bug）。
- 变量可以被后面的单元格**覆盖**（见 §1.2.2 的 `data`）。
- **强制诊断手段**：`Kernel → Restart & Run All`。交作业前**必须做一次**。

**（8）`set(target)` 用作坐标轴标签是错的**

`set` 是无序的，`confusion_matrix` 是按字母序排的。用 `sorted(target.unique())` 或 `le.classes_`。

**（9）布尔筛选后索引不连续**

`data_new_scaled` 打印出的索引 `138, 139, 140, 141, 142, ..., 509, 510, 512, 513, 514` 中间跳过了 511 —— **这是正常的**，pandas 保留原始索引。需要连续索引时用 `.reset_index(drop=True)`。**跨 DataFrame 赋值列时索引不对齐会产生 NaN**，这是相关的坑。

**（10）`plt.show()` 的位置**

在循环里画多张图时，`plt.show()` **必须在循环体内**，否则所有图会叠在一起。

**（11）常数列 `MFCCs_ 1` 全是 1.0**

- 对聚类**毫无贡献**，`StandardScaler` 处理它时标准差为 0（sklearn 会把这列全设为 0，不会报错但也没意义）。
- 严谨的做法应该先做特征筛选，剔除零方差列（`VarianceThreshold`）。notebook 没做，这是可以在评估作业里"讨论 limitations"的好素材。

**（12）K-means 必须自己指定簇数**

- **它不会告诉你有几个簇**。
- 有标签时：簇数 = `value_counts().size`。
- 无标签时：只能"eyeball it"，或用 elbow method / silhouette score（老师提到"there are techniques"但本课不展开）。
- 老师提醒：**簇数越多，组间差异越消失**。

### 6.3 复习自检清单

- [ ] 能说出 supervised / unsupervised / reinforcement 三者的区别与各自的典型任务
- [ ] 能解释"相似 = 数字之间的距离"，并写出 Euclidean distance 的定义
- [ ] 能默写完整的聚类工作流六步
- [ ] 能解释为什么必须标准化，以及哪些算法不需要
- [ ] 能说出四种 scaler 的区别（MinMax / Standard / Robust / MaxAbs）
- [ ] 能解释 PCA 的作用，以及为什么新特征叫 "latent"
- [ ] 能读懂混淆矩阵：行是什么、列是什么、对角线代表什么、整列为 0 意味着什么
- [ ] 能从混淆矩阵手算 accuracy
- [ ] 能区分 parameter 和 hyperparameter，并举例
- [ ] 能解释 train / validation / test 各自的用途
- [ ] 能解释 `n_estimators` 是什么、太大太小分别有什么问题
- [ ] 能解释为什么 K-means 只有 76%/80% 而 Random Forest 有 99%/98%
- [ ] 能说出 `SettingWithCopyWarning` 的成因和三种修法
- [ ] 知道 `train_test_split` 的返回顺序
- [ ] 记得评估作业的五个部分和"必须用 class template"这条硬性要求

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Machine Learning (ML) | 机器学习 | 让计算机从数据中学习模式、做出预测，而不需要人显式编写规则 |
| Artificial Intelligence (AI) | 人工智能 | 更大的领域，机器学习是它的一个子集 |
| Deep Learning (DL) | 深度学习 | 使用多层神经网络自动学习层级化数据表示的机器学习分支 |
| Shallow learning | 浅层学习 | 结构相对简单的模型（线性回归、决策树、SVM），需要人做更多特征工程 |
| Neural network | 神经网络 | 模拟人脑思维通路的计算模型，由分层的"神经元"组成 |
| Foundational model | 基础模型 | 在海量数据上训练、可微调用于多种下游任务的大型通用模型（如 GPT） |
| Large Language Model (LLM) | 大语言模型 | 处理与生成自然语言的基础模型，ChatGPT 是典型代表 |
| Encoding model | 编码模型 | 把文本/图像转换成数字向量，从而能用"数字距离"衡量相似性的模型 |
| Temperature | 温度（采样参数） | LLM 的随机性调节参数：越高输出越多样随机，越低越一致 |
| Supervised learning | 有监督学习 | 用**带标签**的数据训练，学习输入到输出的映射 |
| Unsupervised learning | 无监督学习 | 只给数据不给标签，让算法自己找出隐藏结构 |
| Reinforcement learning | 强化学习 | 智能体与环境交互、不断试错直到达到最优目标 |
| Cluster analysis / Clustering | 聚类分析 | 无监督地把相似的观测分到同一组 |
| K-means | K 均值 | 最简单的聚类算法：迭代优化 k 个质心位置，最小化簇内方差 |
| Centroid | 质心 | 一个簇的中心点，K-means 迭代优化的对象 |
| Within-cluster variance | 簇内方差 | 簇内各点到质心距离的总和，K-means 要最小化的量 |
| Euclidean distance | 欧氏距离 | √(各维差值平方和)，最常用的相似性度量 |
| Feature | 特征 | 模型的输入变量（数据框中的一列） |
| Target / Label | 目标 / 标签 | 想要预测的输出（如 Family、Genus、Species） |
| Labelled data | 带标签数据 | 每条观测都有已知正确答案的数据 |
| Feature engineering | 特征工程 | 人工构造、选择、变换特征以提升模型表现 |
| Scaling | 缩放 | 把不同量纲的特征变换到可比范围的统称 |
| Standardisation | 标准化 | 使特征均值为 0、标准差为 1（Z-score） |
| Normalisation | 归一化 | 把数据缩放到固定区间（本课与 standardisation 常互换使用） |
| Min-Max Scaling | 最小-最大缩放 | 线性映射到 [0, 1] |
| Z-Score Scaling | Z 分数缩放 | 减均值除标准差，即 StandardScaler |
| Robust Scaling | 稳健缩放 | 用中位数与四分位距，对离群值不敏感 |
| Max Abs Scaling | 最大绝对值缩放 | 按每列最大绝对值缩放到 [-1, 1] |
| Log Scaling | 对数缩放 | 取对数以压缩大范围数据的偏度 |
| Outlier | 离群值 | 远离主体分布的极端观测，会严重扭曲距离计算与质心位置 |
| Dimensionality reduction | 降维 | 把高维数据变换到低维空间，同时尽量保留有意义的信息 |
| Principal Component Analysis (PCA) | 主成分分析 | 用原始特征的线性组合构造出解释方差最多的新坐标轴 |
| Principal Component (PC) | 主成分 | PCA 产生的新特征轴（PC1 解释最多方差，PC2 次之） |
| Latent feature | 潜在特征 | 非直接观测、由算法导出的抽象特征（如主成分） |
| Exploratory Data Analysis (EDA) | 探索性数据分析 | 建模前用统计与可视化手段理解数据的过程 |
| Data preparation | 数据准备 | 清洗、标准化、降维等前处理，占机器学习流程 90% 以上的时间 |
| Garbage in, garbage out | 垃圾进，垃圾出 | 输入数据质量差，输出结果必然差 |
| Random Forest | 随机森林 | 用许多棵随机决策树投票/平均得到最终预测的集成算法 |
| Decision tree | 决策树 | 按特征阈值层层分裂来做决策的模型 |
| Estimator (`n_estimators`) | 估计器数量 | 随机森林中决策树的棵数（一个超参数） |
| Bagging | 袋装法 | 每棵树在数据的随机子集上训练，以降低方差 |
| Classification | 分类 | 输出是类别的有监督任务 |
| Regression | 回归 | 输出是连续值的有监督任务 |
| Training set | 训练集 | 用来拟合模型参数的数据 |
| Validation set | 验证集 | 用来调超参数、在开发中无偏评估的数据 |
| Test set | 测试集 | 完全不参与训练、用于最终独立评估的数据 |
| Parameter | 参数 | 模型**从数据中学到**的量（如神经网络权重、质心坐标） |
| Hyperparameter | 超参数 | **训练前由人设定**的配置（如 `n_clusters`、`n_estimators`） |
| Overfitting | 过拟合 | 模型把训练数据的噪声也记住了，在新数据上表现变差 |
| Underfitting | 欠拟合 | 模型太简单，连训练数据的模式都没抓住 |
| Generalise | 泛化 | 模型在没见过的新数据上仍表现良好 |
| Accuracy | 准确率 | 预测正确的样本占全部样本的比例 |
| Confusion matrix | 混淆矩阵 | 行=真实类、列=预测类的计数表，用来诊断分类错误的模式 |
| True Positive (TP) | 真阳性 | 正类被正确预测为正类 |
| True Negative (TN) | 真阴性 | 负类被正确预测为负类 |
| False Positive (FP) | 假阳性 | 负类被错判为正类（第一类错误 Type I error） |
| False Negative (FN) | 假阴性 | 正类被错判为负类（第二类错误 Type II error） |
| Class imbalance | 类别不平衡 | 各类样本数量相差悬殊，导致小类被大类淹没 |
| Misclassification | 误分类 | 样本被判到了错误的类别 |
| Data leakage | 数据泄漏 | 测试集信息不当地渗入训练过程，导致评估结果虚高 |
| scikit-learn / sklearn | —— | Python 主流机器学习库（安装名 scikit-learn，导入名 sklearn） |
| Keras | —— | 高层深度学习框架，入门友好、可视化工具好、支持视频流 |
| PyTorch | —— | 另一个深度学习框架，更底层但性能更好 |
| GPU (Graphics Processing Unit) | 图形处理器 | 含数千个小核心，可大规模并行计算，是深度学习爆发的硬件基础 |
| CPU (Central Processing Unit) | 中央处理器 | 主板上的主处理器，普通电脑约 4–8 核 |
| Gartner Hype Cycle | 高德纳炒作周期 | 描述新技术从期望顶峰到幻灭低谷再到稳定期的曲线 |
| Computer vision | 计算机视觉 | 让机器"看懂"图像的领域，目前处于技术稳定期 |
| Object detection | 目标检测 | 在图像/视频中定位并标注特定物体 |
| MFCC (Mel-Frequency Cepstral Coefficients) | 梅尔频率倒谱系数 | 把一段音频压成一组数值的标准声学特征表征方法 |
| Anuran | 无尾目（蛙类） | 青蛙和蟾蜍所属的两栖动物目 |
| Family / Genus / Species | 科 / 属 / 种 | 生物分类学从宽到窄的三个层级 |
| FFMC / DMC / DC / ISI | 细燃料湿度码 / 腐殖质湿度码 / 干旱码 / 初始蔓延指数 | 加拿大森林火险天气指数（FWI）系统的四个组成指标 |
| Relative Humidity (RH) | 相对湿度 | 空气中水汽含量占饱和值的百分比 |
| `SettingWithCopyWarning` | —— | pandas 警告：正在对切片副本赋值，可能不生效或污染原数据 |
| View vs Copy | 视图 vs 副本 | 视图共享原数据内存，副本是独立数据 |
| `random_state` | 随机种子 | 固定随机过程，使结果可复现 |
| Reproducibility | 可复现性 | 同样的代码在同样的数据上应给出同样的结果 |
| Notebook assessment | Notebook 评估作业 | 本课的考核形式：从 Week 4–9 六个选项中选一个，写成含代码与文字的 notebook |

---

## 📌 本周一页速记

```
主题：机器学习入门（全课最后一次 Lecture）

三类 ML：unsupervised（聚类）/ supervised（分类·回归）/ reinforcement
核心思想：相似 = 数字之间的距离（Euclidean distance）
90% 的时间花在数据准备，不是算法

无监督工作流：
  load → clean → standardise → [reduce dimensions] → fit cluster → [evaluate]

  KMeans(n_clusters=k, random_state=42).fit_predict(X)   → .labels_
  StandardScaler().fit_transform(X)                      → 均值0标准差1
  PCA(n_components=2).fit_transform(X_scaled)            → 降维（先标准化！）
  LabelEncoder().fit_transform(y) / .inverse_transform() → 字符串↔整数
  众数映射（np.bincount().argmax()）把任意簇 ID 对到真实标签

有监督工作流：
  train_test_split(X, y, test_size=0.2, random_state=42)
  RandomForestClassifier(n_estimators=100, random_state=42).fit(X_train, y_train)
  .predict(X_test) → accuracy_score / confusion_matrix

结果对比（青蛙 MFCC 数据 7195 行）：
  K-means + PCA, Family(4类)  → 0.76   ← 两个小类完全没被预测到
  K-means,       Genus(8类)   → 0.80   ← 五个属完全没被预测到
  RandomForest,  Family(4类)  → 0.99
  RandomForest,  Species(10类)→ 0.98

三大坑：
  ① SettingWithCopyWarning     → 用 .copy()
  ② Jupyter 变量残留           → Restart & Run All
  ③ 列名大小写/空格            → 用 df.columns.values 复制

评估作业：六选一（Week 4–9），结构 = Abstract + Intro + Methodology(必须用模板)
         + [GenAI methodology 可选] + Code + Results
         先搞定代码（实验室里有人帮），再补文字
```
