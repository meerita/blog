---
date: 2006-12-11 15:22:20
layout: post
slug: como-tener-multiples-sitios-web-en-nuestro-mac
title: Cómo tener múltiples sitios web en nuestro Mac
category: apple
---

Unas las cosas que un usuario novel de Mac no se puede perder, es la de utilizar el _servidor web_ que trae. Si bien, ningún tipo de usuario, diseñador o maquetador, debe perder la oportunidad de aprender las cosas básicas de un servidor web. Esto te sirve especialmente si trabajas en diseño o empiezas a aprender a programar. En la última reunión de bloguers en Barcelona que se celebró el mes pasado, un asistente me había pedido que explicara cómo monto servidores virtuales en mi Mac. Así, de esta forma podemos tener más de un sitio corriendo en nuestro servidor web.





Mac OS X viene con uno de los mejores servidores web instalados por defecto. Esto es posible desde las primeras primerísimas versiones de OS X. Ponerlo en marcha es fácil y no te hace falta grandes conocimientos:



Ahí está el panel de control sharing en Mac OS X. En castellano tendrá una traducción parecida a _compartir_ y basta con hacer clic en el botoncito Start y tendremos el servidor funcionando. Debajo de la lista están las dos direcciones más importantes para acceder a la página por defecto cargada en nuestro servidor web: `http://192.168.1.24`. Bueno, esta dirección no es la famosa dirección local, así que podemos acceder a esta misma página de 3 formas diferentes:







  1. `http://localhost`


  2. `http://127.0.0.1`


  3. `http://192.168.1.24`*





* El último ejemplo sólo es válido para la red que tengo instalada en mi casa. En vuestro caso puede variar el número.





Bien, si vamos a alguna de estas direcciones, y tenemos activado el servidor web, podremos ver una página por defecto, que no es gran cosa. La dirección para subir ficheros y empezar a ver cambios, y que debes recordar como si fuera la carpeta maestra donde podrás subir archivos de imágenes, html y otras cosas para tener más de un proyecto funcionando:





    <code>/Library/WebServer/Documents</code>





Esa dirección en tu ordenador en Mac OS X es a lo que en Internet fuere `http://localhost` o `http://127.0.0.1` para ver la página funcionando. Para acceder a esta carpeta, debes navegar con el Finder o, una cosa que recomiendo, ponerse en forma utilizando la Terminal del OS X:





    <code>cd /Library/WebServer/Documents</code>





Así de fácil, ahí verás los archivos por defecto que instala Apache. Podrás borrarlos, moverlos a otra carpeta, etc. Lo importante es, como está ahora todo, sólo nos sirve para tener 1 sitio corriendo a la hora. No pueden existir ni dos, ni tres, ni cuatro. Tampoco podremos utilizar un dominio local, por ejemplo, `http://minid.local` o `http://miweblog` pero esto será posible modificando unas poquitas cosas.





#### Teniendo múltiples sitios en nuestro servidor web





Una cosa espectacular para tener en nuestro servidor web es una configuración que nos permita tener muchos sitios web locales de prueba. Esto nos viene de perlas para trabajar: los diseñadores pueden tener varios clientes en una sola instalación de servidor web, con nombres de dominios fáciles y posibilidad de usar MySQL, PHP u otros lenguajes. También va de perlas para testear otros programas en PHP que descargamos en algunos sitios recomendados.





¿Qué nos hace falta tener para empezar a tener sitios múltiples?







  1. Crear la carpeta donde se alojará nuestro sitio de prueba.


  2. Editar el archivo de configuración de Apache.


  3. Crear un dominio local en nuestra máquina.


  4. Reiniciar el servidor.





Primero empezamos creando la carpeta donde estarán los archivos de nuestro supuesto sitio alternativo. Si ya te olvidaste de cómo hacerlo, recuerda la guía de carpetas que tiene el servidor web en Mac OS para la carpeta de documentos del servidor web: `/Library/WebServer/Documents`. Una vez dentro (usando el Terminal) escribimos:





    <code>cd /Library/WebServer/Documents/
    mkdir micliente</code>





Ya tenemos la carpeta de nuestro sitio alternativo y, siempre que quieras trabajar en ella, sólo debes recordar que la guía de carpetas es `/Library/WebServer/Documents/micliente`. Ahora, tenemos que meternos a configurar el servidor web Apache para que tenga activado como servidor virtual esta carpeta, además de la que ya trae por defecto.





Modificar Apache puede ser engorroso. Es un archivo de texto largo, y puede darle más de un dolor de cabeza a alguno. Incluso, si uno toca algo y no sabe como arreglarlo puede dejarnos el servidor web sin funcionamiento. Pero no hay que alarmarse, lo primero, es averiguar qué archivo necesitamos modificar las preferencias de nuestro servidor, y este se llama `httpd.conf`. Lo podrás encontrar en `/etc/httpd/` y sólo se puede editar en modo administrador del ordenador –conocido como root.





Abrimos el Terminal del Mac OS X y escribimos esto:





    <code>$ sudo su
    Password: tupassword</code>





Si usamos la clave de administrador (que un buen día escribiste en al iniciar Mac OS X) cambiará el modo de uso, dejarás de ser, para esa sesión, un usuario normal y serás un superusuario (podrás cambiar, ejecutar e instalar aplicaciones que requieran aprobación de administrador del sistema). Si todo sale bien, luego en tu Terminal mirarás un símbolo `root#`. Si fueras usuario normal, seguiría usando el símbolo de dólar `$`.





    <code>diego-lafuentes-computer:/Library/WebServer/Documents root#</code>





Eso es lo que verás en la Terminal de tu Mac OS X. Ahora podrás modificar el archivo de configuración de Mac OS X. Ahí mismo, así, con ese `root#` en el Terminal debes escribir:





    <code>mate /etc/httpd/httpd.conf</code>





