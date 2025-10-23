---
title: "Microfluidic Sorting Device"
excerpt: "A microfluidic device that sorts particles using pinched flow fractionation."
header:
  image: /assets/img/Assembly-Image.png
  teaser: /assets/img/Syringe-Full.jpeg
gallery:
  - image_path: assets/img/Syringe-Full.jpeg
  - image_path: assets/img/Syringe-Wiring.jpeg
  - image_path: assets/img/Syringe-Electrical.jpeg
   
---

# Introduction
## Pinched Flow Fractionation
Pinched flow fractionation (PFF) is a simple technique for continuously separating particles by size in microfluidic devices. PFF utilizes a “pinched section” where two fluids merge inside a narrow channel, with one containing particles and one particle-free buffer. By adjusting their flow rates, the particles are pushed against the sidewall of the pinched region. When the flow enters a wider “broad section,” the particles follow different paths according to their size, allowing them to be continuously separated into different outlets. 

## Applications of Pinched Flow Fractionation
PFF has many different applications, but it is of particular interest to the biomedical field because it enables continuous separation of biological particles by size in order to isolate and analyze them.  

In [one study](https://doi.org/10.1039/C5LC01014D), PFF was used to separate cancer cells from white blood cells with an accuracy of over 90%. Circulating tumor cells (CTCs) can be shed from tumors and released into the bloodstream, which can result in metastasis. PFF presents an opportunity to isolate CTCs for cancer monitoring quickly and inexpensively compared to current methods.  

Even outside of the biomedical field, PFF can provide incredibly useful diagnostic information. 

# Design
## Sorting Geometry
The particles leaving the pinched region are described by the following relationship:  
<p style="font-family: Arial, sans-serif; font-size: 16px;">
  Y<sub>0</sub> = (w<sub>p</sub> − D/2) · (w<sub>b</sub> / w<sub>p</sub>)
</p>
where Y<sub>0</sub> is the position of the particle in the broad section, w<sub>p</sub> is the width of the pinched section, and w<sub>b</sub> is the width of the broad section. 

The outlet boundaries were placed along these paths to effectively collect each particle. The developed microfluidic device had to sort two particles whose sizes fell into the following ranges: 
1. 125 – 150 um
2. 425 – 500 um
The design had to fit onto a 50 mm x 75 mm chip, so a broad section width of 42 mm was selected to maximize separation while still leaving room at the edges to create the mold. A pinched width of 750 um was selected to ensure the particles would fit without getting stuck in this section. Plugging these two values into the provided equation resulted in the following particle path position ranges:  
Small particle path: 37.8 - 38.5 mm 
Large particle path: 28.0 - 30.1 mm 

The outlet channels were then centered around the midpoint of these paths with extra room provided to ensure accuracy.  

## Symmetric vs. Asymmetric Approach

## Flow Balancing Problem

## Future Improvments


# Instructions for Creating a Microfluidic Device with Resin Printing
1. Develop CAD model
2. Resin print the device
3. Post-process the print
4. Create PDMS mold
5. Test device and iterate


# Discussion
## Resin Printing vs. Other Manufacturing Techniques

## Parylene Coating

## Modifications for a Wider Range of Particle Sizes

## Lower Limit on Particle Size
