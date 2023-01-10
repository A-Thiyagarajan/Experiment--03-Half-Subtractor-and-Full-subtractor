# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
# AIM:
### Ref number: 22008681 A.Thiyagarajan.
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

# Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime
# Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

# Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

# Procedure
It can be implemented using two half subtractors and one OR gate as: Giving one half subtractor the inputs A and B that gives outputs Diff1 and B1. Giving second half subtractor inputs Bin and Diff1 from first subtractor that gives outputs B2 and D (difference for the full subtractor).

# Program
## Half subtractor
```
module halfsub(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
assign Diff=(A^B);
assign Borrow=(~A&B);
endmodule
```

## Full subtractor
```
module fullsub(A,B,C,diff,borrow);
input A,B,C;
output diff,borrow;
assign borrow = (~A&(B^C)|(B&C));
assign diff = (A^B^C);
endmodule
```
# Output:
## Half subtractor
![half sub diagram](https://user-images.githubusercontent.com/118707693/211642606-e6094b74-24aa-4435-ae87-0396741b7528.png)

## Full subtractor
![fullsub diagram](https://user-images.githubusercontent.com/118707693/211642721-71357763-f70e-4059-858f-7ae7b64aae91.png)

# Logic sympol and truth table
## Half subtractor
![half sub symbol and table](https://user-images.githubusercontent.com/118707693/211643844-6abac95e-79d2-48f0-a9ef-3e73221829a0.png)

## Full subtractor
![full sub symbol and table](https://user-images.githubusercontent.com/118707693/211643899-11422246-e153-4faf-8a7c-6458778d0a7a.png)


# Timing diagram 
## Half subtractor
![half sub td](https://user-images.githubusercontent.com/118707693/211643007-6807e761-6700-47e0-94c5-d39d24817a4b.png)

## Full subtractor
![fullsub td](https://user-images.githubusercontent.com/118707693/211643091-512c5005-c93b-4a70-b8fd-611808ee603e.png)

# Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
