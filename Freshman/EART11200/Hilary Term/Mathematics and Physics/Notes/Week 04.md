# Week 4 — 最优化与导数的性质 (Optimisation and Properties of Derivatives)

> 课程：EART11200 The Natural Scientist's Toolkit — Mathematics and Physics
> 对应主手册：Chapter 4 (main(1).md 第 1364–1694 行)
> 授课日期：17/02/2025（校历 Week 23）
> 材料：`Chapter4.md`、`lecture4(1).md`、`EART11200 - 17-Feb-transcript.md`、`Exercises4(1).md`、`Solutions4.md`、`practical4_soln(3).md`

---

## 一、本周主题

### 1. 在课程脉络中的位置

| 周次 | 主题 | 学到什么 |
|---|---|---|
| Week 1 | Calculating Gradients | 梯度＝Δy/Δx，割线→切线 |
| Week 2 | Introduction to Differentiation | 基本求导法则（幂、指数、对数、三角） |
| Week 3 | Differentiating Combinations of Functions | 链式法则、乘积法则、商法则 |
| **Week 4** | **Optimisation & Properties of Derivatives** | **用导数分析函数行为 + 解最优化问题** |
| Week 5 | Second Order Derivatives & Root Finding | 二阶导判别法、Newton–Raphson 求根 |
| Week 6 起 | Integration … | 积分 |

讲师在 transcript 里点明了本周的定位转折：

> "So we've kind of finished on rules of differentiation now. … But now we're gonna actually think about **what do we really need derivatives for**, right?"

前三周是**怎么算导数**（工具制造），本周是**导数拿来干什么**（工具使用）。这是全课第一次把微分真正用在"回答问题"上——地质采矿、气候地球工程、包装设计。

### 2. Intended Learning Outcomes（讲义与 practical 都列了同一份）

1. Describe the **properties of derivatives** in the analysis of functions.（描述导数在函数分析中的性质）
2. Analyse the **behaviour of functions** by applying differentiation in theoretical and real-world applications.
3. **Solve differentiated functions to determine stationary values** in theoretical and real-world applications.
4. **Apply differentiation techniques to optimise functions** in real-world problems.

### 3. 一句话概括本周

> **导数的符号告诉你函数在涨还是在跌；导数为零的地方是函数"转向"的地方；把实际问题写成一个函数再找它的零导数点，就是最优化。**

### 4. 本周不做、下周才做的两件事（讲师反复强调）

- **严格判别**驻点是极大 / 极小 / 鞍点 → 下周用 **second derivative test**（二阶导数）。本周只用"非正式检查"（看图 / 看导数左右符号）。
- 当 $f'(x)=0$ **解不出来**（方程太复杂无法因式分解或配方）时怎么办 → 下周用**数值算法 (root finding)**。本周所有题目都刻意设计成能手解。

---

## 二、核心概念

### 2.1 导数的符号 ↔ 函数的单调性

这是本周的地基。对函数 $f(x)$：

$$
\begin{aligned}
f'(x) > 0 &\;\Longrightarrow\; f(x)\ \text{正在增加 (increasing)}\\
f'(x) < 0 &\;\Longrightarrow\; f(x)\ \text{正在减少 (decreasing)}\\
f'(x) = 0 &\;\Longrightarrow\; f(x)\ \text{很可能在改变方向 (changing direction)}
\end{aligned}
$$

**直觉推理链**（transcript 原话的逻辑）：
> 如果函数在某段是增的（$f'>0$），在另一段是减的（$f'<0$），那么在两段之间**必然存在一个点**使 $f'=0$。因为导数不能从正数直接跳到负数而不经过零。

⚠️ **讲义 Slide 8 有印刷错误**：原文写成
- If $f'(x) > 0$ then $f(x)$ is increasing.
- If $f'(x) > 0$ then $f(x)$ is decreasing. ← **错**

讲师当堂更正："There's a typo there … the second bullet point should be **less than**, not greater than."

### 2.2 驻点 (Stationary point / Stationary value)

**定义**：使 $f'(x)=0$ 的点 $x$，称为**驻点 (stationary point)**；对应的函数值 $f(x)$ 称为**驻值 (stationary value)**。

⚠️ 本课把 "stationary point" 和 "stationary value" 当同义词混用，考试里两个词都可能出现。严格说 point 指 $x$ 坐标，value 指 $f(x)$ 的值。

驻点共有**三种类型**：

| 类型 | 英文 | 左侧 $f'$ | 该点 $f'$ | 右侧 $f'$ | 图形 |
|---|---|---|---|---|---|
| 极大值 | maximum | $>0$ | $=0$ | $<0$ | 先升后降，山顶 ∩ |
| 极小值 | minimum | $<0$ | $=0$ | $>0$ | 先降后升，谷底 ∪ |
| 鞍点 / 拐点式驻点 | saddle point | 同号 | $=0$ | 同号 | 升→平→继续升（或降→平→继续降） |

transcript 原话：
> "If you find that **both the derivatives point in the same direction** around the stationary value, then you have a **saddle point**."

**鞍点很少见但会考**——本周 Question 4.6(b)（采矿"snag"）就是一个鞍点实例。

### 2.3 找驻点的三步法（主手册明确列出）

> **To find a stationary value we:**
> 1. **Differentiate** the function, to find the gradient function $f'(x)$ or $\dfrac{dy}{dx}$.
> 2. **Set the gradient function to zero** and solve for $x$.
> 3. **Substitute $x$ into $f(x)$** to get what the value of the stationary point is.

再加上（strictly should do）：
> 4. **Verify** 驻点类型。

### 2.4 判别驻点类型的两种"非正式"方法（本周唯一允许的方法）

#### 方法 A：函数值检验 (evaluate the function)

在驻点 $x_0$ 两侧各取一点 $x_0-\delta$、$x_0+\delta$，算 $f$ 的值：

- 两侧函数值都**大于** $f(x_0)$ → **极小值**
- 两侧函数值都**小于** $f(x_0)$ → **极大值**

**主手册 Example 4.1 的示范**：$f(x)=\frac{x^2}{2}-5x+2$，驻点 $x=5$，$f(5)=-10.5$。
$$f(4.5)=\frac{4.5^2}{2}-5(4.5)+2=10.125-22.5+2=-10.375$$
$$f(5.5)=\frac{5.5^2}{2}-5(5.5)+2=15.125-27.5+2=-10.375$$
两侧都是 $-10.375 > -10.5$，所以 $x=5$ 是 **minimum**。

#### 方法 B：导数符号检验 (properties of the derivative) ← **更通用，推荐**

在驻点两侧各取一点代入 $f'(x)$，看符号：

**主手册 Example 4.1 的示范**：$f'(x)=x-5$
$$f'(4)=4-5=-1<0 \quad(\text{递减})$$
$$f'(6)=6-5=+1>0 \quad(\text{递增})$$
先降后升 → **minimum** ✓

**为什么方法 B 更好**：算导数值通常比算函数值简单（导数次数更低）；而且能直接读出"增/减"的物理意义；对鞍点也能判（方法 A 判鞍点会失效，因为两侧一高一低）。

#### 符号表 (sign table) 写法（推荐格式，考试排版清晰）

以 $f'(x)=(x-3)(x-5)$ 为例：

| 区间 | $x<3$ | $x=3$ | $3<x<5$ | $x=5$ | $x>5$ |
|---|---|---|---|---|---|
| $f'(x)$ 符号 | $+$ | $0$ | $-$ | $0$ | $+$ |
| $f(x)$ 走势 | ↗ | 极大 | ↘ | 极小 | ↗ |

### 2.5 最优化 (Optimisation)

**定义**（主手册原文）：
> "Optimisation problems involve finding the **best solution**, often the maximum or minimum value(s) of a function **given a set of constraints**."

主手册列举的三大应用领域：

- **Business and Economics**：Maximise profit or minimise cost functions.（最大化利润 / 最小化成本）
- **Physics and Engineering**：Minimise energy or optimise the performance of systems.（最小化能量 / 优化系统性能）
- **Geometry**：Find dimensions that maximise area or volume subject to constraints.（在约束下求最大面积 / 体积的尺寸）

**最优化 = 找驻点 + 约束条件处理**。关键新技能是**把实际问题翻译成单变量函数**。

### 2.6 ⭐ 最优化标准解题流程（本周最重要的可套用模板）

这是本周必须背熟的七步法：

