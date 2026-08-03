# EART26201 Principles of Geochemistry — Week 02 学习笔记

## 一、本周主题

**本周主题：放射成因同位素——岩石的年龄与来源（The age and provenance of rocks: radiogenic isotopes）。**

判定依据：本周讲义 `EART26201_Lecture2_RT_v2.md` 每一张分节页的标题都是 "The age and provenance of rocks: radiogenic isotopes"；课堂录音开头老师亦明确说 "this week we will be talking about radiogenic isotopes and what they can tell us about the age and provenance of rocks"；配套 Practical 的标题是 "Isochron dating and isotopic tracers of magma sources"。三份材料完全一致。

本周讲座分五个部分（Slide 6 的 synopsis）：**Part 1 引论**（元素与同位素、核素图、衰变的两大用途）→ **Part 2 放射性衰变**（核稳定性、三种衰变机制、衰变常数与半衰期、地质年代学基本方程）→ **Part 3 定年与等时线图** → **Part 4 地壳与地幔的同位素演化**（Sr 与 Nd 演化图）→ **Part 5 物源示踪与地幔阵列**。延伸阅读：Misra 第 10 章（理论概览）、White 第 8 章（详尽全面）。

**在全课四大骨架中的位置。** 本课的四大块是「热力学与相图 / 反应动力学与扩散 / 酸碱溶解度与氧化还原 / 放射性与稳定同位素」。本周属于**第四块「放射性与稳定同位素」**中的**放射成因（radiogenic）**一支——即用母体—子体衰变体系做**定年（geochronology）**和**储库示踪（tracing）**。这一块的另一支「稳定同位素与碳定年」排在学期末（大纲 Week 12），本周先把衰变方程、等时线、储库演化这套骨架立起来，后面讲 δ 值分馏时会反复对照：**放射成因同位素比值只随时间与混合改变，稳定同位素则随分馏改变**——这是两支最根本的分界。

**与 Week 01 的衔接。** 讲义和录音在四处显式回指 Lecture 1：（1）**元素分类**（siderophile 亲铁 / chalcophile 亲硫 / lithophile 亲石 / atmophile 亲气）与周期表按 Z 排列——由此引出「同一元素的不同同位素只差中子数 N」；（2）**Oddo–Harkins 规则**（Slide 8 明写 "Oddo-Harkins rule in Lecture 1"）——本周把它落到核物理层面；（3）**分配系数 D 与相容/不相容性**（Slide 20 明写 "Partition coefficients are discussed in Lecture 1"）——这是**等时线能成立的物理前提**：不同矿物之所以在 x 轴上散开，正是因为 D_Rb/D_Sr 在黑云母与长石中差别巨大；（4）**微量元素模型**（Slide 27 "Trace elements tell the same story"）——Sr 同位素演化图讲的故事，和 Week 01 用不相容元素论证地壳—亏损地幔互补的故事是同一个。

Practical 层面也直接接续：Practical 1 做的是**元素数据的线性混合线**，Practical 2 Q2c 特意提醒「同位素图上的混合线是**弯曲的**，因为两端元的 Sr 含量不同」——两周对照着记。

> ⚠️ **周次编号提示**：课程大纲（spec）把 "The age and provenance of rocks: radiogenic isotopes" 列在 Week 3，把 "The geochemist's periodic table" 列在 Week 2。这是因为 spec 从 Week 2 起算并含 reading week，而文件夹按 Week 1–10 连续编号。**本笔记库统一采用文件夹编号，故本周为 Week 02。**

---

## 二、核心概念

### 1. 元素、同位素与核素图（nuclide chart）

- **元素**由**质子数 Z**（原子序数）唯一确定，周期表按 Z 排列。
- **同位素（isotopes）**：Z 相同、**中子数 N 不同**的核素。大多数元素都有多个同位素。
- **Karlsruhe 核素图（Karlsruhe Nuclide Chart）**：y 轴为质子数 Z，x 轴为中子数 N，每一个方格是一个核素；同一水平行是同一元素的全部同位素。不同颜色代表核素的状态（稳定 / 各类放射性衰变模式）。这是查任一核素性质的标准工具图。

### 2. 核稳定性（nuclear stability）

- 核由带正电的**质子**和不带电的**中子**构成；**质量数 A = Z + N**。
- **轻核**：稳定核素大致落在 **N ≈ Z** 线上；**重核**：中子相对过量，稳定带向 N > Z 一侧偏离（材料说在原子序数约 30 以上开始明显偏离）。核素图上稳定核素构成一条紫色的"稳定谷"带。
- **偶数更稳**：Z 和/或 N 为**偶数**的核素更稳定；当 Z 或 N 等于**幻数（magic numbers）**时稳定性最高。这正是 Week 01 学的 **Oddo–Harkins 规则**（偶原子序元素在太阳系中丰度高于相邻奇原子序元素）的核物理根源。
- 📎 **背景补充**：录音里念出的幻数序列被转写弄乱了，标准的幻数是 **2, 8, 20, 28, 50, 82, 126**（对应核壳层闭合）。Z 与 N 同时为幻数的"双幻核"（如 ⁴He、¹⁶O、⁴⁰Ca、²⁰⁸Pb）异常稳定——²⁰⁸Pb 恰好是 ²³²Th 衰变链的终点，不是巧合。

### 3. 放射性衰变（radioactive decay）与三种机制

**大多数核素其实是不稳定的**，会自发衰变。关键是老师强调的一点：**不稳定母核衰变出的子核不一定稳定**，它可以继续衰变，一级一级往下，直到抵达一个稳定核素为止（衰变链）。不同核素的衰变速率跨度极大——有的只存在几分之一秒，有的慢到半衰期上千亿年。衰变速率取决于核素的**能态（energy states）**。

三种机制（Slide 10，配核素图上的移动方向理解）：

| 机制 | 放出的粒子 | Z 的变化 | N 的变化 | 在 N–Z 图上的移动 |
|---|---|---|---|---|
| **α 衰变（alpha decay）** | α 粒子 = 2 质子 + 2 中子 = He 核 | −2 | −2 | 沿 45° 向左下方跳 |
| **β 衰变（beta decay）** | β 粒子 = 电子（β⁻）或正电子（β⁺） | ±1 | ∓1 | 沿反 45° 方向左右移动，A 不变 |
| **γ 衰变（gamma decay）** | γ 射线（光子） | 0 | 0 | 原地不动 |

γ 衰变是**激发态原子核退激到更稳定能态**的过程，Z、N 都不变。

📎 **背景补充**：β⁻ 是核内一个中子变质子（Z+1, N−1），把富中子核推回稳定谷；β⁺（或电子俘获 EC）是质子变中子（Z−1, N+1），修正富质子核。本周两个主力体系正好各占一种：⁸⁷Rb → ⁸⁷Sr 是 β⁻，¹⁴⁷Sm → ¹⁴³Nd 是 α。

### 4. 放射成因同位素的两大用途

老师在 Part 1 就把全周的逻辑主线摆出来了，务必先抓住：

**（A）定年（geochronology）** —— 放射成因同位素的丰度通过衰变常数 λ 与**时间 t** 挂钩。例：苏格兰高地的加里东造山运动（Caledonian Orogeny）岩石定出 **400–425 Ma**，说明当时苏格兰有一条可与今日喜马拉雅类比的山链。

**（B）物源示踪（provenance / tracing）** —— **同位素在高温过程（部分熔融、结晶）中几乎不发生分馏**，理由用 Week 01 的分配系数语言说就是 **D(⁸⁷Sr) ≈ D(⁸⁶Sr)**（同一元素，化学行为几乎相同）。因此同位素比值是**被动示踪剂（passive tracers）**，能"记住"源区；不同地球化学储库各有特征同位素组成。除岩石记录外，Nd 同位素还可**追踪洋流**（Slide 5，van de Flierdt et al. 2016）与量化储库间通量。完整因果链见第四节第 12–13 条。

