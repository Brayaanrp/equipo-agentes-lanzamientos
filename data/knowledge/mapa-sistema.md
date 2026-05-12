# Mapa del Sistema: Equipo de Lanzamiento Digital

Este documento explica visualmente como funciona el sistema, que hace cada pieza, y por que mejora con cada lanzamiento.

---

## La cadena completa

```
TU BRIEF ──────────────────────────────────────────────────────────
  17 preguntas: producto, precio, audiencia, fechas, canales...
  Se guarda en: data/launches/{id}/brief.json
───────────────────────────────────────────────────────────────────

    ┌─────────────────────────────────────────────────────────┐
    │                    CAPA DE KNOWLEDGE                    │
    │  (Lo que hace al sistema inteligente, no generico)      │
    │                                                         │
    │  frameworks/     Metodos probados (PLF, VSL, webinar,   │
    │                  challenge, evergreen)                   │
    │  voice/          TU tono real + copy que funciono        │
    │  playbooks/      Paso a paso (72h carrito, objeciones)  │
    │  retros/         Numeros reales de lanzamientos pasados  │
    │                                                         │
    │  Cada agente consulta INDEX.md y carga solo 2-4         │
    │  archivos relevantes. No lee todo.                      │
    └──────────────────────┬──────────────────────────────────┘
                           │ alimenta a todos los agentes
                           ▼
    ┌──────────────────────────────────────────────────────────┐
    │  FASE 1: ESTRATEGIA                          [Opus 4.6] │
    │  Agente: Estratega                                       │
    │                                                          │
    │  Lee: brief + frameworks + retros similares              │
    │  Produce: ICP (cliente ideal) + estrategia + funnel      │
    │                                                          │
    │  > Analiza mercado y competencia                         │
    │  > Define posicionamiento y oferta                       │
    │  > Elige tipo de funnel con razonamiento                 │
    │  > Proyecta KPIs (conservador/esperado/optimista)        │
    └──────────────────────┬───────────────────────────────────┘
                           │
                    [ TU APROBACION ]
                           │
    ┌──────────────────────▼───────────────────────────────────┐
    │  FASE 2: COPY                             [Sonnet 4.6]  │
    │  Agente: Copywriter                                      │
    │                                                          │
    │  Lee: ICP + estrategia + voz de marca + ejemplos         │
    │  Produce: pagina de venta + opt-in + VSL/webinar         │
    │           + thank you + 10 headlines + 5 hooks            │
    │                                                          │
    │  > Escribe en tu tono real (no generico)                 │
    │  > Usa formulas de headlines probadas                    │
    │  > Pain → agitacion → solucion → transformacion         │
    │  > Beneficios especificos, no vagos                      │
    └──────────────────────┬───────────────────────────────────┘
                           │
                    [ TU APROBACION ]
                           │
    ┌──────────────────────▼───────────────────────────────────┐
    │  FASE 3: EMAILS                           [Sonnet 4.6]  │
    │  Agente: Email Marketer                                  │
    │                                                          │
    │  Lee: estrategia + funnel + copy + playbooks             │
    │  Produce: 5 secuencias completas                         │
    │    - Pre-launch (5-8 emails)                             │
    │    - Launch/carrito abierto (7-10 emails)                │
    │    - Cart abandonment (3-4 emails)                       │
    │    - Post-compra (5 emails)                              │
    │    - Downsell no-compradores (3 emails)                  │
    │                                                          │
    │  > Cada email: subject A/B + preview + body + CTA        │
    │  > Timing + segmento + tags de automatizacion            │
    └──────────────────────┬───────────────────────────────────┘
                           │
                    [ TU APROBACION ]
                           │
    ┌──────────────────────▼───────────────────────────────────┐
    │  FASE 4: SOCIAL                           [Sonnet 4.6]  │
    │  Agente: Social Media Manager                            │
    │                                                          │
    │  Lee: ICP + estrategia + hooks del copywriter            │
    │  Produce: calendario completo + posts individuales       │
    │    - Instagram (feed, stories, reels)                    │
    │    - Facebook, TikTok, YouTube                           │
    │    - Descripcion visual para disenador                   │
    │                                                          │
    │  > Contenido NATIVO por plataforma                       │
    │  > 70% educativo / 20% entretenimiento / 10% venta      │
    └──────────────────────┬───────────────────────────────────┘
                           │
                    [ TU APROBACION ]
                           │
    ┌──────────────────────▼───────────────────────────────────┐
    │  FASE 5: ADS                              [Sonnet 4.6]  │
    │  Agente: Ads Specialist                                  │
    │                                                          │
    │  Lee: estrategia + funnel + hooks + objeciones           │
    │  Produce: campanas Meta + Google completas               │
    │    - TOFU (awareness) → MOFU (leads) → BOFU (ventas)    │
    │    - Audiencias frias/tibias/calientes                   │
    │    - Creativos con copy + descripcion visual             │
    │    - Presupuesto por fase + KPIs objetivo                │
    │                                                          │
    │  > Minimo 3 hooks x 2 angulos x 2 formatos              │
    │  > UTMs en todos los enlaces                             │
    └──────────────────────┬───────────────────────────────────┘
                           │
                    [ TU APROBACION ]
                           │
                           ▼
    ┌──────────────────────────────────────────────────────────┐
    │  PAQUETE FINAL                                           │
    │  launch_package.md — resumen con checklist               │
    │  EXPORT.md — documento unico con todo                    │
    └──────────────────────┬───────────────────────────────────┘
                           │
                    (ejecutas el lanzamiento)
                           │
                           ▼
    ┌──────────────────────────────────────────────────────────┐
    │  RETRO (/cerrar-lanzamiento)                             │
    │                                                          │
    │  Capturas numeros reales:                                │
    │    revenue, unidades, leads, conversion, CPA, ROAS...    │
    │  + Que funciono, que fallo, que cambiar                  │
    │                                                          │
    │  Se guarda en: data/knowledge/retros/                    │
    │                                                          │
    │  ┌────────────────────────────────────────────────────┐  │
    │  │  EFECTO COMPUESTO: El proximo lanzamiento similar  │  │
    │  │  lee esta retro automaticamente. En 3-5 lanza-     │  │
    │  │  mientos el sistema es exponencialmente mejor.     │  │
    │  │                                                    │  │
    │  │  Launch 1 → retro → Launch 2 lee retro 1           │  │
    │  │  Launch 2 → retro → Launch 3 lee retros 1+2        │  │
    │  │  ...cada vez mas inteligente                        │  │
    │  └────────────────────────────────────────────────────┘  │
    └──────────────────────────────────────────────────────────┘
```

