# EART27201 Sedimentary Rocks and Fossils — Week 04 学习笔记

## 一、本周主题

**本周主题（由材料判定）：单向水流下的床面形态序列（第二部分）—— 从沙丘（dunes）到逆行沙丘（antidunes）。**

判定依据三条，互相印证：

1. 讲义首页标题即 **"Class 4: Bed Configurations (Part 2)"**（作者 John Southard, Emeritus MIT），提纲写明两个目标：*describe the bedforms that develop in fine-coarse sands under unidirectional flows (dunes to antidunes)* 与 *why ripples and dunes migrate downstream*。
2. 第 3 周讲义（Class 3: Bed Configurations Part 1）末页明确预告 **"We will conclude our experiment next week"**，并把"下周"内容逐字列为上面同样两条。第 3、4 周是**同一讲的上下两半**。
3. 讲义正文全部围绕沙丘几何与迁移、沙丘尺度与流深、平面形态随流强演化、冲刷平化、上部平床、同相波与逆行沙丘展开，**没有任何化石内容**。

> ⚠️ 课程大纲写的 W4 是 "Macrofossils I. Trilobites and Brachiopods"，与实际发放材料完全不符。整门课实际周次与大纲存在系统性错位（古生物实际排在 W7–W11）。已记入文末勘误表，**正文一律以实际讲义为准**。

**在全课骨架中的位置。**上半程（W1–W6，沉积学）的推进逻辑是：*沉积物与流体的基本物性*（W1 颗粒/基质/胶结物/孔隙度；W2 成分、圆度、球度、粒度与沉降）→ *流体如何塑造床面*（W3–W4，本周所在）→ *床形在岩石记录中留下的沉积构造与古水流信息*（W5 Sedimentary Structures）。

因此本周是**"过程"通向"产物"的枢纽**。第 3 周讲义已给出贯穿全课的**三步倒推法**：(1) 仔细观察并描述沉积构造 → (2) 推断产生它的床形类型、迁移样式、沉积速率 → (3) 解释造成上述结果的流动条件。本周提供的正是第 (2)(3) 步所需的全部床形知识。

**与前三周衔接。**W1 给出描述沉积物的语言；W2 的粒度与 Stokes 沉降是本周所有粒径判据（"<0.2 mm 不形成沙丘"、"波痕只在中砂或更细"、"下部平床只在粗砂或更粗"）背后的物理量；W3 的 Exner 方程、床面剪应力 τ₀、临界剪应力 τ_cr、以及接触载荷/跃移/间歇悬移三种搬运方式，是本周解释沙丘迁移与 washout 的**唯一工具**，本周讲义直接使用不再推导。

**关于本周实习沿用第 3 周 handout。**第 4 周实习讲义文件名为 `Class 3 practical handout 2025.md`，与 `Practical/Week 3/` 下同名文件内容完全一致。**这是课程的有意安排：整个水槽（flume）实验是一次连续的、跨两周的实验，一份 handout 用两周**，第 3 周讲义结尾那句 "We will conclude our experiment next week" 即官方说明。该 handout 内部本身分为 A1–A6 六段，第 3 周做前半（建立流动、判流态、求起动临界剪应力、造出波痕），**第 4 周从 A3「Transition to dunes」起做完**（详见第五段）。

---

## 二、核心概念

### 2.1 术语三分（引自第 3 周讲义，本周默认使用）

- **Bed configuration（床面组构）**：某时刻床面在流动作用下的**整体**几何形态。
- **Bedform（床形）**：构成床面组构的**单个**地形单元（一个沙丘、一个波痕）。
- **Sedimentary structure（沉积构造）**：床形迁移时**留在沉积物内部**的记录（如沙丘迁移形成的交错层理）。

📎 **背景补充：**床形是"现在长什么样"（地貌），沉积构造是"当时留下了什么"（层内纹层）。野外看到的是后者，考试要求由后者反推前者。

### 2.2 沙丘：定义与限定条件

讲义要点（原文）：**大型、不对称床形**；**不是"大号波痕"** —— *ripples don't grow into dunes，transition is abrupt*（波痕不会长大成沙丘，转变是突变的）；**绝不是第一个出现的床形**（never first / lowest velocity bedform to appear）；**在 < ~0.2 mm 的沉积物中不形成**，且**需要水力粗糙边界**；是**沙床河流中最常见的床形**，砾质河床中亦有。讲义示例为美国内布拉斯加 North Loup River 河床沙丘（照片圈出两人作比例尺，Mohrig, 2006）。

📎 **背景补充（为何需要水力粗糙）：**当粒径 D 小于粘性次层厚度时，颗粒被"淹没"在层流薄层内，床面对外部湍流是**水力光滑**的——这正是波痕的条件（第 3 周讲义：*turbulent boundary must be hydraulically smooth for ripples to form*）。D 大于粘性次层厚度时颗粒刺穿薄层直接暴露于湍流，床面变为**水力粗糙**，流动分离才能在颗粒尺度以上组织起来。**波痕与沙丘由两套不同的边界层机制控制，这就是"突变而非渐变"的物理根源。**

### 2.3 迁移机制（本周核心推理链）

**几何：迎流面 stoss（上游）平缓，背流面 lee / slip face（下游）陡。**讲义用"漫游式观察"建立直觉：从波峰出发滑下滑落面、走过槽底、再爬上下游床形的迎流面——沿途感受到的水流**差异极大**；这在真实河流沙丘、潮流沙丘乃至陆上风成沙丘上都可实地执行。

