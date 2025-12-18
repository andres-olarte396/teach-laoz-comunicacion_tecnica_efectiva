# BANCO DE EJERCICIOS: MÓDULO 1 - PIRÁMIDE INVERTIDA

## METADATA

- **Módulo**: Principios de Escritura Técnica
- **Objetivos evaluados**:
  1. Identificar "leads" enterrados en textos densos.
  2. Redactar resúmenes ejecutivos (TL;DR).
  3. Reestructurar actualizaciones de estado cronológicas.
- **Tiempo total estimado**: 20 minutos
- **Nivel**: Básico/Intermedio

---

## EJERCICIO 1: Arqueología del Lead

### ENUNCIADO

Lee el siguiente correo y subraya la única frase que realmente importa (el "Lead").

> "Hola equipo, espero que estén bien. Estuve revisando el ticket sobre la latencia en el dashboard. Hice varias pruebas de carga con JMeter y al principio todo parecía normal. Luego noté que el uso de CPU subía mucho en la instancia de reportes. Después de perfilar el código, vi que el bucle de generación de PDF no está paginado. Básicamente, el servidor se queda sin memoria cuando el reporte es grande. Así que **necesitamos posponer el lanzamiento de mañana** hasta arreglarlo."

### SOLUCIÓN

**Lead Enterrado**: "Necesitamos posponer el lanzamiento de mañana".

---

## EJERCICIO 2: El Arte del TL;DR

### ENUNCIADO

Tienes un RFC de 10 páginas proponiendo migrar de Jenkins a GitHub Actions. Escribe un bloque **TL;DR** de 3 líneas para poner al inicio del documento.

**Datos clave**:

- Costo: Ahorro de $500/mes.
- Esfuerzo: 2 sprints.
- Beneficio: Builds 40% más rápidos.
- Riesgo: Curva de aprendizaje del equipo.

### SOLUCIÓN MODELO

```markdown
## TL;DR
Propuesta para migrar CI/CD a GitHub Actions.
- **Beneficio**: Reducción del tiempo de build en 40% y ahorro de $500/mes.
- **Costo**: 2 sprints de ingeniería.
- **Recomendación**: Proceder con PoC en Q3.
```

---

## EJERCICIO 3: Refactorización de Status Report

### ENUNCIADO

Transforma este update de Slack cronológico en una Pirámide Invertida.

**Texto Original**:
> "@channel Ayer empecé a trabajar en la integración con la API de pagos. Leí la documentación y vi que cambió la autenticación. Intenté usar nuestras llaves viejas y fallaron. Tuve que generar nuevas llaves en el portal de developer. Luego actualicé las variables de entorno en staging. Finalmente pude hacer un pago de prueba. Así que la integración ya funciona en staging."

### SOLUCIÓN MODELO

> "@channel **Integración de Pagos completada en Staging**. ⭐
> Ya pueden probar el flujo de checkout en el entorno de pruebas.
>
> **Detalles**:
>
> - Se actualizaron las API Keys (el proveedor cambió el método de auth).
> - Variables de entorno `STRIPE_KEY` actualizadas en Staging."

---

## AUTOEVALUACIÓN

- [ ] ¿Mis correos empiezan con la conclusión?
- [ ] ¿Uso negritas para destacar la acción requerida?
