dhcp , arp per design insicuri ( non esisteva ai tempi autenticazione) e dobbiamo usare sicurezze in piu

possiamo sfruttare i loro design usando spoofing , man in the middle , relay

## ATTACCO SU ARP

arp spoofing attraverso comando kali linux arpsoof esempio uso possiamo aggirare dns server arp gratuito ( rispondiamo senza che nessuno abbia fatto richiesta

## ATTACCO SU DHCP

4 fasi DHCP :

- discover ( source IP 0.0.0.0 e destinazione 255.255.255.255)
- offer ( offerta ip da dhcp server )
- request
- ack

esempio attacchi su DHCP :

- dhcp starvation ( server dhcp non riesce ad assegnare piu ip perchè subnet piena)
- spoofing dhcp ( diamo noi ip perchè leggiamo su broadcast e rispondiamo prima del dhcp server)