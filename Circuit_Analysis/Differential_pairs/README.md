##  Circuit Analysis of Differntial Pairs in  Op-amp

Given that the ideal op amp has infinite gain and infinite input impedance, our design must have extremely high gain and extremely high input impedance.
Therefore we use a common source amplifier because of its high gain and infinite input impedance rather than common drain or common gate <br><br>


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/c457b577-a86b-4909-8fe4-ef02d3493089" width="400"/>
<br>
<br>


#### The gain of the common source can be maximized by choosing the value of RD properply, It should be ensured that the transistor is in Saturation Region (Vds>Vgs-Vt) so that which gm (transconductance) is maximum, Effectively increasing the gain of the cirucit. <br>


However there are other methodologies to build common source amplifier using feedback techniques.
The feedback technique used for the opamp is source feedback bias , This ensures that the current flowing through the transistor
is as per requirement by self calibration of Vgs of the transistor <br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f242c89f-0a40-4f5d-b524-2440d31d208d" width="400"/>
<br>
<br>
This is a small example of the source feedback CS AMP, As we can see the voltage across current source sets such that effective Vgs is maintained
for the drain current to be I0.
The gain of the transistor remains the same ie < *Av*=*-gmRD*><br>

So now that we know about common source amplifier using source feedback bias, let us now move towards building a differntial pair. <br>

##  The Differential Pair

#### A differntial pair is a circuit whose ouput is proportional to difference between the inputs. As opamp is a device whose ouput is directly proporational to its input ,Therefore differntial Pair is a necessary for design of opamp.
Let us consider 2 signals Vp and Vn and apply to two different CS AMP with source feedback bias. <br> <br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/3fa051ef-608b-4eef-aa4e-451967f50e53" width="400"/>
<br>
<br>

Consider both the transistors and resistance are identical a current of IO flows through each of the transistors .<br>
By performing small signal realization of the circuit it is noted that when the output is measured across each of the 
transistors it is directly proporational to difference between the inputs. <br> <br>

<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/eef8837b-3d78-4332-a3c5-bc1ce5557092" width="400"/> <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/88bde794-bc11-4e3f-9be3-59ae7a703a31" width="400"/>
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


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/2f8c3426-0541-4133-a1fc-e5a06182d927" width="400"/>
<br>
<br>
Thus by small signal analysis it is confirmed that Common mode gain Av(CM) of the differntial pair is zero which resembles the characteristic of opamp.

### Differntial Mode Gain <br>

Let us find the differntial mode gain by applying the differntial input voltages to the two terminals of the transistor. <br>
As the diffferntial voltage at terminal Vn is negative, as the same current is flowing throughout the circuit the node voltage Vx is at small signal ground 
ie Vx=0. <br> <br>


<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/7c71f0a7-4277-45f2-9581-216c41f3fc15" width="400"/>
<br>
<br>

So by small signal analysis, The differntial mode gain < Av(DM)=2gmRD.> which can be made high by ensuring that both transistor remains in saturation region 

