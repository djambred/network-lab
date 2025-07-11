# SETUP

```bash
bash -c "$(curl -sL https://get.containerlab.dev)"
```

# FULL LOOKSLIKE

```bash
r1# enable
r1# configure
r1(config)# int eth1
r1(config-if)# ip address 10.0.0.1/30
r1(config-if)# no sh
r1(config-if)# exit
r1(config)# int eth2
r1(config-if)# ip address 192.168.1.1/24
r1(config-if)# no sh
r1(config-if)# exit
r1(config)# ip forwarding
r1(config)# ip route 192.168.2.0/24 10.0.0.2
r1(config)# exit
r1# write
Note: this version of vtysh never writes vtysh.conf
Building Configuration...
Configuration saved to /etc/frr/zebra.conf
Configuration saved to /etc/frr/staticd.conf
r1#
```

```bash
r2# enable
r2# configure
r2(config)# int eth1
r2(config-if)# ip address 10.0.0.2/30
r2(config-if)# no sh
r2(config-if)# exit
r2(config)# int eth2
r2(config-if)# ip address 192.168.2.1/24
r2(config-if)# no sh
r2(config-if)# exit
r2(config)# ip forwarding
r2(config)# ip route 192.168.1.0/24 10.0.0.1
r2(config)# exit
r2# write
Note: this version of vtysh never writes vtysh.conf
Building Configuration...
Configuration saved to /etc/frr/zebra.conf
Configuration saved to /etc/frr/staticd.conf
r2#
```
