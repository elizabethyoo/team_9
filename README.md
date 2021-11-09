# Problem Statement
Small businesses have been hit hard by the pandemic and face ongoing challenges limiting business recovery.

Most businesses (99.7%) in the US are small businesses, which collectively employ almost half of the nation's private workforce, making them an integral part of the US economy. Unfortunately, more than 60% of small businesses report a moderate to large negative effect of the pandemic.

This report examines the different factors influencing US small business recovery during the pandemic, including coronavirus-related related and socioeconomic factors at the national and state level. Identifying these relationships will enable policymakers to focus on critical areas of improvement to support small business recovery in their cities and states. Companies can also utilize these insights to navigate the current economic landscape more successfully.

# Datasets

## Overview
The team initially identified two publically available datasets from the Small Business Pulse Survey and the Household Pulse Survey conducted by the US Census. These data were supplemented with unemployment data from the Bearua of Labor Statistics and COVID-19 vaccination, case, and death rates from the CDC. In combination, these datasets provided >50 variables related to small businesses, COVID-19, social and economic factors.

## Data Wrangling

For future time series forecasting, we decided to aggregate the data by month and merge on month and state. Each of the datasets presented unique challenges for data acquisition, cleaning, and aggregation to prepare it to merge into the main dataset.

### Joining our Datasets
The unemployment data is only available by month, the HPS data is available weekly as is the SBPS data - although the start and end of the weeks for the HPS data and the SBPS data are not aligned. Therefore, we decided that the most accurate time aggregation level is at the month level. The month assignment for the HPS and SBPS data will be based on the month of the “start of week” field. Vaccination rate data is available daily, real-time and the percentage values are As all datasets provide data at the state level, we will be joining the datasets together by state.

### Small Business Pulse Survey (SBPS)

The small business pulse survey data is quite fragmented - multiple questions are segmented by different fields (e.g., sector, state, employment class) as separate files. We focused on the index data provided at the state level. The index data are numerical qualifications of the survey results provided by the Census Bureau. We munged all the datasets, added “start of week” and “end of week” fields to serve as a time indicator before appending the weekly datasets together to form one file. 

### Household Pulse Survey (HPS)

The HPS data is also available as weekly datasets, similar to the SBPS data. We performed a similar exercise to download the available 36 weeks of data and append them into one file. As the HPS data already contains a week field, we did not have to add additional time indicator fields before appending the weekly datasets. We narrowed down the numerous survey column features and extracted the features regarding the difficulty in finding childcare, housing insecurity, and difficulty meeting basic needs. We also extracted demographic data (e.g. age, gender, etc.). We aggregated and resampled the data to a state and month level to match the SBPS and unemployment data granularity level. 

### Unemployment Data

The unemployment data is encoded with a Series ID that indicates whether the record is associated with unemployment rate, employment, unemployment or labor force. To filter the data, we use string splitting and key mapping to convert the Series ID to the state, date, and metric variables. We filtered the dataset to one metric - seasonally adjusted unemployment rate.

### COVID-19 Vaccination Rate Data
The COVID-19 vaccination data was downloaded from the CDC site, the index was removed and unnecessary columns were dropped. We aggregated by state and resampled by month mean for columns that contain values in percentages.

### COVID-19 Cases Data
The dataset contained cases and deaths as daily counts. To normalize by population, we joined the COVID-19 Cases and Deaths data with the estimated population data (by state) from the US Census. Additional processing for this data in the feature engineering section

# Project Datafolio
![TEAM_9_DATAFOLIO](https://user-images.githubusercontent.com/10517323/140938381-3b3e3867-ca4b-41ac-8e7b-c5a3877ea184.png)
