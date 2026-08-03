# EART24001 Geological Maps — Week 04 学习笔记

> 材料来源：`Week 4/` 下 6 份 md —— `0-HandoutFold.md`（主讲义）、`Vshaped.md`、`EgExSoln.md`、`FoldEPsoln.md`、`MapSoln.md`、`SectSoln.md`，外加课程 unit spec。
> **本周无 transcript**（EART24001 全门 10 周均无 transcript），且四份答案文件是**手绘图件**，转 md 后只剩零碎图注（全周合计约 1,057 词）。因此本笔记大量内容是**由 handout 正文 + 答案图注中的数字反推重建**的作图方法，凡原材料未明说者一律以 `📎 背景补充：` 标出。

---

## 一、本周主题

**褶皱几何（fold geometry）与褶皱地层上的地层等高线（stratum contours on folds）。**

全课主线是**如何在二维图幅上表达并解读三维地质结构**：W1–2 从产状与地层等高线（strike lines / stratum contours）起步；随后逐类构造攻克 —— 不整合（W3）、**褶皱（W4）**、断层（W5）、侵入体与事件序列（W8）；W6–7 引入赤平投影与方向数据统计；W9–10 在真实图幅上综合。

本周是「逐类构造」的**第二类**，位置关键，因为褶皱是第一个让「地层等高线不再是一组平行直线」的构造：W1–2 一个接触面 = 一个平面 → 地层等高线是一组等间距平行直线；W3 不整合多了截切面，但每个面仍近似平面 → 仍是平行直线，只是分组；**W4 同一接触面被弯成曲面 → 地层等高线在两翼各自是直线，却在轴迹处折转**，整套技法必须升级。

同时本周把 `Vshaped.md`（V 字形出露）正式提上台面：handout 明说「褶皱也会产生形状相似的出露图案，所以**在图上定轴迹时必须注意这种由地形造成的效应**」—— 这是本周的核心判读陷阱。对应 **ILO 2**（识别褶皱并与地形效应区分）、**ILO 3**（分析三维几何）、**ILO 4**（剖面表达）。

---

## 二、核心概念

### 1. 柱状褶皱与非柱状褶皱（cylindrical / non-cylindrical folds）— handout 原文

- 一个曲面，如果它的形状**可以由一条直线保持自身平行地平移而生成**，就叫**柱状褶皱面（cylindrically folded surface）**。这条能生成该曲面的直线称为**褶皱轴（fold axis）**。
- 柱状褶皱的一个重要性质：**在任意一组互相平行的剖面上，褶皱的形态都相同**（"the fold shape on parallel cross-section planes, whatever their orientation, is constant"）。

📎 背景补充：这条性质是本周一切作图的**理论前提**。因为形态在平行剖面上不变，才可以：(a) 把图上不同位置测到的产状当成同一褶皱的翼合并处理；(b) 只画一条剖面代表整个构造；(c) 用「两翼平面的交线」求褶皱轴。真实褶皱只在有限范围内近似柱状 —— 这就是答案里必须注明产状测自图幅哪一部分的原因。

### 2. 褶皱的基本几何要素

handout 图注给出的要素名（图已丢失，此处按标准定义补全）：

| 要素 | 英文 | 定义 |
|---|---|---|
| 轴面 | axial plane / axial surface | 含褶皱轴、且在剖面上连接相邻各层**最大曲率点**的面 |
| 枢纽 | hinge | 单一层面上曲率最大的那条线 |
| 翼 | limb | 相邻两个枢纽之间曲率较小（近于平面）的部分 |
| 褶皱轴 | fold axis | 生成柱状褶皱面的那条直线；方向 = 枢纽线方向 |
| 剖面面 | profile plane | **垂直于褶皱轴**的平面；只有在这个面上量的层间角才是真值 |
| 层间角 | interlimb angle | 两翼在剖面面上的夹角 |
| 轴迹 | axial trace | 📎 轴面与地形面（图面）的交线 —— handout 未定义，但这是图上要画的东西 |
| 倾伏 | plunge | 褶皱轴在铅垂面内相对水平面的下倾角，记作 `倾伏角/倾伏向`，如 `4/180` |

handout 关于轴面有一句**必须记住的严格表述**：

> "Strictly, the axial plane is the plane which contains the fold axis and the line in the profile plane which joins the points of maximum curvature on adjacent beds. **If the beds on each limb are of the same thickness the axial plane bisects the interlimb angle; if the beds on each limb are of different thickness, it does not.**"

即：**「轴面 = 层间角平分面（bisector）」只在两翼等厚时成立**。图注里也单独写了 `bisector = axial plane` 与 `bisector / axial plane` 两处，说明讲义反复强调这个条件。`SectSoln` 的答案写 `Axial plane: 150/V (= bisector)` —— 它明确标注「(= bisector)」，就是在声明「本题两翼等厚，所以我用平分面来求轴面」。

### 3. 背形/向形 vs 背斜/向斜 —— handout 原文（本周最爱考的定义）

> "A folded surface which **closes downwards** is referred to as a **synform**; one which **closes upwards** is an **antiform**. A fold in which the **youngest rocks are in the core** is referred to as a **syncline**; one in which the **oldest rocks are in the core** is an **anticline**."

拆开成两套**互相独立**的判据：

- **形态判据（几何）**：闭合方向朝上 = **背形 antiform**；朝下 = **向形 synform**。只看弯曲方向，不需要知道年代。
- **年代判据（地层）**：核部（core）是最老岩层 = **背斜 anticline**；核部是最新岩层 = **向斜 syncline**。只看年代，不需要知道弯曲方向。

于是有四种组合，handout 图注里正列出这四个词：`anticlinal antiform`（正常背斜）、`synclinal synform`（正常向斜）、`anticlinal synform`、`synclinal antiform`。后两者出现在**地层已被倒转**的地区 —— 原背斜被后期构造整体翻转，核部仍最老（anticline），形态却向下闭合（synform）。

