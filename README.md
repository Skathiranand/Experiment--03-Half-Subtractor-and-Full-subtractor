### Name:Kathir Anand.S
### Reg No:23013711

# Experiment 04 Half Subtractor and Full subtractor

## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher Software – Quartus prime

## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

### Procedure:
Connect the supply (+5V) to the circuit Switch ON the main switch If the output is 1, then the led glows.

### Program:
```
module HalfSubstractor (a,b,diff,borrow);
input a,b;
output diff,borrow;
xor (diff,a,b);
and (borrow,~a,b);
endmodule
```
### Truth Table:
![IMG](https://github.com/Skathiranand/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147141136/7afedacc-5cef-430a-9564-f542a448f803)

### RTL Realization:
![IMG](https://github.com/Skathiranand/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147141136/6857737e-3a08-4e4c-9340-03dfb84531f2)

### Timing Diagram:
![IMG](https://github.com/Skathiranand/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147141136/bf6d06b7-0af9-4e43-97bc-5b4a0a4beb54)

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure:
Connect the supply (+5V) to the circuit Switch ON the main switch If the output is 1, then the led glows.

## Program:
```
module FullSubstractor(a,b,c,diff,borrow);
input a,b,c;
output diff,borrow;
xor(diff,a,b,c);
assign borrow=~a&b|c&~(a^b);
endmodule
```
### Truthtable:
![IMG](https://github.com/Skathiranand/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147141136/3820b042-d39c-4f88-9c7b-885267577135)

### RTL Realization:
![IMG](https://github.com/Skathiranand/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147141136/ea35ec99-beaa-44a5-9bfd-61aadf266d68)

## Timing diagram:
![IMG](https://github.com/Skathiranand/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147141136/60f4521b-f745-44e4-bfa4-adc29fd51fd9)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