```
Step 0  读题：明确"要最大/最小化什么"（目标 objective）
             明确"受什么限制"（约束 constraint）

Step 1  写目标函数：把要优化的量写成公式
             例：V = lwh，A = 2πr² + 2πrh，P = G − C

Step 2  写约束方程：把限制条件写成等式
             例：2lw + 2wh + 2lh = 10，πr²h = 330×10⁻⁶，x + y = 9

Step 3  消元 → 化成单变量函数
             用约束方程解出一个变量（如 h = …），代回目标函数
             ★ 这一步是最优化题的分水岭，也是最容易出错的地方
             ★ 目标：得到 V(w) 或 A(r) 这样只含一个自变量的函数

Step 4  求导：算 dV/dw（可能用到链式/乘积/商法则）

Step 5  令导数为零，解方程求驻点

Step 6  筛选物理上合理的解
             ★ 长度、半径、天数、质量不能为负 → 丢弃负根
             ★ 检查定义域（如 ln x 要求 x > 0；w² < 5 保证 h > 0）

Step 7  判别类型 + 回代
             用导数符号检验确认是 max 还是 min
             把最优的自变量值代回，求出其他尺寸和目标函数的最优值
             ★ 回答题目真正问的东西（问"体积"就别只答"宽度"）
```

### 2.7 端点 / 边界检验 (boundary check)

主手册本章没有专门讲，但**在有限定义域上必须做**：

若自变量被限制在 $[a,b]$ 上，函数的**全局**最大/最小值可能出现在：
1. 内部驻点（$f'=0$ 处）
2. **端点** $x=a$ 或 $x=b$
3. 不可导点

例：Question 4.3 的盒子，$w$ 的物理定义域是 $0<w<\sqrt5$（$w=\sqrt5$ 时 $h=0$，盒子塌了）。两端 $V\to 0$，中间有唯一驻点 → 该驻点必为最大。这个论证在有约束的几何优化题里可以替代导数符号检验，且更快。

---

## 三、公式与图表

### 3.1 上周法则回顾（讲义前 3 页复习，本周会用到）

| 法则 | 公式 | 本周用在哪 |
|---|---|---|
| Chain rule 链式法则 | $\dfrac{df}{dx}=\dfrac{df}{dg}\times\dfrac{dg}{dx}$ | Q4.6(a) 求 $\frac{d}{dn}\frac{10^5}{n+1}$；Q4.7 求 $\frac{d}{dC}e^{-dC}$ |
| Product rule 乘积法则 | $\dfrac{df}{dx}=u\dfrac{dv}{dx}+v\dfrac{du}{dx}$ | Q4.6(b) 求 $(0.01n^2+1)e^{-0.1n}$ 的导数 |
| Quotient rule 商法则 | $\dfrac{df}{dx}=\dfrac{v\frac{du}{dx}-u\frac{dv}{dx}}{v^2}$ | Q4.6(a) 的另一条路径 |

**基本导数表**（讲义每页都附）：

| $y=f(x)$ | $\dfrac{dy}{dx}$ |
|---|---|
| constant | $0$ |
| $x$ | $1$ |
| $x^n$ | $nx^{n-1}$ |
| $e^x$ | $e^x$ |
| $e^{kx}$ | $ke^{kx}$ |
| $e^{f(x)}$ | $\dfrac{df}{dx}e^{f(x)}$ |
| $\ln(x)$ | $\dfrac{1}{x}$ |
| $\sin(x)$ | $\cos(x)$ |
| $\cos(x)$ | $-\sin(x)$ |

⚠️ 讲义复习页有排版错误：链式法则的 Step 3 写成 "Apply the **product** rule"，应为 "Apply the **chain** rule"。三页复习都复制粘贴了同一句，全是错的。

**上周三个例子的答案**（讲义复习页 + transcript）：
- $f(x)=\sin(3x+1) \Rightarrow f'(x)=3\cos(3x+1)$
- $f(x)=x\exp(3x) \Rightarrow f'(x)=3x\exp(3x)+\exp(3x)=(3x+1)\exp(3x)$
- $f(x)=\dfrac{3x+1}{6x-1} \Rightarrow f'(x)=\dfrac{3(6x-1)-6(3x+1)}{(6x-1)^2}=\dfrac{-9}{(6x-1)^2}$

> 讲师提示：**三条法则的公式会印在考卷上，不用背公式，但必须会用**。而且求导要按固定流程走："split, differentiate, bring together"（拆开 → 分别求导 → 用公式合起来）。

### 3.2 Example 4.1：二次函数（Figure 4.1）

$$f(x)=\frac{x^2}{2}-5x+2, \qquad -5<x<15$$

**求导**：
$$f'(x)=\frac{2x}{2}-5=x-5$$

**令导数为零**：
$$x-5=0 \;\Longrightarrow\; x=5$$

**驻值**：
$$f(5)=\frac{5^2}{2}-5\times 5+2=12.5-25+2=-10.5$$

**判别**：$f'(4)=-1<0$，$f'(6)=+1>0$ → 先降后升 → **minimum**。

**Figure 4.1 图表判读（两栏对照图，本周最重要的图形直觉）**：
- **上栏** $f(x)$ vs $x$：一条开口向上的抛物线，最低点在 $x=5$ 附近（讲义特意说 "note that it is not obvious"——肉眼看不准，必须靠计算）。
- **下栏** $f'(x)=x-5$ vs $x$：一条**直线**，在 $x=5$ 处穿过零。
- **关键对照**：下栏穿零的横坐标 = 上栏的谷底横坐标。下栏在零线**以下**（负）的区间，上栏在**下降**；下栏在零线**以上**（正）的区间，上栏在**上升**。

### 3.3 Example 4.2：三次函数（Figure 4.2）

$$f(x)=\frac{x^3}{3}+2x^2-5x+1, \qquad -10<x<5$$

**求导**：
$$f'(x)=\frac{3x^2}{3}+4x-5=x^2+4x-5$$

**令导数为零**（得到一个二次方程）：
$$x^2+4x-5=0$$

**因式分解**：
$$(x-1)(x+5)=0 \;\Longrightarrow\; x=1 \ \text{或}\ x=-5$$

**符号表**：

| 区间 | $x<-5$ | $x=-5$ | $-5<x<1$ | $x=1$ | $x>1$ |
|---|---|---|---|---|---|
| $f'(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| $f(x)$ | ↗ | **max** | ↘ | **min** | ↗ |

所以 $x=-5$ 是 **maximum**，$x=1$ 是 **minimum**。

⚠️ **主手册正文有错**：Chapter 4 正文和 lecture slide 11 都写 "a minimum occurs (**x = 2**)"，实际由因式分解得到的是 **$x=1$**。手册后文（slide 12、Figure 2 标注）自己又写成 $x=1$，自相矛盾。**以 $x=1$ 为准。**

**Figure 4.2 判读**：上栏是三次曲线（升→降→升），下栏是抛物线形的 $f'(x)$，在 $x=-5$ 和 $x=1$ 两处穿零。$f'$ 在 $(-5,1)$ 内为负，对应上栏那段下坡。

**核心教学点**：三次函数有 **两个**驻点。一般地，$n$ 次多项式的导数是 $n-1$ 次，最多有 $n-1$ 个驻点。函数越复杂，驻点越多，判别越困难——这正是下周引入二阶导判别法的动机。

### 3.4 sin / cos 的驻点对照（讲义 Slide 13，本周最优雅的例子）

已知
$$y=\sin(x) \;\Longrightarrow\; \frac{dy}{dx}=\cos(x)$$

把两条曲线画在一起对照，就能"看见"求导法则的正确性：

| $\cos(x)$ 的状态 | $\sin(x)$ 的行为 |
|---|---|
| $\cos(x)=0$（在 $x=\pi/2,\ 3\pi/2,\dots$） | $\sin(x)$ **驻点**（波峰/波谷） |
| $\cos(x)>0$（在 $0<x<\pi/2$） | $\sin(x)$ **递增** |
| $\cos(x)<0$（在 $\pi/2<x<3\pi/2$） | $\sin(x)$ **递减** |

transcript 里讲师的完整推演：
- $0 \to \pi/2$：$\cos>0$，$\sin$ 上升
- $x=\pi/2$：$\cos=0$，$\sin$ 到达波峰（驻点）
- $\pi/2 \to 3\pi/2$：$\cos<0$，$\sin$ 下降
- $x=3\pi/2$：$\cos=0$，$\sin$ 到达波谷，之后再次上升

> "**They are mimicking each other's behavior.**"（它们在互相模仿对方的行为）

