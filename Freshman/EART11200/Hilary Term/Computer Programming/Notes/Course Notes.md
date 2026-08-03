# Computer Programming (Hilary Term) — 课程总纲

> EART11200 *The Natural Scientist's Toolkit* 春季学期 Computer Programming 部分，共 9 周（Week 1–9 讲座 + 实践，Week 10–12 只有实践课，用于完成 notebook 评估作业）。
> 讲师：Dave Topping（Earth and Environmental Sciences，方向：数值模型 / AI 与机器学习）。
> 本文是**骨架式复习总纲**，配合 `Week 01.md` – `Week 09.md` 九份周笔记使用。凡具体代码、逐题解法、输出逐行判读，一律回周笔记查；本文只负责**串线、归类、指路、纠错**。

---

## 一、这门课在讲什么

**性质**：这是一门为**地球与行星科学家**开的 Python 课，不是计算机系的编程导论。讲师开宗明义："课程是 **applied（应用型）**而非 fundamental computing"——不讲计算机为什么能工作、不讲编程语言如何实现、不讲算法的数学推导。它教的是**用现成的科学计算生态解决真实的地球科学问题**。

**目标**（讲师的三句话）：
- *"我们不可能教完 Python 的一切，但能给你一套工具，让你开始自己的旅程。"*
- *"你不需要完美记住语法"*（course expectations 原文）——课程给的是一堆可以改、可以复用的 **template（模板）**。
- *"It's all about learning the workflow"*（Week 9）——考的是**工作流**：数据从哪来、经过哪些处理、交给哪个工具、结果怎么验证。

**设计思路**：整门课是一条从"语言"到"生态"再到"科学问题"的单向上升线。前四周把编程当作**语言**来学（讲师原话：学编程像学一门外语），第五周起把编程当作**工具箱**来用，每周引入一个成熟的库，落点始终是真实数据与真实问题——火山喷发数据库、英国基岩与洪水风险图、北京空气质量、葡萄牙森林火灾、亚马逊蛙鸣。

**贯穿全课的三条价值观**（比任何语法都更该记住）：
1. **"Make it work, make it right, make it quick"** —— 先能跑，再正确，最后才谈快。
2. **"Code that works isn't necessarily correct!!"** —— 这句话从 Week 2 一路重复到 Week 9。
3. **"Garbage in, garbage out"** —— Week 6 起反复出现；Week 9 明确说"数据准备占机器学习流程 90% 以上"。

---

## 二、全课主线与各周脉络

课程明确分为两个阶段，分水岭在 **Week 5/6 之间**：

**语言基础期（Week 1–5）**——讲师称 Week 1–2 为 **"Vanilla Python"（原味 Python，不导入任何模块）**，Week 3–5 为 **"Modules and Functions"** 三讲。这一阶段的知识**可迁移到任何编程语言**（讲师原话："不管你学 Python、C、Java 还是 PHP，你都要学会搭这些构件"）。Week 4 的生命游戏是 Week 1–3 的总汇（数组 + 嵌套循环 + 条件语句 + 自定义函数四件套第一次合体），Week 5 是这一阶段的收尾与 checkpoint。

**生态工具期（Week 6–9）**——统称 "Pandas and data discovery" 支线，**四周全部建立在 pandas 之上**（讲师原话）。每周引入一个库，且每周都在上一周的数据结构上加一层能力：pandas 的 DataFrame → 加 geometry 列变成 GeoDataFrame（W7）→ 把 index 换成时间戳（W8）→ 把列拆成 features 与 target 喂给 sklearn（W9）。

| 周 | 主题 | 核心库 | 掌握的能力 | 应用场景 |
|---|---|---|---|---|
| 1 | Python 入门：数据类型 / 运算符 / list & tuple / 循环 | 无（vanilla） | 变量与赋值、int/float/complex、`**` 幂运算、索引从 0 开始、`for`+`range`、缩进规则、读 Traceback | 物理常量计算（E=mc²、德布罗意波长、理想气体） |
| 2 | 循环与条件语句 | 无（vanilla） | `if/elif/else`、比较与逻辑运算符、嵌套循环、字符串拼接、穷举搜索 | 分段函数、Bob Newby 密码破解（5 层嵌套） |
| 3 | 模块与函数、NumPy 入门 | `numpy`、`matplotlib` | `def`/`return`、`import ... as`、`np.zeros`/`np.array`、切片、逐元素运算、向量化 | 二维数值曲面与等值线图 |
| 4 | Conway's Game of Life | `numpy`、`matplotlib`、`IPython.display` | 2D 数组"画图形"、四层嵌套循环、Moore 邻域计数、同步更新、切片放置、伪动画 | 元胞自动机；与二年级 agent-based model 呼应 |
| 5 | 用 SciPy 解微分方程 | `scipy.integrate` | RHS 函数写法、`odeint`、`linspace`、解的形状 `(t, 变量)`、参数敏感性 | 放射性衰变、Lorenz 混沌、Lotka-Volterra 捕食者-猎物 |
| 6 | Pandas 与数据探索 | `pandas`、`cartopy` | `read_csv`、`.head/.shape/.dtypes`、布尔筛选 `&`、`.value_counts()`、`.values` 转 NumPy、世界地图散点 | Smithsonian 全球火山喷发数据库（9891 次喷发） |
| 7 | GeoPandas 与 GIS | `geopandas`、`contextily`、`shapely` | 矢量 vs 栅格、CRS 与 `to_crs`、图层叠加 `ax=`、`sjoin`/`clip`/`buffer`/`distance`/`centroid`/`boundary` | 英国基岩 + 历史煤矿；大曼彻斯特洪水风险 vs 电力变电站 |
| 8 | Pandas 时间索引、合并与统计可视化 | `pandas`、`seaborn` | `to_datetime`、`set_index`、DatetimeIndex 属性、`pd.merge` inner join、`.corr()`、heatmap / pairplot / boxplot | 北京 2017–18 气象 × 空气质量（18 站） |
| 9 | 机器学习入门 | `scikit-learn` | 三类 ML、标准化四种 scaler、PCA 降维、KMeans、簇→标签映射、train/test split、RandomForest、accuracy & confusion matrix | 葡萄牙森林火灾聚类；亚马逊蛙鸣 MFCC 分类（7195 条） |

