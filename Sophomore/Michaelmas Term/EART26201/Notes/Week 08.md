# EART26201 Principles of Geochemistry — Week 08 学习笔记

> 本周材料：Lecture 讲义 `lecture 8 buffering alkalinity and silica v2-1.md`、课堂录音转写 `EART26201 - 24-Nov-transcript.md`（约 6,920 词，本课最长）、`lecture 8 quiz answers 2024.md`（OCR 质量差，仅作线索）、以及 Practical 文件夹下的全课通用实验手册（限定章节读取，详见第五节）。
> 讲师：Greg Holland（Unit coordinator）。课后阅读指定：**Misra, Chapter 7.5–7.7**。

---

## 一、本周主题

本周主题是 **缓冲、碱度与硅（buffering, alkalinity and silica）**，落在本课四大骨架的第三块——**酸碱、溶解度与氧化还原**。

**在全课中的位置。** 本课的四大块是：热力学与相图（W04–W05）／反应动力学与扩散（W06）／酸碱溶解度与氧化还原（W07–W10）／放射性与稳定同位素（W03、W11）。本周是第三块的第二讲：W06 处理离子在溶液中的行为（活度、离子强度），W07 处理**溶解度积与金属–配体络合**（老师在转写里明确回顾："a bit like last week when we talked about having a solid in an equilibrium constant with the solubility product. That was essentially one because it was a solid"），本周则把视角从"某个矿物能溶多少"转向"**溶液本身如何抵抗 pH 变化**"，也就是从溶解度问题升级为**体系的缓冲能力问题**。

**本周的三条线索。** 老师在开场就坦白说明了这一讲的结构（transcript 105–127）：

> "This is one of those lectures where I've just kind of lumped three things sorted together... because neither of them are kind of big enough on their own... I just wanted to say a little bit about essentially **carbonates and silica in solution**. This is what it amounts to."

也就是说本周实质上是**三个半独立的模块拼接**：

1. **酸碱基础的复习 + pH 缓冲与碱度**（碳酸盐体系）——衔接 Lecture 1 的 Ka/pKa/pH；
2. **硅的溶解度与 pH 依赖**（硅酸的分步解离）——衔接 W07 的溶解度思路；
3. **矿物稳定图（mineral stability diagram）**——把平衡常数对数化成直线，用 K-Al-Si-H₂O 体系演示流体–岩石反应路径。

这三块的**共同方法论**其实是同一个：写平衡反应 → 写 K → 取对数 → 得到 pH / 浓度之间的定量关系。理解了这一点，本周的内容就不是"拼盘"，而是同一把工具的三次应用。

**与 Practical 的绑定。** 老师在开头就点明本周实验课的内容（transcript 94–103, 146–156）："this week we'll be doing some experiments to do with buffering and alkalinity… We'll be doing acid based titrations."——即实验手册中的 **EXPERIMENT 2: BUFFERS AND INDICATORS**。讲义中"酸度可用强碱滴定测定、碱度可用强酸滴定测定"这句话，直接就是实验的操作定义。

**对下游课程的支撑。**

📎 背景补充：以下下游关联属课程体系层面的说明，本周材料本身未提及。
- **EART23202 地层记录（碳酸盐成岩）**——本周的 CaCO₃(s) + H⁺ ⇌ Ca²⁺ + HCO₃⁻ 与碳酸种态平衡，是碳酸盐溶解／胶结／压溶等成岩过程的化学底座；本周讲的 chert（燧石）成因（非晶质硅凝胶脱水结晶）也是成岩学直接要用的。
- **EART21202 全球气候变化（海洋碳循环、海洋酸化）**——本周的 CO₂ ⇌ H₂CO₃ ⇌ H⁺ + HCO₃⁻ ⇌ 2H⁺ + CO₃²⁻ 总方程、海水 pH 从工业化前 8.2 降到现今 7.9、以及"缓冲以消耗 CaCO₃ 为代价"的机制，就是海洋酸化章节的化学核心。
- **W09 之后的氧化还原与风化**——本周的矿物稳定图方法（对数化 K → 直线 → 相图）与 W10 Eh–pH 图的构建逻辑完全一致，本周是它的"预演"。

---

## 二、核心概念

### 2.1 酸度与碱度：操作性定义

讲义给的是**可操作**的定义（这一点很重要，它直接对应实验室做法）：

- **酸度（acidity）**：溶液**给出质子的能力**（capacity to donate protons）。测定方法：用**强碱**（如 NaOH）滴定。
- **碱度（alkalinity）**：溶液**接受质子的能力**（capacity to accept protons）。测定方法：用**强酸**（如 HCl）滴定。

老师在课上把碱度描述为酸度的镜像："Similarly alkalinity you can think of it as the opposite."

**为什么酸度重要？** 讲义与课堂都强调：高酸度使矿物和金属更容易溶解，因而常伴随高 **TDS（total dissolved solids，总溶解固体）**，导致水不适合饮用。老师补充说这是**环境问题的驱动因素**："Where you have acid waters you tend to get what's called high total dissolved solids. Which means that unless you clean that water up it's not suitable to drink."

### 2.2 强弱 ≠ 浓度（本周第一个高频易错点）

- **强酸**：更容易释放 H⁺，**解离更完全**；**强碱**：更容易释放 OH⁻，解离更完全。
- 讲义原文用了全大写强调：**"Remember that strength DOES NOT EQUAL concentration."**
- 老师的展开（transcript 219–238）非常清楚：你可以有**低强度但大量**的酸，也可以有**弱酸但高浓度**；两者可能给出**相同的 H⁺ 总量，但机制不同**。

### 2.3 解离常数与分步解离

任何酸在水中的反应写作：

```
HA + H2O ⇋ H+ + A- + H2O
```

（讲义原式，OCR 有错位；本质就是 HA ⇌ H⁺ + A⁻）

- 平衡常数记作 **K**，对酸记 **Ka**、对碱记 **Kb**。
- **pKa = −log Ka**（Lecture 1 引入）。因为是负对数，**pKa 越低 = 酸越强**。
- **多质子酸分步解离**，每一步有各自的 pKa。课上举的例子是**磷酸（三个 H⁺，三步、三个 K）**："There's three H plus here. They don't all go in one step. There's actually an equilibrium constant for each stage."
- 老师明确提示这一点**在 20 分钟后讲硅时要用到**——硅酸也是分步解离的，必须逐步考虑。
- 讲义提示：Ka 与 Kb 的具体数值查 **Faure 书里的表**。

### 2.4 水的自解离与 pH 标度

```
H2O ⇋ OH- + H+
```

- 约定 **[H₂O] = 1.0**（水是溶剂，活度取 1；与 W07 中固体活度取 1 是"不同理由、同一处理"）。于是 **Kw = [H⁺][OH⁻] = 1 × 10⁻¹⁴**（25 °C，1 atm），故 **[H⁺] = [OH⁻] = 1 × 10⁻⁷ mol/L**（详见 3.2）。
- 判据：[H⁺] < 10⁻⁷ → pH > 7 → **碱性 basic**；[H⁺] > 10⁻⁷ → pH < 7 → **酸性 acidic**。
- **温度依赖**：Kw 随 T 变，"中性 pH"随之变。讲义给 **0 °C 时纯水 pH = 7.47**。
- **大多数天然水的 pH 在 5–9 之间**（讲义原文）。

### 2.5 pH 缓冲与缓冲容量

- 加酸或加碱**本应**改变 pH；但**某些溶液会抵抗这种变化**，因为溶解种态能**消耗掉**加入的 H⁺ 或 OH⁻。
- 能在加酸／加碱时维持 pH 的溶液叫 **pH 缓冲液（pH buffer）**。
- **缓冲容量（buffering capacity）**：该溶液在 pH 发生显著变化前**能消耗多少 H⁺ 或 OH⁻**。老师的口语版更形象："how many H plus ions or OH minus ions it can take up **before it actually gives up** and the pH changes."
- 老师补了一句讲义没有的：**所有天然水多少都有一点缓冲能力**，因为都含溶解离子；但**地球系统里最大的缓冲体是海水**。

### 2.6 海水的缓冲体系：CaCO₃–HCO₃⁻

- 海水含大量 **HCO₃⁻ 与 CaCO₃**，二者共同把海水 pH 维持在约 **7.9**（**工业化前为 8.2**）。
- 关键反应：

```
CaCO3(s) + H+ ⇋ Ca2+ + HCO3-
```

- 讲义强调海洋中**表层水与沉积物里悬浮的 CaCO₃ 颗粒实际上是"无限量"的**，任何多余的 H⁺ 都能被 CaCO₃ 的溶解缓冲掉。
- 老师补充的关键机制：真正做缓冲工作的是 **CaCO₃ 供给的 HCO₃⁻**，而 **HCO₃⁻ 是两性的（amphoteric）**——它**既能与 H⁺ 反应，也能与 OH⁻ 反应**，所以能双向工作（这是讲义上没有的重点，见第四节）。
- **代价**：CaCO₃ 是海洋生物（如浮游生物 plankton）造壳的材料。海洋酸化正在**降低钙化速率**——讲义原话是这些生物"effectively working against the gradient established in the above chemical reaction"，老师则直白地说，这些造壳生物"are actively being dissolved here by this process"。

### 2.7 碱度（alkalinity）的严格含义

- **定义**：溶液**中和／"缓冲"酸的能力**。
- 在多数天然水中，**碳酸根 CO₃²⁻ 与碳酸氢根 HCO₃⁻ 是最主要的阴离子**，因此 **总碱度（total alkalinity）≈ 碳酸盐碱度（carbonate alkalinity）**。
- 讲义给出的碳酸盐碱度定义式：

```
Calk = [HCO3-] + 2[CO32-] + [OH-] – [H+]
```

- 老师补充：偶尔 OH⁻ 有一点贡献（某些特定矿物会产 OH⁻），但**在全球质量平衡意义上，碱度就是由 HCO₃⁻ 和 CO₃²⁻ 产生的**。
- **碱度可以抬高 pH**。讲义给的机理链：

```
CaCO3(s) ⇋ Ca2+ + CO32-
CO32- + H2O ⇋ HCO3- + OH-
```

CO₃²⁻ 水解产生 **OH⁻（强碱）**，所以 CaCO₃ 溶解不仅能中和外来的 H⁺，在没有额外 H⁺ 时**还会让 pH 上升一点**。

📎 背景补充（**本周考试最容易混的一点**，讲义没有明说，务必分清）：
- **pH** 是 H⁺ 活度的负对数，是**强度量（intensity）**——它只告诉你"现在有多酸"。
- **碱度** 是**容量量（capacity）**——它告诉你"还能吃掉多少酸"。两者**互不决定**：一杯 pH = 8.2 的去离子水加一滴碱就到 8.2，但碱度几乎为零；海水同样 pH ≈ 8.1，碱度约 2.3 mmol/kg，抗酸能力天差地别。
- **DIC（dissolved inorganic carbon，溶解无机碳）= [CO₂(aq)] + [H₂CO₃] + [HCO₃⁻] + [CO₃²⁻]**，是**所有无机碳种态的物质的量之和**。碱度式里 CO₃²⁻ 前面有系数 **2**（因为它能接受 2 个质子），HCO₃⁻ 系数为 1，而 **H₂CO₃/CO₂ 完全不进碱度式**（它不能再接受质子）；DIC 式里则三者系数都是 1，且 CO₂ 也算。这就是**碱度 ≠ DIC** 的数学根源。
- 实际后果（对 EART21202 极重要）：**往海水里溶入 CO₂，DIC 增加、pH 下降，但碱度完全不变**（因为 CO₂ + H₂O → H⁺ + HCO₃⁻ 同时产生一个 H⁺ 和一个 HCO₃⁻，在 Calk 式里一加一减正好抵消）。反过来，**溶解 CaCO₃ 会使碱度增加 2 个当量、DIC 增加 1 个当量**。这条"碱度：DIC = 2:1"是海洋碳循环建模的基本规则。

