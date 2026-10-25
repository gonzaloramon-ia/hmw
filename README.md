# HWM alfa 0.8.5 AUDIO

Rama experimental de audio basada en la jugabilidad estable de 0.8.4.

## Efectos incluidos

- órdenes del jugador;
- choque cuerpo a cuerpo;
- impacto reforzado de caballería;
- descargas de arqueros;
- lanzamiento de jabalinas de peltastas;
- impactos de proyectiles;
- desbandada de una formación;
- inicio de batalla;
- victoria y derrota.

Los efectos se generan con **Web Audio API** y no requieren archivos de sonido externos. Se agrupan y limitan por tiempo para evitar saturación cuando muchas formaciones combaten a la vez.

El botón **FX** de la barra superior permite activar o silenciar los efectos. La preferencia queda guardada en el navegador.

## Baseline

La rama `main` conserva HWM 0.8.4 como referencia estable. Esta rama no modifica la lógica de combate, moral, cohesión, IA, formaciones ni ritmo de batalla.
