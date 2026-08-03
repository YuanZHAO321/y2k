# Week 1 — 科学方法、实验设计与两组均值的比较（Monte Carlo、t 检验、Wilcoxon 检验）

> 材料来源：Lecture「Asynchronous Lecture 1 Part 1 / Part 2」(Tucker Gilman) + 现场课堂转写 (08-Nov) + Practical 2 及答案 + 手册 *Basic Statistical Approaches for the Natural Sciences* V2.2, Chapter 1 & Chapter 2。

---

## 一、本周主题

本周是 Statistics for Natural Scientists（EART11200 Toolkit 的统计部分，共 6 周）的**第 1 周**，做两件事：

1. **打地基**：什么是科学 (Science)？什么是频率学派假设检验 (frequentist hypothesis testing)？什么是 p 值 (p-value)？实验设计中的对照 (control)、随机化 (randomness)、混杂因素 (confounding factors)、统计功效 (power)、可重复性 (repeatability)、取样单元 (sampling unit)；数据类型 (types of data) 与取样方法 (sampling methods)。
2. **上手第一类检验**：**预测变量 = 二分类（两组），响应变量 = 数值** 时如何比较两组的均值——三条路线：**Monte Carlo 置换法**、**t 检验 (t-test)**、**Wilcoxon 检验 (Wilcoxon test)**；以及如何用 R 实现、如何读输出、如何规范地用文字与图报告结果。

**在全课 6 周中的位置**（老师在课堂上明确列出的路线图）：

| 周次 | 预测变量 | 响应变量 | 方法 |
|---|---|---|---|
| **Week 1（本周）** | 分类（2 组） | 数值 | **t 检验 / Wilcoxon / Monte Carlo** |
| Week 2 | 分类（>2 组） | 数值 | ANOVA + Tukey post hoc |
| Week 3 | 数值 | 数值 | 线性回归 (linear regression) |
| Week 4 | 分类 | 分类 | 卡方检验 (chi-squared) |
| Week 5 | 数值（+分类） | 分类（二分） | 逻辑回归 (logistic regression) |
| Week 6 | 任意（数据不独立） | 任意 | 混合效应模型 (mixed effects models) |

老师原话（转写）：**"If you understand this [频率学派的核心问题]，everything else we'll do for the next six weeks is just details. It'll just be different ways of answering this question for different kinds of data."**

---

## 二、核心概念

### 2.1 什么是科学 (What is Science?)

- 科学不是"整理关于世界的信息"——哲学和宗教也做这件事，但它们不是科学。
- **科学的分界点：把我们的信念 (beliefs / ideas) 与经验证据 (empirical evidence) 相比较。**
- 因此科学是**做 (do)** 出来的，不是读出来的。但不必非要亲自下田或进实验室——用别人收集的证据（书里、论文里）来检验自己的想法，同样是科学。
- 关键是：**证据与想法不符时，修改想法。** 仅因为信任来源就相信一句话，那是"信仰 (faith)"——在某些场合信仰是合理有用的，但它是科学的对立面 (the antithesis of Science)。
- 课堂比喻（转写独有）：野外工作是"一整年做个乖孩子"，最后拿到的一张满是数字的电子表格就是包装好的圣诞礼物；**统计学就是拆包装的过程**——看看里面到底是你想要的那个 pattern，还是 Aunt Bertha 送的又一双袜子。

### 2.2 假设 (hypothesis) 与两类经验检验

- **假设 (hypothesis)**：一个我们认为**可能**为真的陈述。
- **理据 (rationale)**：论证该假设与我们已有的证据一致的那套说理。
- 绝大多数经验检验分两类：

| 类型 | 做法 | 能否推断因果 | 例子 |
|---|---|---|---|
| **操控性研究 (manipulative)** | 研究者制造处理组 (treatment) 与对照组 (control)，人为施加/withhold 处理，再比较响应 (response) | **有时可以推因果**：如果处理前两组相同、处理后不同，则合理相信是处理**造成**了差异 | 随机把小鼠分两组，一组暴露某化学品，一段时间后比较两组癌症发生频率 |
| **观察性研究 (observational)** | 利用自然种群中已存在的变异，测量并分析 | **通常不能推因果** | 想知道"体型大的动物是不是更好的竞争者"——我们无法直接改变动物体型，只能测量不同体型个体的竞争能力 |

- 观察性研究**不是**"随便看看然后讲个故事"：数据同样必须被严格分析并与假设比较。它之所以叫观察性，只是因为变异是自然发生的、不是我们制造的。
- 观察性研究的因果困境示例：即使发现"大个体竞争力更强"，也分不清是"大 → 竞争力强"还是"竞争力强 → 长得大"。要回答这个，需要额外的研究。

### 2.3 实验设计中的重要概念

> 手册强调：**没有唯一正确的实验设计**。通常有好的、不那么好的、和很多糟糕的设计。使设计"好"的最重要一点是**它可行 (practical)**——科学家做得到。糟糕的设计根本给不出正确类型的证据；**哪怕你把计划的数据全部收齐，也可能什么都说明不了。**专业科学家也常设计出不够好/不够高效的实验，所以**开工前一定要让同行帮你看设计**。

#### (1) 对照 (The control)
- 定义：**不接受实验处理的研究组**，作为比较的基线 (baseline)。
- **常见误解：不是每个实验都必须有对照。**只要实验能让我们研究"关注因子在不同水平下"的效应就够了。
- 例：蚊子飞行速度 vs 气温，测 10 °C 与 20 °C——哪个是对照？其实不需要定义对照；0 °C 对水有特殊含义，对蚊子未必有特殊含义。直接比较两个温度下的飞行速度即可。
- **观察性研究尤其常常没有对照**：每个个体的体型都不同，没有"控制组"，分析时是"每个个体与每个其他个体比较"（这就是后面线性回归要做的事）。

#### (2) 随机性 (Randomness) —— *The Literary Digest* 1936 惨案
- 1936-10-31，《文学文摘》发布美国史上当时最大规模的大选前民调，预测共和党 Landon 以 57% : 43% 大胜罗斯福。三天后开票：**罗斯福 61% : 37% 大胜**。杂志信誉崩塌，两年后倒闭。
- **错在哪？** 抽样框来自**杂志订阅名单、汽车登记记录、电话簿**。1936 年是大萧条最深处，只有有闲钱的人才订杂志、买汽车；很多低收入家庭没有电话。于是样本**不成比例地偏向富裕选民**，而富人更倾向投共和党。
- **教训**：若想对某总体下结论，**抽样必须随机**。
- **现实修正**：实际上大多数样本都不是真正随机的。例如你研究蝾螈，样本只包含"你能抓到的"蝾螈——它们可能更慢、更不隐蔽、更不谨慎。所以设计实验时该问的不是"样本是否随机"，而是 **"是否足够随机 (random enough)"**——即，**相对于我们要研究的变量而言是否随机**。这常常没有绝对答案，但**如果你无法给出一个有说服力的"是"，你的结果就很难让有科学素养的读者信服**。

#### (3) 混杂因素 (Confounding factors)
- 定义：可能影响研究对象、并有可能搅乱 (confound) 研究结论的其他因素（年龄、性别等）。
- **真正的麻烦在于：混杂因素与我们要研究的因子不独立时。**
- 手册 Figure 1.1 的经典例子：研究"体型 → 竞争力"，但在一个**雄性比雌性大**的种群里；假设**体型本身不影响竞争力，而性别影响**（雄性更强）。如果只画"竞争力 ~ 体型"的最佳拟合线而不考虑性别，就会**错误地推断出体型效应**。
- 应对：① 在每个性别内部分别研究体型效应；② 用线性回归把混杂因素放进模型（Week 3）；③ **无论如何，第一步永远是意识到它们可能存在**——这是实验设计的重要一环。

#### (4) 统计功效 (Power)
- 定义：实验**检测出研究者想研究的效应**的能力。
- 取决于三样东西：**① 效应量 (effect size)；② 数据中未被解释的变异 (unexplained variability / noise)；③ 样本量 (sample size)。**
- 例（黄松花栗鼠 *Tamias amoenus*，Schulte-Hostedde & Millar 2000）：成年雌性头骨真实均长 36.95 mm，雄性 36.49 mm，则
  $$\text{effect size} = 36.95 - 36.49 = 0.46\ \text{mm}$$
  注意：**开始实验时你并不知道这个数**——这正是实验要去发现的东西。
- **噪音 (noise)**：头骨长度还受基因、幼年食性等影响；若我们没有这些数据，这部分变异就出现在数据里却无法解释。
- **测量误差 (measurement error)** 永远是无法解释的——如果我们知道某次测量错了，直接改掉就好了。
- 效应最容易被检测到的情形：**效应量相对于未解释变异较大**。效应量通常改变不了（系统给你多少就是多少），但**噪音常常可以降低**：① 设计实验以最小化测量误差；② **解释变异而非移除变异**（把更多预测变量纳入模型 —— 见线性回归）。
- **功效分析 (power analysis)**：若能猜出效应量与未解释变异，就能算出需要多大样本才有合理机会检测到效应（手册 Figure 1.3：α = 0.05、效应量 0.46 mm、组内 SD 0.50 mm、用两样本 t 检验时，检测概率随每性别样本数上升的曲线）。本单元不详细讲。
- **无正式功效分析时的实用捷径**：看别人怎么做的。同类问题、同类系统的研究者用 20 或 50 的样本量就得到强结果，那你大概也行；如果他们要上千才得到微弱结果，那你也需要非常大的样本。

#### (5) 可重复性 (Repeatability) vs 可复现性 (Reproducibility)
- **Repeatability（可重复性）**：**同一测量做两次**（或别人按你的方案做）**结果应当相同**。可重复性低 → 测量误差大 → 数据噪音大。
  - 高可重复性例：数家麻雀 (*Passer domesticus*) 巢里的蛋数——数 100 次都一样。
  - 低可重复性例：蛾/蝶**翅膀磨损度 (wing wear)**（可指示年龄与是否迁飞，Deinert 2003）。鳞片难以逐个数清，常用 1–7 目视等级；即使每级定义精确，不同观察者、甚至同一观察者在不同日子，都可能给同一只翅膀不同评分。
  - 解决方案：① **由同一个观察者在短时间内完成全部测量**；② **重复测量后取平均**——**平均值比单次测量更可重复**。
  - 若必须用不同观察者的数据，有时可在分析中校正观察者间差异（ANOVA 那一章会讲）。
- **Reproducibility（可复现性）**：**别人按你的方法完整重做你的实验/分析，得到相同结果**。因此**方法必须记录得精确而详细**；若中途修改了方法，必须极其清楚地说明何时、如何修改。若别人无法照你的方法精确重做，你的工作就不可复现。

#### (6) 取样单元 (Sampling units) —— 早期研究者最常见的设计硬伤
- 定义：**我们希望在其中检测到模式的那个总体的成员**。
- 例 A：比较雄性与雌性虹鳟 (*Oncorhynchus mykiss*) 的代谢率 → 我们在**鱼**之间找模式 → 总体 = 虹鳟，取样单元 = **单条鱼**。
- 例 B：比较**暖湖 vs 冷湖**中虹鳟的代谢率 → 我们在**湖**之间找模式，"其鱼的代谢率"只是湖的一个特征 → 总体 = 湖，取样单元 = **单个湖**。
- **多层抽样 (multi-level sampling)**：例 B 中每个湖的代谢率是由该湖若干条鱼估计出来的。每湖多取几条鱼会**提高估计精度、降低测量误差、减少噪音**；但**并不增加"关于湖"的样本量**——只采两个湖，样本量就是 2，不管你抓了多少条鱼，都无法对暖湖冷湖下结论。
- **误判取样单元 → 用不合理的小样本下结论**，是新手最常见的设计错误。

### 2.4 数据类型 (Types of data)

