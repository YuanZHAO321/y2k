# Week 10 — 阳生/阴生植物的驯化 (Acclimation)：大麦叶片形态测量与叶绿素分光光度定量

> 本周材料清单（全部已通读）
> - `Week 10/Morning/Chlorophyll practical_barley(1).md` — 大麦 (barley) 叶绿素测定实践讲义
>
> ⚠️ **本周只有 Morning 场，没有 Afternoon 场**。本周是全课（Hilary Term 共 10 周）的**最后一周**，也是全课材料量最小的一周（约 1,600 词），下文内容严格按讲义原文撰写，凡讲义未写而由笔记补充的方法学解释均标注「📎 背景补充」。
>
> 📌 **文档转换缺失说明**：原 `.docx` 中有 3 幅图（Figure 1 毛地黄叶片、Figure 2 实验器材、Figure 3 比色皿光路图）和 2 条**公式图片**（吸光度定义式、Beer-Lambert 定律式）在转成 md 时丢失——原文出现「Absorbance (A) is defined as:」后紧接空白、「according to the equation:」后紧接空白的情况。这两条公式的标准形式已在「三、公式与图表」中按讲义随后给出的符号说明（I₀、Iₜ、A、ε、d）补回并标注 📎。

---

## 一、本周主题

**主题**：以「阳生 (sun) vs 阴生 (shade) 条件下生长的同一物种」为对象，同时测量**叶片形态参数**与**叶绿素含量**，检验植物对光环境的**驯化 (acclimation)** 响应。

**本周只有上午场（Morning）**，是一个完整的、贯穿「采样—形态测量—化学提取—仪器测定—数据换算—统计分析—结果解读」全链条的综合实践，兼具**定量化学分析**（分光光度法）与**生物学实验设计/统计**两条主线。作为全课收官周，它把此前分散练过的技能（称量、体积操作、仪器读数、单位换算、误差与重复、作图与统计检验）集中到同一个实验里。

**⚠️ 物种替换（讲义开头第一句，重要）**：
> "Please note the plant *Digitalis purpurea* (the foxglove) has had to be replaced by the plant *Hordeum vulgare* (barley) for this practical in Semester 2 2025."

即：**2025 年第二学期实际使用大麦 (Hordeum vulgare, barley)，替代原定的毛地黄 (Digitalis purpurea, foxglove)**。但讲义正文（标题、Study species 段、Figure 1）**未同步修改，仍通篇写 *D. purpurea***。复习时须留意：**方法与公式完全通用**，只是材料换成了大麦。

📎 **背景补充（关于「为何用大麦」）**：讲义本身**没有**解释替换原因，也没有为大麦另写生物学背景。可确定的只有：讲义为 *D. purpurea* 给出的生态学理由是「原生于林缘、林窗与树篱 (woodland margins and clearings and hedgerows)，因而适应多种光照条件」（Johnson et al. 1993），这一理由**不能直接照搬到大麦**上——大麦是栽培禾本科作物。不过大麦作为实验材料的普适优点是：生长快、播种到取样周期短、叶片扁平薄且无明显叶柄、便于批量在不同光照下培养，适合教学实验。**此点为补充推断，讲义未述，答题时不宜当作讲义内容引用。**

⚠️ 若使用大麦，讲义中「Remove the largest leaf… Measure the length of the **petiole** (the leaf stalk)」这一步在形态上是有问题的：禾本科叶片为**叶鞘 + 叶片**结构，没有毛地黄那样的叶柄。实际操作时按带教老师指示替换为等价的形态指标（如叶长/叶鞘长）。

---

## 二、核心概念

### 2.1 光、叶绿素与光合作用（讲义 Background 段）

- 植物生长需要光。**光能被叶绿素 (chlorophyll) 吸收**。
- 叶绿素吸收**蓝光 (blue)** 与**红光 (red)** 波长 —— 正因为它**不吸收（而反射/透射）绿光**，叶片才呈**绿色**。
- 被吸收的光能用于驱动**电子传递链 (electron transport chain)**（讲义交叉引用了纪录片 *How to Grow a Planet*, Week 1）。
- 该能量最终驱动**糖 (sugars) 的合成**，支持植物生长。
- 植物含**两种形式的叶绿素**：**chlorophyll a** 与 **chlorophyll b**，二者吸收的波长**略有不同**（这是后面能用双波长联立方程分别定量的物理基础）。

### 2.2 竞争与两类响应（形态 + 生化）

自然界中植物为光及其他资源**竞争**。为优化捕光，植物会同时改变两个层面：

| 层面 | 讲义列举的具体内容 |
|---|---|
| **形态 (morphology)** | 叶片排列方式、株高、叶片厚度等 |
| **生化 (biochemistry)** | 包括改变**叶绿素含量 (chlorophyll content)** |

本实验正好一次性覆盖这两个层面：形态端量**叶柄长度**与**叶重比**，生化端量**叶绿素 a/b 含量与比值**。

### 2.3 ⭐ 两个必须分清的定义（讲义给出精确定义，考点）

> **Adaptation（适应）** — a **genetic** difference between individuals or species that makes them better able to survive in particular conditions.
> 「个体或物种之间的**遗传性**差异，使其更能在特定条件下生存。」

