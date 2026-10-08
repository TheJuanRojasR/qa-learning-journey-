# Testing fundamentals

## Error - Defect - Failure

> Objective: Poder desarmar cualquier bug en sus tres piezas y decir DÓNDE vive cada una.

- `error` (o `mistake`): Acción humana que produce un resultado incorrecto. Vive en las PERSONAS.
- `defect` (o `fault`, o `bug`): Imperfección que queda EN UN ARTEFACTO (requisito, diseño, código, dato, configuración). Es la consecuencia de un `error`.
- `failure`: Manifestación observable del `defect` cuando el software se ejecuta. Es lo que VEO.

> [!TIP] error → defect → failure / Humano → artefacto → pantalla.

### The Question I Use to Decide

> ¿De quién habla la frase?
> - Una PERSONA haciendo algo (asumió, olvidó, no documentó, escribió mal) → `error`
> - Un ARTEFACTO siendo como es (la US no define, el código no agrupa, el diseño no contempla) → `defect`
> - La APP EJECUTÁNDOSE (cuando hago X, pasa Y) → `failure`

Es la misma jugada que me destrabó `verification` vs `validation` ("¿quién escribió la regla?"). Las dos me hacen mirar el SUJETO.

### Same Fact, Two Lenses

- "Yo no documenté que el equipo es una unidad." → `error` (persona, acción)
- "La US no define que el equipo es una unidad." → `defect` (artefacto, estado)

Cambia el sujeto y cambia el eslabón. No cambia el problema: cambia desde dónde lo miro.

> [!NOTE] Cada frase es UNO SOLO. Si habla de una persona, es `error`. Si habla de un artefacto, es `defect`. Si habla de la app corriendo, es `failure`. La duda aparece porque el `defect` es CONSECUENCIA del `error`: están pegados, pero se miran distinto.

> [!TIP] El `failure` siempre se escribe así: qué hago → qué esperaba (`expected result`) → qué pasó (`actual result`). Sin el `expected result` no hay `failure`: hay una opinión.

### The Ratio Is Not 1 to 1

- Un `error` puede generar VARIOS `defect`.
- Un `defect` puede producir VARIOS `failure`.
- Y un `failure` puede venir de un `defect` viejo que recién ahora se manifiesta.

### Latent Defect

Un `defect` puede existir y no manifestarse nunca (código muerto, ramas inalcanzables, condiciones que todavía no se dieron). No verlo NO significa que no esté. Es la misma idea del Concepto 1: "_La ausencia de evidencia, no es evidencia de ausencia._"

### Examples: Préstamos and Sedes

**Préstamos — equipo completo:**

- `error`: la instructora no explicitó que un equipo completo (torre + monitor + mouse) es una unidad; yo no lo documenté en la US/UC; el dev asumió y no preguntó. → TRES `error`.
- `defect`: en el requisito (la US/UC no define la agrupación) y en el modelo de datos (cada parte es un ítem independiente, sin agrupación).
- `failure`: en Préstamos, registro el préstamo del equipo completo y el sistema solo registra la torre; el monitor y el mouse siguen apareciendo como disponibles en el área.

- Un defect es algo que quedó mal escrito o que falta en un artefacto, como consecuencia del error de una persona — y ese 'algo' cambia según el artefacto. El error PASA. El defect QUEDA.