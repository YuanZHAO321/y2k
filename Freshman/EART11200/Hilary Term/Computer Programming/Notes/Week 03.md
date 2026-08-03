# Week 3 — 模块与函数、NumPy 数组入门 (Modules, Functions and the NumPy Module)

> 课程：EART11200 The Natural Scientist's Toolkit — Computer Programming（Hilary Term，共 9 周）
> 材料：Lecture_3(1).pdf（讲义）+ 11-Feb 课堂转写（transcript）+ Practical_3.ipynb（配套 Notebook）
> 本周关键词：`def`、`return`、`import`、模块 (module)、函数 (function)、`numpy`、`np.zeros`、`np.array`、切片 (slicing)、逐元素运算 (element-wise operation)、向量化 (vectorisation)

---

## 一、本周主题

本周是整门课的**第一个转折点**。前两周（Week 1–2）做的是所谓 **"Vanilla Python"（纯原生 Python）**：数据类型 (data types)、列表 (list)、元组 (tuple)、循环 (loop)、条件语句 (conditional)、基本运算符 (operator)。老师在课上明确说：那些练习"有点抽象、有点飘 (nebulous)"——你只是东写一段、西写一段代码，然后整本 notebook 跑一遍。

本周开始把这些零散的代码**组织起来**，并且**换掉数据容器**：

1. **函数 (function)**：把重复使用的代码封装成一个可以反复调用的块。用 `def` 关键字自己定义。
2. **模块 (module)**：一个 `.py` 文件就是一个模块，里面装着一堆函数和变量；用 `import` 导入后，通过 `.`（点运算符）访问其中的函数。
3. **NumPy 模块**：从本周起 **不再用 list 存数值数据**，改用 `numpy` 数组 (array)。老师原话大意：「从这一点开始我们不再使用 lists……如果你在 Python 里做任何真正有用的事情，都会被期望把数字存进 NumPy arrays。」
4. **整数组运算 (operations on entire arrays)**：NumPy 允许 `array1 + array2`、`A * B` 这样直接对整个数组做逐元素运算，不需要写 `for` 循环——代码更短、更快、更易读。

### 课程整体地图（老师在课上复述的 course layout）

| 周次 | 内容 |
|---|---|
| 1–2 | Vanilla Python：data types、loops、basic operations、conditionals |
| **3** | **Modules and Functions + the NumPy module（本周）** |
| 4 | Conway's Game of Life（康威生命游戏）——用 numpy 数组 + for 循环 + 逻辑解 4 条规则，并做出屏幕动画 |
| 5 | Differential Equations（微分方程） |
| 6–7 | Pandas and data discovery（数据加载与探索）、Geospatial analysis（地理空间分析） |
| 8–9 | Statistical Analysis（统计分析）、Cluster Analysis（聚类分析，用 Scikit-learn） |
| 10–12 | 制作一本 notebook 作为评估作业 (assessment)，题目从 Week 4–9 中自选 |

老师强调本周的位置：「到这周为止（包括这周）学的东西，是**任何编程语言的起点**。不管你学 Python、C、Java 还是 PHP，你都要学会搭这些构件——数字与字符串的基本表示、加上逻辑。所以前几周的东西是**可以迁移**到别的语言的。」他还打了一个比方：就像人类语言一样，当你在一门语言里足够自信了，就可以同时开始学第二门。

从 Week 4 起课程会**变得不那么抽象**——你能看到自己在造什么（动画、微分方程解、真实数据）。

---

## 二、核心概念

### 2.1 为什么要用函数和模块？（Why modular programming）

老师从"痛点"讲起，这几条理由要记住（考试/报告里能直接用）：

1. **代码会越写越乱 (messy / nebulous)**。一直往下写，几百行之后没人（包括你自己）读得懂。
2. **重复写 = 更容易出错**。「如果你把同一件事写了 10 遍，我们都会犯错，写的次数越多，你越可能犯错。」
3. **修 bug 只需改一处**。函数只写一次；发现问题只在一个地方修。若复制粘贴了 10 份，你得逐份追踪哪份对哪份错。
4. **结构清晰，便于分工**。写软件就像写论文/报告：有清楚分工的章节。团队里一个人做可视化模块、一个人做计算模块、一个人做数据读取模块。
5. **可分享 (sharing) 与独立测试 (independent testing)**。写好的模块可以直接交给别人 `import`。
6. **版本控制 (version control)**。本课不教，但属于软件工程最佳实践 (best practices)：写好一版打个 tag，分享给团队、发布给公众、保留历史。老师说他自己的课程材料放在 GitHub 上，多年迭代，所有版本历史都在。**"只有当底层是函数和模块的时候，你才真正能做到这件事。"**
7. **端用户 (end user) 只看到冰山一角**。你用 `numpy` 时看不到它底下几十万行的"脏活"，因为它已经成熟 (mature) 了。你希望自己的软件也是这样：清楚知道哪部分需要改、哪部分已经稳定。

讲义里那张流程图也是同一个意思：一个程序可以拆成 `INPUT DATA` → `FIND SPECIFIC ENTRY` → `GENERATE STATISTICS` 这样彼此独立的模块。

### 2.2 函数 (function) 的语法结构

讲义里的 **syntax check!**（必背五条）：

- `def` 关键字**通过名字定义一个函数**（告诉解释器：我要定义函数了）。
- **圆括号 `()`** 里可以放一串函数需要的输入 (inputs / arguments / parameters)。
- **函数名 + 输入表以冒号 `:` 结尾**。
- **下一行（即函数的内部工作）缩进 4 个空格 (indented by 4 spaces)**。
- **`return` 语句关闭函数定义** (closes the function definition)。

```python
# 定义一个叫 test 的函数。它只做一件事：向屏幕打印一句话。
def test():                                            # def = 定义函数；test = 函数名；() 里没有参数；行尾冒号必须有
    print("All work and no play makes Jack a dull boy")  # 缩进 4 空格 = 函数体 (function body)
    return                                             # return 后面什么都不跟 = 返回 None，仅表示函数结束

# 调用 (call) 这个函数：写函数名 + 一对括号
test()
```

输出：

```
All work and no play makes Jack a dull boy
```

**输出含义**：函数体里的 `print` 被执行了一次。若什么都没打印出来，说明你只是定义了函数却没有调用它（定义本身不产生任何输出——老师在课上专门说过：「跑完这个 cell 好像什么都没发生。但其实发生了！」——这句原本是说 `import numpy`，对 `def` 同样成立）。

**关于 `return` 的三个层次**（老师课上讲的）：

- `return`（后面空着）→ 返回 `None`，纯粹表示"函数到此为止"。
- `return z` → 把变量 `z` 交还给调用者。
- `return a, b, c` → 可以一次返回多个变量（返回一个元组 tuple）。

老师把它和上周的经验连起来：「就像你写 `x = function(y)`，那就是把一个值返回来放进 `x`。这些东西是很好地串在一起的。」

**函数一旦被解释器读过（编译过），就"存"在那里，任何后续代码都能调用它。**

### 2.3 怎么调用同一个函数 30 次？

老师在课堂上向学生提问：「我怎么把这个函数 `test` 调用 30 次？我可以写 30 遍，但我真的不想。」学生答：用 `for` 循环。

```python
for step in range(30):   # range(30) 产生 0,1,2,...,29 共 30 个值
    test()               # 每次循环调用一次 test()，共打印 30 行
```

老师还补充：也可以用条件语句 (conditional statement)，只在某个条件为真时才调用这个函数。**这就是把前两周学的东西（loop + conditional）和本周的函数结合起来，把代码压缩得更紧凑。**

### 2.4 模块 (module) 是什么、怎么写、怎么用

**定义**：模块是一个包含 Python 定义和语句的**文件**。文件名 = 模块名 + `.py` 后缀。

老师在课上演示的心智模型：

假设我有一个文件 `module_name.py`，里面写着：

```python
# ---- 文件 module_name.py 的内容 ----
def greeting(name):                 # 定义函数 greeting，接受一个参数 name
    print("Hello ", name)           # 打印 "Hello <name>"
    return                          # 结束函数
```

那么在另一个 `.py` 文件或 notebook 里：

```python
import module_name                  # 导入这个模块（文件名去掉 .py）
module_name.greeting("David")       # 用 . 运算符访问模块里的函数
```

输出：`Hello  David`

**关键点**：
- **`import` 之后，解释器让你通过 `模块名.函数名` 访问该文件里定义的所有函数。**
- 「一旦导入了 numpy，你就能用 `numpy.max`、`numpy.min`、`numpy.multiply`——这些都是 numpy 模块里各自独立的函数，numpy 有海量的函数。」
- **模块数量没有上限**。做软件时你会先想：我要怎么切分不同的部分？（可视化一块、计算一块、数据读取一块）团队里不同的人可以并行做不同模块——这正是 GitHub 存在的意义（它编排 orchestrate 不同人的贡献）。

