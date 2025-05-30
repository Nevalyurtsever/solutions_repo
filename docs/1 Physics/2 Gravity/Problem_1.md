Certainly! Here's a comprehensive and readable English version of the content you provided, including explanations and relevant images.

---

## 🪐 Problem 1: Kepler’s Third Law for Circular Orbits

### 1.1 Derivation of Kepler’s Third Law

Kepler’s Third Law states that the square of the orbital period $T$ is proportional to the cube of the orbital radius $r$:

$$
T^2 \propto r^3
$$

This relationship can be derived using Newton's Law of Gravitation and the concept of centripetal force.

**Derivation Steps:**

1. **Gravitational Force:**
   Newton's Law of Gravitation provides the force between two masses:

   $$
   F_{\text{gravity}} = \frac{G M m}{r^2}
   $$

   Where:

   - $G$ is the gravitational constant,
   - $M$ is the mass of the central body (e.g., the Sun),
   - $m$ is the mass of the orbiting object (e.g., a planet),
   - $r$ is the distance between the two masses.

2. **Centripetal Force:**
   For circular motion, the necessary centripetal force is:

   $$
   F_{\text{centripetal}} = \frac{m v^2}{r}
   $$

3. **Equating the Forces:**
   Setting gravitational force equal to centripetal force:

   $$
   \frac{G M m}{r^2} = \frac{m v^2}{r}
   $$

   Simplifying:

   $$
   v^2 = \frac{G M}{r}
   $$

4. **Relating Velocity to Period:**
   The orbital period $T$ is the time it takes to complete one orbit:

   $$
   T = \frac{2\pi r}{v}
   $$

   Substituting $v$:

   $$
   T = \frac{2\pi r}{\sqrt{\frac{G M}{r}}} = 2\pi \sqrt{\frac{r^3}{G M}}
   $$

   Therefore:

   $$
   T^2 = \frac{4\pi^2 r^3}{G M}
   $$

This derivation confirms that $T^2 \propto r^3$, which is Kepler’s Third Law.

**Illustration:**

