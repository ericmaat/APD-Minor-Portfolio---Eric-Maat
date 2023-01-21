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
  - [Data Visualization](#Data-Visualization)
- [Communication](#Communication)
  - [Presentations](#Presentations)
  - [Writing Paper](#Writing-Paper)
- [Python Notebooks](#Python-Notebooks)
- [Experiments](#Experiments)
- [Other Achievements](#Other-Achievements)

# DataCamp Courses

![This is a alt text.](/Images/DatacampEric.png "DataCamp Courses")

# Research Projects
## Food Boost
### Task Definition
The first project I worked on was in regards of the Food Boost case. The case focuses on eating more sustainable and healthy dishes and people's personal preferences towards such recipes. In this case it is possible to apply multiple methods. For example, Data Science could be used to predict wether a person likes a certain recipe or not, statistics could be used to estimate which ingredients a person likes or findig optimal combinations of recipes with the use of linear programming.  

Our group of six (which we called "The Human Machine Teachers") tried to set a research goal where we could use multiple methods. We decided on the following research goal:  

**"What method(s) can be used to create a week schedule consisting of lunch and diner recipes while taking calorie intake and nut allergy into account?"**  
_"**1.** Which ingredients make a recipe be considered a nut allergen?"_  
_"**2.** What is a healthy amount of calories for one lunch and one dinner?"_  
_"**3.** What method(s) can be used to predict wether a person likes a recipe or not?"_  
_"**4.** What method(s) can be used to make a varying week schedule of lunches and diners?"_  

The week schedule mentioned here consists of 14 recipes (7 lunches and 7 diners). For this research we limited the schedule to only provide lunch and diner recipes, because only these two types of recipes were both relevant and provide sufficient data.  

We chose a research goal with this many elements and restrictions, because there are many steps and methods needed to reach the end goal. This requires us to delve into different areas of knowledge, which helps us get familiar with multiple methods and data processes. Using only lunch and diner recipes which contain no nuts requires data preparation. To predict wether a person likes certain recipes or not we can make great use of Data Science. To create an optimal recipe schedule we could make great use of linear programming.

### Future Works

Even though the project would eventually last only six weeks, a lot of progress was made regarding the data preprocessing, predictive analysis and Operational Research. Naturally, there is still room for improvement.  

The original data consisted of approximately 10.000 recipes. Around 4.500 of those were kept by only keeping the nut-free lunch and diner recipes. While these are still enough data elements to base a predictive model on, there might still have been too many features. Only the ingredients were kept that were used for at least one percent of the recipes. That ended up being more than 100 features, which might have led to eventual overfitting. Having more data and/or less features would have probably improved the model performances.  

We based our models on the food opinions of a group mate. He ended up liking 180 of the 265 recipes. This meant our created data had 180 ones and 85 zeros, thus making the dataset skewed. We could have balanced the dataset to give both classes equal proportions.  

Linear programming was used for creating the week schedule by having restrictions based on the energy of each chosen recipe. In the future we could involve nutritients besides energy, like fat or protein. This would add more restrictions to the model, but make for a more balanced recipe schedule.

### Conclusions
_**"1. Which ingredients make a recipe be considered a nut allergen?"**_  

To answer this question we searched for a way to determine if a specific ingredient contained nuts or not. Instead of using going by every ingredient in the dataset, we created a list of strings where if an ingredient of a recipe contained one of these strings, the recipe itself would be considered as a nut allergen.

<details>
<summary> List of forbidden nut strings </summary>

```
notenLijst = ["noot","pinda","eikel","amandel","cashew","hazelno","hican","hickory","kemirie","macadamia","nangaino","parano","pecan","pistache","kastanje","walnoot","betelno","beukenno"]
```

</details>

For this we also had to keep in account eventual false positives. For example, "nootmuskaat" contains the string "noot", but this ingredient does not make a recipe a nut allergen. For these cases a list was created of strings that surpass the previous checklist.

<details>
<summary> List of false positives </summary>

```
falsePositives = ["muskaat"]
```

</details>

_**"2. What is a healthy amount of calories for one lunch and one dinner?"**_  

After my teammates had done there research on this topic, they came to the conclusion that a healthy amount of one lunch and one dinner together is 1040 Kcal. This answer would help make the restrictions for the linear programming model.  

_**"3. What method(s) can be used to predict wether a person likes a recipe or not?"**_  

After following the DataCamp courses and having some lectures about machine learning, we concluded that a classifier would work best to answer this question. We chose three classifiers and after tuning the hyperparameters we wrote down the resulting scores of each of them.  

<details><summary> Model performances </summary>

| Classifier Models   | Precision | Recall | Accuracy |
| ------------------- |:---------:|:------:|:--------:|
| Decision Tree       | 0.83      | 0.88   | 0.74     |
| Logistic Regression | 0.83      | 0.71   | 0.66     |
| K-Nearest Neighbors | 0.78      | 0.60   | 0.55     |

</details>

The classification models with the highest precision seem to be the Decision Tree and Logistic Regression. To determine which one is best suited we will also look at the accuracy of the models. The Decison Tree classifier performs better in this regard, which means it is the best method to use for classifying recipes.  

_**"4. What method(s) can be used to make a varying week schedule of lunches and diners?"**_  

A Linear Programming model was used to create the schedule. After the chosen classifier created a list of liked recipes, the LP model would choose 7 lunches and 7 diners and create a week schedule. The restrictions this model followed were:  
* A recipe can only appear in the week schedule once
* Exactly one lunch each day
* Exactly one diner each day
* The maximum amount of calories per day is 1040

The model tries to maximize the amount of calories for each day. By having the last restriction it will never exceed 1040 Kcal, but will try to get as high as possible.

### Planning

For the six weeks we spent on the FoodBoost project we planned to have three group meetings every week. On Monday, Wednesday and Friday. These meetings would involve anything regarding both individual and shared tasks, team co-operation, short-term planning, deadlines, etc. We also held work sessions on days without either lectures or meetings. These were on Tuesday and Thursday where we would make time to work on the project for at least five hours a day.

We have also set up a Trello Board where we would add multiple tasks, big or small, and distribute these over the team. At the meetings we would discuss what is on the board and would add tasks when necessary. The goal of this method was to have a task for everyone at the end of every meeting. The majority of these tasks had deadlines to ensure that people wouldn't stick to just having one task for a longer period of time.

<details>
<summary>Trello board FoodBoost screenshot</summary>
<img src="Images/TrelloBoardFB.png" />
</details>

## Cofano Containers
### Task Definition

The second project I worked on was in regards of the Cofano Case. This case focuses on the transport of containers from the yard of a terminal to a container ship and vice versa. This transport on the terminal will be handled by a reach stacker. Cofano wants to know what methods could be used to fix the container stacking problem where the end goal is to minimize the cost and delay of the whole proces. There is need for a method that organizes the container stacks on the yard in such a way that minimizes the amount of moves it takes to get certain containers to the ship. This problem can be formulated as an optimization problem where heuristics can be applied to solve it.

Our first research goal covered too much of the main problem to solve it in fourteen weeks, so we agreed on the following research goal:

**"What method(s) can be used to solve the ship to container yard part of the container stacking problem using only a reach stacker?"**  
_"**1.** What method(s)/heuristic(s) have been used to solve the container stacking problem in the past?"_  
_"**2.** What defines a move?"_  
_"**3.** What are the restrictions?"_  
_"**4.** What type of containers are transported?"_  
_"**5.** What is the lay-out of the yard?"_  
_"**6.** How can we simulate container ship data?"_  

Question 1 will introduce us to the most used methods for this problem and how to apply those step by step. Questions 2 to 5 are needed to define the context and environment of the situation that we want to optimize. It is important here to keep in mind that we can only use one reach stacker. Question 6 will use the answers on the previous questions to provide the data we can use in conjunction with the chosen method.

### Future Works

We have worked on this project for twelve weeks and achieved a lot in that time. However, our research only covered a part of Cofano's container stacking problem. This means there is still room for future work and improvements.  

The methods and models we applied were all used on a yard that was always empty at the beginning of an episode. In reality, the yard always contains some containers, so we could have tried to apply our model on a yard that is already partially filled with containers at the beginning of every episode. We could make a selection of containers that is randomly placed at the start of each episode to see how the model would (try to) adapt to this situation.  

During the project, our goal was to have the model fill the whole yard with containers until there is no space left. In reality, not all the space in a yard is used up when unloading just one ship. We could have used more yard space or smaller ships to unload to have the model try to find optimal stacks that do not use up all the avaible space on a yard.

The orginized stacks that our models end up with are optimal as long as the ships the containers are loaded in all arrive on schedule. If the order of incoming ships changes or one ship decides to go to another terminal, the lay-out on the yard would probably be much less optimal. In the future we could have the model adapt to such unforeseen situations by training it to produce multiple optimal lay-outs, each for a different order of ships.

Having the least amount of boxed in containers in the yard lay-out is our top priority, but our model doesn't take into account the time it takes for the reach stacker to go from a container it just placed to the next. In the future we could try to focus more on these limitations to prevent eventual delay. This could be done by starting the lay-out of half of the containers at one side of the yard before placing the other half of the load on the other side.

### Conclusions

_**"1. What method(s)/heuristic(s) have been used to solve the container stacking problem in the past?"**_  

I have found several articles on heuristic methods. Some used there own version on a Linear Programming method, others used a certain "GRASP algorithm" to tackle the problem. All of those were methods that could be applied with the big amount of constraints the container stacking problem introduced. After a while, we found out that reinforcement learning was a popular approach for these kind of problems. We delved deeper into what this method was about and then decided we wanted to use this for our final model.  

_**"2. What defines a move?"**_  

We defined a "move" as placing a container from the ship onto the container yard on the terminal. We decided not to take time into account for this.  

_**"3. What are the restrictions?"**_   

<details>
<summary>A container can not be placed on a space where a previous container is placed</summary>
<img src="Images/restrict2.png" width="400"/>
</details>

<details>
<summary>A container can not be placed on a space where there is no ground or other container beneath it</summary>
<img src="Images/restrict1.png" width="400"/>
</details>

<details>
<summary>A container can not be placed on top of a stack that has already reached its max height</summary>
<img src="Images/restrict3.png" width="400"/>
</details>

<details>
<summary>A container can not be placed outside of the container yard</summary>
<img src="Images/restrict4.png" width="400"/>
</details>

<details>
<summary>A container can not be placed between two existing stacks</summary>
<img src="Images/restrict5.png" width="400"/>
</details>

_**"4. What type of containers are transported?"**_  

To not overcomplicate things and make the problem too complex, we decided that every container has the same size and weight. The only thing that can distinguish containers is which ship they will eventually be loaded in.  

_**"5. What is the lay-out of the yard?"**_  

We decided to have a customizable yard that is always empty at the beginning of a game. For the final product we have a container yard of 4x4x5 spaces. This translates to a space for exactly 80 containers.  

_**"6. How can we simulate container ship data?"**_  

To simulate a ship full of containers that have to be transported we created a list of random numbers between 1 and 3 (container with 1 has the highest priority and 3 has the lowest). There were as many numbers in this list as there are spaces on the yard. The order of these numbers was random each episode.

### Planning

For the twelve weeks we spent on the Cofano container case, we kept the schedule we used for the weeks we spent on the FoodBoost case with some slight adjustments. Halfway through this time period we dropped the meeting on wednesday, because at that time there were less to discuss. The wednesday became a work session day instead.  

There was also planned to put more focus on the individual work of each teammate. We planned to have two weeks where each one of us worked separately on their own Reinforcement Learning model. This way, every teammate had to put work into the project and our individual contributions could be used to improve the final model.  

We also created a new Trello Board for this project. The structure mostly stayed the same compared to the one used for the FoodBoost project, but this time we assigned people to certain categories. This meant that each teammate was responsible for the tasks of their assigned category. This way everyone could fullfil at least one roll in the project.  

<details>
<summary>Trello board Cofano screenshot</summary>
<img src="Images/TrelloBoardCof.png" />
</details>

# Predictive Analytics
## FoodBoost

To predict a person's opinion on thousands of recipes we needed to use Machine Learning. There are too many recipes to do this manually after all. We decided that a person had only two options when rating a recipe. They either liked the recipe (represented by a '1') or did not like the recipe (represented by a '0'). This meant that we were dealing with classes and had to use a classification model.  

Because we try to predict what class a recipe belongs to, this class was made the target variable. The ingredients of a recipe almost always decide wether a person likes a recipe or not, so the ingredients were the the features in this case.  

After doing my assignments on DataCamp, there were, in my opinion, two courses that seemed useful for this case. The courses "Machine Learning with scikit-learn" and "Model Validation in Python" presented several examples of classification models and how to validate these. The three classifiers that stood out here were the **K-Nearest Neighbors**, **Logistic Regression** and **Decision Tree** classifiers.  

After the models were chosen and the data both prepared and splitted into train and test sets, I created and fitted my three own classifier models. The predictions of my models showed the following results.  

<details><summary> Model performances </summary>

| Classifier Models   | Precision | Recall   | Accuracy |
| ------------------- |:---------:|:--------:|:--------:|
| K-Nearest Neighbors | 0.794872  | 0.738095 | 0.641509 |
| Logistic Regression | 0.807692  | 1.000000 | 0.811321 |
| Decision Tree       | 0.848485  | 0.666667 | 0.641509 |

</details>

<details>
<summary>Confusion Matrix: K-Nearest Neighbors</summary>
<img src="Images/KNNmatrix.png" width="400"/>
</details>

<details>
<summary>Confusion Matrix: Logistic Regression</summary>
<img src="Images/LRmatrix.png" width="400"/>
</details>

<details>
<summary>Confusion Matrix: Decision Tree</summary>
<img src="Images/DTCmatrix.png" width="400"/>
</details>

To determine which classifier was best suited for our research, we would choose the one with the highest precision score. If our final model would predict incorrectly that a recipe is not liked, it has no major consequences for our recipe schedule. But if it predicts incorrectly that a recipe is liked, then the schedule might feature recipes the person doesn't like. This leads me to believe the main focus is on reducing the False Positives, which means a higher precision is more desired. In that case the Decision Tree seems to be the best choice.  

___

In order to achieve the highest precision for every classifier, I used hyperparameter tuning on all three models.  

___

For the K-Nearest Neighbors classifier I tuned the `n_neighbors` parameter to see what is the optimal amount of neighbors. The following graph shows the average precision score for 1 to 40 neighbors.  

<details>
<summary>Hyperparameter Tuning: n_neighbors</summary>
<img src="Images/KNNtuning.png" width="500"/>
</details>

Based on the results I used `n_neighbors = 28` for the model  

___

For the Logistic Regression classifier I tuned the `C` and `penalty` parameters using `GridSearchCV` which resulted in the following output.  

```
{'C': 1e-05, 'penalty': 'l2'}
```

Based on this outcome I went with `penalty = 'l2'` and `C = 0.1`  

___

For the Decision Tree I decided to tune the `max_depth` parameter to see the best maximum depth of the tree. The following graph shows the average precision score for 1 to 50 tree depth.

<details>
<summary>Hyperparameter Tuning: max_depth</summary>
<img src="Images/DTFtuning.png" width="500"/>
</details>

Based on the results I went with `max_depth = 33` for the final model.

___

To check if the models do not under- or overfit I used cross-validation. Here I used stratified cross-validation, because the data was unbalanced and I needed to give the five folds the same proportion of 0 and 1 values.  

<details><summary> Cross-Validation Scores </summary>

| Classifier Models   | Average cross_val_score |
| ------------------- |:-----------------------:|
| K-Nearest Neighbors | 0.688762                |
| Logistic Regression | 0.672980                |
| Decision Tree       | 0.672980                |

</details>

___

The code for these operations are in this python notebook.  

# Domain Knowledge

## Subject Field Introduction
Our research focused heavily on predicting wether a person likes a recipe or not. In this field, it is most important to reduce predictions which classify a recipe as 'liked', while in reality the person disliked the recipe (In our case, False Positives). Though it is also favorable to reduce prediction errors that fall into the False Negative category (especially if the person is a picky eater), such errors do not necessarily affect a good recipe schedule. It is worse to have disliked recipes show up on the schedule than missing out on some recipes that the person might have liked.  

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
