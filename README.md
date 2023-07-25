# Predictors_of_Happiness!
![image](https://github.com/dharakhubchandani/Predictors_of_Happiness/assets/124633398/399dde9e-3bb9-4abe-8b69-3dc5e4ffc9ca)

**Purpose of the Project:**
This project is my class project for the course ISYS 812 – Python Programming. All the functions and libraries used in the project are a part of the curriculum for the course. The purpose of doing this project was to find out the predictors of happiness. 

The dataset that we collected was focusing on 3 variables – GDP of countries, the Happiness rank of countries and Gini coefficient. 

**About the datasets:**
There were 10 csv files which we extracted from Kaggle. Below are the sources of the files:

https://www.kaggle.com/datasets/ulrikthygepedersen/gdp-per-country?resource=download
https://www.kaggle.com/datasets/mathurinache/world-happiness-report
https://www.kaggle.com/datasets/ulrikthygepedersen/gini-index-per-country

**Data Exploration and Data Merging:**

The team initially thought to merge all the data sets but rapidly realized it would require more intricacy and attention to detail. The most significant issue began in the dataset provided by Kaggle for the World Happiness Report. The column titles were primarily the same for the first three years of the World Happiness Report (2015 - 2017). The second year introduced the confidence interval for the happiness score, but in 2018, the Dystopia Residual, a measurement of a country’s distance from dystopia, was removed as a value. In the two years following the first three years (2018 - 2019), the columns matched that grouping but not the first three years. The final two years of the World Happiness Report (2020 - 2021) also differed from all prior years. For example, the life expectancy score changed from measuring how life expectancy explains happiness to an average life expectancy in years. Despite many containing the same information, the mismatched columns created an insurmountable amount of null values. For example, the column titled ‘Trust (Government corruption)’ became ‘Perceptions of corruption’ but represented the same information for the category, despite the name change. 

Furthermore, the World Happiness data was downloaded as a csv file for each reporting year, a total of seven csv files. Instead of merging or concatenating the mismatched columns, the team opted to subset the years of the other datasets to keep merging and the risk of data loss at adequate levels to conduct data analysis in the latter portions of the project. For example, the GINI Index and GDP datasets were separated to match the years of the World Happiness Report, meaning for the years 2015 - 2021, we had seven subsets for the GINI and GDP datasets.

The most accessible column for people to recognize was the country name column. Therefore, the team selected the country name as the index column for reindexing at the final data frame. Next, the team pressed forward with the merging process using the identifying country name column. The first datasets to start the merging process were the World Happiness Report and the GDP datasets. The datasets were merged for each subset year (2015 - 2021). Despite the column naming issues identified previously, the team kept the column names of the World Happiness Report intact for this merging section.

The team experienced no significant data loss with the first merge and opted to take the World Happiness and GDP combined data through another merging interval. The final merge required blending the previously combined datasets with the GINI Index. Because the combined and GINI datasets were sectioned into years, the team followed the project’s standard protocol of merging the subset years, requiring seven more merges. The team was left with seven subsets, each containing the World Happiness Report, the GDP, and the GINI Index for the respective years. Still, the team needed to address the column names within the World Happiness Report to create a final data frame satisfactory for data analysis.

The complete data subset represents the year (between 2015 and 2021), the World Happiness Report for the year, the GDP for the year, and the GINI score for the year, identified and indexed by the country name. Through collaboration, the team identified the clearest titles for each column and named them accordingly. The team utilized the matching titles method to preserve the most data. Each complete data subset required the World Happiness columns to be identified, renamed, and sometimes dropped. 

Finally, with the column names matched, the final data frame underwent its last transformation process. The complete data subsets for each year were finally concatenated together. Still, the team needed to address the GDP issue; GDP was represented in string format—the values needed to be stripped of the commas, currency symbols, and periods. The team applied a replace function on the string symbols causing issues, converted the GDP values to integers, and finalized the data frame by setting the index to country (see Appendix, Figure 4). However, the 2020 and 2021 subsets left the data minimized to nineteen total values. The limited values would not allow appropriate data analysis, leaving the team to conclude the years could not be used for the final dataset. The team speculates the COVID pandemic left data severely underreported for those years. Nevertheless, the years could be held for other analysis, under the assumption that the data is not statistically significant and would require further research.

**Questions we wanted to answer:**

1.	Within the model, which variable is strongly correlated with Happiness Score? Is the model significant?
2.	What factors predict the happiness score of a country?
3.	Do countries with higher GDPs have higher happiness scores?
4.	Has Happiness increased over time?

