
----
- TAG: #DIFERENCIAS #PYTHON2 #PYTHON3 #PIP2 #PIP3
----
Python 2 y Python 3 son dos versiones del lenguaje de programación Python, cada una con sus propias características y diferencias clave. PIP2 y PIP3 son las herramientas de gestión de paquetes correspondientes a cada versión, utilizadas para instalar y administrar bibliotecas y dependencias.

**Python 2 vs Python 3:**

- **Sintaxis de print**: En Python 2, ‘print’ es una declaración, mientras que en Python 3, ‘print()’ es una función, lo que requiere el uso de paréntesis.
- **División de enteros**: Python 2 realiza una división entera por defecto, mientras que Python 3 realiza una división real (flotante) por defecto.
- **Unicode**: Python 3 usa Unicode (texto) como tipo de dato por defecto para representar cadenas, mientras que Python 2 utiliza ASCII.
- **Librerías**: Muchas librerías populares de Python 2 han sido actualizadas o reescritas para Python 3, con mejoras y nuevas funcionalidades.
- **Soporte**: Python 2 llegó al final de su vida útil en 2020, lo que significa que ya no recibe actualizaciones, ni siquiera para correcciones de seguridad.

**PIP2 vs PIP3:**

- **Gestión de paquetes**: PIP2 y PIP3 son herramientas que permiten instalar paquetes para Python 2 y Python 3, respectivamente. Es importante usar la versión correcta para garantizar la compatibilidad con la versión de Python que estés utilizando.
- **Comandos de instalación**: El uso de pip o pip3 antes de un comando determina si el paquete se instalará en Python 2 o Python 3. Algunos sistemas operativos pueden requerir especificar pip2 o pip3 explícitamente para evitar ambigüedades.
- **Ambientes virtuales**: Es una buena práctica usar ambientes virtuales para mantener separadas las dependencias de proyectos específicos y evitar conflictos entre versiones de paquetes para Python 2 y Python 3.

La transición de Python 2 a Python 3 ha sido significativa en la comunidad de desarrolladores de Python, y es fundamental que los programadores comprendan las diferencias y sepan cómo trabajar con ambas versiones del lenguaje y sus herramientas asociadas.

----
# Instalación de Python

Como me encuentro en una máquina Linux, la instalación la vamos a realizar por consola. Podemos empezar haciéndolo de la siguiente manera como usuarios **root**:

```
apt install python2 python3
```

¿Por qué se recomienda tener instalada la versión **python2**? Imaginen que están auditando un servicio con una versión vulnerable que han encontrado e investigando en **GitHub** encuentran un **exploit** para explotar este servicio. Imaginen que ese **exploit** fue configurado hace 8 años en python2 y no en python3. A nivel de sintaxis, cambian ciertas cosas, así que a veces va bien tenerlo instalado. A continuación, doy dos ejemplos simples:

**Python2**:

```python2
print "Hola"
```

Aquí, nos representa como una declaración y no como función como pasa en python3:

**Python3**:

```python3
print("Hola")
```

En python2, cuando se emplean números enteros, normalmente se obtiene como resultado un número entero, a diferencia de **python3** que en el resultado de una división, por ejemplo, nos da un _float_ (número decimal).

**Python2**:

```python
>>> 2 / 3 
0 
>>> type(2 / 3) 
<type 'int'> 
```

**Python3**:

```python
>>> 5 / 3 
1.66666666667 
>>> type(5 / 3) 
<class 'float'>
```

Hay muchos más ejemplos entre python2 y python3. Por ejemplo, **Python2** emplea ASCII mientras que **Python3** emplea UNICODE. Esto hace que trabajar con caracteres no ASCII en python3 sea mucho más sencillo. Python3 cuenta con muchas mejoras en su biblioteca estándar, lo que hace que el código sea mucho más eficiente y fácil de leer.

# Instalación y Explicación de PIP2 y PIP3

La palabra pip viene de (PIP INSTALLS PACKAGES), una herramienta que nos permite instalar y administrar paquetes de software adicionales que no suelen estar incluidos en la biblioteca estándar de Python. En Linux, podemos utilizar **pip** de la siguiente manera:

```php
pip install <paquete>
```

Luego, los paquetes se pueden desinstalar o gestionar de otras formas.

## PIP2

Nos referimos a la herramienta que nos permite instalar y administrar paquetes para python2. Recuerden que desde el 2020 _python2_ ya no tiene actualización ni mantenimiento, por lo que no es conveniente usar esta herramienta. Para **python2**, en su momento, se instalaba de la misma manera que python3, pero ahora hay que realizarlo de la siguiente manera:

```shell
wget https://bootstrap.pypa.io/pip/2.7/get-pip.py python2 get-pip.py
```

Aunque parece que al día de hoy ya no existen los paquetes para la instalación de pip2.

## PIP3

Nos referimos a la herramienta que nos permite instalar y administrar paquetes para python3. Para poder instalar **pip3** podemos realizar lo siguiente:

```
sudo apt install python3-pip
```
---

Ahora, para instalar paquetes con pip, lo podemos hacer de la siguiente manera:

`pip3 install pwntools`

De igual manera para **pip2**.

Ahora, si ingresamos al intérprete de python3:

python

`>>> import pwn`

De igual forma, para pip2 a veces suele mostrar error y hay que instalar otra librería adicional.