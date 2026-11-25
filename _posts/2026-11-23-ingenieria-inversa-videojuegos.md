---
title: "Ingeniería inversa: leer un videojuego desde dentro"
description: "Qué significa analizar un juego sin su código fuente y cómo se investiga su funcionamiento."
category: Fundamentos
number: "01"
read_time: 5
image: /assets/img/reversa.svg
image_alt: "Ilustración de un mando con circuitos digitales y fragmentos de código hexadecimal"
---
Cuando pulsamos un botón y nuestro personaje salta, parece que el videojuego responde de forma inmediata. Detrás de ese gesto, sin embargo, trabajan sistemas de entrada, físicas, animación, memoria y sonido. La **ingeniería inversa** propone seguir ese recorrido al revés: observar un programa existente e intentar comprender cómo funciona.

## ¿Qué es la ingeniería inversa?

En el desarrollo habitual diseñamos y escribimos código para obtener un programa. En ingeniería inversa partimos del resultado, que puede ser un ejecutable, un archivo de datos o una comunicación de red, y reconstruimos hipótesis sobre la lógica que lo produce.

**No consiste necesariamente en recuperar el código fuente original.** Dos programas con código diferente pueden comportarse de manera equivalente. Por eso el análisis trata de identificar estructuras, dependencias y reglas verificables, aunque se desconozcan detalles de la implementación inicial.

En videojuegos, un investigador podría preguntarse cómo se guarda una partida, cómo se interpretan los niveles o qué reglas gobiernan un motor. Cada pregunta exige observaciones y herramientas distintas.

## ¿Cómo se investiga el funcionamiento de un juego?

Un proceso básico puede estructurarse en cuatro fases:

<div class="pipeline" aria-label="Proceso de ingeniería inversa"><span>OBSERVAR</span><b>→</b><span>ANALIZAR</span><b>→</b><span>HIPÓTESIS</span><b>→</b><span>COMPROBAR</span></div>

1. **Observar.** Documentamos las entradas y salidas visibles: menús, controles, archivos creados y cambios en el juego.
2. **Inspeccionar.** Estudiamos la estructura de archivos y, cuando está permitido, el programa. Podemos identificar cadenas de texto, cabeceras o referencias a funciones.
3. **Formular hipótesis.** Por ejemplo, que ciertos bytes almacenan información de una partida o que un formato agrupa imágenes y sonidos.
4. **Contrastar.** Utilizamos distintos ejemplos y pruebas para comprobar si las hipótesis predicen de forma consistente el comportamiento.

También se distingue entre **análisis estático** (examinar archivos e instrucciones sin ejecutar el programa) y **análisis dinámico** (observar el comportamiento durante una ejecución controlada). Ambos enfoques se complementan.

## Herramientas y aplicaciones

Una herramienta conocida es [Ghidra](https://ghidra-sre.org/), un entorno de análisis de software que ayuda a explorar programas compilados. También resultan útiles los editores hexadecimales, depuradores y documentación de formatos.

Entre sus aplicaciones aparecen la creación de herramientas compatibles, la documentación de formatos antiguos, la localización de fallos y la investigación sobre sistemas que ya no cuentan con soporte.

Un caso relacionado, aunque distinto, es estudiar el código de [DOOM publicado por id Software](https://github.com/id-Software/DOOM). Allí el código fuente está disponible: podemos aprender directamente de él, sin necesitar reconstruirlo a partir de un ejecutable cerrado.

## La importancia del contexto legal

Comprender un programa no implica tener derecho a redistribuir sus archivos, sus recursos gráficos o su código. Las licencias y la legislación establecen límites distintos para el análisis, la interoperabilidad y la distribución. También conviene evitar alterar servicios o partidas de otras personas sin autorización.

La ingeniería inversa, practicada con responsabilidad, es una forma de convertir la curiosidad sobre un videojuego en conocimiento técnico contrastable.

### Fuentes y lectura complementaria

- [Ghidra — sitio oficial](https://ghidra-sre.org/).
- [id Software — código fuente publicado de DOOM](https://github.com/id-Software/DOOM).
- [Directiva 2009/24/CE sobre programas de ordenador](https://eur-lex.europa.eu/eli/dir/2009/24/oj?locale=es).
