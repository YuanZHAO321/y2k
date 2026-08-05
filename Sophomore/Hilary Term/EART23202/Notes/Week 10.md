# EART23202 Interpreting the Stratigraphic Record — Week 10 学习笔记

> 本周材料：Lecture `Aeolian_Systems (1)`（*Aeolian Systems: Processes and Deposits*，Ian Kane & Grace Cosgrove，共 53 张幻灯片，约 4,825 词——**本课 10 周中最长的一份讲义**）。
> **本周无 practical。** 本课 Practical 只开设到 Week 6，碎屑岩后半段（W07–W10）本就没有实习课，**不是材料缺失**（见第五节）。
> 本课程**全 10 周均无 transcript（课堂录音转写）**，因此「四、课堂补充」一段的内容**全部来自讲义本身**——讲义反复强调的注意事项、图件与案例透露的重点，**不来自课堂口述**。
> 凡以 `📎 背景补充：` 开头的内容为原材料所无、由笔记补足的背景，请与讲义原有内容严格区分。
> **本周是全课最后一周。**

---

## 一、本周主题

本周主题为**风成体系：过程与沉积产物（Aeolian Systems: Processes and Deposits）**。

讲义在第 2、3、24、49 张幻灯片上**反复出现同一张"路线图"页**（共出现 4 次，作为章节分隔），把整堂课拆成三个递进的问题。这三问就是本周的骨架，也是复习时最应该能自问自答的三条主线：

1. **What are aeolian transport processes and where do they operate?**
   风成搬运过程是什么？它们在哪些环境中运作？（幻灯片 4–23）
2. **How do aeolian bedforms develop?**
   风成床型如何发育？（幻灯片 25–48）
3. **How do migrating bedforms in active dune fields form sediment accumulations?**
   活动沙丘场中迁移的床型，如何形成沉积**堆积体（accumulation）**？（幻灯片 50–53）

注意第三问的措辞：讲义问的不是"沙丘长什么样"，而是**迁移中的床型如何变成地层**。这条从"现代过程"到"岩石记录"的转换，正是整门课的核心方法论（相分析 + 瓦尔特定律），本周是它在碎屑体系中的**最后一次、也是最纯粹的一次演练**——因为风成体系是所有沉积体系中"过程—产物"对应关系最干净的一个：一种纹层类型 ≈ 一种明确的物理过程 ≈ 沙丘上一个明确的位置。

### 本周在全课骨架中的位置

本课的实际授课顺序，可由 `Lecture/` 各周文件夹下的讲义**文件名**直接确认（这是仓库中的硬证据，可靠）：

| 周次 | 讲义文件名 | 板块 |
|---|---|---|
| W01 | `01-Stratigraphic methods` | **方法论** |
| W02 | `L2 Facies analysis` | **方法论** |
| W03 | `03-Carbonate platforms` | 碳酸盐 |
| W04 | `04-Facies peritidal-subtidal-shoal` | 碳酸盐 |
| W05 | `05-Facies reef-basin` | 碳酸盐 |
| W06 | `06-Carbonate dynamics` | 碳酸盐 |
| W07 | `Shallow Marine Clastic Environments` | **碎屑** |
| W08 | `Continental Environments Lecture` | **碎屑** |
| W09 | `Deep-water Sedimentary Systems: Process to product` | **碎屑** |
| **W10** | **`Aeolian_Systems`** | **碎屑（本周，全课收尾）** |

> ⚠️ **课程大纲（Syllabus）列出的顺序是"先碎屑（1–6）后碳酸盐（7–10）"，与实际讲义完全颠倒。** 大纲只能用作课程总体目标（ILO）、考核权重与推荐读物的参考，**绝不能用来推断某一周讲了什么**。本表依据的是文件名，不是大纲。

所以本周是**碎屑板块的第四类、也是最后一类沉积环境**。把碎屑段四周连起来看，是一条"离水越来越远"的路径：

```
W07 浅海（波浪/潮汐主导，水下）
  ↓
W08 陆相（河流/湖泊/冲积扇，水在陆上）
  ↓
W09 深水（重力流，水下但远离陆源）
  ↓
W10 风成（介质由水换成空气）  ← 本周
```

**W10 与前三周最根本的区别，是搬运介质从水变成了空气。** 空气密度约为水的 1/800、黏度约为水的 1/55，这一条物理差异会自上而下地改写全部结论：能被搬动的粒度上限更低、颗粒被抛离床面的高度与距离更大、颗粒之间的**碰撞（ballistic impact）**取代流体本身成为主要的启动机制、床型的规模上限却反而更大（可达 draa 级、波长数公里）。讲义虽然没有把这组对比写成一页表格，但它在整堂课里以"跃移—蠕移—反跳三分""冲击波痕""颗粒流—颗粒降落—风成波痕三类纹层"的形式反复体现。

> 📎 **背景补充（材料未直接给出这一对比表，由笔记整合）：**
>
> | | 水流搬运 | 风成搬运 |
> |---|---|---|
> | 介质密度 | ~1000 kg/m³ | ~1.2 kg/m³ |
> | 可搬运粒度上限 | 可达砾级以上 | 通常止于砂级；砾以上留为**滞留砾（reg / serir）** |
> | 跃移轨迹 | 短、低 | **长、高**（可达数十倍粒径的高度、米级的水平距离） |
> | 启动机制 | 流体拖曳/上举为主 | **弹道撞击（impact）**同等重要甚至主导 |
> | 分选与磨圆 | 变化大 | 通常**极好**（长时间反复跃移与撞击） |
> | 床型规模上限 | 沙丘级 | **巨型沙丘（draa）**，波长 500–5000 m、高 >50 m |
>
> 讲义的原文只支持其中"粒度上限（幻灯片 6）""跃移长度控制波痕间距（幻灯片 31）""draa 尺度（幻灯片 47）"三条；**"分选极好、磨圆高"这两条在本讲义中并未出现**，答题时若要用请注意这是常识性补充，而且第六节会指出它其实是个陷阱。

### 与上下游课程的关系

- **上游：EART27201 Sedimentary Rocks and Fossils**（大纲中列明的**唯一 compulsory prerequisite**）。本周几乎每一页都建立在该课的三块基础上：**床型（bedform）概念**、**交错层理的组构（set / coset / foreset / bounding surface）**、**古流向分析**。讲义幻灯片 42–43 讲"床型爬升产生层组与界面"时，是直接默认你已经掌握 set/coset 术语的。
- 📎 **下游：EART26001 Energy and Resources。** 风成砂岩是全球最重要的常规油气储层之一——**北海二叠系 Rotliegend 砂岩**是英国南部气田的主力储层，美国犹他州的 Navajo / Entrada / Cedar Mesa 砂岩（本讲义反复引用的露头案例）是同类储层的地面类比体（outcrop analogue）。风成砂岩之所以是好储层：分选好、泥质少 → 高孔高渗；但其**非均质性由界面体系控制**——沙丘间（interdune）层与各级界面往往是渗透率屏障。**讲义本身完全没有提储层，这一整段是背景补充。**

---

## 二、核心概念

### 2.1 "aeolian" 的定义与词源（幻灯片 4）

讲义给出的原文定义：

> The adjective, **aeolian** describes genetic processes and products of, **erosion, entrainment, transportation and deposition by the wind**.

即：aeolian（风成的）这个形容词描述的是**由风引起的侵蚀、启动、搬运与沉积**这四类**成因过程及其产物**。

词源：拉丁语 **Æolus**（风神），源自希腊语 **Αἴολος**（Aiolos，风之主宰）。

⭐ 注意定义中的四个动词是**并列**的：aeolian 不只指"风吹来的沉积物"，也包括**风的侵蚀作用（deflation 吹蚀）**及其产物。这一点在第 6、50、52 张幻灯片讨论 **deflation lag（吹蚀滞留）** 与 **保存条件** 时会变得非常关键。

### 2.2 风成颗粒的启动：受力平衡（幻灯片 5）

讲义原文：

> Aeolian sediment entrainment occurs when and where **wind forces are able to overcome the effects of surface stabilisation**.

启动（entrainment）的条件是**风力克服地表稳定化效应**。讲义把作用在颗粒上的力分成两组，并给出图中的字母标注：

**L = lift（上举力）、C = cohesion（黏聚力）、D = aerodynamic drag（空气动力拖曳力）、W = weight（重力）、I = impact（撞击力）**

- **促进启动**：**ballistic impacts（弹道撞击，I）** 与 **aerodynamic lift（空气动力上举，L）**
- **阻碍启动**：**particle weight（W）、friction（摩擦）、cohesive inter-particle forces（颗粒间黏聚力，C）**
- 讲义原文还把 **drag** 也列进了"阻碍"一侧——**这与图中把 D 标为一个独立作用力、以及空气动力学常识相冲突，见文末勘误表第 1 条。**

各力的控制因素（原文，Lancaster, 1995）：

| 力 | 由什么决定 |
|---|---|
| **Drag 与 lift** | 由**流体绕流颗粒**（fluid flow over and around particles）产生 |
| **Weight、friction、cohesion** | 由**颗粒粒径、密度、形状、堆积方式（packing）、含水量（moisture content）、矿物成分、颗粒间胶结程度（degree of inter-particle cementation）** 决定 |

⭐ **右栏这一串控制因素是本周的隐性主线**：后面讲的**湿沙丘间（damp/wet interdune）**、**稳定型体系（stabilising system）**、**地表胶结**、**植被**，本质上全都是通过增大右栏（阻力项）来抑制风的搬运能力。把幻灯片 5 和幻灯片 16、19 连起来读，逻辑就通了。

### 2.3 搬运方式与粒度的对应（幻灯片 6–8）

这是本周最基础也最常考的一组对应关系。讲义按**粒度**给出三条命运：

| 粒度 | 搬运方式 | 结果 |
|---|---|---|
| **砂级及更细（sand and finer）** | 主要作为 **bedload（推移质）** 搬运，然后沉积 | 构成**沙丘（dunes）与沙席（sandsheets）** |
| **粉砂与黏土（silt and clay）** | 主要**悬移（in suspension）搬运于高空（aloft）** | 形成**黄土（loess）**、粉尘、远洋风成组分 |
| **砾级及更粗（gravel and coarser）** | **在多数风况下不被搬动** | 原地残留为**吹蚀滞留沉积（deflation lag deposit）**，即 **reg** 或 **serir** |

原文：*The construction of dunes and sandsheets requires the availability of abundant sand grains, which are mostly transported as bedload prior to deposition.*

> **reg / serir**：讲义给的例子是 **Mojave Desert（美国南加州）的 reg**。这两个词是同义的地方性术语，指细粒被吹走后地表残留的砾石覆盖面（俗称"砾漠/戈壁"）。

**推移质砂的三种具体搬运机制（幻灯片 7，原文三条）：**

1. **Rolling or creep（滚动或蠕移）** —— *due to drag directly on the bed*，由直接作用于床面的拖曳力引起。颗粒始终贴床面移动，不离开床面。
2. **Saltation（跃移）** —— *whereby particles are temporarily lifted into the airflow and then collide with other particles in the flow, thereby inducing a **chain reaction of interparticle collisions***。颗粒被短暂举入气流，随后与流中其他颗粒碰撞，**引发颗粒间碰撞的连锁反应**。
3. **Reptation（反跳/蠕跳）** —— *whereby saltating particles that return to the bed impact and nudge other particles and cause them to **hop short distances downwind***。跃移颗粒落回床面时撞击并"推挤"其他颗粒，使后者向下风向**短距离跳跃**。

⭐ **讲义明确指出（幻灯片 8）：三者之中 saltation 对风成砂搬运"especially important"，而 wind impact ripples（风成冲击波痕）的独特形态正是这一过程的产物。** 这句话是把"搬运过程"和"床型/沉积构造"缝合起来的关键，务必记住。

> ⚠️ **易混：creep vs reptation。** 两者都是"短距离、贴近床面"的运动，但成因不同：
> - **creep** = 气流**拖曳力**直接推动，颗粒滚动/滑动，**不离开床面**；
> - **reptation** = 跃移颗粒**落地撞击**的动量传递，被撞颗粒**短距离跳起**。
> 也就是说 reptation 是 saltation 的"次级产物"，而 creep 不是。

### 2.4 风成过程在哪里运作（幻灯片 9–23）

讲义花了整整一个大节（15 张幻灯片）来强调一件事：**风成 ≠ 沙漠**。

原文列举的运作环境：

> Hot and cold climatic deserts, coastal region, fluvial and glacial outwash plains, volcanic regions and aeolian systems supply sediment to the deep ocean.

即：**热带与寒带气候沙漠、海岸带、河流与冰川外冲平原、火山区**，此外风成体系还**向深海供给沉积物**。

但讲义也立刻限定：*Although aeolian processes operate in various climate regimes, they are currently **most active and widespread in arid, hot and cold deserts***——原因是这些地方有**干燥的砂质基底且缺乏显著植被覆盖（dry sandy substrates that lack significant vegetation cover）**。

