# EART29200 Professional Development and Project Preparation — 课程与项目笔记

> 材料来源：unit spec（`(EART29200) …md`）与迷你项目任务书（`SubsidenceAgeProject2025_withNeilMitchell.md`，导师 Neil Mitchell）。
> 凡以 `📎 背景补充：` 开头者为**原材料没有、由笔记补充**的内容；其余忠于原文。

---

## 一、本周主题

EART29200 是大二**唯一的全年课（Full year）**，10 学分，Level 5，不可作自由选修（free choice unit），协调人 Clare Robinson。它的定位很特殊：**不教地质知识，教做科研的方法**。

产出物只有一个——**最多 2000 词的个人科学报告（report），占单元成绩 100%**。被训练的是一整套可迁移技能（transferable skills），对应 8 条 ILO：

| ILO | 内容 |
|---|---|
| 1 | 分析、描述、解释学科定量数据以检验假设（hypothesis） |
| 2 | 执行恰当的统计分析，并就**不确定度（uncertainty）与置信度（confidence）**说明结果意义 |
| 3 | 把研究结果写成有逻辑的叙事（coherent narrative） |
| 4 | 选择并设计能高效呈现结果的图件 |
| 5 | 按**模板（template）**格式化报告 |
| 6 | 准备并进行口头科学论证（oral scientific arguments） |
| 7 | 准备可用于 internship 申请的 **CV** |
| 8 | 具备 **EDIA**（Equality, Diversity, Inclusion and Accessibility）意识的职业行为 |

核心教学法是 **write – feedback – revise（写—反馈—修改）**循环。Aims 明确写道：「A particular emphasis is on reflecting on and incorporating feedback」——**对反馈的反思与吸收本身就是被考核的能力**。

📎 背景补充：这套规范（报告结构、图件规范、引用、第三人称被动语态）会被大二其余课程的 coursework 直接复用——学到的是"以后每一门课交报告的底线格式"。unit spec 未如此表述，属定位解读。

**时间结构（Syllabus 原文）**：S1 共 **10 次每周小组会**，其中一次是 careers event，一次是 EDIA plenary；S2 共 **4 周**。各 pathway 有各自定制项目（bespoke project）。

| 节点 | 内容 |
|---|---|
| S1 W1 | 介绍项目：确定待检验假设 + 检验的性质（nature of the test） |
| S1 W4 | 统计分析思路已讨论完，学生应能自行分析并回报发现 |
| S1 W7 | 统计讨论结束；图件选择与格式、报告叙事结构、模板合规三项指导交付完毕 |
| S1 W8 | **提交草稿（draft），不受理延期（no extension applied）** |
| S1 W9 | 返还个人反馈，讨论共性问题 →（学生修改） |
| S2 W1 | 说明**如何回应了反馈**；互评彼此的修订稿 |
| S2 W2 | 规划小组汇报；**提交终稿（final report）** |
| S2 W3 | 排练小组汇报；某时点 plenary 各组汇报成果 |

另有未定位条目「Week X Intro to Project Choice」。**学时**：Tutorials 22 h + Independent study 78 h = 100 h——**四分之三以上工作量在小组会之外**，小组会只用于校准方向。

---

## 二、核心概念

### (A) 科学内核：洋壳年龄与水深

项目题目 **"Earth's heat loss and the variation in water depth with oceanic crustal age"**。任务书开篇给出两个目的：发展**写科学报告**的技能，以及体会**模型（model）与数据（data）之别**。后者是主线——不是"验证课本"，而是**判断哪个模型能解释你自己造出来的数据**。