**承接关系的几个关键节点**（考试与作业里最值得说的）：
- **W2 → W3**：`for` 循环和条件语句会引入 **overhead**（CPU 要停下来检查），这是引入 NumPy **向量化**的直接动机。
- **W3 → W4**：Week 3 的二维数组索引与切片，就是为了 Week 4 的 50×50 宇宙。
- **W4 → W9**：Week 4 是"**已知规则 → 生成模式**"（正问题），Week 9 聚类是"**已知数据 → 反推分组**"（反问题）。讲师明确点出这个对称。
- **W5 → W6**：Week 5 是最后一次"自己造数据"，Week 6 起全是"别人采集好的真实数据"。
- **W6 → W7**：Week 6 按**数值条件**筛子集（`data[data['Start Year']==2019]`），Week 7 换成按**地理边界**筛（`.clip()`）——讲师原话："否则我们就得把这个边界的所有形状特征都手写出来"。
- **W7 → W8**：Week 7 按**空间**合并（`sjoin`），Week 8 按**时间**合并（`merge` on timestamp）。这是同一个思想的两种坐标。
- **W8 → W9**：Week 8 的 `.corr()` 只能说"相关"，Week 9 才开始做"预测"。讲师用 *"correlation doesn't infer causation"* 完成过渡。

---

## 三、能力体系（按能力而非按周重组）

### 3.1 语言基础（W1–W2 建立，W3 收口）

**数据类型**：`int` / `float` / `complex`（只在 W1 出现一次）/ `str` / `bool`。Python 是**动态类型**——不必事先声明；运算时会**自动把低精度提升为高精度**（int ÷ float → float）。贯穿全课的两个坑是**浮点精度**（`298.15-273.0 = 25.149999999999977`）与 **`NaN`**（W1 认识它，W6 在真实数据里第一次大量遇到，W8 学会 `np.nanmax` 绕开它，W9 学会 `dropna()`）。

**控制流**：`for ... in ...:` → `if/elif/else` → 嵌套循环。递进链条非常清晰：W1 单层循环遍历列表 → W2 循环 + 条件 + 三重/五重嵌套 → W3 双层嵌套填 2D 数组 → W4 四层嵌套（外两层扫棋盘、内两层扫邻域）。**`elif` 链必须"既无重叠也无遗漏"**是 W2 最重要的教训，也是全课"silent failure"概念的起点。

**函数与作用域**（W3 建立，W5 深化）：`def`/`return`/形参与实参/局部变量。两个必须分清的概念：
- **`z[...] = ...`（原地修改，外部可见） vs `z = ...`（重新绑定，外部不可见）** —— W3 Exercise 4 与 Exercise 5 恰好是这对概念的完美对照。
- **全局变量的隐式依赖** —— W5 的 `differential_function` 读全局 `Gamma`，改全局变量就改变了函数行为；方便但危险，正规写法是 `odeint(..., args=(Gamma,))`。

**模块导入**（W3）：`import X` / `import X as Y` / `from X import Y`。三种写法的选择只能靠**查文档**——讲师在 W3、W5、W8 三次强调"去读 documentation"。

### 3.2 数值计算（W3 建立，W4 大练，W5 沿用）

从 list 换成 NumPy array 是一次**思维方式的切换**：

| | list | numpy array |
|---|---|---|
| 数据类型 | 可混装 | **必须统一（dtype）** |
| 大小 | 可 `append` 动态增长 | **创建时定死形状** |
| `+` 的含义 | **拼接** | **逐元素相加** |
| 为什么快 | —— | 正因为事先声明了形状与类型 |

递进脉络：`np.zeros(shape, dtype)` 建骨架 → `[i]`/`[r,c]`/`[a:b]` 索引与切片 → `[:, :]` 表示"全部" → 逐元素运算 `A+B`、`A*B`（**不是矩阵乘法**）→ **向量化**取代显式循环（W3 Exercise 4 的 90000 次循环 vs Exercise 5 的一行 `z = x + y*x`）→ W4 用切片把小图形整块"投放"进大宇宙 → W5 用 `solution[:, k]` 从解矩阵里取出第 k 个变量的时间序列。

**两个反复踩的坑**：切片**左闭右开**（要包含 `row+1` 就得写 `row+2`）；**切片越界会被静默裁剪、整数索引越界才报 IndexError**（W3 Exercise 1 官方解答的 `0:7` 就是靠这个"侥幸"跑通的）。

### 3.3 数据处理（W6 建立，W7–W9 全程使用）

**DataFrame 心智模型**：讲师最精炼的定位是 *"pandas 之于数据 = numpy 之于数组"*。DataFrame 是二维、**大小可变（size-mutable）**、**异质（heterogeneous）**、**带标签轴（labeled axes）**的表格。

