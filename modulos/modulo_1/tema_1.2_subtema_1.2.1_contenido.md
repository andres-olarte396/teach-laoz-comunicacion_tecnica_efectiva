# TEMA 1.2.1. MAPEO DE AUDIENCIA

**Tiempo estimado**: 20 minutos
**Nivel**: Intermedio
**Prerrequisitos**: Tema 1.1.X (Claridad y Estructura)

## ¿Por qué importa este concepto?

El error #1 en documentación técnica no es la gramática, es la **Falta de Empatía**. Escribirle a un Senior Architect como si fuera un Junior, o explicarle a un Usuario Final cómo funciona la base de datos interna.

Si no defines tu audiencia, escribes para nadie.
Distinguir entre **Usuario** (quien usa tu código) y **Mantenedor** (quien arregla tu código) es la diferencia entre una librería exitosa y "abandonware".

## Conexión con conocimientos previos

En programación orientada a objetos, tenemos `public` (interfaz para el usuario) y `private` (implementación para el mantenedor).
La documentación debe respetar ese mismo encapsulamiento.

* **Docs de Usuario**: API pública. Contrato. Cómo se usa.
* **Docs de Mantenedor**: Internals. Lógica de negocio. Por qué se hizo así.

---

## Comprensión intuitiva

Imagina que compras un coche.

1. **Manual del Conductor (Usuario)**: Cómo arrancar, cómo poner aire acondicionado, qué gasolina usa. (Caja Negra).
2. **Manual de Taller (Mantenedor)**: Torque de los tornillos de la culata, diagrama eléctrico del alternador. (Caja Blanca).

Si el manual del conductor explicara el diagrama eléctrico en la página 1, nadie conduciría. Si el manual de taller solo dijera "gire la llave", nadie podría repararlo.

---

## Definición formal

El **Mapeo de Audiencia** es el proceso de identificar el modelo mental y las necesidades del lector antes de escribir.

### Matriz de Audiencia Técnica

| Dimensión | **USUARIO (Consumidor)** | **MANTENEDOR (Colaborador)** |
| :--- | :--- | :--- |
| **Objetivo** | Resolver un problema rápido. | Entender/Modificar el sistema. |
| **Perspectiva** | Caja Negra (Black Box). | Caja Blanca (White Box). |
| **Pregunta clave** | "¿Cómo hago X?" | "¿Por qué X funciona así?" |
| **Artefacto** | README, Guías, API Reference. | CONTRIBUTING, Architecture Docs, Comentarios inline. |

---

## Implementación práctica

### Algoritmo de Segmentación

Antes de escribir un documento, ejecuta este `switch`:

1. **Caso: README / Tutorial** -> **Modo Usuario**.
    * *Ocultar*: Detalles de implementación, dependencias internas, deuda técnica.
    * *Mostrar*: Instalación, configuración, ejemplos de uso (Happy Path).

2. **Caso: Design Doc / Pull Request** -> **Modo Mantenedor**.
    * *Ocultar*: Marketing, promesas vacías.
    * *Mostrar*: Trade-offs, riesgos, complejidad algorítmica ($O(n)$), alternativas rechazadas.

### Ejemplo Comparativo: Endpoint de Login

#### Versión Usuario (Swagger/Docs)
>
> **POST /login**
> Autentica un usuario y devuelve un JWT.
>
> * **Input**: `{user, pass}`
> * **Output**: `200 OK { token }`
> * **Error**: `401 Invalid Credentials`

*(Nota: Al usuario no le importa si usas un hash bcrypt o argon2, solo quiere su token).*

#### Versión Mantenedor (Comentario/Wiki interna)
>
> **Módulo de Autenticación**
> Usamos `bcrypt` con work factor 12.
> **Warning**: No aumentar el factor a >14 porque la latencia de login excede los 500ms y rompe el SLA.
> La validación de password ocurre *antes* de la conexión a DB para mitigar ataques DoS.

---

## Errores frecuentes

### Error 1. "Leaking Internals" (La Fuga)

Explicar la implementación en la guía de usuario.

* *Mal*: "Para guardar el archivo, instanciamos un `FileStream` con buffer de 4kb..."
* *Bien*: "Para guardar el archivo, llame a `save()`."

### Error 2: Asumir el contexto del autor

Escribir pensando que el lector lleva 6 meses en el proyecto.

* *Síntoma*: "Ejecuta el script de siempre."
* *Solución*: "Ejecuta `./scripts/deploy.sh`."

---

## Resumen del concepto

**En una frase**: Decide si estás escribiendo para quien *conduce* el coche (Usuario) o para quien *repara* el motor (Mantenedor), y no mezcles los manuales.

**Cuándo usarlo**: Siempre. Define tu audiencia en la primera línea mentalmente.

**Prerrequisito crítico**: Teoría de la Mente (capacidad de atribuir desconocimiento a otros).

**Siguiente paso**: Módulo 2 - Documentación en el Código (donde aplicaremos esto a Comentarios vs. Docstrings).
