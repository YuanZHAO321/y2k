# Week 3 — 数值预测变量的效应：线性回归 (Linear Regression)

> 课程：EART11200 The Natural Scientist's Toolkit — Statistics for Natural Scientists
> 讲师：Tucker Gilman (tucker.gilman@manchester.ac.uk)
> 本周材料：Lecture 3.1 / 3.2 (slides + 22-Nov 课堂转写)、Practical 4 (+ answer key)、Handbook Chapter 4「Understanding the effects of numerical predictors」

---

## 一、本周主题

本周从「**分类预测变量**」正式转向「**数值预测变量**」，学习 **线性回归 (linear regression)**：当预测变量 (predictor) 是连续数值（如受教育年数、光照强度、股骨长度）而不是分组标签时，如何检验它与数值响应变量 (response variable) 之间是否存在关系、关系有多强、方向如何。

在全课 6 周的主线（按「预测变量类型 × 响应变量类型」组织）中的位置：

| 周次 | 预测变量 | 响应变量 | 方法 |
|---|---|---|---|
| Week 01 | 分类（2 组） | 数值 | t 检验 (t-test) / Wilcoxon |
| Week 02 | 分类（≥3 组、多因子） | 数值 | ANOVA / Kruskal–Wallis / Tukey |
| **Week 03（本周）** | **数值（也可含二分类）** | **数值** | **线性回归 (lm)** / Spearman、Kendall 秩相关 |
| Week 04 | 分类 | 分类 | 卡方检验 (χ²) |
| Week 05 | 数值 | 分类（二值） | 逻辑回归 (logistic regression) |
| Week 06 | 任意（数据非独立） | 任意 | 混合效应模型 (mixed effects models) |

本周的核心洞察是：**线性回归是 t 检验和 ANOVA 的推广**。用指示变量 (indicator) 可以把分类预测变量塞进回归，因此回归能一次性处理「多个预测变量 + 它们之间的交互作用」，这是 t 检验做不到的。本周还建立了整门课最重要的一项工程技能：**多元模型的构建、化简（backward selection）与规范报告**。

**贯穿全章的数据集**：1994 年加拿大安大略省劳动力与收入动态调查 (Canadian Survey of Labour and Income Dynamics)，文件 `can_inc.csv`，100 名工人。列包括：

| 列名 | 含义 | 类型 |
|---|---|---|
| `wage` | 时薪（加元 C$/h）——**响应变量** | 连续数值 |
| `age` | 年龄（岁） | 连续数值 |
| `sex` | 自报性别 `m`/`f` | 二分类 |
| `lang` | 母语 `english`/`other` | 二分类 |
| `apt` | 「学术能力倾向」academic aptitude | 连续数值（**注意：这一列是 Gilman 编造的假数据**，专门用来演示共线性） |
| `school` | 受过的正规教育年数 | 连续数值 |

> **关于 `sex` 一列的伦理提醒（手册与 slides 都专门强调）**：1994 年的问卷强制受访者在 male/female 之间二选一，这叫 **coercive gendering（强制性别化）**，会损失人群信息；而且当年多数人并不区分 sex 与 gender，我们无从知道受访者报告的到底是生理性别还是社会性别。我们只能说「这一列记录的是受访者自报的 sex」。即便如此，它仍能回答一些有意思的问题。

---

## 二、核心概念

### 2.1 为什么不能把数值预测变量硬切成分类变量

手册开篇的例子：想研究雄性马鹿 (*Cervus canadensis*) 后宫中雌鹿数量如何依赖体型。体型是连续变化的，没有天然的分组界限。如果人为按均值切成「小 / 大」两组，就**丢掉了组内个体的精确体型信息**——组内一只刚好比均值大 0.1 kg 的鹿和一只大 50 kg 的鹿被当成同一类。所以我们需要一种**用尽全部信息**的方法：线性回归。

### 2.2 简单线性回归 (simple linear regression) 与最小二乘 (least squares)

**模型形式**：

$$y_i = \beta_0 + \beta_1 x_i + \varepsilon_i$$

- $y_i$：第 $i$ 个个体的响应变量观测值（如时薪）
- $x_i$：第 $i$ 个个体的预测变量观测值（如教育年数）
- $\beta_0$：**截距 (intercept)**，即 $x=0$ 时 $y$ 的预测值
- $\beta_1$：**斜率 (slope)**，也就是这门课里说的**效应量 (effect size)**：$x$ 每增加 1 个单位，$y$ 预期变化多少
- $\varepsilon_i$：**误差项 / 残差 (residual, error)**，第 $i$ 点没被直线解释掉的部分，假定 $\varepsilon_i \sim N(0,\sigma^2)$ 且相互独立

**残差的定义**：

$$e_i = y_i - \hat{y}_i = y_i - (\hat\beta_0 + \hat\beta_1 x_i)$$

即「实际观测值 − 直线预测值」，在图上就是从数据点垂直落到回归线上的那一段（手册 figure 4.2 里的蓝线）。

**最小二乘法 (ordinary least squares, OLS)**：**最佳拟合线 (line of best fit)** 就是使**残差平方和**最小的那条线：

$$\text{SS}_{\text{res}} = \sum_{i=1}^{n} e_i^2 = \sum_{i=1}^{n}\left(y_i - \beta_0 - \beta_1 x_i\right)^2 \;\longrightarrow\; \min$$

**为什么是平方而不是绝对值？** 平方使正负偏差不相互抵消，且大偏差被惩罚得更重；同时平方函数可微，能解析求解。

**推导**（对 $\beta_0$、$\beta_1$ 求偏导并令其为零）：

$$\frac{\partial \text{SS}_{\text{res}}}{\partial \beta_0} = -2\sum\left(y_i - \beta_0 - \beta_1 x_i\right) = 0 \quad\Rightarrow\quad \hat\beta_0 = \bar{y} - \hat\beta_1 \bar{x}$$

$$\frac{\partial \text{SS}_{\text{res}}}{\partial \beta_1} = -2\sum x_i\left(y_i - \beta_0 - \beta_1 x_i\right) = 0$$

把 $\hat\beta_0 = \bar y - \beta_1\bar x$ 代入第二式整理得：

$$\boxed{\;\hat\beta_1 = \frac{\sum_{i}(x_i-\bar{x})(y_i-\bar{y})}{\sum_{i}(x_i-\bar{x})^2} = \frac{S_{xy}}{S_{xx}} = \frac{\operatorname{cov}(x,y)}{\operatorname{var}(x)}\;}$$

$$\boxed{\;\hat\beta_0 = \bar{y} - \hat\beta_1\bar{x}\;}$$

**两个重要推论**（考试爱考）：
1. 回归线**必然经过点 $(\bar x, \bar y)$**（由 $\hat\beta_0$ 的公式直接可得）。
2. 斜率 = 协方差 / 预测变量的方差，因此斜率的符号 = 协方差的符号 = 相关系数的符号。

### 2.3 显著性从哪里来：与 ANOVA 完全相同的「解释 vs 未解释」思想

**关键问题**（Gilman 在 slides 中反复强调）：**任何一团点云都能画出一条最佳拟合线，哪怕这些点是完全随机生成的**。那条线几乎总有一点斜率，几乎总能解释掉一点变异。所以真正要问的是：

> 「**如果总体中预测变量与响应变量真的毫无关系，我们仅凭偶然抽样，看到一条至少像现在这么强的最佳拟合线的概率是多少？**」

这就是频率主义统计的根本问题。回答办法与 ANOVA 一模一样：**把「被回归线解释的变异」和「没被解释的变异」相比**。

参考手册 figure 4.3 / slides Slide 5 的三条线：
- **黑色水平线** = 全体的均值 $\bar y$。如果预测变量毫无作用，我们对每个人的最佳预测就是这条均值线。
- **红色斜线** = 最佳拟合线。如果预测变量有作用，这是最佳预测。
- 对任一数据点：
  - **绿色竖线** $= \hat y_i - \bar y$：偏离均值中**被回归线解释掉**的那部分。
  - **蓝色竖线** $= y_i - \hat y_i$：**未被解释**的那部分（残差）。

**平方和分解 (sum of squares decomposition)**：

$$\underbrace{\sum(y_i-\bar y)^2}_{\text{SS}_{\text{tot}}\;\text{总变异}} = \underbrace{\sum(\hat y_i-\bar y)^2}_{\text{SS}_{\text{reg}}\;\text{回归解释的（绿）}} + \underbrace{\sum(y_i-\hat y_i)^2}_{\text{SS}_{\text{res}}\;\text{残差（蓝）}}$$

若「解释的」相对于「未解释的」足够大，就不太可能只是运气。这个比值在零假设下服从已知的 **F 分布**，据此算出 p 值。

**Slide 6 的随机化直觉（很好的心智模型）**：Gilman 把原始数据里所有 wage 打乱，随机重新分配给不同教育年数的人，此时数据中教育与工资已无任何关系。均值不变（因为工资集合没变），但最佳拟合线明显变平，被解释的变异比例变小。如果**真实数据中被解释的变异，几乎总是比这些随机化版本大**，那么真实数据里的模式很可能不是偶然的。—— 实际上我们不用真去做几千次随机化，R 用 F 分布直接算。

### 2.4 在 R 中做线性回归

```r
# 读入数据
ci = read.csv("can_inc.csv", header = TRUE)   # header=TRUE 表示第一行是列名
head(ci)     # 只显示前 6 行，避免刷屏（lecture 中用 head 而不是直接打 ci）

# 先画散点图看看有没有模式
plot(ci$school, ci$wage,
     xlab = "years of education",     # x 轴标签
     ylab = "hourly wage in C$")      # y 轴标签
# 注意：plot 的第 1 个参数是 x（预测变量），第 2 个是 y（响应变量）

# 拟合线性模型
s.lm = lm(wage ~ school, data = ci)
# lm  = linear model
# wage ~ school ：波浪号 ~ 左边是【响应变量】，右边是【预测变量】
# data = ci    ：告诉 R 到数据框 ci 里去找 wage 和 school 这两个向量
# s.lm         ：给拟合出来的模型起的名字（对象）

summary(s.lm)   # 查看结果
```

**⚠️ 极易错的语法陷阱（Practical 4 专门警告）**：
- `plot(x, y, ...)`：**预测变量在前**（因为要放 x 轴），响应变量在后。
- `lm(y ~ x, ...)`：**响应变量在前**（因为公式 `y ~ x` 读作「y 如何依赖 x」）。
- **两者顺序是反的！搞错了结果就全错。**

### 2.5 读懂 `summary(lm)` 的每一栏

```
Call:
lm(formula = wage ~ school, data = ci)

Residuals:
    Min      1Q  Median      3Q     Max
-10.406  -5.193  -1.107   3.687  24.613

Coefficients:
            Estimate Std. Error t value Pr(>|t|)
(Intercept)   3.0277     3.2303   0.937 0.350924
school        0.9057     0.2313   3.916 0.000166 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 6.883 on 98 degrees of freedom
Multiple R-squared:  0.1353,	Adjusted R-squared:  0.1265
F-statistic: 15.34 on 1 and 98 DF,  p-value: 0.0001664
```

逐栏解释：

| 栏目 | 含义 | 本例读法 |
|---|---|---|
| **Call** | 回显你拟合的公式，确认没写错 | `wage ~ school` |
| **Residuals** 五数概括 | 残差的 Min / 1Q / Median / 3Q / Max。**快速诊断**：Median 应接近 0；1Q 与 3Q 应大致对称 | Median = −1.107，Max = 24.6 而 Min = −10.4 → **明显右偏**，残差不对称，暗示正态性可能有问题 |
| **Estimate**（`(Intercept)` 行） | 截距 $\hat\beta_0$：所有预测变量 = 0 时响应的预测值 | 无任何正规教育的人预期时薪 C$3.03 |
| **Estimate**（`school` 行） | **效应量 (effect size) $\hat\beta_1$ = 斜率**。单位 = 响应变量单位 / 预测变量单位 | 每多受 1 年教育，时薪预期多 **C$0.9057 h⁻¹ y⁻¹** |
| **Std. Error** | 该系数估计的**标准误**，衡量估计的不确定度。样本越大、残差越小、预测变量越分散 → 标准误越小 | 0.2313 |
| **t value** | $t = \dfrac{\hat\beta}{\text{SE}(\hat\beta)}$，检验「该系数 = 0」的统计量 | $0.9057/0.2313 = 3.916$ |
| **Pr(>\|t\|)** | 该系数对应的**双尾 p 值**：若真实系数为 0，看到这么大（或更大）\|t\| 的概率 | 0.000166 → 极显著，教育与工资的关系不太可能是偶然 |
| **Signif. codes** | 星号约定：`***` p<0.001，`**` p<0.01，`*` p<0.05，`.` p<0.1 | `***` |
| **Residual standard error** | 残差标准误 $\hat\sigma = \sqrt{\text{SS}_{\text{res}}/(n-p-1)}$，即典型预测误差的大小，单位与响应变量相同 | 6.883 C$/h；自由度 $98 = 100 - 2$ |
| **Multiple R-squared** | $R^2$：预测变量解释掉的响应变量总变异比例 | 0.1353 → 教育只解释了工资变异的 **13.53%** |
| **Adjusted R-squared** | 对预测变量个数做惩罚后的 $R^2$（多加变量必然抬高 $R^2$，调整后的不会） | 0.1265 |
| **F-statistic + p-value** | **整体模型**的检验：所有预测变量合起来是否比「只用均值预测」更好。简单回归中它的 p 值与斜率的 p 值完全相同 | F = 15.34，df = (1, 98)，p = 0.000166 |

**$R^2$ 是不是「太低了」？** Gilman 的答案：**取决于研究目的**。
- 若目的只是**证明工资随教育上升**（做推断），$R^2$ 低无所谓，小 p 值 + 正效应量就够了。
- 若目的是**用教育预测某人的工资**（做预测），$R^2 = 0.135$ 意味着预测会很不准——有人教育少却挣得多，有人教育多却挣得少。

