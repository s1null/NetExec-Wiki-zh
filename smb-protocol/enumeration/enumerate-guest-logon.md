# 枚举访客登录

使用随机用户名和密码，你可以检查目标是否接受访客登录。如果接受，这意味着你所针对的服务器上的域访客账户或本地访客账户已启用。

{% hint style="danger" %}
确保密码为空
{% endhint %}

```
nxc smb 10.10.10.178 -u 'a' -p '' 
nxc smb 10.10.10.178 -u 'a' -p '' --shares
```

注意，如果域访客账户可用，你将能够使用它来发起诸如 Coerces 之类的攻击。

{% embed url="https://blog.whiteflag.io/blog/guest-vs-null-session-on-windows/" %}

### 示例

Nest 机器是使用 NetExec 进行**访客登录**的一个很好的例子

{% embed url="https://www.hackthebox.eu/home/machines/profile/225" %}
