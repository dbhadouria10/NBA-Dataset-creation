Program (python) version 3 and above 11/27/2022

# NBA-Dataset-creation: Collecting Data for Future Predictions of NBA Games During Regular seasons.
Created an NBA dataset through extensive data acquisition and initial preprocessing. Our dataset incorporates a wealth of statistics and historical data, providing valuable insights for predicting team and player performance.

MOTIVATION:

•We would like to provide a preprocessed dataset for future winning predictions of any game of the NBA basketball league by leveraging statistics, historical data, and prediction analysis. Our dataset will be useful for predicting the winning percentage of a team as a whole and individual players such as two-point field goals, offensive rebounds, assists per game, personal fouls, etc.

CODE STYLE:

•Functional coding style,
•Procedural Coding Style.
	
 
CODE EXAMPLE:
# API Calls to pull team and player information from sport radar:
def get_team_json_resp(season_year, access_level, version, language_code, nba_season, format_var, your_api_key):

  team_id_url = f"https://api.sportradar.us/nba/{access_level}/{version}/{language_code}/seasons/{season_year}/{nba_season}/rankings.{format_var}?api_key={your_api_key}"

  return requests.get(team_id_url).json()

def get_seas_json_resp(season_year, access_level, version, language_code, nba_season, format_var, your_api_key):

  seas_stat_url = f"https://api.sportradar.us/nba/{access_level}/{version}/{language_code}/seasons/{season_year}/{nba_season}/teams/{t_id}/statistics.{format_var}?api_key={your_api_key}"

  return requests.get(seas_stat_url).json()

#API Call to pull comments from reddit:
game_response = get_game_response(token_response, token_headers, game_links[i])
      get_comment_text(game_response, comment_list)

LIBRARIES TO IMPORT: 
•import requests
•import time
•import csv
•import re
•from collections import defaultdict
 
INSTALLATIONS NEEDED:
•Jupyter Notebook
Link to instructions on installing and using Jupyter Notebook: https://test-jupyter.readthedocs.io/en/latest/install.html 

API REFERENCE:
•https://developer.sportradar.com/docs/read/basketball/NBA_v7 
•https://www.reddit.com/dev/api/ 
  

HOW TO USE THE CODE:
1.Create an account on Sportradar and register for an NBA API KEY here: https://developer.sportradar.com/apps/mykeys 
2.Create an account on reddit and register for an API KEY here: https://www.reddit.com/prefs/apps 
3.In the Sportrader Script Section, Input your API key in line 7 (your_api_key = "[YOUR API KEY]"
4.In the Reddit Script, Input your API KEY and API secret in line 3 (client_auth = requests.auth.HTTPBasicAuth('[YOUR API KEY]','[YOUR API SECRET]')
5.In the Reddit Script, Input your username and password in line 4 (post_data = {'grant_type': 'password', 'username': '[username]', 'password': '[password]'})

NOTE: 
•For Sportradar, the API call rate is 1 call per second and 1,000 calls per month.
•For Reddit, the API call rate is 60 requests per minute.
•For each Sportradar call, the sleep rate is 1 second.
•For each Reddit call, the sleep rate is 1 second.
 
CHALLENGES ENCOUNTERED:
•Setting up the URL so the correct page is queried
•Preprocessing nested dictionaries to get the information needed
•Looping through Reddit the get comments
 
LIMITATIONS:
•We only got sport radar data at the season level, not the game day level.
•The Reddit comment thread is Large, so additional processing is required for a deeper analysis
•You have to re-run the code each time you want to get updated data.

CONTACT INFORMATION:
Email: sj3244@drexel.edu, db3533@drexel.edu, jb4575@drexel.edu, cce49@drexel.edu.  


