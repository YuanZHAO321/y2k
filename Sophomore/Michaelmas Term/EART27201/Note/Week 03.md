# EART27201 Sedimentary Rocks and Fossils — Week 03 学习笔记

## 一、本周主题

**本周主题（由材料判定）：床型配置（一）—— 单向水流如何与砂质床面相互作用（Bed Configurations, Part 1）。**

判定依据：本周讲义首页标题即为 `Class 3: Bed Configurations (Part 1)`（John Southard, Emeritus MIT），课堂提纲写明两条 —— "What drives erosion and deposition?"（什么驱动侵蚀与沉积）与 "Describe the bedforms that develop in fine–coarse sands under unidirectional flows"（描述细砂至粗砂在单向流下发育的床型）。实习 handout 标题为 `Class 3: How do water flows interact with a bed made of sand?`，用水槽（flume）实验实地走一遍床型序列。二者主题完全对齐。

具体覆盖的内容可以拆成三块：

1. **侵蚀与沉积的真正控制因素** —— 用沉积物质量平衡（Exner 方程）取代"快流侵蚀、慢流沉积"的直觉，以及湍流造成的边界剪应力时空变化。
2. **颗粒起动与搬运方式** —— 临界剪应力 τ_cr、改良 Hjulström 图、接触载荷 / 跃移 / 间歇悬移三种搬运模式。
3. **床型的概念体系与前两种床型** —— bed configuration / bedform / sedimentary structure 三级术语的区分，床型的成因定义与地质用途，以及单向流床型序列的头两位成员：**下部平坦床（lower plane bed）** 与 **流水波痕（current ripples）**。

讲义在末页明确说 "We will conclude our experiment next week"，即沙丘（dunes）到逆行沙丘（antidunes）留给 Class 4。**所以第 3 周讲义只讲到波痕为止，而第 3 周实习却把整条序列一次走完** —— 这正是同一份实习 handout 被第 3、4 两周共用的原因：第 3 周先动手看现象、做记录，第 4 周补上后半段理论再回头解释。

**与前两周的衔接：**

- **Week 1**（`Lecture 1`：Nature, description and classification of sediments and sedimentary rocks）建立了沉积物/沉积岩的物质描述框架 —— 颗粒、基质、胶结物、孔隙度。
- **Week 2**（`Class 2 Physics of Sedimentation`）是本周的直接前置：流体的密度与黏度、明渠流、层流与湍流、**流动雷诺数 Re**、垂向流速剖面与无滑移条件（no-slip condition）、湍流的基本结构、**边界剪应力 τ₀**、单个颗粒的受力分析；实习做的是 Stokes 定律与颗粒沉降。
- **Week 3 做的事，是把 Week 2 的"单颗粒受力"升级为"整个床面的集体响应"**：一粒砂在什么条件下起动（τ₀ ≥ τ_cr，直接沿用 Week 2 的剪应力概念）→ 成千上万粒砂被搬运后如何自组织成有规则的地形（床型）→ 床型迁移又如何在岩石中留下沉积构造（如交错层理）。Week 2 学的 Re 公式和 τ₀ 概念，在本周实习里直接被拿来做计算题。

**在全课骨架中的位置：** 本课的骨架是「岩石材料学 → 沉积构造 → 化石与生物地层」。本周属于**第二根柱子（物理沉积构造）的成因源头**：先讲清床型是怎么被流体造出来的，后面才能反过来由岩石中的构造去反推古水流条件。讲义把这条反推路线写成了明确的三步法（见"二、核心概念"第 5 条），这三步法是整门课解释沉积构造的通用范式。

> ⚠️ **重要提醒（与课程大纲不符）**：课程大纲（`(EART27201) Sedimentary Rocks and Fossils.md`）的 Syllabus 一节把 W3 列为"碳酸盐岩（Carbonate sedimentary rocks）"、把"物理沉积构造 + 水槽实验"列为 W10。**实际交付的 Class 3 讲义与实习均为床型与水槽实验，与大纲不符。** 已记入文末勘误表。复习时请**以讲义与实习 handout 的实际内容为准，不要用大纲的周次表来定位主题**。

---

## 二、核心概念

### 1. 侵蚀与沉积由什么控制？—— 对"流速决定论"的否定

讲义先立靶子再打靶：

- **常见观点（讲义称之为 "One viewpoint"）**：侵蚀与沉积由**流速**控制；由此推论"高速流侵蚀、低速流沉积"。这正是 **Hjulström 图**被常规使用时给人的印象。
- **讲义的判决**：`We know by studying sedimentary structure in the flume and stratigraphic record this is not true.`（我们通过水槽实验与地层记录已经知道这不成立。）后面又重复强调一次：`it is NOT true that fast flows are erosional and slow flows are depositional (e.g., as implied in the common application of the Hjulstrom diagram)`。

**为什么不成立（成因机制）：** 床面高程会不会变，取决于"进来多少沙、出去多少沙"，而不是流有多快。一段恒定的高速流，只要上游送进来的沙量与下游带走的沙量相等，床面就纹丝不动 —— 既不侵蚀也不沉积。反之，一段很慢的流，只要下游输沙能力比上游还大，照样冲刷。**流速只是间接影响输沙率的一个变量，真正的判据是输沙率沿程的变化。**

### 2. 沉积物质量平衡与 Exner 方程

讲义把目标写成："relate dynamics of topography …… to sediment flow over the bed"（把地形的动态变化，与床面之上的沉积物通量联系起来）。

取床面上一小段长度 Δx 的控制体，涉及三个量：

- **q_s**：单宽、单位时间的沉积物体积通量（volume sediment flux per unit width per unit time）；
- **h**：水深（flow depth）；
- **η**：床面高程（bed elevation）。

平衡关系：**（流内悬浮沉积物储量随时间的增减）+（床面高程的变化）= 通量的沿程差值 q_s,in − q_s,out**。讲义的示意图标注就是 "Temporal loss/gain of sediment from/to flow" 与 "Elevation change of bed" 两项，共同由 ∂q_s/∂x 供给。

**门槛式结论（讲义原话）**：`Threshold concept: Erosion vs deposition is controlled by the rate of change (in space and time) of sediment load` —— 侵蚀还是沉积，由**输沙量在空间与时间上的变化率**决定。

- ∂q_s/∂x > 0（沿流向输沙率递增，即下游带走的比上游送来的多）→ **侵蚀**；
- ∂q_s/∂x < 0（沿流向输沙率递减）→ **沉积**。

> 📎 **背景补充：** 讲义 md 中 Exner 方程的数学式在 PDF→md 转换时丢失（只剩下 `q s`、` x`、` t`、`( y ) dy` 等碎片）。其标准形式为
> **(1 − λ_p) ∂η/∂t + ∂/∂t ∫₀^h c(y) dy = − ∂q_s/∂x**
> 其中 λ_p 为床沙孔隙度，c(y) 为悬移质浓度的垂向分布，∫₀^h c(y) dy 即"存在流体内的沉积物"那一项。若忽略流内储量的变化（稳定流常用简化），即得最常见的简化 Exner 方程 **∂η/∂t = −[1/(1−λ_p)] · ∂q_s/∂x**。讲义碎片中的 `( y ) dy` 与 ` t` 正对应积分项，可佐证此复原。

### 3. 湍流对侵蚀与沉积的意义

讲义列出四条（这是床型能"自己长出来"的物理根源）：

- 湍流使**床面剪应力沿流向和横流向都发生变化**（variation in bed shear stress along and across flows）；
- 作用力随时间可**变化四倍甚至更多**；
- 力的变化**时间尺度极短，可以是零点几秒**；
- 床面剪应力决定水流搬运沉积物的能力；**侵蚀与沉积取决于边界剪应力沿下游方向的变化**；
- 一般而言，**输沙率 q_s 随床面剪应力增大而增大**。

**推论（讲义加框强调）**：`Variation in τ₀ along and across the flow due to turbulence leads to a pattern of erosion and deposition on the bed of a mobile sediment.` —— 湍流造成的 τ₀ 空间不均匀，直接在可动床面上刻出**侵蚀-沉积的斑图**。这就是床型的胚胎：一个随机的小凸起会改变局部流场，进而改变局部 τ₀ 与 q_s，形成正反馈把凸起放大成规则地形。

### 4. 起动门槛与搬运方式

