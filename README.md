# chn-iplist

数据来源 [ APNIC Delegated List](http://ftp.apnic.net/apnic/stats/apnic/delegated-apnic-latest)，使用 mosdns 项目 [ip 合并优化脚本](https://github.com/IrineSistiana/mosdns/blob/main/scripts/update_chn_ip_domain.py)将其转化为 txt 文件以在路由器上使用，并以此制作 Shadowrocket、Quantumult、Kitsunebi、acl、v2rayNG、v2rayN、pac、Qv2ray、AnXray、SagerNet 规则和 v2ray 配置内嵌规则，包含 chn-ip 列表及少量广告屏蔽规则。每月更新一次。

## Subscribe URL:

| ios                                                                                                                                                                                                                          | android                                                                                                                                                                                              | 其他                                                                                                                                                                                                                                                                                                  |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| [Shadowrocket](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Shadowrocket.conf)                                                                                                                            | [Kitsunebi-android](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/backup/Kitsunebi-android.conf)                                                                                   | chnroute [ipv4与ipv6合并版](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute.txt) \| [纯ipv4版](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute-ipv4.txt) \| [纯ipv6版](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute-ipv6.txt) |
| [Quantumult](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/backup/Quantumult.conf) \| [Quantumult(X) (no chn-ip)](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Quantumult(X)_noIP.conf) | [acl (no ban ads)](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chn.acl) \| [acl (ban ads)](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/backup/chn_banad.acl) | [pac](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute.pac) （默认非 chn-ip 网站走 socks5 localhost:1080）                                                                                                                                                                          |
| [Kitsunebi](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Kitsunebi.conf)                                                                                                                                  |                                                                                                                                                                                                      | [v2rayN (no chn-ip)](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/v2rayN_subrules_whitelist)                                                                                                                                                                           |

## 需手动更新：

#### v2rayN(G)

分别将 [proxy](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/proxy.txt)、[direct-noip](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/direct-noip.txt)、[block](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/block.txt) 规则复制粘贴至应用内。

#### Qv2ray

下载[no-chnip方案](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Qv2ray-noip.json)后导入。

#### AnXray & SagerNet

分别将 [domain 屏蔽规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/block-domain.txt)、[domain 代理规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/proxy-domain.txt)、[ip 代理规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/proxy-ip.txt)、[domain 绕过规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/direct-domain.txt)、[ip 绕过规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/direct-ip.txt)复制粘贴至应用内路由对应分类。

#### v2ray 配置内嵌规则

将[规则文本](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2ray-config_rule.json)加入配置文件 routing 对应区域。

## PS.

1. Shadowrocket (ios) 等有 ipv6 设置的，若服务器不支持 ipv6 且连接失败，请设为仅 IPV4。
2. v2rayN(G)、AnXray、SagerNet  和 Qv2ray 支持调用 dat 文件，提供无 chnip 规则版，可配合使用 [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat/releases) 加强版规则。Linux 可用 `bash <(curl -L https://raw.githubusercontent.com/PaPerseller/fhs-install-v2ray/master/xray-install-dat-release.sh)` 更新至 Xray 资源文件夹。
3. AnXray、SagerNet 部分规则由 Loyalsoldier 加强版规则特殊支持，建议将 应用设置-路由资源更新源 设为 Loyalsoldier/v2ray-rules-dat 并在 路由设置-管理路由资源 内更新。
4. v2rayN(G) 已支持在线更新 geoip 数据库，本 v2rayN(G) 规则自 2022-3-15 版起不再内置 cn-ip 列表。

## 致谢

- [CIDR2PAC](https://github.com/wspl/CIDR2PAC) - A es6 script for coverting CIDRs list to PAC proxy script.
- [ACL4SSR/Clash](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash) - Clash规则碎片
- [domain-list-community](https://github.com/v2fly/domain-list-community) - Community managed domain list
- [mosdns](https://github.com/IrineSistiana/mosdns) - 插件化的 DNS 转发/分流器。
- [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) - V2Ray 路由规则文件加强版
