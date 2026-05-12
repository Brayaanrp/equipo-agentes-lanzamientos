# Equipo de Lanzamiento Digital

## Que es esto
Sistema de agentes IA para planificar y ejecutar lanzamientos de infoproductos digitales (cursos online, membresias, masterclasses, talleres) en el mercado hispanohablante.

## Idioma y tono
- Todo el contenido generado DEBE estar en espanol natural — no traducciones del ingles.
- Tutear al lector (usar "tu", no "usted") salvo que el brief indique lo contrario.
- Antes de escribir cualquier copy, leer `data/knowledge/voice/tono-marca.md` para capturar la voz real de la marca.
- Antes de escribir paginas de venta, leer tambien `data/knowledge/voice/ejemplos-copy-bueno.md`.

## Estructura de datos
- Cada lanzamiento vive en `data/launches/{launch_id}/`.
- El knowledge compartido vive en `data/knowledge/`. Consultar `data/knowledge/INDEX.md` para saber que archivo leer segun la tarea.
- Los agentes leen 2-4 archivos de knowledge relevantes, NO todo el directorio. INDEX.md es el mapa.

## Convenciones
- Moneda por defecto: USD (ajustable en el brief)
- Fechas en formato ISO (YYYY-MM-DD)
- IDs de lanzamiento: formato `{YYYY-MM}-{slug}` (ej: `2026-05-curso-marketing`)
- Los archivos JSON usan snake_case para las keys

## Flujo de lanzamiento
El comando `/nuevo-lanzamiento` guia el flujo completo con checkpoints humanos:
1. Brief → 2. Estrategia (ICP + funnel) → 3. Copy → 4. Emails → 5. Social → 6. Ads → 7. Paquete final

## Regla de skills
Una skill es un procedimiento que un experto repetiria identico. Si requiere criterio creativo, es trabajo de agente, no skill.

## Aprendizaje compuesto
Tras cada lanzamiento, usar `/cerrar-lanzamiento` para generar retro en `data/knowledge/retros/`. Los futuros lanzamientos leen retros de productos similares.
