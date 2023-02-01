## Expresión regular re.find y re.find.all:
Para utilizar las expresiones regulares, podemos utilizar la librería re, por ejemplo en primer lugar vamos a buscar un dato dentro de un string con re.search:
```
import re


texto = "Hola que tal"

texto_buscar = "Hola"

  
if re.search(texto_buscar, texto) is not None:
	print("He encontrado el texto: ", texto_buscar)
else:
	print("No lo encontré")
```
Y vemos que nos lo encuentra correctamente:
![[Pasted image 20230119100925.png]]
Pero esto sólo busca una vez, pero qué ocurre si queremos encontrar todas las veces que se repite un patrón; pues para ello hacemos uso de find.all:
```
import re


texto = "Hola que tal. Hola a todos"

texto_buscar = "Hola"
  
lista = re.findall(texto_buscar, texto)

print(lista)
```
Y nos guarda en una lista las veces que se repite una palabra:
![[Pasted image 20230119101437.png]]
O también con .len podemos saber cuantas veces se repite una palabra:
```
import re

texto = "Hola que tal. Hola a todos"
texto_buscar = "Hola"
print(len(re.findall(texto_buscar, texto)))
```
Donde vemos que en este caso se repite dos veces: 
![[Pasted image 20230119101754.png]]
## OBTENER FILA ENTERA AL ENCONTRAR UN PATRRÓN (SIMILAR A GREP)
Podemos obtener algo parecido al grep de Linux, donde podemos obtener la línea entera si nos encuentra un patrón, por ejemplo sería de esta manera:
```
import re

nombres = ["Mario Álvarez", "Pepe Pepón", "Juan Álvarez"]

for cada_nombre in nombres:
re.findall('Mario', cada_nombre)
print(cada_nombre)
```
Y ahora imprimimos el nombre completo cada vez que nos encuentre la coincidencia de Mario:
![[Pasted image 20230119102806.png]]
