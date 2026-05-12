# Diseno de Bonos y Stack de Valor

Procedimiento para disenar bonos que escalen el valor percibido de la oferta y justifiquen el precio.

## Principio Central
Los bonos no son "extras". Son la respuesta a objeciones y aceleradores del resultado. Cada bono debe resolver un problema especifico que el ICP tiene y que el producto principal no cubre directamente.

## Paso 1: Identificar Gaps y Objeciones

Lee `icp.json` y `strategy.json`. Para cada objecion del ICP, pregunta:
- "Puedo crear un bono que elimine esta barrera?"
- "Que necesitan ADEMAS del producto principal para lograr el resultado?"

Gaps comunes:
- **Tiempo**: "No tengo tiempo" → Bono: Plantillas/templates/checklists listas para usar
- **Conocimiento previo**: "No se lo suficiente" → Bono: Curso introductorio/fundamentos
- **Implementacion**: "No se como empezar" → Bono: Guia de inicio rapido / plan de accion
- **Comunidad**: "Me siento solo en esto" → Bono: Acceso a grupo privado
- **Soporte**: "Y si me atasco?" → Bono: Sesiones de Q&A en vivo / soporte por X tiempo
- **Herramientas**: "No tengo las herramientas" → Bono: Acceso a software/tool por X meses

## Paso 2: Disenar cada Bono

Para cada bono:
```
Nombre: [Nombre atractivo — no generico. "Kit de Arranque Rapido" > "Materiales extra"]
Valor percibido: $[precio al que podrias venderlo por separado]
Formato: [PDF, video, plantilla, acceso, sesion en vivo, etc.]
Que resuelve: [objecion o gap especifico]
Por que es valioso solo: [1 frase de por que valdria $X independientemente]
```

## Paso 3: Ordenar el Stack de Valor

Orden de revelacion en la pagina de ventas / oferta:
1. **Producto principal** — lo que prometes y como lo entregas (modulos, duracion, formato)
2. **Bono de implementacion** — lo que acelera el resultado (plantillas, plan de accion)
3. **Bono de soporte** — lo que elimina el miedo al fracaso (grupo, Q&A, mentorias)
4. **Bono de resultado extra** — lo que da un resultado bonus (curso complementario, herramienta)
5. **Bono de urgencia** — solo disponible para los primeros N / esta semana (sesion 1:1, auditoria, etc.)

## Paso 4: Calcular el Anclaje de Precio

```
Producto principal:           $[valor]
+ Bono 1 ([nombre]):          $[valor]
+ Bono 2 ([nombre]):          $[valor]
+ Bono 3 ([nombre]):          $[valor]
+ Bono urgencia ([nombre]):   $[valor]
= Valor total:                $[suma]

Tu inversion hoy:             $[precio real]
Ahorro:                       $[suma - precio] ([porcentaje]% de descuento)
```

## Reglas para buenos bonos
1. **Maximo 4-5 bonos**. Mas de 5 diluye el valor y confunde. Mejor pocos y potentes.
2. **Cada bono tiene valor independiente**. Si no lo venderias por separado, no es bono — es parte del producto.
3. **Los valores deben ser creibles**. Si el curso vale $297, no pongas un PDF a $497. Ancla a precios de mercado reales.
4. **El bono de urgencia es el cierre**. Debe ser algo que genuinamente no van a poder obtener despues (sesion 1:1, auditoria personalizada, precio de lanzamiento).
5. **No regales el bono mas valioso**. Si tu mejor asset es la mentoria 1:1, eso puede ser el producto, no el bono.

## Output esperado
Documento con:
1. Lista de 3-5 bonos con nombre, valor, formato, y que resuelve
2. Stack de valor completo con anclaje de precio
3. Copy sugerido para cada bono (2-3 lineas de pitch)
