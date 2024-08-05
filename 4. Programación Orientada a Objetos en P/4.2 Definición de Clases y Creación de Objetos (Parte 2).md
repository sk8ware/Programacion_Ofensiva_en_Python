
---
- TAG: #Python #POO #Clases #Objetos 
----

Dentro del paradigma de la Programación Orientada a Objetos en Python, existen conceptos avanzados como los decoradores, métodos de clase y métodos estáticos que enriquecen y expanden las posibilidades de cómo interactuamos con las clases y sus instancias.

**Decoradores**

Los decoradores son una herramienta poderosa en Python que permite modificar el comportamiento de una función o método. Funcionan como “envoltorios”, que agregan funcionalidad antes y después del método o función decorada, sin cambiar su código fuente. En POO, los decoradores son frecuentemente utilizados para agregar funcionalidades de manera dinámica a los métodos, como la sincronización de hilos, la memorización de resultados o la verificación de permisos.

**Métodos de Clase**

Un método de clase es un método que está ligado a la clase y no a una instancia de la clase. Esto significa que el método puede ser llamado sobre la clase misma, en lugar de sobre un objeto de la clase. Se definen utilizando el decorador ‘**@classmethod**‘ y su primer argumento es siempre una referencia a la clase, convencionalmente llamada ‘**cls**‘. Los métodos de clase son utilizados a menudo para definir métodos “factory” que pueden crear instancias de la clase de diferentes maneras.

**Métodos Estáticos**

Los métodos estáticos, definidos con el decorador ‘**@staticmethod**‘, no reciben una referencia implícita ni a la instancia (self) ni a la clase (cls). Son básicamente como funciones regulares, pero pertenecen al espacio de nombres de la clase. Son útiles cuando queremos realizar alguna funcionalidad que está relacionada con la clase, pero que no requiere acceder a la instancia o a los atributos de la clase.

Estos elementos de la POO en Python nos permiten crear abstracciones más claras y mantener el código
organizado, modular y flexible, facilitando el mantenimiento y la extensibilidad del software.

----
# Clases y objetos (2/2)
## Ejemplo de la Clase Rectángulo

Este código define una clase `Rectangulo` y muestra cómo crear instancias de la clase, calcular el área y comparar dos rectángulos.

```python
#!/usr/bin/python3

class Rectangulo:

	def __init__(self, ancho, alto):
		self.ancho = ancho
		self.alto = alto 

	@property
	def area (self): # Rectangulo.area(rect1)
		
		return self.ancho *self.alto 
	
	def __str__(self):
		
		return f"\n[+] Propiedades del rectángulo: [Ancho: {self.ancho}][Alto: {self.alto}]"
		
	def __eq__(self, otro):
		
		return self.ancho == otro.ancho and self.alto == otro.alto

rect1 = Rectangulo(20, 80)
rect2 = Rectangulo(29, 10)

print(rect1)
print(f"\n[+] El área es {rect1.area}")
print(f"\n[+] ¿Son iguales? -> {rect1 == rect2}")

```

- **Definición de la clase `Rectangulo`:**
    
    - Se define una clase llamada `Rectangulo`, que representa un rectángulo.
- **Inicialización (`__init__`):**
    
    - La clase tiene un método especial `__init__` que se llama cuando se crea un nuevo objeto de la clase. Este método inicializa los atributos `ancho` y `alto` del rectángulo con los valores pasados como argumentos al crear una instancia de la clase.
- **Propiedad de solo lectura (`@property`):**
    
    - Se define una propiedad llamada `area`, que calcula y devuelve el área del rectángulo multiplicando su ancho por su alto. Esto se hace utilizando el decorador `@property`, lo que permite acceder a la función `area` como si fuera un atributo, sin necesidad de llamarla con paréntesis.
- **Método `__str__`:**
    
    - Se define el método especial `__str__`, que devuelve una representación legible del objeto en forma de cadena de texto. En este caso, devuelve una cadena que muestra las propiedades del rectángulo, incluyendo su ancho y alto.
- **Método de igualdad (`__eq__`):**
    
    - Se define el método especial `__eq__`, que se utiliza para determinar si dos objetos de la clase `Rectangulo` son iguales. En este caso, compara tanto el ancho como el alto de dos rectángulos y devuelve `True` si ambos son iguales en ambas dimensiones, y `False` en caso contrario.
- **Creación de instancias:**
    
    - Se crean dos instancias de la clase `Rectangulo` (`rect1` y `rect2`) con diferentes dimensiones.
