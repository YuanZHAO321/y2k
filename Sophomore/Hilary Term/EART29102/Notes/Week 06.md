# EART29102 Geospatial Techniques — Week 06 学习笔记

> 授课日：09-Mar（Hilary Term, Week 06）
> 材料：`Geospatial Techniques - Lecture 6 - Remote Sensing - 2026`（讲义，含低质量 OCR 段）＋ `EART29102 - 09-Mar-transcript`（课堂录音转写，8,340 词，本课最长）＋ `Practical 6 - Remote Sensing`（ArcGIS Online + ArcGIS Pro 实操教程）
> 本周主题：**遥感（Remote Sensing）**
> ⚠️ 本周由**客座讲师** Peter Grindrod（Natural History Museum, London；曼大荣誉职位）主讲，非课程负责人 Ray Burgess。讲授视角带有强烈的**行星科学**色彩，这直接决定了本周讲义的例子构成。

---

## 一、本周主题

### 1.1 本周在全课骨架中的位置

本课程的实际骨架是：**基础段**（W01 GIS 导论 → W02 空间数据与数据管理 → W03 数据输入与操作）→ **分析段**（W04 空间分析 → W05 空间统计）→ **专题段**（**W06 遥感** → W07 地形分析 → W08 空间可视化 → W09 三维技术）→ W10 课程回顾。

**本周是专题段的起点，也是全课的一次视角切换。**

前五周处理的是**已经存在的、已经进了 GIS 的数据**：W02 教你 vector / raster 两种数据模型和元数据，W03 教你怎么把数据输进来、怎么编辑，W04 教你 overlay / buffer / map algebra / 插值，W05 教你 Moran's I、Gi\*、KDE。这五周从来没有回答一个问题：**这些 raster 图层最初是从哪儿来的？**

W06 就是回答这个问题的一周。**遥感是 GIS 中绝大多数栅格数据的源头。** 三条具体的衔接线：

1. **→ W02 的栅格数据模型。** W02 讲 raster 是「pixel + cell size + bit depth」；W06 把这三个词还原成物理量：cell size 就是 **spatial resolution**（像元在地面上的大小），bit depth 就是 **radiometric resolution**（探测器能分辨多少级亮度），pixel value 就是探测器记录到的**电磁能量通量（DN，digital number）**。W02 笔记里说的「16-bit 是 Landsat/Sentinel 常用」，本周 Practical 导出栅格时就要手动填 `16 bit unsigned`。
2. **→ W04 的 map algebra / raster overlay。** W04 教的「栅格代数」在本周有了最典型的应用：**band ratio（波段比值）与光谱指数**。`(B8−B4)/(B8+B4)` 本质上就是四个栅格图层做逐像元代数运算——这是 W04 工具在真实科学问题上的落地。
3. **→ W05 的空间统计。** W05 分析的是点数据（臭氧站点），但热点分析、KDE 的输入完全可以是遥感反演出的连续场（如 NDVI、地表温度）。**遥感提供的是「全覆盖、多时相、可重复」的数据，这正是空间统计最需要的样本量。**

**向后看**：W06 末尾讲的 **Lidar 与 DTM/DEM**，直接是 **W07 地形分析** 的输入数据；点云与 3D 结构则接 **W09 三维技术**。所以本周在结构上是「数据来源」这一环，前接数据模型、后接地形与三维。

### 1.2 讲义列出的六条内容主线

讲义首页 "Lecture content" 明列六条，这是本周的骨架：

1. Remote sensing data and applications.（遥感数据与应用）
2. Electromagnetic Spectrum Radiation and spectral reflectance.（电磁波谱辐射与光谱反射）
3. Spectral, spatial and radiometric resolution.（光谱、空间、辐射分辨率）
4. Landsat and Sentinel satellites.（两大卫星系列）
5. Image preprocessing, enhancement and transformation.（影像预处理、增强与变换）
6. Radar and Lidar imaging.（雷达与激光雷达成像）

> **注意**：首页只列了三种分辨率，但正文 "Detector Systems → Resolution" 一节实际讲了**四种**（多出 temporal 时间分辨率）。以正文的四种为准。

### 1.3 Practical 列出的三条学习目标

- Use ArcGIS online to easily visualize changes in land use.（用 ArcGIS Online 可视化土地利用变化）
- Be able to work with Landsat and Sentinel 2 imagery in ArcGIS Pro.（在 ArcGIS Pro 中处理 Landsat 与 Sentinel-2 影像）
- Understand how spectral enhancements are used in vegetation and mineral studies.（理解光谱增强在植被与矿物研究中的作用）

### 1.4 老师自己给本周定的调子

转写开头，老师直接说明了他的取向：

> "although I use remote sensing in my research every day, I'm actually a planetary scientist... So we're gonna use the same techniques that you'll learn for the earth, but we use them on a planetary scale."

以及关于物理的部分：

> "I don't wanna reteach you A-level physics. I want to try and show you the parts that are relevant to the things that we'll discuss later on in the lecture."

**复习提示**：本周不考物理推导。要掌握的是**「哪个波段能看到什么、为什么」**这条逻辑链，以及**四种分辨率之间的权衡**。

---

## 二、核心概念

### 2.1 遥感的定义

讲义给出的定义（三条，逐条要点）：

- **Techniques for collecting environmental data from a distance without coming into direct contact with the objects of interest.**（在不与目标直接接触的情况下、从远处收集环境数据的技术）
- **Record the magnitude of electromagnetic energy flux that is reflected or emitted from the objects on the surface or within the atmosphere (normally imagery).**（记录地表或大气中的物体所**反射**或**发射**的电磁能量通量的大小，通常成像）
- **Aeroplanes, satellites, and UAVs equipped with sensors.**（搭载传感器的飞机、卫星与无人机）

老师在转写里的口语版更好记：

> "a way of collecting information without actually going and touching, collecting something."

**注意定义里的两个动词**：*reflected*（反射，来自太阳）与 *emitted*（发射，来自目标自身热辐射）。这两条路径对应后面**反射红外**与**热红外**的分野。

### 2.2 被动遥感 vs 主动遥感（Passive / Active）

| | **Passive（被动）** | **Active（主动）** |
|---|---|---|
| 能量来源 | 太阳（或目标自身热辐射） | 传感器**自带**能量源 |
| 典型 | 光学多光谱成像（Landsat、Sentinel-2） | Radar、Lidar、Sonar |
| 常见程度 | 主流 | 老师原话 "aren't as common, but they have their advantages" |
| 依赖条件 | 需要日照；受云、大气影响大 | 不依赖日照；长波可穿云穿雾 |

老师解释主动遥感的原理时说得很直白：

> "They actually have their own energy source and they direct that energy down to the surface and then collect the information again."

**关键的物理动机**（转写，非常重要，讲义上没有这么讲）：**为什么长波要用主动方法？** 因为太阳辐射在长波段能量本来就极少——

> "as you go to these longer and longer wavelengths, there's actually less and less energy... And so you actually start to move from what are passive techniques, relying on the sun's energy and moving into active techniques."

这条逻辑把黑体曲线、电磁波谱分区、主/被动之分**串成了一条因果链**，是本周最值得掌握的一个「为什么」。

### 2.3 遥感的应用（讲义八条）

- **Urban monitoring and disaster management** —— floods, wildfires, dust storms, landslides, earthquakes.
- **Climate change trends** —— greenhouse gases and air pollution.（讲义唯一加粗的一条）
- **Agriculture** —— crop health, yield estimation, precision farming.
- **Forestry management** —— tracking deforestation, assessing biodiversity.
- **Water resource management** —— 湖泊、河流、湿地、海洋的水质与水量。
- **Archaeological studies.**
- **Environmental conservation.**
- **Land use and infrastructure planning.**

### 2.4 电磁辐射（EMR）：定义

**Electromagnetic (EM) radiation is a form of energy capable of propagating through a vacuum and interacting with matter.**（能在真空中传播并与物质相互作用的一种能量形式）

**波粒二象性的分工**（讲义明确写出，是考点式的表述）：

| 概念 | 描述内容 |
|---|---|
| **Wave（波）** | 连续的**横波**，由相互正交的振荡电场与磁场构成。描述电磁能量如何**传播（propagated）、折射（refracted）、反射（reflected）** |
| **Particle（粒子 / photon 光子）** | 离散、不可分的能量包。描述传感器如何**探测（detection）**电磁能量 |

讲义原话：*"The wave concept describes how electromagnetic energy is propagated, refracted and reflected, whereas the particle concept describes the detection of electromagnetic energy by a sensor."*

### 2.5 EMR：三大属性与速度关系

- **All objects (> 0 K) emit electromagnetic radiation**（所有温度高于绝对零度的物体都发射电磁辐射）——这是热红外遥感的基础。
- 三个主要属性：**1. Wavelength（波长 λ）；2. Frequency（频率 v）；3. Amplitude（振幅）**
- 速度关系：**c = vλ**，其中 c ≈ 3 × 10⁸ m s⁻¹

老师明确说：*"if you know your physics, you know that we also have frequency and amplitude and the function of the speed of light, you don't need to worry about that too much."* —— **本周只需要牢牢抓住 wavelength 这一个变量**，其余不深究。

### 2.6 EMR 与物质的相互作用：五种

能量到达行星体后与物质发生相互作用，**会改变入射辐射的特性（intensity 强度、direction 方向、wavelength 波长、polarization 偏振、phase 相位）——遥感寻找的正是这些改变**。

讲义把五种相互作用分成两组：

**Volume phenomena（体相现象，能量进入介质内部）**
1. **Transmission（透射）**
2. **Absorption（吸收）**
3. **Emission（发射）**

**Surface phenomena（表面现象）**

4. **Scattering（散射）**
5. **Reflection（反射）**

> ⚠️ 讲义原文的排版把 "Emission" 放在 *Volume phenomena* 标注之后、*Surface phenomena* 标注之前，分组归属略有歧义。转写里老师的说法是：「the volume phenomena... these are where the energy is absorbed from the surface down. And we have the surface phenomena. **The scattering and reflection are the ones we're most interested in.**」——所以确定的是：**scattering 与 reflection 属表面现象，且是遥感最关心的两种。**

**转写里老师用四个端元讲反射方式**（讲义只有图，无文字，这段全靠转写）：

1. **Ideal specular reflector（理想镜面反射体）**：入射角 = 反射角。"that is a perfect situation. You'd very rarely see that."（现实中极少见）
2. **Absorption + transmission + refraction（吸收/透射/折射）**：能量进入表面内部，可能把表面加热。
3. **Perfectly diffuse reflection（理想漫反射）**：能量向所有方向反射。老师的判据很好用——"**it wouldn't really matter where your detector was. You're gonna get some energy back.**"（探测器放哪儿都能收到信号）
4. **Emission（自身发射）**：不需要入射能量，物体把先前吸收的能量在**更长的热波长**上发射出去。"the earth does that at longer thermal wavelengths."

### 2.7 黑体辐射与发射率

**核心规律（讲义两条 + 转写详解）**：

- **Amount and wavelength of energy depends on temperature of object.**（能量的多少与波长取决于物体温度）
- **Higher T = more energy, shorter (peak) wavelength.**（温度越高，总能量越大，**峰值波长越短**）

**Emissivity（发射率）= ratio of emittance of a body and that of a blackbody.**（某物体的发射本领与同温黑体发射本领之比）——因为 *"No object is perfect black body."*

📎 **背景补充：** 讲义与转写都没有写出这条定律的名字与公式。「峰值波长随温度升高而变短」即 **Wien's displacement law（维恩位移定律）**：λ_max ≈ 2898 / T（λ_max 单位 µm，T 单位 K）。代入转写中的两个数字可验证：地球 300 K → 2898/300 ≈ 9.7 µm（老师说 "just less than 10 microns" ✓）；太阳 5000 K → 2898/5000 ≈ 0.58 µm（老师说 "just there below a micron" ✓）。**这条公式材料里没有，只做理解用，不必当作本课考点。**

### 2.8 电磁波谱的分区（讲义完整表格）

讲义强调分区是人为的：*"Arbitrary in reality; no sharp breaks."*（现实中没有截然的分界）老师也补了一句：*"you might see slightly different values for these wavelengths."*（不同资料的数值会略有出入）

| Region（区） | Wavelength（波长） | 说明 | 被/主动 |
|---|---|---|---|
| **Gamma-ray** | < 0.03 nm | 被上层大气完全吸收。宇宙线激发与发射 | Passive |
| **X-ray** | 0.03 – 30 nm | 被上层大气完全吸收。太阳能量激发与发射 | Passive |
| **Ultraviolet** | 0.03 – 0.4 µm | 被上层大气（臭氧）部分吸收。诊断特征少 | Passive |
| **Visible** | 0.4 – 0.7 µm | 真彩色与假彩色影像。诊断特征少 | Passive |
| **Infrared** | 0.7 – 100 µm | 反射的太阳能量 + 发射的热能量。**诊断特征众多** | Passive |
| **Near infrared（NIR）** | 0.7 – 1.3 µm | **Reflected（反射）** | Passive |
| **Mid infrared（MIR）** | 1.3 – 3.0 µm | **Reflected（反射）** | Passive |
| **Far infrared（FIR）** | 3.0 – 1000 µm | **Emitted（发射）** | Passive |
| **Microwave** | 0.1 – 100 cm | 可穿透云、霾、尘。无大气散射 | Passive **or** Active |
| **Radar** | 1.0 – 100 cm | 常用于行星研究 | Active |
| **Radio** | > 100 cm | 仅用于通信；内部重力场研究 | Active |

> ⚠️ **表中所有以 µm 为单位的行，讲义原文一律误写为 mm**，这是 OCR 把 µm（或原稿的 μm）识别成 mm 的系统性错误。已在文末勘误表记录。判据很简单：X-ray 上限是 30 nm = 0.03 **µm**，正好与 Ultraviolet 下限 0.03 衔接；若是 mm 则相差 1000 倍，整张表无法自洽。

**关于红外的重要判断（讲义 + 转写一致）**：

> "in some respects, the infrared is one of the most important regions for remote sensing because there are... many diagnostic features, we call them, many **unique spectral features** that can help us figure out, say, what the surface is made of or what an atmosphere is made of."

**记忆抓手**：`0.7–3.0 µm = 反射红外（NIR + MIR）` vs `> 3.0 µm = 发射红外（热红外）`。分界点 3 µm 是「太阳反射」与「地物自身热辐射」谁占主导的转折。

> ⚠️ 术语注意：讲义此处沿用的是**遥感地质学传统（Sabins 式）**的红外划分，把 1.3–3.0 µm 叫 **Mid infrared**。但 Landsat / Sentinel 官方文档和本周 Practical 一律把 1.57–2.29 µm 这一段叫 **SWIR（Short-Wave Infrared，短波红外）**。**两套叫法指的是同一段波长**，看到时不要以为是两个东西。见勘误表。

### 2.9 大气相互作用与大气窗口

讲义两条：

