# EART24001 Geological Maps — Week 08 学习笔记

## 一、本周主题

本课主线是**如何在二维图幅上表达并解读三维地质结构**：W1–2 从产状与地层等高线（strike lines）起步，随后逐类构造攻克——不整合（W3）、褶皱（W4）、断层（W5）；W6–7 插入赤平投影；W9–10 在真实图幅上综合。

**Week 08 是"逐类构造"的最后一类：火成侵入体（igneous intrusions）**，同时也是全课第一个综合周——它第一次要求把前七周的全部判据串成**一条唯一自洽的时间线**（sequence of events）。对应大纲的 **ILO 2/3**（识别并分析侵入体三维几何）与 **ILO 5**（用切割关系组装有证据支撑的事件序列）；ILO 5 只在期末 practical exam（70%）中考，本周是它唯一的正式训练。

材料 = 两份讲义（`HandoutIgneous` 侵入体几何、`HandSequence` 序列写法）+ 一套完整练习（`Cover-1` 题面、`MapSoln-2` 图幅答案、`SectSoln-1` 剖面答案、`SeqSoln` 序列答案）。

> 📎 背景补充：原件几乎全是手绘答案图，转 md 后只剩零碎图注。以下"怎么做"的操作步骤多为反向重建，凡讲义未直接写出者均以 `📎 背景补充：` 标出。

---

## 二、核心概念

### 1. 两分与通名

火成岩体可**喷出（extrusive）**或**侵入（intrusive）**。讲义明确：喷出单元（熔岩流、火山碎屑）**几何上完全按沉积单元处理**，只是横向厚度变化更大，故此后不再讨论。

- **Pluton（侵入体）**：侵入岩体的**通称**，不论大小、形状、成分。
- **Composite（复合）**：不止一期侵位、且**成分不同**；**Multiple（多期）**：不止一期但**成分相同**。

### 2. 图面判读的两个分类维度

讲义指出，从地质图判读角度，pluton 只按两条轴分类：**(a) 形状**——*parallel-sided*（板状）或 *more complex shape*；**(b) 边界相对围岩（country rock）层理的方位**——切穿者为 **discordant**，大体平行者为 **concordant**。

> 📎 背景补充（本课最重要的图面推论）：**concordant 岩体在图面上与地层无异**——可给它画 strike lines、遵守 V 字法则、用与地层相同的方法求真厚度；**discordant 岩体必须独立求产状**，其两壁是与围岩无关的一对平面。这正是 `Cover-1` 第 2 题（沉积接触面）与第 3(c) 题（岩墙**另外**画 strike lines）分开出题的原因。

### 3. Parallel-sided intrusives（板状侵入体）

平面或弧面状，厚度在远大于其厚度的距离上近似恒定。

- **Sill 岩床**：concordant 席状体。大范围岩床常**跨层阶跃**；持续向上阶跃者称 **transgressive sill**。原型为 **Great Whin Sill**（Northumberland / County Durham）。
- **Dyke 岩墙**：discordant 席状体，切穿层理。常成 **swarm**，可为 **parallel** 或 **radial**。
- **Cone-sheet 锥状岩席**：锥面的一部分——**弧形出露、接触面向内倾**，绕共同中心成群。
- **Ring dyke 环状岩墙**：近圆形出露，接触面**直立至陡向外倾**。

> 📎 背景补充：cone-sheet 与 ring dyke 图面都是弧形环带，唯一区别在**倾向**（向内 vs 向外/直立）。判别办法就是给弧形接触面画 strike lines，看等高线值朝圆心方向是降是升。

### 4. Intrusives of more complex shape

| 名称 | 整合性 | 讲义关键判据 |
|---|---|---|
| **Batholith 岩基** | discordant, composite | 众多 pluton 组成，**>100 km²**、**无可观察的底**；见于造山带核部并与之平行 |
| **Stock 岩株** | discordant | 不规则，**<100 km²**；严格义：近圆/椭圆出露、**<20 km²** |
| **Boss 岩瘤** | discordant | 同 stock；圆形出露、**<25 km²**、接触面**陡** |
| **Cupola 岩穹凸起** | — | 自大侵入体伸出的小穹丘，但**图面上与主体隔离** |
| **Plug 岩栓** | discordant | 火山的近圆、直立供岩通道；剥蚀出露后称 **volcanic neck**（法语 **puy**）；广义旧称 **bysmalith** |
| **Diatreme 火山管** | discordant | **胡萝卜形**：直立轴、陡**向内**倾侧壁，深 1–2 km，充填**角砾** |
| **Laccolith 岩盖** | **concordant** | 穹丘状，**上拱上覆层、底面近平**；叠置者 **cedar-tree laccolith**（Henry Mts, Utah） |
| **Lopolith 岩盆** | **concordant** | **碟状、向上凹**；大者如 **Bushveld complex** |
| **Phacolith 岩鞍** | **concordant** | **凹凸相间**，源于褶皱围岩；叠置组称 **saddle reefs** |

