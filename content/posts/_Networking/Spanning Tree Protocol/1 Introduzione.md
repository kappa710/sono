Se mettiamo tanti switch per ridondanza -> problema BROADCAST STORM e MAC ADDRESS FLAPPING
#### BROADCAST STORM
esempio richiesta ARP -> switch flood a tutte le interfacce tranne quella inviata e tutti swith fanno lo stesso e cosi si crea broadcast storm perchè continua fino alla fine
a layer 3 sta TTL a layer 2 non sta quindi fino alla fine 

### MAC ADDRESS FLAPPING
quando frame arriva a switchport switch usa sorgente MAC per aggiornare sua tabella in questo caso troppi aggiornamenti 

soluzione SPANNING TREE PROTOCOL
### classico
IEEE 802.1D è default sempre 

## tipi porte stp
esistono 2 tipi di porte in STP classico ridondanti e di forwarding
### forwarding
quelle di forwarding agiscono normalmente e inviano traffico 
## ridondanti
porte ridondanti come se  disabilitate inviano solo messaggi STP  e usate come backup e vengono attivate solo se interfaccia di forwarding falliscono 


### PROCESSO PER DETERMINARE se porta FORWARDING e RIDONDATI
quando switch viene avviato pensa di essere root switch 
switch invia HELLO BPDU a ogni interfaccia -> se switch riceve  HELLO BPDU minore allora non è piu root e tutti switch alla fine eleggono uno root
dopo designazione switch non non inviano PBDU ma forwardano  
### HELLO BPDU
formato da 

| Bridge Priority | MAC address |
| --------------- | ----------- |
| 16 bit          | 48 bit      |
di default tutti gli switch hanno priorita 32768 quindi MAC address si usa per vedere chi root bridge


Root bridge ha tutte le porte in designed mode (forwarding mode) modo e tutti switch devono poterlo raggiungere

dopo aver designato lo root switch gli altri switch decideranno una loro interfaccia per essere root port (che è in forwarding state) facendo in modo che path per il root abbia costo minore cost root path per raggiungere il root bridge 

### calcolare root path cost per root bridge
ogni volta che si passa una interfaccia si somma a seconda della velocita della porta

| tipo    | root cost |
| ------- | --------- |
| 10 mbs  | 100       |
| 100 mbs | 19        |
| 1 Gbps  | 4         |
| 10 Gbps | 2         |

se costo path per root uguale si procede cosi
1) PATH ROOT COST
2) piu piccolo birdge ID 
3) piu piccolo numero porta su switch

ma ora tutte porte ancora attive e sta il loop
per evitare il loop scegliere Designated port in ogni network segment (connesione tra 2 o piu switch)
Designated port possono inviare e ricevere traffico + forwardare BPDU
switch pensa che tutte le porte non root sono Designated 