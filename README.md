# Redwood Tree Macroscope Exploratory Data Analysis

## Introduction

The purpose of this data exploration project is to offer an extended analysis on the study conducted by Tolle et al. to analyze the microclimate surrounding a 70-meter tall Redwood tree. Wireless sensors were used to record variations in spatial and temporal dynamics, taking into account essential environmental characteristics such temperature, humidity, as well as direct and reflective solar radiation.
These photosynthetically active radiations (PARs) help scientists derive important biological and environmental insights, like the amount of energy available for photosynthetic activities and carbon balance in the surrounding forest region. Furthermore, these findings offer an understanding to scientists on natural processes like the flow of sap through trees. 

The data collection process is operated by a network of sensors called macroscopes, a technology that must be protected from the weather while at the same time, exposed to track the microclimatic changes.  First, these sensor nodes are thoroughly calibrated and then scattered around the tree vertically and horizontally. Vertically, they are placed both near the base and tip, from 15 to 70 meters above the ground with a 2-meter spacing. Horizontally, they are placed 0.1 to 1.0 meters across the trunk's radius. Nodes can also be described by their direction, whether they face the east or the west. The substantial variations one observes create gradients that are observable through plotting and performing explanatory analysis. In addition, readings from the sensors are taken once every five minutes, equivalent to one epoch, and the data proceeds to be transmitted to a database. The data in sonoma-data-log.csv contains data taken from the logging itself and the separate network file is there to compensate for the loss data in the loggings in the case of unexpected failures in battery and such. Conversely, the logging file can do the same for the network. Through inspection, one notices that the data collection process differs between the two files, and these differences should be taken into consideration.

## Data

> Gathering data on the environmental dynamics around 70-meter tall redwood tree for 44 days requires robust system design and a careful deployment methodology.

The dataset we are exploring in this project is the sonoma-data.csv. It is further split into two separate datasets by their retrieval method, whether it was offered by the nodes (sonoma-data-log.csv) or received by the network (sonoma-data-net.csv). In the original form, these datasets contain numerous outliers, inconsistencies between the two data retrieval methods, and missing values, all which require wrangling before we can extract any useful insights. The environmental changes and patterns around the tree were recorded from April 27, 2004 to June 10, 2004, a total of 44 days.

The main variables of interest in this study are: temperature, humidity, the amount of incident or direct radiation, and reflective or indirect radiation. 

* ``result_time``: captures the timestamp the result was taken from the sensor
* ``epoch``: arbitrary integer that tells time
* ``nodeid``: id of the node sensor
* ``parent``: parent node
* ``voltage``: battery voltage of the sensors (analog and digital)
* ``depth``: sensor's position in the network
* ``humidity``: raw humidity
* ``humid_temp``: raw temperature
* ``humid_adj``: humidity adjusted based on temperature
* ``hamatop``: incident (direct) levels of PAR
* ``hamabot``: reflected (ambient) levels of PAR

Here are the first few rows from the entire dataset.
```
result_time, epoch, nodeid, parent, voltage, depth, humidity, humid_temp, humid_adj, hamatop, hamabot
2004-05-07 18:24:58.666424,2812,119,5,220,2,95.3567,12.6678,92.1444,4218.18,0
2004-05-07 18:24:58.805974,2812,105,129,223,3,96.9957,12.6482,93.7072,9363.23,0
2004-05-07 18:24:59.075427,2812,113,118,222,4,94.5031,12.4522,91.2718,9405.41,0
2004-05-07 18:24:59.355354,2812,138,5,223,2,96.8828,12.658,93.6018,9363.23,0
2004-05-07 18:24:59.675467,2812,127,42,222,3,97.8044,12.3836,94.409,4702.7,0
```

## Plots


