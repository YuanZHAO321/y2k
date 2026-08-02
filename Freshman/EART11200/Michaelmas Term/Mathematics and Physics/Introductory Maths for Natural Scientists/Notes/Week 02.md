# Week 2 — 分数与因式分解、热能等价与净初级生产力 (NPP)："人类吃掉了地球多少绿色能量"

## 一、本周主题

本周课程由两条线索交织而成：一是延续第 1 周的数学基础训练，复习**分数 (fractions)**、**展开括号 (expanding brackets)** 与**因式分解 (factorising)** 这三项代数基本功；二是引入本课程贯穿全学期的地球科学应用案例——**净初级生产力 (Net Primary Productivity, NPP)**，即地球上植物/藻类每年通过光合作用固定下来的碳/能量总量。两条线索在 Practical 的核心问题「The greens we eat（人类吃掉了多少绿色能量）」中汇合：学生需要综合运用分数运算、摩尔质量（化学计量学 stoichiometry）、单位换算以及公式代入，估算人类每年的食物消耗占地球 NPP 的比例。本周还顺带引入了热量与能量的等价关系（Joule 实验）、比热容公式 $E=mC\Delta T$，以及归纳出「植被指数 NDVI」这一遥感估算 NPP 的手段。在全课 5 周的编排中，Week 2 处于承上启下的位置：延续 Week 1 的运算与单位基础，为 Week 3 及以后的对数 (logarithms) 和公式变形 (transposing formulae) 做铺垫——事实上本周 Practical 的附加题已经提前用到了指数增长与对数求解的思想。

## 二、核心概念

### 1. 分数 (Fractions)
分数表示整体中的一部分，写作 $\dfrac{\text{numerator}}{\text{denominator}}$（分子/分母）。分母表示整体被划分成的等份数，分子表示取用的份数。例如八分之一 (⅛) 的蛋糕，就是把整个蛋糕切成 8 等份取其中 1 份。

- **真分数 (proper fraction)**：分子 < 分母，例如 $2/7$。
- **假分数 (improper fraction)**：分子 > 分母，例如 $7/3$。假分数可以转换为**带分数 (mixed fraction)**（整数部分 + 真分数），如 $7/3 = 2\dfrac{1}{3}$。
- **百分数 (percentage)**：1% 即百分之一 $(1/100)$；10% 即 $10/100 = 1/10$。

分数是本周 Practical 计算的基础工具——无论是计算碳在葡萄糖分子中所占的质量比例，还是计算不同食物种类在饮食结构中的占比，本质都是分数运算。

### 2. 展开括号 (Expanding brackets)
利用分配律把括号外的因子乘进括号内每一项。讲义给出的例子：

$$4(x+xy-3) = 4x + 4xy - 12$$
$$x\left(x^2 + xy + \frac{2}{x}\right) = x^3 + x^2y + 2$$
$$(x-y)(x+z) = x^2 - yx + zx - yz = x^2 + x(z-y) - yz$$

第三个例子说明了两个二项式相乘要「四项全乘」（俗称 FOIL：首×首、首×尾、尾×首、尾×尾），然后再把含 $x$ 的同类项 $-yx+zx$ 合并写成 $x(z-y)$，这是把展开结果重新「收拢」成更紧凑形式的技巧，也是因式分解思想的雏形。

### 3. 因式分解 (Factorising)
因式分解是展开括号的**逆过程**：把一个多项式改写成若干因子相乘的形式，第一步永远是找**公因子 (common factor)**。

- 提公因子：$42y+7 = 7(6y+1)$（公因子 7）；$6p^2-3p = 3p(2p-1)$（公因子 $3p$）。
- 二次三项式因式分解：$r^2+3r+2=(r+2)(r+1)$，即寻找两个数，其和为一次项系数（3），其积为常数项（2）——这两个数是 2 和 1。
- 先提公因子再因式分解二次式：$4v^2+12v-40 = 4(v^2+3v-10) = 4(v+5)(v-2)$。这里先提出公因子 4，再对括号内的二次三项式 $v^2+3v-10$ 用「和为 3、积为 -10」的两个数（5 和 -2）分解。
- 一般二次三项式的**交叉相乘法 (cross-multiplication)**：对于 $ar^2+br+c$，尝试写成 $(dr+e)(fr+g)$，需要满足
$$d\times f = a,\qquad e\times g = c,\qquad d\times g + e\times f = b$$
即两个括号首项之积等于二次项系数 $a$，尾项之积等于常数项 $c$，交叉相乘之和等于一次项系数 $b$。这是因式分解一般二次三项式（$a\neq1$）的标准方法。