同理可以自己验证 $\frac{d}{dx}\cos(x)=-\sin(x)$：$-\sin$ 为零的地方正是 $\cos$ 的波峰波谷。

### 3.5 Figure 4.3 / 4.4：采矿问题图（Question 4.6）

**Figure 4.3**（三条曲线，纵轴 $\times 10^4$ 英镑，横轴 $n$ = 项目天数 0–100）：
- **实线 Gross profit, $G$**：从 0 快速上升，很快趋于饱和（渐近线 $10^5$）。物理意义：金矿储量有限，越挖越难，回报递减。
- **虚线 Costs, $C$**：一条**直线**，随天数线性增长（每天固定租金/工资）。
- **点划线 Net profit, $P=G-C$**：先陡升，在某处**达到峰值**，然后开始下降并最终变负（约 $n=100$ 处 $P\approx -5\times10^4$）。

**图形要点**：$P$ 的峰值就是我们要找的驻点。峰值左边，多挖一天赚的钱 > 多花的成本；峰值右边，成本超过收益 → 该停工了。

**Figure 4.4**（"snag" 图，单条曲线，纵轴 $\times10^4$，峰值约 $8\times10^4$）：曲线在标注 "Snag" 的位置有一个**平台/水平切线但不改变方向**的特征 → 这就是**鞍点**的图形长相：涨→平→继续涨（或反之）。

### 3.6 Figure 4.5 / 4.6 / 4.7：地球工程问题图（Question 4.7）

- **Figure 4.5**：$E(\Delta T)=500\times\Delta T$，一条过原点的**直线**。横轴 $\Delta T$（0–10 K），纵轴 $E$（0–5000，单位 $10^9$ 美元）。物理意义：全球升温每多 1 K，社会经济损失 5000 亿美元（线性代价模型，参考 Stern Report）。
- **Figure 4.6**：$\Delta T(C)=10\exp(-dC)$，**指数衰减**曲线。横轴 $C$（0–50，$10^9$ 美元），纵轴 $\Delta T$ 从 10 K 衰减。物理意义：花钱做 marine cloud brightening（海洋云增白）能压低升温，但**边际效益递减**——前几十亿最有效，后面越花越没用。
- **Figure 4.7**：$\chi=E+C=5000\exp(-dC)+C$，总成本曲线。图上标注 "we can see there is a minimum in the total cost"——存在一个最优投入。**但注意**：这个"有最小值"只在 $d$ 足够大时成立；题目给的 $d=2\times10^{-4}$ 恰好是临界值（见第五节 Q4.7 详解）。

---

## 四、课堂补充（transcript 独有内容）

### 4.1 课堂管理事项（Practical 形式改革）

讲师当堂做了投票，问 practical 应该怎么组织：
- 选项 1：完全放手，学生自己做，老师只答疑
- 选项 2：答案统一放在课末
- 选项 3：每 10 分钟讲一题（原来的做法）

**投票结果：学生选择"放手 + 课末给答案"**。所以从 Week 5 起：课上先只发题目 slide，学生自己做（可随时问老师），practical 结束时才公布 solutions slide，然后自己按节奏做 handbook 的题。

> 讲师说明改动原因："it's not working the same way as it did last year. You guys seem to want to **jump ahead**."（今年这届学生想往前赶）

另外，Week 5 的 lecture 和 practical 会有**两位教授来听课评估**（讲师的职称评审），可能会随机问学生关于课程和讲师的问题。

### 4.2 讲师的因式分解方法（transcript 详细教学，讲义上没有）

解 $x^2+4x-5=0$ 时，讲师明确说他**不用**求根公式，偏好因式分解，并给出了完整方法：

> **步骤**：
> 1. 写下框架 $(x\ \_\ \_)(x\ \_\ \_)=0$
> 2. 看**常数项**（这里是 $-5$），列出 5 的所有因数对：$1\times5$
> 3. 把因数填进去
> 4. 试组合，看哪种加减能凑出**中间 $x$ 的系数**（这里是 $+4$）：$+5-1=+4$ ✓
> 5. 得 $(x-1)(x+5)=0$

**为什么先看常数项**：展开 $(x+a)(x+b)=x^2+(a+b)x+ab$，常数项 $ab$ 是两数之积，$x$ 的系数 $a+b$ 是两数之和。所以先枚举乘积的因数分解，再筛选和。

**第二个示范**（采矿题）：解 $n^2+2n-99=0$
- 99 的因数对：$1\times99$（$99-1=98$，✗）、$3\times33$（$33-3=30$，✗）、$9\times11$（$11-9=2$ ✓）
- 得 $(n-9)(n+11)=0$

> "There's no real right or wrong answer. I just prefer factorisation." — 求根公式 $x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$ 同样可以，看个人习惯。

### 4.3 讲师的口误与自我更正（听录音会困惑，这里理清）

在讲二次函数导数符号检验时，讲师算 $f'(4)$：
> "so f dashed is equal to four, that's four minus five, and that's equal to one, so that's greater than zero. **No, minus one, sorry. It's less than zero, sorry.**"

**正确的是**：$f'(4)=4-5=-1<0$。讲师第一次说反了，随后自己纠正。

### 4.4 讲师对"为什么学这个"的论述（重要动机段）

> "Maths is useful, I know you probably are bored and hate me for making me do this, but maths is **really, really useful in real world examples**."

> "if you can construct a function and study it to find out where the maximum and minimum are, you can **optimise things**, which kind of plays a real, real **vital role in decision-making**."

**统一模式**（讲师明确点出所有最优化题的共同结构）：
> "they all kind of work in the **same exact way**, where you **build up a function that describes the system**, you **differentiate it**, and **find the stationary values**, because that then tells you something about the process — it tells you where things are maximised and where things are minimised."

### 4.5 讲师提前预告的后续内容

- **下周 (Week 5)**：second order derivative test（二阶导数判别法）——"we'll actually **prove** that those are maximum or minimum"；以及当 $f'(x)=0$ 解不出来时的数值求根算法。
- **学期后段**：differential equations（微分方程）——"you can describe a system of equations by the rate of change, and then you **integrate it back up** at the end."
- **几周后 Dave Topping 的课**：如何用计算机自动求解微分方程，而不是手算。

### 4.6 高维困难的提醒

> "a lot of functions in the **higher dimensions** won't be as nice to visualise, so you **can't just determine** whether they're maximum or minimum points."

意思是：本周靠画图判别是"作弊"，只在一维简单函数上可行。真实科研问题（多变量、多驻点）必须靠代数判别法——这是下周二阶导判别法存在的理由。

### 4.7 采矿问题的完整课堂推演（讲义只有图，文字在 transcript 里）

讲师把讲义版（以百万为单位）写成：
$$G(n)=100-\frac{100}{n+1}, \qquad C(n)=n, \qquad P(n)=G-C=100-\frac{100}{n+1}-n$$

**求导过程（讲师口述的每一步）**：
1. 常数 100 求导 → 0
2. 把 $\dfrac{100}{n+1}$ 改写成 $100(n+1)^{-1}$
3. 用链式法则："bring down the one" → $-100(n+1)^{-2}\times 1$；因为前面本来是负号，所以结果是 $+\dfrac{100}{(n+1)^2}$
4. $-n$ 求导 → $-1$

$$\frac{dP}{dn}=\frac{100}{(n+1)^2}-1$$

**令为零**：
$$\frac{100}{(n+1)^2}=1 \;\Longrightarrow\; (n+1)^2=100 \;\Longrightarrow\; n^2+2n+1=100 \;\Longrightarrow\; n^2+2n-99=0$$
$$(n-9)(n+11)=0 \;\Longrightarrow\; n=9 \ \text{或}\ n=-11$$

**筛选**："we can't really get **negative days**" → 丢弃 $n=-11$。

**结论与商业解读**：
> "we can mine up until **day nine** and we will always see an increase in our net profit. And then after day nine, if we mine to day 10, we actually **start to lose** it. … stop mining **even though there's gold** but because mining that extra gold beyond day nine becomes **too expensive**."

⚠️ 注意：讲师用了捷径 $(n+1)^2=100 \Rightarrow n+1=\pm10$，直接得 $n=9$ 或 $n=-11$，比展开成二次方程更快。展开是为了演示因式分解方法。

---

## 五、Practical 要点

### 5.1 Practical 的目的

