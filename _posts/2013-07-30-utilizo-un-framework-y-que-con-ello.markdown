---
date: 2013-07-30 00:00:01
layout: post
slug: utilizo-un-framework-y-que-con-ello
title: Utilizo un framework ¿y qué con ello?
category: desarrollo
---



> La discusión de siempre: usar o no un framework en HTML/CSS para hacer un sitio web. En cada reunión que voy siempre veo el mismo panorama: una persona dice *Bootstrap* y el otro pone una cara muy similar a la que pone el presidente Mariano Rajoy como cuando le preguntan sobre Bárcenas. Es como una especie de tabú hablar de frameworks con algunos camaradas de profesión. Mencionarlo en público puede que hasta incluso te marquen como el mediocre. ¿Pero en qué planeta vivimos?

Lo cierto es que hace años tuve un encontronazo de este tipo y además de haber sido desagradable fue sin dudas uno de los errores más grandes que hice en mi vida profesional y fue algo así: hace como 5 años, en una cena con desarrolladores web de Barcelona pregunté a un par de prominentes programadores frontend si les apetecía participar de un proyecto de hacer un «framework» de HTML y CSS, algo básico, que tuviera todo lo necesario para empezar un proyecto, que fuera una especie de *reset* de la época pero para ambos lenguajes. Y la reacción de estos dos sujetos (que no pienso nombrar) no me la olvido jamás: la primera fue una mirada incrédula entre los solicitados. Se miraron sin hablarse, pero como si se hubieran dicho lo mismo: *¿Está hablando en serio?* La siguiente respuesta de uno de los solicitados me dejó helado: «no vale la pena y, es de mediocres, yo no necesito ayuda de nada para programar un sitio». Sus argumentos siguieron por la línea, al igual que su amante, yendo siempre por el lado de los que se lo saben todo, de los que son a prueba de todo y de quienes creen que, hacerlo todo *per aspera ad astra* es la mejor forma. Tanto ensañamiento y cuestionamiento a estos supuestos pensamientos impíos me hizo reflexionar y, claro, como quien normalmente no se cree un talibán en cada tema e intenta ver si realmente uno está diciendo sandeces o no dejé pasar la idea. Otros en cambio se pusieron a ello ya ahora han nacido bellos proyectos para desarrollo que más de un desarrollador de prestigio usa.

Hoy puedo decir que nunca estuve tan equivocado. Y es una de las pocas veces que como persona que me apesadumbra el haber dejado pasar la oportunidad y haber hecho algo interesante. Igualmente al poco tiempo me redimí haciendo mi primer framework de desarrollo web en iPhone. Llegué tranquilamente a las 100 mil descargas entre mi blog y la base de código de Google. Aunque la base de código ya esté pasada de moda y anticuada, muchas de las actuales han partido de mi framework y quizás muchas de las ideas que hice ahora son parte de otros frameworks. Nada me puede poner más contento.

Lo cierto es que no soy el único. Gente incluso más importante también se encontró en mi posición y luego se dieron cuenta: fuimos tontos que perdíamos el tiempo y por cuestiones de orgullo no vimos el beneficio. [Andy Clark][andy], autor de unos cuantos libros de desarrollo web, tuvo el mismo dilema hace unos años: [dijo por Twitter][andytweet] (empezando por la odiosa y soberbia frase *"Pro tip"*) que si su CSS era suficientemente complicado para depender de [SASS][sass] o [LESS][less] era que estaba haciendo mal las cosas. Andy se había equivocado y se lo dijeron, pero aún así su pasajero orgullo hizo que no entendiera, hasta que en uno de esos momentos lúcidos probó SASS y se dio cuenta que, como a veces digo: [la conveniencia reemplaza a la nostalgia][fin]. Andy Clark luego rectificó diciendo que estaba realmente equivocado y [que lo sentía mucho][blogpost].

