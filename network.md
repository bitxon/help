# Network tools

## Netcat

Check if port open
```shell
nc -G 3 -zv example.com 80
```
 -  Port Open | Service Listening - `Connection to example.com port 80 [tcp/http] succeeded!`
 -  Port Open | Service Not Listening - `nc: connectx to localhost port 80 (tcp) failed: Connection refused`
 -  Port Close | Service N/A - `nc: connectx to example.com port 22 (tcp) failed: Operation timed out`


## Lsof

Check busy ports on local machine
```shell
lsof -i -n -P | grep TCP | grep LISTEN
```