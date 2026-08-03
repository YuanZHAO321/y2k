# EART26201 Principles of Geochemistry — Week 06 学习笔记

> 材料范围：`Lecture/Week 6/lecture 6 ions in solution 2025.md`（幻灯片）、`Lecture/Week 6/EART26201 - 10-Nov-transcript.md`（课堂录音转写，10 Nov）、`Lecture/Week 6/lecture 6 quiz answers 2024.md`（**2024 旧版 + OCR 质量低**）、`Practical/Week 6/EXPERIMENT 1 2025-1.md`。
> 编号说明：课程大纲（spec）把本讲排在 "Week 8: Acids, bases and solubility"，但大纲含 reading week 且从 Week 2 起编号，与文件夹的 Week 1–10 连续编号错位一格。**本笔记库一律采用文件夹编号，故本讲为 Week 06。**

---

## 一、本周主题

本周是全课的**分水岭**：讲义首页写着 **"EART26201 part 2: fluid geochemistry"**（流体地球化学）。转写里老师开场交代了分工：前五讲由另一位讲师（转写作 "Romant"，ASR 误听）负责 "rock geochemistry, hard, solid geochemistry"，从本周起换成 Greg Holland 讲 "fluid geochemistry"，"inherently it's to do with more shallower depths"——研究深度比前五周浅，主要是地表与浅部地壳的水岩作用。

**Part 2 的五讲提纲（讲义原文）**：

1. Water as a solvent – ions（水作为溶剂——离子）← **本周**
2. Solubility and complexing（溶解度与络合）
3. Acids and bases（酸与碱）
4. Redox reactions（氧化还原反应）
5. Stable isotopes in the hydrologic cycle（水循环中的稳定同位素）

**在全课四大块骨架中的位置**：本周开启第三块「酸碱溶解度与氧化还原」（水溶液地球化学），是**知识枢纽**——

- **向前衔接**：Week 3–4 的热力学建立了「平衡」「理想／非理想」「标准态」框架，本周把它从固相／熔体搬到水溶液，得到的就是**活度系数（activity coefficient）**；Week 5 的动力学讲「多快」，本周的平衡常数讲「最终到哪」（转写强调平衡是**正逆反应速率相等**的动态平衡，正是动力学的语言）。
- **向后衔接**：活度、离子强度、Ka／pKa、Henderson–Hasselbalch 是 Week 7（溶解度与络合）、Week 8（缓冲与碱度）、Week 9（氧化还原）、Week 10（稳定同位素）全部要用的工具。老师原话："whenever I talk about concentrations in any other lecture, I'll actually mean activity."
- 📎 背景补充：跨课程上直接喂给 **EART26001 能源与资源**（热液成矿的金属氯络合、铀的迁移、蒸发岩）与 **EART23202 地层记录**（碳酸盐成岩、方解石溶解／沉淀）。

**本周同时是实验课的起点**，Practical 材料自本周起变为 **EXPERIMENT 系列**。转写说明了新节奏：本周去 Williamson 楼一楼化学实验室 **1.18** 做实验，**下周**做 write-up；再隔一周做第二组实验并写一次；最后一周在 G12 做纸笔练习。老师另宣布本单元**每周课末做 Kahoot 小测**（有巧克力奖品），把 50 分钟理论课切成 30 分钟讲授 + 小测。

---

## 二、核心概念

### 1. 基础复习：原子、amu 与摩尔

- 以 **¹²C = 12.00000 amu** 为参照定义原子质量单位。转写强调这是**人为约定**："carbon-12 is what we're going to use as our whole number of mass units, and everything else is referenced to that"——所以只有 ¹²C 是整数，其他核素都不是。
- **1 mole = 6.02252 × 10²³ 个原子**（Avogadro's number），作用是把「原子个数」和「克」互换：1 mol ¹²C = 12 g，1 mol H = 1 g。
- 讲义粒子表（原文数值）：

| Particle | Symbol | Charge (C) | Mass (amu) |
|---|---|---|---|
| Proton 质子 | Z | +e = 1.6021 × 10⁻¹⁹ | 1.007825 |
| Neutron 中子 | N | 0 | 1.008665 |
| Electron 电子 | e | −e = 1.6021 × 10⁻¹⁹ | 0.0005486 |

- **核结合能（binding energy）**：把 6 个质子 + 6 个中子 + 6 个电子的质量加起来，得 12.098931 amu，比 12.00000 多出 **Δm = 0.098931 amu**，这就是**质量亏损**，对应结合能 E = mc²。老师明说这个不必担心，"whenever you do calculations using atomic masses... you can just get them out of the book"。（⚠️ 表中质子质量数值有问题，见勘误表第 1 条。）

### 2. 化学计量：gram-formula mass、molarity 与 molality

- **克式量（gram-formula mass）**：1 mol 物质的质量（g）在数值上等于其式量（amu）。讲义算例 NaCl：22.9 + 35.45 = 58.35 amu → 58.35 g/mol。转写补了一个有用的细节：**Cl 的 35.45 不是整数，是因为约 3/4 的氯是 ³⁵Cl、1/4 是 ³⁷Cl 的加权平均**（同位素丰度平均）。
- **Molarity（体积摩尔浓度，大写 M）**：每**升溶液**中溶质的摩尔数。做法：把 1 mol 溶质放进 1 L 容量瓶，加水**定容到 1 L 刻度**。
- **Molality（质量摩尔浓度，小写 m）**：每**千克溶剂**中溶质的摩尔数。做法：称 1 kg 水，再加入 1 mol 溶质。
- **两者的区别与何时可以混用**：溶剂是水时，室温下 1 L 水 ≈ 1 kg，所以 M ≈ m；但转写特别强调 **"if you were dissolving something in alcohol, for example, then it would be quite a big discrepancy"**——非水溶剂时二者差别很大。地球化学惯例：**活度用 molality 表示**（mol/kg H₂O）。

### 3. 水作为溶剂：为什么水这么特殊

水是地球上最丰富的液体，是"the medium in which chemical reactions take place in nature"。转写里老师花了很长时间说服学生**水控制地下的一切化学反应**：

> "as soon as you go underground, unless you're above a water table, everything is saturated with water... inside the earth, everywhere is wet. There's no gaps."

你在野外／手标本／显微镜下看到的是"干"的岩石，但地下孔隙全是水；**是水提供了参与反应的原子，也是水把原子搬来搬去**，矿物才能溶解和沉淀。

**水的四个反常性质（讲义原文四条）**：

1. **沸点异常高**——比分子量更大的同类氢化物（如 H₂S）还高，所以地表条件下是**液体**而 H₂S 是气体。
2. **热容极高**——海洋因此是地球气候的**热汇（heat sink）**。转写补："I guess the oceans are struggling now"，但地质时间尺度上一直是缓冲器。
3. **最大密度出现在 4 °C**——所以**冰浮在水面**。讲义把它做成讨论题 **"what would happen if it did?"**（若冰下沉会怎样）：海洋若从底部往上冻结、不再循环、不再与地壳相互作用，地球会完全不同。（📎 背景补充：答题方向——锁死深层水循环、抑制热盐环流、断绝深海与地壳的水岩交换，且冰无法靠夏季表面融化逆转。**材料只提问未给答案**。）
4. **是离子化合物的优良溶剂**——能把化合物**解离（dissociate）**成正负离子。

**极性与介电常数**：

- 水分子 H 端带部分正电、O 端带部分负电 → **偶极（dipole）**；**高介电常数是水极性的量度，也是其溶解能力强的原因**（大幅屏蔽正负离子间的库仑吸引）。
- **纯水是强介电体（strong dielectric）＝电绝缘体**。转写举例："we're all told not to charge our phones in the bath... actually pure water wouldn't be a problem"——导电的是水里的**离子**。实验室的**去离子水（deionised water）**就是把离子剥掉的水。
- **水合（hydration）**：溶解出的离子被偶极水分子包围（阳离子被 O 端吸引、阴离子被 H 端吸引），**阻止它们重新结合**成固体。
- **氢键（hydrogen bonding）**：一个水分子的 O 吸引另一个水分子的 H。转写指出氢键同时解释三件事：①室温下是液体；②固态形成比液态**更疏松的晶体结构** → 冰浮；③极性使其能拆散离子化合物。

