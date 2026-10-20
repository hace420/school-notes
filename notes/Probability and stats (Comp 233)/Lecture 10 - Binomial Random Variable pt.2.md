# Poison Random Variable

```
Poisson distributions model rare events occurring among many opportunities.
```

> In general, let counts occur at random throughout an interval on the real line. If the interval can be divided into sub-intervals such that:

- The probability of more than 1 count in one sub-interval is 0; 
- The probability of 1 count in a sub-interval is the same for all sub-intervals, and proportional to the length of the sub-interval; 
- The count in each sub-interval is independent of counts in other sub-intervals.

![[Pasted image 20261020103126.png]]

## Approximating Binomial Probabilities

- In view of the limiting argument (where n goes to infinity), the Poisson Mass Function provides an excellent approximation to binomial probabilities in the case of large n and small p.
```
We simply set λ=np.
```

##### Example:
```
Suppose the probability that an item produced by a certain machine will be defective is 0.1. Find the probability that a sample of 10 items will contain at most one defective item. Assume that the quality of successive items is independent.
```

![[Pasted image 20261020103809.png]]

![[Pasted image 20261020103839.png]]

## Expectation and Variance of Poisson Mass Function

![[Pasted image 20261020104325.png]]

##### Example:
```
Suppose that the average number of accidents occurring weekly on a particular stretch of a highway equals 3. Calculate the probability that there is at most two accidents this week. 

• Let Nλ denote the number of accidents occurring on the stretch of highway in question during this week. 

Because it is reasonable to suppose that there are a large number of cars passing along that stretch, each having a small probability of being involved in an accident, the number of such accidents should be approximately Poisson distributed.
```

![[Pasted image 20261020104630.png]]

![[Pasted image 20261020104707.png]]

# Exponential Random Variable
## General Case

> • λ requests per minute --> λt requests within t minutes on average. 
> • That is the number of requests within t minutes is Poisson distributed with parameter λt.
> • If the time between 2 requests exceeds t minutes, then NO REQUEST ARRIVED WITHIN within t minutes.
>![[Pasted image 20261020105321.png]]

## The Exponential Density Function

>• Suppose counts in an interval on the number line follow Poisson Density Function with a mean of λ>0. 
>• Then the lengths of intervals between successive counts are said to be exponentially distributed with λ>0 
>![[Pasted image 20261020105610.png]]


### REVIEW
![[Pasted image 20261020105704.png]]


## General case cont.

- In general, for an exponential Density Function with λ>0, we have
![[Pasted image 20261020110038.png]]

##### Example:

```
Suppose that the number of miles that a car can run before its battery wears out is exponentially distributed with an average value of 10,000 miles. 

If a person desires to take a 5,000-mile trip, what is the probability that she will be able to complete her trip without having to replace her car battery?
```

SOL:
```
It follows, by the memoryless property of the exponential distribution, that the remaining lifetime (in thousands of miles) of the battery is exponential with parameter λ = 1/10 (since E[L] = 1/λ).
```

![[Pasted image 20261020110223.png]]

# Uniform Random Variable

## Uniform Density Function

> • As seen previously, a continuous RV is said to be uniformly distributed on [α, β] if its PDF is: 
> ![[Pasted image 20261020110613.png]]