**临界剪应力 τ_cr**：`Concerns the minimum shear stress to get a grain to move in a flow (i.e. τ_cr). In general, large grains require higher τ_cr.`（让颗粒起动所需的最小剪应力；一般颗粒越大，所需 τ_cr 越高。）

**临界角实验（Critical Angle for grain movement）**：把床面缓慢加坡，重力沿坡向的分量增大；当坡度达到某个**临界角 α** 时颗粒开始运动 —— 讲义写作 "τ = τ(fr)"（驱动应力等于摩擦阻力），并给出结论：`an increase in slope leads to grain movement; any decrease in slope will stop grain` → **在任一坡度下都存在一个对应的临界剪应力 τ_cr**。这正是实习中"逐级增加水槽坡度直到床沙起动"这一操作的理论依据。

**搬运方式（讲义按 τ₀ 相对 τ_cr 的超出程度排列）**：

| 超出程度 | 搬运方式 | 说明 |
|---|---|---|
| τ₀ > τ_cr | **接触载荷 Contact load** | 颗粒始终或几乎始终与床面接触，滚动/滑动 |
| τ₀ >> τ_cr | **跃移 Saltation** | 颗粒跳跃、弹跳，短暂离开床面又落回 |
| τ₀ >>> τ_cr | **间歇悬移 Intermittent suspension** | 颗粒被湍流上举，间歇性进入水柱 |

讲义特别指出：`A flow exerts forces on all of the sediment at the surface of a loose sediment bed. In a population of particles of different sizes, the different sizes will move in different ways.` —— **同一股流在同一床面上，不同粒径的颗粒会同时以不同方式运动**（细的悬移、中的跃移、粗的滚动）。这解释了为什么天然沉积物总是分选而非"整体搬走"。

**改良 Hjulström 图（Improved Hjulstrom diagram）**：讲义标注该图为多变量函数 `f(τ, d_s, ρ_s, g, τ₀)`（原文符号在转换中残缺），图上有两条关键界线与三个域 —— 详见"三、公式与图表"第 4 条。

> 📎 **背景补充（讲义此处文字残缺）**：讲义方括号内写 `[Flow Competence: faster moving flows can carry larger particles more; Flow Capacity: faster moving flows can also carry particles]`，第二句显然掉字。这两个术语的标准定义是：
> - **流动能力 / 搬运力（Flow competence）**：水流所能搬运的**最大颗粒粒径**（质的上限）；
> - **流动容量 / 搬运量（Flow capacity）**：水流所能搬运的**沉积物总量**（量的上限）。
> 流速增大时二者同时提高，但它们是两个不同的量：一条流可能 competence 足够（能推动砾石）而 capacity 有限（沙量不足以形成厚层）。

### 5. 术语层级：Bed configuration / Bedform / Sedimentary structure

这是本周**必须分清**的三个层级（讲义原文定义）：

- **Bed configuration（床面配置 / 床型配置）**：`overall bed geometry that exists at a given time in response to the flow` —— 某一时刻床面对水流响应而呈现的**整体几何形态**，由若干 bedform 组成。
- **Bedform（床型 / 底形）**：`individual topographic elements` —— **单个地形单元**（一个沙丘、一个波痕）。
- **Sedimentary structure（沉积构造）**：`record of deposition in the presence of bedforms` —— 床型存在期间沉积作用留下的**记录**（保存进岩石里的那部分）。

讲义给的范例：**交错层理（cross-bedding）是沉积构造，由沙丘（dune）这种床型迁移产生**。

**解释范式（讲义 "Guide to interpretation"，三步法）：**
1. **仔细观察并描述**沉积构造；
2. 由**内部构造**推断：产生它的**床型类型**、**迁移方式（migration pattern）**、**沉积速率（rate of deposition）**；
3. 再由第 2 步的推断，反推产生这些的**水流条件**。

> 这三步法是全课解释沉积构造的通用套路，考试答题结构可以直接照搬：**描述 → 床型 → 流态**，中间不许跳步。

### 6. 床型的成因定义与流-床反馈

讲义的正式定义：`produced by the accumulation of mobile sediment grains into some shape or morphological element due to local changes in deposition and/or erosion in response to the interaction with a flowing current of air or water` —— 可动颗粒因**局部**侵蚀/沉积差异而堆积成的形态单元；介质可以是水也可以是空气。

**反馈**：床型不是流的被动产物，它反过来改造流 —— `create form drag which slows flow (drag coefficient Cf), sheds turbulence`：床型产生**形阻（form drag）**，使流减速（体现为阻力系数 Cf 增大），并**脱落湍流**。所以床型与流是一个耦合系统。

**床型尺度**：`orders of magnitude larger than grains`（比颗粒大若干个数量级），且 `occur under a wide range of conditions`。讲义给的野外例子：海岸的浪成波痕、沙漠中的风成波痕、河床上的沙丘。多数床型发育在砂中，但砾石和粉砂中也有。

### 7. 控制床型的变量

讲义列出的完整清单：

**流的性质**
- **流向类型**：单向流（unidirectional）、纯振荡流（pure oscillatory）、带净迁移的振荡流（flows with some net translation）、复合流（combined）。讲义说这是一个连续谱，任意组合可构成复合流。
- **流的持续时间（duration）**
- **流的强度及其随时间的变化（strength / variation through time）**

**其他重要因素**
- **颗粒直径与密度**
- **湍流边界的性质：水力光滑（hydraulically smooth）还是水力粗糙（hydraulically rough）**

最后一条是理解"为什么粗砂做不出波痕"的钥匙（见第 8、9 条）。

### 8. 平衡与滞后（disequilibrium & lag）

`If the flow changes with time the bed configuration adjusts in response but in natural flows bed configuration lags behind the change in flow – usually the bed configuration and flow are in disequilibrium.`

床型对流的调整需要**时间**（需要把大量沙搬到新位置）。因此在自然界中，床型总是**滞后**于流的变化，二者通常处于**不平衡状态**。

**两个直接后果：**
- 在实验室中必须**等待**床型与流达到（准）平衡才能测量 —— 实习 handout 开篇即用粗体强调这一点；
- 在地层记录中读到的床型，可能记录的是**洪峰过后的残余**而非峰值流况 —— 解释古水流时须留意。

### 9. 床型的地质与工程用途

`Bedforms are important in both geology and engineering`。讲义列出四条：

- 对**流深与流速**提供（宽松的）约束 —— 注意讲义用了 `[loose] constraints`，即定量反演精度有限；
- 指示流态是**浪控、风控、潮控还是单向流控**；
- 作为**古水流方向（palaeocurrent）或古岸线方向**指示；
- 作为**顶底判别（way-up）指示**，对构造研究重要（岩层是否倒转）。

### 10. 床型序列成员之一：下部平坦床（Lower Plane Bed）

`a bed with active transport but no obvious topography` —— **有活跃输沙，但没有明显地形**。

- 形成于**床沙起动门槛处**（form at threshold of bed load motion）；
- 床面**近似平坦**；
- 颗粒以**滚动与跃移混合**的方式搬运（作为**接触载荷**）；
- **平均粒径必须 > 0.5 mm**；
- **水力粗糙（hydraulically rough）**。

野外例子：河流中砂质坝顶覆盖的砾质条带（视域约 15 × 15 m, Mohrig, 2006）。

> 📎 **背景补充（机制解释，讲义未展开）**：0.5 mm 这个门槛来自**水力粗糙度**。湍流底部存在一层**黏性底层（viscous sublayer）**。当颗粒足够细、完全埋在黏性底层内时，床面对流而言是"光滑"的（hydraulically smooth），流的黏性作用可以维持小扰动并放大成波痕；当颗粒足够粗、突出黏性底层之外时，床面是"粗糙"的（hydraulically rough），黏性底层被破坏，波痕形成所需的流动机制不复存在，于是床面在起动门槛附近保持平坦 —— 即下部平坦床。这就是**粗砂做不出波痕、细砂做不出下部平坦床**的物理原因。

### 11. 床型序列成员之二：流水波痕（Current Ripples）

讲义分两页给出完整性质清单：

**形成条件**
- 特征是**极低的输沙率**（characteristic of very low transport rates）；若床面**水力光滑**，则在床沙起动门槛处即形成；
- **平均粒径必须 < 0.5–0.7 mm**（极细砂至中砂，以及部分粗砂）；
- **湍流边界必须是水力光滑的**，波痕才能形成。

