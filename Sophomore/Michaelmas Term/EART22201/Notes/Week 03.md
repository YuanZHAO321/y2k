# EART22201 Igneous Minerals and Processes — Week 03 学习笔记

## 一、本周主题

**本周主题：造岩矿物导论——硅酸盐的晶体化学与主要造岩矿物的光性识别（An introduction to the rock-forming minerals）。**

判定依据（三处互相印证，全部来自材料本身，不依赖文件名）：

1. `W3 notes.md` 首页标题原文即为 "**An introduction to the rock-forming minerals**"，并标注 "**Lesson 3**"，授课人 margaret.hartley@manchester.ac.uk；
2. `Practical 3 solutions.md` 的大标题与讲义完全同名："**Practical 3: An introduction to the rock-forming minerals**"；
3. 20-Oct 课堂转写全程在虚拟显微镜上逐一走过 olivine → cpx → opx → hornblende → biotite/muscovite → quartz → plagioclase → alkali feldspar，开场原话是"The big takeaway... is this **silicate mineral group**... the silica tetrahedron being the building block of all silicate minerals"。

本周内容**明确分成两半**，复习时要分开对待：

- **上半（异步视频 / 讲义 1.1–1.4）**：晶体化学理论。阳离子—阴离子与配位多面体 → [SiO₄]⁴⁻ 四面体 → 硅酸盐矿物族及其结构 → 类质同象（isomorphism）与同质多象（polymorphism）。
- **下半（讲义矿物图鉴 + 20-Oct 课堂实操）**：把上半的结构知识落到**九种必须会认的造岩矿物**上——olivine、garnet、augite（cpx）、chrome diopside、orthopyroxene、hornblende、biotite/phlogopite、muscovite、alkali feldspar、plagioclase、quartz。每一种都给出"晶体化学 → 光性 → 与谁易混、怎么区分"。

**在全课骨架中的位置。** 本课的骨架是：**硅酸盐矿物的晶体化学与偏光显微镜光性 → 相图与地球化学数据 → 解释岩浆的生成、分异与构造背景**。Week 03 正是**第一块的核心与收口**：

- **承 Week 01**（`W1 notes.md` 标题 "Symmetry and the seven crystal systems"）：本周反复用到晶系。opx 属斜方晶系（orthorhombic）→ 平行消光；cpx 属单斜晶系（monoclinic）→ 斜消光；garnet 属等轴晶系（cubic）→ 各向同性、永远全消光；sanidine/orthoclase 单斜、microcline/albite 三斜。**晶系是本周所有光性结论的物理源头。**
- **承 Week 02**（`W2 notes.md` 标题 "Optics and mineralogy"，含 4.2 Cleavage and twinning）：本周用的全部术语——relief、pleochroism、cleavage、extinction、interference colour——都是上周建立的。转写原话："What is pleochroism? Just remind yourself what that is from last week... This will supplement what we did last week."
- **启 Week 04**（`W4 notes.md` 标题 "Igneous processes: Crystallization"）：转写与 Practical 3 都两次预告"We will discuss textures, and order of crystallization, in much more detail **next week**"。本周 Practical 已经先用 poikilitic 结构做了结晶顺序判断，是下周的伏笔。
- **启 Week 06**：讲义斜长石页原文 "Measuring plagioclase composition in a thin section: see **Week 6** and Practical Reference Handout"——用消光角定 An 值的 Michel-Lévy 法留到第 6 周。
- **横向对接 EART26201 地球化学原理**：讲义在 5 处显式挂钩——阳离子/阴离子与配位见其 Lecture 1；橄榄石相图、SiO₂ 同质多象见其 Lecture 3；辉石出溶、碱性长石出溶见其 Lecture 4。转写也说："those of you who are doing principles of geochemistry will talk about this either this week or next week."（EART26201 的 W03 讲热力学与相图原理、W04 讲 An–Di 共结 / Ab–Or 溶线出溶 / Di–En 辉石 / Fo–Qz 包晶——正好与本周的固溶体、出溶、包晶矿物一一对上。）

📎 背景补充：本周是**全课"能不能看薄片"的分水岭**。第 12 周 30% 权重的 practical test 考的就是 ILO 2/3/4/5/9（显微镜鉴定、光性—晶体化学关联、分类、解释成因、素描）。转写末尾老师明说薄片技术素描"will be one of the skills that I'll look for in the practical at the end of the semester"。本周的笔记本身就是考试可带入的 Reference Handout 批注的原始素材。

---

## 二、核心概念

### 1. 阳离子、阴离子与配位多面体（cations, anions and co-ordination polyhedra）

**为什么先讲这个？** 因为矿物结构不是随便堆的：**大离子和小离子谁能挤进哪个位置，由半径比决定**；而哪些阳离子能进哪个位置，又直接决定了固溶体、出溶、颜色和光性。

- 火成岩石学最重要的元素（讲义原文列举）：**O、Si、Mg、Fe**。
- **中性原子 vs 离子的半径完全不同**。讲义给出（单位 Å）：中性 Na⁰ 1.86、Ca⁰ 1.97、Al⁰ 1.46、Si⁰ 1.18、Fe⁰ 1.23、O⁰ 0.73、F⁰ 0.72；成离子后 Na⁺ 1.02、Ca²⁺ 1.00、Al³⁺ 0.39、Si⁴⁺ 0.26、Fe²⁺ 0.74、Fe³⁺ 0.64；阴离子 O²⁻ 1.40、F⁻ 1.33。
  - 规律：**失电子（阳离子）→ 显著变小；得电子（阴离子）→ 显著变大**。Na 从 1.86 缩到 1.02，O 从 0.73 涨到 1.40。
  - 同一元素**价态越高越小**：Fe²⁺ 0.74 > Fe³⁺ 0.64。这在解释 Fe³⁺ 进八面体、Fe²⁺ 占 M 位时有用。

📎 背景补充：讲义把这一整套数值统称 "atomic radii"，严格说带电物种应称**离子半径（ionic radii）**。另外离子半径**随配位数变化**——同一 Na⁺ 在六配位是 1.02 Å，在八/九配位可达 1.24–1.39 Å。这正是后面碱性长石那一页给出 "Na⁺ 0.132 nm、K⁺ 0.155 nm"（即 1.32 Å、1.55 Å）却与前表 Na⁺ 1.02 Å 不一致的原因：长石中的碱金属位是**大配位数**位置。不是矛盾，是配位数不同。

- **"太小 / 刚好 / 太大"（too small / just right / too large）**：讲义用两页图演示同一个阴离子笼子里塞不同大小的阳离子。阳离子太小 → 在笼中"晃荡"、静电上不稳定，会跌落到更低配位；太大 → 撑不进去，只能进更高配位的大位。

**配位多面体表（讲义原表，半径比 = 阳离子半径 / 阴离子半径）：**

| 半径比 | 阳离子配位方式 | 配位数 | 多面体几何 |
|---|---|---|---|
| 0.16 – 0.23 | 3 个阴离子位于三角形顶点 | 3 | 平面三角形 triangle |
| 0.23 – 0.41 | 4 个阴离子位于四面体顶点 | 4 | 四面体 tetrahedron |
| 0.41 – 0.73 | 6 个阴离子位于八面体顶点 | 6 | 八面体 octahedron |
| 0.73 – 1.0 | 8 个阴离子位于立方体顶点 | 8 | 立方体 cube |
| > 1.0 | 12 个阴离子位于立方八面体顶点 | 12 | 立方八面体 cuboctahedron |

用法：Si⁴⁺/O²⁻ → 四配位（四面体）；Mg²⁺、Fe²⁺、Al³⁺ 通常六配位（八面体）；Ca²⁺、Na⁺ 常八配位；K⁺ 常 8–12 配位。**记住这条链：半径比 → 配位数 → 该阳离子只能进结构中的哪种空位 → 哪些元素可以互相替换。**

### 2. [SiO₄]⁴⁻ 四面体：一切硅酸盐的积木

- 讲义给出：晶体中 Si⁴⁺ 半径 ≈ **0.4 Å**，O²⁻ ≈ **1.4 Å**，半径比 ≈ **0.3** → 落在 0.23–0.41 区间 → **四配位四面体**。
- 电荷：1 个 Si⁴⁺（+4）+ 4 个 O²⁻（−8）= **净 −4**，故写作 [SiO₄]⁴⁻。**这 −4 的剩余电荷必须由外来阳离子（Mg²⁺、Fe²⁺、Ca²⁺、Na⁺、K⁺…）或由四面体之间共用氧来中和**——这正是硅酸盐分类的物理基础。
- 转写强调的一句话："the silica tetrahedron being the building block of all silicate minerals and how those tetrahedra form chains or rings or sheets within a mineral structure is an important aspect of the mineral's crystallography **that also gets expressed in its physical and its optical properties**."——**聚合方式 → 解理、习性、双折射率**，这是本周的中心逻辑。

### 3. 硅酸盐矿物族与聚合度（silicate mineral groups）

分类唯一的判据是：**每个 [SiO₄] 单元与相邻四面体共用几个氧（shared oxygens）**。共用越多，硅氧骨架越"自给自足"，需要的外来阳离子越少，矿物越"长英质"。

| 矿物族 | 通式 | 每 [SiO₄] 共用氧数 | 四面体如何排列 | 实例 |
|---|---|---|---|---|
| 岛状硅酸盐 orthosilicates (island silicates) | [SiO₄]⁴⁻ | 0 | 孤立四面体，全靠阳离子连接 | olivine 橄榄石、garnet 石榴子石 |
| 双岛状 double-island silicates（对硅） | [Si₂O₇]⁶⁻ | 1 | 两个四面体共一个角氧 | epidote 绿帘石、zoisite 黝帘石 |
| 环状 ring silicates | [Si₃O₉]⁶⁻ | 2 | 首尾相接成环 | beryl 绿柱石、cordierite 堇青石 |
| 单链 single chain silicates | [Si₂O₆]⁴⁻ | 2 | 一维无限单链 | pyroxenes 辉石 |
| 双链 double chain silicates | [Si₄O₁₁]⁶⁻ | 2 和 3（交替） | 两条单链侧向并联 | amphiboles 角闪石 |
| 层状 sheet silicates | [Si₄O₁₀]⁴⁻ | 3 | 二维无限片 | serpentine、chlorite、micas、clay minerals |
| 架状 framework silicates | [AlSi₃O₈]⁻ / [SiO₂] | 4 | 三维全共角 | feldspars 长石、quartz 石英 |

**必须理解的三条推论：**

