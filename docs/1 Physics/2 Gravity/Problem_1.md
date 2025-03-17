# Problem 1
# Orbital Period and Orbital Radius

## Motivation
Kepler's Third Law states that the square of the orbital period (T) of a planet is proportional to the cube of its orbital radius (r). This relationship is fundamental to celestial mechanics and helps determine planetary motions, satellite orbits, and gravitational interactions.

## Derivation of Kepler's Third Law
For a body in a circular orbit around a central mass M:
- The gravitational force provides the necessary centripetal force:
  
  \[ F_g = F_c \]
  
  \[ \frac{GMm}{r^2} = \frac{m v^2}{r} \]
  
  Simplifying:
  
  \[ v^2 = \frac{GM}{r} \]
  
  The orbital period T is given by:
  
  \[ T = \frac{2\pi r}{v} \]
  
  Substituting for v:
  
  \[ T = \frac{2\pi r}{\sqrt{GM/r}} \]
  
  Squaring both sides:
  
  \[ T^2 = \frac{4\pi^2 r^3}{GM} \]
  
  This shows that:
  
  \[ T^2 \propto r^3 \]

## Applications in Astronomy
- Used to determine planetary masses and distances.
- Essential in satellite orbit calculations.
- Applied in exoplanet discovery through transit methods.

## Computational Model
The following Python script simulates a circular orbit and verifies Kepler's Third Law:

```python
import numpy as np
import matplotlib.pyplot as plt

def orbital_period(radius, mass_central):
    G = 6.67430e-11  # Gravitational constant (m^3 kg^-1 s^-2)
    return 2 * np.pi * np.sqrt(radius**3 / (G * mass_central))

# Define parameters
mass_earth = 5.972e24  # kg (Mass of Earth)
radii = np.linspace(7e6, 4.2e7, 100)  # Varying orbital radii (m)
periods = [orbital_period(r, mass_earth) for r in radii]

# Verify Kepler's Third Law
plt.figure(figsize=(8, 6))
plt.plot(radii**3, periods**2, label="$T^2$ vs $r^3$")
plt.xlabel("$r^3$ (m^3)")
plt.ylabel("$T^2$ (s^2)")
plt.title("Verification of Kepler's Third Law")
plt.legend()
plt.grid()
plt.show()
```