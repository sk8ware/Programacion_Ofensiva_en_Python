
----
- TAG: #Self #Constructor #Clases #Suma
-----
El uso de self es uno de los aspectos más fundamentales y a la vez confusos para quienes se adentran en la Programación Orientada a Objetos (POO) en Python. Este identificador es crucial para entender cómo Python maneja los métodos y atributos dentro de sus clases y objetos.

**Definición de ‘self’**

A nivel conceptual, ‘**self**‘ es una referencia al objeto actual dentro de la clase. Es el primer parámetro que se pasa a cualquier método de una clase en Python. A través de self, un método puede acceder y manipular los atributos del objeto y llamar a otros métodos dentro del mismo objeto.

**Uso de ‘self’**

Cuando se crea una nueva instancia de una clase, Python pasa automáticamente la instancia recién creada como el primer argumento al método ‘**__init__**‘ y a otros métodos definidos en la clase que tienen self como su primer parámetro. Esto es lo que permite que un método opere con datos específicos del objeto y no con datos de la clase en general o de otras instancias de la clase.

**Importancia de ‘self’**

El concepto de self es importante en la POO ya que asegura que los métodos y atributos se apliquen al objeto correcto. Sin self, no podríamos diferenciar entre las operaciones y datos de diferentes instancias de una clase.

En esta clase, nos enfocaremos en comprender a fondo cómo y por qué self es usado en Python, explorando su papel en la interacción con las instancias de la clase. Desarrollaremos una comprensión clara de cómo self permite que las clases en Python sean intuitivas y eficientes, manteniendo un estado consistente a través de las operaciones del objeto. Este conocimiento es esencial para trabajar con clases y objetos de manera efectiva y aprovechar la potencia de la POO.

---

Claro, aquí tienes tus notas corregidas y estructuradas con títulos y subtítulos. He corregido las faltas ortográficas y mejorado la redacción donde era necesario. 

---

# Clase en Python: Uso de `self` en Clases y Métodos

## Introducción

Vamos a practicar con un ejercicio empleando una clase para explicar de mejor manera el uso de `self`. Esta plantilla puede contener tanto métodos como atributos. Recuerden que la clase no es un objeto; es cuando instanciamos la clase que creamos un objeto. Eso sería la instancia de la clase, la cual tendría los métodos y atributos que hayamos definido en la clase.

## Creación de una Clase

### Constructor de la Clase

Se empieza creando un constructor `def __init__()`.

Cuando creamos una instancia de la clase, al hacer esto le estaríamos pasando unos valores para poder crear este objeto. Sus propiedades y atributos serían `("Anthony", 25)`.

```python
#!/usr/bin/python3

class Persona:
    def __init__(self):
        pass

anthony = Persona("Anthony", 25)
```

### Uso de `self` en el Constructor

Como estamos creando este objeto, debemos irlo construyendo, comenzando con el método especial que es el constructor `def __init__()`. Así que le agregamos un `self` que hace referencia a `anthony`.

Ya que cuando creamos el objeto `anthony`, los atributos `("Anthony", 25)` se vinculan de alguna manera al objeto `anthony`.

En el siguiente ejemplo, se hará referencia a `self` al objeto `anthony`, donde nombre valdrá "Anthony" y edad a 25.

```python
#!/usr/bin/python3

class Persona:
    def __init__(self, nombre, edad): # Persona.__init__(anthony, nombre, edad)
        self.nombre = nombre # anthony.nombre = "Anthony"
        self.edad = edad # anthony.edad = 25

anthony = Persona("Anthony", 25)
```

### Definiendo Métodos en la Clase

Si tratáramos de imprimir dicha función, veremos que no funcionará porque no le hemos indicado lo que queremos que nos muestre. Para ello, debemos agregarle una definición con `def`.

```python
#!/usr/bin/python3

class Persona:
    def __init__(self, nombre, edad): # Persona.__init__(anthony, nombre, edad)
        self.nombre = nombre # anthony.nombre = "Anthony"
        self.edad = edad # anthony.edad = 25

    def presentacion(self): # Persona.presentacion(anthony)
        print(f"Hola, soy {self.nombre} y tengo {self.edad} años") # anthony.nombre # anthony.edad

anthony = Persona("Anthony", 25)
anthony.presentacion()
```

Para imprimir el nombre o hacer referencia a él, debemos agregar `anthony.presentacion()` al final del método `presentacion`.

Agregando el `print` nos permitirá ver por consola el texto, incluyendo `{self.nombre}` y `{self.edad}`.

### Accediendo a Otros Métodos de la Clase

Cuando definimos un método, ese método internamente puede acceder a otro método que esté incluido en la plantilla de la clase. Para ello, es necesario utilizar el método `self` para poder acceder a ese otro método desde otro método.

## Ejemplo: Implementación de una Calculadora

### Definición de la Clase Calculadora

Ahora les indicaré otro ejemplo implementando una `class` llamada `Calculadora`, seguido del constructor `__init__()`. Creamos un objeto que se llame `calc` con el valor de `(50)`. Este sería el número con el que estamos inicializando.

