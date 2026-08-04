# 大二（Sophomore）材料目录清单 manifest

> 千年虫计划 · Agent 0b 产出。本文件只做**清点与切分建议**，不含学习顺序判断（见 Agent 0a），不含任何笔记内容。
> 统计口径：**只统计 `.md`**。字数为 `wc -w`（英文词数）。路径均相对各课程文件夹根目录。
> 扫描时间：2026-08-03。仓库根：`/home/user/y2k`，材料根：`Sophomore/`。

---

## 0. 全局口径说明

- **周单元**＝后续一个「周笔记 Agent」的取材单位。同一周的 Lecture + Practical 合并为一个周单元。
- **非教学材料**（`Past Papers/`、`Exams/`、`Assessment(s)/`、`Coursework/`）不计入周单元，单列在各课小节末尾。
- 每门课根目录下的 `(EARTxxxxx) 课程名.md` 是官方 unit spec（课程大纲、考核、学时），**不计入周单元**，但建议每个周 Agent 都先读它作为背景（各 800–1,722 词，成本很低）。
- 组织形态代码：
  - **型1** = `Lecture/` + `Practical/` 双子树，各自再分周
  - **型2** = 课程文件夹下直接 `Week N/`，周内文件平铺
  - **型3** = 无任何周子文件夹（平铺大文件）

---

## 1. 全年总览表

| 课程代码 | 课程名 | 学期 | 组织形态 | 周数 | md 文件数 | 总词数 | 预计周笔记 Agent 数 |
|---|---|---|---|---|---|---|---|
| EART22201 | Igneous Minerals and Processes（火成矿物与过程） | MT | 型1 | 10 | 35 | 129,834 | 10 |
| EART24001 | Geological Maps（地质图） | MT | 型2 | 10 | 53 | 12,680 | 10 |
| EART26001 | Energy and Resources（能源与资源） | MT | 型1 | 11 | 47 | 90,899 | 11 |
| EART26201 | Principles of Geochemistry（地球化学原理） | MT | 型1 | 10 | 49 | 158,981 | 10 |
| EART27201 | Sedimentary Rocks and Fossils（沉积岩与化石） | MT | 型1 | 11 | 26 | 52,922 | 11 |
| EART28101 | Fieldcourse: Intro to Geological Mapping（填图野外课） | MT | 型3 | **0** | **1** | 1,685 | **0（无材料，见异常 A-01）** |
| EART21202 | Global Climate Change（全球气候变化） | HT | 型2 | 10 | 31 | 124,202 | 10 |
| EART23202 | Interpreting the Stratigraphic Record（地层记录解读） | HT | 型1 | 10 | 30 | 31,842 | 10 |
| EART25102 | Advanced Geological Field Techniques（进阶野外技术） | HT | 型3 | **0（非周结构）** | 4 | 37,982 | **6（建议按野外区段切分，见 §2.9）** |
| EART28202 | Structural Geology（构造地质学） | HT | 型1 | 10 | 91 | 110,655 | 10 |
| EART29102 | Geospatial Techniques（地理空间技术） | HT | 型1 | 10 | 27 | 84,216 | 10 |
| EART29200 | Professional Development and Project Preparation（职业发展与项目准备） | 全年 | 型3 | **0（非周结构）** | 2 | 2,891 | **1** |
| — | `Course Units Sophomore.md`（学年课程总表） | — | — | — | 1 | 209 | — |
| **大二合计** | **12 门课** | — | — | **92 个周单元** | **397** | **838,998** | **99**（92 周单元 + 7 非周单元） |

**周单元合计 92** = 22201(10) + 24001(10) + 26001(11) + 26201(10) + 27201(11) + 21202(10) + 23202(10) + 28202(10) + 29102(10)。
**非周单元 7** = EART25102 建议 6 个 + EART29200 1 个。EART28101 无材料，**不派 Agent**。

---

## 2. 逐门课的周清单

### 2.1 EART22201 — Igneous Minerals and Processes（MT，型1，10 周）

Lecture 与 Practical 周次**完全对齐**（`Lecture/Week N` 与 `Practical/Week N` 编号一致，无错位）。交叉验证：Lecture transcript 日期为连续周一 06-Oct → 08-Dec（10 次，中间无跳周），Practical 编号 1–10 与之一一对应。**规范内部编号 = 文件夹编号 Week 01–10。**

| 周次 | Lecture md | Practical md | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Lecture/Week 1/W1 notes.md` (3,162)；`Lecture/Week 1/EART22201 - 06-Oct-transcript.md` (6,635) | `Practical/Week 1/Practical 1 solutions.md` (1,876) | 3 | 11,673 | ✅ 06-Oct | |
| W02 | `Lecture/Week 2/W2 notes.md` (3,991)；`Lecture/Week 2/EART22201 - 13-Oct-transcript.md` (6,296) | `Practical/Week 2/Practical 2 solutions.md` (1,881) | 3 | 12,168 | ✅ 13-Oct | |
| W03 | `Lecture/Week 3/W3 notes.md` (3,091)；`Lecture/Week 3/EART22201 - 20-Oct-transcript.md` (7,012) | `Practical/Week 3/Practical 3 solutions.md` (2,565) | 3 | 12,668 | ✅ 20-Oct | |
| W04 | `Lecture/Week 4/W4 notes.md` (2,911)；`Lecture/Week 4/EART22201 - 27-Oct-transcript.md` (6,569) | `Practical/Week 4/Practical 4 solutions stitch.md` (2,733) | 3 | 12,213 | ✅ 27-Oct | practical 文件含 OCR 补充段 |
| W05 | `Lecture/Week 5/W5 notes.md` (2,317)；`Lecture/Week 5/EART22201 - 03-Nov-transcript.md` (5,179) | `Practical/Week 5/Practical 5 solutions.md` (2,232) | 3 | 9,728 | ✅ 03-Nov | |
| W06 | `Lecture/Week 6/W6 notes.md` (2,477)；`Lecture/Week 6/EART22201 - 10-Nov-transcript.md` (6,849) | `Practical/Week 6/Practical 6 solutions.md` (3,718) | 3 | 13,044 | ✅ 10-Nov | |
| W07 | `Lecture/Week 7/W7 notes.md` (2,566)；`Lecture/Week 7/EART22201 - 17-Nov-transcript.md` (5,823) | `Practical/Week 7/Practical 7 solutions.md` (1,891) | 3 | 10,280 | ✅ 17-Nov | |
| W08 | `Lecture/Week 8/W8 notes.md` (3,321)；`Lecture/Week 8/EART22201 - 24-Nov-transcript.md` (6,557) | `Practical/Week 8/Practical 8 solutions.md` (2,423) | 3 | 12,301 | ✅ 24-Nov | |
| W09 | `Lecture/Week 9/W9 notes.md` (3,936)；`Lecture/Week 9/EART22201 - 01-Dec-transcript.md` (6,637) | `Practical/Week 9/Practical 9 solutions.md` (2,906) | 3 | 13,479 | ✅ 01-Dec | W9 notes 含 OCR 补充段 |
| W10 | `Lecture/Week 10/W10 notes.md` (2,070)；`Lecture/Week 10/EART22201 - 08-Dec-transcript.md` (6,316) | `Practical/Week 10/Practical 10 solutions.md` (2,702) | 3 | 11,088 | ✅ 08-Dec | |

**非周单元材料（不派周 Agent）**
- 课程级参考：`Practical/EART22201 Reference Guide 2025.md` (3,357) — 不在任何 Week 下，属全课通用光性矿物学速查表，**建议 10 个周 Agent 共用/按需引用**。
- 往年卷：`Lecture/Past Papers/EART22201-practice-A.md` (3,044)；`Practical/Past Papers/Dec-practical-practice1-A.md` (2,819)
- 考试反馈：`Practical/Exams/EART22201-practical-test-feedback-2025.md` (913)

---

### 2.2 EART24001 — Geological Maps（MT，型2，10 周）

无 Lecture/Practical 分列，周文件夹内平铺。本课是**纯图件实习课**：每周 1 份 handout（讲义正文）+ 若干答案图件 PDF 转出的 md。下表将 handout 类归入 Lecture 栏、solution 类归入 Practical 栏，仅为便于阅读，**物理上都在 `Week N/` 下**。周次连续 1–10，无错位、无空周。

| 周次 | Lecture md（handout/原理） | Practical md（练习与答案） | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Week 1/Handout.md` (784) | `Week 1/1-Ex1soln.md` (159)；`1-Ex2soln.md` (120)；`1-Ex3soln.md` (121) | 4 | 1,184 | ❌ | 面/线产状表示；地层等高线练习 1–3 |
| W02 | —（无 handout） | `Week 2/Q1soln.md` (123)；`Q2soln1.md` (276)；`Q2soln2.md` (157)；`Q3soln1.md` (181)；`Q3soln2.md` (90) | 5 | 827 | ❌ | 面的产状(2)、V 字法则、钻孔补图。**本周无讲义正文** |
| W03 | `Week 3/2-A_Handout_uc.md` (735) | `Week 3/Q1soln1.md` (141)；`Q1soln2.md` (57) | 3 | 933 | ❌ | 不整合 |
| W04 | `Week 4/0-HandoutFold.md` (491)；`Vshaped.md` (144) | `Week 4/EgExSoln.md` (129)；`FoldEPsoln.md` (61)；`MapSoln.md` (93)；`SectSoln.md` (139) | 6 | 1,057 | ❌ | 褶皱几何与褶皱上的地层等高线 |
| W05 | `Week 5/HandoutFault.md` (929)；`JuxtapositionEG.md` (175) | `Week 5/Q1soln-1.md` (130)；`Q2Soln.md` (239) | 4 | 1,473 | ❌ | 断层几何、断层面(并置)剖面 |
| W06 | `Week 6/1-Principles.md` (80)；`3-Strike_dip.md` (264)；`4-dip_dipdir.md` (222)；`5-plunge_plungedir.md` (230)；`6-pitch.md` (226) | `Week 6/Ex1soln1ab(1).md` (34)；`Ex1soln1bc(1).md` (41)；`Ex1soln2(1).md` (54)；`Ex1soln3(1).md` (74)；`Ex1soln4(1).md` (52)；`Ex1soln5(1).md` (73) | 11 | 1,350 | ❌ | 赤平投影入门（缺 `2-` 编号文件，原件即缺） |
| W07 | `Week 7/0-Handout.md` (596) | `Week 7/2a-Solution2025.md` (197)；`2c-SolnAll.md` (56)；`3-Comments.md` (115)；`MapSoln-1.md` (194)；`Stereogram.md` (113) | 6 | 1,271 | ❌ | 方向数据统计、古流向(Barrême) |
| W08 | `Week 8/HandoutIgneous.md` (911)；`HandSequence.md` (334) | `Week 8/Cover-1.md` (354)；`MapSoln-2.md` (83)；`SectSoln-1.md` (196)；`SeqSoln.md` (292) | 6 | 2,170 | ❌ | 侵入体几何、地质事件序列 |
| W09 | `Week 9/Cover.md` (531) | `Week 9/Soln1-1.md` (36)；`Soln2-1.md` (36)；`Soln3-1.md` (134) | 4 | 737 | ❌ | 真实图幅(Marlborough)地层等高线。三个 soln 均为纯图件，词数极低 |
| W10 | —（无 handout） | `Week 10/Q1soln1.md` (220)；`Q1soln2.md` (113)；`EPQ2soln.md` (188) | 3 | 521 | ❌ | 褶皱+断层综合题。**本课词数最低的一周** |

