# ncaa_transitive_champions
Python notebook answering an NCAA-related championship question

Answering the Riddler Classic from https://fivethirtyeight.com/features/how-many-times-a-day-is-a-broken-clock-right/

Program was written to find the "transitive champions" for both the Men's and Women's NCAA Basketball seasons. A team is 
considered a transitive champion if they won the championship, or beat the team that won the championship, or beat the 
team that beat the team that won the championship, etc.

Program works in two major parts:
1) take text files containing data from https://www.masseyratings.com and parse to get the team names and winner/loser
   for every game in the season. Using that information, create a dictionary with team name as the key, and a set of every
   team that beat that team as the value
2) starting with the NCAA tournament champions (Virginia for the men, Baylor for the women), make a set of the teams that beat
   them. Then, look at a value from that set, get the teams that beat THEM from the dictionary, and create a union of the two
   sets. Continue this process until every team that has beaten one of the teams in that growing set has been included.

At this point, we have a set of every transitive champion. As it turns out, 359 of the 650 teams that played during the men's season
would be considered a transitive champion, as well as 1777 of the 2020 teams that played during the women's season.
