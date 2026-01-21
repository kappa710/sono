
Docker Compose è utile per **gestire più container (servizi)** contemporaneamente, attraverso un file YAML strutturato in 3 sezioni principali:


## 📁 Struttura Base del File `docker-compose.yml`

1. **services** → definisce i container (es: backend, database)
2. **volumes** → volumi condivisi e persistenti
3. **networks** → rete virtuale tra containe



## SERVICES
```

services:
	nome_servizio_1:
		image: nome_immagine_da_prendere_da_docker 
		build: percorso_docker_file se lo hai
		container_name: nome_container
		enviroment:
			NOME_VARIABILE_AMBIENTE: 1223
		 ports:
			 -"porta macchina host: porta container" 
			 - "porta-fineportarange":"..."
		 volumes:
			 - nome volume:cartella da collegare 
			 - file o folder su  host:dove montarla nel container
		 command: comando shell
		 networks: 
			  -
			  -
		depends_on: servizio_che_aspetta_prima_di_partire
```
se comando è al  plurale (ports, volumes) allora è consigliato usare sempre gli -

## VOLUMES
attento se monti cartella nella macchina host  non hai bisogno di specificare nulla
se invece hai bisogno dopo sezione services
```
volumes:
	nome_volume1:
	nome_volume2:
```

## NETWORK

### BRIDGE
crea rete accessibile da altri docker conessi a stessa rete ma separazione da altri docker non connessi

### HOST
nessuna separazione tra docker e hardware fisico del host


##### Esempio Confg
configurazione piu comune 
```yaml

services:
	nomeServizio1:
		image: ...
		networks :
		- nomeNetworkDefinitoFine
		ports:
		- HOST:CONTAINER 
	nomeServizio2:
		image:
		networks:
		- nomeNetworkDefinitoFine

networks:
	nomeNetworkDefinitoFine:
	driver: bridge

```

###### ports
espone le porte su tutti le interfacce del host dove è installato docker

######  expose
non su host dove installato docker 

###### networks
i Docker container per comunicare fra loro devono stare nello stesso networks e accedono gli uni dal altro specificando  in questo modo schema://NomeServizio:Porta esempio in configurazione nginx
esempio ftp://NomeSerivizio1:21
```yaml
networks:
	nomeNetworkDefinitoFine:
	driver: bridge

```



## ⚙️ Comandi Docker Compose

```bash
docker compose up                     # Avvia tutti i servizi
docker compose -f custom.yml up       # Usa un file con nome alternativo
docker compose up -d                  # Avvio in background
docker compose up {nome_servizio}       # Avvia un servizio specifico
docker compose down                   # Ferma e rimuove i container
docker compose down -v --rmi all      # Rimuove anche volumi e immagini
docker compose ps                     # Mostra lo stato dei container
docker compose exec {nome_servizio} sh  # Esegue shell dentro al container

```