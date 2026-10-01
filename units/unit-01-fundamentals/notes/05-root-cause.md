# Testing fundamentals

## Root Cause

> Objective: Poder mirar un bug y llegar hasta la causa que, si la corrijo, evita que el mismo problema aparezca en otra pantalla.

- `root cause`: Es la razón fundamental u origen técnico por el cual ocurre un defect o failure. En el desarrollo de software, el objetivo final no es solo tapar el error visible, sino identificar y solucionar el root cause para garantizar que el bug no vuelva a aparecer en el futuro. A este proceso de investigación se le llama Root Cause Analysis (RCA).

### What "Process" Means

> Proceso: los pasos que el equipo sigue para trabajar. Y los pasos que NO existen.

No es una persona. No es el código. Es CÓMO trabaja el equipo.

Ejemplos concretos:

- "Escribo la US antes de codear."
- "Reviso el código antes de mergear."
- "Le pregunto al PO cuando algo no está claro."
- "Nunca definimos qué pasa cuando se borra un dato." ← **un paso que NO existe**

### The Test I Use to Decide

> ¿Pasó UNA vez por culpa de una persona, está pasando SIEMPRE sin importar la persona?

- **Una vez** → es un `error` de alguien. Se arregla y listo.
- **Siempre** → es una `root cause`. Porque no depende de quién lo haga.

### Analogy: The Kitchen

| En la cocina | En QA |
|---|---|
| El cocinero se olvidó la sal en ESE plato | `error` (una vez, una persona) |
| El plato salió sin sal | `defect` |
| El cliente lo prueba y se queja | `failure` |
| La cocina **no tiene un paso** donde alguien pruebe el plato antes de que salga | `root cause` |

La raíz no es "el cocinero es un descuidado". Es que no hay ningún paso de control: va a volver a pasar con otro cocinero y con otro plato.

### My Case

**Síntoma:** borro una categoría y no puedo reusar su nombre. Muestra "Categoria ya existe".

- `error`: yo no definí en ninguna US/UC qué pasa con el nombre de una categoría eliminada.
- `defect`: vive en el requisito (no lo define) y en el código (la unicidad cuenta los registros borrados).
- `failure`: "Categoria ya existe" al crear la categoría de nuevo.
- `root cause`: **en mi equipo NO existe el paso "antes de codear, definimos qué pasa con los datos que se borran".**

> Si hubiera sido que yo me olvidé una vez, no habría pasado en tres pantallas. Pasó tres veces porque **el paso no existe**.

### Important Limit

- La `root cause` es una **HIPÓTESIS**, no un hecho. Se valida: ¿si corrijo esto, dejan de aparecer los síntomas?
- No siempre hay que llegar a la raíz absoluta: se llega hasta donde la corrección sea accionable y proporcional al riesgo.
- Puede estar fuera de mi alcance (presupuesto, organigrama). Ahí documento el riesgo y aplico un control compensatorio.
- Buscar la raíz **NO reemplaza** arreglar el `failure`. Las dos cosas.
