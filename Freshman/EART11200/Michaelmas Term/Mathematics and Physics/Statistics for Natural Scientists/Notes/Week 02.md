# Week 2 — 比较多组均值：方差分析 (ANOVA) 与事后 Tukey 检验

> 课程：EART11200 The Natural Scientist's Toolkit — Statistics for Natural Scientists（Tucker Gilman）
> 材料来源：Asynchronous Lecture 2 Part 1/2/3 slides + 15-Nov 现场答疑课转写 + Practical 3（含 answer key）+ 手册 Chapter 3 "Comparing the means of more than two groups"
> 物理目录：`Lecture/Week 7` + `Practical/Week 2` = 本课程内部 **Week 02**

---

## 一、本周主题

本周把上周「两组均值比较」（t 检验 / Wilcoxon 检验）推广到 **两组以上**。核心工具是 R. A. Fisher 发明的 **方差分析 (Analysis of Variance, ANOVA)**：把数据的总变异拆成「组间（被分组解释的）变异」和「组内（未被解释的）变异」，用两者的比值构造 F 统计量，从而只做**一次**检验就回答「这些组的均值是否全都一样」。ANOVA 显著之后，再用**事后检验 (post hoc test)**——Tukey HSD——去回答「到底是哪两组不同、差多少」。最后把方法推广到**双因素方差分析 (two-way ANOVA)**：加入第二个预测变量既能「解释掉」噪声、提高检验力 (power)，也能检验**交互作用 (interaction)**。

**在全课 6 周中的位置**（主线＝「预测变量类型 × 响应变量类型」的组合）：

| 周 | 预测变量 | 响应变量 | 方法 |
|---|---|---|---|
| Week 01 | 分类（2 组） | 数值 | t 检验 / Wilcoxon 检验 / Monte Carlo |
| **Week 02（本周）** | **分类（≥2 组，可多个因子）** | **数值** | **ANOVA、Tukey HSD、Kruskal-Wallis、two-way ANOVA** |
| Week 03 | 数值 | 数值 | 线性回归 |
| Week 04 | 分类 | 分类 | 卡方检验 |
| Week 05 | 数值 | 分类（二元） | 逻辑回归 |
| Week 06 | 含非独立结构 | — | 混合效应模型 |

一句话记忆：**t 检验是 ANOVA 在 k = 2 时的特例**；ANOVA 是「一个分类预测变量 + 一个数值响应变量」的通用解法。

---

## 二、核心概念

### 2.1 为什么不能两两做 t 检验——多重检验问题 (multiple testing)

**问题设定**：有 A、B、C 三个基因型的花，想知道哪一种吸引的蜜蜂最多。朴素做法是做 3 次两两 t 检验：A vs B、B vs C、A vs C。

**为什么错**：p 值的定义是「若原假设为真，观察到与现有数据一样极端或更极端结果的概率」。若把显著性阈值定为 $\alpha = 0.05$，那么**即使组间真的完全没有差异**，单次比较也有 5% 的概率被我们误判为「有差异」。这就是：

- **第一类错误 (Type I error)** = 假阳性 (false positive) = 「本无效应，却宣称有效应」
- **假阳性率 (false positive rate)** = $\alpha$，惯例取 0.05

关键在于：**每多加一组，就多了若干次比较机会，至少犯一次错的概率就上升**。k 组时两两比较的次数是

$$m = \binom{k}{2} = \frac{k(k-1)}{2}$$

- k = 3 → m = 3
- k = 4 → m = 6（讲义中亚洲象 4 个亚种的例子）
- k = 6 → m = 15（手册 chickwts 六种饲料）

若各次检验相互独立，**族系错误率 (family-wise error rate, FWER)**——即「至少犯一次第一类错误」的概率——为

$$\alpha_{FW} = 1 - (1-\alpha)^m$$

代入：k = 4 时 $1-0.95^6 = 0.265$；k = 6 时 $1-0.95^{15} = 0.537$——**六组之间两两比较，即使真实上完全没有差异，超过一半的研究会至少报出一个「显著」结果**。

> ⚠️ 严谨性提醒：上式假定各次比较独立，而两两比较之间共用样本、并不独立，所以这只是一个直观上界式的估计。但结论方向完全正确：**比较次数越多，假阳性越不可控**。手册原话：如果有 100 个基因型，「我们几乎必定会发现至少一对基因型显著不同，哪怕它们真的一模一样」。老师在 slides 里的说法更直接：**"if we make pairwise comparisons and we make enough of them, we are certain to make a mistake."**

**ANOVA 的解决方式**：不做 m 次检验，而是把所有组的解释力**加总成一个统计量**，只得到**一个 p 值**，这个 p 值回答的是「若这 k 组是随机划分出来的，它们能解释到至少这么多变异的概率是多少」。一次检验，$\alpha$ 就还是 0.05。

### 2.2 ANOVA 的核心思想：变异的分解 (partitioning variability)

用 Lecture Part 1 里 5 男 5 女身高的简化例子来理解，共三层：

**第 1 层：只知道总均值（grand mean）**
如果对某个人一无所知，猜他的身高，最好的猜测就是**总均值 (grand mean)** $\bar y$。每个人真实身高与总均值之差叫**离差 (deviance / deviation)**。这些离差就是「完全未被解释的变异」。

**第 2 层：知道他属于哪一组（treatment effect）**
知道性别后，可以给每组算一个**组均值 (group / treatment mean)** $\bar y_i$。**组均值与总均值之差 $(\bar y_i - \bar y)$ 就是「属于这一组」带来的效应**，叫**处理效应 (treatment effect)**。这是**被分组解释掉的那部分变异**。
（老师注：即使这里的「组」是性别、不是人为施加的处理，习惯上也叫 treatment effect。）

**第 3 层：剩下的仍然解释不了（error）**
每个数据点与**它自己那组的组均值**之差 $(y_{ij} - \bar y_i)$，是既不能用总均值也不能用分组解释的部分，叫**误差 (error)**。
> ⚠️ 老师和手册都强调：这里的 "error" **不是研究者犯错**的意思，而是「用处理去预测个体响应时的预测误差」。

**用平方和汇总**：每个点都有自己的离差，要用**一个数**概括整体变异，就取 **平方和 (sum of squares, SS)**——把每个离差平方后加总。平方的作用是消去正负号（正负离差本会相消为 0）并放大大偏差的权重。

Lecture Part 1 身高例子的数值：$SS_{tot} = 235.56$，$SS_{treat} = 155.99$，$SS_{err} = 79.57$，且 $155.99 + 79.57 = 235.56$。

**核心比值**：

$$\frac{SS_{treat}}{SS_{err}} = \frac{155.99}{79.57} = 1.96$$

「组解释掉的变异 ÷ 仍未解释的变异」，**这个比值越大，分组这个解释就越好**。

**怎么得到 p 值**（Part 1 的 Monte Carlo 演示）：把观测到的身高**随机重新分配**到两个「伪组」里，重算 $SS_{treat}/SS_{err}$，得到 0.09；再来一次，0.57；再来，0.04……重复几千次，得到「纯靠运气能达到的比值」的分布，再看观测值 1.96 落在这个分布的什么位置——右尾面积就是 p 值。**这和上周 t 检验/Monte Carlo 的逻辑完全一样**，因为问的是同一个问题：随机划分出来的组，均值差异有多大可能达到观测水平。

> 关键结论（Part 1 结尾）：**两组时，ANOVA 和 t 检验给出完全相同的答案**，因为它们问的是同一个问题。ANOVA 的价值不在两组，而在**三组及以上**。

### 2.3 组间变异大 vs 组内变异小——直觉图（手册 Figure 3.1）

手册用一组图说明：左右两列三个样本的**均值完全相同**（16.0、17.9、15.3），但左列源分布 SD = 4.0，右列 SD = 0.5。

- 左列：组内变异大，三个样本看起来完全可能来自同一分布 → p = 0.70
- 右列：组内变异小（中间那组的每一个观测值都大于最下面那组的每一个观测值）→ p = 7.52 × 10⁻¹⁶

**结论**：判断组均值是否真的不同，**不能只看均值差多少，必须相对于组内变异来看**。同样大的均值差，在噪声小的时候是铁证，在噪声大的时候什么也说明不了。这就是 ANOVA 的全部精神。

### 2.4 F 统计量与 F 分布

$SS_{treat}/SS_{err}$ 这个原始比值的分布依赖于组数和样本量，不好查表。**做适当缩放（各自除以自由度）之后**，若原假设为真，这个比值服从已被充分研究的 **F 分布 (F-distribution)**。缩放后的量叫 **F 统计量 (F-statistic)**。公式与自由度见第三节。

### 2.5 omnibus 检验与事后检验 (post hoc test)

**ANOVA 是一个 omnibus test（总括检验 / 全局检验）**：它告诉你「这些组的均值不全相同」，但**不告诉你是哪几组不同**。而我们通常真正关心的是后者。

