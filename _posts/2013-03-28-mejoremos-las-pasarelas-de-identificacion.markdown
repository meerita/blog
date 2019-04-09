---
title: Mejoremos las pasarelas de identificación
date: 2013-03-28 12:12:12
layout: post
slug: mejoremos-las-pasarelas-de-identificacion
category: desarrollo
---

Si hay algo que me pone los pelos de punta son las páginas de acceso a la conexión WiFi que ofrecen operadoras de todo tipo en restaurantes, terminales aéreas, universidades y hoteles, por citar lugares habituales. Tienen varios tipos de denominaciones: pasarelas de acceso WiFi, punto de acceso, páginas de identificación, etc. Seguro que leyendo esto ya sabe de lo que hablo. Estas páginas quizás son todavía un reducto visible de la internet de los tiempos de Maricastaña. Hable con quien hable, casi siempre le dirán lo mismo: *son una mierda*.

¿Por qué estás páginas que nos permiten acceder a internet u otros servicios son tan malas? Existen bastantes razones y se reparten por los siguientes territorios: código anticuado y mal hecho; una importante acumulación de malas prácticas de diseño; y para finalizar una dejadez digna de best-seller.

Estas son las principales razones por las cuales estas páginas todavía no están a la altura de servicio que deben ofrecer. La experiencia de usuario a veces llega a ser tan mala que pone en juego todo el resto del servicio. El punto de acceso siempre ha sido un servicio menospreciado, aunque no lo parezca o digan lo contrario, es un servicio que claramente secundario y se debe, claramente a la poca atención que le merecen.



> Casi todas maquetadas con tablas. [@alpoma][alpoma]

Estamos en 2013. Cabe destacar que, hasta hace 5 años, la penetración de novedades en materia lenguajes frontend era más bien escasa. Pero ahora, con las nuevas tecnologías se puede programar mejor.

Pero todo este benevolente baño de tecnologías no parece limpiar la suciedad de estas pasarelas de acceso: todavía se utilizan en la realización de las mismas una sarta de elementos inapropiados para realizar la disposición del diseño. Un ejemplo claro y asesino es el de maquetar el sitio usando el elemento `TABLE`. Que bien podría uno ganarse la horca o la guillotina automáticamente por maquetar así. Sin embargo es la cosa más común que podemos encontrar hoy en cualquier punto de acceso.

Otra horrible práctica es la de realizar la maqueta utilizando imágenes a modo de composición: gifs transparentes, imágenes con curvas rebuscadas que tarde o temprano conformarán la forma de la pasarela como si se tratara de un rompecabezas. Esto es un error que se debe pagar caro. En la época de Julio César mataban a uno por menos. Sin embargo, aunque parezca un terrible sacrilegio, también sigue siendo una práctica asidua y aceptada. Muchos gerentes, directores que no tienen ni la más remota idea de diseño dirán «preciosa» pero el resto de los usuarios no opinarán lo mismo.

Entre todas las prácticas luego están las menos graves: como pueden ser la utilización de campos de metadatos de HTML que nadie analiza ni tampoco cumplen una función esclarecedora para el usuario final o un robot analizador. O bien elementos de HTML desautorizados o con valores semánticos nulos como pueden ser los elementos `B`, `I`, `BIG`, `SMALL` y otros. Estos no tienen un impacto grave, pero en abuso se pueden sentir bastante más si se accede desde teléfono.

> Para tener una excelente pasarela **el código tiene que ser limpio, ordenado y estándar.** Piense ya en HTML5.

Esta práctica viene heredada desde hace ya unos cuántos años, cuando los *smartphones* eran unos terminales realmente patéticos y con capacidades realmente limitadas pese a que fueron novedosos para su época. Venían todos con versiones limitadas de navegadores como el Internet Explorer u otros de carácter propietario, como los que venían en los Nokia con Symbian. Eran navegadores que, claramente no podían soportar siquiera parte de la especificación CSS2 u XHTML 1.0. Entonces, para hacer que la pasarela «se vea bien en todo» había que hacerla con tablas; recortando imágenes hechas en Photoshop; encajándolas en celdas y todo esto usando todas las técnicas más ruines de desarrollo web.

Pero con la llegada del iPhone y, posteriormente, Android, esto cambió para siempre: *ahora los terminales sí son inteligentes* y soportan casi los mismos estándares de sus pares mayores, por lo tanto no hace falta seguir usando HTML3 mezclado con XHTML y luego metiéndole tecnologías propietarias. Hay que programar ya en HTML5.

