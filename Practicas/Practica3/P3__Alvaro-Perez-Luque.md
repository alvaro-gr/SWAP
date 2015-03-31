#Practica3

##Objetivos:

Configuraremos una red entre varias máquinas de forma que
tengamos un balanceador que reparta la carga entre varios servidores finales



##Instalación y configuración de nginx.

Importamos la clave desde el repositorio software:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica3/Capturas/importar_clave(nginx).png)
	
Después de añadir el repositorio al fichero /etc/apt/sources.list
ya podemos instalar el paquete nginx.

		apt-get install nginx



Una vez instalado, definimos que maquinas queremos añadir y el resto de la configuración.

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica3/Capturas/configuracion(nginx).png)


Probamos su funcionamiento:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica3/Capturas/funcionamiento1(nginx).png)

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica3/Capturas/funcionamiento2(nginx).png)




##Instalación y configuración de haproxy.

Instalamos el paquete con la siguiente orden:
	
		apt-get install haproxy joe

Una vez instalado editamos el fichero /etc/haproxy/haproxy.cfg y añadimos nuestra configuración:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica3/Capturas/configuracion(haproxy).png)

Por ultimo lanzamos el servicio con la siguiente orden:

![image]()

Ya podemos comprobar mediante la orden curl o desde el navegador de la  máquina física que el balanceador está funcionando correctamente.	

![image]()
