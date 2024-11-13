
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


# Pipeline Overview

## Preparing the data
The datasets are imported into Jupyter notebooks with the pands, numpy, and matplotlib libraries imported.

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

## import the datasets and identify each one
KC_file = r'C:\Users\HannahFarrell\OneDrive - Greater Manchester GP Federations Toolkit\Desktop\Python\Apprenticeship\Assessments\DPS\kc_breed_registrations (1).csv'
kc_data = pd.read_csv(KC_file, encoding ='ISO-8859-1')

CHAR_file = r'C:\Users\HannahFarrell\OneDrive - Greater Manchester GP Federations Toolkit\Desktop\Python\Apprenticeship\Assessments\DPS\dog_characteristics.csv'
char_data = pd.read_csv(CHAR_file)


### Applying Business Logic



### Bringing it all Together



### Validating the Outputs



### Displaying Results to the User


# Conclusion

## Outline



## Considerations



#  Bibliography

