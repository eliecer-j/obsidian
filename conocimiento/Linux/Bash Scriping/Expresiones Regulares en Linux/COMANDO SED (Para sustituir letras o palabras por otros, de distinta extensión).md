Por ejemplo vamos a sustituir la palabra Hola por la palabra Mario con el comando sed:
![[Pasted image 20230128181636.png]]
Incluso también podemos sustituir un espacio por lo que queramos, por ejemplo donde había un espacio ponemos un guión:
![[Pasted image 20230128181721.png]]
Lo que pasa que sólo nos sustituye con la primera coincidencia, por lo que si queremos hacer una sustitución en todo el documento debemos poner una 'g' al final:
![[Pasted image 20230128181813.png]]
También puedo eliminar el último elemento de una cadena de texto, escribiendo sed ‘s/.$//’
![[Untitled.png]]
Aunque también podemos incluso sustituir saltos de línea con sed:
![[Untitled 1.png]]
También podemos incluso sustsusituit un determinado patrón dentro de un documento de texto sin necesidad de entrar en él; es decir, podremos automatizar que podamos modificar texto en un documento txt:
![[Untitled 2.png]]