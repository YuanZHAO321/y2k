# Week 1 — Python 入门：为什么是 Python、环境搭建，以及数据类型 / 运算符 / 列表 / 循环

> 材料来源
> - Lecture：`Lecture1-2.md`（两讲合并的幻灯片：Introduction & why python? + setting up python and jupyter notebooks + course layout）
> - Lecture transcript：`EART11200 - 28-Jan-transcript.md`（Dave Topping 教授 2026-01-28 课堂录音转写）
> - Practical：`Practical_1.md`（对应 `Practical_1.ipynb`，含 Exercise 1–4 及参考答案）

---

## 一、本周主题

本周是 EART11200 (The Natural Scientist's Toolkit) 春季学期 **Computer Programming** 九周内容的第 1 周，属于讲师所说的 **"Vanilla Python"（原味 Python，第 1–2 周）**——即不借助任何外部模块 (module)、只用 Python "开箱即得" 的基本功能。

本周分成两条线：

1. **为什么学编程、为什么是 Python，以及怎么把 Python 跑起来**（Lecture）：编程语言存在的意义、计算史、编译型 vs 解释型语言、Jupyter Notebook / Anaconda / GitHub / OneDrive / Google Colab 环境搭建、整门课 12 周的路线图与考核方式。
2. **Python 最底层的四块砖**（Practical 1）：**数据类型 (data types)**、**算术运算符 (arithmetic operators)**、**列表与元组 (list / tuple)**、**循环 (loop)**。

讲师原话大意：这两周会有点"干"，因为它们没有直接的地球科学应用，但它们是 **"nuts and bolts"（螺丝与螺母）**——好比机械工程师必须先学会怎么用扳手。从 Week 3 起才开始"应用化"（模块与函数 → Numpy → 生命游戏 → 微分方程 → Pandas 数据 → GIS → 统计 → 机器学习）。

---

## 二、核心概念

### 2.1 为什么需要编程语言：从 idea 到 computer 的翻译链

幻灯片给出的链条是：

```
Idea  →  algorithm  →  human ／ computer
                        ↑
                  programming language
```

- **Idea（想法）**：科学家心里的一个问题。
- **Algorithm（算法）**：把想法拆成一组可执行的步骤 / 工作流 (workflow)。"algorithm"一词源自 9 世纪阿拉伯学者 **Al-Khwārizmī**（同时也是 "algebra 代数" 一词的来源）。
- **Human vs Computer**：有些算法人可以手算，但很多问题在**体力上和脑力上**都超出人的能力（讲师原话：*"there are some things that are too complex for us physically, but also mentally"*）。
- **Programming language（编程语言）**：把问题翻译成计算机能懂的形式的**中介 (intermediary)**。

选择哪种语言，讲师给了三个必问的问题：

| 问题 | 含义 | 举例 |
| --- | --- | --- |
| **How fast should it run?** | 对运行速度的要求 | 实时应急系统 / App 要"秒回" |
| **What hardware do I need?** | 目标硬件是什么 | 手机、平板、笔记本、超算集群 |
| **What and how much data?** | 数据在哪、多大、是否敏感 | 是否需要数据中心、是否涉及隐私 |

**幻灯片案例（Instagram）**：想法 = 抓取图片 (grab images) → 收集个人数据 (capture personal data) → 卖数据 (sell data) → 赚钱 (make money)。技术选型 = **Django**（一个 Python 的 web 框架 / module），因为它轻量 (lightweight)、开发快、社区大，且要在 android / iOS 上"responsive（响应迅速）"。

**反例（气候模拟）**：IPCC 报告背后是数百个模拟组成的 ensemble，跑在大型超算上，**不会用 Python**，而是 **Fortran / C**——难写，但能榨出硬件性能。讲师："我们跑 100 年的气候模拟，总不能等 100 年才出结果。"

### 2.2 计算史（考试/写作里可以引用的名字）

| 人物 / 机器 | 年代 | 贡献 |
| --- | --- | --- |
| **Al-Khwārizmī** | 约 780–850 | 引入印度-阿拉伯数字与代数概念；algorithm、algebra 两词的来源 |
| **Charles Babbage** | 生于 1791 | 建造 Analytical Engine / 计算引擎（伦敦、曼彻斯特科学博物馆有实物展出，靠摇手柄完成乘除） |
| **Ada Lovelace**（Byron 之女） | 生于 1815 | 世界上第一位程序员；提出机器"might act upon other things besides number"，甚至可以谱写复杂音乐 |
| **Alan Turing** | 1912–1954 | 用图灵机形式化了"算法"与"计算"的概念；办公室就在本楼附近 |
| **Manchester Baby (SSEM)** | 1948-06-21 首次运行 | 世界第一台**电子存储程序计算机**（可把程序存下来），由 Williams、**Tom Kilburn**、Tootill 在曼大建造；科学博物馆有复制品 |
| **Grace Hopper** | 1906–1992 | 美国海军少将；推广**机器无关的编程语言 (machine-independent programming languages)**，催生 COBOL |
| **Radhanath Sickdhar** | 1852 | 花 4 年整理 Great Trigonometrical Survey 数据，算出 Peak XV（珠峰）高度；职称就叫 **"chief computer"** |
| **West Area Computers / Katherine Johnson** | NASA，电影《Hidden Figures》 | "computer"最初指**人**；工作三件事：reading film、running calculations、plotting data |

> 讲师的落点：computing 的历史说明**软件开发正在被"民主化" (democratized)**——不再是"只有黑板前那位科学家才懂"的领域，任何人都能上手。

### 2.3 为什么选 Python

- **生态系统 (ecosystem) 极强**：Python 核心之上可以按需安装模块 (module)。课程会用到：
  - `SciPy`（Scientific Python，含微分方程求解器）
  - `Matplotlib`（绘图）
  - `Pandas`（读数据）
  - `Numpy`（数值数组，Week 3）
  - `sklearn` / scikit-learn（机器学习）
  - `GeoPandas`（GIS 地理信息，Week 7）
  - `Django`（web app）
- **高层语言 (high-level)**：框架替你做掉大量底层工作；相对地 **C / C++ / C#** 是 **低层语言 (low-level)**，要写更多才能得到想要的东西，但更快。**有趣的事实：Python 本身很大一部分是用 C 写的，Python 相当于盖在 C 上的一层。**
- **成熟 (mature)**：1990 年代末问世，社区极大——"你遇到的任何问题，都有人已经解决过"。**Stack Overflow** 是主要的问答平台。
- **技能可迁移 (transferable)**：学完可以切换到别的语言。
- **平台通用**：Mac / Windows / Linux / 甚至平板都能跑。

对比表（讲师口述）：

| 语言 | 定位 |
| --- | --- |
| C / C++ / C# / Objective-C | 最老的一批，"低层"库；追求极致性能（如 F1 赛车控制软件） |
| Java / PHP | web 开发；通信行业常用 |
| Perl | web / 桌面应用 |
| **Fortran** | 类似 C；**所有气候模型都是 Fortran 写的**——讲师担忧"以后还有谁看得懂这些气候模型？"（本课不教 Fortran） |
| **Julia** | MIT 出品，只有 5–7 年历史，但更快；讲师预测"约 10 年后能和 Python 并驾齐驱" |
| **Matlab** | 十年前很流行，大学里仍在用；与 Python 长得很像但有微妙差别，容易混淆 |
| **Python** | 全能选手：数值建模、数据分析、用户界面、web、机器学习 |

### 2.4 编译型 (compiled) vs 解释型 (interpreted) 语言

这是本周最重要的**概念性**知识点。

```
编译型语言 (C++ / FORTRAN)：
    Source code  →  Compiler  →  machine code  →  output

解释型语言 (Python / JavaScript)：
    Source code  →  Interpreter  →  output
```

- **Interpreter（解释器）**：一个"翻译官"，把我们写的人类可读代码，边读边翻译成 **machine code（机器码）**并执行。我们只要点 Run，结果就回来了。
- **Compiler（编译器）**：需要我们自己参与一部分中间步骤——告诉编译器用哪块硬件、哪部分内存。更麻烦，但性能更好。
- **为什么 Python 好移植**：因为不依赖某台特定机器编译出的产物，Mac 上写的 Python 拿到 Windows 上照样跑；Fortran 就没这么容易。
- **本课不会感受到速度差异**：我们的程序要么"一眨眼"跑完，要么一两分钟。

> **Syntax（语法）定义**（幻灯片原文）：*"The syntax of a programming language is the set of rules that create structurally allowed programs."* —— 语法就是**决定哪些程序在结构上是被允许的那套规则**。学 Python 就是学这套规则。讲师补充：他喜欢 Python 的一点是它**强迫你写干净的代码 (clean code)**，写得不干净它就直接报错（指后面要讲的缩进规则）。

### 2.5 怎么运行 Python：三条路

| 方式 | 载体 | 形态 |
| --- | --- | --- |
| **personal computer** | 自己的笔记本 | interactive shell / command prompt / terminal——装好后直接敲 `python` 就打开一个 shell，可当计算器用，但功能有限 |
| **server** | 大学集群 | command line interpreter + source code |
| **web service** | 云端 | **Jupyter Notebook**：virtual lab book + source code |

**本课采用：大学集群上的 Anaconda + Jupyter Notebook；备选 Google Colab。**

- 讲师**不推荐**只在自己笔记本上做课程内容：笔记本坏了又没备份，尤其临近考核期会很惨。

### 2.6 Jupyter Notebook

- 由一个非营利组织维护，宗旨是"develop open-source software, open-standards, and services for interactive computing across dozens of programming languages"。
- **名字来源**：**Ju**lia + **Py**thon + **R** 三种核心语言；同时致敬伽利略记录木星 (Jupiter) 卫星的笔记本。
- **本质**：*"像一本实验记录本 (lab notebook)，你可以把笔记和'做实验'（跑代码）写在一起。"*
- **对比传统做法**：以前是"打开文本编辑器 → 写代码 → 编译 → 崩了 → 回去改 → 再来"，效率很低；Notebook 让你**边写边跑**，还能把生成的图直接嵌进去。
- **对考核的意义**：最终作业就是一份 Jupyter Notebook，等于一份**迷你报告 (mini report)**——可以把代码块折叠隐藏，只留文字和图，交给不关心代码的人看，看起来就像专业报告。
- Notebook 也能跑 Julia 和 R（同学们已经用过 RStudio；RStudio 是 R 的专用环境，但 R 也能在 Notebook 里跑）。

### 2.7 环境搭建（Anaconda / GitHub / OneDrive / Colab）

**Anaconda Python**（https://www.anaconda.com/products/individual，安装时全部接受默认选项）

- 一个 Python **发行版 (distribution)**：不只是"纯 Python"，还打包了课程需要的整个模块生态。
- **注意**：Mac 自带的 Python **不是** Anaconda Python，仍需另装。
- 大学所有集群机器上都已装好。
- Anaconda 的杀手锏是 **environment（虚拟环境）**——讲师称之为 **"virtual laboratory / virtual session"**：可以创建、关闭，互不影响。实践课前 20 分钟就是给自己的 environment 加装几个额外模块（读数据 / 统计 / 机器学习用）。

**集群机器第一次登录的三步**（幻灯片，详细步骤见 Blackboard 上的 PDF）：

1. Create environment（创建环境）
2. Get class content（拉取课程内容）
3. Link and store class content（链接并保存课程内容）

**第二次及以后只需两步**：1) load environment 2) get class content。