1. **共用氧越多 → 剩余负电荷越少 → 需要的金属阳离子越少。** 岛状每个 Si 带 −4，必须配 2 个 M²⁺（如 Mg₂SiO₄）；架状共用 4 个氧后净电荷为 0（SiO₂ 石英完全不需要阳离子）。所以**超镁铁质岩富岛状硅酸盐（橄榄石），长英质岩富架状硅酸盐（长石+石英）**——这是本课后半"岩浆分异"的矿物学根子。
2. **架状里长石为什么还带电荷？** 因为 Al³⁺ 替换了部分四面体位的 Si⁴⁺，每替换一个就产生 −1，需要一个碱金属/碱土金属来补偿。albite NaAlSi₃O₈ 的 Al:Si = 1:3（补 1 个 Na⁺）；anorthite CaAl₂Si₂O₈ 的 Al:Si = 2:2（补 1 个 Ca²⁺）。
3. **解理方向由聚合方式决定**（本周最重要的"结构→可观察性质"链条）：
   - 单链辉石：链间键弱，解理沿链切开，链的横截面近方形 → **两组解理约 90°**（真值 87°/93°）。
   - 双链角闪石：链宽一倍，解理绕过更宽的"I 型梁"走 → **两组解理约 60°**（真值 56°/124°）。
   - 层状云母：层间只靠 K⁺ 维系，极弱 → **一组极完全底面解理**。
   - 岛状橄榄石：无优势弱面 → 基本无解理（讲义写"cleavages at 90°, rarely visible"），代之以**弯曲裂纹**。
   - 石榴子石：等轴、键各向近同性 → **无解理**，只有裂纹。

**"I 型梁（I-beam）"模型（讲义配图，必须会画）：** 把辉石的单链画成侧视图，两排四面体尖端相对、中间夹一层 M 阳离子八面体，形状像工字钢的横截面 → 单链 = 单个 I-beam；角闪石 = **双 I-beam**（double I-beam），因此横截面更宽，解理角变成 60°。**cpx 单胞 = 两套堆叠的 I-beam；opx 单胞 = 四套堆叠的 I-beam**（讲义原文）——这就是二者化学几乎相同、对称性与单胞大小不同的原因。

**T–O–T 层模型（云母）：** T = 硅氧四面体片（tetrahedral sheet），O = 八面体阳离子片（octahedral sheet）。云母 = **T–O–T** 三明治，三明治之间夹一层大阳离子（K⁺）。讲义原文："Micas and clay minerals are made by stacking T and O layers in different orders and combinations, with or without an extra layer of cations behind the T sheets."——不同的堆垛顺序就生成蛇纹石、绿泥石、云母、黏土矿物。**层间 K⁺ 那一层就是解理面。**

**曲轴链（crankshaft chain，长石）：** 讲义原文 "Feldspar framework is made of linked chains of corner-sharing tetrahedra"，侧视像一根来回折的曲轴，端视是四元/八元环。三维互连 → 长石只有两组不太好的解理，薄片里**几乎看不见解理迹**（这是识别长石的重要"负特征"）。

### 4. 类质同象与同质多象（isomorphism / polymorphism）

- **Isomorphism 类质同象**："Same structure, different chemistry"——结构相同、化学不同。例：橄榄石固溶体的全部成分（Fo–Fa）。
- **Polymorphism 同质多象**："Same chemistry, different structure"——化学相同、结构不同。讲义举的例子是水/冰/水蒸气；矿物学上的标准例子是 SiO₂ 的 quartz / tridymite / cristobalite / coesite / stishovite。
- **稳定的多形由 P–T 条件决定**；出现在其稳定 P–T 范围之外的多形称为**亚稳（metastable）**。讲义：地表条件下 quartz 是稳定多形，而 tridymite、cristobalite、coesite、stishovite 有时以亚稳相保存在地表岩石中。

📎 背景补充：讲义举的"水—冰—水蒸气"其实是**物态（相）变化**而非严格意义的同质多象（同质多象指同成分的不同**固相**结构，如冰 Ih / 冰 II / 冰 VII）。作为直觉类比可以，但考试写例子请写 SiO₂ 多形或 Al₂SiO₅ 三态（红柱石/蓝晶石/夕线石）更稳妥。

📎 背景补充：**亚稳保存的物理原因**是动力学而非热力学——高压多形（coesite、stishovite）回到地表后热力学上应转变为 quartz，但低温下原子重排的活化能翻越不了，反应被"冻结"。这正是 EART26201 Lecture 5（动力学与失衡）的内容。

### 5. 造岩矿物逐个过（晶体化学 + 光性 + 成因）

#### (1) 橄榄石 Olivine — (Mg,Fe)₂SiO₄，岛状，斜方晶系

- **结构**：孤立 [SiO₄]⁴⁻ 之间由 **M1、M2 两个阳离子位**连接。讲义原文："The M1 and M2 cation sites have similar sizes but slightly different shapes. **Both sites take M²⁺ cations.**"——**两个位大小接近**，所以 Mg²⁺ 与 Fe²⁺ 可以自由互换。
- **端元与固溶体**：通式 X₂SiO₄；Mg₂SiO₄ = **镁橄榄石 forsterite (Fo)**，Fe₂SiO₄ = **铁橄榄石 fayalite (Fa)**；二者**完全固溶（complete solid solution）**：(Mg,Fe)₂SiO₄。
- **典型成分**：地幔橄榄石 ≈ **Fo₉₂**；多数玄武岩与辉长岩中的橄榄石 **Fo₆₀–Fo₉₀**。
- **产出**：超镁铁质岩（peridotite）、镁铁质岩（basalt、gabbro）。
- **光性（讲义原文 + 转写）**：PPL 无色、**高突起（high relief）**、常见**弯曲裂纹（curved fractures）**、90° 解理极少可见、常**蚀变为蛇纹石 serpentine**；XPL 干涉色**可达高二级**、**平行消光（straight extinction）**。
- **与谁混、怎么分**：与 augite 混。判据（讲义原文）："Distinguish from augite by its **lack of colour**, **straight extinction**, **curving fractures** with common **alteration to serpentine**."

#### (2) 石榴子石 Garnet — (A₃B₂)Si₃O₁₂，岛状，等轴晶系

- **结构与位点**：**A = 大的 M²⁺**（Ca²⁺、Mg²⁺、Fe²⁺、Mn²⁺），占**畸变立方 [8] 配位**；**B = 小的 M³⁺**（Al³⁺、Fe³⁺、Cr³⁺），占**八面体 [6] 配位**。地幔石榴子石 = Mg₃Al₂Si₃O₁₂（**镁铝榴石 pyrope**）。
- 火成岩中主要出现在超镁铁质岩（peridotite）。
- **光性**：PPL 淡粉色、**极高突起（very high relief）**、常见裂纹、**无解理**；XPL **各向同性（isotropic）——永远处于消光**。
- **物理成因**：等轴晶系三个晶轴等价 → 折射率各向同性 → 光通过时不分解为两束 → 加上分析镜后无光透过 → 全黑且旋转载物台不变。
- **易错**：讲义特别提醒 "Distinguish from **vesicles and holes** in the thin section by its high relief and pink colour in PPL"——薄片里的**气孔/空洞在 XPL 下同样全黑**，靠 PPL 的高突起和粉色区分。

#### (3) 辉石 Pyroxenes — (XY)Si₂O₆，单链，cpx 单斜 / opx 斜方

- **结构**：单链 [Si₂O₆]⁴⁻ + 两个阳离子位：
  - **Y = M1（小）**：opx 与 cpx 中通常 Mg²⁺ 或 Fe²⁺；也可为 Mn²⁺、Al³⁺、Fe³⁺。
  - **X = M2（大）**：opx 中通常 Mg²⁺ 或 Fe²⁺；**cpx 中通常 Ca²⁺**；cpx 中还可为 Na⁺。
  - **关键**：**M2 位能否容纳大的 Ca²⁺，是 cpx 与 opx 分家的化学根源**。Ca²⁺ 半径 1.00 Å 远大于 Mg²⁺，塞进 M2 会把结构撑成单斜。
- **主要成员（讲义原文）**：
  - **Augite 普通辉石**：高钙单斜辉石，**玄武岩与辉长岩中极常见**，Ca(Mg,Fe)Si₂O₆。
  - **Pigeonite 易变辉石**：低钙单斜辉石，见于部分辉长岩。
  - **Orthopyroxene 斜方辉石**：(Mg,Fe)Si₂O₆，见于地幔岩，有时见于镁铁质—中性火成岩。
  - **Chrome diopside 铬透辉石**：Ca(Mg,Cr)Si₂O₆，单斜，见于部分地幔岩。
- **光性对照（本周最高频考点）**：

| | Augite (cpx) | Orthopyroxene (opx) |
|---|---|---|
| PPL 颜色 | 通常**淡灰褐**（略带色） | 无色或极淡灰 |
| 突起 | 高 | 中—高 |
| 解理 | 两组 ~90°，常只见一组 | 两组 ~90°，常只见一组 |
| 干涉色 | **可达二级中部**，常见蓝、橙 | **一级**：灰、黄、白 |
| 消光 | **斜消光**，消光角 ~35–45°（转写口述 30–40°） | **平行消光**（相对解理） |
| 双晶 | 有时可见 | 从不出现（Reference Guide） |

- **铬透辉石**：光性与普通辉石几乎相同（高突起、两组 90° 解理、二级中部干涉色、斜消光 35–45°、有时双晶），**唯一决定性判据是手标本与 PPL 下鲜亮的"瓶绿色（bright bottle green）"**——来自 Cr³⁺ 的晶体场吸收。

#### (4) 角闪石 Amphiboles — AB₂C₅Si₈O₂₂(OH)₂，双链，多数单斜

- **位点（讲义原文）**：
  - **A [12]**：Na⁺、K⁺……或**空位 □**；
  - **B [8]**：Ca²⁺、Na⁺、Mg²⁺、Fe²⁺……；
  - **C [6]**：Mg²⁺、Fe²⁺、Al³⁺、Fe³⁺……；
  - **(OH)⁻**，有时被 F⁻ 取代或为空位。
- 讲义结论句："Multiple different cation sites with different sizes means that amphiboles as a mineral group have a **wide range of compositions and solid solutions**."——**位点多 + 尺寸跨度大 = 角闪石族成分极其复杂**，这是它与辉石最本质的化学差别。
- **含 (OH)⁻ 是角闪石的身份证**：这一条在本课后半（构造环境）反复用到。
- **hornblende 普通角闪石**：Ca₂(Mg,Fe)₄Al[Si₇O₂₂](OH)₂（讲义写法，见勘误表第 3 条），单斜。产于中性岩（andesite、diorite）与长英质岩（granite、granodiorite、rhyolite、dacite）。
- **光性**：PPL 中—高突起、**颜色显著（褐或绿）**、**强多色性**、**两组解理约 60°**、火山岩中常有**暗色反应边（reaction rim）**；XPL 干涉色可达二级中部、伸长切面**斜消光，消光角随成分变化，通常 ~15–25°**（转写 15–20°，Practical 实测 ~18°）、有时双晶。
- **区分**：与辉石分——**强颜色/多色性、60° 解理、~20° 消光角**（辉石 90°、~35–45°）；与黑云母分——**两组解理 + 斜消光**（黑云母一组解理 + 平行但斑驳消光）。

#### (5) 云母 Micas — AB₂₋₃Si₄O₁₀(OH,F)₂，层状，单斜或三斜

