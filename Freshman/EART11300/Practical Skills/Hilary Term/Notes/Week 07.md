# Week 7 — 比较形态学测量实践 (Comparative Morphology) / 褶皱与断层的地质图判读 (Folds and Faults on Geological Maps)

> 课程：EART11300 Practical and Professional Skills Development（BSc Earth and Planetary Sciences, Year 1, Hilary Term）
> 本周材料：`Week 7/Morning/`（讲义 Handout + Excel 模板 + 幻灯片操作说明，共 3 个 md）、`Week 7/Afternoon/`（folds-faults practical **含解答版** 1 个 md）
> 注意：下午场 PDF 的内页标题写的是 "Week 6 – Folds and Faults on Geological Maps"，但文件归档在 Week 7 文件夹内。这是材料本身的编号残留，内容以 Week 7 为准。

---

## 一、本周主题

本周是**两场主题完全不同的实践课**，一场生物 / 古生物形态学定量分析，一场构造地质学图件判读。

**上午场：Comparative Morphology Practical（比较形态学实践，2025 年 3 月，Jones）**
- 研究对象：**偶蹄类 (artiodactyls)** 的**掌骨 (metacarpal)**，即前肢的掌部长骨。
- 核心问题：掌骨的**形状**（长 vs 宽）和**关节面面积**如何随体型 / 类群变化？这些变化的**生物力学 (biomechanics)** 与**演化**含义是什么？
- 技能重点：用**游标卡尺 (callipers)** 采集骨骼测量数据 → 录入共享 Google 表格 → 在**桌面版 Excel** 中做散点图 (scatterplot)、分组回归 (regression)、**对数变换 (log transform)** → 解读**斜率 (slope)**、**截距 (intercept)**、**r²**。
- 本质上这是一堂「**定量形态测量 + 缩放律 (scaling) 分析**」课，也是这门课里少见的「野外 / 实验室采数据 → 统计分析 → 图形汇报」的完整链条。

**下午场：Folds and Faults on Geological Maps（褶皱与断层）**
- 前面几周的地质图练习都处理**近水平地层**或整合 (conformable) 层序；本周开始处理**受构造应力改造**的岩层。
- 三大目标（讲义原文）：
  1. 描述地层中**褶皱 (folds)** 与**断层 (faults)** 的几何形态；
  2. 理解造成褶皱 / 断层的**构造过程 (tectonic processes)** 或**岩石自身性质**；
  3. 能在**地质图**上识别褶皱与断层，并用简洁术语描述其几何。
- 技能链条：走向 / 倾角 (strike & dip) 记法 → 橡皮泥 (modelling clay) 三维手作模型 → 从模型「切片」得到**平面图 (map view)** 露头模式 → 在真实 BGS 地质图（Pembrokeshire、Keswick）上认褶皱轴迹与断层类型 → 野外照片素描。
- 关键分界：**韧性变形 (ductile deformation) = 褶皱**；**脆性变形 (brittle deformation) = 断层**。

---

## 二、核心概念

### （一）上午场：比较形态学与骨骼生物力学

#### 1. 讲义给出的六个关键术语（Key Terms，原文照抄 + 展开）

| 术语 | 讲义定义 | 展开理解 |
|---|---|---|
| **Morphology（形态学）** | The study of biological form, shape, or structure. | 研究生物的**形态、形状、结构**本身。 |
| **Comparative morphology（比较形态学）** | Examining variation in morphology across individuals, life stages, or species. | 跨**个体**、跨**生命阶段**、跨**物种**比较形态差异。本周做的是跨物种 + 跨体型（大羊 vs 小羊、大牛 vs 小牛）。 |
| **Biomechanics（生物力学）** | Study of the structure and function of biological systems. | 把骨骼当**力学构件**（杠杆、承重柱）来分析。 |
| **Artiodactyls（偶蹄类）** | Even-toed ungulates including Cervidae, Bovidae, and Giraffidae. | 偶蹄目有蹄类，本周涉及**鹿科 Cervidae**、**牛科 Bovidae**、**长颈鹿科 Giraffidae**。 |
| **Metapodial（掌 / 跖骨）** | Long bones of the hands (metacarpals) and feet (metatarsals) which connect the toes/fingers to the leg/arm bones. | 连接指 / 趾骨与前臂 / 小腿骨的长骨。前肢的叫 **metacarpal（掌骨）**，后肢的叫 **metatarsal（跖骨）**。 |
| **Epiphysis（骨骺）** | The end part of a long bone which articulates with other bones to form a joint. | 长骨的**末端**，与其他骨形成关节的部分。分**近端骨骺 (proximal epiphysis)**（与腕骨关节）和**远端骨骺 (distal epiphysis)**（与指骨关节）。 |

#### 2. 演化背景：融合的第三 / 第四掌跖骨（fused III + IV metapodials）

- 许多偶蹄类共有一个**衍生特征 (evolved / derived character)**：**前肢与后肢的第三、第四掌 / 跖骨愈合成一根骨**（俗称 **cannon bone，炮骨**）。
- 这种手足骨的愈合，与**奔跑哺乳动物的肢体延长 (elongation of limbs)** 相关联。
- 愈合的力学意义（讲义未展开，但是本实践的逻辑前提）：把两根独立的骨合并成一根，**抗弯刚度增加、重量减少、关节自由度受限**，使肢体运动被约束在**矢状面 (parasagittal plane)** 内 —— 这是**奔跑型 (cursorial)** 哺乳动物的典型适应。

#### 3. 掌骨生物力学（Metacarpal biomechanics）—— 本次实践的两条核心假设

讲义原文给出两条力学论断，正好对应 Task 1 与 Task 2：

**论断 A（对应 Task 1，形状）**
> "The breadth of the shaft of the metacarpal relative to its length is related to the mode of locomotion and to the extent of elongation of the limbs. A relatively longer metacarpal indicates a more elongate limb, producing a **long out-lever** for rapid limb movements during running."

- **骨干宽度 (shaft breadth, B) 相对于长度 (length, L) 的比值**，反映**运动方式 (mode of locomotion)** 与**肢体延长程度**。
- 掌骨相对更长 ⇒ 肢体更细长 ⇒ 形成更长的 **out-lever（外力臂 / 输出臂）** ⇒ 奔跑时肢体末端线速度更大、**步幅 (stride length)** 更长。
- 杠杆背景：肌肉附着点到关节的距离是 **in-lever（内力臂）**，关节到肢体末端是 **out-lever**。**out-lever / in-lever 比值大 = 速度优势、力量劣势**（gear ratio 高）。奔跑动物走「高速档」。
- 代价：out-lever 变长意味着骨干承受的**弯矩 (bending moment)** 变大；若骨干宽度不同步增加，**弯曲应力 (bending stress)** 上升，骨折风险增加。所以 B–L 关系的**斜率**就是「细长化 vs 稳健化」的权衡指标。

**论断 B（对应 Task 2，关节缩放）**
> "The surface area of the joint of the metacarpal is designed to carry a large proportion of the animal's body weight, so heavier animals are expected to have larger epiphyses to distribute the load."

- 关节面主要功能是**承重**并把载荷分散，以限制**关节软骨 (joint cartilage) 上的应力**。
- 补充力学前提（讲义 Task 2 开头给出）：**四足动物约 2/3 的体重由前肢承担**（"In most quadrupedal animals approximately two-thirds of the weight of the body is carried on the forelimbs"）。所以用**前肢掌骨**的关节面积对体重作图是合理的。
- 应力 = 力 / 面积 ≈ (体重 × 2/3) / 关节面积。若要**应力恒定**，关节面积必须**正比于体重**。

#### 4. 三大类群（Task 1 的 Q2 要求自己查资料定义）

| 科 | 中文 | 代表 | 头饰 (headgear) | 本周实验标本 |
|---|---|---|---|---|
| **Cervidae** | 鹿科 | 马鹿、驼鹿、狍 | **鹿角 (antlers)**：纯骨质、分叉、**每年脱落再生**，多数仅雄性有 | 驼鹿 *Alces alces*、马鹿 *Cervus elaphus*、狍 *Capreolus capreolus* |
| **Bovidae** | 牛科 | 牛、绵羊、山羊、羚羊 | **洞角 (horns)**：**骨心 + 永久角质鞘 (keratin sheath)**，**不分叉、不脱落**，雌雄常皆有 | 绵羊 *Ovis aries*、家牛 *Bos taurus* |
| **Giraffidae** | 长颈鹿科 | 长颈鹿、㺢㹢狓（霍加狓） | **皮骨角 (ossicones)**：终生被皮肤 / 毛覆盖，**不脱落、不分叉** | 长颈鹿 *Giraffa camelopardalis*，另加文献中的 *Okapia johnstoni* 与三个化石属 |

三者同属**反刍亚目 (Ruminantia)**；讲义提供了一张**反刍类系统发育树 (Ruminant Phylogeny, from Janis & Theodor, Zitteliana 2015)**，用来把测量结果放到演化框架里解读。

> 讲义中把马鹿写成 "*Cervus elephas*"，Excel 模板中写作 "*Cervus elaphus*"。**正确拼写是 *Cervus elaphus***。

#### 5. 化石长颈鹿科类群（文献数据来源）

来自 **Rios et al., Palaeontologia Electronica 2016**，用于把现生标本与化石类群放在同一张图上，从而看**长颈鹿科掌骨延长的演化轨迹**：

| 物种 | 中文 / 说明 | 状态 |
|---|---|---|
| *Giraffa camelopardalis* | 长颈鹿 | 现生 |
| *Okapia johnstoni* | 霍加狓 / 森林长颈鹿（Forest Giraffe） | 现生，森林型、非奔跑特化 |
| *Bohlinia attica* | 波氏长颈鹿（化石） | 灭绝，中新世，长颈鹿的近亲 |
| *Palaeotragus rouenii* | 古麟（化石） | 灭绝 |
| *Canthumeryx sirtensis* | 化石长颈鹿科基干类群 | 灭绝，最原始、掌骨最短 |

---

### （二）下午场：褶皱与断层的构造地质学

#### 1. 岩层产状：走向与倾角（Strike and Dip）

- **地层 (strata)**：岩石层；单数为 **stratum**。
- **走向 (strike)**：某**平面**（如层面 bedding plane）与**水平面**交线的**罗盘方位角**。
  - 走向线**永远水平**。
  - 从**北 (000°)** 起算，**写成三位数**（例：145°）。
  - 同一条走向线有两个读数，相差 180°（075 ↔ 255；160 ↔ 340），两个都可接受。
- **倾角 (dip)**：**永远在垂直于走向的方向上量**，是从**水平面向下量的角度**，取值 **0°（水平）～ 90°（直立）**。
  - 为消除歧义，需注明**倾向的象限**，例：`145 / 50 SW`。
- **倾角 + 倾向 (dip and dip direction)**：另一种记法。倾角同上；**倾向 (dip direction)** 是倾斜方向投影到水平面上的罗盘方位角。
  - 例：某层向南倾 30° → 写作 **30/180**（南 = 180°）。
- **两种记法的换算**（下午场 Exercise 1 的核心考点）：
  - 若倾向在走向线的**顺时针一侧**：`dip direction = strike + 90°`
  - 若倾向在走向线的**逆时针一侧**：`dip direction = strike + 270°`（等价于 strike − 90°）
  - 判断加 90 还是加 270，**必须画罗盘、看象限对不对**。
