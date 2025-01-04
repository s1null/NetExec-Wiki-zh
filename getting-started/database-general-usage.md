# 数据库一般用法

## 数据库一般用法

nxc 会自动将所有使用/转储的凭证(以及其他信息)存储在其数据库中,该数据库在首次运行时设置。

每个协议都有自己的数据库,这使事情变得更加合理,并允许一些很棒的可能性。此外,还有工作区(像 Metasploit),用于分隔不同的任务/渗透测试。

有关特定协议数据库的详细信息和用法,请参阅相应的 wiki 部分。

所有工作区及其相关数据库都存储在 `~/.nxc/workspaces` 中

## 与数据库交互

nxc 附带了一个辅助命令行脚本 `nxcdb`,它抽象了与后端数据库的交互。输入命令 `nxcdb` 将进入命令 shell:

```
#~ nxcdb
nxcdb (default) >
```

## 列出帮助

随时输入 "help" 获取命令列表:

```
nxcdb (default)(smb) > help

已记录的命令 (输入 help <主题>):
========================================
clear_database  creds  dpapi  exit  export  groups  help  hosts  shares  wcc

未记录的命令:
======================
back  import
```

## 工作区

默认工作区名称为 'default'(如提示符中所示),一旦选择了工作区,你在 nxc 中所做的一切都将存储在该工作区中。

创建工作区:

```
nxcdb (default) > workspace create test
[*] Creating workspace 'test'
<-- CUT -->
nxcdb (test) >
```

切换工作区:

```
nxcdb (test) > workspace default
nxcdb (default) >
```

列出工作区:

```
nxcdb (test) > workspace list
[*] Enumerating Workspaces
default
==> test
```

## 访问协议的数据库

要访问协议的数据库,只需运行 `proto <protocol>`,例如:

```
nxcdb (test) > proto smb
nxcdb (test)(smb) >
```

从提示符可以看出,我们现在在名为 'test' 的工作区中使用 SMB 协议的数据库。每个协议数据库都有自己的命令集,你可以运行 `help` 查看可用命令。

请参阅相应的 wiki 部分了解特定协议数据库的详细信息和用法。

切换协议数据库:

```
nxcdb (test)(smb) > back
nxcdb (test) > proto http
nxcdb (test)(http) >
```

## :new: 从数据库导出

你可以通过几种不同的方式从数据库导出信息

```
nxcdb (test)(smb) > export shares detailed file.csv
```

要了解所有最新选项,输入 `help export`

```
nxcdb (default)(smb) > help export

export [creds|hosts|local_admins|shares|signing|keys] [simple|detailed|*] [filename]
导出信息到指定文件

* hosts 除了 simple 和 detailed 外还有第三个选项: signing - 这只会写入启用了签名的主机的 ip 列表
* keys 的第三个选项是 "all" 或要导出的密钥的 id
    export keys [all|id] [filename]
```
