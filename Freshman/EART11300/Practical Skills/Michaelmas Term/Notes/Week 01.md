# Week 1 — 地图入门：比例尺、网格参考与野外定位（Practical 1A）

> **本周材料清单**（Week 1 文件夹内全部 .md）
> - `EART11300 Sem 1 Practical 1A.md` —— Practical Class Week 1 讲义（Aims / Equipment / Activities / Scale / Grid References / Mapping the timeline）
>
> 本周只有这一份材料，且为**任务单式讲义**（只给题目、不给答案），因此笔记以「把每一道题背后的方法与原理讲透 + 给出可套用的算法与工作示例」为主。凡讲义中需要现场实测/现场观察才能得到的数值（比例尺、步长、Brunswick Park 长度、建筑物 GR），笔记中以**占位符 + 算法 + 代入示例**的方式呈现，复习时把自己当天实测的数字代进去即可。

---

## 一、本周主题

本周是 EART11300（Practical and Professional Skills Development）秋季学期 10 次实践课（Week 1、2、4、5、6、7、8、9、10、11，**无 Week 3**）中的**第 1 次**，主题是**地图的使用（working with maps）**。

这门课整学期要反复用到各种地图（校园图、地质图、地形图、野外填图底图），Week 1 的定位是**打地基**：在校园 Brunswick Park（曼彻斯特大学主校区中间的那片绿地）这个「零风险野外」里，把三件最基础、后续每周都要用的技能练成肌肉记忆——

1. **读比例尺 (map scale)** 并在图上距离与地面距离之间双向换算；
2. **读/写网格参考 (grid reference, GR)**，在 OS 英国国家网格 (UK National Grid) 体系下把任一地物定位到指定精度；
3. **把地面上的地物位置正确标绘 (plot) 到野外底图上**，并用估距（步测）而非仪器完成距离测量。

讲义明确的三条 intended learning outcomes（预期学习成果）：

> 1. Estimate the distances between features on a map using the correct map scale（用正确比例尺估算图上地物间的距离）
> 2. Record the grid reference for named features on a map（记录指定地物的网格参考）
> 3. Plot the positions of features on a field map（把地物位置绘到野外图上）

第三部分「Mapping the timeline」是**周二理论课内容的复习 (revision from Tuesday)**：把 Brunswick Park 的实地长度当作 46 亿年的地质时间轴，用比例尺思维做一次「时间的比例尺」换算——既练算术，又直观体会地球历史中各代时长的悬殊。

**在全课 10 周中的位置**：这是唯一一次「纯定位技能」课。后续野外/实验课里，任何一个观测点都必须能写出 GR、任何一张野外记录图都必须有比例尺和北向箭头，本周不过关，后面每周都会持续扣分。

---

## 二、核心概念

### 2.1 地图比例尺 (map scale)

**定义**：图上距离与其代表的地面实际距离之比。

三种表达方式，野外要能互相转换：

| 表达方式 | 英文 | 示例 | 说明 |
|---|---|---|---|
| 代表分数 | Representative Fraction, **RF** | 1:1250、1:10 000、1:50 000 | 无量纲，**与使用的长度单位无关**——1 单位图上 = 1250 同样单位的地面。这是最通用的写法 |
| 文字比例尺 | statement / verbal scale | "1 cm to 12.5 m"、"2 cm to 1 km" | 直观但绑定单位 |
| 线段比例尺 | **scale bar** / linear scale | 图上画一条带刻度的线段 | **唯一在复印/缩放后仍然正确的形式**——因此野外自绘图上必须画 scale bar，而不是只写 "1:1000" |

**核心换算公式**

```
地面实际距离 = 图上量得距离 × 比例尺分母
Ground distance = Map distance × Scale denominator

图上应画距离 = 地面实际距离 ÷ 比例尺分母
Map distance  = Ground distance ÷ Scale denominator
```

注意两边**必须同单位**再换算：先把 cm 换算完，最后再把 cm 转成 m/km（1 m = 100 cm，1 km = 100 000 cm）。

**大比例尺 vs 小比例尺（极易说反）**

- **大比例尺 (large scale)** = 分母小 = 1:1250、1:2500 → 覆盖范围小、**细节多**（能画出单个建筑物轮廓、单棵树）。校园图属于此类。
- **小比例尺 (small scale)** = 分母大 = 1:250 000、1:1 000 000 → 覆盖范围大、细节少。
- 记忆法：把 RF 当成真正的分数看，1/1250 > 1/250000，所以前者「大」。

讲义在 Grid References 一节里正是用这个概念说明为什么可以省略前置数字：

> "Because we are using a **large scale** map we do not need to give the full GR, we only need to use the GR for within each 100 m square."

即：在大比例尺的局部图上，100 km 方格代号和高位数字对所有点都相同，写出来是冗余信息，只保留低位数字即可。

### 2.2 步长与步测 (stride length / pacing)

野外没有卷尺时的标准估距手段，**地质学家的基本功**。

**术语区分（讲义用 stride，务必分清，否则结果差一倍）**

| 英文 | 中文 | 定义 | 成人典型值 |
|---|---|---|---|
| **pace / step** | 单步 | 一只脚落地到**另一只**脚落地 | ≈ 0.7–0.8 m |
| **stride** | 复步 / 跨步 | 同一只脚连续两次落地（= 2 paces） | ≈ 1.4–1.6 m |
| **double pace** | 复步（同 stride） | 军用/野外常用计数单位：只数右脚落地次数 | ≈ 1.5 m |

**标定 (calibration) 步长的正确做法**

1. 找一段**已知长度的平直地面**（例如用地图上量出的、或用建筑物已知尺寸推得的 20 m / 50 m 直线）。
2. 用**自然行走步伐**（不要刻意迈大步或迈小步——刻意的步幅在野外无法保持）走完全程，数步数。
3. 步长 = 已知距离 ÷ 步数。
4. **至少往返走 2–3 次取平均**，减小随机误差。
5. 建议标定「走 100 步走多远」而不是「一步多长」——数大数字时相对误差更小。

