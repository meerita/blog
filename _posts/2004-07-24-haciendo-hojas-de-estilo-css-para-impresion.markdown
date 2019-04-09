---
date: 2004-07-24 23:03:00
layout: post
slug: haciendo-hojas-de-estilo-css-para-impresion
title: Haciendo hojas de estilo CSS para impresión
category: CSS
---

Este creo que va a ser el cursillo de CSS más fácil que voy a contarles: cómo hacer hojas de estilo en cascada (CSS) para impresión. Algo ideal para tu weblog, sitio con textos, etc. Es fácil, sólo hay que tener en cuenta tener ya un sitio con CSS, sino, tomará un poco más trabajo pero también los sitios que no tienen CSS pueden cambiar radicalmente con unas directrices.


#### Primero, comprender cómo funcionan las hojas de estilo





Las hojas de estilo, tienen una función especial llamada "media". Le permite saber a cualquier dispositivo qué hoja de estilo usar. Si miran el código fuente de esta página notaran que tengo una instrucción de XHTML que llama a mi hoja de estilos para imprimir:




  <code>&lt;link rel="stylesheet" type="text/css" <strong>media="print"</strong> href="print.css" /&gt;</code>





Como ven, he creado dos archivos `.css`. Uno que tiene `media="screen"` y otro que tiene `media="print"`. El primero sirve para verse sólo en el navegador y el segundo sólo cuando se imprime o cuando desde el navegador elijes la opción previsualizar impresión.





Esto sirve simplemente para diferenciar diferentes hojas de estilos. Una ventaja para nosotros que usamos código estándar para mantener nuestros contenidos y darle la oportunidad a la gente de utilizar múltiples opciones. Cada opción está beneficiada por una hoja de estilos especial.





En este caso, vamos a cubrir las cosas básicas para experimentar con las hojas de estilo de impresión. Estas no son muy extensibles, pero permiten realizar cosillas interesantes.





#### Paso básico: duplicar la plantilla original y renombrarla a `print.css`





Este es un paso básico. Una vez que terminemos de toquetear nuestra plantilla de CSS de nuestro _weblog_, bastará con salvar como el archivo con un nombre nuevo (`print.cs` por ejemplo) en la carpeta donde está el archivo CSS para el navegador.





Con esto tenemos dos archivos iguales pero nombrados de forma diferente. Luego en print CSS cambiaremos y eliminaremos muchos valores. Pero antes en nuestras plantillas maestras de posts en Blogger, MT o Wordpress tenemos que apuntar el camino a ese archivo `print.css` que salvamos y luego subimos a nuestro _hosting_.





En la plantilla de Blogger o MT pon:





    <code>&lt;link rel="stylesheet" type="text/css" <strong>media="print"</strong> href="print.css" /&gt;</code>





Donde `href="print.css"` cámbialo por la dirección exacta de tu archivo `print.css`, por ejemplo: `href="http://atalaya.blogalia.com/print.css"`. Luego, actualiza tu _weblog_ con una reconstrución total (esto para que el cambio surta efecto en todas las páginas) y con eso ya podremos comenzar a experimentar editando el archivo print.css y subirlo al servidor para ver los cambios.





#### Editando el archivo `print.css`





Recuerda, la propiedad `display: none` será tu amiga de ahora en más. Los valores pt, cm y mm serán tus colegillas de turno, así que acostumbrate a no utilizar ni px, em ni pc porque son valores especiales para **representar en pantalla**, no en papel que es nuestro caso ahora.





Ahora, el paso básico para editar la plantilla es plantearse qué es lo que debe y no debe aparecer en la página cuando se imprima. En mi caso, no me hace falta que aparezca toda esa barra gris que tienes a tu izquierda en la pantalla. Tampoco necesito que aparezcan el logo de minid.net, ni el pie de cada página… sólo quiero que aparezca el _post_; con buena letra; los comentarios y las imágenes que publique en el post también centradas.





