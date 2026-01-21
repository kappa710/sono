crossplatform , riprende programmazione orientata agli oggetti

### cmlets
(command-lets) avanzati rispetto comandi windows
consistono di Verbo-Oggetto
esempio Get-Content

piu importanti
### Get-Command
per vedere cmlet che possiamo usare

### Get-Help
`Get-Help cmdlet`

### Trova e scaricare altri cmdlets
`Find-Module -Name "modulo"`
`Install-Module -Name "modulo"`

### Get-Process
### Get-Service

### Get-NetCPConnection


## PIPING | 
potente in powershell perchè non viene passato solo il testo ma gli oggetti che quindi puoi ottenere metodi e attributi

### Invoke-Comand
fondamentale permette di eseguire comandi su altri computer  appendendo a fine 
-ScriptBlock{cmdlet}
`Invoke-Comand -ComputerName nome_computer -ScriptBlock{Get-Service}`