# Week 10 — 湿化学实验室技能：pH、电导率与滴定法测海水氯度 (Wet-Chemistry Lab Skills: pH, Conductivity & Titration for Seawater Chloride)

> 本周材料（Week 10 文件夹全部 .md）：
> - `Expt1 pH-conductivity_Ans(1).md`——实验一《The effect of the concentration of a basic or acidic solution on its conductivity and pH》（含答案版）
> - `Expt2 titration - seawater salinity_ans(4).md`——实验二《How much chloride is there in seawater?》（含答案版）
>
> 两份都是**带答案的实验讲义 (answer version handout)**，没有 lecture、没有录音转写。
>
> 材料页眉的小矛盾（值得知道，别被绕晕）：实验一页眉写 "EART11300 – Semester 2, pH and conductivity"，实验二页眉写 "EART11300 – Microchemistry, chloride content of seawater"，但两份文件实际归档在 **Michaelmas Term Week 10**。说明这套微化学 (microchemistry) 实验在课程中被复用过，页眉未及更新。**以文件夹归属为准：本周是 Michaelmas Week 10。**

---

## 一、本周主题

本周是 EART11300 十周实践课（Week 1、2、4、5、6、7、8、9、10、11，**无 Week 3**）的**第九次实践**，主题是**湿化学 / 微化学实验室技能 (wet chemistry / microchemistry laboratory skills)**。这是整门课里唯一一次真正进"化学实验台"的一周：前面几周练的是野外记录、岩矿手标本鉴定、生物鉴定与河流评估、测量与数据处理，本周补上地球科学家的**第四条腿——化学分析 (chemical analysis)**。

本周两个实验构成一条完整的"从定性到定量"的技能链：

| | 实验一 | 实验二 |
| --- | --- | --- |
| **题目** | pH 与电导率 (pH and conductivity) | 海水中的氯化物含量 (chloride content of seawater) |
| **性质** | **定性/半定量** (qualitative / semi-quantitative) | **定量** (quantitative) |
| **核心动作** | 自己搭 LED 电路当电流指示器；做**系列稀释 (serial dilution)**；用**万用指示剂试纸 (universal indicator paper)** 读 pH | 用注射器当**滴定管 (burette)**，以 AgNO₃ 滴定"海水"，**荧光素 (fluorescein)** 指示终点 |
| **回答的问题** | 浓度如何影响导电性与 pH？为什么溶液能导电？ | 这份水样里到底有多少 Cl⁻（g/L）？ |
| **可迁移技能** | 稀释计算、pH 计算、离子导电概念 | 滴定操作、化学计量换算、误差评估 |

**贯穿两个实验的一条暗线**：电导率与盐度本质上是同一件事的两种表达。实验一告诉你"离子越多越导电"，实验二告诉你"海水里的离子主要是 Cl⁻ 和 Na⁺"——把这两条接起来，就是海洋学里用**电导率直接反演盐度 (Practical Salinity Scale, PSS-78)** 的原理（详见 §2.9、§3.6）。**这是本周最值得写进论述题的整合点。**

本周还有一个"专业素养"层面的目标：材料反复强调 **micro-chemical procedures（微量化学操作）——用最少的试剂完成同样的测定，以降低成本与环境影响**。这是现代分析化学的绿色化学 (green chemistry) 取向，也是为什么整个滴定只用了 2.5 ml 样品和不到 3 ml 滴定剂。

---

## 二、核心概念

### 2.1 电流、电子与离子：溶液为什么导电

材料里的原句（实验一问题 3 答案）是本周最核心的一句话：

> "In wires, it is electrons that carry the current, but in solutions the current is carried by ions."
> **在导线中载流子是电子 (electrons)，在溶液中载流子是离子 (ions)。**

- **金属导体 (metallic conduction / electronic conduction)**：自由电子在晶格中移动，载流子是电子；温度升高电阻**增大**（晶格振动散射加剧）。
- **电解质导电 (electrolytic / ionic conduction)**：溶液中的正离子 (cations) 向阴极迁移、负离子 (anions) 向阳极迁移，载流子是**离子**；温度升高电导率**增大**（黏度下降、离子迁移更快）。**这个"温度效应方向相反"是常考对比点。**

因此：**溶液导电的前提是存在自由移动的离子**。纯水几乎不导电（去离子水电导率 ~0.055 µS/cm，即理论极限值），加入电解质后电导率骤升。

### 2.2 强电解质的解离 (dissociation of strong electrolytes)

材料要求写出**溶解/解离反应式**（实验一问题 3）：

$$\mathrm{HCl\,(aq)} \longrightarrow \mathrm{H^{+}\,(aq)} + \mathrm{Cl^{-}\,(aq)}$$

$$\mathrm{NaOH\,(aq)} \longrightarrow \mathrm{Na^{+}\,(aq)} + \mathrm{OH^{-}\,(aq)}$$

> 材料原文用的是等号 "="，正式写法应写单向箭头 "→"（强电解质**完全解离 (fully / strongly dissociate)**，无逆向平衡）。若是弱电解质（如 CH₃COOH）才写可逆双箭头 ⇌。

**关键点**：HCl 与 NaOH 都是**强电解质 (strong electrolyte)**——在水中**完全解离**。所以：
- 0.005 M HCl → [H⁺] = 0.005 M（一比一）
- 0.005 M NaOH → [OH⁻] = 0.005 M（一比一）

这正是后面 pH 计算可以直接用配制浓度的原因（见 §3.3）。

**补充（材料未展开，但必须懂）**：若换成弱酸弱碱（醋酸、氨水），解离度 α < 1，必须用 $K_a$ / $K_b$ 平衡计算，pH 不能直接由配制浓度取对数得到；同浓度下弱电解质的**电导率也显著更低**（离子数少）。这是"同浓度醋酸导电性弱于盐酸"的原因。

### 2.3 离子迁移率与摩尔电导率 (ionic mobility & molar conductivity)

材料里的关键论断（实验一问题 4 答案）：

> "The electrical conductance depends upon the **total concentration of the ions** (and hence pH). **The most mobile ions are H⁺ and OH⁻.** So the more acidic or basic the solution the greater the electrical conductivity will be."

拆开理解，电导率取决于两个因子：

$$\kappa \;\propto\; \sum_i c_i \, z_i \, u_i$$

- $c_i$：第 $i$ 种离子的浓度 → **浓度因子**
- $z_i$：电荷数 → **电荷因子**
- $u_i$：**离子迁移率 (ionic mobility)** → **本征因子**

**极限摩尔离子电导率 (limiting molar ionic conductivity) $\lambda^\circ$，25 °C，单位 S·cm²·mol⁻¹**（补充数据，材料未给，但解释"H⁺/OH⁻ 最快"必须有）：

| 离子 | $\lambda^\circ$ | 备注 |
| --- | --- | --- |
| **H⁺ (H₃O⁺)** | **349.8** | 最高，远超其他离子 |
| **OH⁻** | **198.0** | 第二高 |
| Na⁺ | 50.1 | |
| K⁺ | 73.5 | |
| Cl⁻ | 76.3 | |
| NO₃⁻ | 71.4 | |
| Ag⁺ | 61.9 | |

**为什么 H⁺ 和 OH⁻ 特别快？——Grotthuss 机制 (Grotthuss mechanism / proton hopping)**：H⁺ 并不是真的把一个水合质子整个"拖"过溶液，而是通过氢键网络**接力传递 (structural diffusion)**——A 水分子把一个质子交给相邻的 B 水分子，B 再交给 C，电荷传播速度远快于任何实体离子的物理位移。OH⁻ 是同一机制的"空穴"版本（质子反向跳跃）。**这是本周最漂亮的一个物理化学解释，务必记住名字。**

推论：**酸碱溶液的导电性远强于同浓度的中性盐溶液**——这正是为什么本实验用 HCl/NaOH 而不用 NaCl 来演示"浓度—电导率"关系。

### 2.4 电导率的严格定义与单位

- **电阻 (resistance) $R$**，单位 Ω（欧姆）。
- **电导 (conductance) $G = 1/R$**，单位 S（西门子，Siemens；旧称 mho）。
- **电导率 / 比电导 (conductivity, specific conductance) $\kappa$**：把几何因素除掉后的材料本征量，单位 **S/m** 或实用的 **µS/cm、mS/cm**。

$$\kappa = G \cdot \frac{L}{A} = \frac{1}{R}\cdot K_{\text{cell}}$$

其中 $K_{\text{cell}} = L/A$ 是**电极常数 (cell constant)**，$L$ = 两电极间距，$A$ = 电极面积，单位 cm⁻¹。

- **摩尔电导率 (molar conductivity) $\Lambda_m = \kappa / c$**，单位 S·cm²·mol⁻¹（注意 $c$ 要换成 mol/cm³）。

**典型电导率量级（补充参考值，25 °C）**：

| 溶液 | 电导率 |
| --- | --- |
| 超纯/去离子水 (de-ionised water) | 0.055 – 1 µS/cm |
| 雨水 | ~5 – 30 µS/cm |
| 饮用水 / 河水 | 100 – 800 µS/cm |
| 本实验 0.00025 M HCl | ~110 µS/cm（LED 暗） |
| 本实验 0.005 M HCl | ~2100 µS/cm（LED 亮） |
| **海水 (seawater)** | **~50 000 µS/cm = 50 mS/cm** |

**为什么去离子水是配稀释液的必需品**：如果用自来水稀释，自来水自带 ~500 µS/cm 的背景离子，会完全淹没 0.00025 M 溶液的信号（~110 µS/cm），实验彻底失败。**这是实验一里"De-ionised water"这一行试剂清单的真正意义。**

### 2.5 水的自解离与 pH / pOH 标度

**水的自解离 (autoionisation / self-ionisation of water)**：

$$\mathrm{2H_2O\,(l)} \rightleftharpoons \mathrm{H_3O^{+}\,(aq)} + \mathrm{OH^{-}\,(aq)}
\qquad\text{简写}\qquad
\mathrm{H_2O} \rightleftharpoons \mathrm{H^{+}} + \mathrm{OH^{-}}$$

**水的离子积 (ionic product of water)**，25 °C：

$$K_w = [\mathrm{H^+}][\mathrm{OH^-}] = 1.0\times10^{-14} \quad\Longrightarrow\quad \mathrm{p}K_w = 14.00$$

定义：

$$\mathrm{pH} = -\log_{10}[\mathrm{H^+}] \qquad \mathrm{pOH} = -\log_{10}[\mathrm{OH^-}] \qquad \boxed{\mathrm{pH} + \mathrm{pOH} = 14.00\ (25\,^\circ\mathrm{C})}$$

材料在实验一问题 2 里正是这么用的：先算 pOH，再用 `pOH + pH = 14` 换算成 pH。

**重要陷阱（材料未提，但必须知道）**：`pH + pOH = 14` **只在 25 °C 成立**。$K_w$ 随温度上升而增大（自解离是吸热的），例如 100 °C 时 $K_w \approx 5.1\times10^{-13}$，p$K_w \approx 12.3$，此时中性点是 pH ≈ 6.15 而不是 7.00。**中性 (neutral) 的定义是 [H⁺] = [OH⁻]，不是 "pH = 7"。**

**严格性说明**：pH 的严格定义是 $\mathrm{pH} = -\log_{10} a_{\mathrm{H^+}}$（用**活度 activity**而不是浓度）。稀溶液中活度系数 $\gamma \approx 1$，两者近似相等；本实验浓度极低（≤ 0.005 M），用浓度完全够用。高离子强度（如海水）中差别显著。

### 2.6 稀释与稀释定律 (dilution)

稀释的物理本质：**溶质的物质的量 (moles of solute) 不变，只是溶剂变多**。

$$\boxed{M_1 V_1 = M_2 V_2}$$

- $M_1$ = 原液浓度 (mol/L)，$V_1$ = 取用体积
- $M_2$ = 稀释后浓度，$V_2$ = **稀释后的总体积**（注意不是加入的水量！）

**稀释因子 (dilution factor, DF)**：$DF = V_2/V_1$。本实验每一步 $V_1 = 0.1$ ml，$V_2 = 0.1 + 1.9 = 2.0$ ml，所以 **DF = 20**，每一步浓度降到 1/20。

**系列稀释 (serial dilution)**：连续做 $n$ 次相同的稀释，最终浓度 $M_n = M_0 / DF^{\,n}$。本实验做了两级：$0.10 \to 0.005 \to 0.00025$ M。

