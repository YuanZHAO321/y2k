# EART28202 Structural Geology — Week 06 学习笔记

> 本周材料：
> - Lecture：`Lecture/Week 6/Class6_Fractures.md`（Class 6: *Fracturing and the emplacement of minor intrusions*，共 52 张幻灯片，notes pane 极其详尽——是全大二最厚的一份单周讲义）
> - Practical：`Practical/Week 6/Ex1soln(15).md`（*Brittle failure and the Mohr Circle*，(a)–(g) 七问全解）、`Practical/Week 6/Anderson.md`（Andersonian 断层分类图版）
> - 本课全 10 周**没有 transcript**（课堂录音转写）。本笔记的全部内容来自幻灯片正文、notes pane 补充说明与练习答案；「四、课堂补充」一段同样如此，不含任何口头讲解。

---

## 一、本周主题

本周的 Theory 主题是**破裂与小型侵入体的就位（Fracturing and the emplacement of minor intrusions）**；配套 Practical 是**用莫尔图分析破裂（Analysing fracturing using Mohr diagrams）**——具体做的是**脆性破坏（brittle failure）+ 莫尔圆 + Anderson 断层分类**。

### 1.1 本周在全课骨架中的位置：力学段的收尾

EART28202 是春季学期第一门课，是 EART24001 *Geological Maps* 的直接延续——把上学期"纯几何"的走向线、剖面构建、赤平投影，**升级为力学**。全课骨架：

| 阶段 | 周次 | 内容 |
|---|---|---|
| **几何学** | W01–W03 | 褶皱几何、褶皱如何形成、应变（strain） |
| **力学** | W04–W06 | 剪切带、应力（stress）、**破裂（本周）** |
| **构造类型** | W07–W10 | 断层作用、挤压、伸展、走滑构造域 |

**本周是"力学段"的收尾，也是通向后四周"构造类型"分析的判据来源。**三周的逻辑链条是：

- **W04 剪切带**告诉你岩石在**韧性**条件下如何以分布式的方式变形；
- **W05 应力**给了你描述"原因"的完整语言（主应力 σ₁ ≥ σ₂ ≥ σ₃、莫尔圆、有效应力、岩石圈应力状态、Andersonian 应力三分）与那把唯一的图解工具——**莫尔图（Mohr diagram）**；
- **W06（本周）**把这套工具变成一个**判据**：给定应力状态，岩石**会不会**破裂、**什么时候**破裂、**沿什么方向**破裂、破裂**是张性还是剪性**。

Class 5 的幻灯片自己就预告了这一点：Slide 16 说孔隙流体压力把莫尔圆左移"的意义将在后两节课展开"，Slide 23 说古应力分析"构成后两节课的核心材料"。所以本周不是新起一段，而是把 W05 建好的坐标纸真正用起来。

### 1.2 讲义与练习的分工（本周非常关键，务必看懂）

本周有一个容易让人困惑的地方：**讲义（Class 6）与练习（Ex1soln）讲的其实是同一件事的两半，但侧重完全不同**。

- **Class 6 讲义**是**现象学与野外/工程视角**的：破裂如何分类（Mode I–IV）、野外长什么样（羽状构造、张性节理阵列、共轭脉阵列）、如何测量（密度、间距、方位）、在什么构造环境里出现（轻变形沉积盖层、断层旁、褶皱上）、以及后半段完整的**水力压裂与岩墙/岩床就位**力学。讲义**只在 Slide 14–16 用了三张片子**处理莫尔图与破坏包络线，而且**通篇没有写出 Coulomb 准则的方程**。
- **Ex1soln(15) 练习**才是**定量的破坏准则计算**：从实验数据拟合 σ₁ = a + bσ₃，转成 τ = τ₀ + μσₙ，求 φ、μ、τ₀、破裂角、深部应力、孔压触发。
- **Coulomb 准则的方程、Byerlee 定律、Anderson 分类的正式讲授在 Class 7（下周，断层作用）**——本周的 practical 是**先用后讲**。这不是材料错误，而是本课有意的安排：practical 提前把工具练熟，Class 7 再补理论。

> 复习时的取舍：**Theory 笔试**问的是本周讲义的现象与机制（破裂类型、σ₁/σ₃ 关系、孔压作用、岩墙岩床条件）；**Practical 技能考**问的是 Ex1soln 那套莫尔圆计算。两边都要，但不要用一边的内容去答另一边的题。

### 1.3 本周与下周的接力

讲义 Slide 5 明确划了界线：

> "In this class (Class 6) we will consider fractures across which displacements **parallel to the fracture surface are too small to be measurable at the exposure scale** … In the next class (Class 7) we will consider fractures across which the displacement parallel to the fracture surface **is measurable** at the exposure scale, that is, we will consider **faults**."

即：**本周 = 节理、脉、岩墙、小型剪破裂（位移小到露头上量不出来）；下周 = 断层（位移量得出来）**。Slide 22 的 notes 还预告："We shall come back to this next week when we consider how shear fractures coalesce via **wing cracks** to form a through-going fault"——小破裂如何连接成贯通断层，正是下周的开篇。

Slide 5 最后一句是给野外的忠告，也是本周的立意：

> "Minor fractures of the kind that we consider in this class are **generally poorly described by students in the field**. Given their economic significance, this cannot be good."

Slide 3 给出了"economic significance"的具体含义：对水文地质学家、石油/矿产地质学家，破裂对**流体流动**的影响是决定性的；对工程地质学家，破裂对**基底与边坡稳定性**是关键。Slide 3 的照片就是 Pembrokeshire 的 Telpyn Point 海崖因交切节理而在 2009–2010 年间垮塌，把一处极好的露头埋掉了。Slide 4 则展示破裂对**地貌演化**的控制（澳大利亚蓝山的 Three Sisters 就是节理控制的侵蚀产物）。

---

## 二、核心概念

### 2.1 破裂的定义与四模式分类

**破裂（fracture）**的定义（Slide 7）：

> "A fracture is a surface across which there is a **discontinuity in displacement and mechanical properties**. Although described as surfaces because they are very narrow in one dimension compared with the other two, **at some scale they always have thickness**."

两个要点：(1) 破裂面上**位移与力学性质都不连续**——不只是"裂开了"，它还是一个力学界面；(2) 说它是"面"只是因为一个维度远小于另两个维度，**任何尺度上它都是有厚度的**。

破裂按**形成时穿过破裂面的位移方向**分类：

| 类别 | 模式 | 位移方式 |
|---|---|---|
| **张裂隙（extension fracture）** | **Mode I** | 位移**垂直于**破裂壁，**张开**意义 |
| **剪裂隙（shear fracture）** | **Mode II / Mode III** | 位移**平行于**破裂壁；两个模式区分**两个正交的滑移方向** |
| **收缩破裂（contraction fracture）** | **Mode IV** | 位移垂直于破裂壁，**闭合**意义（**anticrack 反裂隙**） |
| **混合型破裂（hybrid / mixed mode）** | — | 上述类型的组合，通常是**张 + 剪**或**压 + 剪** |

📎 背景补充：Mode II 与 Mode III 的常规区别是——Mode II 为**面内剪切（in-plane shear / sliding mode）**，滑移方向垂直于裂纹前缘；Mode III 为**面外剪切（anti-plane shear / tearing mode）**，滑移方向平行于裂纹前缘。讲义只说"两个正交的滑移方向"，没有点名哪个是哪个。

Slide 7 的 notes 里有一条有趣的书目勘误：Mode IV 的图是 Fossen 第 1 版图的**勘误版**，"but this correction seems to have been overlooked when producing the 2nd edition — the figure is correctly shown here but is not in the 2nd edition of the book"。也就是说，**讲义上的 Mode IV 图比课本（Fossen 2016）上的对**。

### 2.2 张裂隙家族：fissure / vein / dyke / joint 的区别

这是本周最需要背准的一组定义（Slide 8）。四者**都是张裂隙**，区别只在**填充物**与**张开量**：

| 术语 | 中文 | 定义 |
|---|---|---|
| **fissure** | 裂缝 / 裂隙 | 张裂隙内填**空气或流体** |
| **vein** | 脉 | 张裂隙内填**矿物** |
| **dyke** | 岩墙 / 岩脉 | 张裂隙内填**岩浆** |
| **joint** | 节理 | 张开量**极小**，且**宏观上观察不到平行于破裂面的位移** |

注意 joint 的定义是"双否定"式的：不是"没张开"，而是"张开量很小 + 看不出面平行位移"。

Slide 8 的三张照片示例：Derbyshire 的 Mam Tor 公路上的 fissure（**路面标线的错开方向指示这是纯张裂隙**——位移矢量垂直于破裂壁）；Skye 的 Aird of Sleat 新生代**复合岩墙**（细的中央岩墙侵入更宽的早期岩墙，早期岩墙外接触带有变色的**冷凝边 chilled margin**）；Tasmania 的 Eaglehawk Neck 的**正交节理组**。

### 2.3 "严格说它们都是混合型"

Slide 9 立刻打了个补丁：**fissure、vein、dyke、joint 虽然通常被当作纯张裂隙，但在薄片下常常能看到微小的面平行位移，或者矿物纤维斜交于裂隙边界，这说明它们其实带有 hybrid 性质。**

判别工具是**矿物纤维（mineral fibres）**：

- 纤维**垂直于**脉壁 → 纯张开（Mode I）；
- 纤维**斜交于**脉壁 → hybrid（张 + 剪）。

Slide 9 的 notes 有一句非常重要的原理性说明：

> "**The fibres grow parallel to σ3** – see Class 4 Slide 37. If I was being really accurate, I should say the fibres grow parallel with **e₁, the maximum extension direction**, that is, in my first statement I am implicitly assuming that σ₃ and e₁ are parallel."

也就是说，**纤维方向严格来说记录的是最大伸长方向 e₁（应变），把它当作 σ₃（应力）是一个隐含假设**。Somerset 海岸 Lilstock 附近的方解石脉，纤维就指示 **左行张扭（sinistral transtension）**。另一个判据在薄片下：Price & Cosgrove p.43 的显微照片里，晚期脉切过早期脉时有 **~10 µm 的右行剪切位移——这在野外根本看不见**。

### 2.4 收缩破裂：缝合线与斜缝合线

Slide 10（讲义说是"for completeness"，即完整性起见）：

- **缝合线（stylolite）**：不规则的锯齿状界面，"牙齿（teeth）"**垂直于**界面 → 该方向发生了"闭合"（压溶）。
- **斜缝合线（slickolite）**：牙齿**斜交于**界面 → 收缩构造也可以是 **hybrid** 性质的。slickolite 常见于**弯滑褶皱（flexural slip folds）**周围。

notes 里给了缝合线的两代力学模型，值得知道：

1. **反裂隙（anticrack）模型**（Fletcher & Pollard, 1981）：溶解产生一个椭圆孔洞；孔洞在压应力下闭合，使孔洞表面周围的应力更强烈地压缩，从而驱动进一步溶解。其应力场直接取"张应力下椭圆孔周围应力场"的反号——故名 anticrack。
2. **更新的椭圆包体模型**：近期分析认为 anticrack 模型描述得不好，缝合线更适合描述为"内部发生了体积缩减的椭圆包体"。这种模型显示，包体周围有些区域应力强压缩、另一些区域强张性并含显著剪切分量——**这才能解释为什么缝合线周围常常同时出现张裂隙与剪裂隙**（Aharanov & Karcz, 2019）。

为什么关心？notes 说得很直白：碳酸盐岩储层的石油与含水层地质学家非常关注缝合线，因为**缝合线面上的不溶残余物可能阻碍流体渗流**（尽管这个渗透率影响也许没有一般认为的那么大——Heap et al., 2014）。

### 2.5 破裂与主应力方向的关系（本周最核心的一条）

Slide 11——**这是本周必须背到条件反射的三条**：

