# EART28202 Structural Geology — Week 08 学习笔记

> 本周材料：
> - Lecture：`Lecture/Week 8/Class8_Contractional.md`（Class 8: Contractional Tectonic Regimes，共 57 张幻灯片，含极详尽的 notes pane）
> - Practical：`Practical/Week 8/` 下 `NewHandout.md`（题面/方法说明，**本周实习的主文件**）、`Map_2024.md`、`Section_2024.md`、`Stereogram_2024.md`（St Monans 2024 版图幅、剖面、赤平投影三件套）、`Soln1(1).md` / `Soln2(1).md` / `Soln3(1).md`（另一套合成练习的题面与分步答案）、`Ex1soln.md` / `Ex2soln.md` / `Ex3soln.md`（褶皱—劈理关系小练习答案）
> - 本课全 10 周**没有 transcript**（课堂录音转写），所有内容均来自幻灯片正文、notes pane、practical 题面与答案图件的文字。

---

## 一、本周主题

### 1.1 本周在全课骨架中的位置

EART28202 是春季学期（Semester 2）的第一门构造地质学课，是 EART24001 *Geological Maps* 的直接延续——把上学期"纯几何"的地质图判读，升级为**力学**。整门课按 syllabus 的 Theory/Practical 配对，骨架是：

| 阶段 | 周次 | 内容 |
|---|---|---|
| **几何学** | W01–W03 | 褶皱几何、褶皱如何形成、应变（strain） |
| **力学** | W04–W06 | 剪切带、应力（stress）、破裂与小型侵入体的就位 |
| **构造类型** | W07–W10 | 断层作用、**挤压构造域（本周）**、伸展构造域、走滑构造域 |

**本周是"构造类型段"的第二类：挤压（收缩）背景。**W07 讲的是断层作用的一般理论（断层几何、位移—长度关系、断层岩），本周把这套工具搬到**挤压构造域**，专讲**逆冲断层系统（thrust systems）及其相关褶皱**。W09/W10 分别处理伸展与走滑。

Syllabus 的课程概述专门交代了最后三讲的定位：

> "The last three Theory sessions seek to integrate the preceding seven by describing the interrelationships between these structures in contractional, extensional and strike-slip tectonic settings."

对应的是 **ILO 6**："show the interrelationship between field scale structures in large scale contractional, extensional, and strike-slip tectonic settings"。也就是说，本周的考核重点不是记住某一个构造的定义，而是**把褶皱、断层、劈理、应变、沉积记录串成一个挤压造山带的整体故事**。

讲义 Slide 2 的 notes pane 里有一句可以当成本周的总纲：

> "In a crude sense, one may think of the first three shortening mechanisms simply as ways of accommodating movement on thrust faults. From this perspective, **when one sees a fold the question to ask is 'Where is the fault that led to its formation?'** If you start to think along these lines whenever you are looking at structures in the field, you will automatically find yourself a long way down the path of integrating the structures with the regional geology."

**"看到褶皱，先问断层在哪里"**——这是本讲最值得带走的一句话。

### 1.2 ⚠️ 本周讲座与实习主题不一致

**必须如实说明：本周的讲座与实习讲的不是同一件事。**

- **讲座**：Class 8 *Contractional Tectonic Regimes*——逆冲断层系统、逆冲相关褶皱、临界楔、平衡剖面。
- **实习**：**St Monans（苏格兰 Fife）的下倾投影剖面（down-plunge projection / profile plane section）**——一条纯粹的图幅 + 赤平投影 + 剖面作图技能训练。

这**不是错误，也不是材料错配**。本课的 Practical 是一条**独立的图幅/赤平投影技能训练序列**，与 Lecture 的主题**并非逐周绑定**：全课 10 周里 W01/W02/W03/W05/W06 两者吻合，W04 与 W07–W10 不吻合，而且不吻合的周次之间也无法用任何固定的周次偏移来解释。**这是这门课的教学传统。**Syllabus 的实习概述也印证了这条独立主线：

> "The practicals develop a working understanding of structural analysis, focusing on the use of graphical techniques… The initial focus is upon the use of stereonets for analysing the geometry of folds and faults and **for constructing cross sections on dipping planes to illustrate that geometry**."

"constructing cross sections on **dipping planes**"（在**倾斜**平面上作剖面）——这正是本周实习做的事：剖面平面是 108/70 S，一个倾斜 70° 的面，不是竖直剖面。

**因此本笔记把两者分开处理**：§二、§三前半、§四、§六前半讲逆冲收缩构造；§三后半、§五、§六后半讲下倾投影。§七的术语表两边都收。

> 📎 背景补充：另需注意，syllabus 把 Week 8 的 practical 列为 "Restorable and balanced sections"（可复原剖面与平衡剖面），而 `Practical/Week 8/` 里实际发放的材料是下倾投影剖面（syllabus 里 "Constructing accurate fold profile plane cross sections" 被列在 Week 7）。这属于**教学安排逐年微调**，syllabus 描述与当年实际发放材料有半周的错位，不是材料错误，也不影响复习——两周的 practical 材料请合起来看。**平衡剖面的内容本周仍在讲义里（Slides 49–56），只是没有配套的作图练习。**

### 1.3 本讲的宏观结构地图

57 张幻灯片可以切成五大块：

| 幻灯片 | 板块 | 核心内容 |
|---|---|---|
| 2–10 | **引子：挤压构造域的尺度谱** | 四种收缩方式；薄皮/厚皮；造山带实例（阿尔卑斯、落基山、比利牛斯、Barrême、坎塔布连）；局部挤压（三角洲趾部、滑坡趾部）；月球 wrinkle ridges、水星 lobate scarps；砂箱模拟 |
| 11–29 | **术语（Terminology）** | 逆冲的定义；nappe/klippe/window/allochthon；断坪—断坡；前缘/斜向/侧向断坡；叠瓦扇与双重构造；双重构造的三种几何与扩展序列；back-thrust/pop-up/triangle zone/passive roof duplex；branch-line/tip-line/cut-off line |
| 30–41 | **褶皱与断层的关系** | 断弯褶皱（含应变史）；断展褶皱（含 trishear）；被切穿的断展褶皱；断坡边缘的雁列褶皱；断滑（detachment）褶皱与其面积法；背形堆垛之上的褶皱；同构造（生长）褶皱 |
| 42–48 | **褶皱—逆冲带的力学模型** | 临界楔（critical taper）；重力的作用（spreading/gliding/extrusion）；逆冲席内的应变分布；后陆一侧根带的处置 |
| 49–57 | **附加内容：剖面平衡** | 分析褶皱—逆冲地体的图件技术；bow-and-arrow 法则；平衡剖面的定义、假设、pin-line/loose-line、线长平衡、面积平衡；阅读书目 |

Slide 1 的 notes pane 提醒：notes pane 里塞满了图源与延伸阅读；syllabus 也说这套 PPT 是**"road map of the subject"**，考试只考各讲中**被明确标为 key material 的部分**。Slide 49 把平衡剖面明确标成 "**Some additional notes**"——即它是补充材料，但 Slide 50 又说 "another technique (balanced cross sections) **is important to be aware of**"，所以**概念与原则要会，但不太可能考大篇幅的手工平衡作业**。

---

## 二、核心概念

### 2.1 收缩的四种实现方式，以及本讲的取舍

Slide 2：挤压构造域中的缩短由以下几种方式的**某种组合**实现：

1. **体积损失（volume loss）**——压溶（pressure solution）/压实（compaction）；
2. **纯剪切（pure shear）**——水平缩短伴随垂向增厚；
3. **弯曲（buckling）**——即屈曲褶皱；
4. **收缩性断层上的运动，以及与该运动相关的褶皱作用**。

前三种已分别在"岩石变形机制"选修 PPT、Class 3（应变）、Class 2（褶皱如何形成）里讲过；**本讲专攻第 4 种**。而且如 §1.1 引的那句 notes：前三种在粗略意义上都可以看成**为逆冲断层上的位移"腾地方"的方式**。

### 2.2 薄皮构造与厚皮构造（thin-skinned / thick-skinned）

Slide 3。这是 1980 年代的认识飞跃：**挤压造山带中绝大部分的缩短量都局部化到逆冲断层上**（而不是均匀分布的塑性变形）。据此分两种风格：

| | **薄皮构造 thin-skinned** | **厚皮构造 thick-skinned** |
|---|---|---|
| 位置 | **前陆（foreland）** | **后陆（hinterland）**，变质级别较高 |
| 卷入层位 | **只有盖层（cover rocks），基底不卷入** | **基底卷入（basement involved）** |
| 逆冲系统厚度 | 薄 | 厚 |

阿尔卑斯的横剖面（Fossen p.362）就是标准示例：前陆一侧是薄皮的褶皱—逆冲带，向后陆过渡为卷入基底的厚皮构造。

Slide 4 的 notes pane 有一条方法论意义很强的评论：当全世界的造山带被用逆冲系统的框架重新分析时，人们常发现**原有的地质图质量非常高、图本身不需要修改，改变的只是构造解释**（例子：Bailey 绘制的 Loch Leven 地区图幅——去复活节野外课的同学会去那里）。

> "This provides a reminder of the importance of **separating data (results) from interpretation**."

**把数据与解释分开**——这条在 practical 里同样是评分点（见 §5.6）。

### 2.3 挤压构造出现在所有尺度上，也出现在别的行星上

- **局部挤压构造**（Slide 7）：滑坡趾部、三角洲斜坡趾部、其他重力驱动的软沉积变形（尼日尔三角洲是记录最好的例子）；砂箱模型（在可流动基底上进积的三角洲，其重量驱动趾部褶皱与逆冲）。notes 说尺度可以一路小到**薄片尺度**。
- **月球的皱脊（wrinkle ridges）**（Slide 8）：出现在月海（mare）**内部**，边缘则伴生**张性月溪（rilles）**。成因是月海玄武岩重量导致的**盆地局部挠曲（basin-localized flexure）**——边缘拉张、内部挤压。
- **水星等的叶状陡坎（lobate scarps）**（Slide 9）：**全球性分布**，反映行星内部净冷却导致的**全球收缩（global contraction）**。几何分析表明它们是**破出地表的逆断层尖端之上的背形的地表表现**。Discovery Rupes 长逾 500 km，是水星最长的叶状陡坎。notes 补充：月球上已填绘出 3200 条以上的叶状陡坎，主要在月球高地，**很年轻（< 50 Ma），有些可能今天仍在活动**；它们与皱脊要区分开（皱脊是更复杂的挤压构造）。

**这一段直接对应 syllabus 里"These matters are illustrated using examples taken from other planetary bodies in addition to Earth"，是本课的特色，可能出简答题。**

### 2.4 基本术语：逆冲、推覆体、飞来峰、构造窗

**逆冲（thrust）**（Slide 12）的定义：

> "A thrust is a **predominantly low angle** fault or shear zone with a **predominantly reverse dip-slip** sense of movement."

判别推论：
- 在**向上变新**的岩层序列中，逆冲把**老岩层带到新岩层之上**；
- 若**变质级别向上降低**，逆冲把**高变质级岩石带到低变质级岩石之上**（例：Glencoul Thrust 把前寒武 Lewisian 片麻岩推到寒武—奥陶纪灰岩之上）。

尺度：从毫米级位移到山脉尺度的 10–100 km 位移都有。

Slide 13 的一组术语：

| 术语 | 含义 |
|---|---|
| **推覆体 nappe / 逆冲席 thrust sheet** | 低角度、大位移逆冲的**上盘**，其宽度远大于厚度（"nappe" 是法语"桌布"） |
| **飞来峰 klippe** | 侵蚀后残留的推覆体孤立残片（经典例：落基山 Lewis Thrust 上的 Chief Mountain） |
| **构造窗 (tectonic) window** | 侵蚀穿透推覆体形成的"洞"，露出其下的单元 |
| **外来体 allochthon** | 被搬运的逆冲席 |
| **原地体 autochthon** | 接近原始位置的**下盘** |
| **准原地体 parautochthon** | 卷入逆冲、但只被搬运了较短距离的基底/盖层碎片 |

Slide 14 一条容易被忽略的观察：**大位移逆冲的断层面可能非常"锐利"（sharp）**——这是应变一旦局部化就极其高效的证明。但 notes 提醒要小心解释这种锐利：野外见到的断层面**可能只是最后一期运动形成的一条裂面**。

### 2.5 断坪与断坡（flat & ramp）——本讲最核心的几何

Slide 15–16。低角度逆冲**并不是一个平面**，它**呈阶梯状向上切穿地层**：

> "A low angle thrust fault typically passes up stratigraphy in a series of steps in which it **alternately follows weak horizons and cuts up section across more competent layers**."

- **断坪（flat）**：断层**平行于层理**的段落（通常沿软弱层，如泥岩、蒸发岩）；
- **断坡（ramp）**：断层**切穿并截断层理**的段落（通常切穿强硬层）。

**关键点 1：断坪与断坡在上盘和下盘上的位置可以不同。**所以必须分别说 hanging wall flat / hanging wall ramp / footwall flat / footwall ramp。位移发生后，一段 hanging wall ramp 可能正躺在一段 footwall flat 之上（这正是断弯褶皱的成因，见 §2.10）。

**关键点 2（Slide 16）**：

> "Note that **for each hanging wall ramp there must be a corresponding footwall ramp**."

——断坡是"切穿地层"这个动作在两盘上留下的对应记录，成对出现。作图与解释时若只画出一侧的断坡而另一侧没有，几何上就不自洽。

