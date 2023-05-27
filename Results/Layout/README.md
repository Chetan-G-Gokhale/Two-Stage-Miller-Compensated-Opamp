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

The differntial pair was surrounded by a P-tap Guard Ring Across it , and was ensured symmetricity was maitained throughout the Common Centriod block



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

The PMOS current mirror was surrounded by Ntap guard ring and NMOS current mirror was surrounded by Ptap Guard Ring and was ensured that symmetricity was maintained across it.
