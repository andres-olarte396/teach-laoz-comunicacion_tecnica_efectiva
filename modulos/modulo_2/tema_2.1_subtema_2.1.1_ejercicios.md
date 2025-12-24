# BANCO DE EJERCICIOS: MÓDULO 2 - COMENTARIOS Y DOCSTRINGS

## METADATA

- **Módulo**: Documentación en el Código
- **Objetivos evaluados**:
  1. Identificar comentarios redundantes (Anti-patrón).
  2. Refactorizar código para eliminar necesidad de comentarios.
  3. Escribir Docstrings estructurados que aporten valor.
- **Tiempo total estimado**: 20 minutos
- **Nivel**: Básico

---

## EJERCICIO 1. Matando el Ruido

### ENUNCIADO

Clasifica los siguientes comentarios como **✅ ÚTIL** o **❌ RUIDO**.

1. `i += 1  // Incrementa el contador`
2. `// TODO: Refactorizar a O(n) antes del lanzamiento`
3. `// Esta función obtiene usuarios` (sobre funcion `get_users()`)
4. `// Workaround para bug en Safari < 14 (Ticket #99)`
5. `return x * 0.16 // Calcula IVA`

### SOLUCIÓN

1. **❌ RUIDO**. El código ya dice que incrementa.
2. **✅ ÚTIL**. Deuda técnica explícita.
3. **❌ RUIDO**. El nombre de la función ya lo dice.
4. **✅ ÚTIL**. Contexto crítico externo (Why).
5. **❌ RUIDO**. Mejor renombrar variable: `return subtotal * TAX_RATE`.

---

## EJERCICIO 2: Refactorización (Code > Comments)

### ENUNCIADO

Elimina los comentarios del siguiente código renombrando variables y funciones para que sea auto-explicativo.

**Código Original:**

```python
# Comprueba si el usuario puede entrar
# a es la edad, s es el estado (1 activo, 0 inactivo)
def check(a, s):
    # Si es mayor de 18 y está activo
    if a >= 18 and s == 1:
        return True
    return False
```

### SOLUCIÓN MODELO

```python
def is_user_eligible_for_entry(age, status):
    is_adult = age >= 18
    is_active = status == 1
    
    return is_adult and is_active
```

*(Nota: Cero comentarios necesarios. El código se lee como inglés).*

---

## EJERCICIO 3: El Docstring Perfecto

### ENUNCIADO

Escribe un Docstring para esta función usando el formato `Args` y `Returns`. Inventa los detalles lógicos.

```python
def calculate_insurance_premium(age, risk_factor):
    ...
```

### SOLUCIÓN MODELO

```python
def calculate_insurance_premium(age: int, risk_factor: float) -> float:
    """
    Calcula la prima mensual del seguro basada en perfil de riesgo.

    La fórmula penaliza exponencialmente el factor de riesgo para
    desincentivar perfiles altos (Política de Negocio 2024).

    Args:
        age: Edad del asegurado (debe ser 18-99).
        risk_factor: Índice de 0.0 a 1.0. 
                     Valores > 0.8 rechazan la póliza automáticamente.

    Returns:
        Monto mensual en USD. Retorna 0 si es rechazado.
    """
```

---

## AUTOEVALUACIÓN

- [ ] ¿He borrado comentarios obvios hoy?
- [ ] ¿Mis variables explican el "qué" para que mis comentarios solo expliquen el "por qué"?
