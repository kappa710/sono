la cosa piu importante in configurazione e troubleshooting
dopo adiacenti possono scambiarsi informazioni network

quando ospf abilitato in interfaccia invia OSPF hello a interventi regolari (10 secondi in Ethernet connection)
Hello message su multicast 224.0.0.5
inviati in IP header con valore 89

STATI NEIGHBORS

| STATI           | SPIEGAZIONE                                                                                                                    |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| DOWN STATE      | R1 invia HELLO a 224.0.0.5 HELLO CONTINEE  PROPRIO RID e RID VICINO 0.0.0.0 perchè non conosce                                 |
| INIT STATE      | R2 pacchetto HELLO ricevuto ma il proprio RID non sta in HELLO ricevuto                                                        |
| 2-WAY STATE     | R2 invia pacchetto che continere proprio RID e quello appena ricevuto e inserisce nella propria tabella OSPF neihbor , e invia |
| 2-WAY STATE     | invia altro HELLO e entrambi ROUTER                                                                                            |
| DR/BDR ELECTION | non avviene sempre                                                                                                             |
| EXSTART         | scegliere quale izia scambio Master - SLAVE necessario solo per inizio scambio RID maggiore Master inviando DBD                |
| EXCHANGE        | si inviano DBD che contengono LSA nel loro SDB (ma senza dettagliate informazioni)                                             |
| LOADING         | LSR link state request per avere LSA che non hanno , router risponde con LSU che contine  LSA , LSAck                          |
| FULL STATE      | hanno identiche LSDB ma continuano ad inviare ogni pacchetto 10 secondi per mantenere                                          |



### REQUISITI PER ROUTER VICINI
1 stessa area 
2 interfacce stessa subnet
3 OSPF non shutdown
4 OSPF RID diversi
5 router devono avere tra loro stesso hello e dead timer 
6 Stessa autenticazione
7 stessa MTU 
8 OSPF network type uguale