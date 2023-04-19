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



Write the detailed procedure here 


## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: deepak.R
RegisterNumber:  212222050008
*/
```
#halfsubractor
module half_sub(a,b,diff,borrow);
input a,b;
output diff,borrow;
wire x;
xor (diff,a,b);
not (x,a);
and (borrow,x,b);
endmodule

#full subractor
module full_sub(a,b,c,diff,borrow);
input a,b,c;
output diff,borrow;
wire p;
assign diff=((a^b)^c);
not(p,a);
assign borrow=((p&b)|(p&c)|(b&c));
endmodule
```

## Output:

## Truthtable
1.
![truth table](https://user-images.githubusercontent.com/131233950/233145868-15ec88d2-7862-4723-bf27-d45a15c6fd87.png)
2.
![truth table2](https://user-images.githubusercontent.com/131233950/233145950-53081770-f2e8-463b-9d07-623b31f4f406.png)




##  RTL realization
1.
![IMG-20230419-WA0015](https://user-images.githubusercontent.com/131233950/233146077-fc7ed725-72c3-4813-aea6-8cace10c68a5.jpg)
2.
![IMG-20230419-WA0016](https://user-images.githubusercontent.com/131233950/233146192-ae5015f8-83da-4ce2-b15f-411b0ca43ee5.jpg)



## Timing diagram 
1.
![IMG-20230419-WA0019](https://user-images.githubusercontent.com/131233950/233146446-d429d0b8-f535-4b63-9960-922cd17a85c0.jpg)
2.
![IMG-20230419-WA0018](https://user-images.githubusercontent.com/131233950/233146539-3fc2c16a-5a44-401b-9df2-c9c78dedfbc2.jpg)



## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
