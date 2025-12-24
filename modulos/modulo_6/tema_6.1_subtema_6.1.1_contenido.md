# TEMA 6.1.1. EL PORTAL DEL DESARROLLADOR (PROYECTO BOOMERANG)

**Tiempo estimado**: 45 minutos (Lectura + Inicio de Proyecto)
**Nivel**: Experto
**Prerrequisitos**: Módulos 1 al 5

## ¿Por qué importa este concepto?

Hasta ahora has escrito "piezas" sueltas: un README, un endpoint de API, un Postmortem.
Pero los desarrolladores no consumen piezas sueltas. Consumen una **Experiencia de Producto**.

Un **Developer Portal** es la tienda donde vendes tu tecnología.
Si la tienda está desordenada, nadie comprará, por muy bueno que sea el producto.
El "Proyecto Boomerang" se llama así porque todo lo que has aprendido regresa para integrarse aquí.

## Conexión con conocimientos previos

* **Módulo 1 (Escritura)**: El tono de tu portal.
* **Módulo 2 (Código)**: Los SDKs y ejemplos.
* **Módulo 3 (APIs)**: La referencia Swagger/OpenAPI.
* **Módulo 4 (Arquitectura)**: Decisiones de diseño (ADRs).
* **Módulo 5 (Soporte)**: Cómo contactar cuando algo falla.

---

## Anatomía de un Developer Portal de Clase Mundial

Analiza portales como *Stripe Docs* o *Twilio Docs*. Todos tienen 4 pilares:

### 1. La Landing Page (El Gancho)

Responde en 5 segundos: *"¿Qué hace esto y por qué debería importarme?"*.

* **Héroe**: Título claro + Botón "Get Started".
* **Value Props**: "Integra pagos en 5 líneas de código".
* **Hello World**: Un snippet de código funcional que muestra simplicidad.

### 2. Guías y Tutoriales (El "Cómo")

Aquí aplicas la **Pirámide Invertida**.

* **Quickstart**: De 0 a "Hello World" en 15 minutos.
* **Tutoriales Temáticos**: "Cómo manejar reembolsos", "Cómo autenticar usuarios".

### 3. Referencia de API (El Diccionario)

Generada automáticamente (Swagger), pero curada humanamente.

* Debe incluir: Endpoints, Parámetros, Códigos de Error (Traffic Lights), y Ejemplos de Request/Response en varios lenguajes (cURL, Python, Node).

### 4. Soporte y Comunidad (La Red de Seguridad)

* **Status Page**: ¿Está caída la API?
* **Changelog**: ¿Qué cambió recientemente?
* **Stack Overflow / Discord**: Dónde pedir ayuda humana.

---

## EL PROYECTO FINAL: "Boomerang"

Tu misión es diseñar la estructura de documentación para una API ficticia: **"Meteor Weather API"**.

### Escenario

Meteor es una API que provee datos del clima histórico y predicciones futuras para aplicaciones de agricultura.
Acaban de lanzar la versión 2.0 y la documentación actual es un PDF de 50 páginas.
Tu trabajo es modernizarla.

### Entregable Requerido

No tienes que programar el portal. Tienes que crear la **Arquitectura de Información** en un archivo `PORTAL_STRUCTURE.md` que contenga:

1. **Home Copy**: Título y propuesta de valor.
2. **Índice de Navegación**: ¿Qué secciones tendrá el menú lateral?
3. **Diseño del Quickstart**: Pasos numerados del tutorial "Obtén el clima de tu ciudad en 5 minutos".
4. **Matriz de Errores**: Lista de 3 errores comunes de la API y cómo los documentarías (Status Code + Mensaje Humano).

Este proyecto demostrará que puedes pensar no solo como escritor, sino como **Product Manager de Documentación**.

---

## Resumen del concepto

**En una frase**: La documentación es un producto, no un artefacto. Trátala como tal.

**Regla de Oro**: La métrica de éxito de un portal es el **TTHW (Time to Hello World)**. ¿Cuánto tarda un dev nuevo en hacer su primera llamada exitosa?

**Siguiente paso**: Manos a la obra. Generaremos ejercicios para bocetar este portal.
