# PrimeDash: Dynamic Dashboards for Amazon Prime Analysis in Power BI

## Problem Statement
This dashboard aims to enhance comprehension of the rising usage of the online streaming platform for watching movies and TV shows. It offers insights into the most favored genres and delves into the trends in release timing for both movies and TV shows across various years. Additionally, it enables the identification of TV shows with numerous seasons, aiding in understanding their success metrics. Moreover, it analyzes the prevalence of specific genres among TV shows with multiple seasons, providing further insights into viewer preferences and engagement patterns.

### Steps Followed
- Step 1: Load the data into Power Bi.The dataset is taken from kaggle.com
https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows?resource=download
- Step 2: Open Power query editor and in view tab under Data preview section, check "Column distribution","colun quality", "column profile" options.
- Step 3: Profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4: It is found that the field date_added contains 98% of the data empty and country contains 89% of the data empty and director contains 37% empty.So these columns are removed as part if data cleaning.
- Step 5: Attribute Duration contains both total duration of movies in minutes and total number of seasons in TV shows.
- Step 6: Therefore the column duration is split for total duration and no of season using the power query.

if [duration.2] = "Season" then [duration.1] else 0

- Step 7: In report view, under view tab, theme was selected.
- Step 8: In Visualization, piechart was choosen to know the total number of TV shows and Movies
- Step 9: Line chart is used to view the release of movies and Tv shows in each year
- Step 10: Three cards were used to view the Total videos available , Total time duration of the videos in Prime and average duration.Caculated using DAX

Total Time = SUM(amazon_prime_titles[Total Duration])

Total shows = COUNT(amazon_prime_titles[show_id]) 

avg.duration = AVERAGE(amazon_prime_titles[Total Duration]) 

-Step 11: Bar chart is created to view the top 5 longest duration of the movies
![Longduration](https://github.com/sudeeptha/Project-BI/assets/26385640/7156c67b-ad05-4f56-a4b5-64dd0c5b45fa)

![longdurationtable](https://github.com/sudeeptha/Project-BI/assets/26385640/75dabf5a-a828-4572-b17c-5e5dc8b059a6)

-Step 12: Clustered Bar chart is created to view the Tv show containing the maximum no of seasons.
-Step 13: Total number of shows according to the rating is viewed.

![seasons](https://github.com/sudeeptha/Project-BI/assets/26385640/fd4298ff-9109-4c7b-b916-f8ad77a79afc)

![seasontable](https://github.com/sudeeptha/Project-BI/assets/26385640/e656f1a1-35a1-4a16-bc1b-b2029bde6301)

## Report Snapshot (Power BI DESKTOP)

![dashboard](https://github.com/sudeeptha/Project-BI/assets/26385640/3dce9223-3022-4360-831b-8f976f6670f9)

## Insights
A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard

### [1]Total no of videos in Prime 
	
	Total number of TV Shows:7814
	Total number of Movies:1854

### [2] Total timimg of videos
	
	Total duration of Movies:713511 mins
	Total duration of TV shows:3195 mins

### [3]Longest duration of Movies
	From the data provided the longest duration is 601 minutes
	The movie name is Soothing Surf at Del Norte for Sleep black screen
	It is seen that the the genre of documentry and special interest conatins the longest duration.

### [4]Maximum Seasons in TV Show
	Amazing Race contains 29 seasons
	Most of the highest TV shows are of reality based.

### [5]Movies and TV shows per release year
	From the graph, it is evident that from 2018 there is an increase in the number of TV shows and movies release.
	It is understood that the platform has been popularised and has been increase in the views with the release of movies and TV shows.

### [6]Movies and TV shows by genre
	The most common genre for movies are drama and  genre comedy follows the second
	The most TV shows are in the genre for Animation,Kids and then followed by drama

### [7]Ratings of TV SHOWS and Movies
	In movies and TV shows the most videos are of rating 13+
 
	  








