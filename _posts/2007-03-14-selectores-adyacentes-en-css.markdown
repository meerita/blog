---
date: 2007-03-14 20:52:57
layout: post
slug: selectores-adyacentes-en-css
title: Selectores adyacentes en CSS
category: CSS
---

En el [texto anterior](/2007/03/12/codigo-inusual/) a este artículo hablaba sobre la rareza de las reglas de CSS. Es verdad, algunas reglas que fabricamos son realmente complejas, raras, inusuales o simplemente, una belleza a los ojos del programador. Esto último, fue sólo un comentario aparte para los que realmente entienden la belleza de construir reglas.


CSS es sin duda algo más que: ponerle color a las tipografías, hover a los enlaces. Es todo un mundo de opciones para _gobernar_ los elementos de una página. La clave está en comprender primero, cómo funciona CSS, cuáles son los valores básicos que un navegador interpreta y luego, la otra cara del asunto: _los selectores_. Existen varios tipos de _selectores_, y hoy hablaremos del que, curiosamente, tomó protagonismo ayer: _los selectores adyacentes directos_.


### Selector adyacente directo





Muchos desarrolladores cuando empiezan con CSS utilizan sólo un puñado de selectores, por no decir dos o tres selectores. Los principiantes, sólo se cruzarán por su trayecto con _selectores de tipo_:





    p { color: red; }





