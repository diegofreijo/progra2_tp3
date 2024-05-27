# TP3 de Programación de Video Juegos 2: UnitInvaders 2.0 en Unity

## Metodología

|                        |                              |
| ---------------------- | ---------------------------- |
| Integrantes por grupo: | 1                            |
| Se aprueba con         | 6                            |
| Fecha de entrega       | Jueves 13 de Junio, 23:59 hs |
| Fecha de re-entrega    | Jueves 27 de Junio, 23:59 hs |


### Objetivos

- Mejorar el manejo de Unity
- Aprender como implementar funcionalidades comunes a muchos juegos en 2D


### Comentarios Adicionales

Tengan en cuenta que en varios de estos ejercicios espero que apliquen los conceptos que vimos en clase como encapsulamiento y polimorfismo. Puede que igual se los de por correctos a los ejercicios donde podrían haberlo usado y no lo hicieron, pero me van a tener que justificar porque no usaron esa solución y se fueron por otro lado.

Pueden asumir cosas que no están aclaradas explícitamente. Si igualmente tienen dudas, pregunten.

Recuerden que, por lo general, la solución más simple es la mejor.

----

## Entrega

### Código

Todo lo van a resolver en un repositorio de GitHub.

Antes de la fecha limite me tienen que mandar el link del repo por mail a <me@diegofreijo.com>.

Tiene que haber una `tag` que se llame `tp3`. Ese commit es el que voy a corregir.

Si crearon branches por feature o por ejercicio, no los borren. Así puedo ver cómo estuvieron trabajando.

### Defensa

Les voy a estar mandando horarios para que cada uno se conecte y tengamos la devolución por Google Meet.

----

## UnitInvaders 2.0

Vamos a extender el UnitInvaders 1, el del TP2, agregándole algunas mejoras parecidas a las que estuvimos viendo en Unity en las ultimas clases.

### Movimiento de los Enemigos (3 puntos)

Vamos a seguir mejorando la avanzada AI de nuestros enemigos. Ya teníamos que disparaban cada tanto, ahora queremos que se muevan. 

El patrón de movimiento va a ser parecido al del juego original. Detallo los pasos:

1. Arrancan moviéndose horizontalmente todos hacia un lado. 
	- Todos se mueven a la par como en el juego original
	- Si quieren que cada alien se mueva a distinta velocidad así no están sincronizados, pueden hacerlo
2. En algún momento van a decidir que ya se movieron lo suficiente y van a bajar. La condición para decidir cuando pasar a la fila de abajo la pueden definir ustedes. Algunas opciones:
	- Cada `n` segundos
	- Cuando el alien mas cercano a la pared se choco o esta muy cerca de la pared
	- Después de haberse movido `x` unidades en el mundo
3. Ustedes también van a poder definir cuanto bajar en el eje `y` cada vez que cambian de fila. Estaría bueno que los aliens puedan al menos bajar 3 veces antes de estar a la misma altura que el jugador, así el nivel le da suficiente tiempo al jugador de dispararle a todos
4. Al bajar de fila, van a comenzar a moverse para el mismo lado
	- O sea que si estaban yendo para la izquierda ahora van a ir para la derecha y vice-versa.
5. Volver al punto 1

Como los enemigos se mueven, ahora van a suponer un nuevo desafío para el jugador. Si alguno lo toca, el jugador pierde.


### Misilazo (4 puntos)

Disparar siempre hacia arriba es aburrido. Vamos a agregar una nueva arma: el misilazo! (pueden cambiarle el nombre)

Vamos a dejar que el jugador pueda seguir disparando como hace ahora con la barra espaciadora. Y el misilazo lo va a hacer con el mouse. Este se va a comportar como el misil normal excepto por estas diferencias:

- Se dispara con el mouse. Va a dispararse con un click e ir en la dirección donde esta el mouse (como el disparo del caballero en clase).
- Va a viajar mas lento que el misil normal
- Cuando impacte contra un enemigo o una pared, va a explotar
- La explosión va a tener cierto radio que pueden definir ustedes. Yo diría que sea de mas o menos el radio de 2 enemigos pero les doy libertad creativa.
- La explosión va a destruir a todos los enemigos a los que alcance. También puede destruir al mismo jugador si quieren!

Como es un arma que nos desbalancea el juego, vamos a nerfearla un poco. El misilazo solo se puede disparar cada 5 segundos (también pueden alterar este numero como les guste). 

Además tenemos que darle algún feedback al jugador para que sepa cuanto le falta para el misilazo. Puede ser un contador numérico en el HUD, o una barra de progreso, etc. 

### Game Feel (3 puntos)

Vamos a ponerle "game feel" a nuestro juego con varias mejoras cosméticas. Estas son las mejoras que se me ocurren pero los invito a que agreguen todas las que gusten!

- Las explosiones de los misiles y misilazos van a mostrar algún efecto visual que desaparezca a los pocos segundos de suceder.
- Alguna animacion para cuando el jugador o algún enemigo es destruido.
- Efectos sonoros a la hora de destruir un enemigo, al jugador, disparos, explosiones. 
- Efectos sonoro cuando se pierde y cuando se gana.
- Screen shake con el misilazo
- Alguna musica de fondo a elección.
