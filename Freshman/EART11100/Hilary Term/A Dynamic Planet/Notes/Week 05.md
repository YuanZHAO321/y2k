# Week 5 — 构造地质学导论与地壳垂直运动（Structural Geology & Vertical Crustal Movement）

> 材料来源：`W5+Lecture.md`（55 张幻灯片）+ `EART11100 - 24-Feb-transcript.md`（2026-02-24 课堂录音转写）
> 讲课主线图：Pyrenees（比利牛斯山，法国—西班牙），整节课的封面与压轴案例都是它。

---

## 一、本周主题

本周把秋季学期学到的"板块的**水平**运动"，扩展到"地球表面的**垂直**运动"——即**为什么地球会有地形（topography）与海底地形（bathymetry）**。

老师明确把这一讲分成 **三个部分**（并且反复强调"这节课记住数字 **3**"——每一层都是三分法）：

| 部分 | 内容 | 对应 ILO（Intended Learning Outcomes） |
|---|---|---|
| Part 1 | 构造地质学基础（Fundamentals of structural geology） | 能描述**挤压（contractional）**、**拉张（extensional）**、**走滑/守恒（conservative）**三种构造体制下形成的主要岩石构造特征 |
| Part 2 | 地壳垂直运动的机制（Mechanisms for vertical crustal movement） | 能解释为什么地形与海底地形反映了一个**处于非平衡态（out-of-equilibrium）**的地球表面；能描述三种垂直运动机制 |
| Part 3 | 不同构造背景下的垂直运动（Vertical crustal movement in different tectonic settings） | 能说明 isostasy、flexural loading、dynamic effects 分别在哪些板块构造背景下起作用；能**预测**地形与垂直运动出现在何处 |

贯穿全课的"三"：
- 三种应力配置（σ1/σ2/σ3 的三种排列）→ 三种端元断层（normal / reverse-thrust / strike-slip）
- 三种垂直运动机制（isostasy / flexural loading / dynamic effects）
- 三种板块边界体制（divergence / convergence / conservative）

**核心因果链（本周最重要的一条线）**：
```
板块的水平运动 → 岩石承受偏应力（deviatoric stress）
   → 岩石应变：脆性断裂（faults）或塑性弯曲（folds）
      → 地壳厚度改变（拉张变薄 / 挤压变厚 / 走滑不变）
         → 均衡（isostasy）响应：浮力变化 → 抬升或沉降
         + 挠曲（flexure）响应：负荷传递到 >100 km 之外的地壳
         + 动力地形（dynamic）：地幔上涌/下沉直接顶起/拉下岩石圈
            → 地表出现高地（山脉/hinterland）与低地（沉积盆地）
               → 高地被侵蚀、低地被充填（地表过程试图恢复平衡）
```

---

## 二、核心概念

### 2.1 什么是构造地质学（Structural geology）

**定义**：研究由应力（stress）在岩石圈中产生的**变形（deformation）**的学科。老师的口头概括：**"实际上就是力学（mechanics）"**——研究岩石如何被破坏、如何被改变形状。

- 它是一门独立的大学科，而且"拥有最壮观的岩石"。
- 幻灯片示例：**Mount Head, Canadian Rockies**（加拿大落基山）——这些岩层**原本是水平沉积**的，现在被褶皱成复杂形态。这是构造地质学的核心观察：**用现在的几何形态反推过去的应力方向与大小**。

### 2.2 岩石为什么会受应力？两类应力

#### （1）Load pressure（负荷压力）
别名：**lithostatic stress（静岩应力）** = **confining stress（围压）**。老师特别提醒：不同教材/不同老师会用其中任意一个词，要都认得。

- **成因**：上覆岩石的重量（weight of overlying rock）。
- **性质**：**在各个方向上均匀作用**（acts uniformly in every direction）。
- **类比**：水下的 hydrostatic pressure（静水压力）。游泳时水从各个方向压你。
- 老师的生动比喻：**你现在正被一整柱大气压着，正是这个"负荷压力"阻止你炸开**；如果离开大气层进入真空，你会直接崩解。深部的岩石也是同理。
- **关键点**：单纯的静岩应力**不会产生构造变形**（因为各向同性，只会压缩体积，不改变形状）。

#### （2）Deviatoric stress（偏应力）
别名：**differential stress（差应力）** = **triaxial stress（三轴应力）**。

- **成因**：**水平构造力通过固体地壳的传递**（transmission of horizontal tectonic forces through the solid Earth's crust）——即板块运动。
- **性质**：应力在某一方向上大于其他方向，**非均匀**。
- 老师比喻：相当于"有人推你"，或者"一个人从这边推、另一个人从那边推把你挤扁"。
- **发生位置**：尤其是**板块边界附近**——岩石被推、被拉、被扭。
- **这才是产生断层和褶皱的原因。**

#### 三个主应力（Principal stresses）
三维世界中，任何物体上永远有**三个相互垂直的主应力**：
- **σ1 = maximum principal stress（最大主应力）**
- **σ2 = intermediate principal stress（中间主应力）**
- **σ3 = minimum principal stress（最小主应力）**

老师安慰："别担心那些 sigma，不重要"——重点是理解**哪一个是垂直的**。

**岩石对施加应力的两种响应**：
1. **Translation（平移）**——只是整体移动，不变形；
2. **Deformation（变形）**——改变形状，又分两种：
   - **Plastic / ductile（塑性/韧性）**：像口香糖一样被拉长，或被折叠起来 → **褶皱（folds）**
   - **Brittle（脆性）**：断裂 → **断层（faults）**

### 2.3 Anderson 的构造应力分类（Anderson's classification of tectonic stress）

**核心逻辑**：地球表面是一个自由面（free surface），因此三个主应力中**必有一个是垂直的**（通常由**重力**提供）。三个主应力只有**三种可能的排列方式**，因此**只存在三种端元断层**。

老师强调："如果有人问你有几种断层——只有三种端元。有些断层可以有多于一种的分量，或者先朝一个方向动再朝另一个方向动，但**根本上只有三种**。这在现在成立，你以后看任何断层也都成立。"