**非周单元材料**：无（本课无 Past Papers 文件夹）。

> ⚠️ 本课整体词数极低（12,680 词 / 10 周，均 1,268 词/周），因为原件几乎全是**手绘答案图**的 PDF。周 Agent 的产出质量高度依赖 `Handout*.md` 正文；W02、W10 无讲义正文，需要靠答案文字反推。

---

### 2.3 EART26001 — Energy and Resources（MT，型1，11 周）

Lecture 1–11，Practical 1–10，编号对齐（Lecture 文件名前缀 `01-`…`11-` 与 Practical `Practical N` 一致）。Week 11 为总结课，无 practical。**规范内部编号 = 文件夹编号 Week 01–11。**

| 周次 | Lecture md | Practical md | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Lecture/Week 1/01-Introduction to Energy and Resources.md` (1,981)；`EART26001 - 30-Sep-transcript.md` (7,434) | `Practical/Week 1/Practical 1.md` (400)；`Critical minerals discussion.md` (1,166)；`1-Exploration map solution.md` (303) | 5 | 11,284 | ✅ 30-Sep | |
| W02 | `Lecture/Week 2/02-Subsurface environment.md` (1,174)；`EART26001 - 07-Oct-transcript.md` (6,642) | `Practical/Week 2/Practical 2 instructions.md` (381)；`Practical 2 discussion.md` (600)；`2-Pressure data students.md` (67)；`2-Temperature data students.md` (137) | 6 | 9,001 | ✅ 07-Oct | 两个 data 文件为 xlsx 转出的裸数据表 |
| W03 | `Lecture/Week 3/03-Fluids and processes.md` (1,372) | `Practical/Week 3/Practical 3A-B discussion.md` (104)；`Practical 3A-magmatic-hydrothermal water solution.md` (292)；`Practical 3B-mineralization sequence.md` (205) | 4 | 1,973 | ❌ **缺** | |
| W04 | `Lecture/Week 4/04-PGE.md` (1,726) | `Practical/Week 4/Practical 4 instructions.md` (577)；`Practical 4_calculation.md` (703) | 3 | 3,006 | ❌ **缺** | |
| W05 | `Lecture/Week 5/05-Diamond deposits.md` (1,426) | `Practical/Week 5/Practical 5 instructions.md` (701) | 2 | 2,127 | ❌ **缺** | 本课最薄的一周 |
| W06 | `Lecture/Week 6/06-Gold deposits.md` (2,239)；`EART26001 - 11-Nov-transcript.md` (7,989) | `Practical/Week 6/Practical 6 instructions.md` (615)；`Practical 6 map solution.md` (247)；`6-Petrography data students.md` (1,014) | 5 | 12,104 | ✅ 11-Nov | |
| W07 | `Lecture/Week 7/07-Uranium deposits.md` (2,103)；`EART26001 - 18-Nov-transcript.md` (6,909) | `Practical/Week 7/7-Diamond game data.md` (456)；`7-Worksheet.md` (26)；`Mineral identification sheet.md` (260) | 5 | 9,754 | ✅ 18-Nov | `7-Worksheet.md` 是**空白表格**（26 词），无信息量 |
| W08 | `Lecture/Week 8/08-Petroleum.md` (2,444)；`EART26001 - 25-Nov-transcript.md` (8,006) | `Practical/Week 8/8-Practical porosity.md` (289)；`8B-Burial graph exercise.md` (224)；`porosity discussion.md` (65) | 5 | 11,028 | ✅ 25-Nov | |
| W09 | `Lecture/Week 9/09-Evaporite deposits.md` (1,765)；`EART26001 - 02-Dec-transcript.md` (6,293) | `Practical/Week 9/9-Petroleum system discussion.md` (628)；`9-Petroleum system exercise.md` (342) | 4 | 9,028 | ✅ 02-Dec | |
| W10 | `Lecture/Week 10/10-Iron and Manganese deposits.md` (2,703)；`EART26001 - 09-Dec-transcript.md` (7,696) | `Practical/Week 10/Practical 10 solutions.md` (577)；`example questions.md` (932) | 4 | 11,908 | ✅ 09-Dec | Practical 10 为复习课 |
| W11 | `Lecture/Week 11/11-Trends.md` (1,267)；`EART26001 - 16-Dec-transcript.md` (7,334) | —（**本周无 practical**） | 2 | 8,601 | ✅ 16-Dec | 总结/趋势课 |

**非周单元材料**
- `Practical/Exams/Feedback carbonate coursework.md` (166) — ⚠️ 疑似**误放**：标题为碳酸盐 coursework 反馈，与 EART23202 `Practical/Coursework/` 下同名文件同名不同内容，本课并无碳酸盐 coursework。见异常 D-03。

---

### 2.4 EART26201 — Principles of Geochemistry（MT，型1，10 周）

Lecture 1–10、Practical 1–10 编号对齐；transcript 日期连续周一 29-Sep → 08-Dec（10 次）。**规范内部编号 = 文件夹编号 Week 01–10。**

| 周次 | Lecture md | Practical md | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Lecture/Week 1/EART26201_Lecture1.md` (2,156)；`EART26201 - 29-Sep-transcript.md` (6,458) | `Practical/Week 1/EART26201_Practical1_feedback.md` (2,631)；`EART26201_Practical1_feedback-1.md` (1,192) | 4 | 12,437 | ✅ 29-Sep | 两个 feedback 分别源自 pdf 与 xlsx |
| W02 | `Lecture/Week 2/EART26201_Lecture2_RT_v2.md` (1,959)；`EART26201 - 06-Oct-transcript.md` (6,205) | `Practical/Week 2/EART26201_Practical2_feedback.md` (1,744)；`EART26201_Practical2_feedback.xlsx.md` (1,012) | 4 | 10,920 | ✅ 06-Oct | |
| W03 | `Lecture/Week 3/EART26201_Lecture3-1_RT-1.md` (1,307)；`EART26201 - 13-Oct-transcript.md` (5,214) | `Practical/Week 3/EART26201_Practical3_feedback-1.md` (1,100)；`EART26201_Practical3_feedback_diagrams-1.md` (59) | 4 | 7,680 | ✅ 13-Oct | diagrams 文件 59 词（纯图） |
| W04 | `Lecture/Week 4/EART26201_Lecture4_RT_v2.md` (2,211)；`EART26201 - 20-Oct-transcript.md` (5,456) | `Practical/Week 4/EART26201_Practical4_feedback.md` (1,882)；`EART26201_Practical4_feedback_diagrams.md` (237) | 4 | 9,786 | ✅ 20-Oct | |
| W05 | `Lecture/Week 5/EART26201_Lecture5_RT.md` (1,456)；`EART26201 - 27-Oct-transcript.md` (5,691) | `Practical/Week 5/EART26201_Practical5_feedback.md` (2,230)；**`EART26201_Practical5_feedback.xlsx.md` (30,488)** | 4 | **39,865** | ✅ 27-Oct | ⚠️ **全年最大单周**。xlsx 转出的宽表数据倾印（222 行 × 极宽列，扩散系数实验数据），建议 Agent **只读表头与前后说明，不逐行读数据** |
| W06 | `Lecture/Week 6/lecture 6 ions in solution 2025.md` (2,113)；`lecture 6 quiz answers 2024.md` (214)；`EART26201 - 10-Nov-transcript.md` (6,408) | `Practical/Week 6/EXPERIMENT 1 2025-1.md` (1,111) | 4 | 9,846 | ✅ 10-Nov | 实验课起点；quiz answers 为 2024 版且 OCR 质量低 |
| W07 | `Lecture/Week 7/Lecture 7 Solubility and complexing 2025.md` (2,013)；`lecture 7 quiz answers-1.md` (193)；`EART26201 - 17-Nov-transcript.md` (6,606) | `Practical/Week 7/exp 1 answers 2025 final.md` (685) | 4 | 9,497 | ✅ 17-Nov | |
| W08 | `Lecture/Week 8/lecture 8 buffering alkalinity and silica v2-1.md` (2,256)；`lecture 8 quiz answers 2024.md` (256)；`EART26201 - 24-Nov-transcript.md` (6,920) | **`Practical/Week 8/EART26201 lab handbook 2025-1.md` (21,717)** | 4 | **31,149** | ✅ 24-Nov | ⚠️ 该 handbook 是**全课实验手册**（安全守则+对数/单位/滴定+Experiment 2），并非第 8 周专属。见异常 D-04 |
| W09 | `Lecture/Week 9/lecture 9 redox 2025-1.md` (1,925)；`lecture 9 quiz answers 2024.md` (286)；`EART26201 - 01-Dec-transcript.md` (7,212) | `Practical/Week 9/practical 2 post lab answers 2.md` (710) | 4 | 10,133 | ✅ 01-Dec | 文件名 "practical 2" 与周次 9 不符（指 Experiment 2） |
| W10 | `Lecture/Week 10/lecture 10 stable isotopes 2025-2.md` (1,465)；`lecture 10 quiz answers 2025.md` (393)；`EART26201 - 08-Dec-transcript.md` (6,744) | `Practical/Week 10/stable isotope practical answers 2025-1.md` (346)；`final practical dec2025 answers-1.md` (355) | 5 | 9,303 | ✅ 08-Dec | |

