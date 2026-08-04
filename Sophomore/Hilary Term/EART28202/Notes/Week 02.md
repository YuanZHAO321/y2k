# EART28202 Structural Geology — Week 02 学习笔记

> 本周材料：
> - 讲义 `Lecture/Week 2/Class2_FoldFormation.md`（Class 2 : How folds form，42 张幻灯片，含 notes pane 注释）
> - 练习 `Practical/Week 2/`：`Cover.md`（Tarskavaig Bay 图幅题面）、`SolnMap.md`（图幅答案注记）、`SolnFold.md`（褶皱几何赤平投影答案）、`SolnGneissFault.md`（片麻岩内构造与断层答案）、`Ex5-1.md`（额外练习题面，旧考卷）、`Ex5soln.md`（额外练习答案）
> - 本课全 10 周均**无 transcript**（无课堂录音转写），详见第四节说明。

---

## 一、本周主题

### 本周在全课骨架中的位置

EART28202 是春季学期（Hilary Term）的第一门构造地质学课，**直接承接大一/大二的 EART24001 地质图**：EART24001 教会你走向线、剖面构建、赤平投影这些**纯几何**工具，EART28202 则把这些几何量升级成**力学与运动学的证据**——同样一张图，不再只问"这层往哪儿倾"，而问"是什么样的受力和流变，把它变成现在这个样子"。

全课骨架分三段：

| 段落 | 周次 | 内容 |
|---|---|---|
| 几何学 | W01–W03 | 褶皱几何与协调小构造 → **褶皱形成（本周）** → 应变 |
| 力学 | W04–W06 | 剪切带 → 应力 → 破裂与小侵入体的就位 |
| 构造类型 | W07–W10 | 断层 → 收缩构造 → 伸展构造 → 走滑构造 |

**本周（Class 2）正好是"从形态描述转向成因机制"的转折点。** 讲义第 2 张幻灯片开门见山地把这层关系说透了：

> "One of the key reasons for describing the geometry of folds (Class 1) is to place constraints upon how they formed."

也就是说，Week 01 里辛苦建立的那套描述语汇——褶皱轴、轴面、翼、翼间角、平分面（bisector）、等倾线（dip isogon）分类 1A/1B/1C/2/3、协调小构造与劈理不对称——**在本周全部变成"诊断工具"**：正交层厚不变（Class 1B）指向屈曲；轴面向层厚不变（Class 2）指向剪切/被动褶皱；外弧张裂脉指向切向纵向应变；一条先存线理在赤平投影上摊成小圆还是大圆，直接判定折叠机制。Week 01 的"名词表"到本周成了"检索表"。

### 本周主线

讲义把"褶皱怎么来的"拆成两个**互相独立的层次**，这是本周最重要、也最容易被学生揉在一起的结构：

1. **褶皱的类型（types of folding）** —— 讲的是**驱动力如何加载**：
   - **屈曲 buckling**：载荷**平行**层面 → 力学不稳定性放大（"主动褶皱 active folding"）
   - **弯曲 bending**：载荷**高角度斜交/垂直**层面 → 被迫成褶（"forced folding"）
   - **被动褶皱 passive folding**：纯运动学效应，标志层只是"随流而动"的一条被动记录线

2. **褶皱的机制（folding mechanisms）** —— 讲的是**岩层内部靠什么变形来实现弯曲**：
   - **弯滑 flexural slip / 弯流 flexural flow**
   - **切向纵向应变 tangential longitudinal strain (TLS)**
   - **剪切褶皱 shear folding**

> ⚠️ **类型 ≠ 机制。** 屈曲和弯曲这两种"类型"，其内部实现的"机制"都可以是弯滑/弯流或 TLS（讲义 Slide 25 明说：这两种机制"are the folding mechanisms that apply for buckling and bending"）；被动褶皱则对应剪切褶皱机制。把 buckling / flexural slip / passive folding 三个词并列成"三大机制"是**典型的概念混淆**，考试审题时务必分清（见第六节）。

本周讲义的重心明确落在**屈曲**上：弯曲只在 Slide 23 列了个清单（留到 Class 8–10 讲构造背景时展开），被动褶皱只在 Slide 24 提了一页（留到 Class 4 剪切带展开）。屈曲则从单层 → 多层 → 各向异性体 → 褶皱的"一生"，占了 Slide 3–22 整整二十页。最后 Slide 31–41 转向**非圆柱状褶皱**与**叠加褶皱干涉型式**，把本周与 Practical 的 Tarskavaig Bay 图幅衔接起来。

---

## 二、核心概念

### 2.1 三种褶皱类型

| 类型 | 定义（讲义 Slide 2） | 力学本质 |
|---|---|---|
| **Buckling 屈曲** | 载荷沿层面方向施加时发生的褶皱 | 压应力沿面内传递，褶皱是**力学不稳定性的放大（amplification）**；又称 active folding |
| **Bending 弯曲** | 载荷与层面高角度相交时发生的褶皱 | 非均匀的力横跨层面施加；又称 forced folding |
| **Passive folding 被动褶皱** | 穿过或包含于变形体中的标志层被折叠 | **纯运动学**：只是描述一条标志线在流动中被带动后的形状 |

### 2.2 屈曲的两个必要条件

讲义 Slide 3 给出屈曲发生的两个前提，缺一不可：

1. **被折叠层必须比围岩（matrix）更"能干"（competent）** —— 即黏度（viscosity）更高。
2. **层界面上必须存在小的不规则性（mechanical instabilities）** —— 这些微小起伏是褶皱的**成核点（nucleation sites）**。讲义注释里说得很直白："Without these there is nothing to kick the folding off."

关于黏度，notes pane 补了一段很重要的流变学铺垫：

- 黏度 = 流体对剪切的阻抗；低黏度"稀"，高黏度"稠"（水 vs. 糖浆）。**地质时间尺度上岩石会流动，因而可视为黏性流体。**
- 严格定义：**黏度 = 剪应力 / 剪应变速率**（这个定义在 Class 3/Class 5 会正式建立）。
- 若黏度与所施加剪力无关，称 **Newtonian viscous（线性黏性）**；岩石的黏度通常**随剪力增大而降低**，即多为 **shear-thinning（剪切变稀）的非牛顿流体**。剪切变稠（shear-thickening）在地质环境中不出现（讲义顺带提了个八卦：这是爱因斯坦当年对面团感兴趣的原因）。

📎 **背景补充**：屈曲理论在地质材料中的系统发展始于 1960 年代 Biot 与 Ramberg 的工作，讲义 Slide 3 注释明确点名了这两位，并说"屈曲理论本身超出本课范围——我们只讨论理论/实验/数值模型试图解释的那些现象"。**所以考试不会要求你推导公式，只会要求你会用公式、会解释各项的物理意义。**

### 2.3 单层屈曲（single layer buckling）

经典屈曲理论的做法：假设单层上叠加了一系列不同波长的小正弦扰动，去找**放大最快的那个波长**——它就成为最终褶皱的**主波长（dominant wavelength）**。

结论（公式详见第三节）：

- **波长随层厚增大而增大**（Slide 5）。野外照片证据：同一露头中薄层的波长短、厚层的波长长；同一层沿走向变厚处波长也变长。
- **黏度比越大**，褶皱**放大越快**，且**层的加厚（layer thickening）越少**（Slide 6）。层的加厚指的是"没有被屈曲吸收掉的那部分平行层缩短"。
- **褶皱的影响随远离折叠层迅速消失**——在约**一个波长**的距离外已可忽略（Slide 4）。这就是后面多层屈曲里"影响区（zone of influence）"概念的来源。讲义配的 Ross of Mull 照片就是证据：便士硬币下方那层里的褶皱，在照片底部的脉体里完全看不到。
- 屈曲形成的折叠层近似 **Class 1B 褶皱（平行褶皱 parallel fold）**——正交层厚绕褶皱不变。

**为什么黏度比值得费劲去测？** notes pane 说：如果我们知道岩层的成分，黏度比就能反推**变形条件**（温度、变形速率）。目前理论还不足以给出可靠的定量估计，但定性洞察是可行的（引用 Sherwin & Chapple 1968 对板岩/千枚岩中石英脉的经典研究）。

### 2.4 例外：被折叠的 pinch-and-swell（Slide 7）

若层本身已经存在**颈缩–膨大（pinch-and-swell）**结构，那么变形集中在薄的部位，**控制褶皱波长的是这些薄处的间距，而不是层厚**。

- **注意**：boudinaged（已经断成布丁状）的层，其褶皱波长**不**受布丁宽度控制。（pinch-and-swell 与 boudinage 的区别在此有实际后果。）
- **构造意义**：这种几何允许你论证**两期变形**：(1) 先平行层伸展，(2) 后褶皱。讲义提醒（Slide 7 注释 + Class 3 预告）：这两阶段未必是完全独立的事件，也可能是**同一次渐进变形（progressive deformation）的早、晚阶段**。
- **识别标志**：褶皱的**一翼明显比另一翼厚**（Kinlochleven 石英岩照片）。实验还显示，较厚的"膨大部（swells）"总是朝同一方向旋转，堆叠起来表面上像叠瓦构造（imbrication）。

### 2.5 多层屈曲（multilayer buckling）

自然界绝大多数褶皱发生在多层体（如沉积序列）中，因此必须考虑**层与层之间的相互影响**。按能干层间距由近到远：

| 情形 | 条件 | 结果 |
|---|---|---|
| **有效单层 effective single layer** | 能干层彼此**很近** | 集体表现为一个厚单层 → **长波长**褶皱 |
| **谐和褶皱 harmonic folding** | 能干层稍远，且层厚与间距变化不大 | 单层公式改为含 N（能干层数）的形式（见第三节） |
| **多谐褶皱 polyharmonic folding** | 能干层的**厚度和/或黏度比差异显著** | 出现**多个波长**，但整个层组仍服从某一**控制层（controlling layer）**的褶皱几何 |
| **不谐褶皱 disharmonic folding** | 能干层间距**大于彼此的影响区（约一个波长）** | 各层**独立**折叠 |
| **肠状褶皱 ptygmatic folding** | 不能干层**远厚于**能干层 → 不能干层控制大尺度变形 | 薄能干层的"波长/层厚"关系相当规则，但**轴面方位变化极大**；这是不谐褶皱的一种特例，翼部常常向自身卷回 |

### 2.6 调节构造（accommodation structures，Slide 11–12）

关键力学事实：**抗屈曲能力正比于层厚的三次方（t³）**。因此**异常厚的层控制整个多层体的屈曲响应**——多层体的波长由厚层决定，其余各层被迫调整形状去迁就它。