讲义特别提醒：分数与括号/因式分解是本周 Practical 会大量用到的工具，如果觉得困难应在 Practical 现场向助教求助。

### 4. 热量与能量的等价 (Heat and Energy equivalence)
这一节从物理学史切入，介绍 **James Prescott Joule (1818–1888)**，英国索尔福德出生的物理学家兼酿酒师。他在 1845 年发表论文，通过一套装置证明了下落重物的**势能 (potential energy)** $mgh$ 可以转化为水中粘滞摩擦产生的**热量** $mc\,\Delta T$，从而定量证明了机械能与热能等价，这一发现直接导致了**能量守恒定律 (law of conservation of energy)** 的确立。Joule 本人的信念也很有意思：他认为「毁灭力量的能力只属于造物主」，因此任何要求「力量湮灭」的理论必然是错误的——这正是能量守恒思想的哲学雏形。SI 单位制中的能量单位「焦耳 (Joule, J)」正是为纪念他而命名。

由此引出食物能量的两个易混淆单位：
- **calorie (小卡, cal)**：使 1 克水温度升高 1°C 所需的热量。
- **Calorie (大卡/千卡, kcal)**：使 1 千克水温度升高 1°C 所需的热量，即 $1\text{ Calorie} = 1000\text{ calories}$。
- 换算关系：$1\ \text{calorie} = 4.18\ \text{J}$（Practical 答案中近似取用 $4.2\ \text{J}$）。

食物中的「热量」本质上就是化学能，可以用来驱动人体活动、维持体温，或转化为其他形式的能量（如电能）。

### 5. 比热容与升温公式
每种物质都有自己特定的**比热容 (specific heat capacity)** $C$，表示单位质量该物质升高单位温度所需吸收的热量。公式为：

$$E = mC\Delta T$$

其中 $E$ 是所需能量（J），$m$ 是质量（kg），$C$ 是比热容（水的比热容 $C=4180\ \text{J kg}^{-1}\text{K}^{-1}$），$\Delta T$ 是温度变化量（K 或 °C，数值相同）。

**例题（Joule 实验的现代版）**：质量 1 kg 的重物悬于 1.0 m 高处，下落后驱动水中的桨叶搅动 0.5 kg 的水，问水温升高多少？
- 重物下落释放的势能：$E_p = mgh$（讲义未给出数值代入，留给学生完成，思路是令势能等于水吸收的热量 $E=mC\Delta T$，反解出 $\Delta T = \dfrac{mgh}{m_{water}C}$）。

**扩展的洗澡水加热例题**（讲义给出完整数值链）：把水从室温加热到 40–45°C（即 $\Delta T\approx 25$°C），所需水量约 140 升（约 30 英制加仑）。计算过程：
$$E = mC\Delta T = (\text{density}\times\text{volume})\times C\times\Delta T = 1000\ \text{kg/m}^3\times 0.14\ \text{m}^3\times 4180\times 25 \approx 14.6\ \text{MJ}\approx 4\ \text{kWh}$$
讲义同时给出了单位换算锚点：$1\ \text{kWh} = 1000\times60\times60\ \text{J} = 3.6\ \text{MJ}$；$1\ \text{m}^3$ 水 $=1000$ 升 $\approx 220$ 英制加仑。并附上英国当时的成本参考：用水成本约 28 便士，电加热约 50 便士，燃气加热约 16 便士——用来说明「同样的能量，不同能源载体的经济成本不同」。

### 6. 初级生产 (Primary production)：光合作用与化能合成
**初级生产 (primary production)** 指生物体利用能量将简单无机物合成为有机化合物（化学能）的过程。绝大部分初级生产的能量来自太阳光（**光合作用, photosynthesis**），极小一部分由利用无机分子化学能的**化能自养生物 (lithotrophic organisms)** 完成（**化能合成, chemosynthesis**）。两者的简化反应式：

$$\text{光合作用：}\quad \text{CO}_2 + \text{H}_2\text{O} + \text{light} \rightarrow \text{CH}_2\text{O} + \text{O}_2$$
$$\text{化能合成（一种形式）：}\quad \text{CO}_2 + \text{H}_2\text{S} \rightarrow \text{CH}_2\text{O} + \text{O}_2 + \dots(\text{含硫产物})$$

