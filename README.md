# quantum-protocol-for-biological-imaging
In this work (see short summary, “xxx”, in the theory folder) I developed a quantum protocol that uses entangled photon pairs, denoted by “S” and “I”, to counter the inherent trade-off between **resolution** and **photodamage** to the sample.

## 1. Image Generation and Key Variables

The image generated can be most generally described by a formula:

$$F_I[i,j] = \sum_{u} \sum_{v} F_S[u,v] K_{\alpha,n}[i+u, j+v]$$,

where:

* $F_{I_{i,j}}$ represents the image of the **“I” photon** which is what we detect.
* $F_{S_{u,v}}$ represents the **biological sample** illuminated by only by the **“S” photon** where $u$ and $v$ are the coordinates at the sample plane.
* $K_{\alpha,n}$ is the quantum kernel function that describes the **entanglement of the “S” and “I“ photons**.
* $\alpha \geq 1$ is a measure of the **symmetry** in the system such that it is symmetric when $\alpha=1$ and gets less symmetric as $\alpha$ increases.
* $n$ is the **number of entangled photons** generated in the process.
---

## 2. Trade-off Analysis using Fourier Ring Correlation (FRC)

To investigate the trade-off mentioned above, we use a method called **Fourier Ring Correlation ($\text{FRC}$)**.

In $\text{FRC}$ we generate two independent images of the same sample, transform them to Fourier space and then *calculate the **correlation** between the two Fourier images for each ring in the Fourier image*. The ring’s radius represents spatial frequency and so it is inversely related to the image resolution.

### The FRC Formula:

The Fourier Ring Correlation (FRC) is calculated as:

$$FRC(u_r) = \frac{\sum_{u_r} \sum_{i,j \in \{u_r\}} F_1(i,j) \cdot F_2^*(i,j)}{\sqrt{\sum_{u_r} \sum_{i,j \in \{u_r\}} F_1^2(i,j) \cdot \sum_{u_r} \sum_{i,j \in \{u_r\}} F_2^2(i,j)}}$$

where i and j are the indices of the pixels contained in the ${u_r}$ ring and ${F_1,2}$ are the Fourier images.

*The Gif bellow qualitatively demonstrates the relation between the FRC score and the resolution (which is inversely related to the ring size in Fourier space).*

<div align="center">
  <img src="https://github.com/user-attachments/assets/4338989e-6b3c-4806-9cb1-5553f4e86393" alt="תיאור GIF" width="85%" />
</div>

---

## 3. Simulation Results
Simulation results show a pattern composed of **real biological refractive index data**.

* The **blue curve** represents the best classical result.
* The **orange curve** represents the result of the quantum simulation for a realistic asymmetry value of $\alpha=5$.
* The three simulation plots demonstrate that *the FRC value increases with photon dose as also evident by the appearent improved resolution*. Crucially, the *quantum protocol surpasses the classical case in addressing the inherent trade-off between resolution and photodamage*.

<img width="616" height="374" alt="biological simulation results" src="https://github.com/user-attachments/assets/d465b85a-fdf1-4d4c-8749-5787cc693d3c" />