### 2.8 碳酸体系总方程——"今天只带走一条式子"

老师明确说这是本讲最该记的东西（transcript 1135–1155）。讲义原式：

```
CO2 + H2O ⇋ H2CO3 ⇋ H+ + HCO3- ⇋ 2H+ + CO32-
```

- 注意：从 H₂CO₃ 走到 CO₃²⁻，**总共释放两个 H⁺**。
- **CO₂ 转化为碳酸 → pH 下降（H⁺ 增加）**。
- 老师的解读（这是理解海洋酸化的钥匙）：这条链的**两端各有一个"输入口"**——
  - **左端**：大气 CO₂ 输入，推动所有平衡**向右**走，使水变酸；
  - **右端**：CaCO₃ 溶解提供 CO₃²⁻ 输入，把所有平衡**推回左边**；
  - "**它们互相对抗，这场 CO₂ 与 CaCO₃ 之间的拉锯，就是全球碱度的故事。**"

### 2.9 碱度为什么重要

- **低碱度**的水在酸进入时会**快速改变 pH**。
- 对水生生物而言，碱度**保护它们免受快速／瞬时 pH 变化（"acid shock"，酸休克）**。
- 两大环境议题：**酸雨（acid rain）** 与 **海洋酸化（ocean acidification）**。老师加了时代注脚：他年轻时酸雨是头号环境议题，如今在某些地区仍是问题但已不如从前；**现在更大的问题是全球性的海洋酸化**。酸雨是**局地的、工业性的**过程，海洋酸化是**全球的**。

### 2.10 硅：非晶质硅、石英与硅酸

- **SiO₂（silica，硅／二氧化硅）** 可以是**非晶质（amorphous）**，也可以是多种**晶质**形态：**石英 quartz**（地壳最丰富矿物之一）、**方石英 cristobalite**、**鳞石英 tridymite**。
- **非晶质硅与水反应生成硅酸（silicic acid, H₄SiO₄）**；**石英几乎不反应**。
- **绝大部分硅酸来自常见铝硅酸盐（长石 feldspar、云母 mica）的风化**，而**几乎不来自石英本身的溶解**。
- 老师的口语补充：非晶质硅"就是一团 blob，完全没有晶体结构"。
- **chert（燧石）的成因**：当硅酸超过溶解度，先沉淀出**凝胶状（gelatinous）的非晶质硅**；随后在成岩压实中**水被慢慢挤出**，硅结晶为 **chert**。老师说："if you ever wonder what chert is, it's actually amorphous silica that's precipitated from water… it's squeezed all the water out."

### 2.11 硅的分步溶解与 pH 依赖

第一步（讲义给出）：`SiO2 + 2H2O ⇋ H4SiO4，K = 1.82 × 10⁻³`，每摩尔 SiO₂ 产一摩尔 H₄SiO₄，折合 **109 ppm** 的饱和浓度（换算见 3.8）。

- 但硅酸**还会继续分步解离**（H₄SiO₄ → H₃SiO₄⁻ → …），严格来说**溶液中的硅浓度必须把所有含 Si 离子加起来**。
- **pH = 7 时**，算出 [H₃SiO₄⁻] **比 H₄SiO₄ 低约 500 倍**，所以其他含 Si 离子**对溶解度没有贡献**——中性条件下只用第一步近似即可。
- **但 pH 一升高就不成立**：pH 7 → 8，[H⁺] 降 10 倍，**[H₃SiO₄⁻] 升高一个数量级**。
- 讲义结论：**到 pH = 9（多数天然水环境的上限）为止溶解度几乎全由 K₁ 决定；pH 更高时随后续 K 项变得重要而呈指数增长。**
- 溶解度**也受温度影响**（方程见 Misra），但老师明确指出：**温度轴是线性、pH 轴是对数，pH 的影响远大于温度**。

### 2.12 硅的沉淀与"pH 微降即沉淀"

- 含硅酸的**碱性溶液 pH 稍降**即可能过饱和并析出非晶质硅。讲义算例：**pH 从 8.5 降到 8.4（仅 0.1 单位），析出 1.37 mg L⁻¹ 硅。**
- 看似微小，但天然环境涉及**大体积地下水与高流速**，因此这是**地球系统中搬运硅的极高效方式**；老师补充工业上也须防范硅在不该沉淀处结垢。
- **石英不是硅酸的重要来源**：**石英溶解度 = 0.0059 g L⁻¹ = 5.9 ppm**，比**非晶质硅 109 ppm 低约 20 倍**。

### 2.13 天然水中的硅：两个"反直觉"

（讲义引 Misra: Table 13.7）

1. **河水相对石英是过饱和（supersaturated）、相对非晶质硅是不饱和（undersaturated）。** 按平衡化学，河里本该到处析出石英——但并没有。**原因是动力学（kinetics）**：石英的沉淀反应速率极慢。这是本周与 W06 动力学的直接呼应。
2. **海水的溶解硅含量比河水还低**——尽管海水更碱性（pH ≈ 8，硅在碱性下更易溶），而河水更接近微酸性的雨水（pH ≈ 6）。**这与预期完全相反。**
   **答案：生物摄取。硅藻（diatoms）等微体生物用硅造壳**，把海水中的溶解硅抽走。讲义在 Summary 里的说法是："In the oceans, precipitation of silica is **biologically mediated**（生物介导）。"这与 CaCO₃ 被造壳生物利用是同一类逻辑。

### 2.14 K-Al-Si-H₂O 体系与矿物稳定图

核心示例反应（微斜长石 → 高岭石）：

```
2KAlSi3O8 (microcline) + 2H+ + 9H2O ⇋ 2K+ + 4H4SiO4 + Al2Si2O5(OH)4 (kaolinite)
```

- 对该反应写 K，两边取对数后可整理成**直线方程**：以 **log[H₄SiO₄] 为 x 轴**、**log([K⁺]/[H⁺]) 为 y 轴**，则该式形如 **y = mx + c**，**斜率 m = −2，y 截距 = log K / 2**。
- 完整体系还需考虑 **K-长石（K-feldspar/microcline）、高岭石（kaolinite）、白云母（muscovite）、三水铝石（gibbsite）、非晶质硅** 之间的一系列反应（讲义编号 1–6）。**反应 1–4 都消耗 H⁺、释放 K⁺ 与硅酸。**
- **矿物稳定图的三个用途**（老师归纳，见第四节）：给定溶解离子浓度时**哪个矿物稳定**；**哪两个矿物可以共存**（边界线上）；以及**预测流体–岩石体系的演化路径**。
- **X1 → X4 演化路径**（本周最需要动手复现的推理，详见第四节）。

---

## 三、公式与图表

### 3.1 酸解离常数

```
HA ⇋ H+ + A-        Ka = [H+][A-] / [HA]
pKa = -log Ka
```

- **符号**：[ ] 为浓度（严格应为活度）；Ka 单位在稀溶液惯例下取 mol/L（实验手册给醋酸 **Ka = 1.82 × 10⁻⁵ mol/L**）。
- **适用条件**：单步解离；多质子酸须逐级写 K₁、K₂、K₃。
- **判读**：**Ka 越大／pKa 越小 = 酸越强**。
- **典型值**：醋酸 pKa = 4.74；碳酸 pK₁ = 6.35（25 °C, 1 atm）。

### 3.2 水的离子积与 pH 标度

```
H2O ⇋ H+ + OH-      Kw = [H+][OH-] = 1 × 10-14   (25 °C, 1 atm)
pH  = -log[H+]
pOH = -log[OH-]
pKw = pH + pOH = 14
```

- **符号与单位**：[H⁺]、[OH⁻] 单位 mol/L；pH、pOH、pKw 无量纲。
- **适用条件**：**只在 25 °C、1 atm 下 pKw = 14**。温度变则 Kw 变、中性 pH 变（讲义给 **0 °C 时纯水 pH = 7.47**）。
- **典型值**：纯水 25 °C，[H⁺] = [OH⁻] = 10⁻⁷ mol/L，pH = 7.00。天然水多在 pH 5–9。

### 3.3 Henderson–Hasselbalch 方程

讲义原式（OCR 有缺符，补全后）：

```
pH = pKa + log ( [A-] / [HA] )
```

碳酸体系形式：

```
pH ≈ pKa + log ( [HCO3-] / [H2CO3] )
```

- **符号**：[A⁻] = 共轭碱（已解离形式）的浓度；[HA] = 未解离酸的浓度。
- **单位**：比值无量纲，两者用同一单位即可（mM 或 M 都行——这是它好用的原因）。
- **适用条件**（实验手册给出了严格推导，见 5.4）：**弱酸 + 其盐**，且**浓度足够高（如 0.1 M）**，使得 [H⁺] 相对 [ACID]、[SALT] 可忽略。强酸不适用。
- **核心判读**：
  - **当 pH ≈ pKa（即 [A⁻]/[HA] ≈ 1）时，加酸／加碱几乎不改变 pH**——缓冲最强。
  - **当 pH 远离 pKa 时，加同样量的酸／碱会大幅改变 pH。**
  - 讲义原句："**Maximum buffering ±1 pH unit from pK.**"（缓冲有效区间约为 **pKa ± 1**）

### 3.4 钠长石溶解的缓冲算例（务必会复算）

**基础反应**（base-generating reaction，产碱反应）：

```
NaAlSi3O8 + 2H2O = 4OH- + Na+ + Al3+ + 3SiO2(aq)
```

**1 摩尔钠长石 → 4 摩尔 OH⁻。** 把长石溶解视为"往溶液里滴定 OH⁻"。

**情形 A：无缓冲（纯水）**
- 20 mmol 钠长石 → **80 mmol OH⁻ = 0.08 mol**
- pOH = −log(0.08) = **1.1**
- pH = pKw − pOH = 14 − 1.1 = **12.9**

**情形 B：有缓冲（水中先有 100 mM H₂CO₃，pK₁ = 6.35）**

反应化学计量：**1 个 H₂CO₃ 中和 1 个 OH⁻**（老师口头补的关键一步）：H₂CO₃ 失去一个 H⁺ 变成 HCO₃⁻，该 H⁺ 与 OH⁻ 结合成水——**一比一**。

| 溶解的钠长石 | 产生 OH⁻ | 消耗后 [HCO₃⁻]/[H₂CO₃] | pH = 6.35 + log(比值) |
|---|---|---|---|
| 12.5 mM | 50 mM | 50 / 50 = 1 | 6.35 + log 1 = **6.35** |
| 20 mM | 80 mM | 80 / 20 = 4 | 6.35 + 0.6 = **6.95** |

**对比的震撼之处**：同样是溶解 20 mmol 钠长石，**无缓冲时 pH = 12.9，有 100 mM 碳酸缓冲时 pH 只有 6.95**——缓冲把 pH 变化压下了近 6 个单位。

老师在图上指出的形态（transcript 1039–1067）：横轴是**线性**的钠长石加入量，纵轴是 pH。**在 pK 附近（虚线处）曲线很平**，"between 5 and 20 [mM] 只变了大约一个 pH 单位"；**在这一段的两侧，很少量的钠长石就带来很大的 pH 变化**——典型的 S 形滴定曲线。

### 3.5 碱度定义式

```
Calk = [HCO3-] + 2[CO32-] + [OH-] - [H+]
```

