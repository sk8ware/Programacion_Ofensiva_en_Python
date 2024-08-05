
---
- TAG: #Python #LambdaFunctions #Programming
----
Esta clase se centra en una característica poderosa y expresiva de Python que permite la creación de funciones en una sola línea: las funciones lambda.

**Funciones Lambda**

Las funciones lambda son también conocidas como funciones anónimas debido a que no se les asigna un nombre explícito al definirlas. Se utilizan para crear pequeñas funciones en el lugar donde se necesitan, generalmente para una operación específica y breve. En Python, una función lambda se define con la palabra clave ‘**lambda**‘, seguida de una lista de argumentos, dos puntos y la expresión que desea evaluar y devolver.

Una de las ventajas de las funciones lambda es su simplicidad sintáctica, lo que las hace ideal para su uso en operaciones que requieren una función por un breve momento y para casos donde la definición de una función tradicional completa sería excesivamente verbosa.

**Usos comunes de las Funciones Lambda**

- **Con funciones de orden superior**: Como aquellas que requieren otra función como argumento, por ejemplo, ‘**map()**‘, ‘**filter()**‘ y ‘**sorted()**‘.
- **Operaciones simples**: Para realizar cálculos o acciones rápidas donde una función completa sería innecesariamente larga.
- **Funcionalidad en línea**: Cuando se necesita una funcionalidad simple sin la necesidad de reutilizarla en otro lugar del código.

En esta clase, aprenderemos cómo y cuándo utilizar las funciones lambda de manera efectiva, además de entender cómo pueden ayudarnos a escribir código más limpio y eficiente. Aunque su utilidad es amplia, también discutiremos las limitaciones de las funciones lambda y cómo el abuso de estas puede llevar a un código menos legible.

Al dominar las funciones lambda, ampliarás tu conjunto de herramientas de programación en Python, permitiéndote escribir código más conciso y funcional.

----
# Lambda anónimas python 
## Introducción

En este documento exploraremos las funciones lambda en Python a través de varios ejemplos prácticos. Las funciones lambda, también conocidas como funciones anónimas, son útiles para escribir funciones pequeñas y de una sola línea.

## Ejemplo Sencillo

Empezaremos creando un ejercicio sencillo para poderlo explicar de mejor manera 
creamos un archivo `test.py` y creamos e imprimimos la función `mi_funcion` 

```python
#!/usr/binpython3

mi_funcion = lambda: "¡Hola mundo!"

print(mi_funcion())

```

## Lambdas con Argumentos

A la misma función se le puede agregar argumentos de la siguiente manera:

```python
#!/usr/bin/python3

cuadrado = lambda x: x**2

print(cuadrada(6))

```

Hemos representado el número 6 elevado al cuadrado que recuerden siempre se lo representa al número con la x por ejemplo y a x lo elevamos al cuadrado con `**`

## Suma de Dos Valores

Si deseamos también que se sumen dos valores con dos diferentes argumentos se lo pueden hacer de la siguiente manera
```python
#!/usr/bin/python3

suma = lambda x, y:x+y

print(suma(6, 8))
```

## Uso de Lambdas en Contextos Más Realistas

Ahora crearemos un ejercicio como en entorno más realista donde convertiremos los siguientes números al cuadrado con la función lambda 
```python
#!/usr/bin/python3

numeros = [1, 2, 3, 4, 5]

cuadrados =list(map(lambda x: x**2, numeros))

print(cuadrados)
```

Recuerden que **map** tine dos argumentos `función` y un `iterable`, donde numeros viene sinedo una lista iterable y `list` nos permite visualizarlos como lista

## Funciones `filter` y `reduce`

También tenemos las funciones  **filter** y **reduce** las cuales las podemos utilizar para funciones **lambda**

Para saber si los números son par o no utilizamos el signo de porcentaje y si a ese número lo dividimos para 2 y su resultado es 0 es por que es número par

### Filtrar Números Impares

Para `filter` es la misma función que `map` se necesita siempre los dos argumentos que son la `función` y un `iterable`

```python
#!/usr/bin/python3

numeros = [1, 2, 3, 4, 5]

impares = list(filter(lambda x: x % 2 !=0, numeros))

print(impares)
```

La función `==` nos permite mostrar los números para los números iterables y la función != nos permite mostrar los impares 

### Reducir una Lista a un Producto

Con la función `reduce `

Del modulo `from functools` nos permite importar la función `reduce` para fusionarla con nuestra función `lambda` 
De igual manera funciona como filter y map con su dos argumentos y el iterable
Para que pueda llamar a la primera función y luego pasara a multiplicar con el siguiente número que se encuentra en la lista iterable
```python

from functools import reduce

numeros = [1, 2, 3, 4, 5]

producto = reduce(lambda x, y: x*y, numeros)

print(producto)
```

## Consideraciones Finales

Las funciones lambda no se utilizan con frecuencia a menos que se necesiten para alguna refactorización de código o para escribir funciones pequeñas y rápidas.