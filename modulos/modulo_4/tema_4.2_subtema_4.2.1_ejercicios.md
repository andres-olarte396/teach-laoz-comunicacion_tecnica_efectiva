# BANCO DE EJERCICIOS: MÓDULO 4 - ADRs

## METADATA

- **Módulo**: Documentación de Arquitectura
- **Objetivos evaluados**:
  1. Estructurar una decisión siguiendo el formato Nygard (Contexto, Decisión, Consecuencias).
  2. Identificar el impacto negativo (Trade-offs) de una decisión técnica.
  3. Diferenciar entre una "Preferencia Personal" y una "Decisión Arquitectónica".
- **Tiempo total estimado**: 25 minutos
- **Nivel**: Avanzado

---

## EJERCICIO 1: El Arquitecto de Caching

### ENUNCIADO

Tu equipo decidió implementar **Redis** para cachear las respuestas de la API de Productos.
Redacta la sección de **"Consecuencias"** de ese ADR.
- **Requisito**: Debes listar al menos 1 consecuencia positiva y 2 consecuencias negativas (riesgos).

### SOLUCIÓN MODELO
>
> **Consecuencias**
>
> - **Positivas**:
>   - Reducción de carga en la base de datos principal en un 80%.
>   - Tiempo de respuesta promedio baja de 200ms a 20ms.
> - **Negativas**:
>   - **Consistencia Eventual**: Los usuarios podrían ver precios viejos por hasta 5 minutos (TTL).
>   - **Complejidad Operativa**: Necesitamos mantener un clúster de Redis altamente disponible; si cae, la DB principal podría colapsar por el tráfico repentino (Thundering Herd).

---

## EJERCICIO 2: Arqueología de Software

### ENUNCIADO

Llegas a un proyecto y ves que todo el código está escrito en **Java 8**, aunque estamos en 2025. Nadie sabe por qué.
Escribe un ADR tipo "Retroactivo" para documentar este hecho y decidir qué hacer.

- **Título**: `ADR-005: Mantener vs Actualizar Java 8`
- **Decisión**: (Elige una: Actualizar a Java 17 o Mantener Java 8) y justifícala brevemente.

### SOLUCIÓN MODELO (Opción: Mantener)
>
> **Contexto**: El sistema usa librerías legacy `sun.misc.*` que fueron eliminadas en Java 9+.
> **Decisión**: Mantendremos Java 8 por los próximos 6 meses.
> **Justificación**: El costo de reescribir las dependencias legacy supera el beneficio de las nuevas features de Java 17 en este momento crítico de negocio.

---

## EJERCICIO 3: Detectando "Opiniones" disfrazadas de ADRs

### ENUNCIADO

Analiza este borrador de ADR y di por qué está mal:

> **Título**: Usar Linter
> **Contexto**: El código está feo.
> **Decisión**: Usaremos el linter de AIRBNB porque me gusta más que el Standard, odio no poner puntos y comas.
> **Consecuencias**: El código se verá mejor.

### CRÍTICA

1. **Contexto débil**: "El código está feo" es subjetivo. Debería hablar de consistencia o errores prevenibles.
2. **Decisión sesgada**: "Porque me gusta más" no es un argumento técnico válido. Debería comparar reglas objetivas o adopción en la comunidad.
3. **Falta de Consecuencias Negativas**: ¿Qué pasa con el código existente? ¿Habrá que arreglar 5000 archivos? ¿Romperá el build?

---

## AUTOEVALUACIÓN

- [ ] ¿He listado al menos una consecuencia negativa para mi decisión?
- [ ] ¿Es mi ADR inmutable (se entiende sin contexto externo)?
