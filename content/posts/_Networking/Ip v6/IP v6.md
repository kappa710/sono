128 bit
vengono rappresentanti in esadecimali e non piu decimali come ipv4
4bit (2^4 uguale 16) rappresentano un esadecimale
ci sono 8 gruppi ognuno ha 4 caratteri in esadecimale separati da :


Localhost ::1
tutte interfacce ::/0

##  SEMPLIFICAZIONI IPV6 
un ipv6 puo essere di questo tipo che è difficile da gestire
`2001:0db8:0000:0000:0000:ff00:0042:8329`
allora si usano 2 tipi di semplificazione


### RIMOZIONI 0 iniziali di ogni blocco
`2001:0db8:0000:0000:0000:ff00:0042:8329` -> `2001:db8:0:0:0:ff00:42:8329

### COMPRESSIONE  blocchi CONSECUTIVI di zero
sostituendo i blocchi consecutivi possono essere di qualsiasi numero con : cosi ci sara tipo ::
ma attento si puo fare solo una volta in ipv6 con blocco continuo piu grande se uguale numero si prende quello piu a sinistra
`2001:0db8:0000:0000:0000:ff00:0042:8329` -> `2001:db8::ff00:42:9239`

ci sono 2 gruppi contigui uno da 2 e uno da 3  
`2001:0db8:0000:0000:abcd:0000:0000:0000`
sostituiamo il piu grande con :
`2001:0db8:0000:0000:abcd::`  
per altro gruppo si fa semplificazione di 0 iniziali
`2001:0db8:0:0:abcd::`

