# Week 4 — 模块与函数（三）：用 NumPy 二维数组实现 Conway's Game of Life（康威生命游戏）

> 课程：EART11200 The Natural Scientist's Toolkit — Computer Programming（Hilary Term / 春季学期）
> 材料：`Lecture4_25.pdf`（讲义 md 版）、`EART11200 - 18-Feb-transcript.md`（课堂录音转写）、`Practical_4.ipynb`（md 版）
> 本周是「Modules and Functions」主题的第 3 讲，也是**评估（assessment）可选题目开始的第一周**。

---

## 一、本周主题

### 1.1 一句话概括

本周不再学新语法，而是**把前三周学的全部零件（NumPy 数组、for 循环、嵌套循环、if/elif/else 条件语句、自定义函数 def/return）组装成一个能跑、能看的完整程序** —— Conway's Game of Life（康威生命游戏）。这是编程教学中最经典的「综合练习」，因为它恰好需要用到上面每一样东西。

老师在转写里说得很直白：

> "today we'll stop being so abstract, so we'll actually build something that has a particular endpoint that we can visualize."
> （今天我们不再那么抽象了，我们要真正做出一个有明确终点、看得见结果的东西。）

> "it's typically when you're learning to code, this is one of the suggested examples, because it brings together everything we've learned up to this point."

### 1.2 课程整体位置（course layout）

讲义第一页给出了 9 周的地图，务必记住自己在哪：

| 周次 | 内容 | 阶段 |
|---|---|---|
| 1–2 | 'Vanilla' Python：data types、loops、basic operations、conditionals | 纯 Python |
| 3 | Modules and Functions；The NumPy module | 模块与函数 |
| **4** | **Conway's Game of Life（本周）** | 模块与函数 |
| 5 | Differential Equations（微分方程数值解） | 模块与函数 |
| 6 | Pandas and data discovery | 数据科学 |
| 7 | Geospatial analysis（地理空间分析） | 数据科学 |
| 8 | Statistical Analysis | 数据科学 |
| 9 | Cluster Analysis（机器学习 / scikit-learn） | 数据科学 |
| 10–12 | Creating a notebook assessment：从 week 4–9 中**选一个主题**做 notebook 提交 | 评估 |

**重要提醒（转写）**：

> "actually from this week onwards begins the assessment option... there will be an option based on today's content where you'll get to simulate Conway's Game of Life for certain scenarios and write that up."

也就是说：**从本周（Week 4）起，每一周的内容都可能成为你最终 notebook 作业的选题**。本周对应的选题是「模拟 Gosper glider gun（高斯帕滑翔机枪）并写报告」。老师说细节 Easter（复活节假）前后才会讲，但现在就该心里有数。

### 1.3 上周回顾（recap，讲义原话）

- **Functions** 帮我们把一组操作重复很多次 —— 用 `def` 和 `return` 语句定义。
- **Modules** 是函数的集合，用 `.` 运算符访问里面的函数（如 `np.zeros`）。
- **NumPy module** 是 Python 中处理数值运算的标准方式。

转写里老师的补充解释：

> "When we install Python... there are some internal functions for us to use, but often we have to build on top of that standard distribution and bring other modules in, so when we created our environment, we did that."
> 装好的 Python 自带一些内建函数，但我们常常要在标准发行版之上再引入别的模块 —— 我们建 environment（conda 环境）时就是在做这件事。

> "We can have a module file written in Python, a .py file, and that will have functions defined using the following syntax, so we use the `def` keyword, name of the function, and then we have brackets, and if there's nothing in the brackets, we're not passing anything, but we still might ask the function to do something, and the `return` statement closes that function off, or it can return variables back."
> 模块就是一个 `.py` 文件；括号里没东西表示不传参，但函数仍然可以做事；`return` 既可以「结束函数」也可以「把变量送回去」。

> "There's no standard module for solving Conway's game of life... you'll see a certain flavor I've used of implementing Conway's rules of life... but there are many different ways of doing it."
> 生命游戏没有标准模块，网上/ChatGPT 上写法千奇百怪，本课只是**其中一种写法**。所以看到别人代码不一样很正常。

### 1.4 为什么地球/环境科学的学生要学这个？

老师在转写里花了不少篇幅解释科学动机，这部分**很可能是考点/写报告时的「引言」素材**：

1. **模式识别（pattern recognition）是环境科学的核心**
   > "the interesting thing in all environmental science is we often try and recognise what's leading to behaviour that we observe."
   > 我们观察到某种现象，然后要反推是什么规则导致了它。

2. **科研的目标是「最简规则」，不是「最复杂方程」**
   > "scientific research isn't all about creating the biggest set of equations and solving the most complex thing, we're always targeting understanding it in the simplest way, because once we do that we can then implement that in a computational programme."
   > 生命游戏只有 4 条极简规则，却能产生从高度有序到完全混沌的行为 —— 这正是「简单规则 → 涌现复杂性（emergence）」的教科书例子。

3. **和二年级 Environmental Modelling 的 agent-based model（基于主体的模型）直接相连**
   > "in the second year there's an environmental modelling option... there's a model in that called an agent based model where you have individual synthetic agents that have sets of rules for how they interact with each other in the environment. Similar kind of thing."
   > 生命游戏的每个 cell 就是最简版本的 agent；ABM 广泛用于生态、人口、土地利用、传染病等环境模拟。

4. **与课程末尾的机器学习形成呼应**
   > "what we're doing today is we're starting from the knowledge of the rules that dictate this, but then at the end of the course we'll assume we know nothing, and we actually need an algorithm to tell us what are the distinct bits in here."
   > 本周是「已知规则 → 生成模式」（正问题）；Week 9 的聚类分析是「已知数据 → 反推分组/模式」（反问题）。这正是数据科学正在革新科学研究的地方。

5. **历史背景**：John Horton Conway（1937-12-26 — 2020-04-11），英国数学家，研究有限群论、数论、组合博弈论、编码理论，也做了大量趣味数学贡献，其中最著名的就是发明了 cellular automaton（细胞自动机）"Game of Life"。生命游戏最初被大量用于**生物学**建模（种群、繁殖、竞争），后来扩展到人类互动模拟。

---

## 二、核心概念

### 2.1 Conway's Game of Life 是什么

- **Universe（宇宙）**：一个二维空间 —— 在我们这里就是一个 **2D NumPy array**。
- **Cell（细胞）**：数组中的每一个元素。只有两种状态：
  - `1` = alive（活）→ 画出来是**黑色**
  - `0` = dead（死）→ 画出来是**白色**
- **Specie（物种）/ 图形**：一组活细胞构成的形状。
- **Neighbours（邻居）**：**水平、垂直、对角相邻的 8 个格子**（即 Moore neighbourhood，摩尔邻域）。注意：**自己不是自己的邻居**。
- **Time step / generation（时间步/世代）**：把整个宇宙扫描一遍并按规则更新一次，就是一个时间步。**动画 = 反复执行时间步**。

### 2.2 生命的四条规则（The 4 laws）— 必须背下来

讲义与 notebook 原文（英文务必记住原句，写报告要引用）：

1. **Any live cell with fewer than two live neighbours dies, as if by underpopulation.**
   活细胞，活邻居 < 2 → 死（人口过疏）。
2. **Any live cell with two or three live neighbours lives on to the next generation.**
   活细胞，活邻居 = 2 或 3 → 存活到下一代。
3. **Any live cell with more than three live neighbours dies, as if by overpopulation.**
   活细胞，活邻居 > 3 → 死（人口过密）。
4. **Any dead cell with exactly three live neighbours becomes a live cell, as if by reproduction.**
   死细胞，活邻居**恰好 = 3** → 复活（繁殖）。

**记忆要点**：
- 活细胞有 **3 条规则**，死细胞只有 **1 条规则**（老师转写里特意强调："there are three rules if you're alive and there's one rule if you're dead"）。
- 死细胞是 `== 3`（**恰好**），不是 `>= 3`。这是最容易写错的地方。
- 规则 2 中的「2 或 3」在 Python 里可以写成 `2 <= count <= 3`。

### 2.3 三类涌现模式（notebook 明确列出）

| 类型 | 英文 | 行为 | 例子 |
|---|---|---|---|
| 静物 | **Still life** | 永远不变，固定在棋盘上 | Block, Tub, Boat, Beehive, Loaf |
| 振荡子 | **Oscillators** | 每步都变形，但若干代后回到初始形状 | Beacon（周期 2）、Toad（周期 2）、Pulsar（周期 3 / 老师口误说 "period of three"） |
| 飞船 | **Space-ships** | 一边变形一边在棋盘上**移动** | Glider（周期 4，斜向移动 1 格）、LWSS = Light-Weight SpaceShip（周期 4，横向移动 2 格） |

老师转写里的说明：

> "you'll come across information online that gives you the number of oscillations a species has. And this one looks like it's blinking. So I have an oscillation of two. So it'll come back to itself in two steps. Some have much more complex oscillations, maybe 12."

> "once you find material online, they even have names. Relatively boring names like block, beehive, loaf, boat."

还有一个巨大的在线社区（LifeWiki 之类）收录了各种形状和它们的相互作用。老师提到 **Gosper glider gun**：

> "you have two things that start meeting halfway and they produce little spaceships by the looks of it that travel across the screen."
> 两组图形在中间相遇，不断「生产」出滑翔机往外飞 —— 这是 Week 4 对应的 assessment 选题。

### 2.4 把规则翻译成程序：5 个必须实现的步骤

notebook 明确给出的「程序化清单」：

1. 定义代表物种的 2D 数组（Defining 2D arrays that represent species）。
2. 写一个函数，搜索每个 cell 的紧邻空间中的 1 和 0。
3. 统计 1 的个数（counting）。
4. 按 4 条规则改变每个 cell 的值。
5. 把 2–4 重复任意多个时间步（loop）。

### 2.5 关键结构：四层嵌套 for 循环（four nested for loops）

