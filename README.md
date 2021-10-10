# Problem Description
## Overview of Problem and Why it Matters
The World Economic Forum states that 34% of small businesses in the United States are still closed due to the COVID-19 pandemic. However, there has been a spike in new business applications, beginning in late 2020 and continuing into 2021 for non-traditional retail businesses. Based on the North American Industry Classification System (NAICS) code assigned to these businesses, ten industries account for 75% of the spike. The Nonstore Retail industry dominated this growth and accounted for 33% of the uptick in new business formation. Other growth industries include Professional, Scientific, and Technical Services, Truck Transportation, and Accommodation and Food Services. 

This investigation will provide an understanding of what factors relate to small businesses recovery during the COVID-19 pandemic, whether that be internal or external factors and whether industry plays a part. Identifying these relationships will enable small businesses to focus on critical areas of improvement to work towards recovery. Companies can also utilize these insights to navigate the current economic landscape more successfully.

## Problem Definition
This investigation will examine the different factors that affected small businesses in the United States through the lens of the COVID-19 pandemic and the recovery rate of small businesses. To do so, we want to develop a recovery rate score that predicts the speed of recovery for small businesses. We will explore the overall effects of the pandemic on small businesses and the factors that may be related to recovery, segmenting our data by state. We will also explore features that may relate to recovery in more detail to determine which has a higher correlation with recovery vs. not. For our project, we will focus on the following features and their relationship with recovery:  covid rate, vaccination rate, childcare access, employment, housing insecurity, difficulty paying for necessities.

# Datasets & Preliminary Data Preparation

## Dataset Details
This project is based on two main datasets - the Small Business Pulse Survey (SBPS) and the Household Pulse Survey(HPS) conducted weekly by the US Census Bureau from May 2020 to the present date. The SBPS data is available as collapsed summary statistics by state, large city, sector, sub sector, and business size. In contrast, the HPS microdata has respondent level survey data. Both of the data sets are large - covering thousands of businesses and households per week. However, due to the collapsed nature of the SBPS data, we will not be able to look at factors that influence individual businesses, but instead can look at statewide or industry wide factors.

Additionally, we will be gathering unemployment data provided by the US Bureau of Labor Statistics. This data will be used as an unbiased source of unemployment data which is a feature to be explored for potential relationships with recovery rate. 