> **Acclimation（驯化 / 驯化适应）** — a change in the **phenotype** of an organism in response to the environment **in which it develops**.
> 「生物体**表型**上的改变，是对其**发育所处环境**的响应。」

**关键区别**：
- Adaptation = **遗传层面**、跨世代、由自然选择塑造、不同基因型之间的差异。
- Acclimation = **表型层面**、个体在自己一生（发育过程）中发生、**基因型相同**也可发生、可逆或至少是环境诱导的。

**本实验测的是 acclimation**：因为阳生与阴生植株是**同一物种（且教学上是同一批种子/同一基因来源）**，只是被放在不同光照下发育，观察到的差异只能归于表型可塑性，而非遗传差异。讲义原话：「When it grows in different conditions, it will **acclimate** to those conditions (Gjindali and Johnson 2023).」

### 2.4 实验目的（Aims）

> "In this experiment, you will examine the **morphology** and the **chlorophyll content** of *D. purpurea*（实为大麦）grown in either **sun** or **shade**."

**每两名学生一组（each pair of students），发 2 株植物：一株来自 sun，一株来自 shade。**

### 2.5 分光光度法的原理

- **吸光度 (absorbance, A)** 讲义定义：「a measure of how much light at a particular wavelength passes through a solution」（衡量特定波长的光有多少透过溶液）。
- 讲义明确指出：在分光光度计 (spectrophotometer) 中测量时，**I₀ 是透过参比样品 (reference sample) 的光**，本实验的参比就是**纯净乙醇 (clean ethanol)**。这就是「调零 (zero)」这一步的物理含义。
- **核心定量前提**：「The amount of light absorbed by a solution is **proportional to the concentration** of the absorbing molecule.」——吸光量与吸光分子浓度成正比，比例关系由**消光系数 (extinction coefficient, ε)** 决定，即 **Beer-Lambert Law**（Rodger 2013）。
- **同一分子在同一溶剂中、每一个波长都有各自的 ε**（讲义原话：「For any light-absorbing molecule, **in a given solvent**, we can measure the extinction coefficient for each wavelength」）。⚠️ **ε 依赖溶剂**——这就是为什么本实验必须用 96% 乙醇提取、且必须使用**乙醇体系对应的**换算系数。

### 2.6 ⭐ 为什么能在混合液中分别算出 a 和 b（联立方程思想）

讲义原话（含一处明显笔误，原文写作 "we can therefore use **simultaneous** to calculate"，应为 **simultaneous equations**）：

> 我们测的是**两种叶绿素**，它们的吸收光谱**互相重叠 (overlapping spectra)**。**两者在 665 nm 和 649 nm 都有吸收**，但在**每个波长上的 ε 不同**。因此可以用**联立方程 (simultaneous equations)** 求出混合液中各自的浓度。

即：两个未知数（[Chl a]、[Chl b]）→ 需要两个独立方程 → 因此需要**两个波长**（665 与 649）的吸光度。这就是波长选择的第一层依据。

---

## 三、公式与图表

### 3.1 吸光度的定义式

讲义写「Absorbance (A) is defined as:」后为公式图片（转换丢失），随后说明「Where I₀ is the light incident on the solution and Iₜ is the light passing through the solution」。

📎 **背景补充（按讲义符号补回标准形式）**：

$$A = \log_{10}\!\left(\frac{I_0}{I_t}\right)$$

| 符号 | 含义 | 讲义原文 |
|---|---|---|
| $A$ | 吸光度 (absorbance)，**无量纲** | — |
| $I_0$ | 入射到溶液上的光强 | "the light **incident on** the solution"；实测时为**透过参比样（纯乙醇）**的光强 |
| $I_t$ | 透过溶液后的光强 | "the light **passing through** the solution" |

含义：A = 1 表示透过率 10%（吸收掉 90%）；A = 2 表示透过率 1%。**A 是对数量**，所以不能直接相加减地理解为「吸收比例」。

### 3.2 Beer-Lambert 定律

讲义写「according to the equation:」后为公式图片（转换丢失），随后说明「Where A is absorbance, ε is the extinction coefficient and d is the distance through which the light passes (the length of the cuvette)」。

📎 **背景补充（按讲义符号补回标准形式）**：

$$A = \varepsilon \, c \, d$$

| 符号 | 含义 | 说明 |
|---|---|---|
| $A$ | 吸光度 | 无量纲 |
| $\varepsilon$ | **消光系数 (extinction coefficient)** | 讲义强调：**对给定分子、给定溶剂、给定波长**各有一个值。单位与 c、d 的单位配套（如 $\mathrm{ml\,\mu g^{-1}\,cm^{-1}}$ 或 $\mathrm{L\,mol^{-1}\,cm^{-1}}$） |
| $c$ | 吸光分子的**浓度** | 本实验目标量 |
| $d$ | **光程 (path length)**，即光穿过溶液的距离 = **比色皿的长度** | 单位 cm |

⭐ **讲义特别指出**：「Usually we use a **1 cm cuvette**, meaning that the **length term can be ignored**.」
—— 使用 1 cm 比色皿时 $d = 1\ \mathrm{cm}$，故 $A = \varepsilon c$，光程项可略去。**这正是下面 Lichtenthaler & Wellburn 换算式中不出现 d 的原因**；若换用其他光程的比色皿，系数必须相应修正。

