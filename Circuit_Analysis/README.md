This Folder Contains the Circuit analysis and detailed explaination of opamp

Table of contents
=================

<!--ts-->
 * CIRCUIT ANALYSIS
      * [DIFFERENTIAL PAIR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Circuit_Analysis/Differential_pairs)
      * [CURRENT MIRROR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/a7e6dc1db5b0d7c6e0652ee6a39ef51033dff6da/Circuit_Analysis/Current_mirror)
      * [SECOND STAGE](#remote-files)

<!--te-->


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



# Current Mirrors

Current Mirrors are very essential in the analog design,because of its two major characteristics :

##### * High output impedance which is insensitive to the output current ensuring low voltage drop across it.
##### * The Ability to produce the same current flowing in the  transistor to any other transistors 

The opamp's differntial pair utilizes both of the characteristics of current mirrors by one pair of PMOS current mirror for high output impedance and 
one pair of NMOS current mirror for biasing of the common source amplifiers.

## Working of Current mirrors

Current mirror works on the pinciple of Drain to source feedback Connection, These are usually called as diode connected transistors as t
Lets us consider a Nmos transistor with a parastitic cap/capacitor connected to its drain terminal
let I0 be the required current supplied to the drain of the NMOS and ID is the current flowing in the transistor 
so therefore the current flowing through the capcitor is ID-I0 <br> <br>



<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/14f795fc-d4a1-4bef-909f-f45f537fb6fa" width="400"/>

<br>
<br>


Consider the 2 cases needed to be analyzed:
#### When ID< I0
   In this case as ID<I0, the current through the capacitor is positive ie (I0-ID) so the voltage across the transistor Vds increases <br>
   As Vds is equal to Vgs due to drain-source connection , the Vgs of the transistor increases <br>
   As Id is directly proportional to Vgs , ID increases upuntill ID=0 . <br>


#### When ID>I0
   In this case when ID>IO, the current through the capacitor is opposite , thereby decreasing Vds of the transistor. <br>
   As Vds decreases Vgs decreases which inturn decreases the ID , As the ID is directly proportional to Vgs. <br>
   Therefore this process is repeated till I0=ID and there is no current flowing in the capacitor. <br>
   
   
   
Therefore is the gate terminal is connected to any number of transistors , given that they have same Vt , Width and length 
and are completely identical so that the current can be mirrored exactly. <br>
And it should be made sure that the Vds of that transistor is greater than its Vgs-vt , so that it remainsin saturation 


#### Note : As process variation may affect the Vgs,Vt and other parameters of transistors ,It is to be ensured that the current mirrors are taken utmost care, especially the diode connected transistor , Therfore techniques such as interdigitation methodology are implemented during layout .
<br>

## Current mirror as finite ouput impedance 

We can recall from the common source amplifier that the gain obtained was Av=-gmRD , so if we need to maximize the gain of the amp then it should be made 
sure by choosing Rd such that the transistor reamains in saturation.

Now the diode connected transistor provides and a high output impedance that is independent of the current flowing across it.
Let us find out the Output impedance of the diode connected transistor by providing a voltage supply at the output and measuring the current.

<br>
<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/635632fa-c3cf-4bae-8f17-3b4e29690991" width="400"/>
<br>
<br>


From the calculations showed above it is noted that the ouput impedance of the diode connected device Rd=1/gm constant which is independent of
the current flowing across it,
As 1/gm is constant , now the amplifier can be properly biased so that it remains in saturation.maximizing the gain of the circuit .

## Second Stage Requirement and Analysis 

As we have seen from the differntial pair, The gain obtained due to differntial pair is gmRd/2,<br>
However if there is a Load or parasitic capacitance present at the output terminal then  it affects the bandiwdth of the opamp,it reduces the bandwidth of the opamp by introducing poles in the system,
Let us look at how the load capacitance affects single stage opamp(differntial pair) <br>


   <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/6ed462a7-ad36-4b7b-a299-c3da1950a56c" width="750" height="750">






As seen from the above figure it is clear that load capacitance introduces a LHP Poles and makes the gain as a function of frequency.<br>



So we consider a 2 stage opamp , where one stage provides the gain of the system and the other stage provides gain to compensated for any load present at the output terminal. <br>

## Miller effect 

Miller compensation is a technique used in electronic circuit design to stabilize the frequency response of amplifiers, particularly in operational amplifiers (op-amps). The Miller compensated capacitor, also known as the Miller capacitor, is a key component in this compensation technique.

Let us look at how the Miller Compensation works by considering the circuit as given below : <br>


   <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/73288a22-10b4-4106-b67a-00abef865741" width="500" height="750">






By Seeing the input impedance across the opamp the capacior value Cc has its equivalent increased to (A+1)Cc,Considering the gaain of the opmap to be very high the an quaivalent capcitor of higher value can be achieved with that of a small capcitor Cc. <br>




## Miller Compesnation

Now that we know how Miller effect works , Let us look into how the Miller capacitance introduced a Concept called as pole splitting, <br> Miller capacitor pulls the dominant poles closer to the origin and pushes the Non dominant poles very far to higher frequency providing us with increased bandwidth of the opamp.<br>


<table>
  <tr>
     <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/b1692960-52db-4bc2-a435-142eb2569259" width=360 height=620></td>
    <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/57349daf-83c4-45ce-82a2-584823fdf122" width=360 height=620></td>
     
  </tr>
  <tr>
     <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/517ea2b9-44a2-4231-afbf-b2bb8c287f12" width=360 height=620></td>
    <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/4446216a-0dc9-44a3-a30d-f8db61e014a8" width=360 height=620></td>
    
  
 </tr>
</table>


# Here are the comparsion of Two Stage Opamp vs a Miller Compesnated Opamp 



 <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/78b9bac6-331f-4121-9cc5-e734b9775802" width="500" height="750">

 <br>
 It is clear from the above approximate bode plot that Miller compesnation provides a higher bandwidth and a good phase margin by the concept of pole spliting