> ⚠️ 注意区分：**元素**会分馏（Rb 与 Sr 行为不同，Rb 更不相容），**同一元素的同位素**不分馏（⁸⁷Sr 与 ⁸⁶Sr 行为相同）。整个示踪逻辑全靠这一条。

### 5. 「系统（system）」的定义——本周最关键的定义

老师专门重复了两遍：

> **A system is a part of a sample that has remained chemically closed for the duration of T.**
> 系统 = 样品中在整个时长 T 内**保持化学封闭**的那一部分。

系统的尺度取决于测试手段，可以逐级细分：

**露头（outcrop）→ 全岩样品（whole-rock samples）→ 单个矿物颗粒（individual mineral grains）**

要把一块岩石里的长石、黑云母、石英当作各自独立的系统，就必须假定它们各自**没有元素进出**。对新鲜岩石样品，这通常是合理假设。

### 6. 等时线（isochron）

**等时线 = 一组具有相同 t 和相同初始 (D/S)₀ 的子系统在 (N/S, D/S) 图上连成的直线。**

它解决的是一个纯数学困境：地质年代学基本方程里有**两个未知数**（t 和初始比值 (D/S)₀），却只有**一个方程**。解法是同时测**多个同源同龄的子系统**：它们共享同一个 t 和同一个 (D/S)₀，于是 t 与 (D/S)₀ 可以被**同时求解**——斜率给 t，截距给 (D/S)₀。

**两条假设（Slide 19）**：

1. **t = 0 时全系统同位素均一**——即所有子系统的初始 (D/S)₀ 相同。老师给的均一储库例子：行星吸积前的太阳系、开始冷却前的岩浆房。
2. **系统在整个 t 内保持封闭**——N、D、S 都没有得失，比值的变化**只能**来自放射性衰变。

图形上的演化过程见第三节图 D；核心结论是 **等时线越陡 = 样品越老**。

**判据（老师特别澄清的逻辑方向）**：如果点**排不成一条直线**，就说明系统**没有保持封闭**，此时**无法**求出年龄。但**反过来不成立**——排成直线并不必然证明系统封闭（可能是混合线，见 Practical Q2）。

### 7. 储库的同位素演化（Sr 与 Nd）

核心因果链（以 Rb–Sr 为例）：地幔部分熔融 → **Rb 不相容**，优先进入熔体 → 熔体（→ 大陆地壳）**Rb/Sr 高**、残留的**亏损地幔 Rb/Sr 低** → 因为 ⁸⁷Rb 衰变成 ⁸⁷Sr，Rb/Sr 高的储库其 **⁸⁷Sr/⁸⁶Sr 随时间涨得更快** → 于是今天**大陆地壳 ⁸⁷Sr/⁸⁶Sr 高、亏损地幔低、BSE 居中**（BSE = Bulk Silicate Earth 硅酸盐地球总体 = 全地球减去地核 = 地幔 + 地壳）。一句话总结：**今天测到的同位素比值，记录的是过去的母/子元素分馏事件。**

**Sm–Nd 体系是完全对称的反例**（Slide 32）：初始 (¹⁴³Nd/¹⁴⁴Nd)₀ 从**球粒陨石（chondrites）**估计，因为 **Sm 与 Nd 都是难熔元素（refractory）**，而 Rb 是**挥发性（volatile）**元素；且**母体 ¹⁴⁷Sm 比子体 ¹⁴³Nd 更相容**（与 Rb–Sr 恰好相反）。因此**亏损地幔演化到高 ¹⁴³Nd/¹⁴⁴Nd，大陆地壳演化到低 ¹⁴³Nd/¹⁴⁴Nd**。两个体系的完整对照见第六节第 9 条。

### 8. 地幔阵列（mantle array）

在 **¹⁴³Nd/¹⁴⁴Nd（y）vs ⁸⁷Sr/⁸⁶Sr（x）** 图上，绝大多数玄武岩落在一条**负相关**的带上（详细读图见第三节图 G）。四类端元：**亏损地幔 / MORB** 在左上，**大陆地壳**在右下（"enriched 富集"端），**OIB** 居中接近 **BSE**，**大陆玄武岩**因受地壳混染沿阵列向右下拖尾。

**为什么 OIB 接近 BSE？** —— **俯冲再循环（subduction recycling）**：俯冲的岩石圈被卷回对流地幔，这些再循环物质把亏损地幔**重新富集**，造出接近 BSE 的组成，再在热点下部分熔融喷出（Slide 37, Koppers et al. 2021）。老师强调这只是一阶图像，细节上"还有很多不确定性"（图上标注 "Recycled crust?"、"Primitive mantle?"）。

---

## 三、公式与图表

### 3.1 公式（保留原文形式 + 逐项解释）

**(1) 衰变速率定律**

```
dN/dt = −λN
```

- `N`：**正在衰变的母核素的数目**（number of decaying nuclides），量纲为个数（或摩尔数、浓度）。
- `λ`：**衰变常数（decay constant）**，单位 **yr⁻¹**（每年）；物理含义是**单位时间内每个母核发生衰变的概率**。
- 负号：N 随时间**减少**。
- 适用条件：λ 是核性质，**与温度、压力、化学状态无关**——这正是同位素定年可靠的根本原因。

**(2) 积分形式**

```
ln(N/N₀) = −λt        等价于        N = N₀ e^(−λt)
```

- `N₀`：t = 0 时刻母核数目。
- 曲线为**指数衰减**。

**(3) 半衰期**

```
t½ = ln2 / λ
```

- `t½`：N 减半所需时间。ln2 = 0.6931。
- **典型数值核对**（用课程给的 λ）：
  - ⁸⁷Rb：λ = 1.42 × 10⁻¹¹ yr⁻¹ → t½ = 0.6931/1.42×10⁻¹¹ = **4.9 × 10¹⁰ yr**（约 500 亿年，录音说"about 5×10¹⁰"，一致）。
  - ¹⁴⁷Sm：λ = 6.54 × 10⁻¹² yr⁻¹ → t½ = **1.06 × 10¹¹ yr**（录音说"just over 1×10¹¹"，一致）。

**(4) 子体的生成量**

```
D* = N₀ − N                →                D* = N(e^(λt) − 1)
```

推导（录音里老师口述的那一步）：D* = N₀ − N，而 N₀ = N e^(λt)，代入得 D* = N e^(λt) − N = N(e^(λt) − 1)。
注意 **D\* 用现今剩余的 N 表达**，这非常重要——因为我们能测的是**今天的** N，不是 N₀。

**(5) 加上初始子体**

```
D = D₀ + N(e^(λt) − 1)
```

- `D₀`：t = 0 时体系中**已经存在**的子体核素数目。老师强调："it's very very rare that all of the D is only created by radioactive decay"——绝大多数体系一开始就有子体元素，必须扣掉。

**(6) 地质年代学与放射成因同位素地球化学的基本方程（fundamental equation）**

```
D/S = (D/S)₀ + (N/S)(e^(λt) − 1)
```

- `S`：一个**非放射成因（non-radiogenic）的稳定同位素**——它既不衰变，也不由别的核素衰变产生，所以其绝对量恒定，可作分母。
- 为什么用比值：**质谱（mass spectrometry）测同位素比值远比测绝对浓度精确、容易**。
- 这就是 Slide 12 标的 "The fundamental equation of geochronology and radiogenic isotope geochemistry"。

**(7) Rb–Sr 体系的等时线方程**

```
⁸⁷Sr/⁸⁶Sr = (⁸⁷Sr/⁸⁶Sr)₀ + (⁸⁷Rb/⁸⁶Sr)(e^(λt) − 1)
```

对应直线 **y = a + bx**：

