# Problem 1
# Measuring Earth's Gravitational Acceleration with a Pendulum

## Overview

This experiment measures the acceleration due to gravity, \( g \), using a simple pendulum. The pendulum's period of oscillation depends on \( g \), enabling us to calculate it through precise measurements of length and time. We also analyze uncertainties to assess the reliability of our results.

---

## Procedure and Assumptions

- **Materials**:
  - 1-meter string
  - Small weight (e.g., bag of coins)
  - Stopwatch
  - Ruler

- **Setup**:
  - Measure the pendulum length, \( L \), from the pivot point to the center of the weight.
  - Ruler resolution is 1 mm (0.001 m), giving an uncertainty of:
    \[
    \delta L = 0.0005 \, \text{m}
    \]

- **Data Collection**:
  - Displace the pendulum by a small angle (<15°) to ensure simple harmonic motion.
  - Measure the time for 10 oscillations, \( t_{10} \), and repeat 10 times.
  - Stopwatch resolution is 0.01 s, with human reaction time (~0.1 s) contributing to uncertainty.

- **Key Formula**:
  The period \( T \) of a simple pendulum is given by:
  \[
  T = 2\pi \sqrt{\frac{L}{g}}
  \]

---

## Example Data

Since no specific measurements were provided, we use realistic values:
- **Length**: 
  \[
  L = 1.000 \, \text{m}, \quad \delta L = 0.0005 \, \text{m}
  \]
- **Time for 10 oscillations** (in seconds, 10 trials):
  \[
  t_{10} = [20.12, 20.08, 20.15, 20.10, 20.09, 20.11, 20.13, 20.07, 20.14, 20.10]
  \]

---

## Calculations

### 1. Calculate the Period (\( T \))

The period is the time for one oscillation, computed as:
\[
T = \frac{t_{10}}{10}
\]

#### Mean Time for 10 Oscillations

Sum the measurements:
\[
20.12 + 20.08 + 20.15 + 20.10 + 20.09 + 20.11 + 20.13 + 20.07 + 20.14 + 20.10 = 201.09 \, \text{s}
\]

Calculate the mean:
\[
\bar{t}_{10} = \frac{201.09}{10} = 20.109 \, \text{s}
\]

#### Standard Deviation

The standard deviation, \( \sigma_t \), quantifies variability:
\[
\sigma_t = \sqrt{\frac{\sum (t_{10,i} - \bar{t}_{10})^2}{N - 1}}, \quad \text{where} \quad N = 10
\]

Compute deviations from the mean (\( \bar{t}_{10} = 20.109 \)):
\[
\begin{aligned}
(20.12 - 20.109)^2 &= 0.000121, \\
(20.08 - 20.109)^2 &= 0.000841, \\
(20.15 - 20.109)^2 &= 0.001681, \\
(20.10 - 20.109)^2 &= 0.000001, \\
(20.09 - 20.109)^2 &= 0.000361, \\
(20.11 - 20.109)^2 &= 0.000001, \\
(20.13 - 20.109)^2 &= 0.000441, \\
(20.07 - 20.109)^2 &= 0.001521, \\
(20.14 - 20.109)^2 &= 0.000961, \\
(20.10 - 20.109)^2 &= 0.000001
\end{aligned}
\]

Sum of squared deviations:
\[
0.000121 + 0.000841 + 0.001681 + 0.000001 + 0.000361 + 0.000001 + 0.000441 + 0.001521 + 0.000961 + 0.000001 = 0.00591
\]

Calculate:
\[
\sigma_t = \sqrt{\frac{0.00591}{9}} = \sqrt{0.0006567} \approx 0.0256 \, \text{s}
\]

#### Uncertainty in the Mean

The uncertainty in the mean time is:
\[
\delta \bar{t}_{10} = \frac{\sigma_t}{\sqrt{N}}
\]
\[
\delta \bar{t}_{10} = \frac{0.0256}{\sqrt{10}} \approx \frac{0.0256}{3.162} \approx 0.0081 \, \text{s}
\]

#### Mean Period

\[
\bar{T} = \frac{\bar{t}_{10}}{10} = \frac{20.109}{10} = 2.0109 \, \text{s}
\]

#### Uncertainty in Period

\[
\delta T = \frac{\delta \bar{t}_{10}}{10} = \frac{0.0081}{10} = 0.00081 \, \text{s}
\]

---

### 2. Determine \( g \)

Rearrange the period formula to solve for \( g \):
\[
T = 2\pi \sqrt{\frac{L}{g}}
\]
\[
T^2 = \frac{4\pi^2 L}{g}
\]
\[
g = \frac{4\pi^2 L}{T^2}
\]

Given:
- \( L = 1.000 \, \text{m} \)
- \( T = 2.0109 \, \text{s} \)

Calculate:
\[
T^2 = (2.0109)^2 \approx 4.0437 \, \text{s}^2
\]
\[
4\pi^2 \approx 4 \times 9.8696 = 39.4784
\]
\[
g = \frac{39.4784 \times 1.000}{4.0437} \approx 9.763 \, \text{m/s}^2
\]

