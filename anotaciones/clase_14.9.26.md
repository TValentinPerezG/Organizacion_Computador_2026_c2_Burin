# Unidad 2

## Maquina Elemental

- Introduccion
    - Concepto de datos / Informacion
    - Bit (Binary Digit / Biestable)
    - Byte
    - Proceso
    - Computadora
        - "Es una maquina que conta de elementos mecanicos, electronicos y electricos capaz de procesar gran cantidad de informacion a alta velocidad"

### Dato e Informacion

Un dato es un elemento que contiene algo, y una informacion es la relacion entre essot datos para crear un sistema con estos.
"20", "18", "dia", "hora", "parcial" son solo datos
"el 20 a las 18 hay parcial" es una informacion

### Bit

El tipo de dato mas basico, es biestable, ya que tiene 2 estados estables posible.
Si se lo saca de uno de estos estados estables, va a ir por si solo al otro estado estable.

### Byte

es un conjunto de 8 bits, lo que hace que pueda tener 2^8 valores diferentes, de 0 a 255, lo que me da mas estados, mas opciones, etc.

## Maquina elemental

- Clasificacion de computadoras segun su generacion
 - Generacion 0 - Computadoras mecanicas (1642-1945)
  - Pascal
   - Maquina mecanica de calculo (sumas y restas) (1642)
  - Babbage
   - Maquina de diferencias 
  - Aiken
   - 
 - Generacion 1 - Tubos de vacio (1945 - 1955)
  - Turing
   - COLOSSUS - Computadora Electronica
  - Mauchley / Eckert
   - ENIAC - Programable por switches
  - Von Neumann
   - IAS Machina - Programa almacenado
 - Generacion 2 - Transistores (1955 - 1965)
  - DEC
   - PDP 1 - Primer minicomputadora
   - PDP 8 - Primera mini masiva / Omnibus
  - IBM
   - 7094 - Dominio en uso cientifico
  - CDC
   - 6600 - Primer supercomputadora
  - Burroughs
   - B5000 - Primera diseñada para lenguaje de alto nivel
 - Generacion 3 - Circuitos Integrados
  - DEC
   - PDP 11 - Minicomputadora dominante
  - IBM
   - SYSTEM 360
 - Generacion 4 - Integracion a muy gran escala (1980-?)
  - IBM
   - PC - Comienzo era computadoras personales
  - APPLE
   - Apple Lisa
  - DEC
  - COMMODORE / ATARI
   - Computadoras hogareñas sin estandar
 - Generacion 5 - Computadoras "invisibles"
  - APPLE
   - Newton - Primera plamtop
  - Computadores embebidos
   - Relojes inteligentes
   - Celulares
   - Electrodomesticos
La generacion 1 se definio por los tubos de vacio y como estas permitian procesar una gran cantidad de informacion. Eran como lamparitas electricas para iluminar, haciendo que parte de la energia se volviera luz y calor
La siguiente tenia transistores, que ya no eran dispositivos que calentaran, y estos eran de estados solido, permitiendo el pasaje o no pasaje de energia electrica sin necesidad de abrir o cerrar un interruptor, teniendo el mismo la particularidad de dejar pasar o no la energia electrica
Para la siguiente, estos transistores con resistencias y demas elementos venian integrados todos juntos en un solo dispositivo, llamados circuitos integrados, lo que permitian computadoras mas eficientes y pequeñas.
La cuarta es cuando se extendieron las computadoras personales y los elementos 

### Aquitectura de Von Neumann

#### Esquema Funcional

     Memoria
 |  \t\t\t\t\ |
 Control \t\t Arithmetic 
 Unit \t\t\t Logic Unit
    >           <
 input \t\t\t Output

En este sistema tiene 2 memorias que se juntan, la memoria RAM y la ROM, ambas encargadas de una claase de informacion.
La ROM guarda instrucciones generales para el inicio de la computadora, es una memoria a la que no tengo acceso.
La RAM es la que se encarga de toda la informacion momentanea en la computadora, como programas, etc.

Si hablamos de dipositivos, de entrada seria un teclado, un mouse, un microfono, y de salida auriculares, monitor, y de entrada y salida por ejemplo un auricular con microfono

### Principios basicos de Von Neumann
- Programa almacenado
Tanto las instrucciones como los datos que en ellas se usan residen en una misma memoria
- Ruptura de secuencia
Debe existir una instruccion que permita a la maquinano seguir con la secuencia de ejecucion

