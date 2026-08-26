# Organizacion_Computador_2026_c2_Burin
Repositorio para anotaciones de la clase de Organizacion del Computador del segundo semestre de 2026 de FIUBA



Hoy voy a anotar aca para no sobrecargar mas la pc

despues lo paso al visual

Para la resta hacemos parecidos a la suma, me acerco a la base como en la suma
asi, si tengo esto
100000000
 57289456

 nos conviene hacer
 99999999 menos
 57289456 mas
        1

Queremos buscar los complementos de la base 
asi, si tengo 3, el complemento es 7
10 - 3 = 7
se cumple al reves
y podemos implementarlo a numeros mas grandes combinando ambas cosas
asi, si buscamos el resultado del complemento haciendo el anterior + 1 de la base
si buscamos el complemento de 324
1000 menos
 324
para que sea mas sencillo, hacemos el complemento a la base - 1 y luego sumamos para llegar a la base
999 - 324 = 675 + 1 = 676 es el complemento a la base


Asi, podemos hacer cada resta como sumas, usando una formula para su solucion que es algo tipo
A + (complemento de base - B) = c + r^n

Supongamos que tenemos 357 (a) - 295 (b) 
sacamos el complemento a la base de B
1000 - 295 = 999 - 295 + 1 = 704 + 1 = 705 = complemento a la base de B

Usamos la formulapara sacar 1062, y podemos aplicar la formula para sacar este complemento con r^n que saca la con las cifras:
A + Complemento de B = C + r^n = 1026 - 1000 = C > C = 26

Hagamos con otro, esta vez en base 16

7AC - 3D8
Buscamos complemento a la base
1000 - 3D8 = FFF - 3D8 + 1 = C27 + 1 = C28
Hacemos la suma de A + CbB
7AC + C28 = 13D4 = A + CbB
Usamos el r^n en C + r^n, y nos queda
C = 13D4 - 1000 > 3D4 = C

ejercicios de la guia ej 6

a. 1101 - 10 base 2
buscamos CbB del B
10000 - 10 = 1111 - 10 + 1 = 1101 + 1 = 1110
1101 + 1110 = C + r^n = 11011 - r^n = C > 11011 - 10000 = C > 1011 = C

b. 5423 - 1111 base 8
busco CbB del B
10000 - 1111 = 7777 - 1111 + 1 = 6666 + 1 = 6667
5423 + 6667 = 14312 = C + r^n = 14312 - 10000 = C > C = 4312

c. DDE - F1F base 16
busco CbB
1000 - F1F = FFF - F1F + 1 = 0E0 + 1 = E1
DDE + E1 = EBF - 1000, como nos pasamos, hacemos el complemento devuelta pero de EBF que es igual a -C
1000 - EBF = FFF - EBF + 1 = 140 + 1 = 141
C = -141

d. 1011 - 1111 base 2
busco CbB
10000 - 1111 = 1111 - 1111 + 1 = 0 + 1 = 1
1011 + 1 = C + r^n > 1100 - 10000, como nos pasamos, buscamos el complemento pero de 1100 que es -C
10000 - 1100 = 1111 - 1100 + 1 = 100
C = -100

e. A213 - 2F1B base 16
busco CbB del B
10000 - 2F1B = FFFF - 2F1B + 1 = D0E4 + 1 = D0E5
A213 + D0E5 = C + r^n > 172F8 - f^n = C > C = 72F8

f. 1111 - 1011 base 2

g. debe dar -440

h. debe dar -2A1F

i. 10011101 - 11001110 base 2
CbB
100000000 - 11001110 = 11111111 - 11001110 + 1 = 110001 + 1 = 110010
10011101 - 110010 = 11001111 - 100000000 como nos pasamos, buscamos complemento de 11001111 que es -C
100000000 - 11001111 = 11111111 - 11001111 + 1 = 00110000 + 1 = 110001
C = -110001

ejercicios de la guia ej 7

a. 6 + 7 = 11
sabemos que en base 10 esto seria 13, y tambien sabemos que 10 es la base y 01 es el primero luego de esto, por lo que buscamos un numero con base 13 - 1. Entonces, este debe estar en base 12
