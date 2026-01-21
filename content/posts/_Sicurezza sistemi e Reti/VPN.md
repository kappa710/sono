
Come funziona VPN
creata un interfaccia virtuale di rete e una subnet appartente a vpn

- **Indirizzamento**: I pacchetti dati destinati a un indirizzo nella subnet della VPN vengono inviati all'interfaccia di rete virtuale.

- **Incapsulamento**: L'interfaccia virtuale cifra i pacchetti e li "impacchetta" in un nuovo pacchetto. Questo pacchetto esterno ha come destinazione l'indirizzo IP pubblico del server VPN e utilizza la porta specificata nella configurazione.

- **Trasmissione**: Il pacchetto cifrato viene infine inviato tramite l'interfaccia di rete fisica del dispositivo (es. Wi-Fi o Ethernet) verso il server VPN.


Attento:
- LA PORTA del SERVER serve a gestire le connessioni
- se vuoi un servizio su server o peer basta che selezioni quel servizio in ascolto su ip della subnet vpn
### CONFIGURAZIONE WIREGUARD

articolo vpn: https://www.digitalocean.com/community/tutorials/how-to-set-up-wireguard-on-ubuntu-20-04

## SERVER e PEERS
crea chiave privata
```
umask 0777
wg genkey | sudo tee /etc/wireguard/private.key
sudo chmod go= /etc/wireguard/private.key
```

crea chiave pubblica 
`sudo cat /etc/wireguard/private.key | wg pubkey | sudo tee /etc/wireguard/public.key`
`wg pubkey > private.key >public_key`



## Configurazione Server

file /etc/wireguard/wg0.cong
```
[Interface]
PrivateKey = {chiave privta tua}
Address = {ip che vuoi dare a macchina nella subnet vpn / subnet}
ListenPort = {porta a cui i peer si collegano (51820)}
SaveConfig = true

[Peer1]
PublicKey = {chiave pubblica del peer stassa vpn}
AllowedIPs = {quale ip subnet accetta da quel peer (subnet vpn/32)}

[Peer2]

```


per permettere ip forwarding verso internet , modifica il file `/etc/sysctl.conf`

``net.ipv4.ip_forward=1``
e riavvia impostazioni con `sudo sysctl -p`



attiva porta 
```
sudo ufw allow 51820/udp
sudo ufw enable
```

attiva servizio su server
```
sudo systemctl enable wg-quick@wg0.service
sudo systemctl start wg-quick@wg0.service
```


## PEER
sempre file in /etc/wireguard/wg0.conf
```
[Interface]
Address = {ip della subnet VPN del peer (ovviamente)}
SaveConfig = true
ListenPort = 33963
PrivateKey = {chiave privata del Peer}

[Peer]
PublicKey = {chiave pubblica del server}
AllowedIPs = {pacchetti con questo range ip verrano inviati al server vpn}
Endpoint = {ip reale del server : porta in cui il server in listening}


```


Per attivare servizio sui Peer
`sudo wg-quick up wg0`

Per modificare qualcosa 
`sudo wg-quick down wg0`
modifica il  file `/etc/wireguard/wg0.conf`
`sudo wg-quick up wg0`

per google cloud diverso serve specificare MTU