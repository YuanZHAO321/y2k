# Week 4 — 分类响应 vs 分类预测变量：二项检验、卡方检验与 Fisher 精确检验

> 材料来源：
> - Lecture 4.1 `Statistics for Natural Scientists L4P1(2)`（binomial test）
> - Lecture 4.2 `Statistics for Natural Scientists L4P2(2)`（chi-squared test）
> - 课堂录音转写 `EART11200 - 29-Nov-transcript`（现场课，主要是回归模型的深化复习 + 本周 practical 预告）
> - 手册 Gilman V2.2, **Chapter 5. Categorical responses to categorical predictors**（pp. 71–84）
> - Practical 5 及答案 key（Meyer & Uetz 2019 狼蛛数据、Tysall et al. 2020 果蝇标记数据、Longbottom et al. 2022 斗牛士蝽数据）

---

## 一、本周主题

本周是全课 6 周中的 **第 4 周**，也是**响应变量（response variable）第一次从数值型变成分类型**的一周。前三周的响应都是"量出来的数字"（身高、体重、股骨长度），预测变量或是分类（t-test / ANOVA）或是数值（linear regression）；本周处理的是"响应本身就是一个类别"的情形——蜜蜂选了红花还是黄花、雄蛛求偶了还是没求偶、硬币是正面还是反面。

课程主线上的位置（Gilman 反复用的那张"数据类型组合表"）：

| 检验 | 预测变量 Predictor | 响应变量 Response | 周次 |
| --- | --- | --- | --- |
| t-test / Wilcoxon | 分类（2 组） | 数值 | Week 1–2 |
| ANOVA / Kruskal-Wallis | 分类（>2 组） | 数值 | Week 2 |
| Linear regression / Spearman's rank correlation | 数值（或二分类） | 数值 | Week 3 |
| **binomial test / chi-squared test / Fisher's exact test** | **分类（或"无预测变量"，只与理论期望比）** | **分类** | **← Week 4（本周）** |
| Logistic regression | 数值 | 分类 | Week 5 |
| Mixed-effects models | 任意（数据不独立） | 任意 | Week 6 |

