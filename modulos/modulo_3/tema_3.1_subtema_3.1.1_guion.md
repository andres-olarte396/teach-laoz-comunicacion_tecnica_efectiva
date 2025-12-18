# GUIÓN: OPENAPI Y CONTRACT-FIRST

## FICHA TÉCNICA

- **Duración**: 4.5 minutos
- **Estilo**: Diálogo Socrático (Mentor vs. Aprendiz)

---

### 00:00 - LA ESCENA

**[LOCUTOR]**:
Imagina esta escena en la Daily Standup.

**[DEV JUNIOR]**: "Ya terminé el endpoint de usuarios. Lo hice en Django. Ahora solo tengo que correr el script para auto-generar el Swagger y se lo paso al Frontend."

**[SENIOR ARCHITECT]**: "Espera. ¿Hiciste el código antes de acordar el contrato?"

**[DEV JUNIOR]**: "Sí, es más rápido. ¿Por qué escribir YAML a mano si el código lo hace solo?"

---

### 01:00 - EL PROBLEMA DEL CODE-FIRST

**[LOCUTOR]**:
Este es el error número uno en integración de sistemas.
Cuando generas el Swagger desde el código, accidentalmente expones tus "intestinos".

**[SENIOR ARCHITECT]**: "Mira tu Swagger auto-generado. Estás devolviendo el campo `password_hash_algorithm` y `created_at_pgsql_index`. Esos son detalles internos de tu base de datos. Si mañana cambiamos a Mongo, rompes al Frontend."

**[LOCUTOR]**:
Eso se llama **Leaking Internals**.
El Frontend no debe saber que usas Postgres. Solo debe saber que recibe un Usuario.

---

### 02:30 - LA SOLUCIÓN: CONTRACT-FIRST

**[LOCUTOR]**:
Contract-First invierte el juego.
Primero, Frontend y Backend se sientan con una cerveza (o un café) y escriben el archivo `api.yaml`.

"¿Cómo se va a llamar el campo? ¿`user_id` o `id`? ¿Es numérico o string?"

Una vez que acuerdan eso, lo firman.
Ese YAML es la ley.
Backend se va a implementar su código para CUMPLIR la ley.
Frontend se va a implementar su código usando un Mock que simula la ley.

---

### 03:45 - CIERRE

**[LOCUTOR]**:
Si trabajas solo, Code-First es aceptable.
Pero si trabajas en equipo, Contract-First es la única forma de evitar la frase: *"En mi local funciona, es culpa del Front"*.

Tu misión hoy: Abre un editor de texto. Escribe un endpoint en YAML. Entiende la estructura antes de escribir una sola línea de código.

*(Fade out)*
