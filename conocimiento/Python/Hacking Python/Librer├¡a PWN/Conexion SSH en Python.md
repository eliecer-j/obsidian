Para comprobar que existe conectividad por ssh, para ello ejecutamos este código con una máquina víctima:
![[Pasted image 20221217094024.png]]
Y veremos que con estos datos es correcto y hay conectividad:
![[Pasted image 20221217094033.png]]
Y ahora podemos entrar por ssh y ejecutar comandos remotamente poniendo este código:
![[Pasted image 20221217094153.png]]
![[Pasted image 20221217094159.png]]
También podemos ejecutar cualquier comando de esta otra manera bastante parecida:
![[Pasted image 20221217094308.png]]

![[Pasted image 20221217094315.png]]
Y también podemos crear un archivo de esta forma:

![[Pasted image 20221217094335.png]]
![[Pasted image 20221217094343.png]]
![[Pasted image 20221217094351.png]]

Ahora con esto podemos colapsar la máquina víctima creando un bucle while infinito que vaya creando archivos sin parar:

![[Pasted image 20221217094412.png]]
![[Pasted image 20221217094418.png]]