| 直线元素 | 对应量 | 地质含义 |
|---|---|---|
| y | ⁸⁷Sr/⁸⁶Sr | 现今测得的 Sr 同位素比值 |
| x | ⁸⁷Rb/⁸⁶Sr | 现今测得的母/子（归一化）比值，反映矿物的 Rb/Sr 分配 |
| a（截距 intercept） | (⁸⁷Sr/⁸⁶Sr)₀ | **初始 Sr 同位素比值 → 源区信息** |
| b（斜率 slope） | e^(λt) − 1 | **含年龄信息** |

**(8) 由斜率反解年龄**

```
t = ln(slope + 1) / λ
```

（Practical 里的四步："Add 1 → take natural logarithm ln() → Divide by λ → Convert to Ga"。）

**(9) 同位素混合（Practical Q2c）**

设 A 为加入的地壳熔体质量分数，下标 c = crust，m = mantle：

```
Sr_from_crust  = A × Sr_c
Sr_from_mantle = (1 − A) × Sr_m
Sr_mix         = A×Sr_c + (1−A)×Sr_m
f_c            = Sr_from_crust / Sr_mix          （Sr 元素来自地壳的比例）
f_m            = Sr_from_mantle / Sr_mix
(⁸⁷Sr/⁸⁶Sr)_mix = f_c × (⁸⁷Sr/⁸⁶Sr)_c + f_m × (⁸⁷Sr/⁸⁶Sr)_m
```

- **关键点**：同位素比值必须按**元素的贡献比例 f**加权，**不能**按质量分数 A 加权。因为两端元 Sr 含量不同（698 vs 150 µg/g），所以 **f_c ≠ A**，混合线在同位素图上是**弯曲的双曲线**，而不是 Practical 1 中元素—元素图上的直线。

### 3.2 图表（文字详解）

**图 A：衰变曲线（Slide 9/11）**
- y 轴：剩余核素数 N（从 100 起，即 N₀ = 100）；x 轴：**半衰期的个数**（number of half-lives）。
- 曲线：单调下降的**指数曲线**。1 个半衰期后剩 50，2 个后剩 25，3 个后 12.5……
- 同图常叠加一条**镜像上升**的曲线，代表**稳定子体的累积**——子体的增长精确镜像母体的衰减（因为 D* = N₀ − N）。
- 读法：读某一时刻的 N/N₀，或反过来由 N/N₀ 读经过了几个半衰期。

**图 B：核素稳定图 N–Z（Slide 8/10）**
- y 轴：质子数 Z；x 轴：中子数 N。
- 图中画有 **N = Z 对角线**；**紫色带**是稳定核素的分布区。轻核紧贴 N = Z；Z 超过约 30 后，稳定带**向 N > Z 一侧弯离**对角线（重核需要更多中子来稀释质子间库仑斥力）。
- 三种衰变在图上是三个方向的**箭头**：α 沿左下 45°（ΔZ = −2, ΔN = −2）；β 沿左上或右下的反 45°（Z 与 N 一增一减）；γ 为原地不动的点。
- 读法：给定一个不稳定核素的位置，判断它离稳定带哪一侧，就能预测它会走哪种衰变把自己拉回稳定谷。

**图 C：地质情境示意图（Slide 13）**
- 纵向时间轴：**底部 = 地球形成**（T = 地球年龄），**顶部 = 今天（t = 0）**。
- 中间某高度：**目标岩石形成于年龄 t（t < T）**——这一刻岩石里已经继承了一定量的子体 **D₀** 和母体 **N₀**，"放射性时钟从此启动"。
- 从 t 到今天：N 衰变减少至今天的 **N**，同时生成 **D\***。
- 今天测到的总子体：**D = D₀ + D\***。
- 读法：这张图是理解"为什么必须扣掉 D₀"的图形化说明——等时线的截距就是在替你扣 D₀。

**图 D：等时线构建图（Slide 21）**
- x 轴：N/S（如 ⁸⁷Rb/⁸⁶Sr）；y 轴：D/S（如 ⁸⁷Sr/⁸⁶Sr）。
- **t₀**：所有样品点排成一条**水平线**，其 y 值即 (D/S)₀。
- 每个点随时间沿一条**斜率为 −1 的轨迹**向左上移动（丢一个 N 就得一个 D）。
- **t₁**：点仍共线，直线斜率为正 → 第一条等时线。
- **t₂**：更陡的第二条等时线。所有等时线**交于同一点**，即 x = 0、y = (D/S)₀ 的截距点（该点无母体，永不演化）。
- 读法：**斜率 → 年龄；截距 → 初始比值 → 源区**。

**图 E：Sr 同位素演化图（Slide 28–30）**
- y 轴：⁸⁷Sr/⁸⁶Sr，量程"略低于 0.70 到 0.72 左右"；x 轴：**T = 距今时间（Ga）**，**0 在右（今天），4.6 Ga 在左（地球形成）**。
- **起点**：4.6 Ga 处一个点，BSE 的初始 ⁸⁷Sr/⁸⁶Sr，**由陨石估计**。
- 从起点发出三条线：
  - **BSE（粉色线）**：中等斜率，一路演化到今天的 BSE 值。
  - **大陆地壳（Continental Crust）**：从约 3 Ga 处**折离 BSE 向上陡升**（Rb/Sr 高 → ⁸⁷Sr/⁸⁶Sr 涨得快），今天位于**最上方**。
  - **亏损地幔（Depleted Mantle，灰线）**：从同一折点**向下缓升**（Rb/Sr 低），今天位于**最下方**。
- **怎么读结论**：现今的大陆地壳组成可由**出露的变质岩和侵蚀产生的沉积物**测得（例如去喜马拉雅这种新近造山带采样）；现今的亏损地幔组成可由**钻探或拖网（dredged）样品**测得。用衰变方程把两者**各自往回外推**，它们与 BSE 曲线**相交的时刻就是"模式年龄（model age）"**——即造出大陆地壳与亏损地幔的那次熔融事件的时间，示意图上约 **3 Ga**。
- **老师明确的保留**：现实远比这复杂——**地幔熔融与大陆生长是连续进行的**，不是一次性事件；真实图上会有多期地壳抽取线。"but you don't need to worry about that for now"。

**图 F：Nd 同位素演化图（Slide 32）**
- 与图 E 结构完全相同，只是 y 轴换成 **¹⁴³Nd/¹⁴⁴Nd**，起点由**球粒陨石**估计。
- **上下关系反转**：**亏损地幔在上（高 ¹⁴³Nd/¹⁴⁴Nd）**，**大陆地壳在下（低）**，因为 **¹⁴⁷Sm（母体）比 ¹⁴³Nd（子体）更相容**。

**图 G：地幔阵列（Slide 36）**
- x 轴：⁸⁷Sr/⁸⁶Sr；y 轴：¹⁴³Nd/¹⁴⁴Nd。
- **BSE** 是参考点（老师用红点标出）。
- 数据沿一条**从左上到右下的负相关带**分布：
  - **左上（西北）**：Depleted Mantle / **MORB**。
  - **中部**：**OIB**（地幔柱来源，靠近 BSE）。
  - **右下**：**大陆地壳**（enriched），以及被地壳混染的**大陆玄武岩**拖尾。
- 读法：一个样品在图上的位置直接给出其源区的"亏损—富集"程度以及被地壳混染的程度。

**图 H：苏格兰第三纪火成岩（Slide 38–39）**
- 同样是 Nd–Sr 图，叠加 MORB / 亏损地幔参考框（左上角）。**最亏损的苏格兰第三纪熔岩**与 MORB 大体相似。
- **Skye 的熔岩**：趋向**低 ¹⁴³Nd/¹⁴⁴Nd + 低 ⁸⁷Sr/⁸⁶Sr** → 与**下地壳（Lower Continental Crust）**混染一致。
- **Rum 的火成岩**：**低 ¹⁴³Nd/¹⁴⁴Nd + 高 ⁸⁷Sr/⁸⁶Sr** → 与**上地壳（Upper Continental Crust）**混染一致。
- 地质背景与解读见第四节第 18–19 条。

