# Heart-Failure-Analysis *In Progress*
## An Analysis of Heart Attack Causes and Trends

## The Dataset

The dataset was clinically and professionally collected by the party below. The original hosting link and heart failure study is available after the author credit. I obtained the dataset through Kaggle.com, and it can be found [here](https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data).

Davide Chicco, Giuseppe Jurman: Machine learning can predict survival patients with heart failure from serum creatine and ejection fraction alone. [BMC Medical Informatics and Decision Making 20, 16 (2020)](https://bmcmedinformdecismak.biomedcentral.com/articles/10.1186/s12911-020-1023-5).

This dataset was built and structured with the main focus being on machine learning. The .csv for the original data as well as the transformed data + change log can be found in the "Data Set and Changelogs" folder.

License: CC BY 4.0

## Methodology

The original dataset was cleaned in excel by giving Patient ID keys to each record, as none previously existed, and also to replace 1/0 values to M/F for the sex column. The purpose of this notebook is to execute exploratory analysis on the heart failure dataset for trends and summary tables. After exploratory analysis is done, I will move the data to Power BI for detailed visualization. Even though the dataset was designed for machine learning, there are still many insights to be made through descriptive analysis.

*Note*: The most important piece of this dataset is the hardest part to understand. The "time" attribute denotes the last status of the patient observed by the scientists, who collected the data, until the patient either died or they lost contact. Losing contact will be considered a "survival" by me and denoted as a "0" as a data point. Any 1's in this attribute are official counted as deaths at the follow-up point by the scientists. This is a small inconsistency in the data set for my analysis, but will still offer enough accuracy for insights.

## The Questions that Need Answered

1. Which age groups are at the highest risk of heart disease?
2. Which attribute contained in the dataset is the highest indicator of heart disease?
3. Are certain attributes in the dataset more likely to affect men more than women, or vise versa?
4. Are there any key indicators that deceased patients show that might help us learn how to decrease the mortality rate?

## Using SQL

The SQL notebook, "Heart Failure Analysis.ipynb," contained within the repository, outlines my use of SQL to find exporatory trends before moving into Power BI for more complex analysis. I used Azure Data Studio to build the notebook.

<img width="1435" alt="Notebook Screenshot" src="https://user-images.githubusercontent.com/103079066/194187229-3d75ebbd-2fa4-4b70-855e-f80427f25007.png">

## Analyzing in Power BI

<img alt="Power BI Dashboard Screenshot" src="https://github.com/colbystout/Heart-Failure-Analysis/blob/main/Power%20BI/Dashboard%20Screenshot.png">

## Results