Una cosa importante, el comando mate, pertenece a un programa de edición de textos que tengo instalado en mi Mac OS X. Si no tienes un editor de texto que lo permita, deberás utilizar lo que viene por defecto, que puede ser bastante complicado o, utilizar otras herramientas.





Una vez ejecutado el comando, se abrirá el editor de textos con el archivo de configuración. Antes de empezar a secarse el sudor, hay que descender casi hasta el final del archivo, hasta que podamos leer:





    <code>### Section 3: Virtual Hosts
    #
    # VirtualHost: If you want to maintain multiple domains/hostnames on your
    # machine you can setup VirtualHost containers for them. Most configurations
    # use only name-based virtual hosts so the server doesn't need to worry about
    # IP addresses. This is indicated by the asterisks in the directives below.
    #</code>





Ahí comienza la sección de virtual hosts. A partir de aquí, nos ponemos en marcha editando las cosas necesarias. Primero, hay que entender que, al borrar cualquier `#` en este archivo lo que se hará será activar esa línea y será interpretada como un comando a ejecutar. Por ello, para documentar este archivo, los programadores comentan usando este símbolo. Siempre que queramos deshabilitar una cosa del servidor, simplemente debemos escribir al comienzo de cada línea el símbolo `#`.





Bien, una vez en esta parte,leeremos esta línea unos retornos de carro más abajo:





    <code>#
    # Use name-based virtual hosting.
    #

    #NameVirtualHost *:80</code>





Más que seguro, encontrarás esta línea comentada (recuerda que irá con un `#`) y necesitarás habilitarla para los servidores virtuales. Es algo que, en muchos casos se puede prescindir pero, no cuesta nada activarlo por si en algún futuro queremos utilizar IPs en vez de nombres de dominio locales. Descomentamos la línea simplemente eliminando `#`.





    <code>#
    # Use name-based virtual hosting.
    #

    NameVirtualHost *:80</code>





Seguimos con las modificaciones, ahora la chicha. Ahora vendrá la sección donde escribiremos cada sitio alternativo. Los que queramos, 10, 20, 30 o mil pueden ir dentro de este espacio. Apache viene con un ejemplo de VirtualHost, para utilizarlo hay que descomentar las líneas de `&lt;VirtualHost *:80&gt;` hasta `&lt;/VirtualHost&gt;`, nunca descomentes el texto explicativo o no funcionará Apache. Modifica este trozo de texto para que quede de esta forma:





    <code>#
    # VirtualHost example:
    # Almost any Apache directive may go into a VirtualHost container.
    # The first VirtualHost section is used for requests without a known
    # server name.
    #

    &lt;VirtualHost&gt;
        DocumentRoot /Library/WebServer/Documents/micliente/
        ServerName micliente
    &lt;/VirtualHost&gt;</code>





Recuerda que, al empezar, has creado una carpeta llamada micliente en `/Library/WebServer/Documents`, que es donde se aloja y se alojan otros sitios virtuales. Tenlo siempre en cuenta. Es necesario este paso para decirle al servidor que, cuando una persona escriba en nuestra máquina la palabra `http://micliente` en el navegador, éste sepa en donde estás los archivos necesarios para mostrar. Salvamos el archivo httpd.conf y vamos a crear un dominio en nuestra máquina.





Para crear un dominio en nuestra máquina, sin tener que editar archivos, lo haremos de forma gráfica y fácil. Para ello, debemos lanzar un programa llamado Netinfo Manager que lo podemos encontrar en la carpeta de Utilities en nuestro Mac OS X. Este es el aspecto que tiene el NetInfo Manager` cuando lo abráis:





![Netinfo Manager](images/picture-12.png)





El candado que observáis en la parte inferior, indica que, la aplicación ha sido ejecutada por un usuario no-administrador del sistema. Para crear nuestro propio dominio, debemos ser super-usuario pero, a diferencia del ejemplo anterior, no tenemos que ir a un Terminal y ejecutar el comando sudo para identificarnos como super-usuario. Lo haremos sin problemas desde esta misma ventana. Haz clic en el icono de candado, saldrá una ventana preguntándote la clave de administrador.





![Poner clave](images/picture-13.png)





Escribe tu contraseña y podrás editar todos los valores. Una vez aprobado como super-administrador, hacemos clic en la lista del medio y elegimos el item machines. Una vez escogido, en la siguiente lista saldrán las máquinas especificadas. Tomaremos una como ejemplo y la modificaremos para que sirva a nuestros propósitos. Selecciona que dice “localhost” y verás esta pantalla:





![picture-14.png](images/picture-14.png)





Bien, como último paso, haz clic en el botón Duplicate que está en la parte superior. Se creará una entrada más en la lista.





![Duplicando maquinas](images/picture-15.png)





Como observarán, he puesto micliente en el nombre del servidor. Así cada vez que escriba micliente en el navegador, el servidor Apache sabrá lo que tiene que buscar. Además, en nuestra configuración de VirtualHosts hemos escrito como valor de dominio la palabra micliente: `ServerName micliente`. Esto está chupado, ya tienes listo todo casi… falta reiniciar el servidor web y listo.





Cómo último paso, luego de salvar y confirmar los cambios, tienes que volver a las preferencias de sistema, en la sección Sharing, y donde dice _stop_, hacemos clic. Se parará el servidor web y nos lo avisará en la misma ventana. Luego de corroborar que esto ha ocurrido, presionamos _start_ de nuevo y ya podemos ir a nuestro navegador favorito y poner http://micliente para ver el resultado.





Si todo ha ido bien, saldrá un índice de carpeta, indicando que no hay ningún archivo. Prueba de poner un HTML con unas pocas líneas de código para ir haciendo pruebas.