Week 4 practical 分两部分：
1. **前半（group exercises，practical4_soln 里的 2 道题）**：一道纯代数驻点题，一道盒子最优化题——建立"翻译 → 消元 → 求导 → 判别"的肌肉记忆。
2. **后半（handbook Exercises 4.1–4.7）**：从纯代数（4.1、4.2）逐步过渡到真实世界问题（4.3–4.7），最后两题（采矿、地球工程）是本课的招牌应用题。

> **题号说明**：以下题号一律以周版文件 `Exercises4(1).md` / `Solutions4.md` / `practical4_soln(3).md` 为准。

---

### 5.2 Practical Group Exercise 1：Stationary values（驻点）

**题目**：求下列函数的驻点，并用导数的性质判别是极大、极小还是鞍点。

（原 slide 上的函数是图片，从解答反推为）
$$f(x)=\frac{x^3}{3}+x^2-15x+c$$

**Solution 1（slide 5–6）**：

**Step 1** 求导：
$$f'(x)=x^2+2x-15$$

**Step 2** 令导数为零并因式分解：
$$x^2+2x-15=0 \;\Longrightarrow\; (x+5)(x-3)=0 \;\Longrightarrow\; x=-5 \ \text{或}\ x=3$$

> 用讲师的因式分解法：15 的因数对 $1\times15$（差 14 ✗）、$3\times5$（$5-3=2$ ✓）→ $(x+5)(x-3)$

**Step 3** 在驻点两侧代入导数：

| 区间 | $x<-5$ | $x=-5$ | $-5<x<3$ | $x=3$ | $x>3$ |
|---|---|---|---|---|---|
| $f'(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| $f(x)$ | ↗ | **maximum** | ↘ | **minimum** | ↗ |

Slide 原文结论：
> "We see that $f(x)$ is **decreasing when $-5<x<3$**, **increasing when $x>3$**. Therefore, $x=-5$ is a **maximum** and $x=3$ is a **minimum**."

（例如取 $x=-6$：$f'=36-12-15=9>0$；取 $x=0$：$f'=-15<0$；取 $x=4$：$f'=16+8-15=9>0$。）

---

### 5.3 Practical Group Exercise 2：Optimisation（盒子体积，与 Q4.3 同题）

**题目**：仓库要做一个长 $l$、宽 $w$、高 $h$ 的盒子，体积
$$V=lwh$$
只有 $10\ \text{m}^2$ 的材料，表面积（封闭盒，六个面）
$$A=2lw+2wh+2lh=10$$
底面是正方形，即 $l=w$。求最大体积。

**Solution 2（slide 8–10）逐步**：

**Step 1** 代入 $l=w$：
$$V=w^2h, \qquad 10=2w^2+2wh+2wh=2w^2+4wh$$

**Step 2** 从约束解出 $h$：
$$4wh=10-2w^2 \;\Longrightarrow\; h=\frac{10-2w^2}{4w}=\frac{5-w^2}{2w}$$

（slide 上明确给出 $h=\dfrac{5-w^2}{2w}$）

**Step 3** 代回体积，化成单变量：
$$V(w)=w^2\cdot\frac{5-w^2}{2w}=\frac{w(5-w^2)}{2}=\frac{5w-w^3}{2}$$

**Step 4** 求导：
$$\frac{dV}{dw}=\frac{5-3w^2}{2}$$

**Step 5** 令为零：
$$5-3w^2=0 \;\Longrightarrow\; w^2=\frac{5}{3} \;\Longrightarrow\; w=\pm\sqrt{\frac{5}{3}}$$

**Step 6** 筛选：宽度不能为负 → $w=\sqrt{5/3}\approx 1.291\ \text{m}$

**Step 7** 回代求 $h$：
$$h=\frac{5-\frac{5}{3}}{2\sqrt{5/3}}=\frac{\frac{10}{3}}{2\sqrt{5/3}}=\frac{5/3}{\sqrt{5/3}}=\sqrt{\frac{5}{3}}$$

**所以 $l=w=h=\sqrt{5/3}$——最优盒子是一个正方体 (cube)！**

**最大体积**：
$$V=\frac{1}{2}\left(5\sqrt{\tfrac{5}{3}}-\left(\sqrt{\tfrac{5}{3}}\right)^3\right)=\left(\sqrt{\tfrac{5}{3}}\right)^3\approx 2.15\ \text{m}^3$$

**⭐ 值得记住的几何结论**：在**给定表面积**下，**封闭长方体**中体积最大的是**正方体**。（更一般地，给定表面积体积最大的立体是球——这是等周问题 isoperimetric problem 的三维版本。）

**判别（slide 未做，应补）**：$\frac{dV}{dw}=\frac{5-3w^2}{2}$，取 $w=1$ 得 $+1>0$；取 $w=1.5$ 得 $\frac{5-6.75}{2}<0$。先升后降 → **maximum** ✓

---

### 5.4 Handbook Question 4.1：求驻点并判别类型

**(a)** $f(x)=x^2+x$
$$f'(x)=2x+1=0 \;\Longrightarrow\; \boxed{x=-\tfrac12}$$
判别：$f'(-1)=-1<0$，$f'(0)=+1>0$ → 先降后升 → **minimum**。
（驻值 $f(-\frac12)=\frac14-\frac12=-\frac14$）

**(b)** $f(x)=2x-x^2$
$$f'(x)=2-2x=0 \;\Longrightarrow\; \boxed{x=1}$$
判别：$f'(0)=+2>0$，$f'(2)=-2<0$ → 先升后降 → **maximum**。
（驻值 $f(1)=2-1=1$）
⚠️ Solutions 文件在 (b) 处**漏写了结论**（只写到 $2-2x=0$ 就断了），必须自己补完：$x=1$，maximum。

**(c)** $f(x)=(x-2)^2$
用链式法则：
$$f'(x)=2(x-2)=0 \;\Longrightarrow\; \boxed{x=2}$$
判别：$f'(1)=-2<0$，$f'(3)=+2>0$ → **minimum**（驻值 $f(2)=0$）。
（也可展开成 $x^2-4x+4$ 再求导，结果相同）

**(d)** $f(x)=(x-2)(3-x)$
用乘积法则：
$$f'(x)=1\cdot(3-x)+(x-2)\cdot(-1)=(3-x)-(x-2)=5-2x$$
$$5-2x=0 \;\Longrightarrow\; \boxed{x=2.5}$$
判别：$f'(2)=+1>0$，$f'(3)=-1<0$ → **maximum**（驻值 $f(2.5)=0.5\times0.5=0.25$）。
💡 也可以展开：$f=-x^2+5x-6$，开口向下的抛物线，显然有 maximum。

**(e)** $f(x)=\dfrac{x^3}{3}-4x^2+15x+5$
$$f'(x)=x^2-8x+15=(x-3)(x-5)=0 \;\Longrightarrow\; \boxed{x=3 \ \text{和}\ x=5}$$
判别（符号表）：

| 区间 | $x<3$ | $x=3$ | $3<x<5$ | $x=5$ | $x>5$ |
|---|---|---|---|---|---|
| $f'$ | $+$（如 $f'(0)=15$） | $0$ | $-$（如 $f'(4)=-1$） | $0$ | $+$（如 $f'(6)=3$） |
| $f$ | ↗ | **max** | ↘ | **min** | ↗ |

$x=3$ 是 **maximum**，$x=5$ 是 **minimum**（与 Solutions 一致："a maximum and a minimum respectively"）。

**(f)** $f(x)=\ln(x)-x$
$$f'(x)=\frac{1}{x}-1=0 \;\Longrightarrow\; \frac1x=1 \;\Longrightarrow\; \boxed{x=1}$$
判别：$f'(0.5)=2-1=+1>0$，$f'(2)=0.5-1=-0.5<0$ → **maximum**（驻值 $f(1)=\ln 1-1=-1$）。
⚠️ **定义域陷阱**：$\ln x$ 要求 $x>0$，所以只在 $x>0$ 上讨论；判别时取的检验点也必须 $>0$（不能取 $x=-1$）。

---

### 5.5 Handbook Question 4.2：和为 9 的两数，一数乘另一数的平方最大

**题目**：求两个非负数，和为 9，使得**其中一个数** × **另一个数的平方**最大。

**Step 1** 建立方程（题目已给提示）：
- 约束：$x+y=9$
- 目标：最大化 $P=x\,y^2$

**Step 2** 消元：$x=9-y$
$$P(y)=(9-y)y^2=9y^2-y^3$$

**Step 3** 求导：
$$\frac{dP}{dy}=18y-3y^2$$

