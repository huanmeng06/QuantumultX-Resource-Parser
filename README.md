# Proxy-Config-Sets

自用代理配置与远程分流规则集，主要维护 Quantumult X 与 Shadowrocket 两套配置。

## 目录

- `Quantumult X/`：Quantumult X 配置、资源解析器和远程分流规则。
- `Shadowrocket/`：Shadowrocket 配置和远程分流规则。

## 维护原则

- 配置文件只保留少量手动规则、策略组、基础设置和兜底规则。
- 大批量分流规则拆到各自的 `rules/*.list`，通过远程规则集引用。
- `GEOIP` 和 `FINAL` 保留在主配置末尾，避免规则顺序被破坏。
- 不公开托管节点、订阅、token、证书、MITM `p12`、`passphrase` 或私有 hostname。

## GitHub Raw

本仓库规则通过 GitHub Raw 引用。路径大小写敏感，例如：

```text
https://raw.githubusercontent.com/huanmeng06/Proxy-Config-Sets/main/Shadowrocket/rules/github.list
https://raw.githubusercontent.com/huanmeng06/Proxy-Config-Sets/main/Quantumult%20X/rules/github.list
```