- **地图符号 (Figure 1)**：
  - **现代 BGS 符号**：**长线 = 走向**，**短线（带数字）= 倾向**，数字是倾角。
  - **旧式（仍常见）符号**：**箭头指示倾向**，数字是倾角。箭头指的是**下倾方向 (downdip direction)**。

#### 2. 褶皱（Folds）

**成因**：地壳内**压缩力 (compressive forces)** 的结果，代表**韧性 (ductile) 的地壳缩短 (crustal shortening)** 方式。
> 记牢这条对照：**韧性变形 = 褶皱；脆性变形 = 断层。**

**四个最容易混淆的名词（几何 vs 年龄）**

| 术语 | 定义 | 判据类型 |
|---|---|---|
| **Antiform（背形）** | 向**上**闭合 (closes upwards) 的褶皱面 | **纯几何描述** |
| **Synform（向形）** | 向**下**闭合 (closes downwards) 的褶皱面 | **纯几何描述** |
| **Anticline（背斜）** | 核部 (core) 是**最老**岩石 | 需要**地层年龄**知识 |
| **Syncline（向斜）** | 核部是**最新**岩石 | 需要**地层年龄**知识 |

- 二者可以**自由组合**：常见的是 **anticlinal antiform（背斜背形）** 与 **synclinal synform（向斜向形）**；但若地层已被更早期变形**倒转 (overturned)**，则可以出现 **anticlinal synform** 或 **synclinal antiform**。
- **Younging symbol（变新符号，Y 形符号）**：**"Y" 的尾巴指向最年轻的地层**；**永远画成与走向成 90°**。

**褶皱解剖学（Figure 4 的术语）**

| 术语 | 中文 | 定义 |
|---|---|---|
| **Limb** | 翼 / 翼部 | 由**倾向不同**的层面构成的褶皱两侧 |
| **Fold hinge** | 枢纽 | 两翼相交处，层理**方向发生转变**的位置 |
| **Fold axis** | 褶皱轴 | 沿褶皱延伸、**平行于枢纽**的假想线 |
| **Axial plane** | 轴面 | 通过枢纽线（与褶皱轴）、**平分褶皱剖面**的假想平面 |
| **Interlimb angle** | 翼间角 | **两翼之间的夹角**（讲义原文："very pleasingly, called the interlimb angle"） |
| **Plunge** | 倾伏 / 倾没 | **褶皱轴本身的倾角**（褶皱轴不水平时即为倾伏褶皱） |
| **Axial trace** | 轴迹 | 轴面**投影到地图平面上**的线，平行于褶皱轴 |

**褶皱分类的两个独立变量（Figure 5）**：
1. **轴面产状 (orientation of the axial plane)** → upright / inclined / overturned / recumbent；
2. **翼间角大小 (interlimb angle)** → gentle / open / close / tight / isoclinal。

#### 3. 断层（Faults）

**成因**：岩石发生**脆性 (brittle) 变形**而非韧性变形。讲义列出三条控制因素：
1. **岩石本身的材料性质 (material properties)**；
2. **深度与温度低**（**高压高温有利于韧性变形**，浅部低温有利于脆性）；
3. **高应变速率 (high strain rates)**（快速变形有利于脆性破裂）。

**定义**：断层是地壳内的一个**平面 (planar surface)**，沿此面岩石发生了**位移 (displacement)**。

**完整刻画一条断层需要三项信息**（讲义明确列出）：
1. **断层面的产状 (orientation of the fault plane surface)**；
2. **滑移矢量的方向 (orientation of the slip vector)** —— 描述运动方向；
3. **位移量 (amount of displacement)**。

**Anderson (1905) 分类**：按**主应力 (principal stresses)** σ1（最大）、σ2（中间）、σ3（最小）的**方位与相对大小**分类（详见第三节对照表）。

**上盘 / 下盘**
- **Hanging wall（上盘）**：位于**断层面之上**的岩块（图 10a 中标 "H"）。
- **Footwall（下盘）**：位于**断层面之下**的岩块。
- 只有**倾斜断层面**才有上下盘之分；**直立断层面**无上下盘。

**三大类断层**（讲义重点区分的三种）
- **Normal fault（正断层）**：断层面**陡倾（~60°）**，**上盘下降 (downthrown)**。效果是把**年轻岩石放到老岩石旁边或之上**。
- **Reverse fault（逆断层）**：断层面可以陡倾（与正断层相似），**也可以很缓（~30°）—— 缓倾者称 thrust fault（逆冲断层）**。**上盘向上运动**，结果是**老岩石被推到年轻岩石之上**。
- **Dip-slip fault（倾滑断层）**：正断层与逆断层的统称，位移**有强烈的垂直分量**。
- **Strike-slip fault（走滑断层）**：位移**以水平 / 侧向为主**，可为**左行 (left lateral / sinistral)** 或**右行 (right lateral / dextral)**。
  - 判别法（讲义原文）：**想象自己站在断层的一侧，向对面看，看对面岩石往哪个方向移动**——往左即左行，往右即右行。
- **Oblique slip（斜滑）**：兼有倾滑与走滑分量（图 10e）。

**构造史意义**：某地断层类型的组合可以重建该区的**构造史 (tectonic history)**。例：英国境内大型 **~SW–NE 走向的逆冲断层**，揭示了不列颠是由若干**古老地壳碎块 (ancient crustal fragments)** 拼合而成。

---

## 三、公式与图表

### （一）上午场：形态学测量的指标与计算

#### 1. Task 1 的两个测量量

| 符号 | 全称 | 含义 | 单位 | 工具 |
|---|---|---|---|---|
| **L** | Maximum length | 掌骨的**最大长度**（两端最远两点之间） | mm | 游标卡尺 |
| **B** | Midshaft breadth | **骨干中段**（midshaft）的**宽度** | mm | 游标卡尺 |

**分析**：以 **L 为 x 轴、B 为 y 轴**做散点图；对 **bovid / cervid / giraffid 三组分别**加线性回归：

```
B = m · L + c
```
- **m（斜率 slope）**：长度每增加 1 mm，骨干宽度增加多少 mm。**斜率大 = 变长的同时也迅速变粗（稳健化 robust）；斜率小 = 变长时宽度几乎不跟上（细长化 gracile）。**
- **c（截距 intercept）**：回归线在 L = 0 处的外推值。截距高 = 在同等长度下整体更粗壮。**注意 L = 0 无生物学意义，截距只作组间相对比较用，不可外推解释。**
- **r²（决定系数）**：回归解释的**方差比例**，0～1，越接近 1 表示 B 与 L 的线性关系越紧密。

**衍生指标（自行计算，便于组间比较）**：
```
稳健指数 (robustness index) = B / L × 100 %
```
数值越小 = 骨干相对越细长。

#### 2. 用讲义给出的长颈鹿科文献数据做的完整算例

原始数据（Rios et al. 2016）：

| Species | L (mm) | B (mm) | B/L (%) |
|---|---|---|---|
| *Giraffa camelopardalis* | 694 | 45.1 | 6.50 |
| *Okapia johnstoni* | 325 | 30.4 | **9.35** |
| *Bohlinia attica* | 687 | 50.3 | 7.32 |
| *Palaeotragus rouenii* | 414 | 29.3 | 7.08 |
| *Canthumeryx sirtensis* | 270 | 19.1 | 7.07 |

对这 5 个点做 B vs L 线性回归（仅文献数据，未含实验室标本）：

```
平均 L = 478.0 mm，平均 B = 34.84 mm
Σ(ΔL·ΔB) = 9755.1     Σ(ΔL)² = 161106
slope m = 9755.1 / 161106 ≈ 0.0606 mm/mm
intercept c = 34.84 − 0.0606 × 478 ≈ 5.90 mm
r ≈ 0.959 → r² ≈ 0.92
```

**解读要点**（可直接用于 Q3）：
- 长颈鹿科的 B–L 关系**非常线性（r² ≈ 0.92）**，斜率仅 **~0.06**：掌骨每延长 100 mm，骨干只加粗约 6 mm。
- **霍加狓 (*Okapia*) 的 B/L 高达 9.35 %，是全组最粗壮**——它是**森林居住、非奔跑特化**的类型；而**长颈鹿 B/L 仅 6.50 %，最细长**。这直接印证「掌骨相对细长程度 ↔ 运动方式」的论断。
- 最原始的 *Canthumeryx*（L = 270 mm）到 *Giraffa*（L = 694 mm），**长度增加了 2.6 倍而 B/L 基本维持在 6.5–7.3 %**，说明长颈鹿科的演化路径是**近乎等比例地整体拉长**，而非单纯细化。

#### 3. Task 2 的关节面积公式

测量量：

| 符号 | 全称 | 含义 | 单位 |
|---|---|---|---|
| **W** | Medio-lateral width | **远端骨骺**的**内–外侧宽度** | mm |
| **D** | Antero-posterior diameter | **远端骨骺**的**前–后向直径** | mm |
| **Mass** | Body mass | 体重（**由文献给定，不测量**） | kg |

**几何模型**：远端掌骨骨骺的关节面**近似为半个圆柱体 (half of a cylinder)** 的侧面。

```
Area = W × D × π ÷ 2          （mm²）
```

> 推导直观理解：把关节面看成一个直径 ≈ D 的半圆柱，圆柱轴长 ≈ W。半圆柱侧面积 = (π·D / 2) × W = W × D × π / 2。

**Excel 模板中的体重数值（已预填，勿改）**：

| Common name | Species | Mass (kg) |
|---|---|---|
| Small sheep | *Ovis aries* | 25 |
| Large sheep | *Ovis aries* | 50 |
| Roe deer | *Capreolus capreolus* | 25 |
| Red deer | *Cervus elaphus* | 170 |
| Moose | *Alces alces* | 450 |
| Small cattle | *Bos taurus* | 250 |
| Large cattle | *Bos taurus* | 500 |
| Giraffe | *Giraffa camelopardalis* | 1000 |

体重跨度 **25 → 1000 kg（40 倍）**，这正是必须做对数变换的原因。

#### 4. 对数变换与缩放律（Scaling）

Excel 公式：`=LOG10(x)`（模板 I15 已给出示例：`LOG10(25) = 1.3979400086720377`）。

**为什么取对数？**
幂律关系 `y = a·x^b` 两边取对数后**变成直线**：
```
log₁₀(y) = log₁₀(a) + b · log₁₀(x)
```
于是 **log–log 图上回归线的斜率就是缩放指数 b**，**截距就是 log₁₀(a)**。

**三种可能结果的判读（Task 2 Q3 的核心）**

| 斜率 b（log Area vs log Mass） | 名称 | 含义 |
|---|---|---|
| **b = 2/3 ≈ 0.67** | **几何相似 / 等比生长 (geometric similarity, isometry)** | 面积 ∝ 长度²，质量 ∝ 长度³ ⇒ Area ∝ Mass^(2/3)。形状不变、单纯放大。**后果：应力 = 质量/面积 ∝ Mass^(1/3)，随体型增大而上升** —— 大动物的关节软骨压力更大。 |
| **b = 1** | **应力恒定 (constant stress)** | 面积**正比于**体重，应力与体型无关。这是讲义 Hint 所指的「the relationship between the two variables remains the same as it scales」。 |
| **2/3 < b < 1** | **正异速生长 (positive allometry)** | 关节面比几何相似预期的**更大**，部分（但未完全）补偿应力上升。**真实哺乳动物数据通常落在 ~0.7–0.8**。 |
| **b < 2/3** | **负异速生长 (negative allometry)** | 关节相对更小，应力上升更快（现实中罕见）。 |