**GitHub**

- 全球通用的**代码分享平台**。讲师把全部课程内容公开发布在他的 GitHub 页面上（Blackboard 上有链接）。
- 讲师强调它**不只是技术工具，更像一份"数字 CV"**：在 AI 时代大家担心代码无法复现 / 无法共享，GitHub 解决了这个问题（还能附上 license 授权协议）。对找工作和申请研究生都有帮助。

**OneDrive**

- 每位学生有 **1 TB** 存储。坐在任何一台校内机器上都可以把 OneDrive 链接过去。
- 流程：**从 GitHub 把课程内容拉到你的 OneDrive** → 每周直接用。好处是自动备份 + 多副本 + 可以在不同机房之间随便换机器，也能链接到自己的电脑在课外继续做。

**Google Colab（Google Colaboratory）**

- 任何有 Google 账号的人都能免费用；每次开会话都能分到一块 **GPU（显卡）**，足以跑机器学习库。只要有网就能用。
- 讲师 GitHub 页面上有一个按钮，一键把课程内容装到你的 Google Drive 并在 Colab 里打开。
- 讲师建议：**即使你用大学集群，也去玩一玩 Colab**——因为这证明你会用**云计算 (cloud compute provision)**，Colab 底下还接着 Google 的一堆服务，甚至能摸到高性能计算。
- 但他更推荐大学集群，理由是 OneDrive 的备份更让人安心（"我相信 Google 不会跑路，但万一呢"）。

### 2.8 数据类型 (data types)：int / float / complex

Python 官方文档定义了三种数值类型：

| Type | Format（写法） | Description |
| --- | --- | --- |
| `int`（Integer 整数） | `a = 10` | 有符号整数 (Signed Integer)。**精度无限**——位数可以一直涨，只受机器内存限制 |
| `float`（Floating point 浮点数） | `a = 45.67` | 浮点实数，通常用**双精度 (double precision)** 实现 |
| `complex`（复数） | `a = 3.14J` | 有实部和虚部，各自都是一个 float。**本课只在这里出现这一次** |

```python
# Whenever you see a hash symbol [#] in Python code, this represents a comment which is ignored by the interpreter.
# 只要看到井号 #，后面的内容就是注释 (comment)，解释器 (interpreter) 完全忽略它。
# 注释是写给人看的：作者留下的说明，方便别人（和三个月后的自己）看懂这段代码。

x = 2.3      # float —— 有小数点，Python 自动判定为浮点数
y = 4        # integer —— 没有小数点，判定为整数
z = 5 + 6j   # complex —— j 表示虚数单位；本课第一次也是最后一次用复数
```

**关键点：Python 是"动态类型"的**——你**不需要事先声明变量是什么类型**（Notebook 原文：*"I'm not defining what each variable is expecting in the first place... I do not have to tell the interpreter what data type to expect in, say, x"*）。这与 C / Fortran 必须先写 `int x;` 完全不同。

**运行上面这段代码，屏幕上什么都不会出现**——因为赋值 (assignment) 本身不产生输出。这是初学者常见的困惑："我点了 Run，怎么没反应？"——没反应就是正常的，值已经存进变量了。

要看到值，得用 `print()`：

```python
# Just adding comment here for the sake of it...
print("x =", x)   # print 可以接收多个参数，用逗号隔开，输出时自动用一个空格连接
print("y =", y)
print("z =", z)
```

```
x = 2.3
y = 4
z = (5+6j)
```

**输出解读**：
- `x = 2.3`：逗号让 `"x ="` 和 `2.3` 之间自动多了一个空格。
- `z` 打印成 `(5+6j)`——**复数会带上括号**，这是 Python 展示复数的固定格式，不是错误。

用 `type()` 查类型：

```python
print("The data type of x is",type(x))
print("The data type of y is",type(y))
print("The data type of z is",type(z))
```

```
The data type of x is <class 'float'>
The data type of y is <class 'int'>
The data type of z is <class 'complex'>
```

**输出解读**：`<class 'float'>` 里的 "class" 是 Python 内部的说法（一切类型本质上都是 class），你只需要看引号里的 `float` / `int` / `complex`。**判断结果是否正确**：`x = 2.3` 有小数点 → 应当是 `float`；`y = 4` 无小数点 → 应当是 `int`。对上了就没问题。

### 2.9 `float` 的特殊写法

| Property | Syntax |
| --- | --- |
| 可以带正负号 | `"+ -"` |
| 可以表示无穷 | `"Infinity"` / `"inf"` |
| 可以表示"非数" (Not a Number) | `"nan"` |

```python
>>> float('+1.23')       # 字符串转浮点，正号可省略
1.23
>>> float('   -12345')   # 前面有空格也没关系，float() 会自动去掉首尾空白
-12345.0                 # 注意：结果带 .0，说明它已经是 float 而不是 int
>>> float('1e-003')      # 科学计数法：1 × 10^(-3)
0.001
>>> float('+1E6')        # 大写 E 和小写 e 等价：1 × 10^6
1000000.0
>>> float('-Infinity')   # 负无穷
-inf
>>> float('NaN')         # Not a Number（常用于表示缺测数据）
nan
```

> `>>>` 是 Python **交互式 shell 的提示符 (prompt)**。在 Notebook 里你**不要**把 `>>>` 抄进去，只写后面那一句。
>
> **科学计数法记法**：`2.5e2` = 2.5 × 10² = 250。大小写 e / E 都行。这在地球科学里极常用（普朗克常数、光速、浓度等）。
>
> **`nan` 的科学意义**：真实观测数据里的缺测值 (missing value) 常常就是 `nan`；后面几周处理气象 / 空气质量数据时会大量遇到。

### 2.10 算术运算符 (arithmetic operators)

| Operation | Result |
| --- | --- |
| `x + y` | x 与 y 之和 |
| `x - y` | x 与 y 之差 |
| `x * y` | x 与 y 之积 |
| `x / y` | x 除以 y 的商 |
| `abs(x)` | x 的绝对值 / 模 |
| `int(x)` | 把 x 转成整数 |
| `float(x)` | 把 x 转成浮点数 |
| `pow(x, y)` | x 的 y 次方 |
| `x ** y` | x 的 y 次方（与 `pow` 等价，更常用） |

### 2.11 列表 (list)、元组 (tuple)、字典 (dictionary)

Python "开箱即得"的三种存储集合的方式：**list、tuple、dictionary**。（本周只细讲 list 和 tuple；dictionary 只提了名字。）

> 对于**数值计算**，真正会用的是 **Numpy**（Practical 3 引入）——因为它专门为此优化过，比"非 Numpy"的做法**快得多**。但 list 仍然会一直出现。

**list 与 tuple 的共同点**：
- 都**按顺序**存一组元素 (store a collection of items sequentially)
- 都能存**任意数据类型**（数字、字符串都行，还能混装）
- 都能**通过索引 (index) 访问**任一元素

**关键区别**：

> **Lists are mutable while tuples are immutable.**
> 列表是**可变的 (mutable)**，元组是**不可变的 (immutable)**——list 的值可以改，tuple 的值不能改。

**语法区别**：list 用**方括号 `[]`**，tuple 用**圆括号 `()`**。

**⚠️ 索引规则（红色警告框）：Python 的索引从 0 开始 (Python indexes start at 0)。** 所以第 1 个元素是 `[0]`，第 4 个元素是 `[3]`。

```python
# First let's create an identical list and tuple containing names of places
# Lists use square brackets, whereas tuples use parentheses
# 先造一个内容完全相同的 list 和 tuple，装的是首都名（字符串 string）

list_capitals  = ['London','Paris','Rome','Ankara']   # 方括号 → list
tuple_capitals = ('London','Paris','Rome','Ankara')   # 圆括号 → tuple

# 访问单个元素用同样的方括号记法，记住索引从 0 开始，所以第一个元素是 [0]
list_capitals[0]
# 在 Notebook 里，一个单元格的最后一行如果是个表达式，它的值会自动显示出来（不需要 print）
```

```
'London'
```

**输出解读**：注意输出是 `'London'`（**带引号**）。这是 Notebook 自动回显表达式值时的形式，引号提示你这是一个**字符串 (string)**。如果用 `print()` 打印，引号就不会出现。

```python
# Now lets access the 4th element of both the list and tuple.
# 访问第 4 个元素——索引是 3，不是 4！

print("4th entry in the list is ",list_capitals[3])
print("4th entry in the tuple is ",tuple_capitals[3])
```

```
4th entry in the list is  Ankara
4th entry in the tuple is  Ankara
```

**输出解读**：两个都是 `Ankara`，说明 list 和 tuple 的**读取**方式完全一样。注意 `Ankara` 前面有**两个空格**——一个来自字符串末尾自己打的空格，一个来自 `print` 的逗号分隔。

### 2.12 mutable vs immutable：一个会报错的实验

Notebook 特意设计了一段**会报错**的代码，让学生亲眼看到区别：

```python
# Change the 2nd entry to 'Beijing'
# 试着把第 2 个元素改成 'Beijing'（索引是 1）

list_capitals[1] = 'Beijing'   # note the index value and the [] bracket notation
print("full list array = ",list_capitals)

tuple_capitals[1] = 'Beijing'  # 对 tuple 做同样的事——这一行会炸
print("full list array = ",tuple_capitals)
```

```
full list array =  ['London', 'Beijing', 'Rome', 'Ankara']

---------------------------------------------------------------------------

TypeError                                 Traceback (most recent call last)

Cell In[9], line 7
      4 # print full array to the screen
      5 print("full list array = ",list_capitals)
----> 7 tuple_capitals[1] = 'Beijing' # note the index value and the [] bracket notation
      8 # print full array to the screen
      9 print("full list array = ",tuple_capitals)

TypeError: 'tuple' object does not support item assignment
```

**报错完整解读（这是本周最重要的调试训练）**：

1. **第一行 `full list array = [...]` 成功打印了** —— 说明 list 的修改是成功的，`'Paris'` 已经变成 `'Beijing'`。**报错发生在报错之前的代码依然会执行**，这是理解 Notebook 行为的关键。
2. **`Traceback (most recent call last)`** —— "回溯"，Python 给出的错误现场报告。读法是**从下往上**看：最下面一行是错误的**类型和原因**，往上是出错的**位置链条**。
3. **`Cell In[9], line 7`** —— 出错在第 9 号执行的单元格的第 7 行。
4. **`----> 7 tuple_capitals[1] = 'Beijing'`** —— 箭头 `--->` **精确指出出错的那一行**。看报错先看这个箭头。
5. **`TypeError: 'tuple' object does not support item assignment`** ——
   - **`TypeError`**：错误类型，意为"你对这个类型做了它不支持的操作"。
   - **`'tuple' object does not support item assignment`**："tuple 对象不支持元素赋值"——正是 immutable 的技术表述。
6. **第二个 `print` 没有执行** —— 因为报错会**中止**整个单元格的后续执行。

**推论**：不只是"改不了值"，**tuple 的长度也改不了**（不能增删元素），而 list 可以。

### 2.13 `.append()`：给 list 加元素

```python
>>[Name of list].append()
```

```python
# Append another city to our list as follows, and then print the new array
# 用 .append() 在列表末尾追加一个新元素
list_capitals.append('Moscow')
print("full list array = ",list_capitals)
```

```
full list array =  ['London', 'Beijing', 'Rome', 'Ankara', 'Moscow']
```

**语法说明**：
- `.append()` 是**方法 (method)**，写法是 `列表名.append(要加的东西)`——点号 `.` 表示"这个列表自己的一个动作"。
- **`.append()` 只接受一个参数**，每次只能加一个元素。要加两个就写两行。
- **`.append()` 是"原地修改"**：它直接改变原列表，**返回值是 `None`**。所以**绝对不要写 `list_capitals = list_capitals.append('Moscow')`**——那样列表会变成 `None`，是初学者的经典陷阱。
- 新元素永远加在**末尾**，索引是"原长度"。原来 4 个元素（索引 0–3），加完 `Moscow` 的索引就是 **4**。

### 2.14 循环 (loop) 与白空格规则

**为什么需要循环**：如果只有 3 个城市，可以手写三行 `print`：

```python
print("first entry is",list_capitals[0])
print("second entry is",list_capitals[1])
print("third entry is",list_capitals[2])
#...and so on
```

```
first entry is London
second entry is Beijing
third entry is Rome
```

但真实数据动辄上万条（讲师提到 Week 8 的空气质量数据有 **18,000 个数据点**），手写完全不可行。**循环**让这件事自动化。

**⚠️ 白空格规则 (White space rule)（红色警告框，Python 的根本要求之一）**：

> **Whenever a series of commands, or command, is terminated by a colon `:`, the following line should be indented.**
> 只要一条（或一串）命令以**冒号 `:`** 结尾，**下一行就必须缩进 (indent)**。典型场景包括循环和函数定义。

Notebook 原文强调：*"obeying the white space rule is a fundamental requirement in Python"*——**遵守空白规则是 Python 的根本要求**。这也呼应讲师在 lecture 里说的："Python 强迫你写干净的代码，写得不干净它就报错。"

**第一个 for 循环**：

```python
# Example loop to print entries in our list of capital cities
for step in range(7):          # 冒号 : 结尾 → 下一行必须缩进
    # 'step' 这个变量名是我随便取的，叫什么都行；
    # 关键是：这个由循环定义出来的变量，被拿去做数组的索引
    print(list_capitals[step])
```

```
London
Beijing
Rome
Ankara
Hanoi
Manchester
Edinburgh
```

**逐部分拆解 `for step in range(7):`**：

| 成分 | 含义 |
| --- | --- |
| `for` | 关键字 (keyword)，宣告"开始一个循环" |
| `step` | **循环变量 (loop variable)**，名字任取（可叫 `i`、`n`、`city_index`…）。每轮循环它会自动取到序列里的下一个值 |
| `in` | 关键字，"从……当中取" |
| `range(7)` | 生成整数序列 **0, 1, 2, 3, 4, 5, 6**（**共 7 个数，从 0 开始，不含 7**） |
| `:` | 冒号，宣告"循环体从下一行开始" |
| 缩进的那一行 | **循环体 (loop body)**，会被执行 7 次 |

**`range()` 函数**（Notebook 原文：函数会在 Practical 3 正式讲）：
- 作用：生成一串定义循环迭代次数的数字。
- 默认基于**整数**；可以传可选参数改变行为（本周不讲）。
- `range(7)` → 0 到 6，**正好对应 7 个元素的列表的全部合法索引**。这个"个数 = range 的参数"的对应关系，正是因为**索引从 0 开始**。

**打印循环变量本身，看清楚发生了什么**：