- **黑云母 Biotite（及金云母 phlogopite）**：K₂(Mg,Fe)₆[Al₂Si₆O₂₀](OH)₄，单斜（近六方）。结构自下而上：**硅氧四面体层（含部分 Si⁴⁺↔Al³⁺ 替换）→ M²⁺ 层（Mg²⁺、Fe²⁺）→ 四面体层 → K⁺ 层**；**K⁺ 层即解理面**。产于中性岩（andesite、diorite）与长英质岩；**phlogopite 见于地幔岩（lherzolite）**。
- **黑云母光性**：PPL 中等突起、**强多色性：深褐 ↔ 麦秆黄**、**一组极完全解理**、花岗岩中常见**多色晕（pleochroic haloes）**、可蚀变为绿泥石 chlorite；XPL 干涉色可达三级中部（淡粉、淡绿）、**平行但"斑驳"消光（straight, speckled extinction）**。
- **白云母 Muscovite**：K₂Al₄[Al₂Si₆O₂₀](OH,F)₄（讲义写作 K₄Al₄…，见勘误表第 2 条），单斜。结构与黑云母同型，只是**八面体层由 Al³⁺ 取代 Mg²⁺/Fe²⁺**（二八面体 vs 三八面体）。产于**S 型花岗岩与花岗闪长岩**。
- **白云母光性**：中等突起、**无色**、一组极完全解理、干涉色可达三级下部（常见亮蓝或亮橙）、平行消光。
- **黑白云母互判**：转写原话——"I tell muscovite and biotite apart **primarily by their colour**: one's intensely coloured and pleochroic, one is colourless."

📎 背景补充：黑云母是**三八面体云母（trioctahedral）**——八面体位全被 M²⁺ 占满（3 个）；白云母是**二八面体云母（dioctahedral）**——因为 Al³⁺ 电荷高，只需占 3 个位中的 2 个即可平衡电荷，留 1 个空位。这正是讲义通式写成 "AB**₂₋₃**Si₄O₁₀(OH,F)₂" 中下标 2–3 的含义，讲义未展开。

#### (6) 长石 Feldspars — 架状，单斜或三斜

**碱性长石 Alkali feldspar (K,Na)AlSi₃O₈**

- 产于长英质岩（granite、granodiorite、rhyolite、dacite）。
- **溶线间隙（miscibility gap）的物理成因（讲义原文）**："Miscibility gap exists at low temperature, due to the **large size difference between K⁺ and Na⁺ cations**. K⁺ 0.155 nm, Na⁺ 0.132 nm."——高温时热振动幅度大，大小差异被"容忍"，Na–K 完全固溶；降温后差异无法容忍，晶体**分离成富 Na 与富 K 两相**。
- **对称性随温度/成分变化**：高温 → 完全固溶、单斜（**mirror plane 垂直于二次轴 diad**）。**K 端**若快速冷却，可保留单斜结构 → **sanidine 透长石**。**Na 端**在低温下单斜结构"塌陷"，二次轴与镜面同时丢失、阳离子位畸变 → **三斜（albite）**。
- **出溶（exsolution）**：讲义示意为寄主 Or₈₀Ab₂₀ 在降温中分离出 Or₆₀Ab₄₀ 的条纹，机制是 **Na⁺ ↔ K⁺** 的扩散重排。产物即**条纹长石结构（perthitic texture）**；**条纹厚度正比于冷却速率**（越慢越粗）。
- **三种碱性长石的判别表（讲义原表，必背）**：

| | 冷却速率 | 对称性 | 双晶 | 条纹（perthite lamellae） | 环带 |
|---|---|---|---|---|---|
| Sanidine 透长石 | 快 | 单斜 | 简单双晶 | 无 | 罕见 |
| Orthoclase 正长石 | 中等 | 单斜 | 简单双晶 | 有 | 可能有 |
| Microcline 微斜长石 | 极慢 | 三斜 | **格子（cross-hatch）双晶** | 有 | 可能有 |

  使用步骤（讲义原文两步）：**① 找双晶、出溶和环带 → 定出最恰当的长石名称；② 由此反推岩石的冷却速率。** 这是"薄片 → 岩浆冷却史"的第一个完整推理链。
- **碱性长石光性**：PPL 极低突起、无色、解理迹极少可见、可见**云雾状黏土化蚀变**；XPL 一级低干涉色、有双晶（sanidine/orthoclase 简单双晶；microcline 细密 ~90° 格子双晶）、orthoclase 与 microcline 常见条纹结构。

**斜长石 Plagioclase (Na,Ca)(Al,Si)AlSi₂O₈，三斜**

- **端元**：albite NaAlSi₃O₈（Al:Si = 1:3）↔ anorthite CaAl₂Si₂O₈（Al:Si = 2:2）。
- **耦合替换（coupled substitution）**：**[NaSi]⁵⁺ ↔ [CaAl]⁵⁺**。这是本周最重要的一个化学式：**Na⁺→Ca²⁺ 多出的 +1 电荷，由四面体位上 Si⁴⁺→Al³⁺ 少的 −1 抵消**，总电荷守恒。因此斜长石可以**完全固溶**。
- **关键对比（讲义原文）**："Complete solid solution from albite to anorthite. Plagioclase **never shows any exsolution textures** in thin section."——**碱性长石有出溶，斜长石没有**。原因：Na⁺ 与 Ca²⁺ 半径接近（1.02 vs 1.00 Å），不存在低温溶线间隙。**这一条是区分两类长石的化学理由，也是薄片判据的理论根据。**
- **产出**：所有常见镁铁质、中性、长英质火成岩中都有；**地幔岩中没有**。
- **光性**：PPL 极低突起、无色、常呈**板状（tabular）习性**、解理迹极少可见、可见**绢云母化（sericite）云雾状蚀变**；XPL 一级低干涉色、**多重聚片双晶（multiple lamellar twinning）**、有时环带、**永不出现出溶条纹**。
- **成分可测**：可用**消光角**在薄片上测出 An 值（方法见 Reference Guide p17 与 Week 6）。

#### (7) 石英 Quartz — SiO₂，架状，三方晶系

- 产于长英质岩（granite、granodiorite、rhyolite、dacite）。
- **SiO₂ 多形**：quartz（地表稳定）、tridymite、cristobalite、coesite、stishovite（后四者在地表岩石中可作为亚稳相出现）。
- **光性（几乎全是"负特征"）**：PPL 极低突起、无色、**无解理**、**从不蚀变**；XPL 一级低干涉色、**无双晶、无环带**、岩石变形后可见**波状/斑块状消光（undulose / patchy extinction）**。
- 讲义判据原文："Distinguish from feldspars by the **absence of twinning, zoning or alteration**."——**石英靠"什么都没有"来识别。**

---

## 三、公式与图表

### 1. 半径比公式

$$\text{radius ratio} = \frac{r_{\text{cation}}}{r_{\text{anion}}}$$

- **符号**：r_cation = 阳离子半径，r_anion = 阴离子半径（造岩硅酸盐中阴离子几乎总是 O²⁻，r = 1.40 Å）。
- **单位**：两者同为 Å（1 Å = 10⁻¹⁰ m = 0.1 nm），**比值无量纲**。
- **适用条件**：假设离子为**刚性球**、键为**纯离子键**、阳离子被阴离子紧密包围。对以离子键为主的氧化物/硅酸盐大体成立；对共价性强或高度极化的键（如 Si–O 实际有约 50% 共价性）只能作半定量指导。
- **典型数值**：Si⁴⁺/O²⁻ = 0.4/1.4 ≈ **0.3** → 四配位；Mg²⁺(0.72)/1.40 ≈ 0.51 → 六配位；Ca²⁺(1.00)/1.40 ≈ 0.71 → 六至八配位边界；K⁺(1.38)/1.40 ≈ 0.99 → 八至十二配位。

⚠️ 注意讲义内部数值不自洽：阳离子表给 Si⁴⁺ = 0.26 Å，代入得 0.26/1.40 = 0.19 → 会错误预测**三配位**；四面体那一页改用 0.4 Å 才得到 0.3。见勘误表第 4 条。

### 2. 硅酸盐分组表

见上文第二节表格。**读法**：给定通式 → 数 Si:O 比 → 反推共用氧数。速算式：共用氧数 n 与 Si:O 比的关系为 **O/Si = 4 − n/2**。验证：岛状 n=0 → O/Si=4（SiO₄）✓；单链 n=2 → O/Si=3（Si₂O₆）✓；层状 n=3 → O/Si=2.5（Si₄O₁₀）✓；架状 n=4 → O/Si=2（SiO₂）✓。📎 背景补充：这条速算公式讲义未给出，是从表格反推的，考试上非常好用。

### 3. 主要矿物化学式与符号解释

| 矿物 | 化学式 | 符号含义 |
|---|---|---|
| Olivine | (Mg,Fe)₂SiO₄ | 括号内 Mg、Fe 在 M1/M2 位任意比例互换；端元 Fo = Mg₂SiO₄，Fa = Fe₂SiO₄ |
| Garnet | (A₃B₂)Si₃O₁₂ | A = 大 M²⁺（Ca,Mg,Fe²⁺,Mn²⁺）[8] 畸变立方；B = 小 M³⁺（Al,Fe³⁺,Cr³⁺）[6] 八面体 |
| Pyroxene | XYSi₂O₆ | X = M2（大位）；Y = M1（小位）；augite 中 X=Ca，Y=Mg/Fe |
| Augite | Ca(Mg,Fe)Si₂O₆ | 高 Ca 单斜辉石 |
| Chrome diopside | Ca(Mg,Cr)Si₂O₆ | 讲义写法；见勘误表第 8 条 |
| Orthopyroxene | (Mg,Fe)Si₂O₆ | M1、M2 均为 Mg/Fe，无 Ca |
| Amphibole | AB₂C₅Si₈O₂₂(OH)₂ | A[12] = Na,K 或空位；B[8] = Ca,Na,Mg,Fe²⁺；C[6] = Mg,Fe²⁺,Al,Fe³⁺；(OH) 可被 F 或空位取代 |
| Hornblende | Ca₂(Mg,Fe)₄Al[Si₇O₂₂](OH)₂ | 讲义写法，缺一个四面体位 Al；见勘误表第 3 条 |
| Mica | AB₂₋₃Si₄O₁₀(OH,F)₂ | A = 层间大阳离子（K）；B = 八面体位（2 个 = 二八面体；3 个 = 三八面体） |
| Biotite | K₂(Mg,Fe)₆[Al₂Si₆O₂₀](OH)₄ | O₂₀ 基准写法（DHZ 体系）；电荷平衡 ✓ |
| Muscovite | K₂Al₄[Al₂Si₆O₂₀](OH,F)₄ | 讲义写作 K₄Al₄…；见勘误表第 2 条 |
| Alkali feldspar | (K,Na)AlSi₃O₈ | Or 端元 = KAlSi₃O₈，Ab 端元 = NaAlSi₃O₈ |
| Plagioclase | (Na,Ca)(Al,Si)AlSi₂O₈ | 讲义写作 (Na,Ca)(Al,Si)Si₂O₈，缺一个 Al；见勘误表第 1 条 |
| Quartz | SiO₂ | 无阳离子位 |

**耦合替换式**：**[NaSi]⁵⁺ ↔ [CaAl]⁵⁺**（斜长石）；**Si⁴⁺ ↔ Al³⁺**（云母四面体片，需层间阳离子补偿）；**Na⁺ ↔ K⁺**（碱性长石出溶）。

### 4. 图表逐个文字化描述