**补充要点**：即使 b < 1，大型动物仍可通过**改变姿态（把四肢摆得更直立 more upright / columnar limb posture）**来降低肌肉力与关节载荷 —— 这是大象、犀牛等的策略（"posture compensation"，Biewener 的经典结论）。

**对数变换的其他好处**（Q2 答题点）：
1. **线性化**幂律关系，可用最简单的线性回归；
2. 斜率直接就是**有生物学意义的缩放指数**；
3. **压缩量级跨度**（25→1000 kg 变成 1.40→3.00），避免长颈鹿这个巨大值成为**高杠杆点 (high-leverage outlier)** 主导回归；
4. **稳定方差 (variance stabilisation)**：生物测量的绝对误差通常随大小成比例增长，取对数后残差更接近同方差，回归假设更成立；
5. 让小体型物种（羊、狍）在图上不再挤成一团。

---

### （二）下午场：褶皱与断层分类对照表

#### 表 1：褶皱按**轴面产状**分类（Figure 5 左）

| 英文 | 中文 | 轴面倾角（参考区间） | 特征 |
|---|---|---|---|
| **Upright fold** | 直立褶皱 | 90°–80° | 轴面近乎垂直，两翼倾角对称 |
| **Inclined fold** | 倾斜褶皱 | 80°–30° | 轴面明显倾斜，两翼倾角不等 |
| **Overturned fold** | 倒转褶皱 | 轴面倾斜且**一翼被倒转** | 有一翼的地层**上下颠倒**（younging 方向朝下） |
| **Recumbent fold** | 平卧褶皱 | 10°–0°（近水平） | 轴面近乎水平 |
| （Vertical / reclined） | 直立轴 / 斜卧 | — | 更细的分类，二年级再深入 |

> 讲义 Exercise 2 解答给出的实测感：**直立背斜的轴面「may be 90° or at least dipping rather steeply」；平卧褶皱的轴面「shallow dip, close to horizontal」。**

#### 表 2：褶皱按**翼间角**分类（Figure 5 右；标准 Fleuty 1964 区间）

| 英文 | 中文 | 翼间角 | 直觉 |
|---|---|---|---|
| **Gentle** | 平缓 | 180°–120° | 几乎是平的，只是轻微起伏 |
| **Open** | 开阔 | 120°–70° | 明显的褶皱但两翼张得很开 |
| **Close** | 闭合 | 70°–30° | 两翼明显靠拢 |
| **Tight** | 紧闭 | 30°–10° | 两翼接近平行 |
| **Isoclinal** | 等斜 | 10°–0° | **两翼几乎完全平行**，强烈缩短 |

> Exercise 2 解答：一个「相对开阔 (relatively open)」的褶皱，翼间角可能是 **45–50°**（按上表其实落在 close 区间，讲义此处用词较宽松，答题时以数值 + 名称同时给出最稳妥）。

#### 表 3：褶皱按**年龄 vs 几何**的四象限组合

| | **核部最老岩石 → Anticline 背斜** | **核部最新岩石 → Syncline 向斜** |
|---|---|---|
| **向上闭合 → Antiform 背形** | **Anticlinal antiform**（最常见、"正常"） | Synclinal antiform（需地层先被倒转，罕见） |
| **向下闭合 → Synform 向形** | Anticlinal synform（需地层先被倒转，罕见） | **Synclinal synform**（最常见、"正常"） |

#### 表 4：褶皱按**倾伏 (plunge)** 分类与地图露头模式

| 类型 | 剖面 | 地图（平面）露头模式 |
|---|---|---|
| **Non-plunging anticline**（水平轴背斜） | 向上拱 | **平行条带**，**最老岩石在中央**，向两侧对称变新；条带**首尾开放不闭合** |
| **Non-plunging syncline**（水平轴向斜） | 向下凹 | **平行条带**，**最新岩石在中央**，向两侧对称变老 |
| **Plunging anticline**（倾伏背斜） | 轴倾斜 | 条带**闭合成 V / U 形的「鼻子 (nose)」**；**鼻尖指向倾伏方向**；核部可露出**更老得多**的岩石 |
| **Plunging syncline**（倾伏向斜） | 轴倾斜 | 条带闭合成鼻状，**鼻尖指向倾伏的反方向**（即向斜向倾伏方向张开） |

> 讲义 Figure 7 用「盒子模型 (box models)」同时展示剖面与平面视图，年龄序：黑色斑点（最老）→ 中灰 → 黄 → 白 → 浅灰（最新）。图片来源：J. Houghton (U. Leeds)。

#### 表 5：**轴迹 (axial trace) 的地图标注符号**

| 褶皱 | 两翼倾向 | 轴迹符号 | 记忆法 |
|---|---|---|---|
| **Antiform（背形）** | 两翼**背离**轴迹倾斜（dip **away** from the fold axis） | **菱形 (diamond) 符号**附在轴迹上 | 想成**三角形箭头指向远离褶皱轴的方向** |
| **Synform（向形）** | 两翼**朝向**轴迹倾斜（dip **towards** the fold axis） | **领结 (bow-tie) 符号**附在轴迹上 | 想成**三角形箭头指向褶皱轴** |

#### 表 6：**断层分类总表**（Anderson 1905/1951 + 几何 + 识别标志）

| 断层类型 | 中文 | 主应力配置 | 断层面倾角 | 上盘运动 | 年龄并置 (age juxtaposition) | 构造环境 | BGS 地图符号 |
|---|---|---|---|---|---|---|---|
| **Normal fault** | 正断层 | **σ1 垂直**；σ2、σ3 水平 | **陡，~60°** | **下降 (downthrown)** | **年轻岩石**贴靠 / 覆于**老岩石**上 | **伸展 (extension)**：裂谷、洋中脊、盆地 | 断层线上带**小刻痕 / 短横线 ("ticks")，画在下降的上盘一侧** |
| **Reverse fault** | 逆断层 | **σ1 水平**；**σ3 垂直** | 可陡（与正断层相似） | **上升** | **老岩石**被推到**年轻岩石之上** | **挤压 (compression)**：造山带、俯冲带 | 带**三角齿 (teeth) / 菱形符号**，画在**上盘一侧** |
| **Thrust fault** | 逆冲断层 | 同逆断层 | **缓，~30°（或更缓）** | **上升，位移量可极大** | **老岩石**推覆于**年轻岩石之上** | 强烈挤压、造山带前陆 | 同上（齿在上盘 / 上覆板片一侧） |
| **Strike-slip (left lateral / sinistral)** | 左行走滑断层 | **σ1 与 σ3 均水平；σ2 垂直** | **近直立** | 无明显上下盘 | 岩层**水平错断**，年龄无系统性上下关系 | **剪切 (shear)**：转换断层、走滑带 | 断层线两侧**成对半箭头**，指示相对运动 |
| **Strike-slip (right lateral / dextral)** | 右行走滑断层 | 同上 | 近直立 | — | 同上 | 同上 | 同上 |
| **Oblique-slip fault** | 斜滑断层 | 主应力斜交 | 变化 | 兼有升降与侧移 | 混合 | 斜向汇聚 / 离散 | 组合符号 |

> **Dip-slip（倾滑）= normal + reverse 的统称**，因为二者位移都有**强烈的垂直分量**。

#### 判读流程 A：**在地质图上识别并刻画褶皱**（可直接照做）

1. **找产状符号**：扫视地图上的 strike/dip 或 dip-direction 箭头，记下**倾角范围**与**倾向**。
2. **找条带的镜像对称**：若同一套岩层**在某条线两侧重复出现**且顺序颠倒（A-B-C-B-A），几乎必定是褶皱。
3. **画轴迹**：沿对称轴画一条线 —— 这就是**轴迹 (axial trace)**。
4. **定 antiform / synform**（靠倾向）：
   - 两翼**背离**轴迹倾斜 → **antiform**；
   - 两翼**朝向**轴迹倾斜 → **synform**。
5. **定 anticline / syncline**（靠年龄，查**地层柱 stratigraphic column / log**）：
   - 核部**最老** → **anticline**；
   - 核部**最新** → **syncline**。
6. **组合命名**：如 "synclinal synform"。
7. **判断是否倾伏 (plunging)**：
   - 条带在某端**闭合成鼻状** → 倾伏；
   - **沿轴迹方向倾角系统性变化** → 倾伏（若不倾伏，倾角沿轴向保持不变）；
   - 条带**始终平行、不闭合、倾角不变** → 近乎水平轴（non-plunging）。
8. **补充描述**：估计**翼间角**（gentle/open/close/tight/isoclinal）与**轴面产状**（upright/inclined/overturned/recumbent）。

#### 判读流程 B：**在地质图上识别断层类型**

1. **看线型符号**（BGS 图例，Figure 14）：ticks → 正断层；teeth → 逆冲 / 逆断层；成对半箭头 → 走滑断层。
2. **用符号确定上盘 / 下盘**：
   - **正断层的 ticks 画在下降的上盘一侧**；
   - **逆冲断层的齿画在上盘（上覆）一侧**。
3. **查地层柱定年龄**：读出断层两侧岩石单元的**相对年龄**。
4. **验证运动学**：
   - 上盘是**年轻**岩石、贴靠下盘的老岩石 → **正断层**（伸展）；
   - 上盘是**老**岩石、覆于下盘年轻岩石之上 → **逆 / 逆冲断层**（挤压）；
   - 两侧年龄无系统上下关系，但**标志层被水平错开** → **走滑断层**。
5. **量位移**：找一个**独特的标志层 (marker bed)**，量它在断层两侧被错开的距离。
6. **判走滑的左右行**：站在断层一侧向对面看，**对面向左移 = 左行 (sinistral)，向右移 = 右行 (dextral)**。
7. **反推应力场**：正断层 ⇒ σ1 垂直（伸展）；逆断层 ⇒ σ1 水平（挤压）；走滑 ⇒ σ2 垂直（剪切）。
8. **注意沿走向的变化**：同一条断层**可以沿走向改变性质**（Causey Pike Fault：西段逆冲、东段走滑）或**改变下降盘**（Coniston Fault：下降侧由北变南）。

---

## 四、课堂补充

### （一）上午场的组织与软件 / 模板使用提示

**分组与器材**
- **2–3 人一组**，每组**至少 1 台联网电脑**，每组需要**一副游标卡尺 (callipers)**。
- **标本一次只能拿一件回工位**（"Only one specimen should be taken to your workstation at a time"），保证大家轮流有得用。
- 每组每个任务需要测**每类各 1 件，共 8 根骨**；**需要和其他组协调借用标本**。
- **必须记录标本编号 (specimen number)**。

**标本清单（现场提供的实物数量）**

| 物种 | 数量 |
|---|---|
| 大绵羊 *Ovis aries* | 7 |
| 小绵羊 *Ovis aries* | 4 |
| 小牛 *Bos taurus* | 3 |
| 大牛 *Bos taurus* | 3 |
| 驼鹿 *Alces alces* | 2 |
| 马鹿 *Cervus elaphus* | 1 |
| 狍 *Capreolus capreolus* | 1 |
| 长颈鹿 *Giraffa camelopardalis* | 3 |

