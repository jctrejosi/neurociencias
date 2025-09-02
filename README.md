# Membrana celular

## 1) Ley básica — forma óhmica para canales

**Ecuación (forma compacta):**

```math
I_x = g_x \, (V_m - E_x)
```

------

### Definición de términos

- **Iₓ** — Corriente del ion *x* por unidad de área. Unidades típicas: **µA/cm²** (o A/m²).
  - Convención: **Iₓ > 0** significa corriente neta *saliente* (carga positiva saliendo del interior).
- **gₓ** — **Conductancia** específica del canal para el ion $x$. Unidades: **mS/cm²**.
  - Puede ser constante o depender de Vₘ y del tiempo (gating).
- **Vₘ** — Potencial de membrana (voltaje interior respecto al exterior). Unidades: **mV**.
- **Eₓ** — Potencial de reversión (potencial de Nernst) del ion *x*. Unidades: **mV**.
  - Si *Vₘ* = *Eₓ* ⇒ *Iₓ* = 0 (no hay flujo neto de ese ion).

------

### Interpretación física (intuitiva)

- La fórmula es **Ohm aplicada a un canal**: la conductancia *gₓ* actúa como una «resistencia» y la diferencia *Vₘ* - *Eₓ* es la **fuerza motriz** (driving force).
- Si *Vₘ* - *Eₓ* > *0* → corriente positiva (salida neta de carga positiva).
- Si *Vₘ* - *Eₓ* < *0* → corriente negativa (entrada neta de carga positiva).
- Para aniones (p. ej. *Cl⁻* ) la interpretación física de dirección se hace siempre en términos de **carga**: *Iₓ* > *0* = salida neta de carga positiva del interior.

------

### Unidades y conversión rápida

```math
\because\quad 
1\ \text{mS} = 10^{-3}\ \text{S}, \quad 
1\ \text{mV} = 10^{-3}\ \text{V}
```

```math
\text{mS/cm}^2 \times \text{mV} = \mu\text{A/cm}^2
```

```math
\Rightarrow\quad 
(10^{-3})(10^{-3}) = 10^{-6}\ \text{A} = 1\ \mu\text{A}

```



------

### Ejemplo numérico

Supongamos valores tipo Hodgkin–Huxley:

```math
g_K = 36 \,\text{mS/cm}^2
\\
V_m = -70 \,\text{mV}
\\
E_K = -95 \,\text{mV}
\\
I_K = g_K \,(V_m - E_K) 
      = 36 \cdot (-70 - (-95)) 
      = 36 \cdot 25 
      = 900 \,\mu\text{A/cm}^2
\\
I_K > 0 \quad \Longrightarrow \quad 
\text{corriente neta saliente de } K^+ 
\; (\text{el potasio sale del interior})

```

------

### Nota práctica

- En modelos sencillos usamos Iₓ = gₓ(Vₘ - Eₓ).

- En modelos más precisos, la conductancia depende de compuertas, y en casos donde la dependencia por concentración o voltaje es fuerte se utiliza la ecuación de Goldman–Hodgkin–Katz (GHK) en lugar de la forma lineal.

  ```math
  g_{\mathrm{Na}} = \bar{g}_{\mathrm{Na}} \, m^3 \, h
  
  ```

  

------

# 2) Potencial de Nernst (potencial de reversión)

Fórmula:
$$
E_x \;=\; \frac{R\,T}{z_x\,F}\,\ln\!\left(\frac{[x]_{\text{out}}}{[x]_{\text{in}}}\right)
$$

- $R=8.314\ \mathrm{J/(mol\cdot K)}$
- $T$ temperatura absoluta [K]
- $F=96485.332\ \mathrm{C/mol}$ (constante de Faraday)
- $z_x$ valencia (e.g. $z_{K}=+1$, $z_{Ca}=+2$, $z_{Cl}=-1$)
- Concentraciones en molar (o mM) dentro/afuera.

**Nota:** si quieres usar $\log_{10}$, multiplica por $\ln 10 \approx 2.302585$.

------

## Ejemplo numérico (cálculo paso a paso)

Usamos $T=310\ \mathrm{K}$ (~37 °C). Primero calculamos el factor $\dfrac{R T}{F}$:

