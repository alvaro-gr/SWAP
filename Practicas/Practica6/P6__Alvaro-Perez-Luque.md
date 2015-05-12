#Practica 6

##Objetivos:

Configurar dos discos en RAID 1 (los discos se añadirán a un sistema ya
instalado y funcionando).

Hacer pruebas de retirar y añadir un disco y comprobar que el RAID sigue funcionando correctamente.



#Configuración del RAID por sofware

Instalamos el software necesario para gestionar el RAID:

	apt-get install mdadm

Con la siguiente orden comprobamos que los discos que hemos añadido están:

	fdisk -l


Una vez hecho esto podemos ya crear el RAID1 para ello utilizamos la siguiente orden:

	mdadm -C /dev/md0 --level=raid1 --raid-devices=2 /dev/sdb /dev/sdc


![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/crear_raid.png)


Formateamos con mkfs y creamos algunos directorios dentro:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/datos_raid.png)




En el fichero /etc/fstab añadimos lo siguiente para que cuando se reinicie el sistema automáticamente se monte el RAID, y con la orden mount podemos ver si se ha montado correctamente:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/fstab.png)


![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/mount.png)


Al reinciar el sistema, este ha renombrado a la unidad montada md0 como md127. Con la siguiente orden podemos ver el estado del RAID:

	mdadm --detail /dev/md127

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/estado_raid.png)


#Simulación de un fallo en un disco del RAID

Simulamos el fallo del disco /dev/sdb  y lo retiramos:

	mdadm /dev/md127 --fail /dev/sdb

	mdadm -r /dev/md127 /dev/sdb


![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/fallo_disco.png)


![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/fallo_disco2.png)


Comprobamos que podemos acceder a la información almacenada en el RAID:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/fallo_disco3.png)


Ahora volvemos a añadir el disco que hemos retirado anteriormente y comprobamos el RAID:

	mdadm -a /dev/md127 /dev/sdb

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica6/Capturas/añadir_disco.png)








