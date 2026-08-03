# EART26201 Principles of Geochemistry — Week 04 学习笔记

## 一、本周主题

**本周主题：熔融与结晶的相图应用（Melting and crystallisation in geochemical systems: phase diagram applications）——二元相图的三种基本类型及其在岩浆系统中的读法。**

这一判断来自材料本身：讲义 `EART26201_Lecture4_RT_v2.md` 首页标题即为 "Melting and crystallisation in geochemical systems: phase diagram applications"，其 synopsis 把本讲分成五个部分：

- Part 1 | Introduction（相图从哪里来：实验岩石学）
- Part 2 | Phase diagrams without solid solution（无固溶体的二元相图：**An–Di**，共结点 eutectic）
- Part 3 | Phase diagrams with a solvus（带溶线的二元相图：**Ab–Or**，出溶 exsolution）
- Part 4 | Pyroxenes and exsolution（辉石 **Di–En** 体系：溶线与共结点相交，冷却速率控制结构）
- Part 5 | Phase diagrams with a peritectic（带包晶点的二元相图：**Fo–Qz**）

延伸阅读：White, Chapter 4（Phase diagram construction）。Practical 4 的标题也完全对应：**"Applying phase diagrams to magmatic systems"**（Dr David Neave），两道题分别是 An–Di（无固溶体）与 Fo–Qz（含包晶）。课堂 transcript 开头也确认："like last week, we are going to talk about thermodynamics and phase diagram… we'll take a step up from last week in terms of looking at phase diagrams that are a bit more complicated."

**在全课骨架中的位置。** 本课的四大块是：热力学与相图 / 反应动力学与扩散 / 酸碱溶解度与氧化还原 / 放射性与稳定同位素。本周属于**第一块的下半段**——上周（Week 03）建立了热力学与**含固溶体**相图（斜长石 Ab–An）的基本读法，本周把工具升级到三类更复杂的二元体系（共结、溶线、包晶），并第一次把相图**直接对应到岩石薄片中看得见的结构**（出溶片晶、反式易变辉石、均一晶体）。老师在课上明确说下一讲（Lecture 5）要讲动力学（kinetics），本讲末尾关于"出溶取决于冷却速率"的讨论正是通往第二块的桥梁。

> 📎 背景补充：**关于周次编号。** 课程大纲（spec）把 "Reactions in geochemical systems: thermodynamics and phase diagram principles" 列在 Week 4、把 "Melting and crystallisation… phase diagram applications" 列在 Week 5；而本文件夹的 Week 4 讲义标题恰是后者。这是已知的"大纲周次含 reading week、文件夹周次连续"造成的错位。本笔记库一律采用**文件夹编号**，故本篇是 Week 04，内容为"相图应用"。同理，大纲把 "Phase diagrams of magmatic systems (paper based)" 排在 Week 5 practical，与本周 Practical 4 的实际标题一致。

---

## 二、核心概念

### 1. 相图是干什么用的：从岩石反推 P–T–X

老师用一张冰岛玄武岩（Icelandic basalt）薄片开场：同一块岩石里，斜长石**晶核（core）**测出 X_An = 0.9，而**基质（groundmass）**中的斜长石只有 X_An = 0.4。对照斜长石二元相图立刻可以读出：富钙的核部结晶于**高温**，富钠的基质斜长石结晶于**较低温**。这就是相图的核心用途——

> "we can use these phase diagrams to estimate the pressure, temperature and chemistry conditions under which magma crystallises."

相图把**压力、温度、成分**三者与**可观察的矿物组合与成分**连接起来。

### 2. 相图从哪里来：实验岩石学（experimental petrology）

要画相图必须先有热力学数据库，而数据库的重要来源是实验。流程（transcript）：

1. 从**氧化物粉末**（oxide powders）出发，按想要的比例研磨、混合；
2. 装入**密封胶囊**（capsule）；
3. 放进可控温压设备——例如**活塞-圆筒装置（piston cylinder）**——加热到目标温度并施加压力；
4. 淬火后分析产物，确定在该 P–T–X 下有哪些相、各相成分如何。

老师强调两点：这类实验**很贵**（"it often costs quite a bit of money"），但必须做，因为要用于**预测模型**；最大的应用之一是**火山灾害（volcanic hazards）**预测——能更准确预报喷发时间，所以有资助机构愿意付钱，"which is here to save people's life"。

### 3. 组分、相、自由度（component / phase / variance）

- **组分（component）**：描述体系全部成分所需的最少化学实体数，在二元图上就是横轴两端的两个端元。
- **相（phase）**：物理化学性质均一、有确定边界的部分。熔体算一个相；每一种矿物算一个相；**固溶体（solid solution）**在溶线以上算一个相（成分连续可变），溶线以下则分裂为两个成分不同的固溶体相。
- **自由度 / 变数（variance, F）**：在不改变体系相组合的前提下可以独立改变的强度变量数目。

课堂上以 An–Di 图为例逐区讨论（压力已固定为 1 atm）：液相线之上只有熔体；液相线上是熔体 + 一种固相，**单变（univariant）**；**共结点是不变点（invariant point, F = 0）**——"you cannot change the temperature or the composition without changing the state of the system"。这正是共结点处**温度被钉死**的原因。

> 📎 背景补充：**Gibbs 相律**（材料未写出公式，只用了 variance 一词）：F = C − P + 2；当压力被固定（相图标注 1 atm）时退化为 **F = C − P + 1**。代入 An–Di：液相线以上 C=2、P=1 → F=2（**双变 divariant**，T 与 X 都可自由改变）；液相线上 C=2、P=2 → F=1（单变）；共结点 C=2、P=3（L+An+Di）→ F=0（不变）。⚠️ 课堂 transcript 说"液相线之上 variance 为 1"，与相律不符，见文末勘误表。

### 4. 液相线、固相线与相区

- **液相线（liquidus）**：温度-成分空间中"开始出现第一颗晶体"的界线；其上全为熔体。
- **固相线（solidus）**："最后一滴熔体消失"的界线；其下全为固体。在无固溶体的 An–Di 体系里，固相线就是通过共结点的那条**水平线**（1274 °C）。
- An–Di 图自上而下的四个区：**L**（熔体）、**An + L**（左）、**Di + L**（右）、**An + Di**（共结温度以下）。

### 5. 共结点（eutectic）

共结点是液相线的**最低温交点**，反应式为

**L = An + Di**（更一般地：L = 固相1 + 固相2）

它是不变点：结晶到共结点后，**温度停住不再下降**，熔体在恒温下同时析出两种矿物，直到熔体耗尽为止。An–Di 体系的共结点在 **1274 °C**，成分讲义写作 An40Di60（practical 用更精确的 X_Di = 0.58，即 An42Di58）。

### 6. 包晶点（peritectic）与不一致熔融（incongruent melting）

包晶反应的形式是 **Fo + L = En**，即

> "a peritectic reaction is basically a reaction where you consume a mineral you've just produced."

对比记忆：
- **共结（eutectic）**：L → 两种矿物（液体消失，产物只增不减）
- **包晶（peritectic）**：先结晶出的矿物 **被回吃**，与熔体反应生成第三种矿物

