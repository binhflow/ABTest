# AB Testing
Random sampling and implement AB Test by Permutation and Multivariate Test

## Test Description
**A/B Test Design**  

| Group          |   Algorithm |   Probability threshold  |  Notifications |
|----------------|-------------|--------------------------|----------------|
| C (Controlled) |   1         |   0.5                    |  No            | 
| A1             |   1         |   0.5                    |  Yes           |
| A2             |   2         |   0.5                    |  Yes           |
| A3             |   1         |   0.76                   |  Yes           |
| A4             |   2         |   0.76                   |  Yes           |


**Description**  
Multiple A/B Tests between A1, A2, A3, A4 and C (Controlled) to find the best combination  
Multivariate Test between A1, A2, A3, A4 to find the most important factors for dependent variable (conversion rate/sale)

**Metrics**  
Conversion rate 2 recommended products (remote shopping, fast checkout, general)  
Conversion rate new SnG users  
Total sales (remote shopping, fast checkout, general)  


## Random Sampling 
### Why sample before running a real test? 
- To know if your sample size is big enough
- To make sure your AB Testing coding is right 
- In case you have many metrics for AB Tests, run a pseudo test make sure sample size, test duration is good enough to cover all of them

## AB Test by Permutation
### Why choose permutation test for A/B Testing? 
- It works on both continuous and discrete variables   
- Regardless of variable distribution, permutation works  

-> Ease of your mind, no need to test for normality or use different test method for different characteristics of variables.  
The cost is only extra few seconds on computing permutation for each test.

### Permutation Test Idea 
The idea is that for null hypothesis, conversion rates between treatment and controlled group are the same, share same distribution.
We could compute the true conversion rates by replicating thousands of new treatment and controlled groups after resampling/permutating, then see if the observation is critical enough to reject null hypothesis. 
Details and guidelines is in the notebook.

## Multivariate Test 
After choosing the winner from multiple A/B Tests, multivariate test is for finding which factors make a winner.   
For categorical variable, I recommended Chi-Square Test   
For continuous/numeric variable, I recommended ANOVA Test   

## References 
<https://towardsdatascience.com/running-chi-square-tests-in-python-with-die-roll-data-b9903817c51b>  
<https://www.jwilber.me/permutationtest/>  
<https://www.datacamp.com/courses/statistical-thinking-in-python-part-2> A lot of permutation code is modified from this course