Para ello, debemos utilizar el comando `display: none` en todas las cosas que queremos que desaparezca. Un ejemplo claro, en mi weblog, toda la barra gris está bajo una `&lt;div&gt;` llamada menu, sobra con ponerle la instrucción y desaparecerá cada vez que previsualicemos el documento en el navegador antes de imprimir (una buena forma de ahorrarse tinta de la impresora probando):





    <code>div#menu {
    		width: 291px;
    		background-color: #F5F5F5;
    		background-image: url(/images/bg_menu.gif);
    		background-position: bottom;
    		background-repeat: no-repeat;
    		padding: 40px 0 130px 0;
    		float: left;
    	}</code>





Ahora limpiaremos todos las propiedades de `div#menu` y lo reduciremos a esto:





    <code>div#menu {
    		display: none;
    	}</code>





Hacemos refrescar (F5 en el navegador); previsualizamos en nuestro navegador y veremos que el menu no sale… ¡magia!. Ahora debemos ir con cuidado e _ir quitando todo lo que no queremos que aparezca_. Ahora la página se imprimirá con algunos márgenes que quedan. Debes quitar todas las propiedades de margenes de las divs y tablas. Todo tiene que fluir suavemente por la horizontalidad de la página.





#### Mientras vamos probando





Mientras subas un cambio de `print.css` a tu servidor y sobre-escribas tu archivo, siempre debes hacer un refresco de página en tu navegador y luego buscas la previsualización para impresión que trae el mismo.





Haz esto porque sino no verás los cambios cada vez que te olvidez de este paso.





Realizar reemplazo de algunos valores, como por ejemplo las tipografías. Algunas tipografías son feas cuando se imprimen a papel, yo utilizo las tipografías _serif_ para impresión, dan una buena sensación en mi opinión. Además como las tipografías las utilizo con valores `em` lo cambio por `pt` y voy probando hasta tener un tamaño ideal para leer.





Poco a poco vamos limpiando y cambiando valores en la plantilla print.css. Por lo general ésta queda reducida a unas pocas líneas de CSS. Mientras menos mejor, recordad eso.





#### Resumiendo y algunos truquitos





¿Vieron lo simple que es esto? Es una pavada. No hay nada científico, ni dificil, sólo es reemplazar unos valores y quitar otros de una copia de plantilla de CSS. El resto es sólo experimentar para que todo quede bien en papel. Mira como ha quedado mi plantilla [print.css](print.css) es realmente pequeña comparada con [la principal](css/older.css).





#### Un truquillo bueno, que aparezcan cosas cuando se impriman y que desaparezcan cuando se ven en pantalla.





Puedes poner en todas tus páginas un párrafo `&lt;p&gt;` con una clase `class="hide"` por ejemplo, y en la plantilla para ver en pantalla usas el `display: none` para esconder el párrafo cuando mires en pantalla, pero cuando imprimes ese párrafo aparece en el papel. De esta forma, puedes meter por ejemplo, la famosa frase de _copyright_ en tus textos, o la licencia de Creative Commons.





Con éste método puedes esconder una `&lt;div&gt;` con una imágen de fondo blanco de tu logotipo, y hacerlo aparecer y acomodarlo en cualquier parte de la pantalla cuando sea para imprimir, pero esconderlo cuando se vea en la pantalla.





Ahora, si no has entendido, formula tus preguntas en los comentarios. Si entendiste algo, comienza a experiementar, verás que tus resultados serán automáticos y la gente se podrá por ejemplo imprimir tus historias, poemas o la tontería de turno que escribas… como esta :)





_¡Hasta otra!_
  *[em]: End Matched
  *[pt]: points
  *[cm]: centimeters
  *[mm]: milimeters
  *[px]: pixels
  *[pc]: Picas
  *[XHTML]: Extensible Hypertext Markup Language
  *[CSS]: Cascading Style Sheets
