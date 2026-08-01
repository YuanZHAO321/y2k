# 千年虫计划 (Y2K Project) — 执行计划（定稿）

> Slogan：大二已死，大二永存。
> 本文件是全项目的任务书。所有子 Agent 的提示词均以本计划为准。
> 状态：全案已与用户确认定稿，等待"开始"指令。

## 0. 总原则

1. **只读 md**：所有原文均已转 md，子 Agent 只读 `.md` 文件，不碰 pdf/pptx/txt/docx/ipynb（Computer Programming 的 ipynb 均有配对 md，无需破例）。
2. **Transcript 全文精读**：课堂录音转写（transcript md）与 slides/handout 同等地位，周 Agent 通读全文，不跳读。
3. **并发控制**：周笔记子 Agent 同时在场最多 **5 个**，结束一个补一个，直到该门课全部周完成。
4. **暂停点**：每门子课程（两份课程笔记做完并推送后）暂停，等用户明确指示后再进入下一门。
5. **笔记语言**：中文为主，专业术语、定义、公式保留英文原文。
6. **Git**：每完成约 5 份周笔记 commit 一次；每门子课程结束时 push 到 `claude/millennium-bug-planning-dqmsmn`。
7. **空周跳过**：某周所有文件夹为空（无任何 md）则不派 Agent。（当前 Freshman 155 个周文件夹均有 md，暂无此情况。）
8. **失败兜底**：子 Agent 输出为空或明显残缺时自动重派一次；仍失败则在本文件记录并跳过，课程结束时向用户汇报。
9. **质量抽查**：每门课派课程笔记 Agent 之前，主控抽看 1–2 份周笔记，风格跑偏及早纠正。

## 1. 课程划分规则

- 正常年份：每个 EART 五位代码 = 一门课。
- 大一特殊：EART 代码的直属子文件夹是课；若直属子文件夹是 Term，则 Term 下面的文件夹是课。
- 跨两个学期的课：每学期各算一门子课程、各出课程笔记；合并版在后处理阶段做。
- EART11200 MT 的 Mathematics and Physics：拆成两门小课（Intro Maths 与 Statistics）。

### 大一（Freshman）子课程清单（共 13 个暂停点）

| # | 子课程 | 学期 | 周数 | 特殊说明 |
|---|---|---|---|---|
| 1 | EART11100 / How to Build a Planet | MT | 10 | 周文件夹内 md 直接混放（slides + transcript） |
| 2 | EART11100 / How to Grow a Planet | MT | 11 | |
| 3 | EART11100 / The Workshops | MT | 7 | 缺 Week 6、8、9，跳过 |
| 4 | EART11200 / Chemistry of the Earth | MT | 11 | Lecture/、Practical/ 各有 Week N，需配对 |
| 5 | EART11200 / M&P: Introductory Maths | MT | 5 | Lecture/Practical 分离 |
| 6 | EART11200 / M&P: Statistics | MT | 6 | ⚠️ Lecture 为 Week 6–11，Practical 为 Week 1–6，周号错位，按 manifest 配对 |
| 7 | EART11300 / Practical Skills | MT | 10 | 缺 Week 3；周文件夹直接在 Term 下 |
| 8 | EART11100 / A Dynamic Planet | HT | 11 | |
| 9 | EART11100 / A Sustainable Planet | HT | 10 | |
| 10 | EART11200 / Computer Programming | HT | 9 | Lecture/Practical 分离 |
| 11 | EART11200 / Mathematics and Physics | HT | 12 | Lecture/Practical 分离；全年唯一 12 周 |
| 12 | EART11300 / Practical Skills | HT | 10 | |
| 13 | EART11300 / 2025 Field Trip | HT | — | 非周结构，派 1 个 Agent 做一份笔记 |

（以上为按学期时间线的暂定顺序，最终顺序由年度排序 Agent 确定。）

## 2. 主流程

