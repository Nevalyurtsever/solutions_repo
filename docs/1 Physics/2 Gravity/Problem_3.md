# 🚀 Problem 3: Trajectories of a Freely Released Payload Near Earth

---

## 🎯 Task 1: Analyze Possible Trajectories

### 🌍 Physical Meaning

When a payload is released near Earth, the path it follows depends on its initial speed and direction:

* **Elliptical Orbit**: If the speed is less than escape velocity and directed tangentially.
* **Parabolic Trajectory**: If the speed is exactly equal to escape velocity.
* **Hyperbolic Trajectory**: If the speed exceeds escape velocity.
* **Suborbital**: If the velocity is insufficient for orbit, it falls back to Earth.

These outcomes are governed by the total specific mechanical energy:

$$
\epsilon = \frac{v^2}{2} - \frac{GM}{r}
$$

* \$\epsilon < 0\$: Elliptical
* \$\epsilon = 0\$: Parabolic
* \$\epsilon > 0\$: Hyperbolic

---

## 🧮 Task 2: Numerical Analysis of Payload Path

### 🧠 Equations of Motion

We model motion using Newton's second law:

$$
\vec{a} = -\frac{GM}{r^3} \vec{r}
$$

Numerical integration (Euler/Runge-Kutta) can be used to simulate motion step by step.

---

## 🐍 Python Simulation: Trajectories Based on Initial Conditions

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # gravitational constant (m^3/kg/s^2)
M = 5.972e24     # mass of Earth (kg)
R_earth = 6.371e6  # radius of Earth (m)

# Initial conditions
r0 = np.array([R_earth + 400e3, 0])  # position (400 km altitude)
v_values = [7000, 7800, 11000]  # test velocities in m/s (different scenarios)
dt = 1  # time step (s)
steps = 15000

plt.figure(figsize=(8, 8))

for v0 in v_values:
    v = np.array([0, v0])
    r = r0.copy()
    trajectory = []

    for _ in range(steps):
        r_mag = np.linalg.norm(r)
        a = -G * M * r / r_mag**3
        v += a * dt
        r += v * dt
        trajectory.append(r.copy())

        # stop if too far
        if r_mag > 10 * R_earth:
            break

    trajectory = np.array(trajectory)
    plt.plot(trajectory[:, 0] / 1000, trajectory[:, 1] / 1000, label=f"v0 = {v0} m/s")

# Earth for reference
theta = np.linspace(0, 2*np.pi, 100)
plt.plot(R_earth*np.cos(theta)/1000, R_earth*np.sin(theta)/1000, 'k')

plt.xlabel("x (km)")
plt.ylabel("y (km)")
plt.title("Payload Trajectories Based on Initial Velocity")
plt.grid(True)
plt.axis("equal")
plt.legend()
plt.tight_layout()
plt.show()
```

---

## 🧭 Task 3: Applications and Scenarios

### 🔍 Real-World Implications

* **Orbital Insertion**: Required velocity and direction to achieve stable orbit.
* **Reentry**: Trajectories falling back to Earth due to low velocity or steep angle.
* **Escape Missions**: Trajectories with \$v > v\_{escape}\$ useful for deep-space probes.

### 🌐 Used In:

* Satellite deployment (e.g., Starlink)
* ISS resupply missions
* Lunar/planetary transfers

---

## 🛠️ Task 4: Simulation Tool Summary

This simulation demonstrates how:

* Initial altitude and velocity control trajectory type
* Increasing velocity transitions orbit → escape
* Python and physics principles combine to model realistic space dynamics

More refined tools may include Runge-Kutta methods, atmospheric drag (for lower altitudes), and multi-body interactions.

---


