# RUNNING

```bash
containerlab deploy -t cisco.yml
```

# CONFIG R1

```bash
docker exec -it clab-cisco-r1 vtysh
```

setelah itu akan muncul <br>
Hello, this is FRRouting (version 8.4_git). <br>
Copyright 1996-2005 Kunihiro Ishiguro, et al.

r1#

## CONFIG ETH1

r1#

```bash
conf t
```

r1(config)#

```bash
interface eth1
```

r1(config-if)#

```bash
ip address 10.0.0.1/30
no shutdown
exit
```

## CONFIG ETH2

r1(config)#

```bash
interface eth2
```

r1(config-if)#

```bash
ip address 192.168.1.1/24
no shutdown
exit
```

r1(config)#

```bash
ip forwarding
```

## ADDED ROUTE R1

r1(config)#

```bash
ip route 192.168.2.0/24 10.0.0.2
exit
```

r1#

```bash
write
exit
```

# CONFIG R2

```bash
docker exec -it clab-cisco-r2 vtysh
```

setelah itu akan muncul <br>
Hello, this is FRRouting (version 8.4_git). <br>
Copyright 1996-2005 Kunihiro Ishiguro, et al.

r2#

## CONFIG ETH1

r2#

```bash
conf t
```

r2(config)#

```bash
interface eth1
```

r2(config-if)#

```bash
ip address 10.0.0.2/30
no shutdown
exit
```

## CONFIG ETH2

r2(config)#

```bash
interface eth2
```

r2(config-if)#

```bash
ip address 192.168.2.1/24
no shutdown
exit
```

r2(config)#

```bash
ip forwarding
exit
```

## ADDED ROUTE R2

r2#

```bash
conf t
```

r2(config)#

```bash
ip route 192.168.1.0/24 10.0.0.1
```

r2#

```bash
write
```
