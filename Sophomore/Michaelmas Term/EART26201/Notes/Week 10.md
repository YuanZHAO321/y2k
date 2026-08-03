# EART26201 Principles of Geochemistry — Week 10 学习笔记

> 本周材料：`Lecture/Week 10/lecture 10 stable isotopes 2025-2.md`（幻灯片）、`Lecture/Week 10/lecture 10 quiz answers 2025.md`（随堂测验答案，2025 版）、`Lecture/Week 10/EART26201 - 08-Dec-transcript.md`（课堂录音转写）、`Practical/Week 10/stable isotope practical answers 2025-1.md`（表格答案）、`Practical/Week 10/final practical dec2025 answers-1.md`（期末 practical 模范答案）。
>
> 📎 背景补充：本笔记内部一律采用**文件夹周次编号**（Week 1–10 连续）。课程大纲（spec）里的周次是 Week 2–12（含 reading week），因此 spec 所写的「Week 12: Stable isotopes and carbon dating」就是本笔记的 Week 10。另外 spec 把 practical「Stable isotopes (paper based)」排在 Week 11，实际就是本周三的这场 practical。

---

## 一、本周主题

本周是 **EART26201 的最后一讲**，主题是**稳定同位素（stable isotopes）在水文循环与古气候中的应用**。老师在课上明确说："this week's the final week. No lectures, no practicals next week. We've just got this lecture on stable isotopes and then there's associated practical on Wednesday."

**本周在课程骨架中的位置。** 全课四大块是：热力学与相图 / 反应动力学与扩散 / 酸碱溶解度与氧化还原 / 放射性与稳定同位素。本周属于第四块的后半段——前面 Week 2 讲的是**放射性（radiogenic）同位素**（定年、物源），本周讲的是**稳定（stable）同位素**（分馏、温度计、示踪）。老师开场就做了这个切割："We're not going to touch on radiogenic isotopes, things like rubidium strontium and hafnium. We're just going to look at stable isotopes."

同时，本周也是**课程后半段「流体地球化学」（fluid geochemistry）子模块的收官**。Week 6 的幻灯片上列出的 part 2 大纲共五条：(1) Water as a solvent – ions；(2) Solubility and complexing；(3) Acids and bases；(4) Redox reactions；(5) **Stable isotopes in the hydrologic cycle**。本周正是第 5 条。老师也强调，本周内容和前面几周的教材来源不同："All the other lectures have kind of been based on one textbook … it was all linked to Misra, which is kind of like a physical chemistry textbook. This is a little bit different, but something that is worth covering, kind of in the context of low temperature geochemistry."

📎 **背景补充（全课十周脉络整合）**：以下十周主线由我根据各周文件夹内的讲义标题与 Week 6 幻灯片上的 part 2 大纲整合而成，**不是本周任何一份原文里的现成段落**，仅供收尾复习串线使用。

| 周次（文件夹） | 讲座主题 | 在骨架中的位置 | 一句话主线 |
|---|---|---|---|
| Week 1 | 地球化学家的元素周期表：元素分配与化学分异 | 全课地基 | 主量/次量/微量元素分组，分配行为驱动行星化学分异 |
| Week 2 | 岩石的年龄与来源：放射性同位素 | 第四块（放射成因） | 衰变 → 等时线定年、模式年龄、地幔不均一性 |
| Week 3 | 地球化学系统中的反应：热力学与相图原理 | 第一块 | 平衡、自由能、相律，相图怎么读 |
| Week 4 | 熔融与结晶：相图应用 | 第一块 | 部分熔融、分离结晶、固溶体（如 X_An） |
| Week 5 | 地球化学过程的速率：动力学与扩散 | 第二块 | 热力学管"能不能"，动力学管"多快"；扩散剖面记录时间 |
| Week 6 | 水作为溶剂——溶液中的离子 | 第三块（流体篇开篇） | 离子在水中的行为、活度与浓度 |
| Week 7 | 溶解度与络合 | 第三块 | K_sp、IAP、饱和度、同离子效应、络合与金属迁移 |
| Week 8 | 缓冲、碱度与硅 | 第三块 | 酸碱强度 vs 浓度、pKa、碳酸盐缓冲、碱度 |
| Week 9 | 氧化还原反应 | 第三块 | 氧化态、pE/Eh、Nernst 方程、pE–pH 图 |
| **Week 10** | **水文循环中的稳定同位素** | **第四块 + 全课收尾** | **δ 记号 → 分馏机制 → 瑞利分馏 → 古温度计 → 冰量效应 → 团簇同位素** |

**对下游课程的支撑。**

- 📎 背景补充：**EART23202 地层记录**——本周的碳酸盐–水氧同位素平衡、有孔虫壳体重结晶（recrystallisation）改变原始 δ¹⁸O、生物扰动（bioturbation）混合不同年龄壳体，都是碳酸盐成岩作用与古环境重建章节的直接前置知识。
- 📎 背景补充：**EART21202 全球气候变化**——δ¹⁸O 古温度计、冰芯记录、米兰科维奇（Milankovitch）周期、末次冰盛期（LGM）海平面下降约 120 m，本周全部铺垫完毕；本周 practical 算出的"1.5‰ 里有一半是冰量、一半是温度"正是该课解读深海岩心曲线的基本功。

本周的学习目标（幻灯片 Summary 页原文）：理解同位素分馏及其温度依赖；理解化学分馏与物理分馏；分馏与全球水文循环——大气降水线（meteoric water line）；水文循环的控制因素；古气候重建方法（壳体、孔隙流体，及各自的复杂性）；团簇同位素（clumped isotopes）在古气候中的用法。

---

## 二、核心概念

### 1. 稳定同位素 vs 放射性同位素

- **放射性（radiogenic）同位素**：靠**衰变**随时间累积子体，用于定年与物源示踪（Week 2 的 Rb–Sr、Sm–Nd、Hf 等）。
- **稳定（stable）同位素**：不衰变，其比值变化完全来自**分馏（fractionation）**，即物理化学过程对轻重同位素的差别对待。本周只讲稳定同位素。
- 老师强调稳定同位素是个**极大的领域**，不只是地球化学："There's all sorts of biological, archaeological, medical, you name it. Most sciences use stable isotopes for one thing or another."

### 2. 稳定同位素在地球与环境科学中的四类应用（幻灯片开篇）

1. **测温（Thermometry）**：岩石、矿物、气体的形成温度，依据是同位素分馏的**温度依赖性**。
2. **古气候学（Palaeoclimatology）**：矿物、流体、气体的同位素比值保存了过去环境条件（尤其是温度）的信息。
3. **示踪剂（Tracers）**：大型陆地储库（海洋、地幔、大气降水、有机质）各有特征同位素信号，可追踪岩石、流体、植物、污染物的来源。
4. **过程（Processes）**：扩散、结晶、开放/封闭系统、细菌过程。

### 3. 分馏（fractionation）与储库（reservoir）

**分馏**的定义（幻灯片原文）：*"Fractionation refers to the partial separation of two isotopes of the same element, producing reservoirs with different ratios of the isotopes."* 即**同一元素的两种同位素被部分分离，产生同位素比值不同的储库**。这些差异称为**同位素异常（isotopic anomalies）**。

老师对"储库"的口头澄清很重要：储库可以是**物理场所**（海洋、湖泊、地球内部），也可以是**一个矿物**——而与之平衡的另一个矿物就是另一个储库。所以"reservoir"要打引号理解，尺度可大可小。

### 4. 三类分馏机制

| 机制 | 物理原因 | 典型例子 | 是否质量相关 |
|---|---|---|---|
| **平衡分馏 equilibrium isotope fractionation** | 化合物中同位素的**键能（bond energies）**差异 | 两个平衡共存的矿物；水与从水中沉淀的碳酸盐；云与降雨 | 是（mass dependent） |
| **动力学分馏 kinetic isotope fractionation** | 不同同位素的**平均速度（velocity）或反应速率（reaction rates）**差异 | 蒸发、扩散、逃逸到太空、细菌代谢 | 是（mass dependent） |
| **质量无关分馏 mass-independent fractionation (MIF)** | 取决于**分子对称性（molecule symmetry）** | 早期太阳系的 O 与 S；大气气体与紫外线相互作用 | 否 |

