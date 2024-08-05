
----
- TAG: #python #manejo-de-errores #excepciones #Programación 
-----
En esta clase, abordaremos el manejo de errores y excepciones, un aspecto crítico para la creación de programas robustos y confiables en Python. Los errores son inevitables en la programación, pero manejarlos correctamente es lo que diferencia a un buen programa de uno que falla constantemente.

**Manejo de Errores**

Los errores pueden ocurrir por muchas razones: errores de código, datos de entrada incorrectos, problemas de conectividad, entre otros. En lugar de permitir que un programa falle con un error, Python nos proporciona herramientas para ‘atrapar’ estos errores y manejarlos de manera controlada, evitando así que el programa se detenga inesperadamente y permitiendo reaccionar de manera adecuada.

**Excepciones**

Una excepción en Python es un evento que ocurre durante la ejecución de un programa que interrumpe el flujo normal de las instrucciones del programa. Cuando el intérprete se encuentra con una situación que no puede manejar, ‘levanta’ o ‘arroja’ una excepción.

**Bloques try y except**

Para manejar las excepciones, utilizamos los bloques ‘**try**‘ y ‘**except**‘. Un bloque ‘**try**‘ contiene el código que puede producir una excepción, mientras que un bloque ‘**except**‘ captura la excepción y contiene el código que se ejecuta cuando se produce una.

**Otras Palabras Clave de Manejo de Excepciones**

- **else**: Se puede usar después de los bloques ‘**except**‘ para ejecutar código si el bloque ‘**try**‘ no generó una excepción.
- **finally**: Se utiliza para ejecutar código que debe correr independientemente de si se produjo una excepción o no, como cerrar un archivo o una conexión de red.

**Levantar Excepciones**

También es posible ‘levantar’ una excepción intencionalmente con la palabra clave ‘**raise**‘, lo que permite forzar que se produzca una excepción bajo condiciones específicas.

En esta clase, aprenderemos a identificar diferentes tipos de excepciones y cómo manejarlas de manera específica. También exploraremos cómo utilizar la declaración ‘**raise**‘ para crear excepciones que ayuden a controlar el flujo del programa y evitar estados erróneos o datos corruptos.

Al final de esta clase, tendrás las habilidades para escribir programas que manejen situaciones inesperadas de manera elegante y mantengan una ejecución limpia y controlada, incluso cuando se encuentren con problemas imprevistos.

----
# Manejo de errores y exepciones 

En esta clase vamos a explorar los tipos de errores y cómo solucionarlos.

Pondremos en práctica el siguiente error con el ejemplo a continuación, donde trataremos de dividir un número entre cero y provocar un error. Para manejar el error, usamos `except`:
```python 
#!/usr/bin/python3

try:	
	num = 5/0

except:
	print("No se puede dividir un núnmero entre cero")
```


Si ejecutamos solo `num = 5 / 0`, veremos que el sistema nos indica que el error es de tipo `ZeroDivisionError`. Podemos manejar este error de la siguiente manera:

```python
#!/usr/bin/python3

try:
	
	num = 5/0

except ZeroDivisionError:
	
	print("No se puede dividir un núnmero entre cero")
```

De esta forma veremos la respuesta de error de mejorar manera 

Si tratamos de mostrar otro tipo de error tratando de imprimir de manera erronea `num = "Hola"/0` el cual nos devolvera un error de tipo `TypeError`
Así que si deseamos agregar este tipo de error a nuestro ejemplo tendríamos que contemplarlo de la siguiente manera 

```python
#!/usr/bin/python3

try:
	
	num = "Hola"/0

except ZeroDivisionError:
	
	print("No se puede dividir un núnmero entre cero")

except TypeError:
	
	print("Solo es posible imprimir números enteros")
```

También podemos jugar con `else` en caso que no se acontezca ninguno de estos errores

```python
#!/usr/bin/python3

try:
	
	num = "Hola"/0

except ZeroDivisionError:
	
	print("No se puede dividir un núnmero entre cero")

except TypeError:
	
	print("La operatoria matemáticas sólo deben realizarse con números!")

else:
	
	print(f"La división de ambos números da como resultado {num}")
```

En las excepciones también manejamos un concepto que se llama `finally` es bloque de código que se va a ejecutar en las excepciones siempre

```python
#!/usr/bin/python3

try:
	
	num = "Hola"/0

except ZeroDivisionError:
	
	print("No se puede dividir un núnmero entre cero")

except TypeError:
	
	print("La operatoria matemáticas sólo deben realizarse con números!")

else:
	
	print(f"La división de ambos números da como resultado {num}")

finally:
	
	print("Esto siempre se va a ejecutar")
```

La excepciones también se pueden lanzar 

Vamos a jugar con el número `x = -5` y si es x es menor que cero `if x < 0 :` y para emplear una excepción debemos utilizar `raise` 

```python
#!/usr/bin/python3

x = -5

if x < 0:
	raise Exception("¡No se pueden utilizar números negativos")
```

Intenten acontecer y ver todos los tipos de errores que puedan para poder seguir practicando un poco sobre el manejo de errores de excepciones 