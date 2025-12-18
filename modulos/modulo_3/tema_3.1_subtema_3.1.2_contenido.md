# TEMA 3.1.2: AUTENTICACIÓN Y ERRORES

**Tiempo estimado**: 30 minutos
**Nivel**: Intermedio
**Prerrequisitos**: Tema 3.1.1 (OpenAPI)

## ¿Por qué importa este concepto?

Una API no se juzga por cómo funciona cuando todo va bien, sino por cómo se comporta cuando algo sale mal.
Los errores son la interfaz de usuario del desarrollador. Un error críptico (`500 Internal Server Error`) hace perder horas de debugging. Un error claro (`400 Bad Request: Missing field 'email'`) se soluciona en segundos.

Igualmente, la autenticación es la puerta de entrada. Si es confusa, nadie entrará.

## Conexión con conocimientos previos

En el Tema 2.1.1 (Comentarios), aprendimos a explicar el "Por Qué". Los errores de API deben hacer lo mismo: explicar *por qué* falló el request y *qué* hacer para arreglarlo.

---

## Comprensión intuitiva

### Los Códigos HTTP son Semáforos

Imagina conducir por una ciudad sin semáforos. Caos total.
Los códigos HTTP son señales universales:

* **2xx (Verde)**: Todo bien. Pasa.
* **4xx (Amarillo/Rojo para ti)**: Tú (Cliente) hiciste algo mal. Corrige tu request.
* **5xx (Rojo para mí)**: Yo (Servidor) tengo un problema. Intenta más tarde.

### El Payload de Error es el Tablero

Si el coche se detiene, no quieres solo una luz roja genérica. Quieres un indicador específico: "Falta aceite" o "Puerta abierta".
Devolver `200 OK` con un cuerpo `{ "status": "error" }` es como poner una pegatina de "Todo está bien" sobre el indicador de "Motor incendiado". **Es mentir**.

---

## Definición formal

### 1. La Santísima Trinidad de los Errores

Nunca inventes códigos. Usa los estándares:

* **400 Bad Request**: Error de sintaxis o validación (falta campo).
* **401 Unauthorized**: "¿Quién eres?" (Falta token).
* **403 Forbidden**: "Sé quién eres, pero no puedes pasar" (Falta permiso).
* **404 Not Found**: Lo que buscas no existe.
* **429 Too Many Requests**: Calma, estás haciendo spam.
* **500 Internal Server Error**: Bug en el código (NullPointer, DB caída).

### 2. Estructura de Error (Standard Problem Details - RFC 7807)

No devuelvas solo texto. Devuelve JSON estructurado.

```json
{
  "type": "about:blank",
  "title": "Saldo insuficiente",
  "status": 403,
  "detail": "Tu saldo actual es 10.00, pero la transacción requiere 25.00.",
  "instance": "/transactions/12345"
}
```

---

## Implementación práctica

### El Anti-Patrón: "200 OK con Error" (El Mentiroso)

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "success": false,
  "error": "Card declined"
}
```

* *Por qué es malo*: Las herramientas de monitoreo (Datadog, New Relic) ven un "200" y piensan que el sistema está saludable. El cliente tiene que parsear el cuerpo para saber si funcionó.

### El Patrón: Autenticación Clara

Define explícitamente cómo autenticarse en tu OpenAPI:

1. **API Key**: Simple. `Authorization: ApiKey <secret>`. Para s2s (server-to-server).
2. **Bearer Token (JWT)**: Estándar para usuarios. `Authorization: Bearer <token>`.

```yaml
components:
  securitySchemes:
    BearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
security:
  - BearerAuth: []
```

---

## Errores frecuentes

### Error 1: Leakear Stack Traces

Nunca devuelvas el stack trace de Java/Python en producción.

* *Mal*: `ValueError: at app.py line 45...`
* *Riesgo*: Expones rutas de archivos y versiones de librerías a atacantes.

### Error 2: Mensajes Genéricos

* *Mal*: `400 Bad Request`.
* *Bien*: `400 Bad Request: Field 'age' must be an integer > 18`.

---

## Resumen del concepto

**En una frase**: Usa los códigos HTTP como se diseñaron (no mientas con 200) y da mensajes de error que ayuden al desarrollador a arreglar el problema sin llamarte.

**Regla de Oro**: Un buen error enseña al usuario cómo usar la API.

**Siguiente paso**: Generación de Ejercicios para diagnosticar APIs mentirosas.