配图另含 tuff ring、crater、septum、roof pendant、root zone。

> 📎 背景补充：**laccolith / lopolith / phacolith 都是 concordant**，图面按地层处理，区别只是弯曲方向（上凸底平 / 下凹 / 骑在转折端）。**batholith / stock / boss / plug / diatreme 都是 discordant**，表现为切断一切地层界线、不遵守 V 字法则的不规则块体。

### 5. 定年判据工具箱

材料实际动用的：**① 切割关系（切者新）**；**② 未被错断**（`SeqSoln`：不整合面 strike lines 在断层南北间距相同、未被错开 → 不整合晚于断层）；**③ 不整合 = 一次抬升+剥蚀间断**；**④ 截切的构造花纹**（`HandSequence`：C/D 接触面截断 D 的花纹 → 该面是不整合）；**⑤ 变质/褶皱的选择性**（只有 D 被变质；C 被褶皱而断层未被褶皱）；**⑥ 现今产状反推掀斜**（现今直立的矿脉与断层，若原本直立，则必晚于造成 8° 倾斜的掀斜）。

> 📎 背景补充（讲义未列、侵入体题必备的三条）：
> - **接触变质晕（contact aureole）**：有晕 → 侵入体**晚于**被烤围岩且侵位时仍热；图上是绕岩体的一圈额外岩性带。
> - **捕虏体（xenolith）**：**被包者老**。
> - **烘烤边 / 冷凝边（baked / chilled margin）**：区分岩床与熔岩流的决定性证据（见第六节）。

---

## 三、公式与图表

### A. 求 discordant 岩体产状（📎 背景补充：讲义未分步写，此为标准做法）

① 选定**一侧**接触面（本题用 *west side of dolerite / vein*），**两壁必须分开、绝不混用**；② 找该接触面与**同一条地形等高线**的两交点，连线即该高程的 strike line；③ 对多条等高线重复；④ 走向 = strike line 方位，倾向 = 等高线值降低方向，tan δ = 等高距 ÷ strike line 水平间距。

本题四组产状（`MapSoln-2` + `SeqSoln`）：

| 面 | 走向/倾角 | 倾角/倾向 |
|---|---|---|
| 砾岩/灰岩、灰岩/泥岩接触面 | 030/8SE | 8/120 |
| **辉绿岩岩墙 dolerite dyke** | **015/24W** | **24/285** |
| **矿脉 ore vein** | **170/V** | 90°（直立） |
| **断层 fault** | **105/V**（见勘误表） | 90°（直立） |
| **不整合面 unconformity** | **095/3N** | **3/005** |

> 📎 背景补充（记法换算）：倾向 = 走向 ± 90°，取落在所标象限者。030/8SE → 030+90=120 ✓；015/24W → 015+270=285 ✓；095/3N → 095−90=005 ✓。**象限写错直接扣分。**

**关键观察**：两组沉积接触面的 strike lines 走向相同、间距相同 → **互相平行** → 三个沉积单元为一套**整合**层序（即 `Cover-1` 第 2(b) 问）。

### B. 由 strike lines 求真厚度

`SeqSoln` 的灰岩厚度算法：

```
顶面（灰岩/泥岩，绿）与底面（砾岩/灰岩，蓝）平行，δ = 8.1°
x = 底面 200 ft 与 顶面 700 ft 两条 strike line 的图上水平距离 = 633 ft
a = x·tan δ = 90.25 ft ； b = 700 − 200 = 500 ft
铅直厚度 V = a + b = 590.25 ft
真厚度 t = (a+b)·cos 8.1° = 584 ft
```

