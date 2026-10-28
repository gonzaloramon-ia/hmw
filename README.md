# HWM alfa 0.8.15

HWM 0.8.7 conserva la jugabilidad de 0.8.6 y suma un pulido visual de lectura táctica sin alterar el combate.

## Música

- **Briefing inicial:** `Shadows of War`
- **Preparación / despliegue:** `Omniscient Evil`
- **Batalla:** sin música por ahora
- **Resultado:** `What History Remembers`

El cambio entre pistas usa fade suave. La música se puede silenciar desde el botón **♫** de la barra superior.

Por las restricciones de reproducción automática del navegador, la primera pista comienza a partir de la primera interacción del jugador.

## Efectos

Los efectos sintéticos de prueba permanecen retirados. La batalla queda preparada para incorporar más adelante muestras reales de armas, escudos, proyectiles, caballería, marcha y voces.

## Movimiento

Cada formación aliada tiene dos velocidades:

- **Marcha:** velocidad normal.
- **Rápido:** +42% de velocidad aproximadamente, con pérdida gradual de cohesión durante el desplazamiento.

## Baselines

- `baseline-0.8.4`: primera versión estable de referencia.
- `baseline-0.8.5`: versión estable anterior a la integración musical.

## Pulido visual 0.8.7

- selección de formaciones más clara, con base translúcida y dirección de frente;
- estandartes con mayor contraste y marca visual según tipo de unidad;
- sombras de formación más sólidas para anclar mejor las tropas al terreno;
- polvo discreto en avance rápido;
- feedback visual breve en choques cuerpo a cuerpo;
- corrección de la transición musical hacia la pantalla de resultado.

## Formaciones visuales 0.8.8

- Línea, Cuña y Columna ahora tienen disposiciones visibles distintas dentro de cada escuadrón.
- El contorno de selección adopta la huella real de la formación.
- La etiqueta de una unidad seleccionada muestra también su formación.
- No se modificaron daño, moral, cohesión, IA ni duración del combate.

## Lectura táctica 0.8.9

- órdenes de movimiento y ataque con marcadores visuales distintos;
- rutas de ataque y movimiento diferenciadas por color;
- línea directa al objetivo cuando una formación tiene blanco asignado;
- selección/hitbox ajustada a la huella visual de Línea, Cuña y Columna;
- resaltado al pasar el cursor sobre formaciones;
- alerta visual discreta en formaciones aliadas con moral o cohesión críticas;
- mayor separación entre formaciones cuando se ordena mover varias a la vez;
- barras de estado reposicionadas según la profundidad de la formación.

La lógica de daño, moral, cohesión, IA y duración del combate permanece sin cambios.

## Limpieza visual 0.8.10

- formaciones ligeramente más compactas;
- estandartes más pequeños y menos invasivos;
- barra de vida visible siempre;
- cohesión y moral visibles sólo al seleccionar, pasar el cursor, combatir o entrar en riesgo;
- alerta crítica más discreta;
- selección con menor opacidad para dejar ver mejor soldados y terreno.

La lógica táctica y el balance permanecen sin cambios.

## Banda sonora 0.8.11

Asignación actual:

- **Briefing:** `Shadows of War(3).mp3`
- **Briefing alternativo:** `Shadows of War (2)(1).mp3`
- **Despliegue:** `Omniscient Evil - usesuno.com.mp3`
- **Batalla:** sin música por ahora
- **Resultado principal:** `hhhhhhhh.mp3` (What History Remembers)
- **Resultado alternativo:** `uuuu(1).mp3` (What History Remembers)

El reproductor hace transiciones suaves y mantiene la batalla sin música hasta cerrar la capa de efectos de sonido.

## Música dinámica 0.8.13

`Omniscient Evil` continúa sin reiniciarse desde el despliegue hacia la batalla. El volumen se adapta al estado táctico:

- despliegue: 52%;
- aproximación / inicio de batalla: 32%;
- combate: 25%;
- crisis: 20%.

Al finalizar, la pista hace transición hacia `What History Remembers`. Este ducking deja espacio para la futura capa de ambiente y efectos de batalla.

## Sonido de batalla 0.8.15

Primera capa de SFX reales, separada de la música:

- ambiente de tropa/crowd durante la batalla;
- choque cuerpo a cuerpo;
- descarga de arqueros / proyectiles;
- carga/impacto de caballería;
- desbandada / ruptura.

Los efectos se disparan desde el estado real de la simulación y tienen límites de frecuencia para evitar saturación. El botón **FX** permite silenciarlos sin afectar la música.

Fuentes iniciales: Mixkit (Mixkit License), incluyendo Sword Strikes Armor, Arrow Shot Through Air, Horse Fast Gallop in the Dirt y crowd ambience. En esta fase se consumen desde el CDN de Mixkit; más adelante conviene guardar copias locales versionadas en el repositorio para eliminar dependencias externas.
