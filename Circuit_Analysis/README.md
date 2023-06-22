![2023_06_22 23_18 Office Lens (2)](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/341729d9-9073-4019-b744-f649e8c70a8a)This Folder Contains the Circuit analysis and detailed explaination of opamp

Table of contents
=================

<!--ts-->
 * CIRCUIT ANALYSIS
      * [DIFFERENTIAL PAIR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Circuit_Analysis#circuit-analysis-of-differntial-pairs-in--op-amp)
      * [CURRENT MIRROR](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Circuit_Analysis#current-mirrors)
      * [SECOND STAGE](https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/tree/main/Circuit_Analysis#second-stage-requirement-and-analysis)

<!--te-->


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



<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/b26a0dd4-2a88-40c8-8548-5d039a483959" width="400"/>

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
<img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/dd8a2304-c5ba-4aea-9ce9-b515ad55bec9" width="400"/>
<br>
<br>


From the calculations showed above it is noted that the ouput impedance of the diode connected device Rd=1/gm constant which is independent of
the current flowing across it,
As 1/gm is constant , now the amplifier can be properly biased so that it remains in saturation.maximizing the gain of the circuit .

## Second Stage Requirement and Analysis 

As we have seen from the differntial pair, The gain obtained due to differntial pair is gmRd/2,<br>
However if there is a Load or parasitic capacitance present at the output terminal then  it affects the bandiwdth of the opamp,it reduces the bandwidth of the opamp by introducing poles in the system,
Let us look at how the load capacitance affects single stage opamp(differntial pair) <br>


   <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/dba355b5-2ec9-4480-8e25-40d67a8fea0f" width="750" height="750">






As seen from the above figure it is clear that load capacitance introduces a LHP Poles and makes the gain as a function of frequency.<br>



So we consider a 2 stage opamp , where one stage provides the gain of the system and the other stage provides gain to compensated for any load present at the output terminal. <br>

## Miller effect 

Miller compensation is a technique used in electronic circuit design to stabilize the frequency response of amplifiers, particularly in operational amplifiers (op-amps). The Miller compensated capacitor, also known as the Miller capacitor, is a key component in this compensation technique.

Let us look at how the Miller Compensation works by considering the circuit as given below : <br>


   <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/8fdf02b0-178f-4c2e-a80c-3715104cf934" width="500" height="750">






By Seeing the input impedance across the opamp the capacior value Cc has its equivalent increased to (A+1)Cc,Considering the gaain of the opmap to be very high the an quaivalent capcitor of higher value can be achieved with that of a small capcitor Cc. <br>




## Miller Compesnation

Now that we know how Miller effect works , Let us look into how the Miller capacitance introduced a Concept called as pole splitting, <br> Miller capacitor pulls the dominant poles closer to the origin and pushes the Non dominant poles very far to higher frequency providing us with increased bandwidth of the opamp.<br>


<table>
  <tr>
     <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/9c4ce510-bdc5-4fb7-956c-8ec3c225ade1" width=360 height=620></td>
    <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/6bb09b2c-36e3-4240-822e-14137fdc94c0" width=360 height=620></td>
     
  </tr>
  <tr>
     <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/c73fbe2a-6601-41a0-a97d-0d02d72fd313" width=360 height=620></td>
    <td><img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/3f0e5e60-3608-4195-9b76-a9028fa5e7f1" width=360 height=620></td>
    
  
 </tr>
</table>


## Here is the comparsion of Two Stage Opamp vs a Miller Compesnated Opamp 



 <img src="https://github.com/Chetan-G-Gokhale/Two-Stage-Miller-Compensated-Opamp/assets/126239004/f7e6f456-511a-4939-8287-ba5d2546d9af" width="500" height="750">

 <br>
 It is clear from the above approximate bode plot that Miller compesnation provides a higher bandwidth and a good phase margin by the concept of pole spliting

