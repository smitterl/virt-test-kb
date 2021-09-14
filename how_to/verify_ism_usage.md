# How to verify ISM usage
```
# yum install -y smc-tools
host1 # smc_chk -S
host2 # smc_chk -C <host1_ip> -p <port>
```