**迁移的因果链（讲义原文逐条）：**
1. **水面与床面反相**；
2. 因而**水深变化也与床面反相**（峰上水浅、槽上水深）；
3. **流速从槽底向波峰加速**；
4. **输沙率从槽底向波峰增大**；
5. **床形向下游迁移**；
6. **床形变得不对称**。

配图标注为 *erodes（迎流面侵蚀）— deposits（背流面沉积）… flow accelerates over crest: dune migrates downstream*。

📎 **背景补充（用 Exner 方程串起来）：**第 3 周的沉积物质量平衡说的是，床面高程变化由**输沙率的空间梯度**决定，而非流速绝对值。标准形式为 **∂η/∂t = −(1/(1−λp))·∂q_s/∂x**（η 床面高程，q_s 单宽输沙通量，x 流向，λp 孔隙度；原讲义 PDF 转 md 后该式符号已丢失，此为补写）。迎流面 ∂q_s/∂x > 0 → **侵蚀**；越过波峰后流动分离、流速骤降，∂q_s/∂x < 0 → **沉积**。**上游侵蚀 + 下游沉积 = 床形向下游平移并变得不对称。**这也正是第 3 周那句反直觉结论——**并非快流必侵蚀、慢流必沉积**（Hjulström 图常见误用）。

**背流面的流动结构（实习要求现场观察）：**
- **separation bubble（分离泡）**：波峰下游的回流区，**内部水流朝上游**，会把颗粒倒扫回滑落面底部；
- **avalanching（崩落）**：颗粒堆积至休止角后成片下滑；
- **boils（涌沸）**：再附着后发展的强湍流团上升至水面形成的沸腾状涡旋。

讲义另有一页标题 **"Bursting cycle resulting from dune topography"**（仅标题与图，无正文）。📎 **背景补充：**bursting cycle 指近底湍流的"抬升—下扫"周期（ejection/sweep）。沙丘地形通过分离与再附着**周期性地组织**这一过程，把随机湍流变成尺度与沙丘匹配的大涡，上升到水面即 boils。**床形塑造湍流，湍流反过来维持床形——这是沙丘自我维持的关键。**

**复合床形：**讲义指出平衡态沙丘的**迎流面上常叠置波痕**（compound bedforms, Mohrig 2006），说明两种床形可在同一流动下共存于不同尺度层级。

### 2.4 尺度关系：为何沙丘随水深标度、波痕不随

**沙丘高度约为流动垂向尺度（水深）的 0.2–0.3 倍**（Leeder, 1999）。讲义在此**提问而不作答**：*Why do dunes scale with the flow depth when ripples do not?*

📎 **背景补充（答案思路）：波痕是"边界层床形"，沙丘是"全水深床形"。**波痕尺度由粘性次层厚度（进而由粒径与粘性）控制，高度仅 0.005–0.05 m、波长 0.05–0.6 m，**感觉不到水面在哪里**（第 3 周原文：*do not interact with water surface and no dependence on flow depth*；波长只随粒径变化，**λ ≈ 1000d**）。沙丘可达米级至十米级，扰动**贯穿整个水深**并触及自由水面（故有 boils 与水面 drawdown），**能被容纳的最大扰动尺度受水深限制**，高度自然按水深标度。

讲义另有一页 **"Dunes: just how big can they get?"**，配图为**叠置的风成床形**（superimposed aeolian bedforms），仅标题无正文。

### 2.5 平面形态随流强演化：2-D → 3-D（讲义数据）

| | **较低流速：2-D 沙丘** | **流速增大：3-D 沙丘** |
|---|---|---|
| 形态 | 低矮、间距大、二维 | 高度增大而间距不增大 |
| 脊线 | 长而平直至微弯 | 复杂：弯曲状至新月形（sinuous to lunate） |
| 背流面坡角 | 接近休止角 **25°–30°** | **< 25°** |
| 尺寸 | 最小高度 **0.05 m** | 波长 **0.6 m – 数百米**，高度 **0.05 m – >10 m** |
| 形态比 form ratio | **50–200** | **15–20**（讲义自注 *shorter and higher*） |
| 搬运方式 | 滚动、滑动、崩落 | 加上跃移与**间歇悬移** |

讲义随后给出关键观察 "at higher velocities……"：**部分颗粒被带过波峰后直接落在下游沙丘的迎流面上**——这是 washout 的前兆。

📎 **背景补充：**讲义未给 form ratio 定义，通用定义为 **波长/高度**。验算：2-D 最小高度 0.05 m、比值 50–200 → 波长约 2.5–10 m；3-D 比值 15–20 在同波长下高度显著增大，与讲义自注"更短更高"一致，定义无误。

### 2.6 冲刷平化（Washout）机制

讲义的判据式表述：*Washout occurs when characteristic **excursion lengths** of a significant number of size classes become long relative to the **distance of the lee face**（i.e. suspension is dominant mode of sediment transport）*。

- **excursion length（跃程）**：颗粒离底后到重新落底之间沿流向前进的距离；流强越大、悬移越多则越长。
- **后果**：颗粒**越过背流面而不落在其上** → **不被并入床形**（not incorporated into bedform）→ **波峰被削平、高度下降**。
- 总述：随流速增大，沙丘**越来越长、越来越低**直至完全消失，让位于**平整床面**，其上大量悬移质与推移质以 **"牵引毯"（traction carpet）** 形式在近底被搬运。

📎 **背景补充：**washout **不是**"沙丘被水磨平"，而是**搬运机制改变导致床形无法维持**——沙丘依赖"颗粒在背流面沉降堆积"这一反馈，一旦颗粒普遍飞越背流面，反馈链断裂，床形自然消亡。这也解释了为何**上部平床在任何粒径下都能形成**：只要剪应力高到悬移主导即可。