**物理链条（任务书叙述）**：
1. 热传导可测：岩石圆盘一侧加热使水温 T₁ 升高，另一侧水温 T₂ 上升；由 T₂ 升幅与水的热容（heat capacity）算出穿过岩石的热能，反推材料常数 k（Figure 1）。
2. 洋中脊（mid-ocean ridge）处岩石很热，岩石圈（lithosphere）/软流圈（asthenosphere）界面靠近地表；向两侧扩张的地幔按式 (1) 冷却。
3. **冷却 → 收缩 → 变致密 → 在下方更塑性的软流圈上下沉**，即海底沉降（seafloor subsidence）。
4. 故**水深随洋壳年龄增加而增加**，这就是待检验的关系。

📎 背景补充（读懂 √t 关系所必需，任务书未展开）：
- 下沉的定量机制是**均衡（isostasy）**：柱体冷却致密后，为维持与软流圈的静力平衡，柱顶必须下降，下降量正比于累计热收缩量。
- **半空间冷却模型（half-space cooling, HSC）**：把冷却地幔当作从上表面向下冷却的半无限介质，热扩散特征深度 ∝ √(κt)，故岩石圈厚度与累计收缩量均 ∝ √t，于是 **d = d₀ + C√t**；同理 **热流 q ∝ 1/√t**。这正是 Parsons & Sclater (1977) 式的物理来源。
- **板块模型（plate model）**：岩石圈厚度存在上限（底部被固定在某温度），冷却到上限后停止加深，水深**指数式趋于渐近值（asymptote）**。任务书中 Parsons & McKenzie (1978) 的"上部力学刚性层 + 下部黏性热边界层"两层模型即属此类，目的正是解释**老洋壳**。
- 因此 **√t 只在年轻洋壳成立**；老洋壳实测水深比 √t 预测**浅**（沉降变缓、变平），热流比 1/√t 预测**高**。任务书原话：这些模型对 old oceanic lithosphere「not well described」。Stein & Stein (1992) 因此**分年轻/年老两段**各给经验式。

**为什么学（任务书自陈）**：做**石油地球科学（petroleum geoscience）**时，岩层温度决定有机质生油还是生气，McKenzie (1978) 模型的变体在油气勘探中被广泛使用；**扩散（diffusion）**框架还用于岩石中的流体流动、含水层（aquifer）中可溶元素的扩散、坡面土壤搬运（地貌学）；**线性化（linearization）**在地学数据分析中无处不在。

### (B) 方法内核

- **假设与检验**：W1 要求同时定下"假设是什么"和"怎么检验"。本项目假设即"水深随年龄按某模型变化"，检验方式是**模型判别**。
- **数据获取**：用 **GeoMapApp** 自己生成数据集。**取样策略本身就是方法学的一部分**（选哪条剖面、避不避海山、平行还是垂直断裂带）。
- **目视对比的局限**：任务书预告把模型曲线叠在散点上「it can be difficult to tell」——**看不出来是设计好的教学环节**，用以逼出线性化。
- **线性化**：把非线性关系经取根号/取对数变换成 `Y = mx + C` 再拟合。任务书给的两类通式是幂律 `y = A·x^B` 与指数 `y = A·e^(Bx)`。
- **写作规范**：图编号 + **图注在下**；表编号 + **标题在上**；不必附原始数据表；正文用**第三人称被动语态**（"A cross-section was drawn…"，不可写 "I drew…"）；须正确 cite 与 reference。
- **报告结构（任务书指定）**：abstract、introduction、methods、results、discussion、conclusion、references。

📎 背景补充（各节写什么，任务书只给节名）：abstract 交代问题/方法/关键数字/结论；introduction 建立背景并明写假设；methods 写到可复现（图层版本、剖面端点经纬度、清洗规则、拟合方法）；results **只陈述事实与数字，不解释**；discussion 才解释、比模型、谈误差与局限；conclusion 直接回答引言的假设。2000 词下常见配比约 200/350/350/400/550/150。

---

## 三、公式与图表

> ⚠️ 任务书 PDF→md 转换时**所有排版为图片/公式框的算式均丢失**，仅 (4)–(7) 以乱序文本残留且数字错位。下面先给**材料原样文本**，再给可复原形式（依据见文末勘误表）。

