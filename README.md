## 更新日志

### 📅 2026.05.17
1. 删除微软 Teams，各游戏平台CDN下载规则，仅保留游戏平台下载兜底规则
2. 阿里云 DOH3 部分地区无法用，替换为阿里云和腾讯 DOH
3. 替换 TikTok 规则，使用聚合 MRS 规则
4. 添加 Speedtest 策略组
5. 替换加密货币 icon
   
---

### 📅 2026.04.22
1. 隐藏节点地区故转策略组，仅在分流策略组显示故转策略组
2. 添加手选策略组、Smart 节点权重描点
3. 添加 PayPal 规则

---

### 📅 2026.04.13
1. 添加 `Encrypted_DNS_IP` 和 `Category-DoH` 规则走 `REJECT`
   > tips：禁止 APP 走软件内置加密 dns，尽量走下游 dns

---

### 📅 2026.04.08
1. `BaseProvider` 请求头更新 `header`: `{User-Agent: ['clash.meta', 'mihomo/1.9.22']}`
2. `fallback`、`select`、`smart` 等策略组健康筛查测试间隔调整为 60s
3. 添加故障转移前置描点、低倍率故转 + `smart` 策略组
4. 修正节点正则筛选
