# EVALUACIÓN: CODE REVIEWS EMPÁTICOS

## FICHA TÉCNICA

- **Tema**: 5.2.1 Revisión de Código
- **Nivel**: Intermedio

---

## CUESTIONARIO

### Pregunta 1

¿Cuál es la diferencia entre un comentario `[BLOCKER]` y un `[NIT]`?
a) `[BLOCKER]` es para errores de sintaxis; `[NIT]` es para errores de lógica.
b) `[BLOCKER]` impide el merge por riesgo grave; `[NIT]` es una sugerencia menor que no impide el merge.
c) `[BLOCKER]` lo escribe el jefe; `[NIT]` lo escriben los juniors.

### Pregunta 2: Comunicación No Violenta

Elige la mejor forma de reportar un bug en un PR:
a) "¿Por qué hiciste esto así? Es muy lento."
b) "Has introducido una regresión de performance."
c) "Veo que este bucle anidado podría causar lentitud con muchos datos. ¿Podríamos optimizarlo?"

### Pregunta 3

¿Por qué se recomienda evitar el pronombre "Tú" en los comentarios?
a) Porque es informal.
b) Porque tiende a sonar acusatorio y pone al autor a la defensiva.
c) Porque Google lo prohíbe.

### Pregunta 4

Si ves un error de indentación (espacios vs tabs) en un archivo que no tiene linter configurado, ¿qué haces?
a) Marcarlo como `[BLOCKER]` y detener el deploy.
b) Marcarlo como `[NIT]` o arreglarlo tú mismo si tienes permisos, y sugerir configurar un Linter automático (Action Item).
c) Ignorarlo.

### Pregunta 5

¿Cuál es el objetivo principal de un Code Review?
a) Encontrar culpables.
b) Asegurar la calidad del código y compartir conocimiento (mentoring).
c) Retrasar el lanzamiento para molestar a Producto.

---

## SOLUCIONARIO

1. **b)**. Claridad en la severidad reduce ansiedad.
2. **c)**. Ataca el problema ("bucle"), no a la persona, y propone solución.
3. **b)**. Separa la identidad del autor del artefacto (código).
4. **b)**. Los problemas de estilo deben ser resueltos por máquinas (Linters), no humanos.
5. **b)**. Es un mecanismo de control de calidad y educación cruzada.
