# Week 5 — 用 SciPy 求解微分方程（Modules and Functions: Solving Differential Equations）

> 课程：EART11200 The Natural Scientist's Toolkit — Computer Programming（Hilary Term）
> 材料：Lecture5_25（讲义）+ EART11200 - 25-Feb-transcript（课堂转写）+ Practical_5（Notebook）
> 本周仍属于「Modules and Functions」大主题的第 3 部分（Part 5 of the slides / part 3 of the module-and-function block），是「纯 Python + NumPy 基础」阶段的收尾，下周开始转向「数据驱动」（Pandas、地理空间数据）。

---

## 一、本周主题

### 1. 一句话概括
学会**把一个（或一组）微分方程翻译成 Python 函数**，然后调用 `scipy.integrate.odeint` 这个现成的 **ODE solver（常微分方程求解器）** 把它**积分**出来，最后用 `matplotlib` 把解画成图。

### 2. 本周在课程中的位置（course layout）
讲义给出的 9 周（12 次）编程内容地图：

| 阶段 | 周次 | 内容 |
|---|---|---|
| 'Vanilla' Python | 1–2 | Data types、Loops、Basic operations、Conditionals |
| Modules and Functions | 3–5 | The NumPy module（W3）→ Conway's Game of Life（W4）→ **Differential Equations（W5，本周）** |
| 数据驱动 | 6–9 | Pandas and data discovery、Geospatial analysis（两周）、Statistical Analysis、Cluster Analysis |
| 评估 | 10–12 | Creating a notebook assessment（从 Week 4–9 中自选一个主题） |

老师原话（转写）：本周之后「**That then really wraps up everything we need to know at this stage in terms of modules and functions**」——模块与函数的知识点到本周就讲完了，但之后每一周都会继续 import 模块用函数。老师建议把本周当作一个 **checkpoint**：确认自己真的懂了 functions、conditionals、arrays，不懂就在 practical 上找助教当面过一遍。

### 3. 上周回顾（recap，讲义原文）
- Functions help us repeat a set of operations many times — 用 `def` 和 `return` 语句定义。
- Modules contain functions we can access using the `.` operator（用点运算符访问模块里的函数）。
- The NumPy module is the standard way to deal with numerical operations in Python。

老师额外强调：**从现在开始一律用 NumPy array**，因为 `odeint` 这类函数**就期望你传 NumPy 数组进去**（"The function that we'll use to solve the differential equations expects us to provide numpy arrays"）。养成这个习惯，才能接上整个 Python 科学生态。

### 4. Practical 5 的学习目标（讲义 practical 5 goals）
**code 层面：**
- Learning how we solve a single differential equation using the SciPy package
- Integrate an exponential decay equation（指数衰减 / 放射性衰变）
- Solve coupled equations: Implement the Predator-Prey equations, or the Lotka-Volterra model

**general experience 层面：**
- Learn how to use existing modules to solve a particular problem（学会用现成模块解决具体问题）
- Start to consider sensitivity to variables（开始考虑解对参数/初值的敏感性）

---

## 二、核心概念

### 1. 为什么地球科学家需要解微分方程
老师在转写里花了很长篇幅做「科学动机」铺垫，这部分是考试/报告里写 background 的好素材：

- **微分方程无处不在**："differential equations are everywhere, unfortunately." 任何想要**数值模拟（numerical model）**一个系统的过程，最终都会遇到「某个量随时间/空间变化」的问题。
- **大多数物理理论一开始就是微分方程的形式**："Newton's laws of motion, heating, many things that describe how things change in space and time start as a differential equation."
- **建模流程**：理论（微分方程）→ 翻译成计算机能解的形式 → 得到一个「数字版的地球」（a digital version of our planet）→ 求解，预测 100 年、200 年后会发生什么。
- **真实系统必然是耦合的**：以人口增长为例，`dP/dt` 不会只依赖 P，还会依赖 geopolitical factors、economic status、land use change……于是很快就变成 **coupled differential equations（耦合微分方程）**——改变其中一个量会改变另一个量，所以**不能一个一个分别积分**。
- **气候政策的现实关联**：解得快很重要，因为「if you're solving something on a 100 year time scale... you want to look at the impacts pretty quickly. We can't leave something running for a year. Governments change, don't they」。老师指出目前很多人正在紧急评估排放情景变化的影响，数值工具与现实世界之间有非常强的联系。

### 2. Differentiation vs Integration（微分 vs 积分）——本课的方向
- 你在数学课（Matt 的课）上做的是：**给一个函数 → 求它的梯度（导数）**，有一套求导规则。
- 本课关心的**主导用法是反过来**：**从一个微分方程出发（它告诉你变化率），想预测 10 分钟后各变量的实际值** → 这就是**积分（integration）**，本质是「reversing differentiation」。
- 原话："This no longer becomes rate of change with respect to time. You're solving it to predict the actual value. So you're reversing differentiation."

### 3. Analytical vs Numerical solution（解析解 vs 数值解）
| | Analytical（解析） | Numerical（数值） |
|---|---|---|
| 做法 | 用微积分规则直接推出表达式，例如从 dN/dt = -ΓN 推出 N(t) = N₀e^(-Γt) | 迭代：不断微调各变量的数值，逐步逼近满足方程的解 |
| 速度 | 一旦得到表达式，计算极快 | 需要反复迭代 |
| 适用 | 只对少数简单方程可行（sometimes we can integrate by hand, sometimes we can't） | 耦合系统、复杂系统基本只能用这个 |
| 精度 | 精确 | **永远不完美**（"numerical solutions are not perfect. They're never perfect."），但可以把误差控制在可接受范围内 |

老师原话："An analytical approach is going from here to here, so we can actually get an expression, which is by far the quickest if you were to run that. A numerical approach is iterative. We keep changing the numbers in the system and make sure it abides by those rules."

### 4. Time step（时间步长）与数值误差 —— 求解器在背后做什么
这是转写里最有价值的一段**直观解释**（配合老师在板上画的 s(t) 曲线）：

1. 你有一条真实解曲线 s(t)（图上的**虚线**）。
2. 在起始点，求解器算出该点的**梯度（导数值）**。
3. 沿着这个梯度方向**走一个 time step**（比如 1 秒），得到下一个点。
4. 在新点再算梯度，再走一步……如此形成一条折线轨迹（图上的**实蓝线**）。
5. **问题**：因为真实曲线是弯的，沿直线梯度外推会偏离；步长越大，"our error is getting worse and worse and worse"，误差不断累积。
6. **求解器的工作**：自动判断 time step 需要多小，才能把误差控制在**你指定的 tolerance（容差）**之内。
7. **代价**："The more accurate a solver becomes, the longer it takes to run, because what it's doing behind the scenes is it's making this time step smaller and smaller to reduce the error projection from each gradient."

> 关键理解：**「naive 地假设解会沿着当前梯度这条直线一直走下去」是错的**，积分的意义就在于持续考虑变化率的变化，从而真正跟随曲线。

