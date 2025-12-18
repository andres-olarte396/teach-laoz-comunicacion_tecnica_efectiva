# GUIÓN: POSTMORTEMS BLAMELESS

## FICHA TÉCNICA

- **Duración**: 4 minutos
- **Tono**: Serio, Reflexivo, "Safety Engineering".

---

### 00:00 - LA BÚSQUEDA DEL CULPABLE

**[LOCUTOR]**:
Lunes, 9 de la mañana. El sitio se cae.
El CEO entra gritando: *"¿Quién fue?"*
Alguien señala a Juan, el junior que hizo el deploy.
Juan es despedido.
El CEO se siente mejor. "Problema resuelto".

**[LOCUTOR]**:
Falso. El problema no está resuelto.
Simplemente has eliminado a la única persona que sabía *exactamente* qué salió mal.
Y has enseñado al resto del equipo a esconder sus errores para sobrevivir.

---

### 01:30 - INGENIERÍA DE SEGURIDAD

**[LOCUTOR]**:
Imagina la aviación.
Cuando un avión se estrella, no dicen: *"El piloto era tonto"*.
Preguntan: *"¿Por qué el altímetro era confuso?"*, *"¿Por qué el sistema permitió bajar el tren de aterrizaje a esa velocidad?"*.

Eso es un **Postmortem Blameless**.
Asumimos que la gente es inteligente y quiere hacer un buen trabajo.
Si fallaron, es porque el sistema, herramientas o procesos les fallaron.

---

### 02:45 - LOS 5 PORQUÉS

**[LOCUTOR]**:
Para llegar a la verdad, usa los 5 Porqués.
- Se cayó la base de datos. ¿Por qué?
- Porque se llenó el disco. ¿Por qué?
- Porque los logs no rotaron. ¿Por qué?
- Porque la configuración por defecto de Linux no lo hace. ¿Por qué?
- **Porque no tenemos un script de inicialización de servidores estandarizado.**

¡Bingo!
La solución no es "Juan, borra logs".
La solución es "Automatizar la configuración del servidor".

### 03:45 - CIERRE

**[LOCUTOR]**:
La próxima vez que algo se rompa, prohíbe los nombres propios en el reporte.
No escribas "Juan rompió la base".
Escribe "Una consulta mal formada causó un bloqueo".
Cambia la cultura del miedo por la cultura del aprendizaje.

*(Fade out)*