**反向使用**：地面距离 ≈ 步数 × 平均步长。

**步测的系统误差来源（野外要主动修正）**

- **上坡步幅变短、下坡步幅变长**（同一坡还会因疲劳漂移）；
- 松软地面（沙、泥、草丛、碎石坡）步幅变短；
- 负重（背野外包、拿地图板）步幅变短；
- 人群、绕障碍物导致**路径非直线**——步测量的是**行走路径长**，不是两点间**直线距离**；
- 疲劳导致后半程步幅缩短。

步测的合理精度约为 **±2%–5%**；因此讲义里让你「estimate（估算）」而不是「measure（测量）」，报告结果时要写成 `≈ 85 m` 而不是 `85.37 m`。

### 2.3 UK National Grid（英国国家网格）与网格参考 GR

**体系结构（自上而下三层）**

1. **500 km 大方格**：以字母 S、T、N、O、H 等标识（英国本土主要落在 S、T、N、H）。
2. **100 km 方格**：在 500 km 方格内再分 5×5，得到两字母代号，如 **SJ、SD、SK、TQ**。
   - 讲义指明：**"The university campus is found within the SJ 100 km grid square of the UK National Grid"**（曼彻斯特大学校园位于 SJ 方格内）。
3. **方格内坐标**：从该 100 km 方格的**西南角**起算，向东为 **Easting（东距）**、向北为 **Northing（北距）**，单位 m，各 0–99 999。

**两种坐标写法**

| 写法 | 形式 | 例 | 说明 |
|---|---|---|---|
| 字母 + 数字（alphanumeric） | `SJ 84775 96699` | 常用于野外记录 | 需要写出 100 km 方格字母 |
| 全数字 / 绝对坐标（all-numeric, full national grid） | `E 384775, N 396699` | 讲义中的 12 figure GR | 从整个国家网格的**总原点（SV 方格西南角，Scilly 群岛西南外海）**起算，E 6 位、N 6 位（北部 N 可达 7 位） |

**讲义给的 12 figure GR：Easting = 384775，Northing = 396699**
- 拆解：Easting 384775 → 3|84775 → 「3」对应 SJ 的东向 100 km 带，方格内 Easting = 84775 m；
- Northing 396699 → 3|96699 → 「3」对应 SJ 的北向 100 km 带，方格内 Northing = 96699 m；
- 因此等价写法为 **SJ 84775 96699**（即 SJ 8477 9669 的 1 m 精度版本），正好落在曼大主校区，与讲义「campus is within SJ」自洽。
- 「12 figure」= 6 位 E + 6 位 N，**定位精度 1 m**（讲义原话："it will locate you within a 1 m square"）。

**GR 位数与精度对照（必背）**

| 位数 (figures) | 形式（SJ 方格内） | 每个数字对 | 定位精度（方格边长） |
|---|---|---|---|
| 2 figure | SJ 8 9 | E 1 位 + N 1 位 | 10 km |
| **4 figure** | SJ 84 96 | E 2 + N 2 | **1 km**（1:50 000 图上一个格） |
| **6 figure** | SJ 847 966 | E 3 + N 3 | **100 m**（最常用的野外记录精度） |
| **8 figure** | SJ 8477 9669 | E 4 + N 4 | **10 m** |
| **10 figure** | SJ 84775 96699 | E 5 + N 5 | **1 m** |
| **12 figure**（全数字绝对坐标） | 384775 / 396699 | E 6 + N 6 | **1 m**（同 10 figure，只是多带了 100 km 方格那一位） |

规律：**每多一对数字，精度提高 10 倍**；位数总是**偶数**，E 和 N 的位数必须**相等**。

**读写 GR 的黄金法则**

> **Easting 先，Northing 后**（讲义原话："Remember the Easting is given first in the GR and then the Northing"）。
>
> 助记：**"Along the corridor, then up the stairs"**（先沿走廊走，再上楼梯）；或 **"Read right, then up"**。

**具体读法（以 6 figure 为例）**

1. 找到目标点**左侧（西侧）**最近的南北向格线，读它的两位编号 → 得 Easting 前 2 位（如 84）。
2. 目测目标点在该格内的**东西向位置**占格宽的十分之几 → 得 Easting 第 3 位（如 0.7 格 → 7）→ Easting = 847。
3. 找到目标点**下方（南侧）**最近的东西向格线，读两位编号 → Northing 前 2 位（如 96）。
4. 目测点在格内**南北向**占十分之几 → 第 3 位（如 6）→ Northing = 966。
5. 合写：**SJ 847 966**（或省略字母写 847966）。

**关键原则：永远取目标点所在方格的西南角（左下角）格线编号**——即向下取整，**不要四舍五入**。

**罗盘玫瑰式记忆**：Easting 增大 = 向东；Northing 增大 = 向北。所以 GR 数字变大的方向就是「右上」。

### 2.4 网格北、真北与磁北（本周未展开，但读图必须知道）

- **Grid North（网格北）**：地图格线指向的北，OS 图上格线的方向。
- **True North（真北）**：指向地理北极。
- **Magnetic North（磁北）**：罗盘指向，随时间与地点漂移。
- 三者夹角即 **magnetic declination（磁偏角）**，OS 图图廓外会给出当年的换算值。本周只用 grid north（读 GR 用不到罗盘），但后续野外课用罗盘量产状时必须做磁偏角改正。

### 2.5 GNSS / OS Locate app 与「精度 vs 有效数字」

讲义要求：**"What does the OS Locate app say is the GR for this locality? How accurate is this GR?"**

