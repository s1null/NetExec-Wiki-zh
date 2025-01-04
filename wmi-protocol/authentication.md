# 身份认证

## 测试凭证

你可以使用两种方法通过 WMI 进行身份认证：`windows` 或 `local`（默认：`windows`）。要使用本地认证，添加 `--local-auth` 标志

### **Windows 认证**

- 当 SMB 端口开放时

```
#~ nxc wmi 10.10.10.52 -u james -p 'J@m3s_P@ssW0rd!'
```

- 当 SMB 端口关闭时，添加 `-d DOMAIN` 标志

```
#~ nxc wmi 10.10.10.52 -u james -p 'J@m3s_P@ssW0rd!' -d HTB
```

预期结果：

```
WMI       10.10.10.52     1433   MANTIS           [+] HTB\james:J@m3s_P@ssW0rd! 
```

### **本地认证**

```
#~ nxc wmi 10.10.10.52 -u admin -p 'admin' --local-auth
```
