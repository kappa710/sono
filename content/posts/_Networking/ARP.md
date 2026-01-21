

#### a cosa serve?
associare indirizzo IP ( layer 3 ) a MAC address ( layer 2)

#### perchè serve ? 
perchè quando craftiamo il pacchetto ( seguendo pila TCP / IP ) dobbiamo inserire anche info per layer 2 che richiede MAC address di source e dest

#### come funziona

1 inviata arp request ( source mac address : quella del pc che fa richiesta , dest mac address : ff:ff:ff:ff (broadcast) e IP da associare a mac address e  IP di chi ha fatto richiesta 

2 chi ha ip cercato invia arp reply (source mac address : quello che ci serviva , dest mac address di chi ha fatto richiesta arp )