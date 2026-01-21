#### Specificare directory corrente
``` ./   ```
Serve per non creare problemi perché se abbiamo file ```-file01```
``` cat -file01``` viene visto da shell come ```cat -f ile01 ``` allora dobbiamo usare ``` cat ./-file01```

##### Accedere a file con spazi vuoti nel nome 
si accede a file con spazi vuoti nel nome usando gli apostrofi
``` cat "file con spazi vuoi"``` 
oppure si usa la \
``` cat file\ con\ spazi\ vuoti ```


#### Caratteri speciali
``` * ``` per indicare tutte le possibili sequenze 
``` file *.pdf``` vale per ogni file che termina con .pdf

```?``` per indicare che al suo posto puo esserci UN qualsiasi carattere


### prodotto cartesiano
{opzione1,opzione2} considera le opzione 1 e opzione 2
/{opzione1,opzione2}/{opzione3,opzione4} fa : {opzione1}/{opzione3}  {opzione1/opzione4}{opzione2}  ecc