**Python 解释器必须"看得见"这个模块**（讲义原话）：所以模块通常要
- 放在**同一个目录 (same directory)** 下，或
- 在 **`PYTHONPATH`** 里，或
- 在代码里明确指出模块的位置。

### 2.5 `import ... as ...`（起别名）

```python
import numpy as np      # 导入 numpy，但在本文件中用 np 这个简称来指代它
```

- 「这只是让我们能用简写来写模块名，省得一遍遍写 `numpy` 这种长名字。」
- **`import numpy as np` 是全世界的通用写法（common practice）**，网上搜到的 Python 例子几乎都是这么写。用 `np.zeros(...)` 和 `numpy.zeros(...)` 完全等价。

标准写法：**所有 import 都放在程序最开头**。

```python
import numpy as np                  # 数值计算，本周主角
import pandas as pd                 # 数据结构与数据分析（Week 6 起）
import sklearn                      # 机器学习。注意：模块名 sklearn 与官方标题 Scikit-learn 不同，.py 用的是 sklearn
import matplotlib                   # 绘图
import matplotlib.pyplot as plt     # 实际最常用的是 matplotlib 里的 pyplot 子模块，别名 plt
```

### 2.6 `from ... import ...`（只导入一个函数）

有时候不想导入整个模块，只要其中一个函数：

```python
from sklearn.cluster import KMeans   # 只从 sklearn 的 cluster 子模块里取出 KMeans 这一个函数/类
```

Notebook 提问：「这个语法说得通吗？`.` 的用法很重要——它让我访问整个包内部的东西。」
用了 `from ... import KMeans` 之后，直接写 `KMeans(...)` 即可，不用再写 `sklearn.cluster.KMeans(...)`。

**判断怎么写的唯一办法：查官方文档 (documentation)。** 老师强调：「到某个阶段，如果你要导入一个函数，你通常必须去看文档，文档会告诉你能传什么、能拿回什么。这就是为什么文档非常重要，本课用到的所有模块都有非常非常成熟的文档。」

### 2.7 本课要用到的模块生态

| 模块 | 中文/用途 | 何时用 |
|---|---|---|
| `numpy` | Numerical Python，数值数组与数学函数 | **本周起贯穿全课** |
| `matplotlib`（`matplotlib.pyplot as plt`）| 绘图 | 全课；**课程始终直接给你绘图模板，不专门教** |
| `pandas` | 数据结构与数据分析工具（读数据、处理数据）| Week 6 起 |
| `scipy` | 数学/科学/工程的开源生态（内含 numpy）| 偶尔 |
| `scikit-learn` (`sklearn`) | 机器学习 | 最后一个 practical |

老师的补充（Practical 1 的回忆）：第一次实践课里我们用 Anaconda 建了环境 (environment)，环境文件里列出了整门课要用的模块，Anaconda 从外部服务器拉取并安装它们。**「Python 之所以好，就是因为有这样一整个模块与函数的生态系统，真的让我们的生活容易很多。」**

**关于 import 报错**：「如果 import 语句报错，意味着模块不在那里——没装，或者找不到。本课里希望不会发生。真发生了我们可以用 conda 重装，相对容易修。」老师顺带吐槽：在别的语言里包管理是"pain in the ass"——你装一个模块可能弄坏另一个；conda 这类包管理器 (package manager) 会帮你算出会不会冲突。

### 2.8 `.ipynb` vs `.py`（课堂补充的重要区分）

- **文件扩展名 (file extension) 告诉计算机这是什么类型的文件、该期待什么内容。**
- Jupyter Notebook = `.ipynb`；纯 Python 脚本 = `.py`。
- 本课**所有东西都写在一个 notebook 里**，因为"文字 + 代码 + 输出"都能看见，最方便。
- 但真正做常规编程时，你会把代码写成独立的 `.py` 文件，然后用 Python 解释器直接运行它。**这样更快**：notebook 有 **overhead（额外开销）**——它要开一个网页浏览器、非常可视化，因此占用一点资源。
- **只有 `.py` 文件才能作为模块被 `import`**（模块名 = 文件名去掉 `.py`）。

### 2.9 为什么改用 NumPy 数组，而不是 list？

老师的原话逻辑链：

- list 仍然有用，而且**比 tuple 更高效**（tuple 不可变，list 可变；这是上周的内容），但**用 list 做数值计算太"手工"了 (too manual)**。
- **NumPy 更高效 (efficient)**。原因之一：课程开头说过"Python 很宽容 (forgiving)，我们什么都不用事先声明"；**但 NumPy 要求你事先声明**——数组多大、什么数据类型 (dtype)。**正因为要事先定义，它才更高效。**
- **不能在一个 NumPy 数组里混合数据类型**（list 可以混，NumPy 不行）。「对我们这门课没问题，而且这正是 NumPy 高效的原因。」
- **NumPy 数组是 Python 里一切的基石**：「即使我们后面用 pandas 载入数据，只要你把数据从 pandas 框架里取出来，你拿到的就是 numpy arrays。所以它真的支撑着 Python 里的一切。」

### 2.10 创建 NumPy 数组：`np.zeros()`

```python
import numpy as np

# np.zeros((形状), dtype=数据类型)：创建一个全是 0 的数组
Integer_array = np.zeros((15,), dtype=int)     # 15 个元素的一维数组，整数型
Float_array   = np.zeros((15,), dtype=float)   # 15 个元素的一维数组，浮点型
```

```python
print("The integer array looks like > ", Integer_array)
print("The floating point array looks like > ", Float_array)
```

输出：

```
The integer array looks like >  [0 0 0 0 0 0 0 0 0 0 0 0 0 0 0]
The floating point array looks like >  [0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0. 0.]
```

**如何判断结果是否正确**：
- 两行都应该是 **15 个 0**（数一数）。
- **整数数组打印为 `0`，浮点数组打印为 `0.`（带小数点）**——这个小数点就是 dtype 的可视化证据，也是"精度 (precision) 的差别"。
- Notebook 原话：「你应该能看出格式（因此是精度）上的差别。」

**函数签名理解**（Notebook 写法）：

> `numpy.zeros((rows, columns), type of data)`

- 第一个参数是**形状 (shape)**，用一个元组 (tuple) 给出。
- 只想要一维时，**忽略 columns**，写 `(15,)`。**注意那个逗号不能省**——`(15)` 在 Python 里就是整数 15，`(15,)` 才是长度为 1 的元组。（实际上 `np.zeros(15)` 也能工作，但本课坚持写 `(15,)` 的规范形式。）
- 想要 15 行 4 列的二维数组（矩阵 matrix）：`np.zeros((15,4), dtype=int)`。
- `dtype=int` / `dtype=float` 是**函数所期望 (expects) 的语法**，文档里能查到。

老师课上的解释：「我传给 `numpy.zeros` 的就是我想要的数组大小和数字类型。我告诉它我要 15 个格子、给我整数类型。函数传回来的就是一个装满 0 的数组，但它们是整数，没有小数点。」

### 2.11 索引与切片：`:` 运算符

**NumPy 数组的索引方式和 list 完全一样，仍然从 0 开始。** 老师：「把矩阵想成有坐标。第一行第一列是 `0,0`。Python 从 0 开始。第一行第二列是 `0,1`。放值进去、取值出来，用的地址方式和 list 一样——只是引擎盖底下的结构非常不同。」

Notebook 给了 O'Reilly 的经典 2D 索引示意图（`Nump_array_indexing.png`）：横向是 column（axis 1），纵向是 row（axis 0），左上角是 `[0,0]`。

**四种把 3×3 矩阵全部填成 298.15 的方法**（298.15 K = 25 °C = 室温，这是地球科学里最常见的参考温度，Kelvin 温标）：

