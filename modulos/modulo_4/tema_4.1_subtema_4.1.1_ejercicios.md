# BANCO DE EJERCICIOS: MÓDULO 4 - DESIGN DOCS Y RFCs

## METADATA

- **Módulo**: Documentación de Arquitectura
- **Objetivos evaluados**:
  1. Redactar el contexto de un problema sin saltar a la solución.
  2. Evaluar Trade-offs en la sección de "Alternativas Consideradas".
  3. Distinguir entre "Diseño de Alto Nivel" y "Detalles de Implementación".
- **Tiempo total estimado**: 30 minutos
- **Nivel**: Avanzado

---

## EJERCICIO 1: El One-Liner Ejecutivo

### ENUNCIADO

Eres el Tech Lead. Tienes que convencer al CTO de reescribir el módulo de pagos de Python a Go.
Escribe el **Resumen (TL;DR)** de tu Design Doc.
- **Restricción**: Máximo 2 oraciones.
- **Debe incluir**: El cambio propuesto y el beneficio de negocio (no solo técnico).

### SOLUCIÓN MODELO
>
> "Proponemos migrar el servicio de checkout a Go para reducir la latencia de P99 de 500ms a 50ms durante el Black Friday. Esto evitará la pérdida estimada de $50k en ventas por timeouts observada el año pasado."

---

## EJERCICIO 2: Matriz de Decisiones (Trade-offs)

### ENUNCIADO

Estás eligiendo una base de datos para guardar logs de auditoría (write-heavy, read-rarely).
Completa la sección "Alternativas Consideradas" para **PostgreSQL** vs **Elasticsearch**.

| Criterio | PostgreSQL | Elasticsearch | Decisión |
| :--- | :--- | :--- | :--- |
| **Escritura** | (A) | (B) | |
| **Búsqueda** | SQL estándar, lenta en texto libre | Búsqueda full-text nativa y rápida | |
| **Costo** | Bajo (ya tenemos infraestructura) | (C) | |

*(Rellena A, B y C)*

### SOLUCIÓN

* **(A)**: ACID, más lenta para ingesta masiva sin sharding.
- **(B)**: Optimizada para append-only, ingesta masiva casi real-time.
- **(C)**: Alto (requiere cluster dedicado y mucha RAM).

---

## EJERCICIO 3: El Detective de Design Docs

### ENUNCIADO

Lee el siguiente fragmento de un Design Doc y marca qué partes **NO** deberían estar ahí (son detalles de implementación o ruido).

> "Para el sistema de notificaciones, vamos a crear una clase `NotificationManager` que hereda de `BaseManager` (línea 45 de `utils.py`). Usaremos un `for loop` para iterar los usuarios. La base de datos estará en la IP 192.168.1.50. El objetivo es enviar emails a usuarios inactivos."

### SOLUCIÓN

* ❌ `hereda de BaseManager`: Detalle de implementación irrelevante para la arquitectura.
- ❌ `línea 45 de utils.py`: Demasiado granular, cambiará mañana.
- ❌ `Usaremos un for loop`: Obvio.
- ❌ `IP 192.168.1.50`: Hardcoded configuration.
- ✅ `El objetivo es enviar emails a usuarios inactivos`: Esto es **Contexto**, y es lo único valioso del párrafo.

---

## AUTOEVALUACIÓN

- [ ] ¿He mencionado los "Riesgos" de mi solución propuesta?
- [ ] ¿He explicado "Por qué NO" elegí las otras alternativas?
