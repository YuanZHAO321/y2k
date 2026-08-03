# Week 4 — 天气与天气预报（Weather and Weather Forecasting）

> 材料来源：`Week4-Lecture2025.pptx`（155 张幻灯片）＋ `EART11100 - 17-Feb-transcript`（课堂全程录音转写）
> 授课人：David Schultz（Prof. Dave，Dept of Earth and Environmental Sciences, University of Manchester）
> 本周是 A Dynamic Planet 大气板块的第二讲，承接 Week 3（大气结构、递减率、绝热过程、急流 jet stream、水汽混合比）。

---

## 一、本周主题

本周把视角从"大气有什么结构"转向"**大气如何演化、我们怎么预测它、为什么预测会失败**"。全课围绕五条主线展开：

1. **天气预报是怎么做出来的（How weather forecasts are made）**
   - 从 19 世纪"预报不是科学"的偏见，到 Bjerknes 提出的**物理基础预报（physically-based forecasting）**两要素配方；
   - 从 Richardson 手算的"预报工厂（Forecast Factory）"梦想，到 1949–50 年第一次计算机预报，再到今天的 ECMWF。
   - 核心因果链：**观测（observations）→ 资料同化（data assimilation）→ 数值模式（computer model）→ 人工预报员（human forecaster）→ 用户（users）**。

2. **为什么好的预报会变坏（Why do good forecasts go bad?）** —— 三大原因：
   - Reason #1：**初始条件不完美**（观测空洞、仪器误差、有些量根本没有观测）；
   - Reason #2：**模式不完美**（算力限制分辨率、物理过程理解不足 → 参数化 parameterization）；
   - Reason #3：**混沌（chaos）** —— 即使模式与初始条件都完美，可预报性也有**两周**的理论上限。

3. **温带气旋结构（Extratropical cyclone structure）** —— 挪威气旋模式（Norwegian cyclone model）的四阶段演化、锋面类型、南北半球镜像、气旋与反气旋对天气的实际影响。

4. **如何用网络看今天的天气** —— 观测（surface map / satellite / radar / lightning）与预报（forecast model output）的严格区分，以及具体网站与 ManUniCast 的使用。

5. **野外天气安全（Weather safety in the field）** —— 雷电安全与洪水安全。老师原话："This lecture could save your life."

> **老师强调的迁移价值**：今天讲的原理不只适用于天气模式，**同样适用于任何建模预测系统**——河流洪水模式（Environment Agency 用的）、气候模式、空气质量预报模式，全都基于同一套原理（观测 + 物理定律 + 网格化 + 参数化 + 混沌限制）。

**本周要求的视频与阅读（幻灯片 Slide 3）**
- Videos: Extratropical cyclones; How does the jet stream control the weather in the midlatitudes?; Weather around the world; Both sides now: Clouds
- Required reading: Midlatitude Cyclones (Schultz 2011); Mountain Safety: Student Ambassador Insights（Olivia Heard，三年级 BSc Geology/Geography 学生的亲历报告）

---

## 二、核心概念

### 2.1 天气预报的史前史：为什么"预报"曾被认为不是科学

**驱动力：观念障碍，而非技术障碍。**

- 19 世纪中叶，皇家学会（Royal Society）那批"绅士科学家"确实在**收集观测**、研究天气如何运作，但他们**没有迈出下一步**——即"既然我知道现在的状态，也许可以用它推断未来"。
- **François Arago（1846）**，巴黎天文台台长、法国科学院常任秘书，代表了当时科学精英的态度：
  > "Whatever may be the progress of sciences, **NEVER** will observers who are trust-worthy, and careful of their reputation, venture to foretell the state of the weather."
  （无论科学如何进步，值得信赖、爱惜声誉的观测者**永远不会**冒险去预言天气状态。）
  这里 "state of the weather" = 大气的状态（conditions in the atmosphere）。
- **1920 年以前**，预报靠的是**经验法则（empirical rules of thumb）**，由老预报员口传给新预报员。当时**没有覆盖区域的天气图**，连"当前状态"都拼不出来，更谈不上未来状态。
- **Robert FitzRoy** 的悲剧（transcript 独有）：他是小猎犬号（HMS Beagle）船长——就是载达尔文环球、促成自然选择理论的那艘船。他在 19 世纪中叶尝试建立英国的气象预报机构（Met Office 的前身）。因为承受巨大压力与嘲讽，最终**自杀**。今天 Met Office 位于 Exeter，所在街道以他命名（FitzRoy Road），算是对他努力的纪念。
  - **因果链要点**：科学界的敌意 → 预报机构缺乏合法性 → 个人承担全部压力 → 事业与生命双重代价。

### 2.2 Vilhelm Bjerknes（1904）：现代气象学的起点

**"Modern meteorology began in Norway."**

- Bjerknes 是**物理学家**，研究**流体力学（fluid mechanics）**，他注意到**流体运动方程**与**电磁学方程**在形式上的相似性。
- 他的核心推理（transcript）：如果我们能用物理定律预测**单摆的运动**、预测**炮弹（projectile）的弹道**，那**为什么不能对大气做同样的事**？
- 由此得出他那句奠基性论断：
  > "**Subsequent atmospheric states develop from the preceding ones according to physical law.**"
  （后继的大气状态是按照物理定律从先前状态发展而来的。）
- 他在挪威建立了研究团队（Bergen school 的源头），其工作是现代气象学的基础。

**Bjerknes 的两要素配方（How to make a weather forecast）** —— 全课最需要背的一条：

1. **A sufficiently accurate knowledge of the state of the atmosphere at the initial time.**（对初始时刻大气状态的足够准确的认识）
2. **A sufficiently accurate knowledge of the laws according to which one state of the atmosphere develops from another.**（对大气由一个状态演变为另一状态所遵循的定律的足够准确的认识）

> 注意"**sufficiently accurate**（足够准确）"这个限定词——不是"完美"，而是"够用"。后半节课讲的三大失败原因，正好就是这两个要素各自被打破的方式（要素 1 破 → Reason #1；要素 2 破 → Reason #2；两者都完美仍然失败 → Reason #3 混沌）。

**1904 年的现实困难**（transcript 补充）：
- 观测收集非常繁琐，且**缺乏把观测跨国/跨区域传输汇集的机制**；
- 定律虽然已知，但**应用它们**在计算上极其耗时。

### 2.3 Lewis Fry Richardson（1922）：第一次数值预报尝试

**人物背景（transcript 大量补充，考点外但极有价值）**
- 来自 Yorkshire，**贵格会教徒（Quaker）与和平主义者（pacifist）**。一战被征召时拒绝作战，**改开救护车**。
- **Richardson number（理查森数）**即以他命名。
- 他在**一战开救护车的间隙**，手工完成了第一次定量数值预报尝试，成果写成 1922 年的书 *Weather Prediction by Numerical Process*（曼大图书馆有藏本；老师评价他"文笔算不上优雅，但方法全在里面"）。

**Richardson's "Dream"：The Forecast Factory（预报工厂）**
- 想象一个**球形大礼堂**，球体内壁绘着**地球地图**；
- **64,000 名"人肉计算员（human computers）"**按经纬度分布坐在球面各自的位置上，每人负责一个约 **220 km 见方**的格子（英国大致只占几个格子）；
- 礼堂中央、从"南极"位置升起的高台上站着一位**指挥者（conductor）**，手持一束光，照到哪个经纬度格子，那格的人就报出自己的计算结果，周围的人便可基于相邻格的结果继续计算；
- 指挥者的作用是**保持所有计算同步向前推进**——这实际上就是**并行计算 + 有限差分格式中格点间信息交换**的物理化比喻。

**Richardson 实际做的事与结果**
- 规模远比梦想"modest"：他挑了过去的某一天，在**德国境内的一个格点**上，尝试预报**未来 6 小时**的天气。
- 花了**数年**（战时断续进行），中途**手稿全部丢失**，后来在**煤堆下面**被找回。
- **结果：彻底失败** —— 算出的**气压变化比实际大 10–100 倍**（幻灯片：Pressure changes were 10–100 times too large!）。

**失败的真正原因（现代事后诸葛）—— 老师的潮汐类比，非常重要**
- 他需要**对初始条件做滤波（filter the initial conditions）**，把**高振幅/高频的特征**去掉。
- 类比：你想测量海滩某点**潮汐的涨落（tide）**，但你的测量里混进了**岸边所有正在破碎的波浪（waves breaking on the shoreline）**。必须先把这些高频波滤掉，才能看到慢速演变的潮汐信号。大气里也一样——快速的重力波（声波/重力波）淹没了慢速演变的天气尺度信号。
- **Peter Lynch（爱尔兰，约 20 年前）** 重做了 Richardson 的计算：加上滤波之后，**Richardson 本可以得到正确答案，做出一个好预报**。
- 结论：**"He was 30 years ahead of his time."** 他不知道这些数学，但他建立的方法本身是对的；现代数值预报的许多原理都出自他。

**Richardson 的后半生（transcript 独有的精彩离题）**
- 他研究大气流动与湍流，一战期间各国政府对他的研究非常感兴趣——因为可以用来**预测芥子气（mustard gas）的扩散**。
- 作为和平主义者，他无法接受自己的工作被用来**杀人**，于是**离开气象学**。
- 后来他转去研究**战争与人类冲突的统计学**。1950 年代面对冷战，他用数学论证：**冷战可以在无人发射核弹的情况下结束**——机制是**军备竞赛（arms race）**升级，其中一方**破产**、无力继续，冷战由此终结。老师评价：在现在被称为"和平研究（peace studies）"的领域里，他**又一次领先时代 30 年**。

### 2.4 从手算到计算机：1949/1950 与 ECMWF

- **1949 年**（幻灯片写 1949，transcript 说 "by 1950"）：**Jule Charney、Ragnar Fjørtoft** 两位气象学家与著名数学家/计算机科学家 **John von Neumann** 一起，用 **ENIAC** 完成了**第一次计算机生成的预报**，对象是**中层大气的流场**。
- 结果：北美中部当天实际有一个**巨大的低压系统**，模式只给出了"some indication"——论文自己承认预报"**uniformly poor**（一致地差）"。但**这是人类第一次真正计算未来天气图的结构与演变**，是里程碑。
- **为什么天气预报是 ENIAC 最早的任务之一**（transcript）：因为它是"**人类算太慢而计算机能算**"的重要问题——要做 24 小时预报，就必须**在 24 小时内算完**，否则预报毫无用处。这条"计算必须跑赢真实天气"的约束，是整个数值天气预报（NWP）发展史的根本驱动力。
- **今天：ECMWF（European Centre for Medium-Range Weather Forecasts）**，总部在英国 **Reading**，是欧洲多国**共同出资（consortium）**建立的机构，公认是世界最好的预报机构之一。
  - 定位：**medium range / 中尺度以上**——他们不关心小尺度现象，关心的是**大陆尺度与全球尺度的天气型**。
  - 图表网站：`charts.ecmwf.int`
