# BANCO DE EJERCICIOS: MÓDULO 5 - CODE REVIEWS EMPÁTICOS

## METADATA

- **Módulo**: Comunicación en Crisis y Feedback
- **Objetivos evaluados**:
  1. Transformar comentarios agresivos en feedback constructivo.
  2. Aplicar etiquetas de severidad (NIT, BLOCKER, OPTIONAL).
  3. Practicar la técnica del "Nosotros" vs "Tú".
- **Tiempo total estimado**: 20 minutos
- **Nivel**: Intermedio

---

## EJERCICIO 1: El Traductor Diplomático

### ENUNCIADO

Reescribe estos comentarios reales y tóxicos para que sean accionables y empáticos, usando la técnica "Nosotros".

1. "¿Por qué diablos usaste un bucle anidado aquí? Es horrible."
2. "Este nombre de variable no tiene sentido. Cámbialo."
3. "Leíste la documentación antes de escribir esto?"

### SOLUCIÓN MODELO

1. "Veo que usamos un bucle anidado. **Nos** preocupa que esto afecte el rendimiento con grandes volúmenes de datos. ¿Podríamos usar un HashMap para evitar la complejidad cuadrática?"
2. "Este nombre de variable (`x`) es un poco ambiguo. **Sugerencia**: ¿Qué tal si lo renombramos a `userSessionId` para que sea más claro para el próximo que lea el código?"
3. "Creo que esta implementación difiere de lo que dicen los docs sobre el manejo de fechas. ¿Podríamos revisar juntos esa parte para asegurarnos de que no estamos introduciendo un bug?"

---

## EJERCICIO 2: Clasificación de Severidad

### ENUNCIADO

Etiqueta los siguientes hallazgos en un PR con `[BLOCKER]`, `[NIT]` o `[QUESTION]`.

1. El código permite inyección SQL en el login.
2. Falta un espacio después del `if`.
3. El desarrollador usó una librería de 2018 que tiene vulnerabilidades conocidas.
4. No entiendo por qué se divide por 100 aquí.
5. Sería mejor (pero no urgente) mover esta función a otro archivo.

### SOLUCIÓN

1. **[BLOCKER]**: Seguridad crítica.
2. **[NIT]**: Estilo, no afecta funcionalidad.
3. **[BLOCKER]**: Seguridad/Deuda técnica crítica.
4. **[QUESTION]**: Necesita contexto antes de juzgar.
5. **[OPTIONAL]** o **[NIT]**: Sugerencia de refactoring.

---

## EJERCICIO 3: El Estancamiento (Stalemate)

### ENUNCIADO

Llevas 3 días discutiendo en los comentarios de un PR con un compañero sobre si usar `Tabs` o `Spaces`. El tono está subiendo.
¿Cuál es la acción profesional correcta?
a) Escalarlo al CTO.
b) Escribir un comentario de 500 palabras explicando por qué tienes razón.
c) Detener la escritura, agendar una llamada de 5 minutos, llegar a un acuerdo verbal, y documentarlo.

### SOLUCIÓN

**c)**. El texto es terrible para resolver conflictos emocionales/opiniones. Una llamada humaniza la interacción y desbloquea el PR.

---

## AUTOEVALUACIÓN

- [ ] ¿He eliminado la palabra "Tú" de mis críticas?
- [ ] ¿He explicado el "Por qué" en mis Blockers?
