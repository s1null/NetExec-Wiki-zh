---
description: 配置 DNS
---

# 🆕 DNS 选项

有几个选项可以用来配置使用的 DNS 服务器。\
除了强制 NetExec 使用 ipv6 外,还有选项可以手动设置 dns 服务器、设置 dns 超时或配置使用 tcp 进行 dns 解析:

```
netexec <protocol> <target(s)> -u username -p password --dns-server <dns-server ip>
netexec <protocol> <target(s)> -u username -p password --dns-timeout <seconds>
netexec <protocol> <target(s)> -u username -p password --dns-tcp    # Use TCP for DNS
netexec <protocol> <target(s)> -u username -p password -6           # Enforce ipv6

```
