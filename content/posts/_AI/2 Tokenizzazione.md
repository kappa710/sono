https://projector.tensorflow.org/
la macchina non capisce linguaggio umano ma la scompone e crea dei token dei caratteri
SCOMPONE IN TESTO IN TOKER COERENTI E ASSOCIA AD OGNI TOKEN UN NUMERO INTERO (vocabolario)
ciao assegnato a combinazione numerica 3241
sono altra combinazione  4321
marco altra ancora combinazione 4865

i numeri messi nel vettore -> vector tocker 
esempio
Testo : Ciao Mondo !
token -> ["Ciao" , "Mondo"]
vocabolario


### WORD LEVEL 
semplice ma fragile 
##### ignora errori di spelling 
token non presente nel vocabolario oppure convertito nel token unknown token
parole nuove , morfologia
##### parole nuove o rare
modello vocabolario fisso
e non riconosicti
#### morfologia
word level tratta parole coniugate o declinate come enitita diverse
modello non capisce che hanno stessa semantica e si trova **ridondanza**
## SUBWORD LEVEL
spezza parole in sottunita attraverso algoritmi : BPE , WordPiece , StentencePiece
le subword radici , prefessi , sufissi o combinazioni comuni
supera i 3 problemi problemi del word level : errori spelling , nuove , morfologia
flessibile (nuove parole ) , robusta (funziona con errori ) , efficace 
 
#### FUNZIONAMENTO
analizza corpus testi 
si trovano le sottosequenze piu frequenti
si costruisce vocabolario compatto di subword

#### BPE
unisce le coppie di caratteri piu frequneti
inizialmente separa tuti caratteri 
step 1 unisce l e O
step 2 unisce e + s
...
risultato finakle -> "low" "est"

#### VANTAGGI 
gestitisce termini sconosciut 
comaptta il lessio 
affronta morfologia e diverse lingue 

### SVATAGGI
token non sempre interpertrabili 
esempio ###it 
richiede training inziale
sensibile a spazi chat 

#### wordpiece
BPE + probabilità
#### SentencePiece
lavora direttamente in byte

### CHARACTER LEVEL 
ogni carretere token
robusta ma super inefficiente 
usato quando morfologia complessa

vantaggi
lingua indipende
morfologia preservata
vocabolario compatto

svantaggi
perdita di significato semantico
sequenze piu lunghe

