# BANCO DE EJERCICIOS: MÓDULO 2 - ESTRUCTURA DE README

## METADATA

- **Módulo**: Documentación en el Código
- **Objetivos evaluados**:
  1. Auditar READMEs usando la regla de los 10 segundos.
  2. Redactar "Hooks" (Ganchos) efectivos.
  3. Diferenciar entre Quickstart y Configuración Avanzada.
- **Tiempo total estimado**: 20 minutos
- **Nivel**: Intermedio

---

## EJERCICIO 1: Auditoría de 10 Segundos

### ENUNCIADO

Abre el último README que escribiste (o un repositorio open source al azar). Cronometra 10 segundos.
Intenta responder estas 3 preguntas:

1. ¿Qué problema resuelve este proyecto?
2. ¿Cuál es el comando para instalarlo?
3. ¿Cuál es el estado del build (funciona o no)?

**Diagnóstico**:

- Si fallaste la #1: Te falta un "One-Liner" claro al inicio.
- Si fallaste la #2: Tu sección de instalación "entierra el lede" o no tienes bloques de código copiables.
- Si fallaste la #3: Te faltan Badges de estado.

---

## EJERCICIO 2: El Gancho (The Hook)

### ENUNCIADO

Transforma la siguiente descripción genérica en un "Gancho" de producto atractivo.

**Original (Aburrido):**
> "Esta es una librería escrita en Python que permite a los usuarios manipular archivos CSV de manera rápida utilizando multiprocesamiento. Fue creada en 2023."

**Tu Misión**:

- Escribe un Título.
- Escribe un One-Liner (Slogan).
- Escribe un bloque de "Por qué usar esto".

### SOLUCIÓN MODELO

```markdown
# ⚡ TurboCSV

> Manipulación de CSVs 10x más rápida usando todos tus núcleos de CPU.

## ¿Por qué TurboCSV?
Las librerías estándar como `pandas` son lentas cargando terabytes de datos.
TurboCSV usa multiprocesamiento nativo para parsear archivos gigantes en segundos, no horas.
```

---

## EJERCICIO 3: Ordenando la Casa

### ENUNCIADO

Ordena las siguientes secciones para un README ideal (de arriba a abajo):

A. Créditos y Agradecimientos a los autores.
B. Comando `npm install fast-logger`.
C. Explicación detallada de la arquitectura interna de la clase Logger.
D. Título y Descripción corta.
E. Ejemplo de uso: `logger.log("Hola")`.

### SOLUCIÓN

1. **D** (Título/Descripción): Lo primero que ves.
2. **B** (Instalación): La acción inmediata.
3. **E** (Ejemplo): Verlo funcionar ("Quickstart").
4. **C** (Arquitectura): Para mantenedores (Caja Blanca), va después.
5. **A** (Créditos): Al final (La cola de la pirámide).

---

## AUTOEVALUACIÓN

- [ ] ¿Mi README tiene bloques de código (` ```bash `) listos para copiar?
- [ ] ¿El primer párrafo explica el valor, no la historia?
