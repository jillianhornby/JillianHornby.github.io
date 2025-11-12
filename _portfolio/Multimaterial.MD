---
title: "Multimaterial Pliers"
excerpt: "A microfluidic device that sorts particles using pinched flow fractionation."
header:
  image: /assets/img/three-models.jpg
  teaser: /assets/img/three-models.jpg
   
---
# Print-in-Place Models
Print-in-place models are 3D designs composed of multiple moving parts printed as a single assembly. By carefully controlling clearances, these models can be used immediately after being removed from the print bed without any post-processing. However, these prints require very precise tolerances to allow motion or rotation, and they can come out poorly due to irregularities in filament printing. Adding flexible sections can greatly improve the performance of these designs and ensure parts can move as expected.  

Print-in-place models can be used to create functional parts made up of linked segments that move independently from one another, such as hinges or chain links. They are also used to create spring-loaded tools, such as pliers or trigger-based tools which require instantly returning to their initial position after being used. Print-in-place models are very beneficial for prototyping, because makers can test their designs quickly without having to spend time assembling multiple components.  

Due to irregularities when printing rigid materials, a combination of rigid and flexible materials is highly effective when creating print-in-place models. A stiff polymer such as PLA provides strength and dimensional accuracy for structural components, while a flexible elastomer like TPU can be used as a spring or a joint. Combining these materials allows for functional motion without the need for external fasteners or springs.  

# Multimaterial Pliers
This project focuses on designing and fabricating a pair of multimaterial needle nose pliers capable of gripping and picking up through-hole resistors. The design incorporates rigid handles and jaws for durability and precision, along with a flexible joint that enables the spring-like motion. The flexible center allows the pliers to automatically return to an open position when not in use, to follow the behavior of traditional spring-loaded pliers. This approach provides an efficient solution for developing pliers using filament 3D printing technology. 

## CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811792e4859d79881a4?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Design Process
The pliers were developed using CAD software to design an assembly made up of two rigid jaws, two rigid handles, and one flexible center element that behaved like a spring. The rigid components were printed in PLA for strength and precision, while the flexible section was printed in TPU to replicate the behavior of a mechanical spring. The pieces were connected using dovetail joints, which provided a secure press fit that required no tools, post-processing, or adhesives to connect.  
 
The flexible center was modeled as a diamond-shaped structure with an internal grid pattern that deformed under pressure, allowing the jaws to close when the handles are squeezed and returned to an open position when released. Multiple prototypes were printed to test different infill densities, in order to find the right balance between flexibility and strength. The following image shows the difference between a 30% infill (left) and a 20% infill (right). 

![Infill Comparison](/assets/img/center-comparison.jpg)

The rigid jaws and handles were modeled following traditional needle-nose pliers. To minimize material waste, the handle-jaw connection areas were printed first to ensure they had the correct fit before printing the full assembly as seen in the following image.

![Plier Connection](/assets/img/plier-connection.jpg)

The initial jaw design came together at one point at the top, which was successful but had room for improvement. Two additional versions were then created: one with larger surface area at the tips for better gripping of resistors, and another with pointy jaws for better precision in small spaces. All three models can be seen in the following image.  

![Plier Models](/assets/img/three-models.jpg)

The final design had the following specifications:  
* Jaw Length: 55 mm 
* Jaw Capacity: 14.142 mm

## Print Settings
The ideal print settings found for the flexible center were 30% infill and a fill density of 40% for a spring-like mechanism that was rigid enough to stay in place while still being easily deformable. Printing this part required setting the horizontal shells to zero so that only the inner grid pattern remained. The printer speed was also reduced to 40% of its maximum value to improve the accuracy of the thin grid lines in the flexible piece.  

For the rigid handles and jaws, the printer used an infill of 15% since they were only being used to pick up resistors, so optimal mechanical strength was not a priority. These parts were printed at the maximum printer speed since they did not have as many small geometries.  