**Step 4** 令为零并因式分解：
$$18y-3y^2=0 \;\Longrightarrow\; 3y(6-y)=0 \;\Longrightarrow\; y=0 \ \text{或}\ y=6$$

**Step 5** 判别：
- $y=0$：$P'(-1)$ 不在定义域内（要求非负），用 $y$ 略大于 0 如 $y=1$：$P'=18-3=15>0$；$y=0$ 处 $P=0$。在非负定义域上 $y=0$ 是**边界极小 (minimum)**。
- $y=6$：$P'(5)=90-75=+15>0$，$P'(7)=126-147=-21<0$ → 先升后降 → **maximum** ✓

**Step 6** 回代：
$$y=6 \;\Longrightarrow\; x=9-6=3$$
$$P_{\max}=3\times 6^2=3\times 36=\boxed{108}$$

💡 **注意"哪个数被平方"**：题目说"一个数 × 另一个数的**平方**"，被平方的那个数是 $y=6$（较大者），不被平方的是 $x=3$。如果搞反了（$6\times3^2=54$）就少了一半。

---

### 5.6 Handbook Question 4.3：Amazon 的封闭盒子（10 m² 材料）

与 Practical Exercise 2 **完全相同**（只是把"仓库"换成 Amazon）。答案：

$$V(w)=\frac{5w-w^3}{2}, \quad \frac{dV}{dw}=\frac{5-3w^2}{2}=0 \;\Longrightarrow\; w=\sqrt{\frac53}\approx 1.29\ \text{m}$$
$$l=w=h=\sqrt{5/3} \quad(\text{cube}), \qquad V_{\max}=\left(\sqrt{5/3}\right)^3\approx \boxed{2.15\ \text{m}^3}$$

Solutions 文件原话："so the optimum box is a **cube**."

---

### 5.7 Handbook Question 4.4：开口盒子（48 m² 材料）

**题目**：做一个**开口 (open)** 的长方体盒子，底为正方形，用 $48\ \text{m}^2$ 材料。什么尺寸体积最大？

**关键差异**：开口 → **少一个正方形顶面**。Solutions 明确提示："Note that we're **leaving one square side off** the constraint."

**Step 1** 设底边 $l=w$，高 $h$：
- 目标：$V=w^2h$
- 约束：底面 $w^2$ + 四个侧面 $4wh$ = 48
$$w^2+4wh=48$$

**Step 2** 解出 $h$：
$$h=\frac{48-w^2}{4w}$$

**Step 3** 代回：
$$V(w)=w^2\cdot\frac{48-w^2}{4w}=\frac{w(48-w^2)}{4}=\frac{48w-w^3}{4}=12w-\frac{w^3}{4}$$

**Step 4** 求导：
$$\frac{dV}{dw}=12-\frac{3w^2}{4}=\frac{48-3w^2}{4}$$

**Step 5** 令为零：
$$48-3w^2=0 \;\Longrightarrow\; w^2=16 \;\Longrightarrow\; w=\pm4$$

**Step 6** 筛选：宽度非负 → $\boxed{w=4\ \text{m}}$

**Step 7** 回代：
$$h=\frac{48-16}{4\times4}=\frac{32}{16}=2\ \text{m}$$
$$V_{\max}=4^2\times 2=\boxed{32\ \text{m}^3}$$

**判别**：$\frac{dV}{dw}(3)=\frac{48-27}{4}>0$；$\frac{dV}{dw}(5)=\frac{48-75}{4}<0$ → **maximum** ✓

**⭐ 值得注意的几何结论**：开口盒子的最优解**不是正方体**，而是 $h=\frac{w}{2}$（高是底边的一半）。因为少了顶面，"长高"的代价变小了？不——恰恰相反：少了顶面后，加大底面积的代价变小，所以最优解变得**更矮更宽**。**这是本题与 Q4.3 对比的最大教学价值：约束条件一改，最优形状就变了，不能背结论。**

---

### 5.8 Handbook Question 4.5：可乐罐（330 ml，用铝最少）⭐

**题目**：圆柱形铝制可乐罐盛 330 ml 液体。可口可乐想知道用铝最少的尺寸。

**公式**：
$$V=\pi r^2 h \quad(\text{体积}), \qquad A=2\pi r^2+2\pi r h \quad(\text{表面积：两个圆底} + \text{侧面})$$

**单位换算**：$330\ \text{ml}=330\ \text{cm}^3=330\times10^{-6}\ \text{m}^3=3.3\times10^{-4}\ \text{m}^3$

#### (a) 数值表格法（"先感受，再证明"）

**思路**：体积固定，所以给定 $r$ 就能算出 $h$，进而算出 $A$：
$$h=\frac{V}{\pi r^2}, \qquad A=2\pi r^2+2\pi r h = 2\pi r^2+\frac{2V}{r}$$

（后一个化简很有用：$2\pi r h = 2\pi r \cdot \frac{V}{\pi r^2}=\frac{2V}{r}$）

**验算示范**（$r=0.010$ m，题目已给）：
$$h=\frac{3.3\times10^{-4}}{\pi(0.01)^2}=\frac{3.3\times10^{-4}}{3.1416\times10^{-4}}=1.050\ \text{m}$$
$$A=2\pi(0.01)^2+\frac{2\times3.3\times10^{-4}}{0.01}=6.28\times10^{-4}+0.0660=0.0666\approx 0.067\ \text{m}^2$$

**完整表格（Solutions 给出）**：

| Radius $r$ (m) | Height $h$ (m) | Surface area $A$ (m²) |
|---|---|---|
| 0.010 | 1.050 | 0.067 |
| 0.020 | 0.263 | 0.036 |
| 0.030 | 0.117 | 0.028 |
| **0.040** | **0.066** | **0.027** ← 最小 |
| 0.050 | 0.042 | 0.029 |
| 0.060 | 0.029 | 0.034 |
| 0.070 | 0.021 | 0.040 |

**(a) 答案**：$r=0.04\ \text{m}$ 附近表面积最小（$A\approx0.027\ \text{m}^2$）。

**表格的物理直觉**：$A=\underbrace{2\pi r^2}_{\text{顶底，随 }r\text{ 增大}}+\underbrace{2V/r}_{\text{侧面，随 }r\text{ 减小}}$。两项此消彼长 → 中间必有最小值。$r$ 太小 → 罐子又细又高，侧面积巨大；$r$ 太大 → 罐子又扁又宽，顶底面积巨大。

#### (b) 微分法（精确解）

**Step 1** 从体积约束解出 $h$：
$$h=\frac{V}{\pi r^2}$$

**Step 2** 代入表面积，化成单变量：
$$A(r)=2\pi r^2+2\pi r\cdot\frac{V}{\pi r^2}=2\pi r^2+\frac{2V}{r}=2\pi r^2+2Vr^{-1}$$

**Step 3** 求导：
$$\frac{dA}{dr}=4\pi r-\frac{2V}{r^2}$$

**Step 4** 令为零：
$$4\pi r=\frac{2V}{r^2} \;\Longrightarrow\; 4\pi r^3=2V \;\Longrightarrow\; r^3=\frac{V}{2\pi} \;\Longrightarrow\; \boxed{r=\sqrt[3]{\frac{V}{2\pi}}}$$

**Step 5** 代入数值：
$$r=\sqrt[3]{\frac{3.3\times10^{-4}}{2\pi}}=\sqrt[3]{5.252\times10^{-5}}\approx 0.0375\ \text{m}\ (=3.75\ \text{cm})$$

**Step 6** 求 $h$：
$$h=\frac{V}{\pi r^2}=\frac{3.3\times10^{-4}}{\pi(0.0375)^2}\approx 0.0749\ \text{m}\ (=7.49\ \text{cm})$$

**⭐ 优美结论**：$h=2r$，即**最省材料的罐子，高度恰好等于直径**（正方形侧影）。
**证明**：由 $V=2\pi r^3$ 代入 $h=\frac{V}{\pi r^2}=\frac{2\pi r^3}{\pi r^2}=2r$ ✓

**最小表面积**：
$$A_{\min}=2\pi r^2+\frac{2V}{r}=2\pi r^2+\frac{2(2\pi r^3)}{r}=2\pi r^2+4\pi r^2=6\pi r^2\approx 0.0264\ \text{m}^2$$

**判别**：$\frac{dA}{dr}(0.03)=4\pi(0.03)-\frac{2(3.3\times10^{-4})}{0.0009}=0.377-0.733<0$；$\frac{dA}{dr}(0.05)=0.628-0.264>0$ → 先降后升 → **minimum** ✓