1. **张裂隙沿最小主压应力 σ₃ 方向张开**（阻力最小的方向），并**在 σ₁–σ₂ 平面内扩展**。
2. **收缩破裂垂直于最大主压应力 σ₁ 形成**（即位于 σ₂–σ₃ 平面内）。
3. **剪裂隙与 σ₁ 的夹角小于 45°，理想情况下含 σ₂**（即 σ₂ 平行于破裂面）。

在张性条件下，第 1 条意味着**张开方向就是拉伸方向**。

notes 里给了那句结构地质学里反复出现的警告：

> "To be strictly accurate, **what we see when observing fractures is strain not stress**, and so in making the points on this slide, we are implicitly assuming that the axes of stress and strain coincide. This is OK in this class because we are considering fractures with **very small displacements** across them."

——位移很小是这个假设成立的前提；对大应变构造就不能这么用了。

### 2.6 野外如何识别"位移量不出来"的剪裂隙

Slide 12。当位移太小无法直接量测时，剪切位移由两类小构造**间接指示**：

- **雁列式张性节理阵列（en échelon arrays of tension gashes）**
- **羽状破裂（pinnate fractures）**，又叫 **feather fractures**（羽毛破裂）——notes 解释了这个名字：它们的方位指示运动方向，就像箭杆上的**飞羽**一样。**羽状破裂的方位与张性节理相同。**

这些阵列**常成共轭对出现，两者夹角 40°–60°**。

**运动学判读的黄金法则**（Slide 12 结论，必背）：

> 张性节理的**张性**性质 + 与之**正交**的缝合线的**收缩**性质 → **最大主压应力 σ₁ 平分共轭对的锐角，σ₃ 平分钝角。**

Pembrokeshire 的 West Angle Bay 石炭系灰岩是经典露头：张性节理与缝合线正交，说明**单条**是张裂隙；但它们的**雁列排列**说明**整个阵列**是**左行剪切**。这是"单体 vs 阵列"两个尺度上运动学含义不同的典型例子——考试很爱考。

### 2.7 共轭脉阵列的几何分类（θ, ψ, δ）

Slide 13 引入 Srivastava (2000) 的分类。真实的共轭脉阵列偏离理想情形（理想 = 每个阵列内的脉彼此平行、且平行于平分面，即 Type 2）。用三个角描述，**收敛型（convergent）阵列**满足：

$$(\theta/2) + (90° - \delta) + (\psi/2) = 90°$$

- 所有天然阵列都满足 **θ ≤ 90° 且 ψ ≤ 90°**，因此落在三角图上的阴影区内；
- **迄今没有报道过天然的发散型（divergent）阵列**；
- notes 说明 **Type 3（θ = 0°）只是端元定义，不可能真实存在**——因为它意味着两个互为共轭的阵列彼此平行却有相反的剪切指向，自相矛盾。

⚠️ 注意：**这里的 θ 是阵列几何角，与莫尔图上"σ₁ 与破裂面法线的夹角 θ"完全不是一回事**，千万别混。

### 2.8 实验中的剪裂隙：为什么不在 45°？

Slide 14——**本周概念的枢纽**。

> "Samples deformed experimentally in axial compression at elevated confining pressure form shear fractures at **20°–30° to the maximum compressive stress**."

在这类**轴向压缩（axial compression）**实验中：**σ₁ = 轴向应力，σ₂ = σ₃ = 围压（confining pressure）**。所以破裂面上的正应力与剪应力可以直接由破裂面与 σ₁ 的夹角在莫尔图上读出。

**核心问题与答案：**

> "**Why don't fractures form at the orientation for which the shear stress on the fracture plane is greatest = 45° to σ₁ (2θ = 90°)?** On a fracture plane at ~30° to σ₁ (2θ = 120°), although the shear stress is **slightly smaller**, the **normal stress is much smaller**."

notes 给出物理原因：

> "The normal stress acts to **push the two sides of the fracture together**. Since **fracturing involves a volume increase**, the normal stress on the fracture plane acts to **suppress** fracturing (fracturing becomes easier as normal stress is decreased)."

即：破裂需要体积膨胀（扩容 dilatancy），而正应力把两壁压在一起、反对膨胀。所以真正的破裂面是"剪应力尽量大、正应力尽量小"的**折中**方位，而不是纯粹剪应力最大的 45° 面。

**角度约定（这是本课最容易翻车的地方，Slide 14 notes 专门强调）：**

> "Remember from Ex.1 of the Stress practical last week that **2θ is 120° for a shear plane formed at 30° to σ₁ because θ is the angle between σ₁ and the normal to the plane (= 60°)**."

即本课的 **θ = σ₁ 与破裂面法线的夹角**；破裂面与 σ₁ 的夹角记作 **α = 90° − θ**。破裂面与 σ₁ 成 30° ⇒ θ = 60° ⇒ **2θ = 120°**。

### 2.9 围压效应与破坏包络线

Slide 15。把不同围压下破坏时刻的（σₙ, τ）点画在莫尔图上，连成的曲线就是**破坏包络线（failure envelope）**。

实验显示随围压增大，破裂型式**连续渐变**：

| 围压 | 破裂类型 | 破裂面与 σ₁ 的夹角 |
|---|---|---|
| 最低 | **张裂隙（extension fracture）** | **平行于 σ₁**（即 0°） |
| 中等 | **混合型（hybrid extension + shear）** | **< 13°** |
| 较高 | **剪裂隙（contractional shear fracture）** | **> 13°** |

notes 的三条说明必须掌握：

1. **破裂在莫尔圆与包络线相切的那个点所对应的方位形成**（图上的实心点）。
2. **围压 = σ₃**，即每个圆左端与 σₙ 轴的交点。**围压升高 → 破裂面上的正应力升高 → 抑制破裂 → 需要更大的差应力（σ₁ − σ₃，即莫尔圆直径）才能破坏。**
3. 三个绿色的莫尔圆代表三种不同的**张性破坏模式**，具体哪一种发生取决于 σ₁ 与 σ₃ 之差（即圆的直径）。

### 2.10 孔隙流体压力与有效应力

Slide 16——**本周第二个枢纽**。

**问题**：张裂隙是"张开的"，按理只能出现在浅部（围压小）。**但岩墙和脉一直到地幔深度都有。为什么？**

**答案：孔隙流体压力（pore fluid pressure）。**

> "Pore fluid pressure acts **against the normal stresses**, while **leaving the shear stresses unaffected** → on a Mohr diagram pore fluid pressures **shift the Mohr circle left without changing its diameter** (if the diagram is plotted with σₙ,eff not σₙ on the x-axis)."

notes 给了物理原因，一句话：**"Fluid pressure acts outwards in a direction everywhere normal to the pore surface. Hence it affects only the normal stresses."**——流体压力处处垂直于孔壁向外作用，所以只影响正应力，不影响剪应力。

**两种破坏结局**（取决于圆左移到接触包络线时，有效 σ₃ 的正负）：

- 接触包络线时 **σ₃,eff = σ₃ − p_fluid 仍为压性（正）** → 形成**剪裂隙**；
- 接触包络线时 **σ₃,eff 已为负（张性）** → 形成 **hybrid 或张裂隙**。

notes 里的现实案例：**人工水库诱发地震**——湖水沿破裂下渗，抬高孔隙流体压力，最终触发地震（阿斯旺大坝是经典研究对象）。

### 2.11 什么过程会抬高孔隙流体压力？

Slide 17 列了五条，**讲义明说"An important first step in interpreting natural fractures is to consider the potential significance of each of these"——即野外解释破裂的第一步就是逐条考虑这五条**：

1. **压实与胶结（compaction and cementation）**：孔隙体积减小 → 孔压升高。
2. **剥蚀（erosion）**：移除上覆负荷（降低围压），若流体漏不掉，则孔压的**相对**重要性升高。
3. **渗透（osmosis）**：不同盐度的水体被半透膜（如富黏土层）隔开，流体从低盐度侧向高盐度侧扩散。
4. **成岩或变质反应产生流体**：含水矿物脱水（黏土、云母、角闪石）与熔融反应。
5. **加热时孔隙流体与围岩的热膨胀差异。**

### 2.12 破裂面形貌：羽状构造与终止线

Slide 19–20，这是**野外读破裂扩展史**的技能。

- **羽状构造 / 羽饰（plumose structure / hackle plume）**：张裂隙面上一组从中央轴发散的细微脊与槽（**hackle 羽痕**），**指示破裂扩展方向**。
- **羽状边缘（hackle fringe）**：在破裂面边缘，破裂面可能分裂成一系列相对主面稍有扭转的小面，形成雁列式张裂隙组成的边缘带；边缘小面上还可发育**二级羽状构造**。
- **肋痕（rib marks）**：横切羽痕线，剖面上呈尖棱形或由光滑弯曲的斜坡组成，**垂直于**羽痕线。解释为**停顿线（arrest lines）**——破裂扩展暂时停止时形成。
- **波痕（ripple marks，又称 Wallner lines）**：圆滑、**斜交**羽痕线，被认为形成于**极快速的破裂扩展**。

⚠️ notes 的野外提醒："If you see a ripple mark on a fracture face, **be careful to record in your notebook that this is not the sedimentary kind of ripple**."（不是沉积波痕！）

- **交切破裂面上的羽痕可以确定破裂形成的相对时序。**

破裂扩展的力学图景（notes）：理想情况下张裂隙从某个成核点**径向**扩展，任一瞬间的扩展前缘呈**椭圆**；扩展速率随破裂长大而增加，故破裂面越来越粗糙；最终扩展快到裂尖遇到界面（如层面）时的应力振荡/调整使破裂弯折扭转，形成羽状边缘。

### 2.13 破裂形状、扩展方式与层厚控制

Slide 21（张裂隙）：

- 破裂**一般近似为椭圆形**，羽痕与肋痕的系统分析支持这一点。
- **张裂隙在自身平面内扩展（propagate in their own plane）。**
- **主节理（master joints）**：长 10 cm 级 – 100 m 级、重复间距 cm 级 – 10 m 级的张裂隙。
- **在互层序列中，破裂垂直于层理方向的尺寸可能受层厚限制。**Pembrokeshire 的照片显示破裂基本被限制在灰岩单元内、不进入泥岩。

Slide 22（剪裂隙）——**与张裂隙的关键反差**：

> "In contrast, **shear fractures cannot propagate in their own plane** but instead propagate either by generating **new extension cracks at their tips (wing cracks)** or by **linking up already existing extension cracks**."

剪裂隙末端的位移被分散到许多更小的破裂上，有三种排布：

| 形式 | 英文 | 特征 |
|---|---|---|
| **分叉（同向剪破裂）** | splaying / synthetic shear fractures | 与主破裂同剪切向 |
| **马尾构造** | horsetailing | 破裂**一侧**的张裂隙群 |
| **反向剪破裂** | antithetic shear fractures | 与主破裂反剪切向 |

notes：wing crack 的形成反映**椭圆孔（裂纹）周围的应力分布**；**断层也常常以这三种破裂组终止**。

### 2.14 破裂之间的相互作用

Slide 23：破裂周围的应力场被扰动。新破裂朝已有破裂生长时，会遇到已有破裂设置的**局部扰动应力场**，并**弯曲以保持与局部 σ₃ 成 90°**。弯曲的方向与幅度取决于远场主应力的相对大小与方位——**因此破裂的弯曲可以反过来提供古应力信息**。

notes 的三种情形：若老破裂是**张开的**（不能承受剪应力）且局部张应力沿老破裂作用，新破裂以 **90°** 相交；若沿老破裂作用的是压应力，则以 **0°** 相交；若老破裂是**闭合的**、能承受剪应力，则 **0°–90° 之间任何角度**都可能。

Slide 24（平行破裂的相互作用）：弯曲形态取决于 **σₓ − σ_y 的符号**（σₓ 平行于破裂）。法国 Barrême 的泥裂照片显示 σₓ − σ_y < 0 的情形——**泥裂中所有应力当然都是张性的**。

### 2.15 破裂密度、间距与方位的定量描述

**密度（Slide 25）**——工程与流体流动应用的核心：

