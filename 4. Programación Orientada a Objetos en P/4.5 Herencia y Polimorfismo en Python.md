
---
- TAG: #Herencia #Polimorfismo
----

La herencia y el polimorfismo son conceptos fundamentales en la programación orientada a objetos que permiten la creación de una estructura de clases flexible y reutilizable.

**Herencia**

Es un principio de la POO que permite a una clase heredar atributos y métodos de otra clase, conocida como su clase base o superclase. La herencia facilita la reutilización de código y la creación de una jerarquía de clases. Las subclases heredan las características de la superclase, lo que permite que se especialicen o modifiquen comportamientos existentes.

----
# Herencia

Para explicarlo de mejor manera vamos con la practica con unos pequeños ejemplos

1. Creamos un archivo nvim `exercise.py`
2. Creamos un ejemplo de clase utilizando la clase `Animal`

```python
#!/usr/bin/python3 

class Animal:  # Definición de una clase llamada Animal
    def __init__(self, nombre):  # Constructor de la clase que inicializa el nombre del animal
        self.nombre = nombre  # Asigna el nombre pasado al crear el objeto a la variable de instancia

    def hablar(self):  # Método que hace que el animal "hable"
        print(f"{self.nombre} dice ¡Miau!")  # Imprime el nombre del animal seguido de "dice ¡Miau!"

gato = Animal("Mitis")  # Crea un nuevo objeto de la clase Animal con el nombre "Mitis"
gato.hablar()  # Llama al método hablar del objeto gato


```
3. Creamos el concepto de la herencia, solemos utilizar `pass` para definir o entender que se debe crear las subclases

O podemos utilizar `raise` para permitir salir un mensaje al momento que nos aparezca un error y el desarrollador pueda entender el error

```python
#!/usr/bin/python3 

class Animal:  # Definición de una clase base llamada Animal
    def __init__(self, nombre):  # Constructor de la clase que inicializa el nombre del animal
        self.nombre = nombre  # Asigna el nombre pasado al crear el objeto a la variable de instancia

    def hablar(self):  # Método que debe ser implementado por las subclases
        raise NotImplementedError("Las subclases definidas deben implementar este método")  # Lanza un error si no se implementa en una subclase

class Gato(Animal):  # Definición de una clase llamada Gato que hereda de Animal
    def hablar(self):  # Implementación del método hablar para la clase Gato
        return f"{self.nombre} dice ¡Miau!"  # Devuelve un mensaje con el nombre del gato y "dice ¡Miau!"

class Perro(Animal):  # Definición de una clase llamada Perro que hereda de Animal
    def hablar(self):  # Implementación del método hablar para la clase Perro
        return f"{self.nombre} dice ¡Guau!"  # Devuelve un mensaje con el nombre del perro y "dice ¡Guau!"

gato = Gato("Mitis")  # Crea un nuevo objeto de la clase Gato con el nombre "Mitis"
perro = Perro("Negra")  # Crea un nuevo objeto de la clase Perro con el nombre "Negra"
gato_dos = Animal("Matrix")  # Crea un nuevo objeto de la clase Animal con el nombre "Matrix"

print(gato.hablar())  # Llama al método hablar del objeto gato y lo imprime
print(perro.hablar())  # Llama al método hablar del objeto perro y lo imprime
print(gato_dos.hablar())  # Llama al método hablar del objeto gato_dos y lo imprime (esto lanzará un error)

```

### Resumen

Este código define una clase base `Animal` que tiene un método `hablar` que debe ser implementado por las subclases. Luego define dos subclases, `Gato` y `Perro`, que implementan el método `hablar` para devolver mensajes específicos para gatos y perros. Se crean objetos de estas clases y se llama al método `hablar` para mostrar los mensajes. Intentar llamar al método `hablar` en un objeto de la clase `Animal` directamente lanzará un error porque no está implementado en `Animal`.

----

# Polimorfismo

**Polimorfismo**

Este concepto se refiere a la habilidad de objetos de diferentes clases de ser tratados como instancias de una clase común. El polimorfismo permite que una función o método interactúe con objetos de diferentes clases y los trate como si fueran del mismo tipo, siempre y cuando compartan la misma interfaz o método. Esto significa que el mismo método puede comportarse de manera diferente en distintas clases, un concepto conocido como sobrecarga de métodos.

Ambos, la herencia y el polimorfismo, son piedras angulares de la POO y son ampliamente utilizados para diseñar sistemas que son fácilmente extensibles y mantenibles.

