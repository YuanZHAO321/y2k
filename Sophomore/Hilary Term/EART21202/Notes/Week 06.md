# EART21202 Global Climate Change — Week 06

## 一、本周主题

本周的题目是 **气候模拟 / 全球气候模式（Climate Modelling / Global Climate Models, GCMs）**，授课时间 **2026 年 3 月 19 日**，主讲 **Dr Thomas Bannan**（Thomas.Bannan@Manchester.ac.uk）。

### ⚠️ 关于周号：文件夹 Week 06 = 课程 Week 7

本课官方周号里包含一个**期中线上测验周**（课程 Week 6，Mid Unit Test，讲义 Slide 2 标注 10th March），那一周**没有讲座、没有讲义材料**，因此课程材料文件夹里没有对应的一周。结果就是：**从本周开始，讲义文件名和幻灯片标题里的 "Week N" 比材料文件夹的周号大 1。**

- **本笔记的规范编号是 Week 06**（按材料文件夹连续编号 01–10，全库统一）。
- **对应的课程官方周号是 Week 7**，这就是讲义标题写 "Global Climate Change – Week 7" 的原因，**不是错标，不必登记勘误**。
- 下文凡是引用讲义原文里的 "week 7"，都指课程官方周号；凡是说「本周」，都指本笔记的 Week 06。两者是同一次课。

### 本周在全课中的位置

讲义 Slide 2 给出了 2026 年的完整课程地图：

- Week 1 — Introduction to climate change and its impacts（5th Feb）
- Week 2 — Natural climate variability（12th Feb）
- Week 3 — Radiation Law / Greenhouse Effect / Radiative forcing / feedbacks（19th Feb）
- Week 4 — Anthropogenic impacts（26th Feb）
- Week 5 — The Evidence Base for Climate Change（5th March）
- Week 6 — **Mid Unit Test（10th March）**
- **Week 7 — Climate Models（19th March）← 本周（＝笔记 Week 06）**
- Week 8 — Climate Change Adaptation（26th March）
- Week 9 — Effects of Climate Change: Case Studies（23rd April）
- Week 10 — Climate Change Mitigation（30th April）
- Week 11 — Revision Lecture（7th May）

讲师开场第一句就点明了本周的定位：

> "welcome to the **second half of Global Climate Change**. This is the **first time I've seen you since the mid-semester test**."

也就是说，**本周是下半学期的第一次讲课**，上一次见面是 3 月 5 日的 Week 5，中间隔了 3 月 10 日的期中测验周。他又补了一句结构说明：

> "we're moving now into the **second component of the tool element** of this course."

（转写的 "tool element" 是 **"taught element"（授课模块）** 的语音讹误，已登记勘误。）

**上下衔接的逻辑链非常清晰，这是理解本周的关键：**

| 周次 | 内容 | 在本周扮演的角色 |
|---|---|---|
| Week 3 | 辐射律、温室效应、辐射强迫、反馈 | **提供模式内部的物理方程**——讲师明说「the concept of radiative forcing is central to climate models」 |
| Week 4 | 人为影响（Simon 主讲）、土地利用变化 | **提供模式的输入项与情景设定** |
| Week 5 | 证据基础、观测与不确定性 | **提供模式的验证数据（hindcast 的比对对象）** |
| **Week 6（本周）** | **气候模式** | **把上述三块拼成「归因 + 预测」的工具** |
| Week 8 | 气候变化适应 | 用本周的模式输出（尤其区域降水投影）去谈适应 |
| Week 9 | 案例研究（讲师在转写里说会请外宾讲地球工程） | 用本周的 1.5 °C 阈值讨论去谈干预 |
| Week 10 | 减缓 | 用本周的 RCP 情景去谈政策 |

### 贯穿全课的那个大问题（Slide 5）

Slide 5 重复了 Week 5 用过的框架，这是全课的骨架句：

> **"How do we know climate change is real — and how do we know it's us?"**

拆成三问：

| 问题 | 靠什么回答 | 对应周次 |
|---|---|---|
| **Is it changing?**（在变吗） | 观测（Observations） | Week 5 |
| **Is it unusual?**（异常吗） | 古气候背景（Context from paleoclimate） | Week 1、Week 2 |
| **Is it us?**（是我们干的吗） | **物理（week 3）＋ 模式（week 7）＋ 测量（week 5）＝ 归因（attribution）** | 本周把「模式」这一块补上 |

讲师在转写里强调：

> "how do we know it's us? It's the **physical basis**, which is developed through week three, **climate models**, which we're going to discuss this week, **measurements**, which you should know more about from week five, which ultimately leads to this sort of **attribution** and understanding."

**换句话说：本周是「归因三件套」里最后交付的那一件。** 没有模式，观测只能告诉你「变了」，物理只能告诉你「有可能是这样」，但没法把观测到的变化**定量地分配**给某一个驱动因子。

### 本周的官方 ILO（Slide 4）

学完本周你应当能够：

1. **理解气候模式的角色**，并解释为什么要用气候模式来研究和预测气候变化。
2. **识别全球气候模式的主要组件**，以及它们如何相互作用。
3. **讨论气候模式中的不确定性**，以及**回报 / 后报（hindcasting）**如何被用来检验模式的可靠性。
4. **区分自然气候变率（natural climate variability）与人为气候变化（anthropogenic climate change）**。
5. **解释代表性浓度路径（Representative Concentration Pathways, RCPs）**如何为未来气候预估提供依据。
6. **理解气候模式未来会如何演变。**

讲师对第 3 条和第 6 条做了额外说明：

> "You should be relatively familiar with the idea of **forecasting**, but perhaps **hindcasting is a new principle** to you."

> "And **a bit that I've added in the last couple of days** that might not be reflected on the [Canvas] side is **how climate models might change into the future**."

**注意**：第 6 条（AI / ML）是讲师**在课前几天临时加进去的新内容**，Canvas 上的旧版材料可能没有。这既说明它是新鲜的、讲师自己感兴趣的内容，也说明它**很可能出现在考题里**——Slide 36 的样题清单里确实有一道专门问这个。

### 本次课的时间结构（Slide 3）

- **Part 1**：Key points on climate change modelling（45 分钟）
- **Part 2**：Q/A and Break（10 分钟）
- **Part 3**：Workshop on climate modelling（50 分钟）

转写显示的实际节奏：讲师连续讲约 25 分钟（讲到「模式发展史」结束）→ 插入 10–15 分钟的 **Mentimeter 互动 workshop**（"build your own global climate model"）→ 回来讲第二半（分辨率、box model、IPCC、RCP、误差、hindcast、AI）→ 讲下周与 Week 9 安排 → 放学生做 Q1–Q9 的完整 workshop。讲师明说：

> "today is probably a **slightly shorter lecture than normal**."

### 本周结束后你应该能回答的问题（Slide 36）

讲义 Slide 36 直接给出了 **13 道样题**（"Example exam questions from today"）。这份清单实际上就是本周第二节的目录，**建议当作复习提纲逐条自测**：

1. 解释为什么 **1.5 °C 全球增温阈值**被认为重要，并论述为什么超过 2 °C 会带来更大风险。
2. 解释为什么**耦合不同地球系统组件**（大气、海洋、冰冻圈、生物圈）能改善气候模式表现。
3. 描述全球气候模式如何被用来**把观测到的增温归因于人类活动**。
4. 解释**自然气候变率与人为气候变化的区别**，以及模式如何帮助区分二者。
5. 描述地球在气候模式**网格**中是如何被表示的，并解释**模式分辨率**为什么重要。
6. 解释 **RCPs** 在预估未来气候变化中的作用。
7. 描述 **hindcasting** 如何被用来评估气候模式的表现。
8. 论述全球气候模式中**不确定性的主要来源**。
9. 解释**大气组分的寿命（lifetime）**（如气溶胶或温室气体）如何影响气候模式预测。
10. 描述**观测数据**在改进与验证气候模式中的作用。
11. 解释为什么气候模式在**全球与长时间尺度**上表现优于**区域与短时间尺度**。
12. 论述**计算能力的进步**如何改善了气候模式的能力与分辨率。
13. 描述气候模拟的**未来发展方向**，包括更高分辨率模式、更好的观测、以及 AI / 机器学习的角色。

📎 背景补充：注意第 9 题（大气组分寿命）在讲义正文里其实**只在 Slide 21 的 box model 那一页隐含出现**（sources / sinks 决定浓度），讲义没有明写 lifetime 的定义或公式。转写里讲师提了一句「it helps us understand **how long these greenhouse gases will live in the atmosphere**」。这道题的答题材料需要你自己把 Slide 21 的质量收支和 Week 3/Week 4 学过的气体寿命概念接起来——本笔记第三节会把这个缺口补上，并明确标注哪部分是补充。

---

## 二、核心概念

本节按讲义推进顺序展开，分为十一大块：

（A）为什么要用气候模式；（B）GCM 的物理内容与四大组件；（C）三维网格与分辨率；（D）模式发展史：从不耦合到地球系统模式；（E）空间与时间分辨率的实际影响；（F）HadCM3 与垂直分层；（G）大气成分的箱模式；（H）IPCC 评估报告与模式演进；（I）模式性能的尺度依赖；（J）RCP 情景与模式间可比性；（K）误差来源、hindcasting 与归因协议；（L）GCM 的未来：AI 与机器学习。

---

### A. 为什么要用气候模式

#### A1. 模式回答的是「观测回答不了」的问题

讲义 Slide 7 和 Slide 8 用两句设问开场：

> **"Our key question today: How do we predict future climate change?"**
> **"Our key question today: How do we predict the impact of climate change?"**

注意这是**两个**问题，不是一个。第一个是「未来会变多少」，第二个是「变了之后会怎样」。讲师在转写里把这两层说得很清楚：

> "Global climate models are essential for both understanding **what those temperatures could look like** into the future, but also **the impacts that they can have**."

**是什么**：全球气候模式（Global Climate Model / General Circulation Model, GCM）是一套用物理方程描述地球气候系统、并在计算机上数值求解的程序。讲义 Slide 9 的定义要点：

> "We have covered the main concepts that feed into computer models to simulate and predict climate change. We now look at **how these models work and their results**."
> "**The concept of radiative forcing is central to climate models.**"

**为什么**（Slide 9 的四点，逐条拆解）：

1. **辐射强迫是核心概念。** 模式内部真正在算的，是每一个格点、每一个时间步上的能量收支。Week 3 学的辐射强迫（radiative forcing）就是模式接受外部扰动的接口。
2. **模式投影的是「气候」，不是「天气」。** 讲义原文：
   > "Climate models project **climate** (the average weather over a long period of time, e.g., a **30-year period**), not **weather** (what an area experiences on an **hourly or daily** basis)."

   讲师补充：
   > "we're really thinking about these on a **multi-annual timescale up to climatological timescales of around 30 years** or so. So we're not predicting weather and isolated events, we're predicting **global aggregate effects** in large part."

3. **模式帮助我们理解「我们的行动如何影响未来气候」。**
4. **模式让我们看不同的排放情景。** 讲义原文："They allow modelers to look at **different scenarios** of increased greenhouse gas emissions and see how increases may affect us."

**怎么用 —— 讲师给了一个非常好的说法「拉杆（levers）」**（转写独有）：

> "once we have an understanding that they're performing sufficiently well, we have a tool to **play with different emission scenarios, different interventions, different scenarios, both economic, behavioral, and environmental**, to see how each one of those decisions we make now might affect us into the future. So they allow us to **pull different levers in a way that we can't do with observations**."

**这句话是「为什么用模式」这道题的最佳答案骨架**：我们只有一个地球，不能做对照实验；模式是唯一能做「反事实实验（counterfactual experiment）」的地方。你可以关掉人为排放跑一次、开着跑一次，两次相减就是人为的贡献——这正是后面 Slide 27 的归因协议。

**边界条件（非常重要，考点）**：模式的可信输出是**长期、大尺度平均**；它**不保证**告诉你 2043 年 7 月曼彻斯特会不会下雨，也**不保证**某一年的年际起伏。讲师后面看 hindcast 图时会再强调一次这一点。

#### A2. 三支柱途径（three pillar approach）— 转写独有

讲师在讲 Slide 7 那张图时说：

> "I love this figure, it's showing a combination of the **fieldwork approach**, which I'm most interested in, but how we must work with **atmospheric modelers, global climate modelers**, to one, **validate the models** that are being produced, but two, **help inform the processes** which are important within them. And ultimately if we take this **three pillar approach**, we can move towards this picture where we understand climate change… so that we can move to an overall more sustainable and equitable planet."

**三支柱 = 外场观测（field work）＋ 实验室研究（laboratory）＋ 模式（modelling）。** 注意讲师给了**外场观测服务于模式的两个具体功能**：

- **validate**（验证模式输出对不对）
- **inform**（告诉建模者哪些过程重要、参数该取什么值）

这第二点很容易被漏掉。**观测不只是"打分员"，它还是"供料方"** —— 参数化方案（parameterisation）里的系数就是从观测里拟合出来的。

#### A3. 为什么要关心 1.5 °C / 2 °C —— 风险随温度的非线性上升

讲师在讲 Slide 8 时（对应 IPCC 的「燃烧棒（burning embers）」类图）说：

> "as we move to elevated temperatures, the **level of additional risk** due to different aspects of climate… become **high or very high**. And that can be in terms of **isolated effects on regional nature** or more **global aggregate impacts**, which as you move above 1.5 or 2 degrees C, the level of additional risk due to climate change becomes **massive**."

并且强调**不只是全球平均的影响**：

> "it's not just the global impacts that we're interested in, it's the impact that it has on **individual communities who might be disproportionately affected** by changes."

这正好对应 Slide 36 的第 1 道样题（1.5 °C 阈值为什么重要）。**答题时要点出「风险不是线性增长的」以及「分布不均、脆弱群体承受更多」这两层。**

#### A4. 模式能预测到多远？—— 2100 与 2300（转写独有的量化界限）

讲师在讲 Slide 6（65–70 Myr 的地球系统变化 + 未来分支图）时说：

> "Much like the measurements, **the further you go back in time, the inaccuracies increase**. It's the same with global climate models. **Typically we predict out to 2100**, because after that the **discrepancies between the models becomes much larger**, and the **uncertainties on the estimates also become larger**. But for the purposes of today… we have included data **up to 2300**, which is about as far out as some of these global climate models will consider predicting."

**记住这个对称性（很好的答题句）**：

> 观测越往过去回溯越不准（冰芯 → 代用指标），模式越往未来外推越不准（模式间离散度增大）。**2100 是常规投影终点，2300 是极限。**

#### A5. 讲师在这里顺带提了 SSP 命名（转写独有 ⚠️）

同一段里，讲师描述 Slide 6 上的未来分支曲线时用的是 **SSP** 而不是讲义正文里的 **RCP**：

> "These are the representative concentration pathways… **a red** is a representative concentration pathway, as we just **crack on as normal**. **SSP 2 to 4.5** is there's mitigations, and **SSP 1 to 2.6** are severe mitigations in terms of reductions of greenhouse gas emissions, very quickly, very abruptly, and probably with the use of **negative emission technologies** as well."

讲义正文（Slide 24）**只讲 RCP**，从头到尾没有出现 SSP。讲师口头把两套命名混着用了。这一条已登记勘误。

📎 背景补充：**RCP 与 SSP 是两代不同的情景框架，不能混为一谈。**
- **RCP（Representative Concentration Pathway，代表性浓度路径）** 出自 IPCC **AR5**（2013–14），编号是 **2100 年的总辐射强迫（W m⁻²）**：RCP2.6 ≈ +2.6 W m⁻²，RCP8.5 ≈ +8.5 W m⁻²。RCP **只规定浓度/强迫轨迹**，不规定社会经济故事线。
- **SSP（Shared Socioeconomic Pathway，共享社会经济路径）** 出自 IPCC **AR6**（2021–23），前一个数字（1–5）是社会经济故事线（1 = 可持续，2 = 中间道路，3 = 区域竞争，4 = 不平等，5 = 化石燃料驱动发展），后一个数字仍是 2100 年辐射强迫。所以 **SSP1-2.6** ＝「可持续路线 + 2.6 W m⁻²」，**SSP2-4.5** ＝「中间道路 + 4.5 W m⁻²」。
- 因此 SSP 是「社会经济情景 × 强迫水平」的矩阵，比 RCP 多了一个维度。本课**考试按讲义走，答 RCP**；但如果你在读 AR6 原文或看新图，看到的会是 SSP。讲师用 SSP 命名，说明他在读的那张图来自 AR6。

---

### B. GCM 里到底装了什么

#### B1. 四大组件（Slide 10）

讲义 Slide 10 的核心陈述：

> "Climate models calculate the physical interactions between **four components**:
> **Atmosphere / Land / Ocean / Sea ice**"

> "The calculations are based on several inputs:
> **Air temperature / Pressure / Density / Water vapor content / Wind magnitude and many more…**"

⚠️ **注意：这里的「四组件」与答案 deck Q4 的「五组件」不一致。** 答案 deck 说 GCM 有五大组件：Atmosphere / Cryosphere / Chemistry / Ocean / Biosphere。这是**讲义与答案 deck 之间真实存在的对不上**，已登记勘误。理解方式见下（B3）。

**逐项拆解「输入变量」在物理上意味着什么：**

| 输入变量 | 物理角色 |
|---|---|
| **Air temperature（气温）** | 决定长波发射（Stefan–Boltzmann）、饱和水汽压、热通量方向 |
| **Pressure（气压）** | 气压梯度力驱动风场；决定气块的绝热过程 |
| **Density（密度）** | 通过状态方程与温压耦合；决定浮力与对流 |
| **Water vapor content（水汽含量）** | 最强的温室气体；相变释放/吸收潜热；水汽反馈的载体 |
| **Wind magnitude（风速）** | 输送热量、水汽、气溶胶；决定海气交换通量 |

📎 背景补充：讲义把这些叫「inputs」，严格说它们更像**预报变量（prognostic variables）**——模式在每个时间步上求解它们的时间演化方程（动量方程、热力学方程、连续方程、水汽方程、状态方程），而不是从外部读入。真正的「外部输入」是**边界条件与强迫**：太阳常数、温室气体浓度、气溶胶排放、地形、土地利用。这个区分讲义没有点明，但在理解「RCP 是怎么进入模式的」时很关键——**RCP 提供的是强迫，不是预报变量**。

#### B2. Slide 10 示意图上能看到的过程（转写复述）

讲师逐项念了 Slide 10 那张 GCM 示意图上的内容（讲义文字只写了标题，具体过程靠转写还原）：

> "You can see different forms of **precipitation, both over land and ocean**. You can see different **transfer of heat**. You can see the **incoming shortwave solar radiation**, the **outgoing longwave radiation**, and the **greenhouse effects** associated with that. We have **land ice or sea ice**. Changes, which we know from week four to affect **albedo**."

然后是本周最值得记住的一句「模式内部长什么样」的描述：

> "in these climate models, essentially there are **hundreds of thousands of lines of code** which simulate individual processes that are then looked at together."

以及模式要吃进去的东西：

> "these calculations can be **all of the things we've discussed in the first five or six weeks of this course** in terms of the greenhouse effect, aerosol concentrations, land use change."

**这句话点破了本周与前五周的关系：前五周教的每一个概念，都是模式里的一段代码。**

讲师还列了几个具体的「难点子系统」：

> "You're looking at **atmospheric composition**. You're looking at **land use change** and how that changes over time. You're looking at **ocean productivity** and emissions from oceans potentially. Things like **how CO₂ interacts under different temperatures of ocean**. And **sea ice extent**, which obviously affects the [reflectivity]."

（转写里 "reef activity" 是 **reflectivity（反射率）** 的语音讹误，已登记勘误。）

#### B3. 四组件 vs 五组件 —— 怎么理解这个不一致

**这是本周最容易在考试里被扣分的地方，务必想清楚。**

- **Slide 10 的「四组件」**（大气 / 陆面 / 海洋 / 海冰）描述的是**经典物理气候模式（physical climate model）** 的构成——只算能量、动量、水的物理循环。
- **答案 deck Q4 的「五组件」**（大气 / 冰冻圈 / 化学 / 海洋 / 生物圈）描述的是 **2010 年代之后的地球系统模式（Earth System Model, ESM）** 的构成——在物理之上再加了化学与生物地球化学。

两者不是矛盾，而是**两个时代的模式架构**。讲义 Slide 14–15 讲的正是从前者到后者的演化。**答题策略**：如果题目问 "key components of a GCM"，按答案 deck 的五组件答（因为那是官方答案），但最好加一句说明「早期 GCM 是 atmosphere / land / ocean / sea ice 四个物理组件，现代耦合模式再加入 chemistry 与 biosphere，冰冻圈从 sea ice 扩展为完整的 cryosphere」——这样两版都覆盖到了。

---

### C. 三维网格：地球是怎么被切开的

#### C1. 网格化（Slide 11）

讲义 Slide 11 的完整论证链：

> "The **size and complexity of the Earth** makes this challenging."
> "**Different places have different responses to energy** (e.g., land warms up and cools down faster than oceans)."
> "We divide Earth into a **3D grid** across the surface, up into the atmosphere, and down into the ocean."
> "**Each cube is analysed individually over time** while receiving information (inputs) from and passing information (outputs) to **neighbouring cubes**."
> "The **size of the cubes varies among models**."
> "A **higher resolution** model has **more, smaller cubes** and provides a **more accurate** picture of how changes to the climate impact an area."

**是什么**：把地球（大气 + 海洋）离散成一堆三维立方体（格点箱，grid box / grid cell）。每个箱子里的所有物理量被视为一个代表值。

**为什么要这样做**：控制气候的方程（Navier–Stokes 方程、热力学方程、辐射传输方程）是**偏微分方程**，没有解析解。唯一的办法是把连续的地球切成有限个格子，把微分换成差分，一步一步往前推。

**怎么用**：
1. 在每个格子里，用当前状态解一遍所有物理过程 → 得到该格子的倾向（tendency）；
2. 与相邻格子交换质量、动量、能量、水汽（**这就是讲义说的 "receiving information from and passing information to neighbouring cubes"**）；
3. 推进一个时间步；
4. 重复几百万次，直到跑完 100 年或 300 年。

讲师的补充（转写）：

> "each one of these physical processes are calculated for each one of these **3D grids** across the surface of the Earth. So these hundreds of thousands of lines of codes **interact in each grid**. And then the **interactions between the grids** are then assessed. So you can see how **computationally this becomes very expensive** as well."

#### C2. 分辨率的权衡（trade-off）—— 讲师的核心强调

讲义只说「higher resolution → more accurate」，讲师把代价说全了：

> "the **size of the cube varies between different models**. Typically, **the smaller the size of the cube, the more accurate the model is**. But computationally, that becomes **much more expensive and time consuming**. So there's a **trade-off between the number of simulations that you can run** and operate and the **resolution and perhaps accuracy** of these models."

**记住这个权衡的两端**：
- 一端是**分辨率 / 精度**；
- 另一端是**能跑多少次模拟**（即能探索多少情景、能做多少集合成员）。

📎 背景补充：这个权衡在数量上非常陡。水平格距减半 → 格点数变 4 倍；同时为了数值稳定性（CFL 条件），时间步长通常也要相应缩短约一半 → 总计算量约变 **8 倍**（若垂直层数也加密则更多）。这就是为什么分辨率的提升在历史上是「跟着超算算力线性爬」的。**这一段推导讲义与转写都没有，是我的补充。**

#### C3. 时间分辨率（转写独有，讲义完全没提）

> "We also need to think about the **time resolution** as well. So it's **not just the size of the cubes**, it's **how often these cubes are analyzed in time**, but also has an effect."

