# RUNNING

```php
containerlab deploy -t mkt.yml
```

# CONFIG R1

```bash
docker attach clab-mikrotik-r1
```

#### untuk keluar dari attach docker tekan CTRL + P + Q

```bash
system/identity/set name=R1
/ip address add address=192.168.1.1/24 interface=ether2
/ip address add address=10.0.0.1/30 interface=ether3
/ip route add dst-address=192.168.2.0/24 gateway=10.0.0.2
```

# CONFIG R2

```bash
docker attach clab-mikrotik-r2
```

#### untuk keluar dari attach docker tekan CTRL + P + Q

```bash
system/identity/set name=R2
/ip address add address=192.168.2.1/24 interface=ether2
/ip address add address=10.0.0.2/30 interface=ether3
/ip route add dst-address=192.168.1.0/24 gateway=10.0.0.1
```

# CONFIG H1

```bash
docker exec -it clab-mikrotik-h1 sh
```

```bash
ip addr add 192.168.1.10/24 dev eth1
ip route del default
ip route add default via 192.168.1.1
```

# CONFIG H2

```bash
docker exec -it clab-mikrotik-h2 sh
```

```bash
ip addr add 192.168.2.10/24 dev eth1
ip route del default
ip route add default via 192.168.2.1
```

# CHECK CONFIGURATION

```bash
docker exec -it clab-mikrotik-h1 ping 192.168.2.10
```

```bash
docker exec -it clab-mikrotik-h2 ping 192.168.1.10
```
