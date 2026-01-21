redirect = dirigere flusso da altre parte
tipologio redirect
standard output >  quello di prima lo metti nel dopo
standard input < (quello che prendi dopo lo metti nel primo comando)

`2>&1` prendi errori standard e mettilo nello stesso stream del output standard
  
differenza uso `2>&1`

ATTENTO un flusso puo essere indirizzato solo da una parte e viene valutato ultima spedizione flusso
`comando > ciao.txt > roma.txt` scrive solo file `roma.txt`
`comando 2> errori.txt > output.txt` scrive entrambi perchè diversi flussi

`find / -name output > ciao.txt 2>&1`
prende output stream errori e li mette insieme a output stream standard nel file e tutti insieme vanno nel file ciao.txt
`find / -name output 2>&1 > ciao.txt`
sul terminale mette stream 2 insieme a stream 1 e poi stampa solo stream che normalmenti stampati

`find / -name output 2>&1 2> ciao.txt`
sul file ciao.txt scrive solo errori