**记忆技巧（老师的核心提示）**：三个块体示意图其实是**同一个图旋转**得来的——
- 把 normal fault 的方块图**侧倒 90°** → 得到 thrust fault 的图（连小箭头方向都一致）；
- 再把它**竖起来** → 得到 strike-slip fault 的图。
- 本质：**断层永远以相同的方式相对主应力定向**，只是主应力的方位不同。

| | Normal fault（正断层） | Reverse / Thrust fault（逆断层/逆冲断层） | Strike-slip fault（走滑断层） |
|---|---|---|---|
| **应力状态** | **σ1 垂直**（=重力），σ2、σ3 水平 | **σ3 垂直**，σ1、σ2 水平 | **σ2 垂直**，σ1、σ3 水平 |
| **构造体制** | Extension（拉张） | Compression（挤压） | Shearing / conservative（剪切/守恒） |
| **断层面产状** | **陡，~60°（相对水平）** | **缓，~30°（相对水平）** | **近垂直** |
| **断层面倾向** | 平行于 **σ3** | 平行于 **σ1** | — |
| **上/下盘** | **Hangingwall 下降（downthrown）** | **Hangingwall 上升（upthrown）** | 无上下盘之分 |
| **滑动类型** | Dip-slip（倾滑） | Dip-slip（倾滑） | Strike-slip（走滑） |
| **对地壳厚度的影响** | **减薄（thins）+ 加宽** | **加厚（thickens）+ 缩短** | **无净变化** |

**术语澄清**：
- **Dip-slip fault（倾滑断层）**：位移沿**倾斜面**发生，两个块体相对地表有**垂直分量**的运动。Normal 与 reverse 都是 dip-slip。
- **Hangingwall（上盘）**：**悬挂在断层面之上**的块体（"hangs above the fault"）。识别正/逆断层的**唯一可靠办法**就是看上盘是下降还是上升。
- **Footwall（下盘）**：断层面之下的块体。
- 走滑断层因为断层面**垂直**，没有块体"挂"在上面，所以**不存在上盘/下盘**。

**为什么 σ1 垂直会造成拉张？** 老师在课堂上提问："地表上什么在提供垂直应力？"——答案是**重力（gravity）**。当重力是最大主应力、而水平方向的 σ3 极弱时，σ3 甚至可以变成**负值（即被拉伸）**，于是形成正断层。

### 2.4 断层的实验与野外证据

#### 拉张实验（Extension video）
Ian 与讲课老师制作的**沙箱/流体箱模型（sandbox model）**：
- 箱内铺设水平层（模拟地质时期沉积的岩层）；
- 重力作为垂直最大应力，**向一侧拉伸**箱体；
- 观察结果：一系列**陡倾正断层**发育，**上盘一律下降**；相邻断块**倾向相反**（形成 horst/graben 式结构）；
- **整体效果**：地壳变**薄**、变**宽**（"以前这么厚，现在越来越薄"）。
- 老师提示：视频中 Ian 会不时加沙，**与本实验要点无关，忽略即可**。

#### 野外正断层照片判读
识别方法：找到**同一标志层（marker bed）**在断层两侧的位置，若一侧明显**下落**，且该侧位于断层面之上 → 正断层。可以**测量断层位移量**，进而**反推该地壳在过去某时曾沿某方向被拉张**（可能现在仍在发生）。

#### 挤压实验（Compression video）
同样的沙箱，用**扳手（wrench）水平推挤**块体：
- 出现**两类**构造：
  1. **逆冲断层**：上盘被**向上推举（shunted upwards）**；
  2. **褶皱（folds）**——老师现场提问"除了断层还发育什么？"，答案是褶皱。**挤压岩石不仅会把它们断开，还常常把它们折叠起来。**
- 因此挤压区常出现 **fold-thrust belts（褶皱-逆冲带）**。

#### Rocky Mountain fold-thrust belt 剖面
- 加拿大落基山的横剖面；
- 蓝色岩层被**一层叠一层地逆冲推覆到彼此之上**——这正是"reverse fault 又叫 thrust fault"的原因；
- **最重要的记忆点**：**逆冲断层的作用是"重复（duplicate）"地层、把它们堆叠起来，从而缩短并加厚地壳**。

#### 小尺度逆冲露头（照片，以罗盘为比例尺）
- 一套特征层组（一个厚层 + 其下两个薄层）**在剖面上重复出现两次** → 说明中间有一条逆冲断层把同一套层重复了；
- 老师强调：**尺度极小，但机制与造山带完全相同**。

#### 走滑断层实例
- **Japan（日本）**：地表水平错断，把农民的**农作物行列**错开——最直观的走滑证据。
- **Piqiang Fault（皮羌断裂），China（中国新疆塔里木）**：卫星影像上一套彩色岩层（含一层醒目的**红层**）在断层两侧被明显水平错开。判读：**东侧（右侧）块体向北位移，西侧块体向南位移**。原本连续的层现在对不上了。

### 2.5 褶皱（Folds）

- **主导机制**：**Buckling（纵弯褶皱作用）**——挤压导致**塑性变形（plastic deformation）**与**缩短（shortening）**。
- **发生环境**：挤压带，尤其是**大陆-大陆碰撞造山带（orogens）**，此时 **σ1 水平**。
- **随应变（strain）增大**，褶皱由宽缓 → 紧闭。

**两套分类标准**：

1. **按轴面（axial plane）产状**
   - **轴面定义**：一个**假想面**，**精确平分两翼间夹角（bisects the interlimb angle）**；老师的表述是"平分褶皱两个岩层最大倾角之间的角度的假想面"。
   - 类型：**vertical（直立）→ inclined（倾斜）→ recumbent（平卧，近水平）**。

2. **按紧闭程度（tightness）= 翼间角（interlimb angle）**
   - 把褶皱两翼想象成三角形的两条边，**夹角越小，褶皱越紧闭**。
   - 序列：**open（开阔）→ tight（紧闭）→ isoclinal（等斜，两翼近平行）**。

**两个端元例子**（幻灯片）：**Vertical open fold（直立开阔褶皱）** vs **Recumbent isoclinal fold（平卧等斜褶皱）**——后者代表极高应变。

**分类在所有尺度上都适用**（works at all scales）；轴面与翼间角是**系统的应力-应变体制的函数**。

---

## 三、公式与图表

### 3.1 三种垂直运动机制（幻灯片汇总图）