**几何与运动**
- **小尺度、不对称**床型：**缓的迎水面（stoss，上游侧）+ 陡的背水面（lee，下游侧）**；
- **尺寸：高 0.005–0.05 m（0.5–5 cm），波长 0.05–0.6 m（5–60 cm）**；
- **向下游迁移**，沉积物搬运**几乎纯为底载荷（bedload）**；
- 因为向下游迁移，**可用于判定古水流方向**。

**与水深、流强的关系（重点，极易记反）**
- **不与水面相互作用，与水深无关**（Do not interact with water surface and no dependence on flow depth）；
- **波痕高度与流强、水深均无关系**（No relationship between ripple height and either flow strength or water depth）；
- **但波长随粒径变化：λ = 1000 d**。

**平面形态（planform）随流强与持续时间变化**（Cheel, 2006）
- 实验表明，**充分发育的波痕总是三维的**；
- **直线形（straight）与弯曲形（sinuous）是亚稳态**，只要时间足够，总会变成**舌状（linguoid）**；
- 因此**二维波痕（直线形/弯曲形）意味着两种情况之一**：
  1. **水流是短暂的（ephemeral）**，没来得及发育到三维；或
  2. **波痕是在有波浪参与的条件下形成的**。

### 12. 本周结论摘要（讲义 "Important points to remember from this week"）

讲义末页自列四条必记结论：**下部平坦床只在粗砂或更粗中形成**；**波痕只在中砂或更细中形成**；**波痕波长随粒径增大而增大**；**波痕尺寸与流强、水深无明确关系**，尽管**平面形态**可能随流强和/或流的持续时间变化。（详见第 10、11 条与"六、易错点"。）

---

## 三、公式与图表

### 1. 流动雷诺数（Reynolds number）

**原文形式：**

> **Re = Uhρ/μ**
>
> where: Re = Reynolds number; U = mean flow velocity; ρ = density of water; μ = molecular viscosity of water; h = mean water depth

**逐项解释：**

| 符号 | 含义 | SI 单位 |
|---|---|---|
| Re | 雷诺数，无量纲 | — |
| U | **断面平均流速**（注意不是表面流速） | m/s |
| h | **平均水深** | m |
| ρ | 水的密度（≈1000 kg/m³ @ 常温） | kg/m³ |
| μ | 水的**分子（动力）黏度** | Pa·s = kg/(m·s) |

**物理意义：** 分子 Uhρ 代表惯性力，分母 μ 代表黏滞力；Re 即**惯性力与黏滞力之比**。比值大 → 惯性主导 → 扰动无法被黏性抹平 → 湍流。

**阈值（明渠流，讲义给定）：**

| Re | 流态 |
|---|---|
| **< 500** | 层流 laminar |
| **500 – 2000** | 过渡流 transitional |
| **> 2000** | 湍流 turbulent |

**讲义的强调与结论：** `All numbers must be in SI units (i.e., kg, m, s)!` —— 全部量必须换算成 SI 单位（水深用 m 不用 cm，这是最常见的失分点）。结论用斜体加粗写出：***The results should demonstrate that all flows in the flume, and also in natural rivers, are fully turbulent even when the surface of the water is smooth and glassy.*** —— 水槽里和天然河流里的流**永远是充分湍流的**，哪怕水面看上去平滑如镜。

> 📎 **背景补充**：管流（pipe flow）常用的临界值是 2000/4000，与此处明渠流的 500/2000 不同，原因是特征长度尺度取法不同（管流取直径，明渠严格应取**水力半径 R = A/P**）。讲义这里用水深 h 近似水力半径，对**宽浅**明渠（宽深比大）是合理近似 —— 水槽实验中水浅、槽窄时该近似的误差会变大，但不影响"充分湍流"这一定性结论。

### 2. 杜布瓦方程（Du Boys equation）—— 床面剪应力

**原文形式**（md 中公式被转换损坏，原文写作 `τ₀ = ρghS`，字母列表见下）：

> **τ₀ = ρ g h S**
>
> where: τ₀ = shear stress acting on the bed; ρ = density of water; S = slope (m/m or sin α); g = acceleration due to gravity

**逐项解释：**

| 符号 | 含义 | SI 单位 |
|---|---|---|
| τ₀ | 作用于床面的（边界）剪应力 | Pa = N/m² |
| ρ | 水密度 ≈ 1000 | kg/m³ |
| g | 重力加速度 ≈ 9.81 | m/s² |
| h | 水深（**原文 where 列表漏列此项**，见勘误表） | m |
| S | 坡度，以 m/m 表示，或取 sin α | 无量纲 |

**推导直觉（为什么是"深度×坡度"）：** 长度 L、宽度 w、深度 h 的一段水体，其重力沿坡向的分量为 ρ g (L·w·h) · sin α；这个力由床面面积 L·w 承担，两边相除即得 τ₀ = ρ g h sin α = ρghS。所以 τ₀ 又叫 **depth–slope product（深度-坡度积）**。

**在实习中的用法（关键推理链）**：在水槽中**逐级抬升坡度**，直到床沙刚刚开始运动（波痕刚开始出现）的那一瞬间，记录此时的**平均水深 h** 与**水槽坡度 S**，代入上式算得的 τ₀，**就等于该粒径砂的临界剪应力 τ_cr** —— 因为"颗粒起动"的定义就是 τ₀ = τ_cr。handout 原话：`Remember for grains to move τ₀ (the applied force on the bed by the flow) = τ_cr`。

### 3. 波痕波长与粒径的关系

**原文形式：λ = 1000 d**

- λ：波痕波长（wavelength / spacing）
- d：平均颗粒直径

**读法与检验：** 波长约为颗粒直径的 **1000 倍**。代入本实习的砂（d ≈ 0.25 mm）得 λ ≈ 250 mm = 25 cm —— 落在讲义给出的波痕波长区间 0.05–0.6 m 之内，自洽。这条经验式也是"**波痕间距随粒径增大而增大**"这一结论的定量形式，且注意它**只含粒径、不含流速和水深**，与"波痕尺寸与流强/水深无关"的结论一致。

### 4. 图解一：改良 Hjulström 图（起动与沉降门槛图）

讲义标题为 `Entrainment Thresholds for Movement of Sediment — Improved Hjulstrom diagram`，并标注该门槛是多个变量的函数 `f(τ, d_s, ρ_s, g, τ₀)`（原符号在转换中残缺）。图上可辨认的标注为三段：`Entrainment threshold` / `TRANSPORT` / `Minimum settling threshold (i.e. when settling velocity > upward turbulent velocity)`。

**怎么读这张图：**

- **横轴**：颗粒粒径 d_s（对数刻度，从黏土到砾石）。
- **纵轴**：流的强度 —— 在"改良"版本中用**床面剪应力 τ₀**（原始 Hjulström 图用流速），这正是"改良"二字的含义：因为**决定颗粒动不动的是剪应力，不是流速**。
- **上方那条曲线：起动门槛线（entrainment threshold）**。位于线**之上**表示床沙被起动并进入搬运。这条线对粗颗粒段是**向右上倾斜**的（颗粒越大，起动所需 τ₀ 越大，即讲义所说 "large grains require higher τ_cr"）。
  > 📎 **背景补充**：对**黏土与粉砂**这一段，起动门槛线会**反转向上翘**（越细反而越难起动），原因是黏土的**内聚力（cohesion）**与颗粒完全埋于黏性底层内。讲义未展开这一段，但这是 Hjulström 图最著名的特征，考试中常考"为什么冲走黏土比冲走细砂还费劲"。
- **下方那条曲线：最小沉降门槛线（minimum settling threshold）**，其判据讲义写得很明确：**当颗粒沉降速度 > 向上的湍流速度分量时**，颗粒才能落下并沉积。位于线**之下**表示沉积。
- **两线之间的区域：TRANSPORT（搬运区）** —— 颗粒既不再被新起动，也还落不下来，处于持续搬运状态。这个夹层的宽度对细颗粒极大（细颗粒一旦悬浮就长期悬浮），对粗颗粒很窄（一停就落）。