📎 背景补充（做题口诀）：**能确定地层新老顺序（younging direction）时才可用 anticline/syncline；只知形状时只能说 antiform/synform。** 本课图幅题图例通常按 stratigraphic order 给出单位序列（如 `MapSoln` 的 8 个单位），两套词都能用。

### 4. 完整描述一个柱状褶皱需要的四项 —— handout 原文

> 除了规模和基本形态（背形/向形、背斜/向斜）之外，**完整指定**一个柱状褶皱的几何需要四件事：
>
> 1. **褶皱轴的方位**（plunge / plunge direction）
> 2. **轴面的产状**（strike / dip）
> 3. **每一翼的代表性产状**
> 4. **层间角**

这四项就是本周所有题目的**标准答案模板** —— `EgExSoln` 给了 (1)(2)(3)，`SectSoln` 四项全给。答题时按这个清单逐项写，不要漏。

### 5. 三张形容词分级表 —— handout 原文，需要背

**褶皱轴倾伏角（Plunge of fold axis）**

| 范围 | 术语 |
|---|---|
| 0°–10° | non-plunging 不倾伏 |
| 10°–30° | gently-plunging 缓倾伏 |
| 30°–60° | moderately-plunging 中等倾伏 |
| 60°–80° | steeply-plunging 陡倾伏 |
| 80°–90° | vertical 直立 |

**层间角（Interlimb angle）**

| 范围 | 术语 |
|---|---|
| 180°–120° | gentle 平缓 |
| 120°–70° | open 开阔 |
| 70°–30° | close 闭合 |
| 30°–0° | tight 紧闭 |
| 0° | isoclinal 等斜 |

**轴面倾角（Dip of axial plane）**

| 范围 | 术语 |
|---|---|
| 0°–10° | recumbent 平卧 |
| 10°–30° | gently-inclined 缓倾斜 |
| 30°–60° | moderately-inclined 中等倾斜 |
| 60°–80° | steeply-inclined 陡倾斜 |
| 80°–90° | upright 直立 |

用这三张表检查本周答案：`EgEx` 轴 `4/180` → non-plunging；轴面 `000/V` → upright。`FoldEP` 轴 `9/180` → non-plunging（刚好卡在 10° 以内）；轴面 `000/V` → upright。`MapSoln/SectSoln` 轴 `0/150` → non-plunging；轴面 `150/V` → upright；层间角 `140°` → **gentle**。

📎 背景补充：本周三题轴面**全部直立**，是有意的教学梯度 —— 直立轴面意味着两翼倾角相等、轴迹在图上是直线，作图最简单；倾斜轴面（不对称褶皱）要到后面综合题才出现。

### 6. 图面判据：怎么在地质图上认出褶皱

📎 背景补充（handout 未系统给出，但做题必需，从答案的构造反推）：

1. **地层重复的对称性**：沿穿越线出现 `… d c b a b c d …` 的**镜像重复** → 褶皱（断层造成的重复不对称，且会有单位缺失或跳跃）。
2. **核部年代**：镜像中心（core）最老 → 背斜；最新 → 向斜。`FoldEPsoln` 剖面上 `b / a … a / b`，中心是 `a Mudstone`（更老）→ **背斜**。
3. **两翼产状相向或相背**：倾向**相背离**（dip away from the axial trace）= 背形；**相对**（dip towards）= 向形。`EgEx` 232/125、`FoldEP` 261/099、`MapSoln` 240/060 —— **本周三题全是背形/背斜。**
4. **倾伏褶皱的「鼻状」闭合（nose）**：出露带呈 U 形闭合，尖端方向是判断倾伏方向的直接证据（推导见第三节 E）。
5. **等高线相关性检验**：出露带的 V 若**与地形等高线的 V 同步弯折**（河谷处内凹、山脊处外凸），多半是 V 字法则造成的地形假象，不是褶皱。这正是 `Vshaped.md` 存在的理由。

### 7. `Vshaped.md`：V 字形出露图案

原文：

> "A uniformly dipping surface which crops out across a valley can give rise to a V-shaped outcrop pattern in which the V points either upstream or downstream. The direction and sharpness of the V depends upon the dip of the surface…
> Since folding may also produce similarly shaped outcrop patterns, **when locating fold axial traces on maps it is important to pay attention to this topographically produced effect.**"

图注给出的六种情形（图注被 OCR 打散，此处按原文字串重排）：

| 岩层产状 | V 尖指向 | 与地形等高线相比 |
|---|---|---|
| 向上游倾（dip upstream） | **上游** | 比等高线**钝**（blunter） |
| 水平（horizontal） | **上游** | 与等高线**平行** |
| 缓倾向下游（dip gently downstream，倾角 < 河床坡度） | **上游** | 比等高线**尖**（sharper） |
| 倾角 = 河床坡度（dip at stream gradient） | **无 V 形** | 出露沿谷底成直线 |
| 陡倾向下游（dip steeply downstream，倾角 > 河床坡度） | **下游** | — |
| 直立（vertical） | **无 V 形** | 出露为直线，完全不受地形影响 |

（图注中的 `700 500 300 100` 是各示意图的等高线高程标注，不是产状数据。）

📎 背景补充（本质）：V 字法则不必死记 —— 出露线永远出现在「地层等高线高程 = 地形等高线高程」的交点上。直立岩层的地层等高线彼此重合成一条直线，故出露不受地形影响；水平岩层的地层等高线「就是」某条地形等高线，故出露与等高线重合。**本课里 V 字法则的两个用途：(a) 快速目估倾向（`EgExSoln` 图上明写 "approximate dip direction given by veeing"）；(b) 找轴迹前先排除地形造成的 V。**

---

## 三、公式与图表

> 本节是本周笔记的重心。原材料只有答案数字，作图法几乎全部靠反推 —— 以下步骤均为 📎 背景补充，除非注明引自 handout。

