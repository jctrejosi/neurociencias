# 🧠 Neurociencias Computacionales

Este repositorio contiene una serie de **laboratorios prácticos** orientados al modelamiento computacional de neuronas.
Se abordan desde ecuaciones diferenciales simples hasta modelos biofísicos complejos como el de **Hodgkin–Huxley** y sus variantes reducidas.

Cada laboratorio incluye **código, notebooks, resultados gráficos y análisis teóricos**.

---

## 📚 Contenido

- [**Lab 1 — Método de Heun–Euler**](./Lab1%20-%20Método%20de%20Heun%20Euler%20para%20solucionar%20EC%20Diferenciales)
  Simulación del potencial de membrana mediante integración numérica con los métodos de Euler y Heun.

- [**Lab 2 — Modelo de Hodgkin–Huxley (HH)**](./Lab2%20-%20Modelo%20Hodgkin-Huxley)
  Implementación del modelo biofísico de canales iónicos de sodio y potasio dependientes de voltaje.

- [**Lab 3 — Curvas F–I (Frecuencia–Corriente)**](./Lab3%20-%20Curva%20F-I%20con%20HH)
  Relación entre la corriente inyectada y la frecuencia de disparo neuronal en el modelo HH.

- [**Lab 4 — FitzHugh–Nagumo (Reducción de Dimensionalidad)**](./Lab4%20-%20Reducción%20de%20dimensionalidad%20(Campos%20vectoriales))
  Simplificación del modelo HH y análisis de nulclinas, puntos de equilibrio y plano de fase.

- [**Lab 5 — Modelo LIF (Leaky Integrate-and-Fire)**](./Lab5%20-%20Modelo%20LIF)
  Modelo simplificado basado en umbral y reinicio del potencial de membrana.

---

## 🧩 Resumen de los Laboratorios

---

### 🔹 **Lab 1 — Método de Heun–Euler**

**Objetivo:**
Aplicar los métodos numéricos de Euler y Heun para resolver ecuaciones diferenciales que modelan la dinámica neuronal.

**Ecuaciones:**

![eq1](https://latex.codecogs.com/svg.image?\frac{dV}{dt}=V-V^3-w+I)

![eq2](https://latex.codecogs.com/svg.image?\frac{dw}{dt}=\frac{V+a-bw}{\tau})

---

### 🔹 **Lab 2 — Modelo de Hodgkin–Huxley**

**Objetivo:**
Simular la generación y propagación del potencial de acción a partir de canales iónicos dependientes de voltaje.

**Ecuaciones principales:**

![eq3](https://latex.codecogs.com/svg.image?C_m\frac{dV}{dt}=I-g_{Na}m^3h(V-E_{Na})-g_Kn^4(V-E_K)-g_L(V-E_L))

![eq4](https://latex.codecogs.com/svg.image?\frac{dn}{dt}=\alpha_n(V)(1-n)-\beta_n(V)n)

![eq5](https://latex.codecogs.com/svg.image?\frac{dm}{dt}=\alpha_m(V)(1-m)-\beta_m(V)m)

![eq6](https://latex.codecogs.com/svg.image?\frac{dh}{dt}=\alpha_h(V)(1-h)-\beta_h(V)h)

---

### 🔹 **Lab 3 — Curvas F–I (Frecuencia–Corriente)**

**Objetivo:**
Estudiar la relación entre la **corriente inyectada (I)** y la **frecuencia de disparo (F)** en el modelo HH.

**Concepto clave:**

![eq7](https://latex.codecogs.com/svg.image?F=f(I)\quad\text{donde}\quad%20F=\frac{\text{número%20de%20spikes}}{\text{duración%20del%20pulso}})

---

### 🔹 **Lab 4 — FitzHugh–Nagumo (Reducción de Dimensionalidad)**

**Objetivo:**
Explorar una versión reducida del modelo HH para estudiar su comportamiento en el plano de fase mediante nulclinas y puntos de equilibrio.

**Ecuaciones:**

![eq8](https://latex.codecogs.com/svg.image?\frac{dV}{dt}=V-\frac{V^3}{3}-w+I_{ext}(t))

![eq9](https://latex.codecogs.com/svg.image?\frac{dw}{dt}=\frac{V+a-bw}{\tau})

**Análisis incluidos:**

- Nulclinas: ![eq10](https://latex.codecogs.com/svg.image?\frac{dV}{dt}=0), ![eq11](https://latex.codecogs.com/svg.image?\frac{dw}{dt}=0)
- Puntos de equilibrio
- Plano de fase dinámico

---

### 🔹 **Lab 5 — Modelo LIF (Leaky Integrate-and-Fire)**

**Objetivo:**
Implementar y analizar un modelo neuronal simplificado con integración lineal, umbral de disparo y reinicio.

**Ecuación base:**

![eq12](https://latex.codecogs.com/svg.image?\tau_m\frac{dV}{dt}=-(V-V_{rest})+R_mI(t))

**Condición de disparo:**

![eq13](https://latex.codecogs.com/svg.image?\text{si%20}V\geq%20V_{th}\Rightarrow%20V\leftarrow%20V_{reset})

---

## 👨‍🔬 Autor

**Juan Carlos Trejos Iglesias**
Proyecto de Modelos Neuronales — Neurociencias Computacionales
Universidad / Grupo de Investigación (si aplica)

---

📂 *Cada carpeta contiene su propio README con explicaciones, código fuente y resultados gráficos.*
