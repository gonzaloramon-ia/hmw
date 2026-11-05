# HWM 0.9.1 RC1 — Grandes batallas de la historia

HWM es un RTS táctico histórico centrado en formaciones, terreno, moral, cohesión y asimetría entre ejércitos.

## Estado actual

La campaña **Campaña del Comandante** tiene 10 batallas válidas:

1. Maratón
2. Termópilas
3. Platea
4. Mantinea
5. Gaugamela
6. Cannas
7. Hastings
8. Agincourt
9. Bosque de Teutoburgo
10. Borodinó

`Maratón 2` queda como archivo/prueba y no cuenta para la campaña.

## Sistemas integrados

- progreso persistente con victorias, puntaje, medallas, XP y rangos;
- reservas y refuerzos;
- moral, cohesión, retirada y reorganización;
- formaciones Línea / Cuña / Columna;
- terreno procedural, bosque, barro, colinas, marjal y redutos;
- objetivo especial de escape y emboscadas en Teutoburgo;
- artillería y shock de área limitado en Borodinó;
- disciplina de falange: hoplitas, falanges y muros de escudos no persiguen automáticamente cuando están en línea y cohesionados;
- roster ampliado a 30 tipos de unidad;
- diferenciación mecánica de persas, macedonios, romanos, cartagineses, normandos, sajones, ingleses, franceses, germanos y ejércitos napoleónicos;
- dos intros cinematográficas locales con rotación automática;
- música y SFX integrados.

## Desarrollo con dos agentes

La coordinación del proyecto se hace mediante:

- `AGENTS.md`: contrato operativo persistente;
- `CAMPAIGN_V1.md`: contrato de campaña;
- GitHub Issue #2: tablero compartido entre agentes.

Roles actuales:

- **Agente A**: chat principal, líder técnico e integrador.
- **Agente B / Work**: ejecutor autónomo de tareas largas y paralelas.

Antes de modificar código, cualquier agente debe leer `AGENTS.md`, HEAD de `main`, `CAMPAIGN_V1.md` y los últimos comentarios de Issue #2.

## Prioridad inmediata

Completar identidad gráfica propia por ejército, empezando por:

Teutoburgo → Cannas → Gaugamela → Hastings → Agincourt → Borodinó.

Después: QA jugable de las 10 batallas, balance fino y cierre de v1.0.

## Estado de release

`0.9.1 RC1` es una release candidate. El JavaScript y los datos pasaron QA lógico/estático, pero todavía falta QA jugable completo en navegador antes de declarar v1.0.

---

## Historial 0.8.x

### Música

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

## Intro cinematográfica 0.8.16

El juego espera el archivo `HWM-intro.mp4` en la raíz del repositorio.

- se reproduce una vez por sesión;
- puede saltarse;
- puede repetirse desde el botón ▶ de la barra superior;
- subtítulos castellanos superpuestos desde el juego;
- pausa adicional de 1,9 s en el primer cartel reflexivo y de 1,5 s en el cierre para mejorar lectura;
- si el archivo no existe o falla, HWM continúa normalmente al briefing.

La intro sigue siendo reemplazable: basta sustituir `HWM-intro.mp4` por una nueva versión manteniendo el mismo nombre.

## Combate humano 0.8.17

- choques de hoplitas reforzados y con segunda capa ocasional de metal;
- grito colectivo al primer contacto de una formación;
- grito de impulso cuando una formación enemiga cercana se desbanda;
- desbandada con voz distinta del grito ofensivo;
- enfriamientos globales y por formación para evitar repetición constante.

## Campo ampliado 0.8.18

- área fuera del mundo jugable representada en negro absoluto;
- dock inferior reducido de ~178 px a ~86 px en escritorio;
- órdenes en una sola fila compacta, estilo taskbar;
- panel de unidad y minimapa reducidos sin quitar funciones;
- etiquetas de órdenes abreviadas para ganar espacio;
- en pantallas chicas se conserva un layout adaptativo más alto.

No se modificó combate, IA, moral, cohesión ni balance.