### 2.6 断坡按走向与运输方向的关系分三类

Slide 17：

| 类型 | 与运输方向的关系 | 运动性质 |
|---|---|---|
| **前缘断坡 frontal ramp** | **垂直**于主运输方向 | 纯倾滑逆断层（pure dip-slip reverse） |
| **斜向断坡 oblique ramp** | 与运输方向**斜交** | 斜滑逆断层（oblique-slip reverse） |
| **侧向断坡 lateral ramp** | **平行**于运动方向 | **走滑断层**；把滑移从一个前缘断坡传递到另一个 → 称**传递断层 transfer fault**；若近直立并切穿上盘，则称**撕裂断层 tear fault** |

（"transfer fault" 与 "tear fault" 会在 W10 走滑一讲里再回来。）

### 2.7 逆冲系统：叠瓦扇与双重构造

Slide 18 是本讲最需要背熟的一页：

- **叠瓦扇（imbricate fan）**：逆冲常常成组出现，每条都是**铲式（listric）**且**滑移方向相同**，使各逆冲席像**屋瓦**一样叠置。
  - **前缘叠瓦扇 leading imbricate fan**：最大滑移在**最前缘那条**断层上；
  - **后缘叠瓦扇 trailing imbricate fan**：最大滑移在**最内侧（最靠后陆）那条**断层上。
- **底板逆冲（sole / floor thrust）**：叠瓦断层向下合并到的那条断层。
- **顶板逆冲（roof thrust）**：叠瓦断层也可能向上合并到一条断层上。
- **双重构造（duplex）**：**同时被底板逆冲与顶板逆冲限定**的叠瓦系统。
- **马（horse）**：双重构造内部**被断层完全包围**的岩块。
- **滑脱面 / 底部拆离 décollement / basal detachment**：一叠推覆体和/或叠瓦系统底部的那条主底板逆冲。

（Slide 18 notes 提醒回顾 Class 7 Slide 4：listric fault 是**向下倾角逐渐变缓**的弯曲断层。）

Slide 19 给了野外实例：Cornwall 的 Widemouth Bay 小尺度逆冲双重构造，配野外素描（标出 roof thrust 与 floor thrust）。**小尺度的 duplex 在海岸露头上很常见，是练眼力的好对象。**

### 2.8 双重构造的三种几何与扩展序列（**极易记混，重点**）

这是本讲最容易在考试里丢分的地方。三种几何 + 两种序列，要**分别记住"马在哪里成核"、"断坡朝哪倾"、"结果长什么样"**。

**（1）后陆倾斜型双重构造（hinterland-dipping duplex）——最常见**（Slide 20）

> "Thrust duplexes form sequentially, usually **propagating towards the foreland**: a horse is formed in the **footwall**, is displaced forwards, and becomes inactive; a new horse is then formed in the footwall…"

- 新的马在**下盘**成核 → 系统整体**向前陆扩展**；
- 限定马的**断坡向后陆倾斜**；
- 结果：一叠像倒下的多米诺骨牌一样、统一向后陆倾的马。
- 这种序列称为**前展式 / 背驮式（foreland-propagating / piggyback sequence）**——老的构造被驮在新的构造之上向前搬运。

**（2）背形堆垛（antiformal stack）**（Slide 22）

> "When there is **greater drive on the roof thrust than on the floor thrust**, foreland-propagating thrust duplexes develop such that the horses are **stacked**, resulting in an **antiform in the overlying thrust sheet**."

- 仍是前展式，但马**垂向堆叠**而不是侧向排开；
- 结果：上覆逆冲席被拱成一个**背形**。
- 实例照片：纽约州 Catskill 附近 Route 23 路堑。

**（3）前陆倾斜型双重构造（foreland-dipping duplex）——较少见**（Slide 23）

> "Less commonly, thrust duplexes develop such that **individual horses are added to the back of the duplex** and the ramps bounding the horses **dip towards the foreland**."

- 新的马加到双重构造的**后面**（后陆一侧）；
- 断坡**向前陆倾斜**。

**扩展序列的两种时序**（Slide 20 + Slide 21）：

| 序列 | 别名 | 新断层在哪里成核 | 扩展方向 |
|---|---|---|---|
| **前展式 foreland-propagating** | piggyback、foreland-breaking | 在**下盘**（现有断层之前方/下方） | **向前陆** |
| **后展式 break-back** | overstep（后退式/后展式） | 在**上盘** | **向后陆** |

Slide 21 另加一类：**不依序逆冲（out-of-sequence thrust）**——虽然逆冲通常向前陆扩展，但在**逆冲前锋之后**的位置发育新逆冲并不罕见；它可能是**新成核的断层**，也可能是**对早期断层的重新活化（reactivation）**。

**如何从剖面判断序列？**Slide 27 给了判据（Waterton 油田剖面，南阿尔伯塔，Lewis thrust 为底板逆冲、Mount Crandell thrust 为顶板逆冲）：

> "Foreland propagation… is implied by the fact that **higher thrusts/horses in the duplex are folded over the ramps and horses in the lower part of the section and so must be earlier**."

——**上部的逆冲/马被下部的断坡与马"驮着弯了"，说明上部的更老 → 前展式。**这是一条可以直接背下来的判据。notes 也坦白："Distinguishing whether the sequence is foreland-propagating (generally assumed to be more common) or break-back is **not always easy**."

Slide 28 更进一步：当马像挤西瓜籽一样被**从原位挤出（far-travelled horses）**时，重建逆冲序列**"perhaps the most difficult mapping challenge there is"**（例：喜马拉雅小喜马拉雅双重构造中的 Rangit duplex，十个马）。

### 2.9 反冲、pop-up、三角带、被动顶板双重构造

Slide 24：

- **反冲断层（back-thrust）**：逆冲席爬过断坡时，可能形成**倒向相反**的逆冲（相当于共轭断层的方位）。
- **pop-up**：一条逆冲与一条反冲，共用同一条底板逆冲，之间的岩块被"顶出来"。
- **三角带（triangle zone）**：同样是逆冲 + 反冲 + 共同底板逆冲的组合，但几何相反（顶部封闭）。

Slide 25 **被动顶板双重构造（passive roof duplex）**：

> "In circumstances where a duplex **underthrusts the foreland** so that the overlying units are **not themselves displaced laterally**, the roof thrust is described as a **passive roof thrust**."

- 本质上是一种**构造剥离（tectonic delamination）**；
- notes：被动顶板逆冲之下、前展式底板逆冲之上的那块区域**就是一个三角带**；
- **在富油气省中可以形成极好的圈闭。**

### 2.10 三维几何：尖灭线、分支线、截切线

Slide 29：

> "**No cross section though a thrust system should be constructed without considering how the individual faults link up to form three-dimensional networks of faults.**"

| 线 | 定义 |
|---|---|
| **尖灭线 tip-line** | 断层位移归零的那条线 |
| **分支线 branch-line** | 断层一分为二（**trailing branch-line**）或两条断层合并（**leading branch-line**）的那条线 |
| **截切线 cut-off line** | 某个接触界面与断层面相交的那条线 |

notes 补充的拓扑约束：**绕一个 horse，分支线构成一个含前缘段与后缘段的闭合环；绕一个叠瓦分支（imbricate splay），分支线连接尖灭线的两端，使尖灭线闭合成环。**讲义明说这些拓扑约束的应用超出本课范围，"you just need to be **aware that such constraints exist**"。但下面这句是可以直接用在野外和考试里的：

> "Whenever you map a fault, think about **how it connects with other faults to produce a consistent slip displacement story**."

### 2.11 逆冲相关褶皱之一：断弯褶皱（fault-bend fold）

Slide 31–32。**这是三类逆冲相关褶皱里最"被动"的一类。**

**成因**：断坡一旦形成、上盘开始爬上断坡，上盘就必然被变形成一个褶皱。

> "The shape of fault-bend folds is determined by the geometry of the ramp because they are **geometrically-necessary folds**. This means that **fold geometry can be predicted from ramp geometry and vice versa**."

**"几何必然褶皱"**——这是断弯褶皱的定义性特征，也是它最有用的地方：**看到褶皱形状可以反推断坡几何，反之亦然**（Suppe 1983 的经典工作）。

**运动学要点**：上盘岩层在爬坡时**先向一个方向转动（上坡时）、再向相反方向转动（进入上部断坪时"回正"）**。褶皱本身**固定在断坡的位置**不动，岩层从它里面穿过去。

**应变史（Slide 32，很漂亮的一页，容易出简答）**：

| 位置 | 应变/组构响应 |
|---|---|
| **下部断坪 lower flat** | 剪切 + 断层面上的拖曳 → 形成**劈理 S1** |
| **断坡 ramp** | 劈理**变陡、增强** |
| **上部断坪 upper flat** | "回正"过程中**剪切方向反转** → 劈理被**缩短**，原则上形成**褶劈理（crenulation）S2** |

是否真的能看到劈理（和褶劈理），取决于**断坡角**与**上盘岩石的力学性质/行为**。notes 很坦率：老师本人不知道有哪个实例的褶劈理被这样解释过，但"这不代表不存在"，值得去互层序列中的**软弱单元（泥岩）**里找。该图假定折劈机制为**弯滑流动（flexural flow）**且逆冲席趾部不变形；换别的褶皱机制（Class 2）会改变应变分布。

### 2.12 逆冲相关褶皱之二：断展褶皱（fault-propagation fold）

Slide 33–36。

**成因**：在逆冲**尖端（tip）之前**，变形以**更塑性的方式**被吸收，形成一对**向前陆倒转的不对称背形—向形对**。

**与断弯褶皱的关键区别**（这是本周最重要的判别题）：

> "Fault-propagation folds differ from fault-bend folds in that they **move with the propagating fault tip** rather than being **stationary at the location of the ramp**."

| | **断弯褶皱 fault-bend fold** | **断展褶皱 fault-propagation fold** |
|---|---|---|
| 位置 | **固定在断坡处**，岩层穿过它 | **随扩展的断层尖端一起移动** |
| 相对断层的位置 | **在断层之上**（上盘） | **在断层尖端之前** |
| 断层位移 | 褶皱处位移不为零 | **位移在尖端归零**，继续的缩短由尖端前方褶皱的生长吸收 |
| 对称性 | 由断坡几何决定，常有平顶（box-like） | **不对称**，向前陆倒转的背形—向形对 |
| 可否反推 | 由断坡几何**直接预测** | 需假设层厚变化，用**位移梯度 + 断层倾角**建模 |

**两种建模路线**（Slide 33 notes，Class 7 Slides 11–12 已提过）：
1. **假定层平行滑动（layer-parallel slip）+ 类膝折褶皱（kink-like）生长**——对**力学各向异性强**的系统更好；
2. **trishear（三角剪切）模型**——断层尖端前方一个三角形区域内的**分布式剪切**——对**各向异性较弱**时更好。

**被切穿的断展褶皱（breached fault-propagation fold）**（Slide 35）：逆冲可能**切穿**断展褶皱，通常沿**陡倾的中间翼（intermediate limb / connecting limb）**切过，形成**上盘背形 + 下盘向形（hanging wall antiform / footwall synform）**的组合。褶皱核部的**空间问题（space problem）**（太多岩石被挤进太小的空间）可导致**"出向斜逆冲"（out-of-the-syncline thrust）**；若主逆冲与之连通，向形就被切穿了。**注意：空间问题在背形核部同样存在，不只是向形。**

**⚠️ 上盘背形/下盘向形对不是断展褶皱的专利**（Slide 36）：它还可以由

- (a) **拖曳（drag）**——drag fold；
- (b) **连接翼的渐进剪切/减薄（progressive shearing/thinning of the connecting limb）**

产生。讲义直说："Distinguishing between these two cases and that of breached fault-propagation folds **may not always be easy**."

### 2.13 逆冲相关褶皱之三：断滑褶皱 / 拆离褶皱（detachment fold）

Slide 38–39。

**成因**：

> "Detachment folds form when **layers above a décollement shorten more than their substrate**."

- 经典实例：**侏罗山（Jura Mts.）**——被褶皱的层是灰岩，滑脱面沿**蒸发岩**；
- 特征：倾向于**直立（upright）**，且形成于**非常软弱的层**之上（超压泥岩或蒸发岩）；
- 它与断弯/断展褶皱的根本差别：**褶皱不是某一条切穿地层的断坡造成的，而是整套地层在一个水平滑脱面之上"多缩短了"的结果**——所以它长在**断坪上（folds on flats）**，而不是断坡上或断层尖端前。

**面积法定深度/缩短量**（Slide 39）——见 §3.3。

### 2.14 其他与逆冲有关的褶皱形态

- **断坡边缘的雁列褶皱**（Slide 37）：逆冲席边缘发育的褶皱，其方位由**下伏下盘断坡的方位**决定。在**侧向断坡与斜向断坡**之上，褶皱形成**雁列（en échelon）阵列**，而**斜列的偏斜方向指示运输方向**。实例：SE France 的 Digne nappe 的背形迹。
- **背形堆垛之上的褶皱**（Slide 40）：逆冲系统中的褶皱核部可能就是一个**背形堆垛**。实例：比利牛斯逆冲席前方始新统/渐新统中的 Oliana 背形。notes 指出：按该剖面，背形的生长与部分地层的沉积**同时发生**，且有些单元被逆冲切割、有些覆盖在逆冲之上，因而**可以获得非常紧的时间约束**。
- **同构造（生长）褶皱**（Slide 41）：**"natural experiments"**——检查并测定构造生长期间沉积的地层，可对构造形成时间给出紧约束。实例：NW Spain 的 Horta（沉积同时被逐渐掀斜）、Senez 生长褶皱（**左翼地层增厚**，因为褶皱在沉积期间就在生长；其上近水平的层**上超（onlap）**到褶皱上）、Digne nappe 就位期间 Vélodrome 构造的发育。notes 补充另一条思路：检查**同构造砾岩的砾石成分**判断造山带哪部分正在被抬升剥蚀——预期**更年轻的砾岩含有来自更深部（更老、变质更强）的砾石**。