### 2.6 均值中心化 (mean centring) ★本章关键概念★

**问题**：原始模型的截距 C$3.03 是「零年教育者的预期时薪」，但这个数**毫无用处**：
1. 数据集中**没有人**教育年数为 0（加拿大法定至少 8 年义务教育）。
2. **在观测范围之外用模型做预测（外推 extrapolation）是坏习惯**——我们没有证据说模型在那里还成立。
3. 加拿大有最低工资法，C$3.03 事实上**不可能**成立。
4. 对 `age` 这样的预测变量问题更荒谬：「年龄为 0 时的预期工资」——0 岁的人根本不工作！

**做法**：把每个观测值减去该变量的样本均值。

$$x_i^{\text{mc}} = x_i - \bar{x}$$

```r
mc_school = ci$school - mean(ci$school)   # 每个人的教育年数减去总体均值
mc_school
# [1] 1.353 -0.447 0.353 2.353 1.353 -0.147 -1.647 0.353 ...

# 想直观对照两列，可以并排显示（lecture 里的做法）
data.frame(ci$school, mc_school)
```

中心化后：均值教育者 = 0；高于均值 = 正值；低于均值 = 负值。本数据集平均教育约 **13.65 年**，所以 `mc_school = school − 13.65`。

**重新拟合**：

```r
s.lm = lm(wage ~ mc_school, data = ci)
summary(s.lm)
```

```
Coefficients:
            Estimate Std. Error t value Pr(>|t|)
(Intercept)  15.3875     0.6883  22.356  < 2e-16 ***
mc_school     0.9057     0.2313   3.916 0.000166 ***

Residual standard error: 6.883 on 98 degrees of freedom
Multiple R-squared:  0.1353,	Adjusted R-squared:  0.1265
F-statistic: 15.34 on 1 and 98 DF,  p-value: 0.0001664
```

**中心化前后对比（必须记牢）**：

| 量 | 是否改变 | 说明 |
|---|---|---|
| 斜率 / 效应量 $\hat\beta_1$ | **不变**（0.9057） | 只是平移 x 轴，线的倾斜程度没变 |
| 斜率的 p 值 | **不变**（0.000166） | |
| $R^2$、Adjusted $R^2$ | **不变**（0.1353） | 拟合优度不受平移影响 |
| Residual standard error、F 统计量 | **不变** | |
| **截距 $\hat\beta_0$** | **改变**：3.0277 → **15.3875** | 含义从「零教育者的工资」变成「**平均教育者的工资**」 |
| 截距的标准误与 p 值 | 改变（3.23 → 0.688；0.35 → <2e-16） | 中心化后截距估计精度大幅提高 |
| 图形 | 只有 x 轴刻度数字变了（整体减去均值），点与线的形状完全一样 | |

**为什么截距会变成 $\bar y$？** 数学上一句话就能证明：中心化后 $\bar{x}^{\text{mc}} = 0$，代入 $\hat\beta_0 = \bar y - \hat\beta_1 \bar{x}^{\text{mc}}$ 得

$$\hat\beta_0^{\text{mc}} = \bar{y} - \hat\beta_1 \times 0 = \bar{y}$$

即**简单回归中心化后的截距恰好等于响应变量的样本均值**（本例 15.3875 = 100 名工人的平均时薪）。几何上：y 轴（$x=0$ 的竖线）被平移到了总体均值处，而回归线必过 $(\bar x, \bar y)$，所以交点纵坐标就是 $\bar y$。

**中心化后截距的 p 值 < 2e-16 意味着什么？** 意味着「平均教育者的预期时薪显著不等于 0」——这本身**是个毫无意义的结论**（谁会怀疑工人时薪不为零？）。Gilman 提醒：截距的 p 值往往不值得报告。

**是否总要中心化？** 不是必须的。但当截距本身没有可解释含义、或需要在含交互作用的模型中解释主效应时，中心化能让输出**大大更好读**。**画图给读者看时**，用未中心化的原始变量更直观（读者不习惯看到「−2 年教育」），可以先用中心化模型解释、再用原始模型作图（手册 code 4.12–4.13 就是这样做的）。

### 2.7 二分类预测变量与指示变量 (indicator / dummy variable)

**破除误解**：Gilman 明确说「有人告诉你线性回归的预测变量必须是连续变量，**这是胡说 (nonsense)**」。离散变量、二分类变量都可以做预测变量——**唯一的要求是它必须是数字**。

**做法**：造一个**指示变量 (indicator)**，取值只有 0 和 1。

```r
# 写法一（手册 code 4.8，分两步，逻辑最清楚）
male = rep(1, length(ci$sex))        # rep(1, n) 生成 n 个 1，长度与 ci$sex 相同
male[which(ci$sex == "f")] = 0       # which(...) 找出所有 sex=="f" 的位置，把它们改成 0

# 写法二（lecture 与 practical 用的，更简洁 —— 推荐）
male = as.numeric(ci$sex == "m")
# ci$sex == "m" 返回一个逻辑向量：是 m 的位置 TRUE，其余 FALSE
# as.numeric() 把 TRUE 转成 1、FALSE 转成 0

# 检查是否成功：并排显示
data.frame(ci$sex, male)
```

> Practical 4 中的写法把结果直接写回数据框：`inc.lue$male = as.numeric(inc.lue$sex == "M")`。写成 `inc.lue$male` 而不是 `male`，是告诉 R 把这个新向量**加进数据框**，之后 `data=inc.lue` 就能找到它。
>
> Gilman 的吐槽：当然你也可以在 Excel 里手动敲一列 0/1，但「能让 R 干活，我们为什么要自己干？」

**拟合与解读**：

```r
s.lm = lm(wage ~ male, data = ci)
summary(s.lm)
```

```
Coefficients:
            Estimate Std. Error t value Pr(>|t|)
(Intercept)   12.865      1.139  11.290  < 2e-16 ***
male           4.135      1.459   2.835  0.00557 **

Residual standard error: 7.116 on 98 degrees of freedom
Multiple R-squared:  0.07578,	Adjusted R-squared:  0.06635
F-statistic: 8.035 on 1 and 98 DF,  p-value: 0.005573
```

- `(Intercept) = 12.865`：预测变量 = 0 时的响应。`male = 0` 代表女性 → **女性预期时薪 C$12.87/h**。这里被编码为 0 的类别称为 **基线 (baseline)**。
- `male = 4.135`：**「一个单位的男性度 (one unit of maleness)」的效应**。由于男 = 1、女 = 0，一个单位就是男女之差 → **男性比女性每小时多挣 C$4.135**。
- 男性预期时薪 = 12.865 + 4.135 = **C$17.00/h**。
- p = 0.00557 → 性别确实预测收入。

> Gilman 的立场声明（slides 明确写出）：「我并不是在论证这个工资差距是对的或好的。恰恰相反，这说明存在一个问题。但社会必须先知道问题存在才能解决它，而科学的一部分职责就是证明问题存在。」

**作图**：

```r
plot(male, ci$wage,
     xlab = "sex", ylab = "wage in C$/h",
     xaxt = "n")                          # xaxt="n" 关掉自动生成的 x 轴
axis(1, at = 0:1, labels = c("female", "male"))
# axis(side=1 表示底部 x 轴, at= 刻度位置, labels= 刻度文字)
abline(s.lm, col = "red")                 # 添加最佳拟合线
```

### 2.8 多元线性回归 (multiple linear regression) 与「控制」

**为什么需要它？**（Gilman 在 slides 12 里的关键论证）
既然 t 检验也能比较两组均值，为什么要用回归？**因为回归能同时研究多个预测变量。** 这在**调查研究 (survey studies)** 里尤其重要，因为调查样本常常**不平衡 (unbalanced)**：也许我们这个数据集里男性恰好受教育更多，那么「男女工资差异」可能根本不是性别造成的，而只是因为男性教育更多。要理清这一点，就必须在**控制一个变量的同时**研究另一个变量的效应。

**统计功效的角度（手册的论证）**：所有方法都靠「被解释的变异 / 未被解释的变异」这个比值来检测效应。如果响应变量确实依赖多个预测变量，**把所有重要的预测变量都放进模型**就能解释更多变异、减少未解释变异、抬高这个比值，从而**提高检验的统计功效 (power)**。

**模型形式**：

$$y_i = \beta_0 + \beta_1 x_{1i} + \beta_2 x_{2i} + \cdots + \beta_k x_{ki} + \varepsilon_i$$

每个 $\beta_j$ 的含义是：**在其他所有预测变量保持不变时**，$x_j$ 每增加 1 单位，$y$ 的预期变化量。这就是「**独立于其他预测变量的效应量**」，也叫**主效应 (main effect)**。

**R 代码**：只需用 `+` 加项。

```r
s.lm = lm(wage ~ mc_school + male, data = ci)
summary(s.lm)
```

```
Coefficients:
            Estimate Std. Error t value Pr(>|t|)
(Intercept)  12.7949     1.0555  12.123  < 2e-16 ***
mc_school     0.9199     0.2215   4.153 7.05e-05 ***
male          4.2502     1.3515   3.145  0.00221 **

Residual standard error: 6.59 on 97 degrees of freedom
Multiple R-squared:  0.2153,	Adjusted R-squared:  0.1991
F-statistic: 13.31 on 2 and 97 DF,  p-value: 7.81e-06
```

**逐项解读（★多元回归中效应量的独立解释★）**：

- `mc_school = 0.9199`：**在性别相同的前提下**，每多 1 年教育，时薪多 C$0.92。
- `male = 4.2502`：**在教育年数相同的前提下**，男性比女性每小时多挣 C$4.25。这叫「**控制教育后的性别效应 (the effect of sex controlling for education)**」。
- `(Intercept) = 12.7949`：所有预测变量都为 0 的人，即「一位**平均教育水平的女性**」（`male=0` 且 `mc_school=0`），预期时薪 C$12.79。**这正是中心化的价值所在**——如果不中心化，截距就变成「零教育女性」这个荒谬的对象（见 code 4.13 中截距变成 0.2408）。
- **p 值比两个简单回归都更小了**（0.000166 → 7.05e-05；0.00557 → 0.00221）：因为模型解释了更多变异，未解释变异从 6.883 降到 6.59，我们对这两个关系更有把握了。
- $R^2$ 从 0.1353 / 0.0758 升到 **0.2153**：两个预测变量合起来解释了 21.5% 的变异。

**★极其重要的一条：`lm()` 对预测变量的顺序不敏感★**
手册明确指出：「与第 3 章的 `aov` 函数不同，`lm` 函数对预测变量加入的顺序不敏感。」课堂转写里 Gilman 也再次强调（讲完 ANOVA 顺序问题后）：「**这在我们的回归模型里不会再出现，因为回归模型的设置使得顺序无关紧要，但 ANOVA 是有关系的。**」原因是 `lm` 报告的每个系数**天然就是控制了其余所有预测变量之后的效应**（相当于 Type III / 偏效应），而 `aov` 默认用序贯（Type I）平方和。

**多元模型的可视化（含 0/1 指示变量 → 两条平行线）**：

为了画图好懂，先用原始（未中心化）的 `school` 重建模型：

```r
s.lm = lm(wage ~ school + male, data = ci)
summary(s.lm)
```

```
Coefficients:
            Estimate Std. Error t value Pr(>|t|)
(Intercept)   0.2408     3.2175   0.075  0.94050
school        0.9199     0.2215   4.153 7.05e-05 ***
male          4.2502     1.3515   3.145  0.00221 **
```

注意：**换成原始变量后，效应量与 p 值一个都没变，只有截距变了**（12.79 → 0.24，因为 0 又回到了「零教育」）。

```r
plot(ci$school, ci$wage, col = "blue",
     xlab = "years of education", ylab = "wage in C$/h")
# 第 1 行：先把所有点画成蓝色

points(ci$school[which(ci$sex == "f")],
       ci$wage[which(ci$sex == "f")], col = "red")
# 第 2 行：把女性的点【覆盖】成红色 → 最终男蓝女红

abline(0.2408, 0.9199, col = "red")
# 第 3 行：女性的最佳拟合线。abline(c, m) 画 y = m x + c，
#          第 1 个参数是截距，第 2 个是斜率
#          女性截距 = 模型截距 0.2408，斜率 = 0.9199

abline(0.2408 + 4.2502, 0.9199, col = "blue")
# 第 4 行：男性的线。男性截距 = 女性截距 + 男性效应；斜率仍是 0.9199
```

结果是 **两条平行线**（图 4.5）：斜率相同（教育对两性效应一样），截距相差 4.25（性别的恒定加成）。**没有交互作用时，指示变量只平移直线、不改变斜率。**

**扩展到 4 个预测变量**：

```r
mc_age = ci$age - mean(ci$age)                  # 年龄中心化

english = rep(1, length(ci$lang))               # 造母语指示变量
english[which(ci$lang == "other")] = 0          # 非英语母语记 0

s.lm = lm(wage ~ mc_school + mc_age + male + english, data = ci)
summary(s.lm)
```

```
Coefficients:
            Estimate Std. Error t value Pr(>|t|)
(Intercept) 11.45168    1.82344   6.280 1.01e-08 ***
mc_school    0.91607    0.20982   4.366 3.22e-05 ***
mc_age       0.21851    0.05029   4.345 3.49e-05 ***
male         5.24222    1.26863   4.132 7.74e-05 ***
english      0.86832    1.75479   0.495    0.622

Residual standard error: 6.081 on 95 degrees of freedom
Multiple R-squared:  0.3456,	Adjusted R-squared:  0.3181
F-statistic: 12.54 on 4 and 95 DF,  p-value: 3.108e-08
```

