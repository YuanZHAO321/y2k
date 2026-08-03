# Mathematics and Physics (Hilary Term) — 课程总纲

> EART11200 *The Natural Scientist's Toolkit* · BSc Earth and Planetary Sciences 大一春季学期
> 授课人：Dr. Matthew Thomas（Week 9 由 Prof. David Topping 代课）
> 本文件是**骨架版复习总纲**，读者应已持有 Week 01–12 的十二份周笔记。
> 定位：串主线、理体系、汇公式、指重点、**列全课勘误表**。详细推导与逐题解法请回查对应周笔记。

---

## 一、这门课在讲什么

**一句话**：这是一门**为自然科学家而非数学系学生开设的微积分课**——它不证明定理，只训练"拿到一个真实过程，把它写成微分方程，再解回去"的能力。

三条设计原则贯穿全课：

1. **从数值直觉出发，再转解析。** Week 1 完全不讲任何微分法则，只用中学的 $\Delta y/\Delta x$ 做三种有限差分，让学生先"看见"梯度是什么、步长为什么要紧；Week 2 才把 $\Delta x\to 0$ 的极限正式变成导数。积分侧同样：Week 6 先用矩形逼近讲清"积分 = 求和 = 曲线下面积"，再转入查表的解析积分。
2. **每一个数学工具都必须落到一个真实物理定律上。** 放射性衰变、流体静力学方程、牛顿运动定律、Fourier 热传导、Fick 扩散——这五条定律像五根钉子，把十周的方法钉在地球科学的现实问题上（Cs-137 污染的羊、Mauna Loa 的 CO₂ 曲线、金矿何时停采、海洋云增白该不该做、地热田的温度剖面）。
3. **解析与数值互为验证，且都承认自己的局限。** 讲师反复强调"没有哪个方法永远最好"；模型选择、步长选择、假设放宽都会改变答案。可乐罐的数学最优解 $h=2r$ 与货架上的真罐子不一样，这本身就是课程想教的批判态度。

**技能落点**：Week 1–5 学会"求变化率并读懂它"；Week 6–10 学会"由变化率还原总量"；最后两周把这些工具对着往年真题重新排练一遍。

---

## 二、全课主线与各周脉络

**三段式结构**：微分段（Week 1–5）→ 积分段（Week 6–10）→ 复习段（Week 11–12）。

微分段本身又是"造工具（W1–3）→ 用工具（W4–5）"；积分段是"基本积分（W6）→ 物理应用（W7）→ 技巧升级（W8）→ 阶数升级（W9）→ 维度升级（W10）"。

| 周 | 主题 | 数学工具 | 应用场景 | 承接关系 |
|---|---|---|---|---|
| 1 | Calculating Gradients | Euler 向后/向前法、中心差分；代数与三角复习 | Mauna Loa CO₂、放射性衰变、斜面受力 | 全课起点：用割线近似切线，为"导数=极限"建立直觉 |
| 2 | Introduction to Differentiation | 一阶原理、幂律、常见导数表、和法则 | 衰变方程、流体静力学方程、气罐泄漏 | 把 W1 的 $\Delta x$ 取极限；首次"验证某函数是某 ODE 的解" |
| 3 | Combinations of Functions | 链式、乘积、商法则（三步法：拆→求导→合） | 生态水库三种排水模型、静力学方程 | 补齐 W2 只有"和"的缺口；讲师明言**本课微分法则到此为止** |
| 4 | Optimisation & Properties | 驻点、符号表、最优化七步法 | 金矿开采天数、可乐罐用铝、地球工程投入 | 从"怎么算导数"转向"导数能回答什么问题" |
| 5 | Second Order Derivatives & Root Finding | 二阶导判别法、稳态判据、Newton–Raphson | 焚烧炉浓度剖面、地温梯度、利润最小化 | 补 W4 两个缺口：驻点分类不严格、$f'=0$ 解不出来 |
| 6 | Introduction to Integration | 积分表、不定/定积分、分离变量法 | 衰变方程求解、静力学方程求解、Cs-137 羊 | **全课分水岭**：方向逆转，由 $f'$ 求 $f$ |
| 7 | Integration using Newton's Laws | $F=ma$ 的三种 ODE 形式、积分限配对 | 自由落体、斜面滑块、球体阻力 | 第一次让学生**自己造微分方程**（受力分析→ODE） |
| 8 | Integration by Substitution | 换元八步法（链式法则的逆） | 带温度递减率的静力学方程、逆风中的球 | 放宽一个物理假设 ⇒ 被积函数升级 ⇒ 必须换元 |
| 9 | Second-Order ODEs | 辅助方程法；稳态直接积分两次 | 阻尼振动、Fick 扩散、Fourier 传热 | 阶数升级；IVP 与 BVP 的分野在此确立 |
| 10 | Vectors and Partial Differentiation | 标量/向量场、向量运算、偏导数、$\nabla f$ | 地形坡度、通量的负梯度方向、天气模式 | 维度升级；为二年级的 PDE 与建模课铺路 |
| 11 | Revision: Differentiation | Crib Sheet 微分部分 + 往年卷 Q1/3/5/6/7 | — | 复盘 W1–5 与 W10 的微分侧 |
| 12 | Revision: Integration | Crib Sheet 积分部分、常数与物理定律表、**考试提供公式清单** + 往年卷 Q2/4/8/9/10 | — | 复盘 W6–9；给出全部应试规则 |

