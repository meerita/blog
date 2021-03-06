---
layout: post
title: "Mi aventura diseñando aplicaciones para smartphones"
date: 2014-05-05 20:26:19 +0200
category: diseño
---

Hace dos años aproximadamente leí que desarrollar aplicaciones para teléfonos móviles era más difícil que desarrollar una aplicación web. Recuerdo que sin leer el artículo un poco de risa sarcástica me había entrado. Cuando leí ese título pensé: ¿qué puede tener de difícil un entorno controlado? Esta persona no sabe lo que es hacer arreglos para Internet Explorer entonces. Lo que ocurría era que en realidad sólo estaba viendo la punta del iceberg. Lamentablemente perdí ese artículo y no logro dar con éste, pero el autor resumía que lo complicado de diseñar una aplicación nativa era un mix entre el uso del lenguaje y las posibilidades que ofrecía éste en comparación con lo que ofrece HTML/CSS junto con Javascript y el entorno mismo.

Luego de diseñar dos aplicaciones nativas quise compartir con ustedes mi visión del asunto que, por muy experimentado que fuere en web, fue más complicado de lo que imaginé. Las diferencias no se limitan sólo al lenguaje: diseñar una buena aplicación requiere, además de ver todo con una vista de águila, un conocimiento general y profundo de cómo funcionan los teléfonos y los patrones de uso que las personas adoptan, que son bien distintos a los que ocurren cuando estamos en un ordenador.

El otro punto es que si bien este artículo no ofrece siempre un ejemplo concreto de éxito tampoco es que lo haya para cada caso particular: ya que cada aplicación requiere, según los datos de uso y la validación que realice pos-pruebas, una solución distinta. Este artículo sí explica las razones por las cuales debe tener en cuenta tal tema u otro y que es lo que a mí, como profesional, me funciona y me lleva más o menos rápido al éxito. El éxito es un resultado de un cúmulo de condiciones y factores, y no como se suele creer que se debe a una particular razón. No hay nada específico que le vaya a asegurar 100% de éxito. Por más que copie Instagram, usted no tendrá el éxito que tuvo Instagram. Es así de simple.

**Este artículo es largo.** El tiempo de lectura medio de minid.net es de aproximadamente 10 minutos, pero el tema requiere explayarse a lo largo y ancho del asunto, por lo tanto, pido disculpas por la extensión. Si dispone de 30 minutos, podrá leerlo sin problemas. Recomiendo, igualmente, leerlo con detenimiento y paciencia.

## No es sólo software

La primera cosa que uno como diseñador web se encuentra al hacer la aplicación nativa para móvil es que uno **dispone de acceso al hardware del teléfono**. Y cuando digo acceso, digo *casi todo el hardware*, por lo tanto, se nos abre un gran abanico de posibilidades para hacer las cosas más amenas. Es tarea del diseñador aprender las posibilidades del teléfono y tomar las decisiones serias de diseño basadas en la información que el teléfono puede automatizar y proveer por el usuario.

Hace años, cuando la cosa estaba en pañales todavía, este tipo de acceso además de estar bastante restringido era también escaso. Hoy, en cambio, los teléfonos tienen cientos de funcionalidades a nivel de hardware. Acelerómetro, Giroscópio, GPS, brújula, sensor de proximidad, de luz ambiental, Magnetómetro, etc. También tienen suficiente potencia para realizar bastantes tareas computacionales y todo está preparado para ello. No hay una capa extra, como solemos hacer cuando diseñamos para un sitio web, donde todo es la capacidad del navegador o determinado *plugin* propietario. El teléfono lo tiene todo y lo ofrece bien documentado. Es importante descubrir qué y cómo mejorarlo.

Un ejemplo de esta categoría podrían ser cosas como preguntarle al usuario su localización de forma automática, si podemos acceder al GPS del teléfono, no necesitamos que esta persona lo rellene luego en un formulario a mano. Otro ejemplo es detectar señal baja de conexión e informarle al usuario que está desconectándose de la red. **Siempre es mejor aprovechar las bondades del teléfono.** Los usuarios disponen de *mucha* información útil ya guardada en el teléfono y accesible mediante API.

Como diseñador considero que las aplicaciones *excelentes* son aquellas que saben exprimir y aprovechar las bondades del *hardware* del teléfono en beneficio del usuario y de una forma que no sea obstructiva. Tanto el hardware como el software del teléfono están siempre al servicio del cliente. Ergo, es tarea del diseñador investigar en estos menesteres **tanto como pueda**, porque de esta forma podrá diseñar algo con efectivos resultados.

