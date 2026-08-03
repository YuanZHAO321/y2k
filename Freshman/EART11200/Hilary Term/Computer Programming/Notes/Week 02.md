# Week 2 — 循环与条件语句 (Loops and Conditionals)：`for` 循环、`if/elif/else`、嵌套循环

> 材料来源
> - Lecture 幻灯片：`Lecture2-DEES-Programming-2025.md`（PDF 转写）
> - Lecture 录音转写：`EART11200 - 04-Feb-transcript.md`
> - Practical：`Practical_2.md`（对应 `Practical_2.ipynb`）

---

## 一、本周主题

本周是 EART11200 春季学期 Computer Programming 部分的第 2 周，主题是 **「循环 (loops) 与条件语句 (conditionals)」**，即给程序加入**重复**和**逻辑判断**这两个最基本的控制流 (control flow) 能力。

课程官方给出的本周三条主线：

1. **`for` 循环续讲 (FOR loops continued)** — 用循环遍历 (iterate) 数组、逐元素读取与修改。
2. **条件语句 (Conditional statements)：`if` / `elif` / `else`** — 让程序根据条件改变执行流程 (change the flow of a program)。
3. **嵌套循环 (Nested loops)** — 在循环里再放循环，处理二维乃至多维问题。

### 1.1 本周在课程中的位置：仍然是「Vanilla Python」

老师在录音里反复强调，第 1、2 周都属于 **「Vanilla Python」（原味 / 开箱即用的 Python）**：

> "This is Python we get out of the box. We're not bringing in any extra modules."

也就是说，本周**不导入任何外部模块**（Practical 里的 `matplotlib` / `numpy` 只是为了画图给你看效果，老师明确说「Do not worry about the syntax or module used to create the plot」，模块系统要到 Week 3 才正式讲）。

老师的原话解释了为什么前两周这么「抽象」：

> "at the moment it feels hard to see how this is applied but we'll get to that specifically from week four where we'll actually make something work."

即：**前 3 周打地基（造数、存数、取数、改数、加逻辑），第 4 周开始真正做出东西。**

### 1.2 完整课程路线图（录音里老师逐周交代，非常有价值）

| 周次 | 内容 | 老师的说明 |
| --- | --- | --- |
| Week 1 | Data types、基本运算、list / tuple、索引 | Vanilla Python |
| **Week 2（本周）** | **Loops、Conditionals、Nested loops** | **Vanilla Python，本周结束「原味 Python」阶段** |
| Week 3 | Modules and Functions、**NumPy** | 引入模块；NumPy = numerical Python，高效数组；「下周我们连 `for` 循环都不用了，可以直接把两个大数组相乘」 |
| Week 4 | **Conway's Game of Life（康威生命游戏）** | 数学家 John Conway 在 1970 年代提出的四条简单规则；在 2D 网格 (mesh / 2D matrix，例如 50×50) 上用嵌套 `for` 循环扫描、用条件语句按「邻居数量」决定细胞生死（过密/过疏则死），再可视化。老师说这是 Week 1+2+3 的**总汇** |
| Week 5 | 微分方程 (Differential Equations) | 与 Matthew 的数学课直接呼应；「大多数科学理论都写成微分方程形式——传热、传质、气候模拟」，人手解不了，交给 Python 数值求解 |
| Week 6 | Pandas 与数据发现 / 载入真实数据 | 首次**载入外部数据**：Smithsonian Institute 的**火山喷发数据库**，画在地图上，会看到喷发点与**板块构造边界 (plate tectonic boundaries)** 完美吻合 |
| Week 7 | 地理空间分析 / Python 里的 GIS | 载入 **shapefiles**、洪水风险图 (flood risk maps)、基岩信息 (bedrock)，绘制英国地图并计算距离 |
| Week 8 | 统计分析 (Statistical Analysis) | 把统计课学的东西交给 Python 做 |
| Week 9 | 聚类分析 (Cluster Analysis) / 机器学习与 AI 初探 | 用 cluster analysis 把观测分组 |
| 复活节后 | 无新内容，做**评估用 Notebook (assessment notebook)** | 从 Week 4–9 的内容里**自选一本** Notebook 复现 |

> 注：幻灯片的编号把 6 标为 "Pandas and data discovery"、7 为 "Geospatial analysis"、8 为 "Statistical Analysis"、9 为 "Cluster Analysis"；录音口述与此基本一致，只是把「载入数据」与「地理空间」讲得更细。

### 1.3 为什么科学软件必须有「逻辑」

老师给了几个非常好的动机例子（都值得记住，考试/写报告时可当作「为什么要用条件语句」的答案）：

- **海洋环流模型**：不同的**尺度 (scale)** 下适用的理论不同，可以用条件语句在尺度变化时**自动切换理论**。
- **物理定律的适用范围**：
  - 分子尺度 → 牛顿定律开始失效，需要分子动力学 (molecular dynamics)；
  - 送火箭上月球 → 牛顿定律很好用；
  - 天文尺度 → 需要相对论 (relativistic laws)。
  → 「所以需要逻辑来切换我们感兴趣的物理定律。」
- **气候模型 (climate models)**：老师认为这是地球科学领域「数值上最有挑战性」的软件，通常用 Fortran / C 这类编译语言写，但**里面一定全是逻辑**。
- **ATM 取款机**：后台一直有逻辑在等你按键，一检测到电信号就开始动作 —— 这就是最基本的 logic。
- **Week 6 的实际用途**：载入火山喷发数据库后，「我可能只想画 1900 到 1980 年之间发生的喷发」，这就需要 `if` 和 `and`。

---

## 二、核心概念

### 2.1 Week 1 回顾（老师本周开头的 recap）

- 编程语言有很多种，**每种有自己的语法 (syntax)**——「就像人类语言各有各的风格」。**现在学的东西可以迁移到别的语言**，只是写法不同。
- 我们写的是**源代码 (source code)**，「代码就是我们这本小说背后的文字」。
- Python 可以写在独立的 `.py` 文件里，但**本课程一律用 Jupyter Notebook**。
- Python 是**解释型语言 (interpreted language)**，不是**编译型语言 (compiled language)**：
  - 解释型：直接写 `x = 2.4`、`y = 4.8` 然后相乘，**不用事先声明类型**；
  - 编译型：必须提前告诉编译器「这是 float 吗？single 吗？integer 吗？」；
  - 代价是**慢**——所以 Week 3 引入 NumPy 来提速。
- **数据类型 (data types)**：可以存单个 `float`、`int`、`str`。
- **list（列表）** 是 Vanilla Python 的「数组」，可以修改、追加条目。
- **索引从 0 开始 (Indexing starts at 0)** —— 老师说这是「跟某些编程语言不太一样的地方」，`list[0]` 取第一个元素。

#### list vs tuple（老师本周又强调了一遍）

| | list | tuple |
| --- | --- | --- |
| 是否可修改 (mutable) | **可以**：扩展、修改、缩短 | **不可以** |
| 内存效率 | 较低 | **较高** |
| 本课程使用 | **一律用 list** | 只是让你认识一下 |

老师用了一个很形象的比喻解释效率差异：

> tuple 「像一排联排别墅 (a row of terraced houses)——电脑确切知道该敲哪扇门，而且门号不会变，所以取数据很高效」；list 则「可能把元素撒在整个小区里」，取数据「字面意义上要多走点路」。

老师同时安慰说：本课程不会有任何计算需要等超过几分钟，所以效率不是问题；「一旦要跑几小时、几天、几周，那才成为问题」。

> ⚠️ **转写中的一个错误**：录音里出现 "With a list, we have square brackets. With a tuple, we have curly brackets."
> 实际上：**list 用方括号 `[]`，tuple 用圆括号 `()`，花括号 `{}` 是 dict / set**。这里应是口误或语音转写错误，**以 `()` 为准**。

#### 「array」和「list」的关系

老师澄清：

> "a list is a specific entity in Python, but arrays are general."

即：**`list` 是 Python 里一个具体的类型；「array（数组）」是一个泛称**，指「一堆东西的集合」，可以是 1 维（strip / 条带）、2 维（matrix / 矩阵）、3、4、5…… 维。课上两个词会混着用。

### 2.2 硬件背景：bit、byte 与数值范围（幻灯片 + 录音）

这一段虽然不是语法，但老师专门讲了，而且与**地球与环境科学**有关：

- 硬件底层就是在**拨开关 (flicking switches between on and off)**。
- **1 byte = 8 bits**（这是 1940–50 年代晶体管制造方式留下的历史习惯）。
- 8-bit 机器能表示的数有一个**最大值**；32-bit 是 64-bit 容量的一半（指位数减半，表示范围呈指数级缩小），16-bit 又减半。
- **今天我们跑的基本都是 64-bit 机器**，Python **默认一切都是 64-bit**。
- 对地球科学，64-bit 精度**绰绰有余**；但**天文学 / 天体物理**可能会碰到计算机能存的最大数的上限。
- **环境角度（老师特别点出）**：「全球数据中心大约占地球电力供应的 17%」——存的数据越多、开关越多、耗电越多。所以有研究在问：**我们真的需要这么多信息吗？气候模型能不能跑在 32-bit 上？**
  > ⚠️ 这个 17% 的数字明显偏高（业界常引用的数值在 1–2% 量级），记笔记时**照录老师原话即可**，但如果要写进作业请自行核查数据来源。
