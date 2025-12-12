---
title: "Generative Design Skateboard Truck"
excerpt: "Lightweight skateboard truck hangar developed using Generative Design."
header:
  image: /assets/img/SLS-Truck-CLose.jpg
  teaser: /assets/img/SLS-Truck-CLose.jpg
   
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
Both Nylon 12 and AlSi10Mg were used as materials in the generative design study. The outcomes for Nylon 12 were significantly bulkier and thicker. Nylon 12 is not as strong or stiff as AlSi10Mg (an aluminum alloy), so the software must generate more support to resist the same forces. While Nylon is excellent for absorbing impact, the resulting shape is too large to reasonably be used as a skateboard truck. The aluminum outcome is much smaller because its high strength and stiffness allow the software to create thinner structures that resist loads with minimal material. This result is superior for the motor mount interface, which has to overcome belt tension and motor torque.  

<figure style="width: 100%; margin: 5px; text-align: center;">
  <img src="/assets/img/AlSi10Mg-Outcome.png" alt="Aluminum Truck Outcome" style="width: 45%;">
  <img src="/assets/img/Detent-Side.png" alt="Nylon Truck Outcome" style="width: 45%;">
  <figcaption>AlSi10Mg (left) and Nylon 12 (right) Generative Design Outcomes</figcaption>
</figure>

The aluminum outcome was powder printed using Nylon 12 as a prototype to assess the design and fit of the truck. 

## Iterative Process

# Discussion
## Powder Bed Fusion and Generative Design 
Powder Bed Fusion (PBF) and Generative Design (GD) are a unique pairing because they address each other’s primary limitations. GD often produces organic geometries with complex internal hollows, overhangs, and other patterns that are impossible to manufacture with traditional subtractive methods. PBF allows for this complexity at no additional cost because it does not require support structures, which helps the production of topologically optimized parts that minimize mass while maximizing stiffness. In aerospace and automotive industries, this pairing is used to lower vehicle mass, which directly correlates to fuel efficiency or battery range.  

## Critique of Generative Design
