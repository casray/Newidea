# 当前工作目录实验历史入口

更新：2026-10-15。此前本工作目录没有同名入口；原始方向历史实际位于`../../experiment_history_and_lessons/`，其中有基础文件及编号2–44的记录（编号并不保证连续）。这些原始文件保留，不能用本索引替代逐方向的配置、seed、日志与负结果。

## 阅读顺序

1. `01_literature_and_research_map.md`与`99_session_handoff.md`，理解当前问题及最新授权。
2. `research/algorithm_redesign_20261013/01_项目与旧实验复盘.md`建立投稿稿件和历史证据定位；具体旧方向回查上述原始历史目录。
3. 当前方向的PLAN、结果CSV、audit和完整结论；本文件只保存入口及关键教训。

## 已完成的本阶段实验

| 方向 | 范围 | 实际记录 | 决策 |
|---|---|---|---|
| 训练内独立证据剪枝 | 六图同GREET树，三协议seed三条件，六新臂；固定惩罚/无惩罚/全票与分折粗中细对照 | experiments/evidence_pruning_20261015已完成324新目标/结果、286新模型38别名，另216历史锚；14测试，54协议1944组件540预测1045输入源哈希审计通过 | defer当前准则；六图目标/分类门槛皆失败，Cora带噪−7.938pp、CS−2.166pp；Squirrel相对细球+2.229pp但不超旧一球且clean−.730pp；Cora过粗与分折损失并存，不扫delta、不默认替换，完整解释见综合结论与接续.md |
| 属性与结构残差互补 | 新Amazon-ratings/Tolokers+Roman/CS，五协议seed、三条件、七目标臂；二分类AUC | experiments/attribute_structure_20261015已完成420目标/300新学生；38测试，420目标/300预测/420配对/953文件哈希独立审计通过 | modify/defer；Amazon BFS比OLD64三条件+1.107/+1.019/+1.293pp均5/5正，但clean低于CE；Tol无稳定AUC增益，CS Pair X/BFS低于OLD64 2.442/5.955pp。四图R目标gate均失败，R学生未启动、不称分类失败；不扫权重，详见综合结论与接续.md |
| 六图嵌套粒球数量诊断 | 新增Actor/Chameleon-filtered/Squirrel-filtered；固定树与support16，8预算，暂不做独立KM/kNN | experiments/ball_count_diagnostic_20261015已完成；1026目标/学生记录、819独立模型、207别名；36分区54协议及81历史锚审计通过，35测试通过 | modify；Cora U同树64→终点40.10→42.44%，CS Pair86.45→84.64%；Squirrel带噪一球较好；拒绝统一sqrt/扩预算，提出未验证的训练内证据剪枝；详见综合结论与接续.md |
| 无标签BFS拓扑区域与原LCSS | 三图五协议seed三条件七臂；目标门槛后训练CoraFull/CS | experiments/topology_bfs_lcss_20261015；315目标、210新学生，3分区/15协议/全部logits审计，12历史分数核查一致 | 修改/暂缓纯BFS异配主线；Cora带噪优于CE但低于旧GB64，CS Pair相对旧版−6.03pp，Roman目标未超过匹配随机；两图简化判据均失败 |
| GREET自适应分球复验 | 同冻结两空间、三图三协议seed三条件；固定64与sqrt支持16，KM/kNN匹配 | experiments/greet_adaptive_ball_20261015已完成；16测试、297目标/学生，18分区27标签协议297logits审计通过，30历史分数一致 | modify；Cora相同新规则GREET带噪+1.67pp且6/6正，但比GREET kNN低1.87pp；Roman增量不足，CS Pair比原版低1.02pp；不统一替换默认 |
| GREET与HF-proxy独立首轮 | 三图、三协议seed、三条件；按门槛推进学生与融合 | experiments/greet_half_pilot_20261015已完成；54协议324目标243辅助模型，审计通过 | A/B门槛均失败，0学生；三图GREET旧规则均1球，带噪目标退化；不等于GREET整体或完整HALF无效 |
| 异配机制诊断 | 原两图、Roman两种表示及可靠性对照 | experiments/heterophily_mechanism_20261014；60单元840行，48seed0学生，20协议审计 | ESS×JS未过推进门槛；不重复无新信号的调温度 |
| 原GB64异配基线 | Texas/Wisconsin/Roman，五split，三条件，CE/GB64/KNN | experiments/heterophily_original_baseline_20261014；135学生，审计通过 | 带噪收益与干净损害并存；小图实际仅4–5球 |
| 自适应sqrt支持4 | 五图五协议目标及seed0分类 | experiments/adaptive_sqrt_ball_20261014；75目标单元600行、75学生，25协议+75学生审计 | Cora/Roman目标过探索筛查；小图学生退化，不能统一采用 |
| 固定支持16后续 | 五图仅seed0；只改最少训练支持 | experiments/adaptive_support16_ball_20261014；15目标单元120行、75学生，5协议+75学生审计 | 小图部分修复但未统一胜旧；Cora正信号，CS Pair负；停止阈值搜索 |
| PiNGDA与上下文构球空间 | Cora/CiteSeer/CoraFull，完整seed0/1，三条件，两分类器，三预算 | experiments/context_gb_two_seed_20261014；24SSL、324目标、684学生，严格审计通过 | defer；相对原GRACE带噪MLP−6.332pp、GCN−1.888pp；GCN对弱PiNGDA+.516pp仅探索信号 |

