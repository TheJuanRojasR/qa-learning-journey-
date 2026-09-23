# Testing fundamentals

## Verification vs Validation

> Objective: Poder revisar cualquier lista de chequeo y decidir si compara contra el documento o contra la necesidad real. Distinguir cuál es la diferencia y qué cambia.

- `verification`: Proceso de comprobar que EL PRODUCTO (documentos, diseño, código, o el software ejecutándose) cumple con la documentación técnica (US, UC, requirements, etc.). Lo que la define no es QUÉ evalúo, sino CONTRA QUÉ comparo: contra lo especificado.
- `validation`: Proceso de comprobar que el producto cubre las necesidades reales del usuario o del negocio. NO hace falta que sea el software final: puede ser un prototipo, un mockup o un incremento.

> [!NOTE] Existe esta distinción porque un producto se puede crear de forma correcta siguiendo la documentación técnica, pero... ¿es el producto que en verdad quiere el usuario final? Puede ser perfecto al contrastarlo con la documentación técnica y, si no es lo que quiere el usuario final, está mal. Por eso están estos dos conceptos: `verification` comprueba si se está siguiendo la documentación técnica, y `validation` comprueba que el software sea lo que en verdad quiere o necesita el usuario final.

> [!TIP] La actividad NO decide si es `verification` o `validation` (leer, ejecutar, estático, dinámico, manual, automatizado). Lo que decide es DE DÓNDE SALIÓ LA EXPECTATIVA: de la documentación técnica o de lo que en realidad necesita el usuario final.

### Classic Questions

- `verification`: *Are we building the product right?* → ¿Estamos construyendo el producto BIEN? (de la manera correcta, siguiendo lo especificado)
- `validation`: *Are we building the right product?* → ¿Estamos construyendo el producto CORRECTO? (el que el usuario realmente necesita)

### Practical Questions

> ¿Quién escribió la regla que estoy comprobando?
> - Una persona, en un papel (US, requisito, manual) → `verification`
> - La realidad (así trabaja la gente, aunque nadie lo haya escrito nunca) → `validation`

### Examples: The Activity Does Not Determine the Type

- `verification` que SÍ se ejecuta: la US dice que el login rechaza una contraseña incorrecta. Ejecuto el login con una contraseña mala y entra igual → FALLA, y era `verification`.
- `validation` que NO ejecuta nada: le muestro a un coordinador un dibujo en papel del buscador y me dice "así no encuentro a nadie entre 200" → FALLA, y era `validation`.

### Important Limit

- Si no hay `test basis` (nadie escribió la regla), `verification` es IMPOSIBLE: no hay contra qué comparar. Pero la salida no es "no puedo": es validar, y además REPORTAR el hueco y proponer el `acceptance criteria` al PO.

### Analogy

Imaginar que un cliente me pide construir una bicicleta de montania

- `verification`: revisar los planos, comprobar que el disenio sea correcta, contar las partes segun el manual y emsanblar la bicicleta.
- `validation`: motarn la bicicleta y probarla en una monatania. Si se creara una bicicleta de ruta esta pasaria el verification, pero no pasaria la validation porque se daniaria al utilizarla en una mantania y no seria lo que el cliente necesitaria.