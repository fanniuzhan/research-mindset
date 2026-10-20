# 思维原则的来源与边界

这是对已经阅读材料的综合改写，不是某机构官方规范。非官方 Google 博客、Google 官方课程、Berkeley 课程与各作者书籍分别署名；科研／EEG 迁移和本 skill 的输出结构属于独立设计。来源更新时应核对网页，不能假设全书或外链实验已复现。

## 核心来源

| 来源 | 进入本 skill 的思想 |
|---|---|
| Patrick Riley, [Practical advice for analysis of large, complex data sets](https://www.unofficialgoogledatascience.com/2016/10/practical-advice-for-analysis-of-large.html) | 生命体征、分布、实例、分组、时间一致性、端到端迭代、计数过滤与明确分母 |
| [Mind Your Units](https://www.unofficialgoogledatascience.com/2016/08/mind-your-units.html) | 观测行、分析单位与独立证据不同，设计与推断需保留依赖 |
| [Unintentional data](https://www.unofficialgoogledatascience.com/2017/10/unintentional-data.html)；[Data scientist as scientist](https://www.unofficialgoogledatascience.com/2015/10/data-scientist-as-scientist.html) | 从现成数据和异常发展问题，提出竞争解释与可检验预测 |
| [Uncertainties: Statistical, Representational, Interventional](https://www.unofficialgoogledatascience.com/2021/12/uncertainties-statistical.html) | 区间之外还需检验代理含义与使用条件变化 |
| [Measuring Validity and Reliability of Human Ratings](https://www.unofficialgoogledatascience.com/2023/07/measuring-validity-and-reliability-of.html) | 标注一致性和测量效度需分开验证 |
| [Estimating the prevalence of rare events](https://www.unofficialgoogledatascience.com/2019/08/estimating-prevalence-of-rare-events.html) | 找问题与估总体比例要有不同设计，风险抽样需概率及权重 |
| [Google Problem Framing](https://developers.google.com/machine-learning/problem-framing) | 真实目标、代理与成功证据，简单基线、Oracle Test、最小实现 |
| [Data 100 Course Notes](https://ds100.org/course-notes/) | 问题、数据整理、探索、建模与现实语境连接；工具语法随版本变化 |
| [Learning Data Science，第 2 章](https://learningds.org/ch/02/data_scope_intro.html) | 目标总体、可访问范围、样本、测量仪器与协议 |
| [第 5 章公交案例](https://learningds.org/ch/05/bus_intro.html) | 记录对象与目标体验不同，长度偏倚、分布尾部与模拟假设 |
| [第 9 章数据整理](https://learningds.org/ch/09/wrangling_intro.html)；[第 12 章空气质量](https://learningds.org/ch/12/pa_intro.html) | 粒度、连接、缺失、时区、采样协议变动与测量比较先于校准 |
| [第 16 章模型选择](https://learningds.org/ch/16/ms_intro.html) | 模型选择与最终评估分开，教学随机切分不自动适合层次依赖 |
| Rohan Alexander, [Telling Stories with Data，第 9 章](https://tellingstorieswithdata.com/09-clean_and_prepare.html) | 清理即分析，保留原始数据、先定义输出、小样本迭代、有效性与内外一致性 |
| Wes McKinney, [Python for Data Analysis](https://wesmckinney.com/book/) | 将连接、重塑、缺失与时间处理落实成明确操作；工具正确不替代科学语义 |
| [Computational and Inferential Thinking](https://inferentialthinking.com/)；[ISL](https://www.statlearning.com/) | 抽样与模拟、关联与因果、推断、重采样和模型比较的基础 |

Google 博客的上述文章已在本任务阅读中逐篇分析；书籍只对选定章节进行精读，其余简介与目录用于选书。源文中的阈值、历史工具、数据案例和简化做法不作为通用强制规则。

## 避免错误迁移

- 产品导向的 framing 可帮助科研，但机制发现不必有即时部署目标。
- 传感器校准依赖参照质量、测量误差和可比范围，不能把其他领域的逆回归公式机械套入 EEG。
- 代表性、独立性、测量效度和计算正确性需要不同证据，单一“质量分”不替代它们。
- 本 skill 不提供通用滤波／伪迹阈值；参数需由协议、领域依据和目标信息决定。
- 在当前数据中发现差异，与证明某机制导致差异之间仍需要实验或识别条件。
