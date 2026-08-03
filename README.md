# 千年虫计划 · Y2K Project

> **大二已死，大二永存。**

这是一套由 AI 通读全部原始课程材料后逐周撰写的**中文学习笔记库**，覆盖英国曼彻斯特大学 BSc Earth and Planetary Sciences（地球与行星科学）本科课程。

笔记由 AI 通读原始材料（讲义、幻灯片、课堂录音转写、习题与解答、野外指南、Jupyter Notebook）后撰写。**大一的原始材料在笔记完成后已从仓库移除**以精简体积——如需回看原文，可从 git 历史中取回（见文末「关于原始材料」）。

**当前状态**：大一（Freshman）13 门子课程主流程已全部完成 —— **125 份笔记，8.2 MB**。大二（Sophomore）材料已就位，等待开工。

---

## 一、快速导航

每门课有两个入口：**课程总纲**（一份，课程文件夹根目录）与**周笔记**（`Notes/` 目录下）。

### 大一 · 秋季学期（Michaelmas Term）

| 子课程 | 周数 | 课程总纲 | 周笔记 |
|---|---|---|---|
| Introductory Maths for Natural Scientists | 5 | [📄 总纲](Freshman/EART11200/Michaelmas%20Term/Mathematics%20and%20Physics/Introductory%20Maths%20for%20Natural%20Scientists/Course%20Notes.md) | [📁 Notes](Freshman/EART11200/Michaelmas%20Term/Mathematics%20and%20Physics/Introductory%20Maths%20for%20Natural%20Scientists/Notes) |
| Chemistry of the Earth | 11 | [📄 总纲](Freshman/EART11200/Michaelmas%20Term/Chemistry%20of%20the%20Earth/Course%20Notes.md) | [📁 Notes](Freshman/EART11200/Michaelmas%20Term/Chemistry%20of%20the%20Earth/Notes) |
| How to Build a Planet | 10 | [📄 总纲](Freshman/EART11100/Michaelmas%20Term/How%20to%20Build%20a%20Planet/Course%20Notes.md) | [📁 Notes](Freshman/EART11100/Michaelmas%20Term/How%20to%20Build%20a%20Planet/Notes) |
| How to Grow a Planet | 11 | [📄 总纲](Freshman/EART11100/Michaelmas%20Term/How%20to%20Grow%20a%20Planet/Course%20Notes.md) | [📁 Notes](Freshman/EART11100/Michaelmas%20Term/How%20to%20Grow%20a%20Planet/Notes) |
| Practical Skills (MT) | 10 | [📄 总纲](Freshman/EART11300/Practical%20Skills/Michaelmas%20Term/Course%20Notes.md) | [📁 Notes](Freshman/EART11300/Practical%20Skills/Michaelmas%20Term/Notes) |
| Statistics for Natural Scientists | 6 | [📄 总纲](Freshman/EART11200/Michaelmas%20Term/Mathematics%20and%20Physics/Statistics%20for%20Natural%20Scientists/Course%20Notes.md) | [📁 Notes](Freshman/EART11200/Michaelmas%20Term/Mathematics%20and%20Physics/Statistics%20for%20Natural%20Scientists/Notes) |
| The Workshops | 7 | [📄 总纲](Freshman/EART11100/Michaelmas%20Term/The%20Workshops/Course%20Notes.md) | [📁 Notes](Freshman/EART11100/Michaelmas%20Term/The%20Workshops/Notes) |

### 大一 · 春季学期（Hilary Term）

