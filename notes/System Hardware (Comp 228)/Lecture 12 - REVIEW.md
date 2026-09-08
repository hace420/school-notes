
kmaps minimal
no boolean algebra
no booths multipllication

NEED TO STUDY

binary
changing bases
negative
ign extension
sign magnitude
fracto=ional numbers
floating point
ascii / utf8

error detcion / corrwction
parrity bit
checksum
cyclic redundancy check
correction : 2d parity
hamming distance
gray codes

DIGITAL LOGIC

AND OR NOT GATES
made with transistors or tubes or relays
truth tabke of logic de morgans
from truth table to circuit
combinational logic multiplie ouptuts hald adder xor 
full adder

decoder
multipler
handling multiple bits
log gate stacks for bit-wise operations n bits would need to go on to  n different gates
tri state buffer 

ALU
inputs two n bit valus a and b
outputs one n bit ressult
each operation is only combinational logic 
operation selected by control lines into alu
control lines contorl a mux
mux inputs are operaiton outputs
alu output is mux ouput
# Diagram

![[Pasted image 20260413183118.png]]
# 
sequenetial circuits
latches level triggered
r-s latch
d latch
flip flops edge triggered 
r-s 
d
j-k 
t

timming diagrams
control lines clock load reset

Registers
 n flip flops bundled together to support n -bit storage
 ![[Pasted image 20260413185706.png]]
 mar address for memory 
mdr actual data at adress

1 bus inputs and outputs on same bus alu has dedicated registers
2 bus  inputs one bus outputs another bus  input bus -> alu -> output bus
3 bus inputs one bus 2 busses for outputs with 2 buffers

![[Pasted image 20260413193059.png]]
![[Pasted image 20260413193720.png]]


Control unit

Assembly code
Fetch, Decode, Execute; Instruction Pipeline
Address Instruction Format, # of addresses, # of registers, size 
Addressing Modes: Immediate, Direct, Indirect, Register, Indexed


Memory is an array of register like components
Size looks like 64x4 meaning 64 slots or addresses of 4 bits each
▶ In this example there are 6 A lines (26 = 64) and 4 D and Q lines



