# Set up Linux bridge on s390x
For a static ipv4 IP on interface enc600:

First, backup your config and take note of addresses, gateway, dns.

```
# nmcli con delete enc600
# nmcli con add type bridge ifname br0
# nmcli con modify enc600 master bridge-br0 slave-type bridge
# nmcli con modify br0 ipv4.addresses <address_from_enc600> ipv4.method manual
# nmcli con modify br0 ipv4.gateway <gateway_from_enc600>
# nmcli con modify br0 ipv4.dns <dns_from_enc600>
# nmcli con add type bridge-slave autoconnect yes con-name enc600 ifname enc600 master br0
# echo "net.ipv4.ip_forward = 1" | tee /etc/sysctl.d/99-ipforward.conf
# sysctl -p /etc/sysctl.d/99-ipforward.conf
# echo “primary” > /sys/class/net/enc600/device/bridge_reflect_promisc
# ip link set dev enc600 promisc on
# systemctl restart NetworkManager
```
