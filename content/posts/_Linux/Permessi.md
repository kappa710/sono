**R**EAD - **W**RITE - E**X**ECUTE
e ogni owner , group , other a questi

il proprietario del file è chi crea il file ( o modificato dopo da comandi)
il gruppo è  il gruppo del proprietario del file
other = estranei ai primi e 2

#### Versione CLASSICA
rwx   

#### Versione OTTALE 
r w x
4 2 1
quindi 0 = --- , 1 = --x , 3 = -wx , 4 = r-- , 5 = r-x

OLTRE A CLASSICI permessi 

## Sticky bit
solo il proprietario file puo eliminare i file (perchè se no tutti potevano eliminare file se avevano permesso nella cartella)
1 davanti a altri 3 numeri della versione ottale
si vede facendo ll e si vede che al posto del execute di others c è una t o T (a seconda di execute è dato a others oppure no)



attento Suid e Guid vale solo per programmi compilati
### Suid 
esiste il **SUID** fondamentale per ethical hacking
SUID = **S**et Owner **U**ser **ID**
permette di **eseguire** un file come se fossi il proprietario del file ma senza esserlo
nella notazione ottale è rapresentato con 4 davanti ai 3 altri numeri

### Guid
#### gruppi
vedere gruppi utente
`id` e `groups`

## CAMBIARE PERMESSI

`chmod` : cambia permessi
`chown` : cambia owner
`chgrp` cambia gruppo
`usermod -aG` : aggiungere utente a gruppo


##### ACCEDERE CON ALTRO USERNAME 
`sudo -u {nome utente}`


#### umask
aiutare a dare permessi a nuovi file tramite operazioni binari
per vedere permessi nuovi file 666 and bit a bit con negato(umask)