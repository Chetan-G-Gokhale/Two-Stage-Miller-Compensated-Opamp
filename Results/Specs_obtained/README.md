# Final Specifications

## Circuit Diagram

 The final circuit of the opamp which includes all the differntial pair and current mirror dummy transistor which were used during the implementation of layout. <br>
 
  
<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/54b222ec-8b71-490f-b21c-a0050bbb1263">
</p>
<br>

# Gain and Phase margin 

The Gain obatined was around 68db with a Unity gain Bandwidth of 23M Hz for a load of Cl=1pf with a phase margin of 80 degrees which is pretty good comparing
for designed specification: <br>
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
  
  #### Conclusion:  If we increase the capacitive load of the opamp then frequency of operation may decrease but opamp wouldnt become unstable this is due      regenerative resistor added in feedback
  
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
  
  As we know the diifferntial mode gain of opamp was found out to be 68db, we can find the common mode gain by providing the same input to both
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
  
 
   
   
   
   

   
