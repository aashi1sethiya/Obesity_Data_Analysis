# obesity_data_analysis
What fuels the escalating obesity rates in Latin America, and how can data analytics help discover insights about the contributing factors? 

##Obesity Dataset Analysis

#Backdrop and Context:
The World Health Organization classifies a BMI ≥ 25 as overweight and a BMI ≥ 30 as obesity in adults. It is projected that by 2030, the proportion of individuals classified as obese or overweight in Latin America and the Caribbean will rise to 81.9%. 

#Research about obesity in Latin America:
Kain et al (2003) state that several factors such as poor nutrition, socioeconomic causes, and a sedentary lifestyle have contributed to the rise in obesity levels in the region. 
A 2019 study by Jiwani et al. found that obesity prevalence is on the rise in the region, with pronounced increases in rural areas and disadvantaged groups, as well as in affluent, urban populations.  
In a study of adults from 8 Latin American nations, deVicto et al (2023) explored how sedentary time and physical activity affected obesity indicators. 
The effect of genetic factors on obesity in Latin America was studied by Guevara-Ramírez et al (2022). 



#Unveiling Obesity Trends in Latin America
Research Question:
What fuels the escalating obesity rates in Latin America, and how can data analytics help discover insights about the contributing factors? 


Dataset Description:
The dataset included individuals from  Mexico, Peru, and Colombia,  with diverse age groups and lifestyles, which helped us understand the interplay of various factors. 

Survey Methodology:
The dataset authors employed a web-based survey and synthetic techniques to  gather 17 attributes and 2111 records, offering a holistic view of dietary habits, physical conditions, and socio-demographics.


      COLOMBIA 	

                 23.9% 
       PERU                            MEXICO
           
          21.1%                                            30.6%
Prevalence of Obesity  

COLOMBIA
PERU
MEXICO

Variables
Variable
Age
Height (in meters)
Weight (in kgs)
Continuous
Variable
Categories
Gender
Female/Male
Family history of overweight
Yes/No
Calorie Consumption Monitoring
Yes/No
Frequent high-caloric food
Yes/No
Smoke
Yes/No
Binary
Variable
Categories
Frequency of consumption of vegetables (FCVC)
Never/ Sometimes/
Always
Number of main meals (NCP)

Between 1 and 2/ Three/ More than three
Consumption of alcohol (CALC)

I do not drink/ Sometimes/Frequently/Always
Consumption of food between meals (CAEC)

No/ Sometimes/ Frequently /Always
Daily water consumption (CH2O)

Less than a liter/Between 1 and 2 L/More than 2 L
Time using technology devices (TUE)
0-2 hours/ 3-5 hours / > 5 hours
Transportation used
Public Transportation/Automobiles/Bike/Motorbike/Walking
Physical activity frequency (FAF)
I do not have/
1 or 2 days/ 2 or 4 days/4 or 5 days
NObesity (NObeyesdad)
Insufficient Weight, Normal Weight, Overweight Level I, Overweight Level II, Obesity Type I, Obesity Type II and Obesity Type III
Categorical 

Data Preparation
Issues with the dataset
The dataset did not have any missing data in any of the columns.
However, there were decimal values for many of the variables, even for the categorical ones (probably because a major part of the data was generated synthetically).
This posed a problem in analyzing the dataset. 
How was the data handled?
Therefore, to simplify the data for the ease of performing analysis, the values with decimals were rounded off to the nearest whole number. 
This was useful in obtaining well defined categories for the categorical variables. 
The new variables obtained were re-coded accordingly with a different name. 

  Exploratory Data Analysis

Descriptive statistics to understand the distribution of weight of the sample population
How many people have a positive family history of overweight? 
What are the different modes of transportation used, and what is their distribution? 
What is the distribution of individuals across different BMI categories?
What is the mean weight of people who monitor their calorie consumption as compared to those who do not?






Descriptive Statistics 
SAS Procedure Used:  PROC UNIVARIATE

Since Mean > Median > Mode:
Weight is slightly skewed to the right.

Mean
86.58 kgs
Median
83 kgs
Mode
80 kgs

All 3 tests for normality have a p value 
< 0.05

Therefore, H0 is rejected and H1 is accepted i.e Weight is not distributed normally. 


Descriptive Statistics

SAS Procedure used : PROC FREQ
81.76 % (1,726 people) had a positive family history.

18.24 % (385 people) did not have a family history.

Descriptive Statistics
SAS Procedure used :
PROC GCHART   

Results:

74.85 % people used public transportation

21.65 % people used automobiles

3.51 % people used other modes of transportation (i.e motorbikes, bikes, and walking)

Descriptive Statistics
The majority of the people in the dataset belonged to the ‘Obese’ category (~ 45 %).
Obese : BMI >= 30 

