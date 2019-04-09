---
date: 2012-10-14 17:14:33
layout: post
slug: el-nuevo-minid-net
title: El nuevo Minid.net
category: minid
summary: This is an old blog post. The original design can be seen in the Web Archive. 
---

Sí, esto que estás viendo es el nuevo cambio de aspecto del blog. Cuando te obsesionas por el diseño y las tecnologías muchas veces terminas harto de ellas y en muchos casos, ciego. Eso me ocurría con el antiguo diseño: Bonito a la vista, incómodo en la práctica, y hasta desmoralizador, diría.





Así podría haberlo definido y, he de admitir, **estaba totalmente equivocado** cuando lo hice, en parte por querer meterme con un diseño basado en grillas totalmente complicado y tipográfico, engañándome a mi mismo mientras lo estaba poniendo en práctica. Con el poco tiempo, el diseño hizo notar sus flaquezas y sus crecientes problemas. Pero lo peor de todo es que tanta producción de diseño terminó aburriéndome y, eso como diseñador suele ocurrirme con las cosas sobre-producidas, con el diseño superfluo que estos días llevo presenciando.





Intentar hacer algo producido en realidad me llevó al efecto contrario que deseaba obtener, por lo tanto, el mismo diseño me llevó a dejar de lado el blog.





En el teléfono no podía verlo, en el iPad, menos. En el portátil me traía algunos escozores pero terminaba por dormirme. No era un diseño orientado a la lectura, sólo a la obsesión por meterlo todo en una grilla y así obtener una forma armónica.





Hace años me refería a este tema con una pasmosa claridad:





> Hace unos días deliraba una pregunta en mi cabeza, ¿por qué no se hacen todas las cosas simples? No pude sacar ninguna conclusión inmediata, así que me puse a leer unas cosas. Entre estas volví a leer un par de capítulos de Don A. Norman y otros como Eduard Tufte, llegando a la conclusión que, hacer algo simple es difícil. Suena cómico, algo que tenga las opciones esenciales sea difícil de hacer. Seguí realizando anotaciones en mi libreta de bolsillo y descubrí un posible patrón a este dilema: creo que a veces transformamos las cosas innecesarias en cosas esenciales creyendo que lo son.





Con el paso del tiempo, e intercambiando muchas tardes de diálogo con el diseñador [Rodrigo Galindez](http://www.rodrigogalindez.com) hice que esta premisa se haga parte de mi ADN de nuevo: volver a las raíces del diseño sencillo, sin complicaciones ni dificultades. Volver a la pureza del diseño mismo y, concentrar los aspectos esenciales y liberarlos de la innecesaria carga que producen los aspectos innecesarios.





Otra de las razones por las cuales he decidido optar por este camino de purificación visual han sido las aplicaciones que estoy usando. Por ejemplo IA/Writer me ayuda a abstraerme de todas las sofisticaciones de la informática para enfocarme directamente en la tarea de escribir. Comprobado, puedo pasarme horas escribiendo sin darle a mi cerebro razones para perder el tiempo con nimiedades. Sorprendentemente, las aplicaciones de iPad en general también evocan este diseño honesto y simple que te motivan a hacer, más que perder el tiempo.





Y así terminé diseñando el blog. Un lienzo en blanco, una grilla meditada y tipografías.











### Ser tu propio cliente





Si realmente vas a diseñar algo… debes ser tu propio cliente. Si algo no lo utilizas con gusto y no te  ayuda, es algo que has planteado mal desde un principio.





> When you are your own target audience you can’t help but make better products.





A lo largo del tiempo que dejé de hacer proyectos para otros para hacer uno para mí, me di cuenta de ello. _No hay mejor forma de diseñar las cosas que pensando en ser cliente de ellas._ ¿Usarías esa barra de navegación? ¿leerías esa introducción en la página de inicio de la empresa? ¿Llenarías un formulario así de largo y complicado? Así que cuando planteé este diseño para el blog pensé en todas las cosas que realmente me gustaría solucionar y tener:


  1. Absolutamente en HTML5.
  2. Uso de CSS3 estándar.
  3. Uso de SVG en vez de imágenes normales.
  4. Tipografías.
  5. Economía de recursos.

La decisión de usar HTML5, CSS3 y SVG no ha sido difícil. Atrás quedaron los días en donde usar HTML5, CSS y PNG eran un trauma. Ahora la gente que ingresa con navegadores realmente problemáticos se ha reducido a nada. IE6 es ya un recuerdo malo, como si habláramos de la pasada epidemia de la vaca loca. El auge de las tabletas y de los iPads, iPhones y iPods es realmente impactante y la implementación de webkit como motor de navegadores es realmente impresionante, haciendo que mis problemas de dudas sobre si tomar un camino u otro ha sido lo de menos. En un futuro muy cercano, la balanza de accesos desde estos dispositivos se inclinará, como lo está haciendo ahora y no será tan tarde ver estadísticas de acceso con dispositivos mayores al 50%, prácticamente en Europa todo el mundo tiene un smartphone con algún navegador decente. Google activa millones de teléfonos al día, al igual que Apple y otros fabricantes y usan navegadores potentes en sus teléfonos y tabletas, ¿por qué esperar?





Por otro lado es importante mantener todo en lo posible austero, sin emplear cantidades ingentes de código para lograr un efecto realmente innecesario, así que todo mi código es estándar, y eso significa que, si hay algún navegador que no soporte la directriz border-radius, pues que esta nimiedad no suponga un problema para el lector del blog para seguir leyendo.





Otro punto importante de éste es, no me interesan tampoco los arreglos de HTML para soportar una u otra cosa de Internet Explorer, ni Modernizr, ni otras cosas que JS soluciona, quiero una página libre de sobrecargas. Si lees esto, está hecho con lo mínimo y disponible en un navegador. El uso de JS es estrictamente hecho para, por ejemplo, colorear el código de ejemplo en tutoriales, y basta.





SVG es un tema aparte, pero la sola mención probablemente ya te haya hecho pensar que es. Simplemente, elimino todo uso de imágenes y lo reemplazo por SVG. Esto me permite ganar independencia de resolución, flexibilidad a la hora de adaptar todo y un mayor ahorro de recursos. Como he mencionado antes, tengo pendiente hablar a fondo de SVG, para que conozcáis todas las ventajas del tema.





El tema tipográfico es simple. Con la venida de pantallas de alta resolución, los dispositivos HDMI y otras yerbas, usar tipografías que no estuvieran por defecto instaladas en el sistema se ha vuelto viable. El sistema realmente funciona de maravillas y no tengo queja alguna. Si alguien entra con un dispositivo que no soporta tipografías web, simplemente verá las de sistema.





El resultado de todo esto me satisface demasiado. El peso de cada página es nimio ahora y se carga velozmente en mi teléfono, también en mi ordenador. Las imágenes en SVG al estar en el mismo HTML se comprimen con este, reduciendo drásticamente el uso de recursos y permitiéndome obtener la tan deseada              independencia de dispositivos y lograr también que todo se pueda usar aprovechando los caches de los teléfonos, tabletas y otros dispositivos que no disponen de la potencia y recursos de los ordenadores  ordinarios.











Eso es todo. Lo próximo será comentar un poco SVG que es un tema que está obteniendo toda mi atención que suelo mencionar bastante en [mi línea de tiempo de Twitter](http://www.twitter.com/minid).