这是本周**最重要的结构性认识**。老师在转写里反复讲：

> "if you've got two for loops to do row and column, we're going to have another set of two for loops for the space around us. So it's going to look like four nested for loops."

```
外层 2 层循环：走遍宇宙的每个 cell（row, col）
    └── 内层 2 层循环：走遍当前 cell 周围 3×3 的邻域（row2, col2）
            └── 排除「越界」和「自己」，统计活邻居数 count
    └── 用 count 和当前 cell 的值，套用 4 条规则，写入 new_space
```

**外层与内层循环边界的关键区别**（老师专门强调）：

> "Notice here in the outer for loops I specified a single number 10 and 23. But I have to now work with the coordinates I'm currently at."

- 外层：`range(total_rows)` —— 是一个**固定**的数字。
- 内层：`range(row-1, row+2)` —— 边界**依赖于当前位置**，是**动态**的。

### 2.6 两个必须排除的情况

老师转写：

> "Ignore everything outside the universe and ignore where I am because I'm not my neighbor."

1. **越界（off the board）**：如果你在第 0 行，「上面一行」根本不存在，没有数据可数 → 用 `pass` 跳过。
2. **自己（same cell）**：`row2 == row and col2 == col` 时，那是自己不是邻居 → 用 `pass` 跳过。

这也解释了为什么边界处的行为和内部不同：宇宙是**有限的、不循环的（无 wrap-around）**，边缘细胞天然邻居更少。

### 2.7 同步更新（synchronous update）—— 为什么必须用 `new_space`

**这是概念上最容易被忽略、但决定程序对错的一点。**

函数里第一行是：

```python
new_space = np.zeros((total_rows,total_cols),dtype=int)
```

所有的**读取**都发生在旧数组 `space` 上，所有的**写入**都发生在新数组 `new_space` 上。

**为什么不能就地修改（in-place）？**
如果你直接改 `space[row,col]`，那么当循环走到下一个 cell 时，它数邻居时会读到**已经被更新过**的值，等于「这一代的一部分细胞已经活在下一代了」。生命游戏要求**所有细胞同时（同步）更新**，所以必须用两块内存：一块读、一块写。

老师转写的表述：

> "have a function that searches through the whole space once and returns the new space. But... what we want to do is take an old universe pass it into the function get the new one back and then pass that one in. So we keep updating the space and that's where we get the animated behavior."

对应主循环代码：

```python
Beacon_new = search_each_cell(6,6,Beacon)  # 旧 → 新
Beacon = Beacon_new                        # 新覆盖旧，准备下一轮
```

### 2.8 数组「地址系统」与切片放置（把物种「投放」进宇宙）

老师转写：

> "rather than then specifying individual elements of the universe array, I've already created this tub space and I'm going to drop the whole space into the universe canvas... We can actually specify the range of rows and columns in a single call using the colon statement."

两种给数组赋值的方式：

**方式 A：逐个元素**（画小图形时用）
```python
Block[1,1] = 1
```

**方式 B：整块切片赋值**（把小图形放进大宇宙时用）
```python
Universe[11:17, 12:19] = LWSS
```
右边 `LWSS` 的形状必须和左边切片选出的区域形状**完全一致**（这里 6 行 × 7 列），否则 NumPy 会报 broadcast 错误。

**index 从 0 开始的换算**（notebook 明说）：
> "for the 12th row and 13th column, I need to refer to element [11,12]."
> 第 12 行第 13 列 → 索引 `[11,12]`。

---

## 三、语法速查与函数表

### 3.1 函数 / 语法速查表

| 名称 | 作用 | 用法示例 | 注意事项 |
|---|---|---|---|
| `import numpy as np` | 导入 NumPy 并起别名 | `import numpy as np` | `as np` 纯粹为了少打字，是全社区惯例 |
| `import matplotlib.pyplot as plt` | 导入绘图子模块 | `plt.imshow(...)` | 注意是 `matplotlib.pyplot`，不是 `matplotlib` |
| `np.zeros(shape, dtype=int)` | 创建全 0 数组 | `np.zeros((6,6),dtype=int)` | **shape 必须是元组**，双层括号 `((6,6))`；不写 `dtype=int` 默认是 `float`，打印出来会是 `0.` 而不是 `0` |
| `array[i,j]` | 访问/赋值单个元素 | `Block[1,1]=1` | NumPy 用 `[i,j]`，**不要写成 list 风格的 `[i][j]`**（虽然也能跑，但慢且不地道）；索引从 0 开始 |
| `array[a:b, c:d]` | 切片：取/赋一个子矩形 | `Universe[11:17,12:19] = LWSS` | **左闭右开**：`11:17` 是第 11,12,13,14,15,16 行，共 6 行；两边形状必须匹配 |
| `array[:,:] = 0` | 把整个数组清零 | `Universe[:,:]=0` | notebook 提到可用来「清空宇宙」；`:` 表示「全部」 |
| `def name(a,b,c):` | 定义函数 | `def search_each_cell(total_rows,total_cols,space):` | 冒号 + 缩进；参数是**位置参数**，调用时顺序必须一致 |
| `return x` | 返回值并结束函数 | `return new_space` | 只写 `return`（无值）等价于返回 `None`；函数体里没有 `return` 也返回 `None` |
| `for i in range(n)` | 循环 n 次，i = 0..n-1 | `for row in range(10):` | 单参数版本从 0 开始 |
| `for i in range(a,b)` | 从 a 到 b-1 | `for row2 in range(row-1,row+2):` | `row+2` 才能包含 `row+1` —— 右开区间的经典陷阱 |
| `if / elif / else` | 条件分支 | `if space[row,col] > 0: ... elif ...` | `elif` 只有前面条件都为假时才判断；缩进决定归属 |
| `==` | 相等**比较** | `if count == 3:` | **与赋值 `=` 严格区分**。notebook 特别提示："When checking a value we use two equals signs `==` as we are not *assigning* a value" |
| `2 <= count <= 3` | 链式比较 | `elif 2<=count<=3:` | Python 特有语法，等价于 `count>=2 and count<=3`；C/Java 不能这么写 |
| `or` / `and` | 逻辑或 / 逻辑与 | `if (row2<0) or (row2>=total_rows):` | Python 用英文单词，**不是** `\|\|` 和 `&&` |
| `pass` | 什么都不做的占位语句 | `pass` | 语法上需要一个语句体但你不想做任何事时使用；不能留空行，否则 `IndentationError` |
| `count = count + 1` | 累加计数器 | `count=count+1` | 也可写 `count += 1`；**必须在进入每个新 cell 时重置 `count = 0`** |
| `plt.imshow(A, cmap='binary')` | 把 2D 数组画成图像（俯视） | `plt.imshow(Block, cmap='binary')` | `cmap='binary'`：0→白，1→黑。老师："imshow is just a way of plotting a two dimensional surface so you're looking above it" |
| `plt.title('...')` | 给当前坐标轴加标题 | `plt.title('Block')` | 必须在 `plt.show()` **之前**调用 |
| `plt.subplot(1,2,1)` | 在 1 行 2 列的网格中选第 1 格 | `plt.subplot(1,2,1).imshow(Tub, cmap='binary')` | 编号**从 1 开始**（不是 0！）；返回一个 axes 对象，可以直接 `.imshow()` |
| `plt.show()` | 渲染并显示图 | `plt.show()` | 一次 `show()` 结束当前 figure；之后再画会开新图 |
| `plt.subplots(figsize=(12,12))` | 创建 figure 和 axes，指定尺寸（英寸） | `fig, ax2 = plt.subplots(figsize=(12, 12))` | 返回**两个**值，必须用两个变量接收 |
| `clear_output(wait=True)` | 清空 Jupyter 单元格输出 | `from IPython.display import clear_output` | `wait=True` 表示等新输出准备好再清，避免闪烁 —— 这是做「伪动画」的关键 |
| `time.sleep(0.2)` | 暂停 0.2 秒 | `import time; time.sleep(0.2)` | 控制动画速度；单位是**秒**（可以是小数） |
| `print()` | 打印 | `print("An empty array",Block)` | 多个参数用逗号分隔，输出时用空格连接；**`print` 本身返回 `None`** |

### 3.2 图表生成方式与判读要点

本周所有「图」都是同一种：**用 `plt.imshow()` 把 2D 整数数组渲染成黑白棋盘**。

**生成方式**：
```python
plt.imshow(Block, cmap='binary')  # 数组 → 图像
plt.title('Block')                # 加标题
plt.show()                        # 显示
```

**如何判读 / 如何检查结果是否正确**：

1. **坐标方向**：`imshow` 默认把 **row 索引画在纵轴（y，向下增大）**，**col 索引画在横轴（x，向右增大）**。也就是说 `A[1,2]` 的黑格出现在「从上往下第 2 格、从左往右第 3 格」。**注意 y 轴是往下增大的**，与数学坐标系相反。
2. **颜色**：`cmap='binary'` 下 **0 = 白，1 = 黑**（值越大越黑）。老师说："The white box is a zero, the black box is one."
3. **坐标轴上的刻度数字**：老师提醒过 —— "ignore these numbers for now. These are just common default matplotlib values for the axis." 那些是 matplotlib 自动生成的默认刻度，不是你要关心的东西。
4. **判断正确性的实用方法**：
   - **先 `print(array)` 再画图**。文本形式的 0/1 矩阵比图更容易逐个核对。notebook 的第一段代码就是这么做的（先打印空数组，再打印填好的数组，最后画图）。
   - **对照参考图（Figure 1/2/3）逐格数**，特别注意「外圈留白」有几圈 —— notebook 提示 "Check the size of each array you need, accounting for white space around the outside."（外围的空白也要算进数组尺寸里，否则边缘细胞的邻域会算错。）
   - **用已知周期验证**：Beacon 应该在 2 步后**完全回到初始形状**；Block/Tub/Boat 应该**永远不动**。如果 Block 变形了，说明规则实现错了。
   - **Exercise 3 的 before / after 双子图**就是一种「肉眼单元测试」—— 讲义 goals 里明确写着 "Start to think about how you check for correct behaviour in working code."（开始思考如何检验代码的行为是否正确。）