SAS Procedure Used : PROC GCHART

Descriptive Statistics
SAS Procedure Used : PROC SGPLOT , PROC MEANS


People who did not monitor their calorie consumption had a higher mean weight (87.7 kgs) compared to those who did (62.3 kgs).


Hypothesis testing:
Is there a potential association between consuming food between meals and the level of obesity (BMI category)? 


H0 = The variables CAEC and BMI_category are independent of each other


H1 = The variables CAEC and BMI_category are dependent on each other

Chi-square test
SAS Procedure Used : PROC FREQ chisq expected

The chi-square test yielded a highly significant result ( p < 0.0001), indicating a strong association between CAEC and BMI_category.

This means that H1 is accepted :  
CAEC and BMI_category are dependent on each other
There is a relationship between the consumption of food between meals and the level of obesity


Key Findings and Interpretation:





Hypothesis Testing:

Is there a potential association between frequent consumption of high calorie food and family history of overweight?


H0 = Frequent consumption of high calorie food and family history of overweight are independent of each other

H1 =  Frequent consumption of high calorie food and family history of overweight are dependent on each other


Chi square test, Odds Ratio, Relative Risk
SAS Procedure Used : 
PROC FREQ , chisq, relrisk

Measure
Value
Interpretation
p-value
< 0.0001
Null hypothesis is rejected, which indicates a significant association between the variables.
Odds Ratio 
3.74
People with a family history of overweight are 3.74 times more likely to consume high calorie foods frequently.
Relative Risk: Column 1
1.42
People with a family history of overweight have a higher chance of frequent high-calorie food consumption compared to those without a family history.
Relative Risk:
Column 2
0.37
Individuals without a family history of overweight have a lower chance of frequent high-calorie food consumption compared to those with a family history.
Key Findings and Interpretation: 

Hypothesis Testing:
Is there a significant difference in the average BMI of males and females?

μ1 = The average BMI of males
μ2 = The average BMI of females
Hypothesis:
H0: μ1 = μ2
H1: μ1 ~= μ2

Independent t-test (Two sample t-test)
SAS Procedures used : 
PROC UNIVARIATE
PROC TTEST

p values for all 3 tests (for both groups) are < 0.05.
Non-normal distribution



Results and Interpretation
The Levene test (equality of variances) shows p < 0.0001.
Therefore, we assume unequal variances (Satterthwaite method).
There is a statistically significant difference in the average BMI for males and females.
29.28 kg/m2 for males vs 30.13 kg/m2 for females

  Linear Correlation
SAS Procedures used : 
PROC SGSCATTER
PROC CORR
H0 = Age and BMI are not correlated with each other
H1 = Age  and BMI are correlated with each other
Question: What is the correlation between BMI and Age? 

Results and Interpretation


Parameter
Value
Interpretation
Correlation Coefficient
0.24
Weakly positive correlation
 p value
< 0.0001
Statistically significant

Linear Regression Analysis

   
How can the relationship between BMI and height be characterized through linear regression?
SAS Procedure used: PROC REG
Parameter
Value
Interpretation
R-Square
0.0169
~ 1.69 % of variance in BMI is explained by height
p value
< 0.0001
Statistically significant
The model has a very low explanatory power

Scatter plot and Simple Linear Regression Line

   

Multiple Regression Analysis
How do factors such as a positive family history, dietary habits, physical activity, and smoking influence the BMI?
SAS Procedure used: PROC GLM

Expected BMI for people with a positive family history, frequent high calorie food consumption, non-monitored calorie consumption, no physical activity, and positive smoking habit is 33.07 kg/m2 (Obese)

Family history, frequent high-calorie food consumption, calorie consumption monitoring, and regular physical activity show a significant association with BMI (p < 0.05), while smoking does not (p = 0.89).

This analysis however has its limitations because it does not take into consideration the effect of interactions between the different factors. 



Logistic Regression Analysis
Analyzing the impact of age on obesity likelihood (being in the overweight or obese category) using logistic regression
This SAS code conducts a logistic regression analysis for a single variable, Age_R, to predict the likelihood of obesity (bmi_category_binary=1). 

Logistic Regression Analysis

AIC (Akaike Information Criterion): 2470.524





The odds ratio for Age_R is 1.242, suggesting that the odds of being in the overweight/obese category increase by approximately 24.2% for each one-unit increase in Age_R.

Summary of Findings:
Weight Distribution:
Weight distribution slightly skewed to the right.
Non-normal distribution observed.

Family History:
81.76% had a positive family history of overweight.

BMI category:
About 45% were in the 'Obese' category.

Transportation:
74.85% used public transportation.

Calorie Monitoring:
Monitoring calorie consumption associated with lower average weight.