#### 2.4.1 沙漠风成环境（幻灯片 10–16）

**关键数字（必背，幻灯片 10）：**

- 现今**约 30% 的陆地表面**为干旱或半干旱气候条件；
- 这 30% 之中，**风成砂沉积覆盖其 20%**；
- 讲义据此写"**6% of the Earth surface**"——**此处换算口径有误，应为陆地表面的 6%，见勘误表第 2 条。**

**沙丘场（dunefield）的分区（幻灯片 11，Porter, 1987）：**

| 术语 | 位置 | 含义 |
|---|---|---|
| **Back-erg（后缘砂海）** | 沙丘场的**上风向（trailing / upwind）边缘** | 砂供给的"尾巴"端 |
| **Fore-erg（前缘砂海）** | 沙丘场的**下风向（leading / downwind）边缘** | 砂体推进的前锋 |
| **Central erg（中央砂海）** | 位于 fore-erg 与 back-erg 之间的**核心区** | 沙丘最发育、最厚 |
| **Erg margin（砂海边缘）** | fore-erg + back-erg + central erg 的**侧向边缘**之合称 | 环绕中央砂海的一圈过渡带 |

⭐ **erg margin 在地层记录中特别重要**：它是风成体系与**非风成体系（河流、盐湖 playa）**相互指状交错的地带，因此常保存最丰富的**相接触关系**与**年代学约束**。

**地貌单元（geomorphic elements，幻灯片 12）：**

原文：*Most larger deserts are subdivided into a series of distinct geomorphic elements, defined by **net sediment erosion, transport (bypass), or deposition**.*

大型沙漠按**净侵蚀 / 净过路（bypass）/ 净沉积**划分地貌单元：

- 净沉积者可发育为 **sand seas（砂海）或 ergs（砂海/沙海）**；
- 讲义定义：*Ergs are wind-formed desert landscapes characterized by extensive sand dunes that cover the terrain.*
- 沙丘还与其他地貌单元共生：**zibars（低平砂垄）、sandsheets（沙席）、interdunes（沙丘间）**，以及一整套**非风成环境**（rivers 河流、playa lakes 盐湖等）。
- 讲义所用的两张卫星影像：**Rub' al Khali（阿曼，ISS027-E-34290）** 与 **Ténéré Desert（撒哈拉沙漠内，尼日尔，ISS022-E-5258）**，后者上直接标注了 dune / interdune / sandsheet / zibar 四个单元，比例尺分别为 10 km 与 5 km。

**⭐ 体系三分：dry / wet / stabilising（幻灯片 16，Kocurek & Havholm, 1993）**

这是本周**最重要的分类之一**——它分的不是"沙丘形态"，而是**堆积（accumulation）受什么控制**：

| 类型 | 堆积由什么控制（原文关键句） | 机理 |
|---|---|---|
| **Dry（干型）** | *accumulation is controlled **solely by aerodynamic configuration*** | **下风向气流减速（down-wind airflow deceleration）**使载砂风卸下部分负载 |
| **Wet（湿型）** | *accumulation is controlled by **progressive water-table rise** concomitant with ongoing aeolian activity* | 地下水位**持续上升**，与沙丘迁移同步进行，把砂"锁"在水位之下 |
| **Stabilising（稳定型）** | *physical, chemical or biogenic agents promote aeolian system construction and accumulation* | 例如**植被（vegetation）或地表胶结（surface cements）**限制了风的**搬运能力（transport capacity）** |

讲义给出的实例：Ténéré Desert（撒哈拉）代表干型；**Baleal, Peniche（葡萄牙）** 的植被固定海岸沙丘代表稳定型。

> ⚠️ **不要把 dry/wet/stabilising 体系（幻灯片 16）与 dry/damp/wet 沙丘间（幻灯片 44）混为一谈。** 前者是**整个体系的堆积控制机制**（三分法主体是"什么让砂留下来"），后者是**沙丘间洼地相对于潜水面位置的三种状态**（主体是"地下水位在哪"）。二者相关但不是同一层级的概念，考试极易搞混，第六节还会再点一次。

#### 2.4.2 海岸风成环境（幻灯片 17–18）

- 例：**Namib Desert（纳米比亚）** 沿南大西洋岸展布，南大西洋的**冷水**显著影响该区气候与天气型式。
- 海岸沙丘场的成分可为**硅质碎屑（siliciclastic）、碳酸盐（carbonate）或二者混合**。
- **硅质碎屑海岸沙丘场**：典型见于**湿润的中—高纬度海岸**。
- **碳酸盐海岸沙丘场**：优先形成于**中—低纬度海岸**，尤其是**毗邻高生产力浅海台地**者——因为台地提供了充足的碳酸盐沉积物供给。
  - ⭐ 这一句直接把本周与 **W03–W06 的碳酸盐板块**接上了：碳酸盐工厂生产的颗粒，可以被风搬上岸变成**风成岩（aeolianite）**。
- 讲义给的 **aeolianite（风成岩/风成碳酸盐砂岩）** 实例三处：**Orkney 群岛 Aikerness（苏格兰）**、**Long Island（巴哈马）的全新世风成岩**、**Horseshoe Bay（百慕大）**。
- 海岸沙丘随**离岸距离**发生序列变化（幻灯片 18A）：讲义图注提到 **yellow dune（黄沙丘，带 Marram Grass 滨草，丹麦 Grenen）** 与 **grey dune（灰沙丘，葡萄牙 Baleal）**。
  - 📎 **背景补充**：标准的海岸沙丘序列由海向陆为 **embryo dune（胚胎沙丘）→ foredune / yellow dune（前丘/黄沙丘，先锋植被如滨草固定）→ grey dune（灰沙丘，植被覆盖度高、有机质与土壤开始发育、颜色变灰）→ 有时进一步到 dune slack / 林地**。"黄→灰"的颜色变化记录的是**植被定殖与成土作用的进程**，因此这一序列本身就是幻灯片 16 中 **stabilising system** 的活教材。**讲义只给了 yellow / grey 两个词和图，没有写出完整序列。**

#### 2.4.3 非沙漠、地外与粉尘（幻灯片 19–23）

- **非沙漠湿润环境（幻灯片 19）**：只要**可供搬运的沉积物过剩（a surfeit of sediment available for transport）**且**风速足够克服地表湿气产生的阻力**，风成过程照样广泛发育。典型是**冰前区（pro-glacial regions；McKenna-Neuman & Gilbert, 1986）**。但湿润区**植被的稳定作用**通常会抑制风成过程。
- **地外风成环境（幻灯片 20）**：讲义列出 **Mars（火星）、Venus（金星）、Earth's Moon（月球）、Titan（土卫六）**，以及 **Eros、Itokawa（糸川）等小行星**。重点实例是**火星盖尔撞击坑（Gale crater）内的 Bagnold 沙丘场**（长 35 km × 宽 2 km），由 **NASA 好奇号（Curiosity）漫游车**详细考察；另有 **HiRISE 拍摄的火星新月形沙丘（barchan）假彩色影像**。
  - ⚠️ **月球与小行星没有大气，严格意义上不存在"风成"过程，见勘误表第 3 条。**
- **黄土（loess，幻灯片 21）**：由**细粒的风成粉砂与黏土**组成。多与**过去冰期广泛冰川活动**的地区相关联。主要分布区：**美国中西部、中国黄土高原、俄罗斯草原、欧洲部分地区**。形成机制：强风把**冰川外冲平原、河谷、沙漠**等裸露地表的细粒物质搬走并再沉积。黄土**矿物富集、保水性好因而肥力高**，但**极易受侵蚀**，尤其在农耕与工程扰动之后。
- **粉尘对其他体系的贡献（幻灯片 22）**：严重事件中大气粉尘浓度可超过 **6000 μg·m⁻³**（Song et al., 2007）。社会影响：能见度下降与交通中断、农业减产、粉尘相关呼吸系统疾病。地球系统意义：**沙尘暴向海洋输入富营养粉尘，刺激浮游植物（海洋食物链的初级生产者）生长，即"海洋施肥"（ocean fertilization；Han et al., 2008）**。
- **火山灰的风成搬运（幻灯片 23）**：可达 **100s–1000s km**，取决于喷发规模、风场型式与大气条件。**细灰（<0.1 mm）** 可长时间悬浮并远距离搬运，粗粒则近源沉降。**颗粒密度与形状**控制沉降速度与悬浮特性——**较轻、形状越不规则的颗粒，越可能长时间悬浮、远距离搬运**。
  - ⭐ 这一页对**火山灰层（tephra / bentonite）作为等时面**用于地层对比有直接意义（呼应 W01 的地层学方法）。📎 该应用讲义未点明。

### 2.5 风成床型的三级尺度（幻灯片 25、26、29、41、47、48）

⭐ **本周第二个核心分类。** 讲义在整堂课中把这张图**重复放了三次**（幻灯片 25、29、41），是最强的"这会考"信号。

> Three distinct scales of aeolian bedform that commonly occur on Earth: **ripples, dunes and megadunes (draa)**.

三级尺度（由小到大）：**波痕（ripples）→ 沙丘（dunes）→ 巨型沙丘（megadunes / draas）**。

- 判别依据图：**Grainsize（取"最粗二十分位数"，coarsest twenty-percentile）对 wavelength（波长）** 的散点图（Modified after Wilson, 1972）。
- 讲义特别注明：*bedforms developed at scales **between** the three fields depicted in the graph **do occur** on Earth, but are less common*——**三个尺度域之间的过渡型床型确实存在，只是较少见**。这是一句防"绝对化"的限定语，值得记。

**关于这套层级的几条原文要点（幻灯片 26）：**

- 三者构成一个**平衡床型的层级体系（a hierarchy of equilibrium bedforms）**；绝大多数沉积性风成环境中都至少存在其中一种或多种。
- **床型的尺寸是最初步的分类与描述依据**（bedform size provides a basis for initial bedform classification and description）。
- **几乎所有沙丘与巨型沙丘的斜坡面上都有波痕**；波痕在**沙席表面与沙丘间**同样常见。
- 风吹表面上有**三种形态上不同的小尺度波痕构造**：**impact ripples（冲击波痕）、megaripples（巨波痕）、adhesion ripples（黏附波痕）**。三者在**垂向剖面**中都能识别，各自产生**不同类型的风成波痕纹层或层理**。
  - ⚠️ **讲义只详细展开了 impact ripples（幻灯片 30–33）与 adhesion ripples（幻灯片 46），megaripples 全程未再提及。** 这是材料的一处内容缺口。
  - 📎 **背景补充**：megaripples（也称 granule ripples）是**双峰粒度**条件下形成的大型波痕，波长可达米级，脊部富集粗砂—细砾，其成因是粗颗粒无法跃移、只能被跃移砂反复撞击而蠕移到脊上。**材料未说明。**

**megadunes / draas（幻灯片 47）：**

- 规模：**波长 500–5000 m、高度 >50 m**（Wilson, 1971, 1972）。
- 形态上为 **compound（复合型）或 complex（复杂型）**（sensu McKee, 1979），其共同点是**其上可以承载叠加的沙丘级床型（superimposed dune-scale bedforms）**。
- ⭐ **compound 与 complex 的区别（高频考点，一字之差）：**
  - **Compound draa**：较小的沙丘叠加在**同一形态类型**的较大沙丘之上。
  - **Complex draa**：较小的沙丘叠加在**不同形态类型**的较大沙丘之上。
- 实例：**Badain Jaran Sand Sea（巴丹吉林沙漠；Dong et al., 2022）**。

**sandsheets 与 zibars（幻灯片 48）：**

- **Aeolian sandsheet（风成沙席）**：*areas of sand accumulation that **lack significant development of high-relief dune-scale or larger bedforms**, but are instead characterised by **relatively flat areas of impact wind ripples***——缺乏高起伏的沙丘级或更大床型，代之以**相对平坦的冲击波痕面**。
- 沙席发育的控制：通常**净沉积收支为正**，但受到**砂的供给量不足和/或砂的可搬运性受限**的制约（Breed et al., 1987; Khalaf, 1989; Kocurek & Nielson, 1986）。
  - ⭐ 注意 **"supply（供给）"与"availability（可搬运性）"是两个不同的限制**：前者是"有没有砂"，后者是"砂能不能被吹动"（受湿度、胶结、砾石覆盖、植被控制）。这组区分在本周多处出现，是 Kocurek 学派的标志性表述。
- **Zibar（低平砂垄）**：低起伏的**垄与穹丘（low-relief ridges and domes）**，坡面**倾角 <10°、起伏不超过数米**（Nielson & Kocurek, 1986）。讲义注明其**又称 proto-dunes（原始沙丘/前驱沙丘）**。
- 实例：现代——Ténéré Desert（比例尺 5 km）；古代——**Upper Tulum Valley（阿根廷中西部；Dal' Bó & Basilici, 2015）**。
  - 📎 **背景补充**：zibar 的一个关键判别特征是**没有滑落面（no slipface）**，因此其内部**不含高角度交错层理，而以低角度风成波痕纹层为主**。这正是它与真正沙丘的沉积学分野。**材料未说明这一点**，但从"倾角 <10°、以冲击波痕为特征"可以直接推出。