那些因为厚度/黏度特征而**过早开始折叠**、结果翼部长度对最终褶皱形态而言"太长或太短"的层，在控制层开始屈曲时就必须调整。为此形成的构造统称**调节构造**：

- **龙骨状铰（keel-like hinge）/ 铰部坍塌（hinge collapse）**
- **铰部逆冲越顶（hinge thrust over）**
- **铰部逆断层（reverse faulting in the hinge）**
- **翼部布丁化（boudinaged limb）**

> notes pane 有一个容易被漏掉但很典型的**反向情形**：Warren Beach（北德文 Hartland Quay）的照片里，是**厚层的形状被一叠薄层控制**（而非通常的"薄层迁就厚层"）。这发生在**尖棱褶皱（chevron fold）**形成时——因为在尖棱褶皱中，给定缩短量下的**翼部倾角依赖于层厚**。

### 2.7 各向异性岩石的屈曲（Slide 13–18）

第二条建模路线：不把多层体拆成一层层单独处理，而是把它当作**统计上均一、但力学各向异性**的连续介质。

- 这里的"各向异性"指：**抗剪切的能力与抗压缩的能力不同**。
- 典型的各向异性岩石：**薄层互层的多层体**，或具强烈**穿透性组构（penetrative fabric）**的岩石，如板岩中的**劈理**。
- 建模方法：寻找那个"打断均匀缩短、使层理变得非平面"的**不稳定性出现条件**。

**只有这种建模路线才能解释的几何特征**（Slide 14）：

1. **翼部非常平直**的褶皱
2. **轴面与原始层理斜交**的褶皱——**即使主压缩方向就沿着层理**
3. **膝折带（kink bands）**

**膝折带的描述（Slide 15）**：膝折带及类膝折几何的褶皱具有 **Class 2（相似褶皱 similar fold）几何**，但因为铰部是**角状（angular）**的，**等倾线方法（dip isogon）用不了**。取而代之，必须直接标注一组角度与尺寸参数（见第三节图件描述）。用这些角度与方位可以反推**缩短量、体积变化**以及**造成它们的应力方位**。

**各向异性度与加载角的联合控制（Slide 16）**：所得构造的几何同时取决于**各向异性程度**和**多层体相对层理被压缩的角度**。一个反直觉但重要的结论：

> **布丁化（boudinage）与伸展型膝折带（extensional kink bands）可以由"垂直层面的压缩"产生——它们并非只能由主动的平行层伸展造成。**

讲义预先解释了表观矛盾：屈曲定义为"沿面内的压应力"，而这里说"垂直层理加载"。二者不冲突——**因为假设了每个方块在竖直方向不能膨胀**；垂直层理压缩时岩层试图沿层理伸展，若不允许伸展，就等价于沿层内产生了压应力。野外例证：Tintagel 的布丁化（竖直方向压缩产生）、Marloes Sands 的波状褶皱（竖直方向压缩产生）。

**膝折带的构造学价值（Slide 18）**：膝折带是**非常常见的造山晚期构造**，形成于各向异性岩石经受最终调整时。这类膝折带被戏称为 **"fag-end"（烟屁股）构造**——因为它们对主变形事件几乎不提供信息。**但是**，更大尺度的类膝折几何褶皱（如 Bude 的箱状褶皱 box fold）说明这种褶皱样式**可以有超出 "fag-end" 的构造意义**。

### 2.8 屈曲褶皱的一生（Slide 19–22）

平行层压缩下屈曲褶皱的发育分 **4 个阶段**（讲义随后又说，把 2、3 合并成 3 阶段其实更合理）：

| 阶段 | 名称 | 内容 |
|---|---|---|
| 1 | **前屈曲缩短 pre-buckle shortening** | 折叠开始前，层先均匀缩短并加厚；缩短量取决于变形条件与黏度比。**也可能不是均匀缩短，而是靠逆冲实现翼部加厚**（Northcott Mouth、Rhoscolyn 的小逆冲/双重构造 duplex） |
| 2 | **成核 fold initiation** | 某个不规则性（如层厚的局部变化）触发折叠。若能干层足够远，各层独立起褶，直到某厚控制层开始屈曲、迫使其余层调整形状（→ 形成调节构造）；若无控制层，则多层体作为整体屈曲 |
| 3 | **放大与锁死 amplification → locking up** | 褶皱长大时层相对压缩方向旋转，最终变成**不利于继续屈曲的方位** → 褶皱"锁死" |
| 4 | **后屈曲压扁 post-buckle flattening** | 继续缩短导致褶皱**被动**生长：振幅增大、翼间角减小，整个"基质+层"包体一起加厚 |

**主动屈曲只发生在阶段 2、3；阶段 4 的褶皱是被动生长的。**

**锁死可以提前发生**（Slide 21 注释）：如果变形过程中岩石变强（应变硬化），或者某种有利于变形的因素（如孔隙流体）被移除，褶皱会过早锁死。这提示——**必须知道岩石内部到底靠什么过程来实现变形**。

**后屈曲压扁对等倾线分类的改造（Slide 22）** —— 这是把 Class 1 的分类真正用起来的地方：

- 后屈曲压扁把褶皱从 **Class 1B → Class 1C**；等倾线分析可以**定量评估压扁量**。
- 一个折叠的多层体可能是：能干层 **Class 1B** + 不能干夹层 **Class 3**；继续缩短时，不能干层保持 Class 3，而能干层变成 **Class 1C**。
- **平行轴面方向**的压缩，把原本屈曲形成的 **Class 1B → Class 1A**。（这类压扁常出现在收缩变形幕的晚期，当岩体被逆冲到早先褶皱之上时；Class 8 会展开。）

### 2.9 弯曲（bending，Slide 23）

弯曲褶皱是**响应相邻岩体变形而在几何上必然出现的褶皱**。清单：

- **颈褶皱 neck folds**：布丁之间
- **断弯褶皱 fault-bend folds**：上盘岩体越过倾角变化的断层（如逆冲坡道 thrust ramp）时被弯曲
- **披覆褶皱 drape folds**：沉积盖层响应下伏基底断裂
- **强力侵入体/底辟周围的褶皱**
- **差异压实形成的褶皱**

这些褶皱的几何取决于**被折叠单元的力学性质**和**强迫方式的性质**。共同点：**非均匀的力横跨层理施加，而非沿层理施加**。

### 2.10 被动褶皱（passive folding，Slide 24）

- 定义：折叠层只是一条**标志带（marker band）**，单纯记录它所在岩体的变形。
- 典型产出：**岩层进入剪切带**处。
- 若原始层是平行边的，被动褶皱产生 **Class 2 相似褶皱**。
- **关键判据**：当层与围岩的**力学性质差异很小**时，被动褶皱的放大最显著 → **被动褶皱在高变质级岩石中更突出**。（对比屈曲：屈曲要求大的能干性差异。二者对能干性差异的要求正好相反，是最好的区分线索。）
- 野外形态：铰部加厚、翼部极度减薄；瑞典拉普兰的角闪片麻岩中的被动褶皱"看起来像水池表面浮沫的花纹"。

### 2.11 三种褶皱机制（Slide 25–30）

#### (a) 弯滑 / 弯流（flexural slip / flexural flow）

- **类比**：把一叠纸沿纸面方向压缩——各张纸彼此**滑动**。
- **滑动量分布**：**拐点（inflection point）处最大，向铰部递减，铰部为零**。
- **层面内无畸变（no distortion within the plane of the layering）** —— 这是最关键的性质。推论：**躺在滑动面内的化石和其他物体保持不变形**（其他机制做不到这一点）。
- **滑动面**：通常是层面（bedding），或某种穿透性组构如劈理。
- **弯流 vs. 弯滑**：滑动面**很密**、层平行剪切均匀分布在整个折叠层内 = **弯流**；滑动面**间距较大**（如互层序列中沿层面滑动）= **弯滑**。
- **次生特征（secondary features）**：
  1. 滑动面上的**线理**（沟槽，更常见的是**晶体纤维**），方位与铰**高角度相交**；讲义称之为 slickolites（见第八节勘误表）。
  2. **雁列张裂脉（en échelon tension gashes）**，指示滑动方向。一翼指一个方向、另一翼指相反方向，与弯滑褶皱两翼相反的剪切指向一致（背形铰左侧翼为右行，右侧翼为左行）。其 S 形（sigmoidal）形态**离铰越远越明显**，说明向拐点方向滑动位移增大。
- **对先存线理的影响（Slide 27）**：由于滑动面内无畸变，**层面上与未来褶皱轴成 α 角的先存线理，折叠后仍与褶皱轴成 α 角**。→ **在赤平投影上，线理被摊布在绕褶皱轴的一个小圆（small circle）上。** 这是判定弯流机制的赤平投影签名。

#### (b) 切向纵向应变（tangential longitudinal strain, TLS）

- **类比**：沿长度方向压缩一块橡皮擦——**外弧（outer arc）受拉伸，内弧（inner arc）受压缩**，二者之间是变形相互抵消的**中和面（neutral surface）**。
- **变形量分布**：**铰部最大，向拐点递减，拐点处为零**。（**注意与弯滑正好相反！**）
- **次生特征**：
  - **外弧**：**张裂隙（extension fractures）**，常被脉体充填（Aberystwyth Grits 背形铰部照片）。
  - **内弧**：**劈理加强**，或**共轭逆冲（conjugate thrusts）**。
- **对先存线理的影响（Slide 29）**：比弯流复杂——赤平投影上线理被摊布在**一个扇形区（sector）内**，具体落在扇形内哪个位置取决于它在折叠层中的**位置**（相对中和面的深度）。

#### (c) 剪切褶皱（shear folding）

- **类比**：剪切一副扑克牌——**剪切面平行于褶皱的轴面**。
- 产生 **Class 2 褶皱**。
- **重要限定**：讲义明说剪切褶皱**并不被认为是一种真实的褶皱机制**，但它是分析 Class 2 褶皱时**极为有用的近似**。
- **对先存线理的影响**：线理在**一个平面内**被重新定向 → 赤平投影上线理被摊布在一条**大圆（great circle）**上。**这条大圆与剪切面（轴面）的交点就是构造 a 方向（tectonic a-direction）**；如果褶皱是断层剪切造成的，**这个方向就是断层滑移矢量（fault slip vector）**。
- notes pane 特别强调：剪切褶皱通常是断层带（剪切带）中褶皱的最佳近似，其轴面平行断层面/剪切带边界。**测量线理进入断层带时的倾伏/倾伏向，找出包含这些线理的大圆与断层面大圆的交点，就能定出断层滑移矢量**——"这是一项非常有用的技术，将是我们多次实习课的重点。任何在含重要断层地区做地质填图的人，都应当对这项技术非常熟悉。" → **本周 Practical 的 `SolnGneissFault` 就是这项技术的第一次实战。**

