pip install lxml // pip install bs4 // html5lib

![[Pasted image 20221217090221.png]]

![[Pasted image 20221217090235.png]]

![[Pasted image 20221217090241.png]]

![[Pasted image 20221217090246.png]]

![[Pasted image 20221217090257.png]]
![[Pasted image 20221217090314.png]]

## SCRIPT PARA EXTRAER EQUIPOS DE LA CLASIFICACIÓN DE FUTBOL
Vamos a crear un bot que extraiga todos los equipos de esta web:
![[Pasted image 20230117213029.png]]
Por tanto en Python lo haríamos de esta forma:
```import requests
from bs4 import BeautifulSoup


website = "https://resultados.as.com/resultados/futbol/primera/clasificacion/"
result = requests.get(website)
content = result.text

soup = BeautifulSoup(content, "html5lib")
print(soup.prettify())


equipos = soup.find_all('span', class_= "nombre-equipo") # Aquí filtramos solo los párrafos.

print(equipos)
```

Y este sería el resultado:
![[Pasted image 20230117213830.png]]
Ahora si queremos ver sólo los equipos sería tan fácil como indicar a python que elimine todos esos patrones en común de las etiquetas con el método .replace:

