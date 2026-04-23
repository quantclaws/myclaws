# Content Factory — 项目状态卡

- 项目名：Content Factory
- 管理归档仓库：`quantclaws/myclaws`
- 代码 canonical repo：`quantclaws/content-factory`
- 当前状态：进入“统一最终需求 → 文档纠偏 → 代码快迭代”阶段；暂停继续沿错误假设扩展功能

## 单一事实源划分

### 1. 代码与产品实现
- 仓库：`quantclaws/content-factory`
- 分支：`main` 为当前主线

### 2. 项目管理状态
- 位置：`myclaws/projects/content-factory/`
- 用途：状态、风险、待办、验收、决策链接

## 当前收口项

### 文档与需求统一（最高优先级）
- [ ] 将 Leo 本地 PRD 正式归档进 canonical repo：`docs/prd/PRD-v1.md`
- [ ] 重写/修正 `docs/specs/spec.md` 中与抓取、筛选、组稿相关的主链路定义
- [ ] 标记已失效或被替代的旧设计，不允许与新要求并存
- [ ] 把“需求变更治理”写入项目规则并在 Content Factory 执行

### 已确认需要纠偏的设计点
- [ ] 取消“信源静态绑定栏目”作为组稿依据；改为“先抓，再由 LLM 按栏目 prompt 分类”
- [ ] 明确抓取与组稿分离：组稿只消费本地新增/未处理文章
- [ ] 固化排他性分类顺序：学术研究 → 大厂动态 → 量化人生/职业规划 → 免费资源 → 全网热搜兜底
- [ ] 每个栏目必须有独立 prompt；批量按每 20 条送 LLM 判断

### 导出与 Git 收尾（次优先级）
- [x] 跟踪 `docs/cf-dly-03/PLAN.md`
- [x] 跟踪 `first-run-sources.md`
- [ ] 让 `logs/daily.log` 彻底退出 git 跟踪
- [x] 修复长图内容区右侧空白
- [x] 修复日历边框/表现问题
- [x] 修复英文未翻译
- [x] 修复空白条目

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
