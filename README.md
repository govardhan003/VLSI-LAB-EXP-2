AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/165632778/64f9538e-6a2b-469e-85a7-19d5897b3f58)


Logic Diagram: 
![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/165632778/f16e5925-7f23-4414-a2d9-cb34aceaf8fa)


Logic Gates: verilod code: module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate); input a,b; output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate; and(andgate,a,b); or(orgate,a,b); xor(xorgate,a,b); nand(nandgate,a,b);
nor(norgate,a,b); xnor(xnorgate,a,b); not(notgate,a); endmodule out put: 324748953-591199a0-016e-40c2-8eff-374918e0c097
![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/165632778/262f10c0-3000-49c0-bea1-241e64aef736)


logic daigram: 

Half Adder: verilog code: module half_adder(Sum,carry,a,b); input a,b; output Sum,carry; assign Sum = a ^ b; assign carry = a & b; endmodule out put: 324749159-9c0dafdb-d179-4f52-b0f9-04c668ad427a
![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/165632778/dd9c5fa2-d34c-4fec-91e8-eb5372c9f61d)

logic daigram: 324749235-52c8feb1-fecd-4ec4-b200-7ca2b5030e3c

Full adder: verilog code: module fulladder(sum,cout,a,b,c); input a,b,c; output sum,cout; wire w1,w2,w3,w4,w5; xor x1(w1,a,b); xor x2(sum,w1,c); and a1(w2,a,b); and a2(w3,b,c); and a3(w4,a,c); or o1(w5,c1,c2); or o2(cout,w5,c3); endmodule out put : 324749296-a0ab6127-fd6f-4d2a-b84a-44fe31bb122e

logic daigram: 324749329-6b49afba-c40c-4c53-9811-a82b5c1a5fd1

Half Subtractor: verilog code: module half_sub(Diff,Borrow,a,b); input a,b; output Diff,Borrow; wire w1; not(w1,a); xor(Diff,a,b); and(Borrow,b,w1); endmodule out put: 324749374-54a47f64-fa15-4cd5-9205-0a9f1147a83e

logic daigrm: 324749398-dbbfe3ee-cf23-452c-ba83-6d2e51917e6f
![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/165632778/dfbef696-2db3-404f-a713-ed805d0a2629)

Full Subtractor: verilog code:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/165632778/10c85286-8b56-4ba9-8ce5-a8f18e8be62b)

module full_sub(borrow,diff,a,b,c); output borrow,diff; input a,b,c; wire w1,w4,w5,w6; xor (diff,a,b,c); not n1(w1,a); and a1(w4,w1,b); and a2(w5,w1,c); and a3(w6,b,c); or o1(borrow,w4,w5,w6); endmodule

out put: 324749487-e471cbc7-5212-45db-a861-552639ce4a43

logic daigram : 301406117-7385a408-40a5-4203-8050-b72818622d79

8 Bit Ripple Carry Adder: verilog code:

module rippe_adder(S, Cout, X, Y,Cin); input [7:0] X, Y;// Two 4-bit inputs input Cin; output [7:0] S; output Cout; wire w1, w2, w3, w4, w5, w6, w7; // instantiating 8 1-bit full adders in Verilog fulladder u1(S[0], w1,X[0], Y[0], Cin); fulladder u2(S[1], w2,X[1], Y[1], w1); fulladder u3(S[2], w3,X[2], Y[2], w2); fulladder u4(S[3], w4,X[3], Y[3], w3); fulladder u5(S[4], w5,X[4], Y[4], w4); fulladder u6(S[5], w6,X[5], Y[5], w5); fulladder u7(S[6], w7,X[6], Y[6], w6); fulladder u8(S[7], Cout,X[7], Y[7], w7); endmodule module fulladder(S, Co, X, Y, Ci); input X, Y, Ci; output S, Co; wire w1,w2,w3; //Structural code for one bit full adder xor G1(w1, X, Y); xor G2(S, w1, Ci); and G3(w2, w1, Ci); and G4(w3, X, Y); or G5(Co, w2, w3); endmodule out put: 324749539-b39f3593-9b6c-4fa6-b03f-23f2aed569cc
![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/165632778/4cfa95a4-796f-48d6-8553-69867d2db355)

RESULT: THUS THE LOGIC GATES,ADDERS,SUBTRACTORS VERILOG CODE IS SIMULATED USING VIVADO 2023.1 AND OUTPUT VERIFIED SUCCESSFULLY