- 通过统计**与一条测线相交的破裂数**估算；**测线最好是圆形（circular count line）**，以避免采样面方位带来的"**切割效应（cut effects）**"。Ramsay & Huber 的图说明：**不同方位的面上，看到的破裂频度与破裂组数完全不同。**
- 若同时统计**破裂端点（tips）**与**破裂交点（intersections）**，就能刻画**破裂网络的拓扑（topology）**并评估**连通性（connectivity）**。
- **拓扑节点三类**：**I 节点**（破裂端点）、**Y 节点**（一条破裂终止于另一条）、**X 节点**（一条破裂横穿另一条）。三者比例画在三角图上区分不同的破裂网络类型。
- notes 的诚实提醒："deciding **what is or is not a fracture** in an image or indeed in real life, can have a **heavy element of subjectivity**."

**间距（Slide 26）**：

> "Fracture spacing changes with **bed thickness** and **bed rigidity**, and is influenced by the nature of the **interfaces between beds** → changes during **diagenesis**."

Somerset 的 Lilstock Bay：**厚层的节理间距更宽**；另一张照片显示**节理间距 ≈ 层厚**。

**方位（Slide 27）**：

- **破裂组（fracture set）** = 一组产状（走向/倾角）相似的破裂。
- **近直立**的破裂方位方便用**玫瑰图（rose diagram）**表示；**非直立**的破裂最好用**赤平投影图（stereogram）**。
- 同成因的破裂方位**可能随岩性改变**（照片显示破裂在不同岩性中"折射 refraction"），所以**画图前最好按岩性分开**，或画**分裂玫瑰图（split rose diagram）**。

### 2.16 构造环境中的破裂：三类典型产状

**(a) 轻微变形的沉积岩（Slide 28–29）**

水平层状、几乎未变形的沉积序列的一大特征是**发育良好的近直立破裂组**。成因链条（承接 Class 5 Slide 29 的**单轴应变参考态 uniaxial strain reference state**）：

1. 在无构造应力时，埋藏与随后剥蚀/隆升过程中的**泊松效应（Poisson effect）**与温度变化，导致 **σ₁ 铅直、σ₃ 水平**（notes：单轴应变参考态下水平应力约为铅直应力的 **0.33–0.5 倍**）；
2. 若孔隙流体压力足够大，使**有效 σ₃ 变为张性**，则形成**垂直于 σ₃ 的直立破裂组**；
3. 这**释放了该方向的应力**，于是若另一个水平主有效应力也是张性的，它就成为**最大有效张应力**，从而形成**与第一组正交的第二组直立节理**。

Slide 29 把模型推广到含**岩石圈挠曲应力**或**远场应力**的情形：Hafner (1951) 对受水平压缩的矩形板的应力分析可以预测**前陆沉积序列**内的应力：σ₁ ~ 水平，且由于 σ₂ ~ σ₃，可以论证 σ₃ 也水平，因此**破裂应为直立**。**靠近逆冲前锋处 σ₁ 大 → 直立共轭剪裂隙；远离前锋 σ₁ 减小 → 直立张裂隙。**这解释了为什么轻变形沉积序列中会出现**非正交的直立破裂组**。

**(b) 断层伴生破裂（Slide 30）**

除张性节理与羽状破裂外，断层周围常有一组**间距很密的断层平行破裂**，以及一组发育较弱的、处于**共轭方位、与断层约成 60°** 的剪裂隙。对**倾滑断层**，用一张**特殊定向**的玫瑰图最方便：**该平面包含滑移矢量与断层面法线**。notes 的方法论评价："This rose diagram shows the virtue in being **imaginative in selecting the plane** for the diagram – **it does not have to be the horizontal plane**."

**(c) 褶皱伴生破裂（Slide 31）**

| 名称 | 定义 |
|---|---|
| **纵向（bc）节理 longitudinal joints** | 平行于褶皱枢纽、正交于层理 |
| **横（ac）节理 cross joints** | 平行于**剖面（profile plane）** |
| **两组共轭斜节理** | 一对被 **bc 节理平分**（见于**褶皱枢纽**）；另一对被 **ac 节理平分**（见于**褶皱翼部**） |
| 其他 | 褶皱枢纽的**内弧与外弧**可有其他破裂组 |

讲义的诚实结论：**"Considerable uncertainty exists over how these fracture sets form and when they form relative to the growth of the fold."** notes 里的 take-home message 也是本课这一整节的立意：

> "The important point to take home from this class is that **when mapping do not ignore minor fractures. They have an important influence on rock properties even if their formation is not yet fully understood.**"

**(d) 剥离（席状）节理 exfoliation / sheet joints（Slide 32）**

定义：跨越数百米平滑弯曲、**近平行于地形面**的张裂隙，在**深成岩（plutonic rocks）**中最典型（Bodmin Moor 花岗岩、Yosemite 的 Half Dome）。

力学解释见 §3.6。

### 2.17 脉、水力压裂与角砾岩化

Slide 34：

- 破裂面上的薄矿物沉淀（石英、长石、方解石、沸石）**指示流体在破裂形成时的重要作用**——但要加一个前提："assuming that the fluids did not come in later and use the fractures as conduits"（**流体也可能是后来才沿破裂通道进来的**）。
- **脉的形成机制**：**流体压力升高到足以生成张裂隙（= 水力压裂 hydraulic fracturing）**，然后矿物从溶液中沉淀出来——因为**多数情况下溶解度随流体压力降低而降低**（即破裂张开时溶解度下降 → 析出）。
- **在流体压力极高的地区，水力压裂过程中可发生构造角砾岩化（tectonic brecciation）。**

notes 的警告值得记：**"Since veins and joints are both extension fractures, it is tempting to treat them in the same way. However, they form at different times and under different conditions."**——脉与节理虽同为张裂隙，但形成时间与条件不同，不能一概而论。

变质杂岩中的脉的成因链：变质反应生成的石英溶于深部孔隙流体，随流体上升冷却/降压而在脉中沉淀。

### 2.18 小型侵入体的就位：岩墙与岩床

Slide 35 的核心命题：

> "Intrusion of magma as planar sheets requires the magma to flow into a **pre-existing open fissure** or to be **forcefully injected**. Since **open fissures cannot exist at depth**, the emplacement of such sheets must usually include at least a component of **forceful injection, that is, of hydraulic fracturing**."

——深部不可能有张开的裂缝，所以席状侵入体的就位**必然含强力注入（= 水力压裂）成分**。

**驱动力：浮力（buoyancy）**（Slide 37）

> "Buoyancy = **magma pressure minus vertical stress in the surrounding rock**, and so it arises from the **lower density of the magma compared with its host rock**."（推导中假定岩浆房内压力为**静岩压力 lithostatic**。）

**岩墙与岩床的条件**见 §3.7。

Slide 36 有一个易被忽略的定义提醒：图中的两个例子里**层理是直立的**，所以那个"sill"其实是**不整合的（discordant）**、那个"dyke"其实是**整合的（concordant）**。⚠️ **dyke/sill 是按产状（近直立/近水平）定义的，不是按与层理的整合关系定义的**——这两套概念在这里正好错开。

### 2.19 水力裂缝的偏转与终止

Slide 40–42。当扩展中的水力裂缝遇到局部应力不利于继续扩展的层时，它可以：**停止（arrest）**、**穿过接触面（penetrate）**、或**沿接触面偏转（deflect）**（单向或双向）。

三个控制因素：

1. **力学不连续面（如层面）附近主应力局部方位的改变**（同 Slide 23 的机制）。
2. **分层剥离（delamination）/ Cook–Gordon 脱粘**：扩展中的水力裂缝**裂尖前方产生的张应力**，通过**泊松效应**在**平行于裂缝的方向**上也诱发张应力；若该方向抗张强度小（例如存在界面），就会张开一条裂缝，**侵入体于是侧向扩展**。（notes 定义："By 'Poisson effect', I am referring to the observation that stretching in one direction leads to contraction in the direction at right angles to this."）
3. **材料性质失配（material property mismatch）**：扩展中的裂缝遇到**弹性上更硬（stiffer）**的层时，**沿界面偏转在能量上更有利**；遇到**更柔顺（compliant）**的层则不然。

**解释陷阱**（Slide 43）：侵入体沿破裂偏转会造成判读困难——地图上的辉绿岩墙看起来被沟里的断层左行错开了，但**很可能只是利用了先存破裂**。Slide 44 给了判据：Glen Coe 的岩墙，**墙壁上的台阶可以跨岩墙对应起来**，从而证明容纳岩墙的那条破裂是 **hybrid（左行张扭）**。

**雁列岩墙（en échelon dykes）**（Slide 45–47）：

- 成因之一：岩墙向地表扩展时**应力场发生旋转**（机制类似羽状边缘的形成）。**这种机制与真正的张扭（transtension）能否区分尚不清楚。**
- 雁列岩墙阵列有一整套术语：**bridge（桥）、horn（角）** 等。
- 阵列中各条裂缝扩展并进入彼此的应力场时会像"干"破裂一样弯曲，而**弯曲的性质对"扩展受远场应力控制还是受岩浆压力控制"很敏感**——Glen Coe 那对雁列岩墙利用了一条横节理连通，**说明扩展主要受远场（构造）应力控制**。

### 2.20 多边形破裂网络与柱状节理

Slide 49–51。**冷却或干缩引起的收缩**导致**正交（orthogonal）或多边形（polygonal）破裂网络**。火星上的图案化地面（patterned ground）：较大的正交阵列被解释为湖泊干涸时的**干缩裂缝**，较小尺度的多边形网络则被归因于**周期性热胀冷缩**（notes 老实说："I am not sure if the interpretation … has stood the test of time"）。

**演化机制（Slide 50）**：

- 裂缝在**缺陷（flaws）**处成核；朝先形成的裂缝扩展时**弯曲以与之正交相交**——因为**最小主应力平行于先存裂缝的自由面**。
- notes 的完整论证很漂亮：张开裂缝的自由面不能承受剪应力，故必有一个主应力方向与之正交、另一个与之平行；由于裂缝张开，正交于裂缝的主应力 ≈ 0；由于裂缝在地表，铅直应力（也是主应力）也 ≈ 0；剩下**平行于裂缝**的那个主应力——在收缩的泥中它是**张性的**，而其余都 ≈ 0，所以它必为 **σ₃**。因此逼近的裂缝会与它**成直角**相交 → **直角网络（顶角 90°）**。
- 在**反复的张开/闭合循环**中，先前张开的裂缝构成弱面，使网络逐步调整为**多边形（顶角趋近 120°）**。

📎 背景补充：讲义提到的 **syneresis cracks（脱水收缩裂缝）**是水下形成的多边形裂缝——含膨胀性黏土（如蒙脱石）的泥在接触水的盐度升高时会收缩（盐度升高使黏土颗粒絮凝解体并使膨胀黏土晶格收缩）。这在浅海或湖相地层中可见，但也有模型认为它们其实是**地震诱发的泥质排水**产物。

**柱状节理（columnar jointing，Slide 51）**：

> "For **homogeneous media containing few flaws** (e.g., crystallizing melts), **rapid nucleation and propagation of multiple cracks from a few points of initiation** → polygonal fracture patterns – this is the geometry that **releases maximum strain energy per unit crack area**."

> "These extension fractures (columnar joints) form **perpendicular to surfaces of equal temperature** (often perpendicular to the interface with the country rock)."

notes 补充：~120° 顶角的多边形花样在"给定平面内各方向收缩量近似相同"时快速形成——在冷却岩浆中，这在**等温面内**成立。破裂在**冷却速率最快处**（如熔岩流的顶与底）成核，并向岩浆体**冷却最慢的部位**扩展。Staffa 的 Fingal's Cave 与 Giant's Causeway 是经典露头；Staffa 上还有**不铅直的**柱状节理。

---

## 三、公式与图表

**这一段是本周的重心。目标是：合上材料也能自己把莫尔圆 + 破坏包络线画出来、把 Anderson 三态画出来、把每个数算出来。**

