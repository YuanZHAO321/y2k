# 大一执行 Manifest

> 由目录统计 Agent（0b）生成。供逐周笔记 Agent 定位材料、供主控预估 token 消耗。
> 词数统计口径：各周单元文件夹内全部 `.md` 的 `wc -w` 词数之和（英文材料，不含已生成的 `Notes/`）。
> 本 Agent 未读取任何课程材料正文，仅通过 `find`/`wc -w` 做目录与词数统计。

## 汇总总表

| # | 子课程 | 学期 | 周单元数 | md 文件数 | 总词数 | 备注 |
|---|---|---|---|---|---|---|
| 1 | How to Build a Planet | MT | 10 | 20 | 124,411 | Week 1–10，无缺周 |
| 2 | How to Grow a Planet | MT | 11 | 23 | 179,172 | Week 1–11，无缺周 |
| 3 | The Workshops | MT | 7 | 7 | 6,154 | 缺 Week 6、8、9 |
| 4 | Chemistry of the Earth | MT | 11 | 33 | 118,612 | Lecture+Practical 配对，Week 1–11，无缺周 |
| 5 | Introductory Maths for Natural Scientists | MT | 5 | 29 | 29,138 | Lecture+Practical 配对，Week 1–5，无缺周 |
| 6 | Statistics for Natural Scientists | MT | 6 | 29 | 93,042 | 周单元统一命名为 **Week 01–06**（用户裁定，内部周号）；Lecture(Week6–11)+Practical(Week1–6) 按位置配对，详见下方特别裁定。另有课程手册 2 份置于子课程根目录（不在周文件夹内，未计入本行词数），逐周应读章节见 `Handbook Index.md` |
| 7 | Practical Skills（MT） | MT | 10 | 25 | 50,120 | 缺 Week 3 |
| 8 | A Dynamic Planet | HT | 11 | 23 | 140,760 | Week 1–11，无缺周 |
| 9 | A Sustainable Planet | HT | 10 | 20 | 135,724 | Week 1–10，无缺周 |
| 10 | Computer Programming | HT | 9 | 27 | 119,726 | Lecture+Practical 配对，Week 1–9，无缺周 |
| 11 | Mathematics and Physics（HT） | HT | 12 | 64 | 140,625 | Lecture+Practical 配对，Week 1–12，无缺周 |
| 12 | Practical Skills（HT） | HT | 10 | 39 | 46,614 | Week 1–10 无缺周；但周内分 Morning/Afternoon（Week8 另有 Museum Quiz）子文件夹 |
| 13 | 2025 Field Trip Material | HT | 非周（1个材料集） | 1 | 613 | 非周结构，单一活动文件夹 |
| — | **大一合计** | | **112 个周单元 + 1 个非周材料集** | **340** | **1,184,711** | |

## 各子课程明细

