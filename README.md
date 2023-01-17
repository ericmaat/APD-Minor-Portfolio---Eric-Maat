# APD-Minor-Portfolio---Eric-Maat  
Studentnumber: 20162928  
Education: Applied Mathematics  
# <a id="table-of-contents"></a>Table of Contents <!-- omit in toc --> 
- [DataCamp Courses](#DataCamp-Courses)
- [Research Projects](#Research-Projects)
  - [Food Boost](#Food-Boost)
  - [Cofano Containers](#Cofano-Containers)
- [Predictive Analytics](#Predictive-Analytics)
  - [Model Selection](#Model-Selection)
  - [Model Configuration](#Model-Configuration)
  - [Model Training](#Model-Training)
  - [Model Evaluation](#Model-Evaluation)
  - [Model Visualization](#Model-Visualization)
- [Domain Knowledge](#Domain-Knowledge)
  - [Subject Field Introduction](#Subject-Field-Introduction)
  - [Literature Research](#Literature-Research)
- [Data Preprocessing](#Data-Preprocessing)
  - [Data Exploration](#Data-Exploration)
  - [Data Cleansing](#Data-Cleansing)
  - [Data Preparation](#Data-Preparation)
  - [Data Explanation](#Data-Explanation)
  - [Data Visualization](#Data-Vizualization)
- [Communication](#Communication)
  - [Presentations](#Presentations)
  - [Writing Paper](#Writing-Paper)
- [Python Notebooks](#Python-Notebooks)
- [Experiments](#Experiments)
- [Other Achievements](#Other-Achievements)

# DataCamp Courses

![This is a alt text.](/Images/DatacampEric.png "This is a sample image.")

# Research Projects
## Food Boost
### Task Definition
The first project I worked on was in regards of the Food Boost case. The case focuses on eating more sustainable and healthy dishes and people's personal preferences towards such recipes. In this case it is possible to apply multiple methods. For example, Data Science could be used to predict wether a person likes a certain recipe or not, statistics could be used to estimate which ingredients a person likes or findig optimal combinations of recipes with the use of linear programming.  

Our group of six (which we called "The Human Machine Teachers") tried to set a research goal where we could use multiple methods. We decided on the following research goal:  

**"What method could be used to create a week schedule consisting of lunch and diner recipes while taking calorie intake and nut allergy into account."**  

The week schedule mentioned here consists of 14 recipes (7 lunches and 7 diners). For this research we limited the schedule to only provide lunch and diner recipes, because only these two types of recipes were both relevant and provide sufficient data.  

We chose a research goal with this many elements and restrictions, because there are many steps and methods needed to reach the end goal. This requires us to delve into different areas of knowledge, which helps us get familiar with multiple methods and data processes. Using only lunch and diner recipes which contain no nuts requires data preparation. To predict wether a person likes certain recipes or not we can make great use of Data Science. To create an optimal recipe schedule we could make great use of linear programming.

### Evaluation

Even though the project would eventually last only six weeks, a lot of progress was made regarding the data preprocessing, predictive analysis and Operational Research. Naturally, there is still room for improvement.  

The original data consisted of approximately 10.000 recipes. Around 4.500 of those were kept by only keeping the nut-free lunch and diner recipes. While these are still enough data elements to base a predictive model on, there might still have been too many features. Only the ingredients were kept that were used for at least one percent of the recipes. That ended up being more than 100 features, which might have led to eventual overfitting. Having more data and/or less features would have probably improved the model performances.  

We based our models on the food opinions of a group mate. He ended up liking 180 of the 265 recipes. This meant our created data had 180 ones and 85 zeros, thus making the dataset skewed. We could have balanced the dataset to give both classes equal proportions.  

Linear programming was used for creating the week schedule by having restrictions based on the energy of each chosen recipe. In the future we could involve nutritients besides energy, like fat or protein. This would add more restrictions to the model, but make for a more balanced recipe schedule.

### Conclusions
<details><summary> Model performances </summary>

| Classifier Models   | Precision | Recall | Accuracy |
| ------------------- |:---------:|:------:|:--------:|
| Decision Tree       | 0.83      | 0.88   | 0.74     |
| Logistic Regression | 0.83      | 0.71   | 0.66     |
| K-Nearest Neighbors | 0.78      | 0.60   | 0.55     |

</details>

### Planning

## Cofano Containers

### Task Definition

### Evaluation

### Conclusions

### Planning

# Predictive Analytics

## Model Selection

## Model Configuration

## Model Training

## Model Evaluation

## Model Visualization


# Domain Knowledge

## Subject Field Introduction
The first project I worked on was in regards of the Food Boost case. The goal was to create a week schedule consisting of lunch and diner recipes (seven lunches and seven diners, so fourteen recipes in total) for a person who is allergic to nuts. Our research focused heavily on predicting wether a person likes a recipe or not. In this field, it is most important to reduce predictions which classify a recipe as 'liked', while in reality the person disliked the recipe (In our case, False Positives). Though it is also favorable to reduce prediction errors that fall into the False Negative category (especially if the person is a picky eater), such errors do not necessarily affect a good recipe schedule. It is worse to have disliked recipes show up on the schedule than missing out on some recipes that the person might have liked.  

## Literature Research

# Data Preprocessing

## Data Exploration

## Data Cleansing

## Data Preparation

## Data Explanation

## Data Visualization

# Communication

## Presentations

## Writing Paper

# Python Notebooks

[Dit is een notebook](/Python%20Notebooks/Score%20Functie%20Ding.ipynb)

# Experiments

# Other Achievements