### 3.3 ⭐⭐ 叶绿素浓度换算公式（本周核心，Lichtenthaler and Wellburn 1983）

讲义要求「Calculate the concentrations of chlorophyll a and b in each of your extracts using the following equations」：

$$\text{Chlorophyll } a \;=\; 13.95\,(A_{665}-A_{750}) \;-\; 6.88\,(A_{649}-A_{750}) \quad \mathrm{\mu g\;ml^{-1}}$$

$$\text{Chlorophyll } b \;=\; 24.96\,(A_{649}-A_{750}) \;-\; 7.32\,(A_{665}-A_{750}) \quad \mathrm{\mu g\;ml^{-1}}$$

（原讲义写法：`Chlorophyll a = 13.95.(A665-A750) – 6.88.(A649-A750) μg.ml-1`，其中的「.」是乘号）

**逐项解释**：

| 项 | 含义 |
|---|---|
| $A_{665}$ | 665 nm 处测得的吸光度 —— 该波长以 **chlorophyll a** 的红区吸收峰为主 |
| $A_{649}$ | 649 nm 处测得的吸光度 —— 该波长上 **chlorophyll b** 的相对贡献更大 |
| $A_{750}$ | 750 nm 处测得的吸光度 —— **两种叶绿素在此均不吸收**（讲义原话：「Neither molecule absorbs at 750 nm」），因此它代表**非叶绿素来源的信号**（见 3.4） |
| $(A_{665}-A_{750})$、$(A_{649}-A_{750})$ | **经基线/浊度校正后的净吸光度** —— 每个测定波长都要减去 750 nm 的读数 |
| $13.95$、$24.96$ | **正系数**：分别把「本色素在其主波长上的净吸光度」换算为浓度 |
| $-6.88$、$-7.32$ | **负的交叉校正系数 (cross-correction)**：扣除**另一种叶绿素**在该波长上的重叠吸收贡献。这正是 2.6 节「联立方程」被解出后写成显式形式的结果 |
| 系数总体性质 | 它们是**由 ε 矩阵求逆得来的组合常数**，因此**绑定于三个条件**：① 溶剂为 **96% 乙醇**；② 光程 **1 cm**；③ 波长恰为 **665 / 649 / 750 nm** |

**单位与量纲**：
- 计算结果单位为 $\mathrm{\mu g\;ml^{-1}}$（微克每毫升），即**提取液中**的叶绿素质量浓度。
- $A$ 无量纲，故系数本身携带 $\mathrm{\mu g\;ml^{-1}}$ 的量纲（等价于 $1/\varepsilon$ 类量）。
- ⚠️ 这是**提取液浓度，不是叶片中的含量** —— 必须再按 3.5 节换算。

**衍生量**：
- 总叶绿素 $= \text{Chl }a + \text{Chl }b$
- **叶绿素 a/b 比值** $= \dfrac{\text{Chl }a}{\text{Chl }b}$（**无量纲**，是本实验重点解读的生化指标之一）

### 3.4 ⭐ 波长选择依据（三个波长各自的角色）

讲义在此处直接向学生**提问**：「Neither molecule absorbs at 750 nm, **so why do we measure at this wavelength?**」（讲义未给答案，是留给学生作答的开放题。）

| 波长 | 选择理由 |
|---|---|
| **665 nm** | 落在 **chlorophyll a** 红区吸收峰附近；提供联立方程的第一个方程 |
| **649 nm** | **chlorophyll b** 在此的相对吸收更强；提供第二个独立方程。两波长的 ε 组合不同，方程组才可解 |
| **750 nm** | **两种叶绿素在此都不吸收**，因此该读数不代表叶绿素 |

📎 **背景补充（对讲义那道提问的标准答案）**：在 750 nm 测到的任何非零读数，只可能来自**非吸收性的干扰**——主要是**未滤净的细微颗粒造成的散射/浊度 (turbidity/scattering)**，以及**基线漂移、比色皿表面污渍或指纹、气泡**等。因为这类干扰在整个可见—近红外区大致平缓地抬高全部读数，所以把 $A_{750}$ 作为**基线**从 $A_{665}$、$A_{649}$ 中减去，就能把它扣掉，得到只属于叶绿素的净吸光度。这就是公式里处处出现 $(A_\lambda - A_{750})$ 的原因。**实践判读**：如果 $A_{750}$ 明显偏大（不接近 0），说明**过滤不彻底或比色皿脏**，应重新过滤/擦净后重测，而不是靠减法硬扣。

### 3.5 由提取液浓度换算到叶片含量

讲义原文（第 7 步）：
> "Knowing the **concentration of chlorophyll a and b in your extracts**, the **volume of extract** you made and the **amount of leaf** you used, you can now calculate the concentration inside your leaf pieces. You can express this **per unit area** of leaf and **per unit weight** of leaf."

讲义**只给出思路，未给出显式公式**。

📎 **背景补充（按讲义给的三个已知量补出换算式）**：

先求提取液中叶绿素的**总质量**：