```
数据
├── 数值数据 (numerical data)
│   ├── 离散 (discrete)：范围内只能取某些值，常为整数。例：每个鸟巢的蛋数（不可能 3.5 个）
│   └── 连续 (continuous)：范围内可取任意值。例：体重（小数位数只受仪器精度限制）
└── 分类数据 (categorical data)：名称/类别而非数字。例：一组树的物种名
    ├── 二分数据 (dichotomous)：只有两个类别。例：雌/雄；死/活
    └── 有序数据 (ordinal)：类别可以被逻辑排序。例：Likert 量表
```

- **Likert 量表**（以组织心理学家 Rensis Likert 命名）：典型五级——strongly disagree / disagree / neither agree nor disagree / agree / strongly agree。它是**有序**的，因为 "disagree" 逻辑上位于 "strongly disagree" 与 "neither" 之间。
- **关键警告**：研究者常给有序类别贴数字（1–5），**但它们仍然是类别，不是数字**。判别方法：**试着做算术**——五个 "strongly disagree" 加起来并不等于一个 "strongly agree"！
- 有时一类数据可以转换成另一类（线性回归那章会讲）。

### 2.5 一些有用的取样方法 (Sampling methods)

- 简单情形（如英国栎 *Quercus robur* 的树围 vs 年龄）：定义总体（如 Lyme Park 的栎树）→ 随机选树 → 测树围 + 取树芯定年。**即使这么简单，取样协议也必须精确定义**：怎么选树？在离地多高处量周长？如果正好那个高度有枝条突出怎么办？
- **样方取样 (quadrat sampling)**：通常是固定尺寸的正方形（刚性方框或用绳子围出；有时也用圆形甚至三角形"样方"——术语上略有滥用）。采样落在样方"内"的个体。**必须定义什么叫"内"**：植物可能部分在内；动物可能在取样期间进出。研究者需事先决定：只算完全在内的，还是算所有部分在内的？最后**跨多个样方合并结果**来推断整个生境斑块的性质。
- **样线取样 (transect sampling)**：建立**线**而非面。设定起止点，用绳子拉线，采样正落在绳下的个体；或不拉可见导引线，直行并采样距样线一定距离内的所有个体。
- **样方/样线的摆放**：可随机放置，也可均匀间隔。**最关键的是：摆放位置必须与所要研究的响应变量独立。** 例：若目标是评估花密度，绝不能优先把样方放在花多的地方。设计出无偏的定位协议往往需要仔细思考。
- **行为学取样**：第一步是**为每个待记录行为建立精确定义**——好定义使行为可被无歧义识别，从而保证可重复性。
  - **扫描取样 (scan sampling)**：预先设定固定时间点，在这些时刻记录种群中每只动物在做什么。优点：可估计**时间预算 (time budget)**，不会让某只动物的行为被过度加权。缺点：若动物可以离开取样点且在外面行为不同，数据会有偏；且**不告诉我们行为的先后顺序**，若目标是"由当前行为预测未来行为"就不适用。
  - **焦点跟踪 (focal follow)**：选定一只动物，记录其在固定时段内做的一切。优点：得到某个体的详细行为与**行为顺序**信息。缺点：聚焦个体，对整个种群的信息量少于扫描取样。
- 结论：**没有唯一"正确"的取样方法**，选最可能提供你所需信息以回答研究问题的那个。

### 2.6 频率学派假设检验 (Frequentist hypothesis testing) 的核心逻辑

- 创立者：**Ronald Aylmer Fisher (R. A. Fisher)**，生物学家/遗传学家/统计学家。课堂补充：他是 20 世纪初群体遗传学、统计学等多个领域的奠基人之一；也因优生学 (eugenics) 主张而具争议——**"leaving that aside, his ideas were really important."**
- Fisher 的核心论证：**我们无法证明一个假设为真，但可以通过证明"替代解释很可能为假"，来表明这个假设很可能为真。**

#### 三个核心术语
- **零假设 (null hypothesis, $H_0$)**：陈述"没有差异 / 没有效应 / 一切只是偶然"。
- **研究假设 (research hypothesis)**：我们真正想支持的陈述。
- **p 值 (p-value)**：
  > **在零假设为真的前提下，仅凭偶然 (by chance alone) 就获得一个至少和观测数据一样极端的结果的概率。**

  手册原话：**"频率学派假设检验的根本问题 —— What is the probability that we would obtain a result at least as extreme as the one in our observed data by chance alone?"** 手册说：如果这本手册里你只打算背一样东西，就背这句话。

#### 显著性判读惯例
| p 值范围 | 通常表述 |
|---|---|
| $p < 0.05$ | **统计显著 (statistically significant)**，可拒绝 $H_0$，研究假设很可能为真 |
| $0.05 \le p < 0.10$ | **弱显著 / marginally significant**——弱证据 |
| $p \ge 0.10$ | 证据不足，不能拒绝 $H_0$ |

- **但 0.05 完全是任意约定 (arbitrary convention)**，没有任何魔力。**p 值实质上是证据强度的连续度量**：p = 0.05 只比 p = 0.0562 的证据略强一点点。因此**报告精确 p 值**，让读者自己判断证据强度。

#### p 值的两条常见误解（手册专门列出）
1. **低 p 值不能"证明 (prove)"你的研究假设。**
   类比：走进房间看到桌上十枚便士全是正面，你会推断有人摆的。"全部同面"纯属偶然的概率（即"硬币随机落下"的 p 值）< 0.002。但它们**仍然可能**是随机落成这样。所以你有**证据 (evidence)**，没有**证明 (proof)**。
   （附带说明：这一点常让非科学公众困惑——科学家回避 "proof" 一词，让人误以为我们的证据比实际更弱。）
2. **高 p 值不构成支持零假设的证据，也不允许你拒绝研究假设。**
   高 p 值只说明你**本可能 (could have)** 靠偶然得到观测结果，而不是说你**确实 (did)** 是靠偶然得到的。类比：十枚硬币中六正四反，"至少六枚同面"的偶然概率是 0.7539——你没有理由相信有人摆过，**但你也没有证据说明没人摆过**，因此不能拒绝"有人摆过"这个假设。
- 课堂补充（Fisher 品茶实验）：Fisher 算出的 1/70，**不是"Muriel Bristol 是靠猜的概率"**——她要么猜了要么没猜，这个事实对我们永远隐藏；它是**"如果她纯靠猜，能看到这么极端结果的概率"**。

#### 报告 p 值时必须同时报告效应量
- 只有 p 值是不够的。若发现效应，还要报告**效应量 (effect size)**。厕所数据里最佳估计就是观测差值 27.63 s。
- 手册示范：**"People who entered the women's restroom in our study spent 27.63 s longer on their visits than people who entered the men's restroom. This difference was marginally significant (p = 0.05652)."**

### 2.7 单尾与双尾检验 (One-tailed and two-tailed tests)

| | 研究假设 | 零假设 | p 值取哪部分 |
|---|---|---|---|
| **双尾 (two-tailed)** | "两组均值**不同**" | "两组均值不同" 的反面：不存在差异 | **两条尾巴之和** |
| **单尾 (one-tailed)** | "A 组均值**大于** B 组"（有 *a priori* 预期） | "A 组均值**不**大于 B 组" | **只取一条尾巴** |

- 厕所例：双尾 p = 0.05652（下尾 0.02734 + 上尾 0.02918）；若事先就预期"女厕停留更久"，则单尾 p = 0.02918。
- **重要原理：有 *a priori* 知识产生的假设会得到更低的 p 值。**
- **但绝对不能用同一批数据既生成假设、又检验该假设！** 例如不能先看 Figure 2.3 的直方图发现"女性好像更久"，再用同一批数据检验这个假设。
- **为什么？（手册的量化论证，务必读懂）**
  假设 $H_0$ 实际为真（如男女平均 IQ 无一致差异）。抽 20 男 20 女，纯偶然也会有差异；假设本次样本里女性 IQ 更高。若我们据此提出"女性 IQ 更高"再做单尾检验，就是在问"观测差值是否落在置换分布的前 5%"——**但我们已经知道它至少在前 50%（否则我们根本不会检验这个方向）**。于是推断出"显著"的概率变成 $0.05 / 0.50 = 0.10$。**即：用同一数据形成并检验假设，会高估证据强度（假阳性率翻倍）。**
- 老师坦承（讲义 notes）：**"For me this is a very difficult idea, and it took several readings (and in fact several years) for me to really understand it."** —— 现在不直觉是正常的，回手册反复读。

### 2.8 数据准备 (Preparing data for analysis)

> 手册：**新手分析数据时最常犯的错误就是把数据组织错了。好在这很容易避免。**

**唯一正确的格式：表格 (table)**
- **每一行 = 一个观测 / 一个数据点 (data point)**
- **每一列 = 对该观测的一项描述**
- **第一行 = 表头 (header)**，写各列的名称

手册例：Hayden & Essink 于 2003 年 11 月在密歇根 Grandville 的 Rivertown Crossings Mall 记录了人们在厕所停留的时间（restroom_time.csv）：

| duration | gender | date |
|---|---|---|
| 93 | women | Thursday |
| 183 | women | Thursday |
| … | … | … |
| 110 | men | Saturday |

- **响应变量 (response variable)** = duration（他们感兴趣的是停留时长如何依赖于所进厕所的性别）。
  - 注意：他们**无法直接观察人的性别**，只能记录**所进厕所的性别**。
- **预测变量 (predictor)** = gender、day。别的书/软件称之为 independent variables、covariates、factors；**本手册统一叫 predictors**。
- 惯例上把响应变量放第一列，但**不是必须的**。
- **Excel 用 "Save As…" 存成 .csv**——csv 是没有微软花哨字段码的纯文本文件，R 能读。

### 2.9 三条路线：比较两组均值

#### 场景界定（本周方法的适用条件）
- **预测变量**：分类且恰好 **2 个水平**（如 men/women、M/F、Ice/CO2）
- **响应变量**：**数值**（连续或离散）
- **问题**：这两组的**均值**（或 Wilcoxon 的**平均秩**）是否不同？

#### 路线 1：Monte Carlo 置换法 (permutation)
**逻辑**：若 $H_0$ 为真（两组用法/性质没有真实差异），那么**每个观测值本来完全可以属于任何一组**——数据中 duration 与 gender 的任何一种重新配对，都和我们实际看到的那一种同样可能。于是：
1. 把响应值随机重排（**置换 permutation**），保持各组的样本量不变；
2. 计算这一次重排下的组间均值差；
3. 重复 $10^4$–$10^5$ 次，得到"**纯偶然能产生的差值分布**"；
4. 数一数其中有多少次的差值**至少和观测差值一样极端**，除以总次数 = **p 值**。

**优点**：直观、准确、**不对分布形状作任何假设**（我们只检验"两个样本是否来自同一分布"）。
**缺点**：计算量大（手册的 100,000 次循环要跑一分多钟；在没有现代计算机的年代要跑几天甚至几周）；需要自己写代码。

#### 路线 2：t 检验 (t-test)
- **发明者**：**William Sealy Gosset**，都柏林 **Guinness 啤酒厂**的化学家兼统计学家，因公司禁止员工发表可能有利于竞争对手的成果，故以笔名 **"Student"** 发表。他当时关心的是**基于样本比较不同大麦品种的产量**——和"基于样本比较男女厕所平均停留时间"是同构的问题。
- **核心洞见**：在一定条件下，"纯偶然可得的均值差分布"（即 Monte Carlo 那张直方图）是**可预测的**。只要知道两件事——**样本方差 (variance)** 和 **样本量 (sample size)**——就能直接算出该分布，无需重抽样。这个分布叫 **t 分布 (t-distribution)**，基于它的检验叫 **t 检验**。
- **三种 t 检验**：