- **Intensity received inversely proportional to square of distance from sun.**（接收到的辐照度与到太阳距离的平方成反比）
- **Presence and composition of atmosphere reduces surface flux further.**（大气的存在与成分进一步削减到达地表的通量）

转写把这张图讲清楚了（**讲义只有图无文字，这段完全依赖转写**）：图上有三条曲线——

1. **黑线**：理想黑体的发射谱；
2. **淡黄/橙线**：太阳的实际能量谱（大气层顶）；
3. **红线**：**到达地球表面的能量**。

红线上的一个个**深谷**，就是大气吸收带。老师原话：

> "where you can see these big drops in the red plot, those are areas where we receive little or no energy at the surface because the atmosphere has absorbed at those wavelengths. And we can ascribe those absorptions to different things that are present in our atmosphere, like **water, oxygen, carbon dioxide**, and there's even some smaller trace gases as well."

**这条结论是整个卫星波段设计的依据**：

> "if you do want to study the surface of the earth... from a satellite above the atmosphere, you have to **pick windows where you've got the most energy coming back**, where the energy isn't absorbed in the atmosphere."

📎 **背景补充：** 这些「能量能穿透的波长区间」在遥感文献中的标准术语是 **atmospheric window（大气窗口）**。讲义与转写都描述了这个概念但**没有使用这个词**。

**一体两面（老师专门强调的思维反转）**：吸收带对地表观测是**障碍**，但对大气成分研究是**信号**——

> "if you wanted to, say, study the composition of the atmosphere of another planet, you can actually use that to your advantage and say, we have absorption features at this wavelength so we know that there is this molecule present."

### 2.10 表面相互作用与光谱反射曲线

讲义定义（**本周最核心的两个定义**）：

- **Spectral reflectance（光谱反射率）**：the portion of the incoming radiation that is reflected.（入射辐射中被反射的部分）
- **Spectral reflectance curve（光谱反射曲线）**：a graph of the spectral reflectance of an object as a function of wavelength.（某物体的光谱反射率随波长变化的曲线图）
- 相互作用的多少取决于三件事：**the wavelength of the energy（波长）、the material（材质）、the condition of the feature（地物状态）**。

**转写对这张图的逐条讲解**（讲义只有 "red / green" 两个字的图片文字，实质内容全在转写里）——图上有三条曲线：**soil（土壤）、vegetation（植被）、clear water（清水）**，横轴从可见光延伸到近红外：

- **Vegetation（植被）**：在**红光与蓝光**波段有明显的**吸收谷**（"you can see these dips for red and blue wavelengths"）；在**绿光**处吸收较少 → **这就是植被看起来是绿色的原因**（"which is why vegetation typically appears green because it's reflecting that portion of the spectrum back to us"）。
- **进入红外后，土壤与植被出现巨大差异**："as you move into the infrared, you can see there's a big difference there between the way that soils absorb energy and the way that vegetation absorbs energy."
- **这个差异的直接用途**：野火后植被烧毁、露出裸土的判别——"if you wanted to say, look at how vegetation has burnt away after wildfires and you're left with bare soil, you can do that when you go to longer wavelengths because there's a real difference between the way that the energy is reflected back from the surface."

📎 **背景补充：** 材料**没有**明确说出「植被在 NIR 高反射、水体在 NIR 强吸收」这组经典结论的定量表述，也没有给出各地物的典型反射率数值。材料只讲到「红蓝有吸收谷、绿处反射高」和「红外波段土壤与植被差异大」。**下面第三节 3.4 给出的完整曲线形态描述中，超出上述范围的部分均已单独标注为背景补充。**

### 2.11 探测器系统（Detector Systems）

#### (1) 基本事实

- **With few early exceptions, remote sensing systems involve satellite platform + digital detectors.**（除少数早期例外，遥感系统 = 卫星平台 + 数字探测器）
- **Early missions used film, or television → modern = digital.**
- **Digital images amongst most common data set.**
  - **Pixels = picture elements, numeric value**（像元 = 图像元素，一个数值）
  - **Bit (binary digit) depth = number of discrete values (controls detail level)**（位深 = 离散取值的个数，控制细节层次）

#### (2) 平台与轨道（Platforms and Orbits）

讲义：**Orbital configuration (Earth); flybys & orbital (planetary)**。
- **Orbital missions**：最适合做**全球研究 + 重复覆盖（repeat coverage）**。
- **Flybys（飞掠）**：主要是早期任务或首次探测（如 New Horizons）。

转写补充的**四种轨道**（讲义上没有文字，全靠转写）：

| 轨道类型 | 特点 | 老师的说明 |
|---|---|---|
| **Polar orbit（极轨）** | 绕两极飞行，靠**地球自转**提供东西向覆盖 | "quite high energy orbits" —— 发射能耗高，要么飞行器更轻，要么火箭更大 |
| **Equatorial orbit（赤道轨道）** | 沿赤道 | 可**借地球自转给火箭一个初速度** |
| **Inclined orbit（倾斜轨道）** | 与赤道成一定夹角 | 同上，因此更常用 |
| **Elliptical orbit（椭圆轨道）** | 距离沿轨道变化 | 近地点可低到几百公里 → **高分辨率影像**；但上层大气会衰减轨道，不能久留 |

**Ground track（星下点轨迹）与 swath（幅宽）**：仪器的 swath 通常**比 ground track 宽**，随时间推移，一条条 swath 累加起来形成**全球覆盖**。

#### (3) 传感器机制（Sensor Mechanics）

讲义两大类：

1. **Framing（框幅式）**：瞬时成像一整帧。**Not common in orbital missions.**（轨道任务中不常见）——老师的类比：**你口袋里的手机就是一台 framing camera**。
2. **Scanning（扫描式）**：视场（FOV）窄，靠扫描把影像「扫」过地表。
   - **Cross-track（穿轨）**：扫描方向**垂直于**飞行方向。
   - **Along-track（沿轨）**：扫描方向**沿着**飞行方向。

转写补充的关键机制（讲义没有这个词）：**push broom instrument（推扫式仪器）**——

> "we would have a detector that might be made up of a **single line of detector**. And what you do is use this spacecraft motion to build up that image. And so you basically push the image across the surface of the earth. So we call it a **push broom** instrument."

**幅宽固定、长度可控**："they would have a fixed swath or a fixed width and then you can control how long your image will be on the surface." 限制因素是**仪器内存**——"These images regularly will go up to **several gigabytes** for a single image."

### 2.12 四种分辨率（本周最核心的框架）

讲义定义：**Resolution = Limit to the level of detail that a detector system can acquire.**（探测器系统能获取的细节层次的极限）**Four main types relevant here:**

#### ① SPATIAL RESOLUTION（空间分辨率）

**定义（转写）**："basically the **size of the pixel as it appears on the surface**."（像元对应到地表的尺寸）

讲义用一组从 100 m/pixel 到 0.1 m/pixel 的演示图说明：

| 像元大小 | 老师现场的判读描述 |
|---|---|
| 100 m/pixel | "you can't make out anything. It just looks like a nice abstract picture." |
| 50 m/pixel | "even if you're squinting, you're not gonna be able to make out much detail" |
| 10 m/pixel | "you start to pick up some colors... You might be able to join some of those colors together into shapes but you're still not gonna make out any detail" |
| 5 m/pixel | "pretty good spatial resolution. You can start to see greens, browns, reds, blues." |
| 1 m/pixel | **这时才认出来是曼彻斯特大学与 Oxford Road** |
| 0.1 m/pixel | Google Earth 上曼彻斯特一带的免费影像，"almost certainly collected actually from an **aeroplane** rather than a satellite" |

**代价（老师反复强调的 trade-off）**："that also means that you would need a **bigger telescope** on the front of your camera and also the size of your data is gonna be much bigger than you're gonna need **bigger data rates** to get them back."

#### ② SPECTRAL RESOLUTION（光谱分辨率）

**定义**：能分辨的波长细分程度——你在多少个、多窄的波长位置上取样。

转写讲得比讲义清楚：

> "You can choose which wavelength you want to look at... you could say, I'm going to take an image at each of those wavelengths. You can combine them and start to build up a spectrum. So **if you're looking for absorption features, this is what you do**. But you have to think about **how close together those bands are to actually resolve a spectral feature**."

讲义引出但**明确说不深入**的两个术语：**full width half maximum（FWHM，半高全宽）**与 **sampling interval（采样间隔）**。老师原话："I won't talk about more today, but it's an important concept when we go into things like Landsat and whether you can resolve spectral features."

讲义关于波段数的判断：**Higher spectral resolution means more bands and more diversity, but also more complexity and noise.**（光谱分辨率越高，波段越多、信息越丰富，但复杂度与噪声也越大）

#### ③ RADIOMETRIC RESOLUTION（辐射分辨率）

**定义**：探测器的**位深（bit depth）**，即能区分多少级亮度。

| 位深 | 灰度级数 |
|---|---|
| 4 bit | 2⁴ = **16** levels |
| 8 bit | 2⁸ = **256** levels |
| 10 bit | 2¹⁰ = **1024** levels |
| 12 bit | 2¹² = **4096** levels |

**代价**："it comes at the expense of your data volumes again. The higher the bit depth, the greater the memory you're gonna need on your spacecraft... and the higher data rates you're gonna need back."

⚠️ **老师明确降低了这一项的考核权重**："Another one that you won't need to worry about too much, but it's important if you ever get into, say, designing an instrument."

#### ④ TEMPORAL RESOLUTION（时间分辨率）

**定义**：同一地点被重复成像的频率（重访周期）。

讲义给出的数字：
- **Weather satellites（气象卫星）**：every **5–10 min**
- **Sentinel-2**：repeat periods of **3–5 days**
- **Landsat**：讲义写 "repeat period every **32 days**" ⚠️（**此数值有误，见勘误表**）

老师对地球 vs 行星的对比很有意思：地球的时间分辨率**太好了以至于常被忽视**，但对火星就非常宝贵——他展示了同一区域相隔 10 年的两幅火星影像，能看到 **dust devils（尘卷风）**留下的黑色条纹和一个**新形成的约 10 m 直径撞击坑**。

#### ⑤ 四者的核心权衡（本周最重要的一句话）

> "Basically if you increase the spatial resolution or the spectral resolution, **you might lose some of the resolution along the way** so you need to consider it."

**统一的物理约束是「单位时间内能收集到的光子数是有限的、且下传带宽是有限的」**：像元更小 → 每个像元收到的能量更少；波段更窄 → 每个波段收到的能量更少。要保持信噪比，就必须在别处让步。**这是遥感所有传感器设计的第一性权衡，也是最典型的考点。**

### 2.13 卫星系列：Landsat 与 Sentinel

讲义要点：

- **Satellites can image different spectral bands.**
- **Some commercial satellites have spatial resolutions of 30–50 cm**, while most non-commercial satellites are **10 – 100s m**.
- **Landsat**：USGS / NASA；讲义写重访 32 天 ⚠️；**8–11 bands**，覆盖 visible、near-infrared、shortwave infrared、thermal infrared；空间分辨率 **15 – 60 m**（因波段而异）。
- **Sentinel**：欧洲（ESA）；重访 **3–5 days**；讲义写 **13–25 bands**，覆盖 visible、near-infrared、shortwave infrared、microwave ⚠️（**混淆了 Sentinel 星座不同成员，见勘误表**）；空间分辨率 **10 – 60 m**。

**Landsat 的独特价值（转写，老师说了两遍）**——**连续性（continuity）**：

> "there's been continuous coverage over time and they'll **overlap** — they'll set up a new spacecraft which overlaps with the previous one before that satellite is decommissioned. So we have continuous temporal coverage which is amazing."

而且不只是**时间上重叠**，**波段上也重叠**：

> "they don't just overlap in time, they overlap with... **wavelength from the bands that were chosen**. So you can see how the earth has changed over time continuously since the 1970s **with similar data**. It is a phenomenal data set and it is **entirely free** for anyone to use."

**波段选择与大气窗口的对应**（转写，是把 2.9 与 2.13 缝起来的关键）：

> "you can see how we tend to choose bands if we wanna look at the surface that **intersect these high energy areas**; where there's a big gap, these bands will be chosen to actually **study the atmosphere**. And you can... use the information in those bands to **improve your surface information**."

即：**落在大气窗口里的波段 → 观测地表；落在吸收带里的波段 → 观测大气，并反过来用于地表影像的大气校正。** 本周 Practical 里 Landsat 8 的 **Band 1 Coastal Aerosol** 和 **Band 9 Cirrus** 正是后一类。

### 2.14 多光谱影像与彩色合成

- 卫星探测器通常**一个波段拍一幅灰度图**，再把若干幅组合成彩色影像。
- 讲义：**Different bands can reveal different information about the surface features, vegetation, water, or atmosphere.**
- 组合方式（转写给出的三级命名）：

| 名称 | 含义 |
|---|---|
| **True colour / Natural colour composite（真彩色）** | 红绿蓝三波段对应显示到 R、G、B 通道，"features in the image are rendered as the human eye would see them in real life"（Practical 原话） |
| **Pseudo natural colour（拟自然色）** | 选取比人眼波长略长或略短的波段，"almost exaggerates what we would see" |
| **False colour（假彩色）** | R、G、B 通道用**完全不同的波长**，用来突出特定地物 |

老师给的判据："if you want to highlight water you can see how that reacts very differently in the infrared to say rock and they heat up at different rates."

### 2.15 影像预处理（Image Preprocessing）

#### (1) Geometric correction（几何校正）

讲义两条：
- **remove geometric distortions caused by sensor-Earth geometry variations.**（消除传感器—地球几何关系变化造成的几何畸变）
- **georeference the image to a particular projected map coordinate system.**（把影像配准到特定投影地图坐标系）

转写补充：需要**非常精确的飞行器位置与指向信息**，"which is actually quite complicated orbital mechanics, but hopefully **someone else is doing that for you as an end user**"。还要做 **map projection（地图投影）**，使其与该区域的其他图层叠合。

#### (2) Radiometric correction（辐射校正）

讲义三条：
- **correct an image for sensor response properties and viewing geometry.**（校正传感器响应特性与观测几何）
- **correct an image for atmospheric effects and scene illumination.**（校正大气效应与场景光照）
- **restore an image to accurately represent the radiance measured by the sensor.**（还原影像以准确表达传感器测到的辐亮度）

讲义配图文字：**"Removing top-of-the atmosphere reflectance"**（去除大气层顶反射率），配的是 **True colour (bands 4, 3 and 2)**。

转写描述效果："we get much better **clarity or contrast** at the surface because we've removed the effects of the atmosphere."

📎 **背景补充：** 材料中出现的 "top-of-the-atmosphere reflectance" 标准缩写是 **TOA reflectance**，经大气校正后得到的量称为 **surface reflectance（地表反射率，SR）**。Practical §5.2 中也出现了 "surface reflectance spectral bands" 的说法。材料没有展开这组术语的区别。

### 2.16 影像增强（Image Enhancement）

讲义四种：