- **OS Locate** 是 Ordnance Survey 官方免费 app，用手机 GNSS（GPS/GLONASS/Galileo）定位，直接输出 **英国国家网格 GR**（可选位数）+ 海拔 + 罗盘方位，并显示**估计精度（accuracy，单位 m）**。
- 手机 GNSS 的现实精度：开阔天空下约 **3–10 m**；被高楼包夹（**urban canyon**，Brunswick Park 四周正是高楼）会因**多路径效应 (multipath)** 恶化到 **10–30 m**；建筑物内或树冠下更差。
- **本活动的核心教学点（评估常考）**：app 可以显示 10 或 12 位 GR（1 m 精度），但真实定位误差可能有 10 m——**显示位数 ≠ 实际精度**，这是典型的 **spurious precision（虚假精度）**。
  - 正确做法：**记录 GR 时的位数应与实际精度相匹配**。若 app 报 accuracy = 8 m，则最多写到 **8 figure（10 m 精度）**，写 10/12 figure 是不诚实的。
  - 同时把 accuracy 值本身记进野外记录本，例如：`SJ 8477 9669 (OS Locate, ±6 m, 11:20 BST)`。
- **校验方法**：把 app 给的 GR 与自己在纸图上目视读出的 GR 比较，差值即两种方法的**符合度**；讨论差异来源（读图目测误差、GNSS 误差、地图本身的绘制误差）。

### 2.6 野外底图标绘 (plotting on a field map) 的基本规范

本周第 3 条学习成果是「把地物位置标绘到野外图上」，这套规范整学期通用：

**一张合格的野外图必须有（记忆口诀 TSNAKE）**

| 字母 | 要素 | 说明 |
|---|---|---|
| **T** | Title | 标题：画的是什么、在哪 |
| **S** | Scale bar | **线段比例尺**（不能只写 RF） |
| **N** | North arrow | 北向箭头，并注明是 grid / true / magnetic north |
| **A** | Author + date | 作者、日期（+ 天气、时间，野外记录必需） |
| **K** | Key / legend | 图例：每个符号、每种颜色的含义 |
| **E** | Eastings & Northings | 格网及其编号（或至少 GR 控制点） |

**标绘作业规范**

- 用**铅笔**先绘（可改），确认后再用**墨水笔**上正式线条与注记（讲义 Equipment 同时要求 pencil 和 pen，就是这个用意）。
- 位置用**小十字或小圆点 + 编号**标注，注记写在旁边并用引线连到点上，避免遮盖底图信息。
- **mapping board（地图板）**：把地图固定在硬板上（通常配透明防水袋/塑料膜），保证在无桌面的户外能平稳、干燥地书写——英国野外的标配。

**点数据的表达方式（讲义第 2 题「How might you show their distribution and other characteristics?」的答题方向）**

对「树」这类点要素，可用的表达手段：

1. **位置**：每棵树在图上打一个点/符号，位置按 GR 或按与已知地物的距离-方向标绘（**offset / triangulation**）。
2. **种类 (species)**：用不同**符号形状**或**颜色**区分，配图例。
3. **大小**：用**比例符号 (proportional symbols)**——圆的半径正比于树冠直径 (canopy diameter) 或胸径 (DBH, diameter at breast height)；也可按树冠实际范围画多边形。
4. **数量/密度**：分格统计做**密度图 (density map)** 或 **choropleth**（每 10 m×10 m 方格内的株数），或**等值线 (isopleth)**。
5. **附加属性**：树高、健康状况、是否有巢箱等，用**表格（属性表）+ 编号**关联到图上的点，而不是把文字全塞进图里。
6. 现代做法：用 GNSS 逐点采点，导出为**点图层**在 GIS 中按属性符号化。

这就是「**空间数据 = 位置 + 属性**」这一 GIS 基本模型的手工版本，也是全课的方法论起点。

### 2.7 深时 (deep time) 与地质年代表

「Mapping the timeline」一节要求把 Brunswick Park 的长度当作**地球全部历史 4.56 Ga**。这类练习叫 **timeline / deep time analogy（深时类比）**，目的是用空间直觉去感受人脑无法直接把握的时间尺度。

**需要用到的地质年代边界（ICS 国际年代地层表，单位 Ma = 百万年前）**

| 事件/界线 | 英文 | 年龄 (Ma) | 备注 |
|---|---|---|---|
| 地球形成 | Origin of the Earth / formation | **≈ 4560**（4.56 Ga；讲义给的基准） | 亦见 4567 Ma（太阳系 CAI 年龄） |
| 冥古宙 | Hadean | 4567–4031 | 无（或极少）岩石记录 |
| **太古宙开始** | base of the **Archean** | **≈ 4000**（正式 4031） | 讲义要求标注 |
| 元古宙开始 | base of Proterozoic | 2500 | |
| 显生宙开始 / 寒武纪 | base of Phanerozoic / Cambrian | 538.8 | |
| **石炭纪开始** | base of the **Carboniferous** | **358.9**（≈359） | 讲义要求标注 |
| **侏罗纪开始** | base of the **Jurassic** | **201.4**（≈201） | 讲义要求标注 |
| **古近纪开始** | base of the **Paleogene** | **66.0** | 白垩纪末大灭绝 K–Pg；讲义要求标注 |
| 现今 | Present day | 0 | 时间轴末端 |

> **数量级警惕**：4.56 **billion** years = 4.56 × 10⁹ a = **4560 Ma**。英式/美式 billion 都是 10⁹。混淆 Ga/Ma 是本节最常见的错误。
> 单位约定：**ka** = 千年、**Ma** = 百万年、**Ga** = 十亿年；表示「距今多少年前」时国际上写 **Ma**（ago 已隐含）或 **Myr ago**。

---

## 三、公式与图表

### 3.1 比例尺换算总表

**基本关系**

```
RF = 1 : S            （S = 比例尺分母）
Ground = Map × S
Map    = Ground ÷ S
```

**常见校园图比例尺的换算（讲义 Scale 题 a–c 的答案模板）**

