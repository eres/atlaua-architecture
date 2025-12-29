# Atlaua v0.1 – Panel de Prioridad de Fugas

Atlaua es un prototipo de panel de inteligencia para ayudar a los municipios a **priorizar fugas de agua** en su red de tuberías, combinando la probabilidad de fuga con el volumen de agua perdida.

## Qué hace este MVP

- Carga datos de tuberías desde un archivo CSV.
- Usa un modelo de machine learning (Random Forest) para estimar la **probabilidad de fuga grave** (`prob_fuga_grave`).
- Calcula la **pérdida mensual estimada** por tubería (`loss_m3_mes`).
- Genera una **puntuación de criticidad** (`puntuacion_critica = probabilidad × pérdida`).
- Clasifica cada tubería en un **nivel crítico**: 🔴 Alta, 🟠 Media, 🟡 Baja.
- Permite asignar y editar el **estado operativo**:
  - 🚨 Prioritaria
  - ⏳ Pendiente
  - 📆 Programable
  - 🛠️ Reparada
- Muestra:
  - Resumen operativo del municipio.
  - Lista filtrada por probabilidad de fuga.
  - Top 5 tuberías más críticas.
  - **Plan de inspección sugerido** según capacidad diaria.
  - Resumen por zona.
  - **Mapa interactivo** de tuberías (con lat/lon).

## Alcance del proyecto (para desarrollo asistido)

Atlaua es un **prototipo funcional orientado a la toma de decisiones municipales**, no un sistema productivo final.

Principios de esta versión:
- El foco principal es **UX operativa y priorización territorial**, no la optimización del modelo de ML.
- El código prioriza **claridad, trazabilidad y criterio humano** sobre performance o abstracción.
- Las decisiones finales siempre pertenecen al **supervisor municipal** (el sistema propone, no decide).
- No incluye persistencia en base de datos, multiusuario ni control de acceso.
- Los cambios deben preservar el **flujo de decisión** y la legibilidad del panel.

## Cómo ejecutar

```bash
cd atlaua_dev
source env/bin/activate   # activar entorno virtual
streamlit run app/atlaua_dashboard.py```
# Atlaua — Plataforma de Decisión Territorial Hídrica (v0.5.x)

Atlaua es una **plataforma de apoyo a la decisión** para municipios, diseñada para ayudar a **supervisores operativos** a priorizar acciones sobre fugas de agua en redes de distribución **a nivel territorial**, no solo a nivel de activos individuales.

Atlaua **no automatiza decisiones**: estructura información compleja para que un humano decida mejor, más rápido y con mayor justificación.

---

## 🎯 Propósito del sistema

El problema central que Atlaua aborda es:

> “Veo muchas fugas y eventos en el mapa, pero no tengo claridad territorial para decidir por dónde empezar esta semana o este mes.”

Atlaua transforma datos dispersos (tuberías, pérdidas, probabilidades, zonas) en **criterios claros de prioridad operativa**, entendibles y defendibles dentro de un contexto municipal.

---

## 🧠 Principios fundacionales

Esta versión del sistema se rige por los siguientes principios:

- **El sistema propone, el supervisor decide.**
- La prioridad es **territorial y operativa**, no puramente algorítmica.
- La UX privilegia **claridad, trazabilidad y criterio humano** sobre sofisticación técnica.
- El mapa informa, pero **no decide por sí solo**.
- Toda interacción debe respetar el flujo:
  
  **Objeto → Control (toggle/filtro) → Feedback visible**

---

## ⚙️ Qué hace el sistema actualmente (v0.5.x)

Atlaua:

- Ingiere datos de tuberías (mock o CSV).
- Estima para cada tubería:
  - **Probabilidad de fuga grave** (`prob_fuga_grave`) mediante un modelo ML (Random Forest).
  - **Pérdida mensual estimada** (`loss_m3_mes`).
- Calcula una **puntuación de criticidad**:
  
  ```
  puntuacion_critica = probabilidad × pérdida
  ```
- Clasifica activos en niveles críticos: 🔴 Alta, 🟠 Media, 🟡 Baja.
- Agrega la información **por zona**, generando:
  - Indicadores territoriales comparables.
  - Rankings claros por prioridad.
- Permite al supervisor:
  - Definir **zonas foco**.
  - Filtrar y explorar activos dentro de una zona.
  - Cambiar el **estado operativo** de tuberías:
    - 🚨 Prioritaria
    - ⏳ Pendiente
    - 📆 Programable
    - 🛠️ Reparada
- Presenta:
  - Resumen operativo municipal.
  - Ranking territorial por zona.
  - Plan de inspección sugerido según capacidad.
  - Mapa interactivo como apoyo visual (no decisional).

---

## 🧩 Qué NO es Atlaua (por diseño)

Esta versión **deliberadamente no incluye**:

- Automatización de decisiones finales.
- Optimización avanzada del modelo de ML.
- Persistencia en base de datos.
- Multiusuario o control de acceso.
- Workflows administrativos complejos.

Estas exclusiones son decisiones conscientes para **proteger la claridad operativa** del sistema.

---

## 📐 Alcance del prototipo

Atlaua es un **prototipo funcional orientado a toma de decisiones reales**, no un producto productivo final.

El código prioriza:
- Legibilidad
- Razonamiento explícito
- Facilidad de auditoría
- Evolución progresiva por versiones (v0.5.x → v0.6)

---

## ▶️ Cómo ejecutar el prototipo

```bash
cd atlaua_dev
source env/bin/activate
streamlit run app/atlaua_dashboard.py
```

---

## 🗺️ Nota para colaboradores y agentes de IA

Al trabajar sobre este proyecto (humano o IA):

- No introducir features que rompan el flujo de decisión.
- No convertir el sistema en “caja negra”.
- Toda mejora debe poder explicarse en lenguaje operativo municipal.
- Si una mejora no ayuda a decidir **qué hacer primero**, probablemente no pertenece aquí.