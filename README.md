# **Wallace Tree Multiplier using Verilog**

**Description**

This project implements a Wallace Tree Multiplier using Verilog. The multiplier takes two 16-bit unsigned integers as input, and outputs a 32-bit unsigned integer as the product. The multiplier uses a series of full and half adders (the Wallace tree) to sum the partial products in stages until two numbers are left. The multiplier uses a carry-lookahead adder to perform the final addition.

**Design and Implementation**

The multiplier consists of six main stages: the partial product generation, the first reduction, the second reduction, the third reduction, the fourth reduction, and the final addition.

- The partial product generation stage uses the PP submodule to multiply each bit of A by each bit of B, and generate 16 partial products, each of 32 bits. The PP submodule uses a grid of AND gates to perform the multiplication.
- The first reduction stage uses five CSA submodules to reduce the number of partial products from 16 to 11, by adding three partial products at a time. The CSA submodule uses a full adder and a half adder to perform the carry-save addition, and outputs a sum and a carry, each of 32 bits.
- The second reduction stage uses three CSA submodules to reduce the number of partial products from 11 to 8, by adding three partial products at a time. The CSA submodule uses the same logic as the previous stage.
- The third reduction stage uses two CSA submodules to reduce the number of partial products from 8 to 6, by adding three partial products at a time. The CSA submodule uses the same logic as the previous stages.
- The fourth reduction stage uses two CSA submodules to reduce the number of partial products from 6 to 4, by adding two partial products at a time. The CSA submodule uses the same logic as the previous stages.
- The final addition stage uses the CLA submodule to add the remaining four partial products, and output the final product and the carry. The CLA submodule uses a carry-lookahead logic to perform the fast addition, and outputs a sum and a carry, each of 32 bits.

The multiplier uses a clock signal and a reset signal to synchronize and initialize the operations. The multiplier uses parameters to define the bit widths of the inputs and outputs. The multiplier uses wires to connect the submodules and the signals.

**Simulation and Testing**

The multiplier was simulated and tested using Vivado. A testbench was created to provide the input values, the clock signal, and the reset signal. The testbench also monitored the output values, the carry, and the internal signals. The testbench used random inputs to test the functionality and the correctness of the multiplier. The testbench also displayed the input values and the output values on a waveform viewer.

The simulation and testing results showed that the multiplier performed the multiplication correctly, and produced the expected output values and the carry. The relevant results are output in the output.txt file.