| RF | 图上 1 cm = 地面 | 地面 10 m = 图上 | 图上 2 cm = 地面 | 地面 100 m = 图上 |
|---|---|---|---|---|
| 1:500 | 5 m | 2.0 cm | 10 m | 20 cm |
| **1:1000** | 10 m | **1.0 cm** | **20 m** | 10 cm |
| **1:1250**（OS 城市大比例尺标准） | 12.5 m | **0.8 cm = 8 mm** | **25 m** | 8 cm |
| **1:2500**（OS 乡村大比例尺标准） | 25 m | **0.4 cm = 4 mm** | **50 m** | 4 cm |
| 1:5000 | 50 m | 2 mm | 100 m | 2 cm |
| 1:10 000 | 100 m | 1 mm | 200 m | 1 cm |
| 1:25 000（OS Explorer） | 250 m | 0.4 mm | 500 m | 4 mm |
| 1:50 000（OS Landranger） | 500 m | 0.2 mm | 1 km | 2 mm |

> **课上填空**：`本图比例尺 = 1 : ______`（读图廓上的标注或 scale bar）→ 其余三格照上表方法算。
> 讲义题 (b) 「10 m 在图上多长」= 10 m ÷ S；题 (c)「图上 2 cm 代表多远」= 2 cm × S。

**换算演算示范（1:1250）**

- (b) 10 m = 1000 cm；1000 cm ÷ 1250 = **0.8 cm**。
- (c) 2 cm × 1250 = 2500 cm = **25 m**。

### 3.2 步长标定与距离估算

```
平均步长 (stride length) = 已知标定距离 ÷ 该距离内的步数
                          L_stride = D_known / N

估算距离 = 步数 × 平均步长
          D_est = N × L_stride
```

**记录表模板（题 d–g）**

| 项目 | 记录 | 计算 |
|---|---|---|
| 标定：走 20 m 用了 N 步 | N = ___ | L_stride = 20 / N = ___ m |
| (e) Williamson Building 门 ↔ Simon Building 门 | N = ___ 步 | D = ___ m |
| (f) Simon Building ↔ Zochonis Building | N = ___ 步 | D = ___ m（**并在图上画出所量线段的起讫**） |
| (g) Brunswick Park 总长 | N = ___ 步 | D = ___ m（并写明估算方法） |

**题 (g)「how did you estimate this?」的答题要点**：要说明
- 起讫点如何定义（公园的哪两端、沿哪条轴线量），
- 用什么方法（连续步测 / 分段步测相加 / 直接在图上量后按比例尺换算 / 两法互校），
- 误差有多大（例如「步测 ≈ 195 m，图上量得 ≈ 200 m，两者相差 2.5%」）。
- **两法互校（步测 vs 图量）是本题真正想训练的东西**：任何一个野外数字都应该有第二种方法做 sanity check。

### 3.3 网格参考读取图解

```
        N ↑
   97 ─┼────────┼────────┼──   ← Northing 格线编号（向北递增）
       │        │  ×P    │
   96 ─┼────────┼────────┼──
       │        │        │
   95 ─┼────────┼────────┼──
       84       85       86      ← Easting 格线编号（向东递增）

P 点：位于 E 格线 85 与 86 之间，约 3/10 处 → Easting = 853
      位于 N 格线 96 与 97 之间，约 7/10 处 → Northing = 967
      6 figure GR = SJ 853 967
```

**位数与精度速查（复述 §2.3）**

```
4 figure → 1 km    |  6 figure → 100 m  |  8 figure → 10 m  |  10 figure → 1 m
每加一对数字，方格边长 ÷ 10
```

### 3.4 讲义给出的两个 GR（务必核对）

| 讲义原文 | 解析 | 精度 | 备注 |
|---|---|---|---|
| **Easting = 384775，Northing = 396699**（12 figure） | = **SJ 84775 96699** ≈ SJ 8477 9669 | **1 m** | 与「campus 位于 SJ 方格」一致，确为曼大主校区 |
| **GR 468667**（6 figure，Easting = 468、Northing = 667） | 讲义要求走到此处数树 | **100 m** | ⚠️ 见下方提示 |

> ⚠️ **一致性提示**：由 12 figure GR 推得的校园 6 figure GR 应形如 **847 966**，与讲义第 2 题给出的 **468667** 数字不吻合。可能的解释是该题使用了 Brunswick Park 纸图上另行印制的**本地格网 (local grid)**，或讲义排版沿用了旧版数字。
> **实操原则：以你手上那张 Brunswick Park 纸图上实际印制的格线编号为准**——GR 永远是相对于「你正在读的那张图上的格网」而言的。同时这也是一个好的自查习惯：拿到任何 GR，先用「它是否落在本图范围内」做合理性检验。

### 3.5 地质时间轴换算（Mapping the timeline）

**基本换算式**

设 Brunswick Park 实测长度 = **L 米**，代表 **T = 4.56 × 10⁹ 年**。

```
① 1 m 代表的时间：   t₁ = T / L        （单位：年 / m）
② 10 Ma 对应的长度：  d₁₀ = L × (10 × 10⁶) / T  =  L × 10⁷ / 4.56×10⁹  =  L / 456   （m）
③ 年龄 A（Ma，距今）在轴上距「地球形成」端的距离：
       x = L × (4560 − A) / 4560      （m）
   （若从「现今」端起算，则 x' = L × A / 4560）
```

**工作示例：取 L = 200 m**

| 量 | 计算 | 结果 |
|---|---|---|
| 1 m 代表多少时间 | 4.56×10⁹ / 200 | **2.28 × 10⁷ 年 = 22.8 Ma / m** |
| 10 Ma 对应多长 | 200 / 456 | **0.439 m ≈ 44 cm** |
| 1 cm 代表 | 22.8 Ma × 0.01 | **0.228 Ma = 228 000 年 / cm** |

**各界线在 200 m 轴上的位置（自「地球形成」端起量）**

