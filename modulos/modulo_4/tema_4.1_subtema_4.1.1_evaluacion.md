# EVALUACIÓN: DESIGN DOCS Y RFCs

## FICHA TÉCNICA

- **Tema**: 4.1.1 Documentación de Arquitectura
- **Nivel**: Avanzado

---

## CUESTIONARIO

### Pregunta 1

¿Cuál es el objetivo principal de escribir un Design Doc **antes** de codificar?
a) Cumplir con los requisitos de RRHH para promoción.
b) Detectar fallos de arquitectura cuando el costo de corrección es bajo (en papel).
c) Generar documentación automática para el usuario final.

### Pregunta 2

En la sección **"Alternativas Consideradas"**, ¿qué debes documentar?
a) Solo la opción que elegiste.
b) Todas las opciones evaluadas y la razón técnica/negocio por la cual fueron descartadas.
c) Un historial de chats de Slack.

### Pregunta 3: Diagnóstico

Estás revisando un Design Doc y ves el siguiente texto: *"En la línea 54 del archivo user_controller.py, usaremos un bucle while..."*. ¿Qué feedback darías?
a) "Excelente detalle".
b) "Esto es un Detalle de Implementación. El Design Doc debe enfocarse en la Arquitectura (Alto Nivel), no en el código línea por línea."
c) "Cambia el while por un for".

### Pregunta 4

¿Qué significan las siglas **RFC** en este contexto?
a) Request for Comments (Solicitud de Comentarios).
b) Ready for Coding (Listo para Codificar).
c) Real Fast Compiler.

### Pregunta 5

¿Cuándo se debe escribir un Design Doc?
a) Al finalizar el proyecto, para dejar registro.
b) Durante la implementación, actualizándolo cada día.
c) Antes de escribir código significativo (ej. tareas de >3 días), como herramienta de planificación.

---

## SOLUCIONARIO

1. **b)**. "Shift left" en la detección de errores.
2. **b)**. El valor está en los trade-offs analizados.
3. **b)**. El código cambia; la arquitectura debe ser estable.
4. **a)**. Es un estándar adoptado del IETF para propuestas colaborativas.
5. **c)**. Es una herramienta de diseño, no de autopsia.
