# Content Factory — 项目状态卡

- 项目名：Content Factory
- 管理归档仓库：`quantclaws/myclaws`
- 代码 canonical repo：`quantclaws/content-factory`
- 当前状态：MVP 已放行，进入产出质量修复与治理收口阶段

## 单一事实源划分

### 1. 代码与产品实现
- 仓库：`quantclaws/content-factory`
- 分支：`main` 为当前主线

### 2. 项目管理状态
- 位置：`myclaws/projects/content-factory/`
- 用途：状态、风险、待办、验收、决策链接

## 当前收口项

### Git 收尾
- [ ] 忽略 `logs/daily.log`
- [ ] 跟踪 `docs/cf-dly-03/PLAN.md`
- [ ] 跟踪 `first-run-sources.md`

### Quantide Daily 导出问题
- [ ] 长图内容区右侧大片空白：确认导出宽度、容器宽度、截图策略
- [ ] 日历无边框
- [ ] 存在英文未翻译
- [ ] 存在空白条目（疑似 Markdown/HTML 解析问题）

## 治理决策
- 不把整个 `leo/workspace/` 作为 git 仓库同步目标。
- 仅把 `leo/workspace/projects/` 作为 **项目管理层** 映射到 `myclaws/projects/`。
- 每个业务项目仍保持自己的 canonical repo，避免 `myclaws` 变成“第二代码仓库”。

## 遗留目录（待后续清理）
- `~/workspace/content-factory/`
- `~/workspace/content-factory-spec/`
- `~/workspace/content-factory-data/`

建议下一步：
1. 将 Leo 后续项目管理文档统一落到 `~/workspace/projects/content-factory/`
2. 逐步把旧管理文档从 `~/workspace/content-factory/` 迁移/归档到这里
3. 不迁移业务代码与运行数据
