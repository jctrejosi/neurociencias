# 🧠 Neurociencias Computacionales

Repositorio de **laboratorios prácticos** enfocados en el **modelamiento computacional de neuronas**, desde ecuaciones diferenciales básicas hasta modelos biofísicos complejos como **Hodgkin–Huxley**.
Cada laboratorio incluye sus *scripts*, *notebooks* (`.ipynb`) y resultados gráficos.

---

## 📘 Contenido General

| Laboratorio | Tema Principal | Descripción breve |
|--------------|----------------|-------------------|
| [**Lab 1 — Método de Heun–Euler para ecuaciones diferenciales**](./Lab1%20-%20Método%20de%20Heun%20Euler%20para%20solucionar%20EC%20Diferenciales) | Integración numérica | Solución de EDOs neuronales con los métodos de Euler y Heun. |
| [**Lab 2 — Modelo Hodgkin–Huxley**](./Lab2%20-%20Modelo%20Hodgkin-Huxley) | Modelo biofísico | Simulación del potencial de acción con canales de Na⁺ y K⁺. |
| [**Lab 3 — Curva F–I con Hodgkin–Huxley**](./Lab3%20-%20Curva%20F-I%20con%20HH) | Frecuencia–corriente | Relación entre corriente inyectada y frecuencia de disparo. |
| [**Lab 4 — FitzHugh–Nagumo (Reducción de dimensionalidad)**](./Lab4%20-%20Reducción%20de%20dimensionalidad%20(Campos%20vectoriales)) | Dinámica reducida | Análisis de nulclinas, equilibrio y plano de fase. |
| [**Lab 5 — Modelo LIF (Leaky Integrate-and-Fire)**](./Lab5%20-%20Modelo%20LIF) | Modelo simplificado | Implementación del modelo Integrate-and-Fire con umbral y reinicio. |

---

## 🔬 Descripción de los Laboratorios

### [**Lab 1 — Método de Heun–Euler**](./Lab1%20-%20Método%20de%20Heun%20Euler%20para%20solucionar%20EC%20Diferenciales)

Implementa los métodos de **Euler explícito** y **Heun** para resolver EDOs del tipo:

\[
\frac{dV}{dt} = V - V^3 - w + I, \qquad
\frac{dw}{dt} = \frac{V + a - b\,w}{\tau}
\]

---

### [**Lab 2 — Modelo de Hodgkin–Huxley**](./Lab2%20-%20Modelo%20Hodgkin-Huxley)

Simulación completa del modelo **Hodgkin–Huxley (HH)** con canales dependientes de voltaje:

\[
C_m \frac{dV}{dt} = I - g_{Na} m^3 h (V - E_{Na}) - g_K n^4 (V - E_K) - g_L (V - E_L)
\]

Incluye la evolución de las compuertas \( m, n, h \) y el análisis del potencial de acción.

---

### [**Lab 3 — Curvas F–I (Frecuencia–Corriente)**](./Lab3%20-%20Curva%20F-I%20con%20HH)

Analiza la relación **F–I** del modelo HH:

\[
F = f(I) = \frac{\text{número de spikes}}{\text{duración del pulso}}
\]

Permite caracterizar la respuesta neuronal frente a estímulos de distinta intensidad.

---

### [**Lab 4 — FitzHugh–Nagumo**](./Lab4%20-%20Reducción%20de%20dimensionalidad%20(Campos%20vectoriales))

Versión reducida del modelo HH que conserva su dinámica esencial:

\[
\frac{dV}{dt} = V - \frac{V^3}{3} - w + I_{ext}, \qquad
\frac{dw}{dt} = \frac{V + a - b\,w}{\tau}
\]

Incluye análisis de nulclinas, estabilidad y trayectorias en el plano de fase.

---

### [**Lab 5 — Modelo LIF (Leaky Integrate-and-Fire)**](./Lab5%20-%20Modelo%20LIF)

Modelo neuronal lineal basado en filtrado RC y umbral de disparo:

\[
\tau_m \frac{dV}{dt} = -(V - V_{rest}) + R_m I(t)
\]

El disparo ocurre cuando \(V \geq V_{th}\), reiniciándose en \(V_{reset}\).
Ideal para simulaciones rápidas de redes neuronales.

---

## 👨‍🔬 Autor

**Juan Carlos Trejos Iglesias**
Proyecto de Modelos Neuronales — *Neurociencias Computacionales*
Universidad / Grupo de Investigación *(si aplica)*

---

📂 Cada carpeta incluye su propio `README.md`, código fuente y resultados gráficos.