**不一致熔融（incongruent melting）**：老师给的操作性定义是"你产生的第一批熔体成分落在体系成分之外"。以 Fo–Qz 为例：从 Fo + En 组成的固体升温，第一滴熔体成分 L2 落在 **En–Qz** 区间而不是 En–Fo 区间。Practical 的写法更直观：**"the solid En melts incongruently to produce L and Fo"**——顽火辉石熔化时不是变成同成分的熔体，而是分解为**橄榄石 + 更富硅的熔体**。

> 📎 背景补充：严格教科书定义中，"不一致熔融"指某一矿物加热时熔化为**成分不同的熔体 + 另一种固相**（En → Fo + L），课堂那句"第一批熔体在体系成分之外"是它在相图上的等价表现，两者说的是同一件事。

### 7. 溶线（solvus）与出溶（exsolution）

**溶线**是固溶体的**混溶间隙（miscibility gap）**边界。成因（课堂原话）：

> "at high temperature it's easy to have solid solution between albite and orthoclase, but at lower temperature it's a lot harder to get good mixing."

即**高温下固溶广泛、低温下固溶受限**。溶线之下，一个均一固溶体在平衡时必须分解为**两个成分不同的固溶体相**共存。

**出溶（exsolution）**："the separation of different solids from a single solid phase"——在已经固结的晶体内部析出**片晶（lamellae）**，也就是"在第一个矿物内部长出第二个矿物"。随着继续降温，出溶体越来越富 Or，寄主越来越富 Ab（Ab–Or 体系），两者比例由**杠杆规则**给出。

**关键**：出溶是固态扩散过程，**需要时间**——"the extent to which these occur depends on cooling rates and kinetics"。这就把相图和岩石结构、岩浆房尺度连了起来（见下节）。

### 8. 四种过程：平衡结晶 / 分离结晶 / 平衡熔融 / 分离熔融

这是全周最需要背熟的框架。两条黄金法则（课堂反复强调）：

- **平衡（equilibrium）过程**：晶体始终与熔体保持接触与反应，**体系最终成分 = 初始成分**。平衡熔融是平衡结晶的**严格逆过程**。
- **分离（fractional）过程**：产物一形成就被移走（晶体被抽离，或熔体被抽离），于是**"体系的成分 = 剩下那一相的成分"**。
  - 分离结晶：**体系成分 = 熔体成分**，熔体一路沿液相线走到**共结点**为止，"last liquid is always at the eutectic"。
  - **分离熔融不是分离结晶的逆过程**（讲义与课堂各强调了一次）。分离熔融中熔体被不断抽走，残余固体成分被推向**难熔端元**，最后一滴熔体是**纯的难熔端元成分**。

### 9. 冷却速率 → 结构 → 岩浆房尺度（辉石的应用）

Di–En 体系是本讲最漂亮的应用：同一条相图路径，只因**冷却速率**不同，产出三种截然不同的薄片结构：

| 冷却速率 | 相图上走到哪 | 薄片中看到什么 | 对应地质环境 |
|---|---|---|---|
| 慢冷（≈平衡） | 一路走完，易变辉石发生相变 → 斜方辉石 | 普通辉石与斜方辉石互相出溶片晶；**"反式易变辉石"（inverted pigeonite）**，厚的普通辉石片晶 | **大型**化石岩浆房（fossil magma chamber） |
| 中等冷却（近平衡） | 出溶开始但未走完；易变辉石**不**发生相变 | 普通辉石与易变辉石互相出溶，**薄**片晶，无斜方辉石 | **小型**岩浆房 |
| 快冷（远离平衡） | 在共结点被"冻住"，无出溶 | **均一（homogeneous）**的普通辉石/易变辉石晶体，保留共结点时的成分 | 火山岩、熔岩；岩墙（dikes）与岩床（sills）等小通道 |

即：**看到什么结构，就能反推岩浆冷却速率与岩浆房规模**——"this is useful to go and relate a rock to what sort of environment it formed in."

---

## 三、公式与图表

本节是本周重点。相图这一段务必读到**能自己默画**为止。

### 0. 通用工具

**（1）Gibbs 相律** 📎 背景补充（材料只用了 variance 概念，未给公式）：

```
F = C − P + 2          （P、T 均自由）
F = C − P + 1          （压力固定，等压相图，如本周全部图件均标 1 atm）
```

- F = 自由度（variance），无量纲；C = 组分数；P = 相数。
- 适用条件：平衡态、不考虑表面能与外场。
- 典型值（An–Di，1 atm）：熔体区 F=2；液相线 F=1；共结点 F=0。

**（2）杠杆规则（lever rule）** —— 材料反复使用但未写出公式，以下代数形式为 📎 背景补充，数值算例均取自材料：

设体系整体成分为 X₀，某温度下共存两相成分分别为 X_A、X_B（同一横轴刻度），则

```
f_A = (X₀ − X_B) / (X_A − X_B)
f_B = (X_A − X₀) / (X_A − X_B)      且 f_A + f_B = 1
```

口诀：**某一相的比例 ∝ 从体系点到"对面那一相"的线段长度**（杠杆的另一臂）。

- 单位：质量分数（本周图件横轴为组分的质量/摩尔分数，图上直接量长度即可）。
- 适用条件：**只在两相共存区内使用**，且两相成分点必须与体系点在同一条等温水平线上。

**算例 1（An–Di，取自 Practical Q1c-i）**：X_Di = 0.8 的熔体冷却到共结温度 1274 °C 的瞬间，共存的是共结熔体（X_Di = 0.58）与纯 Di（X_Di = 1.0）。

```
f_L = (0.8 − 1.0)/(0.58 − 1.0) = 0.2/0.42 = 0.476 ≈ 48%
f_Di = (0.58 − 0.8)/(0.58 − 1.0) = 0.22/0.42 = 0.524 ≈ 52%
```

（Practical 给的是 45% 液 / 55% Di，属图上目测的近似，见勘误表。）

**算例 2（共结点上析出的固体比例）**：共结熔体 X_Di = 0.58 分解为纯 An（0）与纯 Di（1.0）：f_An = 42%，f_Di = 58% ✅ 与 practical 完全一致。

**算例 3（Fo–Qz，Practical Q2c-i 第 6、7 步）**：共结熔体 X_Qz = 0.42 析出 En（X_Qz = 0.30）与 Qz（1.0）：

```
f_En = (0.42 − 1.0)/(0.30 − 1.0) = 0.58/0.70 = 83%
f_Qz = 17%                                    ✅ 与 practical 一致
```

最终全岩（X₀ = 0.32）由 En 与 Qz 组成：f_En = (0.32−1.0)/(0.30−1.0) = 0.68/0.70 = **97%**，f_Qz = **3%** ✅ 与 practical 一致。

### 1. 斜长石 Ab–An 图（上周回顾，Slides 6–8）