两条途径的终点都是**还原碳水化合物 (reduced carbohydrate)** $\text{CH}_2\text{O}$，典型代表是**葡萄糖 (glucose, } \text{C}_6\text{H}_{12}\text{O}_6\text{)}$。这些简单分子可进一步合成蛋白质、复杂碳水化合物、脂质、核酸，或通过呼吸作用释放能量供机体做功。

完成初级生产的生物称为**初级生产者 (primary producers)** 或**自养生物 (autotrophs)**，是食物链的基础——陆地生态系统中主要是植物，水生生态系统中主要是藻类。几乎地球上所有生命都直接或间接依赖初级生产。

### 7. Net 与 Gross Primary Productivity 的区别（**GPP ≠ NPP**）
初级生产可分为**总初级生产力 (Gross Primary Productivity, GPP)** 和**净初级生产力 (Net Primary Productivity, NPP)**：
- **GPP**：植物光合作用固定的**全部**碳/能量，不扣除任何损耗。
- **NPP**：GPP 减去植物自身**细胞呼吸 (cellular respiration)** 消耗掉的部分，即净剩下、真正转化为生物量 (biomass) 的碳量。

讲义特别强调这是一个 **Important point**：NPP 不等于植物每年新增生长的「质量」，因为还有食草动物取食、枯枝落叶分解等其他损耗路径——NPP 只衡量「进入植物生长/生物量的碳量」，单位通常是 $\text{gC yr}^{-1}$（每年多少克碳）。

### 8. 遥感估算 NPP 的方法：NDVI
由于全球尺度上无法逐块测量植物光合作用，科学家利用卫星遥感的反射光谱来估算：植物表面会吸收可见光中的红光用于光合作用，但**不吸收**近红外光 (near-infrared, NIR)，因此可以定义**归一化植被指数 (Normalized Difference Vegetation Index, NDVI)**：

$$\text{NDVI} = \frac{\text{NIR} - \text{red}}{\text{NIR} + \text{red}}$$

植被覆盖度越高、光合作用越活跃，反射的近红外光越强、吸收的红光越多，因而 NDVI 数值越大（为正）；这一指数与光合作用速率相关，从而可用于估算 NPP。讲义也指出，**海面以下**的初级生产（浮游植物光合作用）比陆地更难通过遥感直接估计，因为可见光/近红外无法穿透水体太深。

## 三、公式与图表

**汇总本周所有关键公式：**

1. 因式分解一般二次式：
$$ar^2+br+c=(dr+e)(fr+g),\quad \text{需满足 } df=a,\ eg=c,\ dg+ef=b$$

2. 卡路里换算：
$$1\ \text{calorie} = 4.18\ \text{J}\ (\approx4.2\ \text{J 用于估算})$$
$$1\ \text{Calorie(kcal)} = 1000\ \text{calorie}$$

3. 升温所需能量（比热容公式）：
$$E = mC\Delta T$$
符号含义：$E$——能量 (J)；$m$——质量 (kg)；$C$——比热容 ($\text{J kg}^{-1}\text{K}^{-1}$，水取 4180)；$\Delta T$——温差 (K/°C)。

4. 单位换算锚点：
$$1\ \text{kWh} = 3.6\ \text{MJ},\qquad 1\ \text{m}^3\text{水} = 1000\ \text{L} \approx 220\ \text{加仑}$$

5. 光合作用 / 化能合成方程式（见「二、核心概念」第 6 点）。

6. NDVI 公式：
$$\text{NDVI} = \frac{\text{NIR}-\text{red}}{\text{NIR}+\text{red}}$$

7. **葡萄糖中碳的质量分数**（Practical 核心公式，用于把「碳的质量」换算为「生物量（葡萄糖）总质量」）：
$$f_{\text{碳}} = \frac{\text{一摩尔中碳的总质量}}{\text{一摩尔中碳+氧+氢的总质量}} = \frac{6\times12}{6\times12+6\times16+12\times1}=\frac{72}{180}=0.4$$
即葡萄糖 ($\text{C}_6\text{H}_{12}\text{O}_6$) 中每 1 g 生物量含 0.4 g 碳。这是由**分子式中各元素原子数 × 相对原子质量**求**摩尔质量 (molar mass)**、再取比值得到的**化学计量学 (stoichiometry)** 计算，与图示「Figure 1.2」所讲的方法一致：葡萄糖的分子量 = 6 个碳原子质量 (6×12) + 6 个氧原子质量 (6×16) + 12 个氢原子质量 (12×1)。

