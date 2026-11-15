# Misión Marte · Proyecto Ares 2050

Videojuego educativo para móviles (niños de 7 a 12 años) sobre cómo fundar la primera colonia humana en Marte.

**Historia:** es 2050, la Tierra está en malas condiciones y la humanidad necesita un nuevo hogar. Diriges a la tripulación de astronautas que debe convertir un cráter marciano en una colonia autosuficiente.

## Cómo jugar
- Abre `index.html` en el navegador del móvil junto con la carpeta `assets/` (sprites de los edificios). Para que todo funcione bien, sírvelo desde un servidor web (por ejemplo `python3 -m http.server`).
- Vista isométrica (mapa de 40×40 baldosas de 64×32 px): arrastra para mover la cámara, pellizca o usa + / − para hacer zoom, ⌂ para volver a la base.
- Pulsa **Construir** (o toca el suelo), elige un edificio y colócalo: la huella se ve verde si el sitio es válido y roja si no.
- Elige tu nombre y 3 especialistas (ingeniera, botánico, doctora, geólogo, psicóloga).
- Edificios: base central, pasillos, paneles solares, planta MOXIE (oxígeno del CO₂), extractor de hielo, excavadora minera, batería, bio-laboratorio contra percloratos, invernadero, granja vertical, refugio de regolito (toca un cráter para construirlo ahí), antena, hábitat (doble sobre tubos de lava), comedor, gimnasio, taller de robots, microrreactor nuclear y escudo magnético.
- Recoge las cajas de carga que llegan desde la Tierra.
- Los pasillos solo se unen entre sí y con las puertas de los edificios. Un edificio sin conexión con la base produce un 40% menos y gasta un 50% más de energía.
- Cada sol tiene día y noche: los paneles solo funcionan de día y de noche hacen falta baterías o reactor.
- Los edificios se desgastan y se averían si no se les hace mantenimiento; con el tiempo llegan tormentas largas y meteoritos que dejan muy averiado todo lo que haya en una zona de 4×4 (el escudo magnético los evita).
- Las mecánicas se desbloquean poco a poco: noche (misión 1), conexiones (misión 2), desgaste (sol 4), mejoras (misión 4), comida que se estropea (misión 5), investigación (sol 6), almacenes con límite (misión 7) y meteoritos (misión 9 y sol 12).
- Tripulación de 6: tú y 5 especialistas elegidos entre 10, cada uno con una habilidad propia.
- Las obras tardan en terminarse: paneles, extractor, excavadora y batería 1 sol; MOXIE, laboratorio, invernadero, gimnasio, antena y comedor 2; refugio, taller, hábitat y granja vertical 3; reactor y escudo 4. Los pasillos son instantáneos.
- Mejora los edificios hasta nivel 3 (cada nivel ×1,5 de producción o capacidad); el nivel se ve en el mapa.
- Avisos antes de que pase algo (desgaste alto, energía de la noche, recursos que se acaban, previsión del clima) y confirmación al pasar el sol si hay avisos nuevos.
- La antena (o la meteoróloga) anuncia tormentas y olas de frío 1 o 2 soles antes.
- El bio-laboratorio investiga 9 mejoras con el método científico: primero predices qué pasará, el experimento dura unos soles y al final se compara el resultado con tu hipótesis.
- Cada edificio tiene un botón "¿Por qué?" que explica en dos frases por qué funciona así.
- Las preguntas tratan de lo que acaba de pasar (tras una tormenta, una sobre tormentas; al construir la MOXIE, una sobre el CO₂).
- En la pantalla final, "Datos aprendidos" muestra todas las preguntas respondidas, los experimentos y los datos descubiertos.
- Puntuación final según colonos, edificios en pie (y sus niveles), recursos guardados, rapidez o soles sobrevividos y misiones; con récord guardado.
- 25 logros en 6 grupos con barra de progreso (por ejemplo "Racha perfecta: 3/5"). Se guardan aparte de la partida y no se pierden al empezar de nuevo o al perder.

- Tamaños: base 6×6 (se conecta con pasillos por el extremo de sus 4 brazos); MOXIE 1×3; hábitat, invernadero, granja vertical, extractor, refugio, reactor y escudo 3×3; el resto 2×2; pasillos 1×1. Hay que dejar una baldosa libre entre edificios distintos; los iguales y los pasillos pueden ir pegados.
- Cada colono consume oxígeno, agua y comida en cada sol; casi todo gasta energía.
- Afronta tormentas de polvo, tormentas solares, olas de frío, averías, micrometeoritos y decisiones sin ayuda inmediata de la Tierra (retraso de ~20 min).
- Responde preguntas del control de misión y desbloquea datos reales de la NASA.
- Gana al cumplir las 12 misiones y llegar a 30 colonos.

La partida se guarda automáticamente en el navegador.

## Laika, la IA de la base
- Laika, la inteligencia artificial de la base, acompaña toda la partida con ocho expresiones (normal, explicando, pensativa, sorprendida, feliz, triste, preocupada y alarmada); si pasan varias cosas a la vez muestra la más importante.
- Sus globos de diálogo sustituyen a los avisos emergentes; te frena antes de pasar el sol si hay algo importante, anuncia la previsión del clima y da el tutorial por pasos.
- Al tocar su retrato se abre su menú: objetivo actual, mantenimiento general, cuaderno de ciencia, logros, registro y repaso de consejos.
- Las imágenes están en `assets/laika_*.png`; la correspondencia emoción → imagen está en `MOOD_IMG`, dentro de `index.html`.
- Su historia la cuenta ella misma: toca la base central y pulsa «¿Quién eres?».
- Al empezar cualquier partida, su botón brilla con un aro dorado y un cartel «¡Tócame!» hasta que lo tocas por primera vez.

