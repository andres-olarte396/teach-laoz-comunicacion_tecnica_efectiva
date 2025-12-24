# LECCIÓN 0.1. PRECONCEPTOS FUNDAMENTALES DE LA COMUNICACIÓN TÉCNICA

## ¡Hola Futuro Technical Writer! 👋

Soy **GemPreConceptos**, tu profesor de nivelación. Antes de sumergirnos en la redacción de RFCs complejos o ADKs, necesitamos calibrar nuestra brújula. He analizado el plan curricular y detectado 3 pilares invisibles que sostienen todo el curso. Si estos cimientos fallan, el edificio se cae.

Aquí tienes los conceptos "Boleto de Entrada" para este viaje:

---

### 1. DOCS AS CODE (Documentación como Código)

#### 📝 Definición

Es la filosofía de tratar la documentación con el mismo rigor y herramientas que el código fuente.

#### 💡 ¿Por qué es fundamental?

Imagina que construyes una casa (tu software) pero los planos (la documentación) están dibujados en servilletas dispersas (Word, Wikis desactualizadas, emails). Si cambias una pared, nadie actualiza la servilleta.
**Docs as Code** significa guardar los planos en la misma caja fuerte que los ladrillos (Git), revisarlos con inspectores (Code Review) y publicarlos automáticamente cuando la casa se termina (CI/CD).

#### ⭐ Importancia: 10/10

Sin esto, la documentación siempre estará desincronizada de la realidad.

---

### 2. DEUDA TÉCNICA DOCUMENTAL

#### 📝 Definición

El costo implícito de no documentar una decisión o cambio en el momento en que ocurre.

#### 💡 ¿Por qué es fundamental?

Es como lavar los platos. Si lavas tu plato (documentas tu cambio) justo después de comer, toma 30 segundos. Si esperas al final del mes (el lanzamiento), tienes una montaña de platos sucios con comida pegada. El esfuerzo para "ponerse al día" es exponencialmente mayor y mucho más doloroso.

#### ⭐ Importancia: 9/10

Entender este costo te motivará a escribir *mientras* programas, no después.

---

### 3. VOZ ACTIVA vs. VOZ PASIVA

#### 📝 Definición

- **Voz Activa**: El sujeto realiza la acción. ("El sistema valida los datos").
- **Voz Pasiva**: La acción es recibida por el sujeto. ("Los datos son validados por el sistema").

#### 💡 ¿Por qué es fundamental?

En código, buscamos la ruta más corta de A a B. En escritura técnica, la **Voz Activa** es esa ruta directa ($O(1)$). La Voz Pasiva es un algoritmo ineficiente ($O(n^2)$) que obliga al cerebro del lector a procesar quién hizo qué.
- *Malo*: "El error debe ser corregido por el usuario." (¿Quién manda? ¿Qué pasa?)
- *Bueno*: "Corrija el error." (Instrucción clara, sujeto implícito "usted").

#### ⭐ Importancia: 8/10

Es la herramienta #1 para la claridad.

---

### 🛠️ TU PRIMERA MISIÓN (CHECKLIST DE NIVELACIÓN)

Antes de pasar al Módulo 1, asegúrate de:

1. [ ] Saber qué es **Markdown** (si no, busca un tutorial de 5 min).
2. [ ] Tener un editor de texto (VS Code recomendado).
3. [ ] Entender que escribir es una iteración, igual que programar (Draft -> Review -> Refactor -> Deploy).

¡Estás listo para dejar de ser solo un "coder" y convertirte en un **Ingeniero Comunicador**! 🚀