### 4. 电解质溶液（electrolyte solutions）

NaCl 溶于水：**NaCl(s) ⇌ Na⁺(aq) + Cl⁻(aq)**，得到水合阳离子和水合阴离子。推论链条：

水极强的溶解离子化合物能力 → **自然界的水几乎总含溶解离子**（aqueous solution）→ 溶解离子是带电粒子＝**电解质（electrolytes）**，能导电 → **天然水溶液都是电解质溶液**。纯水只在化学实验室里才有。

### 5. 理想溶液 vs 非理想溶液：活度（activity）

这是本周最核心的新概念。逻辑链（讲义原文＋转写）：

- **极稀溶液中离子彼此不相互作用**——这就是水溶液中离子的**标准态（standard state）／理想溶液（ideal solution）**。
- 浓度升高后，离子开始相互作用 → **非理想溶液**；**某个离子的化学势（chemical potential）会取决于其他离子的浓度**。
- 相互作用分两类：
  - **专属性的（specific）**：离子对（ion pairs）、络合物（complexes）——这正是本周实验的主题；
  - **非专属性的（non-specific）**：**长程库仑相互作用（long-range coulombic interactions）**。
- 结果：**水溶液中离子和分子间的化学反应往往不是其浓度的直接函数**。
- 📎 背景补充：这与 Week 4 相图里固溶体的「理想混合 vs 非理想混合」是同一个思想——理想＝只有构型熵、无额外相互作用能；非理想＝需要引入活度系数把"有效浓度"修正回来。转写里老师直接用**理想气体定律**作类比："If you've got a small number of gas atoms floating around in a particular volume, it will behave ideally. But when you get lots of higher gas pressure, it behaves non-ideally."

**活度与活度系数**：

- 用**活度 a** 取代浓度，**a = γ·m**（γ 为活度系数，m 为质量摩尔浓度）。
- **活度用 molality 表示**（mol 溶质 / kg 水）。
- γ 的物理意义：**修正（实际上是折减）其他离子干扰造成的浓度偏差**。
- 讲义断言 **γ < 1**，即**有效浓度（活度）小于实际浓度**。（⚠️ 这是过度概括，见勘误表第 7 条。）
- **极稀溶液中 a ≈ m**，活度与浓度的差别可以忽略。
- 个别离子的 γ 由 **Debye–Hückel 理论及其扩展式**计算（讲义只给出处 **Misra 7.2.3**，**未给公式本身**）。
- ⭐ **考试提示（转写原话）**："I would never ask you an exam question about **why** activity is the way it is. It's just something you need to be aware of." —— 不考活度的微观理论根源，但**必须会用、必须认得这个词**。

### 6. 离子强度（ionic strength, I）

- 定义：**溶液中离子浓度与电荷的综合量度**；转写口述式定义为"所有离子浓度乘以其电荷平方之和的一半"。
- **典型数值（讲义原文）**：
  - 大多数天然水：**I < 0.1 mol/kg**
  - 恒河河水（Ganges）：**I = 0.0034 mol/kg**
  - **海水：I = 0.685（讲义另一处写 0.7）mol/kg**
  - **油田卤水（oilfield brines）：可达海水的 5 倍**（≈ 3.5 mol/kg）
- **H⁺ 与 OH⁻ 通常不计入**：因为中性溶液中它们的浓度只有 10⁻⁷ mol/kg，贡献可忽略。
- 转写补充：海水里 **Na 接近 0.5 mol/kg**（"almost half a mole of sodium per kilogram of seawater"），主要就是 Na⁺ 和 Cl⁻ 把 I 顶上去的；地下流体（subsurface fluids）还会富集各种金属离子和阳离子。

### 7. γ 与 I 的关系（本周最重要的定量结论）

**两条关键规律（讲义 Key points）**：

1. **γ 随离子电荷增大而减小**（z 越大，修正越狠）；
2. **γ 随离子强度 I 增大而减小**。

直观理解：**离子"干扰（interference）"**——溶液里离子越多，彼此干扰越强，"你得到的是表观浓度而不是真实浓度"。

**定量算例（讲义 + 转写反复强调）**：

| 水体 | I (mol/kg) | γ(Ca²⁺) | 含义 |
|---|---|---|---|
| 恒河河水 | 0.0034 | ≈ **0.80** | 有效浓度比实际**低 20%** |
| 海水 | 0.685 | ≈ **0.26** | 有效浓度比实际**低 74%**（只剩 26%） |

老师强调："it can be a really, really big effect... if you were doing these calculations from first principles, you have to make that correction." 但随即又说，后面的课里"we'll just assume that we've done that"（默认已经改正过了）。

### 8. 平衡常数与质量作用定律（Law of Mass Action）

- **反应是双向的**：A + B → C + D 的同时 C + D → A + B；当**正逆反应速率相等**时达到**平衡（equilibrium）**，宏观上看不出变化，但微观上仍在双向进行。老师强调流体中"this will always be the case"。
- 对 **aA + bB ⇌ cC + dD**，平衡常数 **K = [C]^c[D]^d / ([A]^a[B]^b)**；a、b、c、d 是配平方程中的**化学计量系数**；方括号是**平衡时**的浓度（严格说应为活度）。
- 讲义例子：**H₂(g) + I₂(g) ⇌ 2HI(g)**，**K = [HI]² / ([H₂][I₂])**——指数 2 来自配平系数。

### 9. 酸碱：Arrhenius 定义与解离常数

**Arrhenius 定义（讲义原文）**：

- **酸（Acid）**：含 H 的化合物，溶于水时解离 → 释放 **H⁺（质子）** → **降低 pH**；H⁺ 与水结合形成**水合氢离子 H₃O⁺(aq)（hydronium）**。
- **碱（Base）**：含 OH 基团的化合物，溶于水时解离 → 释放 **OH⁻（氢氧根）** → **升高 pH**；OH⁻ 与水结合形成水合离子。

**解离常数（dissociation constants）**：

- 酸 HₘAₙ ⇌ mH⁺ + nA^(...)：**Ka = [H⁺]^m[A]^n / [HₘAₙ]**
- 碱 B_pOH_q ⇌ pB + qOH⁻：**Kb = [B]^p[OH]^q / [B_pOH_q]**

**强弱酸碱**：

- **强酸**（如 HCl）在水中**几乎完全解离**；**弱酸**（如乙酸 CH₃COOH）只有小部分解离（**Ka ≪ 1**）。碱同理。
- ⚠️ **不要把"强度（strength，解离程度）"和"浓度（concentration，溶解量）"混为一谈**。转写讲得最清楚："a strong acid is something that splits up a lot, but it might be low in concentration, whereas a **high concentration of something that doesn't split up very easily still won't give you a low pH**."
- **解离度 %D = (已解离量 / 原始溶解量) × 100**
- **pH 量度溶液的酸度**（取决于酸碱的浓度和种类）；**pKa 量度酸的强度（解离能力）**（碱用 pKb）。

### 10. pKa、ladder diagram 与 Henderson–Hasselbalch

- **pKa = −log Ka**，**pH = −log[H⁺]**。转写解释了 "p" 就是取负对数，并顺带解释了 **pH 为什么"反着走"**："when you get more hydrogen ions, the pH goes down because it's the minus log."
- **符号规则（讲义原文）**：
  - Ka < 1 → pKa 为**正**
  - Ka = 1 → pKa = 0
  - Ka > 1 → pKa 为**负**
  - **Ka 越大 → 解离程度越高 → 溶液越酸**