### A. 褶皱面上的地层等高线：形态与画法

📎 背景补充：

**为什么褶皱上的地层等高线会折转？** 柱状褶皱面 = 一条直线（褶皱轴）平移生成的曲面。若两翼近似平面，则整个曲面由两块平面拼成。**平面的地层等高线是一组等间距平行直线**，所以：

- **每一翼上，地层等高线仍然是一组等间距平行直线**；
- 两翼各自的等高线方向不同（因为两翼走向不同）；
- **同一高程的两条等高线（一翼一条）必然相交于一点，这个交点就是该高程处的枢纽点**（因为枢纽线同时属于两翼）。

**作图六步：**

1. **描出接触面的出露线**（图上已给的地质界线）。
2. **标出所有交点**：出露线与每一条地形等高线的交点。每个交点是该接触面上一个**已知三维点**（平面位置 + 高程 = 地形等高线的高程）。
3. **同高程连线**：把高程相同的交点连起来。⚠️ 在褶皱上，同一高程的交点通常**多于两个**（每翼至少两个），必须先判断哪些点属于同一翼 —— 用 V 字法则目估的倾向来分组（`EgExSoln` 图上的 "approximate dip direction given by veeing" 就是干这个的）。
4. **每一翼内部，同高程点连成直线**，得到该翼的地层等高线；检查它们是否互相平行、间距是否等距 —— **若不平行/不等距，说明分组错了或该翼不是平面**。
5. **延长两翼的同高程等高线使其相交**，交点即枢纽点。把各高程的枢纽点连起来 → **轴迹（若轴面直立，这是一条直线）**。
6. **读出四项答案**（见 B–E）。

**由地层等高线读倾角（W1–2 已学，此处复用）：**

$$\tan\delta = \frac{\text{CI}}{d}$$

- CI = 地层等高线的高程间隔（= 用到的地形等高线间隔）
- d = 相邻两条地层等高线之间**垂直方向**的图上实距（按比例尺换算成实地距离）

走向 = 地层等高线的方位；倾向 = 指向高程**降低**一侧、且垂直于走向的方向。

**数值校核（用答案反推题目条件）：**

| 题 | 比例尺 / CI | 倾角 | 应有的等高线间距 |
|---|---|---|---|
| `EgEx` | 1000 ft 比例尺，CI ≈ 50 ft | 7° | 50 / tan7° = **407 ft** |
| `FoldEP` | 0–400 m 比例尺，CI = 100 m | 45° | 100 / tan45° = **100 m** |
| `MapSoln` 褶皱翼 | 1:30000，CI = 100 m | 20° | 100 / tan20° = **275 m** ≈ 图上 9.2 mm |
| `MapSoln` 下不整合 | 1:30000，CI = 100 m | 4.8° | 100 / tan4.8° = **1191 m** ≈ 图上 40 mm |

最后一行很说明问题：**下不整合的倾角只有 4.8°，它的地层等高线间距接近图幅宽度的一大截 —— 必须用整幅图上分散的交点来定，不能只用局部两三个点。**

### B. 由两翼产状求褶皱轴：褶皱轴 = 两翼平面的交线

📎 背景补充：这是本周最重要的定量关系，用它可以**完全复现三道题的答案**。

**几何原理**：柱状褶皱两翼都含有褶皱轴，所以褶皱轴 = 两翼平面的交线。

**做法一（图上/立体网）**：把两翼投到赤平网上（W6 内容），两大圆的交点即褶皱轴。

**做法二（视倾角公式，可手算）**：褶皱轴的倾伏角 = **任一翼在含轴迹走向的铅垂面内的视倾角**。视倾角公式：

$$\tan\delta_{\text{app}} = \tan\delta_{\text{true}} \cdot \cos\theta$$

θ = 视倾角所在方向与真倾向之间的夹角。

**做法三（对称褶皱的捷径）**：两翼倾角相等时，轴的**倾伏向 = 两翼倾向的角平分线方向**（取指向下坡的那一支），倾伏角由上式算出。

**三题核校（全部精确复现答案）：**

| 题 | 两翼（走向/倾角+倾向） | 换算成倾向/倾角 | 计算得褶皱轴 | 答案 |
|---|---|---|---|---|
| `EgEx` | 142/7SW、035/7SE | 7/232、7/125 | 平分向 178.5；tan7°·cos52° → **4.2/178.5** | **4/180** ✅ |
| `FoldEP` | 171/45W、009/45E | 45/261、45/099 | 平分向 180；tan45°·cos81° → **8.9/180** | **9/180** ✅ |
| `MapSoln` | 150/20SW、150/20NE | 20/240、20/060 | 两翼走向相同、倾向相反 → 交线水平 → **0/150** | **0/150** ✅ |

注意第三行：**两翼走向完全相同（都是 150）时，褶皱轴必然水平，倾伏向 = 走向**。这是 `MapSoln` 的褶皱不倾伏（non-plunging）的直接证据。

**做法四（由轴迹上的枢纽点直接量倾伏）**：

$$\tan(\text{plunge}) = \frac{\text{CI}}{L}$$

L = 轴迹上相邻两个枢纽点（高程差 CI）之间的图上实距。

核校：`EgEx` 若 CI = 50 ft、plunge = 4°，则 L = 50/tan4° = **715 ft**；`FoldEP` CI = 100 m、plunge = 9°，则 L = 100/tan9° = **631 m**。两者与各自比例尺尺度相符。

### C. 由两翼产状求轴面产状

📎 背景补充：

