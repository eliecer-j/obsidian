La librería random sirve para generar cosas aleatorias:
![[Pasted image 20230104133515.png]]
![[Pasted image 20230104133542.png]]
![[Pasted image 20230104133705.png]]
![[Pasted image 20230104133715.png]]
![[Pasted image 20230104133728.png]]
![[Pasted image 20230104133737.png]]
![[Pasted image 20230104133804.png]]
![[Pasted image 20230104133814.png]]
![[Pasted image 20230104133824.png]]
También podemos utilizar la función input para recoger posibles opciones de regalos y guardar esas opciones en una lista, para posteriormente elegir una de las posibles opciones que intrudujo el usuario:
![[Pasted image 20230104134808.png]]
Ahora también podemos ir añadiendo de forma aleatoria 3 posibles ordenadores que se encuentran dentro de una lista llamada ordenadores, y con la librería random y un bucle for podemos ir añadiendo estos nuevos ordenadores:
![[Pasted image 20230104151954.png]]
![[Pasted image 20230104152014.png]]
Otro ejemplo donde hacemos lo mismo de antes pero con dos tablas y muchos números, donde insertamos muchos datos a la vez con un bucle for dentro de la base de datos:
```
import mysql.connector

import random

  

conexion = mysql.connector.connect(user="root", password="123123",

                                    host="localhost",

                                    database="tienda",

                                    port="3306",)

  

miCursor = conexion.cursor()

  

for posiciones in range(0,1000):

    ganadores = random.choice(range(0,1000))

    miCursor.execute(f"INSERT INTO cesta(ganador, posicion) VALUES ('{ganadores}', '{posiciones}')")

  

conexion.commit()

  

conexion.close()
```
![[Pasted image 20230105132949.png]]


