---
title: "Bike Phone Mount"
excerpt: "3D-printed phone holder developed using a top-down modeling approach."
header:
  image: /assets/img/test_setup.jpeg
  teaser: /assets/img/test_setup.jpeg
   
---

# Introduction
I developed a 3D-printed phone holder for bike handlebars that has the capability to rotate and snap into place between horizontal and vertical orientations. The design was developed in Fusion 360 using a top-down modeling approach, and multiple iterations were 3D-printed to determine the best prototype.  

# Top-Down Modeling
Top-down assembly modeling allows multiple components to be designed and assembled in a singular CAD file. It is particularly beneficial when the parameters of one component affect other components, since changes are automatically propagated. I leveraged this technique to develop the phone holder because my design used 4 individual parts that were connected after printing: a clamp to attach to the handlebars, a detent mechanism to rotate the phone, a phone case, and a connector between the case and the detent mechanism. I changed the sizes and tolerances of individual parts throughout different iterations, and using top-down modeling prevented me from needing to do major rework since the changes propagated to each component.  

# Phone Holder Design
I used filament 3D printing since my design required using heat-set inserts to connect the components, which requires using thermoplastics to develop a design. Both filament printing and SLS printing are acceptable methods for this constraint; however, filament printing is cheaper and more accessible.  

The final design was printed using PETG for the clamp, detent mechanism, and connector, and using TPU 95A for the phone case. The clamp, detent mechanism, and connector needed to be made with rigid materials to stay in an upright position but needed to be slightly flexible to not break when attaching the clamp to the handlebars. While PLA is a rigid material that is easy to print, it is very brittle and therefore not chosen for this project. I initially used ABS for the rigid components since it is very tough while still being able to bend. However, I ran into many printing issues since it is very prone to warping which caused problems when connecting different components. I chose PETG for my final design since it is easier to print than ABS while still maintaining good strength and flexibility capabilities. For the phone case, I chose to use a flexible material so that the phone could snap into place without any extra tools, which is why I chose TPU because it is very flexible and durable.  
