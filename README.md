# Two-Stage-Miller-Compensated-Opamp
### Design Of OPAMP in 90nm of gain 70db and its layout implementation with DRC and LVS Cleared             

This is my first significant project in cadence, completed in my third year of BE. I advise you to watch "Nagendra Krishnapura" lectures from IITM  on "Analog IC Design" to gain a better grasp of the implementation. I learned about the fundamentals and significance of feedback systems in these lectures and designed a two stage opamp with Miller compensation and a nulling resistor.

For the design formulas of the transistors I referred to textbook by P. Allen and D. Holberg,"CMOS Analog Circuit Design",The Oxford Series in Electrical and Computer Engineering, 3rd ed. and some youtube series lectures from Hafeez KT


## DESIGN SPECIFICATION OF OPAMP
Gain= 70db <br>
Slew rate = 10 V/uS <br>
GBW (Gain Bandwidth) = 30M Hz <br>
ICMR(+)= 1.0 V <br>
ICMR(-)= 300 mV <br>
Vdc = 1.2 V <br>
Cl (Load Capacitance) = 1pF <br>




Table of contents
=================

<!--ts-->
   * [SPECIFICATIONS](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/edit/main/README.md#the-design-specifications-of-opamp)
   * [CIRCUIT ANALYSIS](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Circuit_Analysis)
      * [DIFFERENTIAL PAIR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Circuit_Analysis/Differential_pairs)
      * [CURRENT MIRROR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Circuit_Analysis/Current_mirror)
      * [SECOND STAGE](#remote-files)
   * [OUTCOME](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Results)
       * [CIRCUIT DIAGRAM](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Results/Specs_obtained#circuit-diagram)
       * [GAIN AND PHASE MARGIN](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Results/Specs_obtained#gain-and-phase-margin)
       * [SLEW RATE](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Results/Specs_obtained#slew-rate)
       * [CMRR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Results/Specs_obtained#cmrr-common-mode-rejection-ratio)
       * [APPLICATIONS](#public)
   * [LAYOUT](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Results/Layout)
     * [COMMON CENTROID](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Results/Layout#common-centriod)
     * [INTERDIGITATION](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Results/Layout#interdigitation)
     * [DRC CHECK](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/blob/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Results/Layout/OPAMP_DRC_CLEAR.png)
     * [LVS CHECK](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/blob/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Results/Layout/OPAMP_LVS_CLEARog2.png)
     * [FINAL LAYOUT](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/blob/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Results/Layout/FINAL.png)
    <!--te-->
    
## FINAL SPECIFICATION OBTAINED

Gain= 68db <br>
Slew rate = 9 V/uS <br>
GBW (Gain Bandwidth) = 23M Hz <br>
ICMR(+)= 0.8 V <br>
ICMR(-)= 300 mV <br>
Vdc = 1.2 V <br>
Cl (Load Capacitance) = 1pF-5pF <br>
    
    
   






