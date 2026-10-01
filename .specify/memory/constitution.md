# hermesIOS (scarf) Constitution

> iOS 应用项目（自维护 fork，随上游模板周期性同步）。仓库自带 Memophant 记忆系统：`.memory/`、`wiki/`、`design/`、`code/`、`documents/`、`vendors/`、`templates/`、`TASKS.md`、`tasks/` 为托管层。

## Core Principles

### I. 记忆系统是唯一真源 (Memory Is the Source of Truth — NON-NEGOTIABLE)
- 先搜索 `.memory/` 再假设；持久决策/发现写入记忆笔记或 wiki，不写进 AGENTS.md/CLAUDE.md，也不手抄平行文档
- charter（`.memory/charter.md`）优先级最高：charter > 记忆笔记 > 仓库指导文件 > 会话指引

### II. 托管层提交纪律 (Managed-Tier Commit Discipline)
- 托管层文件由 Memophant 逐层提交（含密钥扫描），禁止 `git add/commit`；其保持 dirty 属正常状态
- 托管层之外的路径可正常提交；提交须单一主题

### III. 上游同步兼容 (Upstream-Sync Compatibility)
- 本仓库随上游模板周期性同步；维护性提交不得阻塞或破坏 `sync-upstream` 工作流
- 尽量通过仓库既定覆盖机制实现定制，少内联篡改上游生成文件

### IV. 验证前置 (Verify Before Claim)
- 修复/特性提交附构建或运行级验证证据；未验证项在说明中显式标注

## Governance
- 修订随 commit 说明理由，版本与日期更新

**Version**: 1.0.0 | **Ratified**: 2026-10-02 | **Initial draft**: 基于仓库现状证据起草（AI-assisted, 鲸）
