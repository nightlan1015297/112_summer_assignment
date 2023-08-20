# 112_summer_assignment

This repository is the summer assignment of the Quantum Optics Lab at National Central University (Dep. Physics). This repository contains the codes for the numerical solution of the Schrödinger equation using the finite element method. The codes are written in Julia and are based on the finite element method.

## Finite Element Method
For the time independent Schrödinger equation :

$$\hat{H}\ket{\Psi} = E\ket{\Psi}$$
$$\rightarrow \frac{-\hbar^2}{2m}\frac{\partial^2{\psi}}{\partial{x}^2}+V(x)\psi = E\psi$$

Here,
- $\psi$ : wave function,
- $V(x)$ : potential, 
- $E$ : energy, 
- $m$ : mass of the particle, 
- $\hbar$ : reduced Planck constant.

To solve the Schrödinger equation, we need to discretize the equation. 

First, we have :
$$\frac{\partial\psi}{\partial{x}}$$

Applying a finite difference spatial discretization to above partial differencial expression, we have :

$$\frac{\partial\psi}{\partial{x}} = \frac{\psi_{n}-\psi_{n-1}}{\Delta{x}}$$

Then, for the second order partial differencial expression of wave function $\psi$, we have :

$$\frac{\partial^2\psi}{\partial{x}^2} = \frac{\psi_{n+1}-2\psi_{n}+\psi_{n-1}}{\Delta{x}^2}$$

Here, $\Delta{x}$ is the spatial step size.

By the discretization, we can form a matrix to express the momentum operator $\hat{p}$.

For s momentum operator $\hat{p}$, we have :

$$\hat{p} = \frac{\hbar}{i}\frac{\partial}{\partial{x}}$$
    
Then, we have :
$$\rightarrow \hat{p} = \frac{\hbar}{i\Delta{x}}
\begin{bmatrix}
-1 & 1 & 0 &\cdots & 0 \\
0 & -1 & 1 & \ddots & \vdots\\
\vdots & \ddots & -1 & 1  & 0\\
\vdots & \ddots & \ddots & -1 & 1 \\
0 & \cdots &\cdots & 0 & -1\\
\end{bmatrix}
\\
$$

Using descretization technique, we can form a matrix to express the kinetic energy operator $\hat{T}$.

For a kinetic energy operator $\hat{T}$, we have :
$$\hat{T} = \frac{\hat{p}\cdot\hat{p}}{2m} = \frac{-\hbar^2}{2m}\frac{\partial}{\partial{x}}$$

$$\rightarrow \hat{T} = \frac{-\hbar^2}{2m \Delta{x}^2}
\begin{bmatrix}
-2 & 1 & \cdots &\cdots & 0 \\
1 & -2 & 1 & \ddots & \vdots\\
\vdots & 1 & -2 & 1  & \vdots\\
\vdots &\ddots & 1 & -2 & 1 \\
0 & \cdots &\cdots & 1 & -2\\
\end{bmatrix}
\\
$$

Also, the potential operator $\hat{V}$ can be descretization and expressed as a matrix.

For a potential operator $\hat{V}$, we have :
$$\rightarrow \hat{V} = 
\begin{bmatrix}
V(x_1) & \cdots & \cdots &\cdots & 0 \\
\vdots & V(x_2) & \ddots & \ddots & \vdots\\
\vdots & \ddots & V(x_3) & \ddots  & \vdots\\
\vdots &\ddots & \ddots & V(x_4) & \vdots \\
0 & \cdots &\cdots & \cdots & V(x_5)\\
\end{bmatrix}
\\
$$

With these operators we can construct the matrix form of Hermition operator $\hat{H}$.

$$\hat{H} = \hat{V}+\hat{T}$$

After construc the matrix form of Hermition operator $\hat{H}$, we can solve the eigenvalue problem.

$$\hat{H}\ket{\Psi} = E\ket{\Psi}$$

## FEM with Non-uniform mass system (1-D)

For the non-uniform mass system, we have :
$$m\rightarrow{m(x)}$$

We have new form of schrodinger equation :


## Presentation link

- [0801_progress_report](https://nightlan1015297.github.io/112_summer_assignment/slides/0801_pogress_reports_Raw.html)
- [0814_progress_report](https://nightlan1015297.github.io/112_summer_assignment/slides/0814_pogress_reports_Raw.html)
- [0821_progress_report](https://nightlan1015297.github.io/112_summer_assignment/slides/0821_pogress_reports_Raw)

## Simulation results
- 2-D Harmonic oscillator potential
    - [ground state](https://nightlan1015297.github.io/112_summer_assignment/result/2-d_harmonic_oscillator_potential/py-no0state.html)
    - [1st state](https://nightlan1015297.github.io/112_summer_assignment/result/2-d_harmonic_oscillator_potential/py-no1state.html)
    - [2nd state](https://nightlan1015297.github.io/112_summer_assignment/result/2-d_harmonic_oscillator_potential/py-no2state.html)
    - [3rd state](https://nightlan1015297.github.io/112_summer_assignment/result/2-d_harmonic_oscillator_potential/py-no3state.html)
    - [4th state](https://nightlan1015297.github.io/112_summer_assignment/result/2-d_harmonic_oscillator_potential/py-no4state.html)
    - [5th state](https://nightlan1015297.github.io/112_summer_assignment/result/2-d_harmonic_oscillator_potential/py-no5state.html)
- 2-D Harmonic oscillator potential (with analysis solution)
    - [ground state](https://nightlan1015297.github.io/112_summer_assignment/result/2-D_harmonic_oscillator_potential_with_analysis_sol/0th_eigenvec.html)
    - [1st state](https://nightlan1015297.github.io/112_summer_assignment/result/2-D_harmonic_oscillator_potential_with_analysis_sol/1st_eigenvec.html)
    - [2nd state](https://nightlan1015297.github.io/112_summer_assignment/result/2-D_harmonic_oscillator_potential_with_analysis_sol/2nd_eigenvec.html)
    - [3rd state](https://nightlan1015297.github.io/112_summer_assignment/result/2-D_harmonic_oscillator_potential_with_analysis_sol/3rd_eigenvec.html)
    - [4th state](https://nightlan1015297.github.io/112_summer_assignment/result/2-D_harmonic_oscillator_potential_with_analysis_sol/4th_eigenvec.html)
    - [5th state](https://nightlan1015297.github.io/112_summer_assignment/result/2-D_harmonic_oscillator_potential_with_analysis_sol/5th_eigenvec.html)