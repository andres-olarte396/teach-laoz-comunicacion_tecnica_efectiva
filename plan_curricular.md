# ARQUITECTURA CURRICULAR: COMUNICACIÓN TÉCNICA EFECTIVA PARA DESARROLLADORES

## METADATA

- **Complejidad**: Intermedia/Alta
- **Duración estimada**: 10 horas
- **Audiencia objetivo**: Desarrolladores Senior, Tech Leads, Arquitectos de Software
- **Prerrequisitos obligatorios**:
  1. Experiencia trabajando en equipos ágiles.
  2. Redacción de documentación técnica básica (README, comentarios).
  3. Participación activa en Code Reviews.
- **Fecha de diseño**: 2025-12-07

## MAPA CONCEPTUAL

```mermaid
graph TD
    A[Comunicación Técnica Efectiva] --> B(Fundamentos)
    A --> C(Documentación de Código)
    A --> D(Documentación de Proyecto)
    A --> E(Comunicación Humana)

    B --> B1[Claridad y Concisión]
    B --> B2[Audiencia y Tono]

    C --> C1[Comentarios y Docstrings]
    C --> C2[README y ONBOARDING]
    C --> C3[API Reference]

    D --> D1[RFCs y Design Docs]
    D --> D2[ADRs (Architecture Decision Records)]
    D --> D3[Postmortems]

    E --> E1[Code Reviews Constructivos]
    E --> E2[Feedback Técnico]
```

## OBJETIVOS GENERALES DEL CURSO

1. **Redactar** documentación técnica que reduzca el tiempo de onboarding y soporte en un 30%.
2. **Estructurar** propuestas técnicas (RFCs) persuasivas y claras para la toma de decisiones arquitectónicas.
3. **Aplicar** técnicas de comunicación asertiva y constructiva en Code Reviews y Postmortems.
4. **Implementar** una estrategia de "Docs as Code" en el flujo de trabajo diario.

## ESTRUCTURA MODULAR

### MÓDULO 0: Diagnóstico y Nivelación

**Duración**: 1 hora
**Objetivo**: Validar prerrequisitos y alinear conceptos base de escritura.

#### Ruta Básica

- Concepto 0.1: La falacia de "El código se documenta solo"
  - Objetivo específico: Identificar cuándo el código limpio no es suficiente.
  - Tiempo estimado: 20 min
  - Tipo: Teórico
- Concepto 0.2: Herramientas del escritor técnico (Markdown, Linters)
  - Objetivo específico: Configurar entorno de escritura (Vale, Markdownlint).
  - Tiempo estimado: 40 min
  - Tipo: Práctico

#### Ruta Intermedia

- Enfoque en configuración avanzada de linters de prosa en CI/CD.

#### Ruta Avanzada

- Omitir configuración básica, ir directo a guías de estilo corporativas (Google Developer Documentation Style Guide).

---

### MÓDULO 1: Principios de Escritura Técnica

**Duración**: 1.5 horas
**Objetivo**: Aplicar las reglas de oro de la escritura técnica: claridad, concisión y estructura.

#### TEMA 1.1: Claridad y Estilo

**Objetivo del Tema**: Eliminar ambigüedad y ruido en el texto.

- **Subtema 1.1.1**: Eliminación de voz pasiva y palabras vacías

  - Objetivo: Reescribir oraciones complejas a voz activa.
  - Tipo: Práctica
  - Requiere Código: No

- **Subtema 1.1.2**: Estructura de pirámide invertida
  - Objetivo: Organizar información para lectura rápida (skimmable).
  - Tipo: Teoría

#### TEMA 1.2: Audiencia y Contexto

- **Subtema 1.2.1**: Mapeo de Audiencia (Usuario vs. Mantenedor)
  - Objetivo: Adaptar el tono y profundidad técnica según el lector.
  - Tipo: Práctica

---

### MÓDULO 2: Documentación en el Código

**Duración**: 2 horas
**Objetivo**: Producir artefactos de documentación que vivan junto al código y se mantengan actualizados.

#### TEMA 2.1: Comentarios y Docstrings Pragmáticos

- **Subtema 2.1.1**: El "Por qué" sobre el "Qué"
  - Objetivo: Escribir comentarios que expliquen decisiones, no sintaxis.
  - Tipo: Práctica (Refactoring de comentarios)
  - Requiere Código: Sí

#### TEMA 2.2: The Almighty README

- **Subtema 2.2.1**: Estructura de un README ganador
  - Objetivo: Crear un README que permita levantar el proyecto en <5 min.
  - Tipo: Práctica
  - Requiere Código: Sí (Markdown)

---

### MÓDULO 3: Documentación de Diseño y Arquitectura

**Duración**: 2.5 horas
**Objetivo**: Estructurar y comunicar decisiones técnicas complejas a stakeholders.

#### TEMA 3.1: RFCs (Request for Comments) y Design Docs

- **Subtema 3.1.1**: Anatomía de un Design Doc
  - Objetivo: Redactar Contexto, Alternativas Consideradas y Propuesta.
  - Tipo: Teórico/Práctico

#### TEMA 3.2: ADRs (Architecture Decision Records)

- **Subtema 3.2.1**: Implementando ADRs en el repositorio
  - Objetivo: Registrar decisiones inmutables de arquitectura usando herramientas CLI.
  - Tipo: Práctica
  - Requiere Código: Sí (adr-tools)

