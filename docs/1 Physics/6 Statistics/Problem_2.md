# Problem 2
# Markdown Document: Estimating Pi using Monte Carlo Methods

## Motivation

Monte Carlo methods harness randomness to solve problems numerically, offering a blend of simplicity and power. Estimating \( \pi \) through these techniques—whether by scattering points in a circle or dropping needles across lines—marries probability, geometry, and computation in an intuitive way. This exercise not only approximates a mathematical constant but also illuminates how random sampling can tackle complex challenges in fields like physics, finance, and simulations. It’s a hands-on introduction to convergence, efficiency, and the elegance of probabilistic thinking.

## Part 1: Estimating \( \pi \) Using a Circle

### Theoretical Foundation

Imagine a unit circle (radius = 1) inscribed in a 2x2 square (side length = 2), centered at (0,0). The circle’s area is \( \pi r^2 = \pi(1)^2 = \pi \), and the square’s area is \( 2^2 = 4 \). If we randomly scatter points uniformly across the square, the probability a point lands inside the circle is the ratio of areas: \( \frac{\pi}{4} \). By generating \( N \) total points and counting \( N_{in} \) (those inside the circle, where \( x^2 + y^2 \leq 1 \)), we estimate:

\[
\pi \approx 4 \times \frac{N_{in}}{N}
\]

### Simulation and Visualization

We’ll generate random points, check if they’re inside the unit circle, and plot them. We’ll also track the estimate’s convergence.

### Analysis

Accuracy improves with more points, but convergence is slow due to the method’s probabilistic nature (error \( \sim \frac{1}{\sqrt{N}} \)).

## Part 2: Estimating \( \pi \) Using Buffon’s Needle

### Theoretical Foundation

In Buffon’s Needle problem, a needle of length \( L \) is dropped randomly onto a plane with parallel lines spaced \( D \) apart (assume \( L \leq D \)). The probability it crosses a line depends on its position and angle. For a needle dropped with random midpoint \( y \) (uniform over [0, \( D/2 \)]) and angle \( \theta \) (uniform over [0, \( \pi \)]), the crossing condition is \( y \leq \frac{L}{2} \sin(\theta) \). The probability of crossing is \( \frac{2L}{\pi D} \), so:

\[
\pi \approx \frac{2L \times N}{D \times N_{cross}}
\]

where \( N \) is the number of drops, and \( N_{cross} \) is the number of crossings.

### Simulation and Visualization

We’ll simulate needle drops, count crossings, and visualize the setup.

### Analysis

We’ll compare its convergence to the circle method, noting computational differences.
