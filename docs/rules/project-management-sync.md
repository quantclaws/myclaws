# Project Management Sync Policy

## Purpose
让 Leo 侧的项目管理状态自动同步到 GitHub，同时不破坏“每个业务项目一个 canonical repo”的治理规则。

## Policy
1. `myclaws` 负责承载 **管理层事实**：
   - 项目状态
   - 任务分解
   - 风险与 blocker
   - 验收记录
   - 决策索引
2. 业务代码、应用资产、测试代码、构建产物仍留在各项目自己的 canonical repo。
3. Leo 本地统一使用 `~/workspace/projects/<project>/` 作为项目管理入口；该目录应映射到 `~/workspace/myclaws/projects/<project>/`。
4. 不允许把整个 `~/workspace/` 直接纳入 `myclaws`，否则会混入：
   - 运行数据
   - 临时目录
   - 平行伪项目目录
   - 非 canonical 代码副本

## Current Mapping
- `~/workspace/projects/content-factory/` -> `~/workspace/myclaws/projects/content-factory/`

## Benefits
- Leo 的项目管理状态自动进 Git
- 各业务 repo 继续保持单一代码事实源
- 后续新项目可以复用同一入口与结构
