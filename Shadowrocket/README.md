# Shadowrocket Rules

自用 Shadowrocket 远程分流规则。

## 使用方式

1. 把本目录提交到 GitHub 公开仓库。
2. 将 `Shadowrocket.remote-template.conf` 里的 `<YOUR_GITHUB_USERNAME>/<YOUR_REPO>` 替换成自己的 GitHub 用户名和仓库名。
3. 在 Shadowrocket 中使用精简后的配置，远程规则会从 `shadowrocket/rules/*.list` 拉取。

## 注意

- 不要公开托管节点、订阅、token、证书、MITM ca-p12、ca-passphrase。
- 少量手动规则建议继续留在主配置本地，方便临时调整。
- `GEOIP` 和 `FINAL` 保留在主配置，避免规则顺序被破坏。
