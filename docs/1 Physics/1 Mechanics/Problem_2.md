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


---
## **Theoretical Foundation: Forced Damped Pendulum**

### **Equation of Motion**
The equation governing the motion of a forced damped pendulum is given by:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L}\sin\theta = A\cos(\omega t)
$$

where:
- \( \theta \) is the angular displacement,
- \( b \) is the damping coefficient,
- \( g \) is the acceleration due to gravity,
- \( L \) is the length of the pendulum,
- \( A \) is the amplitude of the external force,
- \( \omega \) is the driving frequency.

---

### **📌 Explanation of the Equation**
This equation describes the motion of a **pendulum that experiences friction (damping) and is influenced by an external periodic force**.

---

### **📘 Breakdown of Each Term**
1️⃣ **Acceleration Term:**  
   - $$ \frac{d^2\theta}{dt^2} $$ → Represents the angular acceleration of the pendulum.  

2️⃣ **Damping (Friction) Term:**  
   - $$ b\frac{d\theta}{dt} $$ → Represents energy loss due to friction or air resistance.  
   - **If \( b \) is large** → The motion decays quickly (stops fast).  
   - **If \( b \) is small** → The pendulum continues oscillating for a long time.  

3️⃣ **Gravitational Force Term:**  
   - $$ \frac{g}{L} \sin\theta $$ → Represents the natural oscillation of the pendulum due to gravity.  

4️⃣ **External Force (Driving) Term:**  
   - $$ A\cos(\omega t) $$ → Represents the external periodic force applied to the pendulum (e.g., a motor or external push).  
   - **If \( A \) is large** → The pendulum swings more due to stronger external force.  
   - **If \( \omega \) matches the natural frequency** → **Resonance occurs**, leading to very large oscillations.  

---
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

