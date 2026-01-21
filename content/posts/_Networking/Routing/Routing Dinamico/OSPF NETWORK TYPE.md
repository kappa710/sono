OSPF BROACAST NETOWKR TYPE
abilitato su ethernet and FDDI interfacce in default
Router dinamicamente scopre vicini sendendo HELLO OSPF packetsu multicast 224.0.0.5
DR (designated router) e B(ackup)BR devono essere  eletti per ogni subnet
Router non DR o BDR è DROther

COME ELETTI DR/BDR 
1 OSPF interfaccia priorita (ma uguali per default 1)
2 RID piu alta 

router faranno piena addiacenze OSPF con BR e BDR del segmento nel network type BROADCAST
DROther non inviano LSA tra loro 
F/C indica quanti FULL 

### MANCA OSPF POINT TO POINT NETWORK TYPE