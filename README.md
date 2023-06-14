# Two-Stage-Miller-Compensated-Opamp
### Design Of OPAMP in 90nm of gain 70db and its layout implementation with DRC and LVS Cleared             

This is my first significant project in cadence, completed in my third year of BE. I advise you to watch "Prof Nagendra Krishnapura" lectures from IITM  on "Analog IC Design" to gain a better grasp of the implementation. I learned about the fundamentals and significance of feedback systems in these lectures and designed a two stage opamp with Miller compensation and a nulling resistor.

For the design formulas of the transistors I referred to textbook by P. Allen and D. Holberg,"CMOS Analog Circuit Design",The Oxford Series in Electrical and Computer Engineering, 3rd ed these are easil available online

I have given the complete detailed Circuit analysis of the opamp in the below folder --->

 ## [CIRCUIT ANALYSIS](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Circuit_Analysis) 
<br>
<br>



Table of contents
=================

<!--ts-->
   * [SPECIFICATIONS](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#design-specification-of-opamp)
   * [RESULTS](#public)
       * [CIRCUIT DIAGRAM](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#circuit-diagram)
       * [GAIN AND PHASE MARGIN](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#gain-and-phase-margin)
       * [SLEW RATE](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#slew-rate)
       * [CMRR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#cmrr-common-mode-rejection-ratio)
       * [APPLICATIONS](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#some-application-using-op-amp)
       * [FINAL SPECS OBTAINED](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#final-specification-obtained)
   * [LAYOUT](#public)
     * [COMMON CENTROID](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#common-centriod)
     * [INTERDIGITATION](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#interdigitation)
     * [FINAL LAYOUT](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#final-layout)
     * [DRC AND LVS CHECK](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp#drc-and-lvs-check)
    <!--te-->
    
    
## DESIGN SPECIFICATION OF OPAMP
Gain= 70db <br>
Slew rate = 10 V/uS <br>
GBW (Gain Bandwidth) = 30M Hz <br>
ICMR(+)= 1.0 V <br>
ICMR(-)= 300 mV <br>
Vdc = 1.2 V <br>
Cl (Load Capacitance) = 1pF <br>

<br> 

    

# Circuit Diagram

 The final circuit of the opamp which includes all the differntial pair and current mirror including dummy transistors which were used during the implementation of layout. <br>
 
  
<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/54b222ec-8b71-490f-b21c-a0050bbb1263">
</p>
<br>

 ### Note: <br> Initially the phase margin obtained for 5pF was not in a satisfactory range. <br>  Therefore I added a resistor in feedback so it can bring back RHP Zero to some extent. <br> I decided the value of resistor by running a simple AC analysis. However,This is not a conventional method of designing a nulling resistor

# Gain and Phase margin 

The Gain obatined was around 68db with a Unity gain Bandwidth of 23M Hz for a load of Cl=1pf with a phase margin of 80 degrees which is pretty identical comparing
for the designed specification: <br>
 **Av=68db**
 <br>
**GBW=23M Hz**
<br>
 **Cl =1pf**
 <br>
 **Phase Margin =78 degree**
 <br>
 
 <p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/15b2efb6-d5e6-4fb8-85fb-7576c91c262a">
</p>
<br>

However considering for the worst case operation whenever there is a greater output load at the opamp. <br>
As the load essentially increases the frequency of operation of the design reduces thereby 
 we need to check if the opamp becomes unstable (ie) if the phase margin becomes less than 45 degree at GBW

So I replaced the Capactive load to 5pf to measure the phase margin and GBW of the opamp 

<p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/c00b35f4-ed17-4850-8fe9-fa28f9fc7c31">
</p>
<br>
With the help of AC analysis we can see that with greater load the gain remains the same however the unity gain bandwidth is decreased From 23M Hz to 18M Hz.
<br>

**Av=68db**
 <br>
**GBW=18M Hz**
<br>
 **Cl =5pf**
 <br>
  **Phase Margin =80 degree**
 <br>
  

 
  # Slew Rate 
  
  Slew rate is one of the major characteristics of opamp , In an ideal opamp the slew rate is infinite however it is not possible for a infinite
  slew rate in pratical cases. <br>
  To find the slew rate first we need to implement a regular voltage follower as shown below  :
  <br>
  <p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/7079777f-fed8-4982-b1b1-391da57d171a">
</p>



 
  <br>
  
  We can find the slew rate of opamp with the help of transient analysis by calculating the rate of change of output with the help of waveforms obtained 
  <br>
  <p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/d52a9160-5d2b-4115-af85-9ce9bbaa3e13">
</p>
 

  
  
  <br>
  
  **Slew rate = dVo/dt**
  
  
  **Slew rate = 999 mV/111 n S  = 9 V/uS**
 
  
   #### Therefore the obtained slew rate of the opamp was found out to be 9 V/uS which is extremely close to that of the our designed specification of 10 V/uS
   
   
   # CMRR (Common Mode Rejection Ratio)
   
   CMRR is ability of the opamp to reject common mode signals , As common mode gain Av(Cm)=0 the CMRR is ideally infinite 
   **CMRR is given by CMRR= Av(DM)/Av(Cm)
      ie (Differrential Mode gain to that of Common mode gain)**
      
  **CMRR(db)= log(Av(DM))-log(Av(CM)) (db)**
  
  <br>
  
  As we know the diifferntial mode gain of opamp was found out to be 68db, we can find the common mode gain by providing the common input to both
  the terminals of the Opamp.
  <br>

  <p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/d87f95e5-cc9e-40b9-b785-20d1489b6044">
</p>
 

<p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/d9351dcd-0bcf-4e9d-88fd-1e8f9a4fe3f5">
</p>


 
  <br>
  From the above diagram is noted that Common mode gain AV(Cm)=-14db 
  <br>
  Therefore
  <br>
  
  **CMRR = 68.4-(-14.3)
  CMRR = 82.7 db**
  
  #### Therefore the Common mode rejection ratio was found out to be 83 db which is pretty good, Ensuring that it rejects common mode signals to good extent
  
 <br>
 


# SOME APPLICATION USING OP AMP

Opamp the name itself indicates it is used to perform operation on signals such as addition,subtraction and more <br>
So let us verify some basic operation with the opamp created  <br>

### VOLTAGE FOLLOWER AND COMPARATOR
These are the most basic operation which could be done using an op amp. Voltage follower is where output follows the input
and comparator produces an output +Vsat or -Vast relative to inputs (Vp-Vn)


<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/7a5e5246-d3b0-4d58-89a9-0f61d8bdc3c2">
</p>
<br>

Circuit shows a voltage follower on the first stage followed by a comparator stage , As +Vast =1.2V and -Vsat =0 the voltage follower is clipped off accordingly

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/4802f107-a770-4380-87e1-28a041c675bd">
</p>
<br>


### NON INVERTING INTEGRATOR

Non Inverting integrator circuit explaination is easily available online, Please refer to those if you dont understand the circuit 



<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/d7fbedab-7797-4c35-a340-e2192163a25b">
</p>
<br>
<br>
Waveform obtained : <br>
<br>

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/494b4f79-e5b2-4cf0-bf3c-071b35c4eb68">
</p>
<br>

## FINAL SPECIFICATION OBTAINED

Gain= 68db <br>
Slew rate = 9 V/uS <br>
GBW (Gain Bandwidth) = 23M Hz <br>
ICMR(+)= 0.8 V <br>
ICMR(-)= 300 mV <br>
Vdc = 1.2 V <br>
Cl (Load Capacitance) = 1pF-5pF <br>

<br>
<br>


# The Layout implementation

In Analog circuits, designs are used like differential pairs and current mirrors, where the matching of device characteristics such as the threshold voltage Vt is important. <br>
If device threshold differences of a few millivolts or less can determine the difference performance and yield of a design. Threshold voltage also varies due to the variations in the number of doping atoms or process variation. For that, we need to match the analog devices

## Common Centriod 

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

## Interdigitation

Interdigitation matching techniques wre used for implementation of both NMOS and PMOS current mirrors, Interdigitation process ensures to
Overcome come mismtach in single orientation axis 
Interdigitation also reqires symmetricity with respect to centre of its axis.

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


# FINAL LAYOUT


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/bc9b6b71-54fa-410d-8b36-153d54d1a07c)" width="1000"/>
    
    
# DRC and LVS Check


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/7394f472-a417-4711-bfcb-ceb9390d44f7)" width="1000"/>
<br>
<br>
<br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/3635a949-701b-47f0-8075-95acd1e2bb6f)" width="1000"/>







