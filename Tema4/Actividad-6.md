# Actividad 6

## Construir imagen con PHP

### Crear dockerfile para ap.web Apache con PHP
```
# syntax=docker/dockerfile:1
FROM debian:stable-slim
RUN apt-get update && apt-get install -y apache2 libapache2-mod-php7.4 php7.4 && apt-get clean && rm -rf /var/lib/apt/lists/* && rm /var/www/html/index.html
COPY app /var/www/html/
EXPOSE 80
CMD apache2ctl -D FOREGROUND
```
![image](https://github.com/user-attachments/assets/a8a68c96-6832-4481-9ee1-991d983ec9de)


### Construir imagen Docker
```
sudo docker build -t josedom24/ejemplo2:v1 .
```
![image](https://github.com/user-attachments/assets/d39fcfb5-7437-4365-a38e-a4b5f3d0b627)

### Ejecutar contenedor
```
sudo docker run -d -p 80:80 --name ejemplo2 josedom24/ejemplo2:v1
```
![image](https://github.com/user-attachments/assets/1e49b594-25d7-498d-9662-fb3b91763ea9)

### Comprobar funcionamiento
![image](https://github.com/user-attachments/assets/aec27a2b-820e-44fb-b6a8-1fa5ef3d0178)

## Construir imagen con Python

### Crear dockerfile para app Python
```
# syntax=docker/dockerfile:1
FROM debian:12
RUN apt-get update && apt-get install -y python3-pip  && apt-get clean && rm -rf /var/lib/apt/lists/*
WORKDIR /usr/share/app
COPY app .
RUN pip3 install --no-cache-dir --break-system-packages -r requirements.txt
EXPOSE 3000
CMD python3 app.py
```
![image](https://github.com/user-attachments/assets/82584a6c-a513-45b6-83b7-c8026090aa1e)

### Construir imagen Docker
```
sudo docker build -t josedom24/ejemplo3:v1 .
```
![image](https://github.com/user-attachments/assets/443e58b6-a5ab-4eb3-a47e-75b041eda605)

### Ejecutar contenedor
```
sudo docker run -d -p 80:3000 --name ejemplo2 josedom24/ejemplo3:v1
```
![image](https://github.com/user-attachments/assets/840f3d5d-7fa5-4ab4-b21b-0107f3fd5502)

### Comprobar funcionamiento
![image](https://github.com/user-attachments/assets/77d21d0e-bb53-42b8-bde3-04608ff44a17)