### 3.1 Coulomb 破坏准则

$$\boxed{\ \tau \;=\; \tau_0 \;+\; \mu\,\sigma_n \;=\; \tau_0 + \sigma_n \tan\phi\ }$$

| 符号 | 名称 | 单位 | 说明 |
|---|---|---|---|
| **τ** | 破裂面上的**剪应力（shear stress）** | MPa | 破坏时刻的值 |
| **σₙ** | 破裂面上的**正应力（normal stress）** | MPa | 有孔隙流体时须换成**有效正应力 σₙ,eff** |
| **τ₀** | **内聚力 / 内聚强度（cohesive strength）** | MPa | 包络线在 τ 轴上的**截距**；= σₙ = 0 时岩石能承受的剪应力 |
| **μ** | **内摩擦系数（coefficient of internal friction）** | 无量纲 | 包络线的**斜率** |
| **φ** | **内摩擦角（angle of internal friction）** | ° | 包络线与 σₙ 轴的夹角，**μ = tan φ** |

**⚠️ μ 与 φ 是同一件事的两种写法，μ = tan φ，绝不可混用数值。**本课的典型值：**φ ≈ 30° ⇒ μ ≈ 0.58**（Anderson.md 用的就是这一组）；Ex1 那块砂岩拟合出 **φ = 37.29° ⇒ μ = 0.7616**。

**符号说明**：本课把内聚力写作 **τ₀**（Ex1soln、Class 7 都用 τ₀）。📎 背景补充：许多教科书写作 **C** 或 **S₀**，含义完全相同；任务说明里给的 `τ = C + μσ_n` 与本课的 `τ = τ₀ + μσ_n` 是同一个式子。

**适用条件**：(1) 只适用于**脆性（cataclastic）**变形域，即较冷、较浅的地壳；(2) 只在包络线**近似为直线**时成立——真实岩石的包络线略呈弯曲，此时写成 **τ = f(σₙ)** 的一般形式称为 **Mohr–Coulomb 准则**（Class 7 Slide 明确区分了这两个名字）；(3) **张性区（σₙ < 0）不适用**，那里包络线弯向张性截止点。

### 3.2 σ₁ = a + bσ₃ 与 τ = τ₀ + σₙ tanφ 的等价（Ex1 (c) 的完整推导）

⚠️ Ex1soln 的 (c) 小问在 PDF→md 转换中**丢失了全部方程**（只剩"Hence from elementary trigonometry"、"so that rearranging"这类连接词）。以下按材料保留下来的中间步骤（第 54、60、64 行）**完整复原**：

**莫尔圆几何**：圆心在 σₙ 轴上的 **(σ₁+σ₃)/2**，半径 **(σ₁−σ₃)/2**。破坏包络线 τ = τ₀ + σₙ tanφ 与 σₙ 轴交于 **σₙ = −τ₀/tanφ**。破坏时圆与包络线**相切**，故从该交点到圆心的距离在 φ 角处张开的直角三角形给出：

$$\sin\phi \;=\; \frac{(\sigma_1-\sigma_3)/2}{\dfrac{\sigma_1+\sigma_3}{2} + \dfrac{\tau_0}{\tan\phi}}$$

交叉相乘（材料第 54 行）：

$$\sigma_1 - \sigma_3 \;=\; \sigma_1\sin\phi + \sigma_3\sin\phi + 2\tau_0\cos\phi$$

整理出 σ₁：

$$\sigma_1 \;=\; \underbrace{\frac{2\tau_0\cos\phi}{1-\sin\phi}}_{a} \;+\; \underbrace{\frac{1+\sin\phi}{1-\sin\phi}}_{b}\;\sigma_3$$

（材料第 60 行给的正是 **a = 2τ₀cosφ/(1−sinφ)，b = (1+sinφ)/(1−sinφ)**。）

用恒等式 **cos²φ = 1 − sin²φ = (1+sinφ)(1−sinφ)** 化简，得到两个**实用反解公式**（这就是材料 (c) 想让你得到的结果）：

$$\boxed{\ \sin\phi = \frac{b-1}{b+1}\ }\qquad \boxed{\ \sqrt{b} = \frac{1+\sin\phi}{\cos\phi} = \tan\!\left(45°+\frac{\phi}{2}\right)\ }\qquad \boxed{\ \tau_0 = \frac{a}{2\sqrt{b}}\ }$$

**自行复算验证**（用材料的 a = 210 MPa、b = 4.075）：

- sinφ = (4.075 − 1)/(4.075 + 1) = 3.075/5.075 = **0.60591** → φ = **37.294°** ✅ 材料写 37.29°
- μ = tan 37.294° = **0.76164** ✅ 材料写 0.7616
- τ₀ = 210/(2√4.075) = 210/4.0373 = **52.01 MPa** ✅ 材料写 52 MPa

**三式全部与材料吻合。**

📎 背景补充：还有一个漂亮的等价形式——因为 **α = 45° − φ/2**（见 §3.3），所以 **√b = tan(45° + φ/2) = cot α**，即 **b = cot²α**。用 α = 26.355° 验算：cot 26.355° = 2.0187，平方 = 4.075 ✅。考试时若已知破裂角，可以直接跳过 φ 求 b。

### 3.3 破裂角公式（本周最容易记错的一条）

$$\boxed{\ \alpha \;=\; 45° - \frac{\phi}{2}\ }\qquad\text{其中 }\alpha = \sigma_1\text{ 与破裂面的夹角}$$

推导（Class 7 notes 给的一句话论证）：**三角形内角和 180°**——莫尔图上，包络线切点、圆心、σₙ 轴构成的三角形中，圆心角 = 2θ；由包络线倾角 φ 可得 **2θ = 90° + φ**，故 **θ = 45° + φ/2**，而 **α = 90° − θ = 45° − φ/2**。

配套的角度换算（**务必分清**）：

| 符号 | 定义 | 与 φ 的关系 | φ = 30° 时 | φ = 37.29° 时 |
|---|---|---|---|---|
| **α** | σ₁ 与**破裂面**的夹角 | α = 45° − φ/2 | **30°** | **26.35°** |
| **θ** | σ₁ 与**破裂面法线**的夹角 | θ = 45° + φ/2 | **60°** | **63.65°** |
| **2θ** | 莫尔图上的**圆心角** | 2θ = 90° + φ | **120°** | **127.29°** |
| **共轭锐角** | 共轭剪裂隙对的夹角 | 2α = 90° − φ | **60°** | **52.7°** |

**共轭锐角（≈ 60°）由 σ₁ 平分，钝角由 σ₃ 平分，σ₂ 平行于两破裂面的交线。**

⚠️ **α 与 45° 的关系**：α **总是小于 45°**（因为 φ > 0）。**最大剪应力面（α = 45°，2θ = 90°）不是实际破裂面**——见 §2.8 与 §6.1。

### 3.4 有效应力（effective stress）

$$\boxed{\ \sigma_{n,\text{eff}} \;=\; \sigma_n - p_{\text{fluid}}\ }\qquad \boxed{\ \sigma_{1,\text{eff}} = \sigma_1 - p_f,\quad \sigma_{3,\text{eff}} = \sigma_3 - p_f\ }\qquad \boxed{\ \tau_{\text{eff}} = \tau\ }$$

**莫尔图上的表现（本周必须画得出来）：**

- **孔压 p_f 升高 → 圆整体向左平移 p_f，直径（= σ₁ − σ₃）不变。**因为 σ₁ 与 σ₃ 各减去同一个 p_f，差不变、圆心左移。
- **剪应力完全不受影响**（流体压力处处垂直孔壁）。

**静水压孔压（连通到地表的"正常压力"流体）：**

$$p_f \;=\; \rho_{\text{water}}\, g\, z$$

**铅直应力（岩石柱重量）：**

$$\sigma_V \;=\; \rho_{\text{rock}}\, g\, z$$

**单位换算**（Ex1 特意提醒）：1 Pa = 1 N m⁻²，1 N = 1 kg m s⁻²。所以 ρ 必须用 **kg m⁻³**（2.3 g cm⁻³ = **2300 kg m⁻³**）、z 用 **m**，算出来是 Pa，再除 10⁶ 得 MPa。

**孔压参数 λ（石油工业常用）：**

$$\boxed{\ \lambda \;=\; \frac{p_{\text{fluid}}}{\sigma_V}\ }$$

- 正常压力（流体连通到地表）：**λ ≈ 0.43**（水/岩密度比 1.0/2.3）；
- **λ > 0.43 → 超压（over-pressured）**，钻孔打穿时可能"喷"；
- **λ 上限 → 1**：因为若 p_fluid > σ_V，岩石处于**张性**状态，而**岩石抗张极弱**。

### 3.5 莫尔圆 + 破坏包络线的完整图解（读图与画图指南）

```
   τ (MPa)
    ↑
    │              破坏包络线  τ = τ₀ + σn tanφ
    │                    ╱
    │             ╱ ╱ ← 斜率 = μ = tanφ
    │        ╱ ╱   ●  ← 切点 = 破裂发生的方位 (σn, τ)
    │   ╱ ╱     ╱‾ ‾╲
 τ₀ ├╱ ╱      ╱   ╲ ╲              ← 截距 = 内聚力 τ₀
    │╱      ╱  ·C   ╲ ╲
────┼──────┼────┼────┼──────────→  σn (MPa)
   0│      σ₃   C    σ₁
    │                  C = 圆心 = (σ₁+σ₃)/2
    │                  半径 R = (σ₁−σ₃)/2  = 差应力的一半
    │  ← 张性区 (σn < 0)
```

**画图五步：**

1. 在 σₙ 轴上标出 **σ₃**（左端）与 **σ₁**（右端），**圆心 C = (σ₁+σ₃)/2**，**半径 R = (σ₁−σ₃)/2**。
2. 画包络线：**τ 轴截距 = τ₀**，**斜率 = μ = tanφ**（上下对称，实际用上半支即可）。
3. **判断是否破裂**：
   - **圆完全落在包络线以下 → 稳定，不破裂**；
   - **圆与包络线相切 → 恰好破裂**；
   - **圆穿过包络线 → 该应力状态在物理上不可达**（岩石早已破坏）。
4. **读破裂面方位**：从**圆心**向**切点**连线，该半径与 **+σₙ 轴**的夹角就是 **2θ**（本课约定**逆时针为正**）。则 **θ = 2θ/2 = σ₁ 与破裂面法线的夹角**，**破裂面与 σ₁ 的夹角 α = 90° − θ**。
5. **读切点坐标**：切点的横坐标 = 破裂面上的 **σₙ**，纵坐标 = 破裂面上的 **τ**。也可用公式（见 §3.8）。

**两条触发破裂的路径，在图上表现完全不同——这是本周最重要的一对对比：**

| 路径 | 物理过程 | 莫尔图表现 | 典型情景 |
|---|---|---|---|
| **(A) 差应力增大** | 构造加载使 σ₁ 升高（或 σ₃ 降低） | **圆变大**（直径 σ₁−σ₃ 增加），圆心可能移动 | 构造挤压/伸展持续进行 |
| **(B) 孔压升高** | p_fluid 增加 | **圆平移向左，直径不变** | 水力压裂、水库诱发地震、超压储层 |

**围压变化（第三条路径）**：围压 = σ₃。**围压升高 → 圆整体右移 → 需要更大的直径才能碰到包络线 → 岩石"更强"**（Slide 15 notes 明说）。这就是为什么深部岩石比浅部难破裂。

**张性域与剪切域的分界**（Slide 15 + Slide 16）：

- 若圆**整体落在 σₙ < 0（张性）区**并触到包络线的张性端 → **张裂隙（Mode I），破裂面平行于 σ₁**（即 α = 0°）；
- 若触及包络线时 **σ₃,eff 已为负但圆跨越 σₙ = 0** → **hybrid 破裂，α < 13°**；
- 若触及包络线时 **σ₃,eff 仍为正（压性）** → **剪裂隙，α > 13°**（并趋近 45° − φ/2 ≈ 26°–30°）。

