# Mathematics and Physics (HT) — 手册分配索引

> 由手册比对与索引 Agent 生成。供逐周笔记 Agent 精确定位本周应读的主手册章节。
> **不切分原文件**：周 Agent 用 Read 工具的 offset/limit 参数只读自己那一段，源材料保持原样。
> 子课程根目录（下文简称 `<ROOT>`）：`/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics`
> 主手册绝对路径：`/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md`（4,291 行，44,393 词）

---

## 一、材料构成

本子课程共有五类 md 材料，关系已实地核实如下：

| 类别 | 位置 | 是什么 | 与主手册的关系 |
|---|---|---|---|
| **主手册** | `<ROOT>/main(1).md` | 《EART11200 Semester 2 Handbook 2024-25》全书，作者 Matthew Thomas。含 15 章：1–5 微分、6–10 积分、11 向量与偏微分、12–15 附加材料 | **唯一完整源**。以下三类文件全部是它的切片 |
| **周版章节正文** | `<ROOT>/Lecture/Week N/ChapterN.md`（N=1..10） | 主手册对应章的**正文部分**（Overview + 编号小节），到该章 `## Exercises` 之前为止 | 逐词核实：与主手册正文段词汇重合率 97%–100%，属**同一文本**。**不含 Exercises、不含 Solutions** |
| **周版习题** | `<ROOT>/Practical/Week N/ExercisesN.md`（N=2..10） | 主手册对应章的 `## Exercises` 一节 | 题号、页眉页码完全对应。**Week 1 无此文件**（见异常） |
| **周版习题解答** | `<ROOT>/Practical/Week N/SolutionsN*.md`（N=1..10） | 主手册对应章的 `## Solutions` 一节 | 题号一一对应 |
| **课堂材料（非手册）** | `Lecture/Week N/lectureN*.md`（幻灯片）、`Lecture/Week N/EART11200 - DD-Mon-transcript.md`（逐字稿）、`Practical/Week N/practicalN_soln*.md`（practical 课堂题解） | 与手册**不同源**的独立材料 | 与主手册无文本重叠，需各周单独阅读 |
| **复习/考试材料** | `Lecture/Week 11/Revision_Differentiation.md`、`Lecture/Week 12/Revision_Integration.md`、`Practical/Week 11 & 12/2324_Exam%281%29.md` | 复习幻灯片与 2023-24 往年真题 | 与主手册无对应章节 |

**结论**：主手册 = 周版 `ChapterN.md` + `ExercisesN.md` + `SolutionsN.md` 三者之和，再加上从未被拆分的部分（见第二节）。

---

## 二、主手册 vs 周版：差异结论（本节是核心）

### 2.1 三条实地核实的结论

**结论 A ——「周版比主手册短」的原因已查明：周版 `ChapterN.md` 只有章正文，Exercises 与 Solutions 被拆到了 `Practical/Week N/` 下，并未丢失。**

以 Week 1 为例：主手册第 1 章占 123–679 行（557 行 / 4,868 词），其中正文仅 123–255 行（2,130 词），Exercises 257–497（1,826 词）、Solutions 498–679（912 词）。周版 `Chapter1.md` 为 131 行 / 2,050 词，恰好等于正文段。十周全部如此，词数与词汇重合率见 2.3 表。**因此「周版缺 Exercises/Solutions」这一初步猜测成立，但需补充：这两节并非缺失，而是被搬到了同周的 Practical 文件夹。**

**结论 B ——「主手册跳过第 10 章」是 PDF 转换假象，主手册其实有第 10 章。**

主手册第 3086–3087 行的内容是：

```
<!-- Start of picture text -->
10. Second-Order Ordinary Differential<br>Equations<br><!-- End of picture text -->
```

即第 10 章的标题在原 PDF 中是**图片形式的章名**，转 md 时被塞进了 HTML 注释块，没有变成 `#` 一级标题，所以 `grep "^#"` 看不到它。第 10 章正文（10.1 Overview / 10.2 Second-order Differential Equations / 10.3 Applied boundary value problems and steady-state）、Exercises、Solutions **全部存在**，占 3086–3420 行（335 行 / 3,596 词）。主手册目录页（第 87–92 行）也明确列出 `10 Second-Order Ordinary Differential Equations . . . 143`。

