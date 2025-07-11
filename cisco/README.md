# RUNNING

```php
containerlab deploy -t cisco.yml
```

# CONFIG R1

```php
docker exec -it clab-cisco-r1 vtysh
```

setelah itu akan muncul <br>
Hello, this is FRRouting (version 8.4_git). <br>
Copyright 1996-2005 Kunihiro Ishiguro, et al.

r1#

## CONFIG ETH1

r1#

```php
conf t
```

r1(config)#

```php
interface eth1
```

r1(config-if)#

```php
ip address 10.0.0.1/30
no shutdown
exit
```

## CONFIG ETH2

r1(config)#

```php
interface eth2
```

r1(config-if)#

```php
ip address 192.168.2.1/24
no shutdown
exit
```

r1(config)#

```php
ip forwarding
exit
```

## ADDED ROUTE R1

r1#

```php
conf t
```

r1(config)#

```php
ip route 192.168.2.0/24 10.0.0.2
```

r1#

```php
write
```

## CONFIG H1

```php
docker exec -it clab-cisco-h1 sh
```

```php
ip addr add 192.168.1.10/24 dev eth1
ip route del default
ip route add default via 192.168.1.1
```

## CEK PING KONEKSI DI H1 ke H2

```php
docker exec clab-cisco-h1 ping 192.168.2.10
```

# CONFIG R2

```php
docker exec -it clab-cisco-r2 vtysh
```

setelah itu akan muncul <br>
Hello, this is FRRouting (version 8.4_git). <br>
Copyright 1996-2005 Kunihiro Ishiguro, et al.

r2#

## CONFIG ETH1

r2#

```php
conf t
```

r2(config)#

```php
interface eth1
```

r2(config-if)#

```php
ip address 10.0.0.2/30
no shutdown
exit
```

## CONFIG ETH2

r2(config)#

```php
interface eth2
```

r2(config-if)#

```php
ip address 192.168.2.1/24
no shutdown
exit
```

r2(config)#

```php
ip forwarding
exit
```

## ADDED ROUTE R2

r2#

```php
conf t
```

r2(config)#

```php
ip route 192.168.1.0/24 10.0.0.1
```

r2#

```php
write
```

## CONFIG H2

```php
docker exec -it clab-cisco-h2 sh
```

```php
ip addr add 192.168.2.10/24 dev eth1
ip route del default
ip route add default via 192.168.2.1
```

## CEK PING KONEKSI DI H2 ke H1

```php
docker exec clab-cisco-h2 ping 192.168.1.10
```
