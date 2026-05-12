# Secuencia de Cart Abandonment (Carrito Abandonado)

Framework para crear 4 emails dirigidos a personas que llegaron al checkout pero no completaron la compra.

## Pre-requisito
Lee `data/knowledge/playbooks/objeciones-frecuentes.md` para las objeciones mas comunes.

## Contexto
Alguien que llega al checkout ya esta convencido al 80-90%. Lo que le frena suele ser:
1. Duda de ultimo momento ("y si no funciona?")
2. Precio ("es mucho dinero de golpe")
3. Distraccion (le interrumpieron, se le olvido)
4. Necesita "consultarlo" (excusa para ganar tiempo)

Los emails de cart abandonment NO son para convencer de cero — son para resolver el ultimo 10-20% de duda.

## Los 4 Emails

### Email 1: El Recordatorio Amable (1 hora despues)

**Objetivo**: Recuperar a los distraidos (los que simplemente se les olvido).

**Subject**: "Se te olvido algo?"
**Subject A/B**: "Tu inscripcion se quedo a medias" | "{{nombre}}, vuelve a donde lo dejaste"

**Tono**: Amable, sin presion, servicial.

**Estructura**:
```
Oye {{nombre}},

Vi que empezaste a inscribirte en [nombre del programa] 
pero no completaste el proceso.

A veces pasa — se cierra una pestana, suena el telefono, 
la vida interrumpe.

Si todavia quieres unirte, tu plaza sigue reservada aqui:
[LINK AL CHECKOUT]

Si tienes alguna duda, respondeme a este email y te ayudo.

[Firma]
```

**Longitud**: 50-80 palabras. No hace falta convencer.

---

### Email 2: La Objecion Principal (24 horas despues)

**Objetivo**: Destruir la objecion que les freno.

**Subject**: "La razon #1 por la que la gente no se inscribe (y por que no aplica en tu caso)"
**Subject A/B**: "Esto es lo que frena a la mayoria" | "Puedo ser honesto contigo?"

**Tono**: Empatico, directo, con evidencia.

**Estructura**:
```
{{nombre}},

La razon mas comun por la que alguien llega al checkout 
y no completa es: [objecion #1 del ICP — generalmente precio o miedo].

Lo entiendo. [Frase de validacion].

Pero dejame mostrarte por que [reframe de la objecion]:

[1 parrafo con evidencia: testimonio, ROI, garantia]

Ademas, recuerda que tienes [garantia: 30 dias, sin preguntas, etc.].
Tu riesgo es literalmente cero.

[LINK AL CHECKOUT]

[Firma]

PD: Si tu duda es otra, escribeme. Estoy aqui para ayudarte 
a tomar la mejor decision (incluso si es no inscribirte).
```

**Longitud**: 100-150 palabras.

---

### Email 3: La Urgencia (48 horas despues / o 24h antes del cierre)

**Objetivo**: Crear urgencia real para el que "lo esta pensando".

**Subject**: "No quiero que te lo pierdas"
**Subject A/B**: "Esto se cierra en [plazo]" | "Decision pendiente sobre [programa]"

**Tono**: Firme pero respetuoso. No desesperado.

**Estructura**:
```
{{nombre}},

Esto es rapido:

[Nombre del programa] cierra inscripciones el [fecha] a las [hora].

Lo que incluye:
- [Bullet 1: beneficio principal]
- [Bullet 2: bono destacado]
- [Bullet 3: garantia]

Precio: $[precio] (o [cuotas] de $[monto])

[LINK AL CHECKOUT]

Una vez que cierre, no se cuando volvere a abrir.
No quiero que te quedes con las ganas.

[Firma]
```

**Longitud**: 80-100 palabras. Escaneable, no prosa.

---

### Email 4: La Ultima Oportunidad (justo antes del cierre, 2-4h)

**Objetivo**: El empujon final para los que genuinamente quieren pero no actuan.

**Subject**: "Ultima oportunidad: cierro en [N] horas"
**Subject A/B**: "Esto es. Dentro o fuera." | "[N] horas para decidir"

**Tono**: Directo, sin adornos, respetuoso.

**Estructura**:
```
{{nombre}},

En [N] horas cierro las inscripciones de [programa].

Si quieres entrar: [LINK]
Si decidiste que no es para ti: lo respeto totalmente. 

Sin presion. Solo queria asegurarme de que no se 
te pasara por alto.

[Firma]
```

**Longitud**: 40-60 palabras. El email mas corto de todos.

---

## Reglas de la secuencia

1. **No enviar si ya compro**. Segmenta SIEMPRE excluyendo compradores.
2. **El email 1 es automatico** (1h post-abandono). Los demas siguen el calendario del lanzamiento.
3. **Si el carrito esta abierto menos de 3 dias**, comprimir: Email 1 (1h) → Email 2 (siguiente dia) → Email 4 (dia de cierre). Saltar el 3.
4. **No suenes desesperado**. Cada email ofrece una salida digna ("si no es para ti, lo respeto").
5. **El PD del email 2 es clave**. Abre la puerta a conversacion. Muchas ventas se cierran por reply.

## Output esperado
4 emails completos con subject + A/B, preview, body, CTA, dia/hora, segmento, y tags de automatizacion.