**这是讲义上没有的一个维度，务必记住。** 一个 GCM 的「分辨率」至少有三个方向：
1. **水平分辨率**（格距，km）
2. **垂直分辨率**（大气层数、海洋层数）
3. **时间分辨率**（时间步长，min）

Slide 25 把误差来源列成 "Grid size" 和 "Atmospheric levels" 两条，正好对应前两个；第三个只在转写里出现。

---

### D. 模式发展史：从「各跑各的」到地球系统模式

这一块是本周的骨干叙事，讲义用了 Slide 12–15 四页，转写又展开了很多。**Slide 12 和 Slide 13 是同一页的两个动画步骤**（先只显示问题，再显示答案），所以文字大量重复，不是排版错误。

#### D1. 第一阶段：1990s–2000s，大气模式与海洋模式各自独立

讲义 Slide 12 / 13 的共同部分：

> "Earlier models calculated physical processes for the atmosphere, land, ocean, and sea ice components **separately**."
> "Initially GCMs treated **atmosphere and ocean models as separate entities**."
> "**Atmosphere models** focused on simulating **atmospheric dynamics**, while **ocean models** represented **oceanic circulation and thermodynamics**."
> "These separate models were **run independently** and their outputs were **not directly interconnected**."

Slide 12 的最后一行是一个抛给学生的问题：**"Why is this a problem?"**

讲师给的历史定位（转写独有）：

> "The **first real true global climate models were introduced in the early 1990s** and incorporated into the **first IPCC report**. These models just looked at the **atmosphere and the ocean in isolation**. And by the atmosphere, I mean **energy transfer** in the atmosphere rather than **atmospheric composition**."

⚠️ **这句话里有一个重要的限定，容易被忽略：早期的「大气模式」指的是大气的能量与动力过程，不包括大气化学成分。** 化学要等到 2010 年代才进模式。

（顺带：IPCC 第一次评估报告 FAR 出版于 **1990 年**，讲师说 "early 1990s… incorporated into the first IPCC report"，时间上略有张力，已登记勘误备查。）

#### D2. 「不耦合」为什么是个大问题 —— 讲师的正反馈例子（转写独有，非常好的答题材料）

讲师没有直接念答案，而是让学生自己想，然后给了一个具体例子：

> "we know that from the course that these are **interacting with one another very readily**. And there can be **positive and negative feedback loops** associated with these sorts of questions. An example of that might be: as the temperature of the Earth gets slightly warmer — that can be due to a **[Milankovitch] cycle**, for example — we know that **warmer oceans contain less CO₂ in solution**. So as the planet gets warmer, there's **more outgassing of CO₂**. Hopefully now you appreciate that that will lead to a **stronger greenhouse effect** and that will continue to **exacerbate that temperature increase**. So that's an example of a **positive feedback loop where the atmosphere and the ocean are interacting**."

**把这个反馈环写成链条（务必能默写）：**

```
米兰科维奇轨道驱动 → 全球温度略升
        ↓
海水温度升高 → CO₂ 溶解度下降（Henry 定律）
        ↓
海洋向大气释放 CO₂（outgassing）
        ↓
大气 CO₂ 升高 → 温室效应增强
        ↓
温度进一步升高 ⟳（正反馈）
```

**这个例子的威力在于：它跨越了两个组件。** 如果大气模式和海洋模式各跑各的，这个环**在物理上根本不存在**——大气模式不知道海洋释放了 CO₂，海洋模式不知道大气变暖了。**这就是 "Why is this a problem?" 的标准答案。**

（转写的 "melancholic cycle" 是 **Milankovitch cycle（米兰科维奇循环）** 的语音讹误，已登记勘误。这个概念来自 Week 2。）

#### D3. 第二阶段：耦合（coupling）

讲义 Slide 13 的新增部分：

> "**Coupling** atmosphere and ocean models allowed for the **interaction** to be simulated."
> "These now allow **feedback loops** between the atmosphere and ocean, such as the influence of **ocean currents on atmospheric circulation patterns and vice versa**."
> "Thus capturing **complex interactions and feedback mechanisms**."
> "Can capture phenomena such as **El Niño–Southern Oscillation (ENSO)** which are crucial for understanding **global climate variability**."
> "GCMs can now produce **more realistic climate projections on both regional and global scales**."

讲师补充了 ENSO 的量级（转写独有）：

> "we can then start to think about simulating important **natural variability** in things like the **La Niña and El Niño cycles**, which we know can drive **temperature changes of a few tenths of a degree**."

**记住这个数字：ENSO 能驱动全球平均温度**约**几个十分之一度（a few tenths of a degree）的年际起伏。** 这个量级很关键——它解释了为什么 hindcast 图上「集合平均抓不住逐年起伏」，也解释了为什么「某一年特别热」不能直接当作趋势证据（Week 5 已经铺垫过）。

**为什么 ENSO 必须靠耦合才能模拟**：ENSO 本质上是**热带太平洋海气耦合振荡**——东风减弱 → 暖水东移 → 海表温度异常 → 大气对流位置改变 → 东风进一步减弱（Bjerknes 反馈）。它的驱动力**同时来自海洋和大气**，任何单独一方都无法自发产生它。

#### D4. 第三阶段：2010s+，地球系统模式与耦合器（Slide 14–15）

讲义 Slide 14 列出了新加入的三个子模式：

**（i）生物圈模式（Biosphere Model Integration）**
> "Terrestrial vegetation, ecosystems, and **biogeochemical cycles**."
> "Simulates processes like **photosynthesis, respiration, and carbon cycling**."
> "Enables assessment of **land use changes, deforestation, and vegetation**."

讲师补充：
> "it also enables assessment of things like **land use change**, which **Simon taught you about in detail in week four**."

**（ii）化学模式（Chemistry Model）**
> "Simulate interactions of **atmospheric gases and aerosols**, including **pollutants and greenhouse gases**."
> "Predicts atmospheric composition changes like **ozone depletion, aerosol formation, and air quality**."
> "Enhances understanding of atmospheric processes, their climate impacts, and the **effectiveness of mitigation strategies targeting pollutant emissions**."

讲师在这里做了本周最有价值的一段口头展开（转写独有）：
> "the atmospheric chemistry model — we know that there's **huge uncertainties** in things like **aerosol production** and the interaction of the aerosols with incoming solar radiation. Both through the **direct effect**, which is directly interacting with incoming solar radiation. Or the **cloud albedo effect**, which is the impact of aerosols on **cloud formation, lifetime and precipitation rates**. So these chemistry models allow us to track and understand production of things like aerosols, tropospheric ozone. And it helps us understand **how long these greenhouse gases will live in the atmosphere**."

**这段话一句话带出了三个考点：**
1. **气溶胶直接效应（direct effect）**：气溶胶粒子本身散射/吸收入射太阳辐射。
2. **云反照率效应（cloud albedo effect，即间接效应 indirect effect）**：气溶胶作为云凝结核（CCN），改变云滴数浓度与大小 → 改变云的反照率、**寿命**、**降水率**。
3. **温室气体寿命（lifetime）**：化学模式的产出之一就是各组分在大气中能存在多久——这直接对应 Slide 36 的第 9 道样题。

**（iii）冰冻圈模式（Cryosphere Model Incorporation）**
> "Cryosphere models represent **ice sheets, glaciers, snow cover, and permafrost dynamics** within GCMs."
> "Captures feedback mechanisms like **ice-albedo, sea level, and climate**."
> "Improves prediction of **ice mass balance, sea ice extent**."

讲师补充：
> "the cryosphere model… starts to look at things like **ice sheets, snow cover** and different [thermodynamics] within global climate models. And it starts to allow us to think about these **feedback loop mechanisms with the ice albedo effect, sea level rise** and different climate and sea ice extents."

**冰-反照率反馈（ice–albedo feedback）复习**（Week 3 内容）：升温 → 冰雪融化 → 地表由高反照率（冰雪 α ≈ 0.6–0.9）变为低反照率（海水 α ≈ 0.06，裸地 α ≈ 0.1–0.3）→ 吸收更多太阳辐射 → 进一步升温。**正反馈**，是极地放大（polar amplification）的主要机制之一。

#### D5. 耦合器（Coupler）—— 架构上的关键部件

Slide 14 / 15 的架构图元素被 OCR 成一串标签：

> "Atmospheric Model / Chemistry Model / Cryosphere Model / **Coupler** / Biosphere Model / Ocean Model"

**这张图的结构是：五个子模式围绕中央一个「耦合器」。** 所有子模式之间的信息交换都经过耦合器中转，而不是子模式之间两两直连。

讲师解释了这个设计的意义（**转写独有，讲义完全没说，非常重要**）：

> "In 2010, this sort of **coupling approach** was developed. And what this allows you to do is **pick your favourite atmospheric model to couple to your favourite biosphere model, to couple to your favourite ocean model** and so on. **There is not a single atmospheric chemistry model. There are many different types.** But this coupling approach allows you to **integrate different approaches to answer different, unique questions**. So this was a **huge step forward** in terms of the **operability** of these sorts of models."

**这就是「模块化 / 可插拔」的思想**：耦合器定义了标准接口（谁在什么时候把什么变量传给谁、单位是什么、格点怎么插值），于是任何符合接口的子模式都能换进来。好处：

1. **不同研究组可以专注做好一个子模式**，不必从头写整个地球系统。
2. **可以针对具体科学问题定制组合**——研究碳循环就配一个精细的生物圈模式，研究臭氧就配一个精细的化学模式。
3. **可以做「换一个子模式看结果变多少」的敏感性实验**，从而定位不确定性来源。

#### D6. 耦合的收益（Slide 15）

> "**Benefits of coupling:**
> - **Comprehensive representation** of Earth's interconnected systems.
> - Facilitates a **deeper understanding** of climate change impacts.
> - **Informs decision-making** for adaptation and mitigation efforts.
> - Enables **more accurate climate projections**, aiding in **policy formulation and resource allocation**."

讲师的收尾（转写独有，补充了一个讲义没有的关键词）：

> "it allows a much more comprehensive representation of the Earth's complete system, rather than just looking at different aspects in isolation. **You can now pick up different feedback loops, which may induce nonlinear responses.** And ultimately this leads to a much more accurate representation of the climate system."

⚠️ **"nonlinear responses"（非线性响应）这个词是转写独有的，而它恰恰是"为什么耦合重要"的最深一层理由**：反馈环把线性的系统变成非线性的；非线性系统里，**整体不等于部分之和**。你把大气模式的结果和海洋模式的结果加起来，**不等于**耦合模式的结果。这是 Slide 36 第 2 道样题（为什么耦合改善模式表现）最高分的答法。

---

### E. 分辨率：数字、历史与「为什么农民在乎」

#### E1. 分辨率的历史演进（Slide 17）

讲义 Slide 17 是本周最密集的一页：

> "Initially, GCMs had resolutions of **250 to 600 km horizontally**, with **limited vertical layers**."
> "**Improved computing power** allowed for higher resolutions, enabling better representation of **small-scale processes**."
> "Higher resolutions are crucial for capturing **regional climate variations** accurately."
> "Challenges remain, such as **parameterizing small-scale processes like clouds**, leading to **uncertainties in future climate projections**."
> "GCMs play a vital role in understanding and predicting the Earth's climate response to increasing greenhouse gas concentrations."
> "This also requires a **huge amount of computational power, not possible on personal computers**."

**记住这个起点数字：250–600 km 水平分辨率。** 直观感受一下：600 km 的格子意味着**整个英格兰只有一两个格点**；意味着**阿尔卑斯山、比利牛斯山、整个不列颠群岛的海陆分布**在模式里几乎不存在。

#### E2. 参数化（parameterisation）—— 本周绕不开的概念

讲义只出现了 "parameterizing small-scale processes like clouds" 和 Slide 25 的 "Rainfall parameterisation" 两处，但这个概念是理解模式不确定性的核心。

**是什么**：当一个物理过程的空间尺度**小于模式格距**时，模式无法直接解析（resolve）它。解决办法是写一个经验/半经验公式，用**格点尺度的变量**（温度、湿度、风切变等）去**估计**这个次网格过程对格点的净效应。这个过程叫参数化。

**典型的被参数化对象**：
- **云与对流（clouds and convection）**——单个积云直径 1–10 km，远小于早期格距
- **湍流与边界层（turbulence and boundary layer）**——米级到百米级
- **降水微物理（precipitation microphysics）**——云滴、雨滴尺度，微米到毫米
- **气溶胶–云相互作用**
- **重力波拖曳、地表通量**

**为什么它是不确定性的主要来源**：参数化公式**不是从第一性原理推出来的**，里面的系数要靠观测或高分辨率模拟去调（tuning）。不同模式组选择不同的参数化方案 → 同样的强迫下给出不同的响应 → **这就是模式间离散度（inter-model spread）的主要来源之一**。

讲师在讲分辨率时说得很直白：

> "Doing this for something like **temperature is relatively easier** compared to something like **simulating cloud processes**, where we know the **uncertainty on those sorts of calculations is much larger**."

**注意这个对比**：温度是一个**平滑的、大尺度的**场，格点平均值有意义；云是**高度不连续、强非线性**的，一个格子里「有云 30%」这种平均值物理意义很弱。**这就是为什么云是气候敏感度不确定性的头号来源。**

#### E3. UK 分辨率演进的具体数字（转写独有，讲义只有图）

Slide 19 那张图讲义只给了标题（"UK 'local' climate projections: summer rainfall"），具体的分辨率历史全靠转写：

> "this is what a global climate model of the UK would have looked like in **1998**. There was quick advances towards **50 kilometres of grids in the early 2000s**, but we're now in a place where we can almost start to think about simulating this on a **metre by metre** spatial resolution for different atmospheric simulation models."

**记住这条时间线：**

| 年代 | UK 区域的有效分辨率 | 能看到什么 |
|---|---|---|
| **1998** | 极粗（讲义 Slide 17 的 250–600 km 量级） | 英国只是几个格子，看不出任何区域差异 |
| **早期 2000s** | **50 km** | 能分出南北、东西的大致差别 |
| **今天** | 讲师说"几乎可以想到米级"（**⚠️ 见下方说明**） | 能分辨单个对流风暴、城市热岛 |

⚠️ **对「米级」这个数字要谨慎。** 讲师自己加了限定词 "almost start to think about" 和 "for different **atmospheric simulation models**"——他说的是**特定的高分辨率大气模拟工具**（📎 背景补充：例如大涡模拟 LES、或云解析模式 CRM），**不是**全球气候模式的常规分辨率。**全球 GCM 目前的业务分辨率仍在几十到 100 km 量级，区域降尺度模式在 1–12 km 量级。** 这一条已登记勘误提醒。

#### E4. 为什么分辨率重要 —— UK 农民的例子（转写独有，贯穿全课的核心比喻）

这是本周讲师用得最多、最值得记住的一个具体例子：

> "the **lack of resolution**, in this case over the UK, makes it very difficult to predict **small scale changes that might affect individuals**. An example of that might be a **UK farmer** who is trying to understand what the climate might look like into the future. **How many rainy days might he expect? What is the rainy day intensity?** These are the sorts of questions that might be really very useful to an individual trying to plan."

他后面又回来用了两次：

> "using that example of a UK farmer trying to predict what is going to happen into the future, **what crops should they plant** — not a great deal of information [from a coarse global map]. This is just a zoomed in version of this high warming scenario. **A farmer couldn't make good use of outputs like this**, so the resolution on which these models are run is very important."

> "using the farming analogy where we know **yields are heavily influenced by rainfall, rainfall severity and periods of drought**, we can start to see what UK climate projections for summer rainfall might look like into the future."

**这个例子的教学功能：它把「分辨率」从一个技术参数变成了一个决策问题。** 一个只告诉你「全球平均升温 3 °C」的模式，对具体的适应决策（种什么作物、修多大的排水管、堤坝加高多少）几乎无用。**Slide 36 的第 5、11 题都可以用这个例子作答。**

#### E5. 沟通同样重要（转写独有，讲师明确强调）

> "But also it's **not just what models and how models are operated, it's how those outputs are communicated** becomes very important as well. So something like this is **almost useless for someone trying to make a decision** based on upcoming change."

**这是讲义完全没有的一层观点**：模式的价值取决于输出能否被使用者理解和使用。一张全球彩色地图对科学家有意义，对农民没有意义。**答"模式的局限"时可以加这一条，是加分点。**

#### E6. 从粗到细，模式输出发生了什么变化（Slide 18 / 19 的读图）

讲师在讲 Slide 18（未来温度投影）时说：

> "As I said, there isn't **one single global climate model** which gives you the best answer. The IPCC brings together and aggregates around **35 to 40 global climate models** to get their **best estimate**, which you see on the left-hand side. And it can be split into models that predict **relatively higher warming** or indeed **very high warming** models. That's really important because **no model is best and there is no one model that stands out as the leading model**. So an **aggregate of effects** is captured through these different modeling scenarios."

⚠️ **这个数字在转写里出现了两次且不一致**：开头 ILO 部分讲师说 "There are **36** climate models that are recognised and used by the IPCC"，这里说 "around **35 to 40**"。已登记勘误——但两个说法量级一致，**答题写「IPCC 汇集了约 35–40 个（数十个）全球气候模式」是安全的**。

**"no model is best" 这句话是本周的一个核心态度**，它直接推出了两件事：
1. 为什么要用**多模式集合（multi-model ensemble）**；
2. 为什么需要 **RCP** 来保证输入一致（见 J 节）。

Slide 19 的降水图，讲师读得很细（讲义正文只有一句 "Summer rainfall is less frequent but more intense"）：

> "what you can see here is the **number of rainy days** on the top figure and the **intensity** of those rainy days in the bottom. And you can start to see **disparities across the UK**… So in the **south** you might expect the **frequency** to change by [an] enormous percent, **50 to 60 percent**. And that's particularly going to affect southern parts of the UK into the future. But in terms of the **intensity of rainfall** that might affect the **eastern** side of the UK more prominently."

**结论句（务必记住，讲义 Slide 19 原话）：**

> **"Summer rainfall is less frequent but more intense."**
> （夏季降水**频次下降但强度上升**。）

📎 背景补充：这个「更少但更强」的组合在物理上并不矛盾，反而是增温下的典型预期。**大气持水能力随温度按 Clausius–Clapeyron 关系增长（约 7% per K）**，所以一旦下雨，可降水量更多、强度更大；而与此同时，环流变化与更强的蒸发需求会拉长干期。**净效应就是：干的时候更干，下的时候更猛。** 这一段物理解释讲义与转写都没有给，是我的补充，但它能把「频次↓、强度↑」这个反直觉结论讲通。

**这个结论的实际含义**（对应上面农民的例子）：
- **总降水量可能变化不大**，但**分布形态完全变了**；
- 意味着**同时增加干旱风险和洪涝风险**；
- 对基础设施（排水系统按「多少年一遇」设计）和农业（作物需要的是稳定供水，不是几场暴雨）都是坏消息。

---

### F. HadCM3 与垂直分层

#### F1. 讲义内容（Slide 20）

> "The **Hadley Centre Third Coupled Model (HadCM3)** was developed by the **UK Met Office's Hadley Centre for Climate Prediction and Research**."
> "HadCM3 was a **pioneering** global climate model that integrated **atmosphere, ocean, sea ice, and land surface** components."
> "It played a significant role in climate research and was widely used in studies assessing the impacts of greenhouse gas emissions and anthropogenic activities on global climate."
> "HadCM3 contributed to the **IPCC assessments**, providing valuable insights into future climate scenarios and informing international climate policy discussions."

#### F2. 垂直层数（转写独有，讲义没写具体数字）

> "It's **not just the spatial resolution across the surface** of the Earth that's important. It's also the resolution that goes **both up into the atmosphere or down into the ocean**. The **HadCM3**, which is the **UK's Met Office Global Climate Model** that was first incorporated into IPCC reports, is an example of that. This model in particular has **19 levels in the atmosphere and 20 levels down into the ocean**. Again this highlights the **complexity** of running a model like this."

**记住：HadCM3 ＝ 大气 19 层 + 海洋 20 层。** 这是本周唯一一个具体的模式配置数字，**很适合作为「模式是三维的、垂直分辨率也重要」的举例**。

**注意 HadCM3 名字里每个词的含义**（考试可能让你解释）：
- **Had** = Hadley Centre（英国气象局哈德利中心）
- **C** = **Coupled**（耦合的——大气与海洋耦合，这是它相对前代的关键进步）
- **M** = Model
- **3** = 第三代

**所以 "HadCM3" 这个名字本身就在讲 D 节的故事**：它是「耦合时代」的代表作。

---

### G. 大气成分的箱模式（Box Model）

#### G1. Slide 21 的结构

Slide 21 是本周唯一一页**定量**的内容，标题 "GCM: Atmospheric Composition"。OCR 把图上的标签打散了，还原后是这样一个**单箱质量收支图**：

讲义给出的元素（OCR 原文）：

> "**Sources / Sinks / Chemical production / Chemical loss**"
> "**Atmospheric "box"; spatial distribution of X within box is not resolved**"
> "**box can be global atmosphere or some subdomain**"
> "**L / P / Outflow / Inflow / X / F_out / F_in / D / E / Deposition / Emission**"
> "**Let m [kg] be the mass of X in the box**"

**符号对照（还原后）：**

| 符号 | 英文 | 中文 | 属于 |
|---|---|---|---|
| **m** | mass of X in the box | 箱内物种 X 的质量 | 状态量 |
| **E** | Emission | 排放（直接排入） | **源 Source** |
| **P** | Chemical production | 化学生成 | **源 Source** |
| **F_in** | Inflow | 流入（从相邻箱输入） | **源 Source** |
| **D** | Deposition | 沉降（干/湿沉降） | **汇 Sink** |
| **L** | Chemical loss | 化学消耗 | **汇 Sink** |
| **F_out** | Outflow | 流出（输出到相邻箱） | **汇 Sink** |

**关键的边界条件（讲义明写，务必记住）：**

> **"spatial distribution of X within box is **not resolved**"**

**箱内是完全混合的（well-mixed），箱内的空间结构被完全丢弃。** 这就是「箱模式」这个名字的含义，也是它的根本近似。**这正是 C 节网格化的微观图景**——GCM 的每一个格点，对每一种化学物种来说，就是这样一个箱子。

第二个边界条件：

> **"box can be global atmosphere or some subdomain"**

箱子的尺度是可选的：可以把**整个全球大气**当一个箱子（做全球寿命估算），也可以是一个 GCM 格点（做三维化学传输）。

#### G2. 讲师的口头展开（转写，比讲义详细得多）

> "In terms of what these **grid boxes** look like in terms of atmospheric composition, we can start to look at this **box modeling approach** for different molecules or different constituents of the atmosphere. An example of this is **molecule X**. This could either be a **greenhouse gas** or be an **aerosol particle** of different kinds. You can have **sources and sinks** of this molecule X and that will dictate the **concentration of X in that grid** and **how then it might move between other grids**."

**逐项还原讲师对每个通量的解释：**

**（i）排放 E（Emission）**
> "In terms of the sources of X you can either have **direct emission** and those emissions can be **widespread**. You should now have a good understanding of the emission sources of **CO₂, methane and N₂O** which are the key greenhouse gases."

**（ii）沉降 D（Deposition）**
> "You can also have **deposition to the surface** that can either be through **wet deposition** i.e. incorporated into precipitation, or **gravitational settling**."

**⚠️ 这里讲师给了沉降的两条路径，很好的考点：**
- **湿沉降（wet deposition）**：被云滴/雨滴捕获，随降水落地。
- **干沉降（dry deposition）/ 重力沉降（gravitational settling）**：颗粒物在重力下沉降，或气体分子与地表接触被吸收。