- 老师的私人例子：**Sega 8-bit Master System**（还在他车库里）。1980 年代游戏机从 8-bit 到 16-bit，画质变好「无非就是信息量变多了」。幻灯片写：「The third generation of video game consoles, also referred to as the 8-bit era, began in 1983.」
- 在编译型语言里可以**指定更低精度**，这在高性能计算 (HPC) 上有意义——想把更多信息塞进去，就得「缩一缩」。属于软件工程范畴，本课不用管。

### 2.3 `for` 循环

**核心思想**：与其手动一个一个访问/修改数值，不如**「循环」遍历数组**（幻灯片原话：Rather than manually access values/entries, we can access and modify by 'looping' through our arrays）。

幻灯片定义：

> A feature of every programming language. Iterating over components of an array and performing an action or modifying an entry.

Python 语法骨架：

```python
for <迭代变量> in <可迭代对象>:
    <缩进的循环体>
```

两个关键点（幻灯片右侧的批注）：

- **`<迭代变量>` 的名字可以随便取**（"Can be any name I want"）。
- **迭代变量会自动采用它所遍历的那个数组/可迭代对象的元素格式**（"The variable adopts the same format as the array/iterable it is searching across"）——遍历数字列表它就是数字，遍历字符串列表它就是字符串。

老师课上的两种写法：

```python
# 写法 A：遍历一个已经存在的 list
primes = [2, 3, 5, 7]     # 我自己造的一个很小的 list，取名 primes
for prime in primes:      # 「对 primes 里的每一个元素」——注意结尾的冒号 :
    print(prime)          # 把它打印到屏幕上；缩进表示这行属于循环体
```

输出（依次、从左到右 / 从头到尾）：

```
2
3
5
7
```

老师的解释：「用英语讲就是 *for an element in that array, print that to the screen*。这是顺序的 (sequential)。`prime` 这个词是我造的。解释器会把每一个顺序取出的条目**赋值**给这个变量。」

⚠️ **老师特别提醒的报错场景**：

> "So I've already created primes. If this didn't exist, you'd get an error. The interpreter would say it doesn't exist. It can't find it."

即：如果 `primes` 没有先被创建，`for prime in primes:` 会报 `NameError: name 'primes' is not defined`。**必须先有变量、它在内存里有地址，循环才能找到它。**

```python
# 写法 B：用 range() 临时造一个序列，不必事先写出数组
for step in range(7):     # range(7) 在幕后造出 0,1,2,3,4,5,6 共 7 个数
    print(step)
```

老师的解释：「我有一个通用场景，我想遍历一行从 1 到 10 的数字，我**不想真的去造那个数组**。我可以用一个叫 `range` 的函数……幕后它替我造了一个 7 元素的数组。区别只是前一种我显式写出了数组，这一种我是在告诉 `for` 循环：走 7 次迭代。」

> **注意 Python 从 0 开始**：`range(7)` 的元素是 **0 到 6**，不是 1 到 7。老师说「有点绕 (a little bit confusing)，但我们会反复练」。

**为什么循环有用？** 老师回答了「我肉眼就能看到数组，为什么还要循环？」：

> "we'll very quickly start working with arrays that have thousands and thousands of elements. So you can't do that visually."

**语法高亮 (syntax highlighting)**：老师顺带解释了为什么 Notebook 里某些词会变绿——那是**内建操作 (internal operations)** 被高亮了；桌面代码编辑器也都有这个功能，且会**随语言变化**，让代码更可读。

### 2.4 条件语句 `if` / `elif` / `else`

幻灯片的定位：

> **Changing the flow of a program using basic logic — very important.**

幻灯片列出的应用场景：

- 等待用户输入 (Waiting for user input)
- 检测某种特定输入 (Detecting a certain type of input)
- 知道何时该换理论 (Knowing when to change theory)
- 在风险缓解中停止某个过程 (Stopping a process in risk mitigation)
- **可以作用于数值型和非数值型 (numeric and non-numeric) 的例子**
- 等待最大/最小值 (Wait for maximum/minimum values)
- 选出数据库中的特定条目 (Select specific entry in database)
- 搜索某条目是否存在 (Search for existence of entry)

#### 比较运算符对照表（Practical 里给的表，必须背）

| 含义 | 数学符号 | Python 符号 |
| --- | --- | --- |
| 小于 Less than | < | `<` |
| 大于 Greater than | > | `>` |
| 小于等于 Less than or equal | ≤ | `<=` |
| 大于等于 Greater than or equal | ≥ | `>=` |
| 等于 Equals | = | `==` |
| 不等于 Not equal | ≠ | `!=` |

> 🔴 **Practical 的红色警告框**：
> "The obvious choice for equals, a single equal sign, is not used to check for equality. It is a common error to use only one equal sign when you mean to test for equality, and not make an assignment!"
>
> 老师在录音里的解释：`=` 是**赋值 (assignment)**——「我要创建变量 x，请给它值 3」；`==` 是**判断相等**。他说「如果我在这里写 `x == 3`（在还没赋值的情况下），会给你报错，因为它是在检查这件事是否为真，而变量可能还没被赋值。」
> （实际报错是 `NameError: name 'x' is not defined`。）

#### 最基础的 `if` 示例

```python
# 初始化两个整型变量
x = 3
y = 5

# 用 IF 语句检查 x 和 y 的相对大小，然后各自行动
if x > y:
    print("X is greater than Y")

if x < y:
    print("X is less than Y")
```

输出：

```
X is less than Y
```

**读法**：解释器**逐行往下走**，遇到 `if` 就检查条件是否为 `True`；为 `True` 就执行冒号后面缩进的那块。第一个 `if`（3 > 5）为 `False`，什么也不做；第二个 `if`（3 < 5）为 `True`，打印。

#### 用 `else` 合并

Practical 里给的「改写版」（注意：**这段是示意，写法本身是错的**，见第六节）：

```python
x = 3
y = 5
if x > y:
    print("X is greater than Y")
else x < y:              # ❌ 非法语法！else 后面不能跟条件
    print("X is less than Y")
```

**正确写法应为**：

```python
if x > y:
    print("X is greater than Y")
else:                    # ✅ else 不带条件，直接冒号
    print("X is less than Y")
```

或者如果确实要第二个条件：

```python
if x > y:
    print("X is greater than Y")
elif x < y:              # ✅ elif 才能带条件
    print("X is less than Y")
```

#### 冒号 `:` 与缩进 (indentation)

**这是 Python 最重要的形式规则**，幻灯片和 Practical 都反复强调：

> "notice how we have introduced a statement that ends with a colon `:` and thus requires the next line to be indented."

老师在录音里把冒号说成 "semicolon"（分号）——**这是口误/转写错误，实际是冒号 `:`**。他的说法：

> "whenever there's a [colon] ... Python then demands you have white space after it. So typically, we'll see functions we write from week three onwards and for loops have [colons] after it. So it's forcing us to write clean code."

即：**冒号强制缩进，缩进强制你写整洁的代码**，你可以顺着缩进层级一眼看出哪块代码属于哪个结构。

**幻灯片还提醒**：注意 `#` 号用于注释 (comments)，以及 `:` 运算符的正确使用。

### 2.5 嵌套循环 (Nested loops)

幻灯片定义：

> In many cases we want to work with more than one variable at a time, often in a two [or more] dimensional setting. **We can combine 'FOR' loops on any number of levels.** We can use conditional statements to refine the process.

通用骨架（Practical 给的伪代码）：

```python
for [first iterating variable] in [outer loop]:        # 外层循环 Outer loop
    [do something]                                     # 可选：在外层做点事
    for [second iterating variable] in [nested loop]:  # 内层/嵌套循环 Nested loop
        [do something]
```

**执行顺序（考点）**：老师原话——

> "behind the scenes, what's happening is the computer iterates on the loop first that's the lowest here. So it will first go through all of these numbers and then increment the outer loops."

即：**最内层跑完一整轮，外层才前进一步**。幻灯片上的示意图正是：

```
step1   0  1
step2   0 1 2 3 4 5 6
```

外层 `step1` 取 0 时，内层 `step2` 从 0 跑到 6；然后 `step1` 变成 1，内层再从 0 跑到 6。总迭代次数 = 外层次数 × 内层次数。

**矩阵心智模型（老师强烈推荐）**：

> "the way I think about this ... I think about a matrix rather than an array. So we've got a number of rows and a number of columns ... I want the program to search through every element of the first row and then every element of the second row. So it's sweeping through that matrix."

- 外层循环 = **行号 (row)**
- 内层循环 = **列号 (column)**
- 再加一层 = **深度 (depth)**，就能处理三维数组

