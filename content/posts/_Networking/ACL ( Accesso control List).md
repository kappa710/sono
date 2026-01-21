

#### a cose serve ?
sicurezza , regola quali dispositivi hanno accesso alla rete

##### cosa è ?
un filtro , che dice a router di permettere o scartare pacchetto

#### cosa è importante acl
implicit deny  su ogni singola ACL e vengono lette (da numero piu basso a piu alto) finche occorrenza non corrisponde

#### miglior modo di configurare    
fare tutta configurazione in stesso numero nome ACL  se no per via del implicito deny puo non arrivare mai a numero successivo
 # si apliccano ( teoria + comandi)
inerface …
ip access-group (nome/numero)   in | out
su interfaccia e poi si sceglie inbound ( traffico che entra in interfaccia ) o outbound (traffico che esce da interfaccia)
    
#### come vedere se inbound o outbound
inbound : router non ha deciso come mandarlo con tabella routing
outbound: router ha deciso come mandarlo tramite tabella routing