老师用一张图把三者放在一起，然后逐个讲。**注意：现实中三者常常同时作用（often all three mechanisms operate simultaneously）。**

#### 机制 1：Isostasy（均衡）——岩石圈**厚度/密度**变化的后果

**前提模型**：把岩石圈看作一系列**密度较小、刚性的"块体"（rigid blocks）**，漂浮在"流体"地幔上；即假设**地幔表现为牛顿流体（Newtonian fluid）**。
老师反复强调：**地幔其实并不是流体**（"it's definitely not a fluid mantle"），这只是一个便于计算的模型假设。

**Airy isostasy model（艾里均衡模型）**
- 物理基础 = **阿基米德原理**："a body immersed in a fluid is buoyed up by a force equal to the weight [volume] of the displaced fluid"（浸在流体中的物体受到的浮力等于它排开流体的重量）。
- 推论：**"块体"厚度的变化 → 作用于其上的浮力变化**。
- 类比：**冰山**。冰山大部分体积在水面以下；冰山融化变小 → 排水量减小 → 浮力减小。地壳完全一样。
- 符号：
  - **b** = 山带**山根（root）**的厚度
  - **h** = 山带高出海平面的高度（height ASL）
  - **ρm** = 地幔密度
  - **ρc** = 地壳密度
- 标准形式：

  $$b = h \cdot \frac{\rho_c}{\rho_m - \rho_c}$$

  代入 ρc ≈ 2.7、ρm ≈ 3.3 g/cm³ → **b ≈ 4.5 h**（山根深度约为山高的 4~5 倍）。

- **老师明确说明**："如果你想学这个方程，随你，但**不会考你方程**（you won't be asked about it）。**我们需要的是能在概念上解释它**。"
- **概念表述（必须掌握）**：
  - 地壳**加厚**（造山带）→ 排开更多地幔 → 下方地幔**把它顶得更高** → 抬升；
  - 地壳**减薄/拉伸** → 浮力**塌缩（relax）** → 沉降。
  - 老师承认这"听起来有点反直觉"，但这就是低密度块体漂浮在牛顿流体上的必然结果——**和冰山一模一样**。

**Pratt isostasy model（普拉特均衡模型）**
- 关注的是**密度**变化而非厚度变化："changes in **density** of the floating blocks will result in changes in buoyant force."
- 符号：
  - **ρp** = 高度 h（ASL）处岩石圈柱体的密度
  - **ρ0** = 岩石圈的参考密度
  - **W** = **compensation depth（补偿深度）**——在此深度以下，所有柱体的压力相等
- 标准形式（等压条件）：

  $$\rho_p (W + h) = \rho_0 W \quad\Longrightarrow\quad \rho_p = \frac{\rho_0 W}{W + h}$$

  即**密度越小的柱体站得越高**。
- **判读要点**：Pratt 解释的是"**为什么大洋地壳坐得低、大陆地壳坐得高**"——大洋地壳（基性/basaltic，ρ≈**2.9**）比大陆地壳（花岗质/granitic，ρ≈**2.7**）**更致密**，所以在软流圈中**坐得更低**。
- ⚠ 幻灯片原文写成"a denser block will have more forces applied upwards"（转写中亦如此），从物理上讲**致密块体最终坐得更低、露出水面更少**——考试时请以"**密度大 → 坐得低**"为准（见第六节易错点）。

#### 机制 2：Flexural loading（挠曲负荷）——岩石圈的弹性挠曲

**为什么需要这个机制？** 因为现实中"**岩石圈板块并不是一堆彼此独立的离散块体**"。老师的即兴演示：用手压讲台一处，"你们能看到它对**别处**也产生了影响"；还打了个比方——"**这就像社会一样，你在一个地方做了一件事，实际上会在另一个地方产生影响**"。

**关键的波长判据（wavelength criterion）**：
- 岩石圈**足够刚性**，能够**抵抗** 由加厚/减薄或密度差造成的、**波长 < 100 km** 的负荷变化 → 此时可用 **"local" isostasy（局部均衡，即 Airy 型）**近似；
- 但波长 **> 100 km** 的负荷变化，会被岩石圈的**弹性挠曲（elastic flexure）完全补偿** → 称为 **regional isostasy（区域均衡）/ flexure**。

**经典案例：Scotland 的冰后回弹（glacial isostatic adjustment）**
- 直到约 **10,000 年前**，苏格兰上覆有一个**局部厚达约 1 km 的冰盖（ice cap）**；**南英格兰没有冰**。
- 冰融化后：
  - 按纯 Airy（局部块体）模型：苏格兰应**回弹上升**，英格兰**不应有任何变化**；
  - 实际观测：**苏格兰在上升，而南英格兰在下沉**。
- **原因**：地壳不是独立块体，而是一块连续的弹性板 → 苏格兰的回弹**通过挠曲把邻区拉下去**（forebulge collapse）。
- 现实后果：**苏格兰在"变大"（露出海面），英格兰在"变小"（沉入海中）**。

#### 机制 3：Dynamic effects（动力效应）——地幔中的流动

老师说这是**最容易理解的一个**（"你得挺笨才听不懂我接下来要说的"），因此只有一张幻灯片：
- **地幔上涌（upwelling）**：更热、密度更小、**体积更大**的物质上涌 → 上覆岩石圈**向上挠曲**（"字面上就像给地表充气"）；
- **地幔下沉（downwelling）**：更冷、密度更大、体积更小的物质下沉 → 岩石圈**向下抽吸/退缩（downward withdrawal）**。
- 这就是 **dynamic topography（动力地形）**。

### 3.2 "非平衡态地球"框图（source–transfer–sink）

```
   隆升区（Uplift）                 沉降区（Subsidence）
   = 山脉 / hinterland              = 沉积盆地 sedimentary basin
        │                                  ▲
        │ 侵蚀（erosion）                   │ 沉积（deposition）
        ▼                                  │
   碎屑沉积物 ──── 搬运带（sediment transfer zone）────┘
```
- **抬升区被侵蚀 → 产生碎屑沉积物（clastic sediment）；沉降区被沉积物充填。**
- **超级重点（幻灯片全大写）**：**ALL SEDIMENTARY ROCKS WERE DEPOSITED IN A SEDIMENTARY BASIN**——地球上**全部的沉积记录与化石记录都保存在沉积盆地中**。
- **"高"区与"低"区代表一个非平衡（out-of-equilibrium）系统**：地球构造在不断制造起伏，而地表过程在不断把它抹平。老师原话："地球忙着把地球的不同部分抬升和下沉，而地表过程则试图通过侵蚀山脉、填满盆地来抵消这一效应。"

