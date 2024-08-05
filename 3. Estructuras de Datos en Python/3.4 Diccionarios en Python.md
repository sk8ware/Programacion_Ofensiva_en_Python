
----
##  TAG: #EstructuraDeDatos #PythonBásico #Mutables 
----
En esta clase, nos centraremos en los diccionarios, una de las estructuras de datos más poderosas y flexibles de Python. Los diccionarios en Python son colecciones desordenadas de pares clave-valor. A diferencia de las secuencias, que se indexan mediante un rango numérico, los diccionarios se indexan con claves únicas, que pueden ser cualquier tipo inmutable, como cadenas o números.

**Características de los Diccionarios**

- **Desordenados**: Los elementos en un diccionario no están ordenados y no se accede a ellos mediante un índice numérico, sino a través de claves únicas.
- **Dinámicos**: Se pueden agregar, modificar y eliminar pares clave-valor.
- **Claves Únicas**: Cada clave en un diccionario es única, lo que previene duplicaciones y sobrescrituras accidentales.
- **Valores Accesibles**: Los valores no necesitan ser únicos y pueden ser de cualquier tipo de dato.

**Operaciones con Diccionarios**

Durante la clase, exploraremos cómo realizar operaciones básicas y avanzadas con diccionarios:

- **Agregar y Modificar**: Cómo agregar nuevos pares clave-valor y modificar valores existentes.
- **Eliminar**: Cómo eliminar pares clave-valor usando del o el método ‘**pop()**‘.
- **Métodos de Diccionario**: Utilizar métodos como ‘**keys()**‘, ‘**values()**‘, y ‘**items()**‘ para acceder a las claves, valores o ambos en forma de pares.
- **Comprensiones de Diccionarios**: Una forma elegante y concisa de construir diccionarios basados en secuencias o rangos.

**Uso de Diccionarios en Python**

- **Almacenamiento de Datos Estructurados**: Ideales para almacenar y organizar datos que están relacionados de manera lógica, como una base de datos en memoria.
- **Búsqueda Eficiente**: Los diccionarios son altamente optimizados para recuperar valores cuando se conoce la clave, proporcionando tiempos de búsqueda muy rápidos.
- **Flexibilidad**: Pueden ser anidados, lo que significa que los valores dentro de un diccionario pueden ser otros diccionarios, listas o cualquier otro tipo de dato.

**Buenas Prácticas**

Enfatizaremos las mejores prácticas para trabajar con diccionarios, incluyendo la selección de claves adecuadas y el manejo de errores comunes, como intentar acceder a claves que no existen.

Al final de esta clase, tendrás una comprensión completa de los diccionarios y estarás listo para utilizarlos para gestionar eficazmente los datos dentro de tus programas. Los diccionarios son una herramienta esencial en Python y saber cómo utilizarlos te abrirá la puerta a un nuevo nivel de programación.

----
# Diccionarios en Python

Los diccionarios son una estructura de datos que almacenan pares de clave

. A diferencia de las listas o las tuplas, los diccionarios no están ordenados, lo que significa que no tienen índices numéricos. Sin embargo, son mutables, lo que nos permite alterar su contenido.

### Creación de un Diccionario

Vamos a hacer una pequeña prueba en un archivo para crear nuestro diccionario. Pueden usar tanto `nano` como `nvim`.

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

print(type(mi_diccionario))
print(mi_diccionario)
```

### Acceso a los Valores

Para acceder a los valores, usamos las claves. Por ejemplo, para obtener la edad:

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

print(mi_diccionario["Edad"])
```

Dentro de los corchetes, pueden cambiar el elemento según su selección para que imprima el valor correspondiente.

### Modificación de Valores

Si deseamos cambiar el nombre o cualquier otro elemento dentro de nuestro diccionario, podemos hacerlo ya que es mutable.

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

mi diccionario["Nombre"] = "Sk8ware"

print(mi_diccionario["Nombre"])
print(mi_diccionario)
```

### Adición de Nuevos Elementos

Podemos agregar elementos que no existan en nuestro diccionario simplemente asignándolos; pero al momento de eliminarlo o quitarlo de tu línea de código ya no aparecerá al momento de imprimirlo .

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

mi_diccionario["Profesión"] = "lammer"

print(mi_diccionario)
```

### Eliminación de Elementos

Podemos eliminar elementos de este diccionario de la siguiente manera:

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

