##  Detailed Circuit Analysis of Op-amp

Given that the ideal op amp has infinite gain and infinite input impedance, our design must have extremely high gain and extremely high input impedance.
Therefore we use a common source amplifier because of its high gain and infinite input impedance rather than common drain or common gate <br><br>

![image](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/c457b577-a86b-4909-8fe4-ef02d3493089)



#### The gain of the common source can be maximized by choosing the value of RD properply, It should be ensured that the transistor is in Saturation Region (Vds>Vgs-Vt) so that which gm (transconductance) is maximum, Effectively increasing the gain of the cirucit. <br>


However there are other methodologies to build common source amplifier using feedback techniques.
The feedback technique used for the opamp is source feedback bias , This ensures that the current flowing through the transistor
is as per requirement by self calibration of Vgs of the transistor <br>

![CS_AMP](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f242c89f-0a40-4f5d-b524-2440d31d208d)

This is a small example of the source feedback CS AMP, As we can see the voltage across current source sets such that effective Vgs is maintained
for the drain current to be I0.
The gain of the transistor remains the same ie *Av*=*-gmRD*<br>

So now that we know about common source amplifier using source feedback bias, let us now move towards building a differntial pair. <br>
#### A differntial pair is a circuit whose ouput is proportional to difference between the inputs. As opamp is a device a device whose ouput is directly proporational to its input , differntial Pair is a higly important for realization of opamp.
Let us consider 2 signals Vp and Vn and apply to two different CS AMP with source feedback bias. <br> <br>


![image](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/3fa051ef-608b-4eef-aa4e-451967f50e53)


Consider both the transistors and resistance are identical a current of IO flows through each of the transistors .<br>
By performing small signal realization of the circuit it is noted that when the output is measured across each of the 
transistors it is directly proporational to difference between the inputs. <br> <br>

![image](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/eef8837b-3d78-4332-a3c5-bc1ce5557092) <br>

![image](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/88bde794-bc11-4e3f-9be3-59ae7a703a31) <br>

#### By small signal model it is confirmed that Vo= gmRD*(Vp-Vn)/2 with its effective gain of  *Av*=*gmRD/2*