**长期平衡收支判读（幻灯片提问 + 答案）**：

| 地点 | 高程 | 长期收支 |
|---|---|---|
| **Mount Everest（珠峰）** | +8,848 m ASL | **Uplift > erosion**（抬升速率快于侵蚀速率，所以山还在） |
| **Mariana Trench（马里亚纳海沟）** | **−10,994 m** | **Subsidence > deposition**（沉降造出的空间还没被沉积物填满） |
| **Canadian Shield（加拿大地盾）** | 极平坦 | **Uplift = erosion；Subsidence = deposition**（处于平衡态） |
| **Dead Sea shore（死海岸）** | −413 m | （幻灯片给出的第三个极值数据） |

### 3.3 Pyrenees 深部地震剖面（本课压轴图，必考级）

- **背景**：Pyrenees 是一条**现已不活动（inactive）**的造山带；**西班牙（Iberia）曾是一个独立板块，向北碰撞进入 Eurasia**，形成比利牛斯山。
- **数据**：一条**穿越整条山脉的深反射地震剖面（seismic survey）**——老师说"真正酷的地方在于我们能看到地壳非常非常深处的样子"。（即著名的 ECORS 剖面；老师提到这里曾是本系的野外实习地点。）
- **判读要点**：
  1. 剖面左侧为 **Spain（Iberian plate）**，右侧为 **France（Eurasian plate）**；
  2. **Iberian plate 俯冲/插入到 Eurasian plate 之下**；
  3. 中央出现一个**极厚地壳带**——**比相邻地区厚一倍（double the thickness）**；
  4. 这个加厚带因 **Airy isostasy** 被**向上浮托 → 形成山脉**；
  5. **课堂现场提问**："那些**没有被加厚**的两侧地壳，原则上应该被向上浮托吗？"——如果每块地壳独立作用，答案是"不应该有变化"。但**实际观察到两侧地壳被向下挠曲**；
  6. 原因：山带的巨大**重量作为负荷（load）**压在地表 → 长波长挠曲 → 两侧形成**正在沉降的盆地**（剖面上的深灰色区）。
- **结论**：一条剖面上同时看到 **isostasy（中央抬升）** 与 **flexural loading（两侧沉降）** 两种机制。

### 3.4 Fold-thrust belt / 造山带-前陆盆地对偶图

```
   前陆盆地        造山带（Orogen）        前陆盆地
 Foreland basin  ←—— 加厚、抬升 ——→   Foreland basin
   （沉降）         （Airy isostasy）        （沉降）
      ↑                  │ 侵蚀                 ↑
      └──── 沉积物 ←──────┴───── 沉积物 ────────┘
     （挠曲下沉：flexural loading，波长 > 100 km）
```
- **大多数山带两侧各有一个前陆盆地**（"Most mountain belts have two foreland basins on either side of them"）。
- 前陆盆地**接收从正在隆升的造山带剥蚀下来的沉积物**——这就是 3.2 那个"非平衡"框图在造山带上的具体实现。

### 3.5 走滑体制下的弯曲（bends）平面图

```
   Transtensional bend（张扭弯曲）        Transpressional bend（压扭弯曲）
   →→→ ┐                                 →→→ ┐
        └ ←←←   两块体相互拉开              └ ←←←   两块体相互挤压
    → 局部拉张 → pull-apart basin        → 局部挤压 → 隆起（push-up）
```
- 判读方法：看**弯曲（kink / double bend / relay）两侧块体的相对运动方向**——若在弯曲处两块体**相互离开** → **transtension（张扭）→ 沉降/盆地**；若**相互靠拢** → **transpression（压扭）→ 隆起**。
- 盆地在平面上呈 **sigmoidal（S 形）**，边界**陡直**（反映走滑断层面近垂直），**沉降极快**。

---

## 四、课堂补充（transcript 独有）

### 4.1 老师反复强调的记忆锚点

- **"记住数字 3"**：老师原话——"如果你今天从这节课带走任何东西，就是数字 3，因为这个数字一次又一次出现。如果我问你从那节课记住了什么，就说'三'。"
- **三种断层是绝对的**："人们现在问你存在哪三种断层——只有三个端元，就是那三种。有些断层可以显示不止一种分量，或者先朝一个方向动再朝另一个方向动，但**根本上只有三种断层**。这现在成立，你以后看任何断层时也都成立。"
- **只有三种主应力配置**："只有那三种可能的组合存在，因此只会发育三种端元断层。"

### 4.2 方块图旋转技巧（口头讲授，幻灯片上没有）

"直觉上感觉有点复杂，但其实你注意到：如果你把第一个展示正断层的方块图**侧倒过来**，就正好得到那个（逆断层）方块图，**连那些小箭头的方向都一致**。然后如果我们把它**竖起来**，就得到这个（走滑）图。**根本上，断层总是以完全相同的方式相对主应力定向，取决于这些主应力的方位。**"

### 4.3 课堂互动与"陷阱题"

**关键投票题（老师说"这是个相当重要的点"）**：
> "这些岩石中哪一组经历了最大的应力？是这些 **open folds** 还是这些 **isoclinal folds**（两翼近乎平行）？"
>
> 第二问：屏幕上有两张照片——一张是**以地质锤为比例尺的、只有几厘米的小褶皱（很紧闭）**，另一张是**几百米宽的巨大褶皱**（老师说"本来应该有个人在里面当比例尺，但我不小心裁掉了"）。老师问："这两个褶皱中，哪一个是由**更大的挤压量**产生的？"
>
> **正确答案：那个很小的、紧闭的褶皱。**
>
> 老师的总结：**"重要的不是尺度，而是褶皱有多紧闭（It's not the scale that matters, it's how tight the fold is）。"**

