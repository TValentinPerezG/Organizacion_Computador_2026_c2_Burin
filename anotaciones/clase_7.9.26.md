## Formato y configuracion

Formato es el formato en el que se presentan una serie de valores, por ejemplo empaquetado, y configuracion es el valor con el que estoy trabajando

### Fomato empaquetado
Un numero decimal escribo en BCD donde cada numero esta escrito en un nible y su digito mas significativo (mas a la derecha) representa su signo (A,B,C,D,E,F)
Donde B,D son negativos y los otros positivos
Sirve para que la computadora nos muestren resultados en decimal

Permite que en lugar de usar un byte entero, cada numero se represente en 4 bits, haciendo un nible
BCD (decimal coficiado en binario) el 9 es el numero mas grande que hay, 

# Tema nuevo

Para expresar numeros de gran tamaño, en lugar de usar una gran cantidad de bits para numeros muy pequeños o muy grandes, usamos los ultimos 2 numeros como potencias de 10, y asi, en lugar de limitarnos en 

9999, podemos llegar a 99x10^99

# Punto flotante (IEEE754)

435
 43,5 x 10^1
 0,0435 x 10^(4)
 435000 x 10^(-3)
 
 -5,67 x 10^3
 -5670 x 10^0
 
 IEEE754
 Punto flotante 
 Simple Precisión --> 32 bits
 Doble Precisión --> 64 bits
 
PUNTO FLOTANTE SIMPLE PRECISIÓN
3 campos: signo, exponente y mantisa
longitud:  1         8         23


CONVERTIR EL NÚMERO DECIMAL 46 A PUNTO FLOTANTE SIMPLE PRECISIÓN

1. Representar el número 46 en binario
543210 <--PESOS
101110 en base 2 = 46 en base 10
1011,10 x 2^(2) 
1,01110 x 2^(5)
101110000 x 2^(-3)

De todas las formas de escribir el mismo numero nos quedamos con 
la que tiene un 1 como parte entera.

2. Escribirlo con 1 como parte entera

1,01110 x 2^(5)
Este 1 de la parte entera se llama bit implícito y no se representa.

3. SIGNO 
Positivo --> escribimos 0
Negativo --> ecribimos 1

Signo = 0

4. EXPONENTE
Lo representamos en código Exceso 127.
Le sumamos 127.
5 + 127 = 132 En el exponente va 132 en binario
132 = 10000000 + 100 = 10000100
Exponente = 10000100 (8 bits)

5. MANTISA
Es todo lo que está a la derecha de la coma.
Mantisa= 01110 (23 bits)


6. Representación IEEE754
0 10000100 0110000000...
0100001000110000000...

   
CONVERTIR A PUNTO FLOTANTE EL NÚMERO DECIMAL 47,96
1. convertir el decimal a binario
543210  <-- pesos
     1  1
    10  2
   100 	4 
  1000	8
 10000  16
100000  32

47 = 32 + 8 + 4 +2 + 1 = 101111  

0,96 x 2 =  1,92
0,92 x 2 =  1,84 
.......

47,96 = 10111,1111010111

2. Correr la coma

1,01111111010111 x 2^(4)


3. signo = 0

4. Exponente = 4
Exceso 127 + 4 --> 131
       128 + 3 --> 10000000 + 11 = 10000011

5. Mantisa
01111111010111

6. Representación
0 10000011 01111111010111

01000001101111111010111


Para doble precisión (64-bits)
signo: 1 bit
exponente: 11 bits
mantisa: 52 bits