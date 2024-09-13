# NFL-Offensive-Effectiveness-Analysis

This is a project I completed for my intro statistics class that I took during the Spring semester of 2021. This class utilized a statistical software that came with the required textbook.

This project attempted to analyize the importance of high powered offenses for super bowl winning teams during the 2010's. To do this I created a statistic that quantified a football 
offenses production called "Offensive Points Created" (OPC). OPC is a statistic made up of all offensive touchdowns plus attempted points after touchdowns and attempted field goals 
for a team during the regular season. Offensive Points Created is essentially how many points an offense puts their team in position to score.

I then was asked to create a model to explain this OPC statistic. To do this, I examined a couple of factors that contribute to an offense's success. These factors were total 
first downs, third down completion percentage, and fourth down completion percentage. Total first downs is the amount of first downs, or progression of 10 yards within 4 attempts 
a team achieves in all 16 of their regular season games. Third down completion percentage is the team's ability to extend drives as fourth down is often used to punt the ball away 
if a team does not achieve a first down in their first 3 tries. If a team elects to risk a turnover and go for another play on fourth down, that gives rise to the fourth down 
completion percentage statistic. These three factors are each important to OPC because if an offense is able to string together long drives through first down accumulations, whether 
that is on third or fourth down, then they are more likely to either score a touchdown or put their team in a scoring position through field goal attempts. 
I ran a multiple linear regression to determine the importance of these parameters. These parameters were found to be statistically significant as a result of a t-test in which all of 
the parameter coefficients had a p-value that was less than .05.

<img width="512" alt="Screen Shot 2024-09-13 at 1 25 13 PM" src="https://github.com/user-attachments/assets/96741cab-6b68-4b61-a031-9e3a8714e0ea">

The coefficient estimates from this table can be used to create the following model: 

`Offensive Points Created = -141.76597 + 1.3011071*x1 + 1.7662826*x2 + 0.30155208*x3`

Where x1 is a team’s regular season total first downs, x2i s a team’s regular season third down completion percentage, and x3 is a team’s regular season fourth down completion percentage.
The adjusted R-squared value for this regression is .686 which means that 68.6% of OPC is explained by these variables. This is a relatively high number especially when working with a dependent variable that comes from human performance.

As part of the assingment, I then used this model to construct predictions for each team’s regular season OPC during the 2010’s. Each year, 12 teams advance to the playoffs 
and continue to compete for a chance at a Super Bowl victory. To simulate this process, we can draw a random sample of 12 of these predictions and find a 95% confidence interval 
about the sample mean. This means that we are 95% confident that the true population mean for OPC for that regular season is within this interval. We can then see if the 
Super Bowl winning team’s OPC is included in this interval or not for each year. This creates the following table:

<img width="507" alt="Screen Shot 2024-09-13 at 1 29 47 PM" src="https://github.com/user-attachments/assets/fe4b18c0-92fc-4208-8ea7-cc7bd13f47ab">

Out of the ten years of the decade, 6 of the Super Bowl winners had OPC above the sample mean’s confidence interval, 3 of the winners’ OPC was within the interval, and 1 of the winners’ OPC was below the confidence interval. 
The results indicate that in order for a team to reach the glory of being Super Bowl champions in the 2010’s, they had highly effective offenses.

This project was not super technical or difficult but that aligns with the fact that this was for an intro class with a prebuilt software frame to help with the technical elements.


Residual plots of the linear model:

<img width="354" alt="Screen Shot 2024-09-13 at 1 32 04 PM" src="https://github.com/user-attachments/assets/7530c297-4d38-4f99-8d70-00c2ad074fd0">


Data - “2020 NFL Team Scoring Statistics: The Football Database.” FootballDB.com, 
www.footballdb.com/stats/teamstat.html?lg=NFL&yr=2020&type=reg&cat=S&group=O&conf=. 
