
----
- TAG: #Python #Tuplas #Programación #inmutables
----
En esta clase, dedicaremos nuestro enfoque a las tuplas, una estructura de datos fundamental en Python que comparte algunas similitudes con las listas, pero se distingue por su inmutabilidad.

Las tuplas son colecciones ordenadas de elementos que no pueden modificarse una vez creadas. Esta característica las hace ideales para asegurar que ciertos datos permanezcan constantes a lo largo del ciclo de vida de un programa.

**Características de las Tuplas**

- **Inmutabilidad**: Una vez que se crea una tupla, no puedes cambiar, añadir o eliminar elementos. Esta inmutabilidad garantiza la integridad de los datos que desea mantener constantes.
- **Indexación y Slicing**: Al igual que las listas, puedes acceder a los elementos de la tupla mediante índices y también puedes realizar operaciones de slicing para obtener subsecuencias de la tupla.
- **Heterogeneidad**: Las tuplas pueden contener elementos de diferentes tipos, incluyendo otras tuplas, lo que las hace muy versátiles.

**Operaciones con Tuplas**

Aunque no puedes modificar una tupla, hay varias operaciones que puedes realizar:

- **Empaquetado y Desempaquetado de Tuplas**: Las tuplas permiten asignar y desasignar sus elementos a múltiples variables de forma simultánea.
- **Concatenación y Repetición**: Similar a las listas, puedes combinar tuplas usando el operador ‘**+**‘ y repetir los elementos de una tupla un número determinado de veces con el operador ‘*****‘.
- **Métodos de Búsqueda**: Puedes usar métodos como ‘**index()**‘ para encontrar la posición de un elemento y ‘**count()**‘ para contar cuántas veces aparece un elemento en la tupla.

**Uso de Tuplas en Python**

- **Funciones y Asignaciones Múltiples**: Las tuplas son muy útiles cuando una función necesita devolver múltiples valores o cuando se realizan asignaciones múltiples en una sola línea.
- **Estructuras de Datos Fijas**: Se usan para crear estructuras de datos que no deben cambiar, como los días de la semana o las coordenadas de un punto en el espacio.

**Buenas Prácticas**

Abordaremos cuándo es más apropiado utilizar tuplas en lugar de listas y cómo la elección de una tupla sobre una lista puede afectar la claridad y la seguridad del código.

Al concluir esta clase, tendrás un entendimiento claro de qué son las tuplas, cómo y cuándo utilizarlas en tus programas, y las prácticas recomendadas para trabajar con este tipo de datos inmutable. Las tuplas son una herramienta poderosa en Python, y saber cómo utilizarlas te permitirá escribir código más seguro y eficiente.

----
# Tuplas en Python

## Introducción

Las tuplas en Python se parecen mucho a las listas, ya que ambas almacenan una secuencia de elementos. Sin embargo, las tuplas se declaran con paréntesis `( )` en lugar de corchetes cuadrados `[ ]` y, a diferencia de las listas, los elementos de una tupla son inmutables. Esto significa que una vez que una tupla es creada, no se puede modificar.

## Declaración y Acceso

Veamos un ejemplo práctico de cómo trabajar con **tuplas**:

```python
#!/usr/bin/python3

example = (1, 2, 3, 4, 5) 

print(example[1:3])
```

En este ejemplo, se observa que, al igual que con las listas, podemos seleccionar un rango de elementos dentro de una tupla.

## Inmutabilidad de las Tuplas

Si intentamos cambiar un elemento de una tupla, obtendremos un error:

```python
#!/usr/bin/python3  

example = (1, 2, 3, 4, 5) 

example[0] = 8
```

Al ejecutar este comando en la consola, se reflejará un error debido a la inmutabilidad de las tuplas.

## Tipos de Elementos en Tuplas

Las tuplas pueden contener diversos tipos de elementos, tales como cadenas, listas, valores booleanos, etc.:

```python
#!/usr/bin/python3  

example = (1, "test", [1, 2, 3], 4, True, {'manzanas': 1, 'peras': 5}, 5) 

for element in example:   
	print(element)
```
## Operaciones con Tuplas

En las Tuplas no tenemos la opción de usar las funciones como `insert()`, `extend()`, `remove()`, `append()`, `pop()`como lo hacíamos con las listas, todas estas funciones no son funcionales ya que las tuplas son inmutables.

Ahora mostraremos un ejemplo donde si queremos recibir elementos de esta tupla y asignarle algunas variables lo podemos hacer de esta manera cómoda donde podemos igualar los valores a, b, c, da `mi_tupla`de forma de que cada elemento de esta variable se convertirá en cada una de las variables a, b, c, d
### Desempaquetado de Tuplas

Podemos asignar los elementos de una tupla a variables de manera cómoda:

```python
#!/usr/bin/python3  

mi_tupla = (1, 2, 3, 4)  

a, b, c, d = mi_tupla  

print(a) 
print(b) 
print(c)
print(d)
```
### Concatenación de Tuplas

Aunque no podemos modificar una tupla directamente, podemos crear nuevas tuplas combinándolas:

```python
#!/usr/bin/python 

mi_primera_tupla = (1, 2, 3, 4)
mi_segunda_tupla = (5, 6, 7, 8, 9)

mi_tercera_tupla = mi_primera_tupla + mi_segunda_tupla 

print(mi_tercera_tupla)
```
### Repetición de Elementos en Tuplas

Podemos duplicar los elementos de una tupla utilizando el símbolo `*`:

```python
#!/usr/bin/python  

mi_primera_tupla = (1, 2, 3, 4)
mi_segunda_tupla = (5, 6, 7, 8, 9)  

mi_tercera_tupla = mi_primera_tupla * 3 

print(mi_tercera_tupla)
```
### Filtrado de Elementos en Tuplas

Para crear una nueva tupla con solo los números pares, podemos usar la siguiente técnica:

Primero queremos iterar por cada uno de los elementos con `for i in mi_tula`para almacenar todos los valores en `i`así que listamos con `i`al inicio pero siempre y cuando se cumpla una función entonces agregamos el `if i % 2 == 0`para cuando divida para `2`su resultado sea y finalmente convertimos todo esto en una `tupla`:

```python
#!/usr/bin/python  

mi_primera_tupla = (1, 2, 3, 4, 5, 6, 7, 8, 9) 

numeros_pares = tuple(i for i in mi_primera_tupla if i % 2 == 0)  

print(numeros_pares)
```

Si cambiamos el valor de `0` a `1` en la condición, obtendremos todos los números impares.

## Casos Prácticos de Uso

### Inmutabilidad en Bases de Datos

La inmutabilidad de las tuplas es útil en situaciones donde los datos no deben ser alterados. Por ejemplo, podemos almacenar credenciales de usuarios en tuplas para asegurar que no sean modificadas:

```python
#!/usr/bin/python3  

db1_credencial = ("chemaAlonso", "chema123")
db2_credencial = ("Hacker", "hacker123")  

try:   
	db1_credencial[0] = "Manolo"
 except TypeError:   
	print("No es posible manipular los elementos de una tupla")
```

## Resumen

Las tuplas en Python son una estructura de datos similar a las listas, pero con la diferencia crucial de que son inmutables. Esta característica permite operaciones seguras con datos que no deben cambiar, como las credenciales de usuarios. A pesar de su inmutabilidad, las tuplas permiten diversas operaciones como concatenación, repetición y filtrado de elementos.