### 5. Boundary value problem（边值问题 / 初值问题）
- 定义（老师版本）：设定一个起始值（和/或终点值）+ 一段时间区间，求这段区间内的解。
- 例子：放射性衰变——给定初始不稳定核数 N₀，给一段时间，求最终值；气候——给定气候的初始状态，预测 100 年。
- Notebook 里的措辞是 **initial boundary problems**（初值问题）：solver 要求我们**定义要解的微分方程 + 一组起始条件**。
- 注意：`odeint` 的文档名字是 **"Solve Initial Value Problems"**（IVP），Notebook 注释里就是这样标注的。

### 6. 数值求解器的其他选项（options）
老师列举了真实科研中会遇到、SciPy 文档里能查到的选项：
- **rtol / atol**：relative tolerance / absolute tolerance（相对容差 / 绝对容差）。值越大→解得越快但可能误差过大；值越小→越准但越慢。
- **Non-negative constraints（非负约束）**：物理/化学量（如浓度、种群数）**不能为负**。若 time step 太大，外推轨迹可能把解推到负值。有些 solver 支持「不许变负」的约束，有些不支持。
- **科学意义上的容差选择**：如果你的实验仪器精度只有某个水平，你的数值解精度**不应该比仪器还差**，否则你无法判断「测到的是不是真值」。老师：「you need to start matching the two」。这也是为什么科研中通常「要么你是 numerical modeller，要么你是 lab/field 人员」，两者的交界处就是精度讨论。

### 7. 不同问题需要不同的 solver
- 「each domain has its own preferred solver」：地下（subsurface）演化的时间尺度极长；大气化学/污染物的组分寿命可能只有几秒甚至更短。**求解策略完全不同**。
- 讲义/幻灯上有一张各语言 ODE 求解能力对比图（绿色 = 很好）：
  - **SciPy 在 boundary value problems 上只是 "fair"**——求解器数量少（老师估计 Python 大约 10–20 个 solver）。对本课的 notebook 足够，但真正复杂的科学问题就不够用了。
  - **Julia 在几乎所有类别都是优秀**（老师估计有约 300 个 solver），正成为数值模拟领域的 "juggernaut"，可能会取代很多气候模型。
  - Python 的价值在于它是一门优秀的 **glue language（胶水语言）**：可以从 Python 调用其他语言，把各语言的优势整合进来。"out of the box, it's not great for numerical simulations"（Python 本来就不是为数值计算而生，它是个 all-rounder）。

### 8. 求解 ODE 的通用工作流（general structure for solving ODEs, using SciPy）
讲义反复出现的**四步骨架**，本周所有代码都是这个模式：

```
1. Import modules                                  导入模块
2. Define a function to solve — the 'Right Hand Side' [RHS]   定义右端项函数
3. Define a period to provide outputs              定义输出时间数组
4. Call the ODE solver, with relevant options      调用求解器（可带选项）
```

**关于 RHS（右端项）这个术语**（老师专门解释）：
> 任何微分方程写成 `dx/dt = ...` 或 `dN/dt = ...`，**等号右边那一坨就叫 right-hand side (RHS)**，左边 `dx/dt` 是 left-hand side。查文档时看到 "rhs" 就是这个意思，是通用术语。我们要写的函数就是把 RHS 翻译成 Python。

**这个工作流不是 Python 独有的**："Actually very common in any other language. We will always need to define the right-hand side function and then call a solver."

### 9. Chaos / Deterministic chaos（确定性混沌）
- **Lorenz system** 是三个耦合微分方程，由美国数学家兼气象学家 Edward Lorenz 研究。
- **butterfly effect（蝴蝶效应）**：Notebook 原文——"In popular media the 'butterfly effect' stems from the real-world implications of the Lorenz attractor, i.e. that in any physical system, in the absence of perfect knowledge of the initial conditions (even the minuscule disturbance of the air due to a butterfly flapping its wings), our ability to predict its future course will always fail."
- 特征："The series does not form limit cycles nor does it ever reach a steady state."（既不形成极限环，也不达到稳态）——这是 **deterministic chaos（确定性混沌）**：方程是完全确定的（同样初值给同样结果），但**两个任意接近的初始状态最终一定会发散**。
- 老师的口头例子：X=1、Y=0.5 跑 10 秒是一个结果；X=1.01、Y=0.5 可能"wildly different"。
- 与气候/天气的联系：天气就是混沌系统，Lorenz 方程被用在气候预报研究中。**这也解释了为什么天气预报有可预报性上限**。

### 10. 敏感性分析（sensitivity）——为什么本周要求你改参数
老师强调：一旦能把方程写成代码，就可以**改参数看系统怎么变**。如果某个参数（例如 Lorenz 的 σ）代表一个会因气候变化而改变的过程，那么改这个参数就能看到对天气系统的影响。"That's the kind of visualization you want to get to, because you can start understanding that. You can tell a story with it."

---

## 三、语法速查与函数表

### 3.1 本周新增/核心函数

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `from scipy.integrate import odeint` | 从 SciPy 的 integrate 子模块**只导入** `odeint` 一个函数（ODE Integrator，解初值问题） | `from scipy.integrate import odeint` | 用 `from ... import ...` 后调用时**不用写前缀**，直接 `odeint(...)`；若写成 `import scipy` 则必须写 `scipy.integrate.odeint(...)` |
| `odeint(func, y0, t)` | 数值积分常微分方程组 | `solution = odeint(differential_function, No, t)` | **参数顺序固定**：① RHS 函数名（**不加括号！**）② 初始条件（标量或序列）③ 输出时刻数组。返回 2D array，形状 `(len(t), 变量个数)` |
| `odeint(func, y0, t, rtol=..., atol=...)` | 带容差选项调用 | `odeint(f, y0, t, rtol=1e-6, atol=1e-8)` | rtol/atol 有默认值，不传就用默认；值越小越准越慢 |
| `np.arange(start, stop, step)` | 按**固定步长**生成数组 | `t = np.arange(0, 1, 0.01)` → 100 个值 | **不含 stop**；元素个数 = (stop-start)/step，容易因浮点误差多/少一个 |
| `np.linspace(start, stop, num=N)` | 生成 start 到 stop 之间 **N 个等间距**的值 | `t = np.linspace(0, 1, num=100)` | **默认包含 stop**（`endpoint=True`）；老师推荐用它定义时间数组，因为「你直接指定要多少个点，它自己算间隔」 |
| `np.zeros((shape), dtype=float)` | 生成全 0 数组，用作「存储容器」 | `np.zeros((100,10), dtype=float)` | shape 用元组；先建空数组再在循环里填是标准套路 |
| `solution[:, 0]` | NumPy **切片索引**：取第 0 列的全部行 | `x = solution[:,0]` | `:` = 「这一维全要」；`[行, 列]` 顺序不能反 |
| `plt.figure(figsize=(5,5))` | 创建画布并指定尺寸（英寸） | `fig = plt.figure(figsize=(10,10))` | figsize 是 (宽, 高) |
| `plt.axes()` | 在当前 figure 上创建一个坐标轴对象 | `ax = plt.axes()` | 之后用 `ax.plot`、`ax.set_xlabel` 等「面向对象」写法 |
| `fig.add_subplot(projection='3d')` | 创建 3D 坐标轴 | `ax = fig.add_subplot(projection='3d')` | 需要 `from mpl_toolkits.mplot3d import Axes3D`（新版 matplotlib 里可省，但 notebook 保留了它） |
| `ax.plot(x, y, z, alpha=0.4)` | 3D 折线图；`alpha` 是**透明度** | 见 Lorenz 例 | alpha 取 0（全透明）到 1（不透明）；Lorenz 轨迹重叠严重，调低 alpha 更容易看出结构 |
| `ax.plot(t, 2D_array)` | 传一个 2D 数组时，**matplotlib 自动为每一列画一条线并自动换颜色** | `lineObjects = ax.plot(t, solution_store_array)` | 返回的是一个 **line objects 列表**，可用于批量加图例 |
| `plt.legend(iter(lineObjects), (标签元组))` | 给一组线对象批量加图例 | 见 Exercise 1 | 标签个数必须与线条数一致，否则少的线没有图例 |
| `plt.plot(t, y, 'r-', label='Rabbits')` | 指定颜色+线型的简写（`'r-'` = 红色实线，`'b-'` = 蓝色实线） | 见 Exercise 2 | 用 `label=` + `plt.legend()` 才会显示图例 |
| `plt.legend(loc='best')` | 自动挑一个不遮挡数据的位置放图例 | | |
| `plt.grid()` | 加网格线 | | 便于读数 |
| `plt.show()` | 显示图 | | 在 notebook 里不加也常能显示，但加上可**避免最后一行返回值被当作文本输出** |

