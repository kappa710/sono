---
title: ip4 intro
---
### prerequisiti

##### trasformazione numero da decimale e binario e viceversa
AGGIUNGI IMMAGINI
###### cosa è idirizzo IP
sono 32 bit ( 4 ottetti ) che identificano unicamente un host in **quella rete**

###### come puo essere un indirizzo ip?
privato o pubblico


#### classi IP v4 Pubbliche
1-126  CLASSE A
128-191 CLASSE B
192-223 CLASSE C
224-239 CLASSE D (MULTICAST)
249-255 CLASSE E SPERIMENTALI
###### classi IP v4 PRIVATE
da 10.0.0.0 a 10.255.255.255    subnetmask  /8  serve per ISP
da 172.16.0.0 a 172.31.255.255 /16 serve per universita ecc.
da 192.168.0.0 a 192.168.255.255  / 24 serve per LAN


###### ip speciale 127.0.0.1 come si chiama
loopback

###### a cosa serve loopback ?
testare network stack ( TCP IP ) nel device     

### SUBNETTING

###### Cosa è il Subnetting?

È il processo di dividere una rete di grandi dimensioni in reti più piccole e gestibili, chiamate sottoreti (subnets). Questo permette una migliore organizzazione, sicurezza e efficienza nella gestione degli indirizzi IP.

###### Cosa è la Subnet Mask?

È un numero a 32 bit (per IPv4) che viene utilizzato per definire quale parte di un indirizzo IP appartiene alla rete e quale parte appartiene all'host all'interno di quella rete. Si compone di una sequenza di '1' seguiti da una sequenza di '0'. Gli '1' indicano la parte di rete, gli '0' la parte di host.

###### A cosa serve l'indirizzo di rete e a quale IP corrisponde?

L'indirizzo di rete serve a identificare in modo univoco una specifica sottorete. È il **primo indirizzo IP disponibile** in una data sottorete (escluso l'indirizzo di broadcast). Per identificarlo correttamente, è necessario l'indirizzo IP e la Subnet Mask (o la notazione CIDR).

###### A cosa serve l'indirizzo di broadcast e a quale IP corrisponde?

L'indirizzo di broadcast serve per inviare dati a **tutti i dispositivi contemporaneamente** all'interno di una specifica sottorete. È sempre l'**ultimo indirizzo IP disponibile** in una data sottorete.

###### IP vs Subnet Mask
- **Indirizzo IP**: Identifica un singolo dispositivo su una rete. È composto da una parte di rete e una parte di host.
- **Subnet Mask**: Definisce i confini tra la parte di rete e la parte di host dell'indirizzo IP. È una sequenza binaria di '1' seguita da '0'. Ad esempio, `255.255.255.0` è una subnet mask comune.


###### Per cosa sta CIDR?

CIDR sta per **C**lasses **I**nter-**D**omain **R**outing. È un metodo per allocare indirizzi IP e indirizzare il routing dei pacchetti IP.

###### Trovare l'indirizzo di rete partendo da un IP (TEORIA)

Per trovare l'indirizzo di rete di un indirizzo IP, devi eseguire un'operazione logica **AND bit a bit** tra l'indirizzo IP e la Subnet Mask corrispondente.

###### Trovare l'indirizzo di rete (Metodo pratico)

1. **Trova la Subnet Mask** o ricavala dalla notazione CIDR.
    
2. Individua l'ottetto (o gli ottetti) della Subnet Mask dove iniziano gli '0' (ovvero dove la Subnet Mask non è `255`).
    
3. Calcola la dimensione del blocco (o "magic number") per quell'ottetto: `256 - valore_subnet_mask_ottetto`. Questo ti darà la dimensione delle sottoreti.
    
4. L'indirizzo di rete sarà un multiplo di questo blocco, il più grande multiplo che è minore o uguale all'ottetto corrispondente dell'IP dato.
    

**Esempio:** Se hai IP `192.168.10.75` e Subnet Mask `255.255.255.192` (che è `/26` CIDR).

- L'ultimo ottetto della SM è `192`.
    
- Dimensione del blocco: `256 - 192 = 64`.
    
- I multipli di `64` sono `0, 64, 128, 192...`
    
- Poiché l'ottetto dell'IP è `75`, l'indirizzo di rete sarà `192.168.10.64`.
    

###### Differenza tra "quanti IP sviluppa" e "IP disponibili"

- **Quanti IP sviluppa (Total IP addresses in a subnet)**: Questo si riferisce al numero totale di indirizzi IP all'interno di una data sottorete. È calcolato come 2numero_di_bit_host.
    
- **IP disponibili (Usable Host IP addresses)**: Questi sono gli indirizzi IP che possono essere effettivamente assegnati ai dispositivi (host) all'interno della sottorete. Sono gli IP totali meno due: l'indirizzo di rete (il primo) e l'indirizzo di broadcast (l'ultimo). Quindi, 2numero_di_bit_host−2.
    

###### Come è la notazione CIDR?

La notazione CIDR è rappresentata come:

`Indirizzo_IP / Numero_CIDR`

- `Indirizzo_IP`: L'indirizzo IP di base della rete o di un host.
    
- `Numero_CIDR`: Un numero intero da 0 a 32 (per IPv4) che indica il numero di bit consecutivi impostati a '1' nella Subnet Mask, partendo da sinistra. Questo numero definisce la dimensione della parte di rete dell'indirizzo IP.
    

**Esempio:** `192.168.18.0/24`

- Il `/24` significa che i primi 24 bit della Subnet Mask sono '1'.
    
- Corrisponde a una Subnet Mask binaria: `11111111.11111111.11111111.00000000`
    
- In decimale: `255.255.255.0`
    

###### Numero di host disponibili da CIDR

Per calcolare il numero di host disponibili in una rete data la notazione CIDR:

1. **Sottrai il numero CIDR da 32**: 32−Numero_CIDR=Numero_di_bit_host. Questo ti dà il numero di bit disponibili per gli host.
    
2. **Eleva 2 alla potenza del "Numero_di_bit_host"**: 2Numero_di_bit_host. Questo è il numero totale di indirizzi IP nella sottorete.
    
3. **Sottrai 2 dal risultato**: 2Numero_di_bit_host−2. Questo è il numero di host effettivamente disponibili (escludendo indirizzo di rete e broadcast).
    

**Esempio:** Per `192.168.9.19/28`

1. `32 - 28 = 4` (ci sono 4 bit per gli host)
    
2. `2^4 = 16` (16 indirizzi IP totali nella sottorete)
    
3. `16 - 2 = 14` (14 host disponibili)