### 2.7 同相波与逆行沙丘

讲义要点：**正弦形床形，伴随与之同相的水面波**（对照沙丘的**反相**）；**出现于超临界流 Fr > 1**，量化示例——**水深 0.1 m 需平均流速 > 1 m/s，水深 1 m 需 > 3 m/s**；**常成长列出现**；**单个波形经历"放大—破坏"循环**；**真正的逆行沙丘是向上游迁移的波形**（Bridge, 2003）。配图为明尼苏达 Hibbing Taconite 矿尾矿池辫状河道的水面波列（Mohrig, 2006）。

📎 **背景补充（上游迁移机制）：**同相条件下床面波峰正对水面波峰，该处水深最大、流速较低 → 沉积；水面凹陷处流速最高 → 侵蚀。结果是床形波峰不断向上游"生长"：颗粒**从一个逆行沙丘的下游面被侵蚀，沉积到下游那个逆行沙丘的上游面**。**水和颗粒始终向下游运动，只有床形向上游移动**——这就是 "anti-dune" 一词的由来。

### 2.8 "Important points to remember"（讲义原文清单，考点）

| 讲义原文 | 含义 |
|---|---|
| Lower plane bed only forms in coarse sand or coarser | 下部平床（有输运无地形）只在粗砂（>0.5 mm）及更粗中出现 |
| Ripples form only in medium sand or finer | 波痕只在中砂及更细中出现 |
| Ripple spacing increases with grain size | 波痕间距随**粒径**增大（λ ≈ 1000d） |
| No clear relationship between ripple size and either flow strength or water depth（but planform may vary） | 波痕**尺寸**与流强、水深无明确关系；**平面形态**会变 |
| Dune spacing: increases with depth, increases with velocity (washing out) | 沙丘间距随水深、随流速均增大 |
| Dune height: increases with depth; **increases and then decreases** with velocity (washing out) | 沙丘高度随流速**先增后减** |
| Upper plane bed will form in any grain size at very high shear stresses where transport in suspension dominates | 上部平床与粒径无关 |
| Antidunes require a **free surface** and supercritical flow | 逆行沙丘必须有自由水面（故不可能出现于满管流）且流动超临界 |

⚠️ 最易记混：**沙丘高度随流速先增后减，而间距一路增大**——两者行为不同，原因都在 washout。

---

## 三、公式与图表

本周讲义几乎没有公式（只有 Fr 的定性判据与沙丘高度比例）；定量内容主要来自实习 handout 与第 3 周讲义。

### 3.1 Du Boys 方程（实习 A2 使用）

```
τ₀ = ρ g h S
```
- **τ₀** 床面剪应力（Pa）；**ρ** 水密度（20 °C，约 998 kg/m³）；**g** = 9.81 m/s²；**h** 平均水深（m）；**S** 坡度，handout 注明单位 **m/m 或 sin α**。

使用条件（handout 原文）：颗粒要起动必须 **τ₀ = τ_cr**。故在水槽中逐步抬升坡度至**刚好看见颗粒运动**的瞬间，代入实测 h 与 S，算出的 τ₀ 即该粒径的 **τ_cr**。

📎 **背景补充：**该式来自**沿坡重力分量与床面阻力的平衡**：厚度 h 的水体沿坡向重力分量为 ρghsinα，均匀流下完全由床面剪应力平衡，小角度近似即 τ₀ = ρghS。⚠️ **S 必须是无量纲坡降，不能代百分数或角度**——本实验最常见的单位错误。

### 3.2 雷诺数（实习 A1 使用，第 3 周讲义给出）

```
Re = U h ρ / μ
```
U 平均流速、h 平均水深、ρ 水密度、μ 分子（动力）粘度；**所有量必须 SI 单位**。明渠流判据：**Re < 500 层流，Re > 2000 湍流**，之间为过渡流。讲义与 handout 用同一句斜体收尾：**所有水槽及自然河流中的流动都是完全湍流的，即使水面光滑如镜。**

### 3.3 Froude 数（判定逆行沙丘的必要条件）

讲义只给 "supercritical flows (Fr > 1)" 与两组数值，**未给定义式**。

📎 **背景补充：Fr = U / √(g h)**，即惯性力与浅水重力波速之比。**Fr < 1 亚临界**：水面波可上溯 → 水面与床面**反相**（波痕、沙丘域）；**Fr = 1 临界**：波驻定 → **驻波**；**Fr > 1 超临界**：波无法上溯 → 水面与床面**同相** → 逆行沙丘域。

验算讲义数值：h = 0.1 m → √(9.81×0.1) = **0.99 m/s** ≈ 讲义 ">1 m/s" ✔；h = 1 m → √(9.81×1) = **3.13 m/s** ≈ 讲义 ">3 m/s" ✔。**两组数值与 Fr = 1 精确吻合，证实讲义确以此式为据。**考试若给水深即可当场算出流速门槛。

### 3.4 沙丘高度—流深比例

```
h_dune ≈ (0.2 – 0.3) × h_flow      (Leeder, 1999)
```
用法：岩石记录中测出交错层理单层（set）厚度，即可粗估当时水深量级。📎 由于沙丘被埋藏时通常只保存下部（波峰被后续侵蚀削去），实测 set 厚度往往**小于**原沙丘高度，故估出的水深是**下限**。

### 3.5 图表的文字描述

**图 A：Allen (1985) 存在域图**（讲义图注：*experimental occurrence of current ripples, dunes and lower stage plane beds in quartz sands and silts*）