> Es el orgullo, la ignorancia y no un framework el que te hace perder el tiempo.

Usar frameworks es sin dudas **una de las mejores decisiones que puede tomar cada desarrollador web** en donde ya entiende cómo funciona HTML y CSS u cualquier otro tema. Y si me apuran, incluso de quien ya entra en el reino del desarrollo avanzado. El tiempo es valioso y no se trata de conocimiento u orgullo, sino, **de no repetir o cometer los mismos errores una y otra vez**, cada vez que quiera hacer algo nuevo. Además, es una de las mejores formas de conocer código bien programado. Pocas veces usted verá o hará algo solo de la calidad de código de Foundation o de Bootstrap mismo.

## Cómo lo ven los programadores

Los programadores no tienen problemas en utilizar frameworks y más sabiendo que éstos están actualizados y mantenidos por una comunidad o algún programador estrella. ¿Por qué habría usted de tenerlos? El ejemplo de Ruby y Ruby on Rails es característico y prueba que, nunca se pierde el tiempo usando un framework, al contrario, se gana mucho más de lo que se cree.

Puede hacer una web con el lenguaje Ruby desde cero, pero es mejor usar el framework Rails porque además de estar desarrollado por una comunidad gigante, es una base sólida para no perder tiempo haciendo algo que ya está hecho por muchos desarrolladores y mejor, sin herir sentimientos. *Siempre es mejor aquello que ha sido mirado por más ojos que el de uno.*

En la comunidad de programadores y hackers no tienen problema de tirar de librerías, frameworks o parches. Cualquier cosa en beneficio propio de la comunidad es bueno. No hay leprosos en estos círculos, ¿por qué le molesta a usted usar frameworks? Como ve, es algo realmente carente de sentido.

> Yo con * { padding: 0; margin: 0; } ya cubro todos mis problemas.

En realidad y, técnicamente hablando, no. Usted no cubre todos sus problemas. Tiene muchos, sólo que no es consciente de ellos. Es uno de los argumentos más pobres que uno puede escuchar en tweets, charlas de café y en la empresa: que con dos reglas uno ya está a salvo de todos los problemas y que, curiosamente, no es cierto: sin un normalizados de CSS usted está en problemas, trabaja de más y tiene más líneas de código del que debería.

Los normalizadores de CSS son otros, de los famosos frameworks que se utilizan día a día en todos los proyectos de Internet. Yahoo! usa y provee uno, Twitter también y hasta Google lo tiene. La razón es simple: **cada navegador hace e hizo de su culo un cabaret distinto** por lo tanto los desarrolladores en pos de obtener equilibrio han optado por hacer normalizadores que básicamente son reglas de CSS que destruyen las reglas por defecto impuestas por los navegadores.

El tema está que, no sólo es un tema de márgenes y rellenos, va más allá: son temas de interlineados, cualidades de elementos y bugs. Por eso, si usted tiene una regla universal como la citada simplemente está solucionando (y muy mal, por cierto) uno, de los 20 0 30 más comunes problemas del desarrollo web del 2013, y ni hablar de los más antiguos.

Si usted sólo tiene esa regla, por ejemplo, no está cubriendo los casos de HTML5 en donde si desea mostrar un elemento `AUDIO`, `CANVAS` y `VIDEO` éste venga sin los problemas de IE8/9 corregidos porque no está definida la propiedad `inline-block` de los mismos.

Así, como ve, es con todo.

Existen miles de cosas que joden al desarrollador y, sólo párese a escuchar uno de los cientos dilemas que todos los desarrolladores formulan en foros, listas de correo para darse cuenta que buscando en Google encuentra la solución. **Una solución que deberá copiar y pegar en su código**, donde probablemente tenga que elegir el mejor lugar dentro de su maraña de código donde ponerla y no afecte mal al código que tiene: en fin, *que perderá tiempo implementando parches para que su sitio se visualice bien en determinado navegador*. Cada error le llevará tiempo. Es por eso que los frameworks son buenos: **cubren el 99% de los problemas conocidos y evitan que usted pierda tiempo en cada proyecto** corrigiendo los errores.

