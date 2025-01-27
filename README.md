**SCL Data - Data Ecosystem Working Group**


<center>
<p float="left">
  <img src="https://scldata.iadb.org/assets/iadb-7779368a000004449beca0d4fc6f116cc0617572d549edf2ae491e9a17f63778.png" width="17%" style="margin:50px 50px">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1f/Mapbox_logo_2019.svg/1200px-Mapbox_logo_2019.svg.png" width="20%" style="margin:50px 50px">
</p>
</center>

<h1 align="center"> Spatial coverage of social infrastructure  </h1>


## Index:
--- 
- [Description and Context](#description-and-context)
- [Structure](#structure)
- [Methodology](#methodology)
- [Author(s)](#authors)

## Description and Context
---

The right to health, education and justice, among others, require social infrastructure on the part of the state to achieve quality access. However, social infrastructure is not always homogeneously distributed throughout the territory of the countries and in many occasions there is unequal access in marginalized populations. (Weiss, 2018). Access to a public service must be studied from a spatial dimension. It is not enough that a person has a popular health insurance, is enrolled in a school or has a membership to a library. Travel costs, whether in terms of distance, time or opportunity cost, constitute an obstacle to access to public services when the beneficiary has limited resources. (Buzza, 2011).

This tool will be beneficial to give an initial assessment of infrastructure availability in the region, guide research, and the possible orientation of public policy decisions.

This analysis focuses on the coverage of education and health facilities. For each country and region we show the percentage of uncovered people for each type of infrastructure. The data from facilities is obtained from official sources when available, and from Open Street Maps (OSM) in case public information is not found. The information from the population of interest is obtained from the Facebook project - High-resolution population density maps. Finally, we use the Mapbox API to calculate the isochrones and determine the percentage of the population that is not covered using a driving time of 15, 30 and 45 minutes. Combining said sources we perform spatial join to identify the population without access to the service with the defined profile.


## Structure
---

This repository contains the code of the *Spatial coverage of social infrastructure tool.* 

- [Shiny app](https://bid-data.shinyapps.io/infrastructure_coverage/)

- [Code](https://github.com/BID-DATA/analytics_spatial_coverage_scl)


## Methodology
---

-	We created a database of amenities for each social infrastructure.

<center>
<img src="./app/assets/hospitals_lac.png" width="500">
</center>


- For this study we defined *coverage* with three driving profiles *15,30 and 45 minutes* by private transport from at least one social service infrastructure. 

-	We used the Mapbox API to calculate distance measurements to each georeference using the desired profile and time. 



<center>
<img src="./app/assets/isochrones.png" width="500">
</center>

- We used the High-Resolution Population Density Map to obtain a location layer of the population of interest in order to perform the coverage analysis.
<center>
<img src="./app/assets/pop_lac.png" width="500">
</center>

- The population outside the proximity polygons were identified. 

<center>
<img src="./app/assets/uncovered_lac.png" width="500">
</center>

-	Outcome metrics were created at the national level and state level to identify the population without coverage.

<center>
<img src="./app/assets/pct_lac.png" width="500">
</center>
### References

- Buzza, C. et al. Distance is relative: unpacking a principal barrier in rural healthcare. J. Gen. Intern. Med. 26, 648–654 (2011).
- Weiss, D. J. et al. A global map of travel time to cities to assess inequalities in accessibility in 2015. Nature 553, 333–336 (2018).


### Authors
- [Roberto Sánchez A.](https://github.com/rsanchezavalos)
- [Luis Tejerina.](https://github.com/luistejerina)
- [María Reyes Retana](https://github.com/mariarrt94)