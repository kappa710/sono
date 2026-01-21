## 1 FAI FUNZIONARE VIRTUALIZZAZIONE AMD VT
disattiva da funzionalita windows
- hypervisor
- sottosistema linux
- windows machine platform

da powershell questo codice
`Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\DeviceGuard" -Name "EnableVirtualizationBasedSecurity" -Value 0`
disattiva da attiva e disattiva funzionalità di windows  hyper V , wsl e piattaforma macchien virtuali 
continua usando questo [tool](https://www.microsoft.com/en-us/download/details.aspx?id=53337)  
se ancora non va usa questa [guida](https://gns3.com/community/featured/fixing-vt-x-or-amd-v-not-available-in-windows-11-with-vmware-ws-pro-and-player)

## INSTALLA VM WARE 
installa , importa .ova e attiva nelle impostazioni macchina sezione processore AMD V

## PER  VM PNETLAB
per fare funzionare ishare2 devi prima rimuovere da `/etc/apt/sources.list`
ultima riga con trusted