**式 (1) 热传导（Fourier 定律）**——材料只保留符号说明：「Q is the rate at which heat energy is transferred (W/m²), DT/Dx is the temperature gradient across the disc (˚/m) and k is the rock's thermal diffusivity (how conducting it is) in W/˚/m.」📎 据此复原：

```
Q = -k · ΔT/Δx        (1)
```
`Q` 热流密度 W m⁻²；`ΔT/Δx` 温度梯度 °C m⁻¹；`k` 单位 W °C⁻¹ m⁻¹——**这是热导率（thermal conductivity）的单位，材料误称为热扩散率**（见勘误 1）。
**负号含义**（任务书思考题）：📎 热沿温度**下降**方向流动，而梯度指向温度上升方向，加负号才使 Q 与实际热流同号。

**式 (2) Parsons & Sclater (1977)**——正文式体缺失，但分析章节给出 Excel 实现，可完全复原：
```
depth (m) = 2500 + 350 · t^0.5        (2)
Excel:  =-(2500+350*[A]^0.5)
```
`t` 年龄（Ma）；`2500` = 洋脊轴部水深（m，即 t=0 截距）；`350` = 沉降系数（m Ma^−0.5）。Excel 外层负号是因为 GeoMapApp 导出的是**高程（elevation，海底为负）**而模型给的是**正水深**。📎 适用范围：年轻洋壳（通常 t ≲ 70 Ma）。

**式 (3) Parsons & McKenzie (1978) 两层模型**——材料仅描述结构（"upper mechanically rigid layer" + "lower viscous thermal boundary layer"），**式体缺失，材料未给出具体形式**。📎 该类板块模型形如 `d = d∞ − Δd·exp(−t/τ)`；文献常引的解为 `d(m) = 6400 − 3200·exp(−t/62.8)`，**此数值不出自任务书，引用前须核原始文献**。

**式 (4)–(7) Stein & Stein (1992)**——材料原样（**已损坏**）：
> `5.0 for younger crust depth (km) = 6.2 + .0365 t (4) for older crust depth (km) = .5651 - .2473.exp(-.00278 t) (5) -2 -5.0 and for younger crust heat flow (mWm) = 510 t (6) for older crust heat flow (mWm -2) = 48 + 96.exp(-.00278 t) (7)`

📎 复原形式（修正依据见勘误 2）：
```
younger:  depth (km)          = 2.6   + 0.365 · t^0.5          (4)
older:    depth (km)          = 5.651 - 2.473 · exp(-0.0278 t) (5)
younger:  heat flow (mW m^-2) = 510 · t^(-0.5)                 (6)
older:    heat flow (mW m^-2) = 48 + 96 · exp(-0.0278 t)       (7)
```
- **注意单位换挡**：式 (2) 用 **m**，式 (4)(5) 用 **km**。
- (4) 与 (2) 同族（√t）；(5)(7) 为指数趋近型，描述老洋壳。
- 任务书明说「I am not expecting you to generate results for the heat-flow equations (6 and 7)」——**热流非必做**。

**通式与线性化**——材料仅存说明（"A and B are constants, and 'e' is a special number with the value 2.7…"），式体丢失。📎 复原：
```
幂律：  y = A · x^B      →  ln y = ln A + B · ln x     （log–log 下为直线）
指数：  y = A · e^(B·x)  →  ln y = ln A + B · x        （半对数下为直线）
```
两者斜率 = B、截距 = ln A。📎 但对 `d = d₀ + C√t` 这类**含非零截距**的关系，正确线性化是**以 √t 为横轴**（不是取对数）——取对数会因 d₀ 而拉不直，这是高频陷阱。

