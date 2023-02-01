Lo primero será instalar la base de datos Oracle y también el SQL Developer para acceder a ella, por tanto voy a instalar el SGBD de Oracle 19c Standard Edition para Windows; por tanto el primer paso será acceder a la web oficial del fabricante:

![[Pasted image 20221217102820.png]]

Y una vez hayamos iniciado sesión se nos empezará a descargar el instalador:

![[Pasted image 20221217102829.png]]

Ahora una vez que los archivos estén descargados y descomprimidos, abriremos la carpeta y veremos un ejecutable, al que tendremos que hacer doble clic para comenzar con la instalación:

![[Pasted image 20221217102836.png]]

En este punto vamos a seleccionar la opción de instancia única - Clase Escritorio – Usar Cuenta Virtual:

![[Pasted image 20221217102849.png]]

Y ahora en esta última ventana, vamos a establecer una contraseña para nuestra base de datos, la cual debe cumplir con ciertos requisitos, que en mi caso utilicé una contraseña con números, letras y letras mayúsculas:

![[Pasted image 20221217102857.png]]

Ahora comienza con la instalación:

![[Pasted image 20221217102904.png]]

Y ya ha finalizado:

![[Pasted image 20221217102912.png]]

Ahora que ya está instalada, se nos habrá instalado también una aplicación que se llama SQL Plus, desde la cual podremos administrar la base de datos, por tanto vamos a comprobar que todo esté bien configurado desde este menú:

![[Pasted image 20221217102920.png]]

Y si lo abrimos, se nos pedirá iniciar sesión (que lo haré con el usuario System) y a continuación insertar la contraseña que establecí en el proceso de instalación. Una vez hecho esto, ya puedo insertar el comando SELECT SYSDATE FROM DUAL; para que se muestre la hora y ver que la instalación se ha completado correctamente:

![[Pasted image 20221217102928.png]]

Ahora vamos a instalar SQL Developer; y para ello simplemente tengo que descargarlo, mover la carpeta al disco duro y crear un acceso directo del ejecutable de SQL en el escritorio para poder ejecutarlo:

![[Pasted image 20221217102936.png]]

Por tanto ahora abrimos SQL Developer y vamos a conectarnos a la base de datos con esta configuración y poniendo la contraseña que configuramos durante el proceso de instalación:
![[Pasted image 20230102200823.png]]
Y ya tendremos disponible la base de datos:
![[Pasted image 20230102200856.png]]