本周要掌握三件事：
1. **与理论期望（a priori expectation）比较**——二项检验 (binomial test) 与卡方拟合优度检验 (chi-squared goodness of fit test)；
2. **比较不同组之间的响应频率**——列联表 (contingency table) + 卡方独立性/关联性检验 (chi-squared test of association) 或 Fisher 精确检验 (Fisher's exact test)；
3. **omnibus 检验之后的 post hoc 两两比较**与 **Bonferroni 校正**，以及规范的文字报告方式。

---

## 二、核心概念

### 2.1 为什么分类响应需要新方法

Gilman 在 L4P1 的开场把这件事讲得很直白：t 检验、ANOVA、回归都在问"预测变量和响应变量之间有没有关系"，但**它们的响应都必须是一个数**——因为它们都要算均值、算方差、算残差平方和。如果响应是"红花 / 黄花 / 白花"，均值毫无意义。

分类响应的数据本质是**计数 (counts)**：每一次独立试验落进某一个类别里，我们统计每个类别里落了多少次。所以所有针对分类响应的检验，本质上都是在问：**观测到的这一组计数，和"零假设为真时应该出现的计数"差得够不够远？**

课上给的典型场景：
- 抛硬币 100 次得 62 次正面 —— 这枚硬币公平吗？
- 种群性别比是否偏离 1:1？（每个个体是一次 trial，结果是 male / female）
- 某足球队赢球是否比随机更频繁？
- 蜜蜂在红/黄/白三色花之间有没有偏好？
- 雄狼蛛是否更愿意向处女雌蛛求偶？

### 2.2 二项检验 (binomial test)

**用在什么场景**：只有**两种可能结果**的一系列独立试验，检验"成功"的概率是否等于某个 *a priori* 指定的值 $p_0$。

**逻辑推导（L4P1 用抛 7 次硬币讲透）**：
设单次试验出正面的概率为 $p$，出反面的概率为 $(1-p)$。

- 7 次全正面（0 反面）：$p \times p \times \cdots \times p = p^7$，只有 HHHHHHH 一种排列。
- 6 正 1 反：任何一个具体序列的概率都是 $p^6(1-p)$（无论那个反面出现在第几次，都是 6 个 $p$ 乘 1 个 $(1-p)$）；反面可以出现在 7 个位置中的任意一个，所以总概率 $7p^6(1-p)$。
- 5 正 2 反：任一具体序列概率 $p^5(1-p)^2$；排列数用 **"n choose k"（二项系数）**：

$$\binom{n}{k}=\frac{n!}{k!\,(n-k)!}$$

  其中 $n!$（n 的阶乘）是 1 到 n 所有整数的乘积，例如 $7!=7\times6\times5\times4\times3\times2\times1=5040$。这里 $\binom{7}{2}=\frac{5040}{2\times120}=21$，所以总概率 $21p^5(1-p)^2$。

把"2 个或更少反面"的三种情况加起来：

$$P(\text{tails}\le 2)=p^7+7p^6(1-p)+21p^5(1-p)^2$$

**一般形式**（n 次试验中出现 x 次或更少"反面"的精确概率）：

$$P(X\le x)=\sum_{k=0}^{x}\binom{n}{k}\,p^{\,n-k}\,(1-p)^{k}$$

符号含义：
- $n$：独立试验总次数
- $k$：某一类结果（这里是"反面"）出现的次数
- $x$：我们观测到的那个数（求"$x$ 或更极端"的累积概率）
- $p$：零假设下单次试验出"正面"的概率
- $\binom{n}{k}$：从 $n$ 次里挑 $k$ 次为反面的排列方式数

**手册里的等价表（80 只雌蛛选深腿/浅腿雄蛛）**——手册用 $n=2,3,4$ 的小表把这个组合逻辑展示了一遍，例如 $n=3$：

| 选深腿雄蛛数 $k$ | 单一实现的概率 | 可能的实现 | 实现数 | 总概率 |
| --- | --- | --- | --- | --- |
| 3 | $p^3$ | DDD | 1 | $p^3$ |
| 2 | $p^2(1-p)$ | DDL, DLD, LDD | 3 | $3p^2(1-p)$ |
| 1 | $p(1-p)^2$ | DLL, LDL, LLD | 3 | $3p(1-p)^2$ |
| 0 | $(1-p)^3$ | LLL | 1 | $(1-p)^3$ |

要求"至少 $k$ 次"，就把最后一列里合适的格子加起来。

**关键性质**：
- **前提假设**：观测来自**独立试验 (independent trials)**。在狼蛛数据里，这意味着某一只雌蛛的选择不影响别的雌蛛的选择。
- 二项检验是 **精确检验 (exact test)**：p 值是**精确算出来的**，不是从某个近似分布里估的。因此 **p 值的准确性不依赖样本量**，**小样本也能用**。
- 只能处理**两类**结果。

### 2.3 卡方拟合优度检验 (chi-squared goodness of fit test)

**用在什么场景**：把每一类的**观测计数**与**理论期望计数**比较，检验观测是否偏离 *a priori* 期望。相对二项检验的最大优势是——**类别可以多于两个**。

**逻辑（L4P2 用大黄蜂选花颜色讲透）**：27 只蜜蜂在红/黄/白三色花间选择，观测到 4 / 15 / 8。如果完全随机选，每色期望 $27/3=9$。

| | Red | Yellow | White | |
| --- | --- | --- | --- | --- |
| **visits（观测 O）** | 4 | 15 | 8 | |
| **expectations（期望 E）** | 9 | 9 | 9 | |
| **differences (O−E)** | −5 | +6 | −1 | |
| **(O−E)²/E** | 2.78 | 4.00 | 0.11 | |
| **χ²** | | **6.89** | | ← 三格求和 |

计算细节：$(-5)^2/9=25/9=2.78$；$6^2/9=36/9=4.00$；$(-1)^2/9=1/9=0.11$；求和 $=6.89$。自由度 $df=C-1=3-1=2$，得 $p\approx0.032$。

**为什么要平方再除以 E**：平方是为了让正负偏差不互相抵消；除以 E 是为了**标准化**——期望值为 100 的格子偏差 5 是小事，期望值为 5 的格子偏差 5 是大事。

**前提假设 / 何时能用**：
- 观测相互独立；
- **每个格子的期望频数都要大于 5**（手册原话："reasonably accurate as long as the expected number of observations in every cell is greater than 5"）。注意是**期望**频数不是观测频数。
- 卡方检验用的是**近似分布**，所以样本太小时 p 值不可靠 → R 会给 `Warning message: Chi-squared approximation may be incorrect`。
- **假设不成立时的替代**：改用 **Fisher 精确检验**（或二类情形下的二项检验）。

**卡方检验永远是双尾的**——手册明确指出：狼蛛数据里 `chisq.test` 的 p 值（2.152e-05）大约是 `binom.test` 单尾 p 值（1.265e-05）的两倍，正是因为卡方检验不区分方向，只问"偏差有多大"。

### 2.4 卡方分布 (chi-squared distribution)

若零假设为真、数据是随机产生的，那么上面构造出来的统计量会服从**自由度为 df 的卡方分布**。要点：
- 卡方统计量恒 $\ge 0$（因为是平方和），分布右偏；
- 分布的均值等于自由度 df；
- 实际使用时**只看右尾**：p 值 = 在零假设下看到"至少这么大"的卡方统计量的概率。这就是为什么 p 值虽然对应"双尾的假设"，但概率计算只取上尾。
- df 越大，分布越往右移、越扁平——所以同样大的 χ² 值，df 越大 p 值越大。

### 2.5 列联表 (contingency table)

**定义**：行代表一个分类变量的各水平，列代表另一个分类变量的各水平，每个格子里放**落进该组合的观测次数（计数）**。

Practical 5 的例子：

| | mated female | virgin female |
| --- | --- | --- |
| **male did not court** | 20 | 9 |
| **male courted** | 54 | 70 |

左上格 = "遇到已交配雌蛛且没有求偶"的雄蛛数，右上格 = "遇到处女雌蛛且没有求偶"的雄蛛数，依此类推。

**列联表本身就是一种"合成 (synthesis)"**——Practical 特别强调：我们不能把原始数据直接丢给读者让他们自己整理，但列联表把一大堆分类观测浓缩成少量计数，**是可以直接作为图表项 (display item) 呈现的**，只要配上清晰的行列标签和图注 (caption)。

### 2.6 独立性 / 关联性检验的逻辑：经验期望 (empirical expectation)

拟合优度检验用的是**理论期望**（如"各色花机会均等"）。但很多时候我们**没有**理论期望，只想问"两组之间的响应频率有没有差异"。L4P2 用两种蜜蜂访红/黄花的例子讲了怎么造一个**经验期望**：

**观测表**：

| Observed | Yellow | Red | 行合计 |
| --- | --- | --- | --- |
| Species 1 | 24 | 13 | **37** |
| Species 2 | 71 | 19 | **90** |
| **列合计** | **95** | **32** | **127** |

**造期望的核心思想**：如果行变量与列变量**独立**（即每个物种访问每种颜色的倾向相同），那么"落进某格"的概率就等于**行边际概率 × 列边际概率**：

- Species 1 的比例 $=37/127=0.291$；Species 2 $=90/127=0.709$
- Yellow 的比例 $=95/127=0.748$；Red $=32/127=0.252$
- Species 1 × Yellow 的期望比例 $=0.291\times0.748=0.218$ → 期望计数 $=0.218\times127=27.7$

| Expected | Yellow | Red | 行合计 |
| --- | --- | --- | --- |
| Species 1 | 27.7 | 9.3 | 37 |
| Species 2 | 67.3 | 22.7 | 90 |
| **列合计** | 95 | 32 | 127 |

**注意期望表的行合计、列合计与观测表完全一致**——这是检查计算是否正确的最好办法。

### 2.7 Fisher 精确检验 (Fisher's exact test)

**用在什么场景**：列联表的关联性检验，尤其是**格子计数很小（期望频数 < 5）**的时候。

**逻辑**（与二项检验同源）：Fisher 精确检验在**固定所有行合计与列合计**的前提下，枚举所有可能的表格排布，精确计算"偏差至少和观测一样极端"的概率之和。

手册的说明很具体：设 $(d, l)$ 分别是在暗处试验、亮处试验中被选中的深腿雄蛛数，观测为 (41, 18)。检验就把 $P(41,18)+P(42,17)+P(43,16)+\cdots$ 一路加下去（每一步行列合计保持不变）。

**关键性质**：
- **精确检验** → p 值精确，**对小样本不敏感**，所以格子计数 < 5 也没问题；
- **缺点**：观测总数很大时，枚举所有排布**计算量爆炸**，R 会算不出来（fails to return a result），这时只能退回卡方检验的近似 p 值。
- 可以做**单尾**：`alternative="greater"` / `"less"`。
- **Fisher 检验的 alternative 方向必须想清楚**（手册专门警告）：用 `greater` 时，问的是"**第一行的响应在第一列的条件下是否更频繁发生**"；用 `less` 则是"是否更不频繁"。行列的摆放顺序会改变含义。

**两种检验的分工总结**：

| | 卡方检验 chisq.test | Fisher 精确检验 fisher.test |
| --- | --- | --- |
| p 值 | 近似（基于卡方分布） | 精确（枚举） |
| 小样本 | 期望 < 5 时不可靠，R 报警告 | 完全可用 → **首选** |
| 大样本 | 快速可靠 | 可能算不出来 → 只能用卡方 |
| 尾数 | 永远双尾 | 可单尾可双尾 |
| 表的大小 | 任意 r × c | 任意 r × c（大表慢） |

### 2.8 omnibus 检验与 post hoc 两两比较

**omnibus（总体/综合）检验**：卡方检验和 Fisher 检验都是 omnibus 检验，与 ANOVA 同理——它们告诉你"**在整张表里的某个地方存在非随机的关联**"，但**不告诉你是哪一对**。

Practical 原话：*"the chi-squared test does NOT tell us which groups are significantly different from which others."*

**post hoc 做法**：把大表拆成一个个 2×2 子表（或对两类做二项检验），逐对检验。

**多重比较问题 (multiple testing issue)**：做 3 个两两比较，每个都用 0.05 作阈值，那么"至少有一个因随机而显著"的总概率会**大于** 0.05。

**Bonferroni 校正（又称 Dunn–Bonferroni correction，由 Olive Jean Dunn 首倡）**：

$$\alpha_B=\frac{\alpha}{m}$$

其中 $\alpha$ 是整体显著性水平（通常 0.05），$m$ 是要做的两两比较总数，$\alpha_B$ 是每一次比较所用的新阈值。三色花的例子：$\alpha_B=0.05/3=0.0167$。

**代价**：每多做一次比较，所有比较的阈值都被压低一次 → **统计功效 (power) 下降**。

**减少代价的正当做法**：**在收集数据之前**就决定只做其中一个子集的比较。手册举例：若某狼蛛物种的簇毛腿总是深色的，我们其实只关心两个比较（tufted vs dark 检验"簇毛"的效应，dark vs light 检验"颜色"的效应），那么 $\alpha_B=0.05/2=0.025$，功效更高。

**⚠ 绝对不能做的事（老师在 slides 里用大写强调）**：先看数据，猜哪些对可能显著，再只做那些比较。这叫 **HARKing (Hypothesising After the Results are Known)**，会系统性地偏倚结果、让 p 值失效，是许多学科的重大问题。**选哪些比较必须在看数据之前定下来。**

### 2.9 自定义零期望

L4P2 最后强调的一个易忽略点：拟合优度检验的零期望**不一定是"均等"**。
- 实验室里每只蜜蜂面对红黄白各一朵 → 零期望 $(1/3,1/3,1/3)$ 合理；
- 野外若红花占 40%、白花占 40%、黄花只占 20% → 零期望应设为 $(0.4, 0.2, 0.4)$，即"蜜蜂按花的丰度随机访问"。这样得到的 p 值才是对该实验设计而言正确的 p 值。

同理手册指出：若每次交配试验里是"1 只浅腿 + 2 只深腿"雄蛛，`binom.test` 的零假设概率就该写 2/3 而不是 0.5。

---

## 三、公式与图表

### 3.1 核心公式汇总

**(1) 二项系数**
$$\binom{n}{k}=\frac{n!}{k!\,(n-k)!}$$

**(2) 二项检验累积概率**
$$P(X\le x)=\sum_{k=0}^{x}\binom{n}{k}\,p^{\,n-k}(1-p)^{k}$$

**(3) 卡方统计量（通用形式）**
$$\chi^{2}=\sum_{\text{all cells}}\frac{(O-E)^{2}}{E}$$
- $O$ = observed，该格的**观测计数**
- $E$ = expected，该格在零假设下的**期望计数**
- 求和遍历表中**每一个格子**

**(4) 拟合优度检验的期望计数**
$$E_i=N\times p_i$$
- $N$ = 观测总数
- $p_i$ = 零假设下落进第 $i$ 类的概率（可以是 $1/C$，也可以是自定义的理论比例）

**(5) 列联表（独立性检验）的期望计数**
$$E_{ij}=\frac{R_i\times C_j}{N}$$
- $R_i$ = 第 $i$ 行的行合计 (row total)
- $C_j$ = 第 $j$ 列的列合计 (column total)
- $N$ = 全表总观测数

  等价的"比例写法"（slides 用的形式）：$E_{ij}=N\times\dfrac{R_i}{N}\times\dfrac{C_j}{N}$，即**行边际比例 × 列边际比例 × 总数**。

**(6) 自由度**

| 情形 | 自由度 |
| --- | --- |
| 拟合优度检验（一行 $C$ 个类别） | $df=C-1$ |
| $r\times c$ 列联表 | $df=(r-1)(c-1)$ |

**为什么是这样**：期望表的行合计与列合计被固定为与观测表相同。在一张 $r\times c$ 的表里，一旦你填好了左上角 $(r-1)\times(c-1)$ 个格子，剩下的格子就被行列合计"逼"出来了，没有自由选择的余地。所以自由度 $=(r-1)(c-1)$。拟合优度是 $1\times C$ 的表，只有总数 $N$ 被固定，填好 $C-1$ 个格子后最后一个就定了，故 $df=C-1$。

例：
- 三色花拟合优度：$df=3-1=2$
- 2×2 列联表：$df=(2-1)(2-1)=1$
- 3×3 列联表：$df=(3-1)(3-1)=4$（手册的 tufted/dark/light × rocks/litter/grass 例子，$\chi^2=26.9084$, $df=4$, $p=2.074\times10^{-5}$）
- 5×2 列联表（Practical Q4 果蝇）：$df=(5-1)(2-1)=4$

**(7) Bonferroni 校正**
$$\alpha_B=\frac{\alpha}{m}$$

### 3.2 完整算例 A：三色花拟合优度（手算 → R 验证）

观测 $O=(4,15,8)$，$N=27$，零假设各色等概率 → $E=(9,9,9)$。

$$\chi^{2}=\frac{(4-9)^2}{9}+\frac{(15-9)^2}{9}+\frac{(8-9)^2}{9}=\frac{25}{9}+\frac{36}{9}+\frac{1}{9}=2.78+4.00+0.11=6.89$$

$df=2$，$p\approx0.032<0.05$ → 蜜蜂并非等概率地选择三种颜色。

### 3.3 完整算例 B：2×2 列联表期望频数与卡方（Practical Q1 狼蛛数据，手算全过程）

观测表：

| | mated (m) | virgin (v) | **行合计 $R_i$** |
| --- | --- | --- | --- |
| **did not court (n)** | 20 | 9 | **29** |
| **courted (y)** | 54 | 70 | **124** |
| **列合计 $C_j$** | **74** | **79** | **N = 153** |

用 $E_{ij}=R_iC_j/N$ 逐格算期望：

| | mated | virgin |
| --- | --- | --- |
| **did not court** | $29\times74/153=14.03$ | $29\times79/153=14.97$ |
| **courted** | $124\times74/153=59.97$ | $124\times79/153=64.03$ |

检查：行合计 $14.03+14.97=29$ ✓；列合计 $14.03+59.97=74$ ✓。

**未校正的卡方统计量**（每格 $|O-E|$ 都是 5.974，这是 2×2 表的固有性质）：

$$\chi^{2}=\frac{5.974^2}{14.03}+\frac{5.974^2}{14.97}+\frac{5.974^2}{59.97}+\frac{5.974^2}{64.03}=2.544+2.383+0.595+0.557=6.08$$

$df=1$ → $p\approx0.0137$。

**但 R 给出的是 $p=0.0239$** —— 因为 **R 对 2×2 表默认施加 Yates 连续性校正 (Yates' continuity correction)**：

$$\chi^{2}_{\text{Yates}}=\sum\frac{(|O-E|-0.5)^{2}}{E}$$

代入 $|O-E|-0.5=5.474$：

$$\chi^{2}_{\text{Yates}}=\frac{5.474^2}{14.03}+\frac{5.474^2}{14.97}+\frac{5.474^2}{59.97}+\frac{5.474^2}{64.03}=2.136+2.001+0.500+0.468=5.10$$

$df=1$ → $p=0.0239$ ✓ 与 Practical 给出的报告完全一致。

> **重要提示**：如果你手算了却对不上 R 的输出，八成就是这个连续性校正。想关掉它用 `chisq.test(court.mate.table, correct = FALSE)`。校正会让 p 值**变大**（更保守）。注意 `chisq.test(c(59,21), p=c(0.5,0.5))` 这种**拟合优度**调用**不做**该校正，只有 2×2 矩阵才做。

### 3.4 完整算例 C：3×3 列联表期望表（手册狼蛛 origin × phenotype）

观测：

| | rocks | litter | grass | **total** |
| --- | --- | --- | --- | --- |
| **tufted-legged** | 30 | 4 | 5 | **39** |
| **dark-legged** | 9 | 18 | 1 | **28** |
| **light-legged** | 6 | 3 | 4 | **13** |
| **total** | **45** | **25** | **10** | **80** |

边际比例：tufted $39/80=0.4875$，dark $28/80=0.35$，light $13/80=0.1625$；rocks $45/80=0.5625$，litter $25/80=0.3125$，grass $10/80=0.125$。

期望（$0.5625\times0.4875\times80=21.94$，依此类推）：

| | rocks (0.5625) | litter (0.3125) | grass (0.125) |
| --- | --- | --- | --- |
| **tufted (0.4875)** | 21.94 | 12.19 | 4.88 |
| **dark (0.35)** | 15.75 | 8.75 | 3.50 |
| **light (0.1625)** | 7.31 | 4.06 | 1.63 |

注意：**有 3 个格子的期望频数 < 5**（4.88、3.50、4.06、1.63 共 4 个），所以卡方检验会报警，**应以 Fisher 精确检验为准**（$p=1.291\times10^{-5}$）。

### 3.5 图表的判读与制作要点

**饼图 (pie chart)**
- 适合展示**比例**数据，因为各扇区之和必然为 1——一类的比例上升，另一类必然下降，这个"此消彼长"的性质饼图能表现，条形图不能。
- 手册建议**把计数写进标签**（如 `"tufted (39)"`），方便读者比较扇区大小。

**条形图 (bar chart)**
- 视觉上更容易精确比较各类的高低，很多作者偏好它。
- 有 y 轴刻度时，标签里就不必再写计数。
- 显著性差异用括号 + `*`（显著）、`°`（marginally significant，边缘显著）标注，并在图注里解释这些符号。

**⚠ 手册明确禁止**：**不要对同一个结果同时画饼图和条形图**——同一结果没有必要用两张图报告两次。

**比较不同组之间的响应频率时**：
- 条形图通常最直观；
- **画频率 (frequency/proportion) 而不是原始计数**，因为读者关心的是比例；
- 各组样本量写进 x 轴标签（如 `rocks\n(n = 45)`，`\n` 在 R 里表示换行）；
- **只有两类响应时，每组画一根柱子就够了**——没画出来的那一类必然是 1 减去它，画第二根不增加任何信息；
- **多于两类响应时，用堆叠条形图 (stacked bar chart)**，并加图例。

---

## 四、课堂补充

> ⚠ **重要说明**：本周的现场课录音（`EART11200 - 29-Nov`）**并没有重讲卡方检验**。Gilman 明确说卡方检验"probably the shortest and most straightforward of the tests"，所以把线上录播留给学生自己看，现场课时间几乎全部用来**深化上周的回归模型**（他说回归"is really the core of this unit"，"if there's only one thing that you walk out of this unit feeling comfortable with, regression models would be the best one"）。这部分内容与 Practical 5 的 Q5、Q6 直接对应，必须记下来。

### 4.1 学习心态（L4P1 开场，slides notes）

Gilman 花了整整一页讲学习统计的心态：学任何技能时都容易只盯着"还有多少不会"，学统计尤其如此——每学一个方法，就会发现还有更多方法、更多数据类型、更多细节不懂，而且**这个过程永远不会停止**。所以要时不时回头看：四周前多数人从没打开过 R，现在已经能读数据、改数据、做一整套基础统计分析、画图。"You haven't just memorized some facts – you have learned to use a new and powerful tool, and to think about data in a new way."

### 4.2 关于公式要不要背（L4P1 Slide 22）

拿到 R 输出的 p 值之后，还需要知道二项检验的公式吗？——"You probably don't. At the very least, you certainly shouldn't feel like you have to memorise it." **但**大致理解检验在干什么很重要：*"There is no magic in statistics. Tests work in particular ways, and for particular reasons. If we understand those, then it is easier to apply them correctly, and easier to recognize when something has gone wrong."*

### 4.3 现场课：加拿大收入数据的回归深化

数据集：1993 年加拿大安大略省收入调查，随机取 100 人。变量：`wage`（自报时薪，加元/小时）、`age`、`school`（受正规教育年数；加拿大 6 年小学 + 6 年中学 = 12 年，超出部分为大学）、`city`、`language`（英语 / 其他，安大略毗邻魁北克故有大量法语母语者，其余语言全部归入 other）、`sex`。

**关于数据本身的科学诚实性（老师专门花时间讲的）**：这个叫 `sex` 的变量其实很可能是**自报性别认同 (self-reported gender)**——1993 年的纸质问卷只给了 male/female 两个选项，非二元性别者要么随便填一个要么直接扔掉问卷，我们不知道发生了什么。**take-home message：在科学中我们经常拿不到真正想要的数据，甚至不清楚"真正想要的数据"是什么，但常常能找到一个足够接近的替代指标 (surrogate)。**

**(1) 简单线性回归**

```r
CI = read.csv("CanadianIncome.csv", header = TRUE)   # 读入数据，第一行是列名
plot(wage ~ age, data = CI)                          # 先画散点图看模式
wage.lm = lm(wage ~ age, data = CI)                  # lm() 建线性模型；wage ~ age 读作"wage 如何依赖 age"
                                                     # data = CI 告诉 R 去 CI 这个数据框里找这两列
summary(wage.lm)                                     # 看模型结果；直接运行 lm() 不报错只说明跑通了，要 summary 才看得到输出
```

输出解读要点（老师逐栏讲）：
- **`age` 那一行**才是我们关心的答案；
- **最后一列的 p-value** 远小于 0.05 → age 对 wage 有效应；
- **`Estimate` 列 = 0.1767**：预测变量每变化一个单位，响应变量变化多少。这里就是**每老一岁，时薪多 17.7 加分**。因为它就是"响应随预测变量单位变化的量"，所以**它就是这条线的斜率**；
- **`(Intercept)` 行 = 8.69**：预测变量为 0 时响应的期望值，也就是这条线与 y 轴的交点。把 x 轴延长到包含 0 就能直接看到；
- **`Multiple R-squared` ≈ 0.088**：预测变量解释了数据中约 **8.8%** 的变异，剩下 92% 未被解释。
  - 老师的评论很值得记：**物理学家看到 8% 会说这是垃圾（他们习惯 90%），但对自然科学家来说 8% 已经相当不错**——自然科学的数据里干扰因素太多了。

**(2) 均值中心化 (mean centering)**

问题：age = 0 时的截距在加拿大毫无意义（小孩不工作）。而且**一般原则：不要外推到观测数据范围之外**（本数据 age 约 17–68 岁，只能在此区间内推断）。

```r
mean(CI$age)                        # 计算平均年龄，约 37.9
CI$MC_age = CI$age - mean(CI$age)   # 新建"均值中心化年龄"列，直接塞回 CI 数据框
cbind(CI$age, CI$MC_age)            # cbind 把两列并排放，方便肉眼核对
wage.lm2 = lm(wage ~ MC_age, data = CI)
summary(wage.lm2)
```

结果：
- **`MC_age` 的 Estimate 和 p 值与原模型完全一致（0.1767）** —— 中心化不改变斜率，只是移动了 x 轴；
- **截距从 8.69 变成 15.39**，而且**这次它有意义了**：它是**数据集中平均年龄那个人的预期时薪**。因为中心化后平均年龄被记为 0。
- 老师总结：**当原始截距落在数据范围之外时，均值中心化常常能把截距变成一个真正有用、有解释力的量。** 若研究的是从负摄氏度到正摄氏度的温度，0 本身有意义，就不必中心化；但年龄 0、股骨长 0 都不是有意义的点（"if a frog has no femurs, it's not because it's tiny"）。

**(3) 多元回归 (multiple regression)**

```r
wage.lm3 = lm(wage ~ age + sex, data = CI)   # 加号表示"再加一个预测变量"，可以加任意多个
summary(wage.lm3)
```

- `age` 仍显著，且 p 值降了一个数量级，斜率略陡（约 0.21）；
- 出现 **`sexM`** 这一行：R **没有**被告知哪个性别做基线，它**按字母序自动选**——F 在 M 前面，所以**女性是基线 (baseline)**，行名后缀的 `M` 表示"这是'身为男性'的效应"；
- 估计值 **+5.07** → **同龄条件下男性时薪比女性高 5.07 加元**；
- **多元回归的关键价值**：每个预测变量的效应都是**控制了其他预测变量之后**的效应（"the effect of gender controlling for age"），这是 t 检验做不到的。
- 这是**可加模型 (additive model)**：性别差在所有年龄上都是同一个 5.07，两条线**平行**。

画图：

```r
coef(wage.lm3)                                  # 取出系数表：intercept, age, sexM
plot(wage ~ age, data = CI, col = ...)          # 散点，按性别着色
abline(4.27, 0.21, col = "red")                 # 女性：截距 = 总截距，斜率 = age 的系数
abline(4.27 + 5.07, 0.21, col = "blue")         # 男性：截距 = 总截距 + sexM 效应，斜率相同
```

**(4) 交互作用 (interaction) —— 老师说这是"最重要、也是最难懂"的概念**

> **定义（务必背下来）：An interaction means that the effect of one predictor depends on the value of another.**

```r
wage.lm4 = lm(wage ~ age + sex + age * sex, data = CI)   # 乘号表示交互项
summary(wage.lm4)
```

`age:sexM` 一行 p 值极低 → **年龄对工资的效应在两性之间不同**。

**有交互项时如何读主效应（main effects）——这是最容易读错的地方**：

> **当模型里有交互项时，各主效应的报告值都是"另一个预测变量取 0 时"的值。**

- 报告的 `age` 效应 = **基线性别（女性）**的年龄效应。这里 p = 0.98 → **本数据中没有证据表明女性工资随年龄变化**；
- 报告的 `sexM` 效应 = **age = 0 时**两性的工资差。它居然是**负的**！看起来矛盾（前面明明说男性挣得多），原因是：女性的线几乎水平、男性的线上升，把两条线**外推回 age = 0**，男性的线就跌到女性之下。而 age = 0 本来就是荒谬的外推点；
- `age:sexM` 交互项 = **男性的年龄效应比基线多出多少**。这里男性每老一岁多挣约 **38 分/小时**，而女性没有变化。

**交互 + 均值中心化**：把 `age` 换成 `MC_age` 重跑，交互项与基线性别的年龄效应不变，但 `sexM` 的效应变成了"**在群体平均年龄处**两性的工资差"，这就有意义了。老师同时提醒：**一旦有交互作用，"男性是不是比女性挣得多"这个问题本身就不再完全有意义了——答案是"看年龄"**：老年男性明显高于老年女性，年轻人则没有明显差异。

**(5) 全模型与模型简化**

```r
full.lm = lm(wage ~ age + sex + school + language + age*sex + school*sex, data = CI)
summary(full.lm)
```

- `school:sex` 交互不显著 → **不显著的交互项应该删掉**，因为交互项留在模型里会让其他主效应难以解释；
- 删掉后重跑，模式更清晰：男性每岁多挣约 **36 分/小时**、女性无年龄效应；**每多受一年教育多挣约 90 分/小时**（两性相同，因为没有 school×sex 交互）；
- `age` 主效应看起来不显著，但**不能把它从模型里拿掉，因为它参与了 age×sex 交互**（层级原则）；
- `language` 完全没有效应 → 留还是删？**没有唯一正确答案**，取决于你对系统的理解：如果别的省份的数据表明母语确实影响工资，就该保留作为控制变量；如果各处都没效应，那可能只是噪声，可以删。**关键是要在方法描述里说清楚你为什么这么做。**

**(6) 二次项 (quadratic term)：让直线弯曲**

学生观察到散点先升后降。老师的处理：

```r
q.lm = lm(wage ~ age + I(age^2) + sex + age*sex + I(age^2)*sex, data = CI)
summary(q.lm)   # age²×sex 的 p ≈ 0.9 → 曲率在两性间无差异，删掉这个交互
q.lm2 = lm(wage ~ age + I(age^2) + sex + age*sex, data = CI)
summary(q.lm2)  # 保留二次项：工资随年龄先升后降，男性比女性每岁多约 24 分/小时
```

**为什么"线性模型"可以拟合曲线**：linear model 的"线性"指的是**对参数线性**，把 $age^2$ 当作一个新的预测变量放进去，模型仍是线性模型，但拟合出来的曲线可以弯。

**对"先升后降"的科学解释（老师引导学生给出）**：不太可能是高薪者突然开始少挣，更可能是**留存偏倚 (selection/attrition bias)**——高薪者到了年纪**能退休就退休了**，而拿加拿大最低工资的人**退不起休**，只能继续工作，所以尾部剩下的都是低薪者。此外 60 岁以上仍在劳动力市场中的以女性居多，这也可能与曲率有关。**这类模式无法从本数据里判定，但可以送社会科学家去实地提出新问题。**

**(7) 科学的社会价值（老师的题外话，值得记）**

老师强调他用这个数据集不是在说"事情本该如此"，而是：科学的价值之一在于**指认问题并加以修正**。1993 年的数据显示"年轻人两性无差异，老年人有差异"，当时人们据此论证"这个问题 30 年后会自然消失"——**30 年后的今天这个模式仍然存在**。所以问题没有自己解决，但**作为科学家能拿出证据把它指出来，本身就是推动改变的手段**。

### 4.4 现场课末尾：本周 practical 预告

- 本周做 **Practical 5**，用卡方检验；
- practical 末尾还有更多回归模型练习；
- **starter code 里第一次出现了自定义函数 (function)**：`ct.to.barplot()`，在代码第 29 行开始（RStudio 里行号旁的小三角可以折叠/展开函数体）。它把一张列联表直接转成条形图。**激活方法：选中整个函数的代码行运行一次**，之后就能像内置函数一样调用。老师明说："I'm not telling you this because I expect anyone to write functions"——只是给你一个省事的工具，比每次手画卡方图轻松得多。
- R 里写函数的意义：**把一组反复要用的命令打包成一个名字，以后调用这个名字就等于执行整套命令。**

---

## 五、Practical 要点

### 5.1 目标（practical 开头写明）

完成 Practical 5 后你将能够：
1. **创建列联表**来研究"分类预测变量 + 分类响应变量"的数据；
2. **执行卡方检验并清晰、简洁地报告结果**。

### 5.2 生物学背景（Q1–Q3：狼蛛的雄性择偶）

一般规律：多数动物中雌性配子少而大 → 雄性繁殖受限于能接触到的雌配子数 → **雄性倾向于不挑剔、多交配**；雌性繁殖受限于自己能产多少配子 → 多交配不增加适合度，但**优质配偶的好基因能提升后代适合度** → **雌性更挑剔**。

**蜘蛛是例外，因为雌蛛很危险**：雄蛛求偶时可能被雌蛛吃掉，因此演化理论预测**雄蛛应当非常挑剔**。

Meyer & Uetz (2019) 研究刷腿狼蛛 *Schizocosa ocreata*：
- *Schizocosa* 属雌蛛能**储存精子**，一生交配一次可能就够给所有卵受精 → 已交配的雌蛛再被求偶时可能不愿再交配。**雄蛛能否察觉并回避已交配雌蛛？**
- **饥饿的雌蛛可能更危险**（可能把靠近的雄蛛当食物而不是配偶）→ 饥饿雌蛛是否更不愿交配？雄蛛是否更不愿向它们求偶？
- 实验设计：每次试验一只雄蛛 + 一只雌蛛放进 arena；雌蛛为处女(v)/已交配(m)、刚喂食(f)/刚饥饿(s)；记录雄蛛**是否求偶**、双方**是否交配**。

数据文件 `Meyer_and_Uetz_2019.csv`，列：`Female`、`Male`（个体 ID）、`MatingStatus`（v = virgin, m = mated）、`HungerStatus`（f = fed, s = starved）、`Courtship`（y / n）等。

### 5.3 Question 1：雄蛛是否更愿意向处女雌蛛求偶

**问题的本质是"关联 (association)"**：求偶是否不成比例地与"virgin"关联，不求偶是否不成比例地与"mated"关联。

Practical 特别指出：上周我们学过可以把二分类变量转成 0/1 当数值用（用于回归），但**今天我们就把它们当类别处理**。

**Step 1：读数据**

```r
spiders = read.csv("Meyer_and_Uetz_2019.csv", header = TRUE)
spiders                # 建议先看一眼数据长什么样
```
（务必命名为 `spiders`，否则 starter code 要大改。）

**Step 2：用 `table()` 造列联表**

手册教的是用 `aggregate()` + `matrix()` 手工造表（练手很好），但 R 有更省事的办法：

```r
court.mate.table = table( spiders$Courtship, spiders$MatingStatus )
court.mate.table
```

`table()` 的工作方式：接受**两个等长的类别向量**，把对应位置的类别**配成对**，数每一对出现了多少次，输出成表。

输出：
```
     m  v
  n 20  9
  y 54 70
```

**Step 3：改行列名（`table()` 按类别名的字母序排行和列）**

```r
rownames( court.mate.table ) = c( "male did not court", "male courted" )
colnames( court.mate.table ) = c( "mated female", "virgin female" )
```

⚠ **必须把对的名字配给对的行列**。`table()` 按**原始类别名的字母序**排：行是 n 然后 y，列是 m 然后 v。Practical 的建议很务实：**与其推理，不如先打印原始表看一眼行列顺序**。

改名后：
```
                   mated female virgin female
male did not court           20             9
male courted                 54            70
```

**Q1.1**：雄蛛向处女雌蛛求偶的试验数？遇到但未求偶的？
→ **70 和 9**。

**Step 4：卡方检验**

```r
chisq.test( court.mate.table )
```

**Q1.2**：有证据表明雌蛛的交配状态影响雄蛛是否求偶吗？怎么知道的？
→ **有，因为 p 值小于 0.05**（p = 0.0239）。

**Step 5：规范报告（本周最重要的技能之一）**

读者不仅需要知道"有没有显著关系"，还需要知道"**这个关系是什么样的**"。Practical 给的范文：

> *"Male* S. ocreata *were more likely to court virgin females (89% females courted) than females that had previously mated (73% females courted, p = 0.0239)."*

百分比直接从列联表算：$70/(70+9)=88.6\%\approx89\%$；$54/(54+20)=72.97\%\approx73\%$。

**→ 报告范式记忆点：方向 + 具体数值（百分比）+ 检验统计量/p 值。光写 "p < 0.05, significant" 是不合格的。**

**Step 6：作图（Q1.3）**

两种选择：
1. **直接呈现列联表本身**——列联表是一种合成，可以直接当作 display item，但**必须有清晰的行列标签和图注**；
2. **条形图**——用 starter code 提供的自定义函数：

```r
ct.to.barplot( court.mate.table )   # 把两行的列联表转成条形图；需先运行 starter code 里的函数定义
```

图注示例（自己写时可参考）：*"Figure 1. Proportion of male* S. ocreata *that courted previously-mated (n = 74) and virgin (n = 79) females. Males were significantly more likely to court virgin females (χ² test, p = 0.0239)."*

**Step 7：不建表也能直接检验**

```r
chisq.test( spiders$Courtship, spiders$MatingStatus )
```
把两个**向量**直接喂给 `chisq.test()`，结果与 `chisq.test(court.mate.table)` **完全相同**。但建表仍值得做，因为**列联表本身帮我们"看见"数据**。

### 5.4 Question 2：雄蛛的求偶决定是否取决于雌蛛是否刚进食

**解法**：完全照搬 Q1 的逻辑，把 `MatingStatus` 换成 `HungerStatus`。

```r
court.hunger.table = table( spiders$Courtship, spiders$HungerStatus )
court.hunger.table
rownames( court.hunger.table ) = c( "male did not court", "male courted" )
colnames( court.hunger.table ) = c( "fed female", "starved female" )
chisq.test( court.hunger.table )
ct.to.barplot( court.hunger.table )
```
（`HungerStatus` 的字母序：f 在 s 之前 → 第一列是 fed。）

**Q2.1 答案（answer key 原文）**：
> *"We found no evidence that female hunger status affected the probability that males would court them (p = 0.3072)."*

**报告范式记忆点**：**结果不显著时，要写 "we found no evidence that…"，而不是 "there is no effect" 或 "we proved there is no difference"。** 不显著只是"没找到证据"，不是"证明了不存在"。

### 5.5 Question 3（Challenge）：子集分析

**科学逻辑链**：Q1 发现雄蛛更少向已交配雌蛛求偶。为什么？假说是"**已交配的雌蛛本来就不太愿意再交配**"，所以雄蛛不值得冒生命危险去求偶。要检验这个假说，就得**只在"被求偶了的雌蛛"里**看交配状态与是否成功交配的关系。

**解法（用前几周学的 subset 技巧）**：

```r
# 只保留雄蛛确实求偶了的试验（Courtship == "y"）
courted = spiders[ spiders$Courtship == "y", ]     # 方括号里逗号前是行条件、逗号后留空表示保留所有列
# 也可以写成 courted = subset(spiders, Courtship == "y")

mate.table = table( courted$Mating, courted$MatingStatus )   # 行 = 是否成功交配，列 = 雌蛛先前的交配状态
mate.table                                                   # 先看一眼行列顺序再改名
rownames( mate.table ) = c( "did not mate", "mated" )
colnames( mate.table ) = c( "previously mated female", "virgin female" )
chisq.test( mate.table )
ct.to.barplot( mate.table )
```
> 注：记录"是否成功交配"的列名在 practical 正文里未逐字给出（正文只说明了 `Female`/`Male`/`MatingStatus`/`HungerStatus`/`Courtship`）。实际操作时先 `names(spiders)` 或 `head(spiders)` 看一眼列名，把上面代码里的 `Mating` 换成真实列名即可。

**Q3.1 答案（answer key 原文）**：
> *"Among females that were courted, virgin females were more likely to mate than were females that had mated previously (p < 0.0001)."*

**报告范式记忆点**：p 值非常小时，写 **`p < 0.0001`** 而不是写一长串科学计数法。

### 5.6 Question 4：多于两类的情形（5×2 列联表）

**背景**：Tysall et al. (2020) 研究**标记方法**是否影响果蝇 *Drosophila melanogaster* 雄蝇的交配成功率。标记的目的是让研究者能在实验里辨认个体；如果不同标记法本身就影响行为，就会**混杂 (confound)** 后续实验的结果。

五种标记法：
- **Wing clipping (C)** —— 在一侧翅上剪一个小缺口
- **Food dye (D)** —— 在食物里加有色染料，活体腹部可见颜色
- **Fluorescent paint (Pa)** —— 胸部点一小点荧光漆
- **Marker pen (Pe)** —— 翅上画一个小点
- **Fluorescent powder (Po)** —— 全身撒荧光粉

实验：每种方法标记 400 只雄蝇，每次试验把**1 只雌蝇 + 1 只标记雄蝇 + 1 只未标记雄蝇**放进一个塞棉花的小试管 arena，记录哪只雄蝇成功交配；一次交配后即结束试验（所以不存在两只都交配的情况）。部分标记雄蝇逃逸或死亡，故实际每组少于 400 次试验。

数据 `Tysall_et_al_2019b.csv`：`mark_type`（C / D / Pa / Pe / Po），`chosen`（M = 标记雄蝇被选中，UM = 未标记雄蝇被选中）。

**解法**：

```r
flies = read.csv("Tysall_et_al_2019b.csv", header = TRUE)
mark.table = table( flies$chosen, flies$mark_type )   # 2 行 × 5 列的列联表
mark.table
rownames( mark.table ) = c( "marked male chosen", "unmarked male chosen" )
colnames( mark.table ) = c( "clip", "dye", "paint", "pen", "powder" )
chisq.test( mark.table )
ct.to.barplot( mark.table )
```
（`chosen` 的字母序 M 在 UM 之前 → 第一行是 M；`mark_type` 的字母序 C, D, Pa, Pe, Po。）

自由度 $df=(2-1)(5-1)=4$。

**Q4.1 答案（answer key 原文）**：
> *"Marking method affected the probability that males were chosen as mates (p = 0.0311)."*

**Practical 的收尾提醒（重要）**：卡方检验和 ANOVA 一样是 **omnibus 检验**——它告诉我们"整张表里的关联组合，离零假设下的期望远到不太可能是偶然"，因此可以推断存在真实关系；**但它不告诉我们哪一组与哪一组显著不同**。要知道那个，就得做额外的 post hoc 检验（见手册，即 §2.8 的 Bonferroni 校正两两比较）。

### 5.7 Question 5–6：回归复习（对应现场课内容）

**Q5 背景**：斗牛士蝽 *Anisoscelis alipes*（"flag-footed bug" 之一）后腿上有巨大的**胫节板 (tibial plate)**。功能未知，普遍认为是雄性求偶时的**配偶质量广告**，这符合 Zahavi (1975) 的 **handicap principle（不利条件原理）**：这类显眼特征代价高昂（降低敏捷性、更易被捕食者发现），一个雄性若能攒够能量长出它、还能带着它活下来，说明它其他方面一定非常优秀——于是这个特征就成了"好基因"的可信广告。

由此推出两个可检验的假说：
1. 控制体型后，**雄性的胫节板比雌性大**；
2. **胫节板大小随体型增大而增大，且雄性增长得更快**（能攒到资源长大的雄性，会把相对更多能量投入昂贵的性信号）。

数据 `data from Longbottom et al 2022.csv`：`ID`、`sex`、`pw`（pronotum width，前胸背板宽度，作为**体型的替代指标**）、`flag.area`（两侧胫节板的平均面积）、以及 tibia / forewing / hindwing 的长度。长度单位 cm，面积 cm²。

**分析前务必取对数**：

```r
matador.data$log.pw = log( matador.data$pw )          # 对体型度量取自然对数
matador.data$log.flag = log( matador.data$flag.area )
```

**为什么要取对数**（practical 明确解释）：
1. **同质化变异 (homogenises variability)** —— 满足回归的等方差假设；
2. **线性化长度与面积的关系** —— 面积 ∝ 长度²，取对数后 $\log(\text{area}) = 2\log(\text{length}) + c$ 变成直线，斜率还有异速生长 (allometry) 的直接解释。

**关于 `NAs introduced by coercion` 警告**：数据里有缺失值，R 对缺失值取对数返回 `NA`（not a number）。这**没问题**——缺失数据本来就不是数。R 会在分析中自动忽略含缺失值的个体，这正是我们想要的。**这个警告值得注意，但不是错误。**

**Q5.1 解法与答案**：

```r
flag.lm = lm( log.flag ~ log.pw + sex + log.pw * sex, data = matador.data )
summary( flag.lm )
```
- `log.pw` 主效应 → 胫节板面积随体型的变化；
- `sex` 主效应 → 控制体型后的两性差异；
- `log.pw:sex` 交互 → 两性的增长速率是否不同（即假说 ii）。

Answer key 原文：
> *"Area of the tibial plate increased with pronotum width (1.99 log(cm²)/log(cm); p < 0.0001). We found weak evidence that males had **smaller** tibial plates than females (−0.052 log(cm²); p = 0.0848). We found no significant evidence that the size of the tibial plate changes differently in male and female matador bugs (p = 0.2068). This does not support the hypothesis that tibial plates are signals of male mate quality in this species."*

**要点**：
- 斜率 **1.99 ≈ 2** —— 正是"面积随长度平方增长"的等距生长 (isometry) 预期，说明胫节板并没有随体型**不成比例地**变大；
- 方向**与假说相反**（雄性反而略小），且只是 weak evidence（p = 0.0848，在 0.05–0.10 之间）；
- **结论：数据不支持"胫节板是雄性质量信号"这一假说。** 这是一个很好的"假说被否定"的报告范例。
- **报告用语分级**：p < 0.05 = "evidence"/"significant"；0.05 < p < 0.10 = "**weak evidence**"/"marginally significant"；p > 0.10 = "no evidence"。

**Q6.1 / Q6.2 / Q6.3：共线性 (collinearity) 的经典演示**

```r
lm1 = lm( log.tibia ~ log.forewing, data = matador.data )              # Q6.1
lm2 = lm( log.tibia ~ log.hindwing, data = matador.data )              # Q6.2
lm3 = lm( log.tibia ~ log.forewing + log.hindwing, data = matador.data ) # Q6.3
```

Answer key：
- **Q6.1**：*"Logged tibia length increased with logged forewing length (0.5085; p < 0.0001)."*
- **Q6.2**：*"Logged tibia length increased with logged hindwing length (0.4584; p < 0.0001)."*
- **Q6.3**：*"We found no evidence that tibia length increased with hindwing length when forewing length was in the model (p = 0.8632). This is because forewing length and hindwing length are **strongly correlated** – they contain much of the same information. So, we cannot learn anything about tibia length from hindwing length that we have not already learned from forewing length."*

**这是全 practical 最重要的概念收获之一**：单独看，前翅长和后翅长各自都极显著地预测胫节长；**但把两者一起放进模型，后翅长就完全不显著了**——因为两个预测变量高度相关、携带几乎相同的信息，前翅长已经把该解释的都解释完了，后翅长没有**额外**信息可贡献。这就是**共线性 (collinearity / multicollinearity)**。

**推论**：多元回归里某个预测变量"不显著"，**不等于**它与响应无关，可能只是它的信息已被别的预测变量涵盖。

---

## 六、易错点 / 重点难点

1. **期望频数 < 5 的处理**
   - 判据是**期望频数**（$E_{ij}=R_iC_j/N$）而不是观测频数；手册的标准是**每个格子的期望都 > 5**。
   - R 会给 `Warning message: In chisq.test(choice) : Chi-squared approximation may be incorrect`。
   - **这是警告不是报错**，R 照样输出 p 值，但那个 p 值不可信 → **必须改用 `fisher.test()`**。
   - 反过来，若总观测数极大，`fisher.test()` 可能算不出来，这时只能用卡方近似。

2. **自由度算错**
   - 拟合优度：$df = C - 1$（**类别数减 1**），不是 $N-1$；
   - 列联表：$df = (r-1)(c-1)$，**不是** $rc-1$，也不是 $r+c-2$。
   - 2×2 表的 df 永远是 1；3×3 表是 4；2×5 表是 4。

3. **忘记 R 对 2×2 表默认做 Yates 连续性校正**
   - 手算得 χ² = 6.08 (p = 0.0137)，R 输出 5.10 (p = 0.0239)——不是你算错了。
   - 关闭：`chisq.test(x, correct = FALSE)`。
   - 拟合优度调用 `chisq.test(c(...), p=c(...))` 不做该校正。

4. **把关联当因果 (correlation ≠ causation)**
   - 卡方检验是 **test for association**，只说明"响应频率与预测变量不独立"，**不能推出因果**。
   - 手册狼蛛例子里，"来自不同基质的雌蛛择偶不同"可能是遗传型差异、可能是环境差异，也可能有共同的第三因素。
   - 现场课的加拿大工资数据同理：观察到关联，能提出问题，但因果解释需要额外证据（比如"高薪者提前退休"只是一个**假说**，本数据无法判定）。

5. **omnibus 检验的过度解读**
   - 卡方检验显著 ≠ 知道哪一对不同。想知道就必须做 post hoc 两两比较 + Bonferroni 校正。
   - 忘记这一步是最常见的错误之一（与 ANOVA 完全同型）。

6. **HARKing —— 看了数据再决定做哪些比较**
   - 老师在 slides 里用最强烈的措辞警告过。**必须在收集数据之前**确定要做哪些 post hoc 比较，否则 p 值失效、结果有偏。
   - 想省 Bonferroni 的代价，正当办法是**事先**缩小比较集合，而不是**事后**挑显著的。

7. **零期望不一定是"均等"**
   - 野外花色丰度不同、每次试验里两种表型雄蛛数目不同，零期望都要相应调整（`p = c(0.4, 0.2, 0.4)` 或 `binom.test(..., p = 2/3, ...)`）。
   - 用错零期望会得到完全错误的 p 值。

8. **`table()` 的行列顺序陷阱**
   - `table()` **按原始类别名的字母序**排行和列（n 在 y 前、m 在 v 前、f 在 s 前、M 在 UM 前）。
   - 改名时张冠李戴会让整个结论方向反过来。**永远先打印原表看一眼再改名。**

9. **`matrix()` 填数是按列的**
   - `matrix(c(41,17,18,4), nrow = 2)` 从**左上角开始往下填满第一列，再填第二列**。
   - 顺手按行填会造出一张转置错乱的表。

10. **Fisher 检验单尾方向的含义**
    - `alternative = "greater"` 问的是"**第一行**的响应在**第一列**条件下是否**更**频繁"；`"less"` 反之。
    - 行列摆放顺序改变，`greater`/`less` 的含义就变了。**没有明确的 a priori 方向时就用默认的双尾。**

11. **不显著 ≠ 不存在**
    - 规范写法是 "**we found no evidence that…**"，不是 "there is no effect"。
    - 0.05 < p < 0.10 应写 "weak evidence" / "marginally significant"，并在图里用 `°` 而不是 `*` 标注。

12. **报告只写 p 值是不够的**
    - 必须同时给出**方向和效应大小**（百分比、比例、χ²、df）。
    - 手册的完整范式还要求：第一次用 $\alpha_B$ 时**必须定义它**，因为 Bonferroni 校正阈值没有标准缩写，读者看不懂。

13. **不要同时用饼图和条形图报告同一结果**（手册明确禁止）。

14. **多元回归里"不显著"可能是共线性造成的**（Q6.3）——不能因此断言该变量与响应无关。

15. **有交互项时不要直接解读主效应**——主效应是"另一个预测变量取 0 时"的值，若 0 落在数据范围之外（如 age = 0），这个值可能荒谬甚至符号相反。**均值中心化能救回它的解释力。**

16. **不显著的交互项应该删掉**，因为它会让其他主效应难以解释；但**参与显著交互的主效应不能删**（层级原则）。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| categorical response | 分类响应变量 | 响应本身是一个类别（红/黄/白、求偶/不求偶），不是一个数。 |
| count data | 计数数据 | 落进每个类别的观测次数，是分类响应分析的基本材料。 |
| binomial test | 二项检验 | 只有两种结果的独立试验中，检验成功概率是否等于某个给定值；精确检验，小样本可用。 |
| exact test | 精确检验 | p 值是精确算出来的而非从近似分布估计的，因此准确性不依赖样本量。 |
| binomial coefficient / "n choose k" | 二项系数 | $\binom{n}{k}=n!/[k!(n-k)!]$，n 次试验中有 k 次某结果的排列方式数。 |
| factorial | 阶乘 | $n!$ = 1 到 n 所有整数的乘积。 |
| a priori expectation | 先验期望 | 在看数据之前、由理论或实验设计给出的零假设比例。 |
| chi-squared goodness of fit test | 卡方拟合优度检验 | 把各类的观测计数与理论期望计数比较，$df=C-1$；可处理多于两类。 |
| chi-squared statistic | 卡方统计量 | $\chi^2=\sum(O-E)^2/E$，衡量观测整体偏离期望的程度。 |
| chi-squared distribution | 卡方分布 | 零假设下卡方统计量服从的右偏分布，均值等于自由度，实际使用只看右尾。 |
| observed frequency (O) | 观测频数 | 实际数到的、落在某格里的次数。 |
| expected frequency (E) | 期望频数 | 零假设为真时该格"应该"有的次数；列联表中 $E_{ij}=R_iC_j/N$。 |
| degrees of freedom (df) | 自由度 | 在行列合计固定的约束下，表中可自由取值的格子数；列联表为 $(r-1)(c-1)$。 |
| contingency table | 列联表 | 行为一个分类变量、列为另一个分类变量、格中放计数的表；既是分析对象也是合格的展示图表。 |
| marginal total (row/column total) | 边际合计（行/列合计） | 某一行或某一列的计数之和，是计算期望频数的原料。 |
| test for association | 关联性检验 | 检验列联表的行变量与列变量是否独立；卡方检验与 Fisher 检验都是。 |
| independence | 独立性 | 若两变量独立，则某格的概率等于行边际概率 × 列边际概率。 |
| empirical expectation | 经验期望 | 没有理论期望时，从数据自身的行列边际比例推出的期望值。 |
| Fisher's exact test | Fisher 精确检验 | 固定行列合计、枚举所有可能表格算出精确 p 值；期望频数 < 5 时的首选。 |
| Yates' continuity correction | Yates 连续性校正 | R 对 2×2 表默认施加的 $(|O-E|-0.5)^2/E$ 修正，使 p 值更保守。 |
| omnibus test | 综合/总体检验 | 只回答"整体上存在差异吗"，不回答"是哪一对"；ANOVA 与卡方检验都是。 |
| post hoc test | 事后检验 | omnibus 检验显著后，逐对比较以定位差异所在。 |
| multiple testing issue | 多重检验问题 | 做多次比较时，"至少一次假阳性"的总概率会超过名义 α。 |
| Bonferroni correction (Dunn–Bonferroni) | Bonferroni 校正 | 把显著性阈值除以比较次数：$\alpha_B=\alpha/m$；代价是统计功效下降。 |
| statistical power | 统计功效 | 当效应真实存在时能检测出它的概率；Bonferroni 校正会降低它。 |
| HARKing | 事后编造假说 | Hypothesising After the Results are Known——看了数据再决定检验什么，会使 p 值失效。 |
| pie chart | 饼图 | 展示比例数据，各扇区之和为 1，能体现"此消彼长"。 |
| bar chart | 条形图 | 便于精确比较各类高低；组间比较时应画频率而非原始计数。 |
| stacked bar chart | 堆叠条形图 | 响应多于两类时按组展示各类频率构成的图。 |
| frequency | 频率 | 某类计数除以该组总数，即比例；展示组间差异时优于原始计数。 |
| marginally significant / weak evidence | 边缘显著 / 弱证据 | 0.05 < p < 0.10 的情形，图中常用 `°` 标注。 |
| surrogate (proxy) | 替代指标 | 拿不到真正想要的变量时使用的近似变量（如用 pronotum width 代表体型）。 |
| mean centering | 均值中心化 | 把预测变量减去其均值，使截距变成"平均个体的预期响应"，从而有解释意义。 |
| multiple regression | 多元回归 | 同时纳入多个预测变量，每个效应都是"控制其他变量后"的效应。 |
| interaction | 交互作用 | 一个预测变量的效应取决于另一个预测变量的取值；R 中写作 `a * b` 或 `a:b`。 |
| main effect | 主效应 | 单个预测变量的效应；模型含交互项时，它是"另一变量取 0 时"的效应。 |
| baseline (reference) level | 基线水平 | R 按字母序自动选定的分类变量参照组（如 F 在 M 前，故女性为基线）。 |
| additive model | 可加模型 | 无交互项的模型，各预测变量的效应简单相加，图上表现为平行线。 |
| quadratic term | 二次项 | 加入 $x^2$ 让"线性模型"能拟合弯曲的关系（线性指对参数线性）。 |
| collinearity | 共线性 | 两个预测变量高度相关、携带重复信息，同时入模型时其中之一会变得不显著。 |
| R-squared | 决定系数 | 预测变量解释的变异比例；自然科学中 8% 已算不错，物理学则会嫌太低。 |
| extrapolation | 外推 | 推断到观测数据范围之外，一般是坏做法（如把年龄外推到 0）。 |
| selection / attrition bias | 留存偏倚 | 因谁留在样本中并非随机而产生的偏差（如高薪者提前退休导致老年段工资看似下降）。 |
| handicap principle | 不利条件原理 | Zahavi (1975)：代价高昂的显眼特征之所以是可信信号，正因为只有优质个体承担得起。 |
| function (in R) | 函数 | 打包成一个名字的一组命令，调用名字即执行整套命令（如 `ct.to.barplot()`）。 |

---

## 附：本周 R 命令速查

```r
# ---------- 与理论期望比较 ----------
binom.test(59, 80, 0.5, alternative = "greater")
#   59 = 观测到的"成功"次数；80 = 总试验数；0.5 = 零假设下的成功概率
#   alternative: "greater"/"less" 单尾，"two.sided" 双尾（有 a priori 方向才用单尾）
#   输出：p-value（假设检验的 p 值）
#         95 percent confidence interval（成功概率的置信区间）
#         probability of success（成功概率的最佳估计 = 59/80 = 0.7375）

chisq.test(c(59, 21), p = c(0.5, 0.5))
#   第一个参数 = 各类的观测计数向量；p = 零假设下各类的概率（必须和为 1）
#   输出：X-squared（卡方统计量）、df（= 类别数 − 1）、p-value（永远双尾）
#   注意：这种拟合优度调用不做 Yates 校正

chisq.test(c(13, 28, 39), p = c(1/3, 1/3, 1/3))   # 多于两类的拟合优度
chisq.test(c(4, 15, 8),  p = c(0.4, 0.2, 0.4))    # 自定义（非均等）零期望

# ---------- 造列联表 ----------
choice = matrix(c(41, 17, 18, 4), nrow = 2,
                dimnames = list(c("dark-legged", "light-legged"),
                                c("light trials", "dark trials")))
#   c(...) 里的数字按列填入：先填满第 1 列（41, 17），再填第 2 列（18, 4）
#   nrow = 2 告诉 R 表有 2 行，列数由此自动推出
#   dimnames = list(行名向量, 列名向量)，可省略但强烈建议写上便于核对

court.mate.table = table(spiders$Courtship, spiders$MatingStatus)
#   更省事的做法：两个等长类别向量 → 自动配对计数成表
#   行列均按原始类别名的字母序排列
rownames(court.mate.table) = c("male did not court", "male courted")
colnames(court.mate.table) = c("mated female", "virgin female")

# ---------- 列联表的检验 ----------
chisq.test(court.mate.table)            # 2×2 表默认做 Yates 校正
chisq.test(court.mate.table, correct = FALSE)   # 关闭 Yates 校正
chisq.test(spiders$Courtship, spiders$MatingStatus)   # 不建表直接检验，结果相同

fisher.test(choice)                     # 双尾 Fisher 精确检验；期望频数 < 5 时首选
fisher.test(choice, alternative = "greater")
#   输出：p-value、odds ratio（优势比，行1响应在列1条件下相对更/更不常见的程度）
#         及其置信区间

# ---------- 作图 ----------
slices = c(39, 28, 13)
lbls = c("tufted (39)", "dark (28)", "light (13)")
pie(slices, lbls)                       # 饼图；标签里带上计数便于比较

lbls = c("tufted", "dark", "light")
barplot(slices, names = lbls, ylim = c(0, 40), ylab = "frequency")
#   ylim 手动指定 y 轴范围，否则 R 可能把轴截断在 30

choice = matrix(c(30/45, 4/25, 5/10), nrow = 1,
                dimnames = list(c("tufted"),
                                c("rocks\n(n = 45)", "litter\n(n = 25)", "grass\n(n = 10)")))
barplot(choice, ylab = "frequency of tufted males chosen",
        xlab = "female origin", ylim = c(0, .8))
#   只有两类响应时，每组一根柱子即可；\n 在标签里插入换行

choice = matrix(c(30/45,9/45,6/45, 4/25,18/25,3/25, 5/10,1/10,4/10), nrow = 3,
                dimnames = list(c("tufted","dark","light"),
                                c("rocks\n(n = 45)","litter\n(n = 25)","grass\n(n = 10)")))
barplot(choice, legend = c(rownames(choice)), ylab = "frequency",
        xlab = "female origin", xlim = c(0, 4.5))
#   多于两类 → 堆叠条形图；legend 加图例；xlim 拉长 x 轴防止图例压住柱子

ct.to.barplot(court.mate.table)         # practical starter code 里的自定义函数
#   把两行的列联表直接转成条形图；使用前需先运行 starter code 中的函数定义行

# ---------- 子集与回归（Q3、Q5、Q6）----------
courted = spiders[spiders$Courtship == "y", ]        # 取子集：逗号前是行条件
matador.data$log.pw = log(matador.data$pw)           # 取自然对数（会对缺失值产生 NA 警告，正常）
lm(log.flag ~ log.pw + sex + log.pw * sex, data = matador.data)   # 含交互的多元回归
lm(log.tibia ~ log.forewing + log.hindwing, data = matador.data)  # 演示共线性
CI$MC_age = CI$age - mean(CI$age)                    # 均值中心化
```
