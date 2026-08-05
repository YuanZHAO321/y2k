# EART21202 Global Climate Change — Week 03

> 授课日期：**19 Feb**（幻灯片周历标注 "Week 3 – Radiation and the Greenhouse Effect (19th Feb)"）
> 主讲：**Dr Thomas Bannan**（Thomas.Bannan@Manchester.ac.uk）
> 材料：讲义 deck（`Week 4_Student Upload_2026`）+ 答案 deck（`Week 4_Student Answers_2026`）+ 课堂录音转写（`EART21202 - 19-Feb-transcript`）
> ⚠️ 两份 deck 的**文件名写作 "Week 4"，但幻灯片首页正文自称 "Week 3"**，转写日期链（05-Feb → 12-Feb → 19-Feb）也指向第 3 周。**本笔记以正文为准，即 Week 03**。转写里讲师亲口解释了这个命名混乱的成因（见第四节），并已登记进末尾勘误表。

---

## 一、本周主题

### 1.1 一句话概括

本周把前两周积累的**现象**（气候正在以史无前例的速率变暖）换成了**机制**：用**电磁辐射（electromagnetic radiation）**的基本物理，加上两条**辐射定律（radiation laws）**——**斯特藩–玻尔兹曼定律（Stefan–Boltzmann Law）**和**维恩定律（Wien's Law）**——先算出地球在"没有大气"的假设下应该有的**黑体平衡温度（blackbody equilibrium temperature）**，发现是 **255 K（−18 °C）**；再拿它跟实测的全球平均地表温度 **288 K（+15 °C）**对比，得到 **33 K 的缺口**；最后用**温室效应（greenhouse effect）**这一套"大气对短波近乎透明、对长波强烈吸收"的不对称性，把这 33 K 解释掉。

讲师在转写开头把这条逻辑说得很直白：

> "So this week is designed to enable you to understand why we are seeing that very rapid uptick in observed temperatures since 1850. ... What we haven't dived into any detail yet is why those greenhouse gases act as they do and why they have the impact that they have in terms of radiative forcing."

也就是说：**第 1 周告诉你"变了"，第 2 周告诉你"自然原因能变多少"，第 3 周（本周）第一次告诉你"温室气体到底凭什么能让它变"。**

### 1.2 在全课中的位置与前后衔接

讲义 Slide 2 给出的完整周历如下（原文照录，含原有的括号未闭合）：

| 周次 | 主题 | 日期 |
|---|---|---|
| Week 1 | Introduction to climate change and its impacts | 5th Feb |
| Week 2 | Natural climate variability | 12th Feb |
| **Week 3** | **Radiation and the Greenhouse Effect** | **19th Feb** |
| Week 4 | Anthropogenic Impacts | 26th Feb |
| Week 5 | The Evidence Base for Climate Change | 5th March |
| Week 6 | Mid Unit Test | 10th March |
| Week 7 | Climate Models | 19th March |
| Week 8 | Climate change adaptation | 26th March |
| Week 9 | Effects of Climate Change: Case Studies | 23rd April |
| Week 10 | Climate change mitigation | 30th April |
| Week 11 | Revision Lecture | 7th May |

**向后看（衔接 Week 2）**：讲师用整整一屏回顾了上周的四大自然变率要素——太阳变率（solar variability）、轨道变化（Milankovitch cycles）、火山活动（volcanic activity）、海洋环流（ocean circulation）。他特意点出，其中**太阳变率**这一条本周会"dive into in much more detail"，因为本周的能量收支计算就是从太阳常数出发的；而**火山**这一条则埋下本周后半段气溶胶讨论的引信：

> "Typically people think about volcanoes as a emission source of greenhouse gases but actually we're aware that volcanoes emit a huge amount of sulphur dioxide, we know that that sulphur dioxide undergoes oxidation and we know that those oxidation products convert into sulphate aerosol rapidly which are bright white aerosols and have an important impact on our radiative balance."

**向前看（衔接 Week 4）**：Slide 24 在讲反照率时就明写"Land-use change driven by human activity modifies surface reflectivity ... – Week 4"；Slide 49 把下周预告写成"Anthropogenic Impacts"，具体包括：地球能量收支如何运作、什么能扰动它、CO₂ 与甲烷之外的人类影响、这些"其他"人为影响背后的物理机制。本周建立的**能量收支框架**就是下周讲**辐射强迫（radiative forcing）**清单的地基。

**与期中测验的关系**：Week 6（10 March）是 Mid Unit Test，占总成绩 30%。讲师在讲评 workshop 时明确说：

> "please do work through that because that's going to be important to understand, particularly the mid-semester test."

这是本周唯一一处**明示的考试提示**，指向的正是黑体平衡温度的计算。

### 1.3 本周的官方 ILOs（Slide 8 原文对照）

课程给的 Intended Learning Outcomes：

1. **Apply blackbody equilibrium and radiation laws** to calculate the equilibrium temperature of Earth and other planets.
   （应用黑体平衡与辐射定律，计算地球及其他行星的平衡温度。）
2. **Explain the physical basis of the greenhouse effect**, including:
   - why the radiation spectra of the Sun and the Earth differ（为什么太阳与地球的辐射谱不同）
   - why greenhouse gases interact differently with incoming solar radiation and outgoing terrestrial radiation（为什么温室气体对入射太阳辐射和出射地面辐射的作用不同）
3. Use this understanding to **explain why Earth's surface temperature is higher than its blackbody equilibrium temperature**.
4. **Evaluate the implications of rising greenhouse gas concentrations.**
5. **Explain why increasing greenhouse gases are expected to drive further warming.**

📎 背景补充：这五条与 unit spec 里的 **ILO 1**（"To understand the concept of Black body equilibrium temperature, the Stefan-Boltzman Law and how to calculate the equilibrium temperature for the Earth & other planets. To explain why the equilibrium temperatures for the planets differ."）几乎逐字对应。也就是说，**本周是全课 11 周里唯一一周直接承担 ILO 1 的**，而 ILO 1 在 unit spec 里被标记为 Developed = Y、Assessed = Y，同时出现在期中 Test 和期末 Exam 的考核 ILO 列表里。换句话说，**本周的计算题是必考内容，不是"讲一讲"的内容。**

### 1.4 本周课堂结构（Slide 3）

- **Part 1**：Lecture and Workshops（80 分钟）——讲课中途插入 Workshop 1
- **Part 2**：Q/A（10 分钟）
- **Part 3**：Full workshop（30 分钟）——即 deck 后半段的 Q1–Q9

讲师在转写里对应说明：

> "today we'll follow the same sort of instructions we ran last week where we'll have a lecture followed by a workshop, half way through the lecture, today there will be a workshop which will test your understanding of the sort of first elements that we talked about, obviously opportunities for questions and then follow on workshop"

### 1.5 学完本周你应该能回答的问题

1. 为什么"任何温度高于 0 K 的物体都在辐射"？它辐射的是单一波长还是一整段谱？
2. 频率、波长、能量三者的关系是什么？写出两条公式。
3. 什么叫黑体？我们凭什么说太阳和地球"近似"是黑体？证据是什么？
4. 斯特藩–玻尔兹曼定律和维恩定律各自说了什么？符号、单位、常数值分别是多少？
5. 为什么太阳发短波、地球发长波？这两条谱之间为什么"几乎不重叠"，分界在哪？
6. 地球能量收支的"进"和"出"分别怎么写？为什么进的面积是 πr² 而出的面积是 4πr²？
7. 反照率是什么？地球的 ~0.3 由哪几部分组成？
8. 完整推导并算出地球的黑体平衡温度 Te。为什么行星半径可以约掉？
9. 用同样的公式算火星和金星。为什么火星算出来跟实测差 2 K，金星却差 500 K 以上？
10. 大气窗口（atmospheric window）在哪两个波段？为什么人眼的敏感波段刚好落在其中之一？
11. 分子为什么只在特定波长吸收？红外吸收和紫外吸收的**微观机制**有什么本质区别？
12. 辐射强迫的定义是什么？为什么温室气体增加对应**正**辐射强迫？
13. CO₂、CH₄、N₂O 三者的主要来源、大气寿命、减排的空气质量共同效益分别是什么？
14. 减少气溶胶为什么"对健康是好事，对气候可能是坏事"？

---

## 二、核心概念

本节按讲义推进顺序逐个展开。每个概念都给「是什么 / 为什么 / 怎么用 / 边界条件」。

### 2.1 温室效应的定性图景（Slide 9 与 Slide 37，首尾呼应）

**是什么。** 讲义在开头（Slide 9）和结尾（Slide 37）用了**同一张图**，这是刻意的教学设计：先给你一张"你大概见过但说不清"的图，讲完物理后再回来，让你能把图上每一个箭头都解释清楚。图的文字标注（deck 提取出的散碎文本）拼起来是这样一套流程：

- **Solar radiation（太阳辐射）** — 标注为 "high temp' source"、"Short Waves"，来自 **SPACE**。
- **Most solar radiation passes straight through the atmosphere and is absorbed to warm the surface**（大部分太阳辐射直接穿过大气，被地表吸收并加热地表）。
- **Some solar radiation is reflected by the earth's surface, clouds and the atmosphere**（部分太阳辐射被地表、云和大气反射）。
- **Some solar radiation is absorbed by clouds and other gases**（部分被云和其他气体吸收）。
- **Terrestrial radiation（地面辐射）** — 标注为 "low temperature source"、"Long Waves"，从 **EARTH** 向上。
- **Some of the infrared radiation is absorbed and re-emitted by the greenhouse gases**（部分红外辐射被温室气体吸收并再发射）。
- **This warms the surface and the atmosphere**（这加热了地表和大气）。

**为什么重要。** 这张图把整周的两条主线都摆在了一起：**（a）短波进、长波出**；**（b）大气对这两者的处理方式完全不同**。讲师在转写里对这张图逐条口述了一遍，并预告："Some of this lecture will be to describe **why** the sun emits short waves and **why** the earth emits longwave radiation."

**怎么用。** 考试若问"用文字描述温室效应"，Slide 39 给了一个可以直接背诵的六步版本（见 §2.16）。

**边界条件。** 这张图是**定性**的，不含任何数值，也没有画出"大气自身向上发射的长波"的完整平衡。它不能用来做定量的能量收支闭合（那是下周 Week 4 的能量收支图的活）。

📎 背景补充：这张图常被批评为"温室"这个类比本身不准确——真正的玻璃温室主要靠**抑制对流（suppressing convection）**保温，而大气温室效应靠的是**红外不透明度（infrared opacity）**。这个类比上的偏差本周材料没有提，但值得知道，以免在解释题里写成"大气像玻璃一样把热挡住"。

### 2.2 电磁辐射的基本描述：波长、频率、光子

**是什么。** Slide 10 是一张示意图（deck 中该页为图片，OCR 只捕捉到 "WAVELENGTHS / Longer Wavelength (lower frequency) / Shorter Wavelength (higher frequency)"）。讲师在转写里把这张图讲得比幻灯片详细得多：

> "A particle of electromagnetic radiation is known as a **photon** and these waves are characterized by both their frequency and their wavelength. The longer the wavelength, as you can see here, the lower the frequency."
> "The wavelength is essentially the **distance between the two crests or troughs** and the frequency can be expressed in **hertz**, which refers to the **number of wavelengths that pass any one point per second**."

他还给了一个具体的数字例子（讲义上没有）：

> "This is an example of radiation with **two hertz** where there's two troughs within a one second period. We **halve the wavelength and double the frequency** to give a radiation packet of **four hertz** here."

**为什么。** 这是后面所有内容的语言基础。没有"波长 ↔ 频率 ↔ 能量"这条链，就没法理解"为什么温室气体挑波长吸收"。

**怎么用。** 记住三个等价的说法：**波长长 = 频率低 = 能量低**；**波长短 = 频率高 = 能量高**。

**边界条件。** 讲师强调："electromagnetic radiation **all travels at the same speed**. So it all travels at the speed of light" —— 这在真空（以及近似地，在大气中）成立。速度是常数，但**能量不是**（Slide 11 原话："Speed of radiation is a constant, but energy is not!"）。

📎 背景补充：严格说光在介质中的传播速度是 c/n（n 为折射率），空气的 n ≈ 1.0003，所以本课把它当作 c 完全够用。另外"波粒二象性"意味着同一份电磁辐射既可以用波（λ, f）描述，也可以用粒子（photon）描述，本周两种语言会交替使用——算能量收支时用波/通量语言，讲分子吸收时用光子语言。

### 2.3 两条基础公式：fλ = c 与 E = hf（Slide 11）

Slide 11 原文（含 OCR 把 λ 显示成 l 的问题）：

- `fl = c`：f = frequency（频率），l = wavelength（波长），c = speed of light（光速）
- `E = hf`：E = Energy（能量），h = Planck's constant（"physical constant, that relates a photon's energy to its frequency"），f = frequency

**是什么。** 第一条是**波的运动学关系**（速度 = 频率 × 波长）；第二条是**普朗克–爱因斯坦关系**，把波动量（频率）翻译成粒子量（单个光子的能量）。

**为什么。** 两条合起来给出 **E = hc/λ**：**能量与波长成反比**。这是"紫外线晒伤人、红外线只让人觉得暖"的根本原因，也是后面"高能辐射能推动电子跃迁、红外只能激发振动转动"的根本原因。

**怎么用。** 讲师的总结句：

> "The speed of these wavelengths is a constant, but the energy within them is not. The energy is **directly related to its frequency**."

**边界条件。** E = hf 给的是**单个光子**的能量，不是一束辐射的总能量。总能量还要乘光子数。斯特藩–玻尔兹曼定律给的才是**单位面积、单位时间的总能量**。这两个"能量"不要混。

📎 背景补充（材料未给数值，此处为我补充）：h = 6.626 × 10⁻³⁴ J s，c = 3.00 × 10⁸ m s⁻¹。代入几个本周会碰到的波长：
- 可见光 λ = 500 nm → f = c/λ = 6.0 × 10¹⁴ Hz → E = 3.98 × 10⁻¹⁹ J ≈ **2.48 eV**
- 地球红外峰值 λ = 10 μm → f = 3.0 × 10¹³ Hz → E = 1.99 × 10⁻²⁰ J ≈ **0.124 eV**
- CO₂ 强吸收带 λ = 15 μm → f = 2.0 × 10¹³ Hz → E = 1.33 × 10⁻²⁰ J ≈ **0.083 eV**

可见光光子的能量是 10 μm 红外光子的**约 20 倍**。这个量级差正是 §2.13 里"红外能量不足以改变电子能级"的定量依据。

### 2.4 电磁波谱（Slide 12）

**是什么。** Slide 12 原文三句：

- "The electromagnetic spectrum represents the complete range of electromagnetic radiation."
- "**Any object warmer than 0 K will emit radiation.**"
- "The Sun radiates over the entire electromagnetic spectrum but as we shall see **not all the energy is radiated equally at all wavelengths**."

讲师把这张图的两端说清楚了（讲义上没有具体数值）：

> "which ranges anywhere from **radio waves, which have a wavelength of thousands of meters**, all the way down to **gamma radiation**, which have a wavelength around the size of atomic [nuclei]. In the middle there, we have **visible, at around 500 nanometers**, which ranges from the lower frequency in the **red** to the higher frequency in the **violet**."

**为什么重要。** 第三句是本周的关键伏笔：**一个物体不是只发一个波长，而是发一整条谱；但这条谱有形状、有峰。**讲师原话：

> "An object doesn't emit, generally, a single wave band. It **will emit over this entire electromagnetic spectrum**."

**边界条件。** "任何高于 0 K 的物体都辐射"里的 0 K 是**绝对零度**，不是 0 °C。这是本周最容易被写错的单位陷阱之一。

### 2.5 什么在发射辐射，两条定律的定性版（Slide 13）

Slide 13 把两条定律先用**大白话**给出，公式留到后面：

- "All objects with a temperature greater than 0 K emit some type of radiation (energy)"
- "This is viewed as an **energy spectrum**"
- **Radiation laws:**
  - "**Warmer objects emit more intensely than cold objects.** (Stefan-Boltzmann Law)"
  - "**Warmer objects emit a higher proportion of their energy at short wavelengths.** (Wien's Law)"

讲师对这两句的评价很有意思，值得记住：

> "The first radiation law is the Stefan-Boltzmann law, which says that warmer objects emit more intensely than cold ones, and **hopefully that's relatively obvious**. ... **What's perhaps less obvious is that warmer objects emit a higher proportion of their energy at short wavelengths.**"

**这句话是本周的认知重心**：第一条是直觉（火越旺越烫），第二条是反直觉（火越旺颜色越偏蓝/白）——而**恰恰是第二条造出了温室效应**。因为如果太阳和地球发的是同一波段的辐射，大气就没法"对进来的透明、对出去的不透明"，温室效应就不存在了。

### 2.6 黑体与黑体辐射（Slide 14）

**是什么。** Slide 14 定义：

- "The Sun and Earth behave **approximately** like a black body"
- "A **Black body**: absorbs **all** radiation falling on it... ...and **reemits it as a function of its surface temperature**"
- "Governed by two radiation laws: Stefan-Boltzmann law, Wien's law"

**为什么可以这样近似？** 讲义没给理由，**转写给了**，而且给的是一个"实测 vs 理论"的对照论证，这是本周最值得记住的方法论片段：

> "if we show, look at this on the figure here where we have essentially the energy intensity on the y-axis and the wavelength on the x-axis, **the full black line is the measured solar electromagnetic spectrum, and the dotted line is the theoretical black body behaviour of something with the surface temperature the same as the sun**. Because the measured electromagnetic spectrum and the theoretical black body with the same surface temperature as the sun **overlap with one another**, you can assume that that holds true in this case."

**怎么用。** 这是典型的"模型验证"逻辑：我们不是**假定**太阳是黑体，而是**先假定、再拿实测谱去比对、发现重合、于是接受这个假定**。答题时如果被问"为什么可以把地球当黑体"，正确答案不是"因为老师这么说"，而是"因为其发射谱与同温度的理论黑体谱吻合良好"。

**边界条件。** 注意 "approximately" 这个词。真实物体有**发射率（emissivity）** ε < 1。

📎 背景补充：完整的斯特藩–玻尔兹曼定律应写成 I = εσT⁴，ε 为发射率（黑体 ε = 1）。地表在红外波段的 ε 通常在 0.90–0.98 之间，很接近 1，所以本课把它省略掉是合理的近似。本周所有计算都默认 ε = 1。另外，"black body（黑体）"这个名字容易误导——它指的是**在所有波长上完全吸收**，与目视颜色无关。雪在可见光下是白的（可见光反照率高），但在 10 μm 红外波段几乎是完美黑体（ε ≈ 0.99）。这也是为什么地球的**反照率**（针对短波）和地球的**黑体发射**（针对长波）可以在同一套公式里并存而不矛盾。

### 2.7 斯特藩–玻尔兹曼定律（Slide 15）

**是什么。** Slide 15 原文：

> "All bodies radiate energy as electromagnetic radiation. A black body absorbs all radiation falling on it and it emits radiation as a function of its surface temperature.
> **Stefan-Boltzmann Law**: Total energy is related to temperature by: [公式]
> where:
> - **I** = Energy per unit area emitted per second (**W m⁻²**)
> - **T** = Equivalent black body Temperature (**K**)
> - **σ** = Stefan-Boltzmann constant (**5.67 × 10⁻⁸ W m⁻² K⁻⁴**)
>
> Warmer objects emit energy more intensely than cold objects."

