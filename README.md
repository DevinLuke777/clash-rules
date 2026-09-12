# clash-rules

一些 Clash / mihomo 规则集。给需要在 Clash 配置里分流特定地区/服务的人用。

## 规则集

### LatinAmerica.list

**拉美 18 国 Mercado Libre 域名表**（用于 Clash `拉美` 策略组）

- 33 个域名
- 18 国 Mercado Libre 子站
- 5 个共用/资产域名（`mercadolibre.com`, `mlstatic.com`, `ml.com`, `mercadoshops.com`, `mercadoclics.com`）

**覆盖国家**：🇦🇷 🇧🇷 🇲🇽 🇨🇱 🇨🇴 🇵🇪 🇺🇾 🇻🇪 🇪🇨 🇧🇴 🇵🇾 🇨🇷 🇩🇴 🇬🇹 🇭🇳 🇳🇮 🇸🇻 🇵🇦

**用法**：

clash.yaml 配置：
```yaml
rule-providers:
  latam:
    type: http
    behavior: domain
    format: text
    url: "https://raw.githubusercontent.com/DevinLuke777/clash-rules/main/LatinAmerica.list"
    path: ./rule-providers/latam.yaml
    interval: 86400

proxy-groups:
  - name: 拉美
    type: select
    proxies: [国外, 自动选择, 手动选择, DIRECT]

rules:
  - RULE-SET,latam,拉美
```

## 来源

- 手写 + 参考 [github.com/blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) 的 `Mercadolibre.list`（如果存在）

## 许可

MIT
