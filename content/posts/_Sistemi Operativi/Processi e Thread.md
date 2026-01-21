
### PROCESSSO VS THREAD
**PROCESSO**: programma in esecuzione con propria memoria o risorse o  unita base della locazione delle risorse 

risorse: codice , dati (variabil) , stato di esecuzione , program counter , risorse
ha suo spazio isolato dedicato

**THREAD** (filo esecuzione) piccola unita schedulabile del processo (thread parte del processo)
viene condivisa codice , dati (variabili) , stato di esecuzione , PC , risorse LI

esempio app che spawna processi diversi : Virtual box processo diverso per ogni virtual box




### CICLO PROCESSO
1) creato e dato PID ( identificatore)
2) READY pronto per essere eseguito e in attesa che cpu lo selezioni  
3) RUNNING 
4) WAITING (aspetta evento esterno spesso I/O)
5) TERMINATED


## SCHEDULING dei processi e thread
orchestratore dei processi 
Process Scheduler decide quale processo eseguire e per quanto tempo , gestendo l uso della CPU 
algoritmi di schedulaizone

### FIFO
firs in firs out , primo che entra viene subito seguito
ma attese inutile
usare in batch (processi che non interagiscono con utente)


### ROUND ROBIN
ogni processo riceve un quantum di tempo per eseguire se non ha finito torna in code 
adatto ai sistemi time-sharing



### SJF
seelezione il prcesso con durata di esecuzione piu breve tra quelli pronti (previsione)
viene eseguito fino al completamento 
negativi
starvation dei processi lunghi = possono essere mai eseguiti quelli lunghi


### MULTILEVEL QUEQUE
i processi vengono classificati in code in base alla loro natura e proprierita
viene eseguita una coda alla volta (prima quelle con + priorità)

negativi
backup mai eseguito




## CONTEXT SWITCH
Meccanismo attraverso il cui sistema operativa passa  l'esecuzione da un processo o thread a altro
anche passaggio a thread stesso processo c è contex switching ma meno "pesante"
durante conte switch il sistema deve : **mode switching** (processa tra user e kernel mode) che avviene quando un programma in esecuzione richiede servizi del kernel 
bisogna salvare lo stato del processo corrente , aggioranare strutture del so ( PCB , scheduler , ready queue ), caricare stato prossimo processo
#### costoso 
non fa nulla (solo overload) , caricamenti e salvataggi




### SINCRONIZZAZIONE dei Thread
esempio 
2 thread che devono accedere a stessa risorsa (variabile globale x)
quattro opzioni di sincronizzazione per dare priorita:
mutex (solo un thread accede a sezione critica del codice)
semafori (gestione tramite contatore )
monitors (incapsula la variabile con metodi di bloccaggio )
spinlocks