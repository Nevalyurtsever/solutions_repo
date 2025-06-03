# Problem 1

# 🧲 Problem 5: Simulating the Effects of the Lorentz Force

---

## 🎯 Task 1: Applications of the Lorentz Force

### ⚡ Systems Where the Lorentz Force is Crucial

- **Particle Accelerators**: Control particle trajectories using magnetic and electric fields.
- **Mass Spectrometers**: Separate ions based on charge-to-mass ratio.
- **Magnetic Confinement Fusion**: Confine plasma using magnetic fields.
- **Cathode Ray Tubes**: Use electric and magnetic fields to deflect electron beams.

### 🧭 Role of Fields

- **Electric Fields ($\vec{E}$)**: Accelerate particles linearly.
- **Magnetic Fields ($\vec{B}$)**: Curve particle trajectories due to perpendicular force $\vec{F} = q \vec{v} \times \vec{B}$.

---

## 🧮 Task 2: Simulating Motion under Lorentz Force

### 🔢 Equations of Motion

Using Newton's second law:

$m \frac{d\vec{v}}{dt} = q(\vec{E} + \vec{v} \times \vec{B})$

### 🐍 Python Code: Particle Simulation in Uniform Fields

```python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# Constants
q = 1.6e-19   # charge (C)
m = 9.11e-31  # mass (kg)
B = np.array([0, 0, 1])  # Tesla
E = np.array([0, 0, 0])  # V/m
v0 = np.array([1e6, 0, 0])  # initial velocity (m/s)
r0 = np.array([0, 0, 0])
dt = 1e-11
steps = 5000

v = v0.copy()
r = r0.copy()
trajectory = [r.copy()]

for _ in range(steps):
    F = q * (E + np.cross(v, B))
    a = F / m
    v += a * dt
    r += v * dt
    trajectory.append(r.copy())

trajectory = np.array(trajectory)

fig = plt.figure(figsize=(8, 6))
ax = fig.add_subplot(111, projection='3d')
ax.plot(trajectory[:,0], trajectory[:,1], trajectory[:,2])
ax.set_title("Trajectory of Charged Particle in Magnetic Field")
ax.set_xlabel("x (m)")
ax.set_ylabel("y (m)")
ax.set_zlabel("z (m)")
plt.tight_layout()
plt.show()
```

---

## 🔍 Task 3: Parameter Exploration

### 🔄 Modifiable Parameters

- **Magnetic Field Strength ($\vec{B}$)**
- **Electric Field Strength ($\vec{E}$)**
- **Initial Velocity ($\vec{v}_0$)**
- **Particle Charge ($q$) and Mass ($m$)**

### 🔄 Effects Observed

- **Circular motion** with $\vec{B}$ only.
- **Helical motion** with $\vec{v}_z \neq 0$.
- **Drift motion** when $\vec{E} \perp \vec{B}$.

---

## 📊 Task 4: Visualization of Results

- **2D/3D plots** of trajectories reveal motion types.
- **Larmor Radius**:
  $r_L = \frac{mv_\perp}{qB}$
- **Drift Velocity** (for $\vec{E} \perp \vec{B}$):
  $\vec{v}_d = \frac{\vec{E} \times \vec{B}}{B^2}$

---

## 🧠 Practical Context & Applications

### ⚙️ Real-World Systems

- **Cyclotrons**: Use $\vec{B}$ to spiral particles outward.
- **Mass Spectrometers**: Particle deflection radius reveals mass/charge.
- **Magnetic Traps**: Confine plasma in fusion experiments.

---

## 🚀 Extensions and Improvements

- Include **non-uniform magnetic fields**.
- Add **relativistic corrections** at high speeds.
- Visualize **multi-particle interactions** or **beam dynamics**.

---