| 标记点 | 年龄 (Ma) | x = 200×(4560−A)/4560 | 距**现今端**的距离 |
|---|---|---|---|
| Origin of the Earth | 4560 | **0 m** | 200 m |
| **Archean** 开始 | ≈ 4000 | **24.6 m** | 175.4 m |
| （Proterozoic 开始） | 2500 | 90.4 m | 109.6 m |
| （Phanerozoic / Cambrian 开始） | 538.8 | 176.4 m | 23.6 m |
| **Carboniferous** 开始 | 358.9 | **184.3 m** | 15.7 m |
| **Jurassic** 开始 | 201.4 | **191.2 m** | 8.8 m |
| **Paleogene** 开始 | 66.0 | **197.1 m** | 2.9 m |
| Present day | 0 | **200 m** | 0 m |

> **通用比例（与 L 无关，可直接乘你自己的 L）**：
> Archean 12.3% L｜Proterozoic 45.2% L｜Cambrian 88.2% L｜Carboniferous 92.1% L｜Jurassic 95.6% L｜Paleogene 98.6% L｜Present 100% L

**从这张表要读出的科学结论（讨论/报告里该写的）**

- **整个显生宙（有丰富宏体化石的全部历史）只占时间轴末端不到 12%**（200 m 中的最后 23.6 m）；
- 恐龙灭绝（66 Ma）距终点仅 **2.9 m**；
- 人属出现（≈ 2.8 Ma）距终点约 **12 cm**；智人（≈ 0.3 Ma）约 **1.3 cm**；有文字的人类史（≈ 5 ka）约 **0.2 mm** —— 一根铅笔线的宽度；
- 因此**前寒武纪（Precambrian）占据了地球历史的近 88%**，这正是「深时」的核心直觉。

**GR 记录要求（讲义最后一问）**

> "What are the 6 and 8 figure grid references for the 6 points on your timeline?"

- 6 个点 = Origin of the Earth、Archean、Carboniferous、Jurassic、Paleogene、Present day。
- **同一个点要写两种位数**：6 figure（100 m 精度）和 8 figure（10 m 精度）。
- **关键洞察（这才是这一问的出题意图）**：Carboniferous、Jurassic、Paleogene 三点在 200 m 轴上彼此只差 7 m、6 m —— **在 6 figure（100 m 方格）精度下，这几个点会得到完全相同的 GR，根本区分不开**；必须用到 8 figure（10 m）才勉强分开，1 m 精度（10 figure）才干净分开。
- 由此得出的通用原则：**记录精度必须与被记录对象的空间尺度相匹配**。野外记录一个直径 2 m 的露头用 4 figure GR 是没意义的；反过来给一个跨 5 km 的地层单元写 10 figure GR 也是虚假精度。

**记录表模板**

| 时间轴标记点 | 年龄 (Ma) | 距起点距离 (m) | 6 figure GR | 8 figure GR |
|---|---|---|---|---|
| Origin of the Earth | 4560 | 0 | | |
| Archean | ≈4000 | | | |
| Carboniferous | 358.9 | | | |
| Jurassic | 201.4 | | | |
| Paleogene | 66.0 | | | |
| Present day | 0 | | | |

---

## 四、课堂补充

本课**无 lecture、无录音转写**。讲义中与课堂组织/口吻相关的信息如下，一并记录：

- **课前准备（必做）**：
  > "You should have read the information on the **BB page** about maps and **watched the short videos**."
  即 Blackboard 上的地图阅读材料与短视频**必须课前看完**——本次实践课上不会重讲基础，只做一个 short introduction 就直接出门。
- **课堂流程**：室内简短导入 (short introduction) → 到户外 (Brunswick Park) 实作。
- **分组方式**：可 **2–5 人小组**，也可**独立完成**。
- **任务顺序自由**：
  > "You do not have to do the activities in order – please start where there is space."
  哪里人少先做哪个，避免所有人挤在同一个点位。
- **师资配置**：现场有 **4 名 lecturer + 4 名 Graduate Teaching Assistant (GTA)**，穿**荧光背心 (high viz jackets)** 以便识别；讲义反复强调「有问题就问，我们在这里就是帮你的」——第一周的课程文化基调是**降低提问门槛**。
- **「revision from Tuesday」**：Mapping the timeline 部分是周二理论课（地质年代/深时内容）的复习，说明本实践课与同周理论课是配套设计的。

---

## 五、Practical 要点

### 5.0 目的与装备

**目的**：在校园这一低风险环境中，把「比例尺换算 — 步测估距 — 网格定位 — 图面标绘」四步串成一条完整的野外工作流，并第一次实际使用野外记录本与地图板。

**Equipment（讲义原文清单，逐项说明用途）**

| 装备 | 英文 | 用途 |
|---|---|---|
| 地图板 | **mapping board** | 户外无桌面时的书写垫板，通常带透明防水套，固定地图不被风吹雨淋 |
| Brunswick Park 纸质地图 | paper map of Brunswick Park | 本次的作业底图，带比例尺与格网 |
| 野外记录本 | **notebook** | 所有原始数据（步数、读数、草图、时间、天气）的第一手记录处 |
| 铅笔 | pencil | 草绘与可修改的标注 |
| 钢笔/签字笔 | pen | 定稿线条与注记 |
| 手机/平板 + OS Locate app | phone or tablet with **OS Locate** app | 读取 GNSS 定位的国家网格 GR 与精度 |
| 时间表/年代表 | **time chart**（iPhone 可用 **ICS Timechart** app） | 查地质年代边界年龄，供 timeline 部分使用 |

> **注**：**ICS** = International Commission on Stratigraphy（国际地层委员会），其发布的 International Chronostratigraphic Chart 是地质年代的国际权威标准；ICS Timechart 是其官方 app。全学期查年代都以此为准。

---

### 5.1 活动一：Scale（比例尺）

**任务 a–d：桌面/图面工作**

