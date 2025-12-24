# TEMA 2.2.1. ESTRUCTURA DE UN README GANADOR

**Tiempo estimado**: 30 minutos
**Nivel**: Intermedio
**Prerrequisitos**: Tema 1.2.1 (Usuario vs Mantenedor)

## ¿Por qué importa este concepto?

El README es la **Landing Page** de tu código.
Es lo primero que ve un desarrollador en GitHub. Es tu única oportunidad para causar una buena impresión.
Un mal README grita "Proyecto abandonado" o "Difícil de usar". Un buen README convierte visitantes en usuarios (o colaboradores).

Tienes aproximadamente **10 segundos** de la atención del lector para responder dos preguntas:

1. ¿Qué hace esto?
2. ¿Cómo lo hago correr en mi máquina?

## Conexión con conocimientos previos

Aplicamos la **Pirámide Invertida** (Tema 1.1.2) y el **Mapeo de Audiencia** (Tema 1.2.1).

* *Pirámide*: Pon el propósito y el "Quickstart" arriba. Mueve la configuración avanzada abajo.
* *Audiencia*: La mayoría de los lectores del README son **Usuarios** que quieren probarlo, no **Mantenedores** que quieren compilarlo desde cero.

---

## Comprensión intuitiva

Imagina que entras a una tienda de Apple (Landing Page).

* **Lo que ves**: Mesas con productos listos para usar (El "Qué" y el "Cómo").
* **Lo que no ves**: Los planos eléctricos de la tienda o el reglamento de los empleados (El "Internals").

Tu README debe sentirse como la tienda, no como el almacén.

---

## Definición formal

Un README efectivo debe contener, en orden de prioridad:

1. **Nombre y One-Liner**: Qué es.
2. **Badges**: Estado del build, versión, licencia (Prueba social).
3. **Descripción / Problema**: Qué soluciona.
4. **Quick Start**: El camino más corto para ver el "Hello World".
5. **Features**: Lista de capacidades clave.
6. **Configuración**: Opciones avanzadas.

---

## Implementación práctica

### Anatomía de un README Perfecto

```markdown
# 🚀 RocketLib (El Título)

> La librería más rápida para enviar cohetes a Marte en Python. (El One-Liner)

[![Build Status](...)](...) [![License](...)](...) (Badges)

## ¿Por qué usar RocketLib? (El Gancho)
Las librerías actuales son lentas. RocketLib usa Rust por debajo para lograr...

## Instalación (La Acción)
```bash
pip install rocket-lib
```

## Quick Start (El "Hello World")

```python
import rocket

rocket.launch(target="Mars")
# > 🚀 Despegando en 3, 2, 1...
```

## Configuración Avanzada (La Cola de la Pirámide)

...

```

### El Anti-Patrón: "El Muro de Texto"

*   Empezar con la historia del proyecto. "Este proyecto nació en 2019 cuando..." (A nadie le importa aún).
*   Empezar con los requisitos de compilación. "Instala GCC v9, Make v4..." (Aburrido. Solo quiero usarlo).

### El Patrón: "Zero to Hero"

Tu sección de instalación debe ser copiables y pegables.
*   *Mal*: "Descarga el código y compílalo."
*   *Bien*:
    ```bash
    git clone ...
    cd ...
    ./install.sh
    ```

---

## Resumen del concepto

**En una frase**: Trata a tu README como un producto de marketing. Vende la solución y facilita la adopción inmediata.

**La Regla de los 10 Segundos**: Si no puedo ejecutar tu código en 10 segundos (o entender qué hace), cerraré la pestaña.

**Siguiente paso**: Generación de Ejercicios para auditar READMEs reales.
