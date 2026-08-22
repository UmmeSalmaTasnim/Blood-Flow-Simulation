# CFD Simulation of Blood Flow Through a Severely Stenosed Artery

## Project Overview

This project presents selected computational fluid dynamics (CFD) visualizations of pulsatile blood flow through a severely stenosed artery (90%). The simulation was performed using **ANSYS Fluent**.

## Motivation

**Arterial stenosis** is the narrowing of an artery that restricts blood flow and alters the normal hemodynamic behavior of blood. In this study, an **axisymmetric artery** is considered to investigate the hemodynamic changes induced by severe stenosis.

## Purpose

* To understand the characteristics of blood flow in a **healthy, non-stenotic axisymmetric artery**.
* To investigate how blood-flow behavior changes with **different degrees of arterial area reduction (stenosis severity)**.
* To examine the hemodynamic consequences of severe stenosis and understand the role of **bypass procedures in restoring or improving blood flow**.

## Computational Approach

* **CFD solver:** ANSYS Fluent
* **Numerical method:** Finite Volume Method (FVM)
* **Flow:** Pulsatile Blood flow through an arterial stenosis
* **Blood model:** Carreau (Non-Newtonian)
* **Governing Equation:** RANS (Reynolds-Averaged Navier–Stokes)
* **Case presented:** 90% stenosis
* **Post-processing:** Velocity, pressure, velocity vectors, streamlines, wall shear stress, and artery geometry

## Geometry and Mesh

### Artery Geometry

The 3D model of the stenosed artery illustrating the 90% narrowing in the vessel lumen and the complete computational domain. The geometry captures the arterial structure with the stenotic constriction.

![Artery Geometry — 90% Stenosis](images/Artery_Geometry.png)

### Artery Mesh

The computational mesh generated for the finite volume discretization of the stenosed artery domain employs a structured hexahedral approach optimized for accurate hemodynamic analysis.

![Artery Mesh — 90% Stenosis](images/Artery_Mesh.png)

**Meshing Specifications:**

* **Element Type:** Hexahedral elements
* **Meshing Method:** Sweep method along the axial direction of the vessel
* **Inflation Layers:** Maximum 15 layers with growth rate = 1.1 to resolve boundary layer effects and wall shear stress variations

**Mesh Sizing:**
* **Global element size:** 0.15 mm
* **Local refinement:** Sphere of influence radius = 2.5 mm with local element size = 0.05 mm at the stenosis region to accurately capture high velocity gradients and flow separation
* **Coarser mesh spacing** in the straight upstream and downstream sections to reduce computational cost where flow gradients are more uniform

**Mesh Quality Metrics:**
* **Skewness:** < 0.58 (high-quality elements)
* **Orthogonal Quality:** > 0.588 (ensures convergence and stability in simulations)

These quality metrics ensure robust numerical solutions and minimize numerical errors in the CFD analysis.

## Selected Simulation Visualizations

### Velocity Contour

The velocity contour illustrates the spatial distribution of flow velocity within the stenosed artery, showing acceleration through the narrowed region.

![Velocity Contour — 90% Stenosis](images/Velocity%20Contour.png)

### Velocity Vector Field

The velocity vectors provide a visualization of the local flow direction and magnitude throughout the arterial domain.

![Velocity Vector Field — 90% Stenosis](images/Velocity%20Vector.png)

### Pressure Contour

The pressure contour presents the computed pressure field throughout the arterial domain, demonstrating the pressure drop across the stenotic region.

![Pressure Contour — 90% Stenosis](images/Pressure%20Contour.png)

### Wall Shear Stress (WSS) Contour

The wall shear stress distribution illustrates the variation of shear loading along the arterial wall, highlighting regions of elevated stress concentration at and downstream of the stenosis.

![Wall Shear Stress — 90% Stenosis](images/WSS%20Contour.png)

### Streamlines

The streamlines illustrate the overall flow pattern through the stenotic region and downstream of the constriction, revealing flow separation and recirculation zones.

![Streamlines — 90% Stenosis](images/Streamline.png)

## Key Hemodynamic Findings

* **Flow Acceleration:** Significant velocity increase through the stenosed section
* **Pressure Drop:** Substantial pressure reduction across the 90% stenosis
* **Wall Shear Stress:** Elevated WSS in the stenosis region with potential for endothelial dysfunction
* **Recirculation Zones:** Formation of vortices and flow separation downstream of the stenosis
* **Complex Flow Patterns:** Non-Newtonian blood behavior influences local hemodynamic conditions

## Clinical Significance

These CFD visualizations demonstrate the complex hemodynamic environment created by severe arterial stenosis, which is relevant to:
- Clinical diagnosis and risk assessment
- Interventional treatment planning
- Stent and scaffold design optimization
- Thrombotic risk evaluation
- Endothelial dysfunction research

## Grid Independence Test

A grid independence study was performed for the **75% stenosed artery** to assess the sensitivity of the numerical solution to mesh resolution. Three different element sizes—**0.20 mm, 0.15 mm, and 0.10 mm**—were considered, and the resulting velocity profiles were compared.

The results showed only minor variations between the different mesh resolutions, indicating that further mesh refinement had a limited effect on the predicted solution. Based on this assessment, the selected mesh provides a suitable balance between **solution accuracy and computational efficiency**.

The same meshing strategy was subsequently applied to the **90% stenosed artery**, maintaining consistency in mesh quality and numerical treatment across the different stenosis severities.

![Grid Independence Test — 75% Stenosis](images/Grid_independence_Test_75_Stenosis.png)

This grid independence assessment supports the reliability of the numerical results presented for the arterial stenosis simulations.


## Note

This repository presents selected visualizations from an ongoing research project. Detailed quantitative results, comparative analyses, and other research findings are reserved for the associated publications.