解读：
- 截距 11.45 = **母语非英语 (english=0)、平均年龄 (mc_age=0)、平均教育 (mc_school=0) 的女性 (male=0)** 的预期时薪。（**所有预测变量同时为 0 的那个人**）
- 教育每多 1 年 +C$0.92/h；年龄每大 1 岁 +C$0.22/h；同龄同教育下男性比女性 +C$5.24/h。
- `english` 的 p = 0.622 → 虽然数据里英语母语者挣得多一点，但这个差异很容易由偶然造成，**我们没有证据表明母语影响时薪**。

### 2.9 交互作用 (interactions) ★本章第二个难点★

**定义**：当**一个预测变量对响应变量的效应，取决于另一个预测变量的取值**时，我们说这两个预测变量之间存在**交互作用**。

> Practical 4 的严厉提醒：「**小心这个词：交互作用是发生在预测变量之间的。预测变量与响应变量之间的关系不叫交互作用！**」

**方向的命名**：
- 若一个预测变量的效应随另一个变量增大而**减弱** → **负交互作用 (negative interaction)**
- 若**增强** → **正交互作用 (positive interaction)**

**举例（手册的猜想）**：教育对时薪的效应可能依赖年龄。年轻时雇主没什么别的可评价，教育很重要；年长后雇主能看工作履历，教育就没那么重要了。若真如此，就是教育 × 年龄的**负**交互作用。

**R 语法**：用乘号 `*` 加一个乘积项。

```r
s.lm = lm(wage ~ mc_school + mc_age + male + english + mc_age*mc_school, data = ci)
summary(s.lm)
```

```
Coefficients:
                 Estimate Std. Error t value Pr(>|t|)
(Intercept)      11.41374    1.81013   6.305 9.28e-09 ***
mc_school         0.81517    0.21814   3.737  0.00032 ***
mc_age            0.23897    0.05162   4.630 1.17e-05 ***
male              5.21140    1.25941   4.138 7.63e-05 ***
english           0.95848    1.74279   0.550  0.58364
mc_school:mc_age  0.02982    0.01917   1.556  0.12315
```

输出中 **`mc_school:mc_age`**（冒号）这一行就是交互作用项。p = 0.1232 → **没有证据**支持年龄与教育之间存在交互作用。

**含指示变量的交互作用（更重要、更常考）**：

```r
s.lm = lm(wage ~ mc_school + mc_age + male + english
                 + mc_age*mc_school + mc_age*male, data = ci)
summary(s.lm)
```

```
Coefficients:
                 Estimate Std. Error t value Pr(>|t|)
(Intercept)      12.78174    1.73361   7.373 6.77e-11 ***
mc_school         0.80202    0.20431   3.926 0.000166 ***
mc_age            0.03816    0.07197   0.530 0.597183
male              4.90329    1.18223   4.147 7.42e-05 ***
english           0.01197    1.65130   0.007 0.994231
mc_school:mc_age  0.03079    0.01795   1.715 0.089657 .
mc_age:male       0.35812    0.09508   3.766 0.000290 ***

Residual standard error: 5.653 on 93 degrees of freedom
Multiple R-squared:  0.4465,	Adjusted R-squared:  0.4108
F-statistic:  12.5 on 6 and 93 DF,  p-value: 2.748e-10
```

**★★ 含交互作用时如何解释主效应（本周最容易出错的地方）★★**

**总规则**：**当模型中含有交互作用时，某个预测变量的「主效应」是在与它交互的那个变量 = 0 时估计的。**

具体到这个模型：
- `male` 是指示变量，女性编码为 0，所以女性是**基线 (baseline)**，男性相对基线做比较。
- **`mc_age = 0.03816, p = 0.5972`**：这是**基线性别（即女性）中年龄的效应**。p 值很大 → **我们没有证据表明年长女性比年轻女性挣得多**。
- **`mc_age:male = 0.35812, p = 0.00029`**：这是**男性的年龄效应相对女性差出多少**。显著为正 → 年长男性确实比年轻男性挣得多。
- **男性的实际年龄效应 = 基线效应 + 交互项 = 0.03816 + 0.35812 = C$0.39128 h⁻¹ y⁻¹**。
  （**必须相加！交互项本身不是男性的斜率，而是「男性斜率 − 女性斜率」的差。**）
- **`male = 4.90329`**：由于 `male` 与 `mc_age` 有交互作用，这个主效应是在 `mc_age = 0`（**平均年龄**）时估计的 → **同为平均年龄、平均教育的男性比女性每小时多挣 C$4.90**。
- `mc_school = 0.80202`：`school` 没有和 `male` 交互（与 `mc_age` 的交互不显著），所以可解释为：任一性别的工人每多 1 年教育，时薪多 C$0.80。
- `english` p = 0.9942 → 仍无母语效应。
- `mc_school:mc_age = 0.03079, p = 0.0897`：**弱证据**支持教育与年龄的正交互作用——与前面的猜想相反，教育可能随年龄增长而**更**值钱。但证据很弱，解释要极其谨慎。

**Slides 中一个略有不同的最终模型**（先剔除了 `english`、`mc_school:mc_age`，模型为 `wage ~ mc_school + mc_age + male + mc_age*male`）：Gilman 报告女性年龄效应约 1.8 分/小时/年（不显著），男性额外 35.5 分 → 男性总计约 37.4 分/小时/年；`male` 主效应约 C$4.94；教育约 C$0.90/年。**数值随模型不同会略有变化，但解释逻辑完全一致。**

**Slides 里非常精彩的一段社会解读（Slide 21）**：图中年轻男女工资差不多，但年长男性远高于年长女性。有两种可能：(a) 问题已部分解决——年轻一代男女同酬，随着他们变老工资会同步上涨，这个模式会消失；(b) 问题持续存在——男女起薪相同，但男性被提拔而女性没有。**这份数据本身无法区分这两种可能**。但 Gilman 指出：这份数据已经 25 年以上了，如果是 (a)，模式今天应该基本消失了；然而我们在包括曼彻斯特大学在内的许多大机构仍能看到非常相似的模式（高薪领导岗位中男性远多于女性）。

### 2.10 模型选择：后向选择 (backward selection)

**问题**：我们试了这么多模型，报告哪一个？

**Gilman 的说明**：统计学家为此奉献了整个职业生涯，**没有唯一正确答案**。本课只教一种：**后向选择**。选它是因为：
1. 简单；
2. 对预测变量数目不多的模型效果不错；
3. **可复现 (replicable)**——两位研究者用同一批数据、同一批预测变量、同样的后向选择，会得到同一个最终模型。

**为什么可复现很重要？** 为了避免 **p-hacking（p 值操纵）**：研究者尝试很多种模型，然后挑一个最符合自己想讲的故事的来报告。

**后向选择的规则**：

1. 先建立 **全模型 (full model)**：包含所有你感兴趣的预测变量（含交互项）。
2. 反复执行：找出**当前 p 值最大**的预测变量或交互项，把它从模型中删掉，重新拟合。
3. **但是：只要一个预测变量还参与着模型中的某个交互作用，就不能删除它**（哪怕它的主效应 p 值最大）。
4. 当**所有剩下的预测变量都显著（或者虽不显著但参与着显著的交互作用）**时，停止。这就是最终模型。

**为什么必须一次只删一个？** 因为删掉一个预测变量后，**其他预测变量的显著性会改变**。

**经验法则 (rule of thumb)**：全模型中的预测变量（每个交互项也算一个）**不应超过数据点数的 1/10**（更保守的人说 1/20）。本例 6 个预测变量、100 个数据点 → 安全。

**实操演示**：

全模型（code 4.17）：
```
mc_school         p = 0.000166 ***
mc_age            p = 0.597183          ← 但它与 male 有交互，不能删
male              p = 7.42e-05 ***
english           p = 0.994231          ← 【p 值最大，且不参与交互 → 删除】
mc_school:mc_age  p = 0.089657 .
mc_age:male       p = 0.000290 ***
```

删掉 `english` 后重新拟合（code 4.18）：
```r
s.lm = lm(wage ~ mc_school + mc_age + male + mc_age*mc_school + mc_age*male, data = ci)
```
```
                 Estimate Std. Error t value Pr(>|t|)
(Intercept)      12.79237    0.92029  13.900  < 2e-16 ***
mc_school         0.80235    0.19826   4.047 0.000106 ***
mc_age            0.03808    0.07062   0.539 0.591056     ← p 最大，但参与显著交互 → 跳过
male              4.90273    1.17336   4.178 6.57e-05 ***
mc_school:mc_age  0.03079    0.01785   1.725 0.087835 .   ← 下一个最大
mc_age:male       0.35822    0.09347   3.832 0.000229 ***
```

**要不要删掉 `mc_school:mc_age` (p = 0.0878)？** 手册说这**存在争议**：删掉一个变量等于宣称它对响应没有效应；p = 0.088 时我们既不能确信它**有**效应，也不能确信它**没有**效应。**Gilman 的个人偏好：留着它，但解释时极度谨慎。** 于是 code 4.18 就是后向选择的「最佳」模型。

> 注意：**slides 版本的演示做法略有不同**（把 `mc_school:mc_age` 也删掉了，得到 `wage ~ mc_school + mc_age + male + mc_age*male`）。这说明「显著性边缘的项去留」确实是判断题，两种做法都能自圆其说——关键是**说清楚你的规则并前后一致**。

**已删除变量的 p 值怎么办？** 如果需要报告被删掉的预测变量的 p 值，**最好把它单独加回最佳模型**，记录它作为唯一「额外」预测变量时的 p 值。这样它的 p 值就不会被其他同样被删掉的变量所混淆。

**强制纳入 (forcing) 变量**：有时即使某个预测变量不显著，我们也想把它留在模型里。例：研究雏鹅体重如何依赖巢在崖壁上的高度；已有大量文献表明雏鹅体重存在性别差异，那我们就该把性别放进模型以**控制**它。如果模型里性别不显著，**不代表体重不因性别而异**——我们已经从既往研究知道它会；只是我们的**统计功效不足**以检测出来。**关键纪律**：是否强制纳入某些变量，**必须在看数据之前**、基于对系统的知识做决定。如果看完数据再随意决定，读者（甚至你自己）都很难相信你没有 cherry-pick。

### 2.11 共线性 (collinearity)

**定义**：两个（或多个）预测变量之间存在**强相关**。

**演示**：数据集里还有一列 `apt`（学术能力倾向，**Gilman 编造的假数据**）。散点图（figure 4.6）显示 `apt` 与 `school` 高度相关，$R^2 = 0.96$——学术能力倾向解释了教育年数 96% 的变异。

把中心化的 `apt` 加进最佳模型：

```r
mc_apt = ci$apt - mean(ci$apt)
s.lm = lm(wage ~ mc_school + mc_age + male + mc_age*mc_apt + mc_age*male + mc_apt, data = ci)
summary(s.lm)
```
```
               Estimate Std. Error t value Pr(>|t|)
(Intercept)   12.803646   0.925291  13.837  < 2e-16 ***
mc_school      0.075132   0.945027   0.080 0.936804    ← 教育突然完全不显著了！
mc_age         0.039207   0.070966   0.552 0.581951
male           4.909340   1.178884   4.164 6.97e-05 ***
mc_apt         0.074458   0.093859   0.793 0.429621    ← apt 也不显著！
mc_age:mc_apt  0.002465   0.001682   1.466 0.146005
mc_age:male    0.355114   0.093887   3.782 0.000275 ***
```

**「加进 mc_apt 后一切都变了！」** 教育和学术能力倾向**双双失去显著性**——这是共线性的典型症状：两个变量携带几乎相同的信息，模型无法判断该把功劳归给谁，于是两个的标准误都膨胀、谁也不显著。（注意 `mc_school` 的标准误从 0.198 暴涨到 0.945！）

继续后向选择：先删 `mc_school`（p 最大）→
```
               Estimate Std. Error t value Pr(>|t|)
(Intercept)   12.802533   0.920282  13.912  < 2e-16 ***
mc_age         0.039642   0.070380   0.563 0.574596
male           4.910741   1.172505   4.188 6.34e-05 ***
mc_apt         0.081752   0.019707   4.148 7.34e-05 ***   ← apt 立刻变得极显著！
mc_age:mc_apt  0.002456   0.001669   1.472 0.144385
mc_age:male    0.355011   0.093381   3.802 0.000255 ***
```
再删 `mc_age:mc_apt` →
```r
s.lm = lm(wage ~ mc_age + male + mc_age*male + mc_apt, data = ci)
```
```
            Estimate Std. Error t value Pr(>|t|)
(Intercept) 12.72998    0.92459  13.768  < 2e-16 ***
mc_age       0.02576    0.07017   0.367 0.714358
male         4.96233    1.17915   4.208 5.83e-05 ***
mc_apt       0.09115    0.01876   4.860 4.64e-06 ***
mc_age:male  0.35298    0.09394   3.757 0.000296 ***
```

**新「最佳」模型与旧的几乎一样**（截距 12.73 vs 12.79；男性效应 4.96 vs 4.90；男性年龄效应 0.38 vs 0.40 C$ h⁻¹y⁻¹），**唯一的大变化是「教育效应」被「学术能力倾向效应」取代了**。

**这是否说明真正起作用的是学术能力倾向而非教育年数？不一定！** 当两个变量高度共线时，我们**无法拆解它们各自的作用**。可能是：
- apt 同时影响教育年数和时薪；或
- apt 影响教育年数，而教育年数影响时薪；或
- apt **和**教育年数都影响时薪；或
- 三者都受某个我们没测量的第四变量影响。

**结论只能是**：学术能力倾向、教育年数和时薪三者强相关，**我们无法归因因果 (we cannot assign causality)**。

**实践建议**：两个预测变量高度共线时，最好**事先 (a priori) 选定你最关心的那一个**，只把它放进模型。结果告诉你该变量与响应相关；然后在**讨论 (discussion)** 部分承认驱动这一相关的机制可能涉及另一个变量。范例写法见「三、公式与图表 · 报告范式」。