| 方法 | 讲义定义 |
|---|---|
| **Band combination（波段组合）** | increasing the amount of information that can be **visually interpreted**（提升可目视解译的信息量） |
| **Pan-sharpening（全色锐化）** | increasing the **spatial resolution of a multispectral image** with a **higher-resolution panchromatic image** |
| **Contrast stretching（对比度拉伸）** | enlarging the **tonal distinction** between different features（扩大不同地物间的色调差别） |
| **Spatial filtering（空间滤波）** | enhancing or suppressing specific **spatial details** |

**Pan-sharpening 的成立条件（转写强调）**："That works best when you have a **single instrument pointing at the same place at the same time**, but you can try it from different instruments at different times. **It's just harder.**" —— 两幅影像必须**共配准（co-registered / aligned）**得非常好。

**Contrast stretching 的三档**（讲义配图）：**Original / Linear contrast stretching / Histogram equalization**。老师提醒**可能过头**："you can even overdo it on the right-hand side. You can equalize the histogram, but it does serve its purpose. You can **highlight the edges** if you're after the boundaries of different units or vegetation."

### 2.17 波段组合与光谱指数（讲义列表，Sentinel-2 波段号）

⚠️ **以下所有 B 编号均为 Sentinel-2 编号**（转写里老师口误说成 "For Landsat"，见勘误表）：

| 组合名 | 波段 | 用途 |
|---|---|---|
| **Natural Colour** | B4, B3, B2 | 自然色 |
| **Color Infrared** | B8, B4, B3 | 健康 / 不健康植被 |
| **Short-Wave Infrared** | B12, B8A, B4 | 植被、裸土与城区 |
| **Agriculture** | B11, B8, B2 | 作物健康状况 |
| **Geology** | B12, B11, B2 | 断层、岩性、矿床 |
| **Bathymetric** | B4, B3, B1 | 海岸研究、水中悬浮泥沙 |
| **Vegetation Index** | (B8 − B4)/(B8 + B4) | 密集冠层、城区与水体 |
| **Moisture Index** | (B8A − B11)/(B8A + B11) | 植物水分胁迫；**较湿的植被值更高**，较低值提示植物因水分不足而受胁迫（干旱区） |
| **Normalised Burn Ratio (NBR)** | (NIR − SWIR)/(NIR + SWIR) | 火烧迹地识别 |

📎 **背景补充：** 讲义把 `(B8−B4)/(B8+B4)` 叫作 **Vegetation Index**，其国际标准名称是 **NDVI（Normalised Difference Vegetation Index，归一化植被指数）**；`(B8A−B11)/(B8A+B11)` 的标准名称是 **NDMI（Normalised Difference Moisture Index）**。**材料从未使用 NDVI / NDMI / NDWI 这些缩写。** 另外，任务提纲中提到的 **NDWI（水体指数）本周材料完全未涉及**，本笔记不代为展开。

### 2.18 主动方法之一：Radar（雷达）

**Radar = Radio wave detection and ranging**，讲义定义：**active method using microwave energy**。

**优势与用途**：
- **Ability to penetrate atmospheres opaque at other wavelengths.**（能穿透在其他波长上不透明的大气）
- **InSAR（Interferometric Synthetic Aperture Radar，干涉合成孔径雷达）**可测量**地表位移**——冰川、冰盖、地震——并可**导出 DEM**。
- **Longer wavelengths are sensitive to length scales that often reflect differences between geological terrain.**（更长的波长对某些尺度敏感，这些尺度往往反映地质地形的差异）

**返回信号强度取决于两组因素**（讲义明列，考点式）：
1. **Radar system properties** —— wavelength（波长）、angle（角度）、polarization（偏振）
2. **Terrain properties** —— dielectric properties（介电性质）、surface roughness（表面粗糙度）、orientation（朝向）

**雷达成像的几何特点（讲义两条 + 转写详解）**：
- **Radar not usually nadir（非天底观测）** —— 有 **look direction（视向）** 和 **depression angle（俯角）**。
- **Records energy as a function of time, not distance → image distortions.**（记录的是能量随**时间**而非**距离**的变化 → 产生影像畸变）

**三种畸变 / 效应**（讲义图片文字 + 转写案例）：

| 效应 | 含义 | 转写中的实例 |
|---|---|---|
| **Foreshortening（前坡缩短）** | 地物看上去像**朝探测器倾斜** | 金星上一座小火山，山顶火山口（caldera）看起来偏在左侧，因为雷达从左侧照射，"everything looks like it's leaning towards the detector, but it's actually in the center" |
| **Layover（叠掩）** | 坡度极陡时，山顶回波先于山脚到达，山体「盖」在前面 | 地球上一条流经山谷的冰川，山看起来把冰川挡住了，"but it's not. It's actually laid over."（雷达从图像顶部向下照射） |
| **Shadow（雷达阴影）** | 雷达「看不到」过高过陡地物的背后 | — |
| **Brightness（雷达亮度）** | 同一区域在不同视向下**看起来完全不同** | 金星同一区域两幅影像，"Nothing has changed between these images taken a few years apart" —— 一幅雷达从右照、一幅从左照，突出的粗糙度特征完全不同 |

**为什么会有这些效应**：因为是主动方法，能量来自飞行器而非太阳——老师的类比是 **"it's almost like shining a torch on a feature"**（就像拿手电照物体）。

**雷达影像看起来跟可见光影像不一样**："you're working at longer wavelengths, and so you're kind of dealing more in **roughness** rather than the actual kind of surface itself."（雷达影像本质上是**粗糙度图**，不是可见光意义上的「表面」）

**Ground penetrating radar（GPR，探地雷达）**（转写，讲义只有 SHARAD 一行标题）：
- 极长波长可穿透 **meters, hundreds of meters, even kilometers**。
- 地球上多用于**野外拖行式测量**；卫星 GPR 用于地球较少（因为到现场做更高分辨率的调查更方便）。
- 火星案例：**MRO 上的 SHARAD** 探测 **NPLD（North Polar Layered Deposits，北极层状沉积）**——富冰沉积逐季累积，可见数百万年的层理；另一幅显示近赤道一处可能富冰且过去发生过流动的地貌。

**InSAR 案例**：**ERS-2 SAR interferogram，1999 年土耳其 Izmit 地震**——利用**雷达相位差**成像地表形变，"you can see these kind of patterns come away from the earthquake location"。老师补充：**行星遥感中从未用过 InSAR 测震，因为从未把这类雷达送到别的行星上。**

### 2.19 主动方法之二：Lidar（激光雷达）

- 本质：**"just using lasers rather than radar."**
- **能穿透植被冠层**："it can penetrate through things like trees and canopies and you get **different energy returns**"。
- 讲义配图：**(A) Top view and (B) Side view of LiDAR point cloud-based 3D structure of forest canopy.**（森林冠层三维结构的点云俯视图与侧视图）
- 性能（转写）："super high spatial resolution, super high precision vertically as well, kind of to like **almost centimeters resolution vertically** so you get amazing elevation models."

**DTM vs DEM**（⚠️ **材料的定义与主流用法相反，见勘误表**）：

讲义配图文字原文：**"DTMs include features above the ground surface. DEMs of the bare ground surface."**
转写原文：**"a DTM or digital terrain model which is everything, or a digital elevation model where you can remove the effect of buildings, trees, forests, and you get representation of the ground surface."**

📎 **背景补充（重要，因为这直接影响 W07 地形分析）：** 遥感与测绘文献中**更通行的约定恰好相反**——**DTM（Digital Terrain Model）= 裸地表**，**DSM（Digital Surface Model）= 含建筑与植被的表面**，**DEM** 则常作为泛称或与 DTM 同义。本课材料把两个词的含义对调了。**记住「含地物的模型」与「裸地表模型」这一对概念本身，比记住哪个词对应哪个更重要**；实际使用时务必看数据说明。

### 2.20 材料**未**涉及的内容（务必知道边界）

任务提纲中提到、但**本周三份材料以及整门课程都完全没有出现**的内容，本笔记不予展开、也不代为编造：

- **Supervised / Unsupervised classification（监督 / 非监督分类）**、训练样本采集
- **Confusion matrix（混淆矩阵）、Overall accuracy（总体精度）、Kappa 系数**
- **Change detection（变化检测）的定量方法**（本周只做了**目视 + 时间动画 + 量距**的定性变化观察）
- **NDWI（归一化水体指数）**

（已对全课程 10 周的 Lecture / Practical 做过关键词检索确认。）

📎 **背景补充（仅备一句，勿当材料内容）：** 影像分类是遥感课程的常见后续内容——把每个像元按其多波段光谱特征归入土地覆盖类别，监督分类需要人工勾绘训练样本，精度用混淆矩阵评价（行列分别为分类结果与地面真实，对角线为正确分类数）。**本课不考。**

---

## 三、公式与图表

### 3.1 电磁波速度关系

$$c = v\lambda$$

- **c** = the speed of light（光速），≈ 3 × 10⁸ m s⁻¹
- **v** = frequency（频率，Hz）
- **λ** = wavelength（波长，m）

含义：光速固定，因此**频率与波长成反比**。遥感文献里光学波段习惯用波长（µm）、微波波段习惯用频率（GHz）或波长（cm），是同一件事的两种表述。

> ⚠️ 讲义 OCR 把这条公式渲染成 `𝑐= 𝑣𝜆`，其中 λ 的符号在后面的说明行中丢失（原文写作 " = wavelength"，前面的希腊字母未被识别）。属低质量 OCR 段。

### 3.2 辐射分辨率与位深

$$\text{灰度级数} = 2^{n}\quad (n = \text{bit depth})$$

| n | 级数 |
|---|---|
| 4 | 16 |
| 8 | 256 |
| 10 | 1024 |
| 12 | 4096 |
| 16 | 65,536（📎 补充：Practical 中导出栅格用的 `16 bit unsigned` 即此档） |

### 3.3 光谱指数与波段比值

**通用的归一化差值指数形式**（📎 背景补充：材料只给了具体式子，没有抽象出通式）：

$$\text{Index} = \frac{\text{Band}_A - \text{Band}_B}{\text{Band}_A + \text{Band}_B}$$

取值范围恒为 **−1 到 +1**（📎 背景补充：材料未说明取值范围）。分母的作用是**归一化**——抵消光照强度、坡向、部分大气影响，使不同时相、不同太阳高度角下的影像可比。这也是为什么它比单纯的差值 `A − B` 更常用。

**材料中出现的三个具体指数**：

| 指数 | 公式（材料原文） | 判读 |
|---|---|---|
| **Vegetation Index（= NDVI）** | (B8 − B4)/(B8 + B4)　【Sentinel-2】 | 用于 dense canopy, urban and water features |
| **Moisture Index（= NDMI）** | (B8A − B11)/(B8A + B11)　【Sentinel-2】 | 值高 = 植被含水量高；值低 = 水分胁迫 / 干旱 |
| **Normalised Burn Ratio (NBR)** | (NIR − SWIR)/(NIR + SWIR) | 火烧区判别 |

📎 **背景补充（材料未给出，仅供理解，不是本课考点）：** 若改写成通用波长名，NDVI = (NIR − Red)/(NIR + Red)。对 **Landsat 8 OLI** 就是 **(B5 − B4)/(B5 + B4)**，对 **Sentinel-2** 才是 (B8 − B4)/(B8 + B4)。**材料中没有出现 Landsat 版本的 NDVI 公式。** 典型取值区间（背景知识，材料未给）：清水与雪 < 0；裸土、岩石、建成区约 0–0.2；稀疏植被约 0.2–0.4；茂密健康植被约 0.6–0.9。

**Band ratioing（波段比值）—— Practical 给出的定义与三组比值**：

> "Band ratioing is a technique which **divides the digital numbers i.e. the brightness values**, corresponding to the peaks of high and low reflectance curve of one band by that of another band."

即：**取「反射率曲线的高峰波段」除以「低谷波段」**，把光谱曲线的形状差异放大成一个数值。

| 比值（Landsat 8 波段号） | 目标矿物 |
|---|---|
| **4 / 2**（Red / Blue） | **Iron oxides（铁氧化物）** |
| **6 / 7**（SWIR1 / SWIR2） | **Hydroxyl and clay minerals（羟基与黏土矿物）** |
| **6 / 5**（SWIR1 / NIR） | **Ferrous minerals（亚铁矿物）** |

**Iron Oxide 比值的物理依据（Practical 原文）**：iron oxides / hydroxides 在 **0.63–0.69 µm（Red）高反射**、在 **0.45–0.52 µm（Blue）强吸收**，所以 Red/Blue 的比值在含铁氧化物区域会显著偏大 → **影像上表现为亮区**。

### 3.4 图表描述①：黑体发射谱（Black body emittance spectra）

**怎么画（据讲义标题 + 转写逐句还原）：**

- **横轴**：wavelength（波长），**对数坐标**，从约 0.1 µm 延伸到 100 µm 以上。
- **纵轴**：emittance（发射本领，即能量）——老师说"emittance is just energy, if you will. It doesn't really matter what we call it, but it's energy."
- **图上是一族曲线，每条对应一个黑体温度**，从右下的 **100 K** 一直到左上的高温曲线。
- **两条规律同时体现**：
  1. **温度越高，整条曲线越往上**（总发射能量越大）；
  2. **温度越高，曲线峰值越往左移**（峰值波长越短）——"as something gets hotter, the wavelength moves to the left. It is going to shorter wavelengths."
- **两个必须记住的标注点**：
  - **绿色曲线，300 K** ≈ 地球平均温度 → 峰值在 **略小于 10 µm** 处（热红外）。
  - **橙色曲线，约 5000 K** ≈ 太阳温度 → 峰值在 **略低于 1 µm** 处，**正好落在可见光区**。
- **老师由此推出的结论（会考的「为什么」）**：人眼在可见光工作不是巧合——"it's no coincidence that we see in visible wavelengths because evolution has figured out that the peak energy coming from the sun is at those wavelengths. We could have infrared eyes, but there'd be less energy for us to deal with."

**第二张相关图（发射率）**：横轴同为波长但改为**非对数坐标**，只画太阳。**黑色曲线 = 理想黑体**，**橙色曲线 = 太阳的真实发射谱**。两条大体重合但有偏离——"it fits the same kind of trend, but there are differences because it's not a perfect black body"——这个偏离量就是 **emissivity（发射率）** 所刻画的东西。峰值仍在可见光区。

### 3.5 图表描述②：大气窗口图（能量到达地表的谱）

**在 3.4 第二张图上再叠一条曲线**：

- **黑线**：理想黑体谱。
- **淡黄 / 橙线**：太阳在**大气层顶**的能量谱（平滑）。
- **红线**：**到达地球表面**的能量谱（锯齿状）。

**红线的形态**：整体低于橙线（大气总会削弱），并在若干波长处**骤降到接近零**，形成一个个尖锐的**深谷**。谷之间的平台段就是**大气窗口**。

**每个谷都能归因于一种大气成分**：**water（水汽）、oxygen（氧）、carbon dioxide（二氧化碳）**，以及若干微量气体。