**结论怎么取：** 给定粒径，从横轴向上作垂线，与两条曲线的交点把纵轴切成三段：低于下线 = 沉积，两线之间 = 搬运，高于上线 = 侵蚀（起动）。**注意讲义的核心警告仍然成立**：这张图给的是"颗粒动不动"，**不是**"床面涨还是落" —— 后者只能由质量平衡（∂q_s/∂x）判定。把 Hjulström 图直接当侵蚀/沉积判据用，正是讲义点名批评的误用。

### 5. 图解二：沉积物质量平衡示意图

**图形结构**：一个水平的床面，其上是水流，标注 **flow**、**h（flow depth）**；床面上方标出 **"sediment stored in the flow"（储存在流中的沉积物）**；控制体左右两侧箭头分别为 **q_s in** 与 **q_s out**；控制体的水平长度标为 **Δx**；床面高程标为 η。

**怎么读：** 左右两个箭头的**长度差**就是一切 —— 出去的箭头比进来的长（∂q_s/∂x > 0），控制体内的沙在净减少，其减少量必须由两处补上：**流内储量的时间变化**（`Temporal loss/gain of sediment from/to flow`）与**床面高程的变化**（`Elevation change of bed`）。若流内储量不变，则全部体现为床面下降 = 侵蚀。反之则淤积。**这张图是本周概念的骨架，比任何一条曲线都重要。**

### 6. 图解三：流水波痕剖面与迁移示意

讲义配图标注为 `Flow direction` / `flow` / `migration`。

**剖面几何**：从上游到下游依次是 —— 波谷（trough）→ **缓倾的迎水面 stoss slope**（坡度小，几度量级）→ **波峰 crest** → **陡倾的背水面 lee slope**（陡，接近休止角）→ 下一个波谷。剖面明显**不对称**，不对称的方向本身就指示流向：**缓坡朝上游、陡坡朝下游**。

**迁移机制（读图要点）**：颗粒沿 stoss 面被滚动/跃移**向上搬运至波峰**，越过波峰后进入背水面的低能区，**堆积在 lee 面顶部**，堆到超过休止角就**崩落（avalanche）**到 lee 面下部。净效果是**整个波痕形体向下游平移**，而颗粒本身也始终向下游运动 —— 二者同向。

**沉积构造的产生**：lee 面上每一次崩落都留下一个**倾斜的前积纹层（foreset lamina）**，一系列前积纹层叠置即成为**交错层理（cross-bedding / cross-lamination）**。**讲义给出的因果链是：床型迁移（过程）→ 交错层理（记录）**。反过来，在岩石中看到前积纹层的倾向，就得到了古水流方向。

### 7. 图解四：沙丘剖面素描（实习 A3 要求手绘，评分对象）

实习 handout 明确列出这张图**必须包含**的要素，等于给出了评分点清单。图应从**一个沙丘的波谷画到下一个沙丘的波谷**，包含：

- **比例尺**：标出**沙丘高度**与**波长**；
- **几何部位名称**：trough（波谷）、stoss slope（迎水面）、crest（波峰）、lee slope（背水面）；
- **流线箭头**，并标出三个点/区：**flow separation（流动分离点，位于波峰）**、**flow reattachment（再附点，位于下游波谷之后）**、**separation vortex / separation bubble（分离涡 / 分离泡，位于 lee 面下方）**。分离泡内部为**反向的上游回流**，会把颗粒**扫回 lee 面**（handout 原文：`causing upstream flow which sweeps grains back up the face`）；
- **侵蚀 / 搬运方式变化 / 沉积的位置**：颗粒在 stoss 面被侵蚀并以**滚动与跃移**向上搬运；在 crest 处越过后**进入分离区、失去搬运能力**；在 lee 面顶部堆积并**崩落（avalanching）**沉积；
- **推断并标注沿沙丘剖面的流速与床面剪应力变化**。
  > 📎 **背景补充（此项 handout 只要求"推断"，未给答案）**：沿 stoss 面向上，过流断面收窄、流线加密，**流速与 τ₀ 逐渐增大，在 crest 处达到最大**（因此输沙率也在 crest 最大）；越过 crest 后流动分离，lee 面正下方 τ₀ 骤降至接近零甚至反向；在**再附点附近**，分离剪切层重新贴附床面，湍流强度极高，**τ₀ 出现第二个局部峰值** —— 这正是**冲刷坑（scour hole）**总出现在沙丘下游波谷的原因，也是 handout 要求你"note the presence and position of any scour holes"的用意。

**水面几何（handout 要求观察，是判别沙丘 vs 逆行沙丘的关键）**：沙丘阶段，**水面在波峰上方被拉低（drawn down），在波谷上方隆起（humped）** —— 即**水面波与床面波异相（out of phase）**。

---

## 四、课堂补充

> **说明：本课全 11 周无 transcript（无课堂录音/文字稿）。本段内容来自讲义（`Class 3 slide handout 2025revised.md`）与实习 handout（`Class 3 practical handout 2025.md`）中所强调的注意事项、操作规范与评分线索，不含课堂口头补充。**

### 讲义反复强调、必须写进答案的点

1. **不要误用 Hjulström 图。** 讲义两次点名 "common application of the Hjulstrom diagram" 给出的"快流侵蚀、慢流沉积"是**错的**。答题时若涉及侵蚀/沉积判据，必须回到**质量平衡与 ∂q_s/∂x**。这是本周唯一被讲义连续否定两次的观点，出题概率极高。
2. **SI 单位。** 讲义在 Re 公式旁加了感叹号：`All numbers must be in SI units (i.e., kg, m, s)!`
3. **"充分湍流"是普适结论。** 水面平滑如镜 ≠ 层流。讲义用斜体强调这一句，并在实习 handout 中原样重复一遍 —— 同一句话在两份材料中出现两次，是最强的重点信号。
4. **粒径门槛的两端。** 下部平坦床 > 0.5 mm；波痕 < 0.5–0.7 mm。讲义在总结页又重述一遍。
5. **波痕尺寸与流强/水深无关，但平面形态与流强/持续时间有关。** 这组"有关/无关"是讲义总结页的最后一条，且句式为让步句（"although planform may vary…"），明显是防误答设计。

### 实习 handout 透露的操作规范与评分要点

1. **安全须知（原文全大写加五个感叹号）**：`SAFETY NOTE: WATER AND ELECTRICITY ARE A LETHAL COMBINATION!!!!` —— 水与电的组合是致命的。
2. **耐心等待平衡（原文加粗）**：`At each stage of the experiment be patient and allow the flow and bed to adjust to the new settings (i.e. reach some sort of equilibrium). At a minimum, allow the new bed state to be established through the middle working section of the flume.` 这与讲义中"床型滞后于流、通常处于不平衡"的理论直接呼应 —— **不等平衡就测量，数据全废**。
3. **测量位置规范**：用蜡笔（chinagraph pencil）在玻璃上标出水槽**中央 50 cm** 作为工作段；**所有观测与测量都必须在该工作段内进行，远离进出口效应（entrance/exit effects）**。
4. **水深测量规范**：平均水深须基于**至少 5 个点**、**间隔 10 cm**、位于工作段内的测量；且**水深是从自由水面量到砂床顶面，不是量到水槽的硬底**（handout 特别加注：`not to the solid flume bed`）。这一点直接影响 Re 与 τ₀ 两个计算的正确性。
5. **团队分工与个人责任**：8 人一组，8 个岗位（见"五、Practical 要点"），但 handout 写明 **`Everyone should make their own observations and calculations`** —— 分工只针对操作，观察与计算**每人必须自己做一份**。这条是防止"抄组员数据"的明确要求。
6. **时间压力（原文斜体）**：`Time is of the essence in the remaining parts of the experiment because the high rates of bed material transport associated with the next bedforms will overwhelm the capacity of the flume to recirculate sediment, resulting in rapid scour down to the solid flume bed. Measurements must be made as quickly as possible once each bedform regime has become established.` —— 上部床型阶段输沙率极高，水槽的循环能力跟不上，会迅速把砂冲光露出硬底。因此**上部平坦床、驻波、逆行沙丘三段必须快速测完**。
7. **要求"边做边判断、必要时调整流程"**：ILO 中写明 `This will require you to evaluate your observations during the experiment and make adjustments to the instructions as required.` —— handout 里多处写 "**If necessary**, increase the slope incrementally"，即给定的步骤是指导性的而非机械的。
8. **门槛的判定要自己定义**：`To find this point you will need to decide how many grains need to be moving for the threshold of motion to be exceeded.` —— 起动门槛没有客观标准，**需要小组自行约定一个操作性定义**（例如"视野内持续有 N 粒以上在动"），并在报告中说明。这本身是可写进报告的方法学讨论点。