| 类型 | 问题 | R 语法 |
|---|---|---|
| **两样本 t 检验 (two-sample t-test)** | 两个总体的均值是否不同？ | `t.test(a, b)` 或 `t.test(y ~ group, data = df)` |
| **单样本 t 检验 (one-sample t-test)** | 某一个总体的均值是否不同于某个关注值？ | `t.test(v, mu = x)` |
| **配对 t 检验 (paired t-test)** | 两个可**成对**的总体，成员间的**差值**是否不为 0？ | 本质上就是对"配对差值"做单样本 t 检验 |

  - **配对 t 检验的正确理解（手册特别强调）**：它其实**只是单样本 t 检验的一个特例**。此时**取样单元是"对" (the pair)**（例：夫妻这一对），**响应变量是对内差值**（例：丈夫停留时长 − 妻子停留时长）。做法：先算对内差值，再做单样本 t 检验问"平均对内差值是否显著不为 0"。
  - 何时该配对？当我们预期"成对成员的响应是相关的"时。例：也许人会因为猜测伴侣会待很久而自己也待久一点（否则出来还得干等）。
- **Welch 校正 (Welch's t-test)**：R 的 `t.test()` **默认**使用，是对 Student t 检验的修正，**用于两组变异程度不同（方差不齐）的情形**。

#### 路线 3：Wilcoxon 检验 (Wilcoxon test)
- **何时用**：数据在组内**明显不服从正态分布**，或**响应变量本身是有序 (ordinal) 数据**。
- **原理**：任何数据——不论分布如何——都可以**排秩 (rank)**。最小值给最低秩；**相同的值给相同的秩**。
  - 手册例：响应 {1.5, 3, 17, 3, 0.9, −7, 14} → 秩 {3, 4, 7, 4, 2, 1, 6}
    （−7 最小 = 1；0.9 = 2；1.5 = 3；两个 3 并列 = 4；14 = 6；17 = 7）
- 然后问：**"若 $H_0$ 为真（组别与秩无真实关系），仅凭偶然，某一组的平均秩至少低到观测水平的概率是多少？"** 答案同样是 p 值，且**对任何数据集都能计算**。
- **Mann-Whitney U 检验**是 Wilcoxon 检验的一个特例。
- **⚠️ 最重要的概念澄清（手册明确点名的错误认识）**：
  > **"Some people believe that the Wilcoxon test is simply an alternative to the t-test that can be used when the data are not normally distributed. This is incorrect."**

  **t 检验问的是"两个总体的均值是否不同"；Wilcoxon 问的是"两个总体的平均秩是否不同"——这是两个不同的问题。**

  **彩球反例（必记）**：一盒彩票球，一半红一半白。红球中一半写 1，另一半写 10；所有白球都写 2。
  - 红球均值 $= (1+10)/2 = 5.5$，白球均值 $= 2$ → **均值不同**。
  - 但对每个白球而言，比它数字大的红球数量**恰好等于**比它小的红球数量 → 白球的平均秩 = 全体的平均秩 = 红球的平均秩 → **平均秩完全相同**。
  - 因此 t 检验和 Wilcoxon 会给出**不同的答案**——它们本来就在回答不同问题。

---

## 三、公式与图表

### 3.1 基本描述统计量

**样本均值 (sample mean)**
$$\bar{x} = \frac{1}{n}\sum_{i=1}^{n} x_i$$
- $x_i$：第 $i$ 个观测值；$n$：样本量；$\bar{x}$：样本均值（对总体均值 $\mu$ 的估计）。

**样本标准差 (sample standard deviation)**
$$s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar{x})^2}$$
- 分母用 $n-1$（自由度）而非 $n$，使之成为总体方差 $\sigma^2$ 的无偏估计。
- **样本方差 (variance)** $s^2$ 度量"个体观测彼此有多不同"——正是 Gosset 需要的两个量之一。

**标准误 (standard error, SE)**（手册定义：标准差除以样本量的平方根）
$$SE = \frac{s}{\sqrt{n}}$$
- 含义：**度量"样本均值接近总体真实均值"的把握程度**。样本越大，SE 越小。
- 注意区分：**SD 描述数据的离散程度；SE 描述均值估计的不确定性。**
- **误差棒 (error bars)** 通常画 ± 1 SE，让读者直观感受两组到底差多少。

### 3.2 t 统计量 (t-statistic)

**两样本 t 检验（Welch 版本，R 的默认）**
$$t = \frac{\bar{x}_1 - \bar{x}_2}{\sqrt{\dfrac{s_1^2}{n_1} + \dfrac{s_2^2}{n_2}}}$$
- 分子 $\bar{x}_1 - \bar{x}_2$：两组样本均值之差（**观测值与零期望的距离**；$H_0$ 下期望差为 0）。
- 分母：差值的标准误 (standard error of the difference)。
- $s_1^2, s_2^2$：两组的样本方差；$n_1, n_2$：两组样本量。

**手册对 t 统计量的直白解释**：
> t 统计量表明**观测值离零期望有多远**，且**已按观测数据的标准差做过缩放**。t = 2 意味着两组均值之差相当于观测数据的两个标准差。**t 越大 → 组间差异越大 → p 值越低。**

**Welch–Satterthwaite 自由度**
$$df = \frac{\left(\dfrac{s_1^2}{n_1} + \dfrac{s_2^2}{n_2}\right)^{2}}{\dfrac{(s_1^2/n_1)^2}{n_1-1} + \dfrac{(s_2^2/n_2)^2}{n_2-1}}$$
- 这就是为什么 R 输出的 df 常常是**小数**（如 df = 21.611、92.973、18.1、27.9、22.1）——Welch 校正下 df 不是整数。

**单样本 t 检验**
$$t = \frac{\bar{x} - \mu_0}{s/\sqrt{n}}, \qquad df = n - 1$$
- $\mu_0$：我们关心的那个参照值（例：120 秒）。

**配对 t 检验**：令 $d_i = x_{1i} - x_{2i}$，则
$$t = \frac{\bar{d}}{s_d/\sqrt{n}}, \qquad df = n - 1$$
- $n$ = **对数**（不是总个体数！）。

### 3.3 自由度 (degrees of freedom, df) 与 t 分布形状

- **df 随样本量增大而增大，它决定 t 分布的形状。**
- **df 大** → t 分布**接近经典正态分布**。
- **df 小** → t 分布出现 **"肥尾" (fat tails)**，这叫 **尖峰厚尾 / 轻峰态 (leptokurtosis)**。
- **肥尾意味着极端值更多 → 同样的 t 值对应更高的 p 值。** 这正确地反映了：**我们对小样本得出的估计信心更低。**
- 实务上：R 用 df 与 t 值算 p 值，你几乎不会自己用它们；但**有些期刊要求报告**，所以照报。
- 课堂原话：**"Back before we had computers, we calculated these numbers by hand, and used them to find p-values in tables. We do not really need them any more, but some readers expect to see them, so it is usually a good idea to report them."** —— 这就是"临界值表"在今天的地位。

### 3.4 95% 置信区间 (95% confidence interval)

- **正确解释（手册的说法，比较绕）**：设想我们能从一个"性质与观测数据相似"的总体中重新抽一个**同样大小**的样本（即：源总体中两组的差异与我们数据中相同，组内变异也与我们数据中相同）。那么**新样本中观测到的组间差异有 95% 的机会落在这个 95% CI 内**。
- **⚠️ 它不是"我们有 95% 把握真值落在这个区间内"。**
- 尽管如此，人们常把它当作"真值可能落在的大致范围"的粗略替代。
- **实用判读**：两样本 t 检验的 95% CI 是**差值**的区间。**若区间跨过 0，则双尾 p > 0.05。**
  - 例（身高数据）：CI = [0.0294, 0.1709]，不含 0，对应 p = 0.0077 < 0.05。
  - 例（厕所数据）：CI = [−0.457, 55.709]，**含 0**，对应 p = 0.0538 > 0.05。

### 3.5 Fisher 品茶实验的概率推导（课堂完整推导，务必掌握）

设有 8 杯茶，4 杯"先倒奶"(milk first)，4 杯"先倒茶"(tea first)。**受试者被告知每类各 4 杯**。问：纯靠猜，全部答对的概率？

**关键简化**：只需考虑她挑出的 4 杯"先倒奶"——若这 4 杯全对，剩下 4 杯自动全是"先倒茶"，也就全对了。

把她想象成手上有 8 张牌（4 张 "milk first"、4 张 "tea first"），依次放到杯子上：

| 第几个"先倒奶"的杯子 | 此时剩余的 milk-first 牌 / 剩余总牌数 | 猜对概率 |
|---|---|---|
| 第 1 个 | 4 / 8 | $\tfrac{4}{8} = \tfrac{1}{2}$ |
| 第 2 个 | 3 / 7 | $\tfrac{3}{7}$ |
| 第 3 个 | 2 / 6 | $\tfrac{2}{6}$ |
| 第 4 个 | 1 / 5 | $\tfrac{1}{5}$ |

各步独立（条件概率连乘）：
$$P(\text{全对}) = \frac{4}{8}\times\frac{3}{7}\times\frac{2}{6}\times\frac{1}{5} = \frac{24}{1680} = \frac{1}{70} \approx 0.0143$$
（老师的口算捷径：$3 \times 2 = 6$ 可与分母的 6 约掉。）

**等价的组合写法**：从 8 杯中选 4 杯的方式共 $\binom{8}{4} = 70$ 种，只有 1 种全对：
$$p = \frac{1}{\binom{8}{4}} = \frac{1}{70} \approx 0.014$$

**Fisher 的推论**：我们不知道她是不是猜的，但**靠猜全对是不太可能的**；**如果某件事不太可能靠偶然发生，我们就可以推断有偶然之外的东西在起作用**。—— 这就是频率学派统计的中心思想。
（顺带：$1/70 = 0.0143 < 0.05$，所以这是"显著"的。这也是"必须全部 8 杯都答对"这个严苛设计的来由。）

### 3.6 超级碗掷币例（Lecture Part 1 的引入例）

- 背景：超级碗开场掷币决定谁先拿球；每年专铸一枚只用一次的纪念币（之后送 Canton, Ohio 的名人堂玻璃柜）。当年超级碗投注总额超 40 亿美元，其中**约 4000 万美元押在掷币结果上**。
- 实验：NFL 只允许掷 100 次（**这是实验的约束条件 constraint**），结果 **62 次正面**。
- 光看数据无法判断——毕竟正好 50:50 反而不太可能。**怎么评估证据？** → **和"真正公平的硬币"的结果比较。**
- 模拟：先做 10 组 100 次投掷（黑点=正面、白圈=反面），从未接近 62；10 组太少 → 做 **1,000,000 次**。
- 结果：**≥62 次正面 10,510 次；≥62 次反面 10,470 次；合计 20,980 / 1,000,000 ≈ 2%**（**双尾**！）。
- 结论：公平硬币出现"某一面 ≥62 次"的概率只有约 2% → **有证据表明这枚硬币不公平**。
- 这个例子直接引出频率学派的根本问题与 p 值。

### 3.7 学生身高数据的 Monte Carlo 演示（Lecture Part 1 的第二例）

- 数据：往年本单元 **25 名女生 + 13 名男生**的自报身高（共 38 人）。男生平均**高 0.1 m**。
- 问题：这是总体中真实存在差异的证据，还是抽样偶然？
- **置换步骤**：把 38 人合并成一组 → 随机抽 25 人当 **"pseudo-females"**、其余 13 人当 **"pseudo-males"** → 算差值 → 重复。
- 前 4 次：3 次 pseudo-男更高、1 次 pseudo-女更高（**注意出现负号**），但差值**从未达到**观测的 0.1 m。
- **10,000 次**后的直方图：蓝色区域 = 差值小于观测值；**红色两尾 = 差值至少和观测一样极端，共 46 / 10,000 → p = 0.0046**。
- 结论：有证据表明总体中男女平均身高不同。
- **名字由来**：因为分布是靠"碰运气"生成的，故以著名赌城命名为 **Monte Carlo 分析**。

### 3.8 数据可视化方式的判读要点

