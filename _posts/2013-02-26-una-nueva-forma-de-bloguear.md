---
title: Blogueando como un Hacker con Jekyll
date: 2013-02-26 23:36:12
layout: post
slug: blogueando-como-un-hacker-con-jekyll
category: blogs
---

## Cómo funciona y sus ventajas

Lo primero que tenemos que saber es que **Jekyll no es un sistema de blogs.** Simplemente es un *parser* (analizador, en inglés) que está hecho con el lenguaje de programación Ruby. Fue creado por [Tom Preston-Werner][tom], uno de los cofundadores de [Github][git] y de esto hace ya unos 4 años. Como han leído bien: esta forma de bloguear no es nueva, pero aunque al principio no fuera ultra popular, con el tiempo se ha vuelto una de las mejores opciones para quienes tienen algo de conocimiento de desarrollo.

Jekyll funciona así: lo instalas en tu máquina. Creas una estructura de carpetas, archivos en donde te plazca donde podrás poner tus plantillas y tus posts. Una instalación típica de Jekyll tiene este aspecto:

{% highlight bash %}
  /_posts/
  /_layouts/
  index.html
  _config.yml
{% endhighlight %}

El sitio final no tiene porqué tener esta composición. Normalmente terminarás con más carpetas. Si quieres, puedes clocar unos cuántos proyectos hechos con Jekyll, incluso puedes [clonar éste sitio](https://github.com/meerita/minidenet "meerita/minidenet · Github") para tener un proyecto de Jekyll bien armado con el que empezar.

En `_config.yml` tenemos la información de configuración del sitio. Es lo que lee el ejecutable de Jekyll cuando analiza tu carpeta. Tiene bastantes opciones interesantes, pero no entraré en detalles. Puedes [usar el que yo hice](https://github.com/meerita/minidenet/blob/master/_config.yml "minidenet/_config.yml at master · meerita/minidenet · GitHub") para guiarte. No deberías tocar nada más.

En `_/layouts/` puedes poner tus plantillas. Las plantillas son simples archivos programados en `.html` utilizando [Liquid Templating][liq] y que ahora no entraremos en detalle. En `/_posts/` irán tus entradas, compuestas por unos archivos de texto, escritos usando [Markdown][md] o [Textile][text]. Estas entradas del blog tienen que estar con un formato correcto para que funcionen. Tanto el contenido, como el nombre del archivo. Jekyll leerá la carpeta, analizará cada archivo y luego los convertirá en archivos de HTML.

Como comenté más arriba: las entradas deben estar escritas con alguno de los dos lenguajes, en mi caso uso *Markdown*. Puedes ver una entrada de ejemplo en mi cuenta de Github. Ese es todo el trabajo de escribir una entrada en el blog: abrir un archivo de texto y ponerle una cabecera y el cuerpo del post, algo así:

{% highlight bash %}
  ---
  title: Un título para la nota
  slug: un-titulo-para-la-nota
  date: 2013-02-26
  ---

  El contenido mi entrada aquí
{% endhighlight %}

¡Y ya está! Sólo esto tienes que tener. Claro que si tienes un blog más complejo puedes agregar más variables, como `categories` o `tags` o lo que quieras, yo uso las mínimas ya que luego de ver que nadie navega categorías para qué tenerlas así que las he removido del blog.



Cuando tienes la plantilla del blog que quieres y tienes convertido tus posts a Markdown, ya puedes realizar la primera
ejecución de tu proyecto en Jekyll. Abres una terminal y escribes:

{% highlight bash %}
  jekyll --server
{% endhighlight %}

Si todo ha estado bien instalado, observarás que Jekyll genera todo y te da una <abbr title="Uniform Resource Locator" lang="en">URL</abbr> donde ver tu sitio generado, en mi caso es http://0.0.0.0:4000 y eso es todo. Escribes posts, los tiras ahí y vuelves a levantar el servidor. Jekyll analiza y convierte todo con toda la información que le pidas.

### Estático vs Dinámico

Ambos mundos tienen sus ventajas. En caso de los blogs, con pocas o muchas entradas (el mío tiene 3000 y algo) el mundo estático les va mejor. Cuando tienes un blog muy concurrido empiezas a notar los dilemas de servir páginas hechas al vuelo. En un CMS dinámico tienes que utilizar alguna solución de *caching* lo cual tampoco te asegura la supervivencia del sitio. Es por eso que muchos sitios simplemente no sobreviven al asedio de visitas y encima manteniendo comentarios. Cuando tienes muchas entradas, el blog no genera caché hasta que no está visitada, cuando tienes muchas el blog se la pasa generando caché sin parar, sin contar aquellos que tienen comentarios abiertos. No está mal, pero no es la mejor solución.

En cambio un sitio estático no tiene ningún tipo de fricción, sólo hay que tener bien configurado el servidor Apache o Nginx como es mi caso, para poder servir grandes cantidades de documentos sin problema. No se utilizan recursos del servidor para gestionar la base de datos, ni generar cachés, ni alojar comentarios (esto último lo generas si quieres con un tercero) y el servidor únicamente se dedica a presentar la página.

En materia velocidad se nota bastante. Si la página (la dinámica) no está cacheada, puede irse a 7 u 8 segundos o más, dependiendo tu servidor, tu plantilla y contenido. Con Jekyll, esto se reduce drásticamente siempre y cuando tomes decisiones inteligentes para distribuir las cargas. En mi caso, pasé de 480ms a 60ms. Una página no cacheada no supera ~175KB y cuando actúa el caché y, la compresión entran en juego, ¡sólo transfiero ~25K en total!

El resultado es impactante. Sobre todo en móviles. La velocidad y el aprovechamiento de caché en móviles trabaja perfectamente cargando cara página en un pestañeo. La velocidad de carga en ordenadores de escritorio con wifi: imperceptible. Los resultados de tests de optimización y velocidad al día. Google Speed Test da un resultado de 94, el de YUI 96 y todavía no terminamos de optimizar algunas áreas para que todo vaya como la auténtica seda.

### Razones personales

Experimentar. Probar cosas nuevas. Realmente no ha cambiado demasiado mi forma de escribir en el blog. Principalmente porque uso un editor de textos para escribir mis posts desde el año 1998. Cuando por fin tuve un CMS, decidí que no podía confiar, literalmente, en los sistemas de conversión WYSIWYG que traen los editores de CMS. Así que seguí con mi tradición. Estaba cansado de publicar copiando y pegando HTML en un campo de formulario. En el pasado, cuando era cliente de Textmate, lo hacía directamente desde el editor, pero luego dejé de usarlo y la comodidad se perdió.

Los CMS con el tiempo devienen en bestias indomables. Wordpress requiere bastante toqueteo para estar a la altura de lo que uno quiere hacer. A veces uno tiene que hackear el `loop` que trae, a veces uno tiene que programarse en PHP porque como está todo hecho a veces no cumple las necesidades que uno quiere. Ni siquiera quiero hablar de Drupal, hay que ser un loco suicida para tener un blog con Drupal, requiere tocar de todo y es sólo para los masoquistas. Todo y eso, los CMS han satisfecho las fantasías más húmedas de los desarolladores y editores de sitios que a tal punto, muchos de estos CMS dejaron de ser sólo una herramienta de blogs. Así que decidí hace tiempo volver a lo estático, a lo simple y lo rápido.

Sin señalar a ninguno en especial, los CMS son una montaña de oro detrás de una puerta de papel: viven asediados de hackers. Hay que actualizar el blog permanente para todo. Si te olvidas de actualizarlo, corres peligro de que tomen el servidor, que te usen el servidor como servidor de correo electrónico o bien te llenen las 4000 entradas del blog que tengas con enlaces de viagra. Esto no lo sufro más. Mi servidor sólo es un servidor Nginx. No hay MySQL instalado, no hay PHP, no hay Ruby. Nada. Todos los problemas de seguridad quedan relegados a actualizar Linux con el último parche y las cosas que uso. Todo lo genero en mis ordenadores en local.

### Futuro

Aprovechar la simpleza de publicación para publicar semanalmente y aprender más a generar cosas con Jekyll, que es una filosofía  interesante.

Seguir mejorando el rendimiento de todo el sitio en general manteniendo un nivel alto de resultado en exámenes de optimización. Si no pasa de 90, entonces descartaremos cualquier tipo de solución.

Mantener el código para que siga siendo cómodo de navegar en teléfono, iPad/Nexus y ordenadores. Un código ordenado, limpio y bien programado en todos los niveles.

Próximamente verás en este blog un curso para instalarlo y, si no quieres perder tiempo, tienes el repositorio de mi sitio disponible para generar tu sitio en Jekyll y empezar a probar una nueva forma de bloguear… *¡como lo hacen los hackers!*

[jk]: http://jekyllrb.com/  "Google Search for life"
[tom]: http://tom.preston-werner.com/ "Tom Preston-Werner"
[git]: http://github.com/ "Github · Build software better, together."
[pages]: http://pages.github.com/ "Github Pages"
[ruby]: http://www.ruby-lang.org/es/ "Lenguaje de Programación Ruby"
[text]: http://textile.sitemonks.com/ "Textile 2.2 Test Page"
[md]: http://daringfireball.net/projects/markdown/ "Daring Fireball: Markdown"
[liq]: http://liquidmarkup.org "The Liquid Templating Markup"
