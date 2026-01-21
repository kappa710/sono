Imitare neuroni biologici 
funzione per connessione e addattamenti
imparano via strati successivi
### NEURONI ARTIFICIALI
riceva danti in input 
elabora input tramite pesi
decide se attivarsi oppure no tramite una funzione di ativazione

Esempio Pratico
input : nuvole peso 0.2 , temp bassa 0.2 meteo 0.9
neurone somma input per peso 
funzione attivazione decide cosa fare

inizialmente pesi casuali ma poi aggiustati per ridurre errore
allenare = modificare pesi 

STRUTTURA DI RETE NEURALE
STRATO Di INPUT
Strati NASCOSTI elaborano (estraggono informazioni , combinano i risultati concreti complessi )
Strato OUTPUT fornisce risultato finale


Funzione di attivazione
serve per dire al neurone quando deve attivarsi

non lineariata 


COME IMPARA RETE 
1 riceve un esempio input
calcola un risultato
confronta con risposta corretta
corregge i pesi per ridurre errore (backpropagation)

ALLENARE RETE =  imparare a CORREGGERE ERRORE

ESEMPIO RICONOSCERE NUMERO a CASO


DEEP LEARNING
tani strati nascosti


## COSA PER ADDESTRARE RETE
DATI
POTENZA DI CALCOLO
TEMPO
OTTIMIZZAZIONE (aggiorna pesi)
PERDITA (misusa quanto rete sbaglia)


## CCN
concetto visivo , elaborazione immagini , non lineare
ESTRAGGONO pattern visivi
usano filtri locali che scansioni parti immagini
Convoluzione : piccoli filtri kernel (scorrono su immagine e calcolano caratteristiche locali linee , curve ,bordi )
Pooling : riducono la dimensione mantenendo le informazioni piu importanti 
Strati densi finali : elaborano le feature per classificare

## RRN
reti che ricordano sequenze testo e suoni 
per dati sequenziali dove ordine conta
output passo input passo successivo

Esempio
il gatto dorme sul per prevedere prossima rete deve ricordare presedenti


## LSTM e GRU
memorizzano meglio grazie a memoria controllata loro decidono cosa ricordare o cosa no

## TRASFORMER
non leggono parola per paorola ma analizzano tutto insieme 
grazie a SELF ATTENTION
### SELF ATTENTION
assegna importanza diversa a parole in baso a contesto


ENCODER capisce il testo
DECODER da output
strati attenzione per assegnare importanza diversa in baso a contesto