**（a）配位多面体图（讲义 1.1）**
一列 5 行的图表。**左列**是半径比区间（从 0.16 到 >1.0，自上而下递增）；**中列**文字描述阴离子如何围绕阳离子排列；**右列**画出多面体几何形体：三角形 → 四面体 → 八面体 → 立方体 → 立方八面体。**读法**：算出半径比，落在哪一行，就读出该阳离子在结构中的配位数与所占空隙的形状。**结论用途**：判断某元素能否替换另一元素（配位数相同且半径相差 < ~15% 才容易置换）。

**（b）"too small / just right / too large" 示意图**
两页图，画一个由若干大阴离子球围成的空隙，中间放不同尺寸的阳离子球。**上一页**：小球在洞里松动（too small）→ 中等球恰好接触所有阴离子（just right）→ 大球把阴离子撑开（too large）。**下一页**换一个更大的空隙重复。**结论**：稳定构型要求**阳离子恰好同时接触所有配位阴离子**；偏离就会改变配位数。

**（c）硅酸盐族结构图（讲义 1.3，两页表）**
表格第 4 列为四面体排列示意：岛状 = 孤立三角形（俯视四面体）；双岛 = 两个三角形共一角；环状 = 三个/六个三角形首尾成环；单链 = 一条锯齿带；双链 = 两条锯齿带并联、共用氧构成六元环孔；层状 = 蜂窝状六元环无限片；架状 = 三维网。**读法**：看到图能说出族名 + 举一个矿物例子——转写原话："If you can recognise the class from the diagram and give an example of a mineral that belongs to each of those classes, you'll be setting yourself up for good things."（**这是明确的考试提示**。）

**（d）I-beam 图（辉石/角闪石）**
两幅：**侧视（side view）**——四面体链在上下，中间夹八面体阳离子层，整体像工字梁；**端视（end-on view）**——沿链方向看下去，看到 I 形横截面在平面上密排，解理面就是绕过 I 形轮廓、不切断 Si–O 链的那些面。辉石（单 I-beam）排出来近正方网格 → **90° 解理**；角闪石（双 I-beam）排出来是拉长的菱形网格 → **60°/120° 解理**。**这张图是解理角度的唯一解释，务必会画。**

**（e）cpx 与 opx 单胞对比图**
两个单胞并排，标出 a 轴与 c 轴。讲义注文："**Cpx unit cell: two sets of stacked I-beams; Opx unit cell: four sets of stacked I-beams**"，并总结"both are single chain silicates and have the same basic structure, but in detail their **symmetry** is different and their **unit cell sizes** are different"。**读法**：opx 的 a 轴约为 cpx 的两倍 → 斜方对称 → 光率体主轴与晶轴重合 → **平行消光**；cpx 单斜 → 光率体主轴相对 c 轴倾斜 → **斜消光**。

**（f）云母 T–O–T 堆垛与解理图**
三个视角：3D 形体（六方板状）、垂直 z 的 2D 切面（近六边形，看不到解理）、平行 z 的 2D 切面（一组平行直线 = 一组极完全底面解理）。**读法**：薄片中云母若切成"书页侧面"，就看到一组极密的直解理；若切成"书页正面"，则解理不可见、干涉色也异常低。

**（g）碱性长石溶线（solvus / miscibility gap）图**
坐标：**横轴 = 成分，从 Or（KAlSi₃O₈）到 Ab（NaAlSi₃O₈）；纵轴 = 温度 T（向上升高）**。图中一条**穹隆状曲线（溶线）**：曲线**以上**为单一均一固溶体区（"High T: complete solid solution"）；曲线**以下**为**两相共存区（miscibility gap）**，任何落入其中的成分都会分离成曲线左右两支所指的两个成分。**读法举例**：寄主晶体 Or₈₀Ab₂₀ 在高温下均一；降温穿过溶线后，晶体分离出富 Na 的条纹（图中标 Or₆₀Ab₄₀ 一支）与富 K 的寄主 → **条纹长石**。**结论**：见到条纹 = 该长石曾穿越溶线并有足够时间扩散 = **缓慢冷却的深成岩**。
📎 背景补充：这正是 EART26201 Week 04 讲的 Ab–Or 溶线出溶，本课只用其结论。

**（h）碱性长石出溶示意图**
两个方框：左框标 "Host crystal: Or₈₀Ab₂₀" 的均一晶体；右框同一晶体内出现细长条带，标 "Or₆₀Ab₄₀"，箭头标 **Na⁺ ↔ K⁺** 的扩散方向。旁注两种薄片表现：**Sanidine** —— 沿晶体长轴的**一条简单双晶面**，见于快速冷却的火山岩（如流纹岩）；**Orthoclase with perthitic texture** —— 蠕虫状条纹，见于深成岩（如花岗岩），**条纹厚度正比于冷却速率**。

**（i）橄榄石与斜长石二元相图（讲义只标注引用）**
讲义两处写 "Olivine phase diagram: See EART 26201 Lecture 3"、"Plagioclase phase diagram: See EART 26201 Lecture 3"。📎 背景补充（本课未展开，取自上游课程结论）：二者都是**完全固溶体的透镜状二元环（binary loop）**：横轴 = 成分（Fo–Fa 或 An–Ab），纵轴 = 温度；上方 **liquidus 液相线**与下方 **solidus 固相线**围成一个两相区。在两相区内水平作**连接线（tie line）**，与液相线交点给出熔体成分、与固相线交点给出晶体成分。结论：**平衡结晶时晶体成分沿固相线连续变化（先结晶富 Mg / 富 Ca），若扩散跟不上就形成环带（zoning）**——这解释了本周薄片中斜长石的成分环带。

**（j）Michel-Lévy 消光角—成分曲线（Reference Guide p17）**
坐标：**横轴 = 斜长石成分（An%，albite → anorthite）；纵轴 = 相对聚片双晶面的最大消光角（度）**。曲线从 Ab 端的负角上升穿过 0，再单调升到 An 端的高角。**操作步骤（Reference Guide 原文 7 步）**：① 找双晶面 N–S 时两组双晶呈**同一浅灰色**的晶体（此方位消光角对称）；② 旋转载物台测 a 与 a′；③ 若 a 与 a′ 相差超过几度则**弃用该晶体**；④ 若相差在几度内，取 **(a + a′)/2**；⑤ 多测几粒；⑥ 因切面方位不同结果会散开，**取最大值**；⑦ 在曲线上查 An 值。**陷阱**：无法区分正负消光角，15° 既可能是 −15°（albite）也可能是 +15°（oligoclase），需另用 Becke 线法测折射率区分。

**（k）体积百分含量目估图（Reference Guide p28）**
一组标注了不同百分比（如 1%、5%、10%…）的斑点图，分别对应 FELDSPAR（一般长石）、CPX、ORTHOPYROXENE 三种矿物的外观。**用法**：把视域中某矿物的面积印象与图中最接近的一格比对，读出百分比。**注意**：这是**目估**，Practical 明确给出 **±5–10% 的不确定度**；精确做法是耗时的**点计数（point counting）**。

**（l）双折射率数值（Reference Guide p16，olivine vs augite 表）**

| 矿物 | 双折射率 δ | 最高干涉色 |
|---|---|---|
| Olivine | **0.035–0.052** | 可达三级 |
| Augite | **0.018–0.033** | 可达二级 |

📎 背景补充：干涉色阶次由 **Δ = t·δ** 决定（Δ = 光程差，t = 薄片厚度，标准 **30 μm = 0.03 mm**，δ = 双折射率）。代入橄榄石 δ=0.05：Δ = 0.03 mm × 0.05 = 0.0015 mm = **1500 nm** → 落在三级；代入普通辉石 δ=0.025：Δ = 750 nm → 二级。**这就是"为什么橄榄石比辉石亮"的定量答案**，讲义未给出公式，但它把 Week 02 的光学与本周的矿物学接起来了。

---

## 四、课堂补充

本周 20-Oct 的课堂 1 小时**几乎全部是虚拟显微镜实操**，是全课信息密度最高的一节。以下按转写顺序提炼讲义上**没有**的内容。

### 1. 课务与资源（考试与复习相关）

- **视频脚本可直接下载**：老师不发 PowerPoint 源文件（备注栏混有自用教学笔记），但**备注中的学术内容就是录视频的脚本**，在视频播放器点 "download transcript" 即可拿到全文；所有讲座也录成 podcast 并配字幕。⚠️ 老师亲口提醒："I can't vouch for how good the transcript is in identifying technical words like **mineral names**."（自动转写对矿物名极不可靠——本周材料本身就是活例，见勘误表。）
- **Virtual Microscope（virtualmicroscope.org）** 是本课核心线上资源，由 **Open University** 为远程学习者建立，扫描了英国多所大学的薄片，涵盖火成岩/变质岩/沉积岩，还有 Apollo 月球样品与陨石。
  - **Teaching resources → manual of minerals**：按矿物查典型薄片，并可复习 pleochroism / relief / cleavage / extinction。
  - 有一个很实用的小栏目教你识别薄片中的**假象（artifacts）**——玻片上的灰尘、指纹、气泡长什么样。看到怪东西先查它是伪影还是矿物。
  - **Explore 标签**可按"岩石类型 + 造岩矿物"组合检索。每个条目有 **Object（手标本）** 与 **Microscope（数字薄片）** 两个标签；数字薄片可切换 PPL/XPL、缩放、量尺寸，多数带 **rotation（旋转序列）**模拟旋转载物台。**PPL = 起偏器东西向；XPL = 再插入南北向分析镜。**

📎 背景补充：讲义末尾"Thin sections for classroom session"的 URL 与转写演示的薄片可逐条对应（推断）：橄榄石 = s339-07-basalt（火山岩）与 olivine-gabbro-huntly（深成岩）；augite = porphyritic-olivine-basalt-mauritius；opx vs cpx = m24-two-pyroxene-granulite-lewisian；角闪石 = i16 hornblende dacite tuff 与 m01 amphibolite Lough Nagilly；黑白云母 = biotite-granite-luxulyan；sanidine = obsidian-sandy-braes；orthoclase = syenite-ben-loyal；microcline = i03 Leinster granite；斜长石 = basalt-giants-causeway 与 diorite-magellan-straits；石英 = granite-lundy（其 Rotation 1 其实是黄玉 topaz）。

### 2. 最重要的方法论：Describe, describe, describe

这是本节课**唯一被反复强调五次**的评分规则，直接关系 30% 的 practical test：

> "If you write down '**this mineral is clinopyroxene**' with no justification and it's not clinopyroxene, **I can't give you any marks** for that. But if you write down: the mineral is lightly coloured in PPL, it has one perfect cleavage, it has no pleochroism, under XPL it has second-order interference colours and inclined extinction at 30° with respect to the cleavage trace — I think it is clinopyroxene — **you get all the marks**. If you write all those observations and then write 'I think it's olivine', **you still get all the marks**, because you've done the hard work of observing the properties."

**结论：分数给在"观察记录"上，不在"结论对错"上。先描述，后判断。** 老师还坦白："A lot of my research is on rocks that contain these two minerals（橄榄石与单斜辉石）and **sometimes I get it wrong**. So don't panic."

另一条个体化建议：**"the things that pop for you might not be the same as the things that pop for me"**——例如色觉障碍者用不上颜色，但可能对突起（relief）更敏感。所以要**建立自己的一套判据清单**，写进可带入考试的 Reference Handout。