**（iii）化学生成 P（Chemical production）—— 讲师用臭氧举例**
> "**Not all atmospheric constituents are directly emitted** into the atmosphere. An example of that… is **ozone**. **Ozone in the troposphere is not directly emitted** but it is **made through a series of photochemical reactions** that we touch on and cover in a huge amount of detail in my **atmospheric composition lecture series in year three**."

**这是本周最容易被问到的一个概念区分：**
- **一次污染物 / 直接排放物种**：有 E，如 CO₂、CH₄、N₂O、一次气溶胶、NOₓ、SO₂。
- **二次生成物种**：E ≈ 0，全靠 P，如 **对流层臭氧（tropospheric ozone）**、二次有机气溶胶、硫酸盐气溶胶。

**对流层臭氧是二次生成的**——它由 NOₓ 与挥发性有机物（VOCs）在阳光下经光化学反应生成。**这一点在气候语境下重要，因为对流层臭氧是一种温室气体**（Week 3/4 有涉及），但你**不能**用「减少臭氧排放」来减缓它，只能控制它的前体物。

**（iv）化学损耗 L（Chemical loss）—— 讲师用甲烷举例**
> "You can also have **chemical losses** where different chemicals interact with one another to lead to the loss of molecule X. An example of that in the context of this course might be something like **methane** which readily reacts with **different oxygens** in the atmosphere and acts as an important **removal mechanism of methane**."

📎 背景补充：讲师说的 "different oxygens" 指的是**羟基自由基（hydroxyl radical, OH·）**——大气的「清洁剂（detergent of the atmosphere）」。甲烷的主要去除路径是 CH₄ + OH· → CH₃· + H₂O，这条路径决定了甲烷约十年量级的大气寿命。**转写里 "different oxygens" 是一个含糊的口语表达，具体的化学讲义没给。**

**（v）输入输出 F_in / F_out**
> "You can also have **interaction with other boxes that lead to increases in concentration**, or you can have **outflow which leads to decreases** in concentration."

#### G3. 怎么用这个箱模式

讲师给出了计算规则：

> "if you want to then calculate the **concentration of X in a particular box** we can start to look at the **sum of the sources minus the sum of the sinks**. And as I say, **not all molecules will have chemical production or direct emission or direct chemical losses or deposition. But in many cases it will be the sum of all of them put together.**"

**边界条件（讲师明说的）：不是每个物种都有全部六个通量。**
- CO₂：有 E、F_in、F_out，几乎没有 L（在对流层化学上惰性）、D 很小（但有海洋与陆地碳汇，属于地表交换）。
- 对流层 O₃：E ≈ 0，P 大、L 大、D 显著。
- 硫酸盐气溶胶：E 小（一次）、P 大（由 SO₂ 氧化生成）、D 大（湿沉降为主）。

**这个模式在历史上的地位（讲师）：**
> "these sorts of models have been used **extensively by the IPCC since the 1990s** when the first real global climate model came into effect."

具体的方程写法见第三节。

---

### H. IPCC 评估报告的历史与模式演进

#### H1. 讲义 Slide 22 的四份报告

| 报告 | 年份 | 讲义要点 |
|---|---|---|
| **FAR**（First Assessment Report） | **1990** | 第一次对气候变化的科学、影响、潜在减缓策略作全面评估；在**提升全球对气候变化议题的意识**上起了关键作用 |
| **SAR**（Second Assessment Report） | **1995** | 提供了更新、更详细的气候变化科学理解；highlighted **脆弱区域**可能受到的影响；**为 1997 年《京都议定书》（Kyoto Protocol）的通过提供了各国政府可援引的重要材料** |
| **TAR**（Third Assessment Report） | **2001** | 评估了观测到的气候变化、未来气候情景的预估、以及气候变化对**农业、水资源、人类健康**等各部门的潜在影响；对国际气候谈判与政策讨论贡献显著 |
| **AR4**（Fourth Assessment Report） | **2007** | 更新了科学、影响、适应与减缓的评估；**纳入了气候模拟、观测数据、以及对气候反馈机制理解的进展**；**为「后京都」协议奠定基础，聚焦于把增温限制在 2 °C** |

⚠️ **讲义 Slide 22 只讲到 AR4（2007）为止，没有提 AR5（2013–14）和 AR6（2021–23）。** 这是一个**内容缺口**，而且有点尴尬——因为**RCP 情景（Slide 24 的主题）恰恰是 AR5 引入的**，而 unit spec 明确说本课主教材是 **AR6 综合报告**。已登记勘误。

📎 背景补充（清楚标注为补充，考试请以讲义为准）：完整的 IPCC 评估报告序列为 FAR (1990) → SAR (1995) → TAR (2001) → AR4 (2007) → **AR5 (2013–14)** → **AR6 (2021–23)**。RCP 出自 AR5，SSP 出自 AR6。与各报告配套的模式比较计划分别是 CMIP3（AR4）、CMIP5（AR5）、CMIP6（AR6）。**这些名称讲义都没给，但如果你去读 AR6 原文会遇到。**

#### H2. 报告间的模式演进（转写独有，对应讲义里没有文字的两页图）

讲师看着两张 IPCC 经典配图讲了两条演进线：

**（i）空间分辨率的提升：**
> "you don't need to know the details of this slide but what you do need to appreciate is **how the spatial resolution of these models has increased over time**. And you can start to see why that's important **over Europe** because there's many different **land masses** which was **not captured by the FAR**, the first assessment report. But **AR4 was starting to capture in a lot more detail** and therefore the **accuracy of these models was dramatically increased**."

**（ii）过程数量的增加：**
> "It's not just the resolution of the models that have increased over time. So you have the **number of processes** that have been incorporated into them… the first real global climate model was the first assessment report. But you can see that that really just captured **some key emissions, perhaps some interactions with clouds**. As we move to the most recent reports we now start to have different **atmospheric chemistry processes**, a much **diverser range of emissions** and a much more accurate representation of all the processes."

**⚠️ 这两条线是本周叙事的总纲，务必能各举一例：**

| 演进维度 | FAR (1990) | AR4 (2007) 及以后 |
|---|---|---|
| **空间分辨率** | 欧洲的陆块形状都分不出来 | 能分辨半岛、山脉、海陆边界 |
| **过程数量** | 关键排放 + 一点云相互作用 | + 大气化学、气溶胶、生物圈、冰冻圈、碳循环 |

讲义 Slide 23 也用一句话说了同一件事：

> "The **complexity** of climate models has increased over the last few decades. The **additional physics** incorporated in the models are shown pictorially by the different features of the modelled world."

---

### I. 模式性能的尺度依赖（Slide 23）

这是全周**最可能出简答题**的一张表，讲义原文：

> "**Modern Coupled GCMs**
> ✓ Perform **well at continental scales**
> ✓ Perform **well at multiannual → climatological scales (30 year)**
> ✗ Perform **less well at short time scales**
> ✗ Perform **less well at regional scales**"

讲师复述并强调：

> "these global climate models now **perform very well at continental scales** and perform very well at **multi-annual climatological time scales**. These are **not yet perfect** and they perform **much less well at short time scales** and **much less well over smaller areas**."

**整理成一个二维表（强烈建议背下来）：**

| | **长时间尺度**（多年–30 年） | **短时间尺度**（日–年） |
|---|---|---|
| **大空间尺度**（全球–大陆） | ✅ **最擅长** | ⚠️ 一般（年际变率受 ENSO 等混沌成分支配） |
| **小空间尺度**（区域–局地） | ⚠️ 一般（需降尺度） | ❌ **最不擅长** |

**为什么是这个模式（Slide 36 第 11 题的标准答案，必须能讲出物理理由）：**

1. **时间上**：气候是统计量。对长时间平均，混沌的天气涨落被平均掉，剩下的是**由能量收支决定的、可预测的**信号。短时间尺度上，系统的**初值敏感性（混沌）**支配一切——这是天气预报只能做 1–2 周的原因。
2. **空间上**：全球平均由**全球能量平衡**决定，是一个强约束；区域气候则取决于**环流形态的位置**（急流在哪、风暴路径在哪），而环流位置的模拟误差远大于全球能量收支的误差。
3. **技术上**：区域尺度接近或小于模式格距，落进了参数化的势力范围（E2 节）。

---

### J. 代表性浓度路径（RCPs）

#### J1. 讲义 Slide 24 的定义

> "Anthropogenic GHG emissions are mainly driven by **population size, economic activity, lifestyle, energy use, land use patterns, technology and climate policy**."
> "The **Representative Concentration Pathways (RCPs)**, which are used for making projections based on these factors, describe **four different 21st century pathways** of **GHG emissions and atmospheric concentrations, air pollutant emissions and land use**."
> "The RCPs include a **stringent mitigation scenario (RCP2.6)**, **two intermediate scenarios (RCP4.5 and RCP6.0)** and **one scenario with very high GHG emissions (RCP8.5)**. Scenarios **without additional efforts** to constrain emissions ('**baseline scenarios**') lead to pathways ranging **between RCP6.0 and RCP8.5**."
> "**RCP2.6 is representative of a scenario that aims to keep global warming likely below 2 °C above pre-industrial temperatures.** The RCPs are consistent with the wide range of scenarios in the literature as assessed by WGIII."

**四条路径速查表：**

| 路径 | 性质 | 讲义描述 |
|---|---|---|
| **RCP2.6** | **严格减缓（stringent mitigation）** | 目标是把全球增温**很可能（likely）控制在 2 °C 以下**（相对工业化前） |
| **RCP4.5** | 中间情景（intermediate） | — |
| **RCP6.0** | 中间情景（intermediate） | — |
| **RCP8.5** | **极高排放（very high GHG emissions）** | — |
| *baseline* | 无额外减缓努力 | 落在 **RCP6.0 与 RCP8.5 之间** |

**⚠️ 记住这个「baseline 落点」——它是一个很好的考点**：所谓「什么都不额外做」的世界，对应的是 RCP6.0–8.5 的区间。这意味着 **RCP8.5 是一个高端而非中心的假设**，而 RCP2.6 需要**主动、剧烈的政策干预**才能实现。

讲师对 RCP2.6 的口头补充（转写独有）：

> "SSP 1 to 2.6 are **severe mitigations**… very quickly, very abruptly, and probably with the use of **negative emission technologies** as well."

**⚠️ 「负排放技术（negative emission technologies）」这个词讲义完全没有，只在转写里出现，但它是理解 RCP2.6 的关键**：2.6 W m⁻² 的路径不只要求排放降到零，还要求**在本世纪后半段实现净负排放**（把已排放的 CO₂ 从大气中移除）。

📎 背景补充：负排放技术包括 BECCS（生物质能 + 碳捕集封存）、DACCS（直接空气捕集 + 封存）、造林与再造林、增强岩石风化等。这些名称本课本周材料没有列出，Week 10（减缓）可能会讲。

#### J2. RCP 真正的作用：保证模式间的可比性（转写独有，⭐ 本周最重要的一段口头内容）

讲义 Slide 24 只说 RCP 是「用来做预估的路径」，**没有说清楚它为什么必须存在**。讲师把这个空白补上了，而且用了一个绝妙的比喻：

> "Like I say **there is no one perfect global climate model**. So the IPCC brings together many climate models together. But what this means is you're comparing a global climate model that might be **run in the US** to a global climate model that is **run in the UK**. **How do you know that the inputs and the emissions are the same between the models? If you didn't know that, you'd be comparing apples with oranges.** To ensure that you can have good comparability between these global climate models it's very important to know that the **inputs are the same**. And that is done through these **universally accepted representative concentration pathways**."

他又强调了一遍：

> "this allows you to **compare and intercompare different climate models run at different locations by different people who don't know each other**. Without that, as I said, you'd be **comparing apples with oranges** and it wouldn't be particularly useful. With these representative concentration pathways you are ensuring that the **inputs are the same**. Therefore you are trying to **predict the effects of the same scenarios**."

**把这个逻辑写成一条链（这是 Slide 36 第 6 题的最佳答案）：**

```
没有单一最优模式 → 必须用多模式集合
        ↓
但不同模式由不同国家、不同团队独立开发
        ↓
如果各自假设自己的排放情景 → 结果差异分不清是"模式不同"还是"输入不同"
        ↓
RCP 提供统一的、普遍接受的输入（浓度/强迫轨迹）
        ↓
模式间的差异就纯粹是"模式响应的差异" → 可以被解释为不确定性
        ↓
IPCC 才能把 35–40 个模式的结果聚合成有意义的最佳估计与不确定性范围
```

**⚠️ 这条链是本周的思想内核。** 很多学生只记住「RCP 是四种排放情景」，但真正的考点是：**RCP 是一个「实验设计的控制变量」机制**，它的功能是**分离「情景不确定性」与「模式不确定性」**。

**RCP 的驱动因子（讲义列的七项，可能被要求列举）**：人口规模（population size）、经济活动（economic activity）、生活方式（lifestyle）、能源使用（energy use）、土地利用格局（land use patterns）、技术（technology）、气候政策（climate policy）。

讲师复述时把 "lifestyle" 说成了 "behavioural activity"，并额外强调了跨学科属性（转写独有）：

> "Very often we're thinking about that in terms of **behavioural change** as well. So it's **not just environmental change**. Also things like **social sciences, economics**. These are sorts of things that might be considered to impact the change that we will see."

**这一点很重要：RCP 的上游是社会科学，不是自然科学。** 一个物理气候模式不能自己预测人口和 GDP，所以情景必须由外部给定。

---

### K. 误差、检验与归因

#### K1. 误差从哪来（Slide 25）

讲义 Slide 25 列了六条：

> "**Grid size / Atmospheric levels / Regional response / Natural variability / Cloud representation / Rainfall parameterisation**"

讲师对每一条都作了口头解释（转写）：

| 误差来源 | 中文 | 讲师的解释 |
|---|---|---|
| **Grid size** | 网格尺寸 | "the smaller the grid the more accurate it is. But we are **not in a place where we are running street level global climate models routinely**." |
| **Atmospheric levels** | 大气层数 | "there are **lots of information at the surface** of the earth. But **much less as we move up into the atmosphere and down into the ocean**. So different atmospheric levels might be **less well simulated than the surface**." |
| **Regional response** | 区域响应 | （见 I 节：区域尺度是模式的弱项） |
| **Natural variability** | 自然变率 | "Things like natural climate variability are often **hard to predict**. Things like **volcanoes**." |
| **Cloud representation** | 云的表征 | "we know there's **big uncertainties** on those sorts of calculations." |
| **Rainfall parameterisation** | 降水参数化 | "predicting **rainfall as a result of those aerosol–cloud interactions** is also **more challenging**." |

**⚠️ 注意 "Atmospheric levels" 这一条的因果**：垂直层的模拟质量差，**根源是观测稀疏**（Week 5 的内容）——地表有成千上万个站，高空和深海几乎没有。**模式的垂直结构缺乏足够的观测去约束和验证。** 这条把 Week 5 和本周连了起来，是很好的综合题材料。

**⚠️ 注意 "Natural variability" 与 "volcanoes"**：火山爆发是**本质上不可预测的外强迫**——你无法预知 2047 年会不会有一次皮纳图博级别的喷发。所以模式在做未来投影时**通常不包含未来的火山活动**（或只包含一个背景平均值）。这不是模式的缺陷，而是问题本身的不可预测性。

#### K2. Hindcasting（回报 / 后报）—— 本周的核心方法论

讲义 Slide 25 的定义：

> "Climate models are evaluated for accuracy by '**hindcasting**,' or **replicating the climate of the past 100 years**."
> "Because models have been **run since the 1990s**, scientists can now see **how accurate earlier models were at projecting future changes**."

讲师的定义（转写）：

> "how do we know whether these models are working correctly? We are working on this principle of **hindcasting**, which is the principle of **predicting what has happened in the past**. **If the observations match very well with those predictions, you've got a good idea that we might be able to extrapolate out to later years into the future.**"

**是什么**：把模式设定到过去某个时刻的状态，让它「预报」已经发生过的历史，然后拿模式输出与真实观测比对。

**为什么这样做是合理的**：这是**唯一可行的验证方式**。你不能等到 2100 年再来检验一个 2026 年的模式。历史是我们唯一拥有的、既有「强迫输入」又有「真实答案」的数据集。

**⚠️ 讲师在 ILO 那一段就提醒过这是个反直觉的概念：**

> "explain why they're important to study **both past change, which is a weird concept for predictive models**, but why they are so important in predicting what might happen into the future."

**"用预测模型去预测过去" 听上去很怪，但这正是它的检验逻辑。**

**边界条件（很重要，容易被忽略）**：hindcast 表现好 ≠ 未来预测一定准。因为：
- 模式的参数可能是**针对历史观测调过的（tuned）**，历史吻合有一部分是「调出来的」；
- 未来的气候可能进入**历史上没有出现过的状态**（no-analogue state），历史上验证过的参数化未必仍然成立。

📎 背景补充：为了缓解第一个问题，严格的评估会用**「不参与调参的独立指标」**去检验，或者用**「out-of-sample」时段**（例如用 1850–1990 调参、用 1990–2020 检验）。**这个方法论细节讲义与转写都没提，是我的补充。** 不过讲义 Slide 25 说的「模式自 1990 年代就在跑，我们现在可以回头看它们当年的预测准不准」，本质上就是一个天然的 out-of-sample 检验。

#### K3. 一个真实的 hindcast 案例（Slide 26 + 转写）

讲义 Slide 26 标题：**"How did we do in 2004?"**

> "**Observed changes in temperature and precipitation have generally been consistent with the changes projected by earlier models.**"
> "The **accurate projections of future climate and hindcasting of past climate** makes us **confident that models can reliably project changes in the climate**."

讲师的细节（转写独有）：

> "An example of that was a piece of work that was **completed in early 2020**, which looked at **global climate models that were run in 2004** and how well they predicted what has happened **from 2004 to today**. So to do that they used this **hindcast approach**… They compared that with the observations and said **look we're doing a pretty good job**. What might happen through to 2022. And you can see the period here where we **moved from hindcast to forecast**. And we can see that the **ensemble mean of the global climate models captures rather nicely the multi-year variation and trends over the last 20 years**."

**然后是本周最重要的一句「读图指导」：**

> "The other thing that you should be able to pull away from this plot is that the **mean doesn't capture the variability on a yearly timescale very well. But it does capture the overall trends very well over the 20 years.** This just backs up the point of the previous slide that we predict and can use these models on a **climatological timescale**, but **less well on predicting what is happening from year to year**."

**⚠️ 这句话把 I 节的「尺度依赖」从抽象结论变成了图上可见的事实。** 集合平均（ensemble mean）之所以抓不住年际起伏，是因为：**每个集合成员的内部变率（ENSO 等）相位是随机的，平均之后互相抵消了。** 集合平均代表的是**强迫响应（forced response）**，不是**任一次实现（realisation）**。

📎 背景补充：这就是为什么正确的做法是拿**观测**与**集合离散度带（ensemble spread）**比，而不是与集合平均比。如果观测年际起伏落在集合成员的散布范围内，模式就是合格的。**这个"比什么"的技术细节讲义没有明说，是我的补充**，但它正是讲师那句话的严格版本。

#### K4. 归因协议：模式怎么证明「是我们干的」（Slide 27）

**这是本周最有操作性的一页，也几乎肯定会考（Slide 36 第 3、4 题）。** 讲义原文：

> "How would such a model simulation be carried out? The following **protocol** is typical.
> **1.** A GCM model is **run for many decades with no external forcing**.
> **2.** The **statistics of the run** (mean climate, annual cycles and variability on a range of time scales) are then **compared with observation** to assess performance.
> **3.** The model is then **re-run with changes in forcing** (such as greenhouse radiative forcing).
> **4.** The **difference in the two climates** provides an **estimate of the consequent climate change arising from that forcing factor**."

**逐步解读（这四步必须能默写）：**

| 步骤 | 做什么 | 目的 |
|---|---|---|
| **1** | 跑一个**无外强迫（no external forcing）**的对照实验，持续数十年 | 生成模式自己的**内部自然变率基线**——这就是「如果没有任何外部扰动，气候会自己怎么晃」 |
| **2** | 把这个对照实验的**统计特征**（平均气候、年循环、各时间尺度上的变率）与**观测**比对 | **先验证模式本身合格**——如果模式连自然变率的幅度都模拟不对，第 4 步的差值就没有意义 |
| **3** | 加上强迫（如温室气体辐射强迫），**重跑**一遍 | 生成扰动实验 |
| **4** | **两次气候的差值** | 就是**该强迫因子造成的气候变化**的估计 |

**⚠️ 第 2 步最容易被漏掉，但它是整个协议的合法性前提。** 很多人答归因时直接说「跑两次相减」，但如果不先验证对照实验的变率是对的，你就无法判断第 4 步的差值是「真实的强迫响应」还是「噪声」。

**这正是 A1 节说的「反事实实验」**：现实世界只有「有人类的地球」，模式给了我们「没有人类的地球」。

讲师在讲这一页（以及 Slide 22 那张经典的「with/without anthropogenic forcing」双色带图）时说：

> "how might we think about separating out **natural variability** from **anthropogenic climate variability**? We can start to think about **running models with and without climate forcing**. And this again gives us some confidence that **it is in fact us** that is driving the climate change we're seeing, not natural variability. And again, that's **only because global climate models predict very nicely what is happening up to today but only when anthropogenic forcings are included**."

**⭐ 最后一句是归因论证的完整形式，务必能复述：**

> **只跑自然强迫（太阳 + 火山）→ 模式给出的 20 世纪后半叶温度是平的甚至微降，与观测不符。**
> **加上人为强迫 → 模式与观测吻合。**
> **⇒ 观测到的增温无法用自然因素解释，必须包含人为因素。**

这是一个**排除法 + 充分性**的双重论证：自然强迫**不充分**，加上人为强迫**才充分**。

#### K5. 仍待解决的问题（Slide 28）

讲义标题 "Factors to consider…"：

> "**Short term changes are not reproduced** but the results look encouraging."
> "However, **problems remain** –
> - Is the **temperature record reliable**?
> - **Cause and effect not finally established**
> - **Large uncertainties in radiative forcing and the effect of aerosols**
> - **Discrepancies remain between predicted and observed regional pattern of change**
> - **Not all factors are represented in GCMs** – e.g. **nitrogen cycle**
> - As **complexity is increased so is computing power**"

讲师逐条展开（转写）：

> "There's some remaining factors to consider, which is **how representative things like the temperature record are across the surface of the earth**. There are still **large uncertainties in aerosol effects both from the direct and indirect effects** of aerosols. And there are still relatively large **discrepancies in regional predictions versus observed regional patterns of change**. And **not all biogeochemical cycles are completely incorporated** into global climate models. Things like the **nitrogen cycle** might have effects on [atmospheric] chemistry but also the biosphere. Ultimately a large part of this is the **reliance on very heavy computer power** to come up with these parameterisations. **Simulation can take weeks on supercomputers.** So you can start to think how this might **limit the number of simulations that any one person could run**."

**⚠️ 几个必须抓住的点：**

1. **"Simulation can take weeks on supercomputers"（转写独有的量化）**——这个数字把 C2 节的 trade-off 变得具体：如果一次模拟要几周，你一年最多跑十几次，**根本没法做大集合或充分的敏感性测试**。
2. **氮循环（nitrogen cycle）是被点名的缺失项**。📎 背景补充：氮循环之所以重要，是因为它同时影响 (a) N₂O 这一强温室气体的收支，(b) 陆地植被的养分限制——如果不考虑氮限制，模式会**高估**未来植被的 CO₂ 施肥效应（即高估陆地碳汇）。**这个机制讲义与转写都没解释，是我的补充。**
3. **"Cause and effect not finally established"** 这条讲义写法比较绝对，讲师没有口头复述这一条。⚠️ 需要谨慎理解：这不是说因果关系没确立（IPCC AR6 的措辞是 "unequivocal"），而是说**某些具体的因果链条（尤其是区域尺度、极端事件）仍未完全确定**。这一条已登记勘误提示。