- **Ladder diagram（阶梯图）**：教科书里以 pKa 为唯一纵轴刻度的图。**顶端是负 pKa 的强酸**（解离得最彻底），往下 pKa 增大、酸性变弱，中段是常见天然水的 "normal pH range"。老师给的算例：Ka = 10 → pKa = −log(10) = −1。
- **Henderson–Hasselbalch 方程**：

  **pH = pKa + log([A⁻]/[HA])**

  推导思路（转写口述）：把 Ka = [H⁺][A⁻]/[HA] 解出 [H⁺]，两边取负对数，利用 **−log(A/B) = log(B/A)** 把比值翻过来即得。老师说这条对数规则"just accept it"。
- ⭐ **地球化学用途（老师明确点出这是本周最有用的工具）**：野外采样时**测得 pH**，再从书上**查 pKa**，就能算出某个分子**有没有解离、解离到什么程度**——"if it has split up and ions are in solution, it's those ions that can then go on to react with different things."

**讲义例题——酚酞（phenolphthalein）**

pKa = 9.3（室温）；A⁻ 为**粉红色**，HA 为**无色**。

- pH 8.2：8.2 = 9.3 + log(A⁻/HA) → log(A⁻/HA) = −1.1 → A⁻:HA = 10^(−1.1) = **0.08 : 1**（即 8 : 100）
- pH 10：10 = 9.3 + log(A⁻/HA) → log(A⁻/HA) = +0.7 → A⁻:HA = 10^0.7 = **5.01 : 1**（即 501 : 100）

结论：pH 8.2 时粉色分子只占极少数（几乎无色）；pH 10 时粉色分子是无色的 5 倍，**所以随 pH 升高显粉红**。老师强调这套算法"can apply to any ions in solution"。

### 11. 矿物的酸碱性质

**大多数矿物与水反应会升高 pH（产生 OH⁻）**：

- 正长石 → 高岭石：2KAlSi₃O₈ + 2H₂O → Al₂Si₂O₅(OH)₄ + 2OH⁻ + 2K⁺（⚠️ 讲义此式未配平，见勘误第 9 条）
- 橄榄石 → 蛇纹石（叶蛇纹石 chrysotile）：2Mg₂SiO₄ + 3H₂O → Mg₃Si₂O₅(OH)₄ + Mg²⁺ + 2OH⁻
- 方解石：CaCO₃ + H₂O → HCO₃⁻ + Ca²⁺ + OH⁻

**少数矿物与水反应会降低 pH**：

- 黄钾铁矾（jarosite）：KFe₃(SO₄)₂(OH)₆ + 3H₂O → K⁺ + 3Fe(OH)₃ + 2SO₄²⁻ + 3H⁺

老师总结："in fluids in the subsurface, **most reactions will tend to produce alkaline solutions rather than acidic solutions**"；同时预告 **"carbonate geochemistry is a little bit more complicated than I've given it credit for here"**（碳酸盐体系留到 Week 8／Week 9 细讲）。

📎 背景补充：黄钾铁矾产酸正是**酸性矿山排水（acid mine drainage, AMD）**的核心反应之一，硫化物氧化 → Fe³⁺ 水解 → 释放 H⁺；这条线索会在 Week 9 氧化还原和 EART26001 的矿床／环境部分再出现。

### 12. 📎 背景补充：水的自解离与 pH 的定义基准（讲义未讲、小测考了）

转写里老师在小测环节自己承认 **"I didn't really talk about this, but water itself actually does slightly dissociate"**——**讲义正文没有讲水的自解离**，但小测考了。补齐：

- **H₂O ⇌ H⁺ + OH⁻**（严格写作 2H₂O ⇌ H₃O⁺ + OH⁻）
- **Kw = a(H⁺)·a(OH⁻) = 1.0 × 10⁻¹⁴（25 °C）**，故 pKw = 14
- 纯水中 [H⁺] = [OH⁻] = 10⁻⁷ mol/kg → **中性 pH = 7**（这也解释了讲义为何说"中性溶液中 H⁺、OH⁻ 浓度只有 10⁻⁷ mol/kg，可不计入离子强度"）
- ⚠️ Kw 随温度显著变化：100 °C 时 pKw ≈ 12.3，中性 pH ≈ 6.1。**"pH 7 = 中性" 只在 25 °C 成立**，在热液体系中不成立——这一点对 Week 10（热液系统）很关键。

### 13. 📎 背景补充：络合（complexing）预告

转写中老师说 "there's things called long range Coulomb interactions and **ion complexing**, which is sort of complicated bonding between water and cations in solution. We'll do a complexing experiment in the practical." **本周讲义没有展开络合理论**，它是 Week 7 的正题，但**本周实验先做**。基本概念见第五段。

---

## 三、公式与图表

### 公式清单

| 公式 | 符号与单位 | 适用条件 / 典型值 |
|---|---|---|
| 1 amu = (1/12 × 12.00000) / (6.02252 × 10²³) = **1.66043 × 10⁻²⁴ g** | amu：原子质量单位 | 以 ¹²C 定义；换算常数 |
| A = Z + N | Z 质子数（原子序数）、N 中子数、A 质量数 | A 是**无量纲**的核子数（讲义写作 amu，见勘误 2） |
| Δm = Σ(核子质量) − 实测核质量 = 12.098931 − 12.00000 = **0.098931 amu** | Δm 质量亏损 | E = mc²，核结合能 |
| 克式量 = 式量（amu）的克数 | g/mol | NaCl：22.9 + 35.45 = 58.35 g/mol（正确值应为 58.44，见勘误 3） |
| **Molarity M = n(溶质) / V(溶液, L)** | mol/L | 定容法；温度敏感（体积随 T 变） |
| **Molality m = n(溶质) / m(溶剂, kg)** | mol/kg | 称重法；**温度无关**，地球化学首选 |
| **a = γ · m** | a 活度（无量纲）、γ 活度系数（无量纲）、m 质量摩尔浓度 mol/kg | γ → 1 时为理想溶液；γ 通常 < 1 |
| **I = ½ Σ mᵢ zᵢ²** | I 离子强度 mol/kg、mᵢ 第 i 种离子的质量摩尔浓度、zᵢ 其电荷数 | **z 要平方**，所以高价离子贡献极大；一般不计 H⁺／OH⁻。天然水 < 0.1；恒河 0.0034；海水 0.685；油田卤水 ~3.4 |
| **K = [C]^c[D]^d / ([A]^a[B]^b)** | K 平衡常数（无量纲）；小写字母为化学计量系数 | 平衡时；严格应用活度而非浓度 |
| **K = [HI]² / ([H₂][I₂])** | — | H₂ + I₂ ⇌ 2HI 的具体形式 |
| **Ka = [H⁺]^m[A]^n / [HₘAₙ]** | Ka 酸解离常数 | 强酸 Ka ≫ 1；弱酸 Ka ≪ 1 |
| **Kb = [B]^p[OH]^q / [B_pOH_q]** | Kb 碱解离常数 | 同上 |
| **%D = (已解离量 / 原始溶解量) × 100** | % | 量化"强度" |
| **pKa = −log Ka**；**pH = −log[H⁺]** | 无量纲 | Ka=10 → pKa=−1；Ka=1 → pKa=0 |
| **pH = pKa + log([A⁻]/[HA])** | Henderson–Hasselbalch | 单质子弱酸；pH = pKa 时 A⁻:HA = 1:1 |

### 📎 背景补充：Debye–Hückel 公式（讲义只给了名字和参考章节 Misra 7.2.3，未给式子）

考试若要求算 γ，最可能用到以下三式之一（25 °C）：

