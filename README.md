# hermesIOS

**Native macOS & iOS app for the [Hermes AI agent](https://github.com/hermes-ai/hermes-agent)** — based on the excellent open-source [Scarf](https://github.com/awizemann/scarf) (MIT), continuously synced and maintained by [x7peeps](https://github.com/x7peeps).

> 上游项目 Scarf 是 Hermes AI agent 的原生客户端（Swift 6 / SwiftUI）：多窗口、
> 多服务器（本地 + SSH 远程）、Chat / Dashboard / Sessions / Memory / Cron / MCP。
> 本仓库每日自动跟进上游版本，同时沉淀我们自己的定制（`UPSTREAM_SYNC.md`）。

## Sync status

| | |
|---|---|
| Base | Scarf v3.3.0 (upstream @ `48059a2`, 2026-09-22) |
| Upstream | https://github.com/awizemann/scarf |
| Auto-sync | daily 06:00 CST via [.github/workflows/sync-upstream.yml](.github/workflows/sync-upstream.yml) |
| Hermes compatibility | v0.6 → v0.21+ (capability-gated; latest Hermes release v0.21.4) |
| License | MIT (inherited from upstream) |

## Why this fork exists

- **版本跟进**: 每日自动 fast-forward 上游 main，同步 release tags
- **自有定制**: 我们的增量改动在独立提交 / 分支上，不会被自动同步覆盖
- **冲突可追溯**: 一旦与上游分叉，自动开 issue 转人工 rebase，绝不静默覆盖

## Build

See upstream [BUILDING.md](BUILDING.md) — Xcode 16+, Swift 6, macOS 14.6+ / iOS 18+.

## Credits

All credit for the original app goes to [@awizemann](https://github.com/awizemann)
and the Scarf contributors. This repository is a maintained downstream distribution.