**这张图的实用读法**：把 Landsat / Sentinel 的波段位置画到这张图上——**波段几乎都落在窗口（平台）上**，只有 Coastal Aerosol、Cirrus 这类专用波段刻意落在或靠近吸收带。转写里老师就是这样解读那张 USGS 幻灯片的：横轴波长、纵轴能量、背景灰色是这条红线、彩色小块是各代 Landsat 的波段位置，早期任务在上、最新任务在下。

### 3.6 图表描述③：典型地物光谱反射曲线（本周最重要的一张图）

**怎么画（据讲义 + 转写还原）：**

- **横轴**：wavelength，范围约 **0.4 → 2.5 µm**（可见光 + 近红外，转写说"we've really zoomed in to just the... visible and a bit of the infrared as well, the near infrared"）。可在轴上标出可见光的蓝（0.45）、绿（0.55）、红（0.65）三段与 NIR 起点（0.7）。
- **纵轴**：reflectance（反射率，0–100% 或 0–1）。
- **三条曲线**：**soil（土壤）、vegetation（植被）、clear water（清水）**。

**各曲线的形态（**材料明确讲到的部分**）：**

- **Vegetation（植被）**：在**蓝光**与**红光**处各有一个**明显的吸收谷（dip）**；两谷之间的**绿光**处有一个**小峰**——**这就是植被呈绿色的原因**。进入**红外**后，植被曲线与土壤曲线**明显分开**。
- **Soil（土壤）**：在可见光—红外范围内的走向与植被**显著不同**，这一差异在**更长波长**处尤为明显，正是野火后「植被烧毁 → 裸土」判别的物理基础。
- **Clear water（清水）**：材料把它作为第三条曲线与土壤对比列出，但**没有描述其形态**。

📎 **背景补充（材料未描述、仅为把图补完整，考试请以材料为准）：** 完整的经典曲线还包括——植被在**红光谷之后（约 0.7 µm）反射率陡然跃升**形成 **red edge（红边）**，并在近红外（0.7–1.3 µm）维持在很高的水平（可达 40–50%），这是由叶片内部海绵组织的多次散射造成的；在 1.4、1.9 µm 附近有**水分吸收谷**。土壤曲线较平缓、随波长单调上升，无红边。**清水在近红外几乎完全吸收，反射率趋近于零**——这与植被在近红外的高反射形成最强反差，是水体提取类指数的物理基础。建筑 / 人工地物曲线整体平坦、无特征。**以上四类地物的对比在本周材料中只讲到了植被与土壤两条，水体只被列出而未描述，建筑完全未出现。**

### 3.7 图表描述④：空间分辨率演示序列

一组同一场景、逐级降采样的影像：**100 → 50 → 10 → 5 → 1 → 0.1 m/pixel**。判读能力的跃迁点在 **5 m** 与 **1 m** 之间：5 m 时能分辨色块，1 m 时才能认出街道格局（曼彻斯特 Oxford Road）。**这张图的用法是给「多少米分辨率够用」建立直觉**，而不是背数字。

### 3.8 图表描述⑤：雷达几何畸变示意

**怎么画：**

1. **画一条水平地面线，右侧立一座三角形山。**
2. **从左上方画一束斜向下的雷达波**（look direction），标出 **depression angle（俯角）**。
3. **在图的上方另画一条「斜距轴」（时间轴）**——雷达按**回波到达时间**排列像元，而非按地面水平距离。
4. **Foreshortening**：山的**朝向雷达一侧**（前坡）在斜距轴上被压缩得比实际短 → 视觉上山像**朝雷达倾倒**。
5. **Layover**：当前坡坡度**陡于入射线**时，**山顶回波比山脚更早到达** → 山顶在影像上被画到山脚**前面**，产生「山盖住谷」的假象。
6. **Shadow**：山的**背向雷达一侧**若坡度过陡，雷达波照不到 → 影像上是一片**无信号的黑区**。

**判读要点（转写案例）**：金星火山口看似偏左 = foreshortening（雷达从左照）；地球上山「压住」冰川 = layover（雷达从上方照）。**同一地物在不同视向下形态完全不同**，因此**雷达影像必须知道 look direction 才能正确判读**。

### 3.9 Landsat 8 OLI 波段表（Practical 原文，逐条核对无误）

| Band | 名称 | 波长（µm） | 空间分辨率 |
|---|---|---|---|
| **Band 1** | Coastal Aerosol | 0.43 – 0.45 | 30 m |
| **Band 2** | Blue | 0.450 – 0.51 | 30 m |
| **Band 3** | Green | 0.53 – 0.59 | 30 m |
| **Band 4** | Red | 0.64 – 0.67 | 30 m |
| **Band 5** | Near-Infrared (NIR) | 0.85 – 0.88 | 30 m |
| **Band 6** | SWIR 1 | 1.57 – 1.65 | 30 m |
| **Band 7** | SWIR 2 | 2.11 – 2.29 | 30 m |
| **Band 8** | Panchromatic (PAN) | 0.50 – 0.68 | **15 m** |
| **Band 9** | Cirrus | 1.36 – 1.38 | 30 m |

**读这张表的三个要点**：
1. **Band 8 是唯一的 15 m 波段**，且波长范围（0.50–0.68 µm）**横跨绿+红** → 这正是**做 pan-sharpening 用的全色波段**：光谱宽 → 进光多 → 可以做得更小的像元。**表与 2.16 的 pan-sharpening 在这里对上了。**
2. **Band 1（Coastal Aerosol）与 Band 9（Cirrus）不是给看地表用的**，是给大气/卷云检测用的——对应 2.13 中「落在吸收带的波段用来研究大气」。
3. **Band 4 = Red、Band 5 = NIR**，因此 Landsat 8 的 NDVI 是 **(B5−B4)/(B5+B4)**，**与讲义里 Sentinel-2 的 (B8−B4)/(B8+B4) 编号完全不同**。

📎 **背景补充：** Practical 说 "There are nine spectral bands"，这**只是 OLI（Operational Land Imager）传感器**的 9 个波段。Landsat 8 整星还搭载 **TIRS（Thermal Infrared Sensor）**，提供 **Band 10 与 Band 11 两个热红外波段（约 10.6–12.5 µm，100 m 重采样至 30 m）**，全星共 11 个波段。**Practical 未提及这两个波段。**

📎 **背景补充：Sentinel-2 关键波段对照**（Practical §6 要求「用下面的信息选择合适的波段」但**该信息以图片形式存在、md 中无文字**，故此处补充最低限度的对照，用时请核对官方文档）：Sentinel-2 MSI 的 **B2 = Blue（约 0.49 µm，10 m）**、**B3 = Green（0.56 µm，10 m）**、**B4 = Red（0.665 µm，10 m）**、**B8 = NIR（0.842 µm，10 m）**、**B8A = Narrow NIR（0.865 µm，20 m）**、**B11 = SWIR1（1.61 µm，20 m）**、**B12 = SWIR2（2.19 µm，20 m）**。因此 Sentinel-2 的 Iron Oxide 比值应为 **B4 / B2**（与 Landsat 8 的 4/2 数字巧合相同，但**含义来源不同，不可当作通则**）。

---

## 四、课堂补充

本周转写长达 8,340 词，且**讲义大量页面只有标题和图、没有正文文字**，所以**转写承担了本周绝大部分的实质内容**。以下按讲课顺序提炼讲义上没有、只有口头讲的部分。

### 4.1 关于讲师与本次课的定位

- 主讲人是 **Peter Grindrod**（转写 ASR 误写为 "Grindrad"），任职于 **Natural History Museum, London**，在曼大有荣誉职位。**不是课程负责人 Ray Burgess。**
- 他自陈的「私心」：**"to try and almost convert some of you to planetary science along the way"**（顺便把你们中的一些人拐去做行星科学）。
- **这解释了本周讲义为什么充满火星、金星、月球的例子**——遥感的技术是同一套，只是被用在了行星尺度上。复习时要有意识地**把行星案例翻译回地球场景**。
- 他开场讲的那张背景图**不是地球，是火星**，是一个「希望四年后降落一台巡视器」的候选着陆点。**关键的一句**：**"we've used remote sensing as the only tool to choose that landing site, and it took us about five years."**（选址完全靠遥感，花了大约五年）——这是全课对「遥感有什么用」最有力的一个回答。

### 4.2 时间安排与内容取舍（对复习范围的直接提示）

老师在课上多次自述进度紧张，这些话本身就是范围提示：

- 开场："there's quite a lot to get through today... very briefly, **depending if I run out of time or not**, touch on radar and LIDAR as well."
- 讲完光谱反射后："**Okay, that was A-level physics in about five minutes**, but as relevant to remote sensing."
- 讲雷达前："**Okay, some of the pre-processing in the last 10 minutes.**"
- 结尾："**Okay, now I know I rushed the last bit** which is kind of tend to, so I need to stop."

**推论**：EMR / 分辨率 / 卫星 / 预处理与增强这四块是主体；**Radar 与 Lidar 讲得很快、深度有限**，但讲义上有完整的 slide，**复习时应以讲义列表为准**（尤其是雷达回波强度的两组决定因素、三种几何畸变）。

老师还提到 **"Take the quiz to test your basic understanding (on BB)"**（讲义 Homework 页）和 **"Read Chapter 6 of course textbook: Remote Sensing"**（教科书是 Liu & Mason, *Image Processing and GIS for Remote Sensing*）。课末有 **QR code**（应为反馈或资源链接，转写未说明用途）。

### 4.3 探测器的历史：三个不该跳过的故事

这三段在讲义上只有图和一行标题，全靠转写：

1. **Ranger 9（1965 年 3 月 24 日，月球）**——"basically a TV camera strapped to the front of a spacecraft that was just pointed at the moon... they just pointed at the moon and they just crashed and they just analyzed every frame as it got closer and closer."（撞击式探测，逐帧分析）老师的评价：**"an amazing achievement at the time, but fair to say you will never work with a detector system like this today."**
2. **同一地点的现代影像**：用 **Lunar Reconnaissance Orbiter (LRO) 的 Narrow Angle Camera**，分辨率 **40 cm/pixel**，能清楚看到 Ranger 9 撞出来的那个 **10 m 直径撞击坑**（亮溅射物 + 暗图案）。**这一对照就是「时间分辨率 + 空间分辨率共同进步」最直观的例子。**
3. **1960 年代的胶片间谍卫星**（大多已解密）——"an actual film camera was launched on a satellite, orbited the earth, took photos on the film. That film, sometimes they're actually developed and processed in orbit, and the developed negatives were then **dropped in a capsule on a parachute and caught with a hook from an aeroplane**."（在轨冲洗，负片装胶囊伞降，由飞机用钩子空中回收）老师的类比是蝙蝠侠被飞机勾走的桥段。
   **科学价值**：**"If you wanted to say look at climate change, we have very high resolution film images from the 1960s."**（这批影像可作为气候变化研究的早期基线数据）

### 4.4 行星影像的分辨率标尺（用来校准直觉）

- **火星 HiRISE 级别**：**25 cm/pixel** —— 好到能**跟踪 Curiosity 巡视器在地面上行驶**。
- **月球大部分区域**：约 **1 m/pixel**，局部更高。
- **曼彻斯特的 Google Earth 影像**：约 **10 cm/pixel**，且几乎肯定是**航空影像而非卫星影像**——"That's why the images are so good."（这条对判断影像来源很有用：**极高分辨率的城市影像通常来自飞机**。）

### 4.5 时间分辨率的两个案例

**火星（10 年对比）**：同一区域、同一影像条件，相隔 10 年——
- 出现大量**黑色条纹**：由 **dust devils（尘卷风）**造成，"very small tornado like features that remove the dust and they appear dark"（卷走亮色浮尘、露出暗色下垫面）。
- 出现一个**新撞击坑**："This black splodge here is actually a new crater **about 10 meters across** that formed in this time period."
- 结论："So we can see **active processes** on Mars."

**地球：玻利维亚的湖（Landsat 三幅时序影像）**——曾是**玻利维亚第二大湖**的一个**咸水湖**，因**农业与采矿**引流，过去几十年入湖水量被截，**如今已不可逆地干涸消失**。老师把这作为「遥感证明气候变化」的代表：

> "we can use evidence, over **30, 40 years** of satellite images now that show **geological processes happening on human timescales** because of climate change."

（📎 背景补充：该湖的名称材料未提及，从描述判断应为 **Lake Poopó（波波湖）**。此为背景推断，非材料内容。）

### 4.6 Magellan vs Galileo：为什么要根据目标选传感器

这是全课**关于「主动 / 被动」最好的一个对照实验**，讲义上只有一行图注：

| | **Magellan** | **Galileo** |
|---|---|---|
| 目标 | **金星**（1990 年代初） | **木星**（1990 年代中—2000 年代初） |
| 飞行器 | 尺寸相近，**都从航天飞机上发射** | 同左 |
| 障碍 | 金星有**完全遮蔽地表的大气与云层**，可见光与多数红外都看不穿 | 无此问题，太阳能量在各波长仍够用 |
| 载荷 | **基本只有一台仪器：主动雷达** —— 穿透云层，主动成像地表 | **一大堆仪器，全部被动** —— UV、可见光、近红外、远红外 |

老师的总结：**"these had very different instruments on very similar spacecraft just because of the conditions and the energy available."**（同样的飞行器，因为环境条件与可用能量不同，载荷完全不同）——**选传感器的第一问永远是「那里有什么能量可用、有什么障碍」。**

### 4.7 Landsat Next：为什么老师两次强调它必须落实

- **Landsat 9（当前在役）**：单星，需要较长时间才能拼出一幅全球影像。
- **Landsat Next**：**两颗卫星在相近轨道上一前一后**，**约 5–6 天即可实现全球覆盖**，随后开始重复。
- 老师的原话："this is why I said it's really important that **Landsat Next actually happens and isn't canceled**... it's an amazing, amazing resource to get repeat coverage and global coverage as well."
- 关于 Landsat 的连续性：**"we just need to hope that this program called Landsat Next actually does happen and can keep on going with this Landsat legacy."**

**Landsat 时间线图的读法**（讲义 slide 无文字）：横轴时间，每颗卫星一条横线。**Landsat 4 和 5 在轨时间很长；Landsat 6 发射失败（"Landsat 6 didn't work"）；Landsat 7 顶上。所有线条彼此重叠**——这就是「连续覆盖」的可视化表达。

### 4.8 大气校正的一个具体做法（火星的 Olympus Mons 方法）

讲义只写了"there's a few ways of doing that"，转写给了一个非常具体、非常漂亮的方法：

> "one of the ways we do this on Mars, for example, is that we collect data at the top of a huge volcano called **Olympus Mons**, which is actually so tall, it's actually **poking out of the top of the atmosphere**. The effects of the atmosphere at the top of Olympus Mons is really, really small. And so we take some data there, and then we collect data from a deep, deep part of the surface, and we can **look at the difference**, and we can remove the atmospheric [effect]."

