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