### 3.2 RHS 函数的写法模板（必须背下来）

**单变量（非耦合）版本：**
```python
def differential_function(N, t):
    return -1.0 * Gamma * N
```
- 参数顺序：**`(当前状态, 当前时间)`**——`odeint` 就是按这个顺序调用你的函数的，**顺序不能反**。
- `t` 即使用不到也**必须写在参数里**，否则 `odeint` 传两个参数进来会报 `TypeError`。
- 返回值 = 微分方程的**右端项**（导数值），不是变量本身。

**多变量（耦合）版本：**
```python
def differential_function(array, t):
    X = array[0]          # 自己规定：第 0 个元素是 X
    Y = array[1]
    Z = array[2]
    dX_dt = ...
    dY_dt = ...
    dZ_dt = ...
    return [dX_dt, dY_dt, dZ_dt]    # 顺序必须与 array 的顺序一致！
```
- 老师强调："I know that according to the address in that array, the first, second, and third element represent X, Y, and Z. **That's just something I've defined. It's not something the computer's defining.**"——变量与下标的对应关系是**你自己约定的**，计算机不知道，所以**输入解包顺序与输出返回顺序必须严格一致**。
- 变量个数可以是 3，也可以是「tens of thousands，it doesn't matter」，模式完全一样。

### 3.3 绘图产物与判读要点

| 图 | 生成方式 | 怎么判断结果对不对 |
|---|---|---|
| 单条指数衰减曲线 | `ax.plot(t, solution)`，solution 是 (100,1) 数组 | 曲线应从 N=1000 出发**单调递减**趋近 0；不应出现上升或负值。可与解析解 N(t)=N₀e^(-Γt) 对照——Γ=5、t=1 时 N ≈ 1000·e⁻⁵ ≈ 6.7 |
| 10 条不同 Γ 的衰减曲线 | 把 10 次解存进 (100,10) 数组，一次 `ax.plot(t, array)` | **Γ 越大衰减越快**——图上曲线应按 1.0、1.5、2.0…25.0 的顺序从「衰减最慢」到「最陡」排列。老师："you can see the bigger the value of gamma, the quicker the decay. That makes sense." 若顺序反了/所有线重合，说明循环里没有正确更新 Gamma |
| Lorenz attractor（3D） | `fig.add_subplot(projection='3d')` + `ax.plot(x,y,z,alpha=0.4)` | 应出现经典的**双叶「蝴蝶／面具」形状**，轨迹在两个「翅膀」之间来回切换、永不闭合也不收敛到点。t 取 10000 个点才够平滑（老师：这就是为什么图这么光滑） |
| Predator-Prey 时间序列 | `plt.plot(t, rabbits, 'r-')` + `plt.plot(t, foxes, 'b-')` | 应看到两条**周期性振荡**曲线，且**狐狸的峰值滞后于兔子的峰值**（兔子多→狐狸吃得饱→狐狸增多→兔子被吃光→狐狸饿死→兔子回升）。两条曲线都应 **≥ 0**；若出现负种群，说明参数或容差有问题 |

---

## 四、课堂补充（transcript 独有）

以下内容**只在课堂录音里出现**，讲义和 notebook 上没有，但对理解非常关键。

### 4.1 老师对「为什么我们不自己写 solver」的态度
> "This course is very much applied. So we'll use modules and we'll trust that they work. **You'll find that sometimes they don't work**, but you don't need to understand how all these equations have been solved, which is great. So it takes the burden off you as a scientist."

要点：① 我们**信任**成熟模块；② 但要意识到**它们有时会失效**（比如 `odeint` 对某些方程"will struggle to get an answer"）；③ 作为科学家你不需要懂求解算法内部，但要懂**怎么判断结果合不合理**。

### 4.2 关于 LLM 与未来的科研工作流（老师的一段展望）
> "I'm pretty sure in the future you'll be able to write these equations in LaTeX or whatever and you'll say, well, please solve these equations with these conditions. And behind the scenes, code will be written and generated... **But it will always require scientists and engineers to understand that process. So there's a safety check there.** It's just the nature of how we do science will change."

——即使 AI 能自动生成代码，**科学家仍必须理解过程**，这是安全检查。

### 4.3 关于「文档（documentation）」的实用建议
讲义："Using module documentation. The most useful have examples as code so you can at least understand the required code structure. Options can look like 'gobble-de-gook', until you practice running examples."

老师补充：
- SciPy 在线文档里每个模块都可以点开、都有可运行的示例，**你可以直接把示例复制到自己的 notebook 里跑**。
- 看文档的价值在于：知道**有哪些选项**，从而判断能不能改进你现在的做法（例如是否支持 non-negative constraints、默认容差是多少）。
- 「每个函数都有 function arguments（函数参数）」——这正是本周还在讲 modules and functions 的原因。

### 4.4 关于「函数名一致性」的现场提醒
> "Make sure that you see how I've structured the definition of the right-hand side... **You can change the name, but make sure the name is consistent between your function name and what the solver sees.**"

即：`def my_ode(...)` 定义了什么名字，`odeint(my_ode, ...)` 就必须传同一个名字；这是最常见的 `NameError` 来源。

### 4.5 关于默认参数值
> "Remember, functions that are in Python modules often have default values. You don't have to change them."

Lorenz 例子里老师**没有**设 rtol/atol，因为默认值"typically they're always very, very small"，够用了。必须传的只有三个：**函数名、起始值、输出时刻数组**。

### 4.6 关于「可以用解析解验证数值解」
> "You could check the output of this by actually knowing that there is an integral function given here. And you'll get, within that set tolerance we've given the solver, the same value. So in this case, **we can check the output from our integral solver because we know what the answer should be. We don't need to solve this with Python, but it's just illustrating that you can.**"

——放射性衰变这个例子**故意选一个有解析解的方程**，目的就是让你能验证数值解。这是很好的调试/验证思维：**先在已知答案的问题上验证你的代码，再拿去解未知问题**。

