Here is your content rewritten in clear, professional English for better readability:

---

# Problem 1

## 1-1. Derivation of Kepler’s Third Law for Circular Orbits (with Code)

Kepler’s Third Law states that the square of the orbital period $T$ is proportional to the cube of the orbital radius $r$:

$$
T^2 \propto r^3
$$

We can derive this relationship using Newton’s Law of Universal Gravitation and the equation for centripetal force.

### Step-by-Step Derivation

**Gravitational Force:**

The gravitational force acting between two objects is:

$$
F = \frac{G M m}{r^2}
$$

Where:

- $G$ is the gravitational constant,
- $M$ is the mass of the central body,
- $m$ is the mass of the orbiting object,
- $r$ is the orbital radius.

This gravitational force provides the necessary centripetal force to keep the object in a circular orbit:

$$
\frac{G M m}{r^2} = \frac{m v^2}{r}
$$

Solving for $v$, the orbital speed:

$$
v^2 = \frac{G M}{r}
$$

The orbital period $T$ is the time it takes to complete one orbit:

$$
T = \frac{2\pi r}{v}
\Rightarrow T^2 = \frac{4\pi^2 r^2}{v^2}
$$

Substituting for $v^2$:

$$
T^2 = \frac{4\pi^2 r^3}{G M}
$$

Thus confirming:

$$
T^2 \propto r^3
$$

---

## 1-2. Implications of Kepler’s Third Law

- **Longer Orbits Take More Time**: Celestial objects farther from the central body (like outer planets) take longer to complete one orbit.

- **Predictive Power**: Knowing the radius of an orbit, we can predict the period, and vice versa.

- **Estimating Masses**: Rearranging the law allows us to estimate the mass $M$ of the central body:

$$
M = \frac{4\pi^2 r^3}{G T^2}
$$

**Example**: The Moon’s orbit can be used to estimate Earth’s mass using its known period and orbital radius.

---

## 1-3. Mathematical Formulation

For two orbiting objects:

$$
\frac{T_1^2}{T_2^2} = \frac{r_1^3}{r_2^3}
$$

This form is useful for comparing satellites or planets orbiting the same central body.

---

## 1-4. Derivation of the Forced Damped Pendulum Equation

A **forced damped pendulum** experiences both damping (e.g., friction) and an external periodic force. Its motion is governed by the second-order nonlinear differential equation:

$$
\frac{d^2\theta}{dt^2} + 2\gamma \frac{d\theta}{dt} + \omega_0^2 \sin(\theta) = F_0 \cos(\omega t)
$$

Where:

- $\theta(t)$ is the angular displacement,
- $\gamma$ is the damping coefficient,
- $\omega_0 = \sqrt{g/L}$ is the natural angular frequency,
- $F_0$ is the amplitude of the external driving force,
- $\omega$ is the driving frequency.

### Small-Angle Approximation

For small angles ($\theta < 0.2$ rad), $\sin(\theta) \approx \theta$, simplifying the equation to:

$$
\frac{d^2\theta}{dt^2} + 2\gamma \frac{d\theta}{dt} + \omega_0^2 \theta = F_0 \cos(\omega t)
$$

This is a linear non-homogeneous differential equation, easier to analyze and simulate.

---

## 4.2 Numerical Simulation

The forced damped pendulum can be numerically solved using methods like the **Runge-Kutta method**. This allows for:

- Time-series analysis,
- Phase portraits,
- Bifurcation diagrams,
- Poincaré sections,

to study complex behaviors like resonance, quasiperiodicity, and chaos.

---