---

## Las 6 skills (recetas reutilizables)

Los agentes invocan estas skills cuando las necesitan. Cada skill es un procedimiento paso a paso:

```
┌─────────────────────┐     ┌─────────────────────┐
│  headline-formulas  │     │  bonos-stack         │
│  10-15 headlines    │     │  Disena bonos que    │
│  por nivel de       │     │  justifican precio   │
│  awareness          │     │  y destruyen         │
│                     │     │  objeciones          │
│  Usado por:         │     │                      │
│  Copywriter, Ads    │     │  Usado por:          │
└─────────────────────┘     │  Copywriter,         │
                            │  Estratega            │
┌─────────────────────┐     └─────────────────────┘
│  estructura-vsl     │
│  Script VSL bloque  │     ┌─────────────────────┐
│  por bloque         │     │  framework-plf       │
│  (Jon Benson)       │     │  3 videos pre-launch │
│                     │     │  + emails + social   │
│  Usado por:         │     │  (Jeff Walker)       │
│  Copywriter         │     │                      │
│  (si funnel = VSL)  │     │  Usado por:          │
└─────────────────────┘     │  Copywriter, Social  │
                            │  (si funnel = PLF)   │
┌─────────────────────┐     └─────────────────────┘
│  email-sequence-    │
│  launch-7d          │     ┌─────────────────────┐
│  11 emails dia a    │     │  secuencia-cart-     │
│  dia para 7 dias    │     │  abandonment         │
│  de carrito         │     │  4 emails para       │
│                     │     │  recuperar carritos  │
│  Usado por:         │     │                      │
│  Email Marketer     │     │  Usado por:          │
│  (SIEMPRE)          │     │  Email Marketer      │
└─────────────────────┘     │  (SIEMPRE)           │
                            └─────────────────────┘
```

---

## Los 5 comandos

```
/nuevo-lanzamiento     Flujo completo: brief → 5 agentes → paquete final
/revisar-estrategia    Cargar lanzamiento existente, iterar sobre estrategia
/iterar                Rehacer una pieza especifica sin regenerar todo
/exportar-lanzamiento  Documento unico con todos los entregables
/cerrar-lanzamiento    Retro con numeros reales → alimenta knowledge
```

---

## Por que es potente (3 razones)

### 1. No es un agente generico
Cada agente es especialista y lee knowledge real (frameworks, tu voz, retros). El output es informado, no improvisado. Un copywriter que lee tu tono de marca y ejemplos de copy que funcionaron produce algo radicalmente diferente a uno que empieza de cero.

### 2. Cada agente construye sobre el anterior
El copywriter no inventa — lee la estrategia aprobada. El email marketer no improvisa — lee el copy aprobado. Y tu apruebas entre cada fase. El resultado: coherencia total desde el brief hasta el ultimo anuncio de Meta.

### 3. Mejora con cada lanzamiento
Las retros con numeros reales alimentan la knowledge base. El estratega del lanzamiento 5 sabe que los webinars de 60 min convirtieron mejor que los de 90, que los bonos de comunidad funcionaron mejor que los de templates, que los emails con historia personal tuvieron 2x mas apertura. Eso no lo tiene ningun copywriter o media buyer que empieza de cero.