**方法的骨架**：找一个**大气路径极短的参考点**（高山顶）和一个**大气路径很长的点**（低洼处），**两者之差即大气贡献**，把它扣掉。老师说地球上也能做类似的事。

📎 **背景补充：** 这一思路在地球遥感中对应的标准方法族称为 **empirical line / dark object subtraction 一类的经验型大气校正**，材料未使用这些名称。

### 4.9 NBR 与洛杉矶野火：band ratio 的实战判读

- 案例：**Los Angeles, 2017 年大火**（讲义另标注 **Eagle Bluff wildfire, 31st July 2023**）。
- 展示方式：**上图为可见光影像，下图为 NBR**。
- 判读："all those **red areas** in the bottom image are basically areas where the **vegetation has been burnt**."
- 物理基础（老师明确点出）："it's exploiting the response, **the difference between kind of healthy vegetation and burnt vegetation**" —— 右侧配了**两条光谱曲线**（健康 vs 烧毁植被）。

**这段的教学意义**：band ratio 不是数学游戏，**每一个指数背后都必须能指出「哪两条光谱曲线在哪个波段分得最开」**。这也是复习时判断一个指数是否合理的通用方法。

### 4.10 老师对 band maths 起源的一句话

> "you also start to see some **band maths** creeping in here as well. So there'll be subtraction, addition, ratios that **people have figured out over the years** to best emphasize different spectral features."

**这些指数是经验积累的产物，不是从第一性原理推出来的。** 所以记忆时**记「用什么波段、为什么这两个波段」比记公式本身更重要**。

### 4.11 反复出现的主题：数据量的代价

这条线索在转写里至少出现四次，值得单独拎出来：

1. 空间分辨率越高 → 需要**更大的望远镜**、更大的数据量、更高的下传速率。
2. 位深越高 → 需要**更大的星上存储**、更高的下传速率。
3. 推扫影像**长度受星上内存限制**，单幅常达**数 GB**——"These are hard to deal with."
4. 总结句："All of this comes at the **data volume cost**."

**这是把四种分辨率串起来的那根线**：它们之所以要权衡，根本原因是**下传带宽与星上存储是硬约束**。

### 4.12 ⚠️ 讲义中来自低质量 OCR 的段落（阅读原讲义时须警惕）

本周讲义 md 由 PDF 转换而来，以下部分**文字层缺失或识别质量低**，读到时不要当作老师的原意：

| 位置 | 问题类型 |
|---|---|
| **Electromagnetic Spectrum 表格**（讲义第 139–151 行） | **单位系统性错误**：所有 µm 被识别为 **mm**（Ultraviolet / Visible / Infrared / Near / Mid / Far infrared 六行）。另有 "Passive **or**Active" 缺空格 |
| **速度公式行**（"Velocity of EM energy, 𝑐= 𝑣𝜆"） | 说明行中 **λ 的希腊字母丢失**，只剩 " = wavelength" |
| **文件末尾 "OCR 补充（原文中无文字层的页面）→ Page 38**" | 明确标注为图片 OCR 结果，内容为 `Landsat orbits / Landsat Next A ' / Elapsed: Odays 1.50 hours` —— **`Odays` 应为 `0 days`（字母 O 误识数字 0）**，`A '` 为残缺片段。**这一页实为 Landsat 9 与 Landsat Next 覆盖率对比动画的截图，无可用文字信息** |
| **大量 `<!-- Start of picture text -->` 块** | 这些是从**图片里**抠出的零散文字（如 "red / green"、"SPATIAL"、"TEMPORAL"、"RADAR Foreshortening"、"DTM / DEM"），**只是图上的标签，不是完整句子**。这些页面的实质内容**必须靠转写补齐** |
| **"higherresolution"**（Pan-sharpening 定义中） | 缺空格，应为 "higher-resolution" |
| **多处 slide 只有标题无正文**（Atmospheric Interactions、Surface Interactions 的图、Landsat spectral bands、Sentinel spectral bands、Landsat timeline、Pan-sharpening、Contrast stretching、各 Radar 页、LiDAR 页） | **原 PDF 该页主体就是图**，md 中只剩标题 + 链接。**本笔记中这些内容全部依据转写还原，已在正文标明来源** |

---

## 五、Practical 要点

> **本段目标：不打开原教程，也能在 ArcGIS Online + ArcGIS Pro 里把整个流程重做一遍。**
> 本 Practical 改编自 **ESRI training "Spatial Analysis with ArcGIS Pro"**。全流程分两大阶段：**§3–4 在 ArcGIS Online（浏览器）做时序可视化，§5–6 在 ArcGIS Pro（桌面）做光谱分析。**

### 5.0 任务背景与目标

**研究对象：Chuquicamata mine, northern Chile（智利北部丘基卡马塔矿）**
- 世界上**按开采体积计最大的露天铜矿**。
- **1882 年开矿，至今仍在生产**，近几十年显著扩张。
- **2019 年**开始转入**地下开采**，作为数十亿美元改造工程的一部分，目标是延长矿山寿命**至少 40 年**。

**任务**：用 Landsat 影像监测矿区扩张，并分析对周边环境的影响。

**关键概念：Multidimensional raster data（多维栅格数据）/ image cubes（影像立方体）**
> "consists of rasters or imagery that have been collected over **multiple times, depths, or heights** and are **stacked into a single dataset**."（在多个时间、深度或高度上采集的栅格被**堆叠成单一数据集**）

📎 **背景补充：** 这与 W02 学过的普通单时相 raster 的区别在于**多了一个维度（通常是时间）**，因此可以直接在图层上做时间动画，而不必手工加载几十个独立图层。

---

### 5.1 阶段一 · ArcGIS Online：加载历史 Landsat 影像

#### 步骤 1 — 定位研究区

1. **登录 ArcGIS Online 的 UoM 账号**（Sign in to your ArcGIS online UoM account）。
2. 在功能区（ribbon）上点击 **Map**。
3. 在地图**右上角的 search box** 中输入 **`Chuquicamata mine`**，按 **Enter**。
4. **关闭弹出的 pop-up**。
5. 用 **zoom tools**，点 **Zoom Out** 按钮 **一次**，让整个矿区都显示出来。

#### 步骤 2 — 换底图并加载多光谱 Landsat 图层

6. 左侧栏点击 **More**（或 **…**）→ 选 **Basemap** → 选 **Light Grey Canvas**。
   - **为什么**：教程说这样做是为了**让标注（labels）显示出来**。灰底图不会与影像抢色，标注提供地理背景与方位参照。
7. 右侧点击 **Layers** → 选 **Living Atlas**（ArcGIS Living Atlas of the World）。
8. 在搜索框中搜 **`Multispectral`** → Enter。
9. 在结果中找到 **Multispectral Landsat** 图层，**添加到地图**。
   - 教程说明：Landsat 的庞大影像存档**已被压缩进一个数据图层**，可在 ArcGIS Online 中直接浏览。

#### 步骤 3 — ⚠️ 清除默认时间过滤器（关键步骤，漏掉就看不到历史影像）

> **默认情况下，Multispectral Landsat 图层带有一个过滤器，只显示最近期的影像。**

10. 右侧打开 **Filter window**。
11. 点击 **Clear all** 清除过滤器 → 这样才能访问 **1970 年代以来的全部影像**。

#### 步骤 4 — 判读影像上应该看到什么（考察目视解译能力）

教程明列四类地物，**这是本 Practical 唯一的「判读题」，务必记住**：

| 地物 | 影像特征与背景 |
|---|---|
| **The mining town of Chuquicamata（矿业城镇）** | **2007 年因为离主坑太近而被废弃** |
| **Terrace-like mining benches（阶梯状开采台阶）** | 在坑内呈**同心环状（concentric rings）**；作用是**支撑作业设备**并**拦截滑落的碎屑（catch material from debris slides）** |
| **Piles of waste rock（废石堆）** | 紧邻坑体；含**低品位可采金属** |
| **Tailings ponds（尾矿池）** | 存放**选矿富集过程后的残余物料** |

#### 步骤 5 — 保存地图并写元数据

12. 右侧点 **Save and open** → **Save as**。
13. **title**：`Change in Chuquicamata mine, Chile`
14. **tags**（每输入一个按 Enter）：`Chile`、`Historical`、`Imagery`
15. **summary**：`This map is a collection of images showing four decades of change in the Chuquicamata mine, Chile`
16. 点 **Save**。

> **呼应 W02/W03**：tags 与 summary 就是**元数据（metadata）**。W03 讲过元数据的作用是让数据可被发现、可被正确使用——这里是一次真实的实践。

---

### 5.2 阶段一（续）· 时间动画（Time animation）

#### 步骤 6 — 启用时间

17. 在 **Contents pane** 中，指向 **Multispectral Landsat** 图层，切换 **Enable time**（启用时间）。

**会发生什么（教程预警，不要以为是出错）**：
- 底部出现 **time animation toolbar（时间动画工具条）**。
- 地图切换到时间轴上**第一个日期区间：July 24, 1972 – July 24, 1977**。
- **地图会变成纯白或纯蓝一片** —— "because of an **error in capturing the first image of this area**"。这是**数据本身的问题，不是操作失误**。
- 教程说明：**Landsat 项目始于 1972 年，早期影像质量常常很差**，后面会用过滤器把这些问题影像剔掉。

18. 在 time animation 工具条上点 **Play/Pause** → 时间轴按时间顺序播放全部可用影像。

**常见现象与处理**：
- **有些影像还没加载完时间轴就跳到下一幅** → **多播放几遍**（"You may need to play the animation more than once to see all of the images"）。
- **默认播放速度太快，不利于观察变化** → 下一步调慢。

#### 步骤 7 — 配置时间动画

19. 点 **Configure** 按钮 → 在 **Play rate** 窗口把播放速度调到**最慢（slowest setting）** → 关闭窗口。

**再播放时会遇到的第二个问题**：时间滑块没动、影像却变了。**原因**：时间轴当前按**五年间隔**划分，一个间隔内可能有多幅影像。

20. **Pause** 动画 → 点 **Configure**：
    - 在 **Start and end points** 窗口：**Start time** 设为 `7/25/1972 12:00 AM`，**End time** 设为 `1/1/1980 12:00 AM`。
    - 在 **Time intervals** 窗口：选 **Length of one interval**，改为 **1 year**。
21. 关闭选项，再次播放。

**为什么要缩小时间范围**：把间隔降到 1 年会让全时段动画播放极慢，所以**同时把时间跨度缩到 1972–1980**，分十年段逐段看，"you can look at the imagery in **more manageable 10-year time periods** and also choose the **best image from each decade**"。

#### 步骤 8 — 读取影像的采集日期

22. 观察结果：**1972–1980 年间大多数年份没有影像**；**1973 和 1975 年**各有一幅可用影像。
23. **点击地图中的影像** → 打开该影像的 **pop-up**，读取 **acquisition date（采集日期）**。
    - 该幅的采集日期为 **February 15, 1975**。

**教程给出的最终选片结果（直接抄下来用）**：

| Decade（年代） | Date（采集日期） |
|---|---|
| **1970s** | **2/15/1975** |
| **1980s** | **No image**（该年代无影像，演示中此十年为空白） |
| **1990s** | **4/4/1990** |
| **2000s** | **10/22/2005** |
| **2010s** | **11/29/2013** |
| **2020s** | **1/28/2024** |

**关于默认显示方式（要点）**：
> "The Landsat images are displayed by default as a **natural colour composite**, where the **red, green, and blue bands are displayed with the corresponding channels**, so features in the image are rendered as the human eye would see them in real life."

#### 步骤 9 — 用属性过滤器筛出这五幅影像

24. 右侧打开 **Filter** 页，确认已选中 **Multispectral Landsat** 图层。
25. 点 **Add new** **五次**，得到五条过滤表达式。
26. 顶部下拉菜单选 **`Any of the following are true`**（**关键：必须是 OR 逻辑，不是 AND**——否则五个条件互斥，结果为空）。
27. 每条表达式：
    - **field** 选 **Acquisition Date**
    - **运算符**选 **`is between`**（这样可以输入两个时间戳，即**该采集日当天的起止时刻**）
28. 依次填入五个日期：**15/2/1975、4/4/1990、22/10/2005、29/11/2013、28/01/2024**。
    > ⚠️ **教程明确提示的坑**：**可能必须先设 End date**，因为界面不允许 Start date 晚于 End date。
29. 点 **Save**。

**⚠️ 此时影像可能仍然不显示** —— 因为时间动画工具条还停留在上一步设定的窄日期范围内。

30. 在动画工具条上点 **Configure**：
    - **Start date** 改为 `01/01/1970`，**End date** 改为影像中最新的日期。
    - 在 **Time intervals** 页签把间隔设为 **10 years**。
    - 关闭 **Configuration** 窗口。
31. 点 **Play/Pause** 查看。**在最慢速度下可能仍需播放几轮**才能全部载入。

**预期结果**：只显示筛选出的五个日期的影像；**1980–1990 之间空白**（该年代无影像）。

#### 步骤 10 — 量测主坑尺寸（定量变化检测）

32. 用时间动画定位到 **1990 年代**的影像。
33. 右侧面板打开 **Map Tools** → 点 **Measurement**。
34. **单击**主坑**最南端**，**双击**主坑**最北端**，得到距离读数。
    - **1990 年，主坑长约 3.5 km。**
35. 切换到 **2020 年代**最新影像，重新量测。
    - **主坑现长约 4 km。**
    - 并注意：**1990–2024 年间还出现或扩大了若干次生坑（secondary pits）。**
36. **关闭 Measure Distance 工具。**

> **这一步是全 Practical 唯一的定量结论**，也是「变化检测」在本课的实现方式：**目视 + 时序动画 + 距离量测**，不涉及任何自动化的变化检测算法。

---

### 5.3 阶段二 · ArcGIS Pro：加载与导出影像

#### 步骤 11 — 在 ArcGIS Pro 中加载同一图层

37. 打开 **ArcGIS Pro**，**新建一个 project**。
38. 在 **Catalog pane** 中选 **Portal** → **Living Atlas**，搜索框输入 **`multispectral`**。
39. 结果中出现 **Multispectral Landsat** 后，**选中并拖拽（select and drag）到 Contents pane**。
    - **⚠️ 若拖拽无效**：**右键该图层 → 选 `Add to Current Map`**。（教程明确给了这个备选路径）
40. 搜索 **`Chuquicamata copper mine`** 定位 → 应出现一幅**自然色影像**。

#### 步骤 12 — 查看处理模板（Processing Templates）

41. 选中 **Multispectral Landsat** 图层 → 功能区点 **Data** 标签页 → 查看可用的 **Processing Templates**，每个都附有简短说明。
    - **概念**：影像服务（image service）可以在服务端按不同模板动态渲染，**不需要下载原始数据就能切换波段组合 / 增强方式**。

#### 步骤 13 — 设定模板并导出为本地栅格

42. 把 **Processing Template** 改为 **`Natural Colour with DRA`**。
    - 📎 **背景补充：DRA = Dynamic Range Adjustment（动态范围调整）**，即按**当前显示范围内**的像元值动态做对比度拉伸。教程未解释这个缩写。**这与讲义 2.16 的 contrast stretching 是同一件事，只是自动化、随视图变化。**