---

## 三、公式与图表

### 3.1 核心公式汇总

**（1）简单线性回归模型**

$$y_i = \beta_0 + \beta_1 x_i + \varepsilon_i,\qquad \varepsilon_i \overset{iid}{\sim} N(0,\sigma^2)$$

**（2）预测（拟合）值与残差**

$$\hat y_i = \hat\beta_0 + \hat\beta_1 x_i,\qquad e_i = y_i - \hat y_i$$

**（3）最小二乘估计**

$$\hat\beta_1 = \frac{\sum(x_i-\bar x)(y_i-\bar y)}{\sum(x_i-\bar x)^2},\qquad \hat\beta_0 = \bar y - \hat\beta_1\bar x$$

**（4）平方和分解**

$$\text{SS}_{\text{tot}} = \text{SS}_{\text{reg}} + \text{SS}_{\text{res}}$$

- $\text{SS}_{\text{tot}} = \sum(y_i - \bar y)^2$：响应变量围绕其均值的总变异
- $\text{SS}_{\text{reg}} = \sum(\hat y_i - \bar y)^2$：回归线解释掉的变异（图中绿线的平方和）
- $\text{SS}_{\text{res}} = \sum(y_i - \hat y_i)^2$：残差平方和（图中蓝线的平方和）

**（5）决定系数 $R^2$**

$$R^2 = \frac{\text{SS}_{\text{reg}}}{\text{SS}_{\text{tot}}} = 1 - \frac{\text{SS}_{\text{res}}}{\text{SS}_{\text{tot}}}$$

含义：预测变量解释了响应变量总变异的多大比例。取值 0–1，越大拟合越好。**简单回归中 $R^2 = r^2$（Pearson 相关系数的平方）。**

**（6）调整后的 $R^2$**（$n$ = 样本量，$p$ = 预测变量个数）

$$R^2_{\text{adj}} = 1 - \frac{\text{SS}_{\text{res}}/(n-p-1)}{\text{SS}_{\text{tot}}/(n-1)}$$

因为**只要加变量 $R^2$ 就必然上升**（哪怕加的是随机噪声），调整后的 $R^2$ 对变量个数施加惩罚，可用于粗略比较不同复杂度的模型。

**（7）残差标准误 (residual standard error)**

$$\hat\sigma = \sqrt{\frac{\text{SS}_{\text{res}}}{n-p-1}}$$

自由度 $n-p-1$：本例 $100-1-1=98$（简单回归），$100-2-1=97$（两个预测变量），$100-6-1=93$（六个预测变量）。

**（8）系数的 t 检验**

$$t = \frac{\hat\beta_j - 0}{\text{SE}(\hat\beta_j)},\qquad \text{df} = n-p-1$$

零假设 $H_0:\beta_j = 0$（该预测变量对响应无线性效应）。

**（9）整体 F 检验**

$$F = \frac{\text{MS}_{\text{reg}}}{\text{MS}_{\text{res}}} = \frac{\text{SS}_{\text{reg}}/p}{\text{SS}_{\text{res}}/(n-p-1)}$$

零假设：所有斜率同时为 0。分子分母自由度分别为 $p$ 和 $n-p-1$（输出中 "on 1 and 98 DF"）。

**（10）均值中心化**

$$x_i^{\text{mc}} = x_i - \bar x \quad\Longrightarrow\quad \hat\beta_0^{\text{mc}} = \bar y \;(\text{简单回归时})$$

**（11）多元回归 + 交互作用（以两预测变量为例）**

$$E(y) = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_1 x_2$$

对 $x_1$ 求偏导，得到 $x_1$ 的**实际斜率**：

$$\frac{\partial E(y)}{\partial x_1} = \beta_1 + \beta_3 x_2$$

**这一式子把交互作用讲透了**：$x_1$ 的效应随 $x_2$ 而变。
- 当 $x_2 = 0$ 时，$x_1$ 的效应恰为 $\beta_1$ ——这就是「主效应在另一变量 = 0 处估计」的数学来源。
- 若 $x_2$ 是指示变量：$x_2=0$ 组的斜率 = $\beta_1$；$x_2=1$ 组的斜率 = $\beta_1 + \beta_3$。
- 截距同理：$x_2=0$ 组的截距 = $\beta_0$；$x_2=1$ 组的截距 = $\beta_0 + \beta_2$。

**（12）用拟合模型做预测**（Practical 4 的核心操作）

直线形式：$y = mx + c$，其中 $m$ = 效应量（slope），$c$ = 截距（intercept）。

例：$\hat{\text{FA}} = -0.003446 \times \text{light} + 0.106949$；当 light = 10 log(lx) 时，$\hat{\text{FA}} = -0.03446 + 0.106949 \approx 0.072$。

含交互作用的多元模型：

$$E(\text{svl}) = \beta_0 + \beta_{\text{femur}}\cdot\text{femur} + \beta_{\text{male}}\cdot\text{male} + \beta_{\text{f:m}}\cdot(\text{femur})(\text{male})$$

代入 male = 1、femur = 32：

$$E(\text{svl}) = -2.0943 + 2.8534(32) + 37.9116(1) + (-1.3317)(32)(1) \approx 84.5\ \text{mm}$$

### 3.2 图表判读要点

**（A）散点图 + 最佳拟合线（本周主力图形）**

```r
plot(ci$school, ci$wage, xlab = "years of education", ylab = "C$/h")
abline(s.lm, col = "red")     # abline 直接接受一个 lm 对象，自动画出拟合线
```

判读：
- 看**趋势方向**（上升/下降）、**离散程度**（点云宽窄 ↔ $R^2$ 高低）。
- 看有没有**曲率 (curvature)**——如果点云呈曲线，说明**线性假设被违反**，需要变换。
- 看有没有**离群点 (outliers)** 明显拉动直线。
- 看变异是否**沿 x 轴均匀**——一头窄一头宽就是**异方差 (heteroscedasticity)**。

**图注 (legend) 范式**：「Hourly wage in C$ as a function of years of formal education for 100 workers in Ontario, Canada in 1994.」——即「响应变量 as a function of 预测变量 for 样本量 + 对象 + 地点 + 时间」。

**（B）分组散点 + 多条拟合线**

无交互作用 → 两条**平行**线（截距不同、斜率相同）。
有交互作用 → 两条**不平行**线（斜率也不同），画法必须手工用 `abline(c, m)` 传入截距与斜率。

**（C）残差直方图（检查正态性假设）**

```r
hist(resid(s.lm), 20)
# resid(s.lm) 提取模型的残差向量
# 20 表示分成 20 个 bin
```

判读：
- 应大致**对称、单峰、钟形**、中心在 0。
- 手册 figure 4.8（时薪最佳模型的残差）：**明显有一条长的右尾** → 违反正态性。
- log 变换响应变量后（figure 4.10）：尾巴两侧都有了，**对称性改善**，是往正确方向走了一步。

**（D）残差 vs 预测值图（检查同方差性 homoscedasticity）**

```r
plot(predict(s.lm), resid(s.lm))
# predict(s.lm) 给出每个数据点的模型预测值 ŷ
# resid(s.lm)   给出对应的残差 e
```

判读：
- **理想图形**：点在 y = 0 水平线上下随机散布，**带宽处处相同**，看不出任何形状（「无结构的云」）。
- **喇叭形 / 扇形**（本例 figure 4.12：预测工资低时残差很小，预测工资高时残差变大）→ **异方差**。
- **U 形 / 弧形** → 违反了**线性假设**，需要变换预测变量。

**（E）箱线图 (box plot) 的构造**（课堂转写中 Gilman 专门解释）
- 盒中的横线：中位数（转写里说的 "the bars are the means" 应理解为盒中的中线，标准箱线图画的是中位数）
- 盒子上下沿：**第 75 与第 25 百分位数**（即四分位距 IQR 的两端）
- 须 (whiskers)：**1.5 倍四分位距**长（转写口误说成 1.55）
- Gilman 的吐槽：「须其实和盒子是冗余信息（就是盒子长度的 1.5 倍），有点奇怪，但发明箱线图的人（他姓 Box，真的叫 Box）就是这么画的，从此大家都这么画，读者也期待这样，所以图就长这样。」

### 3.3 结果报告范式（★本课重点技能，务必背下来★）

**（1）简单线性回归**

> "We found a significant positive effect of education on hourly wage (*β* = 0.9057 C$ h⁻¹ y⁻¹, p = 0.0002, t = 3.916, df = 98)."

或（lecture slide 11 的更口语版本）：

> "We found that hourly wage increased by C$0.91 for every additional year of formal education (t = 3.92, df = 98, p = 0.0002)."

**必备要素**：
- **p 值**和**效应量**必须**都报**，因为它们传达**不同的信息**（p 值说「有没有关系」，效应量说「关系有多大」）。
- 希腊字母 **β**（或斜体 b）常用来表示回归的效应量。
- **效应量几乎总有单位，必须报出来**！单位 = **响应变量的单位 / 预测变量的单位**。例：C$ h⁻¹ y⁻¹ 读作「每小时加元 每年（教育）」。上标 −1 表示该单位在分母上。
- t 统计量和自由度：如果方法部分已经报了样本量，它们是**冗余的**，但许多读者喜欢看到，有些期刊要求必须报。

**（2）不显著/弱证据的结果**

> "We found weak evidence that fluctuating asymmetry decreases with light intensity (−3.4 × 10⁻³ log(lx)⁻¹, p = 0.0554)."
>
> "We found no evidence that leaf area affects FA when controlling for light intensity (p = 0.7908)."
>
> "We found no effect of native language on hourly earnings (p = 0.9942)."

注意：不显著时通常**只报 p 值**（因为效应量估计不可靠），并使用「no evidence that…」的措辞，**绝不能写成「证明了没有效应」**。

**（3）含交互作用的多元回归 — 文字部分**

> "We found a significant positive effect of education on hourly wage (b = 0.80 C$ h⁻¹ y⁻¹, p = 0.0001; table 4.1). Men earned higher wages than women of similar age and education (b = 4.90 C$ h⁻¹, p < 0.0001). We found a significant positive effect of age on hourly wage in men (b = 0.40 C$ h⁻¹ y⁻¹, p < 0.0002) but not in women (p = 0.5911), and we found a weakly significant positive interaction between age and education (b = 0.03 C$ h⁻¹ y⁻¹ y⁻¹, p = 0.0878). We found no effect of native language on hourly earnings (p = 0.9942)."

要点：
- 「Men earned higher wages than **women of similar age and education**」——**必须写出「在……相同的条件下」**，这才是控制变量后的正确表述。
- 交互作用要拆开讲清楚：**男性中有年龄效应、女性中没有**。
- 「age by education」交互作用的单位是 **C$ h⁻¹ y⁻¹ y⁻¹**（两个 y⁻¹！一个是教育年、一个是年龄年）。
- 被删除的预测变量（native language）也要报，读者需要知道你检验过它。

**（4）含交互作用的多元回归 — 表格**

当模型有多个预测变量时，图形容易误导且难懂，**用表格更清楚**。

| Predictor | Effect size | t-statistic | p-value |
|---|---|---|---|
| intercept | 12.79 C$ h⁻¹ | 13.90 | <0.0001 |
| education | 0.80 C$ h⁻¹y⁻¹ | 4.047 | 0.0001 |
| age | 0.04 C$ h⁻¹y⁻¹ | 0.539 | 0.5911 |
| sex | 4.90 C$ h⁻¹ | 4.178 | <0.0001 |
| age by education | 0.03 C$ h⁻¹y⁻¹y⁻¹ | 1.725 | 0.0878 |
| age by sex | 0.36 C$ h⁻¹y⁻¹ | 3.832 | 0.0002 |

**表注 (caption)**：Table 4.1. Predictors of hourly wage among workers in Ontario, Canada in 1994.

**★ Gilman 的铁律（slides 与转写都强调）★**：
> **绝不能把 R 的输出直接复制粘贴进论文当作表格！** 表格必须为读者**清晰地格式化和标注**（用有意义的变量名而非 `mc_school`，加上单位，四舍五入到合理位数，配表注）。同理，报告结果时**必须有一段英文陈述**解释发生了什么，因为我们不能指望读者会读 R。

**（5）共线性情形的报告范式**

> "We found a strong positive correlation between years of education and expected hourly wage in both men and women. However, academic aptitude closely predicts years of education (R² = 0.96). Therefore, we cannot rule out the possibility that the effect on hourly wage is driven by academic aptitude rather than by greater education."

**（6）交互作用的双斜率报告范式（Practical 4 Q4.4）**

> "The relationship between femur length and svl differed in male and female *I. luetkenii* (p = 0.0191). In females, svl increased by 2.85 mm for each 1 mm increase in femur length. In males, svl increased by 1.52 mm for each 1 mm increase in femur length."

---

## 四、课堂补充

> **重要说明**：本周的 22-Nov 课堂录音是一节 **drop-in（答疑/复习）课**，Gilman 用它**回顾上一周 Practical 3（ANOVA）的第 3 题**，并深入讲了一些**只在课堂上出现、slides 与手册里没有的概念**。这些内容既是对 Week 02 的重要补充，也直接铺垫了本周的回归（尤其是「顺序问题」和「对数变换」）。以下内容极有价值，请务必掌握。

### 4.1 课堂串讲的案例：Waraz(Juarez) 等人的蛙类数据，*Hyla* 属

