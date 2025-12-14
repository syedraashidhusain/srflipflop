SR-FLIPFLOP-USING-CASE

Developed by: SYED RAASHID HUSAIN M

register no: 25009038

AIM:
To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:
Quartus prime

THEORY:
SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.



This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.



Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State



By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.



The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

Procedure
1.Open Quartus software and create a new project.
2.Create a new VHDL file and write the code for the SR Flip Flop.
3.Compile the design by clicking on "Processing" -> "Start Compilation".
4.Create a testbench file to simulate the design.
5.Write the testbench code and add stimulus to test the SR Flip Flop.
6.Run the simulation by clicking on "Processing" -> "Start Simulation".
7.Observe the waveforms and verify the SR Flip Flop behavior.
8.Analyze the results and make any necessary changes to the design.
PROGRAM
```
// SR Flip-Flop (with async reset)
module sr_ff (
    input  wire clk, rst, S, R,
    output reg  Q
);
    always @(posedge clk) begin
        if (rst)
            Q <= 1'b0;         // Reset
        else begin
            case ({S,R})
                2'b00: Q <= Q;     // No change
                2'b01: Q <= 1'b0;  // Reset
                2'b10: Q <= 1'b1;  // Set
                2'b11: Q <= 1'bx;  // Invalid
            endcase
        end
    end
endmodule
```


RTL LOGIC FOR FLIPFLOPS
[rtl.pdf](https://github.com/user-attachments/files/24150041/rtl.pdf)



TIMING DIGRAMS FOR FLIP FLOPS
[wave.bmp](https://github.com/user-attachments/files/24150049/wave.bmp)


RESULTS
Thus the SR flipflop using verilog and validating their functionality using their functional tables is implemented successfully