- **横轴**：钠长石 Ab ←→ 钙长石 An（X_An）；**纵轴**：温度 T；压力固定。
- 图形：上凸的**液相线**与下方的**固相线**围成一个"透镜形"两相区（**plag + L**），两线只在两个端元处相交——这是**完全固溶体**的标志，没有共结点。
- **平衡结晶**：熔体降温至 T1 交液相线 → 析出第一颗 plag₁（成分**最富 An**，位于同一水平线上固相线一侧）；继续降温，熔体沿液相线（L1→L2→L3）、固体沿固相线（plag1→plag2→plag3）**同步向富 Ab 方向移动**；**最后一颗斜长石的成分 = 最初熔体的成分**（体系成分守恒）。
- **平衡熔融**：完全反向。
- **分离结晶**：第一颗晶体相同，但晶体一形成就被移走 → 体系成分 = 熔体成分 → 熔体可一路走到 **Ab 端元**，最后结晶的是**纯钠长石**。
- **分离熔融**：熔体不断被抽走，残余固体被推向 **An 端元**。

### 2. An–Di 图：无固溶体 + 共结点（Slides 9–13，Practical Q1）

**画法要点（据 practical 图件文字重建）**：

- **纵轴** T（°C），范围约 1200–1600；**横轴** X_Di 从 0（左端 **An = CaAl₂Si₂O₈**）到 1（右端 **Di = CaMgSi₂O₆**）；标注 **1 atm**。
- 左上角顶点：An 熔点 **1553 °C**；右上角顶点：Di 熔点 **≈1390–1392 °C**。
- 两条液相线从两个熔点向下相交于 **共结点 1274 °C，X_Di = 0.58**（讲义简化为 An40Di60）。
- 通过共结点画一条**水平的固相线**贯穿全图。
- 四个相区：上方 **L**；左侧 **An + L**；右侧 **Di + L**；1274 °C 以下 **An + Di**。
- 关键：两端元**没有固溶**，析出的固相永远是**纯 An** 或**纯 Di**（成分点固定在 0 或 1）。

**三条平衡结晶路径（讲义 Slide 10 + 课堂）**：

| 初始成分 | 过程 | 终态 |
|---|---|---|
| An40Di60（= 共结成分） | 直接冷却到 1274 °C，**L → An + Di**，恒温直到熔体耗尽 | 40% An + 60% Di |
| An70Di30 | 先交左侧液相线，**L → An**（纯钙长石）；熔体沿液相线向右下滑向共结点；到 1274 °C 后 **L → An + Di** 恒温结晶至熔体耗尽 | 70% An + 30% Di（= 初始成分） |
| An20Di80 | 先交右侧液相线，**L → Di**；熔体沿液相线向左下滑；到共结点后 **L → An + Di** | 20% An + 80% Di |

**分离结晶（Slide 11）**：前半段路径完全相同，区别在于晶体被移走 → "the composition of the system is the composition of liquid"；因此无论从哪一侧出发，**最后一滴熔体永远在共结点**，最终固体聚集体成分 = 共结成分（An40Di60 / An42Di58）。两侧的唯一差别是**结晶顺序**：从右侧出发先出 Di 后出 An，从左侧出发先出 An 后出 Di。老师特地指出这在野外/薄片里是可判别的——"if you can see in your rock that diopside is the first phase to form, you know you're on the right hand side."

**分离熔融（Slide 12，以 An70Di30 为例）**：

```
An + Di →(1274 °C 共结) L        直到 Di 耗尽（因为起始 Di 少）
An      →(沿液相线升温) L        直到 An 耗尽
最后一滴熔体 = 纯 An，在 1553 °C
```

**⇒ 分离熔融 ≠ 分离结晶的逆过程。**

**与真实岩石的对应（Slide 13）**：深色基质中带斜长石斑晶的玄武岩 ≈ 从 An 一侧（图中紫色路径）冷却；斜长石与单斜辉石**交生（intergrown）**的玄武岩 ≈ 接近**共结成分**结晶。

### 3. Ab–Or 图：带溶线（Slides 16–19）

- **横轴**：Ab（钠长石）←→ Or（正长石 orthoclase）；**纵轴** T。
- 形态：**上半部是一个像斜长石那样的固溶体透镜（liquidus + solidus）**，但两条液相线在中部下凹相交，形成一个**共结（eutectic / 最低点）**；**下半部是一个圆穹形的溶线（solvus）**，穹顶以下为两种碱性长石固溶体共存区。课堂原话：这类图"sort of a mix of the plagioclase phase diagram and the one we just did"（介于有/无固溶体两者之间）。
- 相区标注用 **afs_ss**（alkali feldspar solid solution，碱性长石固溶体）。溶线以下写作 "Ab-rich afs_ss + Or-rich afs_ss"。

**平衡结晶路径（Slide 18）**：

1. 熔体 L 冷却，于 **T1（课堂读数 1150 °C）**交液相线，析出第一批**富 Ab 的碱性长石**；
2. 熔体（L1→L2）与固体沿液相线/固相线**同时向富 Or 方向移动**，直到**固体成分追上体系成分**（此时熔体耗尽）；
3. 全固态后继续降温，在 **T3** 与**溶线**相交；
4. 溶线以下，**富 Or 的碱性长石从富 Ab 的寄主中逐步出溶**；温度越低，出溶体越富 Or、寄主越富 Ab（两条溶线分支越张越开）；
5. 任一温度下两者比例由**杠杆规则**给出（Slide 18 上标出的线段 **a** 与 **b** 即两条杠杆臂）；
6. 体系总成分自始至终不变。

**分离结晶路径（Slide 19）**：

1. 同样先析出富 Ab 的碱性长石，但立即移出体系 → **液 = 体系**；
2. 于是"nothing prevents your liquid to go all the way down to this eutectic point"——熔体一路走到**共结点**；
3. 在共结点结晶完毕，之后降温交溶线，同样发生出溶（若达到平衡）；
4. **一旦全固态，体系成分不能再变**——所以最终体系成分 = **共结点成分**。

**是否真的出溶，取决于冷却速率**（讲义 Slide 19 末尾直接预告用辉石来讲）。

> 📎 背景补充：Ab = NaAlSi₃O₈，Or = KAlSi₃O₈（材料未给化学式）。这类"溶线与固相线相交"的碱性长石体系产出的**条纹长石（perthite）**——富 Or 寄主中的 Ab 片晶，或反条纹长石（antiperthite）——正是本节出溶机制在花岗质岩石中最常见的产物。材料未使用 perthite 一词。

### 4. Di–En 辉石图：溶线与共结点相交（Slides 22–29）

- **横轴**：En（顽火辉石，富镁辉石）←→ Di（透辉石，富钙镁辉石）；**纵轴** T；**1 atm**。
- 形态：课堂称为 **"rabbit ears"（兔耳形）**——因为图顶部有两个耸起的液相线"耳朵"，中间夹一个共结点。其成因是**溶线（两辉石混溶间隙）向上侵入并与共结点相交**。
- **组分数 = 2**（En、Di）；**相数 = 4**：斜方辉石固溶体 **Opx_ss**（左下）、**易变辉石 Pigeonite (Pig_ss)**（左侧中部）、**普通辉石 Augite (Aug_ss)**（右侧）、**熔体**。
- 关键关系：**易变辉石比斜方辉石稳定在更高温度**（"pigeonite is stable at higher temperature than orthopyroxene"）；左下角存在一个**全固态的不变点**，Di 较富的易变辉石在此**相变（inversion）**为 Di 贫的斜方辉石。
- 相区（课堂点名）：Pig + Opx、L + Pig、Pig + Aug 等。