### 1. How to Build a Planet（MT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11100/Michaelmas Term/How to Build a Planet`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：单文件夹周（slides 与 transcript 混放同一 Week 文件夹）
- 缺周：无
- 异常说明：材料文件名内部编号与文件夹 Week 号不完全对应（例如 Week 6 文件夹内的幻灯片文件名为 `Archean+Week+7+lecture+slides.md`，Week 8 内为 `Week+9++Lecture+handout.md`，Week 9 内为 `Week+10+2020+weathering.md`）——**以文件夹 Week 号为准**，文件名内部数字仅供参考，不代表真实周次。

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../How to Build a Planet/Week 1` | Class+1_Before+the+Earth+Lecture+Slides+Handout.md, EART11100 - 23-Sep-transcript.md | 12,878 |
| Week 2 | `.../Week 2` | Class+2+The+formation+of+stars+and+galaxies+lecture+slides+2024.md, EART11100 - 30-Sep-transcript.md | 12,460 |
| Week 3 | `.../Week 3` | EART11100 - 07-Oct-transcript.md, Week+3+Overview+of+the+Earth+System+handout.md | 10,250 |
| Week 4 | `.../Week 4` | EART11100 - 14-Oct-transcript.md, Week+4+Minerals+%26+Rocks+lecture+slides+lecture_handout.md | 14,141 |
| Week 5 | `.../Week 5` | EART11100 - 21-Oct-transcript.md, Week+5+The+Rock+Cycle+handout.md | 11,240 |
| Week 6 | `.../Week 6` | Archean+Week+7+lecture+slides.md, EART11100 - 04-Nov-transcript.md | 12,967 |
| Week 7 | `.../Week 7` | Class+7+Slides+The+Proterozoic+Earth+2024.md, EART11100 - 11-Nov-transcript.md | 12,605 |
| Week 8 | `.../Week 8` | EART11100 - 18-Nov-transcript.md, Week+9++Lecture+handout.md | 14,010 |
| Week 9 | `.../Week 9` | EART11100 - 25-Nov-transcript.md, Week+10+2020+weathering.md | 11,775 |
| Week 10 | `.../Week 10` | Cenozoic+lecture+2023%281%29.md, EART11100 - 02-Dec-transcript.md | 12,085 |
| **小计** | | | **124,411** |

### 2. How to Grow a Planet（MT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11100/Michaelmas Term/How to Grow a Planet`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：单文件夹周
- 缺周：无
- 异常说明：内部幻灯片编号（Part N）与文件夹 Week 号错位且有重复，例如 Week 4 文件夹内文件名为 `Week+2+2024.md`；Week 9 内含 `Part+9+Palaeogene%281%29.md` 及一个 `Untitled+presentation.md`；Week 10 内同时含 `Part 10 Human Origins 2024.md` 与 `Part+9+slides+-+monocots%281%29.md`；Week 11 内又出现 `Part+10+-+Fields+of+Joy.md`（与 Week 10 的 "Part 10" 重名但内容文件不同）。**以文件夹 Week 号为准**。

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../How to Grow a Planet/Week 1` | EART11100 - 24-Sep-transcript.md, HTGAP+Week+1+2024+DDC.md | 10,194 |
| Week 2 | `.../Week 2` | EART11100 - 01-Oct-transcript.md, Part+4+Ocean+Life.md | 20,580 |
| Week 3 | `.../Week 3` | EART11100 - 08-Oct-transcript.md, L4+Ocean+Life+slides.md | 22,557 |
| Week 4 | `.../Week 4` | EART11100 - 15-Oct-transcript.md, Week+2+2024.md | 15,292 |
| Week 5 | `.../Week 5` | EART11100 - 22-Oct-transcript.md, Week+5+-+Sex+Machine+-+online+version.md | 15,533 |
| Week 6 | `.../Week 6` | EART11100 - 05-Nov-transcript.md, Part+6+-+Reach+for+the+Sky.md | 17,398 |
| Week 7 | `.../Week 7` | EART11100 - 12-Nov-transcript.md, Part+7+Dinosaurs%21.md | 22,903 |
| Week 8 | `.../Week 8` | EART11100 - 19-Nov-transcript.md, Part+8+-+Wildflower.md | 15,654 |
| Week 9 | `.../Week 9` | EART11100 - 26-Nov-transcript.md, Part+9+Palaeogene%281%29.md, Untitled+presentation.md | 18,582 |
| Week 10 | `.../Week 10` | EART11100 - 03-Dec-transcript.md, Part 10 Human Origins 2024.md, Part+9+slides+-+monocots%281%29.md | 20,089 |
| Week 11 | `.../Week 11` | Part+10+-+Fields+of+Joy.md（无 transcript） | 390 |
| **小计** | | | **179,172** |

### 3. The Workshops（MT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11100/Michaelmas Term/The Workshops`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：单文件夹周
- 缺周：Week 6、8、9（实地核查确认，目录中仅存在 Week 1、2、3、4、5、7、10 共 7 个文件夹）
- 异常说明：均无 transcript 文件，仅有 workshop 幻灯片；Week 10 是本课程最后一个出现的周文件夹（Week 11 不存在）。

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../The Workshops/Week 1` | Workshop+1+class+slides.md | 476 |
| Week 2 | `.../Week 2` | Week+2+Geological+Time+_+workshop+slides.md | 513 |
| Week 3 | `.../Week 3` | Week+3+Geological+Time+2024-25.md | 1,053 |
| Week 4 | `.../Week 4` | Workshop+4+But+which+way+is+up2023bb.md | 361 |
| Week 5 | `.../Week 5` | Week+5+Earthquake+workshop+slides.md | 679 |
| Week 7 | `.../Week 7` | EART11100+-+Evolution+Workshop+-+2024+-+compressed.md | 1,328 |
| Week 10 | `.../Week 10` | Workshop+10+2023.md | 1,744 |
| **小计** | | | **6,154** |

### 4. Chemistry of the Earth（MT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11200/Michaelmas Term/Chemistry of the Earth`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：Lecture+Practical 配对（各 11 周，Week 号一一对应，内容主题吻合，配对清晰无歧义）
- 缺周：无
- 异常说明：无

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../Lecture/Week 1`（Lecture）<br>`.../Practical/Week 1`（Practical） | EART11200 - 25-Sep-transcript.md, EART11200 Lecture 1 - What is Earth made of.md ｜ ChemEarth Practical 1 - Chemistry of the Whole Earth - Feedback(1).md | 9,323 + 1,826 = 11,149 |
| Week 2 | `.../Lecture/Week 2`<br>`.../Practical/Week 2` | ChemEarth L2 - Geochemist's Periodic Table.md, EART11200 - 02-Oct-transcript.md ｜ ChemEarth Practical 2 - A Geochemistry view of the Periodic Table - Feedback.md | 8,759 + 2,099 = 10,858 |
| Week 3 | `.../Lecture/Week 3`<br>`.../Practical/Week 3` | ChemEarth L3 - Earth's Layers and element partitioning.md, EART11200 - 09-Oct-transcript.md ｜ Practical 3 2022 - Element partitioning - feedback.md | 8,756 + 2,124 = 10,880 |
| Week 4 | `.../Lecture/Week 4`<br>`.../Practical/Week 4` | ChemEarth L4 - Carbon Cycle & Organics.md, EART11200 - 16-Oct-transcript.md ｜ ChemEarth Practical 4 - Organic Chemistry - Feedback.md | 8,152 + 2,450 = 10,602 |
| Week 5 | `.../Lecture/Week 5`<br>`.../Practical/Week 5` | ChemEarth L5 - Reactions and oxidation state.md, EART11200 - 23-Oct-transcript.md ｜ ChemEarth Practical 5 - Feedback.md | 9,385 + 2,172 = 11,557 |
| Week 6 | `.../Lecture/Week 6`<br>`.../Practical/Week 6` | ChemEarth L6 - Chemical equilibrium.md, EART11200 - 06-Nov-transcript.md ｜ ChemEarth Practical 6 - Chemical Equilibrium - Feedback.md | 10,247 + 2,102 = 12,349 |
| Week 7 | `.../Lecture/Week 7`<br>`.../Practical/Week 7` | ChemEarth L7 - Melting and REE.md, EART11200 - 13-Nov-transcript.md ｜ ChemEarth Practical 7 - Melting and REE - feedback.md | 10,112 + 1,804 = 11,916 |
| Week 8 | `.../Lecture/Week 8`<br>`.../Practical/Week 8` | ChemEarth L8 - Stable isotopes.md, EART11200 - 20-Nov-transcript.md ｜ ChemEarth Practical 8 - Stable Isotopes - feedback(2).md | 9,148 + 1,646 = 10,794 |
| Week 9 | `.../Lecture/Week 9`<br>`.../Practical/Week 9` | ChemEarth L9 - Water.md, EART11200 - 27-Nov-transcript.md ｜ ChemEarth Practical 9 - Water - Feedback.md | 9,557 + 1,815 = 11,372 |
| Week 10 | `.../Lecture/Week 10`<br>`.../Practical/Week 10` | ChemEarth L10 - Radioactive isotopes and Geochronology.md, EART11200 - 04-Dec-transcript.md ｜ ChemEarth Practical 10 - Geochronology - feedback.md | 9,805 + 1,170 = 10,975 |
| Week 11 | `.../Lecture/Week 11`<br>`.../Practical/Week 11` | ChemEarth Overview.md, EART11200 - 11-Dec-transcript.md ｜ ChemEarth+Review+Quiz.md | 5,724 + 436 = 6,160 |
| **小计** | | | **118,612** |

### 5. Introductory Maths for Natural Scientists（MT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Introductory Maths for Natural Scientists`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：Lecture+Practical 配对（各 5 周，Week 号一一对应；Lecture 与 Practical 两侧的 transcript 文件日期完全一致，如 Week1 双方均为 27-Sep-transcript，Week2 均为 04-Oct-transcript，确认配对无误）
- 缺周：无（该子课程本身只设 5 周）
- 异常说明：无

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../Lecture/Week 1`（Lecture）<br>`.../Practical/Week 1`（Practical） | EART11200 - 27-Sep-transcript.md, EART11200_M&P_W1_1/2/3.md ｜ EART11200 - 27-Sep-transcript.md | 1,594 + 27 = 1,621 |
| Week 2 | `.../Lecture/Week 2`<br>`.../Practical/Week 2` | EART11200 - 04-Oct-transcript.md, EART11200_M&P_W2_1/2/3.md ｜ EART11200 - 04-Oct-transcript.md, eart11200_week02_answers.md | 1,443 + 1,387 = 2,830 |
| Week 3 | `.../Lecture/Week 3`<br>`.../Practical/Week 3` | EART11200 - 11-Oct-transcript.md, EART11200_M&P_W3_1/2/3.md ｜ EART11200 - 11-Oct-transcript.md, eart11200_week03_answers.md | 6,815 + 2,175 = 8,990 |
| Week 4 | `.../Lecture/Week 4`<br>`.../Practical/Week 4` | EART11200 - 18-Oct-transcript.md, EART11200_M&P_W4_1/2/3.md ｜ EART11200 - 18-Oct-transcript.md, eart11200_week04_answers(1).md | 6,810 + 2,590 = 9,400 |
| Week 5 | `.../Lecture/Week 5`<br>`.../Practical/Week 5` | EART11200 - 25-Oct-transcript.md, EART11200_M&P_W5_1/2/3.md ｜ EART11200 - 25-Oct-transcript.md, eart11200_week05_answers.md | 4,552 + 1,745 = 6,297 |
| **小计** | | | **29,138** |

### 6. Statistics for Natural Scientists（MT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11200/Michaelmas Term/Mathematics and Physics/Statistics for Natural Scientists`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：Lecture+Practical 配对，**但两侧文件夹的 Week 号编号体系不一致，已裁定配对方案（见下方"特别裁定"章节）**
- **周号口径（用户裁定）**：本门课周单元统一命名为 **Week 01～Week 06**，采用子课程**内部序号**（与 Practical 侧编号一致），**不**采用 Lecture 侧的学期绝对周号 6–11。即 Week 01 = `Lecture/Week 6` + `Practical/Week 1`，……，Week 06 = `Lecture/Week 11` + `Practical/Week 6`。物理文件夹名保持原样不改，仅笔记与 manifest 的周单元命名统一为 01–06。
- 缺周：无（Lecture 与 Practical 各自完整覆盖了该子课程设计的 6 个教学单元，只是编号体系不同）
- 异常说明：见下方"特别裁定"章节的完整证据与结论
- **课程手册（新增材料）**：子课程根目录下另有两份手册（原 pdf 已转 md，不在任何周文件夹内，故未计入下表词数）：
  - `SFNS Handbook (Gilman) V2.2.md`（2,298 行，约 35,884 词）——正文第 1～6 章 + Appendix 1 + Appendix 2 + Index
  - `Chapter 7.md`（242 行，约 7,214 词）——独立增补的第 7 章（Dealing with non-independent data points），V2.2 正文与目录中均不含此章
  - **各周应读的手册章节与精确行号区间见同目录下的 `Handbook Index.md`**（含可直接复制的 Read offset/limit 参数）。周 Agent 请勿整本通读，按索引只读本周那一段。