---

### L. GCM 的未来：AI 与机器学习

这是讲师**课前几天临时加的新内容**（见第一节），也是 Slide 36 第 13 题的直接来源。

#### L1. 现状的三个痛点（Slide 29）

> "Current GCMs rely heavily on **physical equations and parameterisations**."
> "**Struggle with small-scale processes and nonlinear climate behavior.**"
> "**Require very high computational resources.**"

讲师复述：

> "global climate models are completely built on **physical equations and different parameterisations and different inputs**. They **struggle more with smaller scale behaviour** than large scale concepts and they **require very heavy computational resources**."

#### L2. AI / ML 作为可能的解法（Slide 29–30）

讲义 Slide 29：
> "**Artificial Intelligence (AI) and Machine Learning (ML) are possible solutions**
> - Used to **analyse large and complex climate datasets**.
> - **Improves prediction accuracy** in weather and climate systems.
> - Helps **accelerate climate research and simulations**."

讲义 Slide 30：
> "**Advantages**: handles **nonlinear relationships** and **large datasets**. **Faster simulations** and **improved extreme event prediction**."
> "**Challenges**: **model interpretability** and **data bias**. Ensuring **physical consistency with climate laws**."

#### L3. 讲师的架构对比（转写独有，讲义没有这张「两条流水线」的文字说明）

> "What might this look like? So this is a **current setup** where you have a range of **inputs**. You run through your **differential equations, hundreds of thousands of lines of code** to come up with different **outputs** and different **impacts**. These are all based on **physical constants and physical parameterisations and different differential equations which ensures that these models are based in science**. But they are **computationally expensive, very hard to run** and lots of effort goes into them."

> "An **alternative** is that you input the same — you give the AI and machine learning models the **same inputs**. It runs through an **unregulated machine learning or AI model** and it comes up with the **same outputs**. The advantage of that is that **nonlinear relationships are much more easily picked up** with these sorts of models and ultimately it leads to **much faster simulations and potentially improved extreme weather prediction**."

**两条流水线的对比（务必能画出来）：**

```
【传统 GCM】
输入（排放情景、边界条件）
      ↓
物理常数 + 参数化 + 微分方程（数十万行代码）
      ↓
输出（温度、降水…）→ 影响
✅ 物理自洽、可解释    ❌ 极慢、极贵

【AI / ML 模式】
同样的输入
      ↓
机器学习模型（从数据中学到的映射）
      ↓
同样的输出
✅ 极快、擅长非线性、擅长极端事件   ❌ 不保证物理自洽、难解释、依赖训练数据
```

#### L4. 核心challenge：物理一致性与可解释性

讲师的原话：

> "The challenge here is **[interpretability]** of these models given that they are **largely unregulated and not underpinned by that physical science parameterisations**. Which means that there is a **possibility of these models not complying with physical laws** in unregulated operations."

（转写的 "interoperability" 与讲义 Slide 30 的 "model interpretability" 对不上，应以讲义为准，已登记勘误。）

**⚠️ 这是本周最深刻的一个概念对立，务必想清楚：**

| | 物理模式 | AI 模式 |
|---|---|---|
| **知识从哪来** | 从**第一性原理**（守恒律、辐射传输）推出 | 从**历史数据**中学到 |
| **能否外推到没见过的状态** | **可以**（物理定律在新状态下仍成立） | **可疑**（训练集里没有的状态，学到的映射可能失效） |
| **是否保证守恒** | 是（数值格式设计保证质量/能量守恒） | **不保证** |
| **可解释性** | 每一步都能追溯到方程 | 黑箱 |

**这就是答案 deck Q9 的核心论点**：气候投影的本质是**外推到一个人类从未观测过的气候状态**。而 AI 最不擅长的恰恰是外推。因此——

#### L5. 结论：混合建模（hybrid modelling）

答案 deck Q9 给出了明确结论：

> "The most likely future approach is **hybrid modelling**, where machine learning techniques **complement** physics-based models to improve accuracy, efficiency, and representation of complex processes."

**混合的具体形式**（答案 deck 提到的）：用 ML **改进参数化方案**——保留物理模式的动力学骨架（保证守恒与可解释），但把最难的次网格过程（云、湍流、对流）换成从高分辨率模拟中学到的 ML 方案。**这样既保住了物理自洽，又拿到了 ML 的速度与非线性表达能力。**

讲师最后加了一句实况（转写独有）：

> "But nevertheless this is an **exciting opportunity** and is indeed **being used by our department quite regularly now**."

**曼大 EES 已经在常规使用 AI/ML 方法做气候相关研究了。**

---

### M. 总结与前瞻（Slide 31、33、34、35）

#### M1. GCM 能提供什么（Slide 31）

> "Climate models offer **predictions about future climate conditions on a global scale**, informing us about changes driven by increased greenhouse gas emissions."
> "They provide valuable insights into how human activities could impact **global temperatures, humidity, and precipitation patterns**."
> "Climate models project **varying degrees of temperature rise across different regions**, alongside shifts in **precipitation patterns and snowfall events**."
> "These models are instrumental in understanding potential impacts on **natural resources, ecosystems, agriculture, water resources, and coastal areas** globally."
> "They serve as **tools for policymakers, scientists, and stakeholders** to plan for the complex challenges posed by climate change."

#### M2. 讲义 Slide 35 的六条 Lecture Summary（最适合考前速览）

1. **GCM 通过表征大气、海洋、陆地、海冰之间的相互作用来模拟地球气候**，以理解长期气候行为。
2. **地球被划分为三维网格**，温度、气压、风、水汽等变量在格点上被计算并在格点间交换。**更高分辨率提高精度但需要计算能力。**
3. **现代模式是耦合的地球系统模式**，连接大气、海洋、冰冻圈、生物圈与大气化学，以捕捉重要的气候反馈。
4. **模式通过 hindcasting 检验**——把对过去气候的模拟与观测比对以评估可靠性。
5. **RCPs 描述可能的未来温室气体排放情景**，用于预估增温以及降水与极端事件的变化。
6. **未来的气候模式预期将使用更高分辨率、更好的观测数据，以及 AI 与机器学习**等方法，以更好表征复杂过程并降低预估的不确定性。

#### M3. 前瞻：影响与 1.5 °C（Slide 33、34）

这两页讲义明确标注了 **"WEEK 8"** 和 **"WEEK 9"**，是给后续周次的引子，本周只是带过。

**Slide 33 — 自然灾害的增加（标注 WEEK 8）：**

> "Global warming has been linked to an increase in the **frequency, intensity, and severity** of various types of natural disasters."

| 灾害类型 | 讲义给的机制 |
|---|---|
| **热浪（Heatwaves）** | 升温直接导致更频繁、更强的热浪；健康影响严重，**脆弱人群受害尤重** |
| **极端天气（Extreme Weather Events）** | **更暖的海温提供更多能量**给飓风/台风/气旋 → 风速更大、降雨更强 |
| **洪涝（Flooding）** | 冰川与冰盖融化加速 → 海平面上升；叠加**降水强度增加** → 更频繁更严重的洪水 |
| **干旱（Droughts）** | 降水格局改变 + 升温导致蒸发加剧 → 更频繁、更持久的干旱；影响农业、水资源、生态系统与生物多样性 |
| **野火（Wildfires）** | 更暖 + 降水格局改变 → 植被更干、火险更高 → 更大更频繁的野火 |

**Slide 34 — 什么能把增温限制在 1.5 °C（标注 WEEK 9）：**

> "To strengthen the global response, **almost all countries would need to significantly raise their level of ambition**."
> "**Solar, wind, and electricity storage** technologies **more feasible**."
> "**Nuclear energy and carbon capture** technology improvements **lacking**."
> "**Electrification, hydrogen, bio-based feedstocks** crucial for emissions reduction."
> "**Land use transitions** necessary for limiting warming to 1.5 °C."
> "**Efficiency in food production** can reduce emissions and enhance food security."
> "**Dietary shifts and reduced food waste** can lower emissions and increase adaptation."
> "**Participatory and integrated** mitigation and adaptation approaches enable rapid transitions."

⚠️ **注意 Slide 34 标注的是 "WEEK 9"，但按 Slide 2 的课程地图，Week 9 是「Effects of Climate Change: Case Studies」，减缓是 Week 10。** 不过转写里讲师说 Week 9 会请 Jessica 讲地球工程（目标正是限制在 1.5 °C），所以这个标注与他的最新安排是对得上的。已登记勘误提示。

#### M4. 讲师的收尾总结（转写）

> "in summary we know now **what these global climate models can provide**. We know **how they are built**, we know **their impact** and we know now **how they might change into the future**. And we can use these to **predict what might now happen into the future based on different representative concentration pathways**. These representative concentration pathways will not only elicit these **environmental changes** but we might now see — or we **almost certainly will see** — **impacts** of these changes increasing into the future. These are things like **increases in natural disasters** which we will talk about more in next week. And we can then start to think about what **mitigations** we might put in place to reduce **both the change and ultimately the impacts**."

**⚠️ 注意这个「三层递进」，它是全课后半段的结构：**

```
情景（RCP）→ 环境变化（温度、降水）→ 影响（灾害、生态、社会）→ 响应（适应 Week 8 / 减缓 Week 10）
```

---

## 三、公式与图表

**先说明一件事**：本周是全课**公式最少**的一周。讲义里**唯一一个真正的定量框架**是 Slide 21 的箱模式质量收支。其余内容是概念性与图示性的。所以本节的重心放在**图表复述**上，公式部分把 Slide 21 讲透，并明确区分哪些是讲义给的、哪些是我补的。

---

### 3.1 公式：箱模式的质量收支（Slide 21）

#### 3.1.1 讲义给出的是什么

讲义 Slide 21 **只给了图和符号，没有给出方程式本身**。图上的元素是：

- 一个方框，标注 **"Atmospheric 'box'; spatial distribution of X within box is not resolved"**、**"box can be global atmosphere or some subdomain"**
- 箱内一个 **X**，以及 **"Let m [kg] be the mass of X in the box"**
- 六个箭头：**E**（Emission，进）、**P**（Chemical production，进）、**F_in**（Inflow，进）、**D**（Deposition，出）、**L**（Chemical loss，出）、**F_out**（Outflow，出）
- 两个分组标签：**Sources** 与 **Sinks**

讲师给出的计算规则（转写，是口头的，不是公式）：

> "if you want to then calculate the concentration of X in a particular box we can start to look at the **sum of the sources minus the sum of the sinks**."

#### 3.1.2 把它写成方程

📎 **背景补充：以下这个微分方程形式讲义与转写都没有写出，是我按讲师口述的"源之和减汇之和"规则整理的标准写法。** 符号沿用讲义 Slide 21 的定义，没有引入新符号。

$$\frac{dm}{dt} = \underbrace{E + P + F_{in}}_{\text{Sources 源}} - \underbrace{(L + D + F_{out})}_{\text{Sinks 汇}}$$

**符号、含义与单位：**

| 符号 | 含义 | 单位 | 说明 |
|---|---|---|---|
| **m** | 箱内物种 X 的质量 | **kg**（讲义明写 "m [kg]"） | 状态变量 |
| **t** | 时间 | s（或 yr，视应用） | — |
| **dm/dt** | 箱内质量的变化率 | **kg s⁻¹** | 正 = 累积，负 = 消耗 |
| **E** | Emission，直接排放通量 | kg s⁻¹ | 源；对二次物种 ≈ 0 |
| **P** | Chemical production，化学生成通量 | kg s⁻¹ | 源；对惰性一次物种 ≈ 0 |
| **F_in** | Inflow，从相邻箱输入的通量 | kg s⁻¹ | 源；若箱 = 全球大气则 ≈ 0 |
| **L** | Chemical loss，化学消耗通量 | kg s⁻¹ | 汇 |
| **D** | Deposition，沉降通量（干 + 湿） | kg s⁻¹ | 汇 |
| **F_out** | Outflow，输出到相邻箱的通量 | kg s⁻¹ | 汇 |

**适用条件（讲义明写的两条 + 一条隐含）：**

1. **箱内充分混合**——"spatial distribution of X within box is **not resolved**"。箱内不存在浓度梯度，或者说我们不关心它。
2. **箱的尺度可选**——"box can be **global atmosphere or some subdomain**"。可以是一个 GCM 格点，也可以是整个大气。
3. （隐含）**通量在时间步内视为常数**——数值上按有限时间步推进。

**边界情况（讲师明说）：**

> "**not all molecules will have chemical production or direct emission or direct chemical losses or deposition. But in many cases it will be the sum of all of them put together.**"

| 物种 | E | P | L | D | 备注 |
|---|---|---|---|---|---|
| **CO₂** | 大 | ≈0 | ≈0 | 地表交换（碳汇） | 对流层化学惰性，寿命极长 |
| **CH₄** | 大 | ≈0 | **大**（与 OH· 反应） | 小 | L 是主导汇 |
| **对流层 O₃** | **≈0** | **大**（光化学） | 大 | 显著 | **二次生成物种的典型代表** |
| **气溶胶** | 一次有 | 二次有 | — | **大**（湿沉降为主） | 寿命短、时空分布极不均匀 |

#### 3.1.3 稳态与寿命

📎 **背景补充：以下的稳态解与寿命定义讲义完全没有给，是我为了回答 Slide 36 第 9 题（"Explain how the lifetime of atmospheric components influences climate model predictions"）而补充的。考试请注明这是标准的箱模式推论。**

**稳态（steady state）**：当 dm/dt = 0 时

$$E + P + F_{in} = L + D + F_{out}$$

即**源与汇平衡**，箱内质量不变。

**寿命 / 滞留时间（lifetime / residence time）τ** 定义为箱内存量除以总去除率：

$$\tau = \frac{m}{L + D + F_{out}}$$

单位：**秒（或年）**。物理含义：如果所有源突然关掉，箱内的 X 衰减到初始值的 1/e 所需的时间（在一阶去除的假设下）。

**为什么寿命对气候模式重要（这是 Slide 36 第 9 题的答案骨架）：**

| 寿命 | 典型物种 | 后果 |
|---|---|---|
| **长（几十年–几百年以上）** | **CO₂、N₂O** | 在大气中**充分混合（well-mixed）**，全球浓度基本均匀 → 模式**不需要高分辨率**就能算对其辐射效应；但**减排的效果要几十年后才显现**（承诺增温 committed warming） |
| **中（约十年）** | **CH₄** | 半混合；减排见效相对快 |
| **短（几天–几周）** | **气溶胶** | **时空分布极不均匀**（随排放源与天气变化）→ 模式**必须有足够分辨率与化学模式**才能算对；但**减排立刻见效** |

这正好呼应了讲师在 Mentimeter 环节之后说的那段话（转写）：

> "**each one of these parameters or processes are not static. They are all changing in time**, some of them very quickly. Things like **aerosol concentrations change rapidly between times and locations**, whereas **greenhouse gases are much more evenly spread due to their longer nature**."

**⚠️ 「气溶胶时空多变、温室气体分布均匀」这个对比的根源就是寿命。** 这是把 Slide 21 和 Slide 25（误差来源里的 cloud representation、rainfall parameterisation）连起来的关键：**正因为气溶胶寿命短、分布不均，模式在网格尺度上表征它才特别困难，不确定性才特别大。**

---

### 3.2 关键图表复述

#### 图 A — Slide 6：过去 6500–7000 万年 + 未来分支（讲师称之为 "Measurements: last 6 million years"）

**讲义 Slide 6 只有标题**（"Measurements: last 6 million years" / "Global Climate Models"），内容全靠转写还原。⚠️ **注意标题写的是「600 万年」，但讲师口述的是「6500–7000 万年」，二者对不上，已登记勘误。**

**讲师描述的内容：**

> "what it shows is the **Earth system changes over the last 65 to 70 million years**. We know that **observational evidence for temperature has been around since 1850-ish**, and measurements of **CO₂, methane and other greenhouse gases** have been available since around the **1950s** or so. We can use **ice core data** to extrapolate out to **800,000 years** or so… Where that ice core data runs out, we start needing to rely on **proxy data**, things like **isotope data from sediments, phytoplankton data, stomata data**… But the accuracy, both in terms of **time dating** but in terms of things like **CO₂ concentration and temperature**, are also **much less certain**."

**怎么读这张图（这是 Week 5 的内容在本周的复用）：**

| 时间区间 | 数据来源 | 精度 |
|---|---|---|
| **1850 至今** | 器测温度（instrumental） | 最高 |
| **1950s 至今** | 直接大气 CO₂ / CH₄ 测量 | 最高 |
| **至 80 万年前** | **冰芯（ice cores）** | 高（气泡直接封存古大气） |
| **80 万年以前** | **代用指标（proxies）**：沉积物同位素、浮游植物、气孔 | **低**，定年与数值都不确定 |
| **未来** | **全球气候模式 + RCP/SSP** | 越远越不确定 |

**图的右端（未来分支）**：讲师指出图上有几条分叉的未来曲线，分别对应「照常发展」（红色）、「有减缓」（SSP2-4.5）、「严格减缓」（SSP1-2.6）。他明确说：

> "these climate models can be used to predict out into the future… **Typically we predict out to 2100**… we have included data **up to 2300**, which is about as far out as some of these global climate models will consider predicting."

**这张图的教学功能（一句话）：把「过去的观测越回溯越模糊」和「未来的预测越外推越模糊」放在同一张图的两端，中间那一小段清晰的部分就是我们的直接知识。**

#### 图 B — Slide 10：GCM 过程示意图

**坐标轴**：无（这是一张剖面式示意图，不是数据图）。

**画面内容（据转写还原）**：一个地球表面的剖面块，上有大气、下有海洋，图上标注：

- **入射短波太阳辐射（incoming shortwave solar radiation）**箭头向下
- **出射长波辐射（outgoing longwave radiation）**箭头向上，以及**温室效应**导致的部分被吸收再发射
- **降水（precipitation）**，分别标出**陆地上**和**海洋上**
- **热量输运（transfer of heat）**箭头
- **陆冰 / 海冰（land ice / sea ice）**，及其对**反照率（albedo）**的影响
- 四大组件的分区：**Atmosphere / Land / Ocean / Sea ice**

**应该读出的结论**：GCM 不是一个「温度公式」，而是一整套**耦合的能量、水、动量循环**。图上的每一个箭头都对应模式里的一段代码。

#### 图 C — Slide 11：三维网格示意

**画面内容**：一个被切成立方体格子的地球（或地球的一块），网格从**地表向上延伸进大气**、**向下延伸进海洋**。

**应该读出的三点结论：**
1. 离散化是**三维**的，不只是水平的地图分块。
2. **每个格子被单独计算**，然后与**相邻格子交换信息**。
3. **格子越小 → 分辨率越高 → 越准 → 计算量越大**（讲义：'A higher resolution model has more, smaller cubes and provides a more accurate picture'）。

#### 图 D — Slide 12–13：非耦合 vs 耦合的架构图

**Slide 12（动画第一步）**：两个分离的方框，标注 **"Atmosphere only Model"** 与 **"Ocean only Model"**，**两者之间没有箭头**。页面底部一句设问：**"Why is this a problem?"**

**Slide 13（动画第二步）**：同样两个方框，改标注为 **"Atmosphere Model"** 与 **"Ocean Model"**，**之间加上了双向箭头**，代表耦合。

**应该读出的结论**：图上「有没有那对箭头」，就是 1990 年代模式与 2000 年代模式的全部差别，也是能不能模拟 ENSO、能不能捕捉海气正反馈的分水岭。

#### 图 E — Slide 14–15：地球系统模式的耦合器架构

**画面内容**：中央一个方框标 **"Coupler"（耦合器）**，周围五个方框呈辐射状连向它：

- **Atmospheric Model**（大气模式）
- **Chemistry Model**（化学模式）
- **Cryosphere Model**（冰冻圈模式）
- **Biosphere Model**（生物圈模式）
- **Ocean Model**（海洋模式）

**应该读出的结论（两层）：**
1. **拓扑结构是「星形」而非「全连接」**——所有交换经由耦合器中转。这就是讲师说的「pick your favourite X model」之所以可行的架构原因：只要符合耦合器的接口，任何子模式都能插进来。
2. **五个组件的清单就是答案 deck Q4 的答案**（见 B3 节关于「四 vs 五」的讨论）。

#### 图 F — Slide 18：未来温度投影地图（"Temperature Measurements: Future"）

**讲义此页只有标题**，内容据转写还原。

**画面内容**：多张世界地图并排，展示不同情景/不同模式分组下**到 2090 年左右**的温度变化空间分布（彩色填色，暖色 = 增温更多）。

**讲师说明的三块：**
> "The IPCC brings together and aggregates around **35 to 40 global climate models** to get their **best estimate, which you see on the left-hand side**. And it can be split into models that predict **relatively higher warming** or indeed **very high warming** models."

**所以这张图的分栏是：**

| 位置 | 内容 |
|---|---|
| **左侧** | **多模式最佳估计（best estimate）**——35–40 个模式的聚合 |
| **中/右** | 按响应强弱分组：**较高增温模式**、**极高增温模式** |

**基准期（baseline）与集合成员的含义** ⚠️：**讲义与转写都没有说明这张图的基准期是哪一段**（是相对 1850–1900 的工业化前，还是相对 1986–2005 的近期基准）。**本笔记不猜测。** 你在答题或复习时，如果需要引用具体数值，**必须回看原始 pptx 的图注**。

📎 背景补充：一般 IPCC 图件的基准期有两种常见约定——**1850–1900**（代表工业化前，用于表述 1.5 °C / 2 °C 目标）和 **1995–2014**（AR6 的近期基准）。看图时先找图注里的 "relative to"，这决定了同一张图上的数字含义完全不同。

**"集合成员（ensemble member）" 的两种含义**（本周会混用，要分清）：
- **多模式集合（multi-model ensemble）**：不同机构开发的**不同模式**各跑一次 → 反映**模式结构不确定性**。IPCC 的 35–40 个模式属于这种。
- **初值集合（initial-condition ensemble）**：**同一个模式**用略有差异的初值跑多次 → 反映**内部自然变率**。K3 节 hindcast 图里「集合平均抓不住年际起伏」讲的就是这种平均的效果。

#### 图 G — Slide 19：UK 夏季降水的「局地」气候投影 ⭐

**这是本周最值得仔细读的一张图。**

**画面内容**：两张英国地图（讲师明确说了上下关系）：

| 位置 | 变量 | 讲师读出的结论 |
|---|---|---|
| **上图** | **降雨日数（number of rainy days）**的变化（百分比） | **南部（south）**变化最大，**频次改变约 50–60%** |
| **下图** | **降雨强度（intensity of rainy days）**的变化 | **东部（eastern side）**受影响更显著 |

**讲义给出的一句话结论（原文）：**

> **"Summer rainfall is less frequent but more intense."**

**坐标轴 / 图例**：这是**填色地图**，没有 x-y 轴；色标代表**相对基准期的百分比变化**。⚠️ **具体的基准期与情景（哪一条 RCP）讲义与转写均未说明，不做猜测。**

**必须读出的三层结论：**
1. **变化是空间不均的**——不能用一个「英国平均」概括；南部与东部受影响的**方式不同**。
2. **频次与强度是两个独立的量**，可以朝相反方向变化。
3. **这就是为什么需要高分辨率**——1998 年那种粗网格模式在这张图上只会给出一两个格子，什么也看不出来（讲师：'using that 1998 model it would be relatively useless in identifying patterns'）。

#### 图 H — Slide 21：箱模式示意图

见 3.1 节。图上元素与符号已在那里完整还原。

