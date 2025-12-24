# PROYECTO BOOMERANG: EJECUCIÓN

## METADATA

- **Módulo**: Proyecto Integrador Final
- **Objetivos evaluados**:
  1. Diseñar la Arquitectura de Información de un Developer Portal.
  2. Aplicar principios de copywriting técnico (Value Props).
  3. Estructurar un Quickstart efectivo.
- **Entregable**: Un archivo `PORTAL_STRUCTURE.md` (simulado).

---

## PASO 1. La Landing Page (El Pitch)

### INSTRUCCIONES

Estás diseñando la Home de "Meteor Weather API".
Escribe los siguientes 3 elementos para la portada:

1. **H1 (Título Principal)**: Debe ser claro y orientado a la acción. No uses "Meteor API". Usa algo que diga *qué obtiene el usuario*.
2. **Subtítulo (Propuesta de Valor)**: En 2 líneas, explica por qué somos mejores que la competencia (ej. OpenWeatherMap). Pista: Habla de latencia o precisión histórica.
3. **Snippet "Hello World"**: Escribe una llamada `curl` ficticia que devuelva el clima de Tokio. Debe parecer simple.

---

## PASO 2: Arquitectura de Navegación (Card Sorting)

### INSTRUCCIONES

Tienes los siguientes contenidos desordenados. Organízalos en un Menú Lateral con Categorías lógicas (ej. "Inicio", "Guías", "Referencia", "Soporte").

- Cómo autenticarse con OAuth2.
- Endpoint GET /weather/history.
- Librería para Python.
- Preguntas Frecuentes (FAQ).
- Endpoint GET /weather/forecast.
- Primeros pasos: Tu primera request.
- Códigos de Error y Límites de Rate.
- SDK para Node.js.
- Estado del Servicio (Uptime).

---

## PASO 3: El Quickstart (De 0 a Hero)

### INSTRUCCIONES

Escribe el índice (pasos) para el tutorial "Quickstart".
No escribas el contenido completo, solo los **títulos de los pasos**.
El objetivo es que el usuario tenga un JSON con el clima en su terminal en menos de 5 pasos.

*Ejemplo*:

1. *Regístrate para obtener una API Key.*
2. *...*

---

## SOLUCIÓN MODELO (PARA AUTO-REVISIÓN)

### Paso 1

* **H1**: "Pronósticos hiper-locales para agricultura de precisión."
- **Subtítulo**: "Accede a 50 años de datos históricos y predicciones minuto a minuto con nuestra API de baja latencia. Diseñada para agrónomos y desarrolladores."
- **Snippet**:

    ```bash
    curl "https://api.meteor.com/v2/weather?city=Tokyo&key=YOUR_KEY"
    ```

### Paso 2

* **Getting Started**: Primeros pasos, Autenticación (OAuth2), Códigos de Error.
- **Guides**: Quickstart.
- **API Reference**: GET /forecast, GET /history.
- **SDKs**: Python, Node.js.
- **Support**: FAQ, Status.

### Paso 3

1. Obtén tu API Key gratuita.
2. Instala nuestro cliente (o usa cURL).
3. Haz tu primera petición (Copy-Paste).
4. Interpreta la respuesta JSON.