- 轴面**必含褶皱轴** → 轴面的产状必须与已求出的褶皱轴相容（轴的方位角在轴面内）。
- **两翼倾角相等（对称褶皱）→ 轴面直立**，走向 = 褶皱轴的倾伏向（或其反方向）。
  - `EgEx`：两翼都是 7° → 轴面直立，轴倾伏向 178.5 ≈ 180 → 轴面 **000/V** ✅
  - `FoldEP`：都是 45° → 轴面直立，轴倾伏向 180 → **000/V** ✅
  - `MapSoln`：都是 20° → 轴面直立，走向 150 → **150/V** ✅（答案还特意标 `(= bisector)`）
- **两翼倾角不等 → 轴面倾斜**，其产状 = 层间角的平分面（**且仅在两翼等厚时**，见 handout 原文），一般用赤平网求。
- **另一条独立途径**：如果图上能定出**两条不同层位接触面的轴迹**，把它们在剖面上的枢纽点连起来，得到的就是轴面在剖面上的迹线，直接量其倾角。这条路不依赖「等厚」假设。

### D. 层间角

📎 背景补充：层间角必须在**剖面面（profile plane，垂直于褶皱轴）**内量。对于**轴面直立、两翼倾向相反**的褶皱：

$$\text{interlimb angle} = 180° - \delta_1 - \delta_2$$

核校：`MapSoln` 两翼各 20° → 180 − 20 − 20 = **140°** ✅（答案正是 140°），按 handout 分级表属 **gentle**。
`FoldEP` 两翼各 45° → 180 − 45 − 45 = **90°**，属 **open**（材料未给出此值，为推算）。

若两翼**倾向相同**（有一翼已倒转），则层间角 = 180° − |δ₁ − δ₂| 的补角关系会变，必须画图或用立体网，不能套上式。

### E. 倾伏褶皱的「鼻状」出露：闭合方向怎么读

📎 背景补充（本周最容易记反的一条，此处给出推导而非死记）：

设褶皱轴向南倾伏（如 `EgEx` 4/180、`FoldEP` 9/180），地形近似平坦、高程 z₀。

- **背形**：接触面的**脊线（crest line）**高程沿轴向南**降低**。北端脊线高于 z₀ → 拱顶已被剥蚀，接触面只在两翼出露、两线分得很开；南端脊线低于 z₀ → 整个拱在地下、**不出露**；中间脊线 = z₀ 处两条出露线**汇合闭合**。故 **背形的鼻状尖端指向倾伏方向**，核部老地层向上倾方向敞开。
- **向形**：槽线（trough line）同样向南降低，推理反过来 —— **向形的闭合尖端指向倾伏的反方向**，出露带向倾伏方向敞开。

一句话口诀：**背形「尖」向倾伏；向形「开」向倾伏。**

对本周三题：`EgEx`（背形，4/180）与 `FoldEP`（背形，9/180）在图上都应看到**向南收口的鼻状闭合**；`MapSoln` 的褶皱轴 `0/150` 不倾伏，所以**没有鼻状闭合**，出露带是两组平行条带一直延伸到图幅边界 —— 这也解释了为什么 `SectSoln` 的多个厚度只能写 "min"（单位被图幅边界或不整合截断）。

### F. 剖面构建（`SectSoln` 的做法）

`SectSoln` 图注中的关键信息：`Scale 1 : 30000`、**`vertical = horizontal scale`**、剖面 A（SW）–B（NE）、高程刻度 0–1200 m。

📎 背景补充，剖面构建八步：

1. **选剖面线**：尽量**垂直于褶皱轴**。`MapSoln` 轴 0/150、剖面 A–B 走 SW–NE（约 060）正好垂直 → **该剖面即剖面面（profile plane），翼上倾角即真倾角**，直接按 20° 画。对比 `FoldEPsoln`：剖面 `090/V`、轴 9/180，因轴有 9° 倾伏严格说不是剖面面，翼的视倾角 = arctan(tan45°·cos9°) = **44.6°**，与 45° 差不到 0.5°，可忽略；**倾角越大、剖面越斜，这个差越不能忽略。**
2. **做地形剖面**：剖面线与每条地形等高线的交点 → 投到高程格 → 连成地形线。
3. **投地质界线**：剖面线与每条地质界线的交点 → 投到地形线上，得该接触面的**出露点**。
4. **算视倾角**：$\tan\delta_{\text{app}} = \tan\delta_{\text{true}}\cos\theta$，θ = 剖面走向与真倾向的夹角；垂直走向时视倾角 = 真倾角。
5. **从出露点按视倾角画线**，向下延伸到剖面底，向上用**虚线**补出被剥蚀的拱顶 —— **不画虚线拱顶等于没表现出褶皱，是得分点。**
6. **先画截切面**：两个不整合先画（它们**截断**下伏单位），再画其下的褶皱序列，最后画其上的盖层。
7. **标轴面**：连各接触面的枢纽点 → 剖面上的轴面迹线；`MapSoln` 轴面 150/V、剖面垂直走向 → 在剖面上是一条**铅垂线**。
8. **量厚度**（见 G）。

**垂直夸大（vertical exaggeration, VE）**：`SectSoln` 明写 `vertical = horizontal scale`，即 **VE = 1**。
📎 背景补充：若 VE ≠ 1，图上倾角须换算 $\tan\delta_{\text{drawn}} = \text{VE}\cdot\tan\delta_{\text{app}}$，且厚度、层间角、轴面倾角在图上全部失真、不能直接量。**本课构造剖面一律 VE = 1。**

### G. 由地层等高线求真厚度

`SectSoln` 图注里的三个换算式是直接证据：

- `conglomerate : 99.6 m (= 100 cos 4.8°)`
- `grit : 282 m (= 300 cos 20°)`
- `siltstone : 188 m (= 200 cos 20°)`

📎 背景补充，反推出的公式：

$$t_{\text{true}} = V \cdot \cos\delta$$

- V = **铅垂厚度（vertical thickness）**：在图上某一点，该单位**顶面**的地层等高线高程与**底面**的地层等高线高程之差（即两组地层等高线在图上重合处的高程差）；
- δ = 该单位的倾角；
- t = 垂直于层面量的**真厚度**。

