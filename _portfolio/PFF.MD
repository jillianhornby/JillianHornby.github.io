---
title: "Microfluidic Sorting Device"
excerpt: "A microfluidic device that sorts particles using pinched flow fractionation."
header:
  image: /assets/img/test_setup_long.jpeg
  teaser: /assets/img/test_setup_long.jpeg
   
---

# Introduction
## Pinched Flow Fractionation
Pinched flow fractionation (PFF) is a simple technique for continuously separating particles by size in microfluidic devices. PFF utilizes a “pinched section” where two fluids merge inside a narrow channel, with one containing particles and one being a particle-free buffer. By adjusting their flow rates, the particles are pushed against the sidewall of the pinched region. When the flow enters a wider “broad section,” the particles follow different paths according to their size, allowing them to be continuously separated into different outlets. 

## Applications of Pinched Flow Fractionation
PFF has a [wide range of applications](https://doi.org/10.1016/j.cep.2024.110087) across biotechnology, environmental monitoring, and industrial diagnostics. PFF is of particular interest in the biomedical field because it enables continuous separation of biological particles by size in order to isolate and analyze them.  

In [one study](https://doi.org/10.1039/C5LC01014D), PFF was used to separate cancer cells from white blood cells with over 90% efficiency. Even though the different cells had overlapping sizes, PFF was so efficient because it took advantage of cell deformability. Because white blood cells deform more, they followed tighter trajectories, whereas the stiffer cancer cells followed wider trajectories. 

Circulating tumor cells (CTCs) shed from tumors into the bloodstream, which can result in metastasis. Analyzing CTCs plays a critical role in cancer monitoring; however, traditional CTC separation techniques, such as immunomagnetic capture and fluorescence-activated cell sorting, often require expensive equipment and biochemical labels to effectively sort particles. In contrast, PFF provides a low-cost alternative that relies solely on size and deformability differences between cell types. 


# Design
## CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b6028112a0db2cd8e243870?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Symmetric vs. Asymmetric Approach
When choosing the geometry for a PFF microfluidic system, the first step is to choose between a symmetric or an asymmetric approach. In symmetric PFF, all branch channels have the same flow resistance and therefore there is uniform flow distribution across the outlets. This technique relies on the natural separation of particles into different streamlines based on their size. Because this separation distance is limited by widths of the pinched and broad sections, very small particles or particles with small size differences are less likely to be separated successfully using symmetric PFF. 

Asymmetric PFF can overcome this limitation by introducing differences in outlet channel resistance, typically by shortening or widening the buffer channel. This creates an unequal distribution of flow, which increases particle separation in the pinched region. As a result, an asymmetric PFF design can achieve more efficient separation and can handle a wider range of particle sizes.  

For this project, I chose a symmetric PFF design because I was working with particles that had a large size difference. A symmetric design simplifies the design and operation of microfluidic devices and ensures any differences in particle distribution are directly related to hydraulic resistance. I used a three-outlet design: one outlet for small particles, one outlet for large particles, and one buffer outlet. Because size constraints limited the outlet channels from having the same length and width, I had to change the geometry of each outlet path to ensure they had the same flow rate for a symmetric PFF design.  

## Sorting Geometry
The particles leaving the pinched point follow paths described by the following [relationship](https://doi.org/10.1021/ac049863r):  

Y<sub>0</sub> = (w<sub>p</sub> − D/2) · (w<sub>b</sub> / w<sub>p</sub>)

Where D is the diameter of the particle, Y<sub>0</sub> is the position of the particle in the broad section, w<sub>p</sub> is the width of the pinched section, and w<sub>b</sub> is the width of the broad section. 

The microfluidic device had to sort two particles whose sizes fell into the following ranges: 

(1) 125 – 150 um

(2) 425 – 500 um

The design had to fit onto a 50 mm x 75 mm chip, so a broad section width of 42 mm was selected to maximize separation while still leaving room at the edges to create the mold. A pinched width of 750 um was selected to ensure the particles would fit without getting stuck in this section. Plugging these two values into the provided equation resulted in the following particle path position ranges:  
* Small particle path: 37.8 - 38.5 mm 
* Large particle path: 28.0 - 30.1 mm 

The outlet channels were then centered around the midpoint of these paths as seen in the diagram below with added tolerance.
![PFF Geometry](/assets/img/geometry.jpeg)

## Flow Balancing Problem
While it is simple to predict the particle paths, the separated streams can be distorted due to unequal outlet resistance. Fluid follows the path of least resistance, which can cause particles to divert to the wrong outlet. Because the buffer channel carries much more liquid than the other particle channels, this problem is inevitable.  

To solve this problem, on-chip resistance was added so that each channel had the correct amount of flow. This was done by varying the outlet lengths and introducing serpentine paths based on the required flow. The required flow percentages were determined by the channel entry widths in the broad section:  
* Small particle channel entry width = 7.7 mm (18.3%) 
* Large particle channel entry width = 10.5 mm (25%) 
* Buffer channel entry width = 23.8 mm (56.7%) 

The resistance is proportional to the path length, and therefore the flow rate is inversely proportional to the path length. The ratio of the path lengths was then determined by finding the inverse of the flow percentages:  

L<sub>small</sub> : L<sub>large</sub> : L<sub>buffer</sub> = 5.4545 : 4.0000 : 1.7647

This ensured that each channel received the proper proportion of total flow to maintain symmetric operation despite having differing geometries. This ratio was then multiplied by 6 to increase resistance throughout the device to try to minimize distortions caused by outlet tubing:

L<sub>small</sub> : L<sub>large</sub> : L<sub>buffer</sub> = 37.72 : 24.00 : 10.59

These paths were then added to each outlet channel, incorporating serpentine geometries to fit the paths onto the chip.  
![Resistance Path Lengths](/assets/img/path_lengths.jpeg)

## Future Improvments
While testing my design, a vortex formed in the center of the broad section that disrupted laminar flow and caused particles to recirculate instead of reaching the outlets. The issue appeared to be related to unequal back pressures in the outlet tubing. Because each outlet had a separate tube that was not fixed, differences in height can create uneven flow resistance between outlets. Additionally, the height difference between tubes likely caused a siphon effect, where gravity acting on one outlet created a vacuum that pulled fluid from the others. These issues caused uneven flow and resulted in some liquid flowing back into the device, both of which likely contributed to the vortex.   

If I could iterate on this design, I would develop a separate part that could hold outlet tubing in place at similar heights. However, because even small differences in tube elevation can cause significant pressure imbalances, I would also apply negative pressure at the outlets to further eliminate siphoning and backflow. This could be done by using syringe pumps attached to linear actuators at each outlet to limit the effect of gravity on the system.  

I also noticed while testing that when I changed the outlet tubing heights, the flow changed due to altered outlet resistances and the particles started to flow toward the outlets. This change in resistance resulted in an asymmetric PFF operation that cleared the vortex. Because of this, I would also be interested in developing an asymmetric system by decreasing the resistance in the buffer channel to break the recirculating flow.     


# Instructions for Creating a Microfluidic Device with Resin Printing
**(1.) Develop CAD model**

The first step in fabricating the microfluidic device is creating a CAD model for the mold, using the geometry required to effectively separate particles using PFF as described throughout this report. To ensure the model can be resin printed, the dimensions must follow printer specifications:  
* The part must fit within the printer’s build volume 
* Feature sizes must be larger than the laser spot size 
* Features must have separation larger than the minimum resolution 

For this project, the device was modeled using Autodesk Fusion 360.  

**(2.) Resin print the mold**

The mold was fabricated using a Formlabs Form 4 resin printer. The layer thickness was selected to match the Z-resolution of the device, and the mold was oriented such that the bottom surface was perfectly flat and parallel to the resin vat.  

![Resin-printed Mold](/assets/img/mold.jpeg)

**(3.) Post-process the print**

After printing, the mold was post-processed to remove uncured resin by following these steps:  
1. Wash the mold in IPA for 5 minutes on the print bed 
2. Remove the mold from the bed and wash it in IPA for another 5 minutes 
3. Allow the mold to dry upside down for 30 minutes 
4. Gently blow any debris out of the mold using compressed air 
5. Cure the mold under UV light for 60 seconds at room temperature 
6. Remove support materials  

**(4.) Coat the mold in parylene**

To prevent PDMS curing inhibition caused by uncured resin, the mold was coated with a thin layer of parylene. This parylene barrier ensures that the mold can be successfully cast with PDMS and provides a non-stick layer that allows the PDMS device to be peeled off without tearing features.  

**(5.) Cast the PDMS device**

A PDMS microfluidic device was created by pouring SYLGARD™ 184 Silicone Elastomer into the resin mold using a 10:1 mix ratio and curing the device under controlled temperature conditions.  

The following are options for cure time and temperature:  
* 24 hours at 23°C, 
* 4 hours at 65°C, 
* 1 hour at 100°C, or 
* 15 minutes at 150°C 

However, because the Formlabs clear resin will crack at temperatures above 100°C, the PDMS was cured overnight at 55°C to ensure a complete cure without any warping.  

After curing, the PDMS was carefully peeled away from the mold to preserve channel features 

![Casted PDMS Microfluidic Device](/assets/img/casted_device.jpeg)

**(6.) Plasma treat the PDMS device and the glass slide**

Because one side of the device will always be left open after being cast, the PDMS device has to be permanently bonded to a glass slide. To create this bond, both surfaces were [treated with oxygen plasma](https://doi.org/10.3390/bios11080292). This process activates the surfaces by forming silanol groups, which bond covalently when brought into contact. 

![Oxygen Plasma Treatment](/assets/img/Plasma-Treating-Image.jpg)

**(7.) Bond the PDMS device to the glass slide**

Immediately after plasma treatment, the PDMS device is carefully aligned and pressed onto the glass slide.  

If the channels are shallow (<0.2 mm), it is important to not press down on them during the bonding process since this could cause the channels to stick to the glass slide.  

The PDMS device was handled with Kimwipes to avoid contamination. 

**(8.) Test the device**

To test the device, polyethylene (PE) beads were suspended in a 3% Tween solution.  

Independent syringe pumps were used to control the flow rate of the particle-containing stream and buffer stream: 
* 3.0 mL/min for the buffer stream 
* 0.6 mL/min for the particle stream 

The device’s performance was evaluated by visually inspecting particle trajectories through the pinched and broad sections. 

![Microfluidic Device Test Setup](/assets/img/test_setup_large.jpeg)


# Discussion
## Resin Printing vs. Other Manufacturing Techniques
For this project, resin printing was chosen over other manufacturing techniques because it provides the best geometric accuracy and surface finish required for microfluidic devices. Resin printing has the micron-scale resolution required to create small PFF features, while other additive manufacturing methods such as filament printing or powder bed fusion do not have the necessary precision to replicate the micron-scale geometries.  

The surface finish of resin printed molds is very smooth compared to these other methods as well. This is very important when demolding because surface roughness can cause PDMS to stick or tear during removal, which can damage critical features. Further, surface irregularities from rough molds can transfer to the PDMS device, creating flow disturbances that could affect laminar flow. While multijet printing can achieve similarly smooth surfaces and high resolution, it is significantly more expensive than resin printing.  

Even compared to soft lithography, which is traditionally used to create microfluidic molds, resin printing is much faster and more accessible. Soft lithography requires photomasks and many processing steps that are time-consuming and expensive.  Resin printing can achieve comparable feature sizes directly from a CAD model without specialized equipment. Overall, resin printing provides the best combination of resolution, surface quality, cost, and accessibility.

## Parylene Coating
When resin molds are printed using vat photopolymerization, there is always residual uncured resin left in the mold, which inhibits PDMS cross-linking and therefore can create inaccurate molds due to loss of features or incomplete curing. Uncured resin is also toxic to cells, and many applications of microfluidic devices require working with biological particles. Typical post-treatment methods to remove uncured resin are not 100% accurate, and many of these methods (i.e. post-curing with heat or UV light) can cause warping, which can impact the dimensions of features that are critical in PFF.  

Instead, resin molds can be [coated with parylene](https://doi.org/10.1039/D1LC00744K), which is an FDA-approved biocompatible polymer. Parylene not only provides a barrier that prevents uncured resin from interfering with PDMS cross-linking but also ensures the molds can be used to develop microfluidic devices for cell analysis.  

## Modifications for a Wider Range of Particle Sizes
To sort more than just 2 particles, the broad section could be split into more outlet channels to allow collection of more particles. However, this approach requires particle sizes to have a large enough difference to ensure particle trajectories do not overlap. Further, the more outlets that get added results in more outlet resistances and tubing to account for that could cause disturbances.  

Eventually, an asymmetric PFF design may become necessary to continue adding more particles since it would increase particle separation, which would allow particles with similar sizes to be sorted and provide the opportunity for more output channels to be used.  

## Lower Limit on Particle Size
The lower limit on particle size that can be separated with PFF is determined by the surface roughness of the printed mold. When creating molds using resin printing, the surface roughness is approximately equal to the printer’s resolution. In the pinched region, small particles are forced toward the sidewall. If particle size is on the same scale or smaller than surface imperfections, their motion may become unpredictable, or they may get stuck.
