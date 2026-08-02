# Week 4 — 燃烧化石燃料与大气变化：理想气体定律、分压与配平方程 (Burning Fossil Fuels and Altering the Atmosphere)

## 一、本周主题

本周是 Introductory Maths for Natural Scientists 五周课程中的**第 4 周**。老师在课上开门见山地说明：**本周基本没有新的数学内容 (there's not really any new maths that we're covering this week)**，用到的全部是前几周已经讲过的工具——尤其是 **Week 1 的单位换算 (units) 与摩尔 (moles)**——再加上中学化学里的**配平方程 (balancing equations)**。

本周的主线是一个真实的环境科学问题：**全球一年燃烧化石燃料，消耗掉多少 $\mathrm{O_2}$、产生多少 $\mathrm{CO_2}$ 和 $\mathrm{H_2O}$，以及这些 $\mathrm{CO_2}$ 会让大气浓度上升多少 ppmv**。为了解决它，需要三块知识：

1. **理想气体定律 (the ideal gas law)** —— 把"摩尔数"和"体积/压强/温度"联系起来；
2. **道尔顿分压定律 (Dalton's law of partial pressures)** 与由此导出的 **体积混合比 (volumetric mixing ratio) / ppmv**；
3. **碳氢化合物燃烧方程的配平 (balancing hydrocarbon combustion equations)** 与**化学计量常数 (stoichiometric constants)**。

课程定位上，本周同时承担"环境科学背景介绍"的功能：老师讲了 Mauna Loa 的 $\mathrm{CO_2}$ 观测记录、温室效应 (greenhouse effect) 的物理机制、气候模式预测的不确定性，并强调"**这些物理你今天不需要精确掌握，但明白背后是什么很重要，明年在大学课程里还会反复遇到**"。

**课程进度提醒（practical transcript 中老师专门宣布）**：
- 下周（Week 5）**照常有 lecture 和 practical**；
- 再下一周**周三 (Wednesday) 有 summative test**，那一周的**周五没有 lecture 也没有 practical**；
- 再往后开始跟 **Dr. Gilman 学统计 (statistics)**。

---

## 二、核心概念

### 2.1 理想气体定律 (The ideal gas law)

$$PV = NR_{\text{gas}}T \qquad\Longleftrightarrow\qquad \frac{PV}{T} = \text{constant}$$

符号含义：
- $P$ = 压强 (pressure)，SI 单位 **Pa (Pascal)**；
- $V$ = 气体体积 (volume)，SI 单位 $\mathrm{m^3}$；
- $T$ = 温度 (temperature)，**必须用 Kelvin (K)**；
- $N$ = 气体的**摩尔数 (number of moles)**；
- $R_{\text{gas}}$ = **通用气体常数 (universal gas constant)** $= 8.314\ \mathrm{J\,K^{-1}\,mol^{-1}}$。

老师对这条定律的口头解读（transcript 原话意译）：

> "压强乘以体积再除以温度，对任何理想气体来说是一个常数。这意味着**如果你改变气体的压强，那么体积或温度必须有一个跟着变；如果你改变温度，那么压强或体积必须有一个跟着变。你不可能只改变其中一个而其他都不动。**"

**为什么可以把大气当理想气体？** 大气是气体的混合物 (a mixture of gases)：主要成分是**氮气 (nitrogen, $\mathrm{N_2}$)**，其次是**氧气 (oxygen, $\mathrm{O_2}$)**，再加上一堆**痕量气体 (trace gases)**，其中就包括我们关心的 $\mathrm{CO_2}$。老师说：**在我们生活和呼吸的这一层大气里，理想气体假设是非常好的近似 (a very good assumption)**，"throughout most of the atmosphere we can assume the ideal gas law is obeyed"。

而且大气本身时刻在变：即使在地表，**气压 (atmospheric pressure) 一直在小幅变化，温度也有日变化 (diurnal) 和季节变化 (seasonal)**——这正是 $PV/T$ 恒定所描述的动态平衡。

### 2.2 单位陷阱 (Be careful with units!)

这是本周老师反复强调的重点（"units, units, units"，回扣 Week 1）：

**压强 (pressure)**
- 大气压常用 **hPa (hectoPascal, 百帕)** 表示；
- $1\ \mathrm{hPa} = 1\ \mathrm{mbar}$（毫巴，旧文献常见，两者**等价**，但 hPa 才是 SI 单位）；
- **代入理想气体定律前必须换成 Pa**：$1\ \mathrm{hPa} = 100\ \mathrm{Pa}$；
- 老师原话："That's just a conversion factor of 100 from Pascals to hectoPascals, just as you might change between centimetres and metres."（转写里说成 "10"，是自动转写/口误，正确是 **100**：hecto- = $10^2$。）
- 例：标准大气压 $1013\ \mathrm{hPa} = 1.013\times 10^5\ \mathrm{Pa}$。

**温度 (temperature)**
- **理想气体定律里的 $T$ 永远是 Kelvin**。"If you put in the temperature in Celsius, you will get the wrong answer."
- $T(\mathrm{K}) = T(^\circ\mathrm{C}) + 273.15$（课上口头说约 273）；
- 三种温标 (Kelvin / Celsius / Fahrenheit) 的对比图要点：
  - **Celsius 与 Kelvin 的"一度"大小完全相同**，只是**零点偏移 (offset) 273 度**；水的凝固点到沸点之间，Celsius 和 Kelvin 都正好差 100 度；
  - Celsius 把零点设在水的凝固点；**Kelvin 把零点设在绝对零度 (absolute zero)，即一切运动停止的那一点**；
  - Fahrenheit 在英国/欧洲和科学界已基本不用了。老师举了个记忆用的玩笑："美国天气预报说 'it's going to be in the 90s today'（华氏 90 多度），如果那是 90 摄氏度，我们就都极其难受了。"

### 2.3 道尔顿分压定律 (Dalton's law of partial pressures)

**定律陈述**：气体混合物施加的**总压强等于各组分气体单独施加的压强之和**。

$$p = p_1 + p_2 + p_3 + \cdots + p_N = \sum_i p_i$$

其中 $p_i$ 是第 $i$ 种气体的**分压 (partial pressure)**。

**理想气体定律对每种气体单独成立**：

$$p_i V = N_i R_{\text{gas}} T$$

注意这里：**每种气体都占据整个容器体积 $V$，但只贡献自己的分压 $p_i$**。

**老师的"房间实验"直观解释（transcript 独有，非常重要）**：

> 想象这个房间里飘满了红点（氮气 $\mathrm{N_2}$）、蓝点（氧气 $\mathrm{O_2}$）、绿点（二氧化碳 $\mathrm{CO_2}$），它们全混在一起。压强的来源，就是这些分子不断撞击墙壁和我们身体。
>
> 现在做个思想实验：**把所有蓝色的氧气和所有红色的氮气都拿走，只留下 $\mathrm{CO_2}$。** 它们还会频繁撞墙吗？不会——因为 $\mathrm{CO_2}$ 数量很少。偶尔"啵"一下，撞击频率非常低，所以**只剩下 $\mathrm{CO_2}$ 时压强很低，这个压强就是 $\mathrm{CO_2}$ 的分压 $p_1$**。
>
> 现在把氧气放回来（大家可以呼吸了）：撞击频率明显上升，我们**加上了氧气的分压 $p_2$**。再把氮气放回来（氮气分子非常非常多）：**加上 $p_3$**。你现在感受到的总压强，就是绿的+蓝的+红的加在一起。

这就是道尔顿定律的物理图像：**压强来自分子撞击，各组分的撞击贡献可以直接相加。**

### 2.4 分体积 (Partial volumes) —— 另一种等价看法

除了"分压"，还可以换个角度想（老师强调这**在现实中不会真的发生，只是一个 thought process**）：

保持**总压强 $P$ 和温度 $T$ 不变**，想象把混合气体中的每种气体分别装进各自的角落，每种气体占据自己的**分体积 (partial volume) $V_i$**。

对每种气体在其分体积中：

$$P V_i = N_i R_{\text{gas}} T$$

而对整体：

$$P V = N R_{\text{gas}} T$$

并且有两个守恒关系：

$$N = N_1 + N_2 + \cdots + N_n \qquad\text{以及}\qquad V = V_1 + V_2 + \cdots + V_n$$

老师的形象说法："把所有 $\mathrm{CO_2}$ 塞到那个角落，所有氧气放这边，所有氮气放那边——只有一个角落能呼吸——但**它们的体积加起来必须等于整个房间的体积**。"

### 2.5 体积混合比 (Volumetric mixing ratio) 与 ppmv

**定义**：某种气体所占的体积，占整体气体体积的比例。

$$\text{mixing ratio} = \frac{V_i}{V}$$

**关键结论（可由 2.4 直接推出）**：把 $PV_i = N_i R T$ 除以 $PV = NRT$：

$$\frac{V_i}{V} = \frac{N_i}{N}$$

同理把 $p_i V = N_i R T$ 除以 $pV = NRT$：

$$\frac{p_i}{p} = \frac{N_i}{N}$$

于是三者完全等价：

$$\boxed{\ \frac{V_i}{V} = \frac{N_i}{N} = \frac{p_i}{p}\ }$$

即 **体积混合比 = 摩尔分数 (mole fraction) = 分压比**。这是本周最有用的一条恒等式——它意味着**只要算出摩尔数之比，就直接得到 ppmv**，不需要真的去算体积。

**ppmv (parts per million by volume, 百万分之几体积比)**：

$$\text{ppmv} = \frac{V_i}{V}\times 10^{6} = \frac{N_i}{N}\times 10^{6}$$

老师解释为什么要乘 $10^6$："这个比例通常是非常小的数，所以我们通常把它乘以一百万 ($10^6$)，得到 parts per million by volume——**每一百万份空气里有一份是二氧化碳**。"

**用途**：主要用于表达**污染物 (pollutants)** 和痕量成分的浓度——$\mathrm{CO_2}$、其他温室气体如**甲烷 (methane)**、以及气溶胶 (aerosols)、花粉 (pollen) 等。当仪器精度提高、要测更小的量时，还会用 **ppbv (parts per billion by volume)**，甚至 **pptv (parts per trillion by volume)**。

### 2.6 碳氢化合物的燃烧与配平 (Burning hydrocarbons)

**具体例子（slides 上的三个）**：

$$\mathrm{CH_4} + 2\,\mathrm{O_2} \rightarrow \mathrm{CO_2} + 2\,\mathrm{H_2O}$$
$$\mathrm{C_2H_6} + 3.5\,\mathrm{O_2} \rightarrow 2\,\mathrm{CO_2} + 3\,\mathrm{H_2O}$$
$$\mathrm{C_3H_8} + 5\,\mathrm{O_2} \rightarrow 3\,\mathrm{CO_2} + 4\,\mathrm{H_2O}$$

**通用规则（本周必背）**：设**碳链长度 (length of the carbon chain) 为 $n$**，则对于**烷烃 (alkane)**：

| 项目 | 数量 | 理由 |
|---|---|---|
| 分子中的氢原子数 | $2n+2$ | 烷烃通式 $\mathrm{C}_n\mathrm{H}_{2n+2}$ |
| 生成的 $\mathrm{CO_2}$ 分子数 | $n$ | 每个 $\mathrm{CO_2}$ 只含 1 个 C，必须与碳链长度平衡 |
| 生成的 $\mathrm{H_2O}$ 分子数 | $\dfrac{2n+2}{2} = n+1$ | 每个水分子含 2 个 H，所以氢原子数除以 2 |
| 消耗的 $\mathrm{O_2}$ 分子数 | $n + \dfrac{2n+2}{4}$ | 右边共有 $2n$（来自 $\mathrm{CO_2}$）$+\,(n+1)$（来自 $\mathrm{H_2O}$）个 O 原子，除以 2 得 $\mathrm{O_2}$ 分子数 |

化简 $\mathrm{O_2}$ 系数：

$$n + \frac{2n+2}{4} = \frac{4n + 2n + 2}{4} = \frac{6n+2}{4} = \frac{3n+1}{2}$$

**通式**：

$$\mathrm{C}_n\mathrm{H}_{2n+2} + \frac{3n+1}{2}\,\mathrm{O_2}\ \rightarrow\ n\,\mathrm{CO_2} + (n+1)\,\mathrm{H_2O}$$

**验算**：
- $n=1$：$\frac{3+1}{2}=2$ → $\mathrm{CH_4}+2\mathrm{O_2}\to \mathrm{CO_2}+2\mathrm{H_2O}$ ✓
- $n=2$：$\frac{6+1}{2}=3.5$ → $\mathrm{C_2H_6}+3.5\mathrm{O_2}\to 2\mathrm{CO_2}+3\mathrm{H_2O}$ ✓
- $n=3$：$\frac{9+1}{2}=5$ ✓　$n=4$：$\frac{12+1}{2}=6.5$ ✓　$n=5$：$\frac{15+1}{2}=8$ ✓

**配平的推荐顺序（老师明确讲的解题流程）**：
1. **先定 $\mathrm{CO_2}$ 数**：等于碳链长度 $n$（"the easiest thing to start with"）；
2. **再定 $\mathrm{H_2O}$ 数**：氢原子总数 $\div\,2$；老师举例："如果你有 8 个氢原子，就能生成 4 个水分子，因为每个水分子需要 2 个氢。"
3. **最后倒推 $\mathrm{O_2}$ 数**：把右边所有 O 原子数出来（$\mathrm{CO_2}$ 贡献 $2n$ 个，$\mathrm{H_2O}$ 贡献 $n+1$ 个），再把这些 O 原子两两打包成 $\mathrm{O_2}$ 分子。老师原话："如果我们有 4 个 O 原子，那就相当于 2 个 $\mathrm{O_2}$——总共还是 4 个原子，只是我们把它们排成 2 个 $\mathrm{O_2}$ 分子。"

### 2.7 化学计量常数 (Stoichiometric constants)

在 practical 里，燃料的化学式不是整数下标（因为是**平均组成 approximate chemical composition**），所以要用**未知的化学计量常数 $x,\ y,\ z$** 来配平：

$$\mathrm{CH_{1.5}} + x\,\mathrm{O_2}\ \rightarrow\ y\,\mathrm{CO_2} + z\,\mathrm{H_2O}$$

物理意义：**每消耗 1 mol 燃料，就消耗 $x$ mol 氧气，生成 $y$ mol $\mathrm{CO_2}$ 和 $z$ mol $\mathrm{H_2O}$。** 这正是解决整个问题的钥匙。

### 2.8 停留时间 (Residence time) 与 stock–flow 思想

这是回答"为什么不担心燃烧释放的水汽"的核心概念，也是 Problem 4 的提示 ("answering this requires only stock–flow–residence time considerations")。

$$\tau = \frac{\text{stock (库存量)}}{\text{flow (通量/流入率)}}$$

- **$\mathrm{CO_2}$ 的停留时间极长**：老师给的数字是——今天排到大气里的 $\mathrm{CO_2}$，**100 年后还有约 30% 留在那里，1000 年后还有约 13%**。所以 $\mathrm{CO_2}$ 会**逐年累积 (build up)**，"we're continually building on what was there before"。
- **水汽 (water vapour) 的停留时间极短**：只有**天 (days)** 的量级。放进去很快就以降水形式出来了 ("it precipitates to Earth")。所以即使水汽是更强的红外吸收体，它也**不会累积**。
- 老师的结论："这就是为什么我们如此关心 $\mathrm{CO_2}$ 和其他**停留时间很长**的温室气体。"

---

## 三、公式与图表

### 3.1 公式汇总

| 公式 | 含义 |
|---|---|
| $PV = NR_{\text{gas}}T$ | 理想气体定律；$R_{\text{gas}} = 8.314\ \mathrm{J\,K^{-1}\,mol^{-1}}$ |
| $\dfrac{PV}{T} = \text{const}$ | 同上的等价形式（对固定摩尔数） |
| $p_iV = N_iR_{\text{gas}}T$ | 每种组分气体单独满足理想气体定律（分压形式） |
| $PV_i = N_iR_{\text{gas}}T$ | 分体积形式（同压同温） |
| $p = \sum_i p_i$ | 道尔顿分压定律 |
| $V = \sum_i V_i$，$N = \sum_i N_i$ | 分体积与摩尔数守恒 |
| $\dfrac{V_i}{V}=\dfrac{N_i}{N}=\dfrac{p_i}{p}$ | 体积混合比 = 摩尔分数 = 分压比 |
| $\text{ppmv} = \dfrac{N_i}{N}\times 10^6$ | 百万分体积比 |
| $T(\mathrm{K}) = T(^\circ\mathrm{C})+273.15$ | 温标转换 |
| $1\ \mathrm{hPa}=1\ \mathrm{mbar}=100\ \mathrm{Pa}$ | 压强单位 |
| $\mathrm{C}_n\mathrm{H}_{2n+2} + \frac{3n+1}{2}\mathrm{O_2}\to n\mathrm{CO_2}+(n+1)\mathrm{H_2O}$ | 烷烃完全燃烧通式 |
| $V_m = 22.4\ \mathrm{L\,mol^{-1}}$ (STP) | 标准状况摩尔体积（practical 中反复使用） |
| $\tau = \text{stock}/\text{flow}$ | 停留时间 |

**常用换算（practical 必用）**：
- $1\ \mathrm{tonne} = 10^3\ \mathrm{kg} = 10^6\ \mathrm{g}$
- $1\ \mathrm{m^3} = 10^3\ \mathrm{L}$
- 摩尔质量：$\mathrm{C}=12\ \mathrm{g\,mol^{-1}}$，$\mathrm{H}=1\ \mathrm{g\,mol^{-1}}$，$\mathrm{H_2O}=18\ \mathrm{g\,mol^{-1}}$

### 3.2 温标对照图 (Kelvin / Celsius / Fahrenheit)

图的要点：三根并排的温标尺。**Kelvin 与 Celsius 刻度间距相同**（水的凝固→沸腾在两个标度上都是 100 度），只是零点相差 273；**Fahrenheit 刻度更密**（水的凝固→沸腾是 180 华氏度）。绝对零度 = 0 K = $-273.15\ ^\circ$C。图注：Image courtesy of Windows to the Universe (Randy Russell)。

### 3.3 大气组成图 (Composition of atmosphere by moles)

要点：大气是气体混合物，按摩尔数计主要是 $\mathrm{N_2}$（约 78%）、$\mathrm{O_2}$（约 21%），其余是氩气和各种痕量气体（含 $\mathrm{CO_2}$）。**Practical 计算 $\mathrm{O_2}$ 消耗百分比时用的就是 21% 这个数。** 每种气体施加各自的分压 $p_i$，总压是分压之和。

### 3.4 Mauna Loa $\mathrm{CO_2}$ 曲线（Keeling Curve）

数据来源：**Mauna Loa Observatory, Hawaii**，NOAA ESRL (https://www.esrl.noaa.gov/gmd/ccgg/trends/)，**从 1950 年代末开始连续观测至今**。

**图的三个关键特征**：

1. **长期上升趋势 (long-term increase)**：$\mathrm{CO_2}$ 浓度持续升高。

2. **梯度 (gradient) 在变陡——即上升速率本身也在加快**（slides 上明确要求 "Think about how much the $\mathrm{CO_2}$ concentration has increased over time (gradient)"）：
   - 2000→2010 的 10 年：从约 365 ppm 升到约 385 ppm，$385-365 = 20\ \mathrm{ppm}$，**梯度 $=20/10 = 2\ \mathrm{ppm\ yr^{-1}}$**；
   - 1960→1970 的 10 年：从约 315 ppm 升到约 325 ppm，即 10 ppm/10 yr，**梯度 $= 1\ \mathrm{ppm\ yr^{-1}}$**；
   - 结论：**不仅 $\mathrm{CO_2}$ 在增加，$\mathrm{CO_2}$ 的变化率 (rate of change) 也在增加**。
   - 更新数据（老师课上临时展示到 2024 的图）：2023 年 9 月 = **418 ppm**，2024 年 9 月 = **422 ppm**，一年约 **4 ppm**。

3. **年周期振荡 (annual cycle)**，振幅约 4–5 ppm，成因是**北半球植被生长季 (growing season)**：
   - $\mathrm{CO_2}$ 峰值出现在 **4–5 月**，正好在植物大规模生长之前；
   - 夏季北半球植被疯长，**光合作用吸收 $\mathrm{CO_2}$（碳汇 sink）**，浓度下降；
   - 约 **9–10 月**生长停止，落叶开始**腐烂分解 (decay) 释放 $\mathrm{CO_2}$**——**汇消失了，而人类排放仍在继续**，且植被从汇变成了小的源；
   - 冬季浓度持续上升，直到次年 4 月再次转折；
   - 大气完全混合与环流还带来**一点时间滞后 (time lag)**。

**为什么把观测站放在夏威夷山上？** 老师专门讲了：我们要测的是**全球背景值 (global background) / 基线测量 (baseline measurement)**，不是汽车尾气、工厂、住宅区那种局地信号，也不是"几千个学生每小时整点换教室"造成的扰动。所以背景观测站都设在**偏远地区、山上，位于"边界层 (boundary layer)"之上**——边界层是大气最低的约 0.5–1 km，人类活动和影响都集中在那里。我们要的是**充分混合、均一化 (mixed and homogenised) 之后的空气**。此外，南北半球环流不同，所以要对全球取一定平均。

**能从记录里看出的异常年份**：极端炎热年份植物大量死亡、生长减少，年周期的下降幅度就不如往常明显——老师举了 **2022 年英格兰南部和欧洲大范围干旱变褐**的例子，这在 $\mathrm{CO_2}$ 记录里能看出来。

### 3.5 $\mathrm{CO_2}$ 年增量图与十年平均增量图

- **逐年 $\mathrm{CO_2}$ 变化图**：数据比较散乱（受光合作用年际变化影响：太热、太冷、太湿都会影响），但**从左到右有明显上升趋势**——每年的增量在变大。
- **十年平均增量图（黑线表示 10 年平均）**：1990–2000 年间有一段增速放缓（增量比前十年小），但之后又重新加速。

### 3.6 温室效应示意图 (The greenhouse effect)

老师讲的完整能量链条（这是本周最重要的定性物理）：

1. **太阳辐射 (solar energy) 穿过大气**：大部分可见光和近红外直接穿透大气到达地表。**上层大气挡掉了短波的"有害物"——X 射线和短波紫外 (UVC)**。
2. **地表吸收太阳能 → 地表升温 (the Earth's surface warms up)**。
3. **一部分被反射回太空 (reflected back into space)**：
   - 老师举的直观例子：海滩上看到的**海面日光闪烁 (sun glint)**，波浪起伏时闪闪发光，那就是太阳辐射被海面反射；
   - 草看起来是绿色，是因为它把绿色波段的光反射掉了（植物主要利用红光和蓝光）；
   - **云 (cloud) 也会反射**——既能在太阳辐射到达地表前把它反射回太空，也能把地表反射上来的辐射再反射下去。
4. **地表和一切物体都在向外发射辐射 (emitting radiation)**：老师强调 "Me, you, the floor, the chairs — we're all emitting energy." **发射的能量取决于自身温度**。太阳温度约 6000 K 左右，发射的是**可见光**；地球和我们温度低得多，发射的是**长波红外辐射 (long-wavelength infrared radiation)**——肉眼看不见，但确实在发生。
5. **温室气体 (greenhouse gases) 吸收这些外向的长波辐射**，自身温度升高，然后**自己也发射辐射**：一部分继续向外去太空，**一部分向下回到地表**。
6. 地表因此**接收到了原本不会接收到的额外辐射能量，于是进一步升温**。

**一句话总结**：温室气体阻止了一部分辐射逃逸到太空，把能量送回地表，从而使地表变暖。

**正反馈 (positive feedback)——课上学生提问引出的补充**：
- 冰的**反射率 (reflectivity/albedo) 很高**，极地大量太阳辐射直接被反射回太空而未被吸收；
- 一旦**冰融化**，露出下面的**深色岩石**，就会**吸收更多辐射并升温**，进而导致更多冰融化；
- 老师说这就叫 **positive feedback**，气候系统里**有大量正反馈也有负反馈**，"that's what makes it so complicated and difficult to model"。

### 3.7 气候预测图 (Climate predictions)

图的要点：多条不同颜色的曲线代表不同的**排放情景 (scenarios)**，本世纪内温度都在上升，但**预测范围很宽**；右侧的竖直**误差棒 (bars)** 表示各个模式在同一情景下输出结果的范围。

老师的解释：
- 世界上多个机构各自有**气候模式 (climate models)**；
- 为了检验模式之间是否有**共识 (consensus)**，大家跑**固定情景 (fixed scenarios)**：比如 "business as usual"（按某一年的速率继续排放）、"减排 50%"、"减排 90%" 等，都跑到 **2100 年**；
- 各模式**工作方式不同、参数化 (parameterisation) 与简化方式不同**，输出的散布就给出了**模式的不确定性 (uncertainty)**；
- 未来气候的巨大范围既取决于**我们多快减排**，也取决于**哪一套模式情景和参数化是对的——这一点我们目前并不知道**。

### 3.8 全球能源消费图 (Global power consumption)

图的要点：横轴 **Year**，纵轴 **TW (Terawatt)**，按燃料种类分层显示功率消耗：**oil, coal, gas, nuclear, hydro**。老师说明：**这是相当老的图，例题数据来自 1985–87 年**；如果今天重画，还会加上**可再生能源 (renewables)**，并且我们希望看到 oil / coal / gas 开始略微下降。

这张图正是 practical 计算的出发点：**从全球能源消费量 → 燃料燃烧量 → $\mathrm{CO_2}$ 产量 → 大气 $\mathrm{CO_2}$ 浓度变化**。

---

## 四、课堂补充

以下内容只在 transcript 里出现，slides 上没有：

1. **"本周没有新数学"**：老师开场就说 "the good thing about this week is that there's not really any new maths"，本周用的都是已学内容，**重点是单位正确 + 会配平方程**——这两点在化学课里也会遇到，本周是把它们串起来。

2. **"物理你不必精确掌握，但要理解背后是什么"**：老师明确说 "you won't need to know the physics exactly to be able to do your question, but it's good that you understand what's behind it, and you will come across these ideas again certainly very much next year"。所以温室效应、气候模式这些是**背景理解**，不是考点。

3. **理想气体定律的"牵一发动全身"直觉**：$PV/T$ 恒定意味着三个量不能独立变动，改一个必然带动另一个——这个口头解释比公式本身更容易记住。

4. **hPa 与 mbar 的历史关系**：老师提到看**旧文献**会见到 millibar，两者数值等价，但 hPa 才是 SI。

5. **Dalton 定律的"房间里的彩色点"演示**（见 2.3）——这是理解分压最好的记忆锚点，slides 上只有静态图。

6. **分体积概念的实际用途**：老师说 "sometimes when we're working through problems, that's a useful concept to have"，并举了**天气预报中的水汽 (water vapour)** 为例——把水汽单独分离出来，用同样的定律去算，就能预报**雾、雨、雪、霭 (fog, rain, snow, mist)**。

7. **ppbv / pptv 的存在**：随着仪器精度提高，除了 ppmv 还会用到十亿分之一、万亿分之一体积比。

8. **配平的完整口头推演**（以 $\mathrm{C_3H_8}$ 为例）：右边 3 个 $\mathrm{CO_2}$ 已经用掉 3 个 $\mathrm{O_2}$（6 个 O 原子），4 个 $\mathrm{H_2O}$ 需要 4 个 O 原子 = 2 个 $\mathrm{O_2}$，$3+2=5$，所以左边是 $5\,\mathrm{O_2}$。**"我们把 4 个 O 原子重新排列成 2 个 $\mathrm{O_2}$ 分子"** 这句话是理解配平的关键。

9. **背景观测站与边界层 (boundary layer)** 的完整讲解（见 3.4）——slides 上完全没有。

10. **2023/2024 年最新 $\mathrm{CO_2}$ 数据**（418 → 422 ppm）是老师课上临时切出去展示的更新图表。

11. **$\mathrm{CO_2}$ 停留时间的具体数字**：100 年后剩 30%，1000 年后剩 13%。老师强调："所以我们不能指望**停开燃油车之后 $\mathrm{CO_2}$ 就突然掉下来**——峰值会降，但因为这个极长的滞后，浓度会持续叠加在之前的基础上。"

12. **2022 年欧洲干旱在 $\mathrm{CO_2}$ 记录中的印记**（见 3.4）。

13. **冰-反照率正反馈**（学生提问引出，见 3.6）。

14. **关于本周作业的最后一个思考题**：老师在课堂结尾抛出——"燃烧化石燃料同时产生了 $\mathrm{CO_2}$ 和水，**水汽也是很强的温室气体**，为什么我们不担心水汽？"有学生答对了："因为**水汽在大气中的停留时间很短**，放进去几天就出来了。暖空气能容纳更多水汽，但它不会像 $\mathrm{CO_2}$ 那样不断累积——$\mathrm{CO_2}$ 一千年后还在那里。"

15. **关于 summative test 的完整说明（practical transcript，非常实用）**：
    - **形式**：分**两部分**。
      - 第一部分是**机器批改 (marked by a machine)** 的题目。老师严厉提醒：**"题目要求两位小数你就写两位小数"**——"Machines don't have any emotions. They'll just go: this is three decimal places, not two, it's wrong." **认真读题、按要求作答本身就是训练的一部分。**
      - 第二部分是一道**未见过的问题 (an unseen problem)**，**不会**和课上做过的任何一题相同。但**是有引导的 (guided)**：会一步一步问，"第一步你要先算什么"（老师举例：给了角度和地面距离，先算钻孔的垂直深度），**最后一步可能需要把前面第 1、3、4 小问的答案综合起来**得到第 6 问的最终答案。
    - **难度**："It should seem easy after what you've been doing here." 老师说他们的策略是**在课堂上给难题 + 大量帮助，考试里出简单题**，而不是反过来。
    - **应试建议**：**别慌 (don't panic)、一步一步来、回去读题干的 preamble、找出需要的信息在哪里**。
    - **考场规则**：在**电脑机房 (computer cluster)** 进行；**包和手机、iPad 必须放在教室前面**；**可以带计算器，但必须是不能存文字、不能作图的基础型计算器**（能存文字或作图的会被没收）。老师说大部分题目其实纸笔就能做，计算器主要是查个 sin/cos。
    - **性质**：这是 **summative（终结性）考试**，**计入学年成绩和本单元成绩**。这与之前那些 **formative（形成性）** 测验不同——formative 不计分，只是让你看看自己学得怎么样。
    - **成绩**：提交后**不会立刻显示分数**（不像 formative 那样马上弹出 "94%"），因为 summative 需要人工核查（确认 Blackboard 没出岔子）。**成绩会在下一次 lecture 之前放出**，届时老师会到 Dr. Gilman 的课上开头做简短反馈并答疑。
    - 老师说下周还会**再讲一遍**这些考试信息。

---

## 五、Practical 要点

**材料**：`Problem solving 2 — Chemical reactions and equilibria`，§2.1 **Altering the Atmosphere by burning fossil fuels**。

**老师布置的范围（slides 明确）**：
- 先做 **supplementary material**（关于 ppmv / mixing ratio 的补充题）；
- 主问题只需做 **Problem 1 和 2**，**3、4 不必做**（但答案里都有，值得看）；
- **Homework（Blackboard 上的评估）**：① *Altering the Atmosphere*；② *Factorising / simplifying fractions*；
- **背景阅读**：Croft and Davison (2006) 中 'Simplifying algebraic expressions'、'Factorisation'、'Algebraic fractions' 三章，**或** *Foundation Maths Support Pack* 的 2.5–2.9 节。

### 5.1 核心问题

> **Problem 2.1**：在最近某一年中，地球上燃烧化石燃料从大气移除了多少 $\mathrm{O_2}$？燃烧过程产生了多少 $\mathrm{CO_2}$ 和 $\mathrm{H_2O}$？

**背景设定**：
- 三大类化石燃料（**天然气 natural gas、石油 petroleum、煤 coal**）的主要元素成分是**碳和氢**；
- 燃烧时大气中的氧与碳结合生成 $\mathrm{CO_2}$、与氢结合生成 $\mathrm{H_2O}$；
- **煤中还含有水（典型 10–15% by weight），燃烧时直接释放到大气**（这是本题的一个 subtlety，容易漏）；
- 三种燃料还含灰分 (ash)、硫 (sulfur)、痕量金属等，浓度更低，本题忽略。

### 5.2 完整例题：石油 (Petroleum, $\mathrm{CH_{1.5}}$)

**Step 1 — 写出带化学计量常数的反应式**

$$\mathrm{CH_{1.5}} + x\,\mathrm{O_2}\ \rightarrow\ y\,\mathrm{CO_2} + z\,\mathrm{H_2O} \tag{2.1}$$

**Step 2 — 逐元素配平**

- **碳 (C)**：$\mathrm{CH_{1.5}}$ 中 1 mol C 全部变成 $\mathrm{CO_2}$ 中的 C：
  $$1 = y \quad\Longrightarrow\quad y = 1 \tag{2.2}$$

- **氢 (H)**：$\mathrm{CH_{1.5}}$ 中 1.5 mol H；每 mol $\mathrm{H_2O}$ 含 2 mol H，共 $2z$：
  $$1.5 = 2z \quad\Longrightarrow\quad z = 0.75 \tag{2.4}$$

- **氧 (O)**：左边 $x$ mol $\mathrm{O_2}$ = $2x$ mol O；右边 $\mathrm{CO_2}$ 提供 $2y$ mol O，$\mathrm{H_2O}$ 提供 $z$ mol O：
  $$2x = 2y + z \tag{2.5}$$

**Step 3 — 联立求解（式 2.2、2.4、2.5）**

$$2x = 2(1) + 0.75 = 2.75 \quad\Longrightarrow\quad \boxed{x = 1.375}$$

所以：**每燃烧 1 mol $\mathrm{CH_{1.5}}$，消耗 1.375 mol $\mathrm{O_2}$，生成 1 mol $\mathrm{CO_2}$ 和 0.75 mol $\mathrm{H_2O}$。**

**Step 4 — 求一年内燃烧的 $\mathrm{CH_{1.5}}$ 摩尔数**

已知：
- 一年内石油燃烧释放的能量 $= 1.35\times 10^{20}\ \mathrm{J}$
- 石油热值 (heat content) $= 4.3\times 10^{10}\ \mathrm{J\,tonne^{-1}}$
- 石油按重量计 **98% 是 $\mathrm{CH_{1.5}}$**
- $\mathrm{CH_{1.5}}$ 的摩尔质量 $= 12 + 1.5 = 13.5\ \mathrm{g\,mol^{-1}}$

石油总质量：
$$m_{\text{oil}} = \frac{1.35\times 10^{20}\ \mathrm{J}}{4.3\times 10^{10}\ \mathrm{J\,tonne^{-1}}} = 3.14\times 10^{9}\ \mathrm{tonne}$$

其中 $\mathrm{CH_{1.5}}$ 的质量：
$$m_{\mathrm{CH_{1.5}}} = 3.14\times 10^{9} \times 0.98 = 3.08\times 10^{9}\ \mathrm{tonne} = 3.08\times 10^{15}\ \mathrm{g}$$

（换算：$1\ \mathrm{tonne} = 10^6\ \mathrm{g}$）

摩尔数：
$$n(\mathrm{CH_{1.5}}) = \frac{3.08\times 10^{15}\ \mathrm{g}}{13.5\ \mathrm{g\,mol^{-1}}} = \boxed{2.28\times 10^{14}\ \mathrm{mol}}$$

**Step 5 — 乘以化学计量常数**

$$n(\mathrm{O_2}) = x\cdot n(\mathrm{CH_{1.5}}) = 1.375 \times 2.28\times 10^{14} = 3.14\times 10^{14}\ \mathrm{mol}$$
$$n(\mathrm{CO_2}) = y\cdot n(\mathrm{CH_{1.5}}) = 1 \times 2.28\times 10^{14} = 2.28\times 10^{14}\ \mathrm{mol}$$
$$n(\mathrm{H_2O}) = z\cdot n(\mathrm{CH_{1.5}}) = 0.75 \times 2.28\times 10^{14} = 1.71\times 10^{14}\ \mathrm{mol}$$

### 5.3 Problem 1 — 补出天然气与煤的结果

#### (a) 天然气 (Natural gas)

**组成（按摩尔分数 mole fractions）**：$\mathrm{CH_4}$ 75%，$\mathrm{C_2H_6}$ 6%，$\mathrm{C_3H_8}$ 4%，$\mathrm{C_4H_{10}}$ 2%，$\mathrm{C_5H_{12}}$ 1%，**其余 12% 不可燃 (noncombustible)**。

**Step 1 — 分别配平各烷烃**（用 §2.6 的通式，$n=1..5$）

| 组分 | 摩尔分数 | $n(\mathrm{CO_2}) = n$ | $n(\mathrm{H_2O}) = n+1$ | $n(\mathrm{O_2}) = \frac{3n+1}{2}$ |
|---|---|---|---|---|
| $\mathrm{CH_4}$ | 0.75 | 1 | 2 | 2 |
| $\mathrm{C_2H_6}$ | 0.06 | 2 | 3 | 3.5 |
| $\mathrm{C_3H_8}$ | 0.04 | 3 | 4 | 5 |
| $\mathrm{C_4H_{10}}$ | 0.02 | 4 | 5 | 6.5 |
| $\mathrm{C_5H_{12}}$ | 0.01 | 5 | 6 | 8 |
| 不可燃 | 0.12 | 0 | 0 | 0 |

**Step 2 — 用摩尔分数加权平均**，得到"1 mol 天然气"的等效化学计量常数：

$$n(\mathrm{CO_2}) = 1\times0.75 + 2\times0.06 + 3\times0.04 + 4\times0.02 + 5\times0.01$$
$$= 0.75 + 0.12 + 0.12 + 0.08 + 0.05 = \boxed{1.12}$$

$$n(\mathrm{H_2O}) = 2\times0.75 + 3\times0.06 + 4\times0.04 + 5\times0.02 + 6\times0.01$$
$$= 1.50 + 0.18 + 0.16 + 0.10 + 0.06 = \boxed{2.00}$$

$$n(\mathrm{O_2}) = 2\times0.75 + 3.5\times0.06 + 5\times0.04 + 6.5\times0.02 + 8\times0.01$$
$$= 1.50 + 0.21 + 0.20 + 0.13 + 0.08 = \boxed{2.12}$$

> **注意**：不可燃的那 12% 贡献为 0，已经**自动包含在加权平均里**了（因为权重之和是 0.88 而不是 1），**不要再额外乘 0.88**。

**Step 3 — 求天然气的摩尔数**

已知：能量 $= 6.0\times 10^{19}\ \mathrm{J}$，天然气能量密度 $= 3.9\times 10^{7}\ \mathrm{J\,m^{-3}}$。

体积：
$$V = \frac{6.0\times 10^{19}\ \mathrm{J}}{3.9\times 10^{7}\ \mathrm{J\,m^{-3}}} = 1.54\times 10^{12}\ \mathrm{m^3}$$

转成升：
$$V = 1.54\times 10^{12}\ \mathrm{m^3} \times 1000\ \mathrm{L\,m^{-3}} = 1.54\times 10^{15}\ \mathrm{L}$$

**用 STP 摩尔体积 $22.4\ \mathrm{L\,mol^{-1}}$**（"1 mole of any gas occupies 22.4 litres (STP)"）：
$$n(\text{natural gas}) = \frac{1.54\times 10^{15}\ \mathrm{L}}{22.4\ \mathrm{L\,mol^{-1}}} = 6.86\times 10^{13}\ \mathrm{mol}$$

**Step 4 — 乘以加权化学计量常数**

$$n(\mathrm{CO_2}) = 1.12 \times 6.86\times 10^{13} = 7.7\times 10^{13} = 0.77\times 10^{14}\ \mathrm{mol}$$
$$n(\mathrm{H_2O}) = 2.00 \times 6.86\times 10^{13} = 1.37\times 10^{14}\ \mathrm{mol}$$
$$n(\mathrm{O_2}) = 2.12 \times 6.86\times 10^{13} = 1.45\times 10^{14}\ \mathrm{mol}$$

#### (b) 煤 (Coal)

**组成**：平均分子式 $\mathrm{CH_{0.8}}$，**75% 可燃**，另外 **13% 是 $\mathrm{H_2O}$，燃烧时直接释放**。

**Step 1 — 配平 $\mathrm{CH_{0.8}}$**

$$\mathrm{CH_{0.8}} + x\,\mathrm{O_2}\ \rightarrow\ y\,\mathrm{CO_2} + z\,\mathrm{H_2O}$$

- C：$y = 1$
- H：$0.8 = 2z \Rightarrow z = 0.4$
- O：$2x = 2(1) + 0.4 = 2.4 \Rightarrow x = 1.2$

**Step 2 — 乘以可燃比例 75%**（因为只有 75% 参与燃烧）：

$$n(\mathrm{CO_2}) = 1 \times 0.75 = 0.75 \qquad n(\mathrm{H_2O}) = 0.4 \times 0.75 = 0.30 \qquad n(\mathrm{O_2}) = 1.2 \times 0.75 = 0.90$$

（即：每 mol 煤 → 0.75 mol $\mathrm{CO_2}$、0.30 mol $\mathrm{H_2O}$、0.90 mol $\mathrm{O_2}$）

**Step 3 — 煤的质量与摩尔数**

已知：能量 $= 9.0\times 10^{19}\ \mathrm{J}$，煤热值 $= 2.93\times 10^{7}\ \mathrm{J\,kg^{-1}}$，$M(\mathrm{CH_{0.8}}) = 12 + 0.8 = 12.8\ \mathrm{g\,mol^{-1}}$。

$$m_{\text{coal}} = \frac{9.0\times 10^{19}\ \mathrm{J}}{2.93\times 10^{7}\ \mathrm{J\,kg^{-1}}} = 3.07\times 10^{12}\ \mathrm{kg}$$

$$n(\text{coal}) = \frac{3.07\times 10^{12}\ \mathrm{kg}\times 1000\ \mathrm{g\,kg^{-1}}}{12.8\ \mathrm{g\,mol^{-1}}} = \frac{3.07\times 10^{15}\ \mathrm{g}}{12.8\ \mathrm{g\,mol^{-1}}} = 2.4\times 10^{14}\ \mathrm{mol}$$

**Step 4 — 燃烧产物**

$$n(\mathrm{CO_2}) = 0.75 \times 2.4\times 10^{14} = 1.80\times 10^{14}\ \mathrm{mol}$$
$$n(\mathrm{O_2}) = 0.90 \times 2.4\times 10^{14} = 2.16\times 10^{14}\ \mathrm{mol}$$
$$n(\mathrm{H_2O})_{\text{combustion}} = 0.30 \times 2.4\times 10^{14} = 0.72\times 10^{14}\ \mathrm{mol}$$

**Step 5 — 加上煤中直接释放的水（易漏！）**

煤重量的 13% 是水：
$$m_{\mathrm{H_2O}} = 3.07\times 10^{12}\ \mathrm{kg} \times 1000\ \mathrm{g\,kg^{-1}} \times 0.13 = 4.0\times 10^{14}\ \mathrm{g}$$

$$n(\mathrm{H_2O})_{\text{liberated}} = \frac{4.0\times 10^{14}\ \mathrm{g}}{18\ \mathrm{g\,mol^{-1}}} = 2.21\times 10^{13}\ \mathrm{mol} = 0.221\times 10^{14}\ \mathrm{mol}$$

**煤的总水产量**：
$$n(\mathrm{H_2O})_{\text{total}} = 0.72\times 10^{14} + 0.22\times 10^{14} = 0.94\times 10^{14}\ \mathrm{mol}$$

#### (c) 结果汇总表（单位：$\times 10^{14}$ mol）

| | $n(\mathrm{CO_2})$ | $n(\mathrm{H_2O})$ | $n(\mathrm{O_2})$ |
|---|---|---|---|
| **Petroleum 石油** | 2.28 | 1.71 | 3.14 |
| **Natural gas 天然气** | 0.77 | 1.37 | 1.45 |
| **Coal 煤** | 1.80 | 0.94 | 2.16 |
| **Total 合计** | **4.85** | **4.02** | **6.76** |

（合计值与题目给定的 4.85 / 4.02 / 6.76 完全吻合，可用来**自检**。）

> **答案纸上的一处笔误提醒**：原文括号里写 "in addition to the $2.4\times 10^{14} \times 0.4$ from the combustion process itself"，用的是 **0.4**（没乘 75%）。但只有用 **0.3**（$= 0.4\times 0.75$）才能让 $\mathrm{H_2O}$ 合计对上 $4.02\times 10^{14}$：$1.71 + 1.37 + 0.72 + 0.22 = 4.02$ ✓。所以**应当乘 0.75**。

### 5.4 Problem 2 — 这些 $\mathrm{CO_2}$ 让大气浓度上升多少？

> 若一年内化石燃料燃烧释放的 $\mathrm{CO_2}$ 全部留在大气中，会使大气 $\mathrm{CO_2}$ 浓度增加百分之多少？
> （地球半径 $= 6.4\times 10^{6}\ \mathrm{m}$，大气厚度 $\sim 10\ \mathrm{km}$）

**Step 1 — 大气体积（一个薄球壳 thin shell）**

$$V = \frac{4}{3}\pi\left[(R + h)^3 - R^3\right] = \frac{4}{3}\pi\left[(6.4\times 10^{6} + 10\times 10^{3})^3 - (6.4\times 10^{6})^3\right]$$

计算：
- $(6.41\times 10^{6})^3 = 6.41^3 \times 10^{18} = 263.37\times 10^{18}$
- $(6.40\times 10^{6})^3 = 6.40^3 \times 10^{18} = 262.14\times 10^{18}$
- 差值 $= 1.231\times 10^{18}$
- $\times \frac{4}{3}\pi = 4.189$：

$$V \approx 5.15\times 10^{18}\ \mathrm{m^3}$$

**Step 2 — 大气总摩尔数**（同样用 $22.4\ \mathrm{L\,mol^{-1}}$）

$$N_{\text{air}} = \frac{5.15\times 10^{18}\ \mathrm{m^3} \times 1000\ \mathrm{L\,m^{-3}}}{22.4\ \mathrm{L\,mol^{-1}}} = \frac{5.15\times 10^{21}\ \mathrm{L}}{22.4\ \mathrm{L\,mol^{-1}}} \approx 2.3\times 10^{20}\ \mathrm{mol}$$

**Step 3 — 求混合比并转成 ppmv**

利用 §2.5 的恒等式（摩尔分数 = 体积混合比）：

$$\text{ppmv} = \frac{n(\mathrm{CO_2})}{N_{\text{air}}}\times 10^{6} = \frac{4.85\times 10^{14}}{2.3\times 10^{20}}\times 10^{6} \approx 2.1 \approx \boxed{2\ \mathrm{ppmv}}$$

**Step 4 — 对照现实（本题的"点睛之笔"）**

答案纸的注记：**"Note the atmospheric $\mathrm{CO_2}$ conc has increased about 2 ppm per year recently."** —— 这与老师在 lecture 上从 Mauna Loa 曲线**读梯度**得到的 $2\ \mathrm{ppm\ yr^{-1}}$ **完全一致**！这说明：
1. 我们这个粗糙的"信封背面"计算是可信的；
2. **观测到的 $\mathrm{CO_2}$ 增长几乎可以完全用化石燃料燃烧解释**。

（若想表达成"百分比"，则 $2.1\times 10^{-6}\times 100\% = 2.1\times 10^{-4}\%$ 的绝对占比增量；相对于当时约 350–400 ppm 的背景值则是约 0.5–0.6% 的相对增长。）

### 5.5 Problem 3 — 大气 $\mathrm{O_2}$ 被消耗了多少？（不要求做，但很有启发）

大气总摩尔数（上面算的）$= 2.3\times 10^{20}\ \mathrm{mol}$。

大气中 $\mathrm{O_2}$ 占 **21%**：
$$N(\mathrm{O_2}) = 2.3\times 10^{20} \times 0.21 = 4.83\times 10^{19}\ \mathrm{mol}$$

消耗百分比：
$$\frac{6.76\times 10^{14}}{4.83\times 10^{19}} \times 100\% \approx \boxed{0.0014\%}$$

**结论的启发性**：同样一次燃烧，对 $\mathrm{O_2}$ 的影响**微不足道（万分之十四）**，因为 $\mathrm{O_2}$ 的**库存 (stock) 极大**；但对 $\mathrm{CO_2}$ 影响**显著（每年 2 ppm，约 0.5% 相对增幅）**，因为 $\mathrm{CO_2}$ 的库存**很小**。**同样的通量 (flow)，作用在不同大小的库存上，效果天差地别**——这是本周最重要的定量直觉。

### 5.6 Problem 4 — 为什么不担心燃烧释放的水汽？

> 提示：只需用 **stock–flow–residence time** 的思路回答。

**标准答案**：因为**水会降水回到地表 (precipitates to Earth)，在大气中的停留时间 (residence time) 很短（天的量级）**，所以**不会像 $\mathrm{CO_2}$ 那样累积 (doesn't build up like $\mathrm{CO_2}$)**。

**展开理解**：
- 题目本身指出 —— **$\mathrm{H_2O}$ 其实是比 $\mathrm{CO_2}$ 更有效的红外吸收体**，而且本题算出的 $\mathrm{H_2O}$ 排放量（$4.02\times 10^{14}$ mol）与 $\mathrm{CO_2}$（$4.85\times 10^{14}$ mol）**量级相当**。所以直觉上似乎应该同样担心。
- 但**稳态浓度 $\approx$ 通量 $\times$ 停留时间**（$\text{stock} = \text{flow}\times\tau$）。$\tau_{\mathrm{H_2O}}\sim$ 天，$\tau_{\mathrm{CO_2}}\sim$ 百年到千年，相差 5 个数量级以上。所以**同样的排放通量，$\mathrm{CO_2}$ 造成的库存增量比水汽大得多**。
- 大气中水汽含量实际由**温度控制**（Clausius–Clapeyron：暖空气能容纳更多水汽）——所以人为排放的水汽只是被系统迅速"吸收掉"，水汽在气候里扮演的是**反馈 (feedback)** 角色，而不是**驱动 (forcing)** 角色。

---

## 六、易错点 / 重点难点

1. **温度必须用 Kelvin**。代入 $PV=NRT$ 前把 °C 加 273.15。用摄氏度算出来的答案一定是错的。

2. **压强必须用 Pa**。天气图上是 hPa（= mbar），代入公式前 **$\times 100$**。

3. **加权平均已经含了不可燃部分**：天然气加权时权重和是 0.88（含 12% 不可燃贡献 0），**不要再乘一次 0.88**；而煤的 75% 是**在配平之后单独乘上去的**，两者处理方式不同，容易混。

4. **煤中释放的水不要漏**：13% 重量的 $\mathrm{H_2O}$ 是**在燃烧产生的水之外**额外的，用 $M(\mathrm{H_2O})=18\ \mathrm{g\,mol^{-1}}$ 换算。漏掉这一项，$\mathrm{H_2O}$ 合计对不上 $4.02\times 10^{14}$。

5. **煤的 $\mathrm{H_2O}$ 化学计量常数是 $0.4\times 0.75 = 0.3$，不是 0.4**（答案纸此处有笔误，见 §5.3 提醒）。

6. **单位链条中最常见的三处失误**：
   - $\mathrm{tonne} \to \mathrm{g}$ 是 $\times 10^{6}$（不是 $10^3$）；
   - $\mathrm{kg}\to \mathrm{g}$ 是 $\times 10^{3}$；
   - $\mathrm{m^3}\to \mathrm{L}$ 是 $\times 10^{3}$（用 22.4 L/mol 前必须先换到升！）。

7. **摩尔质量不要用整数化学式**：$\mathrm{CH_{1.5}}$ 是 **13.5** g/mol，$\mathrm{CH_{0.8}}$ 是 **12.8** g/mol。这是平均组成，下标不是整数很正常。

8. **薄球壳体积不能用 $4\pi R^2 h$ 就完事**（虽然近似值接近），题目要求用**两个球体积相减**：$\frac{4}{3}\pi[(R+h)^3 - R^3]$。而且**相减时两个数非常接近**（263.37 vs 262.14），中间步骤**必须多保留有效数字**，否则会因舍入丢失全部精度。

9. **配平顺序**：先 C（定 $\mathrm{CO_2}$）→ 再 H（定 $\mathrm{H_2O}$）→ 最后 O（倒推 $\mathrm{O_2}$）。反着来会很痛苦。

10. **不要把"分压"和"分体积"混为一谈**：
    - 分压模型：**每种气体占满整个 $V$**，各自贡献 $p_i$，$\sum p_i = p$；
    - 分体积模型：**每种气体占据自己的 $V_i$**，共享同一个 $P$ 和 $T$，$\sum V_i = V$；
    - 两者数值上给出同一个混合比，但物理图像不同。分体积**在现实中不会真的发生**，只是思维工具。

11. **ppmv 是"体积/摩尔"比，不是"质量"比**。区分 ppmv 与 ppmm（by mass）。

12. **停留时间是理解"为什么担心 $\mathrm{CO_2}$ 不担心水汽"的唯一钥匙**——不要答"因为水汽少"（其实排放量相当），也不要答"因为水汽吸收弱"（其实水汽吸收更强）。

13. **考试格式**：**题目说几位小数就写几位小数**，机器批改不讲情面（practical transcript 老师重点强调）。

14. **不要死记具体题目**：考试第二部分是**未见过的题**，但有引导。训练的是**问题拆解的思维方式 (problem-setting mindset)**，不是背题。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| ideal gas law | 理想气体定律 | $PV = NR_{\text{gas}}T$，即 $PV/T$ 为常数 |
| universal gas constant | 通用气体常数 | $R_{\text{gas}} = 8.314\ \mathrm{J\,K^{-1}\,mol^{-1}}$ |
| mole | 摩尔 | 物质的量单位，$6.022\times10^{23}$ 个粒子（Week 1 内容） |
| Pascal (Pa) | 帕斯卡 | 压强的 SI 单位 |
| hectoPascal (hPa) | 百帕 | $=100\ \mathrm{Pa}$，大气压常用单位 |
| millibar (mbar) | 毫巴 | 与 hPa 数值等价的旧单位 |
| Kelvin (K) | 开尔文 | 绝对温标，零点在绝对零度，$T(\mathrm{K})=T(^\circ\mathrm{C})+273.15$ |
| absolute zero | 绝对零度 | 一切运动停止的温度，0 K $= -273.15\ ^\circ$C |
| Celsius / Fahrenheit | 摄氏度 / 华氏度 | 与 Kelvin 度距相同的温标 / 英美旧温标，科学中已少用 |
| partial pressure | 分压 | 混合气体中某一组分单独贡献的压强 $p_i$ |
| Dalton's law of partial pressures | 道尔顿分压定律 | 总压等于各组分分压之和：$p=\sum p_i$ |
| partial volume | 分体积 | 同压同温下某组分单独占据的体积 $V_i$，$\sum V_i = V$ |
| volumetric mixing ratio | 体积混合比 | $V_i/V$，等于摩尔分数，也等于分压比 |
| mole fraction | 摩尔分数 | $N_i/N$，某组分摩尔数占总摩尔数的比例 |
| ppmv (parts per million by volume) | 百万分体积比 | 混合比 $\times 10^6$，表达痕量气体浓度的常用单位 |
| ppbv / pptv | 十亿分 / 万亿分体积比 | 更小浓度的表达单位 |
| molar volume at STP | 标准状况摩尔体积 | $22.4\ \mathrm{L\,mol^{-1}}$，1 mol 任何气体在 STP 下的体积 |
| hydrocarbon | 碳氢化合物 | 只含碳和氢的化合物，如甲烷、丙烷 |
| alkane | 烷烃 | 通式 $\mathrm{C}_n\mathrm{H}_{2n+2}$ 的饱和碳氢化合物 |
| carbon chain length | 碳链长度 | 分子中碳原子数 $n$，决定生成的 $\mathrm{CO_2}$ 分子数 |
| combustion | 燃烧 | 燃料与氧反应生成 $\mathrm{CO_2}$ 和 $\mathrm{H_2O}$ 并放热 |
| balancing equations | 配平方程 | 使反应式两边各元素原子数相等 |
| stoichiometric constant | 化学计量常数 | 配平式中各物质前的系数 $x, y, z$ |
| fossil fuel | 化石燃料 | 天然气、石油、煤三大类 |
| natural gas / petroleum / coal | 天然气 / 石油 / 煤 | 本周分别按 $\mathrm{C}_n\mathrm{H}_{2n+2}$ 混合物 / $\mathrm{CH_{1.5}}$ / $\mathrm{CH_{0.8}}$ 建模 |
| heat content / calorific value | 热值 | 单位质量或体积燃料释放的能量，如 $4.3\times10^{10}\ \mathrm{J\,tonne^{-1}}$ |
| noncombustible | 不可燃成分 | 燃料中不参与燃烧的部分（天然气 12%，煤 25%） |
| greenhouse effect | 温室效应 | 温室气体吸收地表长波辐射并回辐射，使地表升温 |
| greenhouse gas | 温室气体 | 能吸收长波红外辐射的气体，如 $\mathrm{CO_2}$、$\mathrm{CH_4}$、$\mathrm{H_2O}$ |
| solar / infrared radiation | 太阳辐射 / 红外辐射 | 短波入射辐射 / 地表与大气发出的长波辐射 |
| electromagnetic spectrum | 电磁波谱 | 太阳（约 6000 K）辐射可见光，地球辐射长波红外 |
| reflection / albedo | 反射 / 反照率 | 表面把入射辐射反射掉的能力，冰高、深色岩石低 |
| positive feedback | 正反馈 | 变化放大自身的机制，如冰融化→反照率降低→更暖 |
| negative feedback | 负反馈 | 抑制变化的机制 |
| residence time | 停留时间 | 物质在库存中平均停留的时长，$\tau = \text{stock}/\text{flow}$ |
| stock / flow | 库存 / 通量 | 储量与单位时间的进出量，$\text{stock}=\text{flow}\times\tau$ |
| sink / source | 汇 / 源 | 吸收某物质的过程 / 释放某物质的过程 |
| growing season | 生长季 | 植被光合作用旺盛期，造成 $\mathrm{CO_2}$ 的年周期 |
| boundary layer | 边界层 | 大气最低约 0.5–1 km，人类活动影响集中区 |
| baseline / background measurement | 基线 / 背景观测 | 在偏远高山测充分混合后的全球代表性空气 |
| Mauna Loa Observatory | 冒纳罗亚观测站 | 夏威夷，自 1950 年代末连续观测 $\mathrm{CO_2}$ |
| gradient | 梯度 / 斜率 | 曲线的变化率，本周用来读 $\mathrm{CO_2}$ 的 ppm/yr |
| rate of change | 变化率 | $\mathrm{CO_2}$ 不仅在增加，其变化率本身也在增加 |
| climate model | 气候模式 | 数值模拟气候系统的计算机模型 |
| scenario | 情景 | 假定的未来排放路径，用于比较各模式输出 |
| parameterisation | 参数化 | 用简化公式表示模式无法直接分辨的过程 |
| uncertainty | 不确定性 | 各模式在同一情景下输出的散布范围 |
| summative / formative assessment | 终结性 / 形成性评估 | 计入成绩的考试 / 仅供自查、不计分的测验 |
| factorisation | 因式分解 | 本周 Blackboard 作业与阅读的代数主题 |
| algebraic fraction | 代数分式 | 同上，Croft & Davison 相关章节 |
