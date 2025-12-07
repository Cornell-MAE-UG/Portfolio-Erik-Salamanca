---
layout: project
title: Torque Wrench Design Project
description: Design Project
technologies: [CAD, MatLAB, ANSYS]
image: /assets/images/max_stress_high_mesh.png
---
In this project for MAE 3270 Properties of Materials, Kat Volkova and I designed a torque wrench given requirements for use. These requirements were that it must have a factor of safety against yield of 4, against crack growth of 2, and against fatigue stress at 10^6 cycles of 1.5. All of these factors of safety were based on loading of 600 lbf-in. Additionally, a strain gauge would be attached to the side of the wrench and it must measure a voltage change of 1.0 mV/V at the rated torque of 600 lbf-in. Finally the wrench must be made of either aluminum, steel, or titanium. 

## Overall Model Dimensions

<p align="center">
  <img src="../../assets/images/dimensions_2.png" width="400">
  <br>
  <em>This image depicts the overall dimensions of the wrench design. This model was made by Kat.</em>
</p>

## Using MATLAB to do hand calculations

After making the model of the system I developed a MATLAB livescript to do hand calculations to see if certain materials would meet the requirements set by the problem. I have attached the MATLAB file here; it has the correct dimensions and material we selected in it. 

[Download MATLAB livescript here](../../assets/Erik_Salamanca_Material_Selector_For_Torque_Wrench.mlx)

Using this script we picked Aluminum 7075 T6 which has the relevant material properties:
E = 10000000 psi  
nu = 0.325  
Yield Stress = 72300 psi  
KIC = 424200 psi  
Fatigue Stress at 10^6 cycles = 26000 psi

## Using ANSYS to do finite element modeling

Having a material that would work based on our hand calculations we imported our CAD model into ANSYS to do finite element modeling. 

<p align="center">
  <img src="../../assets/images/loading.png" width="400">
  <br>
  <em>How the torque wrench was loaded in ANSYS to do the FEM.</em>
</p>

From this model we could generate the strain contours and find what the strain would be in the strain gauge direction. 
<p align="center">
  <img src="../../assets/images/Normal_strain_contours.png" width="400">
  <br>
  <em>An image of the normal strain contours in ANSYS.</em>
</p>

Using these values we can again verify that our material and design meet the requirement for the strain gauge to have a high enough voltage change to be measurable by the equation:

$$
\frac{V_{out}}{V_{IN}} = \frac{k(\epsilon_1 + \epsilon_2)}{4}
$$

Where k = 2

We also used ANSYS to generate the stress contours and found the maximum stress.
<p align="center">
  <img src="../../assets/images/max_stress.png" width="400">
  <br>
  <em>This is the relevant area of stress contours on the wrench.</em>
</p>

This model showed us that there actually was a stress concentration higher than what we had predicted in the hand calculations. When we first put the mesh on we had the mesh size set to 0.06 around the filleted area. This gave a stress concentration that did not meet the factor of safety requirement, only being 3.54. However, when the mesh size was increased to 0.1 the factor of safety became 4.03 which meets the design requirement. 

<p align="center">
  <img src="../../assets/images/max_stress_high_mesh.png" width="400">
  <br>
  <em>The mesh set at 0.06.</em>
</p>
<p align="center">
  <img src="../../assets/images/max_stress_low_mesh.png" width="400">
  <br>
  <em>The mesh set at 0.1.</em>
</p>

NOTE: The images show maxes in different spots than where we are saying the max is, but those are due to how the modeling system works with the CAD model’s extrusion interactions. 

The reason that the stress is higher in the mesh that is smaller is because the small meshes exacerbate the stress concentration at the fillet. By increasing the mesh by a bit we get a more accurate understanding of how the stress concentration is actually affecting the wrench.

We also wanted to do a visualization of the maximum deflection to make sure at the maximum rated load the wrench was not ridiculously bent. It would also allow us to compare our hand calculations to what ANSYS predicts the max deflection should be. 
<p align="center">
  <img src="../../assets/images/max_deflection.png" width="400">
  <br>
  <em>The maximum deflection of the wrench at the rated torque of 600 lbf-in.</em>
</p>

The max deflection that ANSYS predicts is actually higher than what our hand calculations do. This makes sense as our calculations do not take into account shear energy or other factors while ANSYS does. 

## Strain Gauge Selection

The final thing that I did is pick a strain gauge that would fit on our design and work with our material. I wanted a half bridge strain gauge as that was what the calculations were based on. This narrowed down the search a lot and I ended up going with a half bridge uniaxial strain gauge model number SGT-1LH/350-TY13. I have linked the documentation below.

[Strain gauge documentation file](../assets/SGT_HALF-BRIDGE-UNIAXIAL.pdf)