### 与评分挂钩的背景（来自课程大纲）

- 课程评分：**笔试 50%**（1.5 小时）+ **报告 1 25%**（约 10 月底交，5 页含素描，考核 ILO 1–3、5）+ **报告 2 25%**（约 12 月底交，5 页含素描，考核 ILO 1–5）。
- **ILO 5 单列了"素描薄片与手标本、绘制沉积柱状图"**，即**画图本身是被单独评分的能力**。本周实习要求的沙丘剖面素描（带标注、带比例尺、带流线与侵蚀/沉积分区）正是这项能力的直接训练，其要素清单应当照单全收。
- 大纲教学法一节写明：`It is crucial that students attend all classes and practical classes, as themes build rapidly on one another through the course.` 本周尤其如此 —— 第 3 周实习做的实验，其后半段（沙丘至逆行沙丘）的理论要到第 4 周讲义才补上。

---

## 五、Practical 要点

### 1. 目的与定位

**实验名称**：Experiment 1 — Bedforms in fine to medium grain sand（细砂至中砂中的床型）。

**目的（原文）**：`to demonstrate the sequence of bedforms which appear under a unidirectional open channel flow, with a mobile sand-bed, as the intensity of sediment transport increases.` —— 演示在单向明渠流下、可动砂床上，**随着输沙强度增加而依次出现的床型序列**。

**本周重心**：handout 写明 `This week we will focus on making qualitative and quantitative observations.`（本周重点是做**定性与定量观测**）。也就是说，第 3 周实习的任务是**采集**现象与数据；理论解释（尤其是沙丘及以上部分）要到第 4 周才完整。

**受控变量（保持恒定）**：
- 粒径：**平均 255 µm，范围 300–150 µm**（handout 背景段；器材段另写作 "0.1 and 0.3 mm"，二者不一致，见勘误表）；
- 颗粒密度：**石英**；
- 流体密度与黏度：**20 °C 的水**。

**自变量**：**水槽坡度**与**泵的排量档位** —— 二者共同提高流强与输沙强度。

### 2. 器材与岗位分工（8 人组）

| 器材 | 用途 |
|---|---|
| Flume（演示水槽） | 主体设备 |
| Stop watch 秒表 | 计时（迁移速率、球速） |
| Digital spirit level 数字水平仪 | 测床面坡度 |
| Ruler 直尺 / Tape measure 卷尺 | 测水深、距离 |
| Neutrally buoyant green balls 中性浮力绿球 | 测表面流速（方法 2） |
| Velocity meter 流速仪 | 测平均流速（方法 1） |
| Chinagraph pencil 蜡笔 | 在玻璃上标记工作段、追踪床型位置 |
| Red food colouring + pipette 红色食用色素与滴管 | 流动显形（判层流/湍流） |

| 岗位 | 职责 |
|---|---|
| Job 1 | "the fat controller" —— 掌控水槽控制系统，兼**溢流监视（flood watch）** |
| Job 2 | 数据记录员 |
| Job 3 | 用数字水平仪测**床面坡度** |
| Job 4 | 流动显形（红色染料 + 滴管） |
| Job 5 | **床型迁移速率**（蜡笔 + 秒表 + 直尺） |
| Job 6 | 流速方法 1（**流速仪**） |
| Job 7 | 流速方法 2（**秒表 + 中性浮力绿球**） |
| Job 8 | 水深（直尺） |

### 3. 装置初始设置

- 均一粒径的砂铺入水槽，**厚度均匀**；
- 砂面**夯实（tamped down）**至均匀密实、轻度压实、尽可能平整；
- **流量阀完全关闭**；
- **水槽坡度设为零**。

**准备**：蜡笔标出中央 50 cm 工作段；确认自己负责的仪器怎么用。

### 4. 操作流程与"观察 → 判定"推理链

实验的核心逻辑是：**每一步只做一件事 —— 小幅提高流强（加坡度或加泵档）→ 等床面达到新平衡 → 记录现象与数据 → 判定当前床型**。以下逐段拆解。

---

#### 起步：无运动的平坦床（plane bed with no motion）

**操作**：坡度归零，**流量阀开两圈**，泵置**最低档 I**，放水入槽，静置数分钟；确认沿全槽达到**稳定流（steady flow）**且**床面无运动**。随后**把坡度略微抬到一个非零值**，但不足以超过床沙起动门槛。

**观察 → 判定**：
- 看到：床面完全不动，几乎零输沙，无任何地形起伏。
- 判定：**plane bed with no motion（无运动的平坦床）**，τ₀ < τ_cr。
- ⚠️ **这不是"下部平坦床"**（后者是**有活跃输沙**的平坦床）。二者极易混淆，见第六节。

---

#### A1：起动前的流与床的基本描述 —— 流态判定

**问题**：`Is the flow structure laminar or turbulent?` 用**两种方法**判定。

**方法 1：染料示踪。** 滴入红色食用色素。
- **观察 → 判定**：染料若**拉成一条清晰细线**不扩散 → 层流；若**迅速被搅散、混合**成一片 → **湍流**。实验中看到的是后者。

**方法 2：计算雷诺数。** 测平均流速 U 与平均水深 h，代入 **Re = Uhρ/μ**（全部用 SI 单位）。
- **观察 → 判定**：算得 Re > 2000 → **湍流**。

**预期结论（handout 斜体原话）**：`The results should demonstrate that all flows in the flume, and also in natural rivers, are fully turbulent even when the surface of the water is smooth and glassy.` —— **水槽与天然河流中的流永远充分湍流，哪怕水面平滑如镜。** 这一句在讲义和 handout 中各出现一次，是本次实习最确定的"标准答案"。

---

#### A2：起动条件 —— 求临界剪应力 τ_cr

**操作**：**逐级增加坡度**，直到出现"小而有限的输沙量"。此时床沙起动，**几乎立刻会出现小的三角形床型 —— 波痕（ripples）**：高几毫米、长一两厘米、不对称（**缓的上游坡 + 陡的下游面**）。观察组成波痕的颗粒如何运动；观察水面的几何形态。

**记录**：**平均水深 h、坡度 S、流速 U**。

**计算 → 判定（关键推理链）**：
1. 判据：颗粒起动的定义是 **τ₀ = τ_cr**（handout 明写）；
2. 因此，在**刚起动的那一刻**测得的 h 与 S，代入 **τ₀ = ρ g h S**；
3. 所得数值**即为该砂（≈0.25 mm 石英砂）的临界剪应力 τ_cr**。

**观察 → 判定（床型）**：看到高 mm 级、长 cm 级、缓坡朝上游 / 陡坡朝下游的小三角形起伏，且颗粒几乎全为底载荷滚动 → 判定为 **current ripples（流水波痕）**。可与讲义给出的尺寸区间（高 0.005–0.05 m、波长 0.05–0.6 m）与 λ = 1000 d ≈ 0.25 m 对照检验。

---

#### A3：向沙丘过渡（Transition to dunes）

**操作**：**泵排量提高到档 III**。水深与输沙率立即上升。**必要时再逐级加坡度**，直到看见颗粒**周期性地跳跃、弹跳** —— 尽管**主导运动方式仍是滚动**。这种跳跃即**跃移（saltation）**。

**观察 → 判定**：
- 出现**更大的三角形床型**，且**比波痕更长、顶部更平坦**，并且**扰动了水的自由表面** → 判定为 **dunes（沙丘）**。
- ⚠️ handout 特别提醒：**小水槽里做出来的沙丘，尺寸并不比自然界的波痕大多少** —— **不能用绝对尺寸来区分波痕与沙丘**，要用"**是否与水面相互作用**"这一判据（波痕不与水面作用、与水深无关；沙丘扰动水面、受水深控制）。

