Certainly! Here's the professionally rewritten and organized version of your **Forced Damped Pendulum** project in English:

---

## 🎓 2-1-1 Theoretical Foundation

### 🧠 Governing Differential Equation

The **forced damped pendulum** is described by the following nonlinear second-order differential equation:

$$
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \sin(\theta) = A \cos(\omega t)
$$

Where:

- **θ(t):** Angular displacement
- **γ:** Damping coefficient
- **ω₀ = √(g/L):** Natural angular frequency
- **A:** Amplitude of the external driving force
- **ω:** Frequency of the external driving force

---

### 🔍 Small-Angle Approximation

For small angles (θ < 0.2 rad):

$$
\sin(\theta) \approx \theta
$$

This simplifies the equation to a linear form:

$$
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \theta = A \cos(\omega t)
$$

---

### ✅ Analytical Solution

The general solution of this second-order linear non-homogeneous ODE is:

$$
\theta(t) = \theta_{\text{hom}}(t) + \theta_{\text{part}}(t)
$$

#### 📘 Homogeneous (Transient) Solution:

$$
\theta_{\text{hom}}(t) = C_1 e^{-\gamma t/2} \cos(\omega_d t) + C_2 e^{-\gamma t/2} \sin(\omega_d t)
$$

Where:

$$
\omega_d = \sqrt{\omega_0^2 - \left(\frac{\gamma}{2}\right)^2}
$$

#### 📘 Particular (Steady-State) Solution:

$$
\theta_{\text{part}}(t) = B \cos(\omega t - \phi)
$$

With:

$$
B = \frac{A}{\sqrt{(\omega_0^2 - \omega^2)^2 + \gamma^2 \omega^2}}, \quad \tan(\phi) = \frac{\gamma \omega}{\omega_0^2 - \omega^2}
$$

---

### 🎯 Resonance Condition

Resonance occurs when the amplitude is maximized, i.e., when the denominator of $B$ is minimized:

$$
\omega_{\text{res}} = \sqrt{\omega_0^2 - 2\gamma^2}
$$

---

## 📊 2-1-2 Dynamics Analysis Summary

The system’s behavior depends on three key parameters:

- **Damping (γ):**

  - Low damping → Sustained oscillations and sharp resonance
  - High damping → Suppressed motion and reduced resonance

- **Driving Amplitude (A):**

  - Small A → Regular periodic motion
  - Large A → Complex or chaotic behavior

- **Driving Frequency (ω):**

  - Near ω₀ → Resonance and large amplitude
  - Far from ω₀ → Periodic, quasiperiodic, or chaotic behavior

As parameters vary, the system may transition from simple harmonic motion to chaos, often via **period doubling**. These behaviors are best visualized using **time series**, **phase portraits**, and **Poincaré sections**.

---

## 🌍 2-1-3 Real-World Applications

1. **Energy Harvesting Devices:**
   Pendulum models help design systems that harvest mechanical vibrations efficiently under periodic driving.

2. **Suspension Bridges:**
   Forced oscillations under wind or traffic loads must be analyzed to prevent resonance-induced failures.

3. **RLC Circuits:**
   Analogous behavior in electrical circuits makes this model useful for analyzing damping and resonance in electronics.

4. **Biomechanics (Human Gait):**
   Useful for understanding walking dynamics and designing prosthetics or studying movement disorders.

---

## 🛠️ 2-1-4 Simulation and Visualization

### 🎯 Objective

This section focuses on advanced simulation of the forced damped pendulum, including:

- **Bifurcation Diagrams** to track how system behavior changes with varying parameters
- **Poincaré Sections** to reveal the underlying structure of chaotic motion
- **Phase Portraits** to visualize trajectories in phase space

---

### 🔬 Tools

#### 📈 Bifurcation Diagram:

Visualizes how long-term system behavior evolves as a parameter (typically A) is varied. It reveals the **route to chaos** via period doubling.

#### 🔁 Poincaré Section:

Samples the system state at regular intervals (e.g., each period of driving force). Helps identify **periodic**, **quasiperiodic**, or **chaotic** regimes.

#### 🌌 Phase Portrait:

Plots angular velocity $\dot{\theta}$ versus angular displacement θ to observe system evolution:

- **Limit cycles** → regular oscillation
- **Strange attractors** → chaotic motion

---

Let me know if you'd like Python implementations (e.g., bifurcation diagrams, Poincaré maps, or phase portraits) to support this theory visually.
