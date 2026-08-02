# Statistics for Natural Scientists — 手册分配索引

> 由手册切分索引 Agent 生成。供逐周笔记 Agent 精确定位本周应读的手册章节。
> **不切分原文件**：周 Agent 用 Read 工具的 offset/limit 参数只读自己那一段，源材料保持原样。

## 周号口径

本门课统一采用子课程内部周号 **Week 01～Week 06**（用户裁定）。与物理目录的对应关系：

| 周单元 | Lecture 文件夹 | Practical 文件夹 |
|---|---|---|
| Week 01 | `Lecture/Week 6` | `Practical/Week 1` |
| Week 02 | `Lecture/Week 7` | `Practical/Week 2` |
| Week 03 | `Lecture/Week 8` | `Practical/Week 3` |
| Week 04 | `Lecture/Week 9` | `Practical/Week 4` |
| Week 05 | `Lecture/Week 10` | `Practical/Week 5` |
| Week 06 | `Lecture/Week 11` | `Practical/Week 6` |

配对原则：Practical Week i ↔ Lecture Week (i+5)，按位置一一对应。完整证据链见 `/home/user/y2k/Freshman/manifest.md` 的「特别裁定：Statistics for Natural Scientists 的周号配对」一节。

子课程根目录（下文所有相对路径均以此为基准）：
`/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists`

## 手册章节行号总表

行号已由本 Agent 逐处 Read 核定（起始行 = 该章标题所在行；结束行 = 下一章标题的前一行；末段到文件末尾）。

| 章节 | 文件 | 起始行 | 结束行 | 行数 | 约词数 |
|---|---|---|---|---|---|
| 卷首（YAML frontmatter、标题页、版本、Table of Contents） | SFNS Handbook (Gilman) V2.2.md | 1 | 68 | 68 | 375 |
| Chapter 1: Introduction | SFNS Handbook (Gilman) V2.2.md | 69 | 251 | 183 | 4,969 |
| Chapter 2. Comparing the means of two groups | SFNS Handbook (Gilman) V2.2.md | 252 | 680 | 429 | 8,826 |
| Chapter 3. Comparing the means of more than two groups | SFNS Handbook (Gilman) V2.2.md | 681 | 990 | 310 | 5,549 |
| Chapter 4. Understanding the effects of numerical predictors | SFNS Handbook (Gilman) V2.2.md | 991 | 1451 | 461 | 9,864 |
| Chapter 5. Categorical responses to categorical predictors | SFNS Handbook (Gilman) V2.2.md | 1452 | 1765 | 314 | 5,095 |
| Chapter 6. Categorical responses to numerical predictors | SFNS Handbook (Gilman) V2.2.md | 1766 | 2077 | 312 | 5,992 |
| Appendix 1: Choosing a statistical test | SFNS Handbook (Gilman) V2.2.md | 2078 | 2091 | 14 | 98 |
| Appendix 2: Installing and navigating R | SFNS Handbook (Gilman) V2.2.md | 2092 | 2277 | 186 | 4,154 |
| Index | SFNS Handbook (Gilman) V2.2.md | 2278 | 2298 | 21 | 962 |
| **合计** | SFNS Handbook (Gilman) V2.2.md | 1 | 2298 | 2,298 | 35,884 |
| Chapter 7. Dealing with non-independent data points | Chapter 7.md | 1 | 242 | 242 | 7,214 |

说明：`Chapter 7.md` 的第 1–5 行是转换工具生成的 YAML frontmatter，第 7 行才是章标题；由于本章整篇归 Week 06，索引仍按整文件 1–242 给出。`SFNS Handbook (Gilman) V2.2.md` 的第 1–5 行同样是 YAML frontmatter，已并入「卷首」。

`Chapter 7.md` 的二级标题（供周 Agent 预览结构）：
- 第 11 行 Why do we need mixed effects models: a motivating example
- 第 78 行 Introducing mixed effects models
- 第 102 行 Fitting mixed effects models in R
- 第 138 行 More complex random effects structures
- 第 182 行 Random slopes
- 第 196 行 Two common warnings
- 第 216 行 Fitting random effects models – a second attempt
- 第 236 行 Choosing the random effects structure

