15. Indicar los números máximos y mínimos, positivos y negativos, que pueden
ser almacenados en el formato flotante IEEE 754 de precisión simple. 

Para maximo y minimo se va a necesitar el mismo numero cambiando el digito mas siginificativo (izquierda) entre 1 y 0 dependiendo del signo.
Quiero el exponente mas grande disponible sin irme al caso del infinito, por lo que el exponente debe ser
11111110
Y finalmente, quiero la mantisa mas grande posible para multiplicar el exponente, lo que deja
0 11111110 11111111111111111111111
siendo el maximo, y
1 11111110 11111111111111111111111
el minimo
