# UPSTREAM_SYNC — hermesIOS 同步维护策略

## 上游
- **Upstream**: https://github.com/awizemann/scarf (MIT License)
- **本项目**: https://github.com/x7peeps/hermesIOS
- **基线**: Scarf v3.3.0 (upstream main @ 48059a2, 2026-09-22)

## 定位
Scarf 是 Hermes AI agent 的原生 macOS/iOS 客户端（Swift 6 / SwiftUI，
多窗口、多服务器 SSH、chat/dashboard/memory/cron/MCP）。
本仓库持续跟进上游版本，同时维护我们自己的增量定制。

## 同步策略（自动化，见 .github/workflows/sync-upstream.yml）
1. **每日 UTC 22:00**（北京时间早 6 点）自动检查上游 main 与最新 release tag。
2. 上游有新提交 → fast-forward 合并进 `main` 并推送（保持历史线性）。
3. 上游发新 release tag（`v*.*.*`）→ 同步打同名 tag 到本仓库。
4. `our/` 分支保存我们的自有定制；上游同步不触碰该分支。
   需要时将 `our/` rebase 到新 `main` 上（人工决策，避免自动合并冲突损坏定制）。

## 冲突处理
- 自动同步只做 **fast-forward**；一旦出现分叉（我们在 main 上有自有提交），
  workflow 会停在一个标注 issue 上，转人工 rebase。

## 本地手动同步
```bash
cd ~/Documents/我的项目/hermesIOS
git remote add upstream https://github.com/awizemann/scarf.git  # 如未添加
https_proxy=http://127.0.0.1:7890 git fetch upstream main --depth 50
git merge --ff-only upstream/main
git push origin main
```

## 版本兼容
- 上游 README 声明支持 Hermes **v0.6 → v0.21+**（capability-gating 自适应）。
- Hermes 最新 release: **v0.21.4 (v2026.9.21)** — Scarf v3.3.0 已覆盖。
- 每次上游大版本同步后，人工核对 `scarf` 内 Hermes capability gate 是否覆盖最新版。