**结论 C ——周版章号相对主手册整体错位 1，真正没被拆分的是主手册第 9 章 Integration by Parts。**

对应关系按标题与内容核实（不是按编号）：

- 周版 Week 1–8 的 `Chapter1..8.md` ↔ 主手册第 1–8 章，**标题逐字相同**；
- 周版 `Week 9/Chapter9.md`「9. Second-Order Ordinary Differential Equations」↔ 主手册**第 10 章**（同名，正文逐段相同，词汇重合率 100%）；
- 周版 `Week 10/Chapter10.md`「10. Vectors and Partial Differentiation」↔ 主手册**第 11 章**（同名，重合率 97%）；
- 主手册**第 9 章 Integration by Parts（3008–3085 行）在任何一周的任何文件中都不存在**。

佐证：`Practical/Week 9/Exercises9(1).md` 的 PDF 页眉写的是「Chapter 9. Second-Order Ordinary Differential Equations」，题号为 Question 9.1–9.8；而主手册第 10 章的 Exercises/Solutions 题号**也是** Question 9.1–9.8，第 11 章题号是 10.1–10.9。也就是说 **主手册在把 Integration by Parts 插入为第 9 章时，只改了章标题编号，题号沿用旧编号未同步更新**；而各周拆分版是从「没有 Integration by Parts」的旧版排版生成的，所以章号少 1、与题号自洽。

### 2.2 主手册第 9 章 Integration by Parts 的实际状态

- 位置：3008–3085 行，78 行 / 454 词，是全书最短的一章。
- 正文（9.1 Overview、9.2 Integration by parts、Example 9.1–9.4）3008–3077 行，442 词，内容完整可读（公式与例题在原 PDF 中是图片，md 中只剩推导步骤文字）。
- **该章的 Exercises 与 Solutions 在主手册中本身就是空壳**：3078–3085 行只有两行占位文字「Algebraic problems Real-world problems」，一道题都没有。
- 全课程 `Lecture/` 与 `Practical/` 下所有 md（含 12 份逐字稿、两份复习幻灯片、往年真题）**均无 "integration by parts" 字样**（已全目录 grep 核实，零命中）。
- 幻灯片 `lecture9.md` 的 COURSE LAYOUT 表列出全部 10 个授课周主题：Calculating Gradients / Introduction to Differentiation / Differentiating Combinations of Functions / Optimisation & Properties of Derivatives / Second Order Derivatives & Root Finding / Introduction to Integration / Integration using Newtons Laws / Integration by Substitution / **Integrating Second Order ODEs** / Vectors and Partial Differentiation ——**没有 Integration by Parts**。

**判定：Integration by Parts 是一个写进手册但当年未实际讲授、未出习题、不在考纲的「遗留章」。**

### 2.3 逐周对应关系与差异表