## 最新生成器方向的必备记录

- **研究假设**：旧固定最小子球和停止门槛限制细分；规模预算可能改善局部证据，但过细分球会减少抗噪投票支持。
- **粒球角色**：冻结表示上的局部软监督证据区域；不作为硬正样本或分类标签。
- **方法动机**：先隔离区域生成，不同时修改GRACE、LCSS与MLP。
- **代码改动**：新增`GB-LCSS_code/src/gblcss/granular_ball_adaptive.py`与两轮独立引擎/测试/审计；旧生成器保留。
- **配置改动**：请求ceil(sqrt(N))、最小球ceil(N/(4B))、总SSE优先及投影fallback；支持4首轮，支持16唯一后续固定值。只读训练集合位置，不读类别。
- **预期机制**：局部性改善与投票支持减少存在权衡，不能以球数达标代替可靠监督。
- **成功标准**：第一轮预设带噪配对Brier≤−.005且至少4/5改善，仅作探索信号；必须报告学生和匹配KM/KNN。第二轮仅seed0，五seed门槛不评定。
- **失败标准**：目标/分类退化、干净错误修正、无匹配对照优势均须保存；不从测试集逐图选择阈值。
- **实验结果**：见`experiments/adaptive_support16_ball_20261014/综合结论与接续.md`及两轮原始CSV。支持4数量14/16/151/141/136；支持16实际3/5/151/141/136。分类结论只单seed，不伪造std。
- **最终决策**：保留生成器研究版；继续确认CoraFull及证据质量；暂缓统一规则部署。不扫8/12/20、不叠已失败ESS×JS，不把sqrt经验写成最优理论。
- **验证与追溯**：source manifests、data/H/split/noise/targets hashes、逐球/分裂统计、raw logs、config、logits、CSV和audit已保存；第二轮30项历史准确率全部一致；34测试+20subtests通过。

## 必须继承的边界

同球身份不等于同类语义；更紧凑不保证更适合分类。增加票数可以降低人工翻转的条件随机波动，但无法消除干净几何中错误类别多数。目标Brier改善未必转化为MLP准确率。五协议目标seed不等于五个学生seed，更不等于五次独立SSL训练。普通kNN/k-means目前仍是必要强对照。

任何后续“继续、修改、暂缓、放弃”必须对照冻结计划及全部条件，不能只引用本文件摘要中的正信号。

## Context-GB 独立方向，2026-10-14已完成

详见`experiments/context_gb_two_seed_20261014/综合结论与接续.md`、同目录方向历史与`runs/summary.csv`、`runs/audit/report.json`。当前defer，不扩大seed或自动调参。用户本轮排除独立KM/KNN，不评定粒球必要性。每个seed有独立SSL，统一200轮，不混比旧CoraFull1000轮或其他分支单seed成绩。

已支持：新空间多数关系/Brier退化，C低秩；MLP相对原GRACE12/12带噪配对下降；GCN总体下降但CoraFull局部改善接近CE。合理解释：增强→最终原图空间有偏移，因果未证。尚未验证：原GRACE增强只加context及真实子图。被削弱：新增强或VICReg自动改善粒球语义的假设。本轮无联合CE，不以分类/对比冲突解释此次失败。
