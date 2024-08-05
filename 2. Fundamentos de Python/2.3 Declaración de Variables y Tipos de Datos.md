
----
- TAG: #Python #Programación #Cadenas #Listas #TypeCasting #Bucles
- ----
Las variables en Python son como nombres que se le asignan a los datos que manejamos. Piensa en una variable como un nombre que pones a un valor, para poder referirte a él y utilizarlo en diferentes partes de tu código.

En la clase actual, vamos a enfocarnos en comprender las variables y algunos de los tipos de datos fundamentales en Python. Estos conceptos son esenciales, ya que nos permiten almacenar y manipular la información en nuestros programas.

**Variables**

Una variable en Python es como un nombre que se le asigna a un dato. No es necesario declarar el tipo de dato, ya que Python es inteligente para inferirlo.

**Cadenas (Strings)**

Las cadenas son secuencias de caracteres que se utilizan para manejar texto. Son inmutables, lo que significa que una vez creadas, no puedes cambiar sus **caracteres individuales**.

**Números**

Python maneja varios tipos numéricos, pero nos centraremos principalmente en:

- **Enteros (Integers)**: Números sin parte decimal.
- **Flotantes (Floats)**: Números que incluyen decimales.

**Listas**

Las listas son colecciones ordenadas y mutables que pueden contener elementos de diferentes tipos. Son ideales para almacenar y acceder a secuencias de datos.

Y para trabajar con estas listas, así como con cadenas y rangos de números, utilizaremos los bucles ‘**for**‘, que nos permiten iterar sobre cada elemento de una secuencia de manera eficiente.

Estas son solo algunas de las estructuras de datos con las que trabajaremos por el momento. A medida que avancemos en las próximas clases, exploraremos más tipos de datos y estructuras más complejas, ampliando nuestras herramientas para resolver problemas y construir programas más sofisticados.

-----
# Cadenas y Listas

## Introducción

Vamos a empezar por la manipulación de cadenas y listas en Python. Estos conceptos son fundamentales para entender y trabajar con datos en Python.

## Cadenas

### Crear y mostrar una cadena

Comencemos creando un archivo `example.py` con el siguiente contenido:

```python
#!/usr/bin/python3  
cadena = "Mi cadena" 
print(cadena)
```
Para ejecutar este archivo desde la consola, usamos:

```sh
python3 example.py
```
**Salida esperada:**

```Copy code
Mi cadena
```


### Variables y convenciones de nombres

Podemos cambiar el contenido de la variable a una dirección IP y usar la convención de nombres `snake_case`:

```python
#!/usr/bin/python3  
ip_address = "123.45.678.90"
print(ip_address)
```

### Tipo de datos en Python

Para ver el tipo de dato de una variable, añadimos el siguiente `print`:

```python
#!/usr/bin/python3  
ip_address = "123.45.678.90" 
print(ip_address)
print(type(ip_address))
```

**Salida esperada:**

```arduino
123.45.678.90 
<class 'str'>
```


Esto muestra que la variable es del tipo `str` (cadena de texto). Si deseamos un tipo de dato numérico, podemos definir un entero:

```python
#!/usr/bin/python3  

port = 80 
print(port)
print(type(port))
```

**Salida esperada:**

```arduino
80 
<class 'int'>
```

### Números de punto flotante (float)

Los números flotantes representan números reales con una parte decimal:

```python
#!/usr/bin/python3 

number = 4.5 
print(number) 
print(type(number))
```

**Salida esperada:**

```arduino
4.5
<class 'float'>
```

### Conversión de tipos (Type Casting)

La conversión de enteros a flotantes se puede realizar así:

```python
#!/usr/bin/python3  

number = float(4) 
print(number) 
print(type(number))
```

**Salida esperada:**

```arduino
4.0 
<class 'float'>
```

## Listas

### Crear y manipular listas

Las listas permiten almacenar múltiples elementos en un solo contenedor y acceder a ellos mediante índices. Aquí hay un ejemplo básico:

```python
#!/usr/bin/python3  

my_ports = [] 
my_ports.append(22)
my_ports.append(80) 
my_ports.append(443)  

print(my_ports[0]) 
print(my_ports[1]) 
print(my_ports[2])
```

### Uso de bucles para iterar sobre listas

Podemos reducir el código anterior utilizando un bucle `for`:

```python
#!/usr/bin/python3  

my_ports = [22, 80, 443]

for port in my_ports:   
	print(f"Puerto: {port}") print(f"\n[+] La lista tiene un total de: {len(my_ports)} elementos")
```

### Agregar elementos a una lista

Podemos agregar elementos a una lista existente de varias maneras:

```python
#!/usr/bin/python3 

my_ports = [22, 80, 443] 
my_ports.extend([84, 85]) 
my_ports += [86, 87] 

my_ports = sorted(my_ports)  

for port in my_ports:   
	print(f"Puerto: {port}") 
print(f"\n[+] La lista tiene un total de: {len(my_ports)} elementos")
```

### Eliminar elementos de una lista

Para eliminar un elemento de una lista, usamos la función `del`:

```python
del my_ports[0]
```

## Practicando en la consola interactiva de Python

Podemos iniciar Python desde nuestra consola y realizar el siguiente ejercicio:

```zsh
python3
>>> mi_lista = [1, 2, 3, 4, 5] 
>>> mi_lista 
[1, 2, 3, 4, 5]
```

Acceder a elementos específicos y rangos:

```python
>>> mi_lista[:2] 
[1, 2] 

>>> mi_lista[3] 
4 

>>> mi_lista[0:3] 
[1, 2, 3]

>>> mi_lista[2:4]
[3, 4]
```

Manipulación de listas:

```python
>>> mi_lista[2:] 
[3, 4, 5]  
>>> mi_lista[-1] 
5  

>>> mi_lista.insert(2, 9)
>>> mi_lista
[1, 2, 9, 3, 4, 5] 

>>> mi_lista.pop()
5 

>>> mi_lista.index(9) 
2  

>>> for x, y in enumerate(mi_lista): 
...     print(x, y) 
...  
0 1 
1 2 
2 9 
3 3 
4 4
```

### Otros métodos útiles

Para encontrar el número más alto, el más bajo, o contar elementos repetidos:

```python
>>> max(mi_lista) 4  
>>> min(mi_lista) 1  >>> mi_lista.count(12) 0  >>> set(mi_lista) {1, 2, 3, 4, 9}  >>> sum(mi_lista) / len(mi_lista) 3.8
```

### Conclusión

Estos conceptos básicos de cadenas y listas en Python te permitirán manipular y procesar datos de manera eficiente.