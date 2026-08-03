# Week 8 — 冰冻圈与气候模拟（Cryosphere & Climate Modelling）

> 材料来源：`Week8-Lecture.md`（56 张幻灯片）＋ `EART11100 - 17-Mar-transcript.md`（课堂全程转写，含课后 Kahoot 逐题讲解）。
> 授课教师：本学期负责大气/气候/海洋部分的老师（Week 9–10 由 Rodrigo 讲授并将离职，Week 11 回到本老师做全课程综合）。

---

## 一、本周主题

本周是 A Dynamic Planet 的第 8 周，主题分两大块，中间用一次上机练习（Build Your Own Earth，简称 BYOE）串起来：

1. **Cryosphere（冰冻圈）**——地球上所有以固态水形式存在的部分：它由哪些组分构成、南北半球为什么如此不对称、现在正在如何变化（NSIDC 实测数据）、以及在地质历史上出现过哪几次大冰期（含 Snowball Earth 的进入与退出机制）。
2. **Climate Modelling（气候模拟）**——气候模式到底是什么、它的理论根基（Bjerknes 1904）、Earth System Model 的耦合演化史、分辨率与算力的关系、**需要输入什么 / 能输出什么**、如何检验模式好坏，以及**如何把气候模式当作研究地质历史的工具**（两个真实科研案例）。
3. **贯穿全周的一条主线（也是本周最重要的 take-home message）**：尽管地球在地质时间尺度上大陆位置、温室气体浓度剧烈变化，**行星尺度的大气环流格局（Hadley 环流、ITCZ 湿带、副热带干带、极锋急流）却是高度稳定的常驻特征**。因此，只要知道某个地体在某个时代的 **paleolatitude（古纬度）**，就能大致推断它当时经历的气候类型 → 进而推断沉积环境、风化速率、植被。这就是把"气候"与"岩石循环/沉积记录"缝合起来的桥梁。

### 本周官方 ILOs（学习目标，逐条对应下文）
- Describe the composition and components of the cryosphere on Earth.（→ 二.1）
- Identify the periods of extensive glaciation in geological time and know their causes.（→ 二.4）
- Explain how the Earth enters and leaves a Snowball Earth episode.（→ 二.5、二.10）
- Discuss the reasons for **Arctic amplification**.（→ 二.3）
- Describe how climate models work, what the required inputs are, and what the simulated quantities are.（→ 二.6–二.8）
- Be able to discuss how to use climate models for research.（→ 二.9、二.10）
- Describe what the geological record tells us about present and future climate.（→ 二.11）

### 本周指定材料（考试相关，务必自己过一遍）
- **视频**：The Cryosphere: Rise and Fall of Ice on Earth；Snowball Earth；Arctic Climate Change；Climate Models and Climate Modeling；BYOE 视频 1–4（Introduction / Walkthrough 1 / Walkthrough 2 / Earth's Past Climates）。
- **必读**：
  - Geological Society of London **Scientific Statement: What the geological record tells us about our present and future climate**（Kahoot 第 6 题的图就出自这里）。
  - **Hoffman & Schrag (2000), "Snowball Earth", Scientific American**——重点是**如何进入**和**如何脱离**雪球地球。
- **延伸阅读**：CarbonBrief.org, *How Do Climate Models Work?*（Blackboard 有链接）。
- **Blackboard 上另有一份 BYOE 练习卷**，老师明确说 "That will be really useful for the final exam"。

---

## 二、核心概念

### 1. Cryosphere 的组成与组分

**定义**：地球系统中所有**冻结水（frozen water）**所在的部分。按赋存形式可分为：

| 组分 | 位置/性质 | 对气候的作用与时间尺度 |
|---|---|---|
| **Sea ice（海冰）** | 漂浮在海面上的冻结海水 | 反照率极高；**融化不改变海平面**（已排开等体积水）；季节性生消，响应时间**数月–数年**，是冰冻圈中**对气候变化最敏感、最脆弱**的部分 |
| **Ice sheets（冰盖）** | 大陆规模冰体：Antarctica（厚达数公里）、Greenland | 储存绝大部分陆地淡水；**融化直接抬升海平面**；响应时间 **10³–10⁵ 年**（惯性极大） |
| **Ice shelves（冰架）** | 冰盖延伸到海上的浮动部分 | 起"支撑（buttressing）"作用，阻挡冰流入海；一旦崩解，上游冰流加速 |
| **Glaciers（山岳冰川）** | 山地、高纬陆地 | 数量众多、体积小、响应快（年–十年级），是气候变化的敏感指示器；老师特别点名 **Andes（安第斯山）冰川**（南半球）与北半球高纬大量山岳冰川 |
| **Permafrost（多年冻土）** | **陆地**上常年冻结的土壤/岩石上层 | **北半球特有的大宗组分**；储存巨量有机碳，融化释放 CO₂/CH₄ → 强正反馈 |
| **Snow cover（积雪）** | 季节性陆面/海冰上积雪 | 反照率最高的自然表面之一；季节尺度，控制春季能量收支 |
| **Lake & river ice（湖冰、河冰）** | 内陆水体 | 局地热收支与生态 |

> **Kahoot Q1 的考点**：**云中的冰晶（ice crystals in clouds）不属于 cryosphere**——它虽然是冰，但属于**大气圈（atmosphere）**的一部分。这是最容易被"望文生义"骗到的题。

**关键机制——ice-albedo feedback（冰-反照率反馈）**：
冰雪的 albedo α ≈ 0.5–0.9，海水 α ≈ 0.06，裸土/森林 α ≈ 0.1–0.25。
降温 → 冰雪扩张 → α 上升 → 吸收太阳辐射减少 → 进一步降温（**正反馈**）。
反之升温 → 冰雪退缩 → α 下降 → 吸收更多 → 进一步升温。
这条反馈链是本周所有内容（Arctic amplification、Snowball Earth、Milankovitch 放大）的共同发动机，**必须能默写因果链**。

---

### 2. 南北半球冰冻圈的强烈不对称（老师用两张极地投影图开场）

这是本周第一个"为什么"，答案完全由**海陆分布（geography）**决定：

**南半球（Antarctic）**
- 中心是一块**被海洋环绕的大陆**，其上驮着数公里厚的 **Antarctic Ice Sheet**。
- 海冰围绕大陆呈**相当对称（rather symmetric）**的环状分布，可自由向外扩展。
- 由于底下有巨大冰盖"托底"（老师原话：sea ice 因为被 Antarctic ice sheet "supported"），加上南大洋环流与极地涡旋的隔离作用，**南极系统对气候变化的抵抗力比北极强得多**（"has been much more resistant to changes than the Arctic"）。
- 另有 **Andes 山脉冰川**。

**北半球（Arctic）**
- 中心是一片**被陆地环绕的海洋**（Arctic Ocean）→ 海冰扩展受陆地边界限制，**范围有限**。
- 永久冰盖只有 **Greenland** 一处，规模远小于南极。
- **关键差异**：因为环北冰洋是大陆，北半球拥有**广阔的 permafrost**。图上不同深浅的粉色代表：**continuous permafrost（全年冻结）** vs **discontinuous/seasonal（只在冷月冻结）**，覆盖北极圈周围陆地的很大一部分。
- 高纬有更多陆地和山脉 → **山岳冰川数量远多于南半球**。

**推论**：由于组分构成不同（北极以薄海冰＋冻土为主，南极以厚冰盖为主），**同样的全球增暖，北极的响应会更快、更剧烈**。这直接引出 Arctic amplification。

---

### 3. Arctic Amplification（北极放大效应）—— ILO 要求"discuss the reasons"

**现象**：北极地表增温速率约为全球平均的 **2–4 倍**。

**驱动机制（因果链，按重要性）**：
1. **Ice-albedo feedback（最主要）**：海冰/积雪退缩 → 暴露暗色海面（α 从 ~0.6 降到 ~0.06）→ 夏季海洋吸收大量短波辐射 → 秋冬把热量释放回大气 → 冰更晚冻结、更薄 → 次年更易融化。
2. **Lapse-rate feedback（递减率反馈）**：北极大气层结**稳定（stable, 常有逆温）**，增暖集中在**近地面薄层**，不像热带那样把热量输送到高空再高效向太空辐射掉 → 同样的能量输入造成更大的地表升温。
3. **Planck feedback 的纬度差异**：基础温度低的地方，按 σT⁴ 计算，要多辐射掉同样的能量需要**更大的温升**。
4. **海洋与大气的经向热输送增强**：低纬多余热量向极地输送（暖水入侵、Atlantification）。
5. **薄冰效应**：多年冰（multi-year ice）被一年冰（first-year ice）取代 → 更薄、更易碎、更易被风与洋流驱散。
6. **水汽与云反馈**：增暖 → 水汽增加（水汽本身是温室气体）→ 冬季低云增加下行长波辐射。
7. **Permafrost carbon feedback（更长时间尺度）**：冻土融化 → 释放 CO₂ 与 CH₄ → 额外温室强迫。

**证据尺度**：卫星时代（1979 至今）连续观测；北极海冰 9 月最小范围的下降趋势约每十年 −12~13%。

---

### 4. 冰冻圈的现状监测：NSIDC 数据的判读（课上重点演示）