### 4.7 课堂上的实际技术故障（值得记录的「踩坑」）
1. **老师自己的签到码 bug**：签到系统"keeps defaulting to the one the week before"（总是默认成上一周的码），老师重新弄了一次才对——提醒：**工具默认值可能是过期的缓存，要检查**。
2. **学生的 Anaconda 安装问题**（Mac）：
   - 症状：磁盘只有 2 GB，删了东西腾出空间后重新下载，安装器却报 **"it already exists on my Macintosh HD"**（已存在）。
   - 后续症状：在 Anaconda Navigator 里创建了 environment，点开却**无法 "open with Jupyter Notebook"**。
   - **老师给的替代方案（重要，遇到装不上就用这个）**：用 **Google Colab**——从老师 GitHub 页面上的 Colab 按钮进入，用 Google 账号登录，"click yes to everything"，可以获得**完全一样的体验**，不需要本地安装任何东西。

### 4.8 关于期末 notebook assessment（学生提问 + 老师回答）
- 会给一份 **rubric（评分标准）**。
- 从 Week 4–9 中**选一个主题**做一份 notebook。可选题目里：**只有 Conway's Game of Life 是非真实世界的**，其余都是真实数据题——地震（earthquake）数据框架、气象数据的统计分析、地理空间分析等。
- 「additional reading」的作用是**给代码提供科学背景**，不是找更多数据来跑。老师描述期望的样子：
  > "Imagine if you were given it to someone who wants to understand what the hell is the code doing and why. It's literally a basic introduction to, you know, like **earthquakes are important because of this. Here's a database we're loading in and plot on the map, and here's how the earthquakes have changed.**"
- **推荐做法**：**先把代码跑通**，再补背景叙述；可以直接把 practical 的代码迁移过去，但要**改一些选项、把功能扩展一点**。
- 老师的评分心态：「The good result is delivering exactly what's been given, briefly describing what happens... It's very hard to not do well in this course in the sense that the people who don't just don't do it.」——**照做就能拿好分，拿不到分的基本是没做**。

---

## 五、Practical 要点

Notebook 文件：`Practical_5.ipynb`（对应 `Practical_5.md`）。
整体说明：Notebook 会给你**绘图模板**，你只需要在标着 `INSERT CODE HERE` 的地方补代码。不必在课上做完，Solutions 文件夹里有参考答案。

---

### 【示例 0】放射性衰变方程 —— 完整示范（已给出，不用你写）

#### 科学背景
放射性衰变方程（radioactive decay equation）：

$$\frac{dN}{dt} = -\Gamma N$$

- `N` = 尚未衰变的不稳定核（unstable nuclei）数量
- `Γ`（Gamma）= 衰变常数（decay constant），越大衰变越快
- 负号表示 N 随时间**减少**
- 这是**有解析解**的方程：N(t) = N₀·e^(−Γt)，所以可以用来验证数值解

#### 题目要求
理解 SciPy 求解单个 ODE 的完整流程；运行代码后回答「图代表什么」。

#### 完整代码（逐行注释）
```python
# ===== 第 1 步：Import the packages we need（导入模块）=====
import numpy as np                        # NumPy：提供数组与数值运算，惯例别名 np
from scipy.integrate import odeint        # 只从 scipy.integrate 里拿 odeint 这一个函数
                                          # odeint = ODE INTegrator，用于 Solve Initial Value Problems
import matplotlib.pyplot as plt           # 绘图库，惯例别名 plt

# ===== 第 2 步：Set some initial conditions and parameter values（设参数与初值）=====
Gamma = 5.0                # 衰变常数 Γ = 5.0（全局变量，函数内部会用到）
No = 1000                  # N 的初始值 N₀ = 1000 个核
t = np.arange(0, 1, 0.01)  # 时间数组：从 0 开始，到 1（不含），步长 0.01
                           # → 得到 [0, 0.01, 0.02, ..., 0.99]，共 100 个元素
                           # 这就是「我要在哪些时刻拿到输出」

# ===== 第 3 步：Define the RHS function（定义右端项函数）=====
# 注意传给函数的变量顺序，以及 ':' 后面的缩进（Python 用缩进划分代码块）
def differential_function(N, t):
    return -1.0*Gamma*N    # 直接把 dN/dt = -Γ·N 的右端翻译成 Python
                           # 返回的是「导数值」，不是 N 本身
                           # 参数 t 这里没用到，但必须写——odeint 会传两个参数进来

# ===== 第 4 步：Call the solver（调用求解器）=====
# 1 - solver 需要知道：起始条件 + 积分的时间跨度
# 2 - solver 返回一个数组，可以直接和 t 一起画图
solution = odeint(differential_function, No, t)   # 三个参数：函数名、初值、输出时刻数组
                                                  # 返回 shape = (100, 1) 的 2D 数组

# ===== 第 5 步：绘图 =====
fig = plt.figure(figsize=(5,5))    # 建一块 5×5 英寸的画布
ax = plt.axes()                    # 在画布上建一个坐标轴对象
ax.plot(t, solution)               # 横轴时间，纵轴解
ax.set_title('Solution to our exponential function')
ax.set_ylabel('N')
ax.set_xlabel('time [seconds]')
```

#### 输出解读
```
Text(0.5, 0, 'time [seconds]')
```
- 这行文字**不是错误**！它是 Jupyter 自动显示 cell **最后一个表达式的返回值**——`ax.set_xlabel(...)` 返回一个 matplotlib `Text` 对象，`(0.5, 0)` 是这个文本对象在坐标轴中的位置，`'time [seconds]'` 是文本内容。想让它消失，可以在末尾加一行 `plt.show()` 或在该行末加分号 `;`。
- 图：一条从 (0, 1000) 出发、快速下降、逐渐趋近 0 的**指数衰减曲线**。
- **正确性判断**：t=1 时应约为 1000·e^(−5·1) ≈ 6.74，接近 0 但不为负。若曲线上升、变负或是直线，说明 RHS 写错（比如漏了负号）。

---

### 【Exercise 1】Integrate an exponential decay equation（循环解 10 个不同的 Γ）

#### 题目要求
遍历 **10 个不同的衰减系数 Γ**，把 10 条衰减曲线画在**同一张图**上。要完成的操作：
- Import the required libraries
- Initialise an array that will store all of the decay values for each choice of decay coefficient（**初始化一个存储数组**）
- Loop through calling the ODE solver for each choice of decay coefficient（**循环调用求解器**）
- Update the array that stores all of the decay values（**更新存储数组**）
- Plot the results

#### 解题思路
1. 时间数组有 100 个点，Γ 有 10 个 → 结果是 **100 行 × 10 列** 的 2D 数组。
2. 先用 `np.zeros((100,10))` **预先开好空数组**（这是 NumPy 的标准做法：不要在循环里不断拼接数组）。
3. 循环 `i` 从 0 到 9：
   - 把 `Gamma` 这个**全局变量**改成 `Gamma_array[i]`——因为 `differential_function` 内部引用的是全局的 `Gamma`，所以改全局变量就能改变函数行为；
   - 调 `odeint` 得到 `solution`（形状 (100,1)）；
   - 把它**压平成一列**存进 `solution_store_array[:, i]`。