Incluso en los países emergentes la penetración de teléfonos móviles ha sido alta y crece a pasos agigantados. La penetración de teléfonos inteligentes en Europa y el resto del mundo es altísima. Busque en Google un poco sobre el tema y los números dan escalofrío de los saltos que dan. Sobre todo aquella que está representada con la bandera de Android. La cantidad de terminales se duplica año tras año y según los baremos de algunas empresas, el tráfico de teléfonos y dispositivos móviles crece sin parar y ya en muchos casos representan más del 30% del tráfico. Por lo tanto, tener una página con prácticas de código antiguas es cuando más [un craso error][craso].

> Acceder desde el teléfono, una panacea.

Otra de las titánicas tareas a superar es acceder al servicio WiFi desde el teléfono. No porque Apple o Google hayan diseñado mal la sección de configuración de su teléfono, esa sería la parte fácil si los comercios no utilizaran pasarelas de identificación, es porque en realidad estas páginas al tener un código tan antiguo es cuasi imposible usarlas con las yemas de los dedos.

Accedes a una pasarela y lo primero que ves es una superpágina reducida a `320px` de ancho. Es imposible leer algo porque la letra es muy diminuta. Pero esto no es lo peor: los campos y los enlaces son demasiados pequeños. Hay que darle a un campo de formulario con la yema del dedo índice y rezar para darle en el primer intento sin darle accidentalmente a otro enlace o a otro campo. Ése es un método. El segundo, que no siempre funciona porque desactivan el zoom, es hacer *pinch* (pellizcar) con los dedos para aumentar la zona y ahí recién podemos hacer un toque con las yemas de los dedos para activar el formulario.

Es normal que la experiencia en el móvil sea horrible. Como anticipé al principio de la entrada: es rara la pasarela que utiliza código nuevo y que esté bien hecho. Sé de buena fe que que muchos de estos trabajos son externalizados a agencias y freelancers por *dos duros* cuando en realidad deberían invertir más dinero en hacerlas mejor.

Si alguien realmente hiciera un estudio de su sistema de pasarela de identificación y nota que 9 de cada 10 no pueden hacer las cosas de forma fluida se daría cuenta automáticamente de lo horribles que están hechas algunas de las mismas. Y no se trata de cambiarle el diseño sino de programarlas mejor para que se adapten a todas las situaciones.

### Diseño, inexistente

Muchas de estas pasarelas de identificación a pesar de tener colores, tipografías y fotografías son una auténtica bazofia de diseño. Si alguna vez le dan dado un puntapié en los dídimos, El primer síntoma es ver un diseño del año 2000 o anterior: una página maquetada a menos de 1024px con letra en `10-11px` puede ser la primera puntada de dolor. El segundo síntoma es la imagen de fondo: de `500Kb` a `1MB` de peso normalmente van estas imágenes, que suelen tener fotos escaneadas de los menús del restaurante o bien una foto sin tratar de alguna mujer feliz de catálogo. Una felicidad hipócrita, porque nadie en su sano juicio ríe luego de usar su pasarela de identificación.

*El diseño de estas páginas tiene que cambiar.* En el pasado, realizando estudios con personas en algunos tipos de pasarelas y aplicaciones la evidencia arrojaba datos estremecedores y puede que le resulte impactante: la gente le importa de poco a nada estos detalles de diseño. Casi todos los usuarios tienen la preocupación de realizar la tarea, no de apreciar la calidad de diseño, que normalmente es la que arruina la experiencia total.

**El usuario promedio no es diseñador.** No sabe de nada de diseño, aunque crea que sepa, **no tiene la capacidad ni el tiempo necesario para juzgar un trabajo de diseño**. Si usted creía que un usuario cada vez que entra a su pasarela de identificación se pone a realizar una crítica de diseño y con eso le pone una medalla, está usted más equivocado que Craso cuando subestimó a los partos. Es por esto que el diseño debe ser invisible. Un buen diseño no obliga al usuario a perder tiempo y le ayuda realizar su tarea satisfactoriamente. Si el diseño entorpece, entonces usted pone en peligro todo el conjunto, no sólo la calidad del diseño, sino, toda la experiencia de usuario.

