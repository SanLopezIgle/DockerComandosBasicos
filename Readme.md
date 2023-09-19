# Práctica: Docker - Comandos básicos

#### 1. Para saber si la imagen está en el equipo:
``` 
docker image ls
 ```

Nos da un listado de las images que tenemos en nuestro equipo

#### 2. Contenedor sin nombre:
``` 
docker run ubuntu
``` 
Para saber el nombre del contenedor (si no podemos ninguno, se pone por defecto) 
``` 
docker ps -a
``` 

#### 3. Crear contenedor con nombre:
``` 
docker run -it --name dam_ubu1 ubuntu bash
``` 

#### 4. Comprobar ip y ping a google.com:

172.17.0.2

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
Utilizamos el comando **ping** con la ip obtenida antes del otro contenedor

#### 6. Salir del terminal ¿qué pasa con el contenedor?:
``` 
exit
``` 
El contenedor se detiene

#### 7. Memoria ocupada en el disco duro y RAM ocupada por los contenedores:

``` 
docker stats -a
```