- **纵轴：无量纲床面剪应力**；**横轴：相对粒径**，定义为**粒径 D 与粘性次层厚度之比**。
- **分区**：current ripples / dunes / lower stage plane beds 三个稳定域。
- **怎么读**：(1) 先看横坐标——颗粒相对粘性次层是"淹没"还是"刺穿"：左侧（水力光滑）落入**波痕**域，右侧（水力粗糙）在低剪应力时落入**下部平床**域，这正是两条粒径规则的图形表达；(2) 沿纵轴上移即提高剪应力，无论从哪个域出发向上都进入**沙丘**域——图形化地证明了 **"沙丘绝不是最先出现的床形"**（沙丘域永远在其他域**上方**）；(3) 波痕域与沙丘域之间**没有连续过渡带**，界线明确，对应 *transition is abrupt*。
- 📎 纵轴即 **Shields 参数 θ = τ₀ / [(ρ_s − ρ)gD]**，用颗粒水下重量归一化剪应力，使不同粒径/密度的实验可画在同一张图上（讲义未写出该式）。

**图 B：单向流床形序列图**（讲义末页）

一列自上而下的床面剖面示意，条件标注 **"constant flow depth"（流深恒定）**，粒度范围 **fine to coarse sands**，并附警告 **"not all bed forms will develop over the fine to coarse sand size range"**。序列（沿流强递增）：

1. **Lower plane bed** —— 平直、有颗粒运动无地形。*仅粗砂或更粗。*
2. **Ripples** —— 小型不对称三角形，缓迎流面/陡背流面，**水面不受扰动**。*仅中砂或更细。*
3. **Dunes** —— 图中分出 **2-dimensional** 与 **3-dimensional** 两子阶段；水面出现与床面**反相**的起伏。
4. **Washed-out dunes** —— 长而低平，槽与冲刷坑减弱或消失。
5. **Upper plane bed** —— 床面重新变平，输沙极强，近底牵引毯。
6. **Downstream-migrating inphase waves → Standing inphase waves → Antidunes** —— 图旁标注 *inphase waves increasing in amplitude and wave-length*。

**怎么读**：**横向读**（同流强、不同粒径）判断某粒径下哪些床形根本不出现（如中砂无下部平床、粗砂无波痕）；**纵向读**（同粒径、流强递增）给出演替次序，即水槽实验要复现的路线；**反推**（岩石记录）由沉积构造 → 床形 → 在图上定位 → 约束流强区间，再配合 3.4 约束水深。

**图 C：沙丘剖面示意图**（实习要求学生自绘，本周核心作图任务，亦即评分点）

画"**从一个槽底到下一个槽底**"的完整剖面，须含：
- **比例尺**：标出沙丘**高度 h** 与**波长 λ**；
- **部位命名**：trough — stoss（缓）— crest — lee/slip face（陡，25°–30°）— 下一个 trough；
- **水面线**：与床面**反相**——**峰上被拉低（drawn down），槽上隆起（humped）**；
- **局部流向箭头**：迎流面贴床加密（加速），越峰后脱离床面；
- **flow separation point** 标在**波峰**；**reattachment point** 标在**背流面下方槽内**；**separation vortex/bubble** 画在两者之间且**内部箭头指向上游**；
- **迎流面标 erosion，背流面标 deposition**；
- **搬运方式沿程变化**：迎流面下部滚动/滑动 → 向上过渡为跃移 → 高流强时峰附近间歇悬移；背流面为崩落；
- **由观察推断的流速与 τ₀ 沿程变化**：槽→峰递增，越峰后骤降；
- 可选：峰下游水面的 **boil**、槽内的 **scour hole**。

**图 D：逆行沙丘循环行为**（Bridge, 2003，配文 *true antidunes have the following cyclical behaviour*）

一组时间序列剖面，展示单个逆行沙丘的生命周期：(1) 床面与水面出现**同相**低振幅正弦起伏 → (2) 振幅**逐渐放大** → (3) 颗粒自上游波形的**下游面**被侵蚀、沉积于下游波形的**上游面** → 波形整体**向上游平移** → (4) 振幅达临界后水流爬峰能耗过大，**在峰处失速并产生强烈湍流，波形破碎并向上游耗散**（breaking antidune）→ (5) 破碎沿波列**由下游向上游依次触发**，随后开始新循环。

**结论读法**：岩石记录中见到逆行沙丘构造，即可判定当时为 **Fr ≳ 1 的超临界明渠流**，指示极强流条件（📎 如洪峰、决口扇、火山碎屑密度流、水下浊流；具体环境为补充，讲义未列举）。

---

## 四、课堂补充

> **说明：本课全 11 周均无 transcript（课堂录音/字幕）。本段内容全部来自讲义与实习 handout 本身透露的强调事项、操作规范与评分线索，不含任何课堂口头材料。**

**（1）被重复两次的内容 = 最强考点信号。**本周讲义专辟一页 "Important points to remember"，其中波痕的三条（粒径限制、间距随粒径、尺寸与流强/水深无关）与第 3 周讲义 Summary 页**重复**。在无 transcript 的情况下，2.8 那张表应整表背下。

**（2）讲义提问而未作答的两处**——*Why do dunes scale with the flow depth when ripples do not?* 与 *Dunes: just how big can they get?*。这类页面通常对应课堂口头讨论，本课无 transcript，**答案必须自备**（第一问的补充答案见 2.4，已标 📎）。

**（3）安全与纪律。**handout 全大写写着 **"SAFETY NOTE: WATER AND ELECTRICITY ARE A LETHAL COMBINATION!!!!"**。团队规模固定 **8 人**且须**在开始前分配完 8 项分工**；但 handout 同时明确 **"Everyone should make their own observations and calculations"** —— **分工只是分担操作，不分担学习，数据记录与计算是个人责任。**

