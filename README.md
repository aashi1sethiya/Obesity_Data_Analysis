# Obesity Data Analysis
## What fuels the escalating obesity rates in Latin America, and how can data analytics help discover insights about the contributing factors? 

# Backdrop and Context:
The World Health Organization classifies a BMI ≥ 25 as overweight and a BMI ≥ 30 as obesity in adults. It is projected that by 2030, the proportion of individuals classified as obese or overweight in Latin America and the Caribbean will rise to 81.9%.

<img width="699" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/4b5622ce-497a-4589-a229-27645dde1ff3">

# Research about obesity in Latin America:
Kain et al (2003) state that several factors such as poor nutrition, socioeconomic causes, and a sedentary lifestyle have contributed to the rise in obesity levels in the region. 

A 2019 study by Jiwani et al. found that obesity prevalence is on the rise in the region, with pronounced increases in rural areas and disadvantaged groups, as well as in affluent, urban populations.  

In a study of adults from 8 Latin American nations, deVicto et al (2023) explored how sedentary time and physical activity affected obesity indicators. 

The effect of genetic factors on obesity in Latin America was studied by Guevara-Ramírez et al (2022). 

# Unveiling Obesity Trends in Latin America
Research Question:
What fuels the escalating obesity rates in Latin America, and how can data analytics help discover insights about the contributing factors? 

# Dataset Description:
The dataset included individuals from  Mexico, Peru, and Colombia,  with diverse age groups and lifestyles, which helped us understand the interplay of various factors. 

# Survey Methodology:
The dataset authors employed a web-based survey and synthetic techniques to  gather 17 attributes and 2111 records, offering a holistic view of dietary habits, physical conditions, and socio-demographics.

# Data Preparation
## Issues with the dataset
The dataset did not have any missing data in any of the columns.

However, there were decimal values for many of the variables, even for the categorical ones (probably because a major part of the data was generated synthetically).

This posed a problem in analyzing the dataset. 

## How was the data handled?
Therefore, to simplify the data for the ease of performing analysis, the values with decimals were rounded off to the nearest whole number. 

This was useful in obtaining well defined categories for the categorical variables. 

The new variables obtained were re-coded accordingly with a different name. 

# Exploratory Data Analysis
Descriptive statistics to understand the distribution of weight of the sample population

How many people have a positive family history of overweight?

What are the different modes of transportation used, and what is their distribution? 

What is the distribution of individuals across different BMI categories?

What is the mean weight of people who monitor their calorie consumption as compared to those who do not?

<img width="508" alt="Screenshot 2023-12-20 121404" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/02a23854-8b56-4278-8da3-2dc6e83397de">

# Summary of Findings:
## Weight Distribution:
Weight distribution slightly skewed to the right.
Non-normal distribution observed.

<img width="515" alt="Screenshot 2023-12-20 121418" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/41fa3ca0-3fb3-4bdd-9f28-e7ab8693a749">

## Family History:
81.76% had a positive family history of overweight.

<img width="306" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/5106d913-f65a-4a01-a8a0-ea81bbeca833">

## BMI category:
About 45% were in the 'Obese' category.

<img width="205" alt="Screenshot 2023-12-20 121448" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/aead72e5-1644-4f5e-9942-71c90f3e98b6">

## Transportation:
74.85% used public transportation.

<img width="489" alt="Screenshot 2023-12-20 121437" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/a31df2e4-7f25-414c-9fad-13c1a30913b2">

## Calorie Monitoring:
Monitoring calorie consumption associated with lower average weight.

<img width="530" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/530cd0b8-ee4e-4447-ad77-bdaa65c2916f">


## Dietary Habits:
Eating between meals significantly associated with BMI categories.
Positive family history linked to frequent high-calorie food consumption.

<img width="547" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/d7dfa015-4f15-4fe7-81c4-39ef0f68f034">


<img width="454" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/88d4c69a-3e61-4cb6-a40a-b0ae69108f73">


<img width="542" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/a03530ef-3d26-4632-8f38-ba6b016ae474">


## Gender and BMI:
Statistically significant relationship observed.

<img width="597" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/2ca6df52-c501-4ee1-ba82-2650f049bb14">


## Age and BMI:
Weakly positive correlation observed.
Odds of overweight/obese category increased by 24.2% with each one-unit increase in age.

<img width="311" alt="Screenshot 2023-12-20 121509" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/f9779119-c017-4814-bcff-9f966dbc2c5d">

<img width="494" alt="image" src="https://github.com/aashi1sethiya/obesity_data_analysis/assets/127284223/7ac19acf-8059-411c-9ca9-cb239f4befcd">


## Biometric Characteristics:
Height minimally explained BMI variance.

## Associations with BMI:
### Family history, frequent high-calorie food consumption, calorie monitoring, and regular physical activity showed significant associations.
### Smoking did not show a significant relationship.