- **AI 时代补充（transcript）**：当前人工智能浪潮中，**天气预报是众多团队最早用大模型攻克的问题之一**。

### 2.5 要素一：观测系统与资料同化

**目的**：确定"现在大气是什么状态"，作为模式的**初始条件（initial conditions）**。

课上给出的 ECMWF 单日（9 月 30 日的一次预报）各观测系统进入同化系统的**观测数量**——数量级关系是考点：

| 观测系统 | 数量（该日） | 覆盖特点 / 局限 |
|---|---|---|
| **Surface observations**（机场与船舶 airports and ships） | **228,333** | 强烈偏向**陆地、有人居住的地方**；海洋与无人区稀疏 |
| **Buoys**（浮标，漂流式或锚定海底） | **2,045** | 填补海面空白，但数量少 |
| **Radiosondes**（无线电探空仪，气球携带） | **1,104** | 唯一直接的高空原位观测；**几乎只在陆地、且集中在全球北方（global north）** 有投资建网的国家 |
| **Aircraft observations**（商业航空器加装仪器） | **883,563** | 约为地面站的 4 倍；但**偏向航线与机场所在位置** |
| **Satellite observations** | **> 8,800,000** | **比其他所有系统高一个数量级**，能填补无观测区，对全球预报误差的降低贡献最大 |

- **人物**：**Professor Vilho Väisälä**（芬兰）在 **1920–30 年代**完善了可由气球携带升空并回传天气条件的仪器——即现代 radiosonde 的原型；Vaisala 公司即源于此（老师赴英前在芬兰工作，与 FMI、Vaisala 有关联）。
- 课上还提到未在幻灯片单列的观测：**雷达（测降水的雷达、测风的雷达）**等更零散的观测系统。

**Data assimilation（资料同化）**
- 定义：把**各种来源、各种类型、分布不规则**的观测，**内插/融合到一个统一的全球网格**上——**不仅是地面的网格，也包括高空各层的网格**。
- 输出：一套三维网格化场，**这就是初始条件**，代表"大气此刻的状态"。
- **重要区分（Kahoot 第 8 题考点）**：**观测的质量控制（quality control）发生在资料同化系统里，不在模式里**，也**不是参数化的功能**。

### 2.6 要素二：大气的五条定律（Laws of the Atmosphere）

> 老师明确说：**不需要背数学形式**，但**必须知道有这五个方程、它们分别管什么、每一项的物理意义**。
> 并且：**气候模式的大气部分用的也是这同样五个方程**（气候模式只是额外再加上大气化学、海气耦合、海洋自身的方程等）。

**五方程一览**

1. **Ideal Gas Law（理想气体定律）** —— 压强、温度、密度（体积）之间的关系
2. **Conservation of mass (water)（水汽质量守恒）**
3. **Conservation of mass (air)（干空气质量守恒）**
4. **How temperature changes（热力学能量方程）**
5. **How wind changes（动量方程 / 运动方程）**

**五个方程、五个未知量（state variables）** —— 这正是方程组闭合的原因：压强 p、密度 ρ、温度 T、水汽混合比 q、三维速度 **v**。

详见"三、公式与图表"一节的逐项解析。

**从微分方程到计算机：finite differences（有限差分）**
- 计算机不懂微分方程形式，必须把**微分方程（differential equations）转化为有限差分（finite difference）形式**——即"在一张格点网上，如何用相邻格点的值计算各项"。
- **关键的闭环**：观测已经通过资料同化放到了**网格**上；模式也在**同一套网格**上做有限差分计算 → 于是可以把网格化的观测直接喂进模式，跑出网格化的预报。
- **所有预报机构都是这么做的**，包括曼大自己的 **ManUniCast**。

### 2.7 预报技巧的历史改进：怎么度量"变好了"

**ECMWF 曲线（Slide 40）**
- 指标：**6 天预报的 500 hPa 位势高度（geopotential height）的均方根误差 RMSE（单位 m）**，在**北半球**平均，对分析场（analysis）检验；绘的是 **12 个月滑动平均**，最后一点为 2020 年 8 月–2021 年 7 月。
- ECMWF 从 **1984 年**开始业务预报；6 天预报误差从 **约 80–90 m 降到接近 40 m**，即**误差减半**。
- **老师提醒的读图陷阱**："The graph is a little misleading. It doesn't go to zero. It only goes to 40." —— **纵轴不是从 0 开始**，视觉上会夸大/扭曲改进幅度，读图时必须看清坐标轴。
- **Persistence forecast（持续性预报）** 作为**基准线（baseline / no-skill forecast）**：
  - 定义：假设**6 天后的天气与今天完全一样**。
  - 用途：这是"**no-brainer / 无技巧预报**"，用它来衡量模式究竟比"什么都不做"好多少。图中蓝线（persistence）远高于红线（模式），差距即为**预报技巧（skill）**。

**Met Office 曲线（Slide 77–81）**
- 指标：**东北大西洋区域地面气压的均方根误差（mb）**，分别对 1–5 天预报绘制。
- 关键解读（幻灯片 Notes）：
  - 1954 年的 Met Mag 周年刊指出，此前 10 年**人工制作的 24 小时预报几乎没有改进**，更长时效则毫无技巧；
  - 1967 年 NWP 的 T+24 技巧与之相当；
  - 这一技巧水平被 NWP **在 1985 年延伸到 2 天**（用了约 **9 年**），**1996 年延伸到 3 天**（约 **10 年**），后续同样约 **10 年、13 年**再各延伸一天。
  - **粗略规律：每十年左右，预报技巧向前延伸约一天。**
- 改进的来源（幻灯片 Notes 列举）：**更细的分辨率、更大的计算域、更长的预报时效、更好地利用观测、对大气过程更好的表达**——而这一切都由**计算机速度与内存的增长**所使能。

### 2.8 为什么好预报会变坏：三大原因

#### Reason #1：对大气当前状态的认识不完美（Imperfect knowledge about current state of atmosphere）

四个子原因（幻灯片 Slide 48）：
1. **Data voids（资料空洞）** —— 海洋、无人区、南半球。虽可用卫星填补，但**卫星数据的质量与分辨率不同**。
2. **Interesting weather in between observing locations** —— 有趣（重要）的天气发生在观测点之间。
   - **因果链**：初始场没抓到这个特征 → 模式在后续积分中**很难自发生成（spontaneously generated）**这个特征 → 预报漏掉了它。这是 1987 年大风暴漏报的机制之一。
3. **Instrument sensitivity and errors** —— 尤其是卫星：**卫星并不直接观测温度**，它测的是**辐射率（radiances）**，再通过各种**经验关系（empirical relationships）反演**出温度等量，因此带有敏感性与误差。
4. **No observations of important quantities（关键量根本没有观测）** —— 本讲最重要的例子：**云内微物理**。

**云内微物理的观测缺口（老师在芬兰的例子，transcript 详述）**
- 场景：老师在芬兰的办公室对面楼上有个**球罩（radome）**，里面是**天气雷达**——雷达本体是个碟形发射天线，球罩只挡风雨，不阻挡电磁辐射。
- **雷达能测什么**：**降水尺度粒子（precipitation-sized particles）**。每发射一束波，就采样大气中的一个小体积（课件上画成一个个小方块）。
- **雷达得到的只是一个"整体量（bulk measure）"** —— 大致相当于该体积内降水尺度凝结水物质的密度。
- **云内真实情况**（来自研究飞机穿云拍摄）：**液态水滴 + 各种形状/尺寸/取向的冰晶**混合共存——有**片状晶（plates）**、有**枝状晶（dendrites）**，还有**像小方糖一样、由许多冻结水滴粘连成团的霰（graupel）**。
- **结论**：我们**不知道那些小方块里到底发生了什么**。而"云里有什么"恰恰**决定这块云是下雨、下雪，还是什么都不产生**。我们既没有观测，也不可能对每一块云都飞一次研究飞机 → **只能做假设与猜测** → 直接引出 Reason #2 的参数化。

#### Reason #2：模式不完美（Imperfect Computer Model）

两个子原因：
1. **需要更快、更强的计算机以支持更多格点**
   - **因果链**：想预报的点越多、点越密（分辨率越高）、想捕捉的特征越小 → 需要的算力越大；但**24 小时预报必须在 24 小时内算完**（否则无用）→ **算力上限直接限制分辨率上限**。
   - 缓解因素：**Moore's law**（计算速度与存储的增长）＋ 更好的**数值方法（numerical methods）**。
2. **对物理过程理解不足** → **Parameterization（参数化）**

**Parameterization（参数化）—— 本周必考概念**
- 定义（幻灯片 Slide 54）：
  - **Simplifies physical processes that we don't fully understand or don't have measurements of**（简化我们尚未完全理解、或没有测量的物理过程）
  - **Calculates processes occurring on scales smaller than grid boxes**（计算小于格距尺度上发生的过程，即"次网格尺度"过程）
- 在方程中的体现：那些被笼统写成 **Q** 的项，**只是占位符（generic placeholders）**，并**不代表第一性原理的物理**。
- 被参数化的典型过程（transcript）：
  - **Turbulent heat and moisture transfer（湍流热量与水汽输送）**
  - **Precipitation（降水 / 云微物理）** —— 我们不追踪云里的每一颗雨滴
  - **Radiation（辐射）** —— 我们不追踪进入地球大气的每一个光子（"That would just be too much."）
- **必须记住的态度**："Parameterization is essential, **but it's a simplification, no doubt**." 没有参数化，就**来不及**产出预报。
- **Kahoot 陷阱**：参数化**不**负责"account for poor quality observations"——观测的质量把关属于**资料同化系统**。

#### Reason #3：混沌（Chaos）

**人物：Prof. Ed Lorenz**（麻省理工，老师本科时的老师之一）

**发现经过（transcript 完整故事）**
- 1960 年代，Lorenz 跑的是**极简化的大气模式**——**不是**本课讲的 5 方程 5 未知量版本，而是 **3 个方程、3 个未知量（x, y, z）**的版本。
- 当时计算机**占了半个演讲厅那么大**、而且**很慢**。为了回看某段已经跑过的结果，他会**中途停机**，从**打印输出（printout）**上抄下 x, y, z 的值，再重新输入、从那点重启模式。
- 结果：**有时得到完全不同的结局**。他反复排查——不是编码错误，也不是输错数——却找不出原因。
- **真相**：计算机**内存里保存 6 位小数（如 5.123456）**，而**打印输出只有 3 位小数（5.123）**。重启时输入的其实是**一个不同的数**——差别**小到无法察觉（imperceptibly small）**。
- **演化过程**（图上解读）：两条曲线（一实线一虚线）起初几乎重合；到**第 7 个时间周期**左右开始**分岔（diverge）**；到**第 10 个周期**左右已完全不像——**仍具有相同的统计结构，但完全不重叠、彼此也不再跟随**。