**读图要点**：**图的左右两侧是对称的**——左边一组箭头指进箱子（Sources：E、P、F_in），右边一组箭头指出箱子（Sinks：D、L、F_out）。中间的 **X** 就是被追踪的物种，**m** 是它的质量。整张图讲的就是一句话：**浓度由源与汇的竞争决定。**

#### 图 I — Slide 23：模式复杂度演进图

**画面内容**：一排（通常是 4–5 个）立方体或球体，从左到右代表历代 IPCC 报告（FAR → SAR → TAR → AR4 …），每一个上面画的「世界特征」越来越多——最左边只有简单的地表和云，越往右加入海洋环流、气溶胶、碳循环、化学、动态植被、冰盖……

**讲义原话**：
> "The complexity of climate models has increased over the last few decades. The **additional physics incorporated in the models are shown pictorially by the different features of the modelled world**."

**应该读出的结论**：**「模式变好」有两个独立的维度**——**分辨率（格子变小）**和**过程数（画面上的特征变多）**。这张图讲的是后者，讲师提到的「欧洲陆块从看不清到看得清」那张图讲的是前者。**答题时两条都要提。**

#### 图 J — Slide 26：Hindcast → Forecast 对比图 ⭐⭐

**这是本周最重要的一张数据图，几乎必考读图。**

**坐标轴：**
- **x 轴**：**年份**，覆盖范围从 hindcast 期一直到约 **2022**（讲师："What might happen through to 2022"）
- **y 轴**：**全球平均温度（或温度距平）**

**曲线：**
| 元素 | 含义 |
|---|---|
| **一条观测曲线** | 真实观测到的全球温度，**逐年起伏明显（锯齿状）** |
| **模式的集合平均（ensemble mean）** | **平滑的上升趋势线** |
| **一条竖直分界线** | **hindcast 与 forecast 的分界**（讲师："you can see the period here where we **moved from hindcast to forecast**"）。分界左侧模式是在"预测已知的过去"，右侧是在"预测当时的未来" |

**背景**（讲师明说）：这是 **2020 年初完成的一项工作**，评估**2004 年运行的一批全球气候模式**对 **2004 → 今天**的预测表现。

**必须读出的两个结论（讲师逐字强调）：**

> ✅ "the **ensemble mean of the global climate models captures rather nicely the multi-year variation and trends over the last 20 years**"
> ⚠️ "the **mean doesn't capture the variability on a yearly timescale very well. But it does capture the overall trends very well over the 20 years.**"

**这两句合起来就是 Slide 23 那张性能表的图形证据**：模式在**气候尺度（多年–数十年）**上可信，在**年际尺度**上不可信。

**这张图为什么有说服力**：因为 2004 年那批模式**在做预测时并不知道 2005–2020 会发生什么**。这是一个天然的、无法作弊的 out-of-sample 检验。**答「hindcasting 如何评估模式」时，务必提到这个"模式自 1990 年代起就在运行、我们现在可以回头验证"的论点（讲义 Slide 25 原文）。**

#### 图 K — Slide 22 附近 / K4 节提到的「with and without anthropogenic forcing」图

**讲师说 "I think I've showed this slide before so I won't spend too much time on it"**，说明这张图在 Week 5 出现过。

**画面内容**：一张时间–温度图，上有：
- **观测曲线**（黑）
- **一条彩色带 = 只含自然强迫（solar + volcanic）的模式集合范围**——20 世纪后半叶**基本持平或下降**
- **另一条彩色带 = 含自然 + 人为强迫的模式集合范围**——**与观测吻合**

**读出的结论**（讲师原话）：

> "that's **only because global climate models predict very nicely what is happening up to today but only when anthropogenic forcings are included**."

**这就是归因论证的图形形式。** 见 K4 节的三段式论证。

#### 图 L — Slide 32：全球温室气体排放与增温情景（OCR 严重受损，谨慎使用）⚠️

**这一页的 md 文本由图片 OCR 得到，讹误很多。** 能可靠还原的部分如下：

**这实际上是两张图拼在一页上。**

**（左/上）IPCC AR5 风格的排放路径图：**
- **x 轴**：年份，**1950 → 2100**
- **y 轴**：**年度人为温室气体排放（Annual emissions, GtCO₂/yr）**，刻度可见 100、200
- **曲线**：**历史排放（Historical emissions）**一条，加上四条 **RCP 情景**：**RCP8.5 / RCP6.0 / RCP4.5 / RCP2.6**（OCR 把 RCP4.5 打成了 "RCPAS"）
- **右侧色带**：**WGIII AR5 情景数据库在 2100 年的全范围**，按 2100 年 CO₂-eq 浓度分类（OCR 给出的类别为 >1000、720–1000、580–720、530–580、430–530、430–480 ppm CO₂-eq —— ⚠️ **这个列表 OCR 有重复/缺项，不可靠，已登记勘误**）

**（右/下）Our World in Data / Climate Action Tracker 的情景图：**
- **标题**：Global greenhouse gas emissions and warming scenarios
- **y 轴**：**年度全球温室气体排放（gigatonnes of CO₂-equivalents）**，可见刻度 100 Gt、150 Gt
- **x 轴**：**1990 → 2100**
- **五条路径 + 对应的 2100 年增温**（**这组数字很值得记，是本周唯一一组情景–温度对照**）：

| 路径 | 2100 年增温（相对工业化前） | 含义 |
|---|---|---|
| **No climate policies** | **4.1–4.8 °C** | 如果各国从未实施任何减排政策的基线 |
| **Current policies** | **2.8–3.2 °C** | 按目前已落实的政策 |
| **Pledges & targets** | **2.5–2.8 °C** | 如果所有国家都兑现其减排承诺 |
| **2 °C pathways** | 2 °C | — |
| **1.5 °C pathways** | 1.5 °C | — |

- **图注明确说明两件事**：
  1. "**Each pathway comes with uncertainty, marked by the shading** from low to high emissions under each scenario."（**每条路径都有一条阴影不确定性带**）
  2. "**Warming refers to the expected global temperature rise by 2100, relative to pre-industrial temperatures.**"（**基准期 = 工业化前**，⚠️ 这是本周唯一一处明确给出基准的图）
- **数据来源**：Climate Action Tracker，**基于截至 2019 年 12 月的各国政策与承诺**。⚠️ **这个日期意味着图上的数字已有数年之久，已登记勘误提示。**

**必须读出的结论：**
1. **「承诺」与「已落实政策」之间有真实的缺口**（2.5–2.8 vs 2.8–3.2 °C）——**说到做到本身就是一个未解决的问题**。
2. **即使兑现所有承诺，仍然远高于 2 °C**，更别说 1.5 °C。
3. **政策确实有效**——从「无政策」的 4.1–4.8 °C 降到「现行政策」的 2.8–3.2 °C，是一个巨大的差距。**这是回答「政策有没有用」的直接证据。**

#### 图 M — 答案 deck Slide 3：地球系统模式的过程清单图（OCR 受损）

这是回答 workshop 讨论题「建模需要哪些变量」的官方答案图。OCR 还原出的是**按四大圈层分组的过程清单**：

| 圈层 | 图上列出的过程（OCR 还原，顺序已重排） |
|---|---|
| **ATMOSPHERE（大气）** | Global water cycle（全球水循环）、Extreme weather（极端天气）、Clouds and convection（云与对流）、Aerosols and atmospheric chemistry（气溶胶与大气化学）、Radiative transfer（辐射传输）、Turbulence and surface exchanges（湍流与地表交换） |
| **OCEAN（海洋）** | Modes of variability（变率模态）、Coastal processes and waves（海岸过程与波浪）、Ocean currents and eddies（洋流与涡旋）、Salinity and biogeochemistry（盐度与生物地球化学）、Mixed layer processes（混合层过程）、Deep ocean circulation（深海环流）、Sea ice（海冰） |
| **LAND（陆地）** | Human interactions with land, water, and energy（人类与土地、水、能源的相互作用）、Plant processes（植物过程）、Vegetation dynamics（植被动力学）、Terrestrial biogeochemistry（陆地生物地球化学）、Soil hydrology（土壤水文） |
| **CRYOSPHERE（冰冻圈）** | Ice sheets and glaciers（冰盖与冰川）、Snowpack（积雪）、Melt channels and ice shelves（融水通道与冰架） |

⚠️ **OCR 把列表打乱了，上表中的圈层归属有部分是按语义重排的**（例如 "Human interactions with land, water, and energy"、"Plant processes" 等被 OCR 混在大气/海洋两栏中间）。**这份清单可以当作 workshop 的答题参考，但如需精确引用请对照原 pptx。已登记勘误。**

#### 图 N — 答案 deck Slide 4：IPCC 经典气候系统示意图（OCR 严重受损）

这是那张著名的 IPCC「气候系统组成与相互作用」总图。OCR 还原出的标签（已修正明显讹误）：

- **Changes in the Atmosphere: Composition, Circulation**（大气的变化：成分、环流）
- **Changes in the Hydrological Cycle**（水循环的变化）
- **Changes in Solar Inputs**（太阳输入的变化）
- **Atmosphere**：**N₂, O₂, Ar, H₂O, CO₂, CH₄, N₂O, O₃ etc.**、**Aerosols**
- **Volcanic Activity**（火山活动）
- **Atmosphere–Biosphere Interaction**（大气–生物圈相互作用）
- **Precipitation / Evaporation**（降水 / 蒸发）
- **Terrestrial Radiation**（地面辐射）
- **Human Influences**（人类影响）
- **Land Surface**（陆地表面）
- **Ice–Ocean Coupling**（冰–海耦合）
- **Changes in the Cryosphere: Snow, Frozen Ground, Sea Ice, Ice Sheets, Glaciers**（冰冻圈的变化）
- **Changes in the Ocean: Circulation, Sea Level, Biogeochemistry**（海洋的变化）
- **Changes in/on the Land Surface: Orography, Land Use, Vegetation, Ecosystems**（陆面的变化）

**这张图的教学功能**：它是「气候系统有哪些组分、彼此如何相互作用」的一站式总览，正好是 workshop 第一问的完整答案。⚠️ **该页 OCR 讹误极多（"NuOy Ar"、"ca-Ocsan Coup" 等），已登记勘误，引用请对照原件。**

---

## 四、课堂补充

**本节专收 transcript 里有、讲义上没有的内容。** 这是本周笔记相对讲义的核心增量。

---

### 4.1 期中测验（Mid-Semester Test）讲评 ⭐

**这是本周开场最重要的行政信息，讲义完全没有。** 讲师原话：

> "This is the **first time I've seen you since the mid-semester test**."
> "**Very well done on the mid-semester test.** I think hopefully a lot of you are happy with the marks you've walked out of there with."
> "**You should now be able to see your grade. I don't think you can yet see the answers to the individual questions.** My job over the last couple of weeks has been just to **check through those marks and make sure that they are accurate. I think they are.** So we're in a place now that **I can upload the questions and answers for you individually**."
> "**If you have questions about any of the marks, any of the questions, please come and find me either by email or chat in the workshops next week.** But hopefully you all should be happy with your marks."

**要点整理：**

| 事项 | 状态（截至 3 月 19 日） |
|---|---|
| **成绩（grade）** | ✅ **已可查看** |
| **各题答案** | ❌ **尚未开放**，但讲师说「现在可以上传了」——所以应该会在本周之后放出 |
| **讲师做了什么** | 过去两周在**核对分数的准确性**，他认为分数是准确的 |
| **有疑问怎么办** | **发邮件**给他，或**下周的 workshop 当面找他聊** |
| **整体表现** | 讲师两次说 "very well done"，语气是满意的 |

**⚠️ 行动项**：如果你对期中测验的某道题有疑问，**Week 07（3 月 26 日）的 workshop 是当面问的窗口**。讲师明确点名了这个渠道。

**注意**：讲师**没有**讲评任何具体题目、也**没有**公布班级平均分或分数分布。转写里没有这些信息，本笔记不作猜测。

### 4.2 期末考试与 Week 11 复习课的规则 ⭐⭐

**这是本周第二条重要行政信息，也是对你最有实际价值的一条。**

> "that leads us on to the **second part of the assessment, which is going to be in the semester two exam period**. What I want you to start thinking about is **the sorts of things you might like me to either go over again or cover in more detail**."
> "So **week 11 revision lecture, there is NO material until you start asking questions**. So that is **entirely dictated by** either **the bits you haven't understood** or **the bits you would like me to go over again**."
> "So please use this **Mentimeter link**. **I'm going to start leaving that at the end of every lecture.**"
> "**If you don't ask any questions, there won't be any slides and it won't be a very long lecture.** And I'm happy to do that. So **the onus is on you guys to ask questions** and help guide what you would like to see in that revision lecture."

他在课末又强调了一次：

> "Last thing I'll say before the workshop is **please start to think about using this code**. Again, comments, feedback, always welcome. But **start to think about the sorts of things you would like me to talk about in the revision lecture**."

**⚠️⚠️ 这是本周最具行动价值的信息，务必执行：**

1. **Week 11（5 月 7 日）的复习课内容 100% 由学生提问决定。**
2. **不提问 = 没有幻灯片 = 复习课很短。** 讲师明说他对此完全接受。
3. **提问渠道是每节课末尾的 Mentimeter 链接**，从本周开始每节课都会留。
4. **建议做法**：从现在开始建一个「不懂清单」，每周上完课就往 Mentimeter 里丢一条。**这是把复习课变成一堂"定制化答疑"的唯一机会。**

**从考试角度看，这条信息的价值**：期末笔试占 **70%**，而复习课是唯一一次能让讲师**按你的弱项**重讲的机会。这是一个几乎零成本、高回报的行动。

### 4.3 「有 36 个 IPCC 认可的气候模式」（讲义未给数字）

> "There are **36 climate models that are recognised and used by the IPCC**. So what we want to do is understand how we can **compare such a broad diversity of global climate models** and **how we can ensure that the inputs are the same**. And that's done through **representative concentration pathways**."

后面看 Slide 18 时又说：

> "The IPCC brings together and aggregates around **35 to 40** global climate models."

⚠️ **两处数字不完全一致（36 vs 35–40），已登记勘误。答题写「约 35–40 个」最安全。**

**这个数字的重要性**：它把 J2 节的「可比性」问题变得具体——**几十个独立开发的模式**，如果输入不统一，聚合结果毫无意义。**RCP 就是为这几十个模式定的"统一考卷"。**

### 4.4 「AI 那部分是我这几天刚加的」

> "**a bit that I've added in the last couple of days** that might not be reflected on the [Canvas] side is **how climate models might change into the future**. And we're going to **think together about what improvements might be needed** based on what we discussed today."

**含义有二：**
1. **Canvas 上的旧版材料可能没有 Slide 29–30**，以课堂发的这版为准。
2. **这是讲师当下关心的话题**，Slide 36 的样题清单里也有专门一题（第 13 题），**考到的概率不低**。

### 4.5 讲师口头使用 SSP 命名（讲义只用 RCP）

见 A5 节。**讲义正文从头到尾只讲 RCP，转写里讲师说的是 SSP1-2.6、SSP2-4.5。** 这说明他在读的那张图来自 AR6。**考试请以讲义的 RCP 为准**，但你应该知道 SSP 是什么（见 A5 节的 📎 补充）。

### 4.6 「负排放技术」（讲义未提）

> "**SSP 1 to 2.6 are severe mitigations** in terms of reductions of greenhouse gas emissions, **very quickly, very abruptly, and probably with the use of negative emission technologies as well**."

**这是理解 RCP2.6 / SSP1-2.6 有多难的关键补充**：不只是「少排」，还需要「负排」。讲义 Slide 24 只说 RCP2.6 是 "stringent mitigation scenario"，没有点破这一层。

### 4.7 模式内部是「数十万行代码」

> "in these climate models, essentially there are **hundreds of thousands of lines of code** which simulate individual processes that are then looked at together."

**这个具体化很有用**：它让「模式」从一个抽象名词变成了一个工程产物。也解释了为什么模式开发需要大团队、为什么模式之间会有结构性差异。

### 4.8 时间分辨率（讲义完全没提）

> "We also need to think about the **time resolution** as well. So it's **not just the size of the cubes**, it's **how often these cubes are analyzed in time**."

见 C3 节。**这是讲义误差清单（Slide 25）里没有的第三个分辨率维度。**

### 4.9 那个海气正反馈的具体例子

见 D2 节。**这是讲师为回答 Slide 12 的设问 "Why is this a problem?" 而口头给出的完整例子，讲义上一个字都没有。** 建议整段背下来当模板。

### 4.10 耦合器 = 「挑你最喜欢的模式」

见 D5 节。

> "what this allows you to do is **pick your favourite atmospheric model to couple to your favourite biosphere model, to couple to your favourite ocean model** and so on. **There is not a single atmospheric chemistry model. There are many different types.**"

**这句话解释了整个"模块化"设计哲学，讲义 Slide 14–15 只画了架构图、没有文字说明。**

### 4.11 气溶胶的直接效应与云反照率效应

见 D4(ii)。

> "the interaction of the aerosols with incoming solar radiation. Both through the **direct effect**, which is directly interacting with incoming solar radiation. Or the **cloud albedo effect**, which is the impact of aerosols on **cloud formation, lifetime and precipitation rates**."

**讲义只说化学模式"模拟气溶胶"，没有拆出这两条机制。这两个术语是考点。**

### 4.12 UK 农民 —— 全周的核心比喻

见 E4。讲师用了**三次**，跨越三张不同的幻灯片。**这是他本周最想让你记住的具象化例子。**

关键的四个问题（讲师原话）：
- "**How many rainy days might he expect?**"
- "**What is the rainy day intensity?**"
- "**What crops should they plant?**"
- 隐含："**这些问题粗分辨率模式一个都答不了。**"

### 4.13 「沟通输出」也是模式价值的一部分

见 E5。

> "it's **not just what models and how models are operated, it's how those outputs are communicated** becomes very important as well. So something like this is **almost useless for someone trying to make a decision**."

**讲义完全没有这一层。** 这是一个很好的「批判性评价」素材。

### 4.14 HadCM3 的 19/20 层

见 F2。**讲义 Slide 20 没有给任何数字，这个 19 层大气 + 20 层海洋完全来自转写。**

### 4.15 对流层臭氧不是直接排放的（+ 三年级课程预告）

见 G2(iii)。

> "**Ozone in the troposphere is not directly emitted** but it is **made through a series of photochemical reactions** that we touch on and cover in a huge amount of detail in **my atmospheric composition lecture series in year three**."

**顺带一条选课信息**：Dr Bannan 在**三年级开设大气成分（atmospheric composition）系列讲座**，会详细讲光化学。对 Energy and Resources 方向、且对大气过程感兴趣的同学，这是一条相关的后续课程线索。

### 4.16 甲烷的化学去除

见 G2(iv)。讲师说甲烷 "readily reacts with **different oxygens** in the atmosphere"。📎 我在 G2 里补充了这实际指 OH· 自由基——**这个具体化学讲义与转写都没给，请注意区分。**

### 4.17 「一次模拟要在超算上跑几周」

> "Ultimately a large part of this is the **reliance on very heavy computer power**… **Simulation can take weeks on supercomputers.** So you can start to think how this might **limit the number of simulations that any one person could run**."

**这个数字把 C2 节抽象的 trade-off 变成了具体的现实约束**，也是 L 节 AI 吸引力的直接来源。

### 4.18 「本系已经在常规使用 AI/ML」

> "this is an **exciting opportunity** and is indeed **being used by our department quite regularly now**."

**曼大 EES 系的现状。** 对将来想做研究/毕设选题的同学，这是一条有用的信息。

### 4.19 ⭐ Week 9 将有客座讲者讲地球工程（讲义课程表里没有）

**这是本周最大的课程安排变动，讲义 Slide 2 与 Slide 37 都没有提到。** 讲师原话：

> "One of the main questions I've got from you guys over the last few weeks is — well the first one is **what's on the exam**. The second one is **how can we modify our climate through geoengineering processes**."
> "I've spoken with a couple of my colleagues and I've asked one of them **who is working directly in geoengineering to come and give our lecture in week 9**. So **Jessica Gerwood** will come in and talk about some of the work she is doing directly on **marine cloud whitening**, which is a **UK project** that will look to **directly modify the lifetime of clouds**."
> "So I've asked her to come in in **week 9** to talk about work that is ongoing here that will **directly look to limit global warming to 1.5 degrees C**. So Jess will come in and talk about some of the work she is doing in geoengineering and she will take **about half an hour** to talk you through some of that."

**要点：**

| 项目 | 内容 |
|---|---|
| **时间** | **课程 Week 9**（＝笔记 Week 08，4 月 23 日） |
| **讲者** | **Jessica Gerwood**（⚠️ 姓名为语音转写，拼写不确定，已登记勘误） |
| **主题** | **地球工程（geoengineering）**，具体是**海洋云增白 / 海洋云增亮（marine cloud whitening / brightening）** |
| **时长** | 约半小时 |
| **背景** | 一个**英国的项目**，目标是**直接改变云的寿命**，从而**把全球增温限制在 1.5 °C** |
| **起因** | **学生反复提问**——讲师明说是因为你们一直在问地球工程 |

📎 背景补充：**海洋云增亮（Marine Cloud Brightening, MCB）** 是一种太阳辐射管理（Solar Radiation Management, SRM）技术：向海洋低层云中喷洒海盐气溶胶，增加云凝结核数量 → 云滴数变多、粒径变小 → **云的反照率增加**（Twomey 效应）、**云寿命延长**（Albrecht 效应）→ 反射更多太阳辐射 → 局地降温。**注意它与本周 D4(ii) 讲的"气溶胶–云反照率效应"是同一个物理机制，只是被主动利用。** 「Twomey / Albrecht 效应」这两个名字本课材料没给，是我的补充。

**⚠️ 讲师用的词是 "marine cloud whitening"，学界更常用的是 "marine cloud brightening"。已登记勘误备查。**

**另外注意讲师顺带说的第一句**：学生问得最多的问题是 **"what's on the exam"**。他的回答方式就是 Slide 36 的 13 道样题 + Week 11 的定制复习课。

### 4.20 下周预告：适应 ≠ 减缓

> "next week we will look at **adapting to climate change**. There is a **big difference between adapting to climate change and mitigating climate change**. We are going to look next week at **adapting and impacts**."

讲义 Slide 37 也列了 Week 8 的 ILO，其中第二条正是：

> "Describe the **difference between climate change adaptation and mitigation**, and why **both approaches are necessary**."

**⚠️ 讲师专门强调了这个区别，说明它是考点。** 先记住核心区分：

| | **减缓（Mitigation）** | **适应（Adaptation）** |
|---|---|---|
| **针对什么** | **原因**——减少温室气体排放/增加吸收 | **后果**——降低已经/将要发生的影响造成的损害 |
| **时间尺度** | 效果滞后数十年（气候惯性） | 效果相对即时 |
| **尺度** | 全球性（一国减排全球受益） | 高度**地方化** |
| **例子** | 可再生能源、碳捕集、造林 | 海堤、抗旱作物、预警系统、空调普及 |

**两者都必需**，因为：已排放的温室气体导致的增温已经锁定（必须适应），而不减缓的话适应的成本会失控（必须减缓）。

### 4.21 Mentimeter 互动 workshop 的实况

见第五节 5.1。讲师给了学生 **8–10 分钟**（他说 "through to 22"，即到下午 2:22 左右）在 Mentimeter 上填写「你的气候模式需要哪些变量」，然后现场点评了学生的答案：

> "you've covered very nicely sort of a **range of natural and anthropogenic impacts** that we've discussed throughout the course. There's also things like capturing **atmosphere, ocean, cryosphere and biosphere**. They've all been covered by these responses largely."

