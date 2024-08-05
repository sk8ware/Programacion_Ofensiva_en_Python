
---
# TAG: 
----
En esta clase, pondremos en práctica todo lo que hemos aprendido sobre listas, tuplas, diccionarios y conjuntos para crear un sistema de gestión de videojuegos en Python. Este proyecto integrador nos servirá para consolidar nuestras habilidades de programación, ya que abordaremos la administración de ventas, la gestión de stock y la actualización de datos en un sistema de control central.

Durante la clase, te guiaremos a través del desarrollo de las funcionalidades clave de nuestro sistema, mostrando cómo se puede aplicar cada estructura de datos en situaciones concretas de manejo de información. Vamos a crear un programa que no solo administre eficientemente los datos de videojuegos, sino que también sea capaz de interactuar con el usuario para realizar consultas y actualizar el inventario.

Este enfoque práctico es ideal para afianzar los conceptos teóricos en un contexto realista, demostrando la potencia y versatilidad de Python en el desarrollo de aplicaciones. La clase será esencialmente una sesión interactiva, por lo que la mayor parte del aprendizaje se realizará a través de la observación y la práctica directa con el código en el vídeo.

Al concluir, habrás experimentado la satisfacción de construir un proyecto completo que simula un escenario del mundo real, reforzando tu comprensión de cómo las estructuras de datos se utilizan en la creación de software y preparándote para futuros proyectos de programación.

---
Vamos a crear una pequeña utilidad para representar la información de cada juego 

```python
#!/usr/bin/python3

# Géneros
generos = {
	"Super Mario Bros": "Aventura",
	"Zelda: Breath of the Wild": "Aventura",
	"Cyberpunk 2077": "Rol",
	"Final Fantasy VII": "Rol"
}

# Ventas y Stock
ventas_y_stock = {
	"Super Mario Bros": (400, 200),
	"Zelda: Breath if the Wild": (60, 120),
	"Cyberpunk 2077": (60, 120),
	"Final Fantasy VII": (924, 3)
}

# Clientes 
clientes = {
	"Super Mario Bros": {"Anthony", "David", "Erick", "Claudia"},
	"Zelda: Breath of the Wild": {"Pepe", "David", "Erick", "Silvia"},
	"Cyberpunk 2077": {"Mateo", "Jose", "Richard", "Gloria"},
	"Final Fantasy VII": {"Claudia", "Jose", "Anthony", "Richard", "Paola"}
}

mi_juego = "Final Fantasy VII"

# Sumario
print(f"\n[i] Resumen del juego {mi_juego}\n")
print(f"\t[+] Género del juego: {generos[mi_juego]}")
print(f"\t[+] Total de ventas para este juego: {ventas_y_stock[mi_juego][0]} unidades")
print(f"\t[+] Total de stock para este juego: {ventas_y_stock[mi_juego][1]} unidades")
print(f"\t[+] Clientes que han adquirido el juego: {' , '.join(clientes[mi_juego])}")
```

Ahora le complicaremos un poco más

```python
#!/usr/bin/python3

juegos = ["Super Mario Bros", "Zelda: Breath of the Wild", "Cyberpunk 2077", "Final Fantasy VII"]

tope = 100

# Géneros
generos = {
	"Super Mario Bros": "Aventura",
	"Zelda: Breath of the Wild": "Aventura",
	"Cyberpunk 2077": "Rol",
	"Final Fantasy VII": "Rol"
}

# Ventas y Stock
ventas_y_stock = {
	"Super Mario Bros": (400, 200),
	"Zelda: Breath of the Wild": (60, 120),
	"Cyberpunk 2077": (60, 120),
	"Final Fantasy VII": (924, 3)
}

# Clientes 
clientes = {
	"Super Mario Bros": {"Anthony", "David", "Erick", "Claudia"},
	"Zelda: Breath of the Wild": {"Pepe", "David", "Erick", "Silvia"},
	"Cyberpunk 2077": {"Mateo", "Jose", "Richard", "Gloria"},
	"Final Fantasy VII": {"Claudia", "Jose", "Anthony", "Richard", "Paola"}
}

def sumario(juego):
	# Sumario
	print(f"\n[i] Resumen del juego {juego}\n")
	print(f"\t[+] Género del juego: {generos[juego]}")
	print(f"\t[+] Total de ventas para este juego: {ventas_y_stock[juego][0]} unidades")
	print(f"\t[+] Total de stock para este juego: {ventas_y_stock[juego][1]} unidades")
	print(f"\t[+] Clientes que han adquirido el juego: {' , '.join(clientes[juego])}")

for juego in juegos:
	if ventas_y_stock[juego][0] > tope:
		sumario(juego)

ventas_totales = lambda: sum(ventas for juego, (ventas, _) in ventas_y_stock.items() if ventas_y_stock[juego][0] > tope)

print(f"\n[+] El total de ventas de todos los productos ha sido de {ventas_totales()} productos")
```

Con `%s/mi_juego/juego` podemos cambiar a `juego`

