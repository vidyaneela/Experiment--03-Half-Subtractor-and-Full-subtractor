# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1.Use module program name(input,output) to start the Verilog programmming.

2.Assign inputs and outputs.

3.End the verilog program using keyword endmodule.


## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Vidyaneela.M
RegisterNumber:  212221230120
*/
### Half-subtractor:
```
module subtractor(output b,d,input x,y);
assign d = x^y;
assign b = ~x&y;
endmodule
```
### Full-subtractor:
```
module fullsub(output d,b,input x,y,z);
assign d = x^y^z;
assign b = ~x&(y^z)|y&z;
endmodule
```
## Output:
### Half-Subtractor:
## Truthtable
![halfsubTT](https://user-images.githubusercontent.com/94169318/196087144-fa0154b4-aaa8-441b-aa45-90155d818cce.png)

##  RTL realization
![subtractor 1](https://user-images.githubusercontent.com/94169318/196087161-e3386bab-ede7-4bfc-b670-2b18479fafc0.png)


## Timing diagram 
![subwave](https://user-images.githubusercontent.com/94169318/196087194-8c040298-f2b4-4885-9518-53fd9871c683.png)

### Full-subtractor:
## Truthtable
![fullsubTT](https://user-images.githubusercontent.com/94169318/196087700-d9296463-f3ed-4cc9-8db2-16599c7a26ae.png)

##  RTL realization
![fullsub](https://user-images.githubusercontent.com/94169318/196087723-2b594da7-59fd-42a8-9356-35b531edc3f8.png)

## Timing diagram 
![wavefull](https://user-images.githubusercontent.com/94169318/196087750-73a1355e-b9c6-490b-a540-f492e73bc4e5.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
