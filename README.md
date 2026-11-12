# Misión Marte · Proyecto Ares 2050

Videojuego educativo para móviles (niños de 7 a 12 años) sobre cómo fundar la primera colonia humana en Marte.

**Historia:** es 2050, la Tierra está en malas condiciones y la humanidad necesita un nuevo hogar. Diriges a la tripulación de astronautas que debe convertir un cráter marciano en una colonia autosuficiente.

## Cómo jugar
- Abre `index.html` en el navegador del móvil junto con la carpeta `assets/` (sprites de los edificios). Para que todo funcione bien, sírvelo desde un servidor web (por ejemplo `python3 -m http.server`).
- Vista isométrica (mapa de 30×30 baldosas de 64×32 px): arrastra para mover la cámara, pellizca o usa + / − para hacer zoom, ⌂ para volver a la base.
- Pulsa **Construir** (o toca el suelo), elige un edificio y colócalo: la huella se ve verde si el sitio es válido y roja si no.
- Elige tu nombre y 3 especialistas (ingeniera, botánico, doctora, geólogo, psicóloga).
- Edificios: base central, pasillos, paneles solares, planta MOXIE (oxígeno del CO₂), extractor de hielo, excavadora minera, batería, bio-laboratorio contra percloratos, invernadero, granja vertical, refugio de regolito (cabe en cráteres), antena, hábitat (doble sobre tubos de lava), comedor, gimnasio, taller de robots, microrreactor nuclear y escudo magnético.
- Recoge las cajas de carga que llegan desde la Tierra.
- Tamaños: base 4×4; hábitat, invernadero, granja vertical, extractor, refugio, reactor y escudo 3×3; el resto 2×2; pasillos 1×1. Hay que dejar una baldosa libre entre edificios (los pasillos pueden ir pegados para unirlos).
- Cada colono consume oxígeno, agua y comida en cada sol; casi todo gasta energía.
- Afronta tormentas de polvo, tormentas solares, olas de frío, averías, micrometeoritos y decisiones sin ayuda inmediata de la Tierra (retraso de ~20 min).
- Responde preguntas del control de misión y desbloquea datos reales de la NASA.
- Gana al cumplir las 12 misiones y llegar a 30 colonos.

La partida se guarda automáticamente en el navegador.