| 周（裁定后统一编号） | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 01 | `.../Lecture/Week 6`（Lecture）<br>`.../Practical/Week 1`（Practical） | EART11200 - 08-Nov-transcript.md, Statistics for Natural Scientists L1P1(1)/L1P2.md ｜ Practical 2 answer key(1).md, Practical 2(2).md | 14,147 + 4,336 = 18,483 |
| Week 02 | `.../Lecture/Week 7`<br>`.../Practical/Week 2` | EART11200 - 15-Nov-transcript.md, Statisitcs for Natural Scientists L2P3.md, Statistics for Natural Scientists L2P1/L2P2.md ｜ Practical 3 answer key(1).md, Practical 3(2).md | 10,519 + 3,547 = 14,066 |
| Week 03 | `.../Lecture/Week 8`<br>`.../Practical/Week 3` | EART11200 - 22-Nov-transcript.md, Statistics for Natural Scientists L4P1(1)/L4P2(1).md ｜ Practical 4 answer key(2).md, Practical 4(2).md | 10,420 + 5,799 = 16,219 |
| Week 04 | `.../Lecture/Week 9`<br>`.../Practical/Week 4` | EART11200 - 29-Nov-transcript.md, Statistics for Natural Scientists L4P1(2)/L4P2(2).md ｜ Practical 5 answer key(1).md, Practical 5(1).md | 14,465 + 4,012 = 18,477 |
| Week 05 | `.../Lecture/Week 10`<br>`.../Practical/Week 5` | EART11200 - 06-Dec-transcript.md, Statistics for Natural Scientists L5P1/L5P2.md ｜ Practical 6 answer sheet(1).md, Practical 6(1).md | 12,024 + 2,686 = 14,710 |
| Week 06 | `.../Lecture/Week 11`<br>`.../Practical/Week 6` | EART11200 - 13-Dec-transcript.md（无幻灯片）｜ Practical 7 answer key.md, Practical 7.md | 6,816 + 4,271 = 11,087 |
| **小计** | | | **93,042**（另加手册按周分配的 43,098 词，见 `Handbook Index.md`） |

