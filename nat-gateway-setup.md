### iptables

```bash
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

### /etc/sysctl.conf
```
net.ipv4.ip_forward = 1
```
```bash
sysctl -p
```