**数据源**：**National Snow and Ice Data Center (NSIDC), University of Colorado**
- `nsidc.org/data/visualize-data`
- **Charctic Interactive Sea Ice Graph**：`nsidc.org/sea-ice-today/sea-ice-tools/charctic-interactive-sea-ice-graph`

**如何读这张图（考试可能给图让你判读）**：
- **横轴**：一年 12 个月（Jan → Dec）；**纵轴**：sea ice extent，单位 **百万平方公里（million km²）**。
- **灰/黑色粗线**：**1981–2010 三十年平均**（气候态基准）。
- 围绕它的**不同深浅灰色带**：该基准的变率范围（如 ±1、±2 个标准差）。
- 网页可**交互点选任意年份**的曲线，与长期平均对比。

**北极（Arctic）**
- 年内循环：冬季增长，**约在 3 月初达最大值**，之后阳光重返北极 → 开始融化；**9 月达最小值**。
- **历史最小纪录出现在 2012 年 9 月**（网页默认显示的就是这条线）。
- 老师现场指出：**2025 年的曲线在当时已经低于 2012 年同期**——注意他谨慎的措辞：这**并不等于 2025 一定会破纪录**，只是说明"通往破纪录年份的那种轨迹"在早期就已经偏低。

**南极（Antarctic）**
- 纵轴量程明显不同：一个坐标轴上到 **22**，另一个只到 **18**（南极海冰最大范围远大于北极，因为可以自由向外扩展；北极受陆地围限）。
- **季节变率的相对幅度更小、更稳定**（因为受背后 Antarctic Ice Sheet 支撑）。
- **历史最小纪录出现在 2023 年 2 月下旬**（南半球夏末）；**2025 年也已经逼近该纪录**。

**判读要点**：南北极最小值出现的**月份相差半年**（北极 9 月、南极 2 月底），因为季节相反——考试给图时先看横轴月份和最小值位置来判断是哪个半球。

---

### 5. 地质历史上的大冰期（ILO：identify periods + know their causes）

| 时期 | 年代 | 主要成因（驱动力） |
|---|---|---|
| **Huronian glaciation**（含 2.4 Ga Snowball Earth） | ~2.45–2.22 Ga | **Great Oxygenation Event (GOE)**：产氧光合作用 → O₂ 上升 → **氧化掉大气中的 CH₄**（强温室气体）→ 温室效应骤减；叠加 **faint young Sun**（太阳光度比今天低约 19%）；本周案例二模拟的正是这一次 |
| **Cryogenian Snowball Earths**（Sturtian & Marinoan） | ~717–660 Ma, ~650–635 Ma | Rodinia 超大陆裂解 → 低纬大量新鲜玄武岩暴露 → **硅酸盐风化加速 → CO₂ 消耗** → 失控的 ice-albedo feedback；Hoffman & Schrag (2000) 讲的就是它 |
| **Late Ordovician (Hirnantian) glaciation** | ~445 Ma | **陆生植物登陆**：植物吸收 CO₂ 并加速岩石风化 → 大气 CO₂ 下降 → 全球降温（**Kahoot Q2 的正确答案**） |
| **Late Palaeozoic Ice Age (Karoo)** | ~360–260 Ma（石炭–二叠） | 维管植物大爆发＋大规模埋藏有机碳（成煤）→ CO₂ 大幅下降；Gondwana 位于南极 |
| **Late Cenozoic / Quaternary glaciation** | 南极冰盖 ~34 Ma 起；北半球冰盖 ~2.7 Ma 起；**Pleistocene 冰期–间冰期旋回** | 构造抬升（喜马拉雅–青藏）→ 风化增强、CO₂ 下降；德雷克海峡打开 → 南极绕极流隔离南极；**Milankovitch cycles ＋ 内部反馈**共同调制冰期节拍；**LGM = 20 ka**（BYOE 中有此模拟） |

**Kahoot Q3 的关键区分（易错）**：
> Pleistocene glacials/interglacials 是由什么造成的？
> **答案不是"Milankovitch cycles"单独一项**，而是 **Milankovitch cycles ＋ 气候系统内部反馈（internal feedbacks）**。
> 老师原话：Milankovitch 只是 **starting point**——轨道参数振荡改变了太阳辐射的**分布（distribution）**，但**这点辐射变化本身不足以触发冰期**；必须有冰-反照率反馈、海洋环流变化（如 AMOC）、CO₂ 释放/吸收等**内部反馈把信号放大**，才能形成完整的冰期旋回。这题"坑倒了一大片人"。

---

### 6. Snowball Earth：如何进入、如何退出（ILO 明确要求）

#### 6.1 如何进入（entry）
1. 某种机制先把 CO₂/CH₄ 温室效应削弱（GOE 氧化甲烷、超大陆裂解导致低纬硅酸盐风化加剧消耗 CO₂、植物登陆吸碳……）。
2. 降温 → 极冰扩张。
3. **临界点（runaway threshold）**：一旦冰缘（ice caps 的边界）推进到**距赤道约 20–25° 纬度以内**，ice-albedo feedback 变成**失控正反馈**，行星在极短时间内完全封冻。老师课上原话：*"If the ice caps came within 20, 25 degrees of the equator, then the thing would almost completely shut up and be covered entirely in snow and ice."*
4. **时间尺度极短**：模拟显示，即使在这种非常粗糙的模式里，**collapse 在几十年（within decades / within 10–20 years）内完成**——从热带 −10 ~ −20 °C 直接"boom"掉到 **−60 °C**。
5. 封冻后的自持机制：全球 α 极高（~0.6+），且**海洋被封住 → 没有水汽源 → 全球降水几乎停止**（模拟中 precipitation 显著下降），大气极端干冷。

#### 6.2 如何退出（exit）—— Kahoot Q5，也是 Hoffman & Schrag 的核心
**驱动力：火山（volcanic outgassing）**
- 冰封状态下，**硅酸盐风化几乎停止**（岩石被冰盖住、没有液态水、没有降水）→ **碳循环的汇（sink）被关闭**。
- 但**火山脱气（源）不受冰的影响**，持续向大气注入 CO₂。
- 同时**海洋被冰封 → 海洋无法吸收 CO₂**（老师强调："you add carbon dioxide to the atmosphere **and you don't allow the oceans to take it up**"）。
- 于是 CO₂ 在大气中**积累数百万年**，累积到极高浓度（估计可达 ~0.1 bar 量级）→ 温室效应最终压倒高反照率 → 冰开始融化 → ice-albedo feedback **反向失控** → **超级温室（super-greenhouse）快速融冰**。
- **留下的可观察证据**：
  - **Cap carbonates（盖帽碳酸盐岩）**：直接覆盖在冰碛岩之上的碳酸盐层，反映融冰后极高 CO₂、极强风化、碱度暴增。
  - **Carbon isotope（δ¹³C）大幅波动**：冰期期间生产力崩溃 → δ¹³C 负偏。
  - **Banded Iron Formations 的短暂回归**：冰下缺氧海洋积累 Fe²⁺，融冰后氧化沉淀。
  - **低纬冰碛岩（low-latitude glacial deposits）＋ 古地磁证据**：证明冰确实到达了赤道附近。

> **Kahoot Q4（易错）**：Neoproterozoic Snowball Earth **紧随其后**发生的事包括：extensive carbonate deposition（cap carbonates）、carbon isotope ratio 的剧烈波动、**Ediacaran biota** 的出现。**唯独 "Cambrian explosion" 不是**——寒武纪大爆发发生在**晚得多**的时候（~541 Ma 之后），不是"immediately followed by"。

---

### 7. 气候模式的理论根基：Bjerknes (1904)

**Vilhelm Bjerknes 提出的天气预报两要件**（老师前面讲天气预报那一周用过同一张幻灯片，本周把它推广到整个地球系统）：

> 1. **A sufficiently accurate knowledge of the state of the atmosphere at the initial time.**（足够准确的**初始状态**）
> 2. **A sufficiently accurate knowledge of the laws according to which one state of the atmosphere develops from another.**（足够准确的**演化定律**）

**从"天气"到"气候"的推广**：Bjerknes 只讲了大气。要预测**整个地球系统（climate system）**，必须把这两条推广到全部圈层：
- **atmosphere（大气圈）** ← physics（主要）
- **hydrosphere（水圈/海洋）** ← physics ＋ chemistry（biogeochemical cycles）＋ biology（浮游生物）
- **cryosphere（冰冻圈）** ← 海冰、冰盖动力学
- **lithosphere（岩石圈）** ← 地形、地表性质、风化
- **biosphere（生物圈）** ← 陆地植被、海洋生物

老师的对比：**天气预报模式基本只连接"大气＋物理"**（大气中生物过程可忽略）；但一旦做**空气化学/空气质量模拟**就必须加化学；海洋一旦要算 **biogeochemical cycles**，就必须与生物圈耦合。**"things can get very complicated very quickly."**

**术语层级**：
- **GCM (General Circulation Model / Global Climate Model)**：大气＋海洋动力学为核心。
- **ESM (Earth System Model)**：GCM ＋ 碳循环、化学、动态植被、动态冰盖、生物地球化学 → 涵盖全部"圈层"。

---

### 8. 气候模式的发展史：算力 → 耦合度 → 分辨率