**⭐ 然后他给了一个学生们普遍漏掉的关键补充：**

> "I guess the other thing that we need to capture in these is **how each one of these is changing**. **Each one of these parameters or processes are not static. They are all changing in time**, some of them very quickly. Things like **aerosol concentrations change rapidly** between times and locations, whereas **greenhouse gases are much more evenly spread due to their longer nature**."
> "So **not only do we need to think about the individual processes, the individual components, but we also need to think how they might change into the future**. Very often we're thinking about that in terms of **behavioural change** as well. So it's **not just environmental change**. Also things like **social sciences, economics**."

**这段点评是本周的一个隐藏考点**：一个气候模式不只需要**变量清单**，还需要**这些变量随时间演化的规律**，而其中一部分（排放、土地利用）的演化**由社会经济因素决定，不属于自然科学范畴**——**这正是为什么需要 RCP/SSP 这种外部给定的情景。** 这条把 workshop、Slide 24（RCP）和 3.1.3（寿命）三处串了起来。

### 4.22 答案上传的承诺

> "I will **upload this brief answer following the lecture** as I normally do."
> "Are there any questions on that? **I'll upload these answers.** OK, so if you do, **I'll be around at the workshop anyway**."

**答案 deck 就是这里承诺的东西**（本笔记第五节全部基于它）。

---

## 五、Practical 要点

本周的 workshop 分两部分：

- **课中的 Discussion（讲义 Slide 16）**——2 道开放讨论题，用 Mentimeter 现场作答，答案在答案 deck 的 Slide 2–5。
- **课后的完整 Workshop（讲义 Slide 39–48）**——**Q1–Q9 共 9 道题**，答案在答案 deck 的 Slide 6–24。

**⚠️ 覆盖情况说明：Q1–Q9 全部 9 道题在答案 deck 里都有对应解答，没有缺题。** 唯一的不完整之处是 Discussion 的第一问（见 5.1）。

---

### 5.1 课中 Discussion（讲义 Slide 16 / 答案 deck Slide 2–5）

#### 题干（两问）

> **"If you were building a climate model, what variables would you absolutely need to include?"**
> （如果你要建一个气候模式，你**绝对必须**包含哪些变量？）
>
> **"If you wanted to test whether a climate model works, how would you do it?"**
> （如果你想检验一个气候模式好不好用，你会怎么做？）

#### 课堂实况

讲师给了 **8–10 分钟**，学生通过 **Mentimeter** 现场填答。他的点评见 4.21 节。

#### 第一问的官方答案 ⚠️

**⚠️ 答案 deck 的 Slide 3 和 Slide 4 标注为 "Brief Answer"，但内容只有两张图，没有任何文字说明。** 也就是说，**第一问在答案 deck 里没有文字答案，只有图**。这两张图的内容我已在第三节的**图 M**（按四大圈层分组的过程清单）和**图 N**（IPCC 气候系统总图）中尽可能还原，但**两页都是 OCR 结果、讹误较多**，已登记勘误。

**据这两张图，可以整理出的答题框架如下：**

**（a）按圈层组织变量清单（答案 deck Slide 3 的结构）：**

| 圈层 | 必须包含的过程/变量 |
|---|---|
| **大气 ATMOSPHERE** | 全球水循环、极端天气、云与对流、气溶胶与大气化学、辐射传输、湍流与地表交换 |
| **海洋 OCEAN** | 变率模态（如 ENSO）、海岸过程与波浪、洋流与涡旋、盐度与生物地球化学、混合层过程、深海环流、海冰 |
| **陆地 LAND** | 人类与土地/水/能源的相互作用、植物过程、植被动力学、陆地生物地球化学、土壤水文 |
| **冰冻圈 CRYOSPHERE** | 冰盖与冰川、积雪、融水通道与冰架 |

**（b）按「变化 / 强迫」组织（答案 deck Slide 4 = IPCC 气候系统图的结构）：**

- **外部强迫**：太阳输入的变化、火山活动、**人类影响**
- **大气**：成分（N₂, O₂, Ar, H₂O, CO₂, CH₄, N₂O, O₃）与环流的变化、气溶胶
- **循环通量**：降水、蒸发、地面辐射、大气–生物圈相互作用、冰–海耦合
- **各圈层的变化**：海洋（环流、海平面、生物地球化学）、陆面（地形、土地利用、植被、生态系统）、冰冻圈（雪、冻土、海冰、冰盖、冰川）

**（c）讲师口头补充的第三层（4.21 节，⭐ 这一层图上没有）：**
> **不只要列出"有哪些变量"，还要说明"它们如何随时间变化"**——而其中的排放、土地利用等项由**社会经济与行为因素**驱动，所以还需要**情景（RCP）**作为外部输入。

**判分要点（我的整理）**：一份好答案应当 (i) **覆盖四大圈层**而不只是大气；(ii) 同时包含**状态变量**（温度、气压、湿度、风）与**强迫项**（太阳、火山、人为排放）；(iii) 提到**这些量随时间演化**、需要情景输入。第 (iii) 点是讲师明确指出学生普遍漏掉的。

#### 第二问的官方答案（答案 deck Slide 5，**有完整文字**）

> **"How would you test whether a climate model works?"**
> - **Run the model to simulate past climate conditions rather than the future.**（让模式去模拟**过去**的气候，而不是未来）
> - **Compare the model output with real observations** such as **temperature, rainfall, and atmospheric circulation records**.（把模式输出与真实观测比对——温度、降水、大气环流记录）
> - **Check whether the model reproduces long-term trends, seasonal cycles, and natural variability.**（检查模式能否再现**长期趋势、季节循环、自然变率**）
> - **Test the model with and without specific forcing factors** (e.g. greenhouse gases or volcanic aerosols) to see whether it captures observed changes.（**加/不加特定强迫因子**分别测试，看能否捕捉观测到的变化）
> - **Compare results with multiple independent datasets**（satellite observations, weather stations, ocean measurements）.（与**多个独立数据集**比对）
> - **Evaluate how well the model reproduces large-scale climate patterns such as ENSO.**（评估对**大尺度气候模态**如 ENSO 的再现能力）
> - **Test the model across different regions and timescales** to assess where it performs well or poorly.（在**不同区域与时间尺度**上测试，找出强项与弱项）
> - **Compare results from multiple climate models** to see whether they produce consistent outcomes.（**多模式互比**，看结论是否一致）
> - **This process is called hindcasting**, and good agreement with observations **increases confidence** that the model can project future climate change.

**解题路径（怎么组织这 9 条）：**

```
① 做什么      → 让模式跑过去（hindcast）
② 跟什么比    → 观测（温度/降水/环流）
③ 比哪些特征  → 趋势 + 季节循环 + 变率（不只是平均值！）
④ 怎么加强论证 → 开/关强迫的对照实验
⑤ 怎么防止巧合 → 多个独立数据集、多个模式、多区域多尺度
⑥ 结论        → 吻合 ⇒ 增加对未来预估的信心
```

**⚠️ 判分要点（容易漏的三条）：**
1. **第 ③ 条**——只比"平均温度对不对"是不够的，还要比**季节循环**和**变率的幅度**。K4 节的归因协议第 2 步就是这个意思。
2. **第 ④ 条**——"with and without forcing" 是把"检验"升级为"归因"的关键。
3. **第 ⑧ 条**——**多模式一致性**是独立于单模式检验的另一层证据。

---

### 5.2 Q1. 科学家为什么要用模式来研究气候变化？

> **题干**：Why do scientists use models to study climate change?

**答案 deck 原文：**

> Climate models are used because they allow us to develop an understanding of:
> - **Past climate changes by recreating historical conditions (hindcasting)**
> - **Forecasting future climate trends under various greenhouse gas emission scenarios.**
> - **Examining the impacts of different factors** (e.g., GHG, aerosols, deforestation, land use change…) **on global temperature** and the effect these may have.
> - These models are **based on physics and incorporate real-world data**, improving our understanding of how climate will change into the future.
> - **Accurate measurements are essential for verifying and improving the reliability** of global climate models. They provide the **observational data needed to test model predictions, identify uncertainties, and guide future model development.**

**解题路径**：答案是三个功能 + 两个属性。

| 层次 | 内容 |
|---|---|
| **功能 1：向后** | **Hindcasting**——重建历史，理解过去的变化 |
| **功能 2：向前** | **Forecasting**——在不同排放情景下预估未来趋势 |
| **功能 3：拆解** | **因子分离**——检验单个因子（温室气体、气溶胶、毁林、土地利用变化）各自的贡献 |
| **属性 1** | **基于物理**（不是曲线拟合），并**融合真实观测数据** |
| **属性 2** | **观测反过来检验和改进模式**（双向关系） |

**⚠️ 加分点（转写里讲师的说法，答案 deck 没写）**：见 A1 节的「拉杆（levers）」比喻——**模式是唯一能做反事实实验的地方**，因为我们只有一个地球，无法做对照实验。**把这句加进答案会明显提升层次。**

**判分要点**：注意最后一条其实是在讲 **Week 5 与本周的关系**——观测不是模式的替代品，而是模式的**检验者、不确定性识别者、发展方向指引者**。答题时不要把模式和观测对立起来。

---

### 5.3 Q2. 气候模式的主要不确定性是什么？如何改进？

> **题干**：What are the major uncertainties in climate models, and how can they be improved?

**答案 deck 原文：**

> Sources of uncertainty include but are not limited to:
> - **Cloud representation**: Clouds contribute to **both warming and cooling**, but **small-scale cloud processes are challenging to model**. **This is a very active area of research at the University.**
> - **Aerosol effects**: The **cooling impact of aerosols** (e.g., from pollution or volcanic eruptions) is **not yet fully understood**. **Again, this is a very active area of research at the University.**
> - **Regional climate responses**: **Model resolution limits accuracy at a local scale**, particularly for **extreme weather events**. This makes **identifying local impacts challenging**.
> - Advances can be made through **higher-resolution models**, **enhanced observational data** (e.g., satellite measurements or more dense ground-based observations), and maybe the use of **artificial intelligence** to refine operations.

**解题路径**：**三个不确定性来源 + 三条改进途径**，结构非常对称，很好记：

```
不确定性               →  改进途径
① 云的表征             →  ① 更高分辨率模式
② 气溶胶效应           →  ② 更好的观测（卫星 + 更密的地面站）
③ 区域气候响应         →  ③ AI / 机器学习
```

**关键细节：**

- **为什么云特别难**：答案 deck 点出了核心——**云同时造成增温和降温**（低云反射太阳辐射 → 降温；高云吸收长波 → 增温）。净效应取决于云的高度、厚度、相态、粒径分布——**这些都是小尺度过程，必须参数化。** 见 E2 节。
- **气溶胶的两个来源**：**污染（pollution，人为）**和**火山喷发（volcanic eruptions，自然）**。这正好接上 Q5 的火山「自然实验」。
- **⚠️ "This is a very active area of research at the University" 出现了两次**——**云与气溶胶都是曼大 EES 的强项研究方向**。讲师在转写里也反复提这两块的不确定性最大。这既是学术信息，也暗示这两条是他心目中的重点。

**⚠️ 可补充的第四条（讲义 Slide 25 有，答案 deck 漏了）**：**自然变率**（火山、ENSO）的不可预测性，以及**大气/海洋垂直层的观测稀疏**。答题时补上这两条会更完整。

---

### 5.4 Q3. 自然变率与人为气候变化的区别？如何在模式中区分？

> **题干**：What is the difference between natural variability and human-induced climate change? How do we model their effects in climate studies?

**答案 deck 原文：**

> - **Natural variability** refers to **fluctuations in the climate system** caused by processes such as **ocean circulation, solar activity, solar input and volcanic eruptions**.
> - **Human induced climate change**, by contrast, results from activities such as **burning fossil fuels, deforestation, and industrial emissions**, which **alter greenhouse gas concentrations**.
> - **Observational records**, including temperature and precipitation data, are **compared with climate models** to distinguish natural variability from anthropogenic effects.
> - Climate models can also be **run with and without anthropogenic inputs** to differentiate between the two types of processes.

**解题路径**：**定义 + 定义 + 两种方法**。

| | 自然变率 | 人为气候变化 |
|---|---|---|
| **驱动源** | 海洋环流、太阳活动 / 太阳输入、火山喷发 | 化石燃料燃烧、毁林、工业排放 |
| **作用机制** | 内部再分配（如 ENSO）或外部自然强迫（太阳、火山） | **改变温室气体浓度**（外部人为强迫） |
| **典型时间尺度** | 年际到千年（ENSO 几年、火山约一年、米兰科维奇数万年） | 工业革命以来持续单向 |

**区分的两种方法：**
1. **观测 vs 模式对比**——把真实的温度、降水记录与模式结果比。
2. **⭐ 开/关人为输入的对照实验**——这就是 K4 节的四步归因协议。

**⚠️ 加分点（讲义 Slide 27 有，答案 deck 没展开）**：把归因协议的**四步**写出来（无强迫控制跑 → 与观测比对验证 → 加强迫重跑 → 取差值），比只说 "run with and without" 详细得多。

**⚠️ 另一个加分点（转写）**：讲师那句结论——

> "global climate models predict very nicely what is happening up to today **but only when anthropogenic forcings are included**"

**这是"充分性论证"，比单纯说"我们跑两次"有力得多。**

---

### 5.5 Q4. GCM 的关键组件是什么？为什么耦合重要？

> **题干**：What are the key components of a Global Climate Model, and why is coupling different models important?

**答案 deck 原文：**

> **GCMs consist of five major components:**
> - **Atmosphere** – Governs **weather patterns, temperature, and precipitation**.
> - **Cryosphere** – Includes **ice sheets, glaciers, and sea ice**, which influence **albedo and ocean circulation**.
> - **Chemistry** – Represents **atmospheric composition**, including **greenhouse gases and aerosols**.
> - **Ocean** – **Regulates heat distribution through currents** and interacts with the atmosphere.
> - **Biosphere** – Encompasses **vegetation, land use, and ecosystems**, which affect **carbon cycling and climate feedbacks**.
>
> **Coupling these components is crucial, as their interactions drive climate variability. For example:**
> - **Ocean currents influence atmospheric circulation patterns.**
> - **Land-use changes impact surface albedo and greenhouse gas concentrations.**
> - **Ice dynamics regulate sea level and energy balance.**
>
> Without coupling, GCMs would **fail to represent critical climate feedback mechanisms**, such as **ENSO** and long-term climate shifts. Integrating these components ensures a more accurate representation of Earth's climate system. **Very big steps forward have been made in this space over the last 20 years.**

**⚠️ 注意**：这里说的是**五个**组件，而讲义 Slide 10 说的是**四个**（Atmosphere / Land / Ocean / Sea ice）。**这是讲义与答案 deck 之间真实的对不上，已登记勘误。答题策略见 B3 节**——按五组件答，并加一句说明这是从早期四组件物理模式演化来的。

**解题路径**：**五组件 + 三个耦合例子 + 一个反证。**

**每个组件的「一句话功能」（务必能默写）：**

| 组件 | 一句话功能 |
|---|---|
| **大气 Atmosphere** | 支配天气形态、温度、降水 |
| **冰冻圈 Cryosphere** | 冰盖、冰川、海冰 → 影响**反照率**与**海洋环流** |
| **化学 Chemistry** | 表征大气成分——温室气体与气溶胶 |
| **海洋 Ocean** | 通过洋流**调节热量分布**，并与大气相互作用 |
| **生物圈 Biosphere** | 植被、土地利用、生态系统 → 影响**碳循环与气候反馈** |

**三个耦合例子的方向性（注意每一条都是跨组件的）：**
- **海洋 → 大气**：洋流影响大气环流形态
- **陆地/生物圈 → 大气**：土地利用变化影响地表反照率与温室气体浓度
- **冰冻圈 → 海洋 + 能量平衡**：冰动力学调节海平面与能量收支

**反证（最有力的部分）**：不耦合 ⇒ **无法表征关键反馈机制**，**ENSO 就模拟不出来**。

**⚠️ 加分点（转写独有，见 D2 和 D6）**：
1. 讲师那个**海洋 CO₂ outgassing 正反馈**的具体例子。
2. **"nonlinear responses"**——耦合之所以重要，是因为反馈让系统非线性，**整体不等于部分之和**。

---

### 5.6 Q5. 火山喷发如何充当研究气溶胶强迫的「自然实验」？

> **题干**：How can volcanic eruptions serve as a "natural experiment" for studying climate response to aerosol forcing?

**答案 deck 原文：**

> - Large volcanic eruptions can inject **large quantities of aerosols (mostly sulphate) into the stratosphere**, which **temporarily cool the Earth's surface**.
> - **Aerosols in the stratosphere have a longer lifetime than those in the troposphere**, so their **cooling effects last longer**.
> - These events allow scientists to observe **short-term (around a year) climatic responses to changes in radiative forcing**.
> - **Smaller eruptions also emit large concentrations of aerosols into the troposphere, like anthropogenic sources of aerosol.**
> - They provide **real world data to test and validate climate model predictions** about aerosol impacts.
> - Case studies, such as the eruption of **Mount Pinatubo in 1991**, are important examples where measurable effects have been observed.
> - **"Figure to the right shows key examples too"** ⚠️（**该图在 md 转换结果中不存在**，已登记勘误）

**解题路径**：这道题的核心是理解「自然实验（natural experiment）」这个词的方法论含义。

📎 背景补充：**"自然实验"指的是：自然界替我们施加了一次我们无法（也不该）人为施加的扰动，且这次扰动的时间、幅度、性质相对清楚，因此可以当作一次准受控实验来分析。** 这个方法论定义答案 deck 没有明说，是我的补充。

**为什么火山是理想的自然实验（四个理由）：**

| 理由 | 说明 |
|---|---|
| **① 强迫是脉冲式的** | 喷发是一个**近似瞬时**的注入，之后自然衰减——干净的「阶跃/脉冲响应」实验 |
| **② 强迫的性质已知** | 主要是**硫酸盐（sulphate）气溶胶**，散射太阳辐射 → **负辐射强迫 → 降温** |
| **③ 强迫的幅度可测** | 卫星与地基观测能测出气溶胶光学厚度 |
| **④ 响应的时间尺度合适** | **约一年**——足够长到能观测到气候响应，又足够短到能与长期趋势区分开 |

**⭐ 平流层 vs 对流层 —— 这是本题最关键的物理区分：**

| | **平流层（stratosphere）气溶胶** | **对流层（troposphere）气溶胶** |
|---|---|---|
| **来源** | **大型**火山喷发（喷发柱足够高，穿透对流层顶） | **小型**火山喷发、**人为排放** |
| **寿命** | **长**（约 1–2 年） | **短**（约几天–几周） |
| **原因** | 📎 平流层**稳定层结、无对流、几乎无降水** → **没有湿沉降这个主要清除机制** | 对流层有云和降水 → 被高效清除 |
| **气候效应** | **持续 1–2 年的全球降温**，效应可测 | 局地/区域效应，时空高度不均 |

（📎 上表中"为什么平流层寿命长"的物理原因是我的补充；答案 deck 只说了 "longer lifetime"，没说原因。**这正好用 3.1.3 的寿命公式解释：D 这一项在平流层几乎为零，所以 τ = m/(L+D+F_out) 变大。**）

**⚠️ 第 4 条容易被跳过，但它很重要**：**小型喷发把气溶胶排进对流层，性质与人为气溶胶相似**——所以火山不只能研究平流层气溶胶，也能作为人为气溶胶的类比对象。

**具体案例**：**1991 年皮纳图博火山（Mount Pinatubo）喷发**——这是本周唯一被点名的案例，务必记住年份。

**这道题与 Q2 的联系**：Q2 说「气溶胶的降温效应尚未被完全理解」，Q5 说的正是**我们用什么手段去减少这个不确定性**——用真实世界的火山事件去**检验和验证（test and validate）**模式对气溶胶的处理。**两道题应当连起来答。**

---

### 5.7 Q6. 自然变率能解释观测到的全球变暖趋势吗？为什么？

> **题干**：Can natural variability explain observed trends in global warming? Why or why not?

**答案 deck 原文：**

> - Earth's climate history has been reconstructed using **indirect records** such as **ice cores, tree rings, glacier lengths, pollen remains, and ocean sediments**, alongside studies of **Earth's orbital changes**.
> - These records **reveal natural climate variability over long timescales, but they do not explain the warming observed since the 1950s.** Instead, it is scientifically established that **human activities have been the primary driver** of this warming.
> - Key greenhouse gases — **carbon dioxide, methane, and nitrous oxide** — have risen significantly since [the industrial revolution] due to human activities. **Can you remember how much by?**
> - Their concentrations are now **higher than at any point in the last 800,000 years**. These emissions have **intensified the greenhouse effect**.
> - While natural processes have always influenced climate, **they cannot account for the recent warming**.
> - **This is all confirmed by the IPCC.**
> - **Solar variations**, for instance, can affect the amount of energy reaching Earth, but **satellite data since 1978 show no net increase in solar output, even as global temperatures continue to rise.**

**答案：不能。**

**解题路径（这是一个标准的「排除法」论证，四步）：**

```
① 我们知道自然变率长什么样 —— 靠古气候重建（冰芯、树轮、冰川长度、
   花粉、海洋沉积物、轨道变化研究）
        ↓
② 已知的自然变率无法解释 1950 年代以来的增温
        ↓
③ 逐个排除具体的自然候选者 —— 太阳：1978 年以来的卫星数据显示
   太阳输出没有净增加，而温度持续上升 ⇒ 太阳不是原因
        ↓
④ 人为温室气体确实大幅上升，且浓度超过过去 80 万年任何时刻
   ⇒ 人类活动是主要驱动者（IPCC 确认）
```

**⚠️ 第 ③ 步是最有说服力的一步**，因为它是**可证伪的定量检验**：如果太阳是原因，那么太阳输出应该在上升——**卫星测了，它没有。** 这个「**趋势分离（divergence）**」论证务必掌握。

**⚠️ 答案 deck 里有一句反问：**

> **"Key greenhouse gases — carbon dioxide, methane, and nitrous oxide — have risen significantly since due to human activities. Can you remember how much by?"**

**这是讲师留给你的自测题，答案 deck 没有给数字。** 这些数值出自 **Week 4（人为影响，Simon 主讲）**，**本周材料里没有**，因此本笔记**不填这个数字**——请回 Week 4 的笔记核对，不要凭印象写。

**⚠️ 注意 "since 1978" 这个年份**：这是卫星测量太阳总辐照度（TSI）的起始年，是一个具体可考的数字，值得记住。

**这道题与 Q3、Q5 的关系**：
- **Q3** 给定义（什么是自然变率、什么是人为）
- **Q6** 做判决（自然变率不足以解释）
- **Q5** 提供一个自然变率的具体研究工具（火山）

---

### 5.8 Q7. 我们需要什么来改进未来的 GCM？

> **题干**：What do we need to improve future GCMs?

**答案 deck 原文：**

> - Climate models are **continually evolving with advances in technology and computing power**, improving **accuracy, resolution, and reducing uncertainties**.
> - **Greater availability of observational data, particularly from the oceans**, is crucial for refining models, **though gaps remain**.
> - **Using recent data ensures models reflect current climate conditions** for more reliable projections.
> - **Enhanced computing power** allows for **higher-resolution models, faster computations, and efficient testing of multiple scenarios**.
> - Emerging **AI and machine learning** techniques further improve model accuracy by **identifying patterns in complex processes**.
> - Despite limitations, advanced climate models provide **critical insights for mitigating climate change and planning for a sustainable future**.

**解题路径**：**三条改进途径（这是全周的核心答案模板，Slide 35 的第 6 条也是它）：**

