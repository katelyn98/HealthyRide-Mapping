# Understanding the Analyses

All of the following analyses were generated in the jupyter notebookes located in the [`notebooks` folder](https://github.com/katelyn98/HealthyRide-Mapping/tree/master/Notebooks). The primary notebook files that have a majority of the analyses are [PGH ML Dataset](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Notebooks/PGH%20ML%20DataSet.ipynb), [PGHCenpy](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Notebooks/PGHCenpy.ipynb), and [NYC Analyses](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Notebooks/NYC%20Analyses.ipynb). There are other analyses scattered throughout the other notebooks. 


---
## Pittsburgh, PA

The bike sharing program in Pittsburgh, PA is called [Healthy Ride](https://healthyridepgh.com/) and is advertised as the public bike share system for Pittsburgh, PA. It is powered by [NextBike](https://www.nextbike.co.uk/en/) which is a company in the UK that provides bikes and infrastructure for a bike sharing program. Healthy Ride was first established in Pittsburgh, in May 2015 and has since expanded to 100 stations and 550 bikes. Below you can see various stages of the program over the past few years.

2015                       |             2018          |          2020            |
:-------------------------:|:-------------------------:|:-------------------------:
![width="40"](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_pgh/2015q2pgh.png?raw=true)  |  ![](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_pgh/2018q4pgh.png?raw=true) | ![](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_pgh/2020q4pgh.png?raw=true)

### Analyses

Several datasets and APIs were used to create the following visualizations. These datasets are not released on this repo, but I can provide access to the datasets I have used upon request. I also provide direct links to the public datasets below.

**Datasets**
- [Healthy Ride Station Locations](https://data.wprdc.org/dataset/healthyride-stations)
- [Healthy Ride Trip Data](https://data.wprdc.org/dataset/healthyride-trip-data)
- [ACS 2019 5 year estimates](https://data.census.gov/cedsci/table?q=ACSDP5Y2019.DP03%20Pittsburgh%20city,%20Pennsylvania&t=Commuting%3AEmployment%3AIncome%20and%20Poverty&g=1400000US42003020100,42003020300,42003030500,42003040500,42003050100,42003050600&tid=ACSDP5Y2019.DP03&hidePreview=true) for employment, population, and commuting trends. *Note: All census tracts were searched for; here is just a sample of 6 of them*
- Points of interest using the [OverPass API](https://overpass-turbo.eu/s/15Fj) for [OpenStreetMap OverPass Turbo](https://overpass-turbo.eu/)
- Transit Score, Bike Score, and Walk Score from [Walk Score API](https://www.walkscore.com/professional/walk-score-apis.php)
- [Poor housing conditions](https://data.wprdc.org/dataset/allegheny-county-poor-condition-residential-parcel-rates)

#### Demographics

A short note about the demographics data for Pittsburgh: I had difficulty accessing Allegheny County census tract data from the `cenpy` Python library. I was able to get data for the census tracts that are considered to be a part of the Pittsburgh metro area for the race attributes. As a result, the maps presented for visualizing race by census tract look slighlty different than the rest of the Pittsburgh maps. 

<p align="center">
  <b> ACS 2019 5 year estimate for population 16 years or older </b>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/population.png" width=550>
  <br>
  <i> Caption here </i>
</p>

<p align="center">
  <b> ACS 2019 5 year estimate for race by census tract </b>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/PGHrace_combo.png" width=750>
  <br>
  <i> The figure on the left shows a high percentage of the population in a majority of the census tracts in Pittsburgh are White. The figure on the right shows a cluster of yellow and orange colored census tracts in the middle of Pittsburgh representing census tracts where a high percentage of the population Black or African American. Out of the 100 bike stations, aprroximately 9 are within marginilized census tracts. </i>
</p>

#### Commuting to Work

<p align="center">
  <b> ACS 2019 5 year estimates for commuting to work </b>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/Commutingtrends.png">
  <br>
  <i> caption here </i>
</p>

<p align="center">
  <b> ACS 2019 5 year estimates for mean travel time to work (minutes)</b>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/meantraveltime.png" width=550>
  <br>
  <i> Caption here </i>
</p>

#### Household Income

<p align="center">
  <b> ACS 2019 5 year estimates for income </b>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/incomecombo.png" width=750>
  <br>
  <i> Caption here </i>
</p>

#### Poor Housing Conditions

<p align="center">
  <b> Allegheny County Poor Housing Conditions </b>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/poorhousingconditions.png" width=550>
  <br>
  <i> Caption here </i>
</p>

#### Infrastructure

<p align="center">
  <b> Bike Score and Walk Score </b> from <a href="https://www.walkscore.com/professional/">walkscore.com</a>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/WalkBikecombo.png" width=750>
  <br>
  <i> The figure on the left shows regions of Pittsburgh that are suitable or not for biking. The figure on the right shows regions of Pittsburgh that are suitable or not for walking. To see ore about how the scores are decided for a particular area, check out Walk Score's <a href="https://www.walkscore.com/methodology.shtml">methodology</a>.  </i>
</p>

#### Points of Interest

*Visualization Coming Soon*

### Demand Prediction

#### Historical Data

2018 Outflow       |     2019 Outflow |    2020 Outflow      | Predicted Demand using mean |
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![width="40"](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/outflow%202018.png)  |  ![](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/outflow%202019.png) | ![](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/outflow%202020.png) | ![](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/predmean.png)

#### Spatially Sensitive (*preliminary*)

<p align="center">
  <b> Predicting Outflow using spatial & infrastructural attributes & demographics </b>
  <br>
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/scorepredoutflow.png" width=550>
  <br>
  <i> Caption here </i>
</p>

---
## New York City, NY

The bike sharing program in New York City, NY is called [Citi Bike](https://www.citibikenyc.com/) and is known as the nation's largest bike sharing program with 19,000 bikes and over 1,000 stations. Citi Bike is powered by [Lyft](https://www.lyft.com/bikes/new-york-city-ny). Citi Bikes were first established in NYC in 2013 with approximately 600 bike stations around Manhatten. Below you can see various stages of the program over the past few yeras.

December 2013        |      August 2015          |   February 2017    | September 2018   | December 2019  | October 2020     | January 2021 |
:-------------------:|:-------------------------:|:------------------:|:----------------:|:--------------:|:----------------:|:------------:|
![December 2013 bike station locations](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_nyc/201312nyc.png)  |  ![August 2015 bike station locations](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_nyc/201508nyc.png) | ![February 2017 bike station locations](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_nyc/201702nyc.png) | ![September 2018 bike station locations](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_nyc/201809nyc.png) | ![decmber 2019 bike station locations](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_nyc/201912nyc.png) | ![October 2020 bike station locations](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_nyc/202010nyc.png) | ![January 2021 bike station locations](https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/stations_nyc/202101nyc.png)

### Analyses

Several datasets and APIs were used to create the following visualizations. These datasets are not released on this repo, but I can provide access to the datasets I used upon request. I also provide direct links to the public datasets below.

**Datasets**


#### Demographics

<p align="center">
  <img src="https://github.com/katelyn98/HealthyRide-Mapping/blob/master/Results/FinalAnalyses/Plasma/NYCrace_combo.png" width=650>
</p>

#### Infrastructure

*Coming Soon*

#### Points of Interest

*Coming Soon*

### Demand Prediction

#### Historical Data

#### Spatially Sensitive
---
## Chicago, IL (*Working Progress*)

The bike sharing program in Chicago, IL is called [Divy Bike](https://www.divvybikes.com/) and is also powered by [Lyft](https://www.lyft.com/bikes/chicago-il).
