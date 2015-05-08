#Practica 5

##Objetivos:
Copiar archivos de copia de seguridad mediante ssh.

Clonar manualmente BD entre máquinas.

Configurar la estructura maestro-esclavo entre dos máquinas para realizar el clonado automático de la información.



#Creación de un BD en MySQL mediante línea de órdenes

Los siguientes pasos describen como conectarse a MySQL desde la línea de órdenes y como crear un base de datos, con una tabla y un registro.

Conexión a MySQL:

	mysql -u root -p

Creación de la BD y una tabla e inserción de un registro:
	
	create database Clientes;

	use Clientes;

	create table socios(Nombre varchar(20), DNI varchar(9));

	insert into socios(Nombre,DNI) values("Pepe","45454545U");

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/bd.png)

#Replicar una BD MySQL con mysqldump

Antes de hacer la copia de seguridad en la máquina1 creamos la BD en la máquina2, y bloqueamos las tablas de la BD en la máquina1 para que no se pueda acceder a ellas.

Con la siguiente orden hacemos una copia de la BD:

	mysqldump  bd_ejemplo -u root -p > bd_ejemplo.sql
	
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/mysqldump_1.png)	
	

En la siguiente imagen se puede ver como se trasfiere la copia sql al servidor secundario y como se restaura:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/mysqldump_2.png)



Y comprobamos que en nuestro servidor 2 se ha restaurado la copia:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/mysqldump_3.png)

#Replicación de BD mediante una configuración maestro-esclavo


##Configuración de mysql del maestro:

Lo primero es añadir la configuración al fichero /etc/mysql/my.cnf. Y reiniciamos el servicio mysql.

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/mycnf.png)


Ahora creamos un usuario y le damos permisos para la replicación:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/ms_1.png)


##Configuración de mysql del esclavo:

Añadimos al fichero my.cnf lo mismo que en el servidor1 pero teniendo en cuenta que en este el server-id es 2. Iniciamos la conexión mysql para indicarle los datos del maestro y después iniciamos el esclavo:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/ms_2.png)

Una vez que hayamos desbloqueado las tablas en el servidor maestro para poder insertar nuevos registros. 
Con la siguiente orden:

	SHOW SLAVE STATUS\G

Podemos ver si todo esta correcto o no, para ello nos fijamos en "Seconds_Behind_Master", y vemos si es distinto de null, si es así significa que todo está correcto, de lo contrario es que hay algún error.

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica5/Capturas/esclavo_ok.png)














	



