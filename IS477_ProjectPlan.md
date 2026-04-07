
# Overview:

The overall goal of this project is to analyze three datasets related to sports data, across three different sports. We want to begin by finding three suitable datasets, one for each of the following sports: MLB, NFL, and NBA. These three datasets should include data about each of the individual teams in these leagues, and data relating to how they performed over the past 20 years. Once we acquire these three datasets, we want to look through to ensure the datasets have data about the city they are from. If the datasets do not contain info of what city they are from, we plan on adding that through a cleaning process. We will use the official websites for these sports in order to add those columns.

The reason we want those columns is that our idea is to analyze locations(cities) for their skill level in sports overall. For that reason, our goal is to merge all of our datasets based on their location, specifically the city. If there are any single sports that have 2 teams for one city, we will decide whether to manually remove the less popular team or to include both teams. (for example, The Chicago Cubs, The Chicago White Sox). After merging the datasets and going through cleaning processes, we analyze the connection between the cities and the quality of skill for the sports.

  

# Team
Rannin Gruen - Team Lead, Data Engineer

-   Rannin’s role as organizer comes down to ensuring the project stays organized. It is just to ensure that the team will progress in a smooth manner, and the entire team is able to contribute.
    
-   Role as Data Engineer is around the acquisition and identification of datasets. He will be working on ensuring that datasets are relevant to our questions and goals from acquisition.
    

Jaedon Lager - Data Wrangler
    

-   Jaedon’s role as Data Wrangler will be to deal with overall data quality and cleaning the datasets. This will include oversight of the duty of merging datasets, however everyone will equally contribute to the production of the merge.
    

Arjun Sivasankaran - Data Interpreter
    

-   Arjun’s role as Data Interpreter is to ensure that the relevancy of the datasets and integration of datasets are clean. He will work with Rannin to ensure that the datasets are relevant to the topic and that the datasets have merged compatibility. He will also focus on a lot of the documentation for the project.
    

-   It is important to note that the roles will be loose, and there will be group work done for most steps, to ensure equality of learning.
    

  
  

# Research or Business Questions

 
The main question that we would like to address is which city has the overall strongest sports performance across the NFL, NBA, and MLB. Some supplemental questions we may be able to answer through the process of merging and cleaning will be: Which professional league contributes the most to every city? How does team performance vary by region when aggregated across leagues?

  

The main question we want to answer is which city is the best for professional sports. The supplemental questions are there to provide us with more visibility and context on the datasets. We will be using these questions to “get familiar” and likely answer them during the data cleaning process.

  

Datasets (we used 3 to match the professor’s requests, given we are a team of 3):

The overlapping attributes that the three sports datasets we chose are cities. Given the different sports related success, we can use this to answer our research question relating to the most successful sports cities in the country.

  

NFL Dataset ([https://www.pro-football-reference.com/teams/](https://www.pro-football-reference.com/teams/https://www.pro-football-reference.com/teams)): The NFL dataset is sourced from the site pro-football-reference.com, and it contains an organized list of every team's data, including their number of games played, playoff history, regular season stats, and much more.

  

MLB Dataset ([https://www.openintro.org/data/index.php?data=mlb_teams](https://www.openintro.org/data/index.php?data=mlb_teams)): The MLB dataset contains a more complex dataset that has the results of every team for every season, dating all the way back to 1876. This dataset contains a lot of information, including regular season data, playoff data, hitting stats, pitching stats, and ballpark. There are a lot of columns to sort through, and also the data is a lot larger compared to the other two because it lists out the statistics per year, not aggregating by team. This is something we will have to fix when cleaning the dataset to make sure they are all showing consistent data for the attribute (city).

  

NBA Dataset ([https://www.basketball-reference.com/teams/](https://www.basketball-reference.com/teams/)): The NBA dataset that we chose is sourced from www.basketball-reference.com, and it contains very similar data to the NFL dataset, as they come from the same parent company. There is data on regular season history, postseason statistics, and total games in the league. There are some NBA teams from the past that no longer exist, and we will have to take these factors out to make sure our “best sports city” is only using data from the past 20 years.

  

# Timeline

  

Our idea behind a timeline for this project is to have weekly checkpoints to ensure that our project moves at a steady pace.

3/27 - We are given some time for spring break, but in order to keep the project moving along, people will be responsible to complete some work over break and the week after break. We want to ensure Data Collection and Acquisition is for sure finalized. Along with that, documentation of Ethical Data Handling will be important as well, at least up to the point that can be documented. Arjun will be responsible for oversight of Ethical Data Handling and Data Quality, and Rannin and Jaedon will oversee Data Collection and Acquisition and Data Cleaning. Everyone will help with everything

  

3/31 - Interim Status Checkpoint due

4/3 - Our goal by this point is to have our datasets merged for Data Integration (Module 7-8) . A part of that will also be data cleaning as well. All 3 team members will participate in this process.

4/10 - A lot of the documentation on data lifecycle and file storage and organization will be caught up during this week, as the datasets would have been integrated and cleaned at this point. We will have a better understanding of the data sets as well. Arjun will work on Data Lifecycle and Rannin and Jaedon will work on file storage and organization

4/17 - During this week we will all work together to ensure we have workflow automation.

4/24 - During this week we will plan to ensure reproducibility of our project. We also want to make sure our Ethical Data Handling is up to par.

5/1 - Ensuring all proper Metadata Documentation. We want to be done with all of the project and documentation side. Final check in before submission.

5/3 - Final Project due

  

# Constraints:

One potential constraint across these datasets is the consistency of the data. Because the datasets come from different sources and represent different sports, the data structures may not match perfectly. For example, wins may appear in different formats such as W, Wins, or W-L, and team names may be labeled differently across datasets ( “Boston,” “BOS,” or “Boston Celtics”). These inconsistencies may require additional data cleaning and standardization before the datasets can be merged effectively. Another constraint is the difference in season structures across sports. Each dataset covers a different historical time range, which creates uneven coverage of seasons. For example, the baseball dataset includes seasons dating back to 1876, basketball begins around 1950, and football data extends back to approximately 1920. In addition, each sport has a different number of games in a season, which makes raw performance metrics such as total wins difficult to compare across leagues. As a result, normalization methods such as win percentage may be necessary to ensure meaningful comparisons.

There should not be many constraints when it comes to holding and preserving the data. Since the datasets we are using are all csv’s, they are easily downloadable so that we are able to integrate and run our analysis.

# Gaps

A major gap in the data is the lack of shared team identifiers across the datasets. For example, team abbreviations and naming conventions differ across sports, which may make it difficult to group observations consistently across the three datasets. Additionally, team relocations and name changes could result in duplicate or misidentified teams when the datasets are merged. To address this issue, we will likely need to create a standardized variable that uniquely identifies each team across all datasets. Another gap involves the need to standardize performance metrics across leagues. As noted in the constraints, each sport has a different season length, which makes direct comparisons across leagues challenging. To address this, we may need to construct standardized measures of team performance, such as win percentage or indicators for playoff qualification. These metrics will allow for more consistent evaluation of team success across cities and sports. A final gap involves validating the merged dataset after integration. It will be important to ensure that the merging process does not introduce duplicate observations or mismatched records. Additional checks will likely be required to confirm that each team-season observation is represented accurately and that the merged dataset reflects the correct information for each league and year.

> Written with [StackEdit](https://stackedit.io/).
