# Práctica: Docker - Comandos básicos

#### 1. Descargar la imagen y saber si la imagen está en el equipo:
``` 
docker pull ubuntu
docker image ls
 ```
Descargamos la imagen **ubuntu** y nos da un listado de las images que tenemos en nuestro equipo

#### 2. Contenedor sin nombre:
``` 
docker -it run ubuntu
``` 
Para saber el nombre del contenedor (si no podemos ninguno, se pone por defecto) 
``` 
docker ps -a
``` 

#### 3. Crear contenedor con nombre:
``` 
docker run -it --name dam_ubu1 ubuntu bash
``` 
Para poder acceder a el en el caso de salir uso el comando:
```
docker exec -it dam_ubu1 bash
```
#### 4. Comprobar ip y ping a google.com:

 **IP obtenida:** 172.17.0.2

Todos estos comandos los uso dentro del contenedor, por eso antes pusimos **-it**, para así poder interactuar con la consola.
``` 
ifconfig
ping www.google.com
``` 
Para que nos funcione el comando **ifconfig** es necesario escribir estos comandos primeros:
``` 
apt update
apt install net-tools
``` 
Para que funcione el comando **ping** es necesario escribir este otro comando:
```
apt install iputils-ping
```

#### 5. Crear otro contendor ¿Se puede hacer ping entre este y el anterior?
```
docker run -it --name dam_ubu2 ubuntu bash
ping 172.17.0.2
```
Utilizamos el comando **ping** con la IP obtenida antes del otro contenedor

#### 6. Salir del terminal ¿qué pasa con el contenedor?:
``` 
exit
``` 
El contenedor se detiene
#### 7. Memoria ocupada en el disco duro:
```
docker system df
```
Este comando nos sirve para saber cuando espacio ocupa Docker, sus imágenes y contenedores
#### 8. RAM ocupada por los contenedores:
``` 
docker stats -a
```
Nos muestra información sobre el uso de la CPU, RAM, etc.