4. **关键提示（notebook 原文给的 HINT）**：`solution` 是 2D 的 (100,1)，而 `solution_store_array[:,i]` 是 1D 的 (100,)，形状不匹配，所以要写 **`solution[:,0]`** 取出第 0 列变成 1D。

#### 完整代码（逐行注释）
```python
# ===== 导入模块（与前例相同）=====
import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt

# ===== 建一个装 10 个 Γ 值的数组，范围 1 到 25 =====
Gamma_array = np.zeros((10), dtype=float)   # 先建一个长度 10、全 0、浮点型的一维数组
Gamma_array[0]=1.0                          # 然后逐个手动赋值
Gamma_array[1]=1.5
Gamma_array[2]=2.0
Gamma_array[3]=5.0
Gamma_array[4]=8.0
Gamma_array[5]=12.0
Gamma_array[6]=15.0
Gamma_array[7]=20.0
Gamma_array[8]=22.5
Gamma_array[9]=25.0
# 注意：索引从 0 到 9（不是 1 到 10），写 Gamma_array[10] 会 IndexError

No = 1000                              # 初值不变
t = np.linspace(0, 1, num=100)         # 这次用 linspace：0 到 1 之间取 100 个等间距点
                                       # 与上例的 np.arange(0,1,0.01) 元素数相同（都是100），
                                       # 但 linspace 是「含端点、指定个数」，arange 是「不含终点、指定步长」

# ===== RHS 函数完全不变 —— 它读的是全局变量 Gamma =====
def differential_function(N, t):
    return -1.0*Gamma*N

# <<-------------------- INSERT CODE HERE ----------------------->>
# 预先开好存储用的 2D 数组：100 个时间点 × 10 个 Γ
solution_store_array = np.zeros((100,10), dtype=float)

# 循环：每次换一个 Γ，解一次，把结果存进对应的列
for i in range(10):                    # range(10) 产生 0,1,2,...,9
    Gamma = Gamma_array[i]             # 把全局变量 Gamma 改成第 i 个值
                                       # ← 这行是关键：函数内部下次被调用时读到的就是新值
    solution = odeint(differential_function, No, t)   # 解这一个 Γ 对应的 ODE
                                                      # solution 形状 (100, 1)
    solution_store_array[:,i] = solution[:,0]         # solution[:,0] 把 (100,1) 变成 (100,)
                                                      # [:,i] 表示「第 i 列的全部行」
# <<------------------------------------------------------------->>

# ===== 绘图：一次传入 2D 数组，Python 自动为每列换颜色 =====
fig = plt.figure(figsize=(5,5))
ax = plt.axes()
lineObjects = ax.plot(t, solution_store_array)   # 传 2D 数组 → 一次画 10 条线
                                                  # 返回值是一个包含 10 个 Line2D 对象的列表
plt.legend(iter(lineObjects),
           ('1.0','1.5','2.0','5.0','8.0','12.0','15.0','20.0','22.5','25.0'))
           # iter(...) 把列表变成迭代器传给 legend，第二个参数是对应的 10 个标签
ax.set_title('Solution to our exponential function')
ax.set_ylabel('N')
ax.set_xlabel('time [seconds]')
```

#### 输出解读
```
Text(0.5, 0, 'time [seconds]')
```
（同上，是 `set_xlabel` 的返回值，非报错。）

图：10 条从 (0,1000) 出发的衰减曲线，颜色各异，带图例。
**正确性判断**：
- **Γ = 1.0 的曲线衰减最慢**（t=1 时仍在 1000·e⁻¹ ≈ 368 附近）；
- **Γ = 25.0 的曲线最陡**，几乎立刻掉到 0（1000·e⁻²⁵ ≈ 1.4×10⁻⁸）；
- 所有曲线单调下降、不交叉、不为负。
- 如果 10 条线**完全重叠**，说明忘了在循环里更新 `Gamma`（比如写成了 `Gamma_array[i]` 却赋给了别的名字）。

#### 关于「全局变量 Gamma」的说明（重要理解点）
`differential_function` 里没有把 `Gamma` 当参数传进去，而是直接引用**函数外部定义的全局变量**。这在 Python 里是允许的（函数体内找不到某个名字时会向外层作用域查找）。这就是为什么在循环里执行 `Gamma = Gamma_array[i]` 后，**下一次调用 `odeint` 时函数读到的就是新的 Γ**。
- **优点**：代码简洁，不用改 `odeint` 的调用方式。
- **风险**：依赖全局状态，可读性差、容易出 bug。更「正规」的做法是用 `odeint` 的 `args=(Gamma,)` 参数把值显式传进去，或者把 Γ 也作为函数参数。本课为简单起见用了全局变量方式，**但要知道这是一个隐式依赖**。

---

### 【示例 1】Additional example: Implementing the Lorenz system（已给出，不用你写）

#### 科学背景
Lorenz 系统是三个耦合一阶微分方程：

$$\frac{dX}{dt} = \sigma(Y-X)$$
$$\frac{dY}{dt} = (\rho-Z)X - Y$$
$$\frac{dZ}{dt} = XY - \beta Z$$

Notebook 用「英文白话」解释（这段要会读方程）：
- The rate of change of component **X** is a function of some constant σ multiplied by component **Y minus X**
- The rate of change of component **Y** is a function of some constant ρ minus component Z, the product of which is multiplied by component X. Then subtract component Y
- The rate of change of component **Z** is a function of X multiplied by Y, minus a constant β times Z

参数含义：σ（sigma）、ρ（rho）、β（beta）是三个常数；本例取 σ=10、β=2.667、ρ=28，这是产生经典蝴蝶形吸引子的标准取值。

#### 解题思路
和单变量的区别只有一点：**不再传单个变量，而是通过数组一次传 3 个变量**。
- RHS 函数**接收**一个含 3 个元素的数组 → 内部按下标解包成 X、Y、Z；
- RHS 函数**返回**一个含 3 个导数的列表，**顺序必须与输入数组一致**；
- `odeint` 的第二个参数变成一个 3 元组 `(X0, Y0, Z0)`；
- 返回的 `solution` 形状是 `(10000, 3)`，用列索引拆出 x、y、z。