---

## 四、课堂补充（transcript 独有）

这一节都是转写里才有、讲义 PDF 上没有的内容。

### 4.1 老师对「为什么是四层循环」的现场推导

> "So in this case, when I get to the black cell and that value is one, and then I have another loop that checks the values around it and it will count zero. There are zero cells. So therefore we'll switch the black to a white cell. It will turn it from one to zero."

老师用讲义上的 3×3 示意图逐条演示：一个孤立的黑格，邻居数为 0，`0 < 2` → 触发规则 1（underpopulation）→ 变白。这是把「规则」映射到「代码」最直观的一次演示。

### 4.2 老师现场把规则翻成伪代码

> "imagine if cell one equals one and if total cells around us equals less than two, cell one equals to zero. So we can start translating this into Python code."

即：
```
if cell == 1 and count < 2:
    cell = 0
```
这就是 Exercise 3 要你补的东西的原型。**先用自然语言写伪代码，再翻译成 Python** —— 这是老师示范的解题方法论。

### 4.3 关于「边界不做环绕」的现场说明

> "notice that the edges and at the top, there is nothing above and to the left or right. So we're literally just counting within our space."

宇宙是有限的、有硬边界的。边缘的细胞邻居更少，所以边缘行为与内部不同。（数学上更「优雅」的做法是 toroidal wrap-around，把上下、左右接起来做成环面，但本课**不这么做**。）

### 4.4 老师亲手拆解讲义上那段搜索代码

> "So for example imagine that we're this blue dot here. We're at row one and column five. This is my search space. So the for loop has to be bounded by that... So these statements `row minus one` and `row plus two` is allowing me to do that and the `column minus one` and `column plus two` is allowing me to do that."

**为什么是 `+2` 不是 `+1`**：因为 `range(a,b)` 右端开区间，`range(row-1, row+2)` 才能产生 `row-1, row, row+1` 这三个值。这是本周最高频的踩坑点。

> "There's some extra complexity I need to add to make sure we don't go outside of the universe space because if I'm on the top row then a row above doesn't mean anything. There's no data there. So there's an extra if statement here that more or less says if you're outside of the space `pass` — that means do nothing."

### 4.5 老师对 Python 性能的现场吐槽（重要的工程认识）

> "I've talked a bit about Python being slow compared to other languages. You'll see that if you make it very large and you make it so you can see each step incrementally it will start to slow down. So people have coded this in different languages and then you visualize it on the screen."

**为什么慢**：四层嵌套 for 循环，对一个 N×M 的宇宙，每个时间步要做 `N × M × 9` 次 Python 层面的循环迭代。50×50 的宇宙每步就是 22,500 次内层迭代，跑 100 步 = 225 万次。纯 Python 循环远慢于 NumPy 的向量化运算或 C/Fortran。

> "you could implement a universe with a thousand by a thousand and just put random ones and zeros in and see what happens and see if you reach a stable state or not. You can lose hours looking at stuff like this."

（1000×1000 用这套四层循环会非常慢 —— 想玩大的需要 NumPy 向量化或卷积法。）

### 4.6 老师提到的「延伸玩法」

> "you could, if you wanted to, check out lots and lots of resources online where people slightly tweak what we've done and then create quite stunning visualisations. Some people have even done it across a globe so you can see things moving across a sphere."

可以改：宇宙大小、迭代速度、颜色（`cmap`）、初始条件、甚至把它铺到球面上。

### 4.7 老师亲自过了一遍 notebook（现场演示）

> "That exercise three really is the main exercise. And you get to test it by passing it the Beacon and that's the oscillating shape. So you have to implement the four rules. In the solutions I've done that. But see if you can do it yourself. And obviously if you can't, read through the solutions and make sure it makes sense as to what's happening with the conditional statements and how it's passing new cell back."

**Exercise 3 是本周唯一的重头戏**，其他都是铺垫或复制粘贴。

> "What's missing here is the implementation then of the four rules. Because at the moment there's no `return`. It just returns nothing. But we want to return a new space back according to those four rules."

老师明确指出 notebook 第一版函数**故意**写成 `return`（什么都不返回），这是为了让你注意到「函数必须有 return 才能把结果送出去」。

### 4.8 课堂末尾的重要提醒

> "It's a good point at this stage to really — if there's anything that you're uncertain about as to how we've created arrays, for loops, conditionals — let us know, because we will keep using this moving forward, particularly when we get to data modules as well. We'll still use conditional statements. We still have to implement logic in our code."

**Week 4 是一个分水岭**：数组、循环、条件语句从此以后天天用（Week 5 微分方程、Week 6+ Pandas 都要）。有不懂的必须现在补。

---

## 五、Practical 要点（Practical_4.ipynb）

> notebook 三大板块：
> 1. 通过修改 2D NumPy 数组创造不同形状（Exercise 1, 2）
> 2. 创建一个搜索局部邻域的函数（Exercise 3, 4）
> 3. 用多个物种填充 Conway 的宇宙（无编号练习）
>
> notebook 提示：**看到 `-------'INSERT CODE HERE'-------` 就是要你写代码的地方**。
> notebook 也说明：不必在课上做完，可以带回去继续；Solutions 文件夹里有参考答案。

---

### 5.0 第 0 格：Google Colab 兼容性样板代码

**题目要求**：先运行这一格。若不在 Colab 上会得到确认信息。

```python
if 'google.colab' in str(get_ipython()):
    # get_ipython() 返回当前 IPython/Jupyter 内核对象；
    # str(...) 把它转成字符串，如果是 Colab 环境，字符串里会含 'google.colab'
    from google.colab import drive          # 只有在 Colab 上才导入 Google Drive 挂载工具
    mount='/content/gdrive'                 # 定义挂载点路径
    print("Colab: mounting Google drive on ", mount)
    drive.mount(mount)                      # 把你的 Google Drive 挂到 /content/gdrive
    drive_root = mount + "/My Drive/Colab Notebooks/DEES_first_year/DEES_programming_course"
    # 字符串拼接出课程文件夹的完整路径
    print("\nColab: Changing directory to ", drive_root)
    %cd $drive_root                         # IPython 的 magic command，切换工作目录
else:
    print('Not running on CoLab')           # 本地 Jupyter / Anaconda 走这条分支
```

**输出**：
```
Not running on CoLab
```

**输出解读**：说明是在本地环境（Anaconda/Jupyter）运行，没有做任何 Drive 挂载 —— 这正是我们想要的。如果这里没打印任何东西或报错，说明你不是在 IPython 内核里跑（比如直接用 `python xxx.py` 跑，`get_ipython()` 会 `NameError`）。

**语法要点**：
- `%cd` 前面的 `%` 是 **IPython magic command**，只在 Jupyter/IPython 里有效，普通 `.py` 脚本里会语法错误。
- `$drive_root` 是 magic command 里引用 Python 变量的写法。
- 这一段跟生命游戏本身无关，纯粹是环境适配，理解即可。

---

### 5.1 示范代码：画出 Block（还给你的完整示例）

**题目要求**：读懂给出的代码和注释，理解如何用 2D 数组「画」出一个形状。

**解题思路**：
1. 用 `np.zeros` 开一块全 0 的画布（全白）。
2. 打印出来确认确实是一个 0 矩阵。
3. 在需要变黑的位置逐个赋值为 1。
4. 再打印确认。
5. 用 `plt.imshow` 画出来。

**完整代码 + 逐行注释**：

```python
#%matplotlib inline #this is to help us retrieve those love animations!
# ↑ 被注释掉了。%matplotlib inline 让图直接嵌在 notebook 里。
#   新版 Jupyter 默认就是 inline，所以可以不写；若图不显示可以取消注释试试。

import numpy as np                  # 导入数值计算库 NumPy，别名 np（社区惯例，纯为方便）
import matplotlib.pyplot as plt     # 导入绘图库的 pyplot 子模块，别名 plt
from matplotlib import animation, rc # 导入动画相关工具（本 cell 其实没用到，为后面铺垫）

# 建立 'Block'。数组名可以随便取，这里就用图案本身的名字
Block = np.zeros((4,4),dtype=int)
# ↑ 建一个 4 行 × 4 列、全部填 0、数据类型为整数(int) 的 NumPy 数组
#   注意双层括号：外层是函数调用的括号，内层 (4,4) 是表示形状的元组 tuple
#   dtype=int 很重要：不写的话默认是 float64，打印出来是 0. 而不是 0

print("An empty array",Block)       # 打印字符串 + 数组，确认是不是一片 0

# 现在把某些格子设为 1（变黑）。Block 图案 = 正中间的 2×2 方块
Block[1,1]=1                        # 第 1 行第 1 列（从 0 数起）设为活
Block[1,2]=1                        # 第 1 行第 2 列
Block[2,1]=1                        # 第 2 行第 1 列
Block[2,2]=1                        # 第 2 行第 2 列
# ↑ 这四个格子构成 4×4 画布正中央的 2×2 黑块，四周留一圈白边

print(print("A finished array",Block))  # ⚠ 注意这里是双重 print，见下方「输出解读」

# 画图
plt.imshow(Block, cmap='binary')    # 把 2D 数组渲染成图像；cmap='binary' → 0 白 1 黑
plt.title('Block')                  # 给当前图加标题
plt.show()                          # 渲染并显示
```

**运行输出**：
```
An empty array [[0 0 0 0]
 [0 0 0 0]
 [0 0 0 0]
 [0 0 0 0]]
A finished array [[0 0 0 0]
 [0 1 1 0]
 [0 1 1 0]
 [0 0 0 0]]
None
```
再加上一张 4×4 的黑白图：正中间是一个 2×2 的黑方块。

