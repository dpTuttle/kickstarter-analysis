# Kickstarting with Excel

## Overview of Project

### Purpose

* To compare different kickstarter campaign outcomes based on launch date and funding goals.

## Analysis and Challenges

### **Analysis**

###### 1. Gathering Data to Evaluate Campaign Outcomes by Launch Date
* To gather data to perform my first analysis for campaign outcomes by launch date, using the raw Kickstarter data, I added an additional column for years (using the 'YEAR' function in Excel) to show campaign start date as 'year started'. Using this data set, I generated a Pivot Table using Parent Category 'Theater' as a primary filter and grouped the results in months with the outcomes as column headers and the count of each outcome type ('successful', 'failed', 'live' or 'canceled') as the values. Below are the PivotTable fields for reference:

###### **Excel Screenshot 1.1**
![Excel_Screenshot_3](https://cvws.icloud-content.com/B/AU_G-jS47hIKP2bjlxg3H386Bzs9AQvbsBjohlDfrX2kU4XEt1224yKp/Screen+Shot+2022-08-14+at+7.58.00+PM.png?o=AkVOJoLh1SjsJK24wnT5lyDwfN58vsfXtpX8ADRCrkT5&v=1&x=3&a=CAoga-3xyIYOlF6v8RA1GU4g5gsrI7JVmEpWJ79lsG_qaSMSbxCwrIT8qTAYsIng_akwIgEAUgQ6Bzs9WgS24yKpaie1vAlP8aM0dFRv9TIStpkeWDeW83Vj172xP2mdHun9LUJNSgjkH3dyJxqoHNZBGAtV4k_sxpSvvRIWStwpZFb6gXSw820Tth2DywMNFEfaOg&e=1660537013&fl=&r=ece5df1f-60b5-4a18-985f-6775ce5b069d-1&k=I6uQQ7-dUXciZ7x3fKIcEA&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=56&s=nxOjWxNmOX64BCDOuTsvMSzRmDU&cd=i)

###### 2. Gathering Data to Evaluate Campaign Outcomes by Funding Goal
* To gather data to perform my analysis for campaign outcome by funding goal, I used the same raw Kickstarter data, however, I generated multiple Goal ranges as categories within which to group the count of campaigns in subcategory 'plays' and their outcomes ('successful', 'failed', and 'cancelled'). Additionally, I added columns to capture the percentage of each outcome within each category. Below is the completed data table:

###### **Excel Screenshot 1.2.**
![Excel_Screenshot_4](https://cvws.icloud-content.com/B/ARW9LCsfawZi74k67sfvUJfHc2XiASelH5r7DEAi14haw5lUz-IX6XmR/Screen+Shot+2022-08-14+at+8.23.31+PM.png?o=AhumS9bXxsPwBaLL_NJEGqKE-T6MVNEk-Gt21k3cR4-p&v=1&x=3&a=CAogtlMCTUsrdecTLnm7Tgc28KtTA9Y9aOvgsNv31A-6OHkSbxDIp7T8qTAYyISQ_qkwIgEAUgTHc2XiWgQX6XmRaicqMeVzuNtpE1c6kbTcQYKuDG_eYzoJRPXQir2nAeo8zrV60rsphd9yJ0VT6REz2tHsAvbjY22jJBLdMmHFJ7zrShmDBawOsJF0bxy5LYJwuQ&e=1660537799&fl=&r=c4e4d354-bbf8-4d72-bd6d-8cb246ee1a35-1&k=dvt6eJQUd_teAjz-JIk86Q&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=56&s=e-qSV1hn2N-4hgEsEARoLeUt0XA&cd=i)

### **Challenges and Difficulties Encountered**

###### 1. Compound 'COUNTIFS' Statements in Excel
* My initital plan to count campaign goals between a specific range in Excel was to use nested 'IF' statements, however, the syntax was a bit difficult. I soon realized that the 'COUNTIFS' function does the hard work for me and I was able to list multiple criteria (including a MIN and MAX Goal amount) that only counted Goal amounts in this range. See the below screenshot for the successful formula noting both criteria for the Goal range greater than or equal to $1,000 and less than or equal to $4,999.

###### Excel Screenshot for Demonstrating 'COUNTIFS' Function in Analysis:
![Excel_Screenshot_1](https://cvws.icloud-content.com/B/AaYKgbDfne_XpeLThrdY7rMqVesNAeSpAR2JWCXAIX_ASdWvU-yttrX5/Screen+Shot+2022-08-14+at+7.15.50+PM.png?o=AqkceziEj8YHByABZWscicDVSik4TTwF5rPtOYeWhNMB&v=1&x=3&a=CAogqqBjrsFZF8KiKrM84dsHN8kIV1TnOgJEDrTDgD7qjucSbxCP3On6qTAYj7nF_KkwIgEAUgQqVesNWgSttrX5aieM__g0s6MVC0TpVPujkNFjyjUYcVBJiJxPG4JF3PHYxGL8B29KDRlyJ-W3ayXIYjGK7SYxLbcJ81hH7nTHNNDNlxz2W4j-DJGxbsgKVmqpbw&e=1660534480&fl=&r=df3de138-b0ef-4d0d-8116-f3ff0e2fab74-1&k=gG6Nb7cQ5ASlQ_MwugpOpw&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=56&s=mc7vZpICR5mBY92tyZLeEh5RQs0&cd=i)

###### 2. Accounting for Dividing by Zero in Formulas
 * Having '#DIV/0' errors in my tables would not have allowed for successful graphing of my results or further analysis. To overcome the divide by zero error that came up when there were no 'CANCELLED' campaigns that met my goal ranges (thus resulting in zeros) and I attempted to divide this result by the total number of campaigns in that goal range, I made the division formula for the percentage the input to the 'IFERROR' formula in Excel to show 0% if dividing by zero campaigns. The resulting formula and output can be seen in the below screenshot:
 
 ###### Excel Screenshot for Demonstrating 'IFERROR' Function in Analysis:
 ![Excel_Screenshot_2](https://cvws.icloud-content.com/B/ATPUed1Mr4kHoONQCHdBOdja0FAWAdV2X6KvW32JuR3DA1-SJ57wo6gd/Screen+Shot+2022-08-14+at+7.17.27+PM.png?o=Al-snjI9nLNg4dFdlSRIoi_bLP3XsS0BXARcfGDNLeOB&v=1&x=3&a=CAog2AFJmvAdQ5yWM7TJbOm9UHUxVioF7VNwiYcr2khyTRkSbxDPoKX7qTAYz_2A_akwIgEAUgTa0FAWWgTwo6gdaieex7GmL7SaGX__AevDsQd8tRVp8rMcXv758RhPt8zFwyTPYLLGTk5yJ8Mtx3wPUw93UDe-vuMnzlMY8i3LLWvV4FyPx3iPjffeeTnet666Aw&e=1660535455&fl=&r=c28a6341-5434-46af-8c04-73367559c4c1-1&k=w1NjJBc_ObzIvjJ0HpRFKQ&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=56&s=g7E9W3tBOnqUoTVteC_OJyDJvYg&cd=i)
 
 ---

### Analysis of Outcomes Based on Launch Date
* The data suggests that across all campaigns in parent category 'theater', the month in which a campaign launches may correlate to the outcome of the campaign but not uniformly. There is not much variation in the number of 'failed' campaigns (the range is roughly 35-50 failed campaigns monthly). However, there are particular months that result in consistently poor outcomes. Overall, the data demonstrates that the month in which a campaign is launched has a higher effect on a 'successful' campaign outcome rather than a 'failed' one. We can extropalate that 'failed' campaigns most likely do not fail as a result of the month in which they are launched, however, 'successful' campaigns benefit from a particular launch month. The below graph highlights this correlation:

###### **Graph 1.1: Theater Campaign Outcomes by Launch Date**
![Excel_Graph_1](https://cvws.icloud-content.com/B/AQjngO18ux6ihOQ4BScuWl-dx5X2ARlM8HYvRdgSeZEqIgVCygsEpyq1/Theater_Outcomes_by_Launch-Date.png?o=Astqsb8w5RNqME2HslMv5_W3KyK_1T93HHkgeg8eiOnv&v=1&x=3&a=CAoggkkAixI-CKalhX-KG1zIQZ7rWcEHCFhTx2Qsdu6QOE4SbxD02e78qTAY9LbK_qkwIgEAUgSdx5X2WgQEpyq1aif1OdFyeRQtnkQnXKDuO2rbgrfboG_ELWKWe5xWpABzDVQ5ABPoNvhyJzD_-3rUsx56B78xtz05lvncFtE7QMIuW_SQgVBjlWc8rt0kJNoIUw&e=1660538755&fl=&r=dd376969-d81a-44e7-9399-9ffaccb239ae-1&k=Sy03A_ul4hTLgqeAD_0gGg&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=56&s=wfWDbt66yO94xV73lnddKLtVMlU&cd=i)

### Analysis of Outcomes Based on Goals
* The data suggests that across subcategory 'plays', the range of the campaign goals is significantly coorelated to the outcome of the campaign. As the graph below details, campaign success rates rise and fall correlative to the goal presented for the campaign. It also demonstrates, that, at a certain goal threshold, a campaign is more likely to fail. Additionally, there is data to suggest that even campaigns in the higher goal range, see a higher probability of success, however, there is a threshold for this range as well.

###### **Graph 1.2: Outcomes Based on Goal**
![Excel_Graph_1](https://cvws.icloud-content.com/B/AerHWpDuYuvYVzHDNUlDMiO56BeLAQ7gVKv32neYdXShd9VQnYeheYU3/Outcomes_Vs_Goals.png?o=AqH5G28anm5d6WZRfb9FP3lHAvxmcIBSulAmojTy3wOJ&v=1&x=3&a=CAogWuRk0qTHDyWxvA9HqBHkNyq5Q8xB_BUHC44A1gXJJ4gSbxCTkaD9qTAYk-77_qkwIgEAUgS56BeLWgSheYU3aic88iGwdcBUmaB_o6OJRoTh5wFgtqoOLuyuYTIX-IsnQdY52G1A6NlyJwoGy-mA9XIJR2FZu-5W-R0-NSL4i26a2LZ5BLP9OK05T6sZUr1qpg&e=1660539565&fl=&r=8706de64-1f1b-4bee-9ea7-d4d25fe21652-1&k=mrpdP2lAoBl6bRfBBWvkow&ckc=com.apple.clouddocs&ckz=com.apple.CloudDocs&p=56&s=TxxU2mQmNUiU2wBYpQXyDBm5DJo&cd=i)

## Results

- **What are two conclusions you can draw about the Outcomes based on Launch Date?**
1. We can conclude that campaigns launched in May, June and July have a higher probability of success than campaigns launched in other months. We may also conclude that the month in which a campaign launches as a greater effect on the probability of success but does not have a higher effect on the probability of failure. 

2. We may also conclude, that, while launch date is not as significant to a failed campaign outcome as it is to successful one, there are particular months that have less than average failure rates (January, March, September, November). While campaigns launched in these months would not have a higher likelihood of success, they may benefit from a lower liklihood of failure. 

- **What can you conclude about the Outcomes based on Goals?**

1. We can conclude that there is a correlation between the range of a campaign goal and the liklihood of success. Of the 694 'successful' campaigns in subcategory 'plays', 76% of them were in the goal range of $0 - $4,999. These campaigns had an average success rate of 74%. The higher the goal range, the lower the success rate. For example, campaigns in the goal range of $5,000 - $24,999, all demonstrate a 50% success rate. One could argue that it is wiser to target a campaign goal less than or equal to $5,000 as this demonstrates a higher probability of complete funding. While one may be able target a campaign goal up to $25,0000 and still benefit from a 50% success rate, other factors in the campaign may become more important than just the goal amount. This analysis does not have the data to determine what those other factors may be. 

- **What are some limitations of this dataset?**
1. From this data, we can only succcessfully argue correlation, not causation. There may be other factors that contribute to campaign success other than the month in which it is launched and the target goal amount. For example, as noted above, campaigns with goal targets between $5,000 and $25,000 show a 50% success rate. There are clearly other factors here that contribute to campaign success or failure at these goal levels that this data set does not include. 

- **What are some other possible tables and/or graphs that we could create?**
1. From this data set, we may also be able to generate target goal range and launch date analysis for other campaign types to compare to our data set and validate our findings. We may find that these success factors are only relevant to parent category 'theater' and subcategory 'plays.'
