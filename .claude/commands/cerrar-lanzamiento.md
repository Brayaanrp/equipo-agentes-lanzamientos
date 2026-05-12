# Cerrar Lanzamiento

Genera una retro del lanzamiento para alimentar el knowledge del equipo. Este es el mecanismo de aprendizaje compuesto — lo mas importante del sistema.

## Instrucciones

1. Pregunta al usuario el `launch_id` del lanzamiento a cerrar.

2. Lee el brief y la estrategia:
   - `data/launches/{launch_id}/brief.json`
   - `data/launches/{launch_id}/strategy.json`
   - `data/launches/{launch_id}/funnel.json`

3. Pide al usuario las metricas reales del lanzamiento:
   - **Revenue total**: cuanto se facturo
   - **Unidades vendidas**: cuantas ventas
   - **Leads generados**: cuantos suscriptores/registrados nuevos
   - **Tasa de conversion**: % de leads que compraron
   - **CPA** (coste por adquisicion): cuanto costo cada venta en ads
   - **ROAS** (return on ad spend): retorno por cada euro/dolar invertido en ads
   - **Tasa de apertura de emails**: promedio de open rate
   - **CTR de emails**: promedio de click-through rate
   - **Engagement en redes**: metricas destacadas
   - **Reembolsos/devoluciones**: cuantos y por que
   - (Si no tienen alguna metrica, salta esa)

4. Pregunta al usuario:
   - "Que funciono mejor de lo esperado?" (top 3)
   - "Que fallo o no cumplio expectativas?" (top 3)
   - "Que harias diferente la proxima vez?" (top 3)
   - "Hubo algun insight no obvio o sorpresa?"

5. Genera la retro en `data/knowledge/retros/{YYYY-MM}-{slug-producto}.md`:

```markdown
# Retro: [Nombre del producto]
**Fecha**: {fecha del lanzamiento}
**Tipo de funnel**: {webinar/VSL/PLF/challenge}
**Ticket**: ${precio}
**Duracion carrito abierto**: {N} dias

## Numeros Reales
| Metrica | Objetivo | Real | vs Objetivo |
|---------|----------|------|-------------|
| Revenue | $X | $Y | +/-% |
| Unidades | N | N | +/-% |
| Leads | N | N | +/-% |
| Conversion | X% | Y% | +/-pp |
| CPA | $X | $Y | +/-% |
| ROAS | Xx | Yx | +/-% |

## Que Funciono (Top 3)
1. [Lo que funciono y POR QUE funciono]
2. ...
3. ...

## Que Fallo (Top 3)
1. [Lo que fallo y POR QUE fallo]
2. ...
3. ...

## Que Cambiar (Top 3)
1. [Cambio concreto para el proximo lanzamiento]
2. ...
3. ...

## Insights No Obvios
[Observaciones sorprendentes o contraintuitivas]

## Contexto para Futuros Lanzamientos
[Resumen de 2-3 lineas que un agente pueda leer rapido para 
saber que aprender de este lanzamiento]
```

6. Actualiza `data/knowledge/INDEX.md`:
   - Anade una fila en la tabla de "Mapa de conocimiento" con formato: `Retro de [tipo producto] + [tipo funnel] | retros/{archivo}.md`
   - Si la retro contiene un aprendizaje que deberia ser un playbook nuevo o actualizar uno existente, sugierelo al usuario.

7. Confirma: "Retro guardada en `data/knowledge/retros/{archivo}.md`. El proximo lanzamiento similar consultara automaticamente estos aprendizajes."
