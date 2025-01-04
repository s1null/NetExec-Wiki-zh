---
description: NetExec 目标格式
---

# 目标格式

## 目标格式

每个协议都支持通过 CIDR 表示法、IP 地址、IP 范围、主机名、包含目标列表的文件或以上所有的组合来指定目标:

```
netexec <protocol> poudlard.wizard
```

```
netexec <protocol> 192.168.1.0 192.168.0.2
```

```
netexec <protocol> 192.168.1.0/24
```

```
netexec <protocol> 192.168.1.0-28 10.0.0.1-67
```

```
netexec <protocol> ~/targets.txt
```
