# Exploring the role of news consumption on attitudes towards outgroups in the USA

<b> 0. Introduction </b> 

This report examines the impact of media consumption on attitudes toward outgroups
(refugees and immigrants) in the United States, utilising the 2021 Public Attitudes towards
Immigration (PATI) dataset. Our hypothesis investigates whether media consumption
correlates with attitudes towards outgroups and does this vary due to demographic
characteristics (such as age). The null hypothesis for this study posits that there is no
significant correlation between media consumption and outgroup attitudes, and that
demographic characteristics do not influence or moderate the relationship between media
consumption and attitudes towards outgroups.
We formulated our hypothesis from drawing on findings from various studies, noting that older
generations tend to hold more anti-immigration sentiments, favor traditional media, and lean
more toward right-wing ideologies (The Independent, 2023). In contrast, younger generations
appear more accepting, prefer online media platforms, and lean left (Migration Observatory,
2023). Additionally, our research indicated that men are generally more critical of immigration
than women (Financial Times, 2023). Building on these observations, we aim to explore
whether similar trends manifest within the PATI dataset.

<b> 1. Preparation </b> 

The first step in preparing for our data analysis was to clean the data - identifying the data
structure, creating a subset of the original data using only questions relevant to our hypothesis,
and handling missing values.
We created a new dataset which includes the following variables deemed most relevant in
studying our hypothesis, renaming each of the columns accordingly. For a full list of variables
included in our study, please see Appendix.
Our final dataset is structured as a Pandas DataFrame consisting of 1503 survey responses
from the USA only.
When examining our dataset, we noted that some values were marked with the integer ‘99999’.
We realised that this was a NaN value used as a placeholder for when there was no recorded
answer, as in the case of Social Media Consumption where the preceding question asked ‘do
you have a social media profile?’ We decided to replace these values with ‘1’, signifying ‘Never
Used’ within the survey codebook.

</b> 2. Initial Exploration </b> 
Our key variables within this study are:
- Moderating Variable: Demographic
- Independent Variable: News Media Consumption
- Dependent Variable: Attitudes Towards Outgroups
To begin our exploration, we performed a statistical analysis on each of these variables
individually.
Demographic - Age
We chose to focus primarily on ‘Age’ for our initial exploration of demographic features. We had
initially predicated that generational differences would have a mediating effect on both news
consumption and attitudes towards outgroups.
To explore the questions raised by our
hypothesis, we decided to group our
samples into generational - Boomers (born
1946-1964, age 57-75), Generation X (born
1965-1980, age 41-56), Millennials (born
1981-1996, age 25-40), and Generation Z
(born 1997-2012, age 9-24) (Parker and
Igielnik, 2019). We did this by creating bins
representing the limits of each age
range/generational category.
The bar graph shows that most of our
samples fell into the ‘Millennial’ category -
we speculated this could be because the
data was collected as ‘online’ survey, which would result in an increase of respondents from a
younger generation (as more inclined to use the Internet).
We also noted that although the ‘Gen Z’ category has a significantly lower count than the
others, this could be a result of the Gen Z age bracket falling from 12 -24, and our youngest
respondent being only 18.
Whilst these imbalances do not prove problematic for our statistical analysis of the data, we
made note to add weight to these values at a later point in our study to ensure that any insights
gained from the results would have relevance to the demographics-at-large and second, that
our analysis was precise.
News Media Consumption
In the survey, ‘news media consumption’ was measured on an ordinal scale of 1-7 with 1 =
Never 4 = Every week 7 = Every day (See Appendix). The questions asked the respondents
consumption habits of each of the news sources below (divided into Television Broadcasts,
Newspapers and Online News).
• Television Broadcasts: PBS, C-Span, Fox, MSNBC, CNN, One America, America News
Network (ANN), Local News Networks (Compilation), Nightly News (ABC, CBS, Fox, or
NBC)
• Newspapers: Washington Post, New York Times, USA Today, Wall Street Journal, Los
Angeles Times, The Boston Globe
• Online News: CNN, Fox, USA Today, New York Times, Washington Post, Wall Street
Journal
These news outlets were chosen by the surveyors for their quality or popularity, as well as to
capture differences between both public and commercial sources. (De Coninck et al., 2021).
To quantify ‘Social Media news consumption’
, we used the responses to the following
questions (measured on an ordinal scale of 1–7, with 1 = Never and 7 = All the time).
- On social media, how often do you:
o … read a blog about current affairs or politics?
o … comment on/discuss current affairs or politics?
o … follow a politician?
o … follow a political party?
To compare news consumption rates across the different types of media we first calculated the
average frequency for each, then created a new aggregate variable for:
- Broadcast News Consumption
- Newspaper Consumption
- Web News Consumption
- SM News Consumption
Analysis of the summary statistics revealed an average consumption frequency of 2 (infrequent
- Newspaper and Web News) and 3 (infrequent to weekly, Broadcast and Social Media News).
There is a similar level of variability in the data for each media type, except from Broadcast
news which is consumed at slightly higher frequencies.
Attitudes Towards Outgroups
To examine attitude towards outgroups, we used the data from two survey questions.
Respondents were asked to rate their ‘overall feelings towards refugees’ and ‘immigrants’ on a
‘feeling thermometer’ scale from 0-100 (negative – positive).
In order to create an aggregate variable (‘Outgroup Thermometer’) to represent
negative/positive attitudes towards outgroups (refugees and immigrants combined), we
analyzed the summary statistics and potential correlation between the two variables.
We calculated at Pearson Correlation Coefficient of 0.7, indicating a strong positive correlation
in attitudes towards immigrants and refugees. This was corroborated by the similar mean value
and thresholds of both variables. As a result, we moved forward with using our aggregate
‘Outgroup Thermometer’ variable.