- **符号与单位**：各项为浓度（mol/L 或 eq/L；碱度在海洋学中常用 **µeq/kg** 或 **mmol/kg**）。
- **注意系数**：**CO₃²⁻ 前面是 2**（可接受两个质子）；**H⁺ 前面是负号**（自由质子抵消碱度）；**H₂CO₃/CO₂ 不出现**。
- **适用条件**：天然水中碳酸种态主导时，总碱度 ≈ 碳酸盐碱度。若水中有硼酸盐、硅酸盐、有机酸阴离子，严格的总碱度还应加上它们。
  📎 背景补充：海水中 **硼酸盐 B(OH)₄⁻ 约贡献总碱度的 3–4%**，因此海洋学里区分 "carbonate alkalinity" 与 "total alkalinity"；本周讲义只说"OH⁻ 偶有贡献"，未提硼。

### 3.6 缓冲容量

📎 背景补充：讲义只给了缓冲容量的**文字定义**（"能消耗多少 H⁺ 或 OH⁻ 而 pH 不显著变化"），**没有给数学式**。标准定义为

```
β = dCb / d(pH) = - dCa / d(pH)
```

其中 Cb、Ca 为加入的强碱／强酸的当量浓度。对单一弱酸缓冲对，**β 在 pH = pKa 处取极大值 β_max = 2.303 × C_total / 4 ≈ 0.576 C_total**，并在 pKa ± 1 之外迅速衰减——这正是讲义"最大缓冲在 pK ±1 单位内"这句话的定量来源。实验手册要求"计算滴定过程中所有 pH 点的缓冲容量并作 β–pH 图"，用的就是这个 β = ΔC/ΔpH 的差商形式。

### 3.7 碳酸体系的 K₁ / K₂ 与 Bjerrum 图

**讲义给出的**：pK₁(H₂CO₃) = **6.35**。

📎 背景补充（**讲义与转写均未给 K₂，也未画 Bjerrum 图；以下整节为补充，但本周考点极可能涉及**）：

碳酸体系两级解离（25 °C，淡水）：

```
H2CO3 ⇋ H+ + HCO3-     K1,  pK1 = 6.35
HCO3- ⇋ H+ + CO32-     K2,  pK2 = 10.33
```

（海水中因离子强度高，表观值约 pK₁* ≈ 5.86、pK₂* ≈ 8.92。）

**Bjerrum 图（碳酸种态随 pH 的分布图）逐项讲透：**

- **横轴**：pH，通常从 2 或 4 画到 12 或 14，**线性刻度**。
- **纵轴**：两种常见画法——(a) 各种态**占 DIC 的摩尔分数**（0 到 1，线性）；(b) **log[种态]**（对数刻度，总 DIC 固定）。教学上最常用 (a)。
- **三条曲线**：**H₂CO₃\*（= CO₂(aq) + H₂CO₃）**、**HCO₃⁻**、**CO₃²⁻**，三者分数之和恒为 1。
- **形状**：H₂CO₃\* 是从左侧的 1 单调降到右侧的 0 的 S 形；CO₃²⁻ 是从左侧 0 单调升到右侧 1 的 S 形；**HCO₃⁻ 是中间的钟形（驼峰）**。
- **两个交点的位置（最关键的记忆点）**：
  - **交点 1 在 pH = pK₁ = 6.35**：此处 **[H₂CO₃\*] = [HCO₃⁻]**，各占约 50%（把 pH = pKa 代入 Henderson–Hasselbalch，log 项 = 0，两者相等——这就是交点与 pK 重合的原因）。
  - **交点 2 在 pH = pK₂ = 10.33**：此处 **[HCO₃⁻] = [CO₃²⁻]**，各占约 50%。
- **HCO₃⁻ 峰顶的位置**：在 **pH = (pK₁ + pK₂)/2 = (6.35 + 10.33)/2 ≈ 8.34**，此处 HCO₃⁻ 占 DIC 的比例接近最大（>95%）。
- **三个统治区间**：
  - **pH < 6.35**：**H₂CO₃\*/CO₂ 占优**；
  - **6.35 < pH < 10.33**：**HCO₃⁻ 占优**（且在 pH 7.5–9.5 之间压倒性占优）；
  - **pH > 10.33**：**CO₃²⁻ 占优**。
- **海水实际 pH 落在哪里**：讲义给现代海水 **pH ≈ 7.9**（工业化前 8.2）。**7.9–8.2 恰好落在中段偏右，深深处在 HCO₃⁻ 的统治区**——实际海水中 **HCO₃⁻ ≈ 87–90% 的 DIC，CO₃²⁻ ≈ 10–11%，溶解 CO₂ 仅 ≈ 0.5%**。
- **这意味着什么（三条推论）**：
  1. **海水的碱度绝大部分由 HCO₃⁻ 承担**——与讲义"total alkalinity ≈ carbonate alkalinity，且主要来自 bicarbonate"完全一致。
  2. 海水 pH ≈ 8.1 与 **pK₂\*(海水) ≈ 8.9** 相距不到 1 个 pH 单位，也与 pK₁ 相距约 2 个单位——**碳酸体系在海水 pH 附近仍有可观缓冲能力**，这解释了为什么大气 CO₂ 涨了这么多，海水 pH 只从 8.2 掉到 7.9。
  3. 加入 CO₂ 时，**H⁺ 主要被 CO₃²⁻ 吃掉转化成 HCO₃⁻**（CO₂ + CO₃²⁻ + H₂O → 2HCO₃⁻）。**CO₃²⁻ 库被消耗 → 碳酸钙饱和度 Ω 下降 → 造壳生物钙化受抑**。这正是讲义所说"working against the gradient"的定量机制。

### 3.8 非晶质硅溶解度的定量

```
SiO2(am) + 2H2O ⇋ H4SiO4        K = 1.82 × 10-3
```

- 因为固体 SiO₂ 活度 = 1、H₂O 活度 = 1，所以 **K 在数值上就等于平衡时的 [H₄SiO₄]（mol/kg）**。
- **换算成质量浓度**：1.82 × 10⁻³ mol/kg × 60.084 g/mol = **0.109 g/kg = 109 ppm（= 109 mg/kg）**。
- **第一级解离（pH = 7 的检验）**：

```
H4SiO4 ⇋ H+ + H3SiO4-       K1 = 1.95 × 10-10
[H3SiO4-] = K1 × [H4SiO4] / [H+]
          = (1.95 × 10-10 × 1.82 × 10-3) / (1 × 10-7)
          = 3.55 × 10-6
```

  **比值 1.82 × 10⁻³ / 3.55 × 10⁻⁶ ≈ 513 ≈ 500 倍**——与讲义"500 times lower"一致（已复核，数值正确）。
- **pH = 8 时**：[H⁺] = 10⁻⁸，分母小 10 倍 → **[H₃SiO₄⁻] = 3.55 × 10⁻⁵**，升高一个数量级。
- **溶解度–pH 曲线的形状**（讲义图 + 课堂描述）：纵轴为**对数**的硅溶解度，横轴为 pH。**pH 4 到 8（甚至 9）几乎是一条水平线**（全由第一步反应控制）；**pH 向 10 靠近时曲线急剧上翘**，因为分母 [H⁺] 越来越小、分步解离项越来越重要。
- **溶解度–温度曲线**：老师明确说温度轴是**线性刻度**、pH 轴是**对数刻度**——因此"**pH 的效应比温度大得多**"。
- **对照数值**：石英 **5.9 ppm**（0.0059 g L⁻¹）；非晶质硅 **109 ppm**；比值约 **20 倍**（109/5.9 ≈ 18.5，与"about 20x"一致）。

### 3.9 矿物稳定图的推导：从 K 到直线

以微斜长石 → 高岭石为例：

```
2KAlSi3O8 + 2H+ + 9H2O ⇋ 2K+ + 4H4SiO4 + Al2Si2O5(OH)4
```

（已核对配平：两侧均为 K₂Al₂Si₆O₂₅H₂₀。）

平衡常数（固相与 H₂O 活度取 1）：

```
K = [K+]2 [H4SiO4]4 / [H+]2
```

两边取对数并用对数法则（log(AB) = logA + logB；log(A/B) = logA − logB；log(Aⁿ) = n·logA）整理：

```
log K = 2 log([K+]/[H+]) + 4 log[H4SiO4]
=> log([K+]/[H+]) = -2 log[H4SiO4] + (log K)/2
```

- **对应 y = mx + c**：
  - **y = log([K⁺]/[H⁺])**（纵轴）
  - **x = log[H₄SiO₄]**（横轴）
  - **斜率 m = −2**
  - **截距 c = log K / 2**
- 讲义强调：该体系完整化需要考虑 **K-长石、高岭石、白云母、三水铝石、非晶质硅** 之间共 6 个反应；每个反应都能同样对数化成一条直线，**六条直线围出的区域就是矿物稳定图**。
- 老师提示：这与**上周 Practical**（EXPERIMENT 1，log–log 图求络合物配位数 n）**是完全同一个数学套路**——"very similar to what we did in practical, where you had something to the power of two, but you wanted to have log values to be able to plot a log-log plot"。

### 3.10 矿物稳定图上的流体演化路径 X1 → X4

假设**封闭条件、低水／岩比**，岩石为微斜长石，引入成分为 **X1** 的流体：

| 阶段 | 位置 | 发生什么 | 反应 |
|---|---|---|---|
| **X1** | 流体落在 **gibbsite（三水铝石）场**内，不在微斜长石场，也不在其边界上 → **不平衡** | 微斜长石溶解，生成 **gibbsite**，同时释放 K⁺ 和硅酸；流体成分沿箭头向右上演化 | `KAlSi3O8(s) + 7H2O(l) + H+(aq) ⇋ K+(aq) + Al(OH)3(s) + H4SiO4(aq)` |
| **X2** | 演化到 **gibbsite–kaolinite 边界**（老师指出约在 **log[H₄SiO₄] = −5**） | 微斜长石继续反应，但**新生成的产物变成高岭石**；同时**先前生成的 gibbsite 与硅酸反应也转化为高岭石**。这一步消耗硅酸，**把流体成分"竖直"向上推**（[H₄SiO₄] 不再增加，只有 K⁺/H⁺ 比上升） | `2KAlSi3O8(s) + 9H2O(l) + 2H+(aq) ⇋ 2K+(aq) + Al2Si2O5(OH)4(s) + 4H4SiO4(aq)`<br>`2Al(OH)3(s) + 2H4SiO4(aq) ⇋ Al2Si2O5(OH)4(s) + H2O(l)` |
| **X3** | **所有 gibbsite 被消耗完** | 没有 gibbsite 再吃掉硅酸，流体**恢复沿原方向（右上）演化**，继续释放 K⁺ 和硅酸 | 同 X2 上式 |
| **X4** | 流体到达 **微斜长石与高岭石共存的边界** | **微斜长石与高岭石达到平衡，反应停止**，流体就此稳定 | — |

**要点**：注意 **X1 与微斜长石场不接触**——老师专门说"note these two minerals are not stable in contact with each other"，即 **gibbsite 与 microcline 不能共存**；但 **muscovite 与 microcline 可以共存**（它们的场有共同边界）。**是否共享边界，就是判断矿物组合是否处于平衡的判据。**

---

## 四、课堂补充

本周有约 6,920 词的完整录音转写，是本课最长的一份。以下提炼**幻灯片上没有、老师口头讲的**内容。

### 4.1 关于这一讲的定位（老师的自我坦白）

老师开门见山地说这一讲是**拼盘**："I've just kind of lumped three things sorted together… because neither of them are kind of big enough on their own… it's a little bit of a mismatch of things"。这句话对复习有实用价值：**不要试图找一条贯穿全讲的单一主线，而应把它拆成"碳酸盐在溶液中"和"硅在溶液中"两大块**，各自独立记忆，再用"写 K → 取对数"这个共同方法把它们串起来。

老师同时明确了本周与实验课的绑定：本周实验课是 buffering 与 alkalinity 的实验，**做的是酸碱滴定**，且这周由 **Jordan** 带（不是他本人），"whichever [session] worked for you last week"——分组不变。