| 周 | 周版文件 | 周版标题 | 对应主手册章节 | 主手册行区间 | 周版缺失部分 |
|---|---|---|---|---|---|
| 1 | `Lecture/Week 1/Chapter1.md` | 1. Calculating Gradients | 第 1 章（同名） | 123–679 | 无（Solutions 在 Practical）；**但 Exercises（257–497，1,826 词）在周材料中完全没有——`Practical/Week 1` 里放的是 `Chapter1(1).md`，即 `Chapter1.md` 的重复件，不是习题** |
| 2 | `Lecture/Week 2/Chapter2.md` | 2. Introduction to Differentiation | 第 2 章（同名） | 680–1003 | Exercises→`Practical/Week 2/Exercises2.md`；Solutions→`Solutions2.md` |
| 3 | `Lecture/Week 3/Chapter3.md` | 3. Differentiating combinations of functions | 第 3 章（同名） | 1004–1363 | 同上（Exercises3 / Solutions3(1)） |
| 4 | `Lecture/Week 4/Chapter4.md` | 4. Optimisation and Properties of Derivatives | 第 4 章（同名） | 1364–1694 | 同上（Exercises4(1) / Solutions4） |
| 5 | `Lecture/Week 5/Chapter5.md` | 5. Second Order Derivatives & Root Finding | 第 5 章（同名） | 1695–2058 | 同上（Exercises5 / Solutions5） |
| 6 | `Lecture/Week 6/Chapter6.md` | 6. Introduction to Integration | 第 6 章（同名） | 2059–2372 | 同上（Exercises6 / Solutions6） |
| 7 | `Lecture/Week 7/Chapter7.md` | 7. Integration using Newton's Laws | 第 7 章（同名） | 2373–2574 | 同上（Exercises7 / Solutions7） |
| 8 | `Lecture/Week 8/Chapter8.md` | 8. Integration by Substitution | 第 8 章（同名） | 2575–3007 | 同上（Exercises8 / Solutions8） |
| — | **无任何周版文件** | — | **第 9 章 Integration by Parts** | **3008–3085** | **整章从未被拆分到任何一周（正文 + 空壳习题）** |
| 9 | `Lecture/Week 9/Chapter9.md` | 9. **Second-Order Ordinary Differential Equations** | **第 10 章**（同名，章号错位 1） | 3086–3420 | 同上（Exercises9(1) / Solutions9，题号 9.x） |
| 10 | `Lecture/Week 10/Chapter10.md` | 10. **Vectors and Partial Differentiation** | **第 11 章**（同名，章号错位 1） | 3421–3709 | 同上（Exercises10 / Solutions10，题号 10.x） |
| 11 | 无 Chapter 文件（`Revision_Differentiation.md`） | 微分复习幻灯片 | 无直接对应章 | — | — |
| 12 | 无 Chapter 文件（`Revision_Integration.md`） | 积分复习幻灯片 | 无直接对应章 | — | — |
| — | **无任何周版文件** | — | **第 12–15 章 Additional Materials**（Crib Sheet / Constants and Physical Laws / Provided Equations in the Exam / Acknowledgments） | **3710–4291** | **整块从未被拆分到任何一周** |

### 2.4 主手册中完全没有被拆进任何一周的内容（汇总）

1. **卷首与目录**：1–122 行（3,598 词，含版权页与 Contents 表）。
2. **第 9 章 Integration by Parts**：3008–3085 行（78 行 / 454 词）。
3. **第 12–15 章 Additional Materials**：3710–4291 行（582 行 / 6,691 词）。
4. **第 1 章 Exercises**：257–497 行（241 行 / 1,826 词）——这是唯一一节既不在 `Lecture/` 也不在 `Practical/` 的习题。

---

## 三、主手册章节行号总表

文件总行数 4,291。词数按 `wc -w` 口径统计（含 md 表格与 HTML 标记）。

