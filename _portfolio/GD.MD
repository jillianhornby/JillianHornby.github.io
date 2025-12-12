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
## CAD Model

## Importance of Proper Load Cases
Applying proper load cases is critical in generative design because the software solves only for the specific forces it’s given. A generative part removes all of the material that isn’t being stressed. If a load case is missing, the software will create a geometry that is weak in that direction, which can lead to failures in the real world. For this project, “commonsense” loads were used with the help of AI for a 90 kg (~200 lbs) rider and the specific mechanical components used (Flipsky 6374 motor, 20T pulley). To improve this process beyond estimating loads, strain gauges could be attached to the longboard truck to record load data during actual riding conditions, such as drops, turns, and braking, to ensure generative design simulation inputs are closer to reality.  

## Determination of Forces
The following “commonsense” forces were included:  
1. Vertical load: Calculated based on a 90 kg rider (~ 880 N) with a safety factor of 3G (~ 2640 N total) distributed across two trucks. This simulates the high-impact stress of landing a jump or hitting a crack.  
2. Belt Tension: Determined by the toque of the Flipsky 6374 motor (8 Nm) divided by the radius of the 20T drive pulley.  
3. Turning/Shear Force: Calculated using the coefficient of friction for polyurethan wheels (u ~= 0.8) against the rider’s weight. This lateral force is applied to both wheels in the same direction to simulate the bending moment created during a sharp turn.  
4. Motor Weight: A shock load (20G) was applied to the motor mass (0.85 kg) to ensure the mount does not fracture due to vibration 
5. Motor Torque: A moment was added to the face of the motor mount with the magnitude of the maximum motor torque (8 Nm) to prevent the mount from twisting.  

## Structural Constraints
The structural constraint was placed on the kingpin bushing seats. With a fixed constraint on this central connection point, the simulation forces material to grow outward toward the wheels and motor mount. This placement is important because it ensures the motor’s hanging mass is properly supported.  

## Iterative Process

# Discussion
## Comparison: Nylon 12 vs. AlSi10Mg
Nylon 12: The outcomes for Nylon 12 are significantly bulkier and thicker. Since Nylon has a much lower Young’s Modulus (stiffness) than aluminum, the software must generate larger cross-sections to resist the same bending forces. While Nylon is excellent for absorbing impact without shattering, the resulting shape is likely too flexible for a precision motor mount.  

AlSi10Mg: The aluminum outcome is much thinner, due to its high specific stiffness that allows for thin structures that resist twisting and bending loads with minimal material. This result is superior for the motor mount interface, where rigidity is required to maintain belt tension.  

## Powder Bed Fusion and Generative Design 
Powder Bed Fusion (PBF) and Generative Design (GD) are a unique pairing because they address each other’s primary limitations. GD often produces organic geometries with complex internal hollows, overhangs, and other patterns that are impossible to manufacture with traditional subtractive methods. PBF allows for this complexity at no additional cost because it does not require support structures, which helps the production of topologically optimized parts that minimize mass while maximizing stiffness. In aerospace and automotive industries, this pairing is used to lower vehicle mass, which directly correlates to fuel efficiency or battery range.  

## Critique of Generative Design