| 图 | 用途 | 判读要点 / 做图要点 |
|---|---|---|
| **直方图 (histogram)** | 看**单组数据的分布形状**，**检查正态性假设** | 是否有中间的峰、两侧渐渐变细的"钟形 (bell curve)"？是否单调递减、是否截断、是否离散？小样本时看不出漂亮钟形是**正常的** |
| **分组直方图（上下两栏）** | 比较两组分布 | **两栏必须用完全相同的分箱 (bins)**，否则不可比 —— 这就是手册用 `b=20*(1:22)` 手动指定 breaks 的原因 |
| **柱状图 + 误差棒 (bar chart with SE bars)** | 报告 **t 检验**结果最直观的图 | ① 坐标轴要有标签（x 轴 = 组名，y 轴 = 变量名 + **单位**）；② 文字要够大能读；③ **必须有误差棒**（通常 ± 1 SE），因为均值只是估计；④ **必须有图注 (figure legend)** |
| **点图/散点带均值差** | 展示原始数据与组间差 | 讲义 slide 8 用的形式：两列散点 + 中间红条表示均值差 |

**图注 (figure caption) 的规范**（Practical 特别强调）：
> 只要产出图，就必须配图注。图注要尽可能简洁，但要包含足够信息，使读者**即使不读正文的任何其他内容也能看懂这张图**（因为有些偷懒的读者真的只看图！）。

- 示例（Practical Q1.4）：**"Figure 1. Femur lengths of 15 female *B. madagascariensis* sampled from museum collections in the United States."**
- 示例（Lecture slide 33）：**"Figure 1. Mean self-reported heights of men and women in the field course prep unit. Error bars indicate standard error."**
- 示例（手册 Figure 2.8）：**"Mean visit durations to the men's (n = 51) and women's (n = 46) restrooms at Rivertown Crossings Mall in November of 2003. Error bars show one standard error."**

### 3.9 检验选择决策表（Lecture Part 2 slide 40，核心考点）

| 我们想知道的是： | 正态性假设满足吗？ | 用： |
|---|---|---|
| **平均秩 (mean rank)** | 满足或不满足**都可以** | **Wilcoxon** |
| **均值 (mean value)** | **满足** | **t 检验** |
| **两者都行 (either will do)** | 不满足 | **Wilcoxon** |
| **均值 (mean value)** | **不满足** | **Monte Carlo**（可能得自己写代码） |

**手册版的四条规则（更细致，含"稍微不正态"的实务处理）**：
1. 若你关心**平均秩**，就必须用 Wilcoxon。一种常见情形是**响应变量为有序 (ordinal) 数据**（如 Likert 量表）——有序数据可排秩但不是数值，"均值"说不清含义，"平均秩"反而是有信息量的度量。
2. 若你关心**均值**且数据**近似正态**，用 t 检验。
3. 若你关心均值、数据**不正态但偏离不太极端**，**仍可能可以用 t 检验**——**t 检验对小幅偏离正态是稳健 (robust) 的**。但此时报告结果时**必须警告读者数据不正态，并保守解读 p 值**。例如得到 p = 0.04，只当作"差异的弱证据"。
4. 若数据**明显不正态**，且**平均秩足以回答你的生物学问题**，Wilcoxon 是好选择。
5. 若数据明显不正态、**但你就是要比较总体均值、平均秩不够用** → **t 检验和 Wilcoxon 都不合适，回退到 Monte Carlo**（Monte Carlo 只检验"两个样本是否来自同一分布"，**对分布形状不作任何假设**）。

---

## 四、课堂补充

> 以下内容出自 08-Nov 现场课堂转写与 slides 的口头 notes，是 slides 正文与手册文本之外的信息。

### 4.1 Fisher 与"品茶女士" (The Lady Tasting Tea) —— 整个单元的开场故事
- 1919 年，年轻的 Fisher 在伦敦附近的 **Rothamsted** 研究站工作。那是**生物学实验室**，不是数学/统计实验室。他的职责是帮助经验研究者设计植物实验，**但研究者们未必觉得自己需要那么多帮助，所以他不一定总有很多事做**。
- **Muriel Bristol** 是那里的**藻类生物学家**。某天在公共休息区，Fisher 提议给大家泡茶，她也接受了。
- 泡好端来后她说："我喝不了这个，我要**先倒奶** (milk first)。"
- Fisher 作为极度定量的科学家反驳：**同样多的奶倒进同样多的茶里，混合之后顺序不该有影响**——这是无稽之谈。她坚持说她能尝出来。
- 在场的另一位研究者 **William Roach** 说："那就测试她啊。"（老师补了一句：Roach 可能有偏袒，因为**大约一年后他娶了她**——不过有偏的是 Roach 不是 Fisher。）
- 他们去厨房做了 **8 杯茶，4 杯先奶、4 杯先茶**，请她逐杯品尝并说明顺序。**她全部 8 杯都答对了。**
- Roach 说"证据在此，她显然能分辨"。Fisher（不喜欢自己出错）说 **"not so fast"——我们怎么知道这不是运气？**
  - 注意关键细节：**她知道每类各有 4 杯**，这个信息决定了概率计算的形式（见 §3.5）。
- 老师现场向学生互动提问："在座有很多英国人——**先放奶还是先放茶**？"以及"**如果给你反过来的那杯，有多少人能尝出差别？**"

### 4.2 老师对本单元的期望与学习方式（非常重要的"元信息"）
- **"This isn't a unit about memorizing."** 老师**不会要求背任何检验或实现方式**。有些东西你会因为反复用而自然记住；只偶尔用到的，**查就好了**（这正是研究者的做法）。**任何评估都允许你查手册、教材、互联网。**
- 目标不是记忆，而是：**当你以后去查的时候，你会认出"我见过这个、我以前搞明白过、我能再来一次、我还能在它之上继续搭建"。**
- **"the really core of this unit are the practicals."** 每周 Blackboard 上有一份练习册（8–9 页文字、4–5 道题）。**如果你能自己做完这些 practical，你就学到了这个单元该学的东西。**
- 老师把**所有课程环节都定位为"可选的支持 (optional support)"**：本次讲座、practical 现场课都是 **optional drop-in**，因此**没有 SEAtS 签到码**（课堂上有学生反复问"今天的 code 是什么"，答案是没有）。
- **每周的 live 会话"滞后一周 (run in arrears)"**：本周讨论**上周**做过的 practical——因为学生很难对还没做过的东西提问。流程是先问有没有问题；如果没有，老师就讲他想讲的（检验的扩展、有趣的数据集/玩法）。
- **强烈建议结对做 practical (work in pairs)**：卡住时同伴可能从不同角度、带着不同背景把你带出来；反过来，**你向同伴解释你自认为懂的东西时，学到的往往比自己闷头理解更多**。不强制，可以单干。
- 支持资源清单：① **unit handbook**（放在 **Dropbox** 而非 Blackboard，因为**课程结束后 Blackboard 的东西你就没权限了**，而老师希望你**整个职业生涯都能用这本手册**——他有学生读博了还在用）；② **录播 lecture**（与手册讲同样的想法，但**用不同的数据集、以略不同的方式切入**，且更短、没那么深入，**两者搭配使用最有效**）；③ **discussion board**（可匿名发问；老师会优先回讨论板而非邮件，因为答案能更快传达给所有人）；④ **live drop-in session**；⑤ **AI**。

### 4.3 老师对 AI 的明确态度（转写独有，且与评估方式直接相关）
- **"Over the past few years, it's turned out that AI has gotten very good at giving advice on how to do statistical analyses. And you can make use of it. I do. I use it a lot."**
- **但："use it as a tool to help you learn, and not as a substitute for learning."** 如果让 AI 替你思考，等你以后需要在这些基础之上搭建时，你会发现自己没有需要的地基。
- 关于**评估 (assessment)**（转写独有，slides 与手册都没有）：
  - 形式：**take-home 问题集**，学校规定必须如此。会**提前公布确切日期**，**至少给一周**时间。
  - 难度：**类似 practical 但更简单**——practical 是刻意来挑战你、逼你想清楚概念的；**评估只是看你会不会用**。
  - 规则：**open book / open notes / open code / 可上网**；**必须独立完成（不是小组作业）**，但可在讨论板提问。
  - 老师坦言：因为无法检测 AI 使用，所以**没法禁止**，因此**分数会很高**；但"probably won't be perfect，因为本单元要讲的分析里**有一个** ChatGPT 之类的 AI 仍然会栽跟头"。
  - 老师的价值判断：这对"只想打勾拿学位"的人是坏事（少了考试这根棍子，代价会在三年级/实习时以"不会分析数据"的形式还回来）；对"真心想学的人"是好事——**去掉了"我到底要学什么才能通过考试"的阴影，可以把它当作一件由好奇心驱动的事**。
- 类比：**小学乘法表**——你现在其实不需要背乘法表（掏出手机就能算 7×8），**但如果你想走得比最基础的东西更远，你必须理解你在做什么**，因为你需要用这些基础工具去搭建更复杂的东西。
- 为什么必须理解原理：**"the data that you'll collect as natural scientists is almost never simple."** 野外数据是复杂的——**拿不到平衡的数据集、缺失预测变量、有无法控制的混杂预测变量**。通常你**不能直接从货架上取下一个 t 检验就用，你得在它之上继续搭建**。

### 4.4 老师为什么选 R（转写独有的完整论证）
1. **R 既是数据分析工具，又是一门编程语言** → 极其强大。Excel / Prism / SPSS 是 point-and-click 程序：可及性好，**但你会很快撞到"它能做的事"的天花板**。R **没有上限，唯一的限制是你能不能想出怎么告诉它去做**——"infinitely expandable"。
2. **全世界科学家广泛使用** → 你在这里做的分析，可以把**数据 + 代码**发给日本或玻利维亚的同行，他们能**一模一样地重跑**、看到你做了什么、不满意还能改。这在 Excel/Prism 里非常难（你得告诉别人按哪些按钮、按什么顺序）。**现在发表论文几乎都要一并归档分析代码**，以便他人复现与检查。
3. **巨大的极客用户社区** → 你遇到的坑，几乎可以保证世界上某处有人踩过并写了网页解释（Stack Exchange 等），Google 一下就能找到答案。
- **但学习曲线陡峭**。老师的共情（转写原话）：第一次面对非点击式程序的空白屏幕、要往里打字却不知道打什么，**"It is abjectly terrifying"**——感觉自己永远学不会。**"And after a few days, you'll be typing away as if you barely have to think about it."**

### 4.5 R/RStudio 现场演示的实操细节（新手最容易卡住的地方）
- **先建文件夹再下载数据**：老师明说"**people download things and they can't find them**"是实验室机器上最大的障碍之一。做法：桌面右键新建文件夹（他命名 "SFNS 24"）→ 从 Blackboard 点下载（文件落进 Downloads）→ **把文件拖进新建文件夹**。
- **RStudio 四个窗格**：
  - **左（下左）Console 控制台**：本质是"一个高级计算器"。可直接算数、可定义变量（`x = 3`）。**注意：定义变量后 R 不会输出任何东西**——它接受了命令但你没让它显示；**想看就把对象名打进去按回车**。
  - **左上 Script 脚本窗格**：点左上角**绿色加号**打开。相当于一个装 R 代码的文档。
  - **右上 Environment 环境窗格**：**导入的数据对象会出现在这里，点一下就能看到内容**。
  - **右下 Files 文件窗格**：像普通目录浏览器。
- **为什么要用脚本而不是直接敲控制台**（老师现场演示的例子：算直角三角形斜边）：
  ```r
  # Compute hypotenuse       # 以 # 开头的是注释 (comment)
  S1 = 4                     # 定义一条直角边
  S2 = 7                     # 定义另一条直角边
  hypotenuse = sqrt(S1^2 + S2^2)   # 名字只是名字，随便取；这里取有意义的名字
  ```
  优点：① **选中整块代码点 Run 一次全跑**；② 想改就改一个字母/一个数字然后重跑，**不必重打所有命令**——在控制台里就得全部重敲；③ **可以加注释**，两周后或一年后再打开还知道这段代码干什么；④ **可以保存**，随时复用。
