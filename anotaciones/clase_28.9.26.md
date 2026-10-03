### Ejercicio

Se desea complementar los cuatro bits intermedios de un byte dejando los otros cuatro bits intactos. ¿Que mascara y que operacion debe usar? resolver el programa. El dato esta en la direccion AA
    10 1011 01
XOR 00 1111 00
    10 0100 01

20 11AA //paso lo que hay en la direccion AA a R1
22 223C //como tengo que cambiar los del medio, necesito una mascara para XOR que usar con el original, y como cambio los intermedios, la mascara es 00111100, que es 3C, guardo esto en R2
24 9312 //Hago XOR con la mascara entre R1 y R2
26 33AB //Pegamos el resultado a AB
28 C000

Nos da una pagina para emular estos, se tienen que cambiar los primeros tales bits por los que quiero revisar:
""

<br>
El puerto de un dispositivo de E/S está en la dirección CA.
Si los bits 1 y 3 recibidos son "0", debe enviar un "1" por el bit 7.
Si los bits 1 y 3 recibidos son "1", debe enviar un "0" por el bit 6.
En los demás casos debe enviar un "0" por el bit 5 y un "1" por el bit 4.
En ningún caso debe modificar los bits restantes al escribir en ese puerto.



20 11CA //Paso el dato a R1
22 200A //Pongo la mascara en R0
24 8210 //Hago AND con la mascara y el valor y lo guardo en R2
26 B238 //Si es igual a la mascara, salta hasta donde ejecuto este
28 2000 //Guardo el nulo en el 2, para ver si ambos bits son 0
2A B240 //Salto hasta donde ejecuto este caso
2C 23DF //Si no se cumplio ninguna, pongo la masc para poner un 0 en el bit 5 en R2
2E 8413 //Hago AND entre el valor y la mascara y guardo en R4
30 2310 //Pongo en R2 la mascara para el 1 en el bit 4
32 7543 //R5 = R4 or R3 para la otra modificacion
34 35CA //Guardo el dato con las 2 modificaciones en CA 
36 B046 //Salto al final
38 23BF //Guardo la mascara para hacer al bit 6 un 0 en R3
3A 8413 //R4 = R1 AND R3 para hacer el bit 6 un 0
3C 34CA //Guardo el dato con el bit modificado en CA
3E B046 //Salto al final
40 2380 //Caso de ambos 1, guardo la mascara para hacer el bit 7 un 1 R3
42 7413 //R4 = R1 OR R3 para hacer el bit 7 un 1
44 34CA //Guardo el dato con el bit modificado en CA
46 C000 //Termino
11CA200A8210B2382000B24023DF84132310754335CAB04623BF841334ACB0462380741334ACC000

https://joeledstrom.github.io/brookshear-emu/#11CA200A8210B2382000B24023DF84132310754335CAB04623BF841334CAB0462380741334CAC0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000080


<br>

## Desplazamiento

Con A

42. Un desplazamiento circular hacia la derecha de tres bits en una cadena de ocho bits es equivalente a un desplazamiento circular a la izquierda de cuantos bits?
10101010 --> derecha 3 bits --> 01010101
10101010 --> izquierda 5 bits --> 01010101

<br>

## Combinacionales

Tenemos 4 entradas A, B, C y D y la salida F, obtener el valor de la salida F cuando la entrada es multiplo de 3 la salida da 1 y cuando no es 0 obtener la salida F(A,B,C,D) simplificando si es posible

A B C D F 
0 0 0 0 1  noAnoBnoCnoD
0 0 0 1 0
0 0 1 0 0
0 0 1 1 1  noAnoBCD
0 1 0 0 0
0 1 0 1 0
0 1 1 0 1  noABCnoD
0 1 1 1 0  
1 0 0 0 0
1 0 0 1 1  AnoBnoCD
1 0 1 0 0
1 0 1 1 0
1 1 0 0 1  ABnoCnoD
1 1 0 1 0 
1 1 1 0 0
1 1 1 1 1  ABCD

F(A,B,C,D) = 
noAnoBnoCnoD + noAnoBCD + noABCnoD + AnoBnoCD + ABnoCnoD + ABCD = 
noAnoB(noCnoD+CD) + noABCnoD + AnoBnoCD + AB(noCnoD+CD) =
noAnoB(0) + noABCnoD + AnoBnoCD + AB(0) =


###

Combinacional depende solamente de las entradas, y la secuencial depende de las salidas y si vuelven a entrar, pudiendo modificar los valores de la entrada y generando un valor final distinto

##

RI: Registro de Instrucción (la que se está a punto de ejecutar)
PC: Program Counter (la dirección de la próxima instrucción a ejecutarse)
RD: Registro de Dirección (guarda la dirección a la cual interesa acceder I/O)
RDM: Registro de Dato de Memoria (contiene el dato de interés para la operación de I/O)