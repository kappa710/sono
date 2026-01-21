
Rendaunt Array of Indipendent Disk
ci serve per replica (non serve per backup ma accedere in maniera piu efficente e far fronte corruzione dati)

concetti piu importanti RAID
### Striping
i blocchi che normalmente sono contigui e distribuiti su in unico disco ora non sono piu continughi ma distrubuiti su piu dischi
### Mirroring 
fai copia esatta del disco in altro disco 
se un disco si corrompe prende i dati da altro disco
### Parity
bit  di parita  usati per ricostruire dati quando corrotti
parita 1 XOR
parita 2 robe molto piu complicate che non ci interessano



### TIPOLOGIE RAID
RAID 0 
RAID 1
RAID 5
RAID 6
ma anche raid annidati
RAID 0+1
RAID 5+0
RAID 6+0



## RAID 0
![[RAID 0 STRIPING.png]]
**STRIPING**
disco lo spalmiamo in strisce 
terribile per gestione dei dati corrotti (0 tolloranza corruzione dati)
ottime performance 


## RAID 1
**MIRRORING**

se si corrompe disco sta altro ma svantaggio occupiamo piu memoria
![[RAID 1 MIRRORING.jpg]]
vantaggio : tollorenza ai dischi n-1 
svantaggio costi 



### RAID 5
**STRIPING** , **MIRRORING** , **PARITY**

si usa XOR
tabella  xor 
00 0
10 1
01 1
11 0

immaginiamo che si rompe una colonna 0101 ma possiamo ricavarci dato iniziale sapendo risultato xor
tolleranza ai dischi (n-1/n)
![[RAID 5.jpg]]

### RAID 6
sempre bit parita di XOR ma anche altra parita possiamo quindi tollerare piu dischi ma piu lento per ricostruire dischi (si usa per archivi non critici) 
formula (n-2)/n
![[Raid 6.png]]




### RAID 1+0 
![[RAID 10.png]]