```
① 更多、更好的观测数据（尤其是海洋——缺口最大）
② 更强的算力 → 更高分辨率 + 更快 + 能测试更多情景
③ AI / 机器学习 → 从复杂过程中识别模式
```

**⚠️ 注意「尤其是海洋（particularly from the oceans）」这个限定**，它与讲师在 K1 节说的完全一致——**地表观测密集，海洋和高空观测稀疏。** 这是把 Week 5（观测）与本周（模式）连起来的接点。

**⚠️ 注意 "Using recent data ensures models reflect current climate conditions"**——这一条容易被忽略：模式需要**持续更新**的数据，而不只是历史数据。因为气候本身在变，用几十年前的数据校准的模式可能已经偏离当前状态。

**注意 "though gaps remain"**——答案自己承认观测缺口仍未填补，这是一个诚实的限定，答题时保留这种 hedge 是加分的。

**这道题几乎是 Q2 后半段的扩写**，两道题可以共用同一套答案骨架，但 Q7 更强调「算力」这一条。

---

### 5.9 Q8. 观测的改进（卫星、海洋测量）如何帮助改进气候模式？

> **题干**：How might improvements in observations (e.g., satellites, ocean measurements) help improve climate models?

**答案 deck 原文（七条 + 一句 "And more perhaps…"）：**

> - Provide **more accurate initial conditions** for climate model simulations.
> - Allow scientists to **validate model outputs** by comparing simulations with real-world measurements.
> - Improve representation of **poorly understood processes** such as **cloud formation, aerosol effects, and ocean circulation**.
> - Provide **better coverage of remote regions** (e.g., oceans, polar regions) that previously had limited observations.
> - Help **refine parameterisations** used to represent **small-scale processes that cannot be directly resolved** in models.
> - Improve estimates of **key climate variables** such as **temperature, precipitation, sea ice extent, and ocean heat content**.
> - Enable **continuous long-term datasets**, which help **detect trends and improve confidence** in model projections.
> - **And more perhaps…**

**解题路径**：这七条其实可以归成**四个功能类别**，这样答起来更有结构：

| 功能类别 | 对应条目 | 说明 |
|---|---|---|
| **① 输入（Input）** | 更准确的**初始条件** | 观测喂给模式作为起点 |
| **② 检验（Validation）** | 验证模式输出；连续长期数据集 | 观测作为「标准答案」 |
| **③ 改进过程表征（Process improvement）** | 改进云、气溶胶、海洋环流的表征；**精化参数化** | ⭐ **这是最重要的一类**——观测直接改进模式内部的物理 |
| **④ 填补空白（Coverage）** | 覆盖海洋、极地等观测稀疏区；改进关键变量的估计 | 消除系统性的地理盲区 |

**⚠️ 第 ③ 类是本题的核心，也最容易被漏掉。** 学生通常只想到「观测用来检验模式」（第 ②类），但讲师在 A2 节的「三支柱」里明确说了观测有**两个**功能：**validate**（检验）**和 inform**（供料）。**"Help refine parameterisations" 就是 inform 那一半。**

**具体的例子（📎 我的补充，帮助理解）**：卫星测得的云滴有效半径与云光学厚度，可以直接用来标定云微物理参数化方案里的系数；Argo 浮标测得的海洋温盐剖面，可以约束海洋混合层与热吸收的参数化。**这些具体例子答案 deck 没给。**

**注意 "ocean heat content"（海洋热含量）这个变量**——📎 背景补充：它之所以重要，是因为**地球能量不平衡的 90% 以上被海洋吸收**，所以海洋热含量是比地表温度更稳定、更少受年际噪声干扰的「地球是否在积累能量」的指标。**这个理由答案 deck 没写。**

**这道题与 Q7 的关系**：Q7 问「需要什么」（答案：观测 + 算力 + AI），Q8 是把其中「观测」那一条**展开讲透**。**两题合起来答会很完整。**

---

### 5.10 Q9. 你认为 AI 和机器学习最终会取代物理气候模式，还是只是补充它们？

> **题干**：Do you think AI and machine learning will eventually replace physics-based climate models, or just complement them? Why?

**这是一道开放性论述题**（"Do you think…"），但答案 deck 给出了明确的立场与论据。

**答案 deck 原文：**

> - Current GCMs are **grounded in physical laws**, which ensures that simulations **remain physically realistic**. **AI models typically learn patterns from data and do not inherently enforce these physical constraints.**
> - AI and machine learning are **powerful for analysing large datasets**. They can **rapidly identify patterns** in climate observations and model outputs that may be difficult for traditional methods to detect.
> - Machine learning can **improve parameterisations of small-scale processes** (such as **clouds, turbulence, or convection**) that are difficult to represent accurately in traditional models.
> - AI can **significantly accelerate climate simulations**. They can reproduce parts of climate models much faster, allowing scientists to **run many more scenarios or sensitivity tests**.
> - AI can help **improve prediction of extreme events** (e.g., heatwaves, storms, or heavy rainfall) by learning from **large historical datasets and high-resolution simulations**.
> - However, **AI models depend strongly on the quality and quantity of training data**, which may **limit their reliability when projecting conditions that have not previously occurred**.
> - **The most likely future approach is hybrid modelling, where machine learning techniques complement physics-based models** to improve accuracy, efficiency, and representation of complex processes.

**官方立场：补充（complement），不是取代（replace）。最可能的未来是混合建模（hybrid modelling）。**

**解题路径（这是一道"论证结构"题，六步）：**

```
① 物理模式的不可替代优势：植根于物理定律 ⇒ 保证物理真实性
   （AI 从数据学模式，不天然强制物理约束）
        ↓
② AI 的优势 A：分析大数据集、快速识别难以察觉的模式
        ↓
③ AI 的优势 B：⭐ 改进小尺度过程的参数化（云、湍流、对流）
        ↓
④ AI 的优势 C：大幅加速模拟 ⇒ 能跑更多情景与敏感性测试
        ↓
⑤ AI 的优势 D：改进极端事件预测（从大量历史数据与高分辨率模拟中学习）
        ↓
⑥ ⭐ AI 的致命限制：强烈依赖训练数据的质量与数量
   ⇒ 在"历史上从未出现过的条件"下可靠性受限
        ↓
结论：混合建模 —— ML 补充物理模式
```

**⚠️⚠️ 第 ⑥ 步是这道题的胜负手，务必想透。**

**为什么「历史上没出现过的条件」对气候预测是致命的**：气候投影的**全部意义**就是预测一个**人类从未观测过的未来气候状态**（比如全球比工业化前暖 3 °C 的世界）。而机器学习的本质是**从训练数据中学到输入–输出映射**，它在**训练分布之内（interpolation）**很强，在**训练分布之外（extrapolation）**没有任何保证。**物理定律不同——能量守恒在 3 °C 更暖的世界里依然成立。**

**这就是为什么答案是 "complement" 而不是 "replace"。**

**⚠️ 第 ③ 步是混合建模的具体落地形式**，务必能说清：**保留物理模式的动力学骨架（保证守恒与可解释），把最难参数化的次网格过程（云、湍流、对流）换成从高分辨率模拟中学到的 ML 方案。** 这样两边的优点都拿到了。

**⚠️ 加分点（讲义 Slide 30 + 转写）**：加上 AI 的另外两个挑战——
- **可解释性（interpretability）**：黑箱模型难以诊断错误来源
- **数据偏差（data bias）**：训练数据本身的地理/时间偏差会被模型继承并放大

以及讲师那句实况：**"is indeed being used by our department quite regularly now"**（曼大 EES 已在常规使用）。

**判分要点**：这是开放题，**立场本身不是判分重点，论证质量才是**。一份高分答案必须 (i) 明确 AI 与物理模式的**认识论差异**（数据驱动 vs 第一性原理）；(ii) 给出 AI 的**具体**优势（不是泛泛说"快"）；(iii) 点出**外推可靠性**这一根本限制；(iv) 落到**混合建模**这个建设性结论。

---

### 5.11 Workshop 整体复习建议

**九道题的内在结构（把它们连起来看，而不是九个孤立问答）：**

```
【为什么用模式】     Q1
        ↓
【模式怎么构成】     Q4（五组件 + 耦合）
        ↓
【模式有多可信】     Discussion Q2（怎么检验）→ hindcasting
        ↓
【模式哪里不可信】   Q2（不确定性：云、气溶胶、区域）
        ↓
【怎么用模式做归因】 Q3（自然 vs 人为）→ Q6（自然变率不足以解释）
        ↓
【怎么验证气溶胶】   Q5（火山自然实验）
        ↓
【怎么改进】         Q7（观测 + 算力 + AI）→ Q8（观测展开）→ Q9（AI 展开）
```

**⚠️ 注意 Slide 36 的 13 道样题与这 9 道 workshop 题高度重叠**——样题 3、4 对应 Q3/Q6，样题 6 对应 RCP，样题 7 对应 hindcasting，样题 8 对应 Q2，样题 10 对应 Q8，样题 13 对应 Q9。**把这 9 道答案吃透，Slide 36 的大部分题就都能答。**

**⚠️ 但注意有几道样题在 workshop 里没有对应题目，需要回讲义正文找材料：**
- 样题 1（1.5 °C 阈值为什么重要）→ 讲义 Slide 34 + 转写 A3 节
- 样题 5（网格与分辨率）→ 讲义 Slide 11、17 + 转写 E 节
- 样题 9（大气组分寿命）→ 讲义 Slide 21 + 本笔记 3.1.3 节（📎 部分为补充）
- 样题 12（算力进步）→ 讲义 Slide 17、28 + 转写 E3 节

---

## 六、易错点·重点难点

### 6.1 概念混淆点

#### ⚠️ 混淆 1：「四组件」还是「五组件」？

**这是本周最直接的陷阱**，因为讲义与答案 deck 给了不同的数字。

| 出处 | 组件 |
|---|---|
| **讲义 Slide 10** | **四个**：Atmosphere / **Land** / Ocean / **Sea ice** |
| **答案 deck Q4** | **五个**：Atmosphere / **Cryosphere** / **Chemistry** / Ocean / **Biosphere** |

**怎么办**：见 B3 节。**按五组件答，并说明这是从早期四组件物理模式演化而来。** 注意两个清单的差异不是随意的——**Land → Biosphere**（从物理陆面升级为带生物地球化学的生物圈）、**Sea ice → Cryosphere**（从海冰扩展为含冰盖、冰川、积雪、冻土）、**新增 Chemistry**。

#### ⚠️ 混淆 2：气候（climate）vs 天气（weather）

讲义 Slide 9 的定义必须能背：

- **气候** = **长时期内的平均天气**，例如**30 年**
- **天气** = 一个地区在**逐时或逐日**尺度上经历的状况

**为什么这个区分在本周特别重要**：它直接决定了模式输出该怎么解读。**"模式没预测到 2023 年是最热的一年" 不是对模式的有效批评**，因为模式从不承诺预测某一年。K3 节的 hindcast 图就是这个道理的图形证据。

#### ⚠️ 混淆 3：Hindcast vs Forecast vs Nowcast

| 术语 | 含义 |
|---|---|
| **Forecast（预报/预测）** | 预测**未来** |
| **Hindcast（后报/回报）** | 用模式"预测"**已经发生的过去**，然后与观测比对以**检验模式** |
| **Projection（预估）** | 📎 补充：IPCC 严格区分 **prediction/forecast** 与 **projection**——**projection 是"条件性的"**：「若 RCP8.5 成立，则……」。因为未来排放取决于人类选择，不可预报，所以气候界说的是 projection 而不是 prediction。**这个区分讲义没有明说，但讲义 Slide 9 用的确实是 "project" 一词。** |

**⚠️ 讲师专门提醒 hindcasting 可能是新概念**，并且说这个概念对预测模型来说 "**a weird concept**"。**这是他明示的重点。**

#### ⚠️ 混淆 4：RCP vs SSP

见 A5 节的 📎 补充。**讲义只讲 RCP，讲师口头说了 SSP。考试按讲义答 RCP。**

**最容易记错的一点**：**RCP 后面的数字是 2100 年的辐射强迫（W m⁻²），不是温度，也不是 CO₂ 浓度。** RCP8.5 ≠ 8.5 °C。

#### ⚠️ 混淆 5：不确定性的三种来源（📎 这是我的补充框架，讲义没有这样分类）

📎 背景补充：气候投影的不确定性通常拆成三类，理解这个分类能让你的答案层次分明：

| 类型 | 含义 | 本周对应内容 |
|---|---|---|
| **情景不确定性（scenario uncertainty）** | 我们不知道人类会选哪条路 | **RCP 的存在就是为了把这一项显式化** |
| **模式不确定性（model uncertainty）** | 同样的输入，不同模式给不同答案 | **35–40 个模式的离散度**；参数化方案的差异 |
| **内部变率（internal variability）** | 气候系统自己的混沌涨落 | **ENSO 的几十分之一度**；hindcast 图上抓不住的年际起伏 |

**⚠️ 关键洞察**：**RCP 的作用就是把「情景不确定性」固定住，从而让剩下的差异可以归给「模式不确定性」。** 这是 J2 节那条论证链的正式说法。

#### ⚠️ 混淆 6：适应（Adaptation）vs 减缓（Mitigation）

见 4.20 节的对照表。**讲师专门强调了这个区别，Week 8 会正式讲。**

#### ⚠️ 混淆 7：气溶胶的直接效应 vs 间接（云反照率）效应

| | **直接效应（direct effect）** | **云反照率效应 / 间接效应（cloud albedo / indirect effect）** |
|---|---|---|
| **机制** | 气溶胶粒子**本身**散射/吸收入射太阳辐射 | 气溶胶作为**云凝结核**，改变云滴数与粒径 → 改变**云的**反照率、**寿命**、**降水率** |
| **是否需要云** | 不需要 | **需要** |

**⚠️ 这两个术语在转写里出现，在讲义正文里没有。** 它们是 Q2「气溶胶不确定性」和 Q5「火山自然实验」的物理基础，也是 Week 9 地球工程（海洋云增亮）的机制基础。

---

### 6.2 单位与量级陷阱

| 项目 | 正确值 | 常见错误 |
|---|---|---|
| **RCP 编号的单位** | **W m⁻²**（2100 年的辐射强迫） | 误当成温度（°C）或浓度（ppm） |
| **早期 GCM 水平分辨率** | **250–600 km** | 误记成 25–60 km |
| **UK 模式分辨率演进** | 1998 粗 → 早期 2000s **50 km** → 现在更细 | ⚠️ 讲师提的"米级"指的是**特定的高分辨率大气模拟**，**不是全球 GCM 的常规分辨率**（见 E3 的警告） |
| **HadCM3 垂直层数** | **大气 19 层 + 海洋 20 层** | 两个数字容易记反；注意大气比海洋少一层 |
| **IPCC 汇集的模式数** | 约 **35–40 个**（讲师另一处说 36） | — |
| **气候的定义时长** | **30 年** | — |
| **模式常规投影终点** | **2100**（极限约 **2300**） | — |
| **平流层火山气溶胶的效应时长** | **约 1 年**（答案 deck: "around a year"） | 误以为持续多年 |
| **冰芯记录的时间深度** | **约 80 万年** | — |
| **卫星测太阳输出的起始年** | **1978** | — |
| **皮纳图博火山喷发** | **1991** | — |
| **一次模拟的耗时** | **超算上数周** | — |
| **ENSO 驱动的温度变化** | **几个十分之一度（a few tenths of a degree）** | 误以为是几度 |
| **UK 南部夏季降水频次变化** | **约 50–60%** | 注意这是**频次**的变化，不是降水量 |
| **2100 年增温：无政策 / 现行政策 / 承诺** | **4.1–4.8 / 2.8–3.2 / 2.5–2.8 °C** | 三组数字容易记混；注意是**相对工业化前** |

**⚠️ 一个尺度直觉练习**：600 km 的格子有多大？大约是**曼彻斯特到巴黎的距离**。整个不列颠群岛在这样的模式里就是**一两个格点**。这个直觉能帮你理解为什么 Slide 19 的降水图必须靠高分辨率模式才画得出来。

---

### 6.3 常见推理谬误

#### ❌ 谬误 1：「模式没预测对某一年，所以模式不可信」

**为什么错**：模式从不承诺预测年际起伏。K3 节讲师明说 "the mean doesn't capture the variability on a yearly timescale very well. **But it does capture the overall trends very well over the 20 years.**"

**正确的检验方式**：看**趋势**是否被捕捉，看观测是否落在**集合离散度带**之内。

#### ❌ 谬误 2：「模式在历史上表现好，所以未来一定准」

**为什么错**：见 K2 节的边界条件——(a) 模式参数可能是针对历史调过的；(b) 未来可能进入历史上没有的状态。

**正确的表述**：hindcast 表现好**增加了信心（increases confidence）**——注意答案 deck 用的正是这个措辞，不是 "proves"。

#### ❌ 谬误 3：「把大气模式的结果和海洋模式的结果加起来 = 耦合模式的结果」

**为什么错**：反馈让系统**非线性**（讲师原话 "nonlinear responses"）。**非线性系统里整体 ≠ 部分之和。** 这就是 D6 节说的、Slide 36 第 2 题的最高分答法。

#### ❌ 谬误 4：「分辨率越高就一定越准」

**为什么部分错**：讲义确实说 "higher resolution → more accurate picture"，但有两个限定：
1. **代价是计算量**（C2 节：分辨率与「能跑多少次模拟」是竞争关系）；
2. 📎 补充：提高分辨率**解决的是"可解析尺度"的问题，不自动解决参数化方案本身的偏差**。如果云的参数化方案有系统性偏差，把格子缩小一半并不会让它消失。

#### ❌ 谬误 5：「AI 更快更准，所以会取代物理模式」

**为什么错**：见 5.10 节第 ⑥ 步——**气候投影本质上是外推到从未观测过的状态**，而这正是数据驱动方法最脆弱的地方。

#### ❌ 谬误 6：「自然变率解释不了增温，因为科学家说的」

**为什么这是个弱论证**：Q6 的力量不在权威，而在**可证伪的定量检验**——太阳输出被卫星实测了 40 多年，它没有上升趋势。**答题时一定要给出这种"具体的、可检验的"排除论据，而不是只引用 IPCC。**

#### ❌ 谬误 7：「夏季降水量会减少」（对 Slide 19 的误读）

**为什么错**：讲义说的是 **"less frequent but more intense"**——**频次**下降、**强度**上升。**总量的变化方向并不是这句话说的内容。** 这两个量是独立的。

---

### 6.4 讲师明示的重点

按转写中的强调程度排序：

| # | 重点 | 讲师的信号 |
|---|---|---|
| **1** | **Week 11 复习课完全由学生提问决定** | 在开头和结尾**各强调一次**，明说"不提问就没幻灯片" |
| **2** | **Hindcasting** | 明说这"可能是你们的新概念"，并说这对预测模型来说"是个奇怪的概念" |
| **3** | **RCP 保证模式间输入一致（apples with oranges 比喻）** | 用同一个比喻**说了两遍** |
| **4** | **模式在气候尺度可信、年际尺度不可信** | 在 Slide 23 和 Slide 26 读图时**各强调一次**，且明说 "the other thing that you should be able to pull away from this plot is…" |
| **5** | **分辨率与 UK 农民的例子** | 跨三张幻灯片**用了三次** |
| **6** | **耦合与非线性反馈** | 用海洋 CO₂ outgassing 的具体例子完整演示了一遍 |
| **7** | **AI/ML 的未来角色** | 明说是"这几天刚加的"新内容 |
| **8** | **适应 ≠ 减缓** | 明说 "There is a **big difference** between adapting and mitigating" |
| **9** | **Slide 36 的 13 道样题** | 明说 "These are the sorts of questions I might ask in the exam" |

---

### 6.5 答题模板：三个高频题型

**📎 以下三个模板是我根据讲义与转写整理的答题结构，不是材料原文。**

#### 模板 A — 「解释模式为什么在某某尺度表现更好/更差」

```
1. 陈述事实：大陆尺度 ✅、30 年气候尺度 ✅、区域尺度 ❌、短时间尺度 ❌
2. 时间维度的物理理由：长期平均滤掉混沌天气噪声，剩下由能量收支
   决定的强迫响应；短尺度被初值敏感性（混沌）支配
3. 空间维度的物理理由：全球平均受全球能量平衡强约束；区域气候取决于
   环流形态的位置，误差更大
4. 技术理由：区域尺度接近或小于格距 → 落入参数化的势力范围
5. 证据：Slide 26 的 hindcast 图 —— 集合平均抓得住 20 年趋势，抓不住逐年起伏
```

#### 模板 B — 「解释模式如何把观测到的增温归因于人类」

```
1. 归因协议四步（Slide 27）：无强迫控制跑 → 与观测比对验证模式性能
   → 加强迫重跑 → 取差值
2. 强调第 2 步是合法性前提：必须先确认模式能正确模拟自然变率的幅度
3. 结果：只含自然强迫 ⇒ 与观测不符；加上人为强迫 ⇒ 与观测吻合
4. 论证形式：自然强迫【不充分】+ 人为强迫【才充分】= 排除法 + 充分性
5. 补充独立证据：太阳输出自 1978 年卫星观测无净增加（Q6）
6. 限定：区域尺度与极端事件的归因仍有较大不确定性（Slide 28）
```

#### 模板 C — 「讨论气候模式的主要不确定性」

```
1. 分类框架：情景不确定性 / 模式不确定性 / 内部变率（📎 本笔记补充的框架）
2. 具体来源（Slide 25 六条）：网格尺寸、大气层数、区域响应、
   自然变率、云的表征、降水参数化
3. 深挖两个最大的：
   - 云 —— 同时造成增温与降温，小尺度过程必须参数化（Q2）
   - 气溶胶 —— 直接效应 + 云反照率效应，冷却量级仍未定（Q2、Q5）
4. 观测侧的根源：地表观测密集，海洋与高空稀疏（Slide 28、Q7、Q8）
5. 结构性缺失：并非所有循环都被纳入，如氮循环（Slide 28）
6. 算力约束：一次模拟数周 ⇒ 限制集合规模与情景数量
7. 改进途径：更高分辨率 + 更好观测（尤其海洋）+ AI/ML（Q2、Q7）
```

---

## 七、本周术语表

