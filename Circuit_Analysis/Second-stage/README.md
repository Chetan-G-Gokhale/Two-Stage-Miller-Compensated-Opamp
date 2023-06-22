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