**输出解读（重要）**：

1. 第一段输出确认 `np.zeros` 确实给了一片全 0 —— **注意打印出来是 `0` 而不是 `0.`，这证明 `dtype=int` 生效了**。
2. 第二段输出中，中间 2×2 变成了 1，外围一圈仍是 0 —— 与 Figure 1 的 Block 图案一致。
3. **那个孤零零的 `None` 是哪来的？** 这是 `print(print(...))` 造成的：
   - 内层 `print("A finished array",Block)` 先执行，把内容打到屏幕上；
   - 但 `print()` 函数**本身的返回值是 `None`**；
   - 外层 `print` 于是把这个 `None` 又打印了一遍。
   - 这**不是错误**，只是 notebook 里的一个笔误 / 意外的教学素材。**关键教训：`print` 是「输出到屏幕」，不是「返回值」。** 很多初学者会写 `x = print(3+4)` 然后发现 `x` 是 `None`。
4. **为什么 Block 是 still life？** 4 个活细胞每个都恰好有 3 个活邻居（规则 2 → 存活）；周围任何死细胞最多只有 2 个活邻居（不满足恰好 3 → 不出生）。所以它永远不变。

---

### 5.2 Exercise 1：画出 Tub 和 Boat（still life）

**题目要求**：创建 2D NumPy 数组，画出 Figure 2 中的 *Tub*（盆）和 *Boat*（船）两种静物。

**解题思路**：
- 两者都需要 **5×5** 的画布（图案本体 3×3，外围留一圈白边）。
- Tub 是一个「菱形/空心钻石」：上、左、右、下 4 个格子为 1，中心为 0。
- Boat = Tub **再补上左上角一格**（`[1,1]`）。
- 先在纸上画 5×5 网格，标出行列号，再逐个写赋值语句。

**完整代码 + 注释**：

```python
# NumPy 和 Matplotlib 上面已经导入，不用重复导入
# 初始化两个 5×5 的全 0 矩阵
Tub  = np.zeros((5,5),dtype=int)
Boat = np.zeros((5,5),dtype=int)

#-------'INSERT CODE HERE'-------
# Tub：菱形，中心 (2,2) 保持为 0（空心）
Tub [1,2]=1   # 上顶点
Tub [2,1]=1   # 左顶点
Tub [3,2]=1   # 下顶点
Tub [2,3]=1   # 右顶点
#--------------------------------

plt.subplot(1, 2, 1).imshow(Tub, cmap='binary')
# ↑ subplot(1,2,1)：把画布切成 1 行 2 列，选中第 1 格（编号从 1 开始！），
#   然后对返回的 axes 对象直接调用 .imshow()
plt.title('Tub')     # 标题作用于「当前」axes，也就是刚选中的第 1 格
#plt.show()          # 被注释掉了：如果这里 show()，第二张图会开一张新 figure，
                     # 两张图就不会并排显示了

#-------'INSERT CODE HERE'-------
# Boat = Tub 的形状 + 左上角补一格
Boat [1,1]=1   # 左上角（Tub 没有的那一格）
Boat [1,2]=1   # 上
Boat [2,1]=1   # 左
Boat [2,3]=1   # 右
Boat [3,2]=1   # 下
#--------------------------------

plt.subplot(1, 2, 2).imshow(Boat, cmap='binary')  # 选中第 2 格
plt.title('Boat')
plt.show()      # 一次性把两个子图都渲染出来
```

**输出**：一张并排两格的图。左边 'Tub' 是一个空心菱形（4 个黑格围着一个白心），右边 'Boat' 是菱形左上角补了一格，看起来像一条小船。

**输出解读 / 正确性检查**：
- 对照 Figure 2 逐格数黑白格。
- 概念检查：两者都必须是 **still life**。
  - Tub 的每个活细胞恰好有 2 个活邻居 → 规则 2 → 存活。中心死细胞有 4 个活邻居 → 不是恰好 3 → 不出生。✔
  - Boat 的 5 个活细胞邻居数分别是 2,3,3,2,2 → 都在 2–3 之间 → 全部存活。周围死细胞邻居数最多 5（中心）、其余最多 2 → 没有恰好 3 的 → 不出生。✔
- 如果你把它扔进模拟器发现它变形了，说明你的形状画错了或规则写错了。

**易踩坑**：
- `plt.subplot` 的编号从 **1** 开始，不是 0。
- 中间那句 `plt.show()` 必须保持注释状态，否则两图不并排。
- `Tub [1,2]` 中变量名和 `[` 之间的空格是**合法**的（Python 忽略），但**不推荐**这么写，规范写法是 `Tub[1,2]`。

---

### 5.3 Exercise 2：画出振荡子和飞船（Toad, Beacon, Glider, LWSS）

**题目要求**：照 Figure 1 和 Figure 3，画出两种 *oscillators*（Toad、Beacon）和两种 *space ships*（Glider、LWSS）。**注意检查每个数组需要多大 —— 要把外围的空白算进去**（"Check the size of each array you need, accounting for white space around the outside."）。

**解题思路**：
- 关键是**先定尺寸**再填格子。为什么要留白边？因为飞船要移动、振荡子要变形，如果贴着边缘，边界效应会让它行为不对。
- Beacon 和 Toad 用 6×6；Glider 用 5×5；LWSS 用 6×7（它是横向长条形）。
- 逐格对照图，把黑格的 (row, col) 一一写出来。

**完整代码 + 注释**：

```python
# 初始化 4 个矩阵，尺寸各不相同
Beacon = np.zeros((6,6),dtype=int)   # 振荡子，周期 2
Toad   = np.zeros((6,6),dtype=int)   # 振荡子，周期 2
Glider = np.zeros((5,5),dtype=int)   # 飞船，周期 4，斜向移动
LWSS   = np.zeros((6,7),dtype=int)   # Light-Weight SpaceShip，周期 4，横向移动
                                     # ↑ 注意是 6 行 7 列，不是正方形！

#-------'INSERT CODE HERE'-------
# --- Beacon（信标）---
# 这是 Beacon 的「相位 2」：两个 2×2 方块对角相接，但相接的两个内角格是空的
Beacon [1,1]=1
Beacon [1,2]=1
Beacon [2,1]=1
Beacon [3,4]=1
Beacon [4,3]=1
Beacon [4,4]=1
# 画出来是：左上角一个缺右下角的 L 形三格，右下角一个缺左上角的 L 形三格

# --- Toad（蟾蜍）---
# 两排各 3 格，上下错开 1 列
Toad [2,2]=1
Toad [2,3]=1
Toad [2,4]=1   # 第 2 行：col 2,3,4
Toad [3,1]=1
Toad [3,2]=1
Toad [3,3]=1   # 第 3 行：col 1,2,3（整体左移一格）

# --- Glider（滑翔机）---
# 经典形状：  . # .
#            . . #
#            # # #
Glider [1,2]=1          # 第 1 行中间
Glider [2,3]=1          # 第 2 行右侧
Glider [3,1]=1
Glider [3,2]=1
Glider [3,3]=1          # 第 3 行整排三格

# --- LWSS（轻量级飞船）---
# 经典形状（rows 1-4, cols 1-5）：
#   . # . . #
#   # . . . .
#   # . . . #
#   # # # # .
LWSS [1,2]=1
LWSS [1,5]=1            # 第 1 行：col 2 和 col 5
LWSS [2,1]=1            # 第 2 行：col 1
LWSS [3,1]=1
LWSS [3,5]=1            # 第 3 行：col 1 和 col 5
LWSS [4,1]=1
LWSS [4,2]=1
LWSS [4,3]=1
LWSS [4,4]=1            # 第 4 行：col 1-4 连成一条
#--------------------------------

# 可视化：两张 figure，每张两个子图
plt.subplot(1, 2, 1).imshow(Beacon, cmap='binary')
plt.title('Beacon')
plt.subplot(1, 2, 2).imshow(Toad, cmap='binary')
plt.title('Toad')
plt.show()      # 第一张 figure 结束

plt.subplot(1, 2, 1).imshow(Glider, cmap='binary')
plt.title('Glider')
plt.subplot(1, 2, 2).imshow(LWSS, cmap='binary')
plt.title('LWSS')
plt.show()      # 第二张 figure 结束
```

**输出**：两张图，共四个子图，分别显示 Beacon / Toad / Glider / LWSS 的形状。

**输出解读 / 正确性检查**：
- 对照 Figure 1（Beacon、Toad）和 Figure 3（Glider、LWSS）逐格核对。
- **行为验证（最可靠）**：把它们扔进 Exercise 4 的循环里跑：
  - Beacon 应该「眨眼」—— 两个方块的内角格反复出现/消失，**周期 2**。
  - Toad 应该在两种形状间来回，**周期 2**。
  - Glider 应该 **4 步后恢复原形状但整体斜移了 1 行 1 列**（本定义朝右下方走）。
  - LWSS 应该 **4 步后恢复原形状但整体横移了 2 列**（本定义朝右走）。
- 如果 Glider 跑着跑着散架了，很可能是形状画错（少一格或多一格）。

**易踩坑**：
- **LWSS 是 6×7 不是 6×6**。后面往宇宙里放它时切片必须写成 6 行 × 7 列（`[a:a+6, b:b+7]`），否则 broadcast 报错。
- 留白不够会导致形状在边界处被「切掉」，行为异常。

---

### 5.4 示范代码：搜索函数的骨架（还没实现规则的版本）

**题目要求**：读懂这个函数在做什么。老师说这是理解本周的核心。

**解题思路**：把函数拆成 8 步叙述（notebook 明确给出，务必背下来）：