**慢冷（平衡）完整路径（Slide 23）**：

1. 从右侧熔体开始降温 → **T1** 交液相线，第一颗固相是**富 Di 的普通辉石（augite）**；
2. 熔体与普通辉石成分**同步向 En 方向移动**；
3. **T2** 熔体到达**共结点**：开始同时结晶**贫 Di 的易变辉石**与**富 Di 的普通辉石**，恒温直到熔体耗尽；
4. 全固态后继续冷却，两种辉石**互相出溶**：普通辉石越来越富 Di，易变辉石越来越贫 Di（沿各自的溶线分支走）；
5. **T3** 到达左侧那个不变点：**富 Di 的易变辉石相变为贫 Di 的斜方辉石**；
6. 之后斜方辉石与普通辉石继续互相出溶，成分继续调整，直到低温下扩散停止；
7. 因为是平衡过程，**体系最终成分 = 初始成分**。

**中等冷却（Slide 24）**：第 1–4 步相同，但**出溶来不及走完**（动力学限制），体系被"冻"在中途；**易变辉石不发生向斜方辉石的相变**。

**快冷（Slide 25）**：走到共结点后**完全冻结，不发生任何出溶**；普通辉石与易变辉石都是**均一晶体**，保留共结点时的成分——课堂给的读数：**易变辉石 ≈ En80，普通辉石 ≈ En 略高于 20**。

**结构 ↔ 环境对照**（Slides 26–29，含文献出处 McDonald et al. 2017；Humphreys & Holness 2010）见"二、核心概念"第 9 点的表。

### 5. Fo–Qz 图：带包晶点（Slides 31–35，Practical Q2）

**完整图（据 practical 图件文字重建）**：

- **纵轴** T，约 1500–1900 °C；**横轴** 从 **Fo（Mg₂SiO₄）**到 **Qz（SiO₂）**，中间 **En（MgSiO₃）**位于 **X_Qz = 0.30**；标注 **1 atm**。
- 左端顶点：Fo 熔点 **≈1890 °C**。
- **包晶点（peritectic）**：**Fo + L = En**，温度 **≈1557–1565 °C**（practical 用 ~1565 °C，课堂读数 "1560"）。
- **共结点（eutectic）**：**L = En + Qz**，温度 **≈1540 °C**，熔体成分 **X_Qz = 0.42（X_Fo = 0.58）**。
- 右上方有一个 **"2L"** 区——**两个不混溶熔体共存**的区域（图件中标在约 1700–1800 °C 的富硅一侧）。
- 相区：**L**、**L + Fo**、**L + En**、**L + Qz**、**Fo + En**、**En + Qz**。
- **教学简化**：只看 **X_Qz ≤ 0.5** 的左半部（"we'll split it at SiO₂ equals 50%"），practical 称之为 **zoomed-in diagram**，并再三提醒"右端只到 0.5 Qz，En 在 X_Qz = 0.3"。

> 📎 背景补充：**为什么 En 落在 X_Qz = 0.30？** 因为 Mg₂SiO₄ + SiO₂ → Mg₂Si₂O₆（= 2 MgSiO₃），按分子量 Fo = 140.7、SiO₂ = 60.1，则 SiO₂ 的质量分数 = 60.1/(140.7+60.1) = **29.9% ≈ 0.30** ✅ 与材料一致。这也解释了为什么 En 是 Fo 与 Qz 的"中间化合物"。
>
> 📎 背景补充：图上写作 Qz 的高温相实际是**方石英（cristobalite, Cr）**——practical 的脚注与讲义 Slide 32–34 的 "Cr + L"、"En + Cr" 标注都用了 Cr。方石英是 SiO₂ 的高温同质多象（polymorph）。⚠️ 课堂说"1400 °C 以上就是方石英"，数值需修正，见勘误表。

**路径 A：平衡结晶，X_Qz = 0.32（落在 En 与 Qz 之间，Practical Q2c-i）**

```
1. ~1580 °C  交液相线，析出 Fo
2.           熔体沿液相线向富 Qz 方向演化，继续析出纯 Fo
3. ~1565 °C  到达包晶点：Fo + L = En，恒温反应
             谁先耗尽？体系 X_Qz = 0.32 > En 的 0.30 → Fo 先耗尽，残留 L + En
4.           熔体沿 L+En 液相线继续向富 Qz 演化，析出 En
5. ~1540 °C  到达共结点，熔体 X_Qz = 0.42；此刻 L : En ≈ 20 : 80（杠杆规则精算 17 : 83）
6.           恒温共结结晶：En : Qz = 83 : 17，直到熔体耗尽
7.           最终固体 En : Qz = 97 : 3，整体成分回到 X_Qz = 0.32 ✅（平衡过程的必然结果）
```

**判断包晶点上"谁先耗尽"的两种方法**（课堂明确给出）：
1. 用**杠杆规则**算；
2. 更快：利用"**平衡结晶终态 = 初始成分**"倒推——把体系成分点垂直投影到底部，看它落在哪个双固相区（Fo+En 还是 En+Qz），就知道最后剩哪两种矿物，从而知道谁被吃光。

**路径 B：平衡结晶，X_Qz < 0.30（落在 Fo 与 En 之间；课堂主讲的例子 + Practical Q2d 的 0.28）**

到达包晶点后同样发生 Fo + L = En，但这次**熔体先耗尽**，反应在包晶点终止；**最后一滴熔体在包晶点结晶**，最终岩石 = **Fo + En**（且 En 多于 Fo，视具体成分而定）。

**路径 C：分离结晶，X_Qz = 0.32（Slide 34，Practical Q2c-ii）**

```
1. ~1580 °C  析出 Fo，但立即移出体系 → 体系成分 = 熔体成分
2.           熔体到达包晶点，但 **包晶反应无法发生**：
             "you can't have a peritectic reaction because you have no forsterite" —— 熔体不再与 Fo 接触
3.           熔体越过包晶点，成分从 L2 直接走到 L3，改为析出 En（同样被移走）
4. ~1540 °C  到达共结点，此时体系 = 纯共结成分熔体（X_Qz = 0.42）
5.           共结结晶 En : Qz = 83 : 17，直到熔体耗尽
6.           最后形成的固体 = En : Qz = 83 : 17 ≠ 初始熔体成分
```

**这是本讲最重要的对比**：包晶反应能否发生，取决于**先结晶的矿物是否还留在体系里**。

**路径 D：分离熔融，X_Qz = 0.32（Practical Q2c-iii）**

```
1. ~1540 °C  第一滴熔体在共结点产生（成分应为 X_Qz = 0.42，practical 此处写错，见勘误），随即被抽走
2.           共结熔融继续，残余固体的 Qz 组分越来越少
3.           当残余固体成分 = En 时，共结熔融停止（Qz 耗尽）
4.           1540 → 1565 °C 之间不发生熔融
5. ~1565 °C  En 发生**不一致熔融**：En → L + Fo
6.           En 耗尽后只剩 Fo（熔体已全部抽走）
7.           1565 → 1890 °C 之间不发生熔融
8. ~1890 °C  Fo 熔化，最后一滴熔体是纯 Fo 成分
```

