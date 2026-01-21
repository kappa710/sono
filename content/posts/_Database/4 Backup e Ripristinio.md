backup full 
backup incrementale copia le ultime modifiche fatte
backup differenziale copia le ultime cose aggiunte


### backup logico
della struttura


### backup fisico
della directory dove salvato i dati


## continuos archiving e PITR
backup fisici + log delle transazioni
non bisogna fare noi il backup , lo fai in modo automatico
```
archive_mode = on
arcive_command='cp %p /path_to_archive/%f'
```

## RIPRISTINO
FERMARE SERVER POSTGRESQL
RIPRISTARE IL BACKUP FISICO NELLA DIRECTORY DATI
COPIARE IL LOG




## RESTORE
copia da archivio secondario e ripristino nella posizione originale


