## Specifications Obtained

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

