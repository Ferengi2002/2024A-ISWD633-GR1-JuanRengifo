## Esquema para el ejercicio
![Imagen](imagenes/esquema-ejercicio3.PNG)

### Crear red net-wp
```
docker network create net-wp
```
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/fa52ffe1-7d83-46a3-9159-f183f4d5f415)


### Para que persista la información es necesario conocer en dónde mysql almacena la información.
En el esquema del ejercicio la carpeta contenedor (a) es /var/lib/mysql.
Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?
La carpeta db del host contiene los archivos de base de datos de MySQL, tales como archivos de tabla, logs de transacciones, etc.

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD
```
docker run -d --name my_mysql --network net-wp -e MYSQL_ROOT_PASSWORD=my_root_password -e MYSQL_DATABASE=my_database -e MYSQL_USER=my_user -e MYSQL_PASSWORD=my_password -v C:\Users\MyHP\Documents\GitHub\2024A-ISWD633-GR1-JuanRengifo\practica3\ejercicio3\db:/var/lib/mysql mysql:8
```
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/7c24fa4f-c6a1-4172-84ee-cd3a7812c80e)


### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
La carpeta db ahora contiene los archivos y directorios de base de datos MySQL, incluyendo los datos del sistema, las tablas, logs de transacciones, y archivos de configuración de la base de datos my_database.
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/c77f40cb-aa96-4642-85cc-ed3a4ec88fc9)


### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
En el esquema del ejercicio la carpeta contenedor (b) es /var/www/html
Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
```
docker run -d --name my_wordpress --network net-wp -p 80:80 -e WORDPRESS_DB_HOST=my_mysql:3306 -e WORDPRESS_DB_USER=my_user -e WORDPRESS_DB_PASSWORD=my_password -e WORDPRESS_DB_NAME=my_database -v C:\Users\MyHP\Documents\GitHub\2024A-ISWD633-GR1-JuanRengifo\practica3\ejercicio3\www:/var/www/html wordpress
```

![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/d9e6b617-6514-4de9-9a33-3e1a2fcfc32d)



### Personalizar la apariencia de wordpress y agregar una entrada
![image](https://github.com/Ferengi2002/2024A-ISWD633-GR1-JuanRengifo/assets/100974435/34d109f4-eea6-471c-a922-c1feab571709)


### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?
Cuando eliminas y creas nuevamente el contenedor de WordPress utilizando los mismos volúmenes, la personalización y las entradas que agregaste persisten. Esto sucede porque los datos se almacenan en las carpetas host (.../ejercicio3/www para WordPress y .../ejercicio3/db para MySQL) que no se borran al eliminar los contenedores.



