---
title: "Generative Design Skateboard Truck"
excerpt: "Lightweight skateboard truck hangar developed using Generative Design."
header:
  image: /assets/img/SLS-Truck-Top.jpg
  teaser: /assets/img/SLS-Truck-Top.jpg
gallery:
  - image_path: assets/img/SLS_Truck-Back.jpg
  - image_path: assets/img/Side-View-Truck.jpg
---

# Introduction
The capabilities of generative design were explored by developing a skateboard truck hangar with an integrated motor mount for a brushless DC motor. The goal was to create a truck hangar that was compatible with an existing skateboard and mechanical parts that were ordered to convert it into an electric skateboard. Generative design was used to minimize the mass of the hangar while ensuring the parts were strong enough to withstand the weight of the rider and resist the torque of the motor.

# Design
## Importance of Proper Load Cases
Applying proper load cases is critical in generative design because the software only solves for the specific forces it’s given. To minimize mass, a generative part removes all of the material that is not being stressed. If a load case is missing, the software will create a geometry that is weak in that direction, which will result in failures when using the part in real life. For this project, “commonsense” loads were used with the help of AI for a 90 kg (~200 lbs) rider and the specific mechanical components used.  

## Determination of Forces
The following “commonsense” forces were included: 

**Vertical Load: The skateboard truck hangar needs to be able to withstand the weight of the rider.**
* A 90 kg rider applies a force of about 900 N on the wheels.  
* To simulate the high-impact stress of landing a jump or hitting a crack, a safety factor of 3g was used, resulting in a force of about 2700 total distributed across two trucks (1350 N applied on each side of the axle).  

**Belt Tension: The belt pulls the motor shaft and wheel axle toward each other, which the motor mount must resist.**
* Determined by the torque of the Flipsky 6374 motor (8 Nm) divided by the radius of the 20T drive pulley.  
* This 500 N force was increased to 550 N for a safety factor.  

**Shear Force: When a turn is carved on a skateboard, friction pushes the wheels sideways.**
* Calculated using the coefficient of friction of rubber on asphalt (0.8) against the rider’s weight (0.8 * 900 N = 720 N) spread between two trucks (360 N) and increased to 400 N for a safety factor.  
* This force is in the lateral direction and applied to both wheels in the same direction to simulate the ground pushing both wheels sideways to turn the board.  

**Motor Weight: The motor mass is hanging off the end of a lever arm, and hitting a bump can multiply that mass and cause the motor mount to snap off.**
* A shock load (20G) was applied to the motor mass (0.85 kg) to ensure the mount doesn’t fracture when hitting bumps. 
* This 170 N force was placed at the center of mass of the motor.  

**Motor Torque: The motor mount arm will twist when high motor torque is applied.**
* A moment was added to the face of the motor mount with magnitude of the maximum motor torque (8 Nm) 

To improve this process beyond estimating loads, strain gauges could be attached to the longboard truck to record load data during actual riding conditions, such as drops, turns, and braking, to ensure generative design simulation inputs are closer to reality. 

## Structural Constraints
The structural constraint was placed between the kingpin bushings. With a fixed constraint on this central connection point, the simulation forces material to grow outward toward the wheels and motor mount. This placement is important because it defines how the hangar is supported and determines where forces are applied. This ensures that the software knows the hangar is held between the two kingpin bushes so that the motor mount hanging mass is properly supported.  

## Comparison: Nylon 12 vs. AlSiMg10
Both Nylon 12 and AlSi10Mg were used as materials in the generative design study. The outcomes for Nylon 12 were significantly bulkier and thicker. Nylon 12 is not as strong or stiff as AlSi10Mg (an aluminum alloy), so the software must generate more support to resist the same forces. While Nylon is excellent for absorbing impact, the resulting shape is too large to reasonably be used as a skateboard truck, as it prevents the top bushing from holding the truck in place. The aluminum outcome is much smaller because its high strength and stiffness allow the software to create thinner structures that resist loads with minimal material. This result is superior for the motor mount interface, which has to overcome belt tension and motor torque.  