del mi_diccionario["Edad"]

print(mi_diccionario)
```

### Comprobación de Claves

Si tienes un diccionario con muchas claves, quizás te interese saber si una clave específica está presente,
Lo podemos hacer a través de un condicional de la siguiente manera 

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

if "Provincia" in mi_diccionario:
	print("Esta clave existe en el diccionario")

```

Pero si quisiera buscar por otro nombre o clave que no existe no mostrará nada ya que no esta representada con un `else`

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

if "Provincia" in mi_diccionario:
	print("Esta clave existe en el diccionario")
else:
	print("Esta clave no existe en el diccionario")
```

### Iteración Sobre un Diccionario

Podemos iterar sobre un diccionario con bucles `for`. Al iterar, obtenemos tanto la clave como el valor.

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

for key, value in mi_diccionario.items():
	print(f"Para la clave {key} tendríamos el valor {value}")

```

Recuerden que en la parte de la clave y valor lo pueden llamar como ustedes quieran siempre y cuando recuerden estos nombres para poderlos llamar 

### Longitud del Diccionario

Los diccionarios también tiene longitudes, si observamos veremos que tenemos 3, lo podríamos observar de la siguiente manera

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

print(f"La longitud del diccionario es de {len(mi_diccionario)}")
```

### Limpieza del Diccionario

Con los diccionarios también podemos limpiar todo el contenido con `.clear()`, si lo vemos de la siguiente manera observaremos que hemos limpiado todo

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

mi_diccionario.clear()

print(f"La longitud del diccionario es de {len(mi_diccionario)} elementos")
print(mi_diccionario)
```

### Diccionarios por Comprensión

Hay un diccionario muy interesante que son los diccionarios de comprensión, creando un ejemplo donde `x` sería la clave, asi que x al principio vale `0` y hara una función empezando desde el cero hasta el 5, ya que se eleva al cuadrado el numero a retornar que seria 0, 1, 2, 3, 4, 5

```python
#!/usr/bin/python3

cuadrados = {x: x**2 for x in range(6)}

print(cuadrados)
```

Si deseas organizar el contenido lo podrías englobar solo al elemento de tu interés con `print(cuadrados[5])`

### Obtener Claves y Valores

Podemos obtener todas las claves y valores de un diccionario.

```python
#!/usr/bin/python3

cuadrados = {x: x**2 for x in range(6)}

print(cuadrados.keys())
print(cuadrados.values())
```

### Uso del Método `.get()`

Para obtener un valor de manera segura, usamos el método `.get()`.

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

print(mi_diccionario.get("Nombre", "No encontrado"))
```

### Actualización de un Diccionario

Podemos ampliar un diccionario con el método `.update()`.

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}
mi_diccionario2 = {"Profesión": "Hacker", "Mascotas":"Gatos"}

mi_diccionario.update(mi_diccionario2))
```

### Diccionarios Anidados

Podemos tener diccionarios anidados, lo que es útil para representar datos más complejos.

```python
my_dict = {
	"nombres": "sk8ware"
	"hobbies": {"primero": "musica", "segundo": "sk8"},
	"edad": 22
}
print(my_dict)
```

Puden ver la longitud de este diccionario con `print(len(my_dict)` además podemos listar por la clave en especifico como `hobbies`

```python
my_dict = {
	"nombres": "sk8ware"
	"hobbies": {"primero": "musica", "segundo": "sk8"},
	"edad": 22
}
print(my_dict["hobbies"]["primero"])
```

Pueden cambiarlo por subclave también si lo desean antes de primero sería el nombre segundo, que seria la subclave
### Iteración Sobre Claves y Valores

La manera de iterar sobre un diccionario es la siguiente, tenemos 3 formas por así decirlo

- Para representar únicamente las claves:

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

for element in my dict:
	print(element)
```

También se le puede poner como `for element in my_dict.key():`

- Si solo quisiéramos iterar por lo valores tendríamos que hacerlo de la siguiente manera

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

for element in my_dict.values():
	print(element)
```

- Ahora si queremos mostrar la clave y el valor tendríamos que hacerlo de la siguiente manera:

```python
#!/usr/bin/python3

mi_diccionario = {"Nombre": "Anthony", "Edad": 22, "Provincia": "Pichincha"}

for key, value in my_dict.items():
	print(f"[{key}]: {value}")
```