## Con o sin conexión

**Debe mentalizarse en diseñar su aplicación para situaciones donde hay (o no) conexión a internet.** Si su aplicación usa datos en servidores entonces este paso *es obligatorio*. Si su aplicación no depende de internet, entonces se ha salvado de tener que hacer esto también offline.

Cuando uno diseña un sitio web no se cuestiona qué ocurriría si alguien se queda sin conexión porque, su sentido común probablemente le dice que en contadas situaciones uno estaría con un ordenador portátil por ahí perdido fuera de cobertura, o bien mayoritariamente la gente usa ordenadores de escritorio para consumir su aplicación, desde sus casas u oficinas. Empero, en el mundo de la telefonía móvil, quedarse sin cobertura es muy habitual, por ende, su aplicación tiene que responder a estas situaciones a la perfección.

Pero la verdad es que diseñar tanto para el uso ordinario como el excepcional. *¿Qué ocurre si en este paso me quedo sin conexión?* Pues esa pregunta se la tiene que hacer en cada momento del flujo de diseño. Mi experiencia en esta parte fue horrorosa porque caí en la cuenta que sin estar bien preparado un usuario queda 100% inhabilitado en la aplicación. Aprendí que hay que informar en el momento que se produce esta desconexión.

La mejor forma es la de comprobar permanentemente la conexión y ofrecer al usuario esa información al instante mediante una notificación. No intente re-inventar la rueda con la notificación. Utilice los medios que le ofrece el framework del teléfono, son mejores y cubren todos los casos. Sí, por supuesto, puede optar por detalles dentro de su aplicación  siempre y cuando no se exceda demasiado en la personalización, como aclarar los botones y deshabilitarlos, poner en gris frases. También dar una explicación detallada al segundo o tercer intento. Guardar información si el usuario estaba completando un proceso o bien darle la posibilidad de terminar el paso luego. Todas estas pequeñeces hacen grandes favores a la experiencia de usuario en su aplicación. Aquellas aplicaciones que no informan adecuadamente, no reaccionan apropiadamente en momentos de desconexión sacan un menos en las calificaciones.

Una excelente aplicación permite al usuario saber que no tiene conexión a internet *in situ*. También le permite cancelar o terminar lo que está haciendo sin ningún tipo de problema y luego actualizar la información en los servidores y en muchos casos, una buena aplicación no necesita conexión a internet para funcionar. Un ejemplo de excelente aplicación que funciona offline es Instagram, por ejemplo. Hay que buscar todas las posibilidades para que el usuario pueda realizar lo que estaba haciendo. Una buena idea es guardar la máxima cantidad de datos en el teléfono y sincronizarlos cuando hay disponibilidad. Los usuarios saben que están utilizando datos en modo offline y que éstos quizás no estén 100% actualizados, por lo tanto, argumentar que lo válido es lo actualizado al instante no sirve porque anularía todo tipo de uso de la misma.

La diferencia entre una aplicación bien pensada y otra que no lo fue es bien simple. Miren el ejemplo de Telegram vs. Whatsapp: dos aplicaciones que son iguales, la diferencia es que sin conexión Whatsapp queda totalmente inhabilitada mientras que Telegram te deja escribir la cantidad de mensajes que quieras y, cuando la conexión regresa, éste se encarga de enviarlo todo automático.


## Organización

Este es un apartado importante. Toda aplicación debe tener un sistema adecuado para moverse con soltura entre la misma. Un sistema adecuado tiene una curva de aprendizaje mínima y pronunciada. Un sistema malo, una curva más larga y menos pronunciada. Es lo mismo que en un sitio web pero aquí hay una divergencia importante en comparación con la web per se. La única ventaja en los teléfonos es que los patrones de navegación *están bien definidos*. La desventaja: las compañías que dominan el mercado de sistemas operativos crean jardines cerrados. Cada jardín es distinto. El de Apple y el de Android puede que tengan cosas en común pero son bien distintos. Ambos habitantes de estos jardines están acostumbrados a unas cosas y otros, no. El problema empieza cuando quiera inventarse el suyo: nadie le entenderá de primeras porque todos los usuarios esperan ver un sistema similar. Tanto Apple, como Google alientan utilizar lo predefinido:

> Los usuarios están familiarizados con la apariencia y el comportamiento de los elementos de interfaz de usuario estándar, de manera que no tenga que detenerse y pensar en la forma de utilizarlos. Cuando se enfrentan con elementos que no se ven o se comportan en absoluto como los estándares, los usuarios pierden la ventaja de su experiencia previa.