**（4）操作规范（直接影响数据质量与评分）。**
- **工作段**：蜡笔在玻璃上标出水槽**中央 50 cm**，所有观测测量都在此段内完成，**远离进出口效应**。
- **平均水深**：基于工作段内**至少 5 点、每点间隔 10 cm** 的测值取平均。
- **量取基准**：⚠️ handout 专门以 "Note that..." 提醒——**从自由水面量到沙床顶面，不是量到硬质槽底**。量错会系统性污染 τ₀ 与 Re。
- **前半段要耐心**：handout 加粗要求每次调整后让流与床达到某种**平衡态**，至少让新床态在中段工作区完整建立再测量。
- **后半段要抢时间**：handout 斜体警告——上部床形阶段输沙率极高，**会超出水槽泥沙循环能力，导致床面迅速冲刷到硬质槽底**，每种床形一旦建立必须尽快测完。**界线在 washed-out dunes：之前从容，之后抢时间。**

**（5）评分线索。**课程 ILO 5 要求"sketch... and construct sedimentary logs"，实习 ILO 对应一条为 *illustrate your observations using **interpreted, annotated** diagrams which show both the physical observations and processes of erosion, transport and deposition*。⚠️ **关键词是 interpreted 与 annotated：只画形状、不标注、不写过程解释的素描按标准不合格**——图上必须同时出现"看到了什么"与"这说明了什么过程"。实习 ILO 另有一条软技能项，要求在实验中**评估自己的观察并按需调整操作步骤**，即 handout 上的坡度/挡位是**指引而非配方**。课程整体评分：**笔试 50%，两份实习报告各 25%**；第一份约 **10 月底**交，**含素描共 5 页**，两周内返回反馈，考核 ILO 1–3、5——**本周的水槽实验与沙丘素描正处在第一份报告的取材窗口内。**

---

## 五、Practical 要点

### 5.1 这份跨周 handout 在第 4 周的用法

**这是同一水槽实验的第二次（也是最后一次）课时。**依据：handout 只安排**一个实验**但内部分为 **A1–A6**；第 3 周讲义明写 "We will conclude our experiment next week"，并把下周内容列为 dunes to antidunes；第 3 周讲义知识**覆盖到波痕为止**，恰对应 A1（流态）与 A2（起动临界剪应力 + 波痕出现）；本周讲义知识**从沙丘开始**，与 **A3「Transition to dunes」** 精确对齐。

| 段落 | 标题 | 归属 |
|---|---|---|
| 背景/ILO/设备/准备 | — | 第 3 周（本周沿用工作段标记与分工） |
| A1 | Basic description of the flow and bed just prior to the initiation of sediment transport | 第 3 周 |
| A2 | Conditions at the initiation of sediment transport（+ 波痕出现） | 第 3 周 |
| **A3** | **Transition to dunes** | **第 4 周（本周起点）** |
| **A4** | **Dune planform and flow strength** | **第 4 周** |
| **A5** | **Transition from dunes to upper plane bed** | **第 4 周** |
| **A6** | **Conditions during the formation of standing waves and antidunes** | **第 4 周** |

*（handout 本身未逐条标注"第几周做哪段"，上表分界依据两周讲义内容与第 3 周的明文预告推断；若第 3 周未做到波痕，本周需从 A2 末补起。）*

### 5.2 固定条件与其直接后果

**粒径平均 255 µm、范围 300–150 µm（中砂）；颗粒为石英；流体为 20 °C 的水。唯一被改变的变量是流动强度**（泵挡位 + 水槽坡度两个旋钮）。

⚠️ **这一设定决定了本次实验会/不会出现哪些床形：**255 µm 是中砂，按讲义"下部平床只在粗砂或更粗形成"，**本实验不会出现 lower plane bed**，而是从 **plane bed with no motion（无运动平床）** 直接跳到**波痕**。这正是床形序列图那句 *not all bed forms will develop...* 的现场演示。

### 5.3 分工（8 人，第 3 周已分，本周沿用）

Job 1 水槽总控（"the fat controller"）兼溢流监视｜Job 2 数据记录｜Job 3 床面坡度（数字水平仪）｜Job 4 流动可视化（红色食用色素 + 移液管）｜Job 5 床形迁移速率（蜡笔 + 秒表 + 直尺）｜Job 6 流速法一（流速仪）｜Job 7 流速法二（秒表 + 中性浮力绿球）｜Job 8 流深（直尺）。

### 5.4 本周逐段操作与判据

**A3 向沙丘过渡。****把泵提高到挡位 III**，流深与输沙率立即增大；**必要时逐级增坡**直到看见颗粒周期性跳跃弹起（=**saltation 跃移**），尽管主要运动仍是滚动；**等沙丘床在整个工作段建立**后再观测。

观察清单（handout 逐条）：**水面在峰上被略微拉低、在槽上隆起 → 水面波与床面波反相**；背流侧的 **boils**；迎流面上的**滚动与跃移**；背流面上的**崩落**；背流面上的 **separation bubble** 及其造成的**上游向水流把颗粒倒扫回滑落面**；沙丘走向、**脊线样式**、**scour hole 的有无与位置**。

作图：按 3.5 图 C 的全部要素画一张槽—槽沙丘横剖面精细素描（本周最重要的可评分产出）。

测量：蜡笔 + 秒表 + 直尺记录**向下游迁移速率**；**方法一**流速仪测**平均流速**；**方法二**绿球测**表面流速**；**handout 追问：为什么两者差这么多？**