📎 背景补充：**Griffith 准则（Griffith criterion）**——任务提到的张性场破坏准则**在 Class 6 讲义中并未出现**；Class 7 的 notes 只提到"椭圆孔周围的应力分析构成了**最重要的脆性破坏理论之一（Griffith 的理论）**的基础"，但**没有给出方程**。其标准形式为：

$$\tau^2 = 4T(\sigma_n + T)\quad\text{（抛物线）},\qquad \text{当 }3\sigma_3 + \sigma_1 < 0\ \text{时退化为 }\sigma_3 = -T$$

其中 **T = 抗张强度（tensile strength）**，且 **τ₀ = 2T**。**复合 Griffith–Coulomb 包络线**即：**张性段（σₙ < 0）用 Griffith 抛物线，压性段（σₙ > 0）用 Coulomb 直线**，两者在过渡区平滑衔接——这正是 Slide 15 那条"随围压连续渐变（张 → hybrid → 剪）"的曲线的解析表达。**本课材料只画了这条曲线的形状、没有给方程，考试按讲义的定性描述作答即可。**

### 3.6 剥离节理的应力公式（Slide 32）

深部岩浆中应力为**静岩（lithostatic）**（把岩浆视为无剪切强度的流体）：

$$\sigma_1 = \sigma_2 = \sigma_3 = \rho g h$$

剥露到地表后，岩体内的应力**变化量**为（假定**无侧向膨胀/收缩**，即单轴应变条件，同 Class 5 Slide 29）：

$$\Delta\sigma_v = -\rho g \Delta h\ ;\qquad \Delta\sigma_h = \left[\frac{\nu}{1-\nu}\right]\rho g \Delta h$$

于是（取 Δh = h，即完全剥露到地表）：

$$\sigma_v = \sigma_3 = 0\ ;\qquad \boxed{\ \sigma_h = \sigma_1 = \left[\frac{1-2\nu}{1-\nu}\right]\rho g h\ }$$

**推导**：σ_h = σ_h,initial − Δσ_h = ρgh − [ν/(1−ν)]ρgh = [(1−2ν)/(1−ν)]ρgh。

**数值验算**（讲义给 h = 5 km，ν = 0.25，ρ = 3 g cm⁻³）：

[(1 − 0.5)/(1 − 0.25)] × 3000 × 10 × 5000 = (0.5/0.75) × 150 MPa = 0.6667 × 150 = **100 MPa** ✅ 与讲义的 100 MPa 完全吻合（用 g = 10 m s⁻²）。

**结论**：**存在一个很大的水平压应力（σ₁ 水平、σ₃ = 0 铅直），可以驱动平行于地表的破裂**——这就是剥离节理。

| 符号 | 含义 |
|---|---|
| ρ | 密度 |
| g | 重力加速度 |
| h | 深度 |
| σ_v | 铅直应力 |
| σ_h | 水平应力 |
| **ν** | **泊松比（Poisson's ratio）**，典型 0.25 |

notes 提醒：**该分析忽略了剥露过程中的温度变化**；剥离节理还有其他成因模型。

### 3.7 岩墙与岩床的就位条件（Slide 38–39）

**岩墙（直立席状体）**：

$$\boxed{\ p_{\text{magma}} - \sigma_h \;>\; T_h\ }$$

其中 **T_h = 岩石在水平方向的抗张强度**。左边 **(p_magma − σ_h) 称为岩浆超压（magma overpressure, p_over）**。**岩墙注入发生在 p_over = T_h 时。**

超压的表达式（Gudmundsson Eq. 9.15，讲义只文字描述、公式在 md 中丢失）依赖 **E（杨氏模量 Young's modulus）**、**ν（泊松比）**、**A（岩墙宽度/开度 aperture）**、**W（岩墙走向长度 width）**。

**实测标定**：冰岛 Reykjanes 半岛 **Vogar 岩墙群**的野外测量 + 合理的 E、ν 值 → **p_over = 4 MPa**。讲义评论：**这个水平抗张强度值极小，也许反映了岩石本身已经破裂的状态**。推论：**既然所需的岩浆超压如此之小，水平岩石强度的微小变化就能深刻影响岩墙的延伸范围与方位。**

📎 背景补充：notes 给了一个实用技巧——若能估出岩墙的走向长度 W 与厚度 A，就能反算岩浆超压、进而得到围岩的水平抗张强度（E、ν 从文献查即可）。当 W 难测时，可用全球岩墙统计的经验值 **W/A = 1500**。

**岩床（水平席状体）**：

$$\boxed{\ p_{\text{magma}} - \sigma_v \;>\; T_v\ }$$

岩床必须由**供给岩墙（feeder dyke）**供给，故在岩床与岩墙的交汇处两式同时成立，相减得：

$$\boxed{\ \sigma_v - \sigma_h \;=\; T_h - T_v\ }$$

**由于岩石的抗张强度都很小（T_v、T_h 都小），岩床形成的条件就是 σ_v − σ_h ≈ 0。**

**完整的物理图景**（必背的一段逻辑）：

> 岩浆在 **σ_v > σ_h** 时以**岩墙**形式上升；但 **σ_v 向地表递减**，因此最终会到达 **σ_v − σ_h ≈ 0** 的位置，此时**岩床成为可能**；若进一步有 **T_h − T_v > 0**（水平层状序列中通常如此，因为层面是弱面、垂向抗张更弱），**岩床就更受青睐**。

### 3.8 应力分量公式（承接 Week 05，本周计算必用）

$$\boxed{\ \tau \;=\; \frac{\sigma_1-\sigma_3}{2}\,\sin 2\theta\ }\qquad\boxed{\ \sigma_n \;=\; \frac{\sigma_1+\sigma_3}{2} \;+\; \frac{\sigma_1-\sigma_3}{2}\,\cos 2\theta\ }$$

θ = σ₁ 与平面法线的夹角，**逆时针为正**（Ex1soln 的图上写着 "+ve: anticlockwise"）。

### 3.9 破裂密度的三个统计公式（Slide 25 notes）

用半径 r 的**圆形计数线**：

| 量 | 公式 | 说明 |
|---|---|---|
| **破裂迹强度 fracture trace intensity** | **n / (4r)** | n = 破裂与圆的**交点数** |
| **破裂迹密度 fracture trace density** | **m / (2πr²)** | m = 圆内的**破裂端点数** |
| **平均迹长 mean trace length** | **(n/m)·πr/2** | 可靠估计需 **m > 30** |

野外做法：带一根一米长的绳子和粉笔即可。m > 30 可通过在多个位置画多个圆并合并结果达到。

**其他定义**（notes）：fracture trace intensity = 单位面积的破裂总长度均值；fracture trace density = 单位面积的破裂中心数均值。

### 3.10 Anderson 断层分类的立体示意与莫尔图（Anderson.md 图版）

`Anderson.md` 的图版对三种情形都画了**三件事**：块体立体图 + 断层产状 + 莫尔图。统一参数：**σ_V = ρgz，φ = 30° ⇒ μ = 0.58，α = 45° − φ/2 = 30°**。

| Anderson 三态 | 铅直主应力 | 水平主应力 | 断层类型 | **断层倾角** | 莫尔图上 σ_V 的位置 |
|---|---|---|---|---|---|
| **伸展（Extensional）** | **σ_V = σ₁** | σ_H = σ₂，σ_h = σ₃ | **正断层（normal fault）** | **60°** | σ_V 在圆的**右端** |
| **挤压（Contractional）** | **σ_V = σ₃** | σ_H = σ₁，σ_h = σ₂ | **逆冲断层（thrust）** | **30°** | σ_V 在圆的**左端** |
| **走滑（Strike-slip）** | **σ_V = σ₂** | σ_H = σ₁，σ_h = σ₃ | **走滑断层（strike-slip fault）** | **90°（直立）** | σ_V 在圆**内部**（σ₃ 与 σ₁ 之间） |

**倾角怎么来的（自行复算验证）：**

- **正断层**：σ₁ 铅直，断层与 σ₁ 成 α = 30° → 断层与铅直线成 30° → **倾角 = 90° − 30° = 60°** ✅ 与 Anderson.md 图上标的 60° 吻合。
- **逆冲**：σ₁ 水平，断层与 σ₁ 成 α = 30° → 断层与水平面成 30° → **倾角 = 30°** ✅ 与图上标的 30° 吻合。
- **走滑**：σ₂ 铅直，而 σ₂ 平行于断层面 → **断层面必含铅直方向 → 直立**；断层走向与 σ_H（=σ₁）成 ±30°。

**Anderson.md 的一句关键批注**：走滑那一格写着 **"need some way of specifying σ₁ or σ₃"**。含义是：伸展与挤压两种情形中，铅直应力就是 σ₁ 或 σ₃，所以只要知道深度就把圆的一端钉住了；**但走滑情形中 σ_V = σ₂，而 σ₂ 不在莫尔圆（σ₁–σ₃ 圆）的任何一端上**，它只落在圆内部，**因此单靠 σ_V = ρgz 无法确定圆的位置，必须另外给定 σ₁ 或 σ₃**。这是三态里唯一需要额外信息的一种，非常适合出简答题。

**Anderson 分类的理论基础**（Class 5 Slide 32 notes）：

> Anderson 注意到，当假定一个主应力为铅直（地表平行方向无剪应力）时，主应力只有三种可能排布；若再假定**共轭断层以 ±30° 于 σ₁ 形成、且 σ₂ 位于每条断层面内（平行于两者交线）**，就得到三种断层几何。

**局限性**（notes 明说，考试的"批判性评价"分就在这里）：

> "the assumption that **σ₂ lies in the fault plane is an oversimplification** and cannot be true in the case where **three or more differently oriented faults** that do not share a common line of intersection are simultaneously active."

---

## 四、课堂补充

> **说明：本课全 10 周均无 transcript（无课堂录音转写）。本段内容全部来自讲义 notes pane 中被强调的注意事项、以及练习答案透露的评分要点与作图规范，不含任何口头讲解。**

### 4.1 讲义反复强调的野外注意事项

1. **不要忽略小型破裂。**Slide 5：学生在野外对这类小破裂"generally poorly described"，而它们有重大经济意义。Slide 31 notes 把这句话作为整节课的 take-home message 重复了一次。
2. **记录时区分野外能看到与看不到的东西。**Slide 9 的显微照片说明 ~10 µm 的剪切位移**在野外不可见**——所以野外定为"纯张裂隙"的东西，薄片下可能是 hybrid。写野外记录时不要把"看不到位移"写成"没有位移"。
3. **破裂面上的 ripple mark 不是沉积波痕**（Slide 20 notes 专门叮嘱），记笔记时必须写清楚，否则日后无法区分。
4. **玫瑰图的投影面不必是水平面。**Slide 30 notes："This rose diagram shows the **virtue in being imaginative in selecting the plane** for the diagram."——分析倾滑断层伴生破裂时，应选**含滑移矢量与断层面法线**的平面。
5. **画方位图前先按岩性分组**（Slide 27）：同成因破裂在不同岩性中方位不同，混在一起画玫瑰图会得出错误结论；正确做法是分岩性画，或画分裂玫瑰图。
6. **近直立破裂用玫瑰图，非直立破裂用赤平投影图**（Slide 27）——这是选图规则，别混。
7. **破裂密度统计要用圆形计数线**，避免采样面方位造成的 cut effects（Slide 25）；且计数面**不能平行于任何一组破裂**。
8. **"什么算一条破裂"本身高度主观**（Slide 25 notes）——报告数据时应说明判别标准。
9. **矿物脉不一定指示流体在破裂形成时就在**（Slide 34）："assuming that the fluids did not come in later and use the fractures as conduits"——解释时必须把这个替代假说写出来。
10. **岩墙被"错开"未必是断层**（Slide 43）：可能只是利用了先存破裂。判据是墙壁台阶能否跨岩墙对应（Slide 44）。
11. **野外工具清单**（Slide 25 notes）：做破裂密度统计只需"一米长的绳子/细绳 + 粉笔"。
12. **Easter 野外课预告**：Kentallen 岩体边部围岩中可见**高流体压力诱发的角砾岩化**（Slide 34 notes）；Glen Coe 的 Stob nan Cabar 山脚附近的岩墙要用**罗盘–步测（compass-and-pace）**方法填图（Slide 44、47 notes）。

