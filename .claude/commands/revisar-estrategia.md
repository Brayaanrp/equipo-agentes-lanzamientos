# Revisar Estrategia

Carga la estrategia de un lanzamiento existente y permite iterar sobre ella.

## Instrucciones

1. Pregunta al usuario el `launch_id` del lanzamiento que quiere revisar. Si no lo saben, lista las carpetas en `data/launches/` para que elijan.

2. Lee los siguientes archivos:
   - `data/launches/{launch_id}/brief.json`
   - `data/launches/{launch_id}/icp.json`
   - `data/launches/{launch_id}/strategy.json`
   - `data/launches/{launch_id}/funnel.json`

3. Presenta un resumen de la estrategia actual:
   - ICP: dolor principal, deseo principal, nivel de awareness
   - Posicionamiento: USP, promesa, angulo
   - Funnel: tipo, etapas, lead magnet
   - Oferta: producto + bonos + precio + garantia
   - Timeline: fechas clave

4. Pregunta: "Que quieres ajustar?"

5. Segun lo que el usuario quiera cambiar, invoca al agente **estratega** con instrucciones especificas de que revisar. Pasa el contexto completo del lanzamiento + la instruccion de revision.

6. Muestra los cambios realizados y pide confirmacion.

7. Repite hasta que el usuario este satisfecho.

## Versionado

Antes de sobrescribir cualquier archivo (icp.json, strategy.json, funnel.json), crea una copia de respaldo:
- Cuenta cuantas versiones `.v{N}` existen del archivo (ej: `strategy.v1.json`, `strategy.v2.json`)
- Copia el archivo actual a `{nombre}.v{N+1}.{extension}`
- Solo guarda la version inmediatamente anterior, no todas las intermedias
- Informa al usuario: "Version anterior guardada como {nombre}.v{N}.{extension}"

## Nota
Si los cambios en la estrategia afectan al copy, emails, social o ads ya generados, avisa al usuario: "Este cambio en la estrategia puede requerir regenerar [los entregables afectados]. Quieres que los actualice?"
