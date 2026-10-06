## Parcial

Lunes 19

Puede haber preguntas teoricas, como detectar overflow, carry, conceptuales

Circuitos combinacionales con salidas o con conpuertas



## Modo de direccionamiento (MD)

Si por ejemplo tengo 4 en la celda de memoria A0, y hago 11A0, estoy pasando el valor dentro de la celda de memoria A0 a R1, por lo que es un direccionamiento directo

### Modo de direccionamiento Indirecto (MDI)

Supongo que tengo A3 en A1 y 2 en A3

Supongamos que tenemos un comando que comienza con Z, y hacemos
Z1A1, en este caso lo que hace es buscar la direccion dentro de la direccion, asi, llegaria a A1, veria A3, y finalmente guardaria en R1 el 2.

En la maquina de bookshear este direccionamiento no existe, por lo que si tenemos un ejercicio que lo pide de esta manera, entonces 

Se puede resolver en la maquina de bookshear, pero no tiene sentido hacerlo porque para un sistema asi se utilizaria otro sistemas que tengan estos modos de direccionamiento

<br>
Ejemplo  

Almacenar en el registro R3 un dato cuya direccion se encuentra en la direccion 0C. Este dato puede ser el primero de los elementos de un vector

00 2213 R2 = 13 Se crea en R2 la primera parte de la instruccion
02 110C R1 = 0E Se guarda en R2 la direccion a la que buscar el dato
04 3208 Se almacena en la dir 08 la primer parte de la instruccion
06 3109 Se almacena en la dir 09 la segunda parte de la instruccion
08 8888 Es irrelevante, despues de ejecutadas las instrucciones va a contener y ejecutarse 130E, los valores que estaban en ella fueron reemplazados por nuestra instruccion deseada, y guarda el dato que tenemos en 0E en R3
0A C000 Fin
0C OE La direccion  es 0E
0E B5 el dato con el que quisimos trabajar desde el inicio es B5

<br>

paso a paso para guiarse

00 2213
02 110C
04 3208
06 3109
08 130E (Inicialmente FFFF)
0A C000
0C 0E
0E B5

R2 R1 M[0C] M[0E] M[08 y 09]  R3
13 0E  0E    B5     FFFF      B5
                    13FF
                    130E

<br>
Otro ejemplo

Sumar los elementos de un vector con los siguientes datos:
La direccion de comienzo de los datosse encuentra almacenada en 34
La longitud del vector se encuentra almacenada en 36
La sumatoria debe guardarse en 38
El programa se inicia en 12

Si tenemos un ejemplo con 3A y 4 de longitud, con los 4 datos siendo 1,2,3 y 4

12 1134 R1=M[34] = 3A la primer direccion
14 1035 R0=M[35] = 4 la longitud
16 2500 Inicializa 5 para
18 2400 Inicializo 4 como contador de iteraciones
1A 2301 Se pone R3 = 0 para incrementar
1C 2612 R6 = 12 primer byte de 123A (Auxiliar de carga para armar la instruccion)
1E 3622 Guardar en 22 la primer parte de la instruccion
20 3123 Guarda en 23 el primer elemento que se guardo antes en R1
22 8888 Dato de relleno, se va pisando con 123A, 123B, etc, guardando los elementos que voy obteniendo en R2
24 5443 Incremento del contador de iteraciones R4 = 1
26 5552 Acumulo el dato de R2 en R5 para la sumatoria
28 B430 Verifico la condicion de final, si ya termino de iterar
2A 5113 Incremento la direcciond e inicio del vector
2C 3134 Almaceno la nueva direccion de inicio en M[34] para la iteracion
2E B020 salto incondicional a 20 para el bucle
30 3539 Guarda la suma que se fue haciendo en R5 en M[38]
32 C000 Fin

<br>

Como definir si tengo en un lugar un 1 o un 0?

Basicamente, guardo la combinacion que busco en 00
Guardo la mascara con 0 en todos los valores que no me interesan y 1s en los que si
Traigo el valor
Hago un and con el valor y la mascaara
comparo con 00 y veo si son iguales

Para poner un 1 en un lugar
creo una mascara con puros 0s y un 1 donde quiero asegurar
Hago un OR con mi valor y la mascara

Para poner un 0 en un lugar
creo una mascara con puros 1s y un 0 donde quiero forzar un 0
Hago un AND entre ese valor y la mascara

Para restar 2 numeros
Hay que sacar el complemento del numero (Mascara de todos 1s y un XOR con el valor original, y se le suma 1)
Hacer la suma del numero original con el complemento a la base del primero con el segundo

Como detectar si un valor es negativo o no con signo

Con la mascara 80 que se guarda en el registro 0
Guardo el valor de memoria en el R1
Hago un AND de r1 y r0
Si el resultado a esto es igual entonces es negativo, si no es positivo