**其他现场提问**：
- "地表上主要的垂直应力是什么？"→ **重力（gravity）**。
- 挤压沙箱实验："除了断层，还发育了什么你不会称之为断层的构造？"→ **褶皱**。
- 俯冲带："如果我们从俯冲板片熔融物质并把它注入上覆板片，又把沉积物刮下来贴到上覆板片上，我们对上覆板片的**总体积**做了什么？"→ **增大体积** → **浮力增大** → **抬升**。
- Pyrenees 剖面："没被加厚的那部分地壳原则上应该被浮起来吗？"→ 引出 flexural loading。
- "如果我们把地壳减薄，等静压响应应该是什么？下方的浮力会怎样？"→ **减小** → **沉降**。

### 4.4 Slab rollback 的"钓鱼"类比（transcript 独有，非常好记）

老师问全班"有人钓鱼吗？"，然后解释：
> "你抛竿出去之后，会钓一会儿，然后收线再重新抛出去。抛出去时，你的鱼钩和倒刺落水，然后**逐渐向你这边漂回来**，所以你必须收线、重新抛到湖中央去。
> **俯冲板片在地球内部做的正是这件事。**"

机制展开：
1. 板片开始时以**相对低的角度**俯冲；
2. **随时间推移，板片越来越陡（steepens with time）**；
3. 变陡的板片开始**向后拉扯上覆板片（pull back on the overriding slab）**；
4. 于是在**岛弧后方**产生**拉张**；
5. 拉张 → 上覆地壳**减薄** → **浮力减小** → **沉降** → 形成 **back-arc basin（弧后盆地）**。
6. 幻灯片补充：**这是"被动裂谷（passive rifting）"的另一种成因机制**。

**因此，最反直觉的结论之一**：在整体**挤压**的洋-洋/洋-陆俯冲背景中，**同时**存在**抬升（island arcs / oceanic arcs）**与**沉降（back-arc basins）**。

> ⚠ **材料内部不一致**：幻灯片 45 说日本弧后的拉张区是 **South China Sea（南海）**；transcript 中老师说的是 **Sea of Japan（日本海）**。**日本弧后盆地 = 日本海**，这是正确答案；南海是另一个（更南的）弧后/边缘海系统。写答案时用 **Sea of Japan**。

### 4.5 "我们差点变成美国"——North Sea 失败裂谷的故事（transcript 独有的完整叙事）

老师的原话讲法（"A brief history of how we nearly became America. 谢天谢地我们现在没有"）：
- 地图上：左边是 **Scotland**，右边是 **Norway / Germany（欧洲大陆）**，中间是 **North Sea**。
- **在侏罗纪（Jurassic，~150 Ma），大西洋最初试图沿着现在的北海位置张开**——而不是在不列颠群岛的西侧。
- 但**它放弃了**（"it gave up；它发现要撕开这段大陆地壳太困难了"）。
- 于是**张裂作用"跳"到了不列颠群岛的另一侧**，形成了今天的大西洋。
- 因此 **North Sea 是一条 failed rift（失败裂谷）**——"是第一条试图张开、然后放弃了的洋，而且**至今还没被沙子完全填满**"。
- 术语：**aulacogen（拗拉槽）**。幻灯片定义：extensional strain 未能维持、**地热梯度已恢复到（接近）正常**的盆地。
- 现实意义（老师没直说但暗含）：北海因此成为巨大的**油气盆地**（侏罗纪裂谷 + 后期热沉降充填）。

### 4.6 关于 Persian Gulf / Arabian Sea 的关键澄清（transcript）

老师讲 Zagros 前陆盆地时特别强调：
> "**这片海之下没有任何洋壳，它就是被 Zagros 山带向下挠曲的大陆地壳。**"

这是理解"前陆盆地不是洋盆"的关键——前陆盆地是**被负荷压弯的大陆岩石圈**，海水只是**淹进了这个负地形**。
（注意：老师口中说的是 "Arabian Sea"，幻灯片写 "Gulf of Arabia"，实际地理对象是 **Persian Gulf / 波斯湾**——这是 Zagros 的前陆盆地。）

### 4.7 Himalayan foreland basin 的补充讲解

- **Gangetic plain（恒河平原）**就是喜马拉雅的前陆盆地，恒河在此流淌。
- **这片区域正在沉降，而不是隆升**——因为**青藏高原/喜马拉雅的重量正在把这块地壳往下压**。
- 但由于喜马拉雅侵蚀产生的沉积物**极其巨量**，所有被创造出的可容空间（accommodation space）**一直被沉积物填满** → 盆地是 **mature（成熟）且 "overfilled"（过充填）** 的。
- 对比 **Persian Gulf**：**沉积物供给不足以填满盆地（insufficient sediment supply to overfill）** → **underfilled（欠充填）**，因此仍是海。
- **这一对对比是理解"盆地充填状态 = 可容空间 vs 沉积物供给的竞争"的最佳案例。**

### 4.8 拉张区两阶段演化的口头解释

老师承认"听起来有点复杂"，但归结为**两件事同时发生**：
1. **拉伸 → 地壳减薄 → 浮力塌缩 → 中央下沉**（isostasy）；
2. **同时下方开始大量熔融 → 地幔对流上涌 → 把整个区域顶起来**（dynamic effects）。

**因此在拉张环境中，三种机制里有两种是重要的：isostasy（造成下沉）+ dynamic effects（造成整体隆起）。**
这解释了看似矛盾的观察：**中央地堑下陷，但两侧翼部（flanks）却在抬升，且整个区域的平均海拔很高**。

### 4.9 关于转写中的语音识别错误（阅读原文时的对照表）

自动转写有大量错听，复习原文时需注意：

| 转写中的错词 | 实际术语 |
|---|---|
| slag | **slab**（板片） |
| bionic / buoy / void forces | **buoyant forces**（浮力） |
| fallen basins | **foreland basins**（前陆盆地） |
| grabbers | **grabens**（地堑） |
| craft isostasy | **Pratt isostasy** |
| Leprosy / lithopshere | **lithosphere**（岩石圈） |
| limanthal | **asthenosphere**（软流圈） |
| Stockholm（"冰盖坐在……之上"） | **Scotland**（苏格兰） |
| photometry | **bathymetry**（海底地形） |
| n-member | **end-member**（端元） |
| slip-slip faults | **dip-slip faults**（倾滑断层） |
| "behaving in a ripple manner" | **brittle manner**（脆性方式） |
| "we do it through foaming" | **folding**（褶皱作用） |
| "Holocaust orientation" | **horizontal orientation**（水平方位） |
| flexor loading | **flexural loading**（挠曲负荷） |
| "blue cat fox model" | 大致指沙箱/方块模型（block model） |
| "structural biologist" | **structural geologist**（构造地质学家） |