Con la organización y la accesibilidad de las acciones, lo mismo: intente no salirse por la tangente. Uno puede optar con un patrón que parece *obvio*, pero que luego puede volverse monótono o incómodo. Contrario a lo que uno cree, tanto Google como Apple cercioran que los usuarios de teléfonos están muy bien acostumbrados y con muy poco uso descubren las formas de completar tareas, lo importante no es caer en extremos, sino, encontrar el gris de este asunto.

**No existe el usuario que mágicamente al abrir su aplicación sepa cómo usarla.** La famosa argumentación de «todos saben usar de primeras la app *acmeapp* porque es fácil» es una de las falacias más comunes que se utilizan para argumentar horribles decisiones de diseño o cambios que van en contra de los patrones universales. Nunca se compare con el usuario: corre el riesgo de perjudicar el diseño. Todos los usuarios dedican un poco de su tiempo a la exploración y ninguno muere por ello. Mire los patrones de uso en su sistema favorito, observe usuarios usar su aplicación: todos experimentan, todos intentan realizar más algún tipo de acción que otras. Lo bueno de las interfaces de usuario de teléfonos es eso: que permiten moverse de forma fluida, ir y venir sin tener que etiquetar todo el proceso. Un buen ejemplo de esto es la cámara del teléfono. Hay al menos 20 funciones en cada sistema, sin embargo no hay 10 millones de carteles indicando todo: solo iconos. El usuario puede tocar todo y aprender, porque al tocar recibe una cosa que se llama *feedback*. Esto, esto es lo que realmente le da valor y lo diferencia de las aplicaciones web, el feedback instantáneo de lo que está haciendo. No aburra a su público con interfaces llenas de palabreríos, carteles, indicadores, intente ser más sutil, deje que sus usuarios experimenten y recuerde: nada de lo que haga será cómodo para todos, siempre habrán cosas más convenientes para algunos usuarios y otras menos convenientes. Nunca podrá darle 100% de importancia a todas las acciones, algunas se sacrificarán por otras. Siempre será así, quiera o no reconocerlo.

Lo que aprendí luego de un corto tiempo y confirmándolo luego mirando charlas de ingenieros de Google y el propio uso de la aplicación es que **el contenido es lo más importante en una aplicación de teléfono** y las acciones tienen que estar bien definidas en torno a éste y no la forma de accederlo. Me explico: a primeras un hombre de negocio te puede decir que los puntos principales de acceso «no son obvios» y habría que ponerlo todo *a la vista*, pero la realidad es que una vez aprendido el esquema de navegación, toda la aplicación se vuelve inútil, aburrida, repetitiva y corremos riesgo de que los usuarios tengan tanta información inútil a la vista que quizás no necesiten *consumir*. Un ejemplo clásico:

<table>
  <thead>
    <tr>
      <th>✗ No haga esto</th>
      <th>✓ Mejor hacer esto</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>La pantalla inicial constará de un menú que muestre cada una de las categorías principales: el usuario hará clic y a partir de ahí usará nuestra app.</td>
      <td>La pantalla inicial constará de un resumen de cada categoría principal para que el usuario comience a consumir, sepa que hay en cada categoría e incluso se entere de nuevas actualizaciones.</td>
    </tr>
  </tbody>
</table>

Siguiendo la línea de ejemplos, otro clásico es la del consumo: no espere que los usuarios valoren todo. Cada usuario tiene sus intereses. Por lo tanto, si lo que usted busca es una intensiva actividad, haga que ésta se distribuya. Para ello, hay que hacer diseño centrado en acciones y que éstas siempre vengan en el momento indicado. Si tiene todo a la vista, el usuario deja de consumir porque ya lo ve todo, en cambio si usted le confiere cosas y le requiere participación, el usuario responderá a tal. Si tiene una galería de imágenes, no las ponga en grande, nadie entrará a ver la ficha de la foto, por poner un ejemplo. Intente no irse por los extremos, pero sepa seducir al usuario a entrar y explorar.

