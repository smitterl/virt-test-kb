# How to set debug logging
```
virt-admin daemon-log-filters "1:qemu 4:*"
virt-admin daemon-log-output "1:file:/var/log/libvirt/debug.log"
```

# How to re-set debug logging
```
virt-admin daemon-log-filters ""
virt-admin daemon-log-output ""
```
