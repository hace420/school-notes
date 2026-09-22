
# Tree Diagrams

Example: Consider an experiment where a die is cast followed by flipping a coin. The tree diagram charts of all the possible outcomes of the experiment
![[Pasted image 20260922101836.png]]

There are two identical bottles.
• One contains 2 green balls and 1 red ball, the other bottle contains 2 red balls. 
• Experiment: A bottle is selected at random and then a ball is drawn from it. 
• What is the probability that the ball is red?

Let I and II stand, respectively, for the events that the first bottle and the second bottle were selected. Hence, P(I) = P(II) = 0.5. The chances to draw a red ball from Bottle 1 are 1/3. For Bottle 2 these chances are 1. So…

![[Pasted image 20260922102250.png]]


# Total Probability Rule: General Case.
part 2 of [[Lecture 3 - Conditional Probability#Total Probability Rule]]

![[Pasted image 20260922102654.png]]

**A bottle is selected at random and a ball is drawn. The ball is red. What are the chances that it was drawn from the first bottle?**
![[Pasted image 20260922103513.png]]

# Baye's Rule

![[Pasted image 20260922104236.png]]

![[Pasted image 20260922104150.png]]

![[Pasted image 20260922104402.png]]

EXAMPLE: 
In semiconductor manufacturing, a chip is subject to high, medium or low contamination levels. The probability of chip failure is 0.1, if contamination level is high, 0.01, if it is medium, and 0.001, if it is low. 20% of chips are subject to high and 30% to medium contamination levels. If a chip causes a product failure, find the probability that the chip was subject to high contamination levels.

Let L, M and H stand for the events that contamination levels were low, medium and high, respectively. Then
		P(L) = 0.5, P(M) = 0.3, P(H) = 0.2
Let F be the event that a chip causes a failure. Then
		P(F|L) = 0.001, P(F|M) = 0.01, P(F|H) =0.1
Then the total probability rule implies
		P(F) = 0.0005 + 0.003 + 0.02 = 0.0235
![[Pasted image 20260922104729.png]]


# Independent Events

• In such a case it is natural to call events N2 and K1 independent. Learning one event gives no info about the other 
• In general, two events, E and F, are called independent if
![[Pasted image 20260922110249.png]]


• Do not be confused between mutually exclusive and independent events! 
• If two events, E and F, are mutually exclusive, it means that if E occurs, then F cannot occur and vice-versa.
• If two events, E and F, are independent, then it means that occurrence of F does not depend on occurrence of E and vice versa. 
• For mutually exclusive events, we add probabilities and for independent events we multiply. 

EXAMPLE:

A system is composed of n separate components. 
• It is parallel if the system functions when at least one component does. 
• It is also assumed that the operation of one component does not affect the other ones. 
• Suppose that the probability that the k-th component functions is pk. Thus the probability that the k-th component fails is 1 - pk . 
• Find the probability that the system functions.

![[Pasted image 20260922110414.png]]

![[Pasted image 20260922110432.png]]·