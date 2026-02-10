review of [[Lecture 3 - 2's compiliment]] and [[Lecture 4 - Error detection and correction]] quiz notebook
![[Pasted image 20260209190725.png]]

# Drawing of gates
review of [[Lecture 4 - Error detection and correction]]

![[Pasted image 20260209190634.png]]
![[Pasted image 20260209184912.png]]

# Normalized forms 

![[Pasted image 20260209183025.png]]

![[Pasted image 20260209184944.png]]
# Decoders

**takes binary number and gives out one specific output**
---> usually used for locating system memory

![[Pasted image 20260209185502.png]]
images show how 8 "options" could be selected using 3 inputs.(can be 4 inputs to 16 and even larger)

math is n-bit = 2^n so 4 inputs = 2^4 = 16 


# Multiplexers (Mux)

**Source lines decides which d line to choose(can be switched if s line is switched )**

![[Pasted image 20260209191258.png]]
![[Pasted image 20260209202435.png]]
# Working with multiple bits
**4 bit adder**
![[Pasted image 20260209192035.png]]

**for this image a3a2a1a0 + b3b2b1b0 = x3x2x1x0  (a3 + b3 = x3 with cin3 for carry)**

**for n bit adder**
![[Pasted image 20260209192301.png]]
the /4 means 4 wires so for a there is a0-a3 wires
**ALWAYS HAVE SAME # OF INPUTS TO OUTPUTS**

# Arithmetic Logic Unit (ALU)

Used to perform arithmetic and logic operations on one or two inputs 

Inputs: Two n-bit values A and B 
Outputs: One n-bit result X and various status flags

Input is usually fed from [[#Decoders]]

![[Pasted image 20260209192604.png]]
JAVA -->
![[Pasted image 20260209192629.png]]