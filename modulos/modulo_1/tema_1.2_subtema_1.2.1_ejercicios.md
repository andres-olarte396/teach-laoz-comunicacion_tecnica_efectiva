# BANCO DE EJERCICIOS: MÓDULO 1 - MAPEO DE AUDIENCIA

## METADATA

- **Módulo**: Principios de Escritura Técnica
- **Objetivos evaluados**:
  1. Diferenciar necesidades de Usuario vs. Mantenedor.
  2. Identificar el nivel de abstracción adecuado por audiencia.
  3. Reescribir contenido técnico para diferentes stakeholders.
- **Tiempo total estimado**: 20 minutos
- **Nivel**: Intermedio

---

## EJERCICIO 1. Clasificación de Documentos

### ENUNCIADO

Clasifica los siguientes fragmentos según su audiencia ideal: **(U) Usuario** o **(M) Mantenedor**.

1. "La función `retry_logic` usa un backoff exponencial para no saturar el servidor aguas arriba."
2. "Para obtener un API Key, navega a Settings > Developer Tools y haz clic en 'Generate New Key'."
3. "Advertencia: Cambiar el tamaño del pool de conexiones requiere reiniciar la instancia."
4. "Migramos de Axios a Fetch porque Axios añadía 15kb al bundle size innecesariamente."
5. "Este endpoint devuelve código 429 si haces más de 100 peticiones por minuto."

### SOLUCIÓN

1. **(M)**. Explica el *cómo* interno y la justificación de estabilidad.
2. **(U)**. Instrucción paso a paso de uso.
3. **(U)**. Advertencia operativa para quien administra el sistema.
4. **(M)**. Justificación de decisión técnica/arquitectura.
5. **(U)**. Contrato de interfaz (Límite de uso).

---

## EJERCICIO 2: El Camaleón Técnico

### ENUNCIADO

Tienes un incidente: "La base de datos se cayó por falta de disco".
Escribe un mensaje de 1 línea para cada una de las siguientes audiencias:

1. **Usuario Final** (Cliente de la app).
2. **CTO / Manager** (Negocio).
3. **Equipo de DevOps** (Técnico).

### SOLUCIÓN MODELO

1. **Usuario Final**: "Estamos experimentando problemas de conexión. El servicio volverá pronto."
   *(Caja Negra: No mencionar "disco" ni "base de datos").*

2. **CTO / Manager**: "Incidente crítico en DB principal. Causa: Disco lleno. ETA de solución: 15 mins."
   *(Impacto y Tiempo: Lo que importa al negocio).*

3. **DevOps**: "PostgreSQL master `disk_usage` al 100% en `/var/lib/postgresql`. Necesitamos purgar logs o extender el volumen EBS."
   *(Caja Blanca: Detalles accionables y técnicos).*

---

## EJERCICIO 3: Depuración de Documentación

### ENUNCIADO

Este párrafo está en la guía de "Primeros Pasos" (Onboarding de Usuario). Identifica la frase que **LEAKS INTERNALS** (fuga detalles de implementación) y reescríbela.

> "Para crear una cuenta, envía un POST a `/signup`. El sistema validará tu email usando una Regex compleja que importamos de la librería `email-validator` v2.0 para asegurar que no sea un dominio temporal. Si es válido, recibirás un 201 Created."

### SOLUCIÓN

**Fuga**: "usando una Regex compleja que importamos de la librería `email-validator` v2.0..."
**Por qué**: Al usuario no le importa qué librería usas.
**Refactor**: "El sistema validará que tu email tenga un formato correcto y no pertenezca a un dominio temporal."

---

## AUTOEVALUACIÓN

- [ ] ¿Antes de escribir, me pregunto "¿Qué quiere lograr el lector?"?
- [ ] ¿Sé ocultar la complejidad innecesaria para el usuario final?