### 4.2 讲义没写、老师口头强调的化学要点

1. **HCO₃⁻ 是两性的（amphoteric）**——这是讲义完全没有的关键概念。"Bicarbonate ions are actually a bit special. There's something called amphoteric which means they can actually react with H plus **or** OH minus. So they can actually work in both directions."
   → **这是碳酸体系能双向缓冲的根本原因**：加酸时 HCO₃⁻ 吃 H⁺ 变 H₂CO₃，加碱时 HCO₃⁻ 放 H⁺ 变 CO₃²⁻。考试中被问"为什么 HCO₃⁻ 是好缓冲剂"，答案就是它两性。

2. **"真正做缓冲的是 CaCO₃ 供给的 HCO₃⁻"** ——不是 CaCO₃ 本身。"it's that supply of bicarbonate ions from calcium carbonate that actually does the buffering."

3. **所有的水都有一点缓冲能力**，因为都含溶解离子；地球系统里最大的缓冲体是海水。这为实验里"去离子水 vs 自来水"的对比埋了伏笔。

4. **水的 K 取 1 的两种理由**：老师把它与上周作了明确对照——"a bit like last week when we talked about having a solid in an equilibrium constant with the solubility product. That was essentially one because it was a **solid**. For a slightly different reason here we ignore it. It's one because it's **water**."（固体：纯相活度定义为 1；水：作为溶剂、稀溶液中活度 ≈ 1。）

5. **温度改变 Kw → 改变"中性 pH"**：老师说这是"你可能从没遇到过的"点。"if you change the temperature because equilibrium constants are dependent on temperature, the natural pH of water will change… pure water therefore has a pH of 7 at 25 degrees C. **But only at 25 degrees C.**"
   ⚠️ 注意：老师紧接着说 "at 0 degrees C pure water is actually slightly alkaline"，**这句说法有问题**（见勘误表）：0 °C 时纯水的 pH = 7.47，但它**仍然是中性的**（[H⁺] = [OH⁻]），只是"中性点"移到了 7.47。**"pH > 7 就是碱性"这个判据只在 25 °C 成立**——这本身正是老师想传达的核心，但表述上把"pH 大于 7"和"碱性"混为一谈了。这是极好的考点。

6. **钠长石缓冲算例里那个"1:1"的化学计量**：老师专门补了讲义上没写的反应式——"you've got one carbonic acid here reacting with one OH. It loses an H+. It becomes HCO3- and that H plus reacts with that OH just to give you water. So it's a **one to one reaction**"。**没有这一步，就理解不了为什么 50 mmol OH⁻ 对应 50/50 的比值。** 老师自己也承认："I should have written the equation on there, sorry."

7. **老师承认幻灯片缺条件**："Carbonic acid has a pK of 6.35. I should have written the conditions there, I haven't. I'll say it's 25 degrees C and one atm."——**pK 值必须带温压条件**，这是答题规范。

### 4.3 考试提示与"最该带走的一件事"

老师给出了本讲**唯一一次**的明确取舍指令（transcript 1135–1155）：

> "**if you only take one bit of what I've said today away in terms of carbonate systems and alkalinity, it's this equation here.** This equation sums up basically everything I've just said… This has got all the equilibrium that you need to consider."

指的就是：**CO₂ + H₂O ⇌ H₂CO₃ ⇌ H⁺ + HCO₃⁻ ⇌ 2H⁺ + CO₃²⁻**

老师随后逐段拆解（这是转写里最有价值的一段解读）：
- **最左端 = 大气排放的 CO₂ 输入**，与水反应生成碳酸；
- **中间两步向右走 = 两次释放 H⁺，把水变酸**；
- **最右端 = CaCO₃ 溶解直接供给 CO₃²⁻ 的输入**；
- **"You add stuff in at the left, all the equilibria go to the right, and it makes things more acidic. You add stuff at the right, pushes everything back to the left again. And it's that battle, if you like, between CO₂ and calcium carbonate that is sort of global alkalinity story."**

另一条明确的考试豁免（transcript 1923–1943）：讲到对数法则时——

> "There's some rules of log involved here. Log rules. **Don't learn them. Please don't learn them. I don't know them either. I will never ever ask you to reproduce or anything about it.** But some people like to know exactly how you get from one point to another point."

→ **不会考对数法则的推导本身，但要会用它把 K 表达式化成直线方程。**

### 4.4 硅部分的口头澄清

1. **凝胶 → chert**：非晶质硅析出时是"gelatinous goo"（凝胶状黏糊），成岩压实把水挤出后成为 **chert**。老师提示学生可能在别的实习课里见过这种非晶质硅。
2. **溶解度曲线是对数纵轴**——"this is log scale, you rapidly increase the silica solubility"；而温度图是线性纵轴。**比较两个效应大小时必须先看坐标类型**，这是老师专门强调的读图纪律。
3. **实际意义**：pH 降 0.1 单位析出 1.37 mg/L 看似微小，但"a lot of water has got silica in it… if you multiply that by volumes of groundwater flow and flow rates, it is a **very efficient way of moving silica around the Earth system**"。老师还提到工业上必须监控这一点，否则硅会在不该沉淀的地方结垢。
4. **石英过饱和却不沉淀 = 动力学**：老师明确说"from an equilibrium chemistry point of view, really, we should get precipitation of quartz in all our rivers… and the reason for that is **kinetics**"——**这是与 W06（kinetics and diffusion）最直接的回扣，也是典型的"平衡预测 vs 实际观测"考题。**
5. **课堂提问：为什么海水的硅比河水少？** 老师提问后**全场无人回答**（"Anyone want to hazard a guess? No? Just checking your hair. OK, fair enough."），随后自己给出答案：**diatoms（硅藻）等生物摄取硅造壳**。老师还做了类比：**"a bit like various creatures use calcium carbonate in their shells, some creatures use silica."**
   → **一个重要的元认知信号：老师主动提问但无人答的知识点，往往就是他认为重要且学生薄弱的地方。**

### 4.5 矿物稳定图的三个用途（老师的归纳）

老师明确列出（transcript 2053–2125），讲义上只零散提到：

1. **给定溶解离子浓度，告诉你哪个矿物稳定**（各个"场"就是该矿物的稳定域）；
2. **告诉你哪些矿物彼此稳定共存**——"where you've got a boundary between two different minerals, they can both coexist… you can see, for example, you have situations where **muscovite and microcline can coexist but not microcline and gibbsite**. So it tells you something fundamental about a particular mineral assemblage. **Is it at equilibrium or is it not?**"
3. **预测特定流体–岩石体系随时间演化的结果**——老师说"I think that's probably the most useful thing to do"。

关于 **X2 处那段"竖直上移"的推理**，老师讲得比讲义细致，是本周最需要跟着走一遍的逻辑：

> 流体在 X2 落在 gibbsite–kaolinite 边界上，此时**两个矿物都稳定**。微斜长石继续反应释放硅酸，本来会把流体推到右上方（离开边界，进入 kaolinite 场），**但只要流体离开那条边界，gibbsite 就不再稳定**；于是 gibbsite 立刻与新产生的硅酸反应生成高岭石，**把硅酸消耗掉，结果流体成分只能"直上"移动**（[H₄SiO₄] 被钉住，只有 K⁺/H⁺ 比上升）。这个过程一直持续到 **X3——gibbsite 被耗尽**。此后再没有东西消耗硅酸，流体恢复沿原方向演化，直到 **X4** 撞上微斜长石–高岭石边界，两相平衡，**反应停止**。

老师的收尾评语点出了方法论意义：**"So it's another use essentially of equilibrium reaction constants."**（矿物稳定图本质上只是平衡常数的又一种用法。）

### 4.6 课堂 Kahoot 测验及老师的即时讲评

本周课末有 12 题 Kahoot（奖品是 Rolos 和 Munchies；约 40 人参与）。测验答案文件 OCR 质量很差，但**转写里保留了老师对每题的口头讲评**，价值更高：

| 题 | 题目（据转写 + OCR 拼合） | 答案与老师讲评 |
|---|---|---|
| 1 | 酸做什么？ | **给出质子 / 提供 H⁺** |
| 2 | 酸性地下水有…… | **"all three"**——高 H⁺、低 pH，且几乎总是高溶解固体。老师："It's another one of those dreaded all three options… I guess you're all right in a sense aren't you because it is all three." |
| 3 | Ka 值大的酸是…… | **强酸** |
| 4 | 若 [H⁺] > 1 × 10⁻⁷ mol/L，溶液是…… | **酸性**。老师："if it was exactly 1×10⁻⁷ then it would be neutral. But if it's more then it's going to be acidic." |
| 5 | 缓冲能力好的溶液…… | **抵抗 pH 变化（resists pH change）**。老师："Nice easy one that one." |
| 6 | 缓冲容量最高的是…… | **含碳（碳酸盐）最多的那个**。老师："The question is essentially **which of those has got the most carbon in**… it's definitely not deionized water because that's got nothing in it at all. **So that's the worst of all of those. And you'll do experiments with deionized water to show actually that it's not very good at buffering capacity.**" ← **直接预告了实验课的结论** |
| 7 | 哪些贡献碱度？ | **全部都贡献**（碳酸根、碳酸氢根等）。老师："All of them do? Well done." |
| 8 | Henderson–Hasselbalch 方程预测什么？ | 老师承认题目出得不好："It's a bit of a tricky question but I don't think I've worded it very well… **the answer I was after was actually that one. It relates to dissociation [and] pH.**"（即：它把**解离程度（[A⁻]/[HA] 比值）与 pH** 联系起来） |
| 9 | 最大缓冲发生在何时？ | **pH 接近 pKa**（不是 pH 高、也不是 pH 低、也不是 pH 高于 pKa）。老师："When is the buffering effect strongest? Or most efficient, should we say? Yes." |
| 10 | 方程 CO₂+H₂O→H₂CO₃→H⁺+HCO₃⁻→2H⁺+CO₃²⁻ 解释了什么？ | **只解释"珊瑚为什么在溶解"**，**不是 all of the above**。**全班都掉进陷阱**——老师："Oh, you've all fallen into the trap… **It doesn't tell you anything about why things are getting warmer, it doesn't tell you about why the atmospheric CO₂ is rising. It's just that one.**" ← **本周最高价值的一道错题，务必记住：这条方程是化学方程，不解释升温机制，也不解释 CO₂ 为何上升，只解释加 CO₂ 之后碳酸钙为何溶解。** |
| 11 | pH 的定义是…… | **H⁺ 浓度（活度）的负对数** |
| 12 | 什么主要控制硅的沉淀？ | **pH**（而非温度）。老师："It **is** temperature dependent, **but it's that pH that makes the biggest difference.**" |

老师对第 12 题的补充措辞值得记住："I couldn't put all three, so I put the opposite."——即题目故意设置了"温度"作为诱答项。

### 4.7 课程事务信息（转写末尾）

- 老师说本周实验课**不是他带**（是 Jordan），他下周一再见学生。
- 提到**作业已全部批改完毕，正在等 DAS 延期的学生**；平台是新的，"you might be able to see the comments but at the moment you can't see the marks"；**"Most people have done really well. It's like 78%."**（班级平均分约 78%。）
  📎 背景补充：从课程大纲看，此处应指 **summative report（占 20%，Week 5 发、Week 7 交）**；转写未点明是哪一份，材料未说明。

---

## 五、Practical 要点

### 5.0 关于读取范围的说明（按任务要求交代）

本周 `Practical/Week 8/` 下只有一份文件 `EART26201 lab handbook 2025-1.md`（约 21,717 词）。**它并不是第 8 周的专属材料，而是全课通用的实验手册**，被归档在 Week 8 文件夹下（已计入勘误表）。

**我实际读取的行段（与预处理给出的行号完全一致，未发生偏移）：**