**概念表述**
- **Sensitive dependence on initial conditions（对初始条件的敏感依赖）**，俗称 **butterfly effect（蝴蝶效应）**。
- **Small differences in initial conditions will lead to large differences later.**
- **推论**：我们**无法做确定性预报（deterministic predictions）**，因为我们**不可能把大气每一点的状态知道到无穷位小数的精度**。
- 论文年份：**1963**（极著名）。

**可预报性上限（predictability limit）—— 必背数字**
- Lorenz 后续追问：**如果**我们对全球急流有**完美的初始条件**，大尺度天气预报能做多久才变得不可用？
- 课堂上同学猜了"两天""六天"，**正确答案是 TWO WEEKS（约两周）**。
- 后续几十年的计算证明 **Lorenz 的估计非常准（spot-on）**。
- **注意限定**：这是**大尺度特征（如急流、大型气旋）**的上限，**不是**小尺度现象（云、雷暴）的上限——后者短得多。
- **实务对照**：ECMWF 对急流有时能做到 **10 天**的像样预报，**再往外就很勉强**；本课演示的 **5 天预报**质量相当好。
- **老师的强烈警告**：某些网站号称提供**一个月预报**，甚至"预报你一年半后婚礼那天的天气"——"**That's a bunch of BS. Crap. Don't believe it.**"
- **我们离这个理论极限还很远**（"We're not at this limit yet"），仍有很大改进空间，但只能是渐进的。

**Kahoot 考点**：Even with a perfect model and perfect initial conditions, the theoretical limit for weather prediction is **three weeks** → **FALSE**（是 **two weeks**）。

#### 汇总：Dave sez

> "Given all these limitations, we have **no right** to do so well in forecasting the weather! What other discipline forecasts the future with as much success as meteorology?"

老师的总结逻辑（Slide 74–76）：
- **In principle, weather forecasting is easy**：初始状态（观测）＋ 大气定律（物理）。
- **In practice, it is more difficult**：初始场误差 ＋ 近似（参数化）＋ 混沌。
- **结论**：考虑到未知的初始状态与求解方程所用的种种近似，我们竟然能把天气预报做得这么好，**是了不起的人类成就**。

### 2.9 反面教材：Michael Fish 与 1987 年 10 月大风暴

- **Michael Fish**：BBC 多年的天气预报员，因**1987 年 10 月**未能预报出穿过**英吉利海峡（English Channel）**的风暴强度而"名垂青史"，被视为**史上最糟预报之一**的代言人。
- **后果**：摧毁了 **Kew Gardens** 大量**古树**；在**英国与法国两侧**都造成人员死亡与大量破坏。
- **老师为他辩护的三条**（正好对应三大失败原因，是极好的案例串联）：
  1. 1987 年的预报水平**本来就远不如现在**；
  2. **关键位置缺少观测**（对应 Reason #1，data voids）；
  3. 当时的数值模式**分辨率不够高**，**捕捉不到**这种风暴（对应 Reason #2，算力/分辨率）。

### 2.10 气旋与反气旋：定义与基本判读

**定义（两半球通用）**
- **Cyclone（气旋）= low-pressure system（低压系统）**
- **Anticyclone（反气旋）= high-pressure system（高压系统）**

**旋转方向（Slide 95）**
| | 北半球 NH | 南半球 SH |
|---|---|---|
| **Cyclone（低压）** | **逆时针 counterclockwise / anticlockwise** | **顺时针 clockwise** |
| **Anticyclone（高压）** | **顺时针 clockwise** | **逆时针 counterclockwise** |

- **老师的建议**：可以死记，但更好的是**理解它来自科里奥利力（Coriolis force）在两半球方向相反**。

**等压线与风速**
- "When **isobars**（lines of constant pressure）are **closely packed**, winds are **strong**."
- **机制来源**：这不是经验规律，而是**直接来自动量方程中的气压梯度力项 −(1/ρ)∇p**。等压线（或等高线）挤得越密 → ∇p 越大 → 风被加速得越强。老师强调"we know **now why** that's the case"——第二节课回头用第一节课的方程解释了这个观察。
- 反过来：**低压中心附近气压梯度小 → CALM（静风）**。课件上多张天气图都标注了低压中心的 "CALM" 与外围的 "strong pressure gradient → strong winds"。

**两类气旋的能量来源对比（必考）**
| | Extratropical cyclone（温带气旋） | Tropical cyclone（热带气旋） |
|---|---|---|
| 位置 | 中纬度，**tropics 之外**（extra-tropical 即"热带之外"） | 热带 |
| 别名 | 温带低压、风暴（Met Office / 爱尔兰气象局命名的风暴就是这类） | hurricane（大西洋/东太平洋）、typhoon（西太平洋）、cyclone（印度洋） |
| **驱动机制** | **温度梯度（temperature gradient）/ 斜压性**，与**急流（jet stream）**的强风带相联系；能量来自急流 | **潜热释放（latent heat release）** |
| 结构模型 | Norwegian cyclone model，有锋面 | 无锋面，暖心 |

**温带气旋的生成机制链条**
1. 地面存在**极锋（polar front）**——冷暖气团的分界；
2. 极锋**上方高空**是**极锋急流（polar front jet stream）**（老师纠正：急流在更高处，锋在地面）；
3. **急流是不稳定的（unstable）**，其上会**发展出波动（waves）**；
4. 这些波可以**从小扰动增长**，成为**大型温带气旋 / 风暴**。

### 2.11 挪威气旋模式（Norwegian Cyclone Model）—— 四阶段演化

**来历**：由 **Jacob Bjerknes**（Vilhelm Bjerknes 的**儿子**）与 Bergen（挪威卑尔根）的同事在**上世纪初**共同发展。
> 幻灯片 Notes 的 Fun fact：告诉我们"如何做基于物理的天气预报"的是父亲 Vilhelm；提出气旋概念模型的是儿子 Jacob。

**图上有两套场**：上半部分是**海平面气压 + 各类锋面**；下半部分是**等温线（isotherms）**，分隔暖空气与冷空气。

**阶段 1：初始波动（incipient wave）**
- 极锋上出现**小小的涟漪（little ripples）**，**小振幅扰动**，气压上可能**只有几毫巴（a few millibars）深**。
- **关键**：它**带有一个环流（circulation）**——北半球是**逆时针**。
- 结果：低压**东侧**，**暖空气自热带向北输送**；低压**西侧**，**冷空气自极地/北极向南输送**。
- 这个环流**扭曲了等温线**，产生温度场的扰动（deformation of isotherms）。

**阶段 2：开放波（open wave）与增强**
- 气旋开始**加深、风增强**，环流开始**卷绕成螺旋（wrap up into a spiral pattern）**。
- **暖锋（warm front，红线 + 半圆）**：暖空气被**抬升越过**暖锋。
- 结果：**地面暖空气所占的面积被缩小（reduced in surface area）**；冷空气开始**包裹（wrapping around）**低压。
- 等温线上出现**更大的扰动**——一个**暖空气的尖峰（peak of warm air）**向北突出。
- 这时候**存在完整的暖区（warm sector）**——夹在**暖锋与冷锋之间**。

**阶段 3：锢囚（occlusion）**
- **冷锋（cold front，蓝线 + 三角）移动速度快于暖锋**，最终**追上暖锋**，形成 **occluded front（锢囚锋）**。
- **occluded = closed up（闭合、被堵住）**。
- 结果：低压中心**完全被冷空气包围**，**大部分暖空气已被抬升到高空**，地面的**暖区变窄（warm sector narrows）**。

**阶段 4：成熟（mature / fully occluded）**
- 完全卷绕的低压系统；**锢囚锋用紫色、三角与半圆交替**表示。
- 这代表**风暴的顶峰（peak of the storm）**。

**南半球：镜像（mirror image）**
- **原理相同，图形上下镜像**。
- 两条物理原因：
  1. **最暖的空气在赤道/热带一侧**——所以南半球的扰动是**从北方拉来暖空气**（对习惯北半球的人来说很别扭）；
  2. **科里奥利力方向相反** → 环流方向相反。
- **云型判读**：北半球看到的是标准的**逗号形（comma-shaped）**云系；南半球看到的是**倒逗号（inverted comma）**——**逗号的"头"在下方，"尾"向上延伸**。

**理想化气旋动画（Schultz and Zhang 2007，Slide 96）**
- 画的是 **850 hPa 高度场、温度场、风羽（wind barbs）**。
- 黄色 = 气压场；绿线 = 温度（南侧暖）；风羽表示风向风速。
- 演化：起初**甚至还不是闭合低压**，只是气压场上的一个**弱区（weakness）**，风已经在气旋式（cyclonically，逆时针）绕它吹——东侧**南风（southerlies）**、西侧**北风（northerlies）**。
- 随后：低压**加深**（风羽上的横杠变多 = 风变强）→ **卷绕 → 锢囚** → 最暖空气被挤成一条**窄脊（ridge）**、像一小撮暖舌向低压中心突入。
- **同时**：其**下游/相邻区域发展出一个反气旋**；冷空气**在低压与高压之间被从极地拖曳南下**；高压也随之增强、其环流加强。
- 教学要点：**气旋与反气旋是成对、串联出现的**——中纬度天气就是"低压过境 → 高压过境 → 下一个低压"的序列。

### 2.12 实例：气旋与反气旋如何改变你脚下的天气

#### 案例 A：2025 年 2 月 3–6 日，Manchester（Whitworth Observatory 实测 + 卫星 + 天气图）

这是老师提前提醒学生留意的一段真实天气，用来**把概念模型与仪器记录对上号**。序列是：**温带气旋（低压）过境，随后是温带反气旋（高压）**。

| 时间 | 天气图/卫星上的位置 | Manchester 的实测表现 |
|---|---|---|
| **0600 UTC 3 Feb** | **暖锋的尖端（tip of warm front）**分析在曼彻斯特**略北**处经过；低压中心位于**冰岛上空**（卫星图上因天黑看不清），但**冷锋从低压中心一路向南延伸**清晰可见 | **轻微风向转变**：从 **200°（西南偏南）** 转为 **150°–180°（东南偏南到正南）**；升温既有**白昼加热**贡献，也有**气团更替**贡献；因为只擦到暖锋尖端，**降水很少** |
| **1200 UTC 3 Feb** | 处于**暖区内部（inside the warm sector，冷暖锋之间）** | **整夜温度维持高位（8 °C）**——暖区的典型特征：夜间不降温 |
| **1200 UTC 4 Feb（冷锋于 1300 UTC 后不久过境）** | **冷锋过境** | **温度骤降**几度、**短促一阵雨（short burst of rain）**、随后转凉；**风向突变且不持久**；卫星上对应**明显云带与降水** |
| **1200 UTC 6 Feb** | 气旋东移离开，**反气旋（高压）**坐镇头顶 | **晴空、日照充足、温暖、风轻（light winds）** |

