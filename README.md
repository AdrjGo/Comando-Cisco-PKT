# Comandos utilizados

## Asignación de IP

### Router 0
```bash
Router>
  enable
Router#
  conf t
Router(config)#interface Gig0/0
Router(config-if)#ip address 192.168.5.17 255.255.255.240
                  no shutdown
                  exit
                  
Router(config)#interface Se0/3/0
Router(config-if)#ip address 192.168.5.33 255.255.255.240
                  no shutdown
                  exit
                  
Router(config)#interface Se0/3/1
Router(config-if)#ip address 192.168.5.81 255.255.255.240
                  no shutdown
                  exit
                  exit
Router#write
```
### Router 1
```bash
Router>
  enable
Router#
  conf t
Router(config)#interface Gig0/0
Router(config-if)#ip address 192.168.5.49 255.255.255.240
                  no shutdown
                  exit
                  
Router(config)#interface Se0/3/0
Router(config-if)#ip address 192.168.5.34 255.255.255.240
                  no shutdown
                  exit
                  
Router(config)#interface Se0/3/1
Router(config-if)#ip address 192.168.5.65 255.255.255.240
                  no shutdown
                  exit
                  exit
Router#write
```
### Router 2
```bash
Router>
  enable
Router#
  conf t
Router(config)#interface Gig0/0
Router(config-if)#ip address 192.168.5.97 255.255.255.240
                  no shutdown
                  exit
                  
Router(config)#interface Se0/3/0
Router(config-if)#ip address 192.168.5.66 255.255.255.240
                  no shutdown
                  exit
                  
Router(config)#interface Se0/3/1
Router(config-if)#ip address 192.168.5.82 255.255.255.240
                  no shutdown
                  exit
                  exit
Router#write
```
## Rutas
### Estáticas
#### Router0

```bash
Router>
  enable
Router# conf t
Router(config)#ip route 192.168.5.48 255.255.255.240 192.168.5.34
Router(config)#exit
Router#show ip route

```
#### Router1
```bash
Router>
  enable
Router# conf t
Router(config)#ip route 192.168.5.16 255.255.255.240 192.168.5.33
Router(config)#exit
Router#show ip route

```
### Dinámicas
#### Router2
```bash
Router>
  enable
Router# conf t
Router(config)#router eigrp 100
                network 192.168.5.48
Router#show ip route

```
## Creacion de Vlan
### Ventas
```bash
Switch>enable
Switch#conf t
Switch(config)#vlan 10
Switch(config-vlan)#name Ventas
Switch(config-vlan)#exit
Switch(config)#interface range Fa0/5 - 10
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#switchport access vlan 10
Switch(config-if-range)#exit
Switch(config)#exit
Switch#show vlan brief
```