```python
# 先用 np.zeros 造一个 3 行 3 列的空矩阵（全 0），浮点型
matrix = np.zeros((3,3), dtype=float)

# 方法 1) 一格一格手动写。第 1 行第 1 列、第 1 行第 2 列……（分号 ; 可以把多条语句写在一行）
matrix[0,0] = 298.15; matrix[0,1] = 298.15; matrix[0,2] = 298.15
matrix[1,0] = 298.15; matrix[1,1] = 298.15; matrix[1,2] = 298.15
matrix[2,0] = 298.15; matrix[2,1] = 298.15; matrix[2,2] = 298.15
print(" first entry method result = ", matrix)

# 方法 2) 逐行赋值：用 ':' 一次跨过该行的所有列
matrix = np.zeros((3,3), dtype=float)   # 重新清零，保证每种方法都是从零开始，结果可比较
matrix[0,0:3] = 298.15                  # 第 0 行，第 0~2 列（0:3 不含 3）
matrix[1,0:3] = 298.15
matrix[2,0:3] = 298.15
print(" second entry method result = ", matrix)

# 方法 3) 逐列赋值：用 ':' 一次跨过该列的所有行
matrix = np.zeros((3,3), dtype=float)
matrix[0:3,0] = 298.15                  # 第 0~2 行，第 0 列
matrix[0:3,1] = 298.15
matrix[0:3,2] = 298.15
print(" third entry method result = ", matrix)

# 方法 4) 两个维度都用 ':' —— 最高效、最紧凑
matrix = np.zeros((3,3), dtype=float)
matrix[0:3,0:3] = 298.15                # 所有行 × 所有列，一次搞定
print(" fourth entry method result = ", matrix)
```

输出（四次完全一样）：

```
 first entry method result =  [[298.15 298.15 298.15]
 [298.15 298.15 298.15]
 [298.15 298.15 298.15]]
 second entry method result =  [[298.15 298.15 298.15]
 [298.15 298.15 298.15]
 [298.15 298.15 298.15]]
 third entry method result =  [[298.15 298.15 298.15]
 [298.15 298.15 298.15]
 [298.15 298.15 298.15]]
 fourth entry method result =  [[298.15 298.15 298.15]
 [298.15 298.15 298.15]
 [298.15 298.15 298.15]]
```

**结果判读**：四段输出必须**一模一样**——这就是"四种方式做同一件事"的验证方式。打印的二维数组用**嵌套方括号**表示：外层 `[]` 是整个矩阵，内层每个 `[...]` 是一行；这里有 3 个内层括号 = 3 行，每行 3 个数 = 3 列。

老师的总结：「第一种非常手工、非常低效。最后一种最高效……这些做的是同一件事，但比第一种快得多。你不会真的感觉到快，因为这还是个很小的操作。但它让我们能写出更紧凑的代码，也就更好读。」

**`[:, :]` 的等价写法**（Part 4 用的）：省略起止就表示"全部"。

```python
A[:,:] = 2.4      # 等价于 A[0:3, 0:3] = 2.4（对 3x3 而言），且不依赖数组大小，更通用
```

### 2.12 逐元素运算 (element-wise operations)：不用 for 循环

**一维：**

```python
import numpy as np

array1 = np.array([10,20,30,40,50], dtype=int)   # np.array() 把一个 list 转成 numpy 数组
array2 = np.array([0,1,2,3,4],  dtype=int)
array3 = array1 + array2                          # 对应位置逐个相加，不需要任何循环

print("array3 = ", array3)
```

输出：

```
array3 =  [10 21 32 43 54]
```

**判读**：10+0=10、20+1=21、30+2=32、40+3=43、50+4=54。**位置一一对应**，这就是 element-wise（逐元素）的含义。因为两个输入都是 `int`，输出也是 `int`（打印时没有小数点）。

老师的解释：「`np.array` 是一个函数，它让我指定一个 list，然后把它变成一个 numpy 数组。我有两个数组，各 5 个元素，都是整数。`array1 + array2` 这个操作会把每个元素相加，给我一个新数组。**所以我们不需要 for 循环了。**」

**二维（矩阵）：**

```python
# 初始化两个空矩阵 A 和 B
A = np.zeros((3,3), dtype=float)
B = np.zeros((3,3), dtype=float)

# 把 A 的所有格子设为 2.4，B 的所有格子设为 1.6
A[:,:] = 2.4
B[:,:] = 1.6

print(A+B)
```

输出：

```
[[4. 4. 4.]
 [4. 4. 4.]
 [4. 4. 4.]]
```

**判读**：2.4 + 1.6 = 4.0，每一格都是。打印成 `4.` 是因为 dtype 是 float。

```python
print(A*B)
```

输出：

```
[[3.84 3.84 3.84]
 [3.84 3.84 3.84]
 [3.84 3.84 3.84]]
```

**判读**：2.4 × 1.6 = 3.84。**注意这不是矩阵乘法！** 如果是真正的矩阵乘法，3×3 全 2.4 乘 3×3 全 1.6，结果每格会是 3 × 2.4 × 1.6 = 11.52。得到 3.84 说明是**逐元素相乘**。

**更清楚的验证例子：**

```python
# 手写两个 numpy 数组（嵌套 list → 2D 数组）
C = np.array([[3,2],[0,1]])     # [[3,2],
                                #  [0,1]]
D = np.array([[3,1],[2,1]])     # [[3,1],
                                #  [2,1]]
print(C*D)                      # 你能确认每一格是独立相乘的吗？
```

输出：

```
[[9 2]
 [0 1]]
```

**判读**：3×3=9、2×1=2、0×2=0、1×1=1。**逐格独立相乘**，完全确认。
（对照：真正的矩阵乘法 `C @ D` 会给 `[[13,5],[2,1]]`——第一行第一列 = 3×3+2×2 = 13。**讲义里专门有一页写着：Elementwise multiplication is not the same as matrix multiplication。**）

老师还提到 numpy 另有 `np.multiply(array1, array2)` 函数，效果与 `array1*array2` **完全相同**：「如果我们真想的话，还有个 numpy 函数叫 multiply，我们可以调用它，但它做的是一模一样的事。你们上周有些人发现了，编程时切同一块蛋糕有多种方法。这里没有哪个更好，通常归结为哪个更快、哪个更整洁。但这个例子里真的无所谓。」

**为什么这很重要**：老师说「我们从函数出发去掉了 for 循环，能把数组加起来、乘起来。之前那个例子里，for 循环要看每个数组的每一个地址，从 X 和 Y 里取值再填进 Z。用 numpy 数组，你不用循环就能加。所以我们的代码又被压缩了。」

「你可能还是需要 for 循环——如果你需要一个条件语句去检查什么时候某件事为真。但我们用 pandas 载数据时会看到，pandas 里也能显式地写'告诉我哪里为真'。」

---

## 三、语法速查与函数表

### 3.1 本周新语法 / 新函数

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `def` | 定义函数的关键字 | `def test():` | 行尾**必须**有冒号 `:`；下一行必须缩进 4 空格 |
| `return` | 结束函数并（可选地）返回值 | `return z` / `return` / `return a, b` | 只写 `return` 返回 `None`；忘记 `return` 时函数也会返回 `None`（不报错，但你拿不到结果） |
| 函数调用 | 执行函数体 | `test()` | **括号不能省**。写 `test` 只是引用函数对象，不会执行 |
| `import` | 导入模块 | `import numpy` | 模块名 = `.py` 文件名（去掉后缀）；解释器必须能找到它 |
| `import ... as ...` | 导入并起别名 | `import numpy as np` | `np` 是全球约定俗成的别名；`plt` 之于 `matplotlib.pyplot` 同理 |
| `from ... import ...` | 只导入模块中的某一部分 | `from sklearn.cluster import KMeans` | 导入后直接用 `KMeans`，不再写前缀 |
| `.`（点运算符）| 访问模块内的函数/变量 | `np.zeros(...)`、`numpy.max(...)` | 也用于访问包里的子模块：`matplotlib.pyplot` |
| `np.zeros(shape, dtype)` | 创建全 0 数组 | `np.zeros((3,3), dtype=float)` | shape 是**元组**；一维要写 `(15,)`（逗号别丢）；`dtype` 只能是**一种**类型 |
| `np.array(list, dtype)` | 把 list（或嵌套 list）转成 numpy 数组 | `np.array([10,20,30], dtype=int)` | 嵌套 list `[[3,2],[0,1]]` → 2D 数组；不能混类型 |
| 索引 `a[i]` / `a[r,c]` | 取/存单个元素 | `x[97]`、`z[row,column]` | **从 0 开始**；二维用**逗号**分隔行列，不要写 `z[row][column]`（虽然也能跑，但慢且不规范） |
| 切片 `a[start:end]` | 取/存一段 | `matrix[0,0:3] = 298.15` | **左闭右开**：`0:3` 是 0,1,2，**不含 3** |
| 切片 `a[:]` / `a[:,:]` | 全部元素 | `A[:,:] = 2.4` | 省略起止 = 从头到尾；比写死数字更安全 |
| `+ - * / **` | 逐元素算术运算 | `array1+array2`、`A*B`、`x**2.0` | 对整个数组生效；`*` **不是**矩阵乘法 |
| `np.multiply(a,b)` | 逐元素相乘（函数形式）| `np.multiply(A,B)` | 与 `A*B` 完全等价 |
| `np.max` / `np.min` | 数组最大/最小值 | `np.max(z)` | 老师课上举例提到，用来快速检查数组范围 |
| `range(n)` | 产生 0..n-1 的整数序列 | `for step in range(30):` | 上周内容，本周用来重复调用函数 |
| `plt.contourf(x,y,z,20,cmap='RdGy')` | 画填充等值线图（2D 面）| 见下 | `20` = 等值线层数；`cmap` = 配色 |
| `plt.colorbar()` | 加色标 | `plt.colorbar();` | 分号只是抑制 notebook 的回显输出 |
| `plt.xlabel/ylabel` | 坐标轴标签 | `plt.xlabel('x')` | 科学作图必须有 |
| `plt.show()` | 显示图 | `plt.show()` | 放最后 |