```r
# 偷懒技巧：不设工作目录，直接把完整路径写进 read.csv
waraz.data = read.csv("完整路径/data_from_Juarez_et_al_2023.csv")
# Gilman 的理由：只要文件没被移动，明年、下次再用这段代码时它照样能找到文件

# 取子集：只保留 genus == "Hyla" 的行
hyla = waraz.data[which(waraz.data$genus == "Hyla"), ]
# 方括号 [行条件, ] —— 逗号后留空表示保留全部列
```
数据内容：作者们跑遍美国的博物馆，测量无尾目 (anurans) 标本的**质量 (mass)、股骨长 (femur length)、吻肛长 (snout-vent length, svl)**，并记录属、种、采集地和性别。*Hyla* 属下有三个种：*cinerea* (Syneria)、*arenicolor* (Arnicolor)、*chinensis* (Enchinensis)。

**「先画图，再分析」的工作习惯**：Gilman 在做 ANOVA 之前先画了带误差棒的条形图，「先看看该期待什么」。目测：*chinensis* 比另外两种小；性别差异不明显。

### 4.2 为什么这里不能用 t 检验 —— 一个极精彩的解释

Practical 3 Q3.1 问：能不能用 t 检验来研究性别对股骨长的影响？**大多数交上来的答案说不能，理由正确。**

理由：**t 检验假定数据服从正态分布**。但如果只按性别把 *Hyla* 属的股骨长画成直方图，会看到**双峰 (two peaks)** ——因为里面混了三个不同大小的物种！

> 「所以如果我们试图用 t 检验做这件事，不仅会因为忽略物种而**丢失信息**，还会做出一个『数据是正态分布』的**错误假设**。」

**这个洞察的普遍价值**：**看起来非正态的数据，常常是因为里面藏着一个你没有建模的分组变量。** 把那个变量加进模型（用 ANOVA 或多元回归），每组内部往往就正态了。

Gilman 还是运行了 t 检验作为反面教材：性别的 p = 0.186（不显著），并预告 ANOVA 会给出不同的结论。

### 4.3 ANOVA 中项的顺序**有关系**，但回归中**没关系** ★★

```r
# 全模型（含交互）
aov(femur ~ species + sex + sex*species, data = hyla)
```

**各项含义**：
- `species`：不同物种间股骨长是否有差异？
- `sex`：不同性别间是否有差异？
- `species*sex`：**交互作用**——性别的效应在不同物种中是否不同？（等价地：物种的效应在两性中是否不同？**这两种问法完全是同一个问题**。）
- 交互作用的直觉例子：**在一个物种里雄性比雌性大，在另一个物种里雌性比雄性大** → 性别的效应因物种而异。

**★ 关键点：`aov()` 对项的顺序敏感 ★**
在 `femur ~ species + sex + sex*species` 中：
- `species` 是**第一项** → 它的效应是**跨两性合并的、没有控制性别的**。
- `sex` 是**第二项** → 它的效应是**已经扣除了物种效应之后的**，即「**控制物种后的性别效应**」。
- 交互作用是最后一项 → 它是在已经扣除物种和性别的主效应之后的。

> 「所以在实践中，ANOVA 往往只解释模型中的**最后一项**。」

**结果**：交互作用完全不显著。虽然图上看起来 *chinensis* 和 *arenicolor* 里两性有差异、*cinerea* 里没有，但 **p 值告诉我们这个差异并不比偶然预期的更大**——在这么小的样本里，柱子们本来就不会完美对齐，这点散布很容易是运气。

**处理不显著交互作用的惯例**：
> 「特别是对交互作用，如果它不显著、你也没有理由相信它解释了数据中的什么东西，**通常最好把它从模型中拿掉**，因为它会**让主效应更难解释**。」

去掉交互作用后：`aov(femur ~ species + sex)` → 性别 p = 0.112，不显著。
调换顺序：`aov(femur ~ sex + species)` → 性别 p = 0.09。

**注意：p 值从 0.112 跳到 0.09，跨过了边缘显著性的另一侧！** Gilman 说这里我们不会把它解读为天差地别，但**它确实变了**，而且在别的分析里**差别可能大得多**。

### 4.4 用模拟数据 (simulation) 理解统计方法 —— 一条通用的科研方法论

Gilman 花了很长时间论证这一点，值得单独记：

> 「在你的整个科学生涯中，你常会遇到一个想用的新分析方法，而且你可能会发现自己并不 100% 确定它在做什么。至少我经常这样。你可以去读文献，但读了也未必能完全解开疑惑。
>
> 所以一个非常有用的做法是：**造一个你知道答案的数据集，然后去分析它。** 如果你知道答案是什么，运行分析后它把你知道的答案反馈回来了，很好，你大概理解了这个分析。如果分析没给出你以为会给的结果，那也许你并不理解这个分析在做什么。
>
> 模拟数据的价值在于：**如果你从自然界采集真实数据，你并不知道里面到底有什么**；不知道里面有什么，你就不知道该不该对分析结果感到惊讶。但如果你模拟数据，你就知道。」

**他的模拟设计**：
1. 从正态分布随机抽取模拟青蛙的股骨长（均值 10）。
2. 随机分配物种 (A/B) 和性别 (M/F)。
3. **给所有雌性的股骨长加 2** → 已知：雌性比雄性大**恰好 2 个单位**。
4. **不给物种加任何效应** → 已知：物种之间**真实差异为 0**。
5. **但故意让抽样不平衡**：物种 A 抽了更多雄性，物种 B 抽了更多雌性。

**结果（这是本节的精髓）**：
- 总均值 ≈ 11（起始 10，雌性 +2，平均下来 ≈ 11）✓
- 先看性别的均值：雌性比雄性大约 2 单位 ✓（我们放进去的）
- **控制性别后**看物种（先把 sex 放进模型，再问物种是否不同）：两个物种在**同一性别内部**的均值几乎完全一样，差异极小，完全可能是偶然 ✓
- **不控制性别**直接看物种（先把 species 放进模型）：**物种均值差别很大**，我们会**错误地推断出物种之间存在差异**！
- 跑 ANOVA 验证：`femur ~ sex + species` → 物种无效应（正确）；`femur ~ species + sex` → 物种有很大效应（**错误结论**）。

**结论**：物种间的表观差异**不是**因为物种内部真的不同，而是因为**两个物种的性别抽样比例不同**。这在自然界的任何抽样中都可能发生，也可能是物种本身就有性别偏倚。

> 「**这就是为什么顺序重要。这是做 ANOVA 时必须想清楚的事情。它在我们的回归模型里不会再出现，因为回归模型的设置使得顺序无关紧要，但 ANOVA 里是有关系的。**」

### 4.5 「缺乏证据 ≠ 证据缺乏」

> 「我们不能基于这个结果说这些蛙的股骨长在两性间有差异。我们也**不能说它没有差异**——**absence of evidence is never evidence of absence（缺乏证据从来不是不存在的证据）**。尤其在这里 p 值是 0.1，如果我们有一个大得多的数据集，真不知道会看到什么。」

**由此引出的一个「哲学问题」**：`femur ~ species + sex` 这个模型里，我们该不该解释 `species`（它没有控制 sex）？
- 一方面：我们没有证据说 sex 重要，所以忽略 sex 或许没问题。
- 另一方面：我们从**其他很多蛙类**的既往研究知道性别是重要的，而 p = 0.1 **绝不是「性别毫无意义」的有力证据**——它只是**不确定 (inconclusive)**。
- **Gilman 本人的选择**：「你这么解释不算错。**但如果是我，我不会这么做。** 我会想：我们知道性别对某些蛙很重要，所以让我们**控制性别之后**再看物种，看看模式会不会变。」→ 于是他改用 `femur ~ sex + species`。

**这一段体现的科研判断力**：统计不是机械套公式，**要把领域知识 (domain knowledge) 带进模型设定的决策里**。

### 4.6 Tukey 事后检验输出的读法（一个非常实用的小技巧）

ANOVA 是一个 **omnibus test（总括检验）**：它告诉你「这些物种之间**某处**存在差异」，但**不告诉你是哪两个之间有差异**。要知道这个，需要跑 **Tukey 事后检验 (post hoc test)**。

**Gilman 的读表技巧**：
> 「对我来说，读这个输出最容易的方式是**把行名 `chinensis-arenicolor` 里的短横线当成减号**。所以 chinensis 减 arenicolor 得到 −0.54 的差值，那就意味着 **arenicolor 必然更大**（才能得到负的差）。」

结果：
- *chinensis* 显著小于 *arenicolor*（p 很小，差值 −0.54）
- *cinerea* 显著大于 *chinensis*
- *cinerea* 与 *arenicolor* **无证据**有差异——它们足够接近，看到的差异很容易是偶然。「我们**不知道哪个更大**。」

### 4.7 ANOVA 的等方差假设：4 倍经验法则 ★

Practical 3 Q3.5（挑战题）问：图里有什么会让你担心不该用 ANOVA？

课堂讨论后的答案：**方差不齐**。
- ANOVA 假设**各组内方差相同**，但箱线图里 *cinerea* 的雌雄组变异非常大，*chinensis* 的各组则挤成一团、组内变异小得多。

**★ 经验法则 (rule of thumb)★**：
> 「ANOVA 对方差差异有**一点稳健性 (robust)**。人们用的经验法则是：**如果方差之差不到大约 4 倍，你大概不用担心。但这里差了将近 9 倍**，所以方差差异相当大。」

### 4.8 为什么要取对数 (log transformation) —— 极重要的推导 ★★

「超级挑战题」问：能对方差不齐做点什么？答案是：**对数据取对数**，尤其是**身体测量数据**。

**Gilman 的完整论证**：

设有一个蛙群体，均值大小 $\mu$，围绕均值正态分布：最大的约 $\mu + X$，最小的约 $\mu - X$。现在假设有一台「魔法生长射线」把所有蛙**按比例放大一倍**：新群体均值变成 $2\mu$，最大的变成 $2\mu + 2X$，最小的变成 $2\mu - 2X$。

**关键观察：变异随均值一起缩放了 (the variability is scaled with the mean)。**

但我们不希望这样！**我们希望改变均值时变异保持不变**，因为这正是 ANOVA（以及大多数线性模型）的假设。

**数学表述**：我们的模型假设观测值是

$$y_i = \mu + \varepsilon_i \qquad (\text{加性误差 additive error})$$

但对于身体测量数据，实际情况往往是

$$y_i = \mu \cdot \varepsilon_i \qquad (\text{乘性误差 multiplicative error，误差大小随均值增长})$$

**取对数就把乘法变成加法**：

$$\log(y_i) = \log(\mu) + \log(\varepsilon_i)$$

于是又回到了模型假设的加性形式。

**第二个理由：幂次关系也能被对数变成加性**。
> 「质量 (mass) 与蛙的**体积**成正比，因为不只是它有多长，还有宽和高；如果三个维度同时放大，质量以任一线性维度的**立方**增长。但同样方便的是，如果我们对**取了幂次**的数据取对数，我们仍然得到加性函数。」

数学上：$M \propto L^3 \Rightarrow \log M = 3\log L + \text{const}$ ——**幂函数取对数后变成直线**，可以直接用线性回归！

**什么时候应该考虑取对数？**
1. **看到数据里有曲线 (curves)** → 常常提示需要取对数。
2. **哲学/机理上的理由**：当你有理由认为**误差随均值缩放**时（身体测量、生长、收入……）。

**与手册第 4 章的呼应**：手册给出的另一个变换例子是**脑容量 vs 股骨长**（figure 4.7）——脑容量是三维量，股骨长是一维量，所以关系是 $\text{volume} \propto \text{length}^3$，**取立方根 (cube root) 后关系变为线性**，即可用线性回归。这与课堂上讲的「质量随线性尺寸立方增长」是同一个道理。

### 4.9 报告结果时的语言纪律（转写中反复强调）

> 「报告结果时，无论哪种科学写作，我们**不能直接把 R 的表格粘进文档**，因为我们不能指望读者会读 R。我们要有一段**英文陈述**来解释发生了什么。」

他给出的 ANOVA 报告范式（结构可迁移到回归）：
1. 陈述**控制了什么**之后**哪个因素有差异**，并给出 p 值；
2. 陈述**哪个因素没有差异**（控制了什么之后），并给出 p 值；
3. 对**存在差异的地方**，同时给出**差异的大小 (magnitude)** 和对应的 p 值。

> 「这几乎是直接从 practical 里抄下来的，只是把 p 值和数字填了进去。」——**这是给学生的实用暗示：practical 题干里的句子本身就是答题模板。**

### 4.10 课程管理信息

- 答案键 (answer key) 原本周四/周五才发，经学生反馈后 Gilman 承诺**改到周一发**，这样大家周末有时间琢磨难题，之后又能及时对答案。
- Gilman 表示交上来的作业（约十来份）质量不错。

---

## 五、Practical 要点

### 5.1 Practical 4 的学习目标

完成 Practical 4 后你应当能够：
- 做并报告**简单**与**多元线性回归**
- 用拟合模型从原始数据**预测响应变量**
- **分析并报告预测变量之间的交互作用**
- 用**图形**展示线性回归结果

### 5.2 数据集一：叶片波动不对称性 (Fluctuating Asymmetry, FA)

**科学背景**：很多动植物是**两侧对称 (bilaterally symmetric)** 的，但任一个体的两侧总有细微差别。**波动不对称性 (FA)** 就是衡量两侧差异有多大的指标。研究者关心 FA，因为它可能是**发育压力 (developmental stress)** 的信号：越对称的个体在发育中承受的压力越小，可能更健康、生物学适合度更高。

**研究**：2018 年曼大学生 Bailey Francis 在意大利阿尔卑斯野外课程中研究**低光照是否促进叶片 FA**。对象是菊科高山植物 ***Adenostyles alliariae***。他从遮阴和不遮阴处的 100 株植物上采叶：
- 在每片叶子的采集地测**光强**，单位 **log(lx)**（lx = lux 勒克斯 = 1 lumen/m²）
- 用 **ImageJ** 软件从照片测**叶片总表面积**
- 测量叶**中脉 (midrib)** 到左右两侧最宽点的距离 R 和 L，据此计算 FA

