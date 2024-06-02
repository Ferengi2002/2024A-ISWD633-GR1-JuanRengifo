# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](imagenes/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
# COMPLETAR (HECHO)
En Docker, una imagen es una plantilla inmutable que contiene todo lo necesario para ejecutar una aplicación, como el código, bibliotecas y configuraciones. Un contenedor, por otro lado, es una instancia en ejecución de esa imagen, que es mutable y puede tener estado. Los contenedores se crean a partir de imágenes y pueden ser iniciados, detenidos y eliminados, permitiendo una gran flexibilidad y eficiencia en el despliegue de aplicaciones. La relación esencial es que las imágenes proporcionan la base para crear y ejecutar los contenedores.


![Imagen y contenedores](imagenes/imagenYcontenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**

Al momento de ejecutar el comando en la terminal, se obtiene el siguiente resultado

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/db4f14f0-7509-4268-adab-17a1213e37f9)


  

# COMPLETAR

**¿Qué es nginx**
Nginx es un servidor web de código abierto, reconocido por su ligereza y alto rendimiento, capaz de gestionar un gran número de solicitudes web simultáneas con eficiencia y utilizando pocos recursos del sistema. Además de servir contenido web estático y dinámico, Nginx se destaca como un proxy inverso, balanceador de carga y servidor de streaming de medios, gracias a su arquitectura modular y su flexibilidad de configuración. Su estabilidad y escalabilidad lo han convertido en una opción popular para sitios web de gran envergadura, siendo utilizado por empresas como Netflix, Airbnb y GitHub.

# COMPLETAR 

Descargar la imagen  **nginx** en la versión **alpine**

Al momento de ejecutar el comando, se presenta la siguiente aplicación.

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/0391ef74-5020-433d-a04f-b1ac776fe31b)

# COMPLETAR

### Listar imágenes

```
docker images
```

con el comando de docker images, se listan las imagenes que tenemos dentro de nuestro docker.
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/7d46e6aa-3012-49e2-8cde-231ab68a1b3e)

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

Al en general, se tiene esta captura de la ejecucion:
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/bd11c329-bfa2-419b-b23b-87c6b6ff74df)


**Identificadores**
En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/9af12143-6216-45ed-a8c2-1d5198ce304a)


# COMPLETAR

**¿Con qué algoritmo se está generando el ID de la imagen**

El ID de la imagen en Docker se genera utilizando un algoritmo de resumen criptográfico, específicamente SHA-256. Este algoritmo calcula una función hash criptográfica de 256 bits sobre los datos de la imagen. Este hash único se utiliza como identificador único para la imagen.
En el resultado de tu comando docker inspect hello-world, puedes observar el campo "Id", que representa el ID de la imagen.
Este enfoque garantiza que cada imagen tenga una identificación única, lo que facilita su referencia y uso en entornos de desarrollo, implementación y distribución de aplicaciones con Docker.
# COMPLETAR

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

en Windows, se necesita usar otro comando el cual es:

```
docker images | findstr <termino a buscar>

```
Ejemplo:
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/456440c0-c390-4584-b1b8-b031591daf00)


### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/11c24b95-6f77-4b88-9d9f-1b41ba5150a4)

# COMPLETAR

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>

```
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/d3e707f8-dfce-4095-92a7-8c003b2e2d61)

