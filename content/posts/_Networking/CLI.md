

###### per cosa sta CLI ?
Command Line Interface
###### con che tipo cavo mi connetto a router / switch Cisco
Rollover cable    
###### come mi connetto da pc a  CLI del router/switch
PuTTy
###### cofigurazione PuTTy
IMMAGINE

## MODALITA

###### quali sono le 3 modalità in dispositivo CISCO
USER , ROOT . CONFIG 
###### con che comando passare da USER  a ROOT
enable
###### da ROOT a CONFIG
configure terminal

###### da CONFIG a ROOT
 exit
###### eseguire comandi in modalità enable da altre modalità
do {comando}

###### quale comando di solito faccio in enable e non altre modalità?
 show


### COMANDI

###### cambiare hostname?
    
    hostname {nome}
    
###### aggiungere password
enable password {password}

###### rendi password encrpytata
service password-encrpytion
###### differenza password e secret   
secret : password criptografia piu forte 

###### come aggiungere secret 
enable secret {secret}    

### CONFIGURAZIONI

###### differenza running-config e startup-config
solo su RAM , si perde a riavvio …….. vs config che si avrà al riavvio

###### comando per passare da running-config a startup-config
copy running-config starting-config


## ROUTER

###### per attivare rete di un router
vai in `configure terminal` → `interface Gi0/0/0 `→` ip address {ip router = ip gateway} {subnetmask}` → `no shutdown` ( attiva solo questa interfaccia )  

###### mostrare interfacce ?
show ip interface brief


## ROUTING

RICORDATI che per PING deve andare pacchetto sia andata sia ritorno

### ROUTING STATICO

- come si fa routing statico
    
    vai in configure terminal → ip route {IP NETWORK che vuoi RAGGIUNGERE (attento IP NETWORK)} {SUBNETMASK} {IP AL GATEWAY DEL NETWORK CHE VUOI RAGGIUNGERE}
    
- come controllare routing
    
    show ip route
    

**ROUTING DINAMICO**

- come si fa
    
    router ospf 1
    
    network {network} {wildcard} area {}
    
    network lo devi fare per ogni network che router ha (  e anche per network che vede staticamente)
    
- cosa opzionale
    
    log…
    
- le 2 cose tricky
    
    ricordati del 1 e wildcard mask si usa