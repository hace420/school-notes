
cont of [[Lecture 1 - Probability Theory]] (making up for missed class)


# Counting Rules

A salesperson needs to get from city A to city B and then to city C. Three roads lead from A to B, and two lead from B to C. How many different routes can the salesperson take to accomplish their task?

![[Pasted image 20260915103435.png]]

**SOLUTION**

The event of getting from A to C is a sequence of two events. 
• The first (from A to B) can occur in 3 different ways. 
• The second (from B to C) can occur in 2 different ways.
**• Thus, getting from A to C can occur in 3 × 2 = 6 different ways**
## Multiplication rule

In a sequence of two experiments, if the first experiment can occur in m different ways and the second one can occur in n different ways, then the sequence of outcomes can occur in mn different ways.
**• The rule is sometimes called the Basic Principle of Counting**

12 character password example: Each character can be: 
• 26 lowercase letters, 26 uppercase letters, 10 digits or 10 special symbols 
Each positions (event) has 26+26+10+10 = 72 outcomes. 
**So, total number of outcomes = $72^{12}$**

## Permutations

The number of repetition-free permutations (linear arrangements) of size r from a set of n distinct objects is given by

![[Pasted image 20260915104205.png]]

**NOTE 0! = 1**

Example:

What is the number of (possibly meaningless) words that are made up of all the letters in the word “computing”?

Words made up of the letters in “computing” are all possible permutations of the letters. 
• Thus, the number of such words is (n = 9; r = 9):

![[Pasted image 20260915104351.png]]


## Combinations

![[Pasted image 20260915105736.png]]


![[Pasted image 20260915105746.png]]


A fair coin is tossed 8 times, what is the probability of getting exactly 4 heads and at least 4 heads

By the multiplication rule, N(S) = 2×2×…×2 = $2^8$= 256.

![[Pasted image 20260915110050.png]]

![[Pasted image 20260915110153.png]]


# Probabilities 2

If a coin is flipped 8 times, find the probability that heads appear at least four times.

![[Pasted image 20260915110313.png]]


## Pascal triangle 

![[Pasted image 20260915110558.png]]



