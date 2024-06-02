# Mapeo de puertos
El mapeo de puertos es un mecanismo que permite redirigir el tráfico de red desde un puerto en el host (tu máquina local o servidor) hacia un puerto específico en un contenedor Docker.
Por ejemplo, supongamos que tienes un contenedor que ejecuta un servidor web en el puerto 80 dentro del contenedor, pero quieres acceder a ese servidor desde tu navegador en la máquina host. Puedes usar el mapeo de puertos para redirigir el tráfico del puerto 80 del contenedor al puerto 3000 en el host. De esta manera, cuando accedas a http://localhost:3000 en tu navegador, el tráfico se dirigirá al servidor web dentro del contenedor en el puerto 80.

![mapeo](imagenes/mapeoPuertos.PNG)

### Para crear un mapeo de puertos (puerto host y puerto contenedor)
El mapeo de puertos se especifica al ejecutar un contenedor Docker utilizando la opción -p o --publish seguida de los puertos que deseas mapear
```
docker run -d --name <nombre contenedor> -p <puerto host>:<puerto contenedor> <nombre imagen>:<tag>

```
Crear un contenedor a partir de la imagen nginx version alpine con el mapeo de puertos del ejemplo gráfico, host 3000 y contenedor 80

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/695b3c01-e732-40e5-a8b6-c6bb08322fda)

# COMPLETAR

# COLOCAR UNA CAPTURA DE PANTALLA  DEL ACCESO http://localhost:3000

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/91b72f6a-d20a-4d73-a7cb-b654cca575a8)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/b37aeda7-f972-4148-b770-84636cd13449)


### Para mapear más de un puerto

```
docker run -d --name <nombre contenedor> -p <puerto host 01>:<puerto contenedor 01> -p <puerto host 02>:<puerto contenedor 02> <nombre imagen>:<tag>
```

Crear un contenedor a partir de la imagen rabbitmq version management-alpine, para este mapeo de puertos usar en el host los mismos puertos del contenedor.

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/2a0b408a-9a5d-45bf-a72b-46fc54f57ec8)

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/5f045795-3e2d-4153-9701-7074f0b349db)


