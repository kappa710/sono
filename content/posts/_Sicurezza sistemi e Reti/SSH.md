Secure shell
ha layer di crittografia
server sshd (deamon = eseguita in background)



per vedere chi ha loggato `w` o `who`

come configurarla
su client e server devi generare chiavi pubbliche e privae
`ssh-keygen`

attento : lascia yes password autenticazione poi dopo aver copiato chiavi puoi disattivarla
client da la  sua chiave pubblicha a server tramite comando
`ssh-copy-id -p {porta se diversa da 22} username@remote_host`
client si collega al server e il server da sue chiavi pubbliche ( del server) e controlla autenticazione


per usare chiave specifica privata per autenticarsi a server ssh
`ssh -i privatekey user@host` ricordati che chiave privata 600 come permessi
