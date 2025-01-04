# 查找域 SID

你可以使用 `--get-sid` 功能查找域 SID

```
$ nxc ldap DC1.scrm.local -u sqlsvc -p Pegasus60 -k --get-sid
LDAP        DC1.scrm.local  389    DC1.scrm.local   [*]  x64 (name:DC1.scrm.local) (domain:scrm.local) (signing:True) (SMBv1:False)
LDAPS       DC1.scrm.local  636    DC1.scrm.local   [+] scrm.local\sqlsvc 
LDAPS       DC1.scrm.local  636    DC1.scrm.local   Domain SID S-1-5-21-2743207045-1827831105-2542523200
```