**注意分离熔融的典型特征：出现两段"什么都不发生"的升温间隔**——因为不变点上的反应一旦把某个相吃光，就必须继续升温才能触发下一个反应。

**平衡 vs 分离：一张对照总表**

| | 体系成分等于什么 | 最后一滴熔体在哪 | 终产物 | 是否互为逆过程 |
|---|---|---|---|---|
| 平衡结晶 | 恒等于初始体系成分 | 共结点（或包晶点，视成分而定） | = 初始成分 | 与平衡熔融**互逆** |
| 分离结晶 | = 剩余熔体的成分 | **永远在共结点** | ≠ 初始成分 | — |
| 平衡熔融 | 恒等于初始体系成分 | — | = 初始成分 | 与平衡结晶**互逆** |
| 分离熔融 | = 残余固体的成分 | — | 残余趋向最难熔端元 | **不是**分离结晶的逆过程 |

### 6. 包晶反应在自然界罕见吗？（Slide 35）

讲义直接给结论：**"Peritectic reactions are rarely observed in natural magmas"**，原因是**分离结晶占主导**——晶体常因重力沉降等被移出，不再与熔体接触，包晶反应就没有反应物。因此自然界的演化是：

**玄武岩（basalt，富 Fo/橄榄石）→ …… → 英安岩（dacite，En + Qz 组合）**，"start Fo rich but end Fo free"。

---

## 四、课堂补充

以下内容来自 5,456 词的完整课堂录音转写，是**讲义幻灯片上没有或只有关键词**的口头讲解。

### 1. 开场：相图不是抽象工具，是读岩石的钥匙

老师先用冰岛玄武岩的**斜长石环带**做锚点：核部 X_An = 0.9、基质 X_An = 0.4，直接对应相图上的高温端与低温端。这是全讲的"为什么要学"——相图的最终目的是**回答岩石学问题**（"how we actually use those to solve some petrology questions"）。他还预告：周三的 practical 才是真正练手的地方，"it's always easier when you do it yourself rather than listening to me explaining these diagrams"。

### 2. 实验岩石学的细节与"钱"的问题

讲义 Slide 3 只有一个标题 "Using experiments to construct phase diagrams"，全部内容都是口头讲的：

- 岩浆是**多元复杂体系**，含大量元素；实验必须在**已知 P、T、成分**下做，才能反推自然界发生了什么反应；
- 实验步骤：氧化物粉末 → 研磨混合 → **封入胶囊** → **piston cylinder（活塞-圆筒）**加温加压；
- 这类研究**很花钱**，但因为直接服务于**火山灾害预报**（预测喷发时间、"save people's life"），所以有资助来源；
- 系里的 **David**（即 practical 的 Dr David Neave）就是做实验岩石学的——这也解释了为什么 practical 由他带。

### 3. 自由度的口头推演（考点提示）

老师在 An–Di 图上逐区问"variance 是多少"，并明确说共结点是**不变点**、液相线是**单变**。他把不变点的物理意义讲得很实在：

> "at this point, you cannot change the temperature or the composition without changing the state of the system… the system will stay at that temperature until all your liquid is crystallised."

**这就是"共结平台"（恒温结晶段）的来源**——考试里常问"为什么温度会停住"，答案就是 F = 0。（⚠️ 他对"液相线之上 variance = 1"的口误见勘误表，正确应为 2。）

### 4. 逐条路径的口头细节（讲义上只有一行字的部分）

- An40Di60（= 共结成分）冷却：**直接降到 1274 °C，然后恒温直到全部结晶**，产物就是 40% An + 60% Di。这是"极端情形"，用来先建立直觉。
- An70Di30 冷却：在**中途某温度**（transcript 记作"1200 度"，应为共结温度以上，见勘误）体系为 **L + An**，两者比例"given by the lever rule"——**杠杆规则不是只在特定点用，而是在整个两相区内随时可用**。
- 分离结晶：两侧出发终点相同（共结成分），**唯一差别是结晶顺序**；老师明确说这是野外可判别的证据（先出 Di ⇒ 起始成分在共结点右侧）。
- 分离熔融 An70Di30：**Di 先耗尽，因为一开始它就少**——这个"谁少谁先没"的判断法很实用。

### 5. 溶线为什么存在（讲义完全没写）

> "at high temperature it's easy to have solid solution between albite and orthoclase, but at lower temperature it's a lot harder to get good mixing. And so we form these solvus."

即高温下熵驱动混合、低温下端元之间的**结构/离子半径差异**使混溶变得困难。老师还顺手解释了 **ss 下标记号**（X_ss = solid solution）与"什么叫出溶"：

> "you've got a crystal and you're going to start forming small lamellae in your crystal. So you basically form a second mineral inside a first mineral."

### 6. 辉石图：老师自己承认"这些不简单"

- 他称这类图为 **"rabbit ears"**（因顶部两个耸起的相区），并解释其成因是**溶线与共结点相交**——一句话点破 Ab–Or 与 Di–En 两张图的血缘关系。
- **易变辉石（pigeonite）比斜方辉石稳定在更高温**，因此慢冷时才有"易变辉石 → 斜方辉石"的相变；
- 快冷时被冻结的成分读数：**Pig ≈ En80，Aug ≈ En 略大于 20**；
- 薄片解读：**深色矿物是斜方辉石，它"曾经是易变辉石"**，里面有普通辉石出溶——这就是 **inverted pigeonite（反式易变辉石）**，只见于**很大的化石岩浆房**；
- 中等冷却：普通辉石中含**细的易变辉石出溶片晶**，见于**较小的岩浆房**；
- 快冷：**均一晶体**，见于火山岩、以及 **dikes（岩墙）与 sills（岩床）**这类"熔岩快速冷却的小通道"。
- 讲完这一段他专门停下来问："Okay, any question on these? These are not super straightforward."——这是老师自己标出的难点。

### 7. 包晶：定义 + 为什么自然界看不到（互动提问）

- 包晶的一句话定义（口头，讲义无）："**a reaction where you consume a mineral you've just produced**"；与共结对照记："eutectic is liquid gives two minerals; peritectic involves consuming a mineral you've just produced"。
- **不一致熔融（incongruent melting）**：老师说"don't worry if you forget instantaneously about it, but you might see the word"——即**认得即可**，定义是"第一批熔体的成分落在体系成分范围之外"。
- **课堂提问**："do you have any idea why we don't see peritectic reactions?" 他自己给出答案，并明确指向**第 2 周讲结晶时的结论**：**大多数岩浆按分离结晶演化**，晶体被移出后不再与熔体接触，包晶反应无法进行。
- 结果：自然界的岩浆演化"start Fo rich but end Fo free"，从**富镁橄榄石的玄武岩**演化到**由 En + Qz 组成的英安岩（dacite）**。

### 8. 方石英的命名说明

图上标 Qz，但"because we're at high temperature… the name of the polymorph is actually cristobalite, but that's a very minor point"。老师自己判定这是**次要细节**——但 practical 的脚注也专门写了同样的提示，说明它可能作为"细心分"出现。