---

## 五、Practical 要点

**（本周无独立 practical）** — 本周材料仅有一份讲座幻灯片（W5+Lecture.pptx）与一份课堂转写，无 practical 手册或实习材料。

但幻灯片中的**实验录像**（沙箱拉张实验、沙箱挤压实验）与**Pyrenees 地震剖面判读**具有 practical 性质，建议按以下方式自测：
1. 给一张野外/剖面照片，能否用**标志层错断方向 + 断层面倾角 + 上盘位置**判断断层类型；
2. 给一条地形图（如 Basin and Range、East African Rift），能否指出哪些是 **graben**、哪些是抬升的 **flank/range**；
3. 给一条造山带剖面，能否标出 **加厚带（orogen）** 与两侧 **前陆盆地**，并说明各自的驱动机制。

---

## 六、易错点 / 重点难点

### 6.1 断层判读

1. **不要用"断层往哪边倾"来判断正/逆断层** —— 正断层和逆断层都可以往左或往右倾。**唯一判据是上盘（hangingwall）是下降还是上升**。先找出哪一块"挂"在断层面之上。
2. **角度记反**：正断层 **~60°**（陡），逆冲断层 **~30°**（缓）。转写里老师特意纠正过——"那图上标的 60° 是相对**垂直**方向的，也就是相对**水平** 30°"。**角度惯例默认是相对水平面。**
3. **断层面倾向与主应力的关系**：正断层面**倾向平行于 σ3**；逆冲断层面**倾向平行于 σ1**。容易混。
4. **走滑断层没有 hangingwall / footwall**——因为断层面近垂直，没有块体"挂"在上面。
5. **端元 ≠ 现实中所有断层都纯粹**：现实断层常有斜滑（oblique-slip）分量，但**端元只有三个**。

### 6.2 褶皱

6. **⭐ 最容易答错的一题**：**褶皱的"大小"与应变量无关，"紧闭度（翼间角）"才反映应变量。** 一个几厘米宽的等斜褶皱，比一个几百米宽的开阔褶皱经历了**更大的挤压**。
7. **轴面 ≠ 褶皱枢纽面的任意一个面**——轴面是**精确平分翼间角**的那个面。

### 6.3 均衡与挠曲

8. **Airy vs Pratt 别混**：
   - **Airy = 厚度变化**（同密度，不同厚度；山根模型；冰山类比）
   - **Pratt = 密度变化**（同补偿深度，不同密度；解释洋壳 vs 陆壳的高差）
9. **"加厚地壳会被顶得更高"听起来反直觉，但正确**——因为它排开更多地幔，浮力更大。老师专门提醒过这一点。
10. **幻灯片 31 的一处措辞需要小心**：写的是 "a denser block will have more forces applied upwards on it"。就物理结果而言，**密度更大的块体最终坐得更低**（如洋壳）。理解时以幻灯片 41 的表述为准：**"Oceanic crust (basic) is denser (2.9) compared to continental crust (granitic, 2.7), so the crust sits lower in the asthenosphere (Pratt isostasy)"**。
11. **100 km 波长判据必须记住**：< 100 km 的负荷 → 岩石圈刚性足以抵抗，可用 **local（Airy）isostasy**；> 100 km 的负荷 → **完全由弹性挠曲补偿（regional isostasy / flexure）**。
12. **纯 Airy 模型无法解释南英格兰的下沉** —— 这正是引入 flexure 的原因（"地壳不像独立块体那样行为"）。
13. **三种机制通常同时作用**，考试若问"某地为什么高/低"，往往需要**同时列出两到三个机制并说明主次**。

### 6.4 构造背景

14. **反直觉结论一**：**洋-洋 / 洋-陆碰撞（挤压背景）同时产生抬升（island arc）与沉降（back-arc basin）**。原因是 **slab rollback / 板片变陡**。
15. **反直觉结论二**：**陆-陆碰撞同时产生抬升（orogen）与沉降（foreland basin）**。原因是**挠曲负荷**。
16. **前陆盆地不是洋盆**：其基底是**被压弯的大陆地壳**（Persian Gulf 是最好的例证）。
17. **前陆盆地成对出现**：大多数山带**两侧各一个**。
18. **Passive vs Active rifting 的因果顺序千万别反**：
    - **Passive rifting（被动裂谷）**：**先拉张** → 地壳减薄 → **减压熔融（decompression melting）** → 软流圈上涌。代表：**Basin and Range, Nevada, USA**；以及**弧后拉张**。
    - **Active rifting（主动裂谷）**：**先有地幔柱/上涌** → 岩石圈**穹隆化（doming）** → 在**重力势能作用下发生崩塌（collapse under gravitational potential）**、地壳"从隆起上滑下来" → 拉张。代表：**East African Rift**。
    - 老师原话："**你先得到上涌，然后才得到扩张**——这和被动裂谷正好相反。"
19. **幻灯片 42 对 aulacogen 的定义有问题**：幻灯片写 failed rifts 是 "basins floored by **oceanic crust**"。但**北海（老师的例子）之下并没有洋壳**，而是**强烈减薄的大陆地壳**。真正的 aulacogen 通常是未发展到洋壳阶段的夭折裂谷。**答题时按老师口头讲的"张裂开始了但放弃了、地热梯度回归正常"的意思写更安全**，不要断言其下有洋壳。
20. **弧后盆地位置**：日本的弧后盆地是 **Sea of Japan（日本海）**，不是幻灯片上误写的 South China Sea。
21. **守恒（走滑）体制下的盆地**：
    - 由 **transtension（张扭）** 造成，通常发生在断层的 **double bends / relays（弯曲与错列）**；
    - 典型：**Death Valley, California**（最低点 **−86 m ASL**），位于 San Andreas 系统上（SF—LA 之间）；
    - 特征：**平面上 sigmoidal（S 形）、边界陡直、沉降极快**；
    - **但在全球盆地总量中体积占比很小（volumetrically a minor component）**——老师说他"基本上不会多讲守恒体制"，因为影响很局部，"不是造山带尺度的抬升"。

