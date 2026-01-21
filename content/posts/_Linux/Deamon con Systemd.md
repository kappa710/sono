### Demone
deamon è un processo che gira in background e di solito è fuori dal controllo del utente 


per creare un demone crea  un nuovo file con estensione `.service` nella cartella `/etc/systemd/system`

risorse [systemd Red Hat](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/10/html/using_systemd_unit_files_to_customize_and_optimize_your_system/working-with-systemd-unit-files)     ,  [systemd Arch Linux](https://wiki.archlinux.org/title/Systemd#Writing_unit_files)


3 parti di un file che definisce un servizio
1. [Unit]: contiene metadati e dipendenze e quando per partire 
2. [Service]: cosa e come fa il servizio
3. [Install]: come servizio deve essere collegato ad avvio automatico (per esempio systemctl enable service)

Esempio : install ci dice che fa parte cantanti , unit che si esibira dopo altro cantante

```
[Unit]

Description=per avviare il mio server fastapi
After=network.target
```

After significa che  se demone verra startato  sara startato solo dopo che network sara up

```
[Service]
User=sammy
Group=www-data
WorkingDirectory=/home/sammy/myproject
Environment="PATH=/home/sammy/myproject/myprojectenv/bin"
ExecStart=/home/sammy/myproject/myprojectenv/bin/uwsgi --ini myproject.ini
```


```

[Install]
WantedBy=multi-user.target

```



ATTENTO DOPO AVER MODIFICATO FILE esegui questo comando 
``` bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl restart prova.service
```


Type: 
forking si stacca ma bisogna seguirlo ma serve PID file per seguirlo e non demone
simple per avvio leggero
exec gestisce bene errori 
onesthoot se ne frega
notify per demoni
dbus per collegamento tra progetti


esempio .service fatto da me 
```
[Unit]
Description=uvicorn instance to serve nginx
After=network.target

[Service]
User=user
Group=www-data
WorkingDirectory=/home/user/Progetti/fastino
ExecStart=/home/user/Progetti/fastino/.venv/bin/uvicorn main:app --uds /home/us>


[Install]
WantedBy=multi-user.target

```