---
date: 2012-10-26 14:00:35
layout: post
slug: descubre-el-fabuloso-mundo-de-svg
title: Descubre el fabuloso mundo de SVG
category: desarrollo
---

Entonces tú querías aprender SVG y has llegado a este artículo. **Pues éste es el momento.** Ni dentro de 5 años, ni en 10… **ahora**. SVG ya está presente y pocos le dan la suficiente atención. Pero no importa, te voy a explicar todo básico sobre SVG para que empieces por tu lado a investigar, probar e, implementar, claro.

<figure class="draw">
  <img src="/images/camiseta-boca.svg">
</figure>


Esta bonita imagen que ves, con todos esos colores, además de ser la ilustración de uno de los conjuntos oficiales utilizados en el 2012 por el glorioso, Rey de Títulos, Club Atlético Boca Juniors (del cual no voy a negar mi eterna fidelidad) también es **una imagen en formato SVG**. Si miras el código de la imagen, observarás que es XML.





_¿Y de bueno qué tiene esto? –Se parece mucho a una imagen JPG, PNG o GIF.–_ Bueno, es cierto, en calidad se parece mucho al resultado que daría un GIF o un PNG, pero si tienes un iPad 2 o 3 (o cualquier otro tablet con Android), puedes hacer una ampliación y, como podrás observar, **la calidad no se ha perdido**, no hay «pixelización» alguna de la imagen.





Esto se debe porque el formato del archivo es vectorial y no es una imagen bitmap: no pierde calidad y asegura la _independencia de resolución_.











### Independencia de resolución





En el actual estado de permanente expansión y crecimiento tecnológico, todos los días hay novedades en formas de visualización HiDPI. Salen nuevos teléfonos inteligentes, tabletas y nuevos ordenadores con tecnología que, literalmente, en muchos casos duplican (y hasta cuadriplican) la cantidad de pixeles por pulgada en cada dispositivo, dando por resultado imágenes con un notable crecimiento de detalle y definición.





Esta concepto tecnológico, que fue creado en 1978 por Donald Knuth, permite que el software y el resultado visual de éste sea independiente de la resolución destino. Cada dispositivo podrá mostrar de la mejor forma algo, sin lugar a pérdida.





