# Two-Stage-Miller-Compensated-Opamp
### Design of Opamp in 90nm with its layout DRC and LVS cleared.                  

This is my first significant project in cadence, completed in my third year of BE. I advise you to watch "Nagendra Krishnapura" lectures from IITM  on "Analog IC Design" to gain a better grasp of the implementation. I learned about the fundamentals and significance of feedback systems in these lectures and designed a two stage opamp with Miller compensation and a nulling resistor.

For the design formulas of the transistors I referred to textbook by P. Allen and D. Holberg,"CMOS Analog Circuit Design",The Oxford Series in Electrical and Computer Engineering, 3rd ed. and some youtube series lectures from Hafeez KT

## The Design specifications of Opamp
Gain= 70db <br>
Slew rate = 10 V/uS <br>
GBW (Gain Bandwidth) = 30M Hz <br>
ICMR(+)= 1.0 V <br>
ICMR(-)= 300 mV <br>
Vdc = 1.2 V <br>
Cl (Load Capacitance) = 1pF <br>



#### Note : The calcualtions obtained were mostly kept the same but was altered in some cases to match the required specification, But it was ensured that the                   changes made doesnot effect the stability of the opamp.








