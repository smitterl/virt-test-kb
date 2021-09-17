# How to create shared storage with NFS
```
# yum install -y nfs-utils
# mkdir -p /srv/shared
# echo "/srv/shared *" >> /etc/exports
# systemctl restart nfs-server
# exportfs -r
```
