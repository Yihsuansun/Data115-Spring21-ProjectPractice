# Data115-Spring21-personal dataset project

This is a project on data analysis.

Washington state university----Data 115----personal dataset project

## Motivation

For this project, my original goal is to know "Is the graduation rate of high school really as high as we imagined."
I have searched for many different data, including the SAT scores of high school students, the rate of college admissions in American high schools, etc. The original goal was to find the relationship between the SAT scores and the high school graduation rate, or the relationship between college admissions rate and the high school graduation rate. Unfortunately, the SAT scores only represent the academic level of the high school students, and this doesn't seem to have a significant connection with the graduation rate. As for the admission rate of American universities. This data seems to be more related to graduation rate than SAT scores, but there is a problem, what if a student successfully graduates from high school but does not plan to continue to university? This is also a question that I must think about if I want to use this data.

In the end, I found the data "high school graduation rate of different groups of people." This is the data with a lot of information, and it seemed to answer my question. The high school graduation rate from 2013 to 2017 was not as high as we thought. This data also gave me another idea, the relationship between the graduation rate of various groups of people and the average graduation rate. This data has shown the graduation rates of many groups of people. I selected several groups of people to analyze. So my final goal becomes finding the correlation between the graduation rate of different groups of people and the average graduation rate. (Before the analysis begins, assume that there is a correlation, but the null hypothesis can be overturned)


## Data process

The first step of processing data is to start from importing data. Read "high-school-graduation-rates.csv" into the R file and name it. Before starting all the analysis, the most important step is to clean the data. There are lots of missing data in this data, and my purpose is to remove those rows that contain missing data. This step is very easy and can be done with na.omit() function.

```sh
GR <- na.omit(GR_O) 
```

After this, I checked again if other places need to make a change; the good thing is this data seems excellent, and no need to clean more, everything looks perfect. 

Before starting the next steps, I have to change some ranges of this data. I don’t want my chart to become weird because of some big numbers. So I created a new data which only include the high school with less than 5000 people. 


After processing the data, I created a new data frame according to the year. From 2012 to 2017, even though we can see from the data that the graduation rate continues to increase with the year, I still want to use boxplots to show more clearly conclusion. From the boxplot I made, I found something more interesting. Even though our graduation rate has risen, the real change is actually the distribution of the graduation rate. From comparing the charts in 2012 and 2017, we can find that the Mean has become closer to the lower quartile, which means that high schools' graduation rate with low graduation rates is also rising rapidly. Most high schools have higher graduation rates than before.


<img width="523" alt="Screen Shot 2021-04-25 at 5 46 44 PM" src="https://user-images.githubusercontent.com/46459933/116015478-3f6f7280-a5ee-11eb-9cb0-57fb1d1305be.png">
<img width="542" alt="Screen Shot 2021-04-25 at 5 46 50 PM" src="https://user-images.githubusercontent.com/46459933/116015490-472f1700-a5ee-11eb-9167-487481b933d8.png">


I used scatterplots to show the relationship between various groups of people and the standard graduation rate. Set x as the total graduation rate of all groups, y as the graduation rate of a specific group, and use the year to represent the color. I have drawn many different graphs. These graphs can be used to present the distribution of individual group graduation rates and total graduation rates.


One of the code are shown below
```sh
ggplot(data = GR_N, mapping = aes(x=All.Subgroups.Percentage.Graduated, y=White.Percentage.Graduated, color = Year..end.year.of.academic.year. )) + geom_point()
```

In the last part, I used regressions to find and plot the relationship between the graduation rate of each group and the average graduation rate. Among them, the white and Black or African American have a linear relationship with the average graduation rate.
In this part, I use the lm() function to complete linear regression.

one of the code are shown below
```sh
linearGR_AandW <- lm(All.Subgroups.Percentage.Graduated~White.Percentage.Graduated,GR_N)

summary(linearGR_AandW)

plot(GR_N$All.Subgroups.Percentage.Graduated~GR_N$White.Percentage.Graduated, col='blue')+abline(linearGR_AandW)
```
## Visualization

<img width="570" alt="Screen Shot 2021-04-25 at 6 19 27 PM" src="https://user-images.githubusercontent.com/46459933/116016878-d76f5b00-a5f2-11eb-8c48-fd590b55bd49.png">
<img width="574" alt="Screen Shot 2021-04-25 at 6 19 37 PM" src="https://user-images.githubusercontent.com/46459933/116016885-de966900-a5f2-11eb-94dc-2b1610301b5e.png">


The above two graphs are the two conclusions. The graduation rate of whites and African American have a linear relationship with the average graduation rate. Two columns are used to draw points, and linear regression is used to draw the relationship line.


## Analysis

I used several skills learned in the DATA115 class to analyze. First, draw several boxplots to represent the Males and Females graduation rate each year. From the boxplot, we can find that the number of graduation rates from 2012 to 2017  continues to increase, and by comparing the distance between the mean and lower quartile from 2012 to 2017, we can conclude that high schools' graduation rate with low graduation rates is also rising rapidly. In this project, I use scatterplots to show the relationship between the graduation rate of each group and the average graduation rate, where the color represents different years. From the graph, we can see that there should be a linear relationship between the graduation rates of whites and African Americans and the average graduation rates. Finally, we use the lm() function to confirm the conclusion of the previous step. There is a linear relationship between them, and their linear equations are y=-2.70594+1.00268x and y=0.35055+1.02969x. The final conclusion is that the graduation rates of whites and African Americans have a linear relationship with the average graduation rate; The graduation rate of other groups doesn't seem to have any connection with average graduation rates, the relatively small number of people may cause it.
