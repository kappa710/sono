LSASS + importante perchè attaccanti possono dumpare il processo e ottenere hash 

| Processo                                     | Cosa fa                                                 |
| -------------------------------------------- | ------------------------------------------------------- |
| System idle process                          | mostra CPU time non usate                               |
| System                                       | gestisce low-level kernel operazioni e driver           |
| lsass.exe (Local Security Autorithy process) | dove salvati loginis e password polcies , hash          |
| smss.exe                                     | gestione sessioni (primo processo user-mode)            |
| csrss.exe                                    | client/server runtime subsystem (console e Gui support) |
| wininit.exe                                  | starta i servizi di sistemi dopo smss                   |
| services.exe                                 | gestisce servizi di windows                             |
| exploorer.exe                                | desktop, taskbar , file browsing                        |