| 子课程 | 周数 | 课程总纲 | 周笔记 |
|---|---|---|---|
| Mathematics and Physics | 12 | [📄 总纲](Freshman/EART11200/Hilary%20Term/Mathematics%20and%20Physics/Course%20Notes.md) | [📁 Notes](Freshman/EART11200/Hilary%20Term/Mathematics%20and%20Physics/Notes) |
| Computer Programming | 9 | [📄 总纲](Freshman/EART11200/Hilary%20Term/Computer%20Programming/Course%20Notes.md) | [📁 Notes](Freshman/EART11200/Hilary%20Term/Computer%20Programming/Notes) |
| A Dynamic Planet | 11 | [📄 总纲](Freshman/EART11100/Hilary%20Term/A%20Dynamic%20Planet/Course%20Notes.md) | [📁 Notes](Freshman/EART11100/Hilary%20Term/A%20Dynamic%20Planet/Notes) |
| A Sustainable Planet | 10 | [📄 总纲](Freshman/EART11100/Hilary%20Term/A%20Sustainable%20Planet/Course%20Notes.md) | [📁 Notes](Freshman/EART11100/Hilary%20Term/A%20Sustainable%20Planet/Notes) |
| Practical Skills (HT) | 10 | [📄 总纲](Freshman/EART11300/Practical%20Skills/Hilary%20Term/Course%20Notes.md) | [📁 Notes](Freshman/EART11300/Practical%20Skills/Hilary%20Term/Notes) |
| 2025 Pembrokeshire 野外实习 | — | [📄 笔记](Freshman/EART11300/Hilary%20Term/2025%20Field%20Trip%20Material/Field%20Trip%20Notes.md) | — |

> 表中顺序即**学习顺序**，由排序 Agent 按知识依赖关系确定（见 [`Freshman/order.md`](Freshman/order.md)），并非文件夹的字母序。

---

## 二、怎么用这些笔记

每门课有两类笔记：

| 文件 | 位置 | 是什么 | 什么时候用 |
|---|---|---|---|
| `Course Notes.md` | 课程文件夹根目录 | **课程总纲**。通读全部周笔记后写成的骨架：主线脉络、知识体系、核心结论、重点难点、勘误表 | 建立全局认识、考前串讲 |
| `Week 01.md` … `Week NN.md` | 课程文件夹下的 `Notes/` | **周笔记**。逐周通读全部材料后写成，目标是**复习时不必再翻原材料** | 系统复习、查具体知识点 |

**建议路径**：先读课程总纲建立框架 → 按需回到周笔记补细节。

### 周笔记的固定七段结构

全部 112 份周笔记结构统一，便于跳读：

1. **本周主题** — 一两句话定位本周在全课中的位置
2. **核心概念** — 逐个概念讲透，不只列名词
3. **公式与图表** — 公式保留原文并解释符号；图表用文字描述判读方法
4. **课堂补充** — 转写里有、幻灯片上没有的内容（老师的口头强调、案例、易错点提醒）
5. **Practical 要点** — 实践目的、步骤、数据处理、结果判读；习题逐题梳理
6. **易错点 / 重点难点**
7. **本周术语表** — 中英对照

技能课（Practical Skills、Computer Programming）的第三、五节按学科作了调整——例如编程课的第三节是「语法速查与函数表」，实践课的第五节升格为主体。

### 标记约定

| 标记 | 含义 |
|---|---|
| **📎 背景补充** | 该段**不是课堂原文**，是 AI 为使内容可读而补充的背景知识。复习时可参考，但不应视为考纲内容 |
| **（本周无）** | 该节在本周确无对应内容，非遗漏 |
| **（已勘误）** | 该数值/表述已修正原材料中的错误，正确值见勘误表 |

**语言约定**：正文中文，专业术语、公式、函数名、物种学名保留英文/拉丁文原文。

---

## 三、勘误表 —— 本项目的意外收获

笔记 Agent 在通读材料时发现了**大量原始教学材料自身的错误**，并逐条核实、更正、记录。累计超过 **250 条**，其中不乏会直接导致理解错误的硬伤。

各课的勘误汇总在对应的 `Course Notes.md` 中：