**关键图件（文字描述）**
1. **剖面位置图**：底图 GMRT 水深/地形，叠加 Müller (2008) 年龄网格（Layer Manager 调不透明度）；标出三条剖面端点、洋脊轴、断裂带、海山。图注注明数据来源与版本。
2. **深度—年龄散点图**：横轴 age (Ma)，纵轴 elevation (m，负) 或 depth (km，正、轴反转)。点从洋脊（t≈0、最浅）向两侧年龄与水深同增，呈**向下弯的凸曲线**（增速随年龄变缓）；叠加 (2)(4)(5) 预测曲线。
3. **线性化图（核心判据）**：横轴 **√t (Ma^0.5)**，纵轴水深。HSC 成立则点成**直线**；**斜率 = 沉降系数 C**（单位 √年龄的沉降量，反映地幔冷却收缩强度），**截距 = 洋脊轴部水深 d₀**（反映洋脊浮力状态）。**老洋壳段的点会系统性落在直线下方（比 √t 预测更浅），出现 flattening**——这正是板块模型/式 (5) 存在的理由，也是 discussion 的主戏。**异常点**：孤立浅点多为**海山**（火山成因，非热沉降信号）；成排的台阶多为**断裂带**（两侧年龄不同造成高差）。
4. **Reykjanes Ridge 剖面**：预期截距 d₀ 明显偏浅（受**冰岛地幔热点**影响），趋势也可能偏离。任务书思考题：「why would the ridge be shallow and why might the trends … be different there?」

---

## 四、课堂补充

> **本单元无 transcript（无课堂录音/逐字稿材料）。本段全部内容来自 unit spec 与项目任务书**，写的是那些"不是知识、但决定成绩"的隐性要求。

**考核构成**：Report（个人）**100%**，**最长 2000 词**，是唯一 summative 考核；S1 初启动，S2 早中期提交。S1 W8 的**草稿是 formative**（不计分）但**明确注明不受理延期**——错过即失去唯一一次拿详细个人反馈的机会。Feedback methods 写明报告考核 **ILO 1–5**；ILO 6（口头汇报）、7（CV）、8（EDIA）在 ILO 表中只标一个 x，即 **developed 而非 assessed——汇报与 CV 本身不进分数**，但属单元达成要求。

**反馈运作（write–feedback–revise）**：S1 W9 返还**个性化详细书面反馈**并集中讲共性问题 → 学生修改 → S2 W1 **口头说明如何回应了反馈** → 终稿提交后**仍有进一步反馈**。

**小组会运作**：由具备**该 pathway 专业背景**的教员带领（本项目为 Neil Mitchell），配合覆盖报告写作与统计分析的**线上材料**。会议是**持续反馈**式的，不是讲座；W4 要求学生 "report back findings"，即**会上要汇报自己动手的进展**。

**同伴互评（peer review）**：S2 W1 互审对方修订稿并给反馈。团队成分还体现在**以小组为单位处理数据集**与**向同伴汇报总结**；S2 W2 规划、W3 排练、择期 plenary 汇报。

**EDIA**：S1 有**一次专门的 EDIA plenary**。ILO 8 措辞是「Behave professionally with awareness of EDIA issues」——考察**在专业环境中的行为**，不是背概念。材料未给更细的评估细则。

**Careers / CV**：S1 有**一次 careers event**；ILO 7 要求 CV 达到**实习（internship）申请**标准，不是泛泛简历。

**学术诚信与 AI**：任务书 **strongly advised against using AI for this report**，理由是必须先自己发展出科学写作能力；若确实使用，**必须按大学规定申报（declare its use）**，抄袭规则同样适用。

---

## 五、Practical 要点

**① 确定假设与检验方式（S1 W1）**
目的：把"研究洋壳沉降"变成可证伪陈述。方法：写成"H：水深随年龄按 d = d₀ + C√t 变化"，并明确**检验方式是模型判别**（用自采数据比较式 (2)(4)(5) 谁更能 "explain the variations"）。判据：假设必须能被数据否掉——"水深和年龄有关"太弱，"年轻段服从 √t、老段偏离"才合格。

