# GUIÓN: CODE REVIEWS EMPÁTICOS

## FICHA TÉCNICA

- **Duración**: 4 minutos
- **Tono**: Colaborativo, Profesional.

---

### 00:00 - EL JUICIO FINAL

**[LOCUTOR]**:
Cierras los ojos y haces click en "Create Pull Request".
Tu ritmo cardíaco sube.
Esperas el veredicto.
Una hora después, llega la notificación: *"Juan ha comentado en tu PR"*.
Abres el comentario: *"Esto está mal. ¿Por qué no usaste un Factory?"*

Te sientes estúpido. Te pones a la defensiva.
*"Lo hice así porque el Factory era overkill..."* respondes, molesto.
Bienvenido al Code Review Tóxico.

---

### 01:15 - NO ES SOBRE TI

**[LOCUTOR]**:
El Código no eres tú.
Un error en tu código no es un error en tu carácter.
Pero como revisores, a menudo atacamos a la persona.
*"Tú olvidaste..."*, *"Tú rompiste..."*.

La primera regla del Code Review Empático es eliminar la palabra "Tú".
Usa "Nosotros" o "El Código".

- *Mal*: "Tú no cerraste el stream".
- *Bien*: "El stream no se cierra en el bloque finally, lo que podría causar fugas".

---

### 02:30 - NITPICKING VS BLOCKERS

**[LOCUTOR]**:
Imagina que escribes una novela y tu editor te critica porque usaste una coma en lugar de un punto y coma en la página 300.
Eso es "Nitpicking".
Es molesto y distrae de lo importante (la trama).

En tus reviews, etiqueta tus comentarios.
Si es un detalle de estilo, pon `[NIT]`. Di: *"Arréglalo si quieres, pero no te bloqueo"*.
Si es un error grave, pon `[BLOCKER]`. Di: *"Esto no puede pasar porque rompe seguridad"*.

Esto elimina la ansiedad del autor. Sabe qué es obligatorio y qué es opcional.

### 03:45 - CIERRE

**[LOCUTOR]**:
El objetivo de un Code Review no es demostrar que eres más listo que el autor.
El objetivo es que **ambos** duerman tranquilos cuando el código llegue a producción.
Sé el revisor que te gustaría tener.

*(Fade out)*