**图 I：夏威夷（Slide 40–41）**
- 同为 Nd–Sr 图，叠加 BSE 与 MORB 参考框。
- **火山生命周期各阶段熔岩组成不同**：早期与晚期的 **Alkalic Pre-Shield 和 Post-Shield**（碱性前盾/后盾阶段）相对**亏损**，靠近 MORB；主生长期的 **Tholeiitic Shield**（拉斑玄武岩盾阶段）更**富集**，靠近 BSE（地幔柱信号最强）。
- 组成变化主要反映**太平洋板块相对下伏地幔柱的移动**；此外**地幔本身也是不均一的**。

---

## 四、课堂补充

以下均为讲义幻灯片上没有、老师口头讲出的内容。

**1. 本周的授课节奏与考核提示。** 老师开场即说："we've got quite a bit to go through today"——本周内容量大。讲座在周一，**周三是两小时 workshop，专门"working with some of the equations that we're going to look at today"**。老师在结尾又重复："we will work on a couple of questions related to that on Wednesday so if you have questions on any of that please do ask on Wednesday"。即：**方程的操作性训练全部放在 Practical，讲座只给框架**。

**2. 定年的"可用范围"经验法则（幻灯片上没有，考试可能考的数值感）。** 老师解释了为什么地球化学常用的体系都是**超长半衰期**：如果半衰期很短，放射性元素早就衰变光了，就无法给老岩石定年。他给出经验法则：

> **一个体系大致能定到其半衰期的 6–7 倍那么老的岩石。**

并举了反例：**¹⁴C 不在这张表上**，因为它只能往回追很短的时间尺度。（⚠️ 录音这里说成 "a couple of million years"，与 ¹⁴C 的实际能力矛盾，见勘误表第 2 条。）

**3. 每个体系的口头细节（Slide 14 表格的展开）。**

