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