**幻灯片给出的标本编号对照表（Mu = 博物馆馆藏号）**

| Small sheep | Large sheep | Roe deer | Red deer | Small cattle | Large cattle | Moose | Giraffe |
|---|---|---|---|---|---|---|---|
| Mu037a | Mu036a | Mu026 | Mu501 | Mu554a | Mu084 | Mu196a | Mu101a |
| Mu037b | Mu036b | | | Mu554b | | Mu196b | Mu101b |
| Mu038a | Mu499 | | | Mu554c | | Mu196c | Mu101c |
| Mu038b | | | | Mu554d | | | |

**数据流（务必按顺序）**
1. 现场测量 → **填进 Blackboard 上链接的 Google 共享表格**（全班共用，便于汇总）；
2. **复制粘贴到自己电脑上的 Excel 模板** 做分析；
3. 图做好后 → **把图贴回 Google 表格的 "results" 标签页，标题改成本组队名**；
4. 全班一起讨论各组结果。

**软件提示（讲义明确警告）**
> **"we recommend you do not use the online version of excel as it lacks some functionality."**
> **不要用网页版 Excel**，因为它缺少数据透视表刷新、趋势线方程显示等功能。**必须用桌面版 Excel。**

**幻灯片给出的骨骼解剖定位（Slide 1）**
- 前肢自上而下：**Humerus（肱骨）→ Radius（桡骨）+ Ulna（尺骨）→ Metacarpal（掌骨）**
- 后肢自上而下：**Femur（股骨）→ Tibia（胫骨）→ Metatarsal（跖骨）**
- 掌骨自身分三段：**Proximal epiphyses（近端骨骺，与腕骨 hand bones 关节）— Shaft（骨干）— Distal epiphysis（远端骨骺，与指骨 fingers 关节）**
- 图片引用：**Doube et al., 2018**

### （二）Excel 模板的字段结构（逐格说明）

**Sheet "Task 1"（Metacarpal shape）**

- 抬头：`Team:` + `[Type team #]` + `[Type team members names]`，另有一个把两者拼接的显示单元格。
- **STEP 1 — 填测量表**：
  | 列 | 字段 | 说明 |
  |---|---|---|
  | A | **Group** | **下拉菜单**：Bovid / Cervid / Giraffid（数据验证列表，**必须用下拉选，不要手打**，否则透视表分组会出错） |
  | B | **Common name** | 已预填 13 行 |
  | C | **Species** | 已预填学名 |
  | D | **Specimen number** | 自己填 Mu 编号；文献行预填 "From Rios et al." |
  | E | **Length (mm)** | 自己测的 L |
  | F | **Breadth (mm)** | 自己测的 B |
- **预填的 13 行**（前 8 行是实测，后 5 行是文献 / 已给）：
  Small sheep、Large sheep、Roe deer、Red deer、Moose、Small cattle、Large cattle、Giraffe（以上 8 行**要自己测**）；
  Giraffe 2 (*Giraffa camelopardalis* B)、Forest Giraffe (*Okapia johnstoni*)、Bohlinia (extinct)、Paleotragus (extinct)、**Canthumeryx (extinct) —— 已作为示例填好 Group=Giraffid, L=270, B=19.1**（这一行是**填法范例**）。
  > 注意：Rios 表里的 *Giraffa camelopardalis* (694 / 45.1) 对应模板的 **"Giraffe 2"** 行，而 **"Giraffe"** 行留给**实验室实测的长颈鹿标本**。**两者不要混填、也不要重复。**
- **STEP 2 — 刷新汇总表**：右侧是一张**数据透视表 (PivotTable)**。
  - 行 = Common name；列 = Group（Bovid / Cervid / Giraffid / (blank)）；值 = **Sum of Length (mm)** 与 **Sum of Breadth (mm)**。
  - 因为每个 Common name 只有一行数据，**"Sum" 实际上就是该标本的原值**。
  - 若 Group 列留空，数据会掉进 **"(blank)" 列**——这是检查有没有漏选分组的最快方法。
  - **刷新方法**：点击蓝灰色横幅内任一单元格 → 顶部 **"PivotTable Analyze"** 选项卡 → **Refresh** 下方箭头 → **Refresh All**。
- **STEP 3 — 看散点图与三组线性拟合**：刷新后散点图会自动填充。图下方有 Group 图例（Bovid / Cervid / Giraffid）。
  - 随图给出的思考题（与讲义 Q3 相同）："How does the slope and intercept vary between these three groups? What might this mean for how their shape changes as they increase in size? What are the biomechanical implications?"
  - **把图复制粘贴到 Google 表格。**

**Sheet "Task 2"（Joint scaling）**

- **STEP 1 — 填测量表**（左侧）：
  | 列 | 字段 | 说明 |
  |---|---|---|
  | A | **Group** | Bovid / Cervid / Giraffid（Task 2 的说明写的是「enter」而非下拉，但仍要与 Task 1 一致） |
  | B | **Common name** | 8 行预填（无文献化石行） |
  | C | **Species** | 预填 |
  | D | **Specimen number** | 自己填 |
  | E | **Width (mm)** | 远端骨骺内–外侧宽 W |
  | F | **Diameter (mm)** | 远端骨骺前–后向直径 D |
  | G | **Mass (kg)** | **已预填，取自文献，不要改** |
  | H | **Area (mm²)** | **自动计算**（`=E×F×PI()/2`）。**W、D 未填时显示 0**，这是正常的初始状态。 |
- **STEP 2** — 画 **Area vs Mass** 散点图并分析："How does joint area change as size increases? Why is this?"
- **STEP 3 — 对数变换表**（右侧）：
  | 列 | 字段 | 说明 |
  |---|---|---|
  | J | **Log10 mass** | `=LOG10(G)`，**示例已给在 I15 附近：LOG10(25) = 1.3979400086720377** |
  | K | **Log10 area** | `=LOG10(H)` |
  > **陷阱**：`LOG10(0)` 会返回 `#NUM!`。必须先把 W、D 填完让 Area 算出非零值，再做对数变换。
- **STEP 4** — 画 **log₁₀(Area) vs log₁₀(Mass)** 散点图 + 回归线 + 显示方程，回答："What impact does log-transforming the data have and why might it be useful？What is the slope of your regression? What does that tell you about how joint area scales?" 然后**把图贴回 Google 表格**。

### （三）Excel 操作附录（讲义 APPENDIX，逐条照抄 + 说明）

**刷新汇总表（Task 1）**
1. 点击表格（蓝灰色横幅）内任一单元格；
2. 选 **"PivotTable Analyze"**；
3. 点 **"Refresh"** 下面的箭头；
4. 选 **"Refresh All"**；
5. 之后散点图会自动填入数据。

**画散点图**
1. 选中感兴趣的 **x 列与 y 列**；
2. 点 **"Insert" → 散点图**（底排那个只有点的图标）。

**加回归 / 趋势线**
1. 点某个数据点选中整个系列 → **右键 → "Add Trendline"**；
2. 选 **Linear（线性）**，勾选 **"Display Equation on chart"**（另外勾 "Display R-squared value on chart" 才能读到 r²）。

**给不同组画各自的线（分组系列）**
1. 全选数据 → **Data → Sort**；
2. **按 Group 列排序**（bovid / cervid / giraffid 各自聚在一起）；
3. 选中图表 → **Design → "Select Data"**；
4. 左框 → **"Add series"**，为每一组各加一个系列；
5. 每个系列选中该组对应的数据区域（例：bovids）；
6. 图上就有多条系列了；
7. 再按前述方法**给每条系列分别加趋势线**。

### （四）下午场的课堂组织与器材

- **橡皮泥 (modelling clay)**：现场提供，用来做**至少两层、最好三层**的三维褶皱模型，**自己指定哪种颜色代表最老、哪种代表最新**。
- **学生证 / 薄塑料片**：用来**「削」掉模型顶层**，模拟**剥蚀 (erosion)**，从而看到褶皱在**平面图 (map view)** 上的露头模式。不确定怎么切要**问助教 (demonstrator)**。
- **BGS 实体地质图**：Pembrokeshire 图幅、**Keswick 图幅**（课堂发实体印刷版；在线也可在 **BGS map portal** 查：`https://www.bgs.ac.uk/information-hub/bgs-maps-portal/`）。
- **野外照片**（Exercise 5 素描用）：
  - **Figure 12**：秘鲁 Morro Solar，**下白垩统 La Herradura Formation**（Wiki Commons）；
  - **Figure 13**：美国犹他州 **Ketobe's Knob**，**侏罗系 Curtis 与 Entrada Formations**（Elaine Martin, 2008）。
- **本堂课会在下课前全班一起讲 Exercise 4 的剖面题**（"We will go through this exercise as a class before the end of the lesson today"）。

---

## 五、Practical 要点

### （一）上午场：Comparative Morphology Practical

#### 【目的 / ILOs（讲义原文的三条学习目标）】
1. **认得**多种偶蹄类物种的**掌骨形态**；
2. **采集、描述并报告**骨骼标本的形态学数据，并在 **Excel 中做回归分析**；
3. **定量比较**物种间掌骨形态的差异，并讨论其**生物力学与演化意义**。

#### 【总体方法链】
```
选标本(记编号) → 卡尺测量 → 录入 Google 共享表 → 复制到桌面 Excel 模板
   → 刷新数据透视表 → 分组散点图 + 线性回归 → 读 slope / intercept / r²
   → (Task 2 额外) 算面积 → log10 变换 → log-log 回归读缩放指数
   → 把图贴回 Google 表 results 页(署队名) → 全班讨论
```

---

#### 【Task 1：Metacarpal Shape（掌骨形状）】

**A. Specimen examination（标本观察）**
- 拿一根掌骨，**观察形态并记录特征**：注意区分 **近端骨骺（与腕骨关节，较宽、关节面复杂）— 骨干 shaft — 远端骨骺（与指骨关节，呈双滑车 double condyle 状）**。
- **中缝**：融合的第三 / 第四掌骨，在**背侧 (dorsal) 常保留一条纵向沟槽**，远端末端裂成**两个滑车 (condyles)** —— 这是识别偶蹄类炮骨的最直观特征。

**Q1: Describe how the metacarpal bones function in the artiodactyl hand.**（参考答案要点）
- 掌骨是**腕骨 (carpals) 与指骨 (phalanges) 之间的力学传递构件**：站立与运动时把地面反作用力沿肢体轴向上传递。
- 第三 + 第四掌骨**愈合成一根 cannon bone**，形成一根**刚性支柱 (rigid strut)**，抗弯抗扭能力强于两根分离的骨。
- 愈合**取消了掌骨之间的相对运动**，把肢体的活动**限制在矢状面内**（前后摆动），提高奔跑效率、降低侧向失稳。
- 掌骨的**延长使肢体远端加长**，增加**步幅 (stride length)** 与**摆动速度**（长 out-lever）。
- 同时，**肌肉大多退居肢体近端**，远端只剩肌腱 —— 远端质量小，**摆动惯量 (moment of inertia) 低**，摆腿更省能量。
- 远端骨骺的**双滑车关节**限制指骨只能做屈伸，进一步稳定步态。