En esta clase, exploraremos cómo implementar herencia en Python y cómo se puede aprovechar el polimorfismo para escribir código más general y potente. Estos conceptos nos ayudarán a entender mejor cómo construir jerarquías de clases y cómo los diferentes objetos pueden interactuar entre sí de manera flexible.
Tambien lo pudimos haberlo hecho de otra manera y es aqui cuando entra en juego el **Polimorfismo** 

- Fuera de las clases creamos una función llamada `hacer_hablar`
- Va a recibir un objeto esta funcón 
- Creamos los objetos :
	- `hacer_hablar(gato)`
	- `hacer_hablar(perro)`
- Hacemos un print dentro de la función donde desconoce el tipo de animal pero de manera dinámica llama al objeto de ese método correspondiente, gracias a ser subclases de las instancias que heredan de la "clase padre"(Animal), automaticamente al ingresar al método `hanlar` sabra que listar por consola 

```python
#!/usr/bin/python3  

class Animal:  # Definición de una clase base llamada Animal
    def __init__(self, nombre):  # Constructor de la clase que inicializa el nombre del animal
        self.nombre = nombre  # Asigna el nombre pasado al crear el objeto a la variable de instancia

    def hablar(self):  # Método que debe ser implementado por las subclases
        raise NotImplementedError("Las subclases definidas deben implementar este método")  # Lanza un error si no se implementa en una subclase

class Gato(Animal):  # Definición de una clase llamada Gato que hereda de Animal
    def hablar(self):  # Implementación del método hablar para la clase Gato
        return f"¡Miau!"  # Devuelve "¡Miau!" cuando se llama a hablar

class Perro(Animal):  # Definición de una clase llamada Perro que hereda de Animal
    def hablar(self):  # Implementación del método hablar para la clase Perro
        return f"¡Guau!"  # Devuelve "¡Guau!" cuando se llama a hablar

def hacer_hablar(objeto):  # Definición de una función que toma un objeto como argumento
    print(f"{objeto.nombre} dice {objeto.hablar()}")  # Imprime el nombre del objeto y lo que dice

gato = Gato("Mitis")  # Crea un nuevo objeto de la clase Gato con el nombre "Mitis"
perro = Perro("Negra")  # Crea un nuevo objeto de la clase Perro con el nombre "Negra"

hacer_hablar(gato)  # Llama a la función hacer_hablar con el objeto gato
hacer_hablar(perro)  # Llama a la función hacer_hablar con el objeto perro

```

### Resumen

Este código define una clase base `Animal` que tiene un método `hablar` que debe ser implementado por las subclases. Luego define dos subclases, `Gato` y `Perro`, que implementan el método `hablar` para devolver los sonidos que hacen. La función `hacer_hablar` toma un objeto de cualquier subclase de `Animal` y muestra el nombre del animal y el sonido que hace. Al final, crea un gato llamado "Mitis" y un perro llamado "Negra", y hace que ambos hablen usando la función `hacer_hablar`.

----
# Reforzando con ejercicios

## Concepto Herencia

Vamos a poner en practica otro ejemplo para reforzar lo indicado 
- Creamos una clase llamada **Automóvil**
- Creamos el constructor con `self` y las `marca` y `modelo`
- Creamos las igualdades con:
	- `self.marca` = marca
	- `self.modelo` = modelo
- Creamos el método `def describir(self):`
- Para llamar al método **Describir** y ver por consola añadimos el `{self.marca}` y el `{self.modelo}`
- Creamos un objeto que represente a la instancia de la clase automóvil y les asignamos los nombres "Toyota", "Corolla"
- Creamos otro objeto que se llame moto con sus respectivas propiedades
- Tratamos de demostrar las propiedades de ese coche con `print` al final
- Si queremos que nos muestre por vehículo en especifico como moto o coche hay que crear unas **subaclases** que heredan de la **clase** **Automóvil** 
- Creamos una instancia de la subclase en el objeto `Coche"Toyota", "Corolla")` y de igual manera para `Moto`
- Creamos el método **Describir** e indicamos la `self.marca` y el `self.modelo`

