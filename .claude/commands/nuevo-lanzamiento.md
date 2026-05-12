# Nuevo Lanzamiento

Flujo guiado para crear un lanzamiento digital completo desde cero. Ejecuta fase por fase con checkpoints humanos.

## Fase 0: Recopilar Brief

Pregunta al usuario la siguiente informacion para construir el brief. Si falta algo, pregunta antes de avanzar:

1. **Nombre del producto** (ej: "Curso Domina Instagram")
2. **Tipo de producto** (curso, membresia, masterclass, taller, mentoria)
3. **Descripcion breve** (1-2 frases de que es y que resultado da)
4. **Precio** (en USD, o moneda local si especifican)
5. **Plan de pago** (pago unico, cuotas — cuantas y de cuanto)
6. **Publico objetivo** (descripcion en palabras del usuario)
7. **Tipo de funnel preferido** (webinar, VSL, PLF, challenge, o "no se")
8. **Fecha de apertura de carrito** (YYYY-MM-DD)
9. **Fecha de cierre de carrito** (YYYY-MM-DD)
10. **Inicio del pre-lanzamiento** (YYYY-MM-DD, o "2 semanas antes" etc.)
11. **Canales disponibles** (email, Instagram, Facebook, YouTube, TikTok, otros)
12. **Presupuesto de ads** (en USD, o "no hay presupuesto de ads")
13. **Meta de revenue** (cuanto quieren facturar)
14. **Meta de unidades** (cuantas ventas)
15. **Tamano de lista de email** (cuantos suscriptores tienen)
16. **Competidores conocidos** (nombres o URLs)
17. **USP / que lo diferencia** (por que alguien eligiria esto sobre la competencia)

Una vez recopilada la informacion:

1. Genera el `launch_id` con formato `{YYYY-MM}-{slug}` (ej: `2026-06-domina-instagram`)
2. Crea la carpeta `data/launches/{launch_id}/` y subcarpetas: `copy/`, `emails/`, `social/`, `ads/`, `analytics/`
3. Guarda `data/launches/{launch_id}/brief.json` con toda la informacion estructurada

## Fase 1: Estrategia

Invoca al agente **estratega** pasandole el launch_id.

Espera a que complete y luego muestra al usuario un resumen de:
- ICP (perfil de cliente ideal)
- Tipo de funnel recomendado y por que
- Estrategia de oferta (stack de valor)
- Timeline del lanzamiento

**CHECKPOINT**: Pregunta al usuario: "Este es el ICP y la estrategia. Quieres ajustar algo antes de continuar con el copy?"

No avances hasta que el usuario apruebe.

## Fase 2: Copywriting

Invoca al agente **copywriter** pasandole el launch_id.

Espera a que complete y muestra al usuario:
- Headline principal y 3 variantes
- Estructura de la pagina de ventas (resumen de secciones)
- CTA principal

**CHECKPOINT**: Pregunta al usuario: "Este es el copy principal. Quieres ajustar algo?"

No avances hasta que el usuario apruebe.

## Fase 3: Email Marketing

Invoca al agente **email-marketer** pasandole el launch_id.

Muestra resumen:
- Numero de emails por secuencia
- Subject lines de los emails clave (apertura, cierre, etc.)

**CHECKPOINT**: Pregunta al usuario: "Estas son las secuencias de email. Quieres ajustar algo antes de continuar con social media?"

No avances hasta que el usuario apruebe.

## Fase 4: Social Media

Invoca al agente **social-media** pasandole el launch_id.

Muestra resumen:
- Numero total de piezas de contenido
- Distribucion por plataforma y formato
- Primera semana del calendario

**CHECKPOINT**: Pregunta al usuario: "Este es el calendario de contenido. Quieres ajustar algo antes de continuar con ads?"

No avances hasta que el usuario apruebe.

## Fase 5: Publicidad

Invoca al agente **ads-specialist** pasandole el launch_id.

Muestra resumen:
- Estructura de campanas
- Distribucion de presupuesto
- Top 3 hooks de anuncios

**CHECKPOINT**: Pregunta al usuario: "Esta es la estructura de campanas. Quieres ajustar algo antes de generar el paquete final?"

No avances hasta que el usuario apruebe.

## Fase 6: Paquete Final

Genera un resumen ejecutivo del lanzamiento completo:

```
# Paquete de Lanzamiento: [Nombre del producto]
## Launch ID: {launch_id}

### Resumen
- Producto: ...
- Precio: ...
- Funnel: ...
- Fechas: pre-launch [fecha] → apertura [fecha] → cierre [fecha]

### Entregables generados
- [ ] ICP: data/launches/{id}/icp.json
- [ ] Estrategia: data/launches/{id}/strategy.json
- [ ] Funnel: data/launches/{id}/funnel.json
- [ ] Pagina de ventas: data/launches/{id}/copy/landing_page.md
- [ ] Script VSL/Webinar: data/launches/{id}/copy/vsl_script.md
- [ ] Pagina de captura: data/launches/{id}/copy/opt_in_page.md
- [ ] Emails pre-launch: data/launches/{id}/emails/pre_launch.json
- [ ] Emails launch: data/launches/{id}/emails/launch.json
- [ ] Emails cart abandonment: data/launches/{id}/emails/cart_abandonment.json
- [ ] Calendario social: data/launches/{id}/social/calendar.json
- [ ] Campanas ads: data/launches/{id}/ads/meta_campaigns.json

### Proximos pasos
1. Rellenar data/knowledge/voice/tono-marca.md si no esta hecho
2. Revisar cada entregable y hacer ajustes
3. Implementar en las plataformas (Mailchimp, Meta Ads, etc.)
4. Tras el lanzamiento: ejecutar /cerrar-lanzamiento {id}
```

Guarda este resumen en `data/launches/{launch_id}/launch_package.md`.