### 3. 橄榄石：口头讲的成因细节（讲义没有）

- **弯曲裂纹的成因**："Imagine that you're a mineral that is growing happily in a magma chamber somewhere at **high pressure** in the crust. And a volcanic eruption picks you up and carries you up to the surface. **The change in pressure can cause the mineral to crack.**"——**减压破裂**。所以弯曲裂纹是"从深部被带上来"的证据。
- **裂纹 ≠ 解理，判据是"是否平面/是否互相平行"**："These are **not cleavage because they are not planar**... they're not parallel to one another." 这是本周被强调两次的区分。
- **蛇纹石化的成因**："The olivine is being **attacked by the water** surrounding it. There's a chemical reaction going on there. And a new mineral, serpentine, is growing around the edge of the olivine." 在**海底喷发的火山岩**中尤其常见，粗粒深成岩中也有。
- **蚀变程度可读出"新鲜度"**：轻微时只在晶体边缘出现绿褐色"脏东西"；严重时蚀变会**沿弯曲裂纹侵入晶体内部**，整颗晶体看起来"very gungy and very unhappy"。
- **火山岩 vs 深成岩中的橄榄石**：光性完全相同，但**深成岩中的裂纹发育得强烈得多**（老师现场对比了两张薄片）。
- **自形程度的现场判断**："You can just about see where the faces of this crystal are — these nearly flat edges. So it's a fairly well-formed crystal. We could call this **euhedral** or potentially **subhedral**."
- **"每 90° 消光一次"不是有用的观察**："That's not a particularly useful observation. **Every mineral does this unless it's isotropic.**" 有用的是**消光角**与**干涉色**。
- 现场把橄榄石的干涉色读作 "**a second-order blue**"。

### 4. 辉石：口头讲的判别要领

- **命名与晶系的对应记忆法**："ortho pyroxene belongs to the **orthorhombic** crystal system; clino pyroxene belongs to the **monoclinic** crystal system."
- **"clino–inclined–monoclinic 三件套"记忆法（老师原创，很好用）**："When you're thinking about pyroxenes, this kind of **clino**, **inclined**, **monoclinic** — they all fit together. So **clinopyroxenes can have inclined extinction**."
- **cpx 的颜色是"faint pinky browny"**，与橄榄石的完全无色形成对比——"It's quite subtle, but **when you see the two next to each other**, often you can tell the difference."（**要并排比较，不要孤立判断**。）
- **两组解理的切面 → 对称消光（symmetrical extinction）**："The mineral should go extinct when **the cleavage is bisected by the crosshairs**." 一组解理的切面 → 测**斜消光角**。
- **口述消光角为 30–40°**（讲义写 35–45°，见勘误表）。
- **双晶的成因（讲义未讲）**："A twin forms when there is some kind of **defect in the crystal lattice** — maybe along that plane the crystal has started growing **mirror images** of the lattice, or the lattice has started growing at slightly the wrong orientation." 表现：XPL 下晶体分成两半、**在不同角度先后消光**；PPL 下看不见双晶面，**XPL 下立刻显现**。
- **opx 与 cpx 的实操判别（老师给出的两步法）**："You look for **the interference colour**, and you look for **does it have inclined or straight extinction**." opx 的干涉色是"grey to a sort of **washed out yellow**"。
- **测量消光角的选片原则（Reference Guide p16 补充）**：要选**只显示一组解理迹**、且**干涉色最高**的晶体。

### 5. 角闪石：把矿物学和构造背景连起来

- **含水是角闪石的关键**："One of the important things about hornblende is that it **incorporates water into its crystal lattice**, so you **can't grow much hornblende in a dry environment**, but you can grow it in a wet environment."
- **因此角闪石是俯冲带的指示矿物**："Subduction zones are a good place for water to be being cycled around in the deep earth and supplied to magma chambers, so we tend to see **hornblende in rocks from subduction zone settings**."——这是本周与本课后半"构造背景"最直接的一根线。
- **火山岩 vs 深成岩中的角闪石颜色**：火山岩中多为**黄褐色调**；深成岩中多为**褐—绿色调**。
- **三种多色性颜色的物理成因**："Hornblende is a **biaxial** mineral — there are **three different colours** associated with it, and we see different colours depending on how the crystal's been sliced."（📎 背景补充：二轴晶有三个主折射率 α、β、γ，对应三个主吸收方向，故有三个多色性颜色；等轴晶只有一个，一轴晶有两个。）现场在粗粒角闪岩里指出三色：浅褐绿 / 深褐绿 / "sludge green"。
- **反应边不是高突起**："This is actually **not high relief**, which is a bit confusing — this is actually the hornblende starting to **react chemically with the material surrounding it**." 火山岩中角闪石常有一圈**尘状反应边**。（成因：岩浆上升脱水后角闪石不再稳定，边缘分解为无水矿物 + 氧化物细晶。此机制为📎背景补充，材料未展开。）
- **基面切片呈假六方（菱形）**："This kind of hexagonal prismatic shape... **It's not perfectly hexagonal, so this is not part of a hexagonal crystal system**, but these kind of six-sided prisms are quite characteristic."
- **现场实测消光角约 17°**，并再次给出角闪石 15–20° vs 辉石 30–40° 的对比。

### 6. 云母：黑云母与角闪石最容易混（本节最细的辨析）

老师明确设问："didn't we just see brown-yellow pleochroism in hornblende? **It's quite easy to confuse biotite and hornblende in thin section.** So what would I use to tell them apart?" 给出**四条**判据：

1. **解理组数**：黑云母**一组**极完全解理；角闪石**两组**（60°）。
2. **斑驳消光（speckled extinction）**——本节课最有价值的一条经验：把解理迹平行于十字丝时，黑云母"**doesn't really go into full extinction**... it never really goes completely black. **We call this speckled extinction.**" 而角闪石"has definitely gone completely black, completely extinct"。老师现场被学生追问后再解释一遍："speckled extinction refers to: if we put it into the position where we think it ought to be in extinction, **it's not quite**." （📎 背景补充：成因是云母薄片中层片轻微弯曲/堆垛无序，使各微区光率体方位略有差异，无法同时消光。材料未给出机制。）
3. **晶形（habit）**：角闪石"quite a well-formed prism"，短轴方向也有平整晶面；黑云母**平行解理方向晶面平整，垂直解理方向则"horrible ragged"（参差不齐）**。
4. **多色晕（pleochroic haloes）**：黑云母内部常见"really dark spots"，角闪石中**从不出现**——"you don't see this effect in amphiboles."
- **黑云母的干涉色**被形容为"really quite weird looking... a little bit **psychedelic**"，因为阶次很高。
- **白云母**：晶形与解理与黑云母相同，但**无色、不多色**；干涉色常见**亮蓝或亮橙**；同样有"平行但不完全"的斑驳消光。
- **共生提示**："These two minerals are **most frequently found together in granites**. So if you see one, it's a good idea to have a look and see if you can find any of the other."

### 7. 三个"无色矿物三明治"：quartz / plagioclase / alkali feldspar

老师把这三个单列一组处理："The last set of minerals are all **colourless in PPL**, so these are ones where you have to work a little bit harder."

- **石英**："Identify quartz by the fact that it's **pretty boring and pretty featureless**." 低突起、晶体边界都难看清、无色、一级灰白干涉色、无双晶、无解理。
- **波状消光的成因**："This rock has undergone a little bit of **deformation**, and that can **distort the crystal lattice** and mean that you get these sort of **shadowy sub-grain effects** where the crystal lattice has been bent." **在深成岩中不算少见，在火山岩中会非常罕见**——所以看到它值得记下来。
- **斜长石**："The most recognizable feature is the **multiple lamellar twinning** — black and white stripes parallel to one another running down the length of the crystal." 火山岩中的斜长石常**细长呈针状（acicular）**；深成岩中**更宽更胖**，但**双晶总是沿晶体长轴延伸**。
- **碱性长石按冷却速率分三种表现**：
  - **火山岩 → sanidine，简单双晶（simple twinning）**：全晶只有**一条**双晶面。"Why is this different from plagioclase? **There's only one twin plane.**"
  - **深成岩 → orthoclase，条纹结构**：XPL 下"**wormy looking lines**"；蠕虫内部富 Na、外部富 K。"**The thicker the wormy texture, the slower the cooling rate.**" "In a volcanic rock we would **never** expect to see this, because there is **not enough time** for this chemical exsolution to occur."
  - **深成岩 → microcline，格子/苏格兰格纹双晶（cross-hatch / tartan twinning）**："**Only forms in very slowly cooled plutonic igneous rocks.**"
- **microcline 与斜长石的区分（口述关键）**："It's quite easy to confuse with the lamellar twinning of plagioclase. What you should look for is that **in plagioclase we only see those twins in one direction; in microcline we see them in two directions.**"
- **云雾状蚀变（dusty alteration）**是热液蚀变的表现，**长石有、石英没有**（此处老师说"only feldspars undergo hydrothermal alteration"，是简化说法，见勘误表第 14 条）。
- **老师给的总结句**："These three minerals — quartz, plagioclase and alkali feldspar — you want to have some notes for yourself about how you're going to tell the difference between them, given that they're **all colourless and low relief in PPL**. It's these properties of **twinning and exsolution versus completely featureless** that are going to be your friends."

### 8. 薄片技术素描：考试要求

课末专门讲了薄片素描（对应 ILO 9，practical test 会考）：

- 性质定位："It's **not an artistic drawing**, it's a **technical drawing**"，与野外素描（转写提到学生在 Aliaga 野外做过 field sketches）同理。
- **两个必须表达的东西**：① 尽可能准确的**晶体形状**；② 该矿物**如何嵌在岩石整体结构中**。
- **不合格示范**："I could say 'does this rock contain olivine?' and you might draw me a **circular blob with an arrow that says olivine**, and I'd be like — well, okay, maybe, **but why is it olivine?**"
- **合格示范**：写出观察到的一组性质；**更好的是**说明"这是橄榄石，它嵌在什么里面"——例如"我能看到这些长的**针状（acicular）**晶体，看起来像斜长石，还有这些浅色晶体被标为**普通辉石（augite, clinopyroxene）**"。
- **硬性要求**：**必须有比例尺（scale bar）**，**图上一切都要标注**。Reference Guide p3 补充：素描要画大（至少半页、约 10 cm）；比例尺不能写"×10/×20"（那只说明物镜倍数，不等于图的比例）；用线宽、阴影、颜色表达细节；描述里提到的每一个矿物和每一处结构特征都要在图上出现。
- 老师会在学期中安排一次反馈机会。

---

## 五、Practical 要点

### 1. 目的与安排

**Practical 3: An introduction to the rock-forming minerals**（与讲义同名）。完成后应能：

- 在**手标本和薄片**中识别常见造岩矿物；
- 在 **PPL 与 XPL** 下描述造岩矿物；
- **目估火成岩的模式矿物组成（modal mineralogy）**。

同时练习的技能：描述 relief、colour、pleochroism、cleavage、twinning、extinction angle；准确素描重要的火成结构与矿物学特征；**用结构观察推断结晶顺序**。