**Q2: 定义 Cervidae / Bovidae / Giraffidae**（需自行上网查；参考答案见本笔记第二节「三大类群」表）。
- 答题时要素：**分类地位（均属反刍亚目 Ruminantia）+ 代表属种 + 头饰类型（antlers / horns / ossicones）+ 生态分布**。

**B. Data Collection（数据采集）**
- 对**鹿科、牛科、长颈鹿科**的标本测量：
  - **L = maximum length（最大长度）**
  - **B = midshaft breadth（骨干中段宽度）**
- **长颈鹿科**：除了实测实验室标本，**还要把 Rios et al. (2016) 表格中的 5 组数值一并加入**（见第三节表）。
- 录入 Google 共享表 → **复制到自己电脑的 Excel 模板**。

**C. Data analysis（数据分析）**
1. **画 B（y）vs L（x）散点图**，**bovid / cervid / giraffid 各成一个独立系列**（用附录的「Select Data → Add series」方法）。
2. **给三组各加线性趋势线**，**显示斜率、截距与 r²**。
3. **图表标题改成本组队名**，复制到 Google 表 results 页。

**Q3: How does the slope and intercept vary between these three groups? What might this mean for how their shape changes as they increase in size? What are the biomechanical implications?**（参考答案框架）

- **数值层面**：先把三组的 `m`、`c`、`r²` 列成表对比。
- **预期模式**：
  - **Giraffidae**：L 跨度最大（270–694 mm），**斜率最低**（本笔记算得 ~0.06），B/L 仅 6.5–7.3 % —— **最细长 (most gracile)**。
  - **Bovidae**（羊、牛）：L 较短但 B 相对大，**斜率与截距较高** —— **最稳健 (most robust)**，因为牛是重型承重体型。
  - **Cervidae**（狍、马鹿、驼鹿）：**居中**，偏细长（鹿是典型的奔跑型 cursorial 动物）。
- **形状随体型变化的含义**：
  - **斜率低**表示「变长时几乎不变粗」→ 随体型增大骨骼**相对越来越细长**（负异速），细长化换取速度与步幅。
  - **斜率高**表示「一边变长一边同步加粗」→ 保持甚至提高稳健度，优先承重与抗折。
  - **截距高**表示在**同等长度**下整体更粗 —— 是一种「基线稳健度」的差异。
- **生物力学含义**：
  - 细长骨干 = 长 out-lever = **高速档 (high gear ratio)**，利于快跑，但**弯曲应力大、抗折安全系数低**，需要严格的**矢状面运动约束**与**直立姿态**来把载荷变成轴向压缩而非弯曲。
  - 粗壮骨干 = **抗弯裕度大、承重能力强**，适合大体重、低速、需要负载稳定的类型（牛）。
  - 长颈鹿的极端延长（694 mm）主要服务于**取食高度 (browsing height)** 与身体整体比例，而非纯粹的速度；它靠**极强的矢状面约束和几乎垂直的柱状肢姿**来控制弯曲应力。
  - **霍加狓的 B/L 最高（9.35 %）**是有力反例：森林生境、机动转向多于持续奔跑 → 更粗壮的掌骨。
- **演化解读**：把点画在 **Rios 的化石序列**上（*Canthumeryx* → *Palaeotragus* → *Bohlinia* → *Giraffa*），可以看出长颈鹿科的掌骨**在演化中持续延长而 B/L 比大体守恒** —— 这是「等比放大 + 延长」而非「单纯细化」的路径。

---

#### 【Task 2：Joint Scaling（关节缩放）】

**背景假设（讲义原文）**
- 四足动物**约 2/3 体重由前肢承担** ⇒ 前肢关节面积应**正比于体重**，以限制**关节软骨上的应力**。
- 检验方法：估算**掌骨远端骨骺关节面的面积**，对**文献体重**作图。

**A. Data collection**
1. 测**远端骨骺 (distal epiphysis)** 的：
   - **W = medio-lateral width（内–外侧宽度）**
   - **D = anterior-posterior diameter（前–后向直径）**
2. 录入 Google 表；
3. 用公式算关节面积（Google 表 / Excel 模板自动算）：
   ```
   Area = W × D × π ÷ 2
   ```
   —— 因为远端关节面**近似半个圆柱 (half of a cylinder)**。
4. 复制到自己电脑的 Excel 模板。

**B. Data Analysis**
1. **画 Area（y）vs Mass（x）散点图**（未变换）。
2. **对 mass 与 area 都做 log₁₀ 变换**（`=log10(x)`）。
3. **画 log Area vs log Mass 散点图 + 线性回归 + 显示方程**。
4. 标题改队名，贴回 Google 表。

**Q1: How does joint area change as size increases? Why is this?**（参考答案）
- 关节面积**随体重增大而增大**，这是承重需求的直接结果；
- 但在未变换的图上，点呈**凹向下的曲线 (concave-down)** 而非直线：面积增长**慢于**体重增长；
- 力学原因：**面积是二维量（∝ L²），质量是三维量（∝ L³）**。几何相似下 `Area ∝ Mass^(2/3)`。
- 因此**如果形状不变，大动物的关节应力必然更高**（应力 ∝ Mass^(1/3)）—— 这就是所谓的「**体型的力学惩罚**」。
- 真实动物往往表现出**轻微正异速（斜率 > 2/3）** + **姿态代偿（更直立的柱状肢）**来部分抵消这个惩罚。

**Q2: What impact does log-transforming the data have and why might it be useful?**（参考答案）
- **把幂律曲线拉直**，可用线性回归；
- **斜率直接读作缩放指数 b**（有明确的生物学解释）；
- **压缩 40 倍的体重跨度**（25→1000 kg 变成 1.40→3.00），使小型物种不再挤在原点附近、长颈鹿不再是主导回归的高杠杆点；
- **稳定方差**，使残差更接近同方差，满足最小二乘回归的假设；
- 便于与文献中的缩放指数**直接对比**（异速生长文献几乎全用 log-log）。

**Q3: What is the slope of your regression? What does that tell you about how joint area scales?**（参考答案）
- 报出实测斜率 b 与 r²，再对照三条基准：
  - **b ≈ 0.67**：**几何相似 (isometry)**，形状不变，**应力随体型上升**；
  - **b ≈ 1**：**应力恒定**（讲义 Hint 所指的「关系不随体型改变」）；
  - **0.67 < b < 1**：**正异速**，关节比几何相似预期更大，**部分补偿**应力上升 —— 这是哺乳动物数据最常见的结果（~0.7–0.8）；
  - **b < 0.67**：负异速，应力上升更快。
- 结论句式模板：「本组测得斜率 b = ___（r² = ___）。该值 大于 / 接近 / 小于 2/3，说明关节面积随体重呈 正异速 / 等比 / 负异速 缩放，即大型物种的关节面积 比 / 恰好符合 / 不及 单纯几何放大的预期，因此关节软骨应力随体型 缓慢上升 / 保持不变 / 快速上升；大型物种还可通过更直立的肢体姿态进一步降低载荷。」

---

### （二）下午场：Folds and Faults on Geological Maps（逐题梳理，含解答）

#### 【Exercise 1 — Strike, dip, and dip direction】

**(a) 在罗盘盘面上画走向线**

| 题目 | 解答 | 原理 |
|---|---|---|
| 走向 075 的地层，另一个可接受读数是？ | **255**（= 075 + 180） | 走向线是一条直线，**两端方位角相差 180°**，两个读数都对 |
| 走向 160 的地层，另一个可接受读数是？ | **340**（= 160 + 180） | 同上 |

> 解答原文：黑箭头 = 075，红箭头 = 255；虚线箭头 = 160，蓝箭头 = 340。

**(b) strike/dip → dip and dip direction 的换算**

| 题目 | 解答 | 计算 | 检查 |
|---|---|---|---|
| **085/40SE** | **40/175** | **strike + 90°** = 085 + 90 = 175 | 175° 在罗盘上确实指向**东南 (SE)** ✓ |
| **085/40NW** | **40/355** | **strike + 270°** = 085 + 270 = 355 | 355° 在罗盘上确实指向**西北 (NW)** ✓ |

**方法论（务必记住）**：
- 倾向必然**垂直于走向**，所以只有 **strike + 90°** 和 **strike + 270°** 两个候选；
- **用题目给的象限字母（SE / NW / N / S…）在罗盘上验证到底该选哪一个**，不能靠死记。

**(c) Pembrokeshire BGS 图幅（Figure 2）的产状描述**

**解答原文要点**：
- **倾角范围很宽**：从**直立与极陡（>70°）**到**中等但仍偏陡（30–55°）**；
- **倾向在图上多次变化**，但绝大多数地层**大致向北或向南倾**；
- **图下半部的地层向北倾（似乎是向内倾）**；**图上半部的地层向南倾**；
- **多数地层的走向大致东–西向**；
- **附加分**：如果你能由此**推断这是一个褶皱构造 (folded structure)** —— 因为「上半部向南倾 + 下半部向北倾 + 走向一致东西向」＝ 地层向中间的一条东西向轴线**相向倾斜**，这正是**向形 (synform)** 的定义。

> **图例提醒（Figure 2 说明）**：图上的箭头是 **dip and dip direction** 记法，**箭头指向下倾方向 (downdip direction)**。

---

#### 【Exercise 2 — Getting Familiar With Folds（橡皮泥建模）】

**操作步骤**
1. 用橡皮泥做**至少 2 层、最好 3 层**的**水平地层**模型；
2. **自己指定颜色的年龄顺序**（哪个最老、哪个最新）；
3. 小组内**把平层弯折成各种褶皱**。

**第一步：做一个 anticlinal antiform（背斜背形）**
- 画出草图并标注：**Limbs（两翼）、fold hinge（枢纽）、younging direction（变新方向）、axial plane（轴面）**；
- **估计翼间角与轴面倾角**。

**解答（Figure 6 上图，直立背斜背形）**
- **轴面倾角：90°，或至少是很陡的倾角**；
- 若褶皱相对**开阔 (open)**，**翼间角可能相当大，例如 45–50°**；
- 变新方向：**两翼的 Y 形符号都指向远离核部的方向**（因为核部是最老的岩石）。

**第二步：把它改造成 isoclinal（等斜）+ recumbent（平卧）**
- 用文字描述并画第二张草图，说明**轴面倾角与翼间角如何变化**。

**解答（Figure 6 下图，平卧等斜褶皱）**
- **平卧褶皱的轴面倾角很小、接近水平**；
- **若同时是等斜的，翼间角也很小，约 10–20°**（两翼几乎平行）。
- **对比要点**：从直立开阔褶皱到平卧等斜褶皱，**轴面从 ~90° 转到 ~0–10°（旋转了近 90°）**，**翼间角从 ~45–50° 收缩到 ~10–20°（强烈缩短）**。
- 两张草图的**虚线**代表**轴面**。

> **答题坑**：解答原文写「if the fold is also isoclinal, the dip angle will be low, ~10-20°」，此处的 "dip angle" 指的是**翼间角**（严格的 isoclinal 定义是翼间角 0–10°）。**答卷时最稳妥的写法是同时给出名称和数值**：「轴面倾角 ~0–10°（recumbent）；翼间角 ~10–20°（tight to isoclinal）」。

