
### Data Science Project: Trends in Kennel Club Registrations (2013 - 2022)


## Overview

This project uses a publicly available dataset which examines each dog breed, providing scores on popularity, size, intelligence, suitability for children (score for kids), lifetime cost, intelligence, longevisty, genetic ailments, purchase price, annual food costs, and grooming frequency. I wish to observe the relationship between popularity and congenital ailments.

### Positive Impact
Better owner education, promotion of healthy breeding etc.

### Negative Impact
Public perception and opinion, breeds becoming extinct.

## Conclusion

##  Bibliography


# Data Sources

# Contents

[Introduction](#introduction)

[Project Background](#project-background)

# Project Background
Dogs are notoriously know as man's best friend, with the vast displays on social media of 'doggos' further illustrating this point. However, with the emergence of social media, in addition to the displays of love and affection these animals bring, it is becoming more common to bare witness to the public debates surrounding the ethics of dog breeding and the health of certain dog breeds. This project aims to examine the relationship between popularity ranking and the number of genetic ailments. 

# Project Summary

## Question
Are dogs with more genetic ailments becoming more popular?

## Solution

## Outcome


# Preparing the data
The datasets are imported into Jupyter notebooks with the pandas, numpy, and matplotlib libraries imported.

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

### import the datasets and identify each one
dogs_file = r'C:\Users\HannahFarrell\Greater Manchester GP Federations Toolkit\GMTHFiles - Documents\GM Training Hub\Information Analysis\.ipynb_checkpoints\dogs-ranking-dataset.csv'
dogs_data= pd.read_csv(dogs_file)

## Check the top 5 rows of the table
dogs_data.head()

![image](https://github.com/user-attachments/assets/96048de0-e306-47bf-9d9a-8a804dd34e15)


### Check for null values and types of data
kc_data.info()

### Remove commas from numerical data and convert to int.64

kc_columns_to_convert = ['2013','2014','2015','2016','2017','2018','2019','2020','2021','2022']
kc_data[kc_columns_to_convert] = kc_data[kc_columns_to_convert].replace({',':''},regex=True).astype(int)
kc_data.info()

## Check for null values and types of data
char_data.info()

## Remove commas from numerical data and convert to int.64

char_data_to_convert = ['Average Weight (kg)']
char_data[char_data_to_convert] = char_data[char_data_to_convert].astype(float)

### we have identified a record with an incontangible value for weight. This must be assumed to be an error and as we are unable to check this value with the original source of the data, on this occasion we will delete the record and highlight as a limitation.

char_data = char_data[char_data['Average Weight (kg)'] != '25-Jul']
char_data_to_convert = ['Average Weight (kg)']
char_data[char_data_to_convert] = char_data[char_data_to_convert].astype(float)
char_data.info()

## the plan is to merge the two datasets using the "breed" column as the key. Therefore need to check that there are no trailing spaces/extra spaces in the key column of each dataset.
kc_data['Extra_Spaces'] = kc_data['Breed'] != kc_data['Breed'].str.strip()
print(kc_data['Extra_Spaces'].any())
True

### Remove the trailing spaces/extra spaces
kc_data['Breed']= kc_data['Breed'].str.strip()

### Check the second dataset for extra spaces/trailing spaces in the "breed" column
char_data['Extra_Spaces'] = char_data['Breed'] != char_data['Breed'].str.strip()
print(char_data['Extra_Spaces'].any())
False

### perform the merge. There are unequal numbers of breeds in the datasets. Therefore an inner join is used.
merged_data = pd.merge(kc_data, char_data, on='Breed', how='inner')

### Check the merged metadata
merged_data.info()

### View the merged dataset
from IPython.display import display
display(merged_data)

### View the merged dataset
from IPython.display import display
display(merged_data)

### Applying Business Logic



### Bringing it all Together



### Validating the Outputs



### Displaying Results to the User


# Conclusion

## Outline



## Considerations



#  Bibliography

