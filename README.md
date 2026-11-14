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