### 2.12 非圆柱状褶皱（Slide 31–34）

Class 1 与 Class 2 的讨论大多以**圆柱状褶皱**为框架（沿褶皱轴不同位置、相同方位的剖面形状一致），但真实褶皱一般是非圆柱状的。所有术语仍然适用，但有几种特例值得单列：

- **穹丘（periclines）与分叉铰（bifurcating hinges）**：褶皱不会绕地球一圈——它沿褶皱轴**生长并消亡**，或者铰线**分叉**。各种尺度上都会发生，直到造山带尺度。常见的空间排列是**雁列式（en échelon）排列的长条形穹丘**（伊朗扎格罗斯山脉为例）。**间距小于约半个波长的雁列穹丘可能连接（link）；间距大于此值则可能重叠并彼此锁死。** → 结论：**不仅要描述褶皱的剖面几何，还要描述它们的平面分布。**
- **鞘褶皱（sheath folds）**：铰线在轴面内弯曲**超过 90°** 的褶皱。常伴随强烈的**拉伸线理（stretching lineation）**。成因：层平行剪切作用下某个初始不规则性的**被动放大**。是剪切带的特征构造（Class 4 展开）。极端情形呈管状。
  - 相关辨析（notes pane）：鞘褶皱 = **弯曲铰线 + 近平面轴面**；**多斜褶皱（polyclinal folds）** = **平直铰线 + 弯曲轴面**；软沉积褶皱常常两者都弯。
- **软沉积褶皱（soft sedimentary folds）**：未固结、水饱和的沉积物很弱，能响应驱动力方向的微小改变（例如遇到运动障碍），因而通常产生**高度非圆柱状**的褶皱。例：滑塌卷曲褶皱（convolute slump folds）、冰川沉积中的冰拖曳褶皱（ice drag folds）。**其几何复杂到通常做完整几何描述已无意义。**

### 2.13 叠加褶皱与干涉型式（Slide 35–41）

**再褶皱褶皱（refolded folds）**：由两期（或更多期）变形产生的褶皱**都是非圆柱状的**，唯一例外是两期折叠**共轴且共面（coaxial and coplanar）**的特殊情况。

> **关键方法论（notes pane）**：再褶皱褶皱的几何可以借助**每期折叠事件所伴随的协调小构造**来解开——因为**第二期折叠虽然会改变第一期褶皱的几何，却无法改变第一期小构造的不对称性**。（这条直接接续 Class 1 的 S/Z 不对称与倒向 vergence。）

**符号约定**：F1、F2 = 第一、第二期变形形成的褶皱；S1、S2 = F1、F2 褶皱的轴面；S0 = 层理；D1、D2 = 变形幕；L1、L2 = 线理。

**四种基本干涉型式**（按两期褶皱的**轴**与**轴面**的相对方位分类）：

| 型式 | 两期褶皱轴 | 两期轴面 / 姿态 | 平面露头图案 |
|---|---|---|---|
| **Type 0** | 共轴 | 共面 | 第二期只是**强化**第一期构造，不产生新图案 |
| **Type 1** | **互成 90°** | **两者都直立，轴面互成 90°** | **穹–盆（dome and basin）**，即"蛋盒"图案 |
| **Type 2** | **互成 90°** | **一组平卧（recumbent）、一组直立（upright）** | **新月形 / 蘑菇形（crescent / mushroom）** |
| **Type 3** | **近似共轴** | **一组平卧、一组直立** | **波状（wavy）**图案；讲义命名为 convergent–divergent |

**Type 3 的重要警告（Slide 39 notes）**：Type 3 中 F1 与 F2 轴向近乎相同（这就是共轴的含义），但两组轴面 S1、S2 差异极大，结果是**近平直的 F1 铰 + 弯曲的 S1**——这就是一个**多斜褶皱（polyclinal fold）**。而**多斜褶皱其实可以在单次变形事件中形成**，也就是说：

> **看到 Type 3 干涉型式，并不自动意味着经历了两期褶皱事件。**

**现实世界（Slide 41）**：上述四种型式是在"每期褶皱都是圆柱状"的前提下定义的。如果一期或两期褶皱本身是非圆柱状的，干涉型式会复杂得多。（学生九月野外填图区 Aliaga（北西班牙）就是大尺度再褶皱褶皱的绝佳实例。）

📎 **背景补充（寄生褶皱 / parasitic folds）**：本周讲义并未专门讨论寄生褶皱的形成机制——它属于 Class 1 的"协调小构造（congruent minor structures）"内容。把两周合起来理解：寄生褶皱是大褶皱翼部因**弯滑机制下的层平行剪切**而在薄弱层中形成的小褶皱，其**不对称性（S/Z）随所在翼而系统改变**，因而可用于定位主褶皱的铰。本周讲义提供的力学基础是 Slide 8–11 的多层屈曲：当薄能干层被厚控制层的褶皱形态约束时，薄层必须以更短的波长起褶——这正是寄生褶皱在多层力学上的来源。**这一段的力学联系是我做的整合，讲义未如此表述。**

📎 **背景补充（劈理与褶皱的关系）**：任务要求覆盖轴面劈理、劈理扇与劈理折射，但**Class 2 讲义完全没有讲劈理**——这些内容在 **Class 1（Week 1）讲义 Slide 30–33** 中。为本周 Practical 服务，把 Class 1 的三条结论摘录于此（**以下三条是 Class 1 讲义原文内容，不是我编的，但确实不属于本周材料**）：
> - **轴面劈理（axial planar cleavage）**：劈理/片理一般平行或近平行于褶皱轴面。它对确定轴面方位无价可替代，并且通过**劈理/层理交线（cleavage/bedding intersection）**还能定出褶皱轴方位。
> - **劈理扇（cleavage fanning）**：除铰部外，劈理常常并非精确平行轴面，而是绕褶皱呈**收敛（convergent）**或**发散（divergent）**方式呈扇形展布。（另有一种情况：在**转换压缩（transpression）**背景下，劈理可系统斜交轴面，称 **transecting cleavage**，是北威尔士板岩带的特征。）
> - **劈理折射（cleavage refraction）**：劈理穿过岩性界面时常**改变倾角但不改变走向**。这反映各层**抗流动能力（能干性）**的差异。规律是：**在更能干的岩性中（典型地，黏土含量更低者），劈理与层理的夹角更大**；在不能干层中劈理更趋近平行层理。谨慎使用时，折射劈理可作为**粒序层理（graded bedding）的顶底判据**——随正粒序层顶部黏土矿物含量升高，劈理越来越接近平行层理。

---

## 三、公式与图表

> **本节是本周笔记的重心。** 本课的 Theory 考试是"图解式、简答题"（syllabus 原文：diagrammatic, short answer questions），因此**能不能默画这些图、能不能解释公式每一项**，直接决定分数。

### 3.1 单层屈曲的主波长公式

$$\lambda = 2\pi d \left[\frac{\eta_L}{6\,\eta_M}\right]^{1/3}$$

**逐项解释**：

| 符号 | 含义 | 单位 |
|---|---|---|
| **λ** | 放大最快的扰动波长 = 褶皱的**主波长（dominant wavelength）** | 长度 |
| **d** | **能干层的层厚**（layer thickness） | 长度 |
| **η_L** | **层（layer）**的黏度 | Pa·s |
| **η_M** | **基质/围岩（matrix）**的黏度 | Pa·s |
| **6** | 无量纲常数，来自理论推导 | — |
| **1/3** | 指数——**注意是黏度比的立方根**，不是平方根、不是一次方 | — |

**读法与推论**：

1. **λ ∝ d（线性）** —— 层厚翻倍，波长翻倍。野外可直接检验：薄层短波长、厚层长波长。
2. **λ ∝ (η_L/η_M)^(1/3)** —— **黏度比进入的是立方根，因此波长对黏度比不敏感**：黏度比要变化 8 倍，波长才变化 2 倍。**这正是"从 λ 和 d 反推黏度比"在实践中难以做到定量精确的原因**（讲义说需要进一步研究才能给出可靠定量估计）。
3. **η_L 必须大于 η_M**（否则不满足屈曲的先决条件）。**方向不能记反**：分子是**层**的黏度，分母是**基质**的黏度。
4. **λ/d = 2π(η_L/6η_M)^(1/3)** —— 实际操作时测量的是**波长与层厚之比**，因为这个比值直接给出黏度比：
   $$\frac{\eta_L}{\eta_M} = 6\left(\frac{\lambda}{2\pi d}\right)^3$$
   📎 **背景补充**：这一步反解是我做的代数变形，讲义只给出正向公式并说"这类方程最有用的解释之一是有可能从实测的 λ 和 d 反推出层/基质黏度比"。反解本身是直接的。

**适用条件（讲义 Slide 4 notes 明列的简化假设）**：

- (a) 层与基质均为**牛顿黏性（Newtonian viscous）**；
- (b) 层的**自重无影响**；
- (c) **不存在未被屈曲吸收的平行层缩短**（即层在缩短过程中**不加厚**）；
- (d) 分析是**剖面平面（profile plane）内的二维分析**——没有物质进出该平面。

更复杂的模型可以放松这些假设。

### 3.2 多层（谐和褶皱）的修正公式

$$\lambda = 2\pi d \left[\frac{N\,\eta_L}{6\,\eta_M}\right]^{1/3}$$

- **N = 层组中能干层的数目**。
- 推论：**N 层能干层的谐和褶皱，波长是单层情形的 N^(1/3) 倍**。8 层能干层 → 波长翻倍。
- 适用条件：能干层**稍微分开**，且**层厚与间距变化不大**。若太近 → 有效单层（更长波长）；若太远（超过约一个波长的影响区）→ 不谐褶皱（各自独立）。

### 3.3 抗屈曲能力与层厚

$$\text{resistance to buckling} \propto t^3$$

层厚**三次方**律。这是"厚层控制整个多层体"的根源——层厚只要翻倍，抗屈曲能力就是 8 倍。**记住指数是 3，不是 2。**

### 3.4 Practical 用到的伸展应变公式（`Cover.md` 第 5 题）

$$e = \frac{\Delta L}{L_0}$$

- **ΔL** = 沿**平行岩墙张开方向**画的一条测线上，**岩墙的总厚度**。
- **L₀** = 该测线**总长度减去 ΔL**，即**岩墙侵位前测线的原始长度**。
- ⚠️ 分母是 **L₀（原始长度）而不是现今长度**——这是**工程应变（engineering strain）/伸长率（extension）**的定义。若误用现今长度作分母会低估应变（那是"stretch" 的另一种表达）。

