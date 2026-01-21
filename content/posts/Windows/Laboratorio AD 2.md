### REPLICAZIONE DC
serve per non avere single point of failiure e migliorare performance
nuovo server , metti come DNS resolver IP del altro DC 
tra le opzioni  (aggiungi nuova foresta ecc.) metti la prima
attento se non riesci ad accedere o crea un nuovo utente e rendilo membro di 'Domain Admins'
o usa account Administrator
#### stato copia
```
repadmin /showreply 
```

```
repadmin /replsummary
```

se proprebli replica forza replica da Siti