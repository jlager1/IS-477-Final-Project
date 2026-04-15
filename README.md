# Best Sports City in America: A Cross-League Analysis of MLB, NFL, and NBA

## **Contributors:**
- Rannin Gruen
- Jaedon Lager
- Arjun Sivasankaran

## **Summary:**

The goal of this project is to analyze sports performance across three major North-American sports leagues. This is Major League Baseball, the National Football League, and the National Basketball Association. We are doing this to determine which city demonstrated the strongest sports success over the past twenty years. While championship wins usually are the dominant force in many sports conversations, continued success across multiple leagues is not studied often. Our goal is to create a broader and more data-driven measure of city-level sports success by combining team performance data from different leagues into one complete dataset.

The motivation for this project comes from the idea that there are certain hubs in North America that are known for building strong sports hubs. Their fan bases and sports cultures can be seen as significantly stronger than other areas. One example is the dominant Boston, known for the Patriots, Celtics, and the Red Sox. Places like Boston are seen as elite sports markets, but those claims are typically from a place of opinion or recency bias, such as a strong championship run. By using historical data that contains objective metrics, we are looking to evaluate if these reputations are supported by results. We are also able to find insights that may not be readily seen without merging datasets from the three major sports.

For this analysis, we are using three datasets from publicly available sources. The NFL data came from Pro Football Reference, the NBA data from Basketball Reference, and the MLB data was obtained from Baseball Reference. These datasets contain team-level stats such as wins, losses, seasonal performance, and playoff appearances. Since the datasets are from different sources that have different structures, we will need to clean the data heavily in order to integrate them for meaningful insights. For data preparation, we are looking to clean any inconsistent column names, standardizing team and city labels, filtering records for records from the 1900s and on, and resolving any other issues that may arise during the cleaning process. We are going to use normalized metrics when merging the three leagues together, in order to ensure no bias to any one sport.

After cleaning and standardization, the three datasets are merged using city as a shared attribute. Once the dataset is integrated, we are able to compare cities based on combined success for the teams across all three leagues. This way, we will be able to evaluate overall consistency and some standout periods of success, like which sports contribute most to a city’s sports reputation, and whether or not a specific region in the USA performs better. As for extra cleaning, we made sure to only use data from the teams existing in 1900s and on, to be consistent throughout sports.

Through this project, we expect to create a ranked view on the strongest cities for sports based on real, objective results, rather than opinion. As this project requires a big merge and cleaning, we expect to learn real skills of documentation, cleaning, ethical data handling, and creating reproducible work. It demonstrates how using multiple different data sources and putting them all together can create strong insights and turn into a meaningful project.

## **Data Profile:**

For this specific project, we used three datasets that contain historical team performance for the MLB, NBA, and NFL. We chose these datasets because they provide key data and objective measures of historical team performance that can be compared across cities and locations. The central goal for these datasets after integration is to determine the city with the most sports success.

The raw data is stored in the GitHub repository as:

- `data/raw/mlb.csv`
- `data/raw/nba.csv`
- `data/raw/nfl.csv`

The cleaned data is stored in the GitHub repository as:

- `data/raw/mlb_cleaned.csv`
- `data/raw/nba_cleaned.csv`
- `data/raw/nfl_cleaned.csv`

The final merged dataset is stored under:

- `data/processed/city_sports_merged.csv`

1. **MLB Dataset**  

   a. **File Name:** `data/raw/mlb.csv`  
   b. **Original Source:** Baseball-Reference  
   c. **Structure:** The MLB dataset is a structured CSV file where each row represents a team’s franchise. It contains cumulative statistics. Some of the column names are Team Name, Playoff Appearances, etc.  
   d. **Content:** This dataset contains information all the way from the 1900s. It contains one row per team. This provides a lot more information from short lengths within the data, including data from active and inactive teams.  
   e. **Relation to Questions:** The MLB dataset contains all the data for the baseball teams per city, contributing an important factor to determining each overall cities’ success in sports. This dataset can also have some important insights into sustained success over periods of times, for a city.  
   f. **Ethical/Legal Constraints:** The data contains all public sports statistics, no proprietary or copyrighted information. It’s appropriate for use with proper citation.  