### 3.5 必须能默画的图（文字描述到可自行复原的程度）

#### 图 A｜三种褶皱机制的应变标志对比图

在同一张图上画**三个并排的对称背形**，每个背形内画一排**应变椭圆（strain ellipse）**（表示初始圆形物体变形后的形状）：

- **弯滑/弯流（左）**：
  - 在**折叠层内部**画一排相同形状的椭圆，长轴平行层理方向且**在两翼方向相反倾斜**（一翼右行、一翼左行剪切），**铰部椭圆退化为圆**（无应变）。
  - 层界面上画**箭头对**表示相邻层相对滑动，**箭头最长在拐点、铰部箭头长度为零**。
  - 在两翼层面上画**雁列张裂脉**：左翼一组、右翼一组，**S 形弯曲方向相反**，且**离铰越远 S 形越强**。
  - 在层面上画一组**高角度斜交铰**的线理（纤维/沟槽）。
  - **旁注**："layer 内无畸变 → 化石不变形"。

- **切向纵向应变 TLS（中）**：
  - 在折叠层内画**一条虚线**从一翼贯穿铰部到另一翼，标注 **neutral surface（中和面）**。
  - **中和面以外（外弧）**的椭圆：长轴**平行层面**（拉伸）；**中和面以内（内弧）**的椭圆：长轴**垂直层面**（层面方向被压缩）。
  - **铰部椭圆最扁（应变最大）；向两侧拐点方向椭圆逐渐趋近圆（应变为零）**。
  - **外弧铰部**画一组**放射状张裂隙**（常被脉体充填）；**内弧铰部**画**加密的劈理**或一对**共轭逆冲**。
  - **旁注**："最大变形在铰部——与弯滑正好相反"。

- **剪切褶皱（右）**：
  - 画一叠**平行轴面的直线**（"扑克牌"），标注 **shear planes ∥ axial surface**。
  - 折叠层在两翼被**极度减薄**、在铰部**加厚**，构成 **Class 2 相似褶皱**。
  - **旁注**："不被认为是真实机制，但是分析 Class 2 褶皱的极好近似"。

#### 图 B｜中和面与褶皱内应变分布示意

画一个单独的**加厚背形铰部**（大比例），层的上下界面为两条同心弧：

- 从铰部到拐点画约 7 组椭圆，排成上、中、下三行。
- **上行（外弧）**：椭圆长轴沿弧向（切向），铰部最扁、拐点处为圆。
- **中行**：全部为圆 → 用一条虚线连成 **neutral surface**。
- **下行（内弧）**：椭圆长轴**径向**（即层面方向被缩短），铰部最扁、拐点处为圆。
- 在外弧顶部画数条**径向张裂隙**（外弧拉张），在内弧底部画**共轭逆冲对**或**密集劈理**（内弧压缩）。
- 标注箭头：**tension（外弧）↔ compression（内弧）**。

> ⚠️ 中和面**不是几何中面**。它的位置随褶皱发育而**向内弧迁移**（📎 **背景补充**：这一点讲义未提，属于常见的进阶知识；讲义只说"between them is the neutral surface where the deformation cancels out"）。考试若问"中和面在哪儿"，**按讲义答"外弧拉张区与内弧压缩区之间、变形相互抵消的那个面"最安全**。

#### 图 C｜三种机制在赤平投影上的"线理签名"（本课最实用的一张图）

画三个并排的**赤平投影网（等面积网 / Wulff 网均可）**，每个网上标出**褶皱轴（fold axis）**为一个点：

1. **弯流/弯滑**：先存线理落在**以褶皱轴为极点的一个小圆（small circle）上**——因为线理与褶皱轴的夹角 α 在折叠过程中保持不变。**画法**：以褶皱轴为中心，画一个半径为 α 的小圆，线理点沿此小圆分布。（若发生后屈曲压扁，分布会偏离理想小圆——讲义 Slide 27 的图右下角就是这种情况。）
2. **TLS**：线理**分布在一个扇形区（sector）内**，落在扇形内的具体位置取决于该线理在折叠层中的位置（外弧/中和面/内弧）。**画法**：画一个楔形的阴影区，不是一条线。
3. **剪切褶皱**：线理落在**一条大圆（great circle）上**。**再画上剪切面（= 轴面）的大圆**；两条大圆的**交点**标注为 **tectonic a-direction = fault slip vector**。

> **这张图就是 Practical 里从线理反推断层滑移矢量的理论依据。**

#### 图 D｜叠加褶皱四种干涉型式的平面图案与成因

统一画法：每格画一个**平面露头图（map view）**，用**闭合的、同心的岩层界线**表达，并在旁边画一个**小立体块图**标出 F1 轴、S1、F2 轴、S2 的相对方位。

| 型式 | 立体块图上的方位 | 平面图案画法 |
|---|---|---|
| **Type 0** | F1 ∥ F2（共轴），S1 ∥ S2（共面） | 简单的平行条带，与单期褶皱无异；**只是振幅更大、翼间角更小** |
| **Type 1** | F1 ⊥ F2；**S1、S2 均直立**且互成 90° | **蛋盒图案**：一系列**卵圆形闭合等值线**，中心交替为**穹（dome，向外变新）与盆（basin，向内变新）**，沿两个正交方向规则排列 |
| **Type 2** | F1 ⊥ F2；**一组平卧、一组直立** | **新月形 / 蘑菇形**：闭合线呈月牙状，成对组合像蘑菇的伞盖；不对称，明显区别于 Type 1 的规则蛋盒 |
| **Type 3** | F1 ∥ F2（近共轴）；**一组平卧、一组直立**（S1 与 S2 差异极大） | **波状条带**：条带整体平行延伸但反复起伏（"convergent–divergent"）；**平直的 F1 铰 + 弯曲的 S1** = 多斜褶皱 |

**记忆抓手**：

- **轴的关系决定"图案有没有闭合圈"**：轴正交（Type 1、2）→ 闭合的穹/盆/新月；轴共轴（Type 0、3）→ 条带状不闭合。
- **轴面的关系决定"图案对称不对称"**：都直立（Type 1）→ 规则对称的蛋盒；一平卧一直立（Type 2、3）→ 不对称的新月/波状。

📎 **背景补充**：讲义未把上述"两条记忆抓手"写成规则，这是我从 Slide 36–39 的四组条件归纳的；条件本身（轴正交/共轴、平卧/直立）全部来自讲义原文。讲义还提示 UCD 断层分析组提供了纸模型可帮助建立空间想象（"Educational Material" → "Superposed Folds"）。

#### 图 E｜膝折带的参数标注图

画一段**水平层理**的多层体，中间被一条带状区域切过：

- 带的两条边界称 **kink band boundaries**，标注它们与层理的夹角。
- 带内层理被**旋转**，与带外层理成一个角度；标注**带内层理与带界面的夹角 α₁**、**带外层理与带界面的夹角 α₂**、**带宽 w**。
- 标注**运动学类型**：**contractional（收缩型，缩短平行层理）**与 **extensional（伸展型）**；**dextral（右行）/ sinistral（左行）** 按带内旋转的指向。讲义照片用的是 **"contractional dextral"**。
- 一对**共轭收缩型膝折带**组合成一个**箱状褶皱（box fold）**。
- **旁注**："Class 2 相似褶皱几何，但铰角状 → 等倾线方法不可用，必须直接标注角度与尺寸"。

#### 图 F｜屈曲褶皱一生的四阶段图

画横轴为 **% shortening（缩短量）**、纵轴为 **fold amplitude ÷ competent layer thickness（振幅/层厚）** 的曲线图：

- 曲线呈 **S 形**：阶段 1（前屈曲缩短）几乎水平；阶段 2–3（主动屈曲）陡升；阶段 4（后屈曲压扁）斜率变缓但仍上升。
- **画多条曲线，标注不同的 η_L/η_M**：**黏度比越大，曲线越陡（同一缩短量下振幅越大）**，且**层加厚越少**。
- 在曲线旁配四个小的褶皱形态草图：加厚的平层 → 起伏的低幅波 → 明显褶皱 → 高幅紧闭褶皱 + 基质整体加厚。

#### 图 G｜等倾线分类回顾图（Class 1 内容，本周反复使用）

画五个褶皱剖面，每个上面画一组**等倾线（dip isogon）**——连接折叠层上下界面上**倾角相等**的点的连线：

| 类别 | 等倾线 | 特征 |
|---|---|---|
| **1A** | 强烈**收敛**（向内弧汇聚） | 铰部相对翼部**减薄** |
| **1B** | 与层**正交**、平行排列 | **平行褶皱**：正交层厚 t_α 绕褶皱不变 |
| **1C** | 轻微收敛 | 1B 被压扁后的产物 |
| **2** | 与轴面**平行** | **相似褶皱**：平行轴面的层厚 T_α 不变 |
| **3** | **发散** | 铰部相对翼部**加厚**，典型的不能干夹层 |

**本周的用法路径**：
`屈曲 → 1B` ；`1B + 垂直轴面继续压扁 → 1C` ；`1B + 平行轴面压缩 → 1A` ；`被动/剪切褶皱 → 2` ；`不能干夹层 → 3`。

---

## 四、课堂补充

> **⚠️ 说明：本课程全 10 周均无 transcript（无课堂录音/口头讲解转写）。** 因此本节不包含任何课堂口头内容，全部改写自**讲义 notes pane 中强调的注意事项**与**练习答案透露的评分要点与作图规范**。

### 4.1 讲义作者反复强调的"元信息"

1. **本课讲义的定位是"参考书"而非"考纲"。** 课程大纲原文：Theory 内容"densely packed"，PPT 的 notes pane 中含大量补充与延伸阅读，**目的是让你在未来的学习中把它当参考资料用**——"这是学科的路线图，不同学生会关注不同方面"。**但考试只考每讲中被明确标为 key material 的部分**（每周 Blackboard 上会另发一份文档，指出本周关键材料及可能的考法）。**结论：notes pane 中的文献引用、野外地点、研究前沿不是考点；正文 bullet 才是。**
2. **屈曲理论的数学推导超出本课范围。** Slide 3 notes 明说："The theory of buckling is beyond the remit of this course – we shall confine ourselves to some of the features that the theory/laboratory experiments/numerical models attempt to explain." → **不会考推导，会考公式的定性使用与图解。**
3. **关于线理与断层滑移矢量的技术，讲义罕见地用了"必须掌握"的口吻**（Slide 30 notes）："This is a very helpful technique and will be a major focus of the exercises in more than one of our practical classes. Anyone undertaking geological mapping in an area containing significant faults, ought to become very familiar with this technique." → **这是本周唯一被作者点名"必须非常熟悉"的技能。**
4. **两阶段还是四阶段？** Slide 19 notes 主动纠正了自己的幻灯片："It is perhaps more sensible to split the development of buckle folds into three stages rather than four by merging Stages 2 and 3" → **答题时写三阶段（前屈曲缩短 / 主动屈曲 / 后屈曲压扁）更稳妥，并注明"成核与放大可合并"。**
5. **"Type 3 不等于两期变形"是作者主动加的警告**（Slide 39 notes，并引 Carreras & Druguet 2019）。**这类"看似必然、实则不必然"的推论，正是简答题最爱设的坑。**
6. **可视化困难是被承认的。** Slide 36 正文直接写："Visualization requires considerable mental dexterity"，并推荐 UCD 的纸模型。→ **复习时真的应该用纸折一遍，而不是死记图案。**

