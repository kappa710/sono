2 file di configurazione importanti 

`/pg_hba.conf` autenticazione basata su host  
`/postgresql.conf` parametri  server (memoria , rete) 

in Postgres il Cluster permette di avere piu database nella stessa istanza ma completamente isolati tra loro
Quando accedi da remoto devi accedere a database  e creare una connessione alla volta (dal client puoi gestire piu connessioni alla volta)

ci sono 2 template 
template 1 
template 0 master (se modifichiamo template 1)
solo proprietario database o SU puo eliminare database
`DROP DATABASE name;` 


### TABLESPACE
organizzare spazio su disco
directory del filesystem per memorizzate dati , tabelle ecc.
2 tablespace : pg_defualt , pg_global

creare tablespace
```
CREATE TABLESPACE tablespace_name
OWER user_name
LOCAION directory_path;
```


### SCHEMA
modo logico per separare database
serve per consentire a molti utenti di utilizzare un database senza interferire tra loro
per organizzare gli oggetti dal database in gruppi logici rendendoli piu gestibili












## CREARE TABELLA
```
CREATE TABLE docenti(
id serial,
nome valchar(20),
cognome valchar(20)
);
```

per creare tabella usando schemi
```
CREATE TABLE nome_schema.nome_tabella(
id serial,
nome valchar(20),
cognome valchar(20)
);
```