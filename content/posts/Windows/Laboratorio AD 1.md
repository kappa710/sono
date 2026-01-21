#### Prerequisiti 
- Windows server iso
-  Virtual Box
-  Windows normale iso
-  creare rete con nat da tools su virtual box ( rete con nat diversa da nat)

### Configurazione 
#### rete server  / domain contoller
ip ricordando che primo ip subnet è il gateway mentre .2 e .3 ecc. vengono usati da virtualbox
subnet dato da rete con nat
gateway primo ip subnet
DNS : qualisiasi server DNS

### rete clients
come DNS ip del domain controller


per creare TEMPLATE craere utente senza login
per riuovere elemento vai in visualizza funzionalita avanzate e poi da proprieta togli spunta 

SG_nome_gruppo (gruppo globale )

GL_nome_gruppo (gruppo locale )


## GPO
### bloccare applicazioni 
per windows 11 meglio usare app locker 
applocker non si applica agli oggetti utenti ma agli oggetti computer quindi devi creare una OU con computer e a quella applicare GPO
per usare applocker devi configurarlo dalla GPO creata e devi attivare nella GPO servizio Windows Identita applicazione 
poi puoi creare regole per Applocker

comando per forzare sul client cambiamenti gpo
``` powershell
gpupdate /force
```