- **极限定律（Debye–Hückel limiting law）**：**log γᵢ = −A zᵢ² √I**，A ≈ 0.5085 (kg/mol)^½。适用 **I < 0.005 mol/kg**（极稀）。
- **扩展式（extended Debye–Hückel）**：**log γᵢ = −A zᵢ² √I / (1 + B åᵢ √I)**，B ≈ 0.3281 Å⁻¹(kg/mol)^½，åᵢ 为离子的**有效水合半径**（Ca²⁺ 约 6 Å）。适用 **I < 0.1 mol/kg**（涵盖绝大多数天然河水、地下水）。
- **Davies 方程**：**log γᵢ = −A zᵢ² [√I/(1+√I) − 0.3 I]**，可用到 **I ≈ 0.5 mol/kg**。

用扩展式验算讲义的恒河数据：I = 0.0034 → √I = 0.0583 → log γ = −0.5085 × 4 × 0.0583 / (1 + 0.3281×6×0.0583) = −0.106 → **γ(Ca²⁺) ≈ 0.78**，与讲义的 0.80 吻合良好。海水 I = 0.685 已超出上述公式的可靠范围（Davies 算得约 0.31，实测约 0.26），**这正是为什么海水需要专门的 Pitzer 模型**。

### 图表描述

**图 1：γ 对 log I 的关系图（本周最重要的图）**
横轴为**离子强度 I 的对数坐标**，范围约 **0.001 → 1**；纵轴为**活度系数 γ**，从 1 向下递减。图上有一族曲线，每条对应一种离子（Na⁺、Ca²⁺、Al³⁺ 等）。所有曲线都**自左上向右下倾斜**：I 越大 γ 越小。**曲线按电荷分层**——**Na⁺（+1）位置最高、下降最慢；Ca²⁺（+2）居中；Al³⁺（+3）最低、下降最快**（老师原话：铝"suffered the most"）。图上标了两条竖虚线：**恒河河水 I = 0.0034** 与 **海水 I = 0.685**；在恒河线上读 Ca²⁺ 曲线得 γ ≈ 0.80，在海水线上读得 γ ≈ 0.26。**读图的两个结论就是 Key points：γ 随电荷增大而降、随 I 增大而降。**

**图 2：海水中离子的种态（ion speciation in seawater）表／图**
讲义给出海水主要溶解组分的**质量摩尔浓度（molalities）**清单，用来演示离子强度计算。转写点明关键读数：**Na 接近 0.5 mol/kg**；正是 Na⁺ 与 Cl⁻ 的高浓度使海水成为强烈非理想的溶液。📎 背景补充：海水（S = 35）主要组分约为 Cl⁻ 0.566、Na⁺ 0.486、Mg²⁺ 0.055、SO₄²⁻ 0.029、Ca²⁺ 0.0106、K⁺ 0.0106 mol/kg，代入 I = ½Σmz² 得 I ≈ 0.72，与讲义的 0.685–0.7 一致。

**图 3：水分子极性与水合示意（取自 Misra 教材）**
一个"米老鼠头"形的水分子：两个 H 端标 **δ⁺**，O 端标 **δ⁻**。多个水分子之间用虚线连接 O···H，表示**氢键**。另一幅卡通图中，中心是一个 **阳离子（cation）**，周围一圈水分子把**带负电的 O 端朝向阳离子**；阴离子周围则相反，H 端朝内。这幅图同时解释了：解离、水合、防止复合、氢键导致的高沸点与冰的疏松结构。

**图 4：pKa ladder diagram（阶梯图）**
纵轴为 pKa 的一维刻度。**顶端标 "strong acids"，pKa 为负**（Ka > 1，解离彻底）；向下 pKa 递增、酸性递减；中段标注 **"Normal pH range"**（天然水的常见 pH 区间）。旁注三条判据：Ka<1→pKa 正；Ka=1→pKa=0；Ka>1→pKa 负。

**图 5：Ca²⁺ 质量摩尔浓度换算算例（恒河）**
讲义演示了从水化学分析报告到 molality 的换算：Ca²⁺ 含量 25.4（mg/L）→ 25.4/1000 = **0.0254 g/L** → 除以 Ca 的原子量 40.08 → **6.34 × 10⁻⁴ mol/kg**。旁注 "(electrons have no mass)" 意思是**算 Ca²⁺ 的质量时可以直接用中性 Ca 原子的原子量**，少两个电子的质量可忽略。

---

## 四、课堂补充

以下是**转写中有、幻灯片上没有**的内容。

### 1. 课程结构与实验安排（务必记住）

- 本单元**50/50 拆给两位老师**：前五讲固体／岩石地球化学，后五讲（本周起）流体地球化学，由 Greg Holland 讲。老师强调二者"complementary"——合起来才是完整的地球化学。
- 部分内容与 **environmental chemistry** 单元重叠，"maybe one lecture's worth"；其余对所有人都是新内容。
- **上课节奏**：讲约 30 分钟 + 课末 Kahoot 小测。理由是内容"theory heavy"，"rather than just drone on for 50 minutes"。**每周都有小测，且会越来越难**，本周是最简单的入门周。
- **Practical 新格式**（与前五周完全不同）：
  - 被分到周三／周四（两场）／周五中的**一场**；没被分到的发邮件给老师。
  - **注意检查二年级 tutorial 是否与实验时段冲突**——老师说另一个单元已经出过冲突问题。
  - 地点：**Williamson 楼一楼化学实验室 1.18**。
  - 节奏：**本周做实验 → 下周跟老师做 write-up（答题＋作图）→ 再隔一周做第二次实验 → 之后再 write-up → 最后一周在 G12 做纸笔练习**。
- 行政通知：Earth & Environmental Sciences 的 **work experience 问卷**（用于专业认证材料），**截止 11 月 21 日**，**做过或没做过的都要填**。另外老师答疑时说，申请 placement 的同学只需发邮件告知申请方向，**英国本土学生不必提前改学位注册，等 5 月拿到 offer 再改即可**；国际学生因签证可能需提前。

### 2. "从最基础讲起"的用意

老师专门说明："I've always had feedback previously that I haven't started at the beginning. So even though we're halfway through a unit, I'll just start with the very fundamentals of some chemistry." 所以幻灯片前几页的 amu／mole／stoichiometry 是**刻意的复习页**，不是新知识点，但**摩尔／molarity／molality 的区分在实验计算里必用**。

### 3. 讲授中的额外解释与举例

- **carbon-12 的任意性**："The humanities just said carbon-12 is what we're going to use"——参照点是人为约定，所以只有 ¹²C 是整数。
- **氯的 35.45 从哪来**：³⁵Cl 约占 3/4、³⁷Cl 约占 1/4 的丰度加权（幻灯片上只有数字，没有解释）。
- **核结合能**：加总 6p+6n+6e 得不到 12，差额被结合能"吃掉"了，"there is an energy-mass equivalent"——但**不会考**，做题直接查表取原子量。
- **molarity vs molality 的实际影响**："for you it won't make any difference in your lab experiments, but if we were using other solvents, then you would have to distinguish between the two."（本周实验里体积与摩尔数成正比就是靠这个近似。）
- **"地下到处是湿的"**（见第二段第 3 节）——这是老师用来立论"流体地球化学是地球化学的主场"的核心论证，很可能作为简答题的开场论述。
- **纯水绝缘**的浴室充电手机例子——考点是"导电的是离子不是水"。
- **理想气体类比**理解理想／非理想溶液。
- 老师自嘲式的诚实："ions start interacting with each other in all sorts of ways that we're not going to go into the detail of. **And I don't understand them either**." → 呼应下面的考试提示。

### 4. ⭐ 考试提示（转写中明确说的）