- 两种基本机制都只取决于**质量差**，所以称为 **mass dependent fractionation**；它们对 ¹⁸O/¹⁶O 的分馏约是对 ¹⁷O/¹⁶O 的**两倍**（因为 18−16 = 2，17−16 = 1）。
- MIF 是"the strange one"，老师说它在早期太阳系至今**仍未被完全理解**，行星方向的同学可能见过；本周不考察。
- 动力学分馏的直观理解（老师原话）："a lighter isotope will tend to do things quicker if you've got the same energy in a particular environment"——同样能量下，轻同位素跑得更快。

### 5. 分馏系数 α（fractionation factor）

α 定义为两个相中同位素比值之比：α = R_A / R_B。例如 A 是碳酸盐、B 是水；或 A 是云、B 是从云里落下的雨。

**关键性质**：α 非常接近 1，因为比值差异只有千分之几。老师："That alpha number will actually be 1.00 and then a few digits after that." 唯一例外是氢，α 可以到 1.07 量级。

### 6. δ 记号（delta notation）与标准物

因为 α ≈ 1.00x 不好读，我们改用 **δ 值**，单位 **‰（per mil，千分号）**。老师的直白解释："really the point of the delta is just to multiply it by a thousand, so that you get these units called per mil, which tend to be whole numbers."

**命名规则**：δ 以**重同位素**命名，写作 δ¹⁸O、δD（δ²H）、δ¹³C，但其含义永远是**重/轻同位素的比值相对于标准**（δ¹⁸O 实际是 ¹⁸O/¹⁶O 的相对偏差）。老师补充：**除锂（Li）之外，所有元素的 δ 都以较重的那个同位素命名**——"I don't know why lithium is the wrong way around, but what it is."

**δ 尺度的读法（幻灯片 Delta scale 页）**：

- R_sample > R_standard → **δ 为正** → 富集重同位素（enriched in heavy isotope）/ 亏损轻同位素 → 口语称 **isotopically heavy**
- R_sample = R_standard → **δ = 0**
- R_sample < R_standard → **δ 为负** → 富集轻同位素 / 亏损重同位素 → 口语称 **isotopically light**

用标准物测比值这个动作叫 **calibrating（校准）**："a sample will be calibrated relative to a specific standard."

**各元素的标准物**（转写课堂原话整理）：

| 元素 | 标准物 | 说明 |
|---|---|---|
| O、H（水/流体） | **SMOW**（Standard Mean Ocean Water） | 老师强调：它**根本不是真的海水**，而是人工配制的、成分被规定好的水，但**非常接近现今海水**。δD = 0‰、δ¹⁸O = 0‰ |
| C | **belemnite（箭石）**——即 PDB 系列 | 老师原话是"some kind of belemnite … some kind of creature that lives in the ocean" |
| S | **troilite（陨硫铁）** | 与陨石有关 |
| N | **atmosphere（大气）** | 即 AIR |

📎 背景补充（材料未展开的现代命名）：目前国际通用的是 **VSMOW**（Vienna-SMOW，水的 O、H）、**VPDB**（Vienna-Pee Dee Belemnite，碳酸盐的 C、O）、**VCDT**（Vienna-Canyon Diablo Troilite，S）、**AIR**（N₂）。碳酸盐的 δ¹⁸O 常报在 VPDB 上，而水的 δ¹⁸O 报在 VSMOW 上，两者之间必须换算才能比较——本周材料没给换算式，只在讲 SPECMAP 曲线时提到"In this case it's got a different standard, but it doesn't make any difference, it's just an offset from that SMOW standard that we normally see."（即只是一个平移量）。

### 7. 水–水汽之间的 O、H 分馏

- **H₂¹⁶O 的蒸气压高于 H₂¹⁸O 和含 D 的水**（"light isotopes move faster"）。
- 因此**蒸发或凝结时，水汽富集 ¹⁶O 与 H，液相富集 ¹⁸O 与 D**。
- **氢的分馏远大于氧**，原因是**相对质量差**：氧是 (18−16)/16 = 1/8；氢是 (2−1)/1 = 1。老师："deuterium is twice the mass of normal hydrogen. So any fractionation effects are going to be magnified with hydrogen relative to oxygen."

**25 °C 的分馏系数（幻灯片数值）**：
- α_(L−V)(¹⁸O/¹⁶O) = **1.0092** → 约 **9‰** 的液–汽差
- α_(L−V)(D/H) = **1.074** → 约 **74‰** 的液–汽差

### 8. 瑞利分馏（Rayleigh fractionation）与降水的同位素演化

幻灯片给出 R/R₀ = f^(α−1)。物理图像（老师的口头版本，非常好用）：

1. 海水 δ¹⁸O ≈ 0‰ 出发；
2. **蒸发** → 生成水汽/云，**同位素偏轻**（这一步既有平衡分馏，也有动力学效应：轻同位素蒸发更快）；
3. 云中**降雨**，雨**比云本身重**；
4. 雨带走了相对重的同位素，**剩下的云就更轻**；再降雨，雨又比此时的云重，但整体一路**越来越轻**；
5. 结果：**从沿海向内陆、从赤道向两极，降水 δ¹⁸O 越来越负**。

老师用一句话概括本节的 take-home："**light isotopes at the poles**（轻同位素在两极）——That's all you really need for the next part of the lecture."

**全球降水 δ¹⁸O 分布图**：赤道附近约 0‰ 甚至略正；向两极（北极、格陵兰、南极）变成紫蓝色，约 **−16‰ 到 −30‰**，南极内陆"minus 20 and below"。

**全球海水 δ¹⁸O 分布图**：全球平均约 0‰，但有区域差异——蒸发强烈的低纬海区（如**地中海**）比平均值**更重**；极区海水因与冰、极地降水混合而**更轻**。这与降水图是同一过程的两面。

### 9. 动力学效应与全球大气降水线（GMWL / meteoric water line）

- **云 → 雨** 这一步基本上是**纯平衡分馏**。
- **海面 → 水汽** 这一步则**平衡分馏 + 动力学分馏叠加**：液面上方先建立液–汽平衡，同时还有扩散与动力学损失。老师提到这个模型（转写为"spare drop model"）。📎 背景补充：从描述看这应当是文献中的 **Craig–Gordon 蒸发模型**（液面薄层平衡 + 扩散边界层动力学），但**转写含糊，材料未明确写出模型名称**，考试作答建议只按"平衡 + 动力学叠加"来描述。
- **动力学分馏的强弱取决于海面条件：湿度（humidity）、温度（temperature）、风速（wind speed）**。**低湿度时动力学分馏最大**。
- **GMWL 图**：横轴 δ¹⁸O、纵轴 δD（δ²H）。全球绝大多数天然水（云、雨等）都落在这条**实线**上；它本质上是一条**平衡分馏线**。
  - **低纬（低纬度）水在右上**——同位素偏重；**高纬水在左下**——δ¹⁸O 与 δD 都偏负。
  - 瑞利分馏只是让水**沿着这条线上下移动**。
  - **海水本身略偏离这条线**，因为海面蒸发是**动力学**过程，而这条线是**平衡**线。
  - **强蒸发的湖泊会明显偏离该线**（蒸发线），因为它由动力学过程主导。
  - 老师说幻灯片上这张图"there's no numbers on it, but that's okay, it's just a schematic"。
- 📎 背景补充（材料未给出的经典数值）：GMWL 的经典表达式为 **δD = 8 × δ¹⁸O + 10**（Craig, 1961），**斜率 8、截距 10‰（即氘盈余 d-excess ≈ 10‰）**。斜率 8 来源于 D/H 与 ¹⁸O/¹⁶O 平衡分馏幅度之比（约 74‰ : 9‰ ≈ 8）；蒸发主导的水体（湖泊、干旱区）蒸发线斜率通常降到 **4–6**。**本周幻灯片与转写都没有给这两个数字**，仅给了"实线 + 高低纬位置"的示意，考试若要求作图，画出斜率约 8 的正相关直线并标出海水在 (0,0) 附近即可。

### 10. 碳酸盐–水氧同位素温度计

