# 📚 Tienda de Libros en Línea

Proyecto académico de una tienda virtual de libros, desarrollado como parte del curso de Programación Web I. Incluye funcionalidades completas para usuarios y administradores, integrando frontend, backend, base de datos y contenedores Docker.

## 🧰 Tecnologías utilizadas

- HTML, CSS, JavaScript
- Perl con CGI
- MySQL (MariaDB)
- Docker (con Apache y MariaDB en contenedores separados)

## 🚀 Funcionalidades

### Para usuarios:
- Visualización de libros disponibles
- Búsqueda por nombre
- Carrito de compras (agregar, eliminar, actualizar)
- Registro e inicio de sesión
- Gestión de perfil y método de pago

### Para administradores:
- Dashboard de administración
- Alta, edición y baja de libros
- Asociación de libros a tiendas con stock
- Gestión de tiendas

## 🗄️ Base de datos

Incluye tablas para:
- Usuarios
- Libros
- Tiendas
- Tarjetas
- Inventario

Con claves primarias y foráneas correctamente diseñadas para mantener integridad referencial.

## 📦 Estructura del sistema

- Contenedor 1: Servidor web Apache + Perl (CGI)
- Contenedor 2: MariaDB con persistencia
- Comunicación entre frontend y backend vía AJAX

## 🖼️ Capturas de pantalla

#### Página de inicio
![image](https://github.com/user-attachments/assets/55f3a365-6184-4fcf-aa8e-afb2ebd0385b)

#### Buscador de libros
![image](https://github.com/user-attachments/assets/e1490c0a-670a-4a6f-8b1f-de57c4d2da6e)

#### Inicio de sesión y registro
![image](https://github.com/user-attachments/assets/5b6bdf03-600a-425c-9d07-e05fc2641b5b)

![image](https://github.com/user-attachments/assets/2eb9caf5-b730-44c0-b412-dfc28043d30b)

#### Método de pago
![image](https://github.com/user-attachments/assets/92d929f8-5142-4b62-8158-96f484876b44)

#### Carrito de compras
![image](https://github.com/user-attachments/assets/db3755e5-2fa9-4761-956c-1cf250b1ad5a)

#### Panel de administrador
![image](https://github.com/user-attachments/assets/9a84380a-9fa9-4b51-b9f9-8f1aea86f43a)





  

COMANDOS CONSTRUCCION DOCKER:

docker build -f Dockerfile.web -t server-web .
docker run -d -p 8112:80 --name server-web server-web


docker build -f .\Dockerfile.db -t biblioteca-db .
docker run -d --name biblioteca-db -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=biblioteca -p 3307:3306 biblioteca-db


Red:
docker network create biblioteca-network
docker network connect biblioteca-network server-web
docker network connect biblioteca-network biblioteca-db

Bash para ambos

docker exec -it biblioteca-db /bin/bash
