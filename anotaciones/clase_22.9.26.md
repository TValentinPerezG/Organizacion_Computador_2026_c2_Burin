### Instrucciones de Maquina de Brookshear

#### Saltar (B)
Ahora vamos a ver la instruccion para Saltar
Se hace con la B, y nos sirve para mandar acciones a registros mas tardios, si es que un valor en el registro llamado es equivalente al valor guardado en el registro 0.
Supongamos que tenemos un sistema que empieza de 22
22 R0=2
24 R3=2
26 B33C
...
Si se cumple esto, como en este caso si dan, se hace el salto y la siguiente instruccion estara en la direccion 3C
Si no es igual, la siguiente instruccion se da como seria de forma generica, en este caso si por ej R3=3, entonces el sistema simplemente seguiria a 28
...
3C

BRXY se fija si el registro R es igual al registro 0. En ese caso, si es igual, la siguiente instruccion esta en la direccion XY.
Si no es igual la sigueinte instruccion es la que sigue.

<br>
Ejercicio  
Sumar los registros R1 Y R2. Si el resultado es 5 guardarlo en la direccion A0. Si el resultado no es 5 guardarlo en la direccion B0.

En pseudo codigo:
R1<--- 3
R2<--- 2
R3<--- R1+R2
R5<--- 5 Para poder usar instruccion B
Preguntar si R3==5, en caso afirmativo guardar R3 en A0, moviendose frente al guardado del caso negativo.
GUARDAR LA SUMA EN EL REGISTRO B0 SI NO SE CUMPLIO
Saltar a salida comparando 0 consigo mismo
Guardar R3 en A0 si se cumplio
Salir

Aplicado seria
20 2103
22 2202
24 5312
26 2005
28 B32E
2A 33B0
2C B030
2E 33A0
30 C000
<br>

#### OR, AND, XOR (7, 8, 9) 

10100100 AND
10001110
10000100 = R3 = R1 AND R2  8312

10100100 OR
10001110
10101110 = R3 = R1 OR R2  7312


10100100 XOR
10001110
00101010 = R3 = R1 XOR R2  9312
<br>
Se lee la direccion AA que tiene un numero binario con signo.
Determinar si es un numero positivo o negativo
Si es positivo poner 0 en la direccion BB.
Si es negativo poner 1 en la direccion BB.

10100110 <-- NUMERO
10000000 <-- Solo importa el signo
es negativo? si: es negativo, no; es positivo

1C 2401 Tenemos el 0 pasarlos a la direccion de memoria correspondiente  
1E 2300 Tenemos el 0 pasarlos a la direccion de memoria correspondiente  
20 11AA Leer y guardar en R1 un numero que esta en AA 
22 2080 Guardamos 10000000 = 80h (mascara) en R0
24 8210 R2 = R1 AND R0
26 B22C Si R2 es igual a R0 salta a la direccion 2C
28 33BB Guardar 0 en BB
2A B02E Saltar a fin
2C 34BB Guardar 1 en BB
2E C000

<br>

Leer el dato que esta en la direccion AA.
Forzarle a ese dato el bit 3 en 1 y el bit 5 en 0 y guardarlo en BB

Leer un dato R1<--M[AA]
x x x x x x x x
7 6 5 4 3 2 1 0 <- nombre de los bits
x x x x Y x x x
x x Y x x x x x 

Bit 3 en 1:
a) mascara:
x x x x Y x x x
0 0 0 0 1 0 0 0 <-- R2
08 en R2
b) operacion: OR
R3 = R2 OR R1 Bit 3 en 1
Para poner 1 en un bit la mascara tiene un solo 1 en ese bit y la operacion es OR

Bit 5 en 1:
x x Y x x x x x
1 1 0 1 1 1 1 1 <-- R4 Mascara
b) operacion: AND
R5 = R4 AND R1 Bit 5 en 0
Para poner 0 en un bit la mascara tiene un solo 0 en ese bit y la operacion es AND

22 11AA M[AA]-->R1
24 2208 R2 = 00001000 mascara para forzar 1 en bit 3
26 24DF R4 = 11011111 mascara para forzar 0 en bit 5
28 7312 R3 = R1 OR R2 Bit 3 forzado a 1
2A 8534 R5 = R3 AND R4 Bit 5 forzado a 0
2C 35BB Guardo R5 que ya tiene ambos modificados en M[BB]
2E C000

<br>

Verificar si los bits 2 y 5 del número que está en la dirección AA son iguales, en caso afirmativo poner un 1 en el bit 4 y un 0 en el bit 3 y guardarlo en la dirección BB. En caso contrario guardar en BB el complemento a la base del número.

Para el complemento a la base, se hace XOR + 1

20 11AA Traigo lo que esta en AA
22 2024 Pongo la mascara para el 2 y 5
24 
-- B1--