1. 把 2D NumPy 数组连同「总行数、总列数」一起传给函数。
2. 用**前两层循环**遍历每个 cell（`row`, `col`），边界由 `total_rows` / `total_cols` 决定。
3. 每到一个新 cell，都要**把计数器 `count` 重置为 0**。
4. 用**后两层循环**看局部邻域：上 1 行、下 1 行、左 1 列、右 1 列。
5. 遍历邻域时，检查是否**越界**或**就是自己**。
6. 若都不是，则检查该格是否 > 0；是的话 `count` 加 1。
7. 对棋盘上每个 cell 重复第 3–6 步。
8. 整个空间搜完后，结束函数，**什么都不返回**。

**完整代码 + 逐行注释**：

```python
# 先建一个 Beacon 作为测试对象
Beacon = np.zeros((6,6),dtype=int)
Beacon [1,1]=1
Beacon [1,2]=1
Beacon [2,1]=1
Beacon [3,4]=1
Beacon [4,3]=1
Beacon [4,4]=1

# 定义函数：遍历 2D 数组中的每个 cell 并搜索其邻域
# 传入三个变量：
#   total_rows - 要搜索的空间的总行数
#   total_cols - 要搜索的空间的总列数
#   space      - 要搜索的 2D 数组本身
def search_each_cell(total_rows,total_cols,space):

    # 1) 用两层嵌套 for 循环走遍每个 cell
    for row in range(total_rows):          # 外层：0,1,2,...,total_rows-1
        for col in range(total_cols):      # 内层：0,1,2,...,total_cols-1
            # 现在 (row, col) 就是「当前 cell」的坐标

            count = 0
            # ↑ 关键：每换一个 cell 就把计数器归零。
            #   位置必须在这里（col 循环体内），放外面就会累加错。

            for row2 in range(row-1,row+2):     # 邻域行：row-1, row, row+1
                for col2 in range(col-1,col+2): # 邻域列：col-1, col, col+1
                    # ↑ 注意 +2 而不是 +1，因为 range 右端是开区间

                    # 检查新位置 [row2, col2] 是否越界
                    if (row2<0) or (row2>=total_rows) or (col<0) or (col2>=total_cols):
                        pass    # 越界 → 什么都不做（没有数据可数）
                        # ⚠ 这里有个 bug：第三个条件应该是 col2<0 而非 col<0，详见第六节

                    elif row2 == row and col2 == col:
                        pass    # 就是自己 → 什么都不做（自己不算自己的邻居）

                    else:
                        # 既没越界也不是自己 → 检查这一格是不是活的
                        if space[row2,col2]>0:
                            count=count+1   # 是活的，计数 +1

    return  # 目前什么都不返回。奇怪吗？我们待会儿会回来处理。

# 调用函数
search_each_cell(6,6,Beacon)

print("Finished function call, nothing to report!")
```

**输出**：
```
Finished function call, nothing to report!
```

**输出解读**：

- **除了这行字什么都没有** —— 因为函数只是「数」，数完就丢掉了，既没有 `print`，也没有 `return` 任何东西。
- `search_each_cell(6,6,Beacon)` 这个表达式的值实际上是 **`None`**（`return` 后面不跟东西 = 返回 `None`）。
- 这一格的教学目的就是让你**感受到「函数必须 return 才有用」**。老师转写："What's missing here is the implementation then of the four rules. Because at the moment there's no return. It just returns nothing."
- **正确性判断**：这一格没有可判断的结果，只要不报错（没有 `IndexError`、没有缩进错误）就算通过。

---

### 5.5 Exercise 3（★本周核心）：实现四条生命规则

**题目要求**：在上面的搜索函数中补上一组条件语句，根据 `count` 和当前 cell 的值，把结果写进 `new_space`，并把 `new_space` 返回。跑完后应该看到 Figure 4：Beacon 的 before / after 对比。

**notebook 给出的规则→伪代码转换（必背）**：

```
- If our current cell is alive [=1]:
   a) If count < 2,        current cell = 0   [it dies]
   b) If 2 <= count <= 3,  current cell = 1   [it stays alive]
   c) If count > 3,        current cell = 0   [it dies]

- If our current cell is dead [=0]:
   a) If count == 3,       current cell = 1   [born]
```

notebook 特别提醒：
> "Notice the syntax I have used for the last conditional: `If count == 3`? When checking a value we use two equals signs `==` as we are not *assigning* a value as we would in, e.g. `x = 4`."
> **比较用 `==`，赋值用 `=`。**

以及：
> "Please note that where I have added 'INSERT CODE HERE' we are using the correct indentation."
> INSERT CODE HERE 的位置**缩进已经给你摆对了**，照着那个层级写。

**解题思路**：
1. 在函数最开头新建一块 `new_space`（全 0），保证「读旧写新」的同步更新。
2. 补上的条件语句要放在**内层两个循环之外、外层 `col` 循环之内**（即数完邻居之后、换下一个 cell 之前）。缩进层级 = 和 `count = 0` 一样。
3. 外层判断：当前 cell 活（`> 0`）还是死（`== 0`）。
4. 内层判断：按 `count` 分支。
5. 把 `return` 改成 `return new_space`。

**完整代码 + 注释（只标出与 5.4 不同的部分）**：

```python
# 初始化 Beacon 矩阵
Beacon = np.zeros((6,6),dtype=int)
Beacon [1,1]=1
Beacon [1,2]=1
Beacon [2,1]=1
Beacon [3,4]=1
Beacon [4,3]=1
Beacon [4,4]=1

def search_each_cell(total_rows,total_cols,space):

    new_space = np.zeros((total_rows,total_cols),dtype=int)
    # ★ 新增：建一块和输入同尺寸的全 0 数组作为「下一代」。
    #   所有读取用 space（旧），所有写入用 new_space（新）→ 保证同步更新。
    #   默认值是 0，所以「死掉」和「保持死亡」的情况可以什么都不写。

    for row in range(total_rows):
        for col in range(total_cols):
            count = 0
            for row2 in range(row-1,row+2):
                for col2 in range(col-1,col+2):
                    if (row2<0) or (row2>=total_rows) or (col<0) or (col2>=total_cols):
                        pass
                    elif row2 == row and col2 == col:
                        pass
                    else:
                        if space[row2,col2]>0:
                            count=count+1

            #-------'INSERT CODE HERE'-------  ← ★ 本练习要补的部分
            if space[row,col] > 0:              # 情况一：当前 cell 是活的
                if count < 2:
                    new_space[row,col] = 0;     # 规则 1：邻居 <2 → 死于人口过疏
                elif 2<=count<=3:
                    new_space[row,col] = 1;     # 规则 2：邻居 2 或 3 → 存活
                elif count > 3:
                    new_space[row,col] = 0;     # 规则 3：邻居 >3 → 死于人口过密
            elif space[row,col] == 0:           # 情况二：当前 cell 是死的
                if count == 3:
                    new_space[row,col] = 1;     # 规则 4：恰好 3 个活邻居 → 诞生
                                                # （其余情况保持 0，因为 new_space 初始就是 0）
            #--------------------------------

    return new_space    # ★ 把整张「下一代」棋盘返回出去

# 调用函数：把旧的 Beacon 传进去，接住返回的新棋盘
Beacon_new = search_each_cell(6,6,Beacon)

print("Finished function call, now lets compare our pattern before and after...")

# 并排画出 before / after
plt.subplot(1, 2, 1).imshow(Beacon, cmap='binary')
plt.title('Beacon - before')
plt.subplot(1, 2, 2).imshow(Beacon_new, cmap='binary')
plt.title('Beacon - after')
plt.show()
```

**输出**：
```
Finished function call, now lets compare our pattern before and after...
```
外加一张并排双图（Figure 4）。

**输出解读（关键 —— 手算验证）**：

初始 Beacon（相位 B）：
```
      col: 0 1 2 3 4 5
row 0:      0 0 0 0 0 0
row 1:      0 1 1 0 0 0
row 2:      0 1 0 0 0 0
row 3:      0 0 0 0 1 0
row 4:      0 0 0 1 1 0
row 5:      0 0 0 0 0 0
```

逐格手算：
- `[1,1]` 活，活邻居 = `[1,2]`,`[2,1]` = **2** → 规则 2 → **保持活**。
- `[1,2]` 活，活邻居 = `[1,1]`,`[2,1]` = **2** → 规则 2 → **保持活**。
- `[2,1]` 活，活邻居 = `[1,1]`,`[1,2]` = **2** → 规则 2 → **保持活**。
- `[2,2]` **死**，邻域（rows 1–3, cols 1–3）活的有 `[1,1]`,`[1,2]`,`[2,1]` = **恰好 3** → 规则 4 → **诞生！**
- `[3,3]` **死**，邻域（rows 2–4, cols 2–4）活的有 `[3,4]`,`[4,3]`,`[4,4]` = **恰好 3** → 规则 4 → **诞生！**
- `[3,4]`,`[4,3]`,`[4,4]` 各有 2 个活邻居 → 保持活。
- 其余所有死格活邻居数都 ≤ 2 → 不诞生。

结果（相位 A）：
```
      col: 0 1 2 3 4 5
row 0:      0 0 0 0 0 0
row 1:      0 1 1 0 0 0
row 2:      0 1 1 0 0 0
row 3:      0 0 0 1 1 0
row 4:      0 0 0 1 1 0
row 5:      0 0 0 0 0 0
```
即**两个 2×2 方块对角相接**。

**判断结果是否正确**：after 图应该比 before 图**多出两个黑格**（正好是两个方块的相接内角 `[2,2]` 和 `[3,3]`）。如果 after 和 before 一模一样，说明你的条件语句根本没生效（可能缩进放错层级了）；如果 after 是一片空白，说明规则写反了或者 `return` 忘了改。

**反向验证（可自己算）**：如果再跑一次，相位 A 会退回相位 B —— 因为此时 `[2,2]` 的活邻居变成 4 个（`[1,1]`,`[1,2]`,`[2,1]`,`[3,3]`），`4 > 3` → 规则 3 → 死。`[3,3]` 同理。**所以周期是 2。**