能力递进：
1. **读与看**（W6）：`read_csv` → `.head()` → `.shape/.size/.ndim/.dtypes/.columns`。**加载后立刻 `.head()`** 是全课最实用的一条纪律（讲师：报错未必是逻辑错，很可能是你根本读错了文件）。
2. **筛**（W6）：布尔掩码 `df[df['col'] > x]`，多条件用 `&`/`|`/`~` 且**每个条件加括号**。这个模式在 W7（选岩性）、W8（选站点、选月份）、W9（选正的过火面积）反复出现。
3. **数**（W6）：`.value_counts()` → `.size` / `.idxmax()` / `.nunique()`。W9 用它确定 `n_clusters` 该填几。
4. **转**（W6）：`.values` 把列变成 NumPy 数组，喂给绘图与 sklearn——这是 pandas 与 numpy 的接缝。
5. **时间索引**（W8）：`pd.to_datetime()` → `set_index()` → 解锁 `.index.hour/.month/.weekday`。这是"把 index 从无意义的行号换成有科学含义的标签"的一次跃迁。
6. **合并**（W7 空间 / W8 时间）：`gpd.sjoin` 按几何关系连接；`pd.merge` 按共同键 inner join。**两者共享同一个动机**：手工对齐两份数据来源"有太多出错机会"。

### 3.4 地理空间（W6 起步，W7 展开）

**W6（Cartopy）**：把经纬度画成散点，理解 `projection=` 与 `transform=` 的区别（前者是画布坐标系，后者是"我给的数据属于哪个坐标系"）。Cartopy 只是"matplotlib 认得地理坐标的画布"。

**W7（GeoPandas）**：真正的 GIS。四个概念层：
- **数据模型**：矢量（Point/LineString/Polygon/MultiPolygon）vs 栅格（网格 + cell values，分辨率依赖）。GeoDataFrame = 普通 DataFrame + 一个 `geometry` 列。
- **坐标参考系（CRS）**：Geographic（EPSG:4326，单位**度**）vs Projected（EPSG:3857 Web Mercator / EPSG:27700 British National Grid，单位**米**）。**统一 CRS 是一切空间分析的前提**——不统一"会看起来很荒谬，房子在海里"。
- **空间运算**：`sjoin`（按位置连接）/ `clip`（饼干模具）/ `buffer`（画圈）/ `distance`（最短距离，点在多边形内为 0）/ `centroid`（多边形→点）/ `boundary`（多边形→轮廓线）。
- **图层堆叠**：第一次 `.plot()` 返回 `ax`，此后每层都传 `ax=ax`，最后 `cx.add_basemap(ax, crs=...)` 铺底图。

### 3.5 可视化（全课隐线，W8 集中）

课程**从不专门教绘图**——讲师明确说"绘图代码这门课始终给你模板"。但按图型分类的话，全课覆盖了：

| 图型 | 出处 | 用途 |
|---|---|---|
| 折线图 `ax.plot` | W2、W5 | 函数曲线、ODE 解、时间序列 |
| 填充等值线 `plt.contourf` | W3 | 二维数值曲面 |
| 图像 `plt.imshow(cmap='binary')` | W4 | 把 2D 整数数组渲染成黑白棋盘 |
| 3D 折线 `add_subplot(projection='3d')` | W5 | Lorenz 吸引子 |
| 地图散点 `plt.scatter(..., transform=)` | W6 | 火山位置 |
| GeoDataFrame `.plot(column=, cmap=, legend=)` | W7 | 专题地图（按属性分类着色） |
| 直方图 `.hist(column=)` / `sns.histplot(hue=)` | W6、W8、W9 | 单变量分布；按类别着色看可分性 |
| 箱线图 `.boxplot(by=)` / `sns.boxplot` | W8、W9 | 五数概括、日变化、按簇分组 |
| 热力图 `sns.heatmap` | W8、W9 | 相关矩阵、混淆矩阵 |
| 配对图 `sns.pairplot` | W8 | 变量两两关系 |

**两条判读纪律**：① 对比两图时必须 `set_ylim` **统一量程**；② 数据跨数量级时用 `set_yscale('log')`（但 log 轴会**静默丢弃 0 和负值**）。

### 3.6 科学计算与建模（W5、W9）

**W5（SciPy 解 ODE）** 的四步骨架**不是 Python 独有的**，任何语言解 ODE 都是这个流程：
```
import 模块 → 定义 RHS 函数 → 定义输出时刻数组 → 调用 solver
```
配套的概念：analytical vs numerical solution、time step 与误差累积、rtol/atol 容差、初值问题、耦合方程组（输入解包顺序 = 输出返回顺序）、确定性混沌与初值敏感性。**方法论亮点**：放射性衰变**故意选了一个有解析解的方程**，让你能验证数值解——"先在已知答案的问题上验证代码，再拿去解未知问题"。

**W9（scikit-learn）** 的核心洞察是 **"相似 = 数字之间的距离"**（欧氏距离），以及 **sklearn 的统一接口**（`Model()` → `.fit()` → `.predict()` / `.transform()`，训练后属性一律带下划线后缀如 `.labels_`）。两套工作流：

```
无监督：load → clean → standardise → [reduce dimensions] → fit cluster → [map to labels → evaluate]
有监督：load → clean → [standardise] → train_test_split → fit → predict → evaluate
```

**必须记住的两个判断**：
- **标准化对距离类算法（KMeans / KNN / SVM / PCA）是必需的，对树类算法（决策树 / 随机森林）是不必要的**——这解释了为什么 W9 里 RandomForest 不标准化也有 0.99。
- **PCA 之前必须先标准化**，因为 PCA 找的是方差最大的方向。

---

## 四、语法与函数速查索引

> 用法："我要做 X，该去哪一周找"。具体参数、示例、输出判读见对应周笔记。

**基础语法** — `#` 注释 / `=` 赋值 / 变量命名（区分大小写）/ 缩进与冒号规则 / 科学计数法 `3.0e8` → **W1**；`==` `!=` `<` `>` `<=` `>=` / `and` `or` `not` / 链式比较 `2<=x<=3` / `pass` → **W2、W4**；f-string `f'{x:.2f}'` → **W9**。