| 章节 | 起始行 | 结束行 | 行数 | 约词数 | 含哪些小节 |
|---|---|---|---|---|---|
| 卷首 + Contents | 1 | 122 | 122 | 3,633 | 标题页、版权声明、Contents（Differentation / Integration / Partial Differentiation / Additional Materials 四部分目录） |
| 1. Calculating Gradients | 123 | 679 | 557 | 4,868 | 1.1 Maths, Calculus and Physics / 1.2 Approximating gradients / 1.3 Working in the practical classes / **Exercises (257–497)** / **Solutions (498–679)** |
| 2. Introduction to Differentiation | 680 | 1003 | 324 | 2,950 | 2.1 Overview / 2.2 Defining differentiation / 2.3 Common differentials / 2.4 Differentiating sums of functions / **Exercises (782–911)** / **Solutions (912–1003)** |
| 3. Differentiating combinations of functions | 1004 | 1363 | 360 | 2,751 | 3.1 Overview / 3.2 Functions of functions / 3.3 Products of functions / 3.4 Quotients of functions / **Exercises (1140–1213)** / **Solutions (1214–1363)** |
| 4. Optimisation and Properties of Derivatives | 1364 | 1694 | 331 | 3,356 | 4.1 Overview / 4.2 Properties of a derivative / 4.3 Optimisation / **Exercises (1450–1564)** / **Solutions (1565–1694)** |
| 5. Second Order Derivatives & Root Finding | 1695 | 2058 | 364 | 3,841 | 5.1 Overview / 5.2 Second-order derivatives（含 Stationary values、Steady state）/ 5.3 Newton-Raphson method / **Exercises (1821–1882)** / **Solutions (1883–2058)** |
| 6. Introduction to Integration | 2059 | 2372 | 314 | 2,859 | 6.1 Overview / 6.2 Integration as the reverse of differentiation / 6.3 Solving ODEs / **Exercises (2191–2282)** / **Solutions (2283–2372)** |
| 7. Integration using Newton's Laws | 2373 | 2574 | 202 | 3,407 | 7.1 Overview / 7.2 Newtons laws of motion / 7.3 Newtons second law of motion / **Exercises (2465–2504)** / **Solutions (2505–2574)** |
| 8. Integration by Substitution | 2575 | 3007 | 433 | 2,945 | 8.1 Overview / 8.2 Integration by substitution / **Exercises (2716–2803)** / **Solutions (2804–3007)** |
| **9. Integration by Parts** | **3008** | **3085** | **78** | **454** | 9.1 Overview / 9.2 Integration by parts（Example 9.1–9.4）/ Exercises (3078–3081，**空壳**) / Solutions (3082–3085，**空壳**) |
| **10. Second-Order Ordinary Differential Equations** | **3086** | **3420** | **335** | **3,596** | 章标题在 3086–3087 行是图片文本注释（无 `#` 标题）/ 10.1 Overview / 10.2 Second-order Differential Equations / 10.3 Applied boundary value problems and steady-state / **Exercises (3219–3268)** / **Solutions (3269–3420)** |
| 11. Vectors and Partial Differentiation | 3421 | 3709 | 289 | 3,353 | 11.1 Overview / 11.2 Scalar fields / 11.3 Vectors（Vector notation、Unit vectors and magnitude、Vector arithmetic）/ 11.4 Partial Differentiation / **Exercises (3566–3619)** / **Solutions (3620–3709)** |
| 12. Crib Sheet | 3710 | 3986 | 277 | 3,037 | 12.1 Overview (3712–3715) / **12.2 Differentiation (3716–3888)**：Finding gradients、Common differentials、Chain/Product/Quotient rule、Properties & Stationary values、Second-order derivatives、Steady state、Newton-Raphson、ODEs、IVP/BVP、Partial differentiation / **12.3 Integration (3889–3986)**：Common integrals、Indefinite/Definite integration、Integration by substitution、Integrating Second-order ODEs |
| 13. Constants and Physical Laws | 3987 | 4259 | 273 | 3,180 | 13.1 Overview / 13.2 Constants, units and common formulae / 13.3 Common formulae / 13.4 Radioactive decay（α/β/γ 衰变与衰变方程）/ 13.5 Newton's laws（第二定律、动能）/ 13.6 Heat transfer and Fourier's laws / 13.7 Mass transfer and Fick's laws / 13.8 Atmospheric pressure and the hydrostatic equation |
| 14. Provided Equations in the Exam | 4260 | 4287 | 28 | 232 | 考试提供的公式：Newton's method、Chain rule、Product rule、Quotient rule、Common differentials 表、Common integrals 表 |
| 15. Acknowledgments | 4288 | 4291 | 4 | 51 | 致谢（无 `#` 标题，仅正文行 `15. Acknowledgments`） |

---

## 四、归属裁定

### 4.1 被遗漏的章节：第 9 章 Integration by Parts（3008–3085 行）

**裁定**：分配给 **Week 8**，标注为**选读 / 非考纲扩展**。

**理由**：

1. **数学序列位置**：该章 9.1 Overview 原文自述「…thus we introduced **integration by substitution** in Chapter 8. In this Chapter, we look at… **products of functions**」——它在文本上直接承接第 8 章，是积分技巧序列中紧随换元法的一环。Week 8 正是 Integration by Substitution 周。
2. **它不属于任何其他周**：Week 9 讲二阶 ODE、Week 10 讲向量与偏微分，与分部积分无关；Week 12 的积分复习幻灯片明确只复习 WEEK 6/7/8/9 四周内容，无分部积分。
3. **不能单独成周**：全章仅 454 词，且 Exercises/Solutions 在手册中就是空的，无法支撑一个独立周单元。
4. **不能丢弃**：内容本身完整可读（分部积分公式的推导 + 不定/定积分两套六步流程 + 四个例题），是主手册正文的一部分，笔记应予覆盖以保证手册完整性。
5. **Week 8 有容量**：Week 8 的 `Chapter8.md` 是十周中最短的（947 词），加上这 454 词后仍低于其他周的正文量。
6. **必须标注为非考纲**：`lecture9.md` 的 COURSE LAYOUT 官方周计划表不含此主题；全课程材料零次提及 "integration by parts"；第 14 章「考试提供公式」也不含分部积分公式。因此 Week 8 的笔记 Agent 应把它写成**附录性质的补充小节**，明确标明「本节为手册遗留章，2024-25 学年未讲授、无习题、不在考试范围」，**不得**与 Week 8 的主线内容等权重展开、不得据此推断考点。

