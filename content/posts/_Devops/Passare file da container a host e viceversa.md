crea immagine e assegnali nome
`podman build . --tag {nome_immagine}`

runna container in modalita interattiva
`podman run --name {nome_container} -it {nome_immagine}`

su altro terminale creato per passare file da container -> host
`podman cp {nome_container}:{posizione_file}   {path}\{nome_file}`