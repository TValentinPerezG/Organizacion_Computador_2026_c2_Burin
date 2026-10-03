17. Expresar en base 2, los máximos y mínimos números almacenables en 32
bits de un binario de punto flotante cuyo formato es distinto al conocido ya
que los primeros 26 bits representan la mantisa, los 5 restantes el
exponente en exceso y el último bit el signo.

 0 25 30 31
 |-------------------------------------------------------|-------------------------|----|
 (mantisa) (característica) (signo)
Nota: La mantisa debe estar normalizada en binario. Tener en cuenta el “1” implícito al igual
que el formato IEEE 754 tradicional

- Es para entender el metodo. Al cambiar la cantidad de bits que van al exponente, cambia tambien el exceso a 15 (16 que es el ultimo represetable - 1)