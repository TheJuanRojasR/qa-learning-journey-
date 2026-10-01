# Testing fundamentals

## Testing vs Debugging

> Objective: Distinguir las dos actividades, saber qué produce cada una y quién las hace.

- `testing`: Actividad que se encarga de **ENCONTRAR** fallas y dar información sobre la calidad y el riesgo. Revisa el material indicado, verifica si hay `defects` / `failures` y los reporta de forma correcta. No arregla nada. Normalmente la hace el QC.
- `debugging`: Actividad que se encarga de **localizar, analizar y CORREGIR** la causa de un `failure` en el código. Normalmente la hace el developer — pero **todo depende de dónde esté el `defect`** (si está en el requisito, lo corrige el PO; si está en los datos, se corrige el dato).
- `retesting`: Volver a ejecutar ESE MISMO caso después de la corrección, para confirmar que el `failure` ya no ocurre.


### Analogy: The Inspection and the Workshop

| | |
|---|---|
| La inspección técnica revisa el auto y te da un informe | `testing` |
| El mecánico abre el motor, encuentra la pieza y la cambia | `debugging` |
| Volvés a la inspección y verifican que ese problema ya no está | `retesting` |

El inspector **NO repara**. El mecánico **NO certifica**. Si el mismo hace las dos cosas, nadie controla a nadie.

### My Case: Devolución vencida

- `testing`: ejecuto la devolución de un elemento vencido, veo que queda prestado para siempre, documento pasos + `expected result` + `actual result`. **NO toco el código.**
- `debugging`: el dev abre la función de devolución, ve que no contempla la fecha vencida, la corrige.
- `retesting`: vuelvo a ejecutar ESE mismo caso y confirmo que ahora sí registra.

### Contrast

| | `testing` | `debugging` |
|---|---|---|
| Objetivo | encontrar y reportar | localizar y corregir |
| Quién | tester / QC | normalmente el developer |
| Produce | información y evidencia | código corregido |
| NO hace | arreglar | certificar que quedó bien |
| Empieza | cuando hay algo que probar | cuando hay un `failure` que explicar |

### Common Mistakes

- **"El tester arregla el bug."** No: el tester **REPORTA**. Arreglar es `debugging`.
- **"Debugging es testing mirando el código."** No: el `debugging` empieza DESPUÉS de que algo falló. El `testing` es el que lo encuentra.
- **"Si soy dev, pruebo yo y listo."** Quien arregla no debería ser el único que verifica.
- **"Lo arreglé, listo."** Sin `retesting` no cerró.

### Important Limits


- Un buen tester **REDUCE el espacio de búsqueda** del dev: un reporte preciso ahorra horas de `debugging`.
- El `debugging` ataca el `defect`. Si la `root cause` está en el proceso, el `debugging` **no llega** — eso lo arregla el equipo.
- El `retesting` confirma el caso especifico, no "todo".
