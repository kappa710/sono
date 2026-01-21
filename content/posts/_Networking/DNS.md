
##### cosa fa DNS ?
risolve nomi di dominio in indirizzi ip

#### cosa sono i nomi di dominio
hostname + Top-level domain 
esempio:   google(hostname).it ( top - level domain)
##### come funziona DNS
1. il nostro pc interroga il recursive  DNS resolver ( dato da ips o inserito da noi)
2. il recursive DNS server interroga il DNS root nameserver
3. il root server da a recursive DNS ip del DNS TLD nameserver per quel T.D.L
4. il recursive DNS resolver invia richiesta a  DNS TLD nameserver  che risponde con ip del  DNS authoritative 
5. il recursive DNS resolver invia richiesta a DNS authoritative  server che risponde con IP  nome di dominio
6. il recursive DNS resolver invia risposta a nostro pc


### ZONA DNS
porzione spazio dei nomi di dominio gestista da una organizzazione o amministratore
ATTENTO : sottodominio puo far parte di stessa zona DNS o altra (Delegazione)

## RECORD DNS


## PTR
reverse dns 
## A 
associare ipv4
## AAAA
associare ipv6

## NS
associa i nameserver o auterevoli
caso sottodominio con differente zona dns dal dominio allora nel record NS ci sara come autorevole nome di dominio padre (shop.github.com -> NS github.com)

#### CNAME 
associare un nome di dominio a altro nome di dominio 
questo serve cosi se cambia ip non abbiamo problemi a cambiarlo per tutte le istanze (mail , web server ecc)

## SOA
State of the Autority

## ZONA TRANSFERT
operazione di copia da master a slave