#### 8.1 耦合的历史（因果：算力增长驱动组件增加）
| 年代 | 模式能力 |
|---|---|
| **1960s** | 只有**最粗糙的 atmosphere-only 模式**；海洋模式在另一批人手里独立发展 |
| **1960s 末 – 1970s 初** | 首次**把海洋模式与大气模式耦合**起来 |
| **1970s** | 加入**陆面（land surface）**：大气从陆地接收热通量；降水落到陆地改变**土壤湿度（soil moisture）**；土壤湿度又反过来控制向大气的水汽通量 —— 这是一条完整的双向反馈链 |
| **之后至今** | 从 **static ice sheets（固定不变的冰盖）** → **dynamic ice sheets（动态冰盖）**：冰盖随降水量、温度变化，模式可算其 **mass balance（物质平衡）**；再加入海洋生物、**nitrogen cycle、sulfur cycle、carbon cycle** 等 biogeochemical cycles，从而能回答"地球系统如何响应人为或自然扰动" |

#### 8.2 算力
- 单位：**1 teraflop = 每秒 1 万亿次浮点运算（floating-point operation）**。气候模式的发展史基本就是超算能力的发展史。
- **运行速度的现实感（老师强调的实际约束）**：
  - 常规气候模式：**1 天 wall-clock time 只能算出 1 年或几年的模拟**。要做几百上千年的模拟 → 要跑好几个月。
  - **FOAM**：**1 天 wall-clock 可算约 450–500 模拟年**。→ 这就是为什么 BYOE 能提供上百个不同情景的模拟。

#### 8.3 分辨率（IPCC 各次评估报告的网格图，重要判读题素材）
| 报告 | 年份 | 典型水平网格间距 | 图上表现 |
|---|---|---|---|
| **FAR**（First Assessment Report） | 1990 | **~500 km** | 地图上**根本没有英国和爱尔兰**——完全无法分辨 |
| **SAR** | 1995 | **~250 km** | 开始出现几个格点代表 Ireland 与 Great Britain |
| **TAR** | 2001 | 更细 | — |
| **AR4** | 2007 | **~110 km** | 能看出英国、爱尔兰的形状，**地形（Alps 等）也从"两个格点"变成有结构的山系** |
| **AR5 / AR6** | 2014 / 2022 | 更高（幻灯片备注：**CMIP5 典型 125–300 km；CMIP6 典型 80–300 km**） | 更多过程被显式解析 |

**"Resolution matters" 的机制含义**：网格越粗，**地形、海岸线、岛屿等边界条件被"抹平"**；许多关键过程（对流、云、地形降水）小于格点尺度，必须靠 **parameterisation（参数化）** 近似 → 参数化方案是模式不确定性的主要来源。分辨率提高 → 更多过程从"参数化"变成"显式解析（explicitly resolved）"。

---

### 9. FOAM 与 Build Your Own Earth：模式的输入与输出（ILO 核心考点）

#### 9.1 FOAM = **Fast Ocean–Atmosphere Model** (v1.5)
BYOE 背后的模式，由多个模式**耦合（coupled）**而成：

```
        ┌──────────────────────┐
        │ 大气动力学 Atmospheric│
        │  dynamics: CAM2      │
        └──────────┬───────────┘
                   │
              ┌────┴─────┐
              │ COUPLER  │  ← 交换热通量、水汽通量、动量、辐射
              └────┬─────┘
         ┌─────────┴─────────┐
┌────────┴───────┐   ┌───────┴────────┐
│ 海洋动力学      │   │ 海冰 Sea ice   │
│ Ocean dynamics │   │  CISM2         │
│  POP3          │   │                │
└────────────────┘   └────────────────┘
```
- 技术世代：**1990 年代初的 GCM**（大气＋海洋）。老师承认"它 30 年前的东西了"，但强调**它在当年是相当不错的模式**。
- **海冰不是完全交互式的**：老师原话——它"takes the conditions in the atmosphere and the ocean and then determines kind of a sea ice configuration that goes with it"，即海冰配置由大气/海洋状态**诊断**得到，而非完全动态预报。
- **为什么叫 "Fast"**：① 粗分辨率；② 改造者对代码做了大量加速优化 → 约 **450–500 模拟年 / 天**。
- **BYOE 的工作方式（幕后）**：老师团队**预先跑好**了一大批模拟（涵盖真实与虚构的地球配置），把预报场画成图，**网站只是把这些预先算好的图"喂"给你**——你在网页上并不是实时跑模式。BYOE 约 **10 年前**为本课程的前身版本建成，合作者为 **Stuart Anderson 和 Sharon Gardner（EPS eLearning Team）**。

#### 9.2 **必背：FOAM 的 required inputs（输入）**
1. **Initial conditions（初始条件）**：t = 0 时刻的大气/海洋状态。
   - **关键洞察（考点）**：初始条件**很快就变得不重要**。因为模式大气/海洋会发展出**自身的内部动力学（internal dynamics）**。老师原话：*"That's the lesson from chaos."* → 这正是**天气预报（初值问题，initial-value problem）**与**气候模拟（边值问题，boundary-value problem）**的根本区别：天气预报的技巧受初值误差指数增长限制（约 2 周），而气候统计特征由边界条件与外强迫决定。
2. **Boundary conditions（边界条件）**：**geography（海陆分布）、terrain（地形高度）、vegetation state（植被状态）**。
   - 为什么植被算边界条件：**森林与沙漠的热通量和水汽通量完全不同**（反照率、粗糙度、蒸散发能力差异）。
3. **External forcings（外强迫）**：**incoming solar radiation / solar constant**；轨道参数（**rotation rate 自转速率、eccentricity 偏心率、obliquity 黄赤交角、date of perihelion 近日点日期**）。
4. **Settings in the model not predicted（模式中不预报、需人为指定的设置）**：最重要的是 **greenhouse gas concentrations（CO₂、CH₄ 等）**。
   - **原因（务必理解）**：FOAM **只有大气与海洋的动力学/热力学方程，没有化学方程**，所以温室气体浓度**不能被模式自己算出来**，必须由使用者设定；它们通过影响**辐射收支（radiation budget）**进而影响热传输与环流。

#### 9.3 **必背：FOAM 的 simulated outputs（输出）**
- **大气/海洋的动力与热力学量**：wind（风）、ocean currents（洋流）、temperature（温度）、pressure（气压）、humidity（湿度）、precipitation（降水）、snow（积雪深度）、salinity（盐度）、geopotential height（位势高度）、cloud fraction（云量）。
- **sea-ice distribution and thickness（海冰分布与厚度）**。

> **Kahoot Q8（易错，"huge changes there"——很多人改错了答案）**：
> "Inputs to climate models include all of the following **except**…" → 正确答案是 **sea ice（海冰分布）**，因为它是**模式的输出/预报量**，不是输入。
> **一句话记忆法**：**边界条件与外强迫是"你给的"，动力/热力状态量与海冰是"模式还你的"。**

#### 9.4 模式检验：BYOE 做得好不好？（Slide 20 那张图的判读）
- **横轴**：地质时间（注意有**多处刻度不连续（discontinuities）**，因为不同时段使用了不同的数据集）。
- **纵轴**：**global mean surface air temperature（全球平均地表气温）**。
- **数据来源的层次**：
  - 近现代 → **仪器观测记录（observational record）**；
  - 更早 → **ice cores（冰芯）**，可见明显的冰期–间冰期振荡；
  - 更早 → **ocean sediments（海洋沉积物）**，一直可用到约 **200 多 Ma**（再往前**洋壳/深海沉积基本已被俯冲消耗殆尽**）；
  - 更古老 → 只能靠模式重建，图中曲线来自 **Royer et al. (2004)**。
- **紫色圆点**：BYOE 各个地质时期模拟的全球平均地表温度。
- **检验结果（老师原话式总结）**：
  - **Miocene（~20 Ma）**："we're not so good at that"，**差约 3 °C**。
  - **K–T boundary（~65 Ma）**：**差约 5 °C**。
  - **更深的地质时间**：反而**很好**，与 Royer 曲线**相差在 1 °C 以内**。
- **为什么这个结果"令人欣慰"（老师的解释）**：3 亿年前的温室气体浓度**没有直接观测**，模式里填的数值全是 **educated guesses（有依据的猜测）**。"We just had to guess. It turned out we guessed pretty well." → 说明模式的**物理内核是可靠的**：给对了强迫，就能得出对的气候。

---

### 10. 研究案例一：用气候模式解释**互层沉积**（Interbedded sediments，Jurassic 170 Ma）

**这是"气候模式 × 沉积地质学"的典范，因果链要背熟。**

**人物**：本系同事 **Stephen Flint** 与其博士生 **Marcello Gugliotta**。
**野外地点**：**Argentina（阿根廷）**的一个露头，**几十米厚（tens of metres）**的重复旋回。

**① 野外观察到的岩石记录（evidence）**
| 阶段 | 岩性与沉积构造 | 水动力解释 |
|---|---|---|
| **Flooding stage（洪水期）** | **粗粒（coarse-grained）**；**erosional bases（侵蚀性底面）**；**mud clasts（泥砾）**；**ripples（波痕）** | 存在**单向、较强的水流（strong current）**，向海方向（seaward-directed） |
| **过渡（waning flow）** | 流速减弱 → 出现 ripples；进一步减弱 → **bidirectional ripples（双向波痕）** | 水流开始**振荡（oscillate）**，出现反向流（潮汐/回流） |
| **Inter-flood stage（洪水间期）** | **粒度明显变细**；**无侵蚀构造**，以**沉积作用（depositional）**为主 | 几乎没有净流；只有 estuary/delta 内部微弱的往复运动 |

