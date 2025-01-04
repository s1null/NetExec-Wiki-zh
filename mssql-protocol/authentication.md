# 身份认证

## 测试凭证

你可以使用两种方法通过 MSSQL 进行身份认证:`windows` 或 `local`(默认:`windows`)。要使用本地认证,添加 `--local-auth` 标志

### **Windows 认证**

1. 当 SMB 端口开放时

```
#~ nxc mssql 10.10.10.52 -u james -p 'J@m3s_P@ssW0rd!'
```

1. 当 SMB 端口关闭时,添加 `-d DOMAIN` 标志

```
#~ nxc mssql 10.10.10.52 -u james -p 'J@m3s_P@ssW0rd!' -d HTB
```

预期结果:

```
MSSQL       10.10.10.52     1433   MANTIS           [+] HTB\james:J@m3s_P@ssW0rd! 
```

### **本地认证**

```
#~ nxc mssql 10.10.10.52 -u admin -p 'm$$ql_S@_P@ssW0rd!' --local-auth
```

预期结果:

```
MSSQL       10.10.10.52     1433   None             [+] admin:m$$ql_S@_P@ssW0rd! (Pwn3d!)
```

### 指定端口

```
#~ nxc mssql 10.10.10.52 -u admin -p 'm$$ql_S@_P@ssW0rd!' --port 1434
```
