# Testing fundamentals

## What is Software Testing?

> Objective: Definir que es Software Testing y explicar su proposito.

- `Software testing`: Actividad de evaluar un sistema(o componente) para detectar si funciona correctamente, y poder dar informacion sobre su calidad y posibles riesgos de este.
  - `Expected result`: Comportamiento definido en los requerimientos o el disenio. Es lo que debe hacer el sistema.
  - `Actual result`: Comportamiento real que se observa durante la ejecucion de la prueba.
  - `Preconditions`: Condiciones que se necesitan ANTES de iniciar la prueba. 

Testing no es encontrar bugs. Esto es una consecuencia, pero no es el objetivo. Lo que busca el testing es decir "_esto funciona, esto no, esto es riesgoso, y estas son las condiciones._"

Tampoco es decir: "_No encontre bugs, no sirvo para nada_". Lo importante es poder decir: "_probé estas áreas, estas condiciones, y no encontré defectos; acá está la evidencia de qué cubrí._". Esta es la informacion que si le ayuda al equipo.

"_no encontré un bug_" no es lo mismo que "el _producto no tiene bugs_". Tener en cuenta esta frase: "_La ausencia de evidencia, no es evidencia de ausencia._"

## QA vs QC

> Objective: Distingiuir QA de QC

- `Quality Assurance (QA)`: Se enfoca en la prevencion _defects_ definiendo, mejorando, y asegurando los procesos del desarrollo de software. Es una actividad preventiva orientada al proceso (_process-oriented_).
  - Ejemplo: requisitos claros, estandares de codigo, code reviews, buenas practicas, etc.
- `Quality Control (QC)`: Se enfoca en identificar los _defects_ en el software ya construido ejecutando _testings_. Es una actividad orientada al producto (_product-oriented_).
  - Ejemplo: testing, inspeccion, verificacion de la entrega contra los criterios.

> [!NOTE]"QA prevents defects. QC finds defects."

### Analogy

Imaginar que trabajo en una fabrica de galletas.

- `QA`: Revisar la receta de la masa, verificar temperatura de los hornos, verificar la calidad de los alimentos. Este proceso se hace antes y durante la preparacion para saber que las galletas no se quemaron.
- `QC`: Tomar una galleta despues de salir del horno y probarla antes de venderla. Si sabe mal o esta quemada (_defect_), se descarta.