「维度多少无所谓 (it doesn't matter how many nested loops you need)，取决于你手上的数据。」

---

## 三、语法速查与函数表

### 3.1 本周出现的语法结构

| 名称 | 作用 | 用法示例 | 注意事项 |
| --- | --- | --- | --- |
| `for ... in ...:` | 遍历可迭代对象，逐元素执行循环体 | `for prime in primes:` / `for step in range(75):` | 结尾必须有冒号；下一行必须缩进；迭代变量名任意；被遍历的对象必须已存在，否则 `NameError` |
| `range(n)` | 生成 `0, 1, ..., n-1` 共 n 个整数 | `range(75)` → 0…74 | **不含 n 本身**；从 0 开始；只适合数值迭代，遍历单词列表时**不要**用 |
| `if <条件>:` | 条件为 `True` 时执行缩进块 | `if x[step] <= 20:` | 用 `==` 不是 `=`；冒号 + 缩进 |
| `elif <条件>:` | 前面所有条件都 `False` 时，再检查这个条件 | `elif x[step] >= 20 and x[step] < 60:` | **顺序至关重要**，第一个为真的分支就会「吃掉」后面所有分支 |
| `else:` | 前面所有条件都 `False` 时的兜底 | `else:` | **`else` 后面不能跟条件**，直接跟冒号 |
| `and` | 逻辑与：两边都为 `True` 才为 `True` | `if x >= 20 and x < 60:` | 用来**给区间加上界**，是本周解决「Version 1 错误」的关键 |
| 嵌套 `for` | 多维遍历 | 见 2.5 | 内层先跑完，外层才前进；每多一层就多一级缩进 |
| `**` | 幂运算 (raise to the power) | `2**3` → `8`；`x[step]**(2.8/x[step])` | Practical 明确提示：「the operator `**` is needed to raise one number to another」。**不是 `^`**（`^` 在 Python 里是按位异或） |
| `#` | 单行注释 | `# Append a value to our x array` | 解释器忽略，写给人看 |
| `+`（作用于字符串） | 字符串拼接 (concatenation) | `word1 + ' ' + word2` | 两边必须都是字符串；数字要先 `str()` 转换，否则 `TypeError` |

### 3.2 本周出现的函数 / 方法

| 名称 | 作用 | 参数 | 返回值 | 用法示例 | 常见误用 |
| --- | --- | --- | --- | --- | --- |
| `print()` | 输出到屏幕 | 任意多个对象，逗号分隔 | `None` | `print("The 72nd element of x is ", x[71])` | 逗号分隔的多个参数之间会**自动加一个空格** |
| `list.append(v)` | 在列表**末尾**追加一个元素 | `v`：要加的值 | `None`（**原地修改**） | `x.append(step+1)` | 不要写 `x = x.append(...)`，那会把 `x` 变成 `None` |
| `range(n)` | 生成整数序列 | `n`（也可 `range(start, stop, step)`） | range 对象（可迭代） | `range(80)` | 上界不含；起点默认 0 |
| `str(n)` | 把数字转成字符串 | 任意对象 | `str` | `letter1 = str(step1)` | 不转就没法用 `+` 拼接 |
| `''.join(seq)` | 把一串字符串用指定分隔符连接成一个字符串 | `seq`：字符串序列 | `str` | `''.join(["3","5","9","8","8"])` → `"35988"` | 前面的 `''` 是**分隔符**（这里是空，即无缝拼接）；序列元素必须都是 `str` |
| `"{}".format(v)` | 字符串格式化，把 `v` 填进 `{}` | 任意值 | `str` | `"{}".format(randint(0,9))` → 如 `"7"` | 现代写法也可用 f-string `f"{v}"` |
| `randint(a, b)` | 生成 **闭区间** `[a, b]` 的随机整数 | `a`、`b` | `int` | `randint(0, 9)` → 0–9 | **两端都含**（与 `range` 不同！）；需先 `from random import randint` |
| `from random import randint` | 从 `random` 模块导入单个函数 | — | — | 同上 | Week 3 才正式讲模块 |
| `get_ipython()` | 获取当前 IPython/Jupyter 环境对象 | — | 环境对象 | `if 'google.colab' in str(get_ipython()):` | 只在 Jupyter/Colab 里能用 |

### 3.3 绘图相关（本周只需「会用」，不需理解）

Practical 明确说：「Do not worry about the syntax or module used to create the plot, we will visit this throughout the course.」

| 语句 | 作用 |
| --- | --- |
| `import matplotlib.pyplot as plt` | 导入绘图模块，起别名 `plt` |
| `import numpy as np` | 导入 NumPy，起别名 `np`（Week 3 详讲） |
| `fig = plt.figure(figsize=(8,8))` | 创建一张 8×8 英寸的画布 |
| `ax = plt.axes()` | 在画布上创建坐标轴对象 |
| `ax.plot(np.array(x), np.log(y))` | 画线：x 轴用 `x`，y 轴用 **`y` 的自然对数** |
| `ax.set_title(...)` / `set_xlabel(...)` / `set_ylabel(...)` | 设标题 / 轴标签 |
| `ax.legend(loc='upper left')` | 显示图例，放在左上角（需要 `plot(..., label='...')` 配合） |
| `plt.show()` | 把图渲染出来 |

**为什么要取 `np.log(y)`？**
因为本周的分段函数在大 `x` 处会爆炸式增长（例如 `x**12.5` 在 x=50 时已经是 1.7×10²¹）。直接画的话，小值部分会被压成一条贴着 0 的直线，**完全看不出分段的台阶**。取对数后各段的斜率差异就清晰可见。

**判读要点**：本周的图都应该看到**「台阶 (step change)」**——在分段点（如 x=20、60，或 Exercise 2 的 250、690）处曲线斜率发生突变。如果本该有台阶的地方是平滑的，说明**条件分支写错了**（见 6.2）。

---

## 四、课堂补充（transcript 独有）

这一节记录只在录音里出现、幻灯片和 Notebook 上没有的内容。

### 4.1 「Make it work, make it right, make it quick」

老师本周最核心的一条工程哲学，讲了两遍：

> "So there's a general rule of thumb. **Make something work, make it right, and then make it quick** ... Because obviously you want to make something work, but **working code isn't necessarily giving you the right answer**."

以及：

> "Typically, if you spend hours and hours writing some code and it's working, finish. **Then come back to it and see why it's working** because it could be giving you the wrong answer."

> "make it quick being the last thing you do because if you try and make something quick first, you'll create lots of issues typically."

幻灯片上对应的一句话（加粗强调）：**"Code that works isn't necessarily correct!!"**

### 4.2 老师讲的「灾难场景」——为什么这条哲学重要

关于 Version 1 的 `elif` 错误，老师说了一段很生动的话：

> "Now imagine I've got x values going all the way to 100. Will it ever leave the middle action after? It won't, will it? ... Imagine you've got thousands and thousands of lines of code. So you'll be getting answers going 'brilliant. New result, I'm going to publish this. It's changed everything we know about the Earth system.' **Crap, it's wrong.**"

**记住这个场景**：代码不报错 ≠ 结果正确。逻辑分支写错是**静默失败 (silent failure)**，最危险。

### 4.3 「Overhead（开销）」——为什么循环和条件语句其实「不好」

这是幻灯片上完全没有的内容：

> "The reason that for loops and conditional statements aren't great is because they introduce what's called an **overhead**. And when we talk about overheads in any software development practices, what we're talking about is **the computer has to stop and check something and then go back to that**. So the more conditions and checks we place, it's not doing the operation we want."

- 气候模型开发者会**尽量避免**过多条件判断，因为要尽快拿到结果。
- 但老师补充：「你在本课程里跑的东西看不出来这种拖慢，只有跑几个小时的程序才看得出来。」
- 这也预告了 Week 3 的 NumPy：**向量化运算**可以避免写 `for` 循环。

### 4.4 变量命名完全是个人选择

> "you'll very quickly see that someone's made a choice over a variable name. So that's just a choice I've made. So when you're working through the examples, **you can change those if you want. Nothing will happen.** Provided the code works ... It's all personal choice."

（老师说他本可以把变量叫 `A`、`B`、`David`、`Bridge`，无所谓。）

### 4.5 Stranger Things / Bob Newby 与 BASIC 语言

Exercise 5 的背景故事（老师讲得很详细）：

> "there's a specific example in practical two where I've kind of tried to replicate the challenge that ... **Bob Newby** did in series two where he had to crack the code before he got mauled to death in the scientific facility. But basically that was a nested for loop to find a combination of numbers that would then crack a passcode. Yeah, very naive passcode, but nonetheless."

老师还展示了剧中 Bob 写的原始 **BASIC** 代码，并做了对比：

> "look, we have four loops written in a slightly different way. And we also have conditional statements, if, do this, end. **This `GOTO` statement**, by the way, was how many programming languages were written quite a while ago. So you jump to a certain line in your code and implement that line. **It became very messy.** We now write in functions and modules so we don't have to read down to line 150 and implement that code."

**知识点**：`GOTO` 是老式语言（BASIC、早期 Fortran）的跳转语句，会造成「意大利面条式代码 (spaghetti code)」，现代编程用**函数 (functions)** 和**模块 (modules)** 取代（正好是 Week 3 的内容）。老师还打趣说 BASIC「大概现在还在 ATM 里用着」。

### 4.6 关于 Google Colab / OneDrive 的实操提醒

> "This initial code block just checks if you're in Google Colab or not. If it is, it will mount your Google Drive. ... **On the cluster machines, remember you'll have to link your OneDrive again** because you stored the repository of the notebooks on your OneDrive. ... but once you've linked the OneDrive, **you don't have to install Python again or the environment**."

### 4.7 关于文本处理与 AI 的顺带一说

> "we've seen in Python, you don't just have to work with numbers. You can work with words as well. ... really relevant for AI at the moment, because a lot of the **large language models are built on recognizing patterns in sentences, sequences**."

Practical 也附了一个可选阅读链接（自然语言处理入门），但明确说「We will not be exploring the rich text processing power of Python in this course」。

### 4.8 老师的学习建议

> "The best thing you can do is **start playing with these things** to understand them."

以及 Practical 顶部的提醒：

> "you should not feel pressured to complete every exercise in class. These practicals are designed for you to take outside of class and continue working on them. Proposed solutions to all exercises can be found in the **'Solutions' folder**."

---

## 五、Practical 要点

**Practical 2 目标（Notebook 开头的绿色 Objectives 框）**：

1. Loops: FOR loops continued
   - Exercise 1: Cycling through arrays and modifying values
2. Conditional statements: IF, ELSE and ELIF
   - Exercise 2: Modify a loop to implement one of two [实为三] equations according to a condition being met
3. Nested loops: Working with more than 1 dimension
   - Exercise 3: Print out the result from a nested loop according to a condition being met
   - Exercise 4: Print out which variables match a condition
   - Exercise 5: Repeat Bob Newby's code breaking nested loops to crack the code in the Hawkins lab

**黄色提示框**：读完题目要求后，在代码块里找 `------'INSERT CODE HERE'------` 这个注释，那就是你要写代码的位置。

### 5.0 开场代码块：Google Colab 环境检测

```python
if 'google.colab' in str(get_ipython()):          # 检查当前运行环境的字符串描述里有没有 'google.colab'
    from google.colab import drive                # 有 → 说明在 Colab 上，导入 drive 模块
    mount='/content/gdrive'                       # 指定 Google Drive 要挂载到的路径
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)                            # 执行挂载（会弹出授权流程）
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
                                                  # 拼出课程仓库在 Drive 里的完整路径
    print("\nColab: Changing directory to ", drive_root)   # \n 是换行符
    %cd $drive_root                               # Jupyter 魔法命令 (magic command)：切换工作目录
else:
    print('Not running on CoLab')                 # 不在 Colab → 什么都不做，只提示一句
```

输出：

```
Not running on CoLab
```

**解读**：这是**本周第一个真实的 `if/else` 应用**，而且是刚好符合本周主题的「让代码对环境作出响应」。看到 `Not running on CoLab` 就说明你在本地/机房机器上跑，一切正常，不需要挂载云盘。

- `str(get_ipython())` 把当前 IPython shell 对象转成字符串；如果是 Colab，这个字符串里会含 `google.colab`。
- `in` 是**成员检测运算符**，判断子串是否存在。
- `%cd` 前面的 `%` 表示这是 Jupyter 的**魔法命令**，不是纯 Python。

---

### 5.1 Exercise 1：遍历数组并修改数值

**题目要求**
用循环实现函数

$$Y = X^{2.8/X}$$

其中 `x` 是一个从 **11 到 85** 的 **75 个值**的数组。然后**逐个打印** `x` 和 `Y` 数组的**最后 4 个值**。

期望输出：

```
The 72nd element of x is  82
The 72nd element of y is  1.1623843156991178
The 73rd element of x is  83
The 73rd element of y is  1.1607534518329277
The 74th element of x is  84
The 74th element of y is  1.1591580160090038
The 75th element of x is  85
The 75th element of y is  1.157596831308393
```

**解题思路**

1. 先建两个**空列表 (empty list)** 装 x 和 y。
2. 循环 75 次。因为 `range(75)` 给的是 `0…74`，而我们要的 x 是 `11…85`，所以需要**平移**：`x = 10 + (step + 1)`，即 step=0 → 11，step=74 → 85。✅
3. 每一轮先 `append` 一个 x 值，**然后立刻用刚存进去的 `x[step]`** 去算 y。这一步是关键：`x[step]` 正好就是本轮刚追加的那个元素（因为追加前列表长度是 `step`，追加后下标 `step` 就是新元素）。
4. 幂运算用 `**`（Practical 特别提示）。

**完整代码**

```python
# 初始化两个空列表，一个存 'x' 一个存 'y'
x = []                              # [] 表示空 list，解释器准备好往里放东西，但现在什么都没有
y = []

# 循环 75 次，每次往两个列表各追加一个值
# 注意：把一个数升到另一个数的幂要用 ** 运算符（例如 2**3）
for step in range(75):              # step 依次取 0,1,2,...,74

    # 往 x 数组追加一个值
    x.append(10 + (step + 1))       # step=0 → 11；step=74 → 85。共 75 个值

    # 往 y 数组追加一个值
    y.append(x[step] ** (2.8 / x[step]))
                                    # x[step] 就是刚刚追加的那个 x 值
                                    # 指数是 2.8/x，随 x 增大而减小

# 打印 x 和 y 数组的最后四个值
print("The 72nd element of x is ", x[71])   # 第 72 个元素 → 下标 71（因为从 0 开始）
print("The 72nd element of y is ", y[71])

print("The 73rd element of x is ", x[72])
print("The 73rd element of y is ", y[72])

print("The 74th element of x is ", x[73])
print("The 74th element of y is ", y[73])

print("The 75th element of x is ", x[74])   # 最后一个元素 → 下标 74
print("The 75th element of y is ", y[74])
```

**输出解读**

```
The 72nd element of x is  82
The 72nd element of y is  1.1623843156991178
The 73rd element of x is  83
The 73rd element of y is  1.1607534518329277
The 74th element of x is  84
The 74th element of y is  1.1591580160090038
The 75th element of x is  85
The 75th element of y is  1.157596831308393
```

- x 的最后一个值是 **85**，正好是题目要求的上界 → **范围对了**。
- y 全部略大于 1，且**随 x 增大而缓慢减小**。这符合数学直觉：当 x 变大，指数 `2.8/x` 趋近 0，而任何数的 0 次方是 1，所以 `Y → 1⁺`。**这就是判断结果是否正确的方法**——不要只对答案，要看趋势是否合理。
- 注意 `print` 中逗号后自动多出一个空格，所以 "is" 和数字之间是**两个空格**（一个是字符串里自带的，一个是逗号带来的）。要复现给定输出，这个细节必须一致。

**常见错误**

- `x.append(step)` → x 从 0 开始，范围错。
- `y.append(x[step+1] ** ...)` → `IndexError: list index out of range`，因为下标 `step+1` 那个元素还不存在。
- 打印时写 `x[72]` 当作「第 72 个」→ 差一错误 (off-by-one)，实际是第 73 个。

---

### 5.2 讲解例：`if` / `else` 实现两段函数（50 个值）

这是 Exercise 2 之前的**示范代码**（不用自己写，但必须读懂）。

**规则**：
- 若 $X \le 20$，则 $Y = \dfrac{X}{12.5}$
- 否则 (else)，$Y = X^{12.5}$

```python
# 初始化两个空列表
x = []
y = []

for step in range(50):              # 循环 50 次，step = 0..49

    # 往 x 数组追加一个值
    x.append(step + 1)              # x = 1, 2, 3, ..., 50

    # 现在加一个条件语句来检查 x 的值
    # 注意多出来的一层缩进
    if x[step] <= 20:               # 如果当前 x 小于等于 20
        # 往 y 数组追加一个值
        y.append(x[step] / 12.5)    # 用第一个公式：除法
    else:                           # 否则（x > 20）
        # 往 y 数组追加一个值
        y.append(x[step] ** 12.5)   # 用第二个公式：12.5 次幂

# 打印 x 和 y 的前四个和后四个值
# 前四个
print("The 1st element of x is ", x[0])
print("The 1st element of y is ", y[0])
print("The 2nd element of x is ", x[1])
print("The 2nd element of y is ", y[1])
print("The 3rd element of x is ", x[2])
print("The 3rd element of y is ", y[2])
print("The 4th element of x is ", x[3])
print("The 4th element of y is ", y[3])

# 后四个
print("The 47th element of x is ", x[46])
print("The 47th element of y is ", y[46])
print("The 48th element of x is ", x[47])
print("The 48th element of y is ", y[47])
print("The 49th element of x is ", x[48])
print("The 49th element of y is ", y[48])
print("The 50th element of x is ", x[49])
print("The 50th element of y is ", y[49])
```

**输出**

```
The 1st element of x is  1
The 1st element of y is  0.08
The 2nd element of x is  2
The 2nd element of y is  0.16
The 3rd element of x is  3
The 3rd element of y is  0.24
The 4th element of x is  4
The 4th element of y is  0.32
The 47th element of x is  47
The 47th element of y is  7.965686757032835e+20
The 48th element of x is  48
The 48th element of y is  1.0363715136605023e+21
The 49th element of x is  49
The 49th element of y is  1.341068619663965e+21
The 50th element of x is  50
The 50th element of y is  1.7263349150062194e+21
```

**输出解读（重点）**

- 前 4 个：x=1→y=0.08，x=2→y=0.16……**等差增长，公差 0.08 = 1/12.5**。走的是**第一个分支**（x ≤ 20）。✅
- 后 4 个：数值变成 `7.96...e+20` 这种**科学计数法 (scientific notation)** —— `e+20` 表示 ×10²⁰。x=47 时 47¹²·⁵ ≈ 8×10²⁰。走的是**第二个分支**。✅
- **判断正确性的方法**：看两段的**数量级差异是否巨大**（0.08 vs 10²⁰），以及每段内部的**增长规律是否符合公式形式**（线性 vs 幂律）。
- 这就是老师说的「你会看到 y 有一个 step change（阶跃）」。

**三层缩进的结构（务必看清）**

```
for step in range(50):          ← 第 0 层
    x.append(...)               ← 第 1 层：属于 for
    if x[step] <= 20:           ← 第 1 层：属于 for
        y.append(...)           ← 第 2 层：属于 if
    else:                       ← 第 1 层：与 if 对齐
        y.append(...)           ← 第 2 层：属于 else
```

---

### 5.3 讲解例：`and` 语句 —— 「能跑但是错的代码」

**这是本周最重要的概念**，幻灯片、录音、Notebook 三处都讲了。

**任务**：创建 `X` 从 1 到 200，按三条规则算 `Y`：
- 若 X < 20：$Y = X/1.56$
- 若 X ≥ 20 **但** < 60：$Y = X^{0.35}$
- 若 X ≥ 60：$Y = 4.5X$

**两个版本**

```python
# Version 1 —— 会跑，但结果是错的
if x[step] < 20:
    <<action>>
elif x[step] >= 20:          # ❌ 没有上界！
    <<action>>
elif x[step] >= 60           # 永远到不了这里（而且这行还漏了冒号）
    <<action>>
```

```python
# Version 2 —— 正确
if x[step] < 20:
    <<action>>
elif x[step] >= 20 and x[step] < 60:    # ✅ 用 and 加上上界
    <<action>>
elif x[step] >= 60                       # 现在能到达了（原文同样漏了冒号）
    <<action>>
```

**Notebook 的解释（原文翻译）**：

> 第一个版本能运行，但会产生错误结果。为什么？如果你像 Python 解释器那样跟着代码指令走，**一旦 `x[step]` 大于 20，第二个条件语句就永远为真**。结果就是它永远不需要进到第三个分支。而在第二个版本中，一旦 `x[step]` 大于等于 60，第二个条件就不再为真了。

**老师的口头版本（更直白）**：

> "There's a certain point when x[step] becomes greater than or equal to 20 when this becomes true. It will no longer jump here ... it will start jumping in here. Now imagine I've got x values going all the way to 100. **Will it ever leave the middle action? It won't, will it?**"

**核心机制**：`if / elif / elif` 链是**互斥且按顺序求值**的——**第一个为 `True` 的分支被执行后，后面所有 `elif` 直接跳过**。所以**分支的顺序和边界必须共同保证「有且只有一个」条件成立**。

**两种正确写法**（都要会）：

```python
# 写法一：显式用 and 把区间两端都写死（Notebook 采用，最清晰、最不易错）
if   x < 20:                      pass   # (-∞, 20)
elif x >= 20 and x < 60:          pass   # [20, 60)
elif x >= 60:                     pass   # [60, +∞)

# 写法二：利用 elif 的「已经排除前面情况」特性，省略下界
if   x < 20:                      pass   # x < 20
elif x < 60:                      pass   # 能走到这里说明 x >= 20，所以等价于 [20,60)
else:                             pass   # 剩下的一定是 x >= 60
```

> Python 还支持链式比较 `if 20 <= x < 60:`，效果与 `and` 版本一致，但本课程按 Notebook 写法用 `and`。

**对比绘图代码**

```python
# 初始化：一个 x，两个 y（分别对应两个版本）
x = []
y_version1 = []
y_version2 = []

for step in range(200):             # x 从 1 到 200

    # 往 x 数组追加一个值
    x.append(step + 1)

    # ---- Version 1（错误版）----
    if x[step] < 20:
        y_version1.append(x[step] / 1.56)
    elif x[step] >= 20:             # 一旦 x>=20 就永远命中这里
        y_version1.append(x[step] ** 0.35)
    elif x[step] >= 60:             # 死代码 (dead code)，永远不会执行
        y_version1.append(4.5 * x[step])

    # ---- Version 2（正确版）----
    if x[step] < 20:
        y_version2.append(x[step] / 1.56)
    elif x[step] >= 20 and x[step] < 60:    # 加了上界
        y_version2.append(x[step] ** 0.35)
    elif x[step] >= 60:                      # 现在可达
        y_version2.append(4.5 * x[step])

# ---- 画图对比 ----
import matplotlib.pyplot as plt      # 导入 Matplotlib 以便画图
import numpy as np                   # NumPy 包 —— 下周细讲
fig = plt.figure(figsize=(8,8))      # 8×8 英寸画布
ax = plt.axes()                      # 创建坐标轴
ax.plot(np.array(x), np.log(y_version1), label='Version 1')   # 画版本 1（取对数）
ax.plot(np.array(x), np.log(y_version2), label='Version 2')   # 画版本 2
ax.set_title('Y as a function of X')
ax.legend(loc='upper left')          # 图例放左上
ax.set_ylabel('Y')
ax.set_xlabel('X')
plt.show()                           # 显示
```

**图的判读要点（`output_9_0.png`）**

- 两条线在 **x < 60** 的区域**完全重合**（因为在这个范围两个版本逻辑相同）。
- 在 **x = 60** 处，**Version 2 出现明显的向上跳跃 (step change)**，之后走 `4.5*x` 的线性（对数坐标下是对数曲线）；**Version 1 则毫无变化**，继续沿 `x**0.35` 平滑爬升。
- **这个「有没有台阶」就是判断逻辑是否正确的可视化标准。** 老师说得对：如果没有这张图对照，你根本不会发现 Version 1 错了——它不报错，只是安静地给出错误答案。

---

### 5.4 Exercise 2：三段函数 + 画图

**题目要求**

数组 X 含 1 到 1000 的值，按三条规则算 Y：
- 若 X ≤ 250：$Y = X^{1.03}$
- 若 X > 250 但 < 690：$Y = X^{1.2}$
- 若 X ≥ 690：$Y = X^{2.5}$

输出应像给定的示例图（`Practical2_example.png`）。

**解题思路**

直接套用 5.3 的 Version 2 模式：
1. `range(1000)` + `x.append(step+1)` → x = 1…1000。
2. 三个分支，**中间那个必须用 `and` 同时限定下界和上界**。
3. 注意题目边界是 **≤ 250**（含 250）和 **≥ 690**（含 690），中间是 **(250, 690)** 开区间——三段**恰好无缝且不重叠**地覆盖了整个整数范围。写条件时要严格对应：`<= 250`、`> 250 and < 690`、`>= 690`。

**完整代码**

```python
# 初始化两个空列表
x = []
y = []

for step in range(1000):            # step = 0..999，共 1000 次

    # 往 x 数组追加一个值
    x.append(step + 1)              # x = 1..1000

    #------'INSERT CODE HERE'------
    # 加条件语句检查 x 的值；注意额外的缩进
    if x[step] <= 250:              # 第一段：x ∈ [1, 250]
        y.append(x[step] ** 1.03)
    elif x[step] > 250 and x[step] < 690:    # 第二段：x ∈ (250, 690)，必须用 and
        y.append(x[step] ** 1.2)
    elif x[step] >= 690:            # 第三段：x ∈ [690, 1000]
        y.append(x[step] ** 2.5)
    #------------------------------

# 导入绘图包
import matplotlib.pyplot as plt     # 导入 Matplotlib 以便画图
import numpy as np                  # NumPy 包 —— 下周细讲
fig = plt.figure(figsize=(8,8))
ax = plt.axes()
ax.plot(np.array(x), np.log(y))     # 对 y 取自然对数再画，否则最后一段会把前两段压平
ax.set_title('Y as a function of X')
ax.set_ylabel('Y')
ax.set_xlabel('X')
plt.show()
```

**输出**

```
Text(0.5, 0, 'X')
```

以及图像 `output_11_1.png`。

**关于那行 `Text(0.5, 0, 'X')`**

这**不是报错**，也不是 `print` 出来的。它是 Jupyter 的行为：**代码单元最后一个表达式的返回值会被自动回显 (echo)**。`ax.set_xlabel('X')` 返回一个 `matplotlib.text.Text` 对象，Jupyter 就把它的 repr 打印了出来（`0.5, 0` 是标签在坐标轴上的相对位置）。

**如何消掉它**：在该语句末尾加分号 `ax.set_xlabel('X');`，或者把 `plt.show()` 放在最后（本例已有 `plt.show()`，输出顺序是转换 md 时的呈现问题）。总之**看到这类 `<matplotlib...object at 0x...>` 或 `Text(...)` 的输出不要慌，它是无害的回显**。

**图的判读要点**

在 `log(y)` 对 `x` 的图上应该看到**两处明显的斜率突变**：
- **x = 250** 处：从 `1.03*ln(x)` 变成 `1.2*ln(x)`，曲线向上一折（有一个小的向上跳跃，因为 250^1.2 > 250^1.03）；
- **x = 690** 处：变成 `2.5*ln(x)`，向上一个**更大的跳跃**。

如果曲线全程平滑无折点 → 说明条件写错了（很可能中间那段漏了 `and`）。

---

### 5.5 讲解例：嵌套循环遍历单词

**关键提示**：这里**不用 `range()`**，因为「我们处理的不是数值，也不是在遍历整数」。**`for` 循环可以遍历任何 list 的成员，无论是数值还是字符串。**

**基础版**

```python
# 创建两个单词列表
list1 = ['Hello','Goodbye']
list2 = ['George','Frank','Susan','Sarah']

for word1 in list1:            # 外层：word1 依次取 'Hello','Goodbye'
    for word2 in list2:        # 内层：对每个 word1，word2 走完 list2 一整轮
        print(word1)
        print(word2)
```

输出（共 2×4 = 8 组，16 行）：

```
Hello
George
Hello
Frank
Hello
Susan
Hello
Sarah
Goodbye
George
Goodbye
Frank
Goodbye
Susan
Goodbye
Sarah
```

**解读**：`Hello` 连续出现 4 次配完 list2 的 4 个名字，然后才轮到 `Goodbye`。**这直观证明了「内层循环先跑完，外层才前进一步」。**

**改进版：拼接字符串**

```python
list1 = ['Hello','Goodbye']
list2 = ['George','Frank','Susan','Sarah']

for word1 in list1:
    for word2 in list2:
        print(word1 + ' ' + word2)    # 用 + 把三段字符串拼起来：单词 + 空格 + 单词
```

输出：

```
Hello George
Hello Frank
Hello Susan
Hello Sarah
Goodbye George
Goodbye Frank
Goodbye Susan
Goodbye Sarah
```

**注意**：`+` 作用于字符串是**拼接 (concatenation)**，作用于数字是加法。`' '` 是一个只含一个空格的字符串，用来分隔。

**加条件版：只输出含 Susan 的**

```python
list1 = ['Hello','Goodbye']
list2 = ['George','Frank','Susan','Sarah']

for word1 in list1:
    for word2 in list2:
        if word2 == "Susan":              # 字符串也能用 == 比较；注意是双等号
            print(word1 + ' ' + word2)
```

输出：

```
Hello Susan
Goodbye Susan
```

**要点**：`==` **可以用于字符串**（区分大小写，且必须完全一致）。老师说这是「展示你在遍历数组时可以非常有选择性」。

---

### 5.6 Exercise 3：三重嵌套循环 + 条件

**题目要求**

三个列表：

```python
list1 = ['Maths','Physics','Programming','Chemistry']
list2 = ['is','can be','is not']
list3 = ['enjoyable','awful!','ok, I guess','....']
```

创建**三重嵌套循环**，只在 list1 的词是 `'Physics'` **且** list2 的条目是 `'can be'` 时输出。

期望输出：

```
Physics can be enjoyable
Physics can be awful!
Physics can be ok, I guess
Physics can be ....
```

**解题思路**

- 三层嵌套 → 总共 4×3×4 = **48 次内层迭代**，但只有 1×1×4 = **4 次**满足条件。
- 判断条件涉及**两个变量同时成立** → 用 `and` 连接两个 `==` 比较。
- 条件放在**最内层**（第三层循环体内），因为只有到那时 `word3` 才有值。
- Notebook 提示「There are multiple ways to achieve this」——也可以把 `if word1 == "Physics":` 放在第一层之后、把 `if word2 == "can be":` 放在第二层之后，这样效率更高（不用进入无用的内层）；但放最内层写法更简单直白。

**完整代码**

```python
# 创建三个单词列表
#------'INSERT CODE HERE'------
list1 = ['Maths','Physics','Programming','Chemistry']
list2 = ['is','can be','is not']
list3 = ['enjoyable','awful!','ok, I guess','....']

for word1 in list1:                   # 第 1 层：学科
    for word2 in list2:               # 第 2 层：系动词短语
        for word3 in list3:           # 第 3 层：形容词/评价
            if word1 == "Physics" and word2 == "can be":
                                      # 两个条件必须同时为真，用 and 连接
                print(word1 + ' ' + word2 + ' ' + word3)
                                      # 三段拼接，中间各加一个空格
#------------------------------
```

**输出**

```
Physics can be enjoyable
Physics can be awful!
Physics can be ok, I guess
Physics can be ....
```

**输出解读**：正好 4 行，对应 list3 的 4 个元素——因为 `word1` 和 `word2` 都被条件锁死了，只有 `word3` 在变。**行数 = 4 就是结果正确的快速验证方式。**

**更高效的等价写法**（值得掌握）：

```python
for word1 in list1:
    if word1 == "Physics":                # 提前过滤，不匹配就跳过整个内层
        for word2 in list2:
            if word2 == "can be":
                for word3 in list3:
                    print(word1 + ' ' + word2 + ' ' + word3)
```

---

### 5.7 Exercise 4：找出满足条件的变量组合

**题目要求**

两个变量 `x` 和 `y`，分别由两个遍历 80 个值的循环给出：

```python
for x in range(80):
    for y in range(80):
        [do something]
```

找出哪些 `x`、`y` 组合通过函数

$$Z = Y + X^{2}$$

得到 `Z = 80`。

**解题思路**

- 这是**穷举搜索 (brute force search)**：80×80 = **6400 种组合**全试一遍。
- 每种组合算出 `z`，用 `if z == 80:` 判断，命中就打印。
- 注意这里**迭代变量直接叫 `x` 和 `y`**（不再是 `step` + 索引），这是 `for` 循环的另一种典型用法——**变量本身就是值，不需要列表**。

**完整代码**

```python
#------'INSERT CODE HERE'------
for x in range(80):                # 外层：x = 0..79
    for y in range(80):            # 内层：对每个 x，y 走 0..79
        z = y + x**2.0             # 计算 z；注意 2.0 是浮点数，所以 z 是 float
        if z == 80:                # 检查是否恰好等于 80
            print('x = ', x)
            print('y = ', y)
#------------------------------
```

**输出**

```
x =  1
y =  79
x =  2
y =  76
x =  3
y =  71
x =  4
y =  64
x =  5
y =  55
x =  6
y =  44
x =  7
y =  31
x =  8
y =  16
```

**输出解读（验算，重要）**

| x | x² | 需要的 y = 80 − x² | 是否在 0–79 内？ |
| --- | --- | --- | --- |
| 0 | 0 | 80 | ❌ 超出 `range(80)`（上限 79），所以**没有输出** |
| 1 | 1 | 79 | ✅ |
| 2 | 4 | 76 | ✅ |
| 3 | 9 | 71 | ✅ |
| 4 | 16 | 64 | ✅ |
| 5 | 25 | 55 | ✅ |
| 6 | 36 | 44 | ✅ |
| 7 | 49 | 31 | ✅ |
| 8 | 64 | 16 | ✅ |
| 9 | 81 | −1 | ❌ 负数，不在范围内 |

- **共 8 组解**，与输出完全一致 ✅
- **关键洞察**：`x = 0, y = 80` 在数学上也满足，但因为 `range(80)` 只到 79，**这个解被搜索范围排除了**。这提醒你：**穷举法的结果完全取决于你设定的搜索范围**——范围写错了，你会以为「没有更多解」。
- x ≥ 9 时 x² > 80，`y` 必须为负，而 `range` 只给非负数，所以自然终止。
- 输出是**按 x 升序、y 降序**排列的，因为外层 x 从小到大，而每个 x 对应的 y 由 80−x² 决定，随 x 增大而减小。这个规律本身就是结果正确的旁证。

**关于 `x**2.0` 与浮点比较的一个提醒**

`x**2.0` 用的是浮点指数，所以 `z` 是 `float`（如 `80.0`），与整数 `80` 比较时 Python 会自动转换，`80.0 == 80` 为 `True`，**本例没问题**。但要知道：**浮点数的 `==` 比较在一般情况下是危险的**（例如 `0.1 + 0.2 == 0.3` 是 `False`）。更稳妥的写法是用 `x**2`（整数幂），或用 `abs(z - 80) < 1e-9`。

---

### 5.8 Exercise 5：Bob Newby 的密码破解（五重嵌套循环）

**题目背景**

模仿《Stranger Things》第二季中 Bob Newby 在 Hawkins 实验室破解密码的桥段。任务：找到一个**每次运行都不同**的密码。这个密码由 Python 内部函数生成，是一个**含 5 个数字的字符串**。我们要写一个 **5 层嵌套循环**，把 5 个不同的数字组合成一个「词」，当它与内部生成的密码匹配时，把这个（正确的）尝试打印出来。

Notebook 给的提示代码：

```python
password_attempt = letter1+letter2+letter3+letter4+letter5
if password_attempt == password_string:
    print("Passwords match!, attempted password = ",password_attempt)
```

以及一个延伸问题：**「看看走了多少步才找到正确密码？」**

**先看密码是怎么生成的**

```python
# 下面这行导入了一个模块（见 Practical 3），然后创建一个 5 位随机数字的字符串
from random import randint
n = 5
password_string = ''.join(["{}".format(randint(0, 9)) for num in range(0, 5)])
print("password = ", password_string)
```

**逐段拆解这行「密集」代码**（考试可能问）：

1. `randint(0, 9)` → 随机整数 0–9（**两端都含**）。
2. `"{}".format(...)` → 把这个整数**转成字符串**，如 `3` → `"3"`。
3. `[... for num in range(0, 5)]` → **列表推导式 (list comprehension)**，重复上述操作 5 次，得到形如 `['3','5','9','8','8']` 的列表。（`num` 只是占位，没用到。）
4. `''.join([...])` → 用**空字符串作分隔符**把列表元素连成一个字符串 → `"35988"`。

> 注：`n = 5` 这行其实**没有被后面用到**（`range(0, 5)` 里的 5 是硬编码的）——这是原代码里的一个小冗余，不影响运行。

**完整代码（含破解循环）**

```python
from random import randint
n = 5
password_string = ''.join(["{}".format(randint(0, 9)) for num in range(0, 5)])
print("password = ", password_string)

# 现在创建一个 5 层嵌套循环，成功匹配密码时打印

#------'INSERT CODE HERE'------

# 第一层循环
for step1 in range(10):                    # 第 1 位数字：0..9
    letter1 = str(step1)                   # 把数字转成字符串（否则不能用 + 拼接）
    # 第二层循环
    for step2 in range(10):
        letter2 = str(step2)
        # 第三层循环
        for step3 in range(10):
            letter3 = str(step3)
            # 第四层循环
            for step4 in range(10):
                letter4 = str(step4)
                # 第五层循环
                for step5 in range(10):
                    letter5 = str(step5)
                    password_attempt = letter1+letter2+letter3+letter4+letter5
                                               # 五个字符拼成一个 5 位字符串

                    if password_attempt == password_string:
                        print("Passwords match!, attempted password = ", password_attempt)

#------------------------------
```

**输出（每次运行密码不同）**

```
password =  35988
Passwords match!, attempted password =  35988
```

**输出解读**

- 两行的数字**必须完全一致**，否则说明比较逻辑或拼接顺序出了问题。
- 只打印**一行** match —— 因为 5 位数字组合是唯一的，穷举空间里恰好只有一个匹配。
- **搜索空间大小 = 10⁵ = 100,000 种组合**（每层 10 种 × 5 层）。这就是老师说的「very naive passcode」——真实密码空间要大得多。

**为什么必须 `str()` 转换？**

如果直接写 `password_attempt = step1+step2+step3+step4+step5`，那是**数字相加**（例如 3+5+9+8+8 = 33），完全不是我们要的拼接。而如果写 `letter1 + step2` 会得到：

```
TypeError: can only concatenate str (not "int") to str
```

**延伸练习：数一数走了多少步**

```python
from random import randint
password_string = ''.join(["{}".format(randint(0, 9)) for num in range(0, 5)])
print("password = ", password_string)

counter = 0                                        # 计步器，循环外初始化为 0

for step1 in range(10):
    letter1 = str(step1)
    for step2 in range(10):
        letter2 = str(step2)
        for step3 in range(10):
            letter3 = str(step3)
            for step4 in range(10):
                letter4 = str(step4)
                for step5 in range(10):
                    letter5 = str(step5)
                    counter = counter + 1          # 每尝试一次就 +1（也可写 counter += 1）
                    password_attempt = letter1+letter2+letter3+letter4+letter5
                    if password_attempt == password_string:
                        print("Passwords match!, attempted password = ", password_attempt)
                        print("Number of steps taken = ", counter)
```

**预期结果的解读**：因为嵌套循环是按 `00000, 00001, ..., 99999` 的顺序枚举的，**步数正好等于「密码作为整数的值 + 1」**。例如密码是 `35988`，步数就是 35989。密码是 `00007` 则步数是 8。**这是验证计步器写对了的绝妙方法。**

注意：**计步器必须在所有循环之外初始化**。如果写在某层循环内部，它会被反复清零，得到错误的结果——这是常见错误。

**（可选）提前退出**：本代码在找到密码后仍会跑完剩余组合。真实场景会用 `break` 跳出循环，但 `break` 只能跳出**一层**，五层嵌套里要跳出全部需要额外技巧（本周不涉及）。

---

### 5.9 Practical 结尾的自我总结（Notebook 原文）

> 在这次 practical 中，我们：
> - 继续使用 **`for` 循环**来高效地重复动作
> - 用循环**逐元素遍历数组**
> - 在循环内修改数值，看数据如何一步步变化
> - 引入**条件语句**：`if` 测试条件，`else` 和 `elif` 在不同结果间选择
> - **结合循环与条件**，根据条件套用不同的方程
> - 使用**嵌套循环**处理多于一维的数据
> - 在嵌套循环内用条件来：控制打印什么、找出满足特定标准的值
> - 练习仔细阅读指令，并让代码输出与期望结果匹配
>
> 🧠 重点是学会**程序如何做决策、如何自动重复任务**——这是几乎所有真实世界代码的核心思想。

---

## 六、易错点 / 重点难点

### 6.1 `=` 与 `==` 混淆（Notebook 红色警告）

```python
x = 3        # 赋值 assignment：把 3 存进变量 x
x == 3       # 比较 comparison：问「x 等于 3 吗？」，返回 True 或 False
```

- 在 `if` 里误用 `=`：**Python 3 会直接语法报错** `SyntaxError: invalid syntax`（这算「幸运」，因为报错了）。
- 在还没赋值的变量上写 `x == 3` → `NameError: name 'x' is not defined`（老师提到的场景）。

### 6.2 ⭐ `elif` 链缺上界 —— 「能跑但是错的代码」

**本周最重要的坑**，见 5.3 详解。

```python
# ❌ 错
elif x >= 20:            # 一旦 x ≥ 20 就永远命中，后面的分支成了死代码

# ✅ 对
elif x >= 20 and x < 60:
```

**症状**：**不报错**，程序照跑，结果安静地错掉。只能靠**画图 / 抽样验算 / 对照预期输出**发现。
**心法**：老师的 "make it work, make it right, make it quick" + "Code that works isn't necessarily correct!!"
**自查方法**：写完分支后，逐个问「哪些 x 值会落进这一条？」把区间画在数轴上，检查是否**既无重叠也无遗漏**。

### 6.3 索引从 0 开始 —— 差一错误 (off-by-one)

- 「第 n 个元素」的下标是 `n-1`。第 72 个 → `x[71]`。
- `range(75)` 给 `0…74`，**不含 75**。
- `randint(0, 9)` 给 `0…9`，**含 9** —— **与 `range` 的行为不一致，极易记混**。

| 函数 | 范围 | 是否含上界 |
| --- | --- | --- |
| `range(n)` | 0 … n−1 | ❌ 不含 |
| `randint(a, b)` | a … b | ✅ 含 |

**越界报错**：`IndexError: list index out of range`

```python
x = [1, 2, 3]
print(x[3])      # ❌ IndexError，最大下标是 2
```

### 6.4 缩进错误 (IndentationError)

冒号 `:` 之后**必须**缩进。常见报错：

```
IndentationError: expected an indented block
```

反过来，不该缩进却缩进了：

```
IndentationError: unexpected indent
```

或者同一块里缩进量不一致：

```
IndentationError: unindent does not match any outer indentation level
```

**建议**：一律用 **4 个空格**，不要混用 Tab 和空格（混用会导致 `TabError`）。

**缩进层级决定语义**（务必分清下面两段的区别）：

```python
# A：条件在内层，每一组 (word1, word2) 都检查
for word1 in list1:
    for word2 in list2:
        if word2 == "Susan":
            print(word1, word2)

# B：条件在外层——语法合法，但含义完全不同
for word1 in list1:
    if word1 == "Hello":       # 只在外层过滤
        for word2 in list2:
            print(word1, word2)
```

### 6.5 缺少冒号 `:`

Notebook 示例代码里就有这个错（`elif x[step] >= 60` 后面漏了冒号）：

```
SyntaxError: expected ':'
```
（旧版本 Python 报 `SyntaxError: invalid syntax`）

`for`、`if`、`elif`、`else`、`while`、`def` 之后**都要有冒号**。

### 6.6 `else` 后面不能跟条件

Notebook 的示例代码里也有这个错：

```python
else x < y:      # ❌ SyntaxError
```

**规则**：
- `if <条件>:` ✅
- `elif <条件>:` ✅
- `else:` ✅（**不带条件**）

### 6.7 `**` vs `^`

Python 的幂运算是 `**`，**不是 `^`**。`^` 是按位异或 (bitwise XOR)，`2^3` 会得到 `1` 而不是 `8`——**不报错，静默给错答案**。

### 6.8 变量未定义 (NameError)

老师专门提到：`for prime in primes:` 中如果 `primes` 没先创建：

```
NameError: name 'primes' is not defined
```

在 Jupyter Notebook 里这个错**特别容易发生**，因为你可能**跳着运行了单元格**，或者重启了内核 (kernel) 导致所有变量丢失。**遇到 NameError 先想：定义那个变量的单元格我跑过吗？**

### 6.9 字符串与数字不能直接相加 (TypeError)

```python
"3" + 5          # ❌ TypeError: can only concatenate str (not "int") to str
str(5) + "3"     # ✅ "53"
5 + int("3")     # ✅ 8
```

Exercise 5 里 `str(step1)` 的转换就是为了避开这个坑。

### 6.10 `append` 返回 `None`

```python
x = x.append(5)     # ❌ x 变成 None！后续所有操作都会 AttributeError
x.append(5)         # ✅ 原地修改，不要接收返回值
```

后续报错通常是 `AttributeError: 'NoneType' object has no attribute 'append'`。

### 6.11 循环内追加与索引的配合

```python
for step in range(75):
    x.append(...)
    y.append(x[step] ** ...)     # ✅ x[step] 就是刚追加的那个
```

原理：追加前 `len(x) == step`，追加后新元素的下标恰是 `step`。
如果把 `x.append(...)` 写在 `y.append(x[step]...)` **之后**，就会 `IndexError`（那个元素还不存在）。**顺序很重要。**

### 6.12 计数器初始化位置

```python
counter = 0                 # ✅ 在所有循环之外
for a in range(10):
    # counter = 0           # ❌ 放这里会每轮清零
    for b in range(10):
        counter += 1
```

### 6.13 浮点数比较

`if z == 80:` 在本周的例子里能用（因为 `x**2.0` 对小整数是精确的），但通用做法应是容差比较。**知道这个陷阱存在即可，本课暂不深究。**

### 6.14 Jupyter 里「多出来」的输出

看到 `Text(0.5, 0, 'X')`、`[<matplotlib.lines.Line2D at 0x...>]` 这类东西——**不是报错**，是最后一个表达式的自动回显。加分号 `;` 可消除。

### 6.15 关于「overhead」的性能直觉

条件语句和 `for` 循环会让 CPU「停下来检查再回去」，**引入开销 (overhead)**。本课程规模下完全无感，但要知道：**这正是 Week 3 引入 NumPy 向量化的动机**。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
| --- | --- | --- |
| loop | 循环 | 让一段代码重复执行的结构 |
| `for` loop | for 循环 | 遍历一个可迭代对象的每个元素，逐个执行动作 |
| iterate / iteration | 迭代 | 循环的一「轮」；遍历元素的过程 |
| iterating variable | 迭代变量 | `for` 后面那个每轮被赋新值的变量，名字随便取 |
| iterable | 可迭代对象 | 能被 `for` 逐个取出元素的东西（list、range、字符串等） |
| conditional statement | 条件语句 | 根据条件真假决定执行哪段代码 |
| `if` / `elif` / `else` | 如果 / 否则如果 / 否则 | 条件分支三件套；`elif` 是 "else if" 的缩写 |
| condition | 条件 | 一个能求值为 `True`/`False` 的表达式 |
| `and` | 逻辑与 | 两个条件同时为真才为真，用来给区间加边界 |
| nested loop | 嵌套循环 | 循环里面套循环，用于处理二维及以上的数据 |
| outer loop | 外层循环 | 嵌套结构中最外面的循环；内层跑完一整轮它才前进一步 |
| control flow | 控制流 | 程序执行的路径与顺序 |
| flow diagram | 流程图 | 用图形表示程序（或电路）执行流程的图 |
| indentation | 缩进 | Python 用行首空格表示代码块归属，冒号后必须缩进 |
| colon `:` | 冒号 | 语句块的开始标记，`for`/`if`/`else` 后都要有 |
| comment | 注释 | `#` 之后的内容，解释器忽略，写给人看 |
| syntax | 语法 | 一门语言的规则与写法风格 |
| syntax highlighting | 语法高亮 | 编辑器把关键字着色，使代码更易读 |
| operator | 运算符 | `+`、`**`、`==`、`<` 这类符号 |
| assignment | 赋值 | 用 `=` 把值存进变量 |
| comparison | 比较 | 用 `==`、`<`、`>=` 等判断关系，结果是布尔值 |
| index / indexing | 索引 | 用下标取元素；**Python 从 0 开始** |
| off-by-one error | 差一错误 | 下标或次数算错 1 的经典 bug |
| element / entry | 元素 / 条目 | 数组或列表中的单个成员 |
| array | 数组 | 一堆元素的集合的泛称，可 1、2、3…维 |
| list | 列表 | Python 的可变数组类型，用 `[]`，本课程主用 |
| tuple | 元组 | 不可变的序列，用 `()`，内存效率更高 |
| mutable / immutable | 可变 / 不可变 | 创建后能否修改内容 |
| `append()` | 追加 | 在列表末尾加一个元素，原地修改 |
| empty list | 空列表 | `[]`，准备好接收元素但目前没有 |
| `range()` | 范围函数 | 生成 `0…n-1` 的整数序列，**不含上界** |
| `str()` | 字符串转换 | 把数字等对象转成字符串 |
| `join()` | 连接 | 用指定分隔符把字符串序列连成一个字符串 |
| concatenation | 拼接 | 用 `+` 把字符串首尾相连 |
| list comprehension | 列表推导式 | `[expr for x in seq]`，一行生成列表的紧凑写法 |
| `randint()` | 随机整数 | 生成闭区间内的随机整数，来自 `random` 模块 |
| brute force | 穷举 / 暴力搜索 | 把所有可能组合都试一遍 |
| counter | 计数器 | 记录循环执行次数的变量，必须在循环外初始化 |
| interpreted language | 解释型语言 | 逐行解释执行，不必预先声明类型（Python） |
| compiled language | 编译型语言 | 需先编译、需声明类型，速度快（C、Fortran） |
| interpreter | 解释器 | 逐行读取并执行 Python 代码的程序 |
| module | 模块 | 可导入的代码包（Week 3 详讲） |
| NumPy | 数值 Python | 高效数组模块，Week 3 起全课程使用 |
| Matplotlib | 绘图库 | Python 最常用的画图模块 |
| Jupyter Notebook | Jupyter 笔记本 | 混合代码、输出与文字的交互式环境，本课程的工作平台 |
| Google Colab | 谷歌 Colab | 云端免费 Jupyter 环境 |
| kernel | 内核 | Notebook 背后执行代码、保存变量的进程 |
| magic command | 魔法命令 | Jupyter 特有的 `%` 开头命令，如 `%cd` |
| overhead | 开销 | 非核心计算的额外时间成本（如条件检查） |
| scientific notation | 科学计数法 | `7.96e+20` 表示 7.96×10²⁰ |
| step change | 阶跃变化 | 曲线在分段点处的突变，用来验证条件逻辑 |
| dead code | 死代码 | 永远不会被执行到的代码分支 |
| silent failure | 静默失败 | 不报错但结果错误，最难发现的 bug |
| `NameError` | 名称错误 | 用了未定义的变量 |
| `IndexError` | 索引错误 | 下标超出列表范围 |
| `SyntaxError` | 语法错误 | 代码写法不合规（漏冒号、`else` 带条件等） |
| `IndentationError` | 缩进错误 | 缩进缺失、多余或不一致 |
| `TypeError` | 类型错误 | 对不兼容的类型做运算（如 str + int） |
| bit / byte | 位 / 字节 | 1 byte = 8 bits；计算机存储信息的最小单位 |
| 64-bit | 64 位 | 现代机器与 Python 的默认数值精度 |
| Conway's Game of Life | 康威生命游戏 | 四条简单规则产生复杂行为的细胞自动机，Week 4 内容 |
| plate tectonic boundary | 板块构造边界 | Week 6 火山数据将验证喷发点与之吻合 |
| shapefile | 形状文件 | GIS 矢量数据格式，Week 7 内容 |
| cluster analysis | 聚类分析 | 把观测数据分组的机器学习方法，Week 9 内容 |