```python
#!/usr/bin/python3  

class Automovil:  # Definición de una clase base llamada Automovil
    def __init__(self, marca, modelo):  # Constructor de la clase que inicializa la marca y el modelo del automóvil
        self.marca = marca  # Asigna la marca pasada al crear el objeto a la variable de instancia
        self.modelo = modelo  # Asigna el modelo pasado al crear el objeto a la variable de instancia

    def describir(self):  # Método que devuelve una descripción del automóvil
        return f"Vehiculo: {self.marca}, {self.modelo}."  # Devuelve una cadena con la marca y el modelo del automóvil

class Coche(Automovil):  # Definición de una clase llamada Coche que hereda de Automovil
    def describir(self):  # Implementación del método describir para la clase Coche
        return f"Coche: {self.marca} {self.modelo}"  # Devuelve una cadena con la marca y el modelo del coche

class Moto(Automovil):  # Definición de una clase llamada Moto que hereda de Automovil
    def describir(self):  # Implementación del método describir para la clase Moto
        return f"Moto: {self.marca} {self.modelo}"  # Devuelve una cadena con la marca y el modelo de la moto

coche = Coche("Toyota", "Corolla")  # Crea un nuevo objeto de la clase Coche con la marca "Toyota" y el modelo "Corolla"
moto = Moto("Honda", "CBR")  # Crea un nuevo objeto de la clase Moto con la marca "Honda" y el modelo "CBR"

print(coche.describir())  # Llama al método describir del objeto coche y lo imprime
print(moto.describir())  # Llama al método describir del objeto moto y lo imprime

```

### Resumen

Este código define una clase base `Automovil` que tiene un método `describir` para devolver una descripción del vehículo. Luego define dos subclases, `Coche` y `Moto`, que implementan su propia versión del método `describir` para devolver descripciones específicas para coches y motos. Se crean objetos de estas clases con sus respectivas marcas y modelos, y se imprime la descripción de cada uno.

## Concepto de Polimorfismo

- Lo primero que deberíamos hacer es borrar los `print` del final 
- Creamos una función que se llame `def describir_vehiculo(vehiculo):`
- Creamos una función antes que el metodo, asi que antes de `coche.describir()` sería :
	- `describir_vehiculo(coche)`
	- `describir_vehiculo(moto)`

ejemplo: 

```python
#!/usr/bin/python3  

class Automovil:  # Definición de una clase base llamada Automovil
    def __init__(self, marca, modelo):  # Constructor de la clase que inicializa la marca y el modelo del automóvil
        self.marca = marca  # Asigna la marca pasada al crear el objeto a la variable de instancia
        self.modelo = modelo  # Asigna el modelo pasado al crear el objeto a la variable de instancia

    def describir(self):  # Método que devuelve una descripción del automóvil
        return f"Vehiculo: {self.marca}, {self.modelo}."  # Devuelve una cadena con la marca y el modelo del automóvil

class Coche(Automovil):  # Definición de una clase llamada Coche que hereda de Automovil
    def describir(self):  # Implementación del método describir para la clase Coche
        return f"Coche: {self.marca} {self.modelo}"  # Devuelve una cadena con la marca y el modelo del coche

class Moto(Automovil):  # Definición de una clase llamada Moto que hereda de Automovil
    def describir(self):  # Implementación del método describir para la clase Moto
        return f"Moto: {self.marca} {self.modelo}"  # Devuelve una cadena con la marca y el modelo de la moto

def describir_vehiculo(vehiculo):  # Definición de una función que toma un objeto como argumento
    print(vehiculo.describir())  # Llama al método describir del objeto y lo imprime

coche = Coche("Toyota", "Corolla")  # Crea un nuevo objeto de la clase Coche con la marca "Toyota" y el modelo "Corolla"
moto = Moto("Honda", "CBR")  # Crea un nuevo objeto de la clase Moto con la marca "Honda" y el modelo "CBR"

print(coche.describir())  # Llama al método describir del objeto coche y lo imprime
print(moto.describir())  # Llama al método describir del objeto moto y lo imprime

```

### Resumen

Este código define una clase base `Automovil` que tiene un método `describir` para devolver una descripción del vehículo. Luego define dos subclases, `Coche` y `Moto`, que implementan su propia versión del método `describir` para devolver descripciones específicas para coches y motos. Se crean objetos de estas clases con sus respectivas marcas y modelos, y se imprime la descripción de cada uno. La función `describir_vehiculo` se puede usar para describir cualquier objeto que tenga un método `describir`.

 -----
 # Jugando con polimorfismo
 
