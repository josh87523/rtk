# rtk 业务与产品逻辑

## 这是什么

rtk 是一个面向 AI coding agent 的 CLI 代理层。它的产品目标不是替代 shell，而是在不改变用户命令习惯的前提下，压缩输出、降低 token 消耗、提升 agent 可消费性。

## 核心产品逻辑

- 用户仍然输入原始命令，hook/rewriter 在执行前把命令透明改写成 `rtk ...`。
- 价值来自“过滤、分组、截断、去重”四类压缩策略，而不是单纯包装已有命令。
- 这是一层横切能力：面向 Claude Code、Codex、Gemini、Cursor、Windsurf 等不同 agent 表面。

## 核心业务闭环

1. 初始化时把 rewriter/hook 接入目标 agent。
2. 用户照常发起 Bash 命令。
3. rtk 根据命令类别选择压缩策略。
4. 执行真实命令并返回 token-optimized 输出。
5. 用户和 agent 在基本不改变工作流的情况下获得更低上下文成本。

## 当前业务边界

- 这是“token economy / command UX”产品，不是项目级业务系统。
- hook 重写注册表是单一真相源；脚本层只是薄代理。
- 只有经过 Bash/hook 的命令才能自动受益，原生 `Read/Grep/Glob` 不会被自动改写。

## 推荐阅读顺序

1. `README.md`
2. `hooks/README.md`
3. `docs/TROUBLESHOOTING.md`
4. `docs/contributing/ARCHITECTURE.md`

