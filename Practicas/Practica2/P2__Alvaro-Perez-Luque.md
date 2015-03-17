#Practica2.

##Objetivos:

• Aprender a copiar archivos mediante ssh

• Clonar contenido entre máquinas

• Configurar el ssh para acceder a máquinas remotas sin contraseña

• Establecer tareas en cron



##Configuración de ssh para acceder sin contraseña

-Ejecutamos la siguiente orden:

		ssh-keygen -t dsa

-Cuando nos pide el passphrase lo dejamos en blanco.

-En el directorio /home/usuario se ha creado el directorio .ssh que
 guarda "ide_dsa" y "id_dsa.pub", para la clave privada y pública.

-Con la siguiente orden copiamos la clave pública a la maquina 1.

	 ssh-copy-id -i .ssh/idsa.pub usuario@maquina1

-Ahora si hacemos ssh usuario@maquina1 nos  debe pedir la password. 

![imagen](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica2/Key_ssh.png)

##Funcionamiento de copia archivos por ssh

-Vamos a copiar un directorio desde la maquina2 a la maquina1:

		tar czf - prueba/ | ssh maquina1 'cat > ~/mitar.tgz'

-Comprobamos que en la maquina1 está en el sitio correcto el archivo "mitar.tgz".

![imagen](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica2/tar.png)

##Instalación de la herramienta rsync
-En la maquina2 se ejecuta orden: sudo apt-get install rsync, y devuelve:
 Rsync ya esta en su versión mas reciente, por tanto ya esta instalado.

-Ahora procedemos a clonar desde la maquina1 a la maquina2 con la siguiente orden:

		rsync -avz -e ssh usuario@maquina1:/var/www/ /var/www/
		
![imagen](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica2/clonacion.png)

##Establecer una tarea cron para manterner aztualizadas las dos maquinas cada hora
-En la maquina2 editamos el fichero /etc/crontab y añadimos la siguiente línea

		0 * * * * usuario  rsync -avz -e ssh usuario@maquina1:/var/www/ /var/www/

-Guardamos y en la siguiente hora se ejecutara la orden.

![imagen](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica2/cron.png)