**非周单元材料**
- 往年卷（5 份）：`Lecture/Past Papers/EART26201 Jan 2025 exam with answers.md` (1,056)；`EART26201 Jan 2024 exam with answers final DN.md` (1,260)；`EART26201 2024 exam referral and deferral with answers final DN.md` (1,262)；`EART26201 jan 2021 with answers updated (1).md` (970)；`example exam questions.md` (1,178)
- 评估反馈：`Practical/Assessments/EART26201_2025_Week5_Summative assessment feedback.md` (1,203)；`...feedback.xlsx.md` (161)

---

### 2.5 EART27201 — Sedimentary Rocks and Fossils（MT，型1，11 周）

Lecture 1–11、Practical 1–11 编号对齐。课程前半（W1–W6）为沉积学，后半（W7–W11）为古生物（换讲师，文件名风格随之改变），Practical 主题与 Lecture 逐周吻合。**规范内部编号 = 文件夹编号 Week 01–11。**

| 周次 | Lecture md | Practical md | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Lecture/Week 1/Lecture 1 2025-26 handoutr.md` (5,359) | `Practical/Week 1/EART 27201 Practical 1 handoutR.md` (1,936) | 2 | 7,295 | ❌ | 全课无 transcript |
| W02 | `Lecture/Week 2/Lecture 2 2025-26 slides.md` (2,135) | `Practical/Week 2/Stokes Law experiment 2025.md` (3,375) | 2 | 5,510 | ❌ | |
| W03 | `Lecture/Week 3/Class 3 slide handout 2025revised.md` (1,831) | `Practical/Week 3/Class 3 practical handout 2025.md` (2,293) | 2 | 4,124 | ❌ | |
| W04 | `Lecture/Week 4/Class 4 slide handout 2025revised.md` (1,035) | `Practical/Week 4/Class 3 practical handout 2025.md` (2,293) | 2 | 3,328 | ❌ | ✅ **Practical 有意沿用 W03 的 handout**（同一份实习讲义跨两周使用），用户 2026-08 确认。**不是缺失、不是误传，不得记为勘误。** |
| W05 | `Lecture/Week 5/Lecture 5 2025-26 revised.md` (3,730) | `Practical/Week 5/Practical 5 2025-26 revised.md` (855)；`Palaeocurrent exercise.md` (1,932)；`Palaeocurrent data and analysis solutions 2025-26.md` (313) | 4 | 6,830 | ❌ | solutions 文件 313 词/5,785 字符（数据表为主） |
| W06 | `Lecture/Week 6/Class 6 slides.md` (2,937)；`Bahamas case study.md` (809) | `Practical/Week 6/Practical 6 Non-clastic sedimentary rocks.md` (1,678) | 3 | 5,424 | ❌ | |
| W07 | `Lecture/Week 7/EART27201 - Sedimentary Rocks and Fossils - Slides - Introduction and Corals - compressed.md` (1,767) | `Practical/Week 7/EART27201 - Sedimentary Rocks and Fossils - Practicals - Intro and corals.md` (3,310) | 2 | 5,077 | ❌ | 古生物段起点 |
| W08 | `Lecture/Week 8/EART27201 - Sedimentary Rocks and Fossils - Slides - Brachiopods and Molluscs - compressed.md` (1,791) | `Practical/Week 8/EART27201 - Sedimentary Rocks and Fossils - Practicals - Brachiopods and Molluscs.md` (1,892) | 2 | 3,683 | ❌ | |
| W09 | `Lecture/Week 9/EART27201 - Sedimentary Rocks and Fossils - Slides - Trilobites and Echinoderms - Compressed.md` (1,645) | `Practical/Week 9/EART27201 - Sedimentary Rocks and Fossils - Practical - Trilobites and Echinoderms - compressed-1.md` (2,112) | 2 | 3,757 | ❌ | |
| W10 | `Lecture/Week 10/EART27201 - Graptolites and conclusion - Slides - compressed-1.md` (1,062) | `Practical/Week 10/EART27201 - Sedimentary Rocks and Fossils - Practical - Graptolites and conclusion.md` (2,098) | 2 | 3,160 | ❌ | |
| W11 | `Lecture/Week 11/EART27201 - Sedimentary Rocks and Fossils - Slides - Microfossils - Compressed.md` (1,129) | `Practical/Week 11/EART27201 - Sedimentary Rocks and Fossils - Practical - Microfossils - compressed.md` (2,337) | 2 | 3,466 | ❌ | |

**非周单元材料**：无。

---

### 2.6 EART28101 — Fieldcourse: Introduction to Geological Mapping（MT，型3，0 周）

**全课只有 1 个 md，即官方 unit spec `(EART28101) Fieldcourse: Introduction to Geological Mapping.md` (1,685 词)。文件夹内没有任何教学材料，也没有任何 pdf/pptx/docx 原件。**

| 周次 | Lecture md | Practical md | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| — | — | — | 0 | 0 | ❌ | **整门课无教学材料，不派任何周 Agent** |

**判断与建议**：这是 10 天法国 SE 住宿野外课（100% 野外报告考核，0 课堂学时）。材料很可能从未上传到课程平台，或在收集环节整体遗漏。**建议向用户确认是否有遗漏的原始材料**；若确无，则本门课在大二笔记库中**留空或仅按 unit spec 写一份 1 页说明**，不占用周 Agent。

---

### 2.7 EART21202 — Global Climate Change（HT，型2，10 周）

无 Lecture/Practical 分列，周文件夹内平铺（讲义 deck + workshop 答案 deck + transcript）。下表把讲义/transcript 归 Lecture 栏、`*Answers*` 归 Practical 栏。

**⚠️ 周次错位（已交叉验证并给出对应关系）**：文件名里的 "Week N" 与文件夹 "Week N" **不一致**，因为课程官方周号包含了一个**期中测验周（无讲课）**。用 transcript 日期 + 幻灯片首页标题双重验证后，对应关系确定如下：

| 文件夹（规范内部编号） | transcript 日期 | 幻灯片首页自称 | 主题 | 文件名里的 "Week N" |
|---|---|---|---|---|
| **W01** | 05-Feb | Week 1 | 气候变化导论与影响 | Week 1 ✅一致 |
| **W02** | 12-Feb | Week 2 | 自然气候变率 | 无周号 |
| **W03** | 19-Feb | **Week 3** | 辐射与温室效应 | 文件名写 "Week 4" ❌**文件名错，正文为准** |
| **W04** | 26-Feb | Week 4 | 人为气候影响 | Week 4 ✅一致 |
| **W05** | 05-Mar | Week 5 | 气候变化的证据基础 | Week 5 ✅一致 |
| （课程 Week 6） | 12-Mar | — | **期中测验周，无讲课、无材料** | — |
| **W06** | 19-Mar | Week 7 | 气候模拟 | Week 7（=课程周号，+1） |
| **W07** | 26-Mar | Week 8 | 气候变化影响与适应 | Week 8（+1） |
| **W08** | 23-Apr | Week 9 | 气候变化减缓 | Week 9（+1） |
| **W09** | 30-Apr | Week 10 | 气候工程 | Week 10（+1） |
| **W10** | 07-May | Week 11 | 复习 | Week 11（+1） |

> **规范内部编号采用文件夹编号 Week 01–10（连续、无空周）**。周 Agent 提到"本周是课程第几周"时应按上表的"课程周号"列注明（W06→课程 Week 7，依此类推），避免与讲义标题打架。19-Mar transcript 开头一句 "welcome to the second half… This is the first time I've seen you since the mid-semester test" 是这条错位的直接证据。

| 周次 | Lecture md（讲义 + transcript） | Practical md（workshop 答案） | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Week 1/GGC_Week 1_2026_Student.md` (3,811)；`Week 1/EART21202 - 05-Feb-transcript.md` (8,713) | — | 2 | 12,524 | ✅ 05-Feb | 讲义含 OCR 低质量段 |
| W02 | `Week 2/Natural Climate_Student_2026_Upload_QuestionsOnly.md` (4,111)；`Week 2/EART21202 - 12-Feb-transcript.md` (6,269) | `Week 2/Natural Climate_Student_2026_Upload_AnswersOnly.md` (1,905) | 3 | 12,285 | ✅ 12-Feb | |
| W03 | `Week 3/Week 4_Student Upload_2026.md` (2,882)；`Week 3/EART21202 - 19-Feb-transcript.md` (5,913) | `Week 3/Week 4_Student Answers_2026.md` (1,400) | 3 | 10,195 | ✅ 19-Feb | 文件名写 Week 4，实为 Week 3；本周原定客座讲座因讲者请假改由本人代讲 |
| W04 | `Week 4/Week 4_Anthropogenic_Impacts_on_Climate-2.md` (3,542)；`Week 4/EART21202 - 26-Feb-transcript.md` (7,269) | `Week 4/Week 4_Student Answers_2026-2.md` (650) | 3 | 11,461 | ✅ 26-Feb | 讲者 Dr Simon O'Meara |
| W05 | `Week 5/Week 5 Development_Student-1.md` (3,796)；`Week 5/EART21202 - 05-Mar-transcript.md` (8,064) | `Week 5/Week 5 Development_Student_Answers.md` (2,734) | 3 | 14,594 | ✅ 05-Mar | |
| W06 | `Week 6/Week 7 2026_Student.md` (3,675)；`Week 6/EART21202 - 19-Mar-transcript.md` (7,035) | `Week 6/Week 7 2026_Answers.md` (1,881) | 3 | 12,591 | ✅ 19-Mar | =课程 Week 7；跳过 12-Mar 测验周 |
| W07 | `Week 7/Week 8 Development 2026_Student Upload.md` (4,674)；`Week 7/EART21202 - 26-Mar-transcript.md` (7,543) | `Week 7/Week 8 Answers.md` (829) | 3 | 13,046 | ✅ 26-Mar | =课程 Week 8；复活节前最后一课 |
| W08 | `Week 8/Week 9 Student_2026.md` (4,022)；`Week 8/EART21202 - 23-Apr-transcript.md` (6,723) | `Week 8/Week 9 Answers 2026.md` (1,496) | 3 | 12,241 | ✅ 23-Apr | =课程 Week 9；复活节后 |
| W09 | `Week 9/GCC_Week 10_Development_2026_Student.md` (3,472)；`Week 9/EART21202 - 30-Apr-transcript.md` (7,114) | `Week 9/GCC_Week 10_Answers.md` (554) | 3 | 11,140 | ✅ 30-Apr | =课程 Week 10 |
| W10 | `Week 10/Week 11_Revision__GCC_2026_Student-1.md` (5,039)；`Week 10/EART21202 - 07-May-transcript.md` (7,446) | — | 2 | 12,485 | ✅ 07-May | =课程 Week 11，复习课 |