| 题 | 问题 | 方法 | 答案形式 |
|---|---|---|---|
| a | What is the scale of this map? | 读图廓上的 RF 标注或 scale bar；若只有 scale bar，量出 bar 上「100 m」占多少 cm，再反算 S = 地面 cm ÷ 图上 cm | `1 : ______` |
| b | 地面 10 m 在图上量多长？ | 10 m = 1000 cm，÷ S | 例：S=1250 → **0.8 cm** |
| c | 图上 2 cm 代表地面多远？ | 2 cm × S，再换算成 m | 例：S=1250 → **25 m** |
| d | 你的步长是多少？ | 见 §3.2 标定流程：在已知长度上走、数步、相除、重复取平均 | 例：**1.5 m / stride** |

**任务 e–g：户外步测**

- **(e) Williamson Building 门 ↔ Simon Building 门**：沿两门之间尽可能直的路径走，数步 → × 步长。
- **(f) Simon Building ↔ Zochonis Building**：同法，**并且讲义明确要求「mark on the map where you have measured this」**——必须在地图上画出你所测的那条线段（起点、终点），否则别人无法复现你的数字。这是**可复现性 (reproducibility)** 的第一课。
- **(g) Brunswick Park 全长**：距离较长，建议
  1. 分段步测（每段 50 步左右记一次，防止数错），
  2. 或步测 + 图上量距互相校核，
  3. **写清估算方法与假设**（讲义直接问 "how did you estimate this?"）。

**数据处理与判读**

- 结果保留 2–3 位有效数字（步测精度不支持更多）。
- 若步测值与图量值差 > 10%，回头检查：是否步长标定错了？是否把 stride 当成 pace（差 2 倍）？是否路径绕行？
- 讲义 (g) 的结果**直接作为时间轴部分的输入 L**，所以这一步算错会连累后面全部计算——务必在进入 timeline 前确认 L。

---

### 5.2 活动二：Grid References（网格参考）

**题 1：走到 12 figure GR — Easting 384775, Northing 396699**

操作步骤：
1. 把 12 figure 拆成 100 km 方格 + 方格内坐标：**SJ 84775 96699**。
2. 在纸图上定位：先按 8 figure（SJ 8477 9669）找到 10 m 方格，再内插到 1 m。
3. 实地走到该点。
4. **观察问题**：*"what is the feature you can see on this building? How might this help increase biodiversity in Brunswick Park?"*
   - 这是**现场观察题，讲义未给答案**——必须到点位上抬头看那栋建筑，把看到的东西记进 notebook 并画草图。
   - 城市校园里典型的「提升生物多样性」建筑附加设施（答题时按实际所见选择并展开）：
     - **green wall / living wall（垂直绿墙）**：提供植被覆盖、传粉昆虫食源、降温滞尘、雨水滞留；
     - **green roof（绿色屋顶）**：无脊椎动物与鸟类栖息地；
     - **bird boxes / swift bricks（鸟巢箱、雨燕砖）**：现代建筑缺少缝隙，人工提供营巢位；
     - **bat boxes（蝙蝠箱）**：替代被封堵的屋檐栖息处；
     - **bee hotels / insect hotels（昆虫旅馆）**：为独居蜂提供筑巢孔洞；
     - **wildflower planting / 本地物种花坛**。
   - **答题逻辑（生态学论证链，比说出名字更重要）**：城市环境中的限制因子是**栖息地缺失与破碎化 (habitat loss & fragmentation)** → 人工结构提供**巢位/食源/庇护 (nesting sites, food resources, shelter)** → 使园区成为城市中的**踏脚石栖息地 (stepping-stone habitat)**，改善**生态连通性 (connectivity)** → 提高**物种丰富度 (species richness)**。

   **题 1a：OS Locate 读数与精度**
   - 打开 OS Locate，站定 30 秒等定位收敛，记录：GR、accuracy（±m）、时间。
   - 与讲义给的 GR 比较，计算差值（可直接把两组 E/N 相减，得到东向/北向偏差，再用勾股求总偏差）。
   - **回答 "How accurate is this GR?"**：不要只写 app 上的数字，要说明
     - app 报告的精度值；
     - 与已知 GR 的实际偏差；
     - 误差来源：城市峡谷多路径、建筑遮挡、卫星几何 (**DOP**)、手机接收机等级；
     - 结论：因此该点位在记录时应写到几位数字才诚实。

**题 2：走到 6 figure GR 468667，统计树木**

- 6 figure = 100 m 方格，因此这是一片区域而不是一个点。
- **"How many trees can you see?"** → 需要先**定义计数规则**（这是关键的方法学问题）：
  - 计数范围如何界定（就是那个 100 m 方格？还是目力所及？）；
  - 什么算「一棵树」（灌木算不算？多干丛生算一棵还是多棵？胸径下限？）；
  - **未明确定义规则的计数是不可复现的**——这是本题的隐含考点。
- **"How might you show their distribution and other characteristics?"** → 见 §2.6 的六种表达手段（点符号、颜色/形状分种、比例符号表示树冠或 DBH、密度分格、属性表关联编号、GIS 点图层）。答题时至少给出「**位置怎么画 + 属性怎么表达 + 图例怎么配**」三层。

**题 3–5：读出指定地物的 GR**

| 题 | 目标 | 要点 |
|---|---|---|
| 3 | **North East corner of the Williamson Building** | 「东北角」是一个明确的**点**，不要读到建筑中心 |
| 4 | **entrance to the Museum** | Manchester Museum 的入口（在 Oxford Road 一侧） |
| 5 | **South West corner of the Kilburn Building** | Kilburn Building（计算机系楼）西南角 |

**读 GR 的标准作业流程（SOP）**

1. 在图上准确定位目标点（角点要看清建筑轮廓的哪个拐角）。
2. **先 Easting**：读点左侧格线编号 → 目测点在格内的东向十分位。
3. **再 Northing**：读点下方格线编号 → 目测点在格内的北向十分位。
4. 按题目要求的位数写出，**E 与 N 位数相同**。
5. 建议同时用 OS Locate 在实地核对一次。
6. 记录格式建议：`Williamson Bldg NE corner — SJ 847 966 (6 fig) / SJ 8471 9663 (8 fig), read from map, 2 Oct`。