### 9. 反复出现的口头强调（可直接当考点清单）

1. **平衡结晶终态 = 初始体系成分**（至少说了三次，并用它反推包晶点上谁先耗尽）；
2. **分离结晶时"体系成分 = 熔体成分"**，最后一滴熔体永远在共结点；
3. **分离熔融不是分离结晶的逆过程**（讲义与课堂各强调一次）；
4. **平衡熔融是平衡结晶的严格逆过程**；
5. 杠杆规则**在任何两相区、任何温度都能用**；
6. **出溶程度由冷却速率/动力学控制**，并预告 Lecture 5 讲动力学。

---

## 五、Practical 要点

**题目**：Practical 4 — *Applying phase diagrams to magmatic systems*（Dr David Neave），**纸笔练习**，两题：Q1 约 40 分钟，Q2 约 80 分钟。老师鼓励**边做边互相讨论**，助教（demonstrators）全程在场，课末有 round-up，反馈发在 Blackboard。答案建议直接打进文档，并在**空白相图**上标注。另有一个 **Blackboard quiz** 覆盖本周其他主题。

**目标（Goals，原文五条）**：
1. 在二元相图上标出**固相线、液相线与各相区**；
2. 解读**无固溶体**的简单二元相图；
3. 解读**含包晶**的二元相图；
4. 用相图解释**平衡/分离**的结晶与熔融；
5. 在不同相图上用**杠杆规则**求相比例。

材料明确指出这些主题会在 **EART22200（Igneous Minerals and Processes）**与 **EART24200（Metamorphic Minerals and Processes）**中再次遇到。

### Q1：An–Di（无固溶体），X_Di = 0.8

**a) 标注**：液相线与固相线；**L**、**L+An**、**L+Di**、**An+Di** 四个相区；共结点（反应 **L = An + Di**）。
**b)** 在图上标出 X_Di = 0.8（20% An + 80% Di）。

**c-i 平衡结晶（五步式标准答法）**
1. **~1355 °C** 析出第一批 **Di**；
2. 熔体沿液相线演化，**Di 组分逐渐降低**；
3. 到 **1274 °C** 共结点时，L : Di = 45 : 55（feedback 数值；杠杆规则精算 ≈ 48 : 52），熔体成分 **X_Di = 0.58**；
4. 共结恒温结晶，产出 **An : Di = 42 : 58**，直到熔体耗尽；
5. 最终固体 **20% An + 80% Di**（= 体系成分）。

**c-ii 分离结晶**：1–2 步同上但晶体被移走、**体系成分 = 熔体成分**；第 3 步到达共结点时体系**只剩共结成分的熔体**；第 4 步共结结晶 42 : 58；第 5 步**最后形成的固体就是 42% An + 58% Di**。

**c-iii 分离熔融**：
1. **1274 °C** 共结点产生第一滴熔体，**X_Di = 0.58**，随即移出；
2. 共结熔融持续，残余固体的 **An 组分不断降低**（体系成分 = 固体成分）；
3. 残余固体成分变为**纯 Di** 时共结熔融停止；
4. **1274 → ~1390 °C 之间不发生熔融**；
5. **~1390 °C** 剩余 Di 熔化，产出 Di 成分的熔体直至全熔。

**d) 野外如何区分不同初始成分的分离结晶产物**（这题考"把相图翻译成野外观察"）：
- X_Di = 0.1（富 An 一侧）：先产出**纯钙长石岩**，随后才是 An + Di 的混合岩石；因为体系成分离 An 端更近，**纯 An 岩石体积更大**；
- X_Di = 0.9（富 Di 一侧）：先产出**纯透辉石岩**，然后是混合岩石；
- 但**共结点离 X_Di = 0.9 比离 0.1 更近**，所以 0.9 情形下"只含 Di 的岩石"占比要**小于** 0.1 情形下"只含 An 的岩石"占比。
（⚠️ 题干写 X_Di = 0.8、答案写 0.9，见勘误表。）

### Q2：Fo–Qz（含包晶），X_Qz = 0.32 / X_Fo = 0.68

**a) 标注**：液相线与固相线；**L**、**L+Fo**、**L+En**、**L+Qz\***、**Fo+En**、**En+Qz** 六个相区；**包晶点（Fo + L = En）**；**共结点（L = En + Qz）**。
（\* 脚注：严格说该温度下稳定的 SiO₂ 同质多象是**方石英 Cristobalite**。）

**b)** 在**放大图**上标出 X_Qz = 0.32——并牢记两条提示：**放大图右端只到 0.5 Qz**，**En 位于 X_Qz = 0.3**。用放大图是为了"看清包晶点附近发生了什么"。

**c-i 平衡结晶 / c-ii 分离结晶 / c-iii 分离熔融**：七至八步的标准答法，已在"三、公式与图表"第 5 节逐条列出（路径 A、C、D），此处不重复。

**d) 若体系成分改为 X_Qz = 0.28 / X_Fo = 0.72（落在 Fo–En 之间）会怎样**：
- **平衡结晶**：包晶反应 Fo + L = En 中，**熔体先于 Fo 耗尽**；最后一滴熔体在**包晶点**结晶完毕，残余固体为 **Fo + En**（而不是 En + Qz）；
- **分离结晶**：**基本不变**，因为分离结晶下包晶反应根本不发生；唯一差别是在熔体成分越过包晶点之前**多结晶一点 Fo**，之后同样改为析出 En；
- **分离熔融**：第一滴熔体出现在"**Fo 与 En 同时与熔体平衡的最低温点**"，当体系成分落在 Fo–En 之间时，这个点是**包晶点**而非共结点。

### 图件（feedback_diagrams）要点

四张标注图（对应 Q1 的平衡/分离与 Q2 的三种情形），共同信息：
- An–Di 图：纵轴 T（°C）1200–1600，横轴 X_Di 0→1，端元写明 **An; CaAl₂Si₂O₈** 与 **Di; CaMgSi₂O₆**，标注 **1 atm**，图上标出 **1553**（An 熔点/液相线左端）与 **1274**（共结/固相线），并用 **1.–5.** 的编号把答案的五个步骤直接画在路径上；"system" 字样标出体系成分的垂直投影线。
- Fo–Qz 图：纵轴 1500–1900 °C，端元 **Fo; Mg₂SiO₄**、**En; MgSiO₃**、**Qz; SiO₂**，标注 **1 atm** 与 **X_Qz = 0.32, X_Fo = 0.68**；图上写出两条反应 **"Fo(+L) = En"**（包晶）与 **"L = En + Qz"**（共结）；右上角有 **2L**（两个不混溶熔体）区；步骤编号 1.–7. 同样画在路径上。

**复习建议**：把这两张空白相图默画出来，自己标出液相线/固相线/相区/两个不变点，再把四种过程的路径与编号步骤复述一遍——这正是 practical 的评分要点（标注是否完整 + 描述是否**定量**，即是否给出温度、成分与杠杆规则算出的比例）。

---

## 六、易错点 / 重点难点