**内建函数** — `print()` `type()` `int()` `float()` `abs()` `pow()` `range()` `len()` → **W1**；`str()` `''.join()` `"{}".format()` → **W2**；`sorted()` `set()` `any()` → **W7、W9**。

**容器** — list `[]` / tuple `()` / 索引 `[i]` / `.append()` → **W1**；列表推导式 `[f(x) for x in seq]` → **W2**；dict `{}` 只提名字，全课未展开。

**函数与模块** — `def` / `return` / 形参实参 / 局部变量 / 副作用 → **W3**；`import` / `import ... as` / `from ... import` / `.` 点运算符 / `PYTHONPATH` → **W3**；`lambda` + `.apply()` → **W7**。

**NumPy** — `np.zeros(shape, dtype)` `np.array()` `np.max/min` `np.multiply` / 索引 `[r,c]` / 切片 `[a:b, c:d]` / `[:, :]` / 逐元素运算 → **W3**；`np.arange` `np.linspace` → **W5**；`np.nanmax` `np.nanmin` `.values` → **W8**；`np.zeros_like` `np.unique` `np.bincount().argmax()` → **W9**。

**SciPy** — `from scipy.integrate import odeint`、`odeint(func, y0, t, rtol=, atol=)`、RHS 函数签名 `(状态, 时间)` → **W5**。

**Pandas — 读与查** `pd.read_csv()`（也能吃 URL，见 W9）/ `.head()` `.tail()` / `.shape` `.size` `.ndim` `.columns` → **W6**；`.dtypes` → **W8**。
**Pandas — 选与筛** `df['col']` / `df[['c1','c2']]` / 布尔掩码 / `&` `|` `~` / `.str.contains()` → **W6、W7**。
**Pandas — 统计** `.value_counts()` `.idxmax()` `.nunique()` `.min()` `.max()` → **W6**；`.corr()` `.dropna()` `.describe()` → **W8**。
**Pandas — 时间** `pd.to_datetime(format='mixed')` / `set_index()` / `.index.hour/.minute/.weekday/.month/.year` → **W8**。
**Pandas — 合并与修改** `pd.merge(on=, how=)` / `df['新列'] = ...` / `.copy()` / `.iterrows()` / `.apply()` / `.reset_index(drop=True)` → **W7、W8**。
**Pandas — 绘图** `.hist(column=)` → **W6**；`.boxplot(column=, by=)` → **W8、W9**；`Series.plot(kind='bar')` → **W7**。

**GeoPandas / GIS** — `gpd.read_file()` / `.crs` / `.to_crs(epsg=)` / `geometry` 列 / `.geom_type` → **W7**；`gpd.sjoin()` / `.clip()` / `.buffer()` / `.distance()` / `.centroid` / `.boundary` → **W7**；`cartopy.crs` / `ccrs.PlateCarree()` / `ax.stock_img()` / `transform=` → **W6**；`contextily.add_basemap(ax, crs=, zoom=, alpha=)` → **W7**。

**Matplotlib** — `plt.figure(figsize=)` / `plt.axes()` / `ax.plot/set_title/set_xlabel/legend` / `plt.show()` → **W2、W5**；`plt.contourf` / `plt.colorbar` / `cmap` → **W3**；`plt.imshow(cmap='binary')` / `plt.subplot(1,2,1)`（**编号从 1 开始**）/ `plt.subplots(figsize=)` / `clear_output` + `time.sleep` 做伪动画 → **W4**；`fig.add_subplot(projection='3d')` / `alpha=` → **W5**；`plt.subplots(r,c)` 网格 + `axs[i,j]` / `set_ylim` / `set_yscale('log')` / `plt.xticks(rotation=90)` → **W7、W8、W9**；8 位 hex 颜色 `#ff000033`（RGBA）→ **W7**。

**Seaborn** — `sns.boxplot(data=, x=, y=, ax=)` / `sns.heatmap(corr, xticklabels=, yticklabels=)` / `sns.pairplot()` → **W8**；`sns.histplot(hue=, kde=, element=)` / `sns.scatterplot(hue=, palette=)` → **W9**。

**scikit-learn** — `KMeans(n_clusters=, random_state=)` / `.fit()` / `.labels_` / `.fit_predict()` → **W9**；`StandardScaler` `MinMaxScaler` `RobustScaler` `MaxAbsScaler` + `.fit_transform()` / `.transform()` → **W9**；`PCA(n_components=)` → **W9**；`LabelEncoder()` + `.inverse_transform()` → **W9**；`train_test_split(X, y, test_size=, random_state=)` → **W9**；`RandomForestClassifier(n_estimators=)` + `.predict()` → **W9**；`accuracy_score` / `confusion_matrix` → **W9**。

**Jupyter / 环境** — `%cd`、`!pip install`、`get_ipython()` 检测 Colab、Restart & Run All → **每周开头的样板 cell**；`os.getcwd()` / `os.path.join()` / `os.environ`（W7 的 PROJ 路径修复）。

---

## 五、跨周的编程思维与方法论

**1. 先想清逻辑，再写代码。** Week 4 讲师现场示范的方法是：先用自然语言写伪代码（`if cell == 1 and count < 2: cell = 0`），再翻译成 Python。Week 2 的 `elif` 边界问题也建议"把区间画在数轴上，检查是否既无重叠也无遗漏"。

**2. 把大问题拆成函数与模块。** Week 3 给的六条理由值得背：代码会越写越乱；重复写更容易出错；修 bug 只需改一处；结构清晰便于分工；可分享可独立测试；只有底层是函数和模块，版本控制才真正可行。反面教材是 Week 2 提到的 BASIC `GOTO` 语句造成的"意大利面条式代码"。

**3. 用小数据验证，再放大。** Week 4 先在 6×6 的 Beacon 上验证四条规则（周期 2，可以**手算**逐格核对），再放进 50×50 的宇宙跑 100 步。Week 5 先解有解析解的衰变方程，再解 Lorenz 与 Lotka-Volterra。

