#Ejercicios Tema2
##Ejercicicio T2.1	
Calcular la disponibilidad del sistema completo si tenernos 3 elementos de cada subsistema, exceptuando el Data Center.
Esta es la disponibilidad con dos elementos de cada subsistema:

![imagen](https://github.com/alvaro-gr/SWAP2015/blob/master/Trabajo_Clase/Ejercicios-Tema2/d1.png)


Si multiplicamos: 97.75%  99%  99.9999%  99.96%  97.75%  99.99%  99.99%  99.75% = 94.3%


Disponibilidad con 3 elementos en cada subsistema:

Web:
	97.75% + ( (1 - 97.75%) * 85% ) = 99.6625%

Application:
	99% + ( (1-99%) *90% ) = 99.9%

Database:
	99.9999% + ( (1-99.9999%) * 99.9%) = 99.9999999%

DNS:
	99.96%  + ( (1-99.96%) * 98%) = 99.9992%

Firewall
	97.75% + ( (1-97.75%) * 85%) = 99.6625%

Switch
	99.99% + ( (1-99.99%) * 99%) = 99.9999%

ISP
	99.75% + ( (1-99.75%) * 95%) = 99.9875%

----------------------------------
99.6625% * 99.9% *  99.9999999% * 99.9992% * 99.6625% * 99.9999% * 99.99% * 99.9875% =  99.2%

Mejora:  99.2% - 94.3% =  4.9%


##Ejercicicio T2.2	

Buscar frameworks y librerías para diferentes lenguajes que permitan hacer aplicaciones altamente disponibles con relativa facilidad. Como ejemplo, examina PM2   (https//github.com/Unitech/pm2) que sirve para administrar clústeres de NodeJS.

==>	JBoss Eclipse IDE Milestone 5. 

==>	Zope (Entorno de Desarollo).

==>	El estándar J2EE.

==>	IBM Lotus Notes


##Ejercicicio T2.3	

¿Cómo analizar el nivel de carga de cada uno de los subsistemas en el servidor? Buscar herramientas.

**Siege**

Una herramienta utilizada ampliamente por desarrolladores para realización de pruebas de carga. Para probar y testear la carga HTTP de un servidor. (Libre)

Ejemplo de uso:

<http://blog.desdelinux.net/siege-medir-rendimiento-servidor-web/>
<http://manpages.ubuntu.com/manpages/hardy/man1/siege.1.html>


**Zabbix**

Zabbix es una clase de mecanismo de vigilancia tipo empresarial que está completamente equipado y tiene soporte comercial. Es capaz de monitorear y dar seguimiento de la situación de los diferentes tipos de servicios de red, servidores y otro hardware de red. Zabbix cuenta con tres módulos principales: el servidor, los agentes, y el usuario. Para almacenar los datos de seguimiento, puede utilizar MySQL, PostgreSQL, Oracle o SQLite como base de datos.  (Libre)

Ejemplo de uso:

 <http://911-ubuntu.weebly.com/zabbix_como_funciona/conoce-la-estructura-de-%20%20%20%20%20%20zabbix-y-como-usarlo>


**Nagios**

Es un sistema de monitorización en software libre, bajo licencia GPL2, que nos permite conocer en todo momento el estado de nuestros sistemas, monitorizando nuestra granja de servidores y los servicios que en éstos se alojan, generando alertas y alarmas cuando el comportamiento de los mismos no sea el esperado. (Libre)

Ejemplo de uso:

<http://www.nagios-cl.org/nagios-nrpe-supervisando-maquinas-linux>


**Ipcheck server monitor**

Es un tipo de utilidad cada vez más necesaria. Ésta realiza constantes comprobaciones de varios tipos, no sólo si la página Web está offline, sino siendo capaz de detectar incluso si no funcionan determinados scripts o formularios.

IPCheck se podría definir como la herramienta para la monitorización avanzada y constante de tus servidores. Es una evolución natural del simple ping, comprobando aspectos que pueden ser muy importantes, sobre todo si tu negocio depende de ello. (No Libre)

Ejemplo de uso: 

<http://www.paessler.com/manuals/ipcheck_server_monitor>


**OpManager**

OpManager proporciona una visión completa de la disponibilidad y el desempeño de sus servidores y ofrece distintas características para enfrentar los retos administrativos de los servidores de diferentes plataformas y tecnologías como pueden ser: Windows, Linux, Solaris, Unix, VMware, AIX, HP-UX, Etc.  OpManager permite utilizar SNMP, WMI, CLI o Telnet/SSH para:

·	Monitorear todos sus servidores en una sola consola.

·	Gestionar el desempeño de sus servidores

·	Planear la capacidad de los servidores.


Ejemplo de uso:

<http://es.slideshare.net/Rooccck/implementacion-de-opmanager-10-en-windows-server-2008-r2>

##Ejercicicio T2.4

Buscar ejemplos de balanceadores software y hardware.

	Productos comerciales para servidores de aplicaciones.

	Productos comerciales para servidores de almacenamiento.



  **Kemp load Balancer** 

 <http://kemptechnologies.com/es/>


    **Barrucada Load Balancer ADC**

 <https://www.barracuda.com/products/loadbalancer>

**Citrix Netscaler**

<http://www.citrix.es/products/netscaler-application-delivery-controller/overview.html?posit=glnav>




