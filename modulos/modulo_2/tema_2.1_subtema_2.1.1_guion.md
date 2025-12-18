# GUIÓN: COMENTARIOS Y DOCSTRINGS

## FICHA TÉCNICA

- **Duración**: 3 minutos
- **Tono**: Pragmático, Directo, Ligeramente Cínico (con el código malo).

---

### 00:00 - LA MENTIRA DEL CÓDIGO AUTODOCUMENTADO

**[LOCUTOR]**:
Hay un mito en ingeniería que dice: *"El buen código se documenta solo"*.
Esto es mentira. O al menos, es una verdad a medias.

El código te dice **QUÉ** está pasando.
`x = x + 1`. Incrementa equis. Perfecto.

Pero el código casi nunca te dice **POR QUÉ** está pasando.
¿Por qué sumamos 1? ¿Por qué no 2? ¿Es un contador de retries? ¿Es un índice de array?

---

### 01:00 - SUBTÍTULOS DE PELÍCULA

**[LOCUTOR]**:
Quiero que pienses en los comentarios como si fueran subtítulos de una película.

Imagina una escena donde el protagonista abre una puerta lentamente.
Un mal subtítulo diría: *"Abre la puerta con la mano derecha"*.
¡Ya lo estoy viendo! ¡Es ruido!

Un buen subtítulo diría: *"Teme que el asesino esté detrás"*.
¡Aha! Eso no lo veo en la acción física. Eso es contexto. Eso es el **POR QUÉ**.

---

### 02:00 - LA REGLA DE KERNIGHAN

**[LOCUTOR]**:
Brian Kernighan, uno de los padres de C, dijo:
*"No comentes código malo. Reescríbelo."*

Si tienes que escribir una parrafada para explicar una función de 50 líneas llamada `con`, el problema no es la falta de comentarios. El problema es que `con` debería llamarse `connect_to_database_with_retry`.

Tu meta esta semana: Borra comentarios.
Sí, borra. Encuentra esos comentarios que dicen `// Asigna variable` y destrúyelos. Deja solo los que expliquen trampas, decisiones de negocio o hacks temporales.

*(Fade out)*
