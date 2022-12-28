---
title: "A Descriptive Analysis of Airbnb accomodations in Bologna"
date: 2022-12-22T20:38:41+01:00
draft: false
tags: ["r","programming", "descriptive analysis", "airbnb"]
categories: ["uni", "r"]
---

**Language used**: R

**Database used**: "listing.csv" from the website <http://insideairbnb.com/get-the-data/> composed by a mix of 18 qualitative and quantitative variables and 3896 cases.


|             **Packages used:**        |
|---------------------------------------|
| **dplyr**: to obtain a general descriptive analysis of the data.    |                                                                    
| **ggplot2**: to create graphs      |                  
| **ggmap**: to be able to show maps     |  
| **RColorBrewer**: to assign colors to the heatmap visualization     |  
| **osmdata**: to obtain the geographic coordinates of the city of Bologna      |  
| **hrbrthemes**: to obtain more ggplot themes    | 

**Variables description**:

| Qualitative variables                   | Quantitative variables                                                                                                    |
|---------------------------------------|---------------------------------|
| **name**: Name of the listing   | **id** : Airbnb's unique identifier for the listing                                                                       |
| **host_name**: Name of the host. Usually just the first name(s).    | **host_id** : Airbnb's unique identifier for the host/user                                                                      |
| **room_type**: Entire home/apt,Private room,Shared room,Hotel      | **latitude**: Uses the World Geodetic System (WGS84) projection for latitude and longitude.                                                                                    |
| **neighbourhood_group**: N/A | **longitude** : Uses the World Geodetic System (WGS84) projection for latitude and longitude.                                                                                 |
|                                           | **price** : daily price in local currency                                                                                |
|                                           | **minimum_nights**: minimum number of night stay for the listing (calendar rules may be different)                                    |
|                                           | **number_of_reviews**: The number of reviews the listing has                                                                                    |
|                                           | **last_review**: The date of the last review                                                                |
|                                           | **reviews_per_month**: Number of reviews per month                                                         |
|                                           | **calculated_host_listings_count**: The number of listings the host has in the current scrape, in the city/region geography. |
|                                           | **availability_365**: avaliability_x. The availability of the listing x days in the future as determined by the calendar. Note a listing may not be available because it has been booked by a guest or blocked by the host.                |
|                                           | **number_of_reviews_ltm**: The number of reviews the listing has (in the last 12 months)                                                  |
|                                           | **licence**: The licence/permit/registration number                                                                       |

### Descriptive analysis

**Translation of some words**
| Spanish                  | English                                                                                                     |
|---------------------------------------|---------------------------------|
| Barrio/s | Neighbourhood/s                                                                       |
| Mediana de los precios     | Median of prices                                                                                    |
| Mediana de las reseñas |  Median of number of reviews                                                                              
| Mediana de número mínimo de noches |  Median of minimum nights                                                                              
| Casa    | House                                                                      |
| Habitación de Hotel |  Hotel room                                                                              
| Habitación privada |  Private room                                                                             
| Habitación compartida |  Shared room|
| Latitud |  Latitud|
| Longitud |  Longitude|
| Tipología de alojamiento |  Accomodation type|
| Precio |  Price |

**Overall summary**
![table_summary](/taller1_airbnb_table_summary.png)

For further analysis, it was decided to take into consideration the median values as in the dataset there are some outliers.
Eg. Minimum number of nights set at 365 or price per night set at 15.365 Euros for an accomodation that does not even show up on the Airbnb platform.

![](/taller1_airbnb_table_2.png)

**Median of price and n. of reviews depending on accomodation type**
![](/taller1_airbnb_scatterplot.png)

Rent an entire apt or house is the most popular option among Airbnb's customers when staying in Bologna.

**Median of price and n. of reviews per neighbourhood showed on a map**
![](/taller1_airbnb_map_bologna.png)

Highest median number of reviews and price:
- Porto - Saragozza (close to the city center "fuori le mura", most populated neighbourhood, close to the main train station)
- Santo Stefano (city center "dentro le mura")

**Accomodation type available to stay for a weekend (two or less nights) with a budget of maximum 25 Euros and in which neighbourhood**
![](/taller1_airbnb_hist.png)

Most chosen option for a student's budget for a weekend getaway:
- Private room
- In Santo Stefano or San Donato-San Vitale neighbourhood (city center)