#### 完整代码（逐行注释）
```python
# ===== 导入模块 =====
import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D   # 导入 3D 绘图工具包，才能画「漂亮的」3D 图

# ===== Set Lorenz parameters and initial conditions（参数与初值）=====
sigma = 10        # σ
beta = 2.667      # β
rho = 28          # ρ
X0 = 5            # X 的初值
Y0 = 1            # Y 的初值
Z0 = 1.05         # Z 的初值

# ===== 定义 RHS 函数：现在接收/返回数组 =====
def differential_function(array, t):
    # 函数收到一个含 3 个格子的数组
    # 在函数外部我们已经「约定」第 1 个是 X、第 2 个是 Y、第 3 个是 Z
    # 所以这里用 Python 索引把它们取出来
    X = array[0]     # 索引从 0 开始
    Y = array[1]
    Z = array[2]

    # The Lorenz equations —— 用有意义的变量名，逐行对应上面的数学式
    dX_dt = sigma*(Y - X)      # dX/dt = σ(Y−X)
    dY_dt = (rho-Z)*X-Y        # dY/dt = (ρ−Z)X − Y
    dZ_dt = X*Y-beta*Z         # dZ/dt = XY − βZ

    # 返回一个装着「各导数值」的数组/列表
    # 顺序必须与输入 array 中变量的顺序完全一致
    return [dX_dt, dY_dt, dZ_dt]

# ===== 定义输出时刻：0 到 100，共 10000 个点（非常高的时间分辨率）=====
t = np.linspace(0, 100, num=10000)

# ===== 调用求解器 =====
# 注意：这里没有传 rtol/atol，用的是 odeint 的默认容差（默认值非常小，够用）
solution = odeint(differential_function, (X0, Y0, Z0), t)
# 传进去的是变量数组，返回的就是「每个时刻每个变量的值」的 2D 数组，形状 (10000, 3)

x = solution[:,0]   # X 是数组第 1 个变量 → 输出的第 0 列
y = solution[:,1]   # Y → 第 1 列
z = solution[:,2]   # Z → 第 2 列

# ===== 用 Matplotlib 的 3D projection 画 Lorenz attractor =====
fig = plt.figure(figsize=(10,10))
ax = fig.add_subplot(projection='3d')   # 创建 3D 坐标轴
ax.plot(x, y, z, alpha=0.4)             # alpha 是透明度；轨迹密集重叠时透明度低更好看
ax.set_xlabel('X')
ax.set_ylabel('Y')
ax.set_zlabel('Z')                      # 只有 3D 轴才有 set_zlabel
plt.show()
```

#### 输出解读
输出是一张 3D 曲线图，呈现经典的 **Lorenz attractor（洛伦兹吸引子）**：两片像蝴蝶翅膀（或面具）的螺旋面，轨迹在两叶之间不规则地来回跳转。
**正确性判断**：
- 应看到**两个明显的螺旋叶片**；
- 轨迹**永远不闭合**（不形成 limit cycle）、**永远不收敛到一点**（不达 steady state）；
- 若图变成一个点或一个封闭圈，说明参数写错（ρ 太小时系统会收敛到不动点）。

#### Notebook 建议的实验（"Why not change the following variables and see how the image responds?"）
- **把 β 改成 4.0** → 吸引子的形状会改变（翅膀的大小/位置变化）。
- **把时间步数改成 1000**（`num=1000`）→ 时间分辨率降低 10 倍，曲线变得**明显折线化、不再平滑**，因为输出点稀疏了。这直接印证了讲义中「time step 与精度」的道理。
- 也可以微调初值（比如 X0 从 5 改成 5.01）来体验**混沌对初始条件的敏感性**——短时间内两条轨迹接近，长时间后完全不同。

---

### 【Exercise 2】Implementing the Predator-Prey equations（Lotka-Volterra model）

#### 科学背景
- 这个例子直接取自 **SciPy 官方 cookbook**（scipy-cookbook.readthedocs.io 的 LotkaVolterraTutorial）。
- **Lotka-Volterra 模型**，又称 **predator-prey equations（捕食者-猎物方程）**：一对**一阶、非线性**微分方程，常用来描述两个物种（一个捕食者、一个猎物）相互作用的生物系统动态。
- 由 **Alfred J. Lotka（1925）** 和 **Vito Volterra（1926）** 各自独立提出。

方程：
$$\frac{dU}{dt} = aU - bUV$$
$$\frac{dV}{dt} = -cV + dbUV$$

参数含义（务必记住）：
| 符号 | 含义 |
|---|---|
| U | number of preys（猎物数量，例如兔子 rabbits） |
| V | number of predators（捕食者数量，例如狐狸 foxes） |
| a | 兔子的**自然增长率**（没有狐狸时） |
| b | 兔子因**被狐狸捕食**而死亡的速率 |
| c | 狐狸的**自然死亡率**（没有兔子时） |
| d | 描述**捕到多少兔子会带来多少狐狸增长**的转化因子（注意它与第一个方程里的捕食项 b 的相似性） |

**方程的物理直觉**（对照老师的讲解）：
- `+aU`：正项 → 兔子自然繁殖，数量增加；
- `−bUV`：负项，且**同时依赖 U 和 V** → 兔子和狐狸「相遇」才会被吃，所以是乘积；
- `−cV`：负项 → 狐狸自然死亡；
- `+dbUV`：正项 → 吃掉的兔子转化成新的狐狸。
- 老师："if you have a negative differential, it leads to a decrease in something. If you have a positive, it leads to an increase."

#### 题目要求
Notebook 已经提供了「导库 + 绘图」模板，你需要在 `INSERT CODE HERE` 之间补上：
- create some initial conditions（起始的兔子与狐狸数量）
- define the constant parameters a, b, c and d
- set up the function that defines our differential equations and is called by the internal ODE solver
- run the simulation for a period of time
- plot the results

#### 解题思路
完全复用 Lorenz 的工作流，只是从 3 个变量降到 2 个变量：
1. 定义参数 a、b、c、d 和初值 U0、V0（都作为全局变量）；
2. 写 RHS 函数：接收 `array` → 解包成 U、V → 算 dU/dt、dV/dt → **按同样顺序**返回 `[dU_dt, dV_dt]`；
3. 定义时间数组；
4. `odeint(函数名, (U0, V0), t)`；
5. 用 `solution[:,0]`、`solution[:,1]` 取出兔子和狐狸；
6. 分别画两条线。

#### 完整代码（逐行注释）
```python
# ===== 导入模块（模板已给）=====
import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D   # 本例其实是 2D 图，这行是从上例复制来的，可省

#-------'INSERT CODE HERE'-------
# ===== Definition of parameters（定义常数参数）=====
a = 1.       # 兔子自然增长率（写成 1. 表示浮点数 1.0）
b = 0.1      # 兔子被捕食的死亡率
c = 1.5      # 狐狸自然死亡率
d = 0.75     # 捕食转化为狐狸增长的因子
U0 = 10      # 初始兔子数量
V0 = 5       # 初始狐狸数量

# ===== 定义 RHS 函数（两个耦合方程）=====
def differential_equations(array, t):
    U = array[0]                  # 约定：第 0 个元素是 U（兔子）
    V = array[1]                  # 第 1 个元素是 V（狐狸）
    dU_dt = a*U - b*U*V           # dU/dt = aU − bUV
    dV_dt = -c*V + d*b*U*V        # dV/dt = −cV + d·b·UV
    return [dU_dt,dV_dt]          # 返回顺序必须与 array 的顺序一致
#--------------------------------

# ===== 定义输出时刻：0 到 15，共 1000 个点 =====
t = np.linspace(0, 15, num=1000)

# ===== 调用求解器 =====
solution = odeint(differential_equations, (U0, V0), t)
# 返回 2D 数组，形状 (1000, 2)

rabbits = solution[:,0]   # 第 0 列 = U = 兔子
foxes   = solution[:,1]   # 第 1 列 = V = 狐狸

# ===== 绘图（模板已给）=====
fig = plt.figure(figsize=(10,10))
plt.plot(t, rabbits, 'r-', label='Rabbits')   # 'r-' = 红色实线；label 用于图例
plt.plot(t, foxes  , 'b-', label='Foxes')     # 'b-' = 蓝色实线
plt.grid()                                     # 加网格
plt.legend(loc='best')                         # 自动选最佳位置放图例
plt.xlabel('time')
plt.ylabel('population')
plt.title('Evolution of fox and rabbit populations')
plt.show()                                     # 显示（并抑制返回值文本）
```

