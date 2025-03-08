# Actividad 5

En la siguiente actividad desplegaremos diferentes aplicaciones utilizando docker compose

## Despliegue app Temperaturas

### Creacion estructura(.yaml)

En primer lugar tendremos que crear un archivo.yaml que contiene la estructura de la aplicacion(frontend+backend)
```
version: '3.1'
services:
  frontend:
    container_name: temperaturas-frontend
    image: iesgn/temperaturas_frontend
    restart: always
    ports:
      - 8081:3000
    environment:
      TEMP_SERVER: temperaturas-backend:5000
    depends_on:
      - backend
  backend:
    container_name: temperaturas-backend
    image: iesgn/temperaturas_backend
    restart: always
```
![image](https://github.com/user-attachments/assets/626f6fa2-076d-4684-8a5d-2905c9c9713d)
### Despliegue contenedores

Con el siguiente comando se desplegaran e iniciaran los contenedores del archivo .yaml 
```
sudo docker compose up -d
```
![image](https://github.com/user-attachments/assets/33431e20-6712-4a0a-8778-e6caf6c4f286)

### Verificación ejecución contenedores

Pra comprobar que se han inicado los contenedores ejecutamos el siguiente comando
```
sudo docker ps
```
![image](https://github.com/user-attachments/assets/338f6cf2-d12c-4323-a3fb-905c60d2a1aa)

![image](https://github.com/user-attachments/assets/58f1a61f-5975-449b-85cf-23d23559d5d3)

## Despliegue Wordpress con MariaDB

### Creacion estructura(.yaml)

En primer lugar tendremos que crear un archivo.yaml como en el apartado anterior que contiene la estructura de la aplicacion(frontend+backend)
```
version: '3.1'
services:
  wordpress:
    container_name: servidor_wp
    image: wordpress
    restart: always
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: user_wp
      WORDPRESS_DB_PASSWORD: asdasd
      WORDPRESS_DB_NAME: bd_wp
    ports:
      - 80:80
    volumes:
      - wordpress_data:/var/www/html/wp-content
  db:
    container_name: servidor_mysql
    image: mariadb
    restart: always
    environment:
      MYSQL_DATABASE: bd_wp
      MYSQL_USER: user_wp
      MYSQL_PASSWORD: asdasd
      MYSQL_ROOT_PASSWORD: asdasd
    volumes:
      - mariadb_data:/var/lib/mysql
volumes:
    wordpress_data:
    mariadb_data:
```
![image](https://github.com/user-attachments/assets/0a661dda-6940-4130-9fea-0a2ec5edc28c)

### Despliegue contenedores

Con el siguiente comando se desplegaran e iniciaran los contenedores del archivo .yaml 
```
sudo docker compose up -d
```
Hemos tenido que borrar servidro_mysql e instalarlo nuevamente ya que nos daba error

![image](https://github.com/user-attachments/assets/3ce2ea9f-5121-4b72-89d9-407390186c1f)
![image](https://github.com/user-attachments/assets/22e041bb-41c3-4ddd-b2ea-1e4c98003ffe)
### Verificación ejecución contenedores

Pra comprobar que se han inicado los contenedores ejecutamos el siguiente comando
```
sudo docker ps
```
![image](https://github.com/user-attachments/assets/1c3d318c-1d9f-444f-971b-a0c545690765)