43. **右键 Multispectral Landsat 图层 → Data → Export Raster**。
44. 在 **Export Raster** 窗格中设置：

| 参数 | 值 | 说明 |
|---|---|---|
| **输出栅格名称** | `Chuquicamata_Landsat` | |
| **Clipping Geometry** | **`Current Display Extent`** | 只导出**当前视图范围**，避免下载整个影像服务 |
| **Pixel Type** | **`16 bit unsigned`** | 教程注明 **"this is default for Landsat imagery"**（Landsat 影像的默认位深） |

45. 点 **Export**。
    - 结果：**Landsat 影像服务的一部分被存到本地磁盘**，并作为新图层出现在 Contents pane 中。

> **⚠️ 导出前务必先把矿区调整到合适的视图范围**（教程原文："With the mine in view as the image below"）——因为 `Current Display Extent` 直接决定了导出的范围。视图缩得太小会漏掉矿区，缩得太大文件会很大。
> **与讲义的对应**：`16 bit unsigned` 就是 2.12 的 **radiometric resolution**，2¹⁶ = 65,536 级。

---

### 5.4 阶段二（续）· 光谱信息与矿物指数

#### 地质背景（教程给的科学动机，理解 band ratio 的前提）

> "Mineral deposits commonly show a spatial association with **hydrothermal alteration（热液蚀变）** of the surrounding rocks which has proved useful in the exploration of mineral deposits. Hydrothermal alteration is frequently identified by the presence of **iron-oxides（铁氧化物）** and **hydroxyl-bearing minerals (clays)（含羟基矿物 / 黏土）**. These minerals have **diagnostic spectral features in the infrared region** of the electromagnetic spectrum that allow their **remote identification**."

**逻辑链（必须能自己复述）**：**铜矿床 → 周围岩石发生热液蚀变 → 蚀变产生铁氧化物与黏土矿物 → 这些矿物在红外有诊断性光谱特征 → 波段比值把这些特征放大成一张图 → 亮区提示可能的蚀变带。**

这正好回扣讲义 2.8 中「infrared 有 many diagnostic features」那句话。

#### 步骤 14 — 计算 Iron Oxide 指数

46. 功能区点 **Imagery** 标签页 → 点 **Indices** → 在 **Geology** 组中点 **Iron Oxide** 按钮。
47. 结果：**地图中新增一个 multidimensional layer（多维图层）**。

**判读（教程原文）**：
- **Bright areas = 铁氧化物含量较高的地方**；
- 注意它们**与自然色影像上的褐 / 红色区域对应**（"notice how these correspond to the brown/reddish areas on the natural colour image"）——**这是一次自我验证：指数结果应该和肉眼看到的颜色一致。**
- 另外注意：**坑体与废石堆相对较暗，说明铁氧化物含量较低。**

#### 步骤 15 — 计算 Clay Minerals 指数

48. 同样在 **Imagery → Indices** 中添加 **Clay Minerals** 索引。
49. **思考题（教程留的）**：**黏土矿物最集中在哪里？**
    - （教程未给答案。结合 §5.4 开头的地质背景，应在**热液蚀变带**——即 6/7 比值高的区域。）
50. **Save** 项目。

📎 **背景补充：** ArcGIS Pro 的 **Imagery → Indices** 库中，Geology 组的三个索引与教程列出的三个比值一一对应（Iron Oxide = Red/Blue，Clay Minerals = SWIR1/SWIR2，Ferrous Minerals = SWIR1/NIR）。教程只让点了前两个，**Ferrous Minerals 只在比值列表中出现、未要求实做**。

---

### 5.5 阶段三 · Sentinel-2 影像与波段自选

51. 在 **Catalog pane → Portal** → 连接 **Living Atlas** → 搜索 **`Sentinel-2 views`**（教程原文误写为 "Sentinal-2"）。
52. **立刻能观察到的差异**：
    - **Sentinel-2：10 m 像元分辨率**
    - **Landsat 8：30 m**
    - 教程原话："The better spatial resolution of the Sentinel 2 imagery... versus the Landsat 8 image... is **immediately apparent**."
53. **使用 Iron Oxide 索引** → **⚠️ 这次系统会提示你选择波段（"you will be prompted for the bands"）**。
54. **选波段的依据（教程给的判据，务必自己会推）**：
    > "Recall that iron oxides have **high reflectance at 0.63–0.69 µm (Red band)** and **high absorption at 0.45–0.52 µm (Blue band)**."
    - 即：**分子选落在 0.63–0.69 µm 的波段，分母选落在 0.45–0.52 µm 的波段。**
    - 对 Sentinel-2 → **Red = B4，Blue = B2**（见 3.9 的背景补充）。

> **⚠️ 这一步是整个 Practical 的「考点浓缩」**：软件在 Landsat 上能自动认出波段，换到 Sentinel-2 就要你自己指定——**因为两颗卫星的波段编号体系不同**。这恰恰是本周最重要的易错点（见第六节）。
>
> ⚠️ 教程说"Use the information below to select the appropriate bands"，但**该「information」在原 PDF 中是一张图，md 转换后丢失**。做题时请自行查阅 Sentinel-2 官方波段表。

### 5.6 资源

- **USGS Earth Shots — Chuquicamata Mine, Chile**：`https://eros.usgs.gov/earthshots/chuquicamata-mine-chile`（原文写作 `htps://`，为 OCR 缺字）

### 5.7 全流程一页速查

```
【ArcGIS Online】
Map → search "Chuquicamata mine" → Zoom Out ×1
  → More/… → Basemap → Light Grey Canvas
  → Layers → Living Atlas → search "Multispectral" → add Multispectral Landsat
  → Filter → Clear all                     ← 不清就只有近期影像
  → Save and open → Save as（title/tags/summary）
  → Contents pane → Enable time
  → Configure → Play rate = slowest
  → Configure → Start/End time + Time intervals = 1 year   ← 逐十年找片
  → 点影像 pop-up 读 acquisition date
  → Filter → Add new ×5 → "Any of the following are true"
       → Acquisition Date / is between（先填 End date！）→ Save
  → Configure → 1970–最新，interval = 10 years → Play
  → Map Tools → Measurement → 单击南端、双击北端  （1990: 3.5 km → 2020s: 4 km）

【ArcGIS Pro】
新建 project → Catalog → Portal → Living Atlas → "multispectral"
  → 拖到 Contents（或右键 Add to Current Map）
  → search "Chuquicamata copper mine"
  → ribbon Data → Processing Templates → Natural Colour with DRA
  → 右键图层 → Data → Export Raster
       name = Chuquicamata_Landsat
       Clipping Geometry = Current Display Extent
       Pixel Type = 16 bit unsigned
  → ribbon Imagery → Indices → Geology → Iron Oxide      （亮 = 高铁氧化物）
  → Imagery → Indices → Clay Minerals
  → Save

【Sentinel-2】
Catalog → Portal → Living Atlas → "Sentinel-2 views"
  → Iron Oxide index → 手动指定波段：Red = B4（0.63–0.69 µm），Blue = B2（0.45–0.52 µm）
```

---

## 六、易错点 / 重点难点

### 6.1 ⚠️ 波段编号：Landsat 8 与 Sentinel-2 绝不能混用（本周头号易错点）

**这是本周最容易失分、也是 Practical 专门设计来考的地方。**

| 波长含义 | **Landsat 8 OLI** | **Sentinel-2 MSI** |
|---|---|---|
| Blue | **B2** | **B2** |
| Green | **B3** | **B3** |
| Red | **B4** | **B4** |
| **NIR** | **B5** | **B8** ⚠️ |
| **SWIR 1** | **B6** | **B11** ⚠️ |
| **SWIR 2** | **B7** | **B12** ⚠️ |

**后果**：
- **NDVI**：Landsat 8 是 **(B5−B4)/(B5+B4)**；Sentinel-2 是 **(B8−B4)/(B8+B4)**。讲义只给了 Sentinel-2 版本，**直接套到 Landsat 上就是错的**（B8 在 Landsat 8 上是 15 m 的全色波段！）。
- **讲义那份「波段组合列表」（Natural Colour / Color Infrared / Agriculture / Geology…）全部是 Sentinel-2 编号**，尽管转写里老师说的是 "For Landsat"（见勘误表）。
- **可见光三波段在两颗星上恰好都是 B2/B3/B4**，这个巧合最容易造成「以为都一样」的错觉——**分歧全在红外端。**

**记忆法**：**Sentinel-2 波段更多（13 个），所以红外波段的编号被「挤」到更大的数字上去了。** 遇到红外波段务必查表。

### 6.2 归一化指数的分子分母顺序不能反

`(NIR − Red)/(NIR + Red)`，**大的在前、小的在后**。写反了会得到符号相反的结果：**植被区从 +0.8 变成 −0.8**，判读结论完全颠倒。

**自检方法（比背公式可靠）**：**问自己「哪种地物应该得高值」**。NDVI 要让植被得高值 → 植被在 NIR 高、在 Red 低 → 所以分子必须是 **NIR − Red**。NBR 要让**健康植被**得高值、火烧区得低值 → **NIR − SWIR**。Moisture Index 要让**湿润植被**得高值 → **B8A − B11**。**先想物理，再写公式。**

### 6.3 波段比值 vs 归一化差值：不是一回事

- **Band ratio（比值）**：`A / B` —— Practical 的 Iron Oxide (4/2)、Clay (6/7)、Ferrous (6/5)。**取值范围 0 到 +∞，无上界。**
- **Normalised difference（归一化差值）**：`(A−B)/(A+B)` —— 讲义的 Vegetation / Moisture Index、NBR。**取值恒在 −1 到 +1。**

**两者物理动机相同（放大两波段的差异），但取值范围与统计性质完全不同**，做符号系统（颜色分级）时不能混着来。

### 6.4 分辨率的四个「resolution」不要串

学生最常见的混淆是**把 spectral 和 radiometric 搞反**：

| | 问的是 | 单位 |
|---|---|---|
| **Spatial** | 一个像元代表地面多大 | m |
| **Spectral** | 有多少个波段、波段有多窄 | 个数 / µm |
| **Radiometric** | 每个像元能分多少级亮度 | bit / 级数 |
| **Temporal** | 多久重访一次 | 天 / 分钟 |

**口诀**：**空间 = 多小；光谱 = 多少色；辐射 = 多少级；时间 = 多久一次。**

**且必须记住它们是相互权衡的**——考「为什么高分辨率卫星的重访周期反而长」这类题时，答案就是幅宽小 + 数据量大。

### 6.5 讲义中 DTM / DEM 的定义与主流用法相反

**本课材料**：DTM = 含地面以上地物；DEM = 裸地表。
**主流用法**：DTM = 裸地表；**DSM** = 含地物；DEM 常为泛称。

**应试策略**：本课考试请按**材料的定义**答；但读外部文献、做 W07 地形分析和大三独立项目时，**一定要看数据说明，不要靠词名判断**。（详见勘误表）

### 6.6 未做大气校正就跨时相比较

讲义把 radiometric correction 的目的写得很清楚：**"correct an image for atmospheric effects and scene illumination"**。

**为什么这条重要**：本 Practical 的核心操作就是**把 1975 / 1990 / 2005 / 2013 / 2024 五个时相摆在一起看**。这五幅影像的**太阳高度角、大气状态、传感器（MSS/TM/ETM+/OLI）全都不同**。
- **做目视对比、量测坑的长度** → 影响不大（几何量不依赖辐射值）。
- **但若要比较 NDVI 数值、判断「植被变好了还是变差了」** → **必须先做大气校正到 surface reflectance，否则比的是大气而不是地面。**

📎 **背景补充：** 归一化指数（分母求和）本身能抵消一部分乘性的光照差异，这是它比单波段差值稳健的原因，**但抵消不了大气的加性散射项**。材料未讨论这一点。

### 6.7 「亮区 = 高含量」不等于「亮区 = 矿床」

Practical 说 Iron Oxide 指数的 **bright areas = 铁氧化物含量高**。**但这只是一个光谱指示，不是地面真实。**

- 教程自己就要求做交叉验证——「注意这些亮区**是否**与自然色影像上的褐红色区域对应」。
- **同一个指数会被很多东西触发**：红色屋顶、裸露的红土、氧化的废石堆都可能是亮的。
- **正确的表述**：「该区域的光谱响应与铁氧化物一致，**提示可能存在**热液蚀变」，而不是「这里有铜矿」。

### 6.8 时间过滤器与时间动画是两套独立机制

Practical 里最容易卡住的一步：**Filter 已经保存了，但地图上什么都不显示。**

**原因**：**Filter（属性过滤）**筛的是「哪些影像有资格显示」，**Time animation（时间动画配置）**决定的是「当前时间窗口是哪一段」。**两者必须都放开，影像才出得来。** 教程明确写了这一点，做的时候一定要记得回去把动画的 Start/End date 改成 1970 – 最新。

### 6.9 日期格式陷阱

Practical 中**同时出现了美式和英式日期**：选片表用 `2/15/1975`（月/日/年），过滤器步骤用 `15/2/1975`（日/月/年）。**输入前先确认软件当前的区域设置**，否则 `4/4/1990` 这种自反日期看不出问题，但 `10/22/2005` 会直接报错、`1/28/2024` 可能被误解析。

### 6.10 雷达影像不看 look direction 就判读

**同一地物在不同视向下形态完全不同**（转写里的金星双图就是为此设计的）。看到「山压住冰川」这类反常现象时，**第一反应应该是 layover，而不是地质解释**。判读雷达影像**必须先确认照射方向**。

### 6.11 Export Raster 的两个必填项容易漏

- **Clipping Geometry 若不设为 `Current Display Extent`** → 可能试图导出整个影像服务，极慢甚至失败。
- **Pixel Type 不设为 `16 bit unsigned`** → 位深不匹配 Landsat 原生数据，可能丢失辐射信息或产生溢出。

### 6.12 别把「材料没讲」当成「不重要」或「我记得学过」

本周材料**完全没有**监督/非监督分类、混淆矩阵、Kappa、NDWI。**不要把在别处看到的这些内容当成本课内容答题**，也不要因为它们「像是遥感课该有的」就自行补上。**本课的遥感是「光谱物理 + 波段组合 + 指数 + 目视判读」这条线，不是「分类 + 精度评价」那条线。**

---

## 七、本周术语表

### 7.1 遥感基础概念