**一条贯穿的暗线**：同一个物理场景反复出现、逐周加码。静力学方程在 W2 是"验证解"、W3 是"链式法则练习"、W6 是"分离变量求解"、W8 是"放宽等温假设后换元求解"、W12 是"往年卷最难的一题"。看懂这条线，就看懂了这门课的设计。

---

## 三、知识体系（按知识块重组）

### 3.1 微分技巧链

$$\text{一阶原理}\ \xrightarrow{\ \text{归纳}\ }\ \text{幂律与导数表}\ \xrightarrow{\ \text{组合}\ }\ \text{链式/乘积/商}\ \xrightarrow{\ \text{重复}\ }\ \text{高阶导数}\ \xrightarrow{\ \text{推广}\ }\ \text{偏导数}$$

- 定义层：$\dfrac{dy}{dx}=\lim\limits_{\Delta x\to0}\dfrac{\Delta y}{\Delta x}$，由 $y=ax$、$y=ax^2$ 两个一阶原理推导归纳出幂律（讲师明说**考试不要求重做一阶原理推导**）。
- 组合层：三条法则的操作流程完全一致——**拆 (split) → 各自求导 (differentiate) → 用公式合回去 (recombine)**。拆分的唯一判据是"拆到每块都能在基本导数表里直接查到"。
- 判别法则的方法：看**最外层的那一次运算**（加减→逐项；乘→product；除→quotient；套→chain）。能展开就展开、能约分就约分往往更快。
- 高阶层：$f''=\frac{d}{dx}(f')$，物理上是"变化率的变化率"（位移→速度→加速度）。
- 多变量层：偏微分**没有任何新求导技巧**，唯一的新东西是"哪些字母现在算常数"。

### 3.2 积分技巧链

$$\text{基本积分表}\ \to\ \text{分离变量}\ \to\ \text{换元积分}\ \to\ \text{二阶 ODE（辅助方程 / 积分两次）}$$

- 积分表就是导数表**从右往左读**——不要单独背积分表。唯一需要小心的是三角函数负号的位置（微分负号跟 $\cos$，积分负号跟 $\sin$）。
- 微分是机械的，**积分本质上是模式识别**：认出"这个式子长得像谁被微分后的样子"。因此练习量不可替代。
- 分离变量三句话固定模板：**除以含 $y$ 的因子 → 两边乘 $dx$ → 两边积分**。
- 换元法是链式法则的逆过程；选 $u$ 的黄金法则是"取函数内部那一坨"，本课几乎全是 $u=ax+b$（讲师明说这是考试提示）。**不定积分换 2 样（函数、$dx$），定积分换 3 样（再加上下限）。**
- 二阶 ODE 分两条路：右端为 0 且含 $y$ 项 → 辅助方程；不含 $y$ 项（如 $\frac{d^2T}{dx^2}=0$）→ 直接积分两次。**别在稳态题上浪费时间写辅助方程。**

### 3.3 数值方法链

- **数值梯度（W1）**：三种差分的可用范围、误差阶（单边 $O(\Delta x)$ 线性收敛，中心 $O(\Delta x^2)$ 二次收敛）。教训：①步长越小越准但计算量越大；②百分比误差在导数接近零处会爆炸；③时间尺度选错会把季节信号当成长期趋势（CO₂ 那题）。
- **数值求根（W5）**：Newton–Raphson $x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}$，来自"沿切线滑到 $x$ 轴"。二次收敛，但**不保证收敛**（除零、发散、循环、跑到别的根、重根变慢）。多根问题必须先画图、逐根设初值。
- **数值积分**：讲师明说**不做**（比数值微分麻烦得多），矩形逼近只作为概念来源。
- **贯穿的方法论**：解析值与数值值互相验证；判断步长是否够小的实用做法是"再试一个更小的，看结果是否稳定"。

### 3.4 多变量推广（W10）

标量场 $f(x,y,z)$ → 偏导数 $\partial f/\partial x$ → 梯度向量 $\nabla f$。核心认知：**$f$ 是标量场，$\nabla f$ 是向量**——这就是"向量"和"偏微分"必须放在同一周的原因。梯度指向最陡上升方向，其模是最陡坡度；自然界的通量几乎总是沿 $-\nabla f$（Fourier、Fick、Darcy 定律里的那个负号）。PDE 只介绍概念，**不要求求解**。

### 3.5 物理应用链（五条定律 + 一张对照表）

| 定律 | 微分方程 | 求解方法 | 出现周 |
|---|---|---|---|
| 放射性衰变 | $\dfrac{dN}{dt}=-\lambda N$ | 分离变量 → $N=N_0e^{-\lambda t}$ | W1, W2, W6 |
| 流体静力学（等温） | $\dfrac{dP}{dz}=-\dfrac{gP}{R_aT}$ | 分离变量 → 指数衰减 | W2, W3, W6 |
| 流体静力学（变温） | $\dfrac{dP}{dz}=-\dfrac{gP}{R_a(T_s-\alpha z)}$ | **换元积分** → 幂律 | W8, W12 |
| 牛顿第二定律 | $F=m\frac{dv}{dt}=mv\frac{dv}{dx}=m\frac{d^2x}{dt^2}$ | 受力分析 + 分离变量 + 配限 | W7, W9, W12 |
| Fourier 热传导（稳态） | $\dfrac{d^2T}{dx^2}=0$ | 积分两次 + 边界条件 → 线性剖面 | W5, W9 |
| Fick 扩散（稳态） | $\dfrac{d^2C}{dx^2}=0$ | 同上 | W5, W9 |