> 📎 背景补充（推导）：把 x 沿顶面走一遍，顶面高程变化 a = x tan δ；加到 700 ft 上，得到**底面 200 ft strike line 正上方**的顶面高程。故同一铅直线上顶底高差 = a+b = **铅直厚度**；真厚度垂直于层面量，再乘 cos δ。
> **通用公式：t = V · cos δ**（V = 同一图上位置顶底面的铅直高差）。

`SectSoln-1` 的地层柱（按比例）：a 砾岩 ~200 ft **min** / b **灰岩 584 ft** / c 泥岩 ~900 ft **min** / **不整合面** / d 砂岩 ~200 ft **min**。a、c、d 标 **min** 是因为另一边界未出露（砾岩底、泥岩顶被不整合截切、砂岩顶被地形截切）——**只能给下限，不要写确定值**，这是评分要点。

> 📎 背景补充：同法可求岩墙厚度。`MapSoln-2` 注"E. side of dolerite is 100 ft lower"（东壁比西壁低 100 ft，即 V = 100 ft），故 t = 100 × cos 24° ≈ **91 ft**。此推论材料未明写。

### C. 断层面剖面（`Cover-1` Q5 / `SectSoln-1`）

📎 背景补充（步骤还原）：① 断层直立，剖面线即断层迹线；② **垂直比例尺必须等于水平比例尺**（1 mm = 40 ft）；③ 沿迹线读出每条地质界线与断层的交点高程并投到剖面；④ 倾斜平面与直立断层面相交，剖面上为**倾斜直线**，连同名点；⑤ 标注地形线、海平面、单元代号 a–d，并附**按比例的地层柱作图例**。

**比例尺换算（选做题答案）**：1 mm = 40 ft = 40×12×25.4 mm = 12192 mm → **1 : 12192**。

### D. 并置剖面（juxtaposition section）求滑距

方法承自 W5。① 在同一张断层面剖面上，**北盘画虚线、南盘画实线**；② 取两条不平行的标志面（题目指定 **灰岩/泥岩接触面** 与 **矿脉西壁**）；③ 每盘上两线的**交点 = piercing point（穿刺点）**，即一条真实三维交线刺穿断层面之处；④ 连接南北两个穿刺点的向量 = **净滑距向量**；⑤ 量长度得净滑距，铅直分量 = dip-slip，水平分量 = strike-slip。

**答案**：断层 115/V（`SectSoln-1`）；**滑距向量 27½/295，720 ft；倾滑 332 ft（down to N）；走滑 639 ft（sinistral 左行）**。

> 📎 背景补充（自洽检验）：720·sin27.5°=332 ✓，720·cos27.5°=639 ✓；滑距倾伏向 295° 与断层走向 115° 相差 180°，证明该向量**确实躺在断层面内**——这是查错最快的办法。因断层直立，dip-slip 方向恰为铅直。

`SectSoln-1` 注明：用 vein/dolerite 交点或 dolerite/灰岩顶面交点得**同样答案**——做题时**至少用两组穿刺点互验**。

### E. 事件序列的可复用流程

> 📎 背景补充（四步法）：**① 清点**——列出所有地层单元 + 侵入体 + 构造面（不整合、断层、褶皱轴面）+ 剥蚀面，一个不漏；**② 两两判先后**——谁切谁、谁被截断、谁被变质/褶皱/错断而另一个没有，得到一串局部约束；**③ 排序**成全序，无直接接触关系者位置不唯一，**必须明说约束区间**；**④ 自洽检查**——复述一遍确认不与任何约束矛盾，并检查"沉积—抬升剥蚀—再沉积"物理闭合（每个不整合上下都要有对应的抬升剥蚀事件）。

---

## 四、课堂补充

> **本周无 transcript**（本课全 10 周皆无）。本段全部来自两份 handout 与四份答案的图注。

**1. `HandSequence` 的两条硬规范**（评分直接依据）：① **格式**——写成"措辞简练的一组 bullet points，编号以指明先后"，不是散文；② **证据**——推断每一步所用证据一般都要写在相应条目中，**任何定量几何信息也要写出来**。示范答案即如此：*"5. Folding（Unit C 被褶皱而断层没有；褶皱为向 SW 倾伏的向形）"*、*"6. Faulting（断层错开 C 中褶皱翼但未影响 B；走向 NW–SE，视位移显示为纯倾滑，NE 盘下降）"*——括号里既有证据又有定量几何。