- **导入数据的完整流程（人们最常卡住的第二处）**：
  1. 在右下 Files 窗格找到数据所在文件夹。**机房电脑的文件结构常常很难导航**——老师自己现场就卡住了一次（"So I've demonstrated now where people get stuck"）。**解决办法：点右侧的"三个点 (…)"打开一个正常的目录选择框**，从那里去桌面找文件夹。
  2. **仅仅在 Files 窗格里打开文件夹是不够的**——那只是"显示给你看"，**并没有告诉 R 用这个文件夹**。
  3. **必须再点蓝色齿轮 (blue gear) → "Set As Working Directory"**。R 会在控制台自动跑出一行 `setwd(...)`。
  4. 然后才能 `read.csv("文件名.csv")`。**计算机对拼写极其挑剔 (notoriously finicky about spelling)**。
  5. **跑完命令后如果没有红色报错，就表示成功了**（R 只是回到提示符，不会夸你）。
- **Practical 的加分技巧**：把控制台里自动出现的那行 `setwd(...)` **复制粘贴到脚本最上方**。以后直接双击代码文件打开 RStudio，运行这一行就自动设好工作目录，不用再在 Files 面板里点来点去。**"in the future when you have R codes and data stored in many different folders you will be glad you did it!"**
- 老师对"现在记不住"的安慰：**"you won't remember the things that I'm telling you now as you're walking to the engineering building in 20 minutes. But when you get there and have R open, I think it will help to have seen them."** 这个流程**每周都会做一遍**，会变成**肌肉记忆 (muscle memory)**。

### 4.6 Lecture slides 的口头强调点（notes 里有、正文没有）
- **单/双尾这一节，老师专门叫停**："I want to pause here to introduce an important, but (for me at least) a difficult, idea." 并说这对他也很难，读了好几遍、其实花了好几年才真懂。
- **`==` vs `=` 的致命区别（slide 22 口头强调）**：`which()` 里必须用**双等号**。双等号是**比较**（比较 sex 那一列和字母 "m"）；**如果用单等号，R 会以为你在告诉它"数据里所有的 sex 都是 m"，然后把数据集里每个人都改成男性！**
- **语法洁癖（slide 13）**："pay close attention to syntax… **If your commas, periods and quotation marks are missing or in the wrong places, your commands will not work!**" 建议：**Dropbox 每个 practical 文件夹里都有语法正确的命令，能复制粘贴就复制粘贴。**
- **不要背命令（slide 25 口头）**："If you have been trying to memorize these commands as we go along, you are probably thinking that this is really painful. But, remember, **you do not have to memorise this**… **There is no reason to learn by memorization. You will learn what you need by using these commands when you analyse data!**"
- **Wilcoxon 报告的措辞陷阱（slide 39 口头）**："**Notice that I have not said anything about means! Wilcoxons study mean ranks rather than means.**"
- **负结果 (negative results) 的报告惯例（slide 39）**：**通常省略图**，但正文里仍必须告诉读者：① 没有发现差异的证据；② 用了什么检验；③ p 值是多少。
- **R 做图 vs 点击式软件（slide 33 / 手册 / Practical 三处都提）**：R 做图确实更笨重，**但换来的是对图形远为精确的控制**——在科学里，精确的图对有效传达结果至关重要。研究者常常一次性投入时间做好一套图代码，然后**带着小修改用一辈子**。

---

## 五、Practical 要点

> 文件：`Practical 2(2).md`（题面）与 `Practical 2 answer key(1).md`（答案）。配套还有 `Starter code for Practical 2.R`（Q1 的代码全给了；Q2 需自己补一些；之后基本自己写）。
> 注意：物理文件名叫 "Practical 2"，但按子课程内部周号，这是 **Week 01** 的 practical（对应 Lecture 1 与手册 Ch.1–2）。

### 5.0 学习目标（practical 开头列出）
完成后你将能够：
- 把数据**导入 R** (import data into R)
- 在**向量与数据框中取子集** (subset data in vectors and data frames)
- **检查数据的正态性** (inspect and check data for normality)
- 在 **t 检验与 Wilcoxon 检验之间做选择**
- 在**单尾与双尾检验之间做选择**
- **清晰简洁地报告** t 检验与 Wilcoxon 检验的结果
- 用**图**来展示 t 检验与 Wilcoxon 检验的结果

### 5.1 生物学背景
- **性二型 (sexual dimorphism)**：许多动物中雌雄在大小、形状、行为上不同。理解其如何演化、如何影响物种与种群的生态，是生态学与演化生物学的重要目标。
- 数据来源：**Juarez, Moen & Adams (2023)**, *Journal of Evolutionary Biology* 36(5):829-841 —— 研究美国博物馆藏品中**无尾类 (anurans，即蛙与蟾蜍)** 的性二型。本 practical 用其中三个物种的子集，每种 30 只，记录 **sex、mass (g)、snout-vent length (mm)、femur length (mm)**：
  - ***Boophis madagascariensis***（马达加斯加树蛙）
  - ***Pseudis paradoxa***（南美"缩水蛙" / shrinking frog）
  - ***Dendrobates auratus***（箭毒蛙）
- **为什么用股骨 (femur) 而不是吻肛长 (snout-vent length, SVL)？**（这是本 practical 的一个重要方法论点）
  - **SVL** = 从吻端到泄殖腔裂后缘的距离，即除尾之外的全身长度。**但它对动物的体位敏感**——博物馆标本保存姿势各异，**跨标本一致地测量 SVL 很困难**（即 §2.3 说的**低可重复性**）。
  - **股骨 (femur)** 是后肢的**一块单一骨头**，**不受体位影响，容易准确测量**；此外**股骨参与跳跃表现**，因而可能还告诉我们关于该动物生态或行为的信息。**代价**：单块骨头未必总能反映整只动物的大小。

### 5.2 Question 1 —— 双尾 t 检验（*B. madagascariensis*）

**目标**：*B. madagascariensis* 中雌雄的**平均股骨长是否不同**？（"是否不同" → **双尾**）

```r
# ---- 第 0 步：设置工作目录（practical 建议把这行贴到脚本最上方） ----
setwd("C:/.../你的项目文件夹")   # 这行由 RStudio 在你点 "Set As Working Directory" 时自动生成

# ---- 第 1 步：导入数据 ----
boo.mad = read.csv( "Boophis_madagascariensis.csv" )
# read.csv()  读取 csv 文件
# 文件名必须与磁盘上完全一致（大小写、下划线、扩展名）
# "="  把结果存进对象 boo.mad（名字任意，取个好记的）
# 注：这里没写 header=TRUE，因为 read.csv() 默认 header=TRUE

# ---- 第 2 步：看看数据对不对 ----
head( boo.mad, 10 )    # 显示前 10 行
# head(x, n)：只看前 n 行。对大数据集，直接打 boo.mad 会显示不下，所以 head() 更有用
# 每一行 = 一只青蛙 = 一个数据点；每一列 = 关于这只蛙的一项信息
```

**Q1.1 第一只蛙是雄是雌？** → **Male**（看第 1 行的 sex 列）
**Q1.2 第 7 只蛙的股骨多长？** → **30.37 mm**（第 7 行 femur 列）
**Q1.3（挑战）第 12 只蛙的吻肛长？** → **53.90 mm**
> 解法思路：`head(boo.mad, 12)` 看第 12 行；或直接索引 `boo.mad$svl[12]` / `boo.mad[12, "svl"]`。挑战点在于 `head(boo.mad,10)` 只给 10 行，得自己想办法拿到第 12 行。

```r
# ---- 第 3 步：取子集 + 检查正态性 ----
male.femurs = boo.mad$femur[ which( boo.mad$sex == "M" ) ]
# boo.mad$femur           用 $ 从数据框里取出 femur 这一列（得到一个向量 vector）
# boo.mad$sex == "M"      逻辑比较，逐行返回 TRUE/FALSE（务必双等号！）
# which( ... )            返回所有 TRUE 的"行号"
# [ ... ]                 索引 (indexing)：按这些行号从 femur 里挑值
# 整句 = "取出 sex 为 M 的那些行的股骨长" —— 这叫 subsetting（取子集）

hist( male.femurs,
      xlab = "male femur lengths in B. madagascariensis",  # x 轴标签
      main = "" )                                          # main 是主标题；设为空串是因为
                                                           # 图注 (caption) 会写在图下方
```

**判读（practical 原文）**：这不是完美的钟形曲线，**但数据集非常小 (n=15)，数据量不大时本来就看不出清晰的钟形**。不过中间确实有个峰，而且我们**没有任何先验理由认为这些值不服从正态分布**，所以把它们当作近似正态来处理并非不合理。

**Q1.4 画雌性股骨长的直方图** → 把 `"M"` 换成 `"F"`：
```r
female.femurs = boo.mad$femur[ which( boo.mad$sex == "F" ) ]
hist( female.femurs, xlab = "female femur lengths in B. madagascariensis", main = "" )
```
配图注："Figure 1. Femur lengths of 15 female *B. madagascariensis* sampled from museum collections in the United States."

```r
# ---- 第 4 步：t 检验（公式语法 formula syntax） ----
t.test( femur ~ sex, data = boo.mad )
# femur ~ sex   公式 (formula)。"~" 读作 "depends on"（依赖于）
#               → 问 "femur 的数据如何依赖于 sex 的数据"
# data = boo.mad  告诉 R 去 boo.mad 这个数据框里找 femur 和 sex 这两列
# 默认：双尾 (two-tailed) + Welch 校正 (Welch correction)
```
> practical 说明：这个公式语法与手册里的 `t.test(a, b)` 语法**不同但更好用**；Q2 会用回手册的语法（因为要控制哪一组是"第一组"）。

**输出（据答案反推）**：
```
	Welch Two Sample t-test

data:  femur by sex
t = 2.56, df = 18.1, p-value = 0.0198
alternative hypothesis: true difference in means between group F and group M is not equal to 0
95 percent confidence interval:
 ...
sample estimates:
mean in group F   mean in group M
          35.1              28.5
```

**输出逐栏读法**：

| 栏目 | 含义 | 本例 |
|---|---|---|
| `Welch Two Sample t-test` | R 用的是 Welch 校正的两样本 t 检验 | — |
| `data:` | 参与比较的两组 | femur by sex |
| `t` | t 统计量：均值差相当于多少个"差值标准误" | 2.56 |
| `df` | 自由度（Welch 下为小数），决定 t 分布形状 | 18.1 |
| `p-value` | 零假设为真时，偶然得到至少这么极端结果的概率 | 0.0198 < 0.05 → 显著 |
| `alternative hypothesis` | R 在检验的备择假设（这里"差值不等于 0" = 双尾） | 双尾 |
| `95 percent confidence interval` | **差值**的 95% CI；不含 0 则双尾 p < 0.05 | — |
| `sample estimates` | 两组的样本均值，**顺序与你放进函数的顺序一致**（公式语法下按分组变量的字母顺序） | F: 35.1, M: 28.5 |

**Q1.5 报告结果（答案）**：
> **"The mean femur length in females was greater than that in males (35.1 mm vs 28.5 mm; Welch's t-test, t = 2.56, df = 18.1, p = 0.0198)."**

这一句话里塞进了：**哪一性别更大 + 大多少（两个均值）+ 用了什么检验 + t + df + p**。
**注意小数位**：R 会给四五位小数，**但不要全报**——这些是基于小样本对总体值的估计，不可能精确到四五位小数；多余小数位对读者是干扰而非信息。没有绝对规则，想想读者需要什么、期刊要求什么。

**Q1.6 提供图**：starter code 给了柱状图代码（带注释，方便以后改用于其他分析），**但图注要你自己写**。

### 5.3 Question 2 —— 单尾 t 检验（*P. paradoxa*）

**为什么这次可以用单尾？**（practical 给出的完整生物学 rationale，这正是"*a priori* 知识"的范例）
- Q1 发现雌性 *B. madagascariensis* 股骨更长；事实上**许多无尾类中雌性都比雄性大**。
- 原因：**更大的雌性能产更多卵 → 繁殖率更高 → 适合度更高**；而**即使很小的雄性，产生的配子也足以给一只很大的雌性的所有卵受精**。
- 而且**多数无尾类中雄性并不为争夺雌性而打斗**，它们靠**鸣叫或鲜艳体色**做广告。所以**雄性没什么理由投资于长大，不如投资于鸣叫或鲜艳颜色**。
- ⇒ 因此我们可以在看数据之前就提出方向性假设："**雌性股骨更长**" → **单尾检验**。

