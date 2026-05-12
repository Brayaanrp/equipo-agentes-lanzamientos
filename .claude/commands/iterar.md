# Iterar

Permite rehacer una pieza especifica de un lanzamiento sin regenerar todo. Util para ajustar un email, reescribir headlines, cambiar una campana de ads, etc.

## Instrucciones

1. Pregunta al usuario el `launch_id`. Si no lo saben, lista las carpetas en `data/launches/` para que elijan.

2. Pregunta que fase quiere iterar:
   - **Estrategia**: ICP, posicionamiento, funnel, oferta
   - **Copy**: pagina de ventas, opt-in, VSL/webinar, headlines/hooks
   - **Emails**: pre-launch, launch, cart abandonment, post-compra, downsell
   - **Social**: calendario, posts especificos, contenido por plataforma
   - **Ads**: campanas Meta, campanas Google, audiencias, creativos

3. Pregunta que pieza especifica quiere modificar. Ejemplos:
   - "Reescribe el email 3 de la secuencia de pre-launch"
   - "Dame 5 headlines alternativos mas agresivos"
   - "Cambia la campana BOFU para enfocarse mas en testimonios"
   - "Reescribe la seccion de bonos de la landing page"

4. Pregunta que quiere cambiar (instruccion libre del usuario).

5. Lee el contexto completo del lanzamiento:
   - `data/launches/{launch_id}/brief.json`
   - `data/launches/{launch_id}/icp.json`
   - `data/launches/{launch_id}/strategy.json`
   - `data/launches/{launch_id}/funnel.json`
   - El archivo especifico que se va a modificar

6. Invoca al agente correspondiente segun la fase:
   - Estrategia → **estratega**
   - Copy → **copywriter**
   - Emails → **email-marketer**
   - Social → **social-media**
   - Ads → **ads-specialist**

   Pasale el contexto completo + la instruccion especifica de revision. Dejale claro que solo debe modificar la pieza solicitada, no regenerar todo.

7. Muestra el resultado al usuario y pide confirmacion.

8. Si el usuario aprueba, guarda solo la pieza modificada en su archivo correspondiente.

## Versionado

Antes de sobrescribir cualquier archivo, crea una copia de respaldo:
- Cuenta cuantas versiones `.v{N}` existen del archivo (ej: `launch.v1.json`, `launch.v2.json`)
- Copia el archivo actual a `{nombre}.v{N+1}.{extension}`
- Solo guarda la version inmediatamente anterior, no todas las intermedias
- Informa al usuario: "Version anterior guardada como {nombre}.v{N}.{extension}"

## Nota

Si la pieza modificada afecta la coherencia de otros entregables (ej: cambiar la estrategia afecta al copy), avisa al usuario: "Este cambio puede afectar a [entregables afectados]. Quieres que los regenere tambien?"