这个序列**反复重复几十米**。地质学家的重建：这是一个 **estuary（河口湾）或 delta（三角洲）**环境。**但他们无法从岩石本身确定这个旋回的时间尺度**——这正是需要模式的地方。

**② 模式的介入**
- 时代 **170 Ma（Middle Jurassic）**，恰好与 BYOE 已有的 Jurassic 模拟**重合**。
- 古地理：这块南美区域**基本还在今天的经纬度位置附近**（"not a lot of motion, relatively speaking"）。当时 **Pangea 正在裂解**，可见越来越多的**内陆海（inland seas）**。
- 模式配置：从已发表的 **paleogeography（古地理重建）**数字化出海陆、地形网格作为边界条件；植被只用了**简单的纬向变化假设**（因为不是研究重点）。

**③ 模式输出的判读**
- **温度（surface temperature）**：比较 **February（南半球夏季）** 与 **August（南半球冬季）**。
  - 2 月：盆地月平均 **30–40 °C**（注意——**这是月平均**，单日峰值会高得多）。
  - 8 月：**10–20 °C**，且盆地上出现**很大的温度梯度（large gradient）**。
- **降水（precipitation）**：
  - **2 月（夏）**：盆地正好落在**副热带高压/反气旋（subtropical anticyclone）中心**下 → **降水极少 → 旱季**。
  - **8 月（冬）**：副热带高压带**北移并扩张**，**jet stream 向赤道方向漂移（drift equatorward）** → 盆地的**向极一侧**开始有更多降水进入 → **雨季**。
- **月降水柱状图**：从旱季 **~5 mm/月** 一路升到雨季 **~30 mm/月**——**很大的年循环**。

**④ 关键分析手段：Fourier decomposition（傅里叶分解）**
- 取模式在盆地对应格点上的**逐日降水时间序列（daily precipitation time series）**。
- 做 **Fourier analysis**，把时间序列分解为不同周期的分量，看**功率（power）**分布在哪些周期上。
- **结果**：绝大多数周期上功率都很低，**只有 12 个月的周期出现明显峰值，解释了 21% 的方差（21% of variance）**。
- **结论（这一步是全案例的钥匙）**：驱动这套沉积旋回的信号是**年周期（annual cycle）**，不是数十年/千年尺度的信号，也不是随机事件。

**⑤ 综合结论**
- **雨季（冬季，jet stream 南下带来风暴）→ 河流大流量 → flooding stage 粗粒、侵蚀底面**；
- **旱季（夏季，副热带高压控制）→ 河流枯竭 → inter-flood stage 细粒、双向波痕**。
- 这种气候被形容为 **"Mediterranean-like"（地中海式）**：**夏干冬湿**（老师也澄清：并非严格意义的地中海式，因为不是两边都有海，但降水季节性的机理相同——夏季副高控制、冬季急流带来锋面风暴）。
- **地质证据 ＋ 模式证据相互独立却相互印证** → 成果得以发表。**这就是"how to use climate models for research"的标准范式**：野外记录提出问题 → 模式提供独立的过程性解释 → 二者一致 → 结论稳健。

**要背的一般性结论**：**在 170 Ma 的地球上，ITCZ、副热带沙漠带、jet stream 全都存在，和今天一样。**

---

### 11. 研究案例二：2.4 Ga 的 Snowball Earth 敏感性实验（MFIS 学生项目）

**科学问题**：2.4 Ga 的超大陆上，**山脉的纬度位置**和**甲烷浓度**如何共同决定地球会不会进入 Snowball 状态？

**① 边界条件的不确定性**
- 超大陆 **Kenorland（2.7–2.4 Ga）**：多个古地理重建都显示它**大致跨骑赤道**、**南北方向延伸很大**、可能有山脉（图上深红色带，有的重建把 **cratons 之间的 sutures（缝合带）**画成南北向山脉）。
- 但这些重建**"just schematics"**——**根本没有可靠的山脉位置信息**。**这正是做敏感性实验（sensitivity experiment）的理由**：既然观测约束不了，就系统地扫一遍参数空间。

**② 模式设置（幻灯片备注中的精确数字，考点）**
- 轨道参数：与**现代相同**（自转速率、偏心率、黄赤交角、近日点日期），**唯一例外是一年设为 360 天**（简化）。
- **Solar constant = 1100 W m⁻²**，即 2.4 Ga 时的预测太阳光度，**比今天低 19%** → 这就是 **faint young Sun paradox（暗弱年轻太阳佯谬）**。
- **补偿机制**：温室气体浓度必须远高于今天。假设 **CO₂ 是主要贡献者**，**固定 CO₂ = 10,000 ppmv**（元古宙可能范围 **4,000–80,000 ppmv**，取了范围内且与他人研究一致的值）。
- **变量 1：CH₄ 浓度**，扫描范围 **1–100 ppmv**（幻灯片；课堂口述扫到了 **1, 20, 40 … 300 ppmv**）。此时正值 **Great Oxygenation Event 前后**——GOE 之前甲烷可以在缺氧大气中长期存在，浓度远高于今天。
- **变量 2：山脉纬度带**。超大陆在 Mercator 投影上被简化成一个**矩形**（全球大部分是海洋——2.4 Ga 陆壳面积本就很小）。山脉配置：
  - **赤道（0°）**、**±10°**、**±20°**、**±30°**、**±40°**、**±50°**
  - 外加 **FLAT**：完全没有山脉的平坦超大陆（对照组）。

**③ 结果：只有两种终态（bimodal outcome）**
每个模拟最后必然落入两类之一：
- **Snowball**：全球完全被冰雪覆盖；
- **Non-snowball**：只在两极维持 **ice caps**，低纬保持开阔海洋。
**临界判据**：**一旦极冰扩展到距赤道 20–25° 以内，系统立刻"关门"，全面封冻。**

**④ 参数矩阵的判读（Slide 35 那张图）**
- 横轴：**methane concentration (ppmv)**；纵轴/分行：**M0, M10, M20, M30, M40, M50, FLAT**（山脉纬度）。
- **不是简单线性关系**——不是"山越靠近热带就越容易 snowball"这么简单。
- **±30°（M30）是最"易发"的配置**：**即使在相当高的甲烷浓度下仍然形成 Snowball Earth**（老师用词：对 snowball 而言"insensitive"，即怎么加温室气体都拦不住）。
- **±40°、±50°**：**很难**形成 Snowball Earth。
- **±30° 与 ±40° 之间存在一个陡峭的转折（threshold）**——山脉位置只差 10°，结局却完全相反。

**⑤ 崩溃过程的时间演化（Slide 37，非常重要的图，务必会读）**
- **三张并排的图**：**Ts（地表气温）**、**precip（降水）**、**snow（地面积雪）**。
- **横轴**：**South Pole → North Pole 的纬度**（**zonally averaged，纬向平均**）。
- **每条曲线**：模拟中**每隔 10 年的 7 月平均值**；全模拟约 **400 年**；**颜色从红 → 紫 → 蓝表示时间推进**。
- **对比对象**：**M30（→ Snowball）** vs **M40（同样甲烷浓度 → 非 Snowball）**。
- **M30 的演化叙事**：
  1. 起初：赤道暖、极地冷的正常剖面。
  2. 随时间推移，整体缓慢降温，热带仍相对温暖。
  3. **突然，在某一个 10 年间隔内**，热带温度从 −10/−20 °C **"boom" 掉到 −60 °C**——完成封冻。
  4. **snow 图**：积雪边界从中纬度一路向低纬推进，最后合拢。
  5. **precip 图**：降水持续下降；**一旦海洋被完全封住，水汽源被切断，全球降水急剧减少**。
- **M40**：低纬海洋**始终保持开阔（open）**，整个 400 年模拟都没有崩溃。
- **核心结论**：**collapse happens quickly — within decades**（10–20 年）。这是一个典型的**临界点/tipping point 行为**：缓慢的强迫变化 → 长期几乎无变化 → 越过阈值后系统在极短时间内跳到另一个稳定态。

**⑥ 归因实验：是"地形"还是"反照率"？（漂亮的对照设计）**
- **初始假说（后被证伪）**：±40° 的山脉像屏障一样**挡住冷空气南下热带**，所以不 snowball。
- **判别实验设计**：把地形**完全压平（terrain is flattened）**，但在原来山脉所在纬度**保留冰的高反照率（replaced with the albedo of ice）**——即"假装那里有个冰盖，但没有高地形"。
  - 这样就把两个混杂因素**解耦**了：**高地形的动力学阻挡作用** vs **高反照率的辐射作用**。
- **结果**：去掉地形、只留高反照率后，**原本不 snowball 的低纬配置现在全都变成 Snowball Earth 了**。
- **结论**：**决定 Snowball Earth 的是低纬度的 albedo，而不是地形本身。**
  - 物理原因：**低纬度接收的太阳辐射通量最大**，同样面积的高反照率表面放在低纬，损失的能量远多于放在高纬 → 低纬的反照率对全球能量收支的杠杆最大。
