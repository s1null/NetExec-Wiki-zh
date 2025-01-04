# BloodHound 集成

当找到账户时,NetExec 会在 BloodHound 中将用户设置为"已拥有"！当 lsassy 在一次转储中找到 20 个凭证时非常有用 :)

首先你需要在你的主目录中配置配置文件: `~/.nxc/nxc.conf` 并添加以下行:

```
[BloodHound]
bh_enabled = True
bh_uri = 127.0.0.1
bh_port = 7687
bh_user = user
bh_pass = pass
```

要直接导入数据,请参考此页面:

{% content-ref url="../ldap-protocol/bloodhound-ingestor.md" %}
[bloodhound-ingestor.md](../ldap-protocol/bloodhound-ingestor.md)
{% endcontent-ref %}
