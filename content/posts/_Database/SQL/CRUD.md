
## SELECT
`SELECT nome_colonna FROM nome_tabella`

## INSERT
```INSERT INTO nome_tablela(colonna1, colonna2,..)
VALUES (valore_colonna1, valore_colonna2)
```

### CLAUSOLE
## GROUP BY
aggrega dati da multipli record e li gruppa in colone
`SELECT nome_colonna, COUNT(*) FROM nome_tabella GROUP BY nome_colonna;`

### ORDER BY
ordina e li ordina in ordine ascendente (ASC) o descendente (DSC) 
`SELECT * FROM nome_tabella ORDER BY nome_colonna ASC`

## HAVING 
è usato con altre clausole per filtrare gruppi o risultati su condizioni
```
SELECT nome_colonna. COUNT(*)
FROM nome_tabella
GROUP BY nome_colonna
HAVING nome_colonna LIKE '%Hack%';
```