**非周单元材料**
- 往年卷：`Past Papers/EART21202 Final Exam Paper.md` (441)；`Past Papers/EART21202_exam_2023.md` (399)

---

### 2.8 EART23202 — Interpreting the Stratigraphic Record（HT，型1，10 周）

Lecture 1–10；**Practical 只有 1–6**。已交叉验证主题：Practical W1 相关(Correlation)↔Lecture W1(地层方法)、W2 岩心相分析↔W2 相分析、W3 台地练习↔W3 碳酸盐台地、W4–W6 相练习↔W4–W6 碳酸盐相/动力学，**逐周吻合，不存在编号错位**。碎屑岩后半段（W7–W10）本就无实习课。**规范内部编号 = 文件夹编号 Week 01–10。**

| 周次 | Lecture md | Practical md | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Lecture/Week 1/01-Stratigraphic methods.md` (1,398) | `Practical/Week 1/Correlation solution(1).md` (671) | 2 | 2,069 | ❌ | 全课无 transcript |
| W02 | `Lecture/Week 2/L2 Facies analysis.md` (1,577) | `Practical/Week 2/Facies core exercise.md` (1,389) | 2 | 2,966 | ❌ | Lecture 含 OCR 低质量段 |
| W03 | `Lecture/Week 3/03-Carbonate platforms.md` (1,513) | `Practical/Week 3/3-Platforms exercise.md` (289)；`Exercise 1a.md` (268)；`Petrography guide.md` (1,299) | 4 | 3,369 | ❌ | |
| W04 | `Lecture/Week 4/04-Facies peritidal-subtidal-shoal .md` (1,459) | `Practical/Week 4/Intro facies exercises.md` (403)；`Exercise 1 discussion.md` (612)；`Exercise 2 discussion.md` (275)；`Exercise 3 discussion.md` (817) | 5 | 3,566 | ❌ | Lecture 文件名末尾有多余空格，Read 时注意 |
| W05 | `Lecture/Week 5/05-Facies reef-basin.md` (1,933) | `Practical/Week 5/Exercise 4 discussion.md` (358)；`Exercise 5 discussion.md` (202)；`facies map exercise discussion.md` (238) | 4 | 2,731 | ❌ | 缺 Exercise 6（原件即缺） |
| W06 | `Lecture/Week 6/06-Carbonate dynamics.md` (1,812) | `Practical/Week 6/Exercise 7.md` (151)；`Exercise 8.md` (109)；`Exercise 9.md` (71) | 4 | 2,143 | ❌ | 三份练习词数均 <160 |
| W07 | `Lecture/Week 7/Shallow Marine Clastic Environments(1).md` (2,835) | —（**无 practical**） | 1 | 2,835 | ❌ | 碎屑岩段起点 |
| W08 | `Lecture/Week 8/Continental Environments Lecture.md` (2,511) | —（**无 practical**） | 1 | 2,511 | ❌ | 含 OCR 低质量段 |
| W09 | `Lecture/Week 9/Deep-water Sedimentary Systems Process to product.md` (2,768) | —（**无 practical**） | 1 | 2,768 | ❌ | 含 OCR 低质量段 |
| W10 | `Lecture/Week 10/Aeolian_Systems (1).md` (4,825) | —（**无 practical**） | 1 | 4,825 | ❌ | |

**非周单元材料**
- 往年卷：`Lecture/Past Papers/23202 Exam 2025 Q.md` (242)；`Lecture/Past Papers/EART23202 Exam Questions.md` (222)
- 评估：`Practical/Assessment/Practical assessment 2026.md` (174)；`Practical/Coursework/Feedback carbonate coursework.md` (166)

---

### 2.9 EART25102 — Advanced Geological Field Techniques（HT，型3，非周结构）

**结构实况**（4 个 md，全部平铺在课程根目录，无任何子文件夹）：

| 文件 | 词数 | 行数 | 性质 |
|---|---|---|---|
| `(EART25102) Advanced Geological Field Techniques.md` | 1,722 | — | 官方 unit spec |
| `Handbook_2026.md` | 24,305 | 1,816 | **Fort William 段（4/7–4/14）野外手册全本** |
| `Fife Field Guide 2026.md` | 10,762 | 1,224 | **Fife & Angus 段（4/15–4/19）野外指南全本** |
| `Scotland_Info2026-2.md` | 1,193 | — | 行程/住宿/交通须知 |

**判断：它不是按周组织的，也不能按周切。** 这是一门 2 周住宿野外课（苏格兰，2026-04-07 至 04-20），教学单位是**野外日 / 露头点（locality）**，不是教学周。两本大手册本身就是**整书**，物理拆分会破坏交叉引用（目录、附录样品清单、安全守则被多处引用）。

**建议：做指针式索引，不物理拆分。** 以下是按章节边界（`grep -n '^#'` 实测行号）给出的 6 个切分单元建议，**本 Agent 不动手切分，交由后续专派 Agent 执行**：

| 建议单元 | 取材（Read 参数） | 约词数 | 主题 |
|---|---|---|---|
| U1 课程总览 · 行程 · 安全 | `Handbook_2026.md` offset=1 limit=193；`Scotland_Info2026-2.md` 全文；unit spec 全文 | ~5,000 | 课程介绍、考核方式、行程、健康安全、格网与磁北 |
| U2 Fort William 区域地质背景 | `Handbook_2026.md` offset=194 limit=223（至 L416） | ~3,000 | Highland 地质背景 |
| U3 Loch Leven + Kentallen | `Handbook_2026.md` offset=417 limit=368（L417–784） | ~5,000 | 两个野外区段的点位信息 |
| U4 Glen Coe + 野外与填图技能 | `Handbook_2026.md` offset=785 limit=613（L785–1397） | ~7,000 | Glen Coe；火成岩/变沉积岩野外描述、野外记录本、野外图、剖面构制 |
| U5 Fife 后勤 · 目标 · 地质背景 | `Fife Field Guide 2026.md` offset=1 limit=365（至 L365） | ~3,500 | Fife/Angus 段行程、潮汐、考核、地质背景 |
| U6 Fife 六个露头点 + 描述资源 | `Fife Field Guide 2026.md` offset=366 limit=570（L366–935） | ~6,000 | Crawton / Arbroath / St Andrews / Pittenweem ×2 / St Monans；沉积岩与火成岩野外描述 |

> 附录段（`Handbook_2026.md` L1398–1710，样品清单与人物小传）与两份文件末尾的 "OCR 补充" 段（Handbook L1711–1816、Fife L936–1224）**信息密度低、OCR 质量差**，建议并入 U4/U6 时只做扫读，不做精读。
> 另注：`Fife Field Guide` 的 St Monans 露头点与 EART28202 Practical Week 8 的 `Map_2024.md` / `Section_2024.md` / `Stereogram_2024.md` 是**同一个野外区域**，后处理阶段可做交叉链接。

---

### 2.10 EART28202 — Structural Geology（HT，型1，10 周）

Lecture 1–10（`Class1`…`Class10`，每份 7,363–10,292 词，是全大二最厚的讲义），Practical 1–10。

**⚠️ 主题错配排查结论（重要，但结论是"不要重编号"）**：交叉比对每周 Lecture 与 Practical 的实际标题后发现——

| 周 | Lecture 主题 | Practical 主题 | 是否吻合 |
|---|---|---|---|
| W01 | 褶皱几何 | 褶皱几何 + Two-dyke 练习 | ✅ |
| W02 | 褶皱形成 | Tarskavaig Bay 图幅（褶皱） | ✅ |
| W03 | 应变 | 应变分析练习 | ✅ |
| W04 | 剪切带 | **断层几何 + 侵入体几何** | ❌ |
| W05 | 应力 | 2D Mohr 圆 | ✅ |
| W06 | 破裂 | 脆性破坏 Mohr 圆 + Anderson 分类 | ✅ |
| W07 | 断层 | **剪切带图幅练习** | ❌ |
| W08 | 逆冲/收缩构造 | 下倾投影剖面（St Monans） | ❌ |
| W09 | 伸展构造 | 剪切带练习 | ❌ |
| W10 | 走滑构造 | 褶皱+断层综合练习 | ❌ |

W01/02/03/05/06 完全吻合，说明**不存在整体位移型错位**（若整体错位则应无一周吻合）。W04↔W07 看似互换（剪切带↔断层），但 W08–W10 无法用任何固定偏移解释。合理解释是：**本课 Practical 是一条独立的"图幅/赤平投影技能训练"序列，与 Lecture 主题并非逐周绑定**（与 EART24001 同一套教学传统，文件命名风格完全一致）。

> **规范内部编号 = 文件夹编号 Week 01–10。不要重编号、不要重新配对。** 周 Agent 只需知道：本课某些周的 practical 主题会"跑到"另一周的 lecture 主题上，属正常，不必强行圆场。

| 周次 | Lecture md | Practical md（文件多，按词数降序列出） | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Lecture/Week 1/Class1_FoldGeometry.md` (7,363) | `1-FoldGeometry(1).md` (491)；`Ex2.md` (391)；`Ex3-EHRsoln1.md` (191)；`DemoExSoln.md` (185)；`Ex1c-SolnSeq(1).md` (177)；`Ex4soln.md` (164)；`Ex3-EHRsoln2.md` (120)；`DemoEx(1).md` (114)；`Ex1-2dyke.md` (110)；`3-MinorStruct(1).md` (109)；`Ex2soln.md` (99)；`Ex1a-SolnFold(1).md` (98)；`2-Bisector.md` (87)；`Ex1b-SolnMap(1).md` (67) | 15 | 9,766 | ❌ | 全课无 transcript |
| W02 | `Lecture/Week 2/Class2_FoldFormation.md` (7,540) | `Cover.md` (592)；`SolnMap.md` (291)；`Ex5-1.md` (117)；`SolnGneissFault.md` (114)；`Ex5soln.md` (85)；`SolnFold.md` (84) | 7 | 8,823 | ❌ | Tarskavaig Bay 图幅 |
| W03 | `Lecture/Week 3/Class3_Strain.md` (9,155) | `2-CoverAns.md` (2,545)；`Logs.md` (340)；`Fig1soln.md` (77)；`4-Ex3sol2.md` (29) | 5 | 12,146 | ❌ | `4-Ex3sol2.md` 已标注"OCR 识别质量低、文字大多不可靠" |
| W04 | `Lecture/Week 4/Class4_ShearZones.md` (8,935) | `1-FaultGeometry.md` (929)；`IgneousBodies.md` (911)；`DescribingIntrusions.md` (241)；`5-GenericAssess.md` (189)；`Ex2seq.md` (168)；`Ex1seq.md` (167)；`2-Method_1offset(1).md` (159)；`3-Method_2offsets(1).md` (156)；`Ex3soln.md` (127)；`Ex4SolnSeq.md` (107)；`Ex4SolnMap.md` (90)；`Ex1.md` (77)；`Ex4SolnFault.md` (77)；`Ex2(4).md` (75)；`Ex1F1soln.md` (72)；`Ex2F2soln.md` (70)；`Ex1F2soln.md` (68)；`Ex2F1soln.md` (66) | 19 | 12,684 | ❌ | 本课文件最多的一周；主题与 Lecture 不符（见上表） |
| W05 | `Lecture/Week 5/Class5_Stress.md` (9,785) | `Ex3soln(1).md` (790)；`Ex1(6).md` (553)；`Handout(2).md` (453)；`Ex2soln(1).md` (332)；`Ex4soln(1).md` (274)；`Ex1bSoln(1).md` (212)；`Ex1dSoln(1).md` (153)；`Ex1cSoln(1).md` (141) | 9 | 12,693 | ❌ | |
| W06 | `Lecture/Week 6/Class6_Fractures.md` (10,292) | `Ex1soln(15).md` (1,492)；`Anderson.md` (173) | 3 | 11,957 | ❌ | 全大二最厚的单份讲义 |
| W07 | `Lecture/Week 7/Class7_Faults.md` (8,612) | `Cover(1).md` (606)；`MapSoln.md` (418)；`FaultPlane.md` (237)；`FoldOut.md` (115)；`FoldIn.md` (100)；`SZattitude.md` (100) | 7 | 10,188 | ❌ | Lecture 含 OCR 补充段 |
| W08 | `Lecture/Week 8/Class8_Contractional.md` (8,550) | `NewHandout.md` (1,050)；`Map_2024.md` (245)；`Section_2024.md` (216)；`Soln2(1).md` (182)；`Soln3(1).md` (147)；`Stereogram_2024.md` (94)；`Soln1(1).md` (79)；`Ex3soln.md` (70)；`Ex1soln.md` (40)；`Ex2soln.md` (36) | 11 | 10,709 | ❌ | St Monans（与 EART25102 Fife 段同一露头） |
| W09 | `Lecture/Week 9/Class9_Extensional.md` (9,780) | `Ex2soln(4).md` (342)；`Ex4soln(2).md` (239)；`Ex5soln1.md` (229)；`Ex1soln(1).md` (188)；`Ex3soln(2).md` (185)；`0-Handout.md` (108)；`Ex5soln2.md` (88) | 8 | 11,159 | ❌ | |
| W10 | `Lecture/Week 10/Class10_StrikeSlip.md` (8,304) | `SolnSum.md` (264)；`SolnFld(1).md` (95)；`Qflt1sol.md` (71)；`SolnMap(2).md` (71)；`Qflt2sol.md` (68) | 6 | 8,873 | ❌ | |

