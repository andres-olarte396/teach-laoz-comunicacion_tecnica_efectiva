# BANCO DE EJERCICIOS: MÓDULO 3 - OPENAPI Y CONTRACT-FIRST

## METADATA

- **Módulo**: Documentación de APIs
- **Objetivos evaluados**:
  1. Leer y modificar especificaciones OpenAPI (YAML).
  2. Identificar riesgos del enfoque "Code-First".
  3. Resolver conflictos de integración mediante contratos.
- **Tiempo total estimado**: 25 minutos
- **Nivel**: Avanzado

---

## EJERCICIO 1: El Inspector de Contratos

### ENUNCIADO

Analiza el siguiente fragmento YAML y encuentra los **3 Errores Críticos** que romperían la integración con el Frontend.

```yaml
paths:
  /users:
    get:
      summary: Obtener usuarios
      responses:
        '200':
          description: OK
          content:
            application/json:
              schema:
                type: array  # Error: No define qué hay dentro del array
        '404':
          description: No encontrado
    post:
      summary: Crear usuario
      parameters: 
        - name: id   # Error: El ID debe ser generado por el server, no enviado en URL
          in: path
          required: true 
          schema:
            type: integer
```

### SOLUCIÓN

1. **Array sin items**: `type: array` necesita `items: { $ref: ... }`. El Front no sabe qué datos esperar.
2. **ID en Path para POST**: Un `POST` a `/users` no debería llevar ID (`/users/{id}`). El ID se crea al guardar.
3. **Falta RequestBody**: El `POST` no define qué datos enviar (Nombre, Email) en el cuerpo.

---

## EJERCICIO 2: Code-First vs Contract-First

### ENUNCIADO

Eres el Tech Lead. Tu equipo Backend sugiere: "Hagamos el código en Python primero, y luego usamos una librería para auto-generar el Swagger".
Escribe 2 argumentos técnicos para **rechazar** esa propuesta y forzar Contract-First.

### SOLUCIÓN MODELO

1. **Bloqueo del Frontend**: "Si esperamos a terminar el código Python para tener el Swagger, el equipo de Frontend estará bloqueado 2 semanas esperando saber qué campos enviaremos. Con Contract-First, pueden usar Mocks hoy mismo."
2. **Leaking Internals**: "Los generadores automáticos tienden a exponer nuestros modelos de Base de Datos (ej. `created_at_db_index`) en la API pública, acoplándonos innecesariamente."

---

## EJERCICIO 3: Diseñando la Hamburguesa

### ENUNCIADO

Escribe el `schema` OpenAPI para un objeto `Product` en una tienda e-commerce.
Requisitos:

- `id`: UUID, solo lectura.
- `name`: String, obligatorio.
- `price`: Número, obligatorio, mayor a 0.
- `tags`: Array de strings (opcional).

### SOLUCIÓN MODELO

```yaml
components:
  schemas:
    Product:
      type: object
      required:
        - name
        - price
      properties:
        id:
          type: string
          format: uuid
          readOnly: true
        name:
          type: string
        price:
          type: number
          minimum: 0.01
        tags:
          type: array
          items:
            type: string
```

---

## AUTOEVALUACIÓN

- [ ] ¿Entiendo que el YAML es la ley, y el código es solo la implementación?
- [ ] ¿Puedo leer un archivo swagger.yaml sin usar la UI gráfica?