| 英文 | 中文 | 要点 |
|---|---|---|
| **Remote sensing** | 遥感 | 不接触目标、从远处收集环境数据 |
| **Electromagnetic (EM) radiation, EMR** | 电磁辐射 | 能穿越真空并与物质相互作用的能量 |
| **Wave / Particle (photon) concept** | 波 / 粒（光子）概念 | 波描述传播、折射、反射；粒描述传感器的探测 |
| **Wavelength (λ)** | 波长 | 本周唯一需要牢牢掌握的属性 |
| **Frequency (v)** | 频率 | c = vλ |
| **Amplitude** | 振幅 | |
| **Black body** | 黑体 | 理想发射体；T↑ → 能量↑、峰值波长↓ |
| **Emittance** | 发射本领 | 黑体曲线的纵轴 |
| **Emissivity** | 发射率 | 实际物体发射本领 / 同温黑体发射本领 |
| **Transmission / Absorption / Emission** | 透射 / 吸收 / 发射 | Volume phenomena（体相现象） |
| **Scattering / Reflection** | 散射 / 反射 | Surface phenomena（表面现象），遥感最关心 |
| **Specular reflector** | 镜面反射体 | 入射角 = 反射角，现实中罕见 |
| **Diffuse reflection** | 漫反射 | 各向均匀反射；探测器放哪儿都收得到 |
| **Spectral reflectance** | 光谱反射率 | 入射辐射中被反射的比例 |
| **Spectral reflectance curve** | 光谱反射曲线 | 反射率随波长变化的曲线 |
| **Diagnostic (spectral) features** | 诊断性（光谱）特征 | 可用于识别成分的独有吸收/反射特征；红外区最丰富 |
| **Surface flux** | 地表通量 | 到达地表的能量；受日距与大气削减 |
| **Passive sensor** | 被动传感器 | 依赖太阳能量或目标热辐射 |
| **Active sensor** | 主动传感器 | 自带能量源（Radar、Lidar、Sonar） |
| **Atmospheric window** | 大气窗口 | 📎 材料描述了概念但未使用此术语 |

### 7.2 电磁波谱分区

| 英文 | 中文 | 波长 |
|---|---|---|
| **Gamma-ray** | 伽马射线 | < 0.03 nm |
| **X-ray** | X 射线 | 0.03 – 30 nm |
| **Ultraviolet (UV)** | 紫外 | 0.03 – 0.4 µm |
| **Visible** | 可见光 | 0.4 – 0.7 µm |
| **Near infrared (NIR)** | 近红外 | 0.7 – 1.3 µm，反射 |
| **Mid infrared (MIR)** | 中红外 | 1.3 – 3.0 µm，反射（= 遥感文献中的 SWIR） |
| **Far infrared (FIR) / Thermal infrared (TIR)** | 远红外 / 热红外 | 3.0 – 1000 µm，发射 |
| **Short-Wave Infrared (SWIR)** | 短波红外 | Landsat/Sentinel 文档用语，约 1.4 – 3.0 µm |
| **Microwave** | 微波 | 0.1 – 100 cm，穿云雾尘，主/被动皆可 |
| **Radar** | 雷达波段 | 1.0 – 100 cm，主动 |
| **Radio** | 无线电 | > 100 cm |

### 7.3 探测器与分辨率

| 英文 | 中文 | 要点 |
|---|---|---|
| **Pixel (picture element)** | 像元 | 影像的最小单元，带一个数值 |
| **Digital number (DN)** | 数字量 / 亮度值 | Practical 定义 band ratioing 时用的量 |
| **Bit (binary digit) depth** | 位深 | 决定离散取值个数 |
| **Spatial resolution** | 空间分辨率 | 像元对应的地面尺寸 |
| **Spectral resolution** | 光谱分辨率 | 波段数量与宽度 |
| **Radiometric resolution** | 辐射分辨率 | = 位深，2ⁿ 级 |
| **Temporal resolution** | 时间分辨率 | 重访周期 |
| **Full width half maximum (FWHM)** | 半高全宽 | 描述波段宽度；老师提及但不深入 |
| **Sampling interval** | 采样间隔 | 同上 |
| **Framing detector** | 框幅式探测器 | 瞬时整帧成像（如手机相机） |
| **Scanning detector** | 扫描式探测器 | 窄视场，扫过地表 |
| **Cross-track scanner** | 穿轨扫描 | 垂直于飞行方向扫描 |
| **Along-track scanner** | 沿轨扫描 | 沿飞行方向扫描 |
| **Push broom** | 推扫式 | 线阵探测器 + 飞行器运动成像 |
| **Field of view (FOV)** | 视场 | |
| **Swath** | 幅宽 | 通常宽于 ground track；累积形成全球覆盖 |
| **Ground track** | 星下点轨迹 | |
| **Polar / Equatorial / Inclined / Elliptical orbit** | 极轨 / 赤道 / 倾斜 / 椭圆轨道 | 极轨能耗高；椭圆轨道近地点分辨率高但寿命受限 |
| **Flyby** | 飞掠 | 行星探测的一次性经过 |
| **Nadir** | 天底 | 正下方观测方向；雷达通常非天底 |

### 7.4 卫星与传感器

| 英文 | 中文 | 要点 |
|---|---|---|
| **Landsat** | 陆地卫星系列 | USGS/NASA；1972 年至今连续覆盖；8–11 波段；15–60 m；数据完全免费 |
| **Landsat 8 / 9** | | 当前在役；OLI + TIRS |
| **OLI (Operational Land Imager)** | 陆地成像仪 | Landsat 8/9 光学传感器，9 个波段 |
| **TM (Thematic Mapper)** | 专题制图仪 | Landsat 4/5 传感器；⚠️ 波段编号与 OLI 不同 |
| **Landsat Next** | | 双星，5–6 天全球覆盖；尚未落实 |
| **Sentinel-2** | 哨兵 2 号 | ESA；重访 3–5 天；10–60 m |
| **MSI** | 多光谱成像仪 | 📎 Sentinel-2 的传感器名，材料未提 |
| **Panchromatic (PAN) band** | 全色波段 | 波长宽、分辨率高（Landsat 8 B8，15 m） |
| **Multispectral image** | 多光谱影像 | 多个波段堆叠 |
| **Multidimensional raster / image cube** | 多维栅格 / 影像立方体 | 在时间、深度或高度维度上堆叠的栅格 |
| **Band** | 波段 | |
| **Coastal Aerosol band** | 海岸/气溶胶波段 | Landsat 8 B1，用于大气 |
| **Cirrus band** | 卷云波段 | Landsat 8 B9，用于卷云检测 |
| **Acquisition date** | 采集日期 | 影像 pop-up 中的属性字段 |

### 7.5 处理、增强与指数

| 英文 | 中文 | 要点 |
|---|---|---|
| **Geometric correction** | 几何校正 | 消除几何畸变 + 配准到投影坐标系 |
| **Georeference** | 地理配准 | |
| **Radiometric correction** | 辐射校正 | 传感器响应、观测几何、大气效应、场景光照 |
| **Atmospheric correction** | 大气校正 | |
| **Top-of-atmosphere (TOA) reflectance** | 大气层顶反射率 | 校正前的量 |
| **Surface reflectance** | 地表反射率 | 校正后的量 |
| **Image enhancement** | 影像增强 | |
| **Band combination** | 波段组合 | 提升可目视解译的信息量 |
| **Pan-sharpening** | 全色锐化 | 用高分全色提升多光谱的空间分辨率；需良好共配准 |
| **Co-registration** | 共配准 | pan-sharpening 的前提 |
| **Contrast stretching** | 对比度拉伸 | Linear stretching / Histogram equalization |
| **Histogram equalization** | 直方图均衡化 | 可能过度增强 |
| **Spatial filtering** | 空间滤波 | 增强或抑制特定空间细节 |
| **True / Natural colour composite** | 真彩色 / 自然色合成 | R-G-B 对应显示 |
| **Pseudo natural colour** | 拟自然色 | 略偏离人眼波长 |
| **False colour composite** | 假彩色合成 | 通道使用完全不同的波长 |
| **Band ratioing** | 波段比值 | 高反射波段 ÷ 低反射波段 |
| **Band maths** | 波段运算 | 经验积累出来的加减乘除组合 |
| **Vegetation Index（= NDVI）** | 植被指数 | (B8−B4)/(B8+B4)【S2】 |
| **Moisture Index（= NDMI）** | 水分指数 | (B8A−B11)/(B8A+B11)【S2】 |
| **Normalised Burn Ratio (NBR)** | 归一化燃烧比 | (NIR−SWIR)/(NIR+SWIR) |
| **Iron Oxide ratio** | 铁氧化物比值 | Landsat 8 的 4/2（Red/Blue） |
| **Clay / Hydroxyl minerals ratio** | 黏土 / 羟基矿物比值 | Landsat 8 的 6/7 |
| **Ferrous minerals ratio** | 亚铁矿物比值 | Landsat 8 的 6/5 |
| **Hydrothermal alteration** | 热液蚀变 | 找矿的光谱线索 |

### 7.6 主动遥感

| 英文 | 中文 | 要点 |
|---|---|---|
| **Radar (Radio wave detection and ranging)** | 雷达 | 主动微波方法 |
| **SAR (Synthetic Aperture Radar)** | 合成孔径雷达 | |
| **InSAR (Interferometric SAR)** | 干涉合成孔径雷达 | 测地表位移（冰川、冰盖、地震），可导出 DEM |
| **Interferogram** | 干涉图 | 如 ERS-2 记录的 1999 Izmit 地震 |
| **Ground penetrating radar (GPR)** | 探地雷达 | 可穿透数米至数公里；火星 SHARAD |
| **Look direction** | 视向 | 雷达照射方向；判读的前提 |
| **Depression angle** | 俯角 | |
| **Foreshortening** | 前坡缩短 | 地物看似朝探测器倾斜 |
| **Layover** | 叠掩 | 陡坡山顶回波先到，山「盖住」前方 |
| **Radar shadow** | 雷达阴影 | 陡坡背后无信号 |
| **Radar brightness** | 雷达亮度 | 同一区域不同视向差异极大 |
| **Surface roughness** | 表面粗糙度 | 雷达影像本质上反映粗糙度 |
| **Dielectric properties** | 介电性质 | 影响回波强度的地物属性之一 |
| **Polarization** | 偏振 | 雷达系统属性之一 |
| **Lidar** | 激光雷达 | 用激光代替雷达；可穿透植被冠层；垂直精度近厘米级 |
| **Point cloud** | 点云 | Lidar 输出的三维数据 |
| **DTM (Digital Terrain Model)** | 数字地形模型 | ⚠️ 本课定义 = 含地面以上地物 |
| **DEM (Digital Elevation Model)** | 数字高程模型 | ⚠️ 本课定义 = 裸地表 |
| **DSM (Digital Surface Model)** | 数字表面模型 | 📎 材料未使用；主流用法中 = 含地物的表面 |

### 7.7 ArcGIS Online / ArcGIS Pro 工具与界面

| 英文 | 中文 / 位置 | 要点 |
|---|---|---|
| **ArcGIS Living Atlas of the World** | 在线权威数据集库 | Landsat/Sentinel 影像服务的来源 |
| **Multispectral Landsat** | 多光谱 Landsat 图层名 | Living Atlas 中搜 `Multispectral` |
| **Sentinel-2 views** | Sentinel-2 图层名 | Living Atlas 中搜索 |
| **Basemap → Light Grey Canvas** | 底图 → 浅灰画布 | 让标注可见、不与影像抢色 |
| **Contents pane** | 内容窗格 | 图层列表 |
| **Catalog pane → Portal → Living Atlas** | 目录窗格 → 门户 → Living Atlas | ArcGIS Pro 中接入在线数据 |
| **Add to Current Map** | 添加到当前地图 | 拖拽失败时的右键备选 |
| **Filter → Add new / Clear all** | 过滤器 → 新增 / 全部清除 | 属性过滤；本 Practical 需先 Clear all |
| **"Any of the following are true"** | 「满足任一条件」 | 五个日期过滤必须用 OR 逻辑 |
| **is between** | 介于 | 过滤运算符，输入起止时间戳 |
| **Acquisition Date** | 采集日期字段 | 过滤所用字段 |
| **Enable time** | 启用时间 | 图层级开关，开启后出现时间动画工具条 |
| **Time animation toolbar** | 时间动画工具条 | |
| **Play/Pause** | 播放/暂停 | |
| **Configure** | 配置 | 时间动画的设置入口 |
| **Play rate** | 播放速率 | 本练习设为最慢 |
| **Start and end points** | 起止时间点 | 设 Start time / End time |
| **Time intervals → Length of one interval** | 时间间隔 → 单个间隔长度 | 本练习用 1 year 与 10 years |
| **Map Tools → Measurement** | 地图工具 → 量测 | 单击起点、双击终点 |
| **Measure Distance** | 距离量测 | |
| **Save and open → Save as** | 保存并打开 → 另存为 | 填 title / tags / summary |
| **ribbon → Data → Processing Templates** | 功能区 → 数据 → 处理模板 | 影像服务的服务端渲染模板 |
| **Natural Colour with DRA** | 自然色 + 动态范围调整 | DRA = Dynamic Range Adjustment |
| **Data → Export Raster** | 数据 → 导出栅格 | 右键图层进入 |
| **Clipping Geometry → Current Display Extent** | 裁剪范围 → 当前显示范围 | 只导出视图范围 |
| **Pixel Type → 16 bit unsigned** | 像素类型 → 16 位无符号 | Landsat 影像默认位深 |
| **ribbon → Imagery → Indices** | 功能区 → 影像 → 指数 | 内置指数库 |
| **Indices → Geology → Iron Oxide** | 指数 → 地质 → 铁氧化物 | 亮区 = 高铁氧化物 |
| **Indices → Clay Minerals** | 指数 → 黏土矿物 | |
| `Chuquicamata_Landsat` | 本练习导出栅格的命名 | |

### 7.8 案例与专有名词

| 名称 | 说明 |
|---|---|
| **Chuquicamata mine, Chile** | 智利北部；按开采体积计世界最大露天铜矿；1882 年开矿；2019 年转入地下开采 |
| **Peter Grindrod** | 本周客座讲师；Natural History Museum, London（转写 ASR 误写为 "Grindrad"） |
| **Ranger 9** | 1965-03-24 撞月任务，TV 相机逐帧成像 |
| **Lunar Reconnaissance Orbiter (LRO), Narrow Angle Camera** | 月球勘测轨道器窄角相机，40 cm/pixel |
| **Magellan** | 1990s 金星任务，仅载主动雷达 |
| **Galileo** | 1990s–2000s 木星任务，全被动多波段仪器 |
| **New Horizons** | 飞掠任务的例子 |
| **MRO / SHARAD** | 火星勘测轨道器上的探地雷达 |
| **NPLD (North Polar Layered Deposits)** | 火星北极层状沉积，富冰、年层可辨 |
| **Olympus Mons** | 火星巨型火山，山顶几乎不受大气影响，用作大气校正参考 |
| **Dust devil** | 尘卷风，火星上留下黑色条纹 |
| **ERS-2 SAR interferogram, Izmit 1999** | 土耳其 Izmit 地震的雷达干涉图 |
| **Seasat: Alaska Range** | 讲义中 layover 的地球实例 |
| **Eagle Bluff wildfire, 31 July 2023 / Los Angeles 2017** | NBR 的火烧案例 |

---

## 附：材料勘误表

