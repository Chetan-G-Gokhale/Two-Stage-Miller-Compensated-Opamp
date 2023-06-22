# The Layout implemented for the Opamp

In Analog circuits, designs are used like differential pairs and current mirrors, where the matching of device characteristics such as the threshold voltage Vt is important. <br>
If device threshold differences of a few millivolts or less can determine the difference performance and yield of a design. Threshold voltage also varies due to the variations in the number of doping atoms or process variation. For that, we need to match the analog devices

## Common Centriod 

Common Centriod matching technique was used for the differntial pairs. It requires absolute symmetricity along both folded X and Y axis 
of the layout.
The Block level implementation of the common centroid method used was as below <br>
<br>
<br>



<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/07c115d7-cdeb-4548-878e-01f6e19f9b79" width="500"/>
<br>
<br>
If $ is the process variation which occurs ,considering it across both the axis tranistor A and B can have a process variation of upto 7$ ,
It is such that both of the transistor undergo same mismatch so that they remain identical. 
<br>
<br>

The differntial pair was surrounded by a P-tap Guard Ring Across it and waas connected to VDD , and was ensured symmetricity was maitained throughout the Common Centriod block. <br>
Dummy transistors were surrounded across the differential pairs on both of the axis, to further protect from process variation.
<br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f20e777b-564a-4347-bf68-e6b5f2771c95" width="500"/>

<br>
<br>

## Interdigitation

Interdigitation matching techniques wre used for implementation of both NMOS and PMOS current mirrors, Interdigitation process ensures to
Overcome come mismtach in single orientation axis 
Interdigitation also reqires symmetricity with respect to centre of its axis.

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/61d40a04-c909-4eb2-ba1a-14f62fcd66f8" width="500"/>

<br>
<br>
If $ is considered as the process variation which occurs as Guass distribution , Then according to the above layout both of the transistor would have a total 
process varation of 14$.
<br.

The PMOS current mirror was surrounded by Ntap guard ring and NMOS current mirror was surrounded by Ptap Guard Ring and was ensured that symmetricity was maintained across it. <br>
Dummy transistors were added at the end of each of side of the current mirrorsto further protect from process variation

#### PMOS current mirror



<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/3cda761e-2644-409d-8ab0-194e7eea9e08" width="1000" height="230">

<br>

#### NMOS current mirror

<br>
<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/ea4212c6-460e-4ca5-85a4-92568616787f" width="1000"/>


# FINAL LAYOUT


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/a9ee0d3f-0f9e-4b75-89e2-3202d1c70488)" width="1000"/>
    
    
# DRC and LVS Check


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/41a6a084-2245-4674-b557-988d92d38590" width="1000"/>
<br>
<br>
<br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f2b3f708-6134-4ed1-9130-3881e30f8b33" width="1000"/>