### 2.15 褶皱—逆冲带的力学模型：临界楔（critical taper）

Slide 43–44。**这是本讲的力学核心。**

**观察**：褶皱—逆冲带在剖面上整体呈**楔形**，**向前陆减薄**。

**类比**：力学上，这个楔类似**推土机前面的一楔砂**——砂持续变形，直到达到一个**恒定的临界锥角（critical taper）**。

**受力**：(a) **后方的推力（push from behind）**；(b) **重力（gravity）**。

**锥角 = α + β**（α = 地表坡角，β = 基底坡角/滑脱面倾角）。它取决于**基底摩擦阻力**与**楔体材料强度**的相对大小：

| 变化 | 对锥角的影响 | 直觉 |
|---|---|---|
| **基底摩擦增大** | **锥角增大** | 需要后方更大的推力，材料在后方**堆得更高** |
| 基底摩擦减小 | 锥角减小 | 低摩擦 → 小锥角 |
| **楔体材料强度增大** | **锥角减小** | 更强的楔可以**更薄**而仍能整体滑动 |

**Slide 44：楔形的自我调节（scale invariance）**

> "Assuming friction and strength remain approximately constant, the shape of the wedge is **scale invariant** – consequently, **any process that acts to change the angle of taper during movement must be compensated**."

三条调节路径：

1. **楔增厚**时，α 增大，但 β 也增大（楔的重量把岩石圈压下去）→ 楔通过**加长**（在趾部形成叠瓦与双重构造）或**减薄**（地表的重力垮塌和/或内部伸展变形）来调节；
2. **楔减薄**（如被剥蚀）时，通过**内部缩短（逆断层、褶皱）造成的隆升**来维持地表坡度；
3. 这些调节伴随**同构造沉积（复理石 flysch）**，把物质在楔顶重新分配，以维持稳定的地表坡度。

**为什么需要楔模型？**（Slide 43 notes 的历史脉络，很值得记）Hubbert & Rubey (1959) 把逆冲席建模成**薄矩形板**，指出一个关键悖论：

> "**rocks are far too weak for a thin sheet of rock to be pushed over other rocks for 100s km without the sheet deforming internally** (it is like trying to push a wet napkin across a tabletop – the napkin will not move as a single rigid unit). Yet thrust sheets that have moved this far are observed."

**"推湿餐巾纸"**是最好记的比喻。保留矩形板几何的各种补救方案"none are entirely satisfactory"；**临界楔模型才是成功的解法**（Dahlen 1990）。

### 2.16 重力的作用与逆冲席内的应变分布

Slide 45：**重力在挤压造山带的发育中扮演重要角色——甚至可能是主导驱动力。**造山带发育时，地壳增厚在造山带**中央**最强；若足够软弱（可能因为受热），这块增厚抬升的地壳会**在自重下垮塌**，把推覆体推向前陆。三种情形：

| 情形 | 流动方向 | 类比 |
|---|---|---|
| **铺展 spreading** | 沿**地表坡**方向 | 冰川的流动；**允许沿基底上坡流动** |
| **滑动 gliding** | 沿**基底坡**方向 | 滑坡；notes 指出这在区域尺度上可能不重要，因为活动造山带的**基底滑脱面一般向后陆倾**（那样流动就得上坡）。几十 km 以下尺度的这类重力垮塌系统称 **surge zones** |
| **挤出 extrusion** | 在约束之间被挤出 | — |

重力驱动变形中可以预期楔体大部分区域有显著的**纯剪切共轴变形**分量，应变椭球的方位反映侧向约束的程度。

Slide 46–47：**逆冲席内应变的分布可以反过来判别驱动机制**（X = 应变椭球长轴，如拉伸线理方向）：

| 机制 | 逆冲席在滑动方向上的行为 | X 的分布特征 |
|---|---|---|
| **重力滑动 gravity-gliding** | **不缩短也不伸长**（纯简单剪切） | 简单剪切的标准 X 分布 |
| **后方推挤 push-from-behind** | **在滑动方向上缩短** | X 与剪切面的夹角**比纯简单剪切时更陡** |
| **重力铺展 gravity-spreading** | **在滑动方向上伸长（并减薄）** | X 呈 **S 形（sigmoidal）**变化，反映地表坡趋于变平 |

实例（Slide 47）：**瑞士阿尔卑斯 Morcles nappe** = 重力滑动或可能是重力铺展（晚期还有挤出的成分）；**澳大利亚 Bendigo 褶皱—逆冲带** = 后方推挤型，其应变变化由**褶皱翼间角（ILA）**与**轴面倾角/斑变晶周围应变影（strain fringes）中纤维的方位**（Class 4）得到。（notes：Bendigo 因背形枢纽中的巨大金矿——**saddle reefs**——而经济上重要。）

讲义自评："Such models of strain variation are **simplified** but may be used as a **framework** within which to interpret real strain measurements."

### 2.17 后陆一侧：底板逆冲往哪里去？

Slide 48。要有完整的逆冲系统图像，必须交代底板逆冲在后陆的归宿。三种可能：

- **A**：底板逆冲**回到地表**——一部分地壳的水平缩短被另一部分的伸展所平衡。notes 评论：整条前陆褶皱—逆冲带的缩短量太大，很难与一块可比的伸展区配对，**所以选项 A 大概只在较小尺度上成立**。
- **B**：底板逆冲**并入高变质级的、韧性变形的根带（root zone）**。notes：这是用根带中的其他缩短过程替代前陆的逆冲缩短；根带缩短增厚造成的地形高的**重力垮塌**，可能反过来驱动褶皱—逆冲带中随后的缩短。
- **C**：**褶皱—逆冲带最终的底板逆冲就是俯冲带**——逆冲带是**汇聚板块边界断层的一系列分支（splays）**。

### 2.18 平衡剖面（balanced cross-section）

Slide 50–56。**Slide 50 先列出四种本课不讲的技术**（等厚线图/isopach maps、分支线与截切线图、地层分隔图 stratigraphic separation diagrams、上盘序列图 hanging wall sequence diagrams），然后给出一条可以直接用的经验法则：

> **弓箭法则（bow-and-arrow rule）**："large thrusts are typically **convex towards the movement direction** in map view, and as a rule-of-thumb this movement direction is at **90° to the line connecting the two tip points** of the thrust."

**平衡剖面的定义**（Slide 51）：

> A balanced cross-section is one that is
> - **Admissible（可容许）**：剖面中所含构造彼此之间、以及对该构造背景而言，**在地质上是合理的**；
> - **Restorable / retro-deformable（可复原）**：剖面可以被"反变形"回去（时间倒推），**不留下显著的空隙或重叠**。

平衡剖面可用来**估算缩短量（或伸展量）**。两句必须记住的告诫：

> "**All** cross-sections should be balanced to check the self-consistency of the interpretation but note that **a balanced section is not necessarily a unique solution to the data.**"

（平衡只是**自洽性检验**，不是唯一性证明。）

**平衡剖面的三条初始假设**（Slide 52）：

1. **无体积变化（no volume change）**；
2. **平面应变（plane strain）**——所有变形都在剖面平面内；
3. （若用**线长平衡**技术）所有褶皱都是**平行褶皱（parallel folds）**、由**弯滑（flexural slip）**形成，因此**层厚保持不变**。

由假设 2 直接得到一条实践推论：

> "It follows that a balanced section through a thrust system should be **constructed parallel to the transport direction**."

**逆冲系统的平衡剖面必须平行于运输方向作。**（notes 还给了一条野外检验：若弯滑成立，则**层面内无应变**，可以通过检查层面上的化石**是否未变形**来验证——Class 2 Slides 26–27。）

**作图流程**（Slides 53–56）：

1. **建模板（template）+ 定 pin-line 与 loose-line**（Slide 53）
   - 检查**前锋逆冲之前的前陆地层**，画出**变形前**各层的地层厚度模板。模板通常是**layer-cake（水平层饼状）**，但若已知层厚沿剖面线的变化，**楔形单元也可以处理**。
   - 在剖面**未变形的一端**定一条参考线 = **pin-line**，在另一端定 **loose-line**（要量到的线）。
   - **pin-line 的三个条件**：(a) **垂直于层理**；(b) **尽可能贯穿整个地层序列**；(c) **不得穿过断层**。
   - 前锋断层的位置可以加到模板上。

2. **线长平衡（line-length balancing）**（Slide 54）
   - 量取某个地层标志（如两单元之间的界面）在**原剖面上**的长度，把这个长度加到模板上；
   - 在电脑绘图之前，量长度用**一段线绳**最方便；
   - **测量应当在每一个断片（fault slice）内部依次进行，由新到老（younger to older）**。

3. **评估复原结果**（Slide 55）——两套判据：

   | 判据 | 通过 | 不通过 |
   |---|---|---|
   | **可容许 admissible** | 复原后的**断坪—断坡夹角不超过约 35°**；复原后的断层**不回折（cut back on themselves）**、**不向下切层（cut down section）** | 断层回折 = inadmissible |
   | **可复原 restorable** | loose line 在复原剖面上是**直的 (a)** 或**平滑变化的 (b)(c)** | loose line **锯齿状 (d)** 或 **阶梯状 (e)** |

4. **面积平衡（area balancing）**（Slide 56）——见 §3.4。
   - **面积平衡可以独立于线长平衡使用，因此可以用来检验线长复原的结果。**
   - **不平衡的剖面需要修改——这可能涉及改变断坡角，或增删马。**

---

## 三、公式与图表

**本段是本周笔记的重心。**前半（§3.1–§3.5）是讲座的定量内容与图件；后半（§3.6–§3.9）是本周实习的下倾投影。

### 3.1 缩短量与缩短率

> 📎 背景补充：**讲义本身没有给出缩短率的定义式**（它只在 Slide 51 说平衡剖面"may be used to estimate the amount of shortening"）。以下定义式是根据 Class 3（应变）的通用约定补出的，考试写答案时要注意讲清自己用的是哪一种。

设某标志层**复原后（变形前）的长度**为 l₀，**现今（变形后）的长度**为 l₁。

**（1）缩短量（amount of shortening）**

$$\Delta L = l_0 - l_1$$

单位是长度（km 或 m）。这是平衡剖面最直接的产出。

**（2）缩短率（shortening / percentage shortening）**——**以初始长度为分母**

$$s = \frac{l_0 - l_1}{l_0} = \frac{\Delta L}{l_0}$$

**（3）伸长率（elongation / extension）e**——构造地质学的通用符号约定，**伸长为正、缩短为负**

$$e = \frac{l_1 - l_0}{l_0}$$

所以缩短时 e 为负，且 **s = −e**。

**（4）伸展量（stretch）S 与其平方（quadratic elongation λ）**

$$S = \frac{l_1}{l_0} = 1 + e, \qquad \lambda = S^2$$

> 📎 背景补充 · 算例：某褶皱—逆冲带剖面，复原长度 l₀ = 120 km，现今长度 l₁ = 80 km。
> - 缩短量 ΔL = 120 − 80 = **40 km**；
> - 缩短率 s = 40/120 = **33.3 %**；
> - 伸长率 e = (80 − 120)/120 = **−0.333**；
> - 伸展量 S = 80/120 = **0.667**。
>
> **⚠️ 极常见错误**：把 ΔL/l₁ = 40/80 = 50 % 当成缩短率。**分母必须是复原长度 l₀，不是现今长度 l₁。**（"缩短了 50%"与"缩短率 33%"在文献里都能见到不同作者的不同写法，所以**答题时务必写清公式**。）

### 3.2 面积平衡的基本关系式（Slide 56）

当层厚**不**保持不变时（例如层被剪切减薄、被压溶去体积，或褶皱不是平行褶皱），不能用线长平衡，改测**断层之间某单元的面积 A**。由于模板已经给出该单元的**原始厚度 t₀**，在**平面应变**假设下：

$$\boxed{L_0 = \frac{A}{t_0}}$$

得到的 L₀ 加进复原剖面即可。

**这个式子的来历**（Slide 56 notes 明说）："in plane strain the area (A = L₀t₀) remains constant during shortening"——**平面应变下面积守恒**，所以 A = L₀t₀ 恒成立，A 与 t₀ 都可测 → L₀ 可求。

**怎么量面积？**（notes 给了三条很"手工"的建议，值得一记）
1. 把剖面画在**方格纸**上，**数格子**；
2. 用**剪刀把该单元剪下来称重**（纸的面密度已知/可标定）；
3. 现在的绘图软件一般都有面积计算功能。

### 3.3 断滑褶皱的面积法（Slide 39）

若已知**到滑脱面的深度 t₁** 与**原始地层厚度 t₀**，在**剖面平面内无体积变化**的假设下，通过测量**超余面积 Ax**（excess area）可求出造成褶皱的缩短量 ΔL。讲义给出的式子是：

$$A_x = A = t_0 \,\Delta L$$

