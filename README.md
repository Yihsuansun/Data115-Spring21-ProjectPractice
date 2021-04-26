# Data115-Spring21-personal dataset project

This is a project on data analysis.

Washington state university----Data 115----personal dataset project

## Motivation

For this project, my original goal is to know "Is the graduation rate of high school really as high as we imagined."
I have searched for many different data, including the SAT scores of high school students, the rate of college admissions in American high schools, etc. The original goal was to find the relationship between the SAT scores and the high school graduation rate, or the relationship between college admissions rate and the high school graduation rate. Unfortunately, the SAT scores only represent the academic level of the high school students, and this doesn't seem to have a significant connection with the graduation rate. As for the admission rate of American universities. This data seems to be more related to graduation rate than SAT scores, but there is a problem, what if a student successfully graduates from high school but does not plan to continue to university? This is also a question that I must think about if I want to use this data.

In the end, I found the data "high school graduation rate of different groups of people." This is the data with a lot of information, and it seemed to answer my question. The high school graduation rate from 2013 to 2017 was not as high as we thought. This data also gave me another idea, the relationship between the graduation rate of various groups of people and the standard graduation rate. This data has shown the graduation rates of many groups of people. I selected several groups of people to analyze. So my final goal becomes finding the correlation between the graduation rate of different groups of people and the standard graduation rate. (Before the analysis begins, assume that there is a correlation, but the null hypothesis can be overturned)

```sh
npm install my-crazy-module --save
```

Windows:

```sh
edit autoexec.bat
```

## Data process

The first step of processing data is to start from importing data. Read "high-school-graduation-rates.csv" into the R file and name it. Before starting all the analysis, the most important step is to clean the data. There are lots of missing data in this data, and my purpose is to remove those rows that contain missing data. This step is very easy and can be done with na.omit() function.

```sh
GR <- na.omit(GR_O) 
```

After this, I checked again if other places need to make a change; the good thing is this data seems excellent, and no need to clean more, everything looks perfect. 

Before starting the next steps, I have to change some ranges of this data. I don’t want my chart to become weird because of some big numbers. So I created a new data which only include the high school with less than 5000 people. 
## Visualization

After processing the data, I created a new data frame according to the year. From 2012 to 2017, even though we can see from the data that the graduation rate continues to increase with the year, I still want to use boxplots to show more clearly conclusion. From the boxplot I made, I found something more interesting. Even though our graduation rate has risen, the real change is actually the distribution of the graduation rate. From comparing the charts in 2012 and 2017, we can find that the Mean has become closer to the lower quartile, which means that high schools' graduation rate with low graduation rates is also rising rapidly. Most high schools have higher graduation rates than before.


<img width="523" alt="Screen Shot 2021-04-25 at 5 46 44 PM" src="https://user-images.githubusercontent.com/46459933/116015478-3f6f7280-a5ee-11eb-9cb0-57fb1d1305be.png">
<img width="542" alt="Screen Shot 2021-04-25 at 5 46 50 PM" src="https://user-images.githubusercontent.com/46459933/116015490-472f1700-a5ee-11eb-9167-487481b933d8.png">


Describe how to install all development dependencies and how to run an automated test-suite of some kind. Potentially do this for multiple platforms.

```sh
make install
npm test
```

## Analysis

* 0.2.1
   * CHANGE: Update docs (module code remains unchanged)
* 0.2.0
    * CHANGE: Remove `setDefaultXYZ()`
    * ADD: Add `init()`
* 0.1.1
    * FIX: Crash when calling `baz()` (Thanks @GenerousContributorName!)
* 0.1.0
    * The first proper release
    * CHANGE: Rename `foo()` to `bar()`
* 0.0.1
    * Work in progress

## Meta

Your Name – [@YourTwitter](https://twitter.com/dbader_org) – YourEmail@example.com

Distributed under the XYZ license. See ``LICENSE`` for more information.

[https://github.com/yourname/github-link](https://github.com/dbader/)

## Contributing

1. Fork it (<https://github.com/yourname/yourproject/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