1. **不考活度的微观成因**："I would never ask you an exam question about why activity is the way it is."
2. **但必须认识"activity"这个词并知道它是浓度的修正**；且**此后凡老师说 "concentration"，实际都指 activity**——"we'll just take it as read that we've made any correction we would need to make."
3. **小测第 4 题（区分度最大的一题）的正确答案**：活度系数在 **"高离子电荷 + 高离子强度"** 时最重要（老师说这题"split everybody"，并回头用 Al³⁺ 曲线讲解）。
4. **log(1) = 0**（小测第 7 题；OCR 把 "1" 认成 "V"）。老师说学生在 0 和 10 之间摇摆。
5. **水释放 H⁺ 会"降低"pH 而不是升高**——小测里"lots of you got the releases H+ bit, which is right, **but it lowers the pH because it's the minus log**"。这是本周**最集中的错误**。
6. **强酸的定义 = 在水中强烈解离**（不是"含氯"、不是"pH = 5"、不是"Ka 低"）。
7. **pH 的定义 = −log[H⁺]**（不是"H⁺ 浓度"本身，也不是 +log[H⁺]）。
8. **大多数矿物与水反应释放 OH⁻**（使水偏碱）。
9. **水的最大密度在 4 °C**；**氢键存在于水中**（不在甲烷、不在 HCl）；**1 mol 碳的质量是 12 g**。

### 5. 老师对常见误解的澄清

- **强度 ≠ 浓度**（见核心概念第 9 条）——这是转写里语气最重的一处澄清。
- **平衡不是"停止"**：正逆反应仍在以相同速率进行，只是宏观看不出变化（"it won't apparently seem to be changing. But in practice, you'll be having a forward reaction happening at the same rate as the backward reaction."）。
- **对数不必怕**："in fluid geochemistry we use logs a lot. Logarithms crop up in lots of calculations." 需要的规则只有 **−log(A/B) = log(B/A)** 和 **log x = y ⟺ x = 10^y**，"just accept it"。
- **碳酸盐比幻灯片上写的复杂**——本周把 CaCO₃ 简化成单纯的产 OH⁻ 反应，真实体系（碳酸／碳酸氢根／碳酸根平衡）留到后面。

### 6. 关于旧版 quiz 文件

`lecture 6 quiz answers 2024.md` 是 **2024 年版**、且是图片 OCR 出来的，**大部分文字不可靠**。把它和 2025 年的 transcript 对照后可以还原出的题目见上面「考试提示」。**凡与 transcript 或 2025 讲义冲突处，一律以后者为准**（详见勘误表）。

---

## 五、Practical 要点

### EXPERIMENT 1：SOLUBILITY AND METAL-LIGAND COMPLEXING（溶解度与金属—配体络合）

> 本周只做实验、记数据；**作图与答题在下周的 write-up 课上完成**。

#### 1. 实验目的（讲义原文四条）

完成本实验及配套习题后，你应能够：

1. 进行一次**沉淀滴定（precipitation titration）**；
2. **对数的代数变换**（取对数、移项）；
3. 由**滴定数据确定金属—配体络合物的化学式**；
4. 理解溶液中**金属—配体平衡**的原理，以及这些平衡**如何影响矿物溶解度**。

#### 2. 原理

**(a) 为什么地球化学关心络合**

许多矿物在水中的溶解度会因**金属—配体络合物（metal-ligand complex）**的形成而**大幅提高**。讲义给的地质例子是**方铅矿（galena, PbS）在咸水中比在淡水中溶解度更大**，因为形成了铅—氯络合物：

- PbS(galena) + H⁺(aq) ⇌ Pb²⁺(aq) + HS⁻(aq)
- Pb²⁺(aq) + 4Cl⁻(aq) ⇌ **PbCl₄²⁻(aq)**

第二步不断消耗自由 Pb²⁺，按勒沙特列原理把第一步向右拉 → 方铅矿溶解更多。**所以模拟咸水条件下的水岩反应，必须知道络合物的种类与稳定性。**

📎 背景补充：这正是**热液矿床成矿的核心机制**——金属靠氯络合物在高盐度卤水中被搬运，遇到降温、稀释、pH 升高或 H₂S 加入时络合物失稳、金属硫化物沉淀成矿。这条链条会在 Week 7 与 EART26001 里反复出现。

**(b) 银—氨络合体系（本实验要测的）**

本实验目标：**测定富氨溶液中占主导的银氨络合物 Ag(NH₃)ₙ⁺ 的化学式（即求 n）**。

用**硝酸银溶液（提供 Ag⁺）滴定／被溴化钾滴定（提供 Br⁻）**，在**沉淀终点**（AgBr 刚开始析出）时，下列平衡成立：

- **AgBr(s) ⇌ Ag⁺(aq) + Br⁻(aq)**，**Ksp = [Ag⁺][Br⁻]**（Ksp 为**溶度积 solubility product**）

若溶液中同时含有**大量氨**，则还有：

- **Ag⁺(aq) + n NH₃(aq) ⇌ Ag(NH₃)ₙ⁺(aq)**，**Kn = [Ag(NH₃)ₙ⁺] / ([NH₃]ⁿ[Ag⁺])**（Kn 为**生成常数 formation constant**）

两式联立（因为氨大大过量，几乎全部银都以络合物形式存在，[Ag(NH₃)ₙ⁺] ≈ 总 AgNO₃）：

**moles KBr = (moles NH₃)ⁿ × Kn × Ksp / (moles AgNO₃)**

两边取对数：

**log(moles KBr) = n · log(moles NH₃) + log(Kn × Ksp / moles AgNO₃)**

这是一条 **y = nx + c** 的直线。**保持 AgNO₃ 的量恒定**，改变氨的量做若干次滴定，作 **log(moles KBr) 对 log(moles NH₃)** 图，**斜率就是 n**——即主导银氨络合物中氨分子的个数。

**(c) 关键实验设计假设**

**每次滴定终点时溶液的总体积必须相同**。这样一来，加入的氨体积与 KBr 体积就**正比于**各自的浓度，AgNO₃ 的浓度也保持不变——于是**可以直接用体积（或由体积算出的摩尔数）代替浓度作图**。这就是讲义在 Kn 定义处写 "[ ] refers to the moles" 的原因。

#### 3. 课前准备（讲义 Section 3，属评分／安全要求）

1. **通读全部操作步骤**；
2. **标出看不懂的步骤**，实验开始前问 demonstrator；
3. **列出所需器材与试剂清单**，实验开始时先核对是否齐全；
4. **标出有潜在危险的步骤并预先想好规避策略**，有疑问先问实验室主管再动手。

#### 4. 试剂与器材

| 试剂 / 器材 | 规格 | 说明 |
|---|---|---|
| 硝酸银溶液 AgNO₃ | **0.01 M**，约 60 ml，贴标签的塑料瓶 | 已放在你的实验台上 |
| 氨水 NH₃ | **2 M** | 在**通风橱（fume cupboard）**的大烧杯中取用 |
| 溴化钾溶液 KBr | **0.02 M** | 装在 **50 ml 滴定管（burette）** 中作滴定剂 |
| 去离子水 | — | 稀释与洗涤 |
| 小烧杯、**250 ml 烧杯**、注射器（syringe）、50 ml 滴定管 | — | 注射器用于量取 20 ml 分装液 |
| 深色背景板 | — | 便于观察**首次出现的永久性浑浊** |
| 通风橱中的废液收集烧杯 | — | 回收含 AgBr 的废液 |

#### 5. 操作步骤（可照做流程）

1. 台上的塑料瓶里有约 **60 ml 0.01 M AgNO₃**。倒入**小烧杯**，用**注射器取 20 ml 分装液（aliquot）**放入 **250 ml 烧杯**。
2. 从通风橱取 **40 ml 2 M 氨水**，加入上述 250 ml 烧杯中的 20 ml 银溶液。
3. 用**去离子水**把银—氨混合液稀释到**总体积 100 ml**。
4. 用滴定管中的 **0.02 M KBr** 滴定，直到**首次出现永久性浑浊（first permanent turbidity）**为止。
   - 技巧：**把烧杯衬在深色背景前观察**；
   - **记录所用 KBr 体积**，同时**记录混合液的总体积**；
   - 滴完用去离子水冲洗烧杯；
   - **建议先做一次粗滴定（rough trial titration）**，摸清大致用量以及终点前后溶液外观的变化。
