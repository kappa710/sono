### algoritmo 1
1. eleggere il root bridge
2. selezionare le root ports per ogni switch diverso da root bridge
3. selezionare le porte disegnate
4. bloccare le porte non disegnate
5. monitorare per fallimenti che possono bloccare le porte disegnate per sbloccare quelle disegnate

## 1 elezione Root bridge
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

## 2 selezionare Root ports
Dopo aver designato lo root switch gli altri switch decideranno 1 loro interfaccia per essere root port (che è in forwarding state) facendo in modo che path per il root abbia costo minore cost root path per raggiungere il root bridge 

#### calcolare root path cost per root bridge
ogni volta che si passa una interfaccia si somma a seconda della velocita della porta finche da quello switch non si raggiunge il root bridge 


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

il root cost viene inviato insieme al PDBU

## 3 selezionare porte disegnate
porte disegnate posso inviare e ricevere traffico oltre forwarding dei BPDU
switch inizialmente pensa che ogni porta non root sia designata solo quando arriva PDBU da altro switch su porta designata capisce che si puo creare un loop e quindi li rende non designate


#### caso Shared fragment
![[Shared Segment.png]]
in questo caso almeno una porta switch deve rimanere designata cosi da inviare il pacchetto con BPDU a porta switch 3 per ricordargli se ancora non è la rotta migliore (cambiamenti topologia o fault)

cosi scelto in shared quale è porta è designata
- **Costo del percorso verso il root più basso**
- **Bridge ID del mittente più basso**
- **Priorità della porta del mittente più bassa**
- **Port ID del mittente più basso**