### 3.2 绘图模板（本课固定给出，不要求自己写）

```python
plt.contourf(x, y, z, 20, cmap='RdGy')   # 填充等值线图：x 为横轴坐标，y 为纵轴坐标，z 为 2D 数值面
plt.colorbar();                          # 画一个颜色条，告诉读者颜色对应什么数值
plt.xlabel('x')                          # 横轴标签
plt.ylabel('y')                          # 纵轴标签
plt.show()                               # 渲染并显示
```

老师明确说：「关于绘图模块，我们不提供专门训练，但会给你们涵盖从折线、散点到 3D 图的模板。你可以拿去改。」「matplotlib 可以讲很多节课，但我们就当默认，绘图代码这门课始终给你。」

### 3.3 两张关键概念图（讲义/Notebook 中的示意图）

| 图 | 内容 | 判读要点 |
|---|---|---|
| `Nump_array_indexing.png`（O'Reilly）| 2D numpy 数组的索引示意 | 左上角 `[0,0]`；第一个索引是**行 (row)**，第二个是**列 (column)**；都从 0 开始 |
| `adding_arrays.png`（Pluralsight）| 两个 1D 数组相加的示意 | 竖直对齐的两个元素相加得到结果的同一位置——直观展示 element-wise |
| `Practical3_example.png` | Exercise 2 应得到的等值线图 | 用来对照你自己的输出，判断代码是否正确 |

**等值线图的判读要点**（对 `z = x + y*x`）：
- `z = x(1+y)`，所以 z 随 x、y 都单调增，且**乘积项主导**——图上一个角（x、y 都大）会是极值，量级达到 100×101 ≈ 10^4（100×100 时）或 300×301 ≈ 9×10^4（300×300 时）。
- 等值线是**双曲线状**（因为是乘积关系），**不是**直线。
- 对照：`z = x + y` 是纯加法，等值线是 45° 直线，图形关于对角线对称。**这是快速判断你是否写对了公式的最好办法**——看图形是"直线条纹"还是"双曲弯曲"。

---

## 四、课堂补充

（以下内容只在 transcript 里出现，讲义 PDF 上没有或没展开）

### 4.1 老师对"能跑 ≠ 正确"的再次强调（承接 Week 2）

老师花了不少时间复习上周的关键教训：

> **"Just because it works does not make it correct."**（讲义 recap 页原句）

上周的例子：有两个都能跑的版本，但**第一个版本永远出不了第二个 `elif` 语句**，因为那个 `elif` 写的是 `x[step] >= 20`——不管 x 多大**永远为真**；而我们真正想要的是在 `x >= 60` 时停下来。

老师给出的**工程三步法**（重要，反复出现）：

1. **先让它能跑 (make it work)**
2. **再让它正确 (make it right)**
3. **有时间/有需要时再让它更快 (make it quicker)**

「这是个好的第一步：先有能跑的代码，然后让它对。……重要的是检查它到底在做什么。它给出你期望的答案了吗？」

### 4.2 Python 解释器 (interpreter) 是什么

「Python 解释器基本上就是把我们写的代码变成计算机能懂的东西的那个东西。如果它看不懂，就会给我们一个报错。你会在 Jupyter Notebook 里看到——它会标出错误，而且是相当清楚的错误。」

**这句话的实用含义**：不要害怕红色报错框，**Python 的报错通常直接告诉你哪一行、什么问题**。

### 4.3 关于越界 (out of bounds)

老师明确提醒：

> 「如果你建了一个 5×5 的数组矩阵，然后你说'把东西放进第一行第七列'，它会说我做不到。所以你会看到我们仍然必须遵守我们告诉 Python 的数组大小。」

**注意这里有个非常重要的细节（老师没细分，但 Practical 的解答里恰好碰到了）：**
- **整数索引越界会报 `IndexError`**：`matrix[0,6] = 1`（矩阵只有 6 列，索引 0–5）→ 报错。
- **切片越界不会报错，会被静默裁剪 (silently clipped)**：`matrix[0:2, 0:7] = 2.5` 在只有 6 列时**不会报错**，只是把 0:6 全填了。这就是 Exercise 1 的官方解答能跑通的原因。**这是 NumPy/Python 切片的一个"陷阱"级特性——它不会提醒你写错了尺寸。**

### 4.4 老师的电影梗（考试不考但有助记忆）

`"All work and no play makes Jack a dull boy"` 出自 Stanley Kubrick 的电影 **《闪灵》(The Shining, 1980)** ——男主角 Jack 在打字机上反复打这一句。老师说：「我猜大家都熟悉这部电影吧？我这些天从来不确定。这是我最喜欢的电影之一。」Exercise 3 就是让你**用 for 循环复现那台打字机**。

### 4.5 下周预告（Week 4：Conway's Game of Life）

「下周我们会把这一切合在一起，用 numpy 数组、一些 for 循环和逻辑，解四条简单的规则，做出所谓的 Conway's Game of Life（康威生命游戏），而且你们会在屏幕上看到动画。」

这解释了**为什么本周必须掌握 numpy 二维数组的索引与切片**——生命游戏的整个棋盘就是一个 2D numpy 数组。

### 4.6 老师关于"抽象"的坦白

「就像我说过几次的，下周我们真的会变得不那么抽象，至少你能看到你在造什么。」「今天的函数或多或少都是围绕二维曲面来的，所以还是抽象的。」

### 4.7 关于 transcript 的自动转写错误（读原文时要注意）

自动语音转写有几处明显笔误，读原文时要在脑子里改回来：

| transcript 里写的 | 实际是 |
|---|---|
| "an ump module" / "numpy as MP" | `numpy` / `np` |
| "LF statement" | `elif` statement |
| "curly brackets"（在讲函数括号时）| 实际指 parentheses `()`，老师口误/转写误 |
| "NumPy.zeros 我传它 15 cells" | `np.zeros((15,), dtype=int)` |

### 4.8 课堂中提到的、但本课不深入的东西

- **版本控制 / GitHub**：不教，但属于软件工程最佳实践。课程材料本身就托管在老师的 GitHub 上（`loftytopping/DEES_programming_course`）。
- **性能优化 (optimisation)**：不教，但要开始有意识——「在很多研究领域，计算时间是提高复杂度的根本障碍。」
- **修改 `PYTHONPATH`**：Notebook 提到"我们这里不讲，但你也可以通过改 Python path 或导入另一个模块来指定你自己写的模块的位置"。

---

## 五、Practical 要点

Practical 3 分 4 个部分、5 个练习。**Notebook 里的解答就是老师给的参考答案**，下面逐个梳理。

### Part 0：Google Colab 检测代码块

```python
if 'google.colab' in str(get_ipython()):        # get_ipython() 返回当前 IPython 环境对象；转成字符串后看里面有没有 'google.colab'
    from google.colab import drive              # 若在 Colab，导入 Google Drive 挂载工具
    mount='/content/gdrive'                     # 挂载点路径
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)                          # 执行挂载（会弹出授权）
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root                             # % 开头是 Jupyter 的 magic command：切换工作目录
else:
    print('Not running on CoLab')               # 本地运行（Anaconda）走这一支
```

输出（本地）：

```
Not running on CoLab
```

**判读**：看到这句就说明你在本地 Anaconda 环境里，一切正常，往下走即可。这段代码本身与本周知识点无关，是为了让在 Colab 上跑的同学能读到数据文件。
（顺带认识：`\n` 是换行符；`%cd` 是 notebook 专有的 magic command，不是普通 Python。）

---

### Part 1：学会用 NumPy 模块

#### 1.1 创建一维数组（示例，非练习）

见 §2.10。要点：`np.zeros((15,), dtype=int)` vs `dtype=float`，输出的 `0` vs `0.`。