**Q2.1 P. paradoxa 数据第 2 行那只蛙的股骨长？** → **27.96 mm**（`head(pse.par, 2)` 或 `pse.par$femur[2]`）
**Q2.2 该数据中体重最大的标本是雄是雌？** → **Female**
> 解法思路：`pse.par$sex[ which.max(pse.par$mass) ]`，或 `pse.par[ which(pse.par$mass == max(pse.par$mass)) , ]`。
**Q2.3（挑战）这个数据集中蛙的平均体重？** → **16.98 g**（`mean(pse.par$mass)`）
**Q2.4 雌雄的股骨长看起来在各性别内近似正态吗？** → 答案："**Yes – or, at least, they look close to me!**"（画两张直方图目视判断）

```r
# ---- 单尾 t 检验的两种写法 ----

# 写法 A：公式语法 + alternative
t.test( femur ~ sex, data = pse.par, alternative = "greater" )
# 问题：谁是"第一组"？公式语法下由分组变量的水平顺序决定（默认字母序），
# 你得先看输出才知道。practical 提示：可以看输出里哪组在前，再改命令。

# 写法 B（practical 推荐，能明确控制顺序）：手册语法
female.femurs = pse.par$femur[ which( pse.par$sex == "F" ) ]
male.femurs   = pse.par$femur[ which( pse.par$sex == "M" ) ]
t.test( female.femurs, male.femurs, alternative = "greater" )
# alternative = "greater" → 检验"第一组均值 > 第二组均值"
# alternative = "less"    → 检验"第一组均值 < 第二组均值"
# 注意：这里没有 data = 参数！因为 female.femurs / male.femurs 不是某个数据框的列，
#       它们是 R 内存里独立的对象，R 不用被告知去哪里找。
```

**Q2.5 报告结果（答案）**：
> **"The mean femur length in females was greater than that in males (27.1 mm vs 24.5 mm; one-sided Welch's t-test, t = 2.97, df = 27.9, p = 0.0030)."**

**注意措辞**：这里写的是 **"one-sided Welch's t-test"** —— **单尾检验必须在报告中声明**，否则读者会以为是双尾。

**Q2.6 提供图**（改 Q1 的图代码即可）。

### 5.4 Question 3 —— 独立完成一整套（*D. auratus*，箭毒蛙）

问题：**雌性 *D. auratus* 是否比雄性更重 (more massive)？**（响应变量换成 **mass**）

**Q3.1 单尾还是双尾？** → **One-tailed（单尾）**
> 理由：问题本身是方向性的（"是否**更重**"），且我们有 Q2 中那套 *a priori* 的生物学理由（雌性大 → 产卵多）。

**Q3.2 报告结果（答案）**：
> **"We found marginally significant evidence that female *D. auratus* were more massive than males (2.60 g vs 2.15 g; one-sided Welch's t-test, t = 1.42, df = 22.1, p = 0.0843)."**

**这句话的示范价值极高**：p = 0.0843 落在 0.05–0.10 之间，所以**不能说 "significant"，而要说 "marginally significant evidence"**——把证据强度如实标定出来。

**Q3.3 提供图**。

### 5.5 Question 4 —— Wilcoxon 检验（果蝇麻醉与交配延迟）

**研究背景**：
- **果蝇 *Drosophila melanogaster*** 是研究得最透彻的动物之一。研究活体行为时常需要**识别与追踪个体**——但研究者很难区分个体果蝇，因此常给它们**做标记**；做标记通常需要**麻醉 (anaesthetise)**：**CO₂** 或**冰上冷却 (chilling on ice)**。有人担心麻醉会影响之后的行为——若属实，实验设计与解读都必须重新斟酌。
- **Tysall, Pembury Smith & Gilman (2020)**（曼大学生 Eirlys Tysall 等，2019 年做的研究），*Animal Behaviour and Cognition* 7(4):492-504：把 3 日龄雄蝇用**冰**或 **CO₂** 麻醉 10 分钟，另设**不麻醉的对照组 (control)**。处理 3 天后，每只雄蝇与一只 6 日龄未交配雌蝇一起放进 15 ml 试管，记录**交配潜伏期 (latency to mate)**。若 2 小时仍未交配则终止试验。
- **⚠️ 数据处理上的重要设计点**：**没交配的试验绝不能丢弃**——丢掉就是丢信息。我们至少知道"这些雄蝇交配用了 **≥ 2 小时**"。所以研究者把 latency 记作 **120 分钟**。这**低估了极端值**，但**保住了信息**。

**Q4.1 在看数据之前，你预期 latency to mate 在组内服从正态分布吗？为什么？**（答案很完整，是本 practical 最有价值的概念题）
> **不服从。** 理由：
> 1. **正态分布两个方向都有长尾**。而**潜伏期不可能小于 0**，所以**左侧不可能有长尾**；
> 2. 数据在**右侧被截断在 2 小时 (truncated)**，所以**右侧也不可能有长尾**；
> 3. 因此，除非所有潜伏期都远离 0 也远离 2 小时（即没有蝇很快交配、也没有蝇失败），否则**分布不可能是正态的**。
> 4. **更一般地：等待时间 (waiting times) 倾向于右偏 (right-skewed)。** 原因：如果事件发生的概率恒定，那么**大量事件会发生在试验早期**（因为那时还有很多个体在等待），**晚期发生的事件较少**（因为多数个体已经经历过事件、不再在等待队列里了）。

然后导入 `Tysall_et_al_2019.csv`，画 ice / CO2 / control 三组的 latency 直方图，验证猜想。
→ **理论上和经验上都有理由认为组内不正态 ⇒ 不能用 t 检验 ⇒ 用 Wilcoxon**。
（再次提醒：**Wilcoxon 比较的是秩序 (rank orders) 而非均值**，它问的是不同的问题。）

```r
# ---- 对整个数据框取子集（这次不是取一列，而是取若干行） ----
an.flies = flies[ which( flies$treatment %in% c( "Ice", "CO2" ) ) , ]
# flies                     导入数据时给整个数据集起的名字（你若用别的名字要相应改）
# flies$treatment %in% c("Ice","CO2")
#                           %in% 判断每个元素是否属于给定集合，返回 TRUE/FALSE 向量
# which( ... )              返回 TRUE 的行号
# flies[ 行 , 列 ]          数据框的二维索引：逗号前选行，逗号后选列
# 逗号后留空                 → 选取所有列
# 整句 = "只保留 treatment 为 Ice 或 CO2 的那些行（丢掉 control），所有列都要"

nrow( an.flies )   # 数行数，检查有没有做对
# 应该是 231 行
```
> 对比记忆：`boo.mad$femur[ which(...) ]` 是**从一个向量里挑元素**（一维，方括号里只有一个位置）；`flies[ which(...) , ]` 是**从数据框里挑行**（二维，方括号里有逗号）。**这个逗号是新手最容易漏的。**

**Q4.2 an.flies 中第 1 只和第 3 只蝇的交配潜伏期分别是多少？** → **120 min 和 2 min**
> `head(an.flies, 3)` 或 `an.flies$latency[c(1,3)]`。
> 注意第一只是 **120 min = 被截断的"未交配"个体**，正好呼应 Q4.1 讲的截断问题。

```r
# ---- Wilcoxon 检验：语法与 t.test() 完全一样 ----
wilcox.test( latency ~ treatment, data = an.flies )
```

**Q4.3 报告结果（答案）**：
> **"We found no difference in latency to mate between flies anaesthetised with ice or CO2 (Wilcoxon rank sum test, p = 0.7974)."**

**报告要点（practical 明确说明）**：**Wilcoxon 没有自由度、也没有 t 统计量可报，而且人们很少报 W 统计量**——所以这些都可以从答案里省略。**只报：结论 + 检验名称 + p 值。**
（再次呼应 lecture：**不要在 Wilcoxon 的结论里谈"均值"**。答案写的是 "no difference in latency"，而不是 "no difference in mean latency"。）

**Q4.4 提供图**：Wilcoxon 结果怎么画图？取决于你想传达什么以及分布长什么样。**一种做法是画可对比的直方图**让读者比较。starter code 里有代码，但**需要你补全缺失的部分并加图注**。

### 5.6 讲义中的另一个 Wilcoxon 完整范例（身高数据的"应答顺序"）

Lecture Part 2 用同一份 `height_data.csv` 演示了 Wilcoxon：
- `resp` 列是**回答身高问卷的顺序**（1 = 第一个回答）。画男女的 resp 直方图 → **完全没有钟形，明显不正态**；但似乎**女性聚集在前段、男性聚集在后段**。
- 假想我们**事先**就有假设"女性回答问卷比男性快" → 单尾。

```r
mro = hd$resp[ which( hd$sex == "m" ) ]   # male response order
fro = hd$resp[ which( hd$sex == "f" ) ]   # female response order
wilcox.test( fro, mro, alternative = "less" )
# 女性数据放在第一个参数位 → alternative="less" 即检验
# "第一组(女)的位置低于第二组(男)"，因为顺序数字越小表示回答越早
```
```
	Wilcoxon rank sum test

data:  fro and mro
W = 145, p-value = 0.3027
alternative hypothesis: true location shift is less than 0
```
- 读输出：**W** = Wilcoxon 秩和统计量（**很少报告**）；**p = 0.3027 > 0.05 → 没有证据**表明女性回答更早。
- 报告：**"We found no evidence that women responded to the survey earlier than men (Wilcox rank sum test, p = 0.3027)."**
- 手册中的另一个 Wilcoxon 例：Hope College 50 名男生 + 50 名女生的**终生车祸次数**（`Hope_College.csv`）。为什么不能用 t 检验？① 各箱人数**单调递减**，不是钟形；② **车祸次数是离散变量，而正态分布是连续的**。
  ```r
  hc = read.csv("Hope_College.csv", header=TRUE)
  head(hc)
  acc.w = hc$accidents[ which(hc$gender == "w") ]
  acc.m = hc$accidents[ which(hc$gender == "m") ]
  wilcox.test(acc.w, acc.m, data = hc)
  # p = 0.12 → 没有证据表明男女的车祸次数不同
  ```
  **⚠️ 手册专门提醒**：这里用的是 `=="w"` 而不是 `=="women"`，因为**这个数据集的 gender 列是用 w / m 编码的**。**编码必须与数据文件里的实际字符完全一致**（Practical 里是 `"M"` / `"F"` 大写！）。

### 5.7 手册中完整的 R 工作流合集（Chapter 2 全部代码，附逐行注释）