**沙丘床面建立后，逐项观察（handout 列出的观察清单）**：
- **水面在波峰上方被略微拉低（drawn down）、在波谷上方隆起（humped）** → **水面波与床面波异相（out of phase）**；
- 沙丘背水侧因湍流出现的**涌沸（boils）**；
- 颗粒沿**迎水面 stoss 以滚动与跃移**向上游侧搬运；
- 颗粒在**背水面 lee 崩落（avalanching）**；
- 背水面存在**分离泡（separation bubbles）**，其内为**上游回流**，把颗粒扫回 lee 面；
- 沙丘的**排列方向、波峰的平面图案**，以及**冲刷坑（scour holes）的有无与位置**。

**产出 1：沙丘剖面素描**（要素清单见"三、公式与图表"第 7 条，逐项对应评分点）。

**产出 2：定量测量**
- 用**蜡笔 + 秒表 + 直尺**记录**沙丘向下游的迁移速率**；
- **方法 1** 测**平均流速**（流速仪）；
- **方法 2** 测**表面流速**（中性浮力绿球 + 秒表）；
- **对比两者，回答 `why are they so different?`**

> 📎 **背景补充（handout 只提问未给答案，但答案在 Week 2 的知识范围内）**：因为**明渠流存在垂向流速剖面**。床面处受**无滑移条件（no-slip condition）**约束流速为零，流速沿水柱向上呈对数式增大，**在近水面处最大**。因此**方法 2 测到的表面流速显著大于方法 1 的断面平均流速**。经验上，明渠中断面平均流速约为表面流速的 **0.8–0.85 倍**（等价地，平均流速大致出现在**水面以下 0.6 倍水深处**）。若报告中需要一个统一的 U 代入 Re 或做流量计算，**应使用断面平均流速（方法 1）**，或对表面流速施加换算系数并说明。

---

#### A4：沙丘平面形态与流强

**操作**：**流量阀全开**，产生最大排量。水深再次增大，泥沙运动强度增大。

**观察 → 判定**：
- **跃移更显著**；可观察到部分颗粒以**悬移载荷（suspended load）**运动 —— 判据非常具体：**颗粒从一个沙丘的波峰直接跃过波谷、落到下一个沙丘的迎水面上，中途不在波谷停留**；
- 观察输沙量与颗粒运动方式的变化，并回答：**这与你看到的沙丘高度和波长的变化有什么关系？**

> 📎 **背景补充（此问 handout 未给答案）**：随流强继续增大，沙丘先增大后开始**被"冲刷"变低变长**（趋向 A5 的 washed-out dunes）。物理原因是悬移作用增强后，颗粒不再全部堆积在 lee 面顶部形成陡坡，而是被带过波谷落到远处，使背水面变缓、地形起伏被削平。

---

#### A5：从沙丘到上部平坦床

**操作 1**：**大幅增加坡度**。

**观察 → 判定**：沙丘**变长、振幅降低** → 形成长而低平的床型，即 **washed-out dunes（冲刷沙丘 / 过渡床型）**。观察其形态、**波谷与冲刷坑的有无**、底载荷的运动情况，以及水面**涌沸与下凹区（boils and drawdown areas）的有无**。

**记录**：当冲刷沙丘占据整个工作段时，记录**流速、平均水深、水槽坡度**。

**操作 2**：**再一次大幅增加坡度**。

**观察 → 判定**：冲刷沙丘消失，建立 **plane bed with motion（有运动的平坦床，即上部平坦床 upper plane bed）**。观察：
- 水深与水面外观的变化，**涌沸与表面湍流的有无**；
- 运动中的底载荷的外观，并从上方注意床面上出现**平行于流向的"条纹（streaks）"** —— 这是上部平坦床的**诊断性特征**。

> 📎 **背景补充**：这些平行流向的条纹在岩石记录中保存下来即为**平行层理（parallel lamination）**，其层面上常见**剥离线理（parting lineation / primary current lineation）** —— 是识别上部流态平坦床沉积的经典标志，也是判定古水流**方位（线，不定向）**的依据。

**⚠️ 从此段起进入 handout 强调的"时间紧迫"区间**：高输沙率会压垮水槽的沉积物循环能力，导致快速冲刷至硬底。**每种床型一旦建立就要尽快测完。**

---

#### A6：驻波与逆行沙丘

**操作 1**：**小幅增加坡度**。

**观察 → 判定**：平滑如镜的水面开始变形为**几乎静止不动的起伏 —— 驻波（standing waves）**。观察床面外观，并注意**床面特征与水面形态之间的关系**。

**操作 2**：**较大幅度增加坡度**，使流进入充分的上部流态（upper regime）。

**观察 → 判定**：
- 观察水面波的振幅与其下方的床型；注意床型的**对称性与规则性** → 判定为 **antidunes（逆行沙丘）**。
- 观察颗粒运动：颗粒**从一个逆行沙丘的下游面被侵蚀，沉积到下游相邻逆行沙丘的上游面上**。
- **关键结论（handout 加粗强调的反直觉点）**：**逆行沙丘的形体向上游迁移**，与水流方向和颗粒运动方向相反。可用蜡笔在槽壁上描出逆行沙丘轮廓、随时间观察其位置来验证。**必须认识到：水与颗粒始终向下游运动，尽管床型向上游移动。**

> 📎 **背景补充**：床型向上游移动，是因为**上游侧侵蚀量 < 上游侧沉积量**造成波形的净上游位移 —— 形体运动方向与物质运动方向可以相反，这与波浪本身的性质一致（波形传播 ≠ 质点输运）。此外，与沙丘阶段相反，逆行沙丘的**水面波与床面波是同相的（in phase）**，这正是 handout 让你"note any relationship between the bed features and the flow surface"的答案，也是野外区分上、下部流态的关键判据。

**操作 3**：**适度增加坡度**。输沙强度相应增加，逆行沙丘的移动速率加快。

**观察 → 判定**：随逆行沙丘振幅增大，水流爬升至波峰所损失的能量越来越大；**到某一点，波峰处的流看似失速（stall），发生强烈湍流，床型被破坏、向上游方向破碎消散** → 判定为 **breaking antidunes（破碎逆行沙丘）**。破碎通常**不是随机的**：下游一个逆行沙丘的破碎会触发其上游相邻者破碎，如此沿槽长依次传递；**自然界中这导致脉动流（pulsing flow）**，但由于需要极高且持续的床沙输运，此类床型**在自然界中相对罕见**。

---

### 5. 本次实习完整的床型序列（判定顺序）

| 阶段 | 床型 | 主要判据 | 主要搬运方式 |
|---|---|---|---|
| 0 | 无运动的平坦床 plane bed with no motion | 床面完全不动，无地形 | （无） |
| 1 | 流水波痕 current ripples | mm–cm 级、不对称三角形、不扰动水面 | 滚动（底载荷） |
| 2 | 沙丘 dunes | 更长更平顶、**扰动水面**、水面与床面**异相** | 滚动 + 跃移 |
| 3 | 冲刷沙丘 washed-out dunes | 长、低平、振幅减小 | 跃移 + 部分悬移 |
| 4 | 上部平坦床 plane bed with motion | 平坦、水面平滑、**平行流向的条纹** | 强跃移 + 悬移 |
| 5 | 驻波 standing waves | 水面出现近静止起伏 | — |
| 6 | 逆行沙丘 antidunes | 对称、规则、水面与床面**同相**、床型**向上游迁移** | — |
| 7 | 破碎逆行沙丘 breaking antidunes | 波峰失速、强湍流、床型向上游破碎 | — |

> **注意：本序列中没有"下部平坦床（lower plane bed）"**。原因是讲义给出的粒径门槛：下部平坦床需要**平均粒径 > 0.5 mm**（粗砂或更粗），而本实验用砂仅约 0.25 mm（细–中砂）。**用这套砂，无论如何调坡度都做不出下部平坦床** —— 起动门槛一被越过就直接进入波痕。这是把讲义的粒径门槛与实习现象对接起来的最好例子，值得作为报告中的讨论点。

### 6. handout 明确要求记录的量（勿漏）

- **起动瞬间**：平均水深、坡度、流速 → 据此算 **τ_cr**；
- **沙丘阶段**：沙丘**迁移速率**、**方法 1 平均流速**、**方法 2 表面流速**（并解释二者差异）、**沙丘剖面素描**；
- **冲刷沙丘占满工作段时**：**流速、平均水深、水槽坡度**；
- 全程：各阶段的**定性观察记录**（水面形态、涌沸、冲刷坑、颗粒运动方式）。

---

