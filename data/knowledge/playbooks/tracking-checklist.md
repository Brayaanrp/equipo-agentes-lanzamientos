# Checklist de Tracking y Analytics

Que medir en cada lanzamiento, donde medirlo, y cuando revisarlo. Sin tracking no hay retro, y sin retro no hay aprendizaje compuesto.

---

## Antes del lanzamiento (configurar)

### Pixel y eventos
- [ ] Meta Pixel instalado y verificado
- [ ] Eventos configurados:
  - `Lead` — registro a webinar/lead magnet
  - `ViewContent` — visita a pagina de venta
  - `InitiateCheckout` — inicia checkout
  - `Purchase` — compra completada (con valor)
- [ ] Google Analytics 4 (si aplica) con eventos equivalentes
- [ ] Dominio verificado en Meta Business Manager

### UTMs
Formato estandar para todos los links:
```
utm_source=   [meta, google, email, instagram, tiktok, youtube]
utm_medium=   [paid, organic, email, social]
utm_campaign= [launch_id] (ej: 2026-05-domina-instagram)
utm_content=  [identificador del creativo/email] (ej: email_launch_d1, ad_tofu_hook1)
```
- [ ] UTMs en todos los links de emails
- [ ] UTMs en todos los links de ads
- [ ] UTMs en links de bio/stories/posts

### Email
- [ ] Segmentos creados en la plataforma de email:
  - Lista completa
  - Registrados (webinar/lead magnet)
  - Compradores
  - No compradores
  - Carrito abandonado
- [ ] Automatizaciones activadas (pre-launch, launch, cart abandonment, post-compra)
- [ ] Tags de comportamiento configurados (opened_cart, clicked_sales_page, etc.)

---

## Durante el lanzamiento (monitorear diario)

### Metricas de email (revisar cada manana)
| Metrica | Alerta si | Accion |
|---------|-----------|--------|
| Open rate | < 25% | Revisar subject lines, probar re-envio |
| CTR | < 3% | Revisar CTA, copy del email |
| Unsubscribe rate | > 1% por envio | Reducir frecuencia o revisar tono |
| Bounce rate | > 5% | Limpiar lista |

### Metricas de ads (revisar cada 12h durante launch)
| Metrica | TOFU objetivo | MOFU objetivo | BOFU objetivo |
|---------|--------------|---------------|---------------|
| CPM | < $10 | < $15 | < $25 |
| CPC | < $1 | < $2 | < $3 |
| CTR | > 1.5% | > 2% | > 3% |
| CPL | - | Segun ticket | - |
| CPA | - | - | < 30% del ticket |
| ROAS | - | - | > 3x |

**Regla**: No tocar un ad set hasta tener al menos 50 conversiones o $50 gastados.

### Metricas de social (revisar diario)
| Metrica | Que indica |
|---------|-----------|
| Engagement rate | > 3% = contenido resonando |
| Saves | Alto valor percibido del contenido |
| Shares | Contenido viral/referible |
| DMs recibidos | Interes de compra (responder < 2h) |
| Story views vs followers | > 10% = buena tasa |

### Metricas de funnel (revisar cada 6h en dias clave)
| Etapa | Metrica | Donde medirlo |
|-------|---------|---------------|
| Trafico → Registro | Conversion opt-in | Landing page analytics |
| Registro → Asistencia | Show-up rate | Plataforma webinar o email opens |
| Asistencia → Pagina venta | Click-through | UTMs + analytics |
| Pagina venta → Checkout | Inicio checkout | Pixel InitiateCheckout |
| Checkout → Compra | Conversion final | Pixel Purchase + plataforma pago |

---

## Despues del lanzamiento (para la retro)

### Recopilar para `/cerrar-lanzamiento`
- [ ] Revenue total (bruto)
- [ ] Unidades vendidas
- [ ] Reembolsos / devoluciones (cantidad y %)
- [ ] Revenue neto (bruto - reembolsos)
- [ ] Leads generados (registros totales)
- [ ] Tasa de conversion (leads → compra)
- [ ] CPA promedio (gasto ads / unidades vendidas)
- [ ] ROAS (revenue / gasto ads)
- [ ] Email open rate promedio (por secuencia: pre-launch, launch, cart abandonment)
- [ ] Email CTR promedio (por secuencia)
- [ ] Mejor email (subject line + open rate + CTR)
- [ ] Peor email (subject line + open rate + CTR)
- [ ] Mejor ad (hook + CTR + conversiones)
- [ ] Peor ad (hook + CTR + gasto sin conversion)
- [ ] Engagement social destacado (post con mas interaccion)

### Dashboard recomendado

Google Sheets con 4 pestanas:

1. **Resumen**: Revenue vs objetivo, unidades vs objetivo, ROAS, CPA
2. **Email**: Open rate y CTR por email, por secuencia. Grafico de tendencia.
3. **Ads**: Gasto, CPL, CPA, ROAS por campana y por dia. Grafico de gasto acumulado vs revenue.
4. **Funnel**: Conversion por etapa. Grafico de embudo con % de caida.

---

## Referencia rapida: donde vive cada metrica

| Fuente | Metricas |
|--------|----------|
| Meta Ads Manager | CPM, CPC, CTR, CPL, CPA, ROAS, frecuencia, alcance |
| Google Ads | CPC, CTR, conversiones, quality score |
| Plataforma de email (Mailchimp, ConvertKit, ActiveCampaign) | Open rate, CTR, unsubscribes, bounces, por email |
| Google Analytics 4 | Trafico por fuente, eventos, conversiones, tiempo en pagina |
| Plataforma de pago (Stripe, Hotmart, etc.) | Ventas, reembolsos, revenue neto, payment plans |
| Plataforma de webinar (si aplica) | Registros, asistencia, duracion promedio, engagement |