| 行号 | 内容 | 是否读取 | 理由 |
|---|---|---|---|
| 65–664 | 实验室安全守则、事故上报、应急程序、健康安全测试与声明、实验前准备、实验记录书写 | **未读** | 该段是**全课通用的安全与行政内容**，与本周"缓冲与碱度"主题无直接关系；按项目安排，留给阶段二的课程级笔记统一处理，避免在周笔记里重复三到四倍的 token 消耗 |
| **665–1003** | PRACTICAL LABORATORY TECHNIQUES（容量玻璃器皿）、SOME USEFUL TIPS ON UNITS、ON LOGARITHMS、ON GRAPHS、Serial dilutions、Titrations、EXPERIMENT 1 | **已读** | 通用实验基本功，是做本周实验的前置技能 |
| **1004–1278** | **EXPERIMENT 2: BUFFERS AND INDICATORS** | **已读** | 与本周主题直接对应的实验 |

⚠️ 一处需说明：**665–1003 这一段的末尾（第 889–1003 行）实际上是 EXPERIMENT 1（Solubility and metal-ligand complexing，银氨络合物）**，那是 **W07 的实验**，不属于"通用技能"。我照读了，但在本周笔记中**只作为背景一笔带过**（见 5.7），详细内容应归入 W07 笔记。

### 5.1 通用实验技能（一）：容量玻璃器皿

**三类器皿**：**移液管 pipette**（转移准确体积）、**滴定管 burette**（连续分液，用于滴定）、**容量瓶 volumetric flask**（准确配液）。

**三条铁律**：保持极度洁净；**绝不可加热**（玻璃膨胀后难恢复原尺寸 → 刻度失准）；必须正确读数。

**弯月面（meniscus）读数**：水在玻璃中形成中间低、贴壁高的凹液面。**眼睛必须与弯月面齐平**（避免**视差 parallax**），**读曲线最低点**。

**滴定管**：底部有**旋塞 stopcock**；从顶部用漏斗加液；**滴定前先放掉约 5 ml 溶液润洗**；**旋塞只用一只手、放在滴定管背后、温柔缓慢地开关**；**体积 = 分液后读数 − 分液前读数**；**不要加到 0.00 ml 刻度以上**（除非用于润洗）。

**容量瓶**：颈部只有一条刻度线，**通常标定于 20 °C**；使用前用溶剂润洗；**用固体配液必须先完全溶解再定容**。

**清洗**：每次实验后用温水清洗、倒扣晾干；**所有玻璃器皿须用去离子水润洗三次**；**洗涤时戴手套**。

### 5.2 通用实验技能（二）：单位

- **所有测量都必须报单位**——"A number on its own is generally ambiguous and mostly useless."（只记 "20" 无法区分 20 °C / 20 K / 20 °F。）
- **MOLALITY（质量摩尔浓度，m）** = mol / **kg 溶剂**；**MOLARITY（体积摩尔浓度，M）** = mol / **L 溶液**；**1 M = 1000 mM**。
- **关键区别**：稀水溶液、恒定低温下两者数值几乎相同；但**盐水（油田卤水、海水）与高温条件下差别可以很大**。
- **本手册统一用 MOLARITY**——因为这些实验是**按体积配液**（容量瓶、滴定管、移液管）而非按重量（精密天平贵得多）。

### 5.3 通用实验技能（三）：对数与作图

**对数**（手册中 "log" 一律指**以 10 为底**；**零与负数的对数无定义**）：

```
若 Y = 10^X 则 X = log(Y)
log(A·B) = log A + log B      log(A/B) = log A - log B
log(1/A) = -log A             log(A^n) = n·log A
【易错不等式】 log(A)/log(B) ≠ log(A/B)   log(A)·log(B) ≠ log(A·B)
【应用】 pH = -log(aH+) = log(1/aH+)      pKa = -log(Ka) = log(1/Ka)
```

**作图规范（报告扣分重灾区）**：**因变量放 Y 轴、自变量放 X 轴**；数据须**铺满至少 2/3 页面**，刻度取整数且增量一致；**绘图数据应为纯数字**（单位放进轴标签，写 "temperature in degrees Celsius" 而非 "temperature"）；**轴标签含变量名与单位**；**标题醒目并指明因变量与自变量**；数据点用带圈的点或小十字，**尽量加误差棒并说明误差如何估算**。**三类线必须注明用的是哪一类**：**model curve**（理论预测）／**best-fit curve**（通常是 y = mx + c，用**最小二乘 least squares** 客观确定）／**trend**（目测勾勒）。手册特别指出**滴定曲线通常无法用直线甚至高阶多项式很好近似**，目测趋势线反而有价值，**但要小心过拟合**。

**系列稀释（serial dilution）**：取母液一份加等量溶剂，反复进行——每步减半。手册例：2.5 mM → 1.25 → 0.625 → 0.312 → 0.156 mM。

### 5.4 通用实验技能（四）：滴定的原理与术语

**定义**：用滴定管逐渐加入**已知浓度的标准溶液（滴定剂 titrant）**，与样品中的**被分析物（analyte）**按已知比例反应，从而测定其未知浓度。

**三个必须分清的术语（高频考点）**：
- **等当点 equivalence point**：滴定剂在**化学计量上恰好等量**的那一点——理论点。
- **终点 end point**：**实验上观察到信号**（指示剂变色或电学性质突变）的那一点。
- **滴定误差 titration error = 终点 − 等当点**；通过合理选择终点信号把它压到最小。

**按反应类型分四类**：**酸碱滴定**（指示剂有酸型／碱型两种颜色，如石蕊、酚酞；不同指示剂的**变色 pH 不同**）、**沉淀滴定**（以有色沉淀出现为终点，如铬酸钾指示剂或吸附指示剂）、**络合滴定**（最重要的是 **EDTA** 滴定金属离子，终点处金属–染料络合物转变为游离染料）、**氧化还原滴定**（指示剂在终点附近被氧化或还原，两态颜色不同）。

**电学检测终点**：**电位滴定**（测电位差）、**电导滴定**（测电导／电阻）、**电流滴定**（测电流），均以所测量的显著变化指示终点。

### 5.5 EXPERIMENT 2：BUFFERS AND INDICATORS（本周实验）

#### 5.5.1 实验目的（Performance Objectives）

完成本实验后应能：
- 理解 **pH 缓冲液**的概念与 **"buffer capacity"** 一词；
- **校准**一台特定的简易 pH 计；
- 理解 **pH 指示剂**的原理；
- 完成一次**酸碱滴定**；
- **准确使用容量瓶**。

#### 5.5.2 原理（一）：矿物对溶液的缓冲

手册的切入角度很地球化学：**如果地下水与热液的成分完全随机可变，我们就根本不可能理解它们的化学；幸运的是，实测的成分往往落在相当窄的范围内。**

**例 1：石英缓冲硅浓度。** 许多地下水的硅浓度接近与石英平衡的值，因为围岩含过量游离石英：

```
SiO2 (quartz) + 2H2O (aq) ⇋ H4SiO4 (aq)     ← 硅浓度下降时，石英溶解
H4SiO4 (aq) ⇋ SiO2 (quartz) + 2H2O (aq)     ← 硅浓度上升时，石英沉淀
```

若这两个机制能有效维持溶解硅的相对恒定，就说**石英"缓冲"了这个溶液**（buffer against change）。
> ⚠️ 手册第一式原文写成 `H2SiO4`，应为 `H4SiO4`（见勘误表）。

**例 2：矿物组合缓冲 K⁺/H⁺ 比。** 在许多花岗岩围岩的热液体系中，**石英 + 钾长石 + 白云母**这一组合缓冲 (K⁺/H⁺)：

```
3KAlSi3O8 (K-feldspar) + 2H+ (aq) ⇋ KAl3Si3O10(OH)2 (muscovite) + 2K+ (aq) + 6SiO2 (quartz)
```

**关键限定条件**：**只有在组合中的每一种矿物都还共存时，这个缓冲才起作用**（一旦某一相被耗尽，缓冲失效）。
→ 这与讲座里 **X3 点"gibbsite 耗尽后流体恢复演化"** 是**同一条原理**，可互相印证。

#### 5.5.3 原理（二）：缓冲溶液与 Henderson–Hasselbalch 的严格推导

**好的缓冲液范例：0.1 M 醋酸（CH₃COOH）+ 0.1 M 醋酸钠（CH₃COONa）。**

手册的完整推导（**这是理解 HH 式适用条件的关键，值得完整跟一遍**）：

```
HA ⇋ H+ + A-        (A = CH3COO-)
Ka = [H+][A-] / [HA]
=> [H+] = Ka × [HA]/[A-]                              ... Eq. A

设 [ACID] 为醋酸的分析浓度：
   [HA] = [ACID] - [H+]                               ... Eq. B

醋酸钠是强电解质、完全解离，设 [SALT] 为其分析浓度：
   [Na+] = [SALT]
   [A-] = [Na+] + [H+]      (电荷平衡)
=> [A-] = [SALT] + [H+]                               ... Eq. C

代入 Eq. A：
   [H+] = Ka × ([ACID] - [H+]) / ([SALT] + [H+])

【关键近似】对足够浓的溶液（如 0.1 M）且为弱酸，[H+] 相对 [ACID] 与 [SALT] 可忽略：
   [ACID] - [H+] ≈ [ACID]
   [SALT] + [H+] ≈ [SALT]

=> [H+] = Ka × [ACID]/[SALT]
=> pH = pKa + log([SALT]/[ACID])
```

**数值验证**：醋酸 **Ka = 1.82 × 10⁻⁵ mol/L → pKa = −log(1.82 × 10⁻⁵) = 4.74**（已复核：5 − log 1.82 = 5 − 0.260 = 4.740 ✓）。
故 **0.1 M 醋酸 / 0.1 M 醋酸钠溶液的 pH = 4.74**（因为 log(0.1/0.1) = 0）。

**→ 注意这个式子的写法**：手册写作 `pH = pKa + log([SALT]/[ACID])`，讲义写作 `pH = pKa + log([A⁻]/[HA])`——**两者完全等价**（[SALT] 就是共轭碱 A⁻，[ACID] 就是未解离的 HA）。**别被两种写法搞混。**

#### 5.5.4 原理（三）：缓冲容量的定量算例

**问题**：往 1 升 0.1 M 醋酸 / 0.1 M 醋酸钠缓冲液中加入 **10 ml 0.1 M HCl**（= 0.001 mol H⁺），pH 会变成多少？

```
HCl 几乎完全解离，其 H+ 打破醋酸/醋酸根平衡，与醋酸根反应生成醋酸：
   H+ + CH3COO- = CH3COOH

[A-] = 0.1 - 0.001 = 0.09  = [SALT]
[HA] = 0.1 + 0.001 = 0.11  = [ACID]

pH = 4.74 + log(0.09/0.11) = 4.74 - 0.09 = 4.65
```

**→ 加入 0.001 mol 强酸，pH 只从 4.74 降到 4.65（降 0.09 个单位）。**

📎 背景补充（对照实验的意义）：同样把 0.001 mol HCl 加进 1 升**纯水**，[H⁺] ≈ 10⁻³，**pH 从 7 直接降到约 3——降了 4 个单位**。**缓冲液把变化压缩到约 1/45**。这就是实验里"缓冲液 vs 去离子水"对照要展示的效果，也是老师在 Kahoot 第 6 题预告的结论。

⚠️ 手册这一算例**忽略了体积稀释**（1 L → 1.01 L）。对结论无影响，但严格计算应考虑（见勘误表）。

#### 5.5.5 实验前准备（Pre-laboratory Preparation）

