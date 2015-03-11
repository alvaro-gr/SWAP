#Practica1

##Ejecucion de las suiguientes ordenes en los dos servidores.
	**apache2 -v**
	**ps aux | grep apache**

**Servidor1:**

==> apache2 -v

	Server version: Apache/2.2.22 (Ubuntu)
	Server built:   Feb 13 2012 01:37:27

==> ps aux | grep apache

	root       936  0.0  1.3  34016  6996 ?        Ss   21:28   0:00 /usr/sbin/apache2 -k start
	www-data   961  0.0  0.7  34040  3768 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   962  0.0  0.7  34040  3768 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   963  0.0  0.7  34056  4020 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   964  0.0  0.9  34492  4628 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   965  0.0  0.7  34040  3768 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data  1280  0.0  0.7  34040  3768 ?        S    21:30   0:00 /usr/sbin/apache2 -k start
	www-data  1281  0.0  0.7  34040  3768 ?        S    21:30   0:00 /usr/sbin/apache2 -k start
	root      1306  0.0  0.1   4364   828 tty1     S+   21:33   0:00 grep --color=auto apache



**Servidor2:**

==> apache2 -v

	Server version: Apache/2.2.22 (Ubuntu)
	Server built:   Feb 13 2012 01:37:27
	

==> ps aux | grep apache
	
	root       916  0.0  1.3  34016  6996 ?        Ss   21:28   0:00 /usr/sbin/apache2 -k start
	www-data   936  0.0  0.7  34040  3768 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   937  0.0  0.7  34040  3768 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   938  0.0  0.7  34040  3768 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   939  0.0  0.7  34056  4020 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data   940  0.0  0.9  34492  4636 ?        S    21:28   0:00 /usr/sbin/apache2 -k start
	www-data  1440  0.0  0.7  34040  3768 ?        S    21:30   0:00 /usr/sbin/apache2 -k start
	www-data  1441  0.0  0.7  34040  3768 ?        S    21:30   0:00 /usr/sbin/apache2 -k start
	www-data  1442  0.0  0.7  34040  3768 ?        S    21:30   0:00 /usr/sbin/apache2 -k start
	root      1467  0.0  0.1   4364   832 tty1     S+   21:39   0:00 grep --color=auto apache
	