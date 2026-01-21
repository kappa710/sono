
![[Pasted image 20251218172131.png]]
### Bus
tutti nodi a singolo cavo

| vantaggi             | svantaggi                |
| -------------------- | ------------------------ |
| facile da implemtare | 1 sigle point of faliure |
|                      | collisioni dati          |
|                      | rallentamenti            |

## ANELLO
modo circolare , ogni nodo ha esattamente 2 vicini

| vantaggi                            | svantaggi                 |
| ----------------------------------- | ------------------------- |
| economiche e facili da implementare | 1 single point of faliure |

### STELLA
nodi collegati a hub centrale 


| vantaggi                      | svantaggi                        |
| ----------------------------- | -------------------------------- |
| facile da risolvere , gestire | prestazioni dipende da unico hub |
| scalabile                     |                                  |

## ALBERO
combina bus e stella -> gerarchica

| vantaggi                        | svantaggi                                    |
| ------------------------------- | -------------------------------------------- |
| facile da implementare e gisero | 1 single point of failiure                   |
|                                 | le prestazioni dipendo da hub piu importante |

## MESH
almentente interconessa , ogni nodo collegato a piu nodi 

| vantaggi        | svantaggi                          |
| --------------- | ---------------------------------- |
| resilienza rete | maggiore complessita progettazione |
| non SPOF        | maggiore complessita manutenzione  |
|                 | poca scalabilità                   |
