Boards -> mantenerei processo dei progetti e pianifichiamo
Pipeline -> testiamo , distribuiamo codice
Azure Monitors -> per vedere metriche



### CI/CD
**C**ontinious **I**ntegration: ogni volta che il codice viene pushato viene buidato e testato
**C**ontinious Delivery: codice buildato e testato per piu sistemi (Linux,mobile,Windows ecc)

### CONTINIOUS IMPROVMENT

##### Pipelines
Pipelines:  automatizzazioni e tools che permetto CI/CD 
esempio caricare un push vede se è stabile anche buildando lo accetta e pusha sul branch
Build Pipelines: compila il codice e fanno dei test

#### Artifacts
Artifact tutto il risultato di un processo devops
Azure Artifacts: gestisce dipendenze


### AGILE
metodologia per organizzare il lavoro in maniera piu flessibile
	SCRUM : maratona ( ma dentro gli Sprint concentrati a fare solo quello) 


esempio , sviluppo app in 2 settimane è SPRINT , per dire al tutto il team per concentrarsi su obbiettivo sprint

sprint backlog : sprint attuale
product backlog : priorita generale 


KANBAN 
Kanban board si divede in : to do , doing , done
user stories : ci si concentra  dal punto di vista del  utente tralasciando il tecnico , tutto quello che utente fa su piattaforma


LEAD TIME : tempo  che inizia quando stakeholder richiede qualcosa fino a realizzazione
CYCLE TIME: quanto tempo passa da quando iniziamo a lavorare veramente fino alla fine



SICUREZZA
vede se codice se sicuro , se non sicuro lo rende
pensata sempre sicurezza del codice in maniera continua
aiutarsi con pipelines
strumento è sonar quebe = analizza codice e trova bug / vulnerabilità 
shift left security la sicurezza viene cosiderata al inizio non alla fine come in waterfall 
