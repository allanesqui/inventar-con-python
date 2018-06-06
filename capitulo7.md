# 7 Diseñando el juego ahorcado con diagrama de flujo
![Imagen de ciencia](https://inventwithpython.com/invent4thed/images/00016.jpeg)

En este capitulo usted va a diseña el guego Ahoracado. Este juego es más complicado que los juegos anteriores, pero también es más divertido. Porque este juego es avanzado, primero, vamos a planearlo creando un diagrama de flujo en este capítulo. En el capítulo 8, nosotros realmente vamos a escribir el código para el juego Ahorcado.
***
* Arte ASCII
* Diseñando programas con diagrama de flujo
***
## Cómo jugar Ahorcado
Ahorcado es un juego para dos personas en el que un jugador piensa en una palabra y después dibuja en una página una línea por cada letra de la palabra. El otro jugador debe intentar adivinar las lteras que pueden estar en la palabra.
Si el segundo jugador adivina la letra correctamente, el primer jugador escribe la letra en el espacio en blanco de la letra. Pero si el segundo jugador se equivoca en la letra, entonces el primer jugador dibuja una parte del cuerpo de una persona ahorcada. El segundo jugador tiene que adivinar todas las letras en la palabra ante de que la persona ahorcada sea dibujada completamente para ganar el juego.
## Ejemplo de ejecutar Hangman
Aqui hay un ejemplo de cómo el jugador podría ver cuando ellos ejecutan el programa de Ahorcado , programa que vamos a escribir en el capítulo 8. El texto que el jugador ingresa está en negrita.
***

A H O R C A D 0 

   +---+
      |
      |
      |
     ===
     
Letra falladas:
_ _ _
Adivine la letra.
a
  +---+
      |
      |
      |
     ===
Letra falladas:
_ a _
Adivine la letra.
*o*
  +---+
  O   |
      |
      |
     ===
Letra falladas: o
_ a _
Adivine la letra.
*r*
  +---+
  O   |
  |   |
      |
     ===
Letra falladas: or
_ a _
Adivine la letra.
*t*
  +---+
  O   |
  |   |
      |
     ===
Letra falladas: or
_ a t
Adivine la letra.
*a*
Usted ya intentó con esa letra. Intente nuevamente.
Adivine la letra.
*c*
¡Sí! ¡La palabra secreta es "cat"(gato)! ¡Usted ha ganado!
¿Le gustaría jugar nuevamente (sí o no)?
no

***

## Arte ASCII

Los graficos para Ahorcado son teclas del teclado escritas en la pantalla. Este tipo de gráficos son llamados Arte ASCII (pronunciado ask-ee), el cual es un tipo de precursor del emoji. Acá está un gato dibujado en arte ASCII:
![Imagen de un gato dibujado en ASCII](https://inventwithpython.com/invent4thed/images/00080.jpeg)

Los dibujos para el juego de Ahorcado se verán así en arte ASCII:
***
 +---+    +---+    +---+    +---+    +---+    +---+    +---+
 
      |    O   |    O   |    O   |    O   |    O   |    O   |
      |        |    |   |   /|   |   /|\  |   /|\  |   /|\  |
      |        |        |        |        |   /    |   / \  |
     ===      ===      ===      ===      ===      ===      ===
***

## Diseñando un programa con un diagrama de flujo
Este juego es un poco más complicado que los otros que hemos visto hasta el momento. Tomemos un momento para pensar cómo poner todo junto. Primero usted va a crear un diagrama de flujo (como el que está en la Figura 5-1 en la página 47 para el juego del Dragón) para ayudar a visualizar que hará este programa.
Como discutimos en el Capítulo 5, un diagrama de flujo es un diagrama que muestra una serie de pasos como cajas conectadas con flechas. Cada caja representa un paso, y cada flecha muestra los posibles pasos. Ponga su dedo en la caja de Inicio (Start) del diagrama de flujo y siga el flujo del programa siguiendo las flechas de las las caja hasta que llegue a la caja de Final (End). Usted puede solo moverse de una caja a la otra en una dirección de la fecha. Usted nunca puede ir hacia atrás, a menos que haya una flecha en dirección hacia atrás, como en la caja del "Player already guessed this letter". 

Figura 7-1 es un diagrama de flujo para Ahorcado

![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00081.jpeg)

Claro, usted no tiene que hacer un diagrama de flujo; usted podría solo empezar a escribir código. Pero, muy a menudo, una vez que inicie a programar, usted pensará e las cosas que deben ser agregadas o cambiadas. Usted podría terminar eliminando un montón de su código, lo cual podria ser una pérdida completa de esfuezo. Para evitar esto, es mejor planear cómo el programa va a funcionar antes de empezar escribirlo.

## Creando un Diagrama de flujo
Su diagrama de flujo no necestia verse con el que está en la figura 7-1. Siempre y cuando usted entienda el diagrama de flujo, será muy útil cuando empiece a codear. Usted puede empezar creando un diagrama de flujo solamente con una caja de INICIO y una caja de FINAL, como es mostrado en la figura 7-2.
Ahora piense en qué pasará cuando usted juegue Ahoracado. Primero, la computadora piensa en una palabra secreta. Después el jugador adivina las letras. Agregue las cajas para estos eventos, como está mostrado en la figura 7-3. Las nuevas cajas en cada diagrama de flujo tienen una línea intermintente.

![Imagen de Inicio y final en el diagrama de flujo](https://inventwithpython.com/invent4thed/images/00083.jpeg)

Figura 7-2: Empiece su diagrama de flujo con una caja de INICIO y una caja de FINAL.

![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00084.jpeg)

Figura 7-3: Dibuje los dos primeros pasos de Ahorcado como cajas con descripciones.
Pero el juego no termina luego de que el jugador adivina la letra. El programa necesita revisar si la letra está en la palaba secreta.

## Ramificando desde una Caja del flujo de diagrama
Hay dos posibilidades: La letra está en la palabra o no. Usted va a añadir dos cajas nuevas en el diagrama de flujo, uno por cada caso. Esto crea una rama en el diagrama de flujo, como está mostrado en la figura 7-4.
![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00087.jpeg)

Figura 7-4: La rama tiene dos flechas que van en cajas separadas.

Si la letra no está en la palabra secreta, revisa si el jugador ha adivinado todas las letras y ha ganado el juego. Si la letra no está en la palabra secreta, revise si el ahorcado está completo y el jugador ha perdido. Agregue cajas para aquellos casos también.
El diagrama de flujo ahora se ve como en la figura 7-5.

![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00089.jpeg)

Figura 7-5 : Después de la rama, los pasos continuan en caminos separados.

## Terminando o reiniciando el juego

Una vez que el jugador ha ganado o perdido, preguntele a ellos si desean jugar de nuevo con una nueva palabra secreta. Si el jugador no quiere jugar de nuevo, el programa termina; de otra forma, el programa continua y piensa en una palabra secreta nueva. Esto se muestra en la figura 7-6.
![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00091.jpeg)

Figura 7-6: La rama del diagrama de flujo después de preguntarle al jugador si quiere jugar nuevamente. 


## Adivinando nuevamente
El diagrama de flujo se ve casi completo, pero aún nos faltan una cuantas coasa. Por ejemplo, el jugador no adivina una letra solamente una vez; ellos constantemente adivinan letras hasta que ganen o pierdan. Dibuje dos nuevas flechas como se muestra en el figura 7-7.
¿Qué pasa si el jugador adivina la misma letra otra vez? En lugar de contar esta letra nuevamente, permitales a ellos adivinar una letra figerente. Esta nueva caja se muestra en la Figura 7-9

![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00092.jpeg)

Figura 7-7: Las flechas intermintentes muestran que el jugador puede volver a adivinar.

![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00094.jpeg)

Figura 7-8: Agregue un nuevo paso en caso de que el jugador adivine una letra que ya haya adivinado.

Si el jugador adivina la misma letra dos veces, el diagrama de flujo conduce de nuevo a la caja de "Pregunte al jugador por una letra".

## Ofreciendo retroalimentación al jugador

El jugador necesita saber cómo le está yendo en el juego. El programa deber mostrarle el dibujo del hombre Ahorcado y la palabra secreta (con los espacios en blanco de las letras que aún no ha adivinado). Estas pistas visuales les permiten a ellos ver de cerca si están ganando o perdiendo el juego.
Esta información es actualizada cada vez que el jugador adivina una letra. Agregue una caja de "Mostrar el dibujo y el espacio al blando al jugdor" en el diagrama de flujo entre la caja de "Imagine una palabra secreta" y la caja de "Preguntele al jugador una letra", como se muestra en la Figura 7-9.

![Imagen del diagrama de flujo](https://inventwithpython.com/invent4thed/images/00095.jpeg)

Figura 7-9: Agregue una caja de "Muestre el dibujo y los espacios en blanco al jugador" para darle retroalimentación al jugador.

¡Eso se ve bien! El diagrama de flujo mapeea completamente el orden de todo lo que puede pasar en el juego de Ahorcado. Cuando usted diseña sus propios juegos, un diagrama de flujo puede ayudarle a recordar todo lo que necesita codear.

## Resumen

Podría verse  que es un montón de trabajo bosquejar el diagrama de flujo sobre el primer programa. Después de todo, las personas quieren jugar juegos, ¡no ver diagramas de flujo! Pero es mucho más fácil hacer cambios e identificar problemas pensando como el programa va a funcionar antes de empezar a escribirlo.
Si usted salta a escribir el código primero, usted puede descubrir problemas que requieran que usted cambie código que ya ha sido escrito, perdiendo tiempo y esfuerzo. Además, cada vez que usted cambie su código, usted corre el riesgo de crear nuevas pulgas al cambiar muy poquito o mucho. Es mucho más eficiente conocer que es lo que quiere construir antes de construirlo. Ahora que tenemos un diagrama de flujo, ¡vamos a crear el programa Ahorcado en el capítulo 8!