### 6.5 概念性大局

22. **"ALL SEDIMENTARY ROCKS WERE DEPOSITED IN A SEDIMENTARY BASIN"**——这是幻灯片全大写强调的一句话，是本课与"沉积环境"周次的桥梁。地球全部沉积与化石记录都存在盆地里。
23. **能预测，而不只是记忆**：ILO 明确要求"**predict where topography and vertical crustal movement might be expected**"。练习方法：拿一张世界板块图，指着任意一个边界，说出该处的应力状态 → 断层类型 → 地壳厚度变化 → 主导的垂直运动机制 → 预期地形。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Structural geology | 构造地质学 | 研究应力在岩石圈中产生的变形的学科，本质是岩石力学。 |
| Stress | 应力 | 单位面积上作用的力，是变形的驱动量。 |
| Strain | 应变 | 岩石对应力的响应，即形状/体积的改变。 |
| Load pressure / Lithostatic stress / Confining stress | 负荷压力 / 静岩应力 / 围压 | 上覆岩石重量造成的、各方向均匀的应力，类比静水压力，本身不造成构造变形。 |
| Deviatoric / Differential / Triaxial stress | 偏应力 / 差应力 / 三轴应力 | 各方向不均匀的应力，由水平构造力传递产生，是断层与褶皱的直接成因。 |
| σ1 / σ2 / σ3 (principal stresses) | 最大/中间/最小主应力 | 三个互相垂直的主应力，其排列方式决定发育哪种断层。 |
| Anderson's classification | 安德森断层分类 | 依据哪个主应力为垂直，把断层分为正、逆、走滑三种端元。 |
| Brittle deformation | 脆性变形 | 岩石通过破裂响应应力，产物是断层。 |
| Plastic / Ductile deformation | 塑性 / 韧性变形 | 岩石像口香糖一样流动或折叠，产物是褶皱与韧性拉伸。 |
| Fault | 断层 | 发生过位移的破裂面。 |
| Dip-slip fault | 倾滑断层 | 沿倾斜面滑动、含垂直运动分量的断层（正断层与逆断层）。 |
| Normal fault | 正断层 | σ1 垂直、拉张体制，倾角约 60°，上盘下降，使地壳减薄加宽。 |
| Reverse / Thrust fault | 逆断层 / 逆冲断层 | σ3 垂直、挤压体制，倾角约 30°，上盘上升，使地壳缩短加厚。 |
| Strike-slip fault | 走滑断层 | σ2 垂直、剪切体制，断层面近垂直，纯水平位移，地壳厚度不变。 |
| Hangingwall | 上盘 | 悬挂在断层面之上的岩块，是判别正/逆断层的关键。 |
| Footwall | 下盘 | 位于断层面之下的岩块。 |
| Fold | 褶皱 | 岩层塑性弯曲形成的构造，多由挤压引起。 |
| Buckling | 纵弯褶皱作用 | 岩层受到平行层面的挤压而屈曲成褶皱的主要机制。 |
| Axial plane | 轴面 | 精确平分褶皱翼间角的假想面，其产状（直立/倾斜/平卧）用于分类。 |
| Interlimb angle | 翼间角 | 褶皱两翼之间的夹角，越小褶皱越紧闭，代表应变越大。 |
| Open fold | 开阔褶皱 | 翼间角大的褶皱，代表低应变。 |
| Isoclinal fold | 等斜褶皱 | 两翼近乎平行、翼间角近 0° 的褶皱，代表极高应变。 |
| Recumbent fold | 平卧褶皱 | 轴面近水平的褶皱。 |
| Fold-thrust belt | 褶皱-逆冲带 | 挤压带中褶皱与逆冲断层共生的构造带，如加拿大落基山。 |
| Accretionary prism | 增生楔 | 从俯冲洋壳表面刮下并贴附到上覆板片上的沉积物楔体。 |
| Orogen / Orogenic belt | 造山带 | 由碰撞造成地壳强烈加厚与变形的山系。 |
| Hinterland | 后陆 / 腹地 | 造山带中被抬升、供给沉积物的高地区。 |
| Topography | 地形 | 陆地表面的高低起伏。 |
| Bathymetry | 海底地形 | 海面以下的地形起伏（"负地形，装满了水"）。 |
| Uplift | 隆升 / 抬升 | 地壳向上的垂直运动，形成高地。 |
| Subsidence | 沉降 | 地壳向下的垂直运动，形成沉积盆地。 |
| Sedimentary basin | 沉积盆地 | 沉降形成并被沉积物充填的低地；地球全部沉积与化石记录都保存在其中。 |
| Out-of-equilibrium | 非平衡态 | 地形起伏本身即表明构造抬升/沉降速率与地表侵蚀/沉积速率不匹配。 |
| Isostasy | 地壳均衡 | 低密度岩石圈块体漂浮在"流体"地幔上、由浮力平衡厚度或密度变化的原理。 |
| Airy isostasy | 艾里均衡 | 密度相同、厚度不同的模型；加厚地壳产生深"山根"并被更强浮力顶起。 |
| Pratt isostasy | 普拉特均衡 | 补偿深度相同、密度不同的模型；密度小的柱体站得高，解释洋壳低于陆壳。 |
| Root (b) | 山根 | 造山带地壳向下伸入地幔的加厚部分，Airy 模型中约为山高的 4–5 倍。 |
| Compensation depth (W) | 补偿深度 | Pratt 模型中各柱体压力相等的深度界面。 |
| Newtonian fluid | 牛顿流体 | 建模时对地幔行为的简化假设（老师强调地幔实际并非流体）。 |
| Flexural loading | 挠曲负荷 | 岩石圈作为弹性板对负荷的响应，把变形传递到 >100 km 之外。 |
| Local isostasy | 局部均衡 | 波长 < 100 km 的负荷，岩石圈刚度足以抵抗，可用块体模型近似。 |
| Regional isostasy / Flexure | 区域均衡 / 挠曲 | 波长 > 100 km 的负荷由岩石圈弹性弯曲完全补偿。 |
| Glacial isostatic rebound | 冰后均衡回弹 | 冰盖消融后地壳回弹；苏格兰上升的同时南英格兰因挠曲而下沉。 |
| Dynamic effects / Dynamic topography | 动力效应 / 动力地形 | 地幔上涌顶起岩石圈、地幔下沉拉低岩石圈所造成的地形。 |
| Rift | 裂谷 | 岩石圈区域拉张减薄形成的线状断陷带。 |
| Graben | 地堑 | 两侧被正断层限定、相对下落的断块，是裂谷盆地的基本单元。 |
| Rift flank uplift | 裂谷肩部抬升 | 裂谷两侧因均衡与动力效应而抬升的高地。 |
| Passive rifting | 被动裂谷作用 | 先区域拉张 → 减薄 → 减压熔融 → 软流圈上涌；如 Basin and Range。 |
| Active rifting | 主动裂谷作用 | 先地幔柱上涌 → 穹隆 → 重力势能驱动崩塌扩张；如 East African Rift。 |
| Decompression melting | 减压熔融 | 地幔在近绝热上升、压力下降时发生的部分熔融，是裂谷火山活动的成因。 |
| Failed rift / Aulacogen | 失败裂谷 / 拗拉槽 | 张裂启动但未能维持、地热梯度已恢复正常的盆地；如北海（侏罗纪 ~150 Ma）。 |
| Back-arc basin | 弧后盆地 | 因俯冲板片变陡回卷而在岛弧后方拉张沉降形成的盆地；如日本海。 |
| Slab rollback / steepening | 板片回卷 / 变陡 | 俯冲角随时间变陡、板片后退，从而拉扯上覆板片产生弧后拉张（"钓鱼"类比）。 |
| Island arc / Oceanic arc | 岛弧 / 洋内弧 | 俯冲带上覆板片因熔体注入与增生楔加厚而被均衡抬升出海的火山链；如日本。 |
| Foreland basin | 前陆盆地 | 造山带负荷使邻区岩石圈挠曲下沉形成的盆地，接收造山带剥蚀的沉积物。 |
| Overfilled basin | 过充填盆地 | 沉积物供给超过可容空间增长，如恒河平原（喜马拉雅前陆）。 |
| Underfilled basin | 欠充填盆地 | 沉积物供给不足以填满可容空间，仍为海，如波斯湾（Zagros 前陆）。 |
| Transtension | 张扭 | 以走滑为主的体制中含拉张分量，产生局部沉降与拉分盆地。 |
| Transpression | 压扭 | 以走滑为主的体制中含挤压分量，产生局部隆起。 |
| Double bend / Relay | 双弯曲 / 断层错列 | 走滑断层不平直处的拐折，是局部张扭或压扭发生的位置。 |
| Pull-apart basin | 拉分盆地 | 走滑断层张扭弯曲处形成的盆地，平面呈 S 形、边界陡、沉降快；如 Death Valley（−86 m）。 |
| Conservative margin | 守恒型边界 | 两板块相互滑过、地壳既不增生也不消亡的边界。 |
| Clastic sediment | 碎屑沉积物 | 由隆升区侵蚀产生、经搬运带运至盆地沉积的颗粒物质。 |

