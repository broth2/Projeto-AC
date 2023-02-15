# PN configuration
## Router Porto

```
conf t


interface f0/1 ! connection to DC.P2
ip address 192.168.1.145 255.255.255.240
no shut

interface f1/0 ! connectiion to DC.P1
ip address 192.168.1.129 255.255.255.240
no shut

interface f6/1 ! Connection to the internet
no shut

interface f1/1 ! connection to Aveiro
ip address 192.168.1.1 255.255.255.240
ip ospf 1 area 0 ! enable ospf inside PN
no shut

interface f0/0 ! connection to Coimbra
ip address 192.168.1.49 255.255.255.240
ip ospf 1 area 0 ! enable ospf inside PN
no shut

interface Lo 0 ! bgp connections
```


## Router Aveiro
```
conf t

int f1/1 ! connection to Porto
ip address 192.168.1.2 255.255.255.240
no shut
ip ospf 1 area 0 ! enable ospf inside PN

int f1/0 ! connection to Coimbra
ip address 192.168.1.17 255.255.255.240
no shut
ip ospf 1 area 0

int f0/0 ! connection to DC.A1
ip address 192.168.1.97 255.255.255.240
no shut

int f0/1 ! connection to DC.A2
ip address 192.168.1.113 255.255.255.240
no shut


interface Lo 0 ! bgp connections
```



## Router Coimbra
```
conf t

int f1/1 ! connection to DC.C1
ip address 192.168.1.81  255.255.255.240
no shut

int f1/0 ! connection to Aveiro
ip address 192.168.1.18  255.255.255.240
ip ospf 1 area 0
no shut

int f0/0 ! connection to Porto
ip address 192.168.1.50  255.255.255.240
ip ospf 1 area 0
no shut

int f0/1 ! connection to Lisboa
ip address 192.168.1.33  255.255.255.240
ip ospf 1 area 0
no shut


interface Lo 0 ! bgp connections
```

## Router Lisboa
```
conf t


int f0/0 ! connection to DC.L1
ip address 192.168.1.65  255.255.255.240
no shut

int f0/1 ! connection to Coimbra
ip address 192.168.1.34  255.255.255.240
ip ospf 1 area 0
no shut

int f6/1  ! connection to internet
no shut

interface Lo 0 ! bgp connections
```


# Lisboa DC
## VyOS DC.L1

```

```

# Porto DC
## VyOS DC.P2

```

```
## Router DC.P1
```
conf t
router bgp 43100
router-id 192.168.1.130
neighbor 192.168.1.168 remote-as 43100
neighbor 192.168.1.168 update-source Lo0

neighbor 192.168.1.169 remote-as 43100
neighbor 192.168.1.169 update-source Lo0

address-family vpnv4
neighbor 192.168.1.168 activate
neighbor 192.168.1.168 send-community both

address-family vpnv4
neighbor 192.168.1.169 activate
neighbor 192.168.1.169 send-community both

interface f0/1
ip address 192.168.1.130 255.255.255.250
no shut

interface f0/0
ip address
no shut



```
# Aveiro DC
## VyOS DC.AC1
```
```
## Router DC.A2
```
```

# Coimbra DC

## Router DC.C1
```
```