- $R\cdot T = 8.314 \cdot 310 = 2577.34$ (J/mol)
- Dividir por $F$: $2577.34 / 96485.332 \approx 0.02671225$ (V) ≈ **26.712 mV** (por unidad de ln).

**E_K** con $[K^+]_{\text{out}}=4\ \mathrm{mM},\ [K^+]_{\text{in}}=140\ \mathrm{mM}$:

- razón: $4/140 = 0.0285714286$
- $\ln(0.0285714286) = -\ln(35) \approx -3.55534806$.
- $E_K = 26.712\ \text{mV}\times(-3.55534806) \approx -94.97\ \text{mV}.$

**E_Na** con $[Na^+]_{\text{out}}=145\ \mathrm{mM},\ [Na^+]_{\text{in}}=15\ \mathrm{mM}$:

- razón: $145/15 \approx 9.6666667$
- $\ln(9.6666667)\approx 2.26864$.
- $E_{Na} = 26.712\ \text{mV}\times 2.26864 \approx +60.60\ \text{mV}.$

> Conclusión: $E_K\approx -95\ \text{mV}$, $E_{Na}\approx +60\ \text{mV}$. Valores típicos en fisiología.

------

# 3) Ecuación de la membrana (compartimento único)

La membrana tiene capacidad $C_m$ por unidad de área; la ley de Kirchhoff da:
$$
C_m\,\frac{dV_m}{dt} = -\sum_x I_x + I_{\text{ext}}
$$
usando la forma ohmica:
$$
C_m\,\frac{dV_m}{dt} = -\sum_x g_x(V_m - E_x) + I_{\text{ext}}(t)
$$

- $I_{\text{ext}}$ corriente inyectada (positivo saliente/entrante según convención).
- Si separas fuga (leak): $g_\text{leak}, E_\text{leak}$ son constantes.

------

# 4) Conductancias dependientes de canal (Hodgkin–Huxley)

En neuronas reales $g_x$ depende de compuertas (variables de activación/inactivación) y del voltaje:
$$
g_{Na}(t,V) = \bar g_{Na}\, m^3(t)\, h(t),\qquad
g_K(t,V) = \bar g_K\, n^4(t)
$$
donde las compuertas siguen dinámicas de primer orden:
$$
\frac{dm}{dt} = \alpha_m(V)\,(1-m) - \beta_m(V)\,m
$$
y análogas para $n$, $h$. Éste es el núcleo del **modelo Hodgkin–Huxley** que genera spikes reales (AP).

------

# 5) Diferencia entre conductancia (g) y permeabilidad (P)

- **g** (mS/cm²): modelo lineal tipo Ohm — sencillo y útil cuando el canal tiene corriente proporcional a $V_m-E_x$.
- **P** (GHK): cuando la dependencia por concentración y por $V_m$ es fuerte y no lineal, usa la ecuación de Goldman–Hodgkin–Katz (GHK) para la corriente:

$$
I_x = P_x z_x^2 \frac{F^2}{R T}\,\frac{V_m}{1-e^{-z_x F V_m/(R T)}}\Big([x]_{\text{in}} - [x]_{\text{out}} e^{-z_x F V_m/(R T)}\Big).
$$

GHK es más fiel cuando hay gradientes grandes y $V_m$ grande; para pequeños $V_m$ la forma ohmica es una buena aproximación.

------

# 6) Constantes útiles y la “batería” de la membrana

- Cuando $V_m = E_x$ → $I_x = 0$. Esto es **equilibrio electroquímico** para ese ion.
- El **potencial de reposo** $V_{rest}$ se obtiene por la combinación de conductancias: por ejemplo con Na, K y leak:

$$
V_{rest} \approx \frac{g_K E_K + g_{Na} E_{Na} + g_{L} E_L}{g_K + g_{Na} + g_L}
$$

(ley de divisores conductivos).

------

# 7) Constante de tiempo y resistencia