### 4.2 练习答案透露的评分要点与作图规范

从 `Ex5-1.md`（旧考卷）与 `Ex5soln.md`、`SolnFold.md`、`SolnGneissFault.md` 的答案版式，可以反推出这门课**赤平投影题的标准答卷格式**：

**（1）赤平投影图必须包含的元素**（三份 Soln 完全一致）：
- **数据层**：极点符号必须**按类型区分**并在图例中说明（poles to bedding / poles to cleavage / minor fold axes / poles to mylonitic foliation / mineral elongation lineation / boudin necks …）。
- **解释层**：另用一套符号标出推导结果（fold axis / poles to representative limbs / pole to axial plane / pole to bisector）。**数据与解释必须视觉可分**。
- **北向标记 N** 与**所有推出的面/线的方位读数**（如 `040/30SE`、`10/057`）。
- **注记（annotation）**：`Cover.md` 明确要求"Make sure that this stereogram is fully annotated with explanatory comments." → **图上写字是给分点**。

**（2）圆柱状褶皱几何的四要素（Class 1 已定，本周仍用）必须齐全**：
① 褶皱轴（倾伏/倾伏向）；② 轴面（走向/倾角）；③ 两翼代表性方位；④ 翼间角。**外加平分面（bisector）方位。**

**（3）"简化剖面平面剖面图（simplified profile plane section）"的作图规范**：
- 剖面平面必须**垂直于褶皱轴**，其方位在图上写明（如 `147/80SW`、`035/65NW`）。
- 视图方向必须是**沿倾伏向下看（looking down-plunge）**，并在剖面两端标注方向（如 `NW–SE`、`NE–SW`）。
- 剖面上各条线的角度**不是真倾角，而是在剖面平面内量得的视倾角**——由该面的大圆与剖面平面大圆的交点，在剖面平面大圆上量到其走向线的角度。
- **必须标注**：两翼视倾角、轴面视倾角、平分面视倾角、翼间角。

**（4）平分面 vs. 轴面的差值是隐藏给分点。** 在 `Ex5soln` 中，轴面在剖面内的视倾角 **56°**、平分面 **43°**，相差 **13°** —— 这个差值意味着**两翼层厚不同**（若两翼层厚相同，平分面 = 轴面）。Week 1 的 `Ex1c-SolnSeq` 里作者就明确把这句话写进了答案文本："The bisector … has an apparent dip in the profile plane which is 13° less than that of the axial surface, indicating that the middle limb of the fold pair is thinner compared with the other limbs." → **只要 bisector ≠ axial plane，就要写一句解释。**

**（5）证据链式写作是本课的书面表达规范。** `Cover.md` 给出了完整的"以证据为基础的构造演化史"章节结构（见第五节），并且 `SolnMap.md` 上的每一条手写注记都是"**观察 → 因此 → 推论**"的句式（"dykes crosscut folds **and so are** later"）。**这是本课练习考试短答题的评分骨架。**

---

## 五、Practical 要点

### 5.0 本周实习总览

课程大纲对第 2 周实习的描述："Map-based consolidation session on analysing and illustrating the geometry of folds using the stereonet; folded lineations; introduction to compiling an evidence-based structural history."

本周实习包 = **一个主图幅练习（Tarskavaig Bay）+ 一道额外练习（Ex5，旧考卷）**：

| 文件 | 性质 | 作用 |
|---|---|---|
| `Cover.md` | 题面（5 问 + 写作大纲） | **本周实习的核心文档** |
| `SolnMap.md` | 完成图 + 手写注记 | 观察 → 推论的证据链 |
| `SolnFold.md` | 变质沉积岩中褶皱的赤平投影 + 剖面 | 第 2 问答案 |
| `SolnGneissFault.md` | 片麻岩内构造与断层的赤平投影 + 应变椭球 | 第 3 问答案 |
| `Ex5-1.md` | 额外练习题面（2017 年旧考卷，1 小时，代码 EART20292） | 独立的褶皱赤平投影训练 |
| `Ex5soln.md` | Ex5 答案 | 标准答卷示范 |

📎 **背景补充（地理与地质背景，材料未说明）**：Tarskavaig Bay 位于苏格兰 **Skye 岛 Sleat 半岛**西岸，是**摩因逆冲带（Moine Thrust Belt）**南端的经典地区；图幅中"高级片麻岩逆冲于低级变质沉积岩之上"与"晚期未变形玄武岩墙群"分别对应加里东期逆冲与古近纪 Skye 岩墙群。**这段背景是我补的；本周材料从头到尾没有交代过地点的真实地质归属，且练习图幅很可能是为教学而简化/理想化的，答题时不应引用真实地层名。**

### 5.1 Tarskavaig Bay 图幅：要解决什么问题

`Cover.md` 开宗明义：

> "The aim of this exercise is to describe the structures shown on the accompanying map and deduce the structural evolution of the area."

出题人特意说明：本可以要求写一篇 1–2 页的"以证据为基础的构造演化史"，但改为用 5 个问题**分步引导**，"Questions 1 to 5 take you the first part of this and provide you with all the information needed to deduce the structural evolution."

**图幅上的岩性单元与符号**（据 `SolnMap.md` 图例）：

- **下盘（footwall，西侧）低级变质沉积岩**——由老到新的**地层序列**：`coarse sandstone`（粗砂岩，最老）→ `slates with sandstones`（含砂岩的板岩）→ `fine sandstone`（细砂岩，最新）
- **上盘（hanging wall，东侧）高级变质岩**：`Foliated quartz+feldspar gneiss`（面理化石英+长石片麻岩）、`Mylonitic quartz+feldspar gneiss`（糜棱岩化片麻岩，靠近断层）、`Amphibolite`（角闪岩）
- **切穿一切的**：`Basalt with chilled margin`（具冷凝边的玄武岩墙）
- **符号**：bedding（层理）、cleavage or foliation（劈理或面理）、mineral elongation lineation（矿物拉伸线理）、younging（顶底指向）、long axis of boudins（布丁长轴）
- 比例尺：**0–500 m**

### 5.2 第 1 问：完成图幅、建立地层序列与事件序列

**题目**："Complete the map, taking particular care when establishing the width and number of dykes… What can and cannot be said about the age relationship between the gneisses and the other units on the map?"

**推理链（据 `SolnMap.md` 注记）**：

| 图上看到什么 | 推断什么 |
|---|---|
| 背形核部为**粗砂岩**，加上 younging 符号 → "antiform is an anticline" | **背形同时是背斜**（核部最老）→ 由此定出地层序列：粗砂岩 → 含砂岩板岩 → 细砂岩 |
| 小褶皱与主背形**协调（congruent）** | 小褶皱与主褶皱同期，可用于定位轴迹 |
| **岩墙切穿褶皱** | 岩墙晚于褶皱 |
| **岩墙切穿断层** | 岩墙晚于断层 |
| **岩墙未变形** | 岩墙侵位于变形之后；**岩墙的倾角无法确定** |
| 岩墙中**冷凝边（chilled margin）呈对称排列** | 冷凝边的**数目指示每个复合侵入体中的岩墙条数**；这种排列意味着**每一次岩浆注入都沿着先存岩墙的中心** |
| 片麻岩与变质沉积岩之间**只有断层接触** | ⭐ **无法确定二者的相对年龄**——没有沉积接触、没有侵入接触，只有构造接触 |

⭐ **第 1 问的"cannot be said"就是答案的核心**：图上**唯一**的片麻岩–沉积岩接触是断层，而断层是构造接触，**既不给沉积先后、也不给侵入先后**。可以说的只是：片麻岩变形于**远高于**变质沉积岩变形的温度（"ductile deformation of the amphibolites at much higher temperature than deformation of the metasediments under the fault"），且高级片麻岩被**放置（emplaced）在**低级变质沉积岩之上。

### 5.3 第 2 问：变质沉积岩中褶皱的几何（`SolnFold.md`）

**题目**："Plot the orientation data given for the low grade metasedimentary units west of the fault and fully determine the geometry of the folding there. On the same sheet of paper draw a simplified down-plunge section illustrating the geometry of the folding."

**解法步骤**：
1. 把**层理（bedding）的极点**投到赤平网上 → 它们应落在一条大圆（π 圆）上 → **该大圆的极点 = 褶皱轴**。
2. 把**劈理（cleavage）的极点**也投上去 → 劈理极点聚成一簇 → **该簇的极点所对应的面 = 轴面**（因为劈理是轴面劈理）。
3. 从层理极点在 π 圆上的**两个聚集区**读出**两翼代表性方位**。
4. 由两翼大圆的夹角读出**翼间角**；由两翼极点的中点定出**平分面**。
5. 作**剖面平面** = 垂直于褶皱轴的面。
6. 沿倾伏向下看，把各面在剖面平面内的**视倾角**画成剖面。

**答案（`SolnFold.md`）**：

| 要素 | 结果 |
|---|---|
| 褶皱轴 fold axis | **10/057**（缓倾伏，plunge 10°–30° 区间的下端） |
| 轴面 axial plane | **040/30SE**（中等倾斜 moderately-inclined） |
| 翼 A limb A | **008/13E** |
| 翼 B limb B | **048/49SE** |
| 翼间角 interlimb angle | **40°** → **紧闭（close，70°–30°）** |
| 剖面平面 profile plane | **147/80SW** |
| 平分面 bisector | **= 轴面**（答案写 "pole to axial plane (= bisector)"）→ **两翼层厚相同** |

**剖面图（looking down-plunge, NW–SE）中标注的视倾角**：翼 A **9°**、翼 B **49°**、轴面/平分面 **29°**。

**自检**：49° − 9° = **40°** = 翼间角 ✓；(49° + 9°)/2 = **29°** = 平分面视倾角 ✓；剖面平面 147/80SW 与褶皱轴 10/057 的关系：走向 057−90 = **327/147** ✓，倾角 90−10 = **80°**，倾向 237 = **SW** ✓。**这三个自检每次做完都应该跑一遍。**

