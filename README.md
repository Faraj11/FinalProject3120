# CIS 3120 Final Project
## By: Faraj Arvid

### [Video Presentation](https://www.youtube.com/watch?v=P8wBLTAJ26M)
### [API Documentation](https://www.api-football.com/documentation-v3)

### Project Purpose and Functionality
My final project aims to build an API-driven application that integrates data analysis, Object-Oriented Programming (OOP), and visualizations to analyze 
football/soccer data. My chosen API was API-FOOTBALL, an API that offers extensive data on football leagues, teams, players, etc. I chose this API because it merges my
big passion for football and my keen interest in data and analytics.

This project allows me to apply the data analysis skills I developed this semester to take metrics/data and transform them into digestible information and charts. Through 
the API, I strive to analyze both team and player performance, visualize trends, and then determine whether the data aligns with the "eye test" (watching matches). 
Similarly, I want to ensure that my analysis is thorough by exploring the context and limitations of the data, which will allow for a better interpretation of the results.

### Installation Instructions
1. Download GitHub Repository
   - Clone or download the project files from the GitHub repository.
2. Create an Account
   - Go to [API-Football](https://www.api-football.com/) and sign up for a free account.
   - Log in to your account and navigate to [your profile](https://dashboard.api-football.com/profile?access) to find your API key.
3. Set Up the API Key
   - Create a new file in the project directory named `API_key.py`.
   - Add the following code to `API_key.py`:
   ```python
   API_KEY = 'your_api_key_here'
   ```
   Replace `your_api_key_here` with your actual API key
4. Verify Necessary Libraries
   - Ensure the following Python libraries are installed:
     - `requests`
     - `pandas`
     - `matplotlib`
5. Run the File
   - Open the project in Jupyter Notebook or VS Code for the best experience.
   - Run the script to view the outputs and visualizations.

### API Architecture
![image](https://github.com/user-attachments/assets/bb41ecef-a349-4dd6-a2fb-4e4eb3e7865e)

The above screenshot is from the API documentation and shows all the endpoints and their parameters. The two boxes highlighted in green are the two endpoints I focused on for this project. For the standings endpoint, I utilized it to fetch standings from various leagues across the world for a particular season for examination. For the players endpoint, I used it to fetch the players who received the most red cards in certain leagues for a particular season to test a certain hypothesis. Further details on the analysis of these API fetches are provided in the next section below.

### Data Visualization Interpretation
For some context, one of the main inspirations that I had for using API-FOOTBALLI was to create visualizations that would test certain stereotypes and common beliefs that football fans have. For example, many fans believe football outside of Europe is worse and at a lower standard, or that footballers born and raised in the Brazilian style are the most gifted players in the world. 

I decided to narrow my project to two certain questions:
- The English League is the most popular league worldwide and is regarded as the most exciting. But which league is the most exciting league in the world?
- The Italian League has a reputation as the most defensive and easiest league to get injured in. But which league is the most dangerous/dirty league in the world?

#### Most Exciting League Visualization:
![image](https://github.com/user-attachments/assets/36195eb3-68f3-4760-89de-2e0188fbe70a)

I decided to define the most exciting league as the one where the most goals are scored. Goals are 100% the excitement factor in football and most people consider low-scoring games to be boring so it is evident that high-scoring games are exciting. Rather than compare the total goals scored across each league, I compared the goals scored per game across each league. This is because comparing the total goals scored would be skewed in certain leagues due to a significant disparity in the number of games played. Using goals scored per game normalizes the data and allows for better comparison across leagues.

The bar chart reveals that the German league had the most goals scored per game at 3.17. This means that on average, games in Germany tended to end with 3 goals scored per match. The English league is second with 2.85 goals scored per game. Based on this graph, it seems that the German league and not the English league is the most exciting. However, the German league only plays 306 games as opposed to the 380 games played in the English league every season (values taken from the code file). The extra 74 games can contribute to fatigue and explain why the English league has a lower goals scored per game value compared to the German league. Additionally, the difference between the goals scored per game between England and Germany is only 0.32 which is fairly small and probably not noticed at all by fans. 

Conclusion: the English league is definitely one of the top and most exciting leagues in the world but saying it is "the most exciting" may not be correct.

#### Most Dangerous/Dirty League Visualization:
![image](https://github.com/user-attachments/assets/c237eb75-1c02-4ff9-a0c2-3b2c2d4ee6ce)

I decided to define the most dirty/dangerous league as the one where the most red cards are accumulated from players. Red cards are usually given to players for violent conduct, serious foul play, or excessive force. The severity of the infraction by the players determines their suspension which could range from days to months. I used a pie chart to compare the distribution and % of red cards. The API only includes the top 20 players with the most red cards earned per league per season, so the sample size for each league is fairly small at 20.

The pie chart reveals that the Spanish league had the largest % at 28.70%. This value means that of all the red cards accounted for in the data, about 29% of the red cards were earned by players from the Spanish league. The Italian league is tied for the third-largest % at 17.39%. Based on this pie chart, it seems that the Spanish league and not the Italian league is the most dangerous/dirty. The fact that the Spanish league is  1st is interesting because it also has a reputation for physical play but is better known for the players' passing and skills. As mentioned before, the API only includes 20 players for each league for red cards earned per season, so the small sample size can explain why the Italian league is not 1st in this visualization.

Conclusion: the Italian league is up there as one of the most physical/rough/dirty leagues in the world but it may not be "the most dangerous" as many proclaim.

### Limitations of the Data and Analysis
Many older fans of football are not impressed by sports analytics and think that analytics cannot take into account many factors and as a result, they base their fandom on watching games and the eye test only. Working on this project helped reinforce the idea that numbers can "lie" and context is almost always needed when examining analytics and statistics, especially in scenarios involving sports where so many factors can influence a variable. From the generated visualizations and analysis, it is clear that there are some limitations to this data and what it implies. The limitations include:

- I only used 5 leagues around the world because these 5 have been known as the top 5 leagues in the world for as long as I have watched football. They are all from Europe and overlap in many ways and it is common practice to group these 5 in an exclusive class for comparison. Using only 5 leagues certainly limits the scope of this project and its findings, but it allowed me to complete all the parts that I desired to complete and still produced a satisfactory result in my opinion.
- As stated before, I measured the excitement and entertainment of a league based on the assumption that more goals equal more entertainment/excitement. I believe this logic makes sense but there are 100% other factors that may influence the excitement of a specific league match including player injuries, match time/location/scheduling, importance of the match, etc.
- As stated before, I measured the danger and physicality of a league based on the assumption that physical players play dirtier and get red cards. I believe this is the only way I can quantifiably measure physicality in any manner, so even though external factors can influence the roughness of a league and its players, this assumption is needed to be able to conduct the resulting analysis.
- The sample size of players with the most red cards earned in a season was limited to 20 per league by the API. This is most likely one of the limits of the free version of the API but it results in a very small sample size that may not provide an accurate representation of the actual red card distribution across the top 5 leagues. Potential solutions to this problem could be using the premium version of the API or another football API entirely.
- The visualizations and data analysis is entirely based on only the 2022 season. This season is the latest season of data that is available on the free version of the API. Regardless, utilizing earlier seasons and comparing the metrics and data to this season would be useful to determine if the data from this season aligns with other years or if any of the values from this season are outliers and out of the norm.