```python
# The following loop counts through a fixed number of integer values using the range function.
# 循环次数的上限是根据"我们知道数组有多大"来定的。
# 如果你让 Python 打印超出数组边界的元素，就会报错。Try it!（Notebook 原文鼓励你去试）

for step in range(7):
    print(list_capitals[step])
    print("the value of step is ", step)   # 同样缩进 → 同属循环体，每轮都执行
```

```
London
the value of step is  0
Beijing
the value of step is  1
Rome
the value of step is  2
Ankara
the value of step is  3
Hanoi
the value of step is  4
Manchester
the value of step is  5
Edinburgh
the value of step is  6
```

**输出解读**：城市名和 step 值**交替出现**，说明循环体里的两行是**在同一轮循环内按顺序执行**，而不是"先跑完所有城市再跑所有 step"。`step` 从 0 递增到 6，共 7 轮——完全符合 `range(7)`。

### 2.15 用循环生成数值数组

任务：造两个各 100 个元素的列表 `x` 和 `y`。`x` 是 1 到 100 的整数，`y = x * 3.4`。

```python
# Create two empty lists. We are going to fill these in the loop
x = []   # 空列表：一对什么都不放的方括号。这是"先开一个空容器，待会往里装"
y = []

# Create a loop that cycles through 100 values, then implement the equation defined above
for step in range(100):          # step 依次取 0, 1, 2, ..., 99（共 100 轮）

    # x 要从 1 到 100，而 step 是从 0 到 99，所以要 +1 做偏移
    x.append(step+1)
    # 第一轮：step = 0，于是往 x 里放进 1

    # 接着定义对应的 y 值
    y.append(x[step]*3.4)
    # 拆成三步理解：
    # 1) 用 .append() 往 y 里追加一个值
    # 2) 用 step 作索引，从 x 里取出刚刚存进去的那个值 —— x[step]
    # 3) 套用公式 y = x * 3.4

# 缩进结束 → 循环结束。下面的代码只执行一次。
print("The 1st element of x is ",x[0])
print("The 1st element of y is ",y[0])

print("The 2nd element of x is ",x[1])
print("The 2nd element of y is ",y[1])

print("The 3rd element of x is ",x[2])
print("The 3rd element of y is ",y[2])

print("The 4th element of x is ",x[3])
print("The 4th element of y is ",y[3])

# What about the 81st element of x and y?
print("The 81st element of x is ",x[80])   # 第 81 个 → 索引 80
print("The 81st element of y is ",y[80])
```

```
The 1st element of x is  1
The 1st element of y is  3.4
The 2nd element of x is  2
The 2nd element of y is  6.8
The 3rd element of x is  3
The 3rd element of y is  10.2
The 4th element of x is  4
The 4th element of y is  13.6
The 81st element of x is  81
The 81st element of y is  275.4
```

**输出解读与正确性检验**：
- `x[0] = 1`：`step=0` 时 `append(0+1)` → 1。✓ 偏移做对了。
- `y[0] = 3.4 = 1 × 3.4`。✓
- `x[80] = 81`：索引 80 对应第 81 个元素，值是 81。**"第 n 个 = 索引 n−1 = 值 n"** 这个三重对应是本练习最容易绕晕的地方。
- `y[80] = 275.4 = 81 × 3.4`。✓ 心算验证：81 × 3.4 = 275.4。**这就是"如何判断结果对不对"的方法——挑一两个点手算核对。**

**为什么 `x[step]` 在这一轮就已经存在？** 因为在同一轮循环里，`x.append(step+1)` 写在前面，已经把索引为 `step` 的位置填好了；紧接着 `x[step]` 就能取到它。**顺序不能颠倒**——如果把两行调换，第一轮就会因为 `x` 还是空的而抛出 `IndexError`。

---

## 三、语法速查与函数表

### 3.1 本周语法结构

| 名称 | 作用 | 用法示例 | 注意事项 |
| --- | --- | --- | --- |
| `#` 注释 (comment) | 写给人看的说明，解释器完全忽略 | `x = 2.3  # float` | 只能到行尾；Notebook 里注释是"未来的自己"的救命稻草 |
| `=` 赋值 (assignment) | 把右边的值存进左边的变量 | `temperature = 298` | **不是数学等号**；`=` 是赋值，`==` 才是比较（下周） |
| 变量命名 | 给数据起名字 | `starting_temperature = 273.14` | 名字本身"不重要"（Notebook 原话：是风格与文档问题），但**区分大小写**：`Price` ≠ `price` |
| `[]` 列表字面量 | 建立一个 list | `x = []` / `['London','Paris']` | 空列表 `[]` 用于"先开容器再填" |
| `()` 元组字面量 | 建立一个 tuple | `('London','Paris')` | 建好之后不能改也不能增删 |
| `[i]` 索引 (indexing) | 取出第 i+1 个元素 | `list_capitals[3]` | **索引从 0 开始**；越界 → `IndexError` |
| `for ... in range(n):` | for 循环 | `for step in range(7):` | 冒号结尾，下一行**必须缩进** |
| 缩进 (indentation) | 界定代码块 | 循环体统一往右缩进 | 混用空格/Tab 或缩进不齐 → `IndentationError` |
| 科学计数法 | 写极大 / 极小的数 | `3.0e8` / `6.62607004e-34` | `e` 与 `E` 等价；`2.5e2` = 250 |

### 3.2 本周函数与方法

| 名称 | 作用 | 参数 | 返回值 | 用法示例 | 注意事项 |
| --- | --- | --- | --- | --- | --- |
| `print()` | 把内容显示到屏幕 | 任意多个，逗号分隔 | `None` | `print("x =", x)` | 逗号分隔的多项之间**自动补一个空格** |
| `type()` | 查询对象的数据类型 | 一个对象 | 类型对象 | `type(x)` | 输出形如 `<class 'float'>` |
| `float()` | 转成浮点数 | 数字或字符串 | float | `float('+1E6')` → `1000000.0` | 能识别 `inf` / `nan` / 前导空格 |
| `int()` | 转成整数 | 数字或字符串 | int | `int(3.9)` → `3` | 对小数是**截断**不是四舍五入 |
| `abs()` | 绝对值 / 模 | 数字 | 同类型 | `abs(-3.4)` → `3.4` | 复数返回模长 |
| `pow(x, y)` | x 的 y 次方 | 两个数字 | 数字 | `pow(2,3)` → `8` | 与 `**` 等价，日常更常用 `**` |
| `range(n)` | 生成 0 到 n−1 的整数序列 | 整数 n | 可迭代序列 | `range(7)` → 0..6 | **不含 n**；配合 list 长度使用 |
| `列表.append()` | 在列表末尾追加一个元素 | 一个元素 | `None`（原地修改） | `list_capitals.append('Moscow')` | **绝不能写 `lst = lst.append(x)`**；tuple 没有这个方法 |

### 3.3 算术运算符速查

| 运算符 | 作用 | 示例 | 结果 |
| --- | --- | --- | --- |
| `+` | 加 | `2.4 + 7.5` | `9.9` |
| `-` | 减 | `4.7 - 3.4` | `1.3000000000000003`（浮点误差） |
| `*` | 乘 | `3.4 * 12.5` | `42.5` |
| `/` | 除 | `12 / 2.3` | `5.217391304347826` |
| `**` | 幂 | `2.3 ** 4.5` | `42.43998894277659` |

### 3.4 图表

**本周无绘图内容。** 讲师提到绘图要用 **Matplotlib** 模块，会从 Week 3（模块与函数）开始出现，Week 4 的 Conway's Game of Life 会有动画，Week 6/7 会在地图上画火山与洪水风险，Week 8 会画 diurnal profiles（日变化曲线）。

---

## 四、课堂补充（transcript 独有内容）

以下是**只在录音转写里出现**、幻灯片和 Notebook 上没有的内容：

### 4.1 讲师自我介绍与课程定位

- **Dave Topping**，Earth and Environmental Sciences 系教授，主攻**数值模型**，目前重心在 **AI 与机器学习**。1998 年读的物理学位，自称"脑子还停在 90 年代"。
- 他讨厌待在实验室（"I hate being in a lab... I break things too easily"），认为编程的优点是**门槛低、可自学、可在家做**，不像实验室需要专门的仪器与场地。
- 开场做了小调查："有人写过代码吗？"有同学答 Python。他提到自己 8 岁的女儿已经在学编程了。
- **课程是"applied（应用型）"而非"fundamental computing（计算机基础理论）"**——因为这是一个应用学位。我们不会讲计算机为什么能工作、编程语言底层如何实现。

### 4.2 关于 AI / LLM 的明确态度（重要！关系到你能怎么用 ChatGPT）

