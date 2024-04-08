SIMULATION AND IMPLEMENTATION OF  COMBINATIONAL LOGIC CIRCUITS

AIM: 
 To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using Xilinx ISE.

APPARATUS REQUIRED:
Xilinx 14.7
Spartan6 FPGA

**LOGIC DIAGRAM**

ENCODER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/3cd1f95e-7531-4cad-9154-fdd397ac439e)


DECODER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/45a5e6cf-bbe0-4fd5-ac84-e5ad4477483b)


MULTIPLEXER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/427f75b2-8e67-44b9-ac45-a66651787436)


DEMULTIPLEXER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/1c45a7fc-08ac-4f76-87f2-c084e7150557)


MAGNITUDE COMPARATOR

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/b2fe7a05-6bf7-4dcb-8f5d-28abbf7ea8c2)


  
PROCEDURE:
STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.

VERILOG CODE

   <<< TYPE YOUR VERILOG CODE >>>

OUTPUT WAVEFORM
 <<< PASTE YOUR OUTPUT WAVEFORM >>>

RESULT
VERILOG CODE

#1 DECODER3to8:-

Code:


OUTPUT WAVEFORM:

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/178b6360-1d49-4436-87d8-9084218a5e9d)

Elaborated Design:

![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/f1208606-2a82-4f5d-952c-de05c9c776cc)

#2 DEMULTIPLEXER 1to8:-

Code:


OUTPUT:-

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/baca60cd-e1a5-4b61-9b75-01a67a4cf913)

Elaborated Design:

![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/510bbc75-3faf-49f5-9d53-3151ee8189e6)

#3 Encoder_8to3:- Code:
Code:
module encoder_8_to_3(a0,a1,a2,d0,d1,d2,d3,d4,d5,d6,d7);�input d0,d1,d2,d3,d4,d5,d6,d7;
output a0,a1,a2;
or g1(a0,d1,d3,d5,d7);
or g2(a1,d2,d3,d6,d7);
or g3(a2,d4,d5,d6,d7);
endmodule

OUTPUT:-

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/277d518b-cf21-4131-aa89-d98f312fb116)

Elaborated Design:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/549e952f-0b07-467f-9177-4aee90faa9e3)

#4 MAGNITUDE_COMPARATOR:- 
Code:
module comparator(a,b,eq,lt,gt);
input [3:0] a,b;
output reg eq,lt,gt;
always @(a,b)
begin
 if (a==b)
 begin
  eq = 1'b1;
  lt = 1'b0;
  gt = 1'b0;
 end
 else if (a>b)
begin
  eq = 1'b0;
  lt = 1'b0;
  gt = 1'b1;
 end
 else
 begin
  eq = 1'b0;
  lt = 1'b1;
  gt = 1'b0;
 end
end 
endmodule

OUTPUT:-

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/b723ad2a-79f2-401f-835d-ffb53dc75ada)
Elaborated Design:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/57c6e0e7-2b78-4f07-98b5-753d69e05f57)
