# Effective Thermal Conductivity of Composites

This repository features MATLAB codes developed to compute the effective thermal conductivity of periodic composite materials. The implementations encompass the analytical formulation of the **Locally-Exact Homogenization Theory (LEHT)** and the numerical **Finite-Volume Theory (FVT)**, utilizing both the Mean-Field Theory approach and the energy-based approach.

The models are designed for composites consisting of an isotropic matrix and circular isotropic inclusions, represented through a periodic unit cell. In addition to determining the effective thermal conductivity matrix, the repository provides the visualization of the temperature field and the microscopic temperature profiles along the coordinate directions. Thus, this computational framework constitutes a robust tool for the comparative analysis between analytical and numerical homogenization methods.

---

## 🔬 Implemented Micromechanical Approaches

### 1. Locally-Exact Homogenization Theory (LEHT)
The LEHT is a highly accurate **analytical** approach. The method uses Fourier series expansions to construct the fluctuating local thermal fields as exact solutions to the governing differential equations. The LEHT formulation implemented in this repository is based on the concepts presented in: **DOI:** [https://doi.org/10.1016/j.ijheatmasstransfer.2020.119477].

The main features of this formulation include:
* **Exact Continuity:** Rigorously satisfies the continuity conditions of temperature and normal heat flux at the fiber-matrix interface.
* **Periodicity:** Ensures the exact fulfillment of periodic boundary conditions at the limits of the Representative Unit Cell (RUC).
* **Homogenization:** The effective thermal conductivity matrix is rigorously obtained by integrating the average heat flux across the RUC boundaries.

### 2. Finite-Volume Theory (FVT)
FVT is a numerical approach based on the spatial discretization of the RUC into subvolumes (finite volumes). To calculate the effective thermal conductivity from the obtained local fields, this repository offers **two distinct mathematical formulations**:

* **Based on Mean-Field Theory:** In this formulation, homogenization is performed through the direct application of the volume averaging theorem. The effective conductivity is calculated by relating the volume average of the local heat fluxes to the average of the thermal gradients applied to the RUC.

* **Based on Energy Theory:** This formulation focuses on energy conservation. Homogenization is performed by ensuring the equivalence of the thermal energy dissipation rate (or entropy production rate) between the original heterogeneous RUC and the equivalent homogeneous material (effective medium).

---

## 🚀 How to Use

All scripts were developed in a modular way in MATLAB, requiring no additional toolboxes to run the direct analyses.

### Input Parameters
At the beginning of each main script, the user can define the following geometric and material parameters:
* `L`, `H`: Dimensions of the Representative Unit Cell (RUC).
* `nx`, `ny`: Mesh discretization (for FVT) or number of terms in the expansions (for LEHT).
* `k_m`: Thermal conductivity of the matrix material.
* `k_i`: Thermal conductivity of the inclusion material.
* `frac`: Volume fraction of the inclusion in the composite.

### Execution
Simply open the desired script (e.g., `main_LEHT_isotropic.m` or the corresponding FVT files) in the MATLAB environment and press *Run*. 

### Results (Outputs)
The programs calculate and print directly to the Command Window the **Effective Thermal Conductivity Matrix ($K^*$)** of dimension $2 \times 2$, reflecting the macroscopic properties of the material in the $X$ and $Y$ directions.

---

## 📚 References and Theoretical Basis
The implemented mathematical models are based on advanced literature regarding computational micromechanics and periodic thermal homogenization. If you use these codes in your academic or research work, please consider citing the relevant bibliographic references associated with the development of these methods.
