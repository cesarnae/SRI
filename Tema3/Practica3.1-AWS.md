# 1. Crear VPC
En primer lugar, iniciamos y entramos en el laboratorio 

![image](https://github.com/user-attachments/assets/3dfed35c-6ba1-4832-9b28-2dcd06aa7135)

Ahora crearemos la VPC, para ello buscamos el apartado y vamos a proceder a crearla.

![image](https://github.com/user-attachments/assets/c8e5acf5-268f-46f5-8f4b-0505caf84ba5)
![image](https://github.com/user-attachments/assets/8ca5871d-9074-45ad-9713-dc5ce50e458c)

Configuramos la VPC como se indica en las capturas, asignamos un nombre, bloque CIDR 10.2.0.0/16, configuramos las subredes y finalmente le damos a crear VPC.

![image](https://github.com/user-attachments/assets/b0713522-8296-490e-b39d-82c601230152)

![image](https://github.com/user-attachments/assets/46cef799-f1be-4587-a9a9-75ebf2f89552)

![image](https://github.com/user-attachments/assets/69e0665e-f7bf-4483-8f6d-45985a2f7154)

Finalmete se empieza a crear y no saldra lo siguiente:

![image](https://github.com/user-attachments/assets/f213e1c1-b3db-4484-bc3e-27ab04d9f066)

![image](https://github.com/user-attachments/assets/c2088aa3-0945-4098-af28-bdde7a90a968)

# 2. Creación máquinas EC2

Buscamos EC2

![image](https://github.com/user-attachments/assets/60df5275-6d55-4c99-a0d5-5d7fcb8f74a5)

Y vamos a lanzar la instancia

![image](https://github.com/user-attachments/assets/0599a11e-f346-45ef-bfcd-48cbc9dca675)

Para crearla le popnemos un nombre, elegimos el SO(ubuntu) 

![image](https://github.com/user-attachments/assets/15bd4db6-5fe6-4ce7-961a-8613ecc5cdd3)

Elegimos el tipo de instancia y usamos vockey en el par de claves

![image](https://github.com/user-attachments/assets/a46e4fc3-fca7-446e-954a-d37bd754a4c9)

A la hora de configurar la red utilizamos la VPC creada y creamos un grupo de seguridad 

![image](https://github.com/user-attachments/assets/faca6918-599f-4a6f-a347-c09d980e6ec2)

Creamos otra regla de seguridad más con HTTP y lanzamos la instancia 

![image](https://github.com/user-attachments/assets/030d1f3b-9059-4b1d-b6ca-670493b811c8)

Comprobamos que ha sido creada con éxito

![image](https://github.com/user-attachments/assets/6e166c17-c4c4-420d-9d89-41e4fe21aa4a)

# 3. Instalación de Apache y PHP 

Actuzalizamos ubuntu 

![image](https://github.com/user-attachments/assets/7e874bca-d83f-460d-85b5-8289f03e2fc6)
![image](https://github.com/user-attachments/assets/8884a2b1-11d5-47ec-8185-2044fe3f567e)

Instalamos e iniciamos Apache

```
sudo apt install apache2
sudo systemctl start apache2
sudo systemctl enable apache2
```

![image](https://github.com/user-attachments/assets/5a703d44-99c1-460e-b870-2893519771e4)
![image](https://github.com/user-attachments/assets/ba2b5bc5-9e40-4618-a5e9-47449276a394)
![image](https://github.com/user-attachments/assets/7cca66ec-5045-4f3a-83cd-a904d7a2d412)

Comprobamos la correcta instalación buscandolo en el navegador mediante la ip publica de la máquina

![image](https://github.com/user-attachments/assets/84a8dcf9-17c9-4b30-b284-d3829abe2aa7)

Ahora procedemos a instalar y reiniciar PHP  con los siguientes comandos
```
sudo add-apt-repository ppa:ondrej/php
sudo apt install php7.4 libapache2-mod-php7.4 php7.4-cli
sudo apt install php7.4-mysql
sudo systemctl restart apache2
```
![image](https://github.com/user-attachments/assets/c1c432b7-6023-420d-9aad-d6855ee6bc5d)
![image](https://github.com/user-attachments/assets/bc7a90f8-a4b2-4793-b522-6385a6dc890b)
![image](https://github.com/user-attachments/assets/9ca81a58-2e8e-4886-8472-85feb56a3b40)
![image](https://github.com/user-attachments/assets/331228b5-5bb3-41f2-80c9-5bfba83ff445)

# 4. Crear base de datos

Buscamos y vamos al apartado rds para crear la base de datos

![image](https://github.com/user-attachments/assets/4605cefb-0ab6-4cf9-ab76-e62d43b11ff5)
![image](https://github.com/user-attachments/assets/f4e50c05-f339-43d1-8f01-a5dcc24a7798)

Elegimos el tipo de base de datos

![image](https://github.com/user-attachments/assets/91b597df-5932-4659-a041-9e68db0f329b)

Seleccionamos la capa gratuita

![image](https://github.com/user-attachments/assets/39b76057-6007-4032-a2dc-febc2bf85221)

Asignamos nombre a la bd, usuario y contraseña

![image](https://github.com/user-attachments/assets/789b9043-d726-45d2-8b4c-488ca5ab509a)

En configuracion de la instancia y almacenamiento lo dejamos igual

![image](https://github.com/user-attachments/assets/4ea319f3-b38b-48c7-a276-61936b4d9c2f)

Suguimos los pasos

![image](https://github.com/user-attachments/assets/fdfddc8d-910a-4cde-90ae-e62c30991519)
![image](https://github.com/user-attachments/assets/62e103c7-259b-40d1-8488-0e4e80d50ac3)

Ponemos el nombre de la base de datos y la creamos

![image](https://github.com/user-attachments/assets/1dbe6f1f-b8b4-4431-aa66-ef2f61666b26)
![image](https://github.com/user-attachments/assets/8a43cedc-c7d0-4113-91d4-20ab84ca7978)

Finalmente queda creada

![image](https://github.com/user-attachments/assets/f6d13e83-544f-4144-93be-9834078506bf)


Ahora configuramos la conexión seleccionando nuestra instancia EC2

![image](https://github.com/user-attachments/assets/c735b9bb-a1ba-4f0c-8afc-37312110c348)
![image](https://github.com/user-attachments/assets/d55bf2dc-61c0-448d-8ccc-493c7a2f23d4)

Y le damos a configurar

![image](https://github.com/user-attachments/assets/6a6d6840-8874-40ab-a97f-b397da9b5214)

![image](https://github.com/user-attachments/assets/a65899bc-8381-4525-9d14-a498b6e3aead)

# 5. Crear sistemas de archivo EFS

Buscamos EFS, vamos a sistemas de archivos y crear un sistema de archivos

![image](https://github.com/user-attachments/assets/b770e38f-98de-4097-9e53-d90b9c8f0a03)

![image](https://github.com/user-attachments/assets/fb649bc3-bcb1-419a-8eb5-edd0d6f71637)

Asignamos nombre y VPC

![image](https://github.com/user-attachments/assets/3b524111-8cd6-4c69-83b5-61f2ca3ab311)

![image](https://github.com/user-attachments/assets/885c9b52-c071-4f1d-b545-a97e1021880a)

Ahora iremos a VPC y añadimos una regla de entrada

![image](https://github.com/user-attachments/assets/81f1c5bc-1cd7-4f5a-98c6-dc2dfee6858c)

![image](https://github.com/user-attachments/assets/33631fe5-86bc-44d5-97e8-a01996d324b7)

Ahora vamos a EFS y en el apartado de red cambiamos el grupo de seguridad

![image](https://github.com/user-attachments/assets/e7ea2c9c-6128-483d-b4d1-7ac664037aa9)

Y lo asociamos con nuestra instancia

![image](https://github.com/user-attachments/assets/e3fc2088-7c18-4ae3-916c-6c3c282e3e90)

Seleccionamos montaje a través de IP y copiamos el código que aparece

![image](https://github.com/user-attachments/assets/a7e8ffd6-9f8e-4661-9e58-b60d854b66b2)

Previamente, instalamos NFS y ahora copiamos el código anterior

```
sudo apt install nfs-common
sudo mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 10.2.2.118:/ efs
```

![image](https://github.com/user-attachments/assets/6ae5227f-e8c9-4c22-9703-4776c86a26c3)

![image](https://github.com/user-attachments/assets/2ac18f6c-9307-4613-9508-2626db52eb55)


