Otros de los puntos clave para llegar al desastre es la emulación. Mucha gente cree que emulando el sistema de navegación de iOS en una aplicación de Android es una buena idea y, como podrá comprobarlo luego: *no*, no lo es. **Es una pésima idea.** Ambos usuarios estarán acostumbrados a patrones distintos, aunque compartan algunos, **no todos los patrones son iguales de eficaces**. Tenga en cuenta que el usuario de iOS cuando se pasa a Android tiene que re-aprender todo y vice-versa. Hay muchas cosas que un usuario de Android no conoce de iOS y cuando usted, en su más humilde gesto de uniformidad diseña la app para que se vea igual en todos los dispositivos y sistemas en realidad lo que está haciendo es obligando a los nuevos usuarios a aprenderse nuevas formas. En iOS es común ejecutar acciones rápidas haciendo doble-tocar sobre algún ítem, en Android, no: es más común esperarse un tocar-mantener que un doble-tocar. A Vine, la red social de vídeos le costó un ojo de la cara haber publicado su versión de Android hecha a lo iOS: la mayoría de las calificaciones eran muy bajas y muchas referenciaban al «no se parece a Android». Durante un tiempo Facebook tuvo su aplicación de iOS portada a Android, lo cierto es que en Android esta aplicación era incómoda de usar: tuvieron que mudar la app al nuevo sistema con la coherencia básica de navegación de Android. La aplicación de Facebook se volvió un poco más útil y cómoda de usar.

Una buena aplicación premia la información fresca, lista para el consumo y no las pantallas repetitivas de siempre, obligando al usuario a tener que hacer las mismas acciones de siempre y a tener que masticarse una película de efectos especiales sólo porque los dueños quieran mostrar este tipo de efectos. Una buena aplicación, invita a abrirla porque ofrece contenido nuevo sin realizar esfuerzo, seduce al usuario con sugerencias. Da a éste razones para volver a menudo sin caer en el famoso *síndrome del control remoto*.

## Velocidad

La velocidad es otra de las cosas que me quitó varias noches de sueño. Sí, puede que haya algo de cierto de que estamos mal acostumbrados a tener que esperar, pero es que hay muchas aplicaciones que no lo hacen. *¿cómo lo hacen?* Pues hacen varias cosas. Una de las cosas son lo que yo denomino como *hacks perceptivos*, que son modificaciones que engañan al usuario. Los otras son los *hacks programáticos*, que son aquellos que matemáticamente permiten ir a la aplicación más rápido gracias a la refactorización de código.

Los *hacks perceptivos* son bien fáciles de identificar. Por ejemplo: evite el uso mensajes de carga. Muchas veces anteponemos mensajes de carga para situaciones en donde no hace tanto falta. Aunque usted cree que le hace un favor al usuario, en realidad, no se lo está haciendo. Sutilmente le está diciendo «somos lentos». Si usted carga una foto desde un servidor y ésta, por lo general, tarda menos de un segundo, no ponga un «cargando». Lo que logra con estos mensajes es crear distracción y sensación de lentitud. Sus usuarios verán este mensaje siempre. Utilice estos mensajes cuando realmente la acción lleve un tiempo considerable, por ejemplo, cuando esa misma foto lleva ya más de 3 o 4 segundos cargando. Ese mensaje dará a entender al usuario que por esa vez su aplicación no está yendo de forma óptima o simplemente quedará claro que quizás su problema es de conexión.

Investigando los famosos *hacks perceptivos* encontré uno particularmente atrevido en la aplicación de iOS de Pinterest. Hace una cosa interesante: cuando uno navega listados, ve la imagen pequeña, cuando hace tocar sobre la imagen, se carga la ficha, a tamaño completo, pero es la misma imagen. Por uno o dos escasos segundos (en conexión 3G), previsualizamos la misma imagen pequeña pero re-escalada al tamaño final. Lo bueno es que se nota apenas y en esos instantes la imagen grande aparece, tapando la antigua con menos resolución. Es como si estuviésemos  cargando un JPG progresivo. **Considero que ésta ha sido una decisión acertada**.

Para alcanzar la *instantaneidad* la aplicación tiene que guardar todos los datos nuevos que sean posibles y mantener los antiguos por si las dudas. Esto debe realizarse de la forma más ofuscada disponible: de esta manera el usuario *no ve ningún mensaje* de carga.

Si solo desea sincronizar a voluntad de uso, lo que tiene que hacer es analizar los puntos calientes de la aplicación y anticiparse a lo que el usuario pueda querer. Por ejemplo: si el usuario está en su galería de fotos, tenga ya las últimas fotos cargadas en máxima resolución: con mucha probabilidad el usuario querrá verlas. Las antiguas ya las tiene. Deseche las muy antiguas, las menos visitadas. Y así con todas las cosas. Anticiparse es una buena forma ganar tiempo, tiempo que el usuario no está interrumpido. Los usuarios suelen vivir interrumpidos en un teléfono: mensajes, fotos, notificaciones. Cualquier excusa es suficiente para salir de lo que estaba haciendo. La velocidad ayuda a que consuman más.

