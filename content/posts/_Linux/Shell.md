

nome_utente@nome_macchina

VARIABILI:

di tue tipo shell ( valgono solo per quel terminale ) vs enviroment valgono ovunque

posso definire variabile di shell cosi

cosi ASSEGNO VARIABILE nome_variabile=contenuto (senza spazio)
per assegnare piu valori dobbiamo usare i :
ciao=valore1:valore2:valore3

cosi la uso $nome_variabile ( posso usare anche cosi quelle di env)

per fare diventare variabile di shell → env comando export
devono essere per convenzione in maiuscolo nomi variabili
quale è variabile di env piu importante PATH dove vengono contenuti i percorsi separati da : dove la shell cerca i “programmi da eseguire”


### Sintassi comandi linux
Argomenti vs  opzioni
opzioni hanno trattino

`comando -o(opzione solo una lettera) --versione_estesa_opzione`
roba tra [] nel --help è opzionale 
### Shebang

si mette prima riga file

#!{path del file che usera per aprire file senza specificare path}

RICORDA devi cambiare permessi per eseguirlo, per eseguirlo :

./{nome_file}


### fare qualcosa ad apertura shell
bashrc