> ⚠️ **这条式子的下标存疑，见文末勘误表。**标准的"超余面积法"（Chamberlin 深度—滑脱面法）应为 **Aₓ = t₁ · ΔL**，其中 t₁ 是到滑脱面的深度。逻辑是：滑脱面之上厚度为 t₁ 的软弱层在缩短 ΔL 时面积守恒——损失的面积 t₁·ΔL 必须挤进褶皱核部，成为背形之下超出"区域面"的那块超余面积 Aₓ。
>
> 📎 背景补充 · 算例：若褶皱的超余面积 Aₓ = 2.0 km²，到滑脱面的深度 t₁ = 4.0 km，则 ΔL = 2.0 / 4.0 = **0.5 km**。反过来，若 ΔL 由别的方法已知，同一式子就变成**估算滑脱面深度**的工具——这正是这个方法在石油勘探中的经典用法。
>
> notes 提示这类面积法由 Mitra & Namson (1989) 详述，实践困难由 Wiltschko & Groshong (2012) 评论。

### 3.4 临界楔的角度关系（Slide 43）

讲义**没有给出定量的临界锥角公式**（这属于 Dahlen 1990 的内容，超出本课范围），只给出**定性关系**，但这个定性关系本身就是考点：

$$\text{锥角(taper)} = \alpha + \beta$$

- α = **地表坡角（surface slope）**；
- β = **基底坡角（basal slope）**，即滑脱面的倾角。

$$\alpha + \beta \;\uparrow\; \text{当基底摩擦} \uparrow \qquad\qquad \alpha + \beta \;\downarrow\; \text{当楔体强度} \uparrow$$

**记忆钩子**：把手指压在桌面上推一堆沙——桌面越粗糙（摩擦大），沙堆得越陡；沙里掺水泥变硬了（强度大），同样的坡就能推得更平。

### 3.5 讲座图件的文字描述（要能自己画出来）

#### 图 A：断坪—断坡几何（Slide 15–16）

**画法**：
1. 画一叠水平地层，自下而上编号 1（老）→ 5（新），层界画成细实线。
2. 画一条从左（后陆）下方向右（前陆）上方的逆冲断层，用**粗线**。这条线**不是直线**：它由"水平段—斜段—水平段—斜段…"交替组成。水平段沿着某一个层界走（**断坪 flat**），斜段（倾角约 15–30°）切穿若干层（**断坡 ramp**）。整体呈**向上向右的阶梯**。
3. **未发生位移时**：上盘的断坪与下盘的断坪重合，上盘的断坡与下盘的断坡重合。此时对每一段可分别命名 hanging wall flat / footwall flat / hanging wall ramp / footwall ramp。
4. **发生位移后**（把上盘整体沿断层向右上方移动一个距离 d）：原本贴合的 hanging wall ramp 现在**坐在了 footwall flat 之上**——这就是断弯褶皱的成因。此时如果沿剖面从左往右走，你会依次经过：footwall flat + hanging wall flat → footwall ramp + hanging wall flat → footwall flat + hanging wall ramp。
5. 每个 hanging wall ramp 一定有一个对应的 footwall ramp（Slide 16）。

#### 图 B：断弯褶皱的分步演化（Slide 31）

画**四格**连续图（时间从左到右或从上到下）：

- **第 1 格（t₀）**：水平层饼；断层由**下部断坪 → 断坡（倾角 θ_r，比如 25°）→ 上部断坪**组成，尚未位移。
- **第 2 格**：上盘向右移动一小段。上盘中原本水平的层，**在断坡上方被顶起来，形成一个前翼陡、后翼缓的隆起**。**两条膝折带（kink band）**从断坡的**上、下两个转折点**向上发散。上盘岩层在两条膝折带之间倾斜（大致平行于断坡）。
- **第 3 格**：位移增大。上盘的岩层**已经爬过断坡顶，进入上部断坪**，在断坡顶上方**第二次转折、恢复水平**。结果是一个**平顶的箱状背形（flat-topped / box-like anticline）**，前翼向前陆倾、后翼由断坡角控制。褶皱的**位置固定在断坡上方**。
- **第 4 格**：继续位移 → **平顶变宽**（顶板的水平段加长），但两翼的倾角**不变**。**这是断弯褶皱最关键的运动学特征：褶皱不"长高"，只"长宽"，而且不移动。**

在第 3、4 格上再叠加 Slide 32 的应变符号：下部断坪处画一组**缓倾的劈理（S1）**；断坡处画**变陡、更密集的 S1**；上部断坪处在 S1 上再叠一组**褶劈理（S2）**的小锯齿。

#### 图 C：断展褶皱的分步演化（Slide 33）

也是**四格**：

- **第 1 格**：水平层饼，断层从左下向右上扩展，**尖端（tip）停在地层中部**，用一个小圆点标出。
- **第 2 格**：位移开始。断层位移沿断层从后向前**逐渐减小，到尖端归零**。尖端之前的地层**被弯曲成一对不对称的背形—向形**：背形靠近断层上盘，向形在其前方（前陆侧）；两者共有一个**陡倾的中间翼（connecting limb）**；整体**向前陆倒转（verges towards the foreland）**。
- **第 3 格**：断层尖端**向前扩展**，褶皱对**跟着尖端一起向前移动**（这是与断弯褶皱的核心差别），同时翼间角变紧、中间翼变陡。
- **第 4 格（Slide 35 的变体）**：断层**切穿陡倾的中间翼** → 形成 **上盘背形 + 下盘向形**。若在向形核部另画一条小的**出向斜逆冲（out-of-the-syncline thrust）**并与主断层连通，切穿就更容易发生。

#### 图 D：双重构造的三种几何（Slides 20、22、23）——**务必分清**

三张图都画：底部一条**底板逆冲（floor thrust，水平粗线）**，顶部一条**顶板逆冲（roof thrust，水平粗线）**，中间夹着 4 个**马（horse）**，编号 1→4 表示形成先后。前陆在**右**，后陆在**左**。

| | **(1) 后陆倾斜型 hinterland-dipping** | **(2) 背形堆垛 antiformal stack** | **(3) 前陆倾斜型 foreland-dipping** |
|---|---|---|---|
| 马的编号顺序（左→右） | 1 在**最左**，4 在**最右** | 从底往上、从后往前叠 | 1 在**最右**，4 在**最左** |
| 成核位置 | **下盘** | 下盘 | **上盘** |
| 扩展方向 | **向前陆** | 向前陆 | **向后陆（break-back）** |
| 限定马的断坡倾向 | **向后陆（左）倾** | 向后陆倾但被后续的马拱弯 | **向前陆（右）倾** |
| 顶板形态 | 顶板逆冲大致平缓、微起伏 | 顶板逆冲被拱成一个**明显的背形** | 顶板逆冲大致平缓 |
| 触发条件 | 常规 | **顶板逆冲上的驱动力大于底板逆冲** | 较少见 |

**画背形堆垛时的要点**：4 个马不是横着排开，而是**一个骑在另一个上面**，像叠罗汉，整体外形呈一个**穹隆**，上覆逆冲席因此被拱成背形。

**顺带画 Slide 24 的三个小图**：
- **反冲（back-thrust）**：在断坡上方画一条**倾向相反**（向前陆倾、上盘向后陆运动）的断层；
- **pop-up**：一条前倾逆冲 + 一条反冲，两者向下并入**同一条底板逆冲**，中间的楔形块被**顶起**，顶部呈屋脊状；
- **三角带（triangle zone）**：同样两条断层 + 同一条底板逆冲，但两条断层**在顶部相交**，围出一个**尖顶朝上的三角形**，其内部的地层未被侧向搬运。
- **被动顶板双重构造**：三角带的一般化——一条前展式底板逆冲在下，一条**被动顶板逆冲**在上（其上盘不发生侧向位移），中间是一叠马。

#### 图 E：平衡剖面的复原步骤（Slides 53–56）

画**上下两栏**：上栏 = **变形剖面（deformed section）**，下栏 = **复原剖面（restored section / template）**。

1. 下栏先画 **template**：一叠水平的、等厚的层（layer-cake），厚度由前陆未变形区的地层柱给出。
2. 在两栏的**左端（前陆未变形一侧）**画一条**竖直的 pin-line**（垂直层理、贯穿全部地层、不穿断层）；在右端画 **loose-line**。
3. 在上栏的变形剖面上，从最前缘的断片开始，**一片一片**地量每个断片内每条地层界面的长度（用线绳），把这些长度**依次首尾相接**地铺到下栏的模板上，**每个断片内由新到老**。
4. 铺完后看下栏的 loose-line：
   - **直线** → 完美复原；
   - **平滑弯曲** → 可接受（不同层被稍不同地量到，但趋势连续）；
   - **锯齿状** 或 **阶梯状** → **不可复原**，剖面解释有问题。
5. 同时检查**可容许性**：复原后每条断层的断坪—断坡夹角是否 ≤ ~35°？断层是否回折或向下切层？
6. 不平衡就**改断坡角**或**增删马**，回到第 3 步。
7. 复原后：ΔL = （下栏铺开的总长度）−（上栏 pin-line 到 loose-line 的水平距离）。

### 3.6 下倾投影（down-plunge projection）：原理

**这是本周实习的核心技能，也是本课 practical 主线的招牌技术。**

**问题**：地质图是**水平面（或地表）上**看到的地质体的分布。如果褶皱**倾伏（plunging）**，那么在地图上看到的褶皱形态、以及在任何竖直剖面上画出的形态，**都不是褶皱的真实形态**——它是被"斜切"过的。

**解法**：沿**褶皱枢纽（fold axis）的倾伏方向**去看这个褶皱。因为**圆柱状褶皱（cylindrical fold）**的定义就是"任一点的几何都可以由沿枢纽方向的平移生成"，所以**垂直于枢纽的那个平面（profile plane / 剖面平面）上看到的截面，就是褶皱的真实截面**，而且它在整条枢纽上处处相同。把地图上的点**沿枢纽方向平行投影**到这个剖面平面上，就得到真实的褶皱剖面。

**两条关键定义**：

- **剖面平面（profile plane）** = **垂直于褶皱枢纽的平面**。因此：**profile plane 的极点 = 褶皱枢纽**。
  - 检验：St Monans 的枢纽是 **20/018**，剖面平面写作 **108/70 S**。极点方位 = 倾向 198 反向 = 018，极点倾伏 = 90 − 70 = 20 → **20/018** ✓ 完全一致。
  - Soln1 的枢纽是 **35/060**，剖面平面 **150/55SW**。极点：倾向 240 反向 = 060，倾伏 = 90 − 55 = 35 → **35/060** ✓。
- **下倾观察（looking down-plunge）** = 视线**顺着**枢纽倾伏的方向看进去（往地下看）。**上倾观察（up-plunge）**则相反。`NewHandout.md` 明说："The section may be drawn **looking up-plunge or down-plunge, whichever is the more convenient**"——两者都可以，但**必须在图名里注明是哪一种**，因为两者互为镜像。

> **左右端的方位怎么定？**（这是最容易搞反的一步，见 §6）
> **下倾观察时**：左端方位 = 倾伏方位 − 90°，右端方位 = 倾伏方位 + 90°。
> - St Monans：倾伏方位 018 → 左 = 288（WNW，标 **NW**），右 = 108（ESE，标 **SE**）。答案图 `Stereogram_2024.md` 与 `Section_2024.md` 标的正是 **NW…SE** ✓。
> - Soln1/Soln3：倾伏方位 060 → 左 = 330（NNW，标 **NW**），右 = 150（SSE，标 **SE**）。答案图标 **NW…SE** ✓。
>
> **上倾观察时左右互换。**

### 3.7 下倾投影的四条投影公式（`NewHandout.md`）

设：
- **θ** = 褶皱枢纽的**倾伏角（plunge）**；
- **d** = 图上待投影点到剖面线（line of section）的**距离，沿倾伏方向量**；
- **y** = 该点在基准面（datum）**之上**的**高程**；
- **h** = 投影后该点在剖面上、离剖面线（datum 迹线）的距离。

| 情形 | 公式 |
|---|---|
| **平坦地形 + 剖面平面（profile plane）** | $h = d\,\sin\theta$ |
| **平坦地形 + 竖直剖面（vertical section）** | $h = d\,\tan\theta$ |
| **起伏地形 + 向上投到剖面上的读数** | $h = a_1 + a_2 = d\,\sin\theta + y\,\cos\theta$ |
| **起伏地形 + 向下投到剖面上的读数** | $h = a_2 - a_1 = y\,\cos\theta - d\,\sin\theta$ |

> ✅ 我已用向量方法逐条复算：以 ĥ 表示水平面内沿倾伏方位的单位向量、ẑ 为铅直向上单位向量，枢纽单位向量 **a** = cos θ·ĥ − sin θ·ẑ，剖面平面内的"倾向"单位向量 **m** = sin θ·ĥ + cos θ·ẑ。位于 (d, y) 的点相对剖面线的位置向量为 d·ĥ + y·ẑ，其在 **m** 上的投影长度 = d sin θ + y cos θ ✓；当 y = 0 时退化为 d sin θ ✓；若沿枢纽投到**竖直**平面上，需沿 −**a** 走 t = d/cos θ，铅直落差 = t sin θ = d tan θ ✓。**四式全部正确。**

**两条实用提醒（来自 handout）**：
1. 对于**走向接近垂直于剖面线**的面，**真倾角与视倾角的差别很小**——可以省点力气，但**不要因此偷懒不查**。
2. **同一条界线（contact）可以在沿线多个点上分别做这个改正**，得到的界线形状在剖面平面内**具有正确的视倾角**。

### 3.8 视倾角的确定

