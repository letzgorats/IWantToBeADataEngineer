![Image](https://github.com/user-attachments/assets/0c2191bf-e38f-4f49-827e-6562d1a1b2ed)

London, or as the Romans called it "Londonium"! Home to [over 8.5 million residents](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/bulletins/populationandhouseholdestimatesenglandandwales/census2021unroundeddata#population-and-household-estimates-england-and-wales-data) who speak over [300 languages](https://web.archive.org/web/20080924084621/http://www.cilt.org.uk/faqs/langspoken.htm). While the City of London is a little over one square mile (hence its nickname "The Square Mile"), Greater London has grown to encompass 32 boroughs spanning a total area of 606 square miles! 

![Image](https://github.com/user-attachments/assets/d3fa8817-ad76-44e9-bb76-a6ccaf883f8e)

Given the city's roads were originally designed for horse and cart, this area and population growth has required the development of an efficient public transport system! Since the year 2000, this has been through the local government body called **Transport for London**, or *TfL*, which is managed by the London Mayor's office. Their remit covers the London Underground, Overground, Docklands Light Railway (DLR), buses, trams, river services (clipper and [Emirates Airline cable car](https://en.wikipedia.org/wiki/London_cable_car)), roads, and even taxis.

The Mayor of London's office make their data available to the public [here](https://data.london.gov.uk/dataset). In this project, you will work with a slightly modified version of a dataset containing information about public transport journey volume by transport type. 

The data has been loaded into a **Snowflake** database called `TFL` with a single table called `JOURNEYS`, including the following data:

## TFL.JOURNEYS

| Column | Definition | Data type |
|--------|------------|-----------|
| `MONTH`| Month in number format, e.g., `1` equals January | `INTEGER` |
| `YEAR` | Year | `INTEGER` |
| `DAYS` | Number of days in the given month | `INTEGER` |
| `REPORT_DATE` | Date that the data was reported | `DATE` |
| `JOURNEY_TYPE` | Method of transport used | `VARCHAR` |
| `JOURNEYS_MILLIONS` | Millions of journeys, measured in decimals | `FLOAT` |

Note that *in Snowflake all databases, tables, and columns are **upper case*** by default.

You will execute SQL queries to answer three questions, as listed in the instructions.



## DataFrame available as `most_popular_transport_types`
```SQL
-- most_popular_transport_types
SELECT TFL.JOURNEYS.JOURNEY_TYPE, SUM(TFL.JOURNEYS.JOURNEYS_MILLIONS) AS TOTAL_JOURNEYS_MILLIONS
FROM TFL.JOURNEYS
GROUP BY TFL.JOURNEYS.JOURNEY_TYPE
ORDER BY TOTAL_JOURNEYS_MILLIONS DESC
```
![Image](https://github.com/user-attachments/assets/5164d7e9-d342-4216-a32d-ba6da2d639f9)
![Image](https://github.com/user-attachments/assets/d5b5d6b1-eb51-4b5b-b29a-0610e1a4d9f3)


## DataFrame available as `emirates_airline_popularity`
```SQL
-- emirates_airline_popularity
SELECT TFL.JOURNEYS.MONTH,TFL.JOURNEYS.YEAR, ROUND(SUM(TFL.JOURNEYS.JOURNEYS_MILLIONS),2) AS ROUNDED_JOURNEYS_MILLIONS
FROM TFL.JOURNEYS
WHERE TFL.JOURNEYS.JOURNEY_TYPE = 'Emirates Airline'
	AND TFL.JOURNEYS.JOURNEYS_MILLIONS IS NOT NULL
GROUP BY TFL.JOURNEYS.MONTH,TFL.JOURNEYS.YEAR
ORDER BY ROUNDED_JOURNEYS_MILLIONS DESC
LIMIT 5 
```
![Image](https://github.com/user-attachments/assets/2528ef39-0fe9-4c5d-8f5b-a909c32588fc)
![image](https://github.com/user-attachments/assets/77cbcfc1-003b-4422-ba32-3e76c7e7fcff)


## DataFrame available as `least_popular_years_tube`
```SQL
-- least_popular_years_tube
SELECT TFL.JOURNEYS.YEAR,TFL.JOURNEYS.JOURNEY_TYPE, SUM(TFL.JOURNEYS.JOURNEYS_MILLIONS) AS TOTAL_JOURNEYS_MILLIONS
FROM TFL.JOURNEYS
WHERE TFL.JOURNEYS.JOURNEY_TYPE = 'Underground & DLR'
GROUP BY TFL.JOURNEYS.YEAR,TFL.JOURNEYS.JOURNEY_TYPE
ORDER BY TOTAL_JOURNEYS_MILLIONS
LIMIT 5
```
![image](https://github.com/user-attachments/assets/bc47d78c-4e53-4533-8af2-b82553fc5193)
![image](https://github.com/user-attachments/assets/71e9e421-08c2-4750-aa9f-b4258ae457b8)