公式本体在 deck 提取时丢失了（是图片/公式对象），但从符号说明和答案 deck 可以确定就是：

**I = σT⁴**

**为什么是四次方？** 讲义没说，讲师也没推导，但他给了一个非常有用的**数值直觉**：

> "Because you're raising the temperature to a power of four, a **small increase in temperature rapidly leads to increases in energy**. So for example, a **doubling of surface temperature** of the sun, for example, **would change the energy emitted by a factor of 16**, which is two to the power of four."

**怎么用。** 两种典型用法：
1. 已知温度求辐射通量（本周能量收支的"出"项）；
2. 已知辐射通量反求**等效黑体温度**（这就是 Te 的定义方式）。

**边界条件。**
- T 必须是**绝对温度（K）**。用摄氏度代入是本周最致命的错误。
- I 是**单位面积**的通量，要得到总功率必须乘面积。
- 这是对**全波段积分**后的结果，不告诉你能量怎么分布在各波长上——那是维恩定律和普朗克函数的事。

📎 背景补充（典型数值，材料未给，由我代入计算）：
- 太阳表面（T ≈ 5800 K）：I = 5.67 × 10⁻⁸ × 5800⁴ ≈ **6.42 × 10⁷ W m⁻²**（约 64 MW/m²）
- 地球等效黑体（T = 255 K）：I = 5.67 × 10⁻⁸ × 255⁴ ≈ **239.7 W m⁻²**
- 地球实际地表（T = 288 K）：I = 5.67 × 10⁻⁸ × 288⁴ ≈ **390.1 W m⁻²**

最后两个数字的差 **390 − 240 ≈ 150 W m⁻²**，就是"地表发出去的长波"与"最终逃到太空的长波"之间的差额——这个 150 W m⁻² 正是温室效应的**能量尺度**。把它和 33 K 的**温度尺度**对照记忆很有帮助。

### 2.8 维恩定律（Slide 16）

**是什么。** Slide 16 原文：

> "**Wien's Law**: The wavelength which emits the most energy is related to temperature by: [公式]
> where:
> - **λmax** = Wavelength in **nm**
> - **T** = Temperature (**K**)
>
> Warmer objects emit a higher proportion of their energy at short wavelengths than cold objects"

公式本体同样在 deck 里丢失，但**答案 deck 的 Q6 答案明确给出了常数**：

**λmax × T = 2.897 × 10⁶**（λmax 以 **nm** 计，T 以 **K** 计）

讲师的口述版本：

> "the maximum wavelength times by temperature equals this constant value. So you can **either measure the wavelength that is emitted preferentially, or if you know the surface temperature**, you can then build an understanding of either the wavelengths that are emitted or the surface temperature, **depending on what you know**."

**怎么用。** 这是一条**双向**工具：
- 正向：知道温度 → 算峰值波长（用来判断一个物体发的是可见光还是红外）
- 反向：测到峰值波长 → 算温度（这就是 Q6 "用图估计太阳表面温度"的解法，也是天文学测恒星温度的基本手段）

**边界条件（极易出错）。** **常数的数值取决于波长的单位。**
- λ 用 **nm**：常数 = 2.897 × 10⁶ nm·K（本课采用）
- λ 用 **μm**：常数 = 2897 μm·K
- λ 用 **m**：常数 = 2.897 × 10⁻³ m·K

用错单位会得到差 10³ 或 10⁹ 的答案。**本课统一用 nm 版本。**

📎 背景补充（典型数值，由我代入）：
| 物体 | T (K) | λmax（本课公式算得） | 落在哪个波段 |
|---|---|---|---|
| 太阳 | 5800 | 2.897×10⁶/5800 = **499 nm** | 可见光（青绿） |
| 地球地表 | 288 | 2.897×10⁶/288 = **10 059 nm ≈ 10.1 μm** | 热红外 |
| 地球等效黑体 | 255 | 2.897×10⁶/255 = **11 361 nm ≈ 11.4 μm** | 热红外 |
| 火星 | 218 | 2.897×10⁶/218 = **13 289 nm ≈ 13.3 μm** | 热红外 |
| 金星 | 735 | 2.897×10⁶/735 = **3941 nm ≈ 3.9 μm** | 中红外 |

注意地球 288 K 算出的 **10.1 μm** 与 Slide 18 里说的"peaks at about 10 [μm]"完全吻合——这个数字要背下来，它同时也是**大气窗口**的位置（见 §2.14），这个巧合（其实并非巧合，是地球能散热的原因）非常重要。

### 2.9 两条定律合起来：普朗克曲线族（Slide 17）

**是什么。** Slide 17 只有三行字："Radiation Laws Combined / As temperature increases: Total energy increases / Peak wavelength decreases"，配一张多条曲线的图。讲师把这张图描述得很具体：

> "you can see the **spectral energy in the y-axis** and the **wavelength in the x-axis** here. And this is simulated for **four or five different temperatures, starting with the warmest temperature of 5,500 Kelvin, working down to 3,500 Kelvin**. For the warmest example, **the emission is significantly higher, and the peak wavelength emission is reduced**."

**图怎么读（文字复述）：**
- **x 轴**：波长（从短到长，通常横跨 UV → 可见 → 红外）
- **y 轴**：光谱辐射强度（spectral energy / spectral radiance）
- **曲线**：每条对应一个温度（5500 K 最上、3500 K 最下），每条都是**单峰、左侧陡右侧缓的驼峰形**
- **要读出的两个结论**：
  1. **温度越高，整条曲线整体抬高**（曲线下的面积 ∝ T⁴ → 斯特藩–玻尔兹曼）
  2. **温度越高，峰的位置越往左（短波）移**（峰位 ∝ 1/T → 维恩）
- **关键的额外性质（讲义未强调，但图上看得见）**：不同温度的曲线**互不相交**——高温曲线在**每一个**波长上都高于低温曲线。

📎 背景补充：这条曲线的解析形式是**普朗克函数（Planck function）**，斯特藩–玻尔兹曼定律是它对全波长积分的结果，维恩定律是它对波长求极值的结果。也就是说，本周学的两条"定律"其实是同一个物理（黑体辐射）的两个推论，不是两个独立的经验规律。本课不要求会写普朗克函数，但知道这层从属关系有助于理解为什么两条定律永远同时成立、不会互相打架。

### 2.10 地面辐射（Slide 18）

Slide 18 原文（照录，含材料本身的问题）：

> "The Earth also acts as a blackbody radiator
> **Te = 288 K** so most of the irradiance from the Earth is in the infra-red part of the spectrum and **peaks at about 10 [μ]m**."

⚠️ 这里有两处材料问题，正文照实转述，已登记勘误：
1. **符号 Te 被复用**。在能量收支那一节（Slide 30、答案 deck）里，**Te 明确指"等效黑体温度 = 255 K"**；这里却拿 Te 指代"实测地表温度 288 K"。两者是本周要**对比**的两个不同的量，用同一个符号会造成严重混淆。
2. **"10 m" 缺少 μ**。地球红外峰值是 **10 微米（10 μm）**，不是 10 米。10 米波长是无线电波。这是 pptx 转 md 时 μ 字符丢失造成的（同类问题在 Slide 19 的 "4 m" 也出现了一次）。

**怎么用。** 记住这条对照：**太阳 ≈ 5800 K → 峰值 ≈ 0.5 μm（可见光）；地球 ≈ 288 K → 峰值 ≈ 10 μm（热红外）**。**温度差 20 倍，峰值波长差 20 倍**（因为 λmax ∝ 1/T）。

### 2.11 太阳谱与地球谱的分离（Slide 19）

**是什么。** Slide 19 是本周最核心的一张图，原文标注：

> "As temperature increases: Total energy increases / Peak wavelength decreases
> **Little overlap between the incoming solar radiation and the outgoing infra-red radiation from the Earth's surface.**
> **Separated by a gap at around 4 [μ]m**
> SW / LW"

**图怎么读（文字复述）：**
- **x 轴**：波长，通常用**对数坐标**（从 0.1 μm 到 100 μm）
- **y 轴**：辐射强度（两条曲线通常各自归一化，否则太阳的峰会把地球的峰压成一条线）
- **左边的驼峰**：太阳辐射，标为 **SW（shortwave，短波）**，峰在 0.5 μm 附近，主体范围约 0.2–4 μm
- **右边的驼峰**：地面辐射，标为 **LW（longwave，长波）**，峰在 10 μm 附近，主体范围约 4–100 μm
- **两峰之间**：在 **≈ 4 μm** 处几乎不重叠

讲师对这两张图（Slide 18/19）的口述特别值得抄下来，因为他明确指出了**前一张图不含强度信息**：

> "**What this figure doesn't show is the energy intensity.** This just shows how wavelengths vary between the Sun and the Earth. And the important bit here is that **there's almost no overlap**."
>
> "This figure takes it one step further. It **starts to show the radiation intensity** and the wavelengths associated with the Sun and the Earth. And this essentially **combines the two radiation laws** ... So we predominantly have shortwave radiation from the Sun here and longwave radiation from the Earth. And this is a function of the surface temperature."

**为什么这是全周最重要的一张图。** 因为**温室效应的存在完全依赖于这个分离**。如果 SW 和 LW 重叠在一起，大气就不可能"对一个透明、对另一个不透明"——它没有办法在同一个波段上做区别对待。**正是 4 μm 这道缝，让大气有可能成为"单向阀"。**

**边界条件。** "几乎不重叠"不是"完全不重叠"。在 3–5 μm 附近两者确有微小的尾巴叠加。本课按"不重叠"处理。

### 2.12 地球能量平衡：稳态假设（Slide 20、21、27）

**是什么。** Slide 20/27（同一张，重复出现两次以强调）：

> "**Energy entering top of atmosphere = Energy leaving Earth's surface**
> Temperature of surface remains constant"

Slide 21：

> "**TE changes quite little from year to year → system is in equilibrium**
> i.e. energy inputs must be balanced approximately by energy losses."

**为什么这个假设合理，以及它的诚实边界。** 讲师在这里做了一段本周最"科学诚实"的说明，讲义上完全没有：

> "The other thing that we know is that the temperature of the surface of the Earth remains **somewhat** constant over day-to-day, week-to-week and year-to-year. **We know that we're seeing a period of increased warming, but as a first principle**, the temperature of the Earth remains somewhat the same over a period of time. ... **We know that that's not quite true, right, from the first lecture. We've seen a rapid increase in temperatures, particularly over the last 15 years.** But given the amount of incoming solar radiation, there is somewhat a balance between what is coming in and what is coming out. So the system **must be somewhat in equilibrium, although we are perturbing that equilibrium in real time**."

**这段话必须理解透**，它回答了一个很自然的学生疑问："既然地球在变暖，凭什么还能假设进出相等？"答案是：**当前的不平衡量（约 1 W m⁻² 量级）相对于总通量（约 240 W m⁻²）是很小的扰动**，所以用平衡假设算 Te 依然是好的一阶近似；而**恰恰是这个小小的不平衡，就是气候变化本身**。

📎 背景补充：这个"小小的不平衡"有个专门名字叫**地球能量失衡（Earth's Energy Imbalance, EEI）**，目前约 +1 W m⁻² 量级，绝大部分被海洋吸收。它相对于 240 W m⁻² 只有约 0.4%，所以平衡假设的误差在 Te 上只有 0.25 × 0.4% × 255 K ≈ 0.25 K 量级——完全不影响本周的结论。这个数字是我补充的，本周材料未给。

**怎么用。** 这个假设是接下来整套推导的**唯一前提**：令"进 = 出"，解出 T。

**边界条件。** 平衡假设成立于**长时间平均**和**全球平均**。它对单个地点、单个季节完全不成立（极地全年净失去能量，赤道净获得能量，靠大气和海洋环流搬运——这也正是 Week 2 讲海洋环流的意义所在）。

### 2.13 能量收入项：太阳常数、截面积、反照率（Slide 22–26）

#### （a）太阳常数（solar constant）

Slide 22 给出：**S₀ = 1370 W m⁻²**（deck 原文写作 "S0=1370 W m2"，上标丢失）。

**是什么。** 在**日地平均距离**处、**垂直于太阳光线**的单位面积上接收到的太阳辐射功率。

讲师补充了一句讲义没有的重要限定：

> "we know that the Sun emits a solar constant of around 1,370 watts per meter squared, and **it does that in all directions**. ... We know that that constant varies slightly from last week. **We know that that varies over an 11-year cycle.** But for the purposes of today, we can think of that as a fixed value."

这一句直接接回 **Week 2 的太阳变率**：所谓"solar constant"其实**不是常数**，它随 11 年太阳周期有约 0.1% 的起伏。本课按固定值处理。

📎 背景补充：S₀ 的现代最佳估计约为 1361 W m⁻²（本课用 1370，属早期常用值，差异 < 1%，对 Te 的影响 < 0.2 K）。S₀ 也可以从太阳表面通量反推：S₀ = σT_sun⁴ × (R_sun/d)² = 6.42×10⁷ × (6.96×10⁸ / 1.496×10¹¹)² ≈ **1388 W m⁻²**，与 1370 相当接近——这是一个很好的自洽性检验。这段推导材料完全没有，是我补充的。

#### （b）截取面积：为什么是 πr² 而不是 4πr²

Slide 22/25 原文：

> "Energy In: Incoming solar radiation = So × Area (A) = So × πre²
> Area of Earth **perpendicular to solar radiation**: A = πre² where re = radius of Earth = **6370 km**"

**为什么。** 太阳光是**近似平行光**打过来的。地球挡住的不是它的整个表面，而是它在垂直于光线方向上投影出来的那个**圆盘（disc）**，面积就是 πr²。

⚠️ 讲师在转写里这句说错了（ASR 或口误）："the area of that that is intercepted from the incoming solar radiation can be calculated by the **diameter** of the Earth, which is of course pi r squared" ——"diameter（直径）"应为"半径 / 截面圆盘"。πr² 用的是半径。已登记勘误。

**这是本周最经典的"因子 4"陷阱**：收入用 **πr²**（迎光圆盘），支出用 **4πr²**（整个球面，因为地球全天候向各个方向辐射）。两者相除就是 **4**。这个 4 会一路带到最终公式的分母里。

📎 背景补充：这个"因子 4"的物理含义可以这样理解——**地球把接收到的太阳能"摊平"到了 4 倍大的面积上去发射**（因为它自转，且夜半球也在辐射）。所以全球平均的入射短波是 S₀/4 ≈ 342 W m⁻²，再乘 (1−α) = 0.7 得到 ≈ 240 W m⁻²。这两个数（342 和 240）在下周的能量收支图里会反复出现，值得先记住。

#### （c）反照率（albedo, α）

Slide 23：

> "But some of the Sun's radiation is reflected away!
> **Albedo (α): Fraction of energy that is reflected away**
> Dark surfaces have α ~ 0
> Light surfaces have α ~ 1"

Slide 24 给出地球反照率的**分解**：

| 来源 | 贡献 |
|---|---|
| 地表（陆地与海洋）反射 | **5%** |
| 云反射 | **20%** |
| 空气散射 | **6%** |
| **合计** | **~30%（α ≈ 0.3）** |

讲师对这个分解做了两处很有价值的口头评注：

> "around **5% of the incoming solar radiation is reflected from land and the ocean surface, and that's predominantly low because of the dark ocean surface**. Around **20% from clouds, which shows you how important they are in terms of the radiative balance and understanding and getting a handle on the cloud effects is vital**, and around **6% is scattered by air**."

两个要点：
1. **地表只贡献 5%，而且低是因为海洋很暗**——地球 71% 是海面，海水在可见光下反照率很低（约 0.06）。
2. **云是最大的单一贡献者（20%，占总反照率的三分之二）**——所以讲师说搞清楚云的效应"is vital"。这句话是理解为什么气候模式里**云反馈是最大不确定性来源**的伏笔（Week 7 讲 Climate Models 时会回来）。

Slide 24 最后一行还预告了 Week 4：

> "Land-use change driven by human activity modifies surface reflectivity, changing the proportion of solar radiation reflected back to space – **Week 4**"

讲师对应说：

> "Simon next week will tell you ... about how we are changing our landscape and having an impact on the surface albedo and the impact that that might have on climate change moving forward."

#### （d）把反照率装进收入项（Slide 26）

Slide 26 原文（照录，含材料错误）：

> "Energy In: Incoming solar radiation = So × Area (A) × **albedo** = **0.7 × So × πre²**"

⚠️ **材料错误**：0.7 是 **(1 − albedo)**，不是 albedo（albedo = 0.3）。文字标注"× albedo"与算式"0.7 ×"自相矛盾。**转写里讲师说对了**：

> "So we can put that into the calculation, so we times the **one minus the albedo**, so **one minus the albedo** to give the amount of incoming solar radiation"

正文照实转述材料，更正已登记勘误。**答题时必须写 (1 − α)。**

**边界条件。** 讲师补了一句："that will obviously **vary by location** and it will **vary over time**, and it will also **as you will find out vary by planet**"——反照率不是普适常数，随地点（冰盖 vs 海洋）、时间（季节雪盖、冰川消退）、行星（金星 0.75 vs 火星 0.16）而变。这也正是**冰–反照率反馈（ice–albedo feedback）**的入口。

### 2.14 能量支出项（Slide 28）

Slide 28 原文（照录）：

> "Energy In: Incoming solar radiation = So × Area (A) × albedo = 0.7 × So × πre²
> **Energy Out: Outgoing Terrestrial radiation = [σ]TE⁴ × 4πre²**
> Surface area of Earth = **4πre²**"

⚠️ 材料在这里把 **σ 丢掉了**（deck 里显示为 "TE4 4πre2"）。正确写法是 **σT_E⁴ × 4πr_e²**。同样的丢失出现在答案 deck 的 Slide 3。已登记勘误。

讲师口述：

> "we know that the Earth radiates, and we know that it radiates **across the entire surface**, and it does so as a function of its temperature, which is defined by the Stefan-Boltzmann law. The surface area of the Earth, you should know, is **4 pi r squared**."

**关键对比再强调一次：**

| | 面积 | 物理理由 |
|---|---|---|
| **收入（短波）** | **πr²** | 平行光只被迎光**圆盘**截住 |
| **支出（长波）** | **4πr²** | 球体**全表面**、全天候向所有方向辐射 |

### 2.15 温度缺口与温室效应的引入（Slide 30）

**是什么。** Slide 30 是全周的转折点：

> "Energy leaving Earth's surface = Energy entering top of atmosphere
> **If Te = 255 K (−18 °C), why is the global mean surface temperature of the earth actually 288 K (+15 °C), why are we not freezing?!**
> Down to the **different ways the atmosphere processes shortwave (solar) and longwave (terrestrial) radiation**
> **The Greenhouse Effect:**
> - **Different molecules absorb radiation at specific wavelengths.**
> - **Several molecules in the atmosphere absorb strongly in the infrared → Greenhouse gases**
> - **The atmosphere is nearly transparent to SW radiation, but absorbs LW.**"

**这三条要点是本周的核心命题**，请逐字理解：

