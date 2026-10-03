### Convenciones para interactuar con el computador

El computador siempre trabajara con 0 y 1, que definen apagados y prendidos.  
Tenemos que crear una convencion con una compatudora para ver como se definen estos apagados y encendidos.  
<br>
directo del profesor:
Supongamos que tenemos el numero
101110
0101
11101
011111
Todos estos numeros pueden significar un monton de cosas.
Para saber a que numero corresponde debo saber la y estar seguro de su base, ya que esto cambia completamente el valor de este.
La maquina no tiene 28 bases, va a tener estos numeros, que en principio son numeros en binario, con un agregado.  
El agregado es que el numero contiene el signo.
Para esto me tienen que decir que el numero esta en REPRESENTACION 
Convencion que se usa en la mayoria de casos: Si tengo un numero y quiero que ese numero sea positivo, el primer digito va a ser un 0, si es positivo, el primer digito va a ser un 1.
Ahora con esto, sabiendo la base y el primer digito, y sabiendo que esta en REPRESENTACION, sabemos que el 101110 es negativo y 011111 es positivo.
Ahora, si tenemos esa misma base para los numeros del medio asi nomas, entonces suponemos que estan en positivo porque no vemos el signo.
Solo por verlos no podemos identificar si estan o no en REPRESENTACION, se nos tiene que identificar.

Entonces, si tengo un numero normal, por ej, el +13 en base 10, y me lo piden en REPRESENTACION, primero tengo que pasar el numero a binario
13/2 = 6 resto 1, 6/2 3 resto 0, 3/2 1 resto 1 = 1101  
y para que sea positivo en REPRESENTACION le agrego un bit de valor 0 al inicio.
Quedando 01101.
Ahoraa, si tengo 13 en negativo, tenemos que extender el proceso
Primero, hacemos el mismo proceso inicial, se pasa el 13 a binario y se le agrega un bit con un 0 delante.
Luego, se hace el completo a la base de ese valor + 1, dando en este caso 10010 + 1, por lo que -13 = 10011
<br>
EJ: -3AD base 16
1- Paso a base 2, me queda 001110101101
2- Agrego un bit de 1 para hacerlo positivo, como aca ya tengo 0 a la izquierda no hay problema, queda 01110101101
3- Hacemos CB + 1, queda 10001010010 + 1 

-3AD = 10001010011
<br>
Si quiero pasar de REPRESENTACION al numero en base 10

Supongamos que tenemos este valor: 10110
Lo que tenemos que hacer es simplemente encontrar el complemento a la base + 1
01001 + 1 = 01010
y si pasamos este valor a base 10, llegamos a que 
10110 = -10

Otro ejemplo rapido, si tengo 1110
complemento: 0001 + 1 = 0010
1110 = -2
Otro: 010010
no necesito complemento, solo pasarlo 
<br>
Si volvemos al primer ejemplo, quiero representar -32 en base 4, sigo los pasos.

como son exponentes, puedo extender el numero a
-1110
para representarlo, agregamos un 0 de los positivos
01110
y finalmente, hacemos el complemento
10001+1=10010=-32 base 4
<br>

Supongamos que tenemos 110, en binario es +6, en representacion es -2

si hacemos la suma, 110 + 110 = 1100 en ambos casos, siendo el primer digito llamado Carry es 1.
Si no contamos el carry, vamos a recibir un valor llamado overflow, que nos dice si con esos digitos se puede hacer un valor, y si la cantidad de digitos es igual a la original, nos dara un overflow de 0.

Nos puede pasar lo siguiente, si tenemos 101, que en binario es 5 y en representacion es -3
En este caso, al hacer 101 + 101 = 1010, con un carry de 1, pero el tema ahora es que 101 + 101 en representacion = 010 que es un numero positivo, lo que nos dice que no alcanzan los numeros para representar el valor al que llegamos, creando un overflow de 1.

En el caso de tener 010 + 010 que es 2 en ambos casos, el carry en este caso es 0, pero en 3 digitos no se puede REPRESENTAR el numero 4, porque si hacemos 010 + 010 = 100, lo que es negativo, por lo que aca el overflow existe.
Tiene sentido, ya que con 3 digitos podemos hacer solo del 0 al 3 positivo, con 000, 001, 010 y 011, por lo que se va a ir de largo.
<br>

010 + 110 = 1|000, como estamos en 3 bits el 1 queda como carry

Entonces, en entero SIN signo, si hay carry, entonces se fue de rango. 
Y en entero CON signo, si hay carry puede o no estar fuera de rango, depende del overflow. Si además de carry hay overflow entonces se fue rango, no hay overflow está dentro del rango.

2# Rc - Rd
Entonces en este ejercicio si lo tomamos sin signo se fue de rango, y si lo tomamos con signo no esta fuera de rango porque no da overflow?