| 位置（文件名 + 大致段落） | 材料原文 | 问题 | 更正 / 说明 |
|---|---|---|---|
| `Geospatial Techniques - Lecture 6 - Remote Sensing - 2026.md`，Electromagnetic Spectrum 表格（Ultraviolet / Visible / Infrared / Near / Mid / Far infrared 六行） | "Ultraviolet 0.03 to 0.4 **mm**"、"Visible 0.4 to 0.7 **mm**"、"Infrared 0.7 to 100 **mm**"、"Near infrared 0.7 to 1.3 **mm**"、"Mid infrared 1.3 to 3.0 **mm**"、"Far infrared 3.0 to 1000 **mm**" | **单位系统性错误（低质量 OCR）**：µm（微米）被识别为 mm（毫米），相差 1000 倍。判据：同表 X-ray 上限为 30 nm = 0.03 **µm**，正好与 Ultraviolet 下限 0.03 衔接；若为 mm 则整表不自洽，且可见光将变成 0.4–0.7 毫米（实为微波量级）。 | 六行单位均应为 **µm**。即：UV 0.03–0.4 µm、Visible 0.4–0.7 µm、IR 0.7–100 µm、NIR 0.7–1.3 µm、MIR 1.3–3.0 µm、FIR 3.0–1000 µm。 |
| 同上，"Satellites: Landsat and Sentinel" 页 | "USGS/NASA **Landsat** satellites have a repeat period every **32 days**." | **重访周期数值错误**。Landsat 自 Landsat 4 起采用 WRS-2 轨道，**单星重访周期为 16 天**；Landsat 8 与 Landsat 9 相位相差 8 天，**双星组合的有效重访为 8 天**。任何一档都不是 32 天。 | 应为 **16 days（单星）/ 8 days（Landsat 8+9 组合）**。同一页 Sentinel-2 的 "3–5 days" 是正确的（双星组合赤道 5 天、中纬 2–3 天）。**这个数字直接影响「Landsat vs Sentinel 谁的时间分辨率更好」这类判断，必须纠正。** |
| 同上，"Digital multispectral images" 页 | "**Sentinel** sensors have **13-25** bands, covering the visible, near-infrared, shortwave infrared, and **microwave** regions." | **混淆了 Sentinel 星座的不同成员**。本周实际使用的 **Sentinel-2** 搭载 MSI，是**纯光学传感器，共 13 个波段，不含任何微波波段**。微波（SAR）属于 **Sentinel-1**，而 SAR 不是「多光谱波段」意义上的 band。"13–25 bands" 若指整个 Sentinel 家族（如 Sentinel-3 OLCI 21 个波段），则不应与 Sentinel-2 的分辨率数据并列陈述。 | 应表述为：**Sentinel-2 MSI 有 13 个波段**，覆盖 visible / NIR / SWIR；**微波观测由 Sentinel-1 的 SAR 提供，属主动遥感，与多光谱波段不是同一概念**。 |
| 同上，"Digital multispectral images" 页 | "**Landsat** sensors have **8-11** bands" | **未覆盖早期传感器**。Landsat 1–5 的 **MSS 只有 4 个波段**；TM 为 7 个；ETM+ 为 8 个；OLI+TIRS 为 11 个。 | 应为 **4–11 bands**，或明确限定为「Landsat 7 及以后」。 |
| 同上，"Transformation using band combinations" 页；及 `EART29102 - 09-Mar-transcript.md` 对应段落 | 讲义列出 Natural Colour (B4,B3,B2)、Color Infrared (B8,B4,B3)、SWIR (B12,B8A,B4)、Agriculture (B11,B8,B2)、Geology (B12,B11,B2)、Bathymetric (B4,B3,B1)、Vegetation Index (B8−B4)/(B8+B4)、Moisture Index (B8A−B11)/(B8A+B11)；转写中老师说 "**For Landsat**, you'll see some standard combinations of the bands" | **卫星归属说错**。上述全部组合使用的是 **Sentinel-2 的波段编号**（B8、B8A、B11、B12 在 Landsat 8 上并不存在或含义完全不同——Landsat 8 的 B8 是 15 m 全色波段，且 OLI 没有 B12）。**这是本周最危险的一处错误**，因为学生很容易把这张表当成 Landsat 用。 | 应说明为 **Sentinel-2 band combinations**。对应的 **Landsat 8** 版本为：Natural Colour = 4-3-2；Color Infrared = 5-4-3；SWIR = 7-5-4（或 7-6-4）；**NDVI = (B5−B4)/(B5+B4)**。 |
| 同上，"Atmospheric Interactions" 页 | "Intensity received inversely proportional to square of distance from sun. • **Solar energy at Venus = twice that at Mars**" | **数值错误**。金星 0.72 AU、火星 1.52 AU，按平方反比：(1.52/0.72)² ≈ **4.4 倍**，不是 2 倍。若原意是「金星是**地球**的约 2 倍」（1/0.72² ≈ 1.9），则是**比较对象写错**。 | 应为 **「金星约为火星的 4.4 倍」** 或 **「金星约为地球的 2 倍」**。该页要传达的定性结论（越靠近太阳、可用能量越多，因此传感器设计不同）不受影响。 |
| 同上，LiDAR 页配图文字；及转写对应段落 | 讲义："**DTMs include features above the ground surface. DEMs of the bare ground surface.**" 转写："a **DTM** or digital terrain model which is **everything**, or a **digital elevation model** where you can **remove** the effect of buildings, trees, forests" | **术语定义与遥感/测绘领域的通行约定相反**。主流约定为：**DTM（Digital Terrain Model）= 裸地表**；**DSM（Digital Surface Model）= 含建筑与植被的表面**；**DEM** 多为泛称或与 DTM 同义。材料把 DTM 与 DEM 的含义对调，且完全没有提到 DSM。 | 通行定义应为：**DSM = 含地面以上地物；DTM / DEM = 裸地表**。**注意：讲义与转写在此处内部是一致的**（不是转写错误），因此这是课件本身的约定问题。本课考试按材料定义答，但读外部文献与做 W07 地形分析时必须以数据说明为准。 |
| 同上，Electromagnetic Spectrum 表格 | 表中把 **Microwave（0.1–100 cm）** 与 **Radar（1.0–100 cm）** 并列为两个独立的「Region」 | **概念层级不对等**。Radar 不是电磁波谱的一个独立区段，而是**使用微波波段的一种主动探测技术**；其波长范围本身就落在 Microwave 之内。 | 应理解为：**Microwave 是波谱区段；Radar 是工作在该区段的技术**。表格的并列排版仅为便于说明用途，不表示两者是并列的波谱分区。 |
| 同上，"Microwave" 行 | "Penetrates cloud, haze, dust. **No atmospheric scattering.**" | **表述过于绝对**。微波受大气分子散射极小，但**降水（尤其是较短波长的微波，如 Ku/Ka 波段）仍会造成显著衰减与散射**，这正是星载降水雷达能工作的原理。 | 应为 **"negligible atmospheric scattering（散射可忽略）"** 而非 "no scattering"。 |
| `Practical 6 -Remote Sensing.md`，§5.2 第二段 | "A single **Landsat TM** image is made of several files... The bands correspond to the following portions of the electromagnetic spectrum, as described in **Landsat 8 Operational Land Imager**." 随后列出 Band 1–9 | **传感器名称自相矛盾**。**TM（Thematic Mapper）是 Landsat 4/5 的传感器，共 7 个波段，编号体系与 OLI 完全不同**（TM 的 B1=蓝、B2=绿、B3=红、B4=NIR、B5=SWIR1、B6=TIR、B7=SWIR2）。而随后列出的 9 个波段确实是 **Landsat 8 OLI** 的。 | 首句应为 **"A single Landsat 8 OLI image..."**。这一处若被误读，会导致波段编号张冠李戴（例如把 TM 的 B3/B1 当成 OLI 的 B3/B1 去做铁氧化物比值）。 |
| `Practical 6 -Remote Sensing.md`，§5.2 铁氧化物段与 §6 | "iron oxides or hydroxides have high reflectance at **0.63-0.69 µm (Red band)** and high absorption at **0.45-0.52 µm (Blue band)**" | **引用的波长区间与同页给出的 Landsat 8 OLI 波段范围不一致**。OLI 的 **Band 4 (Red) 为 0.64–0.67 µm**、**Band 2 (Blue) 为 0.450–0.51 µm**；文中所引的 0.63–0.69 与 0.45–0.52 实为 **Landsat TM 的 Band 3 与 Band 1** 的范围。 | 两组数值在物理上指向同一段光谱，**不影响 4/2 这个比值的正确性**，但反映了该段是从 TM 时代的资料改写而来、未同步更新。做 §6 的 Sentinel-2 选波段时，请以「红光 / 蓝光」的物理含义为准（S2 → **B4 / B2**），而非机械匹配数字区间。 |
| `Practical 6 -Remote Sensing.md`，§5.2 | "There are **nine spectral bands**, (wavelengths) with spatial resolutions as follows" | **表述不完整**。9 个波段仅为 **OLI** 传感器；**Landsat 8 整星还搭载 TIRS，提供 Band 10 与 Band 11 两个热红外波段**，全星共 11 个波段。这也与讲义中「Landsat 覆盖 thermal infrared 区」的说法呼应，但 Practical 的表中没有任何热红外波段。 | 应说明为 **"OLI 提供 9 个波段；TIRS 另提供 2 个热红外波段（Band 10/11），全星共 11 个"**。 |
| `Practical 6 -Remote Sensing.md`，§4.2 选片表 与 §4.3 过滤器步骤 | 选片表用 "**2/15/1975**"、"10/22/2005"（美式 月/日/年）；§4.3 却写 "Repeat this for each image date: **15/2/1975**, 4/4/1990, **22/10/2005**, 29/11/2013 and 28/01/2024"（英式 日/月/年） | **同一份教程内混用两种日期格式**，且未作任何说明。`4/4/1990` 自反看不出问题，但 `2/15/1975` 与 `15/2/1975`、`10/22/2005` 与 `22/10/2005` 直接冲突。 | 两处指的是**同一批日期**：1975-02-15、1990-04-04、2005-10-22、2013-11-29、2024-01-28。输入前请确认 ArcGIS Online 当前的区域日期设置。 |
| `Practical 6 -Remote Sensing.md`，§4.1 与 §4.2 | §4.1："the first date range on the timeline: **July 24, 1972, to July 24, 1977**"；§4.2："Change **Start time** to **7/25/1972** 12:00 AM" | **相差一天**，前后不一致。 | 差异对练习结果无影响（1972–1973 年间本区域无可用影像）。按 §4.2 的 7/25/1972 操作即可。 |
| `Practical 6 -Remote Sensing.md`，§1 Introduction 末句 | "learn how to analyse reflectance spectra **to**"（句子在此中断） | **句子不完整**，原 PDF 排版或转换时截断。 | 从上下文补全应为「…to identify hydrothermal alteration minerals（识别热液蚀变矿物）」之意，见 §5.2。 |
| `Practical 6 -Remote Sensing.md`（全篇） | "**Landasat**"、"**imagary**"、"**ArGIS** Pro"、"**Sentinal**-2"、"**Chiquicamata**"（§3.3，正确应为 Chuquicamata）、"**htps**://"；目录与正文中的 "Introducton"、"Multdimensional"、"multspectral"、"tme"、"animaton"、"Confgure"、"informaton"、"Operatonal"、"Sentnel" | **两类错误**：(1) 拼写错误（Landsat / imagery / ArcGIS / Sentinel / Chuquicamata / https）；(2) **PDF 转换时 `ti`、`fi` 连字（ligature）被吞掉**，造成成批缺字母 i。 | 均为文本层问题，不影响操作内容。**注意 §3.3 的 "Chiquicamata" 与全文其余处的 "Chuquicamata" 是同一个矿。** |
| `Geospatial Techniques - Lecture 6 - Remote Sensing - 2026.md`，文件末尾 "OCR 补充 → Page 38" | "Landsat orbits / Landsat Next A ' / Elapsed: **Odays** 1.50 hours" | **低质量 OCR 段**（文件已自行标注「原文件该处无可提取文字」）。"Odays" 中的 O 是字母误识数字 **0**；"A '" 为残缺片段。 | 应为 **"0 days 1.50 hours"**。该页实为 Landsat 9 与 Landsat Next 全球覆盖速度对比动画的截图（对应转写中「Landsat Next 两星 5–6 天全球覆盖」一段），**无其他可用文字信息**。 |
| `Geospatial Techniques - Lecture 6 - Remote Sensing - 2026.md`，多处 | "Velocity of EM energy, 𝑐= 𝑣𝜆 ... **" = wavelength**"；"increasing the spatial resolution of a multispectral image with a **higherresolution** panchromatic image"；"Passive **orActive**" | **OCR 造成的字符丢失与缺空格**：λ 的希腊字母未被识别、连字符与空格丢失。 | 应分别为 **"λ = wavelength"**、**"higher-resolution"**、**"Passive or Active"**。 |
| `EART29102 - 09-Mar-transcript.md`（全篇，自动语音转写） | "I'm Peter **Grindrad**"、"**radimetric** resolution"、"we have a **long track** scanners"、"these are three **land sat** images"、"a new **meter about**, a new crater about 10 meters across" | **ASR（自动语音识别）造成的误写**，非授课内容错误。 | 正确写法依次为：**Peter Grindrod**、**radiometric**、**along-track**、**Landsat**、（末条为老师口头改口，以 "a new crater about 10 meters across" 为准）。 |
| `Geospatial Techniques - Lecture 6 - Remote Sensing - 2026.md`，首页 "Lecture content" | 只列出 "**Spectral, spatial and radiometric** resolution"（三种） | **与正文不一致**。正文 "Detector Systems → Resolution" 明确写 "**Four main types** relevant here"，并逐页讲了 SPATIAL / SPECTRAL / RADIOMETRIC / **TEMPORAL** 四种。 | 以正文的**四种**为准；**temporal resolution 是本周重点之一**（Landsat 时间序列、火星 10 年对比、Landsat Next 重访能力都建立在这个概念上），不可因首页遗漏而略过。 |
| `Geospatial Techniques - Lecture 6 - Remote Sensing - 2026.md`，Mid infrared 行；与 `Practical 6` 的 SWIR 命名 | 讲义："**Mid infrared** 1.3 to 3.0"；Practical："**Band 6 SWIR 1**(1.57 - 1.65 µm)、**Band 7 SWIR 2** (2.11 - 2.29 µm)" | **同一段波长在两份材料中使用了不同名称**，且从未说明二者等价。讲义沿用遥感地质学传统（Sabins）的 MIR 划分，Practical 与 Landsat 官方文档使用 SWIR。**此外，物理学与热红外文献中的 "MIR" 通常指 3–8 µm**，与讲义的用法又不同。 | 此条**非硬性错误，而是命名体系冲突**，但极易造成混淆。记忆时以**波长数值**为准：**1.3–3.0 µm = 讲义的 Mid infrared = Landsat/Sentinel 文档的 SWIR**，均属反射红外。 |