- 关系由 **Epstein et al. (1953) 经验（实验）测定**，后由 **Craig (1965) 修正**——做法是在已知成分的水中溶解并沉淀碳酸盐。**碳酸盐相对水富集 ¹⁸O**（"the solid is almost always heavier than the water phase"）。
- 幻灯片给出的关系式：**1000·lnα = 17599/T − 29.64**（T 为绝对温度 K）。
- 图的读法：横轴温度，纵轴 1000·lnα（可直接当作碳酸盐与水之间的 δ¹⁸O 差）。图上画了两种不同的方解石。**温度越高，分馏越小**——约 24 °C 时碳酸盐与水差约 **28‰**；90 °C 时降到约 **17–19‰**（转写此处报成"70 per mil"，是明显口误/转写错误，见勘误表）。
- 关键理解：**1000·lnα 与 Δ（δ_A − δ_B）在数值上几乎等价**，所以纵轴写哪个都一样，"You'll see them interchangeably on a y-axis of isotope charts."

### 11. 古气候档案（archives）

幻灯片（Lachniet, 2009 图）列出的水圈同位素档案：**冰芯（ice cores）、地下水（groundwater）、树轮（tree rings）、湖泊沉积（lake sediments）、石笋（speleothems）、有孔虫（foraminifera，深海岩心）、珊瑚（corals）**。

老师的逐项点评：石笋本身是碳酸盐，其氧同位素与滴入洞穴的水相关；老地下水本身就是过去地表水的直接样品；树轮因树木吸水而间接可用（关系不简单）；**深海岩心沉积是本周重点**——既可测其中的有孔虫/珊瑚，也可测**孔隙流体**。历史背景：**Glomar Challenger**，1960 年代建造的第一艘专为深海钻探取岩心设计的科考船。

### 12. 有孔虫（foraminifera）记录与它的三大问题

**核心观测**：深海（**底栖 benthic**）有孔虫记录显示，末次冰盛期（**LGM**，约 2 万年前）相对今天有 **+1.5‰ 的 δ¹⁸O 偏移**。

**SPECMAP**（Spectral Mapping Project）：汇编大量深海岩心底栖有孔虫 δ¹⁸O，本意是做**全球地层对比**（用于给未知年龄的海洋沉积定年），也可用来看冰期–间冰期变化。曲线特征：
- 时间跨度约 70 万年到现今；
- **锯齿状（sawtooth）**：缓慢的冰量累积 + 快速的冰消（老师描述见勘误表，转写有前后矛盾）；
- 明显的 **约 10 万年周期** = **米兰科维奇周期（Milankovitch cycles）**，源于地球**偏心率与轨道参数**变化；虽有多个周期，但最显著的是 10 万年。

**三大问题（quiz 第 10 题答案是"以上全部"）**：
1. **壳体死后可能重结晶（recrystallise）**——所有沉积物都有一定程度重结晶，会改变原始 δ¹⁸O。→ 对策：**仔细挑选没有蚀变迹象的壳体**。
2. **不同年龄的壳体可能被混合**（生物扰动 bioturbation），在**沉积速率低**的地区尤其严重。→ 对策：**选沉积速率高的站位**，让壳体一落底就被埋藏隔离。
3. **水体中的生活深度影响记录到的温度**——浮游（**planktonic**）有孔虫会随季节在不同深度游动（夏浅冬深），把不同温度积分在一起。→ 对策：**用底栖（benthic）有孔虫**，因为**洋底温度在全球都相当一致**。浮游种与底栖种因生态环境特异而容易区分。

### 13. 冰量效应（the "ice volume" effect）

这是本周最核心的概念难点。

- 冰期时，**轻同位素被从海洋中蒸发走、以雪的形式锁进大陆冰盖**。
- 把"海洋 + 冰盖"看作一个**封闭系统（closed system）**：冰盖的 δ¹⁸O 更负、且冰**量**更大 → **剩下的海水必然变重**。
- 于是有孔虫记录的 +1.5‰ 里，**混合了两件事**：(a) **海水温度变化**（冰期冷、间冰期暖，分馏本身随温度变）与 (b) **海水本身成分（δ¹⁸O）的变化**。
- **关键问题（幻灯片原文标题：the really big question in paleoceanography）**：这 1.5‰ 里有多少来自冰量（海平面变化），多少来自温度？
- 老师的重要澄清（quiz 第 8 题）：**冰本身的同位素成分基本不变，变的是冰的量**——"It's kind of equally as light, but there's more of it. Therefore, it's the ocean（变的是海水成分）"。

### 14. 孔隙流体（pore fluids）——独立约束

- 深海沉积物中滞留着 **pore fluids**，那是**被困住的真实海水样品**，可以**直接**测量过去海水的 δ¹⁸O，从而把"水成分变化"这一项单独拿出来。
- **为什么必须建模而不能直接读**（幻灯片）：沉积物压实时**平流（advection）**把水挤出去，**扩散（diffusion）**又不断抹平信号脉冲；因此**只对末次冰盛期（LGM）到现今这一段有效**。
- **结果**：大西洋两个 ODP（Ocean Drilling Program）站位的孔隙流体剖面中存在一个正异常"鼓包"（**glacial enrichment**，冰期的重水），向浅部（现今）变轻。最佳拟合给出冰期–间冰期海水 δ¹⁸O 变化 = **+0.7‰（一个岩心）与 +0.8‰（另一个岩心）**，即约 **0.7–0.8‰**。
- **quiz 第 9 题**：孔隙流体提供的是对**海洋 δ¹⁸O** 的独立确认（不是温度、不是压力、不是冰的 δ¹⁸O）。

### 15. 拆分结果：一半冰量、一半温度，约 4 °C

- 有孔虫总位移 **1.5‰**；孔隙流体给出的水成分变化 **≈ 0.75‰**。
- 因此**约 50% 来自水成分（冰量）变化，约 50% 来自温度变化**。
- 把剩下的 0.75‰ 代入碳酸盐–水分馏曲线：曲线大致从 **100 °C 到 20 °C**（跨度约 **80 °C**）对应约 **15‰** 的 1000·lnα 变化，近似线性 → 0.75‰ × (80/15) = **约 4 °C**。
- **交叉验证**：另一支岩心也给出碳酸盐值与实测水值差约 0.7‰；**Mg/Ca 温度计**在同一时段给出约 **23 °C → 27 °C**，同样是约 4 °C。老师："there's various lines of evidence to suggest that 4 degrees C isn't far off."

### 16. 团簇同位素（clumped isotopes / rare isotopologues）

- **定义**：由**不止一个稀有（重）同位素**组成的分子（rare isotopologue）。
- **现象**：碳酸盐晶体中同位素**并非随机（stochastic）分布**；**¹³C–¹⁸O 键比随机分布应有的丰度更高**——重碳优先与重氧成键，即"clumping"。这种成团程度**温度依赖**（低温 Δ47 大、高温小，与普通分馏同向）。
- **最大优势**：这是**相内 / 分子内（intra-phase / intra-molecular）**信号，**读它不需要参考任何其他物种**——**不用知道成水的同位素成分**，正好绕开"两个过程只有一个测量值"的困境。
- **测量方法**：碳酸盐溶于**磷酸（H₃PO₄）**释放 CO₂，测**质量 47**（主要是 ¹³C¹⁶O¹⁸O）相对**质量 44**（¹²C¹⁶O¹⁶O）的丰度超出随机分布的量，记为 **Δ47**。注意：**不能把分子拆成单个原子**（普通质谱做法），否则丢掉键的信息。
- **标定数据**：约 3 °C 时 Δ47 ≈ **0.8‰**，到约 50 °C 更低。标定对象：无机标定、珊瑚、鱼耳石（otoliths）、土壤碳酸盐、腕足类、软体动物。
- **应用**：古气候（有孔虫、颗石藻 coccoliths、结核、石笋、恐龙、古土壤 paleosols）。**恐龙血温 36–38 °C**，与人类相近；做法是测**生物磷灰石（bioapatite，牙齿）**而非碳酸盐，并用犀牛、大象、鳄鱼、鲨鱼等实测体温验证，**吻合良好**。
- 老师总评："It's a harder measurement to make … but it is more useful, I think, in terms of paleoclimate."

### 17. 📎 背景补充：δ¹³C 的储库差异（本周材料未涉及）