#### 输出解读
输出一张 2D 图，两条**周期性振荡**的曲线（红=兔子，蓝=狐狸）。

**如何判断结果正确：**
1. **两条曲线都严格 ≥ 0**（种群不能为负）。若出现负值，说明容差/步长有问题（对应课上讲的 non-negative constraints 议题）。
2. **周期性、不衰减**：Lotka-Volterra 的经典解是**闭合的周期轨道**，振幅不随时间衰减。
3. **相位滞后**：狐狸的峰值总是**落后于**兔子的峰值。因果链：兔子多 → 狐狸食物充足 → 狐狸增多 → 兔子被大量捕食而减少 → 狐狸挨饿死亡 → 兔子又开始回升 → 循环。老师原话："if the number of rabbits go down, foxes get more hungry and start to die off. So there's interdependencies between the two. That's why you get this behavior in this system."
4. 兔子的峰值应显著高于狐狸（因为 b=0.1 较小，且 U0=10 > V0=5）。

**现实意义提醒**：老师明确说 "of course, reality is much more complex than that, but it's an application of how we can set... we can define these in Python, we can change these values, and then start looking at how the system changes very quickly, so we don't have to spend hours deriving integrals by hand."——这是 **toy model（玩具模型）**，价值在于展示「代码 → 快速改参数 → 快速可视化 → 快速理解系统」这条链路。

#### 可以自己做的延伸（体会 sensitivity）
- 改 `b`（捕食率）→ 振荡的振幅和周期会变；
- 改 `U0`、`V0` → 轨道的「大小」变（相空间中是不同的闭合环）；
- 把 `t` 拉长到 `np.linspace(0, 100, num=5000)` → 看长期是否仍保持周期（理论上是）；
- 减少 `num` → 曲线变粗糙，体会输出分辨率的影响。

---

## 六、易错点 / 重点难点

### 6.1 `odeint` 相关

| 错误写法 | 报错/现象 | 原因与修法 |
|---|---|---|
| `odeint(differential_function(), No, t)` | `TypeError: differential_function() missing 2 required positional arguments` | **传函数名时不能加括号**！加括号是「立即调用」，不加才是「把函数本身作为对象传进去」。改成 `odeint(differential_function, No, t)` |
| `def differential_function(N):` 然后 `odeint(f, No, t)` | `TypeError: differential_function() takes 1 positional argument but 2 were given` | `odeint` 固定用 `(y, t)` 两个参数调用你的函数，**即使不用 t 也必须写在签名里** |
| `def differential_function(t, N):` | 结果完全错误，但**不报错** | 参数**顺序**是 `(状态, 时间)`，写反了 → 你把时间当成了 N 去算。这是最阴险的 bug，因为不报错。（注意：SciPy 的另一个函数 `solve_ivp` 的顺序恰好相反，是 `(t, y)`——不要混淆） |
| RHS 里 `return N` 而不是 `return -Gamma*N` | 图形完全不对（指数增长而非衰减） | RHS 返回的必须是**导数值**，不是状态值 |
| 忘了负号 `return Gamma*N` | 曲线爆炸式上升 | 对照原方程 dN/dt = **−**ΓN 检查符号 |
| 耦合系统里 `return [dY_dt, dX_dt, dZ_dt]`（顺序乱了） | 无报错，但结果完全错误 | **输入解包顺序与输出返回顺序必须严格一致**。老师专门强调这个对应关系「is just something I've defined, it's not something the computer's defining」 |
| `odeint(f, X0, Y0, Z0, t)` | `TypeError` | 多变量的初值要**打包成一个序列**：`odeint(f, (X0, Y0, Z0), t)` |
| 函数名写错 / 定义的名字和调用的名字不一致 | `NameError: name 'xxx' is not defined` | 老师课上专门提醒：「make sure the name is consistent between your function name and what the solver sees」 |

### 6.2 数组形状（shape）问题 —— 本周最容易卡住的地方

```python
solution_store_array[:,i] = solution        # ← 会报 ValueError
```
报错类似：
```
ValueError: could not broadcast input array from shape (100,1) into shape (100,)
```
**原因**：`odeint` **永远返回 2D 数组**，即使只有一个变量，形状也是 `(100, 1)` 而不是 `(100,)`。而 `solution_store_array[:,i]` 是一个 1D 切片，形状是 `(100,)`。两者形状不兼容。

**修法**（notebook 给的 HINT）：
```python
solution_store_array[:,i] = solution[:,0]   # 用 [:,0] 把 (100,1) 降成 (100,)
```

**记忆口诀**：
- `odeint` 输出形状 = `(时间点个数, 变量个数)`
- 取第 k 个变量随时间的序列 → `solution[:, k]`
- `:` 表示「这一维全部要」，逗号前是行（时间），逗号后是列（变量）

### 6.3 `np.arange` vs `np.linspace`

| | `np.arange(0, 1, 0.01)` | `np.linspace(0, 1, num=100)` |
|---|---|---|
| 第三个参数 | **步长** step | **点数** num（要写 `num=` 或作为第三个位置参数） |
| 是否含终点 | **不含**（0 到 0.99） | **含**（0 到 1.0） |
| 元素个数 | 100（(1−0)/0.01） | 100 |
| 间隔 | 0.01 | 1/99 ≈ 0.0101 |
| 风险 | 浮点误差可能导致多/少一个元素 | 无此风险，推荐用于时间数组 |

老师："linspace is just a function that defines linearly separated values. You could use range, it's fine. But linspace allows us to have a start and an endpoint with that many entries. So it'll work out the gap between t."

**注意**：上面表格里两者虽然都是 100 个元素，但**间隔不同、终点不同**。如果你要求「正好 100 个点并且包含 t=1」，必须用 `linspace`。

### 6.4 索引越界
```python
Gamma_array = np.zeros((10), dtype=float)
Gamma_array[10] = 25.0     # IndexError: index 10 is out of bounds for axis 0 with size 10
```
长度 10 的数组，合法索引是 **0 到 9**。Python 索引从 0 开始，这是所有 off-by-one 错误的根源。

### 6.5 全局变量陷阱
`differential_function` 内部用了全局 `Gamma`。潜在问题：
- 如果你在别处不小心改了 `Gamma`（或者根本没定义），行为会莫名其妙；未定义时报 `NameError: name 'Gamma' is not defined`。
- 循环里如果写成 `gamma = Gamma_array[i]`（小写），全局 `Gamma` 根本没变，10 条曲线会**完全重合**——**这不会报错**，只能靠看图发现。
- 更稳妥的写法（进阶，了解即可）：
  ```python
  def differential_function(N, t, Gamma):
      return -1.0*Gamma*N
  solution = odeint(differential_function, No, t, args=(Gamma_array[i],))
  ```
  `args` 是一个**元组**，单元素时逗号不能省（`(x,)` 而非 `(x)`）。

