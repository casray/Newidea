# Newidea：粒球粗化研究

2026-10-20更新：v2正式实验1080/1080完成；全部预测与来源审计通过。

[完整结果、正负证据与下一步决策](gb_c1_ratio_success_20260609/results_ratio_c1_20260609/experiments/budget_gb_coarsening_20261019/analysis_20261020/results/REPORT.md)

结论：球级训练在部分高噪声图上有超出目标平滑的增量；当前留一不纯度粒度评分暂缓，完整效率门槛未过。三seed为描述性筛查，不能概括为完整方法成功。[方向历史与防重复记录](gb_c1_ratio_success_20260609/results_ratio_c1_20260609/experiments/budget_gb_coarsening_20261019/02_experiment_history_and_lessons.md)。

2026-10-20实验后裁决：停止以当前R3+粗图训练组合作为新论文主线，不再追加评分调参。保留的总体分布监督仅为待检验候选，本轮未启动新训练。

[实验后重设计草案](gb_c1_ratio_success_20260609/results_ratio_c1_20260609/research/literature_reassessment_20261019/09_POST_EXPERIMENT_REDESIGN_20261020.md)。

[1080条原始逐运行记录的完整分片与重组校验](gb_c1_ratio_success_20260609/results_ratio_c1_20260609/experiments/budget_gb_coarsening_20261019/analysis_20261020/results/raw_results_parts/README.md)。Git直连和大文件传输失败，GitHub副本采用分片；本机原gzip保留，原始预测NPZ和日志仍在本机。

以下为2026-10-19初始研究快照入口，历史状态以最新结果报告为准。

# 新算法研究快照：预算约束粒球图粗化

分支：`codex/budget-gb-coarsening-20261019`。设计、36篇文献笔记、理论验证和E0单种子冒烟记录。

[进入研究说明与复现入口](gb_c1_ratio_success_20260609/results_ratio_c1_20260609/NEW_ALGORITHM_README.md)

状态：完整新方法尚未实现；E0的效率和抗噪结论尚未确认，已保留最新独立审查。

此仓库仅保存本轮新算法研究快照。详细状态、依赖和复现说明见上述入口。