### 5.4 第 3 问：片麻岩中的构造与断层滑移矢量（`SolnGneissFault.md`）

**题目**："On a separate stereogram, plot a stereogram showing the orientation of the structures in the gneisses. Consider how these structures might be interrelated. What can and cannot be said about the slip vector of the fault that forms the western boundary of the gneisses?"

**投图数据（四类，必须分符号）**：
- poles to gneissose foliation（片麻理极点）
- mineral elongation lineation（远离断层处的矿物拉伸线理）
- boudin necks（布丁颈）
- poles to mylonitic foliation（糜棱面理极点）
- mineral elongation lineation（**朝向断层**的矿物拉伸线理）

**答案数值**：

| 要素 | 结果 |
|---|---|
| 远离断层的片麻理 gneissose foliation | **077/71S** |
| 糜棱面理 mylonitic foliation（**= 轴面**） | **040/30SE** |
| 应变椭球 **X 轴（e1，最大伸长）** | **47/235**（= 矿物拉伸线理） |
| 应变椭球 **Y 轴（e2）** | **34/093**（= 布丁颈） |
| 应变椭球 **Z 轴（e3，最大缩短）** | **19/347**（= **片麻理的极点**） |
| 三轴夹角检验 | **92°、91°、92°** —— 近似两两正交 ✓ |
| **断层滑移矢量 slip vector** | **30/130** |

**关键推理**：

1. **应变椭球的建立**：`X > Y > Z`，`e1 = X = 矿物拉伸线理`，`e2 = Y = 布丁颈`，`e3 = Z = 面理的极点`。
   - **面理垂直于最大缩短方向（Z）**、**线理平行于最大伸长方向（X）** —— 这是"组构 ↔ 应变椭球"的标准对应，本周首次正式使用（Class 3 会系统建立）。
   - 检验：**19/347 确实是 077/71S 的极点**（倾向 167，极点倾伏 19° 朝 347）✓。
   - 图注还说明："long axes of boudins **if limbs boudinaged**" —— 若翼部布丁化，布丁长轴平行 Y。
2. **糜棱面理 = 轴面**：答案图上直接写 "mylonitic foliation (= axial plane)"，其方位 **040/30SE** **与变质沉积岩中褶皱的轴面完全相同**（见 5.3）。这就是第 4 问的关键。
3. **滑移矢量 30/130**：注意 **040/30SE 这个面的倾向就是 130，真倾角 30°** —— 所以 **30/130 正是糜棱面理的真倾向线（down-dip direction）**，即**纯倾向滑动（dip-slip）**。结合"高级片麻岩被放置在低级变质沉积岩之上"，这是一条**逆冲断层（thrust）**，上盘向**上倾方向（约 310，即 NW）**运移。
4. **⭐ "can and cannot be said"**：
   - **可以说**：滑移**方向**（沿 30/130 这条线，即 NW–SE 向的倾向滑动），以及**运移指向**（上盘向 NW 逆冲，由变质级差 + 上/下盘关系确定）。
   - 📎 **背景补充（材料未直接写出，属合理推论）**：**不能说**滑移的**大小（位移量）**——图上没有任何可对比的被错断标志；也不能保证这条线理记录的是**整个滑动史**而非最后一次增量。

**其他从图上读出的时序信息**（`SolnMap.md` 注记）：
- **片麻理与线理都"扫入（swing into）"糜棱带** → 它们**早于**断层作用（先存组构被断层带剪切改造）。
- **下盘岩石不是糜棱岩** → 这条断层是"一条延伸到相当深度的断层的**浅部表现**"（footwall rocks not mylonitic implying that the fault is a shallow expression of a fault which extends to significant depth）。
- **角闪岩的变形可能与片麻理的形成协调（congruent）**。
- **片麻理与褶皱不协调（foliation not congruent with folding）** → 片麻岩中的面理**不是**西侧褶皱事件的产物。
- 图上另有一条问句式注记："curving towards a more lateral part of the thrust?" → 提示逆冲面方位的变化可能反映向逆冲带**侧向部分**的过渡。

### 5.5 第 4 问：褶皱与断层的相互关系

**题目**："Consider the interrelationship between the folding and the fault that forms the western boundary of the gneisses."

**两条互补的证据（`SolnMap.md`）**：

1. **"cleavage parallel to mylonitic foliation implying a genetic relationship between the two"** —— 变质沉积岩中的**轴面劈理**（其定义的轴面为 040/30SE）与片麻岩中的**糜棱面理**（040/30SE）**平行** → 二者**成因相关**：**下盘的褶皱是在逆冲过程中形成的**，不是一次无关的独立事件。
2. **"gneisses not folded implying final stages of thrusting after fold in metasediments formed"** —— 上盘片麻岩**没有被折叠** → 逆冲的**最后阶段发生在下盘褶皱形成之后**。

**综合结论**：褶皱与逆冲属于**同一次渐进变形（progressive deformation）**——褶皱在逆冲过程中于下盘发育（因而共享同一轴面方位），而逆冲的最终增量则**晚于**褶皱定型（因而上盘未被卷入褶皱）。**这正好呼应了讲义 Slide 7 notes 关于"两个阶段可以是同一次渐进变形的早、晚期"的说法。**

### 5.6 第 5 问：岩墙的几何与伸展量

**题目**："What can be said about the geometry of the dykes and how they were emplaced? Determine how much extension the area experienced parallel to the opening direction of the dykes during their emplacement…"

**推理链**：

| 观察 | 推论 |
|---|---|
| 岩墙**切穿褶皱、切穿断层** | 岩墙**晚于全部变形** |
| 岩墙**未变形** | 侵位于变形之后 |
| 图上无法约束 | ⚠️ **岩墙的倾角未知** |
| 各标志的**错开（cut-offs）关系**显示位移**垂直岩墙边界** | **岩墙沿垂直其边界的方向张开（opened normal to margins）** |
| **冷凝边呈对称排列** | (a) 冷凝边的**数目 = 每个复合侵入体中的注入次数**；(b) 每次岩浆注入都**沿先存岩墙的中心**贯入 |

**伸展量计算**：
1. 在图上画一条**平行于岩墙张开方向**（= 垂直岩墙走向）的测线。
2. 量出测线上**所有岩墙厚度之和 = ΔL**。
3. 量出测线**总长度**，减去 ΔL 得到 **L₀**（岩墙侵位前的原始长度）。
4. $e = \Delta L / L_0$。

⚠️ **易错**：分母是 **L₀ = 总长 − ΔL**，**不是总长**。题面已经把这一点写死："L₀ is the total length of that line minus ΔL (that is, L₀ is the original length of the line before the dykes were emplaced)."

### 5.7 写作规范：以证据为基础的构造演化史

`Cover.md` 给出的章节结构（**这就是练习考试短答题的骨架**）：

1. **总引言（无标题）**：先一句话概括图上有什么；然后每个事件用两三句话说明**是什么 + 顺序 + 证据**。**配一个小的地层柱状图会很有帮助。**
2. **The geometry of the structures in gneisses and the faulting** —— 描述片麻岩中构造的几何与断层几何；**附上片麻岩构造的赤平投影图，并充分注记解释性说明**；可加草图说明各构造的相互关系。
3. **The geometry of the folding in the metasedimentary units** —— 描述变质沉积岩中褶皱的几何；**附上褶皱的赤平投影图 + 简化的沿倾伏方向剖面**。
4. **The relationship between the folding and the faulting** —— 描述褶皱与断层的关系，配示意草图。
5. **The geometry of the dykes** —— 描述晚期岩墙的几何，**在叙述中包含伸展量的计算**。

**Tarskavaig Bay 的完整事件序列**（📎 **背景补充：以下顺序是我按 `SolnMap.md` 的各条注记整理成的时间线，材料本身没有把它写成一条列表**）：

1. 变质沉积岩序列沉积（粗砂岩 → 含砂岩板岩 → 细砂岩）
2. 片麻岩与角闪岩在**高温**条件下的韧性变形，形成片麻理（077/71S）、矿物拉伸线理（47/235）与布丁（Y = 34/093）—— **与 (1) 的相对年龄无法确定**
3. 变质沉积岩被折叠：褶皱轴 10/057、轴面 040/30SE、翼间角 40° 的**背形（同时为背斜）**，伴生轴面劈理与协调小褶皱
4. 逆冲：高级片麻岩沿 040/30SE 的糜棱带被推覆到低级变质沉积岩之上，滑移矢量 30/130（倾向滑动，上盘向 NW）；先存片麻理与线理被扫入糜棱带；**(3) 与 (4) 成因相关**，且**逆冲的最后阶段晚于褶皱定型**
5. 未变形的玄武岩墙群侵位，垂直边界张开，复合岩墙沿先存岩墙中心多次注入
6. （隐含）抬升与剥蚀至现今地形

### 5.8 额外练习 Ex5（`Ex5-1.md` / `Ex5soln.md`）

**题面**：2017 年 2 月 9 日的旧考卷（1 小时），大尺度褶皱区，围绕一个**向形（synform）**采集的数据：

- **层理**：086/37S, 109/59S, 125/V, 128/85NE, 131/79NE, 132/76NE, 133/73NE, 004/29E, 008/28E, 013/27E, 017/26E, 049/26SE
- **小褶皱轴**：26/123, 24/128, 27/126, 23/125
- **与小褶皱轴面平行的劈理的走向**：140°

要求："By plotting a stereogram fully describe the geometry of the fold and draw a simplified profile plane section to illustrate that geometry. The marking scheme is exactly as described in the in-class exercises of this kind."

**解题要点**：

1. 层理数据**明显分成两簇**：一簇陡（086/37S 到 133/73NE，倾向大致 S–NE）、一簇缓（004/29E 到 049/26SE，倾向 E–SE）→ 这是一个**明显不对称的褶皱**。
2. **两条独立的褶皱轴证据**：(a) 层理极点拟合的 π 圆的极点；(b) 直接测量的**小褶皱轴**（26/123 等，四个读数高度一致）。**两者应当吻合** —— 这是本题的自检。
3. **劈理只给了走向 140°**（没给倾角）：因此在赤平网上**先画出 140° 的走向线**，再找**同时包含该走向线与褶皱轴的那个平面** → 这个面就是**轴面**。（这是本题最需要动脑的一步：一个平面由"一条走向线 + 一条含于其中的线（褶皱轴）"唯一确定。）

**答案（`Ex5soln.md`）**：

| 要素 | 结果 |
|---|---|
| 褶皱轴 | **25/125** |
| 轴面 | **140/60NE** |
| 平分面 bisector | **150/48NE** |
| 翼 B | **133/73NE** |
| 翼 A | **004/29E** |
| 翼间角 | **56°** |
| 剖面平面 | **035/65NW** |

