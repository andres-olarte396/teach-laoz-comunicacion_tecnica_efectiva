# GUIÓN: AUTENTICACIÓN Y ERRORES

## FICHA TÉCNICA

- **Duración**: 3.5 minutos
- **Tono**: Pedagógico, Basado en Analogías.

---

### 00:00 - MENSAJES CRÍPTICOS

**[LOCUTOR]**:
Imagina que vas al médico. Le dices "me duele la cabeza".
El médico te mira y dice: *"ERROR 500"*. Y se va.

¿Frustrante, no?
Eso es lo que sienten los desarrolladores cuando tu API devuelve un `500 Internal Server Error` sin explicar nada más.
¿Falló la base de datos? ¿Envié mal un dato? ¿Estás en mantenimiento?

---

### 01:00 - EL SEMÁFORO HTTP

**[LOCUTOR]**:
Para comunicarnos, usamos un lenguaje universal de 3 dígitos: Los Códigos de Estado.
Piénsalo como un semáforo.

**La familia del 200 (Verde)**: "Pasa". Tu petición fue exitosa.
**La familia del 400 (Amarillo/Rojo para ti)**: "Es tu culpa". No me diste el token (`401`), o pediste algo que no existe (`404`).
**La familia del 500 (Rojo para mí)**: "Es mi culpa". El servidor explotó. Perdón.

Si devuelves un `200 OK` cuando hubo un error, es como poner un semáforo en verde cuando el puente está roto. Es negligencia criminal.

---

### 02:00 - EL TABLERO DEL COCHE

**[LOCUTOR]**:
Ahora, hablemos del cuerpo del error.
Si el semáforo está en rojo, necesito saber por qué.
En un coche, no se enciende una luz genérica de "Muerte". Se enciende "Falta Aceite".

Tu JSON de error debe ser igual.
No digas solo "Bad Request".
Di: *"El campo 'email' es obligatorio"*.
Usa el estándar RFC 7807 problem details.

---

### 03:00 - CIERRE

**[LOCUTOR]**:
Tu tarea esta semana es la empatía.
Rompe tu propia API a propósito. Envíale basura.
¿Qué te responde? ¿Te ayuda a arreglarlo o te confunde?
Si te confunde, arréglalo antes de que lo haga un cliente furioso.

*(Fade out)*
