passare a utente postrgres
```bash
sudo -i -u postgres
```

Creare database
``` bash
createdb mydb
```

Creare nuovo utente
```bash 
psql -c "CREATE USER myuser WITH PASSWORD 'mypassword';"
```

dare permessi
```bash
psql -c "GRANT ALL PRIVILEGES ON DATABASE mydb TO myuser;"
```

verificare connessione , ricordati che devi accedere ad un database per come funziona cluster postgres
``` bash
psql -U myuser -d mydb -h localhost -W
```