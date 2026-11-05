
# Population Mean

- For a population of size N, its mean, µ, is given by (each x value may appear more than once)

![[Pasted image 20261105102432.png]]![[Pasted image 20261105102441.png]]

# Sample Mean

For a sample of size n, X1, X2, X3 , … , XN, the *sample mean* is given by (again, each X_i may appear more than once)

![[Pasted image 20261105102557.png]]


# The Sample Median

→ The *sample median*, MD, is the midpoint of the entire quantitative data array.

- To determine the median: 
1. Sort the data values. 
2. Pick the value in the middle

→ For n data values: 
	If n is odd, ![[Pasted image 20261105103141.png]]
	If n is even ![[Pasted image 20261105103201.png]]

> The sample median divides the data set into two subsets with equally many values in such a way that all values in the first subset do not exceed the value of the sample median, while all values in the second subset are greater than or equal to the sample median value

**median vs mean → median is more robust to outliers**
# The Sample Mode

- The sample mode is a value that has the highest frequency in a data set. 
- Defined for both qualitative and quantitative data. 
- A distribution may have one, more than one, or no sample mode at all. 
	→ If the respective RV is continuous, then the sample mode predicts where the respective PDF has a peak.

![[Pasted image 20261105104151.png]]


# Example for all 3 

**The following frequency table gives the values obtained in 40 rolls of a die.**

![[Pasted image 20261105104310.png]]

Find (a) the sample mean, (b) the sample median, and (c) the sample mode.

![[Pasted image 20261105104336.png]]


# Approximating the Sample Mean

![[Pasted image 20261105104533.png]]

> where Xj,m is the midpoint of class interval j, and Fj is the frequency of class j for all j = 1,…,k


#### Example:

![[Pasted image 20261105104620.png]]

→ Find the midpoint of each interval. Calculate the average age of an unemployed.

![[Pasted image 20261105104700.png]]


## Practical Considerations

→ here are three steps for computing a percentile. 
1. Sort the data from low to high 
2. Count the number of values (n) 
3. Select the p*(n+1)-th value.

→ You can't always be so lucky to have p*(n+1) be a nice whole number. Here are some contingencies. 
1. If p*(n+1) is not a whole number, then go halfway between the two adjacent numbers.
2. If p*(n+1) < 1, select the smallest value.
3. If p*(n+1) > n, select the largest value.


#### Example: 
![[Pasted image 20261105105115.png]]

# Sample Quartiles

- The sample 25th, 50th and 75th percentiles are called the sample 1st , 2nd and 3rd Quartiles, respectively.
- As their names suggest they split a data set into 4 parts with roughly equal number of values. 
- *Note: the Second Quartile is simply the median*



