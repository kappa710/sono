### passare da MAC a 48 bit a interface identifier (64 bit)

### 1 DIVIDERE MAC in 2 
 00:1A:2B:3C:4D:5E -> 001A2B   2C4D6E
### 2 INSERIRE IN MEZZO FFFE
001A2BFFFE2C4D6E

## 3 inverti il 7 bit (devi passare a binario)
0  = 0 in decimale -> 0000 
inverto il 7 bit -> 0010 -> 2 in decimale -> 2 in esadecimale
021
