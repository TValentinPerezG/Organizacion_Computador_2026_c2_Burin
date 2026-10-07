## Clase de repaso

### Registros en maquina de brookshear
De proposito general, los 16 del R0 al RF para proposito general que usamos.
Y luego estan los registros dedicados, registro de instrudccion donde se guarda la instruccion por ejecutar.
El registro de memoria, que agarra y muestra la direccion de memoria con la que trabajara la operacion.
Y el registro de dato de la memoria, que guarda el dato con el que trabajara la operacion
Estos 2 solo cuando interactua con la memoria.

Si tiene que cargar un registro desde una direccion de memoria o cargar un

Y tambien el PC, donde aparece la direccion de la proxima instruccion a ejecutarse.

### Bit de overflow y de carry

Cuando sumamos en decimal 15 + 16, cuando los sumo junto ambos y me llevo el 1, ese 1 que me llevo es el bit de carry, que, como no hay mas bits en el registro, no tengo donde ponerlo, y por lo tanto se enciende el bit de carry.
Overflow es cuando, con tantos bits, se pueden representar tantos numeros, si la operacion lleva a un valor que no esta en el rango voy a tener un overflow. Esto lo veo cuando los 2 bits d elos operando tienen un mismo signo pero distinto signo en el resultado.

### Cambiar de valor un elemento

Si quiero 1 en un lugar, OR con mascara de 0s y 1 en la posicion deseada
Si quiero 1 en un lugar, AND con mascara de 0s y 1 en la posicion deseada
Si quiero complemento a la base, XOR con mascara de todos 1s


### Flags

son z, n, c, p, w
Z tiene 1 cuando es igual a 0
N tiene 1 cuando es negativo (1 en el bit mas significativo)
P tiene 1 si hay una cantidad impar de 1s
C queda 1 si hay carry
V queda 1 si hay overflow


### Numero dado con menos bits de los necesarios

Si estamos en 8 bits y nos dan un numero, y este es de 5 bits, lo completare dependiendo de su signo, si es muy grande, 


### Cosas que hace el procesador desde que se encience hasta que se apaga

- BUSCAR
- DECODIFICAR
- EJECUTAR

El programa se guarda en la memoria, y el sistema se encarga de analizarlo para ver que se le esta pidiendo hacerlo
La unidad de control se encarga tambien de enviar el comando, ya que es la encargada de coordinar todo el proceso
La unidad de control se encarga de decodificar (UC)
De ejecutar estos procesos se encarga la unidad aritmetico logica (UAL)
Ademas del resultado, de la UAL salen tambien los flags que anote antes.
El OC|Operandos es parte del RI, el registro de instruccion, el OC es el codigo de operacion y que lleva la operacion, y los operandos son los encargados de definir a donde iban

### Ejercicio de Zoneado

CAFE es positivo, BD negativo
Como es el 12345 zoneado
1 zoneado es F1
El sistema entero F1F2F3F4F5A
-654
F6F5F4B
Pasar F5 F0 F2 F7 D a decimal
-5027


### Caso especifico producto flotante

1,1111 ^ (-5) = 0,00011111
1,1111 ^ (+5) = 111110

En el caso de esto, si la potencia es negativa, la coma va para la derecha, y si es positiva, la coma va para la izquierda

NO OLVIDARSE DEL 1 IMPLICITO

Para IEEE punto flotante de simple precision (32 bits)
Si voy de decimal al punto flotante le sumo 127 a la potencia
Si voy de punto flotante a decimal le resto 127 a la potencia
Se tiene 1 bit de signo
Se tiene 8 bits de exponente
Se tiene 23 bits de mantisa
Para el doble precision (64 bits)
1
11
52
el exceso es 1026

### Empaquetado

El empaquetado era BCD (Binario codificado como decimal)
Es en hexadecimal usar solo los digitos del 0 al 9 para representar un numero decimal y el A al F para el signo
Si quieropasar +123456
X'01 23 45 6C'
Luego, si me piden configuracion, es agarrar este nuevo numero que me dieron, y pasarlo a la configuracion pedida

### Direccionamiento directo e indirecto

Aparece solamente como teorico
Directo es aquel donde se obtiene el dato directamente del espacio de memoria que llamamos
Indirecto seria aquel donde en el espacio de memoria se tiene el registro del espacio de memoria donde esta el dato, por lo que tengo que tener un espacio generico para poder enviar la instruccion y el espacio de memoria nuevo

### Restar en maquina elemental

Se obtenia el complemento a la base y luego se suma

### Circuito combinacional y secuencial

El circuito combinacional la salida depende solamente de la entrada
En el secunencial depende de la entrada, pero tambien de la historia previa, teniendo una memoria de los valores previos. Va a tener un retardo tambien, al tener que pasar por los circuitos

"El combinacional tiene una salida que depende unicamente de los valores actuales de las entradas mientras que el secuencial tiene salidas que dependen tanto de las entradas actuales como del estado interno que guarda."

### Ejercicio 15 de la guia

En el ejercicio 15 de la guia, el primero es combinacional, y el segundo es un registro, que lo que hay en la salida despues del pulso de reloj es lo que hay en la entrada, y hasta que no venga un nuevo pulso de reloj, este no cambia, osea, si se pone un 5, se va a mantener un 5 hasta el nuevo pulso de reloj que quiera pisarlo con un nuevo registro.
Depende de las entradas y del clock, como no hay una retroalimentacion, es si o si combinacional.

### Tips para codigo de maquina de brookshear

- No escribir las direcciones al costado de cada instruccion hasta tener todas escritas
- Entre instruccion e instruccion dejar un reglon para poder arreglar errores
- Hacer comentarios lo mas posible para que se entienda 
- Pensar el ejercicio antes de mandarse a escribir


### Bases

Pasar un numero en base 7 a base 8
Paso primero a base 10 (decimal) en el medio
Si es un numero como 27, no pisar el palito, 27 no es representable en base 7, tienen que ser numeros menores.

### Ej 54 guia maquina elemental

BPF hace referencia a Binario de Punto Fijo

### Representacion de un numero en signos

si tengo n bits, puedo representar de [+2^(n-1) - 1 , -2^(n-1)], por ej en 8 bits tenemos de [127, -128]

### Complemento a la base de una resta

Si tengo A - B o A + B o - A + B o - A - B

Si son ambos suma, no necesito hacerle el complemento a la base
solo tengo que hacerle complemento a la base a los que estan negativos

Si tengo un caso donde tengo A - B y B es mas grande que A

Con signo, si se fue de rango, usualmente nos dara un overflow

### Para pasar a decimal con signo

Si tengo con signo y es negativo, obtengo el complemento a la base, y si es positivo, lo mantengo como esta, y luego uso el valor que tengo para pasarlo a decimal

### Analizar flags para rango de representacion

Como tenia que analizar los flags para saber si el resultado se fue de rango de representación? 
En sin signo, si había bit de carry, se fue de rango (sin importar el bit de overflow)
Con signo, si había bit de carry, no indicaba nada, pero si hay bit de overflow, se fue de rango.