本周讲义与转写**完全没有讲 δ¹³C 的储库分布**（本周只讲 δ¹⁸O 与 δD，以及团簇同位素里的 ¹³C–¹⁸O 键）。以下为补充框架，供与下游课程衔接，**数值均非本周材料**，考试以讲义为准：**有机质轻**——光合作用（RuBisCO）强烈偏好 ¹²C，C3 植物 δ¹³C ≈ −25 至 −30‰（VPDB），C4 ≈ −12 至 −14‰；**碳酸盐重**——海相碳酸盐 ≈ 0 ± 2‰；**地幔碳** ≈ −5 至 −7‰；**工业革命前大气 CO₂** ≈ −6.5‰，因化石燃料注入持续变负（**Suess 效应**）。两大碳库相差约 25‰，故 δ¹³C 可示踪有机碳埋藏变化（碳同位素漂移 excursion）、甲烷释放、污染源与古食谱。

---

## 三、公式与图表

### 公式 1：分馏系数（fractionation factor）

$$\alpha = \frac{R_A}{R_B}$$

- **R_A、R_B**：两个相（phase）中的**同位素比值**，例如 ¹⁸O/¹⁶O。A、B 可以是"碳酸盐与水"、"水汽与液态水"、"云与雨"。
- **单位**：**无量纲**。
- **典型值**：**非常接近 1**（"α is close to 1 because ratios differ by parts per thousand"）。25 °C 液–汽体系：α(¹⁸O) = **1.0092**，α(D/H) = **1.074**。
- **适用条件**：严格说 α 描述的是**两相平衡**时的比值关系；动力学过程也常沿用 α 记号但含义是速率比。

### 公式 2：δ 定义式

$$\delta = \left(\frac{R_{\text{sample}}}{R_{\text{standard}}} - 1\right) \times 1000\ ‰$$

- **R_sample / R_standard**：样品与国际公认标准物中重/轻同位素的比值。
- **单位**：**‰（per mil，千分号）**——写法是"百分号再多一个零"。
- **符号规则**：正 = 富重同位素（isotopically heavy）；0 = 与标准相同；负 = 富轻同位素（isotopically light）。
- **典型值范围**：氧同位素体系的分馏"a few per mil to a few tens per mil"。全球降水 δ¹⁸O 从赤道约 0‰ 到南极约 −30‰。
- 📎 背景补充：这个展开式本身在幻灯片上被 PDF 转换吞掉了（原页只剩文字说明），此处按标准形式补回；转写中老师的口头定义"the point of the delta is just to multiply it by a thousand"与之一致。

### 公式 3：δ 差与 1000 lnα 的等价关系

$$\Delta_{A-B} \equiv \delta_A - \delta_B \approx 1000\ln\alpha_{A-B}$$

- 幻灯片写作 "Δ_{a-b} ~ 1000 ln α"。
- **适用条件**：α 接近 1 时的一阶近似（因为 ln(1+x) ≈ x）。α 偏离 1 越远（如氢体系 α = 1.074），误差越大。
- **用途**：图表的纵轴用 1000·lnα 或 Δδ 都可以，可互换读。

📎 背景补充：材料没有写出 **ε（epsilon，富集因子 enrichment factor）**这个符号，但它与上式是同一件事：**ε ≈ (α − 1) × 1000 ≈ 1000 lnα ≈ Δ**，单位 ‰。本周 practical 里那个"Δ¹⁸O_(liquid−vapour) = 9.4‰"扮演的就是 ε 的角色。**α 无量纲、ε 带千分号**，两者不能混写。

### 公式 4：瑞利分馏（Rayleigh fractionation）

幻灯片形式（PDF 转换后残缺，原式为）：

$$\frac{R}{R_0} = f^{(\alpha - 1)}$$

- **R**：残余储库当前的同位素比值；**R₀**：初始比值。
- **f**：**残余分数（fraction remaining）**，即还留在储库里的质量分数，0 < f ≤ 1。
- **α**：产物与残余之间的分馏系数（此处 = α_(liquid−vapour)）。
- **适用条件**：**产物一形成就立刻被移出体系**（瑞利式开放系统 / 蒸馏），且 α 在过程中保持常数。
- 老师的口头版："the ratio will change by a certain amount, which is equal to … the fraction that is rained out or separated from, to the power of this alpha."

**练习用的对数线性形式**（practical 中实际使用）：

$$\delta = \delta_0 + \varepsilon \ln f$$

- 由上式两边取对数、再用 δ ≈ 1000 ln R 近似导出：ln(R/R₀) = (α−1) ln f → δ − δ₀ ≈ 1000(α−1) ln f = ε ln f。
- **符号陷阱**：ln f < 0（f < 1）。若移走的产物**比残余重**（ε > 0，如从水汽中降雨），残余越来越**轻**；若移走的产物**比残余轻**（ε < 0，如海洋失水成冰），残余越来越**重**。

**瞬时产物（雨）的组成**：

$$\delta_{\text{rain}} = \delta_{\text{vapour}} + \varepsilon$$

### 公式 5：碳酸盐–水氧同位素古温度方程

$$1000\ln\alpha = \frac{17599}{T} - 29.64$$

- **T**：**绝对温度（K）**。
- **左边**：碳酸盐与水之间的 1000·lnα，等价于 δ¹⁸O_carbonate − δ¹⁸O_water，单位 ‰。
- **来源**：Epstein et al. (1953) 经验测定，Craig (1965) 修正。
- **数值检验**：T = 297 K（24 °C）→ 17599/297 − 29.64 = **29.6‰**，与课上说的"约 28‰"量级一致；T = 363 K（90 °C）→ 48.5 − 29.6 = **18.8‰**，与"约 17–19‰"一致。**温度升高，分馏减小**。
- 📎 背景补充：Past Papers 中 `EART26201 Jan 2025 exam with answers.md` 第 2 题的标准答案给出的是另一种常见形式 **10³lnα = 2.78(10⁶·T⁻²) − 2.89（O'Neil, 1969）**，属于 T⁻² 形式的标定。**两式都是方解石–水体系的经验标定，写哪一个都可以，但不要把常数记串**。

### 公式 6：把 δ 差换算成温度差（课堂速算法）

$$\Delta T \approx \Delta\delta \times \frac{\Delta T_{\text{图}}}{\Delta(1000\ln\alpha)_{\text{图}}} = 0.75 \times \frac{80}{15} = 4\ ^\circ\text{C}$$

- 依据是碳酸盐–水分馏曲线在 20–100 °C 段**近似线性**：约 80 °C 的温度跨度对应约 15‰ 的 1000·lnα 跨度，即**灵敏度约 0.19‰ per °C**。
- ⚠️ 幻灯片上把它写成 "0.75/(15\*80)"，是**排版错误**，正确是 0.75 ÷ (15/80) 或 0.75 × 80/15（见勘误表）。

### 公式 7：Δ47（团簇同位素）

$$\Delta_{47} = \left(\frac{(47/44)_{\text{sample}}}{(47/44)_{\text{stochastic}}} - 1\right)\times 1000\ ‰$$

- 材料只给了概念表述（"how much more of that one you've got than you would expect"）与图上的 (47/44) 与 ×1000 记号，**未给完整定义式**；上式为按此描述整理的标准写法。
- **质量 47** 主要是 **¹³C¹⁶O¹⁸O**；**质量 44** 是 **¹²C¹⁶O¹⁶O**。
- **典型值**：3 °C 时约 **0.8‰**，50 °C 时更小。
- **核心优点**：**不需要知道成水的 δ¹⁸O**。

### 图表文字描述

**图 A｜Delta scale 尺度条**：一条数轴，中点为 0（R_sample = R_standard）。正方向标"Enriched in heavy isotope / Depleted in light isotope"，负方向标反之。记住：**正=重，负=轻**。

**图 B｜降水的瑞利分馏卡通图**：左边是海洋（δ¹⁸O = 0‰），海面蒸发形成云（δ 明显为负）；云向内陆/向极地移动，沿途一次次降雨。**每场雨都比当时的云重（+ε），但云本身一路变轻，所以后续每场雨也一次比一次轻**，到极地时降水已很负。此图同时是赤道→极地的全球类比。

**图 C｜瑞利分馏曲线（practical 数值版）**：横轴 f 从 1 递减到 0.1，纵轴 δ¹⁸O。
- **残余水汽曲线**（上式 δ = −10 + 9.4 ln f）：从 (1.0, −10.0‰) 起，缓慢下降，(0.5, −16.5‰)，然后在 f 小于 0.3 之后**急剧下坠**，到 (0.1, −31.6‰)。曲线是**凹向下、尾部发散**的对数形状。
- **瞬时降雨曲线**：与残余曲线**平行地整体上移 ε = 9.4‰**，从 (1.0, −0.6‰) 到 (0.1, −22.2‰)。
- 两条线**始终相隔 9.4‰**，且雨永远在上方（更重）。

