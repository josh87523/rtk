# rtk Codebase Map

> 用于人和 AI 快速定位产品逻辑、运行逻辑和对应代码入口。先读 `docs/business-product-logic.md`，再按下表跳到具体模块。

## Module Entrypoints

| Area | Entry | Notes |
|---|---|---|
| 业务逻辑 | `docs/business-product-logic.md` | AI coding token 压缩层边界 |
| 项目入口 | `README.md` | 产品定位、安装和使用方式 |
| 架构 | `docs/contributing/ARCHITECTURE.md` | 命令代理架构和模块组织 |
| 技术说明 | `docs/contributing/TECHNICAL.md` | 端到端流程、hook 和 filter pipeline |
| 源码 | `src/` | Rust CLI、命令过滤器和追踪逻辑 |
| hooks | `hooks/` | agent 命令改写和集成入口 |
| 测试 | `tests/` | 过滤、追踪和集成回归 |

## Reading Contract

- 先用 `docs/business-product-logic.md` 判断这个仓库解决什么问题。
- 再按本页定位到代码或运行入口，避免从文件名猜产品逻辑。
- dated plan、archive、runtime data、generated output 只能当证据或历史参考，不能直接当当前运行合同。
- 涉及外部平台、账号、发布、支付、浏览器 profile 或凭证时，必须读真实运行面和权限边界，不能只读源码。

## Recommended First Read

1. `docs/business-product-logic.md`
2. `README.md`
3. `docs/contributing/ARCHITECTURE.md`
4. `src/`