### 4.2 附加材料（第 12–15 章，3710–4291 行）

**裁定**：按内容属性**三分**，全部落到 Week 11 与 Week 12 两个复习周：

| 分配对象 | 内容 | 行区间 | 行数/词数 |
|---|---|---|---|
| **Week 11**（Revision: Differentiation） | 第 12 章章首 + 12.1 Overview + **12.2 Differentiation** | **3710–3888** | 179 行 / 2,077 词 |
| **Week 12**（Revision: Integration） | **12.3 Integration** + 第 13 章 Constants and Physical Laws + 第 14 章 Provided Equations in the Exam + 第 15 章 Acknowledgments | **3889–4291** | 403 行 / 4,423 词 |

**理由**：

1. **Crib Sheet 天然可按微积分二分，且与两个复习周严丝合缝**。12.2 Differentiation 的小节清单是：Finding gradients、Common differentials、Chain/Product/Quotient rule、Properties of a derivative and Stationary values、Second-order derivatives、Steady state、Newton-Raphson、ODEs、IVP/BVP、Partial differentiation ——恰好覆盖 `Revision_Differentiation.md` 复习的 WEEK 1/2/3/4/5/11 全部主题（已核对该文件的 `## WEEK n` 标题序列）。12.3 Integration 的小节是：Common integrals、Indefinite/Definite integration、Integration by substitution、Integrating Second-order ODEs ——恰好覆盖 `Revision_Integration.md` 复习的 WEEK 6/7/8/9 全部主题。两侧一一吻合，因此 Crib Sheet 拆开比整块给一周更有价值：复习周 Agent 拿到的正是本周要复习的公式速查表。
2. **第 13 章归 Week 12 是内容判断，不是凑数**。13.4 放射性衰变方程、13.5 牛顿定律与动能、13.6 傅里叶导热定律、13.7 菲克扩散定律、13.8 静力学方程——这五节全部是**建立并求解 ODE 的物理背景**，正是第 6/7/10 章（即 Week 6/7/9）real-world problems 反复调用的定律来源，属积分侧应用。放到微分复习周（Week 11）与内容不符。
3. **第 14 章（考试提供公式）与第 15 章（致谢）归 Week 12**。按官方 COURSE LAYOUT，Week 12（05/05/2025）标注为「Revision: Integration **+ Exam Period**」，是考前最后一周；「考试会提供哪些公式、哪些必须背」这条信息在最后一周交付最有实用价值。第 15 章仅 51 词的致谢，随卷尾一并归入 Week 12。
4. **为什么不全给 Week 10**：Week 10 已有完整的第 11 章（289 行），且向量与偏微分和 Crib Sheet 全书性质的速查内容无对应关系；而 Week 11、Week 12 两周**本来没有任何主手册章节**，把附加材料给它们同时解决了「两个复习周手册材料为零」的问题，负载分布也更均衡。
5. **为什么不把 Crib Sheet 整块给 Week 11**：那会让 Week 12 只剩第 13/14 章，且 Week 12 复习积分时手里没有积分速查表，明显不合理。

---

## 五、逐周分配

以下 `Read` 调用可直接复制使用。`limit` 已按 `结束行 − 起始行 + 1` 算好。

> **重要说明（每周都适用）**：主手册章节的**正文段与本周 `ChapterN.md` 是同一文本**，Exercises/Solutions 段与本周 `Practical/Week N/ExercisesN*.md`、`SolutionsN*.md` 是同一文本。为避免重复读取，建议周 Agent **二选一**：
> - **方案甲（推荐）**：只读主手册的整章区间（下方给出的 Read 调用），跳过 `ChapterN.md` / `ExercisesN.md` / `SolutionsN.md` 三个重复文件，另外单独读本周的 `lectureN*.md`、transcript、`practicalN_soln*.md`。
> - **方案乙**：照常读周文件夹内全部 md，主手册只补读下方标注为「**周材料中没有**」的段落。