| 课程 | 勘误条数 | 位置 |
|---|---|---|
| [Mathematics and Physics (HT)](Freshman/EART11200/Hilary%20Term/Mathematics%20and%20Physics/Course%20Notes.md) | **62** + 13 项「反推重建」清单 | 总纲第七节 |
| [A Sustainable Planet](Freshman/EART11100/Hilary%20Term/A%20Sustainable%20Planet/Course%20Notes.md) | **60**（55 条逐条 + ASR 错词五类归并） | 总纲第七节 |
| [Computer Programming](Freshman/EART11200/Hilary%20Term/Computer%20Programming/Course%20Notes.md) | **47**（含 5 条「看似能跑实则有问题」的隐蔽 bug） | 总纲第七节 |
| [A Dynamic Planet](Freshman/EART11100/Hilary%20Term/A%20Dynamic%20Planet/Course%20Notes.md) | **22** 条知识性/数值错误 + 40+ ASR 错词 | 总纲第七节 |
| [Practical Skills (HT)](Freshman/EART11300/Practical%20Skills/Hilary%20Term/Course%20Notes.md) | **19** | 总纲第七节 |
| 其余各课 | 散见 | 各周笔记「易错点」节 |

> A Sustainable Planet 的总纲还单列了一节**考试信息汇总（26 条）**：题型配分、范围、以及老师明确说不考的内容。

**典型案例**（照抄会出大问题的那种）：

- 向量方向被写成 "start minus end"（起点减终点）——**实为终点减起点**，照做所有向量方向反号
- ²³⁹Pu 的半衰期 24,000 年被口述成 **²³⁹U**（实际半衰期 23 分钟，差九个数量级）
- 柯石英被称作石英的「高温」多象——**实为高压**多象，记反则超高压变质的 P-T 判读全废
- 未来人口 "11000–12000 billion"（应为 11–12 billion，差三个数量级）
- 官方 Python 解答注释掉 PCA 后仍传 `pca_components`，**靠 Jupyter 变量残留才跑通**，重启内核即崩
- 手册 F 统计量脚注的缩放因子与自由度写错——由 `chickwts` 数据集实际输出反推验证后确认

---

## 四、材料状况与已知缺口

原始材料存在若干缺失与转换损耗，笔记中已逐处标注。**复习时遇到下列内容，需回看原 PDF 或另行获取**：

### 整周缺失
- **Practical Skills (MT)**：缺 Week 3
- **The Workshops**：缺 Week 6、8、9

### 材料本身缺失
- **A Dynamic Planet W9**：老师两次强调「一定会考」的**线上碳酸盐岩视频不在课程文件夹内**
- **A Dynamic Planet W7**：风成过程被老师明确跳过（原话 "a gaping hole in my lecture"），海岸过程完全未讲
- **Practical Skills (HT)**：6 处练习无官方答案（含 Museum Quiz，讲义写明「答案下周发布」）
- **2025 Field Trip**：仅有行前介绍，**无区域地质内容、无评估要求与评分标准**

### 无课堂转写
- The Workshops（全部 7 周）、Practical Skills（两学期全部）、How to Grow a Planet W11、A Dynamic Planet W11

### 转换损耗（PDF/docx → md）
- **Mathematics and Physics (HT)** 最严重：公式、例题、题面函数大量是图片，转换后仅剩文字骨架。笔记采用**由答案反推重建 + 交叉验证**的办法补全，重建内容均已标注
- **Practical Skills (HT)**：8 周的关键公式与地图图件丢失
- **The Workshops**：练习题与图件大量丢失
- **A Sustainable Planet W1**：转写有大段缺失（幻灯片 16–28 无对应录音）

### 待人工核对
- **How to Grow a Planet**：Week 2 / Week 4 课件疑似对调（W4 内容在演化时间轴上早于 W2、W3）

---

## 五、大二 · Sophomore

材料已上传并转为 md，**尚未开工**。

