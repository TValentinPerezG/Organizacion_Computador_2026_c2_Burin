16. Dadas las siguientes configuraciones de binarios de punto flotante IEEE 754
de precisión simple, indicar el número almacenado en base 10.
a. 86157840]16 b. 321200235]8 c. 00000000]16
d. 2147483648]10 e. 86E4785A]16 f. 17740000000]8


c. 
1) Paso a binario
0000 0000 0000 0000 0000 0000 0000 0000 0000
2) Le doy el formato correcto
0 00000000 00000000000000000000000
3) Busco el exponente
00000000 = 0 - 127 = -127 exponente
4) Vemos el resultado
+1 x2^(-127)
En decimal: 5,88 10^(-39)

f.
ver si entra
son 33 bits, pero como el numero mas significativo es 001, podemos ignorar el primero que sobra y que quede 
01 111 111 100 000 000 000 000 000 000 000
lo separamos para IEEE754 precision simple
0 11111111 00000000000000000000000
2) Calculo el exponente
11111111 = 255 - 127 = 128 exponente
3) Vemos el resultado
+1 x2^128
En decimal: 3,4 10^38