# Algebra de Bool y compuertas

## Logica digital

- La computadora necesitan almacenar datos e instrucciones en memoria
- Sistema binario: solo dos estados posibles.
- Porque?
 - Es mucho mas sencillo identificar entre solo dos estados
 - Es menos propenso a errores

No tiene porque ser 0 o 1, pueden ser valores representados por estos 2, por ejemplo, una potencia promedio de 10 o 15, siendo el 0 la representacion de 10 y el 1 del 15.

Esto permite trabajar con los intermedios con las distancias, si tengo 1 volt en 0 y 5 volt en 1, y tengo en un momento 4 volt, puedo marcarlo con un 1 y tender a 5 volt, siendo el unico caso donde el sistema no tiene seguridad del valor seria en el medio.
Se diferencia de los estados analogicos en que en estos, cada valor tiene su propio estado valido y verdadero, por lo que 4 volt es su propio estado. Esto lo hace un poco mas propenso a los errores.

## Diseño de circuitos
- Circuitos que operan con valores logicos:
 - Verdadero = 1
 - Falso = 0
- Idea: realizar diferentes opreaciones logicas y matematicas combinando circuitos.

### Algebra de Bool
- George Boole, desarrollo un sistema algebraico para formular proposiciones con símbolos.
- Su algebra consiste en un metodo para resolver problemas de logica que recurre solamente a valores binarios
 - verdadero y falso
 - on y off
 - 1 y 0
- simplemente utilizando 3 operadores
 - AND (y)
 - OR (o)
 - NOT (no)

En el AND, ambas afirmaciones deben ser verdaderas
En OR, con que una sea verdadera ya esta
En NOT, nos da el resultado contrario al que teniamos

### Operador AND
- es conocido como producto booleano y se escribe con "."
X   Y   X AND Y
0   0       0
0   1       0
1   0       0
1   1       1

### Operador AND
- es conocido como producto booleano y se escribe con "+"
X   Y   X OR Y
0   0      0
0   1      1
1   0      1
1   1      1

### Operador NOT
- se escribe con una barra sobre la variable
    _
X   X
0   1
1   0


## Funciones booleanas
- El orden de prioridades en estas operaciones es: NOT -> AND -> OR
- Si quiero resolver una funcion F(x,y,z) = x.z_+y, en lugar de hacerlas todas juntas, hago cada accion por separado en acciones entre 2 componentes, asi, podria tener en la tabla los 3 valores basicos, junto con
z_
luego x.z_
y finalmente x.z_+y, y asi puedo llegar a los valores correctos de manera mas segura

### Operador XOR
- Es similar al OR, pero debe ser exclusivo, osea, cada valor que recibe debe ser diferente, igual al OR pero sin incluir el 1 1

### Operadores NAND y NOR

...

<br>
Ejemplo

Y = ABC + B_
para facilitarlo agrego
ABC+B_(C+C_)(A+A_)
ABC+AB_C+AB_C+AB_C_+A_B_C_
Los 2 que son iguales se va uno por ser +
Asi, pasamos nuestro ejemplo de un caso raro a un caso canonico
ABC+AB_C+AB_C_+A_B_C_

Tambien podria hacerse distribuyendo
(A+B_)(B+B_)(C+B_)
se va el B+B_ porque da igual a 1 siempre
para que aparezca en cada caso la variable que me falta en ambos parentesis, agrego un 0
(A+B_+0)(C+B_+0) -> (A+B_+CC_)(C+B_+AA_)

- Buscamos que cada parentesis tenga al menos una vez cada variable porque se denomina minitermino y maxitermino son funciones anonicas que en cada uno de los terminos en producto o en suma estan todas las variables, y estoy ayuda a saber y completar la tabla mas correctamente

- La suma de miniterminos son la cantidad de terminos que te dan 1
- Con maxiterminos, sabes todas las funciones y todos los estados que te dan 0