![Kepler's Third Law Diagram](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Kepler%27s_laws_diagram.svg/500px-Kepler%27s_laws_diagram.svg.png)

_Source: [Wikipedia - Kepler's laws of planetary motion](https://en.wikipedia.org/wiki/Kepler%27s_laws_of_planetary_motion)_

---

### 1.2 Implications of Kepler’s Third Law

- **Longer Periods for Larger Orbits:**
  Planets farther from the Sun have longer orbital periods. For example, Neptune takes about 165 Earth years to complete one orbit.

- **Predicting Orbital Characteristics:**
  Knowing the distance of a planet from the Sun allows us to calculate its orbital period, and vice versa.

- **Determining Central Masses:**
  Rearranging the derived formula:

  $$
  M = \frac{4\pi^2 r^3}{G T^2}
  $$

  This allows us to calculate the mass $M$ of the central body if $r$ and $T$ are known.

---

## 🕰️ Problem 2: Forced Damped Pendulum

### 2.1 Theoretical Foundation

The motion of a forced damped pendulum is described by the nonlinear second-order differential equation:

$$
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \sin(\theta) = A \cos(\omega t)
$$

Where:

- $\theta(t)$: Angular displacement,
- $\gamma$: Damping coefficient,
- $\omega_0 = \sqrt{\frac{g}{L}}$: Natural angular frequency,
- $A$: Amplitude of the driving force,
- $\omega$: Frequency of the external driving force.

**Small-Angle Approximation:**

For small angles ($\theta < 0.2$ rad), $\sin(\theta) \approx \theta$, simplifying the equation to:

$$
\frac{d^2\theta}{dt^2} + \gamma \frac{d\theta}{dt} + \omega_0^2 \theta = A \cos(\omega t)
$$

This is a linear non-homogeneous second-order differential equation.

**Solution Components:**

- **Homogeneous Solution (Transient):**

  $$
  \theta_{\text{hom}}(t) = C_1 e^{-\gamma t / 2} \cos(\omega_d t) + C_2 e^{-\gamma t / 2} \sin(\omega_d t)
  $$

  Where $\omega_d = \sqrt{\omega_0^2 - (\gamma/2)^2}$ is the damped natural frequency.

- **Particular Solution (Steady-State):**

  $$
  \theta_{\text{part}}(t) = B \cos(\omega t - \phi)
  $$

  Where:

  - $B = \frac{A}{\sqrt{(\omega_0^2 - \omega^2)^2 + (\gamma \omega)^2}}$,
  - $\tan(\phi) = \frac{\gamma \omega}{\omega_0^2 - \omega^2}$.

**Resonance Condition:**

Maximum amplitude occurs when the denominator of $B$ is minimized:

$$
\omega_{\text{res}} = \sqrt{\omega_0^2 - \frac{\gamma^2}{2}}
$$

---

### 2.2 Analysis of Dynamics

The behavior of a forced damped pendulum depends on:

- **Damping ($\gamma$):**

  - Low damping: Sustained oscillations and sharp resonance.
  - High damping: Suppressed motion and reduced resonance.

- **Driving Amplitude ($A$):**

  - Small $A$: Regular, periodic motion.
  - Large $A$: Complex or chaotic behavior.

- **Driving Frequency ($\omega$):**

  - Near $\omega_0$: Resonance with large oscillations.
  - Away from $\omega_0$: Periodic, quasiperiodic, or chaotic motion depending on $A$ and $\gamma$.

As parameters change, the system can transition from simple harmonic motion to chaos, often through period doubling.

**Visualizations:**

- **Time Series:** Shows how $\theta(t)$ evolves over time.
- **Phase Portraits:** Plots of $\theta$ vs. $\dot{\theta}$ to visualize trajectories in phase space.
- **Poincaré Sections:** Samples the system at fixed intervals to reveal periodic or chaotic dynamics.

**Illustrations:**

_Time Series Example:_

![Time Series](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Driven_pendulum_time_series.svg/500px-Driven_pendulum_time_series.svg.png)

_Phase Portrait Example:_

![Phase Portrait](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2c/Driven_pendulum_phase_portrait.svg/500px-Driven_pendulum_phase_portrait.svg.png)

_Poincaré Section Example:_

![Poincaré Section](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7e/Driven_pendulum_poincare_section.svg/500px-Driven_pendulum_poincare_section.svg.png)

_Source: [Wikipedia - Driven damped pendulum](https://en.wikipedia.org/wiki/Driven_pendulum)_

---

### 2.3 Practical Applications

The forced damped pendulum model applies to various real-world systems:

- **Energy Harvesting Devices:**
  Devices that capture energy from mechanical vibrations can be modeled to optimize energy extraction under periodic forces.

- **Suspension Bridges:**
  Understanding oscillations under periodic forces (like wind or traffic) is crucial to prevent structural failures due to resonance.

- **Oscillating Circuits:**
  RLC circuits in electronics exhibit similar behavior, making the model useful for analyzing resonance and damping.

- **Biomechanics (Human Gait):**
  The model helps in understanding human locomotion, aiding in prosthetics design and studying movement disorders.

---

### 2.4 Implementation

**Objective:**

Simulate the forced damped pendulum system to analyze its behavior under varying parameters.

**Python Simulation:**

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Parameters
m = 1.0       # mass (kg)
L = 1.0       # length (m)
g = 9.8       # gravity (m/s^2)
gamma = 0.2   # damping coefficient
omega_0 = np.sqrt(g / L)
F_0 = 1.0     # driving force amplitude
omega = 1.0   # driving frequency

# Differential equations
def pendulum(t, y):
    theta, omega_theta = y
    dydt = [omega_theta, -gamma * omega_theta - (g / L) * np.sin(theta) + F_0 * np.cos(omega * t)]
    return dydt

# Initial conditions
theta0 = 0.1
omega_theta0 = 0.0
t_span = (0, 100)
t_eval = np.linspace(0, 100, 10000)

# Solve ODE
sol = solve_ivp(pendulum, t_span, [theta0, omega_theta0], t_eval=t_eval)

# Plot results
plt.figure(figsize=(10, 6))
plt.plot(sol.t, sol.y[0], label='Theta (rad)', color='b')
plt.title('Forced Damped Pendulum Motion')
plt.xlabel('Time (s)')
plt.ylabel('Angular Displacement (rad)')
plt.grid(True)
plt.legend()
plt.show()

# Phase diagram
plt.figure(figsize=(10, 6))
plt.plot(sol.y[0], sol.y[1], label='Phase Space')
plt.title('Phase Space of the Forced Damped Pendulum')
plt.xlabel('Theta (rad)')
plt.ylabel('Angular Velocity (rad/s)')
plt.grid(True)
plt.legend()
plt.show()
```

**Simulation Outputs:**

_Time Series Plot:_

!\[Time Series Plot]\([https://i.imgur](https://i.imgur)