核校：100·cos4.8° = 99.65 ✅；300·cos20° = 281.91 ✅；200·cos20° = 187.94 ✅ —— 三个都与答案完全吻合。

**倒过来用**：`conglomerate` 用的是 cos**4.8°** = 下不整合的倾角 → 说明**砾岩直接覆于下不整合面之上、且产状与不整合面平行**；`grit` 与 `siltstone` 用 cos**20°** → 说明它们属于**不整合之下被褶皱的老序列**（两翼倾角 20°）。这是从一个 cos 的角度值反推地层层序位置的典型手法。

---

## 四、课堂补充

> **本周无 transcript**（EART24001 全门 10 周均无 transcript）。**本段内容全部来自 handout 正文与四份答案图件的图注**，不含课堂口述内容。

### 1. handout 反复强调的两点

- **柱状性假设**：柱状褶皱「在任意平行剖面上形态恒定」是全部作图法的地基。答案里凡是给产状都注明测量范围（见下），本质上是在承认「柱状性只在局部成立」。
- **轴面 ≠ 平分面（除非等厚）**：handout 用整整一段特别声明，并在图注里单列 `bisector` 与 `axial plane` 两个标签。`SectSoln` 写 `Axial plane : 150/V (= bisector)`，**括号里的 "(= bisector)" 就是在向阅卷人交代自己用了哪种方法、并默认了等厚条件**。

### 2. 答案图注透露的评分要点（逐条）

| 证据（图注原文） | 评分要点 |
|---|---|
| `150/20SW = 20/240`、`070/4.8N = 4.8/340`、`150/20NE = 20/060` | **产状必须同时给出两种记法**：走向/倾角+倾向象限（`150/20SW`）与 倾角/倾向（`20/240`）。答案每一个产状都写了等号两边，说明这是要求而非顺手。 |
| `(= 100 cos 4.8°)`、`(= 300 cos 20°)`、`(= 200 cos 20°)` | **换算过程必须写出**，不能只给结果数字。 |
| `~100 m min`、`~200 m min`、`~530 m min`、`364 m min` | **顶面或底面被不整合/图幅边界截断的单位只能给「最小厚度」**，前面加 `~` 与 `min`。写成确定值是错的。 |
| `(NW part of map)`、`(along line of section)`、`(N and NW parts of map)` | **每个产状/厚度都要注明是在图幅哪一部分量的**。因为不整合造成单位横向厚度变化、褶皱造成产状横向变化，不注明位置的数值无意义。 |
| `blue are the strike-lines for the cleaved mudstone/siltstone contact` | **不同接触面的地层等高线要用不同颜色**，并在图例中说明哪种颜色对应哪个接触面。 |
| `vertical = horizontal scale` | 剖面必须**注明是否垂直夸大**。 |
| `approximate dip direction given by veeing`（`EgExSoln`） | **先用 V 字法则目估倾向，再连地层等高线** —— 这是被示范的解题顺序。 |
| `Limbs : Fold axis : Axial plane : Interlimb angle :`（`SectSoln`） | 答案**逐项按 handout 的四要素清单列出**，缺一项扣一项。 |

### 3. 作图约定

📎 背景补充（材料未直接说明，为标准制图规范）：

- **背斜轴迹**：一条实线，两侧各加一个**向外**的箭头（表示两翼倾向相背）；**向斜轴迹**：两侧各加一个**向内**的箭头。
- **倾伏箭头**：在轴迹上沿倾伏方向画一个箭头，箭头旁标倾伏角（如 `9`）。不倾伏的褶皱不画箭头（如 `MapSoln` 的 `0/150`）。
- **倒转翼**：产状符号上加倒转标记（一个反向短钩或半圆），并把倾角数字注明。
- **剖面上的虚线**：地形线以上的构造延伸（被剥蚀部分）一律虚线；地表以下不确定的外推也用虚线。
- **不整合面**：图上与剖面上都用**加粗或波状线**表示，并在图例中单独列出。

---

## 五、Practical 要点

本周四份答案对应四道练习。以下按「问什么 / 给了什么 / 怎么做 / 答案要点」重建。所有**给了什么**的部分都是从答案数值反推的，标 📎。

### 题 1 — `EgExSoln`：STRATUM CONTOURS ON FOLDS (1)，示例题（Example exercise）

**问什么**（题干为材料原文）：

> "By drawing stratum contours on the contact between the mudstone and the grit, determine the geometry of the fold structure shown on the map below.
> (a) Determine the strike/dip of each limb of the fold. Is the fold an antiform or a synform?
> (b) Determine the plunge/plunge direction of the fold axis.
> (c) Determine the strike/dip of the axial plane."

**给了什么**：一幅地形图，等高线高程 600–1000（图注中出现 600、650、700、750、800、850、900、950、1000），**CI = 50**；比例尺条 `0 — 1000 ft`（单位为**英尺**）；图例两个单位：`Sandstone`、`Mudstone`；指北针 N。图上并给了提示 `approximate dip direction given by veeing`。

📎 反推的条件：等高线高程在图两侧对称重复（`…600 650 700 750 800 850 900 / 900 800 850 750 700 650 600…`），是一条 N–S 向的山脊或山谷地形；砂岩/泥岩接触面横切该地形并呈鼻状闭合。

**解法步骤**：

1. 用 **V 字法则**目估两侧接触面的倾向（图上明示的做法）。
2. 标出接触面出露线与各条 50 ft 等高线的全部交点。
3. 按 V 字法则得到的倾向把交点**分成东西两组（两翼）**。
4. 每组内同高程点连直线 → 得两组各自平行等距的地层等高线；检查间距应约 50/tan7° ≈ **407 ft**。
5. 由每组等高线的方位与间距读出走向/倾角。
6. 延长两组同高程线求交 → 各高程的枢纽点 → 连成轴迹（应为一条近 N–S 的直线，相邻枢纽点间距约 50/tan4° ≈ **715 ft**）。
7. 两翼倾角相等（都是 7°）→ 轴面直立，走向 = 轴的倾伏向。