**最值钱的一条模式识别**：只要"某量的变化率正比于该量自身"，解一定是指数函数
$$\frac{dy}{dx}=ky\ \Longrightarrow\ y=y_0e^{kx}$$
衰变（$k=-\lambda$）、气压随高度（$k=-g/R_aT$）、牛顿冷却、人口增长全是这一条。同理，**Fourier 与 Fick 数学上完全同构，记住一个等于记住两个。**

---

## 四、核心公式速查（含"考试是否提供"）

依据主手册第 14 章与 2023–24 真题卷第 2 页：**第 14 章有的 = 不用背；没有的 = 必须背。**

### 4.1 会提供 ✅

| 类别 | 内容 |
|---|---|
| 三大法则 | $\dfrac{df}{dx}=\dfrac{df}{dg}\dfrac{dg}{dx}$；$\ u\dfrac{dv}{dx}+v\dfrac{du}{dx}$；$\ \dfrac{v\frac{du}{dx}-u\frac{dv}{dx}}{v^2}$ |
| 常见导数表 | $x^n\to nx^{n-1}$；$e^{f(x)}\to f'e^{f(x)}$；$\ln x\to\frac1x$；$\sin x\to\cos x$；$\cos x\to-\sin x$ |
| 常见积分表 | $x^n\to\frac{x^{n+1}}{n+1}$（$n\ne-1$）；$\frac1x\to\ln x$；$ke^{kx}\to e^{kx}$；$\cos x\to\sin x$；$\sin x\to-\cos x$；常数 $c\to cx$ |
| Newton 法 | $x_{n+1}=x_n-\dfrac{f(x_n)}{f'(x_n)}$（在第 14 章内；真题中随题干给出） |

> 常用衍生式（表上没有但必须会）：$\displaystyle\int e^{kx}dx=\frac1k e^{kx}+d$，$\displaystyle\int f(ax+b)dx=\frac1a F(ax+b)+c$。

### 4.2 不提供 ❌ —— 必须背

| 内容 | 公式 |
|---|---|
| 三种有限差分 | $\dfrac{y_x-y_{x-\Delta x}}{\Delta x}$，$\dfrac{y_{x+\Delta x}-y_x}{\Delta x}$，$\dfrac{y_{x+\Delta x}-y_{x-\Delta x}}{\mathbf{2}\Delta x}$ |
| 二阶导判别法 | $f''<0$ 极大；$f''>0$ 极小；$f''=0$ **不定** |
| 稳态判据 | 一阶导为常数 ⟺ 二阶导 $=0$ |
| 牛顿第二定律三形式 | $m\frac{dv}{dt}$（速度↔时间）、$mv\frac{dv}{dx}$（速度↔距离）、$m\frac{d^2x}{dt^2}$（位移↔时间）——讲师点名 $v\frac{dv}{dx}$ 最易忘 |
| 恒定加速度三式 | $v_1=v_0+at$；$v_1^2=v_0^2+2ax$；$x=v_0t+\frac12at^2$（**仅当 $a$ 为常数**） |
| 斜面分解 | 法向 $mg\cos\theta$；沿坡 $mg\sin\theta$；摩擦 $\mu N$，恒逆运动方向 |
| 二次求根公式 | $\lambda=\dfrac{-b\pm\sqrt{b^2-4ac}}{2a}$ |
| 二阶 ODE 通解 | $\Delta>0$：$Ae^{\lambda_1x}+Be^{\lambda_2x}$；$\Delta=0$：$(A+Bx)e^{\lambda_1x}$；$\Delta<0$ 不考 |
| 稳态线性剖面 | $T(x)=T_0+\dfrac{T_L-T_0}{L}x$（浓度同形） |
| 衰变与半衰期 | $N=N_0e^{-\lambda t}$，$\lambda=\dfrac{\ln 2}{t_{1/2}}$ |
| 向量与梯度 | $\lvert\bar a\rvert=\sqrt{a_1^2+a_2^2+a_3^2}$；$\hat a=\bar a/\lvert\bar a\rvert$；$\nabla f=\langle f_x,f_y,f_z\rangle$；$\lvert\nabla f\rvert$ |
| 百分比误差 | $100\times\dfrac{\text{数值}-\text{解析}}{\text{解析}}$ |
| 对数/指数律 | $\ln a-\ln b=\ln\frac ab$；$e^{A+\ln B}=Be^A$（每道 ODE 的收尾动作） |

---

## 五、跨周的核心思想与方法论

1. **数值与解析互为验证。** 这是全课第一条也是最后一条方法论：W1 用差分逼近、W2 给出解析导数并对表；W5 在能用求根公式验证的二次方程上先建立对 Newton 法的信任；W8 每做完一个不定积分就"微分回去检查"。往年卷 Q7 直接考"解析速率 vs 中心差分速率 + 百分比误差"。

2. **积分常数必须由物理信息定出。** 数学上的"任意常数"就是物理上"必须去实地测量的量"（代课讲师的原话）。一阶 ODE 一个常数、二阶 ODE 两个常数；**初值问题**在同一点给函数值和导数值，**边值问题**在两个不同点各给一个值。写法上，本课推荐"配对积分限"而非"先不定积分再代入"——不会漏常数，也不会代错。

3. **把物理问题翻译成微分方程，再解回去。** 固定流程：画受力/流程图 → 沿运动方向或沿梯度方向求和 → 选对 ODE 形式 → 分离变量 → 配限积分 → 代数值 → **回答题目真正问的那个量并写单位**。W7 的"五步法"、W4 的"最优化七步法"都是这个骨架的具体化。

4. **量纲与单位是免费的检验工具。** "看单位就知道该微分还是该积分"：$\mathrm{m^3\,s^{-1}}\times\mathrm{s}=\mathrm{m^3}$、$\mathrm{mm\,hr^{-1}}\times\mathrm{hr}=\mathrm{mm}$。积分常数永远与被解出的量同量纲；每积一次 $dt$ 单位就乘一个 s。

5. **放宽一个假设 = 让数学难一级。** 温度恒定 → 指数解（查表即可）；温度线性递减 → 幂律解（必须换元）。这条洞见把 W6、W8 串成一体，也解释了为什么真实科研最终要走数值方法。

6. **符号与合理性检验的习惯。** 算完先问：符号对不对（函数在此处是升是降？阻力是不是减号？）、量级对不对（气压该是 $10^5$ Pa 而不是 0.887 Pa）、极限情形对不对（$\theta=90°$ 该退化成自由落体）。

7. **质量能否约掉，取决于是否所有力都正比于 $m$。** 自由落体、斜面下滑能约掉（所以真空中砖头与羽毛同速）；阻力 $\propto r^2v^2$ 与质量无关，所以 $m$ 必须留着——"同样大小的球，越重滑得越远"。

8. **模型选择本身是科学判断。** 同一个"水库排空"，指数、高斯、幂律三种模型给出量级相近但明显不同的速率；地球工程该不该做，完全取决于一个不确定参数 $d$ 落在临界值哪一侧。数学最优解只在模型假设内最优。

---

## 六、重点与难点分布

### 6.1 权重分布

考试 2 小时、100 分、10 题（每题 10 分）、**5 题微分 + 5 题积分**、难度由 Q1 递增到 Q10。据此倒推的复习权重：

| 优先级 | 内容 | 理由 |
|---|---|---|
| ★★★ | 三大法则的熟练应用与化简（W3） | 微分侧几乎每题都要用；往年 Q6 三小问全考它 |
| ★★★ | 分离变量 + 换元积分（W6、W8） | 积分侧的 Q9、Q10 都靠它；Q10 是全卷最难题 |
| ★★★ | 牛顿定律建 ODE + 积分限配对（W7） | 往年 Q8；"选错 ODE 形式"和"限设错"是两大失分源 |
| ★★ | Newton 法求根（W5） | 往年 Q3；流程固定，每次迭代 3 分，是稳拿分题 |
| ★★ | 最优化：驻点 + 二阶导判别（W4、W5） | 往年 Q5；注意题目说 "find" 就不必再 "prove" |
| ★★ | 定积分求值、基本积分（W6） | 往年 Q2、Q4；讲师称"送分题，期待 10/10" |
| ★★ | 二阶 ODE：辅助方程 + 稳态积分两次（W9） | 公式全部不提供，必须背 |
| ★ | 数值梯度 + 百分比误差（W1） | 往年 Q7 |
| ★ | 偏导数与梯度向量（W10） | 变量数不超过三个；PDE 不考 |

### 6.2 难在哪里

- **W3（组合函数）**：商法则的分子顺序（$v\,du-u\,dv$，不能颠倒）、多重嵌套漏层、化简收尾。讲师明说往年"化简翻车最多"。
- **W7/W8（物理建模）**：不是数学难，是**读题难**——"10 米后"和"10 秒后"用不同的 ODE，答案能差四倍。
- **W9（二阶 ODE）**：重根情形 $(A+Bx)e^{\lambda x}$ 及其乘积法则求导；IVP 与 BVP 用错条件。
- **W12 的 Q10（变温静力学）**：换元 + 换限 + 有效数字 + 百分比差，四层叠加，讲师亲口称"全卷最难"。

### 6.3 两个复习周老师圈定的重点（务必照做）

- **"今年的题会和去年非常相似"** → 往年真题是最高优先级材料。往年卷在 Blackboard 的 "Easter break" 文件夹，解答在复习课后才发。
- **必须写出过程。** 讲师在两周复习课上各强调三次以上：只写答案且答案错 = **0 分**；写了过程即使错也可能拿 5–9 分（**follow-through marks**：前面算错，只要后续方法正确仍给分）。**发现算错也要一路做到底，绝不中途停笔。**
- **不按 1→10 顺序做题**，先做最有把握的。
- **只有草稿纸不批改**，所有得分内容必须写进答题册；字迹必须可辨。
- **角度单位**：题目写 degrees 用 DEG，没写默认 **radians**。
- **画带标注的示意图有分**（往年 Q8(b) 的受力图值 2 分，不需任何计算）。
- **计算器**：不得存文本、不得做代数、不得有绘图功能。
- Crib Sheet（主手册第 12 章）**不能带进考场**；考场只给第 14 章那一页公式。

---

## 七、全课勘误表

> ⚠️ 本节是本课总纲的特殊任务。以下为十二份周笔记中记录的**原始官方材料自身的错误**（印刷、算术、符号、题号交叉引用、前后定义不一致等），按周汇总。**用官方 PDF 复习时请对照本表。**
> 共 **62 条**（不含单纯的 PDF→md 转换丢失，那部分另见 §7.3）。

### 7.1 勘误汇总表

| 周 | 出处文件 | 位置/题号 | 原文 | 应为 | 说明 |
|---|---|---|---|---|---|
| 1 | 主手册 Ch.1 | Q1.13 答案表 | $x=6$ 解析值 $-0.69$ | $-0.68$ | $0.5/\sqrt6+\frac29(-4)=-0.6848$；差值表给 0.00 亦印证 |
| 1 | 主手册 Ch.1 | Q1.16(b) 解答 | "as we **increase** the step size the accuracy increases" | **decrease** | 方向写反，与自己给的表格矛盾 |
| 1 | 主手册 §1.2 | 正文 | 向前法 "you can start at $x=4$ … up to $x=18$" | 应从 $x=2$ 起算 | "start at 4" 是从向后法段落沿用的笔误 |
| 1 | lecture1 幻灯片 | 重排示例 | $y=\sqrt x+2\Rightarrow x=y^2-2$ | $x=(y-2)^2$ | 根号覆盖范围不一致 |
| 1 | lecture1 幻灯片 | Euler backward | 公式写错 | — | 讲师 Week 2 当堂承认并已更正 |
| 1 | Practical/Week 1 | 目录结构 | 放的是 `Chapter1(1).md` | 应为 `Exercises1` | 第 1 章习题只能查主手册 |
| 2 | 主手册 | Figure 2.1 图注 | $2x^3-20x^2+x\,{*}\,4000$ | $+4000$ | |
| 2 | 03-Feb transcript | 二次函数一阶原理 | "2ax·Δx + Δx²"、"dy/dx = 2a" | 漏 $a$、漏 $x$；正确 $\frac{dy}{dx}=2ax$ | 两处口误，以幻灯片为准 |
| 2 | 主手册 | 题号系统 | 题号与章号不自洽 | 以周版 Exercises 为准 | 全课通病 |
| 3 | lecture3 slide 7 | 静力学方程 | $=-\dfrac{P}{R_\alpha T}P$ | $=-\dfrac{g}{R_\alpha T}P$ | 排版把两处压在一起 |
| 3 | lecture3 slide 10, 13 | 乘积/商法则反例 | $v(x)=x^6\Rightarrow\frac{du}{dx}=6x^5$ | $\frac{dv}{dx}=6x^5$ | |
| 3 | lecture3 全部 slide | Step 3 说明 | "Apply the **product** rule" | 应随该页法则而定 | 复制粘贴，chain/quotient 页全错 |
| 3 | lecture3 / Chapter3 | ILO 第 (3) 条 | "products of functions" | "**quotients** of functions" | |
| 3 | Chapter3 | Example 3.2 中间步 | $\sqrt{13x^2-5x+8}$ | $\sqrt{13x^2-6x+8}$ | 最终答案正确 |
| 3 | Chapter3 | Example 3.6 答案 | $\dfrac{-3x^2+2x-3}{(x^2+1)^2}$ | $\dfrac{-3x^2-2x+3}{(x^2+1)^2}$ | 中间项与常数项符号均错 |
| 3 | Chapter3 | Example 3.5 / 3.6 行文 | "using the **product** rule formula" | quotient rule | |
| 3 | Solutions3 | Q3.4(b) | $\frac{du}{dx}=\cos(v)$ | $\frac{du}{dv}=\cos(v)$ | |
| 3 | Solutions3 | Q3.5(b) | "we have been given **3** points where the derivative is zero" | 只有 2 个根（$-\frac12,\frac14$） | |
| 3 | Solutions3 | Q3.7(a) | $-\frac13e^{-1/6}=-0.1829$ | $=-0.2822$ | 解析式对，数值代入错 |
| 3 | Solutions3 | Q3.7(c) | 分母 $(2w^2+1)^2$ | $(t^2+10)^2$ | 从上一题复制残留 |
| 3 | Exercises3 | Q3.4 题干 | "use the result of (a) in **(b)-(e)**" | 实际只有 (a)-(d) | |
| 3 | Exercises3 | Q3.6(a) | $Z(s)=\ldots$ | 变量应为 $x$ | |
| 3 | Exercises3 | Q3.7(c) | $V(t)=\frac{V_0(x+10)}{x^2+10}$ | 变量应为 $t$ | |
| 3 | practical3_soln | Exercise 3 展开 | $\ldots+8x^2-16x^3-16x^3+16x^3$ | 第二项应为 $-16x^2$ | 最终结果正确 |
| 4 | lecture4 slide 8 | 导数符号与单调性 | "If $f'(x)>0$ then $f(x)$ is **decreasing**" | $f'(x)<0$ | 讲师当堂更正 |
| 4 | 主手册 Ch.4 / slide 11 | Example 4.2 | "a minimum occurs (**$x=2$**)" | $x=1$ | 同一材料后文又写 $x=1$，自相矛盾 |
| 4 | lecture4 复习页 | chain / quotient 的 Step 3 | "Apply the **product** rule" | 应分别为 chain / quotient | 三页复习全错 |
| 4 | Solutions4 | Q4.1(b) | 只写到 $2-2x=0$ 就断了 | 应补：$x=1$，maximum | 结论缺失 |
| 4 | Solutions4 | Q4.6(a) | $P=80{,}000$ | 按题给系数算得 $81{,}000$ | 数值不自洽 |
| 4 | 主手册 / Solutions4 | Q4.7 符号 | 正文用 $T=E+C$，图与解答用 $\chi$ | 统一用 $\chi$ | 与温度 $T$ 撞符号 |
| 4 | Solutions4 | Q4.7 结论措辞 | "we can only **increase the temperature** by implementing the scheme" | 应为"只会增加**总成本**" | 表述不严谨 |
| 5 | Solutions5 | Q5.2(a) | "two stationary values at $x=-6$ and $x=-5$" | $x=-6$ 与 $x=+5$ | 后文自己又写 $x=5$ |
| 5 | Solutions5 / 主手册 | Q5.3 | "assuming it is between $x=4$ and $x=6$" | 题干为 $[3,4]$ | 前后矛盾，以题干为准 |
| 5 | Solutions5 | 交叉引用 | "from Chapter 3 Question 5.4(a)"、"Chapter 2 Question 5.8" | 编号错乱 | 一律以周版 Exercises5 为准 |
| 5 | lecture5 幻灯片 | Q5.3 第一步 | $x_1=3.5-\frac{3.6154}{19.1154}$ | 两个负号被省略 | 比值不变，但手算宜保留符号 |
| 5 | practical5 vs Exercises5 | Q5.6 | $C_1=0.11$ vs $C_{1km}=0.1$ | 两版本数字不同 | 方法一致，勿混 |
| 5 | 24-Feb transcript | 稳态一节 | 污染物例与汽车例讲串 | 以 $x(t)=1+68t$ 汽车版为准 | 讲师中途自我叫停 |
| 5 | 24-Feb transcript | Newton 法推导 | 符号混乱、断续 | 以讲义 §5.3 为准 | 讲师自认 "I completely messed that explanation up" |
| 6 | 03-Mar transcript | 常数抵消一段 | 把 definite 说成 **indefinite**（多次） | 语义应为 definite | 以幻灯片与手册为准 |
| 6 | practical6_soln | 静力学方程 | "if we say at **$t=0$**" | $z=0$ | 从衰变页复制残留 |
| 6 | 主手册 Ch.6 | 衰变方程称谓 | "**Newton's** radioactive equations" | 与牛顿无关 | |
| 6 | practical6_soln | Exercise 1(2) | 题面 $+9w^3$ 与答案 $-\frac94w^4$ | 符号不一致 | 原题应为 $-9w^3$ |
| 6 | 主手册 / Chapter6 | OCR | $R_a$ 印成 $R\alpha$、$\rho$ 印成 $\exists/\forall$ | $\rho=P/(R_aT)$，$R_a=287$ | |
| 7 | practical7_soln | Exercise 2 答案 | "8.5 m/s" | $\sqrt{78.4}=8.85$ m/s | 与其自身条件不符 |
| 7 | Solutions7 | Q7.9 | "use the general formula we developed in Question **7.8**" | Question **7.7** | |
| 7 | Exercises7 vs practical7 | 摩擦力定义 | $0.1\times$ contact force ($=0.1mg\cos\theta$) vs $0.1mg$ | 两份材料定义不同 | 考试务必读清题面 |
| 7 | 10-Mar transcript | 牛顿第二定律 | "force times mass equals force" | $F=ma$ | 口误 |
| 7 | 主手册 §7.3 | $a=v\frac{dv}{dx}$ 推导 | PDF 转换后语句错乱 | 见链式法则推导 | |
| 8 | 17-Mar transcript | 定积分求值 | "you end up with **3124** divided by 15" | $3126/15=208.4$ | $5^5-(-1)^5=3126$ |
| 8 | 17-Mar transcript | 三角积分 | "cos integrates to minus cos" | $\int\cos u\,du=\sin u+c$ | 讲师立刻自我更正 |
| 8 | 17-Mar transcript | 第 4 步 | 先说 $\frac{du}{dx}$ | 本课标准写法是 $\frac{dx}{du}$ | 讲师自我更正 |
| 9 | 主手册（第 3099 行） | 齐次定义 | "if $d(x)=0$ the equation is called **non-homogeneous**" | $d(x)\neq0$ | 周版 Chapter9 是对的 |
| 9 | 主手册 | 应用列表 | $\frac{d^2C}{dt^2}=0$、$\frac{d^2T}{dt^2}=0$ | 应为 $\frac{d^2C}{dx^2}$、$\frac{d^2T}{dx^2}$ | 自变量印错 |
| 9 | Exercises9 | Q9.1 小题编号 | (a)(b)(c)**(e)** | 应为 (a)(b)(c)(d) | 跳号 |
| 9 | Solutions9 | Q9.2(b)(c)(d) | 均写 "From Question **9.1(a)**" | 应分别对应 9.1(b)(c)(e) | 复制粘贴 |
| 9 | Solutions9 / 主手册（3347 行） | Q9.3 | 根 $\frac43$ 与 $-2$ 却说 "real and **equal**"；且 $\frac43$ 排版成 "3/4" | real and **distinct**；根为 $\frac43$ | 照 "equal" 会误套重根公式 |
| 9 | Solutions9 | Q9.5(b) | $F=mg\sin30°-mg\cos30°$ | $F=mg\sin30°-\boldsymbol{\mu}\,mg\cos30°$ | 漏摩擦系数，导致加速度为负、物理荒谬 |
| 9 | Solutions9 | Q9.6 / Q9.7 | "**Differentiating** once/twice gives us" | "**Integrating** once/twice" | 方向写反 |
| 9 | Solutions9 | Q9.7 | "the solution to **Fick's** law" | **Fourier's** law | |
| 9 | Solutions9 | Q9.2 各题 | "the full **general** solution" | full solution | 定完常数即非 general |
| 9 | practical9_soln | Exercise 1 题面 | $\frac{d^2y}{dx^2}-\frac{dy}{dx}-6=0$ | $-6y=0$ | OCR 掉字 |
| 9 | 24-Mar transcript | 术语 | 根念作 "gamma"、说成 "$y_1$ and $y_2$"；$\alpha$ 说成 thermal **conductivity** | $\lambda$、$\lambda_1,\lambda_2$；thermal **diffusivity** | 以讲义为准 |
| 10 | 主手册 §11.3 / lecture10 p.13 | 两点求向量 | "using a **start minus end** approach" | **end minus start**（$\overrightarrow{AB}=B-A$） | 与其自身解答及数值答案矛盾；照字面算全错 |
| 10 | lecture10 p.10 | VECTOR FIELDS | "For example, **wind speed** – but not direction." | 应为风向/风矢量 | 从上一页复制残留 |
| 10 | lecture10 p.17 | 例题 | "$\bar b=\langle2,1\rangle=4\hat i+3\hat j$" | $=2\hat i+\hat j$ | 讲师口头更正 |
| 10 | Solutions10 | Q10.8(c) | "$v$ only appears in the **exponential**" | in the **denominator** | 从 (b) 复制残留 |
| 10 | 主手册 §11.4 / lecture10 p.19 | 术语 | 把 $\partial f/\partial x$ 称为 "partial differential **equation**" | partial **derivative** | 同页后半已改口 |
| 10 | Chapter10.md §10.2 | 标题与定义 | 标题缺失、"a **scalar** is a function…" | "Scalar **fields**"、"a scalar **field** is…" | |
| 11 | Revision_Differentiation | 周号标注 | 标 "WEEK 11" | 实为课程 Week 10（向量与偏微分） | 用的是学期绝对周号；讲师已口头更正 |
| 11 | Revision_Differentiation | Q6(a) 答案 | 提公因子后写成 $\cos x+\sin x$ | $5\cos x+\sin x$ | 学生当场指出，讲师承认并将修正 |
| 11 | 2324_Exam | Q1(d) | $f=5x^n\Rightarrow f'=5nx$ | 指数 $n-1$ 印刷遗漏 | 讲师："imagine there's a mystical $n-1$" |
| 11 | 02-May transcript | 术语 | quotient rule 被识别成 "**Cauchy** rule" | quotient rule | 自动转写误听 |
| 11 | 02-May transcript | Q3 迭代值 | 口述 "$-0.734$" | $-0.703$ | 幻灯片为准 |
| 11 | Revision_Differentiation p.3–5 | 例题设定 | 幻灯片写 "At $x=4$"，转写说 $x=16$ | 以幻灯片 $\Delta x=0.25$ 设定为准 | |
| 12 | 主手册 §13.4 | 中子/质子比 | "$146/92=1.587\%$" | 是比值 1.587，非百分比 | |
| 12 | 主手册 §13.6 | Fourier 第一定律 | 面积 $A$ 单位写 $\mathrm{m^{-2}}$ | $\mathrm{m^{2}}$ | |
| 12 | 主手册 表 13.4 | 公制词头 | milli($10^{-3}$) 直接跳到 nano($10^{-9}$) | **漏 micro (μ, $10^{-6}$)** | 真题 Q5 的 μg·m⁻³ 就要用 |
| 12 | 09-May transcript | Q8(a) | "which is 29 metres per second" | **49 m/s** | 语音转写错误 |
| 12 | Revision_Integration | 两处表格 | 排版错误 | — | 讲师承认并将修正后上传 |

### 7.2 章号与题号偏移（结构性问题，非笔误）

- 主手册**第 9 章 Integration by Parts 从未拆入任何一周**（官方十周主题表不含此项，全部课堂逐字稿零次提及，该章习题与解答本身也是空的）。
- 因此**自 Week 9 起，周版章号比主手册章号小 1**：
  - 周版 Chapter 9（Second-Order ODEs）= **主手册第 10 章**
  - 周版 Chapter 10（Vectors and Partial Differentiation）= **主手册第 11 章**
- 主手册的**题号亦比章号小 1**（例如主手册第 10 章里印的是 Q9.x），加之 PDF 转换造成的交叉引用错乱，**引用题号一律以周版 `ExercisesN.md` / `SolutionsN.md` 为准**。
- 未受偏移影响的仍是：第 12 章 Crib Sheet、第 13 章 常数与物理定律、第 14 章 考试提供公式。

### 7.3 "由答案反推重建"的内容清单（复习时请留意）

本课原始材料的 PDF→md 转换损耗极其严重：**主手册与各周文件中的大量公式、例题、题面函数原本是图片，转换后只剩文字骨架**。各周笔记采用了由官方解答/数值结果反推重建的办法补全，并已逐一验算。以下内容属于**重建结果**，与 PDF 原件核对时可能存在形式差异（数学结论已验证自洽）：

| 周 | 重建内容 | 反推依据 |
|---|---|---|
| 1 | Q1.13 主函数 $y=\sqrt x+\left(\frac{x-10}{3}\right)^2$、Q1.16 三次函数 $f(x)=x^3+2x^2-5x+16$、指数律与对数律表 | 解答表逐点验算 |
| 1 | Q1.9 题干与答案、Q1.2(c)、Q1.4(b)(c)(d) | **未能可靠还原，请以 PDF 为准** |
| 2 | Q2.3、Q2.5(b)–(f)、Q2.6 的答案；Q2.9 的四个体积函数 | 解答残留文字 + practical 同构题；**Q2.9 精确题面请查 PDF** |
| 3 | 全部公式已从对应 PDF 重新抽取核对（可当原件用）；Q3.6(b)(c) 来自 `Exercises3.pdf` 第 2 页 | — |
| 4 | practical Exercise 1 的函数 $f(x)=\frac{x^3}{3}+x^2-15x+c$ | 解答的驻点反推 |
| 5 | Q5.5 的三次函数 $x^3-x^2-15x+1$（由三个根 + 韦达定理反推）；Q5.8 的利润函数 $P(x)=e^x-3x^2$ | 迭代路径与最终答案完全复现 |
| 6 | Q6.5 的 ODE 形式、Q6.6 的流量函数 | 解答步骤文字（"multiply both sides by $N$"、"using Q6.4(b)"）；**精确题面请查 PDF** |
| 7 | 阻力公式系数 $\frac12$ | 由 Q7.5 答案 14.66 m 唯一确定 |
| 8 | Solutions8 的全部公式（md 版只剩"用哪个代换"的文字） | 按指定代换逐步补全并核算 |
| 9 | Q9.1(a) 的通解、Q9.3 的方程 $3y''+2y'-8y=0$、Q9.4 的方程 $y''-4y'+4y=0$ | 由根与条件反推，已验算 |
| 10 | Solutions10 的全部推导 | 数值与原解答给出的数字（145.1、$\sqrt{50}$ 等）一致 |
| 11 | Revision 幻灯片 §2.2 的例题函数、Q7 的 $V(t)$ | **均未能还原，请查 `Revision_Differentiation.pdf` 第 3–5 / 39–43 页或 `2324_Exam.pdf`**；但方法、关键数值与误差算法完整 |
| 12 | Q4 的被积函数 $\int_{-3}^{4}(f^2-e^{3f})df$ | 转写还原 |

**使用建议**：总纲与周笔记中凡涉及**具体函数表达式**的地方，若要用于精确核对，优先查 PDF 原件；若只是练方法与流程，重建版完全够用（所有重建都通过了数值验算）。

---

## 八、与其他课程的衔接

**向后接（秋季学期）**：本课明确以 Michaelmas Term 的 Introductory Maths 为地基。Week 1 用整整一章复习幂与指数律、对数律与换底、方程重排、直角三角形与弧度制——这些不是新内容，而是"后面九周的地基"。若秋季学期这块不牢，Week 3 的分数指数、Week 6 的对数律收尾、Week 8 的换元反解都会连锁失分。

**横向接（同学期）**：

- **Programming（David Toppin 部分）**：讲师多次点名，Week 1 的三种差分、Week 5 的 Newton 迭代、Week 6–9 的 ODE 求解，在编程课里会被实现成代码或调用 solver。本课手算是为了理解机制，真实科研中"一行代码"就能解。两门课构成"理解机制 → 自动化执行"的完整链条。
- **Statistics**：数值导数的误差分析、相对误差与绝对误差的区别、时间尺度选择导致的信号混叠（Mauna Loa CO₂ 那题），是数据分析思维的初级版本。
- **Chemistry of the Earth**：放射性衰变与半衰期（地质年代学的定量基础）、Fick 扩散（矿物中的元素扩散、同位素交换）、理想气体定律与分压。
- **地球系统类课程**：流体静力学方程与标高、温度递减率与对流层顶、行星边界层与城市污染累积、地温梯度与热流。

**向前接（二年级及以后）**：

- **Mathematical Modelling**：讲师明说明年会用计算方法处理本课点到为止的内容——偏微分方程、数值积分、优化算法（一维的 Newton 法在多维就是靠 $\nabla f$ 指路的梯度下降；二次求导得到的矩阵叫 Jacobian/Hessian）。
- **大气与海洋动力学**：Week 10 的标量场、向量场、梯度与通量的负梯度方向，直接是流体力学与气象学的语言；Fourier/Fick 的稳态形式一放宽就是扩散方程（PDE），也就是现代天气预报模式的内核。
- **地球物理与地热**：Fourier 定律的稳态解给出线性地温剖面；剖面弯曲即意味着存在源汇（放射性生热、地下水对流、岩浆侵入）——这是把数学结论读成地质结论的标准范式。
- **环境评估与政策**：Week 4 的成本效益分析框架（边际收益 = 边际成本、结论对不确定参数极度敏感）与 Week 5/9 的浓度剖面超标判断，是环境咨询工作的直接技能。

---

## 附：一页总索引

```
微分侧                                    积分侧
W1 三种差分 (中心分母 2Δx)          ←→   W6 积分表 (导数表反读) + 分离变量
W2 一阶原理 → 幂律 → 导数表          ←→   W6 不定(+d) / 定(F(b)−F(a))
W3 拆→求导→合：chain/product/quotient ←→  W8 换元八步 (u = ax+b)
W4 f'=0 找驻点；最优化七步            ←→   W7 受力分析 → 选 ODE 形式 → 配限积分
W5 f'' 判别；稳态 f''=0；Newton 迭代  ←→   W9 辅助方程 / 积分两次；IVP vs BVP
W10 偏导数 → ∇f (标量场 → 向量)

万能模式：dy/dx = ky  ⟹  y = y₀e^{kx}
考场三纪律：写过程 · 不按顺序做 · 做错也做完 (follow-through marks)
```
