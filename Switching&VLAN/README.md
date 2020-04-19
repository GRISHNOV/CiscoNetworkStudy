<h1 align="center">VLAN</h1>

Create VLAN

```
Switch0(config)#vlan X // recommend entering it even if it was created automatically
Switch0(config-vlan)#name ######
```

For access port

```
Switch0#interface fa X/X
Switch0(config)#description “%%%%%%” // description for interface
Switch0(config-if)#switchport mode access
Switch0(config-if)#switchport access vlan X
```

For trunk port

```
Switch0(config)#interface GigabitEthernet X/X
Switch0(config-if)#description “%%%%%%” // description for interface
Switch0(config-if)#switchport mode trunk // allow all VLANs by default, see the following command
Switch0(config-if)#switchport trunk allowed vlan X,Y-Z
Switch0(config-if)#switchport trunk allowed vlan add XX // if need add new VLAN
```

For managment

```
...config vty...
Switch0(config)#interface vlan X
Switch0(config-if)#description ######
Switch0(config-if)#ip address XXX.XXX.XXX.XXX YYY.YYY.YYY.YYY
```

Vlan termination

```
Router0(config)#interface fastEthernet @/@
Router0(config-if)#no shutdown
Router0(config)#interface fa@/@.# // sub-interface
Router0(config-if)#encapsulation dot1Q #
Router0(config-if)#ip address XXX.XXX.XXX.XXX YYY.YYY.YYY.YYY
```