8. **指数增长的「指示方程」(indicial equation)**（Practical 附加题 4，提前预告 Week 3+ 的对数内容）：
$$(6.7\times10^9)\times1.02^x = 1.53\times10^{11}$$
两边取自然对数求解 $x$（见「五、Practical 要点」中的完整推导）。

## 四、课堂补充

本周 Lecture 与 Practical 各自配套的 `*-transcript.md` 转写文件经检查**均为空白占位文件**——文件内只有 YAML 头信息（标题、来源、类型），正文部分没有任何实际课堂录音转写内容（原始 `.txt` 转写文件也仅有极短的占位文本"'EART11200 - 04-Oct', automated transcript"字样，无实质内容）。因此本周**没有可供摘录的课堂口头讲解内容**，「课堂补充」一节暂缺，全部知识点均来自 Lecture 三份幻灯片 PDF 转写稿（`EART11200_M&P_W2_1/2/3.md`）与 Practical 答案文件（`eart11200_week02_answers.md`）本身。（本周无课堂转写内容可补充）

## 五、Practical 要点

### 目的
本周 Practical 的核心问题 **1.3「The greens we eat」（人类吃掉的绿色能量）**，目的是训练学生综合运用**分数、化学计量学（摩尔质量计算）、单位换算**，估算人类每年食物消耗的能量占地球净初级生产力 (NPP) 的比例，从而直观感受人类活动对地球碳/能量循环的占用程度。讲义提示：先完成补充材料 (supplementary material)，再做主问题，最后做相关延伸问题；一周内还需完成 Blackboard 上的练习测验（不计分但需体现参与度）。

### 已知条件
- 地球 NPP：$14.7\ \text{PgC/yr} = 14.7\times10^{15}\ \text{gC yr}^{-1}$
- 干生物量的能量含量：$1.6\times10^4\ \text{J g}^{-1}$
- 2008 年世界人口：$6.7\times10^9$
- 人均每日食物摄入约 2500 kcal

### 解题步骤（主问题）
**第一步：计算全球人类年食物能耗。**
$$2500\ \text{kcal} = 2500\times10^3\ \text{cal}\times4.2\ \text{J/cal} = 1.05\times10^7\ \text{J/day/person}$$
$$1.05\times10^7\ \text{J day}^{-1}\text{person}^{-1}\times6.7\times10^9\ \text{people}\times365\ \text{days/yr}\approx2.6\times10^{19}\ \text{J yr}^{-1}$$

**第二步：把 NPP（碳质量）换算成生物量（葡萄糖）总质量。**
假设生物量近似为葡萄糖 $\text{C}_6\text{H}_{12}\text{O}_6$，先求碳的质量分数（见「三、公式与图表」第 7 条）：$f_{\text{碳}}=0.4$。于是：
$$\text{生物量总质量} = \frac{\text{NPP（碳质量）}}{f_{\text{碳}}} = \frac{14.7\times10^{15}\ \text{gC}}{0.4\ \text{gC/g(biomass)}}\approx3.67\times10^{16}\ \text{g}$$

**第三步：把生物量总质量换算成能量。**
$$1.6\times10^4\ \text{J g}^{-1}\times3.67\times10^{16}\ \text{g}\approx5.88\times10^{20}\ \text{J}$$

**第四步：求比例。**
$$\frac{\text{人类年食物能耗}}{\text{NPP 对应总能量}}=\frac{2.6\times10^{19}}{5.88\times10^{20}}\approx0.0425\approx4\%$$

**结论**：2008 年人类食物消耗约占地球每年净初级生产力（以能量计）的 **4%**。

### 延伸问题（Related problems）及解法思路
1. **用更精确的生物量分子式重算比例**：若用更贴近真实的干生物量化学式 $\text{H}_{2960}\text{O}_{1480}\text{C}_{1480}\text{N}_{160}\text{P}_{18}\text{S}_{10}$（而非简化的葡萄糖）重新计算碳质量分数：
$$f_{\text{碳}} = \frac{1480\times12}{(1\times2960)+(1480\times16)+(1480\times12)+(160\times14)+(18\times31)+(10\times32)}\approx0.37$$
代入同样步骤得生物量总质量 $\approx3.93\times10^{16}\ \text{g}$，对应能量 $\approx6.29\times10^{20}\ \text{J}$，最终比例 $\approx0.0413\approx4\%$——与简化模型结果几乎一致，说明用葡萄糖近似生物量是合理的简化。

