
----
- TAG: #Python #FormateoDeCadenas 

-----
Python proporciona varias maneras de formatear cadenas, permitiendo insertar variables en ellas, así como controlar el espaciado, alineación y precisión de los datos mostrados. Aquí están las técnicas de formateo de cadenas que exploraremos:

**Operador % (Porcentaje)**

También conocido como “i**nterpolación de cadenas**“, este método clásico utiliza marcadores de posición como ‘**%s**‘ para cadenas, ‘**%d**‘ para enteros, o ‘**%f**‘ para números de punto flotante.

**Método format()**

Introducido en Python 2.6, permite una mayor flexibilidad y claridad. Utiliza llaves ‘**{}**‘ como marcadores de posición dentro de la cadena y puede incluir detalles sobre el formato de la salida.

**F-Strings (Literal String Interpolation)**

Disponible desde Python 3.6, los F-Strings ofrecen una forma concisa y legible de incrustar expresiones dentro de literales de cadena usando la letra ‘**f**‘ antes de las comillas de apertura y llaves para indicar dónde se insertarán las variables o expresiones.

En esta clase, nos enfocaremos en cómo utilizar cada uno de estos métodos para formatear cadenas efectivamente, así como las situaciones en las que cada uno podría ser más apropiado. Al final, tendrás las herramientas para presentar información de manera profesional en tus programas de Python.

----

# Formateo de Cadenas

## Creación de un archivo `test.py`

Empezamos creando un archivo `test.py` y practicamos un poco con los siguientes ejercicios:

```python
#!/usr/bin/python3  

name = "sk8ware" 

print("Hola, mi nombre es " + name)
```

### Resultado esperado:

```sh
Hola, mi nombre es sk8ware
```

En este caso, no encontramos ningún error ya que ambos tipos son variables. Sin embargo, si cambiáramos el tipo de texto, podríamos enfrentar problemas.

## Uso de `%s` para formateo de cadenas

Si quisiera sustituir u organizar las variables, las podríamos representar con `%s`, que significa string.

```python
#!/usr/bin/python3 

name = "sk8ware" 
rol = "lammer" 

print("Hola, mi nombre es %s y soy un %s " % (name, rol))
```

### Formateo de números decimales con `%d`

En el caso de que queramos agregar números decimales, lo podemos hacer de la siguiente manera, utilizando `%d`, que significa **decimal**:

```python
#!/usr/bin/python3 

name = "sk8ware" 
rol = "lammer" 
edad = 25  

print("Hola, mi nombre es %s y soy un %s. Actualmente tengo %d años" % (name, rol, edad))
```

Aunque también hubiese funcionado si le agregáramos la función `%s`, es mejor declararlo como decimal para evitar errores.

## Uso de `.format()` para formateo de cadenas

También tenemos otra forma de demostrar este ejemplo de una manera más simplificada utilizando el método `.format()`:

```python
#!/usr/bin/python3  

name = "sk8ware" 
rol = "lammer" 
edad = 25  

print("Hola, soy {}!".format(name))
print("Hola, soy {}! y tengo {} años".format(name, edad))
```

Se pueden agregar índices dentro de las llaves `{0}`, `{1}`, etc., para mayor control:

```python
#!/usr/bin/python3  

name = "sk8ware"
rol = "lammer" 
edad = 25  

print("Hola, soy {}!".format(name)) 
print("Hola, soy {0}! y tengo {1} años. No es broma, mi nombre real es {0}".format(name, edad))
```

## Uso de `f-strings` para formateo de cadenas

Otra forma de hacerlo es con las `f-strings`, que se logra añadiendo una `f` antes de las comillas y utilizando llaves `{}` para las variables. Esta es una de las maneras más cómodas para sustituir valores:

```python
#!/usr/bin/python3 

name = "sk8ware" 
rol = "lammer"
edad = 25   

print(f"Hola, soy {name}!")
print(f"Hola, soy {name}! y tengo {edad} años. No es broma, mi nombre real es {name}")
```