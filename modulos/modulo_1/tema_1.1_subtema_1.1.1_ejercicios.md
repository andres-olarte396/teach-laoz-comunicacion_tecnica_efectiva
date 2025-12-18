# BANCO DE EJERCICIOS: MÓDULO 1 - ELIMINACIÓN DE VOZ PASIVA

## METADATA

- **Módulo**: Principios de Escritura Técnica
- **Objetivos evaluados**:
  1. Identificar construcciones pasivas.
  2. Transformar oraciones pasivas a activas sin perder significado.
  3. Aplicar criterio de agencia en párrafos complejos.
- **Tiempo total estimado**: 25 minutos
- **Tipo**: Formativa
- **Nivel de ruta**: Intermedia

---

## EJERCICIO 1: Detección de Agentes Ocultos

### METADATA

- **ID**: `EJ-MOD1-001`
- **Dificultad**: ⭐ Básico
- **Tiempo estimado**: 5 minutos
- **Nivel Bloom**: Recordar/Comprender
- **Tipo**: Análisis gramatical

### ENUNCIADO

Identifica cuáles de las siguientes oraciones están en **Voz Pasiva** y subraya el verbo auxiliar ("ser").

1. "El servidor de integración continua ha compilado el proyecto exitosamente."
2. "Los errores fueron ignorados por el script de migración."
3. "La base de datos será restaurada automáticamente a las 03:00 AM."
4. "Estamos monitorizando la latencia del API Gateway."
5. "Se ha decidido deprecar la versión 1.0 de la librería."

### RESPUESTA MODELO

1. **Activa**. (Sujeto: El servidor).
2. **Pasiva**. ("**fueron** ignorados"). Agente: script de migración.
3. **Pasiva**. ("**será** restaurada"). Agente: Oculto/Implícito (el sistema).
4. **Activa**. (Sujeto implícito: Nosotros/El equipo).
5. **Pasiva**. ("**ha** decidido" -> Forma impersonal "Se"). Agente: Oculto (El equipo de producto).

---

## EJERCICIO 2: Refactorización Atómica

### METADATA

- **ID**: `EJ-MOD1-002`
- **Dificultad**: ⭐⭐ Intermedio
- **Tiempo estimado**: 10 minutos
- **Nivel Bloom**: Aplicar
- **Tipo**: Reescritura

### ENUNCIADO

Reescribe las siguientes oraciones técnicas para usar **Voz Activa**. Si el agente no es explícito, infiere uno lógico (ej: "el sistema", "el usuario", "el administrador").

**Input:**

1. "El acceso es denegado si la contraseña es introducida incorrectamente tres veces."
2. "Un correo de confirmación será enviado al usuario una vez que el pago sea procesado."
3. "Los datos son encriptados por el cliente antes de ser enviados al servidor."

### SOLUCIÓN MODELO

1. **Input**: "El acceso es denegado si la contraseña es introducida incorrectamente tres veces."
   **Solución**: "El sistema deniega el acceso si el usuario introduce la contraseña incorrectamente tres veces."
   *(Cambio: Agregamos "El sistema" y "el usuario").*

2. **Input**: "Un correo de confirmación será enviado al usuario una vez que el pago sea procesado."
   **Solución**: "El sistema envía un correo de confirmación al usuario una vez que procesa el pago."
   *(Cambio: Eliminamos "será" y unificamos la acción).*

3. **Input**: "Los datos son encriptados por el cliente antes de ser enviados al servidor."
   **Solución**: "El cliente encripta los datos antes de enviarlos al servidor."
   *(Cambio: "El cliente" pasa al inicio).*

---

## EJERCICIO 3: El "Postmortem" Pasivo

### METADATA

- **ID**: `EJ-MOD1-003`
- **Dificultad**: ⭐⭐⭐ Avanzado
- **Tiempo estimado**: 10 minutos
- **Nivel Bloom**: Evaluar/Crear
- **Tipo**: Edición de párrafo

### ENUNCIADO

El siguiente fragmento de un Postmortem oculta responsables y acciones clave. Reescríbelo en voz activa para clarificar la cronología del incidente.

**Texto Original (Pasivo):**
> "A las 14:00, una caída en la latencia fue detectada por el equipo de SRE. Una investigación fue iniciada. Se descubrió que una configuración errónea había sido aplicada al balanceador de carga. La configuración fue revertida y el servicio fue restaurado a las 14:15."

**Tarea:**

1. Identificar los agentes (SRE, configuración, balanceador).
2. Reescribir en voz activa.
3. Mantener el tono profesional (sin culpar, solo reportar hechos).

### RÚBRICA DE EVALUACIÓN

| Criterio | Puntos | Descripción |
| :--- | :--- | :--- |
| **Agencia** | 40% | Todos los verbos principales tienen sujeto explícito. |
| **Concisión** | 30% | El texto resultante es más corto o igual en longitud. |
| **Claridad** | 30% | La secuencia causa-efecto es lineal. |

### SOLUCIÓN MODELO

> "A las 14:00, el equipo de SRE detectó una caída en la latencia e inició una investigación. El equipo descubrió que alguien aplicó una configuración errónea al balanceador de carga. SRE revirtió la configuración y restauró el servicio a las 14:15."

*(Nota: En un entorno real "blameless", podríamos usar "El sistema tenía una configuración errónea", pero la acción de "aplicar" y "revertir" debe ser activa).*

### ERRORES COMUNES

#### ❌ Error: La Pasiva defensiva
>
> "Se cometió un error en la configuración."
**Diagnóstico**: Miedo a señalar la causa.
**Corrección**: "Una configuración errónea causó el fallo." (El objeto inanimado puede ser el sujeto activo).

---

## AUTOEVALUACIÓN

- [ ] ¿Entiendo la diferencia entre sujeto gramatical y actor lógico?
- [ ] ¿Puedo reducir el conteo de palabras eliminando "ser/estar"?
- [ ] ¿Sé cuándo es aceptable usar la pasiva (ej. actor desconocido)?