**图 D｜全球大气降水线 GMWL**：横轴 δ¹⁸O（约 −40 到 +10‰），纵轴 δD（约 −300 到 +50‰）。一条**正相关实线**贯穿，海水在原点 (0, 0) 附近。**左下端 = 高纬（冷、轻）**，**右上端 = 低纬（暖、重）**。海水样品**略偏离线**（因蒸发的动力学效应），强蒸发湖泊沿一条**更缓的斜线**从 GMWL 上分岔出去。📎 背景补充：经典斜率 8、截距 10‰——材料图上无数字。

**图 E｜全球降水与海水 δ¹⁸O 地图**：降水图上赤道带为暖色（≈0‰ 或略正），向两极过渡为紫蓝色（−16 至 −30‰），格陵兰与南极最负。海水图上地中海等强蒸发区**偏正**，极区海水**偏负**，全球平均 0‰。

**图 F｜碳酸盐 δ¹⁸O–温度关系图**：横轴温度（约 20–100 °C），纵轴 1000·lnα（≈ δ¹⁸O_carb − δ¹⁸O_water，约 15–30‰）。两条略有差异的曲线代表两种方解石。整体是**负斜率、近似线性**：低温端约 28–30‰，高温端约 17‰。

**图 G｜SPECMAP 底栖有孔虫 δ¹⁸O 曲线**：横轴年龄 0–700 ka，纵轴 δ¹⁸O。呈**约 10 万年周期的锯齿波**；LGM（约 20 ka）与现今之间的落差约 **1.5‰**（"从略小于 0 到略小于 1.5"）。用途：全球海洋地层对比 + 冰期旋回研究。

**图 H｜冰量效应卡通**：两个方框，左为间冰期（今日）：冰盖小、δ¹⁸O 负，海洋 δ¹⁸O = 0；右为冰期：冰盖大（δ¹⁸O 同样负，但**体积大得多**），海洋因此**变重**（正值）。整个方框是**封闭系统**。

**图 I｜孔隙流体剖面**：横轴 δ¹⁸O，纵轴岩心深度（m）。剖面在中部有一个**正的鼓包（glacial enrichment）**，向浅部（现今）变轻。黑色实线是最佳拟合模型，对应 **0.7‰**（另一站位 0.8‰）的冰期–间冰期海水成分变化。

**图 J｜Δ47 温度标定图**：横轴温度（开尔文，约 3–50 °C 范围），纵轴 Δ47（‰）。**负相关**：低温 Δ47 ≈ 0.8‰，高温更低。数据点来自无机标定、珊瑚、鱼耳石、土壤碳酸盐、腕足类、软体动物，**落在同一条曲线上**。

---

## 四、课堂补充

本节内容来自 `EART26201 - 08-Dec-transcript.md`（约 6,700 词），是幻灯片上**没有**的口头信息。

### 1. 课程收尾与考试相关的提示（最重要）

- **本周是最后一周**："this week's the final week. No lectures, no practicals next week." 只剩本周三上午在 **G12** 的 practical，**没有更多实验室工作**。
- **老师已经把往年考题（exam questions）上传到课程页面**："I've stuck some exam questions on … there is a little bit of text that goes with it … they may not match exactly to what you will get, but some of these are previous exams that we've actually done for this unit. So it should give you a fairly good indication of the sorts of things that you will get."
  - 👉 这就是仓库中 `Lecture/Past Papers/` 里的那批文件。
  - 📎 背景补充（我的核对结果）：`example exam questions.md` 里的 6 道例题**全部来自课程后半段的流体地球化学**（石膏溶解度与 K_sp/IAP、风化作用、酸性矿山排水的 pE 计算、碳酸物种分配、Fe 氧化半反应配平、Nernst 方程算 Mn³⁺/Mn²⁺）——**没有一道稳定同位素题**。但 **`EART26201 Jan 2025 exam with answers.md` 第 2 题就是一道 25 分的稳定同位素论述题**："Detail how oxygen isotopes in different archives (e.g. foraminifera, ice cores, pore waters) can be used to reconstruct past ocean temperature. Include in your discussion a description of the processes that can cause uncertainty in the temperature determination and how some of these may be circumvented."——这几乎就是本周讲座的完整复述。
  - 📎 该标准答案还给出了本周讲座**没提**的两个采分点，值得补记：(a) **死亡组合 ≠ 生活组合**——薄壳个体被选择性溶解、易搬运个体被差异性移除、外来搬运造成污染；(b) **生命效应（vital effect）**——某些种分泌的碳酸盐**不与水平衡**，必须选择完全平衡或已标定的种；此外**底栖有孔虫生活在约 4 °C 的底层水，没有理由认为冰期更冷，所以其变化可近似完全归因于冰量效应，用作标定**。这条"底栖 = 温度近似恒定 → 分离冰量效应"的论证在本周讲座里只是隐含，考试可以直接用。
- **老师会把所有 quiz 答案都放上去**："I will put all the quiz answers in there as well."
- 老师请大家填 **course unit survey**（当场没找到本单元的专属链接）。

### 2. 口头强调的重点与推导

- **α 为什么"看起来没用"而 δ 好用**：α = 1.00xxx，几位小数很难记；δ 就是把它 ×1000，得到整数级别的 per mil。**per mil 符号 = 百分号再多一个 0**。
- **1000·lnα 与 Δδ 可互换**："Thousand log alpha is essentially … dividing this back down from a thousand. So the delta difference … is essentially the same thing as thousand log alpha. You'll see them interchangeably on a y-axis of isotope charts."——这条是读图基本功。
- **SMOW 不是真海水**："It's not actually ocean water at all. It's actually a fabricated water with a specific composition, but it is very close to actually what present ocean water is."
- **除 Li 外 δ 都按重同位素命名**——这个"冷知识"幻灯片上没有。
- **氢分馏远大于氧的根本原因是相对质量差**（1/1 vs 2/16）。这道 quiz 题让不少同学答错："Gosh. Oh. Oh, interesting. Okay. Yes, it's because of the mass difference. That poxed a few of you."
- **哪一步是平衡、哪一步是动力学**：**云 → 雨基本纯平衡**；**海面蒸发 = 平衡 + 动力学叠加**。这直接解释了 **GMWL 是平衡线，而海水略偏离它**。
- **动力学分馏的三个控制变量**：湿度、温度、风速；**低湿度时最大**。
- **锯齿曲线与米兰科维奇**：约 10 万年周期来自**偏心率与轨道变化**；有多个周期但 10 万年最显著。
- **冰量效应的关键澄清**：变的**不是冰的同位素成分，而是冰的量**——"the actual composition of the ice stays broadly the same. It's just the amount of ice that changes. So it's kind of equally as light, but there's more of it. Therefore, it's the ocean."
- **为什么必须用底栖有孔虫**："The ocean floor temperatures are pretty consistently the same everywhere, so it's a good place to collect forams."
- **"两个过程，只有一个测量值"** 是整堂课的核心矛盾表述："we've got two processes and only one measurement." 孔隙流体与团簇同位素就是两条破解路径。
- **团簇同位素的测量要点**：**绝对不能把分子拆成单个原子**——"we don't want to split this up into individual atoms … because we lose the key bit of information."必须以 CO₂ 分子整体测 47/44。
- **课堂现场的近似算术**（值得学会）：老师看着分馏图口算——"the whole thing is 100 down to 20. Roughly 80 degrees C and 15 per mil roughly top to bottom. So you put those two numbers in, 0.75 per mil change, assuming that's a straight line, which it almost is, gives you a value of about 4 degrees C."

### 3. 随堂 Quiz 逐题（`lecture 10 quiz answers 2025.md` + 转写核对）