### Week 01
- **主手册**：`main(1).md` 第 123–679 行（第 1 章 Calculating Gradients，含 1.1–1.3 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=123, limit=557)`
- **周材料中没有的段落**：**Exercises 第 257–497 行（1,826 词）**。`Practical/Week 1` 下没有 `Exercises1.md`，取而代之的 `Chapter1(1).md` 只是 `Lecture/Week 1/Chapter1.md` 的重复件。因此**本周必须读主手册**才能拿到第 1 章习题（Introductory Exercises：Powers and indices / Logarithms and exponentials / Rearranging expressions / Trigonometry；以及 Calculating a gradient）。若只想补这一段：`Read(file_path=".../main(1).md", offset=257, limit=241)`
- **本周其他材料**：`Lecture/Week 1/` 下 `Chapter1.md`、`lecture1(4).md`、`EART11200 - 27-Jan-transcript.md`；`Practical/Week 1/` 下 `Chapter1(1).md`（重复件，可跳过）、`Solutions1(3).md`、`practical1_soln(3).md`

### Week 02
- **主手册**：`main(1).md` 第 680–1003 行（第 2 章 Introduction to Differentiation，含 2.1–2.4 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=680, limit=324)`
- **本周其他材料**：`Lecture/Week 2/` 下 `Chapter2.md`、`lecture2(4).md`、`EART11200 - 03-Feb-transcript.md`；`Practical/Week 2/` 下 `Exercises2.md`、`Solutions2.md`、`practical2_soln(5).md`

### Week 03
- **主手册**：`main(1).md` 第 1004–1363 行（第 3 章 Differentiating combinations of functions，含 3.1–3.4 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=1004, limit=360)`
- **本周其他材料**：`Lecture/Week 3/` 下 `Chapter3.md`、`lecture3(2).md`、`EART11200 - 10-Feb-transcript.md`；`Practical/Week 3/` 下 `Exercises3.md`、`Solutions3(1).md`、`practical3_soln(5).md`

### Week 04
- **主手册**：`main(1).md` 第 1364–1694 行（第 4 章 Optimisation and Properties of Derivatives，含 4.1–4.3 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=1364, limit=331)`
- **本周其他材料**：`Lecture/Week 4/` 下 `Chapter4.md`、`lecture4(1).md`、`EART11200 - 17-Feb-transcript.md`；`Practical/Week 4/` 下 `Exercises4(1).md`、`Solutions4.md`、`practical4_soln(3).md`

### Week 05
- **主手册**：`main(1).md` 第 1695–2058 行（第 5 章 Second Order Derivatives & Root Finding，含 5.1–5.3 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=1695, limit=364)`
- **本周其他材料**：`Lecture/Week 5/` 下 `Chapter5.md`、`lecture5(1).md`、`EART11200 - 24-Feb-transcript.md`；`Practical/Week 5/` 下 `Exercises5.md`、`Solutions5.md`、`practical5_soln(1).md`

### Week 06
- **主手册**：`main(1).md` 第 2059–2372 行（第 6 章 Introduction to Integration，含 6.1–6.3 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=2059, limit=314)`
- **本周其他材料**：`Lecture/Week 6/` 下 `Chapter6.md`、`lecture6.md`、`EART11200 - 03-Mar-transcript.md`（**新增，8,493 词**）；`Practical/Week 6/` 下 `Exercises6.md`、`Solutions6.md`、`practical6_soln(1).md`

### Week 07
- **主手册**：`main(1).md` 第 2373–2574 行（第 7 章 Integration using Newton's Laws，含 7.1–7.3 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=2373, limit=202)`
- **本周其他材料**：`Lecture/Week 7/` 下 `Chapter7.md`、`lecture7.md`、`EART11200 - 10-Mar-transcript.md`（**新增，7,016 词**）；`Practical/Week 7/` 下 `Exercises7.md`、`Solutions7.md`、`practical7_soln(1).md`

### Week 08
- **主手册（主线）**：`main(1).md` 第 2575–3007 行（第 8 章 Integration by Substitution，含 8.1–8.2 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=2575, limit=433)`
- **主手册（追加，见 §4.1 裁定）**：`main(1).md` 第 3008–3085 行（**第 9 章 Integration by Parts**，周材料中完全没有）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=3008, limit=78)`
- **处理要求**：第 9 章须作为**选读补充小节**收录，并明确标注「手册遗留章，2024-25 学年未讲授、无配套习题、不在考试范围（第 14 章考试提供公式中亦无分部积分）」。不得与第 8 章主线等权重展开。
- **本周其他材料**：`Lecture/Week 8/` 下 `Chapter8.md`、`lecture8.md`、`EART11200 - 17-Mar-transcript.md`；`Practical/Week 8/` 下 `Exercises8.md`、`Solutions8.md`、`practical8_soln(1).md`

