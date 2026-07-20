小火箭配置@Shadowrocket-ADBlock-Rules-Forever  
https://github.com/Johnshall/Shadowrocket-ADBlock-Rules-Forever

Singbox全配置@pk-box-singbox配置汇总
https://github.com/huixiao666/pk-box

Clash配置@MIHOMO_YAMLS
https://github.com/HenryChiao/MIHOMO_YAMLS

Singbox_proxy_config
https://github.com/kj163kj/singbox_proxy_config

Substore脚本@scripts
https://github.com/xream/scripts

Anywhere-rules
https://github.com/chikacya/anywhere-rules

规则大全@ios_rule_script
https://github.com/blackmatrix7/ios_rule_script


dns:
  bootstrap:
  - system
  upstreams:
    Domestic-DNS:
    - 223.5.5.5
    - 119.29.29.29
    Domestic-Encrypted-DNS:
    - https://dns.alidns.com/dns-query
    - https://doh.pub/dns-query
    Foreign-Encrypted-DNS:
    - https://cloudflare-dns.com/dns-query
    - https://dns.google/dns-query
  forward:
  - proxy_rule_set:
      match: https://github.com/Repcz/Tool/raw/X/Egern/Rules/Reject.yaml
      value: REJECT
      disabled: false
  - proxy_rule_set:
      match: https://github.com/Repcz/Tool/raw/X/Egern/Rules/ChinaDomain.yaml
      value: Domestic-DNS
      disabled: false
  - domain_wildcard:
      match: '*'
      value: Domestic-Encrypted-DNS
      disabled: false
  hosts:
    dns.google:
    - 8.8.8.8, 8.8.4.4, 2001:4860:4860::8888, 2001:4860:4860::8844
    cloudflare-dns.com:
    - 104.16.249.249, 104.16.248.249, 2606:4700::6810:f8f9, 2606:4700::6810:f9f9
    dns.alidns.com:
    - 223.5.5.5, 223.6.6.6, 2400:3200:baba::1, 2400:3200::1
    doh.pub:
    - 1.12.12.12, 120.53.53.53
    dot.pub:
    - 1.12.12.12, 120.53.53.53
  proxy_nameservers:
  - 119.29.29.29
  - 223.5.5.5