```r
# ========== 导入与查看 ==========
rt = read.csv("restroom_time.csv", header = TRUE)
# read.csv()      从工作目录读 csv
# header = TRUE   告诉 R：文件第一行是各列的名称（列名），不是数据

rt                 # 打出整个数据框
rt$duration        # 只取 duration 这一列 → 得到一个"向量 (vector)"
                   # 向量 = 只有一个维度（一行或一列）的列表

# ========== 单张直方图 ==========
hist(rt$duration, breaks = 20, xlab = "visit duration in seconds")
# hist()        画直方图
# breaks = 20   把数据收进 20 个箱 (bins)，每个箱对应一根柱子
# xlab = "..."  x 轴标签

# ========== 上下两栏、共用分箱的直方图 ==========
split.screen(c(2,1))   # 把绘图区切成 2 行 1 列 → 上下两个面板
screen(1)              # 接下来的图画在第 1 个面板
b = 20*(1:22)          # (1:22) 生成向量 1,2,...,22；乘 20 → 20,40,...,440
                       # 这是"手动指定分箱边界"，目的是让两栏的箱完全一致、可比较
hist(rt$duration[which(rt$gender=="men")], breaks = b,
     main = "men", xlab = "visit duration in seconds")
# main = "..."  每个子图的标题
screen(2)              # 切到第 2 个面板
hist(rt$duration[which(rt$gender=="women")], breaks = b,
     main = "women", xlab = "visit duration in seconds")

# 索引语法拆解（手册逐条讲解的）：
#   rt$duration            → 停留时长的向量
#   rt$gender              → 记录进了哪个厕所的文本向量
#   rt$gender == "men"     → 逐元素比较，返回 TRUE/FALSE 向量（"==" 是逻辑运算符 logical）
#   which(...)             → 返回其中为 TRUE 的那些"编号"（行号）
#   [ ... ]                → 索引 (indexing)：从数据对象中挑出某些元素

# ========== 组均值 ==========
mean(rt$duration[which(rt$gender=="women")])   # [1] 133.78
mean(rt$duration[which(rt$gender=="men")])     # [1] 106.16
# 观测差值 = 133.78 - 106.16 = 27.63 s（这就是效应量 effect size）

# ========== Monte Carlo：单次置换 ==========
samp1 = sample(rt$duration, length(rt$duration), replace = F)
# sample(x, size, replace)  从 x 中随机抽取 size 个值
# length(rt$duration)       返回向量元素个数 → 抽取与原数据同样多的值
# replace = F               无放回抽样 → 每个值只被取一次
# 结果：samp1 含有与原数据完全相同的一组值，但顺序被打乱 → 这叫一次"置换 (permutation)"

mean(samp1[which(rt$gender=="men")])     # [1] 118.57
mean(samp1[which(rt$gender=="women")])   # [1] 120.02
# 本次置换的差值 = 1.45 s
# 手册作者又做了 5 次，得到 6.75, 18.07, 3.60, -8.76, 9.18 s
# → 看起来 27.63 s 这么大的差值不常见，但 6 次太少，需要 10,000 或 100,000 次

# ========== Monte Carlo：for 循环做十万次 ==========
difs = numeric()                # 创建一个空的数值向量，用来存每次置换的差值
for (i in 1:100000) {           # 把大括号里的代码重复 100,000 次
  samp = sample(rt$duration, length(rt$duration), replace = F)   # 一次置换
  mean_womens = mean(samp[which(rt$gender=="women")])            # 伪女性组均值
  mean_mens   = mean(samp[which(rt$gender=="men")])              # 伪男性组均值
  samp_dif    = mean_womens - mean_mens                          # 本次差值
  difs = c(difs, samp_dif)      # c() 把新差值拼接到 difs 末尾（每轮加一个元素）
}
# 跑完后 difs 就是 100,000 个"纯靠偶然可得的差值"

# ========== 数尾巴、算 p 值 ==========
lower_tail  = sum(difs <= -27.63)   # "<=" 也是逻辑运算符，返回 TRUE/FALSE 向量
upper_tail1 = sum(difs >=  27.63)
# sum(...)  对逻辑向量求和；R 做算术时把 TRUE 当 1、FALSE 当 0 → 于是就是"计数"
# 除以 100000 得比例：下尾 0.02734，上尾 0.02918，合计 p = 0.05652（双尾）
# 若是单尾（事先预期女性更久）：p = 0.02918

# ========== t 检验（手册语法） ==========
w.dur = rt$duration[which(rt$gender=="women")]
m.dur = rt$duration[which(rt$gender=="men")]
t.test(w.dur, m.dur)
```
```
	Welch Two Sample t-test

data:  w.dur and m.dur
t = 1.9535, df = 92.973, p-value = 0.05377
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -0.4573838 55.7088757
sample estimates:
mean of x   mean of y
 133.7826    106.1569
```
> **Monte Carlo 得 p = 0.05652，t 检验得 p = 0.05377——非常接近。** 手册评论："我们用两种方法问的是同一个问题，得到相似的答案不该让我们意外！"
> 注意 95% CI = [−0.457, 55.709] **跨过 0**，与 p > 0.05 一致。

```r
# ========== t 检验的变体 ==========
t.test(w.dur, m.dur, alternative = "greater")
# 检验"第一组（女厕）的平均停留时间大于第二组（男厕）" —— 单尾
# ⚠️ 前提：这个方向性假设必须是在看数据之前提出的！

t.test(v, mu = x)                             # 单样本 t 检验的通式
t.test(w.dur, mu = 120, alternative = "greater")
# 问"女厕的平均停留时间是否大于 120 秒" —— 单样本 + 单尾

# ========== 柱状图 + 标准误误差棒 ==========
men_mean   = mean(rt$duration[which(rt$gender=="men")])
women_mean = mean(rt$duration[which(rt$gender=="women")])

barheights = c(mens_mean, womens_mean)        # 把两个均值合成一个向量 → 柱高
lbls       = c("men's", "women's")            # 两根柱子的标签
bp = barplot(barheights, names = lbls,
             ylab = "restroom visit duration in seconds",
             ylim = c(0,160))
# barplot(高度向量, names=标签)  画柱状图
# ylab = "..."   y 轴标签（务必带单位）
# ylim = c(0,160) 指定 y 轴范围；不写的话 R 自己选，你可能不喜欢它的选择
# barplot 除了画图，还"返回"各柱子在 x 轴上的位置 → 存进 bp，画误差棒时要用

# 计算标准误
men_sd        = sd(rt$duration[which(rt$gender=="men")])       # sd()     样本标准差
men_samp_size = length(rt$duration[which(rt$gender=="men")])   # length() 样本量
men_se        = men_sd / sqrt(men_samp_size)                   # sqrt()   平方根
women_sd        = sd(rt$duration[which(rt$gender=="women")])
women_samp_size = length(rt$duration[which(rt$gender=="women")])
women_se        = women_sd / sqrt(women_samp_size)

# 手动加误差棒
segments(bp[1], men_mean - men_se,   bp[1], men_mean + men_se)
segments(bp[2], women_mean - women_se, bp[2], women_mean + women_se)
# segments(a,b,c,d) 从点 (a,b) 画一条线到点 (c,d)
# x 坐标 = bp[1] / bp[2]（第 1、2 根柱子的中心）
# y 从 均值 − SE 画到 均值 + SE
```

---

## 六、易错点 / 重点难点

### A. 概念层面

1. **p 值不是"零假设为真的概率"，也不是"结果出于偶然的概率"。** 它是"**若零假设为真**，看到至少这么极端的结果的概率"。课堂原话（品茶实验）：**"this is not the probability that Muriel Bristol guessed this by chance. She either did or didn't, we'll never know that."**
2. **低 p 值 ≠ 证明 (proof)。** 十枚硬币全正面的偶然概率 < 0.002，但它们仍**可能**是随机落成的。你有证据，没有证明。
3. **高 p 值 ≠ 支持零假设。** 高 p 值只说明"你本可能靠偶然得到这个结果"，不说明"你确实是靠偶然得到的"；**也不允许你拒绝研究假设**。六正四反的偶然概率 0.7539 → 你没理由相信有人摆过，**但你也没有证据说明没人摆过**。
4. **0.05 是纯粹的约定，没有魔力。** p 值是证据强度的**连续**度量。p ∈ [0.05, 0.10) 应报告为"弱证据 / marginally significant"（见 Practical Q3.2 的示范）。
5. **绝不能用同一批数据既生成假设、又检验它。** 否则假阳性率会从 5% 翻到 10%（手册的 IQ 论证）。**"看了直方图觉得女性更久，然后用同一数据做单尾检验"是错的。**
6. **Wilcoxon 不是"t 检验的非正态替代品"。** 二者回答**不同的问题**（均值 vs 平均秩）。**彩球反例**：红球 {1,1,...,10,10,...} 均值 5.5、白球全 2 均值 2 → 均值不同但**平均秩完全相同**。因此 Wilcoxon 结论里**绝不能提"均值"**。
7. **配对 t 检验的取样单元是"对"，不是个体。** 它本质上是对"对内差值"做的单样本 t 检验。
8. **误判取样单元是最常见的设计硬伤。** 两个湖里各抓 100 条鱼，**关于湖的样本量仍然是 2**。多抓鱼只降低每个湖的估计误差，**不增加关于湖的样本量**。
9. **对照不是必需品。** 蚊子飞行速度 10 °C vs 20 °C 就没有天然对照；观察性研究更常常没有对照。
10. **混杂因素与目标变量不独立时才最危险**（性别–体型–竞争力那个图）。第一步永远是**意识到它们可能存在**。
11. **"随机"要问的是"是否足够随机（相对于所研究的变量）"**，而不是"是否绝对随机"。*Literary Digest* 就是抽样框相对于"财富→党派倾向"这个变量完全不随机。
12. **有序数据 (ordinal) 贴上数字后仍然是类别。** 检验方法：**试着做算术**——五个 "strongly disagree" 加不出一个 "strongly agree"。
13. **Repeatability ≠ Reproducibility。** 前者是"同一测量重复做结果一致"，后者是"别人按你的方法完整重做能得到相同结果"。
14. **df 小 → t 分布肥尾 (leptokurtosis) → 同样的 t 对应更高的 p。** 这不是缺陷，而是正确地反映了我们对小样本的低信心。
15. **95% CI 不是"真值有 95% 概率落在其中"。** 正确说法见 §3.4。实用上：**CI 跨 0 ⟺ 双尾 p > 0.05**。
16. **单尾检验必须在报告中声明**（"one-sided Welch's t-test"），否则读者会默认双尾。
17. **只报 p 值不够，必须报效应量**（两组均值 / 差值）。读者需要知道差**多少**。
18. **不要丢弃"未发生事件"的数据**（果蝇 2 小时未交配的那些）——记作截断值保住信息，丢掉就是丢信息。
19. **截断 (truncated) 与有下界 (bounded at 0) 的数据一定不正态**：正态两侧都有长尾，而等待时间左端卡在 0、右端卡在上限。**等待时间普遍右偏 (right-skewed)。**
20. **离散计数数据不可能严格正态**（正态是连续的）——车祸次数就是这样。
21. **t 检验对小幅偏离正态是稳健的**：轻微不正态时仍可用，**但必须在报告中警告读者，并保守解读 p 值**（p = 0.04 只当弱证据）。
22. **小样本看不出漂亮钟形是正常的**，不能因此就断定不正态。要结合**理论理由**（有没有先验理由认为它不正态？）一起判断——这正是 Practical Q1（可以用 t 检验）与 Q4（不能用）的分野。

### B. R 操作层面

23. **`==` vs `=`：`which()` 里必须双等号。** 单等号会让 R 以为你在**赋值**——`hd$sex = "m"` 会把数据集里所有人都变成男性！
24. **语法极度敏感**：逗号、句点、引号缺失或放错，命令就跑不通。能复制粘贴就复制粘贴（Dropbox 每个 practical 文件夹里都有正确语法的代码）。
25. **拼写必须与磁盘上的文件名/数据里的编码完全一致**：`"Boophis_madagascariensis.csv"`；`=="M"` vs `=="men"` vs `=="w"` —— **不同数据集编码方式不同，一定先 `head()` 看一眼**。
26. **仅在 Files 窗格里"打开"文件夹 ≠ 设置工作目录。** 必须点**蓝色齿轮 → Set As Working Directory**（或运行 `setwd(...)`）。这是新手最常卡住的地方。机房电脑文件结构诡异时，**用 Files 面板右侧的"三个点 (…)"打开正常目录框**。
27. **R 执行赋值后不输出任何东西**——没有红色报错就是成功了。**想看内容就把对象名打进控制台**，或点右上 Environment 窗格里的对象。
28. **在脚本窗格 (script) 写代码，不要在控制台里写。** 控制台的代码用完即逝；脚本可编辑、可整块 Run、可用 `#` 注释、可保存复用。
29. **数据框取行 vs 向量取元素的方括号语法不同**：
    - 向量：`rt$duration[ which(...) ]` —— 方括号里**没有逗号**
    - 数据框：`flies[ which(...) , ]` —— 方括号里**必须有逗号**，逗号前选行、逗号后选列；**逗号后留空 = 全部列**。**漏掉这个逗号是高频错误。**
