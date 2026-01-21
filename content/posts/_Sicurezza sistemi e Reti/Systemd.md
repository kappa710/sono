suit di supervisore di processi
systemctl client

3 parti fondamentali di un file  definisce un servizio
1. [Unit]: contiene metadati e dipendenze e quando per partire 
2. [Service]: cosa e come fa il servizio
3. [Install]: come servizio deve essere collegato ad avvio automatico (per esempio systemctl enable service)