## 逐周分配

### Week 01

- **手册**：`SFNS Handbook (Gilman) V2.2.md` 第 1–680 行（680 行，约 14,170 词）
  - 卷首（YAML frontmatter、标题页、Version 2.2、Table of Contents）：第 1–68 行
  - Chapter 1: Introduction：第 69–251 行
  - Chapter 2. Comparing the means of two groups：第 252–680 行
- **Read 用法**：
  `Read(file_path="/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/SFNS Handbook (Gilman) V2.2.md", offset=1, limit=680)`
- **本周其他材料**：`Lecture/Week 6`、`Practical/Week 1` 文件夹下的全部 md
  - Lecture：`EART11200 - 08-Nov-transcript.md`、`Statistics for Natural Scientists L1P1(1).md`、`Statistics for Natural Scientists L1P2.md`
  - Practical：`Practical 2(2).md`、`Practical 2 answer key(1).md`

### Week 02

- **手册**：`SFNS Handbook (Gilman) V2.2.md` 第 681–990 行（310 行，约 5,549 词）
  - Chapter 3. Comparing the means of more than two groups：第 681–990 行
- **Read 用法**：
  `Read(file_path="/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/SFNS Handbook (Gilman) V2.2.md", offset=681, limit=310)`
- **本周其他材料**：`Lecture/Week 7`、`Practical/Week 2` 文件夹下的全部 md
  - Lecture：`EART11200 - 15-Nov-transcript.md`、`Statistics for Natural Scientists L2P1.md`、`Statistics for Natural Scientists L2P2.md`、`Statisitcs for Natural Scientists L2P3.md`（文件名 Statisitcs 为原始拼写错误）
  - Practical：`Practical 3(2).md`、`Practical 3 answer key(1).md`

### Week 03

- **手册**：`SFNS Handbook (Gilman) V2.2.md` 第 991–1451 行（461 行，约 9,864 词）
  - Chapter 4. Understanding the effects of numerical predictors：第 991–1451 行
- **Read 用法**：
  `Read(file_path="/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/SFNS Handbook (Gilman) V2.2.md", offset=991, limit=461)`
- **本周其他材料**：`Lecture/Week 8`、`Practical/Week 3` 文件夹下的全部 md
  - Lecture：`EART11200 - 22-Nov-transcript.md`、`Statistics for Natural Scientists L4P1(1).md`、`Statistics for Natural Scientists L4P2(1).md`
  - Practical：`Practical 4(2).md`、`Practical 4 answer key(2).md`

### Week 04

- **手册**：`SFNS Handbook (Gilman) V2.2.md` 第 1452–1765 行（314 行，约 5,095 词）
  - Chapter 5. Categorical responses to categorical predictors：第 1452–1765 行
- **Read 用法**：
  `Read(file_path="/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/SFNS Handbook (Gilman) V2.2.md", offset=1452, limit=314)`
- **本周其他材料**：`Lecture/Week 9`、`Practical/Week 4` 文件夹下的全部 md
  - Lecture：`EART11200 - 29-Nov-transcript.md`、`Statistics for Natural Scientists L4P1(2).md`、`Statistics for Natural Scientists L4P2(2).md`
  - Practical：`Practical 5(1).md`、`Practical 5 answer key(1).md`

### Week 05

- **手册**：`SFNS Handbook (Gilman) V2.2.md` 第 1766–2298 行（533 行，约 11,206 词；即第 6 章及其后的全部内容，直到文件末尾）
  - Chapter 6. Categorical responses to numerical predictors：第 1766–2077 行
  - Appendix 1: Choosing a statistical test：第 2078–2091 行
  - Appendix 2: Installing and navigating R：第 2092–2277 行
  - Index：第 2278–2298 行
- **Read 用法**：
  `Read(file_path="/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/SFNS Handbook (Gilman) V2.2.md", offset=1766, limit=533)`
- **本周其他材料**：`Lecture/Week 10`、`Practical/Week 5` 文件夹下的全部 md
  - Lecture：`EART11200 - 06-Dec-transcript.md`、`Statistics for Natural Scientists L5P1.md`、`Statistics for Natural Scientists L5P2.md`
  - Practical：`Practical 6(1).md`、`Practical 6 answer sheet(1).md`
