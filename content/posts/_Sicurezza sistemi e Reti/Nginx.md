REVERSE PROXY 
utile per load balancer (smista grossi carichi di lavoro tra vari servies)



NEL CASO USIAMO PYTHON e FRAMEWORK BACKEND  
 startare con uvicorn che crera un socket da zero nella path  indicata (uds sta per unix domain socket) 
```uvicorn nome_file:istanza_principale_di_framewrok --uds ~/fast.sock```



CONFIGURAZIONE

```
server { 
    listen 80;
    listen [::]:80;

    server_name 192.168.22.87;

    location / {
        proxy_pass http://unix:/home/user/fast.sock;
        include proxy_params;
    }
}
```

SERVER_NAME
server_name aiuta nginx a fare routing in questo caso se richiesta viene da chi si è interfacciato a servizio usando ip 192.168.22.87 ( fa x)
si usa anche per diversi nomi di dominio
per capire come funziona server_name usa questa guida : [NGINX server_name: How to use it - Status List](https://statuslist.app/nginx/server_name/)


LOCATION 
indica la path deve inzizare con / e finire con / (solo / nel caso root)


PROXY_PASS 
passa richiesta a  server e poi spedice la risposta del server a chi ha fatto la richiesta
possiamo passare o ip e porta del server 
oppure il file.sock creato dal sever (come in questo caso)