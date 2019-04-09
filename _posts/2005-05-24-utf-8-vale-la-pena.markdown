---
date: 2005-05-24 20:46:00
layout: post
slug: utf-8-vale-la-pena
title: ¡UTF-8 vale la pena!
category: desarrollo
---

Uno de los graves problemas de la gran red es la internacionalización. Desde un principio, la internacionalización de contenidos siempre fueron definidos por unos pocos estándares, entre ellos los americanos como es el ASCII y algunos corporativos como es el de Microsoft Western Windows-1252. Esto por lo general hace que la mezcla de varios idiomas en un documento traiga bastantes dolores de cabeza.

A veces, cuando intentamos convertir documentos o mezclamos los encodings, las cosas terminan siendo como esta palabra IÃ±tÃ«rnÃ¢tiÃ´nÃ lizÃ¦tiÃ¸n, *¿Símbolos raros eh?*

La cuestión es, *¿cómo podemos ofrecer un encoding de archivo que soporte todos estos idiomas?* Hay uno, que curiosamente he puesto a funcionar hace poco. Se llama UTF-8, pertenece a Unicode. Hay varias formas de UTF, entre ellas la más popular la UTF-8, siguiéndoles UTF-12 y hasta un UTF-32.





Unicode se define con esta frase:

> Unicode provides a unique number for every character, no matter what the platform, no matter what the program, no matter what the language.

Resumiendo qué es Unicode y ventajas de usar UTF-8:


  1. Soporte a todos los caracteres.
  2. Compatibilidad entre páginas (véase compartir RSS, agregadotes)
  3. Compatibilidad entre programas.
  4. Menos configuraciones y cosas raras en el servidor.

Usar UTF-8 beneficiaría a todas aquellas páginas que de alguna forma u otra necesitan ofrecer un soporte de internacionalización a externos, en este caso las personas. Yendo más al grano, si usas en tu _weblog_ UTF-8 por ejemplo, le ofreces a aquella gente que no habla tu idioma poder expresarse con el suyo, que puede ser japonés o ruso y utilizando su set de caracteres.

> Το Unicode vπαρέχει έναν μοναδικό αριθμό για κάθε χαρακτήρα, η ο οποίος πλατφόρμα, το της οποίας πρόγραμμα, η του οποίου γλώσσα.

Si tu página no está codificada con UTF-8, probablemente cuando alguien escriba con un set de caracteres diferentes al que tu has seleccionado el texto se verá lleno de símbolos raros. Entonces, el problema surge a la vista. Para ello tenemos Unicode que nos brinda un soporte universal para que cada documento tenga la capacidad de mostrar diferentes sets de caracteres diferentes.

> やれ打つな蝿が手をすり足をする
>
> Oh, no la aplastes! / la mosca frota sus manos / frota sus pies
>
> Kobayashi Issa 一茶   (1762-1826)

UTF-8 es que puede representar directamente todos los caracteres Unicode. Tener todo este soporte abre muchas puertas y da rienda suelta a la creatividad porque no. Lástima que han rechazado el set de caracteres Klingon.

Minid.net desde este rediseño del año 2005 está utilizando este estándar. De esta forma, no necesito escribir código de entidades ISO o HTML para mostrar unas palabras en japonés en mis textos en español, sino que directamente desde mi procesador de texto pego los caracteres kanji en mi entrada del weblog. Cualquier persona que interprete japonés en su ordenador y tenga soporte UTF-8, verá mi página perfectamente codificada y no tendrá que ajustar sus preferencias de idiomas para verlo.

¿Nunca han visto una que otra página web que se dedique a recopilar noticias de otro sitios usando RSS? ¿Comentarios mal codificados? Habrán notado que algunas de las noticias fueron directamente importadas de UTF-8 a una página y servidor que sólo acepta y sirve `iso-8859-1`. Esto se debe a que no han implementado UTF-8 todavía. Si lo hubieran implementado, probablemente no tendrían que hacer movidas raras de conversión antes de guardar un dato en la base de datos.

Otro punto a favor es la semántica del documento. Al estar escrito en UTF-8, no hace falta un navegador para interpretar el documento sino cualquier programa que utilice UTF-8 (la gran mayoría) para el set de caracteres. Esto también me beneficia para el que busca algo en Google por ejemplo, ya que Google no leerá mi documento lleno de códigos ISO sino palabras escritas en otro idioma, que es muy diferente.

Pasarse a UTF-8 no es tan fácil como copiar y pegar. Primero porque tenés que comprender qué cosas hay que configurar para que todo salga como una joya. Muchos como yo, tuvieron problemas a la hora de utilizar UTF-8 porque cuando publicábamos en la web siempre se observaban los documentos de forma rara.

Qué es lo que hice para tener UTF-8 en pasos:

  1. Codifiqué todas las plantillas de Textpattern con UTF-8 desde mi programa, así soporta desde un principio el set de caracteres.
  2. En el .htaccess de Textpattern agregué una línea que le dice a mi servidor Apache que serviré contenido UTF-8 `AddDefaultCharset UTF-8`
  3. Con un _script_ en la consola del Apache convertí todos mis posts de minid.net de `iso-8859-1` a `utf-8`.

Pedro escribió [una guía estupenda](http://www.kusor.net/article/619/utf-8) para el que tiene un poquito de coraje con estas cosas. Yo hoy agregaré unos detalles que me ayudaron en el traspaso de este _weblog_ a una nueva era de internacionalización.
