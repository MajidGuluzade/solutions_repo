# Problem 1
# Interference Patterns on a Water Surface

## Motivation
Interference occurs when two or more waves overlap and combine to form new wave patterns. The result can be either constructive interference (where waves amplify each other) or destructive interference (where they cancel each other out). These patterns are particularly visible on a water surface, where ripples or waves emanating from multiple sources interact with each other, forming striking interference patterns.

In this experiment, we analyze the behavior of waves emitted from point sources arranged in a regular polygonal shape on the water's surface. By observing the superposition of these waves, we can gain insight into:
- **Wave Superposition Principle**: How waves combine when they meet.
- **Constructive and Destructive Interference**: How waves either amplify or cancel each other.
- **Wave Behavior**: The relationship between the phase difference, wave number, and displacement.
- **Applications in Physics**: Real-world examples of interference patterns, such as acoustics, optics, and quantum mechanics.

The study of these interference patterns not only enhances our understanding of wave dynamics but also provides a platform to explore important physical phenomena in real-world systems.

## Problem Statement
The goal of this project is to analyze the interference patterns created by waves emitted from point sources located at the vertices of a regular polygon. These patterns are a direct result of the superposition of multiple waves, and by carefully studying them, we can understand how waves interact with each other.

### Steps to Follow

1. **Select a Regular Polygon**: Choose a regular polygon shape (e.g., equilateral triangle, square, regular pentagon) as the configuration for placing the sources.
   - A polygon with more vertices will create more complex interference patterns.
   
2. **Position the Sources**: Place point wave sources at the vertices of the selected polygon. The sources will emit waves that propagate outward in all directions.

3. **Wave Equations**: Write the wave equations for each point source. These equations describe the displacement of the water surface at a given point \( (x, y) \) and time \( t \), due to the wave emitted from each source.

   \[
   U(x, y, t) = \sum_{i=1}^{N} A \cos(k r_i - \omega t + \phi_0)
   \]
   
   where:
   - \( N \) is the number of sources (vertices of the polygon).
   - \( A \) is the amplitude of the wave.
   - \( k \) is the wave number, which relates to the wavelength \( \lambda \) by \( k = \frac{2\pi}{\lambda} \).
   - \( r_i \) is the distance from the \( i \)-th source to the point \( (x, y) \) on the surface.
   - \( \omega \) is the angular frequency, related to the wave's frequency \( f \) by \( \omega = 2\pi f \).
   - \( \phi_0 \) is the initial phase of the wave, which can be adjusted to account for any initial phase difference between the waves.

4. **Superposition of Waves**: The principle of superposition states that when two or more waves meet, their displacements add together. Thus, the resulting wave displacement at any point is the sum of the displacements caused by each individual source.

5. **Analyze Interference Patterns**: The interference patterns can be examined by plotting the resulting displacement \( U(x, y, t) \) as a function of position and time. Points where the displacements reinforce each other will result in constructive interference, while points where they cancel each other out will produce destructive interference.

6. **Visualization**: Use Python with libraries like `numpy` and `matplotlib` to generate and visualize the interference patterns. By varying the number of sources and their configuration, you can explore how the interference patterns evolve.

## Implementation

The following Python script simulates the interference pattern for a regular polygon with a given number of vertices. It uses `numpy` for numerical calculations and `matplotlib` for plotting the patterns.

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

