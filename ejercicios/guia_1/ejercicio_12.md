Dados los siguientes números, almacenarlos en binario de punto flotante
IEEE 754 de precisión simple e indicar cuál es su configuración binaria y
hexadecimal.
a. 0,100111]2 b. 0,0311]10 c. 93,F1]16

a.
1) Ya esta en binario
2) Movemos el 1 para que quede uno frente a la coma
0,100111 x 2^(-1)
1,00111
3) Juntamos el exponente con 127 y pasamos a binario
127 - 1
126 = 01111110
4) Signo es positivo = 0
5) Mantisa es lo que queda atras de la coma = 00111
El resultado es
0 01111110 00111000000000000000000

b.
1) Paso a binario
0,0311 x 2 = 0,0611
0,0611 x 2 = 0,1222
0,1222 x 2 = 0,2444
0,2444 x 2 = 0,4888
0,4888 x 2 = 0,9776
0,9776 x 2 = 1,9552
0,9552 x 2 = 1,9104
0,9104 x 2 = 1,8208
0,8208 x 2 = 1,6416
0,6416 x 2 = 1,2832
0,0311 base 10 =aprox 0,0000011111
2) Movemos el uno para que quede al frente
1,1111 x 2^(-6) = 1,11110,0000011111
3) Juntamos el exponente con 127 y pasamos a binario
127 - 6 = 121 = 01111001
4) Como es positivo va 0 adelante
5) Mantisa en lo que queda tras la coma = 1111
0 01111001 111100000000000000000000

c. 93,F1
1) Paso a binario
10010011,11110001
2) Movemos el 1
1,001001111110001 x 2^(7)