<b> 3. Further Exploration </b> 

Exploring News Consumption Across Generations
First, we used the Kruskal-Wallis H Test to test the potential statistical significance of the
distributions of news consumption frequencies across different generations.
The Kruskal-Wallis H statistic of 330.836 suggests a significant difference between the groups.
Since the p-value is less than 0.05, we can interpret these results as showing that there is a
significant difference in news consumption frequency across generations.
From examining the boxplots for media consumption by generation we discovered that most
millennials consumed all forms of media on at least a weekly basis. In contrast, the Boomer +
category consumed all forms of media the most infrequently. With online media, half of the
Boomer + group never consumed at all. Surprisingly newspapers were more frequently
consumed by Millennials and Generation Z than Boomers +, which challenged our earlier
assumptions. We also observed that the Boomer+ data included numerous outliers at the
higher end of the news consumption scale (ratings 6-7) across all media types.
After examining the outliers further through the frequency distributions, we decided that they
represent legitimate variations in news consumption habits and should not be removed.
Exploring Attitudes Towards Outgroups across Generation
The summary statistics for cross-generational
Outgroup Thermometer indicate predominantly
neutral to positive attitudes, with mean values of 5.5
(Boomer+), 6.4 (GenX), 7.7 (Millennial) and 7.2 (GenZ).
The standard deviations of attitudes towards
outgroups vary across generations, with Gen Z (1.9) and Millennials (2.0) showing relatively
lower variability in responses compared to Gen X (2.7) and Boomers+ (2.5). This indicates that
Gen X and Boomers+ have more diverse opinions or a broader range of attitudes towards
outgroups in general.
Analysing Outliers - Millennials
Whilst the Outgroup Thermometer scores for Millennials group show mostly positive attitudes
towards outgroups, the outliers on the lower end of the scale (scores below 3), suggest a small
subset of individuals with extremely negative attitudes. Once again, we decided that these
outliers represent legitimate variations in news consumption habits and should remain as part
of the dataset.
Exploring Outgroup Thermometer Outliers - Gender
We decided to examine the Outgroup Thermometer outliers against other demographic
features in more depth to explore any potential patterns which could explain the negative
feelings towards outgroups. We began with Gender.
We found that the outliers were disproportionately
female; (1 = male, 2 = female, 3 = Other (with 0
responses). Outliers were also skewed towards
older generations;
Boomer+ 52
GenX 34
Millennial 16
GenZ 7
We then tested Religion, Marital Status, Employment Status, Income, Living Region but all
returned evenly distributed results. News consumption, however, showed some interesting
results.
Exploring Outgroup Thermometer Outliers – News Consumption
From examining the boxplots for media consumption by generation, we can see that whilst
most Boomer+ respondents consume news media on no more than a weekly basis (1-4).
Outliers are predominantly observed at the higher end of the news consumption scale (ratings
6-7) across all media types.
For each different news medium, outliers were disproportionately skewed towards low
consumption. We then created an “overall news consumption” variable that combined all of
these to create one succinct visualization.
Exploring Attitudes Towards Outgroups and News Consumption
A heatmap matrice was then created to explore the relationship between Attitudes Towards
Outgroups and News Consumption using both Pearson’s and Spearman’s Rank correlation. For
our Pearson calculation we normalised both variables using Min-Max normalization since they
were measured on different scales (0-100 / 1-7).
The results show a moderate positive correlation between attitudes and news consumption.
The associated p-values all fall below the significance level of 0.05, indicating that the
correlations are extremely significant. This provides us with strong evidence against the null
hypothesis, meaning that individuals who consume news more frequently tend to have more
favorable views of outgroups. However further statistical testing is needed to determine the
strength and significance of this relationship.
Since the results from both Pearson's and Spearman's methods are very similar, we can
conclude that the relationship between the variables is both linear and monotonic, and that the
choice between Pearson and Spearman does not significantly impact the conclusions we draw
from the data.

<b> 4. Analysis </b> 
   
To prepare for our variables for further analysis we:
- Used weighting to account for the disproportionality in the generational categories.
- Replaced numerical values in several categorical columns for demographic features
(Gender, Marital Status, Urban Density).
- Mapped ordinal income categories to their corresponding median values for each
income range, created a new numerical variable (Income_Numeric), and handled
missing values by replacing them with the median income.
- Applied Min-Max scaling to Income, News Consumption and Outgroup Thermometer,
transforming the values into a normalized range between 0 and 1.
K-Means Clustering
First, we chose to employ K-Means clustering to our data to identify underlying patterns and
similar groupings based on media habits, attitudes, and additional demographic features. Our
variables within this model were Gender, Marital Status, Urban Density and Income alongside
our original News Consumption, Generation and Outgroup Thermometer variables.
We determined that the optimal number of clusters for our dataset was 2 (with a silhouette
score of 0.352), providing the best balance between compactness and separation.
We then used boxplots to compare the different attitudes towards outgroups between clusters.
The boxplots show that:
• Attitudes towards outgroups: Cluster 0 holds relatively neutral attitudes to outgroups;
Cluster 1's attitudes are more positive.
• News consumption habits: Across all media, Cluster 0 had lower consumption rates
than Cluster 1
Further demographic analysis revealed more notable differences between the clusters:
• Income: Cluster 0 was largely comprised of top 20% wage earners - roughly twice as
many as Cluster 1
• Marital status: Cluster 0 incorporated a larger minority of unmarried people than
Cluster 1
• Gender: Cluster 0 was predominantly female; Cluster 1, predominantly male.
• Urban density: Cluster 0 comprised mostly of dwellers from suburbs and small towns;
Cluster 1 mostly lived in large cities.
These demographic differences may have interacted with media consumption to influence
individuals' attitudes towards outgroups.
Outliers were observed in both Cluster 0 and Cluster 1 across all variables, which may indicate
that some attitudes to outgroups are not yet explained by the demographic features included in
our model.
To summarise, these findings suggest that the K-Means model is effective at segmenting the
data into 2 groups, but further refinement such as examining outliers, adding or modifying could
improve the model's performance.
Multiple Linear Regression Model
We next fitted a multiple linear regression model that used demographic features and News
Consumption as the predictor variables, with Outgroup Thermometer as the response variable.
The model’s coefficients indicate that higher consumption of Web News (0.131) and Broadcast
News (0.137) is associated with more positive attitudes toward outgroups, while certain
variables like Gender: Male (-0.007) and Urban Density: Suburb (-0.042) are linked to more
negative attitudes. The R² score of 0.295 suggests that about 29.5% of the Outgroup
Thermometer variability is explained by the model, meaning that the model has some predictive
strength, but extraneous factors are still likely to play a contributing role. The Mean Squared
Error (0.0346) and Mean Absolute Error (0.1376) indicate that while the model's predictions are
relatively close to the actual values, there is room for improvement in terms of accuracy.
Overall, while the model highlights key relationships between the predictors and outgroup
attitudes, adding more predictors or applying more complex techniques could improve its
performance. This informed our decision to next fit a Random Forest Model.
Random Forest Model
We subsequently chose to fit a random forest model due to its ability to capture complex, non-
linear relationships between variables that our linear regression model potentially could not
fully account for.
The results of the model indicate a MSE of 0.0191 suggesting that the model is making fairly
accurate predictions, as well as indicating that the model's predictions are relatively close to
the true values. However, since ‘Outgroup Thermometer’ is measured on a scale of 0-10, there
may still be room for improvement in the model. The model’s R-squared (R²) value is 0.6851,
meaning that approximately 68.5% of the variance in the target variable is explained by the
model’s independent variables leaving 31.5% of the variance unexplained. This indicates that
there could be additional variables or refinements that might improve the model’s
performance, such as adding more relevant features.
We used the feature importance chart to provide a breakdown of which variables played the
biggest role in predicting the target variable – Attitudes Towards Outgroups.
We can see that Broadcast News Consumption contributed most to the model's predictive
performance. On the other hand, Gender appears to have a relatively low importance,
suggesting that it has little effect on the target variable compared to others. Overall, the chart
suggests that the model is relying heavily on News Consumption across all media types - as
well as demographic features such as Income and Generation - to make its predictions. These
results align with our hypothesis, that media consumption correlates attitudes towards
outgroups and that this varies according to demographic characteristics, such as age.

<b> 5. Presentation/Conclusion </b> 

Reflect on the outcome and the validity of your investigation. What are the answers
to your questions about the data? What additional steps could be included, if there
was more time? Discuss any limitations of your approach and your results. You could
reflect on all the previous steps of the data cycle.
Key Findings
• Attitudes towards outgroups skewed neutral to neutral positive across all generations.
This contradicted our initial assumption that older generations would have
predominantly negative feelings towards outgroups.
• There was a significant level of variance in news consumption frequency across
generations and media types. Boomers had the lowest consumption frequency and
Millennials, the highest. This is in line with our initial assumptions.
• On average, Millennials consumed newspapers and broadcast news more frequently
than Boomers, challenging our initial assumptions about generational behaviours.
• Younger generations’ higher consumption of web-based news indicates a shift in how
people access information and its potential influence on preconceptions and social
attitudes.
• News Consumption (across all media types, but especially Web News) has a moderate-
positive influence on attitudes towards outgroups. We also found that lower levels of
news consumption correlated with more negative attitudes towards outgroups. This
countered our initial assumption that the media at large would have a radicalising effect
on consumers, increasing negative views towards outgroups.
• We also found that demographic variables such as Income, Generation do indeed
moderate the relationship between media consumption and attitudes towards
outgroups. Urban Density, Gender and Marital Status also play a role, but to a lesser
extent.
Next Steps
- To improve our K-Means model, we would examine outliers in more depth and add or
modify the included features to improve the model's performance. We found that the
optimum K value was 2, which we felt to be an oversimplification of the complex
relationships between the variables.
- To improve the performance of our Random Forest model, we could explore using
Gradient Boosting. This could improve the model’s accuracy and achieve more precise
predictions. We could also group News Consumption, Gender and Urban Density, in
order to more succinctly compare the influence each demographic feature holds over
Attitudes Towards Outgroups.
- Undertake more statistical analysis into the demographic features eg. examining
income spread across generations within the study. This would allow us to gain a
deeper understand the moderating influence of these features within our regression
models.
- It could be beneficial to gather survey responses through analog means (eg. postal
survey) as well as online, to avoid a potential sampling bias in the case of individuals
who have limited access to the Internet or are not technologically literate.
- To gain further contextual understanding, we could conduct research into specific
media types to deeper examine their influence. Exploring other demographic
moderators could also provide future insights.

<b> x. Appendix </b> 

Variables included within reduced dataset.
Survey Code Variable Description Codes
cntry Country 8 = USA
V001 Gender 1 = Male 2 = Female 3 = Other
V002 Age -
V003 Marital Status 1 = Unmarried 2 = Unmarried
Cohabitation 3 = Married 4 =
Divorced/Seperated 5= Widowed
V009_1 Activity: Full-time job 0 = Does not apply 1 = Applies
V009_2 Activity: Part-time job 0 = Does not apply 1 = Applies
V009_3 Activity: Disabled 0 = Does not apply 1 = Applies
V009_4 Activity: Student 0 = Does not apply 1 = Applies
V009_5 Activity: Homemaker 0 = Does not apply 1 = Applies
V009_6 Activity: Unemployed 0 = Does not apply 1 = Applies
V009_7 Activity: Retired 0 = Does not apply 1 = Applies
V009_8 Activity: Active Duty 0 = Does not apply 1 = Applies
V009_9 Activity: Other 0 = Does not apply 1 = Applies
V10usa Highest Educational Degree 1 = Grade 1-8 2 = High school
incomplete 3 = High school graduate
4 = Technical, trade, or vocational
school after high school
5 = Some college 6 = College graduate
7 = Post-graduate training or
professional schooling after college
V011usa Net monthly household
income
1 = Lt $1000 2 = $1000 to 2999
3 = $3000 to 3999 4 = $4000 to 4999
5 = $5000 to 5999 6 = $6000 to 6999
7 = $7000 to 7999 8 = $8000 to 9999
9 = $10000 – 14999 10 = $15000 - 19999
11 = $20000 – 24999 2 = $25000 or more
13 = Refused 98 = Don't know 99 = No
answer
V013 Political affiliation 0 = Far left
10 = Far right
V020 Religious Affiliation 1 = Roman Catholic 2 = Protestant
3 = Other Christian denomination 4 =
Muslim 5 = Jewish 6 = Atheist(do not
believe in God)
7 = Agnostic (not sure there is a God)
V025usa_1 V025usa_2 V025usa_3 V025usa_4 V025usa_5 V025usa_6 V025usa_7 V025usa_8 V025usa_9 V027usa_1 V027usa_2 V027usa_3 V027usa_4 V027usa_5 V027usa_6 V029usa_1 V029usa_2 V029usa_3 V029usa_4 V029usa_5 V029usa_6 V033_1 8 = No religion 9 = Do not know
10 = Other
News media past
month: PBS
1 = Never 4 = Every week 7 = Every day
News media past
month: C-Span
1 = Never 4 = Every week 7 = Every day
News media past
month: Fox News
1 = Never 4 = Every week 7 = Every day
News media past
month: MSNBC News
1 = Never 4 = Every week 7 = Every day
News media past
month: CNN News
1 = Never 4 = Every week 7 = Every day
News media past month: One
America
1 = Never 4 = Every week 7 = Every day
News media past month:
America News Network
1 = Never 4 = Every week 7 = Every day
News media past
month: Local TV news
1 = Never 4 = Every week 7 = Every day
News media past month:
Nightly news on ABC, CBS,
FOX, or NBC
1 = Never 4 = Every week 7 = Every day
News media past month: The
Washington Post
1 = Never 4 = Every week 7 = Every day
News media past month: The
New York Times
1 = Never 4 = Every week 7 = Every day
News media past month: USA
Today
1 = Never 4 = Every week 7 = Every day
News media past month: The
Wall Street Journal
1 = Never 4 = Every week 7 = Every day
News media past month: The
L.A. Times
1 = Never 4 = Every week 7 = Every day
News media past month: The
Boston Globe
1 = Never 4 = Every week 7 = Every day
News media past month:
CNN.com
1 = Never 4 = Every week 7 = Every day
News media past month:
foxnews.com
1 = Never 4 = Every week 7 = Every day
News media past month:
usatoday.com
1 = Never 4 = Every week 7 = Every day
News media past month:
nytimes.com
1 = Never 4 = Every week 7 = Every day
News media past month:
washingtonpost.com
1 = Never 4 = Every week 7 = Every day
News media past month:
wsj.com
1 = Never 4 = Every week 7 = Every day
On social media, how often do
you… Read a blog about current
affairs or politics.
1 = Never 7 = All the time
V033_2 On social media, how often do
you… Write a blog post or vlog
about current affairs or politics.
1 = Never 7 = All the time
V033_3 On social media, how often do
you…Comment on/discuss
current affairs or politics
1 = Never 7 = All the time
V033_4 On social media, how
often do you… follow
a politician
1 = Never 7 = All the time
V033_5 On social media, how
often do you… follow
a political party
1 = Never 7 = All the time
V040 Feeling thermometer:
Immigrants
0 = Negative 100 = Positive
V046 Feeling thermometer:
Refugees
0 = Negative 100 = Positive
  
<b> REFERENCES </b> 

De Coninck, D., Duque, M., Schwartz, S. J., & d'Haenens, L. (2021). Public attitudes towards
immigration, news and social media exposure, and political attitudes from a cross-cultural
perspective: Data from seven European countries, the United States, and Colombia. Data in
Brief, 39(2021), 107548.
https://www.sciencedirect.com/science/article/pii/S2352340921008246?via%3Dihub#abs000
1
Parker, K. and Igielnik, R., 2019. Where Millennials end and Generation Z begins. Pew Research
Center. Available at: https://www.pewresearch.org/short-reads/2019/01/17/where-millennials-
end-and-generation-z-begins/ [Accessed 24 Nov. 2024].