La idea de `self` en el constructor `__init__()`: en la clase `Calculadora` estamos creando a través del constructor un nuevo objeto, que es `calc`, y le pasamos el valor `numero`.

Una vez contemplados los valores en el constructor, debemos crear estas igualdades para asignarle el atributo correspondiente. Así que le pasamos `self.numero` para que `calc.numero` valga 50.

```python
#!/usr/bin/python3

class Calculadora:
    def __init__(self, numero): # Calculadora.__init__(calc, numero)
        self.numero = numero # calc.numero = 50
```

### Método para Sumar Números

Ahora, si queremos sumarle un número a ese valor de 50, podemos hacer lo siguiente:

Crear un método que se va a llamar `suma` con `def suma()`.

Agregamos otro valor para que sume con el otro atributo `50`, sería: `calc.suma(8)`. Si le pasamos este nuevo valor, hará referencia a todo el objeto `calc`.

Hacemos referencia a `self` en el método `suma`, haciendo referencia al objeto `calc` y agregándole `(otro_numero)`. Realizando esto, haríamos referencia a ambos números para que se sumen `{self.numero + otro_numero}`.

```python
#!/usr/bin/python3

class Calculadora:
    def __init__(self, numero): # Calculadora.__init__(calc, numero)
        self.numero = numero # calc.numero = 50

    def suma(self, otro_numero): # Calculadora.suma(calc, 8)
        print(self.numero + otro_numero) # calc.numero + 8 -> 50 + 8

calc = Calculadora(50)
calc.suma(8)
```

### Método para Sumar Dos Veces

Ahora trataremos de crear un método que nos devuelva una suma doble. Le agregamos la siguiente definición para poder explicarlo mejor.

Agregamos definición `def doble_suma():`.

Agregamos el `calc.doble_suma(2, 9)`.

Para esto, querremos que el número 2 nos devuelva `2 + 50`, todo eso más el `9 + 50` por separado.

Llamaremos al método `suma` en nuestra definición de `doble_suma()` para pasarle `2 + 50`, que es el atributo de `self`. Luego, llamarla desde el método `doble_suma`, sumará primeramente `50 + 9`.

Como se le están pasando dos valores y estamos tratando con el objeto `calc`, así que le añadimos `def doble_suma(self, num1, num2):`, ya que son dos números los cuales les estamos pasando.

Ahora, cuando queramos ingresar a otro método existente que sea método de la clase, y por consecuencia son métodos que podemos referenciar a través del objeto, nos podemos aprovechar de `calc`, que se representa por un `self.suma` y hacer lo que deseemos.

`Suma` recibiría el método `otro_numero` que recuerden que le sumamos `self.numero` como atributo, que es `50`.

Pero si por debajo le pasamos `self.suma(num1)`, esto haría que para la clase `Calculadora`, llamando al método `suma`, en este caso le estaríamos pasando el `self.suma(num1)`, representando a `calc` y un número que en este caso sería `(num1)`. Pero antes de poner `calc.suma(8)`, porque es la misma referencia de la clase que estamos empleando.

Esto nos dará como resultado que si llamamos a `self.suma(num1)`, equivaldrá a `2`, así que por lo tanto `otro_numero` va a valer 2, y 2 lo va a sumar a `self.numero`, que es 50, lo que daría 52 de respuesta. Ahora quisiéramos volver a llamar a `self.suma(num2)`, pasando `num2` que sería `9` y este número se suma con el 50.

Para evitar errores, eviten usar `print` arriba y realicen un `return` arriba para que el tipo de dato sea el mismo y tengamos un valor entero. Realizado esto, podemos usar el `print`, pero puede que el tipo de dato cambie, así que es preferible utilizar un `return` en ambos lugares.

Y ya desde el final realizar el `print`.

```python
#!/usr/bin/python3

class Calculadora:
    def __init__(self, numero): # Calculadora.__init__(calc, numero)
        self.numero = numero # calc.numero = 50

    def suma(self, otro_numero): # Calculadora.suma(calc, 8)
        return(self.numero + otro_numero) # calc.numero + 8 -> 50 + 8

    def doble_suma(self, num1, num2): # Calculadora.doble_suma(calc, 2, 9)
        return self.suma(num1) + self.suma(num2)

calc = Calculadora(50)
calc.suma(80)

print(calc.doble_suma(2,9))
```

Así que se suma el 50 + 2 y el 50 + 9:

```
  52
+ 59
-----
 111
```

### Conclusión

Para entender las clases, es recomendable representar línea por línea cada una de las cosas.

#### Ejemplo Final

```bash
 #!/usr/bin/python3

class Calculadora:
	def __init__(self, numero): # Calculadora.__init__(calc, numero)
		self.numero = numero # calc.numero = 50

	def suma(self, otro_numero): # Calculadora.suma(calc, 9)
		return(self.numero + otro_numero) # calc.numero + 9 -> 50 + 9 = 59

	def doble_suma(self, num1, num2): # Calculadora.doble_suma(calc, 2, 9)
		return self.suma(num1) + self.suma(num2) # calc.suma(2) + calc.suma(9) -> Calculadora.suma(calc, 2) + Calculadora.suma(calc, 9) = 59 + 52 
```