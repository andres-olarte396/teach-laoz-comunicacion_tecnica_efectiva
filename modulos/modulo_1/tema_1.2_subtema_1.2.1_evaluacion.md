# EVALUACIÓN: MAPEO DE AUDIENCIA

## FICHA TÉCNICA

- **Tema**: 1.2.1 Usuario vs. Mantenedor
- **Nivel**: Intermedio

---

## CUESTIONARIO

### Pregunta 1

¿Cuál es la diferencia principal entre un documento para Usuario y uno para Mantenedor?
a) El de Usuario es más corto.
b) El de Usuario trata el sistema como Caja Negra; el de Mantenedor como Caja Blanca.
c) El de Mantenedor solo contiene código.

### Pregunta 2: Escenario

Estás escribiendo un `README.md` para una librería pública. ¿Qué información **NO** debería estar en la sección de "Inicio Rápido"?
a) Comandos de instalación (`npm install`).
b) Explicación de por qué elegiste el patrón Singleton para la conexión a DB.
c) Ejemplo de código "Hello World".

### Pregunta 3: Anti-patrones

¿Qué es "Leaking Internals" (Fuga de Internos)?
a) Cuando la memoria RAM se llena.
b) Cuando expones detalles de implementación irrelevantes en la documentación de usuario.
c) Cuando publicas contraseñas en GitHub.

### Pregunta 4

Si un lector pregunta "¿Cómo extiendo esta clase para añadir una funcionalidad?", ¿qué rol está asumiendo?
a) Usuario.
b) Mantenedor / Colaborador.
c) Project Manager.

---

## SOLUCIONARIO

1. **b)**. La perspectiva de abstracción es la clave.
2. **b)**. Las decisiones de arquitectura pertenecen a `CONTRIBUTING` o `docs/architecture`, no al Quickstart.
3. **b)**. Ejemplo: Explicar el algoritmo de hashing al usuario que solo quiere loguearse.
4. **b)**. Quiere modificar o extender el código, por lo tanto necesita visión de Caja Blanca.
