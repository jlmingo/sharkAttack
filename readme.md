# Shark Attack - Dataset cleaning and analysis
## Preliminary data cleaning
After importing csv file (which needed an attribute called encoding = "ISO-8859-1"), null values were checked.

There were columns almost empty, and others (age, time, species) almost 50% empty. The first ones were dropped, while the rest were discarded for analysis purposes as they did only provide information for a small portion of the data.

Regarding "Date column" it contained several formats, and some of them were not very relevant. It was considered to analyze the dataframe only using "Year" column.

Looking at the rest of the columns, many analysis could be made, but in order to focus on the relevant data for this particular checking, other columns were discarded. Finally, the columns to be included in the DataFrame were:

"""

["Year", "Country", "Case Number", "Activity", "Injury", "Fatal (Y/N)"]

"""

At this point, general purpose of the analysis and an hypothesis can be made: recent cases will be checked (after 1800) in order to determine if shark attacks happen more often in certain countries and in certain conditions.

The hypothesis is, surfing is the main reason of sharks attacks, being USA and Australia the main countries reporting these incidents.

## Cleaning data by remaining columns
**1. Analyzing Year column**

After checking the data, historical shark attacks will be discarded, and therefore rows before 1800 will be dropped. The reason of this is the data might be incomplete, and although it provides interesting historical insight, it will not provide relevant information for analizing reasons for shark attacks nowadays.

**2. Analyzing Country column**

Many countries are included in the dataset. In order to simplify further analysis, all countries with less than 25 incidents will be renamed as "Other".

**3. Analyzing Activity column**

 First, fields were renamed in the main DataFrame with following criteria:

        a) If contains swimming, rename to Swimming
        b) If contains diving, rename to Diving
        c) If contains surf, rename to Surfing
        d) If contains fish, rename to Fishing

Then, activities with less than 10 ocurrences were re-classified as "Other"

**3. Analyzing Injury column**

Some values were renamed to in Fatal Y/N column.

Then, Injury and Fatal Fatal Y/N columns were double checked to avoid fake fatal reports. There were none.

**4. Attacks by country**

A bar chart was plotted to see in which countries there were most attacks. This resulted in seeing that in USA, Australia and South Africa there are many of them. The column "Other" is significant, but it as said before, it is made from countries with less than 25 incidents in more than 200 years, while only in the USA there were more than 2000.

**5. Activity by relevant country and worldwide**

Pie charts for USA, Australia, South Africa and Worldwide were plotted to see which activities were more related with shark attacks.

In general, Surfing, Fishing and Swimming and seem to be the most risky activities in this context. This confirms the hypothesis, although it is surprising that fishing is so frequent when it comes to shark attacks.

**6. Activity by relevant country and worldwide**

Finally, a bar chart with non-fatal, fatal and unknown attacks in the last 10 years was plotted. It shows a clear majority of non-fatal accidents.

Conclusion of analysis: most of the attacks in the last 200 years were placed in USA, Australia and South America. The most risky activities during these attacks were surfing, fishing and swimming. Most of the attacks don't result in death.
