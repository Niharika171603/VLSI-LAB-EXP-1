# VLSI-LAB-EXPERIMENTS
      
      Simulation and Implementation of logic gates,adders and subtractors.

AIM: 

    To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: 

        vivado 2023.3

PROCEDURE:

STEP:1 Start the Xilinx navigator, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 

STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 

STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained.

STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. 

STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. 

STEP:11 Load the Bit file.

STEP:12 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :


Logic Gates:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/b0edb78b-9591-4324-a66c-0a7b86d68fe3)


Half Adder:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/7e15461b-4c72-4bfb-a0b4-c4bad8ec836b)


Full adder:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/42b5816a-88f6-4e00-be04-78d340b88ee1)



Half Subtractor:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/cbd4cb36-8a8b-47f0-9416-cdf4cf5f7c63)




Full Subtractor:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/34acc0e6-ca27-410a-be6d-715a77a50ff0)




8 Bit Ripple Carry Adder

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/dad36f0b-bd7f-483b-9096-9ff6366ffe37)




VERILOG CODE:

module logic(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate );

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

HALF ADDER:

module HalfAdder(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule

FULL ADDER:

module FA(a,b,cin,sum,cout);

input a,b,cin;

output sum,cout;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,w1,cin);

and g3(w3,a,b);

xor g4(sum,w1,cin);

or g5(cout,w2,w3);

endmodule

HALF SUBTRACTOR:

module halfsubtractor(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor g1(diff,a,b);

and g2(borrow,~a,b);

endmodule

FULL SUBTRACTOR:

module full_sub(a,b,bin,diff,borrow);

input a,b,bin;

output diff,borrow;

wire w1,w2,w3;

xor g1(w1,a,bin);

and g2(w2,~a,b);

xor g3(diff,w1,bin);

or g4(borrow,w2,w3);

and g5(w3,~w1,bin);

endmodule

8 BIT RIPPLE CARRY ADDER:

module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum = a^b^c;

assign carry=(a&b)|(b&c)|(c&a);

endmodule

module rca(a,b,cin,sum,cout);

input [7:0]a,b;

input cin;

output [7:0]sum;

output cout;

wire c1,c2,c3,c4,c5,c6,c7;

fa fa1(a[0],b[0],cin,sum[0],c1);

fa fa2(a[1],b[1],c1,sum[1],c2);

fa fa3(a[2],b[2],c2,sum[2],c3);

fa fa4(a[3],b[3],c3,sum[3],c4);

fa fa5(a[4],b[4],c4,sum[4],c5);

fa fa6(a[5],b[5],c5,sum[5],c6);

fa fa7(a[6],b[6],c6,sum[6],c7);

fa fa8(a[7],b[7],c7,sum[7],cout);

endmodule

OUTPUT:

logic gates:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/04cb2b44-09d4-44c8-b89a-e70ad9400e1c)


HALF ADDER:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/fd1fee5a-7994-4dc9-9b0e-73b9c7fc07b9)


FULL ADDER:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/cc45c429-c28a-4a01-ac3e-85a2d18330c8)


HALF SUBTRACTOR:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/c3f9070f-aaf3-4443-9c8f-1bb7392a6c24)


FULL SUBTRACTOR:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/fe4974a5-9d20-4bb8-a85b-dccaec133bc8)


8 BIT RIPPLE CARRY ADDER:

![image](https://github.com/Niharika171603/VLSI-LAB-EXP-1/assets/161016278/cf33e579-53a1-43ff-8df4-35830673c867)

 

RESULT:

Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .

