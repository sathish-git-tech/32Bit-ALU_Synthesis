# 32Bit-ALU_Synthesis

## Aim:

Synthesize 32 Bit ALU design using Constraints and analyse area and Power reports.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)
## Design code
```
module ALU ( input [3:0] A, B,
input [2:0] ALU_Sel,
output reg [3:0] ALU_Out,
output reg CarryOut );
always @(*) begin
    case (ALU_Sel)
        3'b000: {CarryOut, ALU_Out} = A + B;
        3'b001: {CarryOut, ALU_Out} = A - B;
        3'b010: ALU_Out = A & B;
        3'b011: ALU_Out = A | B;
        3'b100: ALU_Out = A ^ B;
        3'b101: ALU_Out = ~A;
        3'b110: ALU_Out = A << 1;
        3'b111: ALU_Out = A >> 1;
        default: ALU_Out = 4'b0000;
    endcase
end
endmodule
```

### Step 2 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being
used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.

#### Synthesis RTL Schematic :
![image](https://github.com/sathish-git-tech/32Bit-ALU_Synthesis/blob/main/RTL%20vlsi.jpg)
#### Area report:
![image](https://github.com/sathish-git-tech/32Bit-ALU_Synthesis/blob/main/area%20report%20vlsi.jpg)
#### Power Report:
![image](https://github.com/sathish-git-tech/32Bit-ALU_Synthesis/blob/main/power%20output%20vlsi.jpg)

#### Result: 
![image](https://github.com/sathish-git-tech/32Bit-ALU_Synthesis/blob/main/output%20vlsi.jpg)
The generic netlist of 32 bit ALU  has been created, and area, power reports have been tabulated and generated using Genus.
