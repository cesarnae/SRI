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