**2. 方向统一"由老到新"**：`HandSequence` 标题写死 *Sequence of events (oldest to youngest)*，`SeqSoln` 编号亦然。**写序列前先在标题里写清方向并照做；写反即使内容全对也扣分。**

**3. 两个"诚实"要点**：① 讲义原话——若**没有地形和/或各面方位信息，构造几何无法严格描述**，故示范图只给相对顺序、不给产状数字；② 保留不确定性——示范答案末条"剥蚀至现今地形（Unit A 倾角未知，不能排除晚期掀斜）"；`Cover-1` Q7 同样要求"**drawing attention to any ambiguities in age relationships**"。`SeqSoln` 第 (3) 步是最佳范例：*"Tilting［此位置假定矿脉与断层原本直立；若非如此，掀斜只能约束在 (1) 之后、(6) 之前］"*——**这种"假设 + 假设失效后的约束区间"写法是高分点。**

**4. 作图约定**：**分色**——`Cover-1` Q2 要求 "in a different colour"；`SeqSoln` 点名砾岩/灰岩=**蓝**、灰岩/泥岩=**绿**、不整合=**洋红**，必须配图例。**等比例**——两处剖面都加粗强调 vertical scale **SAME** as horizontal。**完整注记**——Q5 要求 "**Fully annotate**" 并画 "**stratigraphic column to scale**" 作图例（方向标、双侧高程刻度、海平面、地形线、单元代号、比例尺俱全）。**线型**——并置剖面 N=虚线、S=实线并在图上注明。

> 📎 背景补充：正式地质图上侵入体常用十字/随机点花纹（酸性）或深色实填（基性岩墙、岩床）；接触变质晕用沿岩体外缘的一圈短线带表示并在图例单列。本周手绘答案未用这些花纹，仅以单元名标注。

**5. `Cover-1` 透露的解题顺序**：先确认能识别出三类要素（两条 discordant parallel-sided 侵入体、一条不整合、一条断层）→ 不整合 strike lines → 沉积接触面 → 岩墙 → 断层 → 剖面 → 滑距 → 序列。题面那句 "**Make sure that you can.**" 是在提醒：**要素识别错，后面全错**。

---

## 五、Practical 要点

本周只有一道大题（`Cover-1`），7 小问。地形图为英尺等高线，比例尺 0–1000 ft；图例注明单元 limestone / conglomerate / sandstone / mudstone / dolerite / vein 且 "**not in stratigraphic order**"——层序必须自己推。

**Q1 不整合**：画 strike lines → (a) **095/3N = 3/005**；(b) strike lines 在断层南北**间距相同、未被错开** → **不整合晚于断层**。

**Q2 沉积单元**：(a) 灰岩/泥岩接触面 **030/8SE = 8/120**；(b) 砾岩/灰岩接触面 strike lines 与之**平行且等间距 → 两接触面平行**；(c) 层序由老到新 **砾岩 → 灰岩 → 泥岩**，不整合面之上为**砂岩**（最新）；(d) 灰岩真厚度 **584 ft**。
> 📎 背景补充：层序由倾向读出——地层向 SE 倾，则向 SE 出露者更新；"base mudstone / top conglomerate" 的命名也确认灰岩夹在中间。

**Q3 两条侵入体**：(a) **矿脉更年轻**——"*crosscuts dolerite dyke*"；(b) 两者**都晚于**三个沉积单元（岩墙 "*crosscuts conglomerates, limestones and mudstones*"），又**都早于**不整合与砂岩（被截切、被断层错开）；(c) 岩墙 **015/24W = 24/285**，矿脉 **170/V（直立）**。
> 注意 `MapSoln-2` 标注用的是 "**W. side of dolerite (south)**"——岩墙被断层错成两段，**只能用同一盘的同一壁**画 strike lines。这是本题最易错的技术点。

**Q4 断层**：(a) **晚于**全部沉积单元与两条侵入体（"conglomerate, limestone, mudstone, dyke and vein are **all offset by fault**"），**早于**不整合；(b) 直立无疑，走向 **105/V**（`MapSoln-2`、`SeqSoln`）/ **115/V**（`SectSoln-1`），见勘误表。

**Q5 断层面剖面**：向北看，W 左 E 右，0（sea）–800 ft，1 mm = 40 ft 等比例；标出 **A = dolerite**、**B = ore vein** 在断层面上的迹线及 a–d 四单元；附按比例地层柱。选做比例尺 = **1 : 12192**。