**答案要点**（材料原文）：

- **Limbs：`142/7SW` 和 `035/7SE`**（换算：7/232 与 7/125）
- **Fold axis：`4/180`**
- **Axial plane：`000/V`**
- 📎 (a) 的第二问：两翼倾向相背离（232 与 125 夹着 180 的轴迹）→ **antiform 背形**；若配合图例的新老关系（Sandstone/Mudstone），核部为老者即 anticline。
- 📎 分级描述：non-plunging，upright axial plane。
- 📎 数值可自洽验证：两平面 7/232 与 7/125 的交线 = **4.2/178.5**，即答案的 4/180。

### 题 2 — `FoldEPsoln`：FOLDING QUESTION（褶皱额外练习题）

📎 `EP` 应为 **Extra Practice**（unit spec 提到「Accompanying all classes there will be extra practice exercises」）。

**给了什么**：地形图，等高线 `100–800 m`，**CI = 100 m**，比例尺 `0 — 200 — 400 m`；两个单位 `a Mudstone`、`b Sandstone`（a 在下、更老）；图上标注四个点 **A、B、C、D**；指北针 N。等高线序列 `400 500 600 700 800 / 800 700 600 500 400 300` 显示一条山脊。

📎 材料未说明 A、B 的用途 —— 答案只给出沿 **C–D** 的剖面，A–B 可能是另一条剖面线或两个已知露头点，**材料未说明**。

**问什么**（由答案反推）：求褶皱的轴面、倾伏、两翼产状，并沿 **C–D** 作铅垂剖面。

**解法步骤**：同题 1 第 1–7 步求出两翼与轴，随后作剖面：

1. 剖面线 **C–D 走向 090（东西向）、铅垂**（答案注明 `090/V`）。
2. 地形剖面刻度取 100–700 m（答案两侧标了 `700 / 600 / 500 / 400 / 300 / 200 / 100`）。
3. 两翼视倾角 = arctan(tan45°·cos9°) = **44.6°**，实际按 **45°** 画。
4. 剖面上单位由核部向外为 `a`（泥岩，老）→ `b`（砂岩，新），**左右对称各出现一次** → 背斜/背形。

**答案要点**（材料原文）：

- **两翼：`171/45 W` 与 `009/45 E`**（换算：45/261 与 45/099）
- **轴面：`000/V`**
- **褶皱倾伏：`9/180`**
- 剖面沿 C–D，注明 `090/V`
- 📎 校核：45/261 与 45/099 的交线 = **8.9/180** ✅
- 📎 层间角 = 180 − 45 − 45 = **90°**，属 open；轴面 upright；轴 non-plunging（9° < 10°，刚好卡线）。
- 📎 因为背形向 180 倾伏，图上老单位 `a` 的出露应呈**向南收口的鼻状闭合**。

### 题 3 — `MapSoln`：图幅题（含双不整合与褶皱）

**给了什么**（图注证据）：

- **比例尺 1:30000**，等高线**单位为米**，图上高程 200–1100 m，**CI = 100 m**。
- **8 个单位，按地层顺序列出**：`dolomitic limestone`（白云质灰岩）、`limestone`（灰岩）、`sandstone`（砂岩）、`conglomerate`（砾岩）、`mudstone`（泥岩）、`grit`（粗砂岩）、`siltstone`（粉砂岩）、`cleaved mudstone`（具劈理泥岩）。
- **两个不整合**：图上标 `u/c u/c`，答案给出 `upper unconformity horizontal`（上不整合水平）与 `lower unconformity : 070/4.8N = 4.8/340`（下不整合走向 070、向北倾 4.8°）。
- 图上注出的产状：`150/20SW = 20/240`、`150/20NE = 20/060`，以及 `below u/c : 150/20SW = 20/240`。
- 剖面线端点 **A（SW）–B（NE）**。
- 图注说明：**蓝色是 `cleaved mudstone / siltstone` 接触面的地层等高线**；另有一串地层等高线高程标注 `+100 +100 +500 +200 0`（📎 出现 0 与低值，说明部分地层等高线要**外推到海平面附近甚至图幅之外**）。

**问什么**（反推）：(a) 用地层等高线补全/解释出露图案；(b) 求两个不整合面的产状；(c) 求不整合之下老序列中褶皱的几何；(d) 沿 A–B 作剖面（→ 题 4）。

**解法步骤**：

1. **先分层**：按劈理（cleaved）与产状把地层分成三套 —— 上不整合之上的**水平盖层**、两不整合之间的**缓倾（≈4.8°）中间层**、下不整合之下的**被褶皱老序列**（倾角 20°）。
2. **上不整合**：产状水平 → 它的出露线**与地形等高线完全重合**（V 字法则「水平岩层」情形）；只需读出它所在的高程即可。
3. **下不整合**：用其出露线与地形等高线的交点画地层等高线；因倾角仅 4.8°，等高线间距达 **1191 m**（图上 40 mm），必须用横跨全图的交点定向。得 `070/4.8N = 4.8/340`。
4. **老序列的褶皱**：分别在图幅 N 与 NW 部分对 `cleaved mudstone/siltstone` 接触面（蓝线）画地层等高线，得两翼 `150/20SW` 与 `150/20NE`；两翼走向相同、倾向相反 → 轴水平。
5. **注意角度不整合关系**：老序列 20° 倾、下不整合 4.8° 倾、上不整合水平 —— **两次角度不整合（angular unconformity）**，说明至少两期变形/剥蚀事件。

**答案要点**（材料原文）：