1. **液相线以上的自由度不是 1，是 2。** 等压二元体系 F = C − P + 1；单相熔体区 F = 2−1+1 = 2（T 与 X 都自由）。课堂口误请勿照抄。
2. **共结 vs 包晶不要混。** 共结：L = A + B，液体分解为两种固体，液相线在此**相交**并出现水平固相线；包晶：Fo + L = En，**已结晶的矿物被回吃**。判断题里"温度恒定不变"两者都成立（都是不变点），但**物质流向相反**。
3. **包晶点上"谁先耗尽"必须先判断体系成分落在哪一侧**：X 体系 > X_En（0.30）→ **Fo 先耗尽**，之后还剩熔体，会一路走到共结点；X 体系 < X_En → **熔体先耗尽**，反应停在包晶点，产物是 Fo + En。最快的判据是"平衡结晶终态 = 初始成分"，把体系点垂直投影到底部看落在哪个双固相区。
4. **分离结晶时包晶反应不发生。** 因为先结晶的 Fo 已被移出，熔体"不再与它接触"。这是"自然界少见包晶反应"的原因，也是 practical Q2d 中"分离结晶几乎无变化"的原因。
5. **分离熔融 ≠ 分离结晶的逆过程；平衡熔融 = 平衡结晶的逆过程。** 这是最高频的判断题。
6. **分离熔融会出现"升温但不熔融"的间隔段**（如 Fo–Qz 中的 1540→1565 °C 与 1565→1890 °C）。写答案时不要漏掉这两步，practical 的标准答案里它们各占一步。
7. **杠杆规则的臂长取反。** 求液体比例要量**从体系点到固相点**那一段。检验方法：体系点离哪个相近，哪个相就多。
8. **无固溶体体系中析出的固相成分是固定的**（纯 An、纯 Di、纯 Fo），只有**比例**变；含固溶体体系中固相**成分本身**随温度移动。两者的杠杆用法因此不同。
9. **溶线以下的两个"相"是同一种矿物的两个不同成分固溶体**（Ab-rich afs_ss 与 Or-rich afs_ss），数相数时要算 **2** 个相，不要算成 1 个。
10. **出溶是动力学过程，不是相图必然结果。** 相图告诉你"平衡时应该出溶"，实际是否出溶、出溶到什么程度，取决于**冷却速率**。快冷 → 均一晶体（火山岩/岩墙岩床）；中等 → 细片晶（小岩浆房）；慢冷 → 粗片晶 + **反式易变辉石**（大岩浆房）。
11. **inverted pigeonite 的因果顺序**：先是易变辉石结晶（高温稳定），冷却到低温不变点后**相变**为斜方辉石，形态却保留了易变辉石的外形，内部还有普通辉石出溶片晶。不是"斜方辉石变成易变辉石"。
12. **Fo–Qz 的横轴刻度陷阱**：练习用的是**放大图，右端只到 X_Qz = 0.5**，En 在 0.30。若误按完整图（右端 1.0）读数，所有杠杆比例都会错。
13. **端元熔点与不变点温度要能背**：An 1553 °C、Di ≈1390 °C、An–Di 共结 **1274 °C（X_Di = 0.58）**；Fo ≈1890 °C、Fo–Qz **包晶 ≈1557–1565 °C**、**共结 ≈1540 °C（X_Qz = 0.42）**、En 在 X_Qz = 0.30。
14. **"Qz" 在这些高温图上其实是方石英（cristobalite）**。老师说是小细节，但 practical 专门加了脚注。

---

## 七、本周术语表

