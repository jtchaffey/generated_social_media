# generated_social_media
Analysis of social media post trends using a randomly-generated dataframe using functions available through packages in Python.

**Data Understanding**

The dataset is composed of 500 observations of 3 attributes for social media posts - date of the post, category of the post, and the number of likes the post gained.
Analysis of these posts could improve understanding of which categories of posts are able to attract the greatest level of social media engagement, and identify trends among posts.
However, this dataset was simulated to create values for each observation, encouraging this project to develop an approach to social media post analysis, rather than perform more specific analysis with this particular dataset.
Several limitations were caused by creating and using simulated data. Each date could only provide one category and like amount, and each post could only be represented by one category.
These limitations do not fully encompass how a post may fit into several categories at once, or the density of posts being made per day, but do reflect how data could be structured for use in analysis.

Data exploration began with examining the first rows of the dataframe, and calculating value counts of posts for each category. 
Following steps identified if the dataframe included any missing or duplicate values. An alternative dataframe was created here to preserve the original dataframe, and create a new one to work with and manipulate going forward.
Because of the way the dataset was simulated, each observation could not be a duplicate because each entry has a unique date. Similarly, missing values were not included in the possible range of the simulated data to include.
However, these steps could be considered for data from other sources, which may require additional data cleaning steps compared to those used here.
Then, data types for each variable were checked. The `date` variable was `datetime`, `category` was `object`, and `likes` was `int64`, which were all applicable to later steps of analysis.
Again, the project includes steps of changing these columns to different data types, which may be used with data from other sources. Data types were checked again afterword to ensure these changes occurred properly.
To conclude data cleaning in this instance, value counts for categories were checked once again.

**Data Visualization and Analysis Techniques**

Data visualization began with summary statistics about the data's `likes` values. The data still contained 500 entries as intended, with an average of 5097 likes. Values ranged from 37 to 9999 likes, with a standard deviation of roughly 2889.
Quartile scores were also calculated and included in the table of summary statistics.

Visualizations included boxplots and histograms for these data. An initial boxplot was used to visualize many of the summary statistics of `likes` values. 
No outlier values were found in this case, with the boxplot whiskers spanning the range of `likes` values observed in the table.
A histogram plotting `likes` and individual post counts was then constructed, aiming to identify the distribution of posts that were able to achieve different values of `likes`. 
A trendline was applied to this visualization as well, but no distinct distribution was observed from this plot.
When using data from different sources, this type of visualization may be useful in determining how frequently posts are reaching high values of `likes`, and whether the distribution of social media post likes is normal or not.
An additional boxplot was used to breakdown `likes` values by category.
This was useful in determining which category of posts had the greatest range of `likes`, which had the highest average, and determining if any of the categories behaved more unpredictably than others.
In this case, all of the categories had ranges which were similar to one another, and many categories had similar average `likes` values. Only one category, `fashion`, had a noticeably lower average than others.
Quartile markers had the most variation across categories, with `health` and `travel` having the smallest differences in values.
This would suggest that there is a higher consistency in `likes` achieved by posts in these categories when compared to others.

To clarify the category-separated boxplot, additional statistics were calculated using the `groupby` method.
The average value of `likes` for the `fashion` category was lower than the other categories at 4399.
The `music` category had the highest average `likes` value at 5510.
Many of the other averages fell between 4700 and 5100, including `culture`, `fitness`, and `food`.

The final visualization was a histogram plotting `likes` and post counts, broken down by `category`. With 8 post categories, this visualization was a bit of a mess, but provided the desired information.
If a similar analysis was performed, this visualization would likely need improvements to identify learnings and insights.
In this case, the histogram was able to display a count of posts which reached different `likes` thresholds.
It was shown that `music` had 12 posts which reached more than 9000 `likes`, making it the category where this occurrence happens the most.
Posts falling under `family`, `food`, and `travel` were all also identifiable through this visualization, reaching 8, 7, and 6 posts with greater than 9000 `likes`.
Considering these values to the previously calculated value counts for each category, `music` was observed to have a high-performing post 12 of 76 times, `family` 8 of 65 times, `food` 7 of 63 times, and `travel` 6 of 61 times.
This ratio of high-performing posts only decreases with the other categories, but may be overall insignificant findings.
However, this approach could be used with other datasets to check for categories with high-performing posts, which would expand helpful insights.

**Insights and Conclusions**

Conclusions drawn about this specific dataset seem reasonable to take several insights. 
The initial distribution of posts across each of the categories was reasonably balanced, with each having a minimum of 50 entries and maximum of 80.
That said, the point that this data is simulated should be reiterated.
The processes used to clean, visualize, and analyze the data are reasonable methods, but the conclusions drawn here should not be applied to a broader body of data.

Several categories stood out as having the highest-average performing `likes` values, as well as numerous high-performing individual posts. 
The most optimal category for engagement was `music`, having the highest average `likes` and the most high-performing posts.
`family` is the second-best option, with 8 high-performing posts and 5351 `likes` on average.
`travel` is the third option, with 6 high-performing posts and 5291 `likes` on average.
Interestingly, `health` and `food` were categories with a high `likes` average and significant count of high-performing posts, respectively.
`health` posts reached an average `likes` value of 5394, while `food` had 7 high-performing posts (ranking it 3rd).

Additional analysis could be performed using additional bodies of data.
The conclusions drawn here may not be consistent, and should be checked against other sources.
This could be done either through joining this dataframe with others, or conducting similar analytical steps to different data, drawing conclusions, and comparing those findings.
Data on `date` was also not implemented in this project due to its simulated nature, but it may be a viable method to investigate post engagement for different categories across time in an alternate project.
Identifying trends in a category, identifying the reasoning/events, and using the data to test a predictive model could be useful in future analysis of social media.

Limitations for this dataframe come from it being single-entry - that is, one date has one category and one like value. 
It neglects posts that are able to encompass multiple categories at once, which closes off multiple avenues of potential analysis.
If a post could have multiple categories, it would be possible to see which combinations of categories are able to drive the most engagement, and whether that combination has an effect that is different than each category separately.
It would also be possible to investigate which categories are most influential by comparing more differences in posts.
It is understandable that this limitation is in place for the purposes of conducting this project, but is an interesting consideration.
