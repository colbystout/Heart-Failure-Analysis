# Heart-Failure-Analysis
## An Analysis of Heart Attack Causes and Trends

## The Dataset

The dataset was clinically and professionally collected by the party below. The original hosting link and heart failure study is available after the author credit. I obtained the dataset through Kaggle.com, and it can be found [here](https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data).

Davide Chicco, Giuseppe Jurman: Machine learning can predict survival patients with heart failure from serum creatine and ejection fraction alone. [BMC Medical Informatics and Decision Making 20, 16 (2020)](https://bmcmedinformdecismak.biomedcentral.com/articles/10.1186/s12911-020-1023-5).

This dataset was built and structured with the main focus being on machine learning. The .csv for the original data as well as the transformed data + change log can be found in the "Data Set and Changelogs" folder.

License: CC BY 4.0

## Methodology

The original dataset was cleaned in excel by giving Patient ID keys to each record, as none previously existed, and also to replace 1/0 values to M/F for the sex column. The purpose of this notebook is to execute exploratory analysis on the heart failure dataset for trends and summary tables. After exploratory analysis is done, I will move the data to Power BI for detailed visualization. Even though the dataset was designed for machine learning, there are still many insights to be made through descriptive analysis.

*Note*: The most important piece of this dataset is the hardest part to understand. The "time" attribute denotes the last status of the patient observed by the scientists, who collected the data, until the patient either died or they lost contact. Losing contact will be considered a "survival" by me and denoted as a "0" as a data point. Any 1's in this attribute are officialy counted as deaths at the follow-up point by the scientists. This is a small inconsistency in the data set from this longitudinal study for my analysis, but will still offer enough accuracy for insights.

## The Questions that Need Answered

1. Which age groups are at the highest risk of heart disease?
2. Which attribute contained in the dataset is the highest indicator of heart disease?
3. Are certain attributes in the dataset more likely to affect men more than women, or vise versa?
4. Are there any key indicators that deceased patients show that might help us learn how to decrease the mortality rate?

## Using SQL

The SQL notebook, "Heart Failure Analysis.ipynb," contained within the repository, outlines my use of SQL to find exporatory trends before moving into Power BI for more complex analysis. I used Azure Data Studio to build the notebook.

### Notebook Steps

1. The early part of the notebook I queried simple breakdowns to get an idea of how attributes distributed across each sex.

**Example:**
<img width="270" alt="Screen Shot 2022-10-08 at 6 13 47 PM" src="https://user-images.githubusercontent.com/103079066/194729613-50198a2e-fbc3-4388-9d31-63a31dd90ffd.png">

2. I aggregated a histogram of ages to find distributions of age groups most likely to have a heart attack, and generate averages for each age group in key attributes.

**Example:**
<img width="1073" alt="Screen Shot 2022-10-08 at 6 16 08 PM" src="https://user-images.githubusercontent.com/103079066/194729658-2308f41b-8068-4237-bda6-0fc9673c6756.png">

3. I further segmented ages into 10 bins to increase the n for outlier ages. This allowed for more trustworthy results across most age bins.

**Example:**
<img width="1435" alt="Notebook Screenshot" src="https://user-images.githubusercontent.com/103079066/194187229-3d75ebbd-2fa4-4b70-855e-f80427f25007.png">

**Example:**
<img width="1272" alt="Screen Shot 2022-10-08 at 6 18 39 PM" src="https://user-images.githubusercontent.com/103079066/194729730-2496fafd-2b56-4981-bb73-03d213d1aa81.png">

## Analyzing in Power BI

PDF Export of my Power BI pages are contained in the "Power BI" folder.

### PAGES:
 
1. Dashboard
2. Metrics
3. Time Trends
4. Level Comparisons by Gender
5. Mortality Rates
6. Age Bin Analysis
7. Time Quadrant Analysis

### Building the Dashboard

1. I imported the data through my Google Drive.
2. (No PowerQuery transformations were needed due to the editing of the raw data in Google Sheets.)
3. Used DAX to write a Mortality Rate metric
  - Mortality Rate = SUM(heart_failure_clinical_records_dataset[DEATH_EVENT]) / COUNT(heart_failure_clinical_records_dataset[DEATH_EVENT])
4. Created a series of pages with exploratory visuals in order to discover the most insightful trends.
5. Finished with the "Dashboard" page to compile the most compelling visuals generated throughout each page.

*Example:*
<img alt="Power BI Dashboard Screenshot" src="https://github.com/colbystout/Heart-Failure-Analysis/blob/main/Power%20BI/Dashboard%20Screenshot.png">

## Results

### Analysis Key Findings

1. Men are more likely to experience heart failure. This is already known but important to establish once again.
2. People in their 60s are most likely to experience heart failure.
3. Mortality rate increases as age increases.
4. The majority of deaths occured in 75 days or less days of final follow-up time by the scientists. The majority of patients would "survive" the heart attack if they stayed alive at least 75 days after the heart attack.
5. Hypertension and Anaeamia are higher risk factors of death than smoking are diabetes are.
6. The first quadrant of follow-up times, which also had the highest deaths, had far higher average serum creatine levels than the other three.
7. CPK levels are much more likely to spike high for men than they are women when serum sodium levels are 130 or higher.
8. Hypertension is more likely for men when serum sodium reaches 130 or higher.
9. Almost 1/3 of heart attackes resulted in death. (The data set does not have a high enough sample size or give a demographic/location to make further statements on this statistic.)

### Recommendations

1. Monitoring serum sodium levels and keeping them under 130 will greatly decrease the risk of heart failure.
2. Patients with the highest serum creatine levels should be monitored the closest during the first 3 months following a heart attack.
3. Patients with anaemia or hypertension, and especially those with both, should be treated with priority; there is almost a 40% mortality rate for these patients.
 - According to the [National Nutrition Council](https://www.nnc.gov.ph/regional-offices/mindanao/region-xi-davao-region/8185-anemia-and-hypertension-are-they-the-same), hypertension is shown to be caused by severe anaemia due to the body trying desperately to get oxygen to the body.

### Data Requests

1. A larger sample size.
2. Race/ethnicity demographic data.
3. Patient geographical location.

Collecting data on the above three criteria would greatly improve effectiveness and accuracy of analysis.

## Please feel free to message me further insights or recommendations; thank you for reading!