### 2.6 床型迁移（幻灯片 27–28）

原文要点：

- **迁移中的波痕、沙丘与 draa，其组成物质就是"处于搬运状态"的沉积物**（*comprise the sediment that is in transport*）。⭐ 这句话概念上很重要：沙丘不是"沉积物"，而是"运输中的沉积物"——只有当它被埋藏到侵蚀基准面之下，才变成地层（呼应幻灯片 50–52）。
- 这些床型**体量大、移动慢**，但在**月、年或更长的时间尺度上可以移动可观的距离**。
- 床型常发育为**间距规则、重复出现的床型列（a train of regularly spaced and repeated bedforms）**，记录了**砂床对风的剪切作用的响应**；一列床型记录的是**在有波动但持续一致的流场型式下、趋向动力平衡（dynamic equilibrium）的一个阶段**（Jimenez et al., 1999）。
- 实例：**卡塔尔的新月形沙丘（barchan）迁移**（Engel et al., 2018）。

### 2.7 三类风成纹层：本周最核心的判别工具

⭐⭐ **这是全周最重要、最可能进考卷的一组概念。** 讲义用了 7 张幻灯片（30–36、39）逐一建立三类"小尺度相单元"，它们是**风成交错层组的内部填充物**。

#### (1) Wind-ripple / impact-ripple strata（风成波痕纹层）——幻灯片 30–33

**形态参数（原文数据，需记）：**

| 参数 | 数值 |
|---|---|
| 波长 | **50–200 mm** |
| 高度 | **5–10 mm，罕见可达 30 mm** |
| **波痕形态指数（ripple-form index = 波长/高度）** | **典型 12–50（高值）** |
| 背风面倾角 | **<20°，低于干松砂的休止角** |
| 脊线 | 平直或弯曲（部分呈蛇曲），**连续**，通常**横切于当地风向** |
| 剖面对称性 | **略不对称** |

其他原文要点：

- 风成波痕是**风成环境中分布最广的波痕类型**（Hunter, 1977a, b; 1981）。
- **起伏低**，且**优先由搬运中砂的较粗组分构成（form preferentially from the coarser-grained fraction of the sand in transport）**。
- **冲击波痕通过跃移（saltation）与反跳（reptation）的组合发育**。

**成因机制（幻灯片 31–32，务必掌握）：**

1. 床面上的**微扰动（表现为地表粗糙度）**影响跃移落地颗粒在床面上的排列方式，从而**触发波痕的起始发育**。
2. ⭐ **冲击波痕的间距由跃移路径长度（saltation path length）决定**；而跃移路径长度是**粒径、颗粒形状、密度，以及近床面平均风速与阵性（gustiness）**的函数。
3. 波痕有**面向上风的迎风坡（stoss slope）**，承受入射颗粒的撞击；以及**面向下风的背风坡（lee slope）**，那里发育**阴影区（shadow zone）**（Anderson, 1987）。
4. ⭐⭐ **粒度分选机制（考点核心）**：
   - **迎风坡**受**高角度撞击**，把**较粗颗粒以蠕移方式推向波痕脊部**；
   - **背风坡**是**阴影区**，只有少量**低角度撞击**发生，因此**较细颗粒得以在波痕槽部堆积**；
   - 随着波痕向下风迁移，这一分选机制产生**具反粒序（inverse grading）的纹层**——即**每一个纹层向上变粗**。

> ⭐ **"反粒序"是识别风成波痕纹层的黄金标志之一。** 直觉上很反常（水成沉积通常正粒序），但成因清楚：脊部粗、槽部细，波痕迁移时脊部的粗砂覆盖在前一位置槽部的细砂之上。

**在岩石记录中的四种表现（幻灯片 33，四张露头照片）：**

| 表现形式 | 描述 | 实例地层 |
|---|---|---|
| **Truncated ripple-foreset cross-laminae**（截切的波痕前积交错纹层） | 波痕前积面被保存但顶部被削截 | 侏罗系 **Navajo Sandstone**，犹他州 |
| **Subcritically climbing translatent strata**（亚临界爬升的平移纹层） | **看不到波痕前积交错纹层**，只见平行纹层 | 二叠系 **Cedar Mesa Sandstone**，犹他州 |
| **Pinstripe lamination（细条纹纹层）** | 波痕以**极低的亚临界角**相互爬升所形成的堆积。**每一条"细条纹"记录一列波痕中一个波痕的通过与堆积**：**略细的组分代表波痕槽部通过，略粗的组分代表波痕脊部通过** | **Twyfelfontein Formation**（原称 Etjo Sandstone），纳米比亚 |
| **低角度倾斜的层组下部翼上的风成波痕纹层包** | 出现在交错层理沙丘层组的**低角度下翼**上 | 侏罗系 **Navajo Sandstone**，犹他州 |

> ⭐ **pinstripe lamination（细条纹纹层）是风成沉积最著名的"指纹"之一**，成因就是上面那套"脊粗槽细"的分选加上极低角度爬升。讲义写得极其精确，值得逐句记。
> 📎 **背景补充：** "translatent strata（平移纹层）"是 Hunter (1977) 的术语，指波痕以低于临界角爬升时、只有波痕**底部**得以保存所形成的一套薄纹层；"subcritical（亚临界）"指爬升角小于波痕迎风坡倾角，因此迎风坡被后续波痕削蚀掉。**材料用了这个词但未定义。**

#### (2) Grainflow strata（颗粒流纹层）——幻灯片 34–35

**原文机制：**

> The **gravitational collapse of dry, loose sand** on aeolian dune and megadune **lee slopes inclined at the angle of repose (typically 32–36°)** generates **grainflow sand avalanches**.

- 成因：**干燥、松散砂在处于休止角（典型 32–36°）的沙丘/巨型沙丘背风坡上发生重力崩塌**，产生**颗粒流砂崩（grainflow sand avalanche）**。
- 运动：颗粒流**沿背风坡向下积累动量**，可以**溢出到倾角较低的床型基座（plinth）与翼部（flanks）**。
- ⭐ **产状数据（需记）**：颗粒流崩塌在交错层理前积层内部形成**倾角 18–36°** 的沉积单元；**古代地层中该倾角会因压实而降低**。

**在岩石记录中的表现（幻灯片 35 四例）：**

- A) 多期颗粒流砂崩沉积**厚层叠置**（Twyfelfontein Fm，纳米比亚）；
- B) 单个颗粒流层由**薄的颗粒降落纹层（grainfall laminae）分隔**（侏罗系 **Entrada Sandstone**，犹他州）；
- C) **内部无构造（internally structureless）**的颗粒流沉积与风成波痕平移纹层**互层**；
- D) C 的更大视野——二者在**交错层理沙丘层组的下部**的排列关系（二叠系 Cedar Mesa Sandstone）。

⭐ **"internally structureless（内部块状/无构造）"是颗粒流纹层的关键描述特征**：因为它是瞬时的重力崩塌，来不及形成内部纹层。此外，颗粒流单元在剖面上常呈**楔形/舌状（tongue）、向下坡尖灭**。

#### (3) Grainfall strata（颗粒降落纹层）——幻灯片 36

**原文机制：**

> **Gravity-driven grainfall** occurs commonly where the wind carries **clouds of saltating grains over a dune brink**. The **airflow decelerates** as it passes into the **lee-side depression** resulting in a **reduction in sediment carrying capacity**.

- 成因：风把**跃移颗粒云**带过**沙丘的丘顶转折点（brink）**，气流进入**背风侧的低压/减速区**后**减速**，**载沙能力下降**，颗粒在重力作用下降落。
- 实例：**Namib Desert 的现代沙丘**。
- **第二种发生位置**：颗粒降落**也可发生于沙丘的翼部或裙裾（apron）**，条件是那里的**次生横向气流（secondary cross-wind airflow）不足以形成波痕**。实例：**Gran Desierto 西北部（墨西哥）一条星状 draa 的臂部**（Brookfield & Silvestro, 2010）。
- 古代实例：颗粒降落纹层**不间断地向下延伸到背风坡坡脚，并披覆（blanketing）在颗粒流纹层之上**（侏罗系 **Page Sandstone**，亚利桑那州）。
  - ⭐ 该照片的图注还给出了**界面的两种标注**：**白线 = set-bounding surfaces（层组界面）**；**粉线 = reactivation surface（再作用面）**，其定义为——*records a **period of lee-face erosion** bounded by packages representing lee-face deposition*，即**记录一段背风面侵蚀期，其上下都是代表背风面沉积的沉积包**。
- 细节：**单个颗粒流单元之间由薄的、席状（tabular）的颗粒降落纹层分隔**（Cardenas et al., 2019）。

#### (4) 三类纹层在沙丘上的空间分布（幻灯片 37、39）

幻灯片 37 是一张纯图页（其文字为 OCR 识别，识别质量差），但可辨认出的标注恰好就是本节最重要的空间关系：

```
wind direction & direction of migration（风向 = 迁移方向）
grainfall blanketing lee slope（颗粒降落披覆背风坡）
grainflow tongues（颗粒流舌状体）
Bottomset — wind-ripple dominated（底积层——风成波痕主导）
```

幻灯片 39 的图注把这套关系说得更完整：

- **顶部照片**：混合的颗粒流与颗粒降落纹层组成的**舌状体（tongues）**，与风成波痕纹层**互层并向其尖灭（pinching out）**，位置在**交错层理沙丘层组的坡脚（toe）**（二叠系 **lower Cutler beds**，犹他州）。
- **底部照片**：界限清晰的**颗粒流舌状体**与风成波痕纹层互层并尖灭，同样在层组坡脚（Cedar Mesa Sandstone）。
- **示意块状图**：交错层理由沙丘迁移与堆积形成，其**前积层内部有三种不同类型的小尺度构造**：**简单锥形的颗粒流纹层、颗粒降落纹层、爬升波痕纹层**。

⭐ **总结成一句话（本周最该背下来的一条）：**
> **在一个风成沙丘的背风面上，颗粒流集中在中—上部并向下尖灭为舌状体，颗粒降落披覆整个背风坡（常在颗粒流之上、也可延伸到坡脚），风成波痕纹层主导坡脚（底积层 bottomset）与低角度的翼部/基座。**

📎 **背景补充（一条常见但材料未写的补充判据）**：沙丘的**迎风坡（stoss slope）**在迁移过程中通常被后续床型削蚀掉，因此**迎风坡的沉积极少被保存**；这也是为什么风成交错层理的保存部分**以背风坡沉积为主**、并且几乎总是显示**单一方向的高角度前积**。**材料未直接说明这一点**，但幻灯片 43 的"截切"机制隐含了它。

### 2.8 从床型到地层：爬升、层组与界面（幻灯片 40、42、43）

⭐ **这是本周第三问的正面回答，也是"过程 → 产物"转换的关键一步。**

**核心条件（幻灯片 42）：**

> In situations where the **net aeolian sediment budget is positive**, accumulation occurs such that bedforms may **climb over one another at various angles**, thereby accumulating **sets and cosets of cross strata, and associated bounding surfaces**.

即：**只有当净风成沉积收支为正（positive net sediment budget）**，床型才会**以各种角度相互爬升**，从而堆积出**交错层理的层组（sets）与层组套（cosets）以及相应的界面（bounding surfaces）**（Brookfield, 1977; Rubin & Hunter, 1982; Rubin, 1987a）。

- 这些 set 与 coset 的**内部**由更小尺度的相单元组成：**风成波痕、颗粒流、颗粒降落与平行层理（plane-bedded）纹层**；
- **各类纹层的相对比例与分布，由过程如何作用于形成床型来决定**（*determined by how processes operated upon the formative bedforms*）；
- 因此：**沙丘单元（dune elements）是由多种更小尺度沉积体以不同方式排列组合而成的、更大尺度的层单元。**

**层组与界面的产生机制（幻灯片 43，逐句拆解）：**

1. 床型相互迁移时，通常作为**床型列（bedform train）**的一部分，**以低角度爬升**，使得**第一个床型最下部的交错层理沉积**在**第二个床型越过它时**得以堆积保存。
2. **第一个床型形成的交错层被第二个床型的通过部分削截（partly truncated）。**
3. ⭐ **这个削截（cut-off）的高度，就生成了一个顶部以侵蚀面为界的交错层组（set）——这个面就叫界面（bounding surface）**（Brookfield, 1977; Rubin & Hunter, 1982）。

**交错层组的两种理想剖面（平行流向切面，幻灯片 43 图注）：**

| 类型 | 前积层几何 | 常见程度 | 成因 | 特殊价值 |
|---|---|---|---|---|
| **A** | **平面状前积层 + 角状底（planar foresets with angular bases）** | **常见（common）** | 可由**小型横向沙丘（small transverse aeolian dunes）**迁移形成 | — |
| **B** | **弯曲前积层 + 渐近/切线状底（curved foresets with asymptotic or tangential bases）** | **非常常见（very common）** | 可由**各种类型的大小风成沙丘**迁移形成 | ⭐ **是有用的顶底判别标志（way-up indicator）** |