- **"ChatGPT is fine.. I use it!"**（幻灯片也写了）。讲师说他两年前开始用，早期"总是产生错误"，现在好很多，每月都在进步。
- **Stack Overflow 的转变**：2022 年他上这门课时，Stack Overflow **封禁了 GPT**，因为它给的答案是错的；到 2023 年，GPT 已经被整合进这个最主流的代码分享平台。
- **Week 9 会专门讲"如何向 LLM 提问才能拿到你要的 Python 代码"**——有策略可循 (*"There are strategies for asking the question"*)。
- 他的现实主义论证：**"When you go into the workforce, you will probably end up using something with an LLM sat behind it anyway. So I don't think there's any point in hiding it."**
- 学术界目前对此很纠结（可复现性、代码共享问题），这也是他强调 GitHub 的原因之一。

### 4.3 时事：Nvidia 一夜蒸发 5000 亿美元

讲师在课上提到"昨天的新闻"：**Nvidia 市值一夜被抹掉 5000 亿美元**，原因是一支中国研究团队发布了新的大语言模型，找到了**不需要 Nvidia 硬件的、效率高得多的训练方法**。他的教学点是：

> **硬件和语言一直在变，但学好基础就能保持敏捷 (agile)。** *"Things are changing all the time, but it's safe for us to keep learning what we're learning because you can be agile to that."*

### 4.4 曼彻斯特本地的计算史彩蛋

- **BBC Micro**（幻灯片里那张有"闪亮壁纸和假砖墙"背景的照片）是讲师童年的第一台电脑。他爸爸本来该拿这笔钱装新厨房，结果买了电脑，为此惹了大麻烦。
- **BBC Micro 的共同发明人至今仍在曼大工作**；同一位也是 **ARM 芯片的共同创造者**——ARM 芯片在你所有的手机和平板里，**比 Intel 芯片省电得多**。
- **Alan Turing** 的办公室就在博物馆侧门附近，你大概走过很多次。
- **Manchester Baby 的复制品**在科学博物馆入口右转，有工作人员在维护运行。
- **Kilburn Building**（以 Tom Kilburn 命名）就在附近。
- Babbage 的计算引擎实物在伦敦（曼彻斯特科学博物馆偶尔展出）。

### 4.5 Boston Dynamics 与 Nvidia Jetson

- 课上放了 **Boston Dynamics 机器人**的视频（讲师评价："amazingly terrifying, quite exciting at the same stage"）。
- 关键点：这些机器人的"大脑"就是一块小主板 + 一块 **Nvidia 的芯片**跑机器学习库，**可以用 Python 编程**。
- 你现在能买到 **Nvidia Jetson** 开发板，开箱就能通过 webcam 做目标检测 (object detection)——"军方用来从飞机上侦测目标的那类技术"。
- 落点：**你今天学的 Python，将来可以迁移到这类机器上。**

### 4.6 IBM 与"personal computer"这个词的由来

讲师讲 Grace Hopper 的"机器无关语言"时补了个故事：80 年代有过一场大战，**大家联合起来对抗 IBM 对生态的垄断**（IBM 想让软件只能在 IBM 机器上跑），**这就是为什么我们今天叫它"personal computer"而不是"IBM"**。

### 4.7 与其他课程的联动

- Matthew 那门课（微积分 / 微分方程）教的东西，**Week 5 会用 Python 几行代码解出来**——"作为科学家，我们为什么要手算一切？我们也算不完。"
- 微分方程是理解地球系统与气候走向的根基，**根本不可能手算**。
- 同学们已经用过 **RStudio**；Notebook 也能跑 R。
- 三年级做毕业项目时会发现很多**基于 Python 的项目**可选；二年级教环境建模的同事既有编译型语言模型也有 Python 模型。

### 4.8 实践课当天的安排（transcript 独有）

- 讲师**不会**在机房站着逐条念安装步骤，只给总体概览；**请严格照 Blackboard 上的 PDF 操作**。
- 有 **7 位 GTA（助教）**会挨个巡视，确保每个人都装好。
- 实践课**前 20 分钟**用来给自己的 Anaconda environment 加装几个额外模块：**读数据、统计、机器学习**用。
- **Blackboard 页面结构**：每周有一段**两分钟的总结视频**（说明本周该带走什么）+ 一份幻灯片副本 + 指向讲师 GitHub 的链接。
- **从第二周起流程简化**：只需重新链接 OneDrive，然后在 Anaconda 里继续做内容。

---

## 五、Practical 要点

**Practical 1 — An introduction to data types, operations and loops**

**总体说明**（Notebook 开篇）：
- 本课程采用**应用式 (applied)** 学习法：从基本数值计算走到数据输入与分析。
- "我们不可能教完 Python 的一切，但能给你一套工具，让你开始自己的旅程。"
- 学编程**像学一门外语**，同时还要对底下的硬件在干什么有个大致概念。
- 课程会给你一堆 **template（模板）**，留着改、留着复用，慢慢积累成你自己的示例库。
- **不必在课堂上做完所有练习**，可以带回去继续做；`solutions` 文件夹里有全部参考答案。
- **⚠️ 找题的方法**：读完说明后，在代码块里搜 `------'INSERT CODE HERE'------`，那就是你要动手写代码的位置。

**本次目标**：
1. 理解数据类型如何表示、常用算术运算符怎么用（Exercise 1、2）
2. 数组与列表（Exercise 3）
3. 循环与条件语句（Exercise 4）

---

### Exercise 1：设置两个新变量并打印类型

**题目要求**：新建两个变量 `temperature` 和 `mass`，分别赋值 **298 Kelvin（整数 int）** 和 **3.78 Kilograms（浮点 float）**，然后把它们的数据类型打印到屏幕。

**解题思路**：
- 要得到 `int`，就**不能写小数点**：写 `298`，不能写 `298.0`（写了就变 float）。
- 要得到 `float`，值 `3.78` 本身就有小数点，天然是 float。
- 用 `type()` 取类型，塞进 `print()` 里。

**代码实现**：

```python
#------'INSERT CODE HERE'------
temperature = 298   # Kelvin —— 没有小数点，Python 判定为 int
mass = 3.78         # Kg —— 有小数点，Python 判定为 float
#------------------------------

# type(...) 取出类型；逗号把多段内容拼进同一行输出
print("The data type of temperature is",type(temperature), "and has a value of ",temperature)
print("The data type of mass is",type(mass), "and has a value of ",mass)
```

**输出**：

```
The data type of temperature is <class 'int'> and has a value of  298
The data type of mass is <class 'float'> and has a value of  3.78
```

**输出解读**：
- `<class 'int'>` 确认 `temperature` 是整数——**如果你写成了 `298.0`，这里会显示 `<class 'float'>`，就算错了。**
- `<class 'float'>` 确认 `mass` 是浮点数。
- **科学背景**：298 K ≈ 25 °C，是标准室温；Kelvin 是绝对温标，地球科学里的温度计算一律用 K，避免负数带来的麻烦。
- **注意 `print` 里注释写的是单位**（`# Kelvin`、`# Kg`）——Python **不记录单位**，单位只能靠注释和变量名来传达。这是科学计算里最重要的纪律之一。

---

### Exercise 2：用算术运算符实现四个物理公式

**题目要求**：把下列四个方程用上面表格里的算术运算符实现：

| Description | Form |
| --- | --- |
| Einstein's relativistic mass-energy relation | E = mc² |
| De Broglie Wavelength | λ = h / (mυ) |
| Ideal gas equation | PV = nRT |
| Kelvin → Celsius | °C = K − 273 |

给定常数：
- Planck's constant, h = 6.62607004 × 10⁻³⁴
- Speed of light in vacuum, c = 3 × 10⁸ m s⁻¹
- Ideal Gas constant, R = 8.205736 × 10⁻⁵ m³·atm/(K·mol)

**期望输出（题目已给，可用来自查）**：

```
The relativistic energy of an electron =  8.199e-14
The De Broglie wavelength of an eletron =  1.3697557246543088e-10
The Pressure of our ideal gas =  0.05260061405059999
The Temperature in Celsius =  25.149999999999977
```

**解题思路**：
1. 先把所有常数用**科学计数法**写成变量——这样公式行读起来就跟课本一样。
2. `E = mc²` → `m*c**2.0`。**注意运算优先级：`**` 的优先级高于 `*`**，所以 `m*c**2.0` 会先算 `c**2.0` 再乘 `m`，正是我们要的。写成 `(m*c)**2.0` 就错了。
3. `λ = h/(mυ)` → `h/(m*vel)`。**分母必须加括号**！写成 `h/m*vel` 会被解释成 `(h/m)*vel`，结果完全不同——这是本练习最经典的陷阱。
4. `PV = nRT` → 求 P，需要移项：`P = (n*R*T)/V`。
5. `°C = K − 273` → `T_celsius = T - 273.0`。