Si bien en materia ordenadores esta tecnología todavía está en pañales, en 5 años probablemente todos los fabricantes ya tendrán modelos HiDPI _de toda_ su línea de ordenadores y sus tabletas digitales. Apple, por ejemplo, _ya tiene el primer portátil_ con tecnología HiDPI que ellos mismos denominan comercialmente como [Retina Display](http://en.wikipedia.org/wiki/Retina_Displays).





¿Y a qué viene que exista más resolución? Como acabo de explicar antes, estos dispositivos aumentan la cantidad de pixeles por pulgada haciendo que muchas cosas aumenten en definición, sobre todo aquellas que son, por antonomasia, formada por vectores. Lo primero que notas con un dispositivo HiDPI es que el texto está mejor definido. Esa es la primera. La segunda es que muchos de los efectos hechos en CSS, algunas cajas y elementos del sistema operativo están perfectamente dibujados en pantalla. Lo único que realmente ves hecho una mierda son las imágenes.





Las imágenes fueron creadas en general para dispositivos que tienen la relación 1:1 de pixeles. O sea, para los ordenadores y dispositivos como los nuestros, que no son HiDPI. Para que las imágenes se miren bien en una pantalla HiDPI hay que hacerlas el doble de grandes y reducirlas al tamaño que las queremos mostrar para que los monitores antiguos puedan mostrarla y los monitores HiDPI puedan aprovechar todos los pixeles disponibles de pantalla, lo que resulta en usar siempre imágenes el doble de grandes, más peso, más lenta la descarga del sitio será.





Existen más técnicas raras, que involucran el olfateo de dispositivos y así sirven una imagen u otra, terminando en un caos de comprobaciones. Pero esto, gracias a la tecnología, sólo involucra a las fotografías y no a aquellas imágenes bidimensionales formadas por vectores.





La independencia de resolución es uno de los conceptos más importantes de esta década y viene para quedarse. Viene a ser de importante como los estándares web en los años 1999 y 2000. Los desarrolladores ya tienen que pensar en desarrollar un producto que se pueda ver en diferentes dispositivos con diferentes capacidades de resolución. Quien obvie esto simplemente se está obligando a trabajar de más en un futuro, o en tirar todo el trabajo hecho, o bien exponerse a una horrible visualización de su contenido.











### Qué es SVG





SVG básicamente **es un modelo de imagen bidimensional basado en XML estándar.** Fue ideado en 1998, pero no fue hasta 1999, según las fuentes, cuando empezó a despegar como desarrollo. La fecha marcada por Wikipedia es el [4 de septiembre de 2001](http://www.w3.org/TR/SVG10/) que es cuando el W3C denomina como «recomendación» al lenguaje. Eso ocurrió hace 11 años, amigos.





En 11 años, SVG creció sin parar, tanto en adopción de navegadores, como adopción por parte de los fabricantes de software. Adobe, uno de los pioneros en el tema (fue el que introdujo el lenguaje PGML que más adelante fomentaría la creación de SVG junto a la absorbida Macromedia) empezó a soportar SVG como formato gráfico en sus aplicaciones vectoriales. Hoy en día, puedes trabajar con SVG en ADobe Illustrator® sin ningún problema. Si no tienes la oportunidad de usar este software privativo, puedes optar por la excelente y nada incompleta solución vectorial Inkscape, u otras: iDraw, Sketch, etc. Pero lo más alucinante de SVG es que puedes crear imágenes a partir de código, a diferencia de otros formatos, XML tiene un idioma digerible por un humano, haciendo de éste un formato ideal para servirlo por partes o bien para modificar o animar determinadas partes del mismo.





¿Cómo se conforma un archivo SVG? Si entiendes XML te será muy fácil, nos basta con abrir un nuevo documento .svg en nuestro editor y escribir esto:




{% highlight html %}
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
 <svg
   version="1.1"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:xlink="http://www.w3.org/1999/xlink"
   x="0px"
   y="0px"
   width="500px"
   height="500px"
   xml:space="preserve">
   <polygon points="30,100 30,468 473,468 473,218 302,30 "/>
</svg>
{% endhighlight %}

Y con eso ya hemos creado **un primer documento SVG** con una figura primitiva no muy difícil de dibujar. Es un pentágono. Y el resultado de este código sería esta imagen que veis a continuación:

<figure class="draw">
  <img src="/images/test.svg" alt="Pentágono generado con SVG">
</figure>

Podrán observar que el elemento `svg` tiene un montón de atributos uno debajo del otro, simplemente lo hice así como ejemplo porque todo no puede entrar normalemente de forma horizontal. Si desnudamos el código ofrecido, la imagen se reduce todo al elemento `&lt;polygon&gt;`.  Este elemento se define por puntos y para que entendamos cómo se forman cada puntos tengo este gráfico (hecho en SVG, claro) que explica la anatomía de los puntos en un gráfico simple de SVG:

<figure class="draw">
  <img src="/images/svg-anatomia.svg" alt="Anatomía de SVG">
</figure>

Como pueden observar, cada punto está definido por una serie de códigos numéricos, como lo es `30,100`. Este código simplemente define un punto en el eje **x 30** y en el eje `Y 100`. Cada punto va definido así, separados por un espacio. Los puntos pueden ser incluso más precisos, podemos especificar puntos luego de cada valor, como por ejemplo:


    300.298,300.889


Este ejemplo de código simplemente nos diría que ese punto en el documento SVG se encontraría en el eje `X=300.298` y en el eje `Y=300.889`. El resultado es posible que sea horrible ya que el valor `1` equivale a 1 pixel en este caso, el eje Y estaríamos hablando ya de casi un pixel extra, si fuera un monitor con Retina es probable que veas bien todo pero en un monitor normal, verías quizás un difuminado.

El orden de serie de estos puntos es indiferente, ya que podemos empezar la serie de atrás para adelante y obtener la misma forma primitiva.


Pero esperen, SVG **no es así de fácil** cuando se trata de hacer, como en mi caso, una camiseta más arriba en este artículo. Eso es más complicado e imposible de hacer prácticamente a mano ciertas ilustraciones pero muchas otras sí son posible.


Lo bueno de SVG a diferencia de otros formatos gráficos es que **podemos cambiar el código fuente y alterar el contenido de cualquier imagen**, ya sea a mano usando el editor y subiéndolo de nuevo al servidor o bien manipulándolo con Javascript.


En las siguientes entregas de este macro-artículo veréis diferentes temas relacionados con el código, ahora me quiero centrar en la parte introductoria.




### Compatibilidad

Como toda tecnología, lleva su tiempo para que se adopte en todos los ámbitos. SVG era impensable en el 2003, pero en el 2012 ya es bien factible, si desarrollas realizando métodos de detección para servir el contenido adecuado según el rango de navegadores. Aquellos que son modernos se beneficiarán increíblemente en comparación con aquellos que no. Los usuarios de navegadores antiguos pueden seguir viendo la web como tal y no se liarían a hostias.


El soporte básico de SVG es [actualmente soportado](http://caniuse.com/#cats=SVG) por los siguientes navegadores en su versión mínima en adelante:


  * Internet Explorer: 9


  * Firefox: 3


  * Chrome: 4


  * Safari: 3.2


  * Opera: 9


  * Safari iOS: 3.2


  * Opera mini: 5


  * Opera mobile: 10


  * Chrome en (android): 18


  * Firefox en (android): 15


Como pueden ver la adopción es masiva, pero sólo una parte de SVG. SVG se compone de varios módulos, algunos más avanzados que otros y otros todavía están en el nivel de «borrador» y no están, siquiera, implementados todavía en algunos navegadores, pero bueno, de aquí a 5 años el soporte de éstos será total y garantizado. Igualmente, para lo básico que puede llegar a ser ilustraciones de páginas web, SVG es sin dudas es una bendición y no debería causar muchos problemas.


Las cosas que no están totalmente soportadas por completo, o simplemente de forma parcial son los módulos de SVG Filters y SVG CSS Background. SVG Filters, básicamente, son filtros para conseguir efectos gráficos potentes en nuestras imágenes de SVG. Un ejemplo de filtro es "blur", por ejemplo. El otro módulo que no está 100% soportado pero que lo será en muy poquito tiempo es CSS Backgrounds y tienen algunos inconvenientes en algunos navegadores de momento.
