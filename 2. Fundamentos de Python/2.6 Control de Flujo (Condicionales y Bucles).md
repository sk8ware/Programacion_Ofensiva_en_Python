
---
- TAG: #Python #Programación #Bucles #Condicionales
-----
Los conceptos vistos en esta clase son esenciales para entender cómo crear programas en Python que puedan tomar decisiones y repetir acciones hasta cumplir ciertos criterios. Aquí es donde nuestros programas obtienen la capacidad de responder a diferentes situaciones y datos.

**Condicionales**

Los condicionales son estructuras de control que permiten ejecutar diferentes bloques de código dependiendo de si una o más condiciones son verdaderas o falsas. En Python, las declaraciones condicionales más comunes son ‘**if**‘, ‘**elif**‘ y ‘**else**‘.

- **if**: Evalúa si una condición es verdadera y, de ser así, ejecuta un bloque de código.
- **elif**: Abreviatura de “**else if**“, se utiliza para verificar múltiples expresiones sólo si las anteriores no son verdaderas.
- **else**: Captura cualquier caso que no haya sido capturado por las declaraciones ‘**if**‘ y ‘**elif**‘ anteriores.

**Bucles**

Los bucles permiten ejecutar un bloque de código repetidamente mientras una condición sea verdadera o para cada elemento en una secuencia. Los dos tipos principales de bucles que utilizamos en Python son ‘**for**‘ y ‘**while**‘.

- **for**: Se usa para iterar sobre una secuencia (como una lista, un diccionario, una tupla o un conjunto) y ejecutar un bloque de código para cada elemento de la secuencia.
- **while**: Ejecuta un bloque de código repetidamente mientras una condición específica se mantiene verdadera.

**Control de Flujo en Bucles**

Existen declaraciones de control de flujo que pueden modificar el comportamiento de los bucles, como ‘**break**‘, ‘**continue**‘ y ‘**pass**‘.

- **break**: Termina el bucle y pasa el control a la siguiente declaración fuera del bucle.
- **continue**: Omite el resto del código dentro del bucle y continúa con la siguiente iteración.
- **pass**: No hace nada, se utiliza como una declaración de relleno donde el código eventualmente irá, pero no ha sido escrito todavía.

En esta clase, profundizaremos en cada uno de estos aspectos con ejemplos detallados. Aprenderemos cómo tomar decisiones dentro de nuestros programas y cómo automatizar tareas repetitivas. Esto nos dará la base para escribir programas que pueden manejar tareas complejas y responder dinámicamente a los datos de entrada. Al final de la clase, estarás equipado con el conocimiento para controlar el flujo de tus programas de Python de manera eficiente y efectiva.

----
Vamos primero por los `bucles y los condicionales`

# Bucles
Los bucles nos permiten iterar sobre una secuencia, pueden ser tanto como duplas, diccionarios, conjuntos etc
Para explicarlo de mejor manera y detallado vamos a realizarlo con el siguiente ejercicio
```python
#!/usr/bin/python3
for pepito in range(5):
	print(pepito)
```
Salida:
```python3
0
1
2
3
4
```

En este caso mostrará la respuesta 01234 ya que cuando especificamos rangos para englobar o elementos de una lista, siempre suele la cantidad que especificamos menos el ultimo número ya que cuenta siempre desde el 0  

Ahora veremos otro ejemplo agregando variables;
```python
#!/usr/bin/python3

names = ["sk8ware", "Marcelo", "TheGodHacker"]

for name in names:
    print(f"El nombre para esta vuelta es{name}")
```

# while
Ahora utilizaremos la función `while` para poder dar un pequeño ejemplo y puedan ver las diferencias entre la creación de bucles con diferentes funciones
```python
#!/usr/bin/python3

i = 0 

while i < 5:
	print(i)
	
	i += 1 
```

Depende de la instrución que le indiquemos cumplira la función pero si no se indica la instrución while sería un bucle infinito 

# Enumerate

Otra forma de jugar es con `Enumerate` 
```python
#!/usr/bin/python3

nombres = ["Pepe", "Mitis", "Claudia", "Negra"]

for contador, nombre in enumerate(nombres):
	print(f"Nombre [{contador+1}]: {name}")
```

Recuerden que enumerate siempre devuelve el indice y el valor
Va retornando tanto el indice como el valor 
Para ello hay que separarlo en dos variables
Y el {i+1} permite que no cuente desde 0 y muestre desde 1 


Otro ejemplo podria ser la implementación de diccionarios junto con bucles
En resume los diccionarios son una estrucutura de datos no ordenados que almacen pares de clave valor 
ejemplo:
```python
#!/usr/bin/python3

frutas = {"sandia": 4, "manzana": 5, "melon": 8}

for fruta, cantidad in frutas.items():
    print(f"Hay {cantidad} cantidades de la fruta {fruta}")
```

Ahora tendremos los bucles anidados

