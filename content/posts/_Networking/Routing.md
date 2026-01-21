

##### indirizzo ip che di solito si da network LAN
192.168.X.X

##### indirizzo ip che di solito si da a reti di router
10.0.X.X


##### cosa è gateway
funge da punto di ingresso e uscita per traffico dati tra 2  reti ma ha ruolo attivo



##### come viene selezionato percorso da fare ? meglio valore grande o piccolo
distanza amministrativa , piccolo


##### Routing Statico

###### come fare routing statico

`ip route {rete che si vuole raggiungere} {sua subnet} {next hop}`


##### Routing Dinamico

##### esistono di 2 tipi
Distance Vector e Link State (inviano meno informazioni)


### OSPF

##### cosa è la cosa piu importante nel OSPF
le aree , soprattutto area 0

##### quale è la caratteristica del area 0
tutte le altre aree devono essere intersecate con area 0

##### come si ottiene wildcard mask
si sottrae ogni valore nella subnet mask per 255
esempio 255.255.255.192 → 0.0.0.63

##### come configurare su cisco packet tracer ?
`router ospf 1`
per ogni network “creato” dal router che stiamo configurando
`network {network visto } {wildcard mask} area {numero area a cui appartiene}`
##### come dare info ad OSPF su rotte statiche e robe collegate al router ?
dopo aver fatto router ospf 1 
`redistribuite static subnets`
`redistribuite connected subnets`