> **提高目测十分位精度的小技巧**：用一张纸条或直尺，把格线间距（图上距离）目视十等分；或用 **romer / roamer（网格尺）**——OS 罗盘和某些直尺上刻有对应 1:25 000 与 1:50 000 的 romer 刻度，可直接读出第三、四位数字。

---

### 5.3 活动三：Mapping the timeline（把地质时间画到公园里）

**这是把前两项技能合起来用的综合任务。**

**步骤**

1. **取 L**：填入 §5.1(g) 得到的 Brunswick Park 长度。
   > `Length of Brunswick Park = ______ m`
2. **算 1 m 代表多少时间**：`t₁ = 4.56×10⁹ / L` 年 —— 注意换算成 Ma 更好读（`t₁ = 4560 / L` Ma/m）。
3. **算 10 Ma 对应多长**：`d₁₀ = L / 456` m。
4. **在地图上画时间轴**：画一条长度等于 L（**按地图比例尺换算后的图上长度** = L ÷ S）的直线，两端分别标 "Origin of the Earth (4560 Ma)" 与 "Present day (0)"。
   - ⚠️ 这里有一次**双重比例尺换算**：先把「时间 → 地面距离」，再把「地面距离 → 图上距离」。两步都要做，漏掉第二步是本节最常见错误。
5. **标出 4 个界线**：Archean、Carboniferous、Jurassic、Paleogene，位置按 `x = L × (4560 − A)/4560` 计算（见 §3.5 表）。
6. **读出 6 个点的 6 figure 与 8 figure GR** 并填表。

**结果判读**

- 检查：Carboniferous / Jurassic / Paleogene 三点是否挤在轴的末端一小段内？若不是，多半是年龄数量级搞错了（例如把 66 Ma 当成 66 Ga，或把 4.56 billion 当成 4.56 million）。
- 检查：6 figure GR 是否出现重复？**出现重复是正常且是预期的结论**（说明 100 m 精度不足以分辨），要在答案里写出来，而不是硬改数字。

---

## 六、易错点 / 重点难点

**比例尺相关**

1. **单位不统一**：算 (b) 时忘了把 10 m 换成 1000 cm，直接 10 ÷ 1250。
2. **乘除颠倒**：图 → 地是**乘**分母，地 → 图是**除**分母。判据：地面距离一定比图上距离**大**。
3. **大/小比例尺说反**：1:1250 是大比例尺。
4. **自绘图只写 RF 不画 scale bar**：一旦缩印就全错，评估必扣分。

**步测相关**

5. **stride 与 pace 混淆**——结果直接差 2 倍，本周最致命的单点错误。标定和使用必须用同一个定义。
6. **只走一次就定步长**：没有重复测量、没有取平均。
7. **刻意迈大步标定，实际用自然步走**（或反之）：系统性偏差。
8. **忘记路径不是直线**：绕开花坛/人群后仍按直线距离报告。
9. **有效数字过多**：步测结果写成 `87.42 m`。

**网格参考相关**

10. **Easting / Northing 顺序颠倒**——最常见的 GR 错误。永远「先右后上」。
11. **E 与 N 位数不等**（如写成 `SJ 847 9663`）：GR 必须成对等长。
12. **格线编号四舍五入**：应取目标点**西南侧**的格线（向下取整）。读 84.7 的格应写 84 而不是 85。
13. **漏写 100 km 方格字母**：在跨图幅或正式报告中，`847966` 是有歧义的，必须写 `SJ 847966`。
14. **把 12 figure 的绝对坐标当成方格内坐标**：384775 不是「SJ 内 Easting 384775」（方格内最大只有 99999），首位「3」是 100 km 带号。
15. **虚假精度 (spurious precision)**：GNSS 显示 12 位就照抄 12 位，而 accuracy 是 ±10 m。**位数必须与实际精度匹配**，并把 accuracy 一并记录。
16. **不核对 GR 是否落在本图范围内**（参见 §3.4 讲义 468667 与 847966 的不一致）——拿到任何 GR 先做范围合理性检验。

**时间轴相关**

17. **Ga / Ma / ka 混淆**，或 billion 数量级搞错：4.56 Ga = 4560 Ma = 4.56 × 10⁹ a。
18. **只做「时间 → 地面距离」而漏掉「地面距离 → 图上距离」**：画到图上的线长必须除以比例尺分母。
19. **方向搞反**：轴的哪一端是 4560 Ma、哪一端是现今，必须标清；计算 x 时要与所选起点一致。
20. **年龄取值不一致**：一会儿用 4.56 Ga 一会儿用 4.6 Ga。全篇统一，并注明数据来源（ICS chart）。
21. **看到几个点 GR 相同就以为算错了**：那正是本练习要你发现的现象。

**记录与规范（评估失分点）**

