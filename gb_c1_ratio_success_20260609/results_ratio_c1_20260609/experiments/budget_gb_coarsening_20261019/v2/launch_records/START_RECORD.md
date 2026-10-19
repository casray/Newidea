# v2正式实验启动记录

2026-10-19，Asia/Shanghai。代码版本 d10617a。

CPU检查37项通过；独立10轮GPU连通清单16/16完成，预测、哈希、标签隔离、精确预算与成本字段审计通过。连通成绩不用于方法选择，不并入正式均值。

正式队列：1080项（1032个机制/成本/敏感性作业，48个精简E2作业），seed0/1/2全部重新运行。运行根目录：D:/codex_temp/Newidea_budget_gb_v2_20261019/formal。GPU按臂串行，预处理先在CPU完成。每臂1800秒超时，失败即停止并保留现场。

状态与结果入口：status.json、PROGRESS.md、runs.csv、summary.csv、paired_deltas.csv，原始日志logs/，逐运行JSON与预测results/。这些大型缓存及动态结果在D盘，不提交到仓库；本目录保留冻结的协议哈希与完整任务清单。后续阶段报告须以实际完成结果为准，启动记录不表示训练全部完成。

本次修正：完整GB-LCSS目标与纯LOO平均分开；共享预测CE恒等式不外推为B与C训练等价；O2仅为干净训练标签切面诊断；原节点/原图验证选主checkpoint；广播预测另选次checkpoint；完整阶段显存与重建冷成本分别记录；只按实际M配对。确认图锁定WikiCS。

恢复命令（配置与源码未改变时）：

```powershell
python -u run_suite.py --config config_v2.json --run-root D:/codex_temp/Newidea_budget_gb_v2_20261019/formal
```

执行前先检查status.json与parent_pid是否仍存活，避免重复启动。若源或配置哈希不一致，不覆盖或强行接续旧结果。
