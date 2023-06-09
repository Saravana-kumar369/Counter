### Ex. No. 6
#### Date: 19.5.23
# Implementation of 4 bit synchronous counters using Verilog HDL
## Aim:
To design and implement the following synchronous counters using Verilog HDL.
1.	UP counter
2.	DOWN counter
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
A Synchronous counter is the counter in which the clock input with all the flip-flops uses the same source and produces the output at the same time.
## UP Counter
### State table
![image](https://github.com/rvinifa/Counter/assets/133735746/ede78598-89fd-4aeb-9d82-329e45d05f2a)

### K-map Simplification

   ![image](https://github.com/rvinifa/Counter/assets/133735746/21554263-611b-44a2-8f78-7b2220ef5a05)
   
### Logic Diagram
![image](https://github.com/rvinifa/Counter/assets/133735746/2ab715d3-f6d5-4cf6-8fda-8fa666518c0b)



## DOWN Counter
### State Table
 ![image](https://github.com/rvinifa/Counter/assets/133735746/5be9585c-11aa-47c3-beaf-0dca916750f2)

### K-map simplification
 ![image](https://github.com/rvinifa/Counter/assets/133735746/dde7bc60-3a4f-4fb7-811d-f420cb74bdef)

### Logic Diagram
 ![image](https://github.com/rvinifa/Counter/assets/133735746/64e2d7b7-1646-4ca7-bc6c-c7c10881223c)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
### UPCOUNTER
```
module exp6(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always @(posedge clk)
begin
q4=(q1&q2&q3)^q4;
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end
endmodule
```
### DOWNCOUNTER
```
module ex6b(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always@ (posedge clk)
begin
 q4=((~q1)&(~q2)&(~q3))^q4;
 q3=((~q1)&(~q2))^q3;
 q2=(~q1)^q2;
 q1=1^q1;
end
endmodule 
```
## RTL Schematic:
### UPCOUNTER
![Screenshot 2023-06-09 140150 - Copy](https://github.com/Saravana-kumar369/Counter/assets/117925254/cc33d135-1675-4b89-9dd0-a28645df7b43)

### DOWNCOUNTER
![Screenshot (207)](https://github.com/Saravana-kumar369/Counter/assets/117925254/48eb23ce-80e8-4338-84ac-efb7b887e75b)
 
 
## Timing Diagram:
### UPCOUNTER
![Screenshot (200)](https://github.com/Saravana-kumar369/Counter/assets/117925254/3b7f4219-1ddd-4a88-925a-ea89ae1a9460)

### DOWNCOUNTER
![Screenshot (208)](https://github.com/Saravana-kumar369/Counter/assets/117925254/75bb0fed-123a-442c-a018-d3534037cccb)


## Result:
Thus the Synchronous UP and DOWN counters using T flipflops are implemented and the state tables are verified.