| 学期 | 课程代码 |
|---|---|
| Michaelmas Term | EART22201、EART24001、EART26001、EART26201、EART27201、EART28101 |
| Hilary Term | EART21202、EART23202、EART25102、EART28202、EART29102 |
| 跨学期 | EART29200 |

共 **12 门课、397 份 md、约 83.9 万词**（约为大一的 71%）。

大二与大一的流程差异：**周笔记全部完成后，才统一回头制作课程笔记**——每门课周笔记做完时把课程笔记的提示词预写入进度文件，待全部课程的周笔记完工后按顺序统一执行。

---

## 六、后处理（待办）

大二结束后统一进行：

**A 层**
- 各门课的**课程整合长文**（`Course Notes (Full).md`）——可独立于周笔记使用的完整长文档
- 各门课的 **MindMap**（mermaid 语法）
- 跨学期合并笔记：Practical Skills 全年版、Mathematics and Physics 全年版
- 三个 EART 大课笔记（EART11100 / EART11200 / EART11300）

**B 层**
- 学期笔记（MT、HT 各一份）
- 大一全年总笔记
- 本 README 的持续更新

---

## 七、项目说明

| 项目 | 说明 |
|---|---|
| 执行方式 | 主控调度 + 子 Agent 逐周撰写，主控与材料内容隔离 |
| 模型 | 全部使用 Opus |
| 大一消耗 | 约 **1553 万 token**，覆盖 118 万词原始材料 |
| 任务书 | [`PLAN.md`](PLAN.md) —— 全项目规则与进度追踪 |
| 学习顺序 | [`Freshman/order.md`](Freshman/order.md) |
| 材料清单 | [`Freshman/manifest.md`](Freshman/manifest.md) —— 逐周材料路径、词数、异常标注（材料已移除，此表作存档用） |

### 关于原始材料

大一的原始材料（约 700 个文件：md / pdf / pptx / docx / ipynb）在笔记完成后已从仓库移除。**它们完整保留在 git 历史中**，需要时可取回：

```bash
# 查看某周原材料
git show <旧提交>:"Freshman/EART11100/Michaelmas Term/How to Build a Planet/Week 1/"

# 恢复整个大一原材料树到工作区
git checkout <旧提交> -- Freshman/
```

`Freshman/manifest.md` 记录了每一周的材料文件名与词数，可据此定位。两份 AI 生成的课程手册分章索引（`Handbook Index.md`，用于 Statistics 与 M&P 的逐周定位）随材料一并移除，同样可从历史取回。

---

## 附录 · 全年周次索引

<details>
<summary><b>秋季学期（Michaelmas Term）</b></summary>

**Introductory Maths for Natural Scientists**（5 周）
1. 科学记数法、单位换算与「测量分子」 · 2. 分数与因式分解、热能等价、净初级生产力 · 3. 勾股定理、三角学与地质几何 · 4. 理想气体定律、道尔顿分压与 ppmv · 5. 对数与指数、里氏震级

**Chemistry of the Earth**（11 周）
1. 地球由什么构成？元素起源 · 2. 地球化学家眼中的元素周期表 · 3. 地球分层与元素分配 · 4. 全球碳循环与有机化学 · 5. 化学反应与氧化态 · 6. 化学平衡与热力学 · 7. 岩石熔融与稀土元素 · 8. 稳定同位素 · 9. 水与大气降水同位素 · 10. 放射性同位素与地质年代学 · 11. 总复习

**How to Build a Planet**（10 周）
1. 地球之前——宇宙的形成 · 2. 恒星与星系的形成 · 3. 太阳系形成与冥古宙 · 4. 矿物与岩石 · 5. 板块构造系统 · 6. 太古宙 · 7. 元古宙 · 8. 古生代 · 9. 中生代 · 10. 新生代