Ahora vamos a estar viendo otro ejemplo practico 
- Creamos una clase llamada `Dispositivo:`
- Creamos un constructor con `__init__(self, modelo)`
- Creamos una función llamada `self.modelo = modelo`
- Vamos a crear un método abstracto, para documentar la intención, ya que es necesario para las subclases existentes creando una funcion llamada `def escamear_vulnerabilidades(self):`
- A continuación le implementamos un `raise` ya que es un método abstracto
- Creamos una clase `Ordenador` que herada de la clase `Dispositivos`
- Creamos la subclase con el metodo de `escanear_vulnerabilidades`
- Hacemos que nos retorne un mensaje con `return`
- Creamos otra clase que podriamos representar como `router` y hereda de la `Dispositivo`
- Creamos su propio metodo de escanear vulnerabilidades
- Luego creamos otra clase `TelefonoMovil` que tambien erada de la clase `Dispositivo`
- Creamos su propio metodo de escanear vulnerabilidades
- Podemos ir creando nuestros objetos al final de todo con el nombre `pc`, `router` y `movil`
- Creamos una función fuera de todas las clases que va a ser la que se va a encargar empleando polimorfismo, devolviendome la cadena correspondiente a la hora de aplicar el escaneo 
- Creamos otra funcion llamada `realizar_escaneo`, va a recibir un objeto que es el `Dispositivo`
- Si queremos mostrar la cadena que estan representadas cada una lo podemos hacer con 
	- `realizar_escaneo(pc)`
	- `realizar_escaneo(router)`
	- `realizar_escaneo(movil)`
- En la función final de `realizar_escaneo` le asignamos los metodos de la subclase que se han instanciad, hereda del padre `Dispositivo`

Gracias a las distintas subclases que hemos creado tenemos una forma mas modular de reutilizar cada uno de las subclases que esta definidas en función del tipo de dispositivo que heredan de clase padre `Dispositivo`

```python
#!/usr/bin/python3  

class Dispositivo:  # Definición de una clase base llamada Dispositivo
    def __init__(self, modelo):  # Constructor de la clase que inicializa el modelo del dispositivo
        self.modelo = modelo  # Asigna el modelo pasado al crear el objeto a la variable de instancia

    def escanear_vulnerabilidades(self):  # Método que debe ser implementado en las subclases
        raise NotImplementedError("Este método debe de ser definido para el resto de subclases existentes")  # Lanza una excepción indicando que este método debe ser definido en las subclases

class Ordenador(Dispositivo):  # Definición de una clase llamada Ordenador que hereda de Dispositivo
    def escanear_vulnerabilidades(self):  # Implementación del método escanear_vulnerabilidades para la clase Ordenador
        return f"[+] Análisis de vulnerabilidades concluido: Actualización de software necesaria, múltiples desactualizaciones de software detectadas"  # Devuelve un mensaje específico para un ordenador

class Router(Dispositivo):  # Definición de una clase llamada Router que hereda de Dispositivo
    def escanear_vulnerabilidades(self):  # Implementación del método escanear_vulnerabilidades para la clase Router
        return f"[+] Análisis de vulnerabilidades concluido: Múltiples puertos críticos detectados como abiertos, es recomendable cerrar estos puertos"  # Devuelve un mensaje específico para un router

class TelefonoMovil(Dispositivo):  # Definición de una clase llamada TelefonoMovil que hereda de Dispositivo
    def escanear_vulnerabilidades(self):  # Implementación del método escanear_vulnerabilidades para la clase TelefonoMovil
        return f"[+] Análisis de vulnerabilidades concluido: Múltiples aplicaciones detectadas con permisos excesivos"  # Devuelve un mensaje específico para un teléfono móvil

def realizar_escaneo(dispositivo):  # Definición de una función que toma un objeto como argumento
    print(dispositivo.escanear_vulnerabilidades())  # Llama al método escanear_vulnerabilidades del objeto y lo imprime

pc = Ordenador("Dell XPS")  # Crea un nuevo objeto de la clase Ordenador con el modelo "Dell XPS"
router = Router("Tp-Link Archer C50")  # Crea un nuevo objeto de la clase Router con el modelo "Tp-Link Archer C50"
movil = TelefonoMovil("Samsung Galaxy S23")  # Crea un nuevo objeto de la clase TelefonoMovil con el modelo "Samsung Galaxy S23"

realizar_escaneo(pc)  # Llama a la función realizar_escaneo con el objeto pc y lo imprime
realizar_escaneo(router)  # Llama a la función realizar_escaneo con el objeto router y lo imprime
realizar_escaneo(movil)  # Llama a la función realizar_escaneo con el objeto movil y lo imprime

```

### Resumen

Este código define una clase base `Dispositivo` que tiene un método `escanear_vulnerabilidades` que debe ser implementado por las subclases. Luego define tres subclases: `Ordenador`, `Router` y `TelefonoMovil`, cada una con su propia implementación del método `escanear_vulnerabilidades`. Se crean objetos de estas clases con sus respectivos modelos y se realiza un escaneo de vulnerabilidades para cada uno, mostrando el resultado.

