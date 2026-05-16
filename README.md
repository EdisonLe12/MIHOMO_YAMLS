## 更新日志

### 📅 2026.04.22
1. 策略组优化：添加手选策略组、Smart 节点权重锚点。
2. 规则更新：添加 PayPal 专属分流规则。
3. 界面优化：隐藏节点地区故障转策略组，仅在分流策略组显示故障转策略组。

---

### 📅 2026.04.13
1. DNS 规则：添加 `Encrypted_DNS_IP` 和 `Category-DoH` 规则走 `REJECT`。
   > Tips：禁止 APP 走软件内置加密 DNS，尽量走下游 DNS。

---

### 📅 2026.04.08
1. 请求头更新：`BaseProvider` 请求头更新 `header` 为 `{User-Agent: ['clash.meta', 'mihomo/1.9.22']}`。
2. 间隔调整：将 `fallback`、`load-balance`、`smart` 等策略组的健康筛查测试间隔调整为 `60s`。
3. 功能添加：添加故障转移前置锚点、低倍率故障转 + `smart` 策略组。
4. 问题修复：修正节点正则筛选。
