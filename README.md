# HWM alfa 0.8.5 AUDIO

Esta versión parte de HWM 0.8.4 y agrega una capa sonora adaptativa sin modificar la lógica de combate.

## Efectos implementados

- confirmación de órdenes con llamada breve tipo salpinx;
- marcha de formaciones;
- galope de caballería;
- choque de escudos / armas en cuerpo a cuerpo;
- impacto reforzado de caballería;
- descarga de arqueros;
- lanzamiento de jabalinas de peltastas;
- impactos diferenciados de flechas y jabalinas;
- desbandada de formaciones;
- señal de penetración del paso en Termópilas;
- inicio de batalla;
- cierre breve de victoria o derrota;
- ambiente de batalla cuya densidad aumenta según la cantidad real de formaciones trabadas.

Los sonidos se generan con Web Audio API y no requieren archivos de audio externos. Se usan límites de frecuencia para evitar saturación cuando varias formaciones combaten al mismo tiempo.

## Estados musicales preparados

El juego emite el evento `hwm:musicstate` con estos estados:

- `menu`
- `deploy`
- `approach`
- `combat`
- `crisis`
- `victory`
- `defeat`

Esto permite integrar después la música de HWM sin tocar el motor táctico.

## Controles

El botón **FX** de la barra superior activa o silencia los efectos. La preferencia queda guardada en el navegador.

## Baseline

HWM 0.8.4 se conserva como referencia estable separada. La 0.8.5 no altera daño, moral, cohesión, IA, formaciones, velocidades ni ritmo de batalla.
