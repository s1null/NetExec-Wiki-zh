# 🆕 导出User Local Security Questions

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限
{% endhint %}

新的 NetExec 模块，用于导出本地用户的安全问题（如果有的话）。

```
$ nxc smb <ip> -u user -p pass -M security-questions
```