**非周单元材料**：无。

> 本课 Practical 共 81 个 md，其中 **50 个 <200 词**、19 个 <100 词——全部是手绘答案图的图注抽取。周 Agent 应把讲义（`ClassN_*.md`）当主干，practical 文件当练习索引，**不要为凑字数逐个精读几十词的答案图**。

---

### 2.11 EART29102 — Geospatial Techniques（HT，型1，10 周）

Lecture 1–10、Practical 1–9（W10 为复习课，无 practical）。Lecture N 与 Practical N 主题逐周吻合（GIS 导论↔ArcGIS Pro 入门、空间分析↔空间分析、遥感↔遥感、3D↔3D）。

**⚠️ 授课日期倒置（不改编号，但要标注）**：transcript 日期显示 `Week 9`（23-Mar，3D geospatial）**实际早于** `Week 8`（21-Apr，Spatial Visualisation）——因为 3D 那节排在复活节假前的第 8 个教学档期，而 Spatial Visualisation 挪到了假后。课程自身的材料编号（`Lecture 8 Spatial Visualisation`、`Practical 8`）与文件夹一致，内容逻辑也成立。
**结论：规范内部编号仍取文件夹编号 Week 01–10**；W08/W09 的周 Agent 需知道 transcript 日期与周号不同步，**不要据日期改写周序**。

