---

## 🚀 Problem 2: Escape Velocities and Cosmic Velocities

---

### 🧠 **Task 1: Define the first, second, and third cosmic velocities**

#### 🔹 First Cosmic Velocity (Orbital Velocity)

* **Definition**: The minimum speed required to enter a stable circular orbit around a celestial body just above its surface.
* **Formula**:

$$
    v_1 = \sqrt{\frac{G M}{r}}
$$

#### 🔹 Second Cosmic Velocity (Escape Velocity)

* **Definition**: The minimum speed needed to escape a celestial body’s gravitational field entirely, without further propulsion.
* **Formula**:

$$
    v_2 = \sqrt{2} \cdot v_1 = \sqrt{\frac{2 G M}{r}}
$$

#### 🔹 Third Cosmic Velocity (Interstellar Escape)

* **Definition**: The velocity needed to escape the gravitational pull of a planetary system (e.g., the Sun).
* **Approximation**:

$$
    v_3 = \sqrt{v_{esc\_planet}^2 + v_{esc\_sun}^2}
$$

---

### 📐 **Task 2: Mathematical Derivations and Parameters**

#### ✅ Escape Velocity Derivation

From conservation of energy:

$$
\text{Kinetic Energy} = \text{Gravitational Potential Energy} \\
\frac{1}{2} m v^2 = \frac{G M m}{r}
$$

Solving for $v$:

$$
    v = \sqrt{\frac{2 G M}{r}}
$$

* $G$: Gravitational constant
* $M$: Mass of the celestial body
* $r$: Radius (distance from center of mass)

---

### 💻 Python Code – Derivation Verification

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # m^3/kg/s^2

# Function to calculate velocities
def compute_cosmic_velocities(M, r):
    v1 = np.sqrt(G * M / r)
    v2 = np.sqrt(2 * G * M / r)
    return v1, v2

# Earth values
M_earth = 5.972e24  # kg
r_earth = 6.371e6   # m

v1_earth, v2_earth = compute_cosmic_velocities(M_earth, r_earth)
print(f"Earth: v1 = {v1_earth:.2f} m/s, v2 = {v2_earth:.2f} m/s")
```

---

### 🌍 **Task 3: Compute for Earth, Mars, and Jupiter**

#### 💡 Celestial Data

```python
# Celestial data (mass in kg, radius in m)
bodies = {
    "Earth": (5.972e24, 6.371e6),
    "Mars": (6.417e23, 3.389e6),
    "Jupiter": (1.898e27, 6.9911e7)
}

# Calculate velocities
results = {}
for body, (M, r) in bodies.items():
    v1, v2 = compute_cosmic_velocities(M, r)
    results[body] = (v1, v2)
    print(f"{body}: v1 = {v1/1000:.2f} km/s, v2 = {v2/1000:.2f} km/s")
```

#### 📊 Visualization

```python
labels = list(results.keys())
v1_vals = [results[b][0] for b in labels]
v2_vals = [results[b][1] for b in labels]

x = np.arange(len(labels))
width = 0.35

plt.figure(figsize=(8,5))
plt.bar(x - width/2, [v/1000 for v in v1_vals], width, label='1st Cosmic (v1)')
plt.bar(x + width/2, [v/1000 for v in v2_vals], width, label='2nd Cosmic (v2)')
plt.ylabel('Velocity (km/s)')
plt.title('Cosmic Velocities of Planets')
plt.xticks(x, labels)
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()
```

---

### 🛰️ **Task 4: Importance in Space Exploration**

#### 🚀 Applications:

* **First Cosmic Velocity**: Used to launch satellites into orbit.
* **Second Cosmic Velocity**: Required for lunar and interplanetary missions.
* **Third Cosmic Velocity**: Enables spacecraft to escape the Solar System (e.g., Voyager missions).

#### 🛸 Summary Table

| Cosmic Velocity | Use Case                   | Example                     |
| --------------- | -------------------------- | --------------------------- |
| 1st (v1)        | Orbiting a planet          | Satellite, ISS              |
| 2nd (v2)        | Escaping a planet          | Mars rover, Moon mission    |
| 3rd (v3)        | Leaving a planetary system | Voyager 1 & 2, New Horizons |

Understanding these velocities ensures efficient fuel usage, mission planning, and reaching new frontiers in space exploration.