## 六、易错点 / 重点难点

1. **"快流侵蚀、慢流沉积" —— 本周最大的靶子。**
   侵蚀/沉积由 **∂q_s/∂x（输沙率的时空变化率）** 决定，不由流速绝对值决定。恒定高速流若进出通量相等，床面不变。**Hjulström 图只能回答"颗粒动不动"，不能回答"床面涨不涨"。** 讲义两次点名批评此误用。

2. **三种"平坦床"必须分清。**
   | 名称 | 有无输沙 | 流态位置 | 粒径要求 |
   |---|---|---|---|
   | Plane bed with **no** motion（无运动平坦床） | 无 | 起动门槛**以下** | 任意 |
   | **Lower** plane bed（下部平坦床） | **有**（接触载荷） | 起动门槛**处**，下部流态 | **> 0.5 mm** |
   | **Upper** plane bed / plane bed with motion（上部平坦床） | 有（强，含悬移） | 上部流态，**沙丘之后** | 任意 |
   最常见的错误是把"起动前的平床"当成"下部平坦床"，或把上、下部平坦床混为一谈。**关键区分：有无输沙 + 位于序列的哪一端。**

3. **波痕的"三无一有"。**
   波痕**与水深无关**、**与水面不相互作用**、**高度与流强/水深均无关系**；**但**波长**有**明确关系：**λ = 1000 d**（只与粒径有关）。考试常把"波痕大小随流速增大而增大"作为诱答项 —— 这是错的。

4. **平面形态的推论方向不要搞反。**
   波痕**尺寸**与流强无关，但**平面形态（planform）**受流强与流的**持续时间**影响。充分发育的波痕**总是三维（舌状 linguoid）**；直线形与弯曲形是**亚稳态**。因此在岩石中看到**二维波痕**，应推断**流是短暂的**，或**有波浪参与** —— 而不是推断"流很弱"。

5. **粒径门槛的两端不要记反。**
   **下部平坦床：粗砂或更粗（> 0.5 mm）**；**波痕：中砂或更细（< 0.5 mm，讲义正文放宽到 0.5–0.7 mm）**。记忆抓手：**粗颗粒突出黏性底层 → 水力粗糙 → 做不出波痕**；细颗粒埋在黏性底层内 → 水力光滑 → 才能起波痕。
   ⚠️ 讲义正文（"< 0.5–0.7 mm, vf–m sand and **some c sand**"）与总结页（"only in **medium sand or finer**"）之间存在轻微矛盾，见勘误表。**考试建议以总结页的 0.5 mm 为准，并在答题时注明约 0.5–0.7 mm 为过渡区间。**

6. **波痕 vs 沙丘不能靠绝对尺寸区分。**
   实习 handout 明写：小水槽中的沙丘"尺寸并不比自然界的波痕大多少"。正确判据是：**是否扰动自由水面 / 是否受水深控制**（波痕否，沙丘是），以及形态（沙丘更长、顶部更平坦）。

7. **水面波与床面波的相位关系是流态判别的钥匙。**
   **沙丘阶段：异相（out of phase）** —— 峰上水面下凹、谷上水面隆起（handout 明写）。**逆行沙丘阶段：同相（in phase）**（📎 补充，handout 只要求你自己观察归纳）。这是区分下部流态与上部流态最直观的野外/实验判据。

8. **逆行沙丘的"逆"只逆在形体上。**
   **床型向上游迁移，但水与颗粒始终向下游运动。** handout 用一整句强调此点（`It must be recognised that the water and the grains move downstream at all times, even though the bedform moves upstream.`）。这也提醒：**形体运动方向 ≠ 物质运动方向**，同一逻辑也适用于解释波痕/沙丘为何向下游迁移。

9. **计算题的三个陷阱。**
   - **单位**：Re 与 τ₀ 全部用 SI（水深换成 m，粒径换成 m）；
   - **水深的量法**：从**自由水面量到砂床顶面**，不是量到水槽硬底 —— 量错会同时污染 Re 与 τ₀；
   - **用哪个流速**：Re 中的 U 是**断面平均流速**（方法 1），不是绿球测的表面流速（方法 2）。

10. **实验方法上的两个易失分点。**
    - **不等床型达到（准）平衡就测量** —— 与"床型滞后于流"的理论矛盾，数据无意义；
    - **观测跑到工作段以外** —— 进出口效应会污染流场；handout 要求全部观测限于中央 50 cm、平均水深取 5 点、间隔 10 cm。

11. **"起动门槛"没有客观定义。**
    handout 明确把"多少粒在动才算超过门槛"交给小组自己决定。答报告时**必须写明你采用的操作性定义**，并意识到这是 τ_cr 测值不确定性的主要来源之一。

12. **Exner 方程的两项不要漏。**
    床面高程变化只是方程的**一部分**，另一部分是**存在流体中的沉积物量的变化**。在悬移质浓度剧烈变化的情形（如洪峰上涨期），通量的沿程变化可能主要被"流内储量增加"吸收，而床面几乎不变。

---

## 七、本周术语表