- `lower unconformity : 070/4.8N = 4.8/340`
- `upper unconformity horizontal`
- 老序列两翼：`150/20SW = 20/240`、`150/20NE = 20/060`
- 蓝色地层等高线 = `cleaved mudstone / siltstone` 接触面
- 📎 事件序列（由此可写出）：老序列沉积 → **褶皱（形成劈理，故 cleaved mudstone）** → 剥蚀 → 下不整合 → 中间层沉积 → 轻微掀斜（4.8°）+ 剥蚀 → 上不整合 → 水平盖层沉积。

### 题 4 — `SectSoln`：沿 A–B 的剖面 + 完整褶皱描述 + 各单位厚度

**给了什么**：`Scale 1 : 30000`，**`vertical = horizontal scale`**（VE = 1），高程刻度 `0 … 1200 m`，**A 在 SW、B 在 NE**，单位以 `a`–`h` 编号（a = dolomitic limestone … h = cleaved mudstone，与 `MapSoln` 图例同序）。

**答案要点**（材料原文，四要素齐全）：

| 项目 | 值 | 注 |
|---|---|---|
| **Limbs 两翼** | `150/20SW` 和 `150/20NE` | (N and NW parts of map) |
| **Fold axis 褶皱轴** | `0/150` | 水平，non-plunging |
| **Axial plane 轴面** | `150/V` | **(= bisector)**，upright |
| **Interlimb angle 层间角** | `140°` | = 180 − 20 − 20，属 **gentle** |

**各单位厚度**（材料原文，括号内为答案给出的换算式与测量位置）：

| 代号 | 单位 | 厚度 | 换算 / 备注 |
|---|---|---|---|
| a | dolomitic limestone 白云质灰岩 | ~100 m **min** | 顶被剥蚀 |
| b | limestone 灰岩 | 100 m | 确值 |
| c | sandstone 砂岩 | ~200 m **min** | |
| d | conglomerate 砾岩 | **99.6 m** | = 100 · cos 4.8° → 与**下不整合平行**，位于其上 |
| e | mudstone 泥岩 | ~530 m **min** | |
| f | grit 粗砂岩 | **282 m** | = 300 · cos 20° → 属**被褶皱的老序列** |
| g | siltstone 粉砂岩 | **188 m** | = 200 · cos 20° → 老序列 |
| h | cleaved mudstone 具劈理泥岩 | 364 m **min** | 底未见，老序列最下 |

（答案另标注 `(NW part of map)` / `(along line of section)` 说明各厚度的测量位置。）

**剖面画法**：见第三节 F 的八步。要点：A–B 走向约 060，**垂直于 0/150 的褶皱轴**，故该剖面即剖面面，**两翼按真倾角 20° 直接画**；轴面 150/V 在剖面上是一条**铅垂线**；被剥蚀的背形拱顶用**虚线**补出。

📎 需要坦白的不确定：从图注无法百分之百确定 `mudstone (e)` 究竟位于下不整合之上还是之下（它的厚度未给 cos 换算式）。可确定的是 `d conglomerate` 紧邻下不整合之上（cos 4.8°）、`f grit` 与 `g siltstone` 属 20° 的褶皱老序列（cos 20°）。**其余分界材料未说明。**

---

## 六、易错点 / 重点难点

1. **背斜/向斜与背形/向形混用。** 前者是**年代**判据（核部最老/最新），后者是**形态**判据（向上/向下闭合）。无年代信息时**只能**说 antiform/synform。`EgExSoln` 原文问的正是 "Is the fold an antiform or a synform?" —— 用词刻意，答成 anticline 就答错了题。

2. **轴面直接写成层间角平分面。** handout 明说只有**两翼等厚**时才成立。要么核实等厚，要么像 `SectSoln` 那样写明 `(= bisector)` 声明假设。

3. **把出露带的 V 当成褶皱闭合。** 均匀倾斜岩层横穿河谷同样产生 V。判据是「V 是否随地形等高线同步弯折」。定轴迹前必须先排除地形效应。

4. **轴迹画成直线而忽略倾伏与轴面倾角的影响。** 轴面**直立**时轴迹在图上确是直线（本周三题都是）；轴面**倾斜**时轴迹本身也服从 V 字法则，**会随地形弯折**。倾伏影响的不是轴迹直/曲，而是**出露带是否收口成鼻状** —— 两件事不要混。

5. **鼻状闭合方向记反。** 记推导而非结论：**背形尖端指向倾伏方向；向形尖端指向倾伏的反方向。**

6. **剖面上翼部倾角未按视倾角换算。** 只有剖面**垂直于走向**时视倾角 = 真倾角，否则 tan δ_app = tan δ_true · cos θ。`FoldEP` 的 C–D 剖面只差 0.4°（可忽略），但陡翼或斜交剖面会差好几度，是常见扣分点。

7. **忘记垂直夸大。** VE ≠ 1 时 tan δ_drawn = VE · tan δ_app，且厚度与层间角在图上失真。`SectSoln` 特意注明 `vertical = horizontal scale`。

8. **铅垂厚度冒充真厚度。** t = V · cos δ。20° 已差 6%（300 → 282 m），45° 差 29%。答案三处换算式全写了 cos。

9. **顶/底被截断的单位写成确定厚度**（必须写 `~… m min`）；**产状/厚度不注明测量位置**（答案每项都带 `(NW part of map)` 之类限定语）。

10. **同高程点连线时把两翼的点连到一起。** 画褶皱地层等高线最常见的失败，结果是一堆互不平行、间距不等的「等高线」。解法：先用 V 字法则分翼。

11. **倒转翼（overturned limb）判读。** 倒转翼地层顺序反转，两翼可能**倾向相同**，此时层间角不能套 180−δ₁−δ₂，且必须用倒转符号标注。本周未涉及，综合题会考。

---

## 七、本周术语表