**② GeoMapApp 环境准备**
从 http://www.geomapapp.org/ 下载 Java 应用双击启动（Java 过期会提示更新；Mac 放 Applications），点 "accept"。小屏或触控板不便时点顶部菜单下的 **"Click for searchable tear-off menus"**。先浏览四个标签：**DataLayers**（全球/局部网格：航天飞机雷达高程、测高+船测组合水深、重力磁力；点数据如地震定位、热流实测点）、**Portals**（外站托管数据）、**FocusSites**（多为 NSF 资助项目）、**Overlays**（做终图有用）。

**③ 加载两个必需图层**
水深/地形：`DataLayers → Bathymetry and Topography models → Global Models → GMRT`（第 4 项）。年龄：`DataLayers → Geophysics → Lithospheric Plates → Crustal age grid (Muller 2008 v3)`。用 **Layer Manager** 调**不透明度**同时显示两套数据、调图层顺序；点窗口内 **"i"** 图标跳转图层说明页（**methods 引用数据来源时用得上**）。⚠️ 浏览器初始只显示**图像**，必须加载**网格数据本身**才能分析。

**④ 画剖面并导出**
选 **"Distance/Profile Tool"**（第二行最左），在图上按下—拖动—松开，弹出的剖面窗**同时含两种数据**。左上角保存：**不要存图片，选 "Save ASCII table"**。用 Excel 打开（`Open → delimited`，tab 分隔）。

**⑤ 选剖面位置（方法学得分点）**
任务书建议**至少三条**、体现不同效应：**东太平洋（East Pacific Rise）**扩张极快；**大西洋（Mid-Atlantic Ridge）**扩张较慢；**冰岛以南 Reykjanes Ridge** 因靠近**冰岛地幔热点**而异常浅。两个必答思考题（应在 methods/discussion 中显式回答）：
- **海山（seamounts）纳入还是避开？** 📎 应避开或剔除——火山堆积不是热沉降信号，会把点系统性拉浅。
- **剖面平行还是垂直于断裂带（fracture zones）？** 📎 应垂直于洋脊、**平行于**扩张方向（即平行断裂带走向），使剖面上年龄单调变化；横切断裂带会跨越年龄不连续的板块段，出现台阶跳变。断裂带由脊段横向错断产生，Wilson (1965) 首先指出其源于几何上必需的走滑（strike-slip）运动。

**⑥ 数据整理与清洗**
把列重排成**第一列 age、第二列 elevation**（散点图默认首列为 x），`Insert → scatter graph` 先目视检查。📎 清洗清单（任务书未列）：剔除年龄网格空值/无效值、陆架与陆地段、海山与海沟段、断裂带跳变附近点；同年龄多点可分箱（bin）取中位数以降噪。**每条剔除规则与剔除点数都要写进 methods。**

**⑦ 模型叠加与目视比较**
新增一列 `=-(2500+350*[A]^0.5)`（`[A]` 指向年龄单元格），叠到散点图上；可再叠 (4)(5)。**预期结果是"难以分辨"**——这是正确的中间结论，应如实写出而非跳过。

**⑧ 线性化与拟合**
目的：把曲线变直线，使"谁更好"可量化。方法：对 √t 型（式 2、4）新增 `=SQRT(age)` 列，以 **√t 为横轴**加线性趋势线；对指数型（式 5、7）把 `d∞ − d` 取自然对数后对 t 作图应成直线，斜率给出衰减常数；通式按上文取对数规则处理。
📎 判据：比较各方案的**拟合优度 R²**与**残差（residual）是否随 x 呈系统趋势**。R² 高但残差呈弯曲趋势说明函数形式仍不对——**残差图比 R² 更能识别模型错误**。
📎 统计层面（ILO 2 要求评论不确定度与置信度，但两份材料均未指定具体检验）：可报告斜率/截距的**标准误与 95% 置信区间**，用**零假设 H₀：斜率 = 0** 的 t 检验给出 **p 值**，并看文献值（2500 m、350 m Ma^−0.5）是否落在置信区间内。**具体做法以小组会与线上材料为准。**

