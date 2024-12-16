# Usando una instancia AWS debemos instalar Apache con las siguientes opciones de configuración:
En primer lugar ejecutamos los siguientes comandos para actualizar paquetes e instalamos Apache

![AWS](Imagenes/aws.PNG)

![AWS](Imagenes/aws1.PNG)

![AWS](Imagenes/aws2.PNG)

## 1. Activar la autenticación con MySql

**Instalamos PHP y MARIADB**

![AWS](Imagenes/aws3.PNG)

![AWS](Imagenes/aws4.PNG)

![AWS](Imagenes/aws5.PNG)

**Activación servicios**

![AWS](Imagenes/aws6.PNG)

**Entramos a mysql y creamos la base de datos**

![AWS](Imagenes/aws7.PNG)

**Otorgamos permisos al admin**

![AWS](Imagenes/aws8.PNG)

**Entramos a la base de datos**

![AWS](Imagenes/aws10.PNG)

Creamos una tabla para usuarios 

![AWS](Imagenes/aws11.PNG)

**Pasamos contraseña a hash**

![AWS](Imagenes/aws12.PNG)

**Insertamos datos en la tabla creada**

![AWS](Imagenes/aws13.PNG)

**Habilitamos modulos correspondientes**

![AWS](Imagenes/aws14.PNG)

**Creación directorio protegido**

![AWS](Imagenes/aws15.PNG)

**Modificamos fichero de configuración**

![AWS](Imagenes/aws16.PNG)

Y tiene que quedar de la siguiente manera:

![AWS](Imagenes/aws17.PNG)

Una vez hecho reiniciamos apache

**A continuación accedemos al directorio poniendo ip/protecteddir**

![AWS](Imagenes/aws18.PNG)

Y vemos comos nos pide usuario y contraseña

![AWS](Imagenes/aws19.PNG)

![AWS](Imagenes/aws20.PNG)



## 2. Crear un certificado autofirmado y activar el módulo SSL

**Abrimos los puertos y activamos el modulo correspondiente**

![AWS](Imagenes/aws21.PNG)

**Procedemos a crear el certificado**

![AWS](Imagenes/aws22.PNG)

Y lo configuramos de la siguiente manera **(todo es opcional menos nuestra ip)**

![AWS](Imagenes/aws23.PNG)

**Ahora modificamos fichero configuración:**

![AWS](Imagenes/aws24.PNG)

Añadiendo lo siguiente:

![AWS](Imagenes/aws25.PNG)

![AWS](Imagenes/aws26.PNG)

Una vez configurado podemos observar el certificado SSL autofirmado:

![AWS](Imagenes/aws27.PNG)

