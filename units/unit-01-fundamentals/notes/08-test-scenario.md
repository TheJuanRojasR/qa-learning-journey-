# Test Scenario

Estas notas reinician el concepto y se limitan a la diferencia entre `test objective` y `test scenario`.

## Definition

Un `test scenario` es una descripción breve y de alto nivel de una situación o flujo concreto en el que se examina un `test objective`. Describe el contexto relevante; no expresa el propósito de la prueba.

La pregunta para identificarlo es: **¿en qué situación concreta comprobaré la pregunta del objetivo?**

Un `test objective` no es necesariamente copiar la regla del requisito: expresa el propósito o la pregunta contestable que orienta la prueba.

**Alcance:** los equipos no usan el término de forma idéntica; aquí significa una situación o flujo de alto nivel. En un proyecto real, confirma la plantilla del equipo.

## Objective vs Scenario

| | `test objective` | `test scenario` |
|---|---|---|
| Pregunta que responde | ¿Qué quiero averiguar o comprobar? | ¿En qué situación lo voy a comprobar? |
| Qué describe | El propósito o la pregunta de la prueba | El contexto relevante: quién participa, qué estado importa y qué ocurre |
| Ejemplo | ¿El sistema impide crear un préstamo si el activo está en mantenimiento? | Un administrador autorizado intenta solicitar el préstamo de un activo en mantenimiento. |
| Relación | Es la pregunta que se quiere responder | Es una situación concreta donde se examina esa pregunta |

**Un objetivo puede examinarse en varias situaciones.** La pregunta puede seguir igual mientras cambian condiciones relevantes de la situación.

## Rules

1. **Mantén la situación conectada con el objetivo.** Si el objetivo pregunta por préstamos de activos en mantenimiento, «un usuario inicia sesión» no basta: no incluye la condición de mantenimiento.
2. **Incluye solo condiciones relevantes.** Puedes preguntarte quién participa, qué estado importa y qué ocurrió antes. Ejemplo: «administrador autorizado + activo en mantenimiento + intento de préstamo». No necesitas incluir los tres datos siempre.
3. **No confundas un dato distinto con otra situación.** Cambiar solo el identificador del activo normalmente no crea otro escenario: A-14 y A-15 tienen el mismo estado y condiciones. Cambiar `Available` por `Maintenance` sí cambia una condición relevante.
4. **No inventes permisos.** Si el requisito confirma que solo un administrador puede prestar, usa un administrador autorizado. Un intento de un instructor podría comprobar el permiso del rol, no la regla de mantenimiento.
5. **Clasifica por la función de la frase, no por el verbo.** «Un administrador intenta prestar un activo en mantenimiento» es un escenario; «¿el sistema bloquea ese préstamo?» es la pregunta objetivo.

## Worked Example

**Supuesto de práctica — no confirmado como requisito real de SENA:** el sistema no permite crear un préstamo cuando el estado del activo es `Maintenance`; un administrador tiene permiso para crear préstamos.

- **`test objective`:** «¿El sistema impide crear un préstamo cuando el activo está en mantenimiento?»
- **`test scenario` 1:** «Un administrador autorizado intenta prestar un activo cuyo estado actual es `Maintenance`.»
- **`test scenario` 2:** «Un administrador autorizado agrega un activo en `Maintenance` a una solicitud de préstamo por lote» (solo si la aplicación permite préstamos por lote).

En ambos escenarios se examina la misma pregunta. Cambia la situación relevante: un préstamo individual frente a uno por lote.

## Common Errors

| ❌ Confusión | ✅ Corrección | Por qué |
|---|---|---|
| «Un instructor intenta prestar...» es un objetivo porque contiene una acción | Es un escenario si describe las condiciones del intento; el objetivo pregunta qué se quiere comprobar | La acción forma parte de la situación; no expresa por sí sola el propósito de la prueba |
| «¿El sistema bloquea un préstamo cuando el activo está en mantenimiento?» es un escenario | Es un `test objective`: pregunta qué se quiere averiguar | Describe qué se quiere averiguar, no bajo qué condiciones se examina |
| El activo A-14 y el activo A-15 son dos escenarios diferentes | Normalmente son la misma situación con identificadores distintos | El identificador no cambia la condición relevante, salvo que tenga un efecto propio |
| «Solo el administrador puede prestar» se añade sin confirmarlo | Verifica el requisito o márcalo como supuesto | Una regla añadida puede cambiar qué comportamiento se está comprobando |

## My Examples, Corrected

| Mi ejemplo | Ajuste | Motivo |
|---|---|---|
| «Un instructor intenta prestar un elemento que está en inventario» — clasificado como objetivo | La frase describe una situación, así que su forma es de `test scenario`; pero `inventario` no coincide con el objetivo sobre `Maintenance` | El estado descrito no permite comprobar la regla de mantenimiento |
| «Un administrador intenta prestar un activo que está en mantenimiento» | Es un `test scenario` para el supuesto de práctica si el administrador está autorizado | Describe quién intenta qué y el estado del activo; no expresa la pregunta que se quiere responder |

En la aplicación real, el rol autorizado debe confirmarse con sus requisitos; el ejemplo anterior es un supuesto didáctico.

## Closing Rule

**`test objective` = qué quiero averiguar. `test scenario` = en qué situación concreta lo averiguo.** Primero identifica la pregunta; después describe las condiciones relevantes donde la examinas.