> ⭐ **B 型可作顶底判据**的原因：前积层**向下变缓、渐近地并入底界面**，而**向上则以角度截切于顶界面**。因此"缓的一端朝下、切的一端朝上"。这在倒转地层中非常有用，是本页唯一被讲义单独点出的应用。

**干型风成序列中的床型爬升（幻灯片 40，实例：侏罗系 Navajo Sandstone，犹他州）**，讲义列出的三条露头特征：

- **Low-angle-inclined bounding surfaces**（低角度倾斜的界面）
- **Climbing cross-bedded sets**（爬升的交错层组）
- **Large scale cross-bedding**（大型交错层理）

**界面的类型（讲义提及的三种）：**

| 界面 | 讲义中的位置 | 定义（原文/图注） |
|---|---|---|
| **Set-bounding surface（层组界面）** | 幻灯片 36 图注（白线）、43 | 由后一床型削截前一床型的交错层所产生的侵蚀面，构成 set 的顶界 |
| **Reactivation surface（再作用面）** | 幻灯片 36 图注（粉线） | **记录一段背风面侵蚀期（a period of lee-face erosion）**，其上下为代表背风面沉积的沉积包 |
| **Superimposition surface（叠加面）** | 幻灯片 38 | 由**较小的横向沙丘沿一个较大巨型沙丘的翼部迁移**所产生的界面（纳米比亚砂海 3D GPR 成像） |

> ⚠️ **本讲义没有讲 Brookfield（1977）的一级/二级/三级界面等级体系（first-/second-/third-order bounding surfaces），也没有出现 "super surface（超级面）" 或 "interdune migration surface" 这两个术语。** 不要凭印象把它们当作本周内容。

> 📎 **背景补充（等级体系，材料完全未涉及，仅供理解上表三种面的层级关系）：** Brookfield (1977) 把风成界面分为三级：
> - **1st-order（一级面）**：近水平、横向延伸最广，代表**巨型沙丘（draa）的迁移**，时间尺度最长（10³–10⁵ yr）；常对应 **interdune migration surface（沙丘间迁移面）**。
> - **2nd-order（二级面）**：中等倾角，代表**叠加在 draa 上的沙丘级床型的迁移**，即上表的 **superimposition surface**。
> - **3rd-order（三级面）**：set 内部的小型面，代表**背风面上局部的侵蚀—再沉积**，即上表的 **reactivation surface**，时间尺度最短（季节性风向变化即可产生）。
> 此外 **super surface（超级面；Kocurek, 1988）** 是更高一级的、区域性的风成体系顶界，常代表整个砂海的停止发育与吹蚀（对应幻灯片 50 讲的"整个 erg 被吹蚀掉"）。
> **以上等级划分与时间尺度全部是补充内容，本讲义未给出，答题时若引用请注意区分。**

### 2.9 沙丘间（interdunes）与黏附构造（幻灯片 44–46）

**定义（幻灯片 44 原文）：**

> Aeolian interdunes are **elongated, relatively flat, and sandy landforms** that exist **between larger sand dunes** in desert and arid environments. They typically form in the **low-lying areas between dune crests**.

⭐⭐ **三分法（按潜水面 water table 与沉积面 depositional surface 的关系，Mountney & Russell, 2004）——高频考点：**

| 类型 | 潜水面位置（原文） | 伴生沉积构造 |
|---|---|---|
| **Dry interdune（干沙丘间）** | **water table is NOT in contact with the depositional surface**（潜水面不与沉积面接触） | **风成波痕纹层（wind-ripple strata）** |
| **Damp interdune（湿润沙丘间）** | **capillary fringes of the water table are in contact with depositional surface**（潜水面的**毛细边缘带**与沉积面接触） | **黏附构造（adhesion strata）** |
| **Wet interdune（含水沙丘间）** | **water table IS in contact with the depositional surface**（潜水面直接与沉积面接触） | **水下波痕（subaqueous ripples）** |

> 讲义把后两者合并表述为：*Wet interdunes & damp interdunes are associated with **subaqueous ripples and adhesion strata***；*Dry interdunes associated with **wind-ripple strata***。

实例（幻灯片 44）：
- **湿型风成体系**：**Askja, NE Iceland（现代）**，比例尺 6 m；
- **干型风成体系**：**Navajo Sandstone, SE Utah（侏罗纪）**。

**沙丘间的建筑要素（architectural elements，幻灯片 45）：**
- A) 湿润与含水沙丘间建筑要素的**典型三维几何形态与内部结构**总结模型（Cain, 2009）；
- B) 实例照片：**水平层理的含水沙丘间要素（红色）夹在交错层理的风成沙丘要素（灰白色）之间**（Navajo Sandstone, SE Utah）。
  - ⭐ 这张图是**风成地层非均质性**的直观体现：**高角度交错层的沙丘体（渗透好） + 水平层理的沙丘间层（渗透差）** 相间叠置。📎 储层意义为补充内容。

**黏附构造（adhesion strata，幻灯片 46）：**

- 成因（Hummel & Kocurek, 1984）：**运动中的颗粒黏附在潮湿表面（damp surface）上**，例如湿润沙丘间的表面。
- 形态：**起伏低（高度数毫米）**，呈**近水平、表面不规则**的构造。
- 三种细分（原文）：
  - **Adhesion plane beds（黏附平行层）**
  - **Adhesion ripples（黏附波痕）**（Kocurek & Fielder, 1982）
  - **Adhesion warts（黏附瘤）**（Olsen et al., 1989）
- 实例：**干砂被吹过湿砂表面时形成的黏附瘤**（Indian Creek, Utah）；**元古界 Independence Fjord Group（北格陵兰）的黏附瘤**（Collinson & Mountney, 2019）。

⭐ **黏附构造的判别意义极强**：它**同时要求"有干砂在风中运动"和"有潮湿的地表"**，因此是**风成体系中潜水面接近地表**的直接证据，也是把体系定为 damp/wet 型的关键岩石学依据。

### 2.10 堆积 ≠ 保存：风成地层的保存条件（幻灯片 50、52）

⭐⭐ **这是本周（也是全课）在概念上最深刻的一段，务必吃透。**

**问题的提出（幻灯片 50 原文）：**

> The **accumulation** of aeolian sequences **does not automatically ensure their long-term preservation**. Indeed, evidence from the Quaternary record (Kocurek et al., 1991a; Kocurek, 1999) argues that **entire ergs may be constructed and accumulated to considerable thicknesses, only to be later deflated to leave no record.**

即：**整个砂海可以建造并堆积到相当厚度，之后却被彻底吹蚀掉、不留下任何记录。**

**保存的必要条件：**

> Long-term preservation requires that the body of strata is **placed below a regional baseline, beneath which erosion does not occur.**

必须把沉积体**置于一个区域性基准面（regional baseline）之下**，在该面之下不发生侵蚀。

因此：

> **The rate of generation of accommodation and the rate at which aeolian accumulations fill that space is a fundamental control on preserved architectural style**（Havholm & Kocurek, 1993; Howell & Mountney, 1997; Mountney & Howell, 2000; Cosgrove et al., 2021c）。

**可容空间（accommodation）的生成速率**与**风成堆积填充该空间的速率**之比，是**保存下来的建筑样式（architectural style）**的根本控制因素。

**两种保存机制（幻灯片 52，原文）：**

> The **principal agent that generates accommodation and promotes preservation is subsidence（沉降）**.

1. **机制一——沉降到侵蚀基准面之下**：堆积发生在一个**正在沉降的盆地**中，可容空间可供填充，沉积体因而被置于所谓的 **baseline of erosion（侵蚀基准面）**之下——该面被定义为**由空气动力学构型所决定的、吹蚀能够下切到的最深水平**（Kocurek & Havholm, 1993）。
2. **机制二——被置于潜水面之下**：堆积体被置于**潜水面（water table）之下**，从而**免受后期吹蚀**。实现途径有两条：
   - **通过沉降穿过一个静止的潜水面**；
   - 或在**较短的地质时间尺度上，通过潜水面的绝对上升（absolute rise in water-table level）**。

> ⭐ **机制二直接解释了幻灯片 16 中的"wet aeolian system"为什么保存潜力高**：湿型体系的定义就是"堆积受持续的潜水面上升控制"，而潜水面上升同时也是保存机制。**干型体系则完全依赖构造沉降**，保存条件更苛刻。这一条把"体系分类"与"保存潜力"串成了因果链，是本周最漂亮的推理。
>
> 📎 **背景补充：** 上面这套"accommodation vs sediment supply（A/S）"的思路，与 W01–W02 层序地层学方法、以及碳酸盐板块（W06）里的"追赶/齐平/放弃"是同一套框架在不同介质中的表达。**这一跨周类比是笔记的整合，讲义未点明。**

### 2.11 讲义自带的总结（幻灯片 53）

讲义最后一页给出的七条 take-home message（原文要点，可直接当复习提纲）：

1. 风成过程在多种**侵蚀性与沉积性**环境中运作：热带与寒带气候沙漠、海岸带、河流与冰川外冲平原、火山区，甚至向深海供沙。
2. 尽管风成过程在各类气候带均有运作，**当前最活跃、最广布的是干旱的热带与寒带沙漠**。
3. 风成沉积产出于多种尺度，由小到大为**波痕级—沙丘级—巨型沙丘级**。
4. 最小尺度上的沉积构造：**风成波痕、颗粒流、颗粒降落与黏附纹层**（wind-ripple, grainflow, grainfall and adhesion strata）。
5. 风成沙丘与**沙丘间（干、湿润、含水）、沙席、zibar** 共生。
6. **风成沙丘与沙丘间通过相互爬升而堆积**（accumulate by climbing over one another）。
7. **上覆床型削截下伏床型，在地质记录中留下交错层组（cross-bedded sets）。**

> ⭐ 注意第 4 条：讲义在总结页把**黏附纹层**也并入了"最小尺度构造"的名单，即最终的四分是 **wind-ripple / grainflow / grainfall / adhesion**。前三者是沙丘（背风坡）体系的，第四者是沙丘间（湿润面）体系的。

---

## 三、公式与图表

> **说明：本讲义通篇没有给出任何定量公式**（既无跃移临界起动风速公式，也无沙丘迁移速率公式）。本节先把讲义中的关键图件用文字复原到"能自己重画"的程度，最后再以 📎 形式补充几条常见的定量关系。

### 图 1｜颗粒受力平衡图（幻灯片 5，Mountney et al., 2023）

**怎么画：**
1. 画一条水平床面，上面放一个圆形颗粒（代表待启动的砂粒）。
2. 从颗粒中心向**正上方**画箭头 → 标 **L（lift，空气动力上举力）**。
3. 从颗粒中心向**正下方**画箭头 → 标 **W（weight，重力）**。
4. 从颗粒中心向**下风向水平方向**画箭头 → 标 **D（aerodynamic drag，空气动力拖曳力）**。
5. 在颗粒与相邻颗粒的接触点画短箭头指向接触点 → 标 **C（cohesion，颗粒间黏聚力）**，代表把颗粒"粘住"的力（含水膜、胶结、静电）。
6. 从**左上方斜向下**画一条带小颗粒的弹道轨迹撞到目标颗粒 → 标 **I（impact，弹道撞击）**。
7. 在图上把箭头分成两组标注：**驱动组 = L + I（+ D）**；**阻力组 = W + C + friction**。

**这张图要回答的问题**：**风力何时能克服地表稳定化效应？** 左侧（气流侧）的变量是风速与湍流；右侧（颗粒侧）的变量是粒径、密度、形状、堆积、含水量、矿物、胶结度。

### 图 2｜搬运方式—粒度对应图（幻灯片 6，Modified after Pye, 1987）

**怎么画：**
- 一条水平的床面，其上按高度分三层画三种运动轨迹：
  - **最高、贯穿画面的水平细箭头流** = **suspension（悬移）**，标注粒度 **silt & clay（粉砂与黏土）**；
  - **中间的一串抛物线弹跳轨迹** = **saltation（跃移）**，标注粒度 **sand（砂）**，注明"落地后引发碰撞连锁反应"；
  - **贴床面的滚动小球** = **creep / reptation（蠕移/反跳）**，标注**较粗砂**；
  - **床面上不动的大颗粒**（画成有棱角的砾石铺成一层）= **deflation lag（吹蚀滞留）= reg / serir**，标注 **gravel and coarser（砾级及更粗）**。
- 在右侧配一张**戈壁砾漠照片**（讲义用的是 Mojave Desert 的 reg）。

**要点**：这张图是本周**粒度—过程—产物**三者对应的总纲。上下三层与三种最终产物一一对应：悬移 → **黄土/远洋粉尘**；跃移+蠕移 → **沙丘与沙席**；不动 → **reg / serir**。

