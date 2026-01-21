Interior Protocol
**Link State protocol** Ogni router conosce tutta topologia: ogni router invia informazione su tutti i suoi link collegati ad ogni router nella rete tramite flooding e poi ogni router calcola proprie path 


Funzionamento in breve:
ogni router floodera LSA finche tutti router del router avranno stessa mappa della rere (LSDB)

OSPF funziona per Aree 
cosi ridotto tempo per calcolare rotte
meno richieste hardware (memoria , processore)

area = set di router che condividono stessa LSDB
AREA 0 BACKBONE speciale ogni altre aree devono essere connesse per forza a questa

internal router = tutte interfaccia   in un  solo area 
Area Border Router =  interfacce in aree diverse
BACKBONE ROUTER = tutti quelli area 0 (anche quelli ABR)
intra-area route = destinazione stessa area
interarea route = route che come destinazione diversa area


### 1 ROUTER LOCALMENTE HA PROPRIO OSPF PROCESSO
che viene attivato con comando `router ospf Process ID`
quando processo inizializzato prova a allocare id univoco  R(outer)ID

##### ASSEGNAZIONE RID
controlla se non assegnato in modo diretto con router id comando
se non prova a usare piu alto ip loopback (per router loopback è interfaccia virtuale creato da amministratore)
se fallisce usa ip piu alto di quelli non loopback (reale)


## 2 STABILIRE  VICINI
dopo processo inizializzato invia messaggi Hello a tutti i link abilitati OSPF  (quelli specificati da comando `network ip wildcard-mask area`)

## 3 SCAMBIARSI LSA  econstruire  topologia (LSDB)
LSA = link-state Advertiments contiene link costo connessi direttamente e impostazioni IP
ogni router invia  LSA finche ogni OSPF ha tutti gli LSA (LSA Flooding)

dal LSA costruito LSDB (link-state Database)

## 4 ESEGUIRE SPF algoritmo 
prende come input LSDB e ottiene le best path per router locale(tutto si basa sul adversted cost of each link) 

## 5 AGGIORNAMETO DELLA ROUTING TABLE