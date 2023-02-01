Para conocer todos los equipos conectados dentro de mi red

`import nmap
`nm = nmap.PortScanner()
`nm.scan("192.168.0.0/24") # Escaneamos toda la red
`print(nm.all_hosts())
![[Pasted image 20221217084458.png]]
`import nmap
`nm = nmap.PortScanner()
`nm.scan("192.168.0.2") # Escaneamos este objetivo
`print(nm.all_hosts()) # Para detectar los hosts de la red.
`print(nm["192.168.0.2"].state()) # Para saber que hosts están encendidos.
`print(nm["192.168.0.2"].all_protocols()) # Los protocolos utilizados.
`print("Puertos abiertos: ", nm["192.168.0.2"]["tcp"].keys()) # Los puertos abiertos.
![[Pasted image 20221217085333.png]]
También podemos hacerlo con un input para poder introducir la IP:

`import nmap
`scanner = nmap.PortScanner()
`ip = input("Inserte una dirección IP: ")
`print("La IP que introduciste es: ",ip)

`print("Nmap Version: ", scanner.nmap_version()) # Muestra la versión de nmap
`scanner.scan(ip, "1-1024", "-v -sS") # Aquí van el rango de puertos y que tipo de escaneo queremos.
`print(scanner.scaninfo())
`print("Ip Status: ", scanner[ip].state()) # Para saber si el host está levantado o no.
`print(scanner[ip].all_protocols()) # Muestra el protocolo que está utilizando.
`print("Puertos abiertos: ", scanner[ip]["tcp"].keys()) # Para saber los puertos abiertos.
![[Pasted image 20221217085231.png]]
