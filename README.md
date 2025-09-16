# Josephson-Junction-Switching-Readou

# Josephson Junction Switching Curves: Thermal vs Quantum Escape

This repo contains a Python script that computes **switching probabilities** of a current-biased Josephson junction (JJ) under a square bias pulse. It compares **macroscopic quantum tunneling (MQT)** to **thermal activation** and plots the resulting **S-curves** \$( P_\mathrm{switch}(I) \$).

> Great for showcasing **plasmon/phase-qubit** intuition: washboard potential, plasma frequency, barrier height, and the quantum–thermal crossover.

---

## What this code does

- Defines realistic JJ device knobs: **critical current** \$(I_c\$) and **capacitance** \$(C\$).
- Computes **plasma frequency** \$(\omega_p(I)\$) and **barrier height** \$(\Delta U(I)\$) of the tilted washboard.
- Uses standard rate formulas to get **escape rates**:
  - **Thermal (Kramers)**: \$(\Gamma_\mathrm{th}\approx \frac{\omega_p}{2\pi}\,e^{-\Delta U/k_BT}\$)
  - **MQT (underdamped cubic WKB)**:  
    \$(\displaystyle \Gamma_\mathrm{MQT}\approx \frac{\omega_p}{2\pi}\sqrt{\frac{864\,\Delta U}{\hbar\omega_p}}\,
    \exp\ \left[-\frac{36\,\Delta U}{5\hbar\omega_p}\right]\$)
- Converts rates to **switching probability** for a square pulse of length \$(t_p\$):  
  \$(\displaystyle P_\mathrm{switch}(I)=1-e^{-\Gamma(I)\,t_p}\$)
- Plots \$(P_\mathrm{switch}\$) for **MQT (T≈0)** and **thermal** at user-set temperatures (e.g., 20 mK, 200 mK).
- Prints a **crossover temperature estimate** \$( T^\star \approx \hbar\omega_p/(2\pi k_B) \$) at mid-bias