Analice realmente todo lo que sus usuarios consumen y guárdelo todo. Eso, como regla general. Revise bien todos los activos que necesite en pantalla y sirva el activo adecuado para cada situación: no utilice el incorrecto, hará que la experiencia de sus usuarios sea lenta y consuman datos de más. Por ejemplo, si usted tiene un *timeline* de toda la vida, y ahí muestra ítems con imágenes de 50x50, sirva la versión retina de 100x100 y no una mayor. Divida las mismas imágenes en diferentes tamaños y aproveche los diferentes pesos a su favor: el usuario navegará su aplicación más rápido. *¿El usuario se detiene en una zona?* Reaccione: descargue en paralelo los recursos que posiblemente verá el usuario. Se sorprenderá la cantidad de veces que puede acertarlo.

Recuerde otra cosa: la estadía de los usuarios es relativa con el estilo de su aplicación. En el mundo *mobile* hay dos tipos de aplicaciones: las de *utilidad* y las de *entretenimiento*. En el primer grupo, los usuarios tienden a generar estadías más cortas y fugaces. Entran, miran, salen. En el segundo grupo, los usuarios están más propensos a gastar tiempo. En el primer grupo las UIs son por lo general más directas, sin florituras, mientras que en el segundo grupo las aplicaciones tienen a ser más efectistas. Lo importante es tener en claro algo: más tiempo de estadía por usuario no indica *valor*. Primero analice qué tipo de aplicación usted hace, luego reflexione el tiempo que le hace usted pasar a sus usuarios. Verá que con menos tiempo pero más efectividad de servicio el valor de su aplicación es mejor que otro que entretiene a su usuario más valioso con efectos inútiles.

Una excelente aplicación consume la cantidad mínima de datos posible y además sincroniza los datos de forma permanente e inteligente. Se anticipa correctamente a las preferencias de los usuarios, generando pocos cuellos de botella. Las aplicaciones bien fluidas ganan a aquellas que no lo son, **esto es ley**.

## Errores

Monitorizar la aplicación en busca de errores y para analizar cómo consumen tu diseño es bueno tanto para el usuario como para los desarrolladores. Los usuarios se beneficiarán de forma indirecta: al ver los cambios de diseño, solución de errores, aumento de velocidad y otras cosas. Los desarrolladores se beneficiarán con la posibilidad de *saber* y la posibilidad de *reaccionar* a tiempo.

Aunque esto parezca obvio, nunca lo ha sido. Al menos, y sin engañarle, tampoco en mis comienzos tuve idea de la magnitud de importancia de este asunto. Cuando hablo con otros desarrolladores suelo notar que no ponen mucho énfasis en medir.  La sensación que me queda es que utilizan las opciones más básicas o bien si disponen de las herramientas más potente aunque no las explotan en su totalidad. Mucha gente me dice: «Sí, tenemos el reporte de la app, creo que es suficiente», pero mi experiencia me ha dicho todo lo contrario: no fue suficiente.

Para realmente hacer un buen diseño, más que una persona con solo buena experiencia diseñando hace falta una persona que **sepa como reaccionar ante datos reales de consumo y los patrones de errores** y no ante suposiciones. Una persona que *no* diseña pensando en medir, es una persona inconsciente
y que con seguridad se encontrará con una hilera importante de problemas. Muchos de éstos nunca tendrán visibilidad y harán que la aplicación *pierda agua por todos los lados*. Una persona que diseña para medir es una persona que sabe que tiene que **validar cada funcionalidad** hasta el punto que no sepa cómo mejorarla más, pero siempre, desde la perspectiva de los datos. Si usted cree que era sólo diseñarla, programarla y lanzarla, está equivocado. Se dará cuenta que además del mantenimiento hay que vigilar todo, como si se tratara de un niño pequeño que requiere supervisión constante. Una aplicación nativa funciona de la misma forma.

Investigue todas las herramientas de monitorización que haya en el mercado. Yo utilizo [Flurry][flurry], aunque existe la posibilidad de integrar [Google Analytics][analytics] en su proyecto sin problemas, tanto en Android como en iOS. Valore los mejores y comience a implementarlo.