5. 重复步骤 1–4，但氨的用量改为 **10 ml 2 M NH₃**（数据表还要求做 **30 ml** 和 **15 ml** 两组，见勘误第 13 条）。**务必补加足量去离子水，使总体积接近步骤 4 中首次记录的总体积。**
6. **废液倒入通风橱中的收集烧杯。绝对不许把溴化银（AgBr）倒进水槽。**

#### 6. 数据记录表（讲义 DATASHEET 原样，括号为标称加入体积）

| VOLUME (ml) 0.01 M AgNO₃ | VOLUME (ml) 2 M NH₃ | VOLUME (ml) 0.02 M KBr | TOTAL VOLUME (ml) |
|---|---|---|---|
| (20) | (40) | 待测 | 待测 |
| (20) | (30) | 10.6（示例） | 115.6（示例） |
| (20) | (15) | 2.5（示例） | 113.5（示例） |
| (20) | (10) | 待测 | 待测 |

⚠️ 表中两行是**印好的示例数据**（推测为设备／课程提供），其余需自己测。示例数据的总体积与"稀释到 100 ml 后滴定"不自洽，见勘误第 12 条。但示例数据本身在斜率上是自洽的：log(10.6/2.5)/log(30/15) = 0.627/0.301 = **2.08**，已经暗示 n ≈ 2。

#### 7. 数据处理（讲义要求）

1. **纵轴 log(moles KBr)，横轴 log(moles NH₃)** 作图。
   ⚠️ 讲义特别强调：**必须先手算出各点的对数值再作图**，"You do this by calculating the log of the moles of KBr and NH₃ **not by plotting the molar data then using the log function to display the graph**"（不许直接画摩尔数再把坐标轴切成对数显示）。
   - 摩尔数换算：n = C × V(L)。例：0.02 M × 6.7 ml = **1.34 × 10⁻⁴ mol**；2 M × 40 ml = **0.08 mol**；0.01 M × 20 ml = **2 × 10⁻⁴ mol**（AgNO₃，恒定）。
2. 用**目测或手算／计算机拟合**求**最佳拟合直线**。
3. **写出最佳拟合直线的方程**。
4. **写出所求 n 值，并据此写出主导银氨络合物的化学式**（n 必须是整数）。
5. **思考题**：若滴定**越过沉淀终点**继续加 KBr，并把这个体积用于计算 n，则第 2 节中的**哪个方程会失效？为什么？**
6. **计算题**：已知 **20 °C 时 AgBr 的溶度积 Ksp = 5 × 10⁻¹³**（Fritz and Schenk, 1979），据此**估算主导银氨络合物的生成常数 Kn**。（提示：**只用一次滴定的数据、或最佳拟合线上的一个点**即可。）
   - 变形式：**Kn = (moles KBr × moles AgNO₃) / ((moles NH₃)ⁿ × Ksp)**

#### 8. 预期结果

📎 背景补充（讲义未直接给出答案，以下为标准化学知识与量纲检查）：**主导物种应为二氨合银(I)离子 Ag(NH₃)₂⁺**，即 **n = 2**，最佳拟合直线斜率应接近 2。这也是照相定影液（"海波"体系）与银氨溶液（Tollens 试剂）中的标准物种。代入一组典型数据（40 ml NH₃ → 0.08 mol；KBr 6.7 ml → 1.34×10⁻⁴ mol；AgNO₃ 2×10⁻⁴ mol）可得 **Kn ≈ 8 × 10⁶**，量级上合理——说明银与氨的络合能力很强。

**第 5 题的答题方向** 📎：越过终点后溶液持续变浑，说明体系中已经析出**大量固体 AgBr**，反应不再处于"AgBr 刚开始沉淀"的临界平衡状态；此时 **AgBr(s) ⇌ Ag⁺ + Br⁻ 及 Ksp = [Ag⁺][Br⁻] 这一步失效**——多加的 Br⁻ 不再通过 Ksp 对应溶液中剩余的 Ag⁺，而是直接进了沉淀，于是"moles KBr"不再是终点时的平衡量，整条推导链断裂。

#### 9. 安全注意事项

- **氨水必须在通风橱中取用**——氨蒸气强烈刺激呼吸道和眼睛（讲义明确要求 2 M NH₃ 从 fume cupboard 的大烧杯取）。
- **硝酸银具腐蚀性，会把皮肤和衣物染成永久的黑褐色**（📎 背景补充：AgNO₃ 遇皮肤蛋白质光解为单质银）。全程戴手套、护目镜、穿实验服。
- **AgBr 废液严禁倒入下水道**，必须倒进通风橱内的指定收集烧杯（讲义用大写强调：DO NOT dispose of the SILVER BROMIDE down the sink）——既是重金属污染问题，也是银的回收问题。
- 使用滴定管前先润洗、排气泡；粗滴定先摸底可减少试剂浪费和终点冲过头。
- **课前必须完成 Section 3 的危险步骤识别**，有疑问先问 supervisor 再操作。

---

## 六、易错点 / 重点难点

1. **molarity（M，mol/L 溶液）vs molality（m，mol/kg 溶剂）**。水溶液中数值相近所以容易混，但定义完全不同；**活度一律用 molality**。非水溶剂里差别巨大。
2. **"水释放 H⁺ 会升高 pH"——这是本周最集中的错误**。因为 pH = −**负**log[H⁺]，H⁺ 越多 pH 越**低**。小测里大批人栽在这里。
3. **酸的"强度"≠"浓度"**。强酸 = 解离彻底（Ka 大、pKa 小甚至为负）；浓度 = 溶了多少。高浓度的弱酸仍可能 pH 不低。
4. **pKa 的符号方向**：Ka 越大 → 酸越强 → pKa 越**小**（可为负）。ladder diagram 上**越靠上越强酸**。
5. **离子强度公式里 z 要平方**。Al³⁺ 的单位浓度贡献是 Na⁺ 的 9 倍；这也是为什么 Al³⁺ 的 γ 修正最狠、Na⁺ 最轻。
6. **γ 随 I 增大而减小、随 z 增大而减小**——两条规律缺一不可，小测第 4 题正是要求两个条件同时满足（"高电荷 + 高离子强度"）。
7. **不要把讲义"γ < 1"当成绝对真理**：在 I > 约 0.5 mol/kg 的强盐水中，某些离子（如 H⁺、Na⁺、Cl⁻）的 γ 会**回升甚至超过 1**（盐析效应）。见勘误 7。
8. **平衡常数表达式的指数来自配平系数**，不是随手写的；且严格意义上 K 用**活度**而非浓度。
9. **Henderson–Hasselbalch 里比值的方向**：分子是**解离态 A⁻**、分母是**未解离态 HA**。写反了 pH 与 pKa 的大小关系就颠倒。**pH = pKa 时正好一半解离**。
10. **对数运算**：log(A⁻/HA) = −1.1 → 比值 = 10^(−1.1) = 0.08，不是 −1.1；这一步在酚酞题和实验数据处理里都会用到。
11. **实验作图必须先算 log 再画**，不能画完摩尔数再切对数轴——讲义明文要求。
12. **实验中"总体积保持一致"是全部推导的前提**。忘了补水就等于改变了浓度，斜率会失真。
13. **实验终点是"首次出现的永久性浑浊"**，不是明显的大量沉淀；越过终点会让 Ksp 平衡关系失效。
14. **正长石／橄榄石／方解石都产 OH⁻（碱化），黄钾铁矾产 H⁺（酸化）**——记住"多数矿物碱化水，jarosite 是例外"。
15. **本周只有 Arrhenius 定义**（酸放 H⁺、碱放 OH⁻），没有讲 Brønsted–Lowry 或 Lewis 定义。📎 背景补充：Lewis 定义（电子对给受）才是理解**络合**的框架——配体 NH₃ 是 Lewis 碱、Ag⁺ 是 Lewis 酸——但**本周材料未涉及**，答题时不要越界。