### Week 09
- **主手册**：`main(1).md` 第 3086–3420 行（**主手册第 10 章** Second-Order Ordinary Differential Equations，含 10.1–10.3 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=3086, limit=335)`
- **编号提醒**：周版文件把本章编为「第 9 章」，主手册编为「第 10 章」，同一内容。手册内的题号是 Question 9.1–9.8（与周版 `Exercises9(1).md` 一致）。撰写笔记时以**周号 Week 9** 为准，如需引用手册请注明「主手册第 10 章」。第 3086–3087 行是被转成 HTML 注释的图片章标题，正文实际从 3089 行 `### 10.1 Overview` 开始。
- **本周其他材料**：`Lecture/Week 9/` 下 `Chapter9.md`、`lecture9.md`、`EART11200 - 24-Mar-transcript.md`；`Practical/Week 9/` 下 `Exercises9(1).md`、`Solutions9.md`、`practical9_soln(1).md`

### Week 10
- **主手册**：`main(1).md` 第 3421–3709 行（**主手册第 11 章** Vectors and Partial Differentiation，含 11.1–11.4 正文 + Exercises + Solutions）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=3421, limit=289)`
- **编号提醒**：周版编为「第 10 章」，主手册编为「第 11 章」，同一内容；题号 Question 10.1–10.9。
- **本周其他材料**：`Lecture/Week 10/` 下 `Chapter10.md`、`lecture10(1).md`、`EART11200 - 04-Apr-transcript.md`；`Practical/Week 10/` 下 `Exercises10.md`、`Solutions10.md`、`practical10_soln(1).md`

### Week 11（复习周：微分）
- **主手册**：`main(1).md` 第 3710–3888 行（**第 12 章 Crib Sheet 的章首 + 12.1 Overview + 12.2 Differentiation**，见 §4.2 裁定）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=3710, limit=179)`
- **本周无对应的手册正文章节**（Week 11 无 `ChapterN.md`），分到的是全书性质的微分公式速查表，与 `Revision_Differentiation.md` 复习的 WEEK 1/2/3/4/5/11 主题一一对应，适合作为复习笔记的公式索引骨架。
- **本周其他材料**：`Lecture/Week 11/` 下 `Revision_Differentiation.md`、`EART11200 - 02-May-transcript.md`；`Practical/Week 11/` 下 `2324_Exam%281%29.md`（2023-24 往年真题，与 Week 12 Practical 同名同内容）

### Week 12（复习周：积分 + 考期）
- **主手册**：`main(1).md` 第 3889–4291 行（**12.3 Integration + 第 13 章 Constants and Physical Laws + 第 14 章 Provided Equations in the Exam + 第 15 章 Acknowledgments**，见 §4.2 裁定；3889–4291 是文件末尾）
- **Read 用法**：`Read(file_path="/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics/main(1).md", offset=3889, limit=403)`
- **如需分段读取**：
  - 12.3 Integration：`offset=3889, limit=98`
  - 第 13 章 Constants and Physical Laws：`offset=3987, limit=273`
  - 第 14 章 Provided Equations in the Exam：`offset=4260, limit=28`
  - 第 15 章 Acknowledgments：`offset=4288, limit=4`
- **本周无对应的手册正文章节**（Week 12 无 `ChapterN.md`）。第 14 章「考试提供公式 vs 需自行背诵」是考前最重要的一页，笔记应予突出。
- **本周其他材料**：`Lecture/Week 12/` 下 `Revision_Integration.md`、`EART11200 - 09-May-transcript.md`；`Practical/Week 12/` 下 `2324_Exam%281%29.md`（与 Week 11 Practical 同一份文件）

### 未分配到任何周的部分
- `main(1).md` 第 1–122 行（卷首、版权页、Contents 目录表，3,633 词）：纯导航与版权信息，无学习内容，**不分配、不写入任何周笔记**。本索引第三节已把目录信息全部提炼出来，周 Agent 无需再读这一段。

