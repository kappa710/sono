### HARD LINK
=alias / ethichetta  , condivide stesso inode (UID) (riferimento diretto al file su memoria fisica)
punta a memoria fisica
rimuovendo il file principale , hardlink rimane
non si puo creare hardlink di cartelle e per file system diversi
`ln file_da_hard_linkare hard_link`
```bash 
ln file_da_hard_linkare nome_hard_link
```

### SOFT LINK 
punta a file di cui fatto softlink
è file che conteiene un collegamento
`ln -s file_da_soft_linkare  soft_link`
```bash 
ln -s  file_da_hard_linkare nome_hard_link
```