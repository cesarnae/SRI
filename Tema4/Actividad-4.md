# Actividad 3
En la siguiente actividad mostraremos tres  ejemplos desplegando aplicaciones con el uso de Docker.

## 1. Despliegue Tomcat + Nginx
### Crear red docker
```
sudo docker network create red_tomcat
```
![image](https://github.com/user-attachments/assets/deb47ade-8b0b-4234-baed-6eecc172484f)

### Desplegar contenedor Tomcat
```
sudo docker run -d --name aplicacionjava \
                --network red_tomcat \
                -v /home/vagrant/tomcat/sample.war:/usr/local/tomcat/webapps/sample.war:ro \
                tomcat:9.0
```
![image](https://github.com/user-attachments/assets/3c905d37-acee-42e8-b21c-90dcb6b1ffe4)

### Desplegar Nginx como proxy inverso
```
sudo docker run -d --name proxy \
                -p 80:80 \
                --network red_tomcat \
                -v /home/vagrant/tomcat/default.conf:/etc/nginx/conf.d/default.conf:ro \
                nginx
```
![image](https://github.com/user-attachments/assets/f210900b-3e3b-4cca-a1c7-3d83dd39d4d0)

### Comprobar despliegue

Comprobamos accediendo a nuestro localhost

![image](https://github.com/user-attachments/assets/47615820-e715-4cd5-804a-4f41f171bc16)

## 2. Despliegue app Temperaturas
### Crear red docker
```
sudo docker network create red_temperaturas
```
![image](https://github.com/user-attachments/assets/28461c4f-20f6-4bf3-8eda-748b2699cdf1)

### Desplegar backend
```
sudo docker run -d --name temperaturas-backend --network red_temperaturas iesgn/temperaturas_backend
```
![image](https://github.com/user-attachments/assets/095b3301-9b7c-4ea0-93fa-70411335b790)

### Desplegar frontend + asignar puerto 3000
```
docker run -d -p 3000:3000 --name temperaturas-frontend --network red_temperaturas iesgn/temperaturas_frontend
```
![image](https://github.com/user-attachments/assets/575fd966-e416-48e9-83d9-7ce334c2596d)

### Comprobar despliegue y funcionamiento

Comprobamos accediendo a https://localhost:3000
![image](https://github.com/user-attachments/assets/d5bb2928-2d46-4415-a819-e6fccb11de13)

![image](https://github.com/user-attachments/assets/7c614c90-4e5b-4f48-a512-789a294bafd9)

## 3. Despliegue Wordpress + Mariadb
### Crear red docker
```
sudo docker network create red_wp
```
![image](https://github.com/user-attachments/assets/c930b4b2-09c1-47f1-8bcf-2de13fff88f3)

### Desplegar contenedor MariaDB
```
sudo docker run -d --name servidor_mysql \
                --network red_wp \
                -v /opt/mysql_wp:/var/lib/mysql \
                -e MYSQL_DATABASE=bd_wp \
                -e MYSQL_USER=user_wp \
                -e MYSQL_PASSWORD=asdasd \
                -e MYSQL_ROOT_PASSWORD=asdasd \
                mariadb
```
![image](https://github.com/user-attachments/assets/20543441-5802-4e22-b36d-4eac909d5b60)


### Desplegar Wordpress enlazandolo a la base de datos
```
sudo docker run -d --name servidor_wp \
                --network red_wp \
                -v /opt/wordpress:/var/www/html/wp-content \
                -e WORDPRESS_DB_HOST=servidor_mysql \
                -e WORDPRESS_DB_USER=user_wp \
                -e WORDPRESS_DB_PASSWORD=asdasd \
                -e WORDPRESS_DB_NAME=bd_wp \
                -p 123:123 \
                wordpress
```
![image](https://github.com/user-attachments/assets/dae75c6e-255f-436d-a90a-84ea62178fc0)

### Comprobar despliegue

Este comando nos devuelve la ip para acceder a Wordpress en el navegador

```
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' servidor_wp
```
![image](https://github.com/user-attachments/assets/8e9b720c-7acd-418b-9396-8e39b9e49885)

Finalmente accedemos a Wordpress

![image](https://github.com/user-attachments/assets/5f0cb220-a8f3-438b-b11f-95bf237aa631)