**4. 读懂报错信息定位问题。** Week 1 就把读 Traceback 训练成三步法：看最后一行（错误类型 + 原因）→ 看 `--->` 箭头（出错行）→ 看 `Cell In[n], line m`。Week 7、W8、W9 进一步区分 **Warning（程序继续跑）与 Error（程序中断）**，并教会看警告里的**文件路径**判断是"你的错"还是"库的错"。

**5. 向量化替代显式循环。** 动机链条：W2 的 overhead → W3 的 `array1+array2` → W3 Exercise 4/5 的 90000 次循环 vs 一行 → W4 亲身体验四层循环有多慢（50×50×100 步 ≈ 2000 万次迭代）→ W6 用 `data[条件]` 一行代替手写筛选循环。

**6. "代码能跑 ≠ 代码正确"的验证意识（全课最核心）。** 课程给了一整套**可操作的自检手段**：
- **心算核对边界值**：98² = 9604（W3）、81 × 3.4 = 275.4（W1）。
- **看数量级 / 色标上限**：W3 Exercise 2 色标该到 10⁴ 而不是 200。
- **看图形该有的特征**：W2 该有"台阶"、W3 该是"双曲弯曲而非直线条纹"、W5 该是"双叶蝴蝶"、W6 火山点该"沿板块边界成带状"。
- **用已知周期/已知答案验证**：W4 的 Beacon 必须周期 2、Block 必须纹丝不动；W8 的六个 `nanmax` 值题目已给。
- **交叉验算**：W6 的 862 与 `Length: 862` 对得上、9891×24 = 237384 对得上；W9 混淆矩阵的行合计必须等于 `value_counts()`。
- **用领域知识回头检查**：W7 发现 12 个煤矿落在火成岩上（不可能）→ 边界效应；W8 的 `wind_direction = 999017` → 伪装的缺测标记；W9 的 76% 准确率里两个类**从未被预测到**。

**7. 永远和"平凡基线"比。** W9 最深刻的一课：Family 分类 76% 看似不错，但"全猜最大类"就有 61.4%；Genus 的 80% 对应的基线是 57.7%，而代价是 5 个属完全丢失。**准确率单独看是不可靠的，必须配混淆矩阵。**

**8. 数据准备远重于算法。** W6 引入 EDA 概念 → W8 讲数据不对齐会产生"erroneous statistic"，进而影响真实决策 → W9 直接给出"数据准备占流程 90% 以上"。讲师的职业建议："越能展示你会做建模之前的清洗步骤，越有竞争力，因为**没多少人愿意花时间在这上面，但一切都建立在它之上**。"

---

## 六、调试与排错速查

| 报错 / 现象 | 典型成因 | 修法 | 首见 |
|---|---|---|---|
| `SyntaxError: invalid syntax` / `expected ':'` | 漏冒号、括号不配对、`if` 里误用 `=` | 从箭头行**往前一行**也检查 | W1、W2 |
| `IndentationError: expected an indented block` | 冒号后没缩进；代码块里只有注释没有语句 | 缩进 4 空格；空块放 `pass` | W1、W4 |
| `IndentationError: unindent does not match...` / `TabError` | 混用 Tab 与空格 | **永远只用 4 个空格** | W2 |
| `NameError: name 'X' is not defined` | 变量未定义；忘 import；notebook 单元格没按序跑 | Restart & Run All | W1、W3 |
| `IndexError: list index out of range` | 索引 ≥ 长度；`x[step+1]` 元素还不存在 | 最后一个索引是"长度−1"；检查 append 与索引的先后顺序 | W1、W2 |
| `TypeError: 'tuple' object does not support item assignment` | 试图改 tuple | tuple 不可变，改用 list | W1 |
| `TypeError: can only concatenate str (not "int") to str` | 字符串与数字直接相加 | `str(n)` 转换 | W2 |
| `TypeError: 'int' object is not callable` / `'ndarray' object is not callable` | 给属性加了括号（`.size()`、`.values()`） | 属性不加括号，方法才加 | W6 |
| `ModuleNotFoundError` | 模块没装或环境不对；`sklearn` 装的是 `scikit-learn` | `conda install` / 切回课程环境 | W3、W9 |
| `TypeError: Argument Z must be a 2-dimensional array` | 函数忘了 `return`，返回 `None` | 补 `return`；`print(z.shape)` | W3、W4 |
| `ValueError: could not broadcast ... shape (6,7) into (5,7)` | 切片区域形状与要塞入的数组不匹配 | 数清 `b-a` 是否等于形状 | W4 |
| `ValueError: operands could not be broadcast together` | 两数组形状不一致做逐元素运算 | 检查 `.shape` | W3 |
| `ValueError: could not broadcast (100,1) into (100,)` | `odeint` 永远返回 2D | 用 `solution[:,0]` 降维 | W5 |
| `TypeError: f() takes 1 positional argument but 2 were given` | RHS 函数漏写 `t` 参数 | 签名必须是 `(状态, 时间)` | W5 |
| `FileNotFoundError` | CSV 路径不对 / 工作目录不是你以为的 | `os.getcwd()`、`os.listdir()` | W6 |
| `KeyError: 'xxx'` | 列名大小写 / 空格 / 拼写错 | **永远用 `df.columns.values` 复制列名** | W6、W9 |
| `ValueError: The truth value of a Series is ambiguous` | 对 Series 用了 `and`/`or`/`not` | 改用 `&` `\|` `~`，且每个条件加括号 | W6 |
| `ValueError: x and y must be the same size` | 两列用了不同的筛选条件 | 先存子集再分别取列 | W6 |
| `AttributeError: 'Index' object has no attribute 'hour'` | index 不是 DatetimeIndex（忘赋值或忘转类型） | 查 `.dtypes` 与 `type(df.index)` | W8 |
| `SettingWithCopyWarning` | 对布尔筛选/clip 得到的"可能是视图"的对象赋新列 | `.copy()`；或 `df.loc[mask, 'col'] = val` | W7、W9 |
| `FutureWarning` / `DeprecationWarning` | 库内部用了将废弃的 API（看路径在 site-packages 里） | 不是你的错，升级库或忽略 | W8 |
| `CRSError` / `Cannot find proj.db` | PROJ 路径未设（曼大 JupyterHub 已知问题） | 设 `os.environ["PROJ_DATA"/"PROJ_LIB"]` | W7 |
| `IndexError: too many indices` | `plt.subplots(1,3)` 后写 `ax[0,0]` | 单行时 `ax` 是一维，用 `ax[0]` | W9 |
| **图是空的 / 一个点都没有** | 条件筛出 0 行（类型不匹配 `=='2019'`、字符串写错如 `'Stockport'` 少了 `District (B)`） | 筛完先 `print(len(subset))` | W6、W7 |
| **点全挤在中心 / 图层错位** | 忘写 `transform=`；两份数据 CRS 不统一 | 统一到 EPSG:3857 | W6、W7 |
| **两图不并排 / 22 张图叠成一张** | `plt.show()` 位置不对 | 子图之间别 show；循环内要 show | W4、W9 |
| **重复运行 cell 结果不断累积** | 含 `.append()` 的 cell 反复跑 | 重新初始化 `x = []` 或重启内核 | W1 |
| **改了代码结果不变 / 注释掉却仍能跑** | Jupyter 变量残留在内核内存里 | **Restart & Run All**（交作业前必做一次） | W7、W9 |
| **`==` 用于浮点数** | 二进制无法精确表示十进制小数 | 用 `abs(a-b) < 1e-9` | W1、W2 |
| **`^` 当成幂运算** | `^` 是按位异或，`2^3 = 1` | 幂用 `**` | W1 |
| **`x = x.append(v)`** | `.append()` 返回 `None` | 直接 `x.append(v)` | W1 |
| **`np.max` 返回 `nan`** | NaN 会"传染" NumPy 统计函数 | `np.nanmax`；或直接用 pandas 的 `.max()`（默认忽略 NaN） | W8 |
| **`.to_crs()` / `set_index()` / `dropna()` 没生效** | Pandas/GeoPandas 方法**默认返回新对象** | 必须赋值回去，或 `inplace=True` | W7、W8 |
| **`cx.add_basemap()` 卡住不动** | 正在从服务器下载瓦片（可能几分钟） | 不是死机；控制 `zoom=`（每 +1 瓦片 ×4） | W7 |