**Q6 并置剖面（选做）**：**27½/295，720 ft；倾滑 332 ft（北盘下降）；走滑 639 ft（左行）**；三组穿刺点结果一致。

### Q7 事件序列（★本周最重要，`SeqSoln`）

**Sequence of Geological Events（oldest → youngest）**

| # | 事件 | 证据（答案原文要点） |
|---|---|---|
| 1 | 依次沉积**砾岩、灰岩、泥岩** | 三者产状一致（030/8SE）、接触面平行 → 整合层序 |
| 2 | 侵入**辉绿岩岩墙** | *crosscuts conglomerates, limestones and mudstones* |
| 3 | **掀斜 Tilting** | *假定矿脉与断层原本直立才能定在此处；若非如此，只能约束在 (1) 之后、(6) 之前* |
| 4 | 侵入**矿脉 ore vein** | *crosscuts dolerite dyke* |
| 5 | **断层作用** | *offsets ore vein*（并错开砾岩、灰岩、泥岩、岩墙） |
| 6 | **抬升与剥蚀，形成不整合面** | *not offset by fault* |
| 7 | 沉积**砂岩** | *above unconformity* |
| 8 | **掀斜**（第二次） | *sandstones are gently tilted*（不整合面现今仍倾 3/005） |
| 9 | **剥蚀至现今地形** | — |

**理解要点**：① **两次掀斜**——第一次把沉积岩掀成 8°，第二次把砂岩掀成 3°，**漏任何一次都是重大失分**；② 第 (3) 步的逻辑——矿脉与断层现今直立，若形成时直立，则使地层倾斜 8° 的掀斜必在其**之前**，否则今日不会直立，这是本题最精巧的一步；③ **(6) 与 (7) 必须分列**，抬升剥蚀与其上沉积是两个事件，绝不能合并成"不整合"一条；④ **(9) 剥蚀至现今地形**永远是最后一条。

---

## 六、易错点 / 重点难点

1. **岩床与熔岩流混淆**（本课最经典陷阱）——两者图面都 concordant、产状随围岩。
   > 📎 背景补充：**岩床上下两侧围岩都有烘烤边，熔岩流只有底面有**（熔岩流上表面当时暴露，上覆地层是后来沉积的）。辅助判据：熔岩流上表面常有气孔、枕状构造、风化面、火山碎屑夹层；岩床两壁都有冷凝边，且可含上覆地层的 xenolith。熔岩流是**地层的一部分**（上覆层必比它新），岩床可比上覆层年轻得多。
2. **把岩墙当断层**——📎 背景补充：**岩墙是有厚度的岩性体**（两条平行接触线夹一种岩石，两侧地层**不错动、可对接**）；**断层是一个面**（一条线，两侧地层**被错开**）。本图两者并存：辉绿岩（有宽度、24/285）与断层（一条线、直立、错开一切）。
3. **跨断层或跨两壁混用点画 strike lines**——`MapSoln-2` 特意注明 "W. side of dolerite (south)"。混点必得错误产状。
4. **漏掉抬升/剥蚀事件**——有不整合就必须有一条 Uplift and erosion；有地形就必须有最后一条 Erosion to present topography。`SeqSoln` 九步中有**两步**是剥蚀。
5. **序列方向写反**——本课统一 oldest → youngest。
6. **只写事件不写证据**——`HandSequence` 要求每条注明依据并给定量几何，**无证据的条目基本不给分**。
7. **忽略侵入体与褶皱/掀斜的先后**——**随围岩一起弯曲的岩床早于褶皱；笔直切过整个褶皱的岩墙晚于褶皱**。本题对应版本即第 (3) 步。
8. **厚度忘乘 cos δ**——strike lines 给的永远是**铅直**高差。8° 时误差仅 1%，24° 时 9%，大倾角错得离谱。
9. **出露不全的单元报成确定厚度**——只能写 "~X ft min"。
10. **剖面垂向放大**——本题两处剖面都必须 1:1，否则量出的滑距长度与倾伏角全部失真。
11. **产状象限写反**——030/8SE 与 030/8NW 是完全不同的构造，换算成"倾角/倾向"后再核一次。

---

## 七、本周术语表

