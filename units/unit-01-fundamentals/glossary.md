# Glossary — Unit 1

Glosario centralizado de la Unidad 1. Cada bloque corresponde a una nota de `notes/`.

## Verification vs Validation

*from `notes/03-verification-vs-validation.md`*

- `verification` — comprobar cumplimiento contra lo especificado.
- `validation` — comprobar aptitud para el uso real.
- `V&V` — el par `Verification and Validation`.
- `test basis` — la base de conocimiento contra la que comparás.
- `conformance` — cumplimiento respecto de la especificación.
- `fitness for purpose` — aptitud para el uso previsto.
- `UAT` — `User Acceptance Testing`, una técnica de `validation`.
- `acceptance criteria` — criterios que definen cuándo algo está aceptado.

## Error / Defect / Failure

*from `notes/04-error-defect-failure.md`*

- `error` / `mistake` — acción humana que produce un resultado incorrecto. **Pasa.**
- `defect` / `fault` — imperfección que quedó guardada en un artefacto: instrucción mal escrita o faltante. **Queda.**
- `bug` — nombre coloquial del `defect`.
- `failure` — manifestación observable del `defect` al ejecutar.
- `latent defect` — defecto que existe y todavía no se manifestó.

## Root Cause

*from `notes/05-root-cause.md`*

- `root cause` — causa de origen que, corregida, elimina el problema y sus hermanos.
- `root cause analysis (RCA)` — el proceso formal de buscarla.
- `5 Whys` — preguntar "¿por qué?" en cadena hasta algo accionable.
- `symptom` — lo visible (el `failure`).
- `workaround` — parche que evita el síntoma sin tocar la causa.
- `corrective action` — acción que elimina la causa ya manifestada.
- `preventive action` — acción que evita que aparezca.

## Testing vs Debugging

*from `notes/06-testing-vs-debugging.md`*

- `testing` — encontrar fallas y dar información; no arregla.
- `debugging` — localizar, analizar y corregir la causa de un `failure` en el código.
- `retesting` / `confirmation testing` — volver a ejecutar el mismo caso tras la corrección.

## Test Objective

*from `notes/07-test-objective.md`*

- `test objective` — la razón o el propósito de una prueba: la **pregunta** que quieres poder contestar cuando termines.
- `test scenario` — el **qué** se prueba. *(próximo concepto)*
- `test case` — el **cómo** se prueba: pasos, datos y resultado esperado. *(próximo concepto)*
