# P2P_Investment_Strategies


The exercise is aimed at predicting and assessing the performance of different investment strategies on a P2P loan portfolio, using different machine learning techniques
 
The data used was from Lending Club, covering a period of 12 years from 2007-2018 and can be sourced here https://www.kaggle.com/wordsforthewise/lending-club/ 
 
The data is made of 605,374 loans and 33 features (e.g. id, loan_amt, int_rate, grade, loan_length etc.)
 
Three investment approaches are considered. 
Random strategy – where an investor randomly selects the loans to invest in 
 
Default strategy – Here, the strategy involves predicting the probability of default (PD) for the loans, the loans are ranked based on their PD and the investor chooses those with the lowest PD
 
Return-based – The expected return on a loan is predicted and those with the highest expected returns are selected
 
 
Three cases of annual returns were also computed. 
            Return 1 = (X2 – X1)/X1 *12/t
 
Return 2 = (X2 – X1)/X1 * 12/m 
 
Return 3* = (S - X1) / X1  * 12/t
 
Where; 
X1 = the initial investment
X2 = final payment
t = nominal length of the loan
m = actual lifetime of the loan
S = X2/m * ((1+J)m – 1) /J * (1+J)t – m
J = the interest rate on the loan
12 is the number of months per year
 
* Return 3 assumes a general case where the investor re-invests all monthly payments earned from the platform, assuming that the payments are uniformly distributed over the term of the loan 
 
For the return-based strategy, a Ridge regression model and Neural Network were used to estimate the return and the top 100 portfolios were selected
 
For the default-based strategy, three models were adopted in estimating the PD; 
            Tree Model
            Logit Model
            Random Forest Model
Comparing the result of the three strategies, the predicted returns using the Logit Model under the Default-based strategy gave the highest returns and most quality loans
