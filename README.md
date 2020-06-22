# CAPP 30122: Final Project
# Mapping Crimes at a Certain Day and hour with Mexico City Crime Data (Using DJANGO and SQLITE)

Team:
* Stephanie Ramos
* Oscar Noriega
* Jesica Ramirez


## Table of contents
* [Setup](#setup)
* Project overview (#project-overview)


## Setup
If you want to replicate this web service application, some modules must be installed.
See: [requirements.txt](requirements.txt)


## Project overview
Django interface: Calls the module views.py (http://127.0.0.1:8000/)

- get_data.py: Connects to Mexico CIty’s Open Data API and obtains crime data from 2018 and 2019, as well as the police precincts delimitation and police stations locations. Calls the module data_cleaning.py, and stores the clean databases on the data folder

- data_cleaning.py: Cleans the crimes database filtering by crimes that could affect the user depending on the way they travel.

- views.py: Returns the rendered site with the output. Calls the modules geocoding_helper.py and queries.py and the visualizations stored in the viz folder.

- geocoding_helper.py: Connects to Google Maps API and returns the number of precinct that the input location belongs to.

- queries.py: Performs the required queries of number of crimes on the crimes SQL database. Also, calls the modules shortest_distance.py and viz.py

- shortest_distance.py: includes a function that calculates the distance of the input location (in km.) to all police stations in CDMX and returns the closest one. 

- viz.py: Produces all four visualizations ( 2 maps and 2 bar graphs)
