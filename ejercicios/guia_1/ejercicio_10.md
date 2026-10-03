10. Convertir al sistema binario con 6 bits los siguientes números que están en base 10 y
operar considerando a los números convertidos como enteros con signo. Indicar los bits
de estado NZCVP:
26+19 26+32 26-19 26-26 19-26 -26+19
-26+26 -19+26 -19-26 -19-30 -19-31 -19-32

Contexto
pasar el numero a la cantidad de bits que se dijo (6) y verlo por representacion para entonces si hacer la cuenta

a. 26 + 19
11010 + 10011 en binario
entonces agregamos el signo a mabos conociendolo, para los 6 bits
011010 + 010011 = 101101
Tenemos que escribir los bits de estado NZCVP
N da que el resultado dio negativo
Z indica que dio 0
C indica si hay carry
V indica si hay overflow
P indica la cantidad de 1s que hay

Como se pasa de largo a los 6 bits, entonces el ultimo valor es 1, entonces lo toma como negativo, N = 1
No es igual a 0
Z = 0
No tuvo acarreo, porque no hay un 1 pasando del valor
C = 0
Sumamos 2 positivos y dio negativo, entonces hay Overflow
V = 1
El valor de P que se requiere para que la cantidad de 1 sea par, como ya hay 4 1s,
P = 0

b. 26 + 32
En este caso el 32 no se puede representar en 6 bits con su signo, por lo que no se puede representar y no se hace la cuenta.

c. 26 - 19
11010 - 10011 en binario
paso 10011 a negativo en representacion
01100 + 1 = 01101
queda
011010 + 101101 = 1|000111
en 6 bits queda 000111, correcto porque el resultado es +7

El ultimo valor es 0, no es negativo
N = 0
No es igual a 0
Z = 0
Tiene un 1 acarreado
C = 1
Es un positivo con un negativo, no puede haber overflow
V = 0
Tiene 3 1s, se necesita uno mas para ser par
P = 1

d. 26-26
11010 - 11010 en binario
paso 11010 a negativo en representacion
00101 + 1 = 00110
queda
011010 + 100110 = 1|000000
en 6 bits queda 000000, correcto porque el resultado es 0

El valor mas a la izquierda es 0
N = 0
Es igual a 0
Z = 1
Tiene un 1 acarreado 
C = 1
No hace overflow
V = 0
Como no hay 1s, ya es par
P = 0

e. 19 - 26
10011 - 11010 en binario
paso 11010 a negativo en represtancion, queda
010011 + 100110 = 111001
Si busco el complemento, me da 000110 + 1 = 000111 lo cual esta bien porque el resultado es -7

Es negativo
N = 1
No es igual a 0
Z = 0
No hay carry
C = 0
No hay overflow
V = 0
Los 1s ya son pares
P = 0

f. -26+19
-11010 + 10011 en binario
paso 11010 a negativo en represtancion, queda
100110 + 010011 = 111001
Si busco el complemento, me da 000110 + 1 = 000111 lo cual esta bien porque el resultado es -7
Se repiten todos los motivos del caso previo

g. 