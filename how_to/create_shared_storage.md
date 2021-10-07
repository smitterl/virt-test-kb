# How to create shared storage with NFS
```
# yum install -y nfs-utils
# mkdir -p /srv/shared
# echo "/srv/shared *"
# systemctl restart nfs-server
# exportfs -r
```