| # | 题目 | 正确答案 | 依据 |
|---|---|---|---|
| 1 | δ¹⁸O 记号表示什么？ | **相对于标准物的氧同位素比值**（ratio of oxygen isotopes relative to a standard） | 答案页勾选 + 转写"That is indeed a ratio 18 to 16 in that case" |
| 2 | 流体中氧同位素使用的标准是？ | **SMOW**（转写："the one I talked most about, although sometimes it is the other one"，另一个指 PDB） | 转写；答案页 OCR 截断 |
| 3 | 为什么氢的同位素分馏远大于氧？ | **氧的同位素之间质量差（相对）更小** | 答案页 + 转写 |
| 4 | 方解石–水分馏主要受什么控制？ | **温度（temperature）** | 转写："that's the whole point of it. It's temperature dependent fractionation" |
| 5 | 海水蒸发成云，同位素上会怎样？ | **云比海水轻，雨也比海水轻** | 转写："the cloud will be lighter … But the rain will also be a bit lighter than the original ocean. Because as well as having the equilibrium fractionation, you have the evaporation effect, which drives more of the lighter stuff off. But the evaporation doesn't really work the other way." |
| 6 | 米兰科维奇周期与什么有关？ | **轨道变化（orbital variation）** | 答案页 + 转写 |
| 7 | 哪些档案可以用来看米兰科维奇周期？ | **仅冰芯（ice cores only）** ⚠️ | **答案页 Slide 4 的更正**："Bit of confusion in the lecture (by me!). It is ice cores only because the other 2 can be palaeoclimate archives but they don't go back far enough in time to cover Milankovitch cycles."——课上老师口头说的是"all three"，随后自己发现说错并在 2025 版答案里更正。**以答案页为准。** |
| 8 | 冰量效应让你可以计算什么？ | **海洋的 δ¹⁸O（海水成分）** | 转写：冰的成分不变、量变，所以变的是海洋 |
| 9 | 孔隙流体提供了对什么的独立确认？ | **海洋的 δ¹⁸O** ✔（温度 ✘、压力 ✘、冰的 δ¹⁸O ✘） | 答案页勾选 + 转写 |
| 10 | 有孔虫作为古气候档案的问题是？ | **以上全部（all 3）**：壳体死后重结晶 / 不同年龄壳体混合 / 水柱中的深度影响环境温度 | 答案页勾选 |
| 11 | 碳酸盐团簇同位素为什么能绕过普通稳定同位素的解释难题？ | **只分析碳和氧同位素本身就能定出温度**（不需要外部参照） | 答案页勾选 + 转写"Very good. Yes, that's right" |

📎 背景补充：答案页幻灯片的 OCR 中**没有第 7、8 题的题面**（只有 Slide 4 的文字更正），上表第 7、8 题的题意是我根据转写复原的，**题面措辞可能与原卷略有出入**。

---

## 五、Practical 要点

本周三上午在 **G12** 的 practical 是**全课最后一次 practical**，也是**期末 practical**。两份答案文件内容互相印证：`final practical dec2025 answers-1.md` 是文字模范答案，`stable isotope practical answers 2025-1.md` 是对应的表格计算结果。老师在课上预告："we'll look at the hydrologic cycle on Wednesday, and we'll try and convert some Rayleigh fractionation into a sea level change and see if we can actually explain global paleoclimate changes by oxygen isotopes."

### 第 1 题：瑞利分馏——云中水汽与降雨的 δ¹⁸O 演化

**给定条件**：初始水汽 **δ¹⁸O = −10‰**；液–汽分馏 **Δ¹⁸O_(liquid−vapour) = 9.4‰**（即 ε = +9.4‰）。

**使用公式**：δ¹⁸O = δ¹⁸O₀ + Δ·ln f

**示范计算（f = 0.9，即损失 10% 质量）**：
- ln 0.9 = **−0.10536**
- δ¹⁸O(水汽) = −10 + 9.4 × (−0.10536) = **−10.9904‰**
- 从这团云中落下的雨：δ¹⁸O(雨) = −10.9904 + 9.4 = **−1.59039‰**

**答案文件的关键附注（原文）**："but assuming single step process here so always use initial water vapour of −10 regardless of f. (This gives a pretty good approximation of global water fractionation)."——即本题按**单步近似**处理，α 全程取常数、初始水汽固定为 −10‰。

**完整数值表**（来自 `stable isotope practical answers 2025-1.md` 的表格，δ 单位 ‰）：

| f（残余分数） | ln f | 水汽 δ¹⁸O | 降雨 δ¹⁸O |
|---|---|---|---|
| 1.0 | 0 | −10.000 | −0.600 |
| 0.9 | −0.10536 | −10.990 | −1.590 |
| 0.8 | −0.22314 | −12.098 | −2.698 |
| 0.7 | −0.35667 | −13.353 | −3.953 |
| 0.6 | −0.51083 | −14.802 | −5.402 |
| 0.5 | −0.69315 | −16.516 | −7.116 |
| 0.4 | −0.91629 | −18.613 | −9.213 |
| 0.3 | −1.20397 | −21.317 | −11.917 |
| 0.2 | −1.60944 | −25.129 | −15.729 |
| **0.1** | **−2.30259** | **−31.644** | **−22.244** |

**读表要点（评分要点）**：
1. 水汽与降雨**永远相差恰好 9.4‰**，雨在上（更重）。
2. **f 越小（雨下得越多）、剩余水汽越轻**，且**非线性加速变负**——这正是"极地降水为什么能到 −20 ~ −30‰"的定量解释。
3. **f = 0.1 时降雨 δ¹⁸O = −22.2‰**——这个数就是第 2 题里"冰盖成分"的来源。

### 第 2 题：从 1.5‰ 反推 LGM 海平面下降

**题面**：LGM 的碳酸盐记录到全球海洋 δ¹⁸O 为 **+1.5‰**。假设这个差异**完全**由海水以雪/冰形式损失所致，用第 1 题的 **Δ¹⁸O = 22.2‰** 计算被锁进冰盖的水的质量。假设今日海洋 δ¹⁸O = 0‰。

**解法**：
$$\delta^{18}O = \delta^{18}O_0 + \Delta \ln f$$
$$0 = 1.5 + 22.24\ \ln f$$
$$\ln f = -1.5 / 22.2 = -0.06757$$
$$f = e^{-0.06757} = \mathbf{0.9347}$$

**含义**：f = 0.9347 是**使海洋同位素组成改变 1.5‰ 所对应的剩余海水质量分数**，即海洋只剩下今日的 **93.47%**。

⚠️ **符号说明（重要）**：答案文件把"δ₀ = 1.5‰、δ = 0‰"这样写，是在**从 LGM 往今天倒着算**，同时用了正号的 Δ = +22.2‰。**物理上更正确的写法**是：海洋是残余储库、冰是被移走的产物，冰比海洋轻约 22.2‰，因此 ε_(ice−ocean) = **−22.2‰**，于是
δ_ocean(LGM) = 0 + (−22.2) × ln f = +1.5 → ln f = −0.06757 → f = 0.9347。
**两种写法数值完全相同**，但后者不会把"移走轻的产物 → 残余变重"的方向弄反。考试时建议写后者。

**海平面换算**：
- 世界大洋平均深度 = **3794 m**
- 粗略假设海洋面积不变，则 LGM 平均深度 = 0.9347 × 3794 = **3546 m**
- 海平面下降 = 3794 − 3546 = **约 248 m**（表格值 247.88 m）

**与观测对比与修正（这是本题的采分核心）**：
- 实测 LGM 海平面约低 **120 m** → 计算值是观测的**两倍**。
- **原因**：1.5‰ **并不是海水成分的真实变化**。按讲座，孔隙流体直接测量给出的海水成分变化只有 **0.7–0.8‰**（取 0.75‰）。
- 修正：**0.75 / 1.5 × 248 = 124 m** —— "Remarkably consistent with 120m!"
- 表格中对应的两个单元格就是缩放因子 **0.5** 与结果 **123.94 m**。

**必须写出的假设/局限（答案文件明确点名）**：
> "Note: assumption that ocean temperature constant – thermal expansion/contraction of oceans also plays a significant role in ocean volume."
即本计算假设海水温度不变，而海水的**热膨胀/收缩**同样显著影响海洋体积。

📎 背景补充（可加分的额外假设）：本计算还隐含 (a) 海洋面积恒定（实际海平面下降会出露大陆架，面积缩小）；(b) 冰盖成分全程恒为 −22.2‰（实际冰盖生长过程中成分也在变）；(c) 海洋充分混合、可视为单一储库。

### 数据表中一个未标注的数值

`stable isotope practical answers 2025-1.md` 的表格右下角有一个孤立数值 **0.9704455335485082**（= e^(−0.03)），**表格中没有任何标签说明它对应哪一问**，本笔记不做推测——**材料未说明**。

---

## 六、易错点 / 重点难点

