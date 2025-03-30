# Problem 1

1-1

1. Theoretical Derivation
   The equations of motion for projectile motion can be derived using Newton’s second law. Assuming no air resistance, the motion is governed by the kinematic equations:

Horizontal motion:

𝑥
(
𝑡
)
=
𝑣
0
cos
⁡
(
𝜃
)
𝑡
x(t)=v
0
​
cos(θ)t
(Constant velocity since no acceleration acts horizontally)

Vertical motion:

𝑦
(
𝑡
)
=
𝑣
0
sin
⁡
(
𝜃
)
𝑡
−
1
2
𝑔
𝑡
2
y(t)=v
0
​
sin(θ)t−
2
1
​
gt
2

(Acceleration due to gravity acts downward)

To determine range
𝑅
R, we find the time of flight by setting
𝑦
(
𝑡
)
=
0
y(t)=0:

𝑡
𝑓
=
2
𝑣
0
sin
⁡
(
𝜃
)
𝑔
t
f
​
=
g
2v
0
​
sin(θ)
​

Substituting this into the horizontal displacement equation:

# 𝑅

𝑣
0
cos
⁡
(
𝜃
)
⋅
2
𝑣
0
sin
⁡
(
𝜃
)
𝑔
R=v
0
​
cos(θ)⋅
g
2v
0
​
sin(θ)
​

Using the trigonometric identity
2
sin
⁡
(
𝜃
)
cos
⁡
(
𝜃
)
=
sin
⁡
(
2
𝜃
)
2sin(θ)cos(θ)=sin(2θ), we obtain:

# 𝑅

𝑣
0
2
𝑔
sin
⁡
(
2
𝜃
)
R=
g
v
0
2
​

​
sin(2θ)
![alt text](image-1.png)

---

1-2
. Theoretical Analysis of the Range
Governing Equations
Projectile motion is described by the kinematic equations for motion in two dimensions. Assuming no air resistance:

Horizontal displacement:

𝑥
(
𝑡
)
=
𝑣
0
cos
⁡
(
𝜃
)
𝑡
x(t)=v
0
​
cos(θ)t
Vertical displacement:

𝑦
(
𝑡
)
=
𝑣
0
sin
⁡
(
𝜃
)
𝑡
−
1
2
𝑔
𝑡
2
y(t)=v
0
​
sin(θ)t−
2
1
​
gt
2

where:

𝑣
0
v
0
​
is the initial velocity,

𝜃
θ is the launch angle,

𝑔
g is gravitational acceleration.

Time of Flight
Setting
𝑦
(
𝑡
)
=
0
y(t)=0 to determine the time the projectile spends in the air:

𝑡
𝑓
=
2
𝑣
0
sin
⁡
(
𝜃
)
𝑔
t
f
​
=
g
2v
0
​
sin(θ)
​

Range Equation
Substituting
𝑡
𝑓
t
f
​
into the horizontal displacement equation:

# 𝑅

𝑣
0
cos
⁡
(
𝜃
)
⋅
2
𝑣
0
sin
⁡
(
𝜃
)
𝑔
R=v
0
​
cos(θ)⋅
g
2v
0
​
sin(θ)
​

Using the trigonometric identity
2
sin
⁡
(
𝜃
)
cos
⁡
(
𝜃
)
=
sin
⁡
(
2
𝜃
)
2sin(θ)cos(θ)=sin(2θ), we obtain:

# 𝑅

𝑣
0
2
𝑔
sin
⁡
(
2
𝜃
)
R=
g
v
0
2
​

​
sin(2θ)

![alt text](image-2.png)

Analysis and Observations
The maximum range occurs at 45°, as expected from the range equation.

The range is symmetric about
45
∘
45
∘
, meaning angles like 30° and 60° result in the same range.

Increasing
𝑣
0
v
0
​
increases the range, while increasing
𝑔
g decreases it.

## Limitations: This model assumes no air resistance, which in real-world scenarios would shift the optimal launch angle slightly lower.

1-3
Here are the basic mathematical equations for projectile motion:

1. Motion Equations
   When a projectile is launched with initial velocity
   𝑣
   0
   v
   0
   ​
   at an angle
   𝜃
   θ:

Horizontal Motion:

𝑥
(
𝑡
)
=
𝑣
0
cos
⁡
(
𝜃
)
⋅
𝑡
x(t)=v
0
​
cos(θ)⋅t
Vertical Motion:

𝑦
(
𝑡
)
=
𝑣
0
sin
⁡
(
𝜃
)
⋅
𝑡
−
1
2
𝑔
𝑡
2
y(t)=v
0
​
sin(θ)⋅t−
2
1
​
gt
2

2. Flight Time
   The total time of flight can be found by setting
   𝑦
   =
   0
   y=0 (when the projectile hits the ground):

𝑡
flight
=
2
𝑣
0
sin
⁡
(
𝜃
)
𝑔
t
flight
​
=
g
2v
0
​
sin(θ)
​

3. Maximum Height
   The maximum height occurs when the vertical velocity is zero (
   𝑣
   𝑦
   =
   0
   v
   y
   ​
   =0):

ℎ
max
=
(
𝑣
0
sin
⁡
(
𝜃
)
)
2
2
𝑔
h
max
​
=
2g
(v
0
​
sin(θ))
2

​

4. Range (Maximum Horizontal Distance)
   The horizontal range or distance traveled is given by:

# 𝑅

𝑣
0
2
sin
⁡
(
2
𝜃
)
𝑔
R=
g
v
0
2
​
sin(2θ)
​

![alt text](image-3.png)
---------------------------------------------------------------------------
1-4
Project Summary: Simulation and Analysis of Projectile Motion
Motivation:
Projectile motion is an essential concept in physics that demonstrates the relationship between velocity, launch angle, and distance. While the problem of analyzing range as a function of the launch angle is simple, it highlights rich principles that apply to various real-world phenomena, from sports to rocket trajectories.

Objective:
The goal is to create a computational tool to simulate projectile motion and visualize the range of the projectile as a function of the launch angle, considering different initial conditions such as initial velocity, gravitational acceleration, and launch height.

Implementation Plan:

Mathematical Model:

Horizontal motion:

𝑥
(
𝑡
)
=
𝑣
0
cos
⁡
(
𝜃
)
⋅
𝑡
x(t)=v 
0
​
 cos(θ)⋅t
Vertical motion:

𝑦
(
𝑡
)
=
𝑣
0
sin
⁡
(
𝜃
)
⋅
𝑡
−
1
2
𝑔
𝑡
2
y(t)=v 
0
​
 sin(θ)⋅t− 
2
1
​
 gt 
2
 
Where 
𝑣
0
v 
0
​
  is the initial velocity, 
𝜃
θ is the angle of projection, and 
𝑔
g is gravitational acceleration.

Computational Tool:

Use Python, with NumPy for calculations and Matplotlib for visualizations, to simulate projectile motion under various initial conditions.

Simulation:

Compute the range of the projectile for each launch angle and plot the range against the angle.

Vary parameters like initial velocity, gravity, and height to see their effects on the range.

Visualizations:

Plot range vs. launch angle for different initial velocities.

Show how maximum range changes with varying launch angles for different speeds.

Analysis:

Explore how different parameters (velocity, angle, gravity, and height) influence the trajectory and range.

Identify the optimal launch angle for maximum range.

Limitations:

The idealized model assumes no air resistance, constant gravity, and a flat launch surface.

Discuss the impact of air resistance, wind, and varying launch heights, and propose ways to include these in more realistic models.
![alt text](image-4.png)
![alt text](image-5.png)