# Actividad 2 Docker
### 1. Ejecuta la imagen "hello-world"

Utilizamos el siguiente comando para ejecutar la imagen 

```
sudo docker run hello-world
```
![image](https://github.com/user-attachments/assets/57f79f58-46e3-4ab1-8b01-6306cff40b75)

Con el siguiente comando comprobaremos los contenedores creados

```
sudo docker ps -a
```
![image](https://github.com/user-attachments/assets/8e5b1e94-6aab-456f-9f8b-a08407086aba)


### 2. Muestra las imágenes Docker instaladas

Con este comando vemos que imágenes tenemos instaladas

```
sudo docker images
```
![image](https://github.com/user-attachments/assets/a0ee03e6-fb08-4716-abab-9985fcbe48b6)


### 3. Muestra los contenedores Docker

Con el comando siguiente mostramos los contenedores

```
sudo docker ps -a
```
![image](https://github.com/user-attachments/assets/8fe9948d-1e03-4f76-8ea1-4f68500a7be1)


### 4. Edita el fichero Dockerfile

Para llevar a cabo este apartado copiaremos un repositorio de Github 

```
sudo git clone https://github.com/docker/getting-started-app.git
```
![image](https://github.com/user-attachments/assets/e05bc24a-db7c-4adf-9b3d-771d48c50c5e)


Y editamos el fichero Dockerfile

```
FROM node:lts-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```
![image](https://github.com/user-attachments/assets/91d692bc-6460-4dbc-89e7-d5b617ca44d4)
### 5. Construye el contenedor

Utilizamos el comando que se muestra a continuación

```
sudo docker build -t getting-started .
```
![image](https://github.com/user-attachments/assets/dfdca4e3-991b-44aa-9b97-5d95ef6f9724)


### 6. Ejecútalo

Y se ejecuta con el comando run

```
sudo docker run -d -p 127.0.0.1:3000:3000 getting-started
```
![image](https://github.com/user-attachments/assets/db51babf-d0d5-45e1-a27a-a6737a6d0cfd)

Comprobamos que funciona

![image](https://github.com/user-attachments/assets/57840e95-4db8-4e95-8693-7de648c8672e)

![image](https://github.com/user-attachments/assets/c1655500-a63c-4fa4-964f-3b8667faa6d5)



