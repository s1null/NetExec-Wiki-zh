# 🆕 枚举网络接口

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

枚举主机上的网络接口：

```
nxc smb 192.168.56.11 -u USERNAME -p 'PASSWORDHERE' --interfaces
```

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>接口枚举的输出示例</p></figcaption></figure>
