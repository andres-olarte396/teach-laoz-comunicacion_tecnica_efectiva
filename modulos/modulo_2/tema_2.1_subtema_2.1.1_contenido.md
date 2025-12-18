# TEMA 2.1.1: COMENTARIOS Y DOCSTRINGS (EL POR QUÉ)

**Tiempo estimado**: 25 minutos
**Nivel**: Básico
**Prerrequisitos**: Tema 1.2.1 (Usuario vs Mantenedor)

## ¿Por qué importa este concepto?

El código explica el **Qué** y el **Cómo**. Los comentarios solo deben existir para explicar el **Por Qué**.

Un comentario que repite lo que dice el código es ruido ("Code Smell"). Un comentario que explica una decisión de negocio compleja o una trampa oculta es oro puro.
Tu objetivo es escribir código que no necesite comentarios, y luego escribir comentarios donde el código no sea suficiente.

## Conexión con conocimientos previos

En el Módulo 1.2.1 aprendimos sobre "Caja Negra" vs "Caja Blanca".

* **Docstrings (Caja Negra)**: Para el Usuario. Explican el contrato (inputs/outputs).
* **Comentarios Inline (Caja Blanca)**: Para el Mantenedor. Explican la implementación (hacks, optimizaciones).

---

## Comprensión intuitiva

Piensa en los subtítulos de una película.

* **Mal comentario**: (Personaje abre la puerta) -> Subtítulo: "Abre la puerta". (Obvio, redundante).
* **Buen comentario**: (Personaje duda antes de abrir) -> Subtítulo: "*Teme que el asesino esté dentro*". (Contexto invisible).

El código es la acción. El comentario es el contexto invisible.

---

## Definición formal

1. **Comentario Pragmático**: Aporta información que no existe en la sintaxis del lenguaje (intención, limitaciones de negocio, referencias a tickets de Jira).
2. **Docstring (Documentation String)**: Texto estructurado asociado a una función/clase que describe su interfaz pública.

### La Regla de Oro
>
> "No comentes código malo; reescríbelo." — Brian Kernighan

Antes de escribir `// Calcula el total`, renombra la variable `t` a `total_invoice_amount`.

---

## Implementación práctica

### Caso 1: El comentario redundante (Anti-patrón)

```python
# Incrementa i en 1
i = i + 1  

# Función que obtiene usuarios
def get_users():
    ...
```

*Crítica*: El lector sabe leer código. Esto insulta su inteligencia y añade deuda de mantenimiento (si el código cambia, el comentario miente).

### Caso 2: El comentario de "Por Qué" (Patrón)

```python
# Usamos un sleep de 2s porque la API de legacy-bank 
# tiene una race condition si reintentamos inmediatamente.
# Ver Ticket JIRA-1234.
time.sleep(2)
```

*Valor*: Explicación crítica. Si borras el sleep para "optimizar", rompes la integración.

### Caso 3: Docstrings Estructurados

Usa formatos estándar (Google, NumPy, Sphinx) para que los IDEs ayuden al usuario.

```python
def connect_db(timeout: int = 30) -> Connection:
    """
    Establece conexión con la base de datos principal.

    Args:
        timeout: Segundos máximos de espera. Si excede, lanza TimeoutError.
                 PRECAUCIÓN: No usar >60s en prod para evitar bloqueos de gunicorn.

    Returns:
        Objeto Connection activo.
    """
```

---

## Guía de Estilo Rápida

1. **TODOs**: Úsalos para deuda técnica reconocida. `// TODO(autor): Refactorizar esto cuando migremos a v2`.
2. **Hacks**: Admite cuando el código es feo. `// FIXME: Solución temporal. Esto es O(n^2), mover a worker en el futuro`.
3. **Referencias**: Linkea a StackOverflow o Docs oficiales. `// Adaptado de: https://stackoverflow.com/...`

---

## Resumen del concepto

**En una frase**: El código dice qué hace. Los comentarios dicen por qué lo hace así (y por qué no de otra forma).

**Cuándo comentar**: Cuando tomaste una decisión no obvia, cuando hay un bug conocido de una librería externa, o cuando la lógica es matemáticamente compleja.

**Siguiente paso**: El README (El documento más importante de tu repositorio).
