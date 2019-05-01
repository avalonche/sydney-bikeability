# sydney-bikeability

Computing bikeability scores in Sydney for each local district. Assignment for DATA 2901.

# Bikeability Scores in Sydney 

This is based on the [WalkScore](https://www.walk.score.com/AU-NSW/Sydney) computed based on density, diversity, design, destination accessibility and distance to cycling infrastructure or transport. Can check if bikeability correlates to property values.

Availability of cafes, restaurants, shopping centres, road network, cycling infrastructure, connectivity to public transport, public parks and trees can be intergrated.

Correlation with median income and average monthly rent calculated from Census data from Australian Bureau of Statistics (ABS) 

## Datasets

SA2 data from ABS and bike sharing data:

StatisticalAreas.csv: *area id, area name, parent area id*

Neighbourhoods.csv: *area id, area name, land area, population, number of dwellings, number of business*

CensusStats.csv: *area id, median household income, avg monthly rent*

BusinessStats.csv:  *area id, num businesses, retail trade, accommodation and food, health care, ...*

BikeSharingPods.csv: *station id, name, num bikes, num scooters, latitude, longitude, description*

## Data Integration and Creation

Building database using PostgreSQL (access to database need to be provided) intergrating data from. At least one additional data set, from a web source using Web Scraping or Web-API. 

1. Sydney neighbourhood data (from CSV)
2. Census Data from neighbourhoods (population count + no of dwellings)
3. Cycling options in terms of of neighbourhoods (spatial join)

## Cyclability Analysis 

1. Formula used: 

*cyclability = z(population density)+z(dwelling density)+z(service balance)+z(bikepod density)*
Using z score assuming normal distribution 

| **Measure**  | **Definition** |**Data Source**|
| ------------- | ------------- |---------------|
| *population density*  | population divided by neighbourhood’s land area |Neighbourhoods.csv|
| *dwelling density*  | number of dwellings divided by neighbourhood land area |Neighbourhoods.csv|
|*dservice balance* |balance of selected business types in neighbourhood|BusinessStats.csv|
|*bikepod density* |number of bike-sharing pods per suburb divided by area|BusinessStats.csv|

2. Measure and Score in each neighbourhood in database. At least one index helpful for data integration and cyclability score
3. Correation between score and median annual household income or average weekly rent per neighbourhood

Include in calculation data inferred using machine learning or natural language processing. (e.g. count named entities about planned cycling infrastructure and geolocation)

## Documentation 

4 page + Appendix. Data integration and outcome.

1. **Dataset Description**: identify data source and how data obtained and pre-processed
2.  **Database Description**: which database schema was database integrated (diagram)
3. **Cyclability Analysis**: formula applied, overview of results. Can use text, highlight, graphical representation
4. **Correlation Analysis**: how well score correlate to median household income, if there is correlation with average weekly rent with neighbourhoods 

### Requirements 

Python Juptyer notebook in Python and SQL. Use Jupyter and PostgreSQL servers in labs. Any extra libraries not in labs need to be disclosed in documentation.

1. Source code for integration and analysis 
2. Report/documentation (up to 4 pages) 
3. Demo
4. Access to database with schema and processed data

