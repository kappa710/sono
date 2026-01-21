avvio server -> avvio istanza di postgres -> postmaster

### POSTMASTER
processo principale che gestisce il server e processi backend
postmaster funge da superivosore del processo
funge da listener
postmaster autenticare connessione , si crea processo backend per ogni connessione 
client puo averere piu connessioni

**ALTRI PROCESSI**
autuvacum : eliminare record droppati
bgwriter : scrive su file 
Wal Writer : writer ahead log 


SHARED MEMORY dati temporaneii ( SHARED BUFFERS , WAL BUFFERS , PROCESS ARREY)
esempio uso shared memory modifico dati con query rimangano nella shared memory cosi se un altro utente accede li prende dalla shared memory e poi dopo vengono scritti sul dischi da BG WRITER
### DATI
cluster di database
direcroty dei dati

## Funzioni istanza
SQL
Allocazione memoria 
sicurezza
e durabilita dei