### 7. Practical Skills（MT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11300/Practical Skills/Michaelmas Term`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：单文件夹周
- 缺周：Week 3（实地核查确认：目录中存在 Week 1、2、4、5、6、7、8、9、10、11，唯独没有 Week 3 文件夹）
- 异常说明：无其他

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../Michaelmas Term/Week 1` | EART11300 Sem 1 Practical 1A.md | 726 |
| Week 2 | `.../Week 2` | Mersey Rivers Trust - Mcr Uni Oct 24.md | 614 |
| Week 4 | `.../Week 4` | Air Quality & Practical Intro_2024-25_GA_DK(1).md, Air_Quality_Practical_Assessment_Data_2024(4).md, Measuring Air Quality-ASSIGNMENT_INFORMATION_2023-24_GA(1).md, Measuring Air Quality_2024-25_GA_DK.md | 31,423 |
| Week 5 | `.../Week 5` | Mam Tor Field Guide.md | 2,937 |
| Week 6 | `.../Week 6` | Practical Sheet _Assessing the health of rivers(2)(1).md, Practical Skills _Identification of organisms part 1(1)/part 2(1).md | 3,002 |
| Week 7 | `.../Week 7` | Alderley tree survey questions_revised2022.md, Rhytisma acerinum.md | 929 |
| Week 8 | `.../Week 8` | Minerals in hand specimen - practical 1 - answers.md, Minerals video 1–4.md | 4,709 |
| Week 9 | `.../Week 9` | Rocks in hand specimen - answers/questions.md, Rocks video 1–3.md | 3,229 |
| Week 10 | `.../Week 10` | Expt1 pH-conductivity_Ans(1).md, Expt2 titration - seawater salinity_ans(4).md | 2,038 |
| Week 11 | `.../Week 11` | Practice minerals & rocks exam questions Dec 2022_feedback.md | 513 |
| **小计** | | | **50,120** |

### 8. A Dynamic Planet（HT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11100/Hilary Term/A Dynamic Planet`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：单文件夹周
- 缺周：无
- 异常说明：Week 10 的 transcript 日期为 "12-May"，明显滞后于其他周（27-Jan 至 24-Mar 递增），推测为补课/重排课，仅记录不改动文件夹归属。

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../A Dynamic Planet/Week 1` | EART11100 - 27-Jan-transcript.md, W1+L1+-+Unit+Introduction-DMS.md | 10,120 |
| Week 2 | `.../Week 2` | EART11100 - 03-Feb-transcript.md, Week2-Lecture.md | 14,465 |
| Week 3 | `.../Week 3` | EART11100 - 10-Feb-transcript.md, W3+Igneous+Processes+and+Volcanoes.md | 15,766 |
| Week 4 | `.../Week 4` | EART11100 - 17-Feb-transcript.md, Week4-Lecture2025.md | 17,695 |
| Week 5 | `.../Week 5` | EART11100 - 24-Feb-transcript.md, W5+Lecture.md | 11,601 |
| Week 6 | `.../Week 6` | EART11100 - 03-Mar-transcript.md, Week6-2025-Lecture.md | 15,742 |
| Week 7 | `.../Week 7` | EART11100 - 10-Mar-transcript.md, Erosional+Landscapes+%282%29.md | 13,544 |
| Week 8 | `.../Week 8` | EART11100 - 17-Mar-transcript.md, Week8-Lecture.md | 11,946 |
| Week 9 | `.../Week 9` | EART11100 - 24-Mar-transcript.md, W9+PART+1/2+Sedimentary+Depositional+Environments.md | 14,733 |
| Week 10 | `.../Week 10` | EART11100 - 12-May-transcript.md（日期异常滞后）, Introduction+to+Metamorphism%281%29.md, W10+PT1.md | 12,422 |
| Week 11 | `.../Week 11` | 11-ClimateFeedbacks-2025%281%29.md（无 transcript） | 2,726 |
| **小计** | | | **140,760** |

### 9. A Sustainable Planet（HT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11100/Hilary Term/A Sustainable Planet`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：单文件夹周
- 缺周：无
- 异常说明：幻灯片文件名内部编号与文件夹 Week 号不一致（如 Week 3 文件夹内文件名为 "wk4_18Feb"，Week 4 内为 "Week 5- Sus Planet"，Week 6 内为 "Week 8- Sus Planet-2024"，Week 8 内为 "Week 9- Sus Planet-2025"，Week 9 内为 "wk10_NEW_VC"）。**以文件夹 Week 号为准**。Week 10 的 transcript 日期为 "29-Apr"，滞后于其余周（28-Jan 至 01-Apr 递增），推测为补课/重排课。

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../A Sustainable Planet/Week 1` | EART11100 - 28-Jan-transcript.md, Week 1- Sus Planet-2025-Bb.md | 9,114 |
| Week 2 | `.../Week 2` | EART11100 - 11-Feb-transcript.md, Week 2- Sus Planet-2025 - Bb.md | 13,909 |
| Week 3 | `.../Week 3` | EART11100 - 18-Feb-transcript.md, Food Crisis and Plant Soil Interactions (wk4_18Feb SN).md | 13,593 |
| Week 4 | `.../Week 4` | EART11100 - 25-Feb-transcript.md, Week 5- Sus Planet-2025-Bb.md | 14,286 |
| Week 5 | `.../Week 5` | EART11100 - 04-Mar-transcript.md, Ecosystem_Biodiversity_March25_SN.md | 13,153 |
| Week 6 | `.../Week 6` | EART11100 - 11-Mar-transcript.md, Week 8- Sus Planet-2024-Bb(1).md | 13,365 |
| Week 7 | `.../Week 7` | CCUS_March25.md, EART11100 - 18-Mar-transcript.md | 15,010 |
| Week 8 | `.../Week 8` | EART11100 - 25-Mar-transcript.md, Week 9- Sus Planet-2025-Bb.md | 13,141 |
| Week 9 | `.../Week 9` | EART11100 - 01-Apr-transcript.md, wk10_NEW_VC_SN.md | 15,475 |
| Week 10 | `.../Week 10` | EART11100 - 29-Apr-transcript.md（日期异常滞后）, EmergingContamPoll_April25.md | 14,678 |
| **小计** | | | **135,724** |

### 10. Computer Programming（HT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11200/Hilary Term/Computer Programming`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：Lecture+Practical 配对（各 9 周，Week 号一一对应，文件名 Lecture N / Practical_N 数字一致，配对清晰）
- 缺周：无
- 异常说明：无

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../Lecture/Week 1`（Lecture）<br>`.../Practical/Week 1`（Practical） | EART11200 - 28-Jan-transcript.md, Lecture1-2.md ｜ Practical_1.md | 8,730 + 4,138 = 12,868 |
| Week 2 | `.../Lecture/Week 2`<br>`.../Practical/Week 2` | EART11200 - 04-Feb-transcript.md, Lecture2-DEES-Programming-2025.md ｜ Practical_2.md | 8,163 + 3,701 = 11,864 |
| Week 3 | `.../Lecture/Week 3`<br>`.../Practical/Week 3` | EART11200 - 11-Feb-transcript.md, Lecture_3(1).md ｜ Practical_3.md | 6,353 + 5,228 = 11,581 |
| Week 4 | `.../Lecture/Week 4`<br>`.../Practical/Week 4` | EART11200 - 18-Feb-transcript.md, Lecture4_25.md ｜ Practical_4.md | 5,819 + 4,974 = 10,793 |
| Week 5 | `.../Lecture/Week 5`<br>`.../Practical/Week 5` | EART11200 - 25-Feb-transcript.md, Lecture5_25.md ｜ Practical_5.md | 7,957 + 2,565 = 10,522 |
| Week 6 | `.../Lecture/Week 6`<br>`.../Practical/Week 6` | EART11200 - 04-Mar-transcript.md, Lecture6_25.md ｜ Practical_6.md | 7,489 + 4,378 = 11,867 |
| Week 7 | `.../Lecture/Week 7`<br>`.../Practical/Week 7` | EART11200 - 11-Mar-transcript.md, lecture7_25.md ｜ Practical_7.md | 7,381 + 11,099 = 18,480 |
| Week 8 | `.../Lecture/Week 8`<br>`.../Practical/Week 8` | EART11200 - 25-Mar-transcript.md, Lecture8_25.md ｜ Practical_8.md | 7,410 + 5,238 = 12,648 |
| Week 9 | `.../Lecture/Week 9`<br>`.../Practical/Week 9` | EART11200 - 01-Apr-transcript.md, Lecture-9b_25.md ｜ Practical_9.md | 9,176 + 9,927 = 19,103 |
| **小计** | | | **119,726** |

### 11. Mathematics and Physics（HT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11200/Hilary Term/Mathematics and Physics`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：Lecture+Practical 配对（各 12 周，Week 号一一对应，Chapter N 编号在 Lecture 和 Practical 两侧一致，配对清晰）
- 缺周：无
- 异常说明：Week 11、12 的 Practical 文件夹均只含同一份 `2324_Exam%281%29.md`（同名同内容文件在两个文件夹重复出现），推测为期末考试材料被放置于两个周文件夹，非缺失。

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../Lecture/Week 1`（Lecture）<br>`.../Practical/Week 1`（Practical） | Chapter1.md, EART11200 - 27-Jan-transcript.md, lecture1(4).md ｜ Chapter1(1).md, Solutions1(3).md, practical1_soln(3).md | 8,509 + 3,782 = 12,291 |
| Week 2 | `.../Lecture/Week 2`<br>`.../Practical/Week 2` | Chapter2.md, EART11200 - 03-Feb-transcript.md, lecture2(4).md ｜ Exercises2.md, Solutions2.md, practical2_soln(5).md | 10,453 + 2,458 = 12,911 |
| Week 3 | `.../Lecture/Week 3`<br>`.../Practical/Week 3` | Chapter3.md, EART11200 - 10-Feb-transcript.md, lecture3(2).md ｜ Exercises3.md, Solutions3(1).md, practical3_soln(5).md | 9,863 + 2,521 = 12,384 |
| Week 4 | `.../Lecture/Week 4`<br>`.../Practical/Week 4` | Chapter4.md, EART11200 - 17-Feb-transcript.md, lecture4(1).md ｜ Exercises4(1).md, Solutions4.md, practical4_soln(3).md | 10,633 + 2,713 = 13,346 |
| Week 5 | `.../Lecture/Week 5`<br>`.../Practical/Week 5` | Chapter5.md, EART11200 - 24-Feb-transcript.md, lecture5(1).md ｜ Exercises5.md, Solutions5.md, practical5_soln(1).md | 12,911 + 2,719 = 15,630 |
| Week 6 | `.../Lecture/Week 6`<br>`.../Practical/Week 6` | Chapter6.md, lecture6.md（无 transcript）｜ Exercises6.md, Solutions6.md, practical6_soln(1).md | 3,715 + 1,903 = 5,618 |
| Week 7 | `.../Lecture/Week 7`<br>`.../Practical/Week 7` | Chapter7.md, lecture7.md（无 transcript）｜ Exercises7.md, Solutions7.md, practical7_soln(1).md | 3,227 + 2,423 = 5,650 |
| Week 8 | `.../Lecture/Week 8`<br>`.../Practical/Week 8` | Chapter8.md, EART11200 - 17-Mar-transcript.md, lecture8.md ｜ Exercises8.md, Solutions8.md, practical8_soln(1).md | 10,225 + 2,449 = 12,674 |
| Week 9 | `.../Lecture/Week 9`<br>`.../Practical/Week 9` | Chapter9.md, EART11200 - 24-Mar-transcript.md, lecture9.md ｜ Exercises9(1).md, Solutions9.md, practical9_soln(1).md | 11,428 + 2,215 = 13,643 |
| Week 10 | `.../Lecture/Week 10`<br>`.../Practical/Week 10` | Chapter10.md, EART11200 - 04-Apr-transcript.md, lecture10(1).md ｜ Exercises10.md, Solutions10.md, practical10_soln(1).md | 11,840 + 2,049 = 13,889 |
| Week 11 | `.../Lecture/Week 11`<br>`.../Practical/Week 11` | EART11200 - 02-May-transcript.md, Revision_Differentiation.md ｜ 2324_Exam%281%29.md | 10,293 + 1,065 = 11,358 |
| Week 12 | `.../Lecture/Week 12`<br>`.../Practical/Week 12` | EART11200 - 09-May-transcript.md, Revision_Integration.md ｜ 2324_Exam%281%29.md（与 Week11 Practical 同名同内容） | 10,166 + 1,065 = 11,231 |
| **小计** | | | **140,625** |

### 12. Practical Skills（HT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11300/Practical Skills/Hilary Term`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：单文件夹周，**但每个 Week 文件夹内部还分 `Morning/`、`Afternoon/` 两个子文件夹**（Week 8 额外多一个 `Museum Quiz/` 子文件夹，Week 6/10 只有单一子文件夹）——这是与其他子课程不同的额外一层结构，下游 Agent 需注意进入子文件夹读取。
- 缺周：无（Week 1–10 齐全）
- 异常说明：Week 1 只有 Afternoon+Morning 各一份材料；Week 6 只有 Afternoon；Week 10 只有 Morning——即并非每周都同时有 Morning 和 Afternoon 两场。

