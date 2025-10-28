# Neurociencias Computacionales

Este repositorio recopila una serie de **laboratorios prácticos** sobre el modelamiento computacional de neuronas.
A través de distintos niveles de complejidad, se exploran modelos basados en **ecuaciones diferenciales ordinarias**,
simulaciones numéricas y análisis dinámicos que permiten comprender cómo las neuronas procesan señales eléctricas.

Desde los métodos numéricos básicos hasta los modelos biofísicos clásicos como **Hodgkin–Huxley** y sus reducciones,
cada laboratorio combina **teoría, simulación y visualización** para desarrollar una comprensión profunda
de los mecanismos que gobiernan la excitabilidad neuronal.

---

## Contenido

- [**Lab 1 — Introducción - Método de Heun–Euler**](./Lab1%20-%20Método%20de%20Heun%20Euler%20para%20solucionar%20EC%20Diferenciales)
  Simulación del potencial de membrana mediante integración numérica con los métodos de Euler y Heun.

- [**Lab 2 — Modelo de Hodgkin–Huxley (HH)**](./Lab2%20-%20Modelo%20Hodgkin-Huxley)
  Implementación del modelo biofísico de canales iónicos dependientes de voltaje.

- [**Lab 3 — Curvas F–I (Frecuencia–Corriente)**](./Lab3%20-%20Curva%20F-I%20con%20HH)
  Estudio de la relación entre corriente inyectada y frecuencia de disparo neuronal.

- [**Lab 4 — Reducción de Dimensionalidad - FitzHugh–Nagumo**](./Lab4%20-%20Reducción%20de%20dimensionalidad%20(Campos%20vectoriales))
  Análisis de nulclinas, puntos de equilibrio y plano de fase en una versión reducida del modelo HH.

- [**Lab 5 — Modelo LIF (Leaky Integrate-and-Fire)**](./Lab5%20-%20Modelo%20LIF)
  Modelo simplificado basado en umbral, reinicio y corriente de entrada.

- [**Lab 6 —  Análisis estadístico en trenes de spikes**](./Lab6%20-%20Modelo%20LIF)
  Conteo de skipes por intérvalos de tiempo, clasificación del comportamiento de la neurona.

---

## Resumen de los Laboratorios

---

### 🔹 **Lab 1 — Método de Heun–Euler**

**Objetivo:**
Aplicar los métodos numéricos de Euler y Heun para resolver ecuaciones diferenciales que modelan la dinámica neuronal.

**Ecuaciones:**

<span style="color:gray">$\frac{dV}{dt} = V - V^3 - w + I$</span>

<span style="color:gray">$\frac{dw}{dt} = \frac{V + a - bw}{\tau}$</span>

---

### 🔹 **Lab 2 — Modelo de Hodgkin–Huxley**

**Objetivo:**
Simular la generación y propagación del potencial de acción a partir de canales iónicos dependientes de voltaje.

**Ecuaciones principales:**

<span style="color:gray">$C_m \frac{dV}{dt} = I - g_{Na}m^3h(V - E_{Na}) - g_K n^4 (V - E_K) - g_L (V - E_L)$</span>

<span style="color:gray">$\frac{dn}{dt} = \alpha_n(V)(1-n) - \beta_n(V)n$</span>

<span style="color:gray">$\frac{dm}{dt} = \alpha_m(V)(1-m) - \beta_m(V)m$</span>

<span style="color:gray">$\frac{dh}{dt} = \alpha_h(V)(1-h) - \beta_h(V)h$</span>

---

### 🔹 **Lab 3 — Curvas F–I (Frecuencia–Corriente)**

**Objetivo:**
Analizar la relación entre la **corriente inyectada (I)** y la **frecuencia de disparo (F)** en el modelo HH.

**Concepto clave:**

<span style="color:gray">$F = f(I) \quad \text{donde} \quad F = \frac{\text{número de spikes}}{\text{duración del pulso}}$</span>

---

### 🔹 **Lab 4 — FitzHugh–Nagumo (Reducción de Dimensionalidad)**

**Objetivo:**
Explorar una versión reducida del modelo HH para estudiar su comportamiento en el plano de fase mediante nulclinas y puntos de equilibrio.

**Ecuaciones:**

<span style="color:gray">$\frac{dV}{dt} = V - \frac{V^3}{3} - w + I_{ext}(t)$</span>

<span style="color:gray">$\frac{dw}{dt} = \frac{V + a - bw}{\tau}$</span>

**Análisis incluidos:**

- Nulclinas:
  <span style="color:gray">$\frac{dV}{dt} = 0$</span>,
  <span style="color:gray">$\frac{dw}{dt} = 0$</span>
- Puntos de equilibrio
- Plano de fase dinámico

---

### 🔹 **Lab 5 — Modelo LIF (Leaky Integrate-and-Fire)**

**Objetivo:**
Implementar y analizar un modelo neuronal simplificado con integración lineal, umbral de disparo y reinicio.

**Ecuación base:**

<span style="color:gray">$\tau_m \frac{dV}{dt} = -(V - V_{rest}) + R_m I(t)$</span>

**Condición de disparo:**

<span style="color:gray">$\text{si } V \geq V_{th} \Rightarrow V \leftarrow V_{reset}$</span>

### 🔹 **Lab 6 — Análisis estadístico en trenes de spikes**

**Objetivo:**
Caracterizar y comparar la actividad neuronal bajo diferentes niveles de estimulación visual mediante el análisis estadístico de trenes de spikes.

**Métricas principales:**  
- **Tasa de disparo (Firing Rate):** comparación entre condiciones de luz baja y alta.  
- **Intervalos entre spikes (ISI):** cálculo del coeficiente de variación \(CV = \frac{\sigma_{ISI}}{\mu_{ISI}}\).  
- **Factor de Fano:** medida de variabilidad \(FF = \frac{\sigma_X^2}{\mu_X}\) con bins de 50 ms.

**Interpretación:**  
| Métrica | ≈ 0 | ≈ 1 | > 1 |
|----------|------|------|------|
| **CV / FF** | Disparo tónico | Proceso Poisson | Disparo en ráfagas |

**Resultados clave:**  
- Firing rate luz baja: **25.0 spikes/s**  
- Firing rate luz alta: **32.3 spikes/s**  
- Incremento: **+7.3 spikes/s (29.2 %)**
---

## Autor

**Juan Carlos Trejos Iglesias**
Proyecto de Modelos Neuronales — Neurociencias Computacionales
Universidad Nacional de Colombia - Manizales

---

📂 *Cada carpeta contiene su propio README con explicaciones, código fuente y resultados gráficos.*
