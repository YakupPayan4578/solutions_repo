# 🌊 Waves

## 📌 Problem 1: Interference Patterns on a Water Surface

### 🎯 Motivation

Interference occurs when waves from different sources overlap. On a water surface, we can clearly observe this when ripples from multiple points meet. The overlapping of waves can:

- **Reinforce each other** (constructive interference)  
- **Cancel each other out** (destructive interference)

Understanding these patterns helps us see how waves interact visually.

---

### 🧪 Task

We describe a circular wave from a point source at coordinates $(x_0, y_0)$ using the following formula:

$$\eta(x,y,t)=\frac{A}{\sqrt{r}}\cdot\cos(kr-\omega t+\phi)$$

Where:

- $\eta(x,y,t)$ = vertical displacement at point $(x,y)$ at time $t$  
- $A$ = amplitude  
- $r=\sqrt{(x-x_0)^2+(y-y_0)^2}$ = distance from the source  
- $k=\frac{2\pi}{\lambda}$ = wave number  
- $\omega=2\pi f$ = angular frequency  
- $\phi$ = initial phase

---

### ❓ Problem Statement

Analyze the **interference patterns** formed by **multiple point wave sources** placed at the **vertices of a regular polygon** on a water surface.

---

### 🔢 Steps to Follow

1. **Select a Regular Polygon**  
   For example: equilateral triangle, square, pentagon, etc.

2. **Position the Sources**  
   Place a wave source at each vertex.

3. **Write Wave Equations**  
   For each source $i$ at position $(x_i, y_i)$:

   $$\eta_i(x,y,t)=\frac{A}{\sqrt{r_i}}\cdot\cos(kr_i-\omega t+\phi)$$

   where:

   $$r_i=\sqrt{(x-x_i)^2+(y-y_i)^2}$$

4. **Apply Superposition**  
   Total displacement is the **sum** of individual waves:

   $$\eta_{\text{sum}}(x,y,t)=\sum_{i=1}^{N} \eta_i(x,y,t)$$

5. **Analyze the Interference Pattern**  
   - **Constructive Interference**: Peaks align → amplification  
   - **Destructive Interference**: Peaks and troughs cancel → zero motion  

6. **Visualize the Pattern**  
   Use Python or another software to generate graphs.

---

### 🔍 Considerations

- All sources have:
  - Same amplitude $A$  
  - Same frequency $f$  
  - Same wavelength $\lambda$  
  - Constant phase difference (coherent waves)

---

### 📦 Deliverables

- ✅ A Markdown document (this one!)  
- ✅ A Python script or notebook simulating the wave interactions  
- ✅ Graphs showing interference patterns (constructive & destructive regions)  
- ✅ A short explanation of how the patterns form
