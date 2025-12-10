---
title: "Bike Phone Mount"
excerpt: "3D-printed phone holder developed using a top-down modeling approach."
header:
  image: /assets/img/Phone-Render-Long.png
  teaser: /assets/img/Phone-Render-Long.png
gallery:
  - image_path: assets/img/BikeConnect1.jpg
  - image_path: assets/img/Phone-on-bar.jpg
   
---

# Introduction
I developed a 3D-printed phone holder for bike handlebars that has the capability to rotate and snap into place between horizontal and vertical orientations. The design was developed in Fusion 360 using a top-down modeling approach, and multiple iterations were 3D-printed to determine the best prototype.  

# Top-Down Modeling
Top-down assembly modeling allows multiple components to be designed and assembled in a singular CAD file. It is particularly beneficial when the parameters of one component affect other components in a model, since changes are automatically propagated throughout the design. I leveraged this technique to develop the phone holder because my design had 6 individual parts that had to be 3D-printed and assembled. Because I changed the sizes and tolerances of these parts throughout different iterations, using tow-down modeling prevented me from needing to do major rework.   

# Phone Holder Design
The phone holder design has three major sections: a clamp to attach to the handlebars, a detent mechanism to rotate the phone, and a phone case. The parts were designed to be assembled relatively simply, requiring only heat set inserts, screws, and nuts. 

## CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b60281138d89b4ccd9116e8?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Rotation Mechanism
For the phone rotation, I chose to use a detent mechanism because it uses a spring-loaded ball mechanism that allows motion when a large enough force is applied but will resist movement when the ball moves into the detent. My design uses a compression spring and a ball bearing that are housed inside the holder, and a rotating piece with cut-outs in 4 corners. The design successfully holds the phone in the correct orientations while still allowing motion when physically turning it. This required trying different compression springs and ball bearings until it had the desired feel when turning and locking into place. 

<figure style="width: 100%; margin: 5px; text-align: center;">
  <img src="/assets/img/detent-top-redo.png" alt="Detent Mechanism Top View" style="width: 31%;">
  <img src="/assets/img/Detent-Side.png" alt="Detent Mechanism Side View" style="width: 31%;">
  <img src="/assets/img/DetentPic.jpg" alt="Detent Photo" style="width: 31%;">
  <figcaption>Detent Model: Top View (Fusion Model), Side View (Fusion Model), Physical Model</figcaption>
</figure>

![Detent Rotating](/assets/img/Detent-Rotate.GIF)

## Manufacturing Techniques
I used filament 3D printing since my design used heat-set inserts to connect the components, which requires a thermoplastic design. Both filament printing and SLS printing are acceptable methods for this constraint, but filament printing is cheaper and more accessible.  

The final design was printed using PETG for the clamp and detent mechanisms and using TPU 95A for the phone case. The clamp needed to be made with a rigid material to stay in an upright position, while still being flexible enough to not break when attaching the clamp to the handlebars. While PLA is a rigid material that is easy to print, it is very brittle and could break the clamp when screwing it onto the handlebars. The detent also needed to be made with a rigid material in order to resist motion to lock the phone position in place. I initially used ABS for the rigid components since it is very tough while still being able to bend. However, ABS is very prone to warping which ended up causing problems when connecting components. I chose PETG for my final design since it is easier to print than ABS while still maintaining good strength and flexibility capabilities. For the phone case, I chose to use a flexible material so that the phone could snap into place without any extra tools, which is why I chose TPU because it is very flexible and durable.  

To account for error in the 3D printing process, I added clearance to areas where different parts are connected. I initially added clearance values of 1-2 mm to through-holes and connection areas since I was struggling with warping while using ABS. However, this was too much and once I switched to PETG I was able to use clearance values of 0.1-0.5 mm. For example, the diameter of the bike handle was 22.2 mm, and the 3D-printed clamp had a diameter of 22.4 mm to have a snug fit, whereas the rotation mechanism in the detent had a clearance of 0.5 mm to have more room to rotate.  

## Assembly
To assemble the components after 3D-printing, heat set inserts were melted into the through holes in the detent mechanism base and in the phone connector to screw together the parts. The phone holder was attached to the bike handles by sliding the clamp on and tightening it using M3 screws and nuts. The phone holder can then support my phone and rotate to vertical and horizontal positions.  
<div style="display: flex; justify-content: space-around; width: 100%;">
    <figure style="width: 48%; text-align: center; margin: 0;">
        <img src="/assets/img/BikeConnect2.jpg" alt="Phone Holder Connection" style="width: 100%;">
        <figcaption>Phone Holder Connection</figcaption>
    </figure>
    <figure style="width: 48%; text-align: center; margin: 0;">
        <img src="/assets/img/Heatsets.jpg" alt="Heatset Inserts" style="width: 100%;">
        <figcaption>Heatset Inserts</figcaption>
    </figure>
</div>

<img src="/assets/img/Exploded-View-Bike.png" alt="Exploded View" style="width: 100%;">
<figcaption>Exploded View Assembly</figcaption>



# Individual Components
<div style="display: flex; flex-wrap: wrap; justify-content: space-around;">
    <figure style="width: 31%; margin: 5px; text-align: center;">
        <img src="/assets/img/Clamp-Render.png" alt="Clamp" style="width: 100%;">
        <figcaption>Clamp</figcaption>
    </figure>
    <figure style="width: 31%; margin: 5px; text-align: center;">
        <img src="/assets/img/Detent-Base-Render.png" alt="Dentent Base" style="width: 100%;">
        <figcaption>Detent Base</figcaption>
    </figure>
    <figure style="width: 31%; margin: 5px; text-align: center;">
        <img src="/assets/img/Detent-Rotation-Render.png" alt="Detent Rotation" style="width: 100%;">
        <figcaption>Detent Rotation</figcaption>
    </figure>
    <figure style="width: 31%; margin: 5px; text-align: center;">
        <img src="/assets/img/Detent-Plate-Render.png" alt="Detent Cover" style="width: 100%;">
        <figcaption>Detent Cover Plate</figcaption>
    </figure>
    <figure style="width: 31%; margin: 5px; text-align: center;">
        <img src="/assets/img/Phone-Case-Render.png" alt="Phone Case" style="width: 100%;">
        <figcaption>Phone Case</figcaption>
    </figure>
    <figure style="width: 31%; margin: 5px; text-align: center;">
        <img src="/assets/img/Phone-Connector-Render.png" alt="Phone Connector" style="width: 100%;">
        <figcaption>Phone Case Connector</figcaption>
    </figure>
</div>

{% include gallery caption="Phone Holder Project Gallery" %}