### 图 3｜风成床型的三级尺度图（幻灯片 25/29/41，Modified after Wilson, 1972）

⭐ **讲义重复三次，最重要的图之一。**

**怎么画：**
- **双对数坐标**。
- **横轴（或纵轴之一）：Wavelength（波长）**，跨度从约 **0.05 m 到 5000 m**。
- **另一轴：Grainsize（粒度）**，且讲义明确指定用的是**最粗二十分位数（coarsest twenty-percentile）**——即粒度分布中最粗的 20% 那一档的代表值，而不是中值粒径。
- 在图上画**三个彼此分离的数据云（field）**，沿一条大致正相关的趋势由小到大排列：
  1. **Ripples（波痕）**：波长约 **0.05–0.2 m**（即 50–200 mm，与幻灯片 30 的数据一致）；
  2. **Dunes（沙丘）**：波长约**十米至数百米**；
  3. **Megadunes / draas（巨型沙丘）**：波长 **500–5000 m**，高度 >50 m（幻灯片 47 数据）。
- ⭐ 三个云之间**留有空白间隙**——但必须在图旁写上讲义的限定语：**"介于三个域之间尺度的床型确实在地球上存在，只是较少见。"**

**这张图要回答的问题**：为什么风成床型是**离散的三级层级**而不是连续谱？（讲义的答案是它们构成一个 **hierarchy of equilibrium bedforms**，各自与不同尺度的气流结构达成动力平衡。）

### 图 4｜沙丘类型判别图：EST vs RDP/DP（幻灯片 15，Modified after Wasson & Hyde, 1983）

⭐ **本周唯一的"分类图"，也是任务清单点名的重点图。**

**讲义给出的信息（可靠部分）——图注原文：**
> Discrimination of dune types in relation to a plot of **Equivalent Sand Thickness (EST)** versus **Resultant Drift Potential (RDP) / Drift Potential (DP)**.

因此两条坐标轴是确定的：

- **纵轴：EST（Equivalent Sand Thickness，等效砂层厚度）**——把该区域全部风成砂摊平后的厚度，是 **砂的供给量/可用量** 的度量。EST 大 = 砂多。
- **横轴：RDP/DP（Resultant Drift Potential / Drift Potential，合成漂移势 / 漂移势之比）**——**风向变率（directional variability）** 的度量。
  - **DP** = 全部方向上的输沙潜力总和；
  - **RDP** = 各方向矢量合成后的净输沙潜力；
  - 因此 **RDP/DP → 1** 表示风**高度单向**（各方向不抵消）；**RDP/DP → 0** 表示风向**多向、彼此抵消**。

> ⚠️ **幻灯片 13、14 两页标题为 "Dune Types"，但转换后的 md 中只剩标题和 "Image: Mountney et al., 2023"，正文文字为零**——即**沙丘形态类型的清单（新月形、横向、线性、星状等）在本讲义的可提取文本中并不存在**。因此以下沙丘类型与图上分区的对应关系**全部是背景补充，不是讲义原文**。

> 📎 **背景补充（Wasson & Hyde, 1983 图上各区的标准分布，材料未给文字，请谨慎引用）：**
>
> ```
>   EST
>  （砂供给量）
>   高 ┤   Star dunes（星状沙丘）      Transverse / barchanoid ridges
>     │   多向风 + 砂多                （横向沙丘 / 新月形沙丘链）
>     │                                 单向风 + 砂多
>     │
>     │   Linear dunes（线性/塞夫沙丘）  Barchan dunes（新月形沙丘）
>   低 ┤   双峰或斜交风 + 砂少           单向风 + 砂少（孤立、可移动）
>     └──────────────────────────────────────────────►
>       低 RDP/DP（风向多变）      高 RDP/DP（风向单一）
> ```
>
> 记忆口诀（📎）：
> - **横轴管"风向单不单一"**：单一 → **新月形/横向（crescentic）**；多向 → **星状（star）**；居中/双峰 → **线性（linear / seif）**。
> - **纵轴管"砂多不多"**：砂少 → **孤立的 barchan（可见基底）**；砂多 → **连续的 barchanoid ridge / transverse ridge 或 star draa**。
> - 因此：**barchan 与 transverse 的区别主要是砂量（EST），barchan 与 star 的区别主要是风向变率（RDP/DP）。**
>
> **上述分区与口诀均为补充，本讲义正文未涉及。** 讲义中唯一以文字出现的具体沙丘类型是 **barchan**（幻灯片 20 火星影像、28 卡塔尔实例、30–31 阿富汗照片）与 **transverse dune**（幻灯片 38、43）；**star draa** 在幻灯片 36 图注中以 "arm of a star draa" 一带而过。

### 图 5｜冲击波痕的成因与分选机制（幻灯片 31–32，Modified after Anderson, 1987）

⭐ **本周机理性最强的一张图，务必能自己画出来。**

**怎么画：**
1. 画一列不对称的低矮波痕，波长标 **50–200 mm**，高度标 **5–10 mm**（比例上极扁，形态指数 12–50）。
2. 标出风向（左 → 右）。
3. 每个波痕的**左侧（迎风侧）= stoss slope（迎风坡）**，右侧（背风侧）= **lee slope（背风坡）**，背风坡倾角标 **<20°**（**低于休止角**，这是与水成波痕的重要差别）。
4. 从左上方画多条**斜向下的跃移弹道轨迹**，**高角度**撞击在迎风坡上；在背风坡后方画一个阴影区域，标 **shadow zone（阴影区）**，其中只画极少数**低角度**的入射轨迹。
5. 在迎风坡上画粗颗粒沿坡向上被"推"向脊部的小箭头，标 **creep of coarser grains towards crest**。
6. 在波痕槽部画细颗粒堆积，标 **finer grains accumulate in troughs**。
7. 在图的下方画出结果：随着波痕向下风迁移，**产生具反粒序（inverse grading）的纹层**——每个纹层底部细、顶部粗。
8. 在图旁标注：**波痕间距 ≈ 跃移路径长度（saltation path length）**，而后者由**粒径、形状、密度、近床面平均风速与阵性**决定。

### 图 6｜沙丘背风坡上三类纹层的空间分布（幻灯片 37、39）

⭐⭐ **本周最该画在脑子里的一张图。**

**怎么画（平行风向的剖面）：**
1. 画一个**不对称的沙丘剖面**：左侧长而缓的**迎风坡（stoss）**，顶部一个转折点标 **brink（丘顶转折）**，右侧是短而陡的**背风坡（lee slope）**，倾角标 **32–36°（角度即休止角）**。
2. 风向箭头由左向右，并标 **wind direction & direction of migration（风向 = 迁移方向）**。
3. 在**迎风坡**上画一串小波痕，标 **wind ripples**（迎风坡以波痕搬运为主）。
4. 在**丘顶转折点之后**画一团被带过顶的跃移颗粒云，向背风侧散开落下 → 标 **grainfall blanketing lee slope（颗粒降落披覆背风坡）**；说明气流在背风侧凹地中**减速 → 载沙能力下降**。
5. 在**背风坡中上部**画数条**楔形/舌状的崩塌体**，从坡上部向下延伸并**逐渐变薄、尖灭**（pinch out）→ 标 **grainflow tongues（颗粒流舌状体）**；注明其内部**无构造（structureless）**、倾角 **18–36°**。
6. 在**背风坡坡脚（toe）** 画一套**低角度、近水平的薄纹层**，标 **bottomset — wind-ripple dominated（底积层，风成波痕主导）**；画出上面的颗粒流舌状体**插入并尖灭进**这套波痕纹层之中。
7. 在**沙丘两翼与基座（plinth / flanks）** 上也标 **wind-ripple strata**（讲义幻灯片 33 的第四张照片正是"层组低角度下翼上的风成波痕纹层包"）。
8. 补一条：**若翼部的次生横向气流弱到不足以形成波痕，则那里也会出现 grainfall**（幻灯片 36，星状 draa 臂部的例子）。

**一句话记忆**：**顶上降落、坡上崩流、脚下波痕。**

### 图 7｜床型爬升产生层组与界面（幻灯片 42–43）

**怎么画：**
1. 画两个（或三个）同向迁移的沙丘剖面，前后错开，**后一个比前一个略高一点**——这就是"**以某个爬升角（angle of climb）向上爬升**"。
2. 在第一个沙丘的背风坡上画出高角度前积层（foresets）。
3. 画出第二个沙丘越过第一个沙丘时，**削去第一个沙丘上部的前积层**——把削掉的部分用虚线保留、实线部分保留。
4. 那条削截线（cut-off surface）就是 **bounding surface（界面）**；它与下伏保存下来的一叠前积层共同构成一个 **set（层组）**。
5. 重复三四次，得到一叠**被低角度界面分隔的交错层组 = coset（层组套）**。
6. 标注幻灯片 40 的三条露头特征：**low-angle-inclined bounding surfaces / climbing cross-bedded sets / large scale cross-bedding**。

**两种理想 set 剖面（同一页图注的 A、B）：**

```
A. 平面前积 + 角状底（common）             B. 弯曲前积 + 渐近/切线底（very common）
 ── 顶界（削截）──                          ── 顶界（削截）──
 ＼＼＼＼＼＼＼＼                            ＼ ＼  ＼   ＼
 ＼＼＼＼＼＼＼＼                             ＼  ＼   ＼    ＼＿
 ────角状相交────                           ──渐近并入底界──
                                            ⭐ way-up indicator（顶底判别标志）
```

**爬升角的意义（📎，讲义只说"以各种角度爬升"，未展开）：**
> 📎 **背景补充：** 爬升角（angle of climb）越大，被保存的床型比例越高——爬升角为零时床型只是**平移（bypass）**，不留下任何堆积；爬升角越大，越多的沙丘下部（甚至迎风坡）得以保存。爬升角本质上等于**净沉积速率 ÷ 床型迁移速率**。**这一定量关系材料未给出。**

### 图 8｜沙丘间建筑要素模型（幻灯片 44–45）

**怎么画（三维块状图）：**
1. 画两个相邻的交错层理沙丘体（浅色，内部为高角度前积层）。
2. 在两者之间夹一层**水平层理的、席状的层**（讲义实例照片中用**红色**标出这一层，沙丘体为灰白色）→ 这就是 **interdune element（沙丘间要素）**。
3. 按潜水面位置在剖面右侧画三条水平虚线，分别标注：
   - 潜水面**远低于**沉积面 → **dry interdune** → 内部填充 **wind-ripple strata**；
   - 潜水面的**毛细边缘带**触及沉积面 → **damp interdune** → 内部填充 **adhesion strata**（黏附平行层、黏附波痕、黏附瘤）；
   - 潜水面**与沉积面相接**（地表有水） → **wet interdune** → 内部填充 **subaqueous ripples（水下波痕）**，可有薄的湖相/盐湖沉积。
4. 标注比例尺：讲义 Askja（冰岛）现代实例的比例尺是 **6 m**。

### 图 9｜理想的风成垂向柱状剖面

> 📎 **本图为背景补充。讲义没有给出任何理想垂向柱状图**——这是本讲义与 W07–W09 三周（浅海、陆相、深水通常都会给经典相模式柱状图）在编排上的一个显著差别。以下柱状图由笔记依据讲义各页信息组装，仅供把零散要素串起来，**答题时不应当作讲义内容引用**。
>
> ```
> 顶  ┬────────────────────  super surface / 区域吹蚀面（若发育）
>     │ ▨▨▨ 交错层理沙丘组   ← 高角度前积（18–36°）
>     │   · 上部：grainflow（块状、舌状、向下尖灭）
>     │   · 全坡：grainfall（薄、席状、披覆）
>     │   · 底积：wind-ripple / pinstripe（低角度、反粒序）
>     ├────────────────────  set-bounding surface（低角度削截面）
>     │ ═══ 沙丘间层：水平层理
>     │   干型 → wind-ripple strata
>     │   湿润 → adhesion strata（黏附瘤/波痕/平行层）
>     │   含水 → 水下波痕、薄层泥/蒸发岩
>     ├────────────────────  set-bounding surface
>     │ ▨▨▨ 下一个交错层理沙丘组 …（重复叠置 = coset）
> 底  ┴────────────────────
> ```
>
> **读这套柱状图的方式**：**沙丘层与沙丘间层的厚度比、以及沙丘间层的类型（干/湿润/含水）**，就是判定体系类型与潜水面演化史的直接证据。若向上沙丘间层由干型变为含水型，说明**潜水面相对上升** → 指示 **wet system** 与更高的保存潜力（呼应 2.10）。

### 关于公式

**讲义中没有任何公式。** 以下三条为补充。