💡 **现实对照（值得思考的地球科学/工程点）**：真实的 330 ml 可乐罐半径约 3.3 cm、高约 11.5 cm，**不是**数学最优解。原因：厚度不均（顶盖更厚更贵）、握持手感、货架陈列、印刷面积、生产线兼容性。**数学模型给出的最优解只在模型假设范围内最优**——这正是"自然科学家的工具箱"想教的批判性态度。

---

### 5.9 Handbook Question 4.6：金矿开采最优化 ⭐⭐（本周旗舰应用题）

#### (a) 最优开采天数

**设定**（handbook 版本，单位为英镑；讲义版本除以 $10^3$）：
$$G(n)=10^5-\frac{10^5}{n+1} \quad (\text{采到的黄金价值，gross profit})$$
$$C(n)=10^3 n \quad (\text{设备租金等成本，随天数线性增长})$$
$$P(n)=G(n)-C(n)=10^5-\frac{10^5}{n+1}-10^3 n \quad(\text{净利润})$$

**物理意义**：
- $G$ 随 $n$ 增大但趋于饱和上限 $10^5$——金脉储量有限，"It becomes **more difficult to mine** the gold as time goes on"（回报递减 diminishing returns）。
- $C$ 线性增长——每天固定成本，不停就一直烧钱。

**Step 1** 求 $\dfrac{dP}{dn}$。

对 $\dfrac{10^5}{n+1}$ 用**链式法则**（Solutions 的做法）：
- 令 $u=n+1$，则 $f=10^5 u^{-1}$
- $\dfrac{df}{du}=-10^5 u^{-2}$，$\dfrac{du}{dn}=1$
- $\dfrac{df}{dn}=-\dfrac{10^5}{(n+1)^2}$

因为 $P$ 中该项前面是**负号**，所以贡献为 $+\dfrac{10^5}{(n+1)^2}$：

$$\frac{dP}{dn}=0+\frac{10^5}{(n+1)^2}-10^3$$

> **另一条路（题目提示可用商法则）**：对 $\frac{10^5}{n+1}$ 用商法则，$u=10^5$（$u'=0$），$v=n+1$（$v'=1$）：
> $$\frac{d}{dn}\frac{u}{v}=\frac{v u'-u v'}{v^2}=\frac{(n+1)\cdot 0-10^5\cdot 1}{(n+1)^2}=-\frac{10^5}{(n+1)^2}$$ 结果相同。

**Step 2** 令为零：
$$\frac{10^5}{(n+1)^2}=10^3 \;\Longrightarrow\; (n+1)^2=\frac{10^5}{10^3}=100$$

**Step 3** 解二次方程（两种走法）：

*快捷法*：$(n+1)^2=100 \Rightarrow n+1=\pm10 \Rightarrow n=9$ 或 $n=-11$

*展开法*（讲师课上的演示，为了练因式分解）：
$$n^2+2n+1=100 \;\Longrightarrow\; n^2+2n-99=0 \;\Longrightarrow\; (n-9)(n+11)=0$$

**Step 4** 筛选：天数不能为负 → 舍去 $n=-11$，取 $\boxed{n=9\ \text{天}}$

**Step 5** 判别（是 maximum）：
$$\frac{dP}{dn}(8)=\frac{10^5}{81}-10^3=1234-1000=+234>0 \quad(\text{还在赚})$$
$$\frac{dP}{dn}(10)=\frac{10^5}{121}-10^3=826-1000=-174<0 \quad(\text{开始亏})$$
先升后降 → **maximum** ✓（与 Figure 4.3 的净利润峰值一致）

**Step 6** 回代求最大利润：
$$P(9)=10^5-\frac{10^5}{10}-10^3\times 9=100000-10000-9000=81{,}000$$

Solutions 文件给的是 "$P=80{,}000$ profit after 9 days"（取整/近似）。**考试建议**：按题目实际给的系数算，写出完整数值并说明单位。

**商业解读（transcript 的原话精神）**：
> 第 9 天之后就该停工。虽然**地下还有金子**，但从第 10 天起，多挖一天的边际收益已经小于边际成本，继续挖只会**吃掉已赚的利润**。

📌 **经济学直觉**：$\frac{dP}{dn}=0$ ⟺ $\frac{dG}{dn}=\frac{dC}{dn}$ ⟺ **边际收益 = 边际成本 (marginal revenue = marginal cost)**。这是微观经济学最基本的最优化条件，本题就是它的微积分证明。

#### (b) 找出"snag"（工程事故日）——鞍点实例 ⭐

**题目**：项目中出现一个 "snag"（卡壳/事故），使得**某一天完全没有利润**（见 Figure 4.4），之后恢复并加速。描述采金量的函数为
$$G(n)=A+\left(0.01n^2+1\right)\exp(-0.1n)$$
（$A$ 为常数项）。用**乘积法则**找出 snag 发生在第几天。

**核心思想**：snag 那一天"没有利润" = 采金量曲线**瞬间水平** = $\dfrac{dG}{dn}=0$ 但**不改变方向** → **鞍点 (saddle point)**。

**Step 1** 常数 $A$ 求导为 0，只需处理乘积项。拆分：
$$u=0.01n^2+1 \;\Longrightarrow\; \frac{du}{dn}=0.02n$$
$$v=\exp(-0.1n) \;\Longrightarrow\; \frac{dv}{dn}=-0.1\exp(-0.1n) \quad(\text{链式法则：}e^{kn}\to ke^{kn})$$

**Step 2** 应用乘积法则 $\dfrac{dG}{dn}=u\dfrac{dv}{dn}+v\dfrac{du}{dn}$：
$$\frac{dG}{dn}=(0.01n^2+1)\bigl(-0.1e^{-0.1n}\bigr)+e^{-0.1n}(0.02n)$$

**Step 3** 提取公因子 $e^{-0.1n}$：
$$\frac{dG}{dn}=e^{-0.1n}\Bigl[-0.1(0.01n^2+1)+0.02n\Bigr]=e^{-0.1n}\bigl[-0.001n^2+0.02n-0.1\bigr]$$

**Step 4** 令为零。因为 $e^{-0.1n}>0$ **恒成立、永不为零**，只需中括号为零：
$$-0.001n^2+0.02n-0.1=0$$
两边乘以 $-1000$：
$$n^2-20n+100=0$$

**Step 5** 因式分解（完全平方！）：
$$(n-10)^2=0 \;\Longrightarrow\; \boxed{n=10}$$

**Step 6** 判别：**重根 (repeated root)** 意味着导数在该点"碰到零就弹回"，两侧同号：
$$\frac{dG}{dn}(9)=e^{-0.9}\bigl[-0.081+0.18-0.1\bigr]=e^{-0.9}(-0.001)<0$$
$$\frac{dG}{dn}(11)=e^{-1.1}\bigl[-0.121+0.22-0.1\bigr]=e^{-1.1}(-0.001)<0$$
两侧**都是负的** → 不是极大也不是极小 → **saddle point** ✓
（Solutions 原话："This is an example of a **saddle point**."）

**Step 7** 结论：**snag 发生在第 10 天**。曲线在此处短暂"停住"（当天净增量为零），随后继续原来的趋势。

⭐ **本题的三个关键技巧（考试高频）**：
1. **提公因子 $e^{kn}$**：指数永远为正，可以直接约掉，把超越方程变成多项式方程。
2. **重根 ⟹ 鞍点**：如果 $f'(x)=0$ 的解是完全平方式的重根，几乎必然是鞍点。这是最快的鞍点识别信号。
3. **常数项求导为零**：$G$ 里的常数 $A$ 完全不影响驻点位置——最优化只关心函数的"形状"，不关心整体平移。

---

### 5.10 Handbook Question 4.7：地球工程 (Geoengineering) ⭐⭐（本周最有思想性的题）

#### 背景与建模

**方程 4.1**（经济学家，参考 Stern Report）——全球升温 $\Delta T$ 对社会造成的经济损失 $E$（单位：十亿美元）：
$$E(\Delta T)=500\times\Delta T \tag{4.1}$$
即每升温 1 K，社会损失 5000 亿美元（线性代价模型）。

**方程 4.2**（气候科学家）——花钱 $C$（十亿美元）做 **marine cloud brightening（海洋云增白）** 可以压低升温：
$$\Delta T(C)=10\exp(-dC) \tag{4.2}$$
其中 $d$ 是**有不确定性**的常数。$C=0$ 时 $\Delta T=10$ K（不干预的基准升温）；花钱越多升温越低，但**指数衰减 = 边际效益递减**。

