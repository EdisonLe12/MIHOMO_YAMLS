📝 更新日志

2026.4.22

1、增加Smart节点权重锚点

2、添加PayPal规则

3、隐藏节点地区故转策略组，仅在分流策略组显示故转策略组

2026.4.13

1、添加Encrypted_DNS_IP和Category-DoH规则走REJECT。 tips：禁止APP走软件内置加密dns，尽量走下游dns




2026.4.8

1、BaseProvider请求头更新header: {User-Agent: ['clash.meta', 'mihomo/1.9.22']}

2、fallback、load-balance、smart等策略组健康筛查测试间隔调整为60s

3、添加故障转移前置描点、低倍率故转+smart策略组

4、修正节点正则筛选
