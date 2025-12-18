# TEMA 1.1.1: ELIMINACIÓN DE VOZ PASIVA

**Tiempo estimado**: 30 minutos
**Nivel**: Intermedia
**Prerrequisitos**: Conceptos de Módulo 0 (Agencia gramatical)

## ¿Por qué importa este concepto?

En la documentación técnica, la ambigüedad se considera un defecto crítico (bug). Cuando se escribe una frase como "Los datos fueron procesados", se oculta información vital para el lector: ¿Quién o qué procesó los datos? ¿Fue el usuario manualmente? ¿El backend automáticamente? ¿Un proceso en segundo plano?

La **Voz Pasiva** diluye la responsabilidad y aumenta lo que llamamos "carga cognitiva": el esfuerzo mental necesario para procesar la información. Al eliminarla, logramos tres objetivos fundamentales de ingeniería:

1. **Precisión**: Se define explícitamente el actor del sistema.
2. **Concisión**: Las oraciones activas son, en promedio, un 20-30% más cortas.
3. **Accionabilidad**: El usuario sabe exactamente qué debe hacer o qué esperar del sistema.

**Ejemplo real**: En la documentación de plataformas como Stripe o Google Cloud, raramente encontrará construcciones como "El pago es recibido". En su lugar, encontrará "Stripe recibe el pago".

## Conexión con conocimientos previos

En el Módulo 0 establecimos que la escritura técnica busca la ruta más eficiente para transmitir información. Podemos usar la analogía de la complejidad algorítmica:

* La **Voz Activa** es una operación de complejidad constante ($O(1)$): el cerebro conecta "Sujeto > Acción" (Acceso directo).
* La **Voz Pasiva** es una operación más costosa, similar a $O(n^2)$, porque obliga al cerebro a buscar en el contexto quién realizó la acción.

---

## Comprensión intuitiva

Para los desarrolladores, es útil pensar en la gramática como si fuera código:

* **Voz Pasiva** es comparable a ejecutar una función anónima sin argumentos claros: `process_stuff()`. ¿Qué entra? ¿Qué contexto usa? El comportamiento es opaco.
* **Voz Activa** es comparable a una función con tipos explícitos: `User.click(Button)`. La estructura es `Sujeto -> Verbo -> Objeto`.

### Ejemplo motivador

Imagine que un desarrollador lee lo siguiente en un archivo README:

> "La configuración debe ser actualizada antes del despliegue."

El desarrollador se detiene y pregunta: "¿Por quién? ¿Debo hacerlo yo manualmente? ¿Lo hace el pipeline de CI/CD automáticamente?". Esta duda detiene el flujo de trabajo y puede provocar errores en producción.

---

## Definición formal

La **Voz Activa** sigue una estructura gramatical directa y lineal:
$$ Sujeto + Verbo + Objeto $$

La **Voz Pasiva** invierte esta estructura, convirtiendo al objeto de la acción en el sujeto gramatical, generalmente introduciendo el verbo auxiliar "ser":
$$ Objeto + ser + participio (+ por + Agente) $$

### Propiedades fundamentales

1. **Agencia Explícita**: El actor siempre precede a la acción.
2. **Direccionalidad**: El flujo de información es lineal (de izquierda a derecha).
3. **Economía Léxica**: Elimina verbos auxiliares innecesarios como "fue", "ha sido" o "es".

---

## Implementación práctica

En ingeniería de software no siempre es posible evitar la voz pasiva (a veces el actor es irrelevante), pero debemos refactorizar agresivamente cuando la acción es crítica.

### Algoritmo de Refactorización

Para corregir frases pasivas, siga este procedimiento paso a paso:

1. **Detectar**: Busque construcciones del tipo "ser + participio" (ejemplos: es hecho, fue enviado, será cancelado).
2. **Identificar Agente**: Pregúntese "¿Quién realiza la acción?".
3. **Reubicar**: Mueva ese Agente al inicio de la oración.
4. **Eliminar Auxiliares**: Borre los verbos auxiliares "ser" o "estar".

### Ejemplos de Refactorización (Antes vs. Después)

#### Caso 1: Instrucciones al Usuario

**Pasiva (Incorrecto):**
> "El botón 'Deploy' deberá ser presionado cuando los tests hayan pasado."
> *Problema: Ambigüedad. ¿Es automático o manual?*

**Activa (Correcto):**
> "Presione el botón 'Deploy' una vez que pasen los tests."
> *Solución: Instrucción imperativa directa al lector.*

#### Caso 2: Descripción del Sistema

**Pasiva (Incorrecto):**
> "Una excepción es lanzada por el servidor si el token es inválido."
> *Problema: Excesivamente largo (12 palabras).*

**Activa (Correcto):**
> "El servidor lanza una excepción si el token es inválido."
> *Solución: Conciso (9 palabras). Ahorro del 25% de texto.*

---

## Práctica Guiada

Intente refactorizar este párrafo técnico común:

**Texto Original (Legacy):**
"Los logs son rotados cada 24 horas por el sistema. Si el espacio en disco es excedido, una alerta será enviada al administrador."

**Análisis de Refactorización:**

1. *Segmento 1*: "son rotados por el sistema" -> Agente identificado: "el sistema".
2. *Segmento 2*: "espacio es excedido" -> Agente implícito: "los logs".
3. *Segmento 3*: "alerta será enviada" -> Agente: "el sistema".

**Texto Refactorizado:**
"El sistema rota los logs cada 24 horas. Si los logs exceden el espacio en disco, el sistema envía una alerta al administrador."

---

## Errores frecuentes

### Error 1: La pasiva "Zombie"

Ocurre cuando se oculta al actor deliberadamente para no sonar "agresivo" o directo.

* *Incorrecto*: "Se cometieron errores en la migración." (Nadie asume la culpa).
* *Correcto*: "El equipo subestimó la carga en la migración." (Honestidad y responsabilidad).

### Error 2: Confundir Pasiva con Estado

No toda construcción "ser + participio" es pasiva. A veces describe un estado del sistema.

* *Válido*: "El sistema está caído." (Esto describe un estado, no una acción pasiva).

---

## Resumen del concepto

**En una frase**: Coloque al actor (Sujeto) antes de la acción (Verbo) para eliminar dudas sobre la responsabilidad.

**Cuándo usarlo**: En la gran mayoría instrucciones, descripciones de procesos y mensajes de error.

**Excepción**: Úsela solo cuando el actor es desconocido o irrelevante (ejemplo: "La función fue deprecada en v2.0", donde no importa qué desarrollador específico la deprecor).

**Siguiente paso**: Estructura de pirámide invertida (Tema 1.1.2).
