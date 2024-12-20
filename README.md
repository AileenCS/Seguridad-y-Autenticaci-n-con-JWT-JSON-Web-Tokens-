# Seguridad y Autenticación con JWT (JSON Web Tokens)

"Este proyecto establece un entorno Flask para gestionar la autenticación y seguridad mediante el uso de JSON Web Tokens (JWT). Además, emplea NGINX como servidor proxy para manejar las solicitudes de la API de forma eficiente."

## Requisitos

- Docker (para ejecutar el contenedor de NGINX)
- Python 3.x
- Flask
- Postman (para realizar pruebas)

## Pasos para configurar y ejecutar el proyecto


1. Iniciar el contenedor de NGINX
Para iniciar el contenedor de NGINX, usa el siguiente comando:

´´´bash
sudo docker start nginx´´´

Accede al contenedor de NGINX:

´´´bash
sudo docker exec -it nginx bash

´´´
Dentro del contenedor, navega a la carpeta donde crearás el proyecto. Por ejemplo:


cd myproject

2. Configuración del entorno virtual
Crea un entorno virtual:

bash

python3 -m venv .venv
Activa el entorno virtual:

En MacOS/Linux:

source .venv/bin/activate



3. Instalar las dependencias necesarias
Dentro del entorno virtual, instala Flask y las librerías necesarias:


pip install flask flask-jwt-extended bcrypt


4. Crear el archivo de la aplicación Flask

vim session.py

5. Configuración de NGINX
Accede al archivo de configuración de NGINX:


cd /etc/nginx/
vim nginx.conf

Agrega las configuraciones necesarias para dirigir las solicitudes a la API de Flask.

6. Reiniciar NGINX
Guarda los cambios en nginx.conf y reinicia NGINX para aplicar las nuevas configuraciones:


sudo service nginx restart
7. Verificar la API en Postman
Abre Postman y realiza las pruebas de tu API utilizando las rutas que hayas implementado, como /register, /login, /protected, etc.
