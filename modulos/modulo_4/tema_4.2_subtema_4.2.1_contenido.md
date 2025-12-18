# TEMA 4.2.1: ADRs (ARCHITECTURE DECISION RECORDS)

**Tiempo estimado**: 30 minutos
**Nivel**: Avanzado
**Prerrequisitos**: Tema 4.1.1 (Design Docs)

## ¿Por qué importa este concepto?

¿Alguna vez has mirado una base de datos y te has preguntado: *"¿Por qué diablos separaron el nombre en 4 campos distintos?"*?
Y nadie sabe la respuesta. La persona que lo decidió se fue hace 3 años.

La arquitectura de software sufre de amnesia.
Un **ADR** es la cura para esa amnesia. Es un registro inmutable (como un commit de git) que explica una decisión en el momento en que se tomó.

## Conexión con conocimientos previos

* **Tema 4.1.1 (Design Docs)**: Un Design Doc es para *proponer* un cambio grande. Un ADR es para *registrar* una decisión concreta (haya habido design doc o no).
* **Git Commit**: Un ADR es a la arquitectura lo que un mensaje de commit es al código.

---

## Comprensión intuitiva

Imagina la **Bitácora del Capitán** de un barco.

* *Día 1*: "Decidimos ir al norte para evitar la tormenta."
* *Día 5*: "La ruta norte está bloqueada por hielo. Decidimos girar al oeste."

Si lees la bitácora, entiendes el viaje. Si solo ves el mapa final, pensarás que el capitán estaba borracho por dar tantas vueltas.
Los ADRs son la bitácora de tu proyecto.

---

## Definición formal

Un **ADR** es un archivo de texto ligero (Markdown) guardado en el repositorio (usualmente en `/doc/adr`) que captura una decisión de arquitectura significativa.

### Formato Estándar (Michael Nygard)

Un ADR tiene 4 secciones obligatorias:

1. **Título**: `001-usar-postgres-para-usuarios.md`
2. **Contexto**: Qué problema teníamos. "Necesitamos transacciones ACID para el saldo."
3. **Decisión**: Qué elegimos. "Usaremos PostgreSQL 14."
4. **Consecuencias**: Lo bueno y lo malo. "Ganamos consistencia, pero perdemos la facilidad de sharding de Mongo."

### Estado del ADR

* **Proposed**: En discusión.
* **Accepted**: Aprobado y vigente.
* **Deprecated**: Fue reemplazado por un ADR posterior. (Nunca borres un ADR, solo márcalo como obsoleto).

---

## Implementación práctica

### Ejemplo de ADR Real

```markdown
# ADR 009: Usar UUIDs para Claves Primarias

**Fecha**: 2025-10-15
**Estado**: Accepted

## Contexto
Actualmente usamos `AUTO_INCREMENT` (Integers) para los IDs de usuarios.
Esto revela el número de usuarios a la competencia (si alguien se registra y recibe el ID 500, sabe que tenemos 500 usuarios).
Además, dificulta la fusión de bases de datos en el futuro (colisión de IDs).

## Decisión
Usaremos **UUID v4** para todas las nuevas tablas y migraremos la tabla `Users`.

## Consecuencias
### Positivas
*   Seguridad: Los IDs no son enumerables.
*   Descentralización: Podemos generar IDs en el cliente o en múltiples nodos sin coordinación.

### Negativas
*   Rendimiento: Los índices B-Tree son más lentos y grandes con UUIDs que con Integers.
*   Legibilidad: Es difícil dictar un UUID por teléfono para soporte (`a4b5...`).
```

### Herramientas

No necesitas software complejo.
Usa la CLI `adr-tools`:

```bash
adr init
adr new "Usar UUIDs"
```

---

## Resumen del concepto

**En una frase**: Si tomas una decisión que afecta cómo trabajarán los demás, escríbela. Si no está escrita, no es una decisión, es solo un rumor.

**Regla de Oro**: Un ADR explica el "Por qué", no solo el "Qué". Incluso "No hacer nada" es una decisión que merece un ADR.

**Siguiente paso**: Generación de Ejercicios para redactar tus primeros ADRs.