- **幻灯片总结原文（Slide 42，可直接当答题模板）**：
  1. Simulations fixed carbon dioxide, but varied methane and mountain ranges.
  2. **Mountains at 30°N/S are most conducive to forming Snowball Earths, even at higher methane concentrations.**
  3. **Increasing albedo is more conducive than mountains at low latitudes to Snowball Earths.**

---

### 12. 大气环流在地质时间中的稳定性（本周最重要的综合结论）

**Slide 51 原文（可直接背）**：
> Although the Earth has undergone large changes over geologic time, the patterns of **moist tropics** and **dry subtropics** with **polar jet streams** are relatively consistent.
> Details about these features change and their locations may shift slightly on the planet, but the **planetary-scale circulation (Hadley cells, polar jet streams) is a consistent feature throughout geologic time.**

**为什么会这样（机制）**：这些环流特征由三个"几乎不变"的行星基本条件决定——
1. **球形地球 ＋ 太阳辐射的纬向分布**（赤道单位面积接收辐射远多于极地）→ 必然存在赤道上升、副热带下沉的 **Hadley cell**；
2. **自转（Coriolis force）**→ 必然产生纬向急流与西风带；
3. **海陆分布与温室气体只改变"细节和位置"，不改变"骨架"**。

**因此的实用推论（老师反复强调）**：
> **只要你知道某地在某个时代的 paleolatitude，就能大致推断其气候类型**（湿热赤道带 / 干旱副热带 / 中纬风暴带），**进而推断其 depositional environment（沉积环境）、风化强度、可能的岩性**。
> 这就是把 Rodrigo 讲的**岩石循环/沉积学**与本部分讲的**大气、气候、海洋**缝合起来的关键接口——也是这门课"holistic thinking"的核心诉求。

**同时要注意的边界（老师的重要限定，防止误读）**：
> "You really have to start changing the Earth **pretty radically**（比如把黄赤交角调到极端值）in order to see dramatically different climates on the **global** scale. Of course, that **doesn't undermine** any of the things that we're doing on the small scale — putting additional CO₂, methane into the atmosphere, changing the land surface, deforesting the Amazon. **These things will lead to local climate changes.** They're not going to upend the whole jet stream circulation."
>
> 即：**"行星尺度环流骨架很稳定" ≠ "人为气候变化不重要"**。人为强迫造成的是显著的**区域/局地**气候变化与全球平均温度变化，而不是把 Hadley 环流整个掀翻。**考试作答时务必把这两个尺度分开讲。**

---

## 三、公式与图表

本周以图为主、公式极少。以下逐图给出**判读方法**。

### 3.1 Bjerknes 框架（本周的"总纲图"）
```
    输入 INPUTS                模式核心 MODEL              输出 OUTPUTS
 ┌───────────────────┐    ┌─────────────────────┐    ┌──────────────────┐
 │ 1 初始条件         │    │                     │    │ 风 wind          │
 │   atmos/ocean @t=0│───▶│  Bjerknes 第 2 条：  │───▶│ 洋流 currents    │
 │ 2 边界条件         │    │  "the laws according │    │ 温度 temperature │
 │   geography/terrain│    │   to which one state │    │ 气压 pressure    │
 │   /vegetation      │    │   develops from      │    │ 湿度 humidity    │
 │ 3 外强迫           │    │   another"           │    │ 降水/积雪        │
 │   solar constant,  │    │  = 流体力学＋热力学   │    │ 海冰分布与厚度    │
 │   orbital params   │    │    方程组，在网格上   │    │ 盐度 salinity    │
 │ 4 不预报的设置      │    │    逐时间步积分       │    │                  │
 │   GHG 浓度         │    │                     │    │                  │
 └───────────────────┘    └─────────────────────┘    └──────────────────┘
```
**判读/答题要点**：被问"inputs vs outputs"时，先说 **"取决于模式类型（Will depend upon the type of climate model）"**，再给 FOAM 的具体清单。**GHG 是输入（因为 FOAM 无化学）**、**sea ice 是输出**——这两条是最常考的分界。

### 3.2 零维能量平衡模型（EBM）—— 理解 ice-albedo feedback 与 Snowball 的定量骨架
虽然课上没写这个公式，但它是解释本周所有反照率论证的最小定量工具：

$$\pi R^2 S_0 (1-\alpha) = 4\pi R^2 \sigma T_e^4 \quad\Longrightarrow\quad T_e = \left[\frac{S_0(1-\alpha)}{4\sigma}\right]^{1/4}$$

**符号**：
- $S_0$ = **solar constant（太阳常数）**，今日 ≈ **1361 W m⁻²**；**2.4 Ga 时 = 1100 W m⁻²（低 19%）**
- $\alpha$ = **planetary albedo（行星反照率）**，今日 ≈ 0.30；全球冰封时可达 **0.6 以上**
- $\sigma$ = Stefan–Boltzmann 常数 = 5.67×10⁻⁸ W m⁻² K⁻⁴
- $T_e$ = **effective radiating temperature（有效辐射温度）**；实际地表温度 = $T_e$ ＋ **温室增温（greenhouse warming）**
- 左边 $\pi R^2$ 是**截面积**（拦截阳光），右边 $4\pi R^2$ 是**球表面积**（向外辐射），二者之比给出公式中的 1/4

**用它讲三件事**：
1. **Faint young Sun paradox**：$S_0$ 低 19% → $T_e$ 低约 5%（≈13 K）→ 若无高浓度温室气体，早期地球本应完全冻结，但地质记录显示有液态水 → 因此必须假设 **CO₂ ≈ 10,000 ppmv ＋ CH₄ 数十 ppmv**。
2. **Ice-albedo feedback**：$T$↓ → 冰↑ → $\alpha$↑ → $T$↓，$dT/d\alpha < 0$ 的正反馈回路。
3. **多稳态（multiple equilibria）**：因为 $\alpha$ 本身是 $T$ 的函数，能量平衡方程可有**多个解** → 同一 $S_0$ 与 CO₂ 下，既可能是"有极冰的温暖态"，也可能是"全球冰封态"——这正是模拟结果只呈现**两种终态**的物理原因，也解释了为什么退出 Snowball 需要把 CO₂ 累积到极高才能"翻回来"（**hysteresis，滞后回线**）。

### 3.3 NSIDC Charctic 海冰范围图
- 横轴：月份；纵轴：sea ice extent（10⁶ km²）。
- 灰粗线 = **1981–2010 平均**；灰色带 = 变率范围；彩色线 = 选定年份。
- **判读顺序**：① 看最小值出现在 9 月（北极）还是 2 月末（南极）；② 看目标年份线相对灰线的位置（低于 = 偏少）；③ 注意纵轴量程（南极到 22，北极到 18）不可直接比较绝对值。
- 关键年份：**Arctic 纪录最小值 = 2012 年 9 月**；**Antarctic 纪录最小值 = 2023 年 2 月**。

### 3.4 IPCC 分辨率演进图
四联图（1990/1995/2001/2007），同一区域（西欧–不列颠群岛）在不同网格间距下的表现。
**判读**：**分辨率 → 能否解析海岸线与地形**。500 km 时英国"不存在"；110 km 时地形结构显现。用于回答"为什么需要更高分辨率"。

### 3.5 Royer et al. (2004) 全球平均温度曲线 ＋ BYOE 紫点
见二.9.4。**判读**：注意横轴**刻度不连续**（数据源切换：仪器 → 冰芯 → 海洋沉积 → 模式重建），紫点与黑线的**垂直距离 = 模式误差**（Miocene ~3 °C，K–T ~5 °C，深时 <1 °C）。

### 3.6 Jurassic 案例的四张图
1. **古地理输入图**：Pangea 裂解、内陆海扩展、南美盆地位置（与今日经纬度接近）。
2. **Feb vs Aug 地表温度图**：2 月 30–40 °C（南半球夏）；8 月 10–20 °C 且梯度大（南半球冬）。
3. **Feb vs Aug 降水图**：**标出 ITCZ、两侧 subtropical deserts、NH winter/summer 的位置漂移**。盆地 2 月在副高中心（干），8 月因急流赤道向移动而变湿。
4. **月降水柱状图**：5 mm → 30 mm 的年循环。
5. **Fourier 功率谱**：横轴周期，纵轴功率。**只有 12-month 处有峰，占 21% 方差** → 证明旋回是年际（annual）驱动。

### 3.7 Kenorland 敏感性矩阵（Slide 35）
- 行 = 山脉纬度配置（**M0 / M10 / M20 / M30 / M40 / M50 / FLAT**）；列 = **methane concentration (ppmv)**；格子颜色 = Snowball / Non-snowball。
- **判读要点**：找 **M30 那一行**——即使在图右侧（高甲烷）仍是 snowball；**M40/M50** 行几乎全是 non-snowball。**关系非线性、存在陡峭阈值。**

### 3.8 Snowball 崩溃的纬度–时间图（Slide 37）
- 三联图：**Ts / precip / snow**，横轴 **South Pole → North Pole**（zonal mean），每条线 = **每 10 年的 7 月平均**，红→紫→蓝 = 时间推进，总时长 ~400 年。
- **判读要点**：找 Ts 图上**曲线突然整体塌落**的那一步（相邻两条线之间的巨大跳跃）→ 那就是 tipping point，跨度只有 10–20 年；同时对照 snow 图的雪线合拢、precip 图的整体下降。