O bien con un _selector de descendencia_ o un _selector de clase_, como por ejemplo éste:





    div p { color: red; }
    p.texto { color: #666; }





Estos selectores son, en la gran mayoría de casos los más utilizados. Pero en muchos, observaremos que son _demasiado específicos_ con lo que queremos hacer. En el primer ejemplo (`p { color: red; }`) obtendremos un resultado bastante radical: todos los párrafos del sitio, indistintamente donde se encuentren tendrán color rojo. En el segundo, sin embargo, obtendremos párrafos de color rojo cuando se encuentren encerrados dentro de un `&lt;div&gt;`. Entonces, cuando queramos hacer un párrafo de color negro, dentro de este documento, vamos a tener que escribir o bien una regla menos específica o bien una clase más, escribiendo la regla en CSS y en el documento HTML poniéndole la correspondiente _clase_, por ende, más código escrito, más reglas para memorizar en un futuro.





Los desarrolladores un poco más experimentados, digamos, un término medio, sólo se cruzarán con unas pocas reglas más. En mi experiencia, a pesar de que muchos usan las reglas sin tener idea de lo que hace, otros desarrolladores utilizan selectores del tipo padre/hija, clase e identificador. En gran parte, los desarrolladores medios comprenden el funcionamiento a medias de CSS, pero no tienen idea de _especificidad, herencia, atributos y de selectores de clase e identificador_. Está claro: logran cosas que los principiantes _no_, pero terminan armando algo que es imposible luego de controlar: las reglas se pisan una y otra vez, terminando luego de forzar muchas reglas y creando cada vez más clases e identificadores.





Los desarrolladores expertos o bien experimentados logran comprender más allá del fin de la utilización de atributos en una regla de CSS. Comprenden la verdadera _naturaleza del documento_, puede ver su árbol de elementos y también saben el _nivel de complejidad_ que necesitarán para crear una o varias hojas de estilo, las cuales tendrán un set de reglas de las cuales, dependiendo una situación u otras, actuarán. Esto les da un poder de control superior al resto. Mientras el resto de los desarrolladores no experimentados son demasiados específicos;  terminando de escribir reglas _para todos los casos_, elementos y posibles problemas, los desarrolladores experimentados sólo escriben _los casos mínimos_, aprovechando las bondades del árbol de elementos de un documento web, los diferentes selectores, la especificidad, la herencia y cómputos.





Esta es la magia de CSS, **el poder controlar todos los valores**, inclusos aquellos que _no_ están especificados, que pueden salir ya sea por acción de un usuario o por un evento. Pero no me enrollaré ahora con los principios básicos, volvamos a los selectores adyacentes.





Los selectores adyacentes, permiten seleccionar _un elemento vecino_ dentro del árbol de elementos de un documento. Si en un documento CSS tenemos:





    p { color: red; }





Todos los `&lt;p&gt;` de este documento de HTML serán de color rojo, como el ejemplo (marcado en negrita):





    &lt;div&gt;
    	&lt;h1&gt;Este es un título&lt;/h1&gt;
    	&lt;p&gt;Párrafo uno del documento…&lt;/p&gt;
    	&lt;p&gt;Párrafo dos del documento…&lt;/p&gt;
     &lt;/div&gt;





Pero en cambio, si tenemos esta regla de CSS con un selector adyacente, como éste:





    h1 + p { color: red; }





En el HTML sólo el primer párrafo será de color rojo, mientras que el segundo tendrá el color por defecto que se encuentre especificado en el objeto `&lt;body&gt;`.





Entonces, resumiendo: este tipo de selector únicamente trabaja con otros elementos que sean de secuencia, como si se tratara de vecinos. Este patrón puede repetirse, mientras se cumpla la regla, por ejemplo:





    p + p { color: red; }





Todos los `&lt;p&gt;`, que sigan después de `&lt;p&gt;` serán de color rojo, el primero de la línea, _no_.





    &lt;div&gt;
    	&lt;h1&gt;Este es un título&lt;/h1&gt;
    	&lt;p&gt;Párrafo uno del documento…&lt;/p&gt;
    	&lt;p&gt;Párrafo dos del documento…&lt;/p&gt;
    	&lt;p&gt;Párrafo tres del documento…&lt;/p&gt;
     &lt;/div&gt;





En el último ejemplo, los últimos dos párrafos (el dos y el tres) serán de color rojo, mientras que el primero tendrá el color por defecto, especificado o no en el `&lt;body&gt;`.





_Simple como eso_.





### Aplicaciones





Este tipo de selectores son realmente poderosos en algunas situaciones, por ejemplo, cuando trabajamos con tablas. Puede ser realmente útil, de hecho, en [Tractis](http://www.tractis.com) los utilizamos para listados, ya que nos permite dar un formato más inteligente sin tener que escribir reglas y repetirlas en cada fila.





Un ejemplo con tablas sería coloreando sólo una columna, mientras que las demás mantendrán un color por defecto. Hace unos meses planteé la posibilidad con Arnau de hacer esto sin necesidad de escribir reglas. Al principio pensé que lo mejor era utilizar elementos `&lt;colgroup&gt;` o `&lt;col&gt;` en mis tablas, pero Arnau me alertó de los problemas que traía semejante opción. Así que, opté por utilizar un selector adyacente directo y escribir una regla como esta:





    table.listados tr td:first-child + td + td + td { background: #ffffcc; }





Esta regla se aplicará en una tabla identificada como «listados» en cualquier página. Sólo será aplicable en la tercera celda de cada fila que se cree en la tabla. Con esto me ahorro de escribir una regla demasiado específica en CSS y, en cada celda donde quiera aplicarla el atributo `class="colorcelda"` por ejemplo.





Como estas celdas son generadas en base por el sistema, si aplico clases específicas a cada celda podría hacer creer el tamaño de mi documento, se repetiría `class="colorcelda"` cada vez que se genere una fila.





En cambio, si aplico un selector adyacente, aprovecho la naturaleza del documento y las propiedades de selección del mismo, sólo seleccionando aquellos elementos cuando cumplan una condición: _que se encuentren adyacentes_.


Como estas aplicaciones, encontrarán muchas, por ejemplo los títulos en páginas que contengan artículos. El título tendrá un `margin-bottom: 0px` si va acompañado de un subtítulo, pero si no tiene subtítulo podría tener un `margin-bottom: 20px`.


### Compatibilidad


Quizás esta es la parte de la que no me gusta hablar. La realidad indica que, si eres un esclavo del sistema, éste tipo de selectores será inútil en tu vida. Internet Explorer 6 **no soporta este selector**, así de claro y directo. Aún empezando, Internet Explorer 7 soporta este selector.



El resto de navegadores avanzados (Safari, Opera, Firefox, etc.), como de costumbre, sí.





Dicho y hecho, los selectores adyacentes son más que útiles y, muy fáciles de aprender y poner en práctica.





Hasta la próxima charla.
