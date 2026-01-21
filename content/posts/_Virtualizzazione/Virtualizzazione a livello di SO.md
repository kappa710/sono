chiamato partizionamento o container di applicazione
virtualizzazione a livello Kernel , SO caricato solo a fase uscita 

## Docker
docker host : SO su cui gira docker
docker machine : installare engine su host
docker engine : permette esecuzione del docker client sul docker host


## Kubernets
per gestire container su cluster di macchine , semplifica distribuzione container
mette a disposizione bilanciamento di carico , errori 

servizi:
	Kube Scheduler
	 proxy : parte networking tra cui load balancing

 oggetti:
	pods : unita piu piccola , formato da almeno un container e condividono rete , volume e istruzioni su come runnarlo 
	repplica set : gestisce replica pods per un determinato cluster specificando numero massimo copie 
	 deployment: gestire deployment e roll back
	 roles : politica acessi a pods
	 secret : gestione password


## OPEN SHIFT 
stato astrazione e nuove funzionalita rispetto a kubernets
Collegamento facile a github e gitlabs
maggiore sicurezza
gestione automatica del build e deploy