2. **不同饮食结构（含肉食）下的比例**：肉类生产存在**能量转化损耗**——生产 1 J 牛肉能量需要约 8 J 谷物能量，1 J 禽肉需要约 3 J 谷物能量，其他动物性食品约需 5 J 植物能量换 1 J 产出。设饮食结构为 1/4 禽肉、1/5 牛肉、1/5 其他动物性食品、7/20 蔬食，则总共需要的「植物当量能量」为：
$$3\times\tfrac{1}{4}\times2.6\times10^{19}+8\times\tfrac{1}{5}\times2.6\times10^{19}+5\times\tfrac{1}{5}\times2.6\times10^{19}+1\times\tfrac{7}{20}\times2.6\times10^{19}\approx9.62\times10^{19}\ \text{J/yr}$$
除以 NPP 总能量 $5.88\times10^{20}$，得比例 $\approx0.16$（约 16%）——比纯素食情形（4%）高出约 4 倍，直观展示了肉食饮食结构对生态资源占用的放大效应。

3. **化石能源全部替换为生物质能所需的 NPP 比例**：直接用 2008 年化石燃料年能耗 $5\times10^{20}\ \text{J}$ 除以 NPP 总能量：
$$\frac{5\times10^{20}}{5.88\times10^{20}}\approx0.85\ (85\%)$$
结论：若要用生物质完全替代化石燃料，需要消耗地球 NPP 的约 85%，远超合理生态承受能力，说明「全面生物质能替代化石燃料」在生态上几乎不可行，会引发严重的粮食安全和生态问题。

4. **人口增长到「吃光」全部 NPP 需要多少年**（需要用到对数，为 Week 3+ 内容预热）：
   - 每人每年能量消耗：$1.05\times10^7\ \text{J/day}\times365\ \text{days/yr}\approx3.8\times10^9\ \text{J/yr/person}$。
   - 用 NPP 总能量除以人均年消耗，得到「NPP 能养活的人数上限」：
   $$\frac{5.88\times10^{20}}{3.8\times10^9}\approx1.53\times10^{11}\ \text{人}$$
   - 设人口年增长率 2%，$x$ 年后人口为初始人口的 $1.02^x$ 倍，列出**指示方程 (indicial equation)**：
   $$(6.7\times10^9)\times1.02^x = 1.53\times10^{11}$$
   - 两边整理并取自然对数求解：
   $$1.02^x = \frac{1.53\times10^{11}}{6.7\times10^9},\qquad \ln(1.02^x)=\ln\!\left(\frac{1.53\times10^{11}}{6.7\times10^9}\right)$$
   $$x\ln1.02 = \ln\!\left(\frac{1.53\times10^{11}}{6.7\times10^9}\right)\ \Rightarrow\ x=\frac{\ln\left(1.53\times10^{11}/6.7\times10^9\right)}{\ln1.02}\approx158\ \text{年}$$
   - 结论：按 2% 的年增长率，约 158 年后人类将需要消耗地球全部的 NPP 才能满足食物能量需求——这显然不可持续，凸显人口增长与地球生态承载力之间的矛盾。

### Homework / 作业提示
- 复习附录 C (Appendix C)，阅读附录 D (Appendix D)。
- 阅读 Croft and Davison (2006) 中「公式变形 (Transposing formulae)」一章，或 *Foundation Maths Support Pack* 的 2.7–2.12 节。
- 完成 Blackboard 本周测验：「Transposing formulae」与「The greens we eat」。
- 若补充材料仍有困难，把答案带到下次课堂与助教讨论。

## 六、易错点 / 重点难点