### 第一步：年度排序 Agent（1 个）
通读全文 `Freshman/Course Units Freshman.md` 与三个 EART 介绍 md，输出：
1. 子课程学习顺序（覆盖上表暂定顺序）；
2. **manifest**（写入 `Freshman/manifest.md`）：每门子课程的周清单、每个周单元对应的具体文件夹路径。同时裁定 EART11200 各课 Lecture/Practical 配对关系，尤其是 Statistics 的周号错位。

### 第二步：逐门课执行（按确定的顺序）
1. **周笔记 Agent**：每周 1 个，同周的 Lecture + Practical 由同一个 Agent 通读全文（含 transcript）、学习并制作该周笔记。并发 ≤5。
2. 全部周笔记完成后，**并行派 2 个课程笔记 Agent**，各自通读全文全部周笔记：
   - Agent A → **课程总纲**：把全课组织成知识体系——主线、各周关系、核心结论、重点难点，配合周笔记使用，不重复细节。
   - Agent B → **课程整合长文**：将全部周内容整合进一份可独立使用的长文档。
3. commit + push → **暂停，等用户指令**。

## 3. 笔记规范

### 输出位置与命名
- 位置：该子课程文件夹下的 `Notes/` 子文件夹。
- 周笔记：`Notes/Week 03.md`（两位数字，便于排序）。
- 课程总纲：`Notes/Course Notes.md`；课程整合长文：`Notes/Course Notes (Full).md`。
- EART11300 Practical Skills 的 Notes 放在对应 Term 文件夹下（如 `Practical Skills/Michaelmas Term/Notes/`）。
- Field Trip 笔记：`2025 Field Trip Material/Notes/Field Trip Notes.md`。

### 周笔记深度与结构（详尽学习笔记，目标：复习时可不翻原材料）
每份周笔记约 1500–3000 字（中文为主+英文术语），固定结构：
1. **本周主题**（一两句话定位本周在全课中的位置）
2. **核心概念**（解释完整，不只列名词）
3. **公式与图表**（公式保留原文并解释各项含义；关键图表用文字描述）
4. **课堂补充**（transcript 中 slides 没有的口头讲解、强调的重点）
5. **Practical 要点**（目的、方法步骤、关键结论）
6. **易错点 / 重点难点**
7. **本周术语表**（中英对照）

## 4. 后处理（主流程完成后，逐项等用户指令）

**A层：**
1. 每门子课程的 MindMap（mermaid mindmap 语法，`Notes/MindMap.md`）。
2. 跨学期合并笔记：Practical Skills 全年版；Mathematics and Physics 全年版（Intro Maths + Statistics + HT M&P 三合一）。
3. 三个 EART 大课各一份大课笔记（通读旗下子课程的课程笔记）。

**B层：**
4. 学期笔记（MT、HT 各一份）+ 大一全年总笔记。
5. `Freshman/README.md` 导航索引页（主控直接生成，不派 Agent）。

（C层可选项——术语表汇总、公式表、自测题库——用户已确认不做。）

## 5. 进度追踪

- [ ] 年度排序 Agent + manifest
- [ ] 1. How to Build a Planet (MT)
- [ ] 2. How to Grow a Planet (MT)
- [ ] 3. The Workshops (MT)
- [ ] 4. Chemistry of the Earth (MT)
- [ ] 5. Intro Maths (MT)
- [ ] 6. Statistics (MT)
- [ ] 7. Practical Skills (MT)
- [ ] 8. A Dynamic Planet (HT)
- [ ] 9. A Sustainable Planet (HT)
- [ ] 10. Computer Programming (HT)
- [ ] 11. Mathematics and Physics (HT)
- [ ] 12. Practical Skills (HT)
- [ ] 13. 2025 Field Trip (HT)
- [ ] 后处理 A层（MindMap / 跨学期合并 / 大课笔记）
- [ ] 后处理 B层（学期笔记 / 全年笔记 / README 导航）
