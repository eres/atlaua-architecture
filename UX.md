

# Atlaua — Reglas de UX y Decisiones de Diseño (v0.5.x)

Este documento captura **reglas explícitas de UX**, criterios de interacción y decisiones de diseño que gobiernan Atlaua.
No es un manual visual ni un checklist de componentes: es un **registro de decisiones cognitivas** que protegen el modelo mental del usuario.

Su función es:
- Mantener coherencia a lo largo de versiones.
- Evitar regresiones conceptuales.
- Permitir que colaboradores humanos y agentes de IA entiendan *por qué* el sistema es como es.

---

## 🧠 Usuario primario (modelo mental)

**Rol:** Supervisor municipal de agua  
**Contexto:**
- Opera bajo presión.
- Tiene responsabilidad territorial, no técnica.
- Debe justificar decisiones ante superiores y equipos.
- Prefiere claridad y criterio defendible sobre precisión matemática extrema.

**Implicación UX clave:**  
Atlaua debe **reducir carga cognitiva**, no aumentarla con opciones o visualizaciones innecesarias.

---

## 🧩 Regla fundamental de interacción

### Regla 001 — Flujo Objeto → Control → Feedback

> Todo control que altere un elemento debe colocarse **después del elemento afectado** y producir feedback inmediato y visible.

**Orden correcto:**
1. El usuario observa el estado base del objeto.
2. Decide si necesita intervenir.
3. Activa un control.
4. Ve el resultado sin ambigüedad.

**Ejemplo aplicado:**
- Objeto: Mapa territorial
- Control: Toggle “Enfocar zonas foco”
- Feedback: Módulo “Zonas foco activas” + cambio visual en mapa

**Aprendizaje (v0.5.3):**  
Colocar el toggle *antes* del mapa generaba confusión y rompía el flujo natural de decisión.

---

## 🎚️ Regla sobre toggles

### Regla 002 — Los toggles no anticipan, reaccionan

Los toggles:
- **No introducen contexto nuevo**
- **No explican**
- **No narran**

Su única función es **modificar un estado ya visible**.

**Consecuencia:**
- No deben ir en headers globales si afectan contenido local.
- Deben estar cerca del objeto que alteran.
- Deben ir acompañados de feedback inmediato o un estado visible.

**Excepción:**
- Toggles de *modo* (ej. “Editar”, “Simulación”) pueden ir en capas superiores.

---

## 🗺️ Regla sobre el mapa

### Regla 003 — El mapa informa, no decide

El mapa en Atlaua:
- Es contextual
- Es exploratorio
- Es confirmatorio

Nunca es:
- La fuente primaria de decisión
- El primer elemento que impone prioridad

**Implicación de diseño:**
- Rankings y métricas preceden al mapa.
- El mapa valida decisiones ya pensadas, no las genera.

---

## 📊 Regla sobre métricas

### Regla 004 — Métricas defendibles > métricas sofisticadas

Las métricas deben:
- Poder explicarse en lenguaje municipal.
- Ser comparables territorialmente.
- Apoyar decisiones prácticas.

**Ejemplo:**
La métrica  
`criticidad = probabilidad × pérdida`  
es preferible a un score complejo si:
- Se entiende.
- Se puede justificar.
- Conduce a acción.

---

## 🚫 Regla sobre sobrecarga visual

### Regla 005 — Menos opciones, más criterio

Agregar controles, filtros o visualizaciones solo es válido si:
- Cambian una decisión.
- Aclaran una prioridad.
- Reducen ambigüedad.

Si solo “se ven bien” o “podrían ser útiles”, no pertenecen al sistema.

---

## 🧭 Regla de evolución del sistema

### Regla 006 — Toda mejora debe responder a una pregunta operativa

Antes de introducir cualquier cambio, debe responderse:

> “¿Qué decisión concreta ayuda a tomar mejor o más rápido?”

Si no hay una respuesta clara, el cambio debe posponerse.

---

## 🤖 Nota para agentes de IA

Al proponer cambios en Atlaua:

- No optimizar por estética.
- No introducir automatización de decisiones finales.
- No agregar complejidad sin impacto operativo claro.
- Priorizar siempre claridad territorial y criterio humano.

Si una propuesta no puede explicarse a un supervisor municipal en 30 segundos, probablemente no pertenece al sistema.

---

## 📌 Estado del documento

Este documento es **vivo**.
Cada versión importante de Atlaua debe:
- Revisar estas reglas.
- Confirmar si siguen vigentes.
- Registrar nuevas decisiones explícitas si aparecen.

Última revisión: v0.5.3