📎 **背景补充（这一问的答案）：**明渠湍流的垂向流速剖面近似对数分布，**近底最低、水面附近最高**。绿球随自由水面漂移测到的是**表面流速**，流速仪按规范在约 0.6h 深处测得的才接近**断面平均流速**，经验关系约 **Ū ≈ 0.80–0.85 × U_surf**，故方法二**必然系统性偏高**。⚠️ **Re 与 Fr 必须用平均流速**，误用表面流速会高估 Fr，可能把亚临界流误判为超临界流。

**A4 平面形态与流强。****把流量阀完全打开**至最大流量。预期：流深再增，跃移更显著，开始出现**悬移载荷**——判据是**颗粒从一个沙丘峰顶腾起后直接落到下一个沙丘的迎流面，中途不在槽内停留**。要回答：输沙量与颗粒运动方式的变化**与沙丘高度、波长的变化有何关系**。预期结论：颗粒开始"飞越"背流面 → 越来越少颗粒被并入床形 → **沙丘变长变低**（呼应"间距随流速增大、高度先增后减"）。**这一段是 washout 起始机制的现场演示。**

**A5 沙丘→上部平床。**(1) **大幅增坡** → 沙丘**变长、振幅减小** → **washed-out dunes**；观察其形态、**槽与冲刷坑是否还在**、推移质运动、**水面 boils 与 drawdown 是否还在**；**当其占满工作段时记录流速、平均水深、坡度**。(2) ⚠️ 此处 handout 插入时间警告（见四·4）。(3) **再次大幅增坡** → 冲刷平化沙丘消失，建立 **plane bed with motion（上部平床）**；观察水深与水面外观变化、boils 与水面湍流的有无，并**从上方俯视注意床面上平行于流向的"条纹"（streaks）**。

📎 **背景补充：**这些条纹即 **primary current lineation（初生流水线理，PCL）**，由近底高低速条带造成颗粒定向排列。岩石记录中 PCL 出现在**平行层理砂岩的层面上**，是**上部平床的诊断标志**，也是野外区分上、下部平床的关键（**下部平床没有 PCL**）。

**A6 驻波与逆行沙丘。**坡度的增量幅度本身就是判据的一部分，须按 handout 的"小/较大/中等"执行：
1. **小幅增坡** → 平坦光亮的水面开始变形为**几乎静止的起伏 = standing waves**；观察床面形貌及**床面特征与水面形态的对应关系**（此时二者开始进入**同相**）。
2. **较大幅度增坡**推进到上部流态深处 → 观察水面波振幅及其下方床形的**对称性与规则性 = antidunes**；观察**颗粒从一个逆行沙丘的下游面被侵蚀、沉积到下游那个的上游面**；**验证上游迁移的方法（handout 明确给出）：用蜡笔在侧壁玻璃上描出某个逆行沙丘的轮廓，观察其随时间移动**。⚠️ handout 强调："必须认识到，**水与颗粒始终向下游运动**，尽管床形本身在向上游移动。"
3. **中等幅度增坡** → 泥沙运动增强，逆行沙丘移速加快；**新现象**：振幅增大使水流爬峰能耗越来越大，**当水流在峰处失速并产生强烈湍流时床形被破坏、向上游破碎耗散 = breaking-antidunes**；**破碎不是随机的——下游波的破碎会触发上游相邻波破碎，沿水槽依次向上游传递**，自然界中导致**脉动流**，但因需要**极高且持续的床沙输运量**而**相对罕见**。

### 5.5 "看到什么 → 判定为什么床形"的判据链

| 观察到的现象 | 判定 |
|---|---|
| 床面平直，无颗粒运动 | **Plane bed with no motion**（τ₀ < τ_cr） |
| 小型三角形床形（高数毫米、长 1–2 cm），缓迎流面 + 陡背流面；**水面完全不受扰动** | **Ripples**，输运几乎纯推移质 |
| 床形显著增大、更长且顶部更平；**开始扰动自由水面**；出现跃移；水面峰上下凹、槽上隆起（**反相**） | **Dunes** |
| 出现 boils、背流面分离泡、槽内冲刷坑；脊线由平直变弯曲/新月形 | **3-D dunes** |
| 颗粒自峰顶腾起直接落到下游沙丘迎流面 | 悬移开始参与 → **washout 起点** |
| 床形变得**长而低**，槽与冲刷坑减弱或消失 | **Washed-out dunes** |
| 床面重新变平但输沙极强；水面平滑；**俯视见平行流向条纹** | **Upper plane bed**（+ PCL） |
| 水面出现几乎静止的起伏 | **Standing waves**（Fr ≈ 1） |
| 床形对称规则、与水面波**同相**；描线显示床形**向上游移动** | **Antidunes**（Fr > 1） |
| 振幅增大后在峰处失速湍流破碎，并沿波列向上游依次触发 | **Breaking antidunes** |

**判据链中的"一票否决"项：**①**水面是否受扰动**——区分波痕与沙丘最可靠的现场判据；②**水面波与床面波同相还是反相**——区分沙丘域与逆行沙丘域；③**床形迁移方向**——顺流为波痕/沙丘，**逆流为逆行沙丘**（蜡笔描线验证）。

### 5.6 预期结论与评分要点

**预期结论：**在粒径、密度、流体性质全部固定的条件下，**仅提高流动强度**，中砂床面即依次经历 **无运动平床 → 波痕 → 2-D 沙丘 → 3-D 沙丘 → 冲刷平化沙丘 → 上部平床 → 驻波 → 逆行沙丘 → 破碎逆行沙丘**。**床形序列因此是流动强度的记录**，反过来即可由岩石中的沉积构造反演古流动条件。

