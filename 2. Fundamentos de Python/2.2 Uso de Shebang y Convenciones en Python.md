
----
- TAG: #Shebang #Python #Scripts #Convenciones #Programación
----
En el desarrollo con Python, el shebang y los convenios de codificación son aspectos importantes que facilitan la escritura de scripts claros y portables.

**Shebang en Python:**

El shebang es una línea que se incluye al principio de un script ejecutable para indicar al sistema operativo con qué intérprete debe ejecutarse el archivo. En los scripts de Python, el shebang común es:

- **#!/usr/bin/env python3**

Esta línea le dice al sistema que utilice el entorno (**env**) para encontrar el intérprete de Python 3 y ejecutar el script con él. Es fundamental para asegurar que el script se ejecute con Python 3 en sistemas donde Python 2 todavía está presente.

**Convenios en Python:**

Los convenios de codificación son un conjunto de recomendaciones que guían a los desarrolladores de Python para escribir código claro y consistente. El más conocido es ‘**PEP 8**‘, que abarca:

- **Nombres de Variables**: Utilizar ‘**lower_case_with_underscores**‘ para nombres de variables y funciones, ‘**UPPER_CASE_WITH_UNDERSCORES**‘ para constantes, y ‘**CamelCase**‘ para clases.
- **Longitud de Línea**: Limitar las líneas a 79 caracteres para código y 72 para comentarios y docstrings.
- **Indentación**: Usar 4 espacios por nivel de indentación.
- **Espacios en Blanco**: Seguir las prácticas recomendadas sobre el uso de espacios en blanco, como no incluir espacios adicionales en listas, funciones y argumentos de funciones.
- **Importaciones**: Las importaciones deben estar en líneas separadas y agrupadas en el siguiente orden: módulos de la biblioteca estándar, módulos de terceros y luego módulos locales.
- **Compatibilidad entre Python 2 y 3**: Aunque Python 2 ha llegado al final de su vida útil, algunos convenios pueden seguirse para mantener la compatibilidad.

El cumplimiento de estos convenios no solo mejora la legibilidad del código, sino que también facilita la colaboración entre desarrolladores y el mantenimiento a largo plazo del software.

El uso adecuado del shebang y la adhesión a los convenios de Python son señales de un desarrollador cuidadoso y profesional. Integrar estos aspectos en tus prácticas de codificación es crucial para el desarrollo de software efectivo y eficiente en Python.

---

# Creación y Ejecución de Scripts en Python

## Creación del Script

En este apartado, vamos a crear un script de Python en nuestra máquina Linux llamado `test.py`:

```sh
nvim test.py
```

Al crear el script, es importante incluir el hashbang o shebang para especificar el intérprete de Python que vamos a usar. Podemos utilizar `#!/usr/bin/python3` si estamos seguros de la ruta del intérprete, o `#!/usr/bin/env python3` para mayor flexibilidad:

```sh
#!/usr/bin/env python3 
print("hola")
```

Para ejecutar el script, utilizamos:

```sh
python3 test.py
```

También podemos hacer que el script sea ejecutable con `chmod +x test.py` y ejecutarlo directamente:

```sh
./test.py
```

Es importante tener en cuenta el shebang para la ejecución directa. Sin embargo, al usar `python3 test.py`, la instrucción se entiende y se ejecutará en consola sin problemas.

## Implementación de un Módulo Principal

Un buen consejo es implementar un módulo principal para distinguir cuándo el script se está ejecutando directamente o importado como un módulo:

```python
#!/usr/bin/env python3 
if __name__ == '__main__':     
	print("Hola, soy el módulo principal") 
else:
	print("No soy el módulo principal")`
```

Todos los archivos de Python son módulos, y podemos importarlos en otros scripts. Creamos un nuevo archivo llamado `ejemplo.py`:

```sh
nvim ejemplo.py
```

Ingresamos el siguiente contenido:

```python
import test
```

Probamos ambos scripts para ver los diferentes mensajes de salida:

```sh
python3 test.py
```

**Salida:**

```
Hola, soy el módulo principal`
```

```sh
python3 ejemplo.py
```

**Salida:**

```yaml
No soy el módulo principal
```

Esto nos ayuda a estructurar mejor el código y saber cuándo un script se ejecuta directamente o se usa como módulo.

## Nomenclatura y Convenciones en Python

### Funciones

Para nombrar funciones, utilizamos el estilo `snake_case`, donde todas las letras son minúsculas y las palabras se separan con guiones bajos:

```python
python3 #!/usr/bin/env python3 
# SCREAMING_SNAKE_CASE 
VERSION_API = 1 
URL_API = "https://hack4u.io"
```
### Clases
# lowerCamelCase
Voy a dar un pequeño ejemplo a continuación implementando `def` que significa un `lower camel case`, se compone que en la primera palabra del nombre entero va todo en minusculas y por el resto de palabra se tiene que componer de la primera palabra en mayuscula

```python
#!/usr/bin/env python3 

# lowerCamelCase 

def comprobacionEstadoApi(): 

if __name__ == '__main__': 
	print("Hola, soy el módulo principal") 
else:
	print("No soy el modulo principal")
```

# UpperCamelCase

Para las clases, utilizamos el estilo `UpperCamelCase`, donde cada palabra comienza con una letra mayúscula:

```python 
#!/usr/bin/env python3 

# UpperCamelCase class

TwitterApi(): 

if __name__ == '__main__': 
	print("Hola, soy el módulo principal")
else:
	print("No soy el modulo principal")
```
### Constantes
# SCREAMING_SNAKE_CASE

Para las constantes, usamos el estilo `SCREAMING_SNAKE_CASE`, donde todas las letras son mayúsculas y las palabras se separan con guiones bajos:

```python
#!/usr/bin/env python3 

# SCREAMING_SNAKE_CASE 

VERSION_API = 1 
URL_API = "https://hack4u.io" 

if __name__ == '__main__':
	print("Hola, soy el módulo principal") 
else: 
	print("No soy el modulo principal") 
```

### Variables Protegidas y Privadas

Para variables protegidas (no públicas), utilizamos un guion bajo al inicio del nombre:

```python
_protegido = "Estoy Protegido"
```

Para variables privadas, utilizamos dos guiones bajos:

```python
__privado = "Estoy Protegido"
```

### Recomendaciones

La guía de estilo para la programación en Python, conocida como `PEP8`, establece convenciones para mejorar la legibilidad del código. Evita usar `l` minúscula, `O` mayúscula y `I`, ya que pueden confundirse fácilmente. Aquí tienes un ejemplo de una función siguiendo `PEP8`:

```python
def comprobar_estado_api():
```
