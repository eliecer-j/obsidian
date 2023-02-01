Lo primero será crear el apk con msfvenom, estableciendo el puerto y dirección IP donde recibiremos la conexión:
![[Pasted image 20221218205156.png]]
Una vez tengamos esto, lo enviamos al teléfono Android y mientras tanto nos ponemos a la escucha desde metasploit con el payload android/meterpreter/reverse_tcp:
![[Pasted image 20221218205203.png]]
![[Pasted image 20221218205206.png]]
A continuación establecemos el LHOST y el LPORT, que será por donde estemos escuchando la conexión:
![[Pasted image 20221218205212.png]]
Y luego con el comando run o exploit lanzamos este TCP handler:
![[Pasted image 20221218205225.png]]
Ahora en el android instalamos el apk malicioso, lo abrimos y ya habremos recibido la conexión:
![[Pasted image 20221218205232.png]]