### 6.6 Jupyter 里的「假报错」
```
Text(0.5, 0, 'time [seconds]')
```
这**不是错误**，是 Jupyter 回显 cell 最后一个表达式的返回值。解决：末尾加 `plt.show()`，或在最后一行末尾加 `;`。

### 6.7 数值解本身的陷阱（概念层面）
- **步长太大 → 误差累积**：折线轨迹逐渐偏离真实曲线，越走越远。
- **解可能变负**：物理上不可能的负浓度/负种群，是步长过大导致的外推穿越。有的 solver 支持非负约束，`odeint` 需要靠调小容差来缓解。
- **容差是速度与精度的权衡**：rtol/atol 越大越快越糙；越小越准越慢。
- **`odeint` 不是万能的**：老师明确说 "It won't work for some, or it will not give you an answer. It will struggle to get an answer. It works for our examples."——**stiff（刚性）方程**等情况可能失败。真出问题时要换 solver 或换语言。
- **能验证就验证**：拿有解析解的方程（如放射性衰变）先验证代码正确性，再用同样的框架解没有解析解的方程。

### 6.8 3D 绘图
- 忘了 `projection='3d'` → `ax.plot(x,y,z)` 会报错（2D 轴不接受三个位置参数）或 `AttributeError: 'AxesSubplot' object has no attribute 'set_zlabel'`。
- 旧写法 `fig.add_subplot(111, projection='3d')` 与新写法 `fig.add_subplot(projection='3d')` 都可以。
- `from mpl_toolkits.mplot3d import Axes3D` 在新版 matplotlib 中已非必需，但保留无害。

### 6.9 环境问题（来自课堂实况）
- Mac 上 Anaconda 安装报「already exists on Macintosh HD」→ 通常是残留的旧安装目录，需要彻底删除后重装；磁盘空间不足（2 GB）也是常见诱因（Anaconda 完整版需要好几 GB）。
- Anaconda Navigator 里 environment 无法 "open with Jupyter Notebook" → 该环境里没装 `notebook` 包。
- **最省事的绕过方案**：用 **Google Colab**（老师 GitHub 页面上有 Colab 按钮），登录 Google 账号，「click yes to everything」，体验与本地完全一致，无需安装。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Differential equation | 微分方程 | 描述某个量的**变化率**如何依赖于该量本身（和其他量）的方程 |
| ODE (Ordinary Differential Equation) | 常微分方程 | 只含对**单一自变量**（通常是时间 t）求导的微分方程 |
| Coupled differential equations | 耦合微分方程 | 多个方程互相依赖——改一个变量会影响另一个的变化率，不能分开单独积分 |
| Differentiation | 微分 / 求导 | 从函数求出它的变化率（梯度） |
| Integration | 积分 | 微分的逆运算——从变化率反推出量的实际值 |
| Analytical solution | 解析解 | 用微积分规则推导出的精确表达式（如 N(t)=N₀e^(−Γt)） |
| Numerical solution | 数值解 | 用迭代方式一步步逼近的近似解，永远不完美但可控制误差 |
| ODE solver / integrator | 常微分方程求解器 / 积分器 | 现成的程序，输入方程与初值，输出各时刻的解 |
| `odeint` | ODE 积分器函数 | SciPy 中解**初值问题**的经典函数，来自 `scipy.integrate` |
| SciPy | 科学计算库 | Python 的科学计算模块集合，含积分、优化、统计、信号处理等 |
| `scipy.integrate` | SciPy 的积分子模块 | 存放各类积分与 ODE 求解函数 |
| RHS (Right Hand Side) | 右端项 | 微分方程等号**右边**那部分；我们要写成 Python 函数的就是它 |
| LHS (Left Hand Side) | 左端项 | 微分方程等号左边，即 dx/dt 这一项 |
| Initial value problem / Boundary value problem | 初值问题 / 边值问题 | 给定起始（和/或终止）条件 + 时间区间，求区间内的解 |
| Initial conditions | 初始条件 | 各变量在 t=0 时刻的取值（如 N₀=1000、X0=5） |
| Time step | 时间步长 | 数值求解时每次沿梯度前进的时间增量；越小越准越慢 |
| Tolerance (rtol / atol) | 容差（相对/绝对） | 你能接受的数值误差上限，求解器据此自动调整步长 |
| Non-negative constraint | 非负约束 | 强制解不得为负（浓度、种群等物理量不可能为负） |
| Deterministic chaos | 确定性混沌 | 方程完全确定，但对初值极端敏感、长期不可预测的行为 |
| Butterfly effect | 蝴蝶效应 | 初始条件的极微小差异导致最终结果天差地别 |
| Lorenz system / Lorenz attractor | 洛伦兹系统 / 洛伦兹吸引子 | Edward Lorenz 提出的三耦合方程；其解在相空间中形成蝴蝶状吸引子 |
| Limit cycle | 极限环 | 解最终收敛到的闭合周期轨道（Lorenz 系统**不会**形成极限环） |
| Steady state | 稳态 | 各变量不再随时间变化的状态（Lorenz 系统**永远达不到**） |
| Lotka-Volterra model | 洛特卡-沃尔泰拉模型 | 又称捕食者-猎物方程，描述两物种相互作用的一对非线性一阶 ODE |
| Predator-Prey equations | 捕食者-猎物方程 | 同上；U=prey（猎物/兔子），V=predator（捕食者/狐狸） |
| Prey / Predator | 猎物 / 捕食者 | 被吃的一方 / 吃的一方 |
| Sensitivity (to initial conditions/parameters) | 敏感性 | 解随初值或参数变化的剧烈程度；本周要求「start to consider」这一点 |
| Numerical simulation | 数值模拟 | 用计算机迭代求解方程来模拟真实系统的演化 |
| NumPy array | NumPy 数组 | Python 科学计算的标准数据容器；`odeint` 要求用它 |
| `np.linspace` | 线性等分数组函数 | 在两端点之间生成指定**个数**的等间距值（含终点） |
| `np.arange` | 等差数组函数 | 按指定**步长**生成数组（不含终点） |
| `np.zeros` | 全零数组函数 | 预先开好指定形状的空数组，用于循环中存结果 |
| Slicing / indexing | 切片 / 索引 | `solution[:,0]` 表示「取第 0 列的所有行」 |
| Shape | 形状 | 数组各维度的大小，如 `(100, 10)` 表示 100 行 10 列 |
| Broadcasting | 广播 | NumPy 自动对齐不同形状数组的机制；形状不兼容时报 `ValueError` |
| `alpha` (matplotlib) | 透明度 | 0（全透明）到 1（不透明），轨迹重叠时调低更易读 |
| Glue language | 胶水语言 | 能方便调用其他语言的语言；Python 的强项之一 |
| Julia | Julia 语言 | 为数值计算与 AI 而生的新兴语言，ODE 求解器数量远超 Python |
| Google Colab | 谷歌 Colab | 浏览器内运行的免费 Jupyter 环境，本地装不上 Anaconda 时的替代方案 |
| Documentation | 官方文档 | 模块的说明书；最有用的文档带**可运行的代码示例** |
| Default value (of an argument) | 参数默认值 | 函数参数在你不传时自动采用的值（如 `odeint` 的 rtol/atol） |