22. **题 (f) 忘记「mark on the map where you have measured this」**：讲义明写的要求，漏做直接失分。
23. **题 (g) 只给数字不答 "how did you estimate this?"**：方法说明与数字同等重要。
24. **野外记录本缺少日期、时间、天气、地点、观察者**：野外记录的元数据是硬性规范。
25. **图上缺北向箭头 / 图例 / 标题**：TSNAKE 六要素缺一即扣。
26. **用铅笔以外的笔起草**：无法修改；正确做法是铅笔起草、墨水笔定稿。
27. **观察题只写名词不给机制**：例如只答「有绿墙」而不说明它**如何**提升生物多样性——本课强调「观察 + 解释」成对出现。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| map scale | 地图比例尺 | 图上距离与地面实际距离之比 |
| Representative Fraction (RF) | 代表分数 | 如 1:1250，无量纲的比例尺写法 |
| scale bar / linear scale | 线段比例尺 | 画在图上的带刻度线段，缩印后仍然正确 |
| large scale map | 大比例尺地图 | 分母小（1:1250），范围小、细节多 |
| small scale map | 小比例尺地图 | 分母大（1:250 000），范围大、细节少 |
| stride | 复步 / 跨步 | 同一只脚连续两次落地的距离，约 1.5 m |
| pace / step | 单步 | 一只脚到另一只脚落地，约 0.75 m，是 stride 的一半 |
| pacing | 步测 | 用数步数 × 步长来估算距离的野外方法 |
| calibration | 标定 | 在已知长度上测出自己步长的过程 |
| UK National Grid | 英国国家网格 | Ordnance Survey 的全国平面坐标参考系统 |
| Ordnance Survey (OS) | 英国国家测绘局 | 英国官方地图机构，OS Locate 为其定位 app |
| 100 km grid square | 100 km 方格 | 用两字母表示的网格单元，曼大校园位于 **SJ** |
| Easting | 东距 | 自方格西南角向东的距离，GR 中**先写** |
| Northing | 北距 | 自方格西南角向北的距离，GR 中**后写** |
| Grid Reference (GR) | 网格参考 | 用 Easting + Northing 表示位置的编码 |
| 6 figure GR | 六位网格参考 | E 3 位 + N 3 位，精度 100 m |
| 8 figure GR | 八位网格参考 | E 4 位 + N 4 位，精度 10 m |
| 12 figure GR | 十二位网格参考 | E 6 位 + N 6 位的全数字绝对坐标，精度 1 m |
| "along the corridor, up the stairs" | 先走廊后楼梯 | 记忆 GR 先读 Easting 再读 Northing 的口诀 |
| romer / roamer | 网格尺 | 刻有格内十分位刻度的读图小尺，用于精确读 GR |
| grid north | 网格北 | 地图格线所指的北 |
| true north | 真北 | 指向地理北极 |
| magnetic north | 磁北 | 罗盘所指的北 |
| magnetic declination | 磁偏角 | 磁北与真北（或网格北）之间的夹角 |
| GNSS / GPS | 全球导航卫星系统 | 卫星定位技术，手机定位的基础 |
| accuracy | 精度 / 定位不确定度 | app 报告的位置误差半径，单位 m |
| spurious precision | 虚假精度 | 记录的位数超出实际测量精度所支持的位数 |
| urban canyon | 城市峡谷 | 高楼夹峙导致卫星信号遮挡与多路径的环境 |
| multipath | 多路径效应 | 信号经建筑反射后到达接收机，造成定位偏差 |
| mapping board | 地图板 | 户外固定并保护地图、提供书写面的硬板 |
| field notebook | 野外记录本 | 记录原始观测数据、草图与元数据的本子 |
| plot (a position) | 标绘 | 把实地位置画到地图上 |
| key / legend | 图例 | 说明地图上各符号与颜色含义的说明框 |
| north arrow | 北向箭头 | 指示地图方位的箭头 |
| proportional symbol | 比例符号 | 符号大小正比于某个属性值（如树冠直径） |
| DBH (diameter at breast height) | 胸径 | 离地约 1.3 m 处测得的树干直径 |
| canopy | 树冠 | 树木枝叶展开的部分 |
| distribution | 分布 | 要素在空间上的排布格局 |
| density map | 密度图 | 用分格统计值表示要素疏密的专题图 |
| biodiversity | 生物多样性 | 某地区物种、基因与生态系统的丰富程度 |
| green wall / living wall | 绿墙 / 生态墙 | 覆植被的建筑立面，为城市提供栖息地 |
| green roof | 绿色屋顶 | 覆植被的屋面，提供无脊椎动物与鸟类栖息地 |
| bird box / swift brick | 鸟巢箱 / 雨燕砖 | 嵌入建筑的人工巢位 |
| bat box | 蝙蝠箱 | 为蝙蝠提供的人工栖息装置 |
| habitat fragmentation | 栖息地破碎化 | 连续栖息地被割裂成孤岛，威胁物种存续 |
| stepping-stone habitat | 踏脚石栖息地 | 城市中的小块绿地，帮助物种在斑块间迁移 |
| connectivity | 生态连通性 | 生物在栖息地斑块之间移动的难易程度 |
| deep time | 深时 | 地质学的极长时间尺度概念 |
| timeline analogy | 时间轴类比 | 把地质时间按比例映射到空间长度上的教学法 |
| ka / Ma / Ga | 千年 / 百万年 / 十亿年 | 地质年代单位，1 Ga = 1000 Ma = 10⁶ ka |
| ICS (International Commission on Stratigraphy) | 国际地层委员会 | 发布国际年代地层表的权威机构 |
| International Chronostratigraphic Chart | 国际年代地层表 | 全球统一的地质年代标准表（time chart） |
| Hadean | 冥古宙 | 4567–4031 Ma，地球最早、几无岩石记录的时期 |
| Archean | 太古宙 | 约 4000–2500 Ma，最古老岩石与最早生命证据 |
| Proterozoic | 元古宙 | 2500–538.8 Ma，含大氧化事件与最早多细胞生物 |
| Precambrian | 前寒武纪 | 冥古宙+太古宙+元古宙的合称，占地球史约 88% |
| Phanerozoic | 显生宙 | 538.8 Ma 至今，宏体化石丰富的时期 |
| Carboniferous | 石炭纪 | 358.9–298.9 Ma，大规模成煤期 |
| Jurassic | 侏罗纪 | 201.4–143.1 Ma，恐龙繁盛期 |
| Paleogene | 古近纪 | 66.0–23.03 Ma，K–Pg 大灭绝之后哺乳动物辐射 |
| GTA (Graduate Teaching Assistant) | 研究生助教 | 实践课现场的辅助教学人员 |
| high viz jacket | 荧光背心 | 野外/户外教学中便于识别教师的高可见度背心 |
| reproducibility | 可复现性 | 他人能依你的记录重复出同样结果的性质 |
| BB page (Blackboard) | Blackboard 课程页 | 课程材料与预习视频的在线平台 |
