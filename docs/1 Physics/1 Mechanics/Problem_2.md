# Problem 2
# Investigating the Dynamics of a Forced Damped Pendulum

## Motivation

The forced damped pendulum is a fascinating physical system exhibiting complex behavior due to the interplay of damping, restoring forces, and external driving forces. By incorporating periodic forcing, the system can display resonance, quasiperiodic motion, and even chaos. These behaviors have practical applications in mechanical engineering, climate systems, and nonlinear oscillators.

## Theoretical Foundation

The motion of a forced damped pendulum is governed by the equation:

\[
\frac{d^2\theta}{dt^2} + b \frac{d\theta}{dt} + \omega_0^2 \sin(\theta) = A \cos(\omega t)
\]

where:
- \( \theta \) is the angular displacement,
- \( b \) is the damping coefficient,
- \( \omega_0 \) is the natural frequency of the pendulum,
- \( A \) is the amplitude of the external force,
- \( \omega \) is the driving frequency.

### Small-Angle Approximation
For small oscillations (\( \theta \approx \sin\theta \)), the equation simplifies to:

\[
\frac{d^2\theta}{dt^2} + b \frac{d\theta}{dt} + \omega_0^2 \theta = A \cos(\omega t)
\]

This equation describes a damped, driven harmonic oscillator.

### Resonance Conditions
Resonance occurs when the external driving frequency matches the system’s natural frequency:

\[
\omega = \omega_0
\]

At resonance, energy transfer is maximized, leading to large amplitude oscillations.

## Analysis of Dynamics

### Effect of Parameters:
1. **Damping Coefficient \( b \)**: High damping suppresses oscillations, while low damping allows sustained motion.
2. **Driving Amplitude \( A \)**: Higher amplitudes can lead to chaotic motion at certain frequencies.
3. **Driving Frequency \( \omega \)**: When near resonance, even small forces can lead to significant oscillations.

### Transition to Chaos:
For certain parameter values, the pendulum enters a chaotic regime, characterized by:
- **Aperiodic motion**
- **Sensitive dependence on initial conditions**
- **Strange attractors in phase space**

This is a hallmark of nonlinear dynamical systems.

## Practical Applications

The forced damped pendulum model applies to various real-world systems:
- **Energy Harvesting**: Oscillators that extract energy from vibrations.
- **Suspension Bridges**: Understanding how periodic forces can induce resonance.
- **Oscillating Circuits**: Electrical analogs of mechanical driven oscillators.

## Implementation

### Computational Model

Below is a Python script to simulate the motion of a forced damped pendulum using numerical integration.

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Define parameters
b = 0.2     # Damping coefficient
A = 1.2     # Driving force amplitude
omega = 2.0 # Driving frequency
omega0 = 1.5 # Natural frequency
g = 9.81    # Gravity
L = 1.0     # Length of pendulum

# Define the system of differential equations
def forced_damped_pendulum(t, y):
    theta, omega_theta = y
    dtheta_dt = omega_theta
    domega_dt = -b * omega_theta - (g / L) * np.sin(theta) + A * np.cos(omega * t)
    return [dtheta_dt, domega_dt]

# Time span
t_span = (0, 50)
t_eval = np.linspace(0, 50, 1000)
y0 = [0.2, 0]  # Initial conditions (small initial angle)

# Solve the system
sol = solve_ivp(forced_damped_pendulum, t_span, y0, t_eval=t_eval)

# Plot results
plt.figure(figsize=(10, 5))
plt.plot(sol.t, sol.y[0], label="θ (Angular Displacement)")
plt.xlabel("Time (s)")
plt.ylabel("Theta (radians)")
plt.title("Forced Damped Pendulum Motion")
plt.legend()
plt.grid()
plt.show()
```