---

#### 【Exercise 3 — Visualising Folds on a Geological Map（从三维到平面）】

**核心问题**：褶皱在**从上往下看的地图**上长什么样？

**推理链**
1. 刚做好的背斜背形，**从上往下看只能看到最年轻的那一层**，根本看不出有褶皱；
2. 现实中，**剥蚀 (erosion) 是把不同深度的基岩暴露出来的强大营力**；
3. 用**学生证 / 薄塑料片把模型顶层削掉**，模拟剥蚀；
4. 再从上往下看 → 出现**平行的岩石条带，从褶皱轴向两侧重复对称出现**（Figure 7）。

**露头模式规律（Figure 7）**
- **背斜 (anticline)**：**较老的岩石出现在构造中央**，向两侧越来越新（剥蚀越深，中央露出的岩石越老）—— Figure 7a；
- **向斜 (syncline)**：**反过来，最年轻的岩石在中央**，向两侧越来越老 —— Figure 7b；
- **倾伏褶皱 (plunging fold)**：把模型**倾斜一下让褶皱轴不再水平**再削顶 —— 露头模式**改变**：条带**闭合成鼻状**。
  - **Plunge（倾伏 / 倾没）的定义：褶皱轴的倾角。**
  - 关键区别（对比 Figure 7a 与 7c）：**如果褶皱倾伏，构造中央可以露出老得多的岩石。**
  - 讲义坦承这部分**很难在脑中想象**，**二年级会更深入学**；一年级只要求**知道褶皱会倾伏、且倾伏会改变露头模式**。

**本练习末尾的地图判读题：回到 Figure 2（Pembrokeshire）**
> 若蓝色单元 "d2" 是最年轻的，结合倾向，判断这是 synform 还是 antiform？syncline 还是 anticline？能否判断是否倾伏？

**解答原文**：
- **核部最年轻 ⇒ syncline（向斜）**；
- **两翼向内倾斜 (dipping inward) ⇒ synform（向形）**；
- **合起来：这是一个 synclinal synform（向斜向形）**；
- **倾伏难以判断 (Plunge is hard to assess)**：
  - 各层**大体平行**，只有最西端例外；
  - 褶皱**可能向西闭合**，但在这一小块视野里**证据不足、结论模糊**；
  - **倾角沿轴向没有变化 —— 如果褶皱倾伏，倾角会沿褶皱轴变化。**（这是判断倾伏与否的关键判据，务必记牢。）

---

#### 【Exercise 4 — Axial Traces（轴迹）】

**题目**：Figure 8 是一张平面草图，画了几个褶皱构造，四个岩石单元从**最老 (1) 到最新 (4)**。要求：**识别出三个褶皱构造，并标出它们的轴迹 (axial trace)**。

**定义**：**轴迹**是把**褶皱轴投影到地图平面上**得到的线，**平行于褶皱轴**。

**标注符号规则（务必记牢）**

| 构造 | 两翼倾向 | 符号 | 助记 |
|---|---|---|---|
| **Antiform（背形）** | **背离**褶皱轴倾斜 (dip **away** from the fold axis) | **菱形 (diamond)** 符号 | 三角形箭头**朝外**指 |
| **Synform（向形）** | **朝向**褶皱轴倾斜 (dip **towards** the fold axis) | **领结 (bow-tie)** 符号 | 三角形箭头**朝内**指 |

**问：这三个构造各是 syncline 还是 anticline？**

**解答原文**：
> **从西到东依次为：syncline（核部最年轻）— anticline（核部最老）— syncline。**

**问：它们同时也是 synform / antiform 吗？**

**解答原文**：
> **由于缺少倾向信息，无法确定**它们是否同时是 synform / antiform。

**追问：哪种更可能？如何判断？**
- 方法：**沿 Figure 8 的一条西–东线画一张剖面草图 (sketch cross section)**；
- **从中央的单元 1（最老）出发**，判断两侧单元 2 的地层是**向内倾**还是**向外倾**；
- **两种解都在几何上成立，但其中一种在地质上更可能**：
  - **解 A（更可能 / 常规解）**：中央 anticline 的两翼**向外倾** ⇒ 它是 **antiform**，对应地两侧的 syncline 就是 **synform**。这是**未经倒转的正常褶皱组合（anticlinal antiform + synclinal synform）**，只需要一期简单的水平缩短即可形成。
  - **解 B（几何可行但地质上少见）**：中央 anticline 的两翼**向内倾** ⇒ 它是 **synform（anticlinal synform）**。这要求**地层在此次褶皱之前已经被倒转**（例如更早期的一次平卧 / 倒转褶皱作用），属于**多期变形 (polyphase deformation)** 的产物，在这样一张简单草图中出现的概率低得多。
- **讲义明确说明这道题会在下课前全班一起讲。**

**答题模板**：「若无倾向数据，只能靠年龄判定 syncline / anticline；synform / antiform 的判定必须要有倾向。默认（单期简单缩短）情形下，anticline = antiform、syncline = synform；只有在存在早期倒转的多期变形区，二者才会脱钩。」

---

#### 【Exercise 5 — Field Sketches of Faulted Rocks（野外照片素描）】

**两张照片**
| 图 | 地点 | 岩性与时代 |
|---|---|---|
| **Figure 12** | 秘鲁 Morro Solar | **下白垩统 La Herradura Formation**，沉积岩 |
| **Figure 13** | 美国犹他州 **Ketobe's Knob** | **侏罗系 Curtis 与 Entrada Formations**，沉积岩 |

**素描必须包含的要素（讲义给出的完整清单）**
1. **Bedding（层理）**：**先找层理**，尤其是「**competent（能干的 / 坚硬的）**」岩层 —— 它们是最好的**标志层**；
2. 用这些层来标出**跨断层的位移方向与位移量 (displacement direction and magnitude)**；
3. 注意是否有**岩性变化 (variation in rock type)**，以及**不同岩石在断层带中的表现是否不同**（能干层脆性断裂、不能干层塑性拖曳）；
4. 找出**断层面 (fault plane) 的位置**；
5. 标注断层面的**走向与倾角 (orientation and dip angle)**；
6. **必须画比例尺 (scale)** —— **两张照片里都有人可作参照物**；
7. 标注 **footwall（下盘）**、**hanging wall（上盘）**；
8. 标注**三个主应力 (σ1, σ2, σ3) 的方向**。

**解答原文**
- **第一张（秘鲁）：正断层 (normal fault)，倾角陡 (steep dip)。**
  - 推理：陡倾断层面 + 上盘相对下降 + 年轻岩层被降到与老岩层并置。
  - 应力：**σ1 垂直、σ3 水平**（伸展）。
- **第二张（犹他）：逆冲断层 (thrust)，倾角缓 (shallow dip)。**
  - 推理：缓倾断层面 + 上盘上冲 + 老岩层被推到年轻岩层之上。
  - 应力：**σ1 水平、σ3 垂直**（挤压）。
- **解答附注**：第二张图里其实还有很多细节可看 —— 若学生有余力，可以指出 **fault splays（断层分支 / 分叉）、ramps（断坡）**；但讲义承认这些**在讲座里还没充分讲到**，属于加分内容。

> **概念补充（帮助理解 splay / ramp）**：逆冲断层常沿软弱层做水平的 **flat（断坪）**，再切穿能干层爬升形成 **ramp（断坡）**，形成阶梯状的 **ramp-flat 几何**；主断层向前端分岔出的次级断层叫 **splay**。

---

#### 【Exercise 6 — Faults on the Keswick Map（BGS Keswick 图幅）】

**前置知识**
- **BGS 地图用不同线型表示不同断层类型（Figure 14）**；
- 这些符号最重要的作用是：**指示跨断层 / 沿断层的位移方向**，从而帮我们**判断哪一侧是上盘、哪一侧是下盘**；
- 再结合**岩石颜色（岩性单元）**及其**相对年龄（查地图上的地层柱 stratigraphic section）**，就能理解为什么某条断层被标为正 / 逆冲 / 走滑。
- 地图来源：课堂发放**印刷版**；也可在 **BGS map portal** 在线查阅。

**任务**：在 Keswick 图幅上找出三条断层 —— **Causey Pike Fault**、**Derwent Water Fault**（两条都在图幅中央附近）、**Coniston Fault**（图幅中下部），判断类型并**用地图上的地质证据（如地层年龄）加以论证**。

---

**1. Causey Pike Fault —— 逆冲断层（西段）+ 走滑断层（东段）**

**解答原文梳理**：
- **西段（along the western parts of its outcrop）：thrust fault（逆冲断层）**；
- **东段（in the eastern part of the map）：已转变为 strike-slip fault（走滑断层）**；
- **判读依据（逐步）**：
  1. **断层线上的菱形 / 三角齿符号 ("teeth")** 画在**上盘 (hanging wall) 一侧**；
  2. **用齿的位置确定上盘**；
  3. **用地层柱确定两侧岩石的年龄关系 (age juxtaposition)**；
  4. 结果应能显示：**老岩石被推覆到年轻岩石之上** —— 这正是逆冲断层的判据；
  5. 具体单元：**奥陶系 Kirkstile Formation (KSt) 位于上盘**，**Buttermere Formation (BUF) 位于下盘**。
- **东段的困难**：这两个组在东段**又彼此相邻**，但**水平位移量难以可靠判读**。

> **⚠️ 材料内部措辞不一致（重要）**：解答原文一方面说「You should be able to show **older rocks have been placed on top of younger**」，另一方面又写「Kirkstile Formation (KSt) are in the hanging wall, i.e. on top of **the older** Buttermere Formation (BUF) in the footwall」——**两句里 KSt 与 BUF 的新老关系互相矛盾**。
> **答题时应抓住不会错的原则**：**逆冲断层 = 上盘（带齿一侧）把较老的岩石推到较新的岩石之上**；具体哪个组更老，**以考场地图上的地层柱为准**，不要背这段解答的字面。

---

**2. Derwent Water Fault —— 走滑断层 (strike-slip fault)**

**解答原文梳理**：
- **类型：strike-slip fault**；
- **判读依据：断层线上的箭头符号指示运动方向 (the arrows show the sense of movement)**；
- **进一步要求**：
  - 判断它是**左行 (left lateral)** 还是**右行 (right lateral)**；
  - **估算位移量**；
- **难点提示**：位移不好看 —— **最好的证据是断层南端附近那个橙色的 "vs" 岩石单元**（用它作为**被错断的标志层 marker**，量它在断层两侧的错开距离）。

---

**3. Coniston Fault —— 正断层 (normal fault)**

**解答原文梳理**：
- **类型：normal fault**；
- **判读依据：小的「刻痕 (tick)」符号画在断层面的下降上盘一侧 (on the downthrown hanging wall side)**；
- **地质验证**：找出**年轻岩石被向下错动、从而与下盘的老岩石并置**的实例；
- **难点提示**：**这条断层比较复杂 —— 沿断层走向从北到南，下降的一侧会发生变化！**（即断层的**下降盘由一侧转到另一侧**，说明位移沿走向不是恒定的，可能存在**铰接 (hinge) 或位移零点**。）

---

#### 【Bonus Question — Pembroke 地质图草图】