### La voz de Laika
- **Habla con voz y el texto aparece poco a poco** (unas 40 letras por segundo, un pitido cada 2–3 letras) solo cuando ella es el centro de atención: bienvenida y consejos del tutorial, su historia, victoria o derrota, sucesos importantes (tormentas, meteoritos, naves, nuevas mecánicas), misiones cumplidas, logros y avisos urgentes.
- **Texto de golpe y sin voz**: mensajes repetidos del globo (obra en marcha, caja abierta, mantenimiento, falta material), listas (objetivo, cuaderno, registro, diccionario), lo que el jugador pide al tocar algo (¿Por qué?, palabras del glosario) y las preguntas del quiz.
- Para que no canse: si habló hace menos de 8 s el siguiente mensaje sale sin sonido (salvo las páginas siguientes de una misma charla); cada tipo de mensaje tiene voz solo las primeras veces (p. ej. «obra terminada», 2 veces); la voz dura como mucho 2,5 s aunque el texto siga.
- Primer toque mientras escribe: el texto sale entero y la voz se corta. Segundo toque: siguiente página o cerrar el globo. Las opciones de un suceso aparecen cuando termina el texto (o con el primer toque), y ese toque no pulsa nada de debajo.
- La voz se apaga aparte en **Ajustes → Voz**, sin quitar música ni efectos. Si el dispositivo tiene activado *reducir movimiento*, el texto sale entero de golpe.

## Dificultad
Se elige antes de la tripulación, en cada partida nueva (en la pantalla de tripulación, «← Cambiar» vuelve a elegirla; el modo difícil pide confirmación antes de empezar):
- **Fácil:** el juego base. Meta de 30 colonos; la puntuación vale la mitad.
- **Normal:** más desastres y meteoritos, un 30% más de desgaste, construir e investigar cuesta un 25% más. Meta de 40 colonos.
- **Difícil:** aún más desastres, un 70% más de desgaste, costes un 50% mayores, los edificios gastan un 20% más de energía y los colonos consumen un 15% más. Se empieza con más comida (110) para compensar el consumo, Laika casi no da consejos y la meta son 50 colonos; la puntuación vale un 50% más.

Las preguntas del control de misión también dependen de la dificultad: 18 en fácil (8-10 años), 18 en normal (11-13) y 25 en difícil (14+). Al agotarse se vuelven a mezclar sin repetir enseguida las últimas.

El refugio de regolito no necesita conexión con la base.

## Naves
- Cuantas más camas libres y mejor antena, más colonos trae cada nave (+2 por nivel de antena y +1 por cada 4 camas libres).
- Desde la ficha de la antena se puede **llamar a una nave** al momento pagando 40 de material (más en normal y difícil).
- Desmontar devuelve la mitad de todo lo pagado, mejoras incluidas.

## Glosario
- Las palabras difíciles aparecen subrayadas en las fichas, sucesos y preguntas (solo la primera vez en cada texto). Al tocarlas, Laika las explica en su globo.
- En el menú de Laika está el **Diccionario**, con todas las palabras por grupos y las ya consultadas marcadas. Consultar 40 da el logro *Diccionario andante*.

## Música
- En los menús (portada, historia, dificultad, tripulación, viaje y pantalla final) suena en bucle la música de menú (`assets/musica_menu.mp3`, provisional).
- En la partida suena la pista de la dificultad (`assets/musica_facil.mp3`, `musica_normal.mp3`, `musica_dificil.mp3`): empieza en un momento al azar, se apaga poco a poco en sus últimos 25 segundos y vuelve a sonar tras un silencio de 1 a 3 minutos.
- Se puede silenciar con el botón 🎵 de la portada o desde Ajustes.

## Clima espacial real (NASA DONKI)
- Las tormentas solares usan erupciones reales del catálogo DONKI de la NASA (CCMC, Goddard): fecha, clase GOES (A, B, C, M, X) y región activa. Cuanto más fuerte la clase, más daño hacen sin refugio.
- La antena anuncia la clase de la erupción antes de que llegue; el cuaderno de ciencia guarda las erupciones vividas y hay un logro, *Cazador de erupciones*.
- Para añadir más erupciones, pega la respuesta JSON de DONKI en `DONKI_RAW` dentro de `index.html`.

## ¿Ciencia real o ficción?
Cada edificio, investigación y dato curioso lleva una etiqueta: ✅ **Real hoy** (existe y ya se usa), 🧪 **En pruebas** (probado en pequeño o en la Tierra) o 🔮 **Idea para el futuro** (todavía no existe). Laika lo explica la primera vez que construyes algo de cada tipo.

Cada refugio de regolito protege a 12 personas: en una tormenta solar, los colonos que no caben sufren daño.

## Fuentes
Todos los datos científicos tienen su fuente oficial (prioridad NASA / JPL / ESA) en [`FUENTES.md`](FUENTES.md). En el juego se consultan en **Ajustes → 📚 Fuentes**, con enlaces a cada página.