Si usted no opta por esta vía y cree que su sitio web va genial con solo unas pocas reglas de CSS, está equivocado: seguramente tiene más de 10 problemas comunes que afectan la visualización, carga de su sitio en los diferentes navegadores. Y no hablemos de móviles, ni *Responsive Web Design*.

## Iníciese ahora

[Bootstrap][bt] es, junto con [Foundation][zurb] de Zurb, uno de los frameworks más utilizados del planeta. Si uno [mira el historial de GitHub][btgithub] puede corroborar que hay trabajo detrás (¡5271 <em>commits</em>!) y siendo un poco consiente, puede uno darse cuenta que el trabajo de muchos es mejor que el que puede hacer uno en un año de trabajo para un cliente. Bootstrap al igual que Foundation y otros, es la mejor base para hacer no uno sino, todos los sitios que uno desea. El requisito: saber CSS/HTML y tener en claro cómo está hecho el framework.

Uno puede chistar que le faltará algo o bien que algo no le cuadra pero eso es lo bueno de estos frameworks: son extensibles. Puede uno optar por no usar el sistema de grillas de Bootstrap pero sí el de Fulanito 1.0. Bootstrap está hecho de modo que sólo necesitas compilar lo que quieras usar y, de no estar satisfecho con Fulanito 1.0, borras el CSS de la grilla y cargas el propio. Y así con todo. Simplemente se ahorra el tiempo y cualquiera podrá tomar el testigo de su trabajo sin problemas porque existe documentación y hay una línea de trabajo definida sumada a la propia que será más legible que una enteramente suya.

Existe sólo un caso en donde no recomiendo usar frameworks: cuando uno no sabe suficiente de HTML/CSS/JS. **Usar frameworks puede ser nocivo para aquellas personas que tienen un muy bajo nivel de conocimiento.** Los frameworks le permiten, básicamente, construir muchas cosas sin tener que programarlas pero hasta cierto punto. Pero también esta comodidad puede hacer que no aprenda nada y se estanque en el estilo por defecto que trae el framework en concreto haciéndole más mal que bien. El día que ese framework deje de ser actualizado usted está jodido. Aún así, quienes empiecen mirando código bien hecho quizás puedan aprender las mejores técnicas para construir determinadas cosas. Aunque parecerá chino al principio, con el tiempo puede traducirse a un español más legible. Cada uno aprende a la velocidad que le es posible. Si estás haciendo un sitio web sin LESS o SASS y sin un framework es casi seguro que estás haciendo un sobre-esfuerzo innecesario, sin contar que estás bajo una lluvia de bugs por solucionar y quizás, el que venga luego a tocar tu código diga la típica frase de siempre:

> «Este código está hecho una mierda. Hay que hacerlo todo desde cero»

[bt]: http://twitter.github.io/bootstrap/ "Bootstrap"
[btgithub]: https://github.com/twbs/bootstrap "twbs/bootstrap · GitHub"
[zurb]: http://foundation.zurb.com "Foundation: The Most Advanced Responsive Front-end Framework from ZURB"
[sass]: http://sass-lang.com "Sass - Syntactically Awesome Stylesheets"
[less]: http://lesscss.org "LESS « The Dynamic Stylesheet language"
[andy]: http://stuffandnonsense.co.uk "Fashionably flexible website design by Stuff & Nonsense"
[andytweet]: https://twitter.com/Malarkey/status/6435096054 "Twitter / Malarkey: Pro tip – If your CSS…"
[blogpost]: http://www.stuffandnonsense.co.uk/blog/about/less "LESS"
[fin]: /2013/02/07/el-inevitable-fin-de-los-libros-en-papel/ "El inevitable fin de los libros en papel – Minid.net"