1. **δ 与 R 混淆**。R 是**绝对比值**（如 ¹⁸O/¹⁶O ≈ 0.002），δ 是**相对于标准的千分偏差**。Quiz 第 1 题的四个选项里，"absolute ratio of oxygen isotopes"和"concentration of the heavy isotope"都是陷阱——δ 既不是绝对比值，也不是浓度。

2. **α 与 ε/Δ 的单位**。**α 无量纲且 ≈ 1.00x**；**ε ≈ (α−1)×1000、Δ ≈ δ_A − δ_B ≈ 1000 lnα，单位是 ‰**。写"α = 9.4‰"或"ε = 1.0094"都是错的。practical 里的 9.4‰ 对应 α = 1.0094。

3. **"重同位素富集"的方向判反**。牢记链条：**蒸发 → 水汽轻 → 液相/雨相对重 → 剩余云越来越轻 → 极地降水最轻**。以及**固相（碳酸盐）几乎总比与之平衡的水重**。Quiz 第 5 题的关键在于：云比海水轻是显然的，但**雨也比海水轻**——因为蒸发这一步的动力学效应把体系整体拉轻了，而"雨比云重 9.4‰"不足以补回来。

4. **平衡分馏与动力学分馏的温度依赖弄反**。**平衡分馏随温度升高而减小**（24 °C 碳酸盐–水约 28‰，90 °C 只有约 17–19‰；Δ47 也是低温大、高温小）。所以"高温体系同位素差异小"是通则。别记成"越热分馏越大"。

5. **哪一步是平衡、哪一步是动力学**。**云→雨 = 平衡**；**海面蒸发 = 平衡 + 动力学**。GMWL 是**平衡线**，所以**海水本身反而落在线外**、强蒸发湖泊沿更缓的蒸发线偏离。这个"反直觉"点很容易在论述题里丢分。

6. **VPDB 与 VSMOW 混用未换算**。水的 δ¹⁸O 报 VSMOW，碳酸盐的 δ¹⁸O 常报 VPDB。讲座里对 SPECMAP 曲线说"it's got a different standard, but it doesn't make any difference, it's just an offset"——那是在**只看相对变化**的语境下才成立；**若要代入 1000lnα = 17599/T − 29.64 求绝对温度，两个 δ 必须在同一标度上**。

7. **1.5‰ ≠ 温度信号**。这是本周最核心的考点。**有孔虫的 1.5‰ = 冰量效应（≈0.75‰）+ 温度效应（≈0.75‰ ≈ 4 °C）**。直接把 1.5‰ 全算成温度会把温度变化算成两倍（约 8 °C），把它全算成冰量则会把海平面下降算成 248 m（观测只有 120 m）。practical 第 2 题就是专门让你踩这个坑再爬出来。

8. **冰量效应里"变的是量不是成分"**。冰盖的 δ¹⁸O 冰期与间冰期差不多（都很负），改变的是**冰的体积**；因为体系封闭，冰多了 → 剩下的海水变重。Quiz 第 8 题考的就是这一点。

9. **米兰科维奇周期只有冰芯档案够长**。虽然地下水、树轮也是合法的古气候档案，但**时间跨度不够覆盖 10 万年周期**。课上老师口头说了"all three"，**2025 版答案页已更正为 ice cores only**——以答案页为准。

10. **瑞利分馏中 f 的定义与 ln f 的符号**。f 是**残余分数**（不是已经反应掉的分数！），f ≤ 1 所以 **ln f ≤ 0**。若把 f 记成"已降雨的比例"，整条曲线方向就反了。

11. **底栖 vs 浮游有孔虫**。**benthic = 底栖 = 洋底 = 温度稳定 = 首选**；planktonic = 浮游 = 随季节改变深度 = 温度被积分、不可靠。别记反。

12. **团簇同位素的独立性来源**。Δ47 之所以不需要知道水的成分，是因为它是**分子内部**的信息（¹³C–¹⁸O 成键概率相对随机分布的超出量），而不是"样品对参照物"的比较。写成"团簇同位素精度更高所以更好"是 Quiz 第 11 题的错误选项。

13. **速算温度时的除法**。0.75‰ 换算成温度是 **0.75 ÷ (15/80)**，也就是 **0.75 × 80/15 = 4 °C**；幻灯片印成 "0.75/(15\*80)" 会得到 0.000625，是排版错误。

---

## 七、本周术语表

### A. 本周（Week 10）术语

| 英文 | 中文 | 要点 |
|---|---|---|
| stable isotope | 稳定同位素 | 不衰变，比值变化来自分馏 |
| radiogenic isotope | 放射成因同位素 | 本周明确**不涉及**（Rb–Sr、Hf 等属 Week 2） |
| isotope fractionation | 同位素分馏 | 同一元素两种同位素的部分分离，产生比值不同的储库 |
| isotopic anomaly | 同位素异常 | 分馏造成的比值差异 |
| reservoir | 储库 | 可以是海洋/湖泊/地幔，也可以是一个矿物相 |
| equilibrium isotope fractionation | 平衡（同位素）分馏 | 源自**键能**差异；温度升高分馏减小 |
| kinetic isotope fractionation | 动力学（同位素）分馏 | 源自**速度/反应速率**差异；蒸发、扩散、逃逸 |
| mass dependent fractionation | 质量相关分馏 | ¹⁸O/¹⁶O 分馏约为 ¹⁷O/¹⁶O 的两倍 |
| mass-independent fractionation (MIF) | 质量无关分馏 | 取决于分子对称性；早期太阳系 O、S；大气 UV 反应 |
| fractionation factor (α) | 分馏系数 | α = R_A/R_B，无量纲，≈1 |
| delta notation (δ) | δ 记号 | (R_样/R_标 − 1)×1000‰，以重同位素命名 |
| per mil (‰) | 千分号 | 百分号多一个零 |
| standard | 标准物 | O/H→SMOW；C→belemnite (PDB)；S→troilite；N→大气 |
| SMOW / VSMOW | 标准平均海水 | 人工配制，δD = δ¹⁸O = 0‰，接近现今海水 |
| calibrate | 校准 | 把样品比值报到标准上的动作 |
| isotopically heavy / light | 同位素偏重 / 偏轻 | δ 为正 / 为负 |
| deuterium (D, ²H) | 氘 | 质量是普通 H 的两倍，所以 H 分馏远大于 O |
| Rayleigh fractionation | 瑞利分馏（瑞利蒸馏） | R/R₀ = f^(α−1)；产物一生成即移出 |
| fraction remaining (f) | 残余分数 | 0 < f ≤ 1，ln f ≤ 0 |
| meteoric water line (GMWL) | （全球）大气降水线 | δD–δ¹⁸O 图上的平衡分馏线；海水略偏离 |
| Epstein et al. (1953) / Craig (1965) | 碳酸盐–水温度计标定 | 1000lnα = 17599/T − 29.64 |
| foraminifera (forams) | 有孔虫 | 钙质壳，深海岩心中的主力档案 |
| benthic / planktonic | 底栖 / 浮游 | 底栖首选（洋底温度稳定） |
| recrystallisation | 重结晶 | 改变壳体原始 δ¹⁸O |
| bioturbation | 生物扰动 | 混合不同年龄壳体，低沉积速率区尤甚 |
| SPECMAP | 光谱制图计划 | 底栖有孔虫 δ¹⁸O 曲线，全球地层对比工具 |
| Last Glacial Maximum (LGM) | 末次冰盛期 | 约 2 万年前，有孔虫 δ¹⁸O 高出今日约 1.5‰ |
| Milankovitch cycles | 米兰科维奇周期 | 轨道/偏心率变化，最显著约 10 万年 |
| ice volume effect | 冰量效应 | 轻同位素锁入冰盖，海水变重；变的是**量**不是成分 |
| pore fluids | 孔隙流体 | 沉积物中滞留的古海水，直接给出海水 δ¹⁸O 变化 0.7–0.8‰ |
| advection / diffusion | 平流 / 扩散 | 压实驱水与扩散抹平，使孔隙流体法只对 LGM 有效 |
| clumped isotopes / rare isotopologues | 团簇同位素 / 稀有同位素体 | 含多于一个稀有同位素的分子 |
| stochastic distribution | 随机（统计）分布 | 团簇同位素的参照基准 |
| Δ47 | 大写 Δ47 | 质量 47（¹³C¹⁶O¹⁸O）相对随机分布的超出量；低温大、高温小 |
| bioapatite | 生物磷灰石 | 牙齿；恐龙体温 36–38 °C 的测定对象 |
| speleothem | 洞穴沉积（石笋等） | 碳酸盐档案 |
| archive | （古气候）档案 | 冰芯、地下水、树轮、湖泊沉积、石笋、有孔虫、珊瑚 |
| Glomar Challenger | 格罗玛·挑战者号 | 1960 年代第一艘深海钻探取心科考船 |