> **物理背景**：Marine cloud brightening 是通过向海洋低层云喷洒海盐气溶胶、增加云滴数浓度、提高云反照率 (albedo)，从而反射更多太阳辐射来抵消 CO₂ 造成的暖化。$d$ 的不确定性来自气溶胶–云相互作用（aerosol–cloud interaction），是 IPCC 报告中不确定性最大的辐射强迫项之一。

#### 建立总成本函数

**Step 1** 把 (4.1) 反解：$\Delta T=\dfrac{E}{500}$，也就是说 $E=500\,\Delta T$。

**Step 2** 把 (4.2) 代入 (4.1)：
$$E(C)=500\times 10\exp(-dC)=5000\exp(-dC)$$

**Step 3** 加上**方案本身的开销** $C$，得到**总成本 (total cost)**：
$$\chi(C)=E+C=5000\exp(-dC)+C \tag{4.3}$$

（手册在此处符号混乱：正文写 $T=E+C$，Figure 4.7 与 Solutions 写 $\chi$。用 $\chi$ 避免和温度 $T$ 混淆。）

**逻辑要点**：不能只看"花钱能降温"就上马——必须把**方案费用**和**残余气候损失**加在一起看**总账**。这是政策分析的核心思维（cost–benefit analysis）。

#### 优化

**Step 4** 求导（对指数项用链式法则：$\frac{d}{dC}e^{-dC}=-d\,e^{-dC}$）：
$$\frac{d\chi}{dC}=5000\times(-d)\exp(-dC)+1=-5000d\exp(-dC)+1$$

**Step 5** 令为零：
$$5000d\exp(-dC)=1 \;\Longrightarrow\; \exp(-dC)=\frac{1}{5000d}$$

取自然对数：
$$-dC=\ln\!\left(\frac{1}{5000d}\right)=-\ln(5000d) \;\Longrightarrow\; \boxed{C^\ast=\frac{\ln(5000d)}{d}}$$

**Step 6** 代入 $d=2\times10^{-4}$：
$$5000d=5000\times 2\times10^{-4}=1$$
$$C^\ast=\frac{\ln(1)}{2\times10^{-4}}=\frac{0}{2\times10^{-4}}=\boxed{0}$$

#### 结果解读（题目真正要考的地方）

**数学结论**：最优投入是 **$C=0$**——**一分钱都不该花在这个地球工程方案上**。

**为什么？** 检查导数符号：当 $d=2\times10^{-4}$ 时
$$\frac{d\chi}{dC}=-5000\times 2\times10^{-4}e^{-dC}+1=1-e^{-dC}$$
对任意 $C>0$，$e^{-dC}<1$，所以 $\dfrac{d\chi}{dC}>0$ ——**总成本在整个可行域上单调递增**。驻点在边界 $C=0$，是**最小值**。

**给决策者的建议 (advice to policy makers)**：
> 在 $d=2\times10^{-4}$ 这个效率参数下，方案**每花一美元所减少的气候损失不足一美元**，社会总成本反而上升。**这个方案不应实施 (It should not go ahead)。**

Solutions 原话是 "therefore this means that we can only **increase** the temperature by implementing the scheme! It should not go ahead."（措辞上手册说"只会升温"，更严谨的说法是"只会**增加总成本**"。）

#### ⭐ 深化：$d$ 的敏感性分析（考试可能追问）

通解 $C^\ast=\dfrac{\ln(5000d)}{d}$ 只有在 $\ln(5000d)>0$ 即 $5000d>1$ 即
$$d>2\times10^{-4}$$
时才给出**正的**最优投入。

- $d<2\times10^{-4}$（技术效率低）→ $C^\ast<0$，无物理意义 → **不该做**
- $d=2\times10^{-4}$（临界值）→ $C^\ast=0$ → **恰好不值得做**
- $d>2\times10^{-4}$（技术效率高）→ $C^\ast>0$ → **值得投入，且有一个明确的最优金额**

**这就是 Figure 4.7 里"总成本存在极小值"的情形对应的 $d$ 取值。** 题目故意把 $d$ 设在临界点上，是为了让学生体会：**结论对不确定参数极度敏感**。$d$ 的不确定性直接决定了"做还是不做"这个二元政策判断——这是气候政策研究的真实困境。

---

## 六、易错点 / 重点难点

### A. 概念类

1. **$f'(x)=0$ 是驻点的必要条件，不是充分条件**。$f'(x_0)=0$ 只说明"可能转向"，不保证是极值——可能是鞍点。主手册用词很谨慎："it is **likely** the function will be changing direction"。

2. **"stationary point" ≠ "maximum/minimum"**。驻点是大类，极大、极小、鞍点是三个子类。答题时不能只写"找到驻点 $x=3$"就完事，必须判别类型。

3. **不是所有极值都在 $f'=0$ 处**。定义域端点（boundary）和不可导点也可能是极值。Q4.2 的 $y=0$ 就是边界点。

4. **局部 vs 全局**：本周找的都是 local maximum / local minimum。全局最值需要额外比较所有驻点值和端点值。

5. **鞍点的判据是"两侧导数同号"**，不是"函数值相等"。用函数值检验法（方法 A）判鞍点会失效。

6. **常数项不影响驻点位置**。$f(x)$ 和 $f(x)+100$ 的驻点完全相同（Q4.6(b) 里的常数项 $A$ 就是这个道理）。

### B. 计算类

7. **符号错误（最高频）**：$\dfrac{d}{dn}\left(-\dfrac{100}{n+1}\right)=+\dfrac{100}{(n+1)^2}$。负负得正，很多人只写了 $-\frac{100}{(n+1)^2}$。链式法则求 $u^{-1}$ 的导数已经带一个负号，再和原来的负号相乘。

8. **讲师本人当堂算错过 $f'(4)$**：$4-5=-1$ 不是 $+1$。检验驻点时**逐位算，不要心算**。

9. **指数因子不能给出解**：$e^{kn}=0$ **永远无解**。看到 $e^{-0.1n}[\cdots]=0$，直接约掉指数、只解中括号。（Q4.6(b)）

10. **因式分解要验算**：$(x-1)(x+5)=x^2+4x-5$ ✓；$(x+1)(x-5)=x^2-4x-5$ ✗。展开检验中间项符号。

11. **$(n+1)^2=100$ 有两个解**：$n+1=+10$ 和 $n+1=-10$。开平方**不要漏负根**（虽然后面会被物理条件筛掉，但漏了会被扣过程分）。

12. **重根的写法**：$n^2-20n+100=(n-10)^2$，只有**一个**驻点 $n=10$（不是两个）。

### C. 建模类（最优化专属）

13. **⭐ 忘记消元就求导**：$V=w^2h$ 有两个变量，**不能直接对 $w$ 求导**（$h$ 也依赖 $w$）。必须先用约束消掉一个变量，得到 $V(w)$ 才能求导。这是最优化题最致命的错误。

14. **⭐ 约束方程写错——封闭 vs 开口**：
    - 封闭长方体（Q4.3）：$A=2lw+2wh+2lh$（六面）
    - 开口方底盒（Q4.4）：$A=w^2+4wh$（一个底 + 四个侧）
    - 注意开口盒的底面**只有一个** $w^2$，不是 $2w^2$。
    审题时先画图，数清楚有几个面。

15. **单位换算**：330 ml $=330\ \text{cm}^3=330\times10^{-6}\ \text{m}^3$（**不是** $330\times10^{-3}$）。因为 $1\ \text{m}^3=10^6\ \text{cm}^3$。如果用 $10^{-3}$ 会导致 $r$ 差 10 倍。

16. **丢弃非物理解**：长度、半径、天数、质量、浓度**不能为负**。Q4.3 的 $w=-\sqrt{5/3}$、Q4.6 的 $n=-11$、Q4.4 的 $w=-4$ 都必须显式说明"discard because we cannot have negative width / days"。**写出这句话是有分的。**

17. **定义域限制**：
    - $\ln x$ 要求 $x>0$（Q4.1(f)）
    - Q4.3 要求 $h>0$ ⟹ $w^2<5$ ⟹ $0<w<\sqrt5$
    - Q4.5 要求 $r>0$