**结构**：Part 1（15 分钟，手标本）+ Part 2（90 分钟，6 张薄片）。薄片可**任意顺序**看，不必每张做透，但**每张都要看过**。每张薄片老师都已给出**分类名和简短描述**，任务是"**核对你能不能找出描述里提到的每一个特征**"。

**Reference Handout 本次要用到的页码（原文列出）**：颜色/结晶度/粒度 p2；矿物光性与判别特征表（封三 inside back cover）；矿物性质详注 pp22–24；**cpx 与 opx 的区分 p25**；**模式含量目估图 p28**；晶形术语 pp15–16。⚠️ 原文提醒："**minerals do not always show the ideal features listed, and may show other useful features that are not listed.**"

📎 背景补充：`EART22201 Reference Guide 2025.md` 这份 md 只转出到 p17 左右（模式含量图那一页戛然而止），Practical 引用的 p20（结构名称）、pp22–25（矿物性质详注与 cpx/opx 区分）、封三光性总表**在 md 中不存在**。但 p16 的"olivine vs augite"和"opx vs cpx"两张判别表已完整转出，是本周最关键的两张速查表。

### 2. 两个必须掌握的术语（Practical 原文定义）

- **Modal mineralogy 模式矿物组成**：岩石中各矿物的**百分比，总和 100%**。精确方法是**点计数（point counting）**，但极耗时，因此本课**用肉眼目估**。
- **Crystal shapes 晶形**：不同矿物有特征形状（例：斜长石倾向形成**板状 tabular**，即块状矩形）；形状还取决于晶面发育程度（good / moderate / absent → euhedral 自形 / subhedral 半自形 / anhedral 他形）。

### 3. 六张薄片：答案与推理链

#### 薄片 273 — biotite hornblende granite（黑云母角闪石花岗岩）

**给定描述**：角闪石在某些方位呈**蓝绿色**，特征**板条状（lath）晶形与菱形横截面**发育良好；黑云母部分蚀变为**绿泥石 chlorite**；另含石英、斜长石、碱性长石；**斜长石有环带**，部分**绢云母化（sericite）**——绢云母是一种类白云母的白色云母：无色、中等双折射、**斑驳消光**；部分薄片含副矿物**榍石 titanite（= sphene）**。

**模式含量答案（合计 100%）**：

| 矿物 | 含量 | 粒径 | 晶形 |
|---|---|---|---|
| Plagioclase | ~25% | 1–6 mm | tabular to subhedral |
| Alkali feldspar | ~35% | 0.5–3 mm | tabular to subhedral |
| Quartz | ~20% | 0.2–3 mm | anhedral；部分重结晶 |
| Biotite | ~5% | 1 mm | subhedral laths |
| Hornblende | ~14% | 0.5–1.5 mm | euhedral；伸长板条 |
| Titanite | 1% | <1 mm | euhedral |
| Oxide | 微量 trace | <1 mm | subhedral to anhedral |

- **斜长石与碱性长石谁多？** 答案："**I found more alkali feldspar than plagioclase**, but the modal proportions vary between thin sections."（**不同薄片会不一样，这是允许的**。）
- **黑云母的颜色与黑云母—绿泥石关系**：黑云母多色性为**褐 ↔ 麦秆黄**，但**褐色带有绿色调**。**绿色的绿泥石正在交代黑云母，最明显是在晶体边缘和沿解理迹**。成因：**含水蚀变（hydrous alteration）**。
- **推理链**：解理迹和晶缘是流体最先进入的通道 → 交代从这两处开始 → 因此"沿解理长出的绿色矿物"是次生蚀变的标准判据。

#### 薄片 81108 — hornblende aegirine alkali syenite（角闪石霓辉石碱性正长岩）

**给定描述**：成分与矿物组合非常特殊。含**微条纹碱性长石（micro-perthite）**、角闪石，以及一种不常见的**富钠单斜辉石：淡绿色的霓辉石—普通辉石 aegirine-augite**；可能见副矿物榍石。（标 81108X 的薄片矿物组合略不同，但**榍石实例最好**，且**额外含斜长石与石英**。）

**模式含量**：alkali feldspar 85%（1–3 mm，tabular to anhedral）；aegirine-augite ≤10%（0.2–2 mm，subhedral）；hornblende ~5%（0.2–1 mm，subhedral）；titanite <1%（0.5–2 mm）；oxide <1%。

- **这是哪种碱性长石？告诉你什么冷却速率？** 答案完整推理链（**本周最典型的一条"结构→冷却史"推理，务必背下来**）：
  > "This is **orthoclase**: it has **simple twinning** and **perthitic exsolution**. All the crystals have distinctive **blebs of Na-rich albite**, and some of these blebs have **lamellar twins**. The exsolved lamellae are quite **coarse**, which suggests that the rock must have **cooled slowly**. **But the cooling rate was not slow enough to cause Al:Si ordering** in the alkali feldspar — otherwise we would have **microcline**."
  - 判据 1：简单双晶 → 单斜 → sanidine 或 orthoclase；
  - 判据 2：有条纹出溶 → 排除 sanidine（火山岩快冷无出溶）→ orthoclase 或 microcline；
  - 判据 3：无格子双晶 → 未发生 Al:Si 有序化 → **不是 microcline** → **定为 orthoclase**；
  - 结论：**冷却慢（条纹粗）但没慢到形成微斜长石**。
- **角闪石为什么围着霓辉石长？** 答案：
  > "The hornblende must have **crystallized later** than the augite. **Pyroxenes are dry, whereas amphiboles can take water** into their crystal lattices. **Progressive crystallization of anhydrous minerals caused the remaining silicate liquid to become more hydrous**, allowing hornblende to start crystallizing. Hornblende has a **very similar crystallographic structure to pyroxenes**, so it uses the clinopyroxene as a convenient **nucleation template**."
  - 三步逻辑：**包裹关系 → 先后顺序** ＋ **无水矿物结晶 → 残余熔体富水** ＋ **单链与双链结构相似 → 成核模板**。这条把晶体化学（双链含 OH）、岩浆演化（残余熔体富集）和结构观察三者串起来，是本周含金量最高的一题。

#### 薄片 R1 — olivine dolerite / olivine gabbro（橄榄粗玄岩，Rum 层状侵入体，苏格兰内赫布里底群岛）

**给定描述**：由橄榄石、普通辉石、斜长石与不透明氧化物组成。橄榄石**高突起、弯曲裂纹**；样品较新鲜，但部分橄榄石在**晶缘与裂纹内**有特征的蛇纹石化。**橄榄石的干涉色随切面方位从低到至少二级黄不等**。多数橄榄石为 subhedral 或 anhedral（**浑圆、缺乏发育良好的晶面**），因此**很可能测不到消光角**。

**模式含量**：olivine ~40%（0.5–1 mm，subhedral–anhedral，部分 euhedral）；plagioclase ~30%（1–2 mm，anhedral）；augite ~30%（<1 至 4 mm，anhedral）；oxide ~1%（~10 μm，euhedral，立方习性）。**原文提醒：斜长石与 cpx 的比例在不同薄片间会变，目估应给自己 ±5–10% 的余量。**

- **结构名称与结晶顺序**：
  > "Olivines are **enclosed by large anhedral crystals of plagioclase and/or augite**. This is a **poikilitic** texture. The olivine crystals **formed first**, and were then enclosed by later-growing plagioclase and augite. The oxides are usually enclosed within plagioclase and augite, but there are **some oxide inclusions within the olivines too**. There must have been **small amounts of oxide crystallizing at the same time as all the other minerals**."
  - **推理链**：被包裹者早、包裹者晚（Reference Guide p5 原则）；氧化物同时出现在两代矿物内部 → **氧化物贯穿整个结晶过程**。
  - 📎 背景补充：**poikilitic 嵌晶结构**的两个专名（Reference Guide p13）——大的包裹晶叫 **oikocryst 主晶**，被包裹的小晶体叫 **chadacryst 客晶**；若被包裹者是斜长石板条、包裹者是普通辉石，则专称 **ophitic 辉绿结构**（粗玄岩典型），部分包裹则为 **subophitic**。

#### 薄片 RFM7 — hornblende syenite（角闪石正长岩）

**给定描述**：含碱性长石、斜长石、角闪石；斜长石为**大晶体，具特征聚片双晶**。

**模式含量**：plagioclase 35%（0.5–1.5 mm，tabular–subhedral）；alkali feldspar 40%（0.5–3 mm，tabular–subhedral）；hornblende 25%（0.5–1 mm，euhedral–subhedral）；apatite 微量（<0.1 mm，自形柱状，**作为包体存在于角闪石中**）。

- **任务**：分别素描（a）**两组解理都可见**的角闪石与（b）**只见一组解理**的角闪石；在图上标出**折射率方向及其对应的多色性颜色**；测一组解理切面的消光角。
- **答案**：
  > "**Basal sections** through hornblende have the characteristic **diamond-like shape**, **two cleavages at ~60°**, and **symmetrical extinction bisecting the cleavage traces**. In the **one-cleavage section**, the extinction angle is about **18°**. The hornblende shows some **simple twinning**. The pleochroism is strong, in shades of **yellow, brown and green**. Some crystals appear to have **concentric rings** picked out by different shades of brown or green. This is **compositional zoning**."
- **磷灰石 apatite 的识别链**：**六方柱状习性 + PPL 无色高突起 + XPL 一级低干涉色 + 极小（<0.1 mm）+ 位于角闪石内部** → 磷灰石（一种磷酸盐矿物）。
- **两种切面的对应关系（本周核心技能）**：**基面切片（垂直 c 轴）→ 见两组解理 → 菱形轮廓 → 对称消光**；**纵切片（平行 c 轴）→ 只见一组解理 → 伸长轮廓 → 斜消光，可测 ~15–20°**。

#### 薄片 SW — biotite muscovite granite（黑云母白云母花岗岩）

**给定描述**：含黑云母、白云母、斜长石、碱性长石、石英。碱性长石为**微条纹长石**，寄主为 **microcline**（部分颗粒可见**微弱的格子双晶**）。部分**出溶的富 Na 碱性长石显示聚片双晶——因为它是 albite，而 albite 既是碱性长石，也是斜长石系列的一个端元**。部分钾长石显示简单双晶。

**模式含量**：plagioclase 15%（0.5–1 mm，tabular）；alkali feldspar 25%（0.5–1 及 4–5 mm，tabular–subhedral）；quartz 40%（<0.1 及 1–2 mm，anhedral）；muscovite ~8%（0.5–1.5 mm，laths）；biotite ~7%（0.5–1 mm，euhedral laths）。（⚠️ 合计 95%，见勘误表第 9 条。）

- **黑云母光性答案**：两种多色性颜色**褐与麦秆黄**；**一组极完全解理**；**平行消光**，接近消光位时呈**斑驳外观**；干涉色**三级高部**。
- **多色晕（pleochroic haloes）的成因（本周最完整的一条微观机制，考试常问）**：
  > "The pleochroic haloes form around **tiny inclusions of the mineral zircon**（锆石本身通常小到看不见）. **Zircon can accommodate a tiny amount of uranium in its crystal structure.** When the uranium undergoes **radioactive decay**, it emits **alpha particles** that cause **radiation damage to the surrounding biotite lattice**. This creates the pleochroic haloes."
  - 推理链：锆石晶体化学允许 U⁴⁺ 替代 Zr⁴⁺（半径相近、同价）→ U 衰变放出 α 粒子 → α 粒子射程约几十 μm → 在黑云母晶格中造成一个**球壳状的辐射损伤区** → 薄片中表现为深色圆环。
