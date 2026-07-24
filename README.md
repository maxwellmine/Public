dns:
  enable: true
  ipv6: false               
  use-system-hosts: true

  bootstrap:
    - system
    - 223.5.5.5
    - 119.29.29.29

  upstreams:
    Domestic-DNS:
      - https://dns.alidns.com/dns-query
      - https://doh.pub/dns-query

    Foreign-Encrypted-DNS:
      - https://cloudflare-dns.com/dns-query
      - https://dns.google/dns-query

  forward:
    # 广告拦截
    - proxy_rule_set:
        match: https://github.com/Repcz/Tool/raw/X/Egern/Rules/Reject.yaml
        value: REJECT
        disabled: false

    # 苹果服务
    - proxy_rule_set:
        match: https://raw.githubusercontent.com/Centralmatrix3/Matrix-io/master/Egern/Ruleset/Apple.yaml
        value: Domestic-DNS
        disabled: false

    # 国内主流域名
    - proxy_rule_set:
        match: https://github.com/Repcz/Tool/raw/X/Egern/Rules/ChinaDomain.yaml
        value: Domestic-DNS
        disabled: false

    # 兜底：国外域名走国外加密 DNS（防泄露、防污染）
    - domain_wildcard:
        match: '*'
        value: Foreign-Encrypted-DNS
        disabled: false

  hosts:
    dns.alidns.com:
      - 223.5.5.5
      - 223.6.6.6
    doh.pub:
      - 1.12.12.12
      - 120.53.53.53

  proxy_nameservers:
    - https://dns.alidns.com/dns-query
    - 119.29.29.29

  public_ip_lookup_url: https://ifconfig.me/ip









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

https://raw.githubusercontent.com/xream/scripts/main/surge/modules/sub-store-scripts/sing-box/template.js#name=机场&outbound=🕳ℹ️hk|香港|hk-auto🏷ℹ️港|hk|hongkong|🇭🇰🕳ℹ️韩国|kr-auto🏷ℹ️KR|Korea|KOR|首尔|韩🕳ℹ️台湾|tw-auto🏷ℹ️台|tw|taiwan|🇹🇼🕳ℹ️日本|jp-auto🏷ℹ️日本|jp|japan|🇯🇵🕳ℹ️新加坡|sg-auto🏷ℹ️^(?!.(?:us)).(新|sg|singapore|🇸🇬)🕳ℹ️美国|us-auto🏷ℹ️美|us|unitedstates|united states|🇺🇸🕳ℹ️全部节点

node C:\sub-store\sub-store.bundle.js

https://sub-store.vercel.app

singbox配置可视化 https://sbcv.app/


