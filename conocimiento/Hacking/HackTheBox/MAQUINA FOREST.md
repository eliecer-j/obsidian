Enumerar usuarios válidos con enum4linux, comprobar usuarios que no usen Kerberos con GetNPUsers, listar recursos compartidos con crackmapexec y evilwinrm para obtener reverse shell - Active Directory)

Haremos los reconocimientos de siempre:
![[Pasted image 20230126111303.png]]
Ya que es una máquina Windows, debemos enumerar con crackmapexec qué máquina es y qué windows tiene instalado, el cual se trata de un Windows Server 2016:
![[Pasted image 20230126111311.png]]
Intentamos listar los recursos compartidos con una null session de esta máquina pero no sale nada:
![[Pasted image 20230126111320.png]]
Lo que podemos hacer es intentar enumerar usuarios válidos haciendo uso de la herramienta enum4linux:
![[Pasted image 20230126112406.png]]
![[Pasted image 20230126112436.png]]
Ahora que tenemos todos estos usuarios, vamos a guardarlos todos en un documento para poder usarlos como ataque de fuerza bruta, esto podemos hacerlo a través de expresiones regulares en bash o copiando y pegando cada usuario:
![[Pasted image 20230126113248.png]]
Y lo guardamos dentro del documento users:
![[Pasted image 20230126113324.png]]
Ahora que tenemos este listado de usuarios, hay una herramienta que se llama GetNPusers de impacket que sirve para obtener Ticket Granting Ticket (TGT) de credenciales de aquellos usuarios que no requieren autenticación Kerberos; por tanto debemos pasarle el dominio y el diccionario con los usuarios, y vemos que nos encuentra un hash de uno de los usuarios:
![[Pasted image 20230126114019.png]]
Ahora guardamos este hash en un documento de texto y con john intentamos deshashearla con un ataque de fuerza bruta utilizando el diccionario rockyou.txt:
![[Pasted image 20230126111407.png]]
Y tras ejecutar este comando, obtenemos una contraseña, la cual es s3rvice:
![[Pasted image 20230126114314.png]]
Ahora con crackmapexec podemos validar si estas credenciales son válidas, las cuales vemos que sí:
![[Pasted image 20230126111426.png]]
Y con estas credenciales ya podemos listar recursos compartidos y los permisos que tenemos:
![[Pasted image 20230126111434.png]]
Y ahora podemos ver si este usuario forma parte del grupo win managament users:
![[Pasted image 20230126111442.png]]
Ahora con toda esta información ya podemos ganar una consola interactiva utilizando las credenciales de este usuario utilizando evil-winrm:
![[Pasted image 20230126111450.png]]
Y navegando por los directorios, obtenemos la flag:
![[Pasted image 20230126111458.png]]