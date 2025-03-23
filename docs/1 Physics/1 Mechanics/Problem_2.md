## **Theoretical Foundation: Forced Damped Pendulum**

### **Equation of Motion**
The equation governing the motion of a forced damped pendulum is given by:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L}\sin\theta = A\cos(\omega t)
$$

where:
- $\theta$ is the angular displacement,
- $b$ is the damping coefficient,
- $g$ is the acceleration due to gravity,
- $L$ is the length of the pendulum,
- $A$ is the amplitude of the external force,
- $\omega$ is the driving frequency.

### **Small-Angle Approximation**
For small oscillations, we approximate:

$$
\sin\theta \approx \theta
$$

which simplifies the equation to:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \theta = A \cos(\omega t)
$$

This is a linear second-order nonhomogeneous differential equation, which can be solved using standard methods.

### **General Solution**
The general solution consists of two parts:

1. **Homogeneous Solution (Natural Response)**

   $$
   \theta_h (t) = C_1 e^{r_1 t} + C_2 e^{r_2 t}
   $$

   where $r_1$ and $r_2$ are roots of the characteristic equation:

   $$
   r^2 + br + \frac{g}{L} = 0
   $$

   The nature of the roots determines the damping behavior:
   - **Overdamped**: Two real distinct roots.
   - **Critically damped**: Two equal real roots.
   - **Underdamped**: Complex conjugate roots leading to oscillatory motion.

2. **Particular Solution (Forced Response)**

   For the external force $A \cos(\omega t)$, we assume a solution of the form:

   $$
   \theta_p (t) = B \cos(\omega t) + C \sin(\omega t)
   $$

   Substituting into the differential equation and solving for $B$ and $C$, we obtain:

   $$
   B = \frac{A (\frac{g}{L} - \omega^2)}{(\frac{g}{L} - \omega^2)^2 + (b\omega)^2}, \quad C = \frac{A b \omega}{(\frac{g}{L} - \omega^2)^2 + (b\omega)^2}
   $$

   The steady-state solution can then be written as:

   $$
   \theta_p (t) = \Theta_0 \cos(\omega t - \delta)
   $$

   where:

   $$
   \Theta_0 = \frac{A}{\sqrt{(\frac{g}{L} - \omega^2)^2 + (b\omega)^2}}
   $$

   and the phase shift $\delta$ is given by:

   $$
   \tan \delta = \frac{b\omega}{\frac{g}{L} - \omega^2}
   $$

### **Resonance Condition**
Resonance occurs when the driving frequency $\omega$ is close to the natural frequency:

$$
\omega_0 = \sqrt{\frac{g}{L}}
$$

At resonance, the amplitude $\Theta_0$ becomes maximum, leading to significant oscillations. This is critical in engineering applications such as **vibration control** and **mechanical resonance avoidance**.

---

This forms the theoretical foundation. Next, we will analyze how different parameters affect the pendulum's behavior.

----

## **2. Analysis of Dynamics**  

We investigate how damping (\(b\)), driving amplitude (\(A\)), and frequency (\(\omega\)) influence the motion:  

- **Low damping**: The system exhibits sustained oscillations.  
- **High damping**: Motion quickly dies out.  
- **Resonance**: Maximum amplitude is observed at a specific \(\omega\).  
- **Chaotic motion**: At certain parameter ranges, the system transitions into chaotic behavior.  

---

## **3. Practical Applications**  

- **Energy Harvesting**: Used in piezoelectric generators.  
- **Suspension Bridges**: Understanding oscillations helps prevent failures (e.g., Tacoma Narrows Bridge collapse).  
- **RLC Circuits**: Analogous behavior in driven electrical oscillators.  

---

## **4. Implementation: Python Simulation**  

Below is a Python script that numerically solves the differential equation using the Runge-Kutta method and visualizes the motion.  

```python

import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Parameters
g = 9.81  # Gravity (m/s^2)
L = 1.0   # Length of pendulum (m)
b = 0.2   # Damping coefficient
A = 1.2   # Driving amplitude
ω = 1.0   # Driving frequency

# Differential equation
def forced_damped_pendulum(t, y):
    θ, ω = y
    dθ_dt = ω
    dω_dt = - (g / L) * np.sin(θ) - b * ω + A * np.cos(ω * t)
    return [dθ_dt, dω_dt]

# Time span
t_span = (0, 20)
t_eval = np.linspace(0, 20, 1000)

# Initial conditions
y0 = [np.pi / 4, 0]

# Solve ODE
sol = solve_ivp(forced_damped_pendulum, t_span, y0, t_eval=t_eval, method='RK45')

# Plot results
plt.plot(sol.t, sol.y[0])
plt.xlabel("Time (s)")
plt.ylabel("Angular Displacement (rad)")
plt.title("Forced Damped Pendulum Motion")
plt.grid()
plt.show()

```