### 4.2 练习答案透露的作图规范与评分要点

`Ex1soln(15).md` 的图注反复出现同样几条标注，说明这些**就是给分点**：

1. **每张莫尔图上必须标出符号约定**：图上写着 **"+ve: anticlockwise"**（逆时针为正）。
2. **必须画出"实物示意图"与莫尔图的对照**：答案图的右侧总是画一个小方块，标出 **σ₁、σ₃ 的方向、断层面、以及断层面的法线（normal to fault plane）**，并标出 **θ（与法线的夹角）与 α（与断层面的夹角）**两个角。**只画莫尔图不画方位示意图会丢分。**
3. **θ 与 α 必须同时标注且区分清楚**：答案图上永远是"63.6° θ"与"26.4° α"成对出现。
4. **"角度在莫尔图上加倍"要写出来**：(e) 的答案图上明确写着 **"angles are doubled on the Mohr diagram"**——18° 的产状差在莫尔图上是 **36°**。
5. **包络线的截距与斜率都要标数值**：τ₀ = 52 MPa、μ = tan 37.29 = 0.76、φ = 37.29° 三个量在每张图上都重复标出。
6. **切点坐标要写成 (σₙ, τ) 的形式**：如 (152.8, 168.1)、(275.6, 211.1)、(104.5, 131.4)。
7. **有孔压时 x 轴标签必须改**：(f) 的图上 x 轴写的是 **σₙ,eff (MPa)** 而不是 σₙ，且 x 轴上同时标出 **σ₃,eff = 39 与 σ₃ = 69**，以及 **p_fluid = 30 MPa 的位移量**。**忘记改轴标签是典型失分点。**
8. **答案鼓励"两条路都走"**：(d) 明说 "Draw a circle with σ₃ = 69 MPa that just touches the failure envelope **OR** calculate first using σ₁ = a + bσ₃"；(g) 也是"图解读出 62.2 MPa"与"用公式解"并列。**说明本课接受图解法，但图解必须画得准。**
9. **答案里的"Note that …"就是考点提示**，共四处：
   - (d) 之后："if you repeated this analysis for a region of **extensional tectonics**, then because now **σ₁ is vertical, the rocks are very much weaker**（若 σ₁ = 69 而非 σ₃ = 69，所需莫尔圆直径小得多）。"
   - (e) 之后："the shear stress on the fracture plane (211.1 MPa) is **greater** than on the fault plane **but the fracture does not fail because the normal stress (275.6 MPa) is also greater**." ——这正是 Slide 14 那个"为什么不在 45°"问题的定量版。
   - (f) 之后："the rock is **weaker** (smaller σ₁ − σ₃) when there is a pore fluid present."
   - (g) 之后：λ 的定义、正常压力值 0.43、超压判据、λ → 1 的上限。
10. **单位换算被单独提出来讲**（(d) 的题干用了三行讲 1 Pa = 1 N m⁻²、1 N = 1 kg m s⁻²）——说明**往年有大量学生在这里出错**。

---

## 五、Practical 要点

### 5.1 题目背景

`Ex1soln(15).md` 标题为 **Brittle failure and the Mohr Circle**。给定一块**砂岩**在**轴向压缩（axial compression）**下、在若干不同**围压 σ₃** 下破坏时所能承受的**差应力 σ₁ − σ₃**：

| σ₃ (MPa) | σ₁ − σ₃ (MPa) | **σ₁ (MPa)（自行推得）** |
|---|---|---|
| 0 | 210 | **210** |
| 50 | 360 | **410** |
| 100 | 520 | **620** |
| 150 | 675 | **825** |
| 200 | 825 | **1025** |

（材料在 (a) 的图注里列出的 σ₁ 列正是 210 / 410 / 620 / 825 / 1025 ✅ 与我的推算完全一致。）

### 5.2 (a) 拟合 σ₁ = a + bσ₃

**做法**：以 σ₃ 为横轴、σ₁ 为纵轴作图，画最佳直线，读**截距 a** 与**斜率 b**（图上标注 "tan⁻¹ b"）。

**材料答案**：**a = 210 MPa，b = 4.075**。

**自行复算**：对五个点做最小二乘拟合得 **a = 209.0 MPa，b = 4.090**。

**结论：与材料吻合。**差异（0.5% 与 0.4%）完全来自手工在坐标纸上目视画线的读数精度，不是错误。材料取 a = 210 是因为 σ₃ = 0 那个点直接给出截距，很自然。**后续所有小问都用 a = 210、b = 4.075。**

### 5.3 (b) 转成 τ = τ₀ + μσₙ，求 τ₀、μ、破裂角

**做法**：把五组 (σ₁, σ₃) 各画成一个莫尔圆，画出**与全部五个圆相切**的公切线 = **破坏包络线**；读 τ 轴截距 = τ₀，读倾角 = φ。

**材料答案**：**φ = 37.29°，μ = tan φ = 0.7616，τ₀ = 52 MPa；α = 45° − φ/2 = 26.355°（图上写 26.4°），θ = 63.6°，2θ = 127.2°。**

**自行复算**（用 §3.2 的公式，由 a、b 反解）：

| 量 | 我的计算 | 材料 | 吻合 |
|---|---|---|---|
| sinφ = (b−1)/(b+1) | 0.60591 | — | — |
| φ | **37.294°** | 37.29° | ✅ |
| μ = tanφ | **0.76164** | 0.7616 | ✅ |
| τ₀ = a/(2√b) | **52.015 MPa** | 52 MPa | ✅ |
| α = 45° − φ/2 | **26.353°** | 26.355° / 26.4° | ✅ |
| θ = 90° − α | **63.647°** | 63.6° | ✅ |
| 2θ | **127.29°** | 127.2° | ✅（材料由 63.6° 取整后加倍） |

**全部吻合。**

### 5.4 (c) 证明两种写法等价（OPTIONAL，在家做）

见 §3.2 的完整推导。⚠️ **该小问的方程在 md 转换中全部丢失**，只剩连接词与最后的 a、b 表达式；§3.2 是按保留下来的中间步骤复原的。**复原结果与材料保留的第 60 行 a、b 表达式完全一致。**

### 5.5 (d) 3 km 深、挤压构造区的最优取向断层上的 σₙ 与 τ

**题干条件**：z = 3 km，ρ_rock = 2.3 g cm⁻³，g = 10 m s⁻²，**假定一个主应力铅直**，**挤压构造（contractional tectonics）**。

**关键判断**：**挤压构造 ⇒ σ_V = σ₃**（Anderson 分类，见 §3.10）。

**步骤与复算**：

1. σ_V = ρgz = 2300 × 10 × 3000 = 6.9 × 10⁷ Pa = **69 MPa** ✅ 材料同
2. 挤压 ⇒ **σ₃ = 69 MPa**
3. σ₁ = a + bσ₃ = 210 + 4.075 × 69 = 210 + 281.175 = **491.175 ≈ 491 MPa** ✅ 材料同
4. 差应力 σ₁ − σ₃ = **422.2 MPa**（材料图上用 422）
5. τ = [(σ₁−σ₃)/2] sin 2θ = (422.175/2) × sin 127.29° = 211.09 × 0.79554 = **167.93 MPa**（材料 168.1）
6. σₙ = (τ − τ₀)/μ = (167.93 − 52.01)/0.76164 = **152.19 MPa**（材料 152.8）
   —— 用几何式核对：σₙ = (491.175+69)/2 + 211.09 × cos127.29° = 280.09 − 127.90 = **152.19 MPa**，两法一致 ✅

**结论：吻合。**材料的 168.1 / 152.8 与我的 167.93 / 152.19 差 0.1% 与 0.4%，来自材料把 μ 截断成 0.76、2θ 截断成 127.2°。**方法与量级完全一致。**

**材料的重要按语**：若在**伸展构造区**重做，因为此时 **σ₁ 铅直 = 69 MPa**，则由 σ₁ = a + bσ₃ 反推 σ₃ = (69−210)/4.075 = **−34.6 MPa**（张性！）——即**莫尔圆直径小得多，岩石弱得多**。这是"同一深度、不同构造域，岩石强度差一个量级"的直接证明。

### 5.6 (e) 断层倾角；以及倾角再陡 18° 的面上的应力

**断层倾角**：σ₁ **水平**（挤压区），σ₁ 与断层面法线成 63.6°，故 σ₁ 与断层面成 **90° − 63.6° = 26.4°**。σ₁ 水平 ⇒ **断层倾角 = 26.4°** ✅（与 Anderson 逆冲断层"~30°"一致）。

**倾角再陡 18°**的破裂面（同倾向）：倾角 = 26.4 + 18 = **44.4°** ⇒ 与 σ₁（水平）成 44.4° ⇒ **θ = 45.6°，2θ = 91.2°** ✅ 材料同。

**复算**：

- τ = 211.09 × sin 91.29° = 211.09 × 0.99975 = **211.03 MPa**（材料 211.1）✅
- σₙ = 280.09 + 211.09 × cos 91.29° = 280.09 − 4.77 = **275.32 MPa**（材料 275.6）✅

**结论：吻合。**

**这一问的全部意义在材料的按语里**：

> "the shear stress on the fracture plane (211.1 MPa) is **greater** than on the fault plane but **the fracture does not fail because the normal stress (275.6 MPa) is also greater**."

——44.4° 的面更接近 45°（最大剪应力方位），剪应力确实更大（211 > 168），**但它不破裂**，因为正应力也大得多（275.6 > 152.8），点落在包络线**下方**。**这是 §6.1 那个易错点的定量证据。**

### 5.7 (f) 有连通地表的孔隙流体时重做 (d)

**步骤与复算**：

1. p_fluid = ρ_water g z = 1000 × 10 × 3000 = **30 MPa** ✅
2. σ₃,eff = 69 − 30 = **39 MPa** ✅（材料图上的 39）
3. σ₁,eff = a + bσ₃,eff = 210 + 4.075 × 39 = **368.9 ≈ 369 MPa** ✅（图上 369）
4. σ₁（总应力）= 369 + 30 = **399 MPa** ✅（图上 399）
5. 差应力 = 369 − 39 = **330 MPa** ✅
6. τ = (330/2) sin 127.29° = 165 × 0.79554 = **131.26 MPa**（材料 131.4）✅
7. σₙ,eff = (131.26 − 52.01)/0.76164 = **104.05 MPa**（材料 104.5）✅

**结论：吻合。**

**要点**：破坏时的差应力从 **422 MPa 降到 330 MPa**——**孔隙流体使岩石变弱**。材料按语："the rock is weaker (smaller σ₁ − σ₃) when there is a pore fluid present."

λ = 30/69 = **0.435 ≈ 0.43** ✅（正常压力孔隙流体的基准值）。

### 5.8 (g) 若 3 km 深处 σ₁ = 300 MPa，需要多大孔压才破裂？

**图解法**：把 σ₃ = 69、σ₁ = 300 的圆向左平移，直到与包络线相切，**平移量就是 p_fluid**。

**代数法**（在有效应力下用同一个破坏准则）：

σ₁,eff = a + b σ₃,eff ⇒ σ₁ − p_f = a + b(σ₃ − p_f)

$$\boxed{\ p_f = \frac{a + b\sigma_3 - \sigma_1}{b - 1}\ }$$

**复算**：p_f = (210 + 4.075×69 − 300)/(4.075 − 1) = (491.175 − 300)/3.075 = 191.175/3.075 = **62.17 MPa** ✅ 材料 62.2 MPa

