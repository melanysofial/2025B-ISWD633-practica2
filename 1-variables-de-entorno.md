# Variables de Entorno
### ¿Qué son las variables de entorno?
Valores que el sistema operativo o una aplicación utiliza para configurar su comportamiento.
Variables dinámicas.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

```
docker create --name variablen nginx:alpine -e username=ml -e role=admin
```

<img width="956" height="300" alt="image" src="https://github.com/user-attachments/assets/bf308119-700f-46d4-99f7-438c55f41224" />


### Crear un contenedor con la imagen de mysql, mapear todos los puertos
```
docker run --name mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:8
```

### ¿El contenedor se está ejecutando?
No, para revisar debemos poner docker ps -a

### Identificar el problema
<img width="1226" height="235" alt="image" src="https://github.com/user-attachments/assets/5677912d-0e55-4cd8-9fc5-d739cf4a18f1" />


### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 

### ¿Qué bases de datos existen en el contenedor creado?
```
docker ps
docker exec -it some-mysql bash
mysql -u root -p
SHOW DATABASES;
```
En el contenedor creado de mysql se encuentran las 4 bases predeterminadas: information_schema, mysql, performance_schema, sys.
<img width="341" height="252" alt="image" src="https://github.com/user-attachments/assets/0cdc3301-fd5b-40a8-8f1b-a501fd0562ca" />