FA 的常用公式（**与叶片大小无关**，这是它的优点）：

$$\text{FA} = \frac{|R-L|}{(R+L)/2} \quad \text{或} \quad \frac{|R-L|}{R+L}$$

（题干中公式图未转出，此处给出该领域标准形式；关键是**分母做尺寸标准化**，使 FA 成为**无量纲 (unitless)** 量。）

数据文件：`data from Francis and Gilman 2018.csv`，导入后命名为 `fa.data`。

**Gilman 的方法论旁白（很有智慧）**：
> 「如果你读 Francis 的论文，会发现他用了比我们这里更复杂的分析。随着你在科学道路上前进，你会发现**无论你做什么分析，几乎总有更复杂的可用**。作为研究者，你的目标常常是找到一个**足够好到能回答你的问题、又不至于让你把一辈子都耗在一个数据集上**的分析。」

#### Question 1：简单线性回归

**Q1.1** 列名分别是：光强 = **`light`**，叶面积 = **`leaf.area`**，波动不对称性 = **`fa`**。

```r
fa.data = read.csv("data from Francis and Gilman 2018.csv", header = TRUE)

# 先画散点图目测
plot(fa.data$light, fa.data$fa,
     xlab = "light intensity in log(lx)",
     ylab = "fluctuating asymmetry")
```

**Q1.2**（目测）：看起来 FA 与光强之间有**微弱的负相关**。答案键：「我猜它大概是统计显著的，或者至少非常接近。」
> 题干安慰：Q1.2 猜错了不要紧，多做几个你就会培养出对这类模式的直觉。

```r
fa.lm = lm(fa ~ light, data = fa.data)   # 注意 lm 里响应在前！
summary(fa.lm)
```

```
Coefficients:
             Estimate Std. Error t value Pr(>|t|)
(Intercept)  0.106949   0.017505   6.109 2.03e-08 ***
light       -0.003446   0.001777  -1.939   0.0554 .
```

**解读**：
- p = 0.0554，**没有低于 0.05，但很接近** → 称为「**弱证据 (weak evidence)**」。
- 效应量 = −0.003446：光强每上升 1 个单位，FA **下降** 0.0034 个单位。
- **报告**：「We found weak evidence that fluctuating asymmetry decreases with light intensity (−3.4 × 10⁻³ log(lx)⁻¹, p = 0.0554).」
- **单位说明**：FA 无量纲，预测变量是 log(lux)，所以效应量单位 = log(lx)⁻¹，上标 −1 表示它在分母上。

**Q1.3 作图**：
```r
plot(fa.data$light, fa.data$fa,
     xlab = "light intensity in log(lx)", ylab = "fluctuating asymmetry")
abline(fa.lm, col = "red")     # 直接把 lm 对象丢给 abline，它会画出拟合线
```
图注：「Fluctuating asymmetry in the leaves of 100 *Adenostyles alliariae* plants plotted as a function of light intensity measured at the leaf location.」
> 「这是你在 R 里做过的**最容易的图**！」

**Q1.4 用模型做预测**：
$$\hat{y} = mx + c = -0.003446 \times 12 + 0.106949 = 0.0656 \approx \mathbf{0.066}$$
（答案键：0.066）

> 也可以**图解**：从 x 轴 12 处向上画竖线交到拟合线，再向左画横线读 y 轴。但**直接计算更容易也更准确**。

#### Question 2：另一个简单回归（叶面积 vs 光强）

```r
la.lm = lm(leaf.area ~ light, data = fa.data)
summary(la.lm)
plot(fa.data$light, fa.data$leaf.area,
     xlab = "light intensity in log(lx)", ylab = "leaf area")
abline(la.lm, col = "red")
```

**Q2.1 答案**：「Leaf area decreases with increasing light intensity (−27.9 cm² log(lx)⁻¹, p < 0.0001).」
→ **强证据**：光照越强，叶片越小（阴生叶更大，这是植物增大受光面积的经典适应）。

**Q2.3 预测**：8 log(lx) 时约 **220 cm²**；12 log(lx) 时约 **108 cm²**。
（自检：差值 112 cm² / 4 单位 = 28 ≈ 斜率 27.9 ✓；反推截距 ≈ 220 + 8×27.9 ≈ 443 cm²。）
> ⚠️ **单位不一致提醒**：题干说 ImageJ 测的面积单位是 mm²，但答案键用的是 cm²。做题时**以数据文件里的实际数值为准**，报告时把单位写对。

#### Question 3：多元回归与「控制」的核心逻辑 ★★

**科学推理链（非常漂亮，值得整段掌握）**：
- Q1 发现：**低光 → FA 更高**（弱证据）
- Q2 发现：**低光 → 叶片更大**（强证据）
- **提问**：FA 的差异会不会**不是**低光造成的，而是**快速生长**造成的？也就是说，叶片长得快、长得大时更容易不对称，而这**完全解释**了光强与 FA 的关系？

**把这个假说翻译成可检验的预测**：若假说成立，则应当有
1. **控制光强**后，更大的叶片仍有更高的 FA；且
2. **控制叶片大小**后，光强与 FA 之间**没有**关系。

**为什么必须用多元回归？** 光强我们可以在精心设计的实验里控制，但**叶片大小我们控制不了**。不过，**在线性模型里我们可以「统计地」控制任一个或两个预测变量**。

```r
fa2.lm = lm(fa ~ light + leaf.area, data = fa.data)
summary(fa2.lm)
```

这一个模型同时给出：
- **控制光强后**，FA 与叶面积的关系
- **控制叶面积后**，FA 与光强的关系

**Q3.1 答案**：**两个都不显著**，我们对哪一种模式都没有显著证据。

**Q3.2 报告**：「We found no effect of light intensity on fluctuating asymmetry when controlling for leaf size (p = 0.1745).」
（叶面积那一项：「We found no evidence that leaf area affects FA when controlling for light intensity (p = 0.7908).」）

**Q3.3（挑战题）：这是否推翻了 Q1.3 的结论？**
答案键的完整推理（**极佳的科学写作范例，务必学会这种论证方式**）：
> 「不，我不这么认为。我们**猜测** FA 可能取决于叶面积而非光强。但我们的模型显示，**控制光强后叶面积毫无效应**，所以我**看不出有什么好理由把叶面积强行塞进模型 (force leaf area into the model)**。而且，**无论模型里有没有叶面积，光强对 FA 的效应在方向和量级上都相似**。我们在第一个分析里找到了 FA 与光强关系的弱证据，我认为**我们现在仍然有弱证据**。」

**要点提炼**：
1. 加入一个**本身不显著**的预测变量后，另一个预测变量的 p 值**变大了**（0.0554 → 0.1745），但这**不是**「原结论被推翻」——而是因为**多加一个无用变量会消耗自由度、抬高标准误、降低统计功效**。
2. 判断标准应看**效应量的方向与量级是否稳定**，而不是只盯 p 值有没有跨过 0.05。
3. **这与 2.10 节的「强制纳入 (forcing)」原则一脉相承**：没有先验理由，就不该硬塞变量。

### 5.3 数据集二：无尾目蛙类形态 (Juarez et al. 2023)

**科学问题**：同种个体不仅可以在**大小**上不同，也可以在**比例 (proportions)** 上不同——即某个尺寸元素与另一个的关系。本题聚焦**股骨长 (femur) 与吻肛长 (svl) 的关系在两性间是否不同**。svl 是动物总长度的度量，股骨是与运动相关的腿骨。**如果某一性别的股骨相对更长，可能意味着两性在运动方式、乃至生态位上存在差异。**

#### Question 4：黄蟾蜍 *Incilius luetkenii*

**背景**：中美洲低地常见蟾蜍。与许多无尾目不同，**雄性黄蟾蜍会通过肢体搏斗竞争交配机会**，对搏斗胜利的选择压力可能促成性二型 (sexual dimorphism)。

```r
# 取子集
inc.lue = anuran.data[which(anuran.data$species == "luetkenii"), ]

# 先画图（男女用不同颜色）
plot(inc.lue$femur, inc.lue$svl, xlab = "femur length (mm)", ylab = "svl (mm)")

# 创建指示变量，并【写回数据框】
inc.lue$male = as.numeric(inc.lue$sex == "M")
# == 返回逻辑向量；as.numeric 把 TRUE/FALSE 转成 1/0
# 写成 inc.lue$male 是为了把新向量加进数据框，这样 data=inc.lue 时能找到它
# 运行后要看一眼 inc.lue，确认结果符合预期
```

**Q4.1**（目测）：看起来 svl 对股骨长的**斜率在雌性中略陡一些**。

**建模——为什么需要交互作用**：

先看不含交互作用的模型 `lm(svl ~ femur + male)` 能回答什么：
- svl 是否随股骨长变化（**在性别内部 / 控制性别后**）？
- 两性在**股骨长相同时** svl 是否不同？

**但这两个都不是我们要问的问题！** 我们想知道的是：**股骨长与 svl 的关系在两性间是否不同**，也就是**股骨长对 svl 的效应是否取决于性别**——这就是**交互作用**。

```r
inc.lue.lm = lm(svl ~ femur + male + femur*male, data = inc.lue)
summary(inc.lue.lm)
```

```
Coefficients:
            Estimate Std. Error t value Pr(>|t|)
(Intercept)  -2.0943     9.8987  -0.212   0.8341
femur         2.8534     0.3154   9.046 1.64e-09 ***
male         37.9116    16.1065   2.354   0.0264 *
femur:male   -1.3317     0.5328  -2.500   0.0191 *
```

**Q4.2 答案**：**有**交互作用的证据，因为交互项 `femur:male` 的 **p = 0.0191 < 0.05**。

**★ 四个系数的逐一解读（本 practical 最核心的一段）★**

| 系数 | 值 | 含义 |
|---|---|---|
| `(Intercept)` | −2.0943 | 所有预测变量 = 0 时的 svl 预测值。`male = 0` 表示雌性，所以这是「**股骨长为 0 的雌性**」的预测 svl。**显然是荒谬的**（没有股骨长为 0 的蟾蜍），但它仍然有用——它是**雌性最佳拟合线的截距**。 |
| `femur` | 2.8534 | **因为存在 `femur:male` 交互作用**，股骨长对 svl 的效应取决于性别，所以报告的 `femur` 效应**不可能是"对所有性别"的**，必然是对某个特定性别的。**按惯例，是被编码为 0 的那个性别（雌性）**。所以这是**雌性拟合线的斜率**：雌性股骨每长 1 mm，svl 增加 2.8534 mm。 |
| `male` | 37.9116 | 「**一个单位的"雄性度"**」对 svl 的效应，**在股骨长 = 0 时**。男 = 1、女 = 0，所以"一个单位的雄性度"就是男女之差。即：**在截距处（femur = 0）**，雄性的预测 svl 比雌性高 37.9116 mm。因此**雄性拟合线的截距 = −2.0943 + 37.9116**。 |
| `femur:male` | −1.3317 | **每增加一个单位的"雄性度"，`femur` 的效应（斜率）改变多少**。雌性斜率是 2.8534，所以**雄性斜率 = 2.8534 + (−1.3317) = 1.5217**。 |

**作图**：
```r
abline(-2.0943, 2.8534, col = "red")                      # 雌性线（红，与雌性点颜色一致）
abline(-2.0943 + 37.9116, 2.8534 + (-1.3317), col = "blue")  # 雄性线（蓝）
# abline(c, m) 画 y = m x + c：第一个参数截距，第二个参数斜率
# 因为有交互作用，abline 无法直接从模型对象画出两条线，必须手动传入
```

**Q4.3（挑战题）：控制股骨长后，雄性的 svl 比雌性大还是小？**
**答案：取决于股骨长 (It depends on the femur length)。**

**这背后是一个极重要的思想（题干专门写了一整段）**：
> 「如果模型中存在交互作用，就**很难对参与该交互作用的预测变量的主效应做一般性陈述**。这**不是模型的怪癖，而是系统本身的属性**。如果交互作用是真实的，那么交互作用中每个预测变量的主效应**都随另一个变量的取值而改变**，**可能根本不存在一般性的模式**。正因为交互作用让主效应难以解释，**所以如果我们检验了交互作用而没有找到证据，我们可能需要研究不含交互作用的模型才能对预测变量做出正确推断**。」

（几何直观：两条不平行的线**必然会相交**。在交点一侧雄性 svl 更大，另一侧雌性更大。所以答案只能是「看股骨长多少」。）

**Q4.4 报告**：
> "The relationship between femur length and svl differed in male and female *I. luetkenii* (p = 0.0191). In females, svl increased by 2.85 mm for each 1 mm increase in femur length. In males, svl increased by 1.52 mm for each 1 mm increase in femur length."

**Q4.5 用含交互作用的模型做预测**：

$$E(\text{svl}) = \beta_0 + \beta_1\,\text{femur} + \beta_2\,\text{male} + \beta_3\,(\text{femur})(\text{male})$$

雌性（male = 0）、股骨 35 mm：

$$E(\text{svl}) = -2.0943 + 2.8534(35) + 37.9116(0) + (-1.3317)(35)(0) = -2.0943 + 99.869 \approx \mathbf{97.8\ \text{mm}}$$

（题干示范：雄性 male = 1、股骨 32 mm → $-2.0943 + 2.8534(32) + 37.9116(1) + (-1.3317)(32)(1) \approx 84.5$ mm）

**Q4.6（超级挑战题）★ 极其重要的技巧 ★**

**问题**：模型告诉我们**雌性**的斜率 2.8534 显著异于 0。雄性斜率 = 2.8534 − 1.3317 = 1.5217。**如何检验雄性斜率是否显著异于 0？**

**为什么现成的 p 值不够用**：
- `femur` 行的 p 值检验的是**雌性斜率 ≠ 0**；
- `femur:male` 行的 p 值检验的是**「雄性斜率与雌性斜率之差」≠ 0**（即"两性的效应显著不同"），**而不是「雄性斜率 ≠ 0」**。