**语法细节**：
- 行尾的分号 `;`（如 `new_space[row,col] = 0;`）在 Python 里**合法但完全没必要** —— 这是从 C/MATLAB 带来的习惯。不要学，写成 `new_space[row,col] = 0` 即可。
- `elif space[row,col] == 0:` 其实可以直接写 `else:`（因为只有 0/1 两种值），但显式写出来更清楚。
- 「死细胞且 count != 3」的情况**不用写任何代码** —— `new_space` 初始就是 0，天然是「保持死亡」。这是巧妙利用默认值省代码的常见技巧。

---

### 5.6 Exercise 4：循环 20 次，看 Beacon 振荡

**题目要求**：把上面写好的条件语句放进这一格的对应位置，运行，观察 Beacon 是否在振荡。绘图代码已给出，但要看懂语法。

**解题思路**：函数本体完全不变，新增的是**外层的时间循环**：每一步调用一次函数、更新棋盘、清屏、重画、稍作停顿 —— 就形成了「伪动画」。

**完整代码（函数体同 5.5，此处只详解新增部分）**：

```python
import numpy as np
import matplotlib.pyplot as plt
from matplotlib import animation, rc
from IPython.display import HTML          # HTML 显示工具（本例其实没直接用）
from IPython.display import clear_output  # ★ 清空当前 cell 输出 —— 做动画的关键
import time                               # ★ 提供 sleep()，控制动画速度

# 初始化 Beacon（同前）
Beacon = np.zeros((6,6),dtype=int)
Beacon [1,1]=1
Beacon [1,2]=1
Beacon [2,1]=1
Beacon [3,4]=1
Beacon [4,3]=1
Beacon [4,4]=1

def search_each_cell(total_rows,total_cols,space):
    new_space = np.zeros((total_rows,total_cols),dtype=int)
    for row in range(total_rows):
        for col in range(total_cols):
            count = 0
            for row2 in range(row-1,row+2):
                for col2 in range(col-1,col+2):
                    if (row2<0) or (row2>=total_rows) or (col<0) or (col2>=total_cols):
                        pass
                    elif row2 == row and col2 == col:
                        pass
                    else:
                        if space[row2,col2]>0:
                            count=count+1
            #-------'INSERT CODE HERE'-------
            if space[row,col] > 0:
                if count < 2:
                    new_space[row,col] = 0;
                elif 2<=count<=3:
                    new_space[row,col] = 1;
                elif count > 3:
                    new_space[row,col] = 0;
            elif space[row,col] == 0:
                if count == 3:
                    new_space[row,col] = 1;
            #--------------------------------
    return new_space

# 先画一次初始状态
fig, ax2 = plt.subplots()
# ↑ plt.subplots() 返回两个东西：figure 对象和 axes 对象，必须用两个变量接
#   （这里 ax2 后面其实没用到，但语法上必须接住）
plt.imshow(Beacon, cmap='binary')
plt.title('Beacon oscillating')
plt.show()

# ★ 时间循环：调用函数 20 次
# 每次都得到一个新形状并画在图上；每步之间等 0.2 秒；应该能看到振荡行为
for x in range(20):                                  # 跑 20 个时间步
    clear_output(wait=True)                          # 清掉上一帧的输出
                                                     # wait=True：等新输出就绪再清，减少闪烁
    Beacon_new = search_each_cell(6,6,Beacon)        # 旧棋盘 → 新棋盘
    Beacon = Beacon_new                              # ★ 新棋盘变成下一轮的「旧」棋盘
                                                     #   没有这一行，就会永远在同一个状态里打转
    plt.imshow(Beacon_new, cmap='binary')            # 画新一帧
    plt.title('Beacon oscillating')
    plt.show()
    time.sleep(0.2)                                  # 停 0.2 秒，让眼睛看得清
```

**输出**：单元格输出区域会不断刷新，显示 Beacon 在**两种形状之间来回切换**，共 20 帧，全程约 4 秒（20 × 0.2 s，加上计算时间）。最终停在第 20 帧。

**输出解读 / 正确性检查**：
- **必须看到「眨眼」效果**：两个 2×2 方块的相接内角格反复出现、消失。
- 20 是偶数，且周期是 2，所以**最后一帧应该和初始状态一样**（回到相位 B）。这是一个很好的自检：改成 `range(21)` 最后一帧就应该是相位 A。
- 若图案「死光了」→ 检查规则 4 是不是写成了 `>= 3`，或者规则 2 的区间写错。
- 若图案完全不动 → 检查有没有忘了写 `Beacon = Beacon_new`。
- 若图案一帧帧叠加、越画越多 → 说明 `clear_output` 没生效（可能没 import，或者不在 Jupyter 环境里）。

**关键语法点**：
- **循环变量 `x` 从头到尾没被用到** —— 它只是用来「数 20 次」。Python 里这种情况按惯例可以写 `for _ in range(20):`。
- `clear_output` + `plt.show()` + `time.sleep()` 是 Jupyter 里做简易动画的**标准三件套**。真正的动画要用 `matplotlib.animation`（notebook 顶部 import 了但没用）。
- `time.sleep(0.2)` 参数单位是**秒**，改小加快、改大放慢。

---

### 5.7 第三部分：创建 50×50 的宇宙

**题目要求**：创建一个足够大的空间来容纳所有物种。

```python
Universe=np.zeros((50,50),dtype=int)   # 50 行 × 50 列的全 0 宇宙
print(Universe)
```

**输出**：
```
[[0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 ...
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 0]]
```

**输出解读**：
- 出现了 `...` —— 这是 **NumPy 对大数组的自动省略显示**。默认超过 1000 个元素（这里是 2500 个）就只显示头尾几行/列。**这不是错误**，只是打印摘要。
- 想看全部可以用 `np.set_printoptions(threshold=np.inf)`，但 50×50 打出来会刷屏，通常没必要 —— 用 `imshow` 看图更实际。
- 确认是 `0` 而不是 `0.` → `dtype=int` 生效。

（讲义里老师用的是 10×23 的宇宙做示范，notebook 用 50×50 —— 尺寸随意，只要装得下你要放的形状。）

---

### 5.8 把 LWSS 放进宇宙（切片赋值示范）

**题目要求**：把一个 LWSS 的左上角放在宇宙的第 12 行、第 13 列，并可视化。

**notebook 原文的关键解释**：
> "Dont forget, indexing in Python starts at 0 so for the 12th row and 13th column, I need to refer to element [11,12]. Im also using the operator `:` which allows us to straddle cells bound by a start and a finish. Why have I chosen the range given below? Feel free to change the values, but if you get the size of space needed to fit in an LWSS [wrong], Python will complain it cannot broadcast a given shape."

```python
# 指定宇宙中你希望 LWSS 出现的位置
Universe[11:17,12:19] = LWSS
# ↑ 行方向：11,12,13,14,15,16 → 共 6 行（17-11=6）
#   列方向：12,13,...,18      → 共 7 列（19-12=7）
#   而 LWSS 的形状正好是 (6,7) → 完全匹配，赋值成功
#   若写成 Universe[11:16,12:19] = LWSS（只有 5 行），会报 broadcast 错误

plt.imshow(Universe, cmap='binary')
plt.title('Universe [with 1 LWSS]')
plt.show()
```

**输出**：一张 50×50 的大白板，左上偏中的位置有一小簇黑点（LWSS）。

**输出解读**：
- 图很大而 LWSS 很小，所以看起来只是一个小黑斑 —— **这是正常的**。
- 验证方法：黑斑应该出现在图的大约 1/4 高、1/4 宽处（行 11–16 / 50，列 12–18 / 50）。

**核心公式（务必记住）**：
> 切片 `[a:b]` 的长度 = `b - a`。
> 要放一个 `h` 行 `w` 列的形状，起点 `(r, c)`，就写 `Universe[r:r+h, c:c+w] = shape`。

---

### 5.9 最终模拟：多物种共存的宇宙

**题目要求**：把上面写好的 `search_each_cell` 函数复制到 `INSERT CODE HERE` 处，运行 100 次迭代的模拟。notebook 还提问："What happens if you increase the number of iterations to 300?"

**notebook 提示**：如果想清空之前放进去的东西，可以写 `Universe[:,:]=0`，但这里保留（所以之前放的那个 LWSS 还在）。

**完整代码 + 注释**：

```python
# 在宇宙中安放各个物种（注意每个切片的尺寸必须和对应形状严格一致）
Universe[30:36,32:39] = LWSS    # 6 行 × 7 列 ← LWSS 是 (6,7) ✔
Universe[11:17,12:19] = LWSS    # 6 行 × 7 列 ✔（和 5.8 是同一个位置，重复赋值）
Universe[22:28,12:18] = Beacon  # 6 行 × 6 列 ← Beacon 是 (6,6) ✔
Universe[33:39,2:8]   = Beacon  # 6 行 × 6 列 ✔
Universe[19:25,32:38] = Toad    # 6 行 × 6 列 ← Toad 是 (6,6) ✔
Universe[1:6,1:6]     = Glider  # 5 行 × 5 列 ← Glider 是 (5,5) ✔
Universe[6:11,25:30]  = Boat    # 5 行 × 5 列 ← Boat 是 (5,5) ✔

plt.imshow(Universe, cmap='binary')
plt.title('Universe [with multiple cell types]')
plt.show()

#-------'INSERT CODE HERE'-------
# 把 Exercise 3 里写好的完整函数原封不动复制过来
def search_each_cell(total_rows,total_cols,space):
    new_space = np.zeros((total_rows,total_cols),dtype=int)
    for row in range(total_rows):
        for col in range(total_cols):
            count = 0
            for row2 in range(row-1,row+2):
                for col2 in range(col-1,col+2):
                    if (row2<0) or (row2>=total_rows) or (col<0) or (col2>=total_cols):
                        pass
                    elif row2 == row and col2 == col:
                        pass
                    else:
                        if space[row2,col2]>0:
                            count=count+1
            if space[row,col] > 0:
                if count < 2:
                    new_space[row,col] = 0;
                elif 2<=count<=3:
                    new_space[row,col] = 1;
                elif count > 3:
                    new_space[row,col] = 0;
            elif space[row,col] == 0:
                if count == 3:
                    new_space[row,col] = 1;
    return new_space
#--------------------------------

fig, ax2 = plt.subplots(figsize=(12, 12))
# ↑ figsize=(12,12)：把图放大到 12×12 英寸，
#   因为 50×50 的宇宙用默认小图看不清单个 cell

plt.imshow(Universe, cmap='binary')
plt.title('Universe simulation')
plt.show()

# 跑 100 个时间步的模拟
for x in range(100):
    clear_output(wait=True)                        # 清屏
    Universe_new = search_each_cell(50,50,Universe) # 计算下一代（注意传 50,50）
    Universe = Universe_new                         # 更新
    plt.imshow(Universe_new, cmap='binary')
    plt.title('Universe simulation')
    plt.show()
    time.sleep(0.2)
```

