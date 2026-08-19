## 更新日志

### Tips：
1. **保留 `China-IP,no-resolve`（规则默认）**：
   * **DNS**：规则匹配时不触发递归解析，**防止 DNS 泄露**（境外域名绝不上报国内 DNS），纯本地匹配消除首次建连时延。
   * **潜在分流影响**：判定完全依赖预设域名库；未收录的小众大陆域名将无法触发国内 IP 判定，**可能直接穿透至末尾兜底规则误走代理**，且其 UDP 443 会被拦截并回退至 TCP 传输。

### 📅 2026.08.01

1. TUN 模式新增 `route-exclude-address-set` 底层路由排除功能
2. 绕过大陆 `Private-IP`、`Trackers-IP` 和 `China-IP` 流量
3. 新增“链式代理”策略组，“家宽-手选”节点组
4. DOMAIN-SUFFIX,steamcontent.com,国内直连 ，强制拦截所有 Steam 下载节点走直连
5. 节点策略组新增 `empty-fallback: "REJECT"` 参数，修正此前节点组无节点时会自动使用 `COMPATIBLE`（直连）的安全隐患，现节点组没有匹配到节点时会直接拦截，彻底防止流量侧漏
6. 添加hosts：services.googleapis.cn: services.googleapis.com，解决谷歌商店无法下载的问题
7. Darwin 性能优化（macOS 原生网络 API 优化），开启 `recv-msg-x: true` 在高速下载时降低 CPU 占用
8. Darwin 性能优化（macOS 原生网络 API 优化），默认关闭`send-msg-x: false` 防止在多线程大流量下载时诱发内核假死


---

### 📅 2026.05.18
1. 修正smart权重锚点写法
   
---

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
