# Variables de Entorno
### ¿Qué son las variables de entorno

Las variables de entorno son pares clave-valor que se utilizan para pasar configuraciones y parámetros importantes a aplicaciones y servicios en contenedores Docker. Estas variables permiten que los contenedores sean configurables y portables, facilitando la personalización del comportamiento de las aplicaciones sin necesidad de modificar el código fuente.


### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETAR

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/af7e91c6-5c2a-4bb7-8537-a6708cbf8aa7)


### Crear un contenedor con mysql:8 , mapear todos los puertos

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/9dbb84d0-3df1-4e36-9909-9997cb8512db)

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/0bc2bd6e-d6e4-4dd2-b229-d854e187e5f7)

### ¿El contenedor se está ejecutando?

Si:
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/8f78f1fa-4044-44ad-a88f-8b4fbdbfa92a)
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/55c34d61-ae10-4c2c-912d-76e342f486fd)


# COMPLETAR

### Identificar el problema
# COMPLETAR

### Eliminar el contenedor creado con mysql:8 
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/868db60d-a117-4d33-9484-61c9b4a28fd3)


### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

Previo a esto es necesario crear el archivo y colocar las variables en un archivo, **.env** se ha convertido en una convención estándar, pero también es posible usar cualquier extensión como **.txt**.
```
docker run -d --name <nombre contenedor> --env-file=<nombreArchivo>.<extensión> <nombre imagen>
```
**Considerar**
Es necesario especificar la ruta absoluta del archivo si este se encuentra en una ubicación diferente a la que estás ejecutando el comando docker run.

### Crear un contenedor con mysql:8 , mapear todos los puertos y configurar las variables de entorno mediante un archivo
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/29f52f1c-244b-48d2-b8a8-039756f78130)

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/28a5f58d-fa55-45a5-a2c2-3791722d7dd9)

# COMPLETAR

 ![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/42419c2e-117a-4c22-b304-573212a9015f)


### ¿Qué bases de datos existen en el contenedor creado?
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/399382bf-dfbd-4de6-a330-8bfeab3d9144)
