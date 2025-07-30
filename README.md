# RAM-DESIGN

COMPANY :CODTECH IT SOLUTIONS

NAME :SANJAY RAJ C

INTERN ID :CT04DH982

DOMAIN: VLSI

DURATION: 4 WEEKS

MENTOR : NEELA SANTOSH

The given Verilog code implements a simple synchronous RAM and its testbench to demonstrate read and write operations. The RAM module, named simple_ram, is designed as a 16 x 8-bit memory, meaning it has 16 memory locations, each capable of storing 8-bit data. It takes a clock signal (clk), a write enable signal (we), a 4-bit address (addr), and an 8-bit input data (data_in). The output data_out provides the data stored at the specified address during a read operation. The memory is declared as reg [7:0] mem [0:15]. The module uses an always @(posedge clk) block to ensure that both read and write operations are synchronized with the rising edge of the clock. If we is set to 1, the data on data_in is written to the memory location specified by addr. When we is 0, the data stored in the selected memory location is output through data_out.

The testbench tb_simple_ram is written to verify the correct functioning of the RAM module. It defines the signals clk, we, addr, and data_in, and instantiates the simple_ram module. A clock signal is generated using always #5 clk = ~clk;, which toggles the clock every 5 nanoseconds, creating a 10 ns clock period. To generate a waveform for debugging and visualization, the testbench includes $dumpfile("dump.vcd") and $dumpvars(0, tb_simple_ram). These commands create a Value Change Dump (VCD) file that can be viewed using EPWave in EDA Playground. The $monitor statement is used to display the values of signals like we, addr, data_in, and data_out at each simulation time step.

The simulation sequence starts by enabling the write operation (we=1) and writing three data values (A5, 5A, and FF in hexadecimal) into addresses 0, 1, and 2, respectively. After writing, the testbench switches to read mode (we=0) and reads from the same addresses to verify that the data stored is correctly retrieved. Each operation is delayed by 10 ns to align with the clock edges, ensuring proper timing for the synchronous RAM. The simulation concludes with the $finish command.

To run this design in EDA Playground, both ram.v (RAM module) and tb_ram.v (testbench) files must be created. Once the code is pasted and executed, the output can be viewed in the EPWave waveform viewer. The waveform visually confirms the read and write processes, showing how data is stored during we=1 and correctly retrieved during we=0. This project demonstrates the basic design and verification of a synchronous RAM using Verilog, making it an essential foundation for more complex memory design tasks.
