Study on MSCD Cases and Their Medical Expenditures Attributable to Smoking: An Analysis of the 2009 Medical Expenditures Panel Survey
================
Xiran Wang
December 6, 2019

I.Analysis Goal
===============

The analysis goal in this project is to estimate the smoking-attributable costs of treating major smoking-caused diseases. The fundamental idea in this project can be explained by the following formula,

To achieve the ultimate goal, estimating the smoking attributable expenditure, the two relationships are analyzed in this project. Firstly, the project evaluates the relationship between having MSCD and smoking behavior. Secondly, investigate the connection between smoking caused disease (MSCD) and their medical cost. In the first section of the analysis, the study target is to estimate the smoking attributable risk of having MSCD, which leads to model the probability of having MSCD given smoking or non-smoking behavior. Therefore, in the project, the logistic model called the disease model is implemented.

In the second section, the MSCD cases and their medical expenditures need to be investigated. In other word, estimate how much medical expenditures that is contributed by MSCD. Hence, the expenditure model is built for solve this question. In this particular analysis, a two-part model will be employed. In the first part of the expenditure model, it estimates probability of occurring any medical. In this case, logistic regression is implemented to model the probability given smoking-related disease and non-disease status. In the second part, the target is to estimate the size of medical expenditure given there already is a positive medical expenditure. Accordingly, the linear regression is used. The following is the analysis outline that the project will be structured.

II.Analysis Outline
===================

### 1.The Disease Model( Logistic Regession )

### 2.The Expenditure Model( Two-Part Model )

**Linear Regression Part:**

**Logistic Regression Part:**

**Combination Two Parts:**

### 3.Final Estimation

*Notions:* 
*Med.Exp - total medical expenditure*
*MSCD.AFE - MSCD-attributable fraction in total medical expenditure*
**i* - ith cluster*
**s**m**o**k**e*<sub>*i*</sub> - smoke=0, i never smokes; smoke=1 i is a former/current smoker*
**X*<sub>*i*</sub> - the other featuers for ith cluster *
*MSCD - smoking caused disease*
*SAE - smoking-attributable medical expenditure*
*SAEF - smoking-attributable medical expenditure fractions*

III.Data Analysis
=================

Part I: Diesase Model
---------------------

### *1.Logistic Regression*

The MSCD logistic regression has variables, such that (1) the binary variable of smoking; (2) key characteristics including age, gender; and (3) additional covariates including poverty status, education years. Moreover, Age is only continious variable in this model. For other variables, such as gender (male=1,female=0), smoke(yes=1,no=0), poverty(yes=1,no=0) are all binary variables. But the education has 4 levels, "20"" stands for less than high school, "21"" is high school, "22"" is 4-years collage, and "23"" means more than 4 years collage.

The logistics regression is meant to model the relationship between the smoking behavior and risk of getting MSCD disease. in the end of this part, the smoking attributable risk will be estimate in different age groups by gender. Based on the attributable risks, for both female and male, the attributable risks decreases as age increases. Given the same age for female and male, male has higher expected attributable risks, which means that male’s the risk of getting disease (MSCD=1) decreases more than female if they had not had smoking habit. Such that, at age 40, the expected attributable risk is 35% for females who smoke, and the true attributable risk will be fluctuating within 7% according to the expected risk value. While, the expected attributed risk is about the same for males who smoke, there are also approximate 7% fluctuation for the true attributed risk. Moreover, at age 80, the attributable risk is decreasing to 26% for females and 23% for males.

Part II: The Expenditure Model
------------------------------

*E*(*E**x**p*.|*M**S**C**D* = 1)=*P*(*E**x**p*.&gt;0|*M**S**C**D* = 1)\**E*(*E**x**p*.|*E**x**p*.&gt;0, *M**S**C**D* = 1)

*E*(*E**x**p*.|*M**S**C**D* = 0)=*P*(*E**x**p*.&gt;0|*M**S**C**D* = 0)\**E*(*E**x**p*.|*E**x**p*.&gt;0, *M**S**C**D* = 0)
 This expenditure model which is also called two-part model estimates the relative size of medical expenditures among persons with vs. without major smoking-caused disease. The following formula shows the basic idea of the two-part model. According to the formulas, to calculate the expected medical expenditure given MSCD or non-MSCD, it needs to model the expected medical expenditure given a positive medical expenditure and MSCD status, as well as probability of occurring any positive medical expenditure given MSCD status.Therefore, two models are implemented to analyze the expectation and the probability in this expenditure model, so called two-part model.

### *1.Linear Regression Model*

The linear regression model is to estimate the size of logged( with base 10) medical expenditure given the occurring of positive medcial expenditures and MSCD status. This regression model incorporates, (1)demographics variables: age (age in years), and gender (Male=1; Female=0); (2)Socioeconomic status (SES): education (years of education);and (3)poverty (Poor=1; Not poor=0); (3)Disease: major smoking-caused diseased (MSCD: Yes=1; No=0). The model linear regression modal and each variable’s corresponding coefficient are showed below. Based on the p values for ecah variable, All variables are significant for the model at 0.05 significant level.