$$m_{\text{chl}} \;(\mathrm{\mu g}) \;=\; C \;(\mathrm{\mu g\;ml^{-1}}) \times V \;(\mathrm{ml})$$

其中 $V = 10\ \mathrm{ml}$（讲义规定用乙醇定容到 10 ml）。

再分别除以叶片面积与叶片重量：

$$\text{单位面积叶绿素} = \frac{C \times V}{A_{\text{leaf}}} \quad \mathrm{\mu g\;cm^{-2}}$$

$$\text{单位重量叶绿素} = \frac{C \times V}{W_{\text{leaf}}} \quad \mathrm{\mu g\;g^{-1}}\ (\text{或 } \mathrm{mg\;g^{-1}},\ \div 1000)$$

其中 $A_{\text{leaf}}$ 为该叶片小方块的实测面积（讲义用方格纸数 mm² 的方法测得，注意 **1 cm² = 100 mm²** 的换算），$W_{\text{leaf}}$ 为该叶片小方块的实测重量。

### 3.6 叶重比 (Leaf Weight Ratio) 公式

讲义定义：

$$\text{Leaf weight ratio} = \frac{\text{weight}}{\text{area}}$$

即单位面积叶片的重量，常用单位 $\mathrm{g\;cm^{-2}}$（或换算为 $\mathrm{mg\;cm^{-2}}$）。它反映**叶片的厚度/致密程度**（越大表示叶片越厚实）。

### 3.7 需要作的图（讲义明确列出 5 张）

讲义要求「Plot graphs to show the values of」：

1. **Petiole length**（叶柄长度）
2. **Leaf weight ratio**（叶重比）
3. **Total chlorophyll (a+b) per unit area**（单位面积总叶绿素）
4. **Total chlorophyll per unit weight**（单位重量总叶绿素）
5. **Chlorophyll a/b**（叶绿素 a/b 比值）

每张图都应是 **sun vs shade** 的对比，并带 **means 与 standard errors**。

### 3.8 讲义中的三幅插图（转换后丢失，此处记录其内容与出处）

| 编号 | 内容 | 出处/版权 |
|---|---|---|
| **Figure 1** | A foxglove leaf（毛地黄叶片，用于示意叶柄 petiole 的位置） | Photo: Pipi69e, Public domain, via Wikimedia Commons |
| **Figure 2** | Equipment used in this experiment（本实验所用器材） | — |
| **Figure 3** | Diagram of a cuvette with light passing through（光穿过比色皿的示意图，用于说明光程 d） | Marmot2019, CC BY-SA 4.0, via Wikimedia Commons |

---

## 四、课堂补充

### 4.1 讲义中的操作警示（原文强调项）

- ⚠️ **"IMPORTANT: make sure you do not mix up the pipettes, you must avoid getting chlorophyll into your clean ethanol stock!"**
  转移绿色提取液时**必须换用新的巴斯德吸管 (new Pasteur pipette)**，绝不能把用过的吸管插回干净乙醇储液瓶——一旦污染，整瓶乙醇报废，且**空白/参比 (blank) 会失效**，所有吸光度读数都会偏。
- ⚠️ 比色皿操作：**"be careful not to touch the sides of the cuvette with your fingers"**（不要用手指碰比色皿的**光学侧面**）；并且 **"Be careful to remember which is which"**（记清哪个是 sun、哪个是 shade，两管外观都是绿色，极易混淆）。
- ⚠️ 过滤时：**"making sure that it all goes into the filter paper and does not go over the top"**（务必让液体全部进入滤纸内，不要从滤纸上缘溢出——溢出即绕过过滤，未滤净的颗粒会抬高 A₇₅₀）。
- 讲义**未**提及乙醇的安全须知（易燃、挥发）；96% 乙醇属易燃液体，实际操作须远离明火，此为常规实验室要求（📎 背景补充，讲义未述）。

### 4.2 关于全课总结 / 评估说明 / 考试提示

**讲义中没有任何全课总结、课程回顾、评估权重、提交截止日期或考试提示。** 尽管本周是 Hilary Term 第 10 周（末周），材料仍是纯粹的实践讲义，未包含课程收尾性的行政信息。

与「评估/交付」最接近的是讲义第 8 点对**数据分析与呈现**的要求（见 5.6），以及讲义正文中留白待填的**答题空行**（petiole length、leaf area、weight、leaf weight ratio、开放问答等）——这份讲义本身即是一份**需填写并提交的 worksheet 式记录单**。

### 4.3 交叉引用与参考文献（讲义 References 全录）

讲义正文交叉引用了纪录片 **How to Grow a Planet (Week 1)** 用于理解电子传递链。

文末参考文献 4 条，完整记录如下：

1. **Gjindali A, Johnson GN (2023)** Photosynthetic acclimation to changing environments. *Biochem Soc Trans* 51(2):473-486. doi:10.1042/bst20211245
   —— 讲义引用处：支持「acclimation」概念。
2. **Johnson GN, Scholes JD, Horton P, Young AJ (1993)** Relationships Between Carotenoid Composition and Growth Habit in British Plant-Species. *Plant Cell Environ* 16(6):681-686. doi:10.1111/j.1365-3040.1993.tb00486.x
   —— 讲义引用处：*D. purpurea* 的生境（林缘、林窗、树篱）。