| 体系 | 衰变方式 | λ | t½ | 测量比值（归一化同位素） |
|---|---|---|---|---|
| ⁸⁷Rb → ⁸⁷Sr | β⁻ | 1.42 × 10⁻¹¹ yr⁻¹ | ≈ 5 × 10¹⁰ yr | ⁸⁷Sr/**⁸⁶Sr** |
| ¹⁴⁷Sm → ¹⁴³Nd | α（放出一个 He 核） | 6.54 × 10⁻¹² yr⁻¹ | 略高于 1 × 10¹¹ yr | ¹⁴³Nd/**¹⁴⁴Nd** |
| ²³²Th → ²⁰⁸Pb | α（衰变链产 He） | — | 见勘误第 1 条 | ²⁰⁸Pb/**²⁰⁴Pb** |
| ²³⁸U → ²⁰⁶Pb | α（衰变链产 He） | — | 见勘误第 1 条 | ²⁰⁶Pb/**²⁰⁴Pb** |

- 老师明确说明 **⁸⁶Sr 就是"用来归一化的那个稳定同位素"**。
- **老师当场指出幻灯片上有一个印刷错误**："it's a typo here it should be ²⁰⁶Pb here for the uranium over ²⁰⁴Pb"——即 ²³⁸U 那一行的测量比值被误印成了 ²⁰⁸Pb/²⁰⁴Pb，应为 **²⁰⁶Pb/²⁰⁴Pb**。这是考试里容易被拿来出判断题的点。
- 关于 Slide 14 的脚注 †（"Very little ⁴He is produced by ¹⁴⁷Sm decay compared with ²³²Th or ²³⁸U"）：老师说 Th、U 体系在衰变链中会**产生 He，He 本身可以做一套独立的定年体系**，但"we won't be talking about that here"——**本课不考 (U-Th)/He 定年**。

**4. D = N(e^{λt} − 1) 的口头推导。** 老师是一步步推的，不是直接给结论：先写 D = N₀ − N（子体数 = 减少掉的母体数），再把 N₀ = N e^{λt} 代进去。理解这一步的意义在于：**我们永远测不到 N₀，只能测今天的 N**，所以必须把方程改写成只含现今可测量的形式。

**5. 为什么要除以一个稳定同位素 S——纯粹是仪器层面的理由。** 老师："in general when we do mass spectrometry it's easier for us to measure the ratio of two isotopes than measuring the absolute concentration of an isotope"。并强调 S 必须是**既不衰变、也不是别的元素衰变产物**的同位素。

**6. 一个方程两个未知数——本周的方法论核心。** 老师把这一点讲得很慢："we can solve for T except we have one equation and two unknowns"，未知的是 **t** 和**先验未知的 (D/S)₀**。破解办法："if we measure multiple related systems with the same t and (D/S)₀ then both t and (D/S)₀ can be determined simultaneously"——**只要找到一组同源同龄的子系统，两个未知数就能同时解出**。等时线图正是这个思路的图形实现。

**7. 关于"系统"的定义，老师主动重复了一遍**（"so I'll repeat it"），说明这是他认为最容易被忽略、也最重要的定义。他还具体演示：要把某块花岗岩里的**长石、黑云母、石英**当作三个系统，就得保证"no elements went in, no elements came out"。

**8. 等时线上样品为什么会在 x 轴上散开——回到 Week 01 的 D。** 老师用花岗岩举例，讲得非常口语化：

> **黑云母（biotite）：Rb 很喜欢进黑云母，Sr 不太愿意 → ⁸⁷Rb/⁸⁶Sr 高（D_Rb/D_Sr 高）。**
> **长石（feldspar）：Sr 很喜欢进长石，Rb 不太愿意 → ⁸⁷Rb/⁸⁶Sr 低（D_Rb/D_Sr 低）。**

**没有这种分配差异，所有点会挤在 x 轴同一处，就画不出直线，也就定不出年龄。** 这是理解等时线法为何有效的关键。

**9. 直线判据的逻辑方向——老师专门澄清的一个常见误解。** 原话：

> "if you can't form a straight line in that diagram that means the system hasn't remained closed, that means you can't derive an age... **but the opposite is not necessarily true — it's not because you have a straight line that necessarily your system has remained closed.**"

即：**非直线 ⇒ 未封闭（充分）；直线 ⇏ 已封闭（不充分）**。Practical Q2 的 Cerro Galán 数据正是反面教材——那里的点不共线，因为它们的 (⁸⁷Sr/⁸⁶Sr)₀ 各不相同（源区不同），而不是"年龄不同"。老师还预告"we see that in the workshop"。

**10. Bholghati 陨石的两重结论。** 幻灯片只写了年龄 ~4.57 Ga，老师口头补了**两条结论**：

- 结论一：**4.57 Ga ≈ 太阳系年龄**，说明**最早的小行星和行星在太阳系起源后仅几百万年内就形成了**——这是 1960–70 年代该体系的核心应用方向。
- 结论二：能拟合出直线本身就说明**这块陨石里的各矿物已经保持化学封闭了四十五亿年**。

**11. Sudbury 的因果链。** 老师把成矿过程完整讲了一遍：巨大的**bolide（陨石/彗星）撞击**加拿大安大略 → 释放巨大能量，**瞬时汽化并熔融**该区大量地壳 → 形成巨大的**熔池（melt pool）** → 熔池结晶时形成**地球上最大的镍矿床之一** → 对矿物分离物和全岩样品定年得 **~1.8 Ga**。要点："you date **both** the formation of the impact crater **and** the formation of the deposits"——一举两得。

**12. 示踪逻辑的完整因果链（Slide 34–35 的口头展开）——这是本周最容易考简答的部分。** 老师画了一张地幔—地壳—火山的剖面图并逐步讲：

1. 地幔部分熔融 → 岩浆上升进入大陆地壳 → 岩浆房 → 火山喷发。
2. **喷发的瞬间**，玄武岩的 ⁸⁷Sr/⁸⁶Sr **等于其地幔源区的 ⁸⁷Sr/⁸⁶Sr**。老师点出这为什么有用："**it's a lot easier to go and pick up some basalts on the volcano than it is to drill 40 kilometres deep to access some rocks from the mantle**"——玄武岩是地幔的免费采样器。
3. **但** 玄武岩的 **Rb/Sr 比值远高于地幔源区**，因为 **Rb 不相容**，部分熔融时优先进熔体。
4. 因此喷发之后，玄武岩的 ⁸⁷Sr/⁸⁶Sr 会**比地幔源区涨得快得多**。
5. 所以："**the isotope ratios we measure today reflect the past fractionation of the parent and daughter isotopes**"——今天的比值记录的是过去的母/子元素分馏。
6. **推论**：如果玄武岩是 4 亿年前喷发的，它今天的 ⁸⁷Sr/⁸⁶Sr **已经不等于**当年的源区值，必须**回算到喷发时刻（初始比值）**才能谈源区。

**13. 被动示踪剂的墨水比喻。** 老师给了一个很直观的类比：

> **把一滴墨水滴进水里，颜料显示出水滴如何运动、如何混合，但它本身不改变水的运动方式。**

同位素比值就是这样：**不受正在进行的化学反应影响，只被时间和混合改变（"only modified by time and mixing"）**。这一句话可以直接当简答题的定义句背。

**14. BSE 的定义，老师专门插了一句"just as a reminder"：** **Bulk Silicate Earth = 整个地球减去地核 = 全部硅酸盐部分**，而 BSE 又可以分成**地幔 + 地壳**两部分。

**15. 为什么要引入 Sm–Nd（幻灯片只给结论，老师给了动机）。** Rb 和 Sr 在**风化和热液蚀变**中**活动性强**：岩石在地表放久了、或与热液作用过，Rb、Sr 浓度可能已被改造，**Sr 同位素就不再可靠地记录高温过程**。他举了具体图例：一块漂亮新鲜的**地幔捕虏体（mantle xenolith）**放在地表久了会变成**风化的蛇纹岩（weathered serpentinite）**。Sm 和 Nd 都是**稀土元素**，相对不活动，因此 **¹⁴³Nd/¹⁴⁴Nd 在示踪上比 ⁸⁷Sr/⁸⁶Sr 更可靠**，两者常配合使用。

**16. 对 Sr 演化图的"降低难度"提示。** 讲到"How the Sr isotope evolution diagram works"这张幻灯片时，老师直接说："**we don't need to worry about that actually, just going to go into what it shows**"——即**不要求掌握该图的构建推导，只要求会读图、会解释它显示了什么**。这是明确的复习范围提示。

**17. 关于模式年龄的两处保留。** (a) 简化图上地壳与亏损地幔都在约 3 Ga 与 BSE 相交，但"in reality it's a bit more complex"；(b) "**mantle melting and continent formation processes are continuous**"——图上看起来像一次性事件，实际是连续的多期地壳抽取。老师说"you don't need to worry about that for now"。

**18. Skye / Rum 对比的解读方式。** 老师强调这两个地方的岩浆"**started off from melting a similar region of the mantle**"，差别只在于**混染物的量和类型不同**：Skye → 下地壳（低 Sr 同位素）；Rum → 上地壳（高 Sr 同位素）。他把这解释为"**the same starting magma contaminated by slightly different components**"，并推测可能是不同的岩浆通道系统所致。这是"用同位素反推地壳结构"的典型案例。

**19. 苏格兰第三纪的地理背景。** 北大西洋约 60 Ma 开始张开，今天的表现是冰岛；但**把大西洋合上**，最早期的张开记录就保存在**苏格兰西北部**和**格陵兰东岸**。具体岛屿：Skye、Rum、Muck。

---

## 五、Practical 要点

**Practical 2：Isochron dating and isotopic tracers of magma sources（等时线定年与岩浆源区的同位素示踪）**
授课人：Dr David Neave。两道题，各约 60 分钟；PC 机房，基于 Excel（`EART26201_Practical2.xlsx`）。

### 学习目标（Goals）

1. 在 Excel 中绘制**等时线图**；
2. **解读**等时线图以确定地质样品的年龄；
3. 用岩浆的放射成因同位素数据**判别不同岩浆源区**；
4. **计算**不同同位素储库之间的**混合趋势（mixing trends）**。

feedback 另注明：本周相关主题另有一个 **Blackboard quiz**；这些主题会在 **EART22200（Igneous Minerals and Processes）** 与 **EART24200（Metamorphic Minerals and Processes）** 中再次遇到。

### Question 1：陨石结晶年龄

**Q1a — 无球粒陨石（achondrite）的成因**
标准答案：**Achondrites 是来自已分异母体（differentiated parent bodies）的地壳与地幔的硅酸盐陨石**，即其母体小行星已分异成富金属的核与富硅酸盐的幔/壳。相对地，**chondrites（球粒陨石）来自未分异的母体**。题干给的判别线索：Juvinas 和 Nakhla **都没有球粒（chondrules）**，都具有大致**玄武质的结构与成分**（Juvinas 含辉石 + 斜长石；Nakhla 含橄榄石 + 辉石 + 斜长石）。

**Q1b–e — Juvinas 的 Rb–Sr 等时线**

| 样品 | ⁸⁷Sr/⁸⁶Sr | ⁸⁷Rb/⁸⁶Sr |
|---|---|---|
| Glass 玻璃 | 0.7049 | 0.090 |
| Tridymite/quartz 鳞石英/石英 | 0.7006 | 0.024 |
| Pyroxene 辉石 | 0.6996 | 0.009 |
| Whole-rock 全岩 | 0.6994 | 0.006 |
| Feldspar 长石 | 0.6993 | 0.005 |

操作：`Insert → Charts → Scatter` 作散点图（**x = ⁸⁷Rb/⁸⁶Sr，y = ⁸⁷Sr/⁸⁶Sr**），再 `Add Chart Element → Trendline → Linear`，然后右键趋势线 `Format Trendline → Display Equation on Chart` 显示方程。

结果与四步换算（Excel 表原样）：

```
slope = e^(λt) − 1 = 0.0656
e^(λt)             = 1.0656          ← Add 1
λt                 = 0.063538        ← take natural logarithm ln()
t                  = 4.4745 × 10⁹ yr ← Divide by λ (1.42 × 10⁻¹¹)
t                  = 4.47 Ga         ← Convert to Ga
```

**(⁸⁷Sr/⁸⁶Sr)₀ = 0.699**（截距）。

📎 **背景补充（我已核算）**：对表 1 五个点做最小二乘回归，斜率 = 0.06560、截距 = 0.69900，与 feedback 完全吻合；五个点残差都在 ±0.00002 以内，拟合极好，正对应 Q1c 问的"能否得到好的拟合，从而说明系统保持封闭且在 t = 0 时同位素平衡"——**答案是能**。

📎 **背景补充**：Juvinas 的初始值 0.699 与文献中的 **BABI（Basaltic Achondrite Best Initial，玄武质无球粒陨石最佳初始值 ≈ 0.69897）**几乎一致。这正是讲座里说的"BSE 的初始 ⁸⁷Sr/⁸⁶Sr 由陨石估计"的具体来源。

**Q1f–g — Nakhla 的 Rb–Sr 等时线**

| 样品 | ⁸⁷Sr/⁸⁶Sr | ⁸⁷Rb/⁸⁶Sr |
|---|---|---|
| Plagioclase A | 0.70492 | 0.1383 |
| Diopside D | 0.70421 | 0.0937 |
| Diopside G | 0.70344 | 0.0522 |
| Diopside H | 0.70469 | 0.1232 |

```
slope = 0.0172 → e^(λt) = 1.0172 → λt = 0.017054 → t = 1.2010 × 10⁹ yr = 1.20 Ga
(⁸⁷Sr/⁸⁶Sr)₀ = 0.7026
```

**Q1h — 用 Sm–Nd 交叉验证**
题目的动机写得很清楚：**Rb–Sr 体系有时会被蚀变作用干扰**（在其他行星体上和在地球上都一样），所以要用另一个体系检验。

| 样品 | ¹⁴³Nd/¹⁴⁴Nd | ¹⁴⁷Sm/¹⁴⁴Nd |
|---|---|---|
| Whole-rock 1 | 0.512628 | 0.09887 |
| Whole-rock 2 | 0.512660 | 0.10284 |
| Pyroxene 1 | 0.513093 | 0.15054 |
| Pyroxene 2 | 0.513058 | 0.15209 |

```
slope = 0.0085 → e^(λt) = 1.0085 → λt = 0.008464 → t = 1.2928 × 10⁹ yr = 1.29 Ga
```

结论原文：**"the Sr and Nd ages are broadly coherent and reliable"**——两个独立体系给出 1.20 Ga 与 1.29 Ga，大体一致，因此年龄可信。

**Q1i — 两块陨石为何年龄不同（需写至少几句）**
标准答案要点：

- **Juvinas 形成于太阳系历史极早期**，太阳星云凝聚后不久；很可能在其母体**分异完成后不久就被抛射**出去。
- **Nakhla 形成得相对晚近**，必然是通过**近期仍活跃的行星体（即类地行星）上的岩浆活动**形成的。
- 题干给的线索：Nakhla 表面的**暴露年龄（exposure dating）**显示它**在太空中只待了 11 Ma** 就落到地球 → 说明它是被**一次很近期的撞击**抛入太空的。
- 结论：Nakhla 属于 **SNC 族陨石**，一般认为**来自火星**。

### Question 2：Cerro Galán（阿根廷）的地壳混染追踪

**背景**：Cerro Galán 是阿根廷安第斯高 Altiplano 上的一座大型**钙碱性（calc-alkaline）**火山。像它这样的**弧火山（arc volcano）**喷出的岩浆，常常是**地幔来源的玄武质熔体**与**大陆地壳来源的英安质/流纹质熔体**的复杂混合物。同位素示踪剂可以定量两者的相对贡献。数据来自 Francis et al. (1980)，共 14 个样品（G3、G4、G26、G30、G33、G35、G44、G49、G55、G56、G57、G58、G64、G67），每个样品给 **Sr 浓度（µg/g）、⁸⁷Rb/⁸⁶Sr、⁸⁷Sr/⁸⁶Sr**。

**Q2a — 能否定出唯一年龄？**
**不能。** 原文：这些点**不落在一条直线上**，说明它们的 **(⁸⁷Sr/⁸⁶Sr)₀ 不同，因而源区不同**，所以拟合不出等时线，也就得不到唯一年龄。
👉 这道题正是讲座第 9 条口头澄清的实操版：**点不共线 ⇒ 不是同一个封闭同源体系**。

**Q2b — 哪个样品最接近地幔熔体？**
作 **x = Sr 浓度、y = ⁸⁷Sr/⁸⁶Sr** 的图（feedback 提醒"要小心怎么选数据列"）。已知**地幔来源熔体的 ⁸⁷Sr/⁸⁶Sr 几乎总是低于大陆地壳**，因此选 **⁸⁷Sr/⁸⁶Sr 最低的样品 = G49（0.70569，Sr = 698 µg/g）**，它是供应到安第斯地壳底部的地幔熔体的最佳代表。

**Q2c — 混合计算**
端元：**地幔端元 = G49（Sr 698 µg/g，⁸⁷Sr/⁸⁶Sr = 0.70569）**；**地壳端元 = Sr 150 µg/g，⁸⁷Sr/⁸⁶Sr = 0.718**。按 **10 wt.% 递增**加入地壳熔体（0/1、0.1/0.9、……、1/0）。

Excel 表的六列结构（务必按此顺序做，这是本题的方法骨架）：

| 列 | 含义 | 公式 |
|---|---|---|
| A | 地壳物质的质量比例 | 0 → 1，步长 0.1 |
| B | 来自地壳的 Sr | A × Sr_crust |
| C | 来自 G49 的 Sr | (1 − A) × Sr_G49 |
| D | Sr 中来自地壳的比例 | B/(B+C) |
| E | Sr 中来自 G49 的比例 | C/(B+C) |
| F | 混合后的 Sr 浓度 | B + C |
| G | 混合后的 Sr 同位素比值 | D × R_crust + E × R_G49 |

关键提醒（feedback 原文）：**"mixing trends on isotope plots are curved because the mixing end-members contain different amounts of Sr"**——与 Practical 1 中元素数据的**线性**混合线形成对比；**在算混合后的同位素比值之前，必须先算出每一步各储库贡献的 Sr 的量**。

计算结果（feedback 表）：

| A（地壳 wt.%） | 混合 Sr (µg/g) | 地壳贡献的 Sr 比例 D | 混合 ⁸⁷Sr/⁸⁶Sr |
|---|---|---|---|
| 0 | 698.0 | 0.000 | 0.70569 |
| 0.1 | 643.2 | 0.0233 | 0.70598 |
| 0.2 | 588.4 | 0.0510 | 0.70632 |
| 0.3 | 533.6 | 0.0843 | 0.70673 |
| 0.4 | 478.8 | 0.1253 | 0.70723 |
| 0.5 | 424.0 | 0.1769 | 0.70787 |
| 0.6 | 369.2 | 0.2438 | 0.70869 |
| 0.7 | 314.4 | 0.3340 | 0.70980 |
| 0.8 | 259.6 | 0.4622 | 0.71138 |
| 0.9 | 204.8 | 0.6592 | 0.71380 |
| 1.0 | 150.0 | 1.000 | 0.71800 |

📎 **背景补充（我已逐行核算）**：以上 11 行全部与公式自洽（例如 A = 0.4：B = 60、C = 418.8、F = 478.8、D = 60/478.8 = 0.12531、G = 0.12531×0.718 + 0.87469×0.70569 = 0.70723）。注意 **A = 0.5 时 D 只有 0.177**——加入 50 wt.% 的地壳物质，Sr 元素却只有 17.7% 来自地壳，因为地壳端元的 Sr 浓度只有地幔端元的约 1/4.7。**这就是曲线弯曲的原因**，也是本题最容易出错的概念点。

**Q2d — G26 与 G55 需要多少混染？**
- **G26（Sr 259，⁸⁷Sr/⁸⁶Sr = 0.71099）→ 加入 80 wt.% 地壳**（对照上表 A = 0.8：Sr 259.6，0.71138 ✓）
- **G55（Sr 477，⁸⁷Sr/⁸⁶Sr = 0.70731）→ 加入 40 wt.% 地壳**（对照 A = 0.4：Sr 478.8，0.70723 ✓）

**Q2e — 混合模型的拟合优度与地壳混染的重要性**
"简单混合线**极好地**解释了这些组成；大多数数据点落在预测趋势线上或很接近它。**地壳混染在 Cerro Galán 非常重要，多数样品记录了 >50 wt.% 的混染**。"

**Q2f — 对地幔 Sr 同位素的启示**
样品**都很靠近同一条混合线**，说明**地幔供应的熔体的 Sr 同位素变化极小**。两种可能解释（feedback 明确给了两条）：**要么地幔本身非常均一，要么任何地幔来源的不均一性在熔体到达大陆地壳之前就已被混合抹平。**

**Q2g — 晶体环带（zoned crystal）的读图题**
Figure 2（Ginibre and Davidson, 2014，来自智利 Parinacota 火山的一颗晶体）给出穿过单颗晶体的剖面：**黑方块 = Sr 浓度，灰框 = ⁸⁷Sr/⁸⁶Sr**，x 轴是穿过晶体的距离。问晶体外缘是 A 还是 B。

**答案：外缘（rim）是 B，内核（core）是 A。** 理由：**从 A 到 B，Sr 浓度下降、Sr 同位素比值上升**，这与"晶体在一个**地幔来源的岩浆中生长、而该岩浆逐渐被低 Sr、高 ⁸⁷Sr/⁸⁶Sr 的地壳所混染**"相一致。
👉 逻辑与 Q2c 完全同构：**地壳端元 = 低 Sr + 高 ⁸⁷Sr/⁸⁶Sr**，混染越深，Sr 越低、同位素越高。晶体环带把这个混合过程"逐帧"记录了下来（feedback 用"像树的年轮"作比）。

### 评分与常见错误要点

- feedback 特别插了一句操作性警告：**"Check you can copy from Word to Excel – a major source of errors by student and academic alike!"**——从 Word 表格粘到 Excel 时数字容易错位/变文本。
- **必须交代推理过程**，Q1i 明确要求"至少写几句话"。
- Q2a 的常见错误：硬拟合一条趋势线并报出一个"年龄"。**必须先判断点是否共线**。
- Q2c 的常见错误：直接用质量分数 A 加权同位素比值（得到直线），而不是先算 Sr 贡献比例 D、E。
- 提交方式：把答案打在文档和/或配套 Excel 文件里；课上有 demonstrator 全程答疑，结束前老师做简短总结，feedback 事后发到 Blackboard。

---

## 六、易错点 / 重点难点

1. **λ 的单位是 yr⁻¹，不是 yr**（材料里两处写成 "1.42 × 10⁻¹¹ years"，是笔误）；λ 是"每年的衰变概率"，只有 **t½ 才以年为单位**。且 **t½ = ln2/λ，两者成反比**：λ 越大 = 衰变越快 = 半衰期越短。本周四个体系全是极小的 λ、极长的 t½。

2. **D\* = N(e^{λt} − 1) 里的 N 是"今天残留的母体"，不是 N₀。** 用错会得到系统性偏大的年龄。

3. **初始子体 D₀ 不能忽略**（"只有极少数情况下全部子体都由衰变产生"）——**等时线的截距就是在替你确定 D₀/S。**

4. **归一化同位素 S 必须是非放射成因的稳定同位素**（⁸⁶Sr、¹⁴⁴Nd、²⁰⁴Pb）——既不衰变、也不是别的核素的衰变产物，其绝对量在整个 t 内恒定。

5. **等时线在 x 轴上散不开就定不出年龄。** 分配系数差异（Week 01）是等时线法的物理前提，不是可有可无的背景。

6. **"直线 ⇏ 封闭"。** 非直线一定说明系统被扰动；但直线可能是混合线（Practical Q2 的 Cerro Galán 就是不共线的反例；更隐蔽的情况是混合线恰好看起来像等时线，即"**errorchron / 假等时线**"）。老师明确点名了这个逻辑不对称。

7. **元素分馏 vs 同位素分馏。** Rb 与 Sr 是不同元素，会分馏（D 不同）；⁸⁷Sr 与 ⁸⁶Sr 是同一元素的同位素，**在高温过程中不分馏**。整个"被动示踪"逻辑建立在后者之上。（📎 **背景补充**：这只在**高温**下成立；低温过程和轻元素会有质量分馏，那是学期末稳定同位素部分的内容。）

8. **Rb–Sr 与 Sm–Nd 的方向相反，是本周最容易记反的一对。**

   | | Rb–Sr | Sm–Nd |
   |---|---|---|
   | 母体相容性 | ⁸⁷Rb **不相容**（比 Sr 更不相容） | ¹⁴⁷Sm **更相容**（比 Nd 更相容） |
   | 大陆地壳 | 高 ⁸⁷Sr/⁸⁶Sr（**上**） | 低 ¹⁴³Nd/¹⁴⁴Nd（**下**） |
   | 亏损地幔 | 低 ⁸⁷Sr/⁸⁶Sr（**下**） | 高 ¹⁴³Nd/¹⁴⁴Nd（**上**） |
   | 初始比值来源 | 陨石（Rb 是挥发性元素，估计较难） | 球粒陨石（Sm、Nd **难熔**，更可靠） |
   | 抗风化/蚀变 | **差**（Rb、Sr 活动性强） | **好**（Sm、Nd 是 REE，不活动） |

   记忆钩子：**两条曲线在 Sr 图与 Nd 图上"上下颠倒"**，所以在地幔阵列（Nd vs Sr）上必然呈**负相关**。

9. **同位素图上的混合线是弯的，元素图上是直的。** 弯曲程度由两端元的**该元素浓度比**决定，浓度差越大越偏向高浓度端元。Practical Q2 的"A = 0.5 却只有 17.7% 的 Sr 来自地壳"就是这个效应的量化体现。

10. **模式年龄（model age）不是岩石的结晶年龄。** 它是演化曲线与参考储库（BSE/CHUR）曲线的**交点时间**，依赖于所选参考储库和"单次事件"的简化假设；老师明确说现实中地幔熔融与大陆生长是**连续**的。

11. **玄武岩的 ⁸⁷Sr/⁸⁶Sr 只在喷发瞬间等于源区值**，对老岩石必须**回算初始比值**才能谈源区。另注意 **⁸⁷Sr/⁸⁶Sr 与 ⁸⁷Rb/⁸⁶Sr 是两回事**：前者是同位素比值（等时线的 y），后者是母/子比值（等时线的 x，反映元素分馏）；Practical Q2b 又特意换成 **Sr 浓度**作 x 轴，三者别混。

12. **定年上限的经验法则**：约 6–7 个半衰期。这就是为什么地质定年用超长半衰期体系，而 ¹⁴C 只能用于很年轻的材料。

13. **Slide 14 的印刷错误**：²³⁸U 行的测量比值应为 **²⁰⁶Pb/²⁰⁴Pb**（幻灯片误印为 ²⁰⁸Pb/²⁰⁴Pb），老师在课上当场更正。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| Radiogenic isotope | 放射成因同位素 | 由放射性衰变产生的同位素 |
| Radioactive decay | 放射性衰变 | 不稳定核素自发转变为其他核素 |
| Nuclide | 核素 | 由 Z 和 N 共同确定的一种原子核 |
| Karlsruhe Nuclide Chart | 卡尔斯鲁厄核素图 | y 轴 Z、x 轴 N 的核素性质总览图 |
| Proton number (Z) | 质子数 / 原子序数 | 决定元素身份 |
| Neutron number (N) | 中子数 | 决定同位素 |
| Mass number (A) | 质量数 | A = Z + N |
| Parent nuclide | 母核素 | 发生衰变的不稳定核素 |
| Daughter nuclide | 子核素 | 衰变产物 |
| Alpha decay (α) | α 衰变 | 放出 He 核，Z −2、N −2 |
| Beta decay (β) | β 衰变 | 放出电子或正电子，Z 与 N 一增一减 |
| Gamma decay (γ) | γ 衰变 | 激发态核放出 γ 射线，Z、N 不变 |
| Decay constant (λ) | 衰变常数 | 单位时间衰变概率，单位 yr⁻¹ |
| Half-life (t½) | 半衰期 | t½ = ln2/λ |
| Magic numbers | 幻数 | 核壳层闭合的 Z 或 N 值 |
| Oddo–Harkins rule | 奥多—哈金斯规则 | 偶原子序元素丰度更高（Week 01） |
| Geochronology | 地质年代学 | 测定岩石与地质事件年龄的学科 |
| System (geochronological) | （地质年代学的）系统 | 在整段 T 内保持化学封闭（closed system，无元素得失）的样品部分 |
| Whole-rock sample / Mineral separate | 全岩样品 / 矿物分离物 | 等时线上的两类子系统 |
| Isochron | 等时线 | 同龄同初始比值样品在 D/S–N/S 图上的直线 |
| Isochron diagram | 等时线图 | x = N/S，y = D/S |
| Initial ratio (D/S)₀ | 初始比值 | 等时线截距，携带源区信息 |
| Non-radiogenic isotope | 非放射成因同位素 | 用作归一化分母的稳定同位素（⁸⁶Sr、¹⁴⁴Nd、²⁰⁴Pb） |
| Partition coefficient (D) | 分配系数 | Week 01；等时线 x 轴散开的原因 |
| Compatible / Incompatible | 相容 / 不相容 | 元素倾向进入固相 / 熔体 |
| Provenance | 物源 | 岩石或物质的来源储库 |
| Passive tracer | 被动示踪剂 | 只随时间与混合改变、不影响体系的示踪剂 |
| Geochemical reservoir | 地球化学储库 | 具特征同位素组成的地球圈层单元 |
| Bulk Silicate Earth (BSE) | 硅酸盐地球总体 | 全地球减去地核 = 地幔 + 地壳 |
| Depleted Mantle (DM) | 亏损地幔 | 抽取地壳熔体后的残余地幔 |
| Continental Crust | 大陆地壳 | 分上地壳 / 下地壳 |
| Chondrite | 球粒陨石 | 来自未分异母体 |
| Achondrite | 无球粒陨石 | 来自已分异母体的壳/幔 |
| Refractory / Volatile | 难熔 / 挥发性 | Sm、Nd 难熔；Rb 挥发 |
| Model age | 模式年龄 | 演化线与参考储库线的交点年龄 |
| Mantle array | 地幔阵列 | ¹⁴³Nd/¹⁴⁴Nd–⁸⁷Sr/⁸⁶Sr 上的负相关带 |
| MORB (mid-ocean ridge basalt) | 洋中脊玄武岩 | 源自亏损地幔 |
| OIB (ocean island basalt) | 洋岛玄武岩 | 源自地幔柱，常近 BSE |
| Mantle plume | 地幔柱 | 热点的深部来源 |
| Subduction recycling | 俯冲再循环 | 岩石圈回卷入对流地幔并使其再富集 |
| Crustal contamination | 地壳混染 | 岩浆上升途中同化地壳物质 |
| Mixing trend | 混合趋势 | 同位素图上因端元浓度不同而弯曲 |
| End-member | 端元 | 混合模型的两个极端组成 |
| Mantle xenolith | 地幔捕虏体 | 被岩浆携带上来的地幔碎块；风化后成蛇纹岩 serpentinite |
| Calc-alkaline | 钙碱性 | 弧岩浆的典型系列（Cerro Galán） |
| Tholeiitic / Alkalic | 拉斑玄武质 / 碱性 | 夏威夷盾阶段 / 前盾与后盾阶段的岩浆类型 |
| Zoned crystal | 环带晶体 | 具同心成分环带，逐帧记录岩浆混染过程 |
| Exposure age | 暴露年龄 | 陨石在太空中受宇宙射线照射的时长 |
| SNC meteorites | SNC 族陨石 | Shergottite–Nakhlite–Chassignite，火星来源 |
| Caledonian Orogeny | 加里东造山运动 | 苏格兰，400–425 Ma |
| Bolide | 撞击体 | 陨石或彗星（Sudbury 镍矿的成因） |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `EART26201 - 06-Oct-transcript.md`，Part 2 讲 ²³²Th / ²³⁸U 体系处 | "both of those are very long half-life here are 140 billion years and here just under 50 billion years" | 半衰期数值**偏大 10 倍** | ²³²Th 的 t½ ≈ **1.4 × 10¹⁰ yr（约 140 亿年 = 14 Ga）**，λ ≈ 4.95 × 10⁻¹¹ yr⁻¹；²³⁸U 的 t½ ≈ **4.47 × 10⁹ yr（约 45 亿年，"just under 5 billion"）**，λ ≈ 1.551 × 10⁻¹⁰ yr⁻¹。疑为口误或自动转写把 "14 billion"/"just under 5 billion" 听成了 "140"/"50"。 |
| 同上，讲 ¹⁴C 处 | "for carbon-14 for example which is not listed here you can go back in time a couple of million years" | ¹⁴C 的可用范围**严重高估** | ¹⁴C 的 t½ = 5730 yr，按老师自己给的"6–7 个半衰期"法则，上限约 **3.5–4 万年**（实务上一般说 ~5 万年），绝非"几百万年"。老师的本意（¹⁴C 只能测很年轻的材料）是对的，数值说错了。 |
| 同上，讲核稳定性 / 幻数处 | "the stability is greatest when Z or N is 28, 20, 28, 50, or 126" | 幻数序列**被转写弄乱、且不完整** | 标准幻数为 **2, 8, 20, 28, 50, 82, 126**。原句开头的 "28" 应为 "2, 8"，且遗漏了 82。 |
| 同上，讲核结构处 | "the atomic mass of an element is the sum of the proton number Z and the neutron number M" | 术语用错 | 应为**质量数（mass number）A = Z + N**。"atomic mass（原子质量）"是另一个量（含质量亏损与同位素丰度加权），且中子数记号是 **N** 不是 M。 |
| 同上，讲 Nd 演化图处 | "T the time before present same starting point 4.6 million years ago" | 单位错误 | 应为 **4.6 billion years ago（4.6 Ga）**。 |
| 同上，讲 Sr 演化图收尾处 | "here it looks like it's a one-off process occurring about three million years ago" | 单位错误 | 应为 **three billion years ago（约 3 Ga）**，与同段前文"about three billion years"的模式年龄一致。 |
| `EART26201_Lecture2_RT_v2.md` Slide 14 对应的表格（表格内容未被提取，但录音中提及） | ²³⁸U 行的测量比值印为 ²⁰⁸Pb/²⁰⁴Pb | 幻灯片印刷错误 | 应为 **²⁰⁶Pb/²⁰⁴Pb**。**老师已在课堂上当场更正**（"it's a typo here it should be 206 lead here for the uranium over 204 lead"）。此处照录以备核对。 |
| `EART26201_Practical2_feedback.md` Q1d 与 Q1h | "𝜆(87Rb) = 1.42 × 10⁻¹¹ **years**"、"𝜆(147Sm) = 6.54 × 10⁻¹² **years**" | 衰变常数**单位写错** | 衰变常数的单位是 **yr⁻¹（per year）**，不是 years。同样的写法也出现在 xlsx 转出版本的 "λ(87Rb)= … years" 两行。 |
| `EART26201_Practical2_feedback.md` Q1h vs `EART26201_Practical2_feedback.xlsx.md` Q1h | PDF 给 λ(¹⁴⁷Sm) = **6.54 × 10⁻¹²**；xlsx 实际使用 **6.547 × 10⁻¹²** | 两份材料取值不一致 | 差异约 0.1%，对结果影响很小：用 6.547 × 10⁻¹² 得 1.2928 Ga，用 6.54 × 10⁻¹² 得 1.2942 Ga，四舍五入后同为 **1.29 Ga**，结论不受影响。答题时按题面给的 6.54 × 10⁻¹² 即可。 |
| `EART26201_Practical2_feedback.xlsx.md` Question 2 混合表表头 | "Proportion Sr from G49 (**C+**/(B+C))" | 表头公式笔误 | 应为 **C/(B+C)**。表中数值本身是对的（我已逐行复核，全部自洽）。 |
| `EART26201_Lecture2_RT_v2.md` Slide 5 | "van der Fierdt et al. (2016)" | 作者姓氏拼写 | 应为 **van de Flierdt**。 |
| `EART26201 - 06-Oct-transcript.md` 全文 | 大量专有名词被自动转写误听 | 自动语音转写噪声（非讲授内容错误） | 对照更正：newtonia → **neodymium (Nd)**；celerophile → **siderophile**；Odo-Harkins → **Oddo–Harkins**；nucleates → **nuclides**；stamarium → **samarium**；isochrone → **isochron**；borgatti → **Bholghati**；phenolith → **xenolith**；"crystal contamination" → **crustal contamination**；"mid-ocean rich basalts" → **mid-ocean ridge basalts**；tolietic → **tholeiitic**；sky / rum / mud → **Skye / Rum / Muck**；"wise lovers" → **whereas lavas**；labors → **lavas**；"mental" → **mantle**；"indelible" → **(mantle) plume**；"ice-tub ratio" → **isotope ratio**；"all deposits" → **ore deposits**；"bolides" → **bolide**；"my reservoir" → **magma reservoir**。 |
