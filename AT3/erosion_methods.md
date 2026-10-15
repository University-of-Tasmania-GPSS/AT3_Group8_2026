# Methodology

A significant portion of the methodology in the erosion component of the project was dedicated to researching what components contributed to erosion and subsequently, what datasets were required. It was concluded that this project would use the same (where possible) factors as a study undertaken by Abuodha and Woodroffe (2010) whose study examined the vulnerability of coasts due to sea level rise.
One of the biggest challenges in undertaking the project was issues relating to this as there was no real guidance for how we should undertake the project. One of the most glaring issues in creating the erosion model is how wave strength was going to be modelled as this is a key contributor to coastal erosion. As there is no wave buoy data in the vicinity of the subject area and certainly not in the Derwent Estuary, a wave model had to be derived using data sourced from external sources. The European Union’s satellite program has publicly available satellite derived climate history data which was able to be used to model wave height. Wind data for the past 5 years was extracted from the ERA5 site which provided easting and northing direction components of wind. With the help of AI, a fetch model was created with the workflow moving as follows.
1.	Points were created every 200 metres along the shore with rays created 22.5 degrees apart around each point (every compass point)
2.	The rays run until a ray from a point hits a piece of land meaning that the waves are effectively modelled through ray distance as any point on the shore is going to have a 0-distance ray and a ray travelling to the other side of the river is going to register a high reading (under the assumption that waves need distance to increase in strength).
3.	The wind was then added to this data by multiplying the ray value with how often (an above 5 metre per second) wind blows from that particular ray and scaling this value between 0 and 1. A coastline point with high wind frequency and large ray distance returned a 1 reading.
Two models were used to visualise the erosion – a coastal vulnerability index and fuzzy gamma overlay. 
Coastal Vulnerability Index is the standard erosion modelling technique. It uses the following equation 
```{figure} figures/CVI_Equation.png
:alt: Coastal Vulnerability Index equation
:width: 60%

The Coastal Vulnerability Index (CVI) equation (USGS, n.d.).
```

Due to the nature of the equation, in order for a cell to read as high susceptibility, it must score high on multiple factors and cannot be skewed by one factor being extremely high. With this in mind a particular downside to this model is the fact that each factor is treated with equal weight whereby geomorphology is likely to be more of a factor than the tidal range at a certain point but the equation does not affect that.

Fuzzy Gamma Overlay is a far more complex method and AI was required to code this technique. It is a spatial technique that can be completed in services such as ArcGIS which also uses the 0-1 range of each raster as seen in the CVI but models the drivers differently. A gamma value is set in this model decided by the user which alters how much a single driver can affect the overall cell value. The gamma value in this project was set high in order to differentiate from the CVI whereby a cell which may be around 0.5 for every factor except 1 very high factor, a very high value for the cell is still returned.

In terms of general coding methodology, the workflow was as follows.:
1.	Set Up – Required libraries were downloaded, data imported and settings such as the coordinate system, grid resolution, gamma values and coastline point differences were set. 
2.	The ELVIS derived 1 metre DEM’s were stitched together as the data was exported from ELVIS as smaller bounding boxes,
3.	Each dataset was clipped onto the bounding box and projected onto the correct MGA2020 coordinate system. 
4.	The fetch calculations were completed (see earlier workflow).
5.	The geology dataset was reclassified with each type of geology given a value 1-5 (5 being most susceptible) based on an erodibility table from (Moosdorf et al., 2018) which defined what type of rocks experience high erodability.

::::{grid} 1 1 2 2

:::{card}
```{image} figures/erodability_index_numbers.png
:alt: Erodibility index values by lithology
:width: 100%
```
Erodibility index values.
:::

:::{card}
```{image} figures/erodability_index_legend.png
:alt: Legend for the erodibility index
:width: 100%
```
Legend.
:::

::::

6.	The Geology, Slope, Wave Exposure, Distance to Shoreline and storm surge datasets were then all scaled to return a cell value between 0 and 1. 
7.	The two models were then created with the data outputted for use in the sinkhole section of the project.
8.	Maps were produced to visualise the outputs. 
