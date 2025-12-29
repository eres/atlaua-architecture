# Atlaua — Changelog de Decisiones (v0.5.x)

Este documento registra **cambios significativos de producto, UX y lógica de decisión** en Atlaua.

No es un log técnico ni una lista de commits. Es un **registro de decisiones conscientes**, pensado para:

* Mantener continuidad conceptual.
* Permitir auditoría (humana y de IA).
* Entender *por qué* el sistema evolucionó como lo hizo.

---

## v0.5.3 — Claridad territorial y control cognitivo

**Estado:** Estable

### 🎯 Problema que se abordó

El sistema mostraba información correcta, pero:

* El supervisor podía perder claridad sobre **qué estaba activo** y **por qué**.
* Algunos controles aparecían *antes* del contexto que modificaban, rompiendo el flujo natural de decisión.

### ✅ Decisiones clave

* Se formaliza la regla **Objeto → Control → Feedback** como principio de UX.
* Los toggles que afectan el mapa se colocan **debajo del mapa**, no arriba.
* El módulo **“Zonas foco activas”** se asocia visual y espacialmente al toggle que lo activa.
* Se descarta el micro‑zoom automático al activar toggles por introducir ruido perceptual.

### 🧠 Impacto cognitivo

* El usuario ve primero el estado base.
* Decide intervenir con intención.
* Recibe feedback inmediato y explícito.

El sistema se vuelve **más predecible y menos ansioso**.

---

## v0.5.2 — Exploración de interacción (iteración descartada)

**Estado:** Experimental (no persistió)

### 🎯 Qué se intentó

* Introducir micro‑zooms automáticos al activar:

  * Zonas foco
  * Tuberías

### ❌ Resultado

* La animación se sentía arbitraria.
* Rompía la sensación de control del usuario.
* Introducía movimiento sin mejorar la decisión.

### 📌 Decisión

* Se descarta completamente esta línea.
* Se refuerza la idea de que **el sistema no debe sorprender**, sino acompañar.

---

## v0.5.1 — Indicadores territoriales por zona

**Estado:** Cerrado

### 🎯 Problema original

> “Veo muchas fugas en el mapa, pero no tengo claridad territorial para decidir por dónde empezar.”

### ✅ Solución implementada

* Consolidación de métricas **por zona**.
* Ranking explícito de zonas según criticidad agregada.
* Orden controlable y entendible.
* Métricas alineadas con lógica operativa municipal.

### 🧠 Cambio estructural

* El mapa deja de ser el eje decisional.
* La prioridad se establece **antes** de explorar visualmente.

Esta versión establece la **base conceptual** del sistema actual.

---

## 📌 Nota de gobierno del sistema

Cada nueva versión debe:

* Referenciar explícitamente este changelog.
* Justificar desviaciones de reglas existentes.
* Registrar aprendizajes, incluso si una idea se descarta.

Última actualización: v0.5.3
