# BANCO DE EJERCICIOS: MÓDULO 3 - AUTENTICACIÓN Y ERRORES

## METADATA

- **Módulo**: Documentación de APIs
- **Objetivos evaluados**:
  1. Seleccionar el código de estado HTTP correcto.
  2. Escribir respuestas de error estructuradas (RFC 7807).
  3. Diferenciar errores de cliente (4xx) vs servidor (5xx).
- **Tiempo total estimado**: 20 minutos
- **Nivel**: Intermedio

---

## EJERCICIO 1. El Semáforo HTTP

### ENUNCIADO

Asocia cada escenario con el Código HTTP más apropiado (No uses 200 ni 500 genérico).

1. El usuario intenta borrar un post que no es suyo.
2. El usuario envía un JSON mal formado (falta una coma).
3. La base de datos se quedó sin conexiones.
4. El token de acceso ha expirado.
5. El recurso solicitado `/users/999` no existe.

### SOLUCIÓN

1. **403 Forbidden**. (Sabe quién eres, pero no tienes permiso).
2. **400 Bad Request**. (Error de sintaxis).
3. **503 Service Unavailable**. (Problema temporal del servidor).
4. **401 Unauthorized**. (Vuelve a loguearte).
5. **404 Not Found**.

---

## EJERCICIO 2: Diseñador de Payload

### ENUNCIADO

Escribe el JSON de respuesta para el siguiente error:
- **Escenario**: Usuario intenta registrarse con el email `bob@gmail`, pero faltan el `.com`.
- **Requisito**: Usa el estándar RFC 7807 (Problem Details).

### SOLUCIÓN MODELO

```json
{
  "type": "https://api.myapp.com/errors/invalid-email",
  "title": "Invalid Input",
  "status": 400,
  "detail": "El campo 'email' no es válido. Falta el dominio.",
  "instance": "/register",
  "invalidParams": [
    {
      "name": "email",
      "reason": "Invalid format"
    }
  ]
}
```

---

## EJERCICIO 3: El Mentiroso

### ENUNCIADO

Refactoriza esta respuesta de API (Anti-patrón) a una respuesta RESTful correcta.

**Respuesta Original (Mala):**

```http
HTTP/1.1 200 OK
{
  "status": "error",
  "msg": "No se encontró el producto"
}
```

**Tu Refactorización:**
*(Escribe el Header y el Body)*

### SOLUCIÓN MODELO

```http
HTTP/1.1 404 Not Found
Content-Type: application/problem+json

{
  "title": "Product Not Found",
  "status": 404,
  "detail": "El producto con ID solicitado no existe en el inventario."
}
```

---

## AUTOEVALUACIÓN

- [ ] ¿He dejado de usar `200 OK` para errores?
- [ ] ¿Mis errores explican CÓMO arreglar el problema?
