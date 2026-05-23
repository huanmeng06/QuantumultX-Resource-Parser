# Proxy-Config-Sets

自用代理配置与远程分流规则集，主要维护 Quantumult X、Shadowrocket 与 Clash Verge Rev 配置。

## 目录

- `Rules/`：三端共用的远程分流规则。
- `Quantumult X/`：Quantumult X 配置和资源解析器。
- `Shadowrocket/`：Shadowrocket 配置。
- `Clash Verge Rev/`：Clash Verge Rev 全局扩展脚本。
- `manifest/rules.json`：三端远程规则引用的统一清单。
- `scripts/generate-rule-refs.js`：根据清单生成三端远程规则引用区。

## 维护原则

- 配置文件只保留少量手动规则、策略组、基础设置和兜底规则。
- 大批量分流规则统一放在根目录 `Rules/*.list`，通过远程规则集引用。
- `GEOIP` 和 `FINAL` 保留在主配置末尾，避免规则顺序被破坏。
- 不公开托管节点、订阅、token、证书、MITM `p12`、`passphrase` 或私有 hostname。

## GitHub Raw

本仓库规则通过 GitHub Raw 引用。路径大小写敏感，例如：

```text
https://raw.githubusercontent.com/huanmeng06/Proxy-Config-Sets/refs/heads/main/Rules/github.list
```

## 生成规则引用

三端配置中的远程规则引用区由 `manifest/rules.json` 维护。修改规则清单后运行：

```bash
node scripts/generate-rule-refs.js
```

脚本只会替换配置文件里的 generated block，策略组、手动规则和兜底规则仍然手写维护。