3. **NBA Dataset**  

   a. **File Name:** `data/raw/nba.csv`  
   b. **Original Source:** Basketball-Reference  
   c. **Structure:** This is also a structured CSV file containing franchise-level historical stats. Each row represents a team franchise, with cumulative and historical statistics. Some column names are: Team Name, Playoff Appearances, Seasons Played.  
   d. **Content:** The NBA dataset is from a similar source as the MLB dataset. It focuses more on franchise history than a team’s individual seasons. It includes active teams as well as potential teams that are not existing anymore.  
   e. **Relation to Questions:** For our analysis, a team's individual seasons are not necessary, so the NBA dataset we have will do. We would’ve potentially gained some more insights, but it was not necessary. Basketball performance is a huge measure of a city’s success from sports.  
   f. **Ethical/Legal Constraints:** All the information is publicly available team data. It is free to use for any academic use, and contains no sensitive data. We can use the dataset with proper citation.  

4. **NFL Dataset**  

   a. **File Name:** `data/raw/nfl.csv`  
   b. **Original Source:** Pro-Football-Reference  
   c. **Structure:** This dataset is also a structured CSV file and it contains franchise-level info about all of the NFL teams. Like the NBA dataset, this CSV has rows that represent teams, rather than individual seasons.  
   d. **Content:** This dataset summarizes the historical success of the NFL franchises and has indicators of the regular season performance. Since the number of NFL games played per season is lower than MLB or NBA, raw win totals will need further interpretation.  
   e. **Relation to Questions:** The NFL dataset contributes football performance to the city-level ranking that we are aiming to do, which is a big indicator of success in sports for a city. NFL success often has a major impact on people’s perception of a cities’ success due to how popular the NFL is.  
   f. **Ethical/Legal Constraints:** All information is publicly available team data. It is free to use for any academic use, and it contains no sensitive data. We can use this dataset with proper citation.
## **Data Quality:**

For our data quality analysis, we will be using the six dimensions of data quality in order to properly assess our quality. This is based on completeness, consistency, timeliness, validity, and uniqueness. Accuracy was accounted for, as these datasets are from a highly reliable source.

1. **Completeness** for all the datasets was overall very high. Core performance variables such as team names, wins, losses and seasons were all present. Some potential gaps were:  
   a. Missing city name in some of the sources  
   b. Franchises joining later vs. earlier (see below)  
   c. Mitigating for historical vs modern franchises  

- In order to mitigate these potential issues, we added city fields if necessary and filtered all records to the average score across their periods. For franchises joining later vs. earlier, we will need to be more careful of playoff appearance stats.

2. **Consistency** was a major challenge for merging the two datasets. One screaming example of this is with the ways the different data sets recorded wins and losses. For the NFL and the NBA datasets, you could see that the wins and losses were recorded as `W` or `L`. In the MLB dataset, it was `wins_total`. Another issue was team names containing potential semantic ambiguity, due to the use of abbreviations. 
- In order to resolve this, we standardized names for a team to just be a state. We also ensured to validate based on truth and trusted databases to standardize all other metrics, such as wins, losses, playoff appearances, and championships.

3. **Validity** was an issue to standardize across league game amounts. For example, season lengths for the NFL were vastly different from MLB or NBA games. For that reason, we couldn’t use raw win totals as a comparison metric. We therefore decided to use a normalized metric such as playoff qualifications, championships, and win percentages. It’s still important to keep total wins, but cannot be used to compare sport to sport. This ensures fair cross-sport comparisons.

4. **Uniqueness** didn’t seem to be an issue, as the dataset is smaller and duplicate observations are easily avoidable. The only issue we wanted to mitigate in terms of uniqueness was potential city relocations causing team name repeatedness. For example, the Charlotte Bobcats and the Hornets. 
- For that, we are merging by city and continuing to keep it as a talent based on location study.

5. **Timeliness** was not an issue except for the difference in historical franchises vs newly-found teams. 
- To mitigate that was quite simple, all that needed to be done was to base our analysis on playoff appearances as a percentage of seasons. There was no cleaning necessary for the dataset itself.

	After cleaning and any other transformation, our datasets were high quality enough to run any analysis we needed. The biggest issues with our specific datasets were the structural differences of each of them, and having to merge the different sources. Once we standardized the three datasets, they provided a stronger foundation for any necessary analysis. The final merged dataset is called `city_sports_merged.csv`. It supports visualization.