| 英文 | 中文 | 要点 |
|---|---|---|
| extrusive / intrusive | 喷出的 / 侵入的 | 喷出岩按沉积单元处理 |
| pluton / country rock | 侵入体 / 围岩 | 侵入岩体通称 / 被侵入的岩石 |
| composite / multiple | 复合 / 多期 | 成分不同 / 成分相同的多期侵位 |
| concordant / discordant | 整合（顺层）/ 切层 | 边界平行 / 切穿层理 |
| parallel-sided | 板状（两壁平行） | 厚度长距离恒定 |
| sill / transgressive sill | 岩床 / 穿层岩床 | concordant 席状体 / 逐级向上跨层 |
| dyke / dyke swarm | 岩墙 / 岩墙群 | discordant 席状体；parallel 或 radial |
| cone-sheet / ring dyke | 锥状岩席 / 环状岩墙 | 接触面**向内**倾 / 直立或**向外**倾 |
| batholith / stock / boss | 岩基 / 岩株 / 岩瘤 | discordant；>100 / <100 / <25 km² |
| cupola | 岩穹凸起 | 图面上与主体隔离的小穹丘 |
| plug / volcanic neck / puy | 岩栓 / 火山颈 | 直立供岩通道；旧称 bysmalith |
| diatreme | 火山管 | 胡萝卜形，深 1–2 km，充填角砾 |
| laccolith / lopolith / phacolith | 岩盖 / 岩盆 / 岩鞍 | 均 concordant；上拱底平 / 碟状下凹 / 凹凸相间 |
| saddle reef / roof pendant / septum | 鞍状矿脉 / 顶垂体 / 隔板 | 叠置 phacolith / 侵入体中的残留围岩 |
| cross-cutting relationship | 切割关系 | 切者新 |
| xenolith | 捕虏体 | 被包者老 |
| contact aureole | 接触变质晕 | 侵入体晚于并烘烤围岩 |
| baked / chilled margin | 烘烤边 / 冷凝边 | 区分岩床与熔岩流 |
| unconformity | 不整合（面） | 代表抬升 + 剥蚀间断 |
| sequence of events | 事件序列 | 编号 bullet + 证据 + 定量几何 |
| strike lines | 地层等高线（走向线） | 同一界面等高程点连线 |
| true thickness | 真厚度 | t = V·cos δ |
| fault plane / juxtaposition section | 断层面剖面 / 并置剖面 | 断层面内作图；用穿刺点求滑距 |
| piercing point / slip vector | 穿刺点 / 滑距向量 | 界线交点 / 净位移（大小 + 方位） |
| dip-slip / strike-slip | 倾滑 / 走滑 | 铅直分量 / 水平分量 |
| sinistral / dextral | 左行 / 右行 | 走滑方向感 |
| downthrown side / tilting | 下降盘 / 掀斜 | 本题北盘下降；掀斜非褶皱 |
| stratigraphic column | 地层柱 | 剖面的按比例图例 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `SectSoln-1.md` 两处标题及末尾 "Faulting" 小节 **vs** `MapSoln-2.md` 图注、`SeqSoln.md` 产状列表 | `SectSoln-1`：**Fault plane section (115/V)**、**Fault plane : 115/V**；`MapSoln-2`：**fault 105/V**；`SeqSoln`：**fault 105/V (= 90°)** | 同一条断层的走向在两份答案中不一致（115 vs 105） | 由滑距向量 **27½/295** 反推：该向量必位于断层面内，故走向应为 295−180 = **115**。**115/V 自洽，105/V 疑为笔误**。做题以 115/V 为准，并可在答卷中注明此不确定性 |
| `MapSoln-2.md` 图注 | `top congomerate : 030/8SE` | 拼写错误 | 应为 **conglomerate** |
| `SeqSoln.md` 厚度计算 | `x = 633 ft`，`a = x tan 8.1° = 90.25 ft` | 633 × tan 8.1° = 90.09 ft，与所给 90.25 略有出入 | 属图上量取与四舍五入的正常误差（相当于 δ ≈ 8.11°），不影响 t = 584 ft。**非实质性错误**，仅作记录 |
| `SeqSoln.md` 首条 bullet | `Strike lines for conglomerate/limestone and limestone/mudstone contacts … indicate that **these three units** all dip 030/8SE` | 严格说 strike lines 只直接给出两个**接触面**的产状，"三个单元"是由此推得 | 原意可理解，无需更正；答题宜写作"两接触面平行，故其间及相邻的三个单元产状一致" |
