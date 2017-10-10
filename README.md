## VALID CARD
#### Contenido:
1. Diagrama de flujo validCard.
2. Pseudocódigo validCard.
3. Ejecución del código en JS.
4. Explicación del código.

- - - - - - -  --- - - - - - - - -- -

### 1. DIAGRAMA DE FLUJO

[diagramaflujo](https://ibb.co/dy78qb)

### 2. PSEUDOCÓDIGO

    inicioProceso
      escribir cardNumber

      función isValidCard <--- (cardNumber)

       // crear variables
       var arrayNumbers, arrayInverse, sum

       //almaceno en la variable cada ejecución
        arrayNumbers <-- cardNumber.split('')
        arrayInverse <-- arrayNumbers.reverse()
        sum <-- 0

      Para i == 0  Hasta i < longitudArrayNumbers Con Paso i++ Hacer
        arrayInverse[i] <-- parseInt(arrayInverse[i])

          Si (i % 2 == 1) Entonces
            arrayInverse[i] <--suma de digitos(multiplicar*2(indice impares))

    	   Fin Si
         sum <-- suma de digitos d ela tarjeta

    	Fin Para
      retornar sum % 10 == 0 ? true : false
    FinProceso

    llamar la funcion
      isValidCard (cardNumber)

- ------------------------------------------