30. **两栏直方图必须手动统一分箱**（`b = 20*(1:22)` + `breaks = b`），否则两栏根本不可比。
31. **`t.test()` 的两种语法各有用处**：
    - `t.test(femur ~ sex, data = df)` —— 简洁，但**"第一组"由分组变量的水平顺序（默认字母序）决定**，做单尾时容易搞反方向。
    - `t.test(a, b, alternative = "greater")` —— **你亲自控制谁是第一组**，做单尾时更保险。**注意这种写法不需要也不能加 `data =`**，因为 a、b 是内存里的独立对象，不是某个数据框的列。
32. **`sample(x, n, replace = F)` 中 `replace = F` 是置换的关键**（无放回 → 得到原数据的一个重排）。写成 `replace = T` 就变成 bootstrap，是另一回事了。
33. **`sum()` 作用于逻辑向量就是计数**（TRUE = 1, FALSE = 0）——`sum(difs >= 27.63)` 就是"数上尾有几个"。
34. **`barplot()` 除了画图还返回柱子的 x 坐标**，必须存下来（`bp = barplot(...)`）才能用 `segments()` 在正确位置画误差棒。
35. **`ylim = c(0,160)` 要自己设**，否则 R 自选的坐标范围可能很难看/误导。
36. **不要报告 R 给的全部小数位**——小样本估计不可能精确到四五位小数，多余小数是干扰。
37. **Wilcoxon 的输出里没有 df 和 t**，且 **W 统计量通常不报**。只报结论 + 检验名 + p 值。
38. **`head(x, n)` 只给前 n 行**；要第 12 行得另想办法（直接索引 `df$col[12]` 或 `df[12, ]`）。
39. **不要试图背命令。** 老师反复强调：查手册、查 Dropbox、查网络都行。**"There is no reason to learn by memorization. You will learn what you need by using these commands when you analyse data!"**

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Science | 科学 | 把关于世界的想法与经验证据相比较的过程，不符就改想法 |
| hypothesis | 假设 | 一个我们认为**可能**为真、并打算用证据检验的陈述 |
| rationale | 理据 | 论证某假设与已有证据一致的说理 |
| manipulative study | 操控性研究 | 人为施加/withhold 处理，设处理组与对照组；有时可推因果 |
| observational study | 观察性研究 | 利用自然存在的变异，测量并分析；通常不能推因果 |
| control | 对照（组） | 不接受实验处理的研究组，作为比较基线；**并非每个实验都需要** |
| treatment | 处理 | 操控性实验中施加给研究组的因子 |
| response (variable) | 响应变量 | 我们测量的、被认为受预测变量影响的那个量 |
| predictor | 预测变量 | 可能影响响应的变量（别处也叫 independent variable / covariate / factor）|
| randomness | 随机性 | 抽样必须相对于所研究的变量"足够随机"，否则结论有偏 |
| confounding factor | 混杂因素 | 与目标因子纠缠在一起、可能搅乱结论的其他变量 |
| power | 统计功效 | 实验检测出目标效应的能力；取决于效应量、噪音、样本量 |
| effect size | 效应量 | 效应本身的大小（如两组均值之差）；报告时必须与 p 值一同给出 |
| noise | 噪音 | 数据中未被解释的变异 |
| measurement error | 测量误差 | 测量本身产生的误差；永远无法解释（知道错了就直接改了） |
| power analysis | 功效分析 | 由效应量与噪音估算所需样本量的方法；本单元不细讲 |
| repeatability | 可重复性 | 同一测量重复做（或他人按你的方案做）结果应相同 |
| reproducibility | 可复现性 | 他人按你记录的方法完整重做你的实验/分析能得到相同结果 |
| sampling unit | 取样单元 | 我们希望在其中检测到模式的那个总体的成员（可能是鱼，也可能是湖） |
| multi-level sampling | 多层抽样 | 取样单元本身的属性由其内部的子样本估计而来 |
| numerical data | 数值数据 | 可用数字表示的数据 |
| discrete data | 离散数据 | 范围内只能取某些值（常为整数），如巢中蛋数 |
| continuous data | 连续数据 | 范围内可取任意值，如体重 |
| categorical data | 分类数据 | 由名称/类别构成的数据，如物种名 |
| dichotomous data | 二分数据 | 只有两个类别的分类数据，如雌/雄、死/活 |
| ordinal data | 有序数据 | 类别可逻辑排序但不是数字，如 Likert 量表 |
| Likert scale | 李克特量表 | 典型五级态度量表（强烈不同意…强烈同意），属有序数据 |
| quadrat sampling | 样方取样 | 用固定尺寸方框（或圆/三角）圈定区域采样 |
| transect sampling | 样线取样 | 沿设定的直线（或线两侧一定距离内）采样 |
| scan sampling | 扫描取样 | 在固定时刻记录每只动物在做什么；可估时间预算，但不给行为顺序 |
| focal follow | 焦点跟踪 | 盯住一只动物，记录其固定时段内的全部行为与顺序 |
| frequentist hypothesis testing | 频率学派假设检验 | 通过"偶然能否产生这么极端的结果"来衡量证据的一整套方法 |
| null hypothesis ($H_0$) | 零假设 | "没有差异 / 一切只是偶然"的陈述 |
| research hypothesis | 研究假设 | 我们真正想找证据支持的陈述 |
| p-value | p 值 | 零假设为真时，仅凭偶然得到至少同样极端结果的概率 |
| statistical significance | 统计显著性 | 约定 p < 0.05 为显著；0.05–0.10 为弱显著；纯属惯例 |
| *a priori* | 先验（事先） | 在看数据之前就具备的知识/预期；是使用单尾检验的前提 |
| one-tailed test | 单尾检验 | 检验方向性假设（A > B），p 值只取一条尾巴 |
| two-tailed test | 双尾检验 | 检验"是否不同"，p 值为两条尾巴之和；R 的默认 |
| Monte Carlo method | 蒙特卡洛方法 | 靠随机重排数据生成"偶然可得结果"的分布，据以算 p 值 |
| permutation | 置换 | 保持组大小不变、把响应值随机重排一次所得的数据版本 |
| data point | 数据点 | 数据表中的一行 = 一个观测 |
| header | 表头 | 数据文件第一行的列名；`read.csv(..., header=TRUE)` |
| data frame | 数据框 | R 中的表格型数据对象 |
| vector | 向量 | 只有一个维度（一行或一列）的列表 |
| indexing | 索引 | 用 `[...]` 从数据对象中挑出某些元素 |
| subsetting | 取子集 | 用 `which()` + 索引挑出满足条件的那部分数据 |
| logical | 逻辑（运算符/值） | `==`、`<=`、`>=` 等返回 TRUE/FALSE；算术中 TRUE=1、FALSE=0 |
| for loop | for 循环 | `for (i in 1:n) { ... }`，把大括号里的代码重复 n 次 |
| working directory | 工作目录 | R 默认查找/保存文件的文件夹；用 `setwd()` 或蓝色齿轮设置 |
| script(ing window) | 脚本（窗格） | 编写、编辑、保存、复用 R 代码的文档窗口 |
| console | 控制台 | 直接执行 R 命令的窗口，本质是个高级计算器 |
| t-distribution | t 分布 | Gosset 发现的、可由方差与样本量算出的"偶然差值"分布 |
| t-test | t 检验 | 基于 t 分布比较均值的检验 |
| Student | 学生氏 | W. S. Gosset 的笔名（Guinness 禁止员工署名发表） |
| two-sample t-test | 两样本 t 检验 | 问两个总体的均值是否不同 |
| one-sample t-test | 单样本 t 检验 | 问一个总体的均值是否不同于某个关注值；`t.test(v, mu=x)` |
| paired t-test | 配对 t 检验 | 取样单元是"对"、响应是对内差值的单样本 t 检验特例 |
| Welch's correction / Welch's t-test | Welch 校正 / Welch t 检验 | Student t 检验的修正版，允许两组方差不等；R 的默认 |
| t-statistic | t 统计量 | 观测差值相对于差值标准误的倍数；越大 p 越小 |
| degrees of freedom (df) | 自由度 | 决定 t 分布形状；df 小则肥尾、p 更高；Welch 下常为小数 |
| leptokurtosis | 尖峰厚尾 / 轻峰态 | 小 df 时 t 分布的"肥尾"特性，包含更多极端值 |
| standard deviation (SD) | 标准差 | 度量数据本身的离散程度；`sd()` |
| standard error (SE) | 标准误 | $s/\sqrt{n}$，度量样本均值接近总体均值的把握；误差棒常用它 |
| 95% confidence interval | 95% 置信区间 | 同样大小的新样本中，观测差值有 95% 机会落入的区间；**不是**"真值有 95% 概率在内" |
| normality assumption | 正态性假设 | t 检验要求响应变量在**每一组内**近似正态 |
| histogram | 直方图 | 检查分布形状与正态性的主力图 |
| bins / breaks | 分箱 / 断点 | 直方图的分组区间；比较两组时必须统一 |
| bar chart | 柱状图 | 展示两组均值 + 误差棒，报告 t 检验最直观的图 |
| error bars | 误差棒 | 通常画 ±1 SE，让读者感受两组差异的可靠程度 |
| figure legend / caption | 图注 | 必须让读者不看正文也能看懂这张图 |
| Wilcoxon test | Wilcoxon 检验 | 比较两组**平均秩**的检验；对任意分布都可用 |
| Wilcoxon rank sum test | Wilcoxon 秩和检验 | 两独立组版本的 Wilcoxon；输出 W 统计量（通常不报） |
| Mann-Whitney U test | Mann-Whitney U 检验 | Wilcoxon 检验的一个特例 |
| rank | 秩 | 按响应值排序后的位次；相同值给相同秩 |
| mean rank | 平均秩 | Wilcoxon 比较的对象，**不是均值** |
| robust | 稳健 | t 检验对小幅偏离正态仍大致可靠 |
| right-skewed | 右偏 | 长尾在右侧的分布；等待时间数据的典型形态 |
| truncated data | 截断数据 | 超过上限被记为上限值的数据（如 2 小时未交配记 120 min） |
| sexual dimorphism | 性二型 | 同种内雌雄在大小、形状、行为上的差异 |
| snout-vent length (SVL) | 吻肛长 | 吻端到泄殖腔裂后缘的长度；对体位敏感、跨标本难以一致测量 |
| femur | 股骨 | 后肢单一骨头，不受体位影响、易准确测量，且与跳跃表现相关 |
| latency to mate | 交配潜伏期 | 从配对到发生交配的等待时间 |
| `read.csv()` | — | 从工作目录读取 csv 文件为数据框；`header=TRUE` 指明首行为列名 |
| `head()` | — | 显示数据框前几行；`head(df, 10)` 显示前 10 行 |
| `which()` | — | 返回逻辑向量中为 TRUE 的元素编号（行号） |
| `%in%` | — | 判断元素是否属于给定集合，返回 TRUE/FALSE |
| `nrow()` | — | 返回数据框的行数 |
| `mean()` / `sd()` / `length()` / `sqrt()` | — | 均值 / 样本标准差 / 元素个数 / 平方根 |
| `sample(x, n, replace=F)` | — | 从 x 无放回随机抽 n 个 → 生成一次置换 |
| `hist()` | — | 画直方图；`breaks=` 指定分箱，`xlab=`/`main=` 设标签与标题 |
| `barplot()` | — | 画柱状图；返回各柱的 x 坐标，供 `segments()` 画误差棒用 |
| `segments(a,b,c,d)` | — | 从点 (a,b) 到点 (c,d) 画一条线段 |
| `split.screen()` / `screen()` | — | 把绘图区切成多个面板 / 切换到指定面板 |
| `t.test()` | — | t 检验；`y ~ group, data=` 或 `(a, b)`；`alternative=`、`mu=` |
| `wilcox.test()` | — | Wilcoxon 检验；语法与 `t.test()` 相同 |
| `setwd()` | — | 设置工作目录；由 RStudio 的 "Set As Working Directory" 自动生成 |
| `#` | — | R 的注释符号，`#` 之后的内容不被执行 |
| `~` (tilde) | 波浪号 | R 公式语法中读作 "depends on"（依赖于） |
| `$` | — | 从数据框中取出某一列，如 `boo.mad$femur` |