- **Impresión:**
    
    - Se imprime la representación de los rectángulos utilizando el método `__str__`.
    - Se imprime el área del `rect1` utilizando la propiedad `area`.
    - Se imprime si los rectángulos `rect1` y `rect2` son iguales o no utilizando el método de igualdad `__eq__`.
- ---
# Método Estático

Ahora mostraremos un ejemplo que utiliza un método estático en la clase `Libro`.

```python
#!/usr/bin/python3

class Libro:

	def __init__(self, titulo, autor, precio):
		
		self.titulo = titulo
		self.autor = autor
		self.precio = precio

	@staticmethod # Decoradores
	def es_bestseller(total_ventas): # Libro.es_bestseller(mi_libro, total_ventas)
		
		return total_ventas > 5000

mi_libro = Libro("¿Cómo ser un Lammer de los de verdad", "Anthony López", 17.5)
print(Libro.es_bestseller(8000))
```

- **Definición de la clase `Libro`:**
    
    - Se define una clase llamada `Libro`, que representa un libro.
- **Inicialización (`__init__`):**
    
    - La clase tiene un método especial `__init__` que se llama cuando se crea un nuevo objeto de la clase. Este método inicializa los atributos `titulo`, `autor` y `precio` del libro con los valores pasados como argumentos al crear una instancia de la clase.
- **Método estático (`@staticmethod`):**
    
    - Se define un método estático llamado `es_bestseller`. Un método estático se asocia con la clase en lugar de con instancias particulares de la clase. No recibe automáticamente una referencia a la instancia o a la clase como primer argumento, por lo que se utiliza el decorador `@staticmethod` para indicar que es un método estático.
    - Este método toma un parámetro `total_ventas` que representa el número total de ventas del libro y devuelve `True` si el número total de ventas es mayor que 5000, indicando que el libro es un bestseller, y `False` en caso contrario.
- **Creación de una instancia de la clase `Libro`:**
    
    - Se crea una instancia de la clase `Libro` llamada `mi_libro` con un título, un autor y un precio específicos.
- **Uso del método estático:**
    
    - Se llama al método estático `es_bestseller` de la clase `Libro`, pasando el número total de ventas (en este caso, 8000) como argumento. Esto determina si el libro es un bestseller basado en el número de ventas y devuelve el resultado.

-----
# Instancias con Bestseller

Aquí mostramos cómo el método estático puede interactuar con atributos de una instancia.

```python
#!/us/bin/python3

class Libro:
	
	def __init__(self, titulo, autor, precio, bestseller_value=5000):
	
		self.titulo = titulo
		self.autor = autor 
		self.precio = precio
		self.bestseller_value = bestseller_value

	@staticmethod # Decoradores
	def es_bestseller(instancia, total_ventas): # Libro.es_bestseller(mi_libro, total_ventas)
		
		return total_ventas > instancia.bestseller_value

mi_libro = Libro("¿C+omo ser un Lammer de los de verdad?", "Anthony López", 17.5)
print(Libro.es_bestseller(mi_libro, 10000))
```

- **Definición de la clase `Libro`:**
    
    - Se define una clase llamada `Libro`, que representa un libro.
- **Inicialización (`__init__`):**
    
    - La clase tiene un método especial `__init__` que se llama cuando se crea un nuevo objeto de la clase. Este método inicializa los atributos `titulo`, `autor`, `precio` y `bestseller_value` del libro con los valores pasados como argumentos al crear una instancia de la clase. `bestseller_value` tiene un valor predeterminado de 5000, pero puede ser modificado al instanciar la clase.
- **Método estático (`@staticmethod`):**
    
    - Se define un método estático llamado `es_bestseller`. Al igual que en el ejemplo anterior, es un método estático que toma dos parámetros: `instancia` y `total_ventas`.
    - Este método determina si un libro es un bestseller comparando el número total de ventas (`total_ventas`) con el valor de bestseller (`bestseller_value`) asociado a la instancia del libro (`instancia`).
- **Creación de una instancia de la clase `Libro`:**
    
    - Se crea una instancia de la clase `Libro` llamada `mi_libro` con un título, un autor y un precio específicos. En este caso, el valor de `bestseller_value` se mantiene en el valor predeterminado de 5000.
- **Uso del método estático:**
    
    - Se llama al método estático `es_bestseller` de la clase `Libro`, pasando la instancia `mi_libro` y el número total de ventas (en este caso, 10000) como argumentos. Esto determina si el libro es un bestseller basado en el número de ventas y el valor de bestseller asociado a la instancia, y devuelve el resultado.

----

# Método de Clase con IVA

