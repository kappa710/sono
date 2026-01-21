
Dynamic Host Configuration Protocol

4 fasi DORA
DHCP **D**iscover (broadcast)
DHCP **O**ffer (unicast)
DCHP **R**equest (dice che accetta) (broadcast)
ACK    **A** (unicast)
##### come è richiesta dhcp inviata da host ?
layer 3 con ip source 0.0.0.0 e ip di destinazione 255.255.255.255
client invia a porta 68 udp  , server risponde a porta 67

cosa è APIPA
AUTOMATIC PRIVATE IP ADDRESSING
meccanismo che permette a host di avere proprio ip privato quando non riesce ad avere uno da un dhcp
`169.254.X.X`
##### come configurare DHCP
`ip dhcp pool {nome che vuoi dare}`
`default-router {ip del gateway rete}`
`network {ip network} {subnetmask}`
`ip dhcp exluded address {ip inizo} {ip fine}`

