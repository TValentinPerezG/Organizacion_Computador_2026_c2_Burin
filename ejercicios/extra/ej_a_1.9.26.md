a. Interpretar a los números como binarios enteros sin signo y obtener el resultado de las
operaciones Ra - Rb , Rc - Rd en binario mediante el procedimiento visto en clase. Indicar los
valores de los flags y justificar si el resultado está dentro del rango de representación.
Verificar que el resultado pasado a decimal se encuentra dentro del rango de representación
para 8 bits

# 1
Ra = 55, Rb = B4, Rc = 59, Rd = 4C

cada numero a binario

Ra = 01010101
Rb = 10110100
Rc = 01011001
Rd = 01001100

 01010101
-10110100

busco complemento a la base de Rb
11111111 - 10110100 + 1 = 01001011 + 1 = 01001100

01010101 
+ 
01001100 = 
10100001 resultado en presentacion

como se pasa, buscamos el complemento de 10100001
11111111 - 01010001 + 1 =  + 1 = 01011111
Resultado = -01011111
En hexadecimal = -5F

En decimal = 5x16 + Fx1 = 30 + 15 = -95 es correcto

es negativo N = 1
no es cero Z = 0
no tiene carry C = 0
tiene overflow V = 1 
tiene cantidad impar de 1s P = 1

Rc - Rd
 01011001
-01001100

busco complemento a la base de Rd
11111111 - 01001100 + 1 = 10110011 + 1 = 10110100

  01011001 
  + 
  10110100 = 
1|00001101

en hexadecimal = 0D

Nos da bien el resultado

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s impares P = 1

# 2
Ra = 5F, Rb = C5, Rc = 95, Rd = 8C

Ra = 01011111
Rb = 11000101
Rc = 10010101
Rd = 10001010

Ra - Rb

 01011111
-11000101

busco complemento de Rb
11111111 - 11000101 + 1 = 00111010 + 1 = 00111011

01011111
+
00111011 =
10011010 resultado en representacion

Busco complemento del resultado
11111111 - 10011010 + 1 = 01100101 + 1 = 01100110
-01100110 resultado final

en hexadecimal = -66

paso todo a decimal

5x16 + Fx1 = 95
Cx16 + 5x1 = 197
6x16 + 6x1 = 102
dan correctamente

Es negativo N = 1
No es cero Z = 0
No tiene carry C = 0
Tiene overflow V = 1
Tiene 1s pares P = 0

Rc - Rd

 10010101
-10001100

busco complemento de Rd
01110011 + 1 = 01110100

  10010101
  +
  01110100 =
1|00001001

resultado en hexadecimal = 09

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s pares P = 0

Vemos en decimal:
9x16 + 5 = 149
8x16 + C = 140
9 = 9

da bien

# 3
Ra = 55, Rb = BB, Rc = F6, Rd = 5F

Ra = 01010101
Rb = 10111011
Rc = 11110110
Rd = 01011111

Ra - Rb

 01010101
-10111011

busco CBRb -> 01000100 + 1 = 01000101

01010101 +
01000101 =
10011010 resultado en representacion

busco complemento del resultado
01100101 + 1 = 01100110
-01100110 = -66

en decimal:
5x16 + 5 = 80 + 5 = 85
Bx16 + B = 176 + 11 = 187
6x16 + 6 = 102
da bien

Es negativo N = 1
No es cero Z = 0
No tiene carry C = 0
Tiene overflow V = 1
Tiene 1s pares P = 0

Rc - Rd

11110110 - 01011111

buscamos CBRd -> 10100000 + 1 = 10100001

  11110110 +
  10100001 =
1|10010111 = 97

en decimal:
Fx16 + 6 = 240 + 6 = 246
5x16 + F = 80 + 15 = 95
9x16 + 7 = 144 + 7 = 151
da bien

Es negativo N = 1
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s impares P = 1


# 4
Ra = A8, Rb = 72, Rc = 8A, Rd = A2

Ra = 10101000
Rb = 01110010
Rc = 10001010
Rd = 10100010

Ra - Rb

10101000 - 01110010

busco CBRb -> 10001101 + 1 = 10001110

  10101000 +
  10001110 =
1|00110110 = 36

en decimal:
Ax16 + 8 = 160 + 8 = 168
7x16 + 2 = 112 + 2 = 114
3x16 + 6 = 48 + 6 = 54
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
Tiene overflow V = 1
Tiene 1s pares P = 0

Rc - Rd

10001010 - 10100010

busco CBRd -> 01011101 + 1 = 01011110

10001010 +
01011110 =
11101000
busco complemento del resultado
00010111 + 1 = 00011000
-00011000 = -18

en decimal:
8x16 + A = 128 + 10 = 138
Ax16 + 2 = 160 + 2 = 162
1x16 + 8 = 16 + 8 = 24
Da bien

Es negativo N = 1
No es cero Z = 0
No tiene carry C = 0
No tiene overflow V = 0
Tiene 1s pares P = 0


# 5
Ra = A7, Rb = 83, Rc = B5, Rd = 77

Ra = 10100111
Rb = 10000011
Rc = 10110101
Rd = 01110111

Ra - Rb
A7 - 83
10100111 - 10000011

busco CBRb -> 01111100 + 1 = 01111101

  10100111 +
  01111101 =
1|00100100 = 24

en decimal:
Ax16 + 7 = 160 + 7 = 167
8x16 + 3 = 128 + 3 = 131
2x16 + 4 = 32 + 4 = 36
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s pares P = 0