**解法：换基线 (switch the baseline)** —— 造一个反过来的指示变量，让**雄性变成编码为 0 的那一组**。

```r
inc.lue$female = as.numeric(inc.lue$sex == "F")   # 雌性=1，雄性=0
inc.lue.lm2 = lm(svl ~ femur + female + femur*female, data = inc.lue)
summary(inc.lue.lm2)
```

```
Coefficients:
             Estimate Std. Error t value Pr(>|t|)
(Intercept)   35.8173    12.7057   2.819  0.00909 **
femur          1.5217     0.4293   3.544  0.00151 **     ← 现在这是【雄性】的斜率！
female       -37.9116    16.1065  -2.354  0.02642 *
femur:female   1.3317     0.5328   2.500  0.01907 *
```

**验证换基线的对称性（自检好方法）**：
- `femur` = 1.5217 = 2.8534 + (−1.3317) ✓（正是我们手算的雄性斜率）
- `female` = −37.9116 = −(原 `male` 系数) ✓
- `femur:female` = +1.3317 = −(原 `femur:male` 系数) ✓
- `(Intercept)` = 35.8173 = −2.0943 + 37.9116 ✓（原来算出的雄性截距）
- **交互作用的 p 值几乎不变**（0.0191 vs 0.01907，微小差异来自舍入）→ **「两性斜率不同」这个结论与基线选择无关** ✓

**报告**：「In male *I. luetkenii*, svl increased by 1.52 mm for each 1 mm increase in femur length (p = 0.0015).」

#### Question 5：温室蛙 *Eleutherodactylus planirostris*

**背景**：加勒比海岛屿（古巴、开曼、巴哈马）落叶层中的小型蛙。与多数蛙不同，**温室蛙没有自由生活的蝌蚪阶段**——蝌蚪在卵壳内就发育成小蛙，卵直接孵出蛙。这被认为是对落叶层生活的适应：那里湿度充足但没有积水。

**Q5.1**：与 Q4 完全相同的流程（取子集 → 建指示变量 → 含交互作用的 lm）。

> "The relationship between femur length and svl differed in male and female *E. planirostris* (p = 0.00714). In females, svl increased by 2.81 mm for each 1 mm increase in femur length. In males, svl increased by 1.10 mm for each 1 mm increase in femur length."

**Q5.2**：作图（同 Q4：散点按性别着色 + 手动两条 `abline`）。

#### Question 6：离群点 (outlier) 的处理 ★重要的科研伦理与方法★

**观察**：Q5.2 的图里有**一只雄性温室蛙股骨异常长、而 svl 相对同股骨长的其他个体偏小**。乍看之下，**Q5.1 的结论可能主要是这一个点造成的**。这个点可能是某种**记录错误**。

**★ Practical 4 给出的黄金原则 ★**：
> 「**我们不能仅仅因为数据点看起来奇怪就把它排除。** 如果那样做，我们的分析就只会显示我们预期的结果，我们就**永远不会从中学到任何新东西**。
>
> **然而**，如果有些数据点我们出于某种理由并不完全信任，那么一个好的做法是：**把数据集在"包含这些点"和"排除这些点"两种情况下都分析一遍**。
> - 如果**两种做法结果相似**，我们对这个故事就更有信心；
> - 如果**不相似**，那么我们在向读者报告时就要**格外谨慎**。」

（与手册 4.3 节的呼应：手册举了蚂蚁的例子——研究蚁群活动如何随温度变化，15 天中有一天下雨。如果那天的点变成了离群点，这可能提示**蚂蚁在雨中的行为根本不同**，那个点无法准确反映晴天的模式。此时可以考虑排除它，**并把解释限定在晴天**。**排除任何离群点，都必须在方法部分仔细论证。**）

```r
ele.pla.1 = ele.pla[ -which( ele.pla$sex == "M" & ele.pla$femur > 10 ), ]
# which(...)  返回满足条件的【行号】：性别为 M【且】股骨长 > 10
# 前面的负号 -  表示【删除】这些行
# 方括号里逗号后留空 → 保留所有列
# & 是逻辑「与」
```

**答案**：

| 题号 | 问题 | 结果 |
|---|---|---|
| **Q6.1** | 去掉可疑点后，股骨—svl 关系在两性间是否不同？ | 「With the dubious data point removed, we found **no evidence** that the relationship between femur length and svl was different in male and female *E. planirostris* (p = 0.216).」**结论完全翻转！** |
| **Q6.2** | 股骨长相同时，两性 svl 是否不同？（不含交互作用的模型） | 「When controlling for femur length, we found no evidence that male and female *E. planirostris* had different snout-vent lengths (p = 0.114).」 |
| **Q6.3** | 两性平均股骨长是否不同？（这是**两组均值比较 → t 检验**，回到 Week 01 的工具！） | 「Female *E. planirostris* had longer femurs than males (**9.57 mm vs 8.14 mm**, p < 0.0001).」 |
| **Q6.4** | 为 Q6.1–3 的显著结果作图 | 只有 Q6.3 显著 → 画**按性别分组的股骨长条形图/箱线图**（Week 02 的技能） |

**Q6 的教学意义（必须体会）**：
1. **一个数据点就能颠覆一个显著结论**（p 从 0.0071 变成 0.216），这正是**离群点的危险性**。
2. **敏感性分析 (sensitivity analysis)** 是负责任的做法：两种做法都跑、都报告。
3. **Q6.1–6.3 依次用了三个不同的模型来回答三个不同的问题**：含交互（关系是否不同）→ 不含交互（截距是否不同）→ t 检验（均值是否不同）。**问题决定模型，不是反过来。**
4. 呼应 Q4.3 的教诲：**没找到交互作用的证据 → 就该去看不含交互作用的模型**（Q6.1 无交互证据 → Q6.2 用不含交互的模型看主效应）。

---

## 六、易错点 / 重点难点

### R 操作与语法

1. **`plot(x, y)` 与 `lm(y ~ x)` 的顺序是反的！** `plot` 里预测变量在前（放 x 轴），`lm` 里响应变量在前（`y ~ x` 读作「y 依赖 x」）。**搞反了结果全错**——这是 Practical 4 专门列出的新手陷阱。
2. **`abline(model)` 只在简单回归（单一拟合线）时能用。** 一旦有交互作用产生多条线，必须手动 `abline(intercept, slope)`，**第一个参数是截距、第二个是斜率**（与 $y=mx+c$ 的书写顺序相反！）。
3. **指示变量要写回数据框**：`inc.lue$male = ...` 而不是 `male = ...`，否则 `data = inc.lue` 找不到它。
4. **`data.frame(原变量, 新变量)` 并排检查**是验证变换/指示变量是否正确的好习惯（lecture 反复演示）。
5. **子集操作**：`df[which(条件), ]` —— 逗号必不可少，逗号后留空表示保留全部列；前面加 `-` 表示删除。
6. `which()` 返回的是**位置（行号）**，不是逻辑值；`as.numeric(逻辑向量)` 才是直接把 TRUE/FALSE 转 1/0。

### 概念与解释

7. **相关不等于因果 (correlation ≠ causation)。** 共线性一节说得最透彻：apt、school、wage 三者强相关，但我们**无法归因因果**——可能是 apt→school→wage，可能是 apt 同时影响两者，也可能有第四个未测变量同时影响三者。**观察性数据（如调查数据）永远不能靠回归证明因果。**
8. **外推 (extrapolation) 的危险。** 「用模型预测观测范围之外的响应是坏做法，因为我们没有证据表明结果在那里成立。」零教育者时薪 C$3.03 不仅无用，而且**不可能成立**（加拿大有最低工资法）。零岁人的工资更是荒谬。
9. **★含交互作用时，主效应是在另一变量 = 0 处估计的★**，绝不是「平均效应」。这是本周最大的坑：
   - 有交互作用时，`femur` 行的系数是**基线组（编码为 0 的组）的斜率**，不是全体的斜率。
   - **另一组的斜率 = 主效应 + 交互项**（要相加，不是直接读交互项！）。
   - 这也是**为什么要中心化连续预测变量**：中心化后 0 = 均值，主效应就变成「平均水平处的效应」，可解释得多。
10. **交互作用存在时，往往无法对主效应做一般性陈述**（Q4.3 的答案就是「取决于股骨长」）。这不是模型的缺陷，而是系统的真实属性：两条不平行的线必然相交。
11. **「没有证据」≠「证据表明没有」**（absence of evidence is never evidence of absence）。p = 0.1 只是**不确定**，不是「无效应」的证明。报告时用 "We found no evidence that…"，绝不用 "We proved there is no…"。
12. **中心化改变什么、不改变什么**：只改截距（及其 SE / t / p），**斜率、斜率的 p 值、$R^2$、残差标准误、F 统计量全都不变**。
13. **$R^2$ 低不等于分析失败**：取决于研究目的是**推断**还是**预测**。
14. **`lm()` 对预测变量的顺序不敏感，`aov()` 敏感。** 这是本周与上周之间最重要的对照。ANOVA 中最后一项才是「控制了前面所有项」的效应；`lm` 中每个系数天然就是控制了其余全部变量的偏效应。
15. **多加一个无用的预测变量会降低统计功效**（消耗自由度、抬高标准误）→ Q3 中光强的 p 值从 0.0554 涨到 0.1745。**判断结论是否稳健要看效应量的方向与量级，不要只盯 0.05 这条线。**
16. **后向选择的两条硬规则**：① 每次只删 p 值最大的**一个**；② **只要一个变量还参与着模型中的交互作用，就绝不能删它**。
17. **不要 p-hacking**：不能试很多模型然后挑最合心意的报告。后向选择的价值就在于**可复现**。
18. **强制纳入变量的时机**：必须在**看数据之前**基于领域知识决定，事后决定会被（也应该被）质疑 cherry-picking。
19. **离群点不能因为「看着不顺眼」就删**；正确做法是**含/不含两种分析都做**，并在方法部分为任何排除给出充分论证。
20. **不能把 R 的输出直接粘进论文当表格**，也不能只贴表格不写文字陈述。表格要重新格式化、加单位、加表注。

### 统计假设与诊断

21. **线性回归的四大假设**（下节详列）中，**「响应变量必须正态分布」是个流传很广的误解**——正态性假设是针对**残差 (residuals)** 的，不是原始数据。
22. **不必对残差做正式的正态性检验**：样本小时检验不出真正的偏离，样本大时会检出无关紧要的偏离。**直接画图看**（直方图 + 残差 vs 预测值图）。
23. **正态性被违反时，效应量估计仍然可靠，受影响的是 p 值。** 所以如果 p 值极小（比如 1e-5），即使 p 值有两个数量级的偏差，结论依然稳固；但如果 p 值本来就在 0.08 附近，就必须向读者坦白「我们对这个效应没有多少把握」。
24. **异方差 (heteroscedasticity)** 常表现为「预测值大时残差也大」的喇叭形；对数变换常能解决。
25. **看到数据里有曲线，先想想要不要变换**（对数、立方根等）。变换最好有**理论依据**（如体积 ∝ 长度³、误差随均值缩放）。

---

### 附：线性回归的四大假设及其处理（完整版）

| # | 假设 | 违反的典型情形 | 如何检查 | 违反了怎么办 |
|---|---|---|---|---|
| **1** | **数据点相互独立 (independence)**：任一点的响应值不依赖于其他点的响应值 | **时间序列**（如纽约证券交易所收盘价：今天开盘价与昨天收盘价相似）→ **时间自相关 (temporal autocorrelation)**；同一个体重复测量；同一巢/同一样方内的个体 | 靠**实验设计**和对数据来源的思考，不是靠图 | 有时可转换（如分析**每日价格变化**而非收盘价），但**若市场有连续上涨/下跌的趋势就无效**。正规办法是**时间序列分析** (本课不讲) 或 **Week 06 的混合效应模型**。**野外课程中：靠仔细的实验设计保证独立性。** |
| **2** | **预测变量对响应有线性效应 (linearity)** | 股骨长 vs **脑容量**：股骨长确实能很好预测脑容量，但**关系不是线性的**；直线拟合会很差 | 散点图看有无**曲率**；残差 vs 预测值图呈**弧形/U 形** | **变换变量 (transformation)**。最好有**理论依据**：把动物身高按因子 $x$ 放大，股骨长增大 $x$ 倍，但脑容量是三维量，会增大 $x^3$ 倍 → 所以对**脑容量取立方根** $(\text{brain volume})^{1/3}$，关系即变为近似线性（figure 4.7b）。同理，质量 ∝ 长度³ → 取对数使之线性。 |
| **3** | **拟合模型中未解释的变异近似正态分布 (normality of residuals)** | 时薪模型的残差直方图有**明显的长右尾**（figure 4.8） | `hist(resid(s.lm), 20)` 目测。**不建议做正式检验**：样本小时检验无力，样本大时会对无关紧要的偏离过度敏感 | **变换响应变量**。长右尾 → 常用 **log 变换**：`ln_wage = log(ci$wage)`，然后**从头重跑后向选择**（最佳模型变成 `lm(ln_wage ~ mc_school + mc_age + male + mc_age*male)`）。变换后残差**仍有长尾，但两侧都有了——对称性是朝正确方向迈进的一步**。<br>**log 变换工资还有理论依据**：收入差距在高端往往绝对量更大（英国学术界：讲师薪级间隔约 £700/年，管理层高端薪级间隔约 £2,800/年，而副校长的薪酬包比教学科研人员高出几十万英镑）。<br>**如果不确定哪种做法更好，两种都做，看结果是否一致。** |
| **3b** | **离群点 (outliers)** —— 正态性偏离的一种特殊形式：残差异常大的点 | figure 4.8 最右边两个残差；figure 4.11 中点 [3.9, 2.0] 把回归线整个拽偏 | 残差直方图、散点图 | **不能仅因为不喜欢它对结果的影响就忽略它**——那等于因为不喜欢证据说的话就无视证据，**这不科学**。但如果有 **a priori 的理由**怀疑某点（如蚂蚁实验中那个下雨天），可以考虑排除，**并把解释限定在相应范围内（如"仅限晴天"），且必须在方法部分仔细论证**。最佳实践：**含/不含都分析一遍**（Practical Q6）。 |
| **4** | **同方差性 (homoscedasticity)**：每个数据点有相同的期望误差 | 时薪模型：预测工资低时预测很准，预测工资高时未解释变异变大（figure 4.12）→ **异方差 (heteroscedasticity)** | `plot(predict(s.lm), resid(s.lm))`，看点云带宽是否处处相同 | 简单**变换**常能解决：**当未解释变异随预测响应增大时，log 变换常有帮助**。若变换无效，研究者有时用**方差加权 (weighting variance)**（本课不讲）。<br>轻微违反通常不致命，但**要谨慎解释**——例如**要求更小的 p 值才肯推断存在关系**。 |

