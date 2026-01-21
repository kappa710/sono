Docker crea ambienti coerenti e replicabili ovunque

MACCHINE VIRTUALI vs DOCKER
Docker condivide  kernel con macchina host  e questo porta a vantaggi 


su DOCKER lavoriamo con **IMMAGINI**,**CONTAINER**,**VOLUMI**


## IMMAGINE
**Immagine** è un blueprint
per costruirla ci serve un DockerFile (non ha estensione)
e usare comando  **```docker build  -t python .```**

opzione -t ci dice che useremo file dockerFile 
. dove si trova il DockerFile


## CONTAINER
Container è istanza isolata del immagine
per creare container dobbiamo usare comando 
``docker run {nome_immagine}

per esporre i servizi docker usiamo flag -p
`docker run -p {porta localhost della macchina host}:{porta contneir docker esposta} {nome_immagine}`


## VOLUMI
Container sono effimeri per default i dati non persistono quindi dobbiamo usare i **VOLUMI**






