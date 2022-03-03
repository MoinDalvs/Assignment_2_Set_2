# Topics: Normal distribution, Functions of Random Variables

1.	The time required for servicing transmissions is normally distributed with  = 45 minutes and  = 8 minutes. The service manager plans to have work begin on the transmission of a customer’s car 10 minutes after the car is dropped off and the customer is told that the car will be ready within 1 hour from drop-off. What is the probability that the service manager cannot meet his commitment? 

A.	0.3875   
B.	0.2676   
C.	0.5   
D.	0.6987 \
Ans: ‘B’ 
 """the serving work will begin after 10 min of drop off so 45+10 
which will now take more than the usual time so new mew is 55 minutes 
and the probability that it will take more than 1 hour to complete""""
mew = 55
std = 8
q1 = 1-stats.norm.cdf(60, loc = mew, scale = std)
q1 = 0.2659
The probability that the service manager cannot meet his commitment is 0.2659


2.	The current age (in years) of 400 clerical employees at an insurance claims processing center is normally distributed with mean  = 38 and Standard deviation  =6. For each statement below, please specify True/False. If false, briefly explain why.
A.	More employees at the processing center are older than 44 than between 38 and 44.\
Ans: False.
Because the probability for employees at the processing center are more between 38 and 44 than older than 44.
mean = 38
std1 = 6
q2_lessthan_38 = stats.norm.cdf(38, loc = mean, scale = std1)
q2_lessthan_38 = 0.5
q2_less_than_44 = stats.norm.cdf(44, loc = mean,  scale = std1)
q2_less_than_44 = 0.841
q2_betweeen_38_and_44 = q2_less_than_44 - q2_lessthan_38
print('The probability of employee age between 38 and 44 is',np.round(q2_betweeen_38_and_44*100,2),'%')
The probability of employee age between 38 and 44 is 34.13 %
q2_morethan_44 = 1-stats.norm.cdf(44, loc = mean, scale = std1)
print('The probability of employee age more than 44 is',np.round(q2_morethan_44*100,2),'%')
The probability of employee age more than 44 is 15.87 %
true_or_false = (q2_morethan_44 > q2_betweeen_38_and_44)
print('Answer:',true_or_false)\
Answer: False

B.	A training program for employees under the age of 30 at the center would be expected to attract about 36 employees.\
Ans: True.
q2b = stats.norm.cdf(30, loc = mean, scale = std1)*100
print('A training program for employees under the age of 30 at the center would be expected to attract about',np.round((q2b*400)/100,0),'employees')
A training program for employees under the age of 30 at the center would be expected to attract about 36.0 employees

3.	If X1 ~ N(μ, σ2) and X2 ~ N(μ, σ2) are iid normal random variables, then what is the difference between 2 X1 and X1 + X2? Discuss both their distributions and parameters.\       
Ans:  
The Normal Distribution has its link with the Central Limit Theorem, which states that ‘Any large sum of independent identically distribution random variables are approximately Normal then
(X1 + X2) and (2X1) tends to have Normal distribution only If X1 and X2 are i.i.d and n is Large. 

The Difference between 2X1 and (X1 + X2) is the magnitude they hold of two different sample subsets (X1 and X2) from the same source(population). 
X1 and X2 can be a different subset of a sample from a similar source (population) but 
If X1 ~ N(μ, σ2)  then, 2 X1 ~ N(2 μ, 4 σ2 ) 
If X1 ~ N(μ, σ2) and X2 ~ N(μ, σ2) are iid normal random variables then 
(X1 + X2)~N(μ+ μ,  σ2+  σ2)~(2 μ, 2 σ2)
Hence, 2X1 – (X1+X2) ~(2 μ – 2 μ, 4 σ2  + 2σ2 )
The distribution remains the same for every sample subset of similar source, it tends to fall under Normal distribution and slight deviations in parameters.

The Normal distribution has two parameters, the mean, µ, and the variance, σ2.
 µ and σ2satisfy −∞ < µ < ∞, σ2> 0. We write X ∼ Normal (µ, σ2) or X ∼ N(µ, σ2 ).

4.	Let X ~ N(100, 202). Find two values, a and b, symmetric about the mean, such that the probability of the random variable taking a value between them is 0.99. \

A.	90.5, 105.9 \
B.	80.2, 119.8 \
C.	22, 78 \
D.	48.5, 151.5\ 
E.	90.1, 109.9\
Ans:  D. 
print("""The two values of a and b, symmetric about the mean, 
      are such that the probability of the random variable 
      taking a value between them is 0.99:""",np.round(stats.norm.interval(0.99, loc = 100, scale = 20),1))
The two values of a and b, symmetric about the mean, 
      are such that the probability of the random variable 
      taking a value between them is 0.99: [ 48.5 151.5]


5.	Consider a company that has two different divisions. The annual profits from the two divisions are independent and have distributions Profit1 ~ N(5, 32) and Profit2 ~ N(7, 42) respectively. Both the profits are in $ Million. Answer the following questions about the total profit of the company in Rupees. Assume that $1 = Rs. 45\

A.	Specify a Rupee range (centered on the mean) such that it contains 95% probability for the annual profit of the company.\
Ans: Rupee ranges in between [9.9 to 98.1] Crore Rupees, 95% of the time for the Annual Profit of the Company.

B.	Specify the 5th percentile of profit (in Rupees) for the company\
Ans: The 5TH Percentile of profit for the company is 17 Crore Rupees

C.	Which of the two divisions has a larger probability of making a loss in a given year?\
Ans: The Division #2 (Profit2 ~ N(7, 42) ) has a larger probability of making a loss in a given year
