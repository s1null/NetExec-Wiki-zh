# ➡ 设置 Tab 补全

## 使用 argcomplete

目前,我们使用 [argcomplete](https://github.com/kislyuk/argcomplete) 通过 argparse 自动进行 tab 补全。

一旦你全局安装了 nxc,执行以下操作:

{% hint style="info" %}
建议使用 pipx 进行全局安装
{% endhint %}

{% code overflow="wrap" fullWidth="false" %}
```
sudo apt install python3-argcomplete

# 对于 Bash
register-python-argcomplete nxc >> ~/.bashrc

# 对于 Zsh
register-python-argcomplete nxc >> ~/.zshrc
```
{% endcode %}

打开一个新的 shell 就可以开始使用了:

```
NetExec
netexec
nxc
```
