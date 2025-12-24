# TEMA 5.2.1. CODE REVIEWS EMPÁTICOS

**Tiempo estimado**: 30 minutos
**Nivel**: Intermedio
**Prerrequisitos**: Tema 5.1.1 (Blameless Culture)

## ¿Por qué importa este concepto?

El Code Review (PR) es el punto de mayor fricción social en el desarrollo.
Es donde el "Mi código" se convierte en "Nuestro código".
Una mala cultura de review crea silos: *"No reviso el código de Ana porque siempre se ofende"* o *"Álex es un pedante que me bloquea por espacios en blanco"*.

Un **Code Review Empático** mejora la calidad del código SIN destruir la moral del equipo.

## Conexión con conocimientos previos

* **Tema 1.1.2 (Pirámide Invertida)**: Tus comentarios en el PR deben ser directos pero amables.
* **Tema 5.1.1 (Postmortems)**: El objetivo es mejorar el sistema, no juzgar al autor.

---

## Comprensión intuitiva

Piensa en un **Editor de Libros**.
El editor no odia al escritor. Quiere que el libro sea un best-seller.
Si el editor dice: *"Este capítulo es aburrido, bórralo"*, el escritor se pone a la defensiva.
Si dice: *"Creo que la trama ganaría velocidad si unimos estos dos capítulos"*, el escritor colabora.

El Code Review es **Edición Colaborativa**, no un examen que se aprueba o reprueba.

---

## Definición formal

Un buen comentario de Code Review tiene 3 características (Google Standard):

1. **Accionable**: Dice claramente qué cambiar.
2. **Justificado**: Explica por qué (Performance, Estilo, Seguridad).
3. **Etiquetado**: Define la severidad.

### Niveles de Severidad (Etiquetas)

Usa prefijos para eliminar la ansiedad:

* **[BLOCKER]**: "Esto rompe producción o introduce un bug de seguridad. No se puede mergear."
* **[NIT]** (Nitpick): "Detalle menor (espacios, nombres). Arréglalo si quieres, pero no bloquea el merge."
* **[OPTIONAL]**: "Sugerencia de refactoring para el futuro. No bloquea."
* **[QUESTION]**: "No entiendo esto, ¿me lo explicas? (No es una crítica, es duda)."

---

## La Técnica "Nosotros" vs "Tú"

Jamás uses "Tú" para señalar un error. Ataca al código, no a la persona.

* *Violento*: "**Tú** olvidaste cerrar la conexión aquí."
* *Neutral*: "El código no cierra la conexión."
* *Empático*: "**Nos** falta cerrar la conexión aquí para evitar memory leaks."

---

## Implementación práctica

### El Sandwich de Feedback (Uso con precaución)

A veces ayuda empezar con algo positivo.
*"¡Gran refactorización de la clase User! Solo tengo un par de dudas sobre el manejo de errores en este método..."*

### Ejemplo de Comentario Constructivo

> **[BLOCKER]**: Veo que estamos iterando la lista `users` dentro del loop de `orders`.
> **Por qué**: Esto crea una complejidad O(n^2) que tumbará el servidor si tenemos más de 100 usuarios.
> **Sugerencia**: Podríamos crear un mapa de usuarios antes del loop para bajarlo a O(n). ¿Qué opinas?

---

## Errores frecuentes

### Error 1. "LGTM" Automático (Looks Good To Me)

Aprobar sin leer es peligroso. Si no entiendes el código, di: *"No tengo contexto suficiente para aprobar esto"*. Es más profesional.

### Error 2: Comentarios Pasivo-Agresivos

* *"¿Por qué harías esto?"*
* *"Esto es obvio..."*
Evita preguntas retóricas. Sé explícito.

---

## Resumen del concepto

**En una frase**: Trata el código de tu compañero con el mismo respeto con el que tratarías el tuyo propio si tuvieras amnesia.

**Regla de Oro**: Si tienes que escribir más de 3 comentarios seguidos sobre el mismo tema, **deja de escribir y haz una videollamada**. El texto es malo para el debate.

**Siguiente paso**: Ejercicios para reescribir comentarios tóxicos.
