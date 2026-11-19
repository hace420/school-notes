# Why Estimate Variance?
*Question: Which system is more predictable? *

Variance measures consistency. 
- Server A latency (ms): 98, 100, 101, 99, 102 
- Server B latency (ms): 20, 180, 130, 50, 120 
- Both have similar average latency. 
- Server A is much more consistent. 

*Low variance = predictable; 
High variance = unpredictable*

# Distribution of the Sample Variance

![[Pasted image 20261119112112.png]]

# The Chi-Square Distribution
*Properties:* 
- Always positive 
- Right-skewed 
- Depends on degrees of freedom 
- df = n − 1 
- Values cannot be negative. Why? 
- Variance is: σ² = Σ(x−μ)² / N 
- Every term is squared. Therefore: σ² ≥ 0 
- This is why the Chi-Square distribution exists only on the positive axis.

## Confidence Intervals on $\sigma^2$ 

- Thus, a two-sided (1-$\alpha$)-confidence interval on $\sigma^2$ is given by
![[Pasted image 20261119112429.png]]

- Hence a 100(1 − α) percent confidence interval for $\sigma^2$ is
![[Pasted image 20261119112458.png]]

## One-Sided Confidence Intervals on $\sigma^2$

![[Pasted image 20261119112530.png]]