| 周次 | Lecture md | Practical md | 该周 md 数 | 该周词数 | transcript | 备注 |
|---|---|---|---|---|---|---|
| W01 | `Lecture/Week 1/Lecture 1 Introduction to GIS.md` (2,074) | `Practical/Week 1/Practical 1 - Introduction to ArcGISPro.md` (2,318) | 2 | 4,392 | ❌ **缺** | |
| W02 | `Lecture/Week 2/Lecture 2 - Spatial Data and Data Management.md` (946) | `Practical/Week 2/Practical 2 - Carlisle_Flood_Map.md` (1,796) | 2 | 2,742 | ❌ **缺** | Lecture 仅 946 词且含 OCR 低质量段，是本课最薄讲义 |
| W03 | `Lecture/Week 3/Lecture_3_Spatial data input and manipulation_handout.md` (1,552) | `Practical/Week 3/Practical 3 - Spatial Data Input and Manipulation.md` (2,113) | 2 | 3,665 | ❌ **缺** | |
| W04 | `Lecture/Week 4/Lecture 4 - Spatial Analysis.md` (1,804)；`EART29102 - 23-Feb-transcript.md` (6,374) | `Practical/Week 4/Practical 4 - Spatial analysis.md` (3,458) | 3 | 11,636 | ✅ 23-Feb | transcript 从本周才开始 |
| W05 | `Lecture/Week 5/Lecture 5 - Spatial statistics.md` (1,103)；`EART29102 - 02-Mar-transcript.md` (5,850) | `Practical/Week 5/Practical 5 - Spatial statistics.md` (2,167) | 3 | 9,120 | ✅ 02-Mar | |
| W06 | `Lecture/Week 6/Geospatial Techniques - Lecture 6 - Remote Sensing - 2026.md` (2,026)；`EART29102 - 09-Mar-transcript.md` (8,340) | `Practical/Week 6/Practical 6 -Remote Sensing.md` (2,878) | 3 | 13,244 | ✅ 09-Mar | 本课最大周 |
| W07 | `Lecture/Week 7/Lecture 7 - Terrain Analysis.md` (1,249)；`EART29102 - 16-Mar-transcript.md` (6,563) | `Practical/Week 7/Practical 7 - Wind turbines.md` (2,623) | 3 | 10,435 | ✅ 16-Mar | |
| W08 | `Lecture/Week 8/Lecture 8 Spatial Visualisation.md` (1,354)；`EART29102 - 21-Apr-transcript.md` (5,353) | `Practical/Week 8/Practical 8 - Solar radiation mapping and map layout.md` (2,658) | 3 | 9,365 | ✅ **21-Apr（假后）** | 实际授课晚于 W09，见上文 |
| W09 | `Lecture/Week 9/Lecture - 3D geospatial techniques.md` (1,923)；`EART29102 - 23-Mar-transcript.md` (5,242) | `Practical/Week 9/Practical - 3D geospatial techniques.md` (3,179) | 3 | 10,344 | ✅ **23-Mar（假前）** | 实际授课早于 W08 |
| W10 | `Lecture/Week 10/Lecture 10 Course review_handout.md` (1,827)；`EART29102 - 27-Apr-transcript.md` (6,506) | —（**无 practical**） | 2 | 8,333 | ✅ 27-Apr | 复习课 |

