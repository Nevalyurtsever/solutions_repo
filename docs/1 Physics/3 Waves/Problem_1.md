# Problem 1
# 🌊 Problem 4: Interference Patterns on a Water Surface

---

## 🎯 Task 1: Define the Physical Setup

### 🔷 Regular Polygon and Source Placement

We consider a regular polygon—e.g., an **equilateral triangle**—with point sources placed at its **vertices** on a water surface. Each point emits **circular waves** with the same amplitude, frequency, and wavelength.

---

## 📐 Task 2: Mathematical Formulation of Waves

### 🧮 Single Wave Expression

A circular wave from a point source at position \$(x\_s, y\_s)\$ is described as:

$$
\eta(x, y, t) = A \cos(k r - \omega t + \phi)
$$

Where:

* \$\eta(x, y, t)\$ is the surface displacement
* \$A\$ is amplitude
* \$k = \frac{2\pi}{\lambda}\$ is the wave number
* \$\omega = 2\pi f\$ is the angular frequency
* \$r = \sqrt{(x - x\_s)^2 + (y - y\_s)^2}\$ is the distance to the source
* \$\phi\$ is the phase (set to 0 for simplicity)

### 🧮 Total Interference (Superposition Principle)

For \$N\$ point sources at \$(x\_i, y\_i)\$:

$$
\eta_{total}(x, y, t) = \sum_{i=1}^N A \cos(k r_i - \omega t)
$$

Where \$r\_i = \sqrt{(x - x\_i)^2 + (y - y\_i)^2}\$ is the distance from point \$(x, y)\$ to source \$i\$.

---

## 🐍 Task 3: Python Simulation – Visualizing Interference

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
A = 1.0            # Amplitude
wavelength = 1.0   # Wavelength (meters)
freq = 1.0         # Frequency (Hz)
k = 2 * np.pi / wavelength
omega = 2 * np.pi * freq

def generate_polygon(n_sides, radius=2.0):
    angles = np.linspace(0, 2*np.pi, n_sides, endpoint=False)
    return [(radius * np.cos(a), radius * np.sin(a)) for a in angles]

# Grid setup
x = np.linspace(-5, 5, 500)
y = np.linspace(-5, 5, 500)
X, Y = np.meshgrid(x, y)

# Polygon source points
sources = generate_polygon(3)  # Triangle

# Time snapshot
t = 0
eta_total = np.zeros_like(X)

for (x_s, y_s) in sources:
    R = np.sqrt((X - x_s)**2 + (Y - y_s)**2)
    eta_total += A * np.cos(k * R - omega * t)

# Plotting
plt.figure(figsize=(8, 6))
plt.contourf(X, Y, eta_total, levels=100, cmap='coolwarm')
plt.colorbar(label='Wave Displacement')
plt.title('Water Surface Interference Pattern (Equilateral Triangle Sources)')
plt.xlabel('x (m)')
plt.ylabel('y (m)')
plt.axis('equal')
plt.grid(True)
plt.tight_layout()
plt.show()
```

---

## 🧭 Task 4: Interpretation and Applications

### 🔍 Interference Analysis

* **Constructive Interference**: Peaks where wave crests meet
* **Destructive Interference**: Nulls where crest meets trough
* **Fringe Patterns**: Formed based on polygon geometry and wavelength

### 🌐 Applications

* Sound systems (phase control)
* Water wave tanks (research and education)
* Optics (laser interference from multiple slits)
* Antenna arrays

---