**⑨ 作图与成文**
图编号 + 图注在下；表编号 + 标题在上；不附原始数据表；坐标轴须标**量名 + 单位**，多剖面同图加图例；按七节结构成文；全篇**第三人称被动语态**；正确 cite（任务书末尾 7 条文献即可用来源）；**总词数 ≤ 2000**。

**⑩ 提交—修订—终稿—汇报**
S1 W8 交草稿（**无延期**）→ W9 收反馈 → 修改 → S2 W1 说明如何回应反馈 + 互评 → W2 交终稿并规划汇报 → W3 排练 → plenary 汇报。

---

## 六、易错点 / 重点难点

1. **把相关当因果，或把"拟合得好"当"模型正确"**。项目的官方目的之一就是理解 models vs data。R²=0.95 不证明 HSC 成立——要看残差结构，看老洋壳段是否系统性偏离。
2. **在未线性化的数据上直接做线性回归**。深度—年龄本身是曲线，直接拟直线必在两端产生系统性残差。
3. **对含非零截距的关系错误取对数**。`d = d₀ + C√t` 不是纯幂律，`ln d` 对 `ln t` 拉不直；正确做法是**以 √t 为横轴**。
4. **老洋壳段仍套 √t**。材料明说这些模型对 old oceanic lithosphere "not well described"。把 ~100 Ma 以上的点混进 √t 拟合会同时污染斜率与截距，应**分段**并说明分段依据。
5. **单位混用**。式 (2) 是 m、式 (4)(5) 是 km；导出量是 **elevation（负）**而模型是 **depth（正）**。忘换算或忘取负是最常见低级失分。
6. **取样偏倚（sampling bias）**：只画一条剖面、只取洋脊附近点、把海山与断裂带混入、剖面横切断裂带。
7. **把 Reykjanes Ridge 的特殊性当"数据坏了"**。它浅是冰岛热点造成的**真实地球物理信号**，应作讨论素材而非静默剔除。
8. **图件不合规**：缺单位、图注放在图上方、缺图例、缺误差棒/置信带、把原始数据整表塞进报告（任务书明说不需要）。
9. **人称语态错**：写成 "I drew a cross-section"。
10. **词数与结构不合模板**：超 2000 词，缺 abstract 或 references，把解释写进 results。
11. **错过 waypoint**：S1 W8 草稿**不受理延期**，是全课最硬的时间点；S2 W1 拿不出"我如何回应反馈"的说明也直接影响单元达成。
12. **引用不规范**：使用 Muller 2008 年龄网格必须引 Müller et al. (2008)；不要列没读过的文献。
13. **AI 使用未申报**：任务书强烈建议不用；若用必须申报，否则触发学术不端。
14. **误信被转换损坏的数字**：**直接照抄 md 中式 (4)–(7) 会得到完全错误的曲线**，见勘误表。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| seafloor subsidence | 海底沉降 | 洋壳随年龄冷却致密而下沉 |
| bathymetry / elevation | 水深、海底地形 / 高程 | GeoMapApp 导出高程，海底为负 |
| oceanic crustal age | 洋壳年龄 | 自变量，单位 Ma |
| mid-ocean ridge | 洋中脊 | 新洋壳生成处，t ≈ 0 |
| lithosphere / asthenosphere | 岩石圈 / 软流圈 | 刚性外层 / 下伏塑性层 |
| thermal boundary layer | 热边界层 | 两层模型的下层 |
| half-space cooling | 半空间冷却 | 📎 给出 d ∝ √t、q ∝ 1/√t |
| plate model | 板块模型 | 📎 厚度有上限，水深指数趋于渐近值 |
| isostasy | 均衡 | 📎 冷却致密 → 下沉的静力学机制 |
| thermal conductivity | 热导率 | 式 (1) 的 k，W m⁻¹ °C⁻¹ |
| thermal diffusivity | 热扩散率 | m² s⁻¹；材料误把 k 称为此项 |
| heat capacity | 热容 | 由水温升幅反推热量所需 |
| heat flow | 热流 | 式 (6)(7)，mW m⁻² |
| diffusion | 扩散 | 同框架亦用于渗流、含水层溶质、坡面土壤搬运 |
| seamount | 海山 | 火山成因高地，取样干扰 |
| fracture zone / strike-slip | 断裂带 / 走滑 | 脊段横向错断产物（Wilson 1965） |
| spreading rate | 扩张速率 | 东太平洋快、大西洋慢 |
| mantle hotspot | 地幔热点 | 冰岛热点使 Reykjanes Ridge 异常浅 |
| GMRT | 全球多分辨率地形 | GeoMapApp 全球水深/地形网格 |
| Crustal age grid (Müller 2008 v3) | 洋壳年龄网格 | 年龄数据源 |
| petroleum geoscience | 石油地球科学 | 岩层温度决定生油或生气 |
| hypothesis / null hypothesis | 假设 / 零假设 | 📎 零假设如"斜率 = 0" |
| p-value / R² | p 值 / 决定系数 | 📎 显著性 / 被解释的方差比例 |
| regression / linearisation | 回归 / 线性化 | 拟合直线；取根号或对数拉直 |
| residual | 残差 | 📎 观测减预测，比 R² 更能揭示模型错误 |
| uncertainty / confidence | 不确定度 / 置信度 | ILO 2 明确要求评论 |
| cross-section / profile | 剖面 | Distance/Profile Tool 产物 |
| ASCII table | ASCII 数据表 | 必须导出的格式（非图片） |
| scatter graph | 散点图 | 深度—年龄第一张图 |
| sampling bias | 取样偏倚 | 剖面位置与点选造成的系统偏差 |
| unit spec | 单元规格说明 | 官方大纲文件 |
| waypoint | 节点 / 里程碑 | Syllabus 的进度检查点 |
| ILO | 预期学习成果 | 本课共 8 条 |
| formative / summative | 形成性（不计分）/ 总结性（计分） | W8 草稿 / 终稿报告 |
| draft | 草稿 | S1 W8 提交，**不受理延期** |
| peer review | 同伴互评 | S2 W1 互审修订稿 |
| template | 模板 | ILO 5：按模板格式化 |
| plenary | 全体大会 | EDIA 专场 + 成果汇报场 |
| tutorial / independent study | 小组辅导课 / 自主学习 | 22 h / 78 h |
| EDIA | 平等、多元、包容与可达性 | Equality, Diversity, Inclusion and Accessibility |
| CV | 简历 | 面向 internship 申请 |
| pathway | 专业方向 | 各 pathway 有 bespoke project |
| credit rating / Level 5 / free choice unit | 学分 / 五级（本科二年级）/ 自由选修单元 | 10 学分；本课**不可**自由选修 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| SubsidenceAge… — "Background"，式 (1) 符号说明 | "k is the rock's **thermal diffusivity** (how conducting it is) in W/˚/m" | 术语用错：W °C⁻¹ m⁻¹ 是**热导率**的单位；热扩散率 κ 的单位是 m² s⁻¹，括注 "how conducting it is" 也描述导率 | 应为 thermal **conductivity**。关系：κ = k/(ρ·c_p) |
| SubsidenceAge… — 式 (4)–(7) 整段 | `5.0 … depth (km) = 6.2 + .0365 t (4) … = .5651 - .2473.exp(-.00278 t) (5) … -2 -5.0 … = 510 t (6) … = 48 + 96.exp(-.00278 t) (7)` | **PDF→md 转换损坏**：上下标被抽离前置（"5.0"实为指数 0.5，"-5.0"实为 −0.5）、数字位序颠倒（"6.2"实为 2.6）、小数点系统左移一位（.0365 / .5651 / .2473 / -.00278）。照抄将得到完全错误的曲线 | 按 Stein & Stein (1992) 复原：(4) 2.6+0.365·t^0.5；(5) 5.651−2.473·exp(−0.0278t)；(6) 510·t^(−0.5)；(7) 48+96·exp(−0.0278t)。**使用前务必核对原始 PDF** |
| SubsidenceAge… — 全文 | 式 (1)(2)(3) 及两条通式的式体 | **公式本体在 md 中整体缺失**（原为图片/公式框），仅存符号说明与式号引用 | (2) 可由 Excel 式复原为 2500+350·t^0.5 (m)；(1) 可由符号说明复原为 Q=−k·ΔT/Δx；**(3) 与两条通式材料未给出具体形式**，需查原 PDF |
| SubsidenceAge… — "Analysing your dataset"，"Doing so for (6) and (7) produces" | 此处 (6)(7) 指刚引入的两条**通式**；但同文档中 (6)(7) 已用作 Stein & Stein **热流公式**（同段末尾又写 "the heat-flow equations (6 and 7)"） | **式号冲突 / 前后矛盾**：同一对编号指代两组不同公式 | 通式应另编号（如 (8)(9)）。阅读按上下文区分 |
| SubsidenceAge… — 单位 | 式 (2) 用 m（2500、350），式 (4)(5) 用 km（2.6、5.651） | 同一文档内**单位不统一**且未提示 | 非错误但高风险；比较模型前必须统一单位 |
| SubsidenceAge… — References | "Stein, C.A. and Stein, S., 1992. … Nature, 359: **123-137**." | **页码疑似有误**，该文实际为 Nature 359, **123–129** | 引用前请核对 |
| SubsidenceAge… — References | "Crosby, A.G. and McKenzie, D., 2009 …" | 列于参考文献但**正文从未引用**（uncited reference） | 属延伸阅读；写进自己报告须先在正文实际引用 |
| SubsidenceAge… — 引言段 | "spreading of **soluable** elements in aquifers" | 拼写错误 | 应为 "soluble" |
| SubsidenceAge… — GeoMapApp 段 | `http://www.geomapapp.org/` | 明文 http 链接 | 建议用 `https://www.geomapapp.org/` |
| unit spec — Learning outcomes, ILO 1 | "…to test a hypothesis. **, describe and interpret discipline specific quantitative data** — x, x" | **文本重复且残缺**（转换时把简称与全称拼接） | 应读作 "Analyse, describe and interpret discipline-specific quantitative data to test a hypothesis." |
| unit spec — Syllabus 首句 | "10 weekly meetings in semester 1 and **4 weeks** in semester 2" | 与其后节点**数量对不上**：S2 只列 W1–W3 三周 | 第 4 周可能对应 "At some point: Plenary session"；以小组会通知为准 |
| unit spec — Syllabus 末行 | "**Week X** Intro to Project Choice" | **占位符未填**，且位置排在 S2 节点之后，逻辑上应属 S1 早期或上一学年末 | 未完成的草稿残留；实际时间以教学团队通知为准 |
| unit spec — Syllabus vs Feedback methods | Syllabus："Week 2 semester two（Submit final report）"；Feedback methods："submit early to **mid** Semester 2" / "final submission **mid-semester**" | 两处对终稿截止时间**表述不一致**（S2 第 2 周并非 mid-semester） | 以本届 Blackboard/小组会公布的正式截止日为准 |
| unit spec — Learning outcomes 表头 | "Developed" 与 "Assessed" 被转换成两行独立文字，各 ILO 末尾只剩 "x, x" 或 "x" | **表格结构在转换中丢失**，无法直接判断每条 ILO 属 developed 还是 assessed | 结合 Feedback methods 的 "ILO tested 1-5" 推断：ILO 1–5 为 developed + assessed，ILO 6–8 仅 developed |
| unit spec — Pre/co-requisites | 表格只有表头，无任何行 | **内容为空** | 应理解为本单元无前置/共修要求（或原文档即未填） |
