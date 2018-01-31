## Credit Card Form
***

 Del proyecto "Credit Card Form" identificar las funciones globales, funciones locales, funciones de callback, expresions, statement, clousure, scope, contextos de ejecución, que funciones forman parte de la pila de ejecución (stack execution) y que funciones forman parte de la cola de eventos (event queue).

 * Funciones globales

```javascript
 - function() {} //línea 1
```

 * Funciones locales

```javascript
  - function() {} //línea 14
  - function desactiveButton(){} //línea 24.  
  - function longitud(input){} //línea 29
  - function soloNumeros(input) {} //línea 36
```

* funciones de callback

```javascript
 - soloNumeros(longitud(numberCard)) //línea 45
```
* Funciones expresions

```javascript
-  // No hay funciones expresions.
```

* Funciones statement

```javascript
- function activeButton(){} //línea 19
- function desactiveButton() {} //línea 24
- function longitud(input) {} //linea 29
- function soloNumeros(input) {} //linea 36
- function isValidCreditCard(numberCard) {} //línea 44
```

* clousure

```javascript
- function activeButton(){}; //línea 19
- function desactiveButton(){}; //línea 24
- function longitud(input){} //línea 29
```

* scope
  * scope global

  ```javascript
  - var $inputCard = $('#card-number'); //línea 6
  - var $inputMonth = $('.input-month'); //línea 7
  - var $inputYear = $('.input-year'); //línea 8
  - var $buttonNext = $('#next'); //línea 9
  - var regexOnlyNumbers = /^[0-9]+$/; //línea 10
  - var labelErrorOrSuccessMessages = $('label[for="card-number"]'); //línea 11
  ```
  * scope local

  ```javascript
  - var regex = /^[0-9]+$/; //línea 37
  - var creditCardNumber = soloNumeros(longitud(numberCard)); //línea 45
  - var arr = []; //línea 47
  - var sumaTotal = 0; //línea 48
  ```

* funciones forman parte de la pila de ejecución (stack execution)

```javascript
-  function(){}// Línea 1
// Cuando ingresa texto en el input entonces se carga las siguientes funciones:
- isValidCreditCard() //línea 14, está llamando a la función y lo carga en la pila.
- soloNumeros(longitud(numberCard)) //línea 45, llama a la función soloNumeros y lo carga a la pila,luego invoca a la función longitud y lo carga en la pila
- activeButton() // Línea 65
- desactiveButton(); // Línea 68
- desactiveButton(); // línea 72

```
* funciones forman parte de la cola de eventos (event queue)
```javascript
- $(document).ready(function() {}) // línea 1
- $inputCard.on('input', function() {}) // Línea 14
```
