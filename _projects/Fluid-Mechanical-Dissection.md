---
layout: project
title: Fluid Mechanical Dissection
description: Analysis Project
technologies: [N/A]
image: /assets/images/FMD_Overall.png
---

For the class MAE 3230 Fluid Dynamics at Cornell University our final assignment was to dissect and analyze a system that uses fluid mechanical devices, then make a video based on what we learned about the system. Our group was given a Keurig coffee maker, which we analyzed as a group. For the video I made a slideshow using the images we took in class. In the video, linked below, I am the third person to speak and I talk about how the heated water moves to the Keurig pod.

[Watch dissection video here](https://www.youtube.com/watch?v=tjRH-V7irec) 

I will also include our analysis on this page aswell.

After we had removed all the plastic from the Keurig we found that the system was basically made of the three systems. The first was a overflow safety system, the second the deliverly system, and the final was the pressurizing system. 

<p align="center">
  <img src="../../assets/images/FMD_Sketch.png" width="400">
  <br>
  <em>Here is a simplified sketch of the system.</em>
</p>

<p align="center">
  <img src="../../assets/images/FMD_Sketch_System_1.png" width="400">
  <br>
  <em>These parts make up the overflow saftey system. The only components here are pipes. </em>
</p>

<p align="center">
  <img src="../../assets/images/FMD_Sketch_System_2.png" width="400">
  <br>
  <em>These parts make up the deliverly system. There are three components: a container which heats and holds the water, a one way valve, and a pipe. </em>
</p>

<p align="center">
  <img src="../../assets/images/FMD_Sketch_System_3.png" width="400">
  <br>
  <em>These parts make up the pressuizing system. There are three components: a pump to pull and push air, a one way valve to direct air, and a pipe. </em>
</p>

### Overflow Safety System

This is the simpliest system as it only consists of a few pipes that direct extra water away from any electronics or other components. This system is only used if the container where water is heated is overfilled. Water will go into any of the three pipes and be guided to a waste container where it can be gotten rid off.

<p align="center">
  <img src="../../assets/images/FMD_Top_Container.jpg" width="400">
  <br>
  <em>Here is the where the water is deposited by the user and heated. It has a fill line and if it is exceed the overflow system will be used. </em>
</p>

<p align="center">
  <img src="../../assets/images/FMD_System_1_Real.png" width="400">
  <br>
  <em>Here are the actual pips on the system and where they go to. The container is missing but it is possibel to see where it might be. </em>
</p>

### Water Delivery System

This part of the Keurig is what moves the water after it is heated to the Keurig pod. It works by first acting as a manometer. The heating container decpicted in the last section is air tight and acts as a pressurizing chamber. This chamber is pressuized by a tube that can be seen in that picture coming in from the top right. 

<p align="center">
  <img src="../../assets/images/FMD_Manometer_Example.png" width="400">
  <br>
  <em>Here is a example of a manometer.</em>
</p>

<p align="center">
  <img src="../../assets/images/FMD_Manometer_Equal.jpeg" width="400">
  <br>
  <em>This is what the system would look like when the top chamber is not begun to pressurize.</em>
</p>

<p align="center">
  <img src="../../assets/images/FMD_Manometer_Separated.jpeg" width="400">
  <br>
  <em>This is what the system would look like after the system had begun to pressurize.</em>
</p>

Manometer work via the hydrostatic equation:
$$
P_{\text{in}} - P_{\text{atm}} = \rho g h
$$

We can estimate the height difference from the top of the fluid surface in the heater to the top of tubing to be 5 cm. Based on this estimate we can say that the pressure difference needed to make the fluid reach the top of tubing is about 195 Pa. This is a very small differecne considering that atmspheric pressure is 101,325 Pa. 

Note: To use the hydrostatic equation we must assume that the fluid is not moving.

Now that the fluid has reached the top of the tubing the system switches form a manometer to a syphon. Since the end point of the spicet is lower than the fluid height all of the liquid will flow out of the heating container.

<p align="center">
  <img src="../../assets/images/FMD_Syphon_Example.png" width="400">
  <br>
  <em>Example image of a syphon.</em>
</p>

<p align="center">
  <img src="../../assets/images/FMD_Syphon.jpeg" width="400">
  <br>
  <em>Sketch of the Kuerig's syphon system.</em>
</p>

Syphons work based on the Bernoulli equation:

$$
P_1 + \frac{1}{2}\rho v_1^2 + \rho g h_1
=
P_2 + \frac{1}{2}\rho v_2^2 + \rho g h_2
$$

For our system we can set \( h_2 \) equal to 0 and we can assume that \( v_1 )\ is zero as the contain level does not move signifacntly. With these assumptions we can rearrange the Bernoulli equation to get:

$$
v_2 = \sqrt{2}\,\sqrt{\frac{P_1 - P_2 + g\,h\,\rho}{\rho}} 
$$

Using our previous calculated value for the pressure difference we can find that the minimum pressure difference needed for the fluid to flow out is -2cm. This means the spikot height can be 2 cm above the fluid line and liquid can still flow out.

Note: to use the Bernoulii equation we must assume that the fluid flow is invisid and imcompressible.

### Pressurizing System

In the last section I mentioned that the heating container was pressurized and this system is what does that pressurizing. The pump that is in this system actually works similar to an engine piston. 

<div style="display: flex; justify-content: center; gap: 10px;">
  <img src="../../assets/images/FMD_Pump_Whole.png" width="250">
  <img src="../../assets/images/FMD_Engine_Example.png" width="250">
</div>

<p style="text-align: center;">
  <em>Here is the pump on the right and depicted on the left is the analogous system of an engine.</em>
</p>

The best way to show this is with a GIF of the opened pump.

<p align="center">
  <img src="../../assets/images/FMD_Pump_Engine.gif" width="400">
</p>

As the piston heads move down they create a low pressure region which pulls air in. When the piston head move up they push the air out. Now the question is how the air is directed to the heating container. This is down by a one way valve.

<p align="center">
  <img src="../../assets/images/FMD_Valve.png" width="400">
  <br>
  <em>Here is the valve that directs the air to move to the heating container. The pipe on the right allows air in but not out. The pipe on the top allows air out but not in. The bottom pipe leads to the pump where air is pulled and pushed. These valves work passively.</em>
</p>

These valve work based on pressure difference on either side. Below is a picture of an example valve that will make visualization of the system easier.

<p align="center">
  <img src="../../assets/images/FMD_Valve_Example.png" width="400">
  <br>
  <em>When pressure is high on the left side of the ball the net force is to the right. This means that no fluid can flow past the bal. If the pressure is high on the right side of the ball then the net force is to the left. This moves the ball out of the way and allows fluid to flow past it. The fluid will want to the pressure to equilibrate so it will go form high to low pressure.</em>
</p>

Using these valve air can come in and go out in a controlled manor that will pressurize the heating container so that it can do it's function. 

This is how a Kuerig coffee maker works and what we learned form our fluid mechanical dissection.