---

### 附：本周关键案例速查

| 案例 | 构造背景 | 主导机制 | 关键数据/要点 |
|---|---|---|---|
| Mount Head, Canadian Rockies | 挤压造山 | — | 原水平层被褶皱；构造地质学的经典露头 |
| Rocky Mountain fold-thrust belt | 挤压造山 | 逆冲重复地层 | 蓝色层被逐层推覆叠置 |
| 日本走滑断层露头 | 守恒 | — | 农作物行列被水平错断 |
| Piqiang Fault, China | 守恒 | — | 卫星影像上彩色层（含红层）水平错开 |
| Basin and Range, Nevada, USA | 拉张（**passive rifting**） | isostasy（地堑沉降）+ dynamic（区域整体高） | 山脊间为 graben；整体海拔高因下方地幔上涌 |
| East African Rift | 拉张（**active rifting**） | dynamic（先上涌成穹隆）→ isostasy | 高地在东非隆起，Kilimanjaro 等活火山，裂谷湖（Great Lakes） |
| Red Sea | 拉张末期→初生洋盆 | Pratt isostasy | 已开始形成洋壳；因洋壳致密且**极薄**故坐得很低 |
| North Sea | 失败裂谷（aulacogen） | 热沉降 | 侏罗纪 ~150 Ma；大西洋"先试图在此张开后放弃、跳到不列颠西侧" |
| Japan（日本弧） | 洋-陆/洋-洋俯冲 | Airy isostasy（体积增加→浮力增加） | Eurasian 板片上覆，Pacific + Philippine 板片俯冲；被"抬出海面" |
| Sea of Japan | 弧后 | slab rollback → 拉张 → isostasy 沉降 | 挤压背景中的拉张盆地（幻灯片误写为 South China Sea） |
| **Pyrenees** | 陆-陆碰撞 | isostasy（中央）+ flexure（两侧） | 全穿越深地震剖面；Iberia 俯冲于 Eurasia 之下；地壳**厚度加倍**；两侧挠曲沉降 |
| Persian Gulf / Gulf of Arabia | 陆-陆碰撞前陆 | flexural loading | Zagros（Iran）加厚 → 邻区挠曲；**基底为大陆壳非洋壳**；**underfilled** |
| Himalayan foreland（Gangetic plain） | 陆-陆碰撞前陆 | flexural loading | 正在沉降但被巨量沉积物填满；**mature / overfilled** |
| Scotland vs Southern England | 冰后回弹 | flexure | ~10 ka 前 ~1 km 厚冰盖；苏格兰上升、南英格兰下沉 |
| Death Valley, California | 守恒（transtension） | 局部拉张 | 最低点 **−86 m ASL**；San Andreas 系统 SF—LA 之间 |
| Mariana Trench | 俯冲 | — | **−10,994 m**；subsidence > deposition |
| Mount Everest | 陆-陆碰撞 | isostasy | **+8,848 m**；uplift > erosion |
| Canadian Shield | 克拉通 | — | 极平坦；uplift = erosion，处于平衡 |
| Dead Sea shore | 走滑拉分 | 局部拉张 | **−413 m** |
