#Practica 5

##Objetivos:
Copiar archivos de copia de seguridad mediante ssh.

Clonar manualmente BD entre máquinas.

Configurar la estructura maestro-esclavo entre dos máquinas para realizar el clonado automático de la información.



#Creación de un BD en MySQL mediante línea de órdenes

Los siguientes pasos describen como conectarse a MySQL desde la línea de órdenes y como crear un base de datos, con una tabla y un registro.

Conexion a MySQL:

	mysql -u root -p

Creación de la BD y una tabla e inserción de un registro:
	
	create database Clientes;

	use Clientes;

	create table socios(Nombre varchar(20), DNI varchar(9));

	insert into socios(Nombre,DNI) values("Pepe","45454545U");


#Replicar una BD MySQL con mysqldump

Antes de hacer la copia de seguridad en la maquina1 creamos la BD en la maquina2, y bloqueamos las tablas de la BD en la maquina1 para que no se pueda acceder a ellas.

Con la siguiente orden hacemos una copia de la BD:

	mysqldump  bd_ejemplo -u root -p > bd_ejemplo.sql

En la siguiente imagen se puede ver como se trasfiere la copia sql al servidor secundario y como se restaura:




Y comprobamos que en nuestro servidor 2 se ha restaurado la copia:


#Replicación de BD mediante una configuración maestro-esclavo


##Configuración de mysql del maestro:

Lo primero es añadir la configuración al fichero /etc/mysql/my.cnf. Y reiniciamos el servicio mysql.



Ahora creamos un usuario y le damos permisos para la replicación:




##Configuración de mysql del esclavo:

Añadimos al fichero my.cnf lo mismo que en el servidor1 pero teniendo en cuenta que en este el server-id es 2. Iniciamos la conexión mysql para indicarle los datos del maestro y después iniciamos el esclavo:


Una vez que hayamos desbloqueado las tablas en el servidor maestro para poder insertar nuevos registros, con la siguiente orden:

	SHOW SLAVE STATUS\G

Podemos ver si todo esta correcto o no, para ello nos fijamos en "Seconds_Behind_Master", y vemos si es distinto de null, si es así significa que todo está correcto, de lo contrario es que hemos cometido algún error.
















	