`NewHandout.md` 开头就点明：把数据放到剖面上要分两步——**(a) 求每个面状读数在剖面上的视倾角；(b) 求每个读数在剖面上的投影位置**（即 §3.7）。

> "The easiest way to determine apparent dips is by using a **stereonet**."

**赤平投影求"剖面平面内的视倾角"的操作**（对**倾斜**的剖面平面同样适用）：
1. 在网上画出**剖面平面**的大圆（如 108/70 S）；
2. 画出**目标面**（如层理 040/45 NW）的大圆；
3. 两个大圆的**交点**即两平面的**交线**——这就是目标面在剖面上的**迹线（trace）**；
4. 沿**剖面平面的大圆**，从它与基圆的交点（即剖面平面的**走向线**，是水平的）数到那个交点，读出的角度就是**该面在剖面平面内的"视倾角"**。

> ⚠️ **注意这个角度的参考基准**：在**倾斜剖面平面**上作图时，图上量的角度是**相对剖面平面的走向线（水平）**的，它**既不是真倾角，也不是竖直剖面上的视倾角**。
>
> ✅ 我用向量法对 `Stereogram_2024.md` 与 `Soln1(1).md` 的全部角度做了独立复算，全部吻合（详见 §5.2、§5.4），这证实了上述解读。

### 3.9 起伏地形下的作图法：弧线法（method of arcs）

`NewHandout.md` 的后半页给的是**弧线法（method of arcs）**——它只是把 §3.7 那组三角计算**用图解方式解出来**。

**handout 给的四步**（原文转述）：

> (1) 画赤平投影图，确定褶皱枢纽的**倾伏角与倾伏方位**；
> (2) 在图幅**上方**画一条平行于倾伏方位的线（**"the axis"**）；画另一条与它**成直角**的线（**"the normal"**）；再画一条通过 axis 与 normal 交点、与 **"the normal" 成角等于褶皱倾伏角**的线（**"the slope"**）；
> (3) 按图示画出**地形线（topography lines）**——**务必确保没有垂向放大（no vertical exaggeration）**；
> (4) 可以开始作剖面了。

**加速技巧（handout 明确给出）**：
> 做完第 3 步后，可以在 Section 象限内画一组**竖直格线**（比如纸面上每 5 mm 一条），把它们**用弧线绕过来、向下扫过图幅**。这样就不必去投影"地形等高线与界线的交点"，而可以直接投影"**格线与界线的交点**"——但**你必须估计这些点的地形高度**，才知道在垂向标尺上要走多高，然后再"绕过来"。

> 📎 背景补充 · 弧线法为什么成立（handout 只给了操作，没给原理；以下为补充推导，答题不必写，但理解了就不会画错）：
> §3.7 的公式 h = d sin θ + y cos θ 本质上是把二维向量 (d, y) **正交投影**到方向 (sin θ, cos θ) 上。而 (sin θ, cos θ) 这个方向**与铅直方向成 θ 角** —— 这正是 "the slope" 与 "the normal" 成 θ 角的含义（"the axis" 代表水平的 d 轴，"the normal" 代表铅直的 y 轴，"the slope" 代表剖面平面内的量度方向 **m**）。
> **圆弧的作用**是"保长搬运"：以 axis 与 normal 的交点 O 为圆心画弧，弧上任意一点到 O 的距离相同，因此可以把一段距离**从图幅象限无失真地转到剖面象限**（相当于把纸面旋转 90°）。这就是为什么 handout 说"arc these around and down across the map"。
> **务必没有垂向放大**——因为整个方法依赖"图上的水平距离与垂直距离是同一把尺"，一旦垂向放大，θ 角的图解就失效了。

---

## 四、课堂补充

**本课全 10 周均无 transcript（课堂录音/文字稿）。本段内容全部来自讲义正文与 notes pane 中反复强调的注意事项、以及练习答案图件所透露的评分要点与作图规范，不是课堂口头补充。**

### 4.1 讲义 notes pane 里反复强调的方法论

1. **"看到褶皱，先问断层在哪里"**（Slide 2 notes）。这是把露头尺度观察与区域地质整合起来的入口。
2. **数据与解释必须分开**（Slide 4 notes）。1980 年代造山带重新解释时，很多老图**一个字都不用改**，改的只是构造解释。这条既是学术态度，也是 practical 的评分规范（见 §5.6）。
3. **断层永远不是孤立的**（Slide 29 notes）："Whenever you map a fault, think about how it connects with other faults to produce a **consistent slip displacement story**."
4. **模型是框架，不是答案**（Slide 46）："Such models of strain variation are **simplified** but may be used as a **framework** within which to interpret real strain measurements."
5. **平衡不等于唯一**（Slide 51）："a balanced section is **not necessarily a unique solution** to the data."
6. **老师会主动承认不确定性**——Slide 32 notes 说自己不知道有谁把褶劈理解释成断弯褶皱上部断坪的产物；Slide 36 说三种上盘背形/下盘向形的成因"may not always be easy"来区分；Slide 27 notes 说前展式与后展式"not always easy"来区分。**考试答"这两者不容易区分，判据是……"比强行给一个绝对答案更符合本课口味。**

### 4.2 哪些是"key material"

Syllabus 说得很明确：

> "Assessment, however, focuses on **key material (highlighted within each lecture)** that any Earth scientist with interests in geology should be familiar with." 并且 "A short document will be posted on Blackboard **each week highlighting the key material** from that week's Theory session, together with **indications of how this might be assessed**."

本周材料中**没有**这份 weekly highlights 文档，所以无法确知官方划的重点。但从讲义自身的结构信号可以推断：

- Slide 11 单独用一页写 "**Terminology**"、Slide 30 单独用一页写 "**Relationship between folding and faulting**"、Slide 42 单独用一页写 "**Models for fold and thrust belts**"——这三块是主体；
- Slide 49 单独用一页写 "**Some additional notes** — Section balancing"——这是**补充**；
- Slide 50 却又说 "another technique (balanced cross sections) is **important to be aware of**"。

**推断**：术语与几何（§2.4–§2.10）+ 褶皱与断层的关系（§2.11–§2.14）+ 临界楔（§2.15）是主考区；平衡剖面考**概念、定义、假设、判据**（admissible / restorable、三条假设、pin-line 三条件、35° 判据）的可能性大于考手工作业。

### 4.3 从练习答案反推的作图与评分规范

`NewHandout.md` 的 "Some general points when drawing cross-sections" 这一节，实质上就是一份**评分表**，逐条抄下来：

**剖面方位的选择**
- 均匀掀斜地区：理想剖面 = **垂直于层理走向的竖直平面**（此时图上所有倾角都是**真倾角**）；
- 褶皱地区：理想剖面 = **褶皱剖面平面（profile plane）**，即沿褶皱枢纽方向看；
- **例外**：褶皱**倾伏平缓**时，通常仍**直接画竖直剖面**；此时剖面的理想方位由**剖面平面的走向**给出。

**剖面上应表示的数据**
- 剖面应该**像野外图一样对待**：**所有用于构建它的数据都要标在剖面上**——露头要投影到剖面平面上画出来，面状产状读数要以**剖面平面内的视倾角**标出；
- 剖面要用**解释**收尾：地层界线、褶皱轴迹、断层的位置，**用与图幅相同的实线/虚线约定**；
- 构造简单时通常方便把**地形**画上；构造复杂、大量信息是从远处投影过来时，**地形就不必画了**（这正是 St Monans 剖面的情形，见 §5.3）。

**图面表达（Presentation）——直接的丢分项**
- **图名必须包含剖面平面的走向/倾角**（例："St. Monans shore section (**108/70 S**)"）；
- **剖面两端都要有方位标注**；
- **横向与纵向都要有比例尺**；
- **完整的图例（key）**，理想情况下还要附一个**简单的地层柱**。

`Section_2024.md` 的图例文字正好逐条印证了这些要求：它列出了 "line of section"、"apparent dip of S0 with younging direction"、"apparent dip of S1"、"formation / member contacts"、"axial trace of F1 antiform"、"axial trace of F1 synform"——**六项符号全部注明**，而且图名带 (108/70 S)，还写明 "Data projected down the plunge of F1 (20/018) on to section plane" 与比例尺 (1:2500)。**这就是满分剖面长什么样。**

`Section_2024.md` 另有三条"诚实标注"的示范，值得学：
- "**no topographic correction needed (wavecut platform)**"——说明为何没做地形改正；
- "**Actually shown are dip lines (reading at centre of line)**"——说明符号的画法约定；
- "**Areas of igneous just show the areas where country rock information is unobtainable, not their presence at depth**"——**说明某个图案的含义边界，防止读者过度解读**。

同样地，`Map_2024.md` 上明写了图幅的**局限**：

> "Map as presently drawn was created to get a detailed dataset of orientation readings around a real structure for teaching (stereonet) purposes. **Yet to map properly**: • Areas SW and E + SE of Davies Rock • Sedimentary and igneous contacts (some spot locations shown) • Internal details to igneous plugs, minor dykes • Minor faults"

以及 "a few minor folds over the hinge of the antiform (**further mapping SE of Davies Rock needed**)"。

**把"还没填清楚的地方"明确写在图上，是本课非常看重的职业习惯**——它正是 §4.1 第 2 条"数据与解释分开"的实践版本。

---

## 五、Practical 要点

**本周实习是 St Monans 的下倾投影剖面，与讲座主题（逆冲收缩构造）不同，两者分开处理。**

十份文件其实是**三组不相干的东西**，先分清楚再看：

| 组 | 文件 | 内容 |
|---|---|---|
| **方法说明** | `NewHandout.md`（1,050 词） | 剖面构建的两步、视倾角、投影公式（平坦/起伏地形）、作图规范、弧线法四步 |
| **主练习：St Monans（2024 版）** | `Map_2024.md` / `Stereogram_2024.md` / `Section_2024.md` | 分别是**图幅**、**赤平投影答案**、**剖面答案** |
| **合成练习 + 小练习** | `Soln2(1).md`（题面）、`Soln1(1).md`（赤平投影答案）、`Soln3(1).md`（剖面答案）；`Ex1soln.md` / `Ex2soln.md` / `Ex3soln.md` | 一套 1:10000 的合成 S0/S1/S2 练习；三份褶皱—劈理关系小练习的答案 |

> ⚠️ **注意 `Soln1`–`Soln3` 的编号不是解题顺序**：**`Soln2(1).md` 才是题面**（含题目文字与数据图），`Soln1(1).md` 是**第 1 步（赤平投影）**的答案，`Soln3(1).md` 是**第 2 步（剖面）**的答案。别被文件名顺序误导。

### 5.1 St Monans 练习的设定

**地点**：St. Monans, Fife（苏格兰东部 Fife 海岸），OS 方格 **NO**，图幅覆盖东距 518–522、北距约 010–013，每格 100 × 100 m；地图比例尺条为 0–100 m，剖面比例尺 **1:2500**。地名标注：**Davies Rock**、**Dovecot Neck**。

**地层**：**Pathhead Formation（Strathclyde Group）**，其中夹有两层可作标志层的灰岩：**Upper Ardross Limestone** 与 **Lower Ardross Limestone**。

**图面符号**（`Map_2024.md` 图例）：
- 走向/倾角 of **S0**（层理），**带younging direction（向上变新方向）**；
- 走向/倾角 of **S1**（**轴面**劈理）；
- **F1 的倾伏角/倾伏方位**（**tick 指向背形**）。

**图幅上的结构**：一个 **F1 背形**与一个 **F1 向形**（`Section_2024.md` 的图例分别给了两者的轴迹符号），背形枢纽之上还有"几个小褶皱"。图上有若干标注 **F** 的断层，以及**火成岩塞（igneous plugs）**与小岩墙。

**关键便利条件**：`Section_2024.md` 明写 —— **"no topographic correction needed (wavecut platform)"**。St Monans 的露头是**海蚀平台**，地形基本水平，所以**只需要用 h = d sin θ，完全不必动弧线法**。这是本练习被选中的原因之一。

> 📎 背景补充：St Monans 位于 Fife 的东内韦（East Neuk）海岸，是苏格兰石炭系（维宪阶，Strathclyde Group）的经典海岸露头，以海蚀平台上连续出露的褶皱、断层与"Ardross 灰岩"标志层著称；图上的 "neck"（如 Dovecot Neck）是石炭纪—早二叠纪东 Fife 火山颈群的一部分，它们切穿沉积岩、在图上表现为"围岩信息不可得"的区域。
>
> 📎 背景补充：本练习所用的露头，与三年级/二年级下学期的 **EART25102（高级地质野外技术）**在 Fife 的野外段是**同一片海岸**——也就是说，你在这张图上做的下倾投影，正是到了野外要现场做的事。**但需注意：本周的材料里没有任何一处提到这一关联**（讲义 Slide 4 的 notes 提到的是复活节野外课会去 **Loch Leven** 地区；syllabus 只说"One practical provides particularly useful preparation for the Easter field course (EART25102) and **will not be assessed in this unit**"，没有指明是哪一次 practical）。**因此这条关联属于课程结构上的补充，不是材料的陈述。**

### 5.2 St Monans 的赤平投影答案（`Stereogram_2024.md`）——**我已逐项复算**

**给出的数据/结果**：

| 项目 | 值 |
|---|---|
| **外翼 outer limbs** | **005/59 E** |
| **中间翼 middle limb** | **040/45 NW** |
| **轴面 axial plane** | **022/80 NW** |
| **褶皱枢纽 fold axis** | **20/018** |
| **翼间角 interlimb angle** | **83°** |
| **剖面平面 profile plane** | **108/70 S** |
| 剖面平面内的角度 | **40°、57°、83°、79°** |

