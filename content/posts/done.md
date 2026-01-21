---
title: "Il mio post largo"
# 1. Specifica l'immagine (deve essere in /assets/)
hero: "image.jpg"

# 2. Forza il layout a tutto schermo
layout: "background"

# 3. Questo è il parametro magico che espande l'immagine hero su tutta la pagina
heroStyle: "background"

# 4. Opzionale: se l'immagine scurisce troppo il testo, puoi provare "big"
# heroStyle: "big"
---
```
caster@kali:/mnt/hgfs/ID$ ./kerbrute userenum --dc core.myownsummer.org -d myownsummer.org possibleusernames.txt            

    __             __               __     
   / /_____  _____/ /_  _______  __/ /____ 
  / //_/ _ \/ ___/ __ \/ ___/ / / / __/ _ \
 / ,< /  __/ /  / /_/ / /  / /_/ / /_/  __/
/_/|_|\___/_/  /_.___/_/   \__,_/\__/\___/                                        

Version: dev (9cfb81e) - 10/19/25 - Ronnie Flathers @ropnop

2025/10/19 16:43:23 >  Using KDC(s):
2025/10/19 16:43:23 >  	core.myownsummer.org:88

2025/10/19 16:43:24 >  [+] VALID USERNAME:	 sspeed@myownsummer.org
2025/10/19 16:43:24 >  [+] VALID USERNAME:	 kestre@myownsummer.org
2025/10/19 16:43:24 >  [+] VALID USERNAME:	 svettel@myownsummer.org
2025/10/19 16:43:24 >  [+] VALID USERNAME:	 rkubica@myownsummer.org
2025/10/19 16:43:25 >  Done! Tested 102 usernames (4 valid) in 1.128 seconds
```

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