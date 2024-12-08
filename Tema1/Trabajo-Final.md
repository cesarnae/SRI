# Trabajo 1º Trimestre.Servidores Web
## 1. Instalación del servidor web apache. Usaremos dos dominios mediante el archivo hosts: centro.intranet(wordpress) y departamentos.centro.intranet(Python)

**Instalación** servidor web apache:

 ![Apache1](Imagenes/Cap2.PNG)

**Comprobacion** de que esta bien instalado:

 ![Apache2](Imagenes/Captura5.PNG)

## 2.Activar los módulos necesarios para ejecutar php y acceder a mysql

**Instalación** MySQL:

 ![MySQL](Imagenes/Mysql1.PNG)

**Comprobación**:

 ![MySQL](Imagenes/mysql3.PNG)
 
**Instalación** PHP:

 ![PHP](Imagenes/php1.PNG)
 

**Comprobación**:

 ![PHP2](Imagenes/php2.png)

 **Creacion dominios mediante el archivo hosts:**

 ![VH](Imagenes/virtualhost.png)
 
 **Comprobacion**:
 
 http://centro.intranet/

 ![CI](Imagenes/ci.png)

 http://departamentos.centro.intranet/

 ![DCI](Imagenes/dci.png)

## 3. Instalar y configurar wordpress(centro.intranet)

**Instalacion en centro.intranet**

![WP1](Imagenes/wordpress.PNG)

**Descomprimimos la carpeta**

![WP2](Imagenes/wordpress2.PNG)

**La movemos a nuestro directorio**

![WP3](Imagenes/wordpress3.PNG)

Ahora vamos a **configurar y habilitar el fichero virtualhost:**

![WP4](Imagenes/wordpress4.PNG)
![WP5](Imagenes/wordpress5.PNG)

**Entramos a centro.intranet**

![WP6](Imagenes/wordpress6.PNG)

**Creamos base  de datos**

![WP7](Imagenes/wordpress7.PNG)

**Creamos usuario y le  damos permiso**

![WP8](Imagenes/wordpress8.PNG)
![WP9](Imagenes/wordpress9.PNG)
![WP10](Imagenes/wordpress10.PNG)
![WP11](Imagenes/wordpress11.PNG)


**Instalamos wordpress**

![WP12](Imagenes/wordpress12.PNG)

Siguiendo los siguientes pasos  **modificamos  archivo  wp-config.php** utilizando como  **plantila wp-config.sample.php**

![WP13](Imagenes/wordpress13.PNG)

**Terminamos la instalacion**

![WP14](Imagenes/wordpress14.PNG)

**Finalmente queda instalada**

![WP15](Imagenes/wordpress15.PNG)

**Iniciamos sesión**

![WP16](Imagenes/wordpress16.PNG)

**Y hasta aqui la  instalacion de  wordpress en centro.intranet**

![WP17](Imagenes/wordpress17.PNG)



## 4. Activar el módulo “wsgi” para permitir la ejecución de aplicaciones Python

**Instalanmos el módulo**

![PY](Imagenes/py.PNG)

**Lo habilitamos**

![PY1](Imagenes/py1.PNG)

**Configuramos virtualhost**

![PY2](Imagenes/py2.PNG)

**Lo habilitamos**

![PY3](Imagenes/py3.PNG)


### 4.1 Crea y despliega una pequeña aplicación python para comprobar que funciona correctamente.

**Creamos archivo py**

![PY4](Imagenes/py4.PNG)

**Archivo ya creado**

![PY7](Imagenes/pyx.png)

### 4.2 Adicionalmente protegeremos el acceso a la aplicación python mediante autenticación

**Creamos archivo para usuario y contraseña**

![PY5](Imagenes/py5.PNG)

**Cuando intentamos iniciar nos pide usuario/contraseña**

![PY6](Imagenes/py6.PNG)

## 5. Instala y configura awstat.
![PY5](Imagenes/py5.PNG)


## 6. Instala un segundo servidor de tu elección (nginx, lighttpd) bajo el dominio  “servidor2.centro.intranet”. Debes configurarlo para que sirva en el puerto 8080 y haz los cambios necesarios para ejecutar php. Instala phpmyadmin.