**作图逻辑**（这就是解题步骤）：
1. 把所有**层理读数**画成**极点（poles to bedding）**；
2. 极点落在一个**大圆**上（因为褶皱是圆柱状的）→ 这个大圆就是 **profile plane**，其**极点就是褶皱枢纽（fold axis）**；`Stereogram_2024.md` 的 "Interpretation" 部分正是这样标的：poles to limbs / fold axis / pole to axial plane；
3. 极点在这个大圆上会聚成**两簇（poles to limbs）**，代表两个翼的平均产状；
4. **轴面 ≈ 两翼的平分面（axial plane ~ bisector）**——`Stereogram_2024.md` 明确写了这句；轴面必须**包含枢纽**；
5. **翼间角**由两翼极点之间的角度求补角得到。

**✅ 我的独立复算（用极点向量与叉积，ENU 坐标系）**：

- 外翼 005/59E 的极点 = 31/275；中间翼 040/45NW 的极点 = 45/130。
- 两极点的**叉积** → **20.5/018.0** —— 与材料的 **20/018 完全一致 ✓**
- 两极点夹角 = 97.6° → 两平面夹角 = 180 − 97.6 = **82.4° ≈ 83° ✓**
- 轴面 022/80NW 的极点 = 10/112；它与枢纽向量的点积 = **−0.003 ≈ 0**，即**该轴面确实包含枢纽 ✓**
- 由两翼极点之差算出的平分面 ≈ **021/83 NW**，与材料的 **022/80 NW** 在野外读数精度内一致 ✓
- 剖面平面 108/70 S 的极点 = **20/018 = 枢纽 ✓**

**那四个角度 40°/57°/83°/79° 是什么？**（材料没有明说，我算出来了）——它们是**在剖面平面内、相对剖面平面走向线（水平的 108 方向）量得的角度**：

| 对象 | 我算得的角度 | 材料 |
|---|---|---|
| **外翼**在剖面平面内的迹线 | 56.6° | **57°** ✓ |
| **中间翼**在剖面平面内的迹线 | 40.9° | **40°** ✓ |
| **轴面**在剖面平面内的迹线 | 79.2° | **79°** ✓ |
| 翼间角 | 180 − 57 − 40 = **83°** | **83°** ✓ |

**所以：在剖面上把外翼画成与水平参考线成 57°、中间翼成 40°（在另一侧），轴迹成 79°，两翼之间就自动是 83°。**这套数字是自洽的，**全部复算通过**。

> 📎 背景补充 · 这个褶皱是什么样的？倾伏 20° 属于**缓倾伏（gently plunging）**；轴面倾 80° 属于**近直立（upright / steeply inclined）**；翼间角 83° 按 Fleuty 分类属于 **open（开阔）**（gentle 180–120°、open 120–70°、close 70–30°、tight 30–10°、isoclinal < 10°）。综合起来是一个**缓倾伏、近直立的开阔褶皱**。（Fleuty 分类的界限值来自 Class 1 的褶皱几何内容，此处为提醒。）

### 5.3 St Monans 的剖面答案（`Section_2024.md`）

标题：**"St. Monans shore section (108/70 S)"**；副题：**"Data projected down the plunge of F1 (20/018) on to section plane"**；比例尺 **1:2500**；方位 **NW（左）… SE（右）**。

**图例六项**：line of section；apparent dip of **S0** with younging direction；apparent dip of **S1**；formation / member contacts；axial trace of F1 **antiform**；axial trace of F1 **synform**。

**四条附注**（都是可以照抄的好习惯）：
1. "no topographic correction needed (wavecut platform)"；
2. "Actually shown are **dip lines** (reading at centre of line)"；
3. "Areas of igneous just show the areas where **country rock information is unobtainable, not their presence at depth**"；
4. 重复了图幅上的"尚待填绘"清单。

**注意**：这张剖面**没有画地形**——完全符合 `NewHandout.md` 的规定（构造复杂、信息大量从远处投影过来时，地形不必画）。

### 5.4 合成练习（`Soln2` 题面 → `Soln1` 赤平投影 → `Soln3` 剖面）

**题面（`Soln2(1).md`）**：

> "In an area of **flat topography** a number of exposures of a **psammite** unit were mapped. **Bedding** and **crenulation cleavage** measurements were taken in several places, and the **asymmetry of the bedding/crenulation cleavage intersection lineation** was noted. In addition, an **early, nearly bedding-parallel, penetrative cleavage** was everywhere observed to indicate **an antiform to the north-west**.
> 1. From the data shown below, construct an accurate **down-plunge cross section**, using **form-lines** to show the shape of the folded bedding.
> 2. Again using form-lines, show **how the penetrative cleavage folds around the folds drawn in part 1**."

比例尺 **1:10000**。图例三项：层理走向/倾角；**褶劈理**走向/倾角；**褶劈理/层理交面线理的倾伏方位**（*tick 指向背形；双向 tick 表示存在对称小褶皱、且褶劈理为其轴面*）。

**面理编号**（由 `Soln3(1).md` 确认）：**S0 = 层理**、**S1 = 早期近层理平行的透入性劈理**、**S2 = 褶劈理**（是本次 **F2** 褶皱的轴面劈理）。所以这道题画的是 **F2 褶皱，它把 S0 与 S1 一起褶皱了**。

**`Soln1(1).md` 的赤平投影答案**：

| 项目 | 值 |
|---|---|
| **翼 A limb A** | **048/74 SE** |
| **翼 B limb B** | **118/40 NE** |
| **褶皱枢纽 fold axis** | **35/060** |
| **轴面（= 平分面）** | **075/70 N** |
| **翼间角** | **90°** |
| **剖面平面** | **150/55 SW** |
| 剖面平面内角度 | 翼 B **20°**、翼 A **70°**、轴面 **65°**、翼间角 **90°** |

**✅ 我的独立复算**：
- 翼 A 极点 = 16/318；翼 B 极点 = 50/208；叉积 → **35.5/059.8 ≈ 35/060 ✓**
- 两极点点积 = **0.0001 ≈ 0** → 两翼**正交** → 翼间角 **90° ✓**
- 轴面 075/70N 的极点 = 20/165；与枢纽点积 = **−0.002 ≈ 0** → **包含枢纽 ✓**
- 由两翼极点之差算出的平分面极点 = **20.3/165.1** → 与轴面极点 20/165 **完全一致 ✓**（真正的"axial plane = bisector"）
- 剖面平面 150/55SW 的极点 = 35/060 = 枢纽 ✓
- 剖面平面内（相对走向线 150）的角度：翼 A = **70.1°**（材料 70 ✓）、翼 B = **19.9°**（材料 20 ✓）、轴面 = **65.2°**（材料 65 ✓）；翼间角 = 180 − 70 − 20 = **90° ✓**

**全部通过，无误。**

**`Soln3(1).md` 的剖面答案**（profile plane 150/55SW，NW 左 / SE 右，比例尺 1:10000，**vertical scale = horizontal scale**）：
- 画出 **S0 的形线（form lines）**——一系列 F2 褶皱；标注的剖面内视倾角有 40、65、20、5、10、15、55、70 等；
- 再画出 **S1 的形线**——**S1 也被 F2 褶皱了**，形态与 S0 相似但**不重合**；
- **S2** 用轴面迹线表示。

**这份答案最有教学价值的一句话**（务必理解）：

> "Note that the **position of the axial trace to the folded S1 is shifted with respect to that of the folded S0** but that it is **in the same orientation**. The shifting is due to the **different orientation of S0 and S1 prior to D2**."

**解释**：F2 褶皱的**轴面方位**由 D2 的变形场决定，所以 S0 的 F2 轴迹与 S1 的 F2 轴迹**方位相同**；但**枢纽（hinge）落在哪一点**取决于被褶皱面在 D2 之前的方位——S0 与 S1 在 D2 前**不完全平行**（S1 只是"nearly bedding-parallel"），因此两者的枢纽点**沿剖面错开**。这是一个非常典型的"叠加褶皱"细节题。

**图例**：apparent dip of **S0**；apparent dip of **S2**（tick 指向背形）；symmetric minor **F2** observed。

### 5.5 三份小练习（`Ex1soln` / `Ex2soln` / `Ex3soln`）

这三份都只有几十词，是**图内文字**，内容是**褶皱—劈理关系与褶皱命名**的答案：

- `Ex1soln.md`：标注 **antiform / synform**；符号为 **trace of bedding**（粗线）与 **trace of cleavage**（细线）。
- `Ex2soln.md`：标注 **syncline / antiform / synform**，**younging**，**F1 / F2**，**74°**；东（E）在左、西（W）在右。
- `Ex3soln.md`：标注 **anticline / syncline / antiform / synform**，**F1 / F2**，**80°**，**fault with sense of movement**。

**这三题要练的核心区分**（📎 背景补充：材料只给了答案标注，未给文字说明，以下为概念梳理）：

| 术语对 | 判据 |
|---|---|
| **背形 antiform / 向形 synform** | **纯几何**：层面向上凸（closing upwards）= 背形；向下凸 = 向形。**不需要知道层序** |
| **背斜 anticline / 向斜 syncline** | **含层序信息**：核部为**最老**岩层 = 背斜；核部为**最新**岩层 = 向斜。**必须知道 younging** |
| 四者的组合 | 若地层正常（向上变新）：背形 = 背斜、向形 = 向斜。若地层**倒转**：**背形向斜（antiformal syncline）**、**向形背斜（synformal anticline）** 就会出现——这正是 Ex2/Ex3 里同时标出四个词的原因 |

**劈理—层理关系的用法**：轴面劈理与层理的**夹角与倒向**指示到枢纽的方向（劈理相对层理的旋向指向背形枢纽），这与 `Soln2` 题面里 "an early, nearly bedding-parallel, penetrative cleavage was everywhere observed to **indicate an antiform to the north-west**" 和图例里的 "**tick towards antiform**" 是同一件事。

### 5.6 下倾投影的完整操作流程（可照做）

把上面所有东西合成一条流水线。**St Monans 的情形（平坦海蚀平台）走 A 线，起伏地形走 B 线。**

**第 0 步：准备**
- 图幅、透明纸、赤平投影网（Wulff 或 Schmidt，本课通常用等面积 Schmidt 网）、直尺、量角器、圆规、线绳。

**第 1 步：由赤平投影定褶皱枢纽**
1. 把图上**所有层理（S0）读数**画成**极点**；
2. 用最佳拟合的**大圆**穿过这些极点（π-circle 法）；
3. 该大圆的**极点 = 褶皱枢纽（fold axis）**，读出**倾伏角 θ 与倾伏方位**（St Monans：**20/018**；合成练习：**35/060**）；
4. **交叉验证**：图上若有量到的 F1 倾伏读数或交面线理，应落在同一点；若有轴面劈理（S1/S2）读数，其大圆应**通过枢纽**。

**第 2 步：定剖面平面**
1. **剖面平面 = 枢纽的垂直面**：在网上以枢纽为极点画大圆，读出其走向/倾角（St Monans：**108/70 S**）；
2. **确定观察方向**：决定 looking **down-plunge**（沿倾伏方向看）还是 up-plunge，并**在图名里写明**；
3. **定左右端方位**：down-plunge 时，左 = 倾伏方位 − 90°、右 = 倾伏方位 + 90°（St Monans：**NW…SE**）。

**第 3 步：在图上画剖面线**
- 剖面线（line of section）应画成**垂直于倾伏方位**的一条直线（即剖面平面与基准面的交线），穿过构造的中心区域。

**第 4 步：求每个产状读数的视倾角**
- 对每个 S0（以及 S1/S2）读数，用 §3.8 的赤平投影法求出它在**剖面平面内**相对剖面平面走向线的角度。
- 提示：走向近垂直于剖面线的面，视倾角 ≈ 真倾角，可粗略处理，但**必须心里有数**。

**第 5A 步（平坦地形，St Monans 走这条）：投影位置**
1. 对图上每个待投影点，量出它到剖面线的距离 **d**，**沿倾伏方位（018）量**（不是垂直剖面线量的最短距离——两者在这里其实一致，因为剖面线本来就垂直于倾伏方位，但方向必须沿倾伏方位）；
2. 计算 **h = d sin θ**；
3. 在剖面上，从剖面线（datum 迹线）沿"向下"方向量出 h，得到该点在剖面上的位置。
   - 例：θ = 20°，某点在剖面线 NNE 侧 250 m 处 → h = 250 × sin20° = 250 × 0.342 = **85.5 m**（图上 1:2500 时为 34.2 mm）。
   - **注意方向**：位于剖面线**下倾伏侧**（018 方向）的点，投影后落在剖面的**一侧**；位于**上倾伏侧**（198 方向）的点落在**另一侧**。取反就整个剖面翻过来了。

**第 5B 步（起伏地形）：弧线法**
1. 按 §3.9 的四步搭好 "the axis / the normal / the slope" 三线与地形标尺，**确保无垂向放大**；
2. 对每个点，用 **h = d sin θ + y cos θ**（向上投）或 **h = y cos θ − d sin θ**（向下投）；
3. 或用格线 + 圆弧的加速法（§3.9），但要为每个交点**估计地形高程 y**。