1. 通读整个实验流程；
2. **阅读题为 "Alkalinity" 的讲义**；
3. 记下任何不理解的步骤，**在实验开始前**向 demonstrator 提问；
4. 列出所需**器材与试剂清单**，以便实验开始时核对是否齐备；
5. 记下任何**存在潜在危险的步骤**并预先考虑规避策略；实验中如有疑问，**在做这些步骤之前**先问实验室主管。

#### 5.5.6 指示剂

| 指示剂 | pH 区间 | 颜色 | 条件 |
|---|---|---|---|
| **酚酞 Phenolphthalein** | 0–8.3 | **无色** | 酸性—接近中性／微碱性 |
| | 8.3–10 | **粉红 → 紫红（fuchsia）** | 碱性 |
| | >10 | **无色** | 强碱性 |
| **筛选甲基橙 Screened methyl orange** | < 3.1 | **红** | 强酸性 |
| | 4.4 到 10+ | **黄** | 从弱酸性到强碱性 |

⚠️ **酚酞在 pH > 10 时又变回无色**——这是个陷阱：**看到无色不能直接判断是酸性**，必须结合另一指示剂或 pH 计。这也是实验流程里要求先用酚酞、变色后再换甲基橙的原因。

#### 5.5.7 操作步骤

**A. pH 计校准（two-point calibration）**

1. 把 pH 计浸入提供的 **pH 7 缓冲液**，检查读数是否为 **7.0 ± 0.2**（**记得摘下保护帽！**）。
2. 若读数在 **6.8–7.2 之外**，用小螺丝刀调节机背标注的相应螺丝，使读数正确。
3. 小心用**自来水**冲洗探头底部，再用**去离子水**冲洗。**手必须保持干燥**；**只把探头下部浸入溶液**；**pH 计始终保持竖直**。
4. **在 pH 7 校准完成之后**，再用 **pH 4 缓冲液**检查，读数应为 **4.0 ± 0.2**；若在 **3.8–4.2** 之外，用侧面的正确螺丝调节。
5. 再次用自来水、去离子水冲洗探头。
6. **最后复检**：把 pH 计放回 pH 7 缓冲液，若读数仍在 6.8–7.2 之外，**重复整个校准流程**。

**B. 溶液的缓冲容量测定**

- 向**两种溶液**（**一种缓冲液 + 一种水**）中各加入 **4 滴筛选甲基橙**指示剂，用滴定管以 **0.1 M HCl** 滴定。
- **共加入 5 ml 的 0.1 M HCl，每次增量约 0.5 ml。**
- 每次增量后记录：
  1. **pH 与滴定管读数**；
  2. **pH 读数稳定所需的时间**（可能从几秒到几十秒不等）；
  3. **溶液的任何颜色变化**。
- **每换一种新溶液前，必须用去离子水彻底冲洗烧杯。**
- 溶液选择（各选一）：
  - **缓冲液**：100 ml **pH = 7 缓冲液** 或 100 ml **pH = 4 缓冲液**
  - **水**：100 ml **去离子水** 或 100 ml **自来水**

**C. 强碱–强酸滴定**

1. 台上有一瓶约 **100 ml 的 0.01 M NaOH 储备液**（有明确标签）。
2. 用**容量瓶**精确量取 **恰好 100 ml** 该溶液至 **250 ml 烧杯**。
3. 测量烧杯中溶液的 **pH**。
4. 加入 **2 滴酚酞**，记录 pH 是否有变化（若有）。
5. 用 **50 ml 滴定管**，以 **0.1 M HCl** 滴定该 0.01 M NaOH 溶液。**每次加入后要等 pH 稳定再加下一次**，并记录累计体积与 pH。分段增量策略如下：
   - **每次约 0.5 ml**，直到 **pH 降到 10.7 以下**；
   - 改为**每次 0.1 ml**，直到**酚酞的粉红色消失**；
   - 记录颜色变化；**溶液一变无色，立即加入 4 滴筛选甲基橙**，继续以 **每次 0.1 ml** 滴定；
   - 记录累计体积、pH 与颜色变化；
   - **当 pH 降到 3 以下时停止滴定。**
6. **作图**：pH 对加入的 0.1 M HCl 体积作图。
7. **计算滴定过程中所有测得 pH 点的缓冲容量，并作缓冲容量对 pH 的图。**

**D. 清场**

- 用去离子水与自来水彻底但小心地清洗 pH 探头；**在保护帽里放少量自来水后套回探头**再存放；**记得关机**；清洗所有用过的玻璃器皿，整理清洁台面。

#### 5.5.8 数据表（Data Sheet）结构

需记录：pH 计编号；pH 7 与 pH 4 缓冲液的实测读数；两张"滴定管读数 / 加入 0.1 M HCl 体积 / pH / 颜色与备注"四栏表（一张给所选缓冲液、一张给所选水）；两张 pH–体积图；以及 0.01 M NaOH 滴定的两页记录表。

#### 5.5.9 预期结果

📎 背景补充（手册未直接给出预期曲线，以下为按化学原理的推断，答题时应以自己实测数据为准）：
- **pH 7 或 pH 4 缓冲液**：加入 5 ml 0.1 M HCl 后 pH 只**小幅下降**（零点几个单位），曲线**近乎平坦**；
- **去离子水**：**几滴酸就使 pH 断崖式下跌**（去离子水几乎无缓冲容量，且其初始 pH 本就不稳定，易受溶解 CO₂ 影响）；
- **自来水**：介于两者之间，**明显好于去离子水**——因为自来水含 HCO₃⁻ 等溶解离子（这正是 Kahoot 第 6 题"哪个含碳最多"的答案逻辑）；
- **0.01 M NaOH 用 0.1 M HCl 滴定**：等当点应在**加入 10.0 ml** 时（0.01 mol/L × 0.100 L = 1.0 mmol NaOH；1.0 mmol ÷ 0.1 mol/L = 10.0 ml HCl）；曲线在等当点附近**极陡**，从 pH ≈ 10 骤降到 pH ≈ 4；**强酸–强碱滴定的等当点 pH = 7**；
- **缓冲容量 β–pH 图**：在**等当点附近出现最小值**（此处 β 最低、pH 最敏感），在曲线两端（过量碱区、过量酸区）β 上升。

#### 5.5.10 课后问题（Post-laboratory Questions）

1. **自来水与去离子水，哪个是更好的缓冲液？**（→ 自来水；因其含溶解的碳酸氢盐等离子）
2. **0.01 M NaOH 用 0.1 M HCl 滴定时，终点的意义是什么？如何用这样的滴定测定未知浓度 NaOH 的浓度？**（→ 终点标志强酸恰好中和强碱；由 c(NaOH)·V(NaOH) = c(HCl)·V(HCl) 反算）
3. **甲基橙与酚酞各在什么 pH 区间变色？**（→ 由实验观察给出，对照 5.5.6 的表）
4. **溴百里酚蓝（bromo-thymol blue）在 pH 6.0–7.6 由黄（酸）变蓝（碱）。为什么它的变色区间可能更适合确定 NaOH–HCl 滴定的终点？**
   📎 背景补充（答题思路）：**强酸–强碱滴定的等当点 pH = 7**，恰好落在溴百里酚蓝的变色区间 6.0–7.6 的中部；而酚酞在 8.3 才开始变色、甲基橙在 3.1–4.4 变色，**两者的变色点都偏离 pH 7**，会引入更大的**滴定误差（titration error = 终点 − 等当点）**。这道题正是在考 5.4 里"终点 vs 等当点"的区分。
5. **100 ml 0.1 M NaOH 与 100 ml 0.1 M HCl 的混合液作为 pH 缓冲液效果如何？请解释。**
   📎 背景补充（答题思路）：两者**恰好完全中和**，产物是 **0.05 M NaCl 溶液**——NaCl 是**强酸强碱盐，不水解、无共轭酸碱对**，因此**几乎完全没有缓冲能力**。这题在考"缓冲液必须是弱酸 + 其共轭碱"这一本质。
6. **采集了 (i) 低缓冲容量地下水与 (ii) 高缓冲容量地下水的小样品，带回实验室测 pH。哪个样品测得的 pH 更能代表原地下水的 pH？请解释。**
   📎 背景补充（答题思路）：**高缓冲容量的样品**。因为样品在运输与储存中会与大气交换 CO₂、可能受容器污染、温度也会变化；**低缓冲容量的水对这些微小扰动极其敏感，pH 会显著漂移**，而高缓冲容量的水能抵抗这些变化。这题把"pH 是强度量、缓冲容量是容量量"的区分放到了**野外采样的实际后果**上，是本周最能体现学科思维的一题。

### 5.6 安全要点

**来自通用技能段（第 715–727 行）：**
- 摇动容量瓶混匀时，**必须同时握住瓶底与顶部的塞子**；
- **绝不可只捏着瓶颈拿装满液体的容量瓶**——颈部可能撑不住瓶身加溶液的重量；
- 不当操作可导致 **玻璃瓶破裂、严重割伤、危险液体失控泄漏**；
- 摇动时瓶内压力可能升高，应**定期缓慢拔出塞子泄压**；**若塞子卡死，绝不可强行拔出**（瓶颈可能断裂割伤手指），**找实验室主管帮忙**；
- 洗涤玻璃器皿时**始终戴手套**。

**来自 EXPERIMENT 2：**
- pH 计操作：**手必须干燥**；**只浸入探头下部**；**保持竖直**；
- 使用 **0.1 M HCl** 与 **0.01 M NaOH**，均为腐蚀性试剂，取用与滴定须遵守常规防护；
- 实验前准备第 5 条要求**预先识别有危险的步骤并制定规避策略**，有疑问先问主管再动手。

📎 背景补充：手册第 65–664 行的完整安全守则（部门政策、事故上报流程、应急程序、消防）本周未读，将在阶段二的课程级笔记中统一整理。

### 5.7 EXPERIMENT 1 备注（属 W07，此处仅存目）

第 889–1003 行是 **EXPERIMENT 1: SOLUBILITY AND METAL-LIGAND COMPLEXING**——用 0.02 M KBr 滴定含氨的 0.01 M AgNO₃ 溶液至**首次出现永久浑浊（沉淀终点）**，以 **log(moles KBr)** 对 **log(moles NH₃)** 作图，**斜率即为银氨络合物 Ag(NH₃)ₙ⁺ 中的 n**。

**为什么本周要知道它**：老师在讲矿物稳定图时**明确回指了这个实验**——"very similar to what we did in practical, where you had something to the power of two, but you wanted to have log values to be able to plot a log-log plot, which you had a straight line on"。**"把带指数的平衡常数表达式取对数变成 y = mx + c，从斜率读出化学计量数"** 这一手法，在 EXPERIMENT 1 里求的是配位数 n，在本周讲座里求的是矿物稳定边界的斜率 −2——**是同一件事**。详细内容归 W07 笔记。

---

## 六、易错点 / 重点难点

### 6.1 碱度 ≠ pH（本周头号易错点）

- **pH 是强度量**（现在有多酸），**碱度是容量量**（还能吃掉多少酸）。
- 两者**可以完全脱钩**：pH 相同的两种水，碱度可以差几个数量级（去离子水 vs 海水）。
- **实践后果**（对应实验课后问题 6）：低碱度的水样在运输储存中 pH 会大幅漂移，测出来的 pH 不代表原位值。
- **答题模板**："Alkalinity measures the *capacity* to neutralise acid, whereas pH measures the *intensity* of acidity at a given instant. A solution can have a high pH but negligible alkalinity."

### 6.2 碱度 ≠ DIC（第二号易错点）