Esto seria una forma muy chula de hacer bucles dentro de otros bucles, para ello vamos a crear una lista sobre otra lista

```python
#!/usr/bin/python3

my_list = [[1, 4, 5], [2, 6, 8], [9, 4, 1]]

for element in_list:
	
	print(element)
```


Para desglozarlo lo podriamos hacer de la siguiente manera:
```python
#!/usr/bin/python3

my_list = [[1, 4, 5], [2, 6, 8], [9, 4, 1]]

for element in_list:
	for element_in_list in element:
		print(element)
```

Le podemos añadir un poco de estética para verlo de mejor manera en la salida por consola:
```python
#!/usr/bin/python3

my_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

for element in my_list:
    print(f"\n[+] Vamos desglosar la lista{element}\n")
    for element_in_list in element:
        print(element_in_list)
```

Para iterar sobre esta lista se usa `element_in_list` 

# Bucles sobre una lista

Otra forma que tuvieras de jugar con bucles sobre una lista es hacer como se conoce una lista de comprensión (for)
creando el ^ de cada numero 
```python
#!/usr/bin/python3
odd_list = [1, 3, 5, 7, 9]
cuadrado = [i ** 2 for i in odd_list]

print(cuadrado)
```

Tambien tenemos una opción que nos permite cortar hasta cierto limite que nosotros queramos con la función `break` 
Hay que tomar en cuenta la importancia de la colocación del `print` ya que segun la posición mostrara uno u otra respuesta
```python
#!/usr/bin/python3

for i in range(10):

	if i == 5:
		break
		
	print(i)
```

o 

```python
#!/usr/bin/python3

for i in range(10):
	print(i)
	
	if i == 5:
		break
```

Aliada a `break` tambien hay la utilllidad en bucles que es `continue` cuando no queramos que pase nada en concreto 
```python
#!/usr/bin/python3

for i in range(10):
	
	if i == 5:
		continue
	print(i)
```

Asi mismo cuando hablamos de condicionales una cosa es el `if` y otra cosa el `else` que es lo que define como lo contrario a la condición
```python
#!/usr/bin/python3

for i in range(10):

	if i ==5:
		print("Actualmente 'i' vale 5")
	else:
		print("Actualmente 'i' no vale 5")
```

Si solo tuvieramos la opción `if` nos mostraria solo la respuesta de lo que vale if, pero si agregamos la función `else` para que muestre lo que vale los demas números dentro de `range(10)`

```python
#!/usr/bin/python3

for i in range(10):

    if i == 5:
        print("Actualmente el valor de 'i' es 5")
    else: 
        print("Actualmente el valor de 'i' no es de 5")

```

Si desean ver el numero al que pertenece simplemente le agregan al final del 5 la función `[{i}]` y la `f` antes de las comillas del principio 

En la parte de `else` hay algo que muchos no saben, es que los propios bucles como for, while y demas tambien tienen un `else` solo que aqui es diferente, como les mostraré a continuación 
```python
#!/usr/bin/python3

for i in range(10):
	if i == 10:
		break
else:
	print("Bucle concluido exitosamente")
```


Aqui sabemos qu e`i` empiza valiendo `0` y por eso nunca llegara al `break` 
A diferencia de que si iteramos hasta el `(16)` y si lo ejecutamos sabremos que sera un codigo exitoso ya que si llegara al break
```python
#!/usr/bin/python3

for i in range(16):
	if i == 10:
		break
else:
	print("Bucle concluido exitosamente")
```

Si deseamos seguir imprimiendo solicitudes o comandos lo podemos seguir haciendo
```python
#!/usr/bin/python3

for i in range(16):
	if i == 10:
		break
else:
	print("Bucle concluido exitosamente")
# ---------------------
print("Continuamos con la ejecución del resto de instrucciones")
```

Si deseamos que aparezcan los dos mensajes
```python
#!/usr/bin/python3

for i in range(6):
	if i == 10:
		break
else:
	print("Bucle concluido exitosamente")
```

# While

Asi mismo con los bucles `while` 

Ahora vamos a mostrarlo con este siguiente ejemplo, donde `i` equivale a 0 y se lo suma hasta el numero 10, si no pusieramos este numero 10 sería un bucle infinito, pero añadiendo el `i += 1` si llegaría al break y como respuesta tuvieramos la salida del bucle while 

```python
#!/usr/bin/python3

i = 0 

while i < 10:
	if i == 10:
		break
	i += 1
else:
	print("El bucle terminó normalmente")
```

Ahora si le pedimos que que se imprima "salimos antes de tiempo" si i llega a valer 10 y terminará el bucle dado por la función `break` y por ultimo imprimirá la función print "Estamos fuera del bucle"
```python
#!/usr/bin/python3

i = 0 

while i < 16:
	if i == 10:
		print("Salimos antes de tiempo")
		break
	i += 1
else:
	print("El bucle terminó normalmente")
# -------------------------------------
print("Estamos fuera del bucle")
```