**第 6 步：作图**
1. 把每个投影点按其视倾角画一小段**倾角线（dip line，读数点在线的中心）**；
2. 用**形线（form lines）**把同一个界面的投影点连起来——**形线必须与各点的视倾角相切**；
3. 圆柱状褶皱的形线应当**平滑、彼此近似平行**（若是平行褶皱则层厚不变）；
4. 加上**地层界线**、**褶皱轴迹**（背形/向形分别标）、**断层**（用与图幅相同的实线/虚线约定）；
5. 若同时有 S1/S2，重复上述过程画出它们的形线。

**第 7 步：图面收尾（丢分重灾区，见 §4.3）**
- 图名（含剖面平面走向/倾角 + 是否 down-plunge）、两端方位、横向与纵向比例尺（**且两者相等，no vertical exaggeration**）、完整图例、地层柱；
- 明确写出做了/没做哪些改正（如"no topographic correction needed"）与图幅的已知局限。

---

## 六、易错点 / 重点难点

### A. 逆冲收缩构造部分

**A1. 断弯褶皱 vs 断展褶皱（最高频混淆）**
记忆钩子：
- **断"弯"褶皱 = 断层弯了（ramp）造成的** → 褶皱**固定在断坡上**，岩层从中穿过；**位移在褶皱处不为零**。
- **断"展"褶皱 = 断层在扩展（propagating）造成的** → 褶皱**在断层尖端之前**、跟着尖端**跑**；**位移在尖端归零**。
一句话判据（Slide 33 原文）："fault-propagation folds **move with the propagating fault tip** rather than being **stationary at the location of the ramp**"。

**A2. 三种逆冲相关褶皱的"位置"记混**
- 断弯褶皱 → 在**断坡之上（on ramps）**；
- 断展褶皱 → 在**断层尖端之前（ahead of tips）**；
- 断滑/拆离褶皱 → 在**断坪之上（on flats）**——Slide 38 的标题就叫 "**Folds on flats** (detachment folds)"。

**A3. 双重构造三种几何记混**
用"**马在哪里成核**"一条线索串起来：
- 在**下盘**成核 → 前展式 → **后陆倾斜型**（若马侧向排开）或**背形堆垛**（若马垂向堆叠，因为顶板驱动 > 底板驱动）；
- 在**上盘**成核 → 后展式（break-back）→ **前陆倾斜型**。
**断坡的倾向永远指向"扩展方向的反面"**：向前陆扩展 → 断坡向后陆倾；向后陆扩展 → 断坡向前陆倾。

**A4. 前展式与后展式的时序判反**
从剖面证据判断（Slide 27）：**上部的逆冲/马被下部的断坡与马"驮弯了" → 上部更老 → 前展式（foreland-propagating）**。反过来，若下部构造切割了上部构造，才是后展式或不依序逆冲。**不要用"谁在前面就谁先"这种直觉**——前展式里最前面的那条恰恰是**最晚**形成的。

**A5. 前缘/侧向/斜向断坡的滑动性质搞反**
- **前缘断坡 ⊥ 运输方向 → 纯倾滑逆断层**；
- **侧向断坡 ∥ 运输方向 → 走滑断层**（transfer / tear fault）。
记忆钩子：断坡**挡在**运动前面 → 只能爬上去（倾滑）；断坡**沿着**运动方向排列 → 只能擦过去（走滑）。

**A6. 上盘背形/下盘向形 ≠ 一定是被切穿的断展褶皱**
Slide 36 明确列了另外两种成因：**拖曳（drag）**、**连接翼的渐进剪切/减薄**。答题要写"三种可能，区分不易，需要看……"。

**A7. 平衡剖面只查线长、不查面积**
- **线长平衡**依赖"平行褶皱 + 弯滑 + 层厚不变"这个**很强的假设**；
- 当层厚变化（剪切减薄、压溶）时线长平衡**失效**，必须用 **L₀ = A/t₀** 的**面积平衡**；
- Slide 56 明说面积平衡**可以独立使用，因此可以用来检验线长复原**。**两个都做才算真的检查过。**

**A8. 平衡剖面的方位取错**
由"平面应变"假设直接推出：**平衡剖面必须平行于运输方向**。若剖面斜交运输方向，物质会进出剖面平面，面积/线长都不守恒。

**A9. 把"平衡"当成"正确"**
平衡剖面是**自洽性检验**，**不是唯一解**（Slide 51）。这是简答题的送分点。

**A10. 临界楔的两条影响记反**
- **摩擦↑ → 锥角↑**（推土机要在粗糙地面上推砂，砂必须堆得更陡）；
- **强度↑ → 锥角↓**（更强的楔可以更薄而仍滑动）。
另外注意锥角 = **α + β 之和**，不是其中之一。

**A11. 混淆"重力铺展"与"重力滑动"**
- **spreading（铺展）**看**地表坡**——**可以沿基底上坡流**（像冰川）；
- **gliding（滑动）**看**基底坡**——只能下坡（像滑坡）；notes 指出区域尺度上活动造山带的基底滑脱面**向后陆倾**，所以 gliding 在区域尺度上多半不成立。

**A12. 皱脊（wrinkle ridge）与叶状陡坎（lobate scarp）混为一谈**
- **皱脊**：月海**内部**，**局部**挤压，成因是月海玄武岩重量造成的**盆地挠曲**，边缘伴生张性月溪；构造更复杂；
- **叶状陡坎**：**全球性分布**，成因是行星内部**净冷却的全球收缩**；是破出地表的逆断层尖端之上的**背形**。

### B. 下倾投影部分

**B1. 投影方向取反**
**必须沿褶皱枢纽的倾伏方向投影/观察。**若取反（up-plunge 却按 down-plunge 标方位，或反之），得到的剖面是**左右镜像**的——所有褶皱的倒向（vergence）、不对称性、轴面倾向全部反了，是致命错误。
**自查方法**：down-plunge 时，左端方位 = 倾伏方位 − 90°、右端 = 倾伏方位 + 90°。St Monans 倾伏 018 → NW…SE；若你画出来是 SE…NW，就是反了。**并且图名里一定要写明 "looking down-plunge"。**

**B2. 把视倾角当真倾角**
两处都会犯：
- 把图上量到的**真倾角**直接画到剖面上（错，必须先用赤平投影转成剖面平面内的视倾角）；
- 把在**竖直剖面**上算的视倾角用到**倾斜的剖面平面**上（错，两者不同）。
**St Monans 的中间翼真倾角是 45°，但在 108/70 S 剖面平面内只有 40°；外翼真倾角 59°，剖面平面内是 57°。**差得不多，但差了。

**B3. 剖面平面内角度的参考基准搞错**
在**倾斜**剖面平面上作图时，图上的"水平线"其实是**剖面平面的走向线**（水平的，但不在水平面上量角）。所有标注的角度都是相对这条线的。**它既不是真倾角，也不是相对真水平的角。**

**B4. 剖面平面与褶皱枢纽的关系记混**
**剖面平面的极点 = 褶皱枢纽**（不是"剖面平面包含枢纽"！包含枢纽的是轴面）。
- 剖面平面 **⊥** 枢纽；
- 轴面 **∋** 枢纽。
数值自查：剖面平面倾角 + 枢纽倾伏角 = 90°（St Monans：70 + 20 = 90 ✓；Soln1：55 + 35 = 90 ✓）。

**B5. 投影公式用错**
- **剖面平面**用 **h = d sin θ**；
- **竖直剖面**用 **h = d tan θ**。
两者在 θ 小时接近，θ 大时差很多（θ = 45° 时 sin = 0.707、tan = 1.000）。**先问自己"我要画的是 profile plane 还是 vertical section"。**

**B6. 起伏地形改正的正负号取反**
- 点在剖面线的**下倾伏侧**且高于基准面 → **h = d sin θ + y cos θ**（两项相加）；
- 点在**上倾伏侧**且高于基准面 → **h = y cos θ − d sin θ**（相减）。
**判据是点在剖面线的哪一侧**。搞反会把点投到剖面的错误深度上。（St Monans 是海蚀平台，y ≈ 0，两式退化为同一式，所以这题不必操心——但考试里别的题会考。）

**B7. 有垂向放大**
弧线法与所有下倾投影都要求**纵横比例尺相等**。`Soln3(1).md` 特意写了 "vertical scale = horizontal scale"。**一旦垂向放大，角度全部失真，褶皱形态与翼间角都不再真实。**

**B8. 忘了 S0 与 S1 的轴迹会错开**
`Soln3(1).md` 的注释：被褶皱的 S1 的轴迹相对被褶皱的 S0 的轴迹**发生了位移，但方位相同**——因为 S0 与 S1 在 D2 之前方位不同。**别把两条轴迹画成重合的。**

**B9. 背形/向形 与 背斜/向斜 混用**
- **antiform/synform 是几何**（向上凸/向下凸）；
- **anticline/syncline 需要层序**（核部老/核部新）。
地层倒转时会出现 **antiformal syncline / synformal anticline**（Ex2/Ex3 就在考这个）。

**B10. 图面规范的丢分**
图名不含剖面平面产状、两端不标方位、缺纵向或横向比例尺、图例不全、没标 younging direction、没写做过哪些改正——`NewHandout.md` 的 "Presentation" 一节每一条都是评分点。

---

## 七、本周术语表

### 7.1 逆冲与收缩构造（讲座）

| 英文 | 中文 | 要点 |
|---|---|---|
| contractional tectonic regime | 挤压（收缩）构造域 | 本周讲座主题；缩短由体积损失、纯剪切、屈曲、逆冲断层四者组合实现 |
| thrust | 逆冲（断层） | **低角度**为主、**逆倾滑**为主的断层或剪切带 |
| thin-skinned tectonics | 薄皮构造 | 前陆；**基底不卷入**，只涉及盖层 |
| thick-skinned tectonics | 厚皮构造 | 后陆；**基底卷入**，变质级较高 |
| foreland / hinterland | 前陆 / 后陆 | 逆冲运输方向的前方 / 后方 |
| nappe / thrust sheet | 推覆体 / 逆冲席 | 大位移低角度逆冲的上盘；宽度 >> 厚度；nappe = 法语"桌布" |
| klippe | 飞来峰 | 推覆体被侵蚀后的孤立残片（例：Chief Mountain） |
| (tectonic) window | 构造窗 | 侵蚀穿透推覆体、露出其下单元的"洞" |
| allochthon / autochthon / parautochthon | 外来体 / 原地体 / 准原地体 | 被搬运的逆冲席 / 接近原位的下盘 / 被搬运距离较短的碎片 |
| flat | 断坪 | 断层**平行于层理**的段落 |
| ramp | 断坡 | 断层**切穿层理**的段落 |
| hanging wall flat / ramp | 上盘断坪 / 断坡 | 位置在两盘上可以不同；**每个上盘断坡必有对应的下盘断坡** |
| footwall flat / ramp | 下盘断坪 / 断坡 | 同上 |
| frontal ramp | 前缘断坡 | ⊥ 运输方向；纯倾滑逆断层 |
| oblique ramp | 斜向断坡 | 斜交运输方向；斜滑逆断层 |
| lateral ramp | 侧向断坡 | ∥ 运输方向；**走滑断层** |
| transfer fault / tear fault | 传递断层 / 撕裂断层 | 把滑移从一条前缘断坡传给另一条；近直立并切穿上盘者为 tear fault |
| imbricate fan | 叠瓦扇 | 同向滑动的一组铲式逆冲，像屋瓦叠置 |
| leading / trailing imbricate fan | 前缘 / 后缘叠瓦扇 | 最大滑移在最前缘断层 / 最内侧断层 |
| duplex | 双重构造 | 同时被**底板逆冲**与**顶板逆冲**限定的叠瓦系统 |
| horse | 马 | 双重构造内被断层**完全包围**的岩块 |
| floor thrust / sole thrust | 底板逆冲 | 叠瓦断层向下合并到的断层 |
| roof thrust | 顶板逆冲 | 叠瓦断层向上合并到的断层 |
| décollement / basal detachment | 滑脱面 / 底部拆离 | 一叠推覆体/叠瓦系统底部的主底板逆冲 |
| hinterland-dipping duplex | 后陆倾斜型双重构造 | 最常见；马在**下盘**成核、向前陆扩展；断坡向后陆倾 |
| antiformal stack | 背形堆垛 | 顶板驱动 > 底板驱动；马**垂向堆叠**，上覆逆冲席被拱成背形 |
| foreland-dipping duplex | 前陆倾斜型双重构造 | 较少见；马加在双重构造**后方**；断坡向前陆倾 |
| foreland-propagating / piggyback sequence | 前展式 / 背驮式序列 | 新断层在**下盘**成核，系统向前陆扩展 |
| break-back / overstep sequence | 后展式 / 后退式序列 | 新断层在**上盘**成核，系统向后陆扩展 |
| out-of-sequence thrust | 不依序逆冲 | 在逆冲前锋**之后**发育的新逆冲，或对早期断层的重新活化 |
| back-thrust | 反冲（断层） | 倒向与主逆冲相反，相当于共轭方位 |
| pop-up | 顶出（构造） | 逆冲 + 反冲共用底板逆冲，中间块被顶起 |
| triangle zone | 三角带 | 逆冲 + 反冲的另一种组合，围出尖顶朝上的三角形 |
| passive roof duplex / passive roof thrust | 被动顶板双重构造 / 被动顶板逆冲 | 双重构造向前陆下冲、上覆单元不发生侧向位移；构造剥离过程；良好油气圈闭 |
| tip-line | 尖灭线 | 断层位移归零的线 |
| branch-line (leading / trailing) | 分支线（前缘 / 后缘） | 两断层合并 / 一断层分叉的线 |
| cut-off line | 截切线 | 某接触界面与断层面的交线 |
| fault-bend fold | 断弯褶皱 | 上盘爬上断坡形成；**几何必然褶皱**；固定在断坡处；可与断坡几何互推 |
| geometrically-necessary fold | 几何必然褶皱 | 由断层面形状**必然**导致的褶皱 |
| fault-propagation fold | 断展褶皱 | 断层尖端**之前**的不对称背形—向形对；**随尖端移动**；位移在尖端归零 |
| trishear | 三角剪切（模型） | 断层尖端前方三角形区内的分布式剪切；适用于力学各向异性较弱者 |
| breached fault-propagation fold | 被切穿的断展褶皱 | 逆冲沿陡倾中间翼切穿 → 上盘背形 + 下盘向形 |
| out-of-the-syncline thrust | 出向斜逆冲 | 由向形核部空间问题产生的断层；与主逆冲连通后促成切穿 |
| connecting / intermediate limb | 连接翼 / 中间翼 | 背形与向形共有的陡倾翼 |
| drag fold | 拖曳褶皱 | 上盘背形/下盘向形的另一种成因 |
| en échelon array | 雁列（阵列） | 侧向/斜向断坡之上的褶皱排列；**斜列偏斜方向指示运输方向** |
| detachment fold | 断滑褶皱 / 拆离褶皱 | 滑脱面之上的层比其基底缩短更多；直立；发育于极软弱层之上（侏罗山） |
| excess area (Aₓ) | 超余面积 | 断滑褶皱面积法中被测的面积 |
| syntectonic / growth fold | 同构造褶皱 / 生长褶皱 | 沉积与构造生长同时进行；提供紧的时间约束；翼部地层增厚、顶部上超 |
| critical taper | 临界锥角 | 楔形褶皱—逆冲带的自我调节角；= α（地表坡）+ β（基底坡） |
| wedge model | 楔模型 | 推土机前的砂楔类比；解决 Hubbert & Rubey 的"推湿餐巾纸"悖论 |
| gravity spreading / gliding / extrusion | 重力铺展 / 滑动 / 挤出 | 分别沿地表坡 / 基底坡 / 约束之间流动 |
| surge zone | 涌动带 | 几十 km 以下尺度的重力垮塌系统 |
| flysch | 复理石 | 同构造沉积，重新分配楔顶物质以维持稳定坡度 |
| root zone | 根带 | 底板逆冲并入的高变质级韧性变形带 |
| wrinkle ridge | 皱脊 | 月海内部的局部挤压构造；盆地挠曲成因 |
| lobate scarp | 叶状陡坎 | 全球收缩（行星冷却）成因；破出地表逆断层之上的背形 |
| balanced cross-section | 平衡剖面 | 同时满足 **admissible** 与 **restorable** 的剖面 |
| admissible | 可容许的 | 构造在地质上合理；复原后断坪—断坡夹角 ≤ ~35°、断层不回折不向下切层 |
| restorable / retro-deformable | 可复原的 | 可反变形回去、不留显著空隙或重叠；loose line 直或平滑 |
| pin-line | 定位线 | 未变形端的参考线；⊥ 层理、贯穿地层、不穿断层 |
| loose-line | 松动线 | 剖面另一端、用于评估复原质量的线 |
| template | 模板 | 由前陆未变形地层建立的变形前地层厚度图（通常 layer-cake） |
| line-length balancing | 线长平衡 | 量标志层长度；假设平行褶皱 + 弯滑 + 层厚不变 |
| area balancing | 面积平衡 | **L₀ = A/t₀**；层厚变化时使用；可独立检验线长平衡 |
| bow-and-arrow rule | 弓箭法则 | 大逆冲在平面上向运动方向凸出；运动方向 ⊥ 两尖灭点连线 |

