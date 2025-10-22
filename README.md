# 🧠 Neurociencias Computacionales

Este repositorio contiene una serie de **laboratorios prácticos** orientados al modelamiento computacional de neuronas, desde ecuaciones diferenciales simples hasta modelos biofísicos más detallados como Hodgkin-Huxley.
Cada laboratorio cuenta con sus scripts, notebooks y resultados gráficos correspondientes.

---

## 📚 Contenido

| Laboratorio | Tema Principal | Descripción breve |
|--------------|----------------|-------------------|
| [**Lab 1**](./Lab1 - Método de Heun Euler para solucionar EC Diferenciales) | Método de Heun-Euler | Simulación del potencial de membrana mediante integración numérica simple. |
| [**Lab 2**](./Lab2 - Modelo Hodgkin-Huxley) | Modelo de Hodgkin-Huxley (HH) | Modelo biofísico completo con canales de sodio y potasio. |
| [**Lab 3**](./Lab3 - Curva F-I con HH) | Curvas F–I del modelo HH | Relación entre la corriente inyectada y la frecuencia de disparo. |
| [**Lab 4**](./Lab4 - Reducción de dimensionalidad (Campos vectoriales)) | Reducción de dimensionalidad — FitzHugh–Nagumo | Simplificación del modelo HH, análisis de nulclinas y plano de fase. |
| [**Lab 5**](./Lab5 - Modelo LIF) | Modelo LIF (Leaky Integrate-and-Fire) | Modelo neuronal simplificado basado en umbral y reinicio. |

---

## 🧩 Resumen de los Laboratorios

---

### 🔹 **Lab 1 — Método de Heun–Euler**

**Objetivo:**
Aplicar los métodos numéricos de Euler y Heun para resolver ecuaciones diferenciales no lineales que describen el comportamiento dinámico de una neurona.

**Ecuaciones:**

\[
\frac{dV}{dt} = V - V^3 - w + I
\]

\[
\frac{dw}{dt} = \frac{V + a - b\,w}{\tau}
\]

**Enlace:** [Ir a Lab1](./Lab1 - Método de Heun Euler para solucionar EC Diferenciales)

---

### 🔹 **Lab 2 — Modelo de Hodgkin–Huxley**

**Objetivo:**
Simular el modelo de Hodgkin-Huxley, que describe la generación y propagación del potencial de acción a partir de canales iónicos dependientes de voltaje.

**Ecuaciones principales:**

\[
C_m \frac{dV}{dt} = I - g_{Na} m^3 h (V - E_{Na}) - g_K n^4 (V - E_K) - g_L (V - E_L)
\]

\[
\frac{dn}{dt} = \alpha_n(V)(1-n) - \beta_n(V)n
\]

\[
\frac{dm}{dt} = \alpha_m(V)(1-m) - \beta_m(V)m
\]

\[
\frac{dh}{dt} = \alpha_h(V)(1-h) - \beta_h(V)h
\]

**Enlace:** [Ir a Lab2](./Lab2 - Modelo Hodgkin-Huxley)

---

### 🔹 **Lab 3 — Curvas F–I (Frecuencia–Corriente)**

**Objetivo:**
Analizar la relación entre la **corriente inyectada (I)** y la **frecuencia de disparo (F)** en el modelo de Hodgkin–Huxley, generando la curva F–I.

**Concepto:**

\[
F = f(I) \quad \text{donde } F = \frac{\text{Número de spikes}}{\text{Duración del pulso}}
\]

**Enlace:** [Ir a Lab3](./Lab3 - Curva F-I con HH)

---

### 🔹 **Lab 4 — FitzHugh–Nagumo (Reducción de dimensionalidad)**

**Objetivo:**
Estudiar una versión reducida del modelo de Hodgkin–Huxley, más fácil de analizar en el plano de fase.
Incluye nulclinas, puntos de equilibrio y simulación de trayectorias.

**Ecuaciones:**

\[
\frac{dV}{dt} = V - \frac{V^3}{3} - w + I_{ext}(t)
\]

\[
\frac{dw}{dt} = \frac{V + a - b\,w}{\tau}
\]

**Análisis incluidos:**

- Nulclinas: \(\frac{dV}{dt} = 0\), \(\frac{dw}{dt} = 0\)
- Puntos de equilibrio
- Plano de fase

**Enlace:** [Ir a Lab4](./Lab4 - Reducción de dimensionalidad (Campos vectoriales))

---

### 🔹 **Lab 5 — Modelo LIF (Leaky Integrate-and-Fire)**

**Objetivo:**
Implementar y analizar un modelo simplificado de neurona tipo "Integrate-and-Fire", donde la dinámica de la membrana es lineal y el disparo ocurre al alcanzar un umbral.

**Ecuación básica:**

\[
\tau_m \frac{dV}{dt} = -(V - V_{rest}) + R_m I(t)
\]

**Condición de disparo:**
\[
\text{si } V \geq V_{th} \Rightarrow V \leftarrow V_{reset}
\]

**Enlace:** [Ir a Lab5](./Lab5 - Modelo LIF)

---

## 👨‍🔬 Autor

**Juan Carlos Trejos Iglesias**
Proyecto de Modelos Neuronales — Neurociencias Computacionales
Universidad / Grupo de Investigación (si aplica)

---

📂 *Cada carpeta contiene su propio README con explicaciones, código y resultados gráficos.*
