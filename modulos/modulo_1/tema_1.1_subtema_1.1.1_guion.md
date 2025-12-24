# GUIÓN: ELIMINACIÓN DE VOZ PASIVA

## FICHA TÉCNICA

- **Duración Estimada**: 4 minutos
- **Tono**: Profesional, Mentor Senior, Directo.
- **Conceptos**: Agencia, Voz Activa, Refactorización.

---

### 00:00 - INTRODUCCIÓN

**[LOCUTOR]**:
¡Hola! Bienvenido a la primera sesión práctica de *Comunicación Técnica Efectiva*.

*(Pausa breve)*

Quiero que imagines por un segundo que estás depurando código. Encuentras una función llamada `procesar_datos()`. No toma argumentos. No devuelve nada. Simplemente... existe. ¿Frustrante, verdad? No sabes qué entra, quién la llama, ni qué estado modifica.

Bueno... eso es exactamente lo que siente un usuario cuando lee una oración en **Voz Pasiva**.

Frases como *"Los datos fueron procesados"* son el equivalente gramatical de esa función misteriosa. Ocultan información crítica: ¿Quién procesó los datos? ¿Fue el usuario? ¿Fue el sistema?

Hoy vamos a arreglar este bug en tu escritura.

---

### 01:00 - EL COSTO COGNITIVO (O(1) vs O(N^2))

**[LOCUTOR]**:
En ingeniería, siempre buscamos la eficiencia.
Piensa en la **Voz Activa** como una operación de complejidad constante, O(1).
El cerebro recibe la información en orden directo: **Sujeto**... realiza **Acción**... sobre **Objeto**.
*"El servidor... lanza... una excepción"*.
Boom. Directo. Sin procesamiento extra.

*(Cambio de tono a uno más pesado)*

La **Voz Pasiva**, en cambio, es ineficiente. Es O(n al cuadrado).
*"Una excepción... es lanzada... por el servidor"*.
El cerebro tiene que esperar hasta el final de la frase para entender quién hizo qué, y luego reconstruir la escena mentalmente.

Al usar voz pasiva, estás gastando ciclos de CPU del cerebro de tu lector inútilmente. Y créeme, sus ciclos son limitados.

---

### 02:15 - ALGORITMO DE REFACTORIZACIÓN

**[LOCUTOR]**:
¿Cómo refactorizamos esto? No necesitas ser un lingüista, solo sigue este algoritmo de 3 pasos:

**Paso 1. Detectar.**
Busca el patrón "ser + un verbo en pasado". "Es hecho", "Fue enviado", "Será cancelado". Ese es tu `code smell`.

**Paso 2: Preguntar "¿Quién?".**
Si lees "El acceso fue denegado", pregúntate: ¿Quién lo denegó? ¿El guardia de seguridad? ¿El firewall? ¿La base de datos?
Digamos que fue el "Sistema de Auth".

**Paso 3: Reubicar.**
Toma a ese actor, el "Sistema de Auth", y ponlo al principio.
*"El Sistema de Auth denegó el acceso"*.

¡Listo! Pasaste de una oración ambigua y pasiva a una sentencia activa y poderosa.

---

### 03:30 - CIERRE Y LLAMADA A LA ACCIÓN

**[LOCUTOR]**:
Una advertencia final: No se trata de eliminar la voz pasiva al 100%. A veces, no sabemos quién es el actor, o no importa. Si dices "El servicio se cayó", no importa quién lo tiró, importa que está caído.

Pero en el 90% de tus documentos, especialmente en instrucciones y guías paso a paso, **sé activo**.

Tu tarea para esta lección es simple: Abre el último README que escribiste. Busca tres oraciones pasivas y refactorízalas. Tu "Yo del futuro" te lo agradecerá cuando tenga que leer eso a las 3 de la mañana durante un incidente.

Nos vemos en el siguiente tema.

*(Fade out)*