---

## 七、本周术语表

| 中文 | English | 说明 |
|---|---|---|
| 原子质量单位 | atomic mass unit (amu) | 以 ¹²C = 12.00000 定义；1 amu = 1.66043 × 10⁻²⁴ g |
| 阿伏伽德罗常数 | Avogadro's number | 讲义值 6.02252 × 10²³ /mol |
| 克式量 | gram-formula mass | 1 mol 物质的克数 |
| 体积摩尔浓度 | molarity (M) | mol 溶质 / L 溶液 |
| 质量摩尔浓度 | molality (m) | mol 溶质 / kg 溶剂 |
| 溶剂 / 溶质 | solvent / solute | — |
| 介电体（绝缘体） | dielectric | 纯水是强介电体＝电绝缘体 |
| 极性 | polarity | 水的高介电常数是其极性的量度 |
| 氢键 | hydrogen bonding | O(δ⁻)···H(δ⁺)，解释水的反常性质 |
| 水合 | hydration | 偶极水分子包裹离子，阻止其复合 |
| 解离 | dissociation | 化合物在水中拆成离子 |
| 电解质（溶液） | electrolyte (solution) | 含溶解离子、能导电的溶液 |
| 去离子水 | deionised water | 剥除离子的实验室纯水 |
| 理想溶液 / 标准态 | ideal solution / standard state | 极稀溶液中离子互不作用 |
| 非理想溶液 | non-ideal solution | 离子间发生相互作用 |
| 化学势 | chemical potential | 非理想时取决于其他离子的浓度 |
| 活度 | activity (a) | 有效浓度，a = γm |
| 活度系数 | activity coefficient (γ) | 修正（折减）因子 |
| 离子强度 | ionic strength (I) | I = ½Σmᵢzᵢ² |
| 长程库仑相互作用 | long-range coulombic interactions | 非专属性离子相互作用 |
| 离子对 / 络合物 | ion pairs / complexes | 专属性离子相互作用 |
| Debye–Hückel 理论 | Debye–Hückel theory | 计算个别离子 γ（Misra 7.2.3） |
| 质量作用定律 | Law of Mass Action | K = 产物 / 反应物（按系数取幂） |
| 平衡常数 | equilibrium constant (K) | 正逆反应速率相等时的比值 |
| 解离常数 | dissociation constant (Ka, Kb) | 酸／碱的平衡常数 |
| 强酸 / 弱酸 | strong acid / weak acid | 按解离程度分，非按浓度 |
| 解离度 | degree of dissociation (%D) | 已解离量 / 原始溶解量 × 100 |
| 水合氢离子 | hydronium ion (H₃O⁺) | H⁺ + H₂O |
| 氢氧根 | hydroxide ion (OH⁻) | — |
| 阶梯图 | ladder diagram | 以 pKa 为刻度的一维图 |
| 亨德森–哈塞尔巴尔赫方程 | Henderson–Hasselbalch equation | pH = pKa + log([A⁻]/[HA]) |
| 酚酞 | phenolphthalein | pKa 9.3；HA 无色、A⁻ 粉红 |
| 正长石 / 高岭石 | orthoclase / kaolinite | 长石水解成黏土，释放 OH⁻ 与 K⁺ |
| 橄榄石 / 蛇纹石 | olivine / chrysotile | 蛇纹石化，释放 OH⁻ 与 Mg²⁺ |
| 黄钾铁矾 | jarosite | 少数使水酸化的矿物 |
| 溶度积 | solubility product (Ksp) | AgBr：5 × 10⁻¹³（20 °C） |
| 生成常数 | formation constant (Kn) | 络合物形成的平衡常数 |
| 金属—配体络合物 | metal-ligand complex | 提高矿物溶解度 |
| 配体 | ligand | 如 Cl⁻、NH₃ |
| 银氨络合物 | silver-ammine complex | Ag(NH₃)ₙ⁺ |
| 方铅矿 | galena (PbS) | 咸水中因 PbCl₄²⁻ 而溶解度增大 |
| 沉淀滴定 | precipitation titration | 以出现沉淀为终点 |
| 浑浊（终点） | turbidity (end-point) | 首次出现永久性浑浊 |
| 分装液 | aliquot | 定量取出的一份溶液 |
| 滴定管 | burette | 50 ml |
| 通风橱 | fume cupboard | 取氨、收废液 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| 1. `lecture 6 ions in solution 2025.md` — "Basic revision: structures of atoms" 粒子表 | Proton … Mass (amu) = **1.007825** | 1.007825 amu 是 **¹H 原子**（质子＋电子）的质量，不是**质子**的质量。用此值计算 6Z+6N+6e 得 **12.10223**，与幻灯片自己写的 12.098931 不符 | 质子质量应为 **1.007276 amu**。用 1.007276 + 1.008665 + 0.00054858 各 6 份，得 **12.09894 ≈ 12.098931** ✓，与幻灯片的质量亏损 0.098931 amu 自洽 |
| 2. 同上，粒子表 | Electron … "**-e = 1.6021 x 10-19**"；脚注 "Atomic mass (A) = Z + N (**amu**)" | ①电子电荷的负号在排版中丢失（正负两行数值写法相同）；②A 是**质量数**，为无量纲的核子数，不该带 amu 单位；③"Symbol: Proton = Z" 不严谨，Z 是原子序数 | ①电子电荷 = −1.602177 × 10⁻¹⁹ C；②应写 "Mass number A = Z + N（无量纲）"，"Atomic mass" 才以 amu 计 |
| 3. 同上，"Basic revision: Stoichiometry" | "atomic mass Na = 22.9 … molecular mass NaCl = 22.9+35.45 = **58.35** amu"（转写中老师照读） | Na 的标准原子量是 **22.990**，不是 22.9 | NaCl 式量应为 **22.99 + 35.45 = 58.44 g/mol**。误差约 0.15%，对本课计算无实质影响，但答题写 58.44 更稳妥 |
| 4. 同上，"Electrolyte solutions" | "**NaCl + Cl⁻ (s) = Na⁺**" | 方程被 PDF 转换打乱，物种与状态标注全部错位，字面完全不成立 | 应为 **NaCl(s) ⇌ Na⁺(aq) + Cl⁻(aq)** |
| 5. 同上，"Relationship between ionic strength (I) and activity" | "Ganges river water (I = 0.0034) **the activity of Ca²⁺ is 0.80** and in seawater (I = 0.685) it is about 0.26" | 0.80 与 0.26 是**活度系数 γ**（无量纲），不是**活度 a**。活度 a = γm，量纲是 mol/kg，恒河 Ca²⁺ 的活度应约 0.8 × 6.34×10⁻⁴ = 5.1×10⁻⁴ mol/kg | 应写 "the **activity coefficient** of Ca²⁺ is 0.80"。转写中老师口述"effective concentration … 20% less"是对的 |
| 6. 同上，"Ionic strength" 与 "Relationship…" 两页 | 一处写 "Seawater has an ionic strength of **0.7** mol/Kg"，另一处写 "seawater (I = **0.685**)" | 同一材料内两个数值不一致 | 二者不矛盾（0.7 是 0.685 的取整），但计算题请统一用 **I = 0.685 mol/kg** |
| 7. 同上，"Activity Coefficient" 页 | "**Values of γ are <1** which means the effective concentration … is less than their actual concentration" | 过度概括。在 I ≳ 0.5 mol/kg 的浓盐水中，因"盐析效应"（离子把自由水分子占用），许多离子的 γ 会回升并**超过 1** | 应表述为"在天然水常见的离子强度范围内 γ 通常 < 1"。油田卤水（I ~3.4）就是 γ > 1 的典型场景，而讲义自己提到了油田卤水 |
| 8. 同上，Ca²⁺ molality 算例 | "grams of Ca²⁺ = **25.4/1000** = 0.0254 g/L … = 0.634 × 10⁻³ **mol/kg**（electrons have no mass）" | ①25.4 的单位未标（由除以 1000 反推应为 **mg/L**）；②起算单位是 g/**L**（molarity），结果却标 mol/**kg**（molality），二者被默认等同而未说明；③"electrons have no mass" 表述错误——电子有质量，只是可忽略 | 应写 "Ca²⁺ = 25.4 **mg/L**"；并注明"稀水溶液中 1 L ≈ 1 kg，故 M ≈ m"；括注应为"电子质量可忽略不计"。计算本身正确：0.0254 / 40.08 = 6.34 × 10⁻⁴ |
| 9. 同上，"Acid-Base properties of minerals" | "2KAlSi₃O₈ + 2H₂O → Al₂Si₂O₅(OH)₄ + 2OH⁻ + 2K⁺" | **未配平**：左侧 Si = 6、O = 18，右侧 Si = 2、O = 11，缺失 4 个 Si 和大量 O、H | 常用的正长石→高岭石水解式为 **2KAlSi₃O₈ + 2H⁺ + 9H₂O → Al₂Si₂O₅(OH)₄ + 4H₄SiO₄ + 2K⁺**（消耗 H⁺、故升高 pH）。同页的橄榄石式、方解石式、jarosite 式经核算**均已配平，无误** |
| 10. 同上，"Summary - 2" 最后一条 | "Most minerals are the salts of a **strong acid and weak base**" | **方向写反**，且与同一份讲义"most minerals react with water to raise the pH"自相矛盾。强酸弱碱盐水解显**酸性**（那是 jarosite 的情形），能使水偏碱的是**弱酸强碱盐** | 应为 "Most minerals are the salts of a **weak acid and a strong base**"（如 CaCO₃ = 弱酸 H₂CO₃ + 强碱 Ca(OH)₂；硅酸盐 = 极弱酸 H₄SiO₄ + 碱金属／碱土金属强碱），水解产 OH⁻ |
| 11. 同上，"Basic revision" 页 | "1 amu = … = **1 66043 x 10⁻²⁴** g" | 小数点在 PDF 转换中丢失 | 应为 **1.66043 × 10⁻²⁴ g** |
| 12. 同上，"Basic revision" 页 | "1 mole = **6.02252 × 10²³**" | 该值为 2019 年 SI 改制前的旧测量值 | 现行 SI **定义值为 6.02214076 × 10²³ /mol**。差异 < 0.01%，不影响本课计算，但引用时宜用现行值 |
| 13. `lecture 6 quiz answers 2024.md` — 全文件 | 文件名即 "**2024**"，且首行注明"图片 OCR、识别质量低" | 本周讲义与转写是 **2025 版**，题目顺序与措辞已不同；OCR 把选项、对错勾叉几乎全部打乱（如 "x « x x ff x x x < ff" 一类乱码），**无法据此判定正确选项** | **一律以 2025 讲义与转写为准。** 由转写还原的 2025 版答案见「四、课堂补充 §4」 |
| 14. `lecture 6 quiz answers 2024.md` — Slide 3 "7- Quiz" | "The log of **V** is" | OCR 把数字 "1" 认成字母 "V" | 应为 "**The log of 1 is**"，答案 **0**（转写："What is the log of 1? … It was either 0 or 10. Yes."） |
| 15. `lecture 6 quiz answers 2024.md` — Slide 2 "5- Quiz" 与 Slide 3 编号 | Slide 2 给出 Q4、Q5；Slide 3 直接跳到 Q7 | **Q6 整题在 OCR 中缺失**；且 2024 版把"Water releases H⁺ …"编为 Q5，而 2025 转写的顺序是 Q5 =「水解离成什么」、Q6 =「水释放 H⁺ 会怎样」 | 缺失题按转写补：**水会轻微自解离成 H⁺ 与 OH⁻**；**水释放 H⁺ 会降低 pH**（转写明确纠正了多数人的错答） |
| 16. `EART26201 - 10-Nov-transcript.md` — 全文 | ASR 误听多处：`amol`（= a mole）、`one oil carbon has mass of`（= one mole of carbon）、`one liter of blood`（= one litre **flask**）、`Miseratec`（= the **Misra** text）、`phenol failing`（= **phenolphthalein**）、`a minus 2Ha`（= **A⁻ to HA**）、`kaO`（= **Ka**）、`Romant`（= 另一位讲师姓名）、`Seats code`（= **Kahoot** code）、`pH equals pKa plus the log of A minus over H`（= over **HA**） | 自动转写的识别错误，非授课内容错误 | 阅读转写时按上表还原即可；本笔记正文已按还原后的意思引用 |
| 17. `EART26201 - 10-Nov-transcript.md` — 活度段 | "activity is that coefficient multiplied by m, **the molar concentration**, where that's expressed in moles per kilogram of water" | 口误：mol/kg 是 **molal**（质量摩尔浓度），不是 molar（体积摩尔浓度）；同一句里自相矛盾 | 应为 "the **molal** concentration"。讲义写的 "Activities are expressed as molalities" 是正确的 |
| 18. `EXPERIMENT 1 2025-1.md` — DATASHEET 示例数据 | 第 2 行 KBr 10.6 ml / 总体积 **115.6** ml；第 3 行 KBr 2.5 ml / 总体积 **113.5** ml | 与步骤 4.3–4.4 不自洽：稀释到 100 ml 后再滴入 10.6 ml 应为 **110.6** ml，滴入 2.5 ml 应为 **102.5** ml。两行的"总体积 − KBr 体积"分别是 105 与 111，也彼此不等，违反了本实验"各次滴定终点总体积必须相同"的核心前提 | 示例数据仅供参考斜率（log 比值给出 n ≈ 2.08，方向正确）。**实际操作时必须自己记录真实总体积，并靠补加去离子水把各次总体积调到一致** |
| 19. `EXPERIMENT 1 2025-1.md` — 步骤 4.5 | "Repeat steps 4.1 to 4.4 however this time using only **10 ml** of the 2M NH₃ solution." | 只写了重复**一次**（10 ml），但 DATASHEET 有 **四行**（40、30、15、10 ml），且两点无法可靠拟合直线 | 应重复至覆盖数据表全部四个氨用量（**40 / 30 / 15 / 10 ml**）；若时间不够，至少完成表中留白的 40 ml 与 10 ml 两行，配合已给的 30、15 ml 示例值凑成四点 |
| 20. `EXPERIMENT 1 2025-1.md` — 第 2.2 节 | Ksp 处写 "[ ] refers to the **concentration** of the enclosed species"，Kn 处写 "[ ] refers to the **moles** of the enclosed species" | 同一份讲义内 [ ] 的定义前后不一致 | 严格意义上平衡常数用**浓度（活度）**；本实验因**各次滴定终点总体积相同**，摩尔数与浓度成固定比例，故可以用摩尔数代入而不影响斜率 n。讲义在第 2.2 节末已说明这一点，但两处标注应统一 |
| 21. `lecture 6 ions in solution 2025.md` — Activity Coefficient 页 | "determined using the **DebyeHukel** theory" | 拼写与连字缺失 | 应为 **Debye–Hückel theory**。另：讲义**全程未给出 Debye–Hückel 公式本身**，只给参考章节 Misra 7.2.3；本笔记「三、公式与图表」中的三条公式为 📎 补充，非材料原文 |
