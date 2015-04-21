#Practica 4

##Objetivos:

Medir el rendimiento de nuestra granja web y de un servidor solo funcionando, utilizando distintas herramientas 
para la realización de las pruebas en un cliente para que este genere carga HTTP.

-------------------------

Para cada ejecución se hace una serie de peticiones, a un servidor solo, a un balanceador nginx y otro, haproxy. La web que deben de servir es muy ligera para las dos primeras herramientas. Para la tercera herramienta se utiliza un script php que contiene un bucle con un numero alto de iteraciones y dentro de este una serie de calculos, para que el servidor le cueste mas servir.

A continuación se describen las mediciones realizdas. Previamente se han hecho 5 ejecuciones sobre las 3 situaciones.



##Apache Benchmark

Para esta herramienta se ha realizado varios tests con la siguiente orden:

	ab -n 100000 -c 100 http://maquina/pagina

Mediciones:

![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/ab_tablas.png)


**MEDIA:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/ab_media.png)



**DESVIACION ESTANDAR:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/ab_desviacion.png)




##HTTPERF

Para esta herramienta se ha realizado varios tests con la siguiente orden:

	httperf --server maquina --port 80 --uri /pagina --rate 100 --num-conn 30000 --num-call 1 --timeout 5

Mediciones:
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/hp_tablas.png)


**MEDIA:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/hp_media.png)


**DESVIACION ESTANDAR:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/hp_desviacion.png)


##SIEGE
Para esta herramienta se ha realizado varios tests con la siguiente orden:

	siege -c300  -r1   http://maquina/f.php

Mediciones:
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/siege_tablas.png)


**MEDIA:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/siege_media.png)


**DESVIACION ESTANDAR:**
![image](https://github.com/alvaro-gr/SWAP2015/blob/master/Practicas/Practica4/Capturas/siege_media.png)