**输出**：一张 50×50 的动画，100 帧。

**输出解读（科学上该看什么）**：

1. **初始帧**：能辨认出 7 个分散的小图案（2 个 LWSS、2 个 Beacon、1 个 Toad、1 个 Glider、1 个 Boat）。
2. **早期（前 10–20 步）**：
   - Boat 完全不动（still life）。
   - 两个 Beacon 和 Toad 原地眨眼（oscillators）。
   - Glider 沿对角线往右下方爬（每 4 步移动 1 行 1 列）。
   - 两个 LWSS 沿水平方向往右冲（每 4 步移动 2 列，比 Glider 快得多）。
3. **中后期**：飞船撞上其他图案或撞上边界 →
   - 相撞可能互相湮灭、可能产生新的碎片、可能生成新的静物或振荡子。老师转写："you'll see things moving across the screen killing each other creating each other whatever."
   - 撞到宇宙边界会被「切掉」变形甚至解体 —— 这是**有限边界的人为效应（boundary artefact）**，不是 bug，但做科学模拟时要意识到边界条件会影响结果。
4. **长期（300 步）**：系统通常会衰减到一个由静物 + 少数振荡子构成的**稳定态（stable state）**，或者剩下几个还在飞的飞船。这正是 notebook 提问的意图 —— **观察系统是否收敛。**

**运行体验上的注意**：
- 50×50 × 100 步 = 每步 22,500 个 cell × 9 次邻域查询 ≈ 2000 万次 Python 循环迭代。**会明显卡**。这正是老师说的 Python 慢的地方。
- 如果嫌慢，可以把 `time.sleep(0.2)` 改小或删掉，把宇宙改小，或减少迭代次数。

**如何验证正确性**：
- **Boat 必须纹丝不动**。如果 Boat 也在变，规则一定写错了。
- **Beacon 必须周期 2**。
- **Glider 必须保持形状且匀速斜移**。如果 Glider 走两步就散了，说明邻域计数有 bug。

---

### 5.10 notebook 末尾的总结（"What We Did"）

> 本次 practical 我们：
> - 把 **Conway's Game of Life** 作为「简单规则驱动的模拟」的范例引入
> - 用 **2D array** 表示游戏棋盘
> - 用数值表示细胞是 **alive** 还是 **dead**
> - 应用**规则**，根据邻居决定每个细胞如何从一步演化到下一步
> - 用**循环 + 数组索引**统计邻居
> - 用**条件语句**决定细胞生、死、还是诞生
> - 反复更新网格，模拟系统**随时间的演化**
> - 每一步可视化网格，观察涌现出的模式
>
> 🧠 重点在于展示**复杂行为如何从简单规则中涌现**，以及 arrays、loops、conditionals 如何协同工作构成一个模拟。

---

## 六、易错点 / 重点难点

### 6.1 ★ notebook 代码里真实存在的一个 bug：`col<0` 应为 `col2<0`

```python
if (row2<0) or (row2>=total_rows) or (col<0) or (col2>=total_cols):
#                                     ^^^^^  ← 应该是 col2<0
```

**问题分析**：
- 四个边界条件本应是：`row2<0`、`row2>=total_rows`、`col2<0`、`col2>=total_cols`。
- 第三个写成了 `col<0`。而 `col` 来自 `range(total_cols)`，**永远 ≥ 0**，所以这个条件**永远为 False**，形同虚设。
- 后果：当 `col == 0` 时，`col2` 会取到 **-1**，这时既没被越界检查拦住，也不等于 `col`，于是进入 `else` 分支执行 `space[row2, -1]`。
- **NumPy 中负索引表示从末尾倒数**，所以 `space[row2, -1]` 读的是**最后一列**！
- 等于：**宇宙的左边界偷偷和右边界连起来了**（部分环绕 / 柱面拓扑），而上下边界和右边界仍然是硬边界。这是一个不对称的、非预期的行为。

**为什么本 notebook 的结果看起来仍然正确？**
因为所有例子的**最后一列都恰好是全 0**：
- Beacon (6×6)：col 5 全是 0。
- Universe (50×50)：所有物种都放在 col 1–38 之间，col 49 全是 0。
所以 `space[row2, -1]` 读到的永远是 0，`count` 不会被错误增加，结果与正确实现一致。**这是一个「潜伏的 bug」—— 换个初始条件（比如在最右列放东西）就会暴露。**

**修法**：
```python
if (row2<0) or (row2>=total_rows) or (col2<0) or (col2>=total_cols):
```

**这是本周最好的调试教学素材**：讲义 goals 明确写着 "Start to think about how you check for correct behaviour in working code."（开始思考如何检验能跑的代码行为是否正确。）—— **代码能跑 ≠ 代码正确**。

### 6.2 `range(a, b)` 的右开区间陷阱

```python
for row2 in range(row-1, row+2):   # ✔ 产生 row-1, row, row+1
for row2 in range(row-1, row+1):   # ✘ 只产生 row-1, row —— 漏掉了下面一行！
```

**症状**：邻居数系统性偏少 → 所有东西都会「饿死」，几步之后棋盘全白。

**记忆法**：要包含 `x`，上界必须写 `x+1`。要包含 `row+1`，就写 `row+2`。

### 6.3 `count = 0` 放错位置

```python
# ✔ 正确：在最内两层循环之前、col 循环体内
for row in range(...):
    for col in range(...):
        count = 0
        for row2 in ...:
            for col2 in ...:
                ...

# ✘ 错误：放在函数最开头
count = 0
for row in range(...):
    for col in range(...):
        for row2 in ...:
```
**症状**：`count` 一路累加，很快就 > 3，导致所有活细胞全部「过密而死」→ 棋盘迅速全白。

### 6.4 `=` 与 `==` 混淆

```python
if count = 3:    # ✘ SyntaxError: invalid syntax
if count == 3:   # ✔
```
Python 会直接报 `SyntaxError`（不像 C 会默默通过），所以这个错误容易发现。但反过来，**该赋值时写了 `==`**（如 `new_space[row,col] == 1`）就不会报错，只是**什么都没做**，非常隐蔽 —— 症状是图案完全不变。

### 6.5 死细胞规则写成 `count >= 3`

```python
elif space[row,col] == 0:
    if count == 3:      # ✔ 恰好 3 个
    # if count >= 3:    # ✘ 会让宇宙疯狂爆炸增殖
```
**症状**：黑色迅速蔓延，整个宇宙变成一大片黑。

### 6.6 忘记 `new_space`，直接改 `space`（就地修改）

```python
# ✘ 错误做法
space[row,col] = 1   # 直接改输入数组
```
**症状**：图案行为完全不对。Beacon 不会规则地振荡，Glider 会变形解体。**原因**：违反了「同步更新」原则 —— 后面的 cell 数邻居时读到了已被更新的值。

**额外坑**：NumPy 数组作为参数传入函数是**传引用**，函数里改 `space` 会**改到函数外面的原数组**！这与传入 int/str 时的行为不同，是 Python 初学者的经典大坑。

### 6.7 忘记 `return new_space` / 忘记接住返回值

```python
def search_each_cell(...):
    ...
    return            # ✘ 返回 None

Beacon_new = search_each_cell(6,6,Beacon)
print(Beacon_new)     # → None
plt.imshow(Beacon_new, cmap='binary')
# → TypeError: Image data of dtype object cannot be converted to float
#   （或 TypeError: Invalid shape () for image data）
```
**修法**：`return new_space`。

### 6.8 忘记 `Beacon = Beacon_new`（循环里没更新状态）

```python
for x in range(20):
    Beacon_new = search_each_cell(6,6,Beacon)
    # 少了 Beacon = Beacon_new
    plt.imshow(Beacon_new, ...)
```
**症状**：20 帧画出来一模一样 —— 因为每次都从同一个初始状态算第一步。

### 6.9 切片形状不匹配 → broadcast 错误

```python
Universe[11:16,12:19] = LWSS   # 左边 5×7，右边 6×7
```
**报错**：
```
ValueError: could not broadcast input array from shape (6,7) into shape (5,7)
```
**如何读这个报错**：`from shape (6,7)` 是你要塞进去的东西的形状，`into shape (5,7)` 是目标空间的形状。两者不一致就报这个错。

**修法**：数清楚 `b-a` 是否等于形状的对应维度。notebook 原话："if you get the size of space needed to fit in an LWSS [wrong], Python will complain it cannot broadcast a given shape."

**特别注意**：LWSS 是 **(6,7)**，不是正方形，最容易在这里翻车。

### 6.10 `np.zeros` 忘了双层括号

```python
Block = np.zeros(4,4,dtype=int)     # ✘ TypeError（第二个 4 被当成 dtype 参数）
Block = np.zeros((4,4),dtype=int)   # ✔ 形状必须是一个 tuple
```

### 6.11 忘了 `dtype=int`

