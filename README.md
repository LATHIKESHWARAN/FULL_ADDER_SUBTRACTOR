# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**
##### FULL ADDER

![image](https://github.com/LATHIKESHWARAN/FULL_ADDER_SUBTRACTOR/assets/119393556/a42660dc-3371-45c8-8b1a-4add672b9740)

##### FULL SUBTRACTOR

![image](https://github.com/LATHIKESHWARAN/FULL_ADDER_SUBTRACTOR/assets/119393556/e1ccc671-a85a-4f50-9bc1-9a46afd975b0)



**Procedure**

Full Adder:
Open Quartus II and create a new project.
Use schematic design entry to draw the full adder circuit.
The circuit consists of XOR, AND, and OR gates.
Compile the design, verify its functionality through simulation.
Implement the design on the target device and program it.


Full Subtractor:
Follow the same steps as for the full adder.
Draw the full subtractor circuit using schematic design.
The circuit includes XOR, AND, OR gates to perform subtraction.
Compile, simulate, implement, and program the design similarly to the full adder.

## Program:

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 

Developed by: LATHIKESHWARAN J

RegisterNumber: 212222230072
*/

### FULL ADDER
```C
module full_add(a,b,cin,sum,carry);
input a,b,cin;
output sum,carry;
wire w1,w2,w3,w4;       
xor(w1,a,b);
xor(sum,w1,cin);        

and(w2,a,b);
and(w3,b,cin);
and(w4,cin,a);

or(carry,w2,w3,w4);
endmodule
```

### FULL SUBTRACTOR
```C
module full_sub(a,b,Bin,BO,DIFF);
input a,b,Bin;
output BO,DIFF;
assign DIFF = a ^ b ^ Bin;
  assign BO = (a & b) | ((a ^ b) & Bin);
endmodule
```

## RTL Schematic

**Output Timing Waveform**
#### FULL ADDER
![image](https://github.com/LATHIKESHWARAN/FULL_ADDER_SUBTRACTOR/assets/119393556/08a8b0bd-cbd4-47ef-9dd7-67f216d23fa5)
#### FULL SUBTRACTOR
![image](https://github.com/LATHIKESHWARAN/FULL_ADDER_SUBTRACTOR/assets/119393556/49030cdb-27f6-4145-80eb-d81faf8642ea)



## Result:

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