| 周 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| Week 1 | `.../Hilary Term/Week 1/Afternoon`、`.../Week 1/Morning` | Afternoon: EART11300 Practical Introduction to Microscopy.md；Morning: P01 ANSWERS Acids, bases and buffers.md | 4,815 |
| Week 2 | `.../Week 2/Afternoon`、`.../Week 2/Morning` | Afternoon: Brighton Map Answers.md, EART11300 Practical Class 2 or 3(1)(1).md, Geological maps 1(3).md, Q3soln(4)(1).md, Q4soln(4)(1).md；Morning: P02 ANSWERS water hardness gravimetric titration.md | 5,682 |
| Week 3 | `.../Week 3/Afternoon`、`.../Week 3/Morning` | Afternoon: Geological maps 2.md；Morning: P03 soil testing practical sheet(1).md | 2,695 |
| Week 4 | `.../Week 4/Afternoon`、`.../Week 4/Morning` | Afternoon: EART11300 Semester 2 Practical Class 2_2023_answers/questions.md；Morning: Air Pollution Analysis Practical Worksheet(2).md, Air_Pollution_Data(5).md, simcity(1).md, wildfire_sheet_answers.md | 9,047 |
| Week 5 | `.../Week 5/Afternoon`、`.../Week 5/Morning` | Afternoon: Describing the physical characteristics of sediment.md, Lab Report Victim.md, POLICE LABORATORY REPORT×4, Summary of Findings.md；Morning: Eruption styles and eruption products.md, Volcanic rocks plus intro.md | 5,238 |
| Week 6 | `.../Week 6/Afternoon`（无 Morning） | Afternoon: Bedforms and sedimentary structures.md, Flume experiment.md | 2,101 |
| Week 7 | `.../Week 7/Afternoon`、`.../Week 7/Morning` | Afternoon: folds-faults-practical_solutions.md；Morning: Jones_Morphology practical_2025_Excel template(1).md, Jones_Morphology practical_2025_Handout(1).md, MorphologyPractical-2025_Slide-instructions(1).md | 6,684 |
| Week 8 | `.../Week 8/Afternoon`、`.../Week 8/Morning`、`.../Week 8/Museum Quiz` | Afternoon: Drawing.md, Fossils Answers.md, How are fossils preserved.md；Morning: volcanic-deposits-risk_first-year_modified2024.md；Museum Quiz: Museum Quiz.md | 5,503 |
| Week 9 | `.../Week 9/Afternoon`、`.../Week 9/Morning` | Afternoon: unconformities-practical_solutions(1).md；Morning: Observing plant stomata under the microscope(1).md | 3,283 |
| Week 10 | `.../Week 10/Morning`（无 Afternoon） | Morning: Chlorophyll practical_barley(1).md | 1,566 |
| **小计** | | | **46,614** |

