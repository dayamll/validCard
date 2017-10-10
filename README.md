## VALID CARD
#### Contenido:
1. Diagrama de flujo validCard.
2. Pseudocódigo validCard.
3. Explicación del código.


- - - - - - -  --- - - - - - - - -- -

### 1. DIAGRAMA DE FLUJO

![validcard](assets/docs/diagramaFlujoCard.png)
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

### 3. EXPLICACIÓN DEL CÓDIGOS

Nos pide válidar el número de tarjeta de crédito, utilizando el algoritmo de Luhn.

**Ingreso de dato**

Aqui solicitamos el número de tarjeta, mediante un `prompt`, guardandolo en la variable cardNumber.

`var cardNumber = prompt ("Ingrese su número de tarjeta: ");`

Ejemplo: cardNumber = '4975226157921705'

>  Ojo, al ingresar un dato en el prompt, este siempre es de tipo string, asi que el número de tarjeta ingresado, será de tipo string.

**Creamos la funcion isValidCard**

`function isValidCard(cardNumber){}`

**Proceso para validar el numero**
  
* El string es convertido en un array con separacion de (''), con split: 

`var arrayNumbers = cardNumber.split('');`

obteniendo: ['4', '9', '7', '5', '2', '2', '6', '1', '5', '7', '9', '2', '1', '7', '0', '5' ]

* Para seguir con el algoritmo de Luhn, invertimos el array, con reverse():

`var arrayInverse = arrayNumbers.reverse();`

obteniendo: ['5', '0', '7', '1', '2', '9', '7', '5', '1', '6', '2', '2', '5', '7', '9', '4' ]

* Creamos el acumulador suma para almacenar más adelante, la suma de digitos.

`var sum = 0;`

* Ahora vamos a convertir los elementos del array tipo string a numbers. 


    for(var i = 0; i < arrayInverse.length; i++){
        arrayInverse[i] = parseInt(arrayInverse[i]);
    }

Se obtendrá: [5, 0, 7, 1, 2, 9, 7, 5, 1, 6, 2, 2, 5, 7, 9, 4 ]

* Debemos multiplicador x2 a las posiciones impares de nuestro array, teniendo encuenta que inicializamos con i = 0, para ello hacemos un if.

![imagen](assets/docs/indice.png)

![imagen](assets/docs/indicemulti.png)

* Despues debeos sumar los digitos de los resultos, es decir, si en mi posición i=5, obtengo un digito de dos cifras debo sumar 1 + 8, y como lo hacemos, separando el número asi:

18 / 10 = 1.8, con parseInt se obtendra 1

18 MOD 10 = 8

obteniendo los digitos separados

En código será asi:


    if(i % 2 == 1){
      arrayInverse[i] = (parseInt((arrayInverse[i] * 2 )/ 10 )) + ((arrayInverse[i] * 2 ) % 10 );
    }

ojo: lo que ejecuta el IF será la suma de los digitos, almacenado en el mismo array.

![imagen](assets/docs/indice2.png)			

* Debemos obtener la suma de digitos, para ellos utilizaremos nuestro acumulador sum, creado anteriormente

          sum += arrayInverse[i];		

    dada como resultado sgunn nuestro ejemplo: 70

* Para validar si este número de tarjeta es correcta nuestra suma MOD 10 debe resulta 0

      sum % 10 == 0
										
  Para este ejemplo 70 mod 10 = 0, es decir que nuestra tarjeta es válida.

* Por último mostrar un document.write que indique si es TRUE o FALSE.		

      return sum % 10 == 0 ? document.write( true + ', su número de tarjeta es válido')  : document.write( false + ', su número de tarjeta NO es válido') ; 

* Finalmente, no olvidar en llamar a la función.

      isValidCard (cardNumber);