- Resistencia de membrana por área $R_m = 1/g_m$ [kΩ·cm²], $C_m$ [μF/cm²].
- **Constante de tiempo**: $\tau_m = R_m C_m$. Determina cuánto tarda $V_m$ en cambiar ante una corriente. (p. ej. $C_m\approx 1\ \mu\mathrm{F/cm}^2$, $R_m$ variable; $\tau$ típicamente 10–100 ms según neurona).

------

# 8) ¿Cómo construir el modelo matemáticamente? — pasos prácticos

1. **Decide el nivel de detalle**: Ohmic conductance (rápido) o Hodgkin–Huxley completo (p/ spikes) o GHK (cuando la dependencia de concentración importa).

2. **Recolecta datos**: $[x]_{in/out}$, $C_m$, $\bar g_x$ (máximas conductancias), funciones $\alpha,\beta$ si usas HH.

3. **Calcula $E_x$** con Nernst (ver ejemplo).

4. **Escribe la ODE**:
   $$
   C_m \frac{dV}{dt} = -\sum_x \bar g_x\,(\text{gating})\,(V-E_x) + I_{\text{ext}}.
   $$
   y las ODEs para cada variable de compuerta.

5. **Integra numéricamente** (RK4 o solvers adaptativos). Euler explícito puede usarse como ejercicio, pero para HH usa métodos más estables (RK4, o `odeint/solve_ivp` en Python).

6. **Valida**: compara valores estacionarios (resolver $dV/dt=0$) y curvas I–V.

------

# 9) Relación con tus conceptos listados

- $I_x = g_x (V_m - E_x)$ → ya está.
- $g_x$ y $R_x=1/g_x$ → unidades y relación.
- $E_x$ = Nernst → fórmula dada y ejemplo.
- $R_l$ → resistencia asociada a canales de pérdida → es $1/g_{\text{leak}}$.
- $V_{\text{rest}}$ y $V_{\text{th}}$ → $V_{\text{rest}}$ sale de combinación de $E_x$ y conductancias; $V_{\text{th}}$ es un umbral práctico (en modelos más simples disparas un spike cuando $V$ cruza $V_{\text{th}}$).
- **Spike / AP** → en modelos HH surge por la interacción no lineal de $g_{Na}(V,t)$ y $g_K(V,t)$.

------

# 10) Ejemplo compacto (modelo de 3 corrientes tipo HH simplificado)

Ecuaciones:
$$
\begin{aligned}
C_m \frac{dV}{dt} &= -\big(g_{Na}^*(V,t)(V-E_{Na}) + g_K^*(V,t)(V-E_K) + g_L(V-E_L)\big) + I_{\text{ext}}\\[4pt]
g_{Na}^*(V,t) &= \bar g_{Na}\,m^3 h,\qquad \frac{dm}{dt}=\alpha_m(1-m)-\beta_m m,\ \text{etc.}
\end{aligned}
$$
Con parámetros y funciones $\alpha,\beta$ de Hodgkin–Huxley obtienes spikes con forma realista.

### Canales iónicos: funciones principales

- **Canales de sodio (Na⁺):**
  - Cuando se abren → entra Na⁺.
  - El interior de la célula se vuelve **menos negativo** → **despolarización**.
- **Canales de potasio (K⁺):**
  - Cuando se abren → sale K⁺.
  - La membrana **vuelve a hacerse negativa (repolarización)** o incluso **más negativa que el reposo (hiperpolarización)** si el flujo es excesivo.
- **Canales de calcio (Ca²⁺):**
  - Cuando se abren → entra Ca²⁺.
  - Desencadenan **señalización intracelular** y **liberación de neurotransmisores** en sinapsis.
- **Canales de cloro (Cl⁻):**
  - Cuando se abren → entra Cl⁻.
  - Interior más negativo → **estabiliza** o **hiperpolariza** la membrana.

### Cambios en el potencial de membrana

1. **Despolarización**
   - El potencial se vuelve **menos negativo** (ej. de –70 mV a –40 mV o incluso positivo).
   - **Causa típica:** apertura de canales de Na⁺ (entrada de cargas positivas).
   - **Consecuencia:** la célula se acerca al **umbral** para disparar un potencial de acción.
2. **Repolarización**
   - Después de la despolarización, la membrana **regresa a su potencial de reposo** (≈ –70 mV).
   - **Causa típica:** apertura de canales de K⁺ (salida de cargas positivas).