3. **Lichtenthaler HK, Wellburn AR (1983)** Determinations of total carotenoids and chlorophylls a and b of leaf extracts in different solvents. *Biochem Soc Trans* 11(5):591-592. doi:10.1042/bst0110591
   —— 讲义引用处：**叶绿素 a/b 换算公式的来源**（⭐ 本周核心公式出处；注意标题中 "in different **solvents**" 呼应 ε 依赖溶剂这一点）。
4. **Rodger A (2013)** Concentration Determination Using Beer-Lambert Law. In: Roberts GCK (ed) *Encyclopedia of Biophysics*. Springer Berlin Heidelberg, pp 360-361. doi:10.1007/978-3-642-16712-6_775
   —— 讲义引用处：**Beer-Lambert Law**。

---

## 五、Practical 要点

### 5.1 目的

比较在 **sun** 与 **shade** 条件下生长的同一物种（2025 S2 为 **barley / Hordeum vulgare**）在
① **形态**（叶柄长度、叶重比）与
② **叶绿素含量**（Chl a、Chl b、总量、a/b 比）
上的差异，从而检验**光驯化 (acclimation)** 的存在与方向。

### 5.2 材料与器材（据讲义操作步骤归纳）

**植物材料**：每对学生 2 株 —— **1 株 sun、1 株 shade**。

**试剂**：
- **96% ethanol（96% 乙醇）** —— 提取溶剂，同时用作**空白/参比 (blank)**。

**器材**：
- 尺（量 petiole length）
- **graph paper（方格纸）** —— 测叶片面积
- **fine balance（精密天平）** —— 称叶片重量
- **mortar and pestle（研钵与研杵）** —— 研磨提取
- **Pasteur pipettes（巴斯德吸管）** —— 至少 2 支，分工严格（见 4.1）
- **measuring cylinder（量筒）** —— 定容至 10 ml
- **parafilm（封口膜）** —— 封口后混匀
- **filter paper（滤纸）+ filter funnel（漏斗）+ beaker（烧杯）** —— 过滤
- **cuvettes（比色皿）×3** —— 1 支空白 + 2 支样品；**1 cm 光程**
- **spectrophotometer（分光光度计）** —— 可设波长、带 Zero 键

### 5.3 步骤 A：形态观察与测量

1. **观察两株植物**，记录外观差异（"Note their appearance, how do they look different?"）。
2. **各摘下最大的一片叶 (the largest leaf)**，**尽可能贴近地面剪取 (cutting it as close to the ground as possible)** —— 目的是保留完整的叶柄。
3. **测量 petiole（叶柄，即 leaf stalk）的长度**。
   - 记录栏：`Petiole Length: ……`

### 5.4 步骤 B：叶面积与叶重比

4. 从每片叶上**剪下约 2 cm × 2 cm 的方块**。
5. **测面积**：把叶块放在**方格纸**上，**沿周边小心描出轮廓**，然后**数轮廓内 mm 方格的个数**来估算面积。
   - 记录栏：`Leaf area sun: ……` / `Leaf area shade: ……`
6. **用精密天平称量**两个叶块。
   - 记录栏：`Weight sun: ……` / `Weight shade: ……`
7. **计算叶重比 (leaf weight ratio) = weight / area**。
   - 记录栏：`Leaf weight ratio sun: ……` / `Leaf weight ratio shade: ……`
8. **思考题（讲义留白）**：「If these values are different, **why do you think this is?**」

⚠️ 注意：**同一个叶块要既测面积、又测重量、还要拿去提取叶绿素** —— 这样才能把叶绿素量同时归一到该叶块的面积和重量上（3.5 节）。所以顺序不能颠倒：**先描面积、再称重、最后研磨**。

### 5.5 步骤 C：叶绿素提取（讲义逐条）

对**每一个**叶块分别做（sun 与 shade 各一套，全程不可混）：

1. 取一块叶片放入**研钵 (mortar)**。
2. 用巴斯德吸管**加 3–4 滴 96% 乙醇**。
3. 用**研杵 (pestle)** 尽可能**充分研磨**叶片 —— 判断标准：**研杵底部出现绿色涂抹痕 (a green smear on the bottom of the pestle)**。
4. **再加几滴乙醇**，用研杵搅拌，得到**均匀的绿色溶液，其中不含任何叶片碎块 (without any leaf pieces in it)**。
5. **换一支新的巴斯德吸管**，把绿色液体转移到**量筒**中。
   - ⚠️ **IMPORTANT：不要弄混吸管，绝不能让叶绿素进入干净的乙醇储液！**
6. **用少量乙醇洗涤研钵 (wash the mortar)**，洗液一并转入量筒 —— 这是**定量转移**的关键，避免损失。
7. **加乙醇定容至 10 ml**。
8. 用 **parafilm 封口**，**小心混匀 (mix carefully)**。

**过滤**：

9. 取一张**滤纸**，**对折两次**（先对半，再对半）成四分之一。
10. 展开折好的三角形形成**圆锥 (cone)**，放入**漏斗**。
11. 把漏斗**尖端朝下**放进**烧杯**。
12. 把叶绿素提取液倒入漏斗，**确保全部进入滤纸内、不从上缘溢出**。