- **波状消光 + 石英呈小的互锁颗粒（重结晶证据）说明什么？** 答："**Undulose extinction and recrystallization are evidence that this rock has undergone some minor deformation.**"
- **斜长石的"脏"外观是什么？还有什么特征？** 答：**热液蚀变成绢云母 sericite**（Practical 此处称其为 "a clay mineral"，见勘误表第 10 条）；此外斜长石具**多重聚片双晶**与**成分环带**；本薄片中**绢云母通常局限在晶体核部**。
  - 📎 背景补充：绢云母集中在核部，说明核部成分更富 Ca（An 更高、更易被流体侵蚀），这与**正环带（normal zoning：核富 Ca、边富 Na）**一致——Reference Guide p14 给出 normal/reverse/oscillatory zoning 的定义。

#### 薄片 DWR10 — 含尖晶石的斜方辉石—斜长石岩

**给定问题**：本岩含一种不透明氧化物，即**尖晶石 spinel**。另外两种硅酸盐是什么？

- **答案与判别链**：
  > "The silicate minerals are **plagioclase and orthopyroxene**. **Opx is identified by its low first-order interference colours, and straight extinction in elongate crystals and one-cleavage sections.** Some of the opx crystals have **brightly birefringent exsolution lamellae of clinopyroxene**. There are also some small clinopyroxene crystals in some of the thin sections."
  - **注意这条**：opx 中出现**高双折射的 cpx 出溶片**——这正是 EART26201 Lecture 4 讲的辉石固溶体降温出溶（Di–En 体系）在薄片中的直接表现。
- **模式含量**：orthopyroxene ~40%（0.5–2 mm，euhedral，prismatic）；plagioclase ~40%（1–4 mm，subhedral）；spinel ~20%（0.1 mm，euhedral，cubic）。
- **结晶顺序**：
  > "The texture is **poikilitic**: **opx and spinel chadacrysts are enclosed in large oikocrysts of plagioclase**. Some of the **spinels are enclosed within larger opx crystals**. These relationships suggest that **spinel was the first mineral to start crystallizing; then spinel and opx crystallized simultaneously. Plagioclase must have started crystallizing later**, because it **fills up the interstitial spaces** between the other minerals."
  - **三条判据齐用**：包裹关系（尖晶石在 opx 内 → 尖晶石更早）+ 自形程度（opx 与尖晶石自形，斜长石半自形）+ **填隙关系（interstitial → 最晚）**。

### 4. 收束任务：三种无色低突起矿物的区分表（Practical 给出的标准答案）

|  | PPL | XPL | 形状 |
|---|---|---|---|
| **Quartz** | 无解理；**从不出现云雾状蚀变** | 无双晶；无出溶；变形后可见**波状/斑块状消光** | 通常浑圆 rounded |
| **Plagioclase** | 解理迹极少可见；可见**绢云母化云雾状蚀变** | **多重聚片双晶**；**从不出溶** | 通常**板状或针状**（tabular / acicular） |
| **Alkali feldspar** | 解理迹极少可见；可见绢云母化云雾状蚀变 | **火山岩中**：多为 sanidine，简单双晶、无出溶，用双晶与解理与石英区分。**深成岩中**：多为 orthoclase 或 microcline，二者都可有**条纹出溶**；orthoclase 简单双晶，microcline **格子双晶** | 通常板状 |

⚠️ Practical 原文强调："**You should come up with your own list of things to look for. Here is mine**"——这张表是老师个人的清单，鼓励学生做自己的版本。

### 5. 常见错误与评分要点

- **只写结论不写观察 → 0 分**（转写明确说明）；写满观察即使结论错也给满分。
- **把裂纹当解理**：解理必须**平面、成组、互相平行**；橄榄石的弯曲裂纹不是解理。
- **把气孔/空洞当各向同性矿物**：两者 XPL 都全黑，靠 PPL 突起与颜色区分（石榴子石高突起+粉色）。
- **把 microcline 的格子双晶当作斜长石聚片双晶**：斜长石双晶**只有一个方向**，microcline **两个方向交叉**。
- **在火山岩里"看到"条纹结构**：物理上不可能（冷却太快，来不及扩散出溶）——看到"条纹"要先怀疑自己的岩石类型判断。
- **模式含量目估**：不要追求精确到个位数，**给 ±5–10% 的余量**；同一岩石的不同薄片本来就会不同。
- **素描无比例尺、无标注 → 扣分**。

---

## 六、易错点 / 重点难点

