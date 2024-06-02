# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/9113c7bf-c5dd-4152-8261-55676569d462)

# COMPLETAR

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/4330c409-f076-47e6-8e52-a8da55b1ecd5)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/7af6bdea-5e41-4f8b-9a5b-3be710e51ffb)

# COMPLETAR

### Listar los contenedores ejecutándose o no

```
docker ps -a
```
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/7c3d8cad-b7da-4e24-bac1-f6bce1818909)

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/195aa3f2-960c-4db0-9b6a-bff4dd416742)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/d1826750-1b1b-4d95-9402-e6f6d42bee62)



# COMPLETAR

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/cc312a6c-509a-4b58-8318-574878d2df91)


### Para detener un contenedor

```
docker stop <nombre contenedor>
```
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/992f3311-9976-42ce-8260-22d20d7bd877)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/9c102326-8eed-46da-941f-1f30947d5cef)


### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](imagenes/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/fac0f7db-fcbe-4e2d-9812-543c53d7bb1f)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/8dea0207-e0f1-4bab-8456-2d5b2d260a91)


# COMPLETAR

**¿Qué sucede luego de la ejecución del comando?**

Después de ejecutar el comando docker run --name srv-web2 nginx:alpine, se inicia un nuevo contenedor Docker utilizando la imagen nginx:alpine. Este contenedor ejecuta el servidor web Nginx. Durante el inicio del contenedor, se realizan configuraciones necesarias a través del script de entrada (docker-entrypoint.sh), incluyendo la ejecución de varios scripts en el directorio /docker-entrypoint.d/. Una vez completada la configuración, el servidor Nginx se inicia y se muestran mensajes que indican su estado, incluyendo la versión de Nginx, detalles del compilador utilizado y del sistema operativo subyacente. Finalmente, Nginx inicia varios procesos de trabajo para manejar las solicitudes de los clientes, quedando el servidor listo para servir contenido web.


# COMPLETAR  

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

Aplastamos Ctrl + C para parar la ejecucion

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/ec697ce6-a147-4adf-975e-36f401788994)

Ahora, ejecutamos el comando
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/cea704f4-7179-424c-8281-8040901fe701)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/d3277566-2731-4d39-a044-4798bdf667ec)


# COMPLETAR

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/a4dde18b-735e-4d59-be80-83289b439506)


# COMPLETAR

Verificar que el contenedor que se eliminó

Para verificar que el contenedor se elimino, se puede ver desde el Docker Desktop

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/8ba09014-852d-4527-80a7-f2bffef9e055)


# COMPLETAR

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/aef08e60-d69a-40f0-9704-88b5b14012b7)

# COMPLETAR

Verificar que el contenedor que se eliminó

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/12b8affe-bea7-44fe-8dd9-43bfbf4d5277)

# COMPLETAR

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

Para inspecionar un contenedor, se puede realizar de la siguiente manera:

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/e0593fb1-2cc5-4d87-bf5a-a783ea929198)

# COMPLETAR
