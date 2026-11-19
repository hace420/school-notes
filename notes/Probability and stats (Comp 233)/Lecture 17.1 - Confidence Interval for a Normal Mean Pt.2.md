
# One-Sided Confidence Intervals: The Main Idea

→ Sometimes we only care about one direction. 

Example 1: 
Is the average chatbot latency LESS than a target value? 

Example 2: 
Is the average GPU lifetime GREATER than a guaranteed minimum?

## Upper Confidence Bound

*Used when asking: *
- How large could the true population mean be? 
- Mathematically: μ < U 

*Interpretation:* 
-  We are 95% confident that the true mean is less than U. 

*Examples:*
- Maximum expected chatbot latency 
- Maximum packet transmission delay 
- Maximum average API response time 

*Since only ONE tail contains the remaining 5%,* 
- we use 1.645 instead of 1.96.

### Upper One-Sided Confidence Interval

![[Pasted image 20261119105141.png]]

## Lower Confidence Bound

*Used when asking:* 
- How small could the true population mean be? 
- Mathematically: μ > L 

*Interpretation:* 
- We are 95% confident that the true mean is greater than L.

*Examples:* 
- Minimum GPU lifetime 
- Minimum system reliability 
- Minimum battery life

### Lower One-Sided Confidence Interval

![[Pasted image 20261119105204.png]]

##### Example:

- Therefore, an observed response time can be modeled as is X = μ + N where N, representing noise, is normally distributed with mean 0 and variance 4. 
- To obtain a more reliable estimate of the true average response time, the same API endpoint is queried 9 times.
- Suppose the successive response times are 5, 8.5, 12, 15, 7, 9, 7.5, 6.5, 10.5 
- Construct the following confidence intervals:
- a) A 95 percent two-sided confidence interval estimate of μ
- b) A 99 percent two-sided confidence interval estimate of μ
- c) A 95 percent one-sided upper confidence estimate of μ 
- d) And a 95 percent one-sided lower confidence estimate of μ 

![[Pasted image 20261119105852.png]]![[Pasted image 20261119105859.png]]![[Pasted image 20261119105907.png]]


