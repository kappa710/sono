struttura comando
``` bash
iptables [option] [chain] [criteria] -j [target]
```
esempio
```bash
iptables -I INPUT 1 -m state --state ESTABLISHED,RELATED -j ACCEPT
```
### glossario
tabella : insieme di catene (es. FILTER:input,output,forward    NAT: ecc)
catene : insieme di regole
target : cosa fare con pacchetto (ACCEPT , DROP)

### Chains (catene)
INPUT : i pacchetti in entrata
OUTPUT : i pacchetti in uscita
FORWARD: pacchetti destinati ad un altro host (il nostro pc fa da proxie)
PREROUTING: prima che i pacchetti in entrata subisco tabella routing
POSTROUTING: dopo che i pacchetti in uscita ma applicate gia altre robe

### Opzioni
-A aggiungi regola a fine 
-I insersci regola in determinata posizione