*E*\[*l**o**g*<sub>10</sub>(*M**e**d**i**c**a**l* *E**x**p*.)\]=*β*<sub>0</sub> + *β*<sub>1</sub>*A**g**e* + *β*<sub>2</sub>*G**e**n**d**e**r* + *β*<sub>3</sub>*A**g**e* × *M**S**C**D* + *β*<sub>4</sub>*P**o**v**e**r**t**y* + *β*<sub>5</sub>*E**d**u**c**a**t**i**o**n* + *β*<sub>6</sub>*M**S**C**D*

From the linear regression above, it is able to estimate the mean medical expenditures given a occurring positive medical costs in different age groups by gender. Table4 and Table5 reveal estimated mean of medical expenditure given positive medical cost and its differences for male and female in different age groups. According to Table 4, For both male and female the estimated expenditures are more and more as age increase. To be noticed, the female's medical cost given MSCD=1 is significantly higher than male when hold the other covariate variables unchanged. Not surprisingly, differences of medical cost for female who smoke and don't smoke are overall larger than male at different age.

### *2.Logistic Regression*

This logistic regression explains the relationship between have MSCD disease and occurring any positive medical expenditures. It models the probability of occurring the positive medical expenditures given MSCD diseases status.

From the logistic regression, the probability for people to any positive cost given MSCD is quite higher than people who don’t have MSCD. But obviously, this difference is smaller when people get older. For example, in table7, for male from age 40 to age 50, the probability of having positive medical cost given MSCD is about 0.953 while with same condition but MSCD=0, the probability has only 0.791. but for male in the age group 70+ years old, the probability of having positive expenditure given MSCD=1 is 0.986 and the non-MSCD has 0.93. For female after 40 years old, the probabilities of having positive medical expenditure are above 0.90 no matter what MSCD condition is. Moreover, reasonably, this positive expenditure probability is overall smaller in population under age 40.

### *3.Conbine Two-part expenditure models*

Combine probability model and expected medical expenditure model, it will provide the estimated mean of medical expenditure given MSCD status without positive cost as condition. The Table 8 and 9 provide the estimated medical expenditure given MSCD status for male and female.
*E*(*E**x**p*.|*M**S**C**D* = 1)=*P*(*E**x**p*.&gt;0|*M**S**C**D* = 1)×*E*(*E**x**p*.|*E**x**p* &gt; 0, *M**S**C**D* = 1)+0 × (1 − *P*(*E**x**p*.&gt;0|*M**S**C**D* = 1))

*E*(*E**x**p*.|*M**S**C**D* = 0)=*P*(*E**x**p*.&gt;0|*M**S**C**D* = 0)×*E*(*E**x**p*.|*E**x**p* &gt; 0, *M**S**C**D* = 1)+0 × (1 − *P*(*E**x**p*.&gt;0|*M**S**C**D* = 0))

$$Disease\\,Attributable\\, Fraction\\, in\\,  Exp. = \\frac{E(Exp.|MSCD=1 )-E(Exp.|MSCD=0)}{E(Exp.|MSCD=1 )}$$

For male population, estimated medical cost has dramatically increase as age increase for both MSCD and non-MSCD population. From age 40 to age 80, the estimated expenditure increases approximate 5 times for MSCD male population and more than 10 times for non-MSCD male population. Nevertheless, the smoking caused disease fraction to medical expenditure is decreasing when people get old. The risk is 0.91 at age 40 for male, decrease to 0.74 at age 80. For female population the imprecise trend is pretty much same as male population’s. but the female population has generally large medical expenditures given MSCD=0 than male’s, at age 80, the expenditure given MSCD=1 reaches 24,000 USD. But same age female without MSCD has only about 6,300 USD.

Part III: Final Estimation
--------------------------

### *1.Combind the Disease Model and the Expenditure Model*

Finally, based on the estimated smoking attributable risk and smoking-related disease attributable fraction to medical expenditure, it concludes that both for male and female population, the smoking habit has significant contribution on medical expenditures, and this contribution is decreasing as people get older. The smoking attribute medical expenditure fraction is 0.31 for people who are 40 to 50 years old. It decreases to 0.18 for female and male respectively with age 81 and older. Yet, the expected smoking attributable medical expenditure is more and more when male smoker getting older, it makes sense since the total medical expenditure of older population to treat MSCD is overall more than younger male populations. For female, the most smoking attributable medical cost occurring during age 51-60, then the trend goes down significantly, there are about 2,651 USD and 2,439 USD medical costs that are attributable to smoking behavior at age group 71-80 and 80+.

*S**m**o**k**i**n**g* *A**t**t**r*. *M**e**d*. *E**x**p*.=∑*M**S**C**D*<sub>*i*</sub> × *T**o**t**a**l* *E**x**p*<sub>*i*</sub> × *S**m**o**k**i**n**g* *A**t**t**r*.*R**i**s**k*<sub>*i*</sub> × *M**S**C**D* *A**t**t**r*.*F**r**a**c**t**i**o**n* *i**n* *M**e**d*.*E**x**p*<sub>*i*</sub>

$$
Smoking\\, Attr.\\,  Med.\\, Exp.\\, Fraction= \\frac{Smoking\\, Attr.\\,  Med.\\, Exp\_i }{\\sum{MSCD\_i}\\times Exp\_i}
$$
