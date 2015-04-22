#Practica 4

##Objetivos:

Medir el rendimiento de nuestra granja web y de un servidor solo funcionando, utilizando distintas herramientas 
para la realización de las pruebas en un cliente para que este genere carga HTTP.

-------------------------

Para cada ejecución se hace una serie de peticiones, a un servidor solo, a un balanceador nginx y otro, haproxy. La web que deben de servir es muy ligera para las dos primeras herramientas. Para la tercera herramienta se utiliza un script php que contiene un bucle con un número alto de iteraciones y dentro de este una serie de cálculos, para que el servidor le cueste más servir.

A continuación se describen las mediciones realizadas. Previamente se han hecho 5 ejecuciones sobre las 3 situaciones.



##Apache Benchmark

Para esta herramienta se ha realizado varios tests con la siguiente orden:

	ab -n 100000 -c 100 http://maquina/pagina
Donde -n es el número de peticiones, que se solicitan de 100 en 100 que se indica con la opción -c.

Mediciones:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/ab_tablas.png)


**MEDIA:**

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/ab_media.png)



**DESVIACIÓN ESTANDAR:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/ab_desviacion.png)




##OpenWebLoad

Para esta herramienta se ha realizado varios tests con la siguiente orden:

	openload http://maquina 300
	
Donde 300 es el número de peticiones concurrentes.
	


Mediciones:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/open_tablas.png)



**MEDIA:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/open_media.png)



**DESVIACIÓN ESTANDAR:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/open_desviacion.png)


##SIEGE
Para esta herramienta se ha realizado varios tests con la siguiente orden:

	siege -c300  -r1   http://maquina/f.php
Con la opción -c especificamos el número de peticiones concurrentes y la opción -r el número de repeticiones.

Mediciones:
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/siege_tablas.png)


**MEDIA:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/siege_media.png)


**DESVIACIÓN ESTANDAR:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/siege_desviacion.png)