#### 1.2 创建二维数组、访问与修改（示例，非练习）

见 §2.11。四种填充方法，输出四次相同。

#### **Exercise 1：创建 2D 数组并填入指定值**

**题目要求**：
- 创建一个空的 2D 数组，**5 行 6 列**，浮点型。
- **前两行**填 `2.5`。
- **其余各行**填 `5.5`。
- 打印到屏幕核对。

期望结果：

```
matrix result =  [[2.5 2.5 2.5 2.5 2.5 2.5]
 [2.5 2.5 2.5 2.5 2.5 2.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]]
```

**HINT（Notebook 给的提示）**：与其一格一格写，不如用上面例 2、例 3 演示的技巧（即 `:` 切片）。

**解题思路**：
1. 用 `np.zeros((5,6), dtype=float)` 建骨架——**先把形状和类型定死**，这是 NumPy 的思维方式。
2. 前两行 = 行索引 `0` 和 `1` = 切片 `0:2`（左闭右开，不含 2）。
3. 其余行 = 行索引 `2,3,4` = 切片 `2:5`。
4. 列全部 = `:` 或 `0:6`。

**代码（Notebook 官方解答）**：

```python
#------'INSERT CODE HERE'------

# 用 np.zeros 初始化一个空的 5 行 6 列浮点二维数组
practice_matrix = np.zeros((5,6), dtype=float)

# 用切片填值
practice_matrix[0:2,0:7]=2.5     # 第 0、1 行（前两行），所有列 → 2.5
practice_matrix[2:6,0:7]=5.5     # 第 2、3、4 行（其余行），所有列 → 5.5

#------------------------------

# 打印矩阵检查
print(" matrix result = ", practice_matrix)
```

**输出**：

```
 matrix result =  [[2.5 2.5 2.5 2.5 2.5 2.5]
 [2.5 2.5 2.5 2.5 2.5 2.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]
 [5.5 5.5 5.5 5.5 5.5 5.5]]
```

**输出解读与正确性判断**：
- 外层括号里有 **5 个内层 `[...]`** → 5 行 ✓
- 每个内层有 **6 个数** → 6 列 ✓
- 前两行全 `2.5`、后三行全 `5.5` ✓
- 全部带小数点 → dtype 是 float ✓

**⚠️ 这份官方解答里的两个"能跑但不严谨"之处（重要考点）**：

1. `0:7` —— 矩阵只有 6 列（索引 0–5），写 `0:7` **超出边界**。**但切片越界不会报错**，NumPy 会自动裁剪到 `0:6`。更干净的写法是 `[0:2, :]`。**若换成整数索引 `practice_matrix[0,6]=2.5` 就会直接 `IndexError`。**
2. `2:6` —— 矩阵只有 5 行（索引 0–4），同理被裁剪成 `2:5`。

**推荐的规范写法**：

```python
practice_matrix = np.zeros((5,6), dtype=float)
practice_matrix[0:2, :] = 2.5     # 前两行，全部列
practice_matrix[2:,  :] = 5.5     # 从第 2 行到末尾，全部列（省略 end 表示"到底"）
```

这样即使以后改了数组尺寸，代码也不会错——**这就是"make it right"的含义**。

---

### Part 2：用条件语句 + 循环修改 NumPy 数组中的值

#### 示例 A：一维循环填值 `y = x^2`

```python
# 先给 x 和 y 各建一个空数组（100 个元素，浮点）
x = np.zeros((100,), dtype=float)
y = np.zeros((100,), dtype=float)

# 用 for 循环走 100 次，生成 X 值和对应的 Y 值
for step in range(100):      # step 依次取 0,1,2,...,99
    x[step] = step+1         # 我们要 x 从 1 开始，而 step 从 0 开始，所以 +1
    y[step] = x[step]**2.0   # ** 是幂运算；y = x 的 2.0 次方

# 打印最后 3 个值。注意：第 98 个元素的索引是 97（从 0 开始）
print("the value of the 98th component of x is ", x[97])
print("the value of the 98th component of y is ", y[97])

print("the value of the 99th component of x is ", x[98])
print("the value of the 99th component of y is ", y[98])

print("the value of the 100th component of x is ", x[99])
print("the value of the 100th component of y is ", y[99])
```

**输出**：

```
the value of the 98th component of x is  98.0
the value of the 98th component of y is  9604.0
the value of the 99th component of x is  99.0
the value of the 99th component of y is  9801.0
the value of the 100th component of x is  100.0
the value of the 100th component of y is  10000.0
```

**输出解读 / 正确性检查**：
- 98² = 9604 ✓、99² = 9801 ✓、100² = 10000 ✓ —— **心算能验的边界值就是最好的测试**。
- 所有数都带 `.0`，说明 dtype=float 生效了 ✓
- **"第 98 个元素"用索引 97** —— 这是理解 0-based indexing 的关键练习。如果你打印 `x[98]` 却期望 98，就会看到 99，说明你差了 1（off-by-one error）。

Notebook 列出这个例子综合了哪些技能：初始化特定大小的 1D 浮点数组、写 `for` 循环遍历整数、通过索引访问 1D 数组中的特定元素（记住 Python 索引从 0 开始）、幂运算、打印到屏幕。

#### 示例 B：嵌套循环填 2D 数组 `z = x + y`

```python
# 导入本次要用的模块
import numpy as np
import matplotlib.pyplot as plt

# 初始化 numpy 数组
x = np.zeros((100,), dtype=float)      # 1D，100 个（代表行坐标）
y = np.zeros((100,), dtype=float)      # 1D，100 个（代表列坐标）
z = np.zeros((100,100), dtype=float)   # 2D，100x100（结果面）

# 把 x、y 填成 1 到 100
for step in range(100):
    x[step]=step+1 # why do we add 1?   （因为 step 从 0 开始，而我们要 1..100）
    y[step]=step+1 # why do we add 1?

# 嵌套循环 (nested loop)：逐维度遍历生成 z
for row in range(100):            # 外层循环：走每一行
    for column in range(100):     # 内层循环：对每一行，横扫每一列
        z[row,column]=x[row]+y[column]   # 用行/列索引取值，填进 z

# 绘图（模板，暂不用管细节）
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

**输出**：一张 `RdGy`（红-灰）配色的填充等值线图，`z` 从左下角的 2 增到右上角的 200，**等值线是一族 45° 斜直线**（因为 z = x+y 在 x-y 平面上是平面）。图形关于对角线**对称**。

**Notebook 用英文把嵌套循环拆解成 4 步（务必背下这个思维模型）**：

1. 为**行索引**写一个 for 循环，变量叫 `row`，从 1 循环到 100，这个索引就是行号。
2. 对**每一个行号**，再循环每一个**列索引**，变量叫 `col`。这相当于**从左到右扫描矩阵**。
3. 现在我们同时有了行号和列号。用这两个索引从 X、Y 数组里取值：`X[row]` 和 `Y[col]`。
4. 用这两个值给 2D 数组 Z 赋值：`Z[row,col] = X[row]+Y[col]`。

> **嵌套循环的执行次数**：外层 100 次 × 内层 100 次 = **10 000 次**赋值。这就是为什么后面 Part 4 的向量化写法值得学——同样的事，一行搞定，而且更快。

#### **Exercise 2：用循环按公式填 2D 数组**

**题目要求**：用 `for` 循环填一个 2D NumPy 数组，按公式

$$z = x + y \cdot x$$

其中 `X` 数组存**行索引**、`Y` 数组存**列索引**，`Z` 是 2D 数组，然后用 matplotlib 画出来，图应与给出的参考图 (`Practical3_example.png`) 一致。

> **⚠️ 题面 vs 解答的尺寸不一致**：题目文字写的是「**200 rows and 300 columns**」，但 Notebook 给出的解答用的是 **100×100**。这是原始材料的疏漏。**理解重点在方法，不在具体数字**；真要严格按题面做，就把 `np.zeros((100,), ...)` 改成 `np.zeros((200,), ...)` / `np.zeros((300,), ...)`、`z = np.zeros((200,300), ...)`，并把两个 `range` 改成 `range(200)` 和 `range(300)`。

**HINT**：需要用嵌套 for 循环遍历行和列，参考上面的例子。**记住 Python 在 `:` 之后要求缩进。**

**解题思路**：整段代码和示例 B **一模一样**，唯一要改的是最内层那一行公式：把 `x[row]+y[column]` 改成 `x[row]+y[column]*x[row]`。

**代码（官方解答）**：

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# Initialise the arrays
x = np.zeros((100,), dtype=float)      # 行坐标数组
y = np.zeros((100,), dtype=float)      # 列坐标数组
z = np.zeros((100,100), dtype=float)   # 结果面

#  ------- 'INSERT CODE HERE' ---------
# 把 x、y 填成 1..100
for step in range(100):
    x[step]=step+1 # why do we add 1?
    y[step]=step+1 # why do we add 1?

#  ------- 'INSERT CODE HERE' ---------
# 嵌套循环生成 z
for row in range(100):
    for column in range(100):
        z[row,column]=x[row]+y[column]*x[row]   # 唯一的改动：加上 *x[row]

# 绘图模板
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

**输出解读**：
- `z = x + y·x = x(1+y)`。当 x=1,y=1 时 z=2；当 x=100,y=100 时 z = 100×101 = **10100**。
- 色标 (colorbar) 的上限应该在 **10^4 量级**——如果你的色标只到 200，说明你把 `*x[row]` 写漏了（那就还是 `z=x+y`）。**这是最快的自查方式。**
- 图形**不再关于对角线对称**：`x` 出现了两次（一次线性、一次乘积），而 `y` 只出现一次，所以 z 对 x 的敏感度远高于对 y。等值线呈**双曲线弯曲**。

---

### Part 3：写你自己的函数

#### 示例 C：`test()` 函数

见 §2.2。

Notebook 复述的五条要点（与讲义 syntax check 完全一致）：
- `def` 关键字通过名字定义函数
- 圆括号 `()` 可以放函数需要的输入列表
- 函数名和输入列表以冒号 `:` 结尾
- 下一行（函数的内部工作）**缩进 4 个空格**
- `return` 语句关闭函数定义

#### **Exercise 3：复刻《闪灵》里的打字机**

**题目要求**：用上面的示例函数，配合 `FOR` 循环，把那句话打印 **30 次** 到屏幕上。

**HINT**：记住 `FOR` 循环的格式是 `for "variable" in range(number):`

**解题思路**：函数定义只写一次（不要在循环里重复 `def`），循环体里调用 30 次。

**代码（官方解答）**：

```python
# 定义函数 test，作用是向屏幕写一条消息
def test():
    print("All work and no play makes Jack a dull boy")
    return