### 5.6 步骤 D：分光光度测定

**测定波长：665 nm、649 nm、750 nm。**

1. 取 **3 支比色皿**：**1 支装干净乙醇**（空白/参比），**另 2 支分别装两份叶绿素提取液**。
   - ⚠️ 记清哪支是 sun、哪支是 shade；**不要用手指碰比色皿侧面**。
2. 将分光光度计**波长设为 665 nm**。
3. 把**干净乙醇比色皿**放入分光光度计。
4. **按 Zero 键调零**。
5. 依次放入两支样品比色皿，**记录各自的吸光度**。
   - 讲义注：视仪器型号而定，有的分光光度计可**同时放入全部比色皿并快速切换**。
6. **波长改为 649 nm**，**重复步骤 c–e**（即：放空白 → 调零 → 测样品）。
7. **波长改为 750 nm**，**重复步骤 c–e**。

⭐ **关键点：每换一个波长都必须重新用乙醇调零**（讲义把 c–e 整段重复，就是这个意思），因为 ε、光源强度与检测器响应都随波长变化。

### 5.7 步骤 E：计算

1. 用 **Lichtenthaler & Wellburn (1983) 公式**（见 3.3）算出**每份提取液**的 Chl a、Chl b 浓度（μg·ml⁻¹）。
2. 结合**提取液体积（10 ml）**与**所用叶片量（面积、重量）**，换算为**叶片中的含量**，并**分别以单位面积和单位重量表示**（见 3.5）。

**📎 计算示例（背景补充，讲义未给示例数据；数值为示范用途）**：

设 sun 叶块测得 $A_{665}=0.812$，$A_{649}=0.340$，$A_{750}=0.012$；叶块面积 $=3.85\ \mathrm{cm^2}$（即 385 mm²），重量 $=0.0462\ \mathrm{g}$，提取液 10 ml。

净吸光度：
$A_{665}-A_{750} = 0.812-0.012 = 0.800$；$A_{649}-A_{750} = 0.340-0.012 = 0.328$

$$\text{Chl }a = 13.95\times0.800 - 6.88\times0.328 = 11.160 - 2.257 = 8.90\ \mathrm{\mu g\,ml^{-1}}$$
$$\text{Chl }b = 24.96\times0.328 - 7.32\times0.800 = 8.187 - 5.856 = 2.33\ \mathrm{\mu g\,ml^{-1}}$$

总叶绿素 $= 8.90+2.33 = 11.23\ \mathrm{\mu g\,ml^{-1}}$；**a/b 比 $= 8.90/2.33 = 3.82$**

总质量 $= 11.23 \times 10 = 112.3\ \mathrm{\mu g}$

单位面积 $= 112.3 / 3.85 = 29.2\ \mathrm{\mu g\,cm^{-2}}$
单位重量 $= 112.3 / 0.0462 = 2431\ \mathrm{\mu g\,g^{-1}} = 2.43\ \mathrm{mg\,g^{-1}}$

叶重比 $= 0.0462 / 3.85 = 0.0120\ \mathrm{g\,cm^{-2}} = 12.0\ \mathrm{mg\,cm^{-2}}$

### 5.8 步骤 F：数据分析与呈现（讲义第 8 点，原文要点全录）

- 生物学参数**本身可变**，且**永远无法完美测量**，所以**每个参数都需要不止一个估计值**，才能对测得的数值有信心，才能判断 sun 与 shade 之间是否真的存在差异。
- ⭐ **因此必须从至少另外 4 对学生 (at least 4 other pairs of students) 收集数据** —— 即每个处理 **n ≥ 5**。
- 对每个参数计算 **means（均值）和 standard errors（标准误）**。
- **作 5 张图**（见 3.7）。
- **必须使用统计检验**判断差异是否**显著 (significantly)**。
- **软件**：讲义点名 **R studio** 或 **GraphPad Prism**。

**讲义留白提问**：
> "What **statistical test** could you use to compare **two numerical values** (assuming they are **normally distributed**)? ……"

