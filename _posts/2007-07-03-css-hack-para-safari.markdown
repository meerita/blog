---
date: 2007-07-03 20:05:54
layout: post
slug: css-hack-para-safari
title: CSS hack para Safari
category: CSS
---

Con la reciente salida de Safari 3 en Windows no es mala idea darle un poquitín de soporte si no es mucha molestia. Estuve buscando por la _web_ y muchos de los hacks disponibles no funcionaban con las versiones nuevas y con las muy viejas tampoco. Así que me vine con este ejemplo que funciona muy bien. No recuerdo la página donde lo tomé, pero si buscáis en Google seguro saldrán algunas páginas donde está el mismo ejemplo.



Para lograr el efecto, demos escribir la primera regla para todos los navegadores, o sea, sin hack alguno:


  <code class="css">div#prueba p { color: #f00; } /* IE, Firefox, etc. */</code>


Cuando toque mover el asunto en Safari, escribimos otra línea con el siguiente hack:





    <code class="css">div#prueba p { color: #f00; } /* IE, Firefox, etc. */
    /*\*/
    html*#prueba p { color: #690; } /* sólo en safari */</code>





Es importante que contenga el juego de comentarios `/*\*/` y el selector `html*` para que sólo sea útil para Safari. Pueden ver un ejemplo terminado en este [archivo de prueba](files/safari-hack.html).