# 在 for 循环里调用这个函数 30 次
for step in range(30):    # range(30) → 0..29，共 30 轮
    test()                # 循环体缩进 4 空格；每轮调用一次函数
```

**输出**（30 行完全相同）：

```
All work and no play makes Jack a dull boy
All work and no play makes Jack a dull boy
... （共 30 行）
All work and no play makes Jack a dull boy
```

**输出解读 / 正确性判断**：
- **数行数**：必须正好 30 行。若是 31 行，多半是 `range(31)` 或在循环外多调了一次；若是 29 行，可能写成了 `range(1,30)`。
- 循环变量 `step` 在函数体内**根本没用到**——这完全正常。当你只需要"重复 N 次"而不关心第几次时，`step`（或惯用的 `_`）只是个计数占位符。

**常见错误**：
- 忘记函数调用的括号：写 `test` 而不是 `test()` → 不打印任何东西，也不报错（在 notebook 里如果是 cell 最后一行，会显示 `<function test at 0x...>`）。
- 把 `def` 放进循环里 → 每轮都重新定义一次函数，虽然结果一样但完全没有意义，违背了"只写一次"的初衷。

#### 示例 D：把嵌套循环**包进函数**里（关键示例！）

这是本周"函数思维"的核心演示——**同样的 `z = x + y`，但整个填值过程被封装了**。

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# 初始化数组（注意：这次没有在外面建 z）
x = np.zeros((100,), dtype=float)
y = np.zeros((100,), dtype=float)

# 把 x、y 填成 1..100
for step in range(100):
    x[step]=step+1 # why do we add 1?
    y[step]=step+1 # why do we add 1?

# 把方程 z=x+y 实现为一个函数
def create_z_array(x,y):                       # 函数名 create_z_array，接收两个输入 x 和 y
    # 在函数内部初始化 z 数组
    z = np.zeros((100,100), dtype=float)       # z 是函数的局部变量 (local variable)
    # 嵌套循环，逐维度生成 z
    for row in range(100):                     # 外层：行
        for column in range(100):              # 内层：列
            z[row,column]=x[row]+y[column]     # 填值

    # 把 z 数组返回给调用者
    return z                                   # ★ 有 return z，外面才拿得到结果

# 调用函数，得到 z 数组
z=create_z_array(x,y)                          # 把返回值赋给外部的变量 z

# 绘图模板
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

**输出**：与示例 B **完全相同**的图。这正是要点——**封装成函数不改变结果，只改变代码组织方式**。

**Notebook 的提问**：「读一遍下面的代码，说得通吗？你能看出我们现在把嵌套循环放进了一个新函数里吗？」

**逐点讲解**：
- `def create_z_array(x,y):` —— 括号里的 `x, y` 是**形参 (parameters)**；调用时 `create_z_array(x,y)` 里的 `x, y` 是**实参 (arguments)**。名字碰巧一样，但概念不同。
- **`z` 在函数内部创建**（`np.zeros` 写在函数体里）—— 这是好设计：函数**自给自足**，调用者不需要事先准备 z。
- **`return z` 是必须的**。如果漏掉，函数返回 `None`，外面的 `z=create_z_array(x,y)` 会让 `z` 变成 `None`，接着 `plt.contourf` 会报 `TypeError`。
- **调用一次 = 干完 10 000 次赋值**。老师的话："如果我想在左边做 10 次，我真的不想写 10 遍。你可以复制粘贴 10 遍，那也行，但你的代码会变得很乱、很长。所以你可以把它包进一个函数，然后在代码里任何想要的地方调用这个函数。……我还可以把这个函数丢进一个 Python 文件叫它模块，然后分享给别人。"

#### **Exercise 4：把 `z = x + y·x` 写成函数**

**题目要求**：插入除绘图外的全部代码，把 Exercise 2 的公式

$$z = x + y \cdot x$$

（X 代表行号、Y 代表列号）实现成一个**函数**。题面说是 200 行 200 列。

**HINT**：大部分代码前面已经写过了，你只需要把它**重新组织成函数形式**。另外注意行列数变了。

> **⚠️ 题面 vs 解答再次不一致**：题面说 200×200，解答用的是 **300×300**。同样，重点是方法。

**解题思路**：
1. 保留外部的 x、y 填值循环（1..300）。
2. 把嵌套循环搬进 `def create_z(x,y,z):` 里。
3. 注意这个版本**把 z 也作为参数传进去**（和示例 D 不同，示例 D 在函数内部造 z）。
4. `return z` 后在外面接收。

**代码（官方解答）**：

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# 初始化数组：这次是 300
x = np.zeros((300,), dtype=float)      # 1D，300 个
y = np.zeros((300,), dtype=float)      # 1D，300 个
z = np.zeros((300,300), dtype=float)   # 2D，300x300 —— 注意：z 在函数外部就建好了

#  ------- 'INSERT CODE HERE' ---------
# 把 x、y 填成 1..300
for step in range(300):
    x[step]=step+1 # why do we add 1?
    y[step]=step+1 # why do we add 1?

#  ------- 'INSERT CODE HERE' ---------
# 把嵌套循环包成函数。注意这次的参数列表是 (x, y, z) —— z 也被传进来
def create_z(x,y,z):
    for row in range(300):                          # 外层：300 行
        for column in range(300):                   # 内层：300 列
            z[row,column]=x[row]+y[column]*x[row]   # 逐格赋值（共 90 000 次）

    return z                                        # 返回填好的 z

z=create_z(x,y,z)      # 调用：把 x、y、z 传进去，把返回的数组再赋回 z

# 绘图模板
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

**输出解读**：
- 与 Exercise 2 同形状的双曲弯曲等值线图，但**分辨率更高、量级更大**：最大值 = 300 + 300×300 = **90300**，色标上限应在 9×10^4 附近。
- **运行时间明显变长**：90 000 次 Python 层面的循环赋值。你会真切感受到"逐格循环慢"——这正好为 Part 4 的向量化做铺垫。

**这里有一个值得注意的编程细节（重点）**：
- `z` 是**通过参数传进函数的**。NumPy 数组是**可变对象 (mutable)**，函数里 `z[row,column]=...` 是**原地修改 (in-place modification)**，会**直接改到外面那个 z**。所以即使不写 `return z`、也不写 `z=create_z(...)`，外面的 z 照样会被改掉。
- **这是一个副作用 (side effect)**。示例 D 的写法（在函数内部 `np.zeros` 造 z 再 return）更"干净"，因为函数不会偷偷改调用者的数据。
- 但对比 Exercise 5 你会发现：一旦函数体里写的是 `z = x + y*x`（**整体重新赋值**而不是逐格赋值），就**不再是原地修改**了，外面的 z 完全不受影响——这时 `return z` 就**必须有**。**同一个参数名，行为却因写法而异，这是初学者最容易踩的坑之一。**

---

### Part 4：对整个数组做 NumPy 运算

Notebook 的引入：「一旦我们开始写*大型*模块，就要开始考虑我们的流程有多高效。在很多研究领域里，**计算时间是提高复杂度的根本障碍**。本课不讲优化，但开始思考哪里可以用更高效的选项是有用的。标准 NumPy 库给了我们多种选择，这也有助于**减少代码体积**，并且**可能让代码更可读**！」

#### 4.1 一维数组运算

见 §2.12 的 `array1 + array2` 例子。输出 `[10 21 32 43 54]`。

#### 4.2 二维数组运算

见 §2.12 的 `A+B`、`A*B`、`C*D` 三个例子。

#### **Exercise 5：用整数组运算重写 Exercise 4 的函数**

**题目要求**：插入除绘图外的全部代码，复现 Exercise 4 的

$$z = x + y \cdot x$$

**关键差异**：Notebook 说「为了帮你起步，我已经把 `X` 和 `Y` 都初始化成了 **2D 数组**」。

**解题思路（这是本周最重要的思维跃迁）**：
- 之前 x、y 是 1D 的"坐标轴"，要靠 `x[row]`、`y[column]` 分别取值，所以必须嵌套循环。
- 现在把 x、y 都做成**和 z 同样形状的 2D 数组**：
  - `x[step,:] = step+1` → **第 step 行整行**都等于 `step+1`。所以 x 的值只随**行**变化 → x 就是"行号面"。
  - `y[:,step] = step+1` → **第 step 列整列**都等于 `step+1`。所以 y 的值只随**列**变化 → y 就是"列号面"。
- 这两个 2D 数组叫做**坐标网格 (coordinate grid / meshgrid)**。
- 一旦形状对齐，公式就可以**一行写完**：`z = x + y*x`，NumPy 自动逐元素计算 90 000 个值。**完全不需要嵌套循环。**

**代码（官方解答）**：

```python
# Import the modules we will be using
import numpy as np
import matplotlib.pyplot as plt

