### SUPERVISIONATO
viene allenato su dati etichettati
input + output desiderato (label , target)
obbiettivo = imparare relazione tra input e outp per generalizzare

istanza addrestamento coppia (input , output) imparare funzione
f: X -> Y dove si sa x e y
il modello minimizzare errore con ottimizzazioni

Tipi di problemi supervesionati
Classificazione 
spam/non spam output categorigo (classe , etichette)

Regressione
output valore numeri continuo
esempio prezzo casa , tempo di arrivo
dati classificati

Algortmi
Logisc Regression Classificazione
Linear Rregression Regression
Decision Tree Entrambi
Random Forest Entrambi
K-NN Classificazione Vicino piu vicino
Reti Neurali Entrambi  

### Vantaggi
Alta precesione se dataset buono
facile e super supportato
### Svantaggi
troppa dipendenza da dataset


## NON SUPERVISIONATO
cerca pattern , strutture relazioni 
dati forniti non hanno etichette black box
obbiettivo e organizzare e interpretare dati 

#### APPLIACZIONI
segmentazione dei clienti
analisi anomalie 

ALGORITMI
K.means : divide in K gruppi 

DBASCAN
cluster basato su denista e identifica anomalie
Hierarichal Cluestering
gerarchia di cluester 
Ridunzione della dimensionalita PCA 
AUTOENCODER (neural newtowkrs) comprime e resitrutisce

### k-means (media) clustering
sceglie numero di kluster numero k
si inizializzano k punti nello spazio che sono i centroidi provvisorio
3 ogni punto del dataset viene assegnato al centroide piu vicino
4 Si trova nuova centroide facendo media dei punti nel cluster
e si ripete 3 e 4 
##### esempio
asse x eta , asse y spesa media 
k means 

##### vantaggi
semplice e veloce
intuitivo da vedere
adatto a dati numerici
utile per preanalisi
##### limiti 
scelta k difificle
funziona bene solo con cluster sferici (blocchi vicino ai centroidi)
sensibili a valori autonomi
richiede normalizzazione dei dati

### DBSCAN
densite dei punti , identifica i cluster come aree dense di dati esperati da aree scarse

DEFINISCE 
esp raggio massimo per considerare punti vicino
min_sample : numero minimo di punti per essere considerato denso

punto
Core point: ha abbastanza vicini → avvia un cluster
Border point: vicino a un core, ma non core esso stesso
Noise point: isolato

### vantaggi
non numero di kluster
rileva di forma abitraria
gestisce arbitraria
svantaggi
devi comunque scegleire 2 parametri
poco performante con alta dimensionalità



### HIERARCHICAL CLUSTERING
costruisce una gerarchia di cluster
AGGLOMERATIVO 
ogni punto cluster 
trova la coppia cluster piu vicina e si unisce in cluster
e si ripete finchè un solo un cluster
rappresentazione dendogramma albero che mostra fusione cluster
vantaggi
non serve K
svantaggi
poco efficacie per grossi dataset


## RINFORZO
apprendimento per rinfornzo 
obbiettivo massizare ricompensa
processo iterativo prova -> osserva -> migliora

componenti 
agente -> cervello che prende decisioni
ambiente -> mondo con cui interagisce agente
stato -> situazione corrente del ambiente
azione -> scelte che agente compie in un determinato stato
ricompensa -> feedback numerico che indica quanto è buona una caerta azione
policy (sigma) -> strategia che l'agente usa per decidere quale azione compiere (regole del gioco)
valore -> stima del valore atteso di uno stato

CICLO APPRENDIMENTO
agente osserva stato
decide azione basato su policy
azione modifica ambiente
agente riceva ricompensa e osserva 
aggiorna propria strategia


## MODEL FREE VS MODEL BASED
model free agente impara solo dalle epserienza
model based agente costruisce ambiente (domotica di casa che mappa area di casa)

### OFF POLICY VS ON-POLICY
off policy : apprende seguendo policy che si sta esplorando 
on policy : apprendo da altre policy

Q-table (MATRICE stato azione)
## Q-LEARNING
off policy

SARSA : on policy


DQN : off policy e RL

## Q LEARNING
off policy (piu policy)
Trovare una funzione Q(s, a) che restituisca il valore atteso cumulativo
della ricompensa che l’agente può ottenere iniziando dallo stato s,
compiendo l’azione a e seguendo poi la strategia ottimale.

Q table
matrice valori q per ogni combinazione di stato S e azione A e



1 INIZIALIZZA 
q table con valori 
tasso di apprendimento alpha
fattore di sconto 
policy esplorazione

2 LOOP APPRENDIMENTO
1 per ogni episodio 
2 osservare stato corrent s
3 selezionare azione a
4 esegui azione ottieni riocompensa e nuova stato s
5 aggiorna tabella q con formula Bellman

VANTAGGI
imparare da esperienza casuali (off policy)
estendibili con DQN
funziona in ambienti discreti

limitazioni
non scala in ambienti continui
richiede molta esplorazione al inizio
q table grande