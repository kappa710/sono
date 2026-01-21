## Scansione Attiva

### NMAP

RICORDA prima cosa nmap vede host è attivo attraverso ping e se non attivo interrompe scansione

fai -Pn per saltare scansione host attivo e fare scansione in ogni caso

nmap -sV ( vede attraverso payload cosa fa veramente porta ) e viene usato spesso con -sU perchè UDP ha bisogno di serie di payload inviati per vedere se porta aperta

## Scansione passiva

DNS Table , ARP table , Wireshark