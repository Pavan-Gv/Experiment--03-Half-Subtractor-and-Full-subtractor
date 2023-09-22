# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
<b>Hardware</b> – PCs, Cyclone II , USB flasher
<b>Software</b> – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)
```
Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y
```
## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)
```
Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin
```
## Procedure
<b>Step 1</b>: Open Quartus and create a new project by selecting "File" > "New Project Wizard."
<b>Step 2</b>: Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).
<b>Step 3</b>: Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
<b>Step 4</b>: Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.
<b>Step 5</b>: Open the newly created Verilog or VHDL file and write the code for your combinational logic.
<b>Step 6</b>: To compile the project, click on "Processing" > "Start Compilation" in the menu.
<b>Step 7</b>: Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.
<b>Step 8</b>: If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
<b>Step 9</b>: Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
<b>Step 10</b>: Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
<b>Step 11</b>: Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.

## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Govindappagari Venkata Pavan Kumar
RegisterNumber:  212221240013
```
#### Half Subtractor:
```
module ex4(a,b,difference,borrow);
input a,b;
output difference,borrow;
wire x;
xor (difference,a,b);
not (x,a);
and (borrow,x,b);
endmodule
```
#### Full Subtractor:
```
module ex4(a,b,bin,difference,borrow);
input a,b,bin;
output difference,borrow;
wire p;
assign difference=((a^b)^bin);
not (p,a);
assign borrow=((p&b)|(p&bin)|(b&bin));
endmodule
```
## Output:
### Truthtable:
### Half Subtractor:

![image](https://github.com/Pavan-Gv/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/94827772/a75d69d9-3154-422c-a5c4-69392ed1b2af)

### Full Subtractor:

![image](https://github.com/Pavan-Gv/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/94827772/a47d7bee-98d8-426e-9a3f-fdc1d49fc418)


##  RTL realization:

### Half Subtractor:

![image](https://github.com/Pavan-Gv/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/94827772/6a29838d-a92f-47e8-962e-f0ce707dd199)

### Full Subtractor:

![image](https://github.com/Pavan-Gv/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/94827772/09440f96-0ee7-43d0-93bf-119ff2f22030)

## Timing diagram :

### Half Subtractor:

![image](https://github.com/Pavan-Gv/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/94827772/36d671a8-eb23-4de7-9b7b-1a1e18fabfe9)

### Full Subtractor:

![image](https://github.com/Pavan-Gv/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/94827772/39eb10f4-6d9b-4150-af74-b6a0b4acbeda)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