📎 **背景补充（该题答案）**：**两独立样本 t 检验 (unpaired / independent-samples Student's t-test)** —— 因为是比较**两组**（sun vs shade）**连续型、正态分布**数据的**均值**，且两组来自不同植株、互相独立。（若数据不服从正态分布，则改用非参数的 **Mann-Whitney U test**。讲义括号里特意写 "assuming they are normally distributed" 正是在提示 t 检验的前提条件。）

### 5.9 步骤 G：结果解读（讲义列出的 4 个必须思考的问题，原文全录）

> "Having completed your experiment, you now need to consider what the results mean. Questions you need to consider include:"

1. **叶柄长度**在两株植物间是否不同？若不同，可能是**为什么**？
2. **叶重比**在 sun 与 shade 植株间是否不同？这告诉你关于**叶片结构 (leaf structure)** 的什么信息？
3. **总叶绿素**在两株植物间如何变化？**分别以单位面积和单位重量表示**时——**这两种表达方式各自告诉你什么？**
4. **叶绿素 a/b 比值**是否随生长条件变化？**改变这两种色素的相对含量对植物有什么好处？**

⚠️ 讲义**未提供**这些问题的答案，它们是开放式解读题。

📎 **背景补充（作答方向，讲义未给；基于讲义 Background 与 acclimation 概念的合理推理）**：
- **Q1 叶柄长度**：遮阴植株常伸长叶柄/茎（**避阴反应 shade avoidance**），把叶片送到光更强的位置，减少被遮挡。
- **Q2 叶重比**：阳生叶通常**更厚更致密**（LWR 更大），有更多层栅栏组织以容纳更多光合机构、应对高光；阴生叶更薄更展开，以最小的建造成本截获最多的光。
- **Q3 两种表达方式**：**per unit area** 反映的是「单位受光面积上的捕光能力」，与光截获效率直接相关；**per unit weight** 反映的是「单位投入生物量所配置的捕光色素量」，是**资源分配效率**的度量。两者可能给出方向不同的结论——例如阴生叶单位面积叶绿素未必更高，但**单位重量**往往显著更高，因为叶片更薄（这正是讲义让学生同时算两种表达方式的教学用意）。
- **Q4 a/b 比值**：Chl b 主要位于**捕光复合体 (light-harvesting complexes, LHC)** 中，Chl a 则同时存在于反应中心与 LHC。**遮阴条件下植株倾向增大 LHC 比例 → Chl b 相对增多 → a/b 比值下降**，从而在弱光下最大化捕光；强光下则减小天线尺寸以避免过量激发能造成的光损伤。

---

## 六、易错点 / 重点难点

| # | 易错点 | 说明与对策 |
|---|---|---|
| 1 | **物种混淆** | 讲义**只有开头一句**说明换成了大麦，正文（标题、Study species、Figure 1）仍写 *Digitalis purpurea*。别在报告里写错实验材料。 |
| 2 | **提取不完全** | 判断标准是**研杵底部有绿色涂抹痕**、且溶液中**没有任何可见叶片碎块**。研磨不足 → 叶绿素残留在组织里 → 浓度系统性偏低。 |
| 3 | **定量转移不完全** | 讲义专门写了「**wash the mortar** with a little more ethanol」这一步。忘记洗研钵 = 直接丢失一部分叶绿素，结果偏低。 |
| 4 | **吸管交叉污染** | 转移绿液**必须换新吸管**。一旦把带叶绿素的吸管插进干净乙醇储液，**空白就被污染**，所有读数全废。这是讲义唯一用 "IMPORTANT" 标出的警告。 |
| 5 | **定容不准** | 必须**加乙醇到 10 ml 整**。体积错了，3.5 节的 $C\times V$ 换算就全错。 |
| 6 | **过滤溢出/过滤不净** | 液体从滤纸上缘溢出 = 绕过过滤。未滤净的颗粒会散射光，**表现为 $A_{750}$ 明显大于 0**。发现 $A_{750}$ 偏高应重滤重测。 |
| 7 | **比色皿指纹与划痕** | 手指只能捏**磨砂面**，不能碰**光学通光面**。指纹属于典型的「非叶绿素吸收/散射」干扰。 |
| 8 | **搞混 sun 与 shade** | 两支提取液都是绿色，外观难辨。**必须做标记**，讲义原文即警告 "Be careful to remember which is which"。 |
| 9 | ⭐ **换波长后忘记重新调零** | 讲义把「c–e」三步**在每个波长下完整重复**。换波长必须重新用乙醇空白调零，否则基线错位。 |
| 10 | ⭐ **波长设错** | 是 **665 / 649 / 750 nm**，不是常见的 663/645（那是 80% 丙酮体系的组合）。**波长与系数是配套的**，设错波长再套 13.95/6.88/24.96/7.32 就完全无效。 |
| 11 | ⭐ **溶剂与系数不匹配** | Lichtenthaler & Wellburn 的系数**绑定 96% 乙醇**。用丙酮、DMF 或不同浓度乙醇必须换一整套系数（讲义强调 ε 是 "in a given solvent" 的）。 |
| 12 | **忘记减 $A_{750}$** | 公式里是 $(A_{665}-A_{750})$ 而**不是** $A_{665}$。漏减会让两个浓度都系统性偏高。 |
| 13 | **交叉项符号弄反** | Chl a 式中 **减** 6.88×(A649−A750)；Chl b 式中 **减** 7.32×(A665−A750)。**两个交叉项都是负号**，且**系数不可互换**（6.88 只配 a 式，7.32 只配 b 式）。 |
| 14 | ⭐ **单位换算** | ① 方格纸数的是 **mm²**，1 cm² = **100** mm²；② 结果是 **μg·ml⁻¹** 不是 mg·ml⁻¹；③ **μg → mg 除以 1000**；④ 天平读数是 **g** 还是 **mg** 要看清；⑤ 别把「提取液浓度 μg·ml⁻¹」当成「叶片含量 μg·cm⁻²」直接汇报。 |
| 15 | **光程假设** | 系数已假定 **1 cm 比色皿**（$d=1$ 才能略去光程项）。若用了半微量或其他光程的比色皿，必须先把 A 折算到 1 cm 等效值。 |
| 16 | **样本量不足** | 讲义硬性要求**再收集至少 4 对同学的数据**。只用自己那 1 株 vs 1 株，n=1，**无法做统计检验，也无法算标准误**。 |
| 17 | **误差棒画错** | 讲义要求 **standard error（标准误 SE）**，不是 standard deviation（标准差 SD）。$SE = SD/\sqrt{n}$。 |
| 18 | **混淆 adaptation 与 acclimation** | 本实验同物种、不同发育光环境 → 观察到的是 **acclimation（表型）**，**不是 adaptation（遗传）**。这是最容易在解读题里失分的概念点。 |

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Chlorophyll | 叶绿素 | 吸收蓝光与红光、反射绿光的光合色素，本周的定量对象 |
| Chlorophyll a | 叶绿素 a | 两种叶绿素之一，在 665 nm 附近吸收占主导，存在于反应中心与捕光复合体 |
| Chlorophyll b | 叶绿素 b | 另一种叶绿素，吸收波长与 a 略有差异，在 649 nm 的相对贡献更大 |
| Chlorophyll a/b ratio | 叶绿素 a/b 比值 | Chl a 与 Chl b 浓度之比，无量纲，反映捕光天线相对大小的生化指标 |
| *Hordeum vulgare* / barley | 大麦 | 2025 年第二学期本实践实际使用的植物材料 |
| *Digitalis purpurea* / foxglove | 毛地黄 | 讲义原定物种，原生于林缘、林窗与树篱，已被大麦替换 |
| Petiole | 叶柄 | 叶片的柄状部分（leaf stalk），本实验测其长度作为形态指标 |
| Leaf weight ratio | 叶重比 | 叶片重量 / 叶片面积，反映叶片厚度与致密程度 |
| Morphology | 形态（学） | 植物的外形结构，如叶片排列、株高、叶厚 |
| Adaptation | 适应 | 个体或物种间的**遗传性**差异，使其更适于在特定条件下生存 |
| Acclimation | 驯化 / 驯化适应 | 生物体针对其**发育环境**发生的**表型**改变，本实验测的就是它 |
| Electron transport chain | 电子传递链 | 被叶绿素吸收的光能所驱动的电子传递过程，最终支撑糖的合成 |
| Sun plant / Shade plant | 阳生植株 / 阴生植株 | 分别在强光与弱光下生长的两组实验植株 |
| Spectrophotometer | 分光光度计 | 可设定波长、测量溶液吸光度的仪器，带 Zero 调零功能 |
| Cuvette | 比色皿 | 盛放待测液的方形光学池，本实验用 1 cm 光程；侧面不可用手触碰 |
| Absorbance (A) | 吸光度 | $A=\log_{10}(I_0/I_t)$，衡量特定波长的光被溶液吸收的程度，无量纲 |
| Blank / Reference sample | 空白 / 参比 | 本实验为纯净 96% 乙醇，用于提供 $I_0$ 并在每个波长调零 |
| Beer-Lambert Law | 朗伯-比尔定律 | $A=\varepsilon c d$，吸光度与浓度及光程成正比 |
| Extinction coefficient (ε) | 消光系数 | 特定分子在**特定溶剂、特定波长**下的吸光能力常数 |
| Path length (d) | 光程 | 光穿过溶液的距离，即比色皿长度；用 1 cm 皿时该项可略去 |
| Overlapping spectra | 重叠光谱 | Chl a 与 b 的吸收带互相重叠，故需联立方程分离 |
| Simultaneous equations | 联立方程 | 用两个波长的吸光度解出两个未知浓度的数学手段 |
| 665 nm | 665 纳米 | 测定波长之一，以 Chl a 吸收为主 |
| 649 nm | 649 纳米 | 测定波长之一，Chl b 相对贡献更大 |
| 750 nm | 750 纳米 | 两种叶绿素均**不吸收**的波长，用作基线以扣除浊度/散射等干扰 |
| Turbidity / Scattering | 浊度 / 散射 | 未滤净颗粒造成的非吸收性信号，靠减 $A_{750}$ 校正 |
| 96% ethanol | 96% 乙醇 | 本实验的提取溶剂兼空白；换算系数与该溶剂绑定 |
| Mortar and pestle | 研钵与研杵 | 研磨叶片以释放叶绿素的器具 |
| Pasteur pipette | 巴斯德吸管 | 转移液体用；干净乙醇与叶绿素液必须分用不同支 |
| Measuring cylinder | 量筒 | 将提取液定容至 10 ml |
| Parafilm | 封口膜 | 封住量筒口以便安全混匀 |
| Filter funnel / Filter paper | 漏斗 / 滤纸 | 滤纸对折两次成锥形置于漏斗中，过滤提取液中的残渣 |
| Fine balance | 精密天平 | 称量叶块重量 |
| Graph paper | 方格纸 | 描出叶块轮廓并数 mm 方格以估算叶面积 |
| Mean | 均值 | 各组重复测量的平均值 |
| Standard error (SE) | 标准误 | 均值的不确定度，$SE = SD/\sqrt{n}$，本实验误差棒用它 |
| t-test | t 检验 | 比较两组正态分布数值均值差异的统计检验（讲义留白题答案，📎） |
| R studio / GraphPad Prism | R studio / GraphPad Prism | 讲义点名可用于作图与统计检验的软件 |