**题目**：Figure X 是 Pembroke 地质图的一部分草图。
1. 结合**倾向**与**地层柱 (stratigraphic log) 给出的岩石年龄**，**识别大尺度褶皱构造**，并**画出它们的轴迹**；
2. 图上有许多**近南–北走向、用粗黑线画的断层**，评估其**位移方向与位移量**。
   - **提示：主要位移是水平的，不是垂直的。**

**解答原文**：
> 这些断层**大多是右行 (right lateral / dextral)**，**位移量约 100–300 m**；**也能找到一些左行的**；**可能还有倾滑分量 (dip-slip component)**。

**方法要点**：
- 由「主要位移是水平的」+「近直立的粗黑线」⇒ 判定为**走滑断层**；
- 位移量的量法：**在断层两侧找同一岩性界线（标志层）在图上被错开的水平距离，用图幅比例尺换算**；
- 左行 / 右行的判法：**站在断层一侧向对面看，对面向右移 = 右行**；在地图上等价于「**对面的地质界线相对于己方向右偏移**」。
- 若同一条断层两侧的地层界线**既有水平错断也有露头宽度 / 年龄的变化**，说明**存在倾滑分量（斜滑 oblique-slip）**。

---

## 六、易错点 / 重点难点

### （一）上午场

| # | 易错点 | 正确做法 |
|---|---|---|
| 1 | **混淆 metacarpal（掌骨）与 metatarsal（跖骨）** | **metacarpal = 前肢**（在 humerus–radius/ulna 之下），**metatarsal = 后肢**（在 femur–tibia 之下）。偶蹄类的**跖骨通常更长、横截面更接近方 / 圆**；掌骨相对更短、**背–掌向更扁**。拿错骨会让整个 Task 2 的「2/3 体重在前肢」假设失效。 |
| 2 | **不记标本编号** | 讲义反复强调「Please note down the specimen number」。**每一行数据都必须有 Mu 编号**，否则出现异常值时无法回溯复测。 |
| 3 | **midshaft breadth 不在中段量** | **B 必须在骨干的正中段量**，不是随手挑一处。骨干宽度沿轴向变化很大（两端骨骺处最宽），量错位置会系统性抬高 B。 |
| 4 | **卡尺未归零 / 读数单位错** | 每次测量前**合拢卡尺检查读数为 0.00**；**统一用 mm**（模板列名就是 mm）。有人用 cm 会让斜率差 10 倍。 |
| 5 | **L 不是「最大长度」** | **maximum length** 是骨两端**最远两点之间**的距离，卡尺要略微转动找最大值，而不是随便夹住两端。 |
| 6 | **Excel 模板中 Group 列手打而非用下拉菜单** | Task 1 的 Group 列是**数据验证下拉菜单**。手打（大小写、空格、拼写差异）会让**数据透视表把数据丢进 "(blank)" 列**，散点图就画不出来。**看到 "(blank)" 列有数字 = 有行没选组。** |
| 7 | **把 Rios 文献的长颈鹿数据和实测长颈鹿数据混填 / 重复计入** | 模板里 **"Giraffe" 行 = 你实测的实验室标本**；**"Giraffe 2" 行 = Rios 表里的 *Giraffa camelopardalis* (694 / 45.1)**。**不要重复录入同一个数值。** |
| 8 | **忘记刷新数据透视表** | 填完数据必须 **PivotTable Analyze → Refresh → Refresh All**，否则汇总表与图表都不会更新，你会以为「模板坏了」。 |
| 9 | **用网页版 Excel** | 讲义明确警告网页版**缺功能**。**必须用桌面版**（趋势线方程、r² 显示、透视表刷新等）。 |
| 10 | **只画一条总回归线，没有按组分开** | Task 1 的核心就是**比较三组的斜率与截距**。必须用「Data → Sort（按 Group）→ Select Data → Add series」为**三组各建一个系列**，再各加趋势线。**一条总线会掩盖组间差异。** |
| 11 | **`LOG10(0)` 报 `#NUM!`** | Area 列在 W、D 未填时显示 **0**。**必须先填完 W、D**，Area 算出非零值后再做对数变换。 |
| 12 | **搞混 `log Area vs log Mass` 的斜率基准** | **几何相似（等比）= 2/3 ≈ 0.67**，**应力恒定 = 1**。**别把 1 当成 isometry**。讲义 Hint 说「slope of one 表示关系不随缩放改变」，指的是**面积与质量的比值不变（应力恒定）**，不是几何相似。答题时**两个基准都要提到**。 |
| 13 | **过度解读截距** | B–L 回归的截距对应 L = 0，**没有生物学意义**，只能用于**组间相对比较**，不可外推。 |
| 14 | **忽略样本量与体型混杂** | 每组每类只测 1 件（n = 1 / 物种），**r² 很容易被少数极端点（长颈鹿）拉高**。讨论时要**声明样本量小、结论是探索性的**。 |
| 15 | **忘了改图表标题为队名 / 忘了贴回 Google 表** | 讲义两个 Task 都明确要求：**标题改成本组队名 + 复制到 results 标签页**，这是课堂讨论的前提。 |
| 16 | **一次拿多件标本** | 明确规定**一次只拿一件回工位**，否则别组无标本可测。 |

### （二）下午场

| # | 易错点 | 正确做法 |
|---|---|---|
| 1 | **Antiform/Synform 与 Anticline/Syncline 混用** | **antiform/synform 是纯几何（闭合方向）；anticline/syncline 靠年龄（核部新老）**。没有年龄信息**只能**说 antiform/synform；没有倾向信息**只能**说 anticline/syncline。**Exercise 4 就是专门考这一点。** |
| 2 | **走向只写两位数或不带方向** | 走向**必须写成三位数**（075，不是 75）；**倾角必须带象限**（145/50 **SW**）以消除歧义。 |
| 3 | **dip direction 加 90 还是加 270 记混** | **没有死记法**：先算出 strike+90 与 strike+270 两个候选，**再用题目给的象限字母在罗盘上验证哪个对**。（085/40SE → +90 = 175 ✓；085/40NW → +270 = 355 ✓） |
| 4 | **忘了倾角只能在 0–90° 之间** | 倾角是**从水平面向下**量的角，**永远 0°～90°**。写出 >90° 的倾角必错。 |
| 5 | **把「倾角」误当成「倾伏」** | **dip** 是**平面（层面 / 断层面）**的倾角；**plunge** 是**线（褶皱轴）**的倾角。两者概念不同。 |
| 6 | **判断褶皱是否倾伏时找错证据** | 关键判据（讲义原文）：**倾角沿褶皱轴方向是否变化 —— 若倾伏，倾角会沿轴变化；若不变，则近乎水平轴。** 另外看**露头条带是否闭合成鼻状**。**不要只凭「条带弯了」就下结论**（也可能是地形起伏）。 |
| 7 | **轴迹符号方向画反** | **背形 (antiform) = 菱形 / 箭头朝外（两翼背离轴倾斜）**；**向形 (synform) = 领结 / 箭头朝内（两翼朝向轴倾斜）**。 |
| 8 | **younging symbol 画歪** | Y 形符号的**尾巴指向最年轻地层**，且**永远画成与走向成 90°**。不确定就问助教（讲义原话）。 |
| 9 | **把 thrust 与 reverse 当成两种完全不同的断层** | **thrust 是 reverse 的一个子类** —— **缓倾（~30° 或更缓）的逆断层就叫 thrust**。二者应力环境相同（σ1 水平），运动学相同（上盘上冲、老覆新）。 |
| 10 | **正断层与逆断层都可以很陡，仅凭倾角判型** | 讲义明说 **reverse faults「may also have steeply dipping fault planes, similar to normal faults」**。**必须结合上盘运动方向 + 年龄并置关系**才能定型，不能只看倾角。 |
| 11 | **上盘 / 下盘搞反** | **hanging wall = 断层面之上的块**（想象在断层面下走隧道，头顶上的是 hanging wall）；**footwall = 断层面之下的块**（脚踩着的）。**直立断层没有上下盘。** |
| 12 | **BGS 断层符号读反** | **正断层的 tick 画在下降的上盘一侧**；**逆冲断层的齿画在上盘（上覆板片）一侧**。两者都标在**上盘**，区别在符号形状与运动方向。 |
| 13 | **默认断层类型沿走向不变** | **Causey Pike Fault 西段逆冲、东段走滑**；**Coniston Fault 的下降侧由北向南发生反转**。**必须沿断层全长逐段判读**。 |
| 14 | **走滑断层的左行 / 右行判反** | 站在断层一侧**向对面看**，**对面块体往左动 = 左行 (sinistral)**，**往右动 = 右行 (dextral)**。**这个判法与你站在哪一侧无关（结果相同）**，所以不用担心选边。 |
| 15 | **在没有标志层的地方量位移** | 量位移必须用**跨断层可对比的独特标志层 (marker)**。Derwent Water Fault 的解答就明确点名**南端的橙色 "vs" 单元**作为唯一可靠标志。 |
| 16 | **忘了野外素描的必备要素** | 讲义清单八项：**层理、位移方向与量、岩性变化、断层面位置、产状与倾角、比例尺（照片中的人）、上下盘标注、三个主应力方向**。**漏掉比例尺和主应力是最常见失分点。** |
| 17 | **把「脆性 / 韧性」的控制因素记成只有深度** | 三条并列：**岩石材料性质**、**深度 / 温压条件（高 P-T 利于韧性）**、**应变速率（高应变速率利于脆性）**。 |
| 18 | **忘了倒转褶皱会让 anticline ≠ antiform** | 只有在**地层未倒转**的常规情形下，anticline 才必然是 antiform。**多期变形区必须分开判断。** |

---

## 七、本周术语表

