# Ping Sweep
Ping sweep is a method used to identify the IP address's are alive or not. You can use one of these method implementation to do ping sweep. Just copy and paste from the bellow to your beloved terminal or command line. Also, make sure you are not forget to adjust the IP addres, mask, or IP range. Feel free to develop these things but remember, this is for educational purpose only. Bravo!

## LINUX TERMINAL
``` batch
for i in {1..255} ;do (ping -c 1 172.17.1.$i | grep "bytes from" &) ;done
```

## Windows Command Line
``` shell
for /L %i in (1,1,255) do @ping -n 1 -w 200 172.17.1.%i > nul && echo 172.17.1.%i is up.
```

## Powershell
``` powershell
1..255 | % {echo "172.17.1.$_"; ping -n 1 -w 172.17.1.$_ | Select-String ttl }
```

## NMap
``` shell
nmap -sn 172.17.1.0/16
```

## Netdiscover
The disadvantage of this tool is longer than the other, but the advantage is it can't be detected by the target.
``` shell
netdiscover -p -r 172.17.1.0/16
```