#### Tip final

Como hemos visto en la clase padre `Dispositivo` existe el método de escanear vulnerabilidades, el cual es subscrito con las subclases que tienen el mismo metodo contemplado.

Nos interesa tambien utilizar ese metodo que esta sinedo empleado en la clase padre, para que no se sobreescriba, esto tambien entra en juego con constructores, no unicamente con metodos 

Tambien por ejemplo cuando sobre escribimos el constructor, el que se haya agregado ultimamente sera el de mayor importancia o el que prevalece 

```python
#!/usr/bin/python3

class A:

	def __init__(self):
		print("Inicializando A")

class B(A):

	def __init__(self):
	print("Inicializando B")

b = B()
```

Si queremos que `A` pase por el `constructor A` `__init__`, tenemos la función de usar `super().__init__()`

```python
#!/usr/bin/python3

class A:

	def __init__(self):
		print("Inicializando A")

class B(A):

	def __init__(self):
	print("Inicializando B")
	super().__init__()

b = B()
```

También se le puede asignar un valor en especifico de la siguiente manera

```python
#!/usr/bin/python3 

class A:  # Definición de una clase llamada A
    def __init__(self, x):  # Constructor de la clase A
        self.x = x  # Asigna el valor pasado al crear el objeto a la variable de instancia x
        print(f"Valor en x: {self.x}")  # Imprime el valor de x

class B(A):  # Definición de una clase llamada B que hereda de A
    def __init__(self, x, y):  # Constructor de la clase B
        self.y = y  # Asigna el valor pasado al crear el objeto a la variable de instancia y
        super().__init__(x)  # Llama al constructor de la clase base A
        print(f"Valor en y: {self.y}")  # Imprime el valor de y

b = B(2, 10)  # Crea un nuevo objeto de la clase B con x = 2 y y = 10
```

Como les mencione no necesariamente tiene que ser solo para constructores.

```python
#!/usr/bin/python3  # Indica que se debe usar Python 3 para ejecutar este script

class A:  # Definición de una clase llamada A
    def saludo(self):  # Método saludo en la clase A
        return "Saludo desde A"  # Devuelve el texto "Saludo desde A"

class B(A):  # Definición de una clase llamada B que hereda de A
    def saludo(self):  # Método saludo en la clase B que sobreescribe el método en la clase A
        original = super().saludo()  # Llama al método saludo de la clase base A y guarda el resultado en la variable original
        print(f"{original}, pero también saludo desde B")  # Imprime el saludo original y añade un mensaje adicional

saludo = B()  # Crea un nuevo objeto de la clase B
saludo.saludo()  # Llama al método saludo del objeto saludo

```

### Resumen

Este código define dos clases `A` y `B`, donde `B` hereda de `A`. La clase `A` tiene un método `saludo` que devuelve un texto simple. La clase `B` sobreescribe el método `saludo` de `A`, llama al método `saludo` de `A` usando `super()`, y luego imprime el saludo original junto con un mensaje adicional. Cuando se crea un objeto de la clase `B` y se llama a su método `saludo`, se muestra el saludo de `A` junto con el mensaje adicional de `B`.
Espero hayan entendido el uso de `super`

Ahora como último ejercicio les dejo el siguienrte ejemplo:

```python
#!/usr/bin/python3  

class Persona:  # Definición de una clase llamada Persona
    def __init__(self, nombre, edad):  # Constructor de la clase Persona
        self.nombre = nombre  # Asigna el valor pasado al crear el objeto a la variable de instancia nombre
        self.edad = edad  # Asigna el valor pasado al crear el objeto a la variable de instancia edad

    def saludo(self):  # Método saludo en la clase Persona
        return f"Hola, soy {self.nombre} y tengo {self.edad} años"  # Devuelve un saludo con el nombre y la edad

class Empleado(Persona):  # Definición de una clase llamada Empleado que hereda de Persona
    def __init__(self, nombre, edad, salario):  # Constructor de la clase Empleado
        super().__init__(nombre, edad)  # Llama al constructor de la clase base Persona
        self.salario = salario  # Asigna el valor pasado al crear el objeto a la variable de instancia salario

    def saludo(self):  # Método saludo en la clase Empleado que sobreescribe el método en la clase Persona
        return f"{super().saludo()}, y cobro {self.salario} dolares brutos anuales"  # Devuelve el saludo de Persona y añade información sobre el salario

persona = Empleado("Kevin", 23, 65000)  # Crea un nuevo objeto de la clase Empleado
print(persona.saludo())  # Llama al método saludo del objeto persona y imprime el resultado

```