### （一）上午场：形态学与生物力学

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Morphology | 形态学 | 研究生物的形态、形状与结构。 |
| Comparative morphology | 比较形态学 | 跨个体、跨生命阶段或跨物种比较形态差异。 |
| Biomechanics | 生物力学 | 把生物结构当作力学系统来研究其结构与功能。 |
| Artiodactyla / artiodactyls | 偶蹄目 / 偶蹄类 | 偶数趾的有蹄类，含鹿科、牛科、长颈鹿科。 |
| Ruminantia | 反刍亚目 | 具反刍胃的偶蹄类支系，本周三个科都属于它。 |
| Cervidae | 鹿科 | 具每年脱落的骨质分叉鹿角 (antlers) 的偶蹄类。 |
| Bovidae | 牛科 | 具骨心 + 永久角质鞘、不脱落洞角 (horns) 的偶蹄类。 |
| Giraffidae | 长颈鹿科 | 具终生被皮的 ossicones、颈与四肢显著延长的偶蹄类。 |
| Metapodial | 掌 / 跖骨（统称） | 连接指趾骨与前臂 / 小腿骨的长骨。 |
| Metacarpal | 掌骨 | **前肢**的 metapodial；偶蹄类第三+第四愈合成炮骨。 |
| Metatarsal | 跖骨 | **后肢**的 metapodial；通常比掌骨更长。 |
| Cannon bone | 炮骨 | 第三与第四掌 / 跖骨愈合形成的单根刚性长骨。 |
| Epiphysis | 骨骺 | 长骨末端、与他骨形成关节的部分。 |
| Proximal epiphysis | 近端骨骺 | 掌骨靠近身体的一端，与腕骨关节。 |
| Distal epiphysis | 远端骨骺 | 掌骨远离身体的一端，与指骨关节；Task 2 的测量对象。 |
| Shaft | 骨干 | 长骨中段的柱状部分；Task 1 在其**中段**测宽度。 |
| Maximum length (L) | 最大长度 | 骨两端最远两点之间的距离（mm）。 |
| Midshaft breadth (B) | 骨干中段宽度 | 骨干正中段的横向宽度（mm）。 |
| Medio-lateral width (W) | 内–外侧宽度 | 远端骨骺沿身体内外方向的宽度（mm）。 |
| Antero-posterior diameter (D) | 前–后向直径 | 远端骨骺沿身体前后方向的直径（mm）。 |
| Out-lever | 外力臂 / 输出臂 | 关节到肢体末端的距离；越长速度越大、力量越小。 |
| In-lever | 内力臂 | 肌肉附着点到关节的距离；越长力量越大、速度越小。 |
| Cursorial | 奔跑型（适应奔跑的） | 四肢延长、运动限于矢状面、适于长距离快速奔跑。 |
| Gracile | 纤细型 / 细长的 | 骨干相对细长（低 B/L），偏速度。 |
| Robust | 稳健型 / 粗壮的 | 骨干相对粗壮（高 B/L），偏承重与抗折。 |
| Callipers | 游标卡尺 | 本次实践的测量工具，读数到 0.01–0.1 mm。 |
| Scatterplot | 散点图 | 两个连续变量配对作图，本周所有分析的基础图型。 |
| Regression (line) | 回归（线） | 拟合 y 对 x 的线性关系，给出斜率与截距。 |
| Slope | 斜率 | 回归线的陡度；log-log 图上即为**缩放指数**。 |
| Intercept | 截距 | 回归线在 x = 0 处的取值；本周仅作组间相对比较。 |
| r² (coefficient of determination) | 决定系数 | 回归解释的方差比例（0–1），衡量拟合优度。 |
| Log transform | 对数变换 | 取 log₁₀ 把幂律关系线性化、压缩量级、稳定方差。 |
| Scaling | 缩放律 | 描述某个量随体型如何变化的规律。 |
| Isometry / geometric similarity | 等比生长 / 几何相似 | 形状不变的纯放大；面积 ∝ 质量^(2/3)，斜率 ≈ 0.67。 |
| Allometry | 异速生长 | 形状随体型改变；斜率偏离等比预期值。 |
| Positive allometry | 正异速生长 | 该结构比等比预期长得更大（此处斜率 > 2/3）。 |
| Stress (mechanical) | 应力 | 单位面积上的力（力 / 面积）；关节软骨的承受量。 |
| Body mass | 体重 | Task 2 的自变量，**由文献给定不测量**（25–1000 kg）。 |
| Joint surface area | 关节面面积 | 用 W × D × π ÷ 2 由半圆柱模型估算（mm²）。 |
| PivotTable | 数据透视表 | Excel 汇总工具；需手动 Refresh All 才更新。 |
| Trendline | 趋势线 | Excel 中给数据系列添加的拟合线（选 Linear）。 |

### （二）下午场：构造地质学

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Strata / stratum | 地层（复数 / 单数） | 岩石层；单层为 stratum。 |
| Bedding plane | 层面 | 分隔相邻地层的沉积界面，是最常用的测产状对象。 |
| Strike | 走向 | 平面与水平面交线的罗盘方位角；永远水平，写三位数。 |
| Dip | 倾角 | 平面从水平面向下量的角度，垂直走向测，0°–90°。 |
| Dip direction | 倾向 | 下倾方向投影到水平面的罗盘方位角 = strike ± 90°。 |
| Compass bearing | 罗盘方位角 | 自北 (000°) 顺时针量的方位角。 |
| Downdip direction | 下倾方向 | 沿平面最陡下降的方向；旧式地图符号的箭头所指。 |
| Ductile deformation | 韧性变形 | 岩石连续弯曲而不破裂的变形 → 形成**褶皱**。 |
| Brittle deformation | 脆性变形 | 岩石破裂并沿破裂面位移 → 形成**断层**。 |
| Crustal shortening | 地壳缩短 | 压缩作用使地壳水平方向变短；褶皱是其韧性表现。 |
| Fold | 褶皱 | 地层受压缩后弯曲形成的构造。 |
| Antiform | 背形 | **向上闭合**的褶皱（纯几何术语）。 |
| Synform | 向形 | **向下闭合**的褶皱（纯几何术语）。 |
| Anticline | 背斜 | **核部为最老岩石**的褶皱（需年龄信息）。 |
| Syncline | 向斜 | **核部为最新岩石**的褶皱（需年龄信息）。 |
| Anticlinal antiform | 背斜背形 | 最常见的正常组合：向上闭合且核部最老。 |
| Synclinal synform | 向斜向形 | 最常见的正常组合：向下闭合且核部最新；Pembrokeshire 即此类。 |
| Core (of a fold) | 褶皱核部 | 褶皱内侧、被两翼包夹的部分；定 anticline/syncline 的依据。 |
| Limb | 翼 / 翼部 | 褶皱两侧倾向不同的地层部分。 |
| Fold hinge | 褶皱枢纽 | 两翼相交、层理方向发生转折的位置。 |
| Fold axis | 褶皱轴 | 沿褶皱延伸、平行于枢纽的假想线。 |
| Hinge line | 枢纽线 | 单个层面上曲率最大点的连线，实际与褶皱轴同向。 |
| Axial plane | 轴面 | 通过枢纽线、平分褶皱剖面的假想平面。 |
| Axial trace | 轴迹 | 轴面投影到地图平面上的线，平行于褶皱轴。 |
| Interlimb angle | 翼间角 | 两翼之间的夹角；用于 gentle→isoclinal 的紧闭度分类。 |
| Plunge | 倾伏 / 倾没 | **褶皱轴本身的倾角**；倾伏会使露头条带闭合成鼻状。 |
| Non-plunging fold | 水平轴褶皱 | 褶皱轴水平；地图上呈平行不闭合的对称条带。 |
| Plunging fold | 倾伏褶皱 | 褶皱轴倾斜；地图上条带闭合成鼻状，核部可露出更老岩石。 |
| Upright fold | 直立褶皱 | 轴面近垂直（~90°–80°）。 |
| Inclined fold | 倾斜褶皱 | 轴面明显倾斜，两翼倾角不等。 |
| Overturned fold | 倒转褶皱 | 有一翼地层上下颠倒（变新方向朝下）。 |
| Recumbent fold | 平卧褶皱 | 轴面近水平（~10°–0°）。 |
| Gentle fold | 平缓褶皱 | 翼间角 180°–120°。 |
| Open fold | 开阔褶皱 | 翼间角 120°–70°。 |
| Close fold | 闭合褶皱 | 翼间角 70°–30°。 |
| Tight fold | 紧闭褶皱 | 翼间角 30°–10°。 |
| Isoclinal fold | 等斜褶皱 | 翼间角 10°–0°，两翼近乎平行，强烈缩短。 |
| Younging symbol | 变新符号 | Y 形符号，尾巴指向最年轻地层，画成与走向成 90°。 |
| Younging direction | 变新方向 | 地层由老变新的方向；判断是否倒转的关键。 |
| Erosion | 剥蚀 | 削去地表岩石、把不同深度的基岩暴露出来的营力。 |
| Map view | 平面视图 / 地图视图 | 从上往下俯视的视角，即地质图所呈现的视角。 |
| Cross section | 剖面 | 沿某条线切开地壳的垂直视图；Exercise 4 用它定 antiform/synform。 |
| Outcrop pattern | 露头模式 | 岩石单元在地图上呈现的条带 / 闭合形态。 |
| Fault | 断层 | 地壳内发生过位移的平面状破裂面。 |
| Fault plane | 断层面 | 位移发生的那个平面本身。 |
| Slip vector | 滑移矢量 | 描述断层两盘相对运动方向的矢量。 |
| Displacement | 位移 | 断层两盘沿断层面错开的距离。 |
| Hanging wall | 上盘 | 位于**断层面之上**的岩块（图 10 中的 "H"）。 |
| Footwall | 下盘 | 位于**断层面之下**的岩块。 |
| Downthrown (side) | 下降盘 | 相对下降的一侧；BGS 正断层符号的 tick 就画在这一侧。 |
| Normal fault | 正断层 | 陡倾（~60°）、上盘下降、年轻覆老、σ1 垂直、伸展环境。 |
| Reverse fault | 逆断层 | 上盘上升、老覆新、σ1 水平、挤压环境；可陡可缓。 |
| Thrust fault | 逆冲断层 | 缓倾（~30° 或更缓）的逆断层；位移量可极大。 |
| Dip-slip fault | 倾滑断层 | 正断层与逆断层的统称，位移以垂直分量为主。 |
| Strike-slip fault | 走滑断层 | 位移以水平 / 侧向为主，断层面近直立、σ2 垂直。 |
| Left lateral / sinistral | 左行走滑 | 站在一侧向对面看，对面块体向**左**移动。 |
| Right lateral / dextral | 右行走滑 | 站在一侧向对面看，对面块体向**右**移动。 |
| Oblique slip | 斜滑 | 同时具有倾滑与走滑分量的位移。 |
| Principal stress (σ1, σ2, σ3) | 主应力（最大 / 中间 / 最小） | 三个互相垂直的应力主轴；其方位决定断层类型。 |
| Anderson's fault classification | Anderson 断层分类 | 按 σ1/σ2/σ3 哪个垂直来划分正 / 逆 / 走滑断层（1905, 1951）。 |
| Extension | 伸展 | σ1 垂直的应力状态，产生正断层（裂谷、洋中脊）。 |
| Compression | 挤压 | σ1 水平、σ3 垂直的应力状态，产生逆 / 逆冲断层（造山带）。 |
| Shear | 剪切 | σ2 垂直、σ1 与 σ3 均水平，产生走滑断层（转换断层）。 |
| Age juxtaposition | 年龄并置关系 | 断层两侧岩石的相对新老关系，是定断层类型的硬证据。 |
| Stratigraphic column / log | 地层柱 | 地图上给出的岩石单元自老到新的顺序表；判读的必查项。 |
| Marker bed | 标志层 | 可跨断层对比的独特岩层，用于测量位移量。 |
| Competent bed | 能干层 | 力学上较硬、抗变形的岩层；野外素描中最好的位移标志。 |
| Fault splay | 断层分支 | 主断层前端分岔出的次级断层（Ketobe's Knob 可见）。 |
| Ramp | 断坡 | 逆冲断层切穿能干层向上爬升的陡段（与 flat 断坪相对）。 |
| Tectonic history | 构造史 | 由断层与褶皱的类型组合重建的区域变形演化史。 |
| BGS (British Geological Survey) | 英国地质调查局 | 本课所用地质图（Pembrokeshire、Keswick）的出版机构。 |
| Causey Pike Fault | 考西派克断层 | Keswick 图幅：西段逆冲、东段走滑；齿在上盘一侧。 |
| Derwent Water Fault | 德文特湖断层 | Keswick 图幅：走滑断层；箭头示运动方向，橙色 "vs" 单元是最佳标志层。 |
| Coniston Fault | 科尼斯顿断层 | Keswick 图幅：正断层；tick 在下降上盘侧，下降侧沿走向由北变南。 |
