---
title: "Syringe Pump"
excerpt: "A motorized syringe pump prototype for precision and full control."
header:
  image: /assets/img/Assembly-Image.png
  teaser: /assets/img/Syringe-Full.jpeg
gallery:
  - image_path: assets/img/Syringe-Full.jpeg
  - image_path: assets/img/Syringe-Wiring.jpeg
  - image_path: assets/img/Syringe-Electrical.jpeg
   
---

# About
Syringe pumps have many applications, particularly in the medical field. This motorized syringe pump prototype can control multiple syringe pump sizes with custom flow rates for ease of use and a more precise output. The development of this project required designing custom 3D-printed parts, controlling a stepper-motor using an Arduino, making electrical connections, and assembling the final product. 

# Features

* **Custom Flow Rate.** The flow rate can be specified for each user for a custom experience. 
* **Two Syringe Sizes.** Special support pieces were developed in CAD to be able to securely hold two different sizes of syringe pumps for a more versatile product. 
* **LED Notification System.** An LED light outputs different colors depending on whether the syringe pump is on, off, or actively running. 

# How to Operate the Syringe Pump
Place a syringe pump filled with the desired fluid in the 3D-printed holders. The syringe pump is then operated with 3 buttons. The leftmost button is the "ON/OFF" button, which gives power to the system. The rightmost button is the "FORWARD" button, which causes the syringe pump to start moving forward at its specified flow rate. The middle button is the "BACKWARDS" button, which brings the syringe pump back to its original position. The flow rate can be specified in the Arduino code. 

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a4c6a1055b32dea03a?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true" frameborder="0"></iframe>

# Arduino Code
[Arduino Code](https://github.com/jillianhornby/SyringePump/blob/main/Linear_Actuator_Code.ino)

# Off-the-Shelf Parts Required
| Part | Specification | Amount |  
| --- | --- | --- |  
| Coupler | N/A | 1 |  
| Flanged Ball Bearing | F688ZZ | 1 |  
| Lead Screw | TR8x8x250mm | 1 |  
| Linear Rod | 8mmx200mm | 1 |  
| Linear Bearing | LM8UU | 1 |  
| Lock Collar for Lead Screw | N/A | 1 |  
| Lock Collar for Linear Rod | N/A | 3 |  
| Thread Forming Screw | M3x8 | 4 |  
| Bolt | M3x10 | 4 |  
| Tee Nut | M5 | 4 |  
| Bolt | M5x8 | 8 |  
| Mean Well Power Supply | RT-65D | 1 |  
| Motor | NEMA-17 | 1 |  
| Nut | TR8x8-4 | 1 |  
| V-Slot | 20x40x350 | 1 |  


# 3D-Printed Parts Required
| Part | Amount |  
| --- | --- |  
| Motor Mount Plate | 1 |  
| Left End Support | 1 |  
| Right End Support | 1 |  
| Middle Support | 1 |  
| Carriage | 1 |  
| Enclosure Base | 1 |  
| Enclosure Lid | 1 |  

{% include gallery caption="Syringe Pump Project Gallery" %}