### 3.9 Obliquity 四联图（课堂练习产出，Slides 44–46）
- 四种黄赤交角：**0°、23.44°（今日）、60°、90°**；每格显示 **surface air temperature ＋ 250 hPa 急流风**（同一月份，如 12 月）。
- **图上必须标注的三条判读规则（Slide 46 原文）**：
  1. **Highest temperatures follow the Sun.**（最高温度跟着太阳直射点走）
  2. **Polar jet streams separate warm from cold air.**（急流是暖冷气团的分界）
  3. **Westerly winds when temperature decreases toward the pole; Easterly winds when temperature increases toward the pole.**（温度向极递减 → 西风；温度向极递增 → 东风）

### 3.10 "地球系统模式组件"耦合框图（Slide 13）
中心是 atmosphere，向外连接 hydrosphere、cryosphere、lithosphere、biosphere，边上标 **physics / chemistry / biology** 三类过程。
**判读**：说明"climate model = 多个圈层子模式 + coupler"，并解释每一对圈层之间交换什么（热通量、水汽通量、动量、碳）。

---

## 四、课堂补充（transcript 独有内容）

1. **BYOE 是"预计算图库"，不是实时模式**：老师明确说幕后流程是"我们有模式 → 跑了一大批模拟（both real and imagined）→ 生成预报场的图 → 网站把图 serve 给你"。所以你在网页上改不了参数、只能在**已有情景库**中选择。BYOE 约 **10 年前**为本课程前身建成。

2. **模式运行速度的直观感受**：常规气候模式"你坐在那儿等每一个模拟年跳过去"（1 天真实时间 ≈ 1 模拟年）；要做几百上千年 → 几个月。FOAM 靠 ① 粗分辨率 ② 代码优化，做到 **~450–500 模拟年/天**。这是"为什么用一个 30 年前的老模式"的**唯一且充分的理由**。

3. **"That's the lesson from chaos"**：老师专门强调初始条件会迅速失去重要性——模式大气/海洋会发展出自己的内部动力学。**这是理解"为什么气候可预测但天气不可预测"的关键一句话，很可能是简答题。**

4. **深时模拟反而更准，是因为"猜对了"**：老师坦率承认 3 亿年前的 GHG 浓度"没有直接观测，我们只能猜"——结果与 Royer 曲线吻合在 1 °C 内。这暗示：**模式误差主要来自输入的强迫，而非物理内核。**

5. **Jurassic 案例中被明确"忽略"的因素**：植被只用了简单的纬向假设，"we didn't really fuss too much with what is the vegetation... That really wasn't what we were after."——**这是模式研究中"抓主要矛盾"的示范**，也提醒你：任何模式结论都有其假设边界。

6. **Snowball 归因的科学方法论示范**：学生先提出"山脉挡住冷空气"的直觉假说 → 设计**压平地形但保留冰反照率**的对照实验 → **证伪了直觉假说**，得出"是 albedo 不是 terrain"。老师原话："it turns out that's not the case at all"。**这个实验设计本身就是可考的方法论要点。**

7. **黄赤交角练习的"反直觉"结论（老师说这正是他喜欢这个练习的原因）**：
   - 直觉预期：倾角越大 → 季节循环越强。**这没错，但只讲了一半。**
   - **真正的大变化是温度梯度反转**：在 **60°、90°** 倾角下，大部分月份**不是赤道正对太阳，而是某个极区正对（或背对）太阳** → **最高温度出现在高纬**，热带反而更冷（因为背对太阳）。
   - **后果：急流方向翻转**。低倾角（0°、23.44°）：暖热带 + 冷极地 → **两支强西风急流（westerly jets）**；高倾角（60°、90°）：冷热带 + 暖极地 → **箭头由东向西 → 东风急流（easterly jet）**。
   - 老师提到的门槛数字：**大约 57° 左右**，极地接收的净辐射开始超过热带，于是发生这个翻转。（他补充：详细原理在**二年级的大气科学课**里学。）
   - **教学寓意**：改变一个参数不会只带来"程度更极端"的同类变化，而会带来**结构性的、定性不同的**气候状态改变。

8. **BYOE 操作细节（做作业/复习时用得上）**：
   - 三大类：**Recent Earths（含 current day = 2015）/ Ancient Earths / Alien Earths**。
   - **改倾角路径**：Recent → 展开箭头 → **Axial tilt** → **Set obliquity** → **View climate model**。
   - 输出是**逐月动画**（monthly mean），可暂停；可切换投影（**本初子午线居中 / 国际日期变更线居中 / 极地立体投影**）。
   - **对比技巧**：右上角按钮**下载当前图片**；或用 **"Add Earth"** 同时显示两个地球（Earth 1 / Earth 2），用**中间的滑块（slider）左右拖动**做同图对比（很适合对比欧洲、非洲等特定区域）。
   - **改要素路径**：**Climate property** → 从 mean temperature 切换到 **precipitation / cloud fraction / pressure / geopotential height / mean winds**。
   - **看急流**：mean winds → 选气压层：**surface / 700 hPa (~3 km) / 500 hPa (~5.5 km) / 250 hPa (~10 km)**。**看急流用 250 hPa。**
   - **验证记忆**：在 23.44° 的 250 hPa 动画里可以看到——**冬半球的急流更强**（12/1/2 月南半球是冬季 → 南半球急流强；反之亦然）。
   - **Ancient Earths 可选时代**：**current day (2015)、LGM (20 ka)、K–T (65 Ma，有"撞击前"和"撞击后"两个版本——后者把大气 optical depth 调高模拟尘埃遮蔽)、Jurassic (170 Ma)、Carboniferous (300 Ma)、Cambrian (540 Ma)、一直到 Ediacaran**。
   - **LGM 小技巧**：进入 LGM 模拟后点 **land 按钮**可以调出**海冰浓度（sea ice concentration）**，看极区被海冰覆盖的范围。

9. **各古气候模拟的定性印象（老师逐个点评，很可能作为图片判读题的背景）**：
   - **LGM (20 ka)**：北半球极冷。
   - **K–T (65 Ma)**：与今天**差别不大，也许略暖**。
   - **Jurassic (170 Ma)**：热带**明显更暖**。
   - **Cambrian (540 Ma)**：非常暖（**CO₂ 浓度很高**）；大陆多为低纬的零散克拉通块体，另有大陆延伸到**南极附近**。
   - **Carboniferous (300 Ma)**：虽然我们把石炭纪想成"温暖潮湿的大煤沼期"，但**极区其实相当冷**；而且**副热带沙漠带依然存在**——**"wet Carboniferous" 是个容易误导的刻板印象**。
   - **共同点（重复三次的重点）**：所有模拟里**永远能看到 ITCZ、永远能看到副热带干带、南北半球永远各有一支急流**，与大陆配置和温室气体浓度无关。

10. **老师提出的 Thought-Provoking Question（Slide 53，明显是综合题/口试素材）**：
    > "Consider a hypothetical distribution of land, oceans, and mountains on the Earth. Map out the associated climate patterns (winds, temperature, precipitation), ocean circulation (currents, temperature, salinity), vegetation, sedimentary record, etc. Justify your map."
    - 老师说明用意：**让你把"岩石循环"的知识和"气候/圈层"的知识拼在一起**——"whatever you learned in geology is not decoupled from the stuff you learned in my bit on the atmosphere, climate, oceans"。并表示**欢迎学生把自己的答案拿去和他讨论**。
    - **推荐的作答骨架**：给定海陆分布 → ① 按纬度画出 Hadley 环流 / ITCZ / 副高 / 中纬急流 → ② 判断哪些海岸是**上升流（东岸型冷洋流→ 海岸沙漠）**，哪些是暖流西边界流 → ③ 地形的**雨影（rain shadow）**与**地形抬升降水** → ④ 大陆度（continentality）决定的温度年较差 → ⑤ 由此推出植被带 → ⑥ 由此推出**沉积环境**：赤道 = 湿润河流/煤系；副热带 = **蒸发岩、风成砂岩、红层**；中纬 = 风暴主导的陆架；高纬 = 冰川沉积（tillite、dropstone）→ ⑦ 每一步都写出理由（justify）。

11. **考试与课程安排**：
    - 老师提到 Blackboard 的 **"Assessment and Feedback"** 下已放出关于 **final exam** 的说明（考什么、怎么复习、结构如何、以及两位老师的出题哲学），并已邮件发出。
    - **Blackboard 上的 BYOE 练习卷"对期末考试非常有用"**。
    - 课程进度：**Week 9–10 由 Rodrigo 讲授**（之后他将离开学校）→ **复活节假期** → **Week 11 由本老师做全课程的综合（synthesis）**。

12. **AI Futures Day**：课程无关的宣传（可雇主交流 AI 在不同职业中的应用），与考试无关。

---

## 五、Practical 要点

**本周无独立 practical。** 但课堂中段有一个**必须掌握的 in-class 上机练习（Build Your Own Earth exercise）**，由两位助教 **Ananya 和 Tom** 现场协助，分两部分：