### 7.2 下倾投影与剖面作图（实习）

| 英文 | 中文 | 要点 |
|---|---|---|
| down-plunge projection | 下倾投影 | 沿褶皱枢纽倾伏方向把图幅数据投到剖面平面上，得到褶皱的真实截面 |
| profile plane | 剖面平面 | **⊥ 褶皱枢纽**的平面；其**极点 = 枢纽**；圆柱状褶皱在其上的截面处处相同 |
| fold axis / hinge line | 褶皱枢纽 / 枢纽线 | 由层理极点大圆（π-circle）的极点求得；本周 St Monans 为 20/018 |
| plunge / plunge direction | 倾伏角 / 倾伏方位 | 枢纽的产状；记法 20/018 = 倾伏 20° 向 018 |
| looking down-plunge / up-plunge | 下倾观察 / 上倾观察 | 两者互为镜像，**必须在图名注明** |
| apparent dip | 视倾角 | 非垂直于走向的剖面上量到的倾角；用赤平投影求 |
| true dip | 真倾角 | 最大倾斜方向上的倾角 |
| line of section | 剖面线 | 剖面平面与基准面（datum）的交线 |
| datum | 基准面 | 高程零参考面 |
| method of arcs | 弧线法 | 用图解（圆弧 + "axis/normal/slope" 三线）代替三角计算 |
| the axis / the normal / the slope | "轴线" / "法线" / "坡线" | 弧线法的三条辅助线；slope 与 normal 的夹角 = 褶皱倾伏角 |
| vertical exaggeration | 垂向放大 | 下倾投影中**必须为零**（纵横比例尺相等） |
| form line | 形线 | 用来表示被褶皱面形态的连线，须与各点视倾角相切 |
| dip line | 倾角线 | 剖面上表示产状的小线段，读数点位于线的中心 |
| axial trace | 轴迹 | 轴面与图幅/剖面的交线 |
| cylindrical fold | 圆柱状褶皱 | 几何可由沿枢纽的平移生成；下倾投影成立的前提 |
| interlimb angle | 翼间角 | 两翼之间的角；St Monans 为 83°（open） |
| axial plane / axial surface | 轴面 | ≈ 两翼的**平分面**；**包含枢纽** |
| bisector | 平分面（线） | 轴面的近似判据 |
| S0 / S1 / S2 | 层理 / 第一期面理 / 第二期面理 | 本周合成练习中：S0 = 层理、S1 = 早期近层理平行透入性劈理、S2 = 褶劈理（F2 轴面） |
| crenulation cleavage | 褶劈理 | 叠加在早期面理上的微褶皱劈理；本练习中为 S2 |
| penetrative cleavage | 透入性劈理 | 贯穿整个岩石体积的劈理；本练习中为 S1 |
| intersection lineation | 交面线理 | 两个面理的交线；其不对称性（tick）指向背形 |
| younging direction | 向上变新方向 | 判别 anticline/syncline 与地层是否倒转的依据 |
| antiform / synform | 背形 / 向形 | **纯几何**判据（向上凸 / 向下凸） |
| anticline / syncline | 背斜 / 向斜 | **需层序**判据（核部老 / 核部新） |
| antiformal syncline / synformal anticline | 背形向斜 / 向形背斜 | 地层倒转时出现的组合 |
| psammite | 变质砂岩 / 长英质变粒岩 | 合成练习中被填绘的岩性单元 |
| wave-cut platform | 海蚀平台 | St Monans 的露头形式；地形近水平 → **无需地形改正** |
| St Monans, Fife | 苏格兰法夫郡圣莫南斯 | 本周实习的真实露头；Pathhead Formation（Strathclyde Group），含 Upper / Lower Ardross Limestone 标志层 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Class8_Contractional.md`，Slide 39「Detachment folds」正文 | "If the **depth to the detachment ( t1 )** is known, together with the **initial stratigraphic thickness ( t0 )**… we can find the amount of shortening ( D L ) … by measuring area Ax : **Ax = A = t0 D L**" | **公式中的下标存疑。**标准的超余面积法（Chamberlin 深度—滑脱面法）应为 **Aₓ = t₁ · ΔL**，即用**到滑脱面的深度 t₁**。推导：滑脱面之上厚度 t₁ 的层在平面应变下面积守恒，t₁·L₀ = t₁·(L₀ − ΔL) + Aₓ ⟹ Aₓ = t₁·ΔL。若公式真的只用 t₀，则前一句中特意引入的 t₁ 完全用不上，逻辑不闭合 | 建议按 **Aₓ = t₁ · ΔL** 理解与作答。**标为"存疑"而非确定错误的原因**：(1) 该页的原图（Price & Cosgrove p.166）未随 pptx→md 转换保留，无法确认图中 t₀ / t₁ 的实际标注位置；(2) 若原图中 t₀ 被定义为"滑脱面到被褶皱标志层之间那套地层的**初始**厚度"（即变形前的滑脱面深度），则 Aₓ = t₀·ΔL 也可自洽。**请对照原 slide 的插图核对两个下标的定义后再使用。** |
| `Class8_Contractional.md`，Slide 39 | "Ax = A = **t0 D L**"（另 Slide 2、Slide 43 等处同样出现 "D L"、"a + b"、"( a )"、"( b )"） | **希腊字母与下标在 pptx→md 转换中丢失**（转换缺陷，非内容错误） | "D L" = **ΔL**；"a"、"b" = **α**、**β**；"t0"、"t1"、"Ax" = **t₀**、**t₁**、**Aₓ**。本笔记已统一改写为正确符号 |
| `Class8_Contractional.md`，Slide 15 底部标签列表 | "footwall flat / hanging wall flat / footwall ramp / hanging wall flat / footwall flat / hanging wall ramp" | **不是错误，是 Fossen p.364 插图上的标签被转换器按版面顺序抓取，脱离了原图位置**，单看这串文字无法还原对应关系 | 需配合原图理解。本笔记 §3.5 图 A 已用文字重建了这套标签的正确对应关系 |
| `Class8_Contractional.md`，Slide 2 正文第一句 | "The essential features of the first three of these **have been already been covered**" | 拼写/语法重复（"have been already been"） | 应为 "have already been covered"。不影响理解 |
| `Class8_Contractional.md`，Slide 55 图注文字 | "**inadmissable** section" | 拼写 | 应为 "**inadmissible**" |
| `NewHandout.md`，"Some general points when drawing cross-sections" 第二条 | "the ideal orientation for a **cross -ection**" | 拼写/断字错误 | 应为 "cross-section" |
| `Soln2(1).md`，图例第三条 | "plunge direction of **crenuation** cleavage/bedding intersection lineation" | 拼写 | 应为 "**crenulation**" |
| `Map_2024.md` / `Section_2024.md` / `Stereogram_2024.md` / `Soln1(1).md` / `Soln3(1).md` / `Ex1–3soln.md` | 图内文字被转换器抓成一长串数字与词组（如 "013 73 46 52 013 46 65 72 25 52 63 53…"） | **图件本体（地图、赤平投影网、剖面）未随 PDF→md 转换保留**，仅剩图内文字碎片（转换缺陷，非内容错误） | 关键的方位数据与角度均可从残留文字中恢复，本笔记 §5.2 / §5.4 已全部列出并复算。但**具体的界线形状、露头分布、格线位置无法从 md 还原**，作图练习仍需查阅原 PDF |

**除上述以外，本周材料中所有可复算的几何量我均已用向量方法逐一独立核对，结果全部与材料一致，未发现错误：**

- `Stereogram_2024.md`：由外翼 005/59E 与中间翼 040/45NW 求得的褶皱枢纽 = **20.5/018.0**（材料 20/018 ✓）；翼间角 = **82.4°**（材料 83° ✓）；轴面 022/80NW **包含**枢纽（点积 −0.003 ≈ 0 ✓）且 ≈ 两翼的平分面（算得 021/83NW，与 022/80NW 在读数精度内一致 ✓）；剖面平面 108/70 S 的极点 = **20/018 = 枢纽** ✓；剖面平面内的角度：外翼 **56.6°**（材料 57 ✓）、中间翼 **40.9°**（材料 40 ✓）、轴面 **79.2°**（材料 79 ✓）、翼间角 180 − 57 − 40 = **83°** ✓。
- `Soln1(1).md`：由翼 A 048/74SE 与翼 B 118/40NE 求得的褶皱枢纽 = **35.5/059.8**（材料 35/060 ✓）；两翼极点点积 = **0.0001 ≈ 0** → 翼间角 **90°**（材料 90° ✓）；轴面 075/70N **包含**枢纽（点积 −0.002 ≈ 0 ✓）且其极点 **20.3/165.1** 与由两翼极点求得的平分面极点 **完全一致** ✓；剖面平面 150/55SW 的极点 = **35/060 = 枢纽** ✓；剖面平面内角度：翼 A **70.1°**（材料 70 ✓）、翼 B **19.9°**（材料 20 ✓）、轴面 **65.2°**（材料 65 ✓）。
- `NewHandout.md` 的四条投影公式 **h = d sin θ**、**h = d tan θ**、**h = d sin θ + y cos θ**、**h = y cos θ − d sin θ**，我用向量正交投影法逐条推导验证，**全部正确**（推导见 §3.7 注）。
- 两份材料中"剖面平面倾角 + 枢纽倾伏角 = 90°"的关系均成立：St Monans **70 + 20 = 90** ✓；合成练习 **55 + 35 = 90** ✓。
- 剖面两端的方位标注与"下倾观察"一致：St Monans 倾伏方位 018 → 左 288（NW）/ 右 108（SE），材料标 NW…SE ✓；合成练习倾伏方位 060 → 左 330（NW）/ 右 150（SE），材料标 NW…SE ✓。

**另需重申：本周讲座（逆冲与收缩构造）与实习（St Monans 下倾投影剖面）主题不一致，是本课 practical 独立成序列的教学安排，不属于材料错误，故不列入本表。**
