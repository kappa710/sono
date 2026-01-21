creato quando eseguo file eseguibile (permessi di r e x)
creato in foreground 
per background si usa il & alla fine comando shell

### generazione dei processi (padre e figlio)
INIT punto di inizio di tutti i processi (PID) e crea una sorta di albero 
al inizio padre e figlio quasi simili ma figlio poi si specializza in altro


#### PCB
tipo i-node ma per processi , tiene tutte informazioni su processo
si trova solo su RAM

esempio robe su PCB
pid numero naturale che identifica univocamente stesso ID (riiutilizzabile)
ppid : pid del processo padre
status


#### BACKGROUND VS FOREGROND VS DEATCHED
FOREGROUND  in primo piano
BACKGROUND in secondo piano non interagisci direttamente 

per processi in terminale cambia leggermente
BACKGROUND è legato a presenza TERMINALE dove se chiuso terminale RIP processo 
DEATCHED non è legato a terminale se terminale chiuso il processo va avanti 