1. **半径比只是半定量指导，不是定律。** 讲义自身的 Si⁴⁺ 数值（0.26 vs 0.4 Å）就前后不一，用 0.26 会得出"三配位"的错误结论。答题写"Si 在硅酸盐中恒为四配位"，并说明该理论假设刚性球与纯离子键，而 Si–O 有明显共价性。
2. **"共用氧数"要会从通式反推**：O/Si = 4 − n/2，别死背表格。
3. **辉石 90° vs 角闪石 60° 是最高频的一分。** 记忆锚点：单链 = 单 I-beam = 窄 = 近方形 = 90°；双链 = 双 I-beam = 宽 = 菱形 = 60°。
4. **消光角三档必须分清**：opx **平行消光（0°）**；hornblende **~15–25°**（实测 ~18°）；cpx/augite **~35–45°**（口述 30–40°）。**只在"只见一组解理"的切面上测**；两组解理的切面看到的是**对称消光**，不是消光角。
5. **"每 90° 消光一次"没有信息量**——所有各向异性矿物都这样。有信息量的是消光角、是否完全消光（斑驳消光）、干涉色阶次。
6. **橄榄石 vs 普通辉石**（Reference Guide p16）：无色 vs 淡粉褐/灰；**弯曲不规则裂纹 vs 两组垂直解理**；δ 0.035–0.052 vs 0.018–0.033；**平行消光（相对晶面）vs 斜消光（相对解理）**；**易蚀变为蛇纹石/伊丁石 vs 抗蚀变**。
7. **opx vs cpx**：**消光角最常用**；opx 通常无色不多色（例外：**enstatite** 有微弱而特征的淡粉—淡绿多色性）；opx 一级、cpx 多为二级干涉色；**opx 从不双晶，cpx 可以有**。
8. **黑云母 vs 角闪石**：一组解理 vs 两组 60° 解理；斑驳（不完全）消光 vs 干净的完全消光；垂直解理方向参差晶缘 vs 良好晶面；有多色晕 vs 无多色晕。
9. **碱性长石有出溶、斜长石没有**——化学理由：K⁺ 与 Na⁺ 半径差大（1.55 vs 1.32 Å）→ 低温有溶线间隙；Na⁺ 与 Ca²⁺ 半径几乎相同（1.02 vs 1.00 Å）且靠 [NaSi]↔[CaAl] 耦合替换 → 完全固溶。**"斜长石永不出现条纹"是判别 A 与 P 的硬判据。**
10. **"三名碱性长石 → 冷却速率"链要能完整复述**：简单双晶 + 无条纹 → sanidine → 快冷火山岩；简单双晶 + 有条纹 → orthoclase → 慢冷；格子双晶 + 有条纹 → microcline → 极慢冷（Al:Si 已有序化）。
11. **石榴子石与气孔/空洞的混淆**：靠 PPL（高突起 + 粉色）而不是 XPL。
12. **结晶顺序的三条判据**（Reference Guide p5）：被包裹者更早；早结晶者更自形；同一矿物中大晶体先于小晶体。⚠️ 原文明确警告：**Bowen 反应序列通常不是判断结晶顺序的好证据**（多数体系中多矿物同时结晶）——要用**结构**说话。
13. **模式含量应合计接近 100%**，且目估必有误差，报区间比报精确数更专业。
14. **蚀变与副矿物不进岩石名**：serpentine / chlorite / sericite / zeolite 是次生矿物；apatite、zircon、opaque oxide、titanite 是副矿物（通常 <5%）。岩石名 = essential + type 矿物，type 矿物按**含量由少到多**排在前面（"biotite muscovite granite" 表示白云母多于黑云母）。
15. **含水矿物 = 含水环境**：角闪石、云母含 (OH)⁻，需含水岩浆；辉石、橄榄石、长石无水。**这条既解释 81108 的角闪石包壳霓辉石，也预告了后半学期的俯冲带岩浆学。**

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| cation / anion | 阳离子 / 阴离子 | 失电子变小 / 得电子变大 |
| ionic radius / radius ratio | 离子半径 / 半径比 | 半径随价态与配位数变化；半径比 = r阳/r阴，决定配位数 |
| co-ordination number / polyhedron | 配位数 / 配位多面体 | 3 三角形、4 四面体、6 八面体、8 立方体、12 立方八面体 |
| [SiO₄]⁴⁻ tetrahedron / shared oxygen | 硅氧四面体 / 共用氧 | 硅酸盐基本单元，净电荷 −4；共用氧数决定聚合度 |
| orthosilicate (island silicate) | 岛状硅酸盐 | [SiO₄]⁴⁻，0 共用氧，例：olivine、garnet |
| sorosilicate / ring silicate | 双岛状 / 环状硅酸盐 | [Si₂O₇]⁶⁻（epidote）/ [Si₃O₉]⁶⁻（beryl、cordierite） |
| single / double chain silicate | 单链 / 双链硅酸盐 | [Si₂O₆]⁴⁻ 辉石 / [Si₄O₁₁]⁶⁻ 角闪石 |
| sheet / framework silicate | 层状 / 架状硅酸盐 | [Si₄O₁₀]⁴⁻ 云母黏土 / [AlSi₃O₈]⁻、SiO₂ 长石石英 |
| isomorphism / polymorphism | 类质同象 / 同质多象 | 结构同化学异 / 化学同结构异 |
| metastable | 亚稳 | 出现在其稳定 P–T 范围之外的相 |
| solid solution / endmember | 固溶体 / 端元 | 如 Fo–Fa、Ab–An、Ab–Or |
| miscibility gap / solvus | 溶线间隙 / 溶线 | 低温下固溶体分离为两相的区域 |
| exsolution / perthite (microperthite) | 出溶 / 条纹长石（微条纹） | 碱性长石降温分离出富 Na 与富 K 条纹 |
| coupled substitution | 耦合替换 | [NaSi]⁵⁺ ↔ [CaAl]⁵⁺（斜长石） |
| forsterite (Fo) / fayalite (Fa) | 镁橄榄石 / 铁橄榄石 | Mg₂SiO₄ / Fe₂SiO₄ |
| albite (Ab) / anorthite (An) / orthoclase (Or) | 钠长石 / 钙长石 / 正长石端元 | NaAlSi₃O₈ / CaAl₂Si₂O₈ / KAlSi₃O₈ |
| sanidine / orthoclase / microcline | 透长石 / 正长石 / 微斜长石 | 冷却速率：快 / 中 / 极慢 |
| plagioclase / alkali feldspar | 斜长石 / 碱性长石 | 前者永无出溶，后者常出溶 |
| augite / pigeonite / diopside / aegirine-augite | 普通辉石 / 易变辉石 / 透辉石 / 霓辉石—普通辉石 | 高 Ca cpx / 低 Ca cpx / CaMg 端元 / 富 Na 淡绿 cpx |
| orthopyroxene (opx) / clinopyroxene (cpx) / enstatite | 斜方辉石 / 单斜辉石 / 顽火辉石 | 平行消光 / 斜消光；enstatite 可有淡粉—淡绿多色性 |
| hornblende / amphibole | 普通角闪石 / 角闪石 | 双链，含 (OH)⁻，解理 ~60° |
| biotite / phlogopite / muscovite | 黑云母 / 金云母 / 白云母 | 层状，一组极完全解理 |
| serpentine / chlorite / sericite | 蛇纹石 / 绿泥石 / 绢云母 | 分别为橄榄石 / 黑云母 / 长石的蚀变产物 |
| titanite (sphene) / apatite / zircon / spinel | 榍石 / 磷灰石 / 锆石 / 尖晶石 | 常见副矿物 |
| relief / pleochroism / pleochroic halo | 突起 / 多色性 / 多色晕 | 多色晕由锆石内 U 衰变的 α 粒子辐射损伤造成 |
| cleavage / fracture | 解理 / 裂纹 | 解理成组平行且平面；裂纹不规则 |
| extinction angle | 消光角 | 消光位时解理迹（或晶棱）与十字丝的夹角 |
| straight / inclined / symmetrical extinction | 平行 / 斜 / 对称消光 | 对应斜方晶系 / 单斜晶系 / 两组解理切面 |
| speckled / undulose extinction | 斑驳消光 / 波状消光 | 云母永不全黑 / 晶格弯曲，变形证据 |
| interference colour / birefringence (δ) | 干涉色 / 双折射率 | Δ = t·δ；olivine 0.035–0.052，augite 0.018–0.033 |
| isotropic / anisotropic; uniaxial / biaxial | 各向同性 / 各向异性；一轴晶 / 二轴晶 | 等轴晶各向同性永远消光；二轴晶有三个多色性颜色 |
| simple / lamellar / cross-hatch twin | 简单 / 聚片 / 格子双晶 | 对应 sanidine-orthoclase / plagioclase / microcline |
| zoning (normal / reverse / oscillatory) | 环带（正 / 反 / 韵律） | 核—边成分变化 |
| modal mineralogy / point counting | 模式矿物组成 / 点计数 | 体积百分比合计 100%；点计数为定量方法 |
| euhedral / subhedral / anhedral | 自形 / 半自形 / 他形 | 晶面发育程度 |
| tabular / acicular / lath / prismatic | 板状 / 针状 / 板条状 / 柱状 | 晶体习性 |
| poikilitic / oikocryst / chadacryst | 嵌晶结构 / 主晶 / 客晶 | 大晶包裹小晶 |
| ophitic / subophitic / interstitial | 辉绿 / 次辉绿 / 填隙 | 普通辉石包裹斜长石板条；填隙者最晚结晶 |
| essential / type / accessory / secondary mineral | 主要 / 类型 / 副 / 次生矿物 | 前两者进岩石名，后两者不进 |
| PPL / XPL | 单偏光 / 正交偏光 | plane-polarized / cross-polarized light |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `W3 notes.md`，Plagioclase 首页 | `(Na,Ca)(Al,Si)Si2O8` | 四面体位阳离子只有 3 个（(Al,Si) + Si₂），长石需 4 个；电荷严重不平衡（代入 Na 得 −4） | 应为 **(Na,Ca)(Al,Si)AlSi₂O₈**。验证：albite = Na+Si+Al+Si₂ = NaAlSi₃O₈ ✓；anorthite = Ca+Al+Al+Si₂ = CaAl₂Si₂O₈ ✓ |
| `W3 notes.md`，Muscovite 标题页 | `K4Al4[Al2Si6O20](OH,F)4` | 电荷不平衡：+4+12−10−4 = **+2** | 应为 **K₂Al₄[Si₆Al₂O₂₀](OH,F)₄**（Deer, Howie & Zussman 的 O₂₀ 基准写法）。同页黑云母 K₂(Mg,Fe)₆[Al₂Si₆O₂₀](OH)₄ 电荷平衡 ✓，可见 K 下标应为 2 |
| `W3 notes.md`，Hornblende 标题页 | `Ca2(Mg,Fe)4Al[Si7O22](OH)2` | 电荷不平衡：+15−16−2 = **−3**；四面体位只有 7 个 Si，缺 1 个阳离子 | 应为 **Ca₂(Mg,Fe)₄Al[AlSi₇O₂₂](OH)₂**（四面体位存在 Al³⁺↔Si⁴⁺ 替换）。验证：+15−13−2 = 0 ✓ |
| `W3 notes.md`，Cations and anions 表 vs [SiO₄] 四面体页 | 前者 `Si4+ … 0.26`（Å）；后者 `Si4+ cation radius in crystal = 0.4 Å … radius ratio = 0.3` | 同一离子两处数值不一致。用 0.26/1.40 = **0.19** 会落入"三配位"区间，与四面体结论矛盾 | 两值来自不同半径体系（Shannon 四配位 0.26 Å vs Pauling 老值 ~0.41 Å）。教学上用 0.4 Å 得 0.3 才自洽。**答题时结论写"Si 恒为四配位"，并说明半径比法只是半定量** |
| `W3 notes.md`，Augite 光性页 vs 20-Oct 转写 | 讲义"Extinction angle … in augites, it is **~35-45°**"；转写"in typical clinopyroxenes, that is somewhere around **30 to 40 degrees**" | 同一参数两个区间 | 两者都在普通辉石实际范围（c∧Z ≈ 35–48°）附近。**建议记"约 35–45°，口试可答 30–45°"**，重点是与角闪石的 15–25° 拉开档次 |
| `W3 notes.md` Olivine 页 vs `EART22201 Reference Guide 2025.md` p16 | 讲义"Interference colours up to **high second order**"；Reference Guide"Birefringence 0.035-0.052: up to **third-order** colours" | 两份材料给的最高阶次不一致 | 二者并不真矛盾：**富 Mg 橄榄石（δ≈0.035）到二级，富 Fe 橄榄石（δ≈0.052）可达三级**。Practical R1 写"低到至少二级黄，取决于切面方位"，与此一致 |
| `W3 notes.md`，Silicate mineral groups 表 | 环状硅酸盐通式 `[Si3O9]6-`，实例 `beryl、cordierite` | 通式对应**三元环**（如 benitoite），而绿柱石与堇青石是**六元环** [Si₆O₁₈]¹²⁻ | Si:O 比相同（均为 1:3），故通式在化学计量上不算错，但**环的元数不同**。答题写实例时最好注明"六元环"，或改举 benitoite 为三元环例 |
| `W3 notes.md`，Chrome diopside 页 | `Ca(Mg,Cr)Si2O6` | 若 Cr 为 Cr³⁺（讲义石榴子石页正是这样定义 Cr³⁺），则该式电荷不平衡（多出 +1） | 铬透辉石实为 **CaMgSi₂O₆ 中含少量 Cr**，Cr³⁺ 进入需与 Al³⁺ 等耦合替换（如 CaCrAlSiO₆ 组分）平衡电荷。讲义写法是简化 |
| `Practical 3 solutions.md`，SW 与 R1 模式含量表 | SW：15+25+40+8+7 = **95%**；R1：40+30+30+1 = **101%** | 与 Practical 自定义"modal mineralogy … **totalling 100%**"不符 | 目估本就有误差，Practical 原文亦提示 ±5–10%。SW 缺的 ~5% 可能是未列出的副矿物/氧化物。**答题时应把各项调整到合计 100%** |
| `Practical 3 solutions.md`，SW 段 vs 273 段 | SW："altered to **a clay mineral** called sericite"；273："**sericite, a muscovite-like white mica**" | 同一文件内对绢云母的归类不一致 | 绢云母是**极细粒白云母（云母族，层状硅酸盐）**，不是黏土矿物。273 的说法正确 |
| `EART22201 Reference Guide 2025.md`，p7 次生矿物举例 | "**serpentite** (alteration of olivine); **chorite** (alteration of biotite)" | 拼写错误 | 应为 **serpentine** 与 **chlorite** |
| `EART22201 Reference Guide 2025.md`，p7 岩石类型表 | 表头把 **andesite / diorite** 归入 "**Mafic** rocks" | 与同文件 p11 的 TAS 分类（SiO₂ 53–62 wt% = **intermediate 中性**）冲突 | 安山岩/闪长岩应为**中性岩**。该表头只是把"非长英质"合并成一栏，读时按 TAS 表为准 |
| `EART22201 Reference Guide 2025.md`，p6–p9 若干处 | "silicaundersaturated"、"the phenocryst **plase**"、"chorite" | PDF 转 md 时的排版/拼写错误 | 分别应为 silica-undersaturated、phase、chlorite。不影响内容 |
| 20-Oct 转写，无色矿物段 | "quartz does not do this — **only feldspars undergo hydrothermal alteration**" | 过度简化 | 正确表述是"**在这三种无色低突起矿物中**只有长石会热液蚀变（成绢云母/黏土），石英不会"。实际上橄榄石、辉石、黑云母同样会热液蚀变（→蛇纹石、绿泥石等），讲义自己也写了 |
| 20-Oct 转写，opx vs cpx 对比段 | "This crystal here is your clinopyroxene. So again, lightly coloured and **first order interference colours**." 随后说 opx "has much **lower** interference colours" | 与讲义（cpx 可达二级中部、opx 一级）冲突 | 很可能是口误或自动转写错字（原意或为 "second order"）。**以讲义为准：cpx 二级、opx 一级** |
| `W3 notes.md`，Feldspars 与 Plagioclase 页 | "Plagioclase feldspars … **NOT found in mantle rocks**" | 过度概括 | 在**浅部（约 <30 km）低压地幔**中存在**斜长石二辉橄榄岩（plagioclase lherzolite）**。教学语境下"典型地幔岩（尖晶石相/石榴石相）中无斜长石"成立，但不宜写成绝对 |
| 20-Oct 转写全文 | "playachroic / playochroic / pleoperoic"、"sheeps"、"u-hedral"、"sanadine"、"gabros"、"orgite"、"klinoperoxene"、"x solution"、"a circular inhabit" | 自动语音识别对矿物学术语的系统性误转 | 正确形式依次为：**pleochroic、sheets、euhedral、sanidine、gabbros、augite、clinopyroxene、exsolution、acicular in habit**。老师本人在课上已提醒转写对矿物名不可靠 |
| `W3 notes.md` 多处 | "General formula: **X SiO 2 4**"、"[Si3O8]3O8]O8]8]]"、"K2(Mg,Fe)6[Al2Si6O20](OH)42(Mg,Fe)6…"、"cation radius radius ratio = anion radius" | PDF 转 md 时下标/上标丢失与字符重复 | 分别应为 **X₂SiO₄**、**[AlSi₃O₈]⁻**、**K₂(Mg,Fe)₆[Al₂Si₆O₂₀](OH)₄**、**radius ratio = cation radius / anion radius**。属转换伪影，非原讲义错误 |