<figure style="width: 100%; margin: 5px; text-align: center;">
  <img src="/assets/img/AlSi10Mg-Outcome.png" alt="Aluminum Truck Outcome" style="width: 45%;">
  <img src="/assets/img/Nylon12-Outcome.png" alt="Nylon Truck Outcome" style="width: 45%;">
  <figcaption>AlSi10Mg (left) and Nylon 12 (right) Generative Design Outcomes</figcaption>
</figure>

Aluminum Outcome CAD Model:
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b6028116ff2436c774e4613?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

Nylon Outcome CAD Model:
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811423e1f18f124cd40?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Iterative Process
To determine the fit and initial thought process for the loads, the aluminum outcome was printed using 3D filament printing with PLA. Two models were printed: one with small loads and one with larger loads. The difference can be seen visually in the following images. The thin skateboard truck had smaller loads, which caused the motor mount to break off when a small force was applied. The thicker skateboard truck was stronger, but it has too much material and is missing some obstacle geometries that prevented it from fitting properly.  

<figure style="width: 100%; margin: 5px; text-align: center;">
  <img src="/assets/img/3D-Print-Truck-2.jpg" alt="Thin Truck Outcome" style="width: 45%;">
  <img src="/assets/img/3D-Print-Truck-1.jpg" alt="Thick Truck Outcome" style="width: 45%;">
  <figcaption>3D-printed Generative Design Outcomes with varying loads</figcaption>
</figure>

For the next iteration, these issues were fixed, resulting in a strong skateboard truck that was able to fit on the baseplate and successfully rotate the wheels with the motor. This iteration was printed using powder bed fusion with Nylon 12, even though the aluminum outcome was printed. While this meant it was not a realistic model to ride on, it proved to be a successful prototype that could be successfully manufactured.  

![SLS Truck](/assets/img/SLS-Truck-CLose.jpg)

To improve upon this model further, the motor torque was increased because it was experiencing some twisting at the motor mount when a large force was applied. This newest solution shows more support beams near the motor mount as compared to the previous model. It meets all the requirements for the truck to be successfully used on a skateboard and could be manufactured using aluminum (AlSi10Mg).  

<figure style="width: 100%; margin: 5px; text-align: center;">
  <img src="/assets/img/Aluminum-Motor-Mount-Iteration.png" alt="New Motor Mount" style="width: 45%;">
  <img src="/assets/img/Initial-Motor-Mount.png" alt="Old Motor Mount" style="width: 45%;">
  <figcaption>Final (Left) and Initial (Right) Motor Mount Design</figcaption>
</figure>


# Discussion
## Powder Bed Fusion and Generative Design 
Powder bed fusion and generative design are a unique pairing because they work effectively together to address their limitations. Generative design produces organic geometries with complex internal structures and other patterns that are nearly impossible to manufacture with traditional subtractive methods. Powder bed fusion allows for this complexity because it does not require support structures, which is ideal for producing parts that have minimal mass. This combination has applications in many industries, such as the aerospace and automotive industries, where the pairing is used to lower vehicle mass, which directly correlates to fuel efficiency or battery range.  

In [one instance](https://www.diabatix.com/papers-and-publications/gain-55-in-cooling-with-dfam-of-a-copper-3d-printing-cpu-cooler), CPU coolers were developed to be more efficient by using generative design to perform thermal analysis. It was used to manage temperatures and ensure even heat distribution, which resulted in a CPU cooler that kept the CPU temperature more than 20 degrees Celsius cooler than the traditional design and a drastically smaller temperature variance. The generative cooler was printed using laser powder bed fusion with copper powder due to its complicated geometries. Cooling CPUs is incredibly important because overheating can lead to degradation and system failures. The result shows how useful the combination of generative design and powder bed fusion can be in many industries where performance optimization is critical.  

## Critique of Generative Design
Generative design can be very useful for specific applications where weight and performance are critical. It is useful for removing human bias from the design process because it can find structural solutions that a human engineer would never think of. However, generative design is not useful for every application. Because it creates organic geometries, the manufacturing methods required can be much more expensive. The parts are also only as good as the input loads, so even if just one force is missing, the generated part may have unpredictable failures.  

Generative design is most useful in vehicle design for aerospace and automotive applications where the high cost of manufacturing is justified by the performance gains. In these instances, reducing a small amount of mass on a rocket can save thousands of dollars in fuel.  

{% include gallery caption="Generative Design Skateboard Truck Project Gallery" %}
