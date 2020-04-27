# ETL-Project by Sarai Embaye, O.J. Ndebbio, Terry Potter
ETL Project Homework Assignment


I.  Project Description - The current economic market condition with respect to oil and gas is at an historical low. This has lead to numerous lay-offs and furloughs within the oil and gas energy sector.  I am curious to find out if the price of crude oil per barrel correlates to the unemployment rate on a national scale. (See graphs for historical USA unemployment rate and WTI crude oil prices, YTD and historical) filenames 'USA Unemployment 1955-2020.png', 'wti-crude-oil-prices-1946-2020.png', 
'wti-crude-prices-ytd-2020-04-23.png'

II.  Project Goals - create a database tracking unemployment rates and crude oil prices on an annual basis.


III.  Extraction (original data sources, formatting, source data description, and source decription)

Data Sources 

1. Data - Unemployment Rate, Source: Labour: Labour market statistics, Jan 1955 - Mar 2020, CSV Format

https://data.oecd.org/unemp/unemployment-rate.htm

The Organisation for Economic Co-operation and Development (OECD) is an international organisation that works to build better policies for better lives. Our goal is to shape policies that foster prosperity, equality, opportunity and well-being for all. 

Unemployment rate is the number of unemployed people as a percentage of the labour force, where the latter consists of the unemployed plus those in paid or self-employment. Unemployed people are those who report that they are without work, that they are available for work and that they have taken active steps to find work in the last four weeks. When unemployment is high, some people become discouraged and stop looking for work; they are then excluded from the labour force. This implies that the unemployment rate may fall, or stop rising, even though there has been no underlying improvement in the labour market.

2. Data - Spot Crude Oil Price: West Texas Intermediate (WTI), Dollars per Barrel Not Seasonally Adjusted, Jan 1946 to Mar 2020, CSV Format (Note: Spot price is current market value whereas futures anticipates a market value or price at an agreed delivery date in the future)

https://fred.stlouisfed.org/tags/series?t=oil

About Economic Research at the St. Louis Fed - The widely used FRED® data service is updated daily and allows 24/7 access to over 500,000 financial and economic data series from more than 85 public and proprietary sources.


IV.  Transformation of the Data (data cleaning and transformation required)

- Imported CSV's into Jupyter Notebook

1. The unemployment data was already annualized. (see unemp_data_transformation.png)
	a. renamed columns
	b. deleted unwanted columns
	b. deleted unwanted rows i.e. foreign countries (only presenting US data)
	c. deleted data segregated by male and female retaining only total unemployment

2. Crude oil data (see crude_oil_data_transformation.png)
	a. renamed columns
	b. data was on a daily basis
		i. created a column containing only the year
		ii. deleted the yyyy-mm-dd column
	c. dropped years less than 1955 to match the unemployment data
	d. groupedby year and calculated the yearly averages

V.  Load (final database, tables/collections, and why this was chosen) (see 'tables_data_from_pandas_query.png')

	The gist of my interests in these datasets is that I have worked in oil & gas for approximately 20 years.  For the first 	15 years or so of my career oil prices were good to really great.  So from a professional perspective life was good.  		About 5 years ago the oil and gas market crashed and the recovery has been slow especially in the deepwater sector.  

	With the most recent drop in oil prices I thought it would be interesting to see if there was a correlation historically 	between oil prices and unemployment on a national scale.  However, I am sure that low oil prices are very attractive to 		industries such as logistics and trucking, commercial airlines, and to consumers in general.
