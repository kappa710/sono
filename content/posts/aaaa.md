---
title: AD
showTableOfContents: true

---

**DEFINIZIONE AD** 
sistema di gestione centralizzato basato su concetto dominio : insieme host sulla rete che condividono risorse e accessi


**Windows Domain** 
insieme di utenti e computers appartengono alla stessa organizzazione 

i Domain servono per centralizzare amministrazione di  computers Windows di identità e security policy

il cuore di Windows Domain è **Active Directory  Domain Service**

il server che runna l Active Directory è il **Domain Controller**




Acive directory supporta tanti oggetti : utenti , gruppi , macchine , stampanti , shares


**utenti** : autenticati e privilegi su risorse (file , printers)
utente : persona fisica (vari permessi) o servizio  (es Mysql , permessi solo per fare funzionare servizio)


**Macchine** : (workstation , server , domain controllers )
macchine hanno account utenti per macchine per gestire localmente la macchina
nome_macchina = `DCO1`   , account_macchina = `DC01$`




Organanitazional Unit (**OUs**)
oggetti sono organizzati in OU
chiara distinzione perchè un oggetto puo appartenere solo a un OU 
OU spesso replicano la struttura del business 


OU vs Security Group
OU delegare permessi
Security Groups dare permission per accedere a risorse (file e cartelle)

## DELEGATION
dare ad un account la possibilita di fare task avanzati su un OU



## GROUP POLICY OBJECT 
collezione di impostazioni che possono essere applicate a OU
GPO distribuite via network share chiamato `SYSVOl`
affiche applicate 2 ore oppure usa `gpupdate /force`



## GERARCHIA AD

### TREE
ho un domain sopra con DC che puo controllare tutti i Domain sottostanti (Enterprise Admin)
condividono cosi stesso namespace
aggiunto sottodominio
thm.local
uk.thm.local us.thm.local
### Forest
altro tipo di dominio 
thm.local  tlc.local




## TRUST RELATIONSHIPS
autorizzare utenti ad accedere risorse di altri domain
A da fiducia a B 
B puo accedere a risorse di A
permette di fare dopo autorizzazione 