核对图上数值：σ₃,eff = 69 − 62.2 = **6.8** ✅（图上 6.8）；σ₁,eff = 300 − 62.2 = **237.8** ✅（图上 "237.8"）。

**λ = 62.2/69 = 0.901** ✅ 材料 0.90 —— **高度超压**。

**结论：全部吻合。**

### 5.9 可照做的解题流程（给定 σ₁、σ₃、τ₀、μ → 判断是否破裂 + 破裂面方位）

**Step 0｜统一符号与单位**：全部化成 MPa；确认 μ 与 φ 哪个已知（μ = tanφ）。

**Step 1｜画包络线**：τ 轴截距 τ₀，斜率 μ。

**Step 2｜画莫尔圆**：圆心 (σ₁+σ₃)/2，半径 (σ₁−σ₃)/2。**若有孔压，先把 σ₁、σ₃ 各减去 p_f，x 轴改标 σₙ,eff。**

**Step 3｜判断**：
- 圆在包络线**下方** → **不破裂**（稳定）。若题目问"还差多少"，可算：需要的差应力增量，或需要的孔压 p_f = (a + bσ₃ − σ₁)/(b − 1)。
- 圆与包络线**相切** → **恰好破裂**，进入 Step 4。

**Step 4｜求破裂角**：
$$\phi = \arctan\mu\ \Rightarrow\ \alpha = 45° - \frac{\phi}{2},\quad \theta = 45° + \frac{\phi}{2},\quad 2\theta = 90° + \phi$$

**Step 5｜求切点应力**：
$$\tau = \frac{\sigma_1-\sigma_3}{2}\sin 2\theta,\qquad \sigma_n = \frac{\sigma_1+\sigma_3}{2} + \frac{\sigma_1-\sigma_3}{2}\cos 2\theta$$
（或更快：先算 τ，再由 σₙ = (τ − τ₀)/μ 反解，两者应一致——**互相校验**。）

**Step 6｜换算成地质产状**（用 Anderson 分类）：
- **σ₁ 铅直（伸展）** → 正断层，**倾角 = 90° − α**（φ=30° 时 60°）；
- **σ₃ 铅直（挤压）** → 逆冲断层，**倾角 = α**（φ=30° 时 30°）；
- **σ₂ 铅直（走滑）** → 断层直立，走向与 σ_H 成 **±α**。
- 共轭对总是**成对**出现，**锐角（= 2α）由 σ₁ 平分**。

**Step 7｜若题目给深度**：σ_V = ρ_rock g z；正常压力孔压 p_f = ρ_water g z；λ = p_f/σ_V（正常 ≈ 0.43）。**先用构造类型判断 σ_V 是 σ₁、σ₂ 还是 σ₃**，再代入 σ₁ = a + bσ₃。**走滑情形下 σ_V = σ₂，无法定圆，必须另给 σ₁ 或 σ₃**（Anderson.md 原话）。

---

## 六、易错点 / 重点难点

### 6.1 ⚠️ 把最大剪应力面当成破裂面（本周头号错误）

- **最大剪应力面**：α = **45°**（2θ = 90°），τ 取最大值 (σ₁−σ₃)/2。
- **实际破裂面**：α = **45° − φ/2**（2θ = 90° + φ），τ 略小、但 **σₙ 小得多**。

**为什么**（Slide 14 notes）：破裂涉及**体积增大**，正应力把两壁压在一起、压制破裂。所以是"剪应力大 + 正应力小"的**折中最优**方位。

**定量证据**：Ex1 (e) —— 44.4° 面上 τ = 211 MPa > 26.4° 面上的 168 MPa，**但 44.4° 面不破裂**，因为其 σₙ = 275.6 MPa ≫ 152.8 MPa。

### 6.2 ⚠️ 共轭锐角平分线方向记反

**正确：σ₁ 平分锐角，σ₃ 平分钝角，σ₂ 沿两破裂面的交线。**

记忆锚点：**破裂面与 σ₁ 的夹角 α < 45°**（因为 α = 45° − φ/2）。既然每一支都"贴着 σ₁"，两支之间夹住 σ₁ 的角自然是**锐角**（2α = 90° − φ ≈ 60°）。**从 α < 45° 就能反推出"锐角平分 σ₁"，不必死记。**

Slide 12 的野外判据：共轭张性节理阵列 + 与之正交的缝合线 → 缝合线的"闭合"方向指示 σ₁ → 与锐角平分线一致。

### 6.3 ⚠️ θ 与 α 混用（本课特有的坑）

**本课约定 θ = σ₁ 与破裂面法线的夹角**，不是与破裂面的夹角！

| | 与 σ₁ 的夹角 | φ = 30° | φ = 37.29° |
|---|---|---|---|
| **破裂面 α** | 45° − φ/2 | 30° | 26.4° |
| **法线 θ** | 45° + φ/2 | 60° | 63.6° |

**莫尔图上永远用 2θ（法线角的两倍）**。破裂面与 σ₁ 成 30° ⇒ **2θ = 120°，不是 60°**。Class 5 Slide 9 用 θ、Slide 10 用 α，**同一门课两套符号并存**，做题前必须先确认题目用的是哪个（Class 7 notes 明说 α = 90° − θ）。

另有第三个 θ：Slide 13 共轭脉阵列分类里的 **θ 是阵列几何角**，与莫尔图的 θ 毫无关系。

### 6.4 ⚠️ 有效应力使圆左移还是右移

**孔压升高 → 圆向左移（σₙ 减小）→ 更容易碰到包络线 → 促进破裂。**

物理直觉：**孔隙里的流体从内部把裂缝顶开**，抵消了把两壁压紧的正应力。σₙ,eff = σₙ − p_f，**减号**，所以左移。

**直径不变**（σ₁ 与 σ₃ 减去同一个数），**剪应力不变**。三点全对才算记住。

### 6.5 ⚠️ Anderson 分类：哪个主应力铅直对应哪种断层

**永远从"σ₁ 是挤的方向、σ₃ 是拉的方向"倒推，不要死背：**

| 铅直的是 | 物理含义 | 断层 | 倾角 |
|---|---|---|---|
| **σ₁** | 上下压得最紧 → 岩石只能**向两侧拉开** | **正断层** | **60°** |
| **σ₂** | 最大与最小都水平 → 只能**水平错动** | **走滑** | **90°** |
| **σ₃** | 上下最松、水平压得最紧 → 岩石只能**向上挤出** | **逆冲** | **30°** |

**倾角配对口诀**：**"正陡逆缓"——正断层 60°（陡），逆冲 30°（缓）**。两者互余，都是由 α = 30° 得来，只是 σ₁ 的方位差了 90°。

**最常见的错法**：以为"挤压 → σ₁ 铅直"。恰恰相反，**挤压区 σ₁ 水平、σ₃ 铅直**（Ex1 (d) 正是靠这一步）。

### 6.6 ⚠️ 内摩擦角 φ 与内摩擦系数 μ 混用

**μ = tan φ，不是 φ 本身，也不是 φ 的弧度值。**

- φ = 30° → μ = 0.577 ≈ 0.58
- φ = 37.29° → μ = 0.7616
- **μ 无量纲，φ 有单位（度）。**

破裂角公式 **α = 45° − φ/2 用的是角度 φ，不是 μ**。若题目只给 μ，必须先 **φ = arctan μ** 再代入。

### 6.7 ⚠️ 破裂角公式的正负号

**α = 45° − φ/2**，是**减号**。检验：φ = 0（无摩擦）→ α = 45°，退化为最大剪应力面 ✅；φ 增大 → α 减小，破裂面越来越贴近 σ₁ ✅（对应"围压低时趋于张裂隙，α → 0°"）。

对应地 **θ = 45° + φ/2（加号）**，**2θ = 90° + φ（加号）**。**三者的符号规律是：面角减、法线角加。**

### 6.8 ⚠️ 张裂隙与剪裂隙的扩展方式反了

- **张裂隙：在自身平面内扩展**（Slide 21）。
- **剪裂隙：不能在自身平面内扩展**，必须靠**裂尖新生张裂纹（wing cracks）**或**连接已有张裂纹**（Slide 22）。

这直接决定了两者的终止构造不同：剪裂隙末端才有 **splay / horsetail / antithetic** 三件套。

### 6.9 ⚠️ dyke / sill 的定义不是"整合与否"

**dyke = 近直立席状体，sill = 近水平席状体**，按**产状**定义。Slide 36 特意举了层理直立的例子：那里"sill"是**不整合**的、"dyke"是**整合**的。别把 concordant/discordant 当成定义。

### 6.10 ⚠️ 岩床条件是 σ_v − σ_h ≈ 0，不是 σ_v < σ_h

材料的推导是：**σ_v − σ_h = T_h − T_v**，而抗张强度都很小，所以**条件是差值 ≈ 0**。物理过程是：岩浆在 **σ_v > σ_h** 时以岩墙上升，**σ_v 向地表递减**，到 σ_v − σ_h ≈ 0 处岩床成为可能；若 **T_h − T_v > 0** 则更倾向岩床。

### 6.11 ⚠️ 单体运动学 ≠ 阵列运动学

Slide 12 的经典陷阱：West Angle Bay 的张性节理**单条是张裂隙**（垂直于缝合线），但**雁列排布的整个阵列指示左行剪切**。答题时必须分两个尺度说。

### 6.12 ⚠️ "看不到位移"不等于"是纯张裂隙"

Slide 9：薄片下的 ~10 µm 剪切位移在野外不可见；纤维斜交同样说明 hybrid。**严格来说 fissure/vein/dyke/joint 常常都是 hybrid。**

### 6.13 ⚠️ 走滑构造域无法只靠深度定莫尔圆

Anderson.md 原文："**need some way of specifying σ₁ or σ₃**"。因为 σ_V = σ₂ 落在莫尔圆内部而非端点。**伸展与挤压两态才能靠 σ_V = ρgz 直接钉住圆的一端。**

### 6.14 ⚠️ 挤压 vs 伸展下同一深度的岩石强度差异巨大

Ex1 (d) 的按语：3 km 深、σ_V = 69 MPa 时——
- **挤压区**（σ₃ = 69）：破坏需 σ₁ − σ₃ = **422 MPa**；
- **伸展区**（σ₁ = 69）：所需圆**小得多**，岩石**弱得多**。

这也是为什么正断层比逆冲断层容易活动。

### 6.15 ⚠️ 有孔压时坐标轴标签必须改

x 轴写 **σₙ,eff**，且答案图上要同时标出 σ₃、σ₃,eff 与 p_fluid 的平移量。写成 σₙ 会被扣分（Ex1 (f) 的答案图特意标注了 "when pore fluids are present"）。

---

## 七、本周术语表

