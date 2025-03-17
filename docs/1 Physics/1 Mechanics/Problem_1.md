# Problem 1
# Investigating the Range as a Function of the Angle of Projection

### Introduction
Projectile motion is a fundamental concept in physics, describing the motion of an object under the influence of gravity alone, after being projected with an initial velocity. One of the key characteristics of projectile motion is the range, which depends on the angle of projection. This investigation aims to analyze how the range varies as a function of the launch angle.

### Theory
The motion of a projectile launched from ground level can be analyzed using the equations of kinematics. The horizontal and vertical components of motion are given by:

- **Horizontal motion:**
  $$
  x = v_0 \cos(\theta) \cdot t
  $$
- **Vertical motion:**
  $$
  y = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
  $$

where:
- \( x \) and \( y \) are the horizontal and vertical displacements, respectively,
- \( v_0 \) is the initial velocity,
- \( \theta \) is the angle of projection,
- \( g \) is the acceleration due to gravity (9.81 m/s²), and
- \( t \) is the time of flight.

The time of flight \( T \) can be found by setting \( y = 0 \):
  $$
  T = \frac{2 v_0 \sin(\theta)}{g}
  $$

The range \( R \) of the projectile is given by:
  $$
  R = v_0 \cos(\theta) \cdot T
  $$
Substituting \( T \):
  $$
  R = \frac{v_0^2 \sin(2\theta)}{g}
  $$
This equation shows that the range is maximized when \( \sin(2\theta) \) is maximized, which occurs at \( 2\theta = 90^\circ \), or \( \theta = 45^\circ \).

#### **Visual Representation**
![Projectile Motion Diagram](images/projectile_motion.png)

*Figure 1: Diagram showing projectile motion with different angles of projection.*


### Experimental Setup

#### **Objective:**
To investigate how the range of a projectile changes with different launch angles, keeping the initial velocity constant.

#### **Materials:**
- A **projectile launcher** (with adjustable angles)
- A **protractor** (to adjust the launch angle)
- A **measuring tape** (to measure the range)
- A **stopwatch** (to measure the time of flight)
- A **smooth launch surface**
- **A constant weight projectile** (to maintain a fixed initial velocity)

#### **Procedure:**
1. Set the launcher to a fixed initial velocity.
2. Vary the launch angle from 10° to 90° in increments (e.g., 10°, 20°, ..., 90°).
3. For each launch angle, measure and record the range (horizontal distance traveled).
4. Repeat the trials for each angle to ensure consistency and calculate the average range.
5. Plot the range as a function of the launch angle.

#### **Expected Results:**
- The range will be highest at a launch angle of 45° (the optimal angle for maximum range in projectile motion).
- As the angle approaches 90°, the range decreases, following the standard projectile motion pattern.

#### **Graphical Representation:**
![Projectile Motion at Different Angles](https://upload.wikimedia.org/wikipedia/commons/e/e9/Ball-projectile-motion-different-angles.svg)

*Figure 1: Projectile motion at different launch angles (showing the range and path at varying angles).*

### Conclusion
The investigation confirms the theoretical prediction that the range of a projectile follows a sinusoidal dependence on the angle of projection, with a maximum at 45°. This study is essential in applications such as ballistics, sports, and engineering.

### Further Investigation
- Exploring the effects of air resistance.
- Analyzing projectile motion on inclined planes.
- Extending the study to different launch heights.

This documentation provides a comprehensive understanding of how the angle of projection influences the range of a projectile.