| 中文 | English | 说明 |
|---|---|---|
| 柱状褶皱 | cylindrical fold | 由一条直线保持平行平移生成的褶皱面；平行剖面上形态恒定 |
| 非柱状褶皱 | non-cylindrical fold | 不满足上述条件；本周方法不适用 |
| 褶皱轴 | fold axis | 生成柱状褶皱面的直线；方位记作 倾伏角/倾伏向 |
| 枢纽 | hinge | 层面上曲率最大处的线 |
| 翼 | limb | 两枢纽之间近于平面的部分 |
| 轴面 / 轴（曲）面 | axial plane / axial surface | 含褶皱轴与各层最大曲率点连线的面 |
| 轴迹 | axial trace | 轴面与图面（地形面）的交线 |
| 剖面面 | profile plane | 垂直于褶皱轴的平面；量层间角的唯一正确平面 |
| 层间角 | interlimb angle | 两翼在剖面面内的夹角 |
| 平分面 | bisector | 层间角的平分面；仅两翼等厚时 = 轴面 |
| 倾伏 / 倾伏角 | plunge | 褶皱轴相对水平面的下倾角 |
| 倾伏向 | plunge direction | 倾伏的方位角 |
| 背形 | antiform | 向**上**闭合的褶皱（形态判据） |
| 向形 | synform | 向**下**闭合的褶皱（形态判据） |
| 背斜 | anticline | 核部为**最老**岩层（年代判据） |
| 向斜 | syncline | 核部为**最新**岩层（年代判据） |
| 背斜背形 | anticlinal antiform | 正常直立背斜 |
| 向斜背形 | synclinal antiform | 地层已倒转的情形 |
| 核部 | core | 褶皱内侧被两翼包围的部分 |
| 脊线 / 槽线 | crest line / trough line | 层面上的最高/最低线 |
| 地层等高线 / 走向线 | stratum contour / strike line | 地质面上等高程点的连线 |
| V 字形出露 | V-shaped outcrop pattern | 倾斜面横穿河谷造成的出露 V 形 |
| 上游 / 下游 | upstream / downstream | V 字法则的参照方向 |
| 河床坡度 | stream gradient | 岩层倾角与之相等时无 V 形 |
| 真倾角 / 视倾角 | true dip / apparent dip | tan δ_app = tan δ_true · cos θ |
| 铅垂厚度 / 真厚度 | vertical thickness / true thickness | t = V · cos δ |
| 最小厚度 | minimum thickness (min) | 顶或底被截断时只能给的下限 |
| 角度不整合 | angular unconformity | 上下产状不一致的不整合 |
| 垂直夸大 | vertical exaggeration (VE) | 剖面纵横比；VE=1 时倾角为真 |
| 劈理 | cleavage | `cleaved mudstone` 中的劈理，指示该单位经历过褶皱变形 |
| 不倾伏 / 缓倾伏 | non-plunging / gently-plunging | 0–10° / 10–30° |
| 平缓 / 开阔 / 闭合 / 紧闭 / 等斜 | gentle / open / close / tight / isoclinal | 层间角分级 |
| 平卧 / 直立（轴面） | recumbent / upright | 轴面倾角 0–10° / 80–90° |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `EgExSoln.md`，题干第一句 | "By drawing stratum contours on the contact between the **mudstone** and the **grit** …" | 题干说接触面是「泥岩与**粗砂岩**（grit）」之间，但同一页的图例只有 `Sandstone` 与 `Mudstone` 两个单位，**没有 grit** | 应为 "the contact between the **mudstone** and the **sandstone**"。推测题干是从 `MapSoln` 那道含 grit 的图幅题复制修改时未改干净（`MapSoln` 的单位表里确有 `grit`） |
| `0-HandoutFold.md`，"BASIC GEOMETRICAL FEATURES OF A FOLD" 下的图注块 | "axial plane<br>**synform ; one which closes upwards is an**<br>syncline<br>anticlinal synclinal<br>synform antiform<br>fold limb<br>fold hinge" | 图注中混入了下方正文的半句话（"synform ; one which closes upwards is an"），且 `anticlinal / synclinal` 与 `synform / antiform` 的配对被打乱 | PDF→md 转换时的**文本层串行**问题，非原讲义错误。正确配对为 `anticlinal antiform`、`synclinal synform`（及倒转时的 `anticlinal synform`、`synclinal antiform`）。原图已丢失，需时请回看 PDF 图 |
| `Vshaped.md`，图注块 | "Beds dip **700** V points upstream<br>upstream **500300** blunter than contours<br>**100** …" | 六个示意图的**等高线高程标注（700/500/300/100）**被 OCR 混入说明文字，读起来像产状数据 | 700/500/300/100 是**地形等高线高程**，不是倾角。正确读法见本笔记第二节第 7 小节的重排表 |
| `SectSoln.md`，图注块 | "Limbs : Fold axis : Axial plane : Interlimb angle :" 与其数值 `150/20SW and 150/20NE`、`0/150`、`150/V (= bisector)`、`140°` 分列在文本块的不同位置；八个单位的厚度值与代号 a–h 亦被打散 | PDF 表格的**行列被拆开重排**，标签与数值在 md 中不相邻 | 已在本笔记第五节题 4 中按原表配对重建；数值经 cos 换算校验全部自洽（100cos4.8=99.65、300cos20=281.91、200cos20=187.94） |
| `(EART24001) Geological Maps.md`，"Syllabus" 编号列表 | "1. Strike-line refresher … 2. Strike-line consolidation … **3. Strike-lines on folds … 4. Strike-lines on faults** … 6. Stereonets refresher" | 该列表只有 6 项，且**漏掉了不整合那一次实习**（周文件夹 Week 3 是 unconformities），导致编号自第 3 项起与周文件夹错位一位；对 10 周的课也明显不全 | 以**周文件夹**为准：W1–2 走向线、W3 不整合、**W4 褶皱**、W5 断层、W6–7 赤平投影、W8 侵入体与事件序列、W9–10 综合。unit spec 的 syllabus 列表应视为不完整摘要 |
