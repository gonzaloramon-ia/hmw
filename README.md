# HWM alfa 0.8.5

Esta versión conserva la base táctica de HWM 0.8.4 e incorpora dos mejoras estructurales:

- **Dos velocidades por formación:** Marcha y Rápido.
- **Arquitectura de audio por estados** preparada para integrar la banda sonora y efectos de mayor calidad.

## Velocidades

Cada formación aliada puede alternar entre:

- **Marcha** — velocidad normal.
- **Rápido** — aproximadamente +42% de velocidad, con pérdida gradual de cohesión mientras la formación se desplaza fuera del contacto.

Esto agrega una decisión táctica sin modificar daño, moral, IA ni reglas de combate.

## Audio

Los efectos sintéticos generados con Web Audio que se probaron durante el desarrollo fueron retirados del build público porque no alcanzaban el nivel de calidad buscado.

Se conserva la lógica de eventos para integrar después muestras reales/cinematográficas sin tocar el motor táctico.

Estados musicales disponibles:

- `menu`
- `deploy`
- `approach`
- `combat`
- `crisis`
- `victory`
- `defeat`

## Baseline

La rama `baseline-0.8.4` conserva la versión estable anterior.