- 备注：Appendix 2（R 的安装与 RStudio 界面导览）与 Index 属于全书性参考材料，被规则归入本周，写笔记时可只做提要，不必与第 6 章同等展开。

### Week 06

- **手册**：`Chapter 7.md` 整个文件，第 1–242 行（242 行，约 7,214 词）
  - Chapter 7. Dealing with non-independent data points：第 7–242 行（第 1–5 行为 YAML frontmatter）
- **Read 用法**：
  `Read(file_path="/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists/Chapter 7.md", offset=1, limit=242)`
- **本周其他材料**：`Lecture/Week 11`、`Practical/Week 6` 文件夹下的全部 md
  - Lecture：`EART11200 - 13-Dec-transcript.md`（本周无幻灯片，仅 transcript）
  - Practical：`Practical 7.md`、`Practical 7 answer key.md`

## 备注

1. **行号已逐处实地核定**，与主控 grep 提供的参考值完全一致：Ch1=69、Ch2=252、Ch3=681、Ch4=991、Ch5=1452、Ch6=1766、Appendix 1=2078、Appendix 2=2092、Index=2278，文件总行数 2298（末行无空行结尾问题）。无差异。
2. **分配规则与 Practical 编号高度自洽**（意外的佐证）：Practical 文件夹内的文件自带编号为 Practical 2～Practical 7，恰好与各周分配到的手册章号一一吻合——Week 01→Ch2/Practical 2、Week 02→Ch3/Practical 3、……、Week 06→Ch7/Practical 7。这独立支持了「Practical Week i ↔ Lecture Week (i+5)」的位置配对裁定，也说明用户给出的手册分配规则与课程实际教学进度一致。
3. **Chapter 7 不在 V2.2 正文与目录中**：`SFNS Handbook (Gilman) V2.2.md` 全文检索不到「Chapter 7」字样，其 Table of Contents 只列到 Appendix 2 与 Index。`Chapter 7.md` 是独立增补材料（单独的 pdf 转 md），并非从 V2.2 中拆出。因此 Week 06 的手册材料只有这一个文件，不需要回到主手册取任何内容。
4. **pdf 转 md 的页码残留**：正文中夹杂着孤立成行的阿拉伯数字（如第 67 行「1」、第 250 行「12」、第 679 行「32」、第 985 行「46」、第 1450 行「70」、第 1764 行「84」、第 2076 行「99」、第 2090 行「100」等），是原 pdf 的页脚页码。这些数字行位于每章结束处、下一章标题之前，已按「结束行 = 下一章标题前一行」的规则归入上一章。周 Agent 读到时忽略即可。
5. **目录页码与 md 行号不构成线性关系**（正常现象）：TOC 标注 Ch1=p.2、Ch2=p.13、Ch3=p.33、Ch4=p.47、Ch5=p.71、Ch6=p.85、Appendix 1=p.100、Appendix 2=p.101、Index=p.110，与 md 行号的对应关系经抽查一致（各章前的页脚页码数字恰好等于该章起始页减 1），未发现章节缺失或错位。
6. **Appendix 1 极短**（14 行、98 词），只有一张「如何选择统计检验」的对照表 Table A1.1，但信息密度高，适合直接整表引用。
7. **Index 段（2278–2298）中夹有页码行「110」「111」「112」**，且原 pdf 的多栏索引在转换后被压成极长的连续段落，可读性差。它是术语-页码对照，对写笔记基本无用，Week 05 的 Agent 可跳过。
8. **原始 pdf 仍在同目录保留**（`SFNS Handbook (Gilman) V2.2.pdf`、`Chapter 7.pdf`），md 为其转换产物。若某处 md 表格/公式明显损坏，可回查 pdf 对应页。
9. 讲义文件名编号存在跳号（无 L3）与重复（L4 出现两次，分属 Week 03 与 Week 04），这是材料制作方的内部编号瑕疵，与周单元划分无关，已在 manifest 中记录。