La estructura de los condicionales es super basica 
Vamos a poner el siguiente ejemplo con la variable edad = 20 , para identificar si eres mayor de edad o no 
```python
#!/usr/bin/python

edad = 20

if edad >= 18:
	print("Eres mayor de edad")
```

Si lo ejecutamos veremos que nos imprime que somos mayores de edad, pero si no tenemos la función `else`no mostrará cuando la respuesta sea menor a 18, asi que para eso deberiamos agregarlo a continuación
```python
#!/usr/bin/python

edad = 15

if edad >= 18:
	print("Eres mayor de edad")
else:
	print("Eres menor de edad")
```

De igual manera podemos jugar con los simbolos 

En las condicionales podemos establecer multiples condiciones partiendo del mismo contexto como a continuación con `elif` 
```python
#!/usr/bin/python

edad = 15

if edad < 13:
	print("Eres un niño")
elif 13 <= edad < 18:
	print("Eres un adolecente")
else:
	print("Eres un adulto")
```

`elif` significa como de lo contrarío a la función de arriba, o si esta dentro de ese rango de dos opciones muestre el mensaje "Ers un adolecente", en cambio `else`es como si ninguna de las anteriores se cumple esto es lo que va a pasar

Jugando con la condicionales tambien podemos jugar con las ternarias 
Operadores ternarios nos permite represntar toda la operatoria en una sola linea
```python
#!/usr/bin/python

edad = 17 

mensaje = "Eres mayor de edad" if edad >= 18 else "Eres menor de edad"

print(mensaje)
```

# AND, NOT, OR

También tenemos a lo que llamamos operadores logicos
**and,  not, or**

En este ejemplo se cumpliria la función **AND**
```python
#!/usr/bin/python

edad = 20 
nacionalidad = "Ecuatoriano"

if edad >= 18 and nacionalidad == "Ecuatoriano":
	print("Puedes votar en las elecciones Ecuatorianas")
else:
	print("No eres Ecuatoriano mmv")
```


Con la función **OR** asi no se cumpla la primera función podria seguir saliendo la respues que si  puede votar
```python
#!/usr/bin/python

edad = 13
nacionalidad = "Ecuatoriano"

if edad >= 18 or nacionalidad == "Ecuatoriano":
	print("Puedes votar en las elecciones Ecuatorianas")
else:
	print("Chiii no eres Ecuatoriano ñañoshh")
```

Y aplicando la función **NOT** se vería de la siguiente manera
```python
#!/usr/bin/python

edad = 20
nacionalidad = "Española"

if edad >= 18 or nacionalidad != "Ecuatoriano":
	print("Puedes votar en las elecciones Ecuatorianas")
else:
	print("Chiii no eres Ecuatoriano ñañoshh")
```
Con respuesta que puedes seguir votando en las elecciones ecuatorianas

Los condicionales tambein nos pueden servir para determinar o detectar elementos existentes en una lista y varios ejemplos mas
Pondre un ejemplo a continuación 
```python
#!/usr/bin/python

mi_lista = [1, 4, 6, 12, 14, 18, 79]

if 18 in mi_lista:
	print("Este número está en la lista")
else:
	print("Este número no está en la lista")
```

Pero si pusieramos un número que no existierá nos reflejaria el mensaje de que no esta en la lista


De igual manera como teniamos para continue en los bucles, en los condiconales tenemos `pass`, sirve únicamente para la validación del codigo en caso de que no pase nada con la función
```python
#!/usr/bin/python

edad = 20
nacionalidad = "Ecuatoriano"

# Condicional anidado
if edad >= 18:
	if nacionalidad == "argentino":
		pass
```

# NÚMEROS PARES

Ahora veremos el tipico ejemplo de los números pares

Nuevamente implementando condionales imaginen que tenemos el siguiente ejemplo 
El simbolo `%` en ocasiones nos permite saber cuando un numero es par o no, asi que lo agregamos dentro del buqle lo argegamos como condición, si divimos e número para 2 y subresto, entoces lo que queremos es verlo en consolo solo numeros pares con print:

```python
#!/usr/bin/python3

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for number in numbers:
	if number % 2 == 0:
		print(number)
```

Aqui solo lee el numero 2 para saber si imprimir numeros pares o impares dentro de la condición, pero si cambiamos los simbolos por `!=` asi solo vamos a ver los números impares o con `if number % 2 == 1:`
```python
#!/usr/bin/python3

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for number in numbers:
	if number % 2 != 0:
		print(number)
```

Y de ultimo ejemplo vamos a emplear un ejemplo donde una variable actua como un valor boleano que puede estar entre true o false
```python
#!/usr/bin/python3

numbers = [2, 4, 6, 8, 10]
todos_son_pares = True

for number in numbers:
	if number % 2 != 0:
		todos_son_pares = False
		break

if todos_son_pares:
	print("Todos los elementos de la lista son pares")
else:
	print("Alguno de los elementos de la lista es impar")
```