此时又想做两两比较——但直接退回两两 t 检验，多重检验问题就又回来了。解决方案是 **Tukey 的诚实显著差异检验 (Tukey's Honest Significant Difference test, Tukey HSD)**，即 **post hoc Tukey test**（由 John Tukey 提出，后由 Clyde Kramer 推广至不等样本量，故有时称 Tukey–Kramer）。它做**所有**两两比较，但**内部已经对多重比较做了校正**，输出的是「校正后的 p 值」`p adj`，并给出 **95% family-wise confidence level** 的置信区间——即整族比较合起来的置信水平是 95%，而不是每一条各自 95%。

> 📌 Practical 中的重要纪律：**只有当 ANOVA 显示存在差异时，才去做 Tukey 检验**。原话：*"we would not do a Tukey test if our ANOVA had not indicated that there were differences among the species. If we had no evidence that differences exist, then there would be no reason to ask how big they are."*
>
> （补充知识，非本课要求：Tukey HSD 的原理是用 studentized range 分布而非 t 分布；另一类常见校正是 Bonferroni 校正，把 $\alpha$ 除以比较次数，比 Tukey 更保守。）

### 2.6 双因素方差分析 (two-way ANOVA)

**动机（Lecture Part 3 开篇）**：ANOVA 靠「解释的变异 / 未解释的变异」判断效应，所以**未解释的变异是敌人**——它会淹没我们想看的效应。降低它有两条路：

1. **控制它**：做严格受控实验（chickwts 里所有小鸡养在同一温度下，因为低温会让小鸡把能量用于保暖而非生长）。但**野外工作做不到**。
2. **解释它**：把可能影响响应变量的其他因子**放进模型**。老师的原话逻辑非常漂亮：**"if we can explain variability, then it is no longer unexplained."**

**大象例子**：一元 ANOVA 只有「亚种」一个预测变量。但哺乳动物体型的一大变异来源是**性别**。把性别加进模型后，每个亚种不再只有一个均值，而是**雄性一个、雌性一个**；误差是每点到**它所属的「亚种×性别」格子均值**的距离，明显变小了。于是检验力上升。

对比数据：

| 模型 | subspec 的 F | subspec 的 p | Residuals Df | Residual SS |
|---|---|---|---|---|
| `mass~subspec`（一元） | 5.138 | 0.00464 | 36 | 8,231,967 |
| `mass~sex+subspec`（二元） | 11.82 | 1.68e-05 | 35 | 3,490,959 |

残差平方和从 823 万降到 349 万（差额被 sex 那一行的 4,727,088 吸收），F 值翻倍以上，p 值小了两个数量级。Tukey 结果也随之更灵敏：一元 ANOVA 只发现 Bornean > Indian、Sri Lankan > Indian；二元 ANOVA **多发现了 Sumatran > Indian (p = 0.0056)**。

**交互作用 (interaction)**：`species*sex` 这一项问的是「**一个预测变量的效应是否依赖于另一个预测变量的取值**」。例如「在某个物种里雌性远大于雄性，在另一个物种里只大一点点」——这就是交互作用。Practical 表述：*"The interaction [tells us] whether the effect of sex is different for each Hyla species."* R 语法上 `a*b` 通常展开为 `a + b + a:b`，本课材料里写成 `helmet+vehicle+helmet*vehicle` 或 `species + sex + species*sex`，即把主效应显式写出、再加交互项；输出中交互项那一行标为 `helmet:vehicle` / `species:sex`。

**主效应 (main effect)**：单个预测变量自身的效应（不含交互）。

### 2.7 ⭐ two-way ANOVA 中「预测变量的顺序至关重要」

这是本周**最容易考、也最容易搞错**的点。

**现象**：同样的数据、同样的两个预测变量，只是在公式里换个先后顺序，Sum Sq 和 p 值都会变。手册 bike_pass 例子：

```
ba1 = aov(pass ~ helmet + vehicle, data=bike)
  helmet    Df 1  Sum Sq 4.3  F 29.878  p 5.09e-08
  vehicle   Df 6  Sum Sq 6.9  F  8.102  p 1.10e-08

ba2 = aov(pass ~ vehicle + helmet, data=bike)
  vehicle   Df 6  Sum Sq 7.1  F  8.269  p 7.00e-09
  helmet    Df 1  Sum Sq 4.1  F 28.880  p 8.46e-08
```

**原因**：`aov()` 用的是**序贯平方和 (sequential / Type I sums of squares)**。R 按公式中出现的顺序依次把变异「分给」各项：第一项拿到它能解释的全部变异；第二项**只能拿到第一项解释之后剩下的**。所以：

> **每一项都是在「控制了它左边所有项」的前提下被检验的。**

**规则**：**把你真正关心的预测变量放在最后**（交互项永远放最右——因为讨论交互作用而不控制主效应几乎没有意义）。

**Lecture Part 3 给出的直观反例**（务必记住）：想象两个虚构的大象亚种，两者**真实上完全相同**（雄性平均质量相同，雌性平均质量相同）。但抽样时，亚种 1 抽到的雄性多，亚种 2 抽到的雌性多。

- **先放 subspec**：先按亚种求均值 → 亚种 1 的均值被雄性拉高、亚种 2 被雌性拉低 → **错误地推断亚种之间有差异**。之后再放 sex，仍然会发现性别效应（因为各亚种内部雄性高于该亚种均值、雌性低于），这个推断是对的，但**亚种的推断是假的**。
- **先放 sex**：先发现性别效应；然后在**同一性别内部**比较两个亚种，发现均值相同 → **正确地推断亚种无效应**。

这正是老师在讲二元 ANOVA 结果时**刻意跳过 sex 那一行不解释**的原因——在 `mass~sex+subspec` 里，sex 是第一项，它没有被 subspec 控制，所以它的 p 值不能直接拿来下结论。要研究 sex，必须重新跑 `mass~subspec+sex`。

**Practical 的严谨表述**：在 `femur ~ species + sex + species*sex` 中，我们问的是「**同一物种内部**，知道性别能否帮我们猜出股骨相对长度」（sex 被 species 控制）；而 species 那一行问的是「**不区分性别地**，各物种整体是否不同」（species 没有被 sex 控制）。这两个问法含义完全不同。

**同一 aov 对象跑 Tukey 的推论**：因为 `TukeyHSD()` 依附于某个 `aov` 模型，**想看哪个预测变量的两两差异，就必须去看「把该变量放在最后」的那个模型**。手册 bike 例子：想看 vehicle 的效应（控制 helmet）→ 看 `ba1`；想看 helmet 的效应（控制 vehicle）→ 看 `ba2`。**这三个结论（helmet 效应、vehicle 效应、无交互作用）来自三个不同的模型！**

### 2.8 模型里该保留哪些项？

Practical 与手册给出的两条不同倾向，需要一起理解：

- **手册的倾向**：如果某个预测变量没有证据影响响应变量（如 bike 数据里 `helmet:vehicle` 的 p = 0.802），**通常把它从模型中删掉**。
- **Practical 的更细致说法**：「拇指规则说删掉不显著的项，但这不总是对的。」如果**先验知识**告诉我们某个因子确实有影响（例如已知很多无尾类的股骨长度确实存在性别差异），那么即使本次数据没测出显著性，**仍可以把它留在模型里以控制其变异**——这叫 **"forcing" a predictor into the model（强制保留预测变量）**。老师原话：*"There is no clear right answer here, and happily that means there is also no clear wrong one."*
- **老师本人在 Hyla 数据上的选择**：删掉交互项（无证据），但**保留 sex 与 species 互相控制**——研究 species 时用 `femur ~ sex + species`，研究 sex 时用 `femur ~ species + sex`。
- **另一类「不感兴趣但要控制」的变量**（手册结尾）：假设 bike 数据的通过距离由 4 位观察者测量，有人系统高估、有人低估，这会平白增加未解释变异、掩盖真正的结果。把 observer 作为预测变量放进模型就能解释掉这部分变异。**这种变量应放在最前面**——因为我们只想控制它，并不想对它做推断。

### 2.9 前提假设、如何检验、假设不成立怎么办

Fisher 的 ANOVA 有两条关键假设：

#### 假设 1：各处理组内部的误差服从正态分布 (normality of within-group error)

**注意措辞**：不是「整个响应变量服从正态分布」，而是「**每一组内部**，观测值围绕**该组均值**呈正态分布」。手册 Figure 3.4 特意画了一个三峰的直方图（红绿蓝三组各一峰），整体明显非正态，**但每组内部正态，所以完全满足假设**。

- **如何检验**：画各组的直方图（`hist()`）目视判断；也可结合理论推理（见第四节转写里老师的示范）。
- **替代方法**：**Kruskal-Wallis 检验 (Kruskal-Wallis test)**。它像上周的 Wilcoxon 检验一样，**用响应值的秩 (rank) 代替原始值**，从而绕开正态性假设。⚠️ 代价是：**它检验的不是均值是否不同，而是平均秩 (mean ranks) 是否不同**——问的是另一个问题。
- **对应的事后检验**：**Dunn's test**（由统计学家 Olive Jean Dunn 提出）。R 基础包没有，需从 CRAN 安装 `dunn.test` 包。
- **实务建议（重要）**：除非响应数据本身是**有序尺度 (ordinal，如 Likert 量表)**，研究者通常更关心均值而非平均秩；而且 **ANOVA 对正态性偏离相当稳健 (robust)**。所以很多人即便误差非正态也照样用 ANOVA——但**必须在文中报告误差非正态，并保守地解读 p 值**。手册给了具体尺度：非正态时，p = 0.05 只能算**弱证据**；p = 0.001 仍然是**强证据**。

#### 假设 2：各处理组内的变异相等（方差齐性, equal variance / homoscedasticity）

- **如何检验**：用 `aggregate()` 逐组算方差；或看箱线图 / 误差条是否宽窄悬殊（Practical Q3.5 就是让你从图上看出来的）。
- **容忍度（拇指规则）**：**只有当某些组的方差超过其他组约 4 倍时才需要担心**。chickwts 各组方差 1491.96 ~ 4212.09，最大/最小 ≈ 2.8 < 4，可以接受。
- **替代方法**：**Welch 校正 (Welch's correction)**，在 R 中用 `oneway.test()`，即「不假定方差相等的单因素均值分析」。因为太容易做了，很多研究者**只要怀疑方差不齐就直接用它**。
- **方差不齐时的事后检验**：Tukey HSD 在方差不齐时也不完全准确，应改用 **Games-Howell 检验**，实现在 R 包 `rstatix` 中。
- **另一条路（Practical Q3.6 的答案）**：**对响应变量取对数** (`log(femur)`)。当方差随均值增大而增大时，取对数常能同时改善方差齐性和正态性。

#### 隐含假设 3：观测独立

材料中未展开，但这是 Week 06 混合效应模型要处理的问题——先记一笔。

---

## 三、公式与图表

### 3.1 符号约定

| 符号 | 含义 |
|---|---|
| $k$ | 组数（处理水平数） |
| $n$ | 总观测数 |
| $n_i$ | 第 $i$ 组的观测数 |
| $y_{ij}$ | 第 $i$ 组的第 $j$ 个观测值 |
| $\bar y$ | 总均值 (grand mean) |
| $\bar y_i$ | 第 $i$ 组的组均值 (treatment mean) |

### 3.2 三个平方和

**总平方和 (total sum of squares)** —— 数据中的全部变异：

$$SS_{tot} = \sum_{i=1}^{k}\sum_{j=1}^{n_i}\left(y_{ij}-\bar y\right)^2$$

**处理平方和 / 组间平方和 (treatment / between-group sum of squares)** —— 被分组解释的变异：

$$SS_{treat} = \sum_{i=1}^{k}\sum_{j=1}^{n_i}\left(\bar y_i-\bar y\right)^2 = \sum_{i=1}^{k} n_i\left(\bar y_i-\bar y\right)^2$$

（注意里层对 $j$ 求和的项与 $j$ 无关，所以等价于「每组的 $n_i$ 乘以组均值离差的平方」。手册的 R 实现是先把组均值**广播到每个个体**上再逐点平方求和，两种写法等价。）

**误差平方和 / 组内平方和 (error / within-group sum of squares)** —— 未被解释的变异：

$$SS_{err} = \sum_{i=1}^{k}\sum_{j=1}^{n_i}\left(y_{ij}-\bar y_i\right)^2$$

### 3.3 ⭐ 平方和分解定理（推导）

$$\boxed{SS_{tot} = SS_{treat} + SS_{err}}$$

**推导**：把每个观测值的总离差拆成两段（加一项减一项）：

$$y_{ij}-\bar y = \underbrace{(\bar y_i - \bar y)}_{\text{处理效应}} + \underbrace{(y_{ij} - \bar y_i)}_{\text{误差}}$$

两边平方并对所有 $i, j$ 求和：

$$\sum_i\sum_j (y_{ij}-\bar y)^2 = \sum_i\sum_j (\bar y_i-\bar y)^2 + \sum_i\sum_j (y_{ij}-\bar y_i)^2 + 2\sum_i\sum_j (\bar y_i-\bar y)(y_{ij}-\bar y_i)$$

看**交叉项**：对固定的 $i$，$(\bar y_i-\bar y)$ 是常数可以提到外面：

$$2\sum_i (\bar y_i-\bar y)\sum_j (y_{ij}-\bar y_i) = 2\sum_i (\bar y_i-\bar y)\cdot 0 = 0$$

因为**任何一组内部，各观测值对该组均值的离差之和恒为 0**（这正是均值的定义性质）。交叉项消失，于是三项平方和的分解成立。∎

**验证**（Lecture Part 1 身高数据）：155.99 + 79.57 = 235.56 ✓
**验证**（手册 chickwts）：231129.2 + 195556 = 426685.2 ✓

### 3.4 均方与 F 统计量

把平方和除以各自的**自由度 (degrees of freedom, Df)**，得到**均方 (Mean Square, MS)**——本质上就是「平均每个自由度承担的变异」，即方差的估计：

$$MS_{treat} = \frac{SS_{treat}}{k-1}, \qquad MS_{err} = \frac{SS_{err}}{n-k}$$

**F 统计量**：

$$F = \frac{MS_{treat}}{MS_{err}} = \frac{SS_{treat}/(k-1)}{SS_{err}/(n-k)} = \frac{SS_{treat}}{SS_{err}}\cdot\frac{n-k}{k-1}$$

若原假设「所有组均值相等」为真，则 $F \sim F_{k-1,\; n-k}$（自由度为 $k-1$ 和 $n-k$ 的 F 分布）。p 值 = 该分布中 $\ge$ 观测 F 值的右尾概率，即 R 输出中的 `Pr(>F)`。

**自由度的直觉**：
- 组间自由度 $k-1$：k 个组均值，一旦知道总均值，只有 k−1 个可以自由变动。
- 组内自由度 $n-k$：每组内部 $n_i$ 个点，扣掉该组自己估计出来的一个均值，剩 $n_i - 1$；对 k 组求和得 $n-k$。

**用 chickwts 验算**：$k=6$，$n=71$。
$MS_{treat} = 231129.2/5 = 46225.8$；$MS_{err} = 195556/65 = 3008.6$；$F = 46225.8/3008.6 = 15.37$ ✓ 与 R 输出一致。

> ⚠️ **手册勘误（重要）**：手册第 37 页脚注写「乘以 $(k-1)/(n-k+1)$，得到自由度为 $k-1$ 和 $n-k+1$ 的 F 统计量」。这有两处笔误：(1) 缩放因子应是 $(n-k)/(k-1)$（分子分母写反了）；(2) 分母自由度应是 $n-k$ 而非 $n-k+1$。用手册自己给出的 chickwts 输出即可验证：Residuals 的 Df = 65 = 71 − 6 = $n-k$，若按脚注应为 66。**考试与作业以 $F_{k-1,\,n-k}$ 为准。**

### 3.5 单因素 ANOVA 表的结构与逐栏判读

```
             Df  Sum Sq  Mean Sq  F value    Pr(>F)
feed          5  231129    46226    15.37  5.94e-10 ***
Residuals    65  195556     3009
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```

| 栏 | 含义 | 怎么读 |
|---|---|---|
| **行名 `feed`** | 处理/预测变量那一行 | 组间部分 |
| **行名 `Residuals`** | 残差行 | 组内部分，即「误差」 |
| `Df` | 自由度 | 处理行 = $k-1$（这里 5 → 6 种饲料）；残差行 = $n-k$（65 → n = 71） |
| `Sum Sq` | 平方和 | 处理行 = $SS_{treat}$；残差行 = $SS_{err}$。两者相加 = $SS_{tot}$ |
| `Mean Sq` | 均方 = Sum Sq / Df | 46226 = 231129/5；3009 = 195556/65 |
| `F value` | F 统计量 = 处理均方 / 残差均方 | 15.37 = 46226/3009。**只有处理行有 F 值** |
| `Pr(>F)` | p 值 | 「若分组毫无效应，纯靠运气得到这么大 F 的概率」。5.94e-10 极小 → 强证据 |
| `***` 等 | 显著性星号 | `***` p<0.001、`**` p<0.01、`*` p<0.05、`.` p<0.1、空格 p<1 |

**从表里能反推出样本量**：$n = \text{Df}_{treat} + \text{Df}_{resid} + 1 = 5 + 65 + 1 = 71$；$k = \text{Df}_{treat}+1 = 6$。

### 3.6 双因素 ANOVA 表的判读

```
                 Df  Sum Sq  Mean Sq  F value   Pr(>F)
helmet            1     4.3    4.264   29.841  5.19e-08 ***
vehicle           6     6.9    1.156    8.092  1.13e-08 ***
helmet:vehicle    6     0.4    0.073    0.509     0.802
Residuals      2341   334.5    0.143
```

- 每个预测变量各占一行，**交互项写成 `helmet:vehicle`**。
- 各项的 F 值都是「该项均方 ÷ 残差均方」，例如 $4.264/0.143 = 29.8$；$0.073/0.143 = 0.51$。
- **交互项自由度 = 两个主效应自由度之积**：$1 \times 6 = 6$。
- helmet 是二水平因子 → Df = 1；vehicle 有 7 种车型 → Df = 6。
- 残差 Df = $n - 1 - \sum \text{Df}_{\text{各项}} = 2355 - 1 - 1 - 6 - 6 = 2341$。
- **判读顺序**：先看交互项。这里 p = 0.802 → **没有交互作用的证据** → 可以删掉交互项，然后干净地解释主效应。若交互显著，则**主效应不能单独解释**（因为一个因子的效应依赖于另一个因子的水平）。

### 3.7 Tukey HSD 输出的判读

```
Tukey multiple comparisons of means
  95% family-wise confidence level
Fit: aov(formula = mass ~ subspec, data = elephants)

$subspec
                          diff        lwr       upr     p adj
Indian-Bornean      -694.49536 -1270.45034 -118.5404 0.0128704
Sri Lankan-Bornean    60.73317  -515.22180  636.6881 0.9918725
Sumatran-Bornean    -190.72152  -766.67650  385.2335 0.8090934
Sri Lankan-Indian    755.22854   179.27356 1331.1835 0.0060659
Sumatran-Indian      503.77384   -72.18113 1079.7288 0.1043831
Sumatran-Sri Lankan -251.45469  -827.40967  324.5003 0.6457027
```

| 栏 | 含义 |
|---|---|
| **行名** | 被比较的一对组。⭐ **把中间的连字符当成减号读**：`Indian-Bornean` = Indian 的均值 − Bornean 的均值 |
| `diff` | 观测到的均值差（含正负号，符号方向由行名顺序决定） |
| `lwr` / `upr` | 该差值的 95% **family-wise** 置信区间下/上限 |
| `p adj` | **已对多重比较校正过的 p 值**。< 0.05 即该对显著 |

**读法示范**：`Indian-Bornean` 的 diff = −694.50 → Indian 比 Bornean **轻** 694.50 kg → **Bornean 比 Indian 重 694 kg**，且 p = 0.0129 < 0.05 显著。
`Sri Lankan-Indian` = +755.23，p = 0.0061 → **Sri Lankan 比 Indian 重 755 kg**，显著。
其余四对 p 均 > 0.05 → 无证据表明有差别。

**另一个交叉验证的技巧**：若置信区间 `[lwr, upr]` **跨越 0**，则该对不显著；不跨越 0 则显著。上表中不显著的行确实都是一负一正。

**双因素 ANOVA 的 Tukey 输出**会按每个预测变量分块（`$helmet`、`$vehicle`，或 `$sex`、`$subspec`），只看你真正控制好的那一块。

### 3.8 可视化：箱线图 (box-and-whiskers plot)

由 John Tukey 发明。R：

```r
boxplot(weight ~ feed, data = chickwts, ylab = "grams")
```

判读要点：
- **盒中粗线 = 中位数 (median)**，不是均值！
- **盒的下沿 / 上沿 = 第 25 / 75 百分位数**（下四分位数 Q1 / 上四分位数 Q3），盒高 = 四分位距 IQR。
- **须 (whiskers)**：最长延伸到距盒沿 1.5 × IQR 处；但若该方向最远的数据点更近，则须**止于最后一个数据点**（须端一定是真实数据点）。
- **须外的点画成圆圈**，即离群点 (outliers)。
- 用途：一眼看出**各组的中心位置**和**各组的离散程度**——后者正是判断方差齐性假设的直观依据（Practical Q3.5 的考点）。

### 3.9 可视化：带显著性横线的条形图（报告 ANOVA 的标准图）

这是本课**报告单因素 ANOVA 结果的推荐图**（手册 Figure 3.3、Lecture Part 2 Slide 14）：

1. **每根条 = 一组的均值**；
2. **误差条 = 该组均值的标准误 (standard error, SE)**（与上周报告 t 检验时的约定一致）；
3. **把条按均值大小排序**（从大到小或从小到大）；
4. **在条的上方画水平横线**：**落在同一条横线之下的各组之间没有显著差异**；不在同一条横线下的组之间显著不同。

**读图示范**（大象例子）：最上面那条横线盖住 Sri Lankan、Bornean、Sumatran → 这三者之间无显著差异；第二条横线盖住 Sumatran 和 Indian → 这两者之间无显著差异；但 Indian 与 Sri Lankan **不在同一条线下** → 二者显著不同。

排序的目的正是让「不显著的组」尽可能相邻，从而能用少数几条横线概括全部 $\binom{k}{2}$ 个比较结果，读者一眼即懂。

**图注 (figure legend) 范式**：
> "Mean mass for four Asian elephant subspecies. Error bars show standard error around the mean. Horizontal lines indicate that species means are not significantly different (α = 0.05)."

> ⚠️ 老师强调：**图注必须让读者不看正文也能看懂这张图**，因为很多读者为省时间只看图。同时图注要尽可能简洁。

### 3.10 结果的文字报告范式（本课重点技能）

**单因素 ANOVA 的整体结果**（手册）：
> "We found strong evidence for an effect of diet on chick mass (F(5,65) = 15.37, p < 0.0001)."

**格式说明**：`F(df_treat, df_resid) = F值, p = ...`。Lecture 中也写作 `(F = 5.1; df = 3, 36; p = 0.0046)`。

**p 值的写法约定（老师的个人规范，本课按此执行）**：
- p 值报到**四位小数**；
- 小于 0.0001 的一律写作 **"p < 0.0001"**，不写 `p = 5.94e-10`。
- 理由：知道 p 是 10⁻⁸ 还是 10⁻⁴ **不会改变我们的解读**；而且极小的 p 值「精确 (precise) 但未必准确 (accurate)」。

**ANOVA + Tukey 的完整报告范式**（Lecture Part 2）：
> "Mean mass differed among elephant subspecies (F = 5.1; df = 3, 36; p = 0.0046). Indian elephants were smaller than Sri Lankan elephants by 755 kg (p = 0.0061) and smaller than Bornean elephants by 694 kg (p = 0.0128)."

**结构**：先报**整体 ANOVA 结论 + F + df + p**，再逐条报**重要的两两比较：效应量 (effect size) + p 值**。

⭐ **必须同时报告效应量和 p 值**——p 值告诉读者「该有多相信这个结果」，效应量告诉读者「这个差异有多大、在生物学上重不重要」。老师原话：*"For a reader trying to understand the empirical system, the effect sizes are the most important part."*

**Practical 给的模板（更完整，含「无差异」的处理）**：
> "Mean femur lengths differed among males of the Hyla species we studied (p < 0.0001). Femurs were longer in H. arenicolor than in H. chinensis (6.25 mm, p < 0.0001) and in H. cinerea than in H. chinensis (7.98 mm, p < 0.0001). We found no significant difference in the mean femur lengths of male H. cinerea and H. arenicolor (p = 0.3034)."

⚠️ 注意：**不显著的那一对只报 p 值、不报差值**——因为我们没有证据说它们不同，报一个差值会误导读者。

**双因素 ANOVA 的报告范式**（Practical Q3.4 答案）：
> "The mean femur length differed among Hyla species when controlling for sex (p < 0.0001), but did not differ among sexes when controlling for species (p = 0.112). We found no evidence for an interaction between sex and species on femur length (p = 0.452). Overall, the mean femur length in H. arenicolor was greater than in H. chinensis by 5.47 mm (p < 0.0001), and the mean femur length in H. cinerea was greater than in H. chinensis by 6.73 mm (p < 0.0001). We found no significant difference in the mean femur length of H. arenicolor and H. cinerea (p = 0.4107)."

⭐ **"when controlling for X" 这个短语是双因素 ANOVA 报告的必备成分**——因为 p 值本身就依赖于「控制了谁」。

**⚠️ 绝对不要做的事**：把 R 的输出表原样粘贴到报告里。手册：*"Avoid that temptation!"* 转写里老师也专门批评了这一点（详见第四节）。手册进一步指出：如果只有三四组，可以在正文里把所有两两比较写完；但**六组就有 15 个两两比较，全写进正文读者会被淹没**——这时必须思考读者真正想知道什么，只聚焦于此。

---

## 四、课堂补充（15-Nov 现场答疑课转写）

> **重要背景**：这节现场课是**非强制的答疑/扩展课**（老师特意说明没放签到码，因为不想为非强制课程触发全校考勤警报）。老师的定位是「尽量做成互动问答课；如果没人提问，我就讲一些超出单元核心、但对你们职业生涯有用的扩展内容」。
> **⚠️ 内容提示**：这节课的绝大部分内容其实在**复习 Week 01 的 t 检验与 Wilcoxon 检验**（讲 Practical 2 的答案），ANOVA 只在最后一句提到（"When we go to the practical session, we'll look at… the ANOVA test"）。但里面有大量 slides 和手册上完全没有的深刻内容，**必须掌握**。

### 4.1 上周 Practical Q3 的完整走查（毒箭蛙 Dendrobates auratus）

**数据**：Juarez 等的无尾类形态测量数据，来自美国的博物馆标本；每个物种 15 雄 15 雌。列：物种、采集国、性别、mass（质量）、femur length（股骨长）、SVL（snout-vent length，吻肛长）。

**老师对三种测量的评价（考点级细节）**：
- **SVL** 变异较大，因为它取决于**标本摆放的姿势**；
- **股骨长 (femur length)** 更稳定，因为它是**骨头**，标本在博物馆里干燥收缩也不会改变。
→ 这解释了为什么 Practical 3 全程用 femur 而不用 SVL。

**工作流程**：
```r
setwd("...")                                    # 设置工作目录
den.or = read.csv("Dendrobates_auratus.csv", header=TRUE)  # 读入 csv
female.mass = den.or$mass[den.or$sex == "F"]    # 方括号子集：取 sex 为 F 的行的 mass 列
male.mass   = den.or$mass[den.or$sex == "M"]
t.test(female.mass, male.mass, alternative="greater")   # 单尾 t 检验
```

**老师关于 `setwd()` 的实用提醒**：把 `setwd()` 写进脚本里，而不是每次手动点菜单——*"I saved this data set years ago and I don't remember where it is… but R remembers it."* 脚本里留着路径，多年后还能直接跑。

**关于 `read.csv`**：*"this is one of the commands that you probably will memorize, not because you have to, but by default, you'll use this many times every week."*

**R 使用习惯**：命令执行后没报错就说明成功了，但看不到结果；想看就在 Environment 面板点开，或把对象名单独运行一次。

**结果与解读**：雌性均值 ≈ 2.6 g，雄性 ≈ 2.15 g，**p = 0.08**。
老师的解读示范：
- p ≈ 0.8 或 0.9 → 「看起来没什么名堂」；
- p < 0.05 → 「算作证据」；
- **p = 0.08 → 人们常称为 "marginally significant"（边缘显著），结论是 inconclusive（不能下定论）**：「靠运气得到这么大的差异并非不可能，但也确实不太可能」。

**为什么是单尾**：因为**进场时就带着一个有方向的假设**（"are females larger?"），不是问「是否不同」。学生提问确认：**双尾检验的 p 值一般会比单尾大**，因为双尾把「雌大于雄」和「雄大于雌」两个方向都算进去了。

### 4.2 ⭐ 老师对「如何报告结果」的当堂批评（本周最重要的软技能）

老师看过学生提交的 practical 后说：整体做得很好，但**有几个人直接把 R 的输出复制粘贴到答题纸上当作答案**。

> *"This is a report of results[?]. And we really can't do that in science. In science, we need to communicate our results to a broader public. And a lot of those people don't code in R and they don't read R output… especially if you're communicating with members of the public, policy makers, these people aren't necessarily trained in the same programs that you will be. So this means very little to them. So we need to convert this into something visual that they can use and plain English."*

老师的标准答案形态 = **一句话 + 一张带图注的图**：
> "We found marginally significant evidence that female *D. auratus* were more massive than males (雌均值, 雄均值; t = …, df = …; p = 0.08)."

这一句话里包含了读者需要的全部信息：**有没有差异、往哪个方向、差多少、有多可信**。

### 4.3 ⭐ 如何判断数据是否正态——两条路

**路径一：看直方图（但要小心样本量）**
老师承认自己先做了检验才画直方图（"I jumped right into analyzing it without looking at the histogram"）——这是不好的习惯，应先看数据。

雌蛙质量的直方图看起来不像钟形。学生说「不正态」，老师的回应值得记住：

> *"Personally, when I look at this, I'm not completely sure because it's a really small data set. If you have a really small data set, you can get a lot of variability just by chance and we don't necessarily see that bell curve. So with a small data set, it can be hard to tell."*

**→ 小样本的直方图很难判断正态性，别过度自信。**

**为什么不正态？（这是生物学问题，不是统计问题）**
老师引导学生想到：**最左边那一小簇小个体可能是幼体 (juveniles)**。如果数据里混了幼体和成体，就是两个不同的分布叠加，自然不是单峰正态。

**路径二：理论推理（更强的判断依据）**
用果蝇交配延迟 (latency to mate) 数据示范：这类数据**有理论上的理由不是正态的**。

推导：设有 N 只果蝇，每只在每一分钟内交配的概率为 R（恒定且相互独立）。
- 第 1 分钟：期望有 $NR$ 只交配；
- 第 2 分钟：已有比例 $R$ 退出，剩下 $N(1-R)$ 只，其中期望 $N(1-R)R$ 只交配；
- 第 3 分钟：$N(1-R)^2R$；
- ……第 t 分钟：$N(1-R)^{t-1}R$。

每一步交配的数量都在**递减**，形成**指数分布 (exponential distribution)**——严重右偏，绝不是正态。

> 老师的核心教诲：*"The point is not to memorize this distribution, but just to think, when you're deciding whether a data set is normally distributed, often there's a theoretical reason for believing it wouldn't be."*

**指数分布怎么办**：有时**取对数 (logging the data)** 就能矫正。但**如果数据是离散化的、大量堆在第一个时间格里，取对数解决不了问题**——这时只能用 Wilcoxon 这类基于秩的方法。

### 4.4 面对非正态数据的两种应对及其风险

**应对一：把可疑的点（疑似幼体）剔除**
学生提出这个方案。老师的评价（**重要的科研伦理/方法论警示**）：

> *"There's a risk… if we were sure that these things on the bottom were juveniles, then we could pull those out and ask about adults. But we don't actually know. Maybe they're small adults. So possibly, if we throw those things out, we might be throwing out information about our data, and then we might assume that females are bigger than they really are, because we've thrown out the small ones."*

**→ 在没有独立证据支持的情况下删数据，会人为制造偏倚。**

**应对二：改用 Wilcoxon 检验**
```r
wilcox.test(female.mass, male.mass, alternative="greater")
```
语法与 `t.test()` 完全相同。结果 **p = 0.04**，比 t 检验的 0.08 更「显著」一点。

**关于警告信息（实用陷阱）**：R 会报 *"cannot compute exact p-values with ties"*。老师解释：Wilcoxon 检验计算 p 值的方式是**枚举数据的所有可能排列 (permutation)**；如果**没有并列值 (ties)**，p 值可以**解析地精确算到无穷位小数**；有并列值时就只能**估计**，但估计精度也有五六位小数。
> **→ 这条警告基本可以忽略。** 老师顺带提醒："Sometimes when I spit out a warning, it's a problem. This one's not."

### 4.5 ⭐⭐ Wilcoxon 检验到底在问什么——它和 t 检验不是一回事

这是本节转写最有价值的部分，slides 和手册里都没有讲透。

**t 检验问的是**：两组的**均值**是否不同。

**Wilcoxon 问的是**（老师的口语化定义，非常好用）：
> *"If I randomly choose a fly from one group, the control group, and I randomly choose one from the anesthetized group, and I ask which one is bigger, and then I do this again and again and again… is the proportion of times that the larger fly is in one group larger than we'd expect by chance?"*

也就是说，Wilcoxon 检验的是**秩 (ranks)**，有人称之为 **superiority（优势性）**——「随机取一对，来自 A 组的那个更大的概率是否偏离 50%」。它**仍然**在回答「控制组的延迟是否短于麻醉组」，但**是通过两两比较而非通过均值**来回答。

**震撼的实例——均值和中位数讲相反的故事**：

果蝇实验（Manchester 本科生 Tysall et al. 2019 的真实数据）：给果蝇标记必须先麻醉（用**冰**或 **CO₂**），因为「你没法在飞着的果蝇身上点一个漆点」。麻醉后等 3 天，把一雌一雄放进小管，记录交配延迟。假设：**麻醉过的果蝇交配更慢**。

```r
control.latency   = flies$latency[flies$treatment == "control"]
treatment.latency = flies$latency[flies$treatment != "control"]  # != 是「不等于」，一次抓住 ice 和 CO2
wilcox.test(control.latency, treatment.latency, alternative="less")
```

结果：**p = 0.995**（！）

老师引导学生注意这个异常。**关键洞见**：
- 单尾检验中，「A < B」的 p 值 ≈ **1 减去**「A > B」的 p 值。
- p = 0.995 意味着反方向的证据极强：**麻醉过的果蝇反而交配得更快**，与假设完全相反。

**但**再看两组的**均值**：**控制组的平均延迟反而更小**（即控制组更快）——与 Wilcoxon 的结论**相反**！

**为什么？**（看直方图就懂）
- 麻醉组的分布整体更靠近 0——**大多数麻醉过的果蝇确实交配得更快**，所以麻醉组的**中位数更小**；
- **但**最右端还有一根柱子：那是**根本没交配的果蝇**。实验在 2 小时时终止，这些果蝇在数据里被记成 120 分钟。**麻醉组里彻底失败的个体更多**。
- 这些 120 的极端值**把麻醉组的均值狠狠拉高**，于是均值讲了一个相反的故事。

**生物学解读（老师的猜想）**：麻醉可能对大多数果蝇没影响，但对那些本来就比较慢的个体，会把它们推向彻底失败。

**⭐⭐ 方法论结论（老师反复强调）**：
> *"People will often think that if you can't do a t-test, you just do a Wilcoxon and it tells you the same thing. It doesn't. It's a different story… And it's worth keeping that in mind because people, even experienced researchers, often ignore that and often miss that subtlety."*

**→ Wilcoxon 不是 t 检验的「无假设版替代品」，它回答的是另一个问题（秩/中位数方向 vs 均值）。** 同理，**Kruskal-Wallis 也不是 ANOVA 的等价替代**——手册也明确说它检验的是 mean ranks 而非 means。

### 4.6 ⭐ HARKing——不能看到结果再改假设

学生自然会问：既然 p = 0.995，我把假设反过来（`alternative="greater"`），不就得到一个很小的 p 值了吗？

老师：**"Not really. People do it, you probably shouldn't."**

理由：这叫 **HARKing（Hypothesizing After the Results are Known，结果已知后才提出假设）**。
> *"We already know that the p-value is gonna be small because we can see it from this test. So if we run the opposite test, it's not really a new hypothesis test. It's something that we knew before we did it. So it's not the probability that we would see this by chance, because we know the probability that we're gonna see this significant p-value here is close to one — we've seen it."*

**→ p 值的意义建立在「假设是事先提出的」之上。事后掉转假设，p 值就不再是它声称的那个概率了。**

但老师也补充：**计算这些 p 值并非毫无价值**——它确实告诉了我们数据里的模式；只是**不能把它当成一次假设检验来报告**。

### 4.7 ⭐ 统计推断的边界：我们的「总体 (population)」到底是什么？

这是老师花了很长时间讲的、极具野外科学特色的一节。

问题：我们说「雌蛙比雄蛙大」——**哪些**雌蛙？

> *"This is something that natural scientists run into a lot, because it's really hard to do controlled experiments."*

推理链条：
- **如果**采集者是从野外种群中**随机抽样**的，那么样本能代表整个物种，结论可以推广到 *Dendrobates auratus* 这个物种。
- **但我们无法确定**。这是**博物馆标本**，存在多种系统性偏倚：
  - 幼体可能**更容易捕捉** → 幼体在数据里被过度代表；
  - **博物馆标本尤其常见的偏倚**：采集者「只带回最好的标本」——**只留最大的个体**。

**老师的结论**：
> *"Here, I think it represents museum samples from the US. And I'm not sure we can really extend this that much to frogs in the field. It might hold in the field or it might not. And that's something we'd have to do further testing to find out."*

**→ 统计检验的 p 值只对「你实际抽样的那个总体」有效。数据的产生过程决定了推论的适用范围。**（这也解释了 Practical 3 里为什么每次都强调这是 Juarez 等人的博物馆数据。）

### 4.8 实用 R 技巧

**`unique()` —— 检查分类变量有哪些水平、顺便查错别字**
```r
unique(flies$treatment)   # 返回该列所有不重复的取值
# [1] "control" "ice" "CO2"
```
老师说明用途：
1. 数据集有几百行时，**手动滚动去找所有类别既慢又容易漏**；
2. **能查出录入错别字**——如果有人把 "control" 打成 "cotnrol"，`unique()` 里会多出一个名字。

**`!=` —— 「不等于」，一次性取补集**
```r
flies$latency[flies$treatment != "control"]   # 所有 treatment 不是 control 的（即 ice + CO2）
```
比写两个条件用 `|` 连接更简洁。

**`View()`** —— 弹出表格窗口查看整个数据框（等价于在 Environment 面板点击对象名）。

### 4.9 扩展：Monte Carlo 检验（非本课考核内容，但要知道它存在）

老师最后提了一个「难题」：**如果我们就是想比较均值（中位数不够用），但数据又不正态，怎么办？**

答案是 **Monte Carlo 检验**（手册中略有提及，本课不要求实现）：

**思路**：如果两组之间真的没有差异，那么把观测值**随机重新分配**到两组里，应该和真实分组没什么两样。于是：
1. 随机打乱分组标签；
2. 计算你**关心的任何统计量**——均值差、中位数差、方差差，任意；
3. 重复几千次，得到「纯靠运气」的**零分布 (null distribution)**；
4. 把观测值画在同一坐标轴上，看它落在零分布的什么位置。

对果蝇数据做均值差的 Monte Carlo 检验，结论是：**随机分组几乎总能产生至少和观测值一样大的均值差 → 没有证据说明两组均值不同**（与 4.5 节 t 检验式的均值比较一致，但与秩的结论不同）。

**为什么本课不教**：*"you have to write a lot of code to get it to work."*

**为什么值得知道**：
> *"It's a very flexible test because you can use it for almost any kind of weird data that you have. And it really can tell you about the specific things that you're interested in."*

**"非参数 (nonparametric)" 的含义**（老师给了一个很清晰的解释）：
> t 检验会**计算均值、计算方差**，并基于这些「参数」工作；Monte Carlo 检验**除了你的检验统计量之外什么都不算**，所以没有参数。代价是：它**不会顺带告诉你方差之类的信息**（除非你自己去算），信息量比参数方法少；好处是几乎不受分布假设约束。

---

## 五、Practical 要点

### 5.1 学习目标（Practical 3 开篇）

完成后你应当能够：
- 实施并**报告**单因素 ANOVA 与事后 Tukey 检验
- 实施并**报告**双因素 ANOVA
- **解读交互作用**
- **用图表展示 ANOVA 的结果**

### 5.2 数据与准备

**数据集**：`data_from_Juarez_et_al_2023.csv`——Juarez, Moen & Adams (2023) 关于无尾类 (anurans) 性二态与跳跃演化的研究数据（*Journal of Evolutionary Biology* 36(5): 829–841）。这是**上周数据的完整版**：上周老师已经把每个物种拆好给你了，**这周要你自己从原始大表里筛**。

```r
anurans = read.csv("data_from_Juarez_et_al_2023.csv", header = TRUE)
# read.csv：读入逗号分隔文件
# header=TRUE：第一行是列名，不是数据

nrow(anurans)      # 返回数据框的行数，用来校验导入是否正确
# 应当返回 3325
```
⚠️ **强烈建议把对象命名为 `anurans`**，否则 practical 附带的 starter code 需要逐处改名。

导入后要**检查每一列的含义**（`View()` / 点 Environment）。

### 5.3 Question 1：单因素 ANOVA（雄性 *Hyla* 三物种的股骨长）

**生物学背景**：**属 (genus, 复数 genera)** 是一组亲缘关系密切的物种。理想情况下属应是**单系的 (monophyletic)**——包含某个共同祖先的**全部且仅有**的后代物种。*Hyla* 是分布在欧洲、亚洲部分地区和北非的树蛙属；自然界有 17 个 *Hyla* 物种，本数据集里只有 3 个：*H. arenicolor*、*H. chinensis*、*H. cinerea*。

**步骤 1：两层子集**
```r
hyla = anurans[anurans$genus == "Hyla", ]        # 先筛出属为 Hyla 的所有行（注意逗号后为空 = 保留所有列）
male.hyla = hyla[hyla$sex == "m", ]              # 再从中筛出雄性
```
（这是上周方括号子集语法的复用；`[行条件, 列条件]`，列条件留空表示全取。）

**步骤 2：单因素 ANOVA**
```r
hyla.femur.aov = aov(femur ~ species, data = male.hyla)
# aov()   ：拟合方差分析模型
# femur   ：响应变量（数值），置于 ~ 左侧
# ~       ：波浪号，读作 "depends on"（取决于）
# species ：预测变量（分类），置于 ~ 右侧
# data=   ：告诉 R 到哪个数据框里去找 femur 和 species 这两个名字
# 结果存入 hyla.femur.aov 这个对象；直接运行不会打印任何东西

summary(hyla.femur.aov)   # 打印 ANOVA 表（Df / Sum Sq / Mean Sq / F value / Pr(>F)）
```

**Q1.1：三个 *Hyla* 物种雄性的股骨长有显著差异吗？怎么知道的？**
> **答**：有。因为 **species 那一行的 p 值 < 0.05**。
> （解题要点：判断依据是**预测变量那一行**的 `Pr(>F)`，不是 Residuals 行。）

**步骤 3：事后 Tukey 检验**
```r
TukeyHSD(hyla.femur.aov)   # 参数是上面 aov() 的输出对象
```
输出：
```
  Tukey multiple comparisons of means
    95% family-wise confidence level
Fit: aov(formula = femur ~ species, data = male.hyla)

$species
                        diff       lwr       upr     p adj
chinensis-arenicolor -6.24600 -9.009707 -3.482293 0.0000066
cinerea-arenicolor    1.73019 -1.082435  4.542816 0.3034225
cinerea-chinensis     7.97619  5.163565 10.788816 0.0000001
```

**逐行判读**：
- 第 1 行 `chinensis-arenicolor`：把连字符读作**减号** → chinensis 的均值 − arenicolor 的均值 = −6.25 mm → **arenicolor 的股骨平均长 6.25 mm**。p adj = 6.6e-06 < 0.05 → 显著。
- 第 2 行 `cinerea-arenicolor`：p adj = 0.3034 > 0.05 → **随机样本的均值本来就很容易差这么多**，不能认为二者真的不同。（注意其置信区间 [−1.08, 4.54] 跨越 0，与不显著一致。）
- 第 3 行 `cinerea-chinensis`：diff = +7.98 → **cinerea 比 chinensis 长 7.98 mm**，p adj = 1e-07 → 高度显著。

**Q1.2：雄性 *H. cinerea* 与 *H. chinensis* 的股骨长差多少？显著吗？**
> **答**：*H. cinerea* 的股骨平均比 *H. chinensis* 长 **7.98 mm**；统计显著（**p < 0.0001**）。

**Q1.3：清晰简洁地报告 ANOVA + Tukey 的结果。**
> **答**：*"Mean femur lengths differed among males of the* Hyla *species we studied (p < 0.0001). Femurs were longer in* H. arenicolor *than in* H. chinensis *(6.25 mm, p < 0.0001) and in* H. cinerea *than in* H. chinensis *(7.98 mm, p < 0.0001). We found no significant difference in the mean femur lengths of male* H. cinerea *and* H. arenicolor *(p = 0.3034)."*
>
> **写作要点**：① 先整体后两两；② 显著的对**同时给效应量和 p**；③ 不显著的对**只给 p、不给差值**；④ 极小 p 值统一写 "p < 0.0001"；⑤ 物种名用斜体。

**Q1.4：作图。**
用 starter code 生成的**排序条形图 + 显著性横线**（见 3.9 节），必须配**图注**。

### 5.4 Question 2：雌性重做一遍（Q1 的迁移练习）

把 Q1 的代码里的 `sex == "m"` 改成 `"f"` 重跑。

**Q2.1 答案**：
> *"Mean femur lengths differed among females of the* Hyla *species we studied (p = 0.0022). Femurs were longer in* H. arenicolor *than in* H. chinensis *(4.70 mm, p = 0.0132) and in* H. cinerea *than in* H. chinensis *(5.52 mm, p = 0.0032). We found no significant difference in the mean femur lengths of* H. cinerea *and* H. arenicolor *(p = 0.8621)."*

**值得注意的对比**：雌性的整体 p 值 (0.0022) 明显不如雄性 (< 0.0001) 小，各对差值也更小（4.70 / 5.52 vs 6.25 / 7.98）——但**定性结论一致**：两个物种大于 *H. chinensis*，而这两个物种之间无差异。

### 5.5 Question 3：双因素 ANOVA（*Hyla* 属是否有性二态）

**问题**：三个 *Hyla* 物种大小不同（Q1、Q2 已证），但**两性之间**是否有大小差异？即这个属是否**性二态 (sexually dimorphic)**？

**Q3.1（挑战题）：这里能用 t 检验吗？为什么？**
> **答**：**不能**。t 检验假设**待比较的两组内部（这里是两个性别组）数据服从正态分布**。而我们这里不满足：**三个物种的平均大小不同，把三个物种混在一起，每个性别的大小数据就会出现多个峰 (multiple modes)**，不是正态分布。
>
> ⭐ 这道题把「正态性假设针对的是**组内**」这条原则用活了——正好对应手册 Figure 3.4 的反向应用：**如果分组结构没有被建模进去，混合分布就会多峰**。

**步骤 1：完整的双因素 ANOVA（含交互项）**
```r
hyla.femur.aov = aov(femur ~ species + sex + species*sex, data = hyla)
# species      ：第一个主效应（先进入模型，未被任何变量控制）
# sex          ：第二个主效应（在控制了 species 的前提下被检验）
# species*sex  ：交互项，必须放在最右边
# data = hyla  ：注意这里用的是完整的 hyla（含两性），不是 male.hyla

summary(hyla.femur.aov)
```

**Q3.2：有证据表明某一性别的股骨可预测地更大吗？有证据表明性别对股骨的影响在不同物种间不同吗？**
> **答**：都**没有**。
> - sex 的主效应 **p = 0.112 > 0.05** → 控制物种后，没有证据说明两性股骨长不同。
> - 交互项 **p = 0.452 > 0.05** → 没有证据说明性别效应因物种而异。

**步骤 2：理解顺序问题（Practical 的精确表述）**

在 `femur ~ species + sex + species*sex` 中：
- **sex 是在控制了 species 的前提下被检验的**——问的是：「**如果一雄一雌属于同一物种**，知道性别能否帮我们猜出谁的股骨更长？」
- **species 则没有被 sex 控制**——问的是：「**不区分性别地**，各物种整体（两性合并）是否互不相同？」而**不是**「各物种的雄性之间不同、且各物种的雌性之间不同」。

想在**控制性别**的前提下研究物种，必须把顺序反过来：
```r
hyla.femur.aov = aov(femur ~ sex + species + species*sex, data = hyla)
summary(hyla.femur.aov)
```
⚠️ **交互项永远放最右边**——「在不控制主效应的情况下讨论交互作用，几乎没有意义」。

**步骤 3：决定最终模型里保留哪些项**

老师的推理（见 2.8 节）：
- **删掉交互项**：本次数据无证据支持，且没有先验理由必须保留；
- **研究 species 时保留 sex**：因为「我们知道许多无尾类的股骨长确实存在性别差异」（先验知识 → 强制保留 / forcing）；
- **研究 sex 时保留 species**：因为「我们知道股骨长确实因物种而异」。

```r
# 研究 species（控制 sex）：species 放最后
hyla.femur.species.aov = aov(femur ~ sex + species, data = hyla)
summary(hyla.femur.species.aov)
```

**Q3.3：按上面的逻辑，研究 *Hyla* 属中 sex 的主效应该用什么代码？**
> **答**：
> ```r
> hyla.femur.species.aov = aov(femur ~ species + sex, data = hyla)
> summary(hyla.femur.species.aov)
> ```
> **要点**：**把 sex 放到最后**，让它在控制 species 的前提下被检验。（答案键里对象名沿用了 `hyla.femur.species.aov`，命名不是重点，**公式里的顺序才是**。）

**步骤 4：Tukey 检验——只看该看的那一块**
```r
TukeyHSD(hyla.femur.species.aov)
```
输出会**同时**给出 `$sex` 和 `$species` 两块。但：
- ANOVA 显示**控制物种后性别无效应** → **没有理由去看 `$sex` 那一块**（没有证据说存在差异，就没必要问差多大）；
- ANOVA 显示**控制性别后物种有效应** → **看 `$species` 那一块**，读法与单因素 Tukey 完全相同。

**Q3.4：填空完成报告。**
> **答**：*"The mean femur length differed among* Hyla *species when controlling for sex (p < 0.0001), but did not differ among sexes when controlling for species (p = 0.112). We found no evidence for an interaction between sex and species on femur length (**p = 0.452**). Overall, the mean femur length in* H. arenicolor *was greater than in* H. chinensis *by 5.47 mm (p < 0.0001), and the mean femur length in* H. cinerea *was greater than in* H. chinensis *by **6.73 mm** (p < 0.0001). We found no significant difference in the mean femur length of* H. arenicolor *and* H. cinerea *(**p = 0.4107**)."*

⭐ **对比 Q1.3 与 Q3.4 的效应量**：Q1（只有雄性、单因素）里 arenicolor − chinensis = 6.25 mm；Q3（两性合并、控制性别）里变成 5.47 mm。**同一对物种、不同模型 → 不同的效应量估计**。这不是矛盾，而是因为两个模型问的是不同的问题（「雄性之间」vs「控制性别后总体上」）。报告时必须写清楚是哪个模型。

**Q3.5（挑战）：图上有什么值得担心的地方？**
> **答**：**ANOVA 假设各组内方差近似相等，但图上看起来各组方差明显不同。**
> （这正是箱线图的用途——各盒的高度/须的长度差异大 = 方差不齐的信号。）

**Q3.6（超级挑战）：能做什么？**
> **答**：**第一步可以考虑先对股骨长取对数 (`log(femur)`) 再做分析。**
> （补充：手册给出的其他路线是用 `oneway.test()` 做 Welch 校正，事后检验改用 `rstatix` 里的 Games-Howell；但对于**双因素**的情形，取对数是更自然的第一步。取对数之所以有效，是因为形态测量数据的方差常与均值同步增长，对数变换能稳定方差。）

**图形**：Q3 用**箱线图 (box plot)** 展示。Practical 建议**读懂 starter code**，因为 Q4 需要自己改写一个类似的图。

### 5.6 Question 4：独立完成一遍（*Eleutherodactylus* 属）

**生物学背景**：*Eleutherodactylus* 是新热带界 (Neotropics) 的一个属，包含 200 多个物种。最著名的是 **common coquí (*E. coqui*)**，原产波多黎各，在夏威夷是**入侵害虫**；也是研究**性选择 (sexual selection)** 的常用模式物种。数据集里有 3 个物种：*E. coqui*、*E. marnockii*、*E. planirostris*。

**任务**：用 Q3 的方法，评估该属中股骨长是否因物种而异、是否因性别而异。

**Q4.1：本分析中 sex 的 p 值是否取决于我们有没有控制 species？**
> **答**：**是（Yes）**。
> 对比：在 *Hyla* 属里性别效应本来就不显著；在 *Eleutherodactylus* 里控制物种后 p = 0.0001。这道题就是要你**亲手跑两遍不同顺序**，看到 p 值确实变了，从而坐实 2.7 节的原理。

**Q4.2：报告 sex 和 species 的效应量时，应该来自同一个 Tukey 检验还是两个不同的 Tukey 检验？为什么？**
> **答**：**两个不同的 Tukey 检验**——一个用来评估「**控制物种后**的性别差异」（模型：`femur ~ species + sex`），另一个用来评估「**控制性别后**的物种差异」（模型：`femur ~ sex + species`）。
> **理由**：`TukeyHSD()` 依附于特定的 `aov` 模型，而 `aov` 用序贯平方和，**只有排在最后的那个预测变量才是被完全控制过的**。想干净地看某个变量的效应，就必须从「该变量排最后」的那个模型里取。

**Q4.3：报告结果。**
> **答**：*"In the genus* Eleutherodactylus, *femur length differed among species when controlling for sex (p < 0.0001), and between sexes when controlling for species (p = 0.0001). The mean femur length in* E. coqui *was greater than that in* E. marnockii *by 2.57 mm and that in* E. planirostris *by 5.90 mm. All pairwise differences among species were strongly significant (p < 0.0001). Controlling for species, femur length in females was greater than that in males by 1.41 mm (p = 0.0001). We found no evidence that the effect of sex differed among species (p = 0.5167)."*
>
> **写作要点（与 *Hyla* 的差异）**：
> - 这里**三对物种全部显著**，所以可以用 **"All pairwise differences among species were strongly significant (p < 0.0001)"** 一句概括，而不必逐条列 p 值——这正是手册说的「按读者需要精简」；
> - 性别效应显著，所以**必须报效应量**：雌性比雄性长 1.41 mm；
> - 交互作用不显著，用一句 "We found no evidence that the effect of sex differed among species (p = 0.5167)" 交代；
> - **每一个 p 值都注明了「controlling for 什么」**。

**Q4.4**：配图（箱线图，改写 Q3 的 starter code）。

### 5.7 Practical 中的关键纪律汇总

1. **ANOVA 不显著就不做 Tukey**。
2. **Tukey 输出里只解读你真正控制好的那一块**。
3. **交互项永远写在最右边**。
4. **想研究谁，就把谁放最后**。
5. **删/留预测变量没有唯一正确答案**，但要能说清理由（数据证据 vs 先验知识）。
6. **报告永远：先整体 → 后两两；显著给效应量+p；不显著只给 p**。
7. **每张图都要有能独立读懂的图注**。

---

## 六、易错点 / 重点难点

### A. 概念层面

1. **「两两 t 检验」为什么不行**——不是因为「t 检验不能用于三组」，而是因为**做 m 次检验会把族系假阳性率从 0.05 推高到远高于 0.05**。k=6 时超过 50%。
2. **ANOVA 是 omnibus 检验**。它只说「不全相同」，绝不说「谁和谁不同」。**看到 ANOVA 显著就断言"A 比 B 大"是典型错误**，必须靠 Tukey。
3. **ANOVA 的 p 值大 ≠ 各组均值相等**。「没有证据说明有差异」≠「有证据说明没有差异」。Practical 反复用 "we found no evidence for…" 而非 "there is no…" 就是这个道理。
4. **"error" 不是「错误」**，是「用处理去预测个体时的残余不确定性」。
5. **F 值只出现在预测变量那一行**，Residuals 行没有 F 和 p——因为 F 是「该项均方 ÷ 残差均方」，残差不能除自己。
6. **正态性假设针对的是「组内误差」，不是整个数据集**。整体三峰、组内正态 → **完全合格**（手册 Fig 3.4）。反之，Practical Q3.1 里把三个物种混在一起 → 多峰 → 不合格。这两个方向都要会讲。
7. **Kruskal-Wallis / Wilcoxon 不是 ANOVA / t 检验的等价替身**。它们检验的是**平均秩**，不是均值。转写里果蝇的例子是最强的反例：**中位数说麻醉组更快，均值说麻醉组更慢，两者都对，只是问题不同**。
8. **中位数与均值可能讲相反的故事**——尤其当数据有**截尾/极端值**时（果蝇 2 小时截止 → 未交配者记为 120）。
9. **「统计显著」≠「生物学重要」**。所以必须报**效应量**。
10. **推论的适用总体由抽样方式决定**。博物馆标本 → 结论只对「美国博物馆标本」成立，不能随意外推到野外种群。
11. **HARKing**：看到结果再倒过来提假设，p 值就失去了原本的含义。
12. **小样本时不要对「不正态」下定论**——小样本本来就随机波动大。判断正态性时，**理论推理（如交配延迟服从指数分布）往往比看图更可靠**。
13. **删除「可疑」数据点是危险操作**。没有独立证据（如年龄鉴定）就剔除小个体，会人为夸大结论。

### B. 双因素 ANOVA 特有的坑

14. **⭐ 预测变量的顺序改变 p 值和 Sum Sq**。`aov()` 用序贯（Type I）平方和，**每项只在控制了左侧所有项之后被检验**。这是本周最重要的「陷阱题」来源。
15. **想研究的变量放最后；只想控制、不想推断的变量（如观察者身份）放最前；交互项永远最右**。
16. **同一份输出里的多个 p 值不能同时"照单全收"**。在 `mass ~ sex + subspec` 里，subspec 的 p 值可以用（被 sex 控制了），**sex 的 p 值不能直接用**（没被控制）——老师在 slides 里两次说 "I will ignore that for now"，就是这个原因。要报告 sex，必须另跑一个模型。
17. **`TukeyHSD()` 的结果继承自它所依附的 aov 模型**。所以「helmet 的效应、vehicle 的效应、有没有交互」这三个结论**可能来自三个不同的模型**。
18. **交互项显著时，主效应不能单独解释**——因为一个因子的效应依赖于另一个因子的水平。
19. **交互项的自由度 = 两个主效应自由度之积**（1 × 6 = 6）。
20. **同一对组在不同模型下效应量不同**（Hyla：6.25 mm vs 5.47 mm）。报告时必须说明模型设定。

### C. R 操作与输出判读的陷阱

21. **`aov()` 运行后什么也不显示**——必须 `summary()` 才看得到结果。「没报错」只代表命令执行了。
22. **`Tukey` 不是 `Turkey`**（Practical 专门开玩笑提醒过）。
23. **Tukey 输出的行名要当减号读**。`A-B` 的 diff 为负 → **B 更大**。方向搞反是最常见的失分点。
24. **`p adj` 才是校正后的 p 值**，不要去看别的列。
25. **置信区间跨越 0 ⇔ 该对不显著**，可用于交叉检查。
26. **`wilcox.test` 的 "cannot compute exact p-values with ties" 警告可以忽略**（只是精度从解析解降为估计，仍有五六位小数）。
27. **`~` 左边是响应变量，右边是预测变量**；`~` 读作 "depends on"。这个语法会贯穿整门课（回归、卡方、逻辑回归、混合模型）。
28. **`data=` 参数只是告诉 R 去哪儿找变量名**；也可以不用它而写 `aov(chickwts$weight ~ chickwts$feed)`，效果相同。
29. **子集语法 `df[条件, ]` 的逗号不能漏**——漏掉逗号会变成对列取子集。
30. **`!=` 是「不等于」**，取补集很方便。
31. **`unique()` 用来列出因子的全部水平并检查录入错别字**。
32. **不要把 R 输出直接粘贴进报告**——老师当堂批评过。
33. **给对象起有意义的名字**（`den.or`、`male.hyla`、`hyla.femur.aov`），并且**不要覆盖你之后还要用的模型**（手册特意把结果分别存为 `ba`、`ba1`、`ba2`，方便回头比较）。
34. **`nrow()` 用来校验数据是否完整导入**（anurans 应为 3325 行）。
35. **手册第 37 页脚注的 F 统计量缩放因子与自由度有笔误**——以 $F=\dfrac{SS_{treat}/(k-1)}{SS_{err}/(n-k)} \sim F_{k-1,\,n-k}$ 为准。

### D. 报告与写作

36. **必须同时给效应量和 p 值**；不显著的对只给 p 值。
37. **p < 0.0001 就写 "p < 0.0001"**，不要写 5.94e-10。其余报到四位小数。
38. **F 值要连自由度一起报**：`F(5,65) = 15.37`。
39. **双因素 ANOVA 的每个 p 值都要注明 "when controlling for …"**。
40. **图注要能脱离正文独立读懂**，且要说明误差条代表什么（SE）、横线代表什么（不显著）、α 是多少。
41. **组太多时不要在正文里列全部两两比较**（6 组 = 15 对）——挑读者真正关心的说，或用「全部显著」一句概括。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Analysis of Variance (ANOVA) | 方差分析 | 通过比较组间变异与组内变异，一次性检验多组均值是否全相同的方法；由 R. A. Fisher 提出 |
| one-way ANOVA | 单因素方差分析 | 只有一个分类预测变量的 ANOVA |
| two-way ANOVA | 双因素方差分析 | 有两个分类预测变量（可含交互项）的 ANOVA |
| multiple testing / multiple comparisons | 多重检验 / 多重比较 | 在同一数据集上做多次比较，导致至少犯一次第一类错误的概率被抬高的问题 |
| Type I error | 第一类错误 | 假阳性：实际无效应却宣称有效应 |
| false positive rate | 假阳性率 | 第一类错误发生的概率，记作 α，惯例取 0.05 |
| α (alpha) | 显著性水平 | 人为设定的 p 值判定阈值，同时也是单次检验的假阳性率 |
| family-wise error rate (FWER) | 族系错误率 | 一整族比较中「至少犯一次第一类错误」的概率 |
| family-wise confidence level | 族系置信水平 | Tukey 输出中「95%」的含义：整族比较合起来的置信水平 |
| omnibus test | 总括检验 / 全局检验 | 只回答「是否存在差异」、不指明「哪两组不同」的检验；ANOVA 即是 |
| post hoc test | 事后检验 | ANOVA 显著后，用于确定具体哪些组两两不同的检验 |
| Tukey's HSD (Honest Significant Difference) test | Tukey 诚实显著差异检验 | 做全部两两比较并内置多重比较校正的事后检验；R 中为 `TukeyHSD()` |
| deviation / deviance | 离差 | 单个观测值与某个均值之差 |
| grand mean | 总均值 | 全体观测值的均值，忽略分组 |
| treatment mean / group mean | 组均值 / 处理均值 | 某一组内部观测值的均值 |
| treatment effect | 处理效应 | 组均值与总均值之差，即「属于这一组」带来的效应 |
| sum of squares (SS) | 平方和 | 各离差平方后求和，用一个数概括变异的大小 |
| total sum of squares ($SS_{tot}$) | 总平方和 | 全部观测值对总均值的平方离差之和 |
| treatment / between-group sum of squares ($SS_{treat}$) | 处理平方和 / 组间平方和 | 被分组解释掉的那部分变异 |
| error / within-group sum of squares ($SS_{err}$) | 误差平方和 / 组内平方和 | 分组之后仍未被解释的变异；此处 "error" 不指研究者犯错 |
| partitioning variability | 变异的分解 | 把总变异拆成组间与组内两部分：$SS_{tot}=SS_{treat}+SS_{err}$ |
| degrees of freedom (Df) | 自由度 | 组间 = $k-1$；组内（残差）= $n-k$ |
| Mean Square (MS) | 均方 | 平方和除以自由度，是方差的估计 |
| F-statistic | F 统计量 | 处理均方 ÷ 残差均方；越大表示分组解释力越强 |
| F-distribution | F 分布 | 原假设为真时 F 统计量服从的分布，用来算 p 值 |
| Pr(>F) | F 检验的 p 值 | ANOVA 表最后一栏，纯靠运气得到这么大 F 的概率 |
| Residuals | 残差（行） | ANOVA 表中代表组内/未解释部分的那一行 |
| main effect | 主效应 | 某个预测变量自身的效应（不含交互） |
| interaction | 交互作用 | 一个预测变量的效应依赖于另一个预测变量的取值 |
| sequential (Type I) sums of squares | 序贯平方和 | `aov()` 使用的分配方式：每项只分到左侧各项解释完后剩下的变异 |
| controlling for | 控制（某变量） | 在扣除某变量所解释的变异之后再评估目标变量 |
| forcing a predictor into the model | 强制保留预测变量 | 尽管本次数据不显著，仍基于先验知识把某变量留在模型中 |
| power | 检验力 | 真有效应时能检测出它的能力；解释掉噪声可提高检验力 |
| robust | 稳健 | 假设被适度违反时结论仍大致可靠；ANOVA 对正态性和方差不齐都较稳健 |
| normality (of within-group error) | （组内误差的）正态性 | ANOVA 假设之一：每组内部观测围绕该组均值正态分布 |
| equal variance / homoscedasticity | 方差齐性 | ANOVA 假设之二：各组组内变异大致相同；拇指规则是最大方差不超过最小的约 4 倍 |
| Welch's correction | Welch 校正 | 不假定方差相等的 ANOVA；R 中为 `oneway.test()` |
| Games-Howell test | Games-Howell 检验 | 方差不齐时替代 Tukey 的事后检验；见 R 包 `rstatix` |
| Kruskal-Wallis test | Kruskal-Wallis 检验 | 非正态时替代单因素 ANOVA 的基于秩的检验；检验平均秩而非均值 |
| Dunn's test | Dunn 检验 | Kruskal-Wallis 对应的事后检验；由 Olive Jean Dunn 提出，见 R 包 `dunn.test` |
| Benjamini-Yekutieli method | Benjamini-Yekutieli 方法 | Dunn 检验中一种多重比较校正方法；`method="by"` |
| Wilcoxon test | Wilcoxon 检验 | 两组情形下基于秩的非参数检验（上周内容） |
| rank | 秩 | 观测值按大小排序后的名次 |
| superiority | 优势性 | Wilcoxon 类检验的直观含义：随机取一对，来自某组的那个更大的概率 |
| ties | 并列值 | 数据中出现相同数值；会使 Wilcoxon 无法解析计算精确 p 值 |
| exponential distribution | 指数分布 | 等待时间类数据（如交配延迟）常见的右偏分布 |
| Monte Carlo test | 蒙特卡洛检验 | 通过随机重排分组标签构造零分布的检验；极其灵活但需大量编程 |
| nonparametric test | 非参数检验 | 不依赖对分布参数（均值、方差）估计的检验 |
| null distribution | 零分布 | 原假设为真时检验统计量的分布 |
| HARKing (Hypothesizing After the Results are Known) | 事后编造假设 | 看到结果后才提出「假设」，会使 p 值失去原有含义 |
| effect size | 效应量 | 差异的实际大小（如「重 694 kg」），与 p 值同等重要 |
| marginally significant | 边缘显著 | p 略大于 0.05（如 0.08）时的说法，结论应视为 inconclusive |
| box-and-whiskers plot / box plot | 箱线图 | 展示中位数、四分位数、须与离群点的图；由 John Tukey 发明 |
| median | 中位数 | 箱线图中盒内的粗线；对极端值不敏感 |
| standard error (SE) | 标准误 | 条形图误差条采用的量，反映均值估计的不确定性 |
| figure legend / caption | 图注 | 让读者不看正文也能读懂该图的说明文字 |
| genus / genera | 属（复数） | 一组亲缘关系密切的物种 |
| monophyletic | 单系的 | 一个类群包含某共同祖先的全部且仅有的后代 |
| sexual dimorphism | 性二态 | 同一物种雌雄个体在形态上的系统性差异 |
| anurans | 无尾类 | 蛙与蟾蜍所属的类群 |
| snout-vent length (SVL) | 吻肛长 | 从吻端到泄殖腔的长度；受标本姿势影响，变异较大 |
| femur length | 股骨长 | 最大腿骨的长度；因是骨骼，测量稳定，标本干缩也不变 |
| `aov()` | — | R 中拟合方差分析模型的函数 |
| `summary()` | — | 打印模型摘要（ANOVA 表） |
| `TukeyHSD()` | — | 对 aov 对象做事后 Tukey 检验 |
| `oneway.test()` | — | 带 Welch 校正的单因素均值分析 |
| `kruskal.test()` | — | Kruskal-Wallis 检验 |
| `boxplot()` | — | 绘制箱线图；语法 `boxplot(y~x, data=, ylab=)` |
| `aggregate()` | — | 按分组对某变量施加一个函数，如 `aggregate(weight~feed, data=chickwts, var)` 逐组求方差 |
| `ave()` | — | 按分组求均值并广播回每个个体，用于手算平方和 |
| `read.csv()` | — | 读入 csv；`header=TRUE` 表示首行是列名 |
| `nrow()` | — | 返回数据框行数，用于校验导入 |
| `unique()` | — | 列出向量中所有不重复的取值；可用于查看因子水平和排查录入错别字 |
| `!=` | 不等于 | R 中的「不等于」运算符，方便取补集 |
| `~` (tilde) | 波浪号 | 公式语法：左为响应变量、右为预测变量，读作 "depends on" |
| `setwd()` | — | 设置工作目录；建议写进脚本以便日后复现 |
| `View()` | — | 在表格窗口中查看数据框 |