*¿Y qué debo monitorizar?* Absolutamente todo. Al principio pensaba que sólo necesitaba saber las áreas de interés de la aplicación: tipo, la cantidad de accesos a secciones, qué elección de registro realizaban, etc. Pero luego esto se transformó en una especie de dato sin sentido y poco riguroso, dado que no tenemos realmente datos extras que corroboren dichos números. Ahí empezamos a capturar todo tipo de dato que nos permitieron saber, cruzar y analizar con un buen grado de profundidad qué hace un usuario, donde intenta *tocar* para realizar acciones o porqué algunos usuarios dejan de realizar la tarea que realizaban. Esto es información valiosa que permite tomar decisiones más sensatas sin tener que entrar en las típicas discusiones del *sexo de los ángeles*.

Sea imaginativo: es posible que descubra usos que sus usuarios desean o quieren. En [Notegraphy][note] cuando realizamos una nueva funcionalidad ponemos los *puntos calientes* para analizar todo de esta forma, en vez de discutir si esto va o no, simplemente lo medimos en muy pocos días de actividad. Así supe que realmente los usuarios esperan previsualizar la nota antes de darle al botón de enviar, incluso si ya la habían diseñado. Esta funcionalidad «imprevista» saldrá dentro de poco. Muchos usuarios nuevos y antiguos podrán disfrutarla. La calidad de la aplicación mejora.

Los grandes proyectos que he conocido están totalmente supervisados. Saben con exactitud muchas cosas: desde errores hasta los patrones más insólitos de uso. **Esto le permitirá validar cualquier hipótesis y virar en su estrategia en todo momento.**

## Texto

> Cada palabra que muestre en una aplicación es parte de una conversación que usted tiene con los usuarios. Utilice esta conversación como una oportunidad para proporcionar claridad y para ayudar a que la gente se sienta cómoda en su aplicación.

Hay, en materia de diseño web y móvil, incontables estudios y recomendaciones en internet sobre como escribir en una aplicación. Mi experiencia diseñando me ha mostrado muchos errores evitables y muchas cosas que parecían sensatas al principio pero que luego demuestran ser un total incordio. En numerosas pruebas con usuarios que utilizaron Notegraphy he podido constatar que las situaciones donde habían textos largos eran ignoradas casi de forma instintiva e incluso, hasta dos o tres veces seguidas. El tour de la aplicación, incluso siendo resumido, es ignorado en muchas situaciones porque la imagen que lo acompaña tiene mejor ganancia. Las razones siempre dan vuelta sobre el mismo tema: tiempo. Sí, leer dos líneas es perder el tiempo. Es por eso que muchos desarrolladores, [incluido Google][write] y [Apple][writeios] recomiendan escribir textos de forma *concisa, simple y amigable*.

El lenguaje debe ser conciso: debe describir **sólo lo que el usuario necesita saber**. Toda redundancia debe *ser eliminada* como lo son títulos que repiten lo mismo que el cuerpo del mensaje, etc.

<table>
  <thead>
    <tr>
      <th>✗ No haga esto</th>
      <th>✓ Mejor hacer esto</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Eliminar archivos</strong><br>Al aceptar esta acción se eliminarán cada uno de los archivos que has seleccionado.</td>
      <td>Se eliminarán los archivos seleccionados.</td>
    </tr>
  </tbody>
</table>

Quitando la redundancia mejoramos notablemente el texto. El título tiene mejor ganancia de atención que el resto del texto. Simple y llano: el usuario sólo lee el título y sigue de largo hacia las acciones. Tanto como en páginas web, la expresión lacónica funciona mejor que la novelesca. El segundo ejemplo en cambio cumple la función del título y descripción a la vez, el usuario sí o sí tiene que leerlo.

Utilice palabras cortas, verbos activos y sustantivos que comúnmente se usan. Siempre ponga la información vital al principio de la frase, nunca al final. Es la única manera de mantener una coherencia en cada mensaje sin que el usuario se pierda en tecnicismos cuando en realidad tiene que entender los beneficios.

<table>
  <thead>
    <tr>
      <th>✗ No haga esto</th>
      <th>✓ Mejor hacer esto</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>30 personas les ha gustado esto, incluyendo a Bill Gates.</td>
      <td>Bill Gates y otras 30 personas les ha gustado esto.</td>
    </tr>
  </tbody>
</table>

Otra de las recurrentes recomendaciones que podemos encontrar es la utilización de lenguaje amigable sin entrar en el uso de argot y jergas de cualquier tipo. Recuerde que incluso limitando el uso a un país, no todo el mundo está a la última moda linguística. La jerga y el argot puede funcionar sólo para un determinado estrato de personas pero no para todas e incluso hasta puede que produzca el efecto contrario: falsa modestia o amistad. No hace falta tratar de usted, los grandes recomiendan el uso de «tú» cuando se refiera al lector.