Vamos a complicar un poco más el ejercicio añadiéndole el **IVA**.

  ```python
  #!/usr/bin/python3

class Libro:

	IVA = 0.21
	
	def __init__(self, titulo, autor, precio):
		
		self.titulo = titulo
		self.autor = autor
		self.precio = precio
		
	@staticmethod # Decoradores
	def es_bestseller(total_ventas): # Libro.es_bestseller(mi_libro, total_ventas)
		return total_ventas > 5000
		
	@classmethod # Decoradores
	def precio_con_iva(cls, precio):
		
		return precio + precio * cls.IVA
		
class LibroDigital(Libro):
		
	IVA = 0.10
		
mi_libro = Libro("¿Cómo ser un Lammer de los de verdad?", "Anthony López", 17.5)
mi_libro_digital = LibroDigital("Iniciación al Lammer", "Anthony López", 17.5)

print(f"\n[+] El precio del libro con IVA incluido es de {LibroDigital.precio_con_iva(mi_libro.precio)}")
print(f"\n[+] El precio del libro digital con IVA incluido es de {LibroDigital.precio_con_iva(mi_libro_digital.precio)}")
```

Este código define dos clases, `Libro` y `LibroDigital`, utilizando conceptos avanzados de Python como variables de clase, métodos estáticos, métodos de clase y herencia. A continuación, te explico cada parte del código:

```python
#!/usr/bin/python3
```

Esta línea es una shebang que indica al sistema operativo que use el intérprete de Python 3 para ejecutar este script.

```python
class Libro:
```

Define una nueva clase llamada `Libro`.

```python
	IVA = 0.21
```

Esta es una variable de clase que representa el IVA (Impuesto al Valor Agregado) del libro, establecida en 21%.

```python
	def __init__(self, titulo, autor, precio):         
		self.titulo = titulo         
		self.autor = autor         
		self.precio = precio
```

Este es el método constructor `__init__`. Se ejecuta automáticamente cuando se crea una nueva instancia de `Libro`. Inicializa los atributos del libro:

- `titulo`: el título del libro.
- `autor`: el autor del libro.
- `precio`: el precio del libro.

```python
	@staticmethod     
	def es_bestseller(total_ventas):         
		return total_ventas > 5000
```

Este es un método estático, marcado con el decorador `@staticmethod`. No necesita una instancia de la clase para ser llamado y verifica si un libro es un bestseller basándose en el total de ventas. Retorna `True` si las ventas son mayores a 5000 y `False` en caso contrario.

```python
	@classmethod     
	def precio_con_iva(cls, precio):         
		return precio + precio * cls.IVA
```

Este es un método de clase, marcado con el decorador `@classmethod`. Toma como parámetro la clase (`cls`) en lugar de una instancia y calcula el precio con IVA incluido, usando la variable de clase `IVA`.

```python
class LibroDigital(Libro):     
	IVA = 0.10
```

Define una nueva clase `LibroDigital` que hereda de `Libro`. Esta clase sobrescribe la variable de clase `IVA`, estableciéndola en 10%.

```python
mi_libro = Libro("¿Cómo ser un Lammer de los de verdad?", "Anthony López", 17.5) 
mi_libro_digital = LibroDigital("Iniciación al Lammer", "Anthony López", 17.5)
```

Se crean dos instancias:

- `mi_libro`, una instancia de `Libro` con el título "¿Cómo ser un Lammer de los de verdad?", autor "Anthony López", y precio 17.5.
- `mi_libro_digital`, una instancia de `LibroDigital` con el título "Iniciación al Lammer", autor "Anthony López", y precio 17.5.

```python
print(f"\n[+] El precio del libro con IVA incluido es de {LibroDigital.precio_con_iva(mi_libro.precio)}") 
print(f"\n[+] El precio del libro digital con IVA incluido es de {LibroDigital.precio_con_iva(mi_libro_digital.precio)}")
```

Estas líneas llaman al método de clase `precio_con_iva` para cada instancia, calculando el precio con IVA incluido y luego imprimiendo el resultado. Notar que se llama `LibroDigital.precio_con_iva` para ambos, lo que es relevante ya que `LibroDigital` tiene un IVA diferente al de `Libro`.

Cuando ejecutas este código, el resultado será:

```zsh
[+] El precio del libro con IVA incluido es de 19.25 
[+] El precio del libro digital con IVA incluido es de 19.25
```

El precio con IVA para el libro y el libro digital es calculado utilizando el método de clase `precio_con_iva`. Aunque en ambos casos se usa `LibroDigital.precio_con_iva`, el IVA aplicado será el correspondiente a la clase `LibroDigital`, que es 10%.