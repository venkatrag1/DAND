# Visualization of Baseball Data Set in Tableau

## Link to Dashboards

### Initial Version (v0.0)
https://public.tableau.com/profile/venkatraghavan.ramesh#!/vizhome/Baseball-Stats-v0/BaseballStats

### Intermediate Version (v1.0)
https://public.tableau.com/profile/venkatraghavan.ramesh#!/vizhome/Baseball-Stats-v1/BaseballStats

### Final Version (v2.0)
https://public.tableau.com/profile/venkatraghavan.ramesh#!/vizhome/Baseball-Stats-v2_0/BaseballStats

### Datset URL (Udacity)
https://www.google.com/url?q=https://s3.amazonaws.com/udacity-hosted-downloads/ud507/baseball_data.csv&sa=D&ust=1544043493098000

## Summary
This visualization of the baseball dataset illustrates the effect of handedness,
height and weight on the scores of 1157 baseball players.

The primary story communicated by the visualization is as follows-
- Batting averages follow a normal distribution with mean around 0.25 whereas
number of Home Runs is a right skewed distribution with a long tail.
- Around 60% of the players tend to be right-handed no matter how we filter on 
the scores. In general, left handed players tend to have higher rates of home
runs as evidenced by the higher mean and median values for this category.
Their batting averages too, tend to be slightly better than the right handed 
category.
- Batting average is mostly similar across various player heights and starts
dropping after 75 inches. Likewise Home Runs also tend to peak for the 75 
inch height bin. 
- Batting averages tend to be more consistent for players in the sub 180 lb 
category. Home Runs do not seem strongly correlated with weight.


## Design

Since the home runs were long tailed, with a large range, we will use 
Logarithmic transform on the axis wherever applicable.

The primary filter will be on the metrics itself - ie. the batting average 
and home runs, as this will allow us to narrow in on say, the top scorers
or simply ignore the outliers. 

For instance, by default we set the minimum batting average to 0.01 and
minimum home run count to 4 to discount the zero valued entries.

It would be good to display the number of players after filtering against
the original sample size to get an idea of how much smaller our dataset is
after filtering and we will display this to the right, next to the filters 
and legends.

We begin by looking at the distributions of the metrics themselves. 

We will use barcharts and histgrams to look at the distribution for each
of the columns, and then use a box and whisker plot to compare it to metrics
if the column is categorical. When the column type is numerical, we will 
plot it against the metrics as scatter plots.

For the points themselves, we will set the Opacity at 50% to allow for an
alpha of 0.5 and set shape to a filled circle and lower the size. 

Whenever the overplotting is manageable, we will represent subsets using color
encoding. When the overplotting is high, we will facet on the subset category 
instead.

We will get rid of the title of the sheet from the dashboard and increase the 
size of axis label and add units to it, to convey the chart purpose with a low
data-ink ratio.

We will use the Analysis tab to show reference lines such as the mean wherever 
appropriate.

We will add the player name as Tooltip so that hovering around points of 
interest will help identify them.

Finally, inorder to relate height and weight, we will create a BMI column and 
encode BMI class (normal, overweight, obese) using color.

We will setup the story such that we begin by exploring the metrics space, set 
appropriate filters and then investigate the correlation of the metrics with
each column beginning with handedness, then height and finally weight.

We will wrap the filters in light blue background to draw attention to them.

We create Aliases for handedness to have more descriptive labels and we 
limit to two plots per dashboard to avoid clutter, having a distribution
and then impact plot for each of the columns.

## Feedback
##### Peer review
- Might be interesting to see if its BMI rather than just height or weight
that is an indicator of the fitness and by extension the scores of the players.
- Start with looking at score distributions in the beginning so that someone
new to baseball can also see the typical ranges and averages for batting average
and home runs.
- Add units to the legends.

##### Udacity review
Please communicate your findings to the reader by placing it as captions. 
Please avoid using abbreviations like R, L, and B. You can have 2 plots per 
dashboard. Including more plots make it cluttered.


## Resources
Understanding the baseball metrics- http://m.mlb.com/glossary/standard-stats/batting-average
How to calculage BMI- http://extoxnet.orst.edu/faqs/dietcancer/web2/twohowto.html