| 中文 | English | 说明 |
|---|---|---|
| 破裂 | fracture | 位移与力学性质不连续的面 |
| 张裂隙 / 张性破裂 | extension fracture (Mode I) | 位移垂直于破裂壁、张开意义 |
| 剪裂隙 / 剪切破裂 | shear fracture (Mode II / Mode III) | 位移平行于破裂壁，两正交滑移方向 |
| 收缩破裂 | contraction fracture (Mode IV) | 闭合意义；即反裂隙 |
| 反裂隙 | anticrack | 缝合线的经典力学模型 |
| 混合型破裂 | hybrid fracture / mixed mode | 张+剪 或 压+剪 |
| 裂缝 / 张开裂隙 | fissure | 张裂隙内填空气或流体 |
| 脉 | vein | 张裂隙内填矿物 |
| 岩墙 / 岩脉 | dyke | 张裂隙内填岩浆，近直立 |
| 岩床 | sill | 近水平的岩浆席状体 |
| 节理 | joint | 张开量极小、无宏观面平行位移 |
| 主节理 | master joint | 长 10 cm–100 m 级，间距 cm–10 m 级 |
| 破裂组 | fracture set | 产状相似的一组破裂 |
| 破裂网络 | fracture network | 破裂的集合体，有拓扑结构 |
| 缝合线 | stylolite | 牙齿垂直于面的压溶界面 |
| 斜缝合线 | slickolite | 牙齿斜交于面，hybrid 性质 |
| 张性节理 / 张裂缝 | tension gash | 雁列阵列指示剪切 |
| 雁列（式） | en échelon | 阶梯状斜列排布 |
| 羽状破裂 / 羽毛破裂 | pinnate fracture / feather fracture | 方位指示运动方向 |
| 共轭（对） | conjugate (pair) | 夹角 40°–60°，σ₁ 平分锐角 |
| 收敛型阵列 | convergent array | (θ/2)+(90°−δ)+(ψ/2)=90° |
| 发散型阵列 | divergent array | 天然界尚未见报道 |
| 羽状构造 / 羽饰 | plumose structure | 指示破裂扩展方向 |
| 羽痕 | hackle | 发散的脊与槽 |
| 羽状边缘 | hackle fringe | 边缘扭转的雁列小面 |
| 肋痕 / 停顿线 | rib mark / arrest line | 破裂暂停的记录 |
| 波痕（破裂面上的） | ripple mark / Wallner line | 极快速扩展的产物；非沉积波痕 |
| 翼裂纹 | wing crack | 剪裂隙裂尖新生的张裂纹 |
| 分叉 | splay | 同向（synthetic）剪破裂群 |
| 马尾构造 | horsetailing | 破裂一侧的张裂隙群 |
| 反向剪破裂 | antithetic shear fracture | 与主破裂反剪切向 |
| 纵向（bc）节理 | longitudinal (bc) joint | 平行褶皱枢纽、正交层理 |
| 横（ac）节理 | cross (ac) joint | 平行剖面（profile plane） |
| 剥离节理 / 席状节理 | exfoliation joint / sheet joint | 近平行地形面，深成岩中典型 |
| 柱状节理 | columnar jointing | 垂直于等温面的张裂隙 |
| 多边形破裂网络 | polygonal fracture network | 冷却或干缩收缩产物 |
| 泥裂 / 干缩裂缝 | mudcrack / desiccation crack | 顶角由 90° 演化向 120° |
| 脱水收缩裂缝 | syneresis crack | 水下形成的收缩裂缝 |
| 应力 | stress | — |
| 主应力 | principal stress (σ₁ ≥ σ₂ ≥ σ₃) | 本课**压为正** |
| 最大主压应力 | maximum compressive stress, σ₁ | — |
| 最小主压应力 | minimum compressive stress, σ₃ | — |
| 差应力 | differential stress (σ₁ − σ₃) | = 莫尔圆直径 |
| 正应力 | normal stress, σₙ | 抑制破裂 |
| 剪应力 | shear stress, τ | 驱动破裂 |
| 围压 | confining pressure | 实验中 = σ₂ = σ₃ |
| 有效（正）应力 | effective (normal) stress, σₙ,eff | = σₙ − p_fluid |
| 孔隙流体压力 | pore fluid pressure, p_fluid | 只影响正应力 |
| 孔压参数 | pore pressure parameter, λ | = p_fluid/σ_V；正常 ≈ 0.43 |
| 超压 | over-pressured | λ > 0.43 |
| 静岩（压力） | lithostatic | σ₁ = σ₂ = σ₃ = ρgh |
| 莫尔图 / 莫尔圆 | Mohr diagram / Mohr circle | 圆心 (σ₁+σ₃)/2，半径 (σ₁−σ₃)/2 |
| 破坏包络线 | failure envelope | 与圆相切即破裂 |
| Coulomb 破坏准则 | Coulomb failure criterion | τ = τ₀ + σₙ tanφ |
| Mohr–Coulomb 准则 | Mohr–Coulomb failure criterion | 包络线非线性时的一般形式 τ = f(σₙ) |
| Griffith 准则 | Griffith criterion | 张性场准则；本周讲义未涉及 |
| Byerlee 定律 | Byerlee's law | 摩擦滑动经验律；见 Class 7 |
| 内聚力 / 内聚强度 | cohesive strength, τ₀ | 包络线的 τ 轴截距 |
| 内摩擦系数 | coefficient of internal friction, μ | 包络线斜率，μ = tanφ |
| 内摩擦角 | angle of internal friction, φ | 多数岩石 φ ≈ 30° |
| 抗张强度 | tensile strength, T | 岩石中很小 |
| 水力压裂 | hydraulic fracturing | 流体压力生成张裂隙 |
| 构造角砾岩化 | tectonic brecciation | 极高流体压力下发生 |
| 浮力 | buoyancy | = 岩浆压力 − 围岩铅直应力 |
| 岩浆超压 | magma overpressure, p_over | = p_magma − σ_h |
| 供给岩墙 | feeder dyke | 给岩床供岩浆 |
| 分层剥离 | delamination / Cook–Gordon debonding | 泊松效应致侧向扩展 |
| 材料性质失配 | material property mismatch | 遇更硬层时沿界面偏转 |
| 冷凝边 | chilled margin | 岩墙外接触带 |
| 脆性变形 / 碎裂流变 | cataclastic deformation | 浅部脆性域 |
| 扩容 | dilatancy | 破裂伴随的体积增大 |
| 泊松比 | Poisson's ratio, ν | 典型 0.25 |
| 泊松效应 | Poisson effect | 一方向拉伸 → 垂向收缩 |
| 杨氏模量 | Young's modulus, E | — |
| 单轴应变参考态 | uniaxial strain reference state | 水平应力 ≈ 0.33–0.5 × 铅直应力 |
| Anderson 断层分类 | Andersonian classification of faults | 按哪个主应力铅直分三类 |
| 正断层 | normal fault | σ₁ 铅直，倾角 ~60° |
| 逆冲断层 | thrust | σ₃ 铅直，倾角 ~30° |
| 走滑断层 | strike-slip fault | σ₂ 铅直，直立 |
| 玫瑰图 | rose diagram | 近直立破裂的方位统计 |
| 分裂玫瑰图 | split rose diagram | 按岩性分开画 |
| 赤平投影图 | stereogram / stereonet | 非直立破裂的方位表示 |
| 圆形计数线 | circular count line / scanline | 避免 cut effects |
| 破裂迹强度 | fracture trace intensity | n/(4r) |
| 破裂迹密度 | fracture trace density | m/(2πr²) |
| 平均迹长 | mean trace length | (n/m)πr/2 |
| 破裂网络拓扑 | fracture network topology | I / Y / X 节点 |
| 连通性 | connectivity | 决定流体渗流 |
| 渗透（作用） | osmosis | 抬高孔压的机制之一 |
| 前陆 | foreland | Hafner 模型的应用对象 |
| 弯滑褶皱 | flexural slip fold | slickolite 常见于其周围 |
| 罗盘–步测（填图） | compass-and-pace (mapping) | 复活节野外课技能 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Practical/Week 6/Anderson.md`，第 10 行图注 | `a = 45° - 2f` | **角度关系写反/写错**：若按字面 α = 45° − 2φ，代入 φ = 30° 得 α = −15°，为负角，物理上不可能；且与同一行给出的 α = 30° 自相矛盾。 | 应为 **α = 45° − φ/2**。代入 φ = 30° 得 α = 45° − 15° = **30°** ✅，与图上另行标注的 α = 30°、正断层 60°、逆冲 30° 全部自洽。这是 PDF 图注文字提取时把上下标 "φ/2" 误读为 "2φ"（分数横线丢失）。**Class 7 讲义 notes 明确写着 "α = 45° − (ϕ/2)"，可作交叉印证。** |
| `Lecture/Week 6/Class6_Fractures.md`，Slide 32（剥离节理），第 551 行 | `σv = - ρ g h   ; σh = [ν / (1- ν ) ] ρ g h` | **公式符号丢失**：按字面读，σ_v = −ρgh 与上一行的 σ₁=σ₂=σ₃=ρgh 直接矛盾（同一个量既是 +ρgh 又是 −ρgh）。 | 这两式描述的是剥露引起的**变化量**，应为 **Δσ_v = −ρg·Δh；Δσ_h = [ν/(1−ν)]·ρg·Δh**。Δ 符号在 pptx→md 转换中丢失。同一 Slide 的 notes（第 565 行）也丢了 Δ："σh = σh,initial - σh = ρgh - [ν/(1-ν)]ρgh … for h = h"，完整应为 **σ_h = σ_h,initial − Δσ_h = ρgh − [ν/(1−ν)]ρgh = [(1−2ν)/(1−ν)]ρgh，其中 Δh = h**。按复原式验算 h=5 km、ν=0.25、ρ=3 g cm⁻³ 得 100 MPa，与讲义给出的 100 MPa 吻合 ✅。 |
| `Practical/Week 6/Ex1soln(15).md`，(c) 小问全段（第 29–71 行） | 只剩 "Hence from elementary trigonometry"、"so that rearranging"、"Dividing both sides by (1 - sin f)"、"so that"、"Check using answers in (a) and (b):" 等连接词，**方程全部缺失** | **内容丢失（非作者错误）**：PDF 中的公式为图片或特殊排版，转 md 时未被提取，导致该小问无法阅读。题干中 "show that σ₁ = a + bσ₃ is equivalent to τ = τ₀ + σₙ tanφ **where**" 后面的 where 子句也是空的。 | 已在本笔记 §3.2 按保留下来的第 54、60、64 行中间步骤完整复原，结论为 **sinφ = (b−1)/(b+1)**、**√b = (1+sinφ)/cosφ = tan(45°+φ/2)**、**τ₀ = a/(2√b)**。用 a=210、b=4.075 验算得 φ=37.294°、μ=0.7616、τ₀=52.01 MPa，与材料 (b) 的答案完全一致 ✅。 |
| `Practical/Week 6/Ex1soln(15).md`，(g) 图注（第 116 行） | `s3, eff 6.8 50 69 150 s237.81, eff 250 300 3501 450 550` | **数字与符号粘连**：`s237.81, eff` 与 `3501` 是 PDF 文字流错位造成的粘连，不是数值错误。 | 应读作 **σ₃,eff = 6.8**；**σ₁,eff = 237.8**（"s" + "237.8" + "1, eff" 粘连）；坐标刻度为 …250, 300, 350, 450, 550…（"3501" = 刻度 "350" 与轴上的 "1" 粘连）。复算：σ₃,eff = 69 − 62.2 = 6.8 ✅，σ₁,eff = 300 − 62.2 = 237.8 ✅。 |
| `Practical/Week 6/Ex1soln(15).md`，(a) 图注（第 22 行） | 拟合结果 `b = 4.075`、`a = 210 MPa` | **非错误，仅记录复算差异**（列出以备考试时数值不一致时判断）。 | 对五个数据点做最小二乘拟合得 **a = 209.0 MPa，b = 4.090**；材料的 210 / 4.075 来自坐标纸上目视画线，差异 < 0.5%。**两者均可接受**，本课后续小问统一使用材料的 210 / 4.075。同理，材料 (d)(e)(f) 中的 168.1 / 152.8 / 211.1 / 275.6 / 131.4 / 104.5 与我用未截断的 μ = 0.76164、2θ = 127.29° 复算的 167.9 / 152.2 / 211.0 / 275.3 / 131.2 / 104.0 相差 0.1–0.5%，全部源自材料把 μ 截断为 0.76、θ 截断为 63.6°，**不是错误**。 |

> 除上述四条转换/排版类问题与一条数值复算差异外，**本周材料的地质学与力学内容未发现实质性错误**。特别核对过：破裂角公式 α = 45° − φ/2 的正负号（讲义 Slide 14 的"20°–30° to σ₁"、Ex1soln 的 26.4°、Anderson.md 的 30° 三处互相自洽）；μ = tanφ 的换算（0.58↔30°、0.7616↔37.29° 均正确）；Anderson 分类的对应关系（σ₁ 铅直→正断层 60°、σ₂ 铅直→走滑直立、σ₃ 铅直→逆冲 30°，三格全部正确）；以及 σ_v − σ_h = T_h − T_v 的推导方向（正确）。