### 练习 A：Axial Tilt（黄赤交角）敏感性实验
**任务**：在 **buildyourownearth.com** 上，对 **0°、23.44°（现今）、60°、90°** 四种倾角，取**同一个月份**（老师用 12 月）分别输出：
- **surface air temperature（地表气温）**
- **jet-stream level winds（250 hPa 风场）**
并拼成一张 2×4 的对比图。

**必须得出的结论**（老师在课上帮大家填完了）：
| 倾角 | 温度梯度 | 急流 |
|---|---|---|
| **0°** | 暖热带、冷极地（正常） | **两支强西风急流（westerly）** |
| **23.44°** | 暖热带、冷极地（正常，有季节循环） | **两支西风急流，冬半球更强** |
| **60°** | **梯度反转**：高纬更暖、热带更冷 | **东风急流（easterly）** |
| **90°** | 梯度反转更极端 | **东风急流** |
**转折点：约 57°** 时极地净辐射开始超过热带。

### 练习 B：Ancient Earths 古气候巡览
**任务**：在 **Ancient Earths** 下选取若干时代（推荐 **LGM 20 ka、Carboniferous 300 Ma、K–T 65 Ma、Jurassic 170 Ma、Cambrian 540 Ma**），查看 **temperature**、**total precipitation**（老师最推荐，因为蓝=湿、红/橙=干，模式很直观）、以及 **250 hPa 急流**，并与 **current day (2015)** 用滑块对比。

**必须得出的结论**：无论大陆怎么摆、温室气体浓度差多少，**ITCZ、副热带干带、南北两支急流永远存在**；变的只是它们的**具体位置与强度**。

### 课后自学
Blackboard 上的 **BYOE 练习卷**（走一遍更多实验），老师明确说对期末考试很有用。

---

## 六、易错点 / 重点难点

**A. 冰冻圈相关**
1. ❌ 把**云中冰晶**算作 cryosphere。✅ 它属于 atmosphere。（Kahoot Q1）
2. ❌ 认为海冰融化会抬升海平面。✅ **海冰融化几乎不改变海平面**（已排开等体积水）；抬升海平面的是**陆基冰盖与冰川**。
3. ❌ 混淆南北极的最小值月份。✅ **北极最小在 9 月、最大在 3 月初**；**南极最小在 2 月末**。
4. ❌ 直接比较北极与南极海冰范围的绝对数值。✅ **两图纵轴量程不同（22 vs 18）**，且成因机制完全不同。
5. ❌ 认为"永久冻土 = 冰盖"。✅ **permafrost 是常年冻结的土壤/岩石**，主要分布在**北半球陆地**，且分为连续型与非连续/季节型。

**B. 冰期与 Snowball**
6. ❌ Pleistocene 冰期旋回 = Milankovitch cycles。✅ **Milankovitch ＋ 内部反馈**——轨道只是"起点"，单靠辐射分布变化**不足以**触发冰期。（Kahoot Q3，全班大量做错）
7. ❌ 把 **Cambrian explosion** 说成 Neoproterozoic Snowball 之后"紧接着"发生的事。✅ 紧接其后的是 **cap carbonates、δ¹³C 大幅波动、Ediacaran biota**；寒武纪大爆发晚得多。（Kahoot Q4）
8. ❌ 认为 Snowball 是靠"太阳变亮"或"轨道变化"结束的。✅ **靠火山持续释放 CO₂，而风化汇与海洋汇同时被冰关闭 → CO₂ 累积到极高 → 温室效应压倒反照率**。（Kahoot Q5）
9. ❌ 认为 Snowball 的进入是缓慢渐变的。✅ **是 tipping point 行为——前期缓慢降温，越过临界（冰缘到达 20–25° 纬度）后在 10–20 年内全面崩溃。**
10. ❌ 认为"山脉离赤道越近就越容易 Snowball"（简单线性）。✅ **关系非线性**：**±30° 最易 snowball，±40°/±50° 很难**；且真正起作用的是 **albedo 而非 terrain**。
11. ❌ 把 Ordovician 降温归因于火山或轨道。✅ **陆生植物登陆 → 吸收 CO₂ ＋ 加速风化 → CO₂ 下降 → 降温**。（Kahoot Q2，也是大量做错的一题）

**C. 气候模式**
12. ❌❌ **最高频错误**：把 **sea ice distribution** 当成模式**输入**。✅ 它是**输出/预报量**。（Kahoot Q8，老师说"huge changes there"）
13. ❌ 把 **greenhouse gas concentration** 当成模式输出。✅ 在 FOAM 这类**只有大气-海洋动力学、没有化学模块**的模式里，**GHG 必须由使用者指定**（属于"settings in model not predicted"）。**注意：在更高级的 ESM 里，如果耦合了碳循环，CO₂ 就可以成为预报量——所以回答时要先说"取决于模式类型"。**
14. ❌ 认为初始条件对气候模拟至关重要。✅ **气候模拟是边值问题**，初始条件很快被内部动力学"遗忘"（chaos）。**天气预报**才是初值问题。
15. ❌ 混淆 boundary conditions 与 external forcings。✅ **boundary conditions = 地球自身的下垫面属性**（海陆分布、地形、植被）；**external forcings = 来自地球系统之外的驱动**（太阳常数、轨道参数）。
16. ❌ 认为高分辨率只是"图更好看"。✅ 分辨率决定**哪些过程能被显式解析、哪些只能参数化**；500 km 时英国根本不存在。
17. ❌ 认为老模式（1990s 的 FOAM）没有价值。✅ 它换来的是**速度（~500 模拟年/天）**，使得**大规模敏感性实验（扫参数空间）**成为可能——这类研究恰恰需要"多"而不是"精"。

**D. 环流与判图**
18. ❌ 把急流画在**温度最高**或**温度最低**的地方。✅ **急流位于地表温度梯度最陡（tightest temperature gradient）处**，且**风速随高度增大**（thermal wind 关系）。（Kahoot Q9）
19. ❌ 在**热带中部**找急流。✅ **热带没有温度梯度 → 没有急流**——老师说选热带是"the worst answer you could give"。
20. ❌ 忘记判断**是哪个半球的冬季**。✅ **冬半球的急流更强**。Kahoot Q9 是"June（6 月）的 Permian"→ **南半球是冬季 → 最强急流在南半球中纬**（答案 D，而不是北半球的 B）。
21. ❌ 认为高倾角只是"季节更极端"。✅ 还会导致**温度梯度反转 → 急流从西风变东风**（约 57° 为门槛）。
22. ❌ 用"行星环流很稳定"推出"人为气候变化不重要"。✅ **两个尺度必须分开**：全球环流骨架稳定；但 CO₂/CH₄ 增加、土地利用变化（如亚马逊毁林）会造成**显著的局地与区域气候变化**及全球平均温升。

