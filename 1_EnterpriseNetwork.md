# Huawei-Based Enterprise Network Design and Implementation

### Тақырыбы: Huawei құрылғылары негізінде корпоративті желіні жобалау және конфигурациялау
### Жұмыстың орындалу қадамы: 
  1) VLAN;
  2) Link Aggregation. LACP;
  3) MSTP (Multiple Spanning Tree Protocol);
  4) Switched Virtual Interface (SVI);
  5) VRRP (Virtual Router Redundancy Protocol);
  6) IP Address Configuration;
  7) Single area OSPFv2;
  8) Access Control List (ACL);
  9) Network Address Translation (NAT);
  10) Default Static Routing.

> SVI — L3 интерфейс, яғни VLAN-ның виртуалды routed интерфейсі (virtual routed interface)

### Корпоративті желінің топологиясы
![Topology Enterprise Network Design](images/Topology_PNETLab_EnterpriseNetworkDesign_HQ1_v1_Huawei.png)
[Download Link for PNETLab Topology File](Topology/Topology_EnterpriseNetworkDesign_HQ1_v1_Huawei.zip)

### A1, A2 – Access Layer Switch-ті конфигурациялау
```shell
<Huawei> undo terminal monitor
<Huawei> system-view
[Huawei] sysname A1
```

### D1, D2 – Distribution Layer Switch-ті конфигурациялау
```shell
Please configure the login password (8-16)
Enter Password: Huawei@123
Confirm Password: Huawei@123

<Huawei> undo terminal monitor
<Huawei> system-view
[Huawei] sysname D1

[Huawei] vlan batch 11 12
[Huawei] display vlan

[Huawei] interface Eth-Trunk 1
[Huawei] port link-type trunk
[Huawei] port trunk allow-pass vlan 11 12
[Huawei] mode lacp

[Huawei] display port vlan
```

### C1 – Core Layer Switch-ті конфигурациялау
```shell
<Huawei> undo terminal monitor
<Huawei> system-view
[Huawei] sysname C1
```

### SRV-D1 – Distribution Layer Switch-ті конфигурациялау
```shell
<Huawei> undo terminal monitor
<Huawei> system-view
[Huawei] sysname SRV-D1
```

### EdgeR1 – Edge Router-ді конфигурациялау
```shell
<Huawei> undo terminal monitor
<Huawei> system-view
[Huawei] sysname EdgeR1
```