1. **"Different molecules absorb radiation at specific wavelengths"** — 吸收是**选择性**的，不是笼统的"挡住热"。为什么有选择性，见 §2.17 的量子解释。
2. **"Several molecules absorb strongly in the infrared → Greenhouse gases"** — **"温室气体"这个身份的定义标准就是"在红外强吸收"**。不是"含碳"、不是"污染物"、不是"浓度高"。N₂ 和 O₂ 占大气 99%，却不是温室气体，就是因为它们不满足这一条（原因见 §2.17 的 📎 补充）。
3. **"The atmosphere is nearly transparent to SW, but absorbs LW"** — **这条不对称性就是温室效应的全部**。

**缺口的大小：288 − 255 = 33 K。** 这个数字必须记住。

讲师的过渡语：

> "We know that we're not sitting in minus 18 degrees on the Earth and there's a huge difference between the actual average temperature of Venus compared to what you have calculated. **Any guesses why?**"

（这是一处课堂互动，学生给出了答案，讲师说 "Perfect. Great."，随后归结到"the way that planets deal with incoming solar radiation versus outgoing radiation"。）

### 2.16 大气窗口（Slide 31）

Slide 31 原文：

> "Radiation is absorbed by the atmosphere......and reradiated in **all directions**
> Radiation can go through: **the atmospheric window**"

讲师对这一页的展开比讲义丰富得多，而且给出了**两个**窗口的位置和一个非常漂亮的洞察：

> "this absorption distribution ... shows the absorption across the electromagnetic spectrum, starting at the **UV, which is almost entirely absorbed by our atmosphere, which is a good thing**. But ... as we move to the infrared bands, there's also pockets where absorption across the infrared is **very strong** also. So through these red bands, radiation is **almost entirely absorbed** by our atmosphere and then it is **re-radiated in all directions**.
> So what this means is that there's a relatively short **atmospheric window** in which radiation is unperturbed by our atmosphere and that's predominantly **in the visible, as you might suspect. That's why our eyes are tuned to see this wavelength** and the infrared window, which is known as the **infrared atmospheric window at 10 microns**."

**三个必须记住的点：**

1. **窗口有两个**：**可见光窗口**（约 0.4–0.7 μm）和**红外大气窗口（infrared atmospheric window）**，后者在 **8–13 μm**，讲师简称"at 10 microns"。
2. **"That's why our eyes are tuned to see this wavelength"** —— 这是讲师抛出的一个**演化论式的洞察**：眼睛之所以对可见光敏感，是因为那是大气**恰好透明**的波段（同时也是太阳辐射最强的波段）。这句话讲义上完全没有，但极有记忆价值。
3. **"re-radiated in all directions"（向各个方向再辐射）**是温室效应的关键动词。**吸收本身不加热地表，"向下的那一半再辐射"才加热地表。** 如果被吸收的能量只向上再辐射，就没有温室效应。

**红外窗口与 10 μm 峰值的关系（重点难点）：** 地球的发射峰在 10 μm，而大气窗口也在 10 μm 附近。**这意味着地球恰好在自己发射最强的波段上拥有一条通往太空的逃生通道。** 如果没有这扇窗，地表温度会比现在高得多。这也解释了为什么答案 deck 的 Q5 会问"如果臭氧的 9.6 μm 红外吸收带不存在会怎样"——因为臭氧的吸收带正好**卡在这扇窗的中间**（见 §五 Q5）。

### 2.17 分子为什么挑波长吸收：量子能级（Slide 32、33、34）

这是本周物理最深的一段，讲义分三页讲。

#### （a）电子能级跃迁：高能辐射（Slide 32 吸收 / Slide 33 发射）

Slide 32 原文：

> "For high energy radiation (<UV) a molecule can only absorb radiant energy **if the wavelength of the radiation corresponds to the difference between two of its energy levels**
> For different molecules (of different composition and shape) **the spacing between energy levels is different** and so the absorption of radiant energy by molecules of differing structure occurs **in different regions of the electromagnetic spectrum**.
> **Absorption**: The molecule is raised from state i to a higher state f by absorbing a photon whose energy is equal to
> **ΔE = E_f − E_i = hν**"

Slide 33 是镜像的发射过程：

> "**Emission**: The molecule drops from a higher energy level or state to a lower energy state. It will emit a photon whose energy is
> **ΔE = E_i − E_f = hν**"

讲师的口述版（把"共振"这个概念说得很清楚）：

> "molecules have different energy states and they can move between the ... energy states relatively rapidly **if the right amount of energy is absorbed**. So you have an energy state one down here and an energy state two, and there's a **very defined difference** between these two energy states. **Only if the photon with exactly the right amount of energy is absorbed, can it move to the next energy state.**
> What this means is that molecules **uniquely interact with different wavelengths depending on the molecule itself**. So **specific molecules only interact with specific energies. Equally, they only emit specific energies.** ... So these molecules will also **emit that same energy as is absorbed**."

**核心逻辑链（必须能自己复述）：**

> 分子的能级是**离散**的 → 相邻能级差 ΔE 是一个**确定的值** → 只有 hν 恰好等于 ΔE 的光子才能被吸收 → 由 E = hc/λ，这对应一个**确定的波长** → 不同分子（组成与形状不同）能级间距不同 → **每种分子有自己独特的"吸收指纹"**

这条链既解释了**为什么温室气体存在**，也解释了**为什么它们只在特定波段起作用**，还顺带解释了**光谱学为什么能识别分子**。

#### （b）红外：振动与转动（Slide 34）

Slide 34 原文（只有一句，但极其关键）：

> "For infrared radiation, **there is not enough energy to change energy levels**, instead molecules **rotate, vibrate, stretch and bend**, and then reradiate."

**这一句是全周最容易被读漏、但考试最爱考的一句。** 它说的是：

- **紫外/可见光**（高能光子，约 2–10 eV）→ 能量足够**推动电子跃迁**（electronic transitions）
- **红外**（低能光子，约 0.05–0.5 eV）→ 能量**不足以**改变电子能级，只能激发分子的**转动（rotate）、振动（vibrate）、伸缩（stretch）、弯曲（bend）**模式，然后再辐射出去

这与我在 §2.3 📎 里算的数字完全对上：可见光光子 2.48 eV，10 μm 红外光子只有 0.124 eV，**差约 20 倍**。这就是"not enough energy"的定量含义。

📎 背景补充（材料完全没讲，但这是理解"为什么 N₂ 和 O₂ 不是温室气体"的唯一途径）：一个分子要**吸收红外**，其振动模式必须能引起**偶极矩（dipole moment）的变化**。
- **N₂、O₂** 是**同核双原子分子**，完全对称，只有一种振动模式（伸缩），而且伸缩时偶极矩始终为零 → **红外不活跃 → 不是温室气体**。这就是为什么占大气 99% 的气体对温室效应毫无贡献。
- **CO₂** 虽然是线性对称分子（永久偶极矩为零），但它有**弯曲模式（bending mode）**和**非对称伸缩模式（asymmetric stretch）**，这两种振动会**破坏对称性、产生瞬时偶极矩** → 红外活跃。CO₂ 的弯曲模式恰好对应 **15 μm** 的强吸收带，这就是 CO₂ 作为温室气体的物理来源。
- **H₂O** 是弯曲的极性分子，本来就有永久偶极矩，且有三种活跃振动模式 + 丰富的转动谱 → 在红外多个波段强吸收，是**最强的温室气体**。

有了这条"对称性 → 偶极矩 → 红外活性"的判据，Slide 30 里"Several molecules absorb strongly in the infrared"就从"记住哪几个"变成了"能自己判断哪几个"。

### 2.18 关键吸收气体与吸收谱（Slide 35、36）

Slide 35 原文：

> "At sea level atmospheric gases have removed sections of the spectrum according to their **absorption bands**.
> Note especially the **strong absorption of infrared radiation by water vapour and carbon dioxide**."

Slide 36 是一张图（OCR 只捕到 "Total absorption and scattering" 和 "black-body spectra"）。

**图怎么读（结合讲师口述复述）：**
这类图通常分成上下两部分：
- **上半部**：太阳与地球的黑体谱（两个驼峰），以及**实际到达地面的谱**（被"啃"掉一块块的曲线）
- **下半部**：**逐种气体**的吸收率随波长的分布（每种气体一条），最下面一条是**总吸收与散射（Total absorption and scattering）**
- **x 轴**：波长（对数），从 UV 经可见到远红外
- **y 轴**：吸收比例（0 到 100%）
- **要读出的结论**：UV 段几乎 100% 被吸收；可见段几乎不被吸收（窗口）；红外段被切成若干"全吸收的红块"与若干"透明的窗口"

讲师对这张图的讲评包含了本周若干关键判断：

> "The figure that I'm showing here is the **total absorbing and scattering, which is made up of lots of different important molecules**. The real focus that we have as climate scientists are on the **long-lived greenhouse gases because they are what we're perturbing through our anthropogenic activity**. But you'll notice that **water vapour is also an important absorber across many bands in the infrared. But because we're actively influencing carbon dioxide, ozone, methane and nitrous oxide, these are the focus of our interests** from a global climate change perspective.
> So you can see that **carbon dioxide has a strong absorption band around 10 to 20 microns and below**.
> **Ozone acts to reduce the UV radiation** ... **But it also, in the troposphere, acts as a greenhouse gas because it also interacts with outgoing infrared radiation.**
> **As the concentrations of these greenhouse gases increase, so does the absorption and therefore so does the temperature on the surface of our planet.**"

**三个要点：**

1. **水汽是最强的红外吸收体，但不是我们关注的对象**——因为**我们不直接排放水汽、也不直接控制它的浓度**。这个区分极其重要：物理重要性 ≠ 政策关注度。（📎 背景补充：水汽在气候系统里的角色是**反馈（feedback）**而非**强迫（forcing）**——大气水汽量由温度决定（Clausius–Clapeyron 关系），温度升高 → 水汽增多 → 温室效应增强 → 温度更高。这是气候系统里最大的正反馈。这个"强迫 vs 反馈"的区分本周材料没有明说，但它正是讲师那句"because we're actively influencing..."背后的逻辑。）
2. **CO₂ 的强吸收带在"10 到 20 微米及以下"**——注意这个范围**正好覆盖地球发射峰（10 μm）的长波一侧**，也正好挤压红外窗口的边缘。
3. **臭氧有双重身份**：平流层里吸收 UV（好事），对流层里作为温室气体吸收出射红外（坏事）。这正是 Q5 的题眼。

### 2.19 大气对辐射的净处理（讲师对 Slide 36 的进一步讲评）

这一段讲义上没有，全部来自转写，但它是把前面所有内容**定量收口**的关键：

> "you can see that the **UV is almost entirely removed by ozone in the stratosphere** and **around 70 to 75% of incoming solar radiation is transmitted**.
> That's quite different. So **lots and lots of the outgoing infrared radiation is absorbed** by different molecules and gases within the atmosphere. **Which means only a small amount of outgoing radiation ever makes it out to space.**
> And that ultimately leads to a warming because **that outgoing infrared radiation is re-radiated, some of which goes back to the surface of the planet and leads to warming**."

**把这段和 Slide 30 的第三条要点并排看：**

| | 短波（太阳） | 长波（地面） |
|---|---|---|
| 大气的处理 | **70–75% 透过** | **大部分被吸收** |
| 结果 | 能量顺利抵达地表 | 能量被截留在系统内 |
| 关键动作 | — | **向所有方向再辐射，其中向下的那部分加热地表** |

**这张对照表就是温室效应的完整机制。**

### 2.20 温室效应的六步总结（Slide 39）

Slide 39 给了一个**可以直接作为简答题答案的六步版本**，建议逐字记忆：

1. Some solar radiation absorbed by earth's surface and atmosphere.
   （部分太阳辐射被地表与大气吸收。）
2. Earth and atmosphere emit infrared radiation.
   （地球与大气发射红外辐射。）
3. Greenhouse gases absorb some of this infrared radiation.
   （温室气体吸收其中一部分红外辐射。）
4. Greenhouse gases (water, CO₂ + others) give off infrared radiation **in all directions**.
   （温室气体向**所有方向**发射红外辐射。）
5. Earth absorbs **downward directed** infrared radiation.
   （地球吸收**向下**的那部分红外辐射。）
6. **Result: warmer surface temperature = 288 K rather than 255 K.**
   （结果：地表温度是 288 K 而非 255 K。）

**判分要点提示**：第 4 步的 "in all directions" 和第 5 步的 "downward directed" 是这道题的**得分关键**。只写"温室气体吸收红外所以变暖"通常拿不到满分，因为没有说明**能量是怎么回到地表的**。

### 2.21 辐射强迫（Slide 38）

Slide 38 原文：

> "**Definition of radiative forcing:**
> The change in radiation balance **at the tropopause** between the incoming solar radiation and the outgoing earth's radiation (**net irradiance**).
> **Significance:**
> Increase in greenhouse gases has **reduced the amount of longwave radiation leaving the troposphere – positive radiative forcing.**"

**是什么。** 辐射强迫 = **对流层顶（tropopause）处净辐射通量的变化量**，单位 **W m⁻²**。

**为什么定义在对流层顶？** 讲义没解释。📎 背景补充：这是一个技术性但重要的约定。对流层内部大气与地表通过对流强耦合，可以看作一个整体；平流层则会在几个月内独立调整到新的辐射平衡。因此把"分界面"取在对流层顶，能最干净地度量"整个地表–对流层系统"净得到了多少能量。IPCC 使用的是"平流层温度调整后的对流层顶辐射强迫"（stratosphere-adjusted RF）或更新的"有效辐射强迫（ERF）"。这些细节本周不要求，但知道"为什么是对流层顶而不是地表或大气顶"能避免死记硬背。

**正负号约定（易错）：**
- **正强迫（positive forcing）= 系统净得到能量 = 趋向变暖**。温室气体增加 → 出射长波减少 → 净通量正变化 → **正强迫**。
- **负强迫（negative forcing）= 系统净失去能量 = 趋向变冷**。硫酸盐气溶胶散射短波 → 反射掉更多入射 → **负强迫**（这是答案 deck Q3 的核心）。

**怎么用。** 辐射强迫是**把各种不同性质的气候驱动因子（温室气体、气溶胶、太阳变率、土地利用）放到同一把尺子上比较**的通用货币。下周（Week 4）的核心就是把这些驱动因子的强迫值列出来比大小。

### 2.22 大气组成（Slide 40）

Slide 40 原文照录：

| 成分 | 体积比 |
|---|---|
| N（应为 N₂） | 78% |
| O₂ | 21% |
| Ar | 0.93% |
| CO₂ | 0.03% |
| CH₄ | 0.0018% |
| H₂O | **0.2 到 2.6%（可变）** |

⚠️ 这一页有三处问题（正文照录，已登记勘误）：
1. **"N 78%"** 应为 **N₂ 78%**（氮以双原子分子存在）。
2. **CO₂ 0.03%** 相当于 300 ppm，是**过时数值**。当代大气 CO₂ 已超过 420 ppm，即约 0.042%。
3. **CH₄ 0.0018%** 相当于 **18 ppm**，与实际的约 1.9 ppm 差了**约一个数量级**。正确值应为约 **0.00019%**。这很可能是漏了一个 0 的打字错误。

**这一页要读出的结论（讲义没明说，但这是它存在的理由）：**

> **占大气 99% 以上的 N₂、O₂、Ar 全都不是温室气体；而真正造成 33 K 增温的 CO₂、CH₄、H₂O 加起来还不到大气的百分之几。**

这个巨大的"浓度 vs 影响"错位，正是理解气候变化的钥匙：**改变一个只占万分之四的成分，就足以改变整个行星的温度。** 另外注意水汽的浓度范围（0.2%–2.6%）比 CO₂ 大一个到两个数量级，且**高度可变**（这就是为什么它是反馈不是强迫）。

### 2.23 三种关键温室气体的档案（Slide 41、42、43）

讲义为 CO₂、CH₄、N₂O 各做了一页档案卡。这三页信息密度很高，逐条整理：

#### （a）二氧化碳 CO₂（Slide 41）

| 项目 | 内容 |
|---|---|
| 地位 | **人为辐射强迫的主导贡献者**（Dominant contributor to anthropogenic radiative forcing） |
| 主要来源 | 化石燃料燃烧（能源、交通、工业） |
| 其他来源 | **水泥生产中的煅烧（calcination）：CaCO₃ → CaO + CO₂** |
| 汇的削弱 | 土地利用变化与毁林**减少长期碳汇** |
| 大气寿命 | **数百年**（with long tail effects，带长尾效应） |
| 减排的空气质量共同效益 | 通过淘汰化石燃料减 CO₂，同时降低 **PM、SO₂、NOₓ** 排放，改善城市空气质量、减少空气污染的健康影响 |

📎 背景补充：水泥的 CO₂ 排放有两个来源——**煅烧的化学反应本身**（CaCO₃ 分解释放 CO₂，这部分无法靠换燃料消除）和**加热窑炉的燃料燃烧**。讲义列的是前者，它是水泥行业"难以脱碳"的根本原因。另外，"long tail"指的是：即使停止排放，一部分 CO₂ 仍会在大气中滞留上千年——CO₂ 没有单一的衰减时间常数，因为它在大气–海洋–陆地生物圈之间循环，不像 CH₄ 那样有明确的化学清除路径。

#### （b）甲烷 CH₄（Slide 42）

| 项目 | 内容 |
|---|---|
| 地位 | **第二重要的人为温室气体** |
| 主要来源 | 反刍动物的**瘤胃发酵（fermentation in ruminants）**、**稻田（rice paddies）** |
| 其他来源 | 化石燃料开采、加工、输配过程中的**泄漏（losses）**；垃圾填埋场与厌氧废物分解 |
| 大气寿命 | **约 12 年（短）** |
| 减排的空气质量共同效益 | 与 CO₂ 类似，但**甲烷控制还能减少近地面臭氧（ground-level O₃）的生成**，改善呼吸系统健康并**提高作物产量** |

📎 背景补充：甲烷的"短寿命 + 强吸收"组合有一个重要的政策含义——**减甲烷见效快**。CO₂ 减排要几十年才在温度上看出效果，而甲烷因为 12 年就周转一轮，减排在十几年尺度上就能明显压低升温速率。这也是近年"全球甲烷承诺（Global Methane Pledge）"类政策的物理依据。另外，甲烷在对流层被 OH 自由基氧化，链式反应会生成臭氧——这就是讲义所说"减甲烷可减近地面臭氧"的化学路径。

#### （c）氧化亚氮 N₂O（Slide 43）

| 项目 | 内容 |
|---|---|
| 地位 | **强温室气体**，且**对平流层臭氧有显著影响** |
| 主要来源 | **农业土壤**，源于**氮肥使用** |
| 微生物过程 | **硝化作用（nitrification）与反硝化作用（denitrification）** |
| 其他来源 | 粪肥管理、工业化学品生产 |
| 大气寿命 | **约 120 年（很长）** |
| 减排的空气质量共同效益 | 提高**化肥利用效率**可减少**氨（NH₃）**排放，从而降低**二次颗粒物（secondary particulate matter）**的生成 |

讲师对这三者的来源做了一段口头补充，并预告了后续案例：

> "I put for now, just for interest, the **global carbon dioxide budget predominantly coming from fossil fuels and industries**. The **global methane budget, which in large part comes from agriculture** and the contribution, of course, in fossil fuel burning. And the suite of **N2O sources, again, with a big focus on the agricultural side of things**. So when we look at the case study examples ... we will focus our attention to the **agricultural settings**, which are a very important driver of some of the climate change we're seeing today."

**三气体横向对比（这是最容易考的一张表）：**