**非周单元材料**：无。

---

### 2.12 EART29200 — Professional Development and Project Preparation（全年，型3，非周结构）

**结构实况**（2 个 md，平铺在 `Sophomore/EART29200/`）：

| 文件 | 词数 | 性质 |
|---|---|---|
| `(EART29200) Professional Development and Project Preparation.md` | 981 | 官方 unit spec（全年 10 学分，22 小时 tutorial，100% 报告考核） |
| `SubsidenceAgeProject2025_withNeilMitchell.md` | 1,910 | Neil Mitchell 组的 tutorial 项目任务书（地球热流与洋壳年龄-水深关系，GeoMapApp 数据分析 + 科学报告写作） |

**判断：不是按周组织，也不该按周切。** 这是全年 tutorial 制课程，学生只跟一个导师做一个项目；仓库里只保留了该学生所在组的**一份项目任务书**。

**建议：派 1 个 Agent 做 1 份笔记**，覆盖 unit spec（考核要求、报告结构规范）+ 项目任务书（模型 vs 数据的方法论、热传导/岩石圈冷却/沉降 e^(-t) 线性化、GeoMapApp 操作）。**不需要切分，不需要建索引**（共 2,891 词）。

---

## 3. 异常与风险清单

> 共 **26 条**。按类别编号：A=缺材料 / B=周次与编号 / C=transcript / D=文件错放与重复 / E=转换质量 / F=需切分或建索引 / G=非教学材料。

### A. 空周、缺周、整门缺材料

| 编号 | 课程 | 描述 | 影响 / 建议 |
|---|---|---|---|
| **A-01** | **EART28101** | **整门课零教学材料**，仅有官方 unit spec（1,685 词），课程文件夹下既无 md 也无任何 pdf/pptx/docx 原件 | 🔴 最严重。**不派周 Agent**。建议向用户确认是否漏收；若确无，仅按 unit spec 出 1 页说明或整门留空 |
| **A-02** | EART21202 | 课程 Week 6（12-Mar）为期中测验周，**无讲课材料**；文件夹从 W05 直接跳到 W06（=课程 Week 7） | 正常缺周，不派 Agent。文件夹编号仍连续 1–10 |
| **A-03** | EART23202 | Practical 只到 Week 6，**W07–W10 无 practical**（碎屑岩后半段无实习课） | 这 4 周只有 lecture，单周词数 2,511–4,825，属正常薄周 |
| **A-04** | EART26001 | **Week 11 无 practical**（总结课） | 正常 |
| **A-05** | EART29102 | **Week 10 无 practical**（复习课） | 正常 |
| **A-06** | EART24001 | **Week 2、Week 10 无 handout 讲义正文**，整周只有答案图件（827 / 521 词） | 周 Agent 需靠答案文字反推知识点，产出质量风险高 |
| **A-07** | EART23202 | Practical Week 5 缺 `Exercise 6`（W05 有 Ex4、Ex5、facies map；W06 直接从 Ex7 起） | 原件即缺，非转换遗漏 |
| **A-08** | EART24001 | Week 6 缺 `2-` 编号文件（有 `1-Principles`、`3-Strike_dip`…） | 原件即缺 |

**空周（文件夹存在但无任何 md）：0 个。** 全部 158 个 Week 文件夹均至少有 1 个 md。

### B. 周次错位与编号问题

| 编号 | 课程 | 描述 | 规范内部编号裁定 |
|---|---|---|---|
| **B-01** | **EART21202** | 文件名里的 "Week N" 与文件夹周号从 W06 起整体 **+1**（课程官方周号含 12-Mar 期中测验周）；另外**文件夹 Week 3 的两个文件被命名为 "Week 4_..."，但幻灯片首页自称 "Week 3 - Radiation and the Greenhouse Effect"** | ✅ **采用文件夹编号 Week 01–10**（连续）。对应表见 §2.7。证据：10 份 transcript 日期链 05-Feb→07-May + 19-Mar transcript 明言"自期中测验后第一次见面" |
| **B-02** | **EART29102** | **W08 与 W09 的实际授课日期倒置**：W09 transcript 为 23-Mar（复活节前），W08 transcript 为 21-Apr（复活节后） | ✅ **采用文件夹/课程官方编号 Week 01–10**，不按日期重排。W08/W09 的 Agent 需在笔记里说明日期与周号不同步 |
| **B-03** | **EART28202** | Lecture 与 Practical 主题在 W04、W07、W08、W09、W10 不对应（W01/02/03/05/06 完全吻合，故**不是整体位移型错位**） | ✅ **不重编号、不重新配对**。Practical 是独立的图幅/赤平投影技能序列。详见 §2.10 |
| **B-04** | EART26201 | Practical 文件名与周号不一致：W06 `EXPERIMENT 1`、W07 `exp 1 answers`、W09 `practical 2 post lab answers`（指 Experiment 1/2 而非第 N 周） | 无需处理，只是实验编号 ≠ 周号 |

### C. 缺 transcript

| 编号 | 课程 | 缺 transcript 的周 | 覆盖率 |
|---|---|---|---|
| **C-01** | **EART23202** | **全部 10 周** | 0/10 |
| **C-02** | **EART24001** | **全部 10 周** | 0/10 |
| **C-03** | **EART27201** | **全部 11 周** | 0/11 |
| **C-04** | **EART28202** | **全部 10 周** | 0/10 |
| **C-05** | EART26001 | Week 3、4、5 | 8/11 |
| **C-06** | EART29102 | Week 1、2、3 | 7/10 |
| — | EART21202 / EART22201 / EART26201 | 无缺失 | 10/10 各 |
| — | EART25102 / EART28101 / EART29200 | 非课堂课，本无 transcript | n/a |

> 全大二 92 个周单元中，**有 transcript 的 45 个（21202×10 + 22201×10 + 26201×10 + 26001×8 + 29102×7），无 transcript 的 47 个**。无 transcript 的周只能靠幻灯片/讲义，笔记的"课堂展开"部分会明显更薄——这是可预期的、不是失败。

### D. 文件错放、重复、疑似上传错误

| 编号 | 课程 | 描述 |
|---|---|---|
| ~~D-01~~ | EART27201 | ~~W04 practical 误传了 W03 的件~~ **→ 已由用户 2026-08 澄清：第四周实习有意沿用第三周的 handout（同一份讲义跨两周使用）。非缺失、非误传，不得记为勘误。** |
| **D-02** | **EART26201** | `Practical/Week 8/EART26201 lab handbook 2025-1.md`（21,717 词）是**全课实验手册**（实验室安全守则、事故上报、单位/对数/滴定通用技能、Experiment 2 缓冲液与指示剂），并非第 8 周专属材料，却只放在 Week 8 下 |
| **D-03** | **EART26001** | `Practical/Exams/Feedback carbonate coursework.md`（166 词）标题为"碳酸盐 coursework 反馈"，而本课（能源与资源）无碳酸盐 coursework；EART23202 `Practical/Coursework/` 下有同名文件（内容不同）。**疑似跨课误放** |
| **D-04** | EART22201 | `Practical/EART22201 Reference Guide 2025.md`（3,357 词）不在任何 Week 下，是全课通用光性矿物学速查表 | 
| **D-05** | EART26001 | `Practical/Week 7/7-Worksheet.md`（26 词）是**完全空白的填表模板**，无任何信息 |
| **D-06** | EART23202 | `Lecture/Week 4/04-Facies peritidal-subtidal-shoal .md` **文件名末尾带一个多余空格**，Read 时必须原样保留，否则找不到文件 |

**全库 md 内容级重复：0 组**（397 个 md 的 md5 全部互异；D-01 因 front-matter 不同才未被 hash 命中，属实质重复）。

### E. 转换质量问题（词数异常小 / OCR 降质 / 正文被吞）