# 初始化数组 —— 注意 x 和 y 现在都是 2D 的！
x = np.zeros((300,300), dtype=float)
y = np.zeros((300,300), dtype=float)
z = np.zeros((300,300), dtype=float)

# 用一个（只有一层的）循环把 x 填成"行号面"，把 y 填成"列号面"
for step in range(300):
    x[step,:]=step+1 # why do we add 1?    第 step 行的所有列 = step+1
    y[:,step]=step+1 # why do we add 1?    所有行的第 step 列 = step+1

#  ------- 'INSERT CODE HERE' ---------
# 把方程写成函数 —— 函数体只有一行！
def create_z(x,y,z):
    z=x+y*x        # 整数组逐元素运算，一次算完 300x300 = 90000 个值
    return z       # ★ 这里的 return 是必须的（见下方解释）
#  ------------------------------------

z=create_z(x,y,z)  # 调用函数，接收返回的新数组

# 绘图模板
plt.contourf(x, y, z, 20, cmap='RdGy')
plt.colorbar();
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

**输出解读**：
- **图形与 Exercise 4 完全一致**——这就是验证向量化写对了的标准：**换了写法，结果不能变**。
- **速度差别巨大**：Exercise 4 是 90 000 次 Python 循环（解释器逐次执行）；Exercise 5 是一次 NumPy 底层 C 循环。后者通常快几十到上百倍。
- 这次 `plt.contourf(x, y, z, ...)` 接收的是**三个 2D 数组**——matplotlib 支持这种"网格形式"的输入，且比 1D 形式更明确。

**⚠️ `return` 在这里为什么是必须的（对比 Exercise 4）**：
- 函数里写 `z = x + y*x` 是**重新绑定局部变量 z**——它在函数内部造了一个全新的数组，然后让局部名字 `z` 指向它。**外部那个 z 一点没变。**
- 所以若删掉 `return z`，函数返回 `None`，`z = create_z(x,y,z)` 让 z 变成 `None`，`plt.contourf` 立刻报错。
- 反观 Exercise 4 的 `z[row,column]=...` 是**原地写入**，会改到外部数组。
- **口诀：`z[...] = ...` 改的是数组内容（外部可见）；`z = ...` 改的是名字的指向（外部不可见）。**

**顺带说明**：这个版本里 `z` 作为参数其实是**多余的**（函数第一行就把它覆盖了）。更干净的写法：

```python
def create_z(x, y):
    return x + y*x       # 直接返回计算结果，不需要预先分配 z

z = create_z(x, y)
```

---

### Practical 总结（Notebook 的 "⚙️ What We Did"）

> 🟦 **在本次实践课中，我们：**
> - 引入了**模块 (modules)** 的概念，以及我们为什么用它们来扩展 Python 的能力
> - 学会了**导入模块 (import modules)**，重点是 `numpy` 模块
> - 创建并使用了 **NumPy 数组**，包括：一维与二维数组、用特定值填充数组
> - 用**条件语句**修改 NumPy 数组内部的值
> - 把方程应用到数组上以自动生成值
> - 编写了我们自己的**函数**：把代码打包成可复用的块、接收输入并返回输出
> - 练习构建能够：操作数组、产生二维曲面图等可视化输出 的函数
> - 学会了 NumPy 如何**一次性对整个数组做运算**，而不需要显式循环
>
> 🧠 *重点是通过使用模块、函数以及 NumPy 高效处理整个数据集的能力，写出更干净、更强大的代码。*

---

## 六、易错点 / 重点难点

### 6.1 语法陷阱

| 陷阱 | 错误示例 | 后果 | 正确写法 |
|---|---|---|---|
| 函数定义忘冒号 | `def test()` | `SyntaxError: expected ':'` | `def test():` |
| 函数体没缩进 | `def test():`<br>`print(...)` | `IndentationError: expected an indented block` | 缩进 4 空格 |
| 缩进混用 Tab 与空格 | 一行 Tab、一行空格 | `TabError: inconsistent use of tabs and spaces` | 统一用 4 个空格 |
| 调用函数忘括号 | `test` | 不执行，无输出（或显示 `<function test at 0x...>`）| `test()` |
| 忘记 `return` | 函数末尾没有 return | 返回 `None`，外部变量变成 `None` | 需要结果就必须 `return` |
| 一维 shape 忘逗号 | `np.zeros((15), dtype=int)` | 恰好也能跑（`(15)`=整数 15），但**概念错了**，二维时会出问题 | `np.zeros((15,), dtype=int)` |
| 切片右端理解错 | 想要 0,1,2 却写 `0:2` | 只拿到 0,1 —— 少一个 | `0:3`（左闭右开） |
| 索引差一 | 想要"第 100 个"写 `x[100]` | `IndexError`（有效索引 0–99）| `x[99]` |
| 二维索引写成两层方括号 | `z[row][column]` | 能跑但更慢（先切出一整行再取元素），不规范 | `z[row,column]` |
| 忘了 `+1` | `x[step]=step` | x 从 0 开始而不是 1，整张图偏移 | `x[step]=step+1` |
| 数组类型混用 | `np.array([1, 'a', 2.5])` | NumPy 会把全部强制转成字符串，后续数学运算报错 | 一个数组只放一种类型 |
| 把 `*` 当矩阵乘法 | `A*B` 期待矩阵积 | 得到逐元素积（讲义专门警告）| 矩阵乘法用 `A @ B` 或 `np.matmul(A,B)` |
| 忘记 import | 直接用 `np.zeros` | `NameError: name 'np' is not defined` | 先 `import numpy as np` |

### 6.2 常见报错速查

| 报错 | 典型原因 | 修法 |
|---|---|---|
| `ModuleNotFoundError: No module named 'numpy'` | 模块没装 / 环境不对 / 拼写错 | 老师原话：「如果 import 语句报错，意味着模块不在那里——没装，或者找不到。」用 `conda install numpy` 或切回课程的 Anaconda environment |
| `NameError: name 'np' is not defined` | 忘了 import，或 notebook 的 import cell 没运行 | 运行最上面的 import cell（**notebook 从上到下的执行顺序很重要**）|
| `IndexError: index 6 is out of bounds for axis 1 with size 6` | 整数索引越界（6 列的有效索引是 0–5）| 检查数组尺寸；老师："你建了 5×5 的矩阵却说放到第七列，它会说我做不到" |
| `IndentationError: expected an indented block` | `:` 后面没缩进 | 缩进 4 空格 |
| `SyntaxError: invalid syntax` | 少冒号、括号不配对 | 从报错行**往上一行**看（很多语法错误报在下一行）|
| `TypeError: Argument Z must be a 2-dimensional array` | 传给 `contourf` 的 z 是 `None`（函数忘了 return）或形状不对 | 加 `return z`；`print(z.shape)` 检查形状 |
| `ValueError: operands could not be broadcast together with shapes (100,) (300,)` | 两个数组形状不匹配却做逐元素运算 | 检查两边 `.shape` 必须一致（或可广播）|
| `AttributeError: module 'numpy' has no attribute 'zeross'` | 函数名拼错 | 查文档；善用 notebook 里的 Tab 补全 |

