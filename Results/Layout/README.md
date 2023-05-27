# The Layout implemented for the Opamp

In Analog circuits, designs are used like differential pairs and current mirrors, where the matching of device characteristics such as the threshold voltage Vt is important. <br>
If device threshold differences of a few millivolts or less can determine the difference performance and yield of a design. Threshold voltage also varies due to the variations in the number of doping atoms or process variation. For that, we need to match the analog devices

### Common Centriod 

Common Centriod matching technique was used for the differntial pairs. It requires absolute symmetricity along both folded X and Y axis 
of the layout.
The Block level implementation of the common centroid method used was as below <br>
<br>
<br>



<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/51f5f927-f278-44f1-a5a5-9bcbb9a1f258" width="500"/>
<br>
<br>
If $ is the process variation which occurs ,considering it across both the axis tranistor A and B can have a process variation of upto 7$ ,
It is such that both of the transistor undergo same mismatch so that they remain identical. 
<br>
<br>

The differntial pair was surrounded by a P-tap Guard Ring Across it and waas connected to VDD , and was ensured symmetricity was maitained throughout the Common Centriod block. <br>
Dummy transistors were surrounded across the differential pairs on both of the axis, to further protect from process variation.
<br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/20c46a97-658f-49af-b1e2-399d5d9bcabb" width="500"/>

<br>
<br>

### Interdigitation

Interdigitation matching techniques wre used for implementation of both NMOS and PMOS current mirrors, Interdigitation process ensures to
Overcome come mismtach in single orientation axis 
Interdigitation also reqires symmetricity with respect to centree of its axis.

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f7d399a9-0ba3-4049-aba5-898b25cbb003" width="500"/>

<br>
<br>
If $ is considered as the process variation which occurs as Guass distribution , Then according to the above layout both of the transistor would have a total 
process varation of 14$.
<br.

The PMOS current mirror was surrounded by Ntap guard ring and NMOS current mirror was surrounded by Ptap Guard Ring and was ensured that symmetricity was maintained across it. <br>
Dummy transistors were added at the end of each of side of the current mirrorsto further protect from process variation

#### PMOS current mirror



<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/dc779fc2-efa3-450a-8259-5cf867c70fd4" width="1000" height="230">

<br>

#### NMOS current mirror

<br>
<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/29abd362-3c08-4251-8b81-28ed30f1d436)" width="1000"/>




