
##### cosa è VLAN
ci permette di isolare domini di broadcast ( quando inviamo messaggi con dest FF:FF:FF:FF con vlan limitiamo destinatari)

###### a cosa serve VLAN
 sicurezza (impedisce scan nmap) e diminuire la banda usata ( meno ARP )  e scalabilità


### ATTENTO
trunk e access e concetto di porta , puoi combinare come vuoi quale native/untagged in trunk basta che dispotivo altra parte porta configurato nella stessa maniera
#### su interfaccia trunk
se riceve frame con tag -> lo invia dove quel tag attetto
se riceve frame senza tag -> lo invia come nativa vlan

### su interfaccia access
non esiste il tag ma switch invia solo dove vlan3 grazie a Port ID VLAN che viene associata ai frame

## CISCO
#### native vlan
ogni trunk deve avere una native vlan puo essere diversa per trunk ma uguale tra porte collegate , il traffico passa untagged

### default vlan
in modo predefinito tutto passa untagged su default vlan


## ATTENTO 
posso combinare nella trunk untaggated e tagged come voglio posso mettere tagged pure a VLAN nativa importante che sta sempre un untagged e che switch che comunica configurazione a specchio

## DISPOSITIVI  per come visto a lezione

| Dispositivo | Modalita                                                                                                                                                                                                                                                    |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Firewall    | come vuoi                                                                                                                                                                                                                                                   |
| Switch      | deve stare una trunked e una untagged (o native che su cisco se non settata default è), puoi mettere qualsiasi vlan  in tagged qualsiasi untagged pure default , se 2 switch collegati allora nelle porte che li collegano deve stare stessa configurazione |
| Telefono    | deve stare una trunked e una untagged (qualasiasi trunked , qualsiasi untagged)                                                                                                                                                                             |
| AP          | untagged quella dove viene fatto managment AP e tagged le altre                                                                                                                                                                                             |




###### come configurare VLAN prima di assegnarla a qualcosa
`vlan {numero a cui assegnata Vlan diverso da 1}`
`name {nome dela Vlan}`l

###### configura vlan su  interfaccia che si collega a host access/untagged
scegli interfaccia    
`switchport mode access`
`switchport access vlan {numero vlan}`
###### cosa permette trunking vlan / tagged
permette di trasportare traffico di piu vlan
`switchport mode trunk`
che devono essere specificate attraverso comando  su switch
`switchport trunk allowed vlan add 2,3,4`

##### cosa succede a switch in trunk mode quando riceve pacchetto tag?
 riceve un pacchetto tag → se  è solo se è in trunk moode lo legge → vede se vlan è allowata in lui → invia se sa MAC se no flood

802.1Q encapsulation ( TAG) permette di passare a switch a router / firwall che fa routing




##### configura vlan su interfaccia che si collega a altro switch
switchport mode trunk  
switchport trunk allowed vlan add {id}

###### come avere info
show vlan [brief]
show interface vlan {id}