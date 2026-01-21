serve per fare task in modo asincrono che non si bloccano aspettando 

  

per I/O ( read , network ecc.)

event loop : sceglie quale runnare 

  

async def creaa coorutine ( funzione che puoè essere messa in pausa permettendo cosi altre funzioni di funzionare e poi ripresa)

e restituisce coorutine

solo con await inzia a essere eseguita coorutine e finisce ( dobbiamo usare task affinche piu coorutine fatte insime )

  
  
  

che deve essre passasato a ayncio.run(funzione_asincrona())



### P2
  

eseguire piu coorutine insieme con coorutine

  

modo 1 creando task

task1= asyncio.create_task(funzione asincrona)

task2 = ecc

  

result1 = await task1

result2 = await task2

  
  

metodo 2

result = await asyncio.gather(funzione1,funzione2)

result sta lista e mette risultati in ordine lista

ma non funziona con errori bene

  
  

metodo3

async with



## THREAD
piu programmi contemporaneamente

  

librearia threading 

  

x=treading.Thread(target=funzione,args=(argomento_funzione1,argomentofunzione2)

  

y=treading.Thread(.....)

x.start()

y.start()

  
  

thread.deamon per vedere se sono attivi o no

  
  

thread.join() per riunirli in quello principale