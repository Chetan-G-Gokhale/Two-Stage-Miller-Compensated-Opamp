##  Circuit Analysis of Differntial Pairs in  Op-amp

Given that the ideal op amp has infinite gain and infinite input impedance, our design must have extremely high gain and extremely high input impedance.
Therefore we use a common source amplifier because of its high gain and infinite input impedance rather than common drain or common gate <br><br>


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f6a76af0-224c-439d-af74-917619c78530" width="400"/>
<br>
<br>


#### The gain of the common source can be maximized by choosing the value of RD properply, It should be ensured that the transistor is in Saturation Region (Vds>Vgs-Vt) so that which gm (transconductance) is maximum, Effectively increasing the gain of the cirucit. <br>


However there are other methodologies to build common source amplifier using feedback techniques.
The feedback technique used for the opamp is source feedback bias , This ensures that the current flowing through the transistor
is as per requirement by self calibration of Vgs of the transistor <br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/eed418e8-3194-418e-8565-20cb706b62cb" width="400"/>
<br>
<br>
This is a small example of the source feedback CS AMP, As we can see the voltage across current source sets such that effective Vgs is maintained
for the drain current to be I0.
The gain of the transistor remains the same ie < *Av*=*-gmRD*><br>

So now that we know about common source amplifier using source feedback bias, let us now move towards building a differntial pair. <br>

##  The Differential Pair

#### A differntial pair is a circuit whose ouput is proportional to difference between the inputs. As opamp is a device whose ouput is directly proporational to its input ,Therefore differntial Pair is a necessary for design of opamp.
Let us consider 2 signals Vp and Vn and apply to two different CS AMP with source feedback bias. <br> <br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/1371e2fe-28fd-4875-a2ec-cacb8cabae5a" width="400"/>
<br>
<br>

Consider both the transistors and resistance are identical a current of IO flows through each of the transistors .<br>
By performing small signal realization of the circuit it is noted that when the output is measured across each of the 
transistors it is directly proporational to difference between the inputs. <br> <br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/5a1ca1d6-36b4-4f8c-b936-9b9030378e36" width="400"/>
<br>
<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/7b565087-ed6c-431a-a62e-0c0834e372ab" width="400"/>
<br>
<br>

#### By small signal model it is confirmed that Vo= gmRD*(Vp-Vn)/2 with its effective gain of  *Av*=*gmRD/2* <br> <br>

# Commom Mode gain and Differntial Mode Gain

We know that an ideal opamp has Common mode gain Av(CM)=0 and Differntial mode gain Av(DM)=Infinity, So let us represent our signal in terms of common mode and
differntial mode signals <br>

Let the average value of both the signal (ie) <VCM= (Vp+Vn)/2> and Differntial voltage <VDM =(Vp-Vn)/2.> <br>
Both the input signals can be represented by common mode voltage and differntial mode voltage <br>
Where Vp = VCM +VDM and  Vn= VCM-VDM

Now we can analyze the effect of common mode and differntial mode input to the differntial pair individually. <br>

### Common Mode Gain   <br>

Let us find the common mode gain by applying common mode inputs to the two terminals of the differntial pair.<br>
The node voltage Vx=Vcm because os the symmetric nature of the circuit. <br>


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/3d16ab06-82ae-493c-a750-08fd62d30ac3" width="400"/>
<br>
<br>
Thus by small signal analysis it is confirmed that Common mode gain Av(CM) of the differntial pair is zero which resembles the characteristic of opamp.

### Differntial Mode Gain <br>

Let us find the differntial mode gain by applying the differntial input voltages to the two terminals of the transistor. <br>
As the diffferntial voltage at terminal Vn is negative, as the same current is flowing throughout the circuit the node voltage Vx is at small signal ground 
ie Vx=0. <br> <br>


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/598eba44-a521-47c1-80d5-7f70a7689476" width="400"/>
<br>
<br>

So by small signal analysis, The differntial mode gain < Av(DM)=2gmRD.> which can be made high by ensuring that both transistor remains in saturation region 
