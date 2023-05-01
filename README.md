# hubmap_analytics

Analyzing and Visualizing Usage for Common Coordinate Framework User Interfaces Using Google Analytics Data

Title: HuBMAP analytics

Mustafa Alsaegh.                                              Xuemei Hu.                                            Arpan Ojha.                                         Amanda Turney     
malsaegh@iu.edu.                                             xh18@iu.edu.                                       arojha@iu.edu.                                     turneya@iu.edu              

Visualization Goals & Needs
User Event Frequencies

The overarching goal of the client is to understand how users are interacting with the ASCT+B Reporter application in order to gain insight of where and how to improve the user interface. One research interest in particular of the client was to understand the distribution of user events such as page views, clicks, and scrolls. A statistical study can provide insight into the different ways users are interacting with the ASCT+B Reporter visualization with a particular focus on the insight needs of distributions and comparison.

The Google Analytics log dataset was cleaned and filtered for logs relating only to the visualization page (https://hubmapconsortium.github.io/ccf-asct-reporter/vis). The count of events per event type on this page is shown in the prototype bar graph below and allows for comparison of these frequencies across event types.

This initial visualization tells us that webpage events, which are exclusively mousemove event subtypes, dominate the total set of events that are captured. Beyond that, we see that click events and page view events have very similar counts. This is surprising because I would expect there to be many more clicks than page views as I would imagine a user would visit the page once but would click and scroll many times on the page as they interact.

However, we can further investigate this by looking at the distribution of click frequencies across users. The click event logs were grouped by the pseudo user id and aggregated by count per user. A prototype of this visualization is shown below in the histogram of click counts.

This visualization tells us that there are a lot of users that have very few clicks in the application but a handful of users that have a lot more, with one user in particular that has over 100 clicks. A potential research analysis could include trying to use unsupervised machine learning techniques, such as clustering, to label users as “casual” or “advanced” based on these types of frequencies across a multitude of user events. Comparing how different types of users interact with the application might be an interesting insight for the client to further pursue. While the above visualization can be done for any event type of interest, a new feature that could be of interest to also engineer and visualize is the session duration. 

The last visualization prototype is a bar graph of the page view event type counts per first level page within the application. This comparison would allow the client to understand what pages within the application are getting the most traffic. Below shows that the visualization web page does get the most traffic with the homepage as the second most visited, followed by the Documentation pages last. Potential interactions on this visualization could include filtering and looking at lower level pages.

Organ Tables

To understand organ tables we need to analyze temporal, topical and network visualizations. 

Topical visualizations are important to search the overall word frequency. To do this we need organ data in the frequency of appearance. The data would look like the following. The goal is to understand oval frequency. Temporal visualizations like trends of organ searches based on time. This data would be organ search data dependent on time. A simple trend bar graph on the number of searches divided across 24 hours of the day. This data is plotted on a bar graph with three parameters, x- time, y - frequency and various key/legends representing organ parts. This would help us identify temporal trends of these searches. An addition to the previous table would be a temporal line graph for the time for which data is available. Instead of coding based on time of the day, we would be able to correlate certain searches based on outbreaks or social hysterias based on time. A line graph with frequency on y axis and time on x axis is sufficient with the option to choose which organ to break down into would be a good marker. 




Tree network visualization can be used to identify the volume of searches and connection between them. If multiple organs are selected at the same time we could connect them in a network. This pattern can be plotted in a simple network tree visualization. This would help us gain insights into most closely related studies.

Visualizations are as follows:

Time of the day searched vs count of searches

Organ search frequency word cloud

Organ search frequency bar plot. Organ v/s count of searches.

Comparison Between Same Time Periods Across Different Years

Google Analytics is an important tool to track and report website traffic and is now the most widely used web analytics service on the internet. Our client utilizes Google Analytics to log the usage of their common coordinate framework that is Registration User Interface(RUI), Exploration User Interface(EUI) and ASCT+B Reporter. In an effort to improve these three user interfaces, our client recently implemented usage tracking via Google Analytics. Specifically, they used custom events to log mouse movement, clicks and organ tables loaded. The datasets were given access from the same time frame in 20211210-20220212 and 20221210-20230212. 

During 20221210-20230212, the datasets include 17529 user pseudo ids. During 20211210-20220212, the datasets include 39599 user pseudo ids. The users were reduced half this year compared to last year. The decrease in users needs to give the website a reminder to find out the reason. The dataset for the project comes as a CSV file. Both datasets include 9 columns which are 1. User_pseudo_id 2. Hostname 3. Page_location 4. Event_date 5. User first touch Timestamp 6. Event_timestamp 7.Event_name 8. Event_category 9. Event_label. 

To compare the differences in the same time frame between the two years, I used Tableau to do visualization. The first visualization is the total number of users' first touch in every week. Both visualizations are that the number of users’ first touch went up and then went down in the two weeks before christmas. However, the first touch users continued to increase after the new year in 2023 and it decreased in 2022. The second visualization is to compare the distinct count in different entry forms to the website. This didn’t make a big difference. Both have the largest number in webpage,  then page_view.

Data Export Formats

Gaining insights into the users’ export preferences of ASCT+B could help stockholders optimize the platform. To do this we filtered the event label column to include only the export events and counted the frequency of each export format. The most frequently exported format is PNG, with a count of 25. This finding is followed by Graph Data with count of 21, and JSON-LD with a count of 16. The fact that PNG is the most frequently exported format suggests that users may find this format more convenient and useful than others. 

After identifying the most frequently used export formats, we looked at the number of unique users who exported and found that out of the 240 users, 28 had exported at least once. This is approximately 11.67% of the total users. A pie chart of the top 10 users by number of exports and their preferred export formats was created. The chart revealed that users had different preferences when it comes to export formats.

We analyzed the organ frequencies for the exports made by the users of the platform. The results showed that the most frequently exported organ was bone marrow with a total of 20 exports, followed by blood with 9 exports, lymph nodes with 8 exports, kidney with 7 exports. We created a line graph that shows the number of exports for each organ. The results indicate that bone marrow is the most in-demand organ among the users of the platform.




Discussion of related work

Due to the popularity of Google Analytics data, there are many different dashboards and visualizations examples that can be found online. One such Tableau dashboard can be viewed at the link below: https://public.tableau.com/app/profile/technical.product.marketing/viz/WebsiteDashboardDemo_10_0/TrafficTrends 

Page view events are tracked over time to visualize the temporal component of the usage data as well as aggregated by count over the different pages within the application, which is similar to the prototype visualization above. Another example of Google Analytics data visualization is the Sankey Graph showing the temporal flow of how users navigate through the CNS webpage as illustrated in the Atlas of Knowledge on page 49. 

Lastly, the link below shows another Tableau dashboard that visualizes website clicks per hour as well as a heatmap overlaid on an image of the web page to visualize where the webpage is getting clicked. 

https://public.tableau.com/app/profile/rachel7046/viz/HeatMapofMainPage_15602656355340/WebsiteClicks 

Some past work on organ data visualization has been shown in the following links but there has been limited work in specifically categorizing organ data: 

RUI: https://hubmapconsortium.github.io/ccf-ui/rui/Links to an external site.  

EUI: https://portal.hubmapconsortium.org/ccf-euiLinks to an external site. https://www.nature.com/articles/s41556-021-00788-6Links to an external site.



Simple Statistics
User Event Frequencies

The client provided two datasets of Google Analytics usage logs for two different time periods: December 2021 to February 2022 and December 2022 to February 2023. Using all data between these two datasets, there are a total of 57,128 records for the entire application. However, when filtering for usage records only pertaining to the specific webpage within the application that has the visualization tool that they are interested in improving, there are 43,846 records.

Based on the user_psuedo_id column in the dataset, there are 552 unique users that have visited anywhere in the website application. However, when looking only at the visualization tool webpage specifically, there are 314 unique users.




Organ Tables

Over 17000 page visits originated from a total of 110 unique users for the most recent time period of Google Analytics records (December 2022-February 2023). Most of these users were very evenly distributed in regards to their purpose. There are a total of 28 organs. Small intestines were by far the most frequently searched organ with 1601 searches followed by 1594 lung searches. Six organs were searched over 1000 times which were small intestine, lungs, blood, kidney, liver and heart. We had some missing data which amounted to 10% of data loss. However we didn't have any losses in organ searches. Three unique hostnames were visited. Finally, the mousemove event category was 2500 times more frequent than the second most used in that category. This suggests that people spend quite some time trying to understand the hubmap.




Comparison Between Same Time Periods Across Different Years

The client provided two different datasets of Google Analytics records over the same time period between consecutive years: December 2021 to February 2022 and December 2022 to February 2023. The dataset corresponding to the earlier time period included 39,599 records whereas the more recent time period only included 17,529 records.




Data Export Formats

The analysis conducted on the data revealed some interesting insights about the export activities of the users. Although the original files had more than 17,000 rows each, filtering the event label column to include only the export events reduced the data to a mere 96 rows. One notable finding is that PNG is the most popular file format for exports, with a count of 25. We also determined that out of the 110 users on the platform, 28 had exported data at least once. This represents approximately 25% of the total users.

This small dataset provided valuable insights into the most frequently exported file formats, the number of users, and what organ tables were exported. However, it is important to note that these findings are based on a limited dataset, and may not be representative of the larger user population. Further analysis using a larger sample size or additional data sources could provide a more accurate picture of user behavior and preferences when it comes to exporting data.




Data Analysis and Visualizations
User Event Frequencies

Data preprocessing and feature engineering was performed to capture some important features of each user session within the application as well as features on the users themselves. Sessions were identified using the session_start user event log and included all chronologically ordered subsequent records for that specific user up until the next session_start event record. Features such as the session duration and user events per session were calculated and analyzed. At the user level, the number of sessions that a user had was calculated as well as a user classification label of engaged or disengaged. Disengaged users were defined as users who had only a single session on the visualization tool that lasted less than 2 minutes. Lastly, given the user event logs, it can be seen whether a user has visited any of the tutorial documentation or videos that are made available within the application that serve as a helpful guide on how to use the visualization tool. An additional feature that was generated at the user level is a flag for whether the user had visited any of the training/tutorial resources or not.

The analysis of user events is primarily a statistical analysis and resulted in a series of statistical visualizations in order to meet the insight needs of distribution and comparison. The first set of visualizations below show histograms of the session features. The far right visualization shows the comparison of distribution of session durations between all one-time users versus returning users.

The visualization on the bottom left is a refined version of the one given in a previous section by adding in the comparison of these user event frequencies between engaged users versus disengaged users. The bottom right visualization is a stacked bar chart showing the counts of users that are engaged versus disengaged and within those categories, the counts based on the training classification.




Organ Tables

We used topical, temporal and network visualization to gain insights. We used word cloud as shown above to identify the most frequently searched item per user. Temporal visualization used bar graph to represent the time of day when the organs were most searched. The tool was used and data was collected according to GMT which is 5 hours ahead of EST assuming most users are located in EST. Finally we used network tree visualization to map most frequently correlated organ searches by user. We used organ names as node labels and edges to signify connections in an undirected graph. We also used edge weight representing frequency of connection. This was done on python’s pyviz.

Network tree of organs. An accompanying html file can be provided to see the visualization in action.




Comparison Between Same Time Periods Across Different Years

One of the research questions of interest was to look for differences in the Google Analytics logs between the same time period across different years. A temporal trend of weekly record counts can be compared between the different years. The top two visualizations below show the count of weekly records for the December 2021 to February 2022 time period on the left and the December 2022 to February 2023 on the right.

The distribution of user event frequencies can also be compared across the years. The bottom set of visualization shows the counts of the different user events with the earlier time period on the left and the more recent time period on the right.

Data Export Formats

The analysis utilized four different types of visualizations to display different aspects of the data being analyzed. A line graph was used to show the number of exports for each organ, highlighting that bone marrow was the most in-demand. A stacked bar chart was used to display the correlation between time and export formats, showing how the formats changed over time. A pie chart was used to display the top 10 users by number of exports and their preferred export formats, giving a quick overview of the different formats used. Finally, a horizontal bar chart was used to show the most frequently exported files, allowing for easy comparison of the different file types being exported. Together, these visualizations helped to provide a comprehensive overview of the data and highlight important trends and patterns.

Key Insights
User Event Frequencies

Overall, we see that the number of sessions per user, the average session duration per user, and the average counts of events per session all have very right skewed distributions. This means that a lot of traffic on the visualization tool web page is coming from one-time users and/or very short sessions. We see that one-time users actually contribute the most to the number of very short session durations. However, there were some one-time users that still spent a substantial amount of time using the visualization tool.

When comparing the user event frequency between the engaged versus disengaged users, it doesn’t look like there is much of a difference in the type of events coming from two types of users. However, when we look at the training rates of the engaged versus disengaged users, we see that the engaged users have a 3x rate of having viewed any sort of training/tutorial documentation or video within the application. So this could be an indicator that some of one-time and short visits could be due to users not fully understanding how to use the visualization tool.




Organ Tables

The key insights gained were as follows:

Topic model word cloud suggests that Small intestine is the most searched model closely followed by lung
Temporal trends suggest that the most frequent searches are made between 1 and 4pm EST. This points to the fact that people either use it just after lunch or before leaving work at 5. It could also be the time window used to test the app. 
Network visualization suggests that uterus and ovary search are not paired with any other organ. People search lymph and blood with lymph and blood vasculature. 
Network map also points to a densely connected map with most organs paired with most other organs. 
Lymph, spleen and skin are most frequently paired followed by blood and eye. This is a curious trend because it is not immediately clear




Comparison Between Same Time Periods Across Different Years

In summary, the users were reduced in half for the most recent time period (2022-2023) compared to the year before. One of the reasons is that they developed three user interfaces (RUI, EUI, and the ASCT+B Reporter). Another reason is that the application was used more than the website in the later year.

There is also a difference in the weekly count of records between the two years. Both visualizations show that the weekly count increased some and then decreased right before Christmas. However, the weekly counts continued to increase after the new year in 2023 whereas it decreased in 2022. The second visualization shows that there isn't a large difference in the distribution of user event frequencies from the earlier time period to the more recent time period.




Data Export Formats

In our analysis of the data exports on the platform, we identified several key insights.

Firstly, we found that out of 110 users, 28 had exported data at least once, representing approximately 25% of the total users.
Secondly, we analyzed the most frequently exported file formats and found that PNG was the most popular format, followed by Graph Data and JSON-LD.
Thirdly, we examined the frequency of organ exports and found that bone marrow was the most commonly exported organ, followed by blood, lymph nodes, and kidney.
Finally, we identified the date of the highest number of exports occurred on 14/12/2021.

These insights provide valuable information about user behavior and preferences on the platform, which could be leveraged to improve the platform's features and user experience.

Problems surfaced during validation & redesigining
User Event Frequencies

One of the largest challenges of this project was scope and the number of different questions you could both ask and answer using the rich Google analytics logs dataset. A number of specific questions came from the client and more exploratory analysis and visualizations were developed by the team that resulted in a large number of piecemeal plots. Our redesign focused on addressing this issue by rebuilding our plots all in Tableau which allowed us to organize into dashboards and stories. Our end product and presentation allows for a structured approach to introducing the client project goal as well as the core questions and supporting visualizations we wanted to answer for this project.

Organ Tables

One of the major pain points was data cleaning. There were a few unintended organs listed in final visualization. We cleaned that and updated our visualizations. Another issue was the displays were quite varied due to us using very different tools like python, html and tableau. We consolidated all of the tables In a single tableau story.  

Comparison Between Same Time Periods Across Different Years

The dataset decreased half in 2022-2023(17529 user pseudo ids) compared to 2021-2022(39599 user pseudo ids).The client commented that it depends on where the events are coming from (whether it is coming from IU i.e. it is a developer or a legitimate user). For that, I will need to figure out all the events. And once that is done, the numbers will generally be closer. One really good instance that the professor shared with me for figuring out the events was that one group disentangled events by page_location, and based on that I would figure out whether the user is the developer or the legitimate user.

Data Export Formats

During validation, the main problem we encountered was the need to clean and preprocess the data before analysis. This was particularly challenging with the "event_label" column, which contained additional information that needed to be filtered out using Python. After preprocessing, we found that only a small portion of the dataset (60 rows out of 29,000) contained export activity, which made it difficult to draw firm conclusions. Our redesign addressed this issue by improving the data collection process and implementing better data cleaning and preprocessing techniques, which allowed us to work with a more accurate and reliable dataset. Additionally, we introduced new features and functionalities to the platform to simplify the export process and improve the user experience overall, which will help to increase the volume and quality of data in the future.

Discussion of challenges and opportunities
User Event Frequencies

A challenge we encountered during this project was that both users and developers/testers were using the ASCT+B application and thus it was hard to identify the usage patterns of our true users that we are interested in understanding. A future improvement could be to ensure that developers and testers use a separate dev or qa environment and only have the production environment monitored for usage logs. Another challenge was the psuedo_user_ids that Google Analytics creates. While we were able to track the same user id across multiple sessions, it was not clear how long Google will associate that particular user with the given pseudo_user_id and for how long that psuedo_user_id will persist for. This makes long-term user analysis more difficult. I think future opportunities could include augmenting this type of analysis with user interviews to learn what features are most helpful and which could be improved.

Organ Tables

A challenge we faced was unfamiliarity with new tools. We got over that by taking time off and learning independently and helping over zoom calls. A significant restriction in the project was the amount of data cleaning and making things proper for enough questions to be asked was a challenge. To add more we would benefit from additional data columns, context of the dataset. 

Comparison Between Same Time Periods Across Different Years

The big challenge that I met is the dataset is small and I can’t get more dataset related to the project, for example, user demographics dataset. Since I need to compare the difference in the same timeframe between two years, a more dataset would be better to give more insight. 

Data Export Formats

The main challenge we faced was the limited amount of data available for analysis, which made it difficult to draw firm conclusions and identify meaningful trends. Additionally, the uneven distribution of export activity among users and the lack of correlation between time and export formats presented further challenges in analyzing the data. However, this project highlighted several opportunities for future work, including expanding the scope of the analysis to include a larger dataset, exploring additional variables and features, such as user demographics and user feedback, and developing more advanced analytical models to identify patterns and trends. These opportunities will enable more comprehensive and robust analysis in the future, which can yield more meaningful insights and drive further improvements to the platform.



