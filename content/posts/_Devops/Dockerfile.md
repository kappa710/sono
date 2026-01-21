file non deve avere estensione

esempio
```
FROM python
WORKDIR /app
COPY . . 
RUN pip3 install flask
ENV MSG="BENVENUTO"
CMD ["python","main.py"]
```

**comandi sempre in maiuscolo** 
per convenzione  WORKDIR  è /app 
COPY . .  (copia contenuto  cartella dove c è immagine e mettilo in workdir)
ENV MSG="BENVENUTO" (metti variabile ambientale = globale per container di docker)
RUN esegue 
CMD esegue  ( ha bisogno comandi come se fossero lista di python)


RUN vs CMD
RUN  viene eseguito durante il build 
CMD quando passiamo da immagine a container