### 6.3 概念难点

**（1）"能跑" ≠ "正确"**（老师全课反复强调）
- Exercise 2 的自查：看色标量级是 200 还是 10^4。
- 一维示例的自查：98² = 9604 心算可验。
- **永远问自己："它给了我期望的答案吗？"**

**（2）切片越界不报错，整数索引越界报错**
这是 Exercise 1 官方解答里 `0:7`、`2:6` 能跑通的原因。**这意味着切片写错尺寸时 Python 不会救你**——必须自己核对形状。养成 `print(arr.shape)` 的习惯。

**（3）`z[...] = ...`（原地修改）vs `z = ...`（重新绑定）**
见 §Exercise 5 的详解。这是理解"函数为什么有时候不用 return 也生效、有时候必须 return"的关键。**Exercise 4 与 Exercise 5 恰好是这对概念的完美对照，考试极可能考。**

**（4）NumPy 数组 vs list 的四点差别**

| | list | numpy array |
|---|---|---|
| 数据类型 | 可以混（`[1, 'a', 2.5]`）| **必须统一**（`dtype`）|
| 大小 | 可动态 `append` | **创建时就定死** |
| 数学运算 | `[1,2]+[3,4]` = `[1,2,3,4]`（**拼接**！）| `array+array` = **逐元素相加** |
| 效率 | 慢，"太手工" | 快，底层是连续内存 |

**⚠️ 最容易混淆的一点**：`list1 + list2` 是**拼接 (concatenation)**，`array1 + array2` 是**逐元素相加**。同一个 `+` 号，语义完全不同。

**（5）二维索引 `[row, column]` 的顺序**
第一个索引永远是**行 (row, axis 0)**，第二个是**列 (column, axis 1)**。`np.zeros((5,6))` = 5 行 6 列。

**（6）`contourf(x, y, z)` 的轴向约定（进阶注意）**
Matplotlib 期望 `Z[i,j]` 对应 `y[i]` 和 `x[j]`——也就是 **Z 的第一个索引对应 y 轴**。而 Practical 里的代码写的是 `z[row,column] = x[row] + ...`，即第一个索引对应 x。对 `z = x+y` 这种对称函数看不出区别；对 `z = x+y*x` 图会相当于**转置**（横轴上画的其实是代码里的 y）。由于题目给出了参考图、大家的代码写法一致，结果能对上，所以本课不追究——**但要知道这个约定，将来自己画图时才不会把轴弄反。**

**（7）Notebook 的执行顺序陷阱**
Jupyter 的 cell 可以任意顺序运行，变量会残留在内存里。**报"某个变量没定义"或"结果莫名其妙"时，先 Kernel → Restart & Run All**，从头顺序跑一遍。

**（8）题面与解答的尺寸不一致（本 Notebook 的已知瑕疵）**
- Exercise 2：题面 200×300，解答 100×100。
- Exercise 4：题面 200×200，解答 300×300。
- Exercise 5：题面 200×200，解答 300×300。
**复习时以方法为准，不要被数字困扰。** 自己练习时可以两种都跑一遍，正好检验代码的通用性。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| module | 模块 | 一个 `.py` 文件，里面装着函数和变量，可以被 `import` 进来用 |
| package / library | 包 / 库 | 一组相关模块的集合，如 `numpy`、`scikit-learn` |
| function | 函数 | 用 `def` 定义的一段可反复调用的代码；接收输入、返回输出 |
| `def` | 定义（关键字）| 告诉 Python 解释器"我要定义一个函数了" |
| `return` | 返回（语句）| 结束函数并把结果交还给调用者；不写值则返回 `None` |
| call (a function) | 调用（函数）| 写"函数名 + 括号"来执行函数，如 `test()` |
| argument / parameter | 实参 / 形参 | 形参是定义时括号里的名字，实参是调用时真正传进去的值 |
| `import` | 导入 | 把某个模块加载进当前程序 |
| alias | 别名 | `import numpy as np` 里的 `np`，用来简写模块名 |
| dot operator `.` | 点运算符 | 访问模块内部的函数/变量，如 `np.zeros` |
| interpreter | 解释器 | 把你写的 Python 代码翻译成计算机能懂的东西；看不懂就报错 |
| indentation | 缩进 | Python 用缩进（4 空格）表示代码块的从属关系 |
| syntax highlighting | 语法高亮 | 编辑器/notebook 用不同颜色标出关键字、内建函数、自定义函数 |
| documentation | 文档 | 官方说明书，告诉你一个函数能接收什么参数、返回什么 |
| NumPy (Numerical Python) | 数值 Python | 处理数值数组的标准模块，本课从此贯穿始终 |
| array | 数组 | NumPy 的核心数据结构，同类型元素的固定大小容器 |
| matrix | 矩阵 | 二维数组的数学叫法 |
| `dtype` (data type) | 数据类型 | 数组元素的类型，如 `int`（整数）、`float`（浮点数）|
| `int` / integer | 整数 | 无小数点的数，打印为 `0` |
| `float` / floating point | 浮点数 | 带小数点的数，打印为 `0.` |
| shape | 形状 | 数组各维度的大小，如 `(5,6)` = 5 行 6 列 |
| `np.zeros()` | 全零数组函数 | 按指定形状和类型创建一个全是 0 的数组 |
| `np.array()` | 数组构造函数 | 把 list（或嵌套 list）转成 NumPy 数组 |
| index / indexing | 索引 | 用位置编号取元素；**Python 从 0 开始** |
| slicing | 切片 | 用 `start:end` 一次取/存一段，**左闭右开** |
| `:` operator | 冒号运算符 | 在切片里表示"从…到…"，单独一个 `:` 表示"全部" |
| element-wise operation | 逐元素运算 | 两个数组对应位置的元素分别做运算 |
| vectorisation | 向量化 | 用整数组运算替代显式 for 循环，更快更短 |
| matrix multiplication | 矩阵乘法 | 线性代数的行乘列求和，`A @ B`；**与 `A*B` 不同** |
| nested loop | 嵌套循环 | 循环里再套循环，用来遍历二维数组的行与列 |
| in-place modification | 原地修改 | 直接改数组内容（`z[i,j]=...`），函数外也能看到 |
| rebinding | 重新绑定 | 让变量名指向新对象（`z = ...`），函数外看不到 |
| local variable | 局部变量 | 只在函数内部存在的变量 |
| side effect | 副作用 | 函数除了返回值以外，还偷偷改了外部的东西 |
| overhead | 额外开销 | 运行某种方式时额外付出的资源代价（如 notebook 要开浏览器）|
| file extension | 文件扩展名 | `.py`（Python 脚本）、`.ipynb`（Jupyter Notebook），告诉计算机文件类型 |
| `PYTHONPATH` | Python 搜索路径 | 解释器寻找模块的目录列表 |
| version control | 版本控制 | 记录软件不同版本历史的做法/工具（如 Git/GitHub）|
| end user | 端用户 | 只使用软件、不参与开发的人；只看到冰山一角 |
| mature (code/module) | 成熟的（代码/模块）| 经过长期使用与测试、稳定可靠，不需要再改 |
| package manager | 包管理器 | 帮你安装模块并解决依赖冲突的工具（如 `conda`）|
| `matplotlib` / `pyplot` | 绘图模块 | Python 标准绘图库；`plt` 是 `matplotlib.pyplot` 的惯用别名 |
| `contourf` | 填充等值线图 | 把二维数值面用颜色块画出来 |
| `colorbar` | 色标 | 图旁的颜色-数值对照条 |
| `cmap` (colormap) | 配色方案 | 数值到颜色的映射规则，如 `'RdGy'`（红-灰）|
| Kelvin (K) | 开尔文 | 绝对温标；298.15 K = 25 °C = 常用室温参考值 |
| Conway's Game of Life | 康威生命游戏 | Week 4 内容：用 4 条规则在二维网格上演化的元胞自动机 |