**为什么用系列稀释而不是一次配到位**：要从 0.10 M 一次配到 0.00025 M，稀释因子是 400，就得取 0.005 ml 原液——注射器根本量不准（一滴就是 0.04 ml！）。**分两级、每级 20 倍，每级取的体积都在仪器可测范围内，误差可控。这是系列稀释存在的全部理由。**

### 2.7 滴定分析的原理 (principle of titration)

材料的定义（实验二引言）：

> "Titration is a common laboratory method for **quantifying concentrations** based upon finding the **equivalence point** of a reaction (also referred to as the **end-point**). The **titrant** (of known concentration) is added stepwise to an **analyte** solution until there is an indication that the reaction is complete."

**术语三件套**（必须分清）：

| 术语 | 含义 | 本实验中是谁 |
| --- | --- | --- |
| **titrant（滴定剂 / 标准溶液）** | **已知浓度**、从滴定管加入的溶液 | 0.5 M AgNO₃ |
| **analyte（被测物 / 待测液）** | **未知浓度**、放在锥形瓶/烧杯中的溶液 | 2.5 ml "海水" |
| **indicator（指示剂）** | 提示反应完成的物质 | 荧光素 fluorescein |

**等当点 vs 终点（这是最容易混的一对，材料把两者当同义词，但严格上有区别）**：

- **等当点 / 化学计量点 (equivalence point)**：理论上滴定剂加入的物质的量**恰好**与被测物按化学计量比完全反应的那一刻。这是一个**理论点**，看不见。
- **终点 (end-point)**：**实际观察到**指示剂变色的那一刻。这是一个**实验点**。
- 两者之差叫**滴定误差 (titration error) / 指示剂误差**。好的指示剂使 end-point 尽可能接近 equivalence point。

材料还给出了**指示终点的几种方式**（很值得记，因为它把本周两个实验串起来了）：

> "the indicator may be a visible change (**colour, precipitate**) or a change in **electrical conductivity**, **pH** or some other measurable parameter."

即：**目视终点（颜色/沉淀）、电导滴定 (conductometric titration)、电位滴定 (potentiometric / pH titration)**——后两种正好用到实验一学的两种测量。

**为什么滴定又叫容量分析 (volumetric determination / volumetric analysis)**：因为最终的定量信息来自"**记录滴定剂的体积**"这一个读数。与之相对的是 §5.2.7 的**重量分析 (gravimetric analysis)**。

### 2.8 沉淀滴定与银量法 (precipitation titration / argentometric titration)

本实验的反应（材料原式）：

$$\mathrm{AgNO_3\,(aq)} + \mathrm{NaCl\,(aq)} \;\rightleftharpoons\; \mathrm{NaNO_3\,(aq)} + \mathrm{AgCl\,(s)}\!\downarrow$$

**净离子方程式 (net ionic equation)**——去掉旁观离子 Na⁺ 和 NO₃⁻ (spectator ions)：

$$\boxed{\mathrm{Ag^{+}\,(aq)} + \mathrm{Cl^{-}\,(aq)} \longrightarrow \mathrm{AgCl\,(s)}\!\downarrow \quad (\text{白色沉淀 white precipitate})}$$

**化学计量比 1 : 1**——这是后面所有计算的基石：$n(\mathrm{Ag^+}) = n(\mathrm{Cl^-})$。

**为什么这个反应能用于滴定**：AgCl 极难溶，**溶度积 (solubility product)**

$$K_{sp}(\mathrm{AgCl}) = [\mathrm{Ag^+}][\mathrm{Cl^-}] = 1.8\times10^{-10} \ (25\,^\circ\mathrm{C})$$

反应平衡常数 $K = 1/K_{sp} = 5.6\times10^{9}$，即反应**几乎完全进行到底**——这是滴定反应的四个必要条件之一。

**滴定反应必须满足的四个条件（通用，务必记）**：
1. 反应**定量完全** ( > 99.9%)，即平衡常数足够大；
2. 反应**化学计量关系确定**（无副反应）；
3. 反应**速率快**（加一滴就立刻反应完，否则终点会"漂移"）；
4. 有**合适的终点指示方法**。

**三种经典银量法（Mohr / Volhard / Fajans）——必须分清，本实验用的是 Fajans 法**：

| 方法 | 指示剂 | 终点现象 | 适用 pH | 原理类型 |
| --- | --- | --- | --- | --- |
| **莫尔法 (Mohr method)** | 铬酸钾 K₂CrO₄ | 出现**砖红色** Ag₂CrO₄ 沉淀 | 6.5 – 10.5（中性至弱碱性） | **生成有色沉淀** |
| **佛尔哈德法 (Volhard method)** | 铁铵矾 Fe³⁺ (NH₄Fe(SO₄)₂) | 过量 SCN⁻ 与 Fe³⁺ 生成**血红色** [FeSCN]²⁺ | 强酸性（HNO₃ 介质） | **返滴定 (back-titration) + 有色配合物** |
| **法扬斯法 (Fajans method)** ← **本实验** | **荧光素 fluorescein**（吸附指示剂 adsorption indicator） | 白色 AgCl 沉淀表面**突然变粉红/玫瑰红** | ~7 – 8（近中性） | **吸附指示剂** |

> ⚠️ **点名注意**：本周材料用的指示剂是 **fluorescein（荧光素）**，因此对应的是 **Fajans 法（吸附指示剂法）**，**不是 Mohr 法**（Mohr 法用铬酸钾）。答题时不要混。三种方法都应知道，但本实验必须写 Fajans。

**Fajans 法（吸附指示剂）的作用机理——本周最需要讲透的机理**：

1. 荧光素是一种弱有机酸染料，在近中性溶液中解离成**荧光素根阴离子 (fluoresceinate anion, Fl⁻)**，溶液呈黄绿色。
2. **等当点之前**：溶液中 Cl⁻ 过量。新生成的 AgCl 是**胶体颗粒 (colloid)**，其表面优先吸附溶液中**过量的、与晶格同种的离子**（Paneth–Fajans–Hahn 吸附规则），即吸附 Cl⁻ → **胶粒表面带负电**。带负电的表面**排斥**同样带负电的 Fl⁻ → 指示剂留在溶液中 → **沉淀是白色的**。
3. **等当点之后（哪怕只多一滴）**：Cl⁻ 耗尽，溶液中 **Ag⁺ 开始过量**。胶粒表面转而吸附 Ag⁺ → **表面翻转为带正电**。带正电的表面**静电吸引** Fl⁻ → 荧光素根被吸附到沉淀表面，形成表面配合物、电子结构改变 → **沉淀表面骤然变成粉红/玫瑰红色**。
4. 材料的描述与此完全对应：
   > "you will observe a **precipitate forms and coagulates**." （沉淀生成并**聚沉**）
   > "The end point is indicated by a **sudden development of colour change on the precipitate**." （**颜色变化发生在沉淀上，不是在溶液里！**）

**因此判断终点的正确姿势**：**盯着沉淀本身的颜色，不是盯着上清液。** 这是 Fajans 法与 Mohr/Volhard 法在操作观感上的最大区别，也是最常被搞错的一点。

**Fajans 法的几个实操约束（补充，材料未写但解释了为什么容易失败）**：
- **pH 必须适中（约 7–8）**：荧光素 p$K_a \approx 6.7$。太酸 → Fl⁻ 被质子化成中性 HFl，不带电就不会被吸附，终点不显色；太碱 → Ag⁺ 会生成 AgOH/Ag₂O 沉淀。
- **沉淀比表面积要大**：吸附指示剂靠表面显色，颗粒聚沉得太厉害（表面积骤减）会让终点变钝。标准做法是加**糊精 (dextrin)** 作保护胶体防止凝聚——微量实验中省略了，所以材料才强调"**swirl the flask regularly**（勤摇动）"来维持分散。
- **避光**：AgCl 见光分解（$2\mathrm{AgCl} \xrightarrow{h\nu} 2\mathrm{Ag} + \mathrm{Cl_2}$），沉淀会变灰紫，干扰对粉红色的判断。滴定要快、不要拖在强光下。

### 2.9 氯度、盐度及其关系 (chlorinity & salinity)

**这一节是本周标题里"seawater salinity"的落点，材料只给了 Cl 的 g/L，换算到盐度需要补充知识。**

**氯度 (chlorinity, Cl‰ 或 Cl)**——历史上的严格定义就是**从银量滴定来的**（所以这个实验有历史意义）：

> 氯度定义为：沉淀 328.5233 g 海水中全部卤素 (halides) 所需的"原子量银"的克数。等价的现代表述：
> $$\mathrm{Cl}\,(‰) = 0.3285234 \times m_{\mathrm{Ag}}\ (\text{每 kg 海水所需 Ag 的克数})$$

注意氯度不只包含 Cl⁻，还包含 Br⁻、I⁻ 等其他卤素（它们同样被 Ag⁺ 沉淀），只是**折算成"等效氯"**表示。这是氯度与"氯离子浓度"的细微差别。

**盐度 (salinity, S)**——海水中溶解盐类的总量，单位 g/kg（‰）或无量纲的 PSU。

**盐度与氯度的换算公式（两代）**：

$$\text{Knudsen (1902)}:\quad S\,(‰) = 0.030 + 1.8050 \times \mathrm{Cl}\,(‰)$$

$$\boxed{\text{UNESCO (1969)，现行}:\quad S\,(‰) = 1.80655 \times \mathrm{Cl}\,(‰)}$$

