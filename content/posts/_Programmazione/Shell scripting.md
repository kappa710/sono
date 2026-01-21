## Variabili 
assegnazione variabile
`numero=1`
`nome_variabile="stringa"`
`nome_array=("Questo" "è" "un" "array")`
`output_comando_linux=$(comando_linux)`


accedere a variabile
`"${nome_variabile}"`


## Array 
leggere elemento in posizione
`${array[0]}`


## IF
```
if [[ condizione ]];  then
	echo " "
elif [[ condizione 2]]; then 
	echo""

else 
	echo ""

fi
```


attento se usi if al posto degli elif bisogna chiudere sempre con fi
```
if [[condizione]]; then
	echo ""
fi

if [[ condizone2 ]]; then
	echo ""
```

esempio particolare uso if
```
if [[ $nome_arrey =~ variabile_da_controllare ]]
```


codice uscita 1 errore
codice uscita 0 tutto bene



## CASE
piu leggibile
```
case variabile in
	valore)
	 cosa da eseguire
	 ;;
	valore2)
	 cosa da eseguire
	 ;;

	 *)  #tipo else
	 cose da eseguire
	 ;;
esac #fine case 
```

## FOR

```
for iteratore in 1 2 3 4 5 6 7 8 9 10 ; do
echo "${iteratore}"
done
```

```
for ((iteratore=1;iteratore<=10;iteratore++)) ; do
echo "${iteratore}"
done
```

```
for iteratore in {1:10} ; do
echo
done
```

```
for nome in "Ciao" "Casa" ; do
echo
done
```

```
for variabile in ${nome_arrey[@]} ; do       
....
done
```

## WHILE
```
while [[ condizione ]] ; do
	echo "ciao"
done
```

### ARGOMENTI DA TERMINALE
`$1` primo parametro comando
`read -p "inserisci una stringa" argomento` (si salva cosi dentro variabile stringa argomento)




### Funzioni
```
nome_funzione(){
	local risultato=$(($1 +$2))
	return $risultato
}

nome_funzione #chiamata funzione
nome_funzione 3 5 
echo "$?" #perchè esegue ultima operazione in questo caso return nome_funzione
```

return si usa per codice di chisura