**E. 其他**
23. ❌ Kahoot Q6：认为上一次大气 CO₂ 达到当今水平（**~420 ppm**）是在更早的时代。✅ **Pliocene（上新世）**——出自 Geological Society 声明中的那张图，"the Pliocene is closest to where we're headed"。
24. ❌ Kahoot Q10：Silurian（3000 ppm CO₂）情景下把 CO₂ 再翻倍。✅ 结果是**热带暖空气区域的扩张（expansion of the warm air in the tropics）**——更多加热 → 暖区向极扩展。
25. ❌ Kahoot Q7：把某个由**内部演化压力（internal evolutionary pressures）决定的生物性状**当成气候代用指标。✅ 判断 climate proxy 的准则是：**该指标是否由物理/化学过程直接记录环境条件**（如冰芯气泡、δ¹⁸O、树轮、孢粉、珊瑚生长带、洞穴石笋、沉积岩性）；若某性状主要由**演化/生态竞争压力**驱动，就不是可靠的气候代用指标。
26. ❌ 认为 Carboniferous 全球都湿热。✅ **极区仍相当冷，副热带依旧有沙漠带。**

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Cryosphere | 冰冻圈 | 地球系统中所有以固态水存在的部分（海冰、冰盖、冰川、冻土、积雪、湖河冰）。 |
| Sea ice | 海冰 | 冻结的海水，漂浮于海面；融化不抬升海平面；对气候最敏感的冰冻圈组分。 |
| Ice sheet | 冰盖 | 大陆规模冰体（南极、格陵兰），响应时间 10³–10⁵ 年，融化直接抬升海平面。 |
| Ice shelf | 冰架 | 冰盖延伸至海面的浮动部分，对上游冰流起支撑（buttressing）作用。 |
| Permafrost | 多年冻土 | 常年冻结的土壤/岩石层，北半球特有大宗组分，含巨量有机碳。 |
| Continuous / discontinuous permafrost | 连续／非连续冻土 | 全年冻结 vs 仅冷月冻结，地图上以不同深浅表示。 |
| Snow cover | 积雪 | 季节性覆盖层，反照率最高的自然表面之一。 |
| Albedo | 反照率 | 表面反射太阳短波辐射的比例；冰雪 0.5–0.9，海水约 0.06。 |
| Ice-albedo feedback | 冰-反照率反馈 | 降温→冰增→反照率升→更冷的正反馈（反之亦然）。 |
| Arctic amplification | 北极放大效应 | 北极增温速率达全球平均 2–4 倍，主因是冰-反照率与递减率反馈。 |
| Lapse-rate feedback | 递减率反馈 | 北极层结稳定，增暖集中于近地面薄层，放大地表升温。 |
| NSIDC | 美国国家冰雪数据中心 | 科罗拉多大学机构，提供 Charctic 等海冰实时监测数据。 |
| Sea ice extent | 海冰范围 | 海冰浓度超过某阈值（通常 15%）的海域总面积，单位 10⁶ km²。 |
| Snowball Earth | 雪球地球 | 全球（含赤道）被冰雪覆盖的极端气候状态，2.4 Ga 与新元古代各出现过。 |
| Huronian glaciation | 休伦冰期 | ~2.45–2.22 Ga 的大冰期，与大氧化事件导致甲烷被氧化有关。 |
| Great Oxygenation Event (GOE) | 大氧化事件 | ~2.4 Ga 大气 O₂ 上升，氧化掉温室气体 CH₄，触发降温。 |
| Faint young Sun paradox | 暗弱年轻太阳佯谬 | 早期太阳光度低（2.4 Ga 时 1100 W m⁻²，低 19%）却有液态水，需高浓度温室气体解释。 |
| Solar constant | 太阳常数 | 地球轨道处垂直入射的太阳辐照度，今日 ≈1361 W m⁻²。 |
| Kenorland | 凯诺兰（超大陆） | 2.7–2.4 Ga 的超大陆，大致跨骑赤道、南北延伸大，本周模拟的边界条件。 |
| Craton | 克拉通 | 古老稳定的大陆核心块体。 |
| Suture | 缝合带 | 两块陆块碰撞拼合的界线，常发育山脉。 |
| Cap carbonate | 盖帽碳酸盐岩 | 直接覆盖在冰碛岩之上的碳酸盐层，是雪球地球终结的标志性证据。 |
| Cryogenian | 成冰纪 | 新元古代含 Sturtian 与 Marinoan 两次雪球事件的时期。 |
| Ediacaran biota | 埃迪卡拉生物群 | 紧随新元古代雪球之后出现的软躯体多细胞生物群。 |
| Milankovitch cycles | 米兰科维奇旋回 | 偏心率、黄赤交角、岁差引起的太阳辐射分布周期变化，冰期旋回的"起搏器"。 |
| Internal feedbacks | 内部反馈 | 冰反照率、海洋环流、碳循环等系统内机制，把轨道信号放大成完整冰期。 |
| Last Glacial Maximum (LGM) | 末次盛冰期 | 约 20 ka 前冰盖体积最大的时期，BYOE 有对应模拟。 |
| Climate proxy | 气候代用指标 | 间接记录过去气候的物理/化学/生物证据（冰芯、海洋沉积、树轮、孢粉等）。 |
| Ice core | 冰芯 | 保存气泡与同位素记录的冰柱，可重建数十万年气候。 |
| Ocean sediments | 海洋沉积物 | 气候代用记录载体，可用至约 200 Ma（更老洋壳已被俯冲）。 |
| Royer et al. (2004) | 罗耶等（2004） | 提供深时全球平均温度重建曲线的论文，用于检验 BYOE。 |
| GCM (General/Global Circulation Model) | 大气环流模式／全球气候模式 | 以大气＋海洋动力学为核心的数值气候模式。 |
| ESM (Earth System Model) | 地球系统模式 | GCM 加碳循环、化学、动态植被与冰盖，涵盖全部圈层。 |
| Coupled model | 耦合模式 | 多个圈层子模式通过 coupler 交换通量而联合运行的模式。 |
| Coupler | 耦合器 | 负责在子模式之间传递热、水汽、动量等通量的模块。 |
| FOAM (Fast Ocean–Atmosphere Model) | 快速海气模式 | BYOE 背后的 1990s 世代耦合模式，约 450–500 模拟年/天。 |
| CAM2 / POP3 / CISM2 | — | FOAM 中的大气动力学／海洋动力学／海冰子模式。 |
| Build Your Own Earth (BYOE) | 自建地球 | 本课程的交互式古气候模拟浏览网站，提供预计算的 FOAM 模拟图库。 |
| Initial conditions | 初始条件 | t=0 时的大气/海洋状态；在气候模拟中会被内部动力学迅速"遗忘"。 |
| Boundary conditions | 边界条件 | 海陆分布、地形、植被等下垫面属性。 |
| External forcing | 外强迫 | 来自系统之外的驱动，如太阳常数与轨道参数。 |
| Orbital parameters | 轨道参数 | 自转速率、偏心率、黄赤交角、近日点日期。 |
| Obliquity / axial tilt | 黄赤交角／地轴倾角 | 自转轴与轨道面法线夹角，今日 23.44°，控制季节强度与温度梯度方向。 |
| Eccentricity | 偏心率 | 地球公转轨道偏离正圆的程度。 |
| Parameterisation | 参数化 | 用经验关系近似表达次网格尺度过程（对流、云等）。 |
| Grid spacing / resolution | 网格间距／分辨率 | 模式格点间的距离；IPCC FAR ~500 km → AR4 ~110 km；CMIP6 典型 80–300 km。 |
| IPCC AR (FAR/SAR/TAR/AR4–AR6) | IPCC 评估报告 | 1990/1995/2001/2007/2014/2022 的国际气候评估。 |
| CMIP5 / CMIP6 | 耦合模式比较计划第 5/6 阶段 | 国际统一实验设计的模式集合，支撑 IPCC 报告。 |
| Teraflop | 万亿次浮点运算 | 每秒 10¹² 次浮点运算，衡量超算能力。 |
| Wall-clock time | 实际墙钟时间 | 真实世界耗时，与"模拟年"相对。 |
| Boundary-value vs initial-value problem | 边值问题 vs 初值问题 | 气候模拟属前者（由强迫决定统计特征），天气预报属后者（受混沌限制）。 |
| Chaos | 混沌 | 对初值敏感依赖，导致天气可预报期有限（约两周）。 |
| Hadley cell | 哈得来环流 | 赤道上升、副热带下沉的低纬经向环流，造就 ITCZ 与副热带沙漠。 |
| ITCZ (Intertropical Convergence Zone) | 热带辐合带 | 赤道附近信风辐合、强对流降水带；随季节南北移动。 |
| Subtropical desert / anticyclone | 副热带沙漠／反气旋 | Hadley 环流下沉支控制区，干燥少雨，蒸发岩与风成沙丘的产地。 |
| Jet stream | 急流 | 对流层上部（~250 hPa）的强风带，位于地表温度梯度最陡处；冬半球更强。 |
| Westerly / easterly winds | 西风／东风 | 温度向极递减时为西风，向极递增时为东风（高倾角情形）。 |
| Thermal wind | 热成风 | 风的垂直切变与水平温度梯度的关系，解释急流为何在高空最强。 |
| Zonal mean | 纬向平均 | 沿同一纬圈取平均，用于绘制"极到极"的剖面图。 |
| Fourier decomposition / analysis | 傅里叶分解／分析 | 把时间序列拆解为不同周期分量并量化各自的功率与方差贡献。 |
| Variance explained | 解释方差 | 某周期分量占总变率的比例（本例 12 个月周期占 21%）。 |
| Interbedded sediments | 互层沉积 | 粗细粒层交替叠置的沉积序列，本例记录洪水/间洪水旋回。 |
| Flooding stage / inter-flood stage | 洪水期／洪水间期 | 强单向流粗粒＋侵蚀底面 vs 弱流细粒＋无侵蚀。 |
| Erosional base | 侵蚀底面 | 沉积单元底部的冲刷面，指示强水流。 |
| Mud clast | 泥砾 | 被水流撕起并搬运的泥质碎块，指示高能侵蚀。 |
| Bidirectional ripples | 双向波痕 | 指示往复/振荡水流（潮汐或回流）的沉积构造。 |
| Estuary / delta | 河口湾／三角洲 | 河流入海的过渡沉积环境，兼具河流与潮汐/波浪作用。 |
| Palaeogeography | 古地理 | 特定地质时期的海陆、地形分布重建，作为模式的边界条件。 |
| Palaeolatitude | 古纬度 | 某地体在过去所处的纬度，是推断其古气候的首要依据。 |
| Pangea | 泛大陆 | 晚古生代–中生代超大陆，侏罗纪时正在裂解并形成内陆海。 |
| Tipping point | 临界点 | 系统越过阈值后迅速跳到另一稳定态（如雪球崩溃仅需数十年）。 |
| Multiple equilibria / hysteresis | 多稳态／滞后 | 同一强迫下可存在多个气候平衡态，进出路径不重合。 |
| Mass balance (ice sheet) | 冰盖物质平衡 | 降雪积累与消融/冰流损失之差，决定冰盖增减。 |
| Biogeochemical cycle | 生物地球化学循环 | 碳、氮、硫等元素在生物圈-水圈-大气圈间的循环。 |
| Pliocene | 上新世 | 上一次大气 CO₂ 接近现今 ~420 ppm 的时期。 |
| Hirnantian glaciation | 赫南特冰期 | 奥陶纪末冰期，成因是陆生植物登陆导致 CO₂ 下降。 |
| Optical depth | 光学厚度 | 大气对辐射的衰减程度；K–T 撞击后模拟中调高以代表尘埃遮蔽。 |
| Geopotential height | 位势高度 | 等压面的高度，反映大气质量分布与环流形态。 |