**这两个公式为什么能成立？——恒定比例定律 (Principle of Constant Proportions / Marcet's Principle, Dittmar 1884)**：

> **无论海水总盐度高低，其主要溶解成分之间的质量比例几乎恒定。**

海水主要离子的恒定质量占比（补充参考）：

| 离子 | 占总盐分质量比 | 每 kg 盐度 35 的海水中 (g) |
| --- | --- | --- |
| **Cl⁻** | 55.0 % | 19.35 |
| **Na⁺** | 30.6 % | 10.76 |
| SO₄²⁻ | 7.7 % | 2.71 |
| Mg²⁺ | 3.7 % | 1.29 |
| Ca²⁺ | 1.2 % | 0.41 |
| K⁺ | 1.1 % | 0.39 |
| 其余 | < 1 % | — |
| **合计** | **≈ 100 %** | **35.0** |

**这正是为什么只测一个 Cl⁻ 就能推出全部盐度**：Cl⁻ 占了 55%，且比例恒定，所以 $S \approx 1.807\,\mathrm{Cl}$。**这是本周实验"为什么值得做"的科学理由，务必答出来。**

**基准对应关系（记住这一组数）**：

$$\mathrm{Cl} = 19.374\ \mathrm{g/kg} \;\Longleftrightarrow\; S = 35.000\ \mathrm{g/kg} \quad (1.80655 \times 19.374 = 35.00\ \checkmark)$$

**现代做法：实用盐度标度 (Practical Salinity Scale 1978, PSS-78)**——**这是把实验一和实验二真正连起来的桥梁**：

现代海洋学**不再做滴定**，而是**测电导率**。PSS-78 定义盐度为水样电导率与标准 KCl 溶液（每 kg 溶液含 32.4356 g KCl）在 15 °C、1 atm 下电导率之比 $K_{15}$ 的函数：

$$K_{15} = \frac{\kappa(\text{样品},\,15\,^\circ\mathrm{C},\,1\,\mathrm{atm})}{\kappa(\text{标准 KCl},\,15\,^\circ\mathrm{C},\,1\,\mathrm{atm})}, \qquad K_{15}=1 \;\Longleftrightarrow\; S = 35.000$$

盐度因此是**无量纲**的（单位常写作 PSU, Practical Salinity Unit，严格说 PSU 不是 SI 单位，只是习惯写法）。

**再新一代：TEOS-10 (2010)** 引入**绝对盐度 (Absolute Salinity, $S_A$)**，单位真正是 g/kg，校正了不同海域成分微小差异（如深层水中溶解硅酸盐的贡献）对电导率法的偏差。

**串起来的逻辑链（本周的"大图"）**：
$$\text{Cl}^- \text{ 占海水盐分 55\% 且比例恒定} \;\Rightarrow\; \text{测 Cl}^- \text{ 可得盐度（滴定法，实验二）} \;\Rightarrow\; \text{离子总量决定电导率（实验一）} \;\Rightarrow\; \text{测电导率可直接得盐度（CTD 仪，PSS-78）}$$

海洋学仪器 **CTD（Conductivity–Temperature–Depth）**就是这条链的工程产物：它测电导率而非化学滴定，因为电导率可以**原位、连续、每秒 24 次**测量，而滴定只能一份一份做。

### 2.10 电导率与离子强度 (ionic strength)

**离子强度 (ionic strength) $I$** 是描述溶液中"电荷环境总强度"的量：

$$I = \frac{1}{2}\sum_i c_i z_i^{2}$$

- $c_i$：第 $i$ 种离子的摩尔浓度 (mol/L)
- $z_i$：该离子的电荷数（带正负号，平方后为正）

例：0.005 M NaOH → $I = \tfrac12[(0.005)(+1)^2 + (0.005)(-1)^2] = 0.005$ M。**1:1 型电解质的离子强度就等于其浓度。**
例：0.54 M NaCl（本实验的"海水"）→ $I = 0.54$ M。
例：0.01 M MgSO₄（2:2 型）→ $I = \tfrac12[(0.01)(4)+(0.01)(4)] = 0.04$ M，是浓度的 4 倍。

**离子强度与电导率的关系**：低浓度下二者近似正比（离子越多越导电）；但浓度升高后，**离子间静电相互作用（松弛效应 relaxation effect 与电泳效应 electrophoretic effect）**使每个离子的有效迁移率下降，摩尔电导率随浓度上升而**下降**——这就是**科尔劳施平方根定律 (Kohlrausch's law)**：

$$\Lambda_m = \Lambda_m^{\circ} - K\sqrt{c}$$

其中 $\Lambda_m^\circ$ 是无限稀释时的**极限摩尔电导率**，$K$ 是与电解质类型和溶剂相关的常数。因此**电导率与浓度并非严格线性**，在高盐度（海水）时尤其明显——这也是 PSS-78 要用一个复杂的多项式而不是简单比例式的原因。

**离子独立迁移定律 (Kohlrausch's law of independent migration of ions)**：

$$\Lambda_m^{\circ} = \nu_+\lambda_+^{\circ} + \nu_-\lambda_-^{\circ}$$

即无限稀释时，电解质的摩尔电导率等于各离子贡献之和（离子彼此独立）。用它就能从 §2.3 的表算出任意强电解质的 $\Lambda^\circ$（见 §3.5 的算例）。

### 2.11 电学基础：欧姆定律与 LED

**欧姆定律 (Ohm's Law)** 的三种形式：

$$V = IR \qquad I = \frac{V}{R} \qquad R = \frac{V}{I}$$

- $V$：电压 / 电位差 (voltage, potential difference)，单位 **V（伏特）**
- $I$：电流 (current)，单位 **A（安培）**；1 mA = 10⁻³ A
- $R$：电阻 (resistance)，单位 **Ω（欧姆）**

**LED (light emitting diode, 发光二极管) 的两个关键特性**：

1. **有极性 (polarity)**：材料原文——
   > "Current flows from the **anode (positive, long wire)** to the **cathode (negative, short wire)**, so ensure that the **anode is connected to the red (+) wire** from the battery."
   > **长脚 = 阳极 = 接正极（红线）；短脚 = 阴极 = 接负极。**
   接反的后果：材料明确说 **"you won't damage the LED, but it won't light"**——二极管反向截止，不亮但不坏。
2. **有正向压降 (forward voltage drop, $V_f$)**：LED 导通后两端维持一个近乎固定的电压降，本实验从技术规格书 (technical specification sheet) 查得 $V_f = 4$ V。**这个值必须查规格书，不能猜**（红色 LED 约 1.8–2.2 V，蓝/白色 LED 约 3–4 V）。
3. **有最大额定电流 (maximum current rating)**：本 LED 为 **20 mA**。

**为什么必须串联电阻 (why do we need a resistor)？**——材料给的理由：

> "The 9V battery typically produces a current of up to a few hundred milliamps (mA), whereas our LED bulb has a **maximum rating of 20 mA**. If we connected it directly to the battery it may work for a few seconds/minutes but it would **become hot and eventually may burn-out**."

即：**LED 本身不限流**（它的 I–V 特性极陡，电压略升电流暴涨），必须靠串联的**限流电阻 (current-limiting resistor)** 把电流压到额定值以下。

材料补充的两个实用要点：
- **电阻可以放在电路的任何位置，也不分方向**："it does not matter where you put the resistor in the circuit (or which way around you connect it)"——串联电路中各处电流相同，电阻是无极性元件。
- **可以用比计算值更大的电阻**："We can use a higher gain resistor than the value calculated and it will still provide enough current for the LED (remember it only needs a few mA)"。材料还说 **"anything between a few to 10 mA provides a perfectly adequate light"**——几个到 10 mA 就足够亮了。

**电阻色环 (resistor colour code)**：材料提示——
> "Resistors are colour coded, usually with **4-6 colour bands**. The trick is to know **which direction to read them**, usually there is a notable **wider gap between the final two bands**, although it is not always easy to spot on a 6-band resistor."

**读色环的关键是先定方向**：容差环（通常金/银色）在末尾，且与前面的环之间有较宽间隙——把它放在右边再从左往右读。材料推荐用在线工具：`https://uk.farnell.com/resistor-colour-code-calculator`。

色环数值对照（补充）：黑 0、棕 1、红 2、橙 3、黄 4、绿 5、蓝 6、紫 7、灰 8、白 9；乘数环同色表示 10ⁿ；容差：金 ±5%、银 ±10%。

---

## 三、公式与图表

### 3.1 限流电阻的计算（实验一，欧姆定律应用）

$$\boxed{R_{\min} = \frac{V_b - V_f}{I_{\max}}}$$

| 符号 | 含义 | 本实验取值 |
| --- | --- | --- |
| $V_b$ | 电池电压 (battery voltage) | 9 V |
| $V_f$ | LED 正向压降 (forward voltage drop across the LED)，查规格书 | 4 V |
| $I_{\max}$ | LED 最大额定电流 (maximum current of the LED) | 20 mA = **0.02 A** |
| $R_{\min}$ | 所需最小电阻 | 待求 |

**代入（材料给出的标准答案）**：

$$R_{\min} = \frac{9 - 4}{0.02} = \frac{5}{0.02} = \boxed{250\ \Omega}$$

**关键量纲检查**：$\dfrac{\mathrm{V}}{\mathrm{A}} = \Omega$ ✓。**最常见的错误是把 20 mA 直接当成 20 代入，得到 R = 0.25 Ω——必须先换算成 0.02 A。**

**反算实际电阻对应的电流**（材料给出的两种电阻）：

| 电阻 | 色环 | 电流 $I = (V_b - V_f)/R$ | 是否安全 |
| --- | --- | --- | --- |
| **640 Ω** | 4 环：blue-yellow-black-black（蓝-黄-黑-黑） | $5/640 = 7.8\times10^{-3}$ A = **7.8 mA** | ✓ < 20 mA，且 > 几 mA，够亮 |
| **1000 Ω** | 3 环：brown-black-red（棕-黑-红） | $5/1000 = 5\times10^{-3}$ A = **5.0 mA** | ✓ < 20 mA，够亮 |

> 色环核对：brown(1)-black(0)-red(×100) = 10 × 100 = **1000 Ω** ✓。
> blue(6)-yellow(4)-black(0)-black(×1) 按 5 环读法 = 640 × 1 = **640 Ω** ✓（材料称之为 4 环，实际是把 640 的三位有效数字 + 乘数一起读；考试时按材料给的 640 Ω 记即可）。

**结论**：640 Ω 与 1000 Ω **都远大于计算出的最小值 250 Ω，因此都安全可用**；电流 7.8 mA / 5.0 mA 落在"几到 10 mA 足够亮"的区间内。

### 3.2 稀释计算（实验一问题 1）

$$\boxed{M_1 V_1 = M_2 V_2 \quad\Longrightarrow\quad M_2 = \frac{M_1 V_1}{V_2}}$$

| 符号 | 含义 | 单位 |
| --- | --- | --- |
| $M_1$ | 原液摩尔浓度 (initial molarity) | mol/L = M |
| $V_1$ | 取出的原液体积 (aliquot volume) | ml（两边同单位即可，不必换 L） |
| $M_2$ | 稀释后浓度 | M |
| $V_2$ | **稀释后总体积** = $V_1$ + 加入的水 | ml |

**Beaker 1**（材料原答：`0.1 x 0.1 = M2 x 2 = 0.005 M`）：

$$M_2 = \frac{0.10\ \mathrm{M} \times 0.1\ \mathrm{ml}}{(0.1+1.9)\ \mathrm{ml}} = \frac{0.010}{2.0} = \boxed{0.005\ \mathrm{M}} = 5\times10^{-3}\ \mathrm{M}$$

**Beaker 2**（取 Beaker 1 的 0.1 ml + 1.9 ml 水，再稀 20 倍）：

$$M_3 = \frac{0.005\ \mathrm{M} \times 0.1\ \mathrm{ml}}{2.0\ \mathrm{ml}} = \frac{0.005}{20} = \boxed{0.00025\ \mathrm{M}} = 2.5\times10^{-4}\ \mathrm{M}$$

**HCl 完全同理，数值相同**（材料原文："Same for both HCl and NaOH"），因为两者原液浓度都是 0.10 M、稀释操作相同。

**总稀释因子检查**：$0.10 / 0.00025 = 400 = 20^2$ ✓（两级各 20 倍）。

### 3.3 pH / pOH 计算（实验一问题 2）

**酸（HCl，强酸，一元）**：

$$[\mathrm{H^+}] = [\mathrm{HCl}] \quad\Longrightarrow\quad \mathrm{pH} = -\log_{10}[\mathrm{H^+}]$$

**碱（NaOH，强碱，一元）**：

$$[\mathrm{OH^-}] = [\mathrm{NaOH}] \;\Longrightarrow\; \mathrm{pOH} = -\log_{10}[\mathrm{OH^-}] \;\Longrightarrow\; \mathrm{pH} = 14 - \mathrm{pOH}$$

**完整四组计算（材料答案 + 补全的 Beaker 2 过程）**：

| 溶液 | 浓度 (M) | 计算过程 | **预测 pH** | **实测 pH（试纸）** | 差值 |
| --- | --- | --- | --- | --- | --- |
| **HCl Beaker 1** | 0.005 | $\mathrm{pH} = -\log(5\times10^{-3}) = 2.30$ | **2.3** | 2 | −0.3 |
| **HCl Beaker 2** | 0.00025 | $\mathrm{pH} = -\log(2.5\times10^{-4}) = 3.60$ | **3.6** | 4 | +0.4 |
| **NaOH Beaker 1** | 0.005 | $\mathrm{pOH} = -\log(5\times10^{-3}) = 2.30$；$\mathrm{pH} = 14 - 2.30$ | **11.7** | 12 | +0.3 |
| **NaOH Beaker 2** | 0.00025 | $\mathrm{pOH} = -\log(2.5\times10^{-4}) = 3.60$；$\mathrm{pH} = 14 - 3.60$ | **10.4** | 10 | −0.4 |

**对数速算技巧（考试无计算器时）**：
$-\log(5\times10^{-3}) = 3 - \log 5 = 3 - 0.699 = 2.30$
$-\log(2.5\times10^{-4}) = 4 - \log 2.5 = 4 - 0.398 = 3.60$
（记住 $\log 2 = 0.301$、$\log 2.5 = 0.398$、$\log 5 = 0.699$ 就够用了。）

**规律检查**：稀释 20 倍 ⇒ $\Delta\mathrm{pH} = \log_{10} 20 = 1.30$。核对：HCl 从 2.30 → 3.60，差 1.30 ✓；NaOH 从 11.7 → 10.4，差 1.30 ✓。**稀释 10 倍恰好改变 1 个 pH 单位——这是必须内化的直觉。**

**预测值与实测值的对比（材料问题要求 "How do these compare with your measured values?"）**：
实测与预测最多差 0.4 个 pH 单位。**万用指示剂试纸的分辨率本来就只有 ±0.5–1 个 pH 单位**（靠肉眼比色卡读整数），因此**这个吻合程度是完全令人满意的**——试纸的整数读数就是把 2.3 读成 2、把 3.6 读成 4、把 11.7 读成 12、把 10.4 读成 10。**答题要点：差异来源是"指示剂试纸的分辨率限制"，而非计算或配液错误。**

**顺带一提的稀释极限（补充思考题，常考）**：如果继续稀释 HCl 到 10⁻⁸ M，能不能得到 pH = 8（碱性）？**不能。** 极稀酸溶液中必须把**水自身解离产生的 H⁺** 计入，做质子守恒/电荷守恒联立，结果 pH 只会**无限趋近 7 但始终略小于 7**（永远是酸性）。本实验浓度都 ≥ 2.5×10⁻⁴ M，远大于 10⁻⁷，可以放心忽略水的贡献。

### 3.4 滴定的浓度计算（实验二核心，含完整量纲）

**四步走，每一步都写单位。**

**Step 1 — 算滴定剂的物质的量 (moles of titrant)**

$$\boxed{n = M \times V}$$

| 符号 | 含义 | 单位 | 本例 |
| --- | --- | --- | --- |
| $n$ | 物质的量 (number of moles) | **mol** | 待求 |
| $M$ | 摩尔浓度 (molarity) | **mol/L** | 0.5 mol/L AgNO₃ |
| $V$ | 体积 | **必须是 L！** | 2.7 ml → 2.7/1000 = 0.0027 L |

$$n(\mathrm{AgNO_3}) = 0.5\ \mathrm{mol\,L^{-1}} \times \frac{2.7}{1000}\ \mathrm{L} = 1.35\times10^{-3}\ \mathrm{mol}$$

**量纲检查**：$\mathrm{mol\,L^{-1}} \times \mathrm{L} = \mathrm{mol}$ ✓

**Step 2 — 用化学计量比转到被测物**

AgNO₃ 完全解离（材料明确提示 "assume silver nitrate in solution fully dissociates into its constituent ions"）：$\mathrm{AgNO_3 \to Ag^+ + NO_3^-}$，故 $n(\mathrm{Ag^+}) = n(\mathrm{AgNO_3})$。

由净离子方程 $\mathrm{Ag^+ + Cl^- \to AgCl}$，**计量比 1 : 1**：

$$\boxed{n(\mathrm{Cl^-}) = n(\mathrm{Ag^+}) = 1.35\times10^{-3}\ \mathrm{mol}}$$

> **通用形式**：若反应为 $a\,\mathrm{A} + b\,\mathrm{B} \to$ 产物，则 $n_B = \dfrac{b}{a} n_A$。本例 $a = b = 1$，所以直接相等；换成 SO₄²⁻ 与 Ba²⁺ 也是 1:1，但换成 Ag⁺ 与 CrO₄²⁻ 就是 2:1，**不要习惯性照抄 1:1**。

**Step 3 — 除以样品体积，得摩尔浓度**

$$\boxed{M(\mathrm{Cl^-}) = \frac{n(\mathrm{Cl^-})}{V_{\text{sample}}\ (\mathrm{L})}}$$

$$M(\mathrm{Cl^-}) = \frac{1.35\times10^{-3}\ \mathrm{mol}}{2.5/1000\ \mathrm{L}} = \frac{1.35\times10^{-3}}{2.5\times10^{-3}} = \boxed{0.54\ \mathrm{mol\,L^{-1}}}$$

> ⚠️ **材料答案里的一处笔误**：原文写作 "M (mol/L) = n (moles) **x** V(L)"，随后代入的却是 `1.35 x 10⁻³ /(2.5/1000)`（**除法**）。**正确关系是 $M = n \div V$，即 $M = n/V$。乘号是打字错误，代入过程是对的。**记忆口诀：**浓度 = 量 ÷ 体积**，量纲上 mol ÷ L = mol/L ✓。

**Step 4 — 摩尔浓度换算成质量浓度 g/L**

$$\boxed{\rho\ (\mathrm{g/L}) = M\ (\mathrm{mol/L}) \times A_r\ (\mathrm{g/mol})}$$

Cl 的相对原子质量 $A_r = 35.453$ g/mol（材料给出）：

$$\rho(\mathrm{Cl^-}) = 0.54\ \mathrm{mol\,L^{-1}} \times 35.453\ \mathrm{g\,mol^{-1}} = \boxed{19.1\ \mathrm{g/L}}$$

**量纲检查**：$\mathrm{mol\,L^{-1}} \times \mathrm{g\,mol^{-1}} = \mathrm{g\,L^{-1}}$ ✓

**与文献值比较（材料要求 "Comment on how they compare"）**：

- 查得的天然海水氯度：**≈ 19.4 g/L Cl**
- 实验测得：**19.1 g/L**
- 相对偏差：$\dfrac{19.1 - 19.4}{19.4} \times 100\% = -1.3\%$

**结论表述**：测得值 19.1 g/L 与文献值 19.4 g/L **高度吻合 (similar to the value looked up)**，偏差仅约 1.3%，在微量滴定（一滴 ≈ 0.04 ml，占 2.7 ml 的 1.5%）的固有精度范围之内——**误差与"一滴的分辨率"同量级，说明实验没有系统性失误。**

**Step 2b — 材料另问的"每 1 ml 中的 Cl⁻ 物质的量"**：

$$n_{\text{per ml}} = \frac{1.35\times10^{-3}\ \mathrm{mol}}{2.5\ \mathrm{ml}} = 5.4\times10^{-4}\ \mathrm{mol/ml}$$

（乘 1000 即得 0.54 mol/L，与 Step 3 自洽 ✓）

**把四步压成一个总式（考试可直接用）**：

$$\boxed{\rho_{\mathrm{Cl^-}}\ (\mathrm{g/L}) = \frac{M_{\mathrm{AgNO_3}} \times V_{\mathrm{AgNO_3}}}{V_{\text{sample}}} \times A_r(\mathrm{Cl})}$$

代入验算：$\dfrac{0.5 \times 2.7}{2.5} \times 35.453 = 0.54 \times 35.453 = 19.1$ g/L ✓
（注意：$V$ 只要**上下同单位**就可以直接用 ml，不必换 L——因为体积之比是无量纲的。这是加速计算的小技巧，但**中间步骤单独算 $n$ 时必须换成 L**。）

### 3.5 电导率的估算（补充：为什么 LED 亮/暗）

用离子独立迁移定律 $\Lambda_m^\circ = \lambda_+^\circ + \lambda_-^\circ$ 和 $\kappa = \Lambda_m^\circ \times c$（$c$ 换成 mol/cm³，即 mol/L ÷ 1000）：

| 溶液 | $\Lambda_m^\circ$ (S·cm²/mol) | $\kappa$ 估算 | LED 现象（材料实测） |
| --- | --- | --- | --- |
| 0.005 M HCl | 349.8 + 76.3 = **426.1** | $426.1 \times 5\times10^{-6} = 2.13\times10^{-3}$ S/cm = **2130 µS/cm** | **bright（亮）** |
| 0.00025 M HCl | 426.1 | **107 µS/cm** | **dull（暗）** |
| 0.005 M NaOH | 50.1 + 198.0 = **248.1** | $248.1 \times 5\times10^{-6} = 1.24\times10^{-3}$ S/cm = **1240 µS/cm** | **bright（亮）** |
| 0.00025 M NaOH | 248.1 | **62 µS/cm** | **dull（暗）** |
| 0.54 M NaCl（实验二"海水"） | 50.1 + 76.3 = 126.4（实际因离子相互作用低得多） | 实测海水 ≈ **50 000 µS/cm** | 会非常亮 |

**读表要点**：
1. 浓度差 20 倍 ⇒ 电导率差 20 倍 ⇒ **LED 从"亮"变"暗"**，与材料实验表完全一致。
2. **同浓度下 HCl 的电导率高于 NaOH**（2130 vs 1240 µS/cm），因为 $\lambda^\circ(\mathrm{H^+}) = 349.8 > \lambda^\circ(\mathrm{OH^-}) = 198.0$。**这是"H⁺ 是所有离子中最快的"的直接量化证据。**
3. 海水电导率比本实验最浓的溶液还高一个数量级——所以海洋 CTD 才能用电导率精确测盐度。

### 3.6 盐度换算（补充，用本实验数据）

**从实测氯度算盐度**，需要两步：

**Step A — 把 g/L（体积浓度）换成 g/kg（质量浓度）**，因为氯度/盐度定义都是"每 kg 海水"：

$$\mathrm{Cl}\ (\mathrm{g/kg}) = \frac{\rho_{\mathrm{Cl}}\ (\mathrm{g/L})}{\rho_{\text{seawater}}\ (\mathrm{kg/L})}$$

海水密度 $\rho_{\text{seawater}} \approx 1.025$ kg/L（S = 35，25 °C）：

$$\mathrm{Cl} = \frac{19.1}{1.025} = 18.6\ \mathrm{g/kg} = 18.6‰$$

**Step B — 代入 UNESCO 换算式**：

$$S = 1.80655 \times \mathrm{Cl} = 1.80655 \times 18.6 = \boxed{33.7}$$

**用文献值核对**：$\mathrm{Cl} = 19.4/1.025 = 18.93$ g/kg → $S = 1.80655 \times 18.93 = 34.2$；标准海水 $\mathrm{Cl} = 19.374$ g/kg → $S = 35.00$。

**结论**：本实验的"海水"盐度约 **33–34**，落在真实海水 33–37 的正常范围内 ✓。

> ⚠️ **最常见的换算错误**：**直接把 g/L 当成 ‰ 用**。‰ 的定义是"每千克溶液中的克数"（g/kg），而不是"每升溶液中的克数"（g/L）。海水密度 1.025 使二者相差 2.5%——在盐度上就是 0.9 个盐度单位，对海洋学来说是巨大的误差。**必须先除以密度。**

### 3.7 实验一的结果记录表（材料原表，完整）

| Beaker | Concn. **NaOH** (M) | LED – dull/bright | pH of solution |
| --- | --- | --- | --- |
| **1** | 0.005 | **bright**（亮） | 12 |
| **2** | 0.00025 | **dull**（暗） | 10 |

| Beaker | Concn. **HCl** (M) | LED – dull/bright | pH of solution |
| --- | --- | --- | --- |
| **1** | 0.005 | **bright**（亮） | 2 |
| **2** | 0.00025 | **dull**（暗） | 4 |

**读表的三条结论**：
1. **浓度 ↓ → LED 变暗 → 电导率 ↓**（离子总浓度下降）；
2. **浓度 ↓ → pH 向 7 靠拢**（酸从 2→4，碱从 12→10）；
3. **酸碱两侧对称**：对 pH 而言，NaOH 的 12 与 HCl 的 2 关于 7 对称（因为 $\mathrm{pH} + \mathrm{pOH} = 14$，两者的 [H⁺] 与 [OH⁻] 数值相同）。

### 3.8 电路图（材料描述的重建）

材料原文描述了两张图（PDF 中的图片未转成文字），文字重建如下：

```
        ┌──── [ 电阻 R = 640 或 1000 Ω ] ────┐
        │                                    │
   ┌────┴────┐                          ┌────┴────┐
   │  9 V    │(+, 红线)          (阳极长脚)│  LED   │
   │ 电池    │                          │        │
   │ (snap-on│                          └────┬────┘
   │  battery│                               │(阴极短脚)
   │   cap)  │                               │
   └────┬────┘                          ─────┘
        │(−, 黑线)                           │
        │                                    │
     电极 A ●                             ● 电极 B
              ↘  两根裸线插入待测溶液  ↙
              （电路故意"不闭合"，由溶液充当导体完成回路）
```

**这张图最重要的设计思想（材料原句）**：

> "Notice in the diagram left, that I have **not closed the circuit** – the two wires will act as **electrodes**. I can place them in a solution to see if it is conducting."

即：**电路故意留一个断口，把两根裸线当电极插入溶液，让溶液本身成为电路的一部分。** 溶液导电 ⇒ 回路闭合 ⇒ LED 亮；溶液不导电 ⇒ 回路断开 ⇒ LED 不亮。LED 的**亮度**则半定量地反映**电流大小**，进而反映**电导率大小**。

**元件清单**：9 V 电池 + 电池扣 (snap-on battery cap) + 导线 (wires) + 限流电阻 (resistor) + LED。

**装好后的自检**：材料说 **"check your circuit is working by touching the two ends of the wires. The LED should light-up."**——**把两根电极直接短接，LED 应亮。若不亮，说明电路本身有问题（多半是 LED 接反），而不是溶液不导电。这一步必须在测样品之前做，否则会把电路故障误判成"溶液不导电"。**

---

## 四、课堂补充

**（本周无 lecture 与 transcript。）**

本周两份材料均为**实验讲义答案版 (answer/model-answer version of the practical handout)**，没有教学视频转写、没有录音、没有幻灯片。所有"课堂内容"都以问题与标准答案的形式嵌在讲义里，已在 §五 中逐题梳理。

需要在此单独记录的、材料中散落的**非实验步骤类补充说明**有三条：

1. **绿色/微量化学的态度声明**（实验二引言，加粗强调）：
   > "**Please follow the instructions carefully.** In particular, note that the micro-chemical procedures that we will be using are designed to **minimise the amount of chemicals used and their impact on the environment**."

   ——这是专业素养 (professional skills) 层面的要求，也解释了为什么全套实验只用几毫升试剂、用注射器代替标准滴定管。

2. **外部工具推荐**：电阻色环在线计算器 `https://uk.farnell.com/resistor-colour-code-calculator`。材料明确说 "using an online tool is easiest"——**在真实工程实践里查表/用工具是被鼓励的，不必背色环表**（但考试可能要求会读）。

3. **"seawater" 打了引号**（材料写作 `"seawater"` 并带脚注标记 ¹）：说明本实验用的是**人工配制的模拟海水（很可能就是纯 NaCl 溶液）**，而非真实海水样品。**这一点在讨论结果时很重要**：真实海水含 Br⁻、I⁻ 等其他卤素，也会被 Ag⁺ 沉淀，测得的是"氯度 (chlorinity)"而非纯粹的"氯离子浓度"；而人工海水只有 Cl⁻，两者相等。（材料中脚注 1 的正文在 PDF 转换时丢失，此处为合理推断。）

---

## 五、Practical 要点

> **本节是本周的重心。两个实验分别展开：目的 → 试剂与仪器 → 详细步骤 → 数据记录 → 完整计算 → 结果判读 → 逐题答案。**

---

## 5.1 实验一：酸碱溶液浓度对电导率与 pH 的影响

### 5.1.1 目的与预期学习成果 (Intended Learning Outcomes)

材料列出四条 ILO，**每一条对应一项可考核的动手技能**：

1. **Be able to design and build a simple electrical current indicator device** —— 会设计并搭建简易电流指示装置（含用欧姆定律选电阻、识别 LED 极性）。
2. **Be able to carry-out a dilution to a specified concentration** —— 会按指定浓度做稀释（含 $M_1V_1=M_2V_2$ 计算与移液操作）。
3. **Be able to calculate a pH and measure it using indicator solution** —— 会**计算** pH，也会用指示剂**测量** pH。
4. **Be able to describe the effects of concentration of acids and bases on conductivity and pH** —— 会**描述并解释**浓度对电导率与 pH 的影响。

**总目标（材料引言）**：稀释 HCl 与 NaOH 溶液，**确定稀释对其电导率与 pH 的影响** ("determine what effect diluting these solutions has on their conductivities and their pH's")。

### 5.1.2 试剂与仪器 (Apparatus and Chemicals)

**仪器 (Apparatus)**：
- 2 × 10 ml 烧杯 (beakers)
- 1 × 10 ml 注射器 (syringe)——**本实验兼作移液器与"滴定管"，实验二会复用**
- 1 × 电流指示器及连线 (current indicator with connections)——自己搭的 LED 电路

**试剂 (Chemicals)**：
- 氢氧化钠 **NaOH(aq)，0.10 M**（强碱）
- 盐酸 **HCl(aq)，0.10 M**（强酸）
- **万用指示剂试纸 (universal indicator test paper)**——用于测 pH
- **去离子水 (de-ionised water)**——用于稀释与冲洗（**不能用自来水，理由见 §2.4**）

**安全提示（材料未明写，但属常识必答）**：0.1 M HCl 与 0.1 M NaOH 均具腐蚀性/刺激性，须戴护目镜 (safety goggles) 与手套；NaOH 溶液触感滑腻（皂化皮肤油脂），沾到立刻大量冲水。

### 5.1.3 阶段一：搭建 LED 电流指示器（步骤与要点）

| 步骤 | 操作 | 背后的原理 / 为什么 |
| --- | --- | --- |
| 1 | 查 LED 规格书，读出 $V_f = 4$ V、$I_{\max} = 20$ mA | 这两个参数决定电阻，不能靠猜 |
| 2 | 用欧姆定律算最小电阻 $R = (V_b - V_f)/I = (9-4)/0.02 = 250\ \Omega$ | 限流，防止 LED 过热烧毁 |
| 3 | 读手上电阻的色环，确认阻值（640 Ω 或 1000 Ω） | 二者都 > 250 Ω，安全 |
| 4 | **先画电路图**再接线 | 材料原句："It is always a good idea to **draw the circuit first** so you know how to connect components together and **avoid accidently damaging them**." |
| 5 | 接线：9V 电池 → 电池扣 → 电阻 → LED **长脚(阳极)接红线(+)** → LED 短脚 → 出裸线 | 二极管有极性；电阻位置与方向随意 |
| 6 | **不要闭合电路**——留下两根裸线当电极 | 让溶液充当回路的一段导体 |
| 7 | **自检：两根电极直接互碰，LED 应亮** | 排除电路本身故障，否则会误判溶液 |

### 5.1.4 阶段二：注射器液滴校准 (drop calibration)

**这一步是本周两个实验共用的基础操作，务必吃透。**

**操作（材料步骤 1）**：
1. 用注射器吸入几毫升**水**；
2. 用烧杯接住液滴，**缓慢推压活塞，数出恰好等于 0.5 ml 所对应的液滴数**；
3. **重复 3 次检查重复性 (repeatability)**；
4. 计算每滴体积。

**计算**：

$$\text{每滴体积} = \frac{0.5\ \mathrm{ml}}{\text{滴数}}$$

**材料给出的标准结果**：平均 **12.5 滴 = 0.5 ml**，故

$$\frac{0.5}{12.5} = \boxed{0.04\ \mathrm{ml/drop}}$$

材料备注："this may vary a little"——**每个人、每支注射器的滴径都可能略有不同，所以必须自己校准，不能照抄 0.04。**

**为什么要做这一步**：
- 注射器刻度最小分度通常是 0.1 或 0.2 ml，**目视只能读到 ±0.1 ml**；
- 而**数滴数**可以把分辨率提高到 **0.04 ml**，精度提升 2.5 倍；
- 在实验二的滴定中，接近终点时需要**一滴一滴**加，此时"一滴 = 多少 ml"就是最终结果精度的下限。

**为什么重复 3 次**：检验**重复性 (repeatability / precision)**。若三次结果差异很大（例如 10、12、15 滴），说明推压速度不稳或注射器口有气泡，需重做。**这是本课程一贯强调的"任何测量都要评估其不确定度"的体现。**

### 5.1.5 阶段三：系列稀释与测量（完整步骤）

材料的 12 步流程，整理为可执行清单：

| 步骤 | 操作 | 要点 |
| --- | --- | --- |
| 1 | 校准液滴体积（见 5.1.4） | 0.04 ml/drop |
| 2 | 注射器取 **0.1 ml 的 0.10 M NaOH** → **Beaker 1** | 用滴数控制：0.1 ml ≈ 2.5 滴 |
| 3 | **用水冲洗注射器** | ⚠️ **关键防交叉污染步骤**——不洗则残留 NaOH 会带进后续加水量 |
| 4 | 加 **1.9 ml 水** 到 Beaker 1 | 总体积 2.0 ml → 0.005 M |
| 5 | **旋摇 (swirl)** Beaker 1 混匀 | 不混匀 → 局部浓度不均 → 电极/试纸读数随位置变 |
| 6 | 注射器从 Beaker 1 取 **0.1 ml 溶液** → **Beaker 2** | 二级稀释开始 |
| 7 | **冲洗注射器**，再加 **1.9 ml 水**到 Beaker 2 | 总体积 2.0 ml → 0.00025 M |
| 8 | 旋摇 Beaker 2 混匀 | |
| 9 | 把电流表电极插入 **Beaker 1**，观察 LED，记录 | 结果：**bright** |
| 10 | **擦净电极 (wipe the electrodes clean)**，再测 Beaker 2 | ⚠️ **不擦净 → 高浓度残留把稀溶液"污染"成假阳性** |
| 11 | 用**万用指示剂试纸**测 Beaker 1、2 的 pH，记录 | 与比色卡对照读数 |
| 12 | **冲洗并擦干烧杯与注射器**，用 **0.10 M HCl** 重复步骤 1–11 | 材料原文写"repeat steps 1 to 10"，但显然应含步骤 11（测 pH），否则 HCl 组无 pH 数据——**讲义的小笔误** |

**移液时的量化提示**：0.1 ml ÷ 0.04 ml/drop = **2.5 滴**；1.9 ml ÷ 0.04 = **47.5 滴**。实际操作中 1.9 ml 用刻度读取更快，0.1 ml 用数滴更准。

### 5.1.6 数据记录（材料实测结果，已见 §3.7）

**NaOH 组**：0.005 M → bright / pH 12；0.00025 M → dull / pH 10
**HCl 组**：0.005 M → bright / pH 2；0.00025 M → dull / pH 4

### 5.1.7 逐题梳理（材料 Questions 1–4，含完整还原的计算）

---

**【问题 1】Calculate the concentration of each of the sodium hydroxide and hydrochloric acid solutions.**
（计算每份 NaOH 与 HCl 溶液的浓度，填入表 1。）

**材料答案原文**：
> "Same for both HCl and NaOH. M1V1 = M2V2. Beaker 1: 0.1 x 0.1 = M2 x 2 = 0.005 M. Beaker 2 = 0.00025 M"

**完整还原**（详见 §3.2）：
- Beaker 1：$M_2 = \dfrac{0.10 \times 0.1}{2.0} = 0.005$ M
- Beaker 2：$M_3 = \dfrac{0.005 \times 0.1}{2.0} = 2.5\times10^{-4}$ M
- HCl 与 NaOH 数值完全相同（原液浓度与操作相同）。

**答题要点**：必须写出 $V_2 = 0.1 + 1.9 = 2.0$ ml，**不是 1.9 ml**。

---

**【问题 2】Calculate the predicted pH of each of the solutions. How do these compare with your measured values?**
（计算每份溶液的预测 pH，并与实测值比较。）

**材料答案原文**：
> "_NaOH_ Beaker 1: [OH-] = NaOH = 0.005; pOH = -log[OH-] = -log 0.005 = 2.3. We are finding pH so: pOH + pH = 14; pH = 14 – 2.3 = **11.7**. Beaker 2: pH = **10.4**.
> _HCl_ Beaker 1: [H+] = [HCl] = 0.005; pH = -log[H+] = -log 0.005 = **2.3**. Beaker 2 – pH = **3.6**"

**完整还原**（含材料未展开的 Beaker 2 过程，详见 §3.3）：

| | 计算链 | 结果 |
| --- | --- | --- |
| NaOH B1 | $[\mathrm{OH^-}]=0.005 \to \mathrm{pOH}=2.30 \to \mathrm{pH}=14-2.30$ | **11.7** |
| NaOH B2 | $[\mathrm{OH^-}]=2.5\times10^{-4} \to \mathrm{pOH}=3.60 \to \mathrm{pH}=14-3.60$ | **10.4** |
| HCl B1 | $[\mathrm{H^+}]=0.005 \to \mathrm{pH}=-\log(0.005)$ | **2.3** |
| HCl B2 | $[\mathrm{H^+}]=2.5\times10^{-4} \to \mathrm{pH}=-\log(2.5\times10^{-4})$ | **3.6** |

**"How do these compare" 的标准答法**（材料未直接给文字，需自己组织）：
> 实测值（12、10、2、4）与预测值（11.7、10.4、2.3、3.6）**差异均在 0.4 个 pH 单位以内**。差异来自**万用指示剂试纸只能给出整数级的 pH 读数（分辨率约 ±0.5 单位）**，以及肉眼比色的主观性。**在试纸的精度范围内，实测与理论完全一致**，验证了 HCl 与 NaOH 均为强电解质、完全解离的假设。

---

**【问题 3】What causes the current indicator to glow, write the dissolution reactions?**
（是什么让电流指示器发光？写出溶解反应。）

**材料答案原文**：
> "HCl (aq) = H⁺ (aq) + Cl⁻ (aq)
> NaOH (aq) = Na⁺ (aq) + OH⁻ (aq)
> In wires, it is electrons that carry the current, but in solutions the current is carried by ions. NaOH and HCl strongly dissociate into ions in solution."

**规范化答案**：

$$\mathrm{HCl\,(aq)} \longrightarrow \mathrm{H^{+}\,(aq)} + \mathrm{Cl^{-}\,(aq)}$$
$$\mathrm{NaOH\,(aq)} \longrightarrow \mathrm{Na^{+}\,(aq)} + \mathrm{OH^{-}\,(aq)}$$

**解释三句话**：
1. HCl 与 NaOH 是**强电解质**，在水中**完全解离**成自由移动的离子；
2. **导线中由电子载流，溶液中由离子载流**——插入溶液的两根电极之间靠离子迁移形成闭合回路；
3. 有电流通过 ⇒ LED 发光；电流越大 ⇒ LED 越亮。

---

**【问题 4】What is the effect of the concentration of a basic or acidic solution on its conductivity and pH?**
（酸碱溶液的浓度对其电导率与 pH 有什么影响？）

**材料答案原文**：
> "The electrical conductance depends upon the **total concentration of the ions** (and hence pH). The most mobile ions are **H⁺ and OH⁻**. So the more acidic or basic the solution the greater the electrical conductivity will be."

**展开的完整答案**：
1. **对电导率**：电导率取决于**离子的总浓度**。浓度越高 → 单位体积载流子越多 → 电导率越大 → LED 越亮。实验中 0.005 M 亮、0.00025 M 暗，浓度差 20 倍。
2. **对 pH**：
   - 酸：浓度 ↑ → [H⁺] ↑ → pH ↓（更酸）；稀释 20 倍 → pH 上升 $\log 20 = 1.3$ 单位；
   - 碱：浓度 ↑ → [OH⁻] ↑ → pOH ↓ → pH ↑（更碱）；稀释 20 倍 → pH 下降 1.3 单位；
   - 无论酸碱，**稀释都使 pH 向 7 靠拢**。
3. **两者的联系**：因为 **H⁺ 与 OH⁻ 是所有离子中迁移率最高的**（Grotthuss 机制），所以**溶液越酸或越碱（pH 越偏离 7），电导率越高**。也就是说，在酸碱体系里，**pH 与电导率不是两个独立的量，而是同一件事（离子浓度）的两个侧面**。

---

## 5.2 实验二：滴定法测定海水中的氯化物含量

### 5.2.1 目的与预期学习成果 (Intended Learning Outcomes)

材料列出三条 ILO：

1. **Know what a titration experiment is and what it is used for.** —— 知道什么是滴定、滴定用来做什么。
2. **Be able to carry out a titration experiment using silver nitrate against seawater using an indicator solution (fluorescein).** —— 会用硝酸银对海水做滴定、用荧光素指示终点。
3. **Be able to use titration results to quantify the concentration of an analyte.** —— 会用滴定结果**定量**计算被测物浓度。

**总目标（材料引言）**：**用滴定法测定海水中氯化物的含量** ("determine the amount of chloride present in seawater using a titration")。

### 5.2.2 反应原理

$$\mathrm{AgNO_3\,(aq)} + \mathrm{NaCl\,(aq)} \rightleftharpoons \mathrm{NaNO_3\,(aq)} + \mathrm{AgCl\,(s)}\!\downarrow$$

净离子方程：$\mathrm{Ag^+ + Cl^- \to AgCl(s)}$，**计量比 1:1**。详见 §2.8。

**白色沉淀是什么？**（材料直接设问）—— **氯化银 (silver chloride, AgCl)**。

### 5.2.3 试剂与仪器

**仪器 (Apparatus)**：
- **滴定管 (burette, 约 10 ml)** —— 材料明确：**"this is your syringe used in the pH experiment"**（就是实验一那支注射器！体现微量化学的器材复用）
- 两个 50 ml 烧杯（**注意讲义前后不一致**：Apparatus 写 "Two 50 ml beakers"，但 Procedure 步骤 4 写 "add 2.5 ml of 'seawater' solution to a **10 ml** beaker"。**以实际取用体积 2.5 ml 判断，用小烧杯更合适**；这是讲义的排版遗留。）

**试剂 (Chemicals)**：
- **0.5 M 硝酸银 AgNO₃ 溶液** —— 滴定剂 (titrant)，已知浓度
- **"海水" (seawater) 溶液** —— 被测物 (analyte)，浓度未知（材料原文有拼写错误 "Seawater solutio9n"）
- **0.2 M 荧光素 (fluorescein) 指示剂** —— 一种有机染料 (an organic dye)

**安全提示（补充）**：AgNO₃ 具腐蚀性，会**把皮肤染成难以洗去的黑褐色**（Ag⁺ 被还原为银单质），且对水生生物有毒——**这正是材料强调微量操作、限制用量的直接原因**。含银废液应回收，不可直接倒入下水道。

### 5.2.4 详细操作步骤（材料 9 步 + 要点解释）

| 步骤 | 材料原文操作 | 要点 / 为什么 |
| --- | --- | --- |
| **1** | 用蒸馏水校准滴定管（注射器）的**滴径**，数出 0.5 ml 对应的滴数；**或直接沿用 pH 实验的校准结果** | 材料答案：**0.04 ml/drop**。终点前的一滴决定了最终精度 |
| **2** | 校准完毕后，**把管内残留的蒸馏水排空** | ⚠️ 残水会稀释 AgNO₃ → 使实际浓度低于 0.5 M → **系统性高估**所需体积 → 高估 Cl⁻。**规范做法是用少量 AgNO₃ 润洗 (rinse) 两次再装液** |
| **3** | 装入**不超过 3 ml** 的 AgNO₃ 溶液 | 微量化学原则：只装够用的量，减少银废液 |
| **4** | 用**另一支**注射器取 **2.5 ml "海水"** 加入小烧杯 | ⚠️ **必须用另一支**，避免 Ag⁺ 与 Cl⁻ 在注射器里就提前沉淀 |
| **5** | 加 **2–3 滴荧光素指示剂** | 指示剂只需微量；加多了自身颜色会掩盖终点变色，也会消耗少量 Ag⁺ |
| **6** | 开始滴定。**可以先直接加约 1 ml，然后改为数滴**；**接近等当点时必须放慢**；**每次只加少量并勤旋摇 (swirl the flask regularly)** | 这是滴定的标准节奏：**先快后慢**。前段快是为了省时间，后段慢是为了不冲过终点。旋摇是为了让 Ag⁺ 与 Cl⁻ 充分接触反应完全，同时**维持 AgCl 胶粒分散、保证吸附指示剂能显色** |
| **7** | 观察到**沉淀生成并聚沉** ("a precipitate forms and coagulates") | 白色 AgCl 逐渐由乳浊变为絮状聚集——**这是反应正在进行的标志，不是终点** |
| **8** | **终点标志：沉淀上突然出现颜色变化** ("a sudden development of colour change **on the precipitate**") | ⚠️ **看沉淀，不看溶液！** Fajans 吸附指示剂的变色发生在固体表面：白色 → **粉红/玫瑰红**。机理见 §2.8 |
| **9** | **记录滴定剂体积** | 这是唯一的定量读数，务必记准（用"起始读数 − 终止读数"或直接数滴数换算） |

**体积读数的两种方式**：
- **刻度法**：读注射器刻度，分辨率 ±0.1 ml；
- **数滴法**：滴数 × 0.04 ml/drop，分辨率 ±0.04 ml。**接近终点时必须用数滴法。**
- 实际做法通常是混合：先按刻度推 1 ml，之后全程数滴。例：1 ml + 42.5 滴 × 0.04 = 1 + 1.7 = **2.7 ml**。

**规范滴定的补充要求（材料未写，但属通用good practice）**：
- 做**至少 3 次平行滴定 (replicate titrations)**，取一致结果（相差 < 0.1 ml）的平均值；
- 第一次可做**粗滴 (rough titration)** 摸清大致体积，后面几次在接近该体积时才开始逐滴加；
- 记录**起始与终止读数**，而不只是差值。

### 5.2.5 数据记录表（建议格式）

| | 粗滴 Rough | 精滴 1 | 精滴 2 | 精滴 3 |
| --- | --- | --- | --- | --- |
| 终止读数 (ml) | | | | |
| 起始读数 (ml) | | | | |
| **用量 (titre, ml)** | | | | |
| 是否采用 (concordant?) | ✗ | | | |

**平均滴定体积 $\bar{V}$ = 采用值的平均**。材料算例用 **$V = 2.7$ ml**。

### 5.2.6 完整计算示例（材料标准答案的逐步还原）

**已知**：
- $M(\mathrm{AgNO_3}) = 0.5$ mol/L
- $V(\mathrm{AgNO_3}) = 2.7$ ml（示例值）
- $V_{\text{sample}} = 2.5$ ml
- $A_r(\mathrm{Cl}) = 35.453$ g/mol
- 文献值：天然海水 Cl ≈ **19.4 g/L**

---

**Step 1：AgNO₃ 的物质的量**

$$n(\mathrm{AgNO_3}) = M \times V = 0.5\ \mathrm{mol/L} \times \frac{2.7}{1000}\ \mathrm{L} = 1.35\times10^{-3}\ \mathrm{mol}$$

> 材料原文："n (moles) = M (moles/L) x V (L)。So if the volume of silver nitrate used is e.g. 2.7 ml then n = 0.5 x (2.7/1000) = 1.35 x 10⁻³ moles"

---

**Step 2：由计量比得 Cl⁻ 的物质的量**

AgNO₃ 完全解离 ⇒ $n(\mathrm{Ag^+}) = 1.35\times10^{-3}$ mol
反应 $\mathrm{Ag^+ + Cl^- \to AgCl}$，1:1 ⇒

$$n(\mathrm{Cl^-}) = n(\mathrm{Ag^+}) = 1.35\times10^{-3}\ \mathrm{mol}$$

> 材料原文："According to the reaction equation: moles Ag⁺ = moles Cl⁻ = 1.35 x 10⁻³ moles"

**每 1 ml 海水中**：$1.35\times10^{-3}/2.5 = 5.4\times10^{-4}$ mol/ml

---

**Step 3：Cl⁻ 的摩尔浓度**

$$M(\mathrm{Cl^-}) = \frac{n}{V_{\text{sample}}} = \frac{1.35\times10^{-3}\ \mathrm{mol}}{2.5\times10^{-3}\ \mathrm{L}} = 0.54\ \mathrm{mol/L}$$

> 材料原文："The concentration of Cl⁻ in 2.5 ml of 'seawater' is M (mol/L) = n (moles) **x** V(L) = 1.35 x 10⁻³ /(2.5/1000) = 0.54 mol/L"
> ⚠️ **注意公式里的 "x" 是笔误，应为 "÷"**；代入的算式本身是正确的除法。

---

**Step 4：换算成 g/L**

$$\rho(\mathrm{Cl^-}) = 0.54\ \mathrm{mol/L} \times 35.453\ \mathrm{g/mol} = 19.1\ \mathrm{g/L}$$

> 材料原文："Convert moles to grams of Cl⁻ by multiplying by the atomic mass of Cl = 35.453. This gives 0.54 x 35.453 = 19.1 g/L similar to the value looked up."

---

**Step 5：与文献值比较**

| | 值 |
| --- | --- |
| 实验测得 | **19.1 g/L** |
| 文献值（天然海水） | **19.4 g/L** |
| 绝对偏差 | −0.3 g/L |
| **相对偏差** | **−1.3 %** |

**判读**：吻合良好。1.3% 的偏差与"一滴 = 0.04 ml，占 2.7 ml 的 1.5%"的仪器分辨率极限同量级，**说明本次滴定的误差主要来自体积读数的随机误差，没有明显的系统误差（如滴定管未润洗、终点判断偏早/偏晚）**。

---

**Step 6（补充）：换算成盐度**

$$\mathrm{Cl}\ (\mathrm{g/kg}) = \frac{19.1}{1.025} = 18.6‰ \quad\Longrightarrow\quad S = 1.80655 \times 18.6 = 33.7$$

落在真实海水盐度 33–37 的正常范围内 ✓。

---

### 5.2.7 材料的重要补充：容量法 vs 重量法

材料在答案最后给了一段极有价值的方法论说明（原文）：

> "Note that in our experiment AgCl is a **solid precipitate**. We could have **filtered, dried and then weighed** the mass of this precipitate as another means to determine the mass of chloride. This kind of experiment, based on **mass of precipitate**, is known as a **gravimetric analysis**. A careful analyst would **obtain the same result** using either **volumetric** or **gravimetric** methods."

**两种经典定量分析法的对比（必考对比）**：

| | **容量分析 (volumetric analysis)** | **重量分析 (gravimetric analysis)** |
| --- | --- | --- |
| **测量的量** | **滴定剂的体积 (volume)** | **沉淀的质量 (mass)** |
| **本实验的实现** | 记录 AgNO₃ 用了 2.7 ml | 把 AgCl 沉淀**过滤 (filter) → 干燥 (dry) → 称重 (weigh)** |
| **所需仪器** | 滴定管、指示剂 | 分析天平、过滤装置、烘箱/干燥器 |
| **速度** | 快（几分钟一次） | 慢（干燥恒重需数小时） |
| **精度** | 好（0.1–0.5%） | **更高**（可达 0.1% 以下），因为质量比体积更容易测准 |
| **关键误差源** | 终点判断、体积读数 | 沉淀溶解损失、洗涤不净、干燥不彻底、共沉淀 |
| **结论** | **两法结果应一致**——"A careful analyst would obtain the same result" | |

**重量法的验算示例（补充，把本实验的数字走一遍）**：
若把 AgCl 全部收集烘干称重，理论质量为

$$m(\mathrm{AgCl}) = n \times M_r(\mathrm{AgCl}) = 1.35\times10^{-3}\ \mathrm{mol} \times 143.32\ \mathrm{g/mol} = 0.1935\ \mathrm{g}$$

再由 AgCl 中 Cl 的质量分数反推：

$$m(\mathrm{Cl}) = 0.1935 \times \frac{35.453}{143.32} = 0.0479\ \mathrm{g}$$

$$\rho(\mathrm{Cl^-}) = \frac{0.0479\ \mathrm{g}}{2.5\times10^{-3}\ \mathrm{L}} = 19.2\ \mathrm{g/L}$$

**与容量法的 19.1 g/L 一致 ✓**——这正是材料那句话的量化证明。（$M_r(\mathrm{AgCl}) = 107.87 + 35.45 = 143.32$ g/mol）

### 5.2.8 逐题梳理（材料 Results and calculations）

| 问题 | 材料答案 | 补充说明 |
| --- | --- | --- |
| **Look-up how much chloride there is in seawater (g/L)** | **约 19.4 g/L** | 对应盐度 35 的标准海水；氯度 19.374 g/kg × 1.025 kg/L ≈ 19.9 g/L（不同教科书取值略有差异，19.4 是常见的"每升海水中氯离子克数"引用值） |
| **What is the white precipitate?** | **氯化银 (silver chloride, AgCl)** | $K_{sp} = 1.8\times10^{-10}$，难溶、白色、见光变紫灰 |
| **Calculate the number of moles of silver nitrate used** | $n = M \times V = 0.5 \times (2.7/1000) = 1.35\times10^{-3}$ mol | 注意 ml → L 的换算 |
| **Find moles of Cl⁻ in 1 ml, then in g/L; comment** | $n(\mathrm{Cl^-}) = 1.35\times10^{-3}$ mol（在 2.5 ml 中）→ 0.54 mol/L → **19.1 g/L**，**与查得值相近** | 每 1 ml：$5.4\times10^{-4}$ mol；相对偏差 −1.3% |
| **（附注）** | 本实验也可改用**重量分析 (gravimetric analysis)**：过滤、干燥、称量 AgCl；**仔细的分析者用两种方法应得到相同结果** | 见 §5.2.7 |

---

## 六、易错点 / 重点难点

### 6.1 操作层面的坑

**【电路部分】**

| 坑 | 后果 | 正确做法 |
| --- | --- | --- |
| **不接限流电阻，LED 直连 9 V 电池** | LED 发热、几秒到几分钟后**烧毁 (burn-out)**（材料明确警告 "don't try this"） | 必须串联 ≥ 250 Ω 的电阻 |
| **把 20 mA 直接当 20 代入欧姆定律** | 算出 R = 0.25 Ω，等于没有电阻 | **先换算 20 mA = 0.02 A** |
| **LED 装反（短脚接了正极）** | LED **不亮但不损坏** | 长脚（阳极）接红线(+)；不亮先检查极性 |
| **不做"两电极互碰"自检就下溶液** | 把电路故障误判成"溶液不导电"，得到全盘错误的结论 | **每次实验开始前必做短接自检** |
| **色环读反方向** | 阻值算错（如 1000 Ω 读成 21 Ω） | 容差环（金/银）与前面有较宽间隙，把它放右边；不确定就用在线计算器 |

**【稀释与移液部分】**

| 坑 | 后果 | 正确做法 |
| --- | --- | --- |
| **用自来水代替去离子水稀释** | 自来水背景电导 ~500 µS/cm，完全淹没 0.00025 M 溶液的 ~110 µS/cm 信号 | **必须用 de-ionised water** |
| **注射器取完 NaOH 不冲洗就量水** | 残留碱带入，实际浓度偏高 | **每次转换液体都冲洗（材料的步骤 3、7 就是干这个的）** |
| **不旋摇混匀** | 溶液分层/局部浓度不均，测得的 pH 与电导随电极位置变化 | **每次稀释后必须 swirl** |
| **电极测完 Beaker 1 不擦就测 Beaker 2** | 高浓度残液污染稀溶液 → 稀溶液"假亮" → 得不出浓度效应 | **wipe the electrodes clean（材料步骤 10 明写）** |
| **注射器里有气泡** | 实际取液量小于刻度值 | 取液后垂直排气泡再调刻度 |
| **照抄 0.04 ml/drop 而不自己校准** | 每支注射器滴径不同，材料明说 "this may vary a little" | **自己数 3 次取平均** |

**【滴定部分】**

| 坑 | 后果 | 正确做法 |
| --- | --- | --- |
| **终点过冲 (overshooting the endpoint)** | 多加的每一滴都被算成 Cl⁻ → **系统性高估**氯度。一滴 0.04 ml 就是 1.5% 的误差 | 接近终点时**逐滴加、加一滴摇一摇看一次**；材料强调 "you will need to **slow down** the rate of titration as you approach the equivalence point" |
| **盯着上清液看颜色** | Fajans 法的变色**发生在沉淀表面**，看溶液会永远等不到明显变色，导致大幅过冲 | **盯着沉淀 (colour change on the precipitate)** |
| **滴定管（注射器）内残留蒸馏水未排净** | 稀释了 AgNO₃ → 实际浓度 < 0.5 M → 需要更多体积 → **高估** Cl⁻ | 材料步骤 2 明确要求排空；更规范的做法是用 AgNO₃ **润洗 (rinse)** 两次 |
| **滴定剂与样品用同一支注射器** | 交叉污染，在注射器内就生成 AgCl | 材料步骤 4 明写 "using **another** syringe" |
| **指示剂加太多** | 荧光素本身黄绿色会掩盖粉红终点；且会消耗少量 Ag⁺ | **只加 2–3 滴** |
| **不摇动 / 摇动不足** | Ag⁺ 与 Cl⁻ 未充分反应，终点提前出现（假终点）；胶粒过度聚沉，表面积骤减，终点变钝 | **swirl the flask regularly（材料步骤 6 明写）** |
| **只做一次滴定就下结论** | 无法评估重复性，单次结果可能含粗差 | 做 3 次平行，取一致值平均 |
| **长时间在强光下滴定** | AgCl 光解成灰紫色，干扰粉红色终点的判断 | 快速完成，避免直射光 |

**【读数部分】**

| 坑 | 后果 | 正确做法 |
| --- | --- | --- |
| **视差 (parallax error)** | 斜着看刻度会系统性读高或读低 | **视线与液面/刻度**保持水平；读**弯月面 (meniscus) 的最低点**（对水溶液） |
| **用试纸读出小数 pH** | 万用指示剂试纸分辨率只有 ±0.5–1 单位，报 "pH = 3.62" 是虚假精度 | **试纸只报整数**；要小数精度必须用 **pH meter** |
| **试纸浸太久或整片泡进溶液** | 指示剂被洗脱、颜色失真；也污染样品 | **用玻棒蘸一滴点在试纸上**，或快速蘸取后立刻比色（30 s 内） |

### 6.2 计算层面的坑

| 坑 | 说明 | 防范 |
| --- | --- | --- |
| **$M_1V_1=M_2V_2$ 中 $V_2$ 用错** | 用"加入的水量 1.9 ml"而不是"总体积 2.0 ml"，结果偏高 5% | **$V_2$ = 取用量 + 加入量 = 0.1 + 1.9 = 2.0 ml** |
| **ml 忘记换成 L** | $n = M \times V$ 中 $V$ 必须是 L，用 2.7 而非 0.0027 会**大 1000 倍** | 每一步都写单位，做**量纲检查**：mol/L × L = mol ✓ |
| **$M = n \times V$ 还是 $n \div V$** | 材料答案就把它写错成乘号 | 记 **"浓度 = 量 ÷ 体积"**；量纲：mol ÷ L = mol/L ✓ |
| **计量比默认 1:1** | 本实验恰好是 1:1，但换成 $\mathrm{2Ag^+ + CrO_4^{2-}}$ 或 $\mathrm{H_2SO_4 + 2NaOH}$ 就不是 | **每次都先写平衡方程，从系数读比例** |
| **pOH 与 pH 混用** | 算碱时算出 pOH = 2.3 就直接当 pH 报出（应是 11.7） | 算碱**必须多走一步** $\mathrm{pH} = 14 - \mathrm{pOH}$ |
| **"pH + pOH = 14" 到处套** | 只在 **25 °C** 成立 | 非 25 °C 要用当时的 p$K_w$ |
| **g/L 与 ‰ (g/kg) 混为一谈** | 海水密度 1.025 kg/L，直接混用引入 2.5% 误差 | **换算盐度前先除以密度** |
| **有效数字 (significant figures)** | 0.5 M 严格说只有 1 位有效数字；但报出 19.1 g/L（3 位）。实践中标准溶液浓度视为精确值（0.500 M），最终有效数字由**体积读数**限定 | **结果的有效数字跟随最不精确的那个测量值**；本例 2.7 ml 是 2 位有效数字，因此严格报 **19 g/L**，报 19.1 属于多保留一位的常见惯例 |
| **对数速算出错** | $-\log(5\times10^{-3})$ 算成 3.0 或 2.0 | 记 $\log 2 = 0.301$、$\log 5 = 0.699$；$-\log(5\times10^{-3}) = 3 - 0.699 = 2.30$ |
| **稀释 20 倍对应的 ΔpH** | 误以为是 2 个单位 | $\Delta\mathrm{pH} = \log_{10}(DF) = \log 20 = 1.30$ |

### 6.3 概念层面的重点难点

1. **equivalence point ≠ end-point**：前者是理论化学计量点，后者是实验观察点，两者之差叫滴定误差。考试问 "define" 时必须分开答。
2. **Fajans 法的变色位置**：**在沉淀表面**，不在溶液中。这是与 Mohr 法（溶液中出现砖红色沉淀）、Volhard 法（溶液变血红色）最大的操作差异。
3. **本实验用的是 Fajans 法（荧光素吸附指示剂），不是 Mohr 法（铬酸钾）**。三种银量法要能列表区分。
4. **导线 vs 溶液的载流子不同**（电子 vs 离子），且**温度效应方向相反**（金属电阻随温升增大，电解质电导随温升增大）。
5. **为什么 H⁺/OH⁻ 特别导电**：Grotthuss 质子接力机制，不是普通的实体离子迁移。
6. **为什么测一个 Cl⁻ 能得到整个盐度**：恒定比例定律 (Principle of Constant Proportions)，Cl⁻ 占海水盐分 55% 且比例恒定。
7. **为什么要做系列稀释而不是一次稀释**：单次 400 倍稀释需要量取 0.005 ml，远低于注射器分辨率（一滴 0.04 ml）；两级 20 倍每级都在可测范围内。
8. **volumetric vs gravimetric**：测体积 vs 测质量，两者应给出相同结果；重量法更准但更慢。

### 6.4 关于本周材料本身的已知错漏（复习时不要被带偏）

| 位置 | 材料原文 | 应为 |
| --- | --- | --- |
| Expt1 页眉 | "Semester 2" | 本文件归档在 **Michaelmas Term Week 10** |
| Expt1 步骤 12 | "repeat steps **1 to 10**" | 应含步骤 11（测 pH），否则 HCl 组无 pH 数据 |
| Expt1 问题 3 | 用 "=" 写解离式 | 强电解质应写 "→" |
| Expt2 试剂 | "Seawater **solutio9n**" | solution（打字错误） |
| Expt2 仪器 vs 步骤 4 | Apparatus 写 "Two **50 ml** beakers"，步骤 4 写 "a **10 ml** beaker" | 取 2.5 ml 样品，用小烧杯更合理 |
| Expt2 计算 | "M (mol/L) = n (moles) **x** V(L)" | **M = n ÷ V**（后面的代入是对的除法） |
| Expt1 色环 | "640 (**4-band** - blue-yellow-black-black)" | blue(6)-yellow(4)-black(0)-black(×1) 是 **5 环读法**才得 640 Ω；按材料给的 640 Ω 记即可 |

---

## 七、本周术语表

### 7.1 电学与仪器

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| Ohm's Law | 欧姆定律 | $V = IR$；本周用其变形 $R = (V_b - V_f)/I$ 算限流电阻 |
| voltage / potential difference | 电压 / 电位差 | 推动电荷流动的"压力"，单位 V |
| current | 电流 | 单位时间通过的电荷量，单位 A；1 mA = 10⁻³ A |
| resistance | 电阻 | 阻碍电流的能力，单位 Ω |
| resistor | 电阻器 | 电路元件；本实验用作**限流电阻**，无极性、位置随意 |
| current-limiting resistor | 限流电阻 | 串联在 LED 前，把电流压到额定值以下，防止 LED 烧毁 |
| LED (light emitting diode) | 发光二极管 | 有极性的发光元件；长脚阳极接正、短脚阴极接负 |
| anode / cathode | 阳极 / 阴极 | LED 的正极（长脚）/ 负极（短脚）；接反则不亮但不损坏 |
| forward voltage drop ($V_f$) | 正向压降 | LED 导通后两端的固定电压降，本实验 4 V，须查规格书 |
| maximum current rating | 最大额定电流 | LED 能承受的电流上限，本实验 20 mA |
| resistor colour code | 电阻色环 | 用 4–6 条色环编码阻值；容差环与前面有较宽间隙，据此定方向 |
| snap-on battery cap | 电池扣 | 9 V 方块电池的卡扣式接头 |
| electrode | 电极 | 插入溶液的两根裸线，让溶液成为电路的一部分 |
| circuit diagram | 电路图 | 接线前先画，避免接错烧元件 |
| current indicator (device) | 电流指示器 | 本实验自制的 LED 电路，靠亮度**半定量**指示溶液电导率 |

### 7.2 溶液化学与 pH

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| conductivity ($\kappa$) | 电导率 | 溶液导电能力的本征量，单位 µS/cm 或 mS/cm |
| conductance ($G$) | 电导 | 电阻的倒数 $G = 1/R$，单位 S（西门子） |
| cell constant ($K_{cell}$) | 电极常数 | 电极几何因子 $L/A$，把电导换算成电导率 |
| molar conductivity ($\Lambda_m$) | 摩尔电导率 | $\kappa/c$，单位 S·cm²·mol⁻¹ |
| limiting molar ionic conductivity ($\lambda^\circ$) | 极限摩尔离子电导率 | 无限稀释时单个离子的导电贡献；H⁺ 349.8 最大，OH⁻ 198.0 次之 |
| ionic mobility | 离子迁移率 | 单位电场下离子的迁移速度；决定该离子的导电效率 |
| Grotthuss mechanism | 格罗特斯机制（质子接力） | H⁺/OH⁻ 沿氢键网络"接力传递"而非整体位移，故迁移率异常高 |
| Kohlrausch's law | 科尔劳施定律 | $\Lambda_m = \Lambda_m^\circ - K\sqrt{c}$；及离子独立迁移定律 $\Lambda^\circ = \lambda_+^\circ + \lambda_-^\circ$ |
| electrolyte | 电解质 | 溶于水后解离成离子、能导电的物质 |
| strong electrolyte | 强电解质 | 在水中**完全解离**（HCl、NaOH、NaCl） |
| weak electrolyte | 弱电解质 | 部分解离，存在解离平衡（醋酸、氨水） |
| dissociation | 解离 | 化合物在溶剂中拆成离子的过程 |
| ion / cation / anion | 离子 / 阳离子 / 阴离子 | 溶液中的载流子；阳离子带正电、阴离子带负电 |
| spectator ion | 旁观离子 | 反应前后不变的离子（本实验的 Na⁺、NO₃⁻） |
| ionic strength ($I$) | 离子强度 | $I = \frac12\sum c_i z_i^2$，描述溶液整体电荷环境强度 |
| pH | 酸碱度 | $-\log_{10}[\mathrm{H^+}]$（严格为活度） |
| pOH | 氢氧根指数 | $-\log_{10}[\mathrm{OH^-}]$；25 °C 时 pH + pOH = 14 |
| $K_w$ / ionic product of water | 水的离子积 | $[\mathrm{H^+}][\mathrm{OH^-}] = 1.0\times10^{-14}$（25 °C） |
| autoionisation of water | 水的自解离 | $\mathrm{2H_2O \rightleftharpoons H_3O^+ + OH^-}$ |
| universal indicator (paper) | 万用指示剂（试纸） | 多种指示剂混合，全 pH 范围显色；分辨率仅 ±0.5–1 单位 |
| pH meter | pH 计 | 玻璃电极电位法测 pH，分辨率 0.01；需用缓冲液（4.01/7.00/10.01）**两点或三点校准** |
| buffer solution | 缓冲溶液 | pH 稳定的标准溶液，用于校准 pH 计 |
| temperature compensation (ATC) | 温度补偿 | 电导率随温度约 **2 %/°C** 变化，仪器自动折算到 **25 °C 参考温度**；pH 计则补偿 Nernst 斜率（25 °C 时 59.16 mV/pH） |
| de-ionised water | 去离子水 | 去除全部离子的水（~0.055 µS/cm），本实验必须用它稀释与冲洗 |
| dilution | 稀释 | 加溶剂降低浓度，溶质物质的量不变：$M_1V_1 = M_2V_2$ |
| serial dilution | 系列稀释 | 连续多级稀释，$M_n = M_0/DF^n$；用于跨越大浓度跨度 |
| dilution factor (DF) | 稀释因子 | $V_2/V_1$；本实验每级 20 倍 |
| molarity ($M$) | 摩尔浓度 | mol/L；本课程的主要浓度单位 |
| aliquot | 移取的定量份 | 用移液器/注射器取出的固定体积样品 |

### 7.3 滴定与定量分析

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| titration | 滴定 | 用已知浓度溶液逐步加入待测液，由消耗体积定量的方法 |
| volumetric determination / analysis | 容量分析 | 靠**测体积**定量的分析方法（滴定属此类） |
| gravimetric analysis | 重量分析 | 靠**称沉淀质量**定量；更准但更慢，与容量法应得相同结果 |
| titrant | 滴定剂 / 标准溶液 | 已知浓度、从滴定管加入的溶液（本实验 0.5 M AgNO₃） |
| analyte | 被测物 / 待测液 | 浓度未知、被滴定的溶液（本实验 2.5 ml "海水"） |
| burette | 滴定管 | 精确控制并读取加入体积的器具；本实验用 10 ml 注射器代替 |
| equivalence point | 等当点 / 化学计量点 | 滴定剂与被测物**恰好**按计量比反应完的**理论**时刻 |
| end-point | 终点 | **实际观察到**指示剂变化的时刻 |
| titration error | 滴定误差 | end-point 与 equivalence point 之差 |
| indicator | 指示剂 | 提示反应完成的物质（颜色、沉淀、电导、pH 变化等） |
| fluorescein | 荧光素 | 有机染料，本实验用作**吸附指示剂**，终点时沉淀由白变粉红 |
| adsorption indicator | 吸附指示剂 | 靠被沉淀表面吸附而变色的指示剂（荧光素） |
| Fajans method | 法扬斯法 | **本实验所用**——银量法之一，用吸附指示剂（荧光素），终点看沉淀变粉红 |
| Mohr method | 莫尔法 | 银量法之一，用 K₂CrO₄ 指示剂，终点出现砖红色 Ag₂CrO₄ 沉淀，pH 6.5–10.5 |
| Volhard method | 佛尔哈德法 | 银量法之一，**返滴定**，Fe³⁺ 指示，终点溶液变血红色 [FeSCN]²⁺，酸性介质 |
| argentometric / precipitation titration | 银量法 / 沉淀滴定 | 以生成难溶银盐为基础的滴定 |
| back-titration | 返滴定 | 先加过量试剂，再滴定剩余量；Volhard 法所用 |
| precipitate | 沉淀 | 反应生成的不溶固体（本实验白色 AgCl） |
| coagulate | 聚沉 / 凝聚 | 胶体颗粒聚集变大的过程；材料明写滴定中会观察到 |
| colloid | 胶体 | 细分散的固体颗粒；AgCl 初生成时呈胶态，表面吸附离子 |
| solubility product ($K_{sp}$) | 溶度积 | 难溶盐的溶解平衡常数；AgCl 为 $1.8\times10^{-10}$ |
| stoichiometry | 化学计量（关系） | 由配平方程读出的物质的量之比；本实验 Ag⁺ : Cl⁻ = 1 : 1 |
| net ionic equation | 净离子方程式 | 去掉旁观离子后的方程：$\mathrm{Ag^+ + Cl^- \to AgCl(s)}$ |
| concordant titres | 一致的滴定读数 | 平行滴定间相差 < 0.1 ml 的结果，可取平均 |
| rough titration | 粗滴 | 第一次快速滴定，用于摸清大致终点体积 |
| relative atomic mass ($A_r$) | 相对原子质量 | Cl = 35.453 g/mol，用于 mol → g 换算 |
| microchemistry | 微量化学 | 用极小试剂量完成分析，降低成本与环境影响 |
| green chemistry | 绿色化学 | 以减少污染为目标的化学实践取向 |

### 7.4 海洋化学

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| seawater | 海水 | 本实验用引号 "seawater"，是人工配制的模拟海水 |
| chloride | 氯化物 / 氯离子 | Cl⁻，海水中含量最高的阴离子，天然海水约 19.4 g/L |
| chlorinity (Cl‰) | 氯度 | 海水中卤素总量的"等效氯"表示，单位 g/kg；历史上就由银量滴定定义 |
| salinity (S) | 盐度 | 海水中溶解盐总量；现代 PSS-78 定义为无量纲，标准海水 S = 35 |
| PSU (Practical Salinity Unit) | 实用盐度单位 | 盐度的习惯写法（严格说盐度无量纲） |
| PSS-78 (Practical Salinity Scale 1978) | 1978 实用盐度标度 | 用**电导率比** $K_{15}$ 定义盐度，取代滴定法 |
| TEOS-10 / Absolute Salinity ($S_A$) | 2010 海水热力学方程 / 绝对盐度 | 最新标准，盐度单位真正是 g/kg，校正区域成分差异 |
| Principle of Constant Proportions | 恒定比例定律 | 海水主要离子的相对比例处处恒定，故测一个 Cl⁻ 即可推全盐度 |
| Knudsen equation | 克努森公式 | $S = 0.030 + 1.8050\,\mathrm{Cl}$（1902 年版） |
| UNESCO conversion | UNESCO 换算式 | $S = 1.80655 \times \mathrm{Cl}$（1969 年版，现行） |
| CTD (Conductivity–Temperature–Depth) | 温盐深仪 | 海洋学标准仪器，测电导率与温度以推算盐度和密度 |

---

## 附：本周一页速记 (One-page recall)

**实验一**
- $R_{\min} = (V_b - V_f)/I = (9-4)/0.02 = 250\ \Omega$；实际用 640 Ω (7.8 mA) 或 1000 Ω (5 mA)
- LED 长脚 = 阳极 = 接红线(+)；接反不亮但不坏；电阻无极性、位置随意
- 滴径校准：0.5 ml / 12.5 滴 = **0.04 ml/drop**
- 稀释：$M_1V_1 = M_2V_2$，每级 DF = 20：**0.10 → 0.005 → 0.00025 M**
- pH：HCl **2.3 / 3.6**；NaOH **11.7 / 10.4**（= 14 − pOH）；实测试纸 2/4/12/10
- 结论：**浓度↑ → 离子↑ → 电导率↑ → LED 亮**；**H⁺、OH⁻ 迁移率最高（Grotthuss）**，故越酸越碱越导电

**实验二**
- $\mathrm{AgNO_3 + NaCl \rightleftharpoons NaNO_3 + AgCl(s)}$；净离子式 $\mathrm{Ag^+ + Cl^- \to AgCl}$，**1:1**
- 白色沉淀 = **AgCl**；指示剂 = **荧光素（Fajans 吸附指示剂）**；**终点：沉淀由白突变粉红**
- $n = MV = 0.5 \times 0.0027 = 1.35\times10^{-3}$ mol → $n(\mathrm{Cl^-})$ 同 → $M = n/V = 1.35\times10^{-3}/0.0025 = 0.54$ M
- $\rho = 0.54 \times 35.453 = $ **19.1 g/L**，文献 19.4 g/L，偏差 **−1.3 %** ✓
- 盐度：$19.1/1.025 = 18.6‰$ → $S = 1.80655 \times 18.6 =$ **33.7**
- 容量法 (volumetric) ↔ 重量法 (gravimetric)：**测体积 vs 测质量，结果应一致**