---

### 3. Propagate Uncertainties

For:
\[
g = \frac{4\pi^2 L}{T^2}
\]

The relative uncertainty in \( g \) is:
\[
\frac{\delta g}{g} = \sqrt{\left( \frac{\delta L}{L} \right)^2 + \left( \frac{2 \delta T}{T} \right)^2}
\]

#### Length Contribution

\[
\frac{\delta L}{L} = \frac{0.0005}{1.000} = 0.0005
\]

#### Period Contribution

\[
\frac{2 \delta T}{T} = \frac{2 \times 0.00081}{2.0109} \approx \frac{0.00162}{2.0109} \approx 0.000805
\]

#### Combine Uncertainties

\[
\left( \frac{\delta L}{L} \right)^2 = (0.0005)^2 = 0.00000025
\]
\[
\left( \frac{2 \delta T}{T} \right)^2 = (0.000805)^2 \approx 0.000000648
\]
\[
\frac{\delta g}{g} = \sqrt{0.00000025 + 0.000000648} = \sqrt{0.000000898} \approx 0.000947
\]

Calculate absolute uncertainty:
\[
\delta g = g \times \frac{\delta g}{g} = 9.763 \times 0.000947 \approx 0.0092 \, \text{m/s}^2
\]

**Final Result**:
\[
g = 9.763 \pm 0.009 \, \text{m/s}^2
\]

---

## Analysis

### 1. Comparison with Standard Value

The standard value at sea level is:
\[
g_{\text{standard}} = 9.80665 \, \text{m/s}^2
\]

Difference:
\[
|9.80665 - 9.763| = 0.04365 \, \text{m/s}^2
\]

The measured \( g \) is 0.44% lower, which is reasonable due to:
- Local variations in \( g \) (e.g., altitude, latitude).
- Systematic errors like air resistance or pivot friction.
- Measurement inaccuracies.

---

### 2. Discussion

- **Measurement Resolution (\( L \))**:
  The ruler’s 1 mm resolution gives:
  \[
  \frac{\delta L}{L} = 0.05\%
  \]
  This is small, but a caliper could improve precision. Using a longer \( L \) would reduce relative uncertainty, but setup constraints limit this.

- **Timing Variability (\( T \))**:
  The standard deviation:
  \[
  \sigma_t = 0.0256 \, \text{s}
  \]
  reflects human reaction time (~0.1 s). Measuring 10 oscillations and 10 trials reduces:
  \[
  \frac{\delta T}{T} \approx 0.04\%
  \]
  Automated timing (e.g., photogate) could reduce variability but isn’t essential.

- **Assumptions and Limitations**:
  - **Small Angles**: \( \theta < 15^\circ \) ensures:
    \[
    T \approx 2\pi \sqrt{\frac{L}{g}}
    \]
    Larger angles increase \( T \), underestimating \( g \).
  - **Ideal Pendulum**: Assumes a point mass and massless string. Real weights shift the effective length slightly.
  - **Environment**: Air resistance and pivot friction are minor but present.
  - **Stopwatch**: Reaction time dominates over the 0.01 s resolution.

---

## Deliverables

### 1. Tabulated Data

| Quantity                       | Value                                           | Uncertainty         |
|--------------------------------|-------------------------------------------------|---------------------|
| \( L \) (m)                    | 1.000                                           | 0.0005              |
| \( t_{10} \) measurements (s)  | 20.12, 20.08, 20.15, 20.10, 20.09, 20.11, 20.13, 20.07, 20.14, 20.10 | -                   |
| \( \bar{t}_{10} \) (s)         | 20.109                                          | 0.0081              |
| \( T \) (s)                    | 2.0109                                          | 0.00081             |
| \( g \) (m/s²)                 | 9.763                                           | 0.009               |

---

### 2. Discussion on Uncertainties

- **Length Measurement**:
  The ruler’s resolution limits \( \delta L \). A caliper could reduce this, but the impact is minor (0.05% relative uncertainty).

- **Timing**:
  Human reaction time causes variability in \( t_{10} \). Measuring multiple oscillations and trials reduces:
  \[
  \delta T \approx 0.00081 \, \text{s}
  \]
  Automation would lower \( \sigma_t \), but the current approach is sufficient.

- **Systematic Errors**:
  Air resistance and pivot friction may slightly lower \( g \). A vacuum or rigid rod could minimize these, but such setups are impractical.

- **Uncertainty Propagation**:
  The \( T^2 \) term in:
  \[
  g = \frac{4\pi^2 L}{T^2}
  \]
  amplifies the period’s uncertainty (by a factor of 2). Thus, precise timing is critical.

The final uncertainty:
\[
\delta g = 0.009 \, \text{m/s}^2 \quad (\sim 0.09\%)
\]
indicates a robust measurement, closely matching the standard value and validating the method.
