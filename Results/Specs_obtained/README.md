# Final Specifications

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
  
 
   
   
   
   

   
