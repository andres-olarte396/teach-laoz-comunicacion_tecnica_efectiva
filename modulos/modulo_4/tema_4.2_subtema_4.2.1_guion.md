# GUIÓN: ADRs (ARCHITECTURE DECISION RECORDS)

## FICHA TÉCNICA

- **Duración**: 3.5 minutos
- **Tono**: Narrativo, Histórico.

---

### 00:00 - LA ARQUEOLOGÍA DEL CÓDIGO

**[LOCUTOR]**:
Llegas a un proyecto nuevo. Abres el código.
Ves que usan una base de datos GraphDB para guardar... lista de compras.
Te preguntas: *"¿En qué estaban pensando?"*
Miras el `git blame`. El autor se fue hace 2 años.
Nadie sabe por qué.
Borrón y cuenta nueva. Reescribes todo en SQL.

Seis meses después, el sistema colapsa por las mismas razones que hicieron que el equipo original eligiera GraphDB.

---

### 01:00 - LA AMNESIA INSTITUCIONAL

**[LOCUTOR]**:
Esto se llama Amnesia Institucional.
Los equipos de software olvidan por qué tomaron sus decisiones.
Y el código solo te dice *qué* hace, no *por qué* lo hace.

La solución no es tener "mejor memoria". Es tener una bitácora.
Un Architecture Decision Record (ADR) es esa bitácora.

---

### 02:00 - EL FORMATO DE MICHAEL NYGARD

**[LOCUTOR]**:
Un ADR no es una tesis doctoral. Es una nota rápida.
Sigue el formato de Michael Nygard:

1. **Contexto**: "Teníamos un problema de latencia".
2. **Decisión**: "Usaremos cache en Redis".
3. **Consecuencias**: "Es rápido, pero si Redis cae, perdemos datos".

Lo más importante son las consecuencias negativas.
Si un documento solo habla maravillas de una tecnología, es marketing, no arquitectura.

---

### 03:00 - TU TAREA

**[LOCUTOR]**:
No intentes documentar el pasado hoy. Es imposible.
Empieza hoy.
La próxima vez que tú o tu equipo digan: *"Vamos a usar la librería X en lugar de Y"*, detente.
Crea un archivo markdown.
`001-usar-libreria-x.md`.
Escribe por qué.
Tu "yo del futuro" te lo agradecerá cuando todo falle en 6 meses.

*(Fade out)*
