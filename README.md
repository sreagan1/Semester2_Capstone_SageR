# Tree Coverage Type Prediction

## Links to the Dataset Source and the Powerpoint

link to dataset source: https://www.kaggle.com/datasets/uciml/forest-cover-type-dataset

link to powerpoint: https://github.com/sreagan1/Semester2_Capstone_SageR/blob/main/Capstone2Prez.pptx

## Summary

Determine tree coverage type based on surrounding forest characteristics. Determining tre coverage type will allow the Bureau of Land Management to know which trees to cut down to thin the Roosevelt National Park forest for better forest health. 

I am using a csv file that contain forest characteritics to train a decision tree model in order to solve a binary classification. The decision tree model has a 95% precision and will be effective in solving this problem. 

![alt text](https://github.com/sreagan1/Semester2_Capstone_SageR/blob/main/README%20image.jpg)

## Business Understanding

This capstone is attempting to determined tree coverage type based on given characteristics within 
Roosevelt National Park and is relative to the forestry and land management industry. The business case 
for this capstone is the Bureau of Land Management wishes to thin parts of the Roosevelt National Forest
so that trees won’t have to fight over water and light within the forest. They have determined that there 
are many Lodgepole Pine trees within the forest and that selling the lumber from these trees will be 
financially beneficial. Therefore, the Bureau of Land Management wants to know if trees in certain areas 
are Lodgepole Pines, based on the surrounding environmental features within the forest. Furthermore, it is 
important that the Bureau not cut down other types of trees as it will not benefit the health of the forest, 
and the lumber from those trees will be worth less financially.

more information on why thinning a forest can be benneficial to it's health: https://www.fs.usda.gov/features/thinning-forest-trees#:~:text=It%20is%20used%20to%20restore,susceptible%20to%20insect%20and%20disease.

## Data Understanding

The following are the variables within the dataset:

- Elevation
- Aspect
- Slope
- Horizontal distance to hydrology
- Vertical distance to hydrology
- Distance to roadways
- Distance to fire points
- Shade on the hillside at 9am, noon, and 3pm
- Specific wilderness area within the park
    - The areas are represented with 4 binary columns
- Soil type. 
    - The soil type is represented with 4 binary columns 
- Type of tree coverage

Tree Coverage Type is the target variable. 

## Jupyter Notebook Steps

To get the data: download data from kaggle link, unzip file into local repository on computer.

Tools used: pandas, numpy, matplotlib, sklearn, git hub 

1. Load data into Jupyter Notebook
2. Examine dataframe to understand what the dataset contains and the neccesary preprossesing steps
    a. There are no null values, are categorical data that needs to be encoded
    b. there is a class imbalance among the target variable (tree cover type). 
3. The target variable is tree cover type. create a binary classification problem by condensing all tree types outside of Lodgepole Pine        into a single class. 
    a. the two classes are now Lodgepole Pine trees and other trees. 
4. Define X and y features of the dataset. y being the target variable (tree cover type) and X being all other variables.
5. Split the dataset into train and test sets. 
6. Train a pruned version of a decision tree classifier and save a model of this tree as an example of a decision tree classifier. 
7. Create a basic decision tree classifier based on the previous train and test sets. 
    a. Create a confusion matrix and evaluate the precision, recall, accuracy, and F1 of this basic model. 
8. Tune max depth, min samples split, and min samples leaf in an attempt to create a more effective model.
    a. start by training decision tree models with several different values of the hyperparamters and graphing those values against the            resulting metrics (precision, recall, accuracy, and F1). 
    b. Based on the previous graphs, determine an apropriate range of values for each hyperparemeter. Then use GridSearchCV to train models        for all combinations of these values. 
9. Based on the results from the GridSearchCV, train an updated model with the best hyperparamter values. 
    a. Create a confusion matrix and evaluate the the precision, recall, accruacy, and F1 of the new model. 
10. Compare the basic model and updated model based on the confusion matric and evaluation metrics of each to determine which model would be     the most benneficial to use in order to solve the business case. 

## Model Evaluation

I used decision tree classifier in order to solve a binary classification problem. 

Baseline model evaluation metrics:
- Precision: 95.4%
- Recall: 95.3%
- Accuracy: 95.5%
- F1: 95.3%

Secondary Model:
- Precision: 95.2%
- Recall: 94.2%
- Accuracy: 94.9%
- F1: 94.7%

While both models performed well, the baseline model performed best in regards to precision, recall, accuracy, and F1. 
Based on these findings, the baseline model should be used for the business case. 

## Conclusion 

I recomend that the baseline model be used in the binary classification of tree types within Roosevelt National Park forest. 

## Repository Navigation

The repository contains 5 files: the README, the Jupyter Notebook, the Capstone Project Proposal, the Capstone Presentation, and the git ignore file. 

There is only a single Jupyter Notebook for this capstone. It contains everything necessary to solve the business case, as well as figures that ensure a more comprehensive understanding of the capstone for the presentation. 

The Capstone Proposal was a document made in the initial steps of the capstone with a plan on what problem the capstone would be adressing and how I plan on going about the problem. 

The capstone presentation is a powerpoint that will explain to a non technical audience what was done for the capstone. 

The git ignore file ensures the repository will ignore the large dataset loaded into the capstone. 