### Maquina Brookshear
Ejemplo didactico de una maquina sin muchas de las complejidades pero con todas las caracteristicas que tiene cualquier procesador
- Conceptos Subyacentes
 - Compuertas: Dipositivos electronico que cumple una mision, por ej una compuerta AND
 - Registro (Register): Guardo la informacion con la particularidad de que por cada dispositivo adentro, sin importar como pase el tiempo, se va a mantener en el valor que se le dio.
 - Celda de memoria: Es una celda de memoria que debe tener 2 partes principales
  - Contenido: Que es lo que guarda esta direccion
  - Direccion: Te va a dar la direccion del lugar donde se guarda esa informacion
 - Bus: El viaje que tiene un bit para llegar a otra parte del sistema

Aca el profesor muestra un grafico, con el que vamos a trabajar unas cuantas clases

#### Caracteristicas
- 16 registros de proposito general de R0 a RF
- Registros de 1 byte
- Memoria principal consta de 256 bytes
- 1 Registro de instruccion de 16 bits, que nos dice que va a hacer la computadora, con cierta cantidad de bits para el CO y el OP
 - CO: Codigo de operacion, la cantidad de acciones que va a poder hacer nuestro sistema, si le damos 4 bits, podria hacer 16 acciones
 - OP: Operador, segun la accion en el codigo de operacion va a cambiar, por ejemplo, si estoy enviando un dato, el operador puede llevar la direccion donde voy a guardar el dato, desde donde, y dependiendo del caso, el dato.
 Si tenemos una suma, necesitamos 3, los dos valores que sumo, y el lugar donde se guarda su resultado.


Viendo el grafico, si tengo un sistema de 2 digitos hexadecimal (de 00 a FF) con un sistema de 8 bits, y tengo 4 instrucciones, algo que hara el sistema primero es pedir el elemento, si son mas de 8 bits, pedira mas espacios de la memoria, usando por ejemplo inicialmente 00 y 01

Con los buses voy de uno a otro

Mientras tengo los registros en la memoria y en la CPU van a tener velocidades distintas al tener estos capacidades distintas en el momento
<br>

Si tengo 1RXY con el binario
0001010111001111
Nos queda 15CF
El 1 representa una instruccion, en este caso buscar un numero en la memoria y cargarlo a cierta posicion
El CF es la memoria a la que va a ir a buscar ese numero que se requiere
El 5 representa la posicion a la que se va a cargar este numero.
Entonces, lo que esta diciendo ahi es que busque en la memoria el valor guardado en CF, y que ese valor lo lleve al espacio de posicion R5.

<br>

2RXY con el binario
0010010111001111 = 25CF
En este caso, la instruccion 2 nos dice que vaya al registro R, y que guarde en esa posicion el valor CF
En este caso, en el registro R5 se guarda el valor 11001111
<br>

### Ejercicio

Ahora 3RXY con el binario de valor 35CF
En este caso, la instruccion 3 envia lo que estaba guardado en el registro R, y lo guarda en la memoria, por lo que aca lo que habia en R5, y se guarda en el espacio de memoria CF
<br>
Sabiendo que la instruccion 5 suma el valor de lo tercero con el cuarto, lo guardarlo en el segundo espacio
<br>
Guardar lo que hay en AB y C6 y guardarlo en el espacio de memoria FF
Los primeros 2 numeros son las acciones, osea el CO
Por eso salta de 2 en 2, porque se hace un salto por cada 8 bits de instruccion, y cada instruccion tiene 16 bits
1A 11AB - 00011010 0001000110101011
(Paso lo de la memoria AB a R1)
1C 12C6 - 00011100 0001001011000110
(Paso lo de la memoria C6 a R2)
1E 5312 - 00011110 0101001100010010
(Sumo lo que tengo en R1 y R2 y lo guardo en R3)
20 33FF - 00100000 0011001111111111
(Paso lo que tengo en R3 y lo guardo en la memoria FF)
22 C000 - 00100010 1100000000000000
(Termino el programa)

Quedaria
1A 11
1B AB
1C 12
1D C6
1E 53
1F 12
20 33
21 FF
22 C0
23 00

<br>

Realizar la suma de 5 numeros que estar guardados en la direcciones de memoria 02, 02, 03, 05 y 06, guardar la misma en la direccion 10 y el programa comienza en la direccion 20

20 1102
22 1203
24 5112
26 1204
28 5112
2A 1205
2C 5112
2E 1206
30 5A12
32 3110
34 C000

<br> 

Intercarmar los valores de memoria de las celdas AA y BB, el programa comienza en la direccion 02.

02 11AA
04 12BB
06 31BB
08 32AA
0A C000

<br>

Se desea sumar los valores A5 y 2A y guardar la suma en la direccion 20, el programa comienza en 04

04 21A5
06 222A
08 5112
0A 3120
0C C000