> 📎 **背景补充（材料完全未涉及，仅供理解）：**
>
> **(1) 起动风速（Bagnold, 1941 的阈值摩阻速度）**
> $$u_{*t} = A\sqrt{\frac{(\rho_s-\rho_a)\,g\,d}{\rho_a}}$$
> - $u_{*t}$：临界摩阻速度（threshold shear velocity）；
> - $A$：经验系数（流体阈值 fluid threshold 约 0.1；撞击阈值 impact threshold 约 0.08，**更低**——这解释了为什么一旦跃移启动、即使风速回落也能维持，即"跃移的自持性"）；
> - $\rho_s$、$\rho_a$：颗粒与空气密度；$g$：重力加速度；$d$：粒径。
> - ⭐ 该式预测**起动风速随 $\sqrt{d}$ 增大**，因此**最容易被吹动的不是最细的颗粒**——极细的粉砂/黏土因**黏聚力（C）**大反而更难启动，这与讲义幻灯片 5 把 cohesion 列为阻力项完全一致。
>
> **(2) 输沙率（Bagnold 输沙公式）**
> $$q \propto u_*^3$$
> 输沙率与摩阻速度的**三次方**成正比 —— 因此**少数几场大风事件就可以主导长期输沙总量**。
>
> **(3) 沙丘迁移速率**
> $$c = \frac{q}{\rho_b\,H}$$
> - $c$：迁移速率；$q$：单宽输沙率；$\rho_b$：床体堆积密度；$H$：沙丘高度。
> - ⭐ 迁移速率**反比于沙丘高度** —— 这正是讲义幻灯片 27 所说"床型可能体量大而移动慢"的定量表达，也解释了为什么小型 barchan 每年可移动数十米、而 draa 几乎不动。

---

## 四、课堂补充

> ⚠️ **本课程全 10 周均无 transcript（课堂录音转写）。** 因此本段**不包含任何课堂口述内容**，全部来自**讲义本身**：重复出现的页面、图注中透露的强调点、案例地层的选择偏好，以及讲义在措辞上刻意加的限定语。

### 4.1 讲义结构本身透露的重点

- **"三问路线图"页出现了 4 次**（幻灯片 2、3、24、49）。这是最强的结构信号：**答题时把答案组织成"过程与场所 / 床型发育 / 堆积与保存"三段，就是讲者的思路。**
- **床型三级尺度图（Wilson, 1972）出现了 3 次**（幻灯片 25、29、41），每次都作为"回到主线"的锚点。**ripple–dune–draa 的层级是本周的组织骨架**，讲义分别在其后展开波痕（30–33）、沙丘（34–46）、巨型沙丘（47–48）。
- 幻灯片 2 与 3 内容完全相同、25/29/41 内容完全相同——这是讲者用同一页作为**章节分隔符**的习惯，不是转换重复。

### 4.2 讲义反复强调的限定语（"防绝对化"信号）

讲者在多处刻意加了限定，这些地方往往就是考试想考"你有没有想当然"的位置：

1. **"风成 ≠ 沙漠"**：幻灯片 9 明确列出海岸、冰川外冲平原、火山区、深海；幻灯片 19 专门讲**湿润气候下的风成过程**（冰前区）。总结页（53）第一条又重申一次。
2. **"床型尺度之间有过渡型"**：三级尺度图的图注每次都写 *bedforms developed at scales between the three fields do occur on Earth, but are less common*。
3. **"堆积不等于保存"**：幻灯片 50 用整页讲"整个 erg 可能被吹光"。这是全周最反直觉的一条。
4. **"沙席受限于 supply 和/或 availability"**（幻灯片 48）——两个词并列，不是同义反复。
5. **"古代地层的颗粒流倾角因压实而降低"**（幻灯片 34）——测量古代交错层倾角时不能直接与现代休止角比较。

### 4.3 案例地层的选择透露的重点

讲义的露头照片高度集中在**少数几套地层**上，这些名字反复出现，几乎肯定是要求认识的：

| 地层 | 时代 / 地点 | 在讲义中出现的位置 |
|---|---|---|
| **Navajo Sandstone** | 侏罗系，犹他州 | 幻灯片 32（爬升波痕）、33（截切波痕前积、低角度翼部波痕包）、40（床型爬升）、43（交错层沙丘组）、44（干型体系代表）、45（含水沙丘间夹层）、53（总结页） |
| **Cedar Mesa Sandstone** | 二叠系，犹他州 | 幻灯片 33（亚临界爬升平移纹层）、35（颗粒流与波痕互层）、39（颗粒流舌状体尖灭） |
| **Twyfelfontein Fm（原 Etjo Sandstone）** | 纳米比亚 | 幻灯片 33（pinstripe 纹层）、35（叠置颗粒流） |
| **Entrada Sandstone** | 侏罗系，犹他州 | 幻灯片 35（颗粒流被颗粒降落纹层分隔） |
| **Page Sandstone** | 侏罗系，亚利桑那州 | 幻灯片 36（颗粒降落披覆 + 再作用面标注） |
| **lower Cutler beds** | 二叠系，犹他州 | 幻灯片 39（混合颗粒流/降落舌状体） |
| **Independence Fjord Group** | 元古界，北格陵兰 | 幻灯片 46（黏附瘤） |

⭐ **注意这份名单的构成：科罗拉多高原的中生界—上古生界风成砂岩占了压倒性多数。** 这既反映了这些露头的经典地位，也直接呼应第一节讲的**下游联系**（📎）：这批地层正是北美与北海风成储层最重要的露头类比体。

**现代实例名单**同样值得记：**Rub' al Khali（阿曼/沙特）、Ténéré（尼日尔）、Namib（纳米比亚）、Badain Jaran（中国）、White Sands（新墨西哥）、Askja（冰岛）、Gran Desierto（墨西哥）、Qatar 的 barchan、Mojave 的 reg、中国黄土高原**。

### 4.4 方法学上的一条"隐藏彩蛋"：探地雷达（GPR）

幻灯片 38 是全周唯一一页讲**观测方法**的：

- **过去的做法（McKee, 1966）**：*"The old days… trenching through dune sands with **weak gypsum cement** using unusual sedimentological field equipment, White Sands, New Mexico."* —— 直接在沙丘上**开挖探槽**。White Sands 的砂是石膏质的、有弱胶结，才挖得动。
- **现在的做法（Bristow & Mountney, 2012）**：**探地雷达（GPR）**——
  - **3D GPR** 成像了**较小的横向沙丘沿一个较大巨型沙丘翼部迁移所形成的叠加面（superimposition surfaces）**（纳米比亚砂海）；
  - **2D GPR 剖面**成像了摩洛哥的一个**新月形沙丘（barchan）**内部。

⭐ **这一页的意义**：它是"现代过程 → 岩石记录"这条转换链上**唯一能直接看到现代沙丘内部结构**的手段。GPR 剖面上的反射面，可以与露头上的界面（bounding surfaces）直接对比，从而**验证** Brookfield / Rubin & Hunter 那套基于露头推断出来的界面成因模型。这是本周方法论上最值得写进论述题的一笔。

### 4.5 讲义中的材料缺口（复习时需自行补的地方）

诚实列出本讲义**没有覆盖**、但同类课程通常会讲的内容，避免复习时误以为学过：

1. **沙丘形态类型的系统清单与图示**（幻灯片 13、14 为纯图页，文本为零）——barchan / transverse / linear / star / parabolic 的定义与判别，**讲义正文中不存在**。
2. **界面等级体系（1st/2nd/3rd order）与 super surface**——**完全未出现**。讲义只用了 bounding surface / reactivation surface / superimposition surface 三个不分级的名词。
3. **megaripples**——在幻灯片 26 被列为三类波痕之一后**再未提及**。
4. **风成 vs 水成交错层理的对比判据表**——讲义提供了全部素材（规模、倾角、纹层类型、界面），但**没有做成对比**。（笔记在第六节替你做了，标 📎。）
5. **理想垂向相序柱状图**——本讲义未给（对比 W07–W09 的做法）。
6. **风成砂岩的储层意义**——完全未提。
7. **定量公式**——一条也没有。

---

## 五、Practical 要点

### ⚠️ 本周无 practical

**本课程的 Practical 只开设到 Week 6。** 仓库中 `Sophomore/Hilary Term/EART23202/Practical/` 下只有 `Week 1`–`Week 6` 六个周文件夹，另加 `Assessment` 与 `Coursework` 两个文件夹——**碎屑岩后半段（W07–W10）本来就没有实习课**，这不是材料缺失或转换遗漏（0b 预处理已核实）。

因此**本周没有实习课内容可以整理**。以下只把讲义中**带有实践性、可直接转化为描述—解释流程**的内容归入本段，**不编造任何实习环节**。

### 5.1 讲义中可直接用于露头/岩心描述的操作性内容

如果在野外或岩心上遇到一段疑似风成的砂岩，讲义提供的**可操作观察清单**如下（全部有讲义出处）：

**第一步：量交错层组的规模与几何**
- 层组厚度、前积层倾角（讲义给的参照：颗粒流单元 **18–36°**，古代因压实偏低；波痕背风面 **<20°**）。
- 前积层的底界形态：**角状（planar/angular，A 型）还是渐近/切线状（asymptotic/tangential，B 型）**（幻灯片 43）。
- ⭐ **若为 B 型，可直接用作顶底判别（way-up indicator）。**

**第二步：识别层组内部的纹层类型（本周核心技能）**

| 观察到的特征 | 判为 | 出处 |
|---|---|---|
| 内部**无构造**、呈**楔形/舌状**、向下坡**尖灭**、常成叠置组 | **Grainflow（颗粒流）** | 幻灯片 34–35、39 |
| **薄、席状（tabular）**、**披覆**在背风坡上、可延伸至坡脚、常夹在颗粒流单元之间 | **Grainfall（颗粒降落）** | 幻灯片 36 |
| **低角度、纹层极薄且规则**、**反粒序**、"细条纹（pinstripe）"外观 | **Wind-ripple / translatent strata（风成波痕纹层）** | 幻灯片 32–33 |
| **近水平、起伏仅数毫米、表面不规则**、呈瘤状或不规则波状 | **Adhesion strata（黏附构造）** → 指示**潮湿地表** | 幻灯片 46 |

**第三步：定位这些纹层在沙丘上的位置**
- 颗粒流多 → 背风坡**中上部**；
- 风成波痕为主的低角度层 → **底积层（bottomset）/ 翼部 / 基座**；
- 若颗粒流舌状体**插入并尖灭进**风成波痕纹层 → 你正看在**背风坡坡脚（toe）**（幻灯片 39）。

**第四步：找界面并判断类型**
- **削截整套前积层、构成层组顶界** → **set-bounding surface**；
- **位于层组内部、上下都是背风面沉积、中间夹一段侵蚀** → **reactivation surface**（幻灯片 36 图注的粉线）；
- **中等倾角、代表较小沙丘沿大型床型翼部迁移** → **superimposition surface**（幻灯片 38）。

**第五步：识别沙丘间层并判定体系类型**
- 夹在交错层组之间的**水平层理层** = **interdune element**（幻灯片 45B 的红色层）；
- 其内部构造决定沙丘间类型：**风成波痕 → dry；黏附构造 → damp；水下波痕 → wet**（幻灯片 44）；
- 由此上推**整个体系**是 **dry / wet / stabilising**（幻灯片 16），并进一步推断**保存机制**（幻灯片 52）。

**第六步：古流向**
- 📎 **背景补充：** 风成交错层前积层的倾向即**古风向（下风向）**。因为风成体系的风况可能多向，古流向数据的**离散度本身就是信息**——低离散 → 单向风况（对应高 RDP/DP）；高离散或双峰/多峰 → 多向风况。**这一条讲义未写**，但它是把野外测量与幻灯片 15 的 RDP/DP 轴连起来的唯一途径，且属于先修课 EART27201 的既有技能。

### 5.2 与考核的关系

大纲给出的考核构成为：**Written assignment 30% / Practical skills assessment 20% / Other（Examination）50%**。由于 W07–W10 无 practical，**本周内容的考核出口只能是期末考试（50%）与写作作业（30%）**——即以**论述与解释**为主，而不是实习技能评分。因此复习本周时，**优先训练"给一段露头描述、说出它的成因过程与体系类型"这种文字论述**，而不是绘图打分式的实操。

---

## 六、易错点 / 重点难点

### 易错点 1（⭐⭐⭐）：三类纹层的成因位置记反

这是本周最容易失分的地方。用一张表钉死：

| 纹层类型 | 成因过程 | **在沙丘上的位置** | 内部特征 | 倾角 |
|---|---|---|---|---|
| **Grainflow（颗粒流）** | 干松砂在休止角坡面上**重力崩塌** | **背风坡中—上部**，向下坡尖灭为舌状体 | **内部无构造（structureless）**、楔形 | **18–36°** |
| **Grainfall（颗粒降落）** | 跃移颗粒云被带过 **brink** 后**气流减速、载沙力下降** | **披覆整个背风坡**，可延伸至坡脚；也见于**翼部/裙裾**（当次生横向风不足以造波痕时） | **薄、席状（tabular）**，常夹在颗粒流单元之间 | 随坡面 |
| **Wind-ripple（风成波痕）** | **跃移 + 反跳**驱动的波痕迁移 | **底积层（bottomset）、坡脚、低角度翼部与基座**；也遍布迎风坡与沙丘间 | **反粒序、pinstripe、平移纹层** | **<20°** |
| **Adhesion（黏附）** | 运动颗粒**黏附在潮湿地表** | **不在沙丘上——在湿润沙丘间（damp interdune）** | 近水平、起伏数毫米、表面不规则 | ≈0° |

