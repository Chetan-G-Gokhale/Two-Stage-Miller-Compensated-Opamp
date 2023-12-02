# Two-Stage-Miller-Compensated-Opamp
### Design Of OPAMP in 90nm of gain 70db and its layout implementation with DRC and LVS Cleared             

This is my first significant project in cadence, completed in my third year of BE. I advise you to watch "Prof Nagendra Krishnapura" lectures from IITM  on "Analog IC Design" to gain a better grasp of the implementation. I learned about the fundamentals and significance of feedback systems in these lectures and designed a two stage opamp with Miller compensation and a nulling resistor.

For the design formulas of the transistors I referred to textbook by P. Allen and D. Holberg,"CMOS Analog Circuit Design",The Oxford Series in Electrical and Computer Engineering, 3rd ed these are easily available online

## I have given the complete detailed Circuit analysis of the opamp in this folder --->  [CIRCUIT ANALYSIS](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Circuit_Analysis#table-of-contents) 


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
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f34772fe-43dc-4bb0-992b-8d23ba6d6120">
</p>
<br>

 #### Note: <br>Initially the phase margin obtained for 5pF was not in a satisfactory range. <br>  Therefore I added a resistor in feedback so it can bring back RHP Zero to some extent. <br> I decided the value of resistor by running a simple AC analysis. However,This is not a conventional method of designing a nulling resistor

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
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/159354a3-4973-4b09-be77-d2537d74a2e3">
</p>
<br>

However considering for the worst case operation whenever there is a greater output load at the opamp. <br>
As the load essentially increases the frequency of operation of the design reduces thereby 
 we need to check if the opamp becomes unstable (ie) if the phase margin becomes less than 45 degree at GBW

So I replaced the Capactive load to 5pf to measure the phase margin and GBW of the opamp 

<p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/cc7e2996-990b-44ce-8ee2-dd0a5a62b60d">
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
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/46fcf50b-0cf0-461f-b7cc-07f943a44106">
</p>



 
  <br>
  
  We can find the slew rate of opamp with the help of transient analysis by calculating the rate of change of output with the help of waveforms obtained 
  <br>
  <p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/796193a4-8b01-454e-b43a-9be9d051ec22">
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
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/05d36b0a-feed-49ba-bb51-7af47124ef35">
</p>

 <br>
 <br>

<p align="center">
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/93e637c2-47c4-4339-9d92-d6c6a44feca0">
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
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f1384cb7-86fe-4296-96da-35f9bf38a259">
</p>
<br>

Circuit shows a voltage follower on the first stage followed by a comparator stage , As +Vast =1.2V and -Vsat =0 the voltage follower is clipped off accordingly

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/51738d00-3162-4c97-8c04-91cdbe569295">
</p>
<br>

### R2R DAC CIRCUIT

Implementation and veification of 4bit R2R DAC was done using th e designed opamp and was tested for it working with the help of waveforms by running a transient analysis 

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/3b31d03b-c5a8-4512-8d1e-347cd9e5133f)">
</p>
<br>
<br>
Waveform obtained : <br>
<br>

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/7bd29708-ffda-44fe-af66-d098c1e8747f)">
</p>
<br>

### NON INVERTING INTEGRATOR

Non Inverting integrator circuit explaination is easily available online, Please refer to those if you dont understand the circuit 



<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/e13f639b-4b41-41a2-899b-3ad20bc494d1">
</p>
<br>
<br>
Waveform obtained : <br>
<br>

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/015689b9-3652-4649-9910-629d87a4c416">
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


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/61d40a04-c909-4eb2-ba1a-14f62fcd66f8" width="500"/>

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

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/07c115d7-cdeb-4548-878e-01f6e19f9b79" width="500"/>

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







