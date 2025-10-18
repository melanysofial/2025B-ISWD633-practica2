## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
```
docker network create net-wp -d bridge
```

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
```
docker run --name mysql --network net-wp -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wp_user -e MYSQL_PASSWORD=wp_pass -d mysql:8
```

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR
```
docker run --name wordpress --network net-wp -e WORDPRESS_DB_HOST=mysql:3306 -e WORDPRESS_DB_NAME=wordpress -e WORDPRESS_DB_USER=wp_user -e WORDPRESS_DB_PASSWORD=wp_pass -p 9300:80 -d wordpress
```

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **9300**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/159664c8-91d5-465d-8e04-29d6f6cc9f63" />


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/933a9bb0-7d14-407c-b4e3-77757c0c2157" />


### Eliminar el contenedor wordpress
```
docker rm -f wordpress
```

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?

La configuración anterior se mantiene ya que la información se guarda en la base de datos de mysql.

