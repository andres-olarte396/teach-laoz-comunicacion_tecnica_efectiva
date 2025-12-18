# EVALUACIÓN: ADRs

## FICHA TÉCNICA

- **Tema**: 4.2.1 Architecture Decision Records
- **Nivel**: Avanzado

---

## CUESTIONARIO

### Pregunta 1

¿Cuál es la diferencia principal entre un **Design Doc** y un **ADR**?
a) El Design Doc es para propuestas futuras (mutables); el ADR es un registro histórico de una decisión tomada (inmutable).
b) Los ADRs son solo para bases de datos.
c) El Design Doc se escribe en Word y el ADR en Excel.

### Pregunta 2

Según el formato de **Michael Nygard**, ¿cuáles son las secciones obligatorias de un ADR?
a) Introducción, Nudo y Desenlace.
b) Contexto, Decisión y Consecuencias.
c) Presupuesto, Plazos y Responsables.

### Pregunta 3

Si una decisión arquitectónica cambia (ej. decidimos dejar de usar Redis y volver a Memcached), ¿qué haces con el ADR original de Redis?
a) Lo borras del repositorio para no confundir.
b) Lo editas y cambias el texto.
c) Creas un nuevo ADR que "Depreca" (Supersedes) al anterior, manteniendo el historial intacto.

### Pregunta 4

¿Qué debe incluirse en la sección de **Consecuencias**?
a) Solo los beneficios.
b) Solo los riesgos.
c) Tanto los beneficios (Pros) como los riesgos/costos (Cons) aceptados.

### Pregunta 5

¿Dónde deben vivir los archivos ADR?
a) En una carpeta compartida de Google Drive.
b) En el mismo repositorio que el código (ej. `/doc/adr`), bajo control de versiones.
c) En la wiki de la empresa (Confluence/Notion) solamente.

---

## SOLUCIONARIO

1. **a)**. El ADR congela el "por qué" en el tiempo.
2. **b)**. Es el estándar de industria para ligereza y claridad.
3. **c)**. La historia no se borra; se evoluciona.
4. **c)**. Toda decisión técnica tiene Trade-offs.
5. **b)**. "Docs as Code": la documentación debe viajar con el software.