**剖面图（looking down-plunge, NE–SW）视倾角**：翼 B **71°**、翼 A **15°**、平分面 **43°**、轴面 **56°**。

**自检**：71° − 15° = **56°** = 翼间角 ✓；(71° + 15°)/2 = **43°** = 平分面 ✓；剖面平面：走向 125−90 = **035**、倾角 90−25 = **65°**、倾向 305 = **NW** ✓。
**给分点**：轴面视倾角 56° 比平分面 43° **陡 13°** → 必须写一句"**两翼层厚不同**（平分面 ≠ 轴面）"。

---

## 六、易错点 / 重点难点

### 6.1 概念层面

| 易错点 | 正确表述 |
|---|---|
| **把"类型"和"机制"混为一谈** | Buckling / Bending / Passive folding 是**类型**（按载荷方向分）；Flexural slip-flow / TLS / Shear folding 是**机制**（按内部变形方式分）。屈曲和弯曲**都**通过弯滑/弯流或 TLS 实现 |
| **把弯滑与 TLS 的应变分布记反** | **弯滑**：滑动量在**拐点最大、铰部为零**；**TLS**：应变在**铰部最大、拐点为零**。⭐ **完全相反，务必背牢** |
| **把外弧/内弧的应力状态记反** | **外弧（凸侧）拉张** → 张裂隙/张脉；**内弧（凹侧）压缩** → 劈理加强 / 共轭逆冲。记忆：**弯一根橡皮筋，外侧被拉长** |
| **误以为中和面是层的几何中面** | 中和面是**变形相互抵消**的那个面。讲义只给这个定义。📎 进阶知识：随褶皱发育它会向内弧迁移——**考试按讲义定义答** |
| **把黏度比的分子分母搞反** | **η_L（层）在分子，η_M（基质）在分母**。屈曲要求 **η_L > η_M**，所以比值 **> 1** |
| **把屈曲与被动褶皱对能干性差异的要求记反** | ⭐ **屈曲需要大的能干性差异**（层必须比基质更能干）；**被动褶皱的放大在能干性差异很小时最显著**（因而在高级变质岩中更突出）。**这两句正好相反，是最好的区分题** |
| **认为剪切褶皱是真实的褶皱机制** | 讲义明说它 **"is not believed to be a real folding mechanism"**，只是分析 Class 2 褶皱的**有用近似** |
| **认为布丁化只能由平行层伸展造成** | Slide 16 明说：**布丁化与伸展型膝折带可以由层法向压缩产生** |
| **认为看到 Type 3 干涉型式就是两期变形** | Slide 39 notes 明确警告：多斜褶皱**可以在单次变形事件中形成** |
| **认为膝折带可以用等倾线分析** | 膝折带是 **Class 2 几何**，但**铰是角状的 → 等倾线方法不适用**，必须直接标注角度与尺寸 |
| **把 pinch-and-swell 与 boudinage 对波长的控制混淆** | **pinch-and-swell** 层：波长由**薄处（颈）的间距**控制（**不是层厚**）；**boudinage** 层：波长**不**由布丁宽度控制 |

### 6.2 公式层面

| 易错点 | 正确表述 |
|---|---|
| **指数写成 1/2 或 1** | 黏度比的指数是 **1/3（立方根）** |
| **常数 6 漏掉或写错位置** | 6 在**分母**，与 η_M 相乘：`[η_L/(6η_M)]^(1/3)`。⚠️ 不是 `[η_L/η_M]^(1/3)/6`，也不是 `[6η_L/η_M]^(1/3)` |
| **2π 写成 π 或 2** | 前系数是 **2π** |
| **多层公式把 N 放错位置** | **N 乘在 η_L 上**（分子）：`[Nη_L/(6η_M)]^(1/3)`；**不是**乘在整个括号外，也不是乘在 d 上 |
| **抗屈曲能力的指数** | **∝ t³**（三次方），不是二次方 |
| **应变 e 的分母** | **e = ΔL/L₀，L₀ = 测线总长 − ΔL**（原始长度），不是现今总长 |

### 6.3 劈理相关（Class 1 内容，Practical 天天用）

| 易错点 | 正确表述 |
|---|---|
| **劈理折射方向判反** | ⭐ **在更能干的岩层中，劈理与层理的夹角更大（更陡地穿过层理）**；在不能干层中劈理**更接近平行层理**。记忆抓手：**软的层"随大流"，劈理躺平贴着层理；硬的层"不合作"，劈理硬顶着层理** |
| **用劈理折射判顶底时方向搞反** | 正粒序层向顶部黏土含量升高 → **劈理越靠近层顶越接近平行层理** |
| **忘了劈理折射改变的是倾角不是走向** | "changes dip (but not strike)" |
| **把劈理扇当成劈理折射** | **扇（fanning）**是同一岩性内劈理绕褶皱的收敛/发散排布；**折射（refraction）**是穿过岩性界面时的突变 |
| **把 transecting cleavage 当成扇** | transecting cleavage 是**转换压缩（transpression）**下劈理**系统性斜交轴面**，是另一回事 |

### 6.4 干涉型式（最需要空间想象）

**对应关系必须精确记住**（讲义原文，逐字核对过）：

| 型式 | 两期褶皱**轴** | 两期**姿态** | 图案 |
|---|---|---|---|
| **Type 0** | **共轴** | **共面** | 无新图案，仅强化 |
| **Type 1** | **⊥（90°）** | **两者皆直立**，轴面互成 90° | **穹–盆（dome and basin）** |
| **Type 2** | **⊥（90°）** | **一平卧、一直立** | **新月–蘑菇（dome-crescent-mushroom）** |
| **Type 3** | **≈ 共轴** | **一平卧、一直立** | **波状（convergent–divergent）** |

⚠️ **最常见的错误是把 Type 1 和 Type 2 弄反**。两者的**褶皱轴关系完全相同（都是 90°）**，区别**只在轴面姿态**：**都直立 = Type 1（规则蛋盒）**；**一平卧一直立 = Type 2（新月/蘑菇）**。
⚠️ **第二常见的错误是把 Type 2 和 Type 3 弄反**。两者的**姿态关系完全相同（一平卧一直立）**，区别**只在褶皱轴**：**轴正交 = Type 2**；**轴共轴 = Type 3**。

**一句话口诀**：**轴定"闭不闭"，面定"匀不匀"**——轴正交才有闭合圈（Type 1/2），轴面都直立才规则对称（Type 1）。

### 6.5 Practical 层面

| 易错点 | 正确表述 |
|---|---|
| **在剖面图上画真倾角** | 剖面图上必须画**在剖面平面内量得的视倾角**，从赤平网上读出 |
| **剖面平面方位算错** | 剖面平面 ⊥ 褶皱轴：**走向 = 倾伏向 ± 90°；倾角 = 90° − 倾伏角；倾向背离倾伏向** |
| **忘了标"looking down-plunge"和两端方向** | 三份 Soln 全都标了。**这是格式分** |
| **平分面 = 轴面 直接默认** | 只有**两翼层厚相同**时才成立。若二者视倾角有差，**必须写一句解释翼厚差异** |
| **赤平投影上数据与解释不分符号** | `Cover.md` 明确要求 "fully annotated with explanatory comments"。**数据符号、解释符号、方位读数、注记文字，四样都要有** |
| **因为片麻岩变质级高就说它更老** | ⭐ **变质级 ≠ 年龄。** 图上片麻岩与沉积岩之间**只有断层接触**，**相对年龄无法确定** |
| **用滑移线理去推位移量** | 线理只给**方向**；**位移量需要被错断的标志**，本图没有 |
| **忘了 X/Y/Z 与组构要素的对应** | **X（e1）= 矿物拉伸线理；Y（e2）= 布丁颈；Z（e3）= 面理的极点** |

---

## 七、本周术语表

