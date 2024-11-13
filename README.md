
### Data Science Project: Trends in Kennel Club Registrations (2013 - 2022)


## Overview

This project uses two publicly available datasets to observe the trends different dogs being bred, according to Kennel Club registered litters, friendliness rating, and health issues risk.

### Positive Impact


### Negative Impact

## Conclusion


##  Bibliography


# Original Documentation

# Contents

[Introduction](#introduction)

[Project Background](#project-background)

[Project Summary](#project-summary)

[Issue at Hand](#issue-at-hand)

[Solution](#solution)

[Outcome](#outcome)

[Pipeline Overview](#pipeline-overview)

[A High Level Look at the Pipeline](#a-high-level-look-at-the-pipeline)

[A Deeper Dive Into the Pipeline](#_Toc124888952)

[Desired Output Structure](#desired-output-structure)

[Ingesting Data from Google Sheets](#ingesting-data-from-google-sheets)

[Preparing the Branches Import](#preparing-the-branches-import)

[Applying Business Logic](#applying-business-logic)

[Bringing it all Together](#bringing-it-all-together)

[Validating the Outputs](#validating-the-outputs)

[Displaying Results to the User](#displaying-results-to-the-user)

[Conclusion](#conclusion)

[Outline](#outline)

[Considerations](#considerations)

[Bibliography](#bibliography)


# Project Background
Dogs are notoriously know as man's best friend, with the vast displays on social media of 'doggos' further illustrating this point. However, with the emergence of social media, in addition to the displays of love and affection these animals bring, it is becoming more common to bare witness to the public debates surrounding the ethics of dog breeding, dog ownership, and the seeming rise in dog attacks.

# Project Summary

## Question
Are more unfriendly dogs being born each year?

## Solution

## Outcome


# Preparing the data
The datasets are imported into Jupyter notebooks with the pands, numpy, and matplotlib libraries imported.

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

### import the datasets and identify each one
KC_file = r'C:\Users\HannahFarrell\OneDrive - Greater Manchester GP Federations Toolkit\Desktop\Python\Apprenticeship\Assessments\DPS\kc_breed_registrations (1).csv'
kc_data = pd.read_csv(KC_file, encoding ='ISO-8859-1')

CHAR_file = r'C:\Users\HannahFarrell\OneDrive - Greater Manchester GP Federations Toolkit\Desktop\Python\Apprenticeship\Assessments\DPS\dog_characteristics.csv'
char_data = pd.read_csv(CHAR_file)

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