```python
Block = np.zeros((4,4))    # 默认 float64
print(Block)
# [[0. 0. 0. 0.]  ← 注意小数点
```
虽然逻辑上仍能跑（`0. > 0` 是 False，`1.` 也能被 `imshow` 正常显示），但打印出来难看，且整数运算更快、语义更准确。**养成写 `dtype=int` 的习惯。**

### 6.12 缩进错误（Python 的头号杀手）

生命游戏的函数有 **5 层缩进**（def → for row → for col → for row2 → for col2）。
- 四条规则的条件语句必须缩进到 **`for col` 的循环体内、`for row2` 的循环体外**（和 `count = 0` 同层）。
  - 放到 `for col2` 里面 → 每检查一个邻居就套一次规则，逻辑完全错乱。
  - 放到 `for row` 层 → 每行只更新一个 cell（用最后一次的 col 值）。
- `return new_space` 必须缩进到 **`def` 的函数体内、`for row` 的循环体外**。
  - 放到 `for row` 里面 → 第一行处理完就返回，只更新了第一行。
- notebook 特别提示 INSERT CODE HERE 处的缩进已经摆好了，照抄那个层级。

**常见报错**：
- `IndentationError: expected an indented block` — 冒号后面没有缩进的代码。
- `IndentationError: unindent does not match any outer indentation level` — 混用了 Tab 和空格。**永远只用空格（4 个）。**

### 6.13 `pass` 不能省略

```python
if (row2<0) or ...:
    # Do nothing        ← ✘ 只有注释，没有语句
elif ...:
```
**报错**：`IndentationError: expected an indented block`
**原因**：注释不算语句。Python 的代码块不能为空，必须放一个 `pass` 占位。

### 6.14 `plt.subplot` 编号从 1 开始

```python
plt.subplot(1,2,0)   # ✘ ValueError: num must be an integer with 1 <= num <= 2
plt.subplot(1,2,1)   # ✔
```
这是 matplotlib 里少数**不从 0 开始**的编号，和 Python 其它地方相反，特别容易搞错。

### 6.15 `plt.show()` 位置不对导致子图不并排

在两个 `subplot` 之间调用 `plt.show()` 会立刻结束当前 figure，后面的图会开新 figure。notebook 里 Exercise 1 中间那句 `#plt.show()` **被故意注释掉**就是这个原因。

### 6.16 `print()` 返回 `None`

见 5.1 —— `print(print(x))` 会多打一个 `None`。记住：**`print` 的作用是「显示」，不是「产生值」。**

### 6.17 边界效应（不是 bug，但要理解）

本实现的宇宙是**有限的、边界处不环绕**。飞船飞到边缘会被截断变形。若想让飞船无限飞行，需要：
- 把宇宙做得足够大，或
- 实现 wrap-around（环面拓扑），用取模运算 `row2 % total_rows`。

（本课不要求，但写 assessment 报告时可以作为「模型局限性」讨论。）

### 6.18 性能：为什么慢，以及能怎么办（延伸）

四层嵌套循环的复杂度是 **O(9 × N × M)** 每步，纯 Python 循环开销巨大。
- 50×50、100 步 ≈ 2000 万次迭代 → 明显卡顿。
- 老师说过大家会用别的语言重写来提速。
- **进阶做法（本课不要求，但值得知道）**：用 NumPy 的数组切片错位相加来一次性算出所有邻居数（向量化），或者用 `scipy.signal.convolve2d` 做卷积，速度能快上百倍。

### 6.19 行尾分号 `;`

`new_space[row,col] = 0;` 中的分号在 Python 中**合法但多余**（分号用来在一行里分隔多条语句）。这是从 C/MATLAB 带来的习惯，PEP 8 明确不推荐。**不要模仿**。

---

## 七、本周术语表

| 英文 | 中文 | 一句话解释 |
|---|---|---|
| Conway's Game of Life | 康威生命游戏 | 由 John Conway 发明的细胞自动机，用 4 条极简规则在二维网格上产生复杂涌现行为 |
| Cellular automaton | 细胞自动机 | 由离散网格 + 局部规则驱动的动力系统，每个格子的下一状态只取决于自己和邻居 |
| Universe | 宇宙 / 棋盘 | 生命游戏中承载所有细胞的二维空间；在代码里就是一个 2D NumPy array |
| Cell | 细胞 / 格子 | 二维数组中的一个元素，取值 1（alive）或 0（dead） |
| Alive / Dead | 活 / 死 | 细胞的两种状态；`1` 画成黑色，`0` 画成白色 |
| Neighbour | 邻居 | 水平、垂直、对角相邻的 8 个格子（Moore neighbourhood），不含自己 |
| Moore neighbourhood | 摩尔邻域 | 以某格为中心的 3×3 区域去掉中心，共 8 格 |
| Generation / Time step | 世代 / 时间步 | 把整个宇宙按规则更新一次称为一代 |
| Underpopulation | 人口过疏 | 规则 1：活细胞活邻居 < 2 → 死 |
| Overpopulation | 人口过密 | 规则 3：活细胞活邻居 > 3 → 死 |
| Reproduction | 繁殖 | 规则 4：死细胞活邻居恰好 = 3 → 复活 |
| Still life | 静物 | 永不改变的图案，如 Block、Tub、Boat、Beehive、Loaf |
| Oscillator | 振荡子 | 每步变形但若干代后回到原形的图案，如 Beacon（周期 2）、Toad（周期 2）、Pulsar |
| Period | 周期 | 振荡子回到初始形状所需的代数 |
| Space-ship | 飞船 | 一边变形一边在棋盘上移动的图案，如 Glider、LWSS |
| Glider | 滑翔机 | 最小的飞船，5 个活细胞，周期 4，每周期斜向移动 1 格 |
| LWSS (Light-Weight SpaceShip) | 轻量级飞船 | 常见飞船，周期 4，每周期横向移动 2 格；本课定义为 6×7 数组 |
| Gosper glider gun | 高斯帕滑翔机枪 | 能持续「发射」滑翔机的结构；本周 assessment 的可选题目 |
| Block / Tub / Boat / Beacon / Toad | 方块 / 盆 / 船 / 信标 / 蟾蜍 | 生命游戏社区约定俗成的图案名字 |
| Emergence | 涌现 | 简单局部规则产生复杂全局行为的现象 |
| Agent-based model (ABM) | 基于主体的模型 | 由许多有规则的个体互动构成的模拟方法；二年级 Environmental Modelling 会学 |
| Synchronous update | 同步更新 | 所有细胞依据「同一代」的状态同时更新；代码上表现为「读旧数组、写新数组」 |
| In-place modification | 就地修改 | 直接改原数组；在本问题中会导致错误结果 |
| Initial condition | 初始条件 | 模拟开始时宇宙中 1 和 0 的分布；决定后续全部演化 |
| Stable state | 稳定态 | 系统演化到不再变化（或只剩周期性振荡）的状态 |
| Boundary effect / artefact | 边界效应 / 边界伪影 | 有限棋盘的边缘导致的非物理行为 |
| Wrap-around / Toroidal | 环绕 / 环面 | 把上下、左右边界接起来的拓扑；本课**未**采用 |
| 2D array / Matrix | 二维数组 / 矩阵 | 有行有列的数值容器；NumPy 中用 `[row, col]` 索引 |
| NumPy | — | Python 的数值计算标准库，提供高效的数组类型 |
| `np.zeros` | 全零数组函数 | 按给定 shape 和 dtype 创建全 0 数组 |
| dtype | 数据类型 | 数组元素的类型，如 `int`（整数）、`float`（浮点数） |
| Index | 索引 / 下标 | 数组中元素的位置编号，**Python 从 0 开始** |
| Slicing | 切片 | 用 `a:b` 一次取/赋一段连续的行或列，**左闭右开** |
| Broadcasting | 广播 | NumPy 在形状不同的数组间做运算的规则；形状不兼容时报 `could not broadcast` |
| Nested for loop | 嵌套 for 循环 | 循环里面套循环；本周用到四层 |
| `range(a,b)` | 范围函数 | 生成 a 到 b-1 的整数序列（右端开区间） |
| Conditional statement | 条件语句 | `if` / `elif` / `else` 构成的分支结构 |
| Chained comparison | 链式比较 | Python 特有写法 `2 <= count <= 3` |
| `pass` | 空语句 | 语法上需要语句体但不想做任何事时的占位符 |
| Counter | 计数器 | 用于累加的整数变量，本周是 `count` |
| Function | 函数 | 用 `def` 定义的可重复调用的代码块 |
| Parameter / Argument | 形参 / 实参 | 函数定义时的变量名 / 调用时实际传入的值 |
| Return value | 返回值 | 函数用 `return` 送回给调用者的结果；无 `return` 则返回 `None` |
| `None` | 空值 | Python 表示「没有值」的特殊对象；`print()` 的返回值就是它 |
| Indentation | 缩进 | Python 用缩进（4 空格）表示代码块归属，不是可选的排版 |
| Matplotlib / pyplot | — | Python 标准绘图库 / 其类 MATLAB 接口子模块 |
| `imshow` | 图像显示函数 | 把 2D 数组当作图像渲染出来（俯视视角） |
| `cmap` (colour map) | 颜色映射 | 数值到颜色的对应规则；`'binary'` 为 0 白 1 黑 |
| `subplot` | 子图 | 把一张画布分成网格并选中其中一格；**编号从 1 开始** |
| `figsize` | 图尺寸 | 以英寸为单位的 figure 宽高 |
| `clear_output` | 清空输出 | IPython 函数，清掉单元格已有输出，用于制作逐帧动画 |
| `time.sleep(s)` | 暂停 | 让程序暂停 s 秒 |
| Magic command | 魔法命令 | IPython/Jupyter 中以 `%` 开头的特殊命令，如 `%cd`、`%matplotlib inline` |
| Google Colab | — | Google 提供的云端 Jupyter 环境；notebook 首格用于检测并适配它 |
| Vectorisation | 向量化 | 用数组整体运算代替显式循环，NumPy 提速的核心手段 |