**关键的仪器判读技巧（Slide 104 + transcript）**
- **太阳辐射曲线近似一条抛物线（almost a parabola）→ 说明几乎无云**。
  - 机制：无云时到达地表的太阳辐射只随**太阳高度角**平滑变化，画出光滑抛物线；有云则出现锯齿状扰动。
  - 图上用的是**直接辐射 + 散射辐射（direct and diffuse solar radiation）的合量**。
  - **注意伪信号（artifacts）**：曲线上一些异常来自**周围建筑物对辐射表的反射**。
- **温度曲线**：Whitworth Observatory（黑线）呈现**漂亮、陡峭的抛物线型日变化**；而**街道（the street）**上的升温**更加陡峭**——因为太阳一出来就加热**沥青路面（asphalt）**，路面**加热大气的效率非常高**。这是**城市地表性质 → 感热通量 → 气温**的直观因果链。
- 数据源：`whitworth.cas.manchester.ac.uk`（曼大自有观测站）；天气图 `wetter3.de`；卫星 NOAA GIBBS / sat24。

#### 案例 B：2025 年 2 月 17 日（讲课当天午夜）的天气型
- **500 hPa 图**：等值线代表 **500 hPa 位势高度**，北侧高度低（低压），线条**密集处 = 急流更强**；**颜色 = 850 hPa（离地约 1.5 km）温度**，南低纬为红（暖）、高纬为蓝绿（冷）。
- **核心判读原则**（承接上周）：**急流是冷暖空气的边界，冷空气在急流的极地一侧**。当天急流分成**两支（two bands）**。
- **五天预报检验**：把 **2 月 12 日 0000 UTC 起报、验证于 2 月 17 日 0000 UTC** 的预报与**实况**叠加对比：
  - **两个低压都抓住了**，基本形态一致；
  - 差别：曼彻斯特一带**实况在 1.5 km 高度上略更冷**；南侧**实况比预报略暖**；**脊（ridge，急流向极地的隆起）的振幅**——**预报没有做得像实况那样窄而尖锐**。
  - 结论：五天出去还能抓住两个独立风暴的形态，**对比 1949 年连北美中部一个巨大低压的 24 小时预报都做不好**，进步惊人。
- **地面图**：一个**占据整个大西洋的巨型低压**，**暖区非常窄**，**已完全锢囚（fully occluded）**且**已经这样"坐"了好几天**。
  - **老师的解释**：这个低压与欧洲大陆上高压的**尺度都很大**，这**减慢了系统的演变** → 天气型**非常缓慢地演变**，所以他**没法用当天的实图演示气旋的完整生命史**。
  - 但仍能读出基本特征：低压中心**前方（东侧）**有暖空气北上（暖锋与锢囚锋之前），中心附近有冷空气；温度对比不大（约 **12 °C vs 15 °C**），因为气团都来自**北大西洋**，海洋使温度**相对稳定均一**。
  - 风场：高压周围风**自东而来**，低压**东侧**为**南来的暖平流**。

#### 案例 C：2023 年 2 月 18–20 日 / 2024 年 2 月 20 日的天气图序列
- 一系列 6 小时间隔的 `wetter3.de` 地面图（0600 / 1200 / 1800 / 0000 UTC 逐时次），反复标注：
  - **低压中心 L** 附近 —— **CALM（静风）**；
  - 低压外围等压线密集 —— **strong pressure gradient → strong winds**；
  - 曼彻斯特位置随系统移动**先后经历 warm wind（暖平流）与 cold wind（冷平流）**；
  - 2023 年 2 月 18 日图上标出的具体温度对比：**−1 °C vs 16 °C**（跨锋面的巨大温差）。
- 教学目的：训练**"给你一张天气图，说出接下来会发生什么"**的能力。**中纬度气旋总体自西向东移动，锋面依次扫过各地**。

#### 案例 D：2021 年 2 月 13 日北美寒潮 —— 反气旋不都是好天气
- 天气图（1200 UTC 13 Feb 2021，单位为**华氏度 °F**）：一个**来自加拿大**的**反气旋（高压）**南下贯穿美国中部，越过 **Front Range / Rockies**。
- 后果链条：
  - **墨西哥湾岸（Gulf Coast）气温降到 32 °F = 0 °C**；
  - 志愿者不得不上海滩**把海龟（sea turtles）搬走**，以免冻死；
  - **水管爆裂**（南得州冬季极少出现冰点温度，管道无防冻设计）；
  - **电网需求暴增**，部分地区**停电（blackouts）**。
- **要记住的原理**：反气旋**大多数时候**（尤其夏季）带来**晴空、暖和的好天气**；但它也能带来**晴空 + 极端冷空气**，后果可以极具破坏性。晴空本身还会通过**夜间强辐射冷却**加剧低温。

### 2.13 观测 vs 预报：老师明确点名的考试易错点

> "**I know that many students will confuse [this] on the test.**"

- **Observations（观测）= 已经发生或正在发生的真实天气**。
  - 载体：**卫星影像（satellite imagery）**、**雷达影像（radar imagery）**、带有**站点模式（station models）与风羽（wind barbs）**的地面图。
  - 这些是**对大气的直接观测**。
- **Forecast（预报）= 未来的东西，来自预报模式**。
- **陷阱**：模式可以输出**看起来像卫星图、雷达图的产品**，但那些是**预报产品**，不是观测。
- **术语纪律**：谈论**已经发生的事**时**不能称之为 forecast**；谈论**未来**时**不能称之为 observation**。可以"看过去的预报"，但那时讨论的对象仍是预报。

### 2.14 网络天气工具（老师推荐清单）

