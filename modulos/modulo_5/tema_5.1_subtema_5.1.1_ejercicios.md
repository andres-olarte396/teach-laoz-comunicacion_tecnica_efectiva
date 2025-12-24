# BANCO DE EJERCICIOS: MÓDULO 5 - POSTMORTEMS

## METADATA

- **Módulo**: Comunicación en Crisis y Feedback
- **Objetivos evaluados**:
  1. Aplicar la técnica de los "5 Porqués".
  2. Detectar y corregir lenguaje culposo (Blame).
  3. Redactar Action Items sistémicos.
- **Tiempo total estimado**: 25 minutos
- **Nivel**: Intermedio

---

## EJERCICIO 1. Los 5 Porqués

### ENUNCIADO

**Incidente**: La facturación mensual falló para el 30% de los usuarios.
**Causa Inmediata**: El proceso batch de facturación se quedó sin memoria (OOM).

Aplica 5 niveles de profundidad para encontrar la Causa Raíz.
*(Usa tu imaginación técnica para rellenar los huecos)*.

1. **¿Por qué falló por memoria?** -> *R: Porque cargó todos los usuarios en memoria a la vez.*
2. **¿Por qué cargó todos los usuarios?** -> *R: ...*
3. **¿Por qué...?** -> *R: ...*
4. **¿Por qué...?** -> *R: ...*
5. **¿Por qué...? (Causa Raíz)** -> *R: ...*

### SOLUCIÓN MODELO

1. Porque cargó todos los usuarios en un array.
2. **¿Por qué?**: Porque el código usaba `User.all()` sin paginación.
3. **¿Por qué?**: Porque el dev asumió que había pocos usuarios (como en local).
4. **¿Por qué?**: Porque no probó con un dataset de tamaño producción.
5. **¿Por qué?**: Porque **Staging no tiene datos seed automatizados** que repliquen el volumen de Prod. (Causa Raíz).

---

## EJERCICIO 2: El Detector de Culpa

### ENUNCIADO

Convierte estas frases de "Culpables" a "Sistémicas".

1. "María se olvidó de renovar el certificado SSL."
2. "El intern borró la base de datos de producción por error."
3. "Nadie revisó el PR con suficiente atención."

### SOLUCIÓN

1. "El sistema de monitoreo no alertó sobre la expiración inminente del certificado SSL con suficiente antelación."
2. "La base de datos de producción era accesible con permisos de escritura desde la terminal de un usuario sin MFA, y no había protección contra borrado masivo."
3. "El proceso de CI/CD permitió mergear código sin requerir la aprobación explícita de un CODEOWNER."

---

## EJERCICIO 3: Action Items Reales

### ENUNCIADO

Para el incidente del Ejercicio 1 (OOM en facturación), escribe 2 Action Items.
- Uno debe ser **Mitigación Inmediata**.
- Uno debe ser **Prevención Definitiva**.

### SOLUCIÓN MODELO

1. **Inmediata**: Refactorizar el script para usar paginación (batch size: 1000) y liberar memoria en cada iteración. (Dueño: Tech Lead. Fecha: Hoy).
2. **Preventiva**: Crear un script de "Data Seeding" en Staging que genere 1 millón de usuarios dummy para testear rendimiento antes de cada release. (Dueño: DevOps. Fecha: Próximo Sprint).

---

## AUTOEVALUACIÓN

- [ ] ¿He evitado usar nombres de personas en mis respuestas?
- [ ] ¿Mis soluciones requieren que la gente "tenga más cuidado" (Mal) o cambian el sistema (Bien)?
