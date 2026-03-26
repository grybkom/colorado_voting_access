<h1 align="center">Voting Access in Colorado - Geospatial Analysis of the 2024 Presidential Election</h1>

# Background
The Safeguard American Voter Eligibility Act (SAVE Act) is a bill passed by the U.S. Congress in February 2026 and as of March 2026, is currently being debated in the Senate. If ratified, the SAVE Act will require voters to prove their citizenship to register to vote and provide an approved form of photo identification to vote in federal elections (Orey et al., 2026). Colorado is one of eight states where all registered voters can vote by mail (Elections Project Staff, 2026). Mail-in voting could be eliminated, or severely restricted due to the photo ID requirement if the SAVE Act is passed. This analysis explores geographic access to voting locations across Colorado counties using spatial data. The goal is to quantify differences in access between regions and evaluate potential disparities in travel distance to voting sites. Rural Colorado generally has fewer polling locations and drop boxes, and many of these communities tend to lean Republican.

# Technology Used
**Python**
- [pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [GeoPandas](https://geopandas.org/en/stable/)

# Data
**ColoradoVotingAccessDataCleaning.ipynb** – Data merging, cleaning and exploration cleaning producing two datasets for analysis, county_df and location_df.


# Analysis
<img width="2000" height="800" alt="colorado_county_maps_election_results_voting_locations_population_2024" src="https://github.com/user-attachments/assets/69a1ba21-9b59-47f3-9fee-e5b9b97f601b" />

# References
## Text
- Orey, W., Weil, M., & Lempert, J. (2026, February 2). Five Things to Know About the SAVE America Act. Bipartisan Policy Center. https://bipartisanpolicy.org/article/five-things-to-know-about-the-save-act/

- Elections Project Staff. (2026, February 20). Mail Voting is Safe and Secure. Bipartisan Policy Center. https://bipartisanpolicy.org/report/mail-voting-is-safe-secure/