| 中文 | English | 一句话释义 |
|---|---|---|
| 全球气候模式 | Global Climate Model / General Circulation Model (GCM) | 用物理方程在计算机上数值求解地球气候系统演化的程序 |
| 地球系统模式 | Earth System Model (ESM) | 在物理气候模式之上再加入化学、生物地球化学循环的耦合模式 |
| 气候 | Climate | 长时期（如 30 年）内的平均天气 |
| 天气 | Weather | 某地在逐时或逐日尺度上经历的大气状况 |
| 辐射强迫 | Radiative Forcing | 对地球能量收支的外部扰动，单位 W m⁻²；讲义称其为气候模式的核心概念 |
| 耦合 | Coupling | 让不同子模式（大气、海洋等）在运行中互相交换信息，从而模拟跨组件反馈 |
| 耦合器 | Coupler | 地球系统模式架构中央的接口模块，所有子模式之间的信息交换经它中转 |
| 大气模式 | Atmosphere Model | 模拟大气动力学与能量传输的子模式 |
| 海洋模式 | Ocean Model | 模拟海洋环流与热力学的子模式 |
| 化学模式 | Chemistry Model | 模拟大气气体与气溶胶（含污染物与温室气体）相互作用的子模式 |
| 生物圈模式 | Biosphere Model | 模拟陆地植被、生态系统与生物地球化学循环的子模式 |
| 冰冻圈模式 | Cryosphere Model | 模拟冰盖、冰川、积雪、冻土动力学的子模式 |
| 冰冻圈 | Cryosphere | 地球系统中所有冻结水的部分：冰盖、冰川、海冰、积雪、冻土 |
| 生物圈 | Biosphere | 地球上所有生物及其栖息环境构成的圈层 |
| 海冰 | Sea Ice | 海水冻结形成的冰，影响反照率与海洋环流 |
| 陆面 | Land Surface | 模式中表征陆地反照率、水文、能量交换的组件 |
| 三维网格 | 3D Grid | 把地球（含大气与海洋）离散成立方体格点的空间划分方式 |
| 格点/格子 | Grid Box / Grid Cell / Cube | 三维网格中的单个立方体，模式在其中计算所有物理过程 |
| 分辨率 | Resolution | 网格的精细程度；含水平、垂直、时间三个维度 |
| 水平分辨率 | Horizontal Resolution | 格点的水平尺度（km）；早期 GCM 为 250–600 km |
| 垂直层 | Vertical Levels / Atmospheric Levels | 模式在垂直方向上的分层数；HadCM3 为大气 19 层、海洋 20 层 |
| 时间分辨率 | Time Resolution | 模式推进的时间步长；转写独有的第三个分辨率维度 |
| 参数化 | Parameterisation | 用格点尺度变量估计小于格距的次网格过程之净效应的经验方法 |
| 次网格过程 | Sub-grid Process | 空间尺度小于模式格距、无法直接解析的过程，如云、湍流、对流 |
| 后报/回报 | Hindcasting | 让模式模拟已经发生的过去气候，与观测比对以检验模式可靠性 |
| 预报/预测 | Forecasting | 预测未来的气候状态 |
| 预估 | Projection | 条件性的未来推演（"若某情景成立，则……"）；气候界的标准用词 |
| 集合 | Ensemble | 多次模拟的集合，用于表征不确定性 |
| 集合平均 | Ensemble Mean | 集合中所有成员的平均，代表强迫响应；不代表任一次具体实现 |
| 多模式集合 | Multi-model Ensemble | 由不同机构开发的不同模式组成的集合，反映模式结构不确定性 |
| 模式间离散度 | Inter-model Spread | 不同模式对同一情景给出结果的差异范围 |
| 代表性浓度路径 | Representative Concentration Pathway (RCP) | 描述 21 世纪温室气体排放/浓度、空气污染物排放与土地利用的四条标准路径；编号为 2100 年辐射强迫（W m⁻²） |
| RCP2.6 | RCP2.6 | 严格减缓情景，目标是把增温 likely 控制在 2 °C 以下 |
| RCP4.5 / RCP6.0 | RCP4.5 / RCP6.0 | 两个中间情景 |
| RCP8.5 | RCP8.5 | 极高温室气体排放情景 |
| 基线情景 | Baseline Scenario | 无额外减排努力的情景；落在 RCP6.0 与 RCP8.5 之间 |
| 共享社会经济路径 | Shared Socioeconomic Pathway (SSP) | AR6 使用的情景框架，把社会经济故事线与辐射强迫水平组合（讲师口头使用，讲义未讲） |
| 负排放技术 | Negative Emission Technologies | 从大气中主动移除 CO₂ 的技术；转写独有，RCP2.6 的实现前提 |
| 归因 | Attribution | 把观测到的气候变化定量分配给特定驱动因子的科学过程 |
| 自然气候变率 | Natural Climate Variability | 由海洋环流、太阳活动、火山等自然过程引起的气候波动 |
| 人为气候变化 | Anthropogenic Climate Change | 由化石燃料燃烧、毁林、工业排放等人类活动引起的气候变化 |
| 内部变率 | Internal Variability | 气候系统自身的混沌涨落，如 ENSO |
| 厄尔尼诺–南方涛动 | El Niño–Southern Oscillation (ENSO) | 热带太平洋的海气耦合振荡，可驱动全球平均温度数个十分之一度的年际变化 |
| 拉尼娜 | La Niña | ENSO 的冷位相 |
| 正反馈 | Positive Feedback | 放大初始扰动的反馈环，如冰-反照率反馈、海洋 CO₂ 释放反馈 |
| 负反馈 | Negative Feedback | 抑制初始扰动的反馈环 |
| 冰-反照率反馈 | Ice-Albedo Feedback | 升温→冰雪融化→反照率下降→吸收更多辐射→进一步升温的正反馈 |
| 反照率 | Albedo | 地表或云对太阳辐射的反射比例 |
| 米兰科维奇循环 | Milankovitch Cycles | 地球轨道参数的周期性变化，驱动冰期–间冰期旋回（Week 2 内容，本周作为例子出现） |
| 气溶胶 | Aerosol | 悬浮于大气中的固态或液态微粒 |
| 气溶胶直接效应 | Aerosol Direct Effect | 气溶胶粒子本身散射或吸收入射太阳辐射 |
| 云反照率效应 | Cloud Albedo Effect | 气溶胶作为云凝结核改变云滴数与粒径，从而改变云的反照率、寿命与降水率（即间接效应） |
| 硫酸盐 | Sulphate | 大型火山喷发注入平流层的主要气溶胶成分 |
| 平流层 | Stratosphere | 对流层之上的稳定层结大气层；气溶胶在此寿命长（约 1–2 年） |
| 对流层 | Troposphere | 最底层大气；有云与降水，气溶胶寿命短 |
| 对流层臭氧 | Tropospheric Ozone | 非直接排放，由光化学反应生成的二次污染物兼温室气体 |
| 箱模式 | Box Model | 把一个空间区域视为内部充分混合的"箱子"，追踪其中物种质量收支的模式 |
| 源 | Source | 使箱内物种质量增加的通量：排放 E、化学生成 P、流入 F_in |
| 汇 | Sink | 使箱内物种质量减少的通量：化学损耗 L、沉降 D、流出 F_out |
| 排放 | Emission (E) | 物种被直接排入箱内的通量 |
| 化学生成 | Chemical Production (P) | 物种在箱内由化学反应生成的通量 |
| 化学损耗 | Chemical Loss (L) | 物种在箱内由化学反应消耗的通量 |
| 沉降 | Deposition (D) | 物种从大气移除到地表的通量，含湿沉降与重力沉降 |
| 湿沉降 | Wet Deposition | 物种被并入降水而落地的移除路径 |
| 重力沉降 | Gravitational Settling | 颗粒物在重力作用下沉降的移除路径 |
| 流入 / 流出 | Inflow (F_in) / Outflow (F_out) | 物种在相邻箱之间的输运通量 |
| 寿命 / 滞留时间 | Lifetime / Residence Time (τ) | 箱内存量除以总去除率；决定物种的时空分布均匀程度（📎 公式为本笔记补充） |
| 充分混合 | Well-mixed | 箱内浓度无空间梯度的假设；也指 CO₂ 等长寿命气体在全球分布均匀 |
| 羟基自由基 | Hydroxyl Radical (OH·) | 大气主要氧化剂，甲烷的主要去除途径（📎 本笔记补充） |
| 政府间气候变化专门委员会 | Intergovernmental Panel on Climate Change (IPCC) | 联合国下属的气候变化科学评估机构 |
| 第一次评估报告 | First Assessment Report (FAR) | 1990 年发布，首次全面评估气候变化科学、影响与减缓 |
| 第二次评估报告 | Second Assessment Report (SAR) | 1995 年发布，为 1997 年《京都议定书》提供依据 |
| 第三次评估报告 | Third Assessment Report (TAR) | 2001 年发布，评估各部门影响并推动国际气候谈判 |
| 第四次评估报告 | Fourth Assessment Report (AR4) | 2007 年发布，为后京都协议奠基，聚焦 2 °C 目标 |
| 《京都议定书》 | Kyoto Protocol | 1997 年通过的国际减排协议 |
| 哈德利中心 | Hadley Centre | 英国气象局的气候预测与研究中心 |
| HadCM3 | Hadley Centre Third Coupled Model | 哈德利中心第三代耦合模式，整合大气、海洋、海冰、陆面；大气 19 层、海洋 20 层 |
| 工作组三 | Working Group III (WGIII) | IPCC 负责减缓的工作组 |
| 人工智能 | Artificial Intelligence (AI) | 用于分析大规模复杂气候数据集的计算方法 |
| 机器学习 | Machine Learning (ML) | 从数据中学习输入–输出映射的方法；擅长非线性与加速，但不天然满足物理约束 |
| 混合建模 | Hybrid Modelling | 用机器学习补充物理模式（如改进参数化）的未来建模范式 |
| 可解释性 | Interpretability | 能否追溯模型给出某结果的原因；AI 模式的主要挑战之一 |
| 数据偏差 | Data Bias | 训练数据本身的系统性偏差，会被机器学习模型继承 |
| 物理一致性 | Physical Consistency | 模拟结果是否遵守守恒律等物理定律 |
| 减缓 | Mitigation | 针对气候变化的**原因**——减少温室气体排放或增加吸收 |
| 适应 | Adaptation | 针对气候变化的**后果**——降低已发生或将发生影响造成的损害 |
| 地球工程 | Geoengineering | 主动大规模干预气候系统的技术（Week 9 客座讲座主题） |
| 海洋云增亮/增白 | Marine Cloud Brightening / Whitening | 向海洋低云喷洒气溶胶以提高云反照率、延长云寿命的地球工程方案 |
| 热浪 | Heatwave | 持续的异常高温事件 |
| 干旱 | Drought | 降水不足与蒸发加剧导致的水分亏缺 |
| 野火 | Wildfire | 植被火灾；受温度与降水格局变化影响 |
| 极端天气事件 | Extreme Weather Event | 飓风、台风、气旋等；暖海温为其提供更多能量 |
| 二氧化碳当量 | CO₂-equivalent (CO₂-eq) | 把各种温室气体按增温潜势折算为 CO₂ 的统一单位 |
| 吉吨 | Gigatonne (Gt) | 10⁹ 吨；温室气体年排放的常用单位 |
| 工业化前 | Pre-industrial | 温度目标的参照基准期 |
| 气候行动追踪 | Climate Action Tracker | Slide 32 情景图的数据来源机构 |
| 三支柱途径 | Three Pillar Approach | 外场观测 + 实验室研究 + 模式，三者协同支撑气候科学（转写独有） |
| 反事实实验 | Counterfactual Experiment | 模拟"若没有某个强迫会怎样"的对照实验，归因的基础 |

---

## 附：材料勘误表

| 位置 | 材料原文 | 问题 | 更正 |
|---|---|---|---|
| **讲义 Slide 10 vs 答案 deck Slide 14（Q4）** | 讲义："Climate models calculate the physical interactions between **four components: Atmosphere / Land / Ocean / Sea ice**"；答案 deck："GCMs consist of **five major components: Atmosphere / Cryosphere / Chemistry / Ocean / Biosphere**" | **讲义与答案 deck 的组件清单数目与内容都不一致**——这是本周最实质的一处对不上 | 二者分别描述**经典物理气候模式**与**现代地球系统模式**；答题按答案 deck 的**五组件**，并说明其由早期四组件演化而来（见笔记 B3 节） |
| **讲义 Slide 4** | "Differentiate between natural climate variability and **antheropogenic** climate change" | 拼写讹误 | 应为 **anthropogenic** |
| **讲义 Slide 27** | "the consequent climate change arising **form** that forcing factor" | 拼写讹误 | 应为 **from** |
| **讲义 Slide 34** | "What could limit global warming to **1.5oC**?" | 度数符号未正确排版 | 应为 **1.5 °C** |
| **讲义 Slide 24** | "The RCPs are consistent with the wide range of scenarios in the literature as assessed by **WGIII5**" | 文末的 "5" 应为脚注标号，被误并入 "WGIII" | 应读作 **WGIII**（IPCC 第三工作组），"5" 是引用标记 |
| **讲义 Slide 6（标题）vs 转写** | 讲义标题："Measurements: **last 6 million years**"；转写讲师描述同一张图："the Earth system changes over the **last 65 to 70 million years**" | **量级相差约一个数量级**（600 万年 vs 6500–7000 万年） | 该图内容按讲师口述为 **65–70 Myr**（新生代尺度）；**标题的 "6 million years" 与图不符**，请对照原 pptx 核实 |
| **讲义 Slide 22** | 只列到 **AR4（2007）** 为止 | **内容缺口**：未提及 AR5（2013–14）与 AR6（2021–23）。而 **RCP（Slide 24 的主题）恰恰出自 AR5**，且 unit spec 明确说本课主教材是 **AR6 综合报告** | 不属于事实错误，但为不完整；完整序列为 FAR(1990) → SAR(1995) → TAR(2001) → AR4(2007) → **AR5(2013–14)** → **AR6(2021–23)** |
| **讲义 Slide 28** | "**Cause and effect not finally established**" | 表述过于绝对，与全课其余部分（Slide 26 "makes us confident"、答案 deck Q6 "it is scientifically established that human activities have been the primary driver"）以及 IPCC 的定论相冲突，属**材料内部自相矛盾** | 应理解为「**某些具体因果链（尤其区域尺度与极端事件）**尚未完全确立」，而非整体归因未确立；答题时勿据此写"因果关系尚不明确" |
| **讲义 Slide 34** | 页面标注 "**WEEK 9**"，内容为「什么能把增温限制在 1.5 °C」（减缓措施） | 按 Slide 2 的课程地图，**Week 9 = Effects of Climate Change: Case Studies**，减缓是 **Week 10** | 但转写中讲师说 Week 9 将请客座讲者讲**地球工程（目标限制在 1.5 °C）**，与该标注可对应；**以转写中讲师的最新安排为准** |
| **讲义 Slide 32（OCR）** | "Annual anthropogenic **CO, et**"、"Annual emissions (**GtCO,/yr**)"、"— **RCPAS**" | OCR 讹误：下标与字符识别错误 | 应为 **CO₂-eq**、**GtCO₂/yr**、**RCP4.5** |
| **讲义 Slide 32（OCR）** | WGIII 情景类别列表："1 >1000 / © 720-1000 / 580-720 / 1) 530-580 / i 430-530 / 1) 430-480" | OCR 讹误：**类别区间有重复与缺项**（430–530 与 430–480 重叠；缺 480–530、580–650、650–720 等），列表不可信 | **该分类清单不可作为引用依据**，须对照原 pptx 或 IPCC AR5 WGIII 原图 |
| **讲义 Slide 32（OCR）** | "Global greenhouse gas emissions and warming scenarios **Qaaveid**"、"in **Data**"、"**0G.** 2.8-3.2°C" | OCR 讹误 | 分别应为图题、"**Our World in Data**"、以及 "**Current policies** 2.8–3.2 °C"（"0G." 为纵轴刻度 "0 Gt" 与文字粘连） |
| **讲义 Slide 32** | "Data source: Climate Action Tracker (based on national policies and pledges **as of December 2019**)" | **数据已过时**（本课为 2026 年授课），各国政策与承诺自 2019 年以来已有变化 | 图上的 2.8–3.2 °C / 2.5–2.8 °C 等数字应视为 **2019 年时点的估计**；引用时须注明年份 |
| **答案 deck Slide 3、Slide 4** | 两页均标注 "**Brief Answer**"，但页面**只有图，没有任何文字答案** | Discussion 第一问（"what variables would you absolutely need to include?"）在答案 deck 中**没有文字解答**，只能靠读图 | 本笔记已在第三节图 M、图 N 与第五节 5.1 尽力还原；**精确内容须对照原 pptx** |
| **答案 deck Slide 3（OCR）** | "**GOOO**"、"Aerosols and / atmospheric chemistry **biogeochemistry** / Radiative transfer **Mixed layer processes** / Turbulence and **Deep ocean circulation**" | OCR 把**多栏排版按行拼接**，导致大气栏与海洋栏的条目互相穿插、圈层归属错乱 | 本笔记第三节图 M 已按语义重排，但**归属有推断成分**；引用请对照原件 |
| **答案 deck Slide 4（OCR）** | "**NuOy Ar**"、"**H,0,CO,,CH,N,0, 0,** etc"、"**Yetanle Activity**"、"**ca-Ocsan Coup**"、"**iia Radiation**"、"‘Changes in the Atmosphere" | OCR 讹误极多，下标全部丢失 | 分别应为 **N₂, O₂, Ar**；**H₂O, CO₂, CH₄, N₂O, O₃**；**Volcanic Activity**；**Ice-Ocean Coupling**；**Terrestrial Radiation**；**Changes in the Atmosphere** |
| **答案 deck Slide 16（Q5）** | "**Figure to the right shows key examples too**" | **该图在 md 转换结果中不存在**（未被提取） | 须回看原 pptx；本笔记不对该图内容作任何推测 |
| **答案 deck Slide 16（Q5）** | "Smaller eruptions also emit large concentrations of aerosols **in to** the troposphere" | 拼写讹误 | 应为 **into** |
| **答案 deck Slide 18（Q6）** | "Key greenhouse gases, carbon dioxide, methane, and nitrous oxide have risen significantly **since due to** human activities" | **缺漏词**——"since" 后面的时间基准（应为"工业革命以来"或类似）丢失 | 应为 "…have risen significantly **since the industrial revolution** due to human activities"（补词为推断，原文缺失） |
| **答案 deck Slide 10（Q2）** | "This is a very active **are** of research at the University" | 拼写讹误 | 应为 **area** |
| **答案 deck Slide 10（Q2）** | "maybe the use of artificial intelligence to **refine operations**" | 用词含糊，与上下文（改进模式）不完全贴合 | 疑为 "refine **parameterisations**" 或 "refine **simulations**"；**无法确证，按原文理解为"改进模式运作"** |
| **答案 deck Q2 vs 讲义 Slide 25** | 答案 deck 只列了三条不确定性来源（云、气溶胶、区域响应）；讲义 Slide 25 列了六条（另有**网格尺寸、大气层数、自然变率、降水参数化**） | 答案 deck 覆盖不全（其自己写了 "include but are not limited to"，属自觉的限定） | 答题时应补上讲义 Slide 25 的其余各条 |
| **转写** | "welcome to the second half… moving now into the **second component of the tool element** of this course"（多处） | 语音转写讹误 | 应为 **taught element（授课模块）** |
| **转写** | "There are **36** climate models that are recognised and used by the IPCC" vs 后文 "the IPCC brings together and aggregates around **35 to 40** global climate models" | **同一转写内前后数字不一致** | 两者量级一致；答题写 **约 35–40 个** 最稳妥 |
| **转写** | "The first real true global climate models were introduced in the **early 1990s** and incorporated into the **first IPCC report**" | 与讲义 Slide 22 略有张力：**FAR 出版于 1990 年**，不属于"early 1990s"之后 | 应理解为「首批真正的 GCM 出现于 1990 年前后，并被纳入 FAR」；**FAR 的年份以讲义 Slide 22 的 1990 为准** |
| **转写** | "that can be due to a **melancholic cycle**, for example" | 语音转写讹误 | 应为 **Milankovitch cycle（米兰科维奇循环）** |
| **转写** | "the effect that different **albinos** have over land" | 语音转写讹误 | 应为 **albedos（反照率）** |
| **转写** | "sea ice extent, which obviously affects the **reef activity**" | 语音转写讹误 | 应为 **reflectivity（反射率）** |
| **转写** | "the **Hadkem III** which is the UK's Met Office Global Climate Model" | 语音转写讹误 | 应为 **HadCM3**（讲义 Slide 20 拼写正确） |
| **转写** | "different **thermophores dynamics** within global climate models" | 语音转写讹误 | 结合上下文（冰冻圈模式）应为 **thermodynamics（热力学）** 或 **permafrost dynamics（冻土动力学）**；**无法确证具体是哪一个** |
| **转写** | "not all **biozoonochemical** cycles are completely incorporated" | 语音转写讹误 | 应为 **biogeochemical（生物地球化学）** |
| **转写** | "the nitrogen cycle might have effects on **abstract chemistry**" | 语音转写讹误 | 应为 **atmospheric chemistry（大气化学）** |
| **转写** | "this is based on the principle that **aggenic** greenhouse gas emissions are driven by…" | 语音转写讹误 | 应为 **anthropogenic（人为的）** |
| **转写** | "there's many different **man masses** which was not captured by the FAR" | 语音转写讹误 | 应为 **land masses（陆块）** |
| **转写** | "The challenge here is **interoperability** of these models" | 与讲义 Slide 30 的 "model **interpretability**" 对不上 | 应为 **interpretability（可解释性）**——以讲义为准 |
| **转写** | "This gives us a **ready to do the confident standpoint**" | 语音转写严重讹误，语义不完整 | 结合上下文疑为 "a **relatively confident** standpoint"；**无法确证** |
| **转写** | "we can use **icicle data** to extrapolate out to 800,000 years" | 语音转写讹误 | 应为 **ice core data（冰芯数据）** |
| **转写** | "we're now in a place where we can almost start to think about simulating this on a **metre by metre** spatial resolution" | **量级存疑**：米级分辨率**不是全球气候模式的常规能力**；讲师自己加了 "almost start to think about" 与 "for different **atmospheric simulation models**" 两处限定 | 应理解为**特定的高分辨率大气模拟工具**（非全球 GCM）；全球 GCM 业务分辨率仍在**数十至 100 km** 量级，区域降尺度在 **1–12 km** 量级 |
| **转写** | "in the south you might expect the frequency to change by **enormous percent**, 50 to 60 percent" | 语句不完整 | 应为 "by **an enormous percentage**"；数值 **50–60%** 按原文保留 |
| **转写** | "**Jessica Gerwood** will come in and talk about… **marine cloud whitening**" | 人名为语音转写，拼写**不确定**；"marine cloud whitening" 与学界通用的 **marine cloud brightening** 用词不同 | **讲者姓名请以 Canvas 或正式课程通知为准，本笔记不猜测拼写**；技术名称通用写法为 **Marine Cloud Brightening (MCB)** |
| **转写** | "methane which readily reacts with **different oxygens** in the atmosphere" | 表述含糊，未指明具体氧化剂 | 📎 实际主要去除路径为与**羟基自由基 OH·** 反应；**此更正为背景补充，材料未给出** |
| **转写 vs 讲义 Slide 24** | 转写使用 **SSP** 命名（"SSP 2 to 4.5"、"SSP 1 to 2.6"）；讲义 Slide 24 全篇只用 **RCP** | **两代情景框架被口头混用**（RCP 出自 AR5，SSP 出自 AR6） | **考试以讲义的 RCP 为准**；SSP 的含义见笔记 A5 节的 📎 补充 |
| **转写头部** | "'EART21202 - 19-Mar', automated transcript / **03/08/2026**" | 该日期为**转写导出日期**，不是授课日期 | 授课日期为 **2026 年 3 月 19 日**（与讲义 Slide 2 一致）；不属于错误，仅提示勿误读 |
| **unit spec《(EART21202) Global Climate Change.md》Syllabus** | "**Week 5: Climate models**"、"Week 7: Natural climate variability"、"Week 8: Other anthropogenic impacts on climate"、"Week 9: Climate change adaptation" | **与本年度实际授课顺序完全不对应**（实际：Week 2 = Natural climate variability；Week 4 = Anthropogenic impacts；Week 5 = Evidence Base；**Week 7 = Climate Models**；Week 8 = Adaptation） | 以讲义 Slide 2 的 **2026 年课程安排**为准；unit spec 的 syllabus 已过时 |
| **unit spec 教师表** | Unit coordinator: **Thomas Choularton / Martin Gallagher** | 与本周实际授课教师不一致 | 本周授课与讲义署名均为 **Dr Thomas Bannan**（Thomas.Bannan@Manchester.ac.uk）；unit spec 的教师信息可能未更新 |
| **unit spec 评估表** | "Test / 30% / **Week 6**" | 与讲义 Slide 2 一致（Week 6 为期中测验周），**不属于错误** | 仅提示：讲义 Slide 2 给的日期是 **10th March**，与本笔记的周号对照体系一致 |