---

## 七、全课勘误表

> 汇总九周笔记记录的**官方 Notebook、解答与讲义中的真实错误**。**★** 标出"看似能跑实则有问题"的隐蔽 bug——它们不报错，只是安静地给出错误或不符合题意的结果。

### 代码 bug（★ 为隐蔽型）

| 周 | 出处 | 问题 | 应为 | 说明 |
|---|---|---|---|---|
| **4** ★ | Practical 4，`search_each_cell` 边界判断 | `if (row2<0) or (row2>=total_rows) or **(col<0)** or (col2>=total_cols)` | `(col2<0)` | `col` 来自 `range()` 永远 ≥0，该条件形同虚设。`col==0` 时 `col2=-1` 进入 else，NumPy 负索引读到**最后一列**——等于左右边界偷偷连成柱面。本周所有例子的最后一列恰好全 0，所以结果看起来正确。**换个初始条件就暴露。** |
| **9** ★ | Practical 9 Exercise 6 | 题目要求"不降维"，`pca = PCA(...)` 两行已注释掉，但 `kmeans.fit_predict(**pca_components**)` 没改 | `fit_predict(features_scaled)` | 靠上一个 cell 残留在内核里的 `pca_components` 跑通，**实际仍在 2 维 PCA 数据上聚类，完全没达到题意**。Restart & Run All 会立刻 `NameError`。 |
| **9** ★ | Practical 9，两处混淆矩阵热图 | `xticklabels=set(target), yticklabels=set(target)` | `sorted(target.unique())` 或 `le.classes_` | `set` **无序**，而 `confusion_matrix` 行列一定按字母序——**坐标轴标签很可能与矩阵错位**。 |
| **8** ★ | Practical 8 Exercise 4 | `sns.boxplot(data=**combined_df**, x=combined_df_new..., y=combined_df_new...)` | `data=combined_df_new` | `data=` 与 `x=`/`y=` 来自**不同的站点**（Shunyi vs pingchang）。因为 x/y 传的是实际数组，`data=` 被忽略，结果碰巧对；但改成 `x='hour'` 就会画出完全错误的图且不报错。 |
| **8** ★ | Practical 8，`set_index()` 出现 4 次 | `Shunyi_met_df.set_index('utc_time')` 等**未赋值** | `df = df.set_index(...)` | 方法返回新对象，原变量纹丝不动。之所以后续能跑，是因为 `pd.merge` 走的是同名列而非索引。 |
| **3** ★ | Practical 3 Exercise 1 官方解答 | `practice_matrix[0:2, **0:7**] = 2.5`；`[2:6, 0:7] = 5.5` | `[0:2, :]` / `[2:, :]` | 矩阵只有 6 列 5 行，写 `0:7`、`2:6` 均**越界**。切片越界**不报错、被静默裁剪**（换成整数索引就会 `IndexError`）。 |
| **2** | Practical 2，`if/else` 改写示例 | `else x < y:` | `else:`（不带条件）或 `elif x < y:` | 非法语法，会 `SyntaxError`。 |
| **2** | Practical 2，Version 1 / Version 2 示意代码 | `elif x[step] >= 60` 两处**漏冒号** | `elif x[step] >= 60:` | `SyntaxError: expected ':'`。 |
| **4** | Practical 4，Block 示范 | `print(print("A finished array", Block))` | 单层 `print(...)` | 双重 print 导致屏幕上多出一个 `None`（`print` 返回 `None`）。 |
| **9** | Practical 9 Exercise 4b 示例 | `x='MCCs_17'` | `'MFCCs_17'` | 少一个 F，会 `KeyError`。 |
| **9** | Practical 9 §1.2.2 演示 scaler | `data = pd.DataFrame({'Height (cm)': ...})` | 换个名字如 `demo_data` | **覆盖了森林火灾的 `data`**，同一次顺序运行下后续 `data["area"]` 会 `KeyError`。 |
| **9** | Practical 9，PCA 段 | `pca_df['target'] = target` | `= target.values` | features 若来自筛选过的 df，索引不对齐会产生大量 NaN。此处恰好未筛选才无恙。 |
| **7** | Practical 7 Exercise 2 | `joined_df_ex2[joined_df_ex2.geom_type == 'Polygon']` | `.geom_type.isin(['Polygon','MultiPolygon'])` | 会**静默丢掉所有 MultiPolygon**。 |
| **7** | Practical 7 Exercise 5 | 复用变量名 `risk_zone = Stock_ssdf_wm_GM.buffer(1000)` | 用新名字如 `risk_zone_stockport` | 覆盖了全 GM 的 `risk_zone`，回头重跑上面的 cell 会画错。 |
| **7** | Practical 7，距离循环 | `ssdf_wm_GM['min distance to flood'] = ...` 触发 `SettingWithCopyWarning` | clip 之后加 `.copy()` | 同一 notebook 前面 `ssdf_wm_copy = ssdf_wm.copy()` 写法是对的，形成对照。 |
| **9** | Practical 9 Exercise 3 | `data_new = data[data["area"] > 0]` 后赋新列 | `.copy()` | 同上，`SettingWithCopyWarning`。 |

