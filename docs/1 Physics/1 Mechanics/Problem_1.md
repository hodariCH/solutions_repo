# Problem 1
# Projectile Motion: Range as a Function of the Angle of Projection

## 1. Introduction

Projectile motion explores the path of an object thrown into the air under the influence of gravity. The range of a projectile—how far it travels horizontally—is influenced by various factors, especially the angle of projection. This report investigates how the range changes with varying projection angles and how other parameters like initial velocity and gravitational acceleration affect the trajectory.

## 2. Theoretical Foundation

Projectile motion follows a parabolic trajectory under constant acceleration due to gravity. The two main equations governing projectile motion are:

- **Horizontal motion (constant velocity):**

  \[
  x(t) = v_0 \cos(\theta) \cdot t
  \]

  Where:
  - \(x(t)\) is the horizontal displacement,
  - \(v_0\) is the initial velocity,
  - \(\theta\) is the launch angle,
  - \(t\) is the time.

- **Vertical motion (accelerated due to gravity):**

  \[
  y(t) = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
  \]

  Where:
  - \(y(t)\) is the vertical displacement,
  - \(g\) is the acceleration due to gravity.

The range \(R\) is the horizontal distance the projectile travels before returning to the ground (i.e., when \(y(t) = 0\)).

### Derivation of Range Formula:

To find the range \(R\), we solve for the time \(t_f\) when the projectile hits the ground. Setting \(y(t_f) = 0\):

\[
v_0 \sin(\theta) \cdot t_f - \frac{1}{2} g t_f^2 = 0
\]
\[
t_f = \frac{2 v_0 \sin(\theta)}{g}
\]

Now, using this time \(t_f\) in the horizontal motion equation:

\[
R = x(t_f) = v_0 \cos(\theta) \cdot t_f = \frac{v_0^2 \sin(2\theta)}{g}
\]

Thus, the range \(R\) as a function of the launch angle \(\theta\) is given by:

\[
R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}
\]

## 3. Analysis of the Range

- The equation \(R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}\) shows that the range is maximized when \(\theta = 45^\circ\), because \(\sin(90^\circ) = 1\).
  
- **Impact of initial velocity:** The range increases quadratically with initial velocity. Doubling the initial velocity doubles the range.
  
- **Impact of gravitational acceleration:** The range decreases with increasing gravitational acceleration. On a planet with stronger gravity, the projectile will travel a shorter distance for the same initial velocity and angle.

### Graph of Range vs. Angle:

We will generate a graph of range \(R(\theta)\) as a function of launch angle \(\theta\) for different initial velocities.

## 4. Practical Applications

This model of projectile motion is a useful approximation in many real-world scenarios, including:

- **Sports:** The trajectory of soccer balls, basketballs, or baseballs can be modeled to optimize shooting or hitting techniques.
  
- **Engineering:** In artillery, this model is used to predict the trajectory of projectiles.
  
- **Space exploration:** Rockets launched from planets or spacecrafts use similar principles to optimize launch angles.

However, this model assumes no air resistance and flat terrain, which is often not the case in real-world situations.

### Limitations:

- **Air Resistance:** The model doesn't account for drag, which significantly affects the range, especially at high speeds.
  
- **Uneven Terrain:** Launching from a height or on inclined surfaces alters the range.
  
- **Wind and Other Factors:** Environmental factors such as wind speed and direction can influence the trajectory and range.

## 5. Implementation: Python Simulation

To calculate and visualize the range as a function of the angle of projection, we can use Python. Below is the Python code to generate the graph.

### **Python Code:**

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # acceleration due to gravity (m/s^2)
v_0 = 20  # initial velocity (m/s)

# Function to calculate range as a function of angle
def range_of_projectile(v_0, theta):
    return (v_0**2 * np.sin(2 * np.radians(theta))) / g

# Angles from 0 to 90 degrees
angles = np.linspace(0, 90, 100)
ranges = range_of_projectile(v_0, angles)

# Plotting the range vs. angle
plt.figure(figsize=(8, 6))
plt.plot(angles, ranges, label=f'v_0 = {v_0} m/s')
plt.title('Range of Projectile vs Launch Angle')
plt.xlabel('Launch Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid(True)
plt.legend()
plt.show()




