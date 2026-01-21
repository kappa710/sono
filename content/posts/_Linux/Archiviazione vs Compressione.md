### ARCHIVIAZIONE
**Archiviazione mette tanti file in un unico file .tar non comprime**

``` bash
tar -cf {nome_archivio.tar} {file1 da archiviare} {file2 da archiviare}
```

### ARCHIVIAZIONE e COMPRESSIONE
mette tutto in unico file .tar e poi
usare algoritmi per diminuire la dimensione dei file

``` bash
tar -czf {nome_archivio.tar.gz} {file1} {cartella1}
```

## ESTRAZIONE 

```bash
tar -xf {nome archivio} -C {cartella appoggio creata in precedenza}
```