**完整代码实现**：

```python
# Constants used in equations
c   = 3.0e8         # Speed of light, [m/s]                    光速
h   = 6.62607004e-34 # Plank's constant [J s]                  普朗克常数
m   = 9.11e-31      # Mass of Electron in kg                   电子质量
T   = 298.15        # Assume temperature is 298.15 K           温度（25 °C）
R   = 8.205736e-5   # Ideal Gas Constant [m3⋅atm/ K⋅mol]       理想气体常数
V   = 1.0           # Assumed volume in ideal gas law          假设体积 1 m³
n   = 2.15          # Number of moles of gas                   物质的量
vel = 5.31e6        # Assumed velocity of electron [m/sec]     电子速度

#------'INSERT CODE HERE'------
# Einsteins relativistic mass-energy relation
E = m*c**2.0        # ** 优先于 *，先算 c 的平方；能量 [J]

# De Broglie's Wavelength
Lambda = h/(m*vel)  # 分母整体加括号！波长 [m]
                    # 变量名用 Lambda 大写开头，因为 lambda 是 Python 保留关键字

# Ideal gas equation
P = (n*R*T)/(V)     # PV = nRT 移项求 P；压强 [atm]

# Covert above equation to degrees Celsius
T_celsius = T-273.0 # 开尔文转摄氏

#------------------------------

print("The relativistic energy of an electron = ", E)
print("The De Broglie wavelength of an eletron = ", Lambda)
print("The Pressure of our ideal gas = ",P)
print("The Temperature in Celsius = ",T_celsius)
```

**输出**：

```
The relativistic energy of an electron =  8.199e-14
The De Broglie wavelength of an eletron =  1.3697557246543088e-10
The Pressure of our ideal gas =  0.05260061405059999
The Temperature in Celsius =  25.149999999999977
```

**输出逐条解读与正确性检验**：

1. **`8.199e-14`**：9.11×10⁻³¹ × (3×10⁸)² = 9.11×10⁻³¹ × 9×10¹⁶ = **8.199×10⁻¹⁴ J**。这是单个电子的静止能量，约 0.511 MeV，与物理常识吻合。**注意 Python 自动用科学计数法显示极小的数。**
2. **`1.3697557246543088e-10`**：h/(mv) = 6.626×10⁻³⁴ / (9.11×10⁻³¹ × 5.31×10⁶) ≈ **1.37×10⁻¹⁰ m = 0.137 nm**。这个尺度和原子间距同量级——正是电子衍射能被晶体观测到的物理原因。
3. **`0.05260061405059999`**：P = nRT/V = 2.15 × 8.205736×10⁻⁵ × 298.15 / 1.0 ≈ **0.0526 atm**。用 1 m³ 装 2.15 mol 气体，压强当然远低于 1 atm，合理。
4. **`25.149999999999977`** ⚠️：数学上 298.15 − 273.0 = **25.15**，但 Python 给出 `25.149999999999977`。
   - **原因**：**浮点数精度 (floating-point precision)**。计算机用二进制存小数，像 0.15 这样的十进制小数在二进制里是无限循环的，只能截断，于是留下极小的误差（约 2×10⁻¹⁴）。
   - **这不是 bug，是所有编程语言的共性**。同样的现象在前面 `-3.4 + 4.7 = 1.3000000000000003` 里也出现过。
   - **实践含义**：**永远不要用 `==` 直接比较两个浮点数是否相等**（下周讲条件语句时会遇到）；要比较时应判断"差的绝对值是否小于某个很小的容差"。

**关于类型自动提升**（Notebook 在除法例子后的说明）：

> *"did you notice we actually asked Python to divide an integer by a float? This is ok in the sense that Python will, by default, change the type of the variable with the lowest precision to the same as the highest."*

即 `Price = 12`（int）除以 `weight = 2.3`（float），Python **自动把精度低的一方提升为精度高的类型**，结果是 float `5.217391304347826`。**你不需要手动转换。**

---

### Exercise 3：往列表里追加两项并修改已有项

**题目要求**：在现有的 `list_capitals` 后面**按顺序**追加：
- Manchester
- Edinburgh

然后把第 5 个元素（当前是 `Moscow`）改成 `Hanoi`。

**期望输出**：

```python
full list array =  ['London', 'Beijing', 'Rome', 'Ankara', 'Hanoi', 'Manchester', 'Edinburgh']
```

**解题思路**：
- 此时列表是 `['London', 'Beijing', 'Rome', 'Ankara', 'Moscow']`（5 个，索引 0–4）。
- `.append()` **一次只能加一个**，所以要写两行；顺序不能反，否则 Manchester 和 Edinburgh 会调换。
- "第 5 个元素" → **索引 4**，直接赋值 `list_capitals[4] = 'Hanoi'`。
- **注意期望输出里 Hanoi 在第 5 位、Manchester 第 6、Edinburgh 第 7**——说明"改第 5 个"是**替换**而不是插入，列表长度从 5 变 7（只因为两次 append）。

**代码实现**：

```python
#------'INSERT CODE HERE'------
list_capitals.append('Manchester')   # 追加到末尾 → 索引 5
list_capitals.append('Edinburgh')    # 再追加 → 索引 6
list_capitals[4] = 'Hanoi'           # 索引 4 = 第 5 个元素，把 Moscow 覆盖掉
#------------------------------

print("full list array = ",list_capitals)
```

**输出**：

```
full list array =  ['London', 'Beijing', 'Rome', 'Ankara', 'Hanoi', 'Manchester', 'Edinburgh']
```

**输出解读**：
- 打印整个 list 时，Python 会显示**方括号 + 逗号分隔 + 每个字符串带单引号**——这是 list 的标准展示形式，据此可以一眼确认它确实是个 list（不是 tuple 的圆括号）。
- 长度从 5 变成 7 ✓；`Moscow` 消失、`Hanoi` 出现在同一位置 ✓；Manchester 在 Edinburgh 之前 ✓。
- **注意 `London` 后面是 `Beijing` 而不是 `Paris`** ——因为前面的 mutable 演示已经把索引 1 改掉了。**这说明 Notebook 的单元格是有状态的 (stateful)：前面跑过的代码会影响后面的结果。**

**⚠️ 顺序陷阱**：如果你先执行 `list_capitals[4] = 'Hanoi'` 再 append，结果其实是一样的（因为索引 4 在两次 append 之前之后都指向同一个位置）。但如果你**重复运行这个单元格**，`Manchester` 和 `Edinburgh` 会被再次追加，列表变成 9 个元素！**这是 Notebook 里最常见的坑：反复 Run 一个含 `.append()` 的单元格会不断累积。** 解决办法是回到定义 `list_capitals` 的那个单元格重新跑一遍，或者 Restart Kernel 后从头顺序执行。

---

### Exercise 4：用循环实现 Y = X^2.8

**题目要求**：写一个循环实现函数

$$ Y = X^{2.8} $$

其中 `x` 是一个从 **1 到 50** 的 50 个值组成的数组。

**解题思路**：
- 与前面 `y = x*3.4` 的模板**完全同构**，只需把 `range(100)` 改成 `range(50)`、把 `*3.4` 改成 `**2.8`。
- Notebook 特意提醒：**"the operator `**` is needed to raise one number to another [e.g 2**3]"** —— 幂运算必须用 `**`，不是 `^`（`^` 在 Python 里是按位异或，写了不会报错但结果全错，属于隐蔽的致命错误）。
- 索引偏移仍然是 `x.append(step+1)`，因为 `range(50)` 给的是 0–49，而我们要 1–50。

**代码实现**：

```python
# Initiliase an empty list for both 'x' and 'y'
x = []   # 重新初始化为空列表 —— 很重要，否则会接着上一段代码的 100 个值继续加
y = []

# Now loop through 50 values and append each list accordingly.
# One list contained values for 'x', the other 'y'.
# Please note the operator ** is needed to raise one number to another [e.g 2**3]
#------'INSERT CODE HERE'------
for step in range(50):          # step = 0, 1, ..., 49（共 50 轮）

    # Append a value to our x array
    x.append(step+1)            # 存入 1, 2, ..., 50

    # Append a value to our y array
    y.append(x[step]**2.8)      # 取回本轮刚存的 x 值，做 2.8 次幂，存入 y

#------'INSERT CODE HERE'------

# Print the last four values from both our x and y arrays
print("The 47th element of x is ",x[46])   # 第 47 个 → 索引 46
print("The 47th element of y is ",y[46])

print("The 48th element of x is ",x[47])
print("The 48th element of y is ",y[47])

print("The 49th element of x is ",x[48])
print("The 49th element of y is ",y[48])

print("The 50th element of x is ",x[49])   # 最后一个 → 索引 49
print("The 50th element of y is ",y[49])
```