Siguiendo el tono de temas por tener en cuenta sobre texto y escritura es: traducción. Nuestra primera intención de lanzamiento con Notegraphy era hacerlo en inglés: un lenguaje casi universal y lo mejor para probar el terreno. Cualquier persona con acceso a tecnología sabe de alguna forma u otra inglés: equivocado. Apple se puso en contacto con nosotros. Estaban alegres y entusiasmados con nuestra aplicación, querían destacar Notegraphy en el App Store y todo. El equipo estaba flotando entre nubes de alegría y reconocimiento con semejante piropo de Apple. Pero la alegría estaba muy lejos todavía: Apple nos recomendó cambios, para que realmente la aplicación estuviese a la altura de lo que ellos consideran «una buena app», o sea, algunas modificaciones de ingreso, uso de su framework pero lo más destacado de todo era la traducción en al menos 5 lenguas: español, francés, alemán, italiano y portugués. Sin esto, Apple no iba a destacar nuestra aplicación. Sabiendo esto nos pusimos manos a la obra y tradujimos la app en todos los idiomas e incluso en catalán.

Con el tiempo y el lanzamiento de Android, me di cuenta aplicando las recomendaciones, en la versión de Android contamos con aproximadamente unas 900 palabras, mientras que en la de iOS, sin haber aplicado correctamente todo, al menos, *nos pasamos tres pueblos*. Y la diferencia se nota. No sólo en precio, sino, en lectura. El interfaz de una aplicación de teléfono no es una página web. Hay que tener en cuenta que tiene que estar todo **diseñado de modo que quepa todo el contenido**. En alemán, ruso y otros idiomas, las cadenas de texto son larguísimas, hay que tener especial don para traducir correctamente porque todo crece. Sólo para que se haga una idea, la palabra *notifications* (notificaciones) en alemán se escribe *benachrichtigungen* o el término *publish* (publicar) en alemán quedaría *veröffentlichen*.


Mi recomendación para una buena aplicación es esa: bien escrita, sin demasiada prosa ni amiguismo y traducida en la máxima cantidad de idiomas. Mida los resultados luego de aplicar estos cambios, tengo la seguridad de que mejorará cualquier índice.


## Detalles

No me quería olvidar el área de detalles. Es igual de importante y le da ese *extra* a su aplicación. Lo que la diferenciará del resto. Esta zona es la más subjetiva. Realmente, luego de analizar cientos de casos en mi carrera, no hay una fórmula secreta para hacer un diseño exitoso en materia de detalles, les estaría mintiendo si les dijera que usando este u otro efecto efecto específico lo tendréis asegurado el éxito, porque la verdad es que sin meter efectos y detalles se puede tener éxito. Lo prueban cientos de casos: Whatsapp (16 millardos de valoración), Snapchat (3,5 millardos), Instagram (1 millardo) y así unos cuántos más. Muchos tienen un diseño más bien *espartano*. Carecen de iconografía personalizada, tipografías hechas por selectos diseñadores y lo más buscado: efectos especiales.

En el mundo donde los marketineros, social media experts, gurús de internet y diseñadores se tocan las partes bajas cada vez que ven efectos especiales en una aplicación, es fácil caer en lo disgustante, repetitivo, abusivo y redundante. Es como ver una película varias veces pero interpretada por diferentes actores. Diría que ganan aquellos que saben aplicar efectos en el momento indicado y con ese toque sutil que pocas aplicaciones lo demuestran. Es importante tener esto en cuenta porque aunque los teléfonos tengan un pedazo de procesador gráfico para mover lo que quieran en pantalla, es denigrante tener que aguantar la misma película cada vez que realizamos una acción. El usuario promedio no aprecia estos detalles de diseño, sólo los usuarios experimentados y la prensa son los principales consumidores. El usuario promedio no entiende, ni sabe de diseño, en cambio un periodista de tecnología valorará su aplicación por este tipo de acabados. Le recomiendo, y claro, bajo validación posterior de su público, que utilice los efectos especiales más sutiles que existan. Recuerde el género de aplicación al que se dedique: si es de utilidad, intente no pasarse de efectista. Si en cambio es de entretenimiento, piense en romper esquemas. Las estadísticas y las posteriores encuestas le dirán si se pasa o no de la raya.

