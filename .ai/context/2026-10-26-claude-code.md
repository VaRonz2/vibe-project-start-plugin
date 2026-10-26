# 上下文存档：vibe-project-start-plugin（2026-10-26）

> 写入：Claude Code，2026-10-26，按 Zhu「每个仓库都需要」统一生成。内容取自本仓库 git 历史、README、STATE、zhu-ledger Issue 和 Claude 项目记忆；**不含**未提交改动的内容，只列文件名。接手前仍以仓库内 STATE / BACKLOG / 代码为准。

## 1. 基本信息
- 路径：`/Users/zhuzhu/Projects/vibe-project-start-plugin`
- 当前分支：`main`
- 远端：https://github.com/VaRonz2/vibe-project-start-plugin.git
- 最后提交：2026-06-12 ZHUZHU：Initial release of Vibe Project Start plugin

## 2. 项目是什么
摘自 `README.md` 开头：

~~~~
# Vibe Project Start

Vibe Project Start is a Codex plugin that helps prepare AI-built projects before coding starts.

It gives Codex a lightweight kickoff workflow for:

- Defining the project brief and core user loop
- Scoping the MVP before feature coding
- Writing milestone exit criteria
- Setting Git checkpoint discipline
- Establishing AI collaboration roles
- Preparing an optional frontend skeleton for web/app projects

The bundled skill is `vibe-project-start`.
~~~~

## 3. 状态文件
### `.ai/product-os-v2/STATE.md`（前 25 行）

~~~~
# STATE

```yaml
task_id: "TASK-YYYYMMDD-001"
state_version: 1
last_updated_by: "Pi"
last_updated_at: "YYYY-MM-DDThh:mm:ssZ"
current_owner: "Pi"
current_executor: "None"
current_phase: "IDLE"
verification: "NOT_STARTED"
open_p0_p1: []
next_action: "Create TASK PACKAGE"
```

## State Integrity

每次写入必须原子更新 `state_version`，并记录更新者与时间。Agent 接收任务时必须声明所读版本；若版本不是当前版本，立即停止写入、重新读取 STATE/DECISIONS，并由 Pi 重新授权。STATE 只描述当前事实，不保存历史叙述。
~~~~

### `STATE.md`（前 25 行）

~~~~
# STATE

当前状态由 [.ai/product-os-v2/STATE.md](.ai/product-os-v2/STATE.md) 管理。请勿在此复制另一份可变状态。
~~~~

### `BACKLOG.md`（前 25 行）

~~~~
# BACKLOG

- [ ] （P2/P3 与未排期事项写这里；P0/P1 必须出现在 STATE.open_p0_p1）
~~~~

### `DECISIONS.md`（前 25 行）

~~~~
# DECISIONS

只记录仍然有效的长期决策（不是聊天流水）。

- 采用 Product OS v2（`.ai/product-os-v2/`）作为本项目工程控制平面。
~~~~


## 4. 最近 15 次提交

~~~~
2026-06-12 31d71a5 ZHUZHU：Initial release of Vibe Project Start plugin
~~~~

## 5. 本地分支（按最近提交）

~~~~
2026-06-12 main
~~~~

## 7. 未提交改动（只列文件名，存档时未提交、未修改）

~~~~
?? .ai/
?? AGENTS.md
?? BACKLOG.md
?? DECISIONS.md
?? PRODUCT.md
?? STATE.md
?? pi.md
~~~~

## 8. zhu-ledger 相关 Issue

（无 `proj:vibe-project-start-plugin` 标签的 Issue）
