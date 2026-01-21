

cosa fondamentale e fare sempre creare un socket 

`s=socket.socket(socket.AF_INET,socket.SOCK_STREAM) # useremo ipv4,useremo TCP`

qua ci sono 2 strade 1 per server e 1 per client 
```python
s.bind('120.23.12.1',800)  # ip e porta a cui si colleghera il client
s.listen()  # mettere il server in modalita ascolto 
accettato,addre=s.accept() # restituisce il socket dove c è collegamento con client e info sul client
```  
(per ogni collegamento con client diverso c è un socket diverso) , finche non stabilisce una connessione non va avanti con il codice



per client invece 
``s.connect()``


comandi uguali per inviare o ricevere byte 
```
s.sendall(bytes)  
s.recv(intero) # indica i byte che saranno presi dal buffer di rete 
```

visto che entrambi funziona attraverso i byte devi trasformare stringe attraverso metodi `.encode() `e `.decode()`