### 题面与解答不一致 / 数字对不上

| 周 | 出处 | 问题 | 说明 |
|---|---|---|---|
| **3** | Practical 3 Exercise 2 | 题面写 **200 行 × 300 列**，解答用 **100×100** | 以方法为准，数字不必纠结 |
| **3** | Practical 3 Exercise 4 | 题面 **200×200**，解答 **300×300** | 同上 |
| **3** | Practical 3 Exercise 5 | 题面 **200×200**，解答 **300×300** | 同上 |
| **2** | Practical 2 Objectives | 写 "one of **two** equations"，实际是**三段函数** | 编号/计数错误 |
| **9** | Practical 9 Exercise 1 题目文字 | 写 `'Rain'`（大写 R），实际列名 `'rain'` | 照抄会 `KeyError` |
| **9** | Practical 9 结尾 "Exercises 1–5" 复述框 | 与正文实际的 **Exercise 1–7** 编号对不上 | 自动生成的通用总结，不是真题目清单 |
| **8** | Practical 8 结尾 "What We Did" | 声称练了 Mean / Standard deviation | 正文并没有单独练习这两项 |
| **8** | Practical 8，merge 后的注释 | "our data now starts on 30/1/2017, **even though we had meteorological data before that date**" | **方向说反**：在此之前有数据的是**空气质量**，气象数据本身就从 1/30 开始 |
| **6** | Practical 6，Series 规模检查 | `print("Shape of dataframe =", series_size)` 与 `print("Size of dataframe =", series_shape)` | **两个标签贴反了**。很好的提醒：输出文字是人写的，不代表它正确 |
| **6** | Practical 6 说明文字 | 写成 `.values()`（带括号） | 属性不加括号；代码里是对的，**以代码为准** |
| **6** | Practical 6 Exercise 1 | "twice as big" 有歧义 | `s` 是**面积**（points²），标准答案取 `s=18`；若指直径翻倍应为 `s=36` |
| **7** | Practical 7 Exercise 2 | 标题写 "Create a map of collieries on mudstone bedrock"，目录写 "Plot the distribution of bedrock under collieries across the UK" | 标题不一致 |

### 讲课口误 / 转写错误 / 事实存疑

| 周 | 出处 | 问题 | 应为 |
|---|---|---|---|
| **2** | 录音转写 | "With a list, we have square brackets. With a tuple, we have **curly brackets**." | tuple 用**圆括号 `()`**；`{}` 是 dict/set |
| **2** | 录音转写 | 把冒号 `:` 说成 "semicolon"（分号） | 是**冒号** |
| **2** | 讲义/口述 | "全球数据中心约占地球电力供应的 **17%**" | 业界常引数值在 **1–2%** 量级；引用前请自行核查 |
| **3** | 录音转写 | "an ump module" / "numpy as MP" / "LF statement" / 讲函数括号时说 "curly brackets" | `numpy` / `np` / `elif` / parentheses `()` |
| **7** | 录音转写 | "So it's a **raster** data because it's a point on a map. Sorry, it's a **vector** data..." | 点 = 矢量（老师当场纠正） |
| **9** | 录音转写 | 讲 min-max scaling 时说 "between **minus one and one**" | Min-Max 标准范围是 **[0, 1]**；[-1,1] 是 MaxAbsScaler |
| **9** | 课末 | notebook 底部承诺的 resources 一节**是空的**；另有一处 "extra 2022" | 老师说"ignore that"，并承诺邮件补发（Keras / PyTorch / Nvidia DLI） |

### 冗余、遗留与未处理的数据问题

