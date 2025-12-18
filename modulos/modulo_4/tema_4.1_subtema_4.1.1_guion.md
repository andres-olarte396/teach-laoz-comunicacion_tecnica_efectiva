# GUIÓN: DESIGN DOCS Y RFCS

## FICHA TÉCNICA

- **Duración**: 4 minutos
- **Tono**: Estratégico, "Big Picture".

---

### 00:00 - EL COSTO DEL CAMBIO

**[LOCUTOR]**:
En ingeniería de software, hay una regla universal:
*"El costo de arreglar un error sube exponencialmente con el tiempo"*

Si te das cuenta de que tu base de datos no escala en el diseño, corregirlo te cuesta 1 hora de editar un documento. Costo: $50.
Si te das cuenta cuando ya escribiste el código, te cuesta 1 semana. Costo: $2,000.
Si te das cuenta en producción... bueno, prepara tu currículum.

---

### 01:00 - EL DOCUMENTO QUE VIAJA EN EL TIEMPO

**[LOCUTOR]**:
Un Design Doc (o RFC) es una máquina del tiempo.
Te permite simular el futuro.
Permite que tu equipo critique tu sistema *antes* de que exista.

No es burocracia. Es la herramienta de "Debugging Arquitectónico".
Si no puedes explicar tu solución en papel, no estás listo para escribirla en código.

---

### 02:00 - ESTRUCTURA: CONTEXTO, OPCIONES, DECISIÓN

**[LOCUTOR]**:
Un buen Design Doc tiene tres pilares:

1. **Contexto**: ¿Por qué estamos aquí? "El sistema actual es lento".
2. **Alternativas Consideradas (La parte más importante)**:
    Aquí es donde demuestras tu seniority.
    "Podríamos usar Postgres, pero no escala. Podríamos usar Mongo, pero perdemos transacciones. Elegimos DynamoDB porque..."
3. **Propuesta**: El plan de batalla.

Si te saltas la sección de Alternativas, no has diseñado. Solo has elegido lo primero que se te ocurrió.

---

### 03:00 - CIERRE

**[LOCUTOR]**:
Tu reto: La próxima vez que tengas una tarea grande (más de 3 días), no abras el IDE.
Abre un Google Doc.
Escribe 1 página.
Compártela con tu equipo y pide: *"Destruyan esta idea"*.
Te prometo que te ahorrarás semanas de dolor.

*(Fade out)*