Dietary Habits:
Eating between meals significantly associated with BMI categories.
Positive family history linked to frequent high-calorie food consumption.
Gender and BMI:
Statistically significant relationship observed.

Age and BMI:
Weakly positive correlation observed.
Odds of overweight/obese category increased by 24.2% with each one-unit increase in age.

Biometric Characteristics:
Height minimally explained BMI variance.

Associations with BMI:
Family history, frequent high-calorie food consumption, calorie monitoring, and regular physical activity showed significant associations.

Smoking did not show a significant relationship.












Conclusion


Thoughts about improving the project:
Explore relationships between variables in greater detail by conducting additional tests with varied combinations of variables.
Investigate alternative methods for cleaning and preparing the dataset to enhance analysis possibilities.

It can be inferred that obesity is influenced by multiple diverse factors, including demographic and physical characteristics, diet, physical activity, and familial history. 
Research and data analytics can identify trends and patterns, and discover correlations between different factors, so as to help in designing and implementing strategies to effectively manage this critical health issue in the region. 

Conclusion
Next steps for the future:
Conduct more regression analyses to test different types of models to predict obesity levels
Work with another dataset that is larger and more comprehensive 
Positive Takeaways:
Uncovering insights from real-world datasets and utilizing SAS to address practical challenges 
Limitations/Challenges:
Navigating errors and troubleshooting issues within SAS

  References
Guevara-Ramí­rez, P., Cadena-Ullauri, S., Ruiz-Pozo, V. A., Tamayo-Trujillo, R., Paz-Cruz, E., Simancas‐Racines, D., & Zambrano, A. K. (2022). Genetics, genomics, and diet interactions in obesity in the Latin American environment. Frontiers in Nutrition, 9. https://doi.org/10.3389/fnut.2022.1063286
Holub CK, Elder JP, Arredondo EM, Barquera S, Eisenberg CM, Sánchez Romero LM, Rivera J, Lobelo F, Simoes EJ. Obesity control in Latin American and U.S. Latinos: a systematic review. Am J Prev Med. 2013 May;44(5):529-37. doi: 10.1016/j.amepre.2013.01.023. PMID: 23597819; PMCID: PMC4808744.
Jiwani, S. S., Carrillo-Larco, R. M., Hernández-Vásquez, A., Barrientos-Gutiérrez, T., Basto-Abreu, A., Gutierrez, L., Irazola, V., Nieto-Martínez, R., Nunes, B. P., Parra, D. C., & Miranda, J. J. (2019). The shift of obesity burden by socioeconomic status between 1998 and 2017 in Latin America and the Caribbean: a cross-sectional series study. The Lancet. Global health, 7(12), e1644–e1654. https://doi.org/10.1016/S2214-109X(19)30421-8
Obesity rates by country 2023. Wisevoter. (2023, March 22). https://wisevoter.com/country-rankings/obesity-rates-by-country/
World Health Organization. (n.d.). Obesity and overweight. World Health Organization. https://www.who.int/news-room/fact-sheets/detail/obesity-and-overweight
World Obesity Federation, World Obesity Atlas 2023. https://data.worldobesity.org/publications/?cat=19
https://globalnutritionreport.org/resources/nutrition-profiles/
World Obesity Federation Global Obesity Observatory. (n.d.). World Obesity Federation Global Obesity Observatory. https://data.worldobesity.org/country/
de Victo, E. R., Fisberg, M., Solé, D., Kovalskys, I., Gómez, G., Rigotti, A., Cortes, L. Y., Yépez-Garcia, M. C., Pareja, R., Herrera-Cuenca, M., Drenowatz, C., Christofaro, D., Araujo, T., Silva, D., & Ferrari, G. (2023). Joint Association between Sedentary Time and Moderate-to-Vigorous Physical Activity with Obesity Risk in Adults from Latin America. International Journal of Environmental Research and Public Health, 20(8), 5562. https://doi.org/10.3390/ijerph20085562 
Kain, J., Vio, F., & Albala, C. (2003). Obesity trends and determinant factors in Latin America. Cadernos de Saúde Pública, 19, S77-S86.


Appendix 1
Dataset Name : Estimation of obesity levels based on eating habits and physical condition

Dataset source :
https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition

Link to article describing the dataset:
Dataset for estimation of obesity levels based on eating habits and physical condition in individuals from Colombia, Peru and Mexico
https://www.sciencedirect.com/science/article/pii/S2352340919306985?via%3Dihub











Appendix 2
Background research and introduction: 
Lizeth Ildefonso


Data Analysis:
Ketaki Narendra Gharpuray
Aashi Sethiya



Summary and Conclusion:
Zy’Ada Hansley

Appendix 3
Topics not covered:
Importing the dataset in SAS
Limitations of the study

