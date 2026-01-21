

| LIVELLO | NOME         | PBU              |
| ------- | ------------ | ---------------- |
| 7       | Applicazione |                  |
| 6       | Presentation |                  |
| 5       | Session      |                  |
| 4       | Transport    | segment/datagram |
| 3       | Network      | packet           |
| 2       | Data Link    | frame            |
| 1       | Phisical     |                  |




##### cosa succede a data dal alto verso il basso
aggiunti data : ENCAPSULATION

##### cosa succede a data dal basso verso alto
data strip off  DE-ENCAPSULATION    

##### cosa fa il Layer 6 e esempio
il presentation layer transla tra formato applicazione a formato network
encrypta e decrypa cosi che recevente e trasmettitore capiscono 

##### cosa fa il Layer 5 ? e cosa controlla ?
Session layer controlla dialoghi / sessioni fra hosts
fasi di instaurazione , mantenimento , disconessione

##### cosa fa il Layer 4
reassembla e frammenta data affichè siano piu facilmente trasmettibile 
permette comunicazione di piu applicazioni degli host

**Multiplexing (**permette a più applicazioni di usare la stessa connessione contemporaneamente, ****evitando di sprecare risorse) e **Demultiplexing** ( Smista i dati ricevuti (da un'unica connessione) all'applicazione corretta usando i numeri di porta, evitando che i dati finiscano all'applicazione sbagliata e permettendo a più applicazioni di condividere la stessa connessione.)

**Connection Management** (establishing)

**Flow Control (Buffering / Windowing) :** regola trasmissione paccheti

**Reliable Transport**

##### differenza buffer e windows size
buffer memoria fisica / promessa di memoria da occupare

##### cosa fa il buffering ?
Assicurarsi che il destinatario abbia abbastanza spazio di memoria (buffer) per ricevere i dati senza problemi.

##### cosa fa il windowing?
Il mittente si adatta alla velocità del destinatario in base a quanto velocemente il destinatario riceve i dati in modo affidabile.


##### cosa fa il layer 3?
Collega end host in reti differenti
Path Selection
Assegna indirizzi logici


##### cosa fa il layer 2?
fornisce connettività nodo su nodo
definisce come data è formattata per trasmissione su mezzo fisico (protocollo)
trova e corregge errori nel layer fisico

esempio Ethernet , Wifi
ha identificatore  M(edia) A(ccess) C(ontrol) (idirizzo fisico)


###### cosa è MAC ADDRESS e numero bit?
MEDIA ACCESS CONTROLLER identificatore univoco della scheda di rete , formato da 48bit


###### cosa fa LLC ?Logical Link Controller , interfaccia tra layer 2 e layer 3