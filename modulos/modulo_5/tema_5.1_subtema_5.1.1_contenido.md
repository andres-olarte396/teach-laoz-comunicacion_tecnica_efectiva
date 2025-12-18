# TEMA 5.1.1: POSTMORTEMS BLAMELESS (CAUSA RAÍZ)

**Tiempo estimado**: 35 minutos
**Nivel**: Intermedio
**Prerrequisitos**: Tema 4.1.1 (Design Docs)

## ¿Por qué importa este concepto?

Cuando un sistema de producción cae, la reacción instintiva es buscar un culpable: *"¿Quién hizo el deploy?"*.
Esta mentalidad garantiza que el error se repetirá.
Si despides al ingeniero que borró la base de datos, has despedido a la única persona que aprendió la lección (y que costó millones entrenar).

Un **Postmortem Blameless** transforma un desastre costoso en un activo de conocimiento.

## Conexión con conocimientos previos

* **Tema 3.1.2 (Errores HTTP)**: Un error `500` en producción es el detonante habitual de un Postmortem.
* **Tema 5.2.1 (Code Reviews)**: La cultura de "no culpar" es la misma que usaremos en los Code Reviews.

---

## Comprensión intuitiva

Piensa en una **Investigación de Accidente Aéreo**.
El objetivo no es meter al piloto en la cárcel.
El objetivo es rediseñar la cabina para que ningún otro piloto pueda cometer ese mismo error, incluso si está cansado o estresado.

* *Culpable*: "Juan borró la tabla."
* *Sistémico*: "El sistema permitió borrar la tabla sin confirmación y con un usuario genérico."

---

## Definición formal

Un **Postmortem** es un documento escrito *después* de que el incidente ha sido resuelto.
No es un chat de Slack. Es un reporte formal que responde:

1. **¿Qué pasó?** (Timeline).
2. **¿Por qué pasó?** (Root Cause Analysis).
3. **¿Cómo evitamos que pase de nuevo?** (Action Items).

### Técnica: Los 5 Porqués (Toyota)

```mermaid
graph TD
    A[Incidente: OOM en Facturación] -->|Why?| B[Cargó todos los usuarios en RAM]
    B -->|Why?| C[Usó User.all() sin paginación]
    C -->|Why?| D[Asumió dataset pequeño]
    D -->|Why?| E[No probó con volúmenes reales]
    E -->|Why?| F[Staging no tiene Data Seeding]
    style F fill:#f96,stroke:#333,stroke-width:4px
```

No te detengas en la primera respuesta.

* **Problema**: El sitio se cayó.

1. *¿Por qué?*: La base de datos CPU llegó al 100%.
2. *¿Por qué?*: Una query sin índice se ejecutó millones de veces.
3. *¿Por qué?*: Se lanzó una nueva feature que usaba esa query.
4. *¿Por qué?*: El desarrollador no probó con datos reales.
5. *¿Por qué? (Causa Raíz)*: **No tenemos un entorno de Staging con volumen de datos similar a Producción.**

*Solución*: Crear un script de anonimización para Staging. (No "Regañar al desarrollador").

---

## Estructura del Documento

1. **Resumen Ejecutivo**: Impacto en el negocio (duración, usuarios afectados, dinero perdido).
2. **Cronología (Timeline)**: Segundo a segundo.
    * `10:00` - Se inicia deploy v2.
    * `10:05` - Alertas de latencia se disparan.
    * `10:15` - Rollback iniciado.
3. **Causa Raíz**: El resultado de los 5 Porqués.
4. **Action Items**: Tareas en Jira con dueño y fecha. "Arreglarlo" no es un action item. "Implementar Rate Limiting en endpoint X" sí lo es.

---

## Errores frecuentes

### Error 1: Lenguaje Acusatorio

* *Mal*: "El error fue causado porque Pedro olvidó el `WHERE`."
* *Bien*: "El comando `DELETE` fue ejecutado sin cláusula `WHERE`, lo que el sistema permitió sin advertencia."

### Error 2: "Ser más cuidadosos" como Solución

"Action Item: Los devs deben tener más cuidado."
Esto NO sirve. Los humanos fallan.
La solución debe ser técnica (Tooling, Automatización, Linter), no psicológica.

---

## Resumen del concepto

**En una frase**: No desperdicies una buena crisis. Úsala para endurecer el sistema, no para castigar a las personas.

**Regla de Oro**: Si en tu postmortem aparece el nombre de una persona como "Causa", has fallado. La causa siempre es el proceso o la herramienta.

**Siguiente paso**: Ejercicios para practicar la técnica de los 5 Porqués.
