<h1 align="center">Voting Access in Colorado - Geospatial Analysis of the 2024 Presidential Election</h1>

# Background
The Safeguard American Voter Eligibility Act (SAVE Act) is a bill passed by the U.S. Congress in February 2026 and as of March 2026, is currently being debated in the Senate. If ratified, the SAVE Act will require voters to prove their citizenship to register to vote and provide an approved form of photo identification to vote in federal elections (Orey et al., 2026). Colorado is one of eight states where all registered voters can vote by mail (Elections Project Staff, 2026). Mail-in voting could be eliminated, or severely restricted, due to the photo ID requirement if the SAVE Act is passed. This analysis explores geographic access to voting locations across Colorado counties using spatial data. The goal is to quantify differences in access between regions and evaluate potential disparities in travel distance to voting sites. Rural Colorado generally has fewer polling locations and drop boxes, and many of these communities tend to lean Republican.

# Technology Used
**Python**
- [pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [GeoPandas](https://geopandas.org/en/stable/)

# Data
**ColoradoVotingAccessDataCleaning.ipynb** – Data merging, cleaning and exploration cleaning producing two datasets for analysis, county_df and location_df.
-	Datasets were joined on the variable ‘county’. 
-	Most cleaning involved formatting strings to ensure consistency across datasets.
-	The dataset for 2024 election results by Colorado county contained a MultiIndexed header resulting in the column “Total”, which represents the summation of all votes cast, also containing the label ‘Robert F. Kennedy Jr. / Nicole Shanahan’. This column was renamed “total votes”. The total votes were also summed by hand to ensure accuracy.
-	Votes for “Kamala D. Harris / Tim Walz” were named “democrat” and votes for “Donald J. Trump / JD Vance” were named republican. 
-	There were eight pairs of candidates represented in the dataset for 2024 election results by Colorado county with the majority of votes being for Kamala D. Harris / Tim Walz were and Donald J. Trump / JD Vance. Therefore, votes for the six other candidates were summed and represented as “other”.
-	The DataFrame county_df contains county level data with one entry for each county. This DataFrame should be used for any population wise calculations and counts. Its features include:
    -	county – the name of the Colorado county
    -	registered voters – the total number of registered voters in the county
    -	democrat – the total number of votes cast for Kamala D. Harris / Tim Walz
    -	republican – the total number of votes cast for Donald J. Trump / JD Vance
    -	other – the total number of votes cast for other candidates 
    -	total votes – the total number of votes cast
-	The DataFrame location_df contains voter site location information. This DataFrame contains the same features as county_df as well as:
    -	X and Y – coordinates for mapping
    -	site_type – the type of voting location (dropbox, early voting, polling location)
    -	geocoded_address – address formatted for GeoPandas

> [!CAUTION]
> Population and voting entries will be repeated in the DataFrame location_df if there are more than one voting site in a county, with each voting site within a county containing the same information for these variables. 

<img align="left" width="320" height="240" alt="colorado_total_votes_2024" src="https://github.com/user-attachments/assets/772b86cf-988f-4c92-a5ac-642b5bba8374" />
<img align="center" width="400" height="300" alt="colorado_top_counties_total_votes_2024" src="https://github.com/user-attachments/assets/5ebfc903-aea1-4058-b225-b3332404b911" />
<img align="right" width="400" height="300" alt="colorado_bottom_counties_total_votes_2024" src="https://github.com/user-attachments/assets/1b449a06-8a61-4fbe-b3ff-398919fec71f" />


 

## Data Access
- Polling station, dropbox and early voting location information:
https://geodata.colorado.gov/datasets/0b26c8161c1e4597816b107f0dba0d15_0/explore?location=39.934750%2C-102.798471%2C6

- 2024 presidential election results: 
https://demography.dola.colorado.gov/assets/html/county.html

- 2024 voting results:
https://results.enr.clarityelections.com/CO/122598/web.345435/#/summary

- Map data: 
https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html

# Analysis
<img width="2000" height="800" alt="colorado_county_maps_election_results_voting_locations_population_2024" src="https://github.com/user-attachments/assets/69a1ba21-9b59-47f3-9fee-e5b9b97f601b" />

# References
## Text
- Orey, W., Weil, M., & Lempert, J. (2026, February 2). Five Things to Know About the SAVE America Act. Bipartisan Policy Center. https://bipartisanpolicy.org/article/five-things-to-know-about-the-save-act/

- Elections Project Staff. (2026, February 20). Mail Voting is Safe and Secure. Bipartisan Policy Center. https://bipartisanpolicy.org/report/mail-voting-is-safe-secure/


