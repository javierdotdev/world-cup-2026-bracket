# 🏆 World Cup 2026 — Cuadro Radial Interactivo

Una visualización **radial e interactiva** del cuadro de eliminatorias del Mundial 2026, construida con HTML, CSS, JavaScript y SVG puros — **sin frameworks ni build**. Un solo archivo `index.html`, listo para hostear en cualquier lado.

> Los 48 equipos convergen desde el anillo exterior hacia el trofeo del centro. Cada resultado real hace que el ganador se **deslice** con animación hacia la siguiente ronda.

**[🔗 Demo en vivo](https://javierdotdev.github.io/world-cup-2026-bracket)** ← reemplaza con tu URL

---

## ✨ Características

- **Cuadro radial 360°** — de 32avos al campeón, con líneas en ángulo recto estilo bracket clásico.
- **Animación de avance** — al cargar, los clasificados se deslizan a su ronda real.
- **Ficha por equipo** — toca una bandera y abre un panel con:
  - Nivel, tipo de favorito y riesgo (perfil estratégico)
  - Partidos ganados en el Mundial (grupos + eliminatoria, sin contar penales)
  - Marcador del partido, alargue/penales y **el pick de la quiniela** con sus puntos
  - Próximo rival y fecha
- **Ruta iluminada** — resalta el camino de un equipo hacia el título.
- **Predicciones temporales** — arrastra una bandera a su siguiente nodo para predecir; se guardan en tu navegador y **nunca alteran los datos reales**.
- **Girar y hacer zoom** — arrastra el fondo para rotar la rueda; las banderas y el trofeo se mantienen derechos.
- **Banderas con doble fuente** — CDN (circle-flags) con copia incrustada de respaldo: funciona hasta sin internet.
- **Responsive** — se adapta a escritorio y móvil.

---

## 🚀 Cómo publicarlo

Es un único archivo estático. Elige una:

**Opción A — Netlify Drop (la más rápida)**
1. Entra a [app.netlify.com/drop](https://app.netlify.com/drop)
2. Arrastra `index.html`
3. Listo: URL pública al instante.

**Opción B — GitHub Pages**
1. Crea un repositorio y sube `index.html`.
2. *Settings › Pages › Source:* rama `main`, carpeta `/root`.
3. Queda en `https://javierdotdev.github.io/world-cup-2026-bracket`.

No requiere Node, npm ni compilación.

---

## 🎯 El método detrás de los picks

Este cuadro nació de una quiniela real de 80 jugadores donde el reto era competir **sin seguir fútbol**, solo con análisis de datos. Cada pick sale de un marco propio:

- **3 tipos de favorito** — vs rival débil/abierto → goleada; vs muro defensivo → victoria corta; vs rival fuerte → resultado ajustado o empate.
- **Capa de gap** — primero se decide el *signo* (gana/empata/pierde), luego el margen.
- **Disciplina** — las lecturas en frío no se cambian por corazonadas de último minuto.

Las fichas muestran cada predicción y sus puntos, así que el cuadro es también el registro visual del método.

---

## 🛠️ Cómo está hecho / cómo editarlo

Todo vive en `index.html`. Los datos son objetos JavaScript al inicio del `<script>`:

- `TEAMS` — los 32 equipos en orden (cada par forma un partido; cada dos partidos, un cruce de la ronda siguiente).
- `MATCHES` — resultados reales por clave `"ronda-partido"`: marcador, quién avanza, penales/alargue, pick y puntos.
- `PROFILES` — perfil estratégico de cada equipo.
- `GROUPWINS` — victorias en fase de grupos.

Para cargar un resultado nuevo, agrega una línea a `MATCHES` (ej. `"2-0": {score:[1,0], adv:"ma", pick:[1,1], pts:3}`) y el ganador se anima solo a la siguiente ronda.

---

## 🧩 ¿Reutilizable como template?

Sí. Sirve para cualquier torneo de eliminación directa (fútbol local, esports, torneos de empresa). Basta cambiar `TEAMS`, `MATCHES` y los perfiles. Para adaptarlo a otro número de equipos hay que ajustar los radios de los anillos en `RADII`.

---

## 📄 Licencia

© 2026 Javier Martínez ([@javierdotdev](https://github.com/javierdotdev)).

Licencia **MIT** — libre de usar, modificar y compartir, conservando este aviso de copyright. Si lo reutilizas, un crédito se agradece. 🙌

---

*Hecho con curiosidad, datos y un poco de terquedad disciplinada.*