**How to Grow a Planet**（11 周）
1. 生命起源与 LUCA · 2. 动物起源——埃迪卡拉到寒武纪大爆发 · 3. 海洋生命与鱼类时代 · 4. 氧气与真核细胞起源 · 5. 登陆 · 6. 从苔藓到第一片森林 · 7. 中生代与恐龙 · 8. 被子植物崛起 · 9. 古近纪 · 10. 草原世界与人类起源 · 11. 农业起源与作物驯化

**Practical Skills (MT)**（10 周，缺 W3）
1. 地图入门与网格参考 · 2. 流域尺度河流管理 · 4. 空气质量测量与误差分析 · 5. Mam Tor 野外指南 · 6. 底栖无脊椎动物鉴定与河流健康评估 · 7. 林地评估与生物指示 · 8. 手标本矿物鉴定 · 9. 手标本岩石鉴定 · 10. 湿化学实验室技能 · 11. 应考演练与反馈

**Statistics for Natural Scientists**（6 周）
1. 科学方法、实验设计与两组均值比较 · 2. ANOVA 与 Tukey 事后检验 · 3. 线性回归 · 4. 卡方与 Fisher 精确检验 · 5. 逻辑回归 · 6. 混合效应模型

**The Workshops**（7 周，缺 W6/8/9）
1. Clocks in Rocks · 2. 地质年代 I（相对定年） · 3. 地质年代 II（绝对定年） · 4. 岩层顶底判别 · 5. 地震 · 7. Evolution 101 · 10. 我们的太阳系「平均」吗？

</details>

<details>
<summary><b>春季学期（Hilary Term）</b></summary>

**Mathematics and Physics**（12 周）
1. 计算梯度 · 2. 微分入门 · 3. 链式/乘积/商法则 · 4. 最优化与导数性质 · 5. 二阶导数与数值求根 · 6. 积分入门 · 7. 用牛顿定律做积分 · 8. 换元积分法 · 9. 二阶常微分方程 · 10. 向量与偏微分 · 11. 微分复习 · 12. 积分复习

**Computer Programming**（9 周）
1. Python 入门 · 2. 循环与条件语句 · 3. 模块、函数与 NumPy · 4. 二维数组与康威生命游戏 · 5. SciPy 解微分方程 · 6. Pandas 与数据探索 · 7. GeoPandas 与 GIS · 8. 时间索引、数据合并与 Seaborn · 9. 机器学习入门

**A Dynamic Planet**（11 周）
1. 单元导论——地球系统 · 2. 大气如何运作 · 3. 火成作用与火山 · 4. 天气与天气预报 · 5. 构造地质学与地壳垂直运动 · 6. 大气化学与水圈 · 7. 侵蚀地貌的形成 · 8. 冰冻圈与气候模拟 · 9. 沉积环境 · 10. 变质作用 · 11. 气候反馈

**A Sustainable Planet**（10 周）
1. UN SDGs 导论 · 2. 地球资源——土壤、肥料与水 · 3. 粮食危机与植物-土壤相互作用 · 4. 矿产资源与电池金属 · 5. 生物多样性、生态系统功能与磷 · 6. 工业矿物与化石燃料 · 7. CCUS · 8. 低碳能源与核能 · 9. 环境挑战与解决方案 · 10. 新兴污染物

**Practical Skills (HT)**（10 周，上午场 / 下午场）
1. 酸碱与缓冲液 / 偏光显微镜入门 · 2. 水硬度滴定 / 地质图判读一 · 3. 土壤磷酸盐测试 / 地质图判读二 · 4. 空气污染数据与野火排放 / 显微镜下三大岩类 · 5. 火山喷发产物 / 法证地质学沉积物比对 · 6.（无）/ 底形与水槽实验 · 7. 形态学测量 / 褶皱与断层判读 · 8. 火山灾害遥感 / 化石保存与科学绘图 · 9. 植物气孔观察 / 不整合面判读 · 10. 叶绿素分光光度定量 /（无）

**2025 Pembrokeshire 野外实习** —— 行前介绍（2025 年 4 月 7–12 日）

</details>
