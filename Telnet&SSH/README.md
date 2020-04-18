<h1 align="center">Telnet&SSH</h1>

# Telnet

Config ip and mask for interface

```
Router(config)# interface fa X/X
Router(config-if)#no shutdown
Router(config-if)#ip address XXX.XXX.XXX.XXX YYY.YYY.YYY.YYY
```

Password for telenet (no password for enable mode yet)

```
Router(config)#line vty 0 4 // for 5 sessions
Router(config-line)#password ******
Router(config-line)#login // Enable password checking
```

Enable mode password

```
Router(config)#enable secret ******
```

Using 'secret' is better

```
Router(config)#enable password test
Router(config)#service password-encryption
```

For login + password (1 version)

```
Router(config)#aaa new-model
Router(config)#username ###### password ******
```

For login + password (2 version)

```
Router(config)#line vty 0 4
Router(config-line)#login local
```

# SSH

After setting up login with your username and password

```
Router(config)#hostname TEST
TEST(config)#ip domain-name test.com
TEST(config)#crypto key generate rsa
TEST(config)#line vty 0 4
TEST(config-line)#transport input ssh
```