3. **Hiperpolarización**
   - El potencial se vuelve **más negativo que el reposo** (ej. de –70 mV a –80 mV).
   - **Causa típica:** canales de K⁺ que permanecen abiertos más tiempo del necesario o entrada de Cl⁻.
   - **Consecuencia:** la célula es **menos excitable** porque queda más lejos del umbral.

------

### Resumen gráfico (conceptual)

- **Despolarización → entra Na⁺ → célula más positiva → potencial de acción inicia.**
- **Repolarización → sale K⁺ → célula vuelve a negativo → fin del potencial de acción.**
- **Hiperpolarización → exceso de salida de K⁺ o entrada de Cl⁻ → célula más negativa que el reposo → menor excitabilidad.**



### **Constantes físicas**

- **R** — Constante universal de los gases, $8.314\ \mathrm{J/(mol·K)}$.
- **T** — Temperatura absoluta en kelvin $[K]$.
- **F** — Constante de Faraday, $96485.332\ \mathrm{C/mol}$.
- **zₓ** — Valencia o carga del ion $x$ (ej.: $z_K = +1$, $z_{Ca} = +2$, $z_{Cl} = -1$).

------

### **Potenciales**

- **Vₘ** — Potencial de membrana [mV]; diferencia de voltaje entre interior y exterior celular.
- **Eₓ** — Potencial de reversión o de Nernst para el ion $x$ [mV]; cuando $Vₘ = Eₓ$, no hay flujo neto de ese ion.
- **Vᵣₑₛₜ** — Potencial de reposo de la neurona (~ −60 mV).
- **Vₜₕ** — Potencial umbral para disparar un potencial de acción (AP).
- **Eᴸ** — Potencial de fuga (leak) asociado a canales pasivos.

------

### **Corrientes y conductancias**

- **Iₓ** — Corriente del ion $x$ [µA/cm²]; positiva si salen cargas positivas, negativa si entran.
- **gₓ** — Conductancia específica del canal para el ion $x$ [mS/cm²]; mide qué tan fácil fluye el ion.
- **Rₓ** — Resistencia específica del canal para el ion $x$ [Ω·cm² o kΩ·cm²]; es $Rₓ = 1/gₓ$.
- **gᴸ** — Conductancia de fuga (canales pasivos).
- **Rᴸ** — Resistencia de fuga (canales pasivos); $Rᴸ = 1/gᴸ$.
- **Iₑₓₜ** — Corriente externa inyectada (puede ser experimental o simulada).

------

### **Propiedades de la membrana**

- **Cₘ** — Capacitancia de membrana por área [µF/cm²]; almacena carga eléctrica.
- **τₘ = RₘCₘ** — Constante de tiempo de la membrana, mide qué tan rápido cambia $Vₘ$.
- **ĝₓ** — Conductancia máxima posible de un canal cuando está completamente abierto.

------

### **Variables de compuerta (modelo Hodgkin–Huxley)**

- **m, h, n** — Variables de activación/inactivación (sin unidades, entre 0 y 1).
- **αₘ(V), βₘ(V)** — Funciones de transición dependientes del voltaje que controlan la dinámica de $m$.
- **gₓ\*(V,t)** — Conductancia efectiva en el tiempo, por ejemplo $g_{Na}^*(t) = ĝ_{Na} m^3 h$.

------

### **Otros conceptos**

- **[x]ᵢₙ, [x]ₒᵤₜ** — Concentraciones intracelular y extracelular de cada ion $x$ [mM].

- **Spike** — Onda de potencial de acción.

- **AP (Action Potential)** — Potencial de acción, disparo rápido de voltaje en la neurona.

- **GHK (Goldman–Hodgkin–Katz)** — Ecuación más precisa para corrientes iónicas que la aproximación lineal $Iₓ = gₓ(Vₘ - Eₓ)$.

- **Potencial de Nernst** — Potencial de equilibrio para un ion específico, dado por
  $$
  Eₓ = \frac{RT}{zₓF}\ln\!\frac{[x]_{out}}{[x]_{in}}.
  $$