| 周 | 出处 | 问题 |
|---|---|---|
| **2** | Exercise 5 密码生成 | `n = 5` 定义后**从未使用**（`range(0,5)` 里的 5 是硬编码） |
| **3、9** | Exercise 5 / §1.5 | 把 `z` / `pca_df` 作为参数或变量创建后**未被使用**；`from scipy.stats import mode` 导入未用 |
| **5** | Exercise 2 模板 | 保留了 `from mpl_toolkits.mplot3d import Axes3D`，但本例是 2D 图 |
| **5** | Exercise 1 | `np.zeros((10), dtype=float)` 少了逗号，规范写法是 `(10,)` |
| **6、8、9** | 三周开头 | `from os import path` 之后立刻 `path = os.getcwd()`，**变量遮蔽了模块名** |
| **6** | print 文本 | `"Earlist Eruption occured in"`（Earliest / occurred 拼写错误） |
| **1** | Exercise 2 期望输出 | `"The De Broglie wavelength of an eletron"`（electron 拼写错误） |
| **4** | Exercise 3 解答 | 行尾多余的分号 `new_space[row,col] = 0;`（C/MATLAB 习惯，PEP 8 不推荐） |
| **9** | 青蛙数据加载 cell | 注释写 `# Load the Air BnB data`，实际载入的是蛙鸣数据（复制粘贴遗留） |
| **9** | 全部特征列表 | `MFCCs_ 1` **全部等于 1.0**（零方差常数列），从未被剔除，对聚类毫无贡献 |
| **8** | 北京气象数据 | `wind_direction` 出现 **999017.0**（物理上不可能），这是仪器的**伪装缺测标记**，notebook 未处理，会毁掉该列的 mean/std/corr |
| **7** | 煤矿-基岩空间连接结果 | 12 个煤矿落在 `MAFIC IGNEOUS-ROCK` 上（火成岩上不可能有煤矿）——边界效应/定位误差，需用地质常识识别 |
| **7、8** | 距离与单位 | 同一段代码里 `distances`（米）、新列（km）、`buffer(1000)`（米）、阈值 `1`（km）**四种单位混用**，列名未标注单位 |

---

## 八、与其他课程的衔接

**与同学期 Mathematics and Physics 的呼应。** 最直接的一处是 **Week 5**：数学课上手算解 ODE（给函数求导数、按规则积分），编程课用 SciPy 几行代码把同一类方程数值解出来。讲师原话："作为科学家，我们为什么要手算一切？我们也算不完。"两门课教的是同一件事的两面——**数学课教你"解是什么、为什么成立"，编程课教你"解不出来的时候怎么办"**。Week 5 特意选了有解析解的放射性衰变作为第一个例子，正是为了让两边对得上。此外 Week 3 的矩阵/逐元素运算与线性代数、Week 5 的 Lorenz 混沌与动力系统、Week 9 的欧氏距离与向量范数，都能和数理课互相印证。

**与秋季学期 Statistics 的 R 语言对照。** 同学们已用过 **RStudio**；Jupyter Notebook 里同样能跑 R（Jupyter 之名就来自 **Ju**lia + **Py**thon + **R**）。Week 8 做的相关系数、箱线图、五数概括、偏态判读，与统计课的内容完全对应，只是换了工具：**统计课教你"这个统计量意味着什么"，编程课教你"在 18000 行真实数据上怎么算出它、怎么画出来"**。两边的关键交叉点是 Week 8 反复强调的"**数据必须先对齐，统计量才有意义**"——这是统计课通常默认成立、而真实数据里根本不成立的前提。

**在本课程内部的落点：notebook 评估作业。** Week 10–12 无讲座，只有实践课答疑。作业形式是**一份 Jupyter Notebook**（`.ipynb`，不接受 PDF/Word，交到 Turnitin），从 **Week 4–9 的六个主题中任选其一**：Conway's Game of Life / Differential Equations / 两个 Geospatial / Pandas 与统计分析 / Cluster analysis。结构 = Abstract + Introduction（讲**科学领域为什么重要**，不是讲数据科学）+ Methodology（**必须用 class template**，说清用了哪些模块与函数、workflow 如何组织）+ [GenAI methodology，可选] + Code（必须有注释）+ Results（含 limitations）。可以直接复用 practical 的代码且**无需引用来源**，但**必须改动**——改参数、改选项、多画几张图。讲师的策略建议：**先在有助教的实验室里把代码跑通，再围绕输出补文字。**

**在后续课程与研究中的用途。**
- **二年级 Environmental Modelling**：Week 4 的生命游戏就是最简版的 **agent-based model**；该课程既有编译型语言写的模型，也有 Python 模型。
- **三年级毕业项目**：有大量基于 Python 的课题可选。
- **GIS 方向**：Week 7 只是"皮毛"，学校有整门 GIS 课程乃至地理空间分析的硕士方向；ArcGIS / QGIS 是行业标准，而在 Python 里做的好处是可以继续往上叠机器学习与统计模块。
- **AI / 数据科学方向**：Week 9 之后的延伸路径是 **Keras**（入门友好、可做实时目标检测）、**PyTorch**（更底层、性能更好）、**Nvidia Deep Learning Institute**（有免费自学课程与证书，系里正与 Nvidia 建立合作）。
- **就业与研究通用**：讲师反复强调 **GitHub 是"数字 CV"**，以及**数据清洗能力比模型能力更稀缺**——"没多少人愿意花时间在这上面，但一切都建立在它之上"。

**最后一句**：这门课交付的不是九周的语法，而是一套可迁移的 workflow——**载入 → 检查 → 清洗 → 对齐 → 分析 → 可视化 → 验证**。讲师说得很清楚："如果你将来做污染数据、健康数据、金融数据，你会学到那个领域的行业标准方法，**但 workflow 是一样的**。这就是为什么这门课是打地基的。"