- **GPP 与 NPP 不可混淆**：NPP 是 GPP 扣除植物自身呼吸消耗后的净值，且 NPP 也不等于「植物新增生长的质量」，因为还要扣掉被取食、分解等损耗——题目反复强调这是最容易搞混的概念。
- **calorie 与 Calorie 大小写陷阱**：小写 calorie (cal) 与大写 Calorie (kcal，营养学中常用的「大卡」) 相差 1000 倍，粗心换算会导致三个数量级的误差。
- **计算生物量碳质量分数时不能只看碳原子数，要按摩尔质量（原子数×相对原子质量）加权**：葡萄糖中碳原子数是 6，占总原子数 (6+6+12=24) 的 25%，但按质量算碳只占 40%（因为氢原子很轻），这是学生最容易犯的「按个数而非按质量」的错误。
- **单位换算链条长，容易漏乘/漏除某一步**：从「每人每天 kcal」到「全球每年 J」要依次乘以人数、天数，并做 kcal→cal→J 的换算，任何一步顺序或指数错了都会导致数量级错误。
- **因式分解二次三项式时符号处理**：交叉相乘法中 $b$ 是两个交叉乘积之**和**，若三项式含负号（如 $v^2+3v-10$），寻找「和为 3、积为 -10」的两个数时要注意一正一负（5 和 -2），符号处理是常见失误点。
- **括号展开后同类项合并的顺序**：如 $(x-y)(x+z)=x^2-yx+zx-yz$ 要进一步合并为 $x^2+x(z-y)-yz$，直接把 $-yx+zx$ 相加而不提取公因子 $x$ 是常见疏漏。
- **对数求解指示方程时，等式两边必须整体取对数**，不能只对一边操作；且要记得 $\ln(a^x)=x\ln a$ 这一对数运算法则——这是本周首次接触，为后续几周的对数专题打基础，若感觉生疏（讲义原话："Leave if you are uncomfortable: we will come back to it later"）可以暂时跳过，后续课程会系统讲解。

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| fraction | 分数 | 表示整体中一部分的数，写作分子/分母 |
| proper fraction | 真分数 | 分子小于分母的分数 |
| improper fraction | 假分数 | 分子大于分母的分数 |
| mixed fraction | 带分数 | 整数部分加真分数部分组成的数 |
| percentage | 百分数 | 以百分之一为单位表示的比例 |
| expanding brackets | 展开括号 | 用分配律把括号外因子乘入括号内各项 |
| factorising | 因式分解 | 把多项式写成若干因子相乘的逆运算 |
| common factor | 公因子 | 多项式各项共有的因子 |
| cross-multiplication | 交叉相乘法 | 因式分解一般二次三项式的标准技巧 |
| specific heat capacity | 比热容 | 单位质量物质升高单位温度所需的热量 |
| calorie (cal) | 小卡 | 使 1 克水升温 1°C 所需的热量 |
| Calorie (kcal) | 大卡/千卡 | 使 1 千克水升温 1°C 所需的热量，1 Calorie=1000 calorie |
| Joule (J) | 焦耳 | SI 制能量单位，以物理学家 Joule 命名 |
| potential energy | 势能 | 物体因位置/高度而具有的能量，$E_p=mgh$ |
| law of conservation of energy | 能量守恒定律 | 能量不能被创造或毁灭，只能相互转化 |
| primary production | 初级生产 | 生物利用能量把无机物合成有机化合物的过程 |
| photosynthesis | 光合作用 | 利用光能将 CO2 和水合成有机物并释放 O2 |
| chemosynthesis | 化能合成 | 利用无机物氧化还原的化学能合成有机物 |
| autotroph / primary producer | 自养生物/初级生产者 | 能自行合成有机物、位于食物链底端的生物 |
| Gross Primary Productivity (GPP) | 总初级生产力 | 光合作用固定的全部碳/能量，未扣除呼吸消耗 |
| Net Primary Productivity (NPP) | 净初级生产力 | GPP 减去植物自身呼吸消耗后净剩的碳/能量，转化为生物量的部分 |
| biomass | 生物量 | 生物体内积累的有机物质总量 |
| NDVI | 归一化植被指数 | 用近红外与红光反射差异估算植被光合活性的遥感指标 |
| stoichiometry | 化学计量学 | 研究化学反应/分子中各元素定量关系的学科 |
| molar mass | 摩尔质量 | 一摩尔物质的质量，等于各原子相对原子质量按原子数加权求和 |
| glucose | 葡萄糖 | 分子式 C6H12O6，光合作用/化能合成的典型产物 |
| indicial equation | 指示方程 | 未知数出现在指数位置的方程，需用对数求解 |
| transposing formulae | 公式变形 | 通过代数运算重新排列公式以求解目标变量 |