📎 背景补充（讲义未展开）：
- 碱度式：`Calk = [HCO₃⁻] + **2**[CO₃²⁻] + [OH⁻] − [H⁺]` ——**CO₃²⁻ 系数为 2，且 H₂CO₃/CO₂ 不出现**。
- DIC 式：`DIC = [CO₂(aq)] + [H₂CO₃] + [HCO₃⁻] + [CO₃²⁻]` ——**所有系数都是 1，且包含 CO₂**。
- **溶入 CO₂：DIC ↑，pH ↓，碱度不变。**（CO₂ + H₂O → H⁺ + HCO₃⁻，在 Calk 式里 +1 和 −1 抵消）
- **溶解 CaCO₃：碱度 +2，DIC +1。**
- 记忆法：**碱度看"电荷／质子接受能力"，DIC 看"碳原子个数"。CO₂ 有碳但不接受质子，所以进 DIC 不进碱度。**

### 6.3 最大缓冲容量出现在 pH = pKa，不是 pH = 7

- 这是 Kahoot 第 9 题，也是最容易凭直觉答错的地方——**"中性"跟"缓冲能力强"毫无关系**。
- 从 Henderson–Hasselbalch 看：pH = pKa ⟺ [A⁻]/[HA] = 1 ⟺ **酸型与碱型各占一半，两个方向都有充足的"弹药"**。
- **有效缓冲区间约为 pKa ± 1**（讲义原句："Maximum buffering ±1 pH unit from pK"）。
- 反例检验：0.1 M 醋酸/醋酸钠缓冲液的**最佳工作 pH 是 4.74**，它在 pH 7 附近**几乎没有缓冲能力**。

### 6.4 强度 ≠ 浓度

- 讲义用全大写强调过。**强酸 = 解离程度高（Ka 大／pKa 小）；浓度 = 有多少。**
- 稀盐酸（强酸低浓度）与浓醋酸（弱酸高浓度）可以有**相同的 [H⁺]**，但**缓冲行为完全不同**：只有后者是缓冲体系。

### 6.5 "pH > 7 = 碱性" 只在 25 °C 成立

- Kw 随温度变化，**中性 pH 也随之变化**（0 °C 时为 **7.47**）。
- **中性的判据是 [H⁺] = [OH⁻]，不是 pH = 7。**
- 老师在课上把 0 °C 的纯水说成 "slightly alkaline"——**这个说法不对**（见勘误表）；它仍是中性的，只是中性点在 7.47。**这个陷阱非常适合出考题。**

### 6.6 加酸／加碱对碱度与 DIC 的不同影响（对照表）

📎 背景补充：

| 操作 | pH | 碱度（Alk） | DIC |
|---|---|---|---|
| 溶入 CO₂（大气→海洋） | ↓ | **不变** | ↑ |
| CaCO₃ 溶解 | ↑ | **+2 当量** | +1 mol |
| CaCO₃ 沉淀（钙化） | ↓ | **−2 当量** | −1 mol |
| 加入强酸 HCl | ↓ | **↓（1:1 消耗）** | 不变 |
| 加入强碱 NaOH | ↑ | **↑（1:1 增加）** | 不变 |
| 光合作用固碳（有机质） | ↑ | 基本不变 | ↓ |

**注意最反直觉的两行**：**加 CO₂ 不改变碱度**；**钙化（造壳）反而降低海水 pH**（因为它同时移除 2 份碱度和 1 份 DIC，净效果是酸化）。

### 6.7 石英与非晶质硅的四组对照

| | 石英 quartz | 非晶质硅 amorphous silica |
|---|---|---|
| 溶解度 | **5.9 ppm**（0.0059 g/L） | **109 ppm**（0.109 g/kg） |
| 与水反应生成硅酸 | 几乎不 | **是**，主要来源之一 |
| 河水的饱和状态 | **过饱和** | **不饱和** |
| 为什么河里不析出石英 | **动力学（反应太慢）** | — |

**答题时最常丢分的地方**：把"河水相对石英过饱和"和"河水相对非晶质硅不饱和"记反；或者用"热力学不允许"来解释石英不沉淀——**正确答案是动力学**。

### 6.8 硅溶解度对 pH 的依赖：注意哪个物种在变

- **[H₄SiO₄] 由与非晶质硅的平衡固定（1.82 × 10⁻³），它不随 pH 变**（只要固相还在）。
- **随 pH 上升而升高的是解离产物 [H₃SiO₄⁻]**（因为分母 [H⁺] 变小）。
- **总硅溶解度 = [H₄SiO₄] + [H₃SiO₄⁻] + ...**，所以**总溶解度随 pH 升高**。
- ⚠️ **讲义在这里把物种写错了**（写成 "the activity of H₄SiO₄ rises by an order of magnitude"），见勘误表——**跟着写会答错**。

### 6.9 海水硅少于河水，不是化学问题而是生物问题

- 按 pH 推断（海水 pH ≈ 8 更碱、硅更易溶；河水 pH ≈ 6），**海水的硅"应该"更多**。
- **实际相反，原因是硅藻（diatoms）等生物摄取造壳。**
- 讲义 Summary 的说法："In the oceans, precipitation of silica is **biologically mediated**."
- 这题老师课上提问**全场无人回答**——**高优先复习项**。

### 6.10 碳酸体系总方程"只解释珊瑚溶解"

- Kahoot 第 10 题**全班掉坑**（都选了 "all of the above"）。
- **CO₂ + H₂O ⇌ H₂CO₃ ⇌ H⁺ + HCO₃⁻ ⇌ 2H⁺ + CO₃²⁻ 只是一条化学方程式**：它解释**为什么加 CO₂ 会使 CaCO₃ 溶解**（珊瑚被溶蚀）。
- 它**不解释**海洋为什么变暖（那是辐射强迫），**也不解释**大气 CO₂ 为什么上升（那是排放）。
- **教训：不要把"化学机制"与"驱动原因"混为一谈。**

### 6.11 终点 ≠ 等当点

- **等当点**是化学计量上的理论点；**终点**是你实际看到信号的点；**两者之差是滴定误差**。
- 选指示剂的原则：**变色区间要尽量套住等当点的 pH**。强酸–强碱滴定等当点 pH = 7，所以溴百里酚蓝（6.0–7.6）比酚酞（8.3 起变）更合适。

### 6.12 酚酞在强碱中也是无色

- 酚酞：pH 0–8.3 无色，8.3–10 粉红，**>10 又变回无色**。
- **"无色"是二义的**——不能单凭无色判断酸碱性。这也是实验流程要求先用酚酞、褪色后再换甲基橙的原因（两段接力覆盖不同 pH 区间）。

### 6.13 矿物组合缓冲的失效条件

- 实验手册明确写道：**quartz + K-feldspar + muscovite 组合"只在所有单个矿物都还共存时"才起缓冲作用**。
- 讲座里 **X3 点** 是同一原理的图解：**gibbsite 一旦耗尽，"消耗硅酸"这个缓冲机制就失效，流体立即恢复原来的演化方向。**
- **通用原则：任何缓冲（无论是溶液缓冲对还是矿物组合缓冲）都有"弹药"上限，弹药打完缓冲就崩溃。**

---

## 七、本周术语表