**记忆链**：**过 brink → 降落（grainfall）→ 堆到休止角 → 崩塌（grainflow）→ 冲到坡脚 → 被波痕接管（wind-ripple bottomset）。** 一条按重力与坡度递进的因果链，比死记位置牢靠得多。

### 易错点 2（⭐⭐⭐）：反粒序的方向与成因

**风成波痕纹层是"反粒序（inverse grading）"——每一纹层向上变粗。** 极易与水成沉积的正粒序混淆，或把成因记反。

**成因必须能复述**：迎风坡受**高角度**撞击 → 粗颗粒被**蠕移推向脊部**；背风坡是**阴影区**、只有少量**低角度**撞击 → 细颗粒沉积在**槽部**。波痕向下风迁移时，**脊部的粗砂盖在前方槽部的细砂之上**，于是每个纹层底细顶粗。

**同一机制也解释 pinstripe lamination**：**略细的条带 = 波痕槽通过；略粗的条带 = 波痕脊通过；一条条纹 = 一个波痕。**

### 易错点 3（⭐⭐）：混淆两套"干/湿"三分法

| | 分的是什么 | 三个类别 | 出处 |
|---|---|---|---|
| **体系（system）三分** | **整个风成体系的堆积由什么控制** | **dry / wet / stabilising** | 幻灯片 16，Kocurek & Havholm (1993) |
| **沙丘间（interdune）三分** | **沙丘间洼地的地表与潜水面的关系** | **dry / damp / wet** | 幻灯片 44，Mountney & Russell (2004) |

⚠️ **注意第二套里有 "damp" 而第一套没有；第一套里有 "stabilising" 而第二套没有。** 看到 "stabilising" 就是在讲体系；看到 "damp" 就是在讲沙丘间。

**并且注意 damp 与 wet 的精确差别**（原文措辞极其精确，答题时要照抄这个措辞）：
- **damp** = **潜水面的毛细边缘带（capillary fringe）** 接触沉积面（地表看起来是湿的，但没有自由水）；
- **wet** = **潜水面本身**接触沉积面（地表有自由水，能形成水下波痕）。

### 易错点 4（⭐⭐）：把 compound 与 complex draa 记反

- **Compound**（复合）= 小沙丘叠加在**同类型**的大沙丘上（"同" → compound，可记作"同类复合"）。
- **Complex**（复杂）= 小沙丘叠加在**不同类型**的大沙丘上（"异" → complex，"复杂"因为混了两种形态）。

（幻灯片 47，sensu McKee, 1979）

### 易错点 5（⭐⭐）：creep 与 reptation 混为一谈

- **creep（蠕移）**：由**床面上的拖曳力直接驱动**，颗粒滚动/滑动，**不离开床面**。
- **reptation（反跳）**：**跃移颗粒落地撞击**传递动量，使被撞颗粒**短距离跳跃**。
- 两者都在床面附近、都是"短距离"，但**驱动力完全不同**：一个是流体，一个是碰撞。
- ⭐ 讲义特别指出 **impact ripples 由 saltation + reptation 组合发育**（幻灯片 30），**不是 creep**——但幻灯片 32 又说迎风坡的高角度撞击**促使粗颗粒 creep 向脊部**。所以两者在波痕成因中**都参与，但角色不同**：reptation 提供普遍的向下风搬运，creep 负责粗颗粒的向脊富集（即分选）。

### 易错点 6（⭐⭐）：以为"堆积"就等于"保存"

**幻灯片 50 的核心信息是反直觉的**：*entire ergs may be constructed and accumulated to considerable thicknesses, only to be later deflated to leave no record.*

答题时若被问"某风成砂体为何得以保存"，**必须回答保存机制而不是堆积机制**：

1. **沉降（subsidence）是产生可容空间、促成保存的首要动力**；
2. 具体两条路径：**(a) 被置于侵蚀基准面（baseline of erosion）之下**——该面由**空气动力学构型**决定，是吹蚀能下切到的极限；**(b) 被置于潜水面之下**——通过沉降穿过静止潜水面，或（更短时间尺度上）通过潜水面的**绝对上升**。
3. **可容空间生成速率 vs 风成堆积填充速率之比**，控制**保存下来的建筑样式**。

### 易错点 7（⭐⭐）：以为风成砂"一定分选极好"

这是常识性直觉最容易翻车的地方。**讲义本身并没有说风成砂分选一定极好**，而且讲义提供了三条反证：

1. **沙丘间（interdune）沉积**完全不同于沙丘砂：**湿型沙丘间**有水下波痕、可含泥质与蒸发质；**湿润型**有黏附构造，其形成机制（干砂黏附到湿面上）本身就不产生分选。
2. **风成波痕纹层的成因就是分选作用**——脊粗槽细，说明**同一套沉积内部存在系统性的粒度差异**，"整体分选好"与"纹层间粒度分异"是两回事。
3. **黄土**（悬移端元）与 **reg / serir**（滞留端元）分别代表被吹走的细粒与留下的粗粒，二者都属于风成过程的产物，但都不是"分选极好的中砂"。

⭐ **正确的表述是**：**风成沙丘砂（尤其是跃移与颗粒流成因的部分）分选好**，但**风成体系整体是高度非均质的**，其非均质性正来自沙丘/沙丘间/沙席/zibar 的相组合与各级界面。

### 易错点 8（⭐⭐）：风成 vs 水成交错层理的判别

> 📎 **本表为背景补充整合。讲义提供了左栏的全部数据，但没有做成对比表；右栏的水成数据来自先修课 EART27201。** 引用时请注意这是笔记的整合。

| 判据 | **风成** | **水成（河流/浅海）** |
|---|---|---|
| **层组规模** | **可极大**（单套 set 可达数米至数十米；draa 级更大） | 通常**厘米—米级** |
| **前积层倾角** | **高**，颗粒流单元 18–36°（近休止角） | 通常较低，且常被流体阻力削缓 |
| **纹层类型** | **grainflow（块状楔形）+ grainfall（薄席状）+ wind-ripple（反粒序、pinstripe）** 三者共存 | 无此三分；以底负载纹层、爬升波痕、悬移泥披为主 |
| **粒序** | 风成波痕纹层**反粒序** | 多为**正粒序**或无粒序 |
| **底积层** | 常呈**渐近/切线状（asymptotic）** | 也可切线状，但规模小 |
| **泥质/生物** | **极少泥、无海相生物、可有根迹与足迹** | 常见泥披、生物扰动、海相化石 |
| **界面** | **低角度、延伸极远的界面**（可数百米—数公里） | 界面延伸有限 |

⭐ **最可靠的单条判据是"三类纹层组合"**：只要在一套高角度交错层的前积面上同时识别出**块状楔形的颗粒流**与**薄席状的颗粒降落**，基本可以定为风成。

### 易错点 9（⭐）：界面术语的层级混淆

讲义只给了**三个不分级的名词**：set-bounding surface / reactivation surface / superimposition surface。**不要在答题时凭印象引用"一级面 / 二级面 / 三级面"或 "super surface" 说这是本课内容**——第 2.8 节的等级体系是笔记补充（📎）。

如果一定要用，务必对应清楚：**reactivation ≈ 3rd order（set 内部、背风面局部侵蚀）；superimposition ≈ 2nd order（叠加沙丘迁移）；interdune migration ≈ 1st order（draa 迁移）**——**并注明这是课外补充**。

### 易错点 10（⭐）：几个数字要背准

| 数字 | 内容 |
|---|---|
| **30% / 20% / 6%** | 陆表干旱—半干旱面积占比 / 其中风成砂覆盖占比 / 相乘所得（⚠️ 讲义写作"Earth surface"有误，见勘误 2） |
| **50–200 mm / 5–10 mm（罕至 30 mm）** | 风成波痕的波长 / 高度 |
| **12–50** | 风成波痕的形态指数（波长/高度） |
| **<20°** | 风成波痕背风面倾角（**低于休止角**） |
| **32–36°** | 干松砂的休止角 |
| **18–36°** | 颗粒流单元在前积层中的倾角（古代因压实偏低） |
| **500–5000 m / >50 m** | draa 的波长 / 高度 |
| **<10°、起伏数米** | zibar 的坡度与起伏 |
| **<0.1 mm** | 可长期悬浮远距离搬运的火山细灰粒径 |
| **6000 μg·m⁻³** | 严重沙尘事件的大气粉尘浓度上限量级 |
| **35 km × 2 km** | 火星 Gale crater 内 Bagnold 沙丘场的规模 |

### 难点：把本周接回全课主线

本周作为**全课最后一周**，最可能出现的综合题是"把风成体系放回相分析框架"。三条抓手：

1. **瓦尔特定律（Walther's Law）**：垂向上相邻叠置的相，必然在横向上曾经相邻。风成体系里最直接的应用就是——**垂向柱状剖面上"沙丘层 ↔ 沙丘间层"的反复叠置，对应横向上"沙丘 ↔ 沙丘间"的地貌配置**，而叠置比例记录了沙丘的**爬升角与可容空间条件**。
2. **过程 → 产物**：本周是全课"过程—产物"对应最干净的一周——**一种纹层 = 一种物理过程 = 沙丘上一个位置**。若被问"如何从岩石反推古环境"，本周的三类纹层是最好的例子。
3. **可容空间控制保存**：幻灯片 50–52 讲的 accommodation/supply 平衡，与碳酸盐板块（W06）以及层序地层学方法（W01）是同一套框架。📎 **这一跨周整合是笔记的推断，讲义未写。**

---

## 七、本周术语表

### 7.1 本周术语（全部出自本周讲义）