### 13. 2025 Field Trip Material（HT）
- 子课程根目录：`/home/user/y2k/Freshman/EART11300/Hilary Term/2025 Field Trip Material`
- 笔记输出目录：`<子课程根目录>/Notes/`
- 结构类型：非周结构（单一活动文件夹，非"Week N"命名）
- 缺周：不适用
- 异常说明：仅一个子文件夹 `Earth and Planetary Field Course 7th - 12th April 2025/`，内含 1 个 md 文件（另有同名 .pptx，未计入词数统计）。

| 单元 | 材料文件夹 | md 文件 | 词数 |
|---|---|---|---|
| （整体活动，非按周） | `.../2025 Field Trip Material/Earth and Planetary Field Course 7th - 12th April 2025` | Pembrokeshire_intro(1).md | 613 |
| **小计** | | | **613** |

## 特别裁定：Statistics for Natural Scientists 的周号配对

### 实地核查证据

**Lecture 文件夹**（标注 Week 6–11）：
- 各 Week 文件夹内均含 `EART11200 - <日期>-transcript.md`，日期依次为 08-Nov、15-Nov、22-Nov、29-Nov、06-Dec、13-Dec（2024 年，均为周五）。
- 与同为 MT 课程、按"绝对学期周号"命名的 Chemistry of the Earth（Lecture 端 Week 6–11 的 transcript 日期为 06-Nov、13-Nov、20-Nov、27-Nov、04-Dec、11-Dec，均为周三）逐一比对：Statistics 的周五日期恰好比 Chemistry 的周三日期晚 2 天，落在同一教学周内。
- **结论：Lecture 侧的 "Week 6–11" 标号是真实的、与学期日历对齐的绝对周号**，可信。
- 幻灯片文件名自带编号：Week6=L1P1/L1P2，Week7=L2P1/L2P2/L2P3，Week8=L4P1(1)/L4P2(1)，Week9=L4P1(2)/L4P2(2)，Week10=L5P1/L5P2，Week11 无幻灯片（仅 transcript）。讲义编号本身存在跳号（无 L3）与重复（L4 出现两次），这是材料制作方内部编号的瑕疵，与本次周文件夹配对无关，仅供下游 Agent 知悉。