| 中文 | English | 说明 |
|---|---|---|
| 酸度 | acidity | 溶液给出质子的能力；用强碱滴定测定 |
| 碱度 | alkalinity | 溶液接受质子／中和酸的能力；用强酸滴定测定 |
| 总碱度 | total alkalinity | 天然水中 ≈ 碳酸盐碱度 |
| 碳酸盐碱度 | carbonate alkalinity | Calk = [HCO₃⁻] + 2[CO₃²⁻] + [OH⁻] − [H⁺] |
| 总溶解固体 | total dissolved solids (TDS) | 高酸度水常伴随高 TDS，不宜饮用 |
| 解离 | dissociation | 物质进入水中分裂为离子 |
| 酸解离常数 | acid dissociation constant, Ka | pKa = −log Ka；pKa 越小酸越强 |
| 分步解离 | stepwise dissociation | 多质子酸逐级解离，每级各有 K |
| pH 缓冲液 | pH buffer | 加酸／加碱时能维持 pH 的溶液 |
| 缓冲容量 | buffering capacity / buffer capacity | pH 显著改变前能消耗的 H⁺ 或 OH⁻ 的量 |
| 亨德森–哈塞尔巴赫方程 | Henderson–Hasselbalch equation | pH = pKa + log([A⁻]/[HA]) |
| 水的离子积 | ion product of water, Kw | 25 °C 时 1 × 10⁻¹⁴；pKw = pH + pOH = 14 |
| 两性的 | amphoteric | 既能与 H⁺ 也能与 OH⁻ 反应，如 HCO₃⁻ |
| 碳酸 | carbonic acid, H₂CO₃ | pK₁ = 6.35（25 °C, 1 atm） |
| 碳酸氢根／重碳酸根 | bicarbonate / hydrogen carbonate, HCO₃⁻ | 海水缓冲的主力，两性 |
| 碳酸根 | carbonate ion, CO₃²⁻ | 碱度式中系数为 2 |
| 溶解无机碳 | dissolved inorganic carbon (DIC) | 📎 补充术语；CO₂+H₂CO₃+HCO₃⁻+CO₃²⁻ 之和 |
| 方解石／碳酸钙 | calcium carbonate, CaCO₃ | 海水 pH 缓冲的固相储库 |
| 海洋酸化 | ocean acidification | 海水 pH 由工业化前 8.2 降至现今约 7.9 |
| 酸雨 | acid rain | 局地／工业性的酸输入过程 |
| 酸休克 | acid shock | 低碱度水中 pH 的快速／瞬时变化，危害水生生物 |
| 钙化 | calcification | 生物用 CaCO₃ 造壳；酸化使其速率下降 |
| 浮游生物 | plankton | 用 CaCO₃ 造壳的海洋生物 |
| 二氧化硅／硅 | silica, SiO₂ | 可为非晶质或多种晶质形态 |
| 非晶质硅 | amorphous silica | 无晶体结构；溶解度约 109 ppm |
| 石英 | quartz | 晶质 SiO₂；溶解度约 5.9 ppm，约低 20 倍 |
| 方石英 / 鳞石英 | cristobalite / tridymite | SiO₂ 的其他晶质形态 |
| 硅酸 | silicic acid, H₄SiO₄ | 非晶质硅与水反应的产物；可分步解离 |
| 燧石 | chert | 非晶质硅凝胶脱水结晶而成 |
| 过饱和 | supersaturated | 河水相对石英过饱和 |
| 不饱和 | undersaturated | 河水相对非晶质硅不饱和 |
| 硅藻 | diatoms | 用硅造壳，是海水溶解硅低于河水的原因 |
| 生物介导的 | biologically mediated | 海洋中硅的沉淀由生物完成 |
| 铝硅酸盐 | aluminosilicate | 长石、云母等；风化是硅酸的主要来源 |
| 钠长石 | albite, NaAlSi₃O₈ | 溶解为产碱反应，1 mol 产 4 mol OH⁻ |
| 微斜长石 / 钾长石 | microcline / K-feldspar, KAlSi₃O₈ | K-Al-Si-H₂O 体系的起始相 |
| 高岭石 | kaolinite, Al₂Si₂O₅(OH)₄ | 黏土矿物，长石风化产物 |
| 白云母 | muscovite, KAl₃Si₃O₁₀(OH)₂ | 可与微斜长石共存 |
| 三水铝石 | gibbsite, Al(OH)₃ | 与微斜长石**不能**共存 |
| 矿物稳定图 | mineral stability diagram | log[H₄SiO₄] vs log([K⁺]/[H⁺]) 的相图 |
| 滴定 | titration | 用已知浓度标准溶液测定未知浓度 |
| 滴定剂 | titrant | 从滴定管加入的标准溶液 |
| 被分析物 | analyte | 待测组分 |
| 等当点 | equivalence point | 化学计量上恰好等量的理论点 |
| 终点 | end point | 实验上观察到信号的那一点 |
| 滴定误差 | titration error | 终点与等当点之差 |
| 指示剂 | indicator | 酸型／碱型颜色不同的物质 |
| 酚酞 | phenolphthalein | 0–8.3 无色，8.3–10 粉红，>10 无色 |
| 筛选甲基橙 | screened methyl orange | <3.1 红，>4.4 黄 |
| 溴百里酚蓝 | bromo-thymol blue | 6.0–7.6 由黄变蓝；适合强酸强碱滴定终点 |
| 电位滴定 | potentiometric titration | 以电位差指示终点 |
| 电导滴定 | conductometric titration | 以电导／电阻指示终点 |
| 电流滴定 | amperometric titration | 以电流指示终点 |
| 沉淀滴定 | precipitation titration | 以有色沉淀出现指示终点 |
| 络合滴定 | complex-formation titration | 常用 EDTA 滴定金属离子 |
| 氧化还原滴定 | redox titration | 指示剂在终点附近被氧化或还原 |
| 弯月面 | meniscus | 读数须眼睛齐平、读曲线最低点 |
| 视差 | parallax | 视线不齐平造成的读数误差 |
| 移液管 / 滴定管 / 容量瓶 | pipette / burette / volumetric flask | 三类容量玻璃器皿 |
| 质量摩尔浓度 | molality (m) | mol / kg 溶剂 |
| 体积摩尔浓度 | molarity (M) | mol / L 溶液；1 M = 1000 mM |
| 系列稀释 | serial dilution | 逐级等量稀释 |
| 最小二乘拟合 | least squares fitting | 客观确定最佳拟合直线 |
| 因变量 / 自变量 | dependent / independent variable | 分别绘于 Y 轴 / X 轴 |
| 动力学 | kinetics | 石英在河水中不沉淀的原因 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| **归档问题**：`Practical/Week 8/EART26201 lab handbook 2025-1.md` | 整份 21,717 词的手册置于 Week 8 文件夹 | 该文件是**全课通用实验手册**（含安全守则、通用技能、EXPERIMENT 1 与 EXPERIMENT 2），并非 Week 8 专属材料 | 属材料归档问题，非内容错误。本周只取用 665–1003（通用技能，末尾含属于 W07 的 EXPERIMENT 1）与 1004–1278（EXPERIMENT 2，本周实验）两段；65–664 的安全守则留待阶段二课程级笔记统一处理 |
| **周次错位**：`(EART26201) Principles of Geochemistry.md`，Syllabus 一节 | 大纲列 "Week 8: Acids, bases and solubility"；"Week 9: Carbonates and the carbon cycle"；practical "Week 9: Buffering and alkalinity" | 大纲从 Week 2 排到 Week 12（含 reading week），与文件夹的 Week 1–10 连续编号错位 | 非错误，是编号体系差异。**本笔记库统一采用文件夹编号，即本周为 Week 08**。文件夹 Week 8 的实际内容（buffering / alkalinity / silica + Experiment 2）对应大纲的 Week 8 后半与 Week 9 |
| 讲义 `lecture 8 ... v2-1.md`，"pH and silica solubility" 一节 | "At pH = 8.0 **the activity of H₄SiO₄** rises by an order of magnitude because [H⁺] decreases by factor of ten" | **物种写错**。只要非晶质硅固相存在，[H₄SiO₄] 由 SiO₂ + 2H₂O ⇌ H₄SiO₄ 的平衡固定在 1.82 × 10⁻³，**不随 pH 变化** | 应为 **H₃SiO₄⁻**。转写中老师的口述是正确的：pH 8 时 [H₃SiO₄⁻] 从 3.55 × 10⁻⁶ 升为 3.55 × 10⁻⁵。**升高的是解离产物，不是硅酸本身**；总硅溶解度因此上升 |
| 转写 `EART26201 - 24-Nov-transcript.md`，约 469–474 行 | "at 0 degrees C pure water is actually **slightly alkaline**" | **概念错误**。0 °C 时 Kw 变小、中性 pH 移到 7.47，但纯水仍满足 [H⁺] = [OH⁻]，**依然是中性的** | 应表述为："0 °C 时纯水的 pH 为 7.47，但它仍然中性——中性的判据是 [H⁺] = [OH⁻]，不是 pH = 7。" 讲义本身写的 "at 0 °C pure water has a pH of 7.47" 是正确的，未称其为碱性 |
| 转写，约 157–165 行 | "alkalinity… it's the capacity to accept those **electrons** that acids are able to donate" | **口误／转写错误**：应为**质子（protons）**，不是电子 | 碱度是接受**质子**的能力。讲义原文正确："capacity to accept protons" |
| 转写，约 350–355 行 | "some of it does naturally split up into H plus and now **H minus**" | 语音转写错误 | 应为 **OH⁻（hydroxide，氢氧根）** |
| 转写，约 1193–1198 行 | "Calcium carbonate dissolves, you get **CO2 plus** and then CO3 2 minus" | 语音转写错误 | 应为 **Ca²⁺（calcium ion）** |
| 转写，约 1350–1360 行 | "produces **1.82 times 3 moles** times 60, which is the molecular mass, is 0.1 grams per kilogram" | 语音转写错误 | 应为 **1.82 × 10⁻³ mol/kg**。数值已复核：1.82 × 10⁻³ × 60.084 = 0.1094 g/kg = **109 ppm ✓** |
| 转写，全文多处 | "salicylic acid"（水杨酸）、"solidic acid"、"acidic acid"、"microclime"、"microfine"、"all-byte"、"Anderson-Hasselbalck"、"Henson Hasselbalch"、"K over 90" | **自动语音识别（ASR）的专名转写错误**，集中出现 | 分别应为 **silicic acid（硅酸）、microcline（微斜长石）、albite（钠长石）、Henderson–Hasselbalch、kaolinite（高岭石）**。阅读转写时需自行还原 |
| 实验手册，第 1028 行（EXPERIMENT 2 · BUFFERS AND MINERALS） | `SiO2 (quartz) + 2H2O (aq) ⇋ H2SiO4 (aq)` | 化学式写错（**H₂SiO₄**），且水的相态标注为 (aq) 不妥 | 应为 **H₄SiO₄**（下一行的逆反应式写的正是 H₄SiO₄，自相矛盾）；水应标 **(l)** |
| 实验手册，第 1093–1109 行（缓冲容量算例） | "10 ml of 0.1M HCl is added to **1 litre** of buffer… [A⁻] = 0.1 − 0.001 = 0.09" | **忽略了体积稀释**：加入 10 ml 后总体积为 1.01 L，各浓度都应再除以 1.01 | 属教学简化，对结论（pH 从 4.74 仅降到 4.65）无实质影响，但严格计算时应考虑。答题若被要求"精确计算"须补上此项 |
| 实验手册，第 1068 行 | `[A-] = [Na+] + [H+]  (from charge balance)` | **电荷平衡式不完整**：完整式为 [Na⁺] + [H⁺] = [A⁻] + [OH⁻]，故 [A⁻] = [Na⁺] + [H⁺] − [OH⁻] | 在酸性缓冲液（pH ≈ 4.74）中 [OH⁻] ≈ 10⁻⁹，可忽略，故简化成立。但**在碱性缓冲体系中不能这样省略** |
| 讲义，Henderson–Hasselbalch 一节 | `NaAlSi3O8 + 2H2O = 4OH- + Na+ + Al3+ + 3SiO2(aq)` | **配平正确**（两侧均为 NaAlSi₃O₁₀H₄，电荷两侧均为 0），但**化学上不合理**：游离 Al³⁺ 与 4 个 OH⁻ 不可能在同一溶液中共存 | 属教学简化写法，目的只是导出"1 mol 钠长石 → 4 mol OH⁻"这一化学计量关系。真实体系中 Al 会以 **Al(OH)₄⁻** 或沉淀为 **gibbsite Al(OH)₃** 存在（讲座后半段的矿物稳定图正是这么处理的）。**答题时若被要求写钠长石水解的真实反应，不应照抄此式** |
| 讲义，pH scale 一节 | `pOH = -log[OH-]   pK = pOH + pH = 14` | 记号不严谨：此处的 pK 特指**水的离子积**，写成 pK 容易与酸的 pKa 混淆 | 应写作 **pKw = pOH + pH = 14**，并注明条件为 **25 °C、1 atm** |
| 讲义，Alkalinity 一节 | "Calk = [HCO3-] + 2[CO32-] + [OH-] – [H+]" 之外未定义 DIC，且未给 pK₂ | **不算错误，属内容缺口** | 讲义只给了 pK₁ = 6.35，**未给碳酸的 pK₂，也没有 Bjerrum 图**。本笔记第 3.7 节的 pK₂ = 10.33、种态分布区间等均已用 📎 标出为补充内容 |
| `lecture 8 quiz answers 2024.md`，Slide 1 | 文件名标注为 **2024**，但 OCR 出的幻灯片内容显示 "Lecture 8 **2023**"，且 Kahoot 元数据显示 "GregHolland2017 / Updated 1 week ago" | **版本标注不一致** | 本周未发现该测验与讲义内容有实质矛盾（12 题的答案与讲义、转写完全一致），故无需按"以讲义为准"作修正。但该文件 OCR 质量很低（第 4 张幻灯片手册注明"识别质量低"），**选项文本大量不可读，仅能作线索**；本笔记第 4.6 节的题目与答案主要依据**转写中老师的口头讲评**重建，可信度更高 |
| 讲义全文 | 多处公式被 PDF 转换打乱，如 `SiO O ⇋ H SiO K = 1.82 × 10-3 2 + 2H2 4 4`、`HA + H O ⇋ H+ + A- + H O 2 2`、`CO + H O ⇋ H CO H+ + HCO - ⇋ 2H+ + CO 2- 2 2 2 3 ⇋ 3 3` | **PDF → Markdown 转换导致下标数字与主体文字分离错位**，并非讲义原件错误 | 阅读时需还原为：`SiO₂ + 2H₂O ⇌ H₄SiO₄`、`HA + H₂O ⇌ H⁺ + A⁻ + H₂O`、`CO₂ + H₂O ⇌ H₂CO₃ ⇌ H⁺ + HCO₃⁻ ⇌ 2H⁺ + CO₃²⁻`。本笔记正文已按还原后的形式呈现并注明 |

**已逐一复核、确认无误的数值**（列出以备查）：
- 60.084 × 1.82 × 10⁻³ = 0.1094 g/kg ≈ **109 ppm** ✓
- (1.95 × 10⁻¹⁰ × 1.82 × 10⁻³) / 10⁻⁷ = **3.55 × 10⁻⁶** ✓；1.82 × 10⁻³ / 3.55 × 10⁻⁶ = **513 ≈ 500 倍** ✓
- −log(0.08) = **1.097 ≈ 1.1**；14 − 1.1 = **12.9** ✓
- 12.5 mM 钠长石 × 4 = **50 mM OH⁻**；6.35 + log(50/50) = **6.35** ✓
- 20 mM 钠长石 × 4 = **80 mM OH⁻**；6.35 + log(80/20) = 6.35 + 0.602 = **6.95** ✓
- −log(1.82 × 10⁻⁵) = **4.74**（醋酸 pKa）✓
- 4.74 + log(0.09/0.11) = 4.74 − 0.087 = **4.65** ✓
- 109 / 5.9 = **18.5 ≈ 20 倍**（非晶质硅 vs 石英）✓
- 微斜长石 → 高岭石反应配平：两侧均为 **K₂Al₂Si₆O₂₅H₂₀** ✓
- 钠长石反应配平：两侧均为 **NaAlSi₃O₁₀H₄**，电荷两侧均为 0 ✓
- 📎 K₁(H₄SiO₄) = 1.95 × 10⁻¹⁰ 对应 pK₁ = 9.71；文献常见值在 pK₁ = 9.7–9.9 之间，讲义取值在合理范围内
