# DNS Caching and Fordwarding Server

## 1. Configuracion caché DNS

En primer lugar actualizamos los paquetes de nuestra maquina ubuntu
```
sudo apt update
```
![image](https://github.com/user-attachments/assets/8e2ffd44-781c-42c4-b9cd-8c9a30f419f3)

Instalamos Bind9
```
sudo apt install bind9 bind9utils bind9-doc
```
![image](https://github.com/user-attachments/assets/8d0b89ab-4339-4cd4-96d2-c02808859b82)

Ahora vamos a editar el fichero de configuración
```
cd /etc/bind
```

```
sudo nano named.conf.options
```

![image](https://github.com/user-attachments/assets/910a1266-b6f1-4959-9ed9-a02c2907b4a0)

Una vez dentro del fichero borramos los comentarios y tenemos que tener algo asi:

![image](https://github.com/user-attachments/assets/1128327d-e96d-4bb3-b654-edcc09325e03)

Después tendremos que añadir un nuevo bloque acl encima de options, para configuar y saber que dispositivos tenranacceso a la DNS

![image](https://github.com/user-attachments/assets/4c89b6fd-7877-4f4e-a6ed-945c87bdd7fe)


Y añadir lo siguiente en el bloque options para que se apliquen los cambios acl

![image](https://github.com/user-attachments/assets/ae532eb2-f71c-46de-8b83-556a54ce5d53)

## 2. Configurar como servidor DNS de reenvío

Ahora tendremos que añadir las IPs recursivas a options:

![image](https://github.com/user-attachments/assets/191468c0-ffcb-4c2f-8f62-c740c16787b5)

![image](https://github.com/user-attachments/assets/74c42527-611b-4368-aa07-f384180bbb24)

Ejecutamos los siguientes comandos para comprobar que todo funciona bien
```
sudo named-checkconf
```
```
sudo systemctl restart bind9
```
```
sudo ufw allow Bind9
```

![image](https://github.com/user-attachments/assets/1f876792-225c-4471-9566-19320c2eb721)

Nos queda comprobar en la maquina cliente windows:
```
nslookup www.google.com 10.4.0.139
```
![image](https://github.com/user-attachments/assets/28f92f17-6168-4165-b77a-444c07862036)

![image](https://github.com/user-attachments/assets/896dc56d-acfc-4eb5-a318-dd47a94c5a8b)









