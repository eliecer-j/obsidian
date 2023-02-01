Lo primero será importar esta librería de esta forma:
```
import socket

socket-socket(socket.AF_INET,socket.SOCK_STREAM)
```
Y estas líneas sirven para indicar que queremos hacer una conexión utilizando IPV4 y el protocolo de transporte TCP, tal y como se explica en la captura:
![[Pasted image 20230112010821.png]]
Y por otra parte aquí tenemos los métodos disponibles para esta librería:

```
socket.recv(buflen)
socket.recvfrom(buflen)
socket.recv_into(buffer)
socker.send(bytes)
socket.sendto(data, address)
socket.sendall(data)
socket.close()
```

# MÉTODOS QUE SE USAN EN SERVIDOR
En el lado del servidor se utilizan estos métodos:
![[Pasted image 20230112011321.png]]
# MÉTODOS QUE SE USAN EN CLIENTE
![[Pasted image 20230112012136.png]]