**当假设 2–4 被严重违反、且变换无法解决时的替代方案 → 秩相关检验。**

### 附：秩相关检验 (rank correlation tests)

**思想**：与前几章的 Wilcoxon、Kruskal–Wallis 一脉相承——**不看数值本身，而是把预测变量和响应变量各自排秩 (rank)，再看两组秩之间有没有关系**。

**检验的问题**：响应变量是不是预测变量的**单调函数 (monotonic function)**？即：响应值是否随预测值**一致地上升或下降**？

**优点**：
- **不假定**预测变量与响应变量之间的关系是**线性的**
- 对正态性、同方差性不敏感

**缺点**：
- **不能用来预测响应值**（没有可用的直线方程）
- 只能告诉你「两个变量是否倾向于同增同减」

#### Spearman's rho 检验（最著名的秩相关检验）

```r
cor.test(ci$wage, ci$school, method = "spearman", alternative = "greater")
```
```
	Spearman's rank correlation rho

data:  ci$wage and ci$school
S = 118738.6, p-value = 0.001864
alternative hypothesis: true rho is greater than 0
sample estimates:
      rho
0.2874973

Warning message:
In cor.test.default(...) : Cannot compute exact p-value with ties
```

**逐参数说明**：
- 前两个参数：要研究的**响应变量和预测变量**（`cor.test` 对二者是对称的，顺序不影响 rho）
- `method = "spearman"`：指定用 Spearman 秩相关
- `alternative = "greater"`：告诉 R 我们的 **a priori 假设**是两者**正相关**，因此做**单尾检验**
  - 若先验假设是负相关 → `alternative = "less"`
  - 若**没有先验预期** → **直接省略这个参数**（默认双尾 `"two.sided"`）
- **警告信息 "Cannot compute exact p-value with ties"**：当预测变量或响应变量里有**重复值 (ties)** 时，无法算出精确 p 值。**不必惊慌**——p 值仍能被估计，而且估计**非常准确**，R 报告的就是这些估计值。

**结果**：rho = 0.287，p = 0.0019 → 与线性模型一致，**工资与教育之间有强证据存在关系**。

#### Kendall's tau 检验

- 比 Spearman 用得少，但**更容易解释**。
- 检验统计量 tau 是 **concordance（一致性）**：如果我们从数据集中**随机选两个观测**并比较两个指标，**concordance 就是「在第一个指标上取值更高的那个观测，在第二个指标上也取值更高」的概率**。
- 放到加拿大收入的例子里：随机选两个人，比较他们的年龄和工资，**concordance 就是「年龄更大的那个人工资也更高」的概率**。
- Gilman 的个人偏好：「因为 concordance 容易理解，**我常常更喜欢 Kendall's tau 而不是 Spearman's rho。但两者几乎总是给出相似的结果！**」

```r
cor.test(ci$wage, ci$age, method = "kendall")
```

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| linear regression | 线性回归 | 用一条（超）平面描述数值预测变量如何预测数值响应变量的方法 |
| simple linear regression | 简单线性回归 | 只有一个预测变量的线性回归 |
| multiple linear regression | 多元线性回归 | 同时包含两个及以上预测变量的线性回归 |
| predictor | 预测变量 | 自变量，放在 `lm(y ~ x)` 的波浪号右边、`plot(x,y)` 的 x 轴 |
| response variable | 响应变量 | 因变量，放在波浪号左边、y 轴 |
| line of best fit | 最佳拟合线 | 使残差平方和最小的那条直线 |
| least squares / OLS | 最小二乘（法） | 通过最小化残差平方和来求解回归系数的准则 |
| residual / error | 残差 / 误差 | 实际观测值减去模型预测值，$e_i = y_i - \hat y_i$ |
| deviation | 偏差 | 某个值与参照值（均值或拟合线）之间的距离 |
| intercept | 截距 | 所有预测变量都为 0 时响应变量的预测值；回归线与 y 轴的交点 |
| slope | 斜率 | 预测变量每增加 1 单位、响应变量的预期变化量 |
| effect size | 效应量 | 本课中即回归系数（斜率），常记作 β 或 b，**必须带单位报告** |
| $R^2$ / coefficient of determination | 决定系数 | 预测变量解释掉的响应变量总变异的比例，0–1 |
| Adjusted R-squared | 调整决定系数 | 对预测变量个数施加惩罚的 $R^2$，便于比较不同复杂度的模型 |
| Estimate | 估计值 | `summary(lm)` 中该系数的点估计（截距或效应量） |
| Std. Error | 标准误 | 系数估计的不确定度；越小估计越精确 |
| t value | t 统计量 | $\hat\beta/\text{SE}(\hat\beta)$，检验该系数是否为 0 |
| Pr(>\|t\|) | p 值 | 若真实系数为 0，观察到这么极端结果的概率 |
| Residual standard error | 残差标准误 | 典型预测误差的大小 $\hat\sigma=\sqrt{\text{SS}_{res}/(n-p-1)}$，单位同响应变量 |
| F-statistic | F 统计量 | 整体模型检验：解释变异均方 / 未解释变异均方 |
| degrees of freedom (df) | 自由度 | 回归中残差自由度 = $n - p - 1$ |
| mean centring | 均值中心化 | 每个观测值减去该变量的均值，使 0 代表「平均水平」，让截距变得有意义 |
| indicator / dummy variable | 指示变量 / 哑变量 | 只取 0/1 的变量，把二分类预测变量转成数字 |
| baseline | 基线（组） | 指示变量中被编码为 0 的那一类，其他类相对它做比较 |
| dichotomous predictor | 二分类预测变量 | 只有两个取值的预测变量（如 m/f、english/other） |
| main effect | 主效应 | 某预测变量独立于其他预测变量的效应；含交互作用时是在另一变量 = 0 处估计的 |
| interaction | 交互作用 | 一个预测变量的效应取决于另一个预测变量的取值；R 中写 `a*b`，输出行名为 `a:b` |
| positive / negative interaction | 正 / 负交互作用 | 一个变量的效应随另一变量增大而增强 / 减弱 |
| controlling for | 控制…… | 在其他预测变量保持不变的前提下考察某变量的效应 |
| backward selection | 后向选择 | 从全模型开始，逐个删除 p 值最大的项，直到只剩显著项（或参与显著交互的项） |
| full model | 全模型 | 包含所有你感兴趣的预测变量与交互项的起始模型 |
| p-hacking | p 值操纵 | 尝试多个模型后专挑最符合自己故事的那个报告，是不当科研行为 |
| forcing a predictor | 强制纳入预测变量 | 基于先验知识把某个不显著的变量留在模型中以做控制；必须在看数据前决定 |
| collinearity | 共线性 | 两个及以上预测变量之间高度相关，导致无法拆解各自的效应、标准误膨胀 |
| extrapolation | 外推 | 在观测数据范围之外做预测，是危险且通常不可靠的做法 |
| independence | 独立性 | 各数据点的响应值互不依赖（回归假设 1） |
| temporal autocorrelation | 时间自相关 | 时间序列中相邻时点的观测值相关，违反独立性假设 |
| linearity | 线性性 | 预测变量对响应有线性效应（回归假设 2） |
| normality of residuals | 残差正态性 | 未解释的变异近似正态分布（回归假设 3）；**不是要求原始数据正态** |
| homoscedasticity | 同方差性 | 每个数据点有相同的期望误差（回归假设 4） |
| heteroscedasticity | 异方差性 | 未解释变异在数据集中分布不均（如随预测值增大而增大） |
| outlier | 离群点 | 残差异常大的数据点，可能强烈影响模型拟合 |
| transformation | 变换 | 按某个数学公式调整变量取值（log、立方根等）以修复假设违反 |
| log transformation | 对数变换 | 把乘性误差 / 幂次关系转化为加性 / 线性关系；治长右尾与异方差的常用手段 |
| omnibus test | 总括检验 | 只告诉你「某处存在差异」而不指明具体在哪的检验（如 ANOVA） |
| post hoc test | 事后检验 | 总括检验显著后，进一步定位差异位置的检验（如 Tukey） |
| rank correlation test | 秩相关检验 | 对预测与响应各自排秩后检验单调关系的非参数方法 |
| Spearman's rho | 斯皮尔曼 rho 检验 | 最著名的秩相关检验，`cor.test(..., method="spearman")` |
| Kendall's tau | 肯德尔 tau 检验 | 另一种秩相关检验，统计量是 concordance，更易解释 |
| concordance | 一致性 | 随机取两个观测，在一个指标上更高者在另一指标上也更高的概率 |
| monotonic function | 单调函数 | 始终上升或始终下降的关系（不必是直线） |
| simulation | 模拟 | 自己造一个「知道正确答案」的数据集来检验自己是否真的理解某个分析方法 |
| fluctuating asymmetry (FA) | 波动不对称性 | 两侧对称生物左右两侧差异的量度，可作为发育压力的信号 |
| snout-vent length (svl) | 吻肛长 | 从吻端到泄殖腔的长度，两栖类体长的标准量度 |
| sexual dimorphism | 性二型 | 同种雌雄个体在形态上的差异 |
| coercive gendering | 强制性别化 | 问卷强迫受访者在男/女之间二选一，会损失人群信息 |
| a priori | 先验的 / 事先的 | 在看数据之前就确定的（假设、变量选择、单尾方向等） |
| ties | 结（并列值） | 数据中的重复值，会使秩检验无法计算精确 p 值（但估计仍很准） |
| box plot | 箱线图 | 盒子为 25–75 百分位，中线为中位数，须长 1.5 倍四分位距 |

---

## 附：本周完整 R 代码速查

```r
# ---------- 读入与查看数据 ----------
ci = read.csv("can_inc.csv", header = TRUE)
head(ci)                                   # 只看前几行
data.frame(ci$school, mc_school)           # 并排对照两列，检查变换是否正确

# ---------- 简单线性回归 ----------
plot(ci$school, ci$wage,
     xlab = "years of education", ylab = "hourly wage in C$")
s.lm = lm(wage ~ school, data = ci)        # lm(响应 ~ 预测, data=)
summary(s.lm)
abline(s.lm, col = "red")                  # 加最佳拟合线

# ---------- 均值中心化 ----------
mc_school = ci$school - mean(ci$school)
mc_age    = ci$age    - mean(ci$age)
mc_apt    = ci$apt    - mean(ci$apt)

# ---------- 指示变量 ----------
male = as.numeric(ci$sex == "m")           # 推荐写法
# 等价的两步写法：
# male = rep(1, length(ci$sex)); male[which(ci$sex=="f")] = 0
english = rep(1, length(ci$lang)); english[which(ci$lang=="other")] = 0

# 分类变量作预测变量时的画图
plot(male, ci$wage, xlab="sex", ylab="wage in C$/h", xaxt="n")
axis(1, at = 0:1, labels = c("female","male"))
abline(s.lm, col = "red")

# ---------- 多元回归 ----------
s.lm = lm(wage ~ mc_school + male, data = ci)
s.lm = lm(wage ~ mc_school + mc_age + male + english, data = ci)

# ---------- 交互作用 ----------
s.lm = lm(wage ~ mc_school + mc_age + male + english
                 + mc_age*mc_school + mc_age*male, data = ci)
# 输出中交互项行名用冒号：mc_school:mc_age

# ---------- 分组作图（两条拟合线） ----------
plot(ci$school, ci$wage, col="blue",
     xlab="years of education", ylab="wage in C$/h")
points(ci$school[which(ci$sex=="f")],
       ci$wage[which(ci$sex=="f")], col="red")   # 覆盖女性点为红色
abline(0.2408, 0.9199, col="red")                # abline(截距, 斜率)
abline(0.2408 + 4.2502, 0.9199, col="blue")

# ---------- 残差诊断 ----------
hist(resid(s.lm), 20)                      # 正态性：残差直方图，20 个 bin
plot(predict(s.lm), resid(s.lm))           # 同方差性：残差 vs 预测值

# ---------- 变换 ----------
ln_wage = log(ci$wage)                     # 对数变换响应变量
# 变换后要从头重跑后向选择！

# ---------- 秩相关检验（假设严重违反时的替代方案） ----------
cor.test(ci$wage, ci$school, method = "spearman", alternative = "greater")
cor.test(ci$wage, ci$school, method = "kendall")     # 无先验方向时省略 alternative

# ---------- 数据子集与删除数据点 ----------
inc.lue  = anuran[which(anuran$species == "luetkenii"), ]
ele.pla.1 = ele.pla[ -which(ele.pla$sex == "M" & ele.pla$femur > 10), ]

# ---------- 换基线以检验另一组的斜率 ----------
inc.lue$female = as.numeric(inc.lue$sex == "F")
lm(svl ~ femur + female + femur*female, data = inc.lue)
```
