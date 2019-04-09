---
title: Cómo instalar Jekyll en OSX
date: 2013-03-11 23:00:23
layout: post
slug: como-instalar-jekyll-en-osx
category: desarrollo
---

Jekyll es ahora la joya de la casa. La Helena de Troya de mis ordenadores. Es el sistema de análisis de archivos que utilizo para realizar y mantener este blog. Si no sabes que es Jekyll, te recomiendo que leas [mi anterior entrada][minid] sobre el tema así entiendes qué es Jekyll, cómo funciona y sus ventajas. Pero si lo que deseas es empezar ya a probar una nueva forma de bloguear entonces empieza por instalar Jekyll y probar como funciona.

Para tener todo a punto, hay instalar unas cosas antes, la gran mayoría son prerequisitos obligatorios para poder tener todo funcionando. Sigue estos pasos y en nada tienes todo preparado.

## Instalar XCode

Jekyll, a diferencia de otros sistemas, requiere de una instalación concreta de programas y módulos. Lo primero que tenemos que tener instalado en nuestro Mac, es XCode. Y la mejor forma de instalarlo, ahora mismo, [es a través de el Mac App Store](https://itunes.apple.com/es/app/xcode/id497799835?mt=12 "XCode").

Una vez instalado XCode, es importante instalar las herramientas de consola. Y como esto no se instala de forma automática, hay que indicarlo en las Preferencias de XCode. En la sección *Downloads* de las preferencias encontrarás, dentro de la pestaña *Components* los paquetes para instalar las herramientas de consola. En la lista tendrás seguro: iOS 6.0, iOS 5.1, iOS 5.0 y las Command Line Tools. La instalación lleva un rato, aunque fueren 114MB los que tiene que descargar, el proceso, no sé porqué, es lento.

Para saber realmente si tienes instalado GCC en tu Mac, debes abrir un Terminal y ejecutar este comando:

{% highlight bash %}
	$ gcc --version
{% endhighlight %}

Y si va todo bien debería decirte:

{% highlight bash %}
	i686-apple-darwin10-llvm-gcc-4.2 (GCC) 4.2.1
{% endhighlight %}

Si aparece este mensaje es que ya puedes realizar el resto del instalaciones sin problemas.



## Instalando Homebrew

Si no tienes Homebrew, es hora ya de instalar este gestor de paquetes. Mi recomendación si tienes algún gestor de paquetes como Ports, es quitarlo así no generan conflictos. Homebrew es una maravilla y te permite instalar muchas cosas sin hacerte problemas. Para instalarlo, corremos el siguiente comando:

{% highlight bash %}
	$ ruby -e "$(curl -fsSkL raw.github.com/mxcl/homebrew/go)"
{% endhighlight %}

Sigue todas las instrucciones que te diga la instalación. No debería llevarte mucho. Una vez instalado Homebrew, puedes instalar cosas con el comando:

{% highlight bash %}
	$ brew doctor
{% endhighlight %}

Y si te dice `Your system is raring to brew` es porque lo tienes instalado perfecto. Sino te dirá algo así:

{% highlight bash %}
	Warning: Your Homebrew is outdated
	You haven't updated for at least 24 hours, this is a long time in brewland!
{% endhighlight %}


## Opcional: instalar Git

El siguiente paso es instalar [Git][git]. Aunque no es necesario, es recomendable ya que de esta forma podremos clonar repositorios y subir nuestro blog a Github para tener una copia backup. Otra de las razones es que la gran mayoría de los plugins están en Github, algunos conversores de un CMS a Markdown sólo están ahí y conviene con una línea de comando ya bajarlos y tenerlos listos.

{% highlight bash %}
	$ brew install git
{% endhighlight %}


### Instalar Ruby

El siguiente paso sería instalar Ruby. [Ruby][ruby] es un lenguaje de programación que utiliza Jekyll y es recomendable tenerlo instalado. Hay que instalar la última versión. Si tienes Mac OS X Mountain Lion, tendrás la versión 1.8.7. Según los tutoriales que he leído, lo más recomendable es tener instalado RVM (Ruby Version Manager) en el Mac. Esto permite realizar varias instalaciones de Ruby en un mismo ordenador y, indicar cuál es la correcta. De esta forma si un día queremos tener algo que funciona sólo en alguna versión antigua podríamos hacerlo con RVM. Instalar RVM es relativamente fácil, abre un Terminal y escribe:

{% highlight bash %}
	$ brew tap homebrew/dupes
	$ brew install autoconf automake apple-gcc42 tcl libksba
	$ curl -L https://get.rvm.io | bash -s stable --ruby
{% endhighlight %}

Sigue los pasos, y cuando tengas instalado RVM, puedes instalar Ruby. Mi recomendación es la 1.9.2 para arriba (1.9.3 ahora creo que van) y con esto ya podrías correr sin problemas Jekyll. Para realizar esto, antes de instalar Ruby tenemos que comprobar si RVM cumple los requerimientos (a veces hace falta instalar algo):

{% highlight bash %}
	$ rvm get head
{% endhighlight %}

Cualquier librería que te falte la puedes instalar usando el comando `brew install`. Si no te faltó nada, entonces ya puedes instalar Ruby:

{% highlight bash %}
	$ rvm install 1.9.3  --with-gcc=clang
{% endhighlight %}

Una vez instalado debemos configurarlo como la versión de Ruby oficial en nuestra máquina:

{% highlight bash %}
	$ rvm use 1.9.3 --default
{% endhighlight %}

Utiliza el comando `$ ruby -v` para verificar que realmente tienes oficializada la versión 1.9.x. Si todo está bien deberías ver algo así como `ruby 1.9.3p392 (2013-02-22 revision 39386) [x86_64-darwin12.2.0]`.

{% highlight bash %}
	$ rvm use 1.9.3 --default
{% endhighlight %}

Con esto ya podemos tirar para adelante con la instalación de Jekyll.

### Instalando Jekyll

La mejor forma de instalar Jekyll es con RubyGems. Si no tienes instalado RubyGems, antes puedes comprobarlo en la Consola ejecutando `$ gem -v`. Si tienes instalado entonces debes ejecutar:

{% highlight bash %}
  gem install jekyll
{% endhighlight %}

Luego instala las siguientes gemas: `directory_watcher`, `liquid`, `maruku` y `classifier` con el instalador de gemas. Es probable que no tengas las últimas versiones de gemas, es buen tiempo para ejecutar un upgrade de todas las gemas:

{% highlight bash %}
  sudo gem update --system
{% endhighlight %}

Bien, de todas las gemas, [Maruku][mar] es una de las gemas encargadas de interpretar los archivos de Markdown. Maruku no es una mala gema pero muchos prefieren [RDiscount][rd] por su velocidad. Yo también elegí esta gema. Para instalar RDiscount simplemente usamos RubyGems:

{% highlight bash %}
  $ sudo gem install rdiscount
{% endhighlight %}

Luego podemos ejecutar RDiscount con Jekyll así:

{% highlight bash %}
  $ jekyll --rdiscount
{% endhighlight %}

O bien en nuestro archivo _config.yml podemos poner:

{% highlight bash %}
  markdown: rdiscount
{% endhighlight %}

Esto hará que todas las veces que ejecutes `jekyll --server` cargue por defecto RDiscount cuando necesite procesar Markdown.

### Empezando con Jekyll

Lo importante que tienes que recordar sobre Jekyll es que es un motor de análisis de texto. Recorre una serie de documentos, carpetas y los convierte usando unas plantillas definidas a páginas de HTML. En medio de este proceso, podemos toquetear las URLs a generarse, la forma de escribir estos documentos con Markdown o Textile y otros elementos más. Ahora que ya tienes instalado Jekyll lo interesante sería crees una carpeta donde poder armar un sitio y vuelques una estructura de documentos adecuada.

Una estructura típica de Jekyll tiene este aspecto:

{% highlight bash %}
  .
  |-- _config.yml
  |-- _includes
  |-- _layouts
  |   |-- default.html
  |   `-- post.html
  |-- _posts
  |   |-- 2013-03-07-como-instalar-jekyll-en-OSX.markdown
  |   `-- 2013-03-26-barcamp-boston-4-roundup.textile
  |-- _site
  `-- index.html
{% endhighlight %}

`_config.yml` es el archivo de configuración del proyecto. Sirve para ejecutar órdenes de forma automática cada vez que inicies el servicio de Jekyll. Ahí dentro podrás configurar el proyecto al 100%. Desde dejar de usar Markdown a utilizar algún analizador de Textile y así con todo.

Funciona de la siguiente manera: existe una función y un estado. Un ejemplo:

{% highlight bash %}
  markdown: rdiscount
{% endhighlight %}

Esta opción le dice a Jekyll que usaremos Markdown en nuestro proyecto pero además, usaremos la gema rdiscount para procesar los archivos de Markdown. Esta es la composición de un `_config.yml`. Puedes revisar claro la documentación sobre este archivo que detalla cada opción.

Ahora para no liarte mucho, crea un archivo de textos y nómbralo a `_config.yml`, dentro escribe lo siguiente:

{% highlight bash %}
  auto: false
  server: false
  lsi: false
  pygments: true
  markdown: rdiscount
  pygments: true
  permalink: /:year/:month/:day/:title
  paginate: 1
  exclude: ["lib", "blog.rb", "Capfile", "config", "log", "Rakefile", "tmp"]
  destination: public
{% endhighlight %}

Parte de este ejemplo está basado en [mi archivo de configuración][config]. Puedes guiarte pero no utilices todo, porque puede que te dé error al cargar Jekyll. Lo importante está en este ejemplo es que básicamente te hará una carpeta `/public/` donde pondrá los archivos `.html` ya procesados y generados con una estructura de html práctica al mejor estilo `/año/mes/día/título` así que no tendrás que preocuparte por configurar Apaches ni nada. En futuros artículos discutiremos varias formas de conseguir los mismos resultados y aprendiendo más cosas.



Teniendo ya el archivo de configuración lo siguiente en importancia tiene más que ver con las carpetas donde se guardan los archivos. Habíamos ejemplificado antes algunas carpetas. Estas carpetas son leídas por Jekyll y algunas son normativas. Por ejemplo, la carpeta `_posts/` será investigada para encontrar archivos de textos con un formato específico. Si encuentra uno, lo analizará y a partir de aquí, generará el resultado final del HTML, pero el resto de carpetas tienen otras funciones predefinidas.

La carpeta `_layouts/` será aquella que contenga tus plantillas en HTML. Servirán para definir todo tipo de plantillas, desde las que utilices en los posts como otras, dependiendo la complejidad del proyecto, claro.

La carpeta `_includes/` será aquella que contenga los archivos parciales que usas en las plantillas. Por ejemplo, si necesitas hacer una cabecera, no hace falta que la tengas que repetir la misma cantidad de HTML en cada plantilla principal. Puedes hacer un archivo `cabecera.html` que contenga el HTML y luego en la plantilla escribes `include header.html` para que cada vez que Jekyll procese esa plantilla llame a ese parcial. Un buen proyecto debería estar separado, de forma que puedas mantenerlo con menos trabajo.

La carpeta `_plugins/` será aquella que utilizaremos para poner nuestros plugins. Los plugins son funciones adicionales que podemos descargar de repositorios en Github ofreciéndonos la posibilidad de extender la funcionalidad que Jekyll no posee. Yo utilizo algunos plugins, pero no demasiados. Hay ya unos cuantos disponibles y la instalación es simple. Tiras un archivo dentro de la carpeta y lo llamas desde `_config.yml`. Así de simple.

Nos queda `index.html` que actualmente será la plantilla de entrada del blog o sitio. Como en Wordpress, esta plantilla dispone de un *loop* con el que puedes sacar los posts.



Estas eran todas las carpetas que necesita el proyecto. Ahora hagamos una entrada de prueba para ver los resultados de nuestra instalación.

### Escribiendo en Jekyll

Jekyll, como analizador, requiere de una estricticidad a la hora de escribir entradas para tu blog. Hay que respetar una cierta estructura. Pero no os asustéis: no es complicado. Lo primero que tenemos que aprender es a componer un post. Y para ello haremos un tutorial rápido de ello.

Abre un editor de textos y empieza por escribir la cabecera de la entrada del blog:

{% highlight bash %}
  ---
  title: Mi nuevo post
  date: 2013-03-15
  slug: mi-nuevo-post
  ---

  Aquí va mi *nueva* entrada
{% endhighlight %}

Eso es la cabecera de cada entrada. Debajo de los guiones, escribes tu entrada con Markdown. Salva el archivo de forma lógica, como tiene que estar: primero la fecha, luego el título. Esta entrada está nombrada así:

{% highlight bash %}
  2013-03-07-como-instalar-jekyll-en-osx.md
{% endhighlight %}

Es importante tener bien esto porque sino habrá problemas para generar el blog luego. Ahora lo que tienes que hacer para generar tu blog y verlo en funcionamiento es ejecutar el comando `$ jekyll --server`. Una vez



Una vez tengas corriendo Jekyll, notarás te ha creado una carpeta extra, llamada `public` que es básicamente la que hemos nombrado en el archivo de configuración. Puedes usar cualquier nombre y volver a regenerar el sitio que Jekyll borrará todo y volverá a hacer.

### Subiendo los cambios

Ya están las entradas escritas, ya están las plantillas, queda subir el blog. Hay varios métodos. Los automáticos y los manuales. Los manuales, los más fáciles para aquellos que no saben hacer scripts de Consola. Simplemente puedes sincronizar tu carpeta con la que tengas por FTP así no subes todos los archivos o bien, puedes subir y sobreescribir todo. El lado automático, ejecutar un comando y que haga todo es más complicado. Además, puedes usar otras herramientas más allá de un script de Consola. Yo utilizo un script que hace varias tareas antes de subirlo todo a mi servidor. El proceso tarda apróximadamente 25 segundos.



Con esto termino el primer artículo técnico sobre Jekyll. El siguiente veremos más temas de plantillas y configuración para pasar tu blog de Wordpress a Jekyll.


[mar]: http://maruku.rubyforge.org/ "Maruku: a Markdown-superset interpreter"
[rd]: https://github.com/rtomayko/rdiscount "rtomayko/rdiscount · Github"





[minid]: /2013/02/27/una-nueva-forma-de-bloguear/ "Blogueando como un Hacker con Jekyll"
[jk]: http://jekyllrb.com/  "Google Search for life"
[tom]: http://tom.preston-werner.com/ "Tom Preston-Werner"
[git]: http://github.com/ "Github · Build software better, together."
[pages]: http://pages.github.com/ "Github Pages"
[ruby]: http://www.ruby-lang.org/es/ "Lenguaje de Programación Ruby"
[text]: http://textile.sitemonks.com/ "Textile 2.2 Test Page"
[md]: http://daringfireball.net/projects/markdown/ "Daring Fireball: Markdown"
[liq]: http://liquidmarkup.org "The Liquid Templating Markup"
[config]: https://github.com/meerita/minidenet/blob/master/_config.yml "minidenet/_config.yml at master · meerita/minidenet"
[minidenet]: https://github.com/meerita/minidenet/ "meerita/minidenet · GitHub"
[configyml]: https://github.com/mojombo/jekyll/wiki/Configuration "Configuration · mojombo/jekyll Wiki"
