SIMULATION AND IMPLEMENTATION OF  COMBINATIONAL LOGIC CIRCUITS

AIM: 
 To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using Vivado Software.
 
APPARATUS REQUIRED:
Vivado™ ML 2023.2

PROCEDURE:

Open Vivado: Launch Xilinx Vivado software on your computer.

Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.


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


RESULT
VERILOG CODE

#1 DECODER3to8:-

Code:
```
module decoder_struct(  
  input [2:0] a,    
  output [7:0] d    
   );
wire x,y,z;
not g1(z,a[0]);
not g2(y,a[1]);
not g3(x,a[2]);
and g4(d[0],x,y,z);
and g5(d[1],x,y,a[0]);
and g6(d[2],x,a[1],z);
and g7(d[3],x,a[1],a[0]);
and g8(d[4],a[2],y,z);
and g9(d[5],a[2],y,a[0]);
and g10(d[6],a[2],a[1],z);
and g11(d[7],a[2],a[1],a[0]);
endmodule
```


OUTPUT WAVEFORM:

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/178b6360-1d49-4436-87d8-9084218a5e9d)

Elaborated Design:

![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/f1208606-2a82-4f5d-952c-de05c9c776cc)

#2 DEMULTIPLEXER 1to8:-

Code:
```
module demux_1_8(y,s,a);
output reg [7:0]y;
input [2:0]s;
input a;

always @(*)
begin 
y=0;
case(s)
3'd0: y[0]=a;
3'd1: y[1]=a;
3'd2: y[2]=a;
3'd3: y[3]=a;
3'd4: y[4]=a;
3'd5: y[5]=a;
3'd6: y[6]=a;
3'd7: y[7]=a;
endcase
end
endmodule
```

OUTPUT:-

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/baca60cd-e1a5-4b61-9b75-01a67a4cf913)

Elaborated Design:

![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/510bbc75-3faf-49f5-9d53-3151ee8189e6)

#3 Encoder_8to3:- Code:
Code:
```
module encoder_8_to_3(a0,a1,a2,d0,d1,d2,d3,d4,d5,d6,d7);�input d0,d1,d2,d3,d4,d5,d6,d7;
output a0,a1,a2;
or g1(a0,d1,d3,d5,d7);
or g2(a1,d2,d3,d6,d7);
or g3(a2,d4,d5,d6,d7);
endmodule
```
OUTPUT:-

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/277d518b-cf21-4131-aa89-d98f312fb116)

Elaborated Design:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/549e952f-0b07-467f-9177-4aee90faa9e3)

#4 MAGNITUDE_COMPARATOR:- 
Code:
```
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
```

OUTPUT:-

Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/b723ad2a-79f2-401f-835d-ffb53dc75ada)
Elaborated Design:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/57c6e0e7-2b78-4f07-98b5-753d69e05f57)
#5 MULTIPLEXER_8to1:-
Code:
```
module mux_8tol (in, sel, out);
    input [7:0] in;
    input [2:0] sel;
    output reg out;
    always @(*)
       begin
          case (sel)
              3'b000: out = in [0];
              3'b001: out = in [1];
              3'b010: out = in [2];
              3'b011: out = in [3];
              3'b100: out = in [4];
              3'b101: out = in [5];
              3'b110: out = in [6];
              3'b111: out = in [7];
              default: out = 1'bx;
          endcase
       end
endmodule
```
OUTPUT:- 
Simulation:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/03153737-c78e-494a-80e9-c7a5ff4b9e0f)


Eloborated Design:
![image](https://github.com/Hariharan177/VLSI-LAB-EXP-2/assets/164841000/5b1e7b7a-5c53-413e-9721-2dbed575ccdb)


RESULT:
Simulation and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR is verified successfully using Vivado Software.