---

### MÓDULO 4: Comunicación en Crisis y Feedback

**Duración**: 2 horas
**Objetivo**: Mantener profesionalismo y claridad bajo presión o conflicto.

#### TEMA 4.1: Postmortems Blameless

- **Subtema 4.1.1**: Causa Raíz y Cronología
  - Objetivo: Redactar un reporte de incidente enfocado en el sistema, no las personas.
  - Tipo: Práctica (Estudio de caso)

#### TEMA 4.2: Code Reviews Empáticos

- **Subtema 4.2.1**: Comentarios accionables y no violentos
  - Objetivo: Formular críticas de código que inviten a la colaboración.
  - Tipo: Práctica

---

### MÓDULO 5: Proyecto Integrador Final

**Duración**: 1 horas
**Objetivo**: Crear el "Developer Portal" de una librería ficticia.

### Especificaciones del proyecto

- **Alcance**: Documentar una librería de procesamiento de pagos legacy.
- **Entregables**:
  1. README optimizado.
  2. 1 ADR explicando una refactorización.
  3. Guía de Contribución (CONTRIBUTING.md).
- **Criterios de evaluación**: Linter de prosa pasando (Vale), claridad en ADR, completitud de README.

---

## MATRIZ DE TRAZABILIDAD

| Módulo    | Conceptos    | Objetivos Bloom | Evaluaciones | Tiempo (h) |
| --------- | ------------ | --------------- | ------------ | ---------- |
| 0         | Nivelación   | Recordar        | Check Config | 1          |
| 1         | Estilo       | Aplicar         | Rewrite Quiz | 1.5        |
| 2         | Code Docs    | Crear           | Code Review  | 2          |
| 3         | Arch Docs    | Analizar        | RFC Draft    | 2.5        |
| 4         | Soft Skills  | Evaluar         | Sims         | 2          |
| 5         | Proyecto     | Crear           | Portfolio    | 1          |
| **TOTAL** | **Docs Eng** | **-**           | **Product**  | **10**     |

---

## ESTRUCTURA JSON (Para Agente Manager)

```json
[
  {
    "modulo_id": 0,
    "titulo": "Diagnóstico y Nivelación",
    "temas": [
      {
        "tema_id": "0.1",
        "titulo": "La falacia de la documentación automática",
        "subtemas": [
          {
            "subtema_id": "0.1.1",
            "titulo": "Cuándo el código limpio no basta"
          },
          {
            "subtema_id": "0.1.2",
            "titulo": "Herramientas del escritor técnico"
          }
        ]
      }
    ]
  },
  {
    "modulo_id": 1,
    "titulo": "Principios de Escritura Técnica",
    "temas": [
      {
        "tema_id": "1.1",
        "titulo": "Claridad y Estilo",
        "subtemas": [
          { "subtema_id": "1.1.1", "titulo": "Eliminación de voz pasiva" },
          {
            "subtema_id": "1.1.2",
            "titulo": "Estructura de pirámide invertida"
          }
        ]
      },
      {
        "tema_id": "1.2",
        "titulo": "Audiencia y Contexto",
        "subtemas": [
          { "subtema_id": "1.2.1", "titulo": "Usuario vs. Mantenedor" }
        ]
      }
    ]
  },
  {
    "modulo_id": 2,
    "titulo": "Documentación en el Código",
    "temas": [
      {
        "tema_id": "2.1",
        "titulo": "Comentarios y Docstrings",
        "subtemas": [
          { "subtema_id": "2.1.1", "titulo": "El Por Qué sobre el Qué" }
        ]
      },
      {
        "tema_id": "2.2",
        "titulo": "The Almighty README",
        "subtemas": [
          { "subtema_id": "2.2.1", "titulo": "Estructura de un README ganador" }
        ]
      }
    ]
  },
  {
    "modulo_id": 3,
    "titulo": "Documentación de Diseño y Arquitectura",
    "temas": [
      {
        "tema_id": "3.1",
        "titulo": "RFCs y Design Docs",
        "subtemas": [
          { "subtema_id": "3.1.1", "titulo": "Anatomía de un Design Doc" }
        ]
      },
      {
        "tema_id": "3.2",
        "titulo": "ADRs (Architecture Decision Records)",
        "subtemas": [{ "subtema_id": "3.2.1", "titulo": "Implementando ADRs" }]
      }
    ]
  },
  {
    "modulo_id": 4,
    "titulo": "Comunicación en Crisis y Feedback",
    "temas": [
      {
        "tema_id": "4.1",
        "titulo": "Postmortems Blameless",
        "subtemas": [
          { "subtema_id": "4.1.1", "titulo": "Causa Raíz y Cronología" }
        ]
      },
      {
        "tema_id": "4.2",
        "titulo": "Code Reviews Empáticos",
        "subtemas": [
          { "subtema_id": "4.2.1", "titulo": "Comentarios accionables" }
        ]
      }
    ]
  },
  {
    "modulo_id": 5,
    "titulo": "Proyecto Integrador Final",
    "temas": [
      {
        "tema_id": "5.1",
        "titulo": "Developer Portal Mockup",
        "subtemas": [
          { "subtema_id": "5.1.1", "titulo": "Ejecución del Proyecto" }
        ]
      }
    ]
  }
]
```