| 英文 | 中文 | 要点 |
|---|---|---|
| Aeolian | 风成的 | 由风引起的**侵蚀、启动、搬运、沉积**四类过程及其产物；源自拉丁语 Æolus（风神） |
| Entrainment | （颗粒的）启动 / 卷扬 | 风力克服地表稳定化效应时发生 |
| Lift (L) | 空气动力上举力 | 促进启动；由流体绕流产生 |
| Aerodynamic drag (D) | 空气动力拖曳力 | 由流体绕流产生（⚠️ 讲义把它列入阻力项，见勘误 1） |
| Cohesion (C) | 颗粒间黏聚力 | 阻碍启动；受含水量、胶结度控制 |
| Impact (I) | 弹道撞击 | 促进启动；跃移颗粒落地传递动量 |
| Bedload | 推移质 | 砂级及更细的砂主要以此方式搬运，构成沙丘与沙席 |
| Suspension | 悬移 | 粉砂与黏土的主要搬运方式，形成黄土与粉尘 |
| Creep | 蠕移 | 床面拖曳力直接驱动的滚动，**不离开床面** |
| Saltation | 跃移 | 颗粒被短暂举入气流后落回并**引发碰撞连锁反应**；风成砂搬运中**最重要** |
| Reptation | 反跳 / 蠕跳 | 跃移颗粒落地撞击导致其他颗粒**短距离跳跃** |
| Deflation | 吹蚀 | 风把细粒吹走的侵蚀作用 |
| Deflation lag / Reg / Serir | 吹蚀滞留沉积 / 砾漠 | 细粒被吹走后残留的砾石覆盖面；实例 Mojave Desert |
| Erg / Sand sea | 砂海 / 沙海 | 以广布沙丘为特征的风成沙漠地貌 |
| Back-erg / Fore-erg / Central erg / Erg margin | 后缘 / 前缘 / 中央砂海 / 砂海边缘 | 按上风—下风位置划分的沙丘场分区（Porter, 1987） |
| Geomorphic element | 地貌单元 | 按**净侵蚀 / 净过路（bypass）/ 净沉积**划分 |
| Dry aeolian system | 干型风成体系 | 堆积**仅由空气动力学构型控制**（下风向气流减速卸载） |
| Wet aeolian system | 湿型风成体系 | 堆积由**潜水面持续上升**控制 |
| Stabilising aeolian system | 稳定型风成体系 | 物理/化学/生物营力（植被、地表胶结）限制风的搬运能力 |
| Aeolianite | 风成岩 / 风成碳酸盐砂岩 | 胶结的风成砂岩，常为碳酸盐质；实例 Bahamas、Bermuda、Orkney |
| Loess | 黄土 | 风成粉砂与黏土；多与冰期外冲平原相关；肥沃但易蚀 |
| Ocean fertilization | 海洋施肥 | 富营养粉尘入海刺激浮游植物生长 |
| Ripple / Dune / Megadune (draa) | 波痕 / 沙丘 / 巨型沙丘 | 风成床型的**三级平衡层级**（Wilson, 1972） |
| Draa | 巨型沙丘 | 波长 500–5000 m、高 >50 m；可承载叠加的沙丘级床型 |
| Compound draa | 复合巨型沙丘 | 小沙丘叠加在**同类型**大沙丘上 |
| Complex draa | 复杂巨型沙丘 | 小沙丘叠加在**不同类型**大沙丘上 |
| Impact ripple / Wind ripple | 冲击波痕 / 风成波痕 | 波长 50–200 mm、高 5–10 mm、形态指数 12–50、背风面 <20° |
| Ripple-form index | 波痕形态指数 | 波长/高度之比；风成波痕为高值（12–50） |
| Saltation path length | 跃移路径长度 | **决定冲击波痕的间距**；受粒径、形状、密度、风速与阵性控制 |
| Stoss slope / Lee slope | 迎风坡 / 背风坡 | 迎风坡受高角度撞击；背风坡为**阴影区（shadow zone）** |
| Inverse grading | 反粒序 | 纹层向上变粗；风成波痕纹层的诊断特征 |
| Translatent strata | 平移纹层 | 波痕以亚临界角爬升所留下的薄纹层 |
| Pinstripe lamination | 细条纹纹层 | 波痕以**极低亚临界角**互爬；粗条=脊、细条=槽，一条=一个波痕 |
| Megaripple | 巨波痕 | 讲义列为三类波痕之一，但**未展开** |
| Adhesion strata | 黏附构造 | 运动颗粒黏附于**潮湿地表**；细分为黏附平行层、黏附波痕、黏附瘤 |
| Adhesion wart | 黏附瘤 | 黏附构造的一种；实例 Indian Creek（Utah）、元古界 Independence Fjord Group |
| Grainflow | 颗粒流 | 休止角（32–36°）坡面上干松砂的**重力崩塌**；单元倾角 18–36°、**内部无构造**、呈舌状 |
| Grainfall | 颗粒降落 | 跃移颗粒云被带过 **brink** 后气流减速、载沙力下降而降落；**薄、席状、披覆背风坡** |
| Brink | 丘顶转折点 | 沙丘顶部由迎风坡转入背风坡的折线 |
| Plinth / Apron / Flank | 基座 / 裙裾 / 翼部 | 沙丘周缘低角度部位，以风成波痕纹层为主 |
| Bottomset | 底积层 | 背风坡坡脚的低角度沉积，**风成波痕主导** |
| Angle of repose | 休止角 | 干松砂典型 32–36° |
| Set / Coset | 层组 / 层组套 | 由界面分隔的交错层单元及其叠置组合 |
| Bounding surface | 界面 | 后一床型削截前一床型的交错层所形成的侵蚀面（Brookfield, 1977） |
| Reactivation surface | 再作用面 | 记录**一段背风面侵蚀期**，上下均为背风面沉积 |
| Superimposition surface | 叠加面 | 较小沙丘沿较大巨型沙丘翼部迁移形成 |
| Interdune | 沙丘间 | 沙丘之间的低平地带；按潜水面关系分 **dry / damp / wet** |
| Damp interdune | 湿润沙丘间 | **潜水面的毛细边缘带**接触沉积面 → 黏附构造 |
| Wet interdune | 含水沙丘间 | **潜水面本身**接触沉积面 → 水下波痕 |
| Sandsheet | 沙席 | 缺高起伏床型、以冲击波痕面为特征；受砂的**供给（supply）与可搬运性（availability）**限制 |
| Zibar | 低平砂垄 / 原始沙丘 | 坡度 <10°、起伏数米的低起伏垄与穹丘；又称 proto-dune |
| Architectural element | 建筑要素 | 具特定几何形态与内部结构的地层单元（如沙丘要素、沙丘间要素） |
| Net sediment budget | 净沉积收支 | 为正时床型才能相互爬升并堆积 |
| Accommodation | 可容空间 | 其生成速率与被填充速率之比控制保存的建筑样式 |
| Baseline of erosion | 侵蚀基准面 | 由**空气动力学构型**决定的吹蚀下切极限（Kocurek & Havholm, 1993） |
| Subsidence | 沉降 | **产生可容空间、促成保存的首要动力** |
| Water table | 潜水面 | 置于其下可保护风成堆积免受吹蚀 |
| EST (Equivalent Sand Thickness) | 等效砂层厚度 | 沙丘类型判别图的一轴，度量**砂供给量** |
| DP / RDP (Drift Potential / Resultant DP) | 漂移势 / 合成漂移势 | RDP/DP 为另一轴，度量**风向变率**；→1 为单向风，→0 为多向风 |
| GPR (Ground Penetrating Radar) | 探地雷达 | 无损成像现代沙丘内部界面的手段（Bristow & Mountney, 2012） |

### 7.2 📎 全课术语汇总（收尾用）

> 📎 **以下整段为背景补充。** 这些术语**不属于本周讲义**，是笔记依据**各周讲义文件名**与**本周讲义中的回顾性内容**整理的收尾清单，用于把全课串起来复习。**具体定义与细节请回查各周笔记与原讲义，不要以本表为准。** 由于本课大纲的授课顺序与实际完全颠倒，本表**不依据大纲**，只依据文件名所确定的板块归属。

| 板块 | 周次 | 核心术语（📎 全部为跨周汇总，非本周内容） |
|---|---|---|
| **方法论** | W01 `Stratigraphic methods` | 岩石地层学 / 生物地层学 / 年代地层学、层序地层学、不整合、等时面 |
| **方法论** | W02 `Facies analysis` | **Facies（相）**、facies association（相组合）、**Walther's Law（瓦尔特定律）**、facies model（相模式） |
| **碳酸盐** | W03 `Carbonate platforms` | Carbonate factory（碳酸盐工厂，T/C/M）、rimmed shelf、ramp、isolated platform、epeiric platform |
| **碳酸盐** | W04 `Facies peritidal-subtidal-shoal` | 潮上/潮间/潮下带、叠层石、微生物席、鲕粒浅滩（ooid shoal）、潟湖 |
| **碳酸盐** | W05 `Facies reef-basin` | Build-up（建隆）、骨架礁 vs mud mound、bioherm / biostrome、前斜坡、盆地相、远洋沉降 |
| **碳酸盐** | W06 `Carbonate dynamics` | Keep-up / catch-up / give-up、drowning unconformity、碳酸盐随地质时代的演变 |
| **碎屑** | W07 `Shallow Marine Clastic` | 波浪 vs 潮汐主导、临滨—前滨—滨外、HCS（丘状交错层理）、进积/退积 |
| **碎屑** | W08 `Continental Environments` | 河流（辫状/曲流）、点砂坝、冲积扇、湖泊、古土壤 |
| **碎屑** | W09 `Deep-water Systems` | 浊流、鲍马序列（Bouma sequence）、海底扇、水道—天然堤—朵体、块体搬运沉积（MTD） |
| **碎屑** | **W10（本周）** | **见 7.1 全表** |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Aeolian_Systems (1).md`，幻灯片 5（Aeolian transport processes，受力平衡页） | "For grains of sand and finer grade, ballistic impacts and aerodynamic lift promote entrainment, whereas **particle weight, friction, drag, and cohesive inter-particle forces retard entrainment**." | **内部自相矛盾且与空气动力学不符。** 同一页下方的图例把 **D = aerodynamic drag** 与 L、I 并列标为作用在颗粒上的力；在标准的颗粒启动受力分析中，**拖曳力（drag）是驱动颗粒运动的力，不是阻碍启动的力**。把 drag 列入"阻碍"一侧与紧邻的前半句（drag 与 lift 同由绕流产生）也不协调 | 应为 "…whereas **particle weight, friction, and cohesive inter-particle forces** retard entrainment"。**正确的受力分组为：驱动 = lift (L) + drag (D) + impact (I)；阻力 = weight (W) + friction + cohesion (C)。** 答题时请按后者作答 |
| `Aeolian_Systems (1).md`，幻灯片 10（Desert aeolian environments） | "Approximately **30% of the present-day land surface** is characterised by arid or semi-arid climatic conditions. Of this 30%, aeolian sand deposits cover 20% of these regions (**6% of the Earth surface**)." | **换算口径错误。** 30%（陆地）× 20% = **6% 的陆地表面**，而不是 6% 的地球表面。地球表面约 71% 为海洋，陆地仅约 29%，故 6% 的陆地表面仅相当于约 **1.7% 的地球总表面** | 应为 "**6% of the land surface（陆地表面的 6%）**"。若确要给出占地球总表面的比例，约为 **1.7%**。⚠️ 这条数字在考试中可能被直接引用，请按"陆地表面的 6%"记 |
| `Aeolian_Systems (1).md`，幻灯片 20（Extra-terrestrial aeolian environments） | "Extra-terrestrial aeolian environments … exist on various celestial bodies, including Mars, Venus, **Earth's Moon**, Titan (Saturn's moon), and **asteroids like Eros and Itokawa**." | **物理上不成立。** aeolian 的定义（本讲义幻灯片 4）明确是"**由风**引起的侵蚀、启动、搬运与沉积"。**月球、Eros、Itokawa 均无大气层，因而不存在风，也就不可能有严格意义上的风成过程** | 月球与小行星上确实存在**颗粒物质的迁移与分选**（如 Eros 表面的 "ponded deposits"、Itokawa 表面的粒度分带），但其营力是**撞击震动、静电悬浮与微重力下的颗粒流**，属 **granular / regolith processes**，**不是 aeolian 过程**。**真正具有风成过程的地外天体是有大气的：火星、金星、土卫六 Titan，以及（争议中的）冥王星与海卫一 Triton。** 答题时切勿写"月球上有风成沙丘" |
| `Aeolian_Systems (1).md`，幻灯片 44（Aeolian bedforms: interdunes，定义句） | "Aeolian interdunes are **elongated, relatively flat, and sandy** landforms that exist between larger sand dunes…" | **过度概化（表述不严谨，非硬性错误）。** (a) "elongated（狭长）"只适用于线性/横向沙丘场中的沙丘间，星状沙丘之间的沙丘间常为**不规则的多边形洼地**；(b) "sandy（砂质）"排除了大量非砂质情形——**湿型沙丘间**常发育泥质、蒸发岩（石膏/盐）与微生物席，**吹蚀型沙丘间**的底面可以是砾石滞留面甚至基岩 | 更稳妥的表述：**沙丘间是位于沙丘之间的低起伏地带，其几何形态受沙丘形态类型控制，其沉积充填由潜水面位置决定（干型为风成波痕砂；湿润型为黏附构造；含水型可含水下波痕、泥质与蒸发岩）**。讲义同页后文自己给出的 dry/damp/wet 三分其实已经与"sandy"这一限定相冲突 |
| `Aeolian_Systems (1).md`，幻灯片 47（Megadunes） | "Complex draas **occus** where a smaller dune is superimposed on a larger dune of a different morphological type" | 拼写错误（typo） | 应为 "**occur**"。不影响理解 |
| `Aeolian_Systems (1).md`，幻灯片 13、14（Dune Types） | 两页仅剩标题 "Dune Types" 与 "Image: Mountney et al., 2023"，**无任何正文** | **不是错误，是内容缺口。** 原件该两页为纯图页（沙丘形态类型图版），pptx→md 转换无法提取图中文字 | **本讲义的可提取文本中不存在沙丘形态类型（barchan / transverse / linear / star / parabolic）的定义与清单。** 复习该内容须回查原 pptx 或教材（Mountney et al., 2023）。本笔记第 2 节与第三节图 4 中的相关内容**已全部标注为 📎 背景补充** |
| `Aeolian_Systems (1).md`，幻灯片 37 | OCR 识别文本："re al / wind directian & direction of migration / gralnfall blanketing lee slope / grainflow tongues / Battomset wind-ripple dominated" | **OCR 识别噪声，非原件错误。** 该页为纯图页，md 中已注明"以下内容由图片 OCR 识别得到…识别可能有误" | 按上下文还原为：**"wind direction & direction of migration"（风向与迁移方向）、"grainfall blanketing lee slope"（颗粒降落披覆背风坡）、"grainflow tongues"（颗粒流舌状体）、"Bottomset — wind-ripple dominated"（底积层，风成波痕主导）**。还原后与幻灯片 39 图注完全吻合，可放心使用。**不计为材料本身的错误** |
| `Aeolian_Systems (1).md`，幻灯片 2/3、25/29/41 | 幻灯片 2 与 3 内容完全相同；25、29、41 三页内容完全相同 | **不是转换重复，是讲者刻意的章节分隔页设计** | 无需更正。**反而是重点信号**：重复出现的页面标示了讲义的三段式结构与最重要的一张图（三级床型尺度图），已在第四节说明 |

**另有一处需要说明但不列为勘误**：幻灯片 26 把小尺度波痕分为 **impact ripples、megaripples、adhesion ripples** 三类，但全篇**只详细展开了 impact ripples 与 adhesion ripples，megaripples 再未提及**。这属于**讲义内容缺口**而非错误（很可能是课堂上口头带过），已在第四节 4.5 与第七节术语表中如实标出。

**本周除上表外未发现其他材料错误。**
