# Problem 2
# 📈 Problem 5: Exploring the Central Limit Theorem through Simulations

---

## 🎯 Task 1: Simulating Sampling Distributions

### 🔢 Population Distributions

We consider the following types of population distributions:

1. **Uniform Distribution**
2. **Exponential Distribution**
3. **Binomial Distribution**

For each case, we generate a large synthetic population.

```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

np.random.seed(0)
n_population = 100000

uniform_pop = np.random.uniform(0, 1, n_population)
exponential_pop = np.random.exponential(1, n_population)
binomial_pop = np.random.binomial(10, 0.5, n_population)
```

---

## 🧪 Task 2: Sampling and Visualization

We take samples of sizes \[5, 10, 30, 50] and compute sample means repeatedly to build a distribution of sample means.

```python
def simulate_sampling(population, sample_sizes, n_trials=1000):
    results = {}
    for size in sample_sizes:
        means = [np.mean(np.random.choice(population, size)) for _ in range(n_trials)]
        results[size] = means
    return results

sample_sizes = [5, 10, 30, 50]

uniform_results = simulate_sampling(uniform_pop, sample_sizes)
exponential_results = simulate_sampling(exponential_pop, sample_sizes)
binomial_results = simulate_sampling(binomial_pop, sample_sizes)
```

### 📊 Visualization

```python
def plot_sampling_distribution(results, dist_name):
    fig, axes = plt.subplots(1, 4, figsize=(20, 4))
    for i, size in enumerate(sample_sizes):
        sns.histplot(results[size], kde=True, ax=axes[i], bins=30)
        axes[i].set_title(f"{dist_name} (n={size})")
    plt.suptitle(f"Sampling Distribution of Sample Mean - {dist_name}")
    plt.tight_layout()
    plt.show()

plot_sampling_distribution(uniform_results, "Uniform")
plot_sampling_distribution(exponential_results, "Exponential")
plot_sampling_distribution(binomial_results, "Binomial")
```

---

## 🔬 Task 3: Parameter Exploration

* As sample size increases, the distribution of sample means approaches a **normal distribution**, regardless of the original shape.
* The spread (variance) of the sample mean distribution **decreases with larger sample sizes**, reflecting $\text{Var}(\bar{X}) = \frac{\sigma^2}{n}$.

---

## 🌍 Task 4: Practical Applications

The CLT is used in numerous fields:

* **Quality Control**: Predicting defect rates from sample batches.
* **Economics & Finance**: Estimating population parameters like average income or stock returns.
* **Social Sciences**: Generalizing results from surveys.

---

## ✅ Deliverables Summary

* ✔️ Python simulation of sampling distributions.
* ✔️ Histograms illustrating convergence to normality.
* ✔️ Theoretical discussion and practical relevance of the CLT.

---

## 🎯 Problem 6: Estimating $\pi$ Using Monte Carlo Methods

---

## 🔵 Part 1: Estimating $\pi$ Using a Circle

### 📐 Theoretical Foundation

To estimate $\pi$, we use the ratio of points that fall inside a unit circle to those inside the enclosing square:

$\pi \approx 4 \cdot \frac{\text{Points in Circle}}{\text{Total Points}}$

### 🧪 Simulation

```python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(0)
n_points = 10000
x = np.random.uniform(-1, 1, n_points)
y = np.random.uniform(-1, 1, n_points)
dist = x**2 + y**2

inside_circle = dist <= 1
pi_estimate = 4 * np.sum(inside_circle) / n_points
print(f"Estimated π: {pi_estimate:.5f}")
```

### 📊 Visualization

```python
plt.figure(figsize=(6,6))
plt.scatter(x[inside_circle], y[inside_circle], s=1, color='blue', label='Inside Circle')
plt.scatter(x[~inside_circle], y[~inside_circle], s=1, color='red', label='Outside Circle')
plt.gca().set_aspect('equal')
plt.title("Monte Carlo π Estimation")
plt.legend()
plt.show()
```

### 📈 Analysis

* Accuracy improves as the number of points increases.
* Convergence is slow: error decreases as $1/\sqrt{N}$.

---

## 🧵 Part 2: Estimating $\pi$ Using Buffon’s Needle

### 📐 Theoretical Foundation

Buffon’s Needle problem uses the formula:

$\pi \approx \frac{2L \cdot N}{d \cdot C}$

Where:

* $L$ = needle length
* $d$ = distance between lines
* $N$ = number of drops
* $C$ = number of times the needle crosses a line

### 🧪 Simulation

```python
np.random.seed(0)
N = 10000
L = 1.0
d = 2.0

y_center = np.random.uniform(0, d/2, N)
theta = np.random.uniform(0, np.pi/2, N)

cross = y_center <= (L/2) * np.sin(theta)
C = np.sum(cross)

pi_est_buffon = (2 * L * N) / (d * C) if C != 0 else float('inf')
print(f"Estimated π (Buffon's Needle): {pi_est_buffon:.5f}")
```

### 📊 Visualization

```python
plt.figure(figsize=(6,6))
for i in range(200):
    y = y_center[i]
    angle = theta[i]
    x_start = np.random.uniform(0, 10)
    x_end = x_start + L * np.cos(angle)
    y_end = y + L * np.sin(angle)
    plt.plot([x_start, x_end], [y, y_end], 'r-' if cross[i] else 'b-')
for i in range(11):
    plt.axhline(i * d / 10, color='black', lw=0.5)
plt.title("Buffon’s Needle Simulation")
plt.show()
```

### 📈 Analysis

* Buffon’s method has more noise and slower convergence.
* Good for illustrating geometric probability.

---

## ✅ Deliverables Summary

* ✔️ Python implementations for both methods.
* ✔️ Visualizations of point and needle distributions.
* ✔️ Convergence analysis and comparison of accuracy.

---

✅ Problem 6 Complete.
