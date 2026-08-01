# 千年虫计划 (Y2K Project) — 执行计划

> Slogan：大二已死，大二永存。
> 本文件是全项目的任务书。所有子 Agent 的提示词均以本计划为准。
> 状态：已与用户确认，等待"开始"指令。

## 0. 总原则

1. **只读 md**：所有原文均已转 md，为控制 token 消耗，子 Agent 原则上只读 `.md` 文件，不碰 pdf/pptx/txt/docx/ipynb。
2. **并发控制**：周笔记子 Agent 同时在场最多 **5 个**，结束一个补一个，直到该门课全部周完成。
3. **暂停点**：每门子课程（课程笔记做完并推送后）暂停，等用户明确指示后再进入下一门。
4. **笔记语言**：中文为主，专业术语、定义、公式保留英文原文。
5. **Git**：每完成约 5 份周笔记 commit 一次；每门子课程结束（课程笔记完成）时 push 到 `claude/millennium-bug-planning-dqmsmn`。
6. **空周跳过**：某周所有文件夹为空（无任何 md）则不派 Agent。（当前 Freshman 155 个周文件夹均有 md，暂无此情况。）

## 1. 课程划分规则

- 正常年份：每个 EART 五位代码 = 一门课。
- 大一特殊：EART 代码的直属子文件夹是课；若直属子文件夹是 Term，则 Term 下面的文件夹是课。
- 跨两个学期的课：每学期各算一门子课程、各出一份课程笔记；合并版在后处理阶段做。
- EART11200 MT 的 Mathematics and Physics：**拆成两门小课**（Intro Maths 与 Statistics）。

### 大一（Freshman）子课程清单（共 13 个暂停点）

| # | 子课程 | 学期 | 周数 | 特殊说明 |
|---|---|---|---|---|
| 1 | EART11100 / How to Build a Planet | MT | 10 | 周文件夹内 md 直接混放 |
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

（以上顺序为按学期时间线的暂定顺序，最终顺序由年度排序 Agent 确定。）

## 2. 主流程

### 第一步：年度排序 Agent（1 个）
通读全文 `Freshman/Course Units Freshman.md` 与三个 EART 介绍 md，输出：
1. 子课程学习顺序（覆盖上表暂定顺序）；
2. **manifest**（写入 `Freshman/manifest.md`）：每门子课程的周清单、每个周单元对应的具体文件夹路径。此步骤同时裁定 EART11200 各课 Lecture/Practical 的配对关系，尤其是 Statistics 的周号错位。

### 第二步：逐门课执行（按确定的顺序）
1. 派周笔记 Agent：每周 1 个，同周的 Lecture + Practical 由同一个 Agent 通读全文、学习并制作该周笔记。并发 ≤5。
2. 该课全部周笔记完成后：派 1 个课程笔记 Agent，通读全文全部周笔记，学习并制作课程笔记。
3. commit + push → **暂停，等用户指令**。

## 3. 输出规范

- 位置：该子课程文件夹下的 `Notes/` 子文件夹。
- 周笔记：`<子课程>/Notes/Week 03.md`（两位数字，便于排序）。
- 课程笔记：`<子课程>/Notes/Course Notes.md`。
- EART11300 Practical Skills 的 Notes 放在对应 Term 文件夹下（如 `Practical Skills/Michaelmas Term/Notes/`）。
- Field Trip 笔记：`2025 Field Trip Material/Notes/Field Trip Notes.md`。

## 4. 后处理（主流程完成后，逐项等用户指令）

1. 每门子课程的 MindMap（mermaid mindmap 语法写入 `Notes/MindMap.md`）。
2. 跨学期合并：Practical Skills 全年笔记；Mathematics and Physics（Intro Maths + Statistics + HT M&P）相关合并笔记——具体合并口径届时与用户确认。
3. 三个 EART 大课各一份大课笔记（通读旗下子课程笔记）。
4. 学期笔记（MT、HT 各一份）与大一全年总笔记。

## 5. 进度追踪

每门子课程完成后在下表打勾（由执行时更新）：

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
- [ ] 后处理
