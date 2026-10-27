# SIS-1: Climate and Population Growth of Kazakhstan Cities

**Course:** Data Collection & Preparation, KBTU, Fall 2026  
**Student:** Nurzhan Kalmurat (ID 24B031138), individual work, team name `Kalmurat`

## What is this project
I collect real data from two different sources, clean it, merge it by city and check:
1. how the climate changes from the south to the north of Kazakhstan;
2. which cities have the most extreme climate;
3. if the climate of a city is connected with its population growth (1999-2023).

## Data sources
| Source | Type | Data |
|---|---|---|
| [Wikipedia: List of cities in Kazakhstan](https://en.wikipedia.org/wiki/List_of_cities_in_Kazakhstan) | static web page, `requests` + `BeautifulSoup` (robots.txt checked) | population 1979-2023, foundation year, status, province |
| [Open-Meteo Geocoding API](https://open-meteo.com/en/docs/geocoding-api) | REST API, JSON | latitude, longitude, elevation |
| [Open-Meteo Historical Weather API](https://open-meteo.com/en/docs/historical-weather-api) | REST API, JSON | daily weather for 2025 (temperature, rain, snow, wind, sunshine) |

## Repository
```
SIS_Kalmurat_Climate_Population.ipynb   main notebook (all steps with outputs)
report_Kalmurat.pdf                     written report
requirements.txt                        libraries
data/raw/                               raw HTML, raw scraped table, raw API answers
data/processed/                         clean and merged tables
figures/                                6 plots from the notebook
```

## How to run
```bash
pip install -r requirements.txt
jupyter notebook SIS_Kalmurat_Climate_Population.ipynb
```
Run all cells (Kernel -> Restart & Run All). Internet is needed, the API does not need a key. Full run takes about 1-2 minutes.

## Main results
- Latitude explains about 80% of the difference in year temperature: about 0.9 °C colder for every 1° to the north.
- The South was 13.5 °C on average in 2025, the North 5.8 °C. Turkistan has the hottest summer, Schuchinsk the coldest winter, Balqash the biggest difference between seasons.
- Cities with a warmer winter grew faster (Spearman rho = 0.63), but this is not causation: Astana is cold and grew +353% because it is the capital, western cities grow because of oil.