### B. 📎 背景补充：全课（Week 1–10）核心术语汇总

> ⚠️ 以下条目**不是本周材料的内容**，是我为期末复习整合的全课回顾，来源为各周讲义标题与关键词。细节以各周原讲义为准。

| 周次 | 英文 | 中文 | 一句话 |
|---|---|---|---|
| W1 | major / minor / trace element | 主量 / 次量 / 微量元素 | >1 wt.% / 0.1–1 wt.% / <0.1 wt.% |
| W1 | partitioning, partition coefficient (D) | 元素分配、分配系数 | 相容（D>1）与不相容（D<1） |
| W1 | chemical differentiation | 化学分异 | 行星尺度的元素再分配 |
| W2 | decay constant (λ), half-life | 衰变常数、半衰期 | 放射性定年的基础 |
| W2 | isochron | 等时线 | 母/稳定 vs 子/稳定 作图，斜率给年龄、截距给初始比值 |
| W2 | model age, depleted mantle | 模式年龄、亏损地幔 | Nd 同位素演化图 |
| W3 | equilibrium, Gibbs free energy | 平衡、吉布斯自由能 | 系统组成不随时间变化 |
| W3 | phase diagram, phase rule | 相图、相律 | P–T–X 空间的稳定域 |
| W4 | partial melting, fractional crystallisation | 部分熔融、分离结晶 | 相图的岩浆系统应用 |
| W4 | solid solution (e.g. X_An) | 固溶体（如斜长石钙长石分数） | 成分随温度连续变化 |
| W5 | kinetics vs thermodynamics | 动力学 vs 热力学 | "能不能" vs "多快" |
| W5 | diffusion, activation energy | 扩散、活化能 | 扩散剖面反演时间尺度 |
| W6 | solvent, ion, activity | 溶剂、离子、活度 | 流体地球化学开篇 |
| W7 | solubility product (K_sp), IAP | 溶度积、离子活度积 | IAP<K_sp 欠饱和，>K_sp 过饱和 |
| W7 | complexing, common ion effect | 络合、同离子效应 | 金属迁移机制 |
| W8 | acidity / alkalinity | 酸度 / 碱度 | 给质子能力 / 接受质子能力 |
| W8 | pKa, buffering | 酸解离常数负对数、缓冲 | 强度 ≠ 浓度 |
| W9 | oxidation state, OIL RIG | 氧化态 | 失电子氧化、得电子还原 |
| W9 | pE / Eh, Nernst equation | pE / Eh、能斯特方程 | pE = 16.9 Eh |
| W9 | pE–pH diagram | pE–pH 图 | 判别元素赋存形态（如 Fe、Mn、As） |
| W10 | δ, α, Rayleigh, ice volume effect, Δ47 | 见上表 A | 全课收尾 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `lecture 10 stable isotopes 2025-2.md`，"Isotopic changes associated with precipitation" 一节（出现两次） | "the δ¹⁸O of rainfall **increases** from equator to pole."（同页连续出现两遍） | **方向写反**。转写、全球降水分布图、瑞利分馏计算全部表明降水 δ¹⁸O 从赤道的约 0‰ 降到极区的 −20 ~ −30‰ | 应为 **decreases**（越向极地越负）。或改述为"降水的 ¹⁸O 亏损程度从赤道向极地增大" |
| 同上，"Summary of the really big question in paleoceanography" 一段 | "0.75‰ equates to 4C: (0.75/(15\*80) from figure below = 4)" | **算式写错**：0.75/(15×80) = 6.25×10⁻⁴，不等于 4 | 应为 **0.75 ÷ (15/80) = 0.75 × 80/15 = 4 °C**。转写中老师的口述逻辑（"80 °C 对应 15‰"）是对的，只是括号里的算式印错 |
| `EART26201 - 08-Dec-transcript.md`，讲碳酸盐–水温度关系图处 | "at 90 degrees C, that difference is only about **70 per mil**" | 数值不可能（90 °C 的分馏必须**小于** 24 °C 时的 28‰） | 代入 1000lnα = 17599/363.15 − 29.64 得 **约 18.8‰**；应为"about **17（或 18）** per mil"。属口误或自动转写错误 |
| `EART26201 - 08-Dec-transcript.md`，讲 SPECMAP 锯齿曲线处 | "it **jumps up quickly and then drops back down again slowly**, so that implies that glaciation, so this bit is relatively **slow**, and then it **spikes up** again as it deglaciates" | **前后自相矛盾**：先说"快升慢降"，后说"冰期缓慢、冰消快速" | 物理上正确的是**冰量缓慢累积（约 90 kyr）+ 快速冰消（terminations）**。δ¹⁸O 曲线的升降方向还取决于纵轴是否倒置，作答时应描述"缓慢建冰、快速消融"而不要死记曲线方向 |
| `EART26201 - 08-Dec-transcript.md`，讲团簇同位素处 | "this bond here, the **carbon 13 to carbon 18** bond" | 不存在"碳-18" | 应为 **¹³C–¹⁸O 键**（碳-13 与氧-18 之间的键）。幻灯片写的是正确的 "¹³C–¹⁸O bond" |
| `lecture 10 quiz answers 2025.md` Slide 4 vs 转写 quiz 第 7 题 | 转写中老师口头答"you can use ground water and tree rings. So all three"；答案页写"It is **ice cores only**" | 课上口头答案与书面答案**不一致**（老师本人已在答案页承认："Bit of confusion in the lecture (by me!)"） | **以答案页为准：仅冰芯**。地下水与树轮虽是合法古气候档案，但时间跨度不足以覆盖 10 万年米兰科维奇周期 |
| `final practical dec2025 answers-1.md` 第 2 题 | "-1.5/**22.24** = -0.06757" | **算术与所写数字不符**：−1.5/22.24 = −0.06745；−0.06757 实际是 −1.5/**22.2** | 表格文件 `stable isotope practical answers 2025-1.md` 中的值 −0.067567567… 确认实际使用的是 **22.2‰**。前一行写的 "22.24" 应统一为 **22.2**（该值来自第 1 题 f = 0.1 时的降雨 δ¹⁸O = −22.244‰，四舍五入取 22.2）。对最终结果影响 <0.1 m，不改变结论 |
| `final practical dec2025 answers-1.md` 第 2 题符号约定 | "where δ¹⁸O₀ = 1.5‰, δ¹⁸O = 0‰ and 22.2‰ to give: 0 = 1.5 + 22.24 ln f" | **物理方向倒置**：把 LGM 当作起点、今日当作终点，同时对"移走的冰"使用了正的 Δ（相当于移走重同位素） | 数值结果不受影响（两处符号相互抵消），但正确写法应为：海洋为残余相、冰为产物且比海洋轻 22.2‰，即 ε = **−22.2‰**，δ_ocean = 0 + (−22.2)ln f = +1.5 → ln f = −0.06757 → f = 0.9347。建议按后者作答以免方向判断出错 |
| `stable isotope practical answers 2025-1.md` Sheet1 最后一个单元格 | "0.9704455335485082" | **无任何标签**，无法确定对应哪一问（数值上等于 e^(−0.03)） | **材料未说明**，本笔记不做推测 |
| `lecture 10 stable isotopes 2025-2.md` 多处 | 大量 δ 符号、下标、公式在 PDF→md 转换中丢失（如 "18O" 缺 δ、"R A 1 … f R 0"、"L .10092"） | 转换损坏而非原件错误 | 已按上下文与转写复原为：δ¹⁸O、R/R₀ = f^(α−1)、α_(L−V) = 1.0092 / 1.074。**复习时若有疑问请以原 PDF 为准** |
| `lecture 10 quiz answers 2025.md` | OCR 中**缺第 7、8 题的题面**，第 2 题的选项也被截断 | 图片 OCR 不完整 | 已按转写复原题意（见第四节表格），措辞可能与原卷有出入 |