**Practical 文件夹**（标注 Week 1–6）：
- 各 Week 文件夹内**没有** transcript 文件，无法用日期直接锚定绝对周号。
- 但文件名自带独立连续编号："Practical 2"（Week1）、"Practical 3"（Week2）、"Practical 4"（Week3）、"Practical 5"（Week4）、"Practical 6"（Week5）、"Practical 7"（Week6）——编号连续无跳号、无重复，且从 "Practical 2" 起始（"Practical 1" 未出现在本目录中，可能是学期初的一次未归档的练习，或课程设计上第一次 practical 本就编号为 2）。
- Practical 侧的 "Week 1–6" 标号与 Lecture 侧不是同一套编号体系，而是该子课程内部"第几次 Practical 活动"的**相对**序号，并非学期绝对周号。

### 裁定依据与结论

1. Lecture 侧 6 个文件夹（Week 6–11）经日期交叉验证，确认对应学期第 6–11 教学周，是可信的绝对周号锚点。
2. Practical 侧 6 个文件夹（Week 1–6）无日期证据，但内容编号连续无缺（Practical 2→7），且数量与 Lecture 侧完全一致（均为 6 个单元），符合"该子课程共开设 6 周，每周一次 Lecture + 一次 Practical"的课程设计推断。
3 因此采用**按顺序位置一一对应**的配对原则：Practical 文件夹的第 i 个（Week i，i=1..6）与 Lecture 文件夹的第 i 个（Week (i+5)，即 Week 6..11）配对，即同一教学周内的 Lecture 与 Practical 材料。

