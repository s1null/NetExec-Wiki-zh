# BloodHound 数据采集

NetExec 内置了 BloodHound 收集器。要配置名称服务器、DNS 超时或使用 TCP 进行 DNS 解析，请查看 NetExec 命令行选项中的 [dns](../getting-started/dns-options.md)。

```
nxc ldap <ip> -u user -p pass --bloodhound --collection All
```

#### 指定 BloodHound 收集方法
```
nxc ldap <ip> -u user -p pass --bloodhound --collection Method1,Method2
```

其他收集方法可以在 BloodHound.py 官方文档 [这里](https://github.com/dirkjanm/BloodHound.py/blob/master/README.md#usage) 找到。
