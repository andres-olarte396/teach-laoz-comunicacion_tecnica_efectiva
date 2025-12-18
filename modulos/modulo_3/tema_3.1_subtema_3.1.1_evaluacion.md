# EVALUACIÓN: OPENAPI Y CONTRACT-FIRST

## FICHA TÉCNICA

- **Tema**: 3.1.1 Diseño de Contratos de API
- **Nivel**: Avanzado

---

## CUESTIONARIO

### Pregunta 1

¿Qué es el enfoque **Contract-First**?
a) Escribir el código primero y luego generar la documentación automáticamente.
b) Definir y acordar la especificación (YAML/JSON) antes de escribir cualquier línea de código.
c) Contratar consultores externos para diseñar la API.

### Pregunta 2: Diagnóstico

Si tu API devuelve un campo llamado `mongoose_internal_id_v2`, ¿qué error de diseño estás cometiendo?
a) Leaking Internals (Fuga de implementación).
b) Over-fetching.
c) Falta de autenticación.

### Pregunta 3

¿Cuál es la función principal de **Swagger UI**?
a) Compilar el código Backend.
b) Generar bases de datos desde cero.
c) Renderizar la especificación OpenAPI de forma visual e interactiva ("Try it out").

### Pregunta 4: YAML

En una especificación OpenAPI, ¿qué define la sección `components/schemas`?
a) Las credenciales de acceso a la base de datos.
b) Los modelos de datos reutilizables (ej. User, Product, Error).
c) La lista de desarrolladores backend.

### Pregunta 5

¿Qué ventaja tiene el Frontend al usar Contract-First?
a) Puede empezar a programar inmediatamente usando servidores Mock basados en el contrato.
b) No tiene que validar los datos.
c) Puede escribir el código del Backend ellos mismos.

---

## SOLUCIONARIO

1. **b)**. Es un acuerdo previo que desacopla el desarrollo.
2. **a)**. Estás exponiendo detalles de tu ORM (Mongoose) que deberían ser privados.
3. **c)**. Es la herramienta de visualización estándar.
4. **b)**. Permite definir la estructura de los objetos (tipos, requeridos) una sola vez.
5. **a)**. Permite paralelismo real entre equipos.