Los efectos especiales, ya sean en aplicaciones de teléfono o web, **son formas de avisar al usuario que algo ocurre con un alto grado de efectividad**. Podemos ahorrarnos el favor de hacerlas, pero el uso de la aplicación se volvería demasiado inalterable y en pruebas de usuario he podido verificar que muchos ni siquiera notan un cambio instantáneo en pantalla. Qué objeto ha cambiado, cuando se produce un cambio en un listado, y se hace más evidente el problema cuando la aplicación es viva en actualizaciones. Intente animar cada evento, no más de 300ms y notará que la aplicación se vuelve amena, sobre todo para que su usuarios tengan tiempo de *escanear* y luego leer la información en pantalla.

## Pruebas

El último dolor de cabeza del diseño de aplicaciones móviles: la realización de pruebas. Si usted cree que con las herramientas que provee Apple o Google está cubierto: está equivocado. Mi experiencia sobre este menester me ha dado unos cuántos disgutos y quitado varios días de sueño. He consultado con muchos profesionales del sector y todos concluyen en la gran mayoría de recomendaciones: realizar pruebas unitarias y luego pruebas de integración. El teléfono es un nuevo medio y como tal, hay más variables en juego.

Pero incluso con ambas prácticas, no ha sido suficiente para encontrar errores de clase fatal. Llevo 18 años de experiencia trabajando en sistemas de todo tipo y es imposible hacer algo 100% libre de errores, pero si hacerlo en web se siente más controlado, espere en un teléfono: es un nuevo mundo. Como lo matemático no es suficiente, hay que probar a mano todo, incluso, de las formas más estúpidas y repetitivas.

Al principio, en Notegraphy, lo hacíamos todo sin un sistema práctico. Con el tiempo empezamos a notar la cantidad de errores que salían a la luz. De los más insólitos. El problema empieza porque es difícil tener reportes concretos de errores en aplicaciones que ya están en el App Store. No es el caso de Google, que genera reportes y uno puede ponerse en contacto con la gente. Con toda esta dificultad, no supimos sino, hasta pasado un buen tiempo que tuvimos un error que bloqueaba la aplicación a todo aquel que tuviese su iPhone configurado con idioma inglés pero de Inglaterra. Inédito. Así, decenas de errores que hacían la idea de tener una aplicación libre de estos incordios una utopía.

Mi recomendación aquí es probar. Probar, probar hasta que se aburra. Nunca está de menos probar la aplicación con otro idioma configurado en el teléfono, ni tampoco está demás cortar internet en medio de un proceso, ni hacer *tap* repetitivamente, ni cargar cada vez más rápido ítems, todo fomenta a que salgan los problemas. Con el tiempo, y la recopilación de los errores comunes, **elabore una batería de pruebas**. Una batería seria, que se pueda seguir, al mejor estilo [*The Checklist Manifesto*][checklist], por ejemplo, donde usted y su equipo de desarollo puedan probar todo.

Nunca estará a salvo de errores. Pero no es lo mismo convivir con decenas de errores fatales a, tener unos concretos cada muerte de obispo. Si bien es cierto que las metodologías de desarrollo basado en pruebas evitan sorpresas, es en la prueba del algodón donde salen a relucir los verdaderos incordios. Además, lo malo del asunto y lo paradójico es que el proceso para enmendar esto es sin dudas peor: 5 días de espera o 3, con suerte, para el caso de aquellos que usen Apple.

Esto aquí no se acaba. Queda todavía temas para publicar sobre el diseño y la producción de aplicaciones para móbiles. Lo expuesto aquí, sirva de ejemplo para cualquiera que esté en proceso de desarollo. Recuerde: no existen las fórmulas mágicas, lo que que existe es seguir un método científico, de modo que usted, pueda hacer su producto más interesante para su público.


[note]: http://www.notegraphy.com "Notegraphy"
[flurry]: http://www.flurry.com/ "Flurry"
[analytics]: http://www.google.com/analytics "Google Analytics"
[write]: http://developer.android.com/intl/es/design/style/writing.html "Writing Style | Android Developers"
[writeios]: https://developer.apple.com/library/ios/documentation/userexperience/conceptual/MobileHIG/FeedbackCommunication.html#//apple_ref/doc/uid/TP40006556-CH56-SW1 "iOS Human Interface Guidelines: Terminology and Wording"
[checklist]: /2014/04/28/the-checklist-manifesto/ "The Checklist Manifesto: How to Get Things Right – Minid.net"