| 英文 | 中文 | 本周语境下的要点 |
|---|---|---|
| Bed configuration | 床面配置 / 床型配置 | 某一时刻床面对流响应的**整体几何形态**，由若干 bedform 组成 |
| Bedform | 床型 / 底形 | **单个地形单元**（一个波痕、一个沙丘）；比颗粒大若干数量级 |
| Sedimentary structure | 沉积构造 | 床型存在期间沉积作用留下的**记录**（如交错层理） |
| Exner equation | 埃克斯纳方程 / 沉积物质量平衡方程 | 侵蚀/沉积由 ∂q_s/∂x 决定，非由流速决定 |
| Sediment mass balance | 沉积物质量平衡 | 进出通量差 = 流内储量变化 + 床面高程变化 |
| q_s (sediment flux) | 单宽输沙通量 | 单位宽度、单位时间的沉积物体积 |
| Bed elevation (η) | 床面高程 | Exner 方程的因变量 |
| Bed shear stress (τ₀) | 床面（边界）剪应力 | 水流施加于床面的单位面积作用力；τ₀ = ρghS |
| Critical shear stress (τ_cr) | 临界剪应力 | 使颗粒起动所需的最小剪应力；粒径越大越高 |
| Critical angle | 临界角 | 使颗粒开始运动的坡度；每个坡度对应一个 τ_cr |
| Du Boys equation | 杜布瓦方程 | τ₀ = ρghS，深度-坡度积 |
| Reynolds number (Re) | 雷诺数 | Re = Uhρ/μ；明渠 <500 层流、>2000 湍流 |
| Laminar flow | 层流 | 染料拉成细线不混合 |
| Turbulent flow | 湍流 | 染料迅速混合；水槽与天然河流恒为充分湍流 |
| Turbulence | 湍流（作用） | 造成 τ₀ 沿流向与横流向的时空变化（可达 4 倍以上，时标 <1 s） |
| Entrainment threshold | 起动门槛 | 改良 Hjulström 图上方曲线，之上即被起动搬运 |
| Minimum settling threshold | 最小沉降门槛 | 沉降速度 > 向上湍流速度时颗粒才落下 |
| Hjulström diagram | Hjulström 图 | 常被误用作侵蚀/沉积判据；改良版纵轴用剪应力 |
| Flow competence | 流动搬运力 | 水流能搬动的**最大粒径** |
| Flow capacity | 流动搬运量 | 水流能搬运的**沉积物总量** |
| Contact load | 接触载荷 | τ₀ > τ_cr；滚动/滑动，几乎不离床面 |
| Bedload | 底载荷 / 推移质 | 沿床面搬运的部分；波痕的搬运几乎纯为底载荷 |
| Saltation | 跃移 | τ₀ >> τ_cr；颗粒跳跃弹跳 |
| (Intermittent) suspension | （间歇）悬移 | τ₀ >>> τ_cr；颗粒被湍流上举进入水柱 |
| Suspended load | 悬移载荷 | 实习判据：颗粒从一个沙丘峰直接跃到下一个沙丘迎水面 |
| Hydraulically smooth | 水力光滑 | 颗粒埋于黏性底层内；波痕形成的必要条件 |
| Hydraulically rough | 水力粗糙 | 颗粒突出黏性底层；下部平坦床的条件 |
| Form drag | 形阻 | 床型对流产生的阻力，使流减速（阻力系数 Cf） |
| Unidirectional flow | 单向流 | 本周实验的流型（河流型） |
| Oscillatory flow | 振荡流 | 波浪型；与单向流组合可成复合流 |
| Combined flow | 复合流 | 单向流与振荡流的叠加 |
| Disequilibrium / lag | 不平衡 / 滞后 | 自然界中床型总滞后于流的变化 |
| Flume | 水槽 | 顶部开敞的人工渠道，本周实习装置 |
| Working reach | 工作段 | 水槽中央 50 cm，所有测量须在此进行 |
| Plane bed with no motion | 无运动的平坦床 | 起动门槛以下，无输沙无地形 |
| Lower plane bed | 下部平坦床 | 有活跃输沙但无明显地形；需 > 0.5 mm 且水力粗糙 |
| Current ripple | 流水波痕 | < 0.5–0.7 mm；高 0.005–0.05 m，λ 0.05–0.6 m，λ = 1000d |
| Stoss (slope) | 迎水面 / 迎流面 | 上游侧，坡缓 |
| Lee (slope) | 背水面 / 背流面 | 下游侧，坡陡；崩落沉积发生处 |
| Crest / Trough | 波峰 / 波谷 | 床型的顶与底 |
| Straight / Sinuous / Linguoid ripple | 直线形 / 弯曲形 / 舌状波痕 | 前两者亚稳态，充分发育必成舌状（三维） |
| Planform | 平面形态 | 随流强与流持续时间变化（尺寸则不随） |
| Dune | 沙丘 | 大型不对称床型；扰动水面，与水深有关 |
| Flow separation / reattachment | 流动分离 / 再附 | 分离于波峰，再附于下游波谷之后 |
| Separation vortex / bubble | 分离涡 / 分离泡 | 背水面下方的反向回流区，把颗粒扫回 lee 面 |
| Avalanching | 崩落 | 颗粒在 lee 面超过休止角后崩塌，形成前积纹层 |
| Boil | 涌沸 | 背水面湍流涡上升至水面形成的沸腾状水面特征 |
| Drawdown | 水面下凹 | 沙丘波峰上方的水面降低 |
| Scour hole | 冲刷坑 | 沙丘下游波谷处的局部深坑（再附点附近剪应力峰值） |
| Washed-out dune | 冲刷沙丘 | 长而低平的过渡床型，沙丘→上部平坦床之间 |
| Plane bed with motion / Upper plane bed | 有运动的平坦床 / 上部平坦床 | 床面平坦，出现平行流向的条纹（streaks） |
| Standing wave | 驻波 | 上部流态，水面近静止的起伏 |
| Antidune | 逆行沙丘 | 对称规则；形体向上游迁移，水与颗粒仍向下游 |
| Breaking antidune | 破碎逆行沙丘 | 峰部失速、强湍流破碎；自然界罕见 |
| Cross-bedding | 交错层理 | 由沙丘迁移产生的沉积构造 |
| Palaeocurrent | 古水流 | 由波痕/沙丘迁移方向恢复 |
| Way-up indicator | 顶底判别标志 | 判定地层是否倒转，对构造研究重要 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `(EART27201) Sedimentary Rocks and Fossils.md`，Syllabus 一节 | "W3: Lecture: Carbonate sedimentary rocks. Allochem types and preservation modes. Practical: Depositional history of carbonate sedimentary rocks from hand specimen and thin sections." | **与实际交付内容不符。** 实际 Class 3 讲义为 "Bed Configurations (Part 1)"，实习为水槽床型实验；大纲把"物理沉积构造 + 水槽实验"列在 W10。同理 Class 4 讲义为 "Bed Configurations (Part 2)"，大纲 W4 却写三叶虫与腕足。整个周次编排系统性错位。 | 以**讲义与实习 handout 的实际内容为准**。大纲的 Syllabus 表可作为"本课涵盖哪些题目"的清单使用，但**不可用于定位周次**。 |
| `Class 3 practical handout 2025.md`，"Background to the practical" 段 vs "Equipment Set Up" 段 | 背景段："The grain size of the sediment will be held constant (mean=255 µm; **range 300-150 µm**)"；器材段："Sand of a uniform size between **0.1 and 0.3mm**" | 两处粒径**下限不一致**：0.15 mm vs 0.1 mm。 | 两处应统一。以背景段的 150–300 µm 更可能为实际用砂（0.1–0.3 mm 疑为口径较粗的概述）。对本实习的结论（细–中砂，不可能形成下部平坦床）无影响。 |
| 同上，"Background to the practical" 段 | "mean=255 µm; range 300-150 µm" | 255 µm 与 150–300 µm 区间的中点（225 µm）不符，**疑为 225 的数字颠倒**。且 255 µm 恰好跨过 Wentworth 细砂/中砂界线（250 µm），会影响"细砂还是中砂"的判定。 | 无法从材料确证，**存疑标注**。若为 225 µm 则为**细砂**；若为 255 µm 则勉强为**中砂**。两种情形均 < 0.5 mm，均落在波痕形成的粒径域内，故不影响实验结论。报告中引用时建议写"细至中砂，约 0.2–0.3 mm"。 |
| `Class 3 practical handout 2025.md`，A2 段 | "You can calculate the shear stress ... using **Du Buoys** equation" | **人名拼写错误。** | 应为 **DuBoys / Du Boys**（法国工程师 P. du Boys, 1879）。 |
| 同上，A2 段公式定义列表 | "where: τ₀ = shear stress acting on the bed, ρ = density of water, S = slope (m/m or sin α), and g = acceleration due to gravity" | **漏列 h（水深）**，而 h 出现在公式 τ₀ = ρghS 中。 | 应补 "h = mean flow depth (m)"。 |
| `Class 3 slide handout 2025revised.md`，"Entrainment Thresholds" 页 | "[Flow Competence: faster moving flows can carry _larger_ particles _more_ Flow Capacity: faster moving flows can also carry particles]" | **句子残缺、两个定义粘连**，Flow Capacity 的定义丢失关键词（应为 "more/a greater quantity of particles"）。 | 正确定义：**Competence = 能搬运的最大粒径**；**Capacity = 能搬运的沉积物总量**。 |
| `Class 3 slide handout 2025revised.md`，Exner 方程两页 | 公式部分仅剩 `q s`、` x`、` t`、`c`、`( y ) dy`、`=` 等碎片，无完整算式 | **PDF→md 转换时数学式丢失**（非作者错误）。 | 已在"三、公式与图表"第 2 节以 📎 标注复原标准形式。复习时如需精确算式请对照原 PDF 或教材（Nichols, *Sedimentology and Stratigraphy*）。 |
| `Class 3 slide handout 2025revised.md`，"Improved Hjulstrom diagram" 页 | "# _f_   , ds,  s, g, 0)" | **希腊字母与左括号在转换中丢失**，函数式不可读。 | 据上下文应为 f(τ, d_s, ρ_s, g, τ₀) 之类的多变量函数式；图中曲线亦丢失，仅存文字标注。 |
| `Class 3 slide handout 2025revised.md`，Current Ripples 页 vs Summary 页 | 正文页："Mean grain size must be **<0.5-0.7 mm** (vf-m sand and **some c sand**)"；总结页："Ripples form only in **medium sand or finer**" | **两处粒径上限不一致**：0.7 mm 属粗砂，与"中砂或更细（≤0.5 mm）"矛盾。 | 建议以 **0.5 mm** 作为记忆基准（与下部平坦床的 > 0.5 mm 门槛互补），并注明 0.5–0.7 mm 为过渡区间。 |
| `Class 3 slide handout 2025revised.md`，Lower Plane Bed 页 vs Current Ripples 页 | 一处写 "Hydraulically rough / hydraulically smooth"，另一处写 "**hydrodynamically** smooth" | **术语不统一**（小问题）。 | 标准术语为 **hydraulically smooth / rough**（水力光滑 / 水力粗糙）。 |

> **说明：** 实习 handout `Class 3 practical handout 2025.md` 同时出现在 `Practical/Week 3/` 与 `Practical/Week 4/` 两处，属课程有意安排 —— 同一场水槽实验横跨两周使用（第 3 周讲义只讲到波痕，沙丘至逆行沙丘的理论在第 4 周补齐）。**这不是重复上传，不计入勘误。**