**评分要点：**①素描必须 **interpreted + annotated**，同时呈现物理观察与过程解释，第三方仅凭图即可识别该床形；②测量规范（中央 50 cm、≥5 点 ×10 cm 间隔的水深、量到沙床顶面、SI 单位）；③计算完整（A1 的 Re、A2 的 τ_cr、A3 的迁移速率与两种流速及其差异解释）；④**每人独立完成自己的观察与计算**；⑤能根据床面实际反应临场调整操作，而非机械执行 handout。

---

## 六、易错点 / 重点难点

1. **"沙丘是长大的波痕"——错。**讲义直接否定：*ripples don't grow into dunes – transition is abrupt*。两者由不同边界层机制（水力光滑 vs 粗糙）控制，在 Allen 图上分属不连续的两域。
2. **"沙丘是最先出现的床形"——错。***Never first (lowest velocity) bedform to appear*；其前必有波痕（细—中砂）或下部平床（粗砂）。
3. **"plane bed with no motion" ≠ "lower plane bed"。**前者 τ₀ < τ_cr、完全无运动；后者**有活跃输运但无明显地形**，且**只在粗砂或更粗中出现**。本次实验用中砂，**不会出现 lower plane bed**。
4. **上、下部平床的区分。**下部平床：限粗砂及更粗、低流强、接触载荷；上部平床：**任何粒径**、极高剪应力、**悬移主导**、近底牵引毯。📎 野外靠 **PCL** 区分（上部有、下部无）。
5. **沙丘高度随流速"先增后减"，不是单调增；间距才一路增大。**washout 是非单调性的原因。**本周最常答错的一条。**
6. **"波痕尺寸随流强或水深变化"——错。**波痕**尺寸**与二者均无明确关系（波长只随粒径 λ≈1000d），只有**平面形态**随流强与**流历时**变化。第 3 周补充：充分发育的波痕总是三维的，二维波痕说明**流动短暂**或**有波浪参与**。
7. **逆行沙丘"向上游迁移"≠ 水或颗粒向上游运动。**水与颗粒始终向下游；机制是"下游面侵蚀 + 上游面沉积"的位置迁移。
8. **Fr 与 Re 混淆。**Re 判**层流/湍流**（本课结论：明渠流永远湍流）；Fr 判**亚/超临界**（决定同相还是反相）。两者都含 U 与 h，极易记混。
9. **τ₀ 计算中 S 必须是无量纲坡降**（m/m 或 sin α），不可代百分数或角度。
10. **水深必须量到沙床顶面**，量到硬质槽底会同时高估 h，使 τ₀、Re 全线偏大、Fr 偏小。
11. **两法测速的差异是物理不是误差。**答"测量误差"不得分，必须说出**垂向流速剖面**（表面流速 > 断面平均流速）。
12. **washout 的机制表述**必须写"跃程相对背流面长度变长、悬移主导、颗粒越过背流面而不被并入床形"，而非"水把沙丘冲平了"。
13. **"逆行沙丘需要自由水面"常被忽略。**它意味着**满管流中不可能出现逆行沙丘**；在岩石记录中识别出逆行沙丘构造，就同时约束了"当时存在自由水面的明渠流"。
14. **实验节奏的两难：**至沙丘阶段要**耐心等平衡**，washed-out dunes 之后要**抢时间**，否则床面被冲刷到底板。**踩错节奏会直接丢掉 A5/A6 的数据。**
15. **不要指望一次实验看到"全部"床形。**序列图明确标注 *not all bed forms will develop over the fine to coarse sand size range*。报告中应**明确说明本粒径条件下哪些床形不会出现、为什么**——这本身就是理解程度的体现。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| Bed configuration | 床面组构 | 某时刻床面的整体几何形态 |
| Bedform | 床形 | 构成床面组构的单个地形单元 |
| Sedimentary structure | 沉积构造 | 床形迁移在沉积物内部留下的记录 |
| Unidirectional flow | 单向流 | 本周全部内容的流动前提 |
| Dune | 沙丘 | 大型不对称床形；需 >~0.2 mm 粒径与水力粗糙边界 |
| Ripple | 波痕 | 小型不对称床形；限中砂或更细；不扰动水面 |
| Compound bedform | 复合床形 | 波痕叠置于沙丘迎流面形成的多尺度床形 |
| Stoss side | 迎流面 | 平缓一侧，发生侵蚀 |
| Lee side / Slip face | 背流面 / 滑落面 | 陡的一侧，发生沉积与崩落 |
| Crest / Trough | 波峰 / 槽 | 床形最高点（流动分离处）／最低处 |
| Form ratio | 形态比 | 📎 波长/高度；2-D 沙丘 50–200，3-D 沙丘 15–20 |
| Angle of repose | 休止角 | 松散颗粒可维持的最大坡角，25°–30° |
| Flow separation / Reattachment point | 流动分离 / 再附着点 | 流动在峰处脱离床面／重新接触床面（槽内） |
| Separation bubble / vortex | 分离泡 / 分离涡 | 背流面下方回流区，内部水流向上游 |
| Boil | 涌沸 | 沙丘引起的大湍流涡上升至水面的沸腾状扰动 |
| Bursting cycle | 猝发循环 | 近底湍流的抬升—下扫周期，被沙丘地形组织化 |
| Scour hole | 冲刷坑 | 背流面下方槽内的局部深挖 |
| Avalanching | 崩落 | 颗粒堆积至休止角后成片下滑 |
| Rolling / Sliding | 滚动 / 滑动 | 接触载荷的运动方式 |
| Saltation | 跃移 | 颗粒跳跃弹起 |
| Suspended load / Intermittent suspension | 悬移载荷 / 间歇悬移 | 被湍流托举、长时间不接触床面／介于跃移与完全悬移之间 |
| Traction carpet | 牵引毯 | 上部平床条件下近底高浓度输沙层 |
| Excursion length | 跃程 | 颗粒离底到落底之间的流向距离 |
| Washout / Washed-out dunes | 冲刷平化 / 冲刷平化沙丘 | 沙丘变长变低直至消失的过程与产物 |
| Lower plane bed | 下部平床 | 有输运无地形；仅粗砂或更粗 |
| Upper plane bed / Plane bed with motion | 上部平床 | 极高剪应力、悬移主导；任何粒径均可形成 |
| Primary current lineation (PCL) | 初生流水线理 | 📎 上部平床的诊断标志，层面上平行流向的条纹 |
| Standing wave | 驻波 | 几乎静止的水面起伏，Fr ≈ 1 |
| Inphase wave | 同相波 | 水面波与床面波相位一致的床形域 |
| Antidune / Breaking antidune | 逆行沙丘 / 破碎逆行沙丘 | 同相、向上游迁移；需 Fr>1 与自由水面／振幅过大后在峰处失速破碎 |
| Supercritical / Subcritical flow | 超临界流 / 亚临界流 | Fr>1 水面扰动无法上溯／📎 Fr<1 可上溯 |
| Froude number (Fr) | 弗劳德数 | 📎 Fr = U/√(gh) |
| Reynolds number (Re) | 雷诺数 | Re = Uhρ/μ；<500 层流，>2000 湍流 |
| Bed shear stress (τ₀) / Critical shear stress (τ_cr) | 床面剪应力 / 临界剪应力 | τ₀ = ρghS；起动条件 τ₀ = τ_cr |
| Du Boys equation | 杜布瓦方程 | τ₀ = ρghS |
| Exner equation | 埃克斯纳方程 | 床面高程变化由输沙率的空间梯度决定 |
| Hydraulically smooth / rough | 水力光滑 / 粗糙 | 由粒径与粘性次层厚度之比决定 |
| Viscous sublayer | 粘性次层 | 紧贴床面的层流薄层 |
| Flume | 水槽 | 顶部开敞的人工渠道，本周实验器材 |
| Palaeocurrent | 古水流 | 由不对称床形/交错层理恢复的古流向 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `(EART27201) Sedimentary Rocks and Fossils.md` — Syllabus，W4 条目 | "W4: Lecture: Macrofossils I. Trilobites and Brachiopods… Practical: Examination and identification of different macrofossil groups using hand specimens." | 与实际发放的第 4 周材料完全不符：实际讲义为 "Class 4: Bed Configurations (Part 2)"，实习为水槽实验。整门课实际周次与大纲系统性错位（大纲 W3 碳酸盐岩、W4–W8 宏体化石；实际 W3–W4 床面形态、W5 沉积构造、W6 非碎屑岩、W7–W11 古生物） | 复习以**实际讲义**为准；大纲的 ILO、评估方式与阅读书目仍然有效 |
| `Class 4 slide handout 2025revised.md` — "Important points to remember" 末行 | "Antidunes require a free surface and that the flow is supercritical (i.e. **Fr~1**)" | 与同一讲义前文自相矛盾——"Inphase wave bedforms (Antidunes)" 页写的是 "supercritical flows (i.e. **Fr>1**)" | 超临界流定义为 **Fr > 1**；**Fr ≈ 1 对应的是驻波**这一临界状态，而非真正的逆行沙丘。此处应为 Fr > 1 |
| `Class 4 slide handout 2025revised.md` — 末页床形序列 | "Downstream-migrating inphase waves / Downstream-migrating inphase waves / Standing inphase waves / Antidunes" | 第一项连续重复两次 | 应为三项：**向下游迁移的同相波 → 驻定同相波 → 逆行沙丘（向上游迁移）**；重复系 PDF 转录时的重复捕获 |
| `Class 3 practical handout 2025.md`（Week 4 副本）— A2 段 | "Remember for grains to move  0 … =  cr" / "� � = ��ℎ�" | PDF 转 md 时希腊字母与公式符号丢失，公式成乱码，τ₀ 与 τ_cr 的下标丢失显示为孤立的 "0" 与 "cr" | 公式应为 **τ₀ = ρ g h S**，起动条件 **τ₀ = τ_cr**。另 handout 中 "Du Buoys" 的标准拼写为 **Du Boys** |
| `Class 3 practical handout 2025.md`（Week 4 副本）— Procedure 第二段 | "Allow the tank to **setting** a couple of minutes." | 拼写/语法笔误 | 应为 "Allow the tank to **settle** for a couple of minutes."（静置几分钟）。同文另有 "Well doneyou have initiated…" 缺空格、ILO 一节 "make evaluate your observations" 中 "make" 冗余，均为排版笔误，不影响理解 |
| `Class 4 slide handout 2025revised.md` 与第 3 周讲义 "Current Ripples" 页 | 本周："Ripples form only in **medium sand or finer**"；第 3 周："Mean grain size must be **<0.5-0.7 mm** (vf-m sand and some c sand)" | 粒径上限不一致：中砂上限为 0.5 mm，而 0.5–0.7 mm 已属粗砂，第 3 周还明写 "and some c sand" | 非严格矛盾而是精度差异。记忆用"中砂或更细"这一保守表述，但需知波痕可延伸至细粒粗砂（约 0.7 mm）；答题建议写 "≲0.5–0.7 mm（中砂及更细，可及部分粗砂）" |