Rc - Rd
B5 - 77
10110101 - 01110111

busco CBRd -> 10001000 + 1 = 10001001

  10110101 +
  10001001 =
1|00111110 = 3D

en decimal:
Bx16 + 5 = 176 + 5 = 181
7x16 + 7 = 112 + 7 = 119
3x16 + D = 48 + 14 = 62
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
Tiene overflow V = 1
Tiene 1s impares P = 1

# 6
Ra = B7, Rb = 83, Rc = A5, Rd = 37

Ra = 10110111
Rb = 10000011
Rc = 10100101
Rd = 00110111

Ra - Rb
B7 - 83
10110111 - 10000011

busco CBRb -> 01111100 + 1 = 01111101

  10110111 +
  01111101 =
1|00110100 = 34

en decimal:
Bx16 + 7 = 176 + 7 = 183
8x16 + 3 = 128 + 3 = 131
3x16 + 4 = 48 + 4 = 52
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s impares P = 1

Rc - Rd
A5 - 37
10100101 - 00110111

busco CBRd -> 11001000 + 1 = 11001001

  10100101 +
  11001001 =
1|01101110 = 6D

en decimal:
Ax16 + 5 = 160 + 5 = 165
3x16 + 7 = 48 + 7 = 55
6x16 + D = 96 + 14 = 110
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
Tiene overflow V = 1
Tiene 1s impares P = 1

# 7
Ra = A4, Rb = 52, Rc = 8A, Rd = B4

Ra = 10100100
Rb = 01010010
Rc = 10001010
Rd = 10110100

Ra - Rb
A4 - 52
10100100 - 01010010

busco CBRb -> 10101101 + 1 = 10101110

  10100100 +
  10101110 =
1|01010010 = 52

en decimal:
Ax16 + 4 = 160 + 4 = 164
5x16 + 2 = 80 + 2 = 82
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
Tiene overflow V = 1
Tiene 1s impares P = 1

Rc - Rd
8A - B4
10001010 - 10110100

busco CBRd -> 01001011 + 1 = 01001100

10001010 +
01001100 =
11010110 valor en representacion
busco complemento de resultado = 00101001 + 1 = 00101010
-00101010 = -2A

en decimal:
8x16 + A = 128 + 10 = 138
Bx16 + 4 = 176 + 4 = 180
2x16 + A = 32 + 10 = 42
Da bien

Es negativo N = 1
No es cero Z = 0
No tiene carry C = 0
No tiene overflow V = 0
Tiene 1s impares P = 1


# 8
Ra = A2, Rb = 73, Rc = B5, Rd = A7

Ra = 10100010
Rb = 01110011
Rc = 10110101
Rd = 10100111

Ra - Rb
A2 - 73
10100010 - 01110011

busco CBRb -> 10001100 + 1 = 10001101

  10100010 +
  10001101 =
1|00101111 = 2F

en decimal:
Ax16 + 2 = 160 + 2 = 162
7x16 + 3 = 112 + 3 = 115
2x16 + F = 32 + 15 = 47
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
Tiene overflow V = 1
Tiene 1s impares P = 1

Rc - Rd
B5 - A7
10110101 - 10100111

busco CBRd -> 01011000 + 1 = 01011001

  10110101 +
  01011001 =
1|00001110 = 0D

en decimal:
Bx16 + 5 = 176 + 5 = 181
Ax16 + 7 = 160 + 7 = 167
0x16 + D = 14
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s impares P = 1

# 9
Ra = CD, Rb = 4A, Rc = 96, Rd = 5C

Ra = 11001101
Rb = 01001010
Rc = 10010110
Rd = 01011100

Ra - Rb
CD - 4A
11001101 - 01001010

busco CBRb -> 10110101 + 1 = 10110110

  11001101 +
  10110110 =
1|10000011 = 83

en decimal:
Cx16 + D = 192 + 13 = 205
4x16 + A = 64 + 10 = 74
8x16 + 3 = 128 + 3 = 131
Da bien

Es negativo N = 1
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s impares P = 1

Rc - Rd
96 - 5C
10010110 - 01011100

busco CBRd -> 10100011 + 1 = 10100100

  10010110 +
  10100100 =
1|00111010 = 3A

en decimal:
9x16 + 6 = 144 + 6 = 150
5x16 + C = 80 + 12 = 92
3x16 + A = 48 + 10 = 58
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
Tiene overflow V = 1
Tiene 1s pares P = 0

# 10
Ra = AB, Rb = AD, Rc = E5, Rd = 9A

Ra = 10101011
Rb = 10101101
Rc = 11100101
Rd = 10011010

Ra - Rb
AB - AD
10101011 - 10101101

busco CBRb -> 01010010 + 1 = 01010011

  10101011 +
  01010011 =
1|11111110 resultado en respresentacion
busco complemento -> 00000001 + 1 = 00000010
-00000010 = -2

en decimal:
Ax16 + B = 160 + 11 = 171
Ax16 + D = 160 + 13 = 173
0x16 + 2 = 2
Da bien

Es negativo N = 1
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s impares P = 1

Rc - Rd
E5 - 9A
11100101 - 10011010

busco CBRd -> 01100101 + 1 = 01100110

  11100101 +
  01100110 =
1|01001011 = 4B

en decimal:
Ex16 + 5 = 224 + 5 = 229
9x16 + A = 144 + 10 = 154
4x16 + B = 64 + 11 = 75
Da bien

No es negativo N = 0
No es cero Z = 0
Tiene carry C = 1
No tiene overflow V = 0
Tiene 1s pares P = 0