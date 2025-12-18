# EVALUACIÓN: AUTENTICACIÓN Y ERRORES

## FICHA TÉCNICA

- **Tema**: 3.1.2 Protocolo HTTP y Errores
- **Nivel**: Intermedio

---

## CUESTIONARIO

### Pregunta 1

¿Qué significa un código de estado de la familia **4xx**?
a) El servidor falló internamente.
b) La petición del cliente tiene un error (Client Error).
c) La petición fue procesada exitosamente.

### Pregunta 2: Escenario

Un usuario intenta acceder a `/admin/panel` pero no tiene privilegios de administrador. Está logueado correctamente. ¿Qué código debes devolver?
a) 401 Unauthorized.
b) 403 Forbidden.
c) 404 Not Found (para ocultarlo).

### Pregunta 3: Anti-patrón

¿Por qué es malo devolver `200 OK` con un cuerpo JSON `{ "error": "failed" }`?
a) Porque consume más ancho de banda.
b) Porque las herramientas de monitoreo creerán que el sistema está saludable cuando no lo está.
c) No es malo, es una práctica común en GraphQL.

### Pregunta 4

Según el estándar RFC 7807 (Problem Details), ¿qué campos debería tener un error JSON?
a) Solo un string con el mensaje.
b) `type`, `title`, `status`, `detail`, `instance`.
c) El stack trace completo del servidor.

### Pregunta 5

¿Cuál es la forma estándar de enviar un token JWT en una petición HTTP?
a) En la URL: `?token=...`
b) En una cookie no segura.
c) En el Header: `Authorization: Bearer <token>`

---

## SOLUCIONARIO

1. **b)**. Indica que el cliente debe corregir algo antes de reintentar.
2. **b)**. 401 es "¿Quién eres?"; 403 es "Sé quién eres, pero no puedes pasar".
3. **b)**. Rompe la semántica del protocolo HTTP y dificulta la observabilidad.
4. **b)**. Provee una estructura estándar para que las máquinas entiendan el error.
5. **c)**. Es el estándar de industria para autenticación stateless.