| 类型 | 网站 / 工具 | 属性 | 要点 |
|---|---|---|---|
| **地面天气图** | **wetter3.de** | 观测 + 预报 | 用的是**德国气象局 DWD** 的图。老师**偏爱 DWD 而非 Met Office 图**，原因：DWD 的锋是**人工分析（hand-analysed）**，简洁、易懂、**更像挪威气旋模式**；Met Office 图**没有观测数据叠加**且用**自动锋面分析（automated fronts）**，"can be pretty ugly" |
| **卫星** | **sat24.com** | 观测 | 常见展示是**可见光（visible，反射的太阳光）与红外（infrared）的混合**（因为日出线两侧不同）；可以切换为**纯可见光**或**纯红外** |
| **雷达** | **netweather.tv/live-weather/radar/** | 观测 | 雷达测的是**降水**，**不是云**——包括云内和**云底以下**的降水；显示的是英国与爱尔兰多部雷达拼接（**mosaic**）成的单幅图 |
| **闪电** | **blitzortung.org** | 观测 | 全球闪电定位，可放大到本地；讲课当天英国附近少，但**土耳其、北非、葡萄牙以西**有雷暴活动 |
| **本地点预报** | **Met Office** 网站（postcode forecast） | 预报 | 老师留了个开放问题："**他们是怎么做出邮编级（point）预报的？**" |
| **自建预报系统** | **ManUniCast.com**（Manchester University Forecast） | 预报 | 曼大 School of Earth, Atmospheric and Environmental Sciences 开发的**社区天气与空气质量预报教学门户**；**免费**；有 **Apple App**（老师自嘲当年没钱做 Android 版）；驱动数据来自**美国**（"as long as they continue to provide that"） |

**ManUniCast 能看什么**（幻灯片）：European Weather、UK Weather、**UK Air Quality**（例：**22 小时预报的地面 SO₂ 混合比，验证于今日 1600 GMT**）、**Meteogram（气象要素时间序列图）for Manchester**、多地点的 **Skew-T–log p 探空图**。
- 单位换算备注（幻灯片 Notes）：**350 µg m⁻³ = 122 ppb；125 µg m⁻³ = 44 ppb**（SO₂）。

**过去—现在—未来的工具映射（Slide 119，极好的框架图）**
```
        PAST                    NOW                    FUTURE
   |--------------- Observations ---------|------ Forecast ------|
     surface maps / satellite / radar        forecast model output
```

### 2.15 野外天气安全（Weather Safety in the Field）

> 背景：本课程会有野外实习；若继续读地学，二、三年级乃至毕业论文都会做野外工作。
> 老师原话：**"This lecture could save your life."**
> 指定阅读：Olivia Heard（三年级 BSc Geology/Geography）的 *Mountain Safety: Student Ambassador Insights* —— 她周末外出，天气骤变，**帐篷被吹丢、被困野外、手机无信号**；因为记得课上讲的原则，最终有惊无险。

#### A. 雷电（LIGHTNING）

**英国的伤亡统计（Elsom and Webb 2017；另见 Elsom & Webb 2014）**
- 平均每年 **2 人死亡**、**29 人受伤**。
- 被击中的典型场景：**树下**、**山上**、**城市环境**（占相当比例）、**公园运动/户外休闲时**、**水面上**。
- 老师的评论：英国雷电不算频繁，但**一旦发生，就有人面临受伤或死亡的风险**。

**闪电形成的必要条件（Necessary Conditions for Lightning Formation）—— 必背**
1. **Updraft in a cumulus cloud**（积云中的上升气流）
2. **Below freezing at cloud top**（云顶温度低于冰点）
3. **Mixed-phase cloud（混合相态云）**，同时含有：
   - **Graupel（霰）**——软的、不规则的雹粒
   - **Ice crystals（冰晶）**
   - **Supercooled liquid water（过冷水）**

> **机制理解**：起电依赖**霰粒与冰晶在过冷水存在下的碰撞（碰撞起电）**，而这需要**强上升气流把水滴带到冰点以下**。所以"三条件"实际上是**电荷分离机制**的必要前提。

**要看的云**（transcript）：**不断向上发展的积云塔（cumulus towers）**——顶部呈**花椰菜状（cauliflower-shaped）**且**持续长高**。区别于晴天那种**蓬松的淡积云（fair-weather cumulus）**。一旦看到垂直发展，就要开始考虑雷电风险。

**闪电即将发生的征兆（When Lightning is Imminent）**
- **头发竖起（hair stands on end）**
- **火花、电放电（sparks, electrical discharges）**
- **St. Elmo's fire（圣艾尔摩之火）**
- **听到静电放电声**

> **老师亲身经历（transcript）**：在 **Colorado** 徒步，整个上午爬到**科罗拉多第二高峰**顶，坐下吃午饭，把三明治递给同伴时，**指尖之间跳出一个火花**——而当时**云还不低**。他立刻判断"我们得走"，**连午饭都没吃就马上下撤**。原理：**一旦出现这些现象，你已经在被充电了**，下一次落雷可能就在你这儿，**绝不能留下来看结果**。
> 附带的另一条教训：科罗拉多夏季徒步的经验法则是"**中午前登顶、之后下山**"，因为**午后雷暴几乎是常态**；而他们那天 **11:30 就登顶了，规则仍然没能救他们**——说明经验法则**不是保证**。

**幻灯片上的真实事故**：1975 年 8 月 20 日，**Sequoia National Park 的 Moro Rock**，1 人死亡、8 人受伤（伤最重的是摄影师），全部来自同一个大家庭；当时**正在下冰雹**，他们在顶部——**比停车场高 300 英尺、水平距离 1/3 英里**。

**The 30–30 Rule（30-30 法则）—— 必背**
- **大多数被雷击致死的人，是在风暴的很早期或很末期被击中的。**
- **闪光（flash）与雷声（bang）之间的时间若为 30 秒或更短 → 立刻寻找掩蔽。**
- **最后一次雷声之后，再等 30 分钟**才恢复户外活动。

**为什么"早期"最危险（transcript 的机制解释）**：**总得有某个地方成为第一次落雷点**，那个地方可能就是你。而此时你所在地**还没开始下雨**、还没有任何雷暴要放电的信号，**人们根本没意识到自己有风险**；相反，**大雨已经下起来时人们自然会去避雨**。
- 老师的实操建议：他从没数到过 30——"我常常只数到五或十就响了"。所以更简单可靠的规则是 **"When thunder roars, go indoors."**（**只要能听见雷声，你就已经处在下一次落雷的风险范围内**，因为雷声就是闪电的可听表现。）

**Lightning Safety Precautions（四条）**

1. **避免危险情境（Avoid dangerous lightning situations）**
   - 留意**快速发展的雷暴**征兆（长高的积云塔）；
   - 留意**你所在区域的其他风暴**（用天气 App 看雷达和闪电定位）；
   - **给自己留出足够时间**到达安全地点，**不要在条件恶化时让自己离安全地点更远**。

2. **安全场所（Safe places）**
   - **住宅或经常有人使用的建筑（四面有墙）**；进入后**避免接触电线、电话线、管道系统**（不要洗澡、不要用固定电话）。
   - **有金属顶的车辆（vehicle with a metal top）** —— 构成 **Faraday cage（法拉第笼）**；**只要不接触车的金属框架**，即使被击中也无恙。

3. **不安全场所（Unsafe places）**
   - **各类无墙棚屋**：避雨棚、遮阳棚、海滩棚、高尔夫棚、野餐棚；
   - **帐篷（tents）**——**能挡雨但挡不了雷**；
   - **横跨超过 100 码的开阔地**；
   - **树木、电杆、任何高耸物体**（尤其是孤立的树）。

4. **NO PLACE OUTSIDE IS SAFE DURING THUNDERSTORMS!（雷暴期间户外没有任何安全的地方）**
   - **在预期出现午后雷暴之前就下山**；
   - **林中小径只比暴露的小径"略微"安全（marginally safer）**；
   - **卸下背包**以便更快撤离（背包可以事后再取）；
   - **洞穴、岩檐、凉亭只能挡雨，挡不了雷** —— 电流**可以从落雷点沿地面传导到你身上**（地电位差 / side flash）。

**水上（On the water）**
- **立刻上岸**。
- **雷击曾在水面上 30 码（yards）以外造成人员伤亡** —— 因为电流沿水面传导。
- 若在皮划艇/独木舟上，除雷击外还有**风起浪打**的风险。

**First Aid for Lightning Victims（雷击急救）—— 逐条**
- **呼叫救援（Call for help）**。
- **不要制造更多伤员** —— 不要让施救者暴露在持续的雷击危险中。
- **触碰雷击伤者是安全的（It is safe to handle a lightning victim.）** —— 人体**不会残留电荷**。这是最重要的一条常见误解澄清。
- **检查呼吸与脉搏** —— 必要时**实施 CPR 和/或人工呼吸**。
- **检查其他伤情**：**骨折**；**闪电的入口与出口点**（常在**手指、脚趾、皮带扣、首饰**处）。
- **疑似脊柱损伤者不要移动**。
- **防止休克**：盖毯保暖、保持干燥、**不要让伤者到处走动**。
- **即使只是被震晕或看似无伤的人也要送医**接受正规检查。

#### B. 洪水（FLOODING）

**关键数字（Slide 146）—— 必背**
| 水深 | 后果 |
|---|---|
| **15 cm（6 inches）** | 足以**把人冲倒**（尤其水在流动、底下又滑时） |
| **30 cm（1 foot）** | 足以**浮起一辆小汽车** |
| **45–60 cm（约 0.5 m，1.5–2 feet）** | 足以**浮起 SUV 或厢式车** |

**机制**：**轮胎是有浮力的（The tires are buoyant）**。人们以为"这可是上千公斤的金属，抓地力很强"，但**浮力一旦抵消足够重量，轮胎就失去摩擦力**，车就被水流带走。
- 幻灯片引用的真实事件：2020 年 8 月英国暴风雨，**医院停车场的车被水漂走**。
- 过河/涉水提示：**如果你知道过一条溪流时水流对你的作用有多强，就该明白大范围积水更危险**。

**口号（两条必背）**
- **"When thunder roars, go indoors."**（雷声一响，赶紧进屋）
- **"Turn around. Don't drown."**（掉头别淹）

**通用野外天气安全清单（Slide 148）**
- **出发前了解预报（Be aware of the forecast before you go）**；
- 若有手机信号，**准备好相应的 App 与雷达、闪电网页书签**；
- **了解针对具体天气的安全规则**；
- **制订安全计划（safety plan）** —— 包括**万一队伍走散怎么办**、**你的安全地点在哪、怎么回去**。

---

## 三、公式与图表

### 3.1 大气五方程逐项解析

> 再次强调：**不要求记数学形式**，但**要求知道有这五个方程、各管什么、每一项的物理含义**。

**(1) Ideal Gas Law（理想气体定律）** —— 联系气压、温度、密度

$$p = \rho R T$$

| 符号 | 含义 |
|---|---|
| $p$ | 气压 pressure |
| $\rho$ | 密度 density |
| $R$ | 理想气体常数（干空气气体常数） |
| $T$ | 温度 temperature |

- 等价形式：$pV = nRT$（$V$ 为体积）。
- 作用：**这是唯一的诊断方程（不含时间导数）**，把三个状态变量绑在一起，使方程组闭合。

**(2) Conservation of mass — water vapour（水汽守恒）**

$$\frac{dq}{dt} = E - C$$

| 项 | 含义 |
|---|---|
| $q$ | **water vapour mixing ratio（水汽混合比）**（上周概念） |
| $dq/dt$ | 水汽混合比**随时间的变化率** |
| $E$ | **evaporation rate（蒸发率）** —— **正号**，向大气**加入**水汽 |
| $C$ | **condensation rate（凝结率）** —— **负号**，从大气**移除**水汽 |

- 物理叙述：**哪里蒸发，哪里大气得到水汽；哪里凝结，哪里大气失去水汽**；两者之差就等于水汽的变化率。老师评价："Very simple."

**(3) Conservation of mass — dry air（干空气质量守恒 / 连续方程）**

$$\frac{d\rho}{dt} = -\rho\,\nabla\!\cdot\!\mathbf{v}$$

| 项 | 含义 |
|---|---|
| $\rho$ | 干空气分量的密度 |
| $d\rho/dt$ | 密度的时间变化率 —— **通常很小，常被忽略** |
| $\nabla\!\cdot\!\mathbf{v}$ | **3D 速度场的散度（divergence of the 3D velocity field）** |

- **3D velocity 的三个分量**：东西向、南北向、上下向。
- **最重要的物理直觉（老师原话）**：
  - **如果我在近地面把空气"汇聚（bring air together）"进来，这些空气只有一个地方可去 —— 向上。**（低层辐合 → 上升运动 → 成云致雨）
  - **如果我让空气辐散（diverge, spread out），就必须有空气下沉来补充它。**（低层辐散 → 下沉 → 晴空）
- 这条直觉是理解**气旋（辐合上升，多云雨）与反气旋（辐散下沉，晴空）**天气差异的根本。

**(4) Thermodynamic energy equation（温度如何变化）**

$$\rho c_v \frac{DT}{Dt} + p\,\nabla\!\cdot\!\mathbf{v} \;=\; Q_{\text{sensible}} + Q_{\text{latent}}$$

| 项 | 含义 |
|---|---|
| $c_v$ | **空气的定容比热（specific heat of air at constant volume）**（幻灯片 Notes 明确） |
| $DT/Dt$ | 温度随时间的变化率 |
| $p\,\nabla\!\cdot\!\mathbf{v}$（含散度项） | **绝热膨胀与压缩（adiabatic expansion and compression）** —— 上周讲过：**空气上升 → 膨胀 → 冷却**；因为这是**大气运动内禀的（implicit to the motions）**，所以放在等号左边 |
| $Q_{\text{sensible}}$ | **感热加热率（sensible heating rate）** —— 例：冷空气吹过相对温暖的地面，**热量从地面传给大气** |
| $Q_{\text{latent}}$ | **潜热加热率（latent heating rate）** —— **凝结放热（Q 为正，增温）**；**蒸发吸热（Q 为负，冷却）** |

- **符号约定要点**：加热 → $Q>0$；通过蒸发移走热量 → 冷却效应 → $Q<0$。
- 这两个 **Q 就是被"参数化"的典型对象**（见 2.6/2.8）。

**(5) Momentum equation（风如何变化）**

$$\frac{D\mathbf{v}}{Dt} + 2\boldsymbol{\Omega}\times\mathbf{v} \;=\; -\frac{1}{\rho}\nabla p \;-\; g\,\mathbf{k} \;+\; \mathbf{F}_{\text{dissipation}}$$

| 项 | 含义 | 老师的讲法 |
|---|---|---|
| $D\mathbf{v}/Dt$ | **三维速度的时间变化率**（两个水平分量 + 一个垂直分量） | 我们要预报的对象 |
| $\boldsymbol{\Omega}\times\mathbf{v}$ | **Coriolis force（科里奥利力）**；$\Omega$ 是**地球自转速率**，与速度场做叉乘 | "因为我们生活在一个**旋转的行星**上，这一项**必须存在**"；它**静态地**由速度与自转率决定，所以放在左边 |
| $-\dfrac{1}{\rho}\nabla p$ | **3D 气压梯度力（pressure gradient force）** | **这就是"等压线/等高线密集处风大"的数学出处**——"where the pressure gradient is tight, that will accelerate the wind"。$\nabla$（倒三角）= 梯度算符 |
| $-g\,\mathbf{k}$ | **重力（gravity）**，$\mathbf{k}$ 为**垂直向上的单位向量** | 把大气**往下拉**，**与向上的垂直气压梯度力相抗衡**（→ 静力平衡） |
| $\mathbf{F}_{\text{dissipation}}$ | **耗散项 / 黏性项（dissipation, viscosity）** | 可理解为**摩擦**。黏度排序：**机油很黏 > 水居中 > 空气最不黏**；但仍必须计入 |

**方程组闭合性**：**5 个方程、5 个未知量（state variables）** —— 这就是我们要预报的状态变量。模式中还有其他表达式，但**做基本大气预报只需要这五条**。

### 3.2 从微分方程到有限差分（finite differences）

- **问题**：计算机不理解微分方程。
- **做法**：把微分方程改写为**有限差分形式** —— 在一张**格点网（grid of points）**上，用**相邻格点之间的差商**近似导数。
- **闭环**（本讲最优雅的一环）：
  ```
  不规则分布的观测
        │  data assimilation
        ▼
  规则的三维全球网格（= 初始条件）
        │  finite-difference 形式的五方程逐步积分
        ▼
  未来时刻的网格化场（= 预报）
  ```
- **误差的注入点**（对应三大失败原因）：**网格化过程丢失细节 → Reason #1**；**格距限制 + 次网格过程参数化 → Reason #2**；**初值的微小误差随积分放大 → Reason #3**。

### 3.3 预报流程框图（Slide 41–44）

```
   全球观测（雷达、卫星、探空气球、地面站……）
                │        [提供初始状态]
                ▼
        COMPUTER FORECASTS
   （物理定律 + 对大气如何运作的近似 → 数值预报）
                │
                ▼
        HUMAN FORECASTER
   （评估质量、修正、增强、解释模式输出）
                │
                ▼
             USERS
   （私营企业、航空、农业、公众 —— "This end user is you!"）
```
- transcript 补充：**某些类型的预报是全自动的**，但对**更具体的用户需求**，通常需要**把人放在回路里（human in the loop）**。

### 3.4 ECMWF 500 hPa / 850 hPa 天气图的判读方法

**图上有两套信息**：
1. **等值线 = 500 hPa 位势高度（geopotential height）** —— 可以理解为"500 hPa 这个气压面所在的高度"。
   - **北侧高度低 → 那里是低压（low）**；
   - **等值线可视作急流中的流线**；
   - **线条挤得越密 → 流动越紧、风越强**；线条稀疏 → 风弱。
2. **色阶 = 850 hPa 温度（约离地 1.5 km）**
   - **红 = 相对暖**（低纬）；**蓝/绿 = 冷**（高纬）。
   - 用 850 hPa 而不是地面温度，是为了**避开地表/边界层的局地噪声**，反映气团本身的性质。

**判读原则**（承接上周）：
- **急流是冷暖空气的分界线，冷空气位于急流的极地一侧（poleward）**；
- **低压中心内部往往嵌着特别冷的空气**（如当天图上那个低压）；
- 急流可以**分裂成两支（two bands）**。

**如何检验预报**：把**同一验证时刻**的"实况分析场"与"N 天前起报的预报场"**逐张来回切换（actual—forecast—actual—forecast）**；**若预报完美，两图应完全重叠**。要看的差异包括：**低压位置与个数、色阶（温度）分布、脊的振幅与尖锐程度**。

### 3.5 挪威气旋模式演化图（Slide 89–94）的判读

**图例**
| 符号 | 名称 | 含义 |
|---|---|---|
| **红线 + 半圆（semicircles）** | **Warm front（暖锋）** | 暖空气**主动爬升**越过冷空气；坡度缓、云雨范围广、降水持续时间长 |
| **蓝线 + 三角（triangles）** | **Cold front（冷锋）** | 冷空气**主动楔入**暖空气下方；坡度陡、**移动比暖锋快**、降水短促而强 |
| **紫线 + 三角与半圆交替** | **Occluded front（锢囚锋）** | 冷锋追上暖锋后形成；标志**风暴的成熟/顶峰** |
| 下半部**等温线（isotherms）** | 温度场 | 显示暖脊被环流扭曲、变尖、最后被挤成窄脊的过程 |

**四阶段序列（北半球）**
```
① 初始波           ② 开放波（open wave）      ③ 开始锢囚             ④ 成熟锢囚低压
极锋上的小涟漪      暖锋、冷锋清晰             冷锋追上暖锋           完全被冷空气包围
几 mb 深            完整暖区（warm sector）    暖区变窄               暖区几乎消失
逆时针环流已存在    暖空气被抬升越过暖锋       暖空气大量抬升至高空   紫色锢囚锋 = 风暴顶峰
等温线轻微变形      暖脊向北突出              冷空气包裹低压         逗号云系最完整
```

**南半球版本的判读**：把整张图**上下镜像** —— 暖空气来自**北方**，环流**顺时针**，卫星云系呈**倒逗号（头在下、尾向上）**。

### 3.6 地面天气图（surface map）判读清单

给你一张 `wetter3.de` 型地面图，按以下顺序读：
1. **找 L（低压中心）与 H（高压中心）**；
2. **看等压线间距**：密 → **strong pressure gradient → strong winds**；疏（尤其低压中心附近）→ **CALM**；
3. **找锋面**：定位**暖锋、冷锋、锢囚锋** → 判断气旋处于**哪个演化阶段**（有完整暖区 = 开放波；已见紫色锢囚锋 = 成熟）；
4. **定位你自己**相对于锋面的位置 → 判断你现在处于**冷区、暖区、还是锋后**；
5. **加上环流方向**（NH 低压逆时针）→ 判断你所在处是**暖平流（warm wind，通常来自南/西南）**还是**冷平流（cold wind，通常来自北/西北）**；
6. **外推**：**中纬度气旋总体自西向东移动** → 未来 6–24 小时哪条锋会扫过你 → 温度、风向、降水将如何突变。

### 3.7 站点观测时间序列（meteogram / Whitworth 记录）的判读

**锋面过境的可观测指纹（本周最实用的技能）**

| 现象 | 温度 | 风向 | 降水 | 云 |
|---|---|---|---|---|
| **暖锋过境** | **逐渐升温**；进入暖区后**夜间也不降温**（例：整夜维持 8 °C） | **较缓和的转向**（例：200° → 150°–180°） | 若只擦到锋尖，**降水很少**；正常暖锋则**范围广、持续时间长** | 层状云系为主 |
| **暖区（warm sector）内部** | **持续偏高且平稳** | 稳定的偏南风 | 少或毛毛雨 | 层云/低云为主 |
| **冷锋过境** | **迅速下降**（几度，abrupt） | **突变，且新风向不持久** | **一阵短促的雨（short burst）** | 卫星上对应**明亮云带** |
| **高压控制（反气旋）** | 日变化大；**日间强升温** | **轻风（light winds）** | 无 | **晴空**；**太阳辐射曲线近似抛物线** |

**辨识伪信号**：辐射曲线上的一些"尖刺"可能是**建筑物反射**造成的仪器伪迹（artifact），不是云。

### 3.8 预报技巧曲线的判读方法

- **纵轴看清是否从 0 开始**（ECMWF 图从 40 起，视觉夸大）。
- **必须有基准线（baseline）**：persistence（持续性）是**零技巧参照**；模式曲线**低于**它的幅度才是真正的**技巧**。
- **横向对比不同时效的曲线**（Met Office 图）：**当某年 N 日预报的误差降到了若干年前 (N−1) 日预报的水平，就说明预报技巧向外延伸了一天** —— 由此读出"**约每十年延伸一天**"。
- 数据都是**12 个月滑动平均**，以滤掉季节波动。

---

## 四、课堂补充（transcript 独有）

以下内容只在录音转写中出现，或课上给出的口头强调、案例与提醒。

### 4.1 老师明确的考试导向

1. **"A reasonable question on the [exam] file might be: here's a weather map. What's going to happen to it? How's the weather going to change?"**
   → **给天气图、判断后续天气演变**是本周最可能的考法。要能说出：气旋自西向东移动、锋面依次过境、各锋面带来什么天气变化。
2. **"I know that many students will confuse on the test... observations are observations."**
   → **观测 vs 预报的术语混用是历年常见失分点**（详见 2.13）。
3. **"You don't need to know these equations by their mathematical form. I want you to know these five equations exist and that they are in all these models."**
   → 五方程**不考数学推导**，但**要能说出有哪五个、每个管什么、各项的物理意义**。
4. **"Again, these are the kinds of things that I want you to focus on."**（在讲完 Manchester 实例后）
   → 重点是**把天气图 / 卫星图 / 地面观测三者对应起来**的能力。

### 4.2 口头补充的重要概念澄清

- **急流与极锋的高度关系**：老师当场纠正自己——"**极锋在地面，急流在其上方更高处（farther aloft）**"。不要说成急流在地面。
- **温带气旋 vs 热带气旋的能量来源**是必须分清的对照（急流/温度梯度 vs 潜热释放）。
- **气旋与反气旋成对出现**：理想化动画里，低压加深的同时，其相邻区域**同步发展出反气旋**，冷空气**从极地被拖曳到低压与高压之间**南下。
- **系统尺度决定演变速度**：2025 年 2 月中旬那个"占满大西洋"的巨型低压与欧洲大陆的大高压，**尺度太大 → 演变极慢 → 已锢囚数日、原地不动**。这是为什么老师**没法用实况演示气旋生命史**，只能用理想化动画。
- **海洋对气团温度的调节**：北大西洋上的气团**温度相对稳定均一**（12 °C vs 15 °C），所以那次锋面两侧温差不显著；对比 2023 年 2 月的例子跨锋面温差达 **−1 °C vs 16 °C**。
- **雷达"看不见云"**：雷达测的是**降水粒子**，不是云滴；卫星可见光看的是**反射的太阳光**，红外看的是**辐射温度**。三者的可见对象不同。

### 4.3 有趣的补充案例与轶事

- **FitzRoy 的自杀**与 Met Office 迁至 Exeter、街道以他命名。
- **Richardson 的手稿在煤堆下失而复得**；他为反战而开救护车；他的成果被用于**芥子气扩散预测**而使他离开气象学；后转向**战争统计学**并预言**冷战以一方破产告终**。
- **Peter Lynch**（爱尔兰）约 20 年前重做 Richardson 的计算并证明"加了滤波就对了"。
- **Lorenz 的计算机占了半个演讲厅**；打印精度 3 位 vs 内存 6 位是混沌被发现的偶然契机。
- **老师在芬兰的办公室对面就是一部装在球罩里的天气雷达**，由此引出"云内我们其实一无所知"。
- **老师在科罗拉多第二高峰的指尖火花事件**（雷电即将发生的亲历征兆）。
- **课上互动**：老师问"可预报性上限是多久"，同学答"两天""六天"，**正确答案两周**。
- **ManUniCast 没有 Android 版**是因为当年经费不足（老师开玩笑说谁给钱就做）；其驱动数据来自美国。
- **AI 与天气预报**：当前很多团队用大模型做天气预报，是 AI 最早攻克的科学问题之一。

### 4.4 Kahoot 全部题目与答案（极佳的复习检查表）

| # | 题目 | 答案 | 解释 |
|---|---|---|---|
| 1 | Which of the following are **stratus** clouds? | 层状、低而均匀铺开的那组 | 层云是英国最常见的云 |
| 2 | Which of the following are **cirrus** clouds? | 高空冰晶、纤细丝缕状的那组 | **cirrus = icy, wispy clouds at high altitudes** |
| 3 | What airstream is this?（低压系统中的红色气流带） | **Warm conveyor belt（暖输送带）** | 干扰项：dry airstream、cold conveyor belt、frosty wave（虚构） |
| 4 | 按 Bjerknes，做出基于物理的天气预报需要哪两个要素？ | **初始条件（initial conditions）+ 物理定律（laws of physics）**（顺序不限） | |
| 5 | 即使有完美模式与完美初始条件，天气预报的理论上限是**三周**。T/F？ | **FALSE** | 是 **两周（two weeks）** |
| 6 | 哪个观测系统贡献进入初始条件的数据最多？ | **Satellites（卫星）** | 比地面观测**高一个数量级** |
| 7 | 下列哪一个**不是**天气预报模式中的方程？ | **Raoult's law（拉乌尔定律）** | 它讲的是**盐在水中的溶解度 / 溶液蒸气压**，与 NWP 无关 |
| 8 | 参数化（parameterization）做以下所有事情，**除了**哪一项？ | **Accounts for poor quality observations（不是）** | 参数化**确实**做的三件事：① 处理未解析的过程（不追踪单个光子/雨滴）；② 简化我们不完全理解的过程（如各种冰晶过程）；③ 弥补我们无法做的测量。**观测的质量控制发生在资料同化系统里，不在模式中** |
| 9 | 热带气旋主要由什么提供能量？ | **Latent heat release（潜热释放）** | 对照：**温带气旋从急流获得能量** |
| 10 | 可见光卫星影像最适合识别下列哪一项？ | **Snow on the ground（地面积雪）** | 干扰项解析：**heavy rain 要用雷达看**；**cold ground surfaces 与暗淡的卷云（dim cirrus）最好用红外识别** |

### 4.5 课程行政信息

- 本周（Week 4）视频 4 个 + 必读 2 篇（见"一、本周主题"）。
- **Week 6 需提前看的视频**（Slide 152）：Stratospheric chemistry；Tropospheric chemistry；The hydrosphere: Where did the oceans come from?；How do the oceans work? Parts 1 and 2；Does the Gulf Stream make Europe temperate?
- 老师说**隐藏的幻灯片（hidden slides）会在课后放出**，其中包含**另一个多年前气旋过境曼彻斯特的完整实例**，把各种要素的变化串在一起。
- 老师提到**如果继续修他的三年级课程，会更深入地讲建模**。

---

## 五、Practical 要点

**（本周无独立 practical）**

但本周有两项**实操性学习任务**，性质接近 practical，务必动手：

1. **用 ManUniCast 自己做一次预报（How to use ManUniCast to make your own forecast）**
   - 网址 `manunicast.com`（有 Apple App）；
   - 可看的产品：European Weather、UK Weather、UK Air Quality（如地面 SO₂ 混合比预报）、Manchester 的 **meteogram**、多站点的 **Skew-T–log p** 探空图；
   - 练习方式：选一个未来时次，**先自己根据天气图判断**（低压在哪、锋面何时过境、温度/风/降水如何变化），**再和模式输出比对**。

2. **Reading Around the Topic（Slide 151）**
   - **练习题：What happened on 25 November 2020?** —— 用本周学到的天气图/卫星/雷达判读方法去查这一天发生了什么。
   - 拓展阅读：
     - **Schultz and Vaughan (2011)**: *Occluded fronts and the occlusion process: A fresh look at conventional wisdom* —— 对锢囚锋传统认识的重新审视；
     - **Wilson et al. (2010)**: *What controls storm tracks?* —— 什么控制风暴路径。

3. **Thought-Provoking Questions（Slide 150）** —— 把大气与本课程其他板块连起来：
   - **大气与地圈（geosphere）以哪些方式相互作用？**
   - **是什么因素决定系外行星与系外卫星上的大气环流与气候？**
   - **太阳系其他行星上有气旋和反气旋吗？**

---

## 六、易错点 / 重点难点

### 6.1 术语与概念混淆（老师点名的考试陷阱）

1. **Observation ≠ Forecast**（最重要）
   - 已发生/正在发生 → **observation**（surface map、satellite imagery、radar imagery、station model、wind barbs）；
   - 未来 → **forecast**（模式输出）。
   - **模式也能输出"看起来像卫星图/雷达图"的产品，那仍然是 forecast**。
   - 描述过去的事情时**说 "forecast" 就是术语错误**。

2. **Cyclone / Anticyclone 的旋转方向**
   - 别只死记；**用科里奥利力两半球方向相反 + 暖空气在热带一侧**来推。
   - 常错：把"cyclone = 逆时针"当成全球通用（**只在北半球成立**）。

3. **温带气旋 vs 热带气旋的能量来源**
   - 温带：**温度梯度 / 急流**；热带：**潜热释放**。**不要写反**。

4. **可预报性上限 = 2 周，不是 3 周、不是 1 个月**
   - 且这是**大尺度（急流、大型气旋）**的上限，**小尺度现象（云、雷暴）短得多**；
   - 实务上 ECMWF 对急流有时可到 **10 天**，5 天预报已相当可靠。

5. **Parameterization 不负责观测质量控制**
   - 参数化 = ①未解析（次网格）过程 ②不完全理解的过程 ③无法测量的量；
   - **观测的质量控制在 data assimilation 系统里**。

6. **雷达测降水，不测云；可见光卫星看反射太阳光（适合看积雪），红外适合看冷表面与暗淡卷云；重降水要看雷达。**

7. **极锋在地面，急流在其上方高空** —— 不要说反。

8. **Vilhelm Bjerknes（父，1904，两要素配方）vs Jacob Bjerknes（子，挪威气旋模式）** —— 父子容易混。

### 6.2 因果链条必须能完整复述（本课程的评分偏好）

**链条 A：为什么等压线密集处风大**
> 动量方程含气压梯度力项 $-\frac{1}{\rho}\nabla p$ → 等压线（或等高线）越密，$\nabla p$ 越大 → 对空气的加速越强 → 风越强。反之低压中心附近梯度小 → **CALM**。

**链条 B：为什么气旋多云雨、反气旋晴朗**
> 质量守恒方程 $d\rho/dt = -\rho\nabla\cdot\mathbf{v}$ → 低层**辐合（convergence）**的空气**只能向上走** → 上升 → **绝热膨胀冷却**（体现在温度方程的散度项） → 达到饱和 → 凝结成云降水（同时释放**潜热**，进入温度方程的 $Q_{latent}$）。
> 反气旋则相反：低层**辐散** → **下沉补偿** → **绝热压缩增温** → 相对湿度下降 → **晴空**。

**链条 C：为什么预报会失败（三重失效，每重都要能举例）**
> ① 初始条件不完美（观测空洞 / 站点之间的天气 / 仪器误差 / **云内微物理根本无观测**）→ 初始场没有的特征后续**难以自发生成**；
> ② 模式不完美（**算力限制分辨率**，因为 24 小时预报必须 24 小时内算完；物理理解不足 → **参数化**是必要的简化）；
> ③ 即使前两者完美，**混沌**仍使误差指数增长 → **两周上限**。
> 案例串联：**Michael Fish / 1987 年 10 月大风暴**同时踩中 ① 和 ②。

**链条 D：温带气旋的完整生命史**
> 极锋（地面冷暖气团分界）→ 其上方的**极锋急流不稳定** → 急流上长出**波动** → 波带有**逆时针环流**（NH）→ 东侧暖平流北上、西侧冷平流南下 → **等温线扭曲、暖区形成** → 气旋加深、卷绕 → **暖空气被抬升越过暖锋、地面暖区缩小** → **冷锋（快）追上暖锋（慢）** → **锢囚锋** → 低压完全被冷空气包围、暖空气尽入高空 → **成熟并最终减弱**。

**链条 E：Manchester 那一周的天气为什么那样变**
> 暖锋尖端过境（风向 200°→150–180°，少雨）→ 进入**暖区**（夜温不降，维持 8 °C）→ **冷锋过境**（骤降温、短促降雨、风向突变）→ 气旋东移、**反气旋接管**（晴空、轻风、**太阳辐射曲线呈抛物线**、街道沥青加剧升温）。

### 6.3 数字类考点速记

| 数字 | 内容 |
|---|---|
| **1904** | Bjerknes 提出两要素配方 |
| **1922** | Richardson 出版数值预报专著；误差 **10–100 倍** |
| **64,000 / 220 km** | Forecast Factory 的人肉计算员数量 / 格子边长 |
| **1949–50** | Charney、Fjørtoft、von Neumann 首次计算机预报（结果 "uniformly poor"） |
| **1963** | Lorenz 混沌论文 |
| **1984** | ECMWF 开始业务预报 |
| **1987 年 10 月** | Michael Fish 漏报的大风暴（Kew Gardens 古树） |
| **2 weeks** | 大尺度天气的**理论可预报性上限** |
| **~10 days** | ECMWF 对急流偶尔可达的实际有用时效 |
| **228,333 / 2,045 / 1,104 / 883,563 / >8,800,000** | 地面站 / 浮标 / 探空 / 飞机 / **卫星**观测数（卫星高一个数量级） |
| **500 hPa** | 位势高度图所在层，代表急流所在的中层大气 |
| **850 hPa ≈ 1.5 km** | 温度色阶所在层 |
| **~40 m（曾 80–90 m）** | ECMWF 第 6 天 500 hPa 高度 RMSE，误差已减半 |
| **约每 10 年 + 1 天** | 预报技巧的历史延伸速率 |
| **2 deaths / 29 injuries per year** | 英国雷电年均伤亡（Elsom and Webb 2017） |
| **30–30** | 闪光到雷声 ≤30 秒 → 躲避；最后一次雷声后等 **30 分钟** |
| **100 yards / 30 yards** | 危险的开阔地跨度 / 水面上雷击致伤的距离 |
| **15 cm / 30 cm / 45–60 cm** | 冲倒人 / 浮起小汽车 / 浮起 SUV 的水深 |
| **32 °F = 0 °C** | 2021 年 2 月墨西哥湾岸的寒潮温度 |

### 6.4 读图技巧类难点

- **纵轴不从 0 开始的误导**（ECMWF 误差图从 40 起）；
- **persistence 作为零技巧基准**的作用与含义；
- **辐射曲线的抛物线判据**（无云）与**建筑反射伪迹**；
- **南半球逗号云的倒置形态**；
- **DWD（手工分析锋）vs Met Office（自动分析锋）图的差异与选择理由**；
- **五天预报检验时该看什么**：低压位置与个数、温度分布、**脊的振幅与尖锐度**。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Weather forecasting | 天气预报 | 用当前大气状态加物理定律推算未来大气状态 |
| Numerical weather prediction (NWP) | 数值天气预报 | 用计算机在网格上求解大气方程组做预报 |
| Initial conditions | 初始条件 | 模式开始积分时刻的三维大气状态，Bjerknes 两要素之一 |
| State of the atmosphere | 大气状态 | 某时刻大气各处的气压、温度、湿度、风等的集合 |
| Data assimilation | 资料同化 | 把散乱的多源观测融合内插到统一三维网格，生成初始条件；观测质量控制也在此完成 |
| Forecast Factory | 预报工厂 | Richardson 设想的球形大厅内 64,000 名人肉计算员并行算天气的场景 |
| Human computers | 人肉计算员 | Richardson 梦想中手工完成格点计算的人 |
| Conductor | 指挥者 | 预报工厂中用光束协调各格点计算同步推进的人 |
| Filtering (of initial conditions) | 初值滤波 | 去掉初始场中高频高振幅噪声（如快波），否则积分会发散——Richardson 失败的原因 |
| Finite differences | 有限差分 | 把微分方程改写成格点间差商形式，使计算机可以求解 |
| Grid / grid box | 网格 / 格点框 | 模式将大气离散化的空间单元；格距决定可分辨的最小特征 |
| Resolution | 分辨率 | 网格的密集程度；越高越能捕捉小尺度特征，但越耗算力 |
| Parameterization | 参数化 | 用简化公式表达次网格尺度或理解不足的过程（辐射、云微物理、湍流通量） |
| Sub-grid-scale process | 次网格尺度过程 | 小于格距、模式无法直接解析的过程 |
| Ideal gas law | 理想气体定律 | p = ρRT，联系气压、密度与温度 |
| Conservation of mass (water) | 水汽质量守恒 | dq/dt = 蒸发率 − 凝结率 |
| Conservation of mass (air) | 空气质量守恒 | 连续方程；低层辐合必致上升，辐散必致下沉 |
| Divergence (of 3D velocity) | 三维速度散度 | ∇·v；正为辐散，负为辐合，决定垂直运动 |
| Convergence | 辐合 | 空气向某处汇聚，迫使空气上升 |
| Water vapour mixing ratio (q) | 水汽混合比 | 单位质量干空气中水汽的质量 |
| Sensible heating | 感热加热 | 通过传导/对流的显热交换（如冷空气流过暖地面被加热） |
| Latent heating | 潜热加热 | 相变释放（凝结，Q>0）或吸收（蒸发，Q<0）的热量 |
| Adiabatic expansion / compression | 绝热膨胀 / 压缩 | 空气上升膨胀冷却、下沉压缩增温，无热量交换 |
| Specific heat at constant volume (c_v) | 定容比热 | 单位质量空气在体积不变时升温 1 K 所需热量 |
| Momentum equation | 动量方程 | 描述三维风如何随时间变化的方程 |
| Coriolis force | 科里奥利力 | 地球自转产生的偏转效应；两半球方向相反 |
| Pressure gradient force (PGF) | 气压梯度力 | −(1/ρ)∇p；等压线越密，风被加速得越强 |
| Isobar | 等压线 | 地图上气压相同各点的连线 |
| Isotherm | 等温线 | 地图上温度相同各点的连线 |
| Geopotential height | 位势高度 | 某等压面（如 500 hPa）所在的高度，用来画高空图 |
| 500 hPa | 500 百帕面 | 约中层大气、急流所在层，高空图的标准层 |
| 850 hPa | 850 百帕面 | 约离地 1.5 km，常用来显示气团温度 |
| Dissipation / viscosity | 耗散 / 黏性 | 类似摩擦的动量损耗项 |
| Persistence forecast | 持续性预报 | "明天和今天一样"的零技巧基准预报 |
| Forecast skill | 预报技巧 | 模式相对于零技巧基准（如 persistence）的改进程度 |
| Root-mean-square error (RMSE) | 均方根误差 | 衡量预报与实况差异的标准统计量 |
| Analysis | 分析场 | 同化得到的"最佳估计的实况"，用作预报的检验基准 |
| Chaos | 混沌 | 确定性系统中初值微小差异随时间指数放大的现象 |
| Butterfly effect | 蝴蝶效应 | 混沌的通俗说法 |
| Sensitive dependence on initial conditions | 对初始条件的敏感依赖 | 混沌的严格表述 |
| Deterministic prediction | 确定性预报 | 给出单一确定未来的预报；因混沌而在长时效上不可行 |
| Predictability limit | 可预报性上限 | 大尺度中纬度天气约为 **两周** |
| Data void | 资料空洞 | 缺乏观测的区域（海洋、无人区、南半球） |
| Radiosonde | 无线电探空仪 | 气球携带升空并回传温压湿风的仪器（Väisälä 完善） |
| Buoy | 浮标 | 海面观测平台，漂流式或锚定海底 |
| Radiance | 辐射率 | 卫星直接测量的量，需通过经验关系反演出温度等 |
| Radar | 雷达 | 测**降水尺度粒子**（不是云）的主动遥感仪器 |
| Radome | 雷达罩 | 保护雷达天线的球形外罩，不阻挡电磁波 |
| Mosaic (radar) | 雷达拼图 | 多部雷达数据合成的单幅降水分布图 |
| Visible imagery | 可见光影像 | 看反射的太阳光；最适合识别**地面积雪** |
| Infrared imagery | 红外影像 | 看辐射温度；适合识别**冷表面与暗淡卷云**，夜间也可用 |
| Meteogram | 气象要素时序图 | 单点上多种气象要素随时间变化的图 |
| Skew-T–log p diagram | 斜温—对数压图 | 显示温度、露点随高度变化的探空图 |
| Station model | 站点模式 | 天气图上用符号紧凑表示单站观测的标准画法 |
| Wind barb | 风羽 | 表示风向与风速的符号；横杠越多风越大 |
| Cyclone | 气旋 | 低压系统；NH 逆时针，SH 顺时针 |
| Anticyclone | 反气旋 | 高压系统；NH 顺时针，SH 逆时针 |
| Extratropical cyclone | 温带气旋 | 中纬度低压，由**温度梯度/急流**驱动，具锋面结构 |
| Tropical cyclone | 热带气旋 | 由**潜热释放**驱动的暖心低压（hurricane / typhoon / cyclone） |
| Norwegian cyclone model | 挪威气旋模式 | Jacob Bjerknes 等在 Bergen 提出的温带气旋概念模型 |
| Bergen school | 卑尔根学派 | Bjerknes 在挪威建立的现代气象学奠基学派 |
| Polar front | 极锋 | 地面上冷暖气团的分界带 |
| Polar front jet stream | 极锋急流 | 位于极锋上方高空的强西风带，其不稳定产生温带气旋 |
| Jet stream | 急流 | 高空强风带，冷暖空气的分界，冷空气在其极地一侧 |
| Baroclinic development | 斜压发展 | 温度梯度提供有效位能、驱动气旋增长的过程 |
| Warm front | 暖锋 | 红线加半圆；暖空气爬升越过冷空气，云雨范围广、持续久 |
| Cold front | 冷锋 | 蓝线加三角；冷空气楔入暖空气下方，移动快、降水短促强烈 |
| Occluded front | 锢囚锋 | 紫线加交替三角与半圆；冷锋追上暖锋后形成，标志气旋成熟 |
| Occlusion | 锢囚 | "closed up"；暖空气被完全抬离地面、低压被冷空气包围的过程 |
| Warm sector | 暖区 | 暖锋与冷锋之间的暖空气区；锢囚过程中不断变窄 |
| Open wave | 开放波 | 尚未锢囚、仍具完整暖区的气旋阶段 |
| Comma cloud | 逗号云 | 气旋成熟时卫星上的逗号形云系；SH 为倒逗号 |
| Warm conveyor belt | 暖输送带 | 气旋中把暖湿空气自暖区抬升北送的主要气流带 |
| Cold conveyor belt | 冷输送带 | 气旋中在暖锋北侧向西流动的冷气流带 |
| Airstream | 气流带 | 气旋中具有共同来源与轨迹的相干气流 |
| Warm advection | 暖平流 | 风把暖空气输送到较冷区域，导致升温 |
| Cold advection | 冷平流 | 风把冷空气输送到较暖区域，导致降温 |
| Cumulus tower | 积云塔 | 垂直发展、顶部呈花椰菜状的积云；雷暴与雷电的前兆 |
| Mixed-phase cloud | 混合相态云 | 同时含冰晶、过冷水与霰的云；闪电形成的必要条件 |
| Graupel | 霰 | 软的、不规则的雹粒；起电过程的关键粒子 |
| Supercooled liquid water | 过冷水 | 温度低于 0 °C 仍保持液态的水滴 |
| Dendrite | 枝状冰晶 | 树枝状生长的冰晶形态 |
| Plate (ice crystal) | 片状冰晶 | 板片状的冰晶形态 |
| Updraft | 上升气流 | 云内向上的气流，闪电形成的必要条件之一 |
| St. Elmo's fire | 圣艾尔摩之火 | 强电场下尖端出现的辉光放电，雷击迫近的征兆 |
| 30–30 rule | 30-30 法则 | 闪光到雷声 ≤30 秒即躲避；末次雷声后再等 30 分钟 |
| Faraday cage | 法拉第笼 | 金属外壳导走电流的屏蔽结构；金属顶车辆即为一例 |
| ECMWF | 欧洲中期天气预报中心 | 位于英国 Reading 的欧洲多国联合预报机构 |
| Met Office | 英国气象局 | 现位于 Exeter，源自 FitzRoy 的努力 |
| DWD | 德国气象局 | wetter3.de 上手工分析锋面图的来源 |
| ManUniCast | 曼大预报系统 | 曼彻斯特大学自建的天气与空气质量预报教学门户 |
| ENIAC | 电子数值积分计算机 | 首次计算机天气预报所用的机器 |
| Richardson number | 理查森数 | 以 L. F. Richardson 命名的表征湍流/层结稳定性的无量纲数 |
| Moore's law | 摩尔定律 | 计算能力随时间指数增长的经验规律，使更高分辨率成为可能 |
| Raoult's law | 拉乌尔定律 | 关于溶液蒸气压/盐溶解度的定律，**不属于**天气预报方程组 |