| 编号 | 范围 | 描述 |
|---|---|---|
| **E-01** | 全库 | **19 个 md 带 `识别质量低` 标记**（原件为手写或纯图件，OCR 文字大多不可靠）：EART21202 W1/W2/W5/W7/W10 讲义各 1；EART23202 Lecture W2/W8/W9、Practical W4 各 1；EART28202 `Practical/Week 3/4-Ex3sol2.md`；EART29102 Lecture W2/W7/W8；EART26001 Practical W1/W8；EART26201 Lecture W6/W7(quiz)/W8/W9 quiz answers；EART27201 `Practical/Week 5/Practical 5 2025-26 revised.md` |
| **E-02** | 全库 | 另有 **41 个 md 带 `OCR 补充` 段**（原件部分页无文字层，用 OCR 补齐），质量介于中等 |
| **E-03** | **EART28202** | Practical 81 个 md 中 **50 个 <200 词、19 个 <100 词**；最小 `Practical/Week 3/4-Ex3sol2.md` 仅 29 词且已标 OCR 低质。这些是手绘答案图的图注残片，**不是转换损坏，而是原件本就没有可提取文字** |
| **E-04** | **EART24001** | 整门 12,680 词 / 53 个 md（均 239 词/文件），同上——原件几乎全是手绘图。最小 4 个文件 34–41 词 |
| **E-05** | **EART26201** | `Practical/Week 5/EART26201_Practical5_feedback.xlsx.md` — 30,488 词但仅 222 行，是 xlsx 转出的**超宽数值表倾印**（Mg-Fe 互扩散实验数据）。信息密度极低但 token 消耗巨大 |
| **E-06** | EART26001 | `Practical/Week 2/2-Pressure data students.md` (67)、`2-Temperature data students.md` (137)、`Practical/Week 6/6-Petrography data students.md` (1,014) 均为 xlsx 裸数据表，无文字说明 |
| **E-07** | EART27201 | `Practical/Week 5/Palaeocurrent data and analysis solutions 2025-26.md` — 313 词 / 5,785 字符，几乎全是古流向方位角数据 |

**图片占位符检查**：全库 **0 个** markdown 图片语法（`![...]`）——转换器把图像内容以 `<!-- Start of picture text -->…<!-- End of picture text -->` 的文字抽取形式内联，未产生"满屏图片占位符"型损坏。

### F. 需切分 / 建索引的课程（型3）

| 编号 | 课程 | 判断 | 处理建议 |
|---|---|---|---|
| **F-01** | **EART25102** | **整书型**：`Handbook_2026.md` 24,305 词 / 1,816 行 + `Fife Field Guide 2026.md` 10,762 词 / 1,224 行 | **指针式索引，不物理拆分**。§2.9 已按实测章节行号给出 6 个单元的 `Read(offset, limit)` 参数草案。切分由后续专派 Agent 执行 |
| **F-02** | **EART29200** | **非周、非书**：仅 unit spec + 1 份项目任务书，共 2,891 词 | **不切分**，派 1 个 Agent 出 1 份笔记 |
| **F-03** | **EART28101** | **无材料** | 无从切分。见 A-01 |
| **F-04** | EART26201 W08 | 单周含 21,717 词的全课实验手册（D-02） | 建议把该 handbook 提为**课程级材料**，W08 Agent 只读其中 `EXPERIMENT 2`（L1004–1278）与通用技能段（L665–1003），安全守则段（L65–664）交由课程笔记阶段一次性处理 |
| **F-05** | EART26201 W05 | 单周 39,865 词，其中 30,488 词是数值表（E-05） | 建议 W05 Agent **只读表头与前后文字说明**，不逐行读数据 |

**需要切分/建索引的课：2 门**（EART25102 建索引、EART26201 建议对两个超大单文件做段内定位）。若只按"型3 且必须先切分才能派 Agent"计，则为 **1 门（EART25102）**。

### G. 非教学材料（单独归类，不计入周单元）

| 课程 | 位置 | 文件数 | 词数 |
|---|---|---|---|
| EART21202 | `Past Papers/` | 2 | 840 |
| EART22201 | `Lecture/Past Papers/`、`Practical/Past Papers/`、`Practical/Exams/` | 3 | 6,776 |
| EART22201 | `Practical/`（根，课程级参考） | 1 | 3,357 |
| EART23202 | `Lecture/Past Papers/`、`Practical/Assessment/`、`Practical/Coursework/` | 4 | 804 |
| EART26001 | `Practical/Exams/` | 1 | 166 |
| EART26201 | `Lecture/Past Papers/`、`Practical/Assessments/` | 7 | 7,090 |
| **合计** | | **18** | **19,033** |

> 往年卷建议在**课程笔记阶段**（而非周笔记阶段）统一使用，用于校验知识点覆盖度。

---

## 4. 体量预估

**换算基准**（大一经验）：**每 1 万词材料 ≈ 15–20 万 token**（含读材料 + 生成笔记）。

| 课程 | 总词数 | Agent 数 | 预估 token（低） | 预估 token（高） |
|---|---|---|---|---|
| EART26201 | 158,981 | 10 | 238 万 | 318 万 |
| EART22201 | 129,834 | 10 | 195 万 | 260 万 |
| EART21202 | 124,202 | 10 | 186 万 | 248 万 |
| EART28202 | 110,655 | 10 | 166 万 | 221 万 |
| EART26001 | 90,899 | 11 | 136 万 | 182 万 |
| EART29102 | 84,216 | 10 | 126 万 | 168 万 |
| EART27201 | 52,922 | 11 | 79 万 | 106 万 |
| EART25102 | 37,982 | 6 | 57 万 | 76 万 |
| EART23202 | 31,842 | 10 | 48 万 | 64 万 |
| EART24001 | 12,680 | 10 | 19 万 | 25 万 |
| EART29200 | 2,891 | 1 | 4.3 万 | 5.8 万 |
| EART28101 | 1,685 | 0 | ~0 | ~0 |
| 学年总表 md | 209 | — | — | — |
| **大二全年合计** | **838,998** | **99** | **约 1,259 万** | **约 1,678 万** |

**分学期**
- MT（EART22201 + 24001 + 26001 + 26201 + 27201 + 28101）：447,001 词 / 52 个 Agent → **约 671 万–894 万 token**
- HT（EART21202 + 23202 + 25102 + 28202 + 29102）：388,897 词 / 46 个 Agent → **约 583 万–778 万 token**
- 全年（EART29200）：2,891 词 / 1 个 Agent → **约 4.3 万–5.8 万 token**

**单周体量分布（92 个周单元）**
- 最大周：EART26201 W05（39,865 词，≈60–80 万 token）、EART26201 W08（31,149 词，≈47–62 万 token）
- 中位周：约 9,700 词（≈15–19 万 token）
- 最小周：EART24001 W10（521 词）、EART24001 W09（737 词）、EART24001 W02（827 词）
- **提示**：EART26201 W05/W08 两周应在派 Agent 时**单独提示"跳读数据表/只读指定章节"**（见 F-04、F-05），否则单周 token 可能超出常规上限的 3–4 倍。

---

## 5. 给后续周笔记 Agent 的取用约定（摘要）

1. **规范内部编号一律采用文件夹的 `Week N`**，全部 9 门周结构课都从 Week 01 起、连续无空缺。三处需要额外说明的：EART21202（讲义标题周号从 W06 起 +1）、EART29102（W08/W09 授课日期倒置）、EART28202（practical 主题不逐周对应 lecture）。
2. **一个周 Agent 读一个周单元 = 该周 `Lecture/Week N/` + `Practical/Week N/` 下的全部 md**（型2 课程为 `Week N/` 下全部 md），外加该课根目录的 `(EARTxxxxx) 课程名.md` 作为背景。
3. **transcript 全文精读**（PLAN.md §0.2），slides/handout 同等地位。无 transcript 的 47 个周单元不必因此判为失败。
4. **不读 pdf/pptx/docx/xlsx 原件**。本次核查确认：**所有 384 个非 md 原件都有配对的 md，无一遗漏**（逐个比对 `<basename>.md` / `<filename>.md` 两种命名，零缺口）。
5. Past Papers / Exams / Assessment / Coursework 下的 18 个 md **不属于任何周单元**，留给课程笔记阶段。
