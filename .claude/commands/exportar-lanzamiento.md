# Exportar Lanzamiento

Empaqueta todos los entregables de un lanzamiento en un documento legible y navegable.

## Instrucciones

1. Pregunta al usuario el `launch_id`. Si no lo saben, lista las carpetas en `data/launches/`.

2. Lee todos los archivos del lanzamiento en `data/launches/{launch_id}/`.

3. Genera un documento unificado `data/launches/{launch_id}/EXPORT.md` con la siguiente estructura:

```markdown
# Lanzamiento: [Nombre del producto]
**Launch ID**: {launch_id}
**Fecha de exportacion**: {fecha actual}

---

## 1. Brief
[Resumen del brief en formato legible]

## 2. Perfil de Cliente Ideal (ICP)
[ICP formateado: demografia, psicografia, pain points, deseos, objeciones]

## 3. Estrategia
[Posicionamiento, funnel, timeline, oferta]

## 4. Copy
### Pagina de Ventas
[Contenido completo de landing_page.md]

### Pagina de Captura
[Contenido de opt_in_page.md]

### Script VSL/Webinar
[Contenido del script]

### Headlines y Hooks
[Lista de headlines y hooks]

## 5. Emails
### Pre-Lanzamiento ([N] emails)
[Subject lines + resumen de cada email]

### Lanzamiento ([N] emails)
[Subject lines + resumen de cada email]

### Cart Abandonment ([N] emails)
[Subject lines + resumen]

### Post-Compra ([N] emails)
[Subject lines + resumen]

## 6. Social Media
### Calendario
[Tabla con fecha, plataforma, formato, resumen]

### Contenido Destacado
[Las 5 piezas mas importantes completas]

## 7. Publicidad
### Campanas Meta
[Estructura, audiencias, presupuesto]

### Creativos Principales
[Top 5 anuncios con copy completo]

## 8. KPIs y Metricas Objetivo
[Tabla de metricas objetivo por canal]
```

4. Informa al usuario: "Exportacion completa en `data/launches/{launch_id}/EXPORT.md`. Puedes abrir este archivo para ver todo el lanzamiento en un solo documento."
