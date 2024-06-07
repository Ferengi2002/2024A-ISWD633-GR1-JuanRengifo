# VOLUMEN TIPO HOST
Un volumen host (o bind mount) es un tipo de volumen donde se monta un directorio o archivo específico del sistema de archivos del host en un contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```

### Crear un volumen tipo host con la imagen nginx:alpine, para la ruta carpeta host: directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html esta ruta se obtiene al revisar la se obtiene desde la documentación
![Volúmenes](imagenes/volumen-host.PNG)

```
docker run -d --name my_nginx -p 80:80 -v C:\Users\MyHP\Documents\GitHub\2024A-ISWD633-GR1-JuanRengifo\practica3\nginx\html:/usr/share/nginx/html nginx:alpine
```

### ¿Qué sucede al ingresar al servidor de nginx?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### ¿Qué pasa con el archivo index.html del contenedor?
Al ingresar al servidor de nginx, se verá el contenido del directorio montado desde el host. Esto significa que cualquier archivo HTML o recursos estáticos (CSS, JS, imágenes) en la carpeta html del host serán servidos por nginx.

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de nginx/html
### ¿Qué sucede al ingresar al servidor de nginx?
El archivo index.html original del contenedor nginx será sobrescrito por el archivo index.html de la carpeta html de tu computadora. Si no hay un archivo index.html en la carpeta html, nginx mostrará un error 404 o una página de índice predeterminada.
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/315e74f8-9b3d-4b99-aec0-bb078c53e4c9)

### Eliminar el contenedor
```
docker rm -f my_nginx
```


### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?
El servidor nginx mostrará nuevamente el contenido de la carpeta html de tu computadora, que contiene el template HTML5 descargado.
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/18d446bd-c3b3-4ac4-9a4f-ff0fc8e1799d)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/5a11dac7-ddbc-43d0-a2c3-4fa19fb63fed)


### ¿Qué hace el comando pwd?
El comando pwd (print working directory) muestra la ruta absoluta del directorio de trabajo actual.

Si quieres incluir el comando pwd dentro de un comando de Docker, lo puedes hacer de diferentes maneras dependiendo del shell que estés utilizando.


### Volumen tipo host usando PWD y PowerShell
```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v ${PWD}/<ruta relativa>:<ruta absoluta> <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (Git Bash)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd -W)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (en Linux)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