| 英文 | 中文 | 简要说明 |
|---|---|---|
| Buckling | 屈曲 | 载荷平行层面时的褶皱；需要 η_L > η_M 与初始扰动；"主动褶皱" |
| Bending | 弯曲 | 载荷高角度斜交层面时的褶皱；"forced folding" |
| Passive folding | 被动褶皱 | 标志层被动记录围岩流动；能干性差异小时最显著 |
| Competent / competence | 能干的 / 能干性 | 对流动的抗力；能干 = 高黏度 |
| Viscosity (η) | 黏度 | 剪应力 / 剪应变速率 |
| Newtonian viscous | 牛顿黏性（线性黏性） | 黏度与所施剪力无关 |
| Shear-thinning | 剪切变稀 | 黏度随剪力增大而降低；岩石常见 |
| Dominant wavelength (λ) | 主波长 | 放大最快的扰动波长 |
| Zone of influence | 影响区 | 折叠层的影响范围，约一个波长 |
| Effective single layer | 有效单层 | 近距能干层集体表现为厚单层 → 长波长 |
| Harmonic folding | 谐和褶皱 | 各能干层同波长同相位；λ 公式含 N |
| Polyharmonic folding | 多谐褶皱 | 多个波长，但服从某控制层 |
| Disharmonic folding | 不谐褶皱 | 能干层间距 > 影响区 → 各自独立折叠 |
| Ptygmatic folding | 肠状褶皱 | 不能干层远厚于能干层；轴面方位变化极大 |
| Controlling layer | 控制层 | 异常厚的层，控制整个多层体的褶皱波长 |
| Accommodation structures | 调节构造 | 龙骨状铰、铰部逆冲越顶、铰部逆断层、翼部布丁化 |
| Keel-like hinge / hinge collapse | 龙骨状铰 / 铰部坍塌 | 一种调节构造 |
| Chevron fold | 尖棱褶皱 | 铰"锐利"的褶皱；翼倾角依赖层厚 |
| Anisotropic | 各向异性的 | 抗剪与抗压的能力不同 |
| Penetrative fabric | 穿透性组构 | 如板岩中的劈理 |
| Kink band | 膝折带 | Class 2 几何但铰角状；收缩/伸展、右行/左行 |
| Box fold | 箱状褶皱 | 一对共轭收缩型膝折带组成 |
| "Fag-end" structures | "烟屁股"构造 | 造山晚期膝折带，对主变形信息量小 |
| Pre-buckle shortening | 前屈曲缩短 | 折叠前的均匀缩短与加厚 |
| Fold initiation / nucleation | 褶皱成核 | 由层内不规则性触发 |
| Locking up | 锁死 | 层旋转至不利方位，屈曲停止 |
| Post-buckle flattening | 后屈曲压扁 | 褶皱被动生长；1B → 1C |
| Dip isogon | 等倾线 | 连接折叠层上下界面上倾角相等的点 |
| Class 1B / parallel fold | 平行褶皱 | 正交层厚不变；屈曲的产物 |
| Class 1C | — | 1B 被垂直轴面压扁后的产物 |
| Class 1A | — | 1B 被平行轴面压缩后的产物 |
| Class 2 / similar fold | 相似褶皱 | 平行轴面的层厚不变；剪切/被动褶皱的产物 |
| Class 3 | — | 铰部加厚；典型的不能干夹层 |
| Flexural slip | 弯滑 | 滑动面间距大（如层面）；层内无畸变 |
| Flexural flow | 弯流 | 滑动面很密，层平行剪切均匀分布 |
| Tangential longitudinal strain (TLS) | 切向纵向应变 | 外弧拉张、内弧压缩、中间为中和面 |
| Neutral surface | 中和面 | 外弧拉张与内弧压缩相互抵消的面 |
| Outer arc / inner arc | 外弧 / 内弧 | 分别受拉伸 / 压缩 |
| Shear folding | 剪切褶皱 | "剪扑克牌"；剪切面平行轴面；非真实机制 |
| Tectonic a-direction | 构造 a 方向 | 线理大圆与轴面的交点；断层滑移矢量 |
| Slip vector | 滑移矢量 | 断层的滑动方向 |
| Slickolites | （讲义用语）滑动面线理 | 讲义注释：非对称压溶缝合线（Class 6） |
| En échelon tension gashes | 雁列张裂脉 | 指示滑动指向；S 形离铰越远越明显 |
| Small circle / great circle | 小圆 / 大圆 | 弯流 → 小圆；剪切褶皱 → 大圆 |
| Inflection point | 拐点 | 弯滑滑动量最大处；TLS 应变为零处 |
| Cylindrical fold | 圆柱状褶皱 | 平行剖面上形状不变 |
| Pericline | 穹丘 | 沿轴生长消亡的长条形穹隆；常雁列排列 |
| Bifurcating hinge | 分叉铰 | 褶皱铰线分岔 |
| Sheath fold | 鞘褶皱 | 铰线在轴面内弯曲 > 90°；剪切带特征 |
| Polyclinal fold | 多斜褶皱 | 平直铰线 + 弯曲轴面 |
| Soft sediment deformation | 软沉积变形 | 产生高度非圆柱状褶皱 |
| Convolute slump fold | 滑塌卷曲褶皱 | 软沉积变形产物 |
| Refolded / superposed folds | 再褶皱 / 叠加褶皱 | 两期及以上变形的产物 |
| Fold interference pattern | 褶皱干涉型式 | Type 0/1/2/3 |
| Dome and basin | 穹–盆 | Type 1 图案（蛋盒） |
| Dome-crescent-mushroom | 穹–新月–蘑菇 | Type 2 图案 |
| Convergent–divergent | 收敛–发散（波状） | Type 3 图案 |
| Coaxial / coplanar | 共轴 / 共面 | 两期褶皱轴平行 / 轴面平行 |
| F1, F2 / S0, S1, S2 / D1, D2 / L1, L2 | 一期、二期褶皱 / 层理、一期、二期劈理 / 变形幕 / 线理 | 讲义标准符号约定 |
| Axial planar cleavage | 轴面劈理 | 平行或近平行轴面（Class 1） |
| Cleavage refraction | 劈理折射 | 穿岩性界面改变倾角不改变走向（Class 1） |
| Cleavage fanning (convergent / divergent) | 劈理扇（收敛 / 发散） | 劈理绕褶皱的扇形展布（Class 1） |
| Transecting cleavage | 斜切劈理 | 转换压缩下系统斜交轴面（Class 1） |
| Crenulation cleavage | 褶劈理 | 已有组构被再变形形成；其存在即证明多期变形（Class 1） |
| Congruent minor structures | 协调小构造 | 与大构造几何系统相关的小构造（Class 1） |
| Bisector | 平分面 | 平分翼间角的面；两翼等厚时 = 轴面 |
| Profile plane | 剖面平面 | 垂直于褶皱轴的平面 |
| Down-plunge section | 沿倾伏向剖面 | 沿褶皱轴倾伏方向观看的剖面 |
| Mylonitic foliation | 糜棱面理 | 断层带中的韧性组构 |
| Gneissose foliation | 片麻理 | 片麻岩中的面理 |
| Mineral elongation lineation | 矿物拉伸线理 | 平行应变椭球 X 轴 |
| Boudin neck | 布丁颈 | 平行应变椭球 Y 轴 |
| Strain ellipsoid (X > Y > Z) | 应变椭球 | e1 = X, e2 = Y, e3 = Z |
| Chilled margin | 冷凝边 | 岩墙边缘的细粒带；数目指示注入次数 |
| Composite intrusion | 复合侵入体 | 多次注入沿先存岩墙中心贯入 |
| Hanging wall / footwall | 上盘 / 下盘 | 断层上方 / 下方岩体 |
| Younging | 顶底指向 | 地层变新方向 |
| Antiform / anticline | 背形 / 背斜 | 向上闭合 / 核部最老 |
| Synform / syncline | 向形 / 向斜 | 向下闭合 / 核部最新 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Class2_FoldFormation.md` Slide 6 正文项目符号 | `- It can also be shown that large viscosity contrasts lead to more rapid fold amplification and less layer thickening (that is, layer` / `- increasing viscosity contrast` / `- parallel shortening other than buckling)` | **pptx → md 提取时项目符号顺序被打乱**，一句话被两个图注插入而截断，字面上读不通 | 完整句应为："It can also be shown that large viscosity contrasts lead to more rapid fold amplification and less layer thickening (that is, **layer-parallel shortening other than buckling**)."；`increasing viscosity contrast` 是插图上的坐标轴标注，不属于正文 |
| `Class2_FoldFormation.md` Slide 6 图注标注 | `- h L /h M` | **希腊字母 η 被误识别为拉丁字母 h**（PowerPoint 中 η 常以 Symbol 字体输入，提取时退化为 h） | 应为 **η_L / η_M**（层黏度 / 基质黏度）。同类问题：正文中的 `η L`、`η M` 之间的空格也是字体切换造成的 |
| `Class2_FoldFormation.md` Slide 4 / 5 / 6 / 8 公式 | `λ = 2π d [ η L / ( 6η M ) ]1/3` | **上标格式丢失**，`1/3` 直接跟在 `]` 后面，容易被误读为"乘以 1/3"或"1 除以 3" | 应为 **λ = 2πd[η_L/(6η_M)]^(1/3)**，即黏度比取**立方根**。公式的系数（2π）、常数（6）、比值方向（层在分子）与指数（1/3）经核对与标准 Biot–Ramberg 主波长公式一致，**内容本身无误，仅排版丢失** |
| `Class2_FoldFormation.md` Slide 19 正文 | `- 0` / `- 1` / `- 2` / `- 4` / `- 3` / `- 3` / `- 2` | 这是幻灯片上两幅插图的**阶段编号标注**被平铺成项目符号，顺序错乱且有重复 | 实际阶段编号为 **1–4**（前屈曲缩短、成核、放大→锁死、后屈曲压扁）；`0` 与重复的 `2`、`3` 是另一幅图上的曲线标注。正文四条阶段名称本身完整无误 |
| `Class2_FoldFormation.md` Slide 26 第一条次生特征 | "Lineations on the slip plane (grooves or more commonly crystal fibres) oriented at a high angle to the hinge (**slickolites**)" | **术语可能不精确**：括号里描述的"沟槽或晶体纤维"在标准术语中是 **slickenlines / slickenfibres（擦痕 / 纤维擦痕）**；而 slickolites 按本讲义自己在 notes pane 中的定义是"asymmetric stylolites（非对称压溶缝合线）"，属于**压溶**成因，与纤维**生长**成因不同 | 建议理解为：弯滑滑动面上可发育两类线理——**擦痕/纤维擦痕**（机械滑动与纤维结晶）与 **slickolites**（非对称缝合线，压溶成因，Class 6 展开）；二者都高角度斜交铰，都可指示滑动方向。**答题时若引用讲义，照写 slickolites 不会失分，但要知道二者的成因区别** |
| `Practical/Week 2/Cover.md` 第 5 题公式 | `e = D L / L 0`，正文 "where D L is the total thickness of dyke…" | PDF 中的希腊字母 **Δ（Delta）被提取为拉丁字母 D** | 应为 **e = ΔL / L₀**。文中随后的 `D L` 也应为 `ΔL` |
| `Practical/Week 2/Ex5-1.md` 页眉 | `EART20292` | 与本课程代码 **EART28202** 不一致 | 这是 **2017 年的旧课程代码**（该练习是当年的正式考卷，现作为 extra practice 使用），**不是错误**，但看到时不要以为拿错了科目的卷子 |
| `Practical/Week 2/Ex5soln.md` 图内文字 | `...axial plane 140/60NE / bisector / limb A 150/48NE / 004/29E` | PDF 图内标注被平铺成一行后，**标签与数值的配对关系丢失**，字面上会读成"limb A = 150/48NE"，与题面给出的层理数据（缓翼一簇为 004/29E–049/26SE）矛盾 | 正确配对应为：**limb B = 133/73NE，axial plane = 140/60NE，bisector = 150/48NE，limb A = 004/29E**。验证：剖面内两翼视倾角 71° 与 15° 之差 = 56° = 翼间角 ✓；(71°+15°)/2 = 43° = 平分面视倾角 ✓ |
| `Practical/Week 2/SolnMap.md` 图内文字整段 | 大段无标点的连续文本，方位读数与注记文字交错 | 这是**手绘注记地图的 PDF 文字提取**，空间排布信息完全丢失，单读 md **无法复原图面**（例如 "antiform is an anticline and so are later" 实为两条独立注记被拼接） | **不是内容错误，是格式损失**。本笔记第五节已按语义把注记逐条拆开还原；如需核对图面细节，只能对照原 PDF/纸质图 |
| `Class2_FoldFormation.md` Slide 39 标题与 Slide 36–38 | Type 1 = dome and basin；Type 2 = dome-crescent-mushroom；Type 3 = convergent-divergent | — | **逐一核对无误**，与 Ramsay (1967) 的原始分类编号完全一致。Type 1/2 的褶皱轴都成 90°、区别在轴面姿态；Type 2/3 的姿态相同、区别在褶皱轴——这两点在讲义中表述准确，**不是错误，但极易记反**（见第六节） |

**除上述条目外，本周材料在物理内容上未发现错误**；所列条目中，绝大多数是 pptx/pdf → markdown 的**格式与字符提取问题**，仅 Slide 26 的 `slickolites` 一条属于术语精确性的讨论。
