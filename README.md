# Ficheros de configuracion de imagenes Docker.

Este repositorio contiene los dockerfiles de las imagenes generadas y utilizadas en diferentes servicios.

 * base_image.df - Dockerfile para la construccion de una imagen basica. Contiene comandos basicos y las
                   bibliotecas necesarias para su correcto funcionamiento.
 * apache-activemq_image.df - Dockerfile para la construccion de una imagen con OpenJDK 1.8.0.222 y Apache ActiveMQ 5.15.9.
                              Construida a partir de base_image.
 * ldap_image.df - Dockerfile para la construccion de una imagen que proporcione un servicio LDAP basado
 		   en OpenLDAP.
 * ldap_configurable_image.df - Dockerfile para la construccion de una imagen que proporcione un servicio LDAP basado
   			        en OpenLDAP. Configurable mediante inyeccion de variables de entorno.
 * jenkins_slave_base.df - Dockerfile para la construccion de una imagn base para contenedores que contengan nodos 
			   slave de Jenkins para la ejecucion de builds con contenedores efimeros.
 * jenkins_slave_gcc.df - Dockerfile para la construccion de una imagn para contenedores que contengan GCC en nodos 
			  slave de Jenkins para la ejecucion de builds con contenedores.
 * apache_http_server - Dockerfile para la construccion de una imagen que proporciona un servidor WEB. La configuracion
                        establecida solo contempla el uso de https, por tanto expone el puerto 443 y necesita un volumen
                        que contendra la pagina web, los scripts cgi y los certificados necesario. Las rutas necesarias 
                        para un correcto uso de esta imagen son: 


                        /WWW/html     -> Para almacenar la pagina web.
                        /WWW/cgi-bin  -> Para almacenar los scripts CGI asociados a la web.
                        /WWW/certs    -> Para almacenar el certificado del servidor web y de la CA. Los nombres 
                                         deben ser CERTIFICATE.crt CA-chain.crt.
                        /WWW/private  -> Para almacenar la clave privada del certificado del servidor. El nombre
                                            debe ser PRIVATE_KEY.key.

 * python_gunicorn
