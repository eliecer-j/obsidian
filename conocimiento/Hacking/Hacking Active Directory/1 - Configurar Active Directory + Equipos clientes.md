Vamos a configurar un entorno de active directory donde habrá un domain controller y otro equipo windows vinculado al dominio. Por tanto lo primero será tener instalado un Windows Server:
![[Pasted image 20230126125541.png]]
Lo primero podemos ponerle un nombre al domain controller:
![[Pasted image 20230126131733.png]]
Ahora debemos abrir la consola de administración:
![[Pasted image 20230126131401.png]]
Y debemos ir al apartado de agregar roles y características:
![[Pasted image 20230126131436.png]]
Elegimos la primera opción:
![[Pasted image 20230126131502.png]]
Aquí dejamos todo igual:
![[Pasted image 20230126132010.png]]
Y aquí dejaremos activada la opción para instalar el Active Directory:
![[Pasted image 20230126132109.png]]
Damos en siguiente dentro de los siguientes menús y lo instalamos:
![[Pasted image 20230126135612.png]]
Y unavez que esté esto instalado, debemos activarlo, ya que veremos que nos salta un triángulo de advertencia en la parte de arriba a la derecha:
![[Pasted image 20230126140313.png]]
Se nos abrirá esta ventana:
![[Pasted image 20230126140351.png]]
Y en este punto vamos a seleccionar la opción de agregar un nuevo bosque y ponemos el nombre de dominio raiz que queramos:
![[Pasted image 20230126140513.png]]
Y ahora nos pide una contraseña, yo pondré la misma que tiene mi DC que es 124816mario:
![[Pasted image 20230126140623.png]]
Daremos todo a siguiente e instalamos lo que falte. Ahora desde otro equipo Windows ya podremos conectarnos al dominio, tal y como podemos ver tras aplicar el reinicio:
![[Pasted image 20230128183801.png]]
Por tanto ahora para no tener problemas, reiniciamos el DC y vamos a deshabilitar el antivirus con este comando:
![[Pasted image 20230128183546.png]]
Ahora vamos a reiniciar el sistema:
![[Pasted image 20230128183642.png]]