---

## 六、备注（核实过程中发现的异常）

1. **主手册第 10 章标题丢失（PDF 转换缺陷）**：第 10 章标题在原 PDF 中是图片，转 md 后位于第 3086–3087 行的 `<!-- Start of picture text -->` 注释块内，因此 `grep "^#"` 看不到 `# 10.` 一级标题，容易误判「主手册缺第 10 章」。**主手册没有缺章，15 章齐全**。同样地，第 15 章 Acknowledgments（4288 行）也没有 `#` 标题。
2. **周版章号相对主手册整体错位 1（第 9 章及以后）**：周版 Week 9 = 主手册第 10 章，周版 Week 10 = 主手册第 11 章。原因是各周拆分 PDF 生成自不含 Integration by Parts 的旧版排版。
3. **主手册自身的题号与章号不自洽**：第 10 章的 Exercises/Solutions 题号是 Question 9.1–9.8，第 11 章是 10.1–10.9，均比章号小 1。说明 Integration by Parts 被插入为第 9 章时只改了章标题，题号未同步。**引用题号时以周版为准**（周版章号与题号自洽）。
4. **第 9 章 Integration by Parts 的 Exercises/Solutions 在主手册中是空壳**：3078–3085 行仅有占位文字「Algebraic problems Real-world problems」，无任何题目。同章正文中的 Example 9.1–9.4 也只有标题行、公式内容是图片未被提取。
5. **全课程零次提及 "integration by parts"**：对 `Lecture/` 与 `Practical/` 下全部 md（含 12 份逐字稿）做过 grep，零命中。`lecture9.md` 的官方 COURSE LAYOUT 周计划表也不含此主题。可确认该章未讲授、不在考纲。
6. **`Practical/Week 1` 缺 `Exercises1.md`**：Week 1 是唯一没有 Exercises 文件的周，该位置放的是 `Chapter1(1).md`（131 行 / 2,050 词，与 `Lecture/Week 1/Chapter1.md` 完全相同的重复件）。主手册第 1 章 Exercises（257–497 行，1,826 词）因此**只存在于主手册**，Week 1 的笔记 Agent 必须读主手册才能覆盖。
7. **`Revision_Differentiation.md` 内部用「WEEK 11」指代向量与偏微分**：该复习幻灯片的章节标题序列为 WEEK 1/2/3/4/5/**11**/2023-24 PAST PAPER，其中「WEEK 11」讲的是 scalar field、向量与偏微分——即本目录 `Lecture/Week 10` 的内容。这是幻灯片沿用了**大学绝对学期周号**（COURSE LAYOUT 表显示本课程占学期第 20–34 周）而非本目录的相对周号所致。**下游 Agent 应以文件夹路径中的 Week 号为准**，不要被幻灯片内的 "WEEK n" 字样误导。
8. **`Revision_Integration.md` 只复习 WEEK 6/7/8/9**：与 Integration by Parts 未讲授的结论互相印证。
9. **`main(1).md` 中公式、图表、例题正文大量是图片**，转 md 后只剩推导步骤的文字说明（如「2. Identify and assign u and differentiate to get du/dx」而无具体式子）。**周 Agent 若需要精确公式，应回到同周的 `ChapterN.md`（同样有此问题）或 `lectureN*.md`/`practicalN_soln*.md`，或参考同目录的 `main(1).pdf`**。第 12 章 Crib Sheet 与第 14 章的公式表因是 md 表格形式，反而保留得较完整。
10. **Week 11 与 Week 12 的 Practical 是同一份文件**（`2324_Exam%281%29.md`，153 行 / 1,065 词，2023-24 往年真题），两周内容实质相同，笔记时避免重复展开。
11. **Week 6、Week 7 的 transcript 已补齐**：`Lecture/Week 6/EART11200 - 03-Mar-transcript.md`（8,493 词）与 `Lecture/Week 7/EART11200 - 10-Mar-transcript.md`（7,016 词）现已存在（早前 manifest 记为「无 transcript」）。至此 Week 1–12 全部 12 周均有 transcript。
12. **主手册 `main(1).md` 位于子课程根目录，不在任何 Week 文件夹内**，因此不计入 manifest 的周词数统计（与 Statistics for Natural Scientists 的手册处理口径一致）。