El diseño es importantísimo y las mejores recomendaciones que puedo dar para estos casos es:

1. Usar tamaños de tipografías grandes.
2. Usar campos de formulario grandes.
3. Evitar el uso de fotografías.
4. Realizar una buena disposición de elementos.
5. Economiza en recursos.

Estamos en 2013. Los monitores de baja resolución y las placas de vídeo de 512MB son una rareza. Si esto es así entonces, ¿por qué seguimos usando letra pequeña? El tamaño de la tipografía tiene que ser visible. Bien visible. No recuerdo cuando fue la última vez que he visto una mayoría de accesos con resoluciones inferiores a `1024px`. Es por ello que utilizar letra pequeña no tiene sentido. ¿Por qué no mejor utilizar tamaños arriba de `13px`?

Si usted cree que leer la información de su pasarela en un teléfono está bien: está usted equivocado. Uno tiene que empañar la pantalla del teléfono para leer lo que dice su pasarela, es un terrible error.



Los formularios es todo un tema. Por norma general, no están siempre bien hechos. Por ejemplo, usan alguna técnica rara de envío, los campos están metidos dentro de *divs* para alcanzar un estilo de diseño. Los campos de formularios, cuanto más estándares, mejor. Nada de utilizar Javascript para posicionar, medir lo que uno escribe, nada. La clave debe ser suficientemente fácil para que no tengamos que hacer malabares y sentirnos penalizados por la ineficacia del navegador que utilicemos en aquel momento. Pero lo más importante de todo es: los campos deben ser grandes, bien grandes. Nunca me he encontrado un campo de formulario grande. Nunca. Lo normal es encontrar formularios minúsculos dispuestos en el lugar más desafortunado de la página.




El tema de las fotografías es cómico. Es increíble que un diseño esté condicionado por fotografías y fondos coloridos hechos a base de imágenes. La conexión entre el router y tu dispositivo siempre es lenta. A veces puedes esperar 20 segundos mirando la pantalla en blanco hasta que la imagen de fondo de la chica feliz o del plato de pasta se termina de cargar. En serio: esta práctica debe morir y los que la promueven, también.

Las pasarelas deben ser modificables, sí, en colores y como mucho, un logotipo. Ya está. No hace falta montarse un diseño al mejor estilo catálogo: el usuario común no es crítico de diseño, no posee la capacidad crítica para valorar vuestro trabajo y esto ni tampoco hará que suba en calificación la calidad del servicio que usted pretende ofrecer. La calidad del servicio siempre se valorará por otros axiomas: la velocidad de conexión, la facilidades que se ofrecen para realizar la tarea y por el coste de la misma. Si usted convierte esta página en un sitio web está cometiendo un error. El usuario no comprará nada, ni le interesan las promociones, ni mucho menos, tiene el tiempo para cambiar de parecer, sólo quiere una cosa: identificarse y usar la conexión.

> Una buena disposición de objetos en la pantalla, ¡aleluya!

Otro aspecto importante es la disposición de los elementos en pantalla. En fotografía, todo el mundo se mata para realizar una buena composición. En diseño de sitios web todo el mundo se mata para ver quien hace la peor composición. Y muchos lo logran con bastante esmero. Un buen diseño, con una buena disposición de elementos es una de las prácticas es la más raras de ver. Todo va siempre como el diseñador o el jefe quiere y esto debe terminar. Hay que elegir una buena disposición y probarla hasta que el diseño demuestre la fuerza que necesita para evitar fricciones a los usuarios que lo utilizarán.

Lo más fácil es eliminar toda información innecesaria. El usuario sabe que tiene que «meter un código», el tema es no hacerle perder el tiempo mostrándole información que no necesita: muéstrele el formulario donde debe poner el código primero. La pasarela de identificación no es el mejor lugar para promociones, ni para torturlar la mente a su cliente con su marca, sus valores, ni su filosofía. La gente entra ahí sólo para meter el código, conseguir acceso a Internet y olvidarse de la cara de los directivos de su empresa, es así.



Es de vital importancia realizar estos cambios. Necesitamos mejores servicios y eso no se reduce a tener una conexión gratuita.

[minid]: http://twitter.com/minid  "Diego Lafuente (minid) en Twitter"
[alpoma]: http://twitter.com/alpoma "Alejandro Polanco (alpoma) en Twitter"
[craso]: /2006/05/26/craso-error/ "Craso error"
