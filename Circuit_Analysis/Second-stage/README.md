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
