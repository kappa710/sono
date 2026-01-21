---
title: "subenetting"
# 1. Specifica l'immagine (deve essere in /assets/)
hero: "image.jpg"

# 2. Forza il layout a tutto schermo

# 3. Questo è il parametro magico che espande l'immagine hero su tutta la pagina
heroStyle: "background"
series: ["Ehi"]
series_order: 2

---


  

## Regola Fondamentale del Subnetting

  

> Nella Subnet Mask: tutti gli `1` (a sinistra) definiscono la rete, tutti gli `0` (a destra) definiscono gli host.

  

---

  

## Conversione CIDR -> Subnet Mask

  

**Obiettivo:** Convertire una notazione CIDR nella corrispondente Subnet Mask.

  

**Metodo:**

  

1.  **Trova il multiplo di 8 più piccolo del CIDR:** Identifica il multiplo di 8 più vicino *e inferiore* al valore del CIDR.

2.  **Calcola la differenza:** `CIDR - (multiplo di 8)`

3.  **Trova il valore dell'ultimo ottetto:** Utilizza la tabella seguente:

  



    *   1 = 128
    *   2 = 192
    *   3 = 224
    *   4 = 240
    *   5 = 248
    *   6 = 252
    *   7 = 254
    
  

**Esempio:**

  

`192.168.19.2/25`

  

1.  Multiplo di 8 più piccolo di 25: `24`

2.  Differenza: `25 - 24 = 1`

3.  Valore dell'ultimo ottetto: `1 = 128`

  

**Subnet Mask:** `255.255.255.128`

  

---

  

## Calcolo del Range di una Subnet Mask

  

**Obiettivo:** Determinare la dimensione di ogni subnet.

  

**Metodo:**

  

`256 - (ultimo numero diverso da 0 nella subnet mask)`

  

**Esempio:**

  

`255.255.128.0`

  

`256 - 128 = 128`

  

Il range è `128`. Le subnet aumentano di 128 nell'ottetto appropriato.

  

---

  

## Conversione Subnet Mask -> CIDR

  

**Obiettivo:** Convertire una Subnet Mask nella corrispondente notazione CIDR.

  

**Metodo:**

  

1.  **Trova il range:** `256 - (ultimo numero diverso da 0 nella subnet mask)`

2.  **Calcola il numero di bit 'n':** Trova `n` tale che `2^n = range`

3.  **Calcola il CIDR:** `(8 * numero di ottetti uguali a 255) + n`

  

**Esempio:**

  

`255.255.240.0`

  

1.  Range: `256 - 240 = 16`

2.  Numero di bit: `2^4 = 16`, quindi `n = 4`

3.  CIDR: `(8 * 2) + 4 = 20`

  

**CIDR:** `/20`

  

---

  

## Calcolo del Range CIDR

  

**Obiettivo:** Determinare l'intervallo di indirizzi IP in una subnet data la notazione CIDR.

  

**Metodo:**

  

`2^(multiplo di 8 maggiore del CIDR - numero CIDR)`

  

**Esempio:**

  

`/22`

  

Multiplo di 8 maggiore di 22: `24`

  

`2^(24 - 22) = 2^2 = 4`

  

Il range è `4`.

  

---

  

## Calcolo del Numero di Host

  

**Obiettivo:** Calcolare il numero di indirizzi IP utilizzabili in una subnet.

  

**Metodo:**

  

`2^(32 - numero CIDR)`

  

**Nota:** Questo calcolo fornisce il *numero totale* di indirizzi. Ricorda di sottrarre 2 per l'indirizzo di rete e l'indirizzo di broadcast per ottenere il numero di *host utilizzabili*.

  

---

  

## Determinazione della Rete (Data una Subnet)

  

**Obiettivo:** Trovare l'indirizzo di rete a cui appartiene un indirizzo IP.

  

**Metodo:**

  

1.  **Calcola il Range:** Vedi "Calcolo del Range di una Subnet Mask".

2.  **Moltiplica il Range per un numero intero:** Trova il multiplo del range che si avvicina di più all'ottetto interessante dell'indirizzo IP.

  

**Esempio:**

  

`48.25.24.71/21`

  

1.  Calcola il range:

    *   `/21` corrisponde a `255.255.248.0`

    *   `256 - 248 = 8`

2.  Le subnet vanno di `8` in `8` nel terzo ottetto.  Dobbiamo raggiungere `24`.  Fortunatamente, `24` è un multiplo di `8`.

  

**Indirizzo di Rete:** `48.25.24.0`

  

**Indirizzo di Broadcast:** `48.25.31.255` (La prossima rete parte da `48.25.32.0`)

  

---

  

## Calcolo del Numero di Sottoreti

  

**Obiettivo:** Determinare quante sottoreti si possono creare.

  

**Metodo:**

  

`2^(numero CIDR - numero minore al CIDR multiplo di 8)`

  

**Esempio:**

  

`/23`

  

`2^(23 - 16) = 2^7 = 128`

  

Si possono creare 128 sottoreti.

  

---