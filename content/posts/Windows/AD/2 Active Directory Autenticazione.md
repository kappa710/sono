
tutte credenziali **salvate nel DC**
quando un utente prova a autenticarsi ad un servizio , il servizio chiederà a Domanin controller se credenziali corrette

Protocolli usati :
**NETLM** (legacy)
**Kerbero**

##
KERBEROS
funziona per ticket


### PREREQUISITO
client invia ticket a servizio KDC  del DC per avere Ticket che permette genarare altro ticket
inviando  nome utente e timestamp criptato con chiave creata da passowrd utente

la rispsota è questo ticket che permette di generare altro ticket che è formato dal ticket hashato in modo che non puo essere letto da client e Session key che invece puo essere letto dal client
![Prerequisiti Kerberos](prerequisiti_kerberos.png) 


### CONNESIONE A SERVIZIO 
ora client chiede a servizio KDC del DC un TGS (Ticket garantet Service) che permette ad autenticarsi su specifico servizio

invia username e timestamp cifrati con session key , TGT hashato piu SPN (service principal Name ) che identifica servizio/nome_servizio) 
![Ticket Granting Ticket](TGT.png) 

il KDC risponde con TGS hashata con chiave del servizio e SVC Session Key hashata con session Key che ha il client

![Ticket Granting Service](TGS.png)


## NetNTLM

1 client invia richiesta al server che vuole accedere
2 server genera random numeri e  li invia al client come Challenge
3 client combina suo hash passowrd con challenge in Response e lo invia al server 
4 server forwarda Challenge e Response al DC
5 il DC sal Challenge prova a ricreare Response e se combaciano Response creato da lui e quella inviata dal Server allora autentica il client


![[NTLM.png]]