| | CO₂ | CH₄ | N₂O |
|---|---|---|---|
| 强迫地位 | 第一 | 第二 | 第三（讲义未明确排序，但按呈现顺序） |
| 主导来源部门 | **能源/工业** | **农业 + 化石燃料泄漏** | **农业（氮肥）** |
| 大气寿命 | **数百年** | **~12 年** | **~120 年** |
| 独特的共同效益 | 减 PM/SO₂/NOₓ | 减近地面 O₃、增产 | 减 NH₃、减二次颗粒物 |

### 2.24 变化中的大气组成与空气质量共同效益（Slide 44、45）

Slide 44 标题为 "Changing Atmospheric Composition"（图，无提取文字），Slide 45 为 "Air-Quality Co-Benefits"（图，无提取文字）。

**图怎么读（📎 基于讲师口述与本课惯例的复述；具体图形内容 deck 未提取出文字，此处只描述可确定的部分）：** Slide 44 依据讲师的话，应是 CO₂、CH₄、N₂O 三者浓度的历史曲线：

> "what we know is that the **concentrations of these greenhouse gases are increasing** and hopefully now you have an appreciation of the impact that they have and the science behind their impact."

讲师对 Slide 45 的讲评（这是本周从"物理"转向"政策"的枢纽）：

> "We are, however, actively trying to reduce these emissions and we can start to think about where there are **co-benefits from an air quality perspective**. So as we ultimately try to reduce emissions of carbon dioxide, methane and N2O, we might **also be actively reducing our aerosol concentrations**. So there's co-benefits from an air quality perspective ... and that might have an impact on our health **almost immediately**."

**"almost immediately" 这个副词很关键**：气候效益是几十年尺度的，而空气质量的健康效益是**当年就兑现**的。这个时间尺度的不对称，是气候政策论证里最有力的一张牌。

### 2.25 气溶胶（Slide 46、47）

Slide 46：

> "**Understanding aerosols**
> Tiny **solid or liquid** particles suspended in the air"

Slide 47：

> "**Health Effects and Radiative Forcing**
> **Particle pollution is associated with disease in every organ where it has been studied**
> Aerosols are also a **key part of radiative forcing**"

讲师对这两页的展开，是本周转写增量最大的一段之一：

> "they are ultimately **tiny solid or liquid particles that are suspended in the air**. This figure shows the **human hair** and it gives you an idea of the sorts of sizes of particles that we're thinking about atmospherically. Typically we think about **PM10 and PM2.5**, so you can fit roughly **five or six PM10 [particles] across the human hair**, which gives you an idea of some of the sizes of these particles.
> It's also true that some of these aerosol particles come from a **very wide range of sources**. They can be **directly emitted from industrial processes, domestic combustion, road transport**."

> "We know that aerosol particles have a detrimental effect on our health. **In almost every organ of the body in which the effects of aerosols have been studied, detrimental effects have been seen.** And that's all the way down to things like **preterm birth, birth weights and adverse birth outcomes**.
> So from a health perspective, reducing aerosol concentrations is fantastic. **But also aerosols, as you know, play a key part in radiative forcing. So they are offsetting some of the warming we are seeing from the increased carbon dioxide, methane and N2O concentrations.** So there's some discussions there about having an **air quality benefit, but a potential climate disadvantage**."

**必须记住的三点：**

1. **气溶胶的定义包含"固体**或**液体"**——硫酸盐气溶胶是液滴，黑碳是固体颗粒。
2. **尺度直觉**：人类头发直径约 50–70 μm，横排能放下 5–6 个 PM10（10 μm）颗粒。PM2.5 更小，能深入肺泡并进入血液。
3. **气溶胶的双重身份**：**健康上是纯粹的坏东西，气候上（对硫酸盐等散射性气溶胶而言）是降温的、即在"掩盖"温室气体的增温**。这个张力就是 Q3、Q4 的全部内容。

📎 背景补充：气溶胶影响气候有两条路径，讲师提到的"direct and indirect effect"就是指这两条：
- **直接效应（direct effect）**：颗粒物本身散射（硫酸盐、硝酸盐 → 降温）或吸收（黑碳 → 增温）太阳辐射。
- **间接效应（indirect effect）**：颗粒物充当**云凝结核（cloud condensation nuclei, CCN）**，使云滴数量增多、粒径变小 → 云更亮、反射更多阳光（Twomey 效应），且云寿命可能延长 → 降温。
答案 deck 在 Q3 里同时提到了"scatter incoming shortwave solar radiation"（直接）和"increase cloud reflectivity"（间接），正是这两条。这个术语区分讲义正文没有明写，但讲师在开场时说过"a lot of that warming is offset by the **direct and indirect effect** of aerosols"。

### 2.26 行星比较：温室效应强度的对照实验（Slide 48 第 7 条 + 答案 deck）

Slide 48 总结第 7 条：

> "Differences between planetary temperatures (e.g. Earth, Mars, Venus) illustrate how **atmospheric composition and pressure** control the strength of the greenhouse effect."

这是本周最漂亮的教学设计：**三颗行星构成一组天然对照实验**，用同一套公式算，差异全部落在"大气"上。

| | 地球 | 火星 | 金星 |
|---|---|---|---|
| 太阳常数 S₀ (W m⁻²) | 1370 | 590 | 2637 |
| 反照率 α | 0.30 | 0.16 | 0.75 |
| 半径 (km) | 6370 | 3389.5 | 6052 |
| **计算黑体温度 T_e (K)** | **255** | **216** | **232** |
| **实测平均表面温度 (K)** | **288** | **218** | **735** |
| **温室效应 ΔT (K)** | **33** | **2** | **≈ 503** |
| 大气压 | ~1000 mb | **~6 mb** | **~92 倍地球密度** |
| CO₂ 情况 | 微量 | 占大气 95%，**总量约为地球的 16 倍** | **绝大部分是 CO₂** |

（数值来源：太阳常数/反照率/半径来自答案 deck Slide 4、5；实测温度 218 K 与 735 K 来自转写讲师口述；压强与 CO₂ 倍数来自答案 deck Slide 6/7 与其备注。）

**要读出的结论：**

1. **黑体温度与"大气"完全无关**——它只由 S₀ 和 α 决定。所以金星虽然离太阳近得多（S₀ 是地球的近 2 倍），但它的反照率极高（0.75，因为整颗星被硫酸云包裹），算出来的 T_e 反而比地球**低**（232 K < 255 K）。**这是本周最反直觉的一个结果**，讲师专门确认过："Venus being slightly warmer than that of Mars, but cooler than that of Earth."
2. **实测与计算的差值 ΔT 才是温室效应的度量**。火星 2 K、地球 33 K、金星 500 K 以上——**跨了两个半数量级**。
3. **差异由什么决定？** 答案 deck 的说法：火星大气**极薄**（6 mb vs 地球 1000 mb），尽管 **95% 是 CO₂、CO₂ 总量约为地球的 16 倍**，温室效应仍只有 2 K；金星大气密度是地球的 **92 倍**且主要是 CO₂，于是成了"a hothouse"（答案 deck Slide 7 用词）/"a raging inferno"（Slide 6 备注用词）。
4. **所以温室效应的强度取决于"吸收体的总柱量"，而不只是浓度百分比。** 火星 CO₂ 占比 95% 远高于地球的 0.04%，但因为大气总量太少，绝对柱量只有地球的 16 倍（而不是几千倍），加上极低的压强导致吸收线**压致展宽（pressure broadening）**很弱，温室效应就上不去。（📎 括号里的"压致展宽"机制是我补充的，讲义只说了"pressure"是控制因素之一，没说是怎么起作用的。）

### 2.27 本周讲义自己的总结（Slide 48 全文）

Slide 48 的八条，可以作为本周的"最小知识集"：

1. All objects with a temperature above 0 K emit electromagnetic radiation, and **both the Sun and Earth behave approximately as blackbody radiators**.
2. Radiation laws (**Stefan–Boltzmann and Wien's Law**) explain why hotter objects emit more energy and at shorter wavelengths than cooler objects.
3. Earth's energy balance is set by incoming solar radiation and outgoing terrestrial radiation; assuming blackbody equilibrium gives an effective Earth temperature of **~255 K (−18 °C)**.
4. The observed global mean surface temperature (**~288 K, +15 °C**) is higher because of the greenhouse effect.
5. The atmosphere is **largely transparent to shortwave** solar radiation, but **absorbs and re-emits longwave infrared** radiation emitted by the Earth.
6. Greenhouse gases (e.g. H₂O, CO₂) absorb infrared radiation at **specific wavelengths** and re-radiate energy **in all directions**, warming the surface and lower atmosphere.
7. Differences between planetary temperatures (e.g. Earth, Mars, Venus) illustrate how **atmospheric composition and pressure** control the strength of the greenhouse effect.
8. Increasing greenhouse gas concentrations enhance infrared absorption, leading to **positive radiative forcing** and further warming.

---

## 三、公式与图表

### 3.1 公式一：波速关系 fλ = c

| 项 | 含义 | 单位 | 典型值 |
|---|---|---|---|
| f | 频率（frequency） | Hz（s⁻¹） | 可见光 ~6 × 10¹⁴ Hz |
| λ | 波长（wavelength） | m（本课常用 nm、μm） | 可见光 ~500 nm |
| c | 光速（speed of light） | m s⁻¹ | 3.00 × 10⁸ m s⁻¹ |

**来源**：波动学的基本运动学关系（速度 = 波长 × 单位时间通过的波数）。
**适用条件**：真空或近真空（大气中折射率 ≈ 1.0003，可忽略）。
**边界**：f 与 λ **成反比**，因为 c 固定。

📎 背景补充（本课未给 c 的具体值，此处补上）：c = 2.998 × 10⁸ m s⁻¹，本课计算用 3 × 10⁸ 足够。

### 3.2 公式二：普朗克–爱因斯坦关系 E = hf

| 项 | 含义 | 单位 |
|---|---|---|
| E | **单个光子**的能量 | J |
| h | 普朗克常数（Planck's constant） | J s |
| f | 频率 | Hz |

**来源**：量子理论的基本假设（讲义直接给出，未推导）。
**变形**：结合 fλ = c 得 **E = hc/λ**。
**适用条件**：描述单个光子；不能直接用来算辐射通量。

📎 背景补充（h 的数值与典型光子能量，材料未给）：h = 6.626 × 10⁻³⁴ J s。
- λ = 500 nm（可见）→ E = 3.98 × 10⁻¹⁹ J = 2.48 eV
- λ = 10 μm（地球红外峰）→ E = 1.99 × 10⁻²⁰ J = 0.124 eV
- λ = 15 μm（CO₂ 带）→ E = 1.33 × 10⁻²⁰ J = 0.083 eV
（1 eV = 1.602 × 10⁻¹⁹ J）

### 3.3 公式三：斯特藩–玻尔兹曼定律 I = σT⁴

| 项 | 含义 | 单位 |
|---|---|---|
| I | 单位面积、单位时间发射的总能量（辐射通量密度） | **W m⁻²** |
| T | 等效黑体温度 | **K** |
| σ | 斯特藩–玻尔兹曼常数 | **5.67 × 10⁻⁸ W m⁻² K⁻⁴** |

**来源**：普朗克函数对全波长积分的结果（本课直接给出，不要求推导）。
**适用条件**：理想黑体（ε = 1）；T 必须是绝对温度。
**关键性质**：**四次方**——温度加倍，辐射强度变 16 倍（讲师亲自举的例子）。

**典型数值（📎 除 239.7 外均为我代入计算的补充）：**

| 物体 | T (K) | I = σT⁴ (W m⁻²) |
|---|---|---|
| 太阳表面 | 5800 | 6.42 × 10⁷ |
| 地球等效黑体 | 255 | **239.7** |
| 地球实际地表 | 288 | 390.1 |
| 火星表面 | 218 | 128.0 |
| 金星表面 | 735 | 1.65 × 10⁴ |

**注意 239.7 这个数**：它同时等于 (1−α)S₀/4 = 0.7 × 1370 / 4 = **239.75 W m⁻²**。这不是巧合——这正是 Te 定义式的两边。

### 3.4 公式四：维恩定律 λmax × T = 2.897 × 10⁶

| 项 | 含义 | 单位 |
|---|---|---|
| λmax | 发射最强的波长（峰值波长） | **nm** |
| T | 温度 | **K** |
| 常数 | 维恩位移常数 | **2.897 × 10⁶ nm·K** |

**来源**：普朗克函数对波长求极值的结果（本课直接给出）。
**适用条件**：黑体；单位必须是 nm 与 K（用别的长度单位必须换常数，见 §2.8 边界条件）。
**双向使用**：已知 T 求 λmax，或已知 λmax 求 T（后者即 Q6 的解法）。

**典型数值**（见 §2.8 的表格）。

### 3.5 公式五（本周核心）：行星黑体平衡温度的完整推导

这是本周唯一需要**完整推导 + 完整计算**的公式。以下按讲义与答案 deck 的路径逐步展开。

**第一步：写出稳态条件（Slide 20/21/27）**

> 能量进入大气层顶 = 能量离开地球
> Energy IN = Energy OUT

**第二步：写出收入项（Slide 22–26）**

太阳辐射是平行光，地球截取的是一个圆盘：

    Energy IN = (1 − α) × S₀ × πr_e²

- S₀ = 太阳常数（地球：1370 W m⁻²）
- α = 反照率（地球：0.30）
- πr_e² = 迎光**截面积**（不是表面积）

⚠️ 材料在 Slide 26 与答案 deck Slide 3 上把这一项的文字标注写成 "× albedo"、算式写成 "0.7 ×"，两者矛盾。**正确的是 (1 − α)**，转写里讲师也是这么说的。

**第三步：写出支出项（Slide 28）**

地球以自身温度向**整个球面**、**所有方向**辐射：

    Energy OUT = σ T_e⁴ × 4πr_e²

- 4πr_e² = 球体**表面积**

⚠️ 材料在 Slide 28 与答案 deck Slide 3 上丢失了 σ。**正确写法必须有 σ。**

**第四步：令两者相等**

    (1 − α) × S₀ × πr_e² = σ T_e⁴ × 4πr_e²

**第五步：约掉半径（这是讲师专门强调的一步）**

两边同时出现 πr_e²，直接约掉：

    (1 − α) × S₀ = 4 σ T_e⁴

讲师原话：

> "You can input the numbers to those equations, but **the size of the Earth or the size of the planets in the case of this calculation do not affect it because they cancel each other out.** So you can rearrange, remove the size of either the Earth, Mars or Venus, plug in the numbers"

**这一步的物理含义极其重要**：**行星的平衡温度与它的大小无关**。一颗大行星接收更多能量，但也有更大的表面积去散热，两者正好抵消。所以答案 deck 里给出的半径（地球 6370 km、火星 3389.5 km、金星 6052 km）**全都是干扰项**，一个都用不上。

**第六步：解出 T_e**

    T_e⁴ = (1 − α) S₀ / (4σ)

    ┌────────────────────────────────────┐
    │   T_e = [ (1 − α) S₀ / (4σ) ]^(1/4)  │
    └────────────────────────────────────┘

这就是答案 deck Slide 3 写的 `Te = [(0.7 x 1370)/ 4σ]^(1/4) = [((1-a) * S) / (4σ)]^(1/4)`。

**第七步：代入数值（三颗行星）**

**地球：**

    T_e = [ (1 − 0.30) × 1370 / (4 × 5.67 × 10⁻⁸) ]^(1/4)
        = [ 959 / (2.268 × 10⁻⁷) ]^(1/4)
        = [ 4.228 × 10⁹ ]^(1/4)
        = 255.0 K   →  −18 °C   ✓

**火星（S₀ = 590 W m⁻², α = 0.16）：**

    T_e = [ 0.84 × 590 / (4 × 5.67 × 10⁻⁸) ]^(1/4)
        = [ 495.6 / (2.268 × 10⁻⁷) ]^(1/4)
        = [ 2.185 × 10⁹ ]^(1/4)
        = 216.2 K   ✓（答案 deck 给 216.2 K）

**金星（S₀ = 2637 W m⁻², α = 0.75）：**

    T_e = [ 0.25 × 2637 / (4 × 5.67 × 10⁻⁸) ]^(1/4)
        = [ 659.25 / (2.268 × 10⁻⁷) ]^(1/4)
        = [ 2.907 × 10⁹ ]^(1/4)
        = 232.2 K   ✓（答案 deck 给 232 K）

**计算器操作提示（📎 我的补充）**：^(1/4) 就是**开两次平方根**。以地球为例：√(4.228 × 10⁹) = 65 026，再 √65 026 = 255.0。没有 x^y 键的计算器也能算。

**第八步：与实测对比，得出温室效应**

| 行星 | T_e（算） | T_实测 | ΔT = 温室效应 |
|---|---|---|---|
| 地球 | 255 K | 288 K | **+33 K** |
| 火星 | 216 K | 218 K | **+2 K** |
| 金星 | 232 K | 735 K | **+503 K** |

**边界条件与适用范围（重要）：**
- 假设行星处于**辐射平衡**（无净能量积累）
- 假设行星是**理想黑体发射体**（ε = 1）
- 假设**无大气温室效应**——所以算出来的必然是"没有温室效应时的温度"
- 假设**没有内部热源**（对地球和火星成立；对木星等巨行星不成立）
- 假设**行星表面温度均匀**（实际有昼夜与纬度差异，因此这是一个"有效温度"而非任何一点的真实温度）

📎 背景补充（灵敏度分析，材料完全没有，但对理解气候变化很有用）：
由 T_e ∝ [(1−α)S₀]^(1/4)，两边取对数微分得 **ΔT_e/T_e = ¼ × [ΔS₀/S₀ − Δα/(1−α)]**。
- **反照率变化的影响**：若 α 从 0.30 升到 0.31（例如冰盖扩张），T_e 从 255.0 K 降到 254.1 K，即 **每 0.01 的反照率变化约对应 0.9 K**。这就是冰–反照率反馈能这么有力的原因。
- **太阳常数变化的影响**：S₀ 变化 1%，T_e 变化约 0.25% ≈ **0.64 K**。而 11 年太阳周期的 S₀ 变化只有约 0.1%，对应约 0.06 K——**远小于观测到的升温**。这个数字直接支持了 Week 2 的结论：太阳变率无法解释当代变暖。
- **极端情形**：若地球反照率为 0（全黑），T_e = 278.8 K = 5.6 °C，仍低于实测的 15 °C。**这说明即使把所有反射都消掉，也补不上 33 K 的缺口——缺口只能由温室效应解释。** 这是一个很有说服力的排除法论证。

### 3.6 公式六：分子能级跃迁 ΔE = hν

| 形式 | 过程 | 讲义原文 |
|---|---|---|
| ΔE = E_f − E_i = hν | **吸收**：分子从低态 i 跃迁到高态 f | Slide 32 |
| ΔE = E_i − E_f = hν | **发射**：分子从高态 i 落到低态 f | Slide 33 |

**符号**：E_i = 初态能量，E_f = 末态能量，h = 普朗克常数，ν（nu）= 频率（与前面的 f 是同一个量，只是符号不同——这是本周材料内部的一处符号不统一，Slide 11 用 f，Slide 32/33 用 v/ν）。

**适用条件**：讲义写的是 "For high energy radiation (<UV)"，即紫外及更高能段的**电子跃迁**。对红外，Slide 34 明确说"there is not enough energy to change energy levels"，此时激发的是**转动/振动/伸缩/弯曲**模式。

**这条公式回答的问题**：为什么吸收谱是**离散的线/带**而不是连续的？因为 E_f − E_i 是离散的。

### 3.7 图表复述汇总

本周关键图表逐张复述（deck 中大量图为图片，以下结合讲师口述还原）：

**图 1 —— Slide 9 / 37「温室效应示意图」**
- 布局：上方标 SPACE，中间横带标 ATMOSPHERE，下方标 EARTH
- 左侧：黄色/橙色箭头从 SPACE 向下 = 太阳辐射（high temp' source, Short Waves）；其中大部分箭头直穿大气到地表；小部分箭头从地表、云、大气折返向上（反射）
- 右侧：红色箭头从 EARTH 向上 = 地面辐射（low temperature source, Long Waves）；其中部分被大气层内的温室气体截住，然后**向各个方向**（包括**向下**）再发射
- 要读出：**短波下行畅通，长波上行受阻，且受阻的部分有一半回到地面**

**图 2 —— Slide 10「电磁波示意」**
- 上下两条正弦波：上面一条波长长、波峰稀疏（标 "Longer Wavelength (lower frequency)"），下面一条波长短、波峰密集（标 "Shorter Wavelength (higher frequency)"）
- 讲师的数字版本：2 Hz（1 秒内 2 个波）→ 波长减半 → 4 Hz
- 要读出：**波长与频率成反比，两者共同描述同一束辐射**

**图 3 —— Slide 12「电磁波谱」**
- x 轴：波长，从左到右由短到长（或反向），跨越 10⁻¹² m 到 10³ m 量级
- 分段（从短到长）：**γ 射线 → X 射线 → 紫外 → 可见 → 红外 → 微波 → 无线电波**
- 讲师给的锚点：无线电波"thousands of meters"；γ 射线"around the size of atomic [nuclei]"；可见光"around 500 nanometers"，红端频率低、紫端频率高
- 要读出：**可见光只占整个谱极小的一段**

**图 4 —— Slide 13「太阳的能量谱（定性）」**
- x 轴：波长（短 → 长）；y 轴：辐射强度
- 单峰曲线，峰落在可见光段
- 讲师给出的**分区百分比（讲义没有）**：**可见光约 45%，紫外约 7%，近红外到无线电约 50%**
- 要读出：**太阳虽然全谱发射，但优先发射在可见光波段**

**图 5 —— Slide 14「实测 vs 理论黑体谱」**
- x 轴：波长；y 轴：能量强度
- **实线**：实测的太阳电磁谱
- **虚线**：与太阳同表面温度的理论黑体曲线
- 要读出：**两条线基本重合 → 太阳可以当黑体处理**（这是本周唯一一处"模型验证"的证据展示）

**图 6 —— Slide 17「普朗克曲线族」**
- x 轴：波长；y 轴：光谱能量
- 4–5 条曲线，从 **5500 K**（最上、峰最靠左）到 **3500 K**（最下、峰最靠右）
- 要读出：**（i）温度↑ → 整条曲线抬高（S-B 定律）；（ii）温度↑ → 峰左移（Wien 定律）；（iii）曲线互不相交**

**图 7 —— Slide 19「太阳谱与地球谱的分离」★本周最重要**
- x 轴：波长（对数），约 0.1–100 μm；y 轴：辐射强度（两峰通常各自归一化）
- **左峰**：标 **SW**，太阳，峰 ≈ 0.5 μm
- **右峰**：标 **LW**，地球，峰 ≈ 10 μm
- **两峰之间在 ≈ 4 μm 处几乎不重叠**
- 要读出：**大气之所以能"对进来的透明、对出去的不透明"，前提就是这两条谱在波长上是分开的**

**图 8 —— Slide 23「反照率对比照片」**
- 讲师描述：一张对比照，展示"dark surfaces which have an albedo of zero, light surfaces which have an albedo of one, and everything in between"
- 要读出：**反照率是一个 0–1 的连续量，由表面性质决定**

**图 9 —— Slide 31 / 35 / 36「大气吸收谱」★第二重要**
- 上半部：太阳与地球的黑体谱，叠加"实际透过的谱"（被啃出缺口）
- 下半部：**逐气体的吸收率曲线**（水汽、CO₂、O₃、CH₄、N₂O 等各一条），最底一条是 **Total absorption and scattering**
- x 轴：波长（对数，UV → 可见 → 红外）；y 轴：吸收比例（0–100%）
- 要读出：
  - **UV 段几乎 100% 被吸收**（主要是平流层臭氧）
  - **可见段几乎透明** = 可见光窗口，透过率 **70–75%**
  - **红外段被切成一块块"全吸收的红带"，中间留下 8–13 μm 的红外大气窗口**
  - **水汽在红外多个波段都有强吸收**；**CO₂ 的强带在"10–20 μm 及以下"**（讲师原话）

**图 10 —— Slide 44「温室气体浓度变化」**
- 依讲师口述，展示 CO₂ / CH₄ / N₂O 浓度的上升趋势
- 要读出：**三者都在上升**

**图 11 —— Slide 46「气溶胶尺度对比图」**
- 一根人类头发的横截面，旁边排列 PM10 与 PM2.5 颗粒
- 讲师给的读数：**约 5–6 个 PM10 颗粒可以横跨一根头发**
- 要读出：**PM2.5 小到可以深入肺泡并进入血液**

**图 12 —— Slide 47「气溶胶健康效应」**
- 人体图，标注受影响的各器官
- 讲师补充的**讲义没有的**具体终点："preterm birth, birth weights and adverse birth outcomes"（早产、出生体重、不良妊娠结局）
- 要读出：**"disease in every organ where it has been studied"**

**图 13 —— 答案 deck Q3 提到的"figure to the right"**
- 答案原文："This represents a negative radiative forcing that partially offsets the warming caused by long-lived greenhouse gases such as carbon dioxide **as is shown in the figure to the right**"
- 📎 根据描述，这应是一张**辐射强迫条形图**（IPCC 式），温室气体为正的长条，气溶胶为负的长条。deck 未提取出图形内容，具体形式不能确定，此处仅按文字描述推断。

---

## 四、课堂补充

本节**只收 transcript 里有、讲义上没有的内容**。本周讲义只有 2 882 词，是本课最薄的一份，因此转写的增量占比极高。

### 4.1 讲师身份：客座讲座临时改由课程负责人代讲 ✅ 已在转写中核实

这是本周的一处教学变动，转写第一句就说明了：

> "Okay great, so welcome to week three of global climate change, **unfortunately Simon isn't very well this week so he was due to give his guest lecture this week**, but hopefully all will be well and he will be able to return to work next week.
> **So I'm going to give the lecture on the radiation and the greenhouse effect this week**, which is a logical succession from the natural variability that we talked about last week.
> So as I say, **Simon will give a lecture next week on the anthropogenic impacts**, all being well ... and then we will move on to the evidence base."

**事实认定：**
- 本周原定由一位名为 **Simon** 的讲者做客座讲座（guest lecture），因身体原因请假。
- 改由 **Dr Thomas Bannan**（两份 deck 首页署名的讲师）代讲"辐射与温室效应"。
- Simon 的内容顺延到 **Week 4（Anthropogenic Impacts，26 Feb）**。

**对内容深度/侧重的影响（我的判断，基于材料）：**

1. **主题没有被牺牲**。讲师明确说这个主题"is a logical succession from the natural variability that we talked about last week"——也就是说，**辐射与温室效应本来就是 Week 3 计划中的内容**（讲义 Slide 2 的周历、unit spec 的 syllabus 都把它排在 Week 3），Bannan 讲的是本来就该讲的东西，不是临时凑数的替代内容。
2. **侧重被讲师本人的研究方向拉了一把**。本周后半段（Slide 41–47）对**气溶胶、空气质量共同效益、PM2.5 健康效应、航运燃油硫含量立法**的篇幅，明显超出"辐射与温室效应"这个标题的必要范围，且讲师对这块讲得格外具体（能随口说出早产、出生体重等健康终点，以及 PM10 与头发的尺度比）。这部分很可能反映了代讲者自身的专长。**对考试的实际意义：Q2/Q3/Q4 三道气溶胶题都出现在本周的 Q&A deck 里，说明这块是要考的，不能因为它"不像辐射题"就跳过。**
3. **材料准备上出现了"双份"**。见 §4.2。

⚠️ 关于 Simon 的姓氏、职称、机构，材料中**没有任何信息**，本笔记不作推测。另外转写里出现了一处人称不一致（"**he** was due to give his guest lecture" 与后文 "all being well and **she** needs to take full health"），这应是自动转写的识别错误，不作为性别信息使用。

### 4.2 为什么文件名写成 "Week 4"：讲师自己解释了

这是本周命名混乱的**直接成因**，转写原文：

> "So I wasn't sure if Simon was going to be available today, so **both the week 3 and week 4 material is available**, the workshops we will be looking at today are the **greenhouse gas and radiative balance** work. Is that clear for everyone?"

也就是说：因为不确定 Simon 能否到场，讲师**同时把 Week 3 和 Week 4 两周的材料都放到了 Canvas 上**，学生下载时文件名被冠上了 "Week 4"。但**本节课实际讲的、workshop 实际做的，是"温室气体与辐射平衡"，即 Week 3 的内容**——这与幻灯片首页的 "Week 3 - Radiation and the Greenhouse Effect" 完全一致。

**结论：本周就是 Week 3，材料内容与周次匹配，只是文件名张冠李戴。** 已登记勘误。

### 4.3 ★ 往年考卷已提前上传（重要的应试信息）

> "there have been a couple of really useful suggestions over the last couple of weeks, one of which has included ... **quite a lot of you in fact have asked for exam papers, so for the guys that have asked for that I have uploaded those to week 11 revision portal on canvas.**
> **I wasn't going to upload those until after the mid semester test, but given that so many of you have asked for them, they are now visible on the week 11 revision module** should you wish to see all the sorts of questions that you might expect in the final exam."

**行动项：往年考卷现在就在 Canvas 的 Week 11 revision module 里，可以立刻去下载。** 讲师原本打算期中测验之后才放，是因为学生集中要求才提前开放的。

（📎 与本笔记库的对应：本课目录下有 `Past Papers/` 文件夹，很可能就是这批材料。）

### 4.4 Mentimeter 反馈渠道

> "I'll just remind you of the Mentimeter QR code so please feel free to use this ... please do use this Mentimeter link, it's really helpful for me to sort of gauge improvements throughout the course rather than wait until the end."

课程用 Mentimeter 做**持续的匿名反馈**，而不是只在学期末做评教。上面那条"提前放考卷"就是通过这个渠道提出并被采纳的——说明这个渠道是真的有人看。

### 4.5 太阳发射能量的波段分配（讲义完全没有的数字）

讲师在讲 Slide 13 的太阳能谱时给出：

> "primarily the sun emits in the visible spectrum. **Around 45 percent of the emission of the sun is in the visible. Only seven of that is higher energy in the UV, and around 50 percent of the sun's emission is through these longer wavelengths, starting in near infrared, moving up to radio waves.**"

| 波段 | 占太阳总发射 |
|---|---|
| 紫外（UV） | ~7% |
| 可见光 | ~45% |
| 近红外及更长 | ~50% |

⚠️ 注意：45 + 7 + 50 = **102%**，加起来超过 100%。这是口头讲课的粗略取整（或转写误差），不必深究，但记数字时要知道这三个是"约值"。已登记勘误。

**这组数字的用途**：它定量支持了"太阳辐射主要是短波"这个说法——**可见光加紫外就占了一半以上，而地球的发射则 100% 在红外**。

### 4.6 黑体假设的验证逻辑（讲义只有结论，转写有论证）

见 §2.6 引用的那段。核心是"**实测谱 ≈ 同温度理论黑体谱 → 因此黑体假设成立**"。

这是本周唯一一处展示**科学方法论**的地方，讲义上只留下 "behave approximately like a black body" 这一句结论。**如果考试问"我们凭什么把太阳当黑体"，这段论证就是答案。**

### 4.7 温度加倍 → 能量 ×16 的直觉例子

> "Because you're raising the temperature to a power of four, a small increase in temperature rapidly leads to increases in energy. So for example, **a doubling of surface temperature of the sun, for example, would change the energy emitted by a factor of 16, which is two to the power of four.**"

这个例子讲义没有。它的价值在于把"四次方"从一个符号变成一个可感知的量级。

📎 背景补充（一个与气候更相关的版本，我补的）：地表温度从 288 K 升到 289 K（升 1 K），发射通量从 390.1 增到 **395.5 W m⁻²**，增加约 **5.4 W m⁻²**。这个"每升 1 K，地表多辐射 5.4 W m⁻²"就是所谓的**普朗克反馈（Planck feedback）**，是气候系统里最基本的**负反馈**——它是防止地球无限升温的刹车。这个概念本周材料未提，但会在讲反馈时用到。

### 4.8 太阳表面温度的范围

> "The Sun has a surface temperature of anywhere between, I think, **5,800 Kelvin to 6,000 Kelvin**."

讲义未给太阳温度。注意讲师说的是一个**范围**并带 "I think"——答案 deck 的 Q6 通过维恩定律算出 **5800 K**，与范围下限一致。**答题时用 5800 K**（因为那是从题目给的 500 nm 算出来的）。

### 4.9 太阳常数会变（回扣 Week 2）

> "We know that that constant varies slightly from last week. **We know that that varies over an 11-year cycle.** But for the purposes of today, we can think of that as a fixed value."

**"solar constant" 名不副实**——它随 11 年太阳活动周期变化。本课把它当常数处理是简化。这一句把 Week 2 的太阳变率和 Week 3 的能量收支缝合了起来。

### 4.10 ★ 半径会约掉（讲师专门强调的解题步骤）

见 §3.5 第五步的引文。这是**解题的关键洞察**，也是判断学生是否真的理解了这个公式的分水岭：

- **不理解的学生**：看到题目给了半径，就想办法把半径用上去，结果推导变复杂甚至算错。
- **理解的学生**：看出 πr_e² 会被约掉，直接跳到 T_e = [(1−α)S₀/(4σ)]^(1/4)。

**答案 deck 给出的火星半径 3389.5 km 和金星半径 6052 km 都是干扰项。**

### 4.11 ★ 明示的考试重点

> "that 255 Kelvin, if you didn't [get it], don't worry, all of this working will be uploaded afterwards, but **please do work through that because that's going to be important to understand, particularly the mid-semester test.**"

**这是本周唯一一处直接点名考试的地方，指向的是黑体平衡温度计算。** Week 6（10 March）的 Mid Unit Test 占 30%。

### 4.12 行星实测温度（讲义未给，转写给了）

> "you know the average surface temperature of the Earth roughly, and **the average surface temperature of Mars is 218 Kelvin, and the average temperature of Venus is 735 Kelvin**."

这两个数字是做"计算值 vs 实测值"对比的前提。答案 deck 只在备注里提了火星的 218 K，**金星的 735 K 只出现在转写里**。

⚠️ 讲师在讲评时口误说"the actual temperature of Mars is 216 and that means it has a greenhouse gas effect of around two degrees"——**216 是计算值，218 才是实测值**。答案 deck 的备注写对了。已登记勘误。

### 4.13 课堂互动记录

转写里保留了几处课堂问答的痕迹，虽然听不到学生的回答，但讲师的反应说明了什么是"对的答案"：

- 算出地球 255 K 后："**Did anyone get anywhere near that? A few nods here and there.** Okay, perfect."
- 算出火星 216 K 后："**Did anyone get that? Yeah, great.**"
- 问为什么金星差这么多："**Any guesses why? Perfect. Great.**" —— 随后他自己给出的收口是："that points well done to the answer being **the way that planets deal with incoming solar radiation versus outgoing radiation**"

**最后这句就是标准答案的核心措辞**：差异在于**行星如何处理入射辐射与出射辐射之间的不对称**，而不是笼统的"金星大气厚"。

### 4.14 两个大气窗口 + "眼睛为什么长成这样"

见 §2.16 的完整引文。要点重述：
- 窗口有**两个**：可见光窗口 + **红外大气窗口（infrared atmospheric window）在 10 μm**
- **"That's why our eyes are tuned to see this wavelength"** —— 讲义完全没有这句，但它把物理和生物连了起来，是本周最有记忆点的一句话

### 4.15 水汽 vs 长寿命温室气体：物理重要性 ≠ 政策关注度

> "you'll notice that **water vapour is also an important absorber across many bands in the infrared. But because we're actively influencing carbon dioxide, ozone, methane and nitrous oxide, these are the focus of our interests** from a global climate change perspective."

这个区分讲义上完全没有，但它是回答"既然水汽才是最强的温室气体，为什么大家只盯着 CO₂"这类质疑（这类质疑在气候怀疑论里很常见）的关键。

### 4.16 臭氧的双重角色

> "**Ozone acts to reduce the UV radiation.** Incoming solar radiation is obviously a good thing. **But it also, in the troposphere, acts as a greenhouse gas because it also interacts with outgoing infrared radiation.**"

**平流层臭氧 = 好（挡 UV）；对流层臭氧 = 温室气体 + 空气污染物（伤肺、伤作物）。** 这是 Q5 的题眼，也与 Slide 42 里"减甲烷可降低近地面臭氧"呼应。

### 4.17 出射辐射只有一小部分能逃逸

> "**lots and lots of the outgoing infrared radiation is absorbed** by different molecules and gases within the atmosphere. **Which means only a small amount of outgoing radiation ever makes it out to space.** And that ultimately leads to a warming because that outgoing infrared radiation is **re-radiated, some of which goes back to the surface** of the planet and leads to warming."

配合"70–75% 的入射太阳辐射透过"，构成了完整的不对称图景。

### 4.18 航运燃油硫含量立法（时事引用，Q4 的现实背景）

> "we're going to sort of develop those ideas through the workshop and through **some recent changes in maritime legislation, which has changed sulfur content of fuel. So I'm interested in understanding what impact that has had on our climate.**"

这是本周唯一的**时事引用**，也是 Q4 的出题背景。讲义 Slide 54 的题干写的是"Recently new legislation was passed to reduce SO₂ emissions from shipping"。

📎 背景补充（材料没给具体法规名称与年份，此处仅给出机制层面的说明，具体法规细节我不确定，故不写）：船舶燃油中的硫在燃烧后生成 SO₂，SO₂ 在大气中氧化生成**硫酸盐气溶胶**，这些气溶胶既直接散射阳光，又作为**云凝结核**让海洋上空的低云变亮（这就是卫星图上能看到的"**船舶航迹云 ship tracks**"）。降低燃油硫含量会同时削弱这两条降温路径。这个机制正是 Q4 想让你论证的东西。

### 4.19 气溶胶健康效应的具体终点

> "In almost every organ of the body in which the effects of aerosols have been studied, detrimental effects have been seen. And that's all the way down to things like **preterm birth, birth weights and adverse birth outcomes**."

讲义 Slide 47 只写了 "disease in every organ where it has been studied"，**具体到妊娠结局这一层是转写独有的**。

### 4.20 后续周次的口头预告（与讲义周历不一致）

讲师在课上两次提到 Week 8：

> "The sources of this greenhouse gas we will think about a little bit more in **week eight where we look at mitigations**."
> "when we look at the case study examples, I think in **week eight**, we will focus our attention to the agricultural settings"

⚠️ 但讲义 Slide 2 的周历是：**Week 8 = Climate change adaptation，Week 9 = Effects of Climate Change: Case Studies，Week 10 = Climate change mitigation**。讲师口头说的"week eight"与讲义标注不符（他自己也说了 "I think in week eight"，语气不确定）。**以讲义周历为准。** 已登记勘误。

### 4.21 课堂节奏与 workshop 安排

- Workshop 1 给了 **10 分钟**（"I'm going to give you until 22"，即到整点后 22 分）
- 答案会在课后上传 Canvas："I'm going to upload the answers as normal to the Canvas site following the lecture"
- 课后半段的 full workshop（Q1–Q9）：讲师说答案会在**课程结束时**上传，并会**逐个走动答疑**："I'll be delighted to come around and have a chat with anyone about the questions individually as well."

### 4.22 转写中的自动识别讹误清单

本周转写的 ASR 质量在专有名词上明显下降，以下讹误已全部识别，正文阅读时请自行还原（也已登记进勘误表）：

| 转写文字 | 应为 |
|---|---|
| "Mankovitch cycles" | **Milankovitch cycles** |
| "**Green's law**" / "**Venus law**" / "**Boone's law**" | **Wien's law**（三处不同的误识，都是维恩定律） |
| "**Steppen-Voltzmann** law" | **Stefan–Boltzmann law** |
| "**theta** is the Stefan-Boltzmann constant" | **sigma（σ）** |
| "wavelength around the size of **atomic energy**" | **atomic nuclei**（原子核） |
| "move between the **five** energy states" | 不同能级（"five" 疑为误识） |
| "the **diameter** of the Earth, which is of course pi r squared" | 应为**半径**决定的**截面圆盘** |
| "from the N2O and **EPA** perspective" | 疑为 **CH₄**（上下文在讲三种温室气体） |
| "answers **1 to 8**" | 应为 Q1a–Q1c（本周 workshop 只有三小问） |

**特别提醒**：由于"Wien's law"在转写里被识别成了三个不同的错名，如果你直接用关键词搜索转写找维恩定律的段落，会搜不到。

---

## 五、Practical 要点

本周有**两组** workshop：课中的 **Workshop 1**（计算题）和课后的 **Full workshop / Q&A**（Q1–Q9，讨论题）。

### 5.1 Workshop 1：行星黑体平衡温度计算

讲师的题目布置（转写）：

> "what I would like you to do is **calculate the blackbody equilibrium temperature of Earth** with the information that I've just given you. We can then use the same principle to look at other planets, and we will look at the **blackbody surface temperature of Mars and Venus**. Using some of the information that I give you at the bottom of the slides, you know the average surface temperature of the Earth roughly, and the average surface temperature of **Mars is 218 Kelvin**, and the average temperature of **Venus is 735 Kelvin**. So I want you to **start to think about why you might get differences in your answers ... to the measured values that I've given you**."

⚠️ 讲义 deck 的 Slide 29 只有 "Workshop 1" 四个字，**题干本身是图片，未提取出文字**。以下题干根据答案 deck 与转写还原。

---

#### **Q1a. 计算地球的黑体平衡温度**

**已知条件**：S₀ = 1370 W m⁻²，α = 0.30，r_e = 6370 km，σ = 5.67 × 10⁻⁸ W m⁻² K⁻⁴

**答案 deck Slide 3 的完整解答（原文照录）：**

> - In steady state the **energy entering top of atmosphere = energy leaving the atmosphere**
> - So × Area (A) × albedo = T_E⁴ × 4πr_e²
> - 0.7 × 1370 × πr_e² = T_e⁴ × 4πr_e²
> - (0.7 × 1370) / 4σ = T_e⁴
> - T_e = [(0.7 × 1370) / 4σ]^(1/4) = [((1−a) × S) / (4σ)]^(1/4)
> - **T_e = 255 K (−18 °C) is the equivalent blackbody temperature of the Earth**

**解题路径（五步）：**

1. **写稳态条件**："energy in = energy out"。**这是第一步也是最关键的一步**，讲师原话："the thing that you needed to do first was to **establish that the energy entering the top of the atmosphere somewhat equals the energy leaving the atmosphere**"。
2. **写出两侧表达式**：进 = (1−α)S₀·πr_e²；出 = σT_e⁴·4πr_e²
3. **约掉 πr_e²**（讲师专门强调，见 §4.10）
4. **整理成 T_e⁴ = (1−α)S₀/(4σ)**
5. **开四次方**（= 连开两次平方根）→ **255 K**，并换算成 **−18 °C**

**判分要点：**
- ✅ 必须**明确写出稳态假设**（能量进 = 能量出）——这是概念分
- ✅ 收入项必须用 **πr²**（截面），支出项必须用 **4πr²**（表面积）——这是本题真正的考点
- ✅ 必须是 **(1 − α)**，不是 α
- ✅ 必须有 **σ**
- ✅ 应说明**半径约掉**（体现理解）
- ✅ 应给出**摄氏度换算**（255 K = −18 °C），讲师特意提了："Hopefully you also realize that that 255 Kelvin is around minus 18 degrees C"
- ❌ 常见失分：用 4πr² 算收入项（会得到 T = 180.4 K）；用 α = 0.3 而非 0.7；忘了开四次方

---

#### **Q1b. 估计火星的表面温度**

**已知（答案 deck Slide 4 原文）**：
- Radius = 3,389.5 km
- Solar constant = 590 W m⁻²
- Albedo = 0.16

**答案 deck 解答（原文照录）：**

> - So × Area (A) × albedo = T_E⁴ × 4πr_e²
> - T = (((1 − albedo) × solar constant) / (4σ))^(1/4)
> - = ((0.84 × 590) / (4 × 5.67 × 10⁻⁸))^(1/4)
> - **= 216.2 K**

**逐步核算：** 0.84 × 590 = 495.6 → 495.6 / (2.268 × 10⁻⁷) = 2.185 × 10⁹ → 开四次方 = **216.2 K** ✓

**判分要点：**
- ✅ **半径 3389.5 km 是干扰项，不该出现在计算中**
- ✅ 注意火星反照率只有 0.16（比地球低）——火星表面是暗红色的岩石与尘埃，反射得少
- ✅ 火星虽然反照率低（吸收比例高达 84%），但太阳常数只有地球的 43%，净效果是更冷

---

#### **Q1c. 估计金星的表面温度**

**已知（答案 deck Slide 5 原文）**：
- Radius = 6052 km
- Solar constant = 2637 W m⁻²
- Albedo = 0.75

**答案 deck 解答：**

> - T = (((1 − albedo) × solar constant) / (4σ))^(1/4)
> - = ((0.25 × 2637) / (4 × 5.67 × 10⁻⁸))^(1/4)
> - **= 232 K**

**逐步核算：** 0.25 × 2637 = 659.25 → 659.25 / (2.268 × 10⁻⁷) = 2.907 × 10⁹ → 开四次方 = **232.2 K** ✓

**这题的教学价值（也是最容易被答错的地方）：**

金星的太阳常数是地球的 **1.9 倍**，但算出来的平衡温度 **232 K < 地球的 255 K**。原因是它的**反照率高达 0.75**——被浓密的硫酸云层反射掉了四分之三的阳光。

讲师确认了这个大小关系：

> "hopefully you then got the same answer. It's just a rinse and repeat with **Venus being slightly warmer than that of Mars, but cooler than that of Earth**."

**排序要记住：火星 216 K < 金星 232 K < 地球 255 K（计算值）**，而**实测值的排序完全颠倒：火星 218 K < 地球 288 K < 金星 735 K**。这个"排序翻转"就是温室效应威力的最好证明。

---

#### **Q1 讨论部分：为什么计算值与实测值有差异？**

**答案 deck Slide 6 / 7 的解答（原文照录，含材料本身的语法残缺）：**

Slide 6：
> - Temperature Ts = (Net Solar Flux/(4 × Stefan-Boltzmann Constant))^0.25
> - **Mars Atmosphere has a Greenhouse Effect of 2°**
> - Mars atmosphere is very thin, approx. pressure is (approx. 6 mb) than Earth's (1000 mb)
> - However, **95% of its atmosphere is CO2, about 16 times the amount CO2 in our atmosphere.**
>
> **备注栏**："actual temperature of Mars as measured is **218 K**, whereas the calculated temperature is **216**. That means it has a greenhouse effect of **2 degrees**. Its atmosphere is very thin but has about 16 times the CO2 in our atmosphere. **Venus on the other hand has 92 times our atmospheric density, mostly CO2, and is a raging inferno.** 1000 mb = 100000 Pascals"

Slide 7：
> - Actual temperature of Mars as measured is **218 K**, whereas the calculated temperature is **216**.
> - That means it has a **greenhouse effect of 2 degrees**.
> - Its atmosphere is very thin but has about **16 times the CO2** in our atmosphere.
> - **Venus on the other hand has 92 times our atmospheric density, mostly CO2, and is a hothouse!**

**讲师的口头讲评：**

> "the calculated temperature, just using the blackbody equations, you can see for **Mars is somewhat similar. So 216 Kelvin, you should have calculated compared to the 218, that is the measured surface temperature of Mars.**
> We know that **we're not sitting in minus 18 degrees on the Earth** and there's a **huge difference between the actual average temperature of Venus compared to what you have calculated**. Any guesses why? ...
> The atmosphere of Mars is very thin, that is 16 times the amount of carbon dioxide compared to our atmosphere. But then if you compare that to **Venus, which has 92 times our atmospheric density and is predominantly made up of CO2**, that points ... to the answer being **the way that planets deal with incoming solar radiation versus outgoing radiation**."

**完整答案应包含的三层：**

1. **差值的定义**：实测温度 − 计算的黑体温度 = **温室效应的强度**。
   - 火星：218 − 216 = **2 K**
   - 地球：288 − 255 = **33 K**
   - 金星：735 − 232 = **约 503 K**
2. **差值大小的解释**：黑体公式**完全不含大气**，所以任何差异都必须归因于大气对长波辐射的处理。
3. **为什么三颗行星差这么多**：
   - **火星**：大气极薄（约 **6 mb**，地球是 **1000 mb**），虽然 95% 是 CO₂ 且 CO₂ 总量约为地球的 16 倍，但柱量与压强都不足以形成强吸收 → 只有 2 K
   - **地球**：中等大气量，微量但有效的温室气体（CO₂、H₂O）→ 33 K
   - **金星**：大气密度是地球的 **92 倍**且几乎全是 CO₂ → 巨大的红外不透明度 → 500 K 以上，成为"hothouse"

⚠️ 答案 deck Slide 6 第三条句子残缺："approx. pressure is (approx. 6 mb) than Earth's (1000 mb)" ——中间漏了 "much lower"（"压强约为 6 mb，**远低于**地球的 1000 mb"）。已登记勘误。

⚠️ 单位换算：答案 deck 备注给了 **1000 mb = 100 000 Pa**，这个换算是正确的（1 mb = 1 hPa = 100 Pa）。

---

### 5.2 Full workshop（Q&A deck，Q1–Q9）

讲义 deck 的 Slide 50–59 是问题，答案 deck 的 Slide 8–26 是问答对照。

⚠️ **重要提示：Q4 的"答案"页只是把题目又重复了一遍，没有实质答案；Q7、Q8、Q9 在两份 deck 里都完全空白（没有题干也没有答案）。** 讲师在课上说"I will upload the answers to the workshop at the end of the class"，所以这些内容很可能在课后单独上传，本笔记范围内的材料里没有。已登记勘误。

---

#### **Q1. What is meant by climate change?**（什么叫气候变化？）

**答案 deck Slide 10 原文：**

> - **Weather** is what is happening in the atmosphere **at any one time**: how warm, windy, sunny or humid it is.
> - **Climate** is the description of the **average weather** we might expect at a given time, **usually taken over a 30 year period** to average out year to year variability perhaps due to a particularly hot summer or very cold winter, and it **also includes information about variability** (e.g. what the usual difference is between hot years and cold years) **and extremes** (e.g. how often an extremely hot day happens).
> - **If the climate is changing, then the 30-year average temperature, or rainfall, etc, is changing.**

**解题路径与判分要点：**

这题的正确打开方式是**先定义天气、再定义气候、最后定义气候变化**——三段式。

- ✅ **天气 = 某一时刻大气的状态**（瞬时）
- ✅ **气候 = 平均的天气**，标准平均期是 **30 年**
- ✅ **关键加分点：气候不只是"平均值"，还包括"变率（variability）"和"极端事件（extremes）"** —— 很多学生只答平均值就止步了，这会丢分。这一点在讨论"气候变化会不会让极端天气更频繁"时至关重要。
- ✅ **气候变化 = 那个 30 年统计量本身在变**
- ❌ 常见失分：把气候变化答成"变暖"（气候变化包括降水、变率、极端等多个维度，不只是温度）

📎 背景补充：30 年这个标准来自 WMO（世界气象组织）的"climate normal"定义，目前使用的标准期是 1991–2020。用 30 年是因为它足够长到能平滑掉 ENSO（约 3–7 年）等年际变率，又足够短到能反映"当前"气候。这个来源材料没给。

---

#### **Q2. Discuss and provide examples of aerosol impacts on air quality and health.**（讨论并举例说明气溶胶对空气质量与健康的影响）

**答案 deck Slide 12 原文：**

> **Air Quality**
> Aerosols contribute significantly to air pollution by **increasing the concentration of particulate matter** in the atmosphere. These particles originate from sources such as **vehicle emissions, industrial activities, and biomass burning**. When aerosol levels rise, **visibility decreases**, and overall air quality deteriorates.
>
> **Health**
> Inhalation of aerosol particles can cause or exacerbate a range of **respiratory problems, including asthma, bronchitis, and other chronic lung conditions**. **The smallest particles can penetrate deep into the lungs and enter the bloodstream**, contributing to **cardiovascular issues such as heart attacks**. Prolonged exposure to high concentrations of particulate matter has also been associated with an increased risk of **lung cancer and premature mortality**. **Vulnerable groups, such as children and the elderly**, are especially susceptible.

**答题结构（这题是标准的"两栏式"讨论题）：**

| 维度 | 要点 | 具体例子 |
|---|---|---|
| **空气质量** | 提高 PM 浓度、降低能见度 | 车辆排放、工业活动、生物质燃烧 |
| **健康（呼吸系统）** | 引发/加重呼吸道疾病 | 哮喘、支气管炎、慢性肺病 |
| **健康（心血管）** | 最小的颗粒可深入肺部并**进入血液** | 心脏病发作 |
| **健康（长期）** | 长期暴露的累积效应 | 肺癌、过早死亡 |
| **易感人群** | — | 儿童、老人 |

**判分要点：**
- ✅ 必须**分开谈空气质量和健康**（题目明确要求两者）
- ✅ 必须**举具体例子**（题目说 "provide examples"）——只给机制不给例子会丢分
- ✅ **"penetrate deep into the lungs and enter the bloodstream"** 是解释"为什么 PM2.5 比 PM10 更危险"的关键机制，应写出
- ✅ 加分项：加上讲师口头提到的 **preterm birth、birth weight、adverse birth outcomes**（答案 deck 没有，转写有），以及"disease in every organ where it has been studied"这句强表述

---

#### **Q3. ★ 为什么减少颗粒物会带来空气质量效益却造成气候上的"负效益"？**

**题干（答案 deck Slide 13 原文）：**

> Atmospheric particles (aerosols) such as **sulfate, nitrate, organic carbon, and black carbon** are a major component of air pollution and are linked to adverse human health outcomes. As a result, air-quality regulations around the world aim to reduce particle concentrations, particularly **PM2.5**. **Why might reducing atmospheric particle concentrations lead to clear air-quality benefits but also create climate disbenefits? What effects might this have on the climate system?**

**答案 deck Slide 14 原文（完整照录，这是本周最长也最重要的一份答案）：**

> - Many aerosols also play an important role in the climate system. Particles such as **sulfate scatter incoming shortwave solar radiation and increase cloud reflectivity, producing a net cooling effect** on the climate. This represents a **negative radiative forcing that partially offsets the warming caused by long-lived greenhouse gases** such as carbon dioxide as is shown in the figure to the right.
> - When aerosol concentrations are reduced, **this cooling effect is weakened**. As a result, **more solar radiation reaches the Earth's surface, leading to a positive change in the radiation balance and an increase in surface temperature**. This warming can occur **relatively quickly because aerosols have short atmospheric lifetimes (days to weeks)**, meaning the climate system responds rapidly once emissions are reduced.
> - This creates a climate "disbenefit" in the short term: although air quality improves, **the removal of aerosols reveals previously masked greenhouse-gas-driven warming**.
> - Overall, this example highlights the complex relationship between air-quality policy and climate change. While aerosol reductions are essential for protecting human health, **they need to be accompanied by rapid reductions in greenhouse gas emissions to avoid additional warming**.

**解题路径（四步论证链，必须全部走完）：**

1. **气溶胶的气候作用是降温的**，通过**两条机制**：
   - **直接**：硫酸盐等散射入射短波
   - **间接**：提高云的反射率（作为云凝结核）
   → 合计构成**负辐射强迫**
2. **这个降温"部分抵消"了温室气体的增温** → 即所谓"**掩盖（masking）**"
3. **减少气溶胶 = 撤掉这层掩盖** → 更多太阳辐射到达地表 → 辐射平衡正向变化 → 地表升温
4. **时间尺度不对称是关键**：气溶胶**寿命只有几天到几周**，所以**一旦减排，气候系统反应很快**；而 CO₂ 的寿命是数百年，已经排出去的还在那里 → **短期内净效果是加速升温**

**判分要点：**
- ✅ **"negative radiative forcing"** 和 **"masked warming"** 是这题的两个关键术语，必须出现
- ✅ 必须提到**两条降温机制**（直接散射 + 间接的云反射率），只提一条不完整
- ✅ **必须提到寿命的对比（气溶胶天到周 vs 温室气体数百年）**——这是解释"为什么反应这么快"的核心，也是最容易漏的一点
- ✅ 结论必须是**平衡的**：不能因此说"所以不该减少气溶胶"。答案明确写了 "While aerosol reductions are **essential** for protecting human health, they **need to be accompanied by** rapid reductions in greenhouse gas emissions"
- ❌ 常见失分：把"气溶胶降温"说成"气溶胶是好的"；忽略了这是一个**政策两难**而非**科学争议**

**讲师的口头对应（转写）：**

> "So from a health perspective, reducing aerosol concentrations is fantastic. But also aerosols, as you know, play a key part in radiative forcing. So **they are offsetting some of the warming** we are seeing from the increased carbon dioxide, methane and N2O concentrations. So there's some discussions there about having an **air quality benefit, but a potential climate disadvantage**."

---

#### **Q4. 航运 SO₂ 减排立法的影响与意外后果**

**题干（讲义 Slide 54 / 答案 deck Slide 15 原文）：**

> Sulfate aerosols originates from **atmospheric oxidation of SO2**. This is a global picture of SO2 emissions. Recently new legislation was passed to **reduce SO2 emissions from shipping**.
> **What impact might this have? What could the unintended consequences of this be? Is it worth improving air quality over the ocean?**

⚠️ **答案 deck Slide 16 只是把题目重复了一遍，没有给出答案。** 这是本周材料的一处明确缺失（已登记勘误）。讲师说答案会在课后单独上传。

**因此以下为解题思路，来自转写中讲师的引导 + Q3 的可迁移逻辑。凡是超出材料的部分我都打了标记。**

**转写中讲师给的唯一线索：**

> "we're going to sort of develop those ideas through the workshop and through **some recent changes in maritime legislation, which has changed sulfur content of fuel. So I'm interested in understanding what impact that has had on our climate.**"

**建议的答题框架：**

1. **直接影响（空气质量）**：船舶燃油含硫量下降 → SO₂ 排放下降 → 大气氧化生成的硫酸盐气溶胶减少 → 沿海与港口地区 PM2.5 下降 → 健康效益。
2. **意外后果（气候）**：套用 Q3 的逻辑链——硫酸盐减少 → 直接散射与云反射率增强效应双双减弱 → 负辐射强迫减小 → **净增温**。
3. **为什么海洋上空的效应可能特别大（📎 我的补充，材料未给）**：海洋背景大气本来非常清洁，气溶胶浓度低，因此**新增一个云凝结核对云反射率的边际效应特别大**（云滴数量对 CCN 的响应在低浓度时最敏感）。这意味着**在洁净的海洋上空移除硫酸盐，其增温效应可能比在已经很脏的陆地上空移除同样多的硫酸盐更强**。
4. **"是否值得"的权衡（这是一道开放的评价题，要给出双方论据）**：
   - **支持**：健康效益是确定的、即时的；SO₂ 也造成酸雨；港口城市人口密集，暴露人数多。
   - **保留**：海洋上空人口稀少，直接健康收益相对小；而气候代价是全球性的、长期的。
   - **📎 我的建议立场（不是材料立场）**：正确的答法不是"该"或"不该"，而是指出**这道题暴露的是"用污染物掩盖变暖"本身就是不可持续的策略**——掩盖迟早要撤，撤得越晚欠账越多。真正的解法是同步、快速地削减温室气体，而不是维持污染。这与 Q3 答案的收尾逻辑完全一致。

---

#### **Q5. 臭氧的 UV 与 IR 吸收各有什么环境效应？如果臭氧的 IR 吸收带不存在，气候会有何不同？**

**题干（答案 deck Slide 17 原文）：**

> Ozone absorbs both UV and IR radiation. **What is the effect on the environment of each? How would the climate differ if the IR absorption band of ozone didn't exist?**

**答案 deck Slide 18 原文：**

> - **Ozone protects life by absorbing harmful UV radiation in the stratosphere** and **warms the atmosphere by absorbing outgoing IR radiation**. This dual role helps maintain the planet's temperature balance.
> - **Without IR absorption at ~9600 nm, less heat would be trapped, leading to a cooler atmosphere and surface. The greenhouse effect would weaken, lowering global temperatures.**

**解题路径：**

这题是一道**"分解 + 反事实推理"**题，必须分两步：

**第一步：分别说清两种吸收的效应**

| 吸收的辐射 | 发生位置 | 环境效应 |
|---|---|---|
| **UV** | 主要在**平流层** | **保护生命**——阻挡有害紫外线到达地表 |
| **IR（红外）** | — | **加热大气**——作为温室气体截留出射长波 |

**第二步：反事实推理——如果 IR 吸收带不存在**

- 更少的热量被截留 → 大气与地表更冷
- 温室效应减弱 → 全球温度下降

**关键数值：臭氧的红外吸收带在 ~9600 nm = 9.6 μm。**

**这个数值为什么重要（这是本题真正的深层考点，答案 deck 没有明说，但值得理解）：**

9.6 μm **正好落在 8–13 μm 的红外大气窗口的中间**（§2.16）。也就是说，臭氧的吸收带**恰好堵住了地球散热效率最高的那扇窗**。在窗口内增加吸收，对温室效应的**边际影响远大于**在已经饱和的波段（比如 CO₂ 的 15 μm 中心）增加吸收。这解释了为什么一条不起眼的吸收带值得单独出一道题。

**判分要点：**
- ✅ 必须**明确区分平流层 UV 吸收（保护性）与 IR 吸收（温室性）**——这两个是完全不同的物理与不同的高度
- ✅ 必须回答**反事实问题**（"没有 IR 带会怎样"），答"变冷"并说明机制（截留的热量减少 → 温室效应减弱）
- ✅ 加分项：指出 9.6 μm 落在大气窗口内，因此该吸收带的效力被放大
- ✅ 加分项（来自转写）：讲师强调**对流层臭氧才是那个作为温室气体的臭氧**，而**平流层臭氧是保护性的**——臭氧"在哪一层"决定了它是好是坏

---

#### **Q6. 能否用下图估计太阳的表面温度？**

**题干（讲义 Slide 56 / 答案 deck Slide 19）：**

> Can you use the graph below to estimate the surface temperature of the sun?

（图未在 deck 中提取出内容，但从答案可知：图上要读出的是太阳辐射谱的**峰值波长 = 500 nm**。）

**答案 deck Slide 20 原文：**

> **Wien's Law:**
> λmax × T = 2.897 × 10⁶
> T = 2.897 × 10⁶ / 500 nm
> **T = 5800 K**

**解题路径（三步）：**

1. **从图上读出峰值波长**：找曲线的最高点，读它对应的 x 坐标 → **500 nm**
2. **认出该用维恩定律**（题目问的是"温度"，给的是"谱"，而联系谱形与温度的就是维恩定律）
3. **代入并注意单位**：T = 2.897 × 10⁶ (nm·K) / 500 (nm) = **5794 K ≈ 5800 K**

**判分要点：**
- ✅ **必须说明是从图上读峰值波长**，并给出读数
- ✅ **必须点名维恩定律**并写出公式
- ✅ **单位必须自洽**：常数 2.897 × 10⁶ 对应波长以 **nm** 为单位。如果把 500 nm 换成 0.5 μm 却仍用 2.897 × 10⁶，会得到 5.8 × 10⁶ K，错了三个数量级。**这是本题唯一的陷阱。**
- ✅ 答案取整到 5800 K 是合适的（图上读数本来就只有一两位有效数字）
- ❌ 常见失分：误用斯特藩–玻尔兹曼定律（那需要知道通量，图上给的是谱形）

**与讲师口述的印证**：他说太阳表面温度"anywhere between 5,800 Kelvin to 6,000 Kelvin"——5800 K 落在范围内，互相印证。

---

#### **Q7 / Q8 / Q9**

⚠️ 讲义 deck 的 Slide 57、58、59 和答案 deck 的 Slide 21–26 **只有标题（"Q7."、"Q7. Answer" 等），没有任何题干或答案文字**。Slide 58 的备注栏只有一个孤立的左括号 "("。这些内容在本笔记可用的材料中**完全缺失**，无法还原。已登记勘误。

**建议行动**：讲师说过 "I will upload the answers to the workshop at the end of the class"，请到 Canvas 上查看课后单独上传的完整答案版本。

---

## 六、易错点·重点难点

### 6.1 单位与量级陷阱（本周最集中的失分来源）

| # | 陷阱 | 说明 |
|---|---|---|
| 1 | **温度必须用 K，不能用 °C** | σT⁴ 里代入 15 而不是 288，答案会完全崩掉。所有辐射公式（S-B、Wien）**只接受绝对温度**。 |
| 2 | **维恩常数与波长单位绑定** | 2.897 × 10⁶ 对应 **nm**；用 μm 要换成 2897；用 m 要换成 2.897 × 10⁻³。**错一个就差 10³**。 |
| 3 | **"10 m" 其实是 "10 μm"** | 讲义 Slide 18、19 因字符丢失把 μm 写成了 m。10 m 是无线电波，10 μm 才是热红外。 |
| 4 | **W m⁻² 被写成 W m2** | 讲义多处上标丢失（S₀=1370 W m2、σ=5.67 x 10-8）。写答案时必须补回正确的上标。 |
| 5 | **CH₄ 浓度差一个数量级** | 讲义 Slide 40 写 0.0018%（= 18 ppm），实际约 1.9 ppm（= 0.00019%）。 |
| 6 | **CO₂ 浓度已过时** | 讲义写 0.03%（300 ppm），现值超过 0.042%（420 ppm）。 |
| 7 | **开四次方 ≠ 除以 4** | T_e⁴ = 4.23 × 10⁹ → T_e = 255，不是 1.06 × 10⁹。用计算器连开两次平方根最稳妥。 |
| 8 | **1000 mb = 100 000 Pa** | 答案 deck 特意在备注里给了这个换算，说明它是个已知的易错点。1 mb = 1 hPa = 100 Pa。 |

### 6.2 ★ 因子 4：收入用 πr²、支出用 4πr²

**这是本周最核心的一个"为什么"，也是最容易被当成公式硬背的地方。**

| | 面积 | 为什么 |
|---|---|---|
| 收入（短波） | **πr²** | 太阳光是**平行光**，只能被行星在垂直方向上的**投影圆盘**截住 |
| 支出（长波） | **4πr²** | 行星向**所有方向**辐射，用的是**整个球面** |

**记忆锚点**：**"接收的是一个圆，发射的是一个球"**。两者之比是 4（球面积 / 圆面积 = 4πr²/πr² = 4）。

**这个 4 最终出现在 T_e = [(1−α)S₀/(4σ)]^(1/4) 的分母里。** 如果漏掉它：
- 若两边都用 4πr²，得 T_e = [(1−α)S₀/σ]^(1/4) = **360.5 K**（严重偏高）
- 若两边都用 πr²，同上
- 若收入用 4πr²、支出用 πr²，得 **510 K**（离谱）

### 6.3 ★ (1 − α) 而不是 α

讲义 Slide 26 与答案 deck Slide 3 的**文字标注写的是 "× albedo"**，但算式里用的是 **0.7**。**0.7 = 1 − 0.3 = 1 − α，是"被吸收的比例"，不是反照率。**

**理解方式**：α 是**反射掉**的比例（浪费掉的），(1 − α) 才是**被行星吸收**的比例（能加热行星的）。

**转写里讲师说对了**："we times the one minus the albedo"。**以此为准。**

### 6.4 ★ 三个温度不要混：T_e、T_surface、以及"实测 vs 计算"

本周有三个温度反复出现，讲义还在 Slide 18 上把符号用混了：

| 符号/说法 | 数值（地球） | 含义 |
|---|---|---|
| **T_e**（equivalent blackbody temperature / effective temperature） | **255 K = −18 °C** | **计算得到的**，假设无温室效应时的平衡温度 |
| **实测全球平均地表温度** | **288 K = +15 °C** | **观测得到的**，我们实际生活的温度 |
| **ΔT = 温室效应** | **33 K** | 两者之差 |

⚠️ 讲义 Slide 18 用 "Te = 288 K" 指代实测地表温度，与其他地方的 Te = 255 K 冲突。**答题时请用 T_e 表示 255 K，用 T_s 或 T_surface 表示 288 K。**

📎 我的建议记法：**T_e 的 e 记成 "effective/equilibrium（有效/平衡）"，它是算出来的；T_s 的 s 记成 "surface（地表）"，它是测出来的。**

### 6.5 ★ 概念混淆：为什么行星大小无关

很多人第一次看到这个推导会觉得"半径肯定有影响"。**它确实完全没有影响**，因为：

> 半径越大 → 接收的能量越多（∝ r²），**但**辐射的面积也越大（∝ r²）→ **两者比例不变** → 平衡温度不变

**推论**：任何和地球在同一轨道、同一反照率的行星，无论多大多小，平衡温度都是 255 K。

**答题时要主动指出半径被约掉**——这体现你理解了物理而不是在套公式。答案 deck 给的三个半径值全都是干扰项。

### 6.6 ★ 反直觉结果：金星的黑体温度比地球低

| 行星 | S₀ | α | T_e | 直觉 vs 结果 |
|---|---|---|---|---|
| 金星 | **2637**（最高） | **0.75**（最高） | **232 K** | 离太阳最近却算得最冷 |
| 地球 | 1370 | 0.30 | **255 K** | 三者中最高 |
| 火星 | 590（最低） | 0.16（最低） | **216 K** | 最冷 |

**原因**：T_e 由 **(1−α)S₀** 这个**乘积**决定，不是由 S₀ 单独决定。金星虽然接收多，但反射掉了 75%。

**净吸收通量对比（📎 我算的）**：金星 0.25 × 2637 = 659 W m⁻²；地球 0.7 × 1370 = 959 W m⁻²。**地球实际净吸收的太阳能比金星还多。**

**而实测温度的排序完全翻转（火星 218 < 地球 288 < 金星 735）——这个翻转本身就是温室效应存在的最强证据。**

### 6.7 ★ 推理谬误：温室效应 = "大气把热挡住了"

这是最常见的错误表述。正确的机制必须包含**"向所有方向再辐射，其中向下的那部分回到地表"**这一步。

| ❌ 错误表述 | ✅ 正确表述 |
|---|---|
| "温室气体像毯子把热挡住" | 温室气体**吸收**出射长波，然后**向所有方向再发射**，其中**向下**的那部分被地表**吸收**，使地表比无大气时更暖 |
| "温室气体让热跑不出去" | 能量最终仍以长波形式逃逸到太空（否则地球会无限升温），只是**逃逸的有效高度更高、更冷**，导致地表必须更暖才能维持平衡 |
| "温室气体把太阳的热挡住了" | 温室气体**对太阳短波近乎透明**，它作用的是**地球发出的长波** |

**Slide 39 的六步版本（§2.20）是最安全的答题模板。**

### 6.8 ★ 概念混淆：温室气体的判定标准

| ❌ 错误判据 | ✅ 正确判据 |
|---|---|
| 浓度高的气体 | **在红外波段有强吸收带的气体** |
| 含碳的气体 | 同上（N₂O 不含碳但是强温室气体；O₂ 不是温室气体） |
| 污染物 | 同上（CO₂ 本身不是空气污染物，但是最重要的温室气体） |

**判据的物理来源**（📎 §2.17 的补充）：分子振动时必须能产生**偶极矩变化**。N₂、O₂ 是对称双原子分子，做不到，所以占大气 99% 却毫无温室效应。

### 6.9 概念混淆：辐射强迫的正负号

| 情形 | 强迫符号 | 温度趋势 |
|---|---|---|
| 温室气体增加 → 出射长波减少 | **正（positive）** | 变暖 |
| 硫酸盐气溶胶增加 → 反射更多短波 | **负（negative）** | 变冷 |
| 气溶胶**减少** → 反射变少 | **正向变化** | 变暖（这是 Q3 的题眼） |
| 反照率增加（如冰盖扩张） | **负** | 变冷 |

**记法：正强迫 = 系统净得到能量 = 变暖。**

**Q3 的特殊之处**：它问的是**"减少一个负强迫"**，等价于**施加一个正强迫**。双重否定容易绕晕，答题时明确写成"负强迫被削弱 → 净辐射平衡正向变化 → 升温"。

### 6.10 概念混淆：直接效应 vs 间接效应（气溶胶）

| | 机制 | 例子 |
|---|---|---|
| **直接效应** | 颗粒物**自身**散射或吸收辐射 | 硫酸盐散射（降温）、黑碳吸收（增温） |
| **间接效应** | 颗粒物作为**云凝结核**改变云的性质 | 云滴更多更小 → 云更亮 → 降温 |

讲师在开场说的 "the direct and indirect effect of aerosols"，以及答案 deck Q3 里的 "scatter incoming shortwave" + "increase cloud reflectivity"，对应的就是这两条。**Q3 答满分需要两条都提到。**

### 6.11 概念混淆：气候 vs 天气；平均值 vs 变率

Q1 的判分重点。**气候不只是"30 年平均"，还包括"变率"和"极端"。** 只答平均值会丢分。

### 6.12 时间尺度的不对称（Q3 与 Q4 的共同核心）

| 物质 | 大气寿命 | 减排后气候响应速度 |
|---|---|---|
| 气溶胶 | **几天到几周** | **几乎立即** |
| CH₄ | ~12 年 | 十几年尺度 |
| N₂O | ~120 年 | 世纪尺度 |
| CO₂ | **数百年（带长尾）** | 世纪到千年尺度 |

**这张表解释了 Q3 的全部张力**：减气溶胶的增温**马上兑现**，而减 CO₂ 的降温**要等几十年**。所以短期内"清洁空气 → 更快变暖"是真实的，也是必须同步大幅减温室气体的理由。

### 6.13 讲师明示的重点

1. **"particularly the mid-semester test"** —— 黑体平衡温度计算（Q1a/b/c）**明确会考**。
2. **"the size of the planets ... cancel each other out"** —— 半径约掉这一步讲师专门讲了。
3. **"there's almost no overlap"** —— 太阳谱与地球谱的分离，讲师在两张连续的幻灯片上重复强调了三次。
4. **"getting a handle on the cloud effects is vital"** —— 云对反照率的贡献（20%，占总量三分之二）。
5. **"the way that planets deal with incoming solar radiation versus outgoing radiation"** —— 这是行星温差问题的标准答案措辞。

### 6.14 材料自身的坑（答题时不要照抄）

| 材料里的写法 | 答题时应该写 |
|---|---|
| "× albedo = 0.7 × S₀" | **× (1 − α)** |
| "T_E⁴ × 4πr_e²" | **σT_E⁴ × 4πr_e²** |
| "Te = 288 K"（Slide 18） | **T_s = 288 K**（T_e 留给 255 K） |
| "peaks at about 10 m" | **10 μm** |
| "N 78%" | **N₂ 78%** |
| "CO₂ 0.03%" | 可写"约 0.04%（>420 ppm）"并注明讲义用的是旧值 |

---

## 七、本周术语表

| 英文 | 中文 | 一句话释义 |
|---|---|---|
| Electromagnetic radiation | 电磁辐射 | 以电磁波形式传播的能量，任何温度高于 0 K 的物体都会发射。 |
| Photon | 光子 | 电磁辐射的粒子，单个光子的能量 E = hf。 |
| Wavelength (λ) | 波长 | 相邻两个波峰（或波谷）之间的距离。 |
| Frequency (f, ν) | 频率 | 单位时间内通过某一点的波数，单位赫兹（Hz）。 |
| Hertz (Hz) | 赫兹 | 频率单位，等于每秒一个周期。 |
| Speed of light (c) | 光速 | 3.00 × 10⁸ m s⁻¹，所有电磁辐射在真空中的传播速度。 |
| Planck's constant (h) | 普朗克常数 | 6.626 × 10⁻³⁴ J s，把光子能量与其频率联系起来的物理常数。 |
| Electromagnetic spectrum | 电磁波谱 | 电磁辐射的完整波长范围，从无线电波到伽马射线。 |
| Gamma radiation | 伽马辐射 | 波长最短、能量最高的电磁辐射。 |
| Ultraviolet (UV) | 紫外线 | 波长短于可见光的辐射，约占太阳发射的 7%，几乎全被大气（主要是臭氧）吸收。 |
| Visible light | 可见光 | 约 400–700 nm，太阳发射的约 45%，也是大气的一个透明窗口。 |
| Infrared (IR) | 红外线 | 波长长于可见光的辐射，地球发射的主要波段。 |
| Shortwave radiation (SW) | 短波辐射 | 太阳发出的辐射，主体约 0.2–4 μm。 |
| Longwave radiation (LW) | 长波辐射 | 地球及大气发出的红外辐射，主体约 4–100 μm。 |
| Terrestrial radiation | 地面辐射 | 地球表面发出的长波红外辐射，"low temperature source"。 |
| Energy spectrum | 能量谱 | 辐射强度随波长的分布曲线。 |
| Radiation intensity | 辐射强度 | 单位面积单位时间的辐射能量。 |
| Black body | 黑体 | 吸收落在其上的**全部**辐射，并按其表面温度再发射的理想物体。 |
| Blackbody radiation | 黑体辐射 | 黑体发出的辐射，其谱形完全由温度决定。 |
| Radiation laws | 辐射定律 | 本周指斯特藩–玻尔兹曼定律与维恩定律两条。 |
| Stefan–Boltzmann Law | 斯特藩–玻尔兹曼定律 | I = σT⁴，温度越高发射越强（四次方关系）。 |
| Stefan–Boltzmann constant (σ) | 斯特藩–玻尔兹曼常数 | 5.67 × 10⁻⁸ W m⁻² K⁻⁴。 |
| Wien's Law | 维恩定律 | λmax × T = 2.897 × 10⁶ nm·K，温度越高峰值波长越短。 |
| Peak wavelength (λmax) | 峰值波长 | 一个物体发射能量最强的波长。 |
| Emissivity | 发射率 | 📎 实际物体发射能力与同温度黑体之比，黑体为 1（本课默认 ε = 1）。 |
| Planck function | 普朗克函数 | 📎 描述黑体谱形的解析函数，S-B 定律与 Wien 定律都是它的推论。 |
| Equivalent blackbody temperature (T_e) | 等效黑体温度 | 由能量平衡算出的、假设无温室效应时的行星温度；地球为 255 K。 |
| Effective temperature | 有效温度 | 同上的另一种叫法。 |
| Global mean surface temperature | 全球平均地表温度 | 地球实测的平均温度，约 288 K（+15 °C）。 |
| Energy balance | 能量平衡（能量收支） | 进入大气层顶的能量与离开地球的能量相等的状态。 |
| Steady state | 稳态 | 系统各量不随时间变化的状态，本周用作计算 T_e 的前提。 |
| Equilibrium | 平衡 | 能量输入与输出相抵的状态。 |
| Solar constant (S₀) | 太阳常数 | 日地平均距离处垂直于日光的单位面积接收功率，本课取 1370 W m⁻²。 |
| Albedo (α) | 反照率 | 被反射回去的入射辐射比例；地球约 0.30，暗表面接近 0，亮表面接近 1。 |
| Cross-sectional area (πr²) | 截面积 | 行星截取平行太阳光的迎光圆盘面积。 |
| Surface area (4πr²) | 表面积 | 球体的总表面积，行星向外辐射用的是这个面积。 |
| Greenhouse effect | 温室效应 | 大气吸收出射长波并向各方向再辐射，使地表温度高于黑体平衡温度的现象。 |
| Greenhouse gases (GHGs) | 温室气体 | 在红外波段强吸收的大气气体，如 H₂O、CO₂、CH₄、N₂O、O₃。 |
| Atmospheric window | 大气窗口 | 大气近乎透明的波段；本周指可见光窗口与 8–13 μm 的红外窗口。 |
| Infrared atmospheric window | 红外大气窗口 | 约 8–13 μm（讲师简称"10 微米"），地球长波逃逸到太空的主要通道。 |
| Absorption band | 吸收带 | 某种分子强烈吸收辐射的特定波长区间。 |
| Absorption | 吸收 | 分子获得光子能量、跃迁到更高能态的过程，ΔE = E_f − E_i = hν。 |
| Emission | 发射 | 分子从高能态落到低能态并放出光子的过程，ΔE = E_i − E_f = hν。 |
| Energy level / state | 能级 / 能态 | 分子可以处于的离散能量状态。 |
| Rotate / vibrate / stretch / bend | 转动 / 振动 / 伸缩 / 弯曲 | 红外辐射能激发的分子运动模式（能量不足以改变电子能级）。 |
| Dipole moment | 偶极矩 | 📎 分子正负电荷中心分离的量度；振动时偶极矩变化是红外吸收的必要条件。 |
| Radiative forcing | 辐射强迫 | 对流层顶净辐射通量的变化量（W m⁻²）；正为增温、负为降温。 |
| Positive radiative forcing | 正辐射强迫 | 系统净获得能量，趋向变暖；温室气体增加即属此类。 |
| Negative radiative forcing | 负辐射强迫 | 系统净损失能量，趋向变冷；散射性气溶胶即属此类。 |
| Tropopause | 对流层顶 | 对流层与平流层的分界面，辐射强迫的定义位置。 |
| Troposphere | 对流层 | 大气最底层，天气现象与大部分水汽所在的层。 |
| Stratosphere | 平流层 | 对流层之上的一层，臭氧层所在、UV 被吸收的地方。 |
| Net irradiance | 净辐照度 | 入射与出射辐射通量之差。 |
| Carbon dioxide (CO₂) | 二氧化碳 | 人为辐射强迫的主导贡献者，寿命数百年，主要来自化石燃料与水泥。 |
| Methane (CH₄) | 甲烷 | 第二重要的人为温室气体，寿命约 12 年，主要来自反刍动物、稻田、化石燃料泄漏。 |
| Nitrous oxide (N₂O) | 氧化亚氮 | 强温室气体兼平流层臭氧破坏物，寿命约 120 年，主要来自农业氮肥。 |
| Ozone (O₃) | 臭氧 | 平流层中吸收 UV（保护性），对流层中作为温室气体吸收 IR（增温）。 |
| Water vapour (H₂O) | 水汽 | 大气中最强的红外吸收体，浓度 0.2–2.6% 且高度可变；是反馈而非强迫。 |
| Calcination | 煅烧 | 水泥生产中 CaCO₃ → CaO + CO₂ 的分解反应，是水泥碳排放的化学来源。 |
| Fermentation in ruminants | 反刍动物瘤胃发酵 | 牛羊等消化过程产生甲烷的过程。 |
| Rice paddies | 稻田 | 淹水厌氧环境产生甲烷的农业源。 |
| Nitrification / Denitrification | 硝化作用 / 反硝化作用 | 土壤微生物的氮转化过程，是 N₂O 的主要生成途径。 |
| Atmospheric lifetime | 大气寿命 | 一种气体在大气中的平均滞留时间，决定减排见效的快慢。 |
| Aerosol | 气溶胶 | 悬浮在空气中的微小固体或液体颗粒。 |
| Particulate matter (PM) | 颗粒物 | 大气中的悬浮颗粒总称。 |
| PM2.5 / PM10 | 细颗粒物 / 可吸入颗粒物 | 空气动力学直径小于 2.5 μm / 10 μm 的颗粒；约 5–6 个 PM10 可横跨一根头发。 |
| Sulfate aerosol | 硫酸盐气溶胶 | SO₂ 氧化产物，明亮、散射阳光，产生降温效应（负强迫）。 |
| Black carbon | 黑碳 | 吸光性气溶胶，与散射性气溶胶相反，产生增温效应。 |
| Organic carbon | 有机碳（气溶胶） | 气溶胶的一种主要成分。 |
| Nitrate (aerosol) | 硝酸盐（气溶胶） | 气溶胶的一种主要成分。 |
| Sulphur dioxide (SO₂) | 二氧化硫 | 硫酸盐气溶胶的前体物，来自火山、燃煤与船用燃油。 |
| Cloud reflectivity | 云反射率 | 云把太阳辐射反射回太空的能力；气溶胶可通过间接效应提高它。 |
| Direct effect (aerosol) | （气溶胶）直接效应 | 📎 颗粒物自身散射或吸收辐射。 |
| Indirect effect (aerosol) | （气溶胶）间接效应 | 📎 颗粒物作为云凝结核改变云的亮度与寿命。 |
| Cloud condensation nuclei (CCN) | 云凝结核 | 📎 水汽凝结成云滴所依附的气溶胶颗粒。 |
| Masked warming | 被掩盖的增温 | 被气溶胶降温效应暂时抵消掉的温室气体增温，一旦气溶胶减少便显现。 |
| Co-benefits | 共同效益 | 一项措施同时带来的额外好处，如减温室气体同时改善空气质量。 |
| Climate disbenefit | 气候负效益 | 一项措施（如减少气溶胶）在气候上造成的不利后果。 |
| Air quality | 空气质量 | 大气中污染物浓度对人体健康与能见度的影响状况。 |
| Ground-level ozone | 近地面臭氧 | 对流层臭氧，既是空气污染物又是温室气体，减甲烷可降低其生成。 |
| Secondary particulate matter | 二次颗粒物 | 由气态前体物（如 NH₃、SO₂、NOₓ）在大气中转化生成的颗粒物。 |
| Ammonia (NH₃) | 氨 | 农业排放的气体，是二次颗粒物的重要前体物。 |
| NOₓ | 氮氧化物 | 燃烧产生的空气污染物，也是臭氧与二次颗粒物的前体物。 |
| Preterm birth | 早产 | 讲师提到的气溶胶暴露相关健康终点之一。 |
| Weather | 天气 | 某一时刻大气的状态（温度、风、日照、湿度等）。 |
| Climate | 气候 | 通常取 30 年平均的天气统计，包含平均值、变率与极端。 |
| Climate change | 气候变化 | 30 年尺度的气候统计量本身发生改变。 |
| Natural variability | 自然变率 | Week 2 内容：太阳变率、轨道变化、火山、海洋环流四大要素。 |
| Milankovitch cycles | 米兰科维奇旋回 | 地球轨道与轴倾角的长周期变化，驱动数万至数十万年尺度的气候变化。 |
| Solar cycle (11-year) | 太阳周期（11 年） | 太阳活动的周期性起伏，使"太阳常数"并非严格恒定。 |
| Ice–albedo feedback | 冰–反照率反馈 | 📎 变暖 → 冰雪减少 → 反照率下降 → 吸收更多 → 更暖的正反馈。 |
| Planck feedback | 普朗克反馈 | 📎 变暖 → 按 T⁴ 发射更多长波 → 抑制进一步变暖的基本负反馈。 |
| Earth's Energy Imbalance (EEI) | 地球能量失衡 | 📎 当前进出能量的净差额（约 +1 W m⁻² 量级），即气候变化本身。 |
| Pressure broadening | 压致展宽 | 📎 高气压下分子碰撞使吸收线变宽，增强总吸收；解释了金星与火星温室效应的巨大差异。 |
| Mid Unit Test | 期中单元测验 | Week 6（10 March）进行，45 分钟，占总成绩 30%。 |
| Mentimeter | Mentimeter（课堂互动平台） | 本课用于收集匿名反馈的工具。 |

---

## 附：材料勘误表

| 位置 | 材料原文 | 问题 | 更正 |
|---|---|---|---|
| 两份 deck 的**文件名** | `Week 4_Student Upload_2026` / `Week 4_Student Answers_2026` | **周号讹误**。两份文件名都写 Week 4，但幻灯片首页正文均为 "Week 3 - Radiation and the Greenhouse Effect"，讲义 Slide 2 周历也把该主题排在 Week 3（19th Feb），转写日期为 19-Feb。成因见转写："I wasn't sure if Simon was going to be available today, so both the week 3 and week 4 material is available" | **本周为 Week 3**。文件名应为 Week 3 |
| 讲义 Slide 26；答案 deck Slide 3 | "Energy In: Incoming solar radiation = So × Area (A) × **albedo** = **0.7** × So × πre²" | **文字标注与算式自相矛盾**。albedo = 0.3，0.7 是 (1 − albedo)。转写中讲师说的是正确的："we times the one minus the albedo" | 应为 **× (1 − α)**，即 0.7 × S₀ × πr_e² |
| 讲义 Slide 28；答案 deck Slide 3 | "Energy Out: Outgoing Terrestrial radiation = **TE4 4πre2**" | **公式缺少斯特藩–玻尔兹曼常数 σ**（pptx→md 转换时符号丢失） | 应为 **σ T_E⁴ × 4πr_e²** |
| 讲义 Slide 18 | "**Te = 288 K** so most of the irradiance from the Earth is in the infra-red" | **符号复用冲突**。Te 在 Slide 30 及答案 deck 中明确指"等效黑体温度 = 255 K"，此处却用它指实测地表温度 288 K | 应写作 **T_s = 288 K** 或 "surface temperature = 288 K" |
| 讲义 Slide 18 | "peaks at about **10 m**" | **单位缺失（μ 字符丢失）**。10 m 是无线电波波段 | 应为 **10 μm** |
| 讲义 Slide 19 | "Separated by a gap at around **4 m**" | 同上，μ 丢失 | 应为 **4 μm** |
| 讲义 Slide 22 / 25 / 26 | "S0=**1370 W m2**" | **单位上标丢失** | 应为 **1370 W m⁻²** |
| 讲义 Slide 15 | "σ = Stefan-Boltzmann constant (**5.67 x 10-8 W m-2 K-4**)" | 上标丢失（OCR/转换问题），数值本身正确 | 应为 **5.67 × 10⁻⁸ W m⁻² K⁻⁴** |
| 答案 deck Slide 4 / 5 | "((0.84*590) / (4*5.67***10-8**))**1/4**" | 上标与指数格式丢失 | 应为 (4 × 5.67 × 10⁻⁸)，整体取 **^(1/4)** |
| 讲义 Slide 40 | "CH4 **0.0018%**" | **数量级错误**。0.0018% = 18 ppm，而实际大气甲烷约 1.9 ppm | 应为约 **0.00019%（≈1.9 ppm）**，疑为漏写一个 0 |
| 讲义 Slide 40 | "CO2 **0.03%**" | **数值过时**。0.03% = 300 ppm，是上世纪的水平 | 当代约 **0.042%（>420 ppm）** |
| 讲义 Slide 40 | "**N** 78%" | 化学式不完整，氮在大气中以双原子分子存在 | 应为 **N₂ 78%** |
| 讲义 Slide 32 / 33 | "For high energy radiation (**<UV**)" | **表述含混**。若读作"波长小于紫外"则与"高能"一致，但符号方向易被误读为"低于紫外"（即能量更低） | 建议理解为"紫外及更短波长（更高能量）的辐射"，即电子跃迁适用的能段 |
| 讲义 Slide 2 | "Week 7 – Climate Models  (**19th March**" | **括号未闭合**（排版错误） | 应为 "(19th March)" |
| 讲义 Slide 2 | "Week 6 – Mid Unit Test (**10th March**)" | **日期与序列不符**（不确定）。其余各周日期均为周四（5/12/19/26 Feb、5/19/26 Mar…），而 10 March 2026 为周二 | 无法从材料确认，**标记为不确定**；以 Canvas 官方日程为准 |
| 讲义 Slide 29（Workshop 1） | 仅有标题 "Workshop 1"，无任何题干文字 | **题干为图片，未提取出文本**，学生无法从 md 版还原原题 | 题干需参照答案 deck Slide 3–5 与转写还原（本笔记 §5.1 已还原） |
| 讲义 Slide 57 / 58 / 59；答案 deck Slide 21–26 | "Q7." / "Q8." / "Q9." 及对应 Answer 页 | **完全空白**——题干与答案均无任何文字内容。Slide 58 备注栏只有一个孤立的 "(" | 材料缺失，需向讲师索取或查看 Canvas 课后上传版本 |
| 答案 deck Slide 16（Q4. Answer） | 页面内容仅为题目的重复，无实质解答 | **有问无答**，问答 deck 之间对不上 | 答案缺失；讲师课上说会在课后上传 |
| 答案 deck Slide 6 | "Mars atmosphere is very thin, approx. pressure is (approx. 6 mb) **than** Earth's (1000 mb)" | **句子残缺**，"than" 前缺少比较级 | 应为 "…is **much lower** than Earth's…" |
| 答案 deck Slide 6 备注 vs Slide 7 | Slide 6 正文 "Mars Atmosphere has a Greenhouse Effect of 2o"；Slide 7 与备注给出 218 K（实测）与 216 K（计算） | Slide 6 正文只给结论未给依据，两页内容重复且详略不一（非事实错误，属编排冗余） | 以 Slide 7 / 备注的完整版为准：实测 218 K − 计算 216 K = 2 K |
| 转写（讲评 Workshop 1） | "the **actual** temperature of Mars is **216** and that means it has a greenhouse gas effect of around two degrees" | **口误/讹误**。216 K 是**计算值**，218 K 才是**实测值** | 实测 218 K，计算 216 K，差值 2 K（答案 deck 备注写对了） |
| 转写 | "the area of that that is intercepted ... can be calculated by the **diameter** of the Earth, which is of course pi r squared" | **口误/ASR 讹误**。πr² 用的是**半径**，且描述的是**截面圆盘** | 应为"由地球**半径**决定的**迎光截面圆盘**，面积 πr²" |
| 转写 | "Around **45** percent … visible. Only **seven** … UV, and around **50** percent … longer wavelengths" | **合计 102%**，超过 100% | 属口头粗略取整，三者应理解为约值 |
| 转写 | "**Mankovitch** cycles" | ASR 讹误 | **Milankovitch cycles** |
| 转写（三处） | "**Green's law**" / "**Venus law**" / "**Boone's law**" | ASR 讹误，同一定律被误识为三个不同名称 | 均应为 **Wien's law（维恩定律）** |
| 转写（两处） | "**Steppen-Voltzmann** law" | ASR 讹误 | **Stefan–Boltzmann law** |
| 转写 | "**theta** is the Stefan-Boltzmann constant" | ASR 讹误，希腊字母识别错误 | 应为 **sigma（σ）** |
| 转写 | "gamma radiation, which have a wavelength around the size of **atomic energy**" | ASR 讹误，语义不通 | 应为 **atomic nuclei（原子核）** |
| 转写 | "they can move between the **five** energy states" | ASR 讹误（讲义与上下文均未提"五个能级"） | 应为"不同能级 / 各能级之间" |
| 转写 | "from the N2O and **EPA** perspective" | ASR 讹误，上下文在讨论三种温室气体的农业源 | 疑为 **CH₄**；**不确定，仅标注** |
| 转写 | "why you might get differences in your answers from answers **1 to 8**" | 与实际题量不符，本周 Workshop 1 只有三小问 | 应为 **Q1a–Q1c** |
| 转写 | "he was due to give his guest lecture" … "all being well and **she** needs to take full health" | **人称前后不一致**（ASR 讹误），且后半句语法不通 | 不作为性别信息使用；讲者姓名材料中仅出现 "Simon" |
| 转写（两处） | "in **week eight** where we look at **mitigations**"；"case study examples, I think in **week eight**" | **与讲义周历不符**。Slide 2：Week 8 = Climate change adaptation，Week 9 = Case Studies，Week 10 = Climate change mitigation | 以**讲义周历**为准；讲师本人也用了 "I think" 表示不确定 |
| unit spec vs 讲义 Slide 2 | unit spec syllabus：W2 Observational evidence / W4 Radiative forcing and feedbacks / W5 Climate models / W7 Natural climate variability / W8 Other anthropogenic impacts；讲义 Slide 2：W2 Natural climate variability / W4 Anthropogenic Impacts / W5 Evidence Base / W7 Climate Models / W8 Adaptation | **两份官方材料的周次编排不一致**（unit spec 为课程注册时的计划，讲义为本学年实际排课） | 以**讲义 Slide 2 的周历**为本学年实际安排；unit spec 仅供了解课程整体轮廓 |
| unit spec teaching staff vs 讲义署名 | unit spec 列 Thomas Choularton、Martin Gallagher 为 Unit coordinator；本周 deck 署名 Dr Thomas Bannan | **人员信息不一致**（可能是不同学年的授课安排，或 unit spec 未更新） | 本周实际主讲为 **Dr Thomas Bannan**；unit spec 的协调人信息未在本周材料中出现，**不作进一步推断** |
