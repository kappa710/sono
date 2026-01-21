## GLOBAL UNICAST
indirizzi pubblici che posso essere usati su internet  (quindi devono essere unici)
prima solo blocco 2000:/3 ora tutti quelli non usati per altri motivi 

## UNIQUE LOCAL
sono indirizzi privati 
FC00::/7 prima ma ora FD 
meglio generare randomicamente rimanenti 40 bit per possibili problemi quando aziende si uniscono ecc

## LINK LOCAL
sono generati automaticamente e non veranno usati sono in unica subnet (no routing perchè router scarta)
esempio uso per next hop 
blocco FE80::/10 ma sempre FE80
i 64 bit generati da eui-64

### MULTICAST
inviano pacchetti a tanti 
FF02::1 a tutti host 
FF02::2 tutti i router
FF02::5 tutti OSPF router
FF02::6 tutti OSPF DRs/BRDs
FF02:9 tutti RIP router
FF02::A tutti EIGRP router
scopo del multicast
FF01 interfaccia locale (non lascia dipositivio)
FF02 link local (rimane subnet)
FF05 site-local (rimane in azienda)
Organization-local FF08 (tipo site-local ma piu grande)
Global FF0E (internet)

## ANYCAST
tanti  router con stesso ipv6
quando host invia richiesta a questo ipv6 usato da tanti dispositivo viene scelto il dispositivo piu vicino
