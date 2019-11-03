# Shark Attack - Dataset cleaning and analysis
## Preliminary data cleaning
After importing csv file (which needed an attribute called encoding = "ISO-8859-1"), null values were checked.

There were columns almost empty, and others (age, time, species) almost 50% empty. The first ones were dropped, while the rest were discarded for analysis purposes as they did only provide information for a small portion of the data.

Regarding "Date column" it contained several formats, and some of them were not very relevant. It was considered to analyze the dataframe only using "Year" column.

Looking at the rest of the columns, many analysis could be made, but in order to focus on the relevant data for this particular checking, other columns were discarded. Finally, the columns to be included in the DataFrame were:

'''
["Year", "Country", "Case Number", "Activity", "Injury", "Fatal (Y/N)"]
'''

At this point, general purpose of the analysis and an hypothesis can be made: recent cases will be checked (after 1800) in order to determine if shark attacks happen more often in certain countries and in certain conditions.

The hypothesis is, surfing is the main reason of sharks attacks, being USA and Australia the main countries reporting these incidents.

## Cleaning data by remaining columns
1. Analyzing Year column

After checking the data, historical shark attacks will be discarded, and therefore rows before 1800 will be dropped. The reason of this is the data might be incomplete, and although it provides interesting historical insight, it will not provide relevant information for analizing reasons for shark attacks nowadays.

2. Analyzing Country column

Many countries are included in the dataset. In order to simplify further analysis, all countries with less than 25 incidents will be renamed as "Other".

To do this, too much code was used