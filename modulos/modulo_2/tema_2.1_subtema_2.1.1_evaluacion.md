# EVALUACIÓN: COMENTARIOS Y DOCSTRINGS

## FICHA TÉCNICA

- **Tema**: 2.1.1 El Por Qué sobre el Qué
- **Nivel**: Básico

---

## CUESTIONARIO

### Pregunta 1

¿Cuál es la función principal de un "Comentario Inline" Pragmático?
a) Explicar la sintaxis del lenguaje para programadores junior.
b) Traducir el código a lenguaje natural línea por línea.
c) Explicar el "Por Qué" (Intención, Negocio) que no es obvio en el código.

### Pregunta 2

Según la Regla de Kernighan, ¿qué debes hacer con el código malo?
a) Comentarlo extensamente para advertir a otros.
b) Reescribirlo para que sea claro sin comentarios.
c) Borrarlo y empezar de cero.

### Pregunta 3

Identifica el comentario **REDUNDANTE**:
a) `// TODO: Refactorizar esto cuando salga v2.0`
b) `// Usamos sleep(1) por race condition en API externa`
c) `total = precio * 1.16 // Multiplica precio por 1.16`

### Pregunta 4

¿Cuál es la diferencia entre un Docstring y un Comentario Inline?
a) El Docstring es para el Usuario (API pública); el Comentario es para el Mantenedor (Implementación).
b) El Docstring es opcional; el Comentario es obligatorio.
c) No hay diferencia.

---

## SOLUCIONARIO

1. **c)**. El código explica el Qué; el comentario explica el Por Qué.
2. **b)**. "Don't comment bad code — rewrite it."
3. **c)**. El código ya explica matemáticamente la operación; mejor sería renombrar la constante 1.16 a `TAX_RATE`.
4. **a)**. Docstring define el contrato de interfaz; Comentario explica detalles internos.