**输出**：

```
The 47th element of x is  47
The 47th element of y is  48069.98672788238
The 48th element of x is  48
The 48th element of y is  50988.87907329358
The 49th element of x is  49
The 49th element of y is  54019.30894617742
The 50th element of x is  50
The 50th element of y is  57163.13149091575
```

**输出解读与正确性检验**：
- `x[49] = 50` ✓ —— 说明偏移正确，最后一个值确实是 50（不是 49，也不是 51）。
- `y[49] = 57163.13...` = 50^2.8。**粗略验算**：50² = 2500，50³ = 125000，2.8 介于 2 和 3 之间且更靠近 3，所以结果应在 2500 与 125000 之间、偏向大值一侧 —— 57163 完全合理 ✓。
- **`y` 的值都是 float**（带很多位小数），即使 `x` 是 int。因为 **`int ** float` 的结果会被提升为 float**。
- 相邻两项的比值 `50988.88/48069.99 ≈ 1.0607`，而 `(48/47)^2.8 ≈ 1.0607` ✓ —— 这是另一种快速验算幂函数的方法。
- 输出打印的是**最后四个**元素（题目模板给的），不是像上一个例子那样打印前四个。改动 index 时要小心。

**⚠️ 如果不重新初始化 `x = []` 会怎样？** 如果沿用上一段代码留下的、已经有 100 个元素的 `x`，那么 `x.append(step+1)` 会从索引 100 开始追加，而 `x[step]`（step=0..49）会取到**旧的**值，`y` 就完全算错了，而且**不会报任何错**——这是最危险的一类 bug：**silent failure（静默失败）**。所以模板里 `x = []` 那两行是必须的。

---

### Practical 收尾总结（Notebook 原文 "⚙️ What We Did"）

> 本次实践课我们：
> - 探索了 **Python 中所有的值都有数据类型 (data type)** 这一观念
> - 认识了常见基本类型：数字（整数与小数）、文本（字符串 string）
> - 用**注释 (`#`)** 解释代码、留下笔记
> - 创建**变量 (variables)** 保存值以备后用
> - 练习用**清晰、有意义的名字**给变量赋值
> - 用 `print()` 函数**显示输出**、检查代码
> - 运行并修改代码单元格，**观察 Python 的反应**
>
> 🧠 核心是：理解 Python 如何存储数据，以及我们在简单程序里如何与之交互。

---

## 六、易错点 / 重点难点

### 6.1 索引三重对应（本周头号难点）

| 说法 | 对应 |
| --- | --- |
| "第 1 个元素" | 索引 `[0]` |
| "第 4 个元素" | 索引 `[3]` |
| "第 81 个元素" | 索引 `[80]` |
| "第 n 个元素" | 索引 `[n-1]` |

`range(n)` 生成 `0 … n-1`，**恰好等于一个长度为 n 的列表的全部合法索引**——这不是巧合，是设计。

### 6.2 常见报错及修法

| 报错 | 典型原因 | 修法 |
| --- | --- | --- |
| `TypeError: 'tuple' object does not support item assignment` | 试图修改 tuple 的元素 | tuple 不可变；改用 list |
| `IndexError: list index out of range` | 索引超出列表边界（Notebook 明确鼓励你去试：*"If you ask Python to print any entries beyond the boundaries of our array, you would get an error message. Try it!"*） | 检查索引是否 ≥ 列表长度；记住最后一个索引是"长度−1" |
| `IndentationError: expected an indented block` | 冒号 `:` 后面那行没缩进 | 给循环体加缩进（惯例 4 个空格） |
| `IndentationError: unexpected indent` | 不该缩进的行缩进了，或缩进宽度不一致 | 同一代码块内缩进必须完全一致；不要混用 Tab 和空格 |
| `NameError: name 'xxx' is not defined` | 变量还没定义就用了；或 Notebook 里定义变量的单元格还没运行 | 按顺序从上到下运行单元格；检查拼写与大小写 |
| `SyntaxError: invalid syntax` | 少了冒号、括号不配对、用了 `=` 该用 `==` 等 | 从箭头指的那一行**往前一行**也检查（少括号常导致报错点后移） |
| `AttributeError: 'tuple' object has no attribute 'append'` | 对 tuple 调用 `.append()` | tuple 没有这个方法 |

**读 Traceback 的三步法**（本周从 tuple 报错里学到的通用技能）：
1. **看最后一行**：错误类型 + 一句话原因。
2. **看 `---->` 箭头**：出错的确切行。
3. **看 `Cell In[n], line m`**：哪个单元格的第几行。

### 6.3 语法陷阱清单

- **`^` 不是幂运算**！Python 里幂是 `**`。写 `2^3` 得到 `1`（按位异或），不报错但结果全错。
- **分母必须加括号**：`h/(m*vel)` ✓ ；`h/m*vel` ✗（被解释成 `(h/m)*vel`）。
- **`**` 优先级高于 `*` 和 `/`**：`m*c**2` = `m*(c**2)` ✓。
- **`=` 是赋值不是等号**：`x = 2` 是"把 2 存进 x"。
- **变量名区分大小写**：Notebook 里用了 `Price`（大写 P），如果后面写 `price` 就会 `NameError`。**建议统一用小写加下划线**，如 `price_per_kg`。
- **`Lambda` 首字母大写是有原因的**：`lambda` 是 Python 的保留关键字，不能当变量名。
- **不要写 `lst = lst.append(x)`**：`.append()` 返回 `None`，这样写会把列表整个变成 `None`。
- **`print` 逗号分隔会自动加空格**：所以 `print("z = ", z)` 会输出 `z =  9.9`（两个空格：一个来自字符串里手打的空格，一个来自逗号）。想精确控制空格就把字符串末尾的空格去掉。

### 6.4 浮点数精度（贯穿全课的坑）

材料里出现了两次：
- `-3.4 + 4.7` → `1.3000000000000003`（不是 `1.3`）
- `298.15 - 273.0` → `25.149999999999977`（不是 `25.15`）

**原因**：十进制小数在二进制里往往无法精确表示，只能近似存储。
**后果与对策**：
- 显示的时候可以格式化到合适位数（后续会学）。
- **永远不要用 `==` 判断两个浮点数相等**。
- 报告科学结果时要按有效数字取舍，别把 `25.149999999999977` 直接写进论文。

### 6.5 Jupyter Notebook 特有的坑

- **单元格是有状态的**：变量在整个 Notebook（kernel）里共享。上面单元格的修改会影响下面。
- **执行顺序 ≠ 显示顺序**：你可以跳着跑单元格，`In[9]` 这个编号记录的是**执行顺序**。乱跑很容易造成"我明明写对了却报 NameError"。**排错第一招：Restart Kernel & Run All，从头顺序执行一遍。**
- **重复运行含 `.append()` 的单元格会不断累积元素**（Exercise 3、4 都有这个风险）。用 `x = []` 重新初始化，或重启 kernel。
- **赋值语句没有输出是正常的**，不要以为"没反应 = 没运行"。
- **单元格最后一行的表达式会自动回显**（如 `list_capitals[0]` → `'London'`），但**只有最后一行**；中间的表达式想看到就必须用 `print()`。

### 6.6 概念上容易混淆的

| 容易混淆 | 区分 |
| --- | --- |
| list vs tuple | `[]` 可变 vs `()` 不可变 |
| `type()` 显示的 `<class 'int'>` | "class"只是 Python 的内部说法，看引号里的字就行 |
| `interpreted` vs `compiled` | Python 走解释器实时翻译；C/Fortran 先编译成机器码 |
| `module` vs `package` vs `library` | 本周不严格区分，都指"别人写好、可以装进来用的功能包" |
| `int(3.9)` | 结果是 `3`（**截断**，不是四舍五入） |
| 科学计数法 `1e-003` 和 `1E6` | `e`/`E` 完全等价 |

### 6.7 课程期望（幻灯片 "course expectations"，值得反复看）

