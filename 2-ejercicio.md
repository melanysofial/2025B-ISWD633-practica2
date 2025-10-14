### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
```
docker run -d --name postgres -e POSTGRES_PASSWORD=mysecretpassword postgres:15-alpine3.21
```

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

```
docker run -d --name pgadmin_cliente -e PGADMIN_DEFAULT_EMAIL=admin@admin.com -e PGADMIN_DEFAULT_PASSWORD=admin123 -p 8080:80 dpage/pgadmin4
```

La figura presenta el esquema creado en donde los puertos son:
- a: 5432
- b: 80
- c: 8080

![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/75d0aa8a-c927-49ad-9184-28212048cc0e" />
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/1c3424ff-52a3-4086-8f2d-b12bbf227ff9" />

Para permitir la comunicación de los contenedores se creó una red personalizada, permitiendo la comunicación directa y estable.

```
#Para crear la red
docker network create postgres-net
#Se conectan los contenedores a la red
docker network connect postgres-net postgres
docker network connect postgres-net pgadmin_cliente
#Para verificar que estén en la misma red
docker network inspect postgres-net 

```
<img width="3840" height="2100" alt="image" src="https://github.com/user-attachments/assets/66e83998-506d-4a8a-9c56-21eb342aedef" />

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.
```
#En la interfaz de usuario
CREATE TABLE personas (id serial PRIMARY KEY, nombre varchar(100));
INSERT INTO personas (nombre) VALUES ('Melany'), ('Dilan');
```

## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info

```
docker exec -it postgres bash
psql -U postgres -d info
```

### Realizar un select *from personas

```
select * from personas;
```

<img width="633" height="284" alt="image" src="https://github.com/user-attachments/assets/baca47d8-8298-4f9a-9471-6401ca7c363a" />