4. **命名口径（用户裁定，2026-08-02 更新）**：以上证据链只确定了「哪个 Lecture 文件夹配哪个 Practical 文件夹」，不决定周单元叫什么名字。**用户已裁定：本门课统一采用子课程内部周号 Week 01～Week 06**（即与 Practical 侧编号一致），不再使用早先 manifest 采用的 Lecture 侧绝对周号 Week 6–11。上方证据与配对关系全部保留有效，仅最终命名改变。物理文件夹名不改动。

**最终配对表**（已应用于上方"6. Statistics for Natural Scientists"明细表；周单元统一以**子课程内部周号 Week 01–06** 命名，括号内为 Lecture 侧的学期绝对周号，仅供对照）：

| 统一周号（内部） | Lecture 文件夹（绝对周号） | Practical 文件夹 |
|---|---|---|
| Week 01 | `Statistics for Natural Scientists/Lecture/Week 6`（学期第 6 周） | `Statistics for Natural Scientists/Practical/Week 1` |
| Week 02 | `Lecture/Week 7`（学期第 7 周） | `Practical/Week 2` |
| Week 03 | `Lecture/Week 8`（学期第 8 周） | `Practical/Week 3` |
| Week 04 | `Lecture/Week 9`（学期第 9 周） | `Practical/Week 4` |
| Week 05 | `Lecture/Week 10`（学期第 10 周） | `Practical/Week 5` |
| Week 06 | `Lecture/Week 11`（学期第 11 周） | `Practical/Week 6` |

下游逐周笔记 Agent 在处理 Statistics for Natural Scientists 时，请按此表取材料，**不要**按两侧原始文件夹名的数字直接字面配对（例如不要把 Lecture Week 6 误配成 Practical Week 6）；笔记文件与标题一律使用 Week 01–06 的内部周号。

**课程手册的周分配**：子课程根目录下的 `SFNS Handbook (Gilman) V2.2.md` 与 `Chapter 7.md` 按章分配到六周（Week 01 = 卷首+Ch1+Ch2，Week 02 = Ch3，Week 03 = Ch4，Week 04 = Ch5，Week 05 = Ch6+两个附录+Index，Week 06 = Chapter 7 全文）。精确行号区间与 Read 参数见 `.../Statistics for Natural Scientists/Handbook Index.md`。附带佐证：Practical 侧文件自带编号为 Practical 2～7，恰与各周分配到的手册章号 Ch2～Ch7 一一吻合，进一步支持上述位置配对裁定。

## 已知异常汇总

1. **The Workshops（MT）**：缺 Week 6、8、9，实际只有 7 个周文件夹（Week 1、2、3、4、5、7、10）。
2. **Practical Skills（MT）**：缺 Week 3，实际只有 10 个周文件夹。
3. **Statistics for Natural Scientists（MT）**：Lecture 与 Practical 两侧文件夹的 Week 编号体系不一致（Lecture 用绝对学期周号 6–11，Practical 用相对活动序号 1–6），已裁定按位置一一配对；**周单元命名经用户裁定统一为内部周号 Week 01–06**，详见上方专节。另：本门课在子课程根目录下新增课程手册 2 份（`SFNS Handbook (Gilman) V2.2.md`、`Chapter 7.md`），不在周文件夹内、未计入词数统计，各周应读章节与行号区间见同目录 `Handbook Index.md`；Week 06（`Lecture/Week 11`）只有 transcript、无幻灯片。
4. **How to Build a Planet / How to Grow a Planet / A Sustainable Planet（均为单文件夹周结构的课程）**：文件夹内部幻灯片文件名所含的编号（如 "Week+9"、"Part 10"、"wk4_18Feb"）与其所在的真实文件夹 Week 号经常不一致，甚至跨周重复。下游 Agent 应始终以**文件夹路径中的 Week 号**为准，不可信任文件名内部数字。
5. **A Dynamic Planet（HT）Week 10** 与 **A Sustainable Planet（HT）Week 10**：transcript 日期（分别为 12-May、29-Apr）明显滞后于本课程其余周次的日期序列，推测为补课或重新排课，材料仍归属其文件夹标注的 Week 号，未做调整。
6. **Mathematics and Physics（HT）Week 11、12 的 Practical**：两个文件夹内是同一份文件 `2324_Exam%281%29.md`（期末考试材料），并非缺失或重复上传错误导致的内容缺口，仅提示下游 Agent 两周材料实质相同。
7. **Practical Skills（HT）**：与其余子课程不同，每个 Week 文件夹下还分 `Morning/`、`Afternoon/`（Week 8 另有 `Museum Quiz/`）子文件夹，且并非每周都同时有 Morning 和 Afternoon（Week 6 只有 Afternoon，Week 10 只有 Morning）。下游 Agent 需要递归进入这些子文件夹才能取到全部材料。
8. **2025 Field Trip Material（HT）**：非周结构，只有一个活动文件夹（Earth and Planetary Field Course 7th - 12th April 2025），内含 1 个 md 文件（同时有 1 个未计入词数统计的 .pptx）。
9. 全目录核查未发现任何子课程已存在 `Notes/` 输出目录（尚未开始笔记生成），也未发现任何 Week 文件夹之外的、需要纳入统计的散落 md 材料文件（仅各层级根目录下的课程说明文件 `(EARTxxxxx) ....md` 及 `Course Units Freshman.md`、`order.md`，均非逐周材料，未计入词数统计）。
10. 13 门子课程的周数与预期表格（用户提供）**完全一致**，未发现结构性差异；本 manifest 中列出的所有"缺周"均为已知的、符合预期的正常情况。
