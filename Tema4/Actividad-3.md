# Actividad 3 Docker

En los siguientes apartados descargaremos las diferentes imágenes

### 1. Descarga la imagen de ubuntu
```
sudo docker pull ubuntu
```
![image](https://github.com/user-attachments/assets/8ce61d96-6456-40a1-8387-36a870c50b9b)

### 2. Descarga la imagen de hello-world
```
sudo docker pull hello-world
```
![image](https://github.com/user-attachments/assets/4bacaca4-7336-4c5c-a13f-8dc0e8e7c905)

### 3. Descarga la imagen nginx
```
sudo docker pull nginx
```
![image](https://github.com/user-attachments/assets/ba74220c-7879-4e5a-ac78-c50aaf72926c)

### 4. Muestra un listado de todas la imágenes
```
sudo docker images
```
![image](https://github.com/user-attachments/assets/3e3a6a87-4f9d-4263-84be-c87fcc484f74)


### 5. Ejecuta un contenedor hello-world y dale nombre “myhello1”
```
sudo docker run --name myhello1 hello-world
```
![image](https://github.com/user-attachments/assets/f6f3ee83-1af4-4e60-8742-8c0bf5fc87f2)

### 6. Ejecuta un contenedor hello-world y dale nombre “myhello2”
```
sudo docker run --name myhello2 hello-world
```
![image](https://github.com/user-attachments/assets/90d67cde-513b-42fa-a6a4-548882c2a0bb)

### 7. Ejecuta un contenedor hello-world y dale nombre “myhello3”
```
sudo docker run --name myhello3 hello-world
```
![image](https://github.com/user-attachments/assets/0e11a6af-cb15-400c-b6ea-5dfbceadfd84)

### 8. Muestra los contenedores que se están ejecutando
```
sudo docker ps
```
![image](https://github.com/user-attachments/assets/78dadec6-885b-4af1-afd3-45f101473631)

### 9. Para el contenedor "myhello1”
```
sudo docker stop myhello1
```
![image](https://github.com/user-attachments/assets/68ff2578-0b07-4e2c-b3b4-2a11e53686ad)

### 10. Para el contenedor "myhello2”
```
sudo docker stop myhello2
```
![image](https://github.com/user-attachments/assets/5808bdb7-a6bf-499c-b376-76a0a3ab2453)

### 11. Borra el contenedor “myhello1”
```
sudo docker rm myhello1
```
![image](https://github.com/user-attachments/assets/e180ee0f-67a3-4c66-927b-7fa54caff9ec)

### 12. Muestra los contenedores que se están ejecutando.
```
sudo docker ps
```
![image](https://github.com/user-attachments/assets/a41e1653-f510-4919-aa7c-6f4c6052a4d0)

### 13. Borra todos los contenedores
```
sudo su
docker rm $(docker ps -a -q)
```
![image](https://github.com/user-attachments/assets/37820aa5-4fcb-42e1-9b84-cfb881051313)