18. **⭐ 回答题目真正问的东西**：
    - Q4.3 问"最大**体积**"，不是最优宽度 → 必须算出 $V\approx2.15\ \text{m}^3$
    - Q4.4 问"什么**尺寸 (dimensions)**" → 要给 $w=4$ **和** $h=2$
    - Q4.5 问"罐子的**尺寸**" → 要给 $r$ **和** $h$
    - Q4.2 问"两个**数**" → 要给 $x=3, y=6$，还要给乘积 108
    - Q4.7 问"**对决策者的建议**" → 不能只写 $C=0$，要写"方案不应实施"

19. **Q4.2 谁被平方**：$x y^2$ 中 $y$ 是被平方的那个。搞反得 54 而非 108。

### D. 材料本身的错误（errata，复习时别被带偏）

20. **Slide 8 打字错误**：第二条 bullet "If $f'(x)>0$ then $f(x)$ is decreasing" 应为 $f'(x)<0$。（讲师当堂更正）

21. **主手册 / Slide 11 打字错误**：Example 4.2 说 "a minimum occurs (**x = 2**)"，实际是 **$x=1$**。同一份材料后文又写 $x=1$，自相矛盾。

22. **讲义复习页错误**：链式法则和商法则的 Step 3 都写成 "Apply the **product** rule"（复制粘贴遗留），应分别是 chain rule / quotient rule。

23. **Solutions4.md 的 Q4.1(b) 缺结论**：只写到 $2-2x=0$，答案 $x=1$ 是 **maximum**，需自己补。

24. **Q4.6 数值不自洽**：按 $G=10^5-\frac{10^5}{n+1}$、$C=10^3 n$ 算，$P(9)=81{,}000$；Solutions 写 $80{,}000$。以自己的计算为准并写清代入过程。

25. **公式全是图片**：主手册和讲义的 md 转写把大量公式丢失了。需要精确公式时，优先看 `practical4_soln(3).md`（保留了 $h=\frac{5-w^2}{2w}$ 等关键式子）和本笔记的重建版本。

### E. 应试技巧

26. **三大法则的公式印在考卷上**，不用背，但必须熟练应用。求导流程固定：**split → differentiate → bring together**。

27. **判别驻点优先用导数符号法（方法 B）**：计算量小，且能识别鞍点。写答案时把检验点的数值算出来（如 "$f'(4)=-1<0$"），不要只写"经检验为极小"。

28. **画符号表**是最清晰的答题格式，尤其多驻点时。

29. **本周只用非正式判别**（图形 / 导数符号）。**下周才有二阶导判别法**——考 Week 4 内容时若写二阶导也对，但要确保理解本周的方法（考试可能明确要求 "using the properties of the derivative"）。

---

## 七、本周术语表

| 英文 | 中文 | 说明 |
|---|---|---|
| derivative | 导数 | $f'(x)$ 或 $\frac{dy}{dx}$，函数在某点的变化率 / 切线斜率 |
| gradient function | 梯度函数 | 即导函数 $f'(x)$，本课常用此说法 |
| rate of change | 变化率 | 导数的物理含义 |
| increasing | 递增 | $f'(x)>0$ |
| decreasing | 递减 | $f'(x)<0$ |
| stationary point | 驻点 | 使 $f'(x)=0$ 的点 $x$ |
| stationary value | 驻值 | 驻点处的函数值（本课常与 stationary point 混用） |
| turning point | 转折点 / 拐折点 | 函数改变增减方向的点（极大或极小） |
| maximum (pl. maxima) | 极大值 | $f'$ 由正变负 |
| minimum (pl. minima) | 极小值 | $f'$ 由负变正 |
| saddle point | 鞍点 | $f'=0$ 但两侧同号，函数不转向 |
| point of inflection | 拐点 | 凹凸性改变的点（下周正式引入） |
| second order derivative | 二阶导数 | $f''(x)$，下周用于严格判别驻点类型 |
| optimisation | 最优化 | 在约束下求函数的最大/最小值 |
| optimise | 优化 | 找到"最好"的解 |
| constraint | 约束条件 | 限制变量的等式或不等式 |
| objective function | 目标函数 | 要被最大化/最小化的那个函数 |
| maximise / minimise | 最大化 / 最小化 | |
| chain rule | 链式法则 | $\frac{df}{dx}=\frac{df}{dg}\cdot\frac{dg}{dx}$ |
| product rule | 乘积法则 | $\frac{d(uv)}{dx}=u\frac{dv}{dx}+v\frac{du}{dx}$ |
| quotient rule | 商法则 | $\frac{d}{dx}\frac uv=\frac{v u'-u v'}{v^2}$ |
| factorisation | 因式分解 | 解方程的手段之一 |
| quadratic formula | 求根公式 | $x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$ |
| repeated root | 重根 | 如 $(n-10)^2=0$，通常对应鞍点 |
| quadratic function | 二次函数 | |
| cubic function | 三次函数 | |
| root finding | 求根 | 数值求解 $f(x)=0$（下周内容） |
| surface area | 表面积 | $A$ |
| volume | 体积 | $V$ |
| cylinder | 圆柱 | $V=\pi r^2h$，$A=2\pi r^2+2\pi rh$ |
| cube | 正方体 | Q4.3 的最优解 |
| open box | 开口盒 | 无顶盖，约束式少一个面（Q4.4） |
| square base | 方形底 | $l=w$ |
| radius / height | 半径 / 高 | $r$ / $h$ |
| gross profit | 毛利 | $G$ |
| costs | 成本 | $C$ |
| net profit | 净利 | $P=G-C$ |
| marginal revenue / cost | 边际收益 / 边际成本 | $\frac{dG}{dn}$ / $\frac{dC}{dn}$，最优处两者相等 |
| diminishing returns | 报酬递减 | 金矿题中 $G$ 趋于饱和的原因 |
| gold seam | 金矿脉 | Q4.6 场景 |
| snag | 卡壳 / 事故 | Q4.6(b) 中导致某天零利润的事件，对应鞍点 |
| geoengineering | 地球工程 | 主动干预气候系统的技术 |
| marine cloud brightening | 海洋云增白 | 喷海盐气溶胶提高云反照率以反射阳光 |
| Stern report | 斯特恩报告 | 2006 年英国气候变化经济学评估报告 |
| economic cost to society | 社会经济成本 | $E$ |
| total cost | 总成本 | $\chi=E+C$ |
| offset warming | 抵消暖化 | |
| policy makers | 决策者 / 政策制定者 | |
| cost–benefit analysis | 成本效益分析 | Q4.7 的方法论 |
| boundary / endpoint | 边界 / 端点 | 有限定义域上必须额外检验的位置 |
| domain | 定义域 | |
| non-negative | 非负 | Q4.2 的约束 |
| sign table | 符号表 | 判别驻点类型的表格化方法 |

---

## 附：本周一页速查 (Cheat Sheet)

**判别口诀**
```
f' > 0  →  ↗ 递增
f' < 0  →  ↘ 递减
f' = 0  →  驻点，再看左右：
              −  0  +   →  minimum  （谷）
              +  0  −   →  maximum  （峰）
              +  0  +   →  saddle   （台阶）
              −  0  −   →  saddle   （台阶）
```

**最优化七步**
```
① 目标函数  ② 约束方程  ③ 消元成单变量
④ 求导      ⑤ 令 = 0    ⑥ 筛物理解
⑦ 判类型 + 回代 + 回答题目问的量
```

**本周重要结果**

| 问题 | 最优解 | 结论 |
|---|---|---|
| 封闭方底盒，$A=10\ \text{m}^2$ | $l=w=h=\sqrt{5/3}\approx1.29$ m | 正方体，$V_{\max}\approx2.15\ \text{m}^3$ |
| 开口方底盒，$A=48\ \text{m}^2$ | $w=4$ m，$h=2$ m | $h=w/2$，$V_{\max}=32\ \text{m}^3$ |
| 圆柱罐，$V=330$ ml | $r\approx0.0375$ m，$h\approx0.0749$ m | $h=2r$（高=直径），$A_{\min}=6\pi r^2\approx0.0264\ \text{m}^2$ |
| 金矿开采 | $n=9$ 天 | $P_{\max}=81{,}000$，边际收益=边际成本 |
| 金矿 snag | $n=10$ 天 | 重根 → **saddle point** |
| 地球工程 | $C^\ast=\frac{\ln(5000d)}{d}$；$d=2\times10^{-4}$ 时 $C^\ast=0$ | 方案不应实施 |
| 和为 9，$xy^2$ 最大 | $x=3,\ y=6$ | 最大值 108 |
