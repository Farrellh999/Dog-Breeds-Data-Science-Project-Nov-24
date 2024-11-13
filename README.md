
# Impact Evaluation: Data Engineering Project (2023)


## Overview

### Positive Impact


### Negative Impact

## Conclusion


##  Bibliography


# Original Documentation

# Contents

[Introduction](#introduction)

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


# Project Summary

## Issue at Hand



## Solution



## Outcome



# Pipeline Overview

## A High Level Look at the Pipeline

## A Deeper Dive Into the Pipeline

### Desired Output Structure



| Output Column              | Source Type      | Source Table(s)                                                   | Noteable Column(s)                    |
|----------------------------|------------------|-------------------------------------------------------------------|---------------------------------------|
| branchkey                  | Application Data | branches                                                          | branchkey                             |
| branchid                   | Application Data | branches                                                          | branchid                              |
| branch                     | Application Data | branches                                                          | branch_name                           |
| cabinet_meterage           | User Input       | gsheet_branches                                                   | cabinet_meterage                      |
| shop_floor_shelf_count     | User Input       | gsheet_branches                                                   | shop_floor_shelf_count                |
| treat as new               | User Input       | gsheet_branches                                                   | treat as new                          |
| cabinet_multiplier         | Calculated       | gsheet_branches                                                   | cabinet_meterage                      |
| media_multiplier           | Calculated       | gsheet_branches                                                   | shop_floor shelf_count                |
| category_id                | Application Data | category                                                          | category_id                           |
| box_category               | Application Data | category                                                          | box_category                          |
| category_location          | User Input       | gsheet_category_types                                             | category_location                     |
| total stock                | Calculated       | aio_fact                                                          | quantity                              |
| average_stock_per_location | Calculated       | aio_fact, gsheet_branches                                         | quantity                              |
| minimum_capacity           | Calculated       | aio_fact, gsheet_branches, gsheet_controls                        | quantity, minimum_capacity_percentage |
| maximum_capacity           | Calculated       | aio_fact, gsheet_branches, gsheet_controls                        | quantity, maximum_capacity_percentage |
| capacity_ratio             | Calculated       | aio_fact, gsheet_branches, gsheet_controls, gsheet_category_types |                                       |
| raw cap                    | Calculated       | aio_fact, gsheet_branches, gsheet_controls, gsheet_category_types |                                       |
| new_capacity               | Calculated       | aio_fact, gsheet_branches, gsheet_controls, gsheet_category_types |                                       |

### Ingesting Data from Google Sheets

#### Transforming the Controls



### Preparing the Branches Import


### Applying Business Logic



### Bringing it all Together



### Validating the Outputs



### Displaying Results to the User


# Conclusion

## Outline



## Considerations



#  Bibliography

