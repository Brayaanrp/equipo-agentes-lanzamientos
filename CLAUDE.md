# Equipo de Lanzamiento Digital

## Que es esto
Sistema de agentes IA para planificar y ejecutar lanzamientos de infoproductos digitales (cursos online, membresias, masterclasses, talleres) en el mercado hispanohablante.

---

## Como funciona (guia rapida)

### La idea en 30 segundos
Tienes un equipo de 5 agentes especializados que trabajan en cadena para generar todo lo que necesitas en un lanzamiento: estrategia, copy, emails, contenido social y campanas de ads. Tu les das un brief, ellos producen, y tu apruebas o pides cambios en cada paso.

> Para un mapa visual completo del sistema (cadena de agentes, knowledge, ciclo de retros y por que es potente), ver `data/knowledge/mapa-sistema.md`. Para una version simplificada para usuario final, ver `data/knowledge/mapa-sistema-simple.md`.

### Los 4 comandos que necesitas saber

| Comando | Cuando usarlo | Que hace |
|---------|---------------|----------|
| `/nuevo-lanzamiento` | Arrancas un lanzamiento | Te guia paso a paso: brief → estrategia → copy → emails → social → ads |
| `/revisar-estrategia` | Quieres ajustar algo | Carga un lanzamiento existente y te deja iterar sobre la estrategia |
| `/iterar` | Quieres cambiar una pieza especifica | Reescribe un email, headline, campana o seccion sin regenerar todo |
| `/exportar-lanzamiento` | Necesitas ver todo junto | Genera un documento unico con todos los entregables del lanzamiento |
| `/cerrar-lanzamiento` | Termino el lanzamiento | Genera una retro con numeros reales y aprendizajes para futuros lanzamientos |

### Los 5 agentes y que hace cada uno

```
Tu das el brief
    |
    v
[Estratega]        Analiza mercado, define cliente ideal, disena el funnel y la oferta
    |               Modelo: Opus (el mas potente — aqui se juega la estrategia)
    v
[Copywriter]       Escribe pagina de ventas, scripts de VSL/webinar, pagina de captura
    |               Modelo: Sonnet 4.6 (rapido y creativo)
    v
[Email Marketer]   Crea todas las secuencias: pre-launch, launch, cart abandonment, post-compra
    |               Modelo: Sonnet 4.6
    v
[Social Media]     Genera calendario de contenido, posts, reels, stories, carruseles
    |               Modelo: Sonnet 4.6
    v
[Ads Specialist]   Disena campanas Meta/Google: audiencias, copy de anuncios, presupuesto
                    Modelo: Sonnet 4.6
```

Cada agente lee lo que produjo el anterior. Tu apruebas entre fases.

### La capa de knowledge (lo que hace al sistema inteligente)

Los agentes no improvisan desde cero. Leen de `data/knowledge/`:

- **frameworks/** — Metodos probados (PLF, VSL, webinar, challenge). El agente elige cual usar segun tu funnel.
- **voice/** — Tu tono de marca real y ejemplos de copy que funciono. Esto es lo que evita que el output suene generico.
- **playbooks/** — Procedimientos paso a paso (como abrir carrito 72h, como manejar objeciones).
- **retros/** — Aprendizajes de lanzamientos pasados. Esto es lo mas valioso: el sistema mejora con cada lanzamiento.

Los agentes NO leen todo. Consultan `data/knowledge/INDEX.md` (un mapa de 1 pagina) y cargan solo 2-4 archivos relevantes.

### Las 6 skills (procedimientos reutilizables)

Las skills son recetas paso a paso. Se activan cuando un agente las necesita:

| Skill | Para que sirve |
|-------|----------------|
| `framework-plf` | Ejecutar los 4 videos pre-launch de Jeff Walker |
| `headline-formulas` | Generar 10-15 headlines con formulas probadas |
| `bonos-stack` | Disenar bonos que escalen el valor percibido de la oferta |
| `email-sequence-launch-7d` | Estructura dia por dia de emails en 7 dias de carrito abierto |
| `estructura-vsl` | Script completo de VSL bloque por bloque |
| `secuencia-cart-abandonment` | 4 emails para recuperar carritos abandonados |

### El ciclo de mejora continua

```
Lanzamiento 1 → /cerrar-lanzamiento → Retro con numeros y aprendizajes
                                            |
Lanzamiento 2 → El estratega lee la retro → Mejor estrategia
                                            |
Lanzamiento 3 → Lee retros 1 y 2 → Aun mejor
                                            |
                    ... el sistema se vuelve mas inteligente con cada lanzamiento
```

### Donde vive cada cosa

```
equipo-lanzamiento-digital/
├── CLAUDE.md                    ← Estas aqui. Contexto global.
├── .claude/
│   ├── agents/                  ← Los 5 agentes (estratega, copywriter, etc.)
│   ├── skills/                  ← Las 6 recetas reutilizables
│   └── commands/                ← Los 4 comandos (/nuevo-lanzamiento, etc.)
└── data/
    ├── launches/{id}/           ← Un lanzamiento por carpeta (brief, copy, emails, etc.)
    ├── knowledge/               ← El cerebro del equipo (frameworks, voz, playbooks, retros)
    └── templates/               ← Plantillas base para ICP y secuencias de email
```

### Antes de tu primer lanzamiento

El sistema necesita conocer TU marca para no ser generico. Rellena estos archivos con contenido real:

1. `data/knowledge/voice/tono-marca.md` — Parrafos de muestra reales de tu comunicacion
2. `data/knowledge/voice/ejemplos-copy-bueno.md` — 1-2 paginas de venta tuyas que funcionaron
3. `data/knowledge/retros/` — 1-2 retros de lanzamientos pasados (aunque sean de memoria)
4. Un framework en `data/knowledge/frameworks/` — revisa que el del tipo de funnel que uses aplique a tu caso

Sin estos archivos los agentes funcionan, pero producen contenido generico.

---

## Reglas para los agentes

### Idioma y tono
- Todo el contenido generado DEBE estar en espanol natural — no traducciones del ingles.
- Tutear al lector (usar "tu", no "usted") salvo que el brief indique lo contrario.
- Antes de escribir cualquier copy, leer `data/knowledge/voice/tono-marca.md` para capturar la voz real de la marca.
- Antes de escribir paginas de venta, leer tambien `data/knowledge/voice/ejemplos-copy-bueno.md`.

### Estructura de datos
- Cada lanzamiento vive en `data/launches/{launch_id}/`.
- El knowledge compartido vive en `data/knowledge/`. Consultar `data/knowledge/INDEX.md` para saber que archivo leer segun la tarea.
- Los agentes leen 2-4 archivos de knowledge relevantes, NO todo el directorio. INDEX.md es el mapa.

### Convenciones
- Moneda por defecto: USD (ajustable en el brief)
- Fechas en formato ISO (YYYY-MM-DD)
- IDs de lanzamiento: formato `{YYYY-MM}-{slug}` (ej: `2026-05-curso-marketing`)
- Los archivos JSON usan snake_case para las keys

### Flujo de lanzamiento
El comando `/nuevo-lanzamiento` guia el flujo completo con checkpoints humanos:
1. Brief → 2. Estrategia (ICP + funnel) → 3. Copy → 4. Emails → 5. Social → 6. Ads → 7. Paquete final

### Regla de skills
Una skill es un procedimiento que un experto repetiria identico. Si requiere criterio creativo, es trabajo de agente, no skill.

### Aprendizaje compuesto
Tras cada lanzamiento, usar `/cerrar-lanzamiento` para generar retro en `data/knowledge/retros/`. Los futuros lanzamientos leen retros de productos similares.
