# Scrape LigaMX FBref data

Code for regular season table comes from: https://github.com/chmartin/FBref_EPL
I've only modified a thing or two to get it working with the apertura and clausura format

Code for scrape liguilla table is mine

For player stats and other features you can check this repository: https://github.com/parth1902/Scrape-FBref-data

First you need to set the URL of the season you want to scrape the data from, see the example below:
```
  res = requests.get("https://fbref.com/en/comps/31/2022-2023/2022-2023-Liga-MX-Stats")
```

Then you can use the functions to generate the dataframes, you have genTable for league table, league home/away table, regular season Apertura and regular season Clausura. genLiguilla is for Apertura Liguilla and Clausura Liguilla. 

You only give the function the two correspondent variables, for example the code below generate the dataframes for the Apertura Liguilla and for the Apertura regular season, then it creates a CSV file for each one:
```
  df_liguilla = genLiguilla(liguilla_apertura, liguilla_features)
  df_liguilla.to_csv("liguilla.csv", encoding="utf-8-sig")
  
  df_apertura = genTable(league_apertura, league_apertura_features)
  df_apertura.to_csv("apertura.csv", encoding="utf-8-sig")
```

Dataframe: 
![DF](https://github.com/franco-e-s-c/FBref-LigaMx-Scraper/blob/b9655d5d9e0d8f6cb6a1d695a99272baefd5b89a/img/df_general.jpg)

CSV: 
![](https://github.com/franco-e-s-c/FBref-LigaMx-Scraper/blob/b9655d5d9e0d8f6cb6a1d695a99272baefd5b89a/img/csv_liguilla.JPG)
