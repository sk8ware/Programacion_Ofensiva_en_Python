

----
- TAG: #python #operadores #fundamentos
----
Los operadores aritméticos son símbolos que Python utiliza para realizar cálculos matemáticos.

Los fundamentales son:

- **Suma (+)**: No solo suma números, sino que también une secuencias como cadenas y listas, creando una nueva secuencia que es la combinación de ambas.
- **Resta (-)**: Se utiliza para restar un número de otro. Con listas, su uso es menos directo y generalmente no se aplica como operador directo.
- **Multiplicación (*)**: Cuando se multiplica un número por otro, obtenemos el producto. Con cadenas y listas, este operador repite los elementos la cantidad de veces especificada.
- **División (/)**: Divide un número entre otro y el resultado es siempre un número flotante, incluso si los números son enteros.
- **Exponente (**):** Eleva un número a la potencia de otro. Por ejemplo, ‘**2 ** 3**‘ resultará en 8. Este operador es menos común en operaciones con cadenas o listas.

**Operaciones con Cadenas**

En Python, las cadenas son objetos que representan secuencias de caracteres y se pueden manipular usando operadores aritméticos:

- **Concatenación (+)**: Une varias cadenas en una sola. Por ejemplo, ‘Hola’ + ‘ ‘ + ‘Mundo’ se convierte en ‘Hola Mundo’.
- **Repetición (*)**: Crea repeticiones de la misma cadena. ‘Hola’ * 3 generará ‘HolaHolaHola’.

**Operaciones con Listas**

Las listas son colecciones ordenadas y mutables de elementos:

- **Concatenación (+)**: Similar a las cadenas, unir dos listas las combina en una nueva lista.
- **Repetición (*)**: Repite todos los elementos de la lista un número determinado de veces.

**Funciones Especiales para Listas**

- **Zip**: Toma dos o más listas y las empareja, creando una lista de tuplas. Cada tupla contiene elementos de las listas originales que ocupan la misma posición.
- **Map**: Aplica una función específica a cada elemento de un iterable, lo que resulta útil para transformar los datos contenidos.

Asimismo, otro de los conceptos que mencionamos es el de ‘**TypeCast**‘. El TypeCast, o conversión de tipo, es el proceso mediante el cual se cambia una variable de un tipo de dato a otro.

En Python, esto se realiza de manera muy directa, utilizando el nombre del tipo de dato como una función para realizar la conversión. Por ejemplo, convertir una cadena a un entero se hace pasando la cadena como argumento a la función **int()**, y transformar un número a una cadena se hace con la función **str()**. Esta capacidad de cambiar el tipo de dato es especialmente útil cuando se necesita estandarizar los tipos de datos para operaciones específicas o para cumplir con los requisitos de las estructuras de datos.

A medida que progresemos, ampliaremos nuestro repertorio para incluir operaciones más complejas y explorar otros tipos de datos y estructuras en Python.

-----
# Operadores y Operaciones Básicas en Python


Vamos a crear unos ejemplos básicos para que esto quede muy claro. Empezamos creando un archivo que se llame `test.py`.

## Creación de Variables y Sumas

Primero, creamos una variable para la práctica:

```python
#/usr/bin/python

first_number = 2 
second_number = 8  

print(first_number + second_number)
```

Podríamos realizar la misma operación de la siguiente manera, almacenando el resultado en una variable:

```python
#/usr/bin/python 

first_number = 2 
second_number = 8  

result = first_number + second_number 

print(type(result))
```

De igual manera, podemos hacer esto con la resta, multiplicación y división tan solo cambiando el signo correspondiente en lugar del `+`.

También se puede elevar a la potencia con doble asterisco `**`.

Si deseamos redondear las respuestas, lo podemos hacer con la función `round`:

```python
#/usr/bin/python 

first_number = 2 
second_number = 8  

result = first_number / second_number  

print(round(result, 2))
```

## Formateo de Salidas en Python

Ahora hablaremos un poco sobre los formateos en las salidas de respuesta en Python. Este proceso consiste en convertir datos a una representación específica o estructura, es decir, darles un formato específico siguiendo un conjunto de reglas.

Podríamos hacer lo siguiente para añadir puntos o comas en los números para distinguir si son miles, cientos, etc.:

```python
#/usr/bin/python

first_number = 2 
second_number = 8  

result = first_number ** second_number 

print("{:,}".format(result))
```

Aquí podríamos sustituir las comas por puntos:

```python
#/usr/bin/python  

first_number = 2 
second_number = 8  

result = first_number ** second_number  

print("{:,}".format(result).replace(",", "."))
```

## Operador de Módulo `%`

El operador `%` se utiliza para obtener el resto de una división. Por ejemplo:

```python
#/usr/bin/python  

first_number = 10 
second_number = 3  

result = first_number % second_number 

print(result)  # Output: 1
```

## Operaciones con Cadenas

Ahora realizaremos operaciones con cadenas:

```python
first_str = "Hola" 
second_str = " " 
third_str  = "Mundo"  

print(first_str + second_str + third_str)
```

Esto nos daría como resultado en la consola `Hola Mundo`. La función `print(first_str * 3)` nos imprime 3 veces la palabra "Hola" ubicada en `first_str`.

En cambio, si solo deseamos repetir una letra en específico, podemos hacerlo con `print(first_str[0] * 8)`. También podemos jugar con rangos usando `print(third_str[0:3] * 5)` para imprimir en un rango de 5 veces la palabra `MunMunMun`.

## Operaciones con Listas

También podemos realizar operaciones con listas y muchas cosas más. En el siguiente ejemplo veremos cómo combinar la información de dos listas:

```python
#!/usr/bin/python3  

first_elements = [1, 3, 5, 7, 9] 
second_elements = [2, 4, 6, 8] 

result = first_elements + second_elements 

print(result)
```

Si deseamos mostrar los números en paralelo y en orden, lo podemos hacer de la siguiente manera:

```python
#!/usr/bin/python3  

odd_numbers = [1, 3, 5, 7, 9] 
even_numbers = [2, 4, 6, 8] 

result = zip(odd_numbers, even_numbers) 

for element in result:  
	print(element)
```

Para sumar los números en paralelo, podemos usar la siguiente función:

```python
#!/usr/bin/python3  

odd_numbers = [1, 3, 5, 7, 9] 
even_numbers = [2, 4, 6, 8, 10] 

result = map(sum, zip(odd_numbers, even_numbers)) 

for element in result:     
	print(element)
```

Finalmente, para fusionar las sumas en una sola lista en la salida por consola, lo podemos hacer de la siguiente manera:

```python
#!/usr/bin/python3  

odd_numbers = [1, 3, 5, 7, 9] 
even_numbers = [2, 4, 6, 8, 10] 

result = list(map(sum, zip(odd_numbers, even_numbers)))  

print(result)
```
