# Testing fundamentals

## Test Objective

> Objective: Poder mirar cualquier situación y escribir el objetivo de prueba como una **pregunta contestable**.

### Definition

El `test objective` es **la razón o el propósito por el cual hago una prueba**. Responde a:

> **¿Qué quiero lograr o demostrar al ejecutar esta prueba?**

El atajo: **es la pregunta que quiero poder contestar cuando termino de probar.**

| | |
|---|---|
| **Pregunta** | "¿Un instructor dado de baja puede dejar elementos sin responsable?" |
| **Objetivo** | "Verificar que al dar de baja a un instructor sus elementos pendientes no queden sin responsable." |
| **Evidencia** | "Lo probé con 3 elementos: quedaron sin responsable." |

Y mi prueba termina cuando puedo contestar esa pregunta con evidencia — no cuando "ya probé esa pantalla".

### The Formula

```
[Verbo] + [qué componente o flujo] + [bajo qué condición o regla]
```

### The Puzzle

| | | |
|---|---|---|
| **Objetivo** | ¿**Para qué**? | Quiero saber si al dar de baja a un instructor sus elementos quedan sin responsable |
| **Escenario** | ¿**Qué**? | La baja de un instructor con elementos pendientes |
| **Caso** | ¿**Cómo**? | Doy de baja al instructor X, que tiene 3 elementos, y miro qué pasa |

### The Rule I Keep

> **Un buen objetivo nombra un RIESGO, no una funcionalidad.**
> Si el sistema hace lo que mi objetivo dice… ¿me alegro? Entonces está bien escrito.

### Where the Risk Comes From: the FEAR Generator

> **No escribo la función: escribo mi miedo.** (miedo = `risk`)

1. Escribo el miedo en negativo: "que la cuenta bloqueada igual deje entrar".
2. Lo convierto en objetivo nombrando al villano:
   - Verbo guardián: "…que **impida / rechace / no permita** [el mal]".
   - Condición que lo caza: "…que se conserve **al reconectar**", "…que reciba `obsoleto` **a los 6 meses**".
3. Lo paso por los 3 tests: ¿según qué? · ¿me alegro o me preocupo? · ¿es copia del requisito?

Ejemplo: miedo "que al reconectar el saldo se reinicie a 100" → "Verificar que el saldo de monedas se conserve exactamente como estaba después de reconectar a la partida."

### The Conversion, Step by Step (fear → objective)

1. **Escena** (en primera persona): "Estoy inactivo un rato, vuelvo… y todavía puedo seguir."
2. **La niego**: "…y ya NO puedo seguir: me pide autenticarme de nuevo."
3. **La paso a la fórmula**: "Verificar que al volver tras 15 minutos de inactividad, la app no permita seguir sin autenticarse."

**Tests de control:**

- Si mi objetivo **le puede dar pass a un sistema roto**, no me sirve. ("Que la sesión se cierre" deja pasar el bug del botón "atrás"; "que no permita seguir" lo caza.)
- **La puerta:** "giré la llave" (lo que el sistema dice que hizo) ≠ "empujo y no se abre" (lo que compruebo). Escribo mi objetivo con la puerta que no se abre.
- El objetivo sale de **mi miedo**, no de la descripción de la función. Si hay un requisito al lado, lo ignoro para escribir el objetivo.

> [!NOTE] Mi miedo ya estaba bien; lo que me faltaba era usarlo para escribir el objetivo.

### Verbs

**De acción (abren el objetivo):** `Verificar` · `Validar` · `Confirmar` · `Evaluar` · `Demostrar`

**Guardianes (bloquean el mal):** `impida` · `rechace` · `no permita` · `no deje` · `deje de funcionar` · `no aparezca` · `no se dupliquen`

**Fórmula del objetivo guardián:** "[Verbo] que [guardián] [el mal]" — "…que **no permita ingresar** a más de 8 jugadores".

### My Exercises

| # | Situación | Miedo | Mi respuesta | Versión final |
|---|---|---|---|---|
| 1 | Mochila abierta al cambiar de personaje | Los objetos se duplican | "Validar que al abrir el inventario y cambie de personaje no permita la duplicación de objetos" | "Validar que al abrir el inventario y cambiar de personaje no se dupliquen los objetos" |
| 2 | Silenciar a un jugador en el chat | Sus mensajes siguen apareciendo | "Validar que cuando un jugador sea silenciado en el chat no se permita la visualización de sus mensajes en pantalla" | "Validar que al silenciar a un jugador, sus mensajes no se muestren en el chat" |
| 3 | Roles de la app | Un INSTRUCTOR ve el panel de ADMIN | "Verificar que los usuarios con rol de Instructor no tengan permitido la visualización del panel del ADMIN" | "Validar que un usuario con rol INSTRUCTOR no pueda ver el panel de ADMIN" |
| 4 | Progreso del juego | Se pierde al cerrar y reabrir | "Validar que al momento de cerrar y volver a abril el juego, no permita perder el progreso de la ultima partida" | "Validar que al cerrar y volver a abrir el juego no se pierda el progreso de la última partida" |
| 5 | Cambio de contraseña | La contraseña vieja sigue sirviendo para entrar | "Verificar que al cambiar la contraseña un usuario, esta deje de funcionar al tratar de entrar" | "Verificar que cuando un usuario cambia su contraseña, la contraseña anterior deje de funcionar para entrar" |
| 6 | Sistema anti-trampas | Expulsa a un jugador que no hizo nada malo | "Validar que el sistema no permita la expusion de un jugador en partida, cuando no haya roto ninguna regla" | "Validar que el sistema no expulse de la partida a un jugador que no haya roto ninguna regla" |
| 7 | Eliminar un elemento | Sigue apareciendo en las búsquedas | "Verificar que al eliminar un elemento del inventario. El elemento no aparezca en los resultados de busqueda" | "Verificar que al eliminar un elemento del inventario, el elemento eliminado no aparezca en los resultados de búsqueda" |
| 8 | Salas de partida (máx. 8 jugadores) | Permite unirse a más jugadores | "Verificar que las salas de partidas no permitan ingresar a más de 8 jugadores por partida" | "…que no permitan ingresar a más de 8 jugadores (ojo: el 8.º SÍ debe poder entrar; el 9.º, bloqueado por cualquier vía)" |