- **Give yourself time** —— 给自己时间。
- **It is ok to find this difficult** —— 觉得难是正常的。
- **No one produces perfect code** —— 没人能写出完美代码。
- **Practice… practice… practice…** —— 反复练习。（幻灯片配图梗："spock was ok in the end…"）
- **Try** —— 动手试。
- **Helping each other is fine** —— 互相帮忙没问题。
- **You are not expected to remember syntax perfectly** —— **不要求你完美记住语法。**
- **ChatGPT is fine.. I use it!** —— 用 AI 是允许的，讲师自己也用。
- **Programming is a continual journey…into a wonderous tomorrow** —— 编程是一段持续的旅程。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| algorithm | 算法 | 解决某个问题的一组有序步骤；词源来自 Al-Khwārizmī |
| syntax | 语法 | 决定哪些程序在结构上被允许的一套规则 |
| interpreter | 解释器 | 边读边把源代码翻译成机器码并执行的"翻译官"，Python 用它 |
| compiler | 编译器 | 先把整份源代码翻译成机器码再运行，C/Fortran 用它 |
| machine code | 机器码 | 计算机真正执行的、人类几乎读不懂的底层指令 |
| interpreted language | 解释型语言 | 靠解释器运行的语言（Python、JavaScript），跨平台方便 |
| compiled language | 编译型语言 | 需要编译的语言（C++、Fortran），性能高但移植麻烦 |
| high-level / low-level language | 高层 / 低层语言 | 高层帮你做掉很多底层活（Python）；低层要你自己管（C） |
| source code | 源代码 | 我们写的、人类可读的程序文本 |
| module | 模块 | 别人写好、可按需装进 Python 的功能包（如 numpy、pandas） |
| ecosystem | 生态系统 | Python 周边所有模块与工具的总和，是它最大的优势 |
| distribution | 发行版 | 打包好 Python 加一堆常用模块的安装包，本课用 Anaconda |
| environment | 环境 / 虚拟环境 | 可创建可关闭、互不干扰的独立"虚拟实验室" |
| Jupyter Notebook | Jupyter 笔记本 | 能把文字、代码、输出、图表放在一起的交互式"虚拟实验记录本" |
| kernel | 内核 | Notebook 背后真正执行代码、保存变量状态的进程 |
| cell | 单元格 | Notebook 中可独立运行的一块内容（代码或文字） |
| comment | 注释 | `#` 后的文字，解释器忽略，写给人看 |
| variable | 变量 | 用名字指代一个存储起来的值 |
| assignment | 赋值 | 用 `=` 把右边的值存进左边的变量 |
| data type | 数据类型 | 值的种类，如 int、float、complex、string |
| integer (`int`) | 整数 | 无小数点的数，精度只受内存限制 |
| floating point (`float`) | 浮点数 | 带小数点的实数，通常用双精度存储 |
| complex | 复数 | 有实部和虚部，虚部用 `j` 标记，本课只出现一次 |
| string (`str`) | 字符串 | 用引号括起来的文本，如 `'London'` |
| double precision | 双精度 | 浮点数的常用存储规格（约 15–17 位有效数字） |
| floating-point precision | 浮点精度（误差） | 二进制无法精确表示某些十进制小数，导致 `25.15` 变成 `25.149999999999977` |
| `NaN` (Not a Number) | 非数 | 表示"不是一个数字"，实测数据里常用来标记缺测值 |
| `inf` / Infinity | 无穷 | 浮点数可表示的正 / 负无穷 |
| scientific notation | 科学计数法 | `2.5e2` 表示 2.5 × 10²，`e` 与 `E` 等价 |
| arithmetic operator | 算术运算符 | `+ - * / **` 等做数学运算的符号 |
| exponentiation | 幂运算 | Python 用 `**` 或 `pow(x,y)`，**不是 `^`** |
| array | 数组 | 按顺序存放多个值的结构（本周用 list 充当） |
| list | 列表 | 用 `[]` 建立，**可变 (mutable)**，可增删改 |
| tuple | 元组 | 用 `()` 建立，**不可变 (immutable)**，建好就定型 |
| dictionary | 字典 | 第三种集合类型，本周只提名字，后续再讲 |
| mutable | 可变的 | 建立之后还能改内容（list） |
| immutable | 不可变的 | 建立之后不能改内容（tuple） |
| index / indexing | 索引 | 用 `[n]` 取元素；**Python 索引从 0 开始** |
| element / item / entry | 元素 / 项 | 数组里的单个值 |
| `.append()` | 追加 | 列表的方法，在末尾加一个元素，原地修改 |
| method | 方法 | 附在对象上、用 `.` 调用的函数，如 `list.append()` |
| function | 函数 | 可复用的一段功能，如 `print()`、`type()`、`range()`；Practical 3 详讲 |
| argument / parameter | 参数 | 传给函数的输入值 |
| return value | 返回值 | 函数算完后交回来的结果 |
| loop | 循环 | 让一段代码重复执行 |
| `for` loop | for 循环 | 按序列逐项执行的循环 |
| loop variable | 循环变量 | 每轮自动取到序列下一个值的变量（如 `step`） |
| iteration | 迭代 | 循环的一轮 |
| `range()` | 范围函数 | 生成 0 到 n−1 的整数序列 |
| conditional statement | 条件语句 | `if` 之类的判断结构，本周只提及，下周展开 |
| indentation / white space rule | 缩进 / 空白规则 | 冒号 `:` 后的下一行必须缩进，Python 靠它界定代码块 |
| colon `:` | 冒号 | 宣告"下面是一个缩进代码块" |
| error / exception | 错误 / 异常 | 程序运行不下去时抛出的信号 |
| `TypeError` | 类型错误 | 对某个类型做了它不支持的操作 |
| `IndexError` | 索引错误 | 索引超出数组边界 |
| `NameError` | 名称错误 | 用了一个尚未定义的变量名 |
| `IndentationError` | 缩进错误 | 缩进不合规 |
| `SyntaxError` | 语法错误 | 写法违反 Python 语法规则 |
| Traceback | 回溯 | 报错时的现场报告，从下往上读，`--->` 指出错行 |
| debugging | 调试 | 找出并修正代码错误的过程 |
| GitHub | GitHub | 全球通用的代码分享平台，本课课程内容托管于此；也是"数字 CV" |
| Anaconda | Anaconda | 最常用的 Python 发行版，自带整套科学计算模块 |
| Google Colab | 谷歌 Colab | 免费的云端 Notebook 服务，每次会话还赠送 GPU |
| GPU | 图形处理器 | 擅长并行计算的芯片，机器学习训练的主力 |
| Stack Overflow | Stack Overflow | 全球最大的编程问答社区 |
| LLM (Large Language Model) | 大语言模型 | 如 ChatGPT，可生成代码；讲师允许并鼓励使用，Week 9 会教提问策略 |
| vanilla (Python) | 原味 / 裸装 Python | 不加任何模块的、开箱即得的基础 Python（Week 1–2 的内容） |
| Numpy | Numpy | 数值 Python 模块，做数组运算比纯 Python 快得多（Practical 3） |
| SciPy | SciPy | 科学计算模块，含微分方程求解器（Week 5） |
| Matplotlib | Matplotlib | Python 的绘图框架 |
| Pandas | Pandas | 载入与处理表格数据的模块（Week 6） |
| GeoPandas | GeoPandas | 在 Python 里做 GIS 分析的模块（Week 7） |
| sklearn (scikit-learn) | scikit-learn | 机器学习模块（Week 9） |
| Django | Django | Python 的 web 应用框架（Instagram 案例） |
| GIS | 地理信息系统 | Geographical Information Systems，处理带空间坐标的数据 |
| ARM chip | ARM 芯片 | 手机平板里的芯片，比 Intel 省电，共同发明人在曼大 |
| Fortran | Fortran | 老牌科学计算语言，**所有气候模型都用它写** |
| Julia | Julia | MIT 出品的新语言，比 Python 快，讲师预测十年后成熟 |

---

## 附：整门课 12 周路线图（Lecture "course layout"）

| 周次 | 主题 | 说明 |
| --- | --- | --- |
| **1–2** | **'Vanilla' Python**：Data types、Basic operations、Loops、Conditionals | 不用任何模块的基础语法。"nuts and bolts" |
| **3** | **Modules and Functions**（含 **The Numpy module**） | 引入模块生态与自定义函数；Numpy 数值数组 |
| **4** | **Conway's Game of Life** | 四条规则生成屏幕上互相作用的"数字物种"动画，综合前三周所学 |
| **5** | **Differential Equations** | 用 Python（SciPy）解微分方程，配合 Matthew 的数学课 |
| **6** | **Pandas and data discovery** | 载入数据；火山数据库、把火山位置画在地图上看它如何贴合板块边界 |
| **7** | **Geospatial analysis** | GeoPandas 做 GIS；载入 Environment Agency 洪水风险图，叠加英国行政边界，看洪水离发电站有多近 |
| **8** | **Statistical Analysis** | 载入空气质量与气象数据（约 18,000 个数据点），比较站点、画日变化曲线 |
| **9** | **Cluster Analysis** | 机器学习入门：让算法自己把数据分成不同的簇；也会讲如何用 LLM 辅助写代码 |
| **10–12** | **Creating a notebook assessment** | 无讲座，只有实践课；从 **Week 4–9 的 Notebook 中选一个主题**深入做，最终提交一份 Jupyter Notebook 作为课程作业 |

每周结构：**lecture + practical，并提供参考答案 (Solutions are given)**。Blackboard 上每周还有一段**两分钟总结视频**和幻灯片副本。
