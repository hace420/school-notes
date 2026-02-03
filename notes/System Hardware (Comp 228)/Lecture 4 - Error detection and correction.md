# Detecting

--> **usually done by adding redundant information**

parity bit = **can detect single bit error** (add a bit at the start of word to say if there are even number of ones or odd number)

checksum = **detect large number of bit errors** (group number into categories and make sure a certain rule is followed ie : if we add all numbers then mod10 should give mod0 and if not there was error)

Cyclic redundancy check =  **detect long run errors** (uses mod 2 division to check remainder and if remainder is different something went wrong)

--> **ALL ALLOW DETECTION BUT NOT WHERE ERROR IS OR HOW TO FIX**

# Correcting

--> **Usually requesting data again and again until we get the right data is usually quicker**

When data cannot be repeated: 
- 2D Parity: arrange the data into a grid, calculate the parity for each row and column If there is an error, one row and column will have an error, intersection is the error. (for example: having even number ones in columns and rows )
- Hamming Codes: Each position belongs to a unique set of parity, if only those parity bits are wrong and no other, that is the position in error (**SEE YOUTUBE**)

**THESE ONLY WORK FOR SINGLE BIT ERRORS**

### Hamming distance

--> The number of bits that change is known as the Hamming distance.

Going from 7 to 8 involves 4 bits to change 00000111 → 00001000

Gray codes are a solution where all adjacent values only differ by 1 bit 
--> This solves he hamming distance problem at the cost of not following the positional number system

# Digital Logic

done in notebook

![[Pasted image 20260202194836.png]]

![[Pasted image 20260202195117.png]]