| 中文 | English | 说明 |
|---|---|---|
| 相图 | phase diagram | 联系 P、T、成分与相组合的图 |
| 组分 | component (C) | 描述体系成分所需最少化学实体数 |
| 相 | phase (P) | 性质均一、有边界的物质部分 |
| 自由度 / 变数 | variance / degrees of freedom (F) | 不改变相组合可独立变化的变量数 |
| 不变点 | invariant point | F = 0，温度与成分都被钉死 |
| 单变 / 双变 | univariant / divariant | F = 1 / F = 2 |
| 液相线 | liquidus | 开始出现第一颗晶体的界线 |
| 固相线 | solidus | 最后一滴熔体消失的界线 |
| 共结点 | eutectic (point) | L = A + B 的不变点 |
| 包晶点 | peritectic (point) | Fo + L = En，回吃已结晶矿物 |
| 不一致熔融 | incongruent melting | 矿物熔化产生成分不同的熔体 + 另一固相 |
| 固溶体 | solid solution (ss) | 成分连续可变的单一固相 |
| 溶线 / 混溶间隙 | solvus / miscibility gap | 低温下固溶受限的边界 |
| 出溶 | exsolution | 单一固相内部分离出第二种固相 |
| 出溶片晶 | exsolution lamellae | 出溶形成的板片状包裹体 |
| 平衡结晶 | equilibrium crystallisation | 晶体与熔体始终反应，终态 = 初态 |
| 分离结晶 | fractional crystallisation | 晶体一形成即移出，体系 = 熔体 |
| 平衡熔融 | equilibrium melting | 平衡结晶的逆过程 |
| 分离熔融 | fractional melting | 熔体一形成即移出；非分离结晶的逆过程 |
| 杠杆规则 | lever rule | 由线段长度求两相比例 |
| 实验岩石学 | experimental petrology | 用控温控压实验建立热力学数据库 |
| 活塞-圆筒装置 | piston cylinder | 高温高压实验设备 |
| 钙长石 | anorthite (An), CaAl₂Si₂O₈ | 斜长石富钙端元 |
| 钠长石 | albite (Ab), NaAlSi₃O₈ 📎 | 斜长石富钠端元 / 碱性长石端元 |
| 正长石 | orthoclase (Or), KAlSi₃O₈ 📎 | 碱性长石富钾端元 |
| 碱性长石固溶体 | alkali feldspar solid solution (afs_ss) | Ab–Or 固溶体 |
| 透辉石 | diopside (Di), CaMgSi₂O₆ | 富钙单斜辉石 |
| 顽火辉石 | enstatite (En), MgSiO₃ | 富镁辉石 |
| 镁橄榄石 | forsterite (Fo), Mg₂SiO₄ | 富镁橄榄石端元 |
| 石英 | quartz (Qz), SiO₂ | — |
| 方石英 | cristobalite (Cr) | SiO₂ 的高温同质多象 |
| 同质多象 | polymorph | 同成分不同结构的矿物 |
| 普通辉石 | augite (Aug) | 富 Di 的单斜辉石 |
| 易变辉石 | pigeonite (Pig) | 贫 Ca 单斜辉石，高温稳定 |
| 斜方辉石 | orthopyroxene (Opx) | 低温稳定的贫 Ca 辉石 |
| 反式易变辉石 | inverted pigeonite | 由易变辉石相变而来的斜方辉石 |
| 岩墙 / 岩床 | dike / sill | 快速冷却的小型侵入体 |
| 化石岩浆房 | fossil magma chamber | 已固结并出露的古岩浆房 |
| 玄武岩 | basalt | 富 Fo/橄榄石的镁铁质火山岩 |
| 英安岩 | dacite | 由 En + Qz 组合代表的演化火山岩 |
| 不混溶（两熔体） | liquid immiscibility (2L) | 两个熔体共存的区域 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `EART26201 - 20-Oct-transcript.md`，An–Di 自由度讨论 | "If you're above the liquidus, you have a variance of one. So you can change the temperature or the composition without affecting the composition of the system." | **自由度数值错误**。等压二元体系 F = C − P + 1；液相线以上 C=2、P=1（仅熔体）→ **F = 2**。他随后描述的"T 与 X 都可自由改变"本身就对应 2 个自由度，与所说的 1 自相矛盾 | 应为 **divariant，F = 2**。液相线上 F=1、共结点 F=0 的说法均正确 |
| 同上，Ab–Or 相图介绍 | "albite, so the sodium-rich plagioclase feldspar, and orthoclase, the **potassium-rich plagioclase feldspar**" | **矿物分类错误**。正长石是**碱性长石（alkali feldspar）**，不属于斜长石（plagioclase）系列 | 应为 "orthoclase, the potassium-rich **alkali** feldspar"。钠长石 Ab 兼作斜长石与碱性长石的端元，故前半句可接受 |
| 同上，An70Di30 平衡结晶 | "at 1200 degrees, you would have some liquid and some anorthite in these proportions" | **温度不可能**。共结温度为 1274 °C，1200 °C 已在固相线之下，体系应为全固态的 An + Di，不可能有熔体 | 该温度必须在 **1274 °C 以上**（如 1300–1400 °C）；疑为口误或录音转写错误 |
| 同上，Ab–Or 平衡结晶 | "we start with this liquid, which has about **25% albite and the rest of orthoclase**"，随后"the first solid you will form is that **albite rich** alkali feldspar…both become progressively richer and richer in orthoclase" | **内部不自洽**。若体系为 Or75，位于最低点（共结）富 Or 一侧，第一批长石应是**富 Or** 的，且熔体应向富 Ab 方向演化 | 与后文自洽的读法是体系约为 **Ab75Or25（25% 正长石）**。疑为口误或自动转写把 albite/orthoclase 对调 |
| 同上，方石英说明 | "cristobalite is the high-temperature polymorph of quartz… because we're at high temperature, we're **above 1400 degrees**" | **转变温度不准确**。1 atm 下 SiO₂ 的顺序是：石英 →(867 °C) 鳞石英 →(1470 °C) 方石英 →(1713 °C) 熔体。1400–1470 °C 之间稳定的是**鳞石英（tridymite）** | 方石英稳定域应为 **>1470 °C**。所幸 Fo–Qz 共结点在 ~1540 °C，确实落在方石英域内，故图上标 Cr 无误 |
| 同上，Ab–Or 相数统计 | "So two components and **two phases**"（前一句刚列举了 Ab-rich 长石、Or-rich 长石与熔体） | **与他自己的计数口径不一致**。在辉石图中他把 Opx_ss、Pig、Aug、melt 计为 4 个相；同一口径下 Ab–Or 应为 **3 个相**（两种碱性长石固溶体 + 熔体） | 建议按 **C = 2、P = 3** 记忆；若只指"任一时刻最多共存的相"另当别论，但材料未作此说明 |
| 同上，辉石图低温不变点 | "Once you reach that point here, you've reached **another eutectic** here on the left hand side"（指易变辉石→斜方辉石的转变点） | **术语不严谨**。共结（eutectic）按定义涉及**熔体**（L = A + B）；此处体系已全固态，是"固体 → 两种固体"的**共析型（eutectoid）**不变点 | 应称**共析点/固态不变点**，或直接称"易变辉石的反转（inversion）边界"。反应本身的描述（Di 较富的易变辉石相变为 Di 贫的斜方辉石）正确 |
| 同上，斜长石回顾段 | "in fractional melting, if we start from this plagioclase, for example, you can end up **crystallising pure albite**" | **过程用词错误/语句残缺**。分离熔融中熔体被抽走，**残余固体**趋向难熔端元，最终残余为**纯钙长石（anorthite）**；"结晶出纯钠长石"是**分离结晶**的结论（前一句刚讲过） | 应为"最终残余固体为纯 An"。疑为口误或转写丢词 |
| 同上，Fo–Qz 图介绍 | "we've got **enstatite here at 30% forsterite**" | **组分标错**。practical 明确写 "En has a composition of **X_Qz = 0.3**"，即 30% 石英组分、70% 镁橄榄石组分 | 应为 "at 30% **quartz**"。按分子量核算：60.1/(140.7+60.1) = 29.9% ✅ 支持 practical 的数值 |
| `EART26201_Practical4_feedback.md`，Q1 d) 题干与答案 | 题干："initial compositions of X_Di = **0.1** and X_Di = **0.8**"；答案通篇讨论 X_Di = **0.9** | **题干与答案不一致** | 答案内部自洽（用 0.9 的推理与"共结点更靠近 0.9"的结论均正确），应是题干或答案其一笔误；建议按 **0.1 vs 0.9** 理解 |
| 同上，Q2 c-i 第 5 步 | "the system contains liquid and En proportions of 20% liquid and **80% Di**" | **矿物名错误**。Fo–Qz 体系中不存在透辉石（Di） | 应为 **80% En**。另按杠杆规则精算（体系 0.32、En 0.30、共结熔体 0.42）应为 **17% 液 / 83% En**，20/80 属图上目测近似 |
| 同上，Q2 c-iii 第 1 步 | "The first liquid forms at the eutectic at 1540 °C, has a composition of **X_Qz = 0.32, X_Fo = 0.68**" | **成分错误**。0.32/0.68 是**体系**的整体成分；共结点产生的第一滴熔体必然是**共结成分** | 应为 **X_Qz = 0.42, X_Fo = 0.58**（与同文件 c-i 第 5 步、c-ii 第 5 步给出的共结成分一致） |
| 同上，Q1 c-i 第 3 步 | "the system contains liquid and Di proportions of **45% liquid and 55% Di**" | **数值偏差**。用文件自身给出的数据（体系 X_Di = 0.8、共结熔体 0.58、纯 Di = 1.0）做杠杆规则：f_L = 0.2/0.42 = **47.6%**，f_Di = **52.4%** | 应为约 **48% 液 / 52% Di**；45/55 属读图近似，答题时建议按杠杆规则计算 |
| 讲义 `EART26201_Lecture4_RT_v2.md` Slide 10–11 与 practical 的共结成分 | 讲义写 "An40Di60 …(eutectic)"；practical 写共结熔体 **X_Di = 0.58**（即 An42Di58） | **两份材料数值不一致**（非错误，但会造成答题困惑） | 实测的 An–Di 共结点为 **1274 °C, An42Di58**；讲义的 An40Di60 是取整。计算题一律采用 practical 的 **0.58** |
| `EART26201_Practical4_feedback_diagrams.md`，Fo–Qz 图内文字 | OCR 作 "1600 **Fo = En+L**" | **反应式书写方向不成立**（Fo 单独分解不能给出 En + L） | 正确写法为**包晶反应 Fo + L = En**（与 practical 题干 "The peritectic point described by the reaction Fo + L = En" 一致）；此处应为图件 OCR 时"+"号位置错乱 |
