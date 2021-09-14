# How to check early VM crash
```
# virsh dumpxml vm
...
<serial type="pty">
 <log file="/var/log/libvirt/serial.log" append="off"/>
</serial>
```
