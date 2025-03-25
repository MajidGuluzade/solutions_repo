# Problem 1
# Interference Patterns on a Water Surface

## Motivation
Interference occurs when waves from different sources overlap, creating new patterns. On a water surface, this can be easily observed when ripples from different points meet, forming distinctive interference patterns. These patterns help us understand wave behavior, including constructive and destructive interference.

Studying these patterns allows us to explore:
- The relationship between wave phase and multiple wave sources.
- Constructive interference (amplification) and destructive interference (cancellation).
- Real-world applications such as acoustics, optics, and fluid dynamics.
- Understanding wave behavior in multi-source systems such as sound waves, electromagnetic waves, and water waves.

## Problem Statement
Analyze the interference patterns formed on a water surface due to the superposition of waves emitted from point sources placed at the vertices of a chosen regular polygon.

### Steps to Follow
1. **Select a Regular Polygon:** Choose a regular polygon (e.g., equilateral triangle, square, regular pentagon).
2. **Position the Sources:** Place point wave sources at the vertices of the selected polygon.
3. **Wave Equations:** Write the equations describing the waves emitted from each source, considering their respective positions.
4. **Superposition of Waves:** Apply the principle of superposition by summing the wave displacements at each point on the water surface:
   
   \[
   U(x, y, t) = \sum_{i=1}^{N} A \cos(k r_i - \omega t + \phi_0)
   \]
   
   where:
   - \( N \) is the number of sources (vertices of the polygon).
   - \( A \) is the wave amplitude.
   - \( k \) is the wave number.
   - \( r_i \) is the distance from the \( i \)-th source to a given point.
   - \( \omega \) is the angular frequency.
   - \( \phi_0 \) is the initial phase.
   
5. **Analyze Interference Patterns:** Examine the resulting displacement \( U(x, y, t) \) as a function of position and time. Identify regions of constructive and destructive interference.
6. **Visualization:** Use Python and plotting libraries to visualize the interference patterns.

## Implementation
The following Python script simulates and visualizes the interference pattern using `numpy` and `matplotlib`.

```python
import numpy as np
import matplotlib.pyplot as plt

# Parameters
A = 1  # Amplitude
wavelength = 1  # Wavelength
k = 2 * np.pi / wavelength  # Wave number
omega = 2 * np.pi  # Angular frequency
phi_0 = 0  # Initial phase
num_sources = 3  # Number of sources (triangle)
radius = 2  # Radius of the polygon

def wave_displacement(x, y, t, sources):
    displacement = np.zeros_like(x)
    for (x_s, y_s) in sources:
        r = np.sqrt((x - x_s)**2 + (y - y_s)**2)
        displacement += A * np.cos(k * r - omega * t + phi_0)
    return displacement

# Define the polygon vertices
angles = np.linspace(0, 2 * np.pi, num_sources, endpoint=False)
sources = [(radius * np.cos(a), radius * np.sin(a)) for a in angles]

# Create a grid
x = np.linspace(-3, 3, 200)
y = np.linspace(-3, 3, 200)
X, Y = np.meshgrid(x, y)
t = 0  # Snapshot at t=0

# Compute wave interference
Z = wave_displacement(X, Y, t, sources)

# Plot the interference pattern
plt.figure(figsize=(8, 6))
plt.contourf(X, Y, Z, levels=50, cmap='RdBu_r')
plt.colorbar(label='Wave Displacement')
plt.scatter(*zip(*sources), color='black', marker='o', label='Wave Sources')
plt.legend()
plt.xlabel('X')
plt.ylabel('Y')
plt.title(f'Interference Pattern for {num_sources}-sided Polygon')
plt.show()
```

## Additional Visualizations
To enhance understanding, we generate:
- **3D Surface Plot:** Provides a height-map representation of wave displacement.
- **Animated Wave Evolution:** Shows real-time changes in the interference pattern.

### 3D Surface Plot
```python
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure(figsize=(10, 6))
ax = fig.add_subplot(111, projection='3d')
ax.plot_surface(X, Y, Z, cmap='coolwarm')
ax.set_xlabel('X')
ax.set_ylabel('Y')
ax.set_zlabel('Displacement')
ax.set_title('3D Wave Interference Pattern')
plt.show()
```

### Animated Wave Evolution
```python
import matplotlib.animation as animation

fig, ax = plt.subplots(figsize=(8, 6))
contour = ax.contourf(X, Y, wave_displacement(X, Y, 0, sources), levels=50, cmap='RdBu_r')
plt.colorbar(contour)
ax.set_title("Wave Interference Animation")

def update(frame):
    ax.clear()
    contour = ax.contourf(X, Y, wave_displacement(X, Y, frame * 0.1, sources), levels=50, cmap='RdBu_r')
    return contour.collections

ani = animation.FuncAnimation(fig, update, frames=100, interval=50, blit=False)
plt.show()
```

## Analysis
- The contour plot visualizes constructive (bright) and destructive (dark) interference regions.
- The 3D surface plot provides a better spatial understanding of displacement variations.
- The animated plot shows how waves evolve dynamically over time.
- Increasing `num_sources` modifies the pattern based on the polygon shape.
- Regions of maximal constructive interference correspond to points where multiple waves reinforce each other in phase.
- Regions of destructive interference form where waves cancel each other out due to phase differences.

## Considerations
- All sources emit waves with the same amplitude, wavelength, and frequency.
- The waves are coherent, maintaining a constant phase difference.
- The simulation assumes an idealized water surface without external disturbances.
- Real-world factors such as wave damping, reflections, and external disturbances can alter interference patterns.
- This model can be extended to explore three-dimensional wave interference or interactions with boundaries.

## Applications
This study of interference patterns has applications in multiple domains:
- **Acoustics:** Understanding sound wave interference in concert halls and noise cancellation technology.
- **Optics:** Designing anti-reflective coatings and diffraction gratings in lenses and optical instruments.
- **Fluid Dynamics:** Studying wave behaviors in oceans, lakes, and engineered fluid systems.
- **Quantum Mechanics:** Wave-particle duality concepts, such as the double-slit experiment.

## Conclusion
This experiment provides an intuitive way to study wave interference through simulations. The resulting patterns reveal how waves combine, reinforcing or canceling each other out in predictable ways. By adjusting the number and positions of sources, different interference patterns can be observed, helping us understand wave behavior in real-world applications. Further extensions of this